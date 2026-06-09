# Windows::Registry::DeleteSystemValue(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)

- ea: `0x18006e730`
- end: `0x18006e87e`
- name: `?DeleteSystemValue@Registry@Windows@@UEAAXV?$basic_zstring_view@_W@wil@@00@Z`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x1800bfaa4`

## callees

- `0x180011680`
- `0x18006e730`
- `0x180083c20`
- `0x1800855a0`
- `0x1800dd930`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e84f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e84f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18006e801`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18006e801`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006e7a9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006e7a9`

## string_xrefs

- `0x18006e7e7`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Registry.cpp`
- `0x18006e834`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Registry.cpp`

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
0x18006e730  mov     rax, rsp
0x18006e733  push    rbp
0x18006e734  push    rbx
0x18006e735  push    rdi
0x18006e736  lea     rbp, [rax-5Fh]
0x18006e73a  sub     rsp, 0A0h
0x18006e741  movaps  xmmword ptr [rax-28h], xmm6
0x18006e745  mov     rax, cs:__security_cookie
0x18006e74c  xor     rax, rsp
0x18006e74f  mov     qword ptr [rbp+57h+var_28], rax
0x18006e753  movups  xmm6, xmmword ptr [r9]
0x18006e757  movups  xmm0, xmmword ptr [r8]
0x18006e75b  movdqu  [rbp+57h+var_70], xmm0
0x18006e760  movups  xmm1, xmmword ptr [rdx]
0x18006e763  movdqu  [rbp+57h+var_60], xmm1
0x18006e768  lea     r9, [rbp+57h+var_70]
0x18006e76c  lea     r8, [rbp+57h+var_60]
0x18006e770  lea     rdx, [rbp+57h+lpSubKey]
0x18006e774  call    ?GetRedirectedRegistryKeyName@Registry@Windows@@UEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_zstring_view@_W@wil@@0@Z; Windows::Registry::GetRedirectedRegistryKeyName(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x18006e779  nop
0x18006e77a  mov     [rbp+57h+hKey], 0
0x18006e782  lea     rdx, [rbp+57h+lpSubKey]
0x18006e786  cmp     [rbp+57h+var_30], 7
0x18006e78b  cmova   rdx, [rbp+57h+lpSubKey]; lpSubKey
0x18006e790  lea     rax, [rbp+57h+hKey]
0x18006e794  mov     [rsp+0B0h+phkResult], rax; phkResult
0x18006e799  mov     r9d, 20006h; samDesired
0x18006e79f  xor     r8d, r8d; ulOptions
0x18006e7a2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006e7a9  call    cs:__imp_RegOpenKeyExW
0x18006e7af  lea     ecx, [rax-2]
0x18006e7b2  cmp     ecx, 1
0x18006e7b5  jbe     loc_18006E846
0x18006e7bb  lea     rdx, [rbp+57h+lpSubKey]
0x18006e7bf  cmp     [rbp+57h+var_30], 7
0x18006e7c4  cmova   rdx, [rbp+57h+lpSubKey]
0x18006e7c9  mov     rcx, [rbp+5Fh]; this
0x18006e7cd  movq    qword ptr [rsp+30h], xmm6
0x18006e7d3  mov     [rsp+0B0h+var_88], rdx; char *
0x18006e7d8  lea     rdi, aWsWs; "%ws[%ws]"
0x18006e7df  mov     [rsp+0B0h+phkResult], rdi; unsigned int
0x18006e7e4  mov     r9d, eax; char *
0x18006e7e7  lea     r8, aCW1SSrcOrchest_32; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18006e7ee  mov     edx, 18Bh; void *
0x18006e7f3  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x18006e7f8  movq    rdx, xmm6; lpValueName
0x18006e7fd  mov     rcx, [rbp+57h+hKey]; hKey
0x18006e801  call    cs:__imp_RegDeleteValueW
0x18006e807  lea     ecx, [rax-2]
0x18006e80a  cmp     ecx, 1
0x18006e80d  jbe     short loc_18006E846
0x18006e80f  lea     rdx, [rbp+57h+lpSubKey]
0x18006e813  cmp     [rbp+57h+var_30], 7
0x18006e818  cmova   rdx, [rbp+57h+lpSubKey]
0x18006e81d  mov     rcx, [rbp+5Fh]; this
0x18006e821  movq    qword ptr [rsp+30h], xmm6
0x18006e827  mov     [rsp+0B0h+var_88], rdx; char *
0x18006e82c  mov     [rsp+0B0h+phkResult], rdi; unsigned int
0x18006e831  mov     r9d, eax; char *
0x18006e834  lea     r8, aCW1SSrcOrchest_32; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18006e83b  mov     edx, 193h; void *
0x18006e840  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x18006e845  nop
0x18006e846  mov     rcx, [rbp+57h+hKey]; hKey
0x18006e84a  test    rcx, rcx
0x18006e84d  jz      short loc_18006E856
0x18006e84f  call    cs:__imp_RegCloseKey
0x18006e855  nop
0x18006e856  lea     rcx, [rbp+57h+lpSubKey]; void *
0x18006e85a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006e85f  mov     rcx, qword ptr [rbp+57h+var_28]
0x18006e863  xor     rcx, rsp; StackCookie
0x18006e866  call    __security_check_cookie
0x18006e86b  movaps  xmm6, [rsp+0B0h+var_28+8]
0x18006e873  add     rsp, 0A0h
0x18006e87a  pop     rdi
0x18006e87b  pop     rbx
0x18006e87c  pop     rbp
0x18006e87d  retn
```
