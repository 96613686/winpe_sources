# ShieldProvider::CPeriodicTaskManager::RegisterCommunicationManagerIfOnWcosGuest(void)

- ea: `0x180013260`
- end: `0x1800134f2`
- name: `?RegisterCommunicationManagerIfOnWcosGuest@CPeriodicTaskManager@ShieldProvider@@QEAAJXZ`
- size: `658`
- prototype: `__int64 __fastcall(ShieldProvider::CPeriodicTaskManager *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180015430`

## callees

- `0x18000ccb0`
- `0x18000ccd4`
- `0x18000d7fc`
- `0x180011730`
- `0x180013260`
- `0x180015850`
- `0x1800c2290`
- `0x1800ceb24`
- `0x1800ceb60`
- `0x1800e7010`

## import_xrefs

- `ole32!CoSetProxyBlanket` at `0x18001337b`
- `ole32!CoSetProxyBlanket` at `0x18001337b`
- `ole32!CoCreateInstance` at `0x180013309`
- `ole32!CoCreateInstance` at `0x180013309`

## pseudocode

```c
__int64 __fastcall ShieldProvider::CPeriodicTaskManager::RegisterCommunicationManagerIfOnWcosGuest(
        ShieldProvider::CPeriodicTaskManager *this)
{
  HRESULT Instance; // eax
  unsigned int v3; // ebx
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  ShieldProvider *v6; // rcx
  const struct _GUID *v7; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  IUnknown *pProxy; // [rsp+68h] [rbp+28h] BYREF
  void *v12; // [rsp+70h] [rbp+30h] BYREF
  __int64 v13; // [rsp+78h] [rbp+38h] BYREF

  if ( ShieldProvider::IsOSWcos(this) )
  {
    pProxy = 0;
    v12 = 0;
    v13 = 0;
    Instance = CommonUtil::NewRefInstance<ShieldProvider::ComClientImpersonator>(&v13);
    v3 = Instance;
    if ( Instance < 0 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_28;
      v5 = 16;
LABEL_27:
      WPP_SF_d(v4[2], v5, WPP_c15b3361942b3cf72eefef62f859076e_Traceguids, (unsigned int)Instance);
LABEL_28:
      CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(&v13);
      CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&v12);
      CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&pProxy);
      return v3;
    }
    if ( pProxy )
    {
      ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
      pProxy = 0;
    }
    Instance = CoCreateInstance(
                 &CLSID_CrossContainerCommunicationManagerShield,
                 0,
                 0x100004u,
                 &GUID_c39622c7_dda7_4385_bd69_b6cc374c2e2f,
                 (LPVOID *)&pProxy);
    v3 = Instance;
    if ( Instance < 0 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_28;
      v5 = 17;
      goto LABEL_27;
    }
    if ( ShieldProvider::IsOSWcosGuest(v6) )
    {
      Instance = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, 0, 0, 3u, 0, 0x20u);
      v3 = Instance;
      if ( Instance < 0 )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_28;
        v5 = 18;
        goto LABEL_27;
      }
      ShieldProvider::CPeriodicTaskManager::UnRegisterCommunicationManagerIfOnWcosGuest(this);
      v7 = (const struct _GUID *)v12;
      if ( v12 )
      {
        (*(void (__fastcall **)(void *))(*(_QWORD *)v12 + 16LL))(v12);
        v12 = 0;
      }
      Instance = CrossContainerCommunicationManagerSink_CreateInstance(v7, &v12);
      v3 = Instance;
      if ( Instance < 0 )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_28;
        v5 = 19;
        goto LABEL_27;
      }
      Instance = ((__int64 (__fastcall *)(IUnknown *, void *, char *, char *))pProxy->lpVtbl[1].QueryInterface)(
                   pProxy,
                   v12,
                   (char *)this + 120,
                   (char *)this + 120);
      v3 = Instance;
      if ( Instance < 0 )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_28;
        v5 = 20;
        goto LABEL_27;
      }
      v9 = *((_QWORD *)this + 18);
      if ( v9 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      *((_QWORD *)this + 18) = v12;
      v12 = 0;
    }
    v10 = *((_QWORD *)this + 17);
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    *((_QWORD *)this + 17) = pProxy;
    pProxy = 0;
    CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(&v13);
    CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&v12);
    CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&pProxy);
  }
  return 0;
}

```

## disassembly

```asm
0x180013260  push    rbp
0x180013262  push    rbx
0x180013263  push    rdi
0x180013264  mov     rbp, rsp
0x180013267  sub     rsp, 40h
0x18001326b  mov     rdi, rcx
0x18001326e  call    ?IsOSWcos@ShieldProvider@@YA_NXZ; ShieldProvider::IsOSWcos(void)
0x180013273  test    al, al
0x180013275  jz      loc_1800134E8
0x18001327b  lea     rcx, [rbp+arg_18]
0x18001327f  mov     [rbp+pProxy], 0
0x180013287  mov     [rbp+arg_10], 0
0x18001328f  mov     [rbp+arg_18], 0
0x180013297  call    ??$NewRefInstance@VComClientImpersonator@ShieldProvider@@@CommonUtil@@YAJPEAPEAVComClientImpersonator@ShieldProvider@@@Z; CommonUtil::NewRefInstance<ShieldProvider::ComClientImpersonator>(ShieldProvider::ComClientImpersonator * *)
0x18001329c  mov     ebx, eax
0x18001329e  test    eax, eax
0x1800132a0  jns     short loc_1800132CD
0x1800132a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800132a9  lea     rdx, WPP_GLOBAL_Control
0x1800132b0  cmp     rcx, rdx
0x1800132b3  jz      loc_180013458
0x1800132b9  test    byte ptr [rcx+1Ch], 1
0x1800132bd  jz      loc_180013458
0x1800132c3  mov     edx, 10h
0x1800132c8  jmp     loc_180013445
0x1800132cd  mov     rcx, [rbp+pProxy]
0x1800132d1  test    rcx, rcx
0x1800132d4  jz      short loc_1800132EA
0x1800132d6  mov     rax, [rcx]
0x1800132d9  mov     rax, [rax+10h]
0x1800132dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800132e2  mov     [rbp+pProxy], 0
0x1800132ea  lea     rax, [rbp+pProxy]
0x1800132ee  xor     edx, edx; pUnkOuter
0x1800132f0  lea     r9, _GUID_c39622c7_dda7_4385_bd69_b6cc374c2e2f; riid
0x1800132f7  mov     [rsp+40h+ppv], rax; ppv
0x1800132fc  mov     r8d, 100004h; dwClsContext
0x180013302  lea     rcx, CLSID_CrossContainerCommunicationManagerShield; rclsid
0x180013309  call    cs:__imp_CoCreateInstance
0x18001330f  mov     ebx, eax
0x180013311  test    eax, eax
0x180013313  jns     short loc_180013340
0x180013315  mov     rcx, cs:WPP_GLOBAL_Control
0x18001331c  lea     rdx, WPP_GLOBAL_Control
0x180013323  cmp     rcx, rdx
0x180013326  jz      loc_180013458
0x18001332c  test    byte ptr [rcx+1Ch], 1
0x180013330  jz      loc_180013458
0x180013336  mov     edx, 11h
0x18001333b  jmp     loc_180013445
0x180013340  call    ?IsOSWcosGuest@ShieldProvider@@YA_NXZ; ShieldProvider::IsOSWcosGuest(void)
0x180013345  test    al, al
0x180013347  jz      loc_1800134A2
0x18001334d  mov     rcx, [rbp+pProxy]; pProxy
0x180013351  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x180013354  mov     [rsp+40h+dwCapabilities], 20h ; ' '; dwCapabilities
0x18001335c  mov     r8d, edx; dwAuthzSvc
0x18001335f  mov     [rsp+40h+pAuthInfo], 0; pAuthInfo
0x180013368  xor     r9d, r9d; pServerPrincName
0x18001336b  mov     [rsp+40h+dwImpLevel], 3; dwImpLevel
0x180013373  mov     dword ptr [rsp+40h+ppv], 0; dwAuthnLevel
0x18001337b  call    cs:__imp_CoSetProxyBlanket
0x180013381  mov     ebx, eax
0x180013383  test    eax, eax
0x180013385  jns     short loc_1800133B2
0x180013387  mov     rcx, cs:WPP_GLOBAL_Control
0x18001338e  lea     rdx, WPP_GLOBAL_Control
0x180013395  cmp     rcx, rdx
0x180013398  jz      loc_180013458
0x18001339e  test    byte ptr [rcx+1Ch], 1
0x1800133a2  jz      loc_180013458
0x1800133a8  mov     edx, 12h
0x1800133ad  jmp     loc_180013445
0x1800133b2  mov     rcx, rdi; this
0x1800133b5  call    ?UnRegisterCommunicationManagerIfOnWcosGuest@CPeriodicTaskManager@ShieldProvider@@QEAAXXZ; ShieldProvider::CPeriodicTaskManager::UnRegisterCommunicationManagerIfOnWcosGuest(void)
0x1800133ba  mov     rcx, [rbp+arg_10]
0x1800133be  test    rcx, rcx
0x1800133c1  jz      short loc_1800133D7
0x1800133c3  mov     rax, [rcx]
0x1800133c6  mov     rax, [rax+10h]
0x1800133ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800133cf  mov     [rbp+arg_10], 0
0x1800133d7  lea     rdx, [rbp+arg_10]; void **
0x1800133db  call    ?CrossContainerCommunicationManagerSink_CreateInstance@@YAJAEBU_GUID@@PEAPEAX@Z; CrossContainerCommunicationManagerSink_CreateInstance(_GUID const &,void * *)
0x1800133e0  mov     ebx, eax
0x1800133e2  test    eax, eax
0x1800133e4  jns     short loc_180013406
0x1800133e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800133ed  lea     rdx, WPP_GLOBAL_Control
0x1800133f4  cmp     rcx, rdx
0x1800133f7  jz      short loc_180013458
0x1800133f9  test    byte ptr [rcx+1Ch], 1
0x1800133fd  jz      short loc_180013458
0x1800133ff  mov     edx, 13h
0x180013404  jmp     short loc_180013445
0x180013406  mov     rcx, [rbp+pProxy]
0x18001340a  lea     r8, [rdi+78h]
0x18001340e  mov     rdx, [rbp+arg_10]
0x180013412  mov     r9, r8
0x180013415  mov     rax, [rcx]
0x180013418  mov     rax, [rax+18h]
0x18001341c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013421  mov     ebx, eax
0x180013423  test    eax, eax
0x180013425  jns     short loc_180013477
0x180013427  mov     rcx, cs:WPP_GLOBAL_Control
0x18001342e  lea     rdx, WPP_GLOBAL_Control
0x180013435  cmp     rcx, rdx
0x180013438  jz      short loc_180013458
0x18001343a  test    byte ptr [rcx+1Ch], 1
0x18001343e  jz      short loc_180013458
0x180013440  mov     edx, 14h
0x180013445  mov     rcx, [rcx+10h]
0x180013449  lea     r8, WPP_c15b3361942b3cf72eefef62f859076e_Traceguids
0x180013450  mov     r9d, eax
0x180013453  call    WPP_SF_d
0x180013458  lea     rcx, [rbp+arg_18]
0x18001345c  call    ??1?$AutoRef@VAssessmentQueueItem@HealthAdvisor@WSD@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(void)
0x180013461  lea     rcx, [rbp+arg_10]
0x180013465  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x18001346a  lea     rcx, [rbp+pProxy]
0x18001346e  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x180013473  mov     eax, ebx
0x180013475  jmp     short loc_1800134EA
0x180013477  mov     rcx, [rdi+90h]
0x18001347e  test    rcx, rcx
0x180013481  jz      short loc_18001348F
0x180013483  mov     rax, [rcx]
0x180013486  mov     rax, [rax+10h]
0x18001348a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001348f  mov     rax, [rbp+arg_10]
0x180013493  mov     [rdi+90h], rax
0x18001349a  mov     [rbp+arg_10], 0
0x1800134a2  mov     rcx, [rdi+88h]
0x1800134a9  test    rcx, rcx
0x1800134ac  jz      short loc_1800134BA
0x1800134ae  mov     rax, [rcx]
0x1800134b1  mov     rax, [rax+10h]
0x1800134b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800134ba  mov     rax, [rbp+pProxy]
0x1800134be  lea     rcx, [rbp+arg_18]
0x1800134c2  mov     [rdi+88h], rax
0x1800134c9  mov     [rbp+pProxy], 0
0x1800134d1  call    ??1?$AutoRef@VAssessmentQueueItem@HealthAdvisor@WSD@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(void)
0x1800134d6  lea     rcx, [rbp+arg_10]
0x1800134da  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x1800134df  lea     rcx, [rbp+pProxy]
0x1800134e3  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x1800134e8  xor     eax, eax
0x1800134ea  add     rsp, 40h
0x1800134ee  pop     rdi
0x1800134ef  pop     rbx
0x1800134f0  pop     rbp
0x1800134f1  retn
```
