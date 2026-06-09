# WaasMedic::CbsUtil::FodEnumerationCheck(void)

- ea: `0x180058c50`
- end: `0x180058f46`
- name: `?FodEnumerationCheck@CbsUtil@WaasMedic@@CAJXZ`
- size: `758`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18004fa50`

## callees

- `0x180009a34`
- `0x180009a54`
- `0x180058b60`
- `0x180058c50`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180058cfe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180058d88`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180058e16`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180058ea5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180058cfe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180058d88`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180058e16`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180058ea5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180058c84`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180058c84`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180058cb3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180058f33`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180058cb3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180058f33`

## string_xrefs

- `0x180058d7d`: `DismOpenSession`
- `0x180058c7d`: `dismapi.dll`

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
0x180058c50  push    rbp
0x180058c52  push    rbx
0x180058c53  push    rdi
0x180058c54  lea     rbp, [rsp-47h]
0x180058c59  sub     rsp, 90h
0x180058c60  xor     edi, edi
0x180058c62  mov     [rbp+57h+arg_10], edi
0x180058c65  mov     [rbp+57h+var_60], rdi
0x180058c69  mov     [rbp+57h+var_58], rdi
0x180058c6d  mov     [rbp+57h+arg_0], dil
0x180058c71  mov     [rbp+57h+arg_8], dil
0x180058c75  xor     edx, edx; hFile
0x180058c77  mov     r8d, 800h; dwFlags
0x180058c7d  lea     rcx, aDismapiDll; "dismapi.dll"
0x180058c84  call    cs:__imp_LoadLibraryExW
0x180058c8a  mov     [rbp+57h+hLibModule], rax
0x180058c8e  test    rax, rax
0x180058c91  jnz     short loc_180058CC0
0x180058c93  mov     rcx, [rbp+5Fh]; this
0x180058c97  lea     r8, aOnecoreEnduser_21; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180058c9e  mov     edx, 0F9h; void *
0x180058ca3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180058ca8  mov     ebx, eax
0x180058caa  mov     rcx, [rbp+57h+hLibModule]; hLibModule
0x180058cae  test    rcx, rcx
0x180058cb1  jz      short loc_180058CB9
0x180058cb3  call    cs:__imp_FreeLibrary
0x180058cb9  mov     eax, ebx
0x180058cbb  jmp     loc_180058F3B
0x180058cc0  lea     rcx, [rbp+57h+arg_8]
0x180058cc4  mov     [rbp+57h+var_50], rcx
0x180058cc8  lea     rcx, [rbp+57h+hLibModule]
0x180058ccc  mov     [rbp+57h+var_48], rcx
0x180058cd0  lea     rcx, [rbp+57h+var_60]
0x180058cd4  mov     [rbp+57h+var_40], rcx
0x180058cd8  lea     rcx, [rbp+57h+var_58]
0x180058cdc  mov     [rbp+57h+var_38], rcx
0x180058ce0  lea     rcx, [rbp+57h+arg_10]
0x180058ce4  mov     [rbp+57h+var_30], rcx
0x180058ce8  lea     rcx, [rbp+57h+arg_0]
0x180058cec  mov     [rbp+57h+var_28], rcx
0x180058cf0  mov     [rbp+57h+var_20], 1
0x180058cf4  lea     rdx, aDisminitialize; "DismInitialize"
0x180058cfb  mov     rcx, rax; hModule
0x180058cfe  call    cs:__imp_GetProcAddress
0x180058d04  test    rax, rax
0x180058d07  jnz     short loc_180058D3A
0x180058d09  mov     rcx, [rbp+5Fh]; this
0x180058d0d  mov     ebx, 8007000Eh
0x180058d12  mov     r9d, ebx; char *
0x180058d15  lea     r8, aOnecoreEnduser_21; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180058d1c  mov     edx, 11Dh; void *
0x180058d21  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058d26  nop
0x180058d27  mov     [rbp+57h+var_20], dil
0x180058d2b  lea     rcx, [rbp+57h+var_50]
0x180058d2f  call    _lambda_99c085c1750c74f319cfea667be7654b___operator__
0x180058d34  nop
0x180058d35  jmp     loc_180058CAA
0x180058d3a  xor     r8d, r8d
0x180058d3d  xor     edx, edx
0x180058d3f  lea     ecx, [rdx+1]
0x180058d42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058d47  mov     ebx, eax
0x180058d49  test    eax, eax
0x180058d4b  jns     short loc_180058D79
0x180058d4d  mov     rcx, [rbp+5Fh]; this
0x180058d51  mov     r9d, eax; char *
0x180058d54  lea     r8, aOnecoreEnduser_21; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180058d5b  mov     edx, 11Eh; void *
0x180058d60  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058d65  nop
0x180058d66  mov     [rbp+57h+var_20], dil
0x180058d6a  lea     rcx, [rbp+57h+var_50]
0x180058d6e  call    _lambda_99c085c1750c74f319cfea667be7654b___operator__
0x180058d73  nop
0x180058d74  jmp     loc_180058CAA
0x180058d79  mov     [rbp+57h+arg_0], 1
0x180058d7d  lea     rdx, aDismopensessio; "DismOpenSession"
0x180058d84  mov     rcx, [rbp+57h+hLibModule]; hModule
0x180058d88  call    cs:__imp_GetProcAddress
0x180058d8e  test    rax, rax
0x180058d91  jnz     short loc_180058DBD
0x180058d93  mov     rcx, [rbp+5Fh]; this
0x180058d97  lea     r8, aOnecoreEnduser_21; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180058d9e  mov     edx, 122h; void *
0x180058da3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180058da8  mov     ebx, eax
0x180058daa  mov     [rbp+57h+var_20], dil
0x180058dae  lea     rcx, [rbp+57h+var_50]
0x180058db2  call    _lambda_99c085c1750c74f319cfea667be7654b___operator__
0x180058db7  nop
0x180058db8  jmp     loc_180058CAA
0x180058dbd  lea     r9, [rbp+57h+arg_10]
0x180058dc1  xor     r8d, r8d
0x180058dc4  xor     edx, edx
0x180058dc6  lea     rcx, aDism53bfae52B1; "DISM_{53BFAE52-B167-4E2F-A258-0A37B57FF"...
0x180058dcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058dd2  mov     ebx, eax
0x180058dd4  test    eax, eax
0x180058dd6  jns     short loc_180058E04
0x180058dd8  mov     rcx, [rbp+5Fh]; this
0x180058ddc  mov     r9d, eax; char *
0x180058ddf  lea     r8, aOnecoreEnduser_21; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180058de6  mov     edx, 123h; void *
0x180058deb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058df0  nop
0x180058df1  mov     [rbp+57h+var_20], dil
0x180058df5  lea     rcx, [rbp+57h+var_50]
0x180058df9  call    _lambda_99c085c1750c74f319cfea667be7654b___operator__
0x180058dfe  nop
0x180058dff  jmp     loc_180058CAA
0x180058e04  mov     [rbp+57h+arg_8], 1
0x180058e08  mov     [rbp+57h+arg_18], edi
0x180058e0b  lea     rdx, aDismgetfeature; "DismGetFeatures"
0x180058e12  mov     rcx, [rbp+57h+hLibModule]; hModule
0x180058e16  call    cs:__imp_GetProcAddress
0x180058e1c  test    rax, rax
0x180058e1f  jnz     short loc_180058E4B
0x180058e21  mov     rcx, [rbp+5Fh]; this
0x180058e25  lea     r8, aOnecoreEnduser_21; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180058e2c  mov     edx, 128h; void *
0x180058e31  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180058e36  mov     ebx, eax
0x180058e38  mov     [rbp+57h+var_20], dil
0x180058e3c  lea     rcx, [rbp+57h+var_50]
0x180058e40  call    _lambda_99c085c1750c74f319cfea667be7654b___operator__
0x180058e45  nop
0x180058e46  jmp     loc_180058CAA
0x180058e4b  lea     rcx, [rbp+57h+arg_18]
0x180058e4f  mov     qword ptr [rsp+0A0h+var_80], rcx; int
0x180058e54  lea     r9, [rbp+57h+var_60]
0x180058e58  xor     r8d, r8d
0x180058e5b  xor     edx, edx
0x180058e5d  mov     ecx, [rbp+57h+arg_10]
0x180058e60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058e65  mov     ebx, eax
0x180058e67  test    eax, eax
0x180058e69  jns     short loc_180058E97
0x180058e6b  mov     rcx, [rbp+5Fh]; this
0x180058e6f  mov     r9d, eax; char *
0x180058e72  lea     r8, aOnecoreEnduser_21; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180058e79  mov     edx, 129h; void *
0x180058e7e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058e83  nop
0x180058e84  mov     [rbp+57h+var_20], dil
0x180058e88  lea     rcx, [rbp+57h+var_50]
0x180058e8c  call    _lambda_99c085c1750c74f319cfea667be7654b___operator__
0x180058e91  nop
0x180058e92  jmp     loc_180058CAA
0x180058e97  mov     [rbp+57h+var_70], edi
0x180058e9a  lea     rdx, aDismgetcapabil; "DismGetCapabilities"
0x180058ea1  mov     rcx, [rbp+57h+hLibModule]; hModule
0x180058ea5  call    cs:__imp_GetProcAddress
0x180058eab  test    rax, rax
0x180058eae  jnz     short loc_180058EDA
0x180058eb0  mov     rcx, [rbp+5Fh]; this
0x180058eb4  lea     r8, aOnecoreEnduser_21; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180058ebb  mov     edx, 12Dh; void *
0x180058ec0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180058ec5  mov     ebx, eax
0x180058ec7  mov     [rbp+57h+var_20], dil
0x180058ecb  lea     rcx, [rbp+57h+var_50]
0x180058ecf  call    _lambda_99c085c1750c74f319cfea667be7654b___operator__
0x180058ed4  nop
0x180058ed5  jmp     loc_180058CAA
0x180058eda  lea     r8, [rbp+57h+var_70]
0x180058ede  lea     rdx, [rbp+57h+var_58]
0x180058ee2  mov     ecx, [rbp+57h+arg_10]
0x180058ee5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058eea  mov     ebx, eax
0x180058eec  test    eax, eax
0x180058eee  jns     short loc_180058F1C
0x180058ef0  mov     rcx, [rbp+5Fh]; this
0x180058ef4  mov     r9d, eax; char *
0x180058ef7  lea     r8, aOnecoreEnduser_21; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180058efe  mov     edx, 12Eh; void *
0x180058f03  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058f08  nop
0x180058f09  mov     [rbp+57h+var_20], dil
0x180058f0d  lea     rcx, [rbp+57h+var_50]
0x180058f11  call    _lambda_99c085c1750c74f319cfea667be7654b___operator__
0x180058f16  nop
0x180058f17  jmp     loc_180058CAA
0x180058f1c  mov     [rbp+57h+var_20], dil
0x180058f20  lea     rcx, [rbp+57h+var_50]
0x180058f24  call    _lambda_99c085c1750c74f319cfea667be7654b___operator__
0x180058f29  nop
0x180058f2a  mov     rcx, [rbp+57h+hLibModule]; hLibModule
0x180058f2e  test    rcx, rcx
0x180058f31  jz      short loc_180058F39
0x180058f33  call    cs:__imp_FreeLibrary
0x180058f39  xor     eax, eax
0x180058f3b  add     rsp, 90h
0x180058f42  pop     rdi
0x180058f43  pop     rbx
0x180058f44  pop     rbp
0x180058f45  retn
```
