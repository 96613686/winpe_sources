# Add(ushort const *,ushort const *,ushort const *,bool)

- ea: `0x140003bd4`
- end: `0x140003e5a`
- name: `?Add@@YAXPEBG00_N@Z`
- size: `646`
- prototype: `void __fastcall(int *lpSubKey, int *, int *, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400063b0`
- `0x140006440`

## callees

- `0x140001008`
- `0x140003bd4`
- `0x1400064d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003c5b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003c5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003c48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003c48`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140003d90`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140003d90`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140003c9a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140003cd9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140003d18`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140003d57`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140003c9a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140003cd9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140003d18`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140003d57`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003c53`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003da7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003db7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003dc7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003dd7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003c53`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003da7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003db7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003dc7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003dd7`

## string_xrefs

- `0x140003c8c`: `SOFTWARE\Microsoft\Provisioning\CommandResults`

## pseudocode

```c
void __fastcall Add(int *lpSubKey, int *a2, int *a3, __int64 a4)
{
  int v4; // r12d
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // eax
  unsigned int dwOptions; // [rsp+20h] [rbp-59h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-59h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-59h]
  unsigned int dwOptionsc; // [rsp+20h] [rbp-59h]
  unsigned int dwOptionsd; // [rsp+20h] [rbp-59h]
  BYTE Data[8]; // [rsp+50h] [rbp-29h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-21h] BYREF
  HKEY v20; // [rsp+60h] [rbp-19h] BYREF
  HKEY v21; // [rsp+68h] [rbp-11h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-9h] BYREF
  int *v23; // [rsp+78h] [rbp-1h] BYREF
  int *v24; // [rsp+80h] [rbp+7h] BYREF
  int *v25; // [rsp+88h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v4 = (unsigned __int8)a4;
  hKey = 0;
  if ( (unsigned int)dword_140010000 > 4 )
  {
    v23 = a3;
    v24 = a2;
    v25 = lpSubKey;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (__int64)lpSubKey,
      (__int64)byte_14000D189,
      (__int64)a3,
      a4,
      &v25,
      &v24,
      &v23);
  }
  hKey = 0;
  v8 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Provisioning\\CommandResults",
         0,
         0,
         0,
         0xF003Fu,
         0,
         &hKey,
         0);
  if ( v8 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x2B,
      (int)"admin\\prov\\launch\\exe\\main.cpp",
      (const char *)v8,
      dwOptions);
  phkResult = 0;
  v9 = RegCreateKeyExW(hKey, (LPCWSTR)lpSubKey, 0, 0, 0, 0xF003Fu, 0, &phkResult, 0);
  if ( v9 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x30,
      (int)"admin\\prov\\launch\\exe\\main.cpp",
      (const char *)v9,
      dwOptionsa);
  v21 = 0;
  v10 = RegCreateKeyExW(phkResult, (LPCWSTR)a2, 0, 0, 0, 0xF003Fu, 0, &v21, 0);
  if ( v10 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x35,
      (int)"admin\\prov\\launch\\exe\\main.cpp",
      (const char *)v10,
      dwOptionsb);
  v20 = 0;
  v11 = RegCreateKeyExW(v21, (LPCWSTR)a3, 0, 0, 0, 0xF003Fu, 0, &v20, 0);
  if ( v11 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x3A,
      (int)"admin\\prov\\launch\\exe\\main.cpp",
      (const char *)v11,
      dwOptionsc);
  *(_DWORD *)Data = v4 + 1;
  v12 = RegSetValueExW(v20, L"State", 0, 4u, Data, 4u);
  if ( v12 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x43,
      (int)"admin\\prov\\launch\\exe\\main.cpp",
      (const char *)v12,
      dwOptionsd);
  if ( v20 )
    RegCloseKey(v20);
  if ( v21 )
    RegCloseKey(v21);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x140003bd4  push    rbp
0x140003bd6  push    rbx
0x140003bd7  push    rsi
0x140003bd8  push    rdi
0x140003bd9  push    r12
0x140003bdb  push    r13
0x140003bdd  push    r14
0x140003bdf  push    r15
0x140003be1  lea     rbp, [rsp-1Fh]
0x140003be6  sub     rsp, 98h
0x140003bed  movzx   r12d, r9b
0x140003bf1  mov     r15, r8
0x140003bf4  mov     r14, rdx
0x140003bf7  mov     rsi, rcx
0x140003bfa  xor     r13d, r13d
0x140003bfd  mov     [rbp+57h+hKey], r13
0x140003c01  mov     eax, cs:dword_140010000
0x140003c07  cmp     eax, 4
0x140003c0a  jbe     short loc_140003C3F
0x140003c0c  mov     [rbp+57h+var_58], r8
0x140003c10  mov     [rbp+57h+var_50], rdx
0x140003c14  mov     [rbp+57h+var_48], rcx
0x140003c18  lea     rax, [rbp+57h+var_58]
0x140003c1c  mov     [rsp+0D0h+lpSecurityAttributes], rax
0x140003c21  lea     rax, [rbp+57h+var_50]
0x140003c25  mov     qword ptr [rsp+0D0h+samDesired], rax
0x140003c2a  lea     rax, [rbp+57h+var_48]
0x140003c2e  mov     qword ptr [rsp+0D0h+dwOptions], rax
0x140003c33  lea     rdx, byte_14000D189
0x140003c3a  call    ??$Write@U?$_tlgWrapSz@G@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x140003c3f  mov     rdi, [rbp+57h+hKey]
0x140003c43  test    rdi, rdi
0x140003c46  jz      short loc_140003C61
0x140003c48  call    cs:__imp_GetLastError
0x140003c4e  mov     ebx, eax
0x140003c50  mov     rcx, rdi; hKey
0x140003c53  call    cs:__imp_RegCloseKey
0x140003c59  mov     ecx, ebx; dwErrCode
0x140003c5b  call    cs:__imp_SetLastError
0x140003c61  mov     [rbp+57h+hKey], r13
0x140003c65  mov     [rsp+0D0h+lpdwDisposition], r13; lpdwDisposition
0x140003c6a  lea     rax, [rbp+57h+hKey]
0x140003c6e  mov     [rsp+0D0h+phkResult], rax; phkResult
0x140003c73  mov     [rsp+0D0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x140003c78  mov     ebx, 0F003Fh
0x140003c7d  mov     [rsp+0D0h+samDesired], ebx; samDesired
0x140003c81  mov     [rsp+0D0h+dwOptions], r13d; unsigned int
0x140003c86  xor     r9d, r9d; lpClass
0x140003c89  xor     r8d, r8d; Reserved
0x140003c8c  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Provisioning\\Comm"...
0x140003c93  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140003c9a  call    cs:__imp_RegCreateKeyExW
0x140003ca0  mov     rcx, [rbp+5Fh]; this
0x140003ca4  test    eax, eax
0x140003ca6  jnz     loc_140003E06
0x140003cac  mov     [rbp+57h+var_60], r13
0x140003cb0  mov     [rsp+0D0h+lpdwDisposition], r13; lpdwDisposition
0x140003cb5  lea     rax, [rbp+57h+var_60]
0x140003cb9  mov     [rsp+0D0h+phkResult], rax; phkResult
0x140003cbe  mov     [rsp+0D0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x140003cc3  mov     [rsp+0D0h+samDesired], ebx; samDesired
0x140003cc7  mov     [rsp+0D0h+dwOptions], r13d; unsigned int
0x140003ccc  xor     r9d, r9d; lpClass
0x140003ccf  xor     r8d, r8d; Reserved
0x140003cd2  mov     rdx, rsi; lpSubKey
0x140003cd5  mov     rcx, [rbp+57h+hKey]; hKey
0x140003cd9  call    cs:__imp_RegCreateKeyExW
0x140003cdf  mov     rcx, [rbp+5Fh]; this
0x140003ce3  test    eax, eax
0x140003ce5  jnz     loc_140003E1B
0x140003ceb  mov     [rbp+57h+var_68], r13
0x140003cef  mov     [rsp+0D0h+lpdwDisposition], r13; lpdwDisposition
0x140003cf4  lea     rax, [rbp+57h+var_68]
0x140003cf8  mov     [rsp+0D0h+phkResult], rax; phkResult
0x140003cfd  mov     [rsp+0D0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x140003d02  mov     [rsp+0D0h+samDesired], ebx; samDesired
0x140003d06  mov     [rsp+0D0h+dwOptions], r13d; unsigned int
0x140003d0b  xor     r9d, r9d; lpClass
0x140003d0e  xor     r8d, r8d; Reserved
0x140003d11  mov     rdx, r14; lpSubKey
0x140003d14  mov     rcx, [rbp+57h+var_60]; hKey
0x140003d18  call    cs:__imp_RegCreateKeyExW
0x140003d1e  mov     rcx, [rbp+5Fh]; this
0x140003d22  test    eax, eax
0x140003d24  jnz     loc_140003E30
0x140003d2a  mov     [rbp+57h+var_70], r13
0x140003d2e  mov     [rsp+0D0h+lpdwDisposition], r13; lpdwDisposition
0x140003d33  lea     rax, [rbp+57h+var_70]
0x140003d37  mov     [rsp+0D0h+phkResult], rax; phkResult
0x140003d3c  mov     [rsp+0D0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x140003d41  mov     [rsp+0D0h+samDesired], ebx; samDesired
0x140003d45  mov     [rsp+0D0h+dwOptions], r13d; unsigned int
0x140003d4a  xor     r9d, r9d; lpClass
0x140003d4d  xor     r8d, r8d; Reserved
0x140003d50  mov     rdx, r15; lpSubKey
0x140003d53  mov     rcx, [rbp+57h+var_68]; hKey
0x140003d57  call    cs:__imp_RegCreateKeyExW
0x140003d5d  mov     rcx, [rbp+5Fh]; this
0x140003d61  test    eax, eax
0x140003d63  jnz     loc_140003E45
0x140003d69  inc     r12d
0x140003d6c  mov     dword ptr [rbp+57h+Data], r12d
0x140003d70  lea     r9d, [rax+4]; dwType
0x140003d74  mov     [rsp+0D0h+samDesired], r9d; cbData
0x140003d79  lea     rax, [rbp+57h+Data]
0x140003d7d  mov     qword ptr [rsp+0D0h+dwOptions], rax; unsigned int
0x140003d82  xor     r8d, r8d; Reserved
0x140003d85  lea     rdx, ValueName; "State"
0x140003d8c  mov     rcx, [rbp+57h+var_70]; hKey
0x140003d90  call    cs:__imp_RegSetValueExW
0x140003d96  mov     rcx, [rbp+5Fh]; this
0x140003d9a  test    eax, eax
0x140003d9c  jnz     short loc_140003DF1
0x140003d9e  mov     rcx, [rbp+57h+var_70]; hKey
0x140003da2  test    rcx, rcx
0x140003da5  jz      short loc_140003DAE
0x140003da7  call    cs:__imp_RegCloseKey
0x140003dad  nop
0x140003dae  mov     rcx, [rbp+57h+var_68]; hKey
0x140003db2  test    rcx, rcx
0x140003db5  jz      short loc_140003DBE
0x140003db7  call    cs:__imp_RegCloseKey
0x140003dbd  nop
0x140003dbe  mov     rcx, [rbp+57h+var_60]; hKey
0x140003dc2  test    rcx, rcx
0x140003dc5  jz      short loc_140003DCE
0x140003dc7  call    cs:__imp_RegCloseKey
0x140003dcd  nop
0x140003dce  mov     rcx, [rbp+57h+hKey]; hKey
0x140003dd2  test    rcx, rcx
0x140003dd5  jz      short loc_140003DDD
0x140003dd7  call    cs:__imp_RegCloseKey
0x140003ddd  add     rsp, 98h
0x140003de4  pop     r15
0x140003de6  pop     r14
0x140003de8  pop     r13
0x140003dea  pop     r12
0x140003dec  pop     rdi
0x140003ded  pop     rsi
0x140003dee  pop     rbx
0x140003def  pop     rbp
0x140003df0  retn
0x140003df1  mov     r9d, eax; char *
0x140003df4  lea     r8, aAdminProvLaunc; "admin\\prov\\launch\\exe\\main.cpp"
0x140003dfb  mov     edx, 43h ; 'C'; void *
0x140003e00  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x140003e06  mov     r9d, eax; char *
0x140003e09  lea     r8, aAdminProvLaunc; "admin\\prov\\launch\\exe\\main.cpp"
0x140003e10  mov     edx, 2Bh ; '+'; void *
0x140003e15  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x140003e1b  mov     r9d, eax; char *
0x140003e1e  lea     r8, aAdminProvLaunc; "admin\\prov\\launch\\exe\\main.cpp"
0x140003e25  mov     edx, 30h ; '0'; void *
0x140003e2a  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x140003e30  mov     r9d, eax; char *
0x140003e33  lea     r8, aAdminProvLaunc; "admin\\prov\\launch\\exe\\main.cpp"
0x140003e3a  mov     edx, 35h ; '5'; void *
0x140003e3f  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x140003e45  mov     r9d, eax; char *
0x140003e48  lea     r8, aAdminProvLaunc; "admin\\prov\\launch\\exe\\main.cpp"
0x140003e4f  mov     edx, 3Ah ; ':'; void *
0x140003e54  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
