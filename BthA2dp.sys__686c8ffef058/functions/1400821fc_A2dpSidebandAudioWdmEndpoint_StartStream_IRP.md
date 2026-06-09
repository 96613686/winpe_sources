# A2dpSidebandAudioWdmEndpoint::StartStream(_IRP *)

- ea: `0x1400821fc`
- end: `0x1400826f0`
- name: `?StartStream@A2dpSidebandAudioWdmEndpoint@@AEAAJPEAU_IRP@@@Z`
- size: `1268`
- prototype: `__int64 __fastcall(A2dpSidebandAudioWdmEndpoint *__hidden this, struct _IRP *)`
- caller_count: `1`
- callee_count: `15`
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
- `0x140014d0c`
- `0x14001f93c`
- `0x1400202e8`
- `0x14002e8c8`
- `0x140033530`
- `0x140036e14`
- `0x140037454`
- `0x140037dc0`
- `0x1400821fc`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14008229c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14008229c`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400822ab`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400822ab`

## pseudocode

```c
__int64 __fastcall A2dpSidebandAudioWdmEndpoint::StartStream(A2dpSidebandAudioWdmEndpoint *this, struct _IRP *a2)
{
  char v3; // di
  __int64 v4; // r8
  int v5; // edx
  int v6; // r14d
  int v7; // edx
  int v8; // r8d
  A2DP_Device *v9; // r15
  int v10; // edx
  __int64 v11; // rbx
  char v12; // al
  __int64 v13; // r8
  __int64 v14; // rdx
  unsigned __int8 v15; // r15
  __int64 v16; // rbx
  int v17; // ecx
  int v18; // r9d
  PVOID DeviceExtension; // r9
  struct _DEVICE_OBJECT *AttachedDevice; // rcx
  utl::_RefCountBase *v21; // rcx
  __int16 v23; // [rsp+30h] [rbp-39h]
  char v24; // [rsp+40h] [rbp-29h]
  char v25; // [rsp+40h] [rbp-29h]
  __int64 v26; // [rsp+60h] [rbp-9h] BYREF
  utl::_RefCountBase *v27; // [rsp+68h] [rbp-1h]
  __int64 v28; // [rsp+70h] [rbp+7h] BYREF
  utl::_RefCountBase *v29; // [rsp+78h] [rbp+Fh]
  int v30; // [rsp+D0h] [rbp+67h] BYREF
  struct _IRP *v31; // [rsp+D8h] [rbp+6Fh] BYREF
  __int64 v32; // [rsp+E0h] [rbp+77h] BYREF
  char *v33; // [rsp+E8h] [rbp+7Fh] BYREF

  v31 = a2;
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
      83,
      (__int64)WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids,
      (char)this);
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)((char *)this + 744));
  v5 = *((_DWORD *)this + 200);
  v6 = -1073741436;
  v33 = (char *)this + 744;
  if ( v5 != 1 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x12u)
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      v3 = 0;
    }
    if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v24 = v5;
      LOBYTE(v5) = v3;
      LOBYTE(v4) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_Dq(
        WPP_GLOBAL_Control->AttachedDevice,
        v5,
        v4,
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        19,
        84,
        (__int64)WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids,
        v24,
        this);
    }
    goto LABEL_75;
  }
  utl::weak_ptr<BtaMpmContext>::lock((char *)this + 616, &v28, v4);
  if ( (unsigned __int8)utl::operator==<A2dpSidebandAudioWdmDevice>(&v28) )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      v3 = 0;
    }
    if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v7) = v3;
      LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        v7,
        v8,
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        18,
        85,
        (__int64)WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids,
        132);
    }
LABEL_60:
    if ( v29 )
      utl::_RefCountBase::_DecStrong(v29);
    goto LABEL_75;
  }
  v9 = *(A2DP_Device **)(v28 + 488);
  utl::make_shared<wil::details::kernel_event_t<1>,>(&v26);
  if ( !v26 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      v3 = 0;
    }
    if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = v3;
      WPP_RECORDER_AND_TRACE_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        v10,
        WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        19,
        86,
        (__int64)WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids,
        (char)this);
    }
    if ( v27 )
      utl::_RefCountBase::_DecStrong(v27);
    if ( v29 )
      utl::_RefCountBase::_DecStrong(v29);
    v6 = -1073741670;
    goto LABEL_75;
  }
  v11 = MEMORY[0xFFFFF78000000014];
  A2DP_Device::SetPinStateRunning(v9);
  v12 = wil::details::kernel_event_t<1>::wait(v26, *((int *)this + 152));
  v14 = (unsigned __int128)((MEMORY[0xFFFFF78000000014] - v11) * (__int128)0x346DC5D63886594BLL) >> 64;
  v15 = v12 ^ 1;
  v16 = (MEMORY[0xFFFFF78000000014] - v11) / 10000;
  if ( (unsigned int)dword_14006F0F8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_14006F0F8, 0x400000000000LL, v13) )
  {
    v30 = v15;
    LOWORD(v31) = v16;
    v32 = 50333696;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
      v17,
      (unsigned int)byte_140069C41,
      v13,
      v18,
      (__int64)&v32,
      (__int64)&v31,
      (__int64)&v30);
  }
  LOBYTE(v14) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0
             && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
  if ( (_BYTE)v14 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_llq(
      WPP_GLOBAL_Control->AttachedDevice,
      v14,
      v13,
      WPP_GLOBAL_Control->DeviceExtension,
      3,
      19,
      87,
      (__int64)WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids,
      v16,
      v15,
      (char)this);
  }
  if ( v15 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      v3 = 0;
    }
    LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( !v3 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_58;
    DeviceExtension = WPP_GLOBAL_Control->DeviceExtension;
    AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
    v25 = -124;
    v23 = 88;
LABEL_57:
    LOBYTE(v14) = v3;
    WPP_RECORDER_AND_TRACE_SF_d(
      (_DWORD)AttachedDevice,
      v14,
      v13,
      (_DWORD)DeviceExtension,
      2,
      18,
      v23,
      (__int64)WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids,
      v25);
LABEL_58:
    if ( v27 )
      utl::_RefCountBase::_DecStrong(v27);
    goto LABEL_60;
  }
  v6 = A2dpSidebandAudioWdmEndpoint::SendAvdtpBrb<_BRB_HCI_VS_MSFT_AVDTP_START>(this);
  if ( v6 < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      v3 = 0;
    }
    LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( !v3 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_58;
    DeviceExtension = WPP_GLOBAL_Control->DeviceExtension;
    AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
    v25 = v6;
    v23 = 89;
    goto LABEL_57;
  }
  v21 = v27;
  *((_DWORD *)this + 200) = 2;
  if ( v21 )
    utl::_RefCountBase::_DecStrong(v21);
  if ( v29 )
    utl::_RefCountBase::_DecStrong(v29);
  v6 = 0;
LABEL_75:
  __1__unique_storage_U__resource_policy_PEAU_FAST_MUTEX____A6AXPEAU1___E_1_release_fast_mutex_with_critical_region_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAA_XZ(&v33);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400821fc  mov     [rsp-8+arg_8], rdx
0x140082201  push    rbp
0x140082202  push    rbx
0x140082203  push    rsi
0x140082204  push    rdi
0x140082205  push    r12
0x140082207  push    r13
0x140082209  push    r14
0x14008220b  push    r15
0x14008220d  lea     rbp, [rsp-1Fh]
0x140082212  sub     rsp, 88h
0x140082219  mov     rsi, rcx
0x14008221c  mov     rcx, cs:WPP_GLOBAL_Control
0x140082223  lea     r13, WPP_GLOBAL_Control
0x14008222a  mov     edi, 1
0x14008222f  cmp     rcx, r13
0x140082232  jz      short loc_140082246
0x140082234  bt      dword ptr [rcx+2Ch], 12h
0x140082239  jnb     short loc_140082246
0x14008223b  cmp     byte ptr [rcx+29h], 4
0x14008223f  jb      short loc_140082246
0x140082241  mov     dl, dil
0x140082244  jmp     short loc_140082248
0x140082246  xor     dl, dl
0x140082248  lea     r12, WPP_RECORDER_INITIALIZED
0x14008224f  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140082256  lea     r9, WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids
0x14008225d  setnz   r8b
0x140082261  test    dl, dl
0x140082263  jnz     short loc_14008226A
0x140082265  test    r8b, r8b
0x140082268  jz      short loc_140082295
0x14008226a  mov     [rsp+0C0h+var_80], rsi
0x14008226f  mov     [rsp+0C0h+var_88], r9
0x140082274  mov     r9, [rcx+40h]
0x140082278  mov     rcx, [rcx+18h]
0x14008227c  mov     word ptr [rsp+0C0h+var_90], 53h ; 'S'
0x140082283  mov     dword ptr [rsp+0C0h+var_98], 13h
0x14008228b  mov     byte ptr [rsp+0C0h+var_A0], 4
0x140082290  call    WPP_RECORDER_AND_TRACE_SF_q
0x140082295  lea     rbx, [rsi+2E8h]
0x14008229c  call    cs:__imp_KeEnterCriticalRegion
0x1400822a3  nop     dword ptr [rax+rax+00h]
0x1400822a8  mov     rcx, rbx; FastMutex
0x1400822ab  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1400822b2  nop     dword ptr [rax+rax+00h]
0x1400822b7  mov     edx, [rsi+320h]
0x1400822bd  mov     r14d, 0C0000184h
0x1400822c3  mov     [rbp+57h+arg_18], rbx
0x1400822c7  cmp     edx, edi
0x1400822c9  jz      short loc_14008233E
0x1400822cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400822d2  cmp     rcx, r13
0x1400822d5  jz      short loc_1400822E4
0x1400822d7  bt      dword ptr [rcx+2Ch], 12h
0x1400822dc  jnb     short loc_1400822E4
0x1400822de  cmp     byte ptr [rcx+29h], 2
0x1400822e2  jnb     short loc_1400822E7
0x1400822e4  xor     dil, dil
0x1400822e7  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400822ee  setnz   r8b
0x1400822f2  test    dil, dil
0x1400822f5  jnz     short loc_140082300
0x1400822f7  test    r8b, r8b
0x1400822fa  jz      loc_1400826CF
0x140082300  mov     r9, [rcx+40h]
0x140082304  lea     rbx, WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids
0x14008230b  mov     rcx, [rcx+18h]
0x14008230f  mov     [rsp+0C0h+var_78], rsi
0x140082314  mov     dword ptr [rsp+0C0h+var_80], edx
0x140082318  mov     dl, dil
0x14008231b  mov     [rsp+0C0h+var_88], rbx
0x140082320  mov     word ptr [rsp+0C0h+var_90], 54h ; 'T'
0x140082327  mov     dword ptr [rsp+0C0h+var_98], 13h
0x14008232f  mov     byte ptr [rsp+0C0h+var_A0], 2
0x140082334  call    WPP_RECORDER_AND_TRACE_SF_Dq
0x140082339  jmp     loc_1400826CF
0x14008233e  lea     rcx, [rsi+268h]
0x140082345  lea     rdx, [rbp+57h+var_50]
0x140082349  call    ?lock@?$weak_ptr@VBtaMpmContext@@@utl@@QEBA?AV?$shared_ptr@VBtaMpmContext@@@2@XZ; utl::weak_ptr<BtaMpmContext>::lock(void)
0x14008234e  lea     rcx, [rbp+57h+var_50]
0x140082352  call    ??$?8VA2dpSidebandAudioWdmDevice@@@utl@@YA_NAEBV?$shared_ptr@VA2dpSidebandAudioWdmDevice@@@0@$$T@Z; utl::operator==<A2dpSidebandAudioWdmDevice>(utl::shared_ptr<A2dpSidebandAudioWdmDevice> const &,std::nullptr_t)
0x140082357  test    al, al
0x140082359  jz      short loc_1400823CC
0x14008235b  mov     rcx, cs:WPP_GLOBAL_Control
0x140082362  cmp     rcx, r13
0x140082365  jz      short loc_140082376
0x140082367  test    dword ptr [rcx+2Ch], 20000h
0x14008236e  jz      short loc_140082376
0x140082370  cmp     byte ptr [rcx+29h], 2
0x140082374  jnb     short loc_140082379
0x140082376  xor     dil, dil
0x140082379  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140082380  setnz   r8b
0x140082384  test    dil, dil
0x140082387  jnz     short loc_140082392
0x140082389  test    r8b, r8b
0x14008238c  jz      loc_14008262F
0x140082392  mov     r9, [rcx+40h]
0x140082396  lea     rbx, WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids
0x14008239d  mov     rcx, [rcx+18h]
0x1400823a1  mov     dl, dil
0x1400823a4  mov     dword ptr [rsp+0C0h+var_80], r14d
0x1400823a9  mov     [rsp+0C0h+var_88], rbx
0x1400823ae  mov     word ptr [rsp+0C0h+var_90], 55h ; 'U'
0x1400823b5  mov     dword ptr [rsp+0C0h+var_98], 12h
0x1400823bd  mov     byte ptr [rsp+0C0h+var_A0], 2
0x1400823c2  call    WPP_RECORDER_AND_TRACE_SF_d
0x1400823c7  jmp     loc_14008262F
0x1400823cc  mov     rax, [rbp+57h+var_50]
0x1400823d0  lea     rcx, [rbp+57h+var_60]
0x1400823d4  mov     r15, [rax+1E8h]
0x1400823db  call    ??$make_shared@V?$kernel_event_t@$00@details@wil@@$$V@utl@@YA?AV?$shared_ptr@V?$kernel_event_t@$00@details@wil@@@0@XZ; utl::make_shared<wil::details::kernel_event_t<1>,>(void)
0x1400823e0  cmp     [rbp+57h+var_60], 0
0x1400823e5  jnz     loc_14008247A
0x1400823eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400823f2  cmp     rcx, r13
0x1400823f5  jz      short loc_140082406
0x1400823f7  test    dword ptr [rcx+2Ch], 40000h
0x1400823fe  jz      short loc_140082406
0x140082400  cmp     byte ptr [rcx+29h], 2
0x140082404  jnb     short loc_140082409
0x140082406  xor     dil, dil
0x140082409  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140082410  setnz   r8b
0x140082414  test    dil, dil
0x140082417  jnz     short loc_14008241E
0x140082419  test    r8b, r8b
0x14008241c  jz      short loc_140082453
0x14008241e  mov     r9, [rcx+40h]
0x140082422  lea     rbx, WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids
0x140082429  mov     rcx, [rcx+18h]
0x14008242d  mov     dl, dil
0x140082430  mov     [rsp+0C0h+var_80], rsi
0x140082435  mov     [rsp+0C0h+var_88], rbx
0x14008243a  mov     word ptr [rsp+0C0h+var_90], 56h ; 'V'
0x140082441  mov     dword ptr [rsp+0C0h+var_98], 13h
0x140082449  mov     byte ptr [rsp+0C0h+var_A0], 2
0x14008244e  call    WPP_RECORDER_AND_TRACE_SF_q
0x140082453  mov     rcx, [rbp+57h+var_58]; this
0x140082457  test    rcx, rcx
0x14008245a  jz      short loc_140082461
0x14008245c  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140082461  mov     rcx, [rbp+57h+var_48]; this
0x140082465  test    rcx, rcx
0x140082468  jz      short loc_14008246F
0x14008246a  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14008246f  mov     r14d, 0C000009Ah
0x140082475  jmp     loc_1400826CF
0x14008247a  mov     r12, 0FFFFF78000000014h
0x140082484  lea     rdx, [rbp+57h+var_60]
0x140082488  mov     rcx, r15; this
0x14008248b  mov     rbx, [r12]
0x14008248f  call    ?SetPinStateRunning@A2DP_Device@@QEAAXAEBV?$shared_ptr@V?$kernel_event_t@$00@details@wil@@@utl@@@Z; A2DP_Device::SetPinStateRunning(utl::shared_ptr<wil::details::kernel_event_t<1>> const &)
0x140082494  movsxd  rdx, dword ptr [rsi+260h]
0x14008249b  mov     rcx, [rbp+57h+var_60]
0x14008249f  call    ?wait@?$kernel_event_t@$00@details@wil@@QEAA_N_J@Z; wil::details::kernel_event_t<1>::wait(__int64)
0x1400824a4  mov     rcx, [r12]
0x1400824a8  mov     r15b, al
0x1400824ab  sub     rcx, rbx
0x1400824ae  mov     rax, 346DC5D63886594Bh
0x1400824b8  imul    rcx
0x1400824bb  mov     eax, cs:dword_14006F0F8
0x1400824c1  xor     r15b, dil
0x1400824c4  mov     rbx, rdx
0x1400824c7  sar     rbx, 0Bh
0x1400824cb  mov     rcx, rbx
0x1400824ce  shr     rcx, 3Fh
0x1400824d2  add     rbx, rcx
0x1400824d5  cmp     eax, 5
0x1400824d8  jbe     short loc_14008252E
0x1400824da  mov     rdx, 400000000000h
0x1400824e4  lea     rcx, dword_14006F0F8
0x1400824eb  call    _tlgKeywordOn
0x1400824f0  test    al, al
0x1400824f2  jz      short loc_14008252E
0x1400824f4  movzx   eax, r15b
0x1400824f8  lea     rdx, byte_140069C41
0x1400824ff  mov     [rbp+57h+arg_0], eax
0x140082502  lea     rax, [rbp+57h+arg_0]
0x140082506  mov     [rsp+0C0h+var_90], rax
0x14008250b  lea     rax, [rbp+57h+arg_8]
0x14008250f  mov     [rsp+0C0h+var_98], rax
0x140082514  lea     rax, [rbp+57h+arg_10]
0x140082518  mov     [rsp+0C0h+var_A0], rax
0x14008251d  mov     word ptr [rbp+57h+arg_8], bx
0x140082521  mov     [rbp+57h+arg_10], 3000800h
0x140082529  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$01@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$01@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x14008252e  mov     rcx, cs:WPP_GLOBAL_Control
0x140082535  cmp     rcx, r13
0x140082538  jz      short loc_14008254E
0x14008253a  test    dword ptr [rcx+2Ch], 40000h
0x140082541  jz      short loc_14008254E
0x140082543  cmp     byte ptr [rcx+29h], 3
0x140082547  jb      short loc_14008254E
0x140082549  mov     dl, dil
0x14008254c  jmp     short loc_140082550
0x14008254e  xor     dl, dl
0x140082550  lea     r12, WPP_RECORDER_INITIALIZED
0x140082557  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14008255e  setnz   r8b
0x140082562  test    dl, dl
0x140082564  jnz     short loc_14008256B
0x140082566  test    r8b, r8b
0x140082569  jz      short loc_1400825B0
0x14008256b  mov     [rsp+0C0h+var_70], rsi
0x140082570  movzx   r9d, bx
0x140082574  lea     rbx, WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids
0x14008257b  movzx   eax, r15b
0x14008257f  mov     dword ptr [rsp+0C0h+var_78], eax
0x140082583  mov     dword ptr [rsp+0C0h+var_80], r9d
0x140082588  mov     r9, [rcx+40h]
0x14008258c  mov     rcx, [rcx+18h]
0x140082590  mov     [rsp+0C0h+var_88], rbx
0x140082595  mov     word ptr [rsp+0C0h+var_90], 57h ; 'W'
0x14008259c  mov     dword ptr [rsp+0C0h+var_98], 13h
0x1400825a4  mov     byte ptr [rsp+0C0h+var_A0], 3
0x1400825a9  call    WPP_RECORDER_AND_TRACE_SF_llq
0x1400825ae  jmp     short loc_1400825B7
0x1400825b0  lea     rbx, WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids
0x1400825b7  test    r15b, r15b
0x1400825ba  jz      loc_140082646
0x1400825c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400825c7  cmp     rcx, r13
0x1400825ca  jz      short loc_1400825DB
0x1400825cc  test    dword ptr [rcx+2Ch], 20000h
0x1400825d3  jz      short loc_1400825DB
0x1400825d5  cmp     byte ptr [rcx+29h], 2
0x1400825d9  jnb     short loc_1400825DE
0x1400825db  xor     dil, dil
0x1400825de  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400825e5  setnz   r8b
0x1400825e9  test    dil, dil
0x1400825ec  jnz     short loc_1400825F3
0x1400825ee  test    r8b, r8b
0x1400825f1  jz      short loc_140082621
0x1400825f3  mov     r9, [rcx+40h]
0x1400825f7  mov     rcx, [rcx+18h]
0x1400825fb  mov     dword ptr [rsp+0C0h+var_80], r14d
0x140082600  mov     [rsp+0C0h+var_88], rbx
0x140082605  mov     word ptr [rsp+0C0h+var_90], 58h ; 'X'
0x14008260c  mov     dword ptr [rsp+0C0h+var_98], 12h
0x140082614  mov     dl, dil
0x140082617  mov     byte ptr [rsp+0C0h+var_A0], 2
0x14008261c  call    WPP_RECORDER_AND_TRACE_SF_d
0x140082621  mov     rcx, [rbp+57h+var_58]; this
0x140082625  test    rcx, rcx
0x140082628  jz      short loc_14008262F
0x14008262a  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14008262f  mov     rcx, [rbp+57h+var_48]; this
0x140082633  test    rcx, rcx
0x140082636  jz      loc_1400826CF
0x14008263c  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140082641  jmp     loc_1400826CF
0x140082646  mov     rcx, rsi; this
0x140082649  call    ??$SendAvdtpBrb@U_BRB_HCI_VS_MSFT_AVDTP_START@@@A2dpSidebandAudioWdmEndpoint@@AEAAJW4_BRB_TYPE@@@Z; A2dpSidebandAudioWdmEndpoint::SendAvdtpBrb<_BRB_HCI_VS_MSFT_AVDTP_START>(_BRB_TYPE)
0x14008264e  mov     r14d, eax
0x140082651  test    eax, eax
0x140082653  jns     short loc_1400826A6
0x140082655  mov     rax, cs:WPP_GLOBAL_Control
0x14008265c  cmp     rax, r13
0x14008265f  jz      short loc_140082670
0x140082661  test    dword ptr [rax+2Ch], 20000h
0x140082668  jz      short loc_140082670
0x14008266a  cmp     byte ptr [rax+29h], 2
0x14008266e  jnb     short loc_140082673
0x140082670  xor     dil, dil
0x140082673  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14008267a  setnz   r8b
0x14008267e  test    dil, dil
0x140082681  jnz     short loc_140082688
0x140082683  test    r8b, r8b
0x140082686  jz      short loc_140082621
0x140082688  mov     r9, [rax+40h]
0x14008268c  mov     rcx, [rax+18h]
0x140082690  mov     dword ptr [rsp+0C0h+var_80], r14d
0x140082695  mov     [rsp+0C0h+var_88], rbx
0x14008269a  mov     word ptr [rsp+0C0h+var_90], 59h ; 'Y'
0x1400826a1  jmp     loc_14008260C
0x1400826a6  mov     rcx, [rbp+57h+var_58]; this
0x1400826aa  mov     dword ptr [rsi+320h], 2
0x1400826b4  test    rcx, rcx
0x1400826b7  jz      short loc_1400826BE
0x1400826b9  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1400826be  mov     rcx, [rbp+57h+var_48]; this
0x1400826c2  test    rcx, rcx
0x1400826c5  jz      short loc_1400826CC
0x1400826c7  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1400826cc  xor     r14d, r14d
0x1400826cf  lea     rcx, [rbp+57h+arg_18]
0x1400826d3  call    ??1?$unique_storage@U?$resource_policy@PEAU_FAST_MUTEX@@$$A6AXPEAU1@@_E$1?release_fast_mutex_with_critical_region@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400826d8  mov     eax, r14d
0x1400826db  add     rsp, 88h
0x1400826e2  pop     r15
0x1400826e4  pop     r14
0x1400826e6  pop     r13
0x1400826e8  pop     r12
0x1400826ea  pop     rdi
0x1400826eb  pop     rsi
0x1400826ec  pop     rbx
  ... truncated ...
```
