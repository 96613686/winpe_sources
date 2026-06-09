# Microsoft::Bluetooth::Protocols::Avctp::AvctpServiceHost::OnStart(void)

- ea: `0x180027b9c`
- end: `0x180027eb7`
- name: `?OnStart@AvctpServiceHost@Avctp@Protocols@Bluetooth@Microsoft@@QEAAXXZ`
- size: `795`
- prototype: `void __fastcall(Microsoft::Bluetooth::Protocols::Avctp::AvctpServiceHost *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b710`

## callees

- `0x1800021dc`
- `0x18000b3f0`
- `0x18000b69c`
- `0x18000b810`
- `0x18000c850`
- `0x18000de78`
- `0x18000e0c0`
- `0x180012554`
- `0x1800266f8`
- `0x1800273fc`
- `0x18002791c`
- `0x180027970`
- `0x180027b9c`
- `0x180028160`
- `0x18002e05c`
- `0x18002fa40`
- `0x180046e7c`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180027e86`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180027c3a`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180027c3a`

## string_xrefs

- `0x180027e90`: `onecore\drivers\bluetooth\foundation\lib\ComServiceModule.h`
- `0x180027ea5`: `onecore\drivers\bluetooth\profiles\avrcp\avctp\service\lib\avctpservicehost.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Microsoft::Bluetooth::Protocols::Avctp::AvctpServiceHost::OnStart(
        Microsoft::Bluetooth::Protocols::Avctp::AvctpServiceHost *this)
{
  char v2; // dl
  char v3; // r8
  int v4; // eax
  __int64 v5; // rax
  std::_Ref_count_base *v6; // rcx
  __int64 v7; // rcx
  __int64 *Shared; // rax
  __int64 v9; // rcx
  __int64 v10; // rdx
  std::_Ref_count_base *v11; // rcx
  std::_Ref_count_base *v12; // rdx
  std::_Ref_count_base *v13; // rcx
  __int64 v14; // rax
  __int64 *v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rdx
  std::_Ref_count_base *v18; // rcx
  __int64 v19; // rdi
  __int64 v20; // rax
  __int64 v21; // rdx
  const unsigned __int16 *v22; // rdx
  int v23; // eax
  char v24; // dl
  char v25; // r8
  int v26; // [rsp+20h] [rbp-50h]
  std::_Ref_count_base *v27[2]; // [rsp+50h] [rbp-20h] BYREF
  _BYTE v28[8]; // [rsp+60h] [rbp-10h] BYREF
  std::_Ref_count_base *v29; // [rsp+68h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  Microsoft::Bluetooth::Foundation::MtaReference *v31; // [rsp+A8h] [rbp+38h] BYREF
  int v32; // [rsp+B0h] [rbp+40h]

  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || (v2 = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u) )
  {
    v2 = 0;
  }
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    || (v3 = 1, !*((_WORD *)WPP_GLOBAL_Control + 24)) )
  {
    v3 = 0;
  }
  if ( v2 || v3 )
    WPP_RECORDER_AND_TRACE_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v2,
      v3,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      5,
      1,
      10,
      &WPP_79edd0d2b9a03db1d70daf21b10a07c1_Traceguids,
      (char)this);
  v4 = RoInitialize(1);
  v32 = v4;
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x22,
      (unsigned int)"onecore\\drivers\\bluetooth\\profiles\\avrcp\\avctp\\service\\lib\\avctpservicehost.cpp",
      (const char *)(unsigned int)v4,
      v26);
  v5 = Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Profiles::Avrcp::AvrcpMediaControllerProxySingleton,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Profiles::Avrcp::AvrcpMediaControllerProxySingleton>>::Instance(v27);
  std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncDeviceInterfaceWatcher>::operator=((char *)this + 192, v5);
  v6 = v27[1];
  if ( v27[1] )
    std::_Ref_count_base::_Decref(v27[1]);
  LOBYTE(v31) = 0;
  wil::wnf_publish<Microsoft::Bluetooth::Protocols::Avctp::AvctpServiceInitializationState>((__int64)v6, (__int64)&v31);
  LOBYTE(v31) = 1;
  wil::wnf_publish<Microsoft::Bluetooth::Protocols::Avctp::AvctpServiceInitializationState>(v7, (__int64)&v31);
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 23) + 8LL))(*((_QWORD *)this + 23));
  Shared = (__int64 *)Microsoft::Bluetooth::Protocols::Avctp::AvctpRadioEnumerator::MakeShared(v27);
  v9 = *Shared;
  v10 = Shared[1];
  *Shared = 0;
  Shared[1] = 0;
  *((_QWORD *)this + 15) = v9;
  v11 = (std::_Ref_count_base *)*((_QWORD *)this + 16);
  *((_QWORD *)this + 16) = v10;
  if ( v11 )
    std::_Ref_count_base::_Decref(v11);
  if ( v27[1] )
    std::_Ref_count_base::_Decref(v27[1]);
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 21) + 8LL))(*((_QWORD *)this + 21));
  Microsoft::Bluetooth::Profiles::Avrcp::Details::AvrcpTransportAdapterEnumerator::MakeShared(v27);
  v12 = v27[1];
  *((std::_Ref_count_base **)this + 17) = v27[0];
  v13 = (std::_Ref_count_base *)*((_QWORD *)this + 18);
  *((_QWORD *)this + 18) = v12;
  if ( v13 )
    std::_Ref_count_base::_Decref(v13);
  *(_OWORD *)v27 = 0;
  v14 = *((_QWORD *)this + 18);
  if ( v14 )
    _InterlockedIncrement((volatile signed __int32 *)(v14 + 8));
  v27[0] = *((std::_Ref_count_base **)this + 17);
  v27[1] = *((std::_Ref_count_base **)this + 18);
  v15 = (__int64 *)Microsoft::Bluetooth::Protocols::Avctp::AvctpProfileServiceProvider::MakeShared(v28, v27);
  v16 = *v15;
  v17 = v15[1];
  *v15 = 0;
  v15[1] = 0;
  *((_QWORD *)this + 19) = v16;
  v18 = (std::_Ref_count_base *)*((_QWORD *)this + 20);
  *((_QWORD *)this + 20) = v17;
  if ( v18 )
    std::_Ref_count_base::_Decref(v18);
  if ( v29 )
    std::_Ref_count_base::_Decref(v29);
  Microsoft::Bluetooth::Foundation::ComServiceModule::IncrementObjectCount(*((Microsoft::Bluetooth::Foundation::ComServiceModule **)this
                                                                           + 22));
  v19 = *((_QWORD *)this + 22);
  v31 = (Microsoft::Bluetooth::Foundation::MtaReference *)operator new(0x18u);
  v20 = Microsoft::Bluetooth::Foundation::MtaReference::MtaReference(v31);
  v31 = 0;
  v21 = *(_QWORD *)(v19 + 40);
  *(_QWORD *)(v19 + 40) = v20;
  if ( v21 )
    std::default_delete<Microsoft::Bluetooth::Foundation::MtaReference>::operator()();
  std::unique_ptr<Microsoft::Bluetooth::Foundation::MtaReference>::~unique_ptr<Microsoft::Bluetooth::Foundation::MtaReference>(&v31);
  if ( *(_BYTE *)(v19 + 20) )
    v23 = Microsoft::Bluetooth::Foundation::ComServiceModule::RegisterContextObjects(
            (Microsoft::Bluetooth::Foundation::ComServiceModule *)v19,
            v22);
  else
    v23 = Microsoft::WRL::Details::RegisterObjects<2>(v19, 0);
  if ( v23 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x44,
      (unsigned int)"onecore\\drivers\\bluetooth\\foundation\\lib\\ComServiceModule.h",
      (const char *)(unsigned int)v23,
      v26);
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || (v24 = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u) )
  {
    v24 = 0;
  }
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    || (v25 = 1, !*((_WORD *)WPP_GLOBAL_Control + 24)) )
  {
    v25 = 0;
  }
  if ( v24 || v25 )
    WPP_RECORDER_AND_TRACE_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v24,
      v25,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      5,
      1,
      11,
      &WPP_79edd0d2b9a03db1d70daf21b10a07c1_Traceguids,
      (char)this);
  RoUninitialize();
}

```

## disassembly

```asm
0x180027b9c  mov     [rsp-28h+arg_0], rbx
0x180027ba1  mov     [rsp-28h+arg_18], rsi
0x180027ba6  push    rbp
0x180027ba7  push    rdi
0x180027ba8  push    r12
0x180027baa  push    r13
0x180027bac  push    r15
0x180027bae  mov     rbp, rsp
0x180027bb1  sub     rsp, 70h
0x180027bb5  mov     rbx, rcx
0x180027bb8  xor     esi, esi
0x180027bba  lea     r15, WPP_GLOBAL_Control
0x180027bc1  mov     rcx, cs:WPP_GLOBAL_Control
0x180027bc8  cmp     rcx, r15
0x180027bcb  jz      short loc_180027BDB
0x180027bcd  test    byte ptr [rcx+1Ch], 1
0x180027bd1  jz      short loc_180027BDB
0x180027bd3  cmp     byte ptr [rcx+19h], 5
0x180027bd7  mov     dl, 1
0x180027bd9  jnb     short loc_180027BDE
0x180027bdb  mov     dl, sil; int
0x180027bde  lea     r12, WPP_RECORDER_INITIALIZED
0x180027be5  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180027bec  jz      short loc_180027BF7
0x180027bee  cmp     [rcx+30h], si
0x180027bf2  mov     r8b, 1
0x180027bf5  jnz     short loc_180027BFA
0x180027bf7  mov     r8b, sil; int
0x180027bfa  lea     r13, WPP_79edd0d2b9a03db1d70daf21b10a07c1_Traceguids
0x180027c01  test    dl, dl
0x180027c03  jnz     short loc_180027C0A
0x180027c05  test    r8b, r8b
0x180027c08  jz      short loc_180027C35
0x180027c0a  mov     qword ptr [rsp+70h+var_30], rbx; char
0x180027c0f  mov     [rsp+70h+MessageGuid], r13; MessageGuid
0x180027c14  mov     [rsp+70h+var_40], 0Ah; __int16
0x180027c1b  mov     [rsp+70h+var_48], 1; int
0x180027c23  mov     [rsp+70h+var_50], 5; int
0x180027c28  mov     r9, [rcx+28h]; int
0x180027c2c  mov     rcx, [rcx+10h]; int
0x180027c30  call    WPP_RECORDER_AND_TRACE_SF_q
0x180027c35  mov     ecx, 1
0x180027c3a  call    cs:__imp_RoInitialize
0x180027c40  mov     [rbp+arg_10], eax
0x180027c43  mov     rcx, [rbp+28h]; this
0x180027c47  test    eax, eax
0x180027c49  js      loc_180027EA2
0x180027c4f  lea     rcx, [rbp+var_20]
0x180027c53  call    ?Instance@?$SingletonWithFactory@VAvrcpMediaControllerProxySingleton@Avrcp@Profiles@Bluetooth@Microsoft@@U?$SingletonDefaultFactory@VAvrcpMediaControllerProxySingleton@Avrcp@Profiles@Bluetooth@Microsoft@@@Foundation@45@@Foundation@Bluetooth@Microsoft@@SA?AV?$shared_ptr@VAvrcpMediaControllerProxySingleton@Avrcp@Profiles@Bluetooth@Microsoft@@@std@@XZ; Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Profiles::Avrcp::AvrcpMediaControllerProxySingleton,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Profiles::Avrcp::AvrcpMediaControllerProxySingleton>>::Instance(void)
0x180027c58  lea     rcx, [rbx+0C0h]
0x180027c5f  mov     rdx, rax
0x180027c62  call    ??4?$shared_ptr@VAsyncDeviceInterfaceWatcher@Foundation@Bluetooth@Microsoft@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncDeviceInterfaceWatcher>::operator=(std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncDeviceInterfaceWatcher> &&)
0x180027c67  mov     rcx, [rbp+var_20+8]; this
0x180027c6b  test    rcx, rcx
0x180027c6e  jz      short loc_180027C75
0x180027c70  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180027c75  mov     byte ptr [rbp+arg_8], sil
0x180027c79  lea     rdx, [rbp+arg_8]
0x180027c7d  call    ??$wnf_publish@UAvctpServiceInitializationState@Avctp@Protocols@Bluetooth@Microsoft@@@wil@@YAXAEBU_WNF_STATE_NAME@@AEBUAvctpServiceInitializationState@Avctp@Protocols@Bluetooth@Microsoft@@@Z; wil::wnf_publish<Microsoft::Bluetooth::Protocols::Avctp::AvctpServiceInitializationState>(_WNF_STATE_NAME const &,Microsoft::Bluetooth::Protocols::Avctp::AvctpServiceInitializationState const &)
0x180027c82  mov     byte ptr [rbp+arg_8], 1
0x180027c86  lea     rdx, [rbp+arg_8]
0x180027c8a  call    ??$wnf_publish@UAvctpServiceInitializationState@Avctp@Protocols@Bluetooth@Microsoft@@@wil@@YAXAEBU_WNF_STATE_NAME@@AEBUAvctpServiceInitializationState@Avctp@Protocols@Bluetooth@Microsoft@@@Z; wil::wnf_publish<Microsoft::Bluetooth::Protocols::Avctp::AvctpServiceInitializationState>(_WNF_STATE_NAME const &,Microsoft::Bluetooth::Protocols::Avctp::AvctpServiceInitializationState const &)
0x180027c8f  mov     rcx, [rbx+0B8h]
0x180027c96  mov     rax, [rcx]
0x180027c99  mov     rax, [rax+8]
0x180027c9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027ca2  lea     rcx, [rbp+var_20]
0x180027ca6  call    ?MakeShared@AvctpRadioEnumerator@Avctp@Protocols@Bluetooth@Microsoft@@SA?AV?$shared_ptr@VAvctpRadioEnumerator@Avctp@Protocols@Bluetooth@Microsoft@@@std@@XZ; Microsoft::Bluetooth::Protocols::Avctp::AvctpRadioEnumerator::MakeShared(void)
0x180027cab  mov     rcx, [rax]
0x180027cae  mov     rdx, [rax+8]
0x180027cb2  mov     [rax], rsi
0x180027cb5  mov     [rax+8], rsi
0x180027cb9  mov     [rbx+78h], rcx
0x180027cbd  mov     rcx, [rbx+80h]; this
0x180027cc4  mov     [rbx+80h], rdx
0x180027ccb  test    rcx, rcx
0x180027cce  jz      short loc_180027CD5
0x180027cd0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180027cd5  mov     rcx, [rbp+var_20+8]; this
0x180027cd9  test    rcx, rcx
0x180027cdc  jz      short loc_180027CE3
0x180027cde  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180027ce3  mov     rcx, [rbx+0A8h]
0x180027cea  mov     rax, [rcx]
0x180027ced  mov     rax, [rax+8]
0x180027cf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027cf6  lea     rcx, [rbp+var_20]
0x180027cfa  call    ?MakeShared@AvrcpTransportAdapterEnumerator@Details@Avrcp@Profiles@Bluetooth@Microsoft@@SA?AV?$shared_ptr@VAvrcpTransportEnumerator@Avrcp@Profiles@Bluetooth@Microsoft@@@std@@XZ; Microsoft::Bluetooth::Profiles::Avrcp::Details::AvrcpTransportAdapterEnumerator::MakeShared(void)
0x180027cff  mov     rax, [rbp+var_20]
0x180027d03  mov     rdx, [rbp+var_20+8]
0x180027d07  mov     [rbx+88h], rax
0x180027d0e  mov     rcx, [rbx+90h]; this
0x180027d15  mov     [rbx+90h], rdx
0x180027d1c  test    rcx, rcx
0x180027d1f  jz      short loc_180027D26
0x180027d21  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180027d26  xorps   xmm0, xmm0
0x180027d29  movdqu  xmmword ptr [rbp+var_20], xmm0
0x180027d2e  mov     rax, [rbx+90h]
0x180027d35  test    rax, rax
0x180027d38  jz      short loc_180027D3E
0x180027d3a  lock inc dword ptr [rax+8]
0x180027d3e  mov     rax, [rbx+88h]
0x180027d45  mov     [rbp+var_20], rax
0x180027d49  mov     rax, [rbx+90h]
0x180027d50  mov     [rbp+var_20+8], rax
0x180027d54  lea     rdx, [rbp+var_20]
0x180027d58  lea     rcx, [rbp+var_10]
0x180027d5c  call    ?MakeShared@AvctpProfileServiceProvider@Avctp@Protocols@Bluetooth@Microsoft@@SA?AV?$shared_ptr@VAvctpProfileServiceProvider@Avctp@Protocols@Bluetooth@Microsoft@@@std@@V?$shared_ptr@VAvrcpTransportEnumerator@Avrcp@Profiles@Bluetooth@Microsoft@@@7@@Z; Microsoft::Bluetooth::Protocols::Avctp::AvctpProfileServiceProvider::MakeShared(std::shared_ptr<Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransportEnumerator>)
0x180027d61  mov     rcx, [rax]
0x180027d64  mov     rdx, [rax+8]
0x180027d68  mov     [rax], rsi
0x180027d6b  mov     [rax+8], rsi
0x180027d6f  mov     [rbx+98h], rcx
0x180027d76  mov     rcx, [rbx+0A0h]; this
0x180027d7d  mov     [rbx+0A0h], rdx
0x180027d84  test    rcx, rcx
0x180027d87  jz      short loc_180027D8E
0x180027d89  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180027d8e  mov     rcx, [rbp+var_8]; this
0x180027d92  test    rcx, rcx
0x180027d95  jz      short loc_180027D9C
0x180027d97  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180027d9c  mov     rcx, [rbx+0B0h]; this
0x180027da3  call    ?IncrementObjectCount@ComServiceModule@Foundation@Bluetooth@Microsoft@@UEAAKXZ; Microsoft::Bluetooth::Foundation::ComServiceModule::IncrementObjectCount(void)
0x180027da8  mov     rdi, [rbx+0B0h]
0x180027daf  mov     ecx, 18h; Size
0x180027db4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180027db9  mov     [rbp+arg_8], rax
0x180027dbd  mov     rcx, rax; this
0x180027dc0  call    ??0MtaReference@Foundation@Bluetooth@Microsoft@@QEAA@XZ; Microsoft::Bluetooth::Foundation::MtaReference::MtaReference(void)
0x180027dc5  mov     [rbp+arg_8], rsi
0x180027dc9  mov     rdx, [rdi+28h]
0x180027dcd  mov     [rdi+28h], rax
0x180027dd1  test    rdx, rdx
0x180027dd4  jz      short loc_180027DDB
0x180027dd6  call    ??R?$default_delete@VMtaReference@Foundation@Bluetooth@Microsoft@@@std@@QEBAXPEAVMtaReference@Foundation@Bluetooth@Microsoft@@@Z; std::default_delete<Microsoft::Bluetooth::Foundation::MtaReference>::operator()(Microsoft::Bluetooth::Foundation::MtaReference *)
0x180027ddb  lea     rcx, [rbp+arg_8]
0x180027ddf  call    ??1?$unique_ptr@VMtaReference@Foundation@Bluetooth@Microsoft@@U?$default_delete@VMtaReference@Foundation@Bluetooth@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::Bluetooth::Foundation::MtaReference>::~unique_ptr<Microsoft::Bluetooth::Foundation::MtaReference>(void)
0x180027de4  mov     rcx, rdi; this
0x180027de7  cmp     [rdi+14h], sil
0x180027deb  jz      short loc_180027DF4
0x180027ded  call    ?RegisterContextObjects@ComServiceModule@Foundation@Bluetooth@Microsoft@@AEAAJPEBG@Z; Microsoft::Bluetooth::Foundation::ComServiceModule::RegisterContextObjects(ushort const *)
0x180027df2  jmp     short loc_180027DFB
0x180027df4  xor     edx, edx
0x180027df6  call    ??$RegisterObjects@$01@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBG@Z; Microsoft::WRL::Details::RegisterObjects<2>(Microsoft::WRL::Details::ModuleBase *,ushort const *)
0x180027dfb  mov     rcx, [rbp+28h]; this
0x180027dff  test    eax, eax
0x180027e01  js      loc_180027E8D
0x180027e07  mov     rcx, cs:WPP_GLOBAL_Control
0x180027e0e  cmp     rcx, r15
0x180027e11  jz      short loc_180027E21
0x180027e13  test    byte ptr [rcx+1Ch], 1
0x180027e17  jz      short loc_180027E21
0x180027e19  cmp     byte ptr [rcx+19h], 5
0x180027e1d  mov     dl, 1
0x180027e1f  jnb     short loc_180027E24
0x180027e21  mov     dl, sil; int
0x180027e24  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180027e2b  jz      short loc_180027E36
0x180027e2d  cmp     [rcx+30h], si
0x180027e31  mov     r8b, 1
0x180027e34  jnz     short loc_180027E39
0x180027e36  mov     r8b, sil; int
0x180027e39  test    dl, dl
0x180027e3b  jnz     short loc_180027E42
0x180027e3d  test    r8b, r8b
0x180027e40  jz      short loc_180027E6E
0x180027e42  mov     qword ptr [rsp+70h+var_30], rbx; char
0x180027e47  mov     [rsp+70h+MessageGuid], r13; MessageGuid
0x180027e4c  mov     [rsp+70h+var_40], 0Bh; __int16
0x180027e53  mov     [rsp+70h+var_48], 1; int
0x180027e5b  mov     [rsp+70h+var_50], 5; char
0x180027e60  mov     r9, [rcx+28h]; int
0x180027e64  mov     rcx, [rcx+10h]; int
0x180027e68  call    WPP_RECORDER_AND_TRACE_SF_q
0x180027e6d  nop
0x180027e6e  lea     r11, [rsp+70h+var_s0]
0x180027e73  mov     rbx, [r11+30h]
0x180027e77  mov     rsi, [r11+48h]
0x180027e7b  mov     rsp, r11
0x180027e7e  pop     r15
0x180027e80  pop     r13
0x180027e82  pop     r12
0x180027e84  pop     rdi
0x180027e85  pop     rbp
0x180027e86  jmp     cs:__imp_RoUninitialize
0x180027e8d  mov     r9d, eax; char *
0x180027e90  lea     r8, aOnecoreDrivers_6; "onecore\\drivers\\bluetooth\\foundation"...
0x180027e97  mov     edx, 44h ; 'D'; void *
0x180027e9c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180027ea2  mov     r9d, eax; char *
0x180027ea5  lea     r8, aOnecoreDrivers_34; "onecore\\drivers\\bluetooth\\profiles\\"...
0x180027eac  mov     edx, 22h ; '"'; void *
0x180027eb1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
