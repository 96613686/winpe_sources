# WSD::HealthAdvisor::AdvisorEngine::~AdvisorEngine(void)

- ea: `0x18004e530`
- end: `0x18004e781`
- name: `??1AdvisorEngine@HealthAdvisor@WSD@@EEAA@XZ`
- size: `593`
- prototype: `void __fastcall(WSD::HealthAdvisor::AdvisorEngine *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x18004eb20`

## callees

- `0x180004710`
- `0x18000ccb0`
- `0x18000f02c`
- `0x18000f094`
- `0x180016d08`
- `0x18001e128`
- `0x180029b38`
- `0x180046e44`
- `0x18004d9b0`
- `0x18004e4d0`
- `0x18004e500`
- `0x18004e530`
- `0x18004ea1c`
- `0x1800d3b3c`
- `0x1800d3bf4`
- `0x1800de2d8`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18004e648`
- `KERNEL32!CloseHandle` at `0x18004e666`
- `KERNEL32!CloseHandle` at `0x18004e678`
- `KERNEL32!CloseHandle` at `0x18004e648`
- `KERNEL32!CloseHandle` at `0x18004e666`
- `KERNEL32!CloseHandle` at `0x18004e678`
- `KERNEL32!UnregisterWaitUntilOOBECompleted` at `0x18004e636`
- `KERNEL32!UnregisterWaitUntilOOBECompleted` at `0x18004e636`

## pseudocode

```c
void __fastcall WSD::HealthAdvisor::AdvisorEngine::~AdvisorEngine(WSD::HealthAdvisor::AdvisorEngine *this)
{
  __int64 v2; // rbx
  __int64 i; // rbx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  _BYTE v10[16]; // [rsp+20h] [rbp-228h] BYREF
  char v11; // [rsp+30h] [rbp-218h]
  _BYTE v12[240]; // [rsp+40h] [rbp-208h] BYREF
  _BYTE v13[240]; // [rsp+130h] [rbp-118h] BYREF

  *(_QWORD *)this = &WSD::HealthAdvisor::AdvisorEngine::`vftable';
  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(
    v10,
    (char *)this + 16);
  v2 = *((_QWORD *)this + 12);
  v11 = 1;
  while ( v2 != *((_QWORD *)this + 13) )
  {
    ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(
      (ShieldProvider::CRPCTimeoutEx *)v12,
      0x3E8u,
      L"WSD::HealthAdvisor::AdvisorEngine::~AdvisorEngine");
    CommonUtil::AutoRef<IHardwareShield16>::operator=(v2 + 8);
    ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx((ShieldProvider::CRPCTimeoutEx *)v12);
    v2 += 16;
  }
  for ( i = *((_QWORD *)this + 9); i != *((_QWORD *)this + 10); i += 16 )
  {
    ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(
      (ShieldProvider::CRPCTimeoutEx *)v12,
      0x3E8u,
      L"WSD::HealthAdvisor::AdvisorEngine::~AdvisorEngine");
    CommonUtil::AutoRef<IHardwareNotificationsSink3>::operator=(i + 8, 0);
    ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx((ShieldProvider::CRPCTimeoutEx *)v12);
  }
  ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(
    (ShieldProvider::CRPCTimeoutEx *)v13,
    0x3E8u,
    L"WSD::HealthAdvisor::AdvisorEngine::~AdvisorEngine");
  CommonUtil::AutoRef<ICrossContainerCommunicationManager>::operator=((char *)this + 56);
  CommonUtil::AutoRef<IHardwareShield16>::operator=((char *)this + 64);
  ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx((ShieldProvider::CRPCTimeoutEx *)v13);
  v11 = 0;
  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v10);
  if ( *((_QWORD *)this + 39) )
    UnregisterWaitUntilOOBECompleted();
  v4 = (void *)*((_QWORD *)this + 36);
  if ( v4 )
    CloseHandle(v4);
  std::deque<CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>>::~deque<CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>>((char *)this + 232);
  v5 = (void *)*((_QWORD *)this + 28);
  if ( v5 )
    CloseHandle(v5);
  v6 = (void *)*((_QWORD *)this + 27);
  if ( v6 )
    CloseHandle(v6);
  v7 = *((_QWORD *)this + 19);
  if ( v7 )
  {
    std::_Destroy_range<std::allocator<CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentRuntimeInfo>>>(
      v7,
      *((_QWORD *)this + 20));
    std::_Deallocate<16>(
      *((_QWORD *)this + 19),
      (*((_QWORD *)this + 21) - *((_QWORD *)this + 19)) & 0xFFFFFFFFFFFFFFF8uLL);
    *((_QWORD *)this + 19) = 0;
    *((_QWORD *)this + 20) = 0;
    *((_QWORD *)this + 21) = 0;
  }
  std::_Tree<std::_Tmap_traits<unsigned int,enum _tagHealthAdvisorSeverity,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,enum _tagHealthAdvisorSeverity>>,0>>::~_Tree<std::_Tmap_traits<unsigned int,enum _tagHealthAdvisorSeverity,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,enum _tagHealthAdvisorSeverity>>,0>>((char *)this + 136);
  std::_Tree<std::_Tmap_traits<unsigned int,enum _tagHealthAdvisorSeverity,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,enum _tagHealthAdvisorSeverity>>,0>>::~_Tree<std::_Tmap_traits<unsigned int,enum _tagHealthAdvisorSeverity,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,enum _tagHealthAdvisorSeverity>>,0>>((char *)this + 120);
  v8 = *((_QWORD *)this + 12);
  if ( v8 )
  {
    std::_Destroy_range<std::allocator<WSD::HealthAdvisor::AdvisorEngine::_tagAdvisorSink>>(v8, *((_QWORD *)this + 13));
    std::_Deallocate<16>(
      *((_QWORD *)this + 12),
      (*((_QWORD *)this + 14) - *((_QWORD *)this + 12)) & 0xFFFFFFFFFFFFFFF0uLL);
    *((_QWORD *)this + 12) = 0;
    *((_QWORD *)this + 13) = 0;
    *((_QWORD *)this + 14) = 0;
  }
  v9 = *((_QWORD *)this + 9);
  if ( v9 )
  {
    std::_Destroy_range<std::allocator<WSD::HealthAdvisor::AdvisorEngine::_tagAdvisorSink>>(v9, *((_QWORD *)this + 10));
    std::_Deallocate<16>(
      *((_QWORD *)this + 9),
      (*((_QWORD *)this + 11) - *((_QWORD *)this + 9)) & 0xFFFFFFFFFFFFFFF0uLL);
    *((_QWORD *)this + 9) = 0;
    *((_QWORD *)this + 10) = 0;
    *((_QWORD *)this + 11) = 0;
  }
  CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>((char *)this + 64);
  CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>((char *)this + 56);
  CommonUtil::CMpCriticalSection::~CMpCriticalSection((struct _RTL_CRITICAL_SECTION *)((char *)this + 16));
}

```

## disassembly

```asm
0x18004e530  mov     [rsp+arg_8], rbx
0x18004e535  mov     [rsp+arg_10], rbp
0x18004e53a  push    rsi
0x18004e53b  push    rdi
0x18004e53c  push    r14
0x18004e53e  sub     rsp, 230h
0x18004e545  mov     rax, cs:__security_cookie
0x18004e54c  xor     rax, rsp
0x18004e54f  mov     [rsp+248h+var_28], rax
0x18004e557  lea     rax, ??_7AdvisorEngine@HealthAdvisor@WSD@@6B@; const WSD::HealthAdvisor::AdvisorEngine::`vftable'
0x18004e55e  mov     rdi, rcx
0x18004e561  mov     [rcx], rax
0x18004e564  lea     rdx, [rcx+10h]
0x18004e568  lea     rcx, [rsp+248h+var_228]
0x18004e56d  call    ??0?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@AEBVCMpCriticalSection@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(CommonUtil::CMpCriticalSection const &,CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::ENUM_LOCK_INITIAL_STATE)
0x18004e572  mov     rbx, [rdi+60h]
0x18004e576  lea     rsi, aWsdHealthadvis_1; "WSD::HealthAdvisor::AdvisorEngine::~Adv"...
0x18004e57d  mov     [rsp+248h+var_218], 1
0x18004e582  mov     r14d, 3E8h
0x18004e588  cmp     rbx, [rdi+68h]
0x18004e58c  jz      short loc_18004E5B7
0x18004e58e  mov     r8, rsi; unsigned __int16 *
0x18004e591  lea     rcx, [rsp+248h+var_208]; this
0x18004e596  mov     edx, r14d; DueTime
0x18004e599  call    ??0CRPCTimeoutEx@ShieldProvider@@QEAA@KPEBG@Z; ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(ulong,ushort const *)
0x18004e59e  lea     rcx, [rbx+8]
0x18004e5a2  call    ??4?$AutoRef@UIHardwareShield16@@@CommonUtil@@QEAAAEAV01@PEAUIHardwareShield16@@@Z; CommonUtil::AutoRef<IHardwareShield16>::operator=(IHardwareShield16 *)
0x18004e5a7  lea     rcx, [rsp+248h+var_208]; this
0x18004e5ac  call    ??1CRPCTimeoutEx@ShieldProvider@@QEAA@XZ; ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx(void)
0x18004e5b1  add     rbx, 10h
0x18004e5b5  jmp     short loc_18004E588
0x18004e5b7  mov     rbx, [rdi+48h]
0x18004e5bb  mov     r8, rsi; unsigned __int16 *
0x18004e5be  mov     edx, r14d; DueTime
0x18004e5c1  cmp     rbx, [rdi+50h]
0x18004e5c5  jz      short loc_18004E5EC
0x18004e5c7  lea     rcx, [rsp+248h+var_208]; this
0x18004e5cc  call    ??0CRPCTimeoutEx@ShieldProvider@@QEAA@KPEBG@Z; ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(ulong,ushort const *)
0x18004e5d1  lea     rcx, [rbx+8]
0x18004e5d5  xor     edx, edx
0x18004e5d7  call    ??4?$AutoRef@UIHardwareNotificationsSink3@@@CommonUtil@@QEAAAEAV01@PEAUIHardwareNotificationsSink3@@@Z; CommonUtil::AutoRef<IHardwareNotificationsSink3>::operator=(IHardwareNotificationsSink3 *)
0x18004e5dc  lea     rcx, [rsp+248h+var_208]; this
0x18004e5e1  call    ??1CRPCTimeoutEx@ShieldProvider@@QEAA@XZ; ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx(void)
0x18004e5e6  add     rbx, 10h
0x18004e5ea  jmp     short loc_18004E5BB
0x18004e5ec  lea     rcx, [rsp+248h+var_118]; this
0x18004e5f4  call    ??0CRPCTimeoutEx@ShieldProvider@@QEAA@KPEBG@Z; ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(ulong,ushort const *)
0x18004e5f9  lea     rcx, [rdi+38h]
0x18004e5fd  call    ??4?$AutoRef@UICrossContainerCommunicationManager@@@CommonUtil@@QEAAAEAV01@PEAUICrossContainerCommunicationManager@@@Z; CommonUtil::AutoRef<ICrossContainerCommunicationManager>::operator=(ICrossContainerCommunicationManager *)
0x18004e602  lea     rcx, [rdi+40h]
0x18004e606  call    ??4?$AutoRef@UIHardwareShield16@@@CommonUtil@@QEAAAEAV01@PEAUIHardwareShield16@@@Z; CommonUtil::AutoRef<IHardwareShield16>::operator=(IHardwareShield16 *)
0x18004e60b  lea     rcx, [rsp+248h+var_118]; this
0x18004e613  call    ??1CRPCTimeoutEx@ShieldProvider@@QEAA@XZ; ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx(void)
0x18004e618  xor     r14d, r14d
0x18004e61b  lea     rcx, [rsp+248h+var_228]
0x18004e620  mov     [rsp+248h+var_218], r14b
0x18004e625  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x18004e62a  mov     rcx, [rdi+138h]
0x18004e631  test    rcx, rcx
0x18004e634  jz      short loc_18004E63C
0x18004e636  call    cs:__imp_UnregisterWaitUntilOOBECompleted
0x18004e63c  mov     rcx, [rdi+120h]; hObject
0x18004e643  test    rcx, rcx
0x18004e646  jz      short loc_18004E64E
0x18004e648  call    cs:__imp_CloseHandle
0x18004e64e  lea     rcx, [rdi+0E8h]
0x18004e655  call    ??1?$deque@V?$AutoRef@VAssessmentQueueItem@HealthAdvisor@WSD@@@CommonUtil@@V?$allocator@V?$AutoRef@VAssessmentQueueItem@HealthAdvisor@WSD@@@CommonUtil@@@std@@@std@@QEAA@XZ; std::deque<CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>>::~deque<CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>>(void)
0x18004e65a  mov     rcx, [rdi+0E0h]; hObject
0x18004e661  test    rcx, rcx
0x18004e664  jz      short loc_18004E66C
0x18004e666  call    cs:__imp_CloseHandle
0x18004e66c  mov     rcx, [rdi+0D8h]; hObject
0x18004e673  test    rcx, rcx
0x18004e676  jz      short loc_18004E67E
0x18004e678  call    cs:__imp_CloseHandle
0x18004e67e  mov     rcx, [rdi+98h]
0x18004e685  test    rcx, rcx
0x18004e688  jz      short loc_18004E6C5
0x18004e68a  mov     rdx, [rdi+0A0h]
0x18004e691  call    ??$_Destroy_range@V?$allocator@V?$AutoRef@VAssessmentRuntimeInfo@HealthAdvisor@WSD@@@CommonUtil@@@std@@@std@@YAXPEAV?$AutoRef@VAssessmentRuntimeInfo@HealthAdvisor@WSD@@@CommonUtil@@QEAV12@AEAV?$allocator@V?$AutoRef@VAssessmentRuntimeInfo@HealthAdvisor@WSD@@@CommonUtil@@@0@@Z; std::_Destroy_range<std::allocator<CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentRuntimeInfo>>>(CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentRuntimeInfo> *,CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentRuntimeInfo> * const,std::allocator<CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentRuntimeInfo>> &)
0x18004e696  mov     rcx, [rdi+98h]
0x18004e69d  mov     rdx, [rdi+0A8h]
0x18004e6a4  sub     rdx, rcx
0x18004e6a7  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18004e6ab  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18004e6b0  mov     [rdi+98h], r14
0x18004e6b7  mov     [rdi+0A0h], r14
0x18004e6be  mov     [rdi+0A8h], r14
0x18004e6c5  lea     rcx, [rdi+88h]
0x18004e6cc  call    ??1?$_Tree@V?$_Tmap_traits@IW4_tagHealthAdvisorSeverity@@U?$less@I@std@@V?$allocator@U?$pair@$$CBIW4_tagHealthAdvisorSeverity@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<uint,_tagHealthAdvisorSeverity,std::less<uint>,std::allocator<std::pair<uint const,_tagHealthAdvisorSeverity>>,0>>::~_Tree<std::_Tmap_traits<uint,_tagHealthAdvisorSeverity,std::less<uint>,std::allocator<std::pair<uint const,_tagHealthAdvisorSeverity>>,0>>(void)
0x18004e6d1  lea     rcx, [rdi+78h]
0x18004e6d5  call    ??1?$_Tree@V?$_Tmap_traits@IW4_tagHealthAdvisorSeverity@@U?$less@I@std@@V?$allocator@U?$pair@$$CBIW4_tagHealthAdvisorSeverity@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<uint,_tagHealthAdvisorSeverity,std::less<uint>,std::allocator<std::pair<uint const,_tagHealthAdvisorSeverity>>,0>>::~_Tree<std::_Tmap_traits<uint,_tagHealthAdvisorSeverity,std::less<uint>,std::allocator<std::pair<uint const,_tagHealthAdvisorSeverity>>,0>>(void)
0x18004e6da  mov     rcx, [rdi+60h]
0x18004e6de  test    rcx, rcx
0x18004e6e1  jz      short loc_18004E70C
0x18004e6e3  mov     rdx, [rdi+68h]
0x18004e6e7  call    ??$_Destroy_range@V?$allocator@U_tagAdvisorSink@AdvisorEngine@HealthAdvisor@WSD@@@std@@@std@@YAXPEAU_tagAdvisorSink@AdvisorEngine@HealthAdvisor@WSD@@QEAU1234@AEAV?$allocator@U_tagAdvisorSink@AdvisorEngine@HealthAdvisor@WSD@@@0@@Z; std::_Destroy_range<std::allocator<WSD::HealthAdvisor::AdvisorEngine::_tagAdvisorSink>>(WSD::HealthAdvisor::AdvisorEngine::_tagAdvisorSink *,WSD::HealthAdvisor::AdvisorEngine::_tagAdvisorSink * const,std::allocator<WSD::HealthAdvisor::AdvisorEngine::_tagAdvisorSink> &)
0x18004e6ec  mov     rcx, [rdi+60h]
0x18004e6f0  mov     rdx, [rdi+70h]
0x18004e6f4  sub     rdx, rcx
0x18004e6f7  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18004e6fb  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18004e700  mov     [rdi+60h], r14
0x18004e704  mov     [rdi+68h], r14
0x18004e708  mov     [rdi+70h], r14
0x18004e70c  mov     rcx, [rdi+48h]
0x18004e710  test    rcx, rcx
0x18004e713  jz      short loc_18004E73E
0x18004e715  mov     rdx, [rdi+50h]
0x18004e719  call    ??$_Destroy_range@V?$allocator@U_tagAdvisorSink@AdvisorEngine@HealthAdvisor@WSD@@@std@@@std@@YAXPEAU_tagAdvisorSink@AdvisorEngine@HealthAdvisor@WSD@@QEAU1234@AEAV?$allocator@U_tagAdvisorSink@AdvisorEngine@HealthAdvisor@WSD@@@0@@Z; std::_Destroy_range<std::allocator<WSD::HealthAdvisor::AdvisorEngine::_tagAdvisorSink>>(WSD::HealthAdvisor::AdvisorEngine::_tagAdvisorSink *,WSD::HealthAdvisor::AdvisorEngine::_tagAdvisorSink * const,std::allocator<WSD::HealthAdvisor::AdvisorEngine::_tagAdvisorSink> &)
0x18004e71e  mov     rcx, [rdi+48h]
0x18004e722  mov     rdx, [rdi+58h]
0x18004e726  sub     rdx, rcx
0x18004e729  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18004e72d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18004e732  mov     [rdi+48h], r14
0x18004e736  mov     [rdi+50h], r14
0x18004e73a  mov     [rdi+58h], r14
0x18004e73e  lea     rcx, [rdi+40h]
0x18004e742  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x18004e747  lea     rcx, [rdi+38h]
0x18004e74b  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x18004e750  lea     rcx, [rdi+10h]; this
0x18004e754  call    ??1CMpCriticalSection@CommonUtil@@QEAA@XZ; CommonUtil::CMpCriticalSection::~CMpCriticalSection(void)
0x18004e759  mov     rcx, [rsp+248h+var_28]
0x18004e761  xor     rcx, rsp; StackCookie
0x18004e764  call    __security_check_cookie
0x18004e769  lea     r11, [rsp+248h+var_18]
0x18004e771  mov     rbx, [r11+28h]
0x18004e775  mov     rbp, [r11+30h]
0x18004e779  mov     rsp, r11
0x18004e77c  pop     r14
0x18004e77e  pop     rdi
0x18004e77f  pop     rsi
0x18004e780  retn
```
