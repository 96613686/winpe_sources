# WaasMedic::CbsUtil::FodEnumerationCheck(void)

- ea: `0x18006a240`
- end: `0x18006a536`
- name: `?FodEnumerationCheck@CbsUtil@WaasMedic@@CAJXZ`
- size: `758`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180061790`

## callees

- `0x18000bbb4`
- `0x18000bbd4`
- `0x18006a150`
- `0x18006a240`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006a2ee`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006a378`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006a406`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006a495`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006a2ee`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006a378`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006a406`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006a495`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006a2a3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006a523`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006a2a3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006a523`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18006a274`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18006a274`

## string_xrefs

- `0x18006a26d`: `dismapi.dll`
- `0x18006a36d`: `DismOpenSession`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 WaasMedic::CbsUtil::FodEnumerationCheck(void)
{
  HMODULE Library; // rax
  const char *v1; // r9
  unsigned int LastError; // ebx
  FARPROC ProcAddress; // rax
  int v5; // eax
  FARPROC v6; // rax
  const char *v7; // r9
  int v8; // eax
  FARPROC v9; // rax
  const char *v10; // r9
  int v11; // eax
  FARPROC v12; // rax
  const char *v13; // r9
  int v14; // eax
  int v15; // [rsp+20h] [rbp-29h]
  int v16; // [rsp+30h] [rbp-19h] BYREF
  HMODULE hLibModule; // [rsp+38h] [rbp-11h] BYREF
  __int64 v18; // [rsp+40h] [rbp-9h] BYREF
  __int64 v19; // [rsp+48h] [rbp-1h] BYREF
  _QWORD v20[6]; // [rsp+50h] [rbp+7h] BYREF
  char v21; // [rsp+80h] [rbp+37h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]
  char v23; // [rsp+B0h] [rbp+67h] BYREF
  char v24; // [rsp+B8h] [rbp+6Fh] BYREF
  unsigned int v25; // [rsp+C0h] [rbp+77h] BYREF
  int v26; // [rsp+C8h] [rbp+7Fh] BYREF

  v25 = 0;
  v18 = 0;
  v19 = 0;
  v23 = 0;
  v24 = 0;
  Library = LoadLibraryExW(L"dismapi.dll", 0, 0x800u);
  hLibModule = Library;
  if ( !Library )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xF9,
                  (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\cbsutil.cpp",
                  v1);
LABEL_3:
    if ( hLibModule )
      FreeLibrary(hLibModule);
    return LastError;
  }
  v20[0] = &v24;
  v20[1] = &hLibModule;
  v20[2] = &v18;
  v20[3] = &v19;
  v20[4] = &v25;
  v20[5] = &v23;
  v21 = 1;
  ProcAddress = GetProcAddress(Library, "DismInitialize");
  if ( !ProcAddress )
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11D,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\cbsutil.cpp",
      (const char *)0x8007000ELL,
      v15);
    v21 = 0;
    lambda_99c085c1750c74f319cfea667be7654b_::operator()(v20);
    goto LABEL_3;
  }
  v5 = ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD))ProcAddress)(1, 0, 0);
  LastError = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11E,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\cbsutil.cpp",
      (const char *)(unsigned int)v5,
      v15);
    v21 = 0;
    lambda_99c085c1750c74f319cfea667be7654b_::operator()(v20);
    goto LABEL_3;
  }
  v23 = 1;
  v6 = GetProcAddress(hLibModule, "DismOpenSession");
  if ( !v6 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x122,
                  (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\cbsutil.cpp",
                  v7);
    v21 = 0;
    lambda_99c085c1750c74f319cfea667be7654b_::operator()(v20);
    goto LABEL_3;
  }
  v8 = ((__int64 (__fastcall *)(const wchar_t *, _QWORD, _QWORD, unsigned int *))v6)(
         L"DISM_{53BFAE52-B167-4E2F-A258-0A37B57FF845}",
         0,
         0,
         &v25);
  LastError = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x123,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\cbsutil.cpp",
      (const char *)(unsigned int)v8,
      v15);
    v21 = 0;
    lambda_99c085c1750c74f319cfea667be7654b_::operator()(v20);
    goto LABEL_3;
  }
  v24 = 1;
  v26 = 0;
  v9 = GetProcAddress(hLibModule, "DismGetFeatures");
  if ( !v9 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x128,
                  (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\cbsutil.cpp",
                  v10);
    v21 = 0;
    lambda_99c085c1750c74f319cfea667be7654b_::operator()(v20);
    goto LABEL_3;
  }
  v11 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, __int64 *))v9)(v25, 0, 0, &v18);
  LastError = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x129,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\cbsutil.cpp",
      (const char *)(unsigned int)v11,
      (int)&v26);
    v21 = 0;
    lambda_99c085c1750c74f319cfea667be7654b_::operator()(v20);
    goto LABEL_3;
  }
  v16 = 0;
  v12 = GetProcAddress(hLibModule, "DismGetCapabilities");
  if ( !v12 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x12D,
                  (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\cbsutil.cpp",
                  v13);
    v21 = 0;
    lambda_99c085c1750c74f319cfea667be7654b_::operator()(v20);
    goto LABEL_3;
  }
  v14 = ((__int64 (__fastcall *)(_QWORD, __int64 *, int *))v12)(v25, &v19, &v16);
  LastError = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12E,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\cbsutil.cpp",
      (const char *)(unsigned int)v14,
      (int)&v26);
    v21 = 0;
    lambda_99c085c1750c74f319cfea667be7654b_::operator()(v20);
    goto LABEL_3;
  }
  v21 = 0;
  lambda_99c085c1750c74f319cfea667be7654b_::operator()(v20);
  if ( hLibModule )
    FreeLibrary(hLibModule);
  return 0;
}

```

## disassembly

```asm
0x18006a240  push    rbp
0x18006a242  push    rbx
0x18006a243  push    rdi
0x18006a244  lea     rbp, [rsp-47h]
0x18006a249  sub     rsp, 90h
0x18006a250  xor     edi, edi
0x18006a252  mov     [rbp+57h+arg_10], edi
0x18006a255  mov     [rbp+57h+var_60], rdi
0x18006a259  mov     [rbp+57h+var_58], rdi
0x18006a25d  mov     [rbp+57h+arg_0], dil
0x18006a261  mov     [rbp+57h+arg_8], dil
0x18006a265  xor     edx, edx; hFile
0x18006a267  mov     r8d, 800h; dwFlags
0x18006a26d  lea     rcx, aDismapiDll; "dismapi.dll"
0x18006a274  call    cs:__imp_LoadLibraryExW
0x18006a27a  mov     [rbp+57h+hLibModule], rax
0x18006a27e  test    rax, rax
0x18006a281  jnz     short loc_18006A2B0
0x18006a283  mov     rcx, [rbp+5Fh]; this
0x18006a287  lea     r8, aOnecoreEnduser_11; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18006a28e  mov     edx, 0F9h; void *
0x18006a293  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18006a298  mov     ebx, eax
0x18006a29a  mov     rcx, [rbp+57h+hLibModule]; hLibModule
0x18006a29e  test    rcx, rcx
0x18006a2a1  jz      short loc_18006A2A9
0x18006a2a3  call    cs:__imp_FreeLibrary
0x18006a2a9  mov     eax, ebx
0x18006a2ab  jmp     loc_18006A52B
0x18006a2b0  lea     rcx, [rbp+57h+arg_8]
0x18006a2b4  mov     [rbp+57h+var_50], rcx
0x18006a2b8  lea     rcx, [rbp+57h+hLibModule]
0x18006a2bc  mov     [rbp+57h+var_48], rcx
0x18006a2c0  lea     rcx, [rbp+57h+var_60]
0x18006a2c4  mov     [rbp+57h+var_40], rcx
0x18006a2c8  lea     rcx, [rbp+57h+var_58]
0x18006a2cc  mov     [rbp+57h+var_38], rcx
0x18006a2d0  lea     rcx, [rbp+57h+arg_10]
0x18006a2d4  mov     [rbp+57h+var_30], rcx
0x18006a2d8  lea     rcx, [rbp+57h+arg_0]
0x18006a2dc  mov     [rbp+57h+var_28], rcx
0x18006a2e0  mov     [rbp+57h+var_20], 1
0x18006a2e4  lea     rdx, aDisminitialize; "DismInitialize"
0x18006a2eb  mov     rcx, rax; hModule
0x18006a2ee  call    cs:__imp_GetProcAddress
0x18006a2f4  test    rax, rax
0x18006a2f7  jnz     short loc_18006A32A
0x18006a2f9  mov     rcx, [rbp+5Fh]; this
0x18006a2fd  mov     ebx, 8007000Eh
0x18006a302  mov     r9d, ebx; char *
0x18006a305  lea     r8, aOnecoreEnduser_11; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18006a30c  mov     edx, 11Dh; void *
0x18006a311  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006a316  nop
0x18006a317  mov     [rbp+57h+var_20], dil
0x18006a31b  lea     rcx, [rbp+57h+var_50]
0x18006a31f  call    _lambda_99c085c1750c74f319cfea667be7654b___operator__
0x18006a324  nop
0x18006a325  jmp     loc_18006A29A
0x18006a32a  xor     r8d, r8d
0x18006a32d  xor     edx, edx
0x18006a32f  lea     ecx, [rdx+1]
0x18006a332  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a337  mov     ebx, eax
0x18006a339  test    eax, eax
0x18006a33b  jns     short loc_18006A369
0x18006a33d  mov     rcx, [rbp+5Fh]; this
0x18006a341  mov     r9d, eax; char *
0x18006a344  lea     r8, aOnecoreEnduser_11; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18006a34b  mov     edx, 11Eh; void *
0x18006a350  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006a355  nop
0x18006a356  mov     [rbp+57h+var_20], dil
0x18006a35a  lea     rcx, [rbp+57h+var_50]
0x18006a35e  call    _lambda_99c085c1750c74f319cfea667be7654b___operator__
0x18006a363  nop
0x18006a364  jmp     loc_18006A29A
0x18006a369  mov     [rbp+57h+arg_0], 1
0x18006a36d  lea     rdx, aDismopensessio; "DismOpenSession"
0x18006a374  mov     rcx, [rbp+57h+hLibModule]; hModule
0x18006a378  call    cs:__imp_GetProcAddress
0x18006a37e  test    rax, rax
0x18006a381  jnz     short loc_18006A3AD
0x18006a383  mov     rcx, [rbp+5Fh]; this
0x18006a387  lea     r8, aOnecoreEnduser_11; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18006a38e  mov     edx, 122h; void *
0x18006a393  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18006a398  mov     ebx, eax
0x18006a39a  mov     [rbp+57h+var_20], dil
0x18006a39e  lea     rcx, [rbp+57h+var_50]
0x18006a3a2  call    _lambda_99c085c1750c74f319cfea667be7654b___operator__
0x18006a3a7  nop
0x18006a3a8  jmp     loc_18006A29A
0x18006a3ad  lea     r9, [rbp+57h+arg_10]
0x18006a3b1  xor     r8d, r8d
0x18006a3b4  xor     edx, edx
0x18006a3b6  lea     rcx, aDism53bfae52B1; "DISM_{53BFAE52-B167-4E2F-A258-0A37B57FF"...
0x18006a3bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a3c2  mov     ebx, eax
0x18006a3c4  test    eax, eax
0x18006a3c6  jns     short loc_18006A3F4
0x18006a3c8  mov     rcx, [rbp+5Fh]; this
0x18006a3cc  mov     r9d, eax; char *
0x18006a3cf  lea     r8, aOnecoreEnduser_11; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18006a3d6  mov     edx, 123h; void *
0x18006a3db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006a3e0  nop
0x18006a3e1  mov     [rbp+57h+var_20], dil
0x18006a3e5  lea     rcx, [rbp+57h+var_50]
0x18006a3e9  call    _lambda_99c085c1750c74f319cfea667be7654b___operator__
0x18006a3ee  nop
0x18006a3ef  jmp     loc_18006A29A
0x18006a3f4  mov     [rbp+57h+arg_8], 1
0x18006a3f8  mov     [rbp+57h+arg_18], edi
0x18006a3fb  lea     rdx, aDismgetfeature; "DismGetFeatures"
0x18006a402  mov     rcx, [rbp+57h+hLibModule]; hModule
0x18006a406  call    cs:__imp_GetProcAddress
0x18006a40c  test    rax, rax
0x18006a40f  jnz     short loc_18006A43B
0x18006a411  mov     rcx, [rbp+5Fh]; this
0x18006a415  lea     r8, aOnecoreEnduser_11; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18006a41c  mov     edx, 128h; void *
0x18006a421  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18006a426  mov     ebx, eax
0x18006a428  mov     [rbp+57h+var_20], dil
0x18006a42c  lea     rcx, [rbp+57h+var_50]
0x18006a430  call    _lambda_99c085c1750c74f319cfea667be7654b___operator__
0x18006a435  nop
0x18006a436  jmp     loc_18006A29A
0x18006a43b  lea     rcx, [rbp+57h+arg_18]
0x18006a43f  mov     qword ptr [rsp+0A0h+var_80], rcx; int
0x18006a444  lea     r9, [rbp+57h+var_60]
0x18006a448  xor     r8d, r8d
0x18006a44b  xor     edx, edx
0x18006a44d  mov     ecx, [rbp+57h+arg_10]
0x18006a450  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a455  mov     ebx, eax
0x18006a457  test    eax, eax
0x18006a459  jns     short loc_18006A487
0x18006a45b  mov     rcx, [rbp+5Fh]; this
0x18006a45f  mov     r9d, eax; char *
0x18006a462  lea     r8, aOnecoreEnduser_11; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18006a469  mov     edx, 129h; void *
0x18006a46e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006a473  nop
0x18006a474  mov     [rbp+57h+var_20], dil
0x18006a478  lea     rcx, [rbp+57h+var_50]
0x18006a47c  call    _lambda_99c085c1750c74f319cfea667be7654b___operator__
0x18006a481  nop
0x18006a482  jmp     loc_18006A29A
0x18006a487  mov     [rbp+57h+var_70], edi
0x18006a48a  lea     rdx, aDismgetcapabil; "DismGetCapabilities"
0x18006a491  mov     rcx, [rbp+57h+hLibModule]; hModule
0x18006a495  call    cs:__imp_GetProcAddress
0x18006a49b  test    rax, rax
0x18006a49e  jnz     short loc_18006A4CA
0x18006a4a0  mov     rcx, [rbp+5Fh]; this
0x18006a4a4  lea     r8, aOnecoreEnduser_11; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18006a4ab  mov     edx, 12Dh; void *
0x18006a4b0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18006a4b5  mov     ebx, eax
0x18006a4b7  mov     [rbp+57h+var_20], dil
0x18006a4bb  lea     rcx, [rbp+57h+var_50]
0x18006a4bf  call    _lambda_99c085c1750c74f319cfea667be7654b___operator__
0x18006a4c4  nop
0x18006a4c5  jmp     loc_18006A29A
0x18006a4ca  lea     r8, [rbp+57h+var_70]
0x18006a4ce  lea     rdx, [rbp+57h+var_58]
0x18006a4d2  mov     ecx, [rbp+57h+arg_10]
0x18006a4d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a4da  mov     ebx, eax
0x18006a4dc  test    eax, eax
0x18006a4de  jns     short loc_18006A50C
0x18006a4e0  mov     rcx, [rbp+5Fh]; this
0x18006a4e4  mov     r9d, eax; char *
0x18006a4e7  lea     r8, aOnecoreEnduser_11; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18006a4ee  mov     edx, 12Eh; void *
0x18006a4f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006a4f8  nop
0x18006a4f9  mov     [rbp+57h+var_20], dil
0x18006a4fd  lea     rcx, [rbp+57h+var_50]
0x18006a501  call    _lambda_99c085c1750c74f319cfea667be7654b___operator__
0x18006a506  nop
0x18006a507  jmp     loc_18006A29A
0x18006a50c  mov     [rbp+57h+var_20], dil
0x18006a510  lea     rcx, [rbp+57h+var_50]
0x18006a514  call    _lambda_99c085c1750c74f319cfea667be7654b___operator__
0x18006a519  nop
0x18006a51a  mov     rcx, [rbp+57h+hLibModule]; hLibModule
0x18006a51e  test    rcx, rcx
0x18006a521  jz      short loc_18006A529
0x18006a523  call    cs:__imp_FreeLibrary
0x18006a529  xor     eax, eax
0x18006a52b  add     rsp, 90h
0x18006a532  pop     rdi
0x18006a533  pop     rbx
0x18006a534  pop     rbp
0x18006a535  retn
```
