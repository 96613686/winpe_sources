# Microsoft::Bluetooth::Protocols::Avctp::AvctpServiceHost::OnStop(void)

- ea: `0x180027ec0`
- end: `0x18002815a`
- name: `?OnStop@AvctpServiceHost@Avctp@Protocols@Bluetooth@Microsoft@@QEAAXXZ`
- size: `666`
- prototype: `void __fastcall(Microsoft::Bluetooth::Protocols::Avctp::AvctpServiceHost *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000c020`

## callees

- `0x180004060`
- `0x18000c230`
- `0x18000db6c`
- `0x18000de78`
- `0x18000dfec`
- `0x18000e0c0`
- `0x180012554`
- `0x18002791c`
- `0x180027b44`
- `0x180027ec0`
- `0x180028230`
- `0x18002fb00`
- `0x1800334f8`
- `0x180034928`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002805c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002805c`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18002813e`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180027f70`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180027f70`

## string_xrefs

- `0x180027fa2`: `onecore\drivers\bluetooth\profiles\avrcp\avctp\service\lib\avctpservicehost.cpp`
- `0x180027feb`: `onecore\drivers\bluetooth\profiles\avrcp\avctp\service\lib\avctpservicehost.cpp`
- `0x180028148`: `onecore\drivers\bluetooth\profiles\avrcp\avctp\service\lib\avctpservicehost.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Microsoft::Bluetooth::Protocols::Avctp::AvctpServiceHost::OnStop(
        Microsoft::Bluetooth::Foundation::ComServiceModule **this)
{
  PVOID v2; // rcx
  char v3; // dl
  char v4; // r8
  int v5; // eax
  const unsigned __int16 *v6; // rdx
  bool v7; // r8
  int v8; // eax
  const unsigned __int16 *v9; // r8
  bool v10; // r9
  std::_Ref_count_base *v11; // rcx
  RTL_SRWLOCK *v12; // rdi
  std::_Ref_count_base *v13; // rcx
  char v14; // dl
  char v15; // r8
  int v16; // [rsp+20h] [rbp-58h]
  char *v17; // [rsp+30h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  int v19; // [rsp+88h] [rbp+10h] BYREF
  RTL_SRWLOCK *v20; // [rsp+90h] [rbp+18h] BYREF

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || (v3 = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u) )
  {
    v3 = 0;
  }
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    || (v4 = 1, !*((_WORD *)WPP_GLOBAL_Control + 24)) )
  {
    v4 = 0;
  }
  if ( v3 || v4 )
    WPP_RECORDER_AND_TRACE_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v3,
      v4,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      5,
      1,
      12,
      &WPP_79edd0d2b9a03db1d70daf21b10a07c1_Traceguids,
      (char)this);
  LOBYTE(v19) = 0;
  wil::wnf_publish<Microsoft::Bluetooth::Protocols::Avctp::AvctpServiceInitializationState>((__int64)v2, (__int64)&v19);
  v5 = RoInitialize(1);
  v19 = v5;
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3E,
      (unsigned int)"onecore\\drivers\\bluetooth\\profiles\\avrcp\\avctp\\service\\lib\\avctpservicehost.cpp",
      (const char *)(unsigned int)v5,
      v16);
  v8 = Microsoft::Bluetooth::Foundation::ComServiceModule::Unregister(this[22], v6, v7);
  if ( v8 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x40,
      (unsigned int)"onecore\\drivers\\bluetooth\\profiles\\avrcp\\avctp\\service\\lib\\avctpservicehost.cpp",
      (const char *)(unsigned int)v8,
      v16);
  Microsoft::Bluetooth::Foundation::ComServiceModule::DecrementObjectCount(this[22]);
  LOBYTE(v9) = 1;
  LOBYTE(v16) = Microsoft::WRL::Details::TerminateMap(this[22], 0, v9, v10);
  wil::details::in1diag3::Log_HrIfFalseMsg(
    retaddr,
    (void *)0x48,
    (unsigned int)"onecore\\drivers\\bluetooth\\profiles\\avrcp\\avctp\\service\\lib\\avctpservicehost.cpp",
    (const char *)0x8007139FLL,
    v16,
    (bool)"Objects remaining after module termination.",
    v17);
  Microsoft::Bluetooth::Protocols::Avctp::AvctpProfileServiceProvider::Shutdown(this[19]);
  (*(void (__fastcall **)(Microsoft::Bluetooth::Foundation::ComServiceModule *))(*(_QWORD *)this[17] + 24LL))(this[17]);
  (*(void (__fastcall **)(Microsoft::Bluetooth::Foundation::ComServiceModule *))(*(_QWORD *)this[21] + 16LL))(this[21]);
  this[15] = 0;
  v11 = this[16];
  this[16] = 0;
  if ( v11 )
    std::_Ref_count_base::_Decref(v11);
  v12 = (RTL_SRWLOCK *)*((_QWORD *)this[24] + 1);
  AcquireSRWLockExclusive(v12 + 3);
  v20 = v12 + 3;
  std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<unsigned char>,long>>::operator=(
    &v12[4],
    &v12[6]);
  std::_Tree<std::_Tmap_traits<unsigned long,std::shared_ptr<Microsoft::Bluetooth::Profiles::Avrcp::UserMediaController>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::shared_ptr<Microsoft::Bluetooth::Profiles::Avrcp::UserMediaController>>>,0>>::clear(&v12[8]);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v20);
  this[24] = 0;
  v13 = this[25];
  this[25] = 0;
  if ( v13 )
    std::_Ref_count_base::_Decref(v13);
  (*(void (__fastcall **)(Microsoft::Bluetooth::Foundation::ComServiceModule *))(*(_QWORD *)this[23] + 16LL))(this[23]);
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || (v14 = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u) )
  {
    v14 = 0;
  }
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    || (v15 = 1, !*((_WORD *)WPP_GLOBAL_Control + 24)) )
  {
    v15 = 0;
  }
  if ( v14 || v15 )
    WPP_RECORDER_AND_TRACE_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v14,
      v15,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      5,
      1,
      13,
      &WPP_79edd0d2b9a03db1d70daf21b10a07c1_Traceguids,
      (char)this);
  RoUninitialize();
}

```

## disassembly

```asm
0x180027ec0  mov     [rsp+arg_0], rbx
0x180027ec5  mov     [rsp+arg_18], rbp
0x180027eca  push    rsi
0x180027ecb  push    rdi
0x180027ecc  push    r12
0x180027ece  push    r13
0x180027ed0  push    r15
0x180027ed2  sub     rsp, 50h
0x180027ed6  mov     rsi, rcx
0x180027ed9  lea     r12, WPP_GLOBAL_Control
0x180027ee0  xor     ebp, ebp
0x180027ee2  mov     rcx, cs:WPP_GLOBAL_Control
0x180027ee9  cmp     rcx, r12
0x180027eec  jz      short loc_180027EFC
0x180027eee  test    byte ptr [rcx+1Ch], 1
0x180027ef2  jz      short loc_180027EFC
0x180027ef4  cmp     byte ptr [rcx+19h], 5
0x180027ef8  mov     dl, 1
0x180027efa  jnb     short loc_180027EFF
0x180027efc  mov     dl, bpl; int
0x180027eff  lea     r15, WPP_RECORDER_INITIALIZED
0x180027f06  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180027f0d  jz      short loc_180027F18
0x180027f0f  cmp     [rcx+30h], bp
0x180027f13  mov     r8b, 1
0x180027f16  jnz     short loc_180027F1B
0x180027f18  mov     r8b, bpl; int
0x180027f1b  lea     r13, WPP_79edd0d2b9a03db1d70daf21b10a07c1_Traceguids
0x180027f22  test    dl, dl
0x180027f24  jnz     short loc_180027F2B
0x180027f26  test    r8b, r8b
0x180027f29  jz      short loc_180027F56
0x180027f2b  mov     qword ptr [rsp+78h+var_38], rsi; char
0x180027f30  mov     [rsp+78h+MessageGuid], r13; MessageGuid
0x180027f35  mov     word ptr [rsp+78h+var_48], 0Ch; char *
0x180027f3c  mov     dword ptr [rsp+78h+var_50], 1; int
0x180027f44  mov     [rsp+78h+var_58], 5; int
0x180027f49  mov     r9, [rcx+28h]; int
0x180027f4d  mov     rcx, [rcx+10h]; int
0x180027f51  call    WPP_RECORDER_AND_TRACE_SF_q
0x180027f56  mov     byte ptr [rsp+78h+arg_8], bpl
0x180027f5e  lea     rdx, [rsp+78h+arg_8]
0x180027f66  call    ??$wnf_publish@UAvctpServiceInitializationState@Avctp@Protocols@Bluetooth@Microsoft@@@wil@@YAXAEBU_WNF_STATE_NAME@@AEBUAvctpServiceInitializationState@Avctp@Protocols@Bluetooth@Microsoft@@@Z; wil::wnf_publish<Microsoft::Bluetooth::Protocols::Avctp::AvctpServiceInitializationState>(_WNF_STATE_NAME const &,Microsoft::Bluetooth::Protocols::Avctp::AvctpServiceInitializationState const &)
0x180027f6b  mov     ecx, 1
0x180027f70  call    cs:__imp_RoInitialize
0x180027f76  mov     [rsp+78h+arg_8], eax
0x180027f7d  mov     rcx, [rsp+78h]; this
0x180027f82  test    eax, eax
0x180027f84  js      loc_180028145
0x180027f8a  mov     rcx, [rsi+0B0h]; this
0x180027f91  call    ?Unregister@ComServiceModule@Foundation@Bluetooth@Microsoft@@QEAAJPEBG_N@Z; Microsoft::Bluetooth::Foundation::ComServiceModule::Unregister(ushort const *,bool)
0x180027f96  mov     rcx, [rsp+78h]; this
0x180027f9b  test    eax, eax
0x180027f9d  jns     short loc_180027FB3
0x180027f9f  mov     r9d, eax; char *
0x180027fa2  lea     r8, aOnecoreDrivers_34; "onecore\\drivers\\bluetooth\\profiles\\"...
0x180027fa9  mov     edx, 40h ; '@'; void *
0x180027fae  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180027fb3  mov     rcx, [rsi+0B0h]; this
0x180027fba  call    ?DecrementObjectCount@ComServiceModule@Foundation@Bluetooth@Microsoft@@UEAAKXZ; Microsoft::Bluetooth::Foundation::ComServiceModule::DecrementObjectCount(void)
0x180027fbf  mov     r8b, 1; unsigned __int16 *
0x180027fc2  xor     edx, edx; struct Microsoft::WRL::Details::ModuleBase *
0x180027fc4  mov     rcx, [rsi+0B0h]; this
0x180027fcb  call    ?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEBG_N@Z; Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,ushort const *,bool)
0x180027fd0  mov     rcx, [rsp+78h]; this
0x180027fd5  lea     rdx, aObjectsRemaini; "Objects remaining after module terminat"...
0x180027fdc  mov     qword ptr [rsp+78h+var_50], rdx; bool
0x180027fe1  mov     [rsp+78h+var_58], al; int
0x180027fe5  mov     r9d, 8007139Fh; char *
0x180027feb  lea     r8, aOnecoreDrivers_34; "onecore\\drivers\\bluetooth\\profiles\\"...
0x180027ff2  mov     edx, 48h ; 'H'; void *
0x180027ff7  call    ?Log_HrIfFalseMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Log_HrIfFalseMsg(void *,uint,char const *,long,bool,char const *,...)
0x180027ffc  mov     rcx, [rsi+98h]; this
0x180028003  call    ?Shutdown@AvctpProfileServiceProvider@Avctp@Protocols@Bluetooth@Microsoft@@QEAAXXZ; Microsoft::Bluetooth::Protocols::Avctp::AvctpProfileServiceProvider::Shutdown(void)
0x180028008  mov     rcx, [rsi+88h]
0x18002800f  mov     rax, [rcx]
0x180028012  mov     rax, [rax+18h]
0x180028016  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002801b  mov     rcx, [rsi+0A8h]
0x180028022  mov     rax, [rcx]
0x180028025  mov     rax, [rax+10h]
0x180028029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002802e  mov     [rsi+78h], rbp
0x180028032  mov     rcx, [rsi+80h]; this
0x180028039  mov     [rsi+80h], rbp
0x180028040  test    rcx, rcx
0x180028043  jz      short loc_18002804A
0x180028045  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002804a  mov     rax, [rsi+0C0h]
0x180028051  mov     rdi, [rax+8]
0x180028055  lea     rbx, [rdi+18h]
0x180028059  mov     rcx, rbx; SRWLock
0x18002805c  call    cs:__imp_AcquireSRWLockExclusive
0x180028062  mov     [rsp+78h+arg_10], rbx
0x18002806a  lea     rdx, [rdi+30h]
0x18002806e  lea     rcx, [rdi+20h]
0x180028072  call    ??4?$shared_ptr@V?$AsyncRequestWithUniqueResultAutoCancel@V?$vector@EV?$allocator@E@std@@@std@@J@Foundation@Bluetooth@Microsoft@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<uchar>,long>>::operator=(std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<uchar>,long>> const &)
0x180028077  lea     rcx, [rdi+40h]
0x18002807b  call    ?clear@?$_Tree@V?$_Tmap_traits@KV?$shared_ptr@UUserMediaController@Avrcp@Profiles@Bluetooth@Microsoft@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@UUserMediaController@Avrcp@Profiles@Bluetooth@Microsoft@@@std@@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<ulong,std::shared_ptr<Microsoft::Bluetooth::Profiles::Avrcp::UserMediaController>,std::less<ulong>,std::allocator<std::pair<ulong const,std::shared_ptr<Microsoft::Bluetooth::Profiles::Avrcp::UserMediaController>>>,0>>::clear(void)
0x180028080  lea     rcx, [rsp+78h+arg_10]
0x180028088  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002808d  mov     [rsi+0C0h], rbp
0x180028094  mov     rcx, [rsi+0C8h]; this
0x18002809b  mov     [rsi+0C8h], rbp
0x1800280a2  test    rcx, rcx
0x1800280a5  jz      short loc_1800280AC
0x1800280a7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800280ac  mov     rcx, [rsi+0B8h]
0x1800280b3  mov     rax, [rcx]
0x1800280b6  mov     rax, [rax+10h]
0x1800280ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800280bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800280c6  cmp     rcx, r12
0x1800280c9  jz      short loc_1800280D9
0x1800280cb  test    byte ptr [rcx+1Ch], 1
0x1800280cf  jz      short loc_1800280D9
0x1800280d1  cmp     byte ptr [rcx+19h], 5
0x1800280d5  mov     dl, 1
0x1800280d7  jnb     short loc_1800280DC
0x1800280d9  mov     dl, bpl; int
0x1800280dc  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1800280e3  jz      short loc_1800280EE
0x1800280e5  cmp     [rcx+30h], bp
0x1800280e9  mov     r8b, 1
0x1800280ec  jnz     short loc_1800280F1
0x1800280ee  mov     r8b, bpl; int
0x1800280f1  test    dl, dl
0x1800280f3  jnz     short loc_1800280FA
0x1800280f5  test    r8b, r8b
0x1800280f8  jz      short loc_180028126
0x1800280fa  mov     qword ptr [rsp+78h+var_38], rsi; char
0x1800280ff  mov     [rsp+78h+MessageGuid], r13; MessageGuid
0x180028104  mov     word ptr [rsp+78h+var_48], 0Dh; __int16
0x18002810b  mov     dword ptr [rsp+78h+var_50], 1; int
0x180028113  mov     [rsp+78h+var_58], 5; char
0x180028118  mov     r9, [rcx+28h]; int
0x18002811c  mov     rcx, [rcx+10h]; int
0x180028120  call    WPP_RECORDER_AND_TRACE_SF_q
0x180028125  nop
0x180028126  lea     r11, [rsp+78h+var_28]
0x18002812b  mov     rbx, [r11+30h]
0x18002812f  mov     rbp, [r11+48h]
0x180028133  mov     rsp, r11
0x180028136  pop     r15
0x180028138  pop     r13
0x18002813a  pop     r12
0x18002813c  pop     rdi
0x18002813d  pop     rsi
0x18002813e  jmp     cs:__imp_RoUninitialize
0x180028145  mov     r9d, eax; char *
0x180028148  lea     r8, aOnecoreDrivers_34; "onecore\\drivers\\bluetooth\\profiles\\"...
0x18002814f  mov     edx, 3Eh ; '>'; void *
0x180028154  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
