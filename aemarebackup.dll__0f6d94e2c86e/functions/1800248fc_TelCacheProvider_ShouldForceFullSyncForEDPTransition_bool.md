# TelCacheProvider::ShouldForceFullSyncForEDPTransition(bool)

- ea: `0x1800248fc`
- end: `0x180024adb`
- name: `?ShouldForceFullSyncForEDPTransition@TelCacheProvider@@AEAAH_N@Z`
- size: `479`
- prototype: `__int64 __fastcall(TelCacheProvider *__hidden this, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180024458`

## callees

- `0x180004ea0`
- `0x1800248fc`
- `0x18004c020`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002495e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002495e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180024ab4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180024ab4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180024941`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180024941`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800249cb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180024a15`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800249cb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180024a15`

## string_xrefs

- `0x18002493a`: `DiagnosticDataSettings.dll`
- `0x1800249b3`: `RedirectedRegistryRoot`
- `0x180024a9a`: `TelCacheProvider::ShouldForceFullSyncForEDPTransition`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TelCacheProvider::ShouldForceFullSyncForEDPTransition(TelCacheProvider *this, char a2)
{
  unsigned int v4; // edi
  HMODULE Library; // rax
  HMODULE v6; // rbx
  FARPROC ProcAddress; // rax
  __int64 v8; // r8
  bool v9; // zf
  LSTATUS ValueW; // eax
  const WCHAR *v11; // rdx
  __int64 v12; // rax
  DWORD pcbData[2]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v15[3]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE pvData[528]; // [rsp+60h] [rbp-A0h] BYREF

  v4 = 0;
  v15[0] = 0;
  Library = LoadLibraryExW(L"DiagnosticDataSettings.dll", 0, 0x800u);
  v6 = Library;
  v15[1] = Library;
  if ( Library
    && (ProcAddress = GetProcAddress(Library, "TelIsOsInProcessorMode"), pcbData[0] = 0, ProcAddress)
    && ((int (__fastcall *)(DWORD *))ProcAddress)(pcbData) >= 0 )
  {
    v8 = 0;
    v9 = pcbData[0] == 0;
  }
  else
  {
    pcbData[0] = 520;
    ValueW = RegGetValueW(
               HKEY_LOCAL_MACHINE,
               L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Diagnostics\\DiagTrack",
               L"RedirectedRegistryRoot",
               2u,
               0,
               pvData,
               pcbData);
    v11 = (const WCHAR *)pvData;
    if ( ValueW )
      v11 = L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Diagnostics\\DiagTrack";
    pcbData[0] = 8;
    RegGetValueW(HKEY_LOCAL_MACHINE, v11, L"mspflags", 0x20000040u, 0, v15, pcbData);
    v8 = 0;
    v9 = v15[0] == 0;
  }
  LOBYTE(v8) = !v9;
  v15[0] = v8;
  if ( !a2 )
  {
    *(_QWORD *)pcbData = 0;
    if ( (*(int (__fastcall **)(_QWORD, const WCHAR *, DWORD *))(**((_QWORD **)this + 11) + 64LL))(
           *((_QWORD *)this + 11),
           L"mspflags",
           pcbData) >= 0 )
      v12 = *(_QWORD *)pcbData;
    else
      v12 = 0;
    if ( v12 == v15[0] )
      goto LABEL_16;
    v4 = 1;
  }
  (*(void (__fastcall **)(_QWORD, const WCHAR *))(**((_QWORD **)this + 11) + 88LL))(*((_QWORD *)this + 11), L"mspflags");
  if ( v4 )
    AslLogCallPrintf(
      3,
      "TelCacheProvider::ShouldForceFullSyncForEDPTransition",
      2136,
      "Full sync may be needed because of EDP");
LABEL_16:
  if ( v6 )
    FreeLibrary(v6);
  return v4;
}

```

## disassembly

```asm
0x1800248fc  push    rbp
0x1800248fe  push    rbx
0x1800248ff  push    rsi
0x180024900  push    rdi
0x180024901  push    r14
0x180024903  push    r15
0x180024905  lea     rbp, [rsp-188h]
0x18002490d  sub     rsp, 288h
0x180024914  mov     rax, cs:__security_cookie
0x18002491b  xor     rax, rsp
0x18002491e  mov     [rbp+1B0h+var_40], rax
0x180024925  mov     r14b, dl
0x180024928  mov     rsi, rcx
0x18002492b  xor     edi, edi
0x18002492d  mov     [rsp+2B0h+var_268], rdi
0x180024932  xor     edx, edx; hFile
0x180024934  mov     r8d, 800h; dwFlags
0x18002493a  lea     rcx, aDiagnosticdata_0; "DiagnosticDataSettings.dll"
0x180024941  call    cs:__imp_LoadLibraryExW
0x180024947  mov     rbx, rax
0x18002494a  mov     [rsp+2B0h+var_260], rax
0x18002494f  test    rax, rax
0x180024952  jz      short loc_180024988
0x180024954  lea     rdx, aTelisosinproce; "TelIsOsInProcessorMode"
0x18002495b  mov     rcx, rax; hModule
0x18002495e  call    cs:__imp_GetProcAddress
0x180024964  mov     [rsp+2B0h+var_270], edi
0x180024968  test    rax, rax
0x18002496b  jz      short loc_180024988
0x18002496d  lea     rcx, [rsp+2B0h+var_270]
0x180024972  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024977  test    eax, eax
0x180024979  js      short loc_180024988
0x18002497b  xor     r8d, r8d
0x18002497e  cmp     [rsp+2B0h+var_270], r8d
0x180024983  jmp     loc_180024A23
0x180024988  mov     [rsp+2B0h+var_270], 208h
0x180024990  lea     rax, [rsp+2B0h+var_270]
0x180024995  mov     [rsp+2B0h+pcbData], rax; pcbData
0x18002499a  lea     rax, [rsp+2B0h+var_250]
0x18002499f  mov     [rsp+2B0h+pvData], rax; pvData
0x1800249a4  mov     [rsp+2B0h+pdwType], 0; pdwType
0x1800249ad  mov     r9d, 2; dwFlags
0x1800249b3  lea     r8, aRedirectedregi; "RedirectedRegistryRoot"
0x1800249ba  lea     r15, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800249c1  mov     rdx, r15; lpSubKey
0x1800249c4  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800249cb  call    cs:__imp_RegGetValueW
0x1800249d1  lea     rdx, [rsp+2B0h+var_250]
0x1800249d6  test    eax, eax
0x1800249d8  cmovnz  rdx, r15; lpSubKey
0x1800249dc  mov     [rsp+2B0h+var_270], 8
0x1800249e4  lea     rax, [rsp+2B0h+var_270]
0x1800249e9  mov     [rsp+2B0h+pcbData], rax; pcbData
0x1800249ee  lea     rax, [rsp+2B0h+var_268]
0x1800249f3  mov     [rsp+2B0h+pvData], rax; pvData
0x1800249f8  mov     [rsp+2B0h+pdwType], 0; pdwType
0x180024a01  mov     r9d, 20000040h; dwFlags
0x180024a07  lea     r8, aMspflags; "mspflags"
0x180024a0e  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180024a15  call    cs:__imp_RegGetValueW
0x180024a1b  xor     r8d, r8d
0x180024a1e  cmp     [rsp+2B0h+var_268], r8
0x180024a23  setnz   r8b
0x180024a27  mov     [rsp+2B0h+var_268], r8
0x180024a2c  test    r14b, r14b
0x180024a2f  jnz     short loc_180024A72
0x180024a31  mov     qword ptr [rsp+2B0h+var_270], 0
0x180024a3a  mov     rcx, [rsi+58h]
0x180024a3e  mov     rax, [rcx]
0x180024a41  lea     r8, [rsp+2B0h+var_270]
0x180024a46  lea     rdx, aMspflags; "mspflags"
0x180024a4d  mov     rax, [rax+40h]
0x180024a51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024a56  test    eax, eax
0x180024a58  jns     short loc_180024A5E
0x180024a5a  xor     eax, eax
0x180024a5c  jmp     short loc_180024A63
0x180024a5e  mov     rax, qword ptr [rsp+2B0h+var_270]
0x180024a63  mov     r8, [rsp+2B0h+var_268]
0x180024a68  cmp     rax, r8
0x180024a6b  jz      short loc_180024AAC
0x180024a6d  mov     edi, 1
0x180024a72  mov     rcx, [rsi+58h]
0x180024a76  mov     rax, [rcx]
0x180024a79  lea     rdx, aMspflags; "mspflags"
0x180024a80  mov     rax, [rax+58h]
0x180024a84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024a89  test    edi, edi
0x180024a8b  jz      short loc_180024AAC
0x180024a8d  lea     r9, aFullSyncMayBeN_1; "Full sync may be needed because of EDP"
0x180024a94  mov     r8d, 858h
0x180024a9a  lea     rdx, aTelcacheprovid_4; "TelCacheProvider::ShouldForceFullSyncFo"...
0x180024aa1  mov     ecx, 3
0x180024aa6  call    AslLogCallPrintf
0x180024aab  nop
0x180024aac  test    rbx, rbx
0x180024aaf  jz      short loc_180024ABA
0x180024ab1  mov     rcx, rbx; hLibModule
0x180024ab4  call    cs:__imp_FreeLibrary
0x180024aba  mov     eax, edi
0x180024abc  mov     rcx, [rbp+1B0h+var_40]
0x180024ac3  xor     rcx, rsp; StackCookie
0x180024ac6  call    __security_check_cookie
0x180024acb  add     rsp, 288h
0x180024ad2  pop     r15
0x180024ad4  pop     r14
0x180024ad6  pop     rdi
0x180024ad7  pop     rsi
0x180024ad8  pop     rbx
0x180024ad9  pop     rbp
0x180024ada  retn
```
