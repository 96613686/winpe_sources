# Microsoft::Bluetooth::Protocols::Avctp::AvctpRadioEnumerator::InitGmcsHandler(void)

- ea: `0x18002de00`
- end: `0x18002df8e`
- name: `?InitGmcsHandler@AvctpRadioEnumerator@Avctp@Protocols@Bluetooth@Microsoft@@AEAAXXZ`
- size: `398`
- prototype: `void __fastcall(Microsoft::Bluetooth::Protocols::Avctp::AvctpRadioEnumerator *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002e1e0`

## callees

- `0x18000d0c0`
- `0x18000de78`
- `0x18000e0c0`
- `0x1800266f8`
- `0x18002c40c`
- `0x18002c4ac`
- `0x18002d050`
- `0x18002de00`
- `0x18003381c`
- `0x18005f010`

## string_xrefs

- `0x18002de59`: `onecore\drivers\bluetooth\profiles\avrcp\avctp\service\lib\avctpradioenumerator.cpp`
- `0x18002deba`: `onecore\drivers\bluetooth\profiles\avrcp\avctp\service\lib\avctpradioenumerator.cpp`
- `0x18002df00`: `onecore\drivers\bluetooth\profiles\avrcp\avctp\service\lib\avctpradioenumerator.cpp`
- `0x18002df30`: `onecore\drivers\bluetooth\profiles\avrcp\avctp\service\lib\avctpradioenumerator.cpp`
- `0x18002df64`: `onecore\drivers\bluetooth\profiles\avrcp\avctp\service\lib\avctpradioenumerator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall Microsoft::Bluetooth::Protocols::Avctp::AvctpRadioEnumerator::InitGmcsHandler(
        Microsoft::Bluetooth::Protocols::Avctp::AvctpRadioEnumerator *this)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rsi
  int v4; // eax
  __int64 v5; // rdx
  char v6; // r8
  __int64 v7; // rcx
  __int64 v8; // rbx
  __int64 (__fastcall *v9)(__int64, _QWORD, char *); // rdi
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // [rsp+20h] [rbp-28h] BYREF
  std::_Ref_count_base *v14; // [rsp+28h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v16; // [rsp+50h] [rbp+8h] BYREF
  __int64 v17; // [rsp+58h] [rbp+10h] BYREF
  __int64 v18; // [rsp+60h] [rbp+18h] BYREF

  v2 = (_QWORD *)Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Profiles::Avrcp::AvrcpMediaControllerProxySingleton,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Profiles::Avrcp::AvrcpMediaControllerProxySingleton>>::Instance(&v13);
  v18 = *(_QWORD *)Microsoft::Bluetooth::Profiles::Avrcp::AvrcpMediaControllerProxySingleton::Get(*v2, &v16);
  v3 = (_QWORD *)((char *)this + 520);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 520);
  v4 = Microsoft::WRL::Details::MakeAndInitialize<Microsoft::Bluetooth::Profiles::MediaControl::Interface::MediaControlOperationHandler,Microsoft::Bluetooth::Profiles::MediaControl::Interface::IMediaControlOperationHandler,IBthAvMediaController *>(
         (char *)this + 520,
         &v18);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB1,
      (unsigned int)"onecore\\drivers\\bluetooth\\profiles\\avrcp\\avctp\\service\\lib\\avctpradioenumerator.cpp",
      (const char *)(unsigned int)v4,
      v13);
  v7 = v16;
  if ( v16 )
  {
    v16 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  }
  if ( v14 )
    std::_Ref_count_base::_Decref(v14);
  wil::GetActivationFactory<Microsoft::Bluetooth::Profiles::MediaControl::Interface::IMediaControlServiceStatics>(
    (const WCHAR *)&v17,
    v5,
    v6);
  v8 = v17;
  if ( !v17 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB4,
      (unsigned int)"onecore\\drivers\\bluetooth\\profiles\\avrcp\\avctp\\service\\lib\\avctpradioenumerator.cpp",
      (const char *)0x80004002LL,
      v13);
  v9 = *(__int64 (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)v17 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 528);
  v10 = v9(v8, *v3, (char *)this + 528);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB5,
      (unsigned int)"onecore\\drivers\\bluetooth\\profiles\\avrcp\\avctp\\service\\lib\\avctpradioenumerator.cpp",
      (const char *)(unsigned int)v10,
      v13);
  v11 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v3 + 128LL))(*v3);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB7,
      (unsigned int)"onecore\\drivers\\bluetooth\\profiles\\avrcp\\avctp\\service\\lib\\avctpradioenumerator.cpp",
      (const char *)(unsigned int)v11,
      v13);
  v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v3 + 120LL))(*v3, *((_QWORD *)this + 66));
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB8,
      (unsigned int)"onecore\\drivers\\bluetooth\\profiles\\avrcp\\avctp\\service\\lib\\avctpradioenumerator.cpp",
      (const char *)(unsigned int)v12,
      v13);
  wil::com_ptr_t<Microsoft::Bluetooth::Profiles::Cap::Interface::ICapEndpointEnumeratorStatics,wil::err_exception_policy>::~com_ptr_t<Microsoft::Bluetooth::Profiles::Cap::Interface::ICapEndpointEnumeratorStatics,wil::err_exception_policy>(&v17);
}

```

## disassembly

```asm
0x18002de00  mov     [rsp+arg_18], rbx
0x18002de05  push    rsi
0x18002de06  push    rdi
0x18002de07  push    r14
0x18002de09  sub     rsp, 30h
0x18002de0d  mov     r14, rcx
0x18002de10  lea     rcx, [rsp+48h+var_28]
0x18002de15  call    ?Instance@?$SingletonWithFactory@VAvrcpMediaControllerProxySingleton@Avrcp@Profiles@Bluetooth@Microsoft@@U?$SingletonDefaultFactory@VAvrcpMediaControllerProxySingleton@Avrcp@Profiles@Bluetooth@Microsoft@@@Foundation@45@@Foundation@Bluetooth@Microsoft@@SA?AV?$shared_ptr@VAvrcpMediaControllerProxySingleton@Avrcp@Profiles@Bluetooth@Microsoft@@@std@@XZ; Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Profiles::Avrcp::AvrcpMediaControllerProxySingleton,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Profiles::Avrcp::AvrcpMediaControllerProxySingleton>>::Instance(void)
0x18002de1a  nop
0x18002de1b  lea     rdx, [rsp+48h+arg_0]
0x18002de20  mov     rcx, [rax]
0x18002de23  call    ?Get@AvrcpMediaControllerProxySingleton@Avrcp@Profiles@Bluetooth@Microsoft@@QEAA?AV?$ComPtr@UIBthAvMediaController@@@WRL@5@XZ; Microsoft::Bluetooth::Profiles::Avrcp::AvrcpMediaControllerProxySingleton::Get(void)
0x18002de28  nop
0x18002de29  mov     rax, [rax]
0x18002de2c  mov     [rsp+48h+arg_10], rax
0x18002de31  lea     rsi, [r14+208h]
0x18002de38  mov     rcx, rsi
0x18002de3b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002de40  lea     rdx, [rsp+48h+arg_10]
0x18002de45  mov     rcx, rsi
0x18002de48  call    ??$MakeAndInitialize@VMediaControlOperationHandler@Interface@MediaControl@Profiles@Bluetooth@Microsoft@@UIMediaControlOperationHandler@23456@PEAUIBthAvMediaController@@@Details@WRL@Microsoft@@YAJPEAPEAUIMediaControlOperationHandler@Interface@MediaControl@Profiles@Bluetooth@2@$$QEAPEAUIBthAvMediaController@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Microsoft::Bluetooth::Profiles::MediaControl::Interface::MediaControlOperationHandler,Microsoft::Bluetooth::Profiles::MediaControl::Interface::IMediaControlOperationHandler,IBthAvMediaController *>(Microsoft::Bluetooth::Profiles::MediaControl::Interface::IMediaControlOperationHandler * *,IBthAvMediaController * &&)
0x18002de4d  mov     rcx, [rsp+48h]; this
0x18002de52  test    eax, eax
0x18002de54  jns     short loc_18002DE6B
0x18002de56  mov     r9d, eax; char *
0x18002de59  lea     r8, aOnecoreDrivers_41; "onecore\\drivers\\bluetooth\\profiles\\"...
0x18002de60  mov     edx, 0B1h; void *
0x18002de65  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002de6b  mov     rcx, [rsp+48h+arg_0]
0x18002de70  test    rcx, rcx
0x18002de73  jz      short loc_18002DE8B
0x18002de75  mov     [rsp+48h+arg_0], 0
0x18002de7e  mov     rax, [rcx]
0x18002de81  mov     rax, [rax+10h]
0x18002de85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002de8a  nop
0x18002de8b  mov     rcx, [rsp+48h+var_20]; this
0x18002de90  test    rcx, rcx
0x18002de93  jz      short loc_18002DE9A
0x18002de95  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002de9a  lea     rcx, [rsp+48h+arg_8]
0x18002de9f  call    ??$GetActivationFactory@UIMediaControlServiceStatics@Interface@MediaControl@Profiles@Bluetooth@Microsoft@@@wil@@YA?AV?$com_ptr_t@UIMediaControlServiceStatics@Interface@MediaControl@Profiles@Bluetooth@Microsoft@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<Microsoft::Bluetooth::Profiles::MediaControl::Interface::IMediaControlServiceStatics>(ushort const *)
0x18002dea4  nop
0x18002dea5  mov     rcx, [rsp+48h]; this
0x18002deaa  mov     rbx, [rsp+48h+arg_8]
0x18002deaf  test    rbx, rbx
0x18002deb2  jnz     short loc_18002DECC
0x18002deb4  mov     r9d, 80004002h; char *
0x18002deba  lea     r8, aOnecoreDrivers_41; "onecore\\drivers\\bluetooth\\profiles\\"...
0x18002dec1  mov     edx, 0B4h; void *
0x18002dec6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002decc  mov     rax, [rbx]
0x18002decf  mov     rdi, [rax+30h]
0x18002ded3  lea     rcx, [r14+210h]
0x18002deda  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002dedf  lea     r8, [r14+210h]
0x18002dee6  mov     rdx, [rsi]
0x18002dee9  mov     rcx, rbx
0x18002deec  mov     rax, rdi
0x18002deef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002def4  mov     rcx, [rsp+48h]; this
0x18002def9  test    eax, eax
0x18002defb  jns     short loc_18002DF12
0x18002defd  mov     r9d, eax; char *
0x18002df00  lea     r8, aOnecoreDrivers_41; "onecore\\drivers\\bluetooth\\profiles\\"...
0x18002df07  mov     edx, 0B5h; void *
0x18002df0c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002df12  mov     rcx, [rsi]
0x18002df15  mov     rax, [rcx]
0x18002df18  mov     rax, [rax+80h]
0x18002df1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002df24  mov     rcx, [rsp+48h]; this
0x18002df29  test    eax, eax
0x18002df2b  jns     short loc_18002DF42
0x18002df2d  mov     r9d, eax; char *
0x18002df30  lea     r8, aOnecoreDrivers_41; "onecore\\drivers\\bluetooth\\profiles\\"...
0x18002df37  mov     edx, 0B7h; void *
0x18002df3c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002df42  mov     rcx, [rsi]
0x18002df45  mov     rax, [rcx]
0x18002df48  mov     rdx, [r14+210h]
0x18002df4f  mov     rax, [rax+78h]
0x18002df53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002df58  mov     rcx, [rsp+48h]; this
0x18002df5d  test    eax, eax
0x18002df5f  jns     short loc_18002DF76
0x18002df61  mov     r9d, eax; char *
0x18002df64  lea     r8, aOnecoreDrivers_41; "onecore\\drivers\\bluetooth\\profiles\\"...
0x18002df6b  mov     edx, 0B8h; void *
0x18002df70  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002df76  lea     rcx, [rsp+48h+arg_8]
0x18002df7b  call    ??1?$com_ptr_t@UICapEndpointEnumeratorStatics@Interface@Cap@Profiles@Bluetooth@Microsoft@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Microsoft::Bluetooth::Profiles::Cap::Interface::ICapEndpointEnumeratorStatics,wil::err_exception_policy>::~com_ptr_t<Microsoft::Bluetooth::Profiles::Cap::Interface::ICapEndpointEnumeratorStatics,wil::err_exception_policy>(void)
0x18002df80  mov     rbx, [rsp+48h+arg_18]
0x18002df85  add     rsp, 30h
0x18002df89  pop     r14
0x18002df8b  pop     rdi
0x18002df8c  pop     rsi
0x18002df8d  retn
```
