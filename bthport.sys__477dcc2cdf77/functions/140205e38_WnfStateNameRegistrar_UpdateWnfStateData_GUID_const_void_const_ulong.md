# WnfStateNameRegistrar::UpdateWnfStateData(_GUID const &,void const *,ulong)

- ea: `0x140205e38`
- end: `0x140206046`
- name: `?UpdateWnfStateData@WnfStateNameRegistrar@@QEAAJAEBU_GUID@@PEBXK@Z`
- size: `526`
- prototype: `__int64 __fastcall(WnfStateNameRegistrar *__hidden this, const struct _GUID *, const void *, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140009bc0`
- `0x1400f8f30`

## callees

- `0x140005dd8`
- `0x140019ff8`
- `0x140026d7c`
- `0x14002a504`
- `0x140131a98`
- `0x140205e38`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140205e62`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140205e62`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140205e73`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140205e73`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x140205fa4`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x140205fa4`

## pseudocode

```c
__int64 __fastcall WnfStateNameRegistrar::UpdateWnfStateData(
        WnfStateNameRegistrar *this,
        const struct _GUID *a2,
        const void *a3,
        unsigned int a4)
{
  wil::push_lock *p_m_lock; // rbx
  struct utl::_DlistNode<utl::shared_ptr<WnfStateNameRegistrar::WnfStateContext> > *v5; // rsi
  utl::_RefCountBase *v6; // rdi
  struct utl::_DlistNode<utl::shared_ptr<WnfStateNameRegistrar::WnfStateContext> > **v11; // r9
  struct utl::_DlistNode<utl::shared_ptr<WnfStateNameRegistrar::WnfStateContext> > **v12; // r8
  struct utl::_DlistNode<utl::shared_ptr<WnfStateNameRegistrar::WnfStateContext> > *v13; // rcx
  char v14; // dl
  unsigned int RecorderLog; // eax
  _QWORD *v16; // rcx
  __int64 v17; // r10
  int v18; // edx
  int v19; // r8d
  unsigned int updated; // ebx
  unsigned int v22; // eax
  _QWORD *v23; // rcx
  int v24; // r8d
  __int64 v25; // r10
  int v26; // edx
  utl::list<utl::shared_ptr<WnfStateNameRegistrar::WnfStateContext>,utl::allocator<utl::shared_ptr<WnfStateNameRegistrar::WnfStateContext> > > *p_m_wnfStateContexts; // [rsp+50h] [rbp-58h] BYREF
  wil::push_lock *v28; // [rsp+58h] [rbp-50h] BYREF
  struct utl::_DlistNode<utl::shared_ptr<WnfStateNameRegistrar::WnfStateContext> > *MyDnext; // [rsp+B0h] [rbp+8h] BYREF

  p_m_lock = &this->m_lock;
  v5 = 0;
  v6 = 0;
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(p_m_lock, 0);
  v28 = p_m_lock;
  MyDnext = this->m_wnfStateContexts._MyList._MyHead._MyDnext;
  p_m_wnfStateContexts = &this->m_wnfStateContexts;
  if ( (unsigned __int8)____9U__intrusive_member_hook_traits__MPEQ_HCI_COMMAND_BIP_CONTEXT__U_LIST_ENTRY__0LI__Foundation_Bluetooth_Microsoft___0A__0A__Details_Foundation_Bluetooth_Microsoft__YA_NAEBV__iterator_t_U__intrusive_member_hook_traits__MPEQ_HCI_COMMAND_BIP_CONTEXT__U_LIST_ENTRY__0LI__Foundation_Bluetooth_Microsoft___0A__0123_0_Z(
                          &MyDnext,
                          &p_m_wnfStateContexts) )
  {
    v12 = v11;
    while ( 1 )
    {
      v13 = v12[2];
      if ( *(_QWORD *)v13 == *(_QWORD *)&a2->Data1
        && *((_QWORD *)v13 + 1) == *(_QWORD *)a2->Data4
        && !*((_BYTE *)v13 + 24) )
      {
        break;
      }
      MyDnext = *v11;
      if ( !(unsigned __int8)____9U__intrusive_member_hook_traits__MPEQ_HCI_COMMAND_BIP_CONTEXT__U_LIST_ENTRY__0LI__Foundation_Bluetooth_Microsoft___0A__0A__Details_Foundation_Bluetooth_Microsoft__YA_NAEBV__iterator_t_U__intrusive_member_hook_traits__MPEQ_HCI_COMMAND_BIP_CONTEXT__U_LIST_ENTRY__0LI__Foundation_Bluetooth_Microsoft___0A__0123_0_Z(
                               &MyDnext,
                               &p_m_wnfStateContexts) )
        goto LABEL_11;
    }
    v6 = (utl::_RefCountBase *)v12[3];
    if ( v6 )
      _InterlockedIncrement(&v6->_MyStrong);
    v5 = v13;
  }
LABEL_11:
  __1__unique_storage_U__resource_policy_PEAU_EX_PUSH_LOCK__P6AXPEAU1___E_1_release_push_lock_exclusive_details_wil__YAX0_ZU__integral_constant__K_00_wistd__PEAU1_PEAU1__0A___T_details_wil___details_wil__QEAA_XZ(&v28);
  if ( v5 )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 || (v14 = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
      v14 = 0;
    if ( v14 || LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      RecorderLog = (unsigned int)Fdo::GetRecorderLog(this->m_fdo);
      WPP_RECORDER_AND_TRACE_SF_q_guid_(
        *(_QWORD *)(v17 + 24),
        v18,
        v19,
        RecorderLog,
        5,
        1,
        18,
        (__int64)WPP_30bad959c23b372925b958b8ac05da3d_Traceguids,
        *v16,
        (__int64)a2);
    }
    updated = ZwUpdateWnfStateData((char *)v5 + 16, a3, a4);
    if ( v6 )
      utl::_RefCountBase::_DecStrong(v6);
    return updated;
  }
  else
  {
    v22 = (unsigned int)Fdo::GetRecorderLog(this->m_fdo);
    LOBYTE(v24) = 1;
    WPP_RECORDER_AND_TRACE_SF_q_guid_(
      *(_QWORD *)(v25 + 24),
      v26,
      v24,
      v22,
      2,
      1,
      17,
      (__int64)WPP_30bad959c23b372925b958b8ac05da3d_Traceguids,
      *v23,
      (__int64)a2);
    if ( v6 )
      utl::_RefCountBase::_DecStrong(v6);
    return 3221226021LL;
  }
}

```

## disassembly

```asm
0x140205e38  push    rbx
0x140205e3a  push    rbp
0x140205e3b  push    rsi
0x140205e3c  push    rdi
0x140205e3d  push    r12
0x140205e3f  push    r13
0x140205e41  push    r14
0x140205e43  push    r15
0x140205e45  sub     rsp, 68h
0x140205e49  xor     r13d, r13d
0x140205e4c  lea     rbx, [rcx+10h]
0x140205e50  mov     esi, r13d
0x140205e53  mov     edi, r13d
0x140205e56  mov     r15d, r9d
0x140205e59  mov     r12, r8
0x140205e5c  mov     rbp, rdx
0x140205e5f  mov     r14, rcx
0x140205e62  call    cs:__imp_KeEnterCriticalRegion
0x140205e69  nop     dword ptr [rax+rax+00h]
0x140205e6e  xor     edx, edx
0x140205e70  mov     rcx, rbx
0x140205e73  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140205e7a  nop     dword ptr [rax+rax+00h]
0x140205e7f  lea     rax, [r14+18h]
0x140205e83  mov     [rsp+0A8h+var_50], rbx
0x140205e88  mov     r9, [rax]
0x140205e8b  lea     rdx, [rsp+0A8h+var_58]
0x140205e90  lea     rcx, [rsp+0A8h+arg_0]
0x140205e98  mov     [rsp+0A8h+arg_0], r9
0x140205ea0  mov     [rsp+0A8h+var_58], rax
0x140205ea5  call    ??$?9U?$intrusive_member_hook_traits@$MPEQ_HCI_COMMAND_BIP_CONTEXT@@U_LIST_ENTRY@@0LI@@Foundation@Bluetooth@Microsoft@@$0A@$0A@@Details@Foundation@Bluetooth@Microsoft@@YA_NAEBV?$iterator_t@U?$intrusive_member_hook_traits@$MPEQ_HCI_COMMAND_BIP_CONTEXT@@U_LIST_ENTRY@@0LI@@Foundation@Bluetooth@Microsoft@@$0A@@0123@0@Z
0x140205eaa  test    al, al
0x140205eac  jz      short loc_140205F04
0x140205eae  mov     r8, r9
0x140205eb1  mov     rcx, [r8+10h]
0x140205eb5  mov     rax, [rcx]
0x140205eb8  cmp     rax, [rbp+0]
0x140205ebc  jnz     short loc_140205ECE
0x140205ebe  mov     rax, [rcx+8]
0x140205ec2  cmp     rax, [rbp+8]
0x140205ec6  jnz     short loc_140205ECE
0x140205ec8  cmp     [rcx+18h], r13b
0x140205ecc  jz      short loc_140205EF4
0x140205ece  mov     r8, [r9]
0x140205ed1  lea     rdx, [rsp+0A8h+var_58]
0x140205ed6  lea     rcx, [rsp+0A8h+arg_0]
0x140205ede  mov     [rsp+0A8h+arg_0], r8
0x140205ee6  mov     r9, r8
0x140205ee9  call    ??$?9U?$intrusive_member_hook_traits@$MPEQ_HCI_COMMAND_BIP_CONTEXT@@U_LIST_ENTRY@@0LI@@Foundation@Bluetooth@Microsoft@@$0A@$0A@@Details@Foundation@Bluetooth@Microsoft@@YA_NAEBV?$iterator_t@U?$intrusive_member_hook_traits@$MPEQ_HCI_COMMAND_BIP_CONTEXT@@U_LIST_ENTRY@@0LI@@Foundation@Bluetooth@Microsoft@@$0A@@0123@0@Z
0x140205eee  test    al, al
0x140205ef0  jnz     short loc_140205EB1
0x140205ef2  jmp     short loc_140205F04
0x140205ef4  mov     rdi, [r8+18h]
0x140205ef8  test    rdi, rdi
0x140205efb  jz      short loc_140205F01
0x140205efd  lock inc dword ptr [rdi+8]
0x140205f01  mov     rsi, rcx
0x140205f04  lea     rcx, [rsp+0A8h+var_50]
0x140205f09  call    ??1?$unique_storage@U?$resource_policy@PEAU_EX_PUSH_LOCK@@P6AXPEAU1@@_E$1?release_push_lock_exclusive@details@wil@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140205f0e  test    rsi, rsi
0x140205f11  jz      loc_140205FC3
0x140205f17  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140205f1e  mov     eax, [r10+2Ch]
0x140205f22  test    al, 1
0x140205f24  jz      short loc_140205F2F
0x140205f26  cmp     byte ptr [r10+29h], 5
0x140205f2b  mov     dl, 1
0x140205f2d  jnb     short loc_140205F32
0x140205f2f  mov     dl, r13b
0x140205f32  movzx   eax, word ptr [r10+48h]
0x140205f37  test    ax, ax
0x140205f3a  setnz   r8b
0x140205f3e  test    dl, dl
0x140205f40  jnz     short loc_140205F47
0x140205f42  test    ax, ax
0x140205f45  jz      short loc_140205F88
0x140205f47  mov     rcx, [r14]; this
0x140205f4a  call    ?GetRecorderLog@Fdo@@QEBAPEAURECORDER_LOG__@@XZ; Fdo::GetRecorderLog(void)
0x140205f4f  mov     r9, [rcx]
0x140205f52  lea     rcx, WPP_30bad959c23b372925b958b8ac05da3d_Traceguids
0x140205f59  mov     [rsp+0A8h+var_60], rbp
0x140205f5e  mov     [rsp+0A8h+var_68], r9
0x140205f63  mov     r9, rax
0x140205f66  mov     [rsp+0A8h+var_70], rcx
0x140205f6b  mov     rcx, [r10+18h]
0x140205f6f  mov     word ptr [rsp+0A8h+var_78], 12h
0x140205f76  mov     [rsp+0A8h+var_80], 1
0x140205f7e  mov     byte ptr [rsp+0A8h+var_88], 5
0x140205f83  call    WPP_RECORDER_AND_TRACE_SF_q_guid_
0x140205f88  mov     [rsp+0A8h+var_78], r13d
0x140205f8d  lea     rcx, [rsi+10h]
0x140205f91  mov     [rsp+0A8h+var_80], r13d
0x140205f96  xor     r9d, r9d
0x140205f99  mov     r8d, r15d
0x140205f9c  mov     [rsp+0A8h+var_88], r13
0x140205fa1  mov     rdx, r12
0x140205fa4  call    cs:__imp_ZwUpdateWnfStateData
0x140205fab  nop     dword ptr [rax+rax+00h]
0x140205fb0  mov     ebx, eax
0x140205fb2  test    rdi, rdi
0x140205fb5  jz      short loc_140205FBF
0x140205fb7  mov     rcx, rdi; this
0x140205fba  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140205fbf  mov     eax, ebx
0x140205fc1  jmp     short loc_140206034
0x140205fc3  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140205fca  mov     eax, [r10+2Ch]
0x140205fce  test    al, 1
0x140205fd0  jz      short loc_140205FDB
0x140205fd2  cmp     byte ptr [r10+29h], 2
0x140205fd7  mov     dl, 1
0x140205fd9  jnb     short loc_140205FDE
0x140205fdb  mov     dl, r13b
0x140205fde  mov     rcx, [r14]; this
0x140205fe1  call    ?GetRecorderLog@Fdo@@QEBAPEAURECORDER_LOG__@@XZ; Fdo::GetRecorderLog(void)
0x140205fe6  mov     r9, [rcx]
0x140205fe9  mov     r8b, 1
0x140205fec  mov     [rsp+0A8h+var_60], rbp
0x140205ff1  lea     rcx, WPP_30bad959c23b372925b958b8ac05da3d_Traceguids
0x140205ff8  mov     [rsp+0A8h+var_68], r9
0x140205ffd  mov     r9, rax
0x140206000  mov     [rsp+0A8h+var_70], rcx
0x140206005  mov     rcx, [r10+18h]
0x140206009  mov     word ptr [rsp+0A8h+var_78], 11h
0x140206010  mov     [rsp+0A8h+var_80], 1
0x140206018  mov     byte ptr [rsp+0A8h+var_88], 2
0x14020601d  call    WPP_RECORDER_AND_TRACE_SF_q_guid_
0x140206022  test    rdi, rdi
0x140206025  jz      short loc_14020602F
0x140206027  mov     rcx, rdi; this
0x14020602a  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14020602f  mov     eax, 0C0000225h
0x140206034  add     rsp, 68h
0x140206038  pop     r15
0x14020603a  pop     r14
0x14020603c  pop     r13
0x14020603e  pop     r12
0x140206040  pop     rdi
0x140206041  pop     rsi
0x140206042  pop     rbp
0x140206043  pop     rbx
0x140206044  retn
```
