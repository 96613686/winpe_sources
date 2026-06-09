# wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create(HKEY__ *,ushort const *,bool,wistd::function<void (wil::RegistryChangeKind)> &&)

- ea: `0x180020398`
- end: `0x18002046e`
- name: `?create@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXPEAUHKEY__@@PEBG_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180021c3c`

## callees

- `0x180010920`
- `0x18001fb98`
- `0x180020398`
- `0x180020474`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800203ec`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800203ec`

## string_xrefs

- `0x180020410`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x180020446`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create(
        __int64 a1,
        HKEY a2,
        const WCHAR *a3,
        char a4,
        __int64 a5)
{
  int Key; // eax
  bool v8; // sf
  int common; // eax
  DWORD dwOptions; // [rsp+20h] [rbp-48h]
  HKEY v12[3]; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v12[0] = 0;
  Key = RegCreateKeyExW(a2, a3, 0, 0, 0, 0x10u, 0, v12, 0);
  v8 = Key < 0;
  if ( Key > 0 )
  {
    Key = (unsigned __int16)Key | 0x80070000;
    v8 = Key < 0;
  }
  if ( v8 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)Key,
      dwOptions);
  common = wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create_common(
             a1,
             (__int64)v12,
             a4,
             a5);
  if ( common < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)common,
      dwOptions);
  return wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v12);
}

```

## disassembly

```asm
0x180020398  mov     r11, rsp
0x18002039b  mov     [r11+8], rbx
0x18002039f  push    rdi
0x1800203a0  sub     rsp, 60h
0x1800203a4  mov     bl, r9b
0x1800203a7  mov     rax, r8
0x1800203aa  mov     r10, rdx
0x1800203ad  mov     rdi, rcx
0x1800203b0  mov     qword ptr [r11-18h], 0
0x1800203b8  mov     qword ptr [r11-28h], 0
0x1800203c0  lea     rcx, [r11-18h]
0x1800203c4  mov     [r11-30h], rcx
0x1800203c8  mov     qword ptr [r11-38h], 0
0x1800203d0  mov     [rsp+68h+samDesired], 10h; samDesired
0x1800203d8  mov     [rsp+68h+dwOptions], 0; int
0x1800203e0  xor     r9d, r9d; lpClass
0x1800203e3  xor     r8d, r8d; Reserved
0x1800203e6  mov     rdx, rax; lpSubKey
0x1800203e9  mov     rcx, r10; hKey
0x1800203ec  call    cs:__imp_RegCreateKeyExW
0x1800203f3  nop     dword ptr [rax+rax+00h]
0x1800203f8  test    eax, eax
0x1800203fa  jle     short loc_180020406
0x1800203fc  movzx   eax, ax
0x1800203ff  or      eax, 80070000h
0x180020404  test    eax, eax
0x180020406  jns     short loc_180020422
0x180020408  mov     rcx, [rsp+68h]; this
0x18002040d  mov     r9d, eax; char *
0x180020410  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180020417  mov     edx, 1CBEh; void *
0x18002041c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180020422  mov     r9, [rsp+68h+arg_20]
0x18002042a  mov     r8b, bl
0x18002042d  lea     rdx, [rsp+68h+var_18]
0x180020432  mov     rcx, rdi
0x180020435  call    ?create_common@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@AEAAJ$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z; wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create_common(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)
0x18002043a  mov     rcx, [rsp+68h]; this
0x18002043f  test    eax, eax
0x180020441  jns     short loc_180020458
0x180020443  mov     r9d, eax; char *
0x180020446  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002044d  mov     edx, 1CBEh; void *
0x180020452  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180020458  lea     rcx, [rsp+68h+var_18]
0x18002045d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180020462  mov     rbx, [rsp+68h+arg_0]
0x180020467  add     rsp, 60h
0x18002046b  pop     rdi
0x18002046c  retn
```
