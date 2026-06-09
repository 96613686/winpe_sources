# RecreateNetworkInterface

- ea: `0x1800223a4`
- end: `0x180022665`
- name: `RecreateNetworkInterface`
- size: `705`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180023af4`

## callees

- `0x180001b50`
- `0x180001c38`
- `0x1800027c0`
- `0x1800082c0`
- `0x180008e3c`
- `0x18000d954`
- `0x18000d974`
- `0x18000d9b4`
- `0x18001b168`
- `0x18001e734`
- `0x18001ea44`
- `0x1800223a4`
- `0x18002442c`
- `0x180024468`
- `0x1800244e0`
- `0x180024520`
- `0x180024a04`
- `0x180028dc4`
- `0x18002923c`
- `0x180029840`
- `0x18002bba8`
- `0x18002c728`
- `0x18002c89c`
- `0x18002ce44`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
LSTATUS __fastcall RecreateNetworkInterface(
        __int64 a1,
        NetSetup2::ActiveObject *a2,
        NetSetup2::NetworkInterfaceTemplate *a3,
        __int64 a4,
        char *a5)
{
  const wchar_t *v9; // rax
  char v10; // bl
  unsigned int Uint32; // edi
  unsigned int IfType; // ebx
  unsigned int v13; // edi
  __int64 v14; // r8
  int v15; // eax
  __int64 v16; // rdx
  _QWORD *v17; // r8
  __int64 v18; // r10
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 v21; // r9
  unsigned int v22; // ebx
  __int64 *v24; // [rsp+50h] [rbp-91h] BYREF
  __int64 *v25[2]; // [rsp+58h] [rbp-89h] BYREF
  char v26[8]; // [rsp+68h] [rbp-79h] BYREF
  unsigned int PnpDeviceInterfaceNumber; // [rsp+70h] [rbp-71h] BYREF
  char v28; // [rsp+74h] [rbp-6Dh]
  unsigned int v29; // [rsp+78h] [rbp-69h] BYREF
  HKEY v30; // [rsp+80h] [rbp-61h] BYREF
  _OWORD v31[2]; // [rsp+88h] [rbp-59h] BYREF
  _BYTE v32[16]; // [rsp+A8h] [rbp-39h] BYREF
  struct Property v33[2]; // [rsp+B8h] [rbp-29h] BYREF
  int v34; // [rsp+CCh] [rbp-15h]
  _BYTE v35[24]; // [rsp+D0h] [rbp-11h] BYREF
  __int128 v36; // [rsp+E8h] [rbp+7h] BYREF

  v9 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  NetSetupDevice::NetSetupDevice((NetSetupDevice *)v32, v9, 0);
  NetSetupDevice::OpenSoftwareKey((NetSetupDevice *)v32, (RegistryKey *)&v30, 2u, a5);
  NetSetup2::ActiveObject::GetProperty(
    a2,
    (const struct _NETSETUPPROPKEY *)v33,
    (unsigned int)NETSETUPPKEY_Interface_IfAliasUniquifier);
  if ( v34 )
  {
    Uint32 = NetSetup2::Property::GetUint32((NetSetup2::Property *)v33);
    v10 = 1;
    v28 = 1;
    PnpDeviceInterfaceNumber = Uint32;
    std::vector<unsigned char>::_Tidy((__int64)v35);
  }
  else
  {
    v28 = 0;
    std::vector<unsigned char>::_Tidy((__int64)v35);
    v10 = 0;
    Uint32 = PnpDeviceInterfaceNumber;
  }
  if ( v10 )
  {
    v29 = Uint32;
    NetSetup2::ObjectCreationTemplate::SetPropertyToValue<7,unsigned long>(
      (__int64)a3,
      (__int128 *)NETSETUPPKEY_Interface_IfAliasUniquifier,
      (__int64)&v29);
  }
  v31[0] = 0;
  v31[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v31[0]) = 0;
  NetSetupDevice::GetStringProperty(v32, &DEVPKEY_Device_ConfigurationId, v31);
  IfType = NetSetup2::NetworkInterface::get_IfType(a2);
  v13 = NetSetup2::NetworkInterfaceTemplate::get_IfType(a3);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    NetSetup2::NetworkInterface::get_NetLuid(a2);
    std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
    v15 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
    WPP_SF_SDDS_guid_I(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, (_DWORD)v17, v15, IfType, v13, v18, v16, *v17);
  }
  if ( (unsigned int)dword_180049000 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180049000, 0x400000000000LL, v14) )
  {
    v29 = v13;
    PnpDeviceInterfaceNumber = IfType;
    v24 = (__int64 *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
    v25[0] = (__int64 *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v19,
      (int)&dword_1800418AC,
      v20,
      v21,
      v25,
      &v24,
      (__int64)&PnpDeviceInterfaceNumber,
      (__int64)&v29);
  }
  PnpDeviceInterfaceNumber = NetSetup2::NetworkInterface::get_PnpDeviceInterfaceNumber(a2);
  NetSetup2::ObjectCreationTemplate::SetPropertyToValue<7,unsigned long>(
    (__int64)a3,
    (__int128 *)NETSETUPPKEY_Interface_PnpDeviceInterfaceNumber,
    (__int64)&PnpDeviceInterfaceNumber);
  v26[0] = 0;
  NetSetup2::ActiveObject::SetPropertyToValue<17,bool>(
    a2,
    NETSETUPPKEY_Interface_RemovePnpDeviceWhenInterfaceRemoved,
    v26);
  NetSetup2::ActiveObject::Delete(a2);
  v36 = *(_OWORD *)CreateNewNetworkInterface(v25, a1, a3, a4);
  NetSetup2::ObjectCreationTemplate::GetProperty(a3, v33);
  if ( v34 )
    v22 = NetSetup2::Property::GetUint32((NetSetup2::Property *)v33);
  else
    v22 = 0;
  std::vector<unsigned char>::_Tidy((__int64)v35);
  if ( !v22 )
    FinalizeNewlyCreatedNetworkInterface(a1, &v30, &v36);
  std::wstring::_Tidy_deallocate((__int64)v31);
  return wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v30);
}

```

## disassembly

```asm
0x1800223a4  push    rbp
0x1800223a6  push    rbx
0x1800223a7  push    rsi
0x1800223a8  push    rdi
0x1800223a9  push    r12
0x1800223ab  push    r14
0x1800223ad  push    r15
0x1800223af  lea     rbp, [rsp-1Fh]
0x1800223b4  sub     rsp, 100h
0x1800223bb  mov     rax, cs:__security_cookie
0x1800223c2  xor     rax, rsp
0x1800223c5  mov     [rbp+4Fh+var_38], rax
0x1800223c9  mov     r15, r9
0x1800223cc  mov     r14, r8
0x1800223cf  mov     rsi, rdx
0x1800223d2  mov     r12, rcx
0x1800223d5  mov     rbx, [rbp+4Fh+arg_20]
0x1800223d9  mov     rcx, r9
0x1800223dc  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800223e1  xor     r8d, r8d; bool
0x1800223e4  mov     rdx, rax; wchar_t *
0x1800223e7  lea     rcx, [rbp+4Fh+var_88]; this
0x1800223eb  call    ??0NetSetupDevice@@QEAA@PEB_W_N@Z; NetSetupDevice::NetSetupDevice(wchar_t const *,bool)
0x1800223f0  mov     r9, rbx
0x1800223f3  mov     r8d, 2
0x1800223f9  lea     rdx, [rbp+4Fh+var_B0]
0x1800223fd  lea     rcx, [rbp+4Fh+var_88]
0x180022401  call    ?OpenSoftwareKey@NetSetupDevice@@QEAA?AVRegistryKey@@KPEAXW4DeviceKeyFailPolicy@1@@Z; NetSetupDevice::OpenSoftwareKey(ulong,void *,NetSetupDevice::DeviceKeyFailPolicy)
0x180022406  nop
0x180022407  lea     r8, NETSETUPPKEY_Interface_IfAliasUniquifier
0x18002240e  lea     rdx, [rbp+4Fh+var_78]; struct _NETSETUPPROPKEY *
0x180022412  mov     rcx, rsi; this
0x180022415  call    ?GetProperty@ActiveObject@NetSetup2@@QEBA?AVProperty@2@AEBU_NETSETUPPROPKEY@@@Z; NetSetup2::ActiveObject::GetProperty(_NETSETUPPROPKEY const &)
0x18002241a  nop
0x18002241b  cmp     [rbp+4Fh+var_64], 0
0x18002241f  jnz     short loc_180022435
0x180022421  mov     [rbp+4Fh+var_BC], 0
0x180022425  lea     rcx, [rbp+4Fh+var_60]
0x180022429  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18002242e  xor     bl, bl
0x180022430  mov     edi, [rbp+4Fh+var_C0]
0x180022433  jmp     short loc_180022452
0x180022435  lea     rcx, [rbp+4Fh+var_78]; this
0x180022439  call    ?GetUint32@Property@NetSetup2@@QEBAKXZ; NetSetup2::Property::GetUint32(void)
0x18002243e  mov     edi, eax
0x180022440  mov     bl, 1
0x180022442  mov     [rbp+4Fh+var_BC], bl
0x180022445  mov     [rbp+4Fh+var_C0], eax
0x180022448  lea     rcx, [rbp+4Fh+var_60]
0x18002244c  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180022451  nop
0x180022452  test    bl, bl
0x180022454  jz      short loc_18002246D
0x180022456  mov     [rbp+4Fh+var_B8], edi
0x180022459  lea     r8, [rbp+4Fh+var_B8]
0x18002245d  lea     rdx, NETSETUPPKEY_Interface_IfAliasUniquifier
0x180022464  mov     rcx, r14
0x180022467  call    ??$SetPropertyToValue@$06K@ObjectCreationTemplate@NetSetup2@@IEAAXAEBU_NETSETUPPROPKEY@@AEBK@Z; NetSetup2::ObjectCreationTemplate::SetPropertyToValue<7,ulong>(_NETSETUPPROPKEY const &,ulong const &)
0x18002246c  nop
0x18002246d  xorps   xmm0, xmm0
0x180022470  movups  [rbp+4Fh+var_A8], xmm0
0x180022474  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18002247c  movdqu  [rbp+4Fh+var_98], xmm1
0x180022481  xor     eax, eax
0x180022483  mov     word ptr [rbp+4Fh+var_A8], ax
0x180022487  lea     r8, [rbp+4Fh+var_A8]
0x18002248b  lea     rdx, DEVPKEY_Device_ConfigurationId
0x180022492  lea     rcx, [rbp+4Fh+var_88]
0x180022496  call    ?GetStringProperty@NetSetupDevice@@QEAA_NAEBU_DEVPROPKEY@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; NetSetupDevice::GetStringProperty(_DEVPROPKEY const &,std::wstring &)
0x18002249b  mov     rcx, rsi; this
0x18002249e  call    ?get_IfType@NetworkInterface@NetSetup2@@QEBAKXZ; NetSetup2::NetworkInterface::get_IfType(void)
0x1800224a3  mov     ebx, eax
0x1800224a5  mov     rcx, r14; this
0x1800224a8  call    ?get_IfType@NetworkInterfaceTemplate@NetSetup2@@QEBAKXZ; NetSetup2::NetworkInterfaceTemplate::get_IfType(void)
0x1800224ad  mov     edi, eax
0x1800224af  lea     rax, WPP_GLOBAL_Control
0x1800224b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800224bd  cmp     rcx, rax
0x1800224c0  jz      short loc_18002251D
0x1800224c2  cmp     byte ptr [rcx+19h], 3
0x1800224c6  jb      short loc_18002251D
0x1800224c8  lea     rdx, [rsp+130h+var_D8]
0x1800224cd  mov     rcx, rsi; this
0x1800224d0  call    ?get_NetLuid@NetworkInterface@NetSetup2@@QEBA?AT_NET_LUID_LH@@XZ; NetSetup2::NetworkInterface::get_NetLuid(void)
0x1800224d5  mov     r8, rax
0x1800224d8  mov     rcx, r15
0x1800224db  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800224e0  mov     r10, rax
0x1800224e3  lea     rdx, [rsi+14h]
0x1800224e7  lea     rcx, [rbp+4Fh+var_A8]
0x1800224eb  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800224f0  mov     r9, rax
0x1800224f3  mov     rcx, [r8]
0x1800224f6  mov     [rsp+130h+var_F0], rcx
0x1800224fb  mov     [rsp+130h+var_F8], rdx
0x180022500  mov     [rsp+130h+var_100], r10
0x180022505  mov     dword ptr [rsp+130h+var_108], edi
0x180022509  mov     dword ptr [rsp+130h+var_110], ebx
0x18002250d  mov     rcx, cs:WPP_GLOBAL_Control
0x180022514  mov     rcx, [rcx+10h]
0x180022518  call    WPP_SF_SDDS_guid_I
0x18002251d  mov     eax, cs:dword_180049000
0x180022523  cmp     eax, 5
0x180022526  jbe     short loc_180022595
0x180022528  mov     rdx, 400000000000h
0x180022532  lea     rcx, dword_180049000
0x180022539  call    _tlgKeywordOn
0x18002253e  test    al, al
0x180022540  jz      short loc_180022595
0x180022542  mov     [rbp+4Fh+var_B8], edi
0x180022545  mov     [rbp+4Fh+var_C0], ebx
0x180022548  lea     rcx, [rbp+4Fh+var_A8]
0x18002254c  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180022551  mov     [rsp+130h+var_E0], rax
0x180022556  mov     rcx, r15
0x180022559  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002255e  mov     [rsp+130h+var_D8], rax
0x180022563  lea     rax, [rbp+4Fh+var_B8]
0x180022567  mov     [rsp+130h+var_F8], rax
0x18002256c  lea     rax, [rbp+4Fh+var_C0]
0x180022570  mov     [rsp+130h+var_100], rax
0x180022575  lea     rax, [rsp+130h+var_E0]
0x18002257a  mov     [rsp+130h+var_108], rax
0x18002257f  lea     rax, [rsp+130h+var_D8]
0x180022584  mov     [rsp+130h+var_110], rax
0x180022589  lea     rdx, dword_1800418AC
0x180022590  call    ??$Write@U?$_tlgWrapSz@_W@@U1@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@3AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180022595  mov     rcx, rsi; this
0x180022598  call    ?get_PnpDeviceInterfaceNumber@NetworkInterface@NetSetup2@@QEBAKXZ; NetSetup2::NetworkInterface::get_PnpDeviceInterfaceNumber(void)
0x18002259d  mov     [rbp+4Fh+var_C0], eax
0x1800225a0  lea     r8, [rbp+4Fh+var_C0]
0x1800225a4  lea     rdx, NETSETUPPKEY_Interface_PnpDeviceInterfaceNumber
0x1800225ab  mov     rcx, r14
0x1800225ae  call    ??$SetPropertyToValue@$06K@ObjectCreationTemplate@NetSetup2@@IEAAXAEBU_NETSETUPPROPKEY@@AEBK@Z; NetSetup2::ObjectCreationTemplate::SetPropertyToValue<7,ulong>(_NETSETUPPROPKEY const &,ulong const &)
0x1800225b3  mov     [rbp+4Fh+var_C8], 0
0x1800225b7  lea     r8, [rbp+4Fh+var_C8]
0x1800225bb  lea     rdx, NETSETUPPKEY_Interface_RemovePnpDeviceWhenInterfaceRemoved
0x1800225c2  mov     rcx, rsi
0x1800225c5  call    ??$SetPropertyToValue@$0BB@_N@ActiveObject@NetSetup2@@IEAAXAEBU_NETSETUPPROPKEY@@AEB_N@Z; NetSetup2::ActiveObject::SetPropertyToValue<17,bool>(_NETSETUPPROPKEY const &,bool const &)
0x1800225ca  mov     rcx, rsi; this
0x1800225cd  call    ?Delete@ActiveObject@NetSetup2@@QEAAXXZ; NetSetup2::ActiveObject::Delete(void)
0x1800225d2  mov     r9, r15
0x1800225d5  mov     r8, r14
0x1800225d8  mov     rdx, r12
0x1800225db  lea     rcx, [rsp+130h+var_D8]
0x1800225e0  call    CreateNewNetworkInterface
0x1800225e5  movups  xmm0, xmmword ptr [rax]
0x1800225e8  movdqu  [rbp+4Fh+var_48], xmm0
0x1800225ed  lea     r8, NETSETUPPKEY_Interface_PnpDeviceInterfaceNumber
0x1800225f4  lea     rdx, [rbp+4Fh+var_78]; struct _NETSETUPPROPKEY *
0x1800225f8  mov     rcx, r14; this
0x1800225fb  call    ?GetProperty@ObjectCreationTemplate@NetSetup2@@QEBA?AVProperty@2@AEBU_NETSETUPPROPKEY@@@Z; NetSetup2::ObjectCreationTemplate::GetProperty(_NETSETUPPROPKEY const &)
0x180022600  nop
0x180022601  cmp     [rbp+4Fh+var_64], 0
0x180022605  jnz     short loc_18002260B
0x180022607  xor     ebx, ebx
0x180022609  jmp     short loc_180022616
0x18002260b  lea     rcx, [rbp+4Fh+var_78]; this
0x18002260f  call    ?GetUint32@Property@NetSetup2@@QEBAKXZ; NetSetup2::Property::GetUint32(void)
0x180022614  mov     ebx, eax
0x180022616  lea     rcx, [rbp+4Fh+var_60]
0x18002261a  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18002261f  test    ebx, ebx
0x180022621  jnz     short loc_180022634
0x180022623  lea     r8, [rbp+4Fh+var_48]
0x180022627  lea     rdx, [rbp+4Fh+var_B0]
0x18002262b  mov     rcx, r12
0x18002262e  call    FinalizeNewlyCreatedNetworkInterface
0x180022633  nop
0x180022634  lea     rcx, [rbp+4Fh+var_A8]
0x180022638  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002263d  nop
0x18002263e  lea     rcx, [rbp+4Fh+var_B0]
0x180022642  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180022647  mov     rcx, [rbp+4Fh+var_38]
0x18002264b  xor     rcx, rsp; StackCookie
0x18002264e  call    __security_check_cookie
0x180022653  add     rsp, 100h
0x18002265a  pop     r15
0x18002265c  pop     r14
0x18002265e  pop     r12
0x180022660  pop     rdi
0x180022661  pop     rsi
0x180022662  pop     rbx
0x180022663  pop     rbp
0x180022664  retn
```
