# Java Security Checklist
*Devoxx Poland 2025 – Tomasz Janczewski*

## 1. Walidacja i sanityzacja danych wejściowych
- [ ] **Nigdy nie ufaj danym od użytkownika** – waliduj i filtruj wszystkie dane wejściowe.
- [ ] **Sanityzuj** dane przekazywane do frontendu (np. za pomocą HtmlUtils, jsoup).

## 2. Ochrona przed SQL Injection
- [ ] Używaj **PreparedStatement** zamiast dynamicznego budowania zapytań.
- [ ] Preferuj **ORM** (Hibernate, JPA) z bezpiecznym mapowaniem parametrów.
- [ ] Nigdy nie wstawiaj surowych danych użytkownika do zapytań SQL.

## 3. Ochrona przed Cross-Site Scripting (XSS)
- [ ] Escapuj wszystkie dane wyświetlane na stronie.
- [ ] Stosuj odpowiednie nagłówki bezpieczeństwa (np. Content-Security-Policy).
- [ ] Testuj aplikację pod kątem XSS (np. za pomocą OWASP ZAP).

## 4. Kontrola dostępu i autoryzacja
- [ ] **Nie polegaj wyłącznie na rolach** – weryfikuj dostęp do zasobów na poziomie identyfikatora użytkownika.
- [ ] Nigdy nie udostępniaj danych na podstawie przekazanego userId bez sprawdzenia, czy należy do zalogowanego użytkownika.
- [ ] Korzystaj z narzędzi frameworka (np. Spring Security) do egzekwowania reguł dostępu.

## 5. Bezpieczne przechowywanie i hashowanie haseł
- [ ] Hashuj hasła użytkowników z użyciem **BCrypt** lub Argon2 (nigdy nie używaj MD5/SHA1).
- [ ] Nie zapisuj haseł wprost, nawet zaszyfrowanych.

## 6. Zarządzanie sekretami i konfiguracją
- [ ] Przechowuj klucze API, hasła, sekrety poza repozytorium kodu (np. w Spring Cloud Vault, HashiCorp Vault, zmiennych środowiskowych).
- [ ] Regularnie audytuj konfigurację pod kątem wycieków.

## 7. Bezpieczeństwo API
- [ ] Zabezpiecz wszystkie endpointy REST – autoryzacja i uwierzytelnianie (Spring Security, OAuth2/JWT).
- [ ] Ograniczaj dostęp CORS tylko do zaufanych domen.

## 8. Eliminacja podatności w bibliotekach
- [ ] Regularnie skanuj zależności narzędziem **OWASP Dependency-Check** lub Snyk.
- [ ] Aktualizuj zależności do najnowszych wersji.

## 9. Nagłówki bezpieczeństwa HTTP
- [ ] Ustaw nagłówki: Content-Security-Policy, X-Frame-Options, X-Content-Type-Options, Strict-Transport-Security.
- [ ] Zawsze wymuszaj HTTPS.

## 10. Testowanie bezpieczeństwa aplikacji
- [ ] Stosuj automatyczne testy bezpieczeństwa (np. OWASP ZAP, Snyk).
- [ ] Przeprowadzaj regularne testy penetracyjne i code review.

---

**Pamiętaj:**  
Bezpieczeństwo to proces, nie jednorazowe zadanie.  
Weryfikuj, edukuj zespół i aktualizuj swoją wiedzę!

---

*Więcej przykładów znajdziesz w tym repozytorium oraz w materiałach z prezentacji.*
