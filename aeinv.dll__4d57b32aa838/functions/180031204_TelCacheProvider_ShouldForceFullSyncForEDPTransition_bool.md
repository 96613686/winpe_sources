# TelCacheProvider::ShouldForceFullSyncForEDPTransition(bool)

- ea: `0x180031204`
- end: `0x1800313ec`
- name: `?ShouldForceFullSyncForEDPTransition@TelCacheProvider@@AEAAH_N@Z`
- size: `488`
- prototype: `__int64 __fastcall(TelCacheProvider *__hidden this, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180066814`

## callees

- `0x1800197d4`
- `0x180031204`
- `0x180059920`
- `0x180130010`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x1800312dc`
- `ADVAPI32!RegGetValueW` at `0x180031326`
- `ADVAPI32!RegGetValueW` at `0x1800312dc`
- `ADVAPI32!RegGetValueW` at `0x180031326`
- `KERNEL32!LoadLibraryExW` at `0x180031252`
- `KERNEL32!LoadLibraryExW` at `0x180031252`
- `KERNEL32!FreeLibrary` at `0x1800313c5`
- `KERNEL32!FreeLibrary` at `0x1800313c5`
- `KERNEL32!GetProcAddress` at `0x18003126f`
- `KERNEL32!GetProcAddress` at `0x18003126f`

## string_xrefs

- `0x18003124b`: `DiagnosticDataSettings.dll`
- `0x1800312c4`: `RedirectedRegistryRoot`
- `0x1800313ab`: `TelCacheProvider::ShouldForceFullSyncForEDPTransition`

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

  v15[1] = -2;
  v4 = 0;
  v15[0] = 0;
  Library = LoadLibraryExW(L"DiagnosticDataSettings.dll", 0, 0x800u);
  v6 = Library;
  v15[2] = Library;
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
      (unsigned int)"TelCacheProvider::ShouldForceFullSyncForEDPTransition",
      2136,
      (unsigned int)"Full sync may be needed because of EDP");
LABEL_16:
  if ( v6 )
    FreeLibrary(v6);
  return v4;
}

```

## disassembly

```asm
0x180031204  push    rbp
0x180031206  push    rbx
0x180031207  push    rsi
0x180031208  push    rdi
0x180031209  push    r14
0x18003120b  push    r15
0x18003120d  lea     rbp, [rsp-188h]
0x180031215  sub     rsp, 288h
0x18003121c  mov     [rsp+2B0h+var_260], 0FFFFFFFFFFFFFFFEh
0x180031225  mov     rax, cs:__security_cookie
0x18003122c  xor     rax, rsp
0x18003122f  mov     [rbp+1B0h+var_40], rax
0x180031236  mov     r14b, dl
0x180031239  mov     rsi, rcx
0x18003123c  xor     edi, edi
0x18003123e  mov     [rsp+2B0h+var_268], rdi
0x180031243  xor     edx, edx; hFile
0x180031245  mov     r8d, 800h; dwFlags
0x18003124b  lea     rcx, aDiagnosticdata_0; "DiagnosticDataSettings.dll"
0x180031252  call    cs:__imp_LoadLibraryExW
0x180031258  mov     rbx, rax
0x18003125b  mov     [rsp+2B0h+var_258], rax
0x180031260  test    rax, rax
0x180031263  jz      short loc_180031299
0x180031265  lea     rdx, aTelisosinproce; "TelIsOsInProcessorMode"
0x18003126c  mov     rcx, rax; hModule
0x18003126f  call    cs:__imp_GetProcAddress
0x180031275  mov     [rsp+2B0h+var_270], edi
0x180031279  test    rax, rax
0x18003127c  jz      short loc_180031299
0x18003127e  lea     rcx, [rsp+2B0h+var_270]
0x180031283  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031288  test    eax, eax
0x18003128a  js      short loc_180031299
0x18003128c  xor     r8d, r8d
0x18003128f  cmp     [rsp+2B0h+var_270], r8d
0x180031294  jmp     loc_180031334
0x180031299  mov     [rsp+2B0h+var_270], 208h
0x1800312a1  lea     rax, [rsp+2B0h+var_270]
0x1800312a6  mov     [rsp+2B0h+pcbData], rax; pcbData
0x1800312ab  lea     rax, [rsp+2B0h+var_250]
0x1800312b0  mov     [rsp+2B0h+pvData], rax; pvData
0x1800312b5  mov     [rsp+2B0h+pdwType], 0; pdwType
0x1800312be  mov     r9d, 2; dwFlags
0x1800312c4  lea     r8, aRedirectedregi; "RedirectedRegistryRoot"
0x1800312cb  lea     r15, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800312d2  mov     rdx, r15; lpSubKey
0x1800312d5  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800312dc  call    cs:__imp_RegGetValueW
0x1800312e2  lea     rdx, [rsp+2B0h+var_250]
0x1800312e7  test    eax, eax
0x1800312e9  cmovnz  rdx, r15; lpSubKey
0x1800312ed  mov     [rsp+2B0h+var_270], 8
0x1800312f5  lea     rax, [rsp+2B0h+var_270]
0x1800312fa  mov     [rsp+2B0h+pcbData], rax; pcbData
0x1800312ff  lea     rax, [rsp+2B0h+var_268]
0x180031304  mov     [rsp+2B0h+pvData], rax; pvData
0x180031309  mov     [rsp+2B0h+pdwType], 0; pdwType
0x180031312  mov     r9d, 20000040h; dwFlags
0x180031318  lea     r8, aMspflags; "mspflags"
0x18003131f  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180031326  call    cs:__imp_RegGetValueW
0x18003132c  xor     r8d, r8d
0x18003132f  cmp     [rsp+2B0h+var_268], r8
0x180031334  setnz   r8b
0x180031338  mov     [rsp+2B0h+var_268], r8
0x18003133d  test    r14b, r14b
0x180031340  jnz     short loc_180031383
0x180031342  mov     qword ptr [rsp+2B0h+var_270], 0
0x18003134b  mov     rcx, [rsi+58h]
0x18003134f  mov     rax, [rcx]
0x180031352  lea     r8, [rsp+2B0h+var_270]
0x180031357  lea     rdx, aMspflags; "mspflags"
0x18003135e  mov     rax, [rax+40h]
0x180031362  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031367  test    eax, eax
0x180031369  jns     short loc_18003136F
0x18003136b  xor     eax, eax
0x18003136d  jmp     short loc_180031374
0x18003136f  mov     rax, qword ptr [rsp+2B0h+var_270]
0x180031374  mov     r8, [rsp+2B0h+var_268]
0x180031379  cmp     rax, r8
0x18003137c  jz      short loc_1800313BD
0x18003137e  mov     edi, 1
0x180031383  mov     rcx, [rsi+58h]
0x180031387  mov     rax, [rcx]
0x18003138a  lea     rdx, aMspflags; "mspflags"
0x180031391  mov     rax, [rax+58h]
0x180031395  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003139a  test    edi, edi
0x18003139c  jz      short loc_1800313BD
0x18003139e  lea     r9, aFullSyncMayBeN_1; "Full sync may be needed because of EDP"
0x1800313a5  mov     r8d, 858h
0x1800313ab  lea     rdx, aTelcacheprovid_3; "TelCacheProvider::ShouldForceFullSyncFo"...
0x1800313b2  mov     ecx, 3
0x1800313b7  call    AslLogCallPrintf
0x1800313bc  nop
0x1800313bd  test    rbx, rbx
0x1800313c0  jz      short loc_1800313CB
0x1800313c2  mov     rcx, rbx; hLibModule
0x1800313c5  call    cs:__imp_FreeLibrary
0x1800313cb  mov     eax, edi
0x1800313cd  mov     rcx, [rbp+1B0h+var_40]
0x1800313d4  xor     rcx, rsp; StackCookie
0x1800313d7  call    __security_check_cookie
0x1800313dc  add     rsp, 288h
0x1800313e3  pop     r15
0x1800313e5  pop     r14
0x1800313e7  pop     rdi
0x1800313e8  pop     rsi
0x1800313e9  pop     rbx
0x1800313ea  pop     rbp
0x1800313eb  retn
```
