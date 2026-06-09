# Windows::Compat::Appraiser::Utilities::SendRequest(void * &,void * &,ushort const *,ulong,ushort const * *,bool,ulong)

- ea: `0x1800911bc`
- end: `0x180092826`
- name: `?SendRequest@Utilities@Appraiser@Compat@Windows@@SAJAEAPEAX0PEBGKPEAPEBG_NK@Z`
- size: `5738`
- prototype: `__int64 __fastcall(void **, void **, const unsigned __int16 *, unsigned int, const unsigned __int16 **, bool, unsigned int)`
- caller_count: `2`
- callee_count: `25`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18008513c`
- `0x1800911bc`

## callees

- `0x180001008`
- `0x1800011ac`
- `0x18000147c`
- `0x180001f18`
- `0x180008570`
- `0x1800092dc`
- `0x180011d94`
- `0x180013c7c`
- `0x1800142b4`
- `0x1800151d8`
- `0x1800151f4`
- `0x18001a2f4`
- `0x18002924c`
- `0x180029258`
- `0x18002c0fc`
- `0x18002d7f8`
- `0x18002ebb8`
- `0x1800301d0`
- `0x180087e70`
- `0x18008b1ac`
- `0x18008b878`
- `0x1800911bc`
- `0x180092f40`
- `0x1800a5d88`
- `0x180217460`

## import_xrefs

- `KERNEL32!Sleep` at `0x180091c53`
- `KERNEL32!Sleep` at `0x180091c53`
- `KERNEL32!ExitProcess` at `0x18009274d`
- `KERNEL32!ExitProcess` at `0x18009274d`
- `KERNEL32!GetSystemTime` at `0x180091914`
- `KERNEL32!GetSystemTime` at `0x1800923ea`
- `KERNEL32!GetSystemTime` at `0x180091914`
- `KERNEL32!GetSystemTime` at `0x1800923ea`
- `KERNEL32!GetProcessHeap` at `0x180091e24`
- `KERNEL32!GetProcessHeap` at `0x1800920f3`
- `KERNEL32!GetProcessHeap` at `0x180092549`
- `KERNEL32!GetProcessHeap` at `0x1800927ed`
- `KERNEL32!GetProcessHeap` at `0x180091e24`
- `KERNEL32!GetProcessHeap` at `0x1800920f3`
- `KERNEL32!GetProcessHeap` at `0x180092549`
- `KERNEL32!GetProcessHeap` at `0x1800927ed`
- `KERNEL32!HeapAlloc` at `0x180092104`
- `KERNEL32!HeapAlloc` at `0x180092104`
- `KERNEL32!CloseHandle` at `0x180092762`
- `KERNEL32!CloseHandle` at `0x180092762`
- `KERNEL32!GetLastError` at `0x1800912f4`
- `KERNEL32!GetLastError` at `0x180091334`
- `KERNEL32!GetLastError` at `0x180091364`
- `KERNEL32!GetLastError` at `0x180091383`
- `KERNEL32!GetLastError` at `0x1800913de`
- `KERNEL32!GetLastError` at `0x1800913fd`
- `KERNEL32!GetLastError` at `0x180091424`
- `KERNEL32!GetLastError` at `0x180091456`
- `KERNEL32!GetLastError` at `0x180091475`
- `KERNEL32!GetLastError` at `0x18009160f`
- `KERNEL32!GetLastError` at `0x18009163f`
- `KERNEL32!GetLastError` at `0x18009165e`
- `KERNEL32!GetLastError` at `0x180091739`
- `KERNEL32!GetLastError` at `0x18009175d`
- `KERNEL32!GetLastError` at `0x18009177e`
- `KERNEL32!GetLastError` at `0x1800919ef`
- `KERNEL32!GetLastError` at `0x180091a1c`
- `KERNEL32!GetLastError` at `0x180091a3b`
- `KERNEL32!GetLastError` at `0x180091a8f`
- `KERNEL32!GetLastError` at `0x180091ab3`
- `KERNEL32!GetLastError` at `0x180091ad2`
- `KERNEL32!GetLastError` at `0x180091bbc`
- `KERNEL32!GetLastError` at `0x180091bec`
- `KERNEL32!GetLastError` at `0x180091c0b`
- `KERNEL32!GetLastError` at `0x180091d45`
- `KERNEL32!GetLastError` at `0x180091d66`
- `KERNEL32!GetLastError` at `0x180091d6e`
- `KERNEL32!GetLastError` at `0x180092098`
- `KERNEL32!GetLastError` at `0x1800920a3`
- `KERNEL32!GetLastError` at `0x1800920c4`
- `KERNEL32!GetLastError` at `0x1800920cc`
- `KERNEL32!GetLastError` at `0x18009214a`
- `KERNEL32!GetLastError` at `0x18009216b`
- `KERNEL32!GetLastError` at `0x180092173`
- `KERNEL32!GetLastError` at `0x1800921ba`
- `KERNEL32!GetLastError` at `0x1800921de`
- `KERNEL32!GetLastError` at `0x1800921fd`
- `KERNEL32!GetLastError` at `0x1800922b1`
- `KERNEL32!GetLastError` at `0x1800922d2`
- `KERNEL32!GetLastError` at `0x1800922f3`
- `KERNEL32!GetLastError` at `0x1800924a7`
- `KERNEL32!GetLastError` at `0x1800924d9`
- `KERNEL32!GetLastError` at `0x1800924fa`
- `KERNEL32!GetLastError` at `0x1800925b0`
- `KERNEL32!GetLastError` at `0x1800925cb`
- `KERNEL32!GetLastError` at `0x1800925ef`
- `KERNEL32!GetLastError` at `0x180092745`
- `KERNEL32!GetLastError` at `0x1800912f4`
- `KERNEL32!GetLastError` at `0x180091334`
- `KERNEL32!GetLastError` at `0x180091364`
- `KERNEL32!GetLastError` at `0x180091383`
- `KERNEL32!GetLastError` at `0x1800913de`
- `KERNEL32!GetLastError` at `0x1800913fd`
- `KERNEL32!GetLastError` at `0x180091424`
- `KERNEL32!GetLastError` at `0x180091456`
- `KERNEL32!GetLastError` at `0x180091475`
- `KERNEL32!GetLastError` at `0x18009160f`
- `KERNEL32!GetLastError` at `0x18009163f`
- `KERNEL32!GetLastError` at `0x18009165e`
- `KERNEL32!GetLastError` at `0x180091739`
- `KERNEL32!GetLastError` at `0x18009175d`
- `KERNEL32!GetLastError` at `0x18009177e`
- `KERNEL32!GetLastError` at `0x1800919ef`
- `KERNEL32!GetLastError` at `0x180091a1c`
- `KERNEL32!GetLastError` at `0x180091a3b`
- `KERNEL32!GetLastError` at `0x180091a8f`
- `KERNEL32!GetLastError` at `0x180091ab3`
- `KERNEL32!GetLastError` at `0x180091ad2`
- `KERNEL32!GetLastError` at `0x180091bbc`
- `KERNEL32!GetLastError` at `0x180091bec`
- `KERNEL32!GetLastError` at `0x180091c0b`
- `KERNEL32!GetLastError` at `0x180091d45`
- `KERNEL32!GetLastError` at `0x180091d66`
- `KERNEL32!GetLastError` at `0x180091d6e`
- `KERNEL32!GetLastError` at `0x180092098`
- `KERNEL32!GetLastError` at `0x1800920a3`
- `KERNEL32!GetLastError` at `0x1800920c4`
- `KERNEL32!GetLastError` at `0x1800920cc`
- `KERNEL32!GetLastError` at `0x18009214a`
- `KERNEL32!GetLastError` at `0x18009216b`
- `KERNEL32!GetLastError` at `0x180092173`
- `KERNEL32!GetLastError` at `0x1800921ba`
- `KERNEL32!GetLastError` at `0x1800921de`
- `KERNEL32!GetLastError` at `0x1800921fd`
- `KERNEL32!GetLastError` at `0x1800922b1`
- `KERNEL32!GetLastError` at `0x1800922d2`
- `KERNEL32!GetLastError` at `0x1800922f3`
- `KERNEL32!GetLastError` at `0x1800924a7`
- `KERNEL32!GetLastError` at `0x1800924d9`
- `KERNEL32!GetLastError` at `0x1800924fa`
- `KERNEL32!GetLastError` at `0x1800925b0`
- `KERNEL32!GetLastError` at `0x1800925cb`
- `KERNEL32!GetLastError` at `0x1800925ef`
- `KERNEL32!GetLastError` at `0x180092745`
- `KERNEL32!HeapFree` at `0x180091e33`
- `KERNEL32!HeapFree` at `0x180092557`
- `KERNEL32!HeapFree` at `0x1800927fb`
- `KERNEL32!HeapFree` at `0x180091e33`
- `KERNEL32!HeapFree` at `0x180092557`
- `KERNEL32!HeapFree` at `0x1800927fb`
- `ADVAPI32!RevertToSelf` at `0x1800925a2`
- `ADVAPI32!RevertToSelf` at `0x1800925a2`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x18009172f`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x18009172f`
- `SHLWAPI!UrlGetPartW` at `0x180091539`
- `SHLWAPI!UrlGetPartW` at `0x180091539`
- `WINHTTP!WinHttpOpen` at `0x1800912e2`
- `WINHTTP!WinHttpOpen` at `0x1800912e2`
- `WINHTTP!WinHttpCrackUrl` at `0x180091416`
- `WINHTTP!WinHttpCrackUrl` at `0x180091416`
- `WINHTTP!WinHttpConnect` at `0x180091600`
- `WINHTTP!WinHttpConnect` at `0x180091600`
- `WINHTTP!WinHttpOpenRequest` at `0x1800919dc`
- `WINHTTP!WinHttpOpenRequest` at `0x1800919dc`
- `WINHTTP!WinHttpSetOption` at `0x180091a85`
- `WINHTTP!WinHttpSetOption` at `0x180091a85`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x180091bb2`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x180091bb2`
- `WINHTTP!WinHttpSendRequest` at `0x180091cec`
- `WINHTTP!WinHttpSendRequest` at `0x180091cec`
- `WINHTTP!WinHttpReceiveResponse` at `0x180091d02`
- `WINHTTP!WinHttpReceiveResponse` at `0x180091d02`
- `WINHTTP!WinHttpQueryHeaders` at `0x180091d3b`
- `WINHTTP!WinHttpQueryHeaders` at `0x18009208e`
- `WINHTTP!WinHttpQueryHeaders` at `0x18009213c`
- `WINHTTP!WinHttpQueryHeaders` at `0x180091d3b`
- `WINHTTP!WinHttpQueryHeaders` at `0x18009208e`
- `WINHTTP!WinHttpQueryHeaders` at `0x18009213c`
- `WINHTTP!WinHttpQueryAuthSchemes` at `0x180091f04`
- `WINHTTP!WinHttpQueryAuthSchemes` at `0x180091f04`
- `WINHTTP!WinHttpSetCredentials` at `0x18009201d`
- `WINHTTP!WinHttpSetCredentials` at `0x18009201d`
- `WINHTTP!WinHttpCloseHandle` at `0x180092256`
- `WINHTTP!WinHttpCloseHandle` at `0x18009226a`
- `WINHTTP!WinHttpCloseHandle` at `0x18009253a`
- `WINHTTP!WinHttpCloseHandle` at `0x18009256d`
- `WINHTTP!WinHttpCloseHandle` at `0x180092583`
- `WINHTTP!WinHttpCloseHandle` at `0x180092256`
- `WINHTTP!WinHttpCloseHandle` at `0x18009226a`
- `WINHTTP!WinHttpCloseHandle` at `0x18009253a`
- `WINHTTP!WinHttpCloseHandle` at `0x18009256d`
- `WINHTTP!WinHttpCloseHandle` at `0x180092583`

## string_xrefs

- `0x1800912a4`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x180091392`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x180091495`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x18009156c`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x1800915b9`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x1800916c6`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x18009170b`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x180091790`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x18009182b`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x1800918e7`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x180091999`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x1800919b2`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x180091b6c`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x180091c15`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x180091db1`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x180091e8c`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x180091ec4`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x180091f43`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x180091f97`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x180092195`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x18009220f`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x180092515`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x1800925f9`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x1800912d9`: `WicaAgent`
- `0x180091aee`: `WicaAgent`
- `0x18009131e`: `Invalid parameter provided while trying to open the Internet with auto proxy: [0x%x].`
- `0x18009127a`: `Too many HTTP forwarding links.`
- `0x180091287`: `Windows::Compat::Appraiser::Utilities::SendRequest`
- `0x180091310`: `Windows::Compat::Appraiser::Utilities::SendRequest`
- `0x180091346`: `Windows::Compat::Appraiser::Utilities::SendRequest`
- `0x1800913bf`: `Windows::Compat::Appraiser::Utilities::SendRequest`
- `0x18009142e`: `Windows::Compat::Appraiser::Utilities::SendRequest`
- `0x1800914e9`: `Windows::Compat::Appraiser::Utilities::SendRequest`
- `0x1800914be`: `Attempting INTERNET_SCHEME_HTTPS (https) download request.`
- `0x18009133a`: `Error opening the internet with auto proxy: [%d].`
- `0x1800913b4`: `Error opening the internet: [%d].`
- `0x1800914d3`: `Attempting INTERNET_SCHEME_HTTP (http) download request.`
- `0x1800914e2`: `Attempting unknown http type request.`
- `0x18009173f`: `Failed to impersonate user to get proxy: [%d].`
- `0x1800919f9`: `Failed to open http request %ls: [%d].`
- `0x1800917af`: `Impersonating user for http request.`
- `0x180091afa`: `Accept: text/*\nUser-Agent: %ls\n`
- `0x180091cb1`: `Link %ls.`
- `0x180091c7d`: `%ls - Appraiser link download attempt %lu: ImpersonateUserDuringCall: %ls.`
- `0x1800924b1`: `%ls - Attempt %lu. Failed to connect to the internet, or send request, or request encountered HTTP error: [%d].`
- `0x1800925d1`: `Failed to un-impersonate user: [%d].`
- `0x18009245c`: `%ls - HTTP request succeeded on attempt %lu.`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Appraiser::Utilities::SendRequest(
        void **a1,
        void **a2,
        WCHAR *a3,
        unsigned int a4,
        const unsigned __int16 **a5,
        bool a6,
        unsigned int a7)
{
  void **v9; // r14
  HINTERNET *v10; // r12
  unsigned __int16 *v11; // r13
  signed int v12; // ebx
  HINTERNET v13; // rax
  DWORD LastError; // eax
  DWORD v15; // eax
  const char *v16; // r15
  signed int v17; // eax
  DWORD v18; // eax
  char v19; // dl
  signed int v20; // eax
  DWORD v21; // eax
  signed int v22; // eax
  char v23; // dl
  __int64 v24; // r8
  const char *v25; // r9
  HRESULT PartW; // eax
  DWORD v27; // eax
  signed int v28; // eax
  int UserSession; // eax
  char v30; // dl
  DWORD v31; // eax
  signed int v32; // eax
  int Credentials; // eax
  int v34; // r14d
  volatile signed __int64 *v35; // rcx
  void **v36; // rdx
  int v37; // ebx
  int v38; // r8d
  int v39; // r9d
  void *v40; // rax
  DWORD v41; // eax
  const char *v42; // r15
  signed int v43; // eax
  const char *lpszUrlPath; // rax
  char v45; // dl
  DWORD v46; // eax
  signed int v47; // eax
  int v48; // eax
  unsigned __int64 v49; // rdx
  DWORD v50; // eax
  signed int v51; // eax
  BOOL v52; // r12d
  unsigned int i; // r14d
  const wchar_t *v54; // rcx
  HINTERNET *v55; // rbx
  void *v56; // rcx
  DWORD v57; // eax
  DWORD v58; // ebx
  signed int v59; // eax
  const char *v60; // rcx
  char v61; // dl
  HANDLE ProcessHeap; // rax
  int ProxyAuthenticationHeaderResponseAlloc; // ebx
  bool v64; // zf
  char v65; // dl
  __int64 v66; // rcx
  DWORD v67; // eax
  DWORD v68; // ebx
  HANDLE v69; // rax
  wchar_t *v70; // rax
  DWORD v71; // eax
  DWORD v72; // eax
  signed int v73; // eax
  DWORD v74; // eax
  signed int v75; // eax
  char v76; // dl
  const char *v77; // rax
  volatile signed __int64 *v78; // rcx
  int v79; // ebx
  int v80; // r8d
  int v81; // r9d
  DWORD v82; // eax
  signed int v83; // eax
  void *v84; // r14
  HANDLE v85; // rax
  signed int v86; // eax
  signed int v87; // ebx
  DWORD v88; // eax
  TraceLoggingCorrelationVector *v89; // rcx
  const struct _tlgProvider_t *GeneralProvider; // rax
  int v91; // r15d
  __int64 v92; // rax
  __int64 v93; // r14
  __int64 v94; // rsi
  __int64 v95; // rdi
  const unsigned __int16 *v96; // rax
  __int64 v97; // rbx
  struct _SYSTEMTIME *v98; // rdx
  struct _SYSTEMTIME v99; // xmm0
  int v100; // r8d
  int v101; // r9d
  UINT v102; // eax
  int v103; // eax
  HANDLE v104; // rax
  const char *dwFlags; // [rsp+20h] [rbp-E0h]
  const char *dwFlagsa; // [rsp+20h] [rbp-E0h]
  const char *dwFlagsb; // [rsp+20h] [rbp-E0h]
  const char *dwFlagsj; // [rsp+20h] [rbp-E0h]
  const char *dwFlagsc; // [rsp+20h] [rbp-E0h]
  const char *dwFlagsd; // [rsp+20h] [rbp-E0h]
  const char *dwFlagsk; // [rsp+20h] [rbp-E0h]
  const char *dwFlagse; // [rsp+20h] [rbp-E0h]
  const char *dwFlagsf; // [rsp+20h] [rbp-E0h]
  const char *dwFlagsg; // [rsp+20h] [rbp-E0h]
  const char *dwFlagsh; // [rsp+20h] [rbp-E0h]
  const char *dwFlagsi; // [rsp+20h] [rbp-E0h]
  const char *dwFlagsl; // [rsp+20h] [rbp-E0h]
  const char *ppwszAcceptTypes; // [rsp+28h] [rbp-D8h]
  const char *ppwszAcceptTypesa; // [rsp+28h] [rbp-D8h]
  LPCWSTR *ppwszAcceptTypesb; // [rsp+28h] [rbp-D8h]
  const char *ppwszAcceptTypesc; // [rsp+28h] [rbp-D8h]
  LPCWSTR *ppwszAcceptTypesd; // [rsp+28h] [rbp-D8h]
  const char *v124; // [rsp+30h] [rbp-D0h]
  WCHAR *v125; // [rsp+30h] [rbp-D0h]
  const char *v126; // [rsp+30h] [rbp-D0h]
  const char *v127; // [rsp+30h] [rbp-D0h]
  __int64 v128; // [rsp+38h] [rbp-C8h]
  DWORD v129; // [rsp+38h] [rbp-C8h]
  __int64 v130; // [rsp+40h] [rbp-C0h]
  bool v131; // [rsp+60h] [rbp-A0h]
  char v132; // [rsp+61h] [rbp-9Fh]
  char *v133; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD dwBufferLength; // [rsp+6Ch] [rbp-94h] BYREF
  int v135; // [rsp+70h] [rbp-90h] BYREF
  HINTERNET *v136; // [rsp+78h] [rbp-88h]
  DWORD dwSupportedSchemes; // [rsp+80h] [rbp-80h] BYREF
  DWORD pdwAuthTarget; // [rsp+84h] [rbp-7Ch] BYREF
  DWORD dwFirstScheme; // [rsp+88h] [rbp-78h] BYREF
  wchar_t *v140; // [rsp+90h] [rbp-70h]
  LPVOID lpMem; // [rsp+98h] [rbp-68h] BYREF
  DWORD pcchOut; // [rsp+A0h] [rbp-60h] BYREF
  int Buffer; // [rsp+A4h] [rbp-5Ch] BYREF
  void **v144; // [rsp+A8h] [rbp-58h]
  char *v145; // [rsp+B0h] [rbp-50h] BYREF
  struct _SYSTEMTIME *v146; // [rsp+B8h] [rbp-48h] BYREF
  const char *v147; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v148; // [rsp+C8h] [rbp-38h] BYREF
  HINTERNET hConnect; // [rsp+D0h] [rbp-30h]
  HANDLE hToken; // [rsp+D8h] [rbp-28h] BYREF
  unsigned int v151; // [rsp+E0h] [rbp-20h]
  struct _SYSTEMTIME SystemTime; // [rsp+F0h] [rbp-10h] BYREF
  LPCWSTR *v153; // [rsp+100h] [rbp+0h]
  char *v154; // [rsp+108h] [rbp+8h] BYREF
  $BC2FB811D417144E831EE3AEA4A279C8 UrlComponents; // [rsp+110h] [rbp+10h] BYREF
  struct _SYSTEMTIME v156; // [rsp+180h] [rbp+80h] BYREF
  char v157[144]; // [rsp+190h] [rbp+90h] BYREF
  char v158[144]; // [rsp+220h] [rbp+120h] BYREF
  unsigned __int16 v159[264]; // [rsp+2B0h] [rbp+1B0h] BYREF
  WCHAR pszOut[256]; // [rsp+4C0h] [rbp+3C0h] BYREF
  WCHAR pwszUserName[264]; // [rsp+6C0h] [rbp+5C0h] BYREF
  WCHAR pwszPassword[264]; // [rsp+8D0h] [rbp+7D0h] BYREF
  WCHAR szHeaders[2048]; // [rsp+AE0h] [rbp+9E0h] BYREF

  v144 = a2;
  v136 = a1;
  v9 = a2;
  v151 = a4;
  v10 = a1;
  v153 = a5;
  pcchOut = 0;
  Buffer = 0;
  v133 = 0;
  dwBufferLength = 0;
  dwSupportedSchemes = 0;
  dwFirstScheme = 0;
  pdwAuthTarget = 0;
  memset_0(&UrlComponents, 0, sizeof(UrlComponents));
  v11 = 0;
  UrlComponents.dwStructSize = 104;
  UrlComponents.dwUrlPathLength = 1;
  lpMem = 0;
  v131 = 0;
  v132 = 0;
  v140 = 0;
  pwszPassword[0] = 0;
  pwszUserName[0] = 0;
  hToken = 0;
  if ( a7 >= 0xA )
  {
    AslLogCallPrintf(3, "Windows::Compat::Appraiser::Utilities::SendRequest", 2458, "Too many HTTP forwarding links.");
    v12 = -2147023895;
    LODWORD(dwFlags) = -2147023895;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      155,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
      "Windows::Compat::Appraiser::Utilities::SendRequest",
      dwFlags,
      (int)"Too many HTTP forwarding links.",
      v124);
    goto LABEL_174;
  }
  v13 = WinHttpOpen(L"WicaAgent", a4, 0, 0, 0);
  *v9 = v13;
  if ( !v13 )
  {
    LastError = GetLastError();
    if ( a4 == 4 )
    {
      if ( LastError == 87 )
      {
        v12 = -2147024809;
        AslLogCallPrintf(
          3,
          "Windows::Compat::Appraiser::Utilities::SendRequest",
          2478,
          "Invalid parameter provided while trying to open the Internet with auto proxy: [0x%x].",
          -2147024809);
        goto LABEL_174;
      }
      v15 = GetLastError();
      v16 = "Error opening the internet with auto proxy: [%d].";
      AslLogCallPrintf(
        3,
        "Windows::Compat::Appraiser::Utilities::SendRequest",
        2482,
        "Error opening the internet with auto proxy: [%d].",
        v15);
      v17 = GetLastError();
      v12 = v17;
      if ( v17 > 0 )
        v12 = (unsigned __int16)v17 | 0x80070000;
      if ( v12 >= 0 )
        v12 = -2147467259;
      v18 = GetLastError();
      v19 = -77;
    }
    else
    {
      v16 = "Error opening the internet: [%d].";
      AslLogCallPrintf(
        3,
        "Windows::Compat::Appraiser::Utilities::SendRequest",
        2487,
        "Error opening the internet: [%d].",
        LastError);
      v20 = GetLastError();
      v12 = v20;
      if ( v20 > 0 )
        v12 = (unsigned __int16)v20 | 0x80070000;
      if ( v12 >= 0 )
        v12 = -2147467259;
      v18 = GetLastError();
      v19 = -72;
    }
    LODWORD(v124) = v18;
    LODWORD(dwFlagsa) = v12;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      v19,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
      "Windows::Compat::Appraiser::Utilities::SendRequest",
      dwFlagsa,
      (int)v16,
      v124);
LABEL_174:
    if ( *v9 )
    {
      WinHttpCloseHandle(*v9);
      *v9 = 0;
    }
    if ( *v10 )
    {
      WinHttpCloseHandle(*v10);
      *v10 = 0;
    }
    goto LABEL_179;
  }
  if ( !WinHttpCrackUrl(a3, 0, 0, &UrlComponents) )
  {
    v21 = GetLastError();
    AslLogCallPrintf(
      3,
      "Windows::Compat::Appraiser::Utilities::SendRequest",
      2499,
      "Could not crack url %ls: [%d].",
      a3,
      v21);
    v22 = GetLastError();
    v12 = v22;
    if ( v22 > 0 )
      v12 = (unsigned __int16)v22 | 0x80070000;
    if ( v12 >= 0 )
      v12 = -2147467259;
    v129 = GetLastError();
    v23 = -60;
    v125 = a3;
    ppwszAcceptTypes = "Could not crack url %ls: [%d].";
LABEL_24:
    LODWORD(dwFlagsb) = v12;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      v23,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
      "Windows::Compat::Appraiser::Utilities::SendRequest",
      dwFlagsb,
      (int)ppwszAcceptTypes,
      (const char *)v125,
      v129);
    goto LABEL_174;
  }
  if ( UrlComponents.nScheme == INTERNET_SCHEME_GOPHER )
  {
    v24 = 2505;
    v25 = "Attempting INTERNET_SCHEME_HTTPS (https) download request.";
  }
  else if ( UrlComponents.nScheme == INTERNET_SCHEME_FTP )
  {
    v24 = 2509;
    v25 = "Attempting INTERNET_SCHEME_HTTP (http) download request.";
  }
  else
  {
    v24 = 2513;
    v25 = "Attempting unknown http type request.";
  }
  AslLogCallPrintf(3, "Windows::Compat::Appraiser::Utilities::SendRequest", v24, v25);
  AslLogCallPrintf(3, "Windows::Compat::Appraiser::Utilities::SendRequest", 2515, "URL %ls.", a3);
  pcchOut = 256;
  PartW = UrlGetPartW(a3, pszOut, &pcchOut, 2u, 0);
  v12 = PartW;
  if ( PartW < 0 )
  {
    AslLogCallPrintf(
      3,
      "Windows::Compat::Appraiser::Utilities::SendRequest",
      2532,
      "UrlGetPart failed to retrieve host name for %ls: [0x%x].",
      a3,
      PartW);
    LODWORD(dwFlagsj) = v12;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      229,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
      "Windows::Compat::Appraiser::Utilities::SendRequest",
      dwFlagsj,
      (int)"UrlGetPart failed to retrieve host name for %ls: [0x%x].",
      (const char *)a3,
      v12);
    goto LABEL_173;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x9E5u,
      "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
      "Windows::Compat::Appraiser::Utilities::SendRequest",
      "UrlGetPart failed to retrieve host name for %ls: [0x%x].",
      a3,
      PartW);
  AslLogCallPrintf(3, "Windows::Compat::Appraiser::Utilities::SendRequest", 2535, "Host name is %ls.", pszOut);
  hConnect = WinHttpConnect(*v9, pszOut, 0x50u, 0);
  if ( !hConnect )
  {
    v27 = GetLastError();
    AslLogCallPrintf(
      3,
      "Windows::Compat::Appraiser::Utilities::SendRequest",
      2543,
      "Failed to connect to host %ls: [%d].",
      pszOut,
      v27);
    v28 = GetLastError();
    v12 = v28;
    if ( v28 > 0 )
      v12 = (unsigned __int16)v28 | 0x80070000;
    if ( v12 >= 0 )
      v12 = -2147467259;
    v129 = GetLastError();
    v23 = -16;
    v125 = pszOut;
    ppwszAcceptTypes = "Failed to connect to host %ls: [%d].";
    goto LABEL_24;
  }
  if ( a6 )
  {
    UserSession = Windows::Compat::Appraiser::Utilities::FindUserSession(&hToken, (int *)&v133 + 1);
    v12 = UserSession;
    if ( UserSession < 0 )
    {
      AslLogCallPrintf(
        3,
        "Windows::Compat::Appraiser::Utilities::SendRequest",
        2559,
        "Failed to look for current user session: [0x%x].",
        UserSession);
      LODWORD(v124) = v12;
      ppwszAcceptTypesa = "Failed to look for current user session: [0x%x].";
      v30 = 0;
LABEL_43:
      LODWORD(dwFlagsc) = v12;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        v30,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
        "Windows::Compat::Appraiser::Utilities::SendRequest",
        dwFlagsc,
        (int)ppwszAcceptTypesa,
        v124);
LABEL_169:
      WinHttpCloseHandle(hConnect);
      goto LABEL_170;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    {
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0xA00u,
        "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
        "Windows::Compat::Appraiser::Utilities::SendRequest",
        "Failed to look for current user session: [0x%x].",
        UserSession);
      v9 = v144;
    }
    if ( HIDWORD(v133) )
    {
      if ( !ImpersonateLoggedOnUser(hToken) )
      {
        v31 = GetLastError();
        AslLogCallPrintf(
          3,
          "Windows::Compat::Appraiser::Utilities::SendRequest",
          2566,
          "Failed to impersonate user to get proxy: [%d].",
          v31);
        v32 = GetLastError();
        v12 = v32;
        if ( v32 > 0 )
          v12 = (unsigned __int16)v32 | 0x80070000;
        if ( v12 >= 0 )
          v12 = -2147467259;
        LODWORD(v124) = GetLastError();
        LODWORD(dwFlagsd) = v12;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          7,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
          "Windows::Compat::Appraiser::Utilities::SendRequest",
          dwFlagsd,
          (int)"Failed to impersonate user to get proxy: [%d].",
          v124);
        goto LABEL_169;
      }
      v131 = 1;
      AslLogCallPrintf(
        3,
        "Windows::Compat::Appraiser::Utilities::SendRequest",
        2571,
        "Impersonating user for http request.");
    }
  }
  Credentials = Windows::Compat::Appraiser::Utilities::SetUserProxyInfoAndGetCredentials(
                  v9,
                  a3,
                  v131,
                  pwszUserName,
                  0x104u,
                  pwszPassword,
                  0x104u);
  v34 = Credentials;
  if ( Credentials >= 0 )
  {
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0xA15u,
        "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
        "Windows::Compat::Appraiser::Utilities::SendRequest",
        "Failed to get or set proxy info, swallowing: [0x%x].",
        Credentials);
  }
  else
  {
    AslLogCallPrintf(
      3,
      "Windows::Compat::Appraiser::Utilities::SendRequest",
      2580,
      "Failed to get or set proxy info, swallowing: [0x%x].",
      Credentials);
    LODWORD(v126) = v34;
    LODWORD(dwFlagsk) = v34;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      21,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
      "Windows::Compat::Appraiser::Utilities::SendRequest",
      dwFlagsk,
      (int)"Failed to get or set proxy info, swallowing: [0x%x].",
      v126);
    TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v157);
    v35 = (volatile signed __int64 *)v157;
    if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
      v35 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v35,
      _InterlockedExchangeAdd64(v35 + 17, 0),
      v158);
    if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
      UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v36);
    v37 = qword_1802C9628;
    if ( *(_DWORD *)qword_1802C9628 > 5u
      && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
    {
      HIDWORD(v133) = v34;
      v154 = v158;
      v146 = (struct _SYSTEMTIME *)"Windows::Compat::Appraiser::Utilities::SendRequest";
      v148 = (__int64)&szValueBuf;
      v147 = "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp";
      v135 = 2581;
      SystemTime = 0;
      GetSystemTime(&SystemTime);
      v145 = (char *)&v156;
      v156 = SystemTime;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v37,
        (unsigned int)&unk_1802A2270,
        v38,
        v39,
        (__int64)&v145,
        (__int64)&v148,
        (__int64)&v135,
        (__int64)&v147,
        (__int64)&v146,
        (__int64)&v133 + 4,
        (__int64)&v154);
    }
  }
  v40 = WinHttpOpenRequest(hConnect, 0, (LPCWSTR)UrlComponents.lpszUrlPath, 0, 0, v153, 0x100u);
  *v10 = v40;
  if ( !v40 )
  {
    v41 = GetLastError();
    v42 = "Failed to open http request %ls: [%d].";
    AslLogCallPrintf(
      3,
      "Windows::Compat::Appraiser::Utilities::SendRequest",
      2596,
      "Failed to open http request %ls: [%d].",
      (const wchar_t *)UrlComponents.lpszUrlPath,
      v41);
    v43 = GetLastError();
    v12 = v43;
    if ( v43 > 0 )
      v12 = (unsigned __int16)v43 | 0x80070000;
    if ( v12 >= 0 )
      v12 = -2147467259;
    LODWORD(v128) = GetLastError();
    lpszUrlPath = UrlComponents.lpszUrlPath;
    v45 = 37;
LABEL_71:
    LODWORD(dwFlagse) = v12;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      v45,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
      "Windows::Compat::Appraiser::Utilities::SendRequest",
      dwFlagse,
      (int)v42,
      lpszUrlPath,
      v128);
    goto LABEL_169;
  }
  Buffer = 3;
  if ( !WinHttpSetOption(v40, 0x3Fu, &Buffer, 4u) )
  {
    v46 = GetLastError();
    AslLogCallPrintf(
      3,
      "Windows::Compat::Appraiser::Utilities::SendRequest",
      2605,
      "Failed to set flags for request handle: [%d].",
      v46);
    v47 = GetLastError();
    v12 = v47;
    if ( v47 > 0 )
      v12 = (unsigned __int16)v47 | 0x80070000;
    if ( v12 >= 0 )
      v12 = -2147467259;
    LODWORD(v124) = GetLastError();
    ppwszAcceptTypesa = "Failed to set flags for request handle: [%d].";
    v30 = 46;
    goto LABEL_43;
  }
  v48 = StringCchPrintfW(szHeaders, 0x800u, L"Accept: text/*\r\nUser-Agent: %ls\r\n", L"WicaAgent");
  v12 = v48;
  if ( v48 < 0 )
  {
    AslLogCallPrintf(
      3,
      "Windows::Compat::Appraiser::Utilities::SendRequest",
      2610,
      "Failed to printf http headers: [0x%x].",
      v48);
    LODWORD(v124) = v12;
    ppwszAcceptTypesa = "Failed to printf: [0x%x].";
    v30 = 51;
    goto LABEL_43;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0xA33u,
      "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
      "Windows::Compat::Appraiser::Utilities::SendRequest",
      "Failed to printf: [0x%x].",
      v48);
  AslLogCallPrintf(
    3,
    "Windows::Compat::Appraiser::Utilities::SendRequest",
    2613,
    "Headers for http request are: %ls",
    szHeaders);
  if ( !WinHttpAddRequestHeaders(*v10, szHeaders, 0xFFFFFFFF, 0) )
  {
    v50 = GetLastError();
    v42 = "Failed to add header %ls: [%d].";
    AslLogCallPrintf(
      3,
      "Windows::Compat::Appraiser::Utilities::SendRequest",
      2618,
      "Failed to add header %ls: [%d].",
      szHeaders,
      v50);
    v51 = GetLastError();
    v12 = v51;
    if ( v51 > 0 )
      v12 = (unsigned __int16)v51 | 0x80070000;
    if ( v12 >= 0 )
      v12 = -2147467259;
    LODWORD(v128) = GetLastError();
    lpszUrlPath = (const char *)szHeaders;
    v45 = 59;
    goto LABEL_71;
  }
  v52 = 0;
  LODWORD(v133) = 0;
  for ( i = 0; ; ++i )
  {
    if ( i >= 3 )
    {
      if ( v52 )
        goto LABEL_151;
      goto LABEL_162;
    }
    if ( i && !v52 )
      Sleep(0x4E20u);
    Windows::Compat::Appraiser::Utilities::GetSystemTimeIso8601(v159, v49);
    v54 = L"TRUE";
    if ( !a6 )
      v54 = L"FALSE";
    LODWORD(ppwszAcceptTypesb) = i + 1;
    AslLogCallPrintf(
      3,
      "Windows::Compat::Appraiser::Utilities::SendRequest",
      2644,
      "%ls - Appraiser link download attempt %lu: ImpersonateUserDuringCall: %ls.",
      v159,
      ppwszAcceptTypesb,
      v54);
    AslLogCallPrintf(3, "Windows::Compat::Appraiser::Utilities::SendRequest", 2645, "Link %ls.", a3);
    v55 = v136;
    v52 = WinHttpSendRequest(*v136, 0, 0, 0, 0, 0, 0);
    if ( !v52 )
      continue;
    if ( !WinHttpReceiveResponse(*v55, 0) )
    {
      v74 = GetLastError();
      AslLogCallPrintf(
        3,
        "Windows::Compat::Appraiser::Utilities::SendRequest",
        2660,
        "Failed to receive http request: [%d]",
        v74);
      v75 = GetLastError();
      v12 = v75;
      if ( v75 > 0 )
        v12 = (unsigned __int16)v75 | 0x80070000;
      if ( v12 >= 0 )
        v12 = -2147467259;
      LODWORD(v124) = GetLastError();
      v76 = 101;
      v77 = "Failed to receive request: [%d].";
      goto LABEL_167;
    }
    v56 = *v55;
    dwBufferLength = 4;
    if ( !WinHttpQueryHeaders(v56, 0x20000013u, 0, &v133, &dwBufferLength, 0) )
    {
      v57 = GetLastError();
      AslLogCallPrintf(
        3,
        "Windows::Compat::Appraiser::Utilities::SendRequest",
        2673,
        "Failed to query HTTP status code: [%d]",
        v57);
      v58 = GetLastError();
      v59 = GetLastError();
      if ( v59 > 0 )
        v59 = (unsigned __int16)v59 | 0x80070000;
      v60 = "Failed to query HTTP status code: [%d].";
      v61 = 114;
      goto LABEL_132;
    }
    if ( (_DWORD)v133 == 200 )
    {
      ++i;
LABEL_151:
      if ( (unsigned int)((_DWORD)v133 - 200) <= 0x63 )
      {
        if ( i > 1 )
        {
          TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v157);
          v78 = (volatile signed __int64 *)v157;
          if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
            v78 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
          TraceLoggingCorrelationVector::ToStringImpl(
            (TraceLoggingCorrelationVector *)v78,
            _InterlockedExchangeAdd64(v78 + 17, 0),
            v158);
          if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
            UtcThrottle::Throttle(
              (UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler,
              (void **)v49);
          v79 = qword_1802C9628;
          if ( *(_DWORD *)qword_1802C9628 > 5u )
          {
            v49 = 0x200000000000LL;
            if ( (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
              && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
            {
              v148 = 0x1000000;
              v145 = v158;
              v135 = i;
              v147 = (const char *)&szValueBuf;
              SystemTime = 0;
              GetSystemTime(&SystemTime);
              v146 = &v156;
              v156 = SystemTime;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
                v79,
                (unsigned int)&unk_1802A2211,
                v80,
                v81,
                (__int64)&v146,
                (__int64)&v147,
                (__int64)&v135,
                (__int64)&v148,
                (__int64)&v145);
            }
          }
        }
        Windows::Compat::Appraiser::Utilities::GetSystemTimeIso8601(v159, v49);
        AslLogCallPrintf(
          3,
          "Windows::Compat::Appraiser::Utilities::SendRequest",
          2847,
          "%ls - HTTP request succeeded on attempt %lu.",
          v159,
          i);
        AslLogCallPrintf(3, "Windows::Compat::Appraiser::Utilities::SendRequest", 2848, "URL %ls.", a3);
        v12 = 0;
        goto LABEL_168;
      }
LABEL_162:
      Windows::Compat::Appraiser::Utilities::GetSystemTimeIso8601(v159, v49);
      v82 = GetLastError();
      AslLogCallPrintf(
        3,
        "Windows::Compat::Appraiser::Utilities::SendRequest",
        2837,
        "%ls - Attempt %lu. Failed to connect to the internet, or send request, or request encountered HTTP error: [%d].",
        v159,
        i,
        v82);
      v83 = GetLastError();
      v12 = v83;
      if ( v83 > 0 )
        v12 = (unsigned __int16)v83 | 0x80070000;
      if ( v12 >= 0 )
        v12 = -2147467259;
      LODWORD(v124) = GetLastError();
      v76 = 23;
      v77 = "Failed to connect to the internet, or send request, or request encountered HTTP error: [%d].";
LABEL_167:
      LODWORD(dwFlagsi) = v12;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        v76,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
        "Windows::Compat::Appraiser::Utilities::SendRequest",
        dwFlagsi,
        (int)v77,
        v124);
      goto LABEL_168;
    }
    LODWORD(v124) = (_DWORD)v133;
    Windows::Compat::Appraiser::WriteLog(
      0,
      132,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
      "Windows::Compat::Appraiser::Utilities::SendRequest",
      0,
      (int)"Internet request HTTP status code was %d, not success.",
      v124);
    AslLogCallPrintf(
      3,
      "Windows::Compat::Appraiser::Utilities::SendRequest",
      2693,
      "Internet request HTTP status code was %d, not success.",
      (_DWORD)v133);
    if ( (_DWORD)v133 != 407 )
      break;
    if ( (_BYTE)v11 )
      continue;
    AslLogCallPrintf(
      3,
      "Windows::Compat::Appraiser::Utilities::SendRequest",
      2700,
      "Proxy authentication issue: getting more info on what the proxy requires.");
    if ( lpMem )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, lpMem);
      lpMem = 0;
    }
    ProxyAuthenticationHeaderResponseAlloc = Windows::Compat::Appraiser::Utilities::GetProxyAuthenticationHeaderResponseAlloc(
                                               *v55,
                                               (unsigned __int16 **)&lpMem);
    if ( ProxyAuthenticationHeaderResponseAlloc >= 0 )
    {
      AslLogCallPrintf(
        3,
        "Windows::Compat::Appraiser::Utilities::SendRequest",
        2711,
        "Proxy authentication info is [%ls].",
        (const wchar_t *)lpMem);
      v124 = (const char *)lpMem;
      v65 = -104;
      ppwszAcceptTypesc = "Proxy authentication info is [%ls].";
LABEL_110:
      v66 = 0;
      dwFlagsg = 0;
      goto LABEL_111;
    }
    AslLogCallPrintf(
      3,
      "Windows::Compat::Appraiser::Utilities::SendRequest",
      2706,
      "Failed to find proxy authentication info in response header: [0x%x].",
      (_DWORD)v133);
    v64 = !Windows::Compat::Appraiser::AppraiserTestHooks::TreatWarningsAsErrors();
    LODWORD(v124) = ProxyAuthenticationHeaderResponseAlloc;
    ppwszAcceptTypesc = "Failed to find proxy authentication info in response header: [0x%x].";
    v65 = -109;
    if ( v64 )
      goto LABEL_110;
    LODWORD(dwFlagsg) = ProxyAuthenticationHeaderResponseAlloc;
    v66 = 1;
LABEL_111:
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)v66,
      v65,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
      "Windows::Compat::Appraiser::Utilities::SendRequest",
      dwFlagsg,
      (int)ppwszAcceptTypesc,
      v124);
    WinHttpQueryAuthSchemes(*v136, &dwSupportedSchemes, &dwFirstScheme, &pdwAuthTarget);
    if ( ProxyAuthenticationHeaderResponseAlloc < 0 )
    {
      AslLogCallPrintf(
        3,
        "Windows::Compat::Appraiser::Utilities::SendRequest",
        2726,
        "Failed to get proxy authentication schemes: [0x%x].",
        ProxyAuthenticationHeaderResponseAlloc);
      v64 = !Windows::Compat::Appraiser::AppraiserTestHooks::TreatWarningsAsErrors();
      LODWORD(v124) = ProxyAuthenticationHeaderResponseAlloc;
      ppwszAcceptTypesd = (LPCWSTR *)"Failed to get proxy authentication schemes: [0x%x].";
      v61 = -89;
      if ( v64 )
      {
        Windows::Compat::Appraiser::WriteLog(
          0,
          167,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
          "Windows::Compat::Appraiser::Utilities::SendRequest",
          0,
          (int)"Failed to get proxy authentication schemes: [0x%x].",
          v124);
        continue;
      }
      LODWORD(dwFlagsf) = ProxyAuthenticationHeaderResponseAlloc;
      goto LABEL_133;
    }
    AslLogCallPrintf(
      3,
      "Windows::Compat::Appraiser::Utilities::SendRequest",
      2732,
      "Proxy authentication schemes are: supported = [0x%x], first = [0x%x], target = [0x%x].",
      dwSupportedSchemes,
      dwFirstScheme,
      pdwAuthTarget);
    LODWORD(v130) = pdwAuthTarget;
    LODWORD(v128) = dwFirstScheme;
    LODWORD(v127) = dwSupportedSchemes;
    Windows::Compat::Appraiser::WriteLog(
      0,
      173,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
      "Windows::Compat::Appraiser::Utilities::SendRequest",
      0,
      (int)"Proxy authentication schemes are: supported = [0x%x], first = [0x%x], target = [0x%x].",
      v127,
      v128,
      v130);
    if ( (dwSupportedSchemes & 1) != 0 && pdwAuthTarget == 1 && pwszUserName[0] )
    {
      if ( WinHttpSetCredentials(*v136, 1u, 1u, pwszUserName, pwszPassword, 0) )
      {
        LOBYTE(v11) = 1;
        i = 0;
        continue;
      }
      v72 = GetLastError();
      AslLogCallPrintf(
        3,
        "Windows::Compat::Appraiser::Utilities::SendRequest",
        2756,
        "Failed to set proxy credentials: [%d].",
        v72);
      v73 = GetLastError();
      v12 = v73;
      if ( v73 > 0 )
        v12 = (unsigned __int16)v73 | 0x80070000;
      if ( v12 >= 0 )
        v12 = -2147467259;
      LODWORD(v124) = GetLastError();
      LODWORD(dwFlagsh) = v12;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        197,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
        "Windows::Compat::Appraiser::Utilities::SendRequest",
        dwFlagsh,
        (int)"Failed to set proxy credentials: [%d].",
        v124);
LABEL_168:
      v10 = v136;
      v11 = v140;
      goto LABEL_169;
    }
LABEL_134:
    ;
  }
  if ( (((_DWORD)v133 - 302) & 0xFFFFFFFA) != 0 || (_DWORD)v133 == 306 )
    goto LABEL_134;
  AslLogCallPrintf(3, "Windows::Compat::Appraiser::Utilities::SendRequest", 2774, "Redirecting HTTP request.");
  if ( !WinHttpQueryHeaders(*v55, 0x21u, 0, 0, &dwBufferLength, 0) && GetLastError() != 122 )
  {
    v67 = GetLastError();
    AslLogCallPrintf(
      3,
      "Windows::Compat::Appraiser::Utilities::SendRequest",
      2784,
      "Failed to query HTTP redirect location size: [%d].",
      v67);
    v58 = GetLastError();
    v59 = GetLastError();
    if ( v59 > 0 )
      v59 = (unsigned __int16)v59 | 0x80070000;
    v60 = "Failed to query HTTP redirect location size: [%d].";
    v61 = -31;
    goto LABEL_132;
  }
  v68 = dwBufferLength;
  v69 = GetProcessHeap();
  v70 = (wchar_t *)HeapAlloc(v69, 8u, v68);
  v140 = v70;
  if ( !v70 )
  {
    AslLogCallPrintf(
      3,
      "Windows::Compat::Appraiser::Utilities::SendRequest",
      2792,
      "Failed to allocate space for the redirect http target.");
    v12 = -2147024882;
    goto LABEL_168;
  }
  if ( !WinHttpQueryHeaders(*v136, 0x21u, 0, v70, &dwBufferLength, 0) )
  {
    v71 = GetLastError();
    AslLogCallPrintf(
      3,
      "Windows::Compat::Appraiser::Utilities::SendRequest",
      2805,
      "Failed to query HTTP redirect location: [%d].",
      v71);
    v58 = GetLastError();
    v59 = GetLastError();
    if ( v59 > 0 )
      v59 = (unsigned __int16)v59 | 0x80070000;
    v60 = "Failed to query HTTP redirect location: [%d].";
    v61 = -10;
LABEL_132:
    LODWORD(v124) = v58;
    LODWORD(ppwszAcceptTypesd) = (_DWORD)v60;
    LODWORD(dwFlagsf) = v59;
LABEL_133:
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      v61,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
      "Windows::Compat::Appraiser::Utilities::SendRequest",
      dwFlagsf,
      (int)ppwszAcceptTypesd,
      v124);
    goto LABEL_134;
  }
  v11 = v140;
  AslLogCallPrintf(3, "Windows::Compat::Appraiser::Utilities::SendRequest", 2810, "Redirect target is %ls", v140);
  WinHttpCloseHandle(hConnect);
  v10 = v136;
  if ( *v136 )
  {
    WinHttpCloseHandle(*v136);
    *v10 = 0;
  }
  v132 = 1;
  v12 = -2147467259;
LABEL_170:
  v84 = lpMem;
  if ( lpMem )
  {
    v85 = GetProcessHeap();
    HeapFree(v85, 0, v84);
  }
  if ( v12 < 0 )
  {
LABEL_173:
    v9 = v144;
    goto LABEL_174;
  }
  v9 = v144;
LABEL_179:
  if ( v131 && !RevertToSelf() )
  {
    v86 = GetLastError();
    v87 = v86;
    if ( v86 > 0 )
      v87 = (unsigned __int16)v86 | 0x80070000;
    if ( v87 >= 0 )
      v87 = -2147467259;
    v88 = GetLastError();
    AslLogCallPrintf(
      3,
      "Windows::Compat::Appraiser::Utilities::SendRequest",
      2886,
      "Failed to un-impersonate user: [%d].",
      v88);
    LODWORD(v124) = GetLastError();
    LODWORD(dwFlagsl) = v87;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      71,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
      "Windows::Compat::Appraiser::Utilities::SendRequest",
      dwFlagsl,
      (int)"Failed to un-impersonate user: [%d].",
      v124);
    TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v157);
    v89 = (TraceLoggingCorrelationVector *)v157;
    if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
      v89 = Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
    TraceLoggingCorrelationVector::ToString(v89, v158);
    if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
      UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler);
    GeneralProvider = Windows::Compat::Shared::Telemetry::TelemetryProvider::GetGeneralProvider((Windows::Compat::Shared::Telemetry::TelemetryProvider *)&APPRAISER_INSTRUMENTATION_PROVIDER);
    v91 = (int)GeneralProvider;
    if ( *(_DWORD *)GeneralProvider > 5u )
    {
      if ( (unsigned __int8)tlgKeywordOn(GeneralProvider, 0x200000000000LL) )
      {
        v92 = _tlgWrapSz<unsigned short>::_tlgWrapSz<unsigned short>(&v148, v158);
        v135 = v87;
        v93 = v92;
        v94 = _tlgWrapSz<unsigned short>::_tlgWrapSz<unsigned short>(
                &v147,
                "Windows::Compat::Appraiser::Utilities::SendRequest");
        v95 = _tlgWrapSz<unsigned short>::_tlgWrapSz<unsigned short>(
                &v146,
                "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp");
        HIDWORD(v133) = 2887;
        v96 = Windows::Compat::Appraiser::WicaFactory::Pcfp();
        v97 = _tlgWrapSz<unsigned short>::_tlgWrapSz<unsigned short>(&v154, v96);
        v99 = *Windows::Compat::Appraiser::GetCurrentSystemTime((Windows::Compat::Appraiser *)&SystemTime, v98);
        v145 = (char *)&v156;
        v156 = v99;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v91,
          (unsigned int)&unk_1802A21A4,
          v100,
          v101,
          (__int64)&v145,
          v97,
          (__int64)&v133 + 4,
          v95,
          v94,
          (__int64)&v135,
          v93);
      }
    }
    v102 = GetLastError();
    ExitProcess(v102);
  }
  if ( (char *)hToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hToken);
  if ( v132 )
  {
    if ( v11 )
    {
      v103 = Windows::Compat::Appraiser::Utilities::SendRequest(v10, v9, v11, v151, v153, a6, a7 + 1);
      v12 = v103;
      if ( v103 < 0 )
      {
        AslLogCallPrintf(
          3,
          "Windows::Compat::Appraiser::Utilities::SendRequest",
          2903,
          "Sending redirect request failed: [0x%x].",
          v103);
        AslLogCallPrintf(3, "Windows::Compat::Appraiser::Utilities::SendRequest", 2904, "Redirect target %ls.", v11);
      }
LABEL_200:
      v104 = GetProcessHeap();
      HeapFree(v104, 0, v11);
    }
  }
  else if ( v11 )
  {
    goto LABEL_200;
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800911bc  push    rbp
0x1800911be  push    rbx
0x1800911bf  push    rsi
0x1800911c0  push    rdi
0x1800911c1  push    r12
0x1800911c3  push    r13
0x1800911c5  push    r14
0x1800911c7  push    r15
0x1800911c9  lea     rbp, [rsp-19F8h]
0x1800911d1  mov     eax, 1AF8h
0x1800911d6  call    _alloca_probe
0x1800911db  sub     rsp, rax
0x1800911de  mov     rax, cs:__security_cookie
0x1800911e5  xor     rax, rsp
0x1800911e8  mov     [rbp+1A30h+var_50], rax
0x1800911ef  mov     rax, [rbp+1A30h+arg_20]
0x1800911f6  xor     esi, esi
0x1800911f8  mov     ebx, r9d
0x1800911fb  mov     [rbp+1A30h+var_1A88], rdx
0x1800911ff  mov     r15, r8
0x180091202  mov     [rsp+1B30h+var_1AB8], rcx
0x180091207  mov     r14, rdx
0x18009120a  mov     [rbp+1A30h+var_1A50], ebx
0x18009120d  mov     r12, rcx
0x180091210  mov     [rbp+1A30h+var_1A30], rax
0x180091214  lea     edi, [rsi+68h]
0x180091217  mov     [rbp+1A30h+pcchOut], esi
0x18009121a  mov     r8d, edi; Size
0x18009121d  mov     [rbp+1A30h+Buffer], esi
0x180091220  xor     edx, edx; Val
0x180091222  mov     dword ptr [rsp+1B30h+var_1ACC], esi
0x180091226  lea     rcx, [rbp+1A30h+UrlComponents]; void *
0x18009122a  mov     [rsp+1B30h+dwBufferLength], esi
0x18009122e  mov     [rbp+1A30h+dwSupportedSchemes], esi
0x180091231  mov     [rbp+1A30h+dwFirstScheme], esi
0x180091234  mov     [rbp+1A30h+pdwAuthTarget], esi
0x180091237  mov     dword ptr [rsp+1B30h+var_1ACC+4], esi
0x18009123b  call    memset_0
0x180091240  cmp     [rbp+1A30h+arg_30], 0Ah
0x180091247  mov     r13d, esi
0x18009124a  mov     [rbp+1A30h+UrlComponents.dwStructSize], edi
0x18009124d  mov     [rbp+1A30h+UrlComponents.dwUrlPathLength], 1
0x180091254  mov     [rbp+1A30h+lpMem], rsi
0x180091258  mov     [rsp+1B30h+var_1AD0], sil
0x18009125d  mov     [rsp+1B30h+var_1ACF], sil
0x180091262  mov     [rbp+1A30h+var_1AA0], rsi
0x180091266  mov     [rbp+1A30h+pwszPassword], si
0x18009126d  mov     [rbp+1A30h+pwszUserName], si
0x180091274  mov     [rbp+1A30h+hToken], rsi
0x180091278  jb      short loc_1800912CF
0x18009127a  lea     rbx, aTooManyHttpFor; "Too many HTTP forwarding links."
0x180091281  mov     r8d, 99Ah
0x180091287  lea     rdi, aWindowsCompatA_462; "Windows::Compat::Appraiser::Utilities::"...
0x18009128e  mov     r9, rbx
0x180091291  lea     esi, [r13+3]
0x180091295  mov     rdx, rdi
0x180091298  mov     ecx, esi
0x18009129a  call    AslLogCallPrintf
0x18009129f  mov     [rsp+1B30h+ppwszAcceptTypes], rbx; int
0x1800912a4  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appcompat\\appraiser\\he"...
0x1800912ab  mov     ebx, 800703E9h
0x1800912b0  lea     ecx, [rsi-2]; this
0x1800912b3  mov     r9, rdi; char *
0x1800912b6  mov     [rsp+1B30h+dwFlags], ebx; char *
0x1800912ba  mov     edx, 99Bh; bool
0x1800912bf  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800912c4  mov     r15d, 80004005h
0x1800912ca  jmp     loc_180092565
0x1800912cf  xor     r9d, r9d; pszProxyBypassW
0x1800912d2  mov     [rsp+1B30h+dwFlags], esi; dwFlags
0x1800912d6  xor     r8d, r8d; pszProxyW
0x1800912d9  lea     rcx, pszAgentW; "WicaAgent"
0x1800912e0  mov     edx, ebx; dwAccessType
0x1800912e2  call    cs:__imp_WinHttpOpen
0x1800912e8  mov     [r14], rax
0x1800912eb  test    rax, rax
0x1800912ee  jnz     loc_18009140A
0x1800912f4  call    cs:__imp_GetLastError
0x1800912fa  cmp     ebx, 4
0x1800912fd  jnz     loc_1800913B4
0x180091303  cmp     eax, 57h ; 'W'
0x180091306  jnz     short loc_180091334
0x180091308  lea     esi, [rax-54h]
0x18009130b  mov     ebx, 80070057h
0x180091310  lea     rdi, aWindowsCompatA_462; "Windows::Compat::Appraiser::Utilities::"...
0x180091317  mov     [rsp+1B30h+dwFlags], ebx
0x18009131b  mov     rdx, rdi
0x18009131e  lea     r9, aInvalidParamet_0; "Invalid parameter provided while trying"...
0x180091325  mov     ecx, esi
0x180091327  mov     r8d, 9AEh
0x18009132d  call    AslLogCallPrintf
0x180091332  jmp     short loc_1800912C4
0x180091334  call    cs:__imp_GetLastError
0x18009133a  lea     r15, aErrorOpeningTh; "Error opening the internet with auto pr"...
0x180091341  mov     esi, 3
0x180091346  lea     rdi, aWindowsCompatA_462; "Windows::Compat::Appraiser::Utilities::"...
0x18009134d  mov     [rsp+1B30h+dwFlags], eax
0x180091351  mov     r9, r15
0x180091354  mov     rdx, rdi
0x180091357  mov     ecx, esi
0x180091359  mov     r8d, 9B2h
0x18009135f  call    AslLogCallPrintf
0x180091364  call    cs:__imp_GetLastError
0x18009136a  mov     ebx, eax
0x18009136c  test    eax, eax
0x18009136e  jle     short loc_180091379
0x180091370  movzx   ebx, ax
0x180091373  or      ebx, 80070000h
0x180091379  test    ebx, ebx
0x18009137b  mov     eax, 80004005h
0x180091380  cmovns  ebx, eax
0x180091383  call    cs:__imp_GetLastError
0x180091389  mov     edx, 9B3h; bool
0x18009138e  mov     [rsp+1B30h+var_1B00], eax; char *
0x180091392  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appcompat\\appraiser\\he"...
0x180091399  mov     [rsp+1B30h+ppwszAcceptTypes], r15; int
0x18009139e  mov     r9, rdi; char *
0x1800913a1  mov     ecx, 1; this
0x1800913a6  mov     [rsp+1B30h+dwFlags], ebx; char *
0x1800913aa  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800913af  jmp     loc_1800912C4
0x1800913b4  lea     r15, aErrorOpeningTh_0; "Error opening the internet: [%d]."
0x1800913bb  mov     [rsp+1B30h+dwFlags], eax
0x1800913bf  lea     rdi, aWindowsCompatA_462; "Windows::Compat::Appraiser::Utilities::"...
0x1800913c6  mov     esi, 3
0x1800913cb  mov     r9, r15
0x1800913ce  mov     rdx, rdi
0x1800913d1  mov     ecx, esi
0x1800913d3  mov     r8d, 9B7h
0x1800913d9  call    AslLogCallPrintf
0x1800913de  call    cs:__imp_GetLastError
0x1800913e4  mov     ebx, eax
0x1800913e6  test    eax, eax
0x1800913e8  jle     short loc_1800913F3
0x1800913ea  movzx   ebx, ax
0x1800913ed  or      ebx, 80070000h
0x1800913f3  test    ebx, ebx
0x1800913f5  mov     eax, 80004005h
0x1800913fa  cmovns  ebx, eax
0x1800913fd  call    cs:__imp_GetLastError
0x180091403  mov     edx, 9B8h
0x180091408  jmp     short loc_18009138E
0x18009140a  lea     r9, [rbp+1A30h+UrlComponents]; lpUrlComponents
0x18009140e  xor     r8d, r8d; dwFlags
0x180091411  xor     edx, edx; dwUrlLength
0x180091413  mov     rcx, r15; pwszUrl
0x180091416  call    cs:__imp_WinHttpCrackUrl
0x18009141c  test    eax, eax
0x18009141e  jnz     loc_1800914B2
0x180091424  call    cs:__imp_GetLastError
0x18009142a  mov     dword ptr [rsp+1B30h+ppwszAcceptTypes], eax
0x18009142e  lea     rdi, aWindowsCompatA_462; "Windows::Compat::Appraiser::Utilities::"...
0x180091435  mov     esi, 3
0x18009143a  mov     qword ptr [rsp+1B30h+dwFlags], r15
0x18009143f  mov     rdx, rdi
0x180091442  lea     r9, aCouldNotCrackU; "Could not crack url %ls: [%d]."
0x180091449  mov     ecx, esi
0x18009144b  mov     r8d, 9C3h
0x180091451  call    AslLogCallPrintf
0x180091456  call    cs:__imp_GetLastError
0x18009145c  mov     ebx, eax
0x18009145e  test    eax, eax
0x180091460  jle     short loc_18009146B
0x180091462  movzx   ebx, ax
0x180091465  or      ebx, 80070000h
0x18009146b  test    ebx, ebx
0x18009146d  mov     eax, 80004005h
0x180091472  cmovns  ebx, eax
0x180091475  call    cs:__imp_GetLastError
0x18009147b  mov     dword ptr [rsp+1B30h+var_1AF8], eax
0x18009147f  mov     edx, 9C4h; bool
0x180091484  lea     rax, aCouldNotCrackU; "Could not crack url %ls: [%d]."
0x18009148b  mov     qword ptr [rsp+1B30h+var_1B00], r15; char *
0x180091490  mov     [rsp+1B30h+ppwszAcceptTypes], rax; int
0x180091495  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appcompat\\appraiser\\he"...
0x18009149c  mov     [rsp+1B30h+dwFlags], ebx; char *
0x1800914a0  mov     r9, rdi; char *
0x1800914a3  mov     ecx, 1; this
0x1800914a8  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800914ad  jmp     loc_1800912C4
0x1800914b2  cmp     [rbp+1A30h+UrlComponents.nScheme], 2
0x1800914b6  jnz     short loc_1800914C7
0x1800914b8  mov     r8d, 9C9h
0x1800914be  lea     r9, aAttemptingInte_0; "Attempting INTERNET_SCHEME_HTTPS (https"...
0x1800914c5  jmp     short loc_1800914E9
0x1800914c7  cmp     [rbp+1A30h+UrlComponents.nScheme], 1
0x1800914cb  jnz     short loc_1800914DC
0x1800914cd  mov     r8d, 9CDh
0x1800914d3  lea     r9, aAttemptingInte; "Attempting INTERNET_SCHEME_HTTP (http) "...
0x1800914da  jmp     short loc_1800914E9
0x1800914dc  mov     r8d, 9D1h
0x1800914e2  lea     r9, aAttemptingUnkn; "Attempting unknown http type request."
0x1800914e9  lea     rdi, aWindowsCompatA_462; "Windows::Compat::Appraiser::Utilities::"...
0x1800914f0  mov     esi, 3
0x1800914f5  mov     rdx, rdi
0x1800914f8  mov     ecx, esi
0x1800914fa  call    AslLogCallPrintf
0x1800914ff  lea     r9, aUrlLs; "URL %ls."
0x180091506  mov     qword ptr [rsp+1B30h+dwFlags], r15
0x18009150b  mov     r8d, 9D3h
0x180091511  mov     rdx, rdi
0x180091514  mov     ecx, esi
0x180091516  call    AslLogCallPrintf
0x18009151b  lea     r9d, [rsi-1]; dwPart
0x18009151f  mov     [rbp+1A30h+pcchOut], 100h
0x180091526  lea     r8, [rbp+1A30h+pcchOut]; pcchOut
0x18009152a  mov     [rsp+1B30h+dwFlags], r13d; dwFlags
0x18009152f  lea     rdx, [rbp+1A30h+pszOut]; pszOut
0x180091536  mov     rcx, r15; pszIn
0x180091539  call    cs:__imp_UrlGetPartW
0x18009153f  mov     ebx, eax
0x180091541  test    eax, eax
0x180091543  jns     short loc_18009159C
0x180091545  mov     dword ptr [rsp+1B30h+ppwszAcceptTypes], eax
0x180091549  lea     r14, aUrlgetpartFail; "UrlGetPart failed to retrieve host name"...
0x180091550  mov     r9, r14
0x180091553  mov     qword ptr [rsp+1B30h+dwFlags], r15
0x180091558  mov     r8d, 9E4h
0x18009155e  mov     rdx, rdi
0x180091561  mov     ecx, esi
0x180091563  call    AslLogCallPrintf
0x180091568  mov     dword ptr [rsp+1B30h+var_1AF8], ebx
0x18009156c  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appcompat\\appraiser\\he"...
0x180091573  mov     qword ptr [rsp+1B30h+var_1B00], r15; char *
0x180091578  lea     ecx, [rsi-2]; this
0x18009157b  mov     [rsp+1B30h+ppwszAcceptTypes], r14; int
0x180091580  mov     r9, rdi; char *
0x180091583  mov     edx, 9E5h; bool
0x180091588  mov     [rsp+1B30h+dwFlags], ebx; char *
0x18009158c  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x180091591  mov     r15d, 80004005h
0x180091597  jmp     loc_180092561
0x18009159c  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800915a2  test    al, 1
0x1800915a4  jz      short loc_1800915CA
0x1800915a6  mov     dword ptr [rsp+1B30h+ppwszAcceptTypes], ebx
0x1800915aa  lea     r9, aUrlgetpartFail; "UrlGetPart failed to retrieve host name"...
0x1800915b1  mov     r8, rdi; char *
0x1800915b4  mov     qword ptr [rsp+1B30h+dwFlags], r15
0x1800915b9  lea     rdx, aOnecoreBaseApp_7; "onecore\\base\\appcompat\\appraiser\\he"...
0x1800915c0  mov     ecx, 9E5h; unsigned int
0x1800915c5  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800915ca  lea     rax, [rbp+1A30h+pszOut]
0x1800915d1  mov     r8d, 9E7h
0x1800915d7  lea     r9, aHostNameIsLs; "Host name is %ls."
0x1800915de  mov     qword ptr [rsp+1B30h+dwFlags], rax
0x1800915e3  mov     rdx, rdi
0x1800915e6  mov     ecx, esi
0x1800915e8  call    AslLogCallPrintf
0x1800915ed  mov     rcx, [r14]; hSession
0x1800915f0  lea     rdx, [rbp+1A30h+pszOut]; pswzServerName
0x1800915f7  mov     r8d, 50h ; 'P'; nServerPort
0x1800915fd  xor     r9d, r9d; dwReserved
0x180091600  call    cs:__imp_WinHttpConnect
0x180091606  mov     [rbp+1A30h+hConnect], rax
0x18009160a  test    rax, rax
0x18009160d  jnz     short loc_180091683
0x18009160f  call    cs:__imp_GetLastError
0x180091615  mov     dword ptr [rsp+1B30h+ppwszAcceptTypes], eax
0x180091619  lea     r15, aFailedToConnec; "Failed to connect to host %ls: [%d]."
0x180091620  lea     rax, [rbp+1A30h+pszOut]
0x180091627  mov     r8d, 9EFh
0x18009162d  mov     r9, r15
0x180091630  mov     qword ptr [rsp+1B30h+dwFlags], rax
0x180091635  mov     rdx, rdi
0x180091638  mov     ecx, esi
0x18009163a  call    AslLogCallPrintf
0x18009163f  call    cs:__imp_GetLastError
0x180091645  mov     ebx, eax
0x180091647  test    eax, eax
0x180091649  jle     short loc_180091654
0x18009164b  movzx   ebx, ax
0x18009164e  or      ebx, 80070000h
0x180091654  test    ebx, ebx
0x180091656  mov     eax, 80004005h
0x18009165b  cmovns  ebx, eax
0x18009165e  call    cs:__imp_GetLastError
0x180091664  mov     dword ptr [rsp+1B30h+var_1AF8], eax
0x180091668  mov     edx, 9F0h
0x18009166d  lea     rax, [rbp+1A30h+pszOut]
0x180091674  mov     qword ptr [rsp+1B30h+var_1B00], rax
0x180091679  mov     [rsp+1B30h+ppwszAcceptTypes], r15
0x18009167e  jmp     loc_180091495
0x180091683  cmp     [rbp+1A30h+arg_28], r13b
0x18009168a  jz      loc_1800917CB
0x180091690  lea     rdx, [rsp+1B30h+var_1ACC+4]; int *
0x180091695  lea     rcx, [rbp+1A30h+hToken]; void **
0x180091699  call    ?FindUserSession@Utilities@Appraiser@Compat@Windows@@SAJPEAPEAXPEAH@Z; Windows::Compat::Appraiser::Utilities::FindUserSession(void * *,int *)
0x18009169e  mov     ebx, eax
0x1800916a0  test    eax, eax
0x1800916a2  jns     short loc_1800916F3
0x1800916a4  lea     r14, aFailedToLookFo; "Failed to look for current user session"...
0x1800916ab  mov     [rsp+1B30h+dwFlags], eax
0x1800916af  mov     r9, r14
0x1800916b2  mov     r8d, 9FFh
0x1800916b8  mov     rdx, rdi
0x1800916bb  mov     ecx, esi
0x1800916bd  call    AslLogCallPrintf
0x1800916c2  mov     [rsp+1B30h+var_1B00], ebx; char *
0x1800916c6  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appcompat\\appraiser\\he"...
  ... truncated ...
```
