# WnfStateNameRegistrar::RegisterWnfState(ulong,_SECURITY_DESCRIPTOR *,_GUID *,_WNF_STATE_NAME *)

- ea: `0x140205874`
- end: `0x140205c98`
- name: `?RegisterWnfState@WnfStateNameRegistrar@@QEAAJKPEAU_SECURITY_DESCRIPTOR@@PEAU_GUID@@PEAU_WNF_STATE_NAME@@@Z`
- size: `1060`
- prototype: `__int64 __fastcall(WnfStateNameRegistrar *__hidden this, unsigned int, struct _SECURITY_DESCRIPTOR *, struct _GUID *, struct _WNF_STATE_NAME *)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x140009044`
- `0x1400f7af4`

## callees

- `0x140005b4c`
- `0x140005c04`
- `0x140005dd8`
- `0x140019ff8`
- `0x140024ac4`
- `0x140026d7c`
- `0x14002a504`
- `0x14012d72c`
- `0x140131a98`
- `0x14015bf58`
- `0x14015eef8`
- `0x140205874`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1402059f6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1402059f6`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140205a07`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140205a07`
- `ntoskrnl!ZwCreateWnfStateName` at `0x140205958`
- `ntoskrnl!ZwCreateWnfStateName` at `0x140205958`

## pseudocode

```c
__int64 __fastcall WnfStateNameRegistrar::RegisterWnfState(
        WnfStateNameRegistrar *this,
        __int64 a2,
        struct _SECURITY_DESCRIPTOR *a3,
        struct _GUID *a4,
        struct _WNF_STATE_NAME *a5)
{
  struct _GUID *v6; // r15
  struct _GUID *v7; // rdx
  struct _GUID *v8; // rbx
  char v9; // dl
  unsigned int RecorderLog; // eax
  _QWORD *v11; // rcx
  __int64 v12; // r10
  int v13; // edx
  int v14; // r8d
  int WnfStateName; // ebx
  unsigned int v16; // eax
  _QWORD *v17; // rcx
  int v18; // r8d
  __int64 v19; // r10
  int v20; // edx
  struct utl::_DlistNode<utl::shared_ptr<WnfStateNameRegistrar::WnfStateContext> > *MyDnext; // rbx
  __int64 v23; // rax
  struct utl::_DlistNode<utl::shared_ptr<WnfStateNameRegistrar::WnfStateContext> > *v24; // rdi
  char v25; // dl
  unsigned int v26; // eax
  _QWORD *v27; // rcx
  __int64 v28; // r10
  int v29; // edx
  int v30; // r8d
  __int64 v31; // rcx
  void **v32; // rdx
  unsigned int v33; // eax
  int v34; // r8d
  _QWORD *v35; // rcx
  __int64 v36; // r10
  int v37; // edx
  _QWORD *v38; // rbx
  _QWORD *v39; // rdx
  __int64 v40; // rax
  utl::_RefCountBase *v41; // rcx
  struct _WNF_STATE_NAME *v42; // rcx
  _QWORD *v43; // rbx
  _QWORD *v44; // rdx
  __int64 v45; // rax
  utl::_RefCountBase *v46; // rcx
  struct utl::_DlistNode<utl::shared_ptr<WnfStateNameRegistrar::WnfStateContext> > *v47; // [rsp+58h] [rbp-21h] BYREF
  utl::list<utl::shared_ptr<WnfStateNameRegistrar::WnfStateContext>,utl::allocator<utl::shared_ptr<WnfStateNameRegistrar::WnfStateContext> > > *p_m_wnfStateContexts; // [rsp+60h] [rbp-19h] BYREF
  wil::push_lock *p_m_lock; // [rsp+68h] [rbp-11h] BYREF
  GUID ActivityId; // [rsp+70h] [rbp-9h] BYREF
  struct _GUID *v51; // [rsp+80h] [rbp+7h] BYREF
  utl::_RefCountBase *v52; // [rsp+88h] [rbp+Fh]
  void *v53; // [rsp+90h] [rbp+17h] BYREF
  void **v54; // [rsp+98h] [rbp+1Fh]
  __int64 v55; // [rsp+A0h] [rbp+27h]

  v6 = a4;
  utl::make_shared<WnfStateNameRegistrar::WnfStateContext,>(&v51);
  v8 = v51;
  if ( !v51 )
  {
LABEL_33:
    if ( v52 )
      utl::_RefCountBase::_DecStrong(v52);
    return 3221225626LL;
  }
  *v8 = *Microsoft::Bluetooth::Foundation::ActivityIdFactory::GetNextId(&ActivityId, v7);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 || (v9 = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
    v9 = 0;
  if ( v9 || LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    RecorderLog = (unsigned int)Fdo::GetRecorderLog(this->m_fdo);
    WPP_RECORDER_AND_TRACE_SF_q_guid_(
      *(_QWORD *)(v12 + 24),
      v13,
      v14,
      RecorderLog,
      5,
      1,
      11,
      (__int64)WPP_30bad959c23b372925b958b8ac05da3d_Traceguids,
      *v11,
      (__int64)v8);
  }
  WnfStateName = ZwCreateWnfStateName(&v8[1], 3, 4);
  if ( WnfStateName < 0 )
  {
    v16 = (unsigned int)Fdo::GetRecorderLog(this->m_fdo);
    LOBYTE(v18) = 1;
    WPP_RECORDER_AND_TRACE_SF_qL(
      *(_QWORD *)(v19 + 24),
      v20,
      v18,
      v16,
      2,
      1,
      12,
      (__int64)WPP_30bad959c23b372925b958b8ac05da3d_Traceguids,
      *v17,
      WnfStateName);
    if ( v52 )
      utl::_RefCountBase::_DecStrong(v52);
    return (unsigned int)WnfStateName;
  }
  v55 = 0;
  v53 = &v53;
  v54 = &v53;
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(&this->m_lock, 0);
  p_m_lock = &this->m_lock;
  MyDnext = this->m_wnfStateContexts._MyList._MyHead._MyDnext;
  v47 = MyDnext;
  p_m_wnfStateContexts = &this->m_wnfStateContexts;
  if ( (unsigned __int8)____9U__intrusive_member_hook_traits__MPEQ_HCI_COMMAND_BIP_CONTEXT__U_LIST_ENTRY__0LI__Foundation_Bluetooth_Microsoft___0A__0A__Details_Foundation_Bluetooth_Microsoft__YA_NAEBV__iterator_t_U__intrusive_member_hook_traits__MPEQ_HCI_COMMAND_BIP_CONTEXT__U_LIST_ENTRY__0LI__Foundation_Bluetooth_Microsoft___0A__0123_0_Z(
                          &v47,
                          &p_m_wnfStateContexts) )
  {
    do
    {
      v23 = *((_QWORD *)MyDnext + 2);
      if ( *(_BYTE *)(v23 + 24) && (++*(_DWORD *)(v23 + 28), *(_DWORD *)(v23 + 28) >= this->m_cleanupPassLimit) )
      {
        v24 = MyDnext;
        MyDnext = *(struct utl::_DlistNode<utl::shared_ptr<WnfStateNameRegistrar::WnfStateContext> > **)MyDnext;
        v47 = MyDnext;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 || (v25 = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
          v25 = 0;
        if ( v25 || LOWORD(WPP_GLOBAL_Control->DeviceType) )
        {
          v26 = (unsigned int)Fdo::GetRecorderLog(this->m_fdo);
          WPP_RECORDER_AND_TRACE_SF_q_guid_(
            *(_QWORD *)(v28 + 24),
            v29,
            v30,
            v26,
            5,
            1,
            13,
            (__int64)WPP_30bad959c23b372925b958b8ac05da3d_Traceguids,
            *v27,
            *((_QWORD *)v24 + 2));
        }
        *(_QWORD *)&ActivityId.Data1 = v24;
        p_m_wnfStateContexts = (utl::list<utl::shared_ptr<WnfStateNameRegistrar::WnfStateContext>,utl::allocator<utl::shared_ptr<WnfStateNameRegistrar::WnfStateContext> > > *)&v53;
        if ( (unsigned __int8)____9U__intrusive_member_hook_traits__MPEQ_HCI_COMMAND_BIP_CONTEXT__U_LIST_ENTRY__0LI__Foundation_Bluetooth_Microsoft___0A__0A__Details_Foundation_Bluetooth_Microsoft__YA_NAEBV__iterator_t_U__intrusive_member_hook_traits__MPEQ_HCI_COMMAND_BIP_CONTEXT__U_LIST_ENTRY__0LI__Foundation_Bluetooth_Microsoft___0A__0123_0_Z(
                                &ActivityId,
                                &p_m_wnfStateContexts) )
        {
          v31 = *(_QWORD *)v24;
          v32 = *(void ***)(*(_QWORD *)v24 + 8LL);
          **((_QWORD **)v24 + 1) = *(_QWORD *)v24;
          *(_QWORD *)(v31 + 8) = *((_QWORD *)v24 + 1);
          *((_QWORD *)v24 + 1) = v54;
          *v54 = v24;
          *v32 = &v53;
          --this->m_wnfStateContexts._MySize;
          ++v55;
          v54 = v32;
        }
      }
      else
      {
        MyDnext = *(struct utl::_DlistNode<utl::shared_ptr<WnfStateNameRegistrar::WnfStateContext> > **)MyDnext;
        v47 = MyDnext;
      }
      p_m_wnfStateContexts = &this->m_wnfStateContexts;
    }
    while ( (unsigned __int8)____9U__intrusive_member_hook_traits__MPEQ_HCI_COMMAND_BIP_CONTEXT__U_LIST_ENTRY__0LI__Foundation_Bluetooth_Microsoft___0A__0A__Details_Foundation_Bluetooth_Microsoft__YA_NAEBV__iterator_t_U__intrusive_member_hook_traits__MPEQ_HCI_COMMAND_BIP_CONTEXT__U_LIST_ENTRY__0LI__Foundation_Bluetooth_Microsoft___0A__0123_0_Z(
                               &v47,
                               &p_m_wnfStateContexts) );
    v6 = a4;
  }
  if ( !(unsigned __int8)utl::list<utl::shared_ptr<PeriodicAdvertisingSyncQueueEvent>,utl::allocator<utl::shared_ptr<PeriodicAdvertisingSyncQueueEvent>>>::push_back(
                           &this->m_wnfStateContexts,
                           &v51) )
  {
    v33 = (unsigned int)Fdo::GetRecorderLog(this->m_fdo);
    LOBYTE(v34) = 1;
    WPP_RECORDER_AND_TRACE_SF_q(
      *(_QWORD *)(v36 + 24),
      v37,
      v34,
      v33,
      2,
      1,
      14,
      (__int64)WPP_30bad959c23b372925b958b8ac05da3d_Traceguids,
      *v35);
    __1__unique_storage_U__resource_policy_PEAU_EX_PUSH_LOCK__P6AXPEAU1___E_1_release_push_lock_exclusive_details_wil__YAX0_ZU__integral_constant__K_00_wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAA_XZ(&p_m_lock);
    while ( 1 )
    {
      v38 = v53;
      if ( v53 == &v53 )
        break;
      v39 = (_QWORD *)*((_QWORD *)v53 + 1);
      v40 = *(_QWORD *)v53;
      *v39 = *(_QWORD *)v53;
      *(_QWORD *)(v40 + 8) = v39;
      v41 = (utl::_RefCountBase *)v38[3];
      if ( v41 )
        utl::_RefCountBase::_DecStrong(v41);
      operator delete(v38);
    }
    v55 = 0;
    goto LABEL_33;
  }
  __1__unique_storage_U__resource_policy_PEAU_EX_PUSH_LOCK__P6AXPEAU1___E_1_release_push_lock_exclusive_details_wil__YAX0_ZU__integral_constant__K_00_wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAA_XZ(&p_m_lock);
  v42 = (struct _WNF_STATE_NAME *)v51;
  *v6 = *v51;
  *a5 = v42[2];
  while ( 1 )
  {
    v43 = v53;
    if ( v53 == &v53 )
      break;
    v44 = (_QWORD *)*((_QWORD *)v53 + 1);
    v45 = *(_QWORD *)v53;
    *v44 = *(_QWORD *)v53;
    *(_QWORD *)(v45 + 8) = v44;
    v46 = (utl::_RefCountBase *)v43[3];
    if ( v46 )
      utl::_RefCountBase::_DecStrong(v46);
    operator delete(v43);
  }
  v55 = 0;
  if ( v52 )
    utl::_RefCountBase::_DecStrong(v52);
  return 0;
}

```

## disassembly

```asm
0x140205874  mov     rax, rsp
0x140205877  mov     [rax+8], rbx
0x14020587b  mov     [rax+10h], rsi
0x14020587f  mov     [rax+20h], r9
0x140205883  push    rbp
0x140205884  push    rdi
0x140205885  push    r12
0x140205887  push    r14
0x140205889  push    r15
0x14020588b  lea     rbp, [rax-57h]
0x14020588f  sub     rsp, 0A0h
0x140205896  mov     r14, rcx
0x140205899  mov     r15, r9
0x14020589c  lea     rcx, [rbp+4Fh+var_48]
0x1402058a0  mov     rdi, r8
0x1402058a3  mov     esi, edx
0x1402058a5  call    ??$make_shared@UWnfStateContext@WnfStateNameRegistrar@@$$V@utl@@YA?AV?$shared_ptr@UWnfStateContext@WnfStateNameRegistrar@@@0@XZ; utl::make_shared<WnfStateNameRegistrar::WnfStateContext,>(void)
0x1402058aa  mov     rbx, [rbp+4Fh+var_48]
0x1402058ae  xor     r12d, r12d
0x1402058b1  test    rbx, rbx
0x1402058b4  jz      loc_140205BFC
0x1402058ba  lea     rcx, [rbp+4Fh+ActivityId]; ActivityId
0x1402058be  call    ?GetNextId@ActivityIdFactory@Foundation@Bluetooth@Microsoft@@YA?AU_GUID@@XZ; Microsoft::Bluetooth::Foundation::ActivityIdFactory::GetNextId(void)
0x1402058c3  movups  xmm0, xmmword ptr [rax]
0x1402058c6  movdqu  xmmword ptr [rbx], xmm0
0x1402058ca  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1402058d1  mov     eax, [r10+2Ch]
0x1402058d5  test    al, 1
0x1402058d7  jz      short loc_1402058E2
0x1402058d9  cmp     byte ptr [r10+29h], 5
0x1402058de  mov     dl, 1
0x1402058e0  jnb     short loc_1402058E5
0x1402058e2  mov     dl, r12b
0x1402058e5  movzx   eax, word ptr [r10+48h]
0x1402058ea  test    ax, ax
0x1402058ed  setnz   r8b
0x1402058f1  test    dl, dl
0x1402058f3  jnz     short loc_1402058FA
0x1402058f5  test    ax, ax
0x1402058f8  jz      short loc_14020593B
0x1402058fa  mov     rcx, [r14]; this
0x1402058fd  call    ?GetRecorderLog@Fdo@@QEBAPEAURECORDER_LOG__@@XZ; Fdo::GetRecorderLog(void)
0x140205902  mov     [rsp+0C0h+var_78], rbx
0x140205907  mov     r9, rax
0x14020590a  mov     rax, [rcx]
0x14020590d  mov     rcx, [r10+18h]
0x140205911  mov     [rsp+0C0h+var_80], rax
0x140205916  lea     rax, WPP_30bad959c23b372925b958b8ac05da3d_Traceguids
0x14020591d  mov     [rsp+0C0h+var_88], rax
0x140205922  mov     word ptr [rsp+0C0h+var_90], 0Bh
0x140205929  mov     dword ptr [rsp+0C0h+var_98], 1
0x140205931  mov     byte ptr [rsp+0C0h+var_A0], 5
0x140205936  call    WPP_RECORDER_AND_TRACE_SF_q_guid_
0x14020593b  xor     r9d, r9d
0x14020593e  mov     [rsp+0C0h+var_90], rdi
0x140205943  lea     rcx, [rbx+10h]
0x140205947  mov     dword ptr [rsp+0C0h+var_98], esi
0x14020594b  mov     qword ptr [rsp+0C0h+var_A0], r12
0x140205950  lea     edx, [r9+3]
0x140205954  lea     r8d, [r9+4]
0x140205958  call    cs:__imp_ZwCreateWnfStateName
0x14020595f  nop     dword ptr [rax+rax+00h]
0x140205964  mov     ebx, eax
0x140205966  test    eax, eax
0x140205968  jns     short loc_1402059DE
0x14020596a  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140205971  mov     ecx, [r10+2Ch]
0x140205975  test    cl, 1
0x140205978  jz      short loc_140205983
0x14020597a  cmp     byte ptr [r10+29h], 2
0x14020597f  mov     dl, 1
0x140205981  jnb     short loc_140205986
0x140205983  mov     dl, r12b
0x140205986  mov     rcx, [r14]; this
0x140205989  call    ?GetRecorderLog@Fdo@@QEBAPEAURECORDER_LOG__@@XZ; Fdo::GetRecorderLog(void)
0x14020598e  mov     dword ptr [rsp+0C0h+var_78], ebx
0x140205992  mov     r9, rax
0x140205995  mov     rax, [rcx]
0x140205998  mov     r8b, 1
0x14020599b  mov     rcx, [r10+18h]
0x14020599f  mov     [rsp+0C0h+var_80], rax
0x1402059a4  lea     rax, WPP_30bad959c23b372925b958b8ac05da3d_Traceguids
0x1402059ab  mov     [rsp+0C0h+var_88], rax
0x1402059b0  mov     word ptr [rsp+0C0h+var_90], 0Ch
0x1402059b7  mov     dword ptr [rsp+0C0h+var_98], 1
0x1402059bf  mov     byte ptr [rsp+0C0h+var_A0], 2
0x1402059c4  call    WPP_RECORDER_AND_TRACE_SF_qL
0x1402059c9  mov     rcx, [rbp+4Fh+var_40]; this
0x1402059cd  test    rcx, rcx
0x1402059d0  jz      short loc_1402059D7
0x1402059d2  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1402059d7  mov     eax, ebx
0x1402059d9  jmp     loc_140205C0F
0x1402059de  lea     rax, [rbp+4Fh+var_38]
0x1402059e2  mov     [rbp+4Fh+var_28], r12
0x1402059e6  mov     [rbp+4Fh+var_38], rax
0x1402059ea  lea     rbx, [r14+10h]
0x1402059ee  lea     rax, [rbp+4Fh+var_38]
0x1402059f2  mov     [rbp+4Fh+var_30], rax
0x1402059f6  call    cs:__imp_KeEnterCriticalRegion
0x1402059fd  nop     dword ptr [rax+rax+00h]
0x140205a02  xor     edx, edx
0x140205a04  mov     rcx, rbx
0x140205a07  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140205a0e  nop     dword ptr [rax+rax+00h]
0x140205a13  lea     rsi, [r14+18h]
0x140205a17  mov     [rbp+4Fh+var_60], rbx
0x140205a1b  mov     rbx, [rsi]
0x140205a1e  lea     rdx, [rbp+4Fh+var_68]
0x140205a22  lea     rcx, [rbp+4Fh+var_70]
0x140205a26  mov     [rbp+4Fh+var_70], rbx
0x140205a2a  mov     [rbp+4Fh+var_68], rsi
0x140205a2e  call    ??$?9U?$intrusive_member_hook_traits@$MPEQ_HCI_COMMAND_BIP_CONTEXT@@U_LIST_ENTRY@@0LI@@Foundation@Bluetooth@Microsoft@@$0A@$0A@@Details@Foundation@Bluetooth@Microsoft@@YA_NAEBV?$iterator_t@U?$intrusive_member_hook_traits@$MPEQ_HCI_COMMAND_BIP_CONTEXT@@U_LIST_ENTRY@@0LI@@Foundation@Bluetooth@Microsoft@@$0A@@0123@0@Z
0x140205a33  test    al, al
0x140205a35  jz      loc_140205B4E
0x140205a3b  lea     r15, WPP_30bad959c23b372925b958b8ac05da3d_Traceguids
0x140205a42  mov     rax, [rbx+10h]
0x140205a46  cmp     [rax+18h], r12b
0x140205a4a  jnz     short loc_140205A58
0x140205a4c  mov     rbx, [rbx]
0x140205a4f  mov     [rbp+4Fh+var_70], rbx
0x140205a53  jmp     loc_140205B31
0x140205a58  inc     dword ptr [rax+1Ch]
0x140205a5b  mov     eax, [rax+1Ch]
0x140205a5e  cmp     eax, [r14+8]
0x140205a62  jb      short loc_140205A4C
0x140205a64  mov     rdi, rbx
0x140205a67  mov     rbx, [rbx]
0x140205a6a  mov     [rbp+4Fh+var_70], rbx
0x140205a6e  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140205a75  mov     eax, [r10+2Ch]
0x140205a79  test    al, 1
0x140205a7b  jz      short loc_140205A86
0x140205a7d  cmp     byte ptr [r10+29h], 5
0x140205a82  mov     dl, 1
0x140205a84  jnb     short loc_140205A89
0x140205a86  mov     dl, r12b
0x140205a89  movzx   eax, word ptr [r10+48h]
0x140205a8e  test    ax, ax
0x140205a91  setnz   r8b
0x140205a95  test    dl, dl
0x140205a97  jnz     short loc_140205A9E
0x140205a99  test    ax, ax
0x140205a9c  jz      short loc_140205ADC
0x140205a9e  mov     rcx, [r14]; this
0x140205aa1  call    ?GetRecorderLog@Fdo@@QEBAPEAURECORDER_LOG__@@XZ; Fdo::GetRecorderLog(void)
0x140205aa6  mov     r9, rax
0x140205aa9  mov     rax, [rdi+10h]
0x140205aad  mov     [rsp+0C0h+var_78], rax
0x140205ab2  mov     rax, [rcx]
0x140205ab5  mov     rcx, [r10+18h]
0x140205ab9  mov     [rsp+0C0h+var_80], rax
0x140205abe  mov     [rsp+0C0h+var_88], r15
0x140205ac3  mov     word ptr [rsp+0C0h+var_90], 0Dh
0x140205aca  mov     dword ptr [rsp+0C0h+var_98], 1
0x140205ad2  mov     byte ptr [rsp+0C0h+var_A0], 5
0x140205ad7  call    WPP_RECORDER_AND_TRACE_SF_q_guid_
0x140205adc  lea     rax, [rbp+4Fh+var_38]
0x140205ae0  mov     qword ptr [rbp+4Fh+ActivityId.Data1], rdi
0x140205ae4  lea     rdx, [rbp+4Fh+var_68]
0x140205ae8  mov     [rbp+4Fh+var_68], rax
0x140205aec  lea     rcx, [rbp+4Fh+ActivityId]
0x140205af0  call    ??$?9U?$intrusive_member_hook_traits@$MPEQ_HCI_COMMAND_BIP_CONTEXT@@U_LIST_ENTRY@@0LI@@Foundation@Bluetooth@Microsoft@@$0A@$0A@@Details@Foundation@Bluetooth@Microsoft@@YA_NAEBV?$iterator_t@U?$intrusive_member_hook_traits@$MPEQ_HCI_COMMAND_BIP_CONTEXT@@U_LIST_ENTRY@@0LI@@Foundation@Bluetooth@Microsoft@@$0A@@0123@0@Z
0x140205af5  test    al, al
0x140205af7  jz      short loc_140205B31
0x140205af9  mov     rcx, [rdi]
0x140205afc  mov     rax, [rdi+8]
0x140205b00  mov     rdx, [rcx+8]
0x140205b04  mov     [rax], rcx
0x140205b07  mov     rax, [rdi+8]
0x140205b0b  mov     [rcx+8], rax
0x140205b0f  mov     rax, [rbp+4Fh+var_30]
0x140205b13  mov     [rdi+8], rax
0x140205b17  mov     rax, [rbp+4Fh+var_30]
0x140205b1b  mov     [rax], rdi
0x140205b1e  lea     rax, [rbp+4Fh+var_38]
0x140205b22  mov     [rdx], rax
0x140205b25  dec     qword ptr [rsi+10h]
0x140205b29  inc     [rbp+4Fh+var_28]
0x140205b2d  mov     [rbp+4Fh+var_30], rdx
0x140205b31  lea     rdx, [rbp+4Fh+var_68]
0x140205b35  mov     [rbp+4Fh+var_68], rsi
0x140205b39  lea     rcx, [rbp+4Fh+var_70]
0x140205b3d  call    ??$?9U?$intrusive_member_hook_traits@$MPEQ_HCI_COMMAND_BIP_CONTEXT@@U_LIST_ENTRY@@0LI@@Foundation@Bluetooth@Microsoft@@$0A@$0A@@Details@Foundation@Bluetooth@Microsoft@@YA_NAEBV?$iterator_t@U?$intrusive_member_hook_traits@$MPEQ_HCI_COMMAND_BIP_CONTEXT@@U_LIST_ENTRY@@0LI@@Foundation@Bluetooth@Microsoft@@$0A@@0123@0@Z
0x140205b42  test    al, al
0x140205b44  jnz     loc_140205A42
0x140205b4a  mov     r15, [rbp+4Fh+arg_18]
0x140205b4e  lea     rdx, [rbp+4Fh+var_48]
0x140205b52  mov     rcx, rsi
0x140205b55  call    ?push_back@?$list@V?$shared_ptr@VPeriodicAdvertisingSyncQueueEvent@@@utl@@V?$allocator@V?$shared_ptr@VPeriodicAdvertisingSyncQueueEvent@@@utl@@@2@@utl@@QEAA_NAEBV?$shared_ptr@VPeriodicAdvertisingSyncQueueEvent@@@2@@Z; utl::list<utl::shared_ptr<PeriodicAdvertisingSyncQueueEvent>,utl::allocator<utl::shared_ptr<PeriodicAdvertisingSyncQueueEvent>>>::push_back(utl::shared_ptr<PeriodicAdvertisingSyncQueueEvent> const &)
0x140205b5a  test    al, al
0x140205b5c  jnz     loc_140205C2C
0x140205b62  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140205b69  mov     eax, [r10+2Ch]
0x140205b6d  test    al, 1
0x140205b6f  jz      short loc_140205B7A
0x140205b71  cmp     byte ptr [r10+29h], 2
0x140205b76  mov     dl, 1
0x140205b78  jnb     short loc_140205B7D
0x140205b7a  mov     dl, r12b
0x140205b7d  mov     rcx, [r14]; this
0x140205b80  call    ?GetRecorderLog@Fdo@@QEBAPEAURECORDER_LOG__@@XZ; Fdo::GetRecorderLog(void)
0x140205b85  mov     r9, rax
0x140205b88  mov     r8b, 1
0x140205b8b  mov     rax, [rcx]
0x140205b8e  mov     rcx, [r10+18h]
0x140205b92  mov     [rsp+0C0h+var_80], rax
0x140205b97  lea     rax, WPP_30bad959c23b372925b958b8ac05da3d_Traceguids
0x140205b9e  mov     [rsp+0C0h+var_88], rax
0x140205ba3  mov     word ptr [rsp+0C0h+var_90], 0Eh
0x140205baa  mov     dword ptr [rsp+0C0h+var_98], 1
0x140205bb2  mov     byte ptr [rsp+0C0h+var_A0], 2
0x140205bb7  call    WPP_RECORDER_AND_TRACE_SF_q
0x140205bbc  lea     rcx, [rbp+4Fh+var_60]
0x140205bc0  call    ??1?$unique_storage@U?$resource_policy@PEAU_EX_PUSH_LOCK@@P6AXPEAU1@@_E$1?release_push_lock_exclusive@details@wil@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140205bc5  mov     rbx, [rbp+4Fh+var_38]
0x140205bc9  lea     rax, [rbp+4Fh+var_38]
0x140205bcd  cmp     rbx, rax
0x140205bd0  jz      short loc_140205BF8
0x140205bd2  mov     rdx, [rbx+8]
0x140205bd6  mov     rax, [rbx]
0x140205bd9  mov     [rdx], rax
0x140205bdc  mov     [rax+8], rdx
0x140205be0  mov     rcx, [rbx+18h]; this
0x140205be4  test    rcx, rcx
0x140205be7  jz      short loc_140205BEE
0x140205be9  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140205bee  mov     rcx, rbx; void *
0x140205bf1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140205bf6  jmp     short loc_140205BC5
0x140205bf8  mov     [rbp+4Fh+var_28], r12
0x140205bfc  mov     rcx, [rbp+4Fh+var_40]; this
0x140205c00  test    rcx, rcx
0x140205c03  jz      short loc_140205C0A
0x140205c05  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140205c0a  mov     eax, 0C000009Ah
0x140205c0f  lea     r11, [rsp+0C0h+var_20]
0x140205c17  mov     rbx, [r11+30h]
0x140205c1b  mov     rsi, [r11+38h]
0x140205c1f  mov     rsp, r11
0x140205c22  pop     r15
0x140205c24  pop     r14
0x140205c26  pop     r12
0x140205c28  pop     rdi
0x140205c29  pop     rbp
0x140205c2a  retn
0x140205c2c  lea     rcx, [rbp+4Fh+var_60]
0x140205c30  call    ??1?$unique_storage@U?$resource_policy@PEAU_EX_PUSH_LOCK@@P6AXPEAU1@@_E$1?release_push_lock_exclusive@details@wil@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140205c35  mov     rcx, [rbp+4Fh+var_48]
0x140205c39  mov     rax, [rbp+4Fh+arg_20]
0x140205c3d  movups  xmm0, xmmword ptr [rcx]
0x140205c40  movdqu  xmmword ptr [r15], xmm0
0x140205c45  mov     rcx, [rcx+10h]
0x140205c49  mov     [rax], rcx
0x140205c4c  mov     rbx, [rbp+4Fh+var_38]
0x140205c50  lea     rax, [rbp+4Fh+var_38]
0x140205c54  cmp     rbx, rax
0x140205c57  jz      short loc_140205C7F
0x140205c59  mov     rdx, [rbx+8]
0x140205c5d  mov     rax, [rbx]
0x140205c60  mov     [rdx], rax
0x140205c63  mov     [rax+8], rdx
0x140205c67  mov     rcx, [rbx+18h]; this
0x140205c6b  test    rcx, rcx
0x140205c6e  jz      short loc_140205C75
0x140205c70  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140205c75  mov     rcx, rbx; void *
0x140205c78  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140205c7d  jmp     short loc_140205C4C
0x140205c7f  mov     rcx, [rbp+4Fh+var_40]; this
0x140205c83  mov     [rbp+4Fh+var_28], r12
0x140205c87  test    rcx, rcx
0x140205c8a  jz      short loc_140205C91
0x140205c8c  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140205c91  xor     eax, eax
0x140205c93  jmp     loc_140205C0F
```
