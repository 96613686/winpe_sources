# InitializeSls

- ea: `0x1800447a0`
- end: `0x180044905`
- name: `InitializeSls`
- size: `357`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800447ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800447dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004480d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004483e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004486f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800448a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800448d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800447ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800447dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004480d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004483e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004486f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800448a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800448d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800447cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180044800`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180044831`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180044862`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180044893`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800448c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800448f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800447cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180044800`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180044831`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180044862`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180044893`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800448c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800448f5`

## string_xrefs

- `0x18004482a`: `https://login.windows.net/common`
- `0x1800447c8`: `www.microsoft.com`
- `0x18004488c`: `mobilling.microsoft.com`
- `0x18004485b`: `https://onestore.microsoft.com`
- `0x1800448ee`: `https://purchase.mp.microsoft.com`
- `0x1800448bd`: `user.auth.xboxlive.com`

## pseudocode

```c
__int64 __fastcall InitializeSls(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)
{
  WindowsDeleteString(qword_1800665D8);
  qword_1800665D8 = 0;
  WindowsCreateString(L"www.microsoft.com", 0x11u, &qword_1800665D8);
  WindowsDeleteString(qword_1800665E8);
  qword_1800665E8 = 0;
  WindowsCreateString(L"mbi_ssl", 7u, &qword_1800665E8);
  WindowsDeleteString(qword_1800665F8);
  qword_1800665F8 = 0;
  WindowsCreateString(L"https://login.windows.net/common", 0x20u, &qword_1800665F8);
  WindowsDeleteString(qword_180066608);
  qword_180066608 = 0;
  WindowsCreateString(L"https://onestore.microsoft.com", 0x1Eu, &qword_180066608);
  WindowsDeleteString(qword_180066618);
  qword_180066618 = 0;
  WindowsCreateString(L"mobilling.microsoft.com", 0x17u, &qword_180066618);
  WindowsDeleteString(qword_180066628);
  qword_180066628 = 0;
  WindowsCreateString(L"user.auth.xboxlive.com", 0x16u, &qword_180066628);
  WindowsDeleteString(qword_180066638);
  qword_180066638 = 0;
  WindowsCreateString(L"https://purchase.mp.microsoft.com", 0x21u, &qword_180066638);
  return 1;
}

```

## disassembly

```asm
0x1800447a0  sub     rsp, 28h
0x1800447a4  mov     rcx, cs:qword_1800665D8; string
0x1800447ab  call    cs:__imp_WindowsDeleteString
0x1800447b1  lea     r8, qword_1800665D8; string
0x1800447b8  mov     cs:qword_1800665D8, 0
0x1800447c3  mov     edx, 11h; length
0x1800447c8  lea     rcx, aWwwMicrosoftCo; "www.microsoft.com"
0x1800447cf  call    cs:__imp_WindowsCreateString
0x1800447d5  mov     rcx, cs:qword_1800665E8; string
0x1800447dc  call    cs:__imp_WindowsDeleteString
0x1800447e2  lea     r8, qword_1800665E8; string
0x1800447e9  mov     cs:qword_1800665E8, 0
0x1800447f4  mov     edx, 7; length
0x1800447f9  lea     rcx, aMbiSsl_0; "mbi_ssl"
0x180044800  call    cs:__imp_WindowsCreateString
0x180044806  mov     rcx, cs:qword_1800665F8; string
0x18004480d  call    cs:__imp_WindowsDeleteString
0x180044813  lea     r8, qword_1800665F8; string
0x18004481a  mov     cs:qword_1800665F8, 0
0x180044825  mov     edx, 20h ; ' '; length
0x18004482a  lea     rcx, aHttpsLoginWind; "https://login.windows.net/common"
0x180044831  call    cs:__imp_WindowsCreateString
0x180044837  mov     rcx, cs:qword_180066608; string
0x18004483e  call    cs:__imp_WindowsDeleteString
0x180044844  lea     r8, qword_180066608; string
0x18004484b  mov     cs:qword_180066608, 0
0x180044856  mov     edx, 1Eh; length
0x18004485b  lea     rcx, aHttpsOnestoreM; "https://onestore.microsoft.com"
0x180044862  call    cs:__imp_WindowsCreateString
0x180044868  mov     rcx, cs:qword_180066618; string
0x18004486f  call    cs:__imp_WindowsDeleteString
0x180044875  lea     r8, qword_180066618; string
0x18004487c  mov     cs:qword_180066618, 0
0x180044887  mov     edx, 17h; length
0x18004488c  lea     rcx, aMobillingMicro; "mobilling.microsoft.com"
0x180044893  call    cs:__imp_WindowsCreateString
0x180044899  mov     rcx, cs:qword_180066628; string
0x1800448a0  call    cs:__imp_WindowsDeleteString
0x1800448a6  lea     r8, qword_180066628; string
0x1800448ad  mov     cs:qword_180066628, 0
0x1800448b8  mov     edx, 16h; length
0x1800448bd  lea     rcx, aUserAuthXboxli; "user.auth.xboxlive.com"
0x1800448c4  call    cs:__imp_WindowsCreateString
0x1800448ca  mov     rcx, cs:qword_180066638; string
0x1800448d1  call    cs:__imp_WindowsDeleteString
0x1800448d7  lea     r8, qword_180066638; string
0x1800448de  mov     cs:qword_180066638, 0
0x1800448e9  mov     edx, 21h ; '!'; length
0x1800448ee  lea     rcx, aHttpsPurchaseM; "https://purchase.mp.microsoft.com"
0x1800448f5  call    cs:__imp_WindowsCreateString
0x1800448fb  mov     eax, 1
0x180044900  add     rsp, 28h
0x180044904  retn
```
