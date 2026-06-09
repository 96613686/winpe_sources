# wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::create(HKEY__ *,wchar_t const *,bool,wistd::function<void (wil::RegistryChangeKind)> &&)

- ea: `0x180009184`
- end: `0x180009256`
- name: `?create@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJPEAUHKEY__@@PEB_W_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z`
- size: `210`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001eea8`

## callees

- `0x180009184`
- `0x18000bc58`
- `0x18000c15c`
- `0x18000d2a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009211`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009211`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800091ee`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800091ee`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::create(
        __int64 a1,
        __int64 a2,
        const WCHAR *a3,
        __int64 a4,
        __int64 a5)
{
  LSTATUS v6; // eax
  __int64 v7; // r8
  int common; // ebx
  HKEY hKey; // [rsp+50h] [rbp-18h] BYREF

  hKey = 0;
  v6 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, a3, 0, 0, 0, 0x10u, 0, &hKey, 0);
  common = v6;
  if ( v6 > 0 )
    common = (unsigned __int16)v6 | 0x80070000;
  if ( common >= 0 )
  {
    common = wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::create_common(
               a1,
               (__int64)&hKey,
               v7,
               a5);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  }
  else if ( hKey )
  {
    RegCloseKey(hKey);
  }
  return (unsigned int)common;
}

```

## disassembly

```asm
0x180009184  mov     r11, rsp
0x180009187  mov     [r11+10h], rbx
0x18000918b  mov     [r11+20h], rsi
0x18000918f  push    rdi
0x180009190  sub     rsp, 60h
0x180009194  mov     rax, cs:__security_cookie
0x18000919b  xor     rax, rsp
0x18000919e  mov     [rsp+68h+var_10], rax
0x1800091a3  mov     rdx, r8; lpSubKey
0x1800091a6  mov     rdi, rcx
0x1800091a9  mov     rsi, [rsp+68h+arg_20]
0x1800091b1  mov     qword ptr [r11-18h], 0
0x1800091b9  mov     qword ptr [r11-28h], 0
0x1800091c1  lea     rcx, [r11-18h]
0x1800091c5  mov     [r11-30h], rcx
0x1800091c9  mov     qword ptr [r11-38h], 0
0x1800091d1  mov     [rsp+68h+samDesired], 10h; samDesired
0x1800091d9  mov     [rsp+68h+dwOptions], 0; dwOptions
0x1800091e1  xor     r9d, r9d; lpClass
0x1800091e4  xor     r8d, r8d; Reserved
0x1800091e7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800091ee  call    cs:__imp_RegCreateKeyExW
0x1800091f4  mov     ebx, eax
0x1800091f6  test    eax, eax
0x1800091f8  jle     short loc_180009203
0x1800091fa  movzx   ebx, ax
0x1800091fd  or      ebx, 80070000h
0x180009203  test    ebx, ebx
0x180009205  jns     short loc_180009219
0x180009207  mov     rcx, [rsp+68h+hKey]; hKey
0x18000920c  test    rcx, rcx
0x18000920f  jz      short loc_180009235
0x180009211  call    cs:__imp_RegCloseKey
0x180009217  jmp     short loc_180009235
0x180009219  mov     r9, rsi
0x18000921c  lea     rdx, [rsp+68h+hKey]
0x180009221  mov     rcx, rdi
0x180009224  call    ?create_common@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@AEAAJ$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z; wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::create_common(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)
0x180009229  mov     ebx, eax
0x18000922b  lea     rcx, [rsp+68h+hKey]
0x180009230  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180009235  mov     eax, ebx
0x180009237  mov     rcx, [rsp+68h+var_10]
0x18000923c  xor     rcx, rsp; StackCookie
0x18000923f  call    __security_check_cookie
0x180009244  lea     r11, [rsp+68h+var_8]
0x180009249  mov     rbx, [r11+18h]
0x18000924d  mov     rsi, [r11+28h]
0x180009251  mov     rsp, r11
0x180009254  pop     rdi
0x180009255  retn
```
