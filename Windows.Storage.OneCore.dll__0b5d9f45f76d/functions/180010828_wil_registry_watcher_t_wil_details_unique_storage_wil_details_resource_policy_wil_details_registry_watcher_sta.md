# wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create(HKEY__ *,ushort const *,bool,wistd::function<void (wil::RegistryChangeKind)> &&)

- ea: `0x180010828`
- end: `0x180010909`
- name: `?create@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXPEAUHKEY__@@PEBG_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z`
- size: `225`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ca78`

## callees

- `0x18000d524`
- `0x180010670`
- `0x180010828`
- `0x180010910`
- `0x180011344`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001088a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001088a`

## string_xrefs

- `0x1800108ab`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x1800108e4`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

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
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)Key,
      dwOptions);
  common = wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create_common(
             a1,
             phkResult,
             a4,
             a5);
  if ( common < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)common,
      dwOptions);
  return wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(phkResult);
}

```

## disassembly

```asm
0x180010828  push    rbx
0x18001082a  push    rbp
0x18001082b  push    rsi
0x18001082c  push    rdi
0x18001082d  sub     rsp, 68h
0x180010831  mov     sil, r9b
0x180010834  mov     rbx, r8
0x180010837  mov     rdi, rdx
0x18001083a  mov     rbp, rcx
0x18001083d  mov     [rsp+88h+var_38], 0
0x180010846  xor     edx, edx
0x180010848  lea     rcx, [rsp+88h+var_38]
0x18001084d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180010852  mov     [rsp+88h+lpdwDisposition], 0; lpdwDisposition
0x18001085b  lea     rax, [rsp+88h+var_38]
0x180010860  mov     [rsp+88h+phkResult], rax; phkResult
0x180010865  mov     [rsp+88h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18001086e  mov     [rsp+88h+samDesired], 10h; samDesired
0x180010876  mov     [rsp+88h+dwOptions], 0; int
0x18001087e  xor     r9d, r9d; lpClass
0x180010881  xor     r8d, r8d; Reserved
0x180010884  mov     rdx, rbx; lpSubKey
0x180010887  mov     rcx, rdi; hKey
0x18001088a  call    cs:__imp_RegCreateKeyExW
0x180010890  test    eax, eax
0x180010892  jle     short loc_18001089E
0x180010894  movzx   eax, ax
0x180010897  or      eax, 80070000h
0x18001089c  test    eax, eax
0x18001089e  jns     short loc_1800108BD
0x1800108a0  mov     rcx, [rsp+88h]; this
0x1800108a8  mov     r9d, eax; char *
0x1800108ab  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800108b2  mov     edx, 1CBEh; void *
0x1800108b7  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800108bd  mov     r9, [rsp+88h+arg_20]
0x1800108c5  mov     r8b, sil
0x1800108c8  lea     rdx, [rsp+88h+var_38]
0x1800108cd  mov     rcx, rbp
0x1800108d0  call    ?create_common@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@AEAAJ$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z; wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create_common(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)
0x1800108d5  mov     rcx, [rsp+88h]; this
0x1800108dd  test    eax, eax
0x1800108df  jns     short loc_1800108F6
0x1800108e1  mov     r9d, eax; char *
0x1800108e4  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800108eb  mov     edx, 1CBEh; void *
0x1800108f0  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800108f6  lea     rcx, [rsp+88h+var_38]
0x1800108fb  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180010900  add     rsp, 68h
0x180010904  pop     rdi
0x180010905  pop     rsi
0x180010906  pop     rbp
0x180010907  pop     rbx
0x180010908  retn
```
