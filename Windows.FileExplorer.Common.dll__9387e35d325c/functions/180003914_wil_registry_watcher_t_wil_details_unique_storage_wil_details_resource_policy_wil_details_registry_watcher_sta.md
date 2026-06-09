# wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::create(HKEY__ *,ushort const *,bool,wistd::function<void (wil::RegistryChangeKind)> &&)

- ea: `0x180003914`
- end: `0x1800039b7`
- name: `?create@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJPEAUHKEY__@@PEBG_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z`
- size: `163`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009374`

## callees

- `0x180003914`
- `0x1800039c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800039a4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800039a4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000396a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000396a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::create(
        __int64 a1,
        HKEY a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  LSTATUS v6; // eax
  __int64 v7; // r8
  int v8; // ebx
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  hKey = 0;
  v6 = RegCreateKeyExW(a2, &String1, 0, 0, 0, 0x10u, 0, &hKey, 0);
  v8 = v6;
  if ( v6 > 0 )
    v8 = (unsigned __int16)v6 | 0x80070000;
  if ( v8 >= 0 )
    v8 = wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::create_common(
           a1,
           &hKey,
           v7,
           a5);
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180003914  mov     r11, rsp
0x180003917  mov     [r11+8], rbx
0x18000391b  mov     [r11+18h], r8
0x18000391f  push    rdi
0x180003920  sub     rsp, 50h
0x180003924  mov     rax, rdx
0x180003927  mov     rdi, rcx
0x18000392a  mov     qword ptr [r11+18h], 0
0x180003932  mov     qword ptr [r11-18h], 0
0x18000393a  lea     rcx, [r11+18h]
0x18000393e  mov     [r11-20h], rcx
0x180003942  mov     qword ptr [r11-28h], 0
0x18000394a  mov     [rsp+58h+samDesired], 10h; samDesired
0x180003952  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18000395a  xor     r9d, r9d; lpClass
0x18000395d  xor     r8d, r8d; Reserved
0x180003960  lea     rdx, String1; lpSubKey
0x180003967  mov     rcx, rax; hKey
0x18000396a  call    cs:__imp_RegCreateKeyExW
0x180003970  mov     ebx, eax
0x180003972  test    eax, eax
0x180003974  jle     short loc_18000397F
0x180003976  movzx   ebx, ax
0x180003979  or      ebx, 80070000h
0x18000397f  test    ebx, ebx
0x180003981  js      short loc_18000399A
0x180003983  mov     r9, [rsp+58h+arg_20]
0x18000398b  lea     rdx, [rsp+58h+hKey]
0x180003990  mov     rcx, rdi
0x180003993  call    ?create_common@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@AEAAJ$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z; wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::create_common(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)
0x180003998  mov     ebx, eax
0x18000399a  mov     rcx, [rsp+58h+hKey]; hKey
0x18000399f  test    rcx, rcx
0x1800039a2  jz      short loc_1800039AA
0x1800039a4  call    cs:__imp_RegCloseKey
0x1800039aa  mov     eax, ebx
0x1800039ac  mov     rbx, [rsp+58h+arg_0]
0x1800039b1  add     rsp, 50h
0x1800039b5  pop     rdi
0x1800039b6  retn
```
