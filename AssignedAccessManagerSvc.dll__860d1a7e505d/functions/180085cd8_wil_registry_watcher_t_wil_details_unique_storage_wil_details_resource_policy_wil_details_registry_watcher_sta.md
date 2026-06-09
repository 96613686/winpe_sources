# wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create(HKEY__ *,ushort const *,bool,wistd::function<void (wil::RegistryChangeKind)> &&)

- ea: `0x180085cd8`
- end: `0x180085db9`
- name: `?create@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXPEAUHKEY__@@PEBG_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z`
- size: `225`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180085af8`

## callees

- `0x180020050`
- `0x180029c04`
- `0x18002b4c8`
- `0x180085cd8`
- `0x180085dc0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180085d3a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180085d3a`

## string_xrefs

- `0x180085d5b`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x180085d94`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create(
        __int64 *a1,
        HKEY a2,
        const WCHAR *a3,
        char a4,
        __int64 a5)
{
  int Key; // eax
  bool v10; // sf
  int common; // eax
  DWORD dwOptions; // [rsp+20h] [rbp-68h]
  HKEY phkResult[7]; // [rsp+50h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  phkResult[0] = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    phkResult,
    0);
  Key = RegCreateKeyExW(a2, a3, 0, 0, 0, 0x10u, 0, phkResult, 0);
  v10 = Key < 0;
  if ( Key > 0 )
  {
    Key = (unsigned __int16)Key | 0x80070000;
    v10 = Key < 0;
  }
  if ( v10 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)Key,
      dwOptions);
  common = wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create_common(
             a1,
             (__int64)phkResult,
             a4,
             a5);
  if ( common < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)common,
      dwOptions);
  return wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(phkResult);
}

```

## disassembly

```asm
0x180085cd8  push    rbx
0x180085cda  push    rbp
0x180085cdb  push    rsi
0x180085cdc  push    rdi
0x180085cdd  sub     rsp, 68h
0x180085ce1  mov     sil, r9b
0x180085ce4  mov     rbx, r8
0x180085ce7  mov     rdi, rdx
0x180085cea  mov     rbp, rcx
0x180085ced  mov     [rsp+88h+var_38], 0
0x180085cf6  xor     edx, edx
0x180085cf8  lea     rcx, [rsp+88h+var_38]
0x180085cfd  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180085d02  mov     [rsp+88h+lpdwDisposition], 0; lpdwDisposition
0x180085d0b  lea     rax, [rsp+88h+var_38]
0x180085d10  mov     [rsp+88h+phkResult], rax; phkResult
0x180085d15  mov     [rsp+88h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180085d1e  mov     [rsp+88h+samDesired], 10h; samDesired
0x180085d26  mov     [rsp+88h+dwOptions], 0; int
0x180085d2e  xor     r9d, r9d; lpClass
0x180085d31  xor     r8d, r8d; Reserved
0x180085d34  mov     rdx, rbx; lpSubKey
0x180085d37  mov     rcx, rdi; hKey
0x180085d3a  call    cs:__imp_RegCreateKeyExW
0x180085d40  test    eax, eax
0x180085d42  jle     short loc_180085D4E
0x180085d44  movzx   eax, ax
0x180085d47  or      eax, 80070000h
0x180085d4c  test    eax, eax
0x180085d4e  jns     short loc_180085D6D
0x180085d50  mov     rcx, [rsp+88h]; this
0x180085d58  mov     r9d, eax; char *
0x180085d5b  lea     r8, aOnecoreInterna_6; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180085d62  mov     edx, 1CBEh; void *
0x180085d67  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180085d6d  mov     r9, [rsp+88h+arg_20]
0x180085d75  mov     r8b, sil
0x180085d78  lea     rdx, [rsp+88h+var_38]
0x180085d7d  mov     rcx, rbp
0x180085d80  call    ?create_common@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@AEAAJ$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z; wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create_common(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)
0x180085d85  mov     rcx, [rsp+88h]; this
0x180085d8d  test    eax, eax
0x180085d8f  jns     short loc_180085DA6
0x180085d91  mov     r9d, eax; char *
0x180085d94  lea     r8, aOnecoreInterna_6; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180085d9b  mov     edx, 1CBEh; void *
0x180085da0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180085da6  lea     rcx, [rsp+88h+var_38]
0x180085dab  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180085db0  add     rsp, 68h
0x180085db4  pop     rdi
0x180085db5  pop     rsi
0x180085db6  pop     rbp
0x180085db7  pop     rbx
0x180085db8  retn
```
