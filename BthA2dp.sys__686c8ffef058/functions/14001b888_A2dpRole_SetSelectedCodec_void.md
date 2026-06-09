# A2dpRole::SetSelectedCodec(void)

- ea: `0x14001b888`
- end: `0x14001bbbe`
- name: `?SetSelectedCodec@A2dpRole@@QEAAEXZ`
- size: `822`
- prototype: `unsigned __int8 __fastcall(A2dpRole *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400070f0`

## callees

- `0x140003530`
- `0x140005030`
- `0x140006410`
- `0x14000f950`
- `0x14001b888`
- `0x14001bbc4`
- `0x14001bc08`
- `0x14001bd20`
- `0x14001c160`
- `0x14002b928`
- `0x14005c870`

## string_xrefs

- `0x14001b9bd`: `AptX Adaptive codec is configured even though it's disabled`
- `0x14001ba53`: `AAC codec is configured even though it's disabled`
- `0x14001baee`: `aptX codec is configured even though it's disabled`

## pseudocode

```c
char __fastcall A2dpRole::SetSelectedCodec(A2dpRole *this)
{
  char v2; // dl
  _QWORD *v3; // rdi
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 ConfiguredCodecWithId; // rax
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rax
  char v14; // bl
  _BYTE v16[4]; // [rsp+50h] [rbp-9h] BYREF
  int v17; // [rsp+54h] [rbp-5h]
  __int16 v18; // [rsp+58h] [rbp-1h]
  __int64 v19; // [rsp+60h] [rbp+7h] BYREF
  utl::_RefCountBase *v20; // [rsp+68h] [rbp+Fh]
  _BYTE v21[8]; // [rsp+70h] [rbp+17h] BYREF
  utl::_RefCountBase *v22; // [rsp+78h] [rbp+1Fh]
  _BYTE v23[48]; // [rsp+80h] [rbp+27h] BYREF

  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
    || (v2 = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
  {
    v2 = 0;
  }
  if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      v2,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      5,
      33,
      (__int64)WPP_7c0da6a8da193713e093ba9e03de3d02_Traceguids,
      (char)this);
  wil::acquire_kspin_lock(v23, (char *)this + 96);
  v3 = (_QWORD *)((char *)this + 112);
  *((_WORD *)this + 52) = -32640;
  utl::shared_ptr<BtaMpmContext>::reset((char *)this + 112);
  v4 = *(_QWORD *)this;
  v16[0] = -1;
  v18 = 173;
  v17 = 215;
  A2dpAudioCodecManager::GetConfiguredCodecWithId(v4, &v19, v16);
  if ( !*((_BYTE *)this + 18) )
    goto LABEL_46;
  if ( !v19 )
    goto LABEL_15;
  if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v19 + 128LL))(v19) )
  {
    utl::shared_ptr<A2dpAudioCodec>::operator=((char *)this + 112, &v19);
    v5 = v19;
    *((_BYTE *)this + 105) = 56;
    *((_BYTE *)this + 104) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 112LL))(v5);
  }
  else
  {
LABEL_46:
    if ( v19 && (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v19 + 128LL))(v19) )
      MicrosoftTelemetryAssertTriggeredMsgKM("AptX Adaptive codec is configured even though it's disabled");
  }
LABEL_15:
  if ( !*v3 )
  {
    v6 = *(_QWORD *)this;
    v16[0] = 2;
    v17 = 0;
    v18 = 0;
    ConfiguredCodecWithId = A2dpAudioCodecManager::GetConfiguredCodecWithId(v6, v21, v16);
    utl::shared_ptr<A2dpAudioCodec>::operator=(&v19, ConfiguredCodecWithId);
    if ( v22 )
      utl::_RefCountBase::_DecStrong(v22);
    if ( *((_BYTE *)this + 17) )
    {
      if ( v19 && (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v19 + 128LL))(v19) )
      {
        utl::shared_ptr<A2dpAudioCodec>::operator=((char *)this + 112, &v19);
        v8 = *v3;
        *((_BYTE *)this + 105) = 55;
        *((_BYTE *)this + 104) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 112LL))(v8);
      }
    }
    else if ( v19 )
    {
      MicrosoftTelemetryAssertTriggeredMsgKM("AAC codec is configured even though it's disabled");
    }
    if ( !*v3 )
    {
      v9 = *(_QWORD *)this;
      v16[0] = -1;
      v17 = 79;
      v18 = 1;
      v10 = A2dpAudioCodecManager::GetConfiguredCodecWithId(v9, v21, v16);
      utl::shared_ptr<A2dpAudioCodec>::operator=(&v19, v10);
      if ( v22 )
        utl::_RefCountBase::_DecStrong(v22);
      if ( *((_BYTE *)this + 16) )
      {
        if ( v19 && (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v19 + 128LL))(v19) )
        {
          utl::shared_ptr<A2dpAudioCodec>::operator=((char *)this + 112, &v19);
          v11 = *v3;
          *((_BYTE *)this + 105) = 54;
          *((_BYTE *)this + 104) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 112LL))(v11);
        }
      }
      else if ( v19 )
      {
        MicrosoftTelemetryAssertTriggeredMsgKM("aptX codec is configured even though it's disabled");
      }
      if ( !*v3 )
      {
        v12 = *(_QWORD *)this;
        v16[0] = 0;
        v17 = 0;
        v18 = 0;
        v13 = A2dpAudioCodecManager::GetConfiguredCodecWithId(v12, v21, v16);
        utl::shared_ptr<A2dpAudioCodec>::operator=(&v19, v13);
        if ( v22 )
          utl::_RefCountBase::_DecStrong(v22);
        if ( v19 && (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v19 + 128LL))(v19) )
        {
          utl::shared_ptr<A2dpAudioCodec>::operator=((char *)this + 112, &v19);
          *((_BYTE *)this + 105) = *((_BYTE *)this + 89) != 0 ? 36 : 52;
          *((_BYTE *)this + 104) = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v3 + 112LL))(*v3);
        }
        if ( !*v3 )
          MicrosoftTelemetryAssertTriggeredMsgKM("No available codec");
      }
    }
  }
  v14 = *((_BYTE *)this + 105);
  if ( v20 )
    utl::_RefCountBase::_DecStrong(v20);
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>(v23);
  return v14;
}

```

## disassembly

```asm
0x14001b888  push    rbp
0x14001b88a  push    rbx
0x14001b88b  push    rsi
0x14001b88c  push    rdi
0x14001b88d  push    r14
0x14001b88f  lea     rbp, [rsp-37h]
0x14001b894  sub     rsp, 90h
0x14001b89b  mov     rbx, rcx
0x14001b89e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b8a5  lea     rax, WPP_GLOBAL_Control
0x14001b8ac  xor     esi, esi
0x14001b8ae  lea     r14d, [rsi+1]
0x14001b8b2  cmp     rcx, rax
0x14001b8b5  jz      short loc_14001B8C7
0x14001b8b7  mov     eax, [rcx+2Ch]
0x14001b8ba  test    al, 10h
0x14001b8bc  jz      short loc_14001B8C7
0x14001b8be  cmp     byte ptr [rcx+29h], 4
0x14001b8c2  mov     dl, r14b
0x14001b8c5  jnb     short loc_14001B8CA
0x14001b8c7  mov     dl, sil
0x14001b8ca  lea     rax, WPP_RECORDER_INITIALIZED
0x14001b8d1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001b8d8  setnz   r8b
0x14001b8dc  test    dl, dl
0x14001b8de  jnz     short loc_14001B8E5
0x14001b8e0  test    r8b, r8b
0x14001b8e3  jz      short loc_14001B917
0x14001b8e5  mov     r9, [rcx+40h]
0x14001b8e9  lea     rax, WPP_7c0da6a8da193713e093ba9e03de3d02_Traceguids
0x14001b8f0  mov     rcx, [rcx+18h]
0x14001b8f4  mov     [rsp+0B0h+var_70], rbx
0x14001b8f9  mov     [rsp+0B0h+var_78], rax
0x14001b8fe  mov     [rsp+0B0h+var_80], 21h ; '!'
0x14001b905  mov     [rsp+0B0h+var_88], 5
0x14001b90d  mov     [rsp+0B0h+var_90], 4
0x14001b912  call    WPP_RECORDER_AND_TRACE_SF_q
0x14001b917  lea     rdx, [rbx+60h]
0x14001b91b  lea     rcx, [rbp+57h+var_30]
0x14001b91f  call    ?acquire_kspin_lock@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUkspin_lock_saved_irql@details@wil@@@Z$1?Release@123@SAX0@ZU?$integral_constant@_K$01@wistd@@U123@PEA_K$0A@$$T@details@wil@@@details@wil@@@1@PEA_K@Z; wil::acquire_kspin_lock(unsigned __int64 *)
0x14001b924  lea     rdi, [rbx+70h]
0x14001b928  mov     word ptr [rbx+68h], 8080h
0x14001b92e  mov     rcx, rdi
0x14001b931  call    ?reset@?$shared_ptr@VBtaMpmContext@@@utl@@QEAAXXZ; utl::shared_ptr<BtaMpmContext>::reset(void)
0x14001b936  mov     rcx, [rbx]
0x14001b939  lea     r8, [rbp+57h+var_60]
0x14001b93d  mov     eax, 0ADh
0x14001b942  mov     [rbp+57h+var_60], 0FFh
0x14001b946  lea     rdx, [rbp+57h+var_50]
0x14001b94a  mov     [rbp+57h+var_58], ax
0x14001b94e  mov     [rbp+57h+var_5C], 0D7h
0x14001b955  call    ?GetConfiguredCodecWithId@A2dpAudioCodecManager@@QEAA?AV?$shared_ptr@VA2dpAudioCodec@@@utl@@AEBVCodecId@@@Z; A2dpAudioCodecManager::GetConfiguredCodecWithId(CodecId const &)
0x14001b95a  cmp     [rbx+12h], sil
0x14001b95e  jz      short loc_14001B9A1
0x14001b960  mov     rcx, [rbp+57h+var_50]
0x14001b964  test    rcx, rcx
0x14001b967  jz      short loc_14001B9C9
0x14001b969  mov     rax, [rcx]
0x14001b96c  mov     rax, [rax+80h]
0x14001b973  call    _guard_dispatch_icall
0x14001b978  test    al, al
0x14001b97a  jz      short loc_14001B9A1
0x14001b97c  lea     rdx, [rbp+57h+var_50]
0x14001b980  mov     rcx, rdi
0x14001b983  call    ??4?$shared_ptr@VA2dpAudioCodec@@@utl@@QEAAAEAV01@AEBV01@@Z; utl::shared_ptr<A2dpAudioCodec>::operator=(utl::shared_ptr<A2dpAudioCodec> const &)
0x14001b988  mov     rcx, [rbp+57h+var_50]
0x14001b98c  mov     byte ptr [rbx+69h], 38h ; '8'
0x14001b990  mov     rax, [rcx]
0x14001b993  mov     rax, [rax+70h]
0x14001b997  call    _guard_dispatch_icall
0x14001b99c  mov     [rbx+68h], al
0x14001b99f  jmp     short loc_14001B9C9
0x14001b9a1  mov     rcx, [rbp+57h+var_50]
0x14001b9a5  test    rcx, rcx
0x14001b9a8  jz      short loc_14001B9C9
0x14001b9aa  mov     rax, [rcx]
0x14001b9ad  mov     rax, [rax+80h]
0x14001b9b4  call    _guard_dispatch_icall
0x14001b9b9  test    al, al
0x14001b9bb  jz      short loc_14001B9C9
0x14001b9bd  lea     rcx, aAptxAdaptiveCo; "AptX Adaptive codec is configured even "...
0x14001b9c4  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14001b9c9  cmp     [rdi], rsi
0x14001b9cc  jnz     loc_14001BB93
0x14001b9d2  mov     rcx, [rbx]
0x14001b9d5  lea     r8, [rbp+57h+var_60]
0x14001b9d9  lea     rdx, [rbp+57h+var_40]
0x14001b9dd  mov     [rbp+57h+var_60], 2
0x14001b9e1  mov     [rbp+57h+var_5C], esi
0x14001b9e4  mov     [rbp+57h+var_58], si
0x14001b9e8  call    ?GetConfiguredCodecWithId@A2dpAudioCodecManager@@QEAA?AV?$shared_ptr@VA2dpAudioCodec@@@utl@@AEBVCodecId@@@Z; A2dpAudioCodecManager::GetConfiguredCodecWithId(CodecId const &)
0x14001b9ed  mov     rdx, rax
0x14001b9f0  lea     rcx, [rbp+57h+var_50]
0x14001b9f4  call    ??4?$shared_ptr@VA2dpAudioCodec@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::shared_ptr<A2dpAudioCodec>::operator=(utl::shared_ptr<A2dpAudioCodec> &&)
0x14001b9f9  mov     rcx, [rbp+57h+var_38]; this
0x14001b9fd  test    rcx, rcx
0x14001ba00  jz      short loc_14001BA07
0x14001ba02  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14001ba07  cmp     [rbx+11h], sil
0x14001ba0b  jz      short loc_14001BA4D
0x14001ba0d  mov     rcx, [rbp+57h+var_50]
0x14001ba11  test    rcx, rcx
0x14001ba14  jz      short loc_14001BA5F
0x14001ba16  mov     rax, [rcx]
0x14001ba19  mov     rax, [rax+80h]
0x14001ba20  call    _guard_dispatch_icall
0x14001ba25  test    al, al
0x14001ba27  jz      short loc_14001BA5F
0x14001ba29  lea     rdx, [rbp+57h+var_50]
0x14001ba2d  mov     rcx, rdi
0x14001ba30  call    ??4?$shared_ptr@VA2dpAudioCodec@@@utl@@QEAAAEAV01@AEBV01@@Z; utl::shared_ptr<A2dpAudioCodec>::operator=(utl::shared_ptr<A2dpAudioCodec> const &)
0x14001ba35  mov     rcx, [rdi]
0x14001ba38  mov     byte ptr [rbx+69h], 37h ; '7'
0x14001ba3c  mov     rax, [rcx]
0x14001ba3f  mov     rax, [rax+70h]
0x14001ba43  call    _guard_dispatch_icall
0x14001ba48  mov     [rbx+68h], al
0x14001ba4b  jmp     short loc_14001BA5F
0x14001ba4d  cmp     [rbp+57h+var_50], rsi
0x14001ba51  jz      short loc_14001BA5F
0x14001ba53  lea     rcx, aAacCodecIsConf; "AAC codec is configured even though it'"...
0x14001ba5a  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14001ba5f  cmp     [rdi], rsi
0x14001ba62  jnz     loc_14001BB93
0x14001ba68  mov     rcx, [rbx]
0x14001ba6b  lea     r8, [rbp+57h+var_60]
0x14001ba6f  lea     rdx, [rbp+57h+var_40]
0x14001ba73  mov     [rbp+57h+var_60], 0FFh
0x14001ba77  mov     [rbp+57h+var_5C], 4Fh ; 'O'
0x14001ba7e  mov     [rbp+57h+var_58], r14w
0x14001ba83  call    ?GetConfiguredCodecWithId@A2dpAudioCodecManager@@QEAA?AV?$shared_ptr@VA2dpAudioCodec@@@utl@@AEBVCodecId@@@Z; A2dpAudioCodecManager::GetConfiguredCodecWithId(CodecId const &)
0x14001ba88  mov     rdx, rax
0x14001ba8b  lea     rcx, [rbp+57h+var_50]
0x14001ba8f  call    ??4?$shared_ptr@VA2dpAudioCodec@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::shared_ptr<A2dpAudioCodec>::operator=(utl::shared_ptr<A2dpAudioCodec> &&)
0x14001ba94  mov     rcx, [rbp+57h+var_38]; this
0x14001ba98  test    rcx, rcx
0x14001ba9b  jz      short loc_14001BAA2
0x14001ba9d  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14001baa2  cmp     [rbx+10h], sil
0x14001baa6  jz      short loc_14001BAE8
0x14001baa8  mov     rcx, [rbp+57h+var_50]
0x14001baac  test    rcx, rcx
0x14001baaf  jz      short loc_14001BAFA
0x14001bab1  mov     rax, [rcx]
0x14001bab4  mov     rax, [rax+80h]
0x14001babb  call    _guard_dispatch_icall
0x14001bac0  test    al, al
0x14001bac2  jz      short loc_14001BAFA
0x14001bac4  lea     rdx, [rbp+57h+var_50]
0x14001bac8  mov     rcx, rdi
0x14001bacb  call    ??4?$shared_ptr@VA2dpAudioCodec@@@utl@@QEAAAEAV01@AEBV01@@Z; utl::shared_ptr<A2dpAudioCodec>::operator=(utl::shared_ptr<A2dpAudioCodec> const &)
0x14001bad0  mov     rcx, [rdi]
0x14001bad3  mov     byte ptr [rbx+69h], 36h ; '6'
0x14001bad7  mov     rax, [rcx]
0x14001bada  mov     rax, [rax+70h]
0x14001bade  call    _guard_dispatch_icall
0x14001bae3  mov     [rbx+68h], al
0x14001bae6  jmp     short loc_14001BAFA
0x14001bae8  cmp     [rbp+57h+var_50], rsi
0x14001baec  jz      short loc_14001BAFA
0x14001baee  lea     rcx, aAptxCodecIsCon; "aptX codec is configured even though it"...
0x14001baf5  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14001bafa  cmp     [rdi], rsi
0x14001bafd  jnz     loc_14001BB93
0x14001bb03  mov     rcx, [rbx]
0x14001bb06  lea     r8, [rbp+57h+var_60]
0x14001bb0a  lea     rdx, [rbp+57h+var_40]
0x14001bb0e  mov     [rbp+57h+var_60], sil
0x14001bb12  mov     [rbp+57h+var_5C], esi
0x14001bb15  mov     [rbp+57h+var_58], si
0x14001bb19  call    ?GetConfiguredCodecWithId@A2dpAudioCodecManager@@QEAA?AV?$shared_ptr@VA2dpAudioCodec@@@utl@@AEBVCodecId@@@Z; A2dpAudioCodecManager::GetConfiguredCodecWithId(CodecId const &)
0x14001bb1e  mov     rdx, rax
0x14001bb21  lea     rcx, [rbp+57h+var_50]
0x14001bb25  call    ??4?$shared_ptr@VA2dpAudioCodec@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::shared_ptr<A2dpAudioCodec>::operator=(utl::shared_ptr<A2dpAudioCodec> &&)
0x14001bb2a  mov     rcx, [rbp+57h+var_38]; this
0x14001bb2e  test    rcx, rcx
0x14001bb31  jz      short loc_14001BB38
0x14001bb33  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14001bb38  mov     rcx, [rbp+57h+var_50]
0x14001bb3c  test    rcx, rcx
0x14001bb3f  jz      short loc_14001BB82
0x14001bb41  mov     rax, [rcx]
0x14001bb44  mov     rax, [rax+80h]
0x14001bb4b  call    _guard_dispatch_icall
0x14001bb50  test    al, al
0x14001bb52  jz      short loc_14001BB82
0x14001bb54  lea     rdx, [rbp+57h+var_50]
0x14001bb58  mov     rcx, rdi
0x14001bb5b  call    ??4?$shared_ptr@VA2dpAudioCodec@@@utl@@QEAAAEAV01@AEBV01@@Z; utl::shared_ptr<A2dpAudioCodec>::operator=(utl::shared_ptr<A2dpAudioCodec> const &)
0x14001bb60  mov     al, [rbx+59h]
0x14001bb63  neg     al
0x14001bb65  sbb     cl, cl
0x14001bb67  and     cl, 0F0h
0x14001bb6a  add     cl, 34h ; '4'
0x14001bb6d  mov     [rbx+69h], cl
0x14001bb70  mov     rcx, [rdi]
0x14001bb73  mov     rax, [rcx]
0x14001bb76  mov     rax, [rax+70h]
0x14001bb7a  call    _guard_dispatch_icall
0x14001bb7f  mov     [rbx+68h], al
0x14001bb82  cmp     [rdi], rsi
0x14001bb85  jnz     short loc_14001BB93
0x14001bb87  lea     rcx, aNoAvailableCod; "No available codec"
0x14001bb8e  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14001bb93  mov     rcx, [rbp+57h+var_48]; this
0x14001bb97  mov     bl, [rbx+69h]
0x14001bb9a  test    rcx, rcx
0x14001bb9d  jz      short loc_14001BBA4
0x14001bb9f  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14001bba4  lea     rcx, [rbp+57h+var_30]
0x14001bba8  call    ??1?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUkspin_lock_saved_irql@details@wil@@@Z$1?Release@123@SAX0@ZU?$integral_constant@_K$01@wistd@@U123@PEA_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>(void)
0x14001bbad  mov     al, bl
0x14001bbaf  add     rsp, 90h
0x14001bbb6  pop     r14
0x14001bbb8  pop     rdi
0x14001bbb9  pop     rsi
0x14001bbba  pop     rbx
0x14001bbbb  pop     rbp
0x14001bbbc  retn
```
