# NetSetupFindPropertiesFromVmHost

- ea: `0x1800207bc`
- end: `0x1800209d5`
- name: `NetSetupFindPropertiesFromVmHost`
- size: `537`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18001f2e4`

## callees

- `0x1800027c0`
- `0x180008d94`
- `0x180008e3c`
- `0x18000d954`
- `0x18000d974`
- `0x18000d9b4`
- `0x1800207bc`
- `0x1800209dc`
- `0x180022800`
- `0x180024b14`
- `0x180026980`
- `0x180026dcc`
- `0x180026eec`
- `0x180027d2c`
- `0x180027ef4`
- `0x1800285cc`
- `0x18002c728`
- `0x18002d038`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180020904`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180020904`

## string_xrefs

- `0x180020849`: `Services\Netvsc\InterfaceMap`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
LSTATUS __fastcall NetSetupFindPropertiesFromVmHost(__int64 a1, __int64 a2, NetSetup2::NetworkInterfaceTemplate *a3)
{
  struct Property v5; // rax
  void *Uint64; // rbx
  RegistryKey *v7; // rax
  int NumSubKeys; // edi
  int i; // ebx
  const WCHAR *v10; // rax
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rax
  __int64 v14; // r8
  int v15; // r9d
  HKEY v17; // [rsp+30h] [rbp-59h] BYREF
  HKEY *v18; // [rsp+38h] [rbp-51h] BYREF
  int v19; // [rsp+40h] [rbp-49h]
  HKEY v20; // [rsp+48h] [rbp-41h] BYREF
  HKEY v21; // [rsp+50h] [rbp-39h] BYREF
  __int64 v22; // [rsp+58h] [rbp-31h] BYREF
  __int64 v23; // [rsp+60h] [rbp-29h] BYREF
  int v24; // [rsp+68h] [rbp-21h]
  __int128 v25; // [rsp+6Ch] [rbp-1Dh]
  _BYTE v26[24]; // [rsp+80h] [rbp-9h] BYREF
  _BYTE v27[24]; // [rsp+98h] [rbp+Fh] BYREF

  v22 = a1;
  v23 = 0;
  v24 = 9;
  v25 = 0;
  v5.lpVtbl = NetSetup2::ActiveObject::GetProperty(
                (NetSetup2::ActiveObject *)&v22,
                (const struct _NETSETUPPROPKEY *)v26,
                (unsigned int)NETSETUPPKEY_Transaction_CurrentControlSetRegistryHandle).lpVtbl;
  Uint64 = (void *)NetSetup2::Property::GetUint64((NetSetup2::Property *)v5.lpVtbl);
  std::vector<unsigned char>::_Tidy((__int64)v27);
  v7 = RegistryKey::DuplicateFrom((RegistryKey *)&v17, Uint64);
  RegistryKey::TryOpenSubKey(v7, &v20, L"Services\\Netvsc\\InterfaceMap", 9, 0);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v17);
  std::unique_ptr<std::vector<NetSetup2::Property>>::~unique_ptr<std::vector<NetSetup2::Property>>(&v23);
  if ( v20 )
  {
    NumSubKeys = RegistryKey::GetNumSubKeys(&v20);
    v18 = &v20;
    for ( i = 0; ; ++i )
    {
      v19 = i;
      if ( i == NumSubKeys )
        break;
      RegistryKeyIterator::operator*((__int64)&v18, (__int64)v26);
      v10 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
      RegistryKey::OpenSubKey(&v20, (RegistryKey *)&v21, v10, 1, 0);
      RegistryKey::GetValueString(&v21, (__int64)&v22, L"PnPId", 1);
      std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
      v11 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
      if ( !(unsigned int)_o__wcsicmp(v11, v12) )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
          v13 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
          WPP_SF_SS(*(_QWORD *)(v14 + 16), 51, v14, v15, v13);
        }
        NetSetupImportPropertiesFromVmHost(a3, &v21);
        RemoveConflictingNetworkInterfaces(a1, a3);
        std::wstring::_Tidy_deallocate((__int64)&v22);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v21);
        std::wstring::_Tidy_deallocate((__int64)v26);
        return wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v20);
      }
      std::wstring::_Tidy_deallocate((__int64)&v22);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v21);
      std::wstring::_Tidy_deallocate((__int64)v26);
    }
  }
  return wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v20);
}

```

## disassembly

```asm
0x1800207bc  mov     [rsp-8+arg_18], rbx
0x1800207c1  push    rbp
0x1800207c2  push    rsi
0x1800207c3  push    rdi
0x1800207c4  push    r14
0x1800207c6  push    r15
0x1800207c8  lea     rbp, [rsp-37h]
0x1800207cd  sub     rsp, 0C0h
0x1800207d4  mov     rax, cs:__security_cookie
0x1800207db  xor     rax, rsp
0x1800207de  mov     [rbp+57h+var_30], rax
0x1800207e2  mov     rsi, r8
0x1800207e5  mov     r14, rdx
0x1800207e8  mov     r15, rcx
0x1800207eb  xorps   xmm0, xmm0
0x1800207ee  mov     [rbp+57h+var_88], rcx
0x1800207f2  mov     [rbp+57h+var_80], 0
0x1800207fa  mov     edi, 9
0x1800207ff  mov     [rbp+57h+var_78], edi
0x180020802  movdqu  [rbp+57h+var_74], xmm0
0x180020807  lea     r8, NETSETUPPKEY_Transaction_CurrentControlSetRegistryHandle
0x18002080e  lea     rdx, [rbp+57h+var_60]; struct _NETSETUPPROPKEY *
0x180020812  lea     rcx, [rbp+57h+var_88]; this
0x180020816  call    ?GetProperty@ActiveObject@NetSetup2@@QEBA?AVProperty@2@AEBU_NETSETUPPROPKEY@@@Z; NetSetup2::ActiveObject::GetProperty(_NETSETUPPROPKEY const &)
0x18002081b  nop
0x18002081c  mov     rcx, rax; this
0x18002081f  call    ?GetUint64@Property@NetSetup2@@QEBA_KXZ; NetSetup2::Property::GetUint64(void)
0x180020824  mov     rbx, rax
0x180020827  lea     rcx, [rbp+57h+var_48]
0x18002082b  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180020830  mov     rdx, rbx
0x180020833  lea     rcx, [rbp+57h+var_B0]
0x180020837  call    ?DuplicateFrom@RegistryKey@@SA?AV1@PEAUHKEY__@@@Z; RegistryKey::DuplicateFrom(HKEY__ *)
0x18002083c  nop
0x18002083d  mov     [rsp+0E0h+var_C0], 0
0x180020846  mov     r9d, edi
0x180020849  lea     r8, aServicesNetvsc; "Services\\Netvsc\\InterfaceMap"
0x180020850  lea     rdx, [rbp+57h+var_98]
0x180020854  mov     rcx, rax
0x180020857  call    ?TryOpenSubKey@RegistryKey@@QEBA?AV1@PEB_WKPEAX@Z; RegistryKey::TryOpenSubKey(wchar_t const *,ulong,void *)
0x18002085c  nop
0x18002085d  lea     rcx, [rbp+57h+var_B0]
0x180020861  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180020866  nop
0x180020867  lea     rcx, [rbp+57h+var_80]
0x18002086b  call    ??1?$unique_ptr@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@U?$default_delete@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::vector<NetSetup2::Property>>::~unique_ptr<std::vector<NetSetup2::Property>>(void)
0x180020870  cmp     [rbp+57h+var_98], 0
0x180020875  jz      loc_1800209A9
0x18002087b  lea     rcx, [rbp+57h+var_98]; this
0x18002087f  call    ?GetNumSubKeys@RegistryKey@@QEBAKXZ; RegistryKey::GetNumSubKeys(void)
0x180020884  mov     edi, eax
0x180020886  lea     rax, [rbp+57h+var_98]
0x18002088a  mov     [rbp+57h+var_A8], rax
0x18002088e  xor     ebx, ebx
0x180020890  mov     [rbp+57h+var_A0], ebx
0x180020893  cmp     ebx, edi
0x180020895  jz      loc_1800209A9
0x18002089b  lea     rdx, [rbp+57h+var_60]
0x18002089f  lea     rcx, [rbp+57h+var_A8]
0x1800208a3  call    ??DRegistryKeyIterator@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; RegistryKeyIterator::operator*(void)
0x1800208a8  nop
0x1800208a9  lea     rcx, [rbp+57h+var_60]
0x1800208ad  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800208b2  mov     r8, rax
0x1800208b5  mov     [rsp+0E0h+var_C0], 0
0x1800208be  mov     r9d, 1
0x1800208c4  lea     rdx, [rbp+57h+var_90]
0x1800208c8  lea     rcx, [rbp+57h+var_98]
0x1800208cc  call    ?OpenSubKey@RegistryKey@@QEBA?AV1@PEB_WKPEAX@Z; RegistryKey::OpenSubKey(wchar_t const *,ulong,void *)
0x1800208d1  nop
0x1800208d2  mov     r9d, 1
0x1800208d8  lea     r8, aPnpid; "PnPId"
0x1800208df  lea     rdx, [rbp+57h+var_88]
0x1800208e3  lea     rcx, [rbp+57h+var_90]
0x1800208e7  call    ?GetValueString@RegistryKey@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WW4MissingValueDisposition@1@@Z; RegistryKey::GetValueString(wchar_t const *,RegistryKey::MissingValueDisposition)
0x1800208ec  nop
0x1800208ed  mov     rcx, r14
0x1800208f0  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800208f5  mov     rdx, rax
0x1800208f8  lea     rcx, [rbp+57h+var_88]
0x1800208fc  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180020901  mov     rcx, rax
0x180020904  call    cs:__imp__o__wcsicmp
0x18002090a  test    eax, eax
0x18002090c  jz      short loc_180020932
0x18002090e  lea     rcx, [rbp+57h+var_88]
0x180020912  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180020917  nop
0x180020918  lea     rcx, [rbp+57h+var_90]
0x18002091c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180020921  nop
0x180020922  lea     rcx, [rbp+57h+var_60]
0x180020926  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002092b  inc     ebx
0x18002092d  jmp     loc_180020890
0x180020932  lea     rax, WPP_GLOBAL_Control
0x180020939  mov     r8, cs:WPP_GLOBAL_Control
0x180020940  cmp     r8, rax
0x180020943  jz      short loc_180020973
0x180020945  cmp     byte ptr [r8+19h], 4
0x18002094a  jb      short loc_180020973
0x18002094c  mov     rcx, r14
0x18002094f  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180020954  mov     r9, rax
0x180020957  lea     rcx, [rbp+57h+var_60]
0x18002095b  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180020960  mov     edx, 33h ; '3'
0x180020965  mov     [rsp+0E0h+var_C0], rax
0x18002096a  mov     rcx, [r8+10h]
0x18002096e  call    WPP_SF_SS
0x180020973  lea     rdx, [rbp+57h+var_90]; RegistryKey *
0x180020977  mov     rcx, rsi; this
0x18002097a  call    NetSetupImportPropertiesFromVmHost
0x18002097f  mov     rdx, rsi
0x180020982  mov     rcx, r15
0x180020985  call    RemoveConflictingNetworkInterfaces
0x18002098a  nop
0x18002098b  lea     rcx, [rbp+57h+var_88]
0x18002098f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180020994  nop
0x180020995  lea     rcx, [rbp+57h+var_90]
0x180020999  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002099e  nop
0x18002099f  lea     rcx, [rbp+57h+var_60]
0x1800209a3  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800209a8  nop
0x1800209a9  lea     rcx, [rbp+57h+var_98]
0x1800209ad  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800209b2  mov     rcx, [rbp+57h+var_30]
0x1800209b6  xor     rcx, rsp; StackCookie
0x1800209b9  call    __security_check_cookie
0x1800209be  mov     rbx, [rsp+0E0h+arg_18]
0x1800209c6  add     rsp, 0C0h
0x1800209cd  pop     r15
0x1800209cf  pop     r14
0x1800209d1  pop     rdi
0x1800209d2  pop     rsi
0x1800209d3  pop     rbp
0x1800209d4  retn
```
