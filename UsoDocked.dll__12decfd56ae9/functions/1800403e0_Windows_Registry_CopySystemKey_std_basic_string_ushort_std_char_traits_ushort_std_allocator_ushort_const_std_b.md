# Windows::Registry::CopySystemKey(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800403e0`
- end: `0x1800405cf`
- name: `?CopySystemKey@Registry@Windows@@UEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@000@Z`
- size: `495`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x180007660`
- `0x18001ee04`
- `0x1800403e0`
- `0x1800408f8`
- `0x180071010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800404f9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800404f9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004058b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004059b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004058b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004059b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180040490`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180040490`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x180040539`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x180040539`

## string_xrefs

- `0x180040561`: `srcPath: %ws destPath: %ws`
- `0x1800404bc`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\registry.cpp`
- `0x18004051e`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\registry.cpp`
- `0x180040570`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\registry.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::Registry::CopySystemKey(__int64 a1, __int64 a2, __int64 *a3, __int64 a4, _QWORD *a5)
{
  const char *v6; // rsi
  _QWORD *v8; // r14
  const WCHAR *v9; // rdx
  unsigned int v10; // eax
  LPCWSTR *v11; // rdx
  const WCHAR *v12; // rdx
  unsigned int v13; // eax
  LPCWSTR *v14; // rdx
  unsigned int v15; // eax
  HKEY hKeySrc; // [rsp+50h] [rbp-31h] BYREF
  HKEY hKeyDest; // [rsp+58h] [rbp-29h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+60h] [rbp-21h] BYREF
  unsigned __int64 v20; // [rsp+78h] [rbp-9h]
  LPCWSTR v21[3]; // [rsp+80h] [rbp-1h] BYREF
  unsigned __int64 v22; // [rsp+98h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+57h]

  v6 = (const char *)a3;
  v8 = a5;
  (*(void (__fastcall **)(__int64, LPCWSTR *, __int64, __int64 *))(*(_QWORD *)a1 + 88LL))(a1, v21, a2, a3);
  (*(void (__fastcall **)(__int64, LPCWSTR *, __int64, _QWORD *))(*(_QWORD *)a1 + 88LL))(a1, lpSubKey, a4, a5);
  hKeyDest = 0;
  v9 = (const WCHAR *)lpSubKey;
  if ( v20 > 7 )
    v9 = lpSubKey[0];
  v10 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v9, 0, 0, 0, 0xF003Fu, 0, &hKeyDest, 0);
  v11 = lpSubKey;
  if ( v20 > 7 )
    v11 = (LPCWSTR *)lpSubKey[0];
  wil::details::in1diag3::Throw_IfWin32ErrorMsg(
    retaddr,
    (void *)0x100,
    (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\registry.cpp",
    (const char *)v10,
    (unsigned int)"%ws",
    (const char *)v11);
  hKeySrc = 0;
  v12 = (const WCHAR *)v21;
  if ( v22 > 7 )
    v12 = v21[0];
  v13 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v12, 0, 0x20019u, &hKeySrc);
  v14 = v21;
  if ( v22 > 7 )
    v14 = (LPCWSTR *)v21[0];
  wil::details::in1diag3::Throw_IfWin32ErrorMsg(
    retaddr,
    (void *)0x109,
    (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\registry.cpp",
    (const char *)v13,
    (unsigned int)"%ws",
    (const char *)v14);
  v15 = RegCopyTreeW(hKeySrc, 0, hKeyDest);
  if ( a5[3] > 7u )
    v8 = (_QWORD *)*a5;
  if ( *((_QWORD *)v6 + 3) > 7u )
    v6 = *(const char **)v6;
  wil::details::in1diag3::Throw_IfWin32ErrorMsg(
    retaddr,
    (void *)0x10F,
    (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\registry.cpp",
    (const char *)v15,
    (unsigned int)"srcPath: %ws destPath: %ws",
    v6,
    v8);
  if ( hKeySrc )
    RegCloseKey(hKeySrc);
  if ( hKeyDest )
    RegCloseKey(hKeyDest);
  std::wstring::_Tidy_deallocate(lpSubKey);
  return std::wstring::_Tidy_deallocate(v21);
}

```

## disassembly

```asm
0x1800403e0  push    rbp
0x1800403e2  push    rbx
0x1800403e3  push    rsi
0x1800403e4  push    rdi
0x1800403e5  push    r14
0x1800403e7  lea     rbp, [rsp-2Fh]
0x1800403ec  sub     rsp, 0B0h
0x1800403f3  mov     rax, cs:__security_cookie
0x1800403fa  xor     rax, rsp
0x1800403fd  mov     [rbp+4Fh+var_30], rax
0x180040401  mov     rdi, r9
0x180040404  mov     rsi, r8
0x180040407  mov     rbx, rcx
0x18004040a  mov     r14, [rbp+4Fh+arg_20]
0x18004040e  mov     rax, [rcx]
0x180040411  mov     r9, r8
0x180040414  mov     r8, rdx
0x180040417  lea     rdx, [rbp+4Fh+var_50]
0x18004041b  mov     rax, [rax+58h]
0x18004041f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040424  nop
0x180040425  mov     rax, [rbx]
0x180040428  mov     r9, r14
0x18004042b  mov     r8, rdi
0x18004042e  lea     rdx, [rbp+4Fh+lpSubKey]
0x180040432  mov     rcx, rbx
0x180040435  mov     rax, [rax+58h]
0x180040439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004043e  nop
0x18004043f  mov     [rbp+4Fh+hKeyDest], 0
0x180040447  lea     rdx, [rbp+4Fh+lpSubKey]
0x18004044b  cmp     [rbp+4Fh+var_58], 7
0x180040450  cmova   rdx, [rbp+4Fh+lpSubKey]; lpSubKey
0x180040455  mov     [rsp+0D0h+lpdwDisposition], 0; lpdwDisposition
0x18004045e  lea     rax, [rbp+4Fh+hKeyDest]
0x180040462  mov     [rsp+0D0h+phkResult], rax; phkResult
0x180040467  mov     [rsp+0D0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180040470  mov     [rsp+0D0h+samDesired], 0F003Fh; samDesired
0x180040478  mov     [rsp+0D0h+dwOptions], 0; dwOptions
0x180040480  xor     r9d, r9d; lpClass
0x180040483  xor     r8d, r8d; Reserved
0x180040486  mov     rbx, 0FFFFFFFF80000002h
0x18004048d  mov     rcx, rbx; hKey
0x180040490  call    cs:__imp_RegCreateKeyExW
0x180040496  lea     rdx, [rbp+4Fh+lpSubKey]
0x18004049a  cmp     [rbp+4Fh+var_58], 7
0x18004049f  cmova   rdx, [rbp+4Fh+lpSubKey]
0x1800404a4  mov     rcx, [rbp+57h]; this
0x1800404a8  mov     qword ptr [rsp+0D0h+samDesired], rdx; char *
0x1800404ad  lea     rdi, aWs; "%ws"
0x1800404b4  mov     qword ptr [rsp+0D0h+dwOptions], rdi; unsigned int
0x1800404b9  mov     r9d, eax; char *
0x1800404bc  lea     r8, aOnecoreEnduser_0; "onecore\\enduser\\windowsupdate\\muse\\"...
0x1800404c3  mov     edx, 100h; void *
0x1800404c8  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x1800404cd  nop
0x1800404ce  mov     [rbp+4Fh+hKeySrc], 0
0x1800404d6  lea     rdx, [rbp+4Fh+var_50]
0x1800404da  cmp     [rbp+4Fh+var_38], 7
0x1800404df  cmova   rdx, [rbp+4Fh+var_50]; lpSubKey
0x1800404e4  lea     rax, [rbp+4Fh+hKeySrc]
0x1800404e8  mov     qword ptr [rsp+0D0h+dwOptions], rax; phkResult
0x1800404ed  mov     r9d, 20019h; samDesired
0x1800404f3  xor     r8d, r8d; ulOptions
0x1800404f6  mov     rcx, rbx; hKey
0x1800404f9  call    cs:__imp_RegOpenKeyExW
0x1800404ff  lea     rdx, [rbp+4Fh+var_50]
0x180040503  cmp     [rbp+4Fh+var_38], 7
0x180040508  cmova   rdx, [rbp+4Fh+var_50]
0x18004050d  mov     rcx, [rbp+57h]; this
0x180040511  mov     qword ptr [rsp+0D0h+samDesired], rdx; char *
0x180040516  mov     qword ptr [rsp+0D0h+dwOptions], rdi; unsigned int
0x18004051b  mov     r9d, eax; char *
0x18004051e  lea     r8, aOnecoreEnduser_0; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180040525  mov     edx, 109h; void *
0x18004052a  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x18004052f  mov     r8, [rbp+4Fh+hKeyDest]; hKeyDest
0x180040533  xor     edx, edx; lpSubKey
0x180040535  mov     rcx, [rbp+4Fh+hKeySrc]; hKeySrc
0x180040539  call    cs:__imp_RegCopyTreeW
0x18004053f  cmp     qword ptr [r14+18h], 7
0x180040544  jbe     short loc_180040549
0x180040546  mov     r14, [r14]
0x180040549  cmp     qword ptr [rsi+18h], 7
0x18004054e  jbe     short loc_180040553
0x180040550  mov     rsi, [rsi]
0x180040553  mov     rcx, [rbp+57h]; this
0x180040557  mov     [rsp+0D0h+lpSecurityAttributes], r14
0x18004055c  mov     qword ptr [rsp+0D0h+samDesired], rsi; char *
0x180040561  lea     rdx, aSrcpathWsDestp; "srcPath: %ws destPath: %ws"
0x180040568  mov     qword ptr [rsp+0D0h+dwOptions], rdx; unsigned int
0x18004056d  mov     r9d, eax; char *
0x180040570  lea     r8, aOnecoreEnduser_0; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180040577  mov     edx, 10Fh; void *
0x18004057c  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x180040581  nop
0x180040582  mov     rcx, [rbp+4Fh+hKeySrc]; hKey
0x180040586  test    rcx, rcx
0x180040589  jz      short loc_180040592
0x18004058b  call    cs:__imp_RegCloseKey
0x180040591  nop
0x180040592  mov     rcx, [rbp+4Fh+hKeyDest]; hKey
0x180040596  test    rcx, rcx
0x180040599  jz      short loc_1800405A2
0x18004059b  call    cs:__imp_RegCloseKey
0x1800405a1  nop
0x1800405a2  lea     rcx, [rbp+4Fh+lpSubKey]
0x1800405a6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800405ab  nop
0x1800405ac  lea     rcx, [rbp+4Fh+var_50]
0x1800405b0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800405b5  mov     rcx, [rbp+4Fh+var_30]
0x1800405b9  xor     rcx, rsp; StackCookie
0x1800405bc  call    __security_check_cookie
0x1800405c1  add     rsp, 0B0h
0x1800405c8  pop     r14
0x1800405ca  pop     rdi
0x1800405cb  pop     rsi
0x1800405cc  pop     rbx
0x1800405cd  pop     rbp
0x1800405ce  retn
```
