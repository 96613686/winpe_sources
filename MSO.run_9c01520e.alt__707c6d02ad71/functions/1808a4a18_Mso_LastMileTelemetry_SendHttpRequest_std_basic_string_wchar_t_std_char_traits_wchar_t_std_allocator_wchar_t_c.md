# Mso::LastMileTelemetry::SendHttpRequest(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,Mso::LastMileTelemetry::MeasureValue &,bool,bool,int)

- ea: `0x1808a4a18`
- end: `0x1808a5e43`
- name: `?SendHttpRequest@LastMileTelemetry@Mso@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@00AEAV34@AEAUMeasureValue@12@_N3H@Z`
- size: `5163`
- prototype: `__int64 __usercall@<rax>(LPCWSTR pswzServerName@<rcx>, LPCWSTR pwszObjectName@<rdx>, LPCWSTR pwszVerb@<r8>, __int64, char, char, int)`
- caller_count: `4`
- callee_count: `22`
- tags: `reparse_path`

## callers

- `0x180890440`
- `0x1808a4550`
- `0x1808a6380`
- `0x1818e7abc`

## callees

- `0x180003890`
- `0x18001af02`
- `0x18001d310`
- `0x180028b74`
- `0x180029310`
- `0x18002b13c`
- `0x1800b65ac`
- `0x1800f5e44`
- `0x18014a2b0`
- `0x18016bcd0`
- `0x18016c768`
- `0x18016c820`
- `0x18016c950`
- `0x18016ccb8`
- `0x18016e05c`
- `0x18030b960`
- `0x180485240`
- `0x1805452dc`
- `0x1808a4a18`
- `0x1808a5e44`
- `0x1808a5e8c`
- `0x1808a5edc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1808a4e76`
- `KERNEL32!GetLastError` at `0x1808a4eaf`
- `KERNEL32!GetLastError` at `0x1808a4ee3`
- `KERNEL32!GetLastError` at `0x1808a4f17`
- `KERNEL32!GetLastError` at `0x1808a567b`
- `KERNEL32!GetLastError` at `0x1808a4e76`
- `KERNEL32!GetLastError` at `0x1808a4eaf`
- `KERNEL32!GetLastError` at `0x1808a4ee3`
- `KERNEL32!GetLastError` at `0x1808a4f17`
- `KERNEL32!GetLastError` at `0x1808a567b`
- `KERNEL32!QueryPerformanceCounter` at `0x1808a4ccf`
- `KERNEL32!QueryPerformanceCounter` at `0x1808a4e18`
- `KERNEL32!QueryPerformanceCounter` at `0x1808a4ccf`
- `KERNEL32!QueryPerformanceCounter` at `0x1808a4e18`
- `KERNEL32!QueryPerformanceFrequency` at `0x1808a4be3`
- `KERNEL32!QueryPerformanceFrequency` at `0x1808a4be3`
- `MSVCP140!?setw@std@@YA?AU?$_Smanip@_J@1@_J@Z` at `0x1808a5257`
- `MSVCP140!?setw@std@@YA?AU?$_Smanip@_J@1@_J@Z` at `0x1808a5257`
- `MSVCP140!??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@H@Z` at `0x1808a528b`
- `MSVCP140!??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@H@Z` at `0x1808a528b`
- `MSVCP140!?fill@?$basic_ios@_WU?$char_traits@_W@std@@@std@@QEAA_W_W@Z` at `0x1808a527b`
- `MSVCP140!?fill@?$basic_ios@_WU?$char_traits@_W@std@@@std@@QEAA_W_W@Z` at `0x1808a527b`
- `MSVCP140!??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x1808a5239`
- `MSVCP140!??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x1808a5239`
- `MSVCP140!??1?$basic_ios@_WU?$char_traits@_W@std@@@std@@UEAA@XZ` at `0x1808a544c`
- `MSVCP140!??1?$basic_ios@_WU?$char_traits@_W@std@@@std@@UEAA@XZ` at `0x1808a544c`
- `MSVCP140!?_Xlength_error@std@@YAXPEBD@Z` at `0x1808a5d64`
- `MSVCP140!?_Xlength_error@std@@YAXPEBD@Z` at `0x1808a5d64`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1808a501e`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1808a501e`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1808a5556`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1808a5b77`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1808a5556`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1808a5b77`
- `CRYPT32!CryptHashCertificate` at `0x1808a4f89`
- `CRYPT32!CryptHashCertificate` at `0x1808a521c`
- `CRYPT32!CryptHashCertificate` at `0x1808a4f89`
- `CRYPT32!CryptHashCertificate` at `0x1808a521c`
- `CRYPT32!CertGetNameStringW` at `0x1808a52e7`
- `CRYPT32!CertGetNameStringW` at `0x1808a537f`
- `CRYPT32!CertGetNameStringW` at `0x1808a52e7`
- `CRYPT32!CertGetNameStringW` at `0x1808a537f`
- `CRYPT32!CertFreeCertificateContext` at `0x1808a5438`
- `CRYPT32!CertFreeCertificateContext` at `0x1808a5438`
- `WINHTTP!WinHttpReceiveResponse` at `0x1808a4d02`
- `WINHTTP!WinHttpReceiveResponse` at `0x1808a4d02`
- `WINHTTP!WinHttpQueryHeaders` at `0x1808a4d9a`
- `WINHTTP!WinHttpQueryHeaders` at `0x1808a4dd7`
- `WINHTTP!WinHttpQueryHeaders` at `0x1808a4e70`
- `WINHTTP!WinHttpQueryHeaders` at `0x1808a4ea9`
- `WINHTTP!WinHttpQueryHeaders` at `0x1808a4edd`
- `WINHTTP!WinHttpQueryHeaders` at `0x1808a4f11`
- `WINHTTP!WinHttpQueryHeaders` at `0x1808a561d`
- `WINHTTP!WinHttpQueryHeaders` at `0x1808a5826`
- `WINHTTP!WinHttpQueryHeaders` at `0x1808a5994`
- `WINHTTP!WinHttpQueryHeaders` at `0x1808a5c0f`
- `WINHTTP!WinHttpQueryHeaders` at `0x1808a4d9a`
- `WINHTTP!WinHttpQueryHeaders` at `0x1808a4dd7`
- `WINHTTP!WinHttpQueryHeaders` at `0x1808a4e70`
- `WINHTTP!WinHttpQueryHeaders` at `0x1808a4ea9`
- `WINHTTP!WinHttpQueryHeaders` at `0x1808a4edd`
- `WINHTTP!WinHttpQueryHeaders` at `0x1808a4f11`
- `WINHTTP!WinHttpQueryHeaders` at `0x1808a561d`
- `WINHTTP!WinHttpQueryHeaders` at `0x1808a5826`
- `WINHTTP!WinHttpQueryHeaders` at `0x1808a5994`
- `WINHTTP!WinHttpQueryHeaders` at `0x1808a5c0f`
- `WINHTTP!WinHttpOpenRequest` at `0x1808a4c93`
- `WINHTTP!WinHttpOpenRequest` at `0x1808a4c93`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x1808a4df8`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x1808a4df8`
- `WINHTTP!WinHttpQueryOption` at `0x1808a4d23`
- `WINHTTP!WinHttpQueryOption` at `0x1808a4f48`
- `WINHTTP!WinHttpQueryOption` at `0x1808a4d23`
- `WINHTTP!WinHttpQueryOption` at `0x1808a4f48`
- `WINHTTP!WinHttpSetTimeouts` at `0x1808a4c22`
- `WINHTTP!WinHttpSetTimeouts` at `0x1808a4c22`
- `WINHTTP!WinHttpSendRequest` at `0x1808a4cef`
- `WINHTTP!WinHttpSendRequest` at `0x1808a4cef`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x1808a4cc5`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x1808a4cc5`
- `WINHTTP!WinHttpOpen` at `0x1808a4bfe`
- `WINHTTP!WinHttpOpen` at `0x1808a4bfe`
- `WINHTTP!WinHttpReadData` at `0x1808a56df`
- `WINHTTP!WinHttpReadData` at `0x1808a56df`
- `WINHTTP!WinHttpConnect` at `0x1808a4c47`
- `WINHTTP!WinHttpConnect` at `0x1808a4c47`
- `WINHTTP!WinHttpCloseHandle` at `0x1808a5c4b`
- `WINHTTP!WinHttpCloseHandle` at `0x1808a5c4b`
- `WS2_32!InetNtopW` at `0x1808a4d55`
- `WS2_32!InetNtopW` at `0x1808a5d7f`
- `WS2_32!InetNtopW` at `0x1808a4d55`
- `WS2_32!InetNtopW` at `0x1808a5d7f`

## pseudocode

```c

```
