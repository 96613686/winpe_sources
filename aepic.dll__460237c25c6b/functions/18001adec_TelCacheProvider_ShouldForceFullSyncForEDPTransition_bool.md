# TelCacheProvider::ShouldForceFullSyncForEDPTransition(bool)

- ea: `0x18001adec`
- end: `0x18001afd1`
- name: `?ShouldForceFullSyncForEDPTransition@TelCacheProvider@@AEAAH_N@Z`
- size: `485`
- prototype: `__int64 __fastcall(TelCacheProvider *__hidden this, bool)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001aa44`

## callees

- `0x180005890`
- `0x180010390`
- `0x18001adec`
- `0x1800295dc`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001ae36`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001ae36`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001ae50`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001ae50`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001aebd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001af07`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001aebd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001af07`

## string_xrefs

- `0x18001ae2f`: `DiagnosticDataSettings.dll`
- `0x18001aea5`: `RedirectedRegistryRoot`
- `0x18001af8c`: `TelCacheProvider::ShouldForceFullSyncForEDPTransition`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TelCacheProvider::ShouldForceFullSyncForEDPTransition(TelCacheProvider *this, char a2)
{
  unsigned int v4; // ebx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  __int64 v7; // r8
  bool v8; // zf
  LSTATUS ValueW; // eax
  const WCHAR *v10; // rdx
  __int64 v11; // rax
  DWORD pcbData[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v14; // [rsp+48h] [rbp-B8h] BYREF
  HMODULE v15[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE pvData[528]; // [rsp+60h] [rbp-A0h] BYREF

  v4 = 0;
  v14 = 0;
  Library = LoadLibraryExW(L"DiagnosticDataSettings.dll", 0, 0x800u);
  v15[0] = Library;
  if ( Library
    && (ProcAddress = GetProcAddress(Library, "TelIsOsInProcessorMode"), pcbData[0] = 0, ProcAddress)
    && ((int (__fastcall *)(DWORD *))ProcAddress)(pcbData) >= 0 )
  {
    v7 = 0;
    v8 = pcbData[0] == 0;
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
    v10 = (const WCHAR *)pvData;
    if ( ValueW )
      v10 = L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Diagnostics\\DiagTrack";
    pcbData[0] = 8;
    RegGetValueW(HKEY_LOCAL_MACHINE, v10, L"mspflags", 0x20000040u, 0, &v14, pcbData);
    v7 = 0;
    v8 = v14 == 0;
  }
  LOBYTE(v7) = !v8;
  v14 = v7;
  if ( a2 )
    goto LABEL_14;
  *(_QWORD *)pcbData = 0;
  if ( (*(int (__fastcall **)(_QWORD, const WCHAR *, DWORD *))(**((_QWORD **)this + 11) + 64LL))(
         *((_QWORD *)this + 11),
         L"mspflags",
         pcbData) >= 0 )
    v11 = *(_QWORD *)pcbData;
  else
    v11 = 0;
  if ( v11 != v14 )
  {
    v4 = 1;
LABEL_14:
    (*(void (__fastcall **)(_QWORD, const WCHAR *))(**((_QWORD **)this + 11) + 88LL))(
      *((_QWORD *)this + 11),
      L"mspflags");
    if ( v4 )
      AslLogCallPrintf(
        3,
        "TelCacheProvider::ShouldForceFullSyncForEDPTransition",
        2136,
        "Full sync may be needed because of EDP");
  }
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(v15);
  return v4;
}

```

## disassembly

```asm
0x18001adec  mov     [rsp-8+arg_8], rbx
0x18001adf1  mov     [rsp-8+arg_10], rsi
0x18001adf6  push    rbp
0x18001adf7  push    rdi
0x18001adf8  push    r14
0x18001adfa  lea     rbp, [rsp-180h]
0x18001ae02  sub     rsp, 280h
0x18001ae09  mov     rax, cs:__security_cookie
0x18001ae10  xor     rax, rsp
0x18001ae13  mov     [rbp+190h+var_20], rax
0x18001ae1a  mov     sil, dl
0x18001ae1d  mov     rdi, rcx
0x18001ae20  xor     ebx, ebx
0x18001ae22  mov     [rsp+290h+var_248], rbx
0x18001ae27  xor     edx, edx; hFile
0x18001ae29  mov     r8d, 800h; dwFlags
0x18001ae2f  lea     rcx, aDiagnosticdata_0; "DiagnosticDataSettings.dll"
0x18001ae36  call    cs:__imp_LoadLibraryExW
0x18001ae3c  mov     [rsp+290h+var_240], rax
0x18001ae41  test    rax, rax
0x18001ae44  jz      short loc_18001AE7A
0x18001ae46  lea     rdx, aTelisosinproce; "TelIsOsInProcessorMode"
0x18001ae4d  mov     rcx, rax; hModule
0x18001ae50  call    cs:__imp_GetProcAddress
0x18001ae56  mov     [rsp+290h+var_250], ebx
0x18001ae5a  test    rax, rax
0x18001ae5d  jz      short loc_18001AE7A
0x18001ae5f  lea     rcx, [rsp+290h+var_250]
0x18001ae64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ae69  test    eax, eax
0x18001ae6b  js      short loc_18001AE7A
0x18001ae6d  xor     r8d, r8d
0x18001ae70  cmp     [rsp+290h+var_250], r8d
0x18001ae75  jmp     loc_18001AF15
0x18001ae7a  mov     [rsp+290h+var_250], 208h
0x18001ae82  lea     rax, [rsp+290h+var_250]
0x18001ae87  mov     [rsp+290h+pcbData], rax; pcbData
0x18001ae8c  lea     rax, [rsp+290h+var_230]
0x18001ae91  mov     [rsp+290h+pvData], rax; pvData
0x18001ae96  mov     [rsp+290h+pdwType], 0; pdwType
0x18001ae9f  mov     r9d, 2; dwFlags
0x18001aea5  lea     r8, aRedirectedregi; "RedirectedRegistryRoot"
0x18001aeac  lea     r14, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001aeb3  mov     rdx, r14; lpSubKey
0x18001aeb6  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001aebd  call    cs:__imp_RegGetValueW
0x18001aec3  lea     rdx, [rsp+290h+var_230]
0x18001aec8  test    eax, eax
0x18001aeca  cmovnz  rdx, r14; lpSubKey
0x18001aece  mov     [rsp+290h+var_250], 8
0x18001aed6  lea     rax, [rsp+290h+var_250]
0x18001aedb  mov     [rsp+290h+pcbData], rax; pcbData
0x18001aee0  lea     rax, [rsp+290h+var_248]
0x18001aee5  mov     [rsp+290h+pvData], rax; pvData
0x18001aeea  mov     [rsp+290h+pdwType], 0; pdwType
0x18001aef3  mov     r9d, 20000040h; dwFlags
0x18001aef9  lea     r8, aMspflags; "mspflags"
0x18001af00  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001af07  call    cs:__imp_RegGetValueW
0x18001af0d  xor     r8d, r8d
0x18001af10  cmp     [rsp+290h+var_248], r8
0x18001af15  setnz   r8b
0x18001af19  mov     [rsp+290h+var_248], r8
0x18001af1e  test    sil, sil
0x18001af21  jnz     short loc_18001AF64
0x18001af23  mov     qword ptr [rsp+290h+var_250], 0
0x18001af2c  mov     rcx, [rdi+58h]
0x18001af30  mov     rax, [rcx]
0x18001af33  lea     r8, [rsp+290h+var_250]
0x18001af38  lea     rdx, aMspflags; "mspflags"
0x18001af3f  mov     rax, [rax+40h]
0x18001af43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001af48  test    eax, eax
0x18001af4a  jns     short loc_18001AF50
0x18001af4c  xor     eax, eax
0x18001af4e  jmp     short loc_18001AF55
0x18001af50  mov     rax, qword ptr [rsp+290h+var_250]
0x18001af55  mov     r8, [rsp+290h+var_248]
0x18001af5a  cmp     rax, r8
0x18001af5d  jz      short loc_18001AF9E
0x18001af5f  mov     ebx, 1
0x18001af64  mov     rcx, [rdi+58h]
0x18001af68  mov     rax, [rcx]
0x18001af6b  lea     rdx, aMspflags; "mspflags"
0x18001af72  mov     rax, [rax+58h]
0x18001af76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001af7b  test    ebx, ebx
0x18001af7d  jz      short loc_18001AF9E
0x18001af7f  lea     r9, aFullSyncMayBeN_1; "Full sync may be needed because of EDP"
0x18001af86  mov     r8d, 858h
0x18001af8c  lea     rdx, aTelcacheprovid_3; "TelCacheProvider::ShouldForceFullSyncFo"...
0x18001af93  mov     ecx, 3
0x18001af98  call    AslLogCallPrintf
0x18001af9d  nop
0x18001af9e  lea     rcx, [rsp+290h+var_240]
0x18001afa3  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18001afa8  mov     eax, ebx
0x18001afaa  mov     rcx, [rbp+190h+var_20]
0x18001afb1  xor     rcx, rsp; StackCookie
0x18001afb4  call    __security_check_cookie
0x18001afb9  lea     r11, [rsp+290h+var_10]
0x18001afc1  mov     rbx, [r11+28h]
0x18001afc5  mov     rsi, [r11+30h]
0x18001afc9  mov     rsp, r11
0x18001afcc  pop     r14
0x18001afce  pop     rdi
0x18001afcf  pop     rbp
0x18001afd0  retn
```
