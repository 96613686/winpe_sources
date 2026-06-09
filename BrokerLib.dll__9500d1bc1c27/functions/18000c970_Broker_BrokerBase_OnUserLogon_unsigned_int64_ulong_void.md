# Broker::BrokerBase::OnUserLogon(unsigned __int64,ulong,void *)

- ea: `0x18000c970`
- end: `0x18000ccb5`
- name: `?OnUserLogon@BrokerBase@Broker@@AEAAX_KKPEAX@Z`
- size: `837`
- prototype: `void __fastcall(struct _RTL_SRWLOCK *this, unsigned __int64, unsigned int, void *)`
- caller_count: `2`
- callee_count: `21`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000c4c0`
- `0x18000c8d0`

## callees

- `0x180001cbc`
- `0x180002614`
- `0x180003760`
- `0x180003980`
- `0x180004500`
- `0x180004ae0`
- `0x180004c70`
- `0x180004e38`
- `0x180006540`
- `0x180008340`
- `0x180008604`
- `0x1800088c8`
- `0x180008dd8`
- `0x18000c970`
- `0x18000eb40`
- `0x18000ed50`
- `0x18000f400`
- `0x18000fe88`
- `0x1800111d4`
- `0x180014474`
- `0x180017308`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000caeb`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000caeb`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000c9ec`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000c9ec`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000cbdf`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000cbdf`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall Broker::BrokerBase::OnUserLogon(struct _RTL_SRWLOCK *this, __int64 a2, __int64 a3, char *a4)
{
  char *v4; // rsi
  unsigned int v5; // ebx
  struct _RTL_SRWLOCK *v7; // rdi
  char v8; // al
  __int64 i; // rbx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 j; // rbx
  int v15; // r8d
  int v16; // r9d
  int v17; // ecx
  Broker::ApplicationStateTable::State *Ptr; // rax
  char *pSida; // [rsp+20h] [rbp-C8h]
  PSID pSid; // [rsp+20h] [rbp-C8h]
  char v21[8]; // [rsp+30h] [rbp-B8h] BYREF
  Broker::ApplicationStateTable::State *v22; // [rsp+38h] [rbp-B0h] BYREF
  std::_Ref_count_base *v23; // [rsp+40h] [rbp-A8h]
  int v24; // [rsp+48h] [rbp-A0h] BYREF
  Broker::ApplicationIdentity *v25[2]; // [rsp+50h] [rbp-98h] BYREF
  __int64 v26; // [rsp+60h] [rbp-88h]
  __int64 v27; // [rsp+68h] [rbp-80h] BYREF
  char v28; // [rsp+70h] [rbp-78h]
  __int128 v29; // [rsp+78h] [rbp-70h] BYREF
  __int64 v30; // [rsp+88h] [rbp-60h]
  _QWORD v31[3]; // [rsp+90h] [rbp-58h] BYREF
  _QWORD v32[3]; // [rsp+A8h] [rbp-40h] BYREF
  Broker::Win32Error *v33; // [rsp+C0h] [rbp-28h] BYREF

  v4 = a4;
  v5 = a3;
  v7 = this;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    WPP_SF__guid__sid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x30u, a3, (__int64)this[1].Ptr, a4);
  Broker::ScopedWriteLock::ScopedWriteLock((Broker::ScopedWriteLock *)&v27, v7, 1);
  v29 = 0;
  v30 = 0;
  pSida = &v4[GetLengthSid(v4)];
  std::vector<unsigned char>::insert<unsigned char *,0>(
    (unsigned int)&v29,
    (unsigned int)&v22,
    DWORD2(v29),
    (_DWORD)v4,
    (__int64)pSida);
  try
  {
    v8 = Broker::UserContextTable::UserLogon(&v7[32], a2, &v29, v5);
  }
  catch ( std::bad_alloc )
  {
    v7 = this;
    v4 = a4;
    goto LABEL_10;
  }
  if ( v8 )
  {
LABEL_10:
    Broker::BrokerBase::SelectUserAppStates(v7, v32, &v29);
    for ( i = v32[0]; i != v32[1]; i += 16 )
    {
      std::shared_ptr<Broker::BrokerBase>::shared_ptr<Broker::BrokerBase>(&v22, i);
      *((_DWORD *)v22 + 35) = 0;
      if ( v23 )
        std::_Ref_count_base::_Decref(v23);
    }
    RtlReleaseSRWLockExclusive(v27);
    try
    {
      v28 = 0;
      Broker::CoInitWrapper::CoInitWrapper((Broker::CoInitWrapper *)v21);
      Broker::BackgroundAccessApplicationsWrapper::GetBackgroundAccessAppsForUser(v10, v25, v4);
      Broker::ScopedWriteLock::Acquire((Broker::ScopedWriteLock *)&v27);
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        LODWORD(pSid) = -1171354717 * ((v25[1] - v25[0]) >> 3);
        WPP_SF__sid_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          0x32u,
          &WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids,
          v4,
          pSid);
      }
      std::for_each_std::_Vector_iterator_std::_Vector_val_std::_Simple_types_Broker::ApplicationIdentity_______lambda_df661c2a494d52659c55fd0f8700369c___(
        &v22,
        v25[0],
        v25[1],
        v7);
      if ( v25[0] )
      {
        std::_Destroy_range<std::allocator<Broker::ApplicationIdentity>>(v25[0]);
        std::_Deallocate<16>(v25[0], 8 * ((signed __int64)(v26 - (unsigned __int64)v25[0]) >> 3));
        *(_OWORD *)v25 = 0;
        v26 = 0;
      }
      CoUninitialize();
    }
    catch ( std::bad_alloc )
    {
      v7 = this;
    }
    catch ( Broker::Win32Error *v33 )
    {
      if ( (unsigned int)dword_180028000 > 5 && (unsigned __int8)tlgKeywordOn(v11, 0x400000000000LL, v12, v13) )
      {
        v17 = *((_DWORD *)v33 + 8);
        v24 = v17;
        if ( this[1].Ptr )
          Ptr = (Broker::ApplicationStateTable::State *)this[1].Ptr;
        else
          Ptr = 0;
        v22 = Ptr;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
          v17,
          (unsigned int)&unk_180021E27,
          v15,
          v16,
          (__int64)&v22,
          (__int64)&v24);
      }
      v7 = this;
    }
    Broker::BrokerBase::SelectUserAppStates(v7, v31, &v29);
    for ( j = v31[0]; j != v31[1]; j += 16 )
    {
      std::shared_ptr<Broker::BrokerBase>::shared_ptr<Broker::BrokerBase>(&v22, j);
      if ( Broker::ApplicationStateTable::State::OnUserLogon(v22) )
        Broker::BrokerBase::OnAppEnable(v7, 6, v22);
      if ( v23 )
        std::_Ref_count_base::_Decref(v23);
    }
    std::vector<std::shared_ptr<Broker::BILayer::WnfNotification>>::_Tidy(v31);
    std::vector<std::shared_ptr<Broker::BILayer::WnfNotification>>::_Tidy(v32);
    std::vector<unsigned char>::_Tidy(&v29);
    Broker::ScopedWriteLock::~ScopedWriteLock((Broker::ScopedWriteLock *)&v27);
  }
  else
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      WPP_SF__sid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x31u, &WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids, v4);
    std::vector<unsigned char>::_Tidy(&v29);
    Broker::ScopedWriteLock::~ScopedWriteLock((Broker::ScopedWriteLock *)&v27);
  }
}

```

## disassembly

```asm
0x18000c970  mov     [rsp+arg_8], rbx
0x18000c975  mov     [rsp+arg_18], r9
0x18000c97a  mov     [rsp+arg_0], rcx
0x18000c97f  push    rsi
0x18000c980  push    rdi
0x18000c981  push    r15
0x18000c983  sub     rsp, 0D0h
0x18000c98a  mov     rsi, r9
0x18000c98d  mov     ebx, r8d
0x18000c990  mov     r15, rdx
0x18000c993  mov     rdi, rcx
0x18000c996  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c99d  test    dword ptr [rcx+1Ch], 800h
0x18000c9a4  jz      short loc_18000C9C3
0x18000c9a6  cmp     byte ptr [rcx+19h], 5
0x18000c9aa  jb      short loc_18000C9C3
0x18000c9ac  mov     edx, 30h ; '0'
0x18000c9b1  mov     [rsp+0E8h+pSid], r9; pSid
0x18000c9b6  mov     r9, [rdi+8]
0x18000c9ba  mov     rcx, [rcx+10h]; LoggerHandle
0x18000c9be  call    WPP_SF__guid__sid_
0x18000c9c3  mov     r8b, 1; bool
0x18000c9c6  mov     rdx, rdi; struct _RTL_SRWLOCK *
0x18000c9c9  lea     rcx, [rsp+0E8h+var_80]; this
0x18000c9ce  call    ??0ScopedWriteLock@Broker@@QEAA@AEAU_RTL_SRWLOCK@@_N@Z; Broker::ScopedWriteLock::ScopedWriteLock(_RTL_SRWLOCK &,bool)
0x18000c9d3  nop
0x18000c9d4  xorps   xmm0, xmm0
0x18000c9d7  movdqu  [rsp+0E8h+var_70], xmm0
0x18000c9dd  mov     [rsp+0E8h+var_60], 0
0x18000c9e9  mov     rcx, rsi; pSid
0x18000c9ec  call    cs:__imp_GetLengthSid
0x18000c9f2  mov     ecx, eax
0x18000c9f4  add     rcx, rsi
0x18000c9f7  mov     [rsp+0E8h+pSid], rcx
0x18000c9fc  mov     r9, rsi
0x18000c9ff  mov     r8, qword ptr [rsp+0E8h+var_70+8]
0x18000ca07  lea     rdx, [rsp+0E8h+var_B0]
0x18000ca0c  lea     rcx, [rsp+0E8h+var_70]
0x18000ca11  call    ??$insert@PEAE$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@PEAE1@Z; std::vector<uchar>::insert<uchar *,0>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,uchar *,uchar *)
0x18000ca16  nop
0x18000ca17  lea     rcx, [rdi+100h]
0x18000ca1e  mov     r9d, ebx
0x18000ca21  lea     r8, [rsp+0E8h+var_70]
0x18000ca26  mov     rdx, r15
0x18000ca29  call    ?UserLogon@UserContextTable@Broker@@QEAA_N_KAEBV?$vector@EV?$allocator@E@std@@@std@@K@Z; Broker::UserContextTable::UserLogon(unsigned __int64,std::vector<uchar> const &,ulong)
0x18000ca2e  test    al, al
0x18000ca30  jnz     short loc_18000CA7B
0x18000ca32  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ca39  test    dword ptr [rcx+1Ch], 800h
0x18000ca40  jz      short loc_18000CA61
0x18000ca42  cmp     byte ptr [rcx+19h], 5
0x18000ca46  jb      short loc_18000CA61
0x18000ca48  mov     edx, 31h ; '1'
0x18000ca4d  mov     r9, rsi
0x18000ca50  lea     r8, WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids
0x18000ca57  mov     rcx, [rcx+10h]; LoggerHandle
0x18000ca5b  call    WPP_SF__sid_
0x18000ca60  nop
0x18000ca61  lea     rcx, [rsp+0E8h+var_70]
0x18000ca66  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18000ca6b  nop
0x18000ca6c  lea     rcx, [rsp+0E8h+var_80]; this
0x18000ca71  call    ??1ScopedWriteLock@Broker@@QEAA@XZ; Broker::ScopedWriteLock::~ScopedWriteLock(void)
0x18000ca76  jmp     loc_18000CCA1
0x18000ca7b  jmp     short loc_18000CA8D
0x18000ca7d  mov     rdi, [rsp+0E8h+arg_0]
0x18000ca85  mov     rsi, [rsp+0E8h+arg_18]
0x18000ca8d  lea     r8, [rsp+0E8h+var_70]
0x18000ca92  lea     rdx, [rsp+0E8h+var_40]
0x18000ca9a  mov     rcx, rdi
0x18000ca9d  call    ?SelectUserAppStates@BrokerBase@Broker@@AEAA?AV?$vector@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@V?$allocator@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@2@@std@@AEBV?$vector@EV?$allocator@E@std@@@4@@Z; Broker::BrokerBase::SelectUserAppStates(std::vector<uchar> const &)
0x18000caa2  nop
0x18000caa3  mov     rbx, [rsp+0E8h+var_40]
0x18000caab  cmp     rbx, [rsp+0E8h+var_38]
0x18000cab3  jz      short loc_18000CAE6
0x18000cab5  mov     rdx, rbx
0x18000cab8  lea     rcx, [rsp+0E8h+var_B0]
0x18000cabd  call    ??0?$shared_ptr@VBrokerBase@Broker@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Broker::BrokerBase>::shared_ptr<Broker::BrokerBase>(std::shared_ptr<Broker::BrokerBase> const &)
0x18000cac2  mov     rcx, [rsp+0E8h+var_B0]
0x18000cac7  mov     dword ptr [rcx+8Ch], 0
0x18000cad1  mov     rcx, [rsp+0E8h+var_A8]; this
0x18000cad6  test    rcx, rcx
0x18000cad9  jz      short loc_18000CAE0
0x18000cadb  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000cae0  add     rbx, 10h
0x18000cae4  jmp     short loc_18000CAAB
0x18000cae6  mov     rcx, [rsp+0E8h+var_80]
0x18000caeb  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000caf1  mov     [rsp+0E8h+var_78], 0
0x18000caf6  mov     byte ptr [rsp+0E8h+arg_18], 1
0x18000cafe  lea     rcx, [rsp+0E8h+var_B8]; this
0x18000cb03  call    ??0CoInitWrapper@Broker@@QEAA@XZ; Broker::CoInitWrapper::CoInitWrapper(void)
0x18000cb08  nop
0x18000cb09  mov     r8, rsi
0x18000cb0c  lea     rdx, [rsp+0E8h+var_98]
0x18000cb11  call    ?GetBackgroundAccessAppsForUser@BackgroundAccessApplicationsWrapper@Broker@@QEAA?AV?$vector@UApplicationIdentity@Broker@@V?$allocator@UApplicationIdentity@Broker@@@std@@@std@@PEAX@Z; Broker::BackgroundAccessApplicationsWrapper::GetBackgroundAccessAppsForUser(void *)
0x18000cb16  nop
0x18000cb17  lea     rcx, [rsp+0E8h+var_80]; this
0x18000cb1c  call    ?Acquire@ScopedWriteLock@Broker@@QEAAXXZ; Broker::ScopedWriteLock::Acquire(void)
0x18000cb21  mov     byte ptr [rsp+0E8h+arg_18], 0
0x18000cb29  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cb30  test    dword ptr [rcx+1Ch], 800h
0x18000cb37  jz      short loc_18000CB79
0x18000cb39  cmp     byte ptr [rcx+19h], 5
0x18000cb3d  jb      short loc_18000CB79
0x18000cb3f  mov     rax, [rsp+0E8h+var_98+8]
0x18000cb44  sub     rax, [rsp+0E8h+var_98]
0x18000cb49  sar     rax, 3
0x18000cb4d  mov     rbx, 2E8BA2E8BA2E8BA3h
0x18000cb57  imul    rax, rbx
0x18000cb5b  mov     edx, 32h ; '2'
0x18000cb60  mov     dword ptr [rsp+0E8h+pSid], eax; char
0x18000cb64  mov     r9, rsi
0x18000cb67  lea     r8, WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids
0x18000cb6e  mov     rcx, [rcx+10h]; LoggerHandle
0x18000cb72  call    WPP_SF__sid_d
0x18000cb77  jmp     short loc_18000CB83
0x18000cb79  mov     rbx, 2E8BA2E8BA2E8BA3h
0x18000cb83  mov     r9, rdi
0x18000cb86  mov     r8, [rsp+0E8h+var_98+8]
0x18000cb8b  mov     rdx, [rsp+0E8h+var_98]
0x18000cb90  lea     rcx, [rsp+0E8h+var_B0]
0x18000cb95  call    std__for_each_std___Vector_iterator_std___Vector_val_std___Simple_types_Broker__ApplicationIdentity_______lambda_df661c2a494d52659c55fd0f8700369c___
0x18000cb9a  nop
0x18000cb9b  mov     rcx, [rsp+0E8h+var_98]; this
0x18000cba0  test    rcx, rcx
0x18000cba3  jz      short loc_18000CBDF
0x18000cba5  mov     rdx, [rsp+0E8h+var_98+8]
0x18000cbaa  call    ??$_Destroy_range@V?$allocator@UApplicationIdentity@Broker@@@std@@@std@@YAXPEAUApplicationIdentity@Broker@@QEAU12@AEAV?$allocator@UApplicationIdentity@Broker@@@0@@Z; std::_Destroy_range<std::allocator<Broker::ApplicationIdentity>>(Broker::ApplicationIdentity *,Broker::ApplicationIdentity * const,std::allocator<Broker::ApplicationIdentity> &)
0x18000cbaf  mov     rcx, [rsp+0E8h+var_98]
0x18000cbb4  mov     rax, [rsp+0E8h+var_88]
0x18000cbb9  sub     rax, rcx
0x18000cbbc  sar     rax, 3
0x18000cbc0  imul    rax, rbx
0x18000cbc4  imul    rdx, rax, 58h ; 'X'
0x18000cbc8  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000cbcd  xorps   xmm0, xmm0
0x18000cbd0  movdqu  xmmword ptr [rsp+0E8h+var_98], xmm0
0x18000cbd6  mov     [rsp+0E8h+var_88], 0
0x18000cbdf  call    cs:__imp_CoUninitialize
0x18000cbe5  nop
0x18000cbe6  jmp     short loc_18000CC04
0x18000cbe8  cmp     byte ptr [rsp+0E8h+arg_18], 1
0x18000cbf0  jnz     short loc_18000CBFC
0x18000cbf2  lea     rcx, [rsp+0E8h+var_80]; this
0x18000cbf7  call    ?Acquire@ScopedWriteLock@Broker@@QEAAXXZ; Broker::ScopedWriteLock::Acquire(void)
0x18000cbfc  mov     rdi, [rsp+0E8h+arg_0]
0x18000cc04  lea     r8, [rsp+0E8h+var_70]
0x18000cc09  lea     rdx, [rsp+0E8h+var_58]
0x18000cc11  mov     rcx, rdi
0x18000cc14  call    ?SelectUserAppStates@BrokerBase@Broker@@AEAA?AV?$vector@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@V?$allocator@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@2@@std@@AEBV?$vector@EV?$allocator@E@std@@@4@@Z; Broker::BrokerBase::SelectUserAppStates(std::vector<uchar> const &)
0x18000cc19  nop
0x18000cc1a  mov     rbx, [rsp+0E8h+var_58]
0x18000cc22  cmp     rbx, [rsp+0E8h+var_50]
0x18000cc2a  jz      short loc_18000CC70
0x18000cc2c  mov     rdx, rbx
0x18000cc2f  lea     rcx, [rsp+0E8h+var_B0]
0x18000cc34  call    ??0?$shared_ptr@VBrokerBase@Broker@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Broker::BrokerBase>::shared_ptr<Broker::BrokerBase>(std::shared_ptr<Broker::BrokerBase> const &)
0x18000cc39  nop
0x18000cc3a  mov     rcx, [rsp+0E8h+var_B0]; this
0x18000cc3f  call    ?OnUserLogon@State@ApplicationStateTable@Broker@@QEAA_NXZ; Broker::ApplicationStateTable::State::OnUserLogon(void)
0x18000cc44  test    al, al
0x18000cc46  jz      short loc_18000CC5B
0x18000cc48  mov     r8, [rsp+0E8h+var_B0]
0x18000cc4d  mov     edx, 6
0x18000cc52  mov     rcx, rdi
0x18000cc55  call    ?OnAppEnable@BrokerBase@Broker@@AEAAXW4_BR_EVENT_CALL_REASON@@AEBUApplicationIdentity@2@@Z; Broker::BrokerBase::OnAppEnable(_BR_EVENT_CALL_REASON,Broker::ApplicationIdentity const &)
0x18000cc5a  nop
0x18000cc5b  mov     rcx, [rsp+0E8h+var_A8]; this
0x18000cc60  test    rcx, rcx
0x18000cc63  jz      short loc_18000CC6A
0x18000cc65  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000cc6a  add     rbx, 10h
0x18000cc6e  jmp     short loc_18000CC22
0x18000cc70  lea     rcx, [rsp+0E8h+var_58]
0x18000cc78  call    ?_Tidy@?$vector@V?$shared_ptr@VWnfNotification@BILayer@Broker@@@std@@V?$allocator@V?$shared_ptr@VWnfNotification@BILayer@Broker@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<Broker::BILayer::WnfNotification>>::_Tidy(void)
0x18000cc7d  nop
0x18000cc7e  lea     rcx, [rsp+0E8h+var_40]
0x18000cc86  call    ?_Tidy@?$vector@V?$shared_ptr@VWnfNotification@BILayer@Broker@@@std@@V?$allocator@V?$shared_ptr@VWnfNotification@BILayer@Broker@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<Broker::BILayer::WnfNotification>>::_Tidy(void)
0x18000cc8b  nop
0x18000cc8c  lea     rcx, [rsp+0E8h+var_70]
0x18000cc91  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18000cc96  nop
0x18000cc97  lea     rcx, [rsp+0E8h+var_80]; this
0x18000cc9c  call    ??1ScopedWriteLock@Broker@@QEAA@XZ; Broker::ScopedWriteLock::~ScopedWriteLock(void)
0x18000cca1  mov     rbx, [rsp+0E8h+arg_8]
0x18000cca9  add     rsp, 0D0h
0x18000ccb0  pop     r15
0x18000ccb2  pop     rdi
0x18000ccb3  pop     rsi
0x18000ccb4  retn
```
