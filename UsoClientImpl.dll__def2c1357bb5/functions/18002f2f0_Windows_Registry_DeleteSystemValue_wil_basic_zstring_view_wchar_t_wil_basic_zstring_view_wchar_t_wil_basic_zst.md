# Windows::Registry::DeleteSystemValue(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)

- ea: `0x18002f2f0`
- end: `0x18002f43e`
- name: `?DeleteSystemValue@Registry@Windows@@UEAAXV?$basic_zstring_view@_W@wil@@00@Z`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x1800143e8`

## callees

- `0x180009380`
- `0x18002f2f0`
- `0x18003c020`
- `0x18003df70`
- `0x180056500`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f40f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f40f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f369`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f369`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002f3c1`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002f3c1`

## string_xrefs

- `0x18002f3a7`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Registry.cpp`
- `0x18002f3f4`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Registry.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Windows::Registry::DeleteSystemValue(__int64 a1, __int128 *a2, __int128 *a3, __int128 *a4)
{
  __int128 v4; // xmm6
  const WCHAR *v5; // rdx
  unsigned int v6; // eax
  LPCWSTR *v7; // rdx
  unsigned int v8; // eax
  LPCWSTR *v9; // rdx
  __int128 v10; // [rsp+48h] [rbp-19h] BYREF
  __int128 v11; // [rsp+58h] [rbp-9h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+7h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+70h] [rbp+Fh] BYREF
  unsigned __int64 v14; // [rsp+88h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+C0h] [rbp+5Fh]

  v4 = *a4;
  v10 = *a3;
  v11 = *a2;
  Windows::Registry::GetRedirectedRegistryKeyName(a1, lpSubKey, &v11, &v10);
  hKey = 0;
  v5 = (const WCHAR *)lpSubKey;
  if ( v14 > 7 )
    v5 = lpSubKey[0];
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 0x20006u, &hKey);
  if ( v6 - 2 > 1 )
  {
    v7 = lpSubKey;
    if ( v14 > 7 )
      v7 = (LPCWSTR *)lpSubKey[0];
    wil::details::in1diag3::Throw_IfWin32ErrorMsg(
      retaddr,
      (void *)0x18B,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Registry.cpp",
      (const char *)v6,
      (unsigned int)"%ws[%ws]",
      (const char *)v7,
      (_QWORD)v4);
    v8 = RegDeleteValueW(hKey, (LPCWSTR)v4);
    if ( v8 - 2 > 1 )
    {
      v9 = lpSubKey;
      if ( v14 > 7 )
        v9 = (LPCWSTR *)lpSubKey[0];
      wil::details::in1diag3::Throw_IfWin32ErrorMsg(
        retaddr,
        (void *)0x193,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Registry.cpp",
        (const char *)v8,
        (unsigned int)"%ws[%ws]",
        (const char *)v9,
        (_QWORD)v4);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  std::wstring::~wstring(lpSubKey);
}

```

## disassembly

```asm
0x18002f2f0  mov     rax, rsp
0x18002f2f3  push    rbp
0x18002f2f4  push    rbx
0x18002f2f5  push    rdi
0x18002f2f6  lea     rbp, [rax-5Fh]
0x18002f2fa  sub     rsp, 0A0h
0x18002f301  movaps  xmmword ptr [rax-28h], xmm6
0x18002f305  mov     rax, cs:__security_cookie
0x18002f30c  xor     rax, rsp
0x18002f30f  mov     qword ptr [rbp+57h+var_28], rax
0x18002f313  movups  xmm6, xmmword ptr [r9]
0x18002f317  movups  xmm0, xmmword ptr [r8]
0x18002f31b  movdqu  [rbp+57h+var_70], xmm0
0x18002f320  movups  xmm1, xmmword ptr [rdx]
0x18002f323  movdqu  [rbp+57h+var_60], xmm1
0x18002f328  lea     r9, [rbp+57h+var_70]
0x18002f32c  lea     r8, [rbp+57h+var_60]
0x18002f330  lea     rdx, [rbp+57h+lpSubKey]
0x18002f334  call    ?GetRedirectedRegistryKeyName@Registry@Windows@@UEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_zstring_view@_W@wil@@0@Z; Windows::Registry::GetRedirectedRegistryKeyName(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x18002f339  nop
0x18002f33a  mov     [rbp+57h+hKey], 0
0x18002f342  lea     rdx, [rbp+57h+lpSubKey]
0x18002f346  cmp     [rbp+57h+var_30], 7
0x18002f34b  cmova   rdx, [rbp+57h+lpSubKey]; lpSubKey
0x18002f350  lea     rax, [rbp+57h+hKey]
0x18002f354  mov     [rsp+0B0h+phkResult], rax; phkResult
0x18002f359  mov     r9d, 20006h; samDesired
0x18002f35f  xor     r8d, r8d; ulOptions
0x18002f362  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002f369  call    cs:__imp_RegOpenKeyExW
0x18002f36f  lea     ecx, [rax-2]
0x18002f372  cmp     ecx, 1
0x18002f375  jbe     loc_18002F406
0x18002f37b  lea     rdx, [rbp+57h+lpSubKey]
0x18002f37f  cmp     [rbp+57h+var_30], 7
0x18002f384  cmova   rdx, [rbp+57h+lpSubKey]
0x18002f389  mov     rcx, [rbp+5Fh]; this
0x18002f38d  movq    qword ptr [rsp+30h], xmm6
0x18002f393  mov     [rsp+0B0h+var_88], rdx; char *
0x18002f398  lea     rdi, aWsWs_0; "%ws[%ws]"
0x18002f39f  mov     [rsp+0B0h+phkResult], rdi; unsigned int
0x18002f3a4  mov     r9d, eax; char *
0x18002f3a7  lea     r8, aCW1SSrcOrchest_2; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18002f3ae  mov     edx, 18Bh; void *
0x18002f3b3  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x18002f3b8  movq    rdx, xmm6; lpValueName
0x18002f3bd  mov     rcx, [rbp+57h+hKey]; hKey
0x18002f3c1  call    cs:__imp_RegDeleteValueW
0x18002f3c7  lea     ecx, [rax-2]
0x18002f3ca  cmp     ecx, 1
0x18002f3cd  jbe     short loc_18002F406
0x18002f3cf  lea     rdx, [rbp+57h+lpSubKey]
0x18002f3d3  cmp     [rbp+57h+var_30], 7
0x18002f3d8  cmova   rdx, [rbp+57h+lpSubKey]
0x18002f3dd  mov     rcx, [rbp+5Fh]; this
0x18002f3e1  movq    qword ptr [rsp+30h], xmm6
0x18002f3e7  mov     [rsp+0B0h+var_88], rdx; char *
0x18002f3ec  mov     [rsp+0B0h+phkResult], rdi; unsigned int
0x18002f3f1  mov     r9d, eax; char *
0x18002f3f4  lea     r8, aCW1SSrcOrchest_2; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18002f3fb  mov     edx, 193h; void *
0x18002f400  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x18002f405  nop
0x18002f406  mov     rcx, [rbp+57h+hKey]; hKey
0x18002f40a  test    rcx, rcx
0x18002f40d  jz      short loc_18002F416
0x18002f40f  call    cs:__imp_RegCloseKey
0x18002f415  nop
0x18002f416  lea     rcx, [rbp+57h+lpSubKey]; void *
0x18002f41a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002f41f  mov     rcx, qword ptr [rbp+57h+var_28]
0x18002f423  xor     rcx, rsp; StackCookie
0x18002f426  call    __security_check_cookie
0x18002f42b  movaps  xmm6, [rsp+0B0h+var_28+8]
0x18002f433  add     rsp, 0A0h
0x18002f43a  pop     rdi
0x18002f43b  pop     rbx
0x18002f43c  pop     rbp
0x18002f43d  retn
```
