# SyncRootManagerSettingsProviderHelpers::SubstituteHostUserSidWithContainerUserSidHelper(void *,ushort const *)

- ea: `0x180034de8`
- end: `0x18003500a`
- name: `?SubstituteHostUserSidWithContainerUserSidHelper@SyncRootManagerSettingsProviderHelpers@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEAXPEBG@Z`
- size: `546`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18006f5c0`

## callees

- `0x180004d6c`
- `0x180015fa0`
- `0x180017a98`
- `0x180022f7c`
- `0x18002a780`
- `0x1800348e8`
- `0x180034de8`
- `0x1800356d8`
- `0x180035c58`
- `0x180036110`
- `0x180037780`
- `0x180059c98`
- `0x18006e1d0`
- `0x18006e884`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180034f14`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180034f14`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180034f3e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180034f3e`

## string_xrefs

- `0x180034fa4`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\SyncRootManagerSettingsProviderHelpers.h`
- `0x180034fb9`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\SyncRootManagerSettingsProviderHelpers.h`
- `0x180034fce`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\SyncRootManagerSettingsProviderHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall SyncRootManagerSettingsProviderHelpers::SubstituteHostUserSidWithContainerUserSidHelper(
        _QWORD *a1,
        void *a2,
        const unsigned __int16 *a3)
{
  unsigned __int64 i; // rsi
  __int64 v6; // rdi
  __int64 v7; // r14
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rax
  LPCWSTR *v11; // rcx
  const WCHAR *v12; // r8
  unsigned int ValueW; // eax
  const WCHAR *v14; // rdx
  unsigned int v15; // eax
  int v16; // eax
  unsigned int pdwType; // [rsp+20h] [rbp-E0h]
  HKEY hkey; // [rsp+40h] [rbp-C0h] BYREF
  int v20; // [rsp+48h] [rbp-B8h]
  DWORD pcbData[2]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v22[4]; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR lpValue[3]; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int64 v24; // [rsp+90h] [rbp-70h]
  unsigned __int16 pvData[264]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+1E8h]

  v22[3] = a1;
  SyncRootManagerSettingsProviderHelpers::GetSyncRootNamesUnderGivenUserSid((__int64)a1, a2);
  v20 = 1;
  for ( i = 0; i < (__int64)(a1[1] - *a1) >> 5; ++i )
  {
    hkey = 0;
    SyncRootManagerSettingsProviderHelpers::GetUserSyncRootsSubkey(*a1 + 32 * i, &hkey);
    *(_QWORD *)pcbData = hkey;
    SyncRootManagerSettingsProviderHelpers::GetRegistryValues(v22, pcbData);
    v6 = v22[0];
    v7 = v22[1];
    while ( v6 != v7 )
    {
      std::wstring::wstring(lpValue, v6);
      v10 = std::_WChar_traits<unsigned short>::length(L"(Default)", v8, v9);
      v11 = lpValue;
      if ( v24 > 7 )
        v11 = (LPCWSTR *)lpValue[0];
      if ( !(unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v11, lpValue[2], L"(Default)", v10) )
      {
        pcbData[0] = 520;
        v12 = (const WCHAR *)lpValue;
        if ( v24 > 7 )
          v12 = lpValue[0];
        ValueW = RegGetValueW(hkey, 0, v12, 2u, 0, pvData, pcbData);
        if ( ValueW )
          wil::details::in1diag3::_Throw_Win32(
            retaddr,
            (void *)0x152,
            (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\SyncRootManagerSettingsProviderHelpers.h",
            (const char *)ValueW,
            pdwType);
        v14 = (const WCHAR *)lpValue;
        if ( v24 > 7 )
          v14 = lpValue[0];
        v15 = RegDeleteValueW(hkey, v14);
        if ( v15 )
          wil::details::in1diag3::_Throw_Win32(
            retaddr,
            (void *)0x153,
            (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\SyncRootManagerSettingsProviderHelpers.h",
            (const char *)v15,
            pdwType);
        v16 = SHRegSetString(hkey, 0, a3, pvData);
        if ( v16 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x154,
            (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\SyncRootManagerSettingsProviderHelpers.h",
            (const char *)(unsigned int)v16,
            pdwType);
      }
      std::wstring::_Tidy_deallocate(lpValue);
      v6 += 32;
    }
    std::vector<std::wstring>::_Tidy(v22);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  }
  return a1;
}

```

## disassembly

```asm
0x180034de8  mov     [rsp-8+arg_18], rbx
0x180034ded  push    rbp
0x180034dee  push    rsi
0x180034def  push    rdi
0x180034df0  push    r14
0x180034df2  push    r15
0x180034df4  lea     rbp, [rsp-1C0h]
0x180034dfc  sub     rsp, 2C0h
0x180034e03  mov     rax, cs:__security_cookie
0x180034e0a  xor     rax, rsp
0x180034e0d  mov     [rbp+1E0h+var_30], rax
0x180034e14  mov     r15, r8
0x180034e17  mov     rbx, rcx
0x180034e1a  mov     [rsp+2E0h+var_270], rcx
0x180034e1f  mov     [rsp+2E0h+var_298], 0
0x180034e27  call    ?GetSyncRootNamesUnderGivenUserSid@SyncRootManagerSettingsProviderHelpers@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEAX@Z; SyncRootManagerSettingsProviderHelpers::GetSyncRootNamesUnderGivenUserSid(void *)
0x180034e2c  mov     [rsp+2E0h+var_298], 1
0x180034e34  xor     esi, esi
0x180034e36  mov     rax, [rbx+8]
0x180034e3a  sub     rax, [rbx]
0x180034e3d  sar     rax, 5
0x180034e41  cmp     rsi, rax
0x180034e44  jnb     loc_180034FE0
0x180034e4a  mov     [rsp+2E0h+hkey], 0
0x180034e53  mov     rcx, rsi
0x180034e56  shl     rcx, 5
0x180034e5a  add     rcx, [rbx]
0x180034e5d  lea     rdx, [rsp+2E0h+hkey]
0x180034e62  call    ?GetUserSyncRootsSubkey@SyncRootManagerSettingsProviderHelpers@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; SyncRootManagerSettingsProviderHelpers::GetUserSyncRootsSubkey(std::wstring const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &)
0x180034e67  mov     rax, [rsp+2E0h+hkey]
0x180034e6c  mov     qword ptr [rsp+2E0h+var_290], rax
0x180034e71  lea     rdx, [rsp+2E0h+var_290]
0x180034e76  lea     rcx, [rsp+2E0h+var_288]
0x180034e7b  call    ?GetRegistryValues@SyncRootManagerSettingsProviderHelpers@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEBQEAUHKEY__@@@Z; SyncRootManagerSettingsProviderHelpers::GetRegistryValues(HKEY__ * const &)
0x180034e80  nop
0x180034e81  mov     rdi, [rsp+2E0h+var_288]
0x180034e86  mov     r14, [rsp+2E0h+var_280]
0x180034e8b  jmp     loc_180034F7B
0x180034e90  mov     rdx, rdi
0x180034e93  lea     rcx, [rsp+2E0h+lpValue]
0x180034e98  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180034e9d  nop
0x180034e9e  lea     rcx, aDefault; "(Default)"
0x180034ea5  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180034eaa  lea     rcx, [rsp+2E0h+lpValue]
0x180034eaf  cmp     [rbp+1E0h+var_250], 7
0x180034eb4  cmova   rcx, [rsp+2E0h+lpValue]
0x180034eba  mov     r9, rax
0x180034ebd  lea     r8, aDefault; "(Default)"
0x180034ec4  mov     rdx, [rbp+1E0h+var_258]
0x180034ec8  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180034ecd  test    al, al
0x180034ecf  jnz     loc_180034F6D
0x180034ed5  mov     [rsp+2E0h+var_290], 208h
0x180034edd  lea     r8, [rsp+2E0h+lpValue]
0x180034ee2  cmp     [rbp+1E0h+var_250], 7
0x180034ee7  cmova   r8, [rsp+2E0h+lpValue]; lpValue
0x180034eed  lea     rax, [rsp+2E0h+var_290]
0x180034ef2  mov     [rsp+2E0h+pcbData], rax; pcbData
0x180034ef7  lea     rax, [rbp+1E0h+var_240]
0x180034efb  mov     [rsp+2E0h+pvData], rax; pvData
0x180034f00  mov     [rsp+2E0h+pdwType], 0; unsigned int
0x180034f09  xor     edx, edx; lpSubKey
0x180034f0b  lea     r9d, [rdx+2]; dwFlags
0x180034f0f  mov     rcx, [rsp+2E0h+hkey]; hkey
0x180034f14  call    cs:__imp_RegGetValueW
0x180034f1a  mov     rcx, [rbp+1E8h]; this
0x180034f21  test    eax, eax
0x180034f23  jnz     loc_180034FCB
0x180034f29  lea     rdx, [rsp+2E0h+lpValue]
0x180034f2e  cmp     [rbp+1E0h+var_250], 7
0x180034f33  cmova   rdx, [rsp+2E0h+lpValue]; lpValueName
0x180034f39  mov     rcx, [rsp+2E0h+hkey]; hKey
0x180034f3e  call    cs:__imp_RegDeleteValueW
0x180034f44  mov     rcx, [rbp+1E8h]; this
0x180034f4b  test    eax, eax
0x180034f4d  jnz     short loc_180034FB6
0x180034f4f  lea     r9, [rbp+1E0h+var_240]; unsigned __int16 *
0x180034f53  mov     r8, r15; unsigned __int16 *
0x180034f56  xor     edx, edx; unsigned __int16 *
0x180034f58  mov     rcx, [rsp+2E0h+hkey]; HKEY
0x180034f5d  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x180034f62  mov     rcx, [rbp+1E8h]; this
0x180034f69  test    eax, eax
0x180034f6b  js      short loc_180034FA1
0x180034f6d  lea     rcx, [rsp+2E0h+lpValue]
0x180034f72  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180034f77  add     rdi, 20h ; ' '
0x180034f7b  cmp     rdi, r14
0x180034f7e  jnz     loc_180034E90
0x180034f84  lea     rcx, [rsp+2E0h+var_288]
0x180034f89  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180034f8e  nop
0x180034f8f  lea     rcx, [rsp+2E0h+hkey]
0x180034f94  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180034f99  inc     rsi
0x180034f9c  jmp     loc_180034E36
0x180034fa1  mov     r9d, eax; char *
0x180034fa4  lea     r8, aShellcommonShe_9; "shellcommon\\shell\\fileexplorer\\windo"...
0x180034fab  mov     edx, 154h; void *
0x180034fb0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180034fb6  mov     r9d, eax; char *
0x180034fb9  lea     r8, aShellcommonShe_9; "shellcommon\\shell\\fileexplorer\\windo"...
0x180034fc0  mov     edx, 153h; void *
0x180034fc5  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180034fcb  mov     r9d, eax; char *
0x180034fce  lea     r8, aShellcommonShe_9; "shellcommon\\shell\\fileexplorer\\windo"...
0x180034fd5  mov     edx, 152h; void *
0x180034fda  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180034fe0  mov     rax, rbx
0x180034fe3  mov     rcx, [rbp+1E0h+var_30]
0x180034fea  xor     rcx, rsp; StackCookie
0x180034fed  call    __security_check_cookie
0x180034ff2  mov     rbx, [rsp+2E0h+arg_18]
0x180034ffa  add     rsp, 2C0h
0x180035001  pop     r15
0x180035003  pop     r14
0x180035005  pop     rdi
0x180035006  pop     rsi
0x180035007  pop     rbp
0x180035008  retn
```
