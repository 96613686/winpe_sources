# PerFolderRootCache::Remove_NoLock(std::shared_ptr<PerFolderRootInfo const> const &)

- ea: `0x1800595b8`
- end: `0x180059667`
- name: `?Remove_NoLock@PerFolderRootCache@@AEAAXAEBV?$shared_ptr@$$CBUPerFolderRootInfo@@@std@@@Z`
- size: `175`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180059414`
- `0x18005951c`

## callees

- `0x180004d6c`
- `0x18002037c`
- `0x1800595b8`
- `0x180059c98`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005961a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005961a`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18005963b`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18005963b`

## string_xrefs

- `0x180059655`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\perfolderrootmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PerFolderRootCache::Remove_NoLock(__int64 a1, const WCHAR **a2)
{
  unsigned int v3; // eax
  const WCHAR *v4; // rdx
  DWORD dwOptions; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF

  _InterlockedIncrement((volatile signed __int32 *)(a1 + 104));
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v3 = RegCreateKeyExW(
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\PerFolderRoots",
         0,
         0,
         0,
         0x20006u,
         0,
         &hKey,
         0);
  if ( v3 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x15C,
      (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\perfolderrootmanager.cpp",
      (const char *)v3,
      dwOptions);
  v4 = *a2;
  if ( *((_QWORD *)*a2 + 3) > 7u )
    v4 = *(const WCHAR **)v4;
  RegDeleteKeyW(hKey, v4);
  return wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
}

```

## disassembly

```asm
0x1800595b8  push    rbx
0x1800595ba  sub     rsp, 50h
0x1800595be  mov     rbx, rdx
0x1800595c1  lock inc dword ptr [rcx+68h]
0x1800595c5  mov     [rsp+58h+hKey], 0
0x1800595ce  xor     edx, edx
0x1800595d0  lea     rcx, [rsp+58h+hKey]
0x1800595d5  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800595da  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x1800595e3  lea     rax, [rsp+58h+hKey]
0x1800595e8  mov     [rsp+58h+phkResult], rax; phkResult
0x1800595ed  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800595f6  mov     [rsp+58h+samDesired], 20006h; samDesired
0x1800595fe  mov     [rsp+58h+dwOptions], 0; unsigned int
0x180059606  xor     r9d, r9d; lpClass
0x180059609  xor     r8d, r8d; Reserved
0x18005960c  lea     rdx, ?PerFolderRegKey@Details@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180059613  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18005961a  call    cs:__imp_RegCreateKeyExW
0x180059620  mov     rcx, [rsp+58h]; this
0x180059625  test    eax, eax
0x180059627  jnz     short loc_180059652
0x180059629  mov     rdx, [rbx]
0x18005962c  cmp     qword ptr [rdx+18h], 7
0x180059631  jbe     short loc_180059636
0x180059633  mov     rdx, [rdx]; lpSubKey
0x180059636  mov     rcx, [rsp+58h+hKey]; hKey
0x18005963b  call    cs:__imp_RegDeleteKeyW
0x180059641  nop
0x180059642  lea     rcx, [rsp+58h+hKey]
0x180059647  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005964c  add     rsp, 50h
0x180059650  pop     rbx
0x180059651  retn
0x180059652  mov     r9d, eax; char *
0x180059655  lea     r8, aShellcommonShe_10; "shellcommon\\shell\\fileexplorer\\windo"...
0x18005965c  mov     edx, 15Ch; void *
0x180059661  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
