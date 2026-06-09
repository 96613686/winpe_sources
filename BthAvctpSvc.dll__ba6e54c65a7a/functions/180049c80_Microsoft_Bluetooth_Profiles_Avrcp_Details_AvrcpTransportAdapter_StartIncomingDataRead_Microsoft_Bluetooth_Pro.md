# Microsoft::Bluetooth::Profiles::Avrcp::Details::AvrcpTransportAdapter::StartIncomingDataRead(Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransport::ChannelType,unsigned __int64)

- ea: `0x180049c80`
- end: `0x18004a09e`
- name: `?StartIncomingDataRead@AvrcpTransportAdapter@Details@Avrcp@Profiles@Bluetooth@Microsoft@@AEAAXW4ChannelType@AvrcpTransport@3456@_K@Z`
- size: `1054`
- prototype: `void __fastcall(Microsoft::Bluetooth::Profiles::Avrcp::Details::AvrcpTransportAdapter *__hidden this, enum ChannelType, unsigned __int64)`
- caller_count: `2`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18004905c`
- `0x180049258`

## callees

- `0x180001dd0`
- `0x1800039c0`
- `0x180003fbc`
- `0x180004060`
- `0x180009920`
- `0x18000b69c`
- `0x18000de78`
- `0x18000deb0`
- `0x18000e0c0`
- `0x180012168`
- `0x180012554`
- `0x180023374`
- `0x1800334f8`
- `0x1800479d0`
- `0x180047bb4`
- `0x180047d0c`
- `0x180047fec`
- `0x180049c80`
- `0x18004a104`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180049cc2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180049cc2`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Microsoft::Bluetooth::Profiles::Avrcp::Details::AvrcpTransportAdapter::StartIncomingDataRead(
        RTL_SRWLOCK *this,
        unsigned int a2,
        __int64 a3)
{
  RTL_SRWLOCK *v6; // rbx
  __int64 v7; // rdx
  __int64 v8; // r8
  const GUID *v9; // r9
  int v10; // edx
  int v11; // r8d
  RTL_SRWLOCK *v12; // rbx
  __int64 v13; // rax
  char IsEnabled; // al
  std::_Ref_count_base *v15; // rbx
  unsigned int v16; // eax
  __int64 v17; // rax
  __int64 v18; // rdx
  _QWORD *v19; // rax
  _QWORD *v20; // rax
  _QWORD *v21; // r8
  unsigned int v22; // eax
  int v23; // [rsp+20h] [rbp-E0h]
  int v24; // [rsp+50h] [rbp-B0h] BYREF
  RTL_SRWLOCK *v25; // [rsp+58h] [rbp-A8h] BYREF
  std::_Ref_count_base *v26; // [rsp+60h] [rbp-A0h]
  unsigned int v27; // [rsp+68h] [rbp-98h] BYREF
  std::_Ref_count_base *v28[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v29; // [rsp+80h] [rbp-80h] BYREF
  std::_Ref_count_base *v30; // [rsp+88h] [rbp-78h]
  _QWORD v31[4]; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v32; // [rsp+B0h] [rbp-50h]
  char v33[8]; // [rsp+C8h] [rbp-38h] BYREF
  std::_Ref_count_base *v34; // [rsp+D0h] [rbp-30h]
  char v35[8]; // [rsp+D8h] [rbp-28h] BYREF
  char v36[104]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v37; // [rsp+148h] [rbp+48h]
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  v27 = a2;
  *(_OWORD *)v28 = 0;
  v6 = this + 3;
  AcquireSRWLockExclusive(this + 3);
  v25 = v6;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || (LOBYTE(v7) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u) )
  {
    LOBYTE(v7) = 0;
  }
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    || (LOBYTE(v8) = 1, !*((_WORD *)WPP_GLOBAL_Control + 24)) )
  {
    LOBYTE(v8) = 0;
  }
  v9 = &WPP_141f3789e59c364aaec3b9f7a8a4c73b_Traceguids;
  if ( (_BYTE)v7 || (_BYTE)v8 )
    WPP_RECORDER_AND_TRACE_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      v8,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      5,
      1,
      16,
      &WPP_141f3789e59c364aaec3b9f7a8a4c73b_Traceguids,
      (char)this);
  v24 = Microsoft::Bluetooth::Profiles::Avrcp::Details::AvrcpTransportAdapter::ToDriverChannelType(a2, v7, v8, v9);
  if ( a2 )
  {
    if ( a2 != 1 )
    {
      v22 = wil::verify_hresult<long>(2147549183LL);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1F6,
        (unsigned int)"onecore\\drivers\\bluetooth\\legacy\\avrcptransportadapter\\lib\\avrcptransportadapter.cpp",
        (const char *)v22,
        v23);
    }
    v12 = this + 19;
    if ( this[19].Ptr )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || (LOBYTE(v10) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u) )
      {
        LOBYTE(v10) = 0;
      }
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
        || (LOBYTE(v11) = 1, !*((_WORD *)WPP_GLOBAL_Control + 24)) )
      {
        LOBYTE(v11) = 0;
      }
      if ( (_BYTE)v10 || (_BYTE)v11 )
        WPP_RECORDER_AND_TRACE_SF_q(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v10,
          v11,
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          5,
          1,
          18,
          &WPP_141f3789e59c364aaec3b9f7a8a4c73b_Traceguids,
          (char)this);
LABEL_35:
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v25);
      return;
    }
  }
  else
  {
    v12 = this + 17;
    if ( this[17].Ptr )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || (LOBYTE(v10) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u) )
      {
        LOBYTE(v10) = 0;
      }
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
        || (LOBYTE(v11) = 1, !*((_WORD *)WPP_GLOBAL_Control + 24)) )
      {
        LOBYTE(v11) = 0;
      }
      if ( (_BYTE)v10 || (_BYTE)v11 )
        WPP_RECORDER_AND_TRACE_SF_q(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v10,
          v11,
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          5,
          1,
          17,
          &WPP_141f3789e59c364aaec3b9f7a8a4c73b_Traceguids,
          (char)this);
      goto LABEL_35;
    }
  }
  v13 = (*(__int64 (__fastcall **)(PVOID, __int64 *, __int64, int *, __int64, __int64))(*(_QWORD *)this[11].Ptr + 32LL))(
          this[11].Ptr,
          &v29,
          4276240,
          &v24,
          4,
          a3);
  std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncDeviceInterfaceWatcher>::operator=(v12, v13);
  if ( v30 )
    std::_Ref_count_base::_Decref(v30);
  std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<unsigned char>,long>>::operator=(
    v28,
    v12);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v25);
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_59215879>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59215879>::GetImpl'::`2'::impl);
  v15 = v28[0];
  if ( IsEnabled )
  {
    std::weak_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<unsigned char>,long>>::weak_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<unsigned char>,long>>(
      &v25,
      &this[1].Ptr);
    v16 = (unsigned int)std::weak_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<unsigned char>,long>>::weak_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<unsigned char>,long>>(
                          &v29,
                          v28);
    v17 = lambda_5b3d8d177d827835fb4be07c36b035c6_::_lambda_5b3d8d177d827835fb4be07c36b035c6_(
            (unsigned int)v31,
            (unsigned int)&v25,
            v16,
            (unsigned int)&v27,
            (__int64)&this[25]);
    v37 = 0;
    v37 = wistd::__function::__func__lambda_5b3d8d177d827835fb4be07c36b035c6__void___cdecl_void__::__func__lambda_5b3d8d177d827835fb4be07c36b035c6__void___cdecl_void__(
            v36,
            v17);
    lambda_5b3d8d177d827835fb4be07c36b035c6_::__lambda_5b3d8d177d827835fb4be07c36b035c6_(v18);
    (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)v15 + 1) + 24LL))(*((_QWORD *)v15 + 1), v35);
    wistd::function<void (Microsoft::Bluetooth::Foundation::IoTargetIoctlResult<Microsoft::Bluetooth::Foundation::RequestBufferView<KSIDENTIFIER>,std::nullptr_t>)>::~function<void (Microsoft::Bluetooth::Foundation::IoTargetIoctlResult<Microsoft::Bluetooth::Foundation::RequestBufferView<KSIDENTIFIER>,std::nullptr_t>)>((__int64)v35);
    if ( v30 )
      std::_Ref_count_base::_Decwref(v30);
    if ( v26 )
      std::_Ref_count_base::_Decwref(v26);
  }
  else
  {
    v19 = (_QWORD *)std::enable_shared_from_this<Microsoft::Bluetooth::Foundation::Details::AsyncDeviceInterfaceWatcherImpl>::shared_from_this(
                      &this[1],
                      v33);
    std::weak_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<unsigned char>,long>>::weak_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<unsigned char>,long>>(
      &v25,
      v19);
    v20 = std::weak_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<unsigned char>,long>>::weak_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<unsigned char>,long>>(
            &v29,
            v28);
    v31[0] = *v21;
    v31[1] = v21[1];
    *v21 = 0;
    v21[1] = 0;
    v31[2] = *v20;
    v31[3] = v20[1];
    *v20 = 0;
    v20[1] = 0;
    v32 = a2;
    wistd::function_void___cdecl_void__::function_void___cdecl_void____lambda_ec0d9aac2969bba4531ab9c67057e5bf__void_(
      v35,
      v31);
    (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)v15 + 1) + 24LL))(*((_QWORD *)v15 + 1), v35);
    wistd::function<void (Microsoft::Bluetooth::Foundation::IoTargetIoctlResult<Microsoft::Bluetooth::Foundation::RequestBufferView<KSIDENTIFIER>,std::nullptr_t>)>::~function<void (Microsoft::Bluetooth::Foundation::IoTargetIoctlResult<Microsoft::Bluetooth::Foundation::RequestBufferView<KSIDENTIFIER>,std::nullptr_t>)>((__int64)v35);
    if ( v30 )
      std::_Ref_count_base::_Decwref(v30);
    if ( v26 )
      std::_Ref_count_base::_Decwref(v26);
    if ( v34 )
      std::_Ref_count_base::_Decref(v34);
  }
  if ( v28[1] )
    std::_Ref_count_base::_Decref(v28[1]);
}

```

## disassembly

```asm
0x180049c80  mov     [rsp-8+arg_18], rbx
0x180049c85  push    rbp
0x180049c86  push    rsi
0x180049c87  push    rdi
0x180049c88  push    r14
0x180049c8a  push    r15
0x180049c8c  lea     rbp, [rsp-60h]
0x180049c91  sub     rsp, 160h
0x180049c98  mov     rax, cs:__security_cookie
0x180049c9f  xor     rax, rsp
0x180049ca2  mov     [rbp+80h+var_30], rax
0x180049ca6  mov     r14, r8
0x180049ca9  mov     esi, edx
0x180049cab  mov     rdi, rcx
0x180049cae  mov     [rsp+180h+var_118], edx
0x180049cb2  xorps   xmm0, xmm0
0x180049cb5  movdqu  xmmword ptr [rsp+180h+var_110], xmm0
0x180049cbb  lea     rbx, [rcx+18h]
0x180049cbf  mov     rcx, rbx; SRWLock
0x180049cc2  call    cs:__imp_AcquireSRWLockExclusive
0x180049cc8  mov     [rsp+180h+var_128], rbx
0x180049ccd  lea     rax, WPP_GLOBAL_Control
0x180049cd4  xor     r15d, r15d
0x180049cd7  mov     rcx, cs:WPP_GLOBAL_Control
0x180049cde  cmp     rcx, rax
0x180049ce1  jz      short loc_180049CF1
0x180049ce3  test    byte ptr [rcx+1Ch], 1
0x180049ce7  jz      short loc_180049CF1
0x180049ce9  cmp     byte ptr [rcx+19h], 5
0x180049ced  mov     dl, 1
0x180049cef  jnb     short loc_180049CF4
0x180049cf1  mov     dl, r15b; int
0x180049cf4  lea     rax, WPP_RECORDER_INITIALIZED
0x180049cfb  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180049d02  jz      short loc_180049D0E
0x180049d04  cmp     [rcx+30h], r15w
0x180049d09  mov     r8b, 1
0x180049d0c  jnz     short loc_180049D11
0x180049d0e  mov     r8b, r15b; int
0x180049d11  lea     r9, WPP_141f3789e59c364aaec3b9f7a8a4c73b_Traceguids
0x180049d18  test    dl, dl
0x180049d1a  jnz     short loc_180049D21
0x180049d1c  test    r8b, r8b
0x180049d1f  jz      short loc_180049D4C
0x180049d21  mov     qword ptr [rsp+180h+var_140], rdi; char
0x180049d26  mov     [rsp+180h+MessageGuid], r9; MessageGuid
0x180049d2b  mov     [rsp+180h+var_150], 10h; __int16
0x180049d32  mov     [rsp+180h+var_158], 1; int
0x180049d3a  mov     [rsp+180h+var_160], 5; int
0x180049d3f  mov     r9, [rcx+28h]; int
0x180049d43  mov     rcx, [rcx+10h]; int
0x180049d47  call    WPP_RECORDER_AND_TRACE_SF_q
0x180049d4c  mov     ecx, esi
0x180049d4e  call    ?ToDriverChannelType@AvrcpTransportAdapter@Details@Avrcp@Profiles@Bluetooth@Microsoft@@SA?AW4BLUETOOTH_AVRCP_TRANSPORT_CHANNEL_TYPE@@W4ChannelType@AvrcpTransport@3456@@Z; Microsoft::Bluetooth::Profiles::Avrcp::Details::AvrcpTransportAdapter::ToDriverChannelType(Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransport::ChannelType)
0x180049d53  mov     [rsp+180h+var_130], eax
0x180049d57  test    esi, esi
0x180049d59  jz      loc_180049DE1
0x180049d5f  cmp     esi, 1
0x180049d62  jnz     loc_18004A078
0x180049d68  lea     rbx, [rdi+98h]
0x180049d6f  cmp     [rbx], r15
0x180049d72  jz      loc_180049E7E
0x180049d78  mov     rcx, cs:WPP_GLOBAL_Control
0x180049d7f  lea     rax, WPP_GLOBAL_Control
0x180049d86  cmp     rcx, rax
0x180049d89  jz      short loc_180049D9A
0x180049d8b  test    [rcx+1Ch], sil
0x180049d8f  jz      short loc_180049D9A
0x180049d91  cmp     byte ptr [rcx+19h], 5
0x180049d95  mov     dl, sil
0x180049d98  jnb     short loc_180049D9D
0x180049d9a  mov     dl, r15b
0x180049d9d  lea     rax, WPP_RECORDER_INITIALIZED
0x180049da4  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180049dab  jz      short loc_180049DB7
0x180049dad  cmp     [rcx+30h], r15w
0x180049db2  mov     r8b, 1
0x180049db5  jnz     short loc_180049DBA
0x180049db7  mov     r8b, r15b
0x180049dba  test    dl, dl
0x180049dbc  jnz     short loc_180049DC7
0x180049dbe  test    r8b, r8b
0x180049dc1  jz      loc_180049E6E
0x180049dc7  mov     qword ptr [rsp+180h+var_140], rdi
0x180049dcc  lea     r9, WPP_141f3789e59c364aaec3b9f7a8a4c73b_Traceguids
0x180049dd3  mov     [rsp+180h+MessageGuid], r9
0x180049dd8  mov     [rsp+180h+var_150], 12h
0x180049ddf  jmp     short loc_180049E53
0x180049de1  lea     rbx, [rdi+88h]
0x180049de8  cmp     [rbx], r15
0x180049deb  jz      loc_180049E7E
0x180049df1  mov     rcx, cs:WPP_GLOBAL_Control
0x180049df8  lea     rax, WPP_GLOBAL_Control
0x180049dff  cmp     rcx, rax
0x180049e02  jz      short loc_180049E12
0x180049e04  test    byte ptr [rcx+1Ch], 1
0x180049e08  jz      short loc_180049E12
0x180049e0a  cmp     byte ptr [rcx+19h], 5
0x180049e0e  mov     dl, 1
0x180049e10  jnb     short loc_180049E15
0x180049e12  mov     dl, r15b; int
0x180049e15  lea     rax, WPP_RECORDER_INITIALIZED
0x180049e1c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180049e23  jz      short loc_180049E2F
0x180049e25  cmp     [rcx+30h], r15w
0x180049e2a  mov     r8b, 1
0x180049e2d  jnz     short loc_180049E32
0x180049e2f  mov     r8b, r15b; int
0x180049e32  test    dl, dl
0x180049e34  jnz     short loc_180049E3B
0x180049e36  test    r8b, r8b
0x180049e39  jz      short loc_180049E6E
0x180049e3b  mov     qword ptr [rsp+180h+var_140], rdi; char
0x180049e40  lea     r9, WPP_141f3789e59c364aaec3b9f7a8a4c73b_Traceguids
0x180049e47  mov     [rsp+180h+MessageGuid], r9; MessageGuid
0x180049e4c  mov     [rsp+180h+var_150], 11h; __int16
0x180049e53  mov     [rsp+180h+var_158], 1; int
0x180049e5b  mov     r9, [rcx+28h]; int
0x180049e5f  mov     [rsp+180h+var_160], 5; char
0x180049e64  mov     rcx, [rcx+10h]; int
0x180049e68  call    WPP_RECORDER_AND_TRACE_SF_q
0x180049e6d  nop
0x180049e6e  lea     rcx, [rsp+180h+var_128]
0x180049e73  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180049e78  nop
0x180049e79  jmp     loc_18004A055
0x180049e7e  mov     rcx, [rdi+58h]
0x180049e82  mov     qword ptr [rsp+180h+var_158], r14
0x180049e87  mov     rax, [rcx]
0x180049e8a  mov     qword ptr [rsp+180h+var_160], 4
0x180049e93  lea     r9, [rsp+180h+var_130]
0x180049e98  mov     r8d, 414010h
0x180049e9e  lea     rdx, [rbp+80h+var_100]
0x180049ea2  mov     rax, [rax+20h]
0x180049ea6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049eab  mov     rdx, rax
0x180049eae  mov     rcx, rbx
0x180049eb1  call    ??4?$shared_ptr@VAsyncDeviceInterfaceWatcher@Foundation@Bluetooth@Microsoft@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncDeviceInterfaceWatcher>::operator=(std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncDeviceInterfaceWatcher> &&)
0x180049eb6  mov     rcx, [rbp+80h+var_F8]; this
0x180049eba  test    rcx, rcx
0x180049ebd  jz      short loc_180049EC4
0x180049ebf  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180049ec4  mov     rdx, rbx
0x180049ec7  lea     rcx, [rsp+180h+var_110]
0x180049ecc  call    ??4?$shared_ptr@V?$AsyncRequestWithUniqueResultAutoCancel@V?$vector@EV?$allocator@E@std@@@std@@J@Foundation@Bluetooth@Microsoft@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<uchar>,long>>::operator=(std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<uchar>,long>> const &)
0x180049ed1  nop
0x180049ed2  lea     rcx, [rsp+180h+var_128]
0x180049ed7  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180049edc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_59215879@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_59215879@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59215879> `wil::Feature<__WilFeatureTraits_Feature_59215879>::GetImpl(void)'::`2'::impl
0x180049ee3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_59215879@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59215879>::__private_IsEnabled(void)
0x180049ee8  mov     rbx, [rsp+180h+var_110]
0x180049eed  test    al, al
0x180049eef  jz      loc_180049F94
0x180049ef5  lea     rdx, [rdi+8]
0x180049ef9  lea     rcx, [rsp+180h+var_128]
0x180049efe  call    ??$?0V?$AsyncRequestWithUniqueResultAutoCancel@V?$vector@EV?$allocator@E@std@@@std@@J@Foundation@Bluetooth@Microsoft@@$0A@@?$weak_ptr@V?$AsyncRequestWithUniqueResultAutoCancel@V?$vector@EV?$allocator@E@std@@@std@@J@Foundation@Bluetooth@Microsoft@@@std@@QEAA@AEBV?$shared_ptr@V?$AsyncRequestWithUniqueResultAutoCancel@V?$vector@EV?$allocator@E@std@@@std@@J@Foundation@Bluetooth@Microsoft@@@1@@Z; std::weak_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<uchar>,long>>::weak_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<uchar>,long>>(std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<uchar>,long>> const &)
0x180049f03  lea     rdx, [rsp+180h+var_110]
0x180049f08  lea     rcx, [rbp+80h+var_100]
0x180049f0c  call    ??$?0V?$AsyncRequestWithUniqueResultAutoCancel@V?$vector@EV?$allocator@E@std@@@std@@J@Foundation@Bluetooth@Microsoft@@$0A@@?$weak_ptr@V?$AsyncRequestWithUniqueResultAutoCancel@V?$vector@EV?$allocator@E@std@@@std@@J@Foundation@Bluetooth@Microsoft@@@std@@QEAA@AEBV?$shared_ptr@V?$AsyncRequestWithUniqueResultAutoCancel@V?$vector@EV?$allocator@E@std@@@std@@J@Foundation@Bluetooth@Microsoft@@@1@@Z; std::weak_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<uchar>,long>>::weak_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<uchar>,long>>(std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<uchar>,long>> const &)
0x180049f11  lea     rcx, [rdi+0C8h]
0x180049f18  mov     qword ptr [rsp+180h+var_160], rcx
0x180049f1d  lea     r9, [rsp+180h+var_118]
0x180049f22  mov     r8, rax
0x180049f25  lea     rdx, [rsp+180h+var_128]
0x180049f2a  lea     rcx, [rbp+80h+var_F0]
0x180049f2e  call    _lambda_5b3d8d177d827835fb4be07c36b035c6____lambda_5b3d8d177d827835fb4be07c36b035c6_
0x180049f33  mov     rdx, rax
0x180049f36  mov     [rbp+80h+var_38], r15
0x180049f3a  lea     rcx, [rbp+80h+var_A0]
0x180049f3e  call    wistd____function____func__lambda_5b3d8d177d827835fb4be07c36b035c6__void___cdecl_void______func__lambda_5b3d8d177d827835fb4be07c36b035c6__void___cdecl_void__
0x180049f43  mov     [rbp+80h+var_38], rax
0x180049f47  mov     rcx, rdx
0x180049f4a  call    _lambda_5b3d8d177d827835fb4be07c36b035c6_____lambda_5b3d8d177d827835fb4be07c36b035c6_
0x180049f4f  nop
0x180049f50  mov     rcx, [rbx+8]
0x180049f54  mov     rax, [rcx]
0x180049f57  lea     rdx, [rbp+80h+var_A8]
0x180049f5b  mov     rax, [rax+18h]
0x180049f5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049f64  nop
0x180049f65  lea     rcx, [rbp+80h+var_A8]
0x180049f69  call    ??1?$function@$$A6AXU?$IoTargetIoctlResult@V?$RequestBufferView@UKSIDENTIFIER@@@Foundation@Bluetooth@Microsoft@@$$T@Foundation@Bluetooth@Microsoft@@@Z@wistd@@QEAA@XZ; wistd::function<void (Microsoft::Bluetooth::Foundation::IoTargetIoctlResult<Microsoft::Bluetooth::Foundation::RequestBufferView<KSIDENTIFIER>,std::nullptr_t>)>::~function<void (Microsoft::Bluetooth::Foundation::IoTargetIoctlResult<Microsoft::Bluetooth::Foundation::RequestBufferView<KSIDENTIFIER>,std::nullptr_t>)>(void)
0x180049f6e  mov     rcx, [rbp+80h+var_F8]; this
0x180049f72  test    rcx, rcx
0x180049f75  jz      short loc_180049F7C
0x180049f77  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180049f7c  mov     rcx, [rsp+180h+var_120]; this
0x180049f81  test    rcx, rcx
0x180049f84  jz      loc_18004A046
0x180049f8a  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180049f8f  jmp     loc_18004A046
0x180049f94  lea     rdx, [rbp+80h+var_B8]
0x180049f98  lea     rcx, [rdi+8]
0x180049f9c  call    ?shared_from_this@?$enable_shared_from_this@VAsyncDeviceInterfaceWatcherImpl@Details@Foundation@Bluetooth@Microsoft@@@std@@QEAA?AV?$shared_ptr@VAsyncDeviceInterfaceWatcherImpl@Details@Foundation@Bluetooth@Microsoft@@@2@XZ; std::enable_shared_from_this<Microsoft::Bluetooth::Foundation::Details::AsyncDeviceInterfaceWatcherImpl>::shared_from_this(void)
0x180049fa1  mov     rdx, rax
0x180049fa4  lea     rcx, [rsp+180h+var_128]
0x180049fa9  call    ??$?0V?$AsyncRequestWithUniqueResultAutoCancel@V?$vector@EV?$allocator@E@std@@@std@@J@Foundation@Bluetooth@Microsoft@@$0A@@?$weak_ptr@V?$AsyncRequestWithUniqueResultAutoCancel@V?$vector@EV?$allocator@E@std@@@std@@J@Foundation@Bluetooth@Microsoft@@@std@@QEAA@AEBV?$shared_ptr@V?$AsyncRequestWithUniqueResultAutoCancel@V?$vector@EV?$allocator@E@std@@@std@@J@Foundation@Bluetooth@Microsoft@@@1@@Z; std::weak_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<uchar>,long>>::weak_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<uchar>,long>>(std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<uchar>,long>> const &)
0x180049fae  mov     r8, rax
0x180049fb1  lea     rdx, [rsp+180h+var_110]
0x180049fb6  lea     rcx, [rbp+80h+var_100]
0x180049fba  call    ??$?0V?$AsyncRequestWithUniqueResultAutoCancel@V?$vector@EV?$allocator@E@std@@@std@@J@Foundation@Bluetooth@Microsoft@@$0A@@?$weak_ptr@V?$AsyncRequestWithUniqueResultAutoCancel@V?$vector@EV?$allocator@E@std@@@std@@J@Foundation@Bluetooth@Microsoft@@@std@@QEAA@AEBV?$shared_ptr@V?$AsyncRequestWithUniqueResultAutoCancel@V?$vector@EV?$allocator@E@std@@@std@@J@Foundation@Bluetooth@Microsoft@@@1@@Z; std::weak_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<uchar>,long>>::weak_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<uchar>,long>>(std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<uchar>,long>> const &)
0x180049fbf  mov     rcx, [r8]
0x180049fc2  mov     [rbp+80h+var_F0], rcx
0x180049fc6  mov     rcx, [r8+8]
0x180049fca  mov     [rbp+80h+var_E8], rcx
0x180049fce  mov     [r8], r15
0x180049fd1  mov     [r8+8], r15
0x180049fd5  mov     rcx, [rax]
0x180049fd8  mov     [rbp+80h+var_E0], rcx
0x180049fdc  mov     rcx, [rax+8]
0x180049fe0  mov     [rbp+80h+var_D8], rcx
0x180049fe4  mov     [rax], r15
0x180049fe7  mov     [rax+8], r15
0x180049feb  mov     [rbp+80h+var_D0], esi
0x180049fee  lea     rdx, [rbp+80h+var_F0]
0x180049ff2  lea     rcx, [rbp+80h+var_A8]
0x180049ff6  call    wistd__function_void___cdecl_void____function_void___cdecl_void____lambda_ec0d9aac2969bba4531ab9c67057e5bf__void_
0x180049ffb  nop
0x180049ffc  mov     rcx, [rbx+8]
0x18004a000  mov     rax, [rcx]
0x18004a003  lea     rdx, [rbp+80h+var_A8]
0x18004a007  mov     rax, [rax+18h]
0x18004a00b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a010  nop
0x18004a011  lea     rcx, [rbp+80h+var_A8]
0x18004a015  call    ??1?$function@$$A6AXU?$IoTargetIoctlResult@V?$RequestBufferView@UKSIDENTIFIER@@@Foundation@Bluetooth@Microsoft@@$$T@Foundation@Bluetooth@Microsoft@@@Z@wistd@@QEAA@XZ; wistd::function<void (Microsoft::Bluetooth::Foundation::IoTargetIoctlResult<Microsoft::Bluetooth::Foundation::RequestBufferView<KSIDENTIFIER>,std::nullptr_t>)>::~function<void (Microsoft::Bluetooth::Foundation::IoTargetIoctlResult<Microsoft::Bluetooth::Foundation::RequestBufferView<KSIDENTIFIER>,std::nullptr_t>)>(void)
0x18004a01a  mov     rcx, [rbp+80h+var_F8]; this
0x18004a01e  test    rcx, rcx
0x18004a021  jz      short loc_18004A028
0x18004a023  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18004a028  mov     rcx, [rsp+180h+var_120]; this
0x18004a02d  test    rcx, rcx
0x18004a030  jz      short loc_18004A037
0x18004a032  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18004a037  mov     rcx, [rbp+80h+var_B0]; this
0x18004a03b  test    rcx, rcx
0x18004a03e  jz      short loc_18004A046
0x18004a040  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004a045  nop
0x18004a046  mov     rcx, [rsp+180h+var_110+8]; this
0x18004a04b  test    rcx, rcx
0x18004a04e  jz      short loc_18004A055
0x18004a050  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004a055  mov     rcx, [rbp+80h+var_30]
0x18004a059  xor     rcx, rsp; StackCookie
0x18004a05c  call    __security_check_cookie
0x18004a061  mov     rbx, [rsp+180h+arg_18]
0x18004a069  add     rsp, 160h
0x18004a070  pop     r15
0x18004a072  pop     r14
0x18004a074  pop     rdi
0x18004a075  pop     rsi
0x18004a076  pop     rbp
0x18004a077  retn
0x18004a078  mov     ecx, 8000FFFFh
0x18004a07d  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18004a082  mov     r9d, eax; char *
0x18004a085  mov     rcx, [rbp+88h]; this
0x18004a08c  lea     r8, aOnecoreDrivers_22; "onecore\\drivers\\bluetooth\\legacy\\av"...
0x18004a093  mov     edx, 1F6h; void *
0x18004a098  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
