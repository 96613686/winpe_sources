# wil::make_registry_watcher_nothrow(HKEY__ *,ushort const *,bool,wistd::function<void (wil::RegistryChangeKind)> &&)

- ea: `0x18002334c`
- end: `0x1800233e4`
- name: `?make_registry_watcher_nothrow@wil@@YA?AV?$unique_any_t@V?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@1@PEAUHKEY__@@PEBG_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z`
- size: `152`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001f604`
- `0x18001f998`

## callees

- `0x180021a48`
- `0x18002334c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800233d5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800233d5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800233a0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800233a0`

## pseudocode

```c
wil::details **__fastcall wil::make_registry_watcher_nothrow(
        wil::details **a1,
        __int64 a2,
        const WCHAR *a3,
        __int64 a4,
        __int64 a5)
{
  LSTATUS v6; // eax
  __int64 v7; // r8
  bool v8; // sf
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  *a1 = 0;
  hKey = 0;
  v6 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, a3, 0, 0, 0, 0x10u, 0, &hKey, 0);
  v8 = v6 < 0;
  if ( v6 > 0 )
    v8 = 1;
  if ( !v8 )
    wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::create_common(
      a1,
      &hKey,
      v7,
      a5);
  if ( hKey )
    RegCloseKey(hKey);
  return a1;
}

```

## disassembly

```asm
0x18002334c  mov     rax, rsp
0x18002334f  mov     [rax+10h], rdx
0x180023353  push    rbx
0x180023354  sub     rsp, 50h
0x180023358  mov     rdx, r8; lpSubKey
0x18002335b  mov     rbx, rcx
0x18002335e  mov     qword ptr [rcx], 0
0x180023365  mov     qword ptr [rax+10h], 0
0x18002336d  mov     qword ptr [rax-18h], 0
0x180023375  lea     rcx, [rax+10h]
0x180023379  mov     [rax-20h], rcx
0x18002337d  mov     qword ptr [rax-28h], 0
0x180023385  mov     dword ptr [rax-30h], 10h
0x18002338c  mov     dword ptr [rax-38h], 0
0x180023393  xor     r9d, r9d; lpClass
0x180023396  xor     r8d, r8d; Reserved
0x180023399  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800233a0  call    cs:__imp_RegCreateKeyExW
0x1800233a6  test    eax, eax
0x1800233a8  jle     short loc_1800233B4
0x1800233aa  movzx   eax, ax
0x1800233ad  or      eax, 80070000h
0x1800233b2  test    eax, eax
0x1800233b4  js      short loc_1800233CB
0x1800233b6  mov     r9, [rsp+58h+arg_20]
0x1800233be  lea     rdx, [rsp+58h+hKey]
0x1800233c3  mov     rcx, rbx
0x1800233c6  call    ?create_common@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@AEAAJ$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z; wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::create_common(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)
0x1800233cb  mov     rcx, [rsp+58h+hKey]; hKey
0x1800233d0  test    rcx, rcx
0x1800233d3  jz      short loc_1800233DB
0x1800233d5  call    cs:__imp_RegCloseKey
0x1800233db  mov     rax, rbx
0x1800233de  add     rsp, 50h
0x1800233e2  pop     rbx
0x1800233e3  retn
```
