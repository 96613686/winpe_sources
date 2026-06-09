# _lambda_ea9c6a719f4a9bb818bf1c421ccbcdfc_::operator()(void)

- ea: `0x180012e64`
- end: `0x180012f94`
- name: `??R_lambda_ea9c6a719f4a9bb818bf1c421ccbcdfc_@@QEBA@XZ`
- size: `304`
- prototype: `__int64 __fastcall(bool **, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800133a4`

## callees

- `0x1800033d0`
- `0x180012654`
- `0x180012e64`
- `0x18001982c`
- `0x18001d02c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180012f4b`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180012f4b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012ed9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012ed9`

## pseudocode

```c
__int64 __fastcall _lambda_ea9c6a719f4a9bb818bf1c421ccbcdfc_::operator()(bool **a1, const unsigned __int16 **a2)
{
  int SyncRootManagerRegistryLocation; // eax
  unsigned int v4; // ebx
  unsigned int v5; // eax
  unsigned int v6; // r8d
  __int64 v7; // rdx
  int phkResult; // [rsp+20h] [rbp-48h]
  unsigned int phkResulta; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  DWORD cSubKeys; // [rsp+78h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+18h] BYREF
  LPCWSTR lpSubKey; // [rsp+88h] [rbp+20h] BYREF

  lpSubKey = 0;
  SyncRootManagerRegistryLocation = Windows::Internal::SyncRootHelpers::GetSyncRootManagerRegistryLocation(
                                      (Windows::Internal::SyncRootHelpers *)&lpSubKey,
                                      a2);
  v4 = SyncRootManagerRegistryLocation;
  if ( SyncRootManagerRegistryLocation >= 0 )
  {
    hKey = 0;
    v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20119u, &hKey);
    if ( v5 )
    {
      v7 = 62;
    }
    else
    {
      cSubKeys = 0;
      v5 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
      if ( !v5 )
      {
        v4 = 0;
        **a1 = cSubKeys != 0;
        goto LABEL_9;
      }
      v7 = 66;
    }
    v4 = wil::details::in1diag3::Return_Win32(retaddr, (void *)v7, v6, (const char *)v5, phkResulta);
LABEL_9:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v4;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x3B,
    (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\StateSepUtil.h",
    (const char *)(unsigned int)SyncRootManagerRegistryLocation,
    phkResult);
  return v4;
}

```

## disassembly

```asm
0x180012e64  mov     rax, rsp
0x180012e67  mov     [rax+8], rbx
0x180012e6b  push    rdi
0x180012e6c  sub     rsp, 60h
0x180012e70  mov     rdi, rcx
0x180012e73  mov     qword ptr [rax+20h], 0
0x180012e7b  lea     rcx, [rax+20h]; this
0x180012e7f  call    ?GetSyncRootManagerRegistryLocation@SyncRootHelpers@Internal@Windows@@YAJPEAPEBG@Z; Windows::Internal::SyncRootHelpers::GetSyncRootManagerRegistryLocation(ushort const * *)
0x180012e84  mov     ebx, eax
0x180012e86  test    eax, eax
0x180012e88  jns     short loc_180012EA8
0x180012e8a  mov     rcx, [rsp+68h]; this
0x180012e8f  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180012e96  mov     r9d, eax; char *
0x180012e99  mov     edx, 3Bh ; ';'; void *
0x180012e9e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012ea3  jmp     loc_180012F87
0x180012ea8  mov     rdx, [rsp+68h+lpSubKey]; lpSubKey
0x180012eb0  lea     rax, [rsp+68h+hKey]
0x180012eb8  mov     r9d, 20119h; samDesired
0x180012ebe  mov     [rsp+68h+phkResult], rax; phkResult
0x180012ec3  xor     r8d, r8d; ulOptions
0x180012ec6  mov     [rsp+68h+hKey], 0
0x180012ed2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180012ed9  call    cs:__imp_RegOpenKeyExW
0x180012edf  test    eax, eax
0x180012ee1  jz      short loc_180012EEA
0x180012ee3  mov     edx, 3Eh ; '>'
0x180012ee8  jmp     short loc_180012F5A
0x180012eea  mov     rcx, [rsp+68h+hKey]; hKey
0x180012ef2  lea     rax, [rsp+68h+cSubKeys]
0x180012ef7  mov     [rsp+68h+lpftLastWriteTime], 0; lpftLastWriteTime
0x180012f00  xor     r9d, r9d; lpReserved
0x180012f03  mov     [rsp+68h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x180012f0c  xor     r8d, r8d; lpcchClass
0x180012f0f  mov     [rsp+68h+lpcbMaxValueLen], 0; lpcbMaxValueLen
0x180012f18  xor     edx, edx; lpClass
0x180012f1a  mov     [rsp+68h+lpcbMaxValueNameLen], 0; lpcbMaxValueNameLen
0x180012f23  mov     [rsp+68h+lpcValues], 0; lpcValues
0x180012f2c  mov     [rsp+68h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x180012f35  mov     [rsp+68h+lpcbMaxSubKeyLen], 0; lpcbMaxSubKeyLen
0x180012f3e  mov     [rsp+68h+phkResult], rax; unsigned int
0x180012f43  mov     [rsp+68h+cSubKeys], 0
0x180012f4b  call    cs:__imp_RegQueryInfoKeyW
0x180012f51  test    eax, eax
0x180012f53  jz      short loc_180012F6B
0x180012f55  mov     edx, 42h ; 'B'; void *
0x180012f5a  mov     rcx, [rsp+68h]; this
0x180012f5f  mov     r9d, eax; char *
0x180012f62  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180012f67  mov     ebx, eax
0x180012f69  jmp     short loc_180012F7A
0x180012f6b  cmp     [rsp+68h+cSubKeys], 0
0x180012f70  mov     rax, [rdi]
0x180012f73  setnbe  cl
0x180012f76  xor     ebx, ebx
0x180012f78  mov     [rax], cl
0x180012f7a  lea     rcx, [rsp+68h+hKey]
0x180012f82  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180012f87  mov     eax, ebx
0x180012f89  mov     rbx, [rsp+68h+arg_0]
0x180012f8e  add     rsp, 60h
0x180012f92  pop     rdi
0x180012f93  retn
```
