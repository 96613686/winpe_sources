# Windows::Compat::Appraiser::Utilities::ExtractResourceStringAlloc(ushort * *,ulong,ushort const *)

- ea: `0x180087348`
- end: `0x180087623`
- name: `?ExtractResourceStringAlloc@Utilities@Appraiser@Compat@Windows@@SAJPEAPEAGKPEBG@Z`
- size: `731`
- prototype: `static int(unsigned __int16 **, unsigned int, const unsigned __int16 *)`
- caller_count: `9`
- callee_count: `5`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800be304`
- `0x1800be60c`
- `0x1800beb74`
- `0x1800bf3a8`
- `0x1800bf8a8`
- `0x1801edcf0`
- `0x1801f5c50`
- `0x1801fc9d4`
- `0x1801fcaf8`

## callees

- `0x180008570`
- `0x18002ebb8`
- `0x1800301d0`
- `0x18006a45c`
- `0x180087348`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800873b3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800873b3`
- `KERNEL32!GetFullPathNameW` at `0x180087398`
- `KERNEL32!GetFullPathNameW` at `0x180087398`
- `KERNEL32!LoadLibraryExW` at `0x180087405`
- `KERNEL32!LoadLibraryExW` at `0x180087405`
- `KERNEL32!FreeLibrary` at `0x180087571`
- `KERNEL32!FreeLibrary` at `0x180087571`
- `KERNEL32!GetProcessHeap` at `0x1800874d2`
- `KERNEL32!GetProcessHeap` at `0x1800875dc`
- `KERNEL32!GetProcessHeap` at `0x1800874d2`
- `KERNEL32!GetProcessHeap` at `0x1800875dc`
- `KERNEL32!HeapAlloc` at `0x1800874e0`
- `KERNEL32!HeapAlloc` at `0x1800874e0`
- `KERNEL32!GetLastError` at `0x180087413`
- `KERNEL32!GetLastError` at `0x180087432`
- `KERNEL32!GetLastError` at `0x18008746a`
- `KERNEL32!GetLastError` at `0x180087489`
- `KERNEL32!GetLastError` at `0x18008757d`
- `KERNEL32!GetLastError` at `0x18008759c`
- `KERNEL32!GetLastError` at `0x180087413`
- `KERNEL32!GetLastError` at `0x180087432`
- `KERNEL32!GetLastError` at `0x18008746a`
- `KERNEL32!GetLastError` at `0x180087489`
- `KERNEL32!GetLastError` at `0x18008757d`
- `KERNEL32!GetLastError` at `0x18008759c`
- `KERNEL32!HeapFree` at `0x1800875ea`
- `KERNEL32!HeapFree` at `0x1800875ea`
- `USER32!LoadStringW` at `0x18008745d`
- `USER32!LoadStringW` at `0x18008745d`

## string_xrefs

- `0x180087513`: `Failed to copy to string %ls [0x%x].`
- `0x180087544`: `Failed to copy to string %ls [0x%x].`
- `0x1800873f0`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x1800874a9`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x180087556`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x1800875c3`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x1800873dd`: `Must provide full path to extract, '%ls' has full path of '%ls'.`
- `0x180087441`: `Could not OpenHandle to resource: [%d].`
- `0x1800875ab`: `Failed to get full path from resource path: [%d].`
- `0x1800873e4`: `Windows::Compat::Appraiser::Utilities::ExtractResourceStringAlloc`
- `0x1800874b4`: `Windows::Compat::Appraiser::Utilities::ExtractResourceStringAlloc`
- `0x18008754f`: `Windows::Compat::Appraiser::Utilities::ExtractResourceStringAlloc`
- `0x1800875bc`: `Windows::Compat::Appraiser::Utilities::ExtractResourceStringAlloc`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Appraiser::Utilities::ExtractResourceStringAlloc(
        unsigned __int16 **a1,
        UINT a2,
        const unsigned __int16 *a3)
{
  HMODULE Library; // rax
  HMODULE v7; // r15
  signed int v8; // eax
  signed int v9; // ebx
  char v10; // dl
  const char *v11; // rax
  int StringW; // eax
  unsigned __int64 v13; // r14
  signed int v14; // eax
  char v15; // dl
  unsigned __int64 v16; // r12
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v18; // rax
  int v19; // eax
  signed int LastError; // eax
  void *v21; // rdi
  HANDLE v22; // rax
  char *v24; // [rsp+20h] [rbp-278h]
  const char *v25; // [rsp+28h] [rbp-270h]
  char *v26; // [rsp+30h] [rbp-268h]
  DWORD v27; // [rsp+38h] [rbp-260h]
  WCHAR v28[4]; // [rsp+40h] [rbp-258h] BYREF
  WCHAR Buffer[264]; // [rsp+50h] [rbp-248h] BYREF

  *a1 = 0;
  *(_QWORD *)v28 = 0;
  if ( GetFullPathNameW(a3, 0x104u, Buffer, 0) - 1 > 0x103 )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( v9 >= 0 )
      v9 = -2147467259;
    LODWORD(v26) = GetLastError();
    v10 = 62;
    v11 = "Failed to get full path from resource path: [%d].";
    goto LABEL_32;
  }
  if ( (unsigned int)_o__wcsicmp(a3, Buffer) && (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x344u,
      "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
      "Windows::Compat::Appraiser::Utilities::ExtractResourceStringAlloc",
      "Must provide full path to extract, '%ls' has full path of '%ls'.",
      a3,
      Buffer);
  Library = LoadLibraryExW(a3, 0, 0x22u);
  v7 = Library;
  if ( Library )
  {
    StringW = LoadStringW(Library, a2, v28, 0);
    v13 = StringW;
    if ( !StringW )
    {
      v14 = GetLastError();
      v9 = v14;
      if ( v14 > 0 )
        v9 = (unsigned __int16)v14 | 0x80070000;
      if ( v9 >= 0 )
        v9 = -2147467259;
      v27 = GetLastError();
      v15 = 84;
      LODWORD(v26) = a2;
      v25 = "Could not load resource with id %d: [%d].";
      goto LABEL_17;
    }
    v16 = StringW + 1;
    ProcessHeap = GetProcessHeap();
    v18 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 2 * v16);
    *a1 = v18;
    if ( v18 )
    {
      v19 = StringCchCopyNW(v18, v16, *(const unsigned __int16 **)v28, v13);
      v9 = v19;
      if ( v19 < 0 )
      {
        v27 = v19;
        v15 = 91;
        v26 = *(char **)v28;
        v25 = "Failed to copy to string %ls [0x%x].";
LABEL_17:
        LODWORD(v24) = v9;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          v15,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
          "Windows::Compat::Appraiser::Utilities::ExtractResourceStringAlloc",
          v24,
          (int)v25,
          v26,
          v27);
        goto LABEL_25;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x35Bu,
          "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
          "Windows::Compat::Appraiser::Utilities::ExtractResourceStringAlloc",
          "Failed to copy to string %ls [0x%x].",
          *(const wchar_t **)v28,
          v19);
      v9 = 0;
    }
    else
    {
      v9 = -2147024882;
    }
LABEL_25:
    FreeLibrary(v7);
    if ( v9 >= 0 )
      return (unsigned int)v9;
    goto LABEL_33;
  }
  v8 = GetLastError();
  v9 = v8;
  if ( v8 > 0 )
    v9 = (unsigned __int16)v8 | 0x80070000;
  if ( v9 >= 0 )
    v9 = -2147467259;
  LODWORD(v26) = GetLastError();
  v10 = 74;
  v11 = "Could not OpenHandle to resource: [%d].";
LABEL_32:
  LODWORD(v24) = v9;
  Windows::Compat::Appraiser::WriteLog(
    (Windows::Compat::Appraiser *)1,
    v10,
    (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
    "Windows::Compat::Appraiser::Utilities::ExtractResourceStringAlloc",
    v24,
    (int)v11,
    v26);
LABEL_33:
  v21 = *a1;
  if ( *a1 )
  {
    v22 = GetProcessHeap();
    HeapFree(v22, 0, v21);
    *a1 = 0;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180087348  mov     [rsp+arg_18], rbx
0x18008734d  push    rdi
0x18008734e  push    r12
0x180087350  push    r13
0x180087352  push    r14
0x180087354  push    r15
0x180087356  sub     rsp, 270h
0x18008735d  mov     rax, cs:__security_cookie
0x180087364  xor     rax, rsp
0x180087367  mov     [rsp+298h+var_38], rax
0x18008736f  mov     rbx, r8
0x180087372  mov     qword ptr [rcx], 0
0x180087379  mov     r12d, edx
0x18008737c  mov     qword ptr [rsp+298h+var_258], 0
0x180087385  mov     r13, rcx
0x180087388  lea     r8, [rsp+298h+Buffer]; lpBuffer
0x18008738d  mov     rcx, rbx; lpFileName
0x180087390  xor     r9d, r9d; lpFilePart
0x180087393  mov     edx, 104h; nBufferLength
0x180087398  call    cs:__imp_GetFullPathNameW
0x18008739e  dec     eax
0x1800873a0  cmp     eax, 103h
0x1800873a5  ja      loc_18008757D
0x1800873ab  lea     rdx, [rsp+298h+Buffer]
0x1800873b0  mov     rcx, rbx
0x1800873b3  call    cs:__imp__o__wcsicmp
0x1800873b9  mov     edi, 1
0x1800873be  test    eax, eax
0x1800873c0  jz      short loc_1800873FC
0x1800873c2  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800873c8  and     eax, edi
0x1800873ca  test    al, al
0x1800873cc  jz      short loc_1800873FC
0x1800873ce  lea     rax, [rsp+298h+Buffer]
0x1800873d3  mov     ecx, 344h; unsigned int
0x1800873d8  mov     qword ptr [rsp+298h+var_270], rax
0x1800873dd  lea     r9, aMustProvideFul; "Must provide full path to extract, '%ls"...
0x1800873e4  lea     r8, aWindowsCompatA_370; "Windows::Compat::Appraiser::Utilities::"...
0x1800873eb  mov     [rsp+298h+var_278], rbx
0x1800873f0  lea     rdx, aOnecoreBaseApp_7; "onecore\\base\\appcompat\\appraiser\\he"...
0x1800873f7  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800873fc  xor     edx, edx; hFile
0x1800873fe  mov     rcx, rbx; lpLibFileName
0x180087401  lea     r8d, [rdx+22h]; dwFlags
0x180087405  call    cs:__imp_LoadLibraryExW
0x18008740b  mov     r15, rax
0x18008740e  test    rax, rax
0x180087411  jnz     short loc_18008744F
0x180087413  call    cs:__imp_GetLastError
0x180087419  mov     ebx, eax
0x18008741b  test    eax, eax
0x18008741d  jle     short loc_180087428
0x18008741f  movzx   ebx, ax
0x180087422  or      ebx, 80070000h
0x180087428  test    ebx, ebx
0x18008742a  mov     eax, 80004005h
0x18008742f  cmovns  ebx, eax
0x180087432  call    cs:__imp_GetLastError
0x180087438  mov     dword ptr [rsp+298h+var_268], eax
0x18008743c  mov     edx, 34Ah
0x180087441  lea     rax, aCouldNotOpenha; "Could not OpenHandle to resource: [%d]."
0x180087448  mov     ecx, edi
0x18008744a  jmp     loc_1800875B7
0x18008744f  xor     r9d, r9d; cchBufferMax
0x180087452  lea     r8, [rsp+298h+var_258]; lpBuffer
0x180087457  mov     edx, r12d; uID
0x18008745a  mov     rcx, r15; hInstance
0x18008745d  call    cs:__imp_LoadStringW
0x180087463  movsxd  r14, eax
0x180087466  test    eax, eax
0x180087468  jnz     short loc_1800874C7
0x18008746a  call    cs:__imp_GetLastError
0x180087470  mov     ebx, eax
0x180087472  test    eax, eax
0x180087474  jle     short loc_18008747F
0x180087476  movzx   ebx, ax
0x180087479  or      ebx, 80070000h
0x18008747f  test    ebx, ebx
0x180087481  mov     eax, 80004005h
0x180087486  cmovns  ebx, eax
0x180087489  call    cs:__imp_GetLastError
0x18008748f  mov     [rsp+298h+var_260], eax
0x180087493  mov     edx, 354h; bool
0x180087498  lea     rax, aCouldNotLoadRe; "Could not load resource with id %d: [%d"...
0x18008749f  mov     dword ptr [rsp+298h+var_268], r12d; char *
0x1800874a4  mov     qword ptr [rsp+298h+var_270], rax; int
0x1800874a9  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appcompat\\appraiser\\he"...
0x1800874b0  mov     dword ptr [rsp+298h+var_278], ebx; char *
0x1800874b4  lea     r9, aWindowsCompatA_370; "Windows::Compat::Appraiser::Utilities::"...
0x1800874bb  mov     ecx, edi; this
0x1800874bd  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800874c2  jmp     loc_18008756E
0x1800874c7  lea     eax, [r14+1]
0x1800874cb  movsxd  r12, eax
0x1800874ce  lea     rbx, [r12+r12]
0x1800874d2  call    cs:__imp_GetProcessHeap
0x1800874d8  mov     r8, rbx; dwBytes
0x1800874db  xor     edx, edx; dwFlags
0x1800874dd  mov     rcx, rax; hHeap
0x1800874e0  call    cs:__imp_HeapAlloc
0x1800874e6  mov     [r13+0], rax
0x1800874ea  test    rax, rax
0x1800874ed  jnz     short loc_1800874F6
0x1800874ef  mov     ebx, 8007000Eh
0x1800874f4  jmp     short loc_18008756E
0x1800874f6  mov     r8, qword ptr [rsp+298h+var_258]; unsigned __int16 *
0x1800874fb  mov     r9, r14; unsigned __int64
0x1800874fe  mov     rdx, r12; unsigned __int64
0x180087501  mov     rcx, rax; unsigned __int16 *
0x180087504  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180087509  mov     ebx, eax
0x18008750b  test    eax, eax
0x18008750d  jns     short loc_180087533
0x18008750f  mov     [rsp+298h+var_260], eax
0x180087513  lea     r9, aFailedToCopyTo; "Failed to copy to string %ls [0x%x]."
0x18008751a  mov     rax, qword ptr [rsp+298h+var_258]
0x18008751f  mov     edx, 35Bh
0x180087524  mov     [rsp+298h+var_268], rax
0x180087529  mov     qword ptr [rsp+298h+var_270], r9
0x18008752e  jmp     loc_1800874A9
0x180087533  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180087539  and     eax, edi
0x18008753b  test    al, al
0x18008753d  jz      short loc_18008756C
0x18008753f  mov     rax, qword ptr [rsp+298h+var_258]
0x180087544  lea     r9, aFailedToCopyTo; "Failed to copy to string %ls [0x%x]."
0x18008754b  mov     [rsp+298h+var_270], ebx
0x18008754f  lea     r8, aWindowsCompatA_370; "Windows::Compat::Appraiser::Utilities::"...
0x180087556  lea     rdx, aOnecoreBaseApp_7; "onecore\\base\\appcompat\\appraiser\\he"...
0x18008755d  mov     [rsp+298h+var_278], rax
0x180087562  mov     ecx, 35Bh; unsigned int
0x180087567  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18008756c  xor     ebx, ebx
0x18008756e  mov     rcx, r15; hLibModule
0x180087571  call    cs:__imp_FreeLibrary
0x180087577  test    ebx, ebx
0x180087579  jns     short loc_1800875F8
0x18008757b  jmp     short loc_1800875D3
0x18008757d  call    cs:__imp_GetLastError
0x180087583  mov     ebx, eax
0x180087585  test    eax, eax
0x180087587  jle     short loc_180087592
0x180087589  movzx   ebx, ax
0x18008758c  or      ebx, 80070000h
0x180087592  test    ebx, ebx
0x180087594  mov     eax, 80004005h
0x180087599  cmovns  ebx, eax
0x18008759c  call    cs:__imp_GetLastError
0x1800875a2  mov     dword ptr [rsp+298h+var_268], eax; char *
0x1800875a6  mov     edx, 33Eh; bool
0x1800875ab  lea     rax, aFailedToGetFul_0; "Failed to get full path from resource p"...
0x1800875b2  mov     ecx, 1; this
0x1800875b7  mov     qword ptr [rsp+298h+var_270], rax; int
0x1800875bc  lea     r9, aWindowsCompatA_370; "Windows::Compat::Appraiser::Utilities::"...
0x1800875c3  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appcompat\\appraiser\\he"...
0x1800875ca  mov     dword ptr [rsp+298h+var_278], ebx; char *
0x1800875ce  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800875d3  mov     rdi, [r13+0]
0x1800875d7  test    rdi, rdi
0x1800875da  jz      short loc_1800875F8
0x1800875dc  call    cs:__imp_GetProcessHeap
0x1800875e2  mov     r8, rdi; lpMem
0x1800875e5  xor     edx, edx; dwFlags
0x1800875e7  mov     rcx, rax; hHeap
0x1800875ea  call    cs:__imp_HeapFree
0x1800875f0  mov     qword ptr [r13+0], 0
0x1800875f8  mov     eax, ebx
0x1800875fa  mov     rcx, [rsp+298h+var_38]
0x180087602  xor     rcx, rsp; StackCookie
0x180087605  call    __security_check_cookie
0x18008760a  mov     rbx, [rsp+298h+arg_18]
0x180087612  add     rsp, 270h
0x180087619  pop     r15
0x18008761b  pop     r14
0x18008761d  pop     r13
0x18008761f  pop     r12
0x180087621  pop     rdi
0x180087622  retn
```
