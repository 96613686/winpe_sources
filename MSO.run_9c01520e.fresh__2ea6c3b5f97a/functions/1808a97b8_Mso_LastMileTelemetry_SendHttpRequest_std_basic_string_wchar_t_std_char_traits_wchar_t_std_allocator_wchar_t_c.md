# Mso::LastMileTelemetry::SendHttpRequest(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,Mso::LastMileTelemetry::MeasureValue &,bool,bool,int)

- ea: `0x1808a97b8`
- end: `0x1808aabe3`
- name: `?SendHttpRequest@LastMileTelemetry@Mso@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@00AEAV34@AEAUMeasureValue@12@_N3H@Z`
- size: `5163`
- prototype: `__int64 __usercall@<rax>(LPCWSTR pswzServerName@<rcx>, LPCWSTR pwszObjectName@<rdx>, LPCWSTR pwszVerb@<r8>, __int64, char, char, int)`
- caller_count: `4`
- callee_count: `22`
- tags: `reparse_path`

## callers

- `0x1808951e0`
- `0x1808a92f0`
- `0x1808ab120`
- `0x1818e80dc`

## callees

- `0x180003890`
- `0x18001aef2`
- `0x18001d310`
- `0x180028b74`
- `0x180029310`
- `0x18002b13c`
- `0x180096ca4`
- `0x1800b6ef4`
- `0x18014c810`
- `0x18016c548`
- `0x18016c880`
- `0x18016c930`
- `0x18016ca60`
- `0x18016ced0`
- `0x18016cef4`
- `0x18016eca0`
- `0x1803533b0`
- `0x18054541c`
- `0x1808a97b8`
- `0x1808aabe4`
- `0x1808aac2c`
- `0x1808aac7c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1808a9c16`
- `KERNEL32!GetLastError` at `0x1808a9c4f`
- `KERNEL32!GetLastError` at `0x1808a9c83`
- `KERNEL32!GetLastError` at `0x1808a9cb7`
- `KERNEL32!GetLastError` at `0x1808aa41b`
- `KERNEL32!GetLastError` at `0x1808a9c16`
- `KERNEL32!GetLastError` at `0x1808a9c4f`
- `KERNEL32!GetLastError` at `0x1808a9c83`
- `KERNEL32!GetLastError` at `0x1808a9cb7`
- `KERNEL32!GetLastError` at `0x1808aa41b`
- `KERNEL32!QueryPerformanceCounter` at `0x1808a9a6f`
- `KERNEL32!QueryPerformanceCounter` at `0x1808a9bb8`
- `KERNEL32!QueryPerformanceCounter` at `0x1808a9a6f`
- `KERNEL32!QueryPerformanceCounter` at `0x1808a9bb8`
- `KERNEL32!QueryPerformanceFrequency` at `0x1808a9983`
- `KERNEL32!QueryPerformanceFrequency` at `0x1808a9983`
- `MSVCP140!?setw@std@@YA?AU?$_Smanip@_J@1@_J@Z` at `0x1808a9ff7`
- `MSVCP140!?setw@std@@YA?AU?$_Smanip@_J@1@_J@Z` at `0x1808a9ff7`
- `MSVCP140!??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@H@Z` at `0x1808aa02b`
- `MSVCP140!??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@H@Z` at `0x1808aa02b`
- `MSVCP140!?fill@?$basic_ios@_WU?$char_traits@_W@std@@@std@@QEAA_W_W@Z` at `0x1808aa01b`
- `MSVCP140!?fill@?$basic_ios@_WU?$char_traits@_W@std@@@std@@QEAA_W_W@Z` at `0x1808aa01b`
- `MSVCP140!??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x1808a9fd9`
- `MSVCP140!??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x1808a9fd9`
- `MSVCP140!??1?$basic_ios@_WU?$char_traits@_W@std@@@std@@UEAA@XZ` at `0x1808aa1ec`
- `MSVCP140!??1?$basic_ios@_WU?$char_traits@_W@std@@@std@@UEAA@XZ` at `0x1808aa1ec`
- `MSVCP140!?_Xlength_error@std@@YAXPEBD@Z` at `0x1808aab04`
- `MSVCP140!?_Xlength_error@std@@YAXPEBD@Z` at `0x1808aab04`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1808a9dbe`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1808a9dbe`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1808aa2f6`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1808aa917`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1808aa2f6`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1808aa917`
- `CRYPT32!CryptHashCertificate` at `0x1808a9d29`
- `CRYPT32!CryptHashCertificate` at `0x1808a9fbc`
- `CRYPT32!CryptHashCertificate` at `0x1808a9d29`
- `CRYPT32!CryptHashCertificate` at `0x1808a9fbc`
- `CRYPT32!CertGetNameStringW` at `0x1808aa087`
- `CRYPT32!CertGetNameStringW` at `0x1808aa11f`
- `CRYPT32!CertGetNameStringW` at `0x1808aa087`
- `CRYPT32!CertGetNameStringW` at `0x1808aa11f`
- `CRYPT32!CertFreeCertificateContext` at `0x1808aa1d8`
- `CRYPT32!CertFreeCertificateContext` at `0x1808aa1d8`
- `WINHTTP!WinHttpReceiveResponse` at `0x1808a9aa2`
- `WINHTTP!WinHttpReceiveResponse` at `0x1808a9aa2`
- `WINHTTP!WinHttpQueryHeaders` at `0x1808a9b3a`
- `WINHTTP!WinHttpQueryHeaders` at `0x1808a9b77`
- `WINHTTP!WinHttpQueryHeaders` at `0x1808a9c10`
- `WINHTTP!WinHttpQueryHeaders` at `0x1808a9c49`
- `WINHTTP!WinHttpQueryHeaders` at `0x1808a9c7d`
- `WINHTTP!WinHttpQueryHeaders` at `0x1808a9cb1`
- `WINHTTP!WinHttpQueryHeaders` at `0x1808aa3bd`
- `WINHTTP!WinHttpQueryHeaders` at `0x1808aa5c6`
- `WINHTTP!WinHttpQueryHeaders` at `0x1808aa734`
- `WINHTTP!WinHttpQueryHeaders` at `0x1808aa9af`
- `WINHTTP!WinHttpQueryHeaders` at `0x1808a9b3a`
- `WINHTTP!WinHttpQueryHeaders` at `0x1808a9b77`
- `WINHTTP!WinHttpQueryHeaders` at `0x1808a9c10`
- `WINHTTP!WinHttpQueryHeaders` at `0x1808a9c49`
- `WINHTTP!WinHttpQueryHeaders` at `0x1808a9c7d`
- `WINHTTP!WinHttpQueryHeaders` at `0x1808a9cb1`
- `WINHTTP!WinHttpQueryHeaders` at `0x1808aa3bd`
- `WINHTTP!WinHttpQueryHeaders` at `0x1808aa5c6`
- `WINHTTP!WinHttpQueryHeaders` at `0x1808aa734`
- `WINHTTP!WinHttpQueryHeaders` at `0x1808aa9af`
- `WINHTTP!WinHttpOpenRequest` at `0x1808a9a33`
- `WINHTTP!WinHttpOpenRequest` at `0x1808a9a33`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x1808a9b98`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x1808a9b98`
- `WINHTTP!WinHttpQueryOption` at `0x1808a9ac3`
- `WINHTTP!WinHttpQueryOption` at `0x1808a9ce8`
- `WINHTTP!WinHttpQueryOption` at `0x1808a9ac3`
- `WINHTTP!WinHttpQueryOption` at `0x1808a9ce8`
- `WINHTTP!WinHttpSetTimeouts` at `0x1808a99c2`
- `WINHTTP!WinHttpSetTimeouts` at `0x1808a99c2`
- `WINHTTP!WinHttpSendRequest` at `0x1808a9a8f`
- `WINHTTP!WinHttpSendRequest` at `0x1808a9a8f`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x1808a9a65`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x1808a9a65`
- `WINHTTP!WinHttpOpen` at `0x1808a999e`
- `WINHTTP!WinHttpOpen` at `0x1808a999e`
- `WINHTTP!WinHttpReadData` at `0x1808aa47f`
- `WINHTTP!WinHttpReadData` at `0x1808aa47f`
- `WINHTTP!WinHttpConnect` at `0x1808a99e7`
- `WINHTTP!WinHttpConnect` at `0x1808a99e7`
- `WINHTTP!WinHttpCloseHandle` at `0x1808aa9eb`
- `WINHTTP!WinHttpCloseHandle` at `0x1808aa9eb`
- `WS2_32!InetNtopW` at `0x1808a9af5`
- `WS2_32!InetNtopW` at `0x1808aab1f`
- `WS2_32!InetNtopW` at `0x1808a9af5`
- `WS2_32!InetNtopW` at `0x1808aab1f`

## pseudocode

```c

```
