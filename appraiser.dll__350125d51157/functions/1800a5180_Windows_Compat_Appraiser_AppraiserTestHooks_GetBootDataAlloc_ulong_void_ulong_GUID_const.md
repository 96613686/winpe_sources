# Windows::Compat::Appraiser::AppraiserTestHooks::GetBootDataAlloc(ulong,void * *,ulong *,_GUID const *)

- ea: `0x1800a5180`
- end: `0x1800a5479`
- name: `?GetBootDataAlloc@AppraiserTestHooks@Appraiser@Compat@Windows@@CAJKPEAPEAXPEAKPEBU_GUID@@@Z`
- size: `761`
- prototype: `__int64 __fastcall(unsigned int, void **, unsigned int *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800a5a3c`

## callees

- `0x18002ebb8`
- `0x1800301d0`
- `0x1800a5180`
- `0x18021f010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x1800a51c8`
- `KERNEL32!LoadLibraryExW` at `0x1800a51c8`
- `KERNEL32!FreeLibrary` at `0x1800a5447`
- `KERNEL32!FreeLibrary` at `0x1800a5447`
- `KERNEL32!GetProcessHeap` at `0x1800a53c5`
- `KERNEL32!GetProcessHeap` at `0x1800a5452`
- `KERNEL32!GetProcessHeap` at `0x1800a53c5`
- `KERNEL32!GetProcessHeap` at `0x1800a5452`
- `KERNEL32!GetProcAddress` at `0x1800a51f5`
- `KERNEL32!GetProcAddress` at `0x1800a5208`
- `KERNEL32!GetProcAddress` at `0x1800a521b`
- `KERNEL32!GetProcAddress` at `0x1800a522e`
- `KERNEL32!GetProcAddress` at `0x1800a5241`
- `KERNEL32!GetProcAddress` at `0x1800a51f5`
- `KERNEL32!GetProcAddress` at `0x1800a5208`
- `KERNEL32!GetProcAddress` at `0x1800a521b`
- `KERNEL32!GetProcAddress` at `0x1800a522e`
- `KERNEL32!GetProcAddress` at `0x1800a5241`
- `KERNEL32!HeapAlloc` at `0x1800a53d6`
- `KERNEL32!HeapAlloc` at `0x1800a53d6`
- `KERNEL32!HeapFree` at `0x1800a5460`
- `KERNEL32!HeapFree` at `0x1800a5460`

## string_xrefs

- `0x1800a5285`: `onecore\base\appcompat\appraiser\helpers\appraisertesthooks.cpp`
- `0x1800a52e8`: `onecore\base\appcompat\appraiser\helpers\appraisertesthooks.cpp`
- `0x1800a532f`: `onecore\base\appcompat\appraiser\helpers\appraisertesthooks.cpp`
- `0x1800a5391`: `onecore\base\appcompat\appraiser\helpers\appraisertesthooks.cpp`
- `0x1800a51d8`: `bcd.dll binary not exist, using statically linked BCD functions`
- `0x1800a51a3`: `bcd.dll`
- `0x1800a51fb`: `BcdOpenObject`
- `0x1800a51eb`: `BcdOpenStore`
- `0x1800a5279`: `Windows::Compat::Appraiser::AppraiserTestHooks::GetBootDataAlloc`
- `0x1800a52f9`: `Windows::Compat::Appraiser::AppraiserTestHooks::GetBootDataAlloc`
- `0x1800a5323`: `Windows::Compat::Appraiser::AppraiserTestHooks::GetBootDataAlloc`
- `0x1800a5385`: `Windows::Compat::Appraiser::AppraiserTestHooks::GetBootDataAlloc`
- `0x1800a52d8`: `Failed to open System Store: [0x%x]`
- `0x1800a5318`: `Failed to open System Store: [0x%x]`
- `0x1800a5266`: `Missing BCD functions in bcd.dll, using statically linked BCD functions`
- `0x1800a535f`: `Failed to open Boot Manager Object: [0x%x]`
- `0x1800a537a`: `Failed to open Boot Manager Object: [0x%x]`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Appraiser::AppraiserTestHooks::GetBootDataAlloc(
        __int64 a1,
        void **a2,
        unsigned int *a3,
        const struct _GUID *a4)
{
  void *v5; // rdi
  HMODULE Library; // rax
  HMODULE v7; // rsi
  const char *v8; // r10
  char v9; // dl
  FARPROC ProcAddress; // rbx
  FARPROC v11; // r15
  FARPROC v12; // r14
  void (*v13)(void); // r12
  FARPROC v14; // rax
  int v15; // eax
  unsigned int v16; // ebx
  const char *v17; // r9
  char v18; // dl
  int v19; // eax
  unsigned int v20; // ebx
  HANDLE ProcessHeap; // rax
  LPVOID v22; // rax
  int v23; // eax
  HANDLE v24; // rax
  char *v26; // [rsp+20h] [rbp-38h]
  char *v27; // [rsp+30h] [rbp-28h]
  void (*v28)(void); // [rsp+40h] [rbp-18h]
  SIZE_T dwBytes; // [rsp+A0h] [rbp+48h] BYREF
  void **v30; // [rsp+A8h] [rbp+50h]
  __int64 v31; // [rsp+B0h] [rbp+58h] BYREF
  __int64 v32; // [rsp+B8h] [rbp+60h] BYREF

  v30 = a2;
  *a3 = 0;
  *a2 = 0;
  v31 = 0;
  v32 = 0;
  v5 = 0;
  LODWORD(dwBytes) = 0;
  Library = LoadLibraryExW(L"bcd.dll", 0, 0x800u);
  v7 = Library;
  if ( !Library )
  {
    v8 = "bcd.dll binary not exist, using statically linked BCD functions";
    v9 = 113;
LABEL_9:
    Windows::Compat::Appraiser::WriteLog(
      0,
      v9,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\appraisertesthooks.cpp",
      "Windows::Compat::Appraiser::AppraiserTestHooks::GetBootDataAlloc",
      0,
      (int)v8,
      v27);
    v28 = (void (*)(void))BcdCloseStore;
    ProcAddress = BcdOpenStore;
    v11 = BcdOpenObject;
    v12 = BcdGetElementData;
    v13 = (void (*)(void))BcdCloseObject;
    goto LABEL_10;
  }
  ProcAddress = GetProcAddress(Library, "BcdOpenStore");
  v11 = GetProcAddress(v7, "BcdOpenObject");
  v12 = GetProcAddress(v7, "BcdGetElementData");
  v13 = (void (*)(void))GetProcAddress(v7, "BcdCloseObject");
  v14 = GetProcAddress(v7, "BcdCloseStore");
  v28 = (void (*)(void))v14;
  if ( !ProcAddress || !v11 || !v12 || !v13 || !v14 )
  {
    v8 = "Missing BCD functions in bcd.dll, using statically linked BCD functions";
    v9 = -125;
    goto LABEL_9;
  }
LABEL_10:
  v15 = ((__int64 (__fastcall *)(_QWORD, __int64, __int64 *))ProcAddress)(0, 2, &v31);
  v16 = v15 | 0x10000000;
  if ( v15 < 0 )
  {
    v17 = "Failed to open System Store: [0x%x]";
    v18 = -109;
LABEL_12:
    LODWORD(v27) = v16;
    LODWORD(v26) = v16;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      v18,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\appraisertesthooks.cpp",
      "Windows::Compat::Appraiser::AppraiserTestHooks::GetBootDataAlloc",
      v26,
      (int)v17,
      v27);
    goto LABEL_24;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x193u,
      "onecore\\base\\appcompat\\appraiser\\helpers\\appraisertesthooks.cpp",
      "Windows::Compat::Appraiser::AppraiserTestHooks::GetBootDataAlloc",
      "Failed to open System Store: [0x%x]",
      v16);
  v19 = ((__int64 (__fastcall *)(__int64, GUID *, __int64 *))v11)(v31, &GUID_WINDOWS_BOOTMGR, &v32);
  v16 = v19 | 0x10000000;
  if ( v19 < 0 )
  {
    v17 = "Failed to open Boot Manager Object: [0x%x]";
    v18 = -106;
    goto LABEL_12;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x196u,
      "onecore\\base\\appcompat\\appraiser\\helpers\\appraisertesthooks.cpp",
      "Windows::Compat::Appraiser::AppraiserTestHooks::GetBootDataAlloc",
      "Failed to open Boot Manager Object: [0x%x]",
      v16);
  v16 = ((__int64 (__fastcall *)(__int64, __int64, _QWORD, SIZE_T *))v12)(v32, 369098825, 0, &dwBytes) | 0x10000000;
  if ( v16 == -805306333 )
  {
    v20 = dwBytes;
    ProcessHeap = GetProcessHeap();
    v22 = HeapAlloc(ProcessHeap, 8u, v20);
    v5 = v22;
    if ( v22 )
    {
      v23 = ((__int64 (__fastcall *)(__int64, __int64, LPVOID, SIZE_T *))v12)(v32, 369098825, v22, &dwBytes);
      v16 = v23 | 0x10000000;
      if ( v23 >= 0 )
      {
        *v30 = v5;
        v5 = 0;
        v16 = 0;
        *a3 = dwBytes;
      }
    }
    else
    {
      v16 = -2147024882;
    }
  }
LABEL_24:
  if ( v32 )
    v13();
  if ( v31 )
    v28();
  if ( v7 )
    FreeLibrary(v7);
  if ( v5 )
  {
    v24 = GetProcessHeap();
    HeapFree(v24, 0, v5);
  }
  return v16;
}

```

## disassembly

```asm
0x1800a5180  mov     [rsp-40h+arg_18], r9
0x1800a5185  mov     [rsp-40h+arg_8], rdx
0x1800a518a  mov     dword ptr [rsp-40h+dwBytes], ecx
0x1800a518e  push    rbp
0x1800a518f  push    rbx
0x1800a5190  push    rsi
0x1800a5191  push    rdi
0x1800a5192  push    r12
0x1800a5194  push    r13
0x1800a5196  push    r14
0x1800a5198  push    r15
0x1800a519a  mov     rbp, rsp
0x1800a519d  sub     rsp, 58h
0x1800a51a1  xor     ebx, ebx
0x1800a51a3  lea     rcx, aBcdDll; "bcd.dll"
0x1800a51aa  mov     [r8], ebx
0x1800a51ad  mov     r13, r8
0x1800a51b0  mov     [rdx], rbx
0x1800a51b3  mov     r8d, 800h; dwFlags
0x1800a51b9  xor     edx, edx; hFile
0x1800a51bb  mov     [rbp+arg_10], rbx
0x1800a51bf  mov     [rbp+arg_18], rbx
0x1800a51c3  mov     edi, ebx
0x1800a51c5  mov     dword ptr [rbp+dwBytes], ebx
0x1800a51c8  call    cs:__imp_LoadLibraryExW
0x1800a51ce  mov     rsi, rax
0x1800a51d1  test    rax, rax
0x1800a51d4  jnz     short loc_1800A51EB
0x1800a51d6  mov     al, bl
0x1800a51d8  lea     r10, aBcdDllBinaryNo; "bcd.dll binary not exist, using statica"...
0x1800a51df  mov     edx, 171h
0x1800a51e4  mov     ecx, ebx
0x1800a51e6  jmp     loc_1800A5274
0x1800a51eb  lea     rdx, aBcdopenstore; "BcdOpenStore"
0x1800a51f2  mov     rcx, rsi; hModule
0x1800a51f5  call    cs:__imp_GetProcAddress
0x1800a51fb  lea     rdx, aBcdopenobject; "BcdOpenObject"
0x1800a5202  mov     rcx, rsi; hModule
0x1800a5205  mov     rbx, rax
0x1800a5208  call    cs:__imp_GetProcAddress
0x1800a520e  lea     rdx, aBcdgetelementd; "BcdGetElementData"
0x1800a5215  mov     rcx, rsi; hModule
0x1800a5218  mov     r15, rax
0x1800a521b  call    cs:__imp_GetProcAddress
0x1800a5221  lea     rdx, aBcdcloseobject; "BcdCloseObject"
0x1800a5228  mov     rcx, rsi; hModule
0x1800a522b  mov     r14, rax
0x1800a522e  call    cs:__imp_GetProcAddress
0x1800a5234  lea     rdx, aBcdclosestore; "BcdCloseStore"
0x1800a523b  mov     rcx, rsi; hModule
0x1800a523e  mov     r12, rax
0x1800a5241  call    cs:__imp_GetProcAddress
0x1800a5247  mov     [rbp+var_18], rax
0x1800a524b  test    rbx, rbx
0x1800a524e  jz      short loc_1800A5264
0x1800a5250  test    r15, r15
0x1800a5253  jz      short loc_1800A5264
0x1800a5255  test    r14, r14
0x1800a5258  jz      short loc_1800A5264
0x1800a525a  test    r12, r12
0x1800a525d  jz      short loc_1800A5264
0x1800a525f  test    rax, rax
0x1800a5262  jnz     short loc_1800A52BB
0x1800a5264  xor     al, al
0x1800a5266  lea     r10, aMissingBcdFunc; "Missing BCD functions in bcd.dll, using"...
0x1800a526d  xor     ecx, ecx
0x1800a526f  mov     edx, 183h; bool
0x1800a5274  mov     qword ptr [rsp+58h+var_30], r10; int
0x1800a5279  lea     r9, aWindowsCompatA_543; "Windows::Compat::Appraiser::AppraiserTe"...
0x1800a5280  mov     [rsp+58h+var_38], rcx; char *
0x1800a5285  lea     r8, aOnecoreBaseApp_49; "onecore\\base\\appcompat\\appraiser\\he"...
0x1800a528c  movzx   ecx, al; this
0x1800a528f  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800a5294  lea     rax, BcdCloseStore
0x1800a529b  mov     [rbp+var_18], rax
0x1800a529f  lea     rbx, BcdOpenStore
0x1800a52a6  lea     r15, BcdOpenObject
0x1800a52ad  lea     r14, BcdGetElementData
0x1800a52b4  lea     r12, BcdCloseObject
0x1800a52bb  lea     r8, [rbp+arg_10]
0x1800a52bf  mov     edx, 2
0x1800a52c4  xor     ecx, ecx
0x1800a52c6  mov     rax, rbx
0x1800a52c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a52ce  mov     ebx, eax
0x1800a52d0  or      ebx, 10000000h
0x1800a52d6  jge     short loc_1800A530E
0x1800a52d8  lea     r9, aFailedToOpenSy_0; "Failed to open System Store: [0x%x]"
0x1800a52df  mov     edx, 193h; bool
0x1800a52e4  mov     dword ptr [rsp+58h+var_28], ebx; char *
0x1800a52e8  lea     r8, aOnecoreBaseApp_49; "onecore\\base\\appcompat\\appraiser\\he"...
0x1800a52ef  mov     qword ptr [rsp+58h+var_30], r9; int
0x1800a52f4  mov     ecx, 1; this
0x1800a52f9  lea     r9, aWindowsCompatA_543; "Windows::Compat::Appraiser::AppraiserTe"...
0x1800a5300  mov     dword ptr [rsp+58h+var_38], ebx; char *
0x1800a5304  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800a5309  jmp     loc_1800A541C
0x1800a530e  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800a5314  test    al, 1
0x1800a5316  jz      short loc_1800A533B
0x1800a5318  lea     r9, aFailedToOpenSy_0; "Failed to open System Store: [0x%x]"
0x1800a531f  mov     dword ptr [rsp+58h+var_38], ebx
0x1800a5323  lea     r8, aWindowsCompatA_543; "Windows::Compat::Appraiser::AppraiserTe"...
0x1800a532a  mov     ecx, 193h; unsigned int
0x1800a532f  lea     rdx, aOnecoreBaseApp_49; "onecore\\base\\appcompat\\appraiser\\he"...
0x1800a5336  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800a533b  mov     rcx, [rbp+arg_10]
0x1800a533f  lea     r8, [rbp+arg_18]
0x1800a5343  lea     rdx, GUID_WINDOWS_BOOTMGR
0x1800a534a  mov     rax, r15
0x1800a534d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5352  mov     ebx, eax
0x1800a5354  mov     r15d, 10000000h
0x1800a535a  or      ebx, r15d
0x1800a535d  jge     short loc_1800A5370
0x1800a535f  lea     r9, aFailedToOpenBo; "Failed to open Boot Manager Object: [0x"...
0x1800a5366  mov     edx, 196h
0x1800a536b  jmp     loc_1800A52E4
0x1800a5370  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800a5376  test    al, 1
0x1800a5378  jz      short loc_1800A539D
0x1800a537a  lea     r9, aFailedToOpenBo; "Failed to open Boot Manager Object: [0x"...
0x1800a5381  mov     dword ptr [rsp+58h+var_38], ebx
0x1800a5385  lea     r8, aWindowsCompatA_543; "Windows::Compat::Appraiser::AppraiserTe"...
0x1800a538c  mov     ecx, 196h; unsigned int
0x1800a5391  lea     rdx, aOnecoreBaseApp_49; "onecore\\base\\appcompat\\appraiser\\he"...
0x1800a5398  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800a539d  mov     rcx, [rbp+arg_18]
0x1800a53a1  lea     r9, [rbp+dwBytes]
0x1800a53a5  xor     r8d, r8d
0x1800a53a8  mov     edx, 16000049h
0x1800a53ad  mov     rax, r14
0x1800a53b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a53b5  mov     ebx, eax
0x1800a53b7  or      ebx, r15d
0x1800a53ba  cmp     ebx, 0D0000023h
0x1800a53c0  jnz     short loc_1800A541C
0x1800a53c2  mov     ebx, dword ptr [rbp+dwBytes]
0x1800a53c5  call    cs:__imp_GetProcessHeap
0x1800a53cb  mov     r8d, ebx; dwBytes
0x1800a53ce  mov     edx, 8; dwFlags
0x1800a53d3  mov     rcx, rax; hHeap
0x1800a53d6  call    cs:__imp_HeapAlloc
0x1800a53dc  mov     rdi, rax
0x1800a53df  test    rax, rax
0x1800a53e2  jnz     short loc_1800A53EB
0x1800a53e4  mov     ebx, 8007000Eh
0x1800a53e9  jmp     short loc_1800A541C
0x1800a53eb  mov     rcx, [rbp+arg_18]
0x1800a53ef  lea     r9, [rbp+dwBytes]
0x1800a53f3  mov     r8, rdi
0x1800a53f6  mov     edx, 16000049h
0x1800a53fb  mov     rax, r14
0x1800a53fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5403  mov     ebx, eax
0x1800a5405  or      ebx, r15d
0x1800a5408  jl      short loc_1800A541C
0x1800a540a  mov     rax, [rbp+arg_8]
0x1800a540e  mov     [rax], rdi
0x1800a5411  xor     edi, edi
0x1800a5413  mov     eax, dword ptr [rbp+dwBytes]
0x1800a5416  xor     ebx, ebx
0x1800a5418  mov     [r13+0], eax
0x1800a541c  mov     rcx, [rbp+arg_18]
0x1800a5420  test    rcx, rcx
0x1800a5423  jz      short loc_1800A542D
0x1800a5425  mov     rax, r12
0x1800a5428  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a542d  mov     rcx, [rbp+arg_10]
0x1800a5431  test    rcx, rcx
0x1800a5434  jz      short loc_1800A543F
0x1800a5436  mov     rax, [rbp+var_18]
0x1800a543a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a543f  test    rsi, rsi
0x1800a5442  jz      short loc_1800A544D
0x1800a5444  mov     rcx, rsi; hLibModule
0x1800a5447  call    cs:__imp_FreeLibrary
0x1800a544d  test    rdi, rdi
0x1800a5450  jz      short loc_1800A5466
0x1800a5452  call    cs:__imp_GetProcessHeap
0x1800a5458  mov     r8, rdi; lpMem
0x1800a545b  xor     edx, edx; dwFlags
0x1800a545d  mov     rcx, rax; hHeap
0x1800a5460  call    cs:__imp_HeapFree
0x1800a5466  mov     eax, ebx
0x1800a5468  add     rsp, 58h
0x1800a546c  pop     r15
0x1800a546e  pop     r14
0x1800a5470  pop     r13
0x1800a5472  pop     r12
0x1800a5474  pop     rdi
0x1800a5475  pop     rsi
0x1800a5476  pop     rbx
0x1800a5477  pop     rbp
0x1800a5478  retn
```
