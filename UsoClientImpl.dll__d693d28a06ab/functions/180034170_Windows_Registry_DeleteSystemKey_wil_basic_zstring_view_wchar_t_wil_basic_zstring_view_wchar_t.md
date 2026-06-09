# Windows::Registry::DeleteSystemKey(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)

- ea: `0x180034170`
- end: `0x180034226`
- name: `?DeleteSystemKey@Registry@Windows@@UEAAXV?$basic_zstring_view@_W@wil@@0@Z`
- size: `182`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18000cde8`
- `0x18000d2a8`

## callees

- `0x180009380`
- `0x180034170`
- `0x18003c020`
- `0x18003df70`
- `0x180056500`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800341c2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800341c2`

## string_xrefs

- `0x1800341f6`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Registry.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Windows::Registry::DeleteSystemKey(__int64 a1, __int128 *a2, __int128 *a3)
{
  const WCHAR *v3; // rdx
  unsigned int v4; // eax
  LPCWSTR *v5; // rdx
  __int128 v6; // [rsp+30h] [rbp-50h] BYREF
  __int128 v7; // [rsp+40h] [rbp-40h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+50h] [rbp-30h] BYREF
  unsigned __int64 v9; // [rsp+68h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  v6 = *a3;
  v7 = *a2;
  Windows::Registry::GetRedirectedRegistryKeyName(a1, lpSubKey, &v7, &v6);
  v3 = (const WCHAR *)lpSubKey;
  if ( v9 > 7 )
    v3 = lpSubKey[0];
  v4 = RegDeleteTreeW(HKEY_LOCAL_MACHINE, v3);
  if ( v4 - 2 > 1 )
  {
    v5 = lpSubKey;
    if ( v9 > 7 )
      v5 = (LPCWSTR *)lpSubKey[0];
    wil::details::in1diag3::Throw_IfWin32ErrorMsg(
      retaddr,
      (void *)0x1A4,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Registry.cpp",
      (const char *)v4,
      (unsigned int)"%ws",
      (const char *)v5);
  }
  std::wstring::~wstring(lpSubKey);
}

```

## disassembly

```asm
0x180034170  push    rbp
0x180034172  mov     rbp, rsp
0x180034175  sub     rsp, 80h
0x18003417c  mov     rax, cs:__security_cookie
0x180034183  xor     rax, rsp
0x180034186  mov     [rbp+var_10], rax
0x18003418a  movups  xmm0, xmmword ptr [r8]
0x18003418e  movdqu  [rbp+var_50], xmm0
0x180034193  movups  xmm1, xmmword ptr [rdx]
0x180034196  movdqu  [rbp+var_40], xmm1
0x18003419b  lea     r9, [rbp+var_50]
0x18003419f  lea     r8, [rbp+var_40]
0x1800341a3  lea     rdx, [rbp+lpSubKey]
0x1800341a7  call    ?GetRedirectedRegistryKeyName@Registry@Windows@@UEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_zstring_view@_W@wil@@0@Z; Windows::Registry::GetRedirectedRegistryKeyName(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x1800341ac  nop
0x1800341ad  lea     rdx, [rbp+lpSubKey]
0x1800341b1  cmp     [rbp+var_18], 7
0x1800341b6  cmova   rdx, [rbp+lpSubKey]; lpSubKey
0x1800341bb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800341c2  call    cs:__imp_RegDeleteTreeW
0x1800341c8  lea     ecx, [rax-2]
0x1800341cb  cmp     ecx, 1
0x1800341ce  jbe     short loc_180034208
0x1800341d0  lea     rdx, [rbp+lpSubKey]
0x1800341d4  cmp     [rbp+var_18], 7
0x1800341d9  cmova   rdx, [rbp+lpSubKey]
0x1800341de  mov     rcx, [rbp+8]; this
0x1800341e2  mov     [rsp+80h+var_58], rdx; char *
0x1800341e7  lea     rdx, aWs; "%ws"
0x1800341ee  mov     qword ptr [rsp+80h+var_60], rdx; unsigned int
0x1800341f3  mov     r9d, eax; char *
0x1800341f6  lea     r8, aCW1SSrcOrchest_2; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1800341fd  mov     edx, 1A4h; void *
0x180034202  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x180034207  nop
0x180034208  lea     rcx, [rbp+lpSubKey]; void *
0x18003420c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180034211  mov     rcx, [rbp+var_10]
0x180034215  xor     rcx, rsp; StackCookie
0x180034218  call    __security_check_cookie
0x18003421d  add     rsp, 80h
0x180034224  pop     rbp
0x180034225  retn
```
