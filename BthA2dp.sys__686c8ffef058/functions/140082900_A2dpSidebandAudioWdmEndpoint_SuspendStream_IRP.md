# A2dpSidebandAudioWdmEndpoint::SuspendStream(_IRP *)

- ea: `0x140082900`
- end: `0x140082dfe`
- name: `?SuspendStream@A2dpSidebandAudioWdmEndpoint@@AEAAJPEAU_IRP@@@Z`
- size: `1278`
- prototype: `__int64 __fastcall(A2dpSidebandAudioWdmEndpoint *__hidden this, struct _IRP *)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x140080730`

## callees

- `0x140001708`
- `0x140003530`
- `0x140006410`
- `0x140006a88`
- `0x14000e690`
- `0x14000f6e4`
- `0x140010628`
- `0x140014d0c`
- `0x14001f93c`
- `0x1400202e8`
- `0x14002d8e8`
- `0x14002e8c8`
- `0x140033440`
- `0x1400370ac`
- `0x140037454`
- `0x140037dc0`
- `0x140082900`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1400829a0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400829a0`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400829af`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400829af`

## pseudocode

```c
__int64 __fastcall A2dpSidebandAudioWdmEndpoint::SuspendStream(A2dpSidebandAudioWdmEndpoint *this, struct _IRP *a2)
{
  char v3; // di
  _DWORD *v4; // r14
  __int64 v5; // rcx
  int v6; // r8d
  __int64 *v7; // rdx
  unsigned int v8; // ebx
  __int64 *v9; // rdx
  int v10; // eax
  int v11; // edx
  __int64 v12; // r8
  int v13; // r8d
  __int64 *v14; // rdx
  A2DP_Device *v15; // r15
  __int64 *v16; // rdx
  __int64 v17; // rbx
  char v18; // al
  __int64 v19; // r8
  __int64 v20; // rdx
  unsigned __int8 v21; // r15
  __int64 v22; // rbx
  int v23; // ecx
  int v24; // r9d
  utl::_RefCountBase *v25; // rcx
  __int64 v27; // [rsp+60h] [rbp-9h] BYREF
  utl::_RefCountBase *v28; // [rsp+68h] [rbp-1h]
  __int64 v29; // [rsp+70h] [rbp+7h] BYREF
  utl::_RefCountBase *v30; // [rsp+78h] [rbp+Fh]
  int v31; // [rsp+D0h] [rbp+67h] BYREF
  struct _IRP *v32; // [rsp+D8h] [rbp+6Fh] BYREF
  __int64 v33; // [rsp+E0h] [rbp+77h] BYREF
  char *v34; // [rsp+E8h] [rbp+7Fh] BYREF

  v32 = a2;
  v3 = 1;
  LOBYTE(a2) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x12u)
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)a2,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      19,
      90,
      (__int64)WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids,
      (char)this);
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)((char *)this + 744));
  v34 = (char *)this + 744;
  v4 = (_DWORD *)((char *)this + 800);
  if ( (unsigned int)Feature_60759990__private_IsEnabledDeviceUsageNoInline(v5) && *v4 == 3 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x12u)
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      v3 = 0;
    }
    if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v7 = WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids;
      LOBYTE(v7) = v3;
      WPP_RECORDER_AND_TRACE_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        (_DWORD)v7,
        WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
        WPP_GLOBAL_Control->DeviceExtension,
        4,
        19,
        91,
        (__int64)WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids,
        (char)this);
    }
LABEL_73:
    v8 = 0;
    goto LABEL_74;
  }
  v8 = -1073741436;
  if ( *v4 == 2 )
  {
    v10 = A2dpSidebandAudioWdmEndpoint::SendAvdtpBrb<_BRB_HCI_VS_MSFT_AVDTP_SUSPEND>(this);
    if ( v10 < 0 )
    {
      LOBYTE(v11) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                 && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x12u)
                 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
      LOBYTE(v12) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( (_BYTE)v11 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_AND_TRACE_SF_dq(
          WPP_GLOBAL_Control->AttachedDevice,
          v11,
          v12,
          WPP_GLOBAL_Control->DeviceExtension,
          3,
          19,
          93,
          (__int64)WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids,
          v10,
          (char)this);
    }
    utl::weak_ptr<BtaMpmContext>::lock((char *)this + 616, &v29, v12);
    if ( (unsigned __int8)utl::operator==<A2dpSidebandAudioWdmDevice>(&v29) )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        v3 = 0;
      }
      if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v14 = WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids;
        LOBYTE(v14) = v3;
        LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          (_DWORD)v14,
          v13,
          WPP_GLOBAL_Control->DeviceExtension,
          2,
          18,
          94,
          (__int64)WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids,
          132);
      }
      if ( v30 )
        utl::_RefCountBase::_DecStrong(v30);
    }
    else
    {
      v15 = *(A2DP_Device **)(v29 + 488);
      utl::make_shared<wil::details::kernel_event_t<1>,>(&v27);
      if ( v27 )
      {
        v17 = MEMORY[0xFFFFF78000000014];
        A2DP_Device::SetPinStateNotRunning(v15);
        v18 = wil::details::kernel_event_t<1>::wait(v27, *((int *)this + 152));
        v20 = (unsigned __int128)((MEMORY[0xFFFFF78000000014] - v17) * (__int128)0x346DC5D63886594BLL) >> 64;
        v21 = v18 ^ 1;
        v22 = (MEMORY[0xFFFFF78000000014] - v17) / 10000;
        if ( (unsigned int)dword_14006F0F8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_14006F0F8, 0x400000000000LL, v19) )
        {
          v31 = v21;
          LOWORD(v32) = v22;
          v33 = 50333696;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
            v23,
            (unsigned int)byte_140069BEB,
            v19,
            v24,
            (__int64)&v33,
            (__int64)&v32,
            (__int64)&v31);
        }
        LOBYTE(v20) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                   && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0
                   && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
        if ( (_BYTE)v20 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v19) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_llq(
            WPP_GLOBAL_Control->AttachedDevice,
            v20,
            v19,
            WPP_GLOBAL_Control->DeviceExtension,
            3,
            19,
            96,
            (__int64)WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids,
            v22,
            v21,
            (char)this);
        }
        v25 = v28;
        *v4 = 1;
        if ( v25 )
          utl::_RefCountBase::_DecStrong(v25);
        if ( v30 )
          utl::_RefCountBase::_DecStrong(v30);
        goto LABEL_73;
      }
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x12u)
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        v3 = 0;
      }
      if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v16 = WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids;
        LOBYTE(v16) = v3;
        WPP_RECORDER_AND_TRACE_SF_q(
          WPP_GLOBAL_Control->AttachedDevice,
          (_DWORD)v16,
          WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
          WPP_GLOBAL_Control->DeviceExtension,
          2,
          19,
          95,
          (__int64)WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids,
          (char)this);
      }
      if ( v28 )
        utl::_RefCountBase::_DecStrong(v28);
      if ( v30 )
        utl::_RefCountBase::_DecStrong(v30);
      v8 = -1073741670;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x12u)
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      v3 = 0;
    }
    if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v9 = WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids;
      LOBYTE(v9) = v3;
      LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_Dq(
        WPP_GLOBAL_Control->AttachedDevice,
        (_DWORD)v9,
        v6,
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        19,
        92,
        (__int64)WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids,
        *v4,
        this);
    }
  }
LABEL_74:
  __1__unique_storage_U__resource_policy_PEAU_FAST_MUTEX____A6AXPEAU1___E_1_release_fast_mutex_with_critical_region_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAA_XZ(&v34);
  return v8;
}

```

## disassembly

```asm
0x140082900  mov     [rsp-8+arg_8], rdx
0x140082905  push    rbp
0x140082906  push    rbx
0x140082907  push    rsi
0x140082908  push    rdi
0x140082909  push    r12
0x14008290b  push    r13
0x14008290d  push    r14
0x14008290f  push    r15
0x140082911  lea     rbp, [rsp-1Fh]
0x140082916  sub     rsp, 88h
0x14008291d  mov     rsi, rcx
0x140082920  mov     rcx, cs:WPP_GLOBAL_Control
0x140082927  lea     r13, WPP_GLOBAL_Control
0x14008292e  mov     edi, 1
0x140082933  cmp     rcx, r13
0x140082936  jz      short loc_14008294A
0x140082938  bt      dword ptr [rcx+2Ch], 12h
0x14008293d  jnb     short loc_14008294A
0x14008293f  cmp     byte ptr [rcx+29h], 4
0x140082943  jb      short loc_14008294A
0x140082945  mov     dl, dil
0x140082948  jmp     short loc_14008294C
0x14008294a  xor     dl, dl
0x14008294c  lea     r15, WPP_RECORDER_INITIALIZED
0x140082953  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14008295a  lea     r9, WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids
0x140082961  setnz   r8b
0x140082965  test    dl, dl
0x140082967  jnz     short loc_14008296E
0x140082969  test    r8b, r8b
0x14008296c  jz      short loc_140082999
0x14008296e  mov     [rsp+0C0h+var_80], rsi
0x140082973  mov     [rsp+0C0h+var_88], r9
0x140082978  mov     r9, [rcx+40h]
0x14008297c  mov     rcx, [rcx+18h]
0x140082980  mov     word ptr [rsp+0C0h+var_90], 5Ah ; 'Z'
0x140082987  mov     dword ptr [rsp+0C0h+var_98], 13h
0x14008298f  mov     byte ptr [rsp+0C0h+var_A0], 4
0x140082994  call    WPP_RECORDER_AND_TRACE_SF_q
0x140082999  lea     rbx, [rsi+2E8h]
0x1400829a0  call    cs:__imp_KeEnterCriticalRegion
0x1400829a7  nop     dword ptr [rax+rax+00h]
0x1400829ac  mov     rcx, rbx; FastMutex
0x1400829af  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1400829b6  nop     dword ptr [rax+rax+00h]
0x1400829bb  mov     [rbp+57h+arg_18], rbx
0x1400829bf  lea     r14, [rsi+320h]
0x1400829c6  call    Feature_60759990__private_IsEnabledDeviceUsageNoInline
0x1400829cb  test    eax, eax
0x1400829cd  jz      short loc_140082A44
0x1400829cf  cmp     dword ptr [r14], 3
0x1400829d3  jnz     short loc_140082A44
0x1400829d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400829dc  cmp     rcx, r13
0x1400829df  jz      short loc_1400829EE
0x1400829e1  bt      dword ptr [rcx+2Ch], 12h
0x1400829e6  jnb     short loc_1400829EE
0x1400829e8  cmp     byte ptr [rcx+29h], 4
0x1400829ec  jnb     short loc_1400829F1
0x1400829ee  xor     dil, dil
0x1400829f1  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400829f8  setnz   r8b
0x1400829fc  test    dil, dil
0x1400829ff  jnz     short loc_140082A0A
0x140082a01  test    r8b, r8b
0x140082a04  jz      loc_140082DDC
0x140082a0a  mov     r9, [rcx+40h]
0x140082a0e  lea     rdx, WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids
0x140082a15  mov     rcx, [rcx+18h]
0x140082a19  mov     [rsp+0C0h+var_80], rsi
0x140082a1e  mov     [rsp+0C0h+var_88], rdx
0x140082a23  mov     dl, dil
0x140082a26  mov     word ptr [rsp+0C0h+var_90], 5Bh ; '['
0x140082a2d  mov     dword ptr [rsp+0C0h+var_98], 13h
0x140082a35  mov     byte ptr [rsp+0C0h+var_A0], 4
0x140082a3a  call    WPP_RECORDER_AND_TRACE_SF_q
0x140082a3f  jmp     loc_140082DDC
0x140082a44  mov     edx, [r14]
0x140082a47  mov     ebx, 0C0000184h
0x140082a4c  cmp     edx, 2
0x140082a4f  jz      short loc_140082AC4
0x140082a51  mov     rcx, cs:WPP_GLOBAL_Control
0x140082a58  cmp     rcx, r13
0x140082a5b  jz      short loc_140082A6A
0x140082a5d  bt      dword ptr [rcx+2Ch], 12h
0x140082a62  jnb     short loc_140082A6A
0x140082a64  cmp     byte ptr [rcx+29h], 2
0x140082a68  jnb     short loc_140082A6D
0x140082a6a  xor     dil, dil
0x140082a6d  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140082a74  setnz   r8b
0x140082a78  test    dil, dil
0x140082a7b  jnz     short loc_140082A86
0x140082a7d  test    r8b, r8b
0x140082a80  jz      loc_140082DDE
0x140082a86  mov     r9, [rcx+40h]
0x140082a8a  mov     rcx, [rcx+18h]
0x140082a8e  mov     [rsp+0C0h+var_78], rsi
0x140082a93  mov     dword ptr [rsp+0C0h+var_80], edx
0x140082a97  lea     rdx, WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids
0x140082a9e  mov     [rsp+0C0h+var_88], rdx
0x140082aa3  mov     dl, dil
0x140082aa6  mov     word ptr [rsp+0C0h+var_90], 5Ch ; '\'
0x140082aad  mov     dword ptr [rsp+0C0h+var_98], 13h
0x140082ab5  mov     byte ptr [rsp+0C0h+var_A0], 2
0x140082aba  call    WPP_RECORDER_AND_TRACE_SF_Dq
0x140082abf  jmp     loc_140082DDE
0x140082ac4  mov     rcx, rsi; this
0x140082ac7  call    ??$SendAvdtpBrb@U_BRB_HCI_VS_MSFT_AVDTP_SUSPEND@@@A2dpSidebandAudioWdmEndpoint@@AEAAJW4_BRB_TYPE@@@Z; A2dpSidebandAudioWdmEndpoint::SendAvdtpBrb<_BRB_HCI_VS_MSFT_AVDTP_SUSPEND>(_BRB_TYPE)
0x140082acc  test    eax, eax
0x140082ace  jns     short loc_140082B3C
0x140082ad0  mov     r10, cs:WPP_GLOBAL_Control
0x140082ad7  cmp     r10, r13
0x140082ada  jz      short loc_140082AF0
0x140082adc  bt      dword ptr [r10+2Ch], 12h
0x140082ae2  jnb     short loc_140082AF0
0x140082ae4  cmp     byte ptr [r10+29h], 3
0x140082ae9  jb      short loc_140082AF0
0x140082aeb  mov     dl, dil
0x140082aee  jmp     short loc_140082AF2
0x140082af0  xor     dl, dl
0x140082af2  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140082af9  setnz   r8b
0x140082afd  test    dl, dl
0x140082aff  jnz     short loc_140082B06
0x140082b01  test    r8b, r8b
0x140082b04  jz      short loc_140082B3C
0x140082b06  mov     r9, [r10+40h]
0x140082b0a  mov     rcx, [r10+18h]
0x140082b0e  mov     [rsp+0C0h+var_78], rsi
0x140082b13  mov     dword ptr [rsp+0C0h+var_80], eax
0x140082b17  lea     rax, WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids
0x140082b1e  mov     [rsp+0C0h+var_88], rax
0x140082b23  mov     word ptr [rsp+0C0h+var_90], 5Dh ; ']'
0x140082b2a  mov     dword ptr [rsp+0C0h+var_98], 13h
0x140082b32  mov     byte ptr [rsp+0C0h+var_A0], 3
0x140082b37  call    WPP_RECORDER_AND_TRACE_SF_dq
0x140082b3c  lea     rcx, [rsi+268h]
0x140082b43  lea     rdx, [rbp+57h+var_50]
0x140082b47  call    ?lock@?$weak_ptr@VBtaMpmContext@@@utl@@QEBA?AV?$shared_ptr@VBtaMpmContext@@@2@XZ; utl::weak_ptr<BtaMpmContext>::lock(void)
0x140082b4c  lea     rcx, [rbp+57h+var_50]
0x140082b50  call    ??$?8VA2dpSidebandAudioWdmDevice@@@utl@@YA_NAEBV?$shared_ptr@VA2dpSidebandAudioWdmDevice@@@0@$$T@Z; utl::operator==<A2dpSidebandAudioWdmDevice>(utl::shared_ptr<A2dpSidebandAudioWdmDevice> const &,std::nullptr_t)
0x140082b55  test    al, al
0x140082b57  jz      short loc_140082BD7
0x140082b59  mov     rcx, cs:WPP_GLOBAL_Control
0x140082b60  cmp     rcx, r13
0x140082b63  jz      short loc_140082B74
0x140082b65  test    dword ptr [rcx+2Ch], 20000h
0x140082b6c  jz      short loc_140082B74
0x140082b6e  cmp     byte ptr [rcx+29h], 2
0x140082b72  jnb     short loc_140082B77
0x140082b74  xor     dil, dil
0x140082b77  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140082b7e  setnz   r8b
0x140082b82  test    dil, dil
0x140082b85  jnz     short loc_140082B8C
0x140082b87  test    r8b, r8b
0x140082b8a  jz      short loc_140082BC0
0x140082b8c  mov     r9, [rcx+40h]
0x140082b90  lea     rdx, WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids
0x140082b97  mov     rcx, [rcx+18h]
0x140082b9b  mov     dword ptr [rsp+0C0h+var_80], ebx
0x140082b9f  mov     [rsp+0C0h+var_88], rdx
0x140082ba4  mov     dl, dil
0x140082ba7  mov     word ptr [rsp+0C0h+var_90], 5Eh ; '^'
0x140082bae  mov     dword ptr [rsp+0C0h+var_98], 12h
0x140082bb6  mov     byte ptr [rsp+0C0h+var_A0], 2
0x140082bbb  call    WPP_RECORDER_AND_TRACE_SF_d
0x140082bc0  mov     rcx, [rbp+57h+var_48]; this
0x140082bc4  test    rcx, rcx
0x140082bc7  jz      loc_140082DDE
0x140082bcd  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140082bd2  jmp     loc_140082DDE
0x140082bd7  mov     rax, [rbp+57h+var_50]
0x140082bdb  lea     rcx, [rbp+57h+var_60]
0x140082bdf  mov     r15, [rax+1E8h]
0x140082be6  call    ??$make_shared@V?$kernel_event_t@$00@details@wil@@$$V@utl@@YA?AV?$shared_ptr@V?$kernel_event_t@$00@details@wil@@@0@XZ; utl::make_shared<wil::details::kernel_event_t<1>,>(void)
0x140082beb  cmp     [rbp+57h+var_60], 0
0x140082bf0  jnz     loc_140082C89
0x140082bf6  mov     rcx, cs:WPP_GLOBAL_Control
0x140082bfd  cmp     rcx, r13
0x140082c00  jz      short loc_140082C0F
0x140082c02  bt      dword ptr [rcx+2Ch], 12h
0x140082c07  jnb     short loc_140082C0F
0x140082c09  cmp     byte ptr [rcx+29h], 2
0x140082c0d  jnb     short loc_140082C12
0x140082c0f  xor     dil, dil
0x140082c12  lea     rax, WPP_RECORDER_INITIALIZED
0x140082c19  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140082c20  setnz   r8b
0x140082c24  test    dil, dil
0x140082c27  jnz     short loc_140082C2E
0x140082c29  test    r8b, r8b
0x140082c2c  jz      short loc_140082C63
0x140082c2e  mov     r9, [rcx+40h]
0x140082c32  lea     rdx, WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids
0x140082c39  mov     rcx, [rcx+18h]
0x140082c3d  mov     [rsp+0C0h+var_80], rsi
0x140082c42  mov     [rsp+0C0h+var_88], rdx
0x140082c47  mov     dl, dil
0x140082c4a  mov     word ptr [rsp+0C0h+var_90], 5Fh ; '_'
0x140082c51  mov     dword ptr [rsp+0C0h+var_98], 13h
0x140082c59  mov     byte ptr [rsp+0C0h+var_A0], 2
0x140082c5e  call    WPP_RECORDER_AND_TRACE_SF_q
0x140082c63  mov     rcx, [rbp+57h+var_58]; this
0x140082c67  test    rcx, rcx
0x140082c6a  jz      short loc_140082C71
0x140082c6c  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140082c71  mov     rcx, [rbp+57h+var_48]; this
0x140082c75  test    rcx, rcx
0x140082c78  jz      short loc_140082C7F
0x140082c7a  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140082c7f  mov     ebx, 0C000009Ah
0x140082c84  jmp     loc_140082DDE
0x140082c89  mov     r12, 0FFFFF78000000014h
0x140082c93  lea     rdx, [rbp+57h+var_60]
0x140082c97  mov     rcx, r15; this
0x140082c9a  mov     rbx, [r12]
0x140082c9e  call    ?SetPinStateNotRunning@A2DP_Device@@QEAAXAEBV?$shared_ptr@V?$kernel_event_t@$00@details@wil@@@utl@@@Z; A2DP_Device::SetPinStateNotRunning(utl::shared_ptr<wil::details::kernel_event_t<1>> const &)
0x140082ca3  movsxd  rdx, dword ptr [rsi+260h]
0x140082caa  mov     rcx, [rbp+57h+var_60]
0x140082cae  call    ?wait@?$kernel_event_t@$00@details@wil@@QEAA_N_J@Z; wil::details::kernel_event_t<1>::wait(__int64)
0x140082cb3  mov     rcx, [r12]
0x140082cb7  mov     r15b, al
0x140082cba  sub     rcx, rbx
0x140082cbd  mov     rax, 346DC5D63886594Bh
0x140082cc7  imul    rcx
0x140082cca  mov     eax, cs:dword_14006F0F8
0x140082cd0  xor     r15b, dil
0x140082cd3  mov     rbx, rdx
0x140082cd6  sar     rbx, 0Bh
0x140082cda  mov     rcx, rbx
0x140082cdd  shr     rcx, 3Fh
0x140082ce1  add     rbx, rcx
0x140082ce4  cmp     eax, 5
0x140082ce7  jbe     short loc_140082D3D
0x140082ce9  mov     rdx, 400000000000h
0x140082cf3  lea     rcx, dword_14006F0F8
0x140082cfa  call    _tlgKeywordOn
0x140082cff  test    al, al
0x140082d01  jz      short loc_140082D3D
0x140082d03  movzx   eax, r15b
0x140082d07  lea     rdx, byte_140069BEB
0x140082d0e  mov     [rbp+57h+arg_0], eax
0x140082d11  lea     rax, [rbp+57h+arg_0]
0x140082d15  mov     [rsp+0C0h+var_90], rax
0x140082d1a  lea     rax, [rbp+57h+arg_8]
0x140082d1e  mov     [rsp+0C0h+var_98], rax
0x140082d23  lea     rax, [rbp+57h+arg_10]
0x140082d27  mov     [rsp+0C0h+var_A0], rax
0x140082d2c  mov     word ptr [rbp+57h+arg_8], bx
0x140082d30  mov     [rbp+57h+arg_10], 3000800h
0x140082d38  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$01@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$01@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x140082d3d  mov     rcx, cs:WPP_GLOBAL_Control
0x140082d44  cmp     rcx, r13
0x140082d47  jz      short loc_140082D5D
0x140082d49  test    dword ptr [rcx+2Ch], 40000h
0x140082d50  jz      short loc_140082D5D
0x140082d52  cmp     byte ptr [rcx+29h], 3
0x140082d56  jb      short loc_140082D5D
0x140082d58  mov     dl, dil
0x140082d5b  jmp     short loc_140082D5F
0x140082d5d  xor     dl, dl
0x140082d5f  lea     rax, WPP_RECORDER_INITIALIZED
0x140082d66  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140082d6d  setnz   r8b
0x140082d71  test    dl, dl
0x140082d73  jnz     short loc_140082D7A
0x140082d75  test    r8b, r8b
0x140082d78  jz      short loc_140082DBD
0x140082d7a  mov     [rsp+0C0h+var_70], rsi
0x140082d7f  movzx   eax, r15b
0x140082d83  mov     dword ptr [rsp+0C0h+var_78], eax
0x140082d87  lea     rax, WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids
0x140082d8e  movzx   r9d, bx
0x140082d92  mov     dword ptr [rsp+0C0h+var_80], r9d
0x140082d97  mov     r9, [rcx+40h]
0x140082d9b  mov     rcx, [rcx+18h]
0x140082d9f  mov     [rsp+0C0h+var_88], rax
0x140082da4  mov     word ptr [rsp+0C0h+var_90], 60h ; '`'
0x140082dab  mov     dword ptr [rsp+0C0h+var_98], 13h
0x140082db3  mov     byte ptr [rsp+0C0h+var_A0], 3
0x140082db8  call    WPP_RECORDER_AND_TRACE_SF_llq
0x140082dbd  mov     rcx, [rbp+57h+var_58]; this
0x140082dc1  mov     [r14], edi
0x140082dc4  test    rcx, rcx
0x140082dc7  jz      short loc_140082DCE
0x140082dc9  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140082dce  mov     rcx, [rbp+57h+var_48]; this
0x140082dd2  test    rcx, rcx
0x140082dd5  jz      short loc_140082DDC
0x140082dd7  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140082ddc  xor     ebx, ebx
0x140082dde  lea     rcx, [rbp+57h+arg_18]
0x140082de2  call    ??1?$unique_storage@U?$resource_policy@PEAU_FAST_MUTEX@@$$A6AXPEAU1@@_E$1?release_fast_mutex_with_critical_region@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140082de7  mov     eax, ebx
0x140082de9  add     rsp, 88h
0x140082df0  pop     r15
0x140082df2  pop     r14
  ... truncated ...
```
