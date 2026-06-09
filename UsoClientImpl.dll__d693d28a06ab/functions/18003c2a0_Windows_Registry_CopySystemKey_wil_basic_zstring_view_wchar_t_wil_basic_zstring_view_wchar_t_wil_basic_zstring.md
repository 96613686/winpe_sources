# Windows::Registry::CopySystemKey(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)

- ea: `0x18003c2a0`
- end: `0x18003c498`
- name: `?CopySystemKey@Registry@Windows@@UEAAXV?$basic_zstring_view@_W@wil@@000@Z`
- size: `504`
- prototype: `void __fastcall(__int64, __int128 *, const char **, __int128 *, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task`

## callees

- `0x180009380`
- `0x18003c020`
- `0x18003c2a0`
- `0x18003df70`
- `0x180056500`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c454`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c464`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c454`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c464`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003c3d0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003c3d0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003c367`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003c367`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x18003c410`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x18003c410`

## string_xrefs

- `0x18003c393`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Registry.cpp`
- `0x18003c3f5`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Registry.cpp`
- `0x18003c439`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Registry.cpp`
- `0x18003c42a`: `srcPath: %ws destPath: %ws`

## pseudocode

```c
void __fastcall Windows::Registry::CopySystemKey(__int64 a1, __int128 *a2, const char **a3, __int128 *a4, _QWORD *a5)
{
  const WCHAR *v8; // rdx
  unsigned int v9; // eax
  LPCWSTR *v10; // rdx
  const WCHAR *v11; // rdx
  unsigned int v12; // eax
  LPCWSTR *v13; // rdx
  unsigned int v14; // eax
  __int128 v15; // [rsp+50h] [rbp-51h] BYREF
  __int128 v16; // [rsp+60h] [rbp-41h] BYREF
  HKEY hKeySrc; // [rsp+70h] [rbp-31h] BYREF
  HKEY hKeyDest; // [rsp+78h] [rbp-29h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+80h] [rbp-21h] BYREF
  unsigned __int64 v20; // [rsp+98h] [rbp-9h]
  LPCWSTR v21[3]; // [rsp+A0h] [rbp-1h] BYREF
  unsigned __int64 v22; // [rsp+B8h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+57h]

  v15 = *(_OWORD *)a3;
  v16 = *a2;
  Windows::Registry::GetRedirectedRegistryKeyName(a1, v21, &v16, &v15);
  v16 = *(_OWORD *)a5;
  v15 = *a4;
  Windows::Registry::GetRedirectedRegistryKeyName(a1, lpSubKey, &v15, &v16);
  hKeyDest = 0;
  v8 = (const WCHAR *)lpSubKey;
  if ( v20 > 7 )
    v8 = lpSubKey[0];
  v9 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v8, 0, 0, 0, 0xF003Fu, 0, &hKeyDest, 0);
  v10 = lpSubKey;
  if ( v20 > 7 )
    v10 = (LPCWSTR *)lpSubKey[0];
  wil::details::in1diag3::Throw_IfWin32ErrorMsg(
    retaddr,
    (void *)0xEF,
    (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Registry.cpp",
    (const char *)v9,
    (unsigned int)"%ws",
    (const char *)v10);
  hKeySrc = 0;
  v11 = (const WCHAR *)v21;
  if ( v22 > 7 )
    v11 = v21[0];
  v12 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v11, 0, 0x20019u, &hKeySrc);
  v13 = v21;
  if ( v22 > 7 )
    v13 = (LPCWSTR *)v21[0];
  wil::details::in1diag3::Throw_IfWin32ErrorMsg(
    retaddr,
    (void *)0xF8,
    (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Registry.cpp",
    (const char *)v12,
    (unsigned int)"%ws",
    (const char *)v13);
  v14 = RegCopyTreeW(hKeySrc, 0, hKeyDest);
  wil::details::in1diag3::Throw_IfWin32ErrorMsg(
    retaddr,
    (void *)0xFB,
    (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Registry.cpp",
    (const char *)v14,
    (unsigned int)"srcPath: %ws destPath: %ws",
    *a3,
    *a5);
  if ( hKeySrc )
    RegCloseKey(hKeySrc);
  if ( hKeyDest )
    RegCloseKey(hKeyDest);
  std::wstring::~wstring(lpSubKey);
  std::wstring::~wstring(v21);
}

```

## disassembly

```asm
0x18003c2a0  push    rbp
0x18003c2a2  push    rbx
0x18003c2a3  push    rsi
0x18003c2a4  push    rdi
0x18003c2a5  push    r14
0x18003c2a7  lea     rbp, [rsp-2Fh]
0x18003c2ac  sub     rsp, 0D0h
0x18003c2b3  mov     rax, cs:__security_cookie
0x18003c2ba  xor     rax, rsp
0x18003c2bd  mov     [rbp+4Fh+var_30], rax
0x18003c2c1  mov     rbx, r9
0x18003c2c4  mov     r14, r8
0x18003c2c7  mov     rdi, rcx
0x18003c2ca  mov     rsi, [rbp+4Fh+arg_20]
0x18003c2ce  movups  xmm0, xmmword ptr [r8]
0x18003c2d2  movdqu  [rbp+4Fh+var_A0], xmm0
0x18003c2d7  movups  xmm1, xmmword ptr [rdx]
0x18003c2da  movdqu  [rbp+4Fh+var_90], xmm1
0x18003c2df  lea     r9, [rbp+4Fh+var_A0]
0x18003c2e3  lea     r8, [rbp+4Fh+var_90]
0x18003c2e7  lea     rdx, [rbp+4Fh+var_50]
0x18003c2eb  call    ?GetRedirectedRegistryKeyName@Registry@Windows@@UEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_zstring_view@_W@wil@@0@Z; Windows::Registry::GetRedirectedRegistryKeyName(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x18003c2f0  nop
0x18003c2f1  movups  xmm0, xmmword ptr [rsi]
0x18003c2f4  movdqu  [rbp+4Fh+var_90], xmm0
0x18003c2f9  movups  xmm1, xmmword ptr [rbx]
0x18003c2fc  movdqu  [rbp+4Fh+var_A0], xmm1
0x18003c301  lea     r9, [rbp+4Fh+var_90]
0x18003c305  lea     r8, [rbp+4Fh+var_A0]
0x18003c309  lea     rdx, [rbp+4Fh+lpSubKey]
0x18003c30d  mov     rcx, rdi
0x18003c310  call    ?GetRedirectedRegistryKeyName@Registry@Windows@@UEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_zstring_view@_W@wil@@0@Z; Windows::Registry::GetRedirectedRegistryKeyName(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x18003c315  nop
0x18003c316  mov     [rbp+4Fh+hKeyDest], 0
0x18003c31e  lea     rdx, [rbp+4Fh+lpSubKey]
0x18003c322  cmp     [rbp+4Fh+var_58], 7
0x18003c327  cmova   rdx, [rbp+4Fh+lpSubKey]; lpSubKey
0x18003c32c  mov     [rsp+0F0h+lpdwDisposition], 0; lpdwDisposition
0x18003c335  lea     rax, [rbp+4Fh+hKeyDest]
0x18003c339  mov     [rsp+0F0h+phkResult], rax; phkResult
0x18003c33e  mov     [rsp+0F0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18003c347  mov     [rsp+0F0h+samDesired], 0F003Fh; samDesired
0x18003c34f  mov     [rsp+0F0h+dwOptions], 0; dwOptions
0x18003c357  xor     r9d, r9d; lpClass
0x18003c35a  xor     r8d, r8d; Reserved
0x18003c35d  mov     rbx, 0FFFFFFFF80000002h
0x18003c364  mov     rcx, rbx; hKey
0x18003c367  call    cs:__imp_RegCreateKeyExW
0x18003c36d  lea     rdx, [rbp+4Fh+lpSubKey]
0x18003c371  cmp     [rbp+4Fh+var_58], 7
0x18003c376  cmova   rdx, [rbp+4Fh+lpSubKey]
0x18003c37b  mov     rcx, [rbp+57h]; this
0x18003c37f  mov     qword ptr [rsp+0F0h+samDesired], rdx; char *
0x18003c384  lea     rdi, aWs; "%ws"
0x18003c38b  mov     qword ptr [rsp+0F0h+dwOptions], rdi; unsigned int
0x18003c390  mov     r9d, eax; char *
0x18003c393  lea     r8, aCW1SSrcOrchest_2; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18003c39a  mov     edx, 0EFh; void *
0x18003c39f  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x18003c3a4  nop
0x18003c3a5  mov     [rbp+4Fh+hKeySrc], 0
0x18003c3ad  lea     rdx, [rbp+4Fh+var_50]
0x18003c3b1  cmp     [rbp+4Fh+var_38], 7
0x18003c3b6  cmova   rdx, [rbp+4Fh+var_50]; lpSubKey
0x18003c3bb  lea     rax, [rbp+4Fh+hKeySrc]
0x18003c3bf  mov     qword ptr [rsp+0F0h+dwOptions], rax; phkResult
0x18003c3c4  mov     r9d, 20019h; samDesired
0x18003c3ca  xor     r8d, r8d; ulOptions
0x18003c3cd  mov     rcx, rbx; hKey
0x18003c3d0  call    cs:__imp_RegOpenKeyExW
0x18003c3d6  lea     rdx, [rbp+4Fh+var_50]
0x18003c3da  cmp     [rbp+4Fh+var_38], 7
0x18003c3df  cmova   rdx, [rbp+4Fh+var_50]
0x18003c3e4  mov     rcx, [rbp+57h]; this
0x18003c3e8  mov     qword ptr [rsp+0F0h+samDesired], rdx; char *
0x18003c3ed  mov     qword ptr [rsp+0F0h+dwOptions], rdi; unsigned int
0x18003c3f2  mov     r9d, eax; char *
0x18003c3f5  lea     r8, aCW1SSrcOrchest_2; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18003c3fc  mov     edx, 0F8h; void *
0x18003c401  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x18003c406  mov     r8, [rbp+4Fh+hKeyDest]; hKeyDest
0x18003c40a  xor     edx, edx; lpSubKey
0x18003c40c  mov     rcx, [rbp+4Fh+hKeySrc]; hKeySrc
0x18003c410  call    cs:__imp_RegCopyTreeW
0x18003c416  mov     rcx, [rbp+57h]; this
0x18003c41a  mov     rdx, [rsi]
0x18003c41d  mov     [rsp+0F0h+lpSecurityAttributes], rdx
0x18003c422  mov     rdx, [r14]
0x18003c425  mov     qword ptr [rsp+0F0h+samDesired], rdx; char *
0x18003c42a  lea     rdx, aSrcpathWsDestp; "srcPath: %ws destPath: %ws"
0x18003c431  mov     qword ptr [rsp+0F0h+dwOptions], rdx; unsigned int
0x18003c436  mov     r9d, eax; char *
0x18003c439  lea     r8, aCW1SSrcOrchest_2; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18003c440  mov     edx, 0FBh; void *
0x18003c445  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x18003c44a  nop
0x18003c44b  mov     rcx, [rbp+4Fh+hKeySrc]; hKey
0x18003c44f  test    rcx, rcx
0x18003c452  jz      short loc_18003C45B
0x18003c454  call    cs:__imp_RegCloseKey
0x18003c45a  nop
0x18003c45b  mov     rcx, [rbp+4Fh+hKeyDest]; hKey
0x18003c45f  test    rcx, rcx
0x18003c462  jz      short loc_18003C46B
0x18003c464  call    cs:__imp_RegCloseKey
0x18003c46a  nop
0x18003c46b  lea     rcx, [rbp+4Fh+lpSubKey]; void *
0x18003c46f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003c474  nop
0x18003c475  lea     rcx, [rbp+4Fh+var_50]; void *
0x18003c479  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003c47e  mov     rcx, [rbp+4Fh+var_30]
0x18003c482  xor     rcx, rsp; StackCookie
0x18003c485  call    __security_check_cookie
0x18003c48a  add     rsp, 0D0h
0x18003c491  pop     r14
0x18003c493  pop     rdi
0x18003c494  pop     rsi
0x18003c495  pop     rbx
0x18003c496  pop     rbp
0x18003c497  retn
```
