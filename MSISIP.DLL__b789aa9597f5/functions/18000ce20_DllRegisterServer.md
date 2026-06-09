# DllRegisterServer

- ea: `0x18000ce20`
- end: `0x18000cf10`
- name: `DllRegisterServer`
- size: `240`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callees

- `0x18000ce20`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000cec8`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000cec8`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18000cef3`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18000cef3`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x18000cea9`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x18000cea9`

## string_xrefs

- `0x18000ce43`: `crypt32.dll`
- `0x18000ce4a`: `MSISIP.DLL`
- `0x18000ce63`: `MsiSIPGetSignedDataMsg`
- `0x18000ce6e`: `MsiSIPPutSignedDataMsg`
- `0x18000ce79`: `MsiSIPCreateIndirectData`
- `0x18000ce84`: `MsiSIPVerifyIndirectData`
- `0x18000ce8f`: `MsiSIPRemoveSignedDataMsg`
- `0x18000ce9a`: `MsiSIPIsMyTypeOfFile`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  HMODULE LibraryW; // rax
  HMODULE v1; // rdi
  FARPROC ProcAddress; // rax
  HRESULT v4; // ebx
  _QWORD v5[3]; // [rsp+20h] [rbp-60h] BYREF
  __int128 v6; // [rsp+38h] [rbp-48h]
  const wchar_t *v7; // [rsp+48h] [rbp-38h]
  const wchar_t *v8; // [rsp+50h] [rbp-30h]
  const wchar_t *v9; // [rsp+58h] [rbp-28h]
  const wchar_t *v10; // [rsp+60h] [rbp-20h]
  const wchar_t *v11; // [rsp+68h] [rbp-18h]
  const wchar_t *v12; // [rsp+70h] [rbp-10h]
  __int64 v13; // [rsp+78h] [rbp-8h]

  v5[0] = 96;
  v13 = 0;
  v5[2] = L"MSISIP.DLL";
  v5[1] = &gMSI;
  v7 = L"MsiSIPGetSignedDataMsg";
  v8 = L"MsiSIPPutSignedDataMsg";
  v9 = L"MsiSIPCreateIndirectData";
  v10 = L"MsiSIPVerifyIndirectData";
  v11 = L"MsiSIPRemoveSignedDataMsg";
  v12 = L"MsiSIPIsMyTypeOfFile";
  v6 = 0;
  LibraryW = LoadLibraryW(L"crypt32.dll");
  v1 = LibraryW;
  if ( !LibraryW )
    return -2147467259;
  ProcAddress = GetProcAddress(LibraryW, "CryptSIPAddProvider");
  if ( ProcAddress )
    v4 = ((unsigned int (__fastcall *)(_QWORD *))ProcAddress)(v5) == 0 ? 0x80004005 : 0;
  else
    v4 = -2147467259;
  FreeLibrary(v1);
  return v4;
}

```

## disassembly

```asm
0x18000ce20  mov     [rsp-8+arg_0], rbx
0x18000ce25  mov     [rsp-8+arg_8], rdi
0x18000ce2a  push    rbp
0x18000ce2b  mov     rbp, rsp
0x18000ce2e  sub     rsp, 80h
0x18000ce35  xor     eax, eax
0x18000ce37  mov     [rbp+var_60], 60h ; '`'
0x18000ce3f  mov     [rbp+var_8], rax
0x18000ce43  lea     rcx, aCrypt32Dll; "crypt32.dll"
0x18000ce4a  lea     rax, aMsisipDll_0; "MSISIP.DLL"
0x18000ce51  xorps   xmm0, xmm0
0x18000ce54  mov     [rbp+var_50], rax
0x18000ce58  lea     rax, ?gMSI@@3U_GUID@@A; _GUID gMSI
0x18000ce5f  mov     [rbp+var_58], rax
0x18000ce63  lea     rax, aMsisipgetsigne_0; "MsiSIPGetSignedDataMsg"
0x18000ce6a  mov     [rbp+var_38], rax
0x18000ce6e  lea     rax, aMsisipputsigne_0; "MsiSIPPutSignedDataMsg"
0x18000ce75  mov     [rbp+var_30], rax
0x18000ce79  lea     rax, aMsisipcreatein_0; "MsiSIPCreateIndirectData"
0x18000ce80  mov     [rbp+var_28], rax
0x18000ce84  lea     rax, aMsisipverifyin_0; "MsiSIPVerifyIndirectData"
0x18000ce8b  mov     [rbp+var_20], rax
0x18000ce8f  lea     rax, aMsisipremovesi_0; "MsiSIPRemoveSignedDataMsg"
0x18000ce96  mov     [rbp+var_18], rax
0x18000ce9a  lea     rax, aMsisipismytype_0; "MsiSIPIsMyTypeOfFile"
0x18000cea1  mov     [rbp+var_10], rax
0x18000cea5  movups  [rbp+var_48], xmm0
0x18000cea9  call    cs:__imp_LoadLibraryW
0x18000ceaf  mov     rdi, rax
0x18000ceb2  test    rax, rax
0x18000ceb5  jnz     short loc_18000CEBE
0x18000ceb7  mov     eax, 80004005h
0x18000cebc  jmp     short loc_18000CEFB
0x18000cebe  lea     rdx, aCryptsipaddpro; "CryptSIPAddProvider"
0x18000cec5  mov     rcx, rdi; hModule
0x18000cec8  call    cs:__imp_GetProcAddress
0x18000cece  test    rax, rax
0x18000ced1  jnz     short loc_18000CEDA
0x18000ced3  mov     ebx, 80004005h
0x18000ced8  jmp     short loc_18000CEF0
0x18000ceda  lea     rcx, [rbp+var_60]
0x18000cede  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cee3  neg     eax
0x18000cee5  mov     ebx, 80004005h
0x18000ceea  sbb     ecx, ecx
0x18000ceec  not     ecx
0x18000ceee  and     ebx, ecx
0x18000cef0  mov     rcx, rdi; hLibModule
0x18000cef3  call    cs:__imp_FreeLibrary
0x18000cef9  mov     eax, ebx
0x18000cefb  lea     r11, [rsp+80h+var_s0]
0x18000cf03  mov     rbx, [r11+10h]
0x18000cf07  mov     rdi, [r11+18h]
0x18000cf0b  mov     rsp, r11
0x18000cf0e  pop     rbp
0x18000cf0f  retn
```
