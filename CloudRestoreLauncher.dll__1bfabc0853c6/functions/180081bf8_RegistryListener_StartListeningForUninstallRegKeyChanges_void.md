# RegistryListener::StartListeningForUninstallRegKeyChanges(void)

- ea: `0x180081bf8`
- end: `0x180081d6a`
- name: `?StartListeningForUninstallRegKeyChanges@RegistryListener@@AEAAXXZ`
- size: `370`
- prototype: `void __fastcall(RegistryListener *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180081b90`

## callees

- `0x18000c6e0`
- `0x1800164c0`
- `0x18002498c`
- `0x180043b14`
- `0x18006d5c0`
- `0x180075c20`
- `0x180081bf8`
- `0x1800825bc`
- `0x180082770`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x180081cbf`
- `ADVAPI32!RegCreateKeyExW` at `0x180081cbf`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall RegistryListener::StartListeningForUninstallRegKeyChanges(RegistryListener *this)
{
  LPCWSTR *i; // rdi
  __int64 v3; // rbx
  LSTATUS v4; // eax
  __int64 v5; // r8
  bool v6; // sf
  __int64 v7; // [rsp+50h] [rbp-B0h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v9[8]; // [rsp+60h] [rbp-A0h] BYREF
  std::_Ref_count_base *v10; // [rsp+68h] [rbp-98h]
  RegistryListener *v11; // [rsp+70h] [rbp-90h]
  _QWORD v12[3]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v13[8]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v14[14]; // [rsp+98h] [rbp-68h] BYREF

  std::weak_ptr<AppAndTileMatcher>::weak_ptr<AppAndTileMatcher>(v9, (char *)this + 8);
  for ( i = (LPCWSTR *)((char *)this + 24); i != (LPCWSTR *)((char *)this + 376); i += 11 )
  {
    v11 = this;
    std::weak_ptr<AppAndTileMatcher>::weak_ptr<AppAndTileMatcher>(v12, v9);
    v14[0] = &off_180130370;
    v14[1] = v11;
    v14[2] = v12[0];
    v14[3] = v12[1];
    v14[4] = i;
    v14[13] = v14;
    v3 = 0;
    v7 = 0;
    phkResult = 0;
    v4 = RegCreateKeyExW((HKEY)*i, i[1], 0, 0, 0, 0x10u, 0, &phkResult, 0);
    v6 = v4 < 0;
    if ( v4 > 0 )
      v6 = 1;
    if ( !v6 )
    {
      wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::create_common(
        (__int64)&v7,
        (__int64)&phkResult,
        v5,
        (__int64)v13);
      v3 = v7;
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
    if ( i + 2 != (LPCWSTR *)&v7 )
    {
      wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::reset(
        i + 2,
        v3);
      v7 = 0;
    }
    wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>(&v7);
    wistd::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::~function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>(v13);
  }
  if ( v10 )
    std::_Ref_count_base::_Decwref(v10);
}

```

## disassembly

```asm
0x180081bf8  mov     [rsp-8+arg_8], rbx
0x180081bfd  mov     [rsp-8+arg_10], rsi
0x180081c02  push    rbp
0x180081c03  push    rdi
0x180081c04  push    r14
0x180081c06  lea     rbp, [rsp-10h]
0x180081c0b  sub     rsp, 110h
0x180081c12  mov     rax, cs:__security_cookie
0x180081c19  xor     rax, rsp
0x180081c1c  mov     [rbp+20h+var_18], rax
0x180081c20  mov     rsi, rcx
0x180081c23  lea     rdx, [rcx+8]
0x180081c27  lea     rcx, [rsp+120h+var_C0]
0x180081c2c  call    ??0?$weak_ptr@VAppAndTileMatcher@@@std@@QEAA@AEBV01@@Z; std::weak_ptr<AppAndTileMatcher>::weak_ptr<AppAndTileMatcher>(std::weak_ptr<AppAndTileMatcher> const &)
0x180081c31  lea     rdi, [rsi+18h]
0x180081c35  lea     r14, [rdi+160h]
0x180081c3c  jmp     loc_180081D2E
0x180081c41  mov     [rsp+120h+var_B0], rsi
0x180081c46  lea     rdx, [rsp+120h+var_C0]
0x180081c4b  lea     rcx, [rsp+120h+var_A8]
0x180081c50  call    ??0?$weak_ptr@VAppAndTileMatcher@@@std@@QEAA@AEBV01@@Z; std::weak_ptr<AppAndTileMatcher>::weak_ptr<AppAndTileMatcher>(std::weak_ptr<AppAndTileMatcher> const &)
0x180081c55  lea     rcx, off_180130370
0x180081c5c  mov     [rbp+20h+var_88], rcx
0x180081c60  mov     rax, [rsp+120h+var_B0]
0x180081c65  mov     [rbp+20h+var_80], rax
0x180081c69  mov     rax, [rsp+120h+var_A8]
0x180081c6e  mov     [rbp+20h+var_78], rax
0x180081c72  mov     rax, [rbp+20h+var_A0]
0x180081c76  mov     [rbp+20h+var_70], rax
0x180081c7a  mov     [rbp+20h+var_68], rdi
0x180081c7e  lea     rax, [rbp+20h+var_88]
0x180081c82  mov     [rbp+20h+var_20], rax
0x180081c86  xor     ebx, ebx
0x180081c88  mov     [rsp+120h+var_D0], rbx
0x180081c8d  mov     [rsp+120h+var_C8], rbx
0x180081c92  mov     [rsp+120h+lpdwDisposition], rbx; lpdwDisposition
0x180081c97  lea     rax, [rsp+120h+var_C8]
0x180081c9c  mov     [rsp+120h+phkResult], rax; phkResult
0x180081ca1  mov     [rsp+120h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x180081ca6  mov     [rsp+120h+samDesired], 10h; samDesired
0x180081cae  mov     [rsp+120h+dwOptions], ebx; dwOptions
0x180081cb2  xor     r9d, r9d; lpClass
0x180081cb5  xor     r8d, r8d; Reserved
0x180081cb8  mov     rdx, [rdi+8]; lpSubKey
0x180081cbc  mov     rcx, [rdi]; hKey
0x180081cbf  call    cs:__imp_RegCreateKeyExW
0x180081cc5  test    eax, eax
0x180081cc7  jle     short loc_180081CD3
0x180081cc9  movzx   eax, ax
0x180081ccc  or      eax, 80070000h
0x180081cd1  test    eax, eax
0x180081cd3  js      short loc_180081CED
0x180081cd5  lea     r9, [rbp+20h+var_90]
0x180081cd9  lea     rdx, [rsp+120h+var_C8]
0x180081cde  lea     rcx, [rsp+120h+var_D0]
0x180081ce3  call    ?create_common@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@AEAAJ$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z; wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::create_common(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&,bool,wistd::function<void (wil::RegistryChangeKind)> &&)
0x180081ce8  mov     rbx, [rsp+120h+var_D0]
0x180081ced  lea     rcx, [rsp+120h+var_C8]
0x180081cf2  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180081cf7  nop
0x180081cf8  lea     rcx, [rdi+10h]
0x180081cfc  lea     rax, [rsp+120h+var_D0]
0x180081d01  cmp     rcx, rax
0x180081d04  jz      short loc_180081D17
0x180081d06  mov     rdx, rbx
0x180081d09  call    ?reset@?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUregistry_watcher_state@23@@Z; wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::reset(wil::details::registry_watcher_state *)
0x180081d0e  mov     [rsp+120h+var_D0], 0
0x180081d17  lea     rcx, [rsp+120h+var_D0]
0x180081d1c  call    ??1?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>(void)
0x180081d21  lea     rcx, [rbp+20h+var_90]
0x180081d25  call    ??1?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEAA@XZ; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::~function<long (ushort *,unsigned __int64,unsigned __int64 *)>(void)
0x180081d2a  add     rdi, 58h ; 'X'
0x180081d2e  cmp     rdi, r14
0x180081d31  jnz     loc_180081C41
0x180081d37  mov     rcx, [rsp+120h+var_B8]; this
0x180081d3c  test    rcx, rcx
0x180081d3f  jz      short loc_180081D46
0x180081d41  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180081d46  mov     rcx, [rbp+20h+var_18]
0x180081d4a  xor     rcx, rsp; StackCookie
0x180081d4d  call    __security_check_cookie
0x180081d52  lea     r11, [rsp+120h+var_10]
0x180081d5a  mov     rbx, [r11+28h]
0x180081d5e  mov     rsi, [r11+30h]
0x180081d62  mov     rsp, r11
0x180081d65  pop     r14
0x180081d67  pop     rdi
0x180081d68  pop     rbp
0x180081d69  retn
```
