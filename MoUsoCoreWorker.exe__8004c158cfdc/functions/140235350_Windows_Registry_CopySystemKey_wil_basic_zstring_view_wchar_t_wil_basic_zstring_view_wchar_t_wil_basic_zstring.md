# Windows::Registry::CopySystemKey(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)

- ea: `0x140235350`
- end: `0x140235548`
- name: `?CopySystemKey@Registry@Windows@@UEAAXV?$basic_zstring_view@_W@wil@@000@Z`
- size: `504`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task`

## callees

- `0x140045404`
- `0x1402350d0`
- `0x140235350`
- `0x14023695c`
- `0x140379070`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140235480`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140235480`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140235504`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140235514`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140235504`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140235514`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x1402354c0`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x1402354c0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140235417`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140235417`

## string_xrefs

- `0x140235443`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Registry.cpp`
- `0x1402354a5`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Registry.cpp`
- `0x1402354e9`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Registry.cpp`
- `0x1402354da`: `srcPath: %ws destPath: %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::Registry::CopySystemKey(
        __int64 a1,
        __int128 *a2,
        const char **a3,
        __int128 *a4,
        _QWORD *a5)
{
  const WCHAR *v8; // rdx
  unsigned int v9; // eax
  LPCWSTR *v10; // rdx
  const WCHAR *v11; // rdx
  unsigned int v12; // eax
  LPCWSTR *v13; // rdx
  unsigned int v14; // eax
  __int128 v16; // [rsp+50h] [rbp-51h] BYREF
  __int128 v17; // [rsp+60h] [rbp-41h] BYREF
  HKEY hKeySrc; // [rsp+70h] [rbp-31h] BYREF
  HKEY hKeyDest; // [rsp+78h] [rbp-29h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+80h] [rbp-21h] BYREF
  unsigned __int64 v21; // [rsp+98h] [rbp-9h]
  LPCWSTR v22[3]; // [rsp+A0h] [rbp-1h] BYREF
  unsigned __int64 v23; // [rsp+B8h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+57h]

  v16 = *(_OWORD *)a3;
  v17 = *a2;
  Windows::Registry::GetRedirectedRegistryKeyName(a1, v22, &v17, &v16);
  v17 = *(_OWORD *)a5;
  v16 = *a4;
  Windows::Registry::GetRedirectedRegistryKeyName(a1, lpSubKey, &v16, &v17);
  hKeyDest = 0;
  v8 = (const WCHAR *)lpSubKey;
  if ( v21 > 7 )
    v8 = lpSubKey[0];
  v9 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v8, 0, 0, 0, 0xF003Fu, 0, &hKeyDest, 0);
  v10 = lpSubKey;
  if ( v21 > 7 )
    v10 = (LPCWSTR *)lpSubKey[0];
  wil::details::in1diag3::Throw_IfWin32ErrorMsg(
    retaddr,
    (void *)0xEF,
    (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Registry.cpp",
    (const char *)v9,
    (unsigned int)"%ws",
    (const char *)v10);
  hKeySrc = 0;
  v11 = (const WCHAR *)v22;
  if ( v23 > 7 )
    v11 = v22[0];
  v12 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v11, 0, 0x20019u, &hKeySrc);
  v13 = v22;
  if ( v23 > 7 )
    v13 = (LPCWSTR *)v22[0];
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
  return std::wstring::~wstring(v22);
}

```

## disassembly

```asm
0x140235350  push    rbp
0x140235352  push    rbx
0x140235353  push    rsi
0x140235354  push    rdi
0x140235355  push    r14
0x140235357  lea     rbp, [rsp-2Fh]
0x14023535c  sub     rsp, 0D0h
0x140235363  mov     rax, cs:__security_cookie
0x14023536a  xor     rax, rsp
0x14023536d  mov     [rbp+4Fh+var_30], rax
0x140235371  mov     rbx, r9
0x140235374  mov     r14, r8
0x140235377  mov     rdi, rcx
0x14023537a  mov     rsi, [rbp+4Fh+arg_20]
0x14023537e  movups  xmm0, xmmword ptr [r8]
0x140235382  movdqu  [rbp+4Fh+var_A0], xmm0
0x140235387  movups  xmm1, xmmword ptr [rdx]
0x14023538a  movdqu  [rbp+4Fh+var_90], xmm1
0x14023538f  lea     r9, [rbp+4Fh+var_A0]
0x140235393  lea     r8, [rbp+4Fh+var_90]
0x140235397  lea     rdx, [rbp+4Fh+var_50]
0x14023539b  call    ?GetRedirectedRegistryKeyName@Registry@Windows@@UEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_zstring_view@_W@wil@@0@Z; Windows::Registry::GetRedirectedRegistryKeyName(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x1402353a0  nop
0x1402353a1  movups  xmm0, xmmword ptr [rsi]
0x1402353a4  movdqu  [rbp+4Fh+var_90], xmm0
0x1402353a9  movups  xmm1, xmmword ptr [rbx]
0x1402353ac  movdqu  [rbp+4Fh+var_A0], xmm1
0x1402353b1  lea     r9, [rbp+4Fh+var_90]
0x1402353b5  lea     r8, [rbp+4Fh+var_A0]
0x1402353b9  lea     rdx, [rbp+4Fh+lpSubKey]
0x1402353bd  mov     rcx, rdi
0x1402353c0  call    ?GetRedirectedRegistryKeyName@Registry@Windows@@UEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_zstring_view@_W@wil@@0@Z; Windows::Registry::GetRedirectedRegistryKeyName(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x1402353c5  nop
0x1402353c6  mov     [rbp+4Fh+hKeyDest], 0
0x1402353ce  lea     rdx, [rbp+4Fh+lpSubKey]
0x1402353d2  cmp     [rbp+4Fh+var_58], 7
0x1402353d7  cmova   rdx, [rbp+4Fh+lpSubKey]; lpSubKey
0x1402353dc  mov     [rsp+0F0h+lpdwDisposition], 0; lpdwDisposition
0x1402353e5  lea     rax, [rbp+4Fh+hKeyDest]
0x1402353e9  mov     [rsp+0F0h+phkResult], rax; phkResult
0x1402353ee  mov     [rsp+0F0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1402353f7  mov     [rsp+0F0h+samDesired], 0F003Fh; samDesired
0x1402353ff  mov     [rsp+0F0h+dwOptions], 0; dwOptions
0x140235407  xor     r9d, r9d; lpClass
0x14023540a  xor     r8d, r8d; Reserved
0x14023540d  mov     rbx, 0FFFFFFFF80000002h
0x140235414  mov     rcx, rbx; hKey
0x140235417  call    cs:__imp_RegCreateKeyExW
0x14023541d  lea     rdx, [rbp+4Fh+lpSubKey]
0x140235421  cmp     [rbp+4Fh+var_58], 7
0x140235426  cmova   rdx, [rbp+4Fh+lpSubKey]
0x14023542b  mov     rcx, [rbp+57h]; this
0x14023542f  mov     qword ptr [rsp+0F0h+samDesired], rdx; char *
0x140235434  lea     rdi, aWs_0; "%ws"
0x14023543b  mov     qword ptr [rsp+0F0h+dwOptions], rdi; unsigned int
0x140235440  mov     r9d, eax; char *
0x140235443  lea     r8, aCW1SSrcOrchest_85; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x14023544a  mov     edx, 0EFh; void *
0x14023544f  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x140235454  nop
0x140235455  mov     [rbp+4Fh+hKeySrc], 0
0x14023545d  lea     rdx, [rbp+4Fh+var_50]
0x140235461  cmp     [rbp+4Fh+var_38], 7
0x140235466  cmova   rdx, [rbp+4Fh+var_50]; lpSubKey
0x14023546b  lea     rax, [rbp+4Fh+hKeySrc]
0x14023546f  mov     qword ptr [rsp+0F0h+dwOptions], rax; phkResult
0x140235474  mov     r9d, 20019h; samDesired
0x14023547a  xor     r8d, r8d; ulOptions
0x14023547d  mov     rcx, rbx; hKey
0x140235480  call    cs:__imp_RegOpenKeyExW
0x140235486  lea     rdx, [rbp+4Fh+var_50]
0x14023548a  cmp     [rbp+4Fh+var_38], 7
0x14023548f  cmova   rdx, [rbp+4Fh+var_50]
0x140235494  mov     rcx, [rbp+57h]; this
0x140235498  mov     qword ptr [rsp+0F0h+samDesired], rdx; char *
0x14023549d  mov     qword ptr [rsp+0F0h+dwOptions], rdi; unsigned int
0x1402354a2  mov     r9d, eax; char *
0x1402354a5  lea     r8, aCW1SSrcOrchest_85; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1402354ac  mov     edx, 0F8h; void *
0x1402354b1  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x1402354b6  mov     r8, [rbp+4Fh+hKeyDest]; hKeyDest
0x1402354ba  xor     edx, edx; lpSubKey
0x1402354bc  mov     rcx, [rbp+4Fh+hKeySrc]; hKeySrc
0x1402354c0  call    cs:__imp_RegCopyTreeW
0x1402354c6  mov     rcx, [rbp+57h]; this
0x1402354ca  mov     rdx, [rsi]
0x1402354cd  mov     [rsp+0F0h+lpSecurityAttributes], rdx
0x1402354d2  mov     rdx, [r14]
0x1402354d5  mov     qword ptr [rsp+0F0h+samDesired], rdx; char *
0x1402354da  lea     rdx, aSrcpathWsDestp; "srcPath: %ws destPath: %ws"
0x1402354e1  mov     qword ptr [rsp+0F0h+dwOptions], rdx; unsigned int
0x1402354e6  mov     r9d, eax; char *
0x1402354e9  lea     r8, aCW1SSrcOrchest_85; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1402354f0  mov     edx, 0FBh; void *
0x1402354f5  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x1402354fa  nop
0x1402354fb  mov     rcx, [rbp+4Fh+hKeySrc]; hKey
0x1402354ff  test    rcx, rcx
0x140235502  jz      short loc_14023550B
0x140235504  call    cs:__imp_RegCloseKey
0x14023550a  nop
0x14023550b  mov     rcx, [rbp+4Fh+hKeyDest]; hKey
0x14023550f  test    rcx, rcx
0x140235512  jz      short loc_14023551B
0x140235514  call    cs:__imp_RegCloseKey
0x14023551a  nop
0x14023551b  lea     rcx, [rbp+4Fh+lpSubKey]
0x14023551f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140235524  nop
0x140235525  lea     rcx, [rbp+4Fh+var_50]
0x140235529  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14023552e  mov     rcx, [rbp+4Fh+var_30]
0x140235532  xor     rcx, rsp; StackCookie
0x140235535  call    __security_check_cookie
0x14023553a  add     rsp, 0D0h
0x140235541  pop     r14
0x140235543  pop     rdi
0x140235544  pop     rsi
0x140235545  pop     rbx
0x140235546  pop     rbp
0x140235547  retn
```
