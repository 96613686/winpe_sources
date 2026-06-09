# ShieldProvider::DashboardEx::GetThreatPillarStatusEx(PillarStatusEx * *)

- ea: `0x1800696c4`
- end: `0x180069889`
- name: `?GetThreatPillarStatusEx@DashboardEx@ShieldProvider@@AEAAJPEAPEAUPillarStatusEx@@@Z`
- size: `453`
- prototype: `__int64 __fastcall(ShieldProvider::DashboardEx *__hidden this, struct PillarStatusEx **)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x180069000`

## callees

- `0x18000ccb0`
- `0x18000d7fc`
- `0x18000f02c`
- `0x18000f094`
- `0x18001b7d4`
- `0x180037d70`
- `0x180067a7c`
- `0x180068508`
- `0x1800696c4`
- `0x1800e7010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180069802`
- `ole32!CoTaskMemFree` at `0x180069819`
- `ole32!CoTaskMemFree` at `0x18006982a`
- `ole32!CoTaskMemFree` at `0x180069802`
- `ole32!CoTaskMemFree` at `0x180069819`
- `ole32!CoTaskMemFree` at `0x18006982a`

## pseudocode

```c
__int64 __fastcall ShieldProvider::DashboardEx::GetThreatPillarStatusEx(
        ShieldProvider::DashboardEx *this,
        struct PillarStatusEx **a2)
{
  int v5; // r14d
  _QWORD *v6; // r12
  __int64 v7; // rbx
  int DefenderPillarStatus; // ebx
  struct PillarStatusEx *v9; // rcx
  _QWORD *v10; // rdi
  void *v11; // rcx
  void *v12; // rcx
  _QWORD *v13; // [rsp+20h] [rbp-30h] BYREF
  __int64 v14; // [rsp+28h] [rbp-28h] BYREF
  _BYTE v15[16]; // [rsp+30h] [rbp-20h] BYREF
  char v16; // [rsp+40h] [rbp-10h]
  int v17; // [rsp+90h] [rbp+40h] BYREF
  __int64 v18; // [rsp+98h] [rbp+48h] BYREF

  if ( (unsigned int)ShieldProvider::IsShieldProviderSvcStopPending(this) )
    return 2147942421LL;
  v5 = 0;
  v14 = 0;
  v17 = 0;
  v18 = 0;
  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(
    v15,
    (char *)this + 112);
  v6 = (_QWORD *)((char *)this + 168);
  CommonUtil::AutoRef<IForceFieldSink>::operator=(&v18, (char *)this + 168);
  v7 = v18;
  if ( v18 )
    v5 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v18 + 56LL))(v18, &v17);
  v16 = 0;
  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v15);
  if ( v7 && v5 >= 0 && v17 )
  {
    CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(
      v15,
      (char *)this + 112);
    if ( *v6 )
      DefenderPillarStatus = (*(__int64 (__fastcall **)(_QWORD, struct PillarStatusEx **))(*(_QWORD *)*v6 + 72LL))(
                               *v6,
                               a2);
    else
      DefenderPillarStatus = -2147024875;
    v16 = 0;
    CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v15);
  }
  else
  {
    DefenderPillarStatus = ShieldProvider::DashboardEx::GetDefenderPillarStatus(this, (struct PillarStatus *)&v14);
    if ( DefenderPillarStatus < 0 )
      goto LABEL_23;
    v13 = 0;
    DefenderPillarStatus = CommonUtil::UtilCoTaskMemAllocObject<PillarStatusEx>(&v13);
    if ( DefenderPillarStatus < 0 )
    {
      v10 = v13;
    }
    else
    {
      v9 = (struct PillarStatusEx *)v13;
      v10 = 0;
      *v13 = v14;
      *((_QWORD *)v9 + 1) = 0;
      *((_QWORD *)v9 + 2) = 0;
      *a2 = v9;
    }
    if ( v10 )
    {
      v11 = (void *)v10[1];
      if ( v11 )
      {
        CoTaskMemFree(v11);
        v10[1] = 0;
      }
      v12 = (void *)v10[2];
      if ( v12 )
      {
        CoTaskMemFree(v12);
        v10[2] = 0;
      }
      CoTaskMemFree(v10);
    }
  }
  if ( DefenderPillarStatus < 0 )
  {
LABEL_23:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        60,
        WPP_9a072a55361f3902b023016d7eb82632_Traceguids,
        (unsigned int)DefenderPillarStatus);
  }
  CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&v18);
  return (unsigned int)DefenderPillarStatus;
}

```

## disassembly

```asm
0x1800696c4  mov     [rsp-28h+arg_0], rbx
0x1800696c9  mov     [rsp-28h+arg_8], rsi
0x1800696ce  push    rbp
0x1800696cf  push    rdi
0x1800696d0  push    r12
0x1800696d2  push    r14
0x1800696d4  push    r15
0x1800696d6  mov     rbp, rsp
0x1800696d9  sub     rsp, 50h
0x1800696dd  mov     rsi, rdx
0x1800696e0  mov     rdi, rcx
0x1800696e3  call    ?IsShieldProviderSvcStopPending@ShieldProvider@@YAHXZ; ShieldProvider::IsShieldProviderSvcStopPending(void)
0x1800696e8  test    eax, eax
0x1800696ea  jz      short loc_1800696F6
0x1800696ec  mov     eax, 80070015h
0x1800696f1  jmp     loc_180069870
0x1800696f6  xor     r14d, r14d
0x1800696f9  mov     [rbp+var_28], 0
0x180069701  lea     rdx, [rdi+70h]
0x180069705  mov     [rbp+arg_10], r14d
0x180069709  lea     rcx, [rbp+var_20]
0x18006970d  mov     [rbp+arg_18], r14
0x180069711  call    ??0?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@AEBVCMpCriticalSection@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(CommonUtil::CMpCriticalSection const &,CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::ENUM_LOCK_INITIAL_STATE)
0x180069716  lea     r12, [rdi+0A8h]
0x18006971d  mov     rdx, r12
0x180069720  lea     rcx, [rbp+arg_18]
0x180069724  call    ??4?$AutoRef@UIForceFieldSink@@@CommonUtil@@QEAAAEAV01@AEBV01@@Z; CommonUtil::AutoRef<IForceFieldSink>::operator=(CommonUtil::AutoRef<IForceFieldSink> const &)
0x180069729  mov     rbx, [rbp+arg_18]
0x18006972d  test    rbx, rbx
0x180069730  jz      short loc_180069748
0x180069732  mov     rax, [rbx]
0x180069735  lea     rdx, [rbp+arg_10]
0x180069739  mov     rcx, rbx
0x18006973c  mov     rax, [rax+38h]
0x180069740  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069745  mov     r14d, eax
0x180069748  lea     rcx, [rbp+var_20]
0x18006974c  mov     [rbp+var_10], 0
0x180069750  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x180069755  test    rbx, rbx
0x180069758  jz      short loc_1800697A5
0x18006975a  test    r14d, r14d
0x18006975d  js      short loc_1800697A5
0x18006975f  cmp     [rbp+arg_10], 0
0x180069763  jz      short loc_1800697A5
0x180069765  lea     rdx, [rdi+70h]
0x180069769  lea     rcx, [rbp+var_20]
0x18006976d  call    ??0?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@AEBVCMpCriticalSection@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(CommonUtil::CMpCriticalSection const &,CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::ENUM_LOCK_INITIAL_STATE)
0x180069772  mov     rcx, [r12]
0x180069776  test    rcx, rcx
0x180069779  jz      short loc_18006978E
0x18006977b  mov     rax, [rcx]
0x18006977e  mov     rdx, rsi
0x180069781  mov     rax, [rax+48h]
0x180069785  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006978a  mov     ebx, eax
0x18006978c  jmp     short loc_180069793
0x18006978e  mov     ebx, 80070015h
0x180069793  lea     rcx, [rbp+var_20]
0x180069797  mov     [rbp+var_10], 0
0x18006979b  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x1800697a0  jmp     loc_180069830
0x1800697a5  lea     rdx, [rbp+var_28]; struct PillarStatus *
0x1800697a9  mov     rcx, rdi; this
0x1800697ac  call    ?GetDefenderPillarStatus@DashboardEx@ShieldProvider@@AEAAJPEAUPillarStatus@@@Z; ShieldProvider::DashboardEx::GetDefenderPillarStatus(PillarStatus *)
0x1800697b1  mov     ebx, eax
0x1800697b3  test    eax, eax
0x1800697b5  js      short loc_180069834
0x1800697b7  lea     rcx, [rbp+var_30]
0x1800697bb  mov     [rbp+var_30], 0
0x1800697c3  call    ??$UtilCoTaskMemAllocObject@UPillarStatusEx@@@CommonUtil@@YAJPEAPEAUPillarStatusEx@@_K_N@Z; CommonUtil::UtilCoTaskMemAllocObject<PillarStatusEx>(PillarStatusEx * *,unsigned __int64,bool)
0x1800697c8  mov     ebx, eax
0x1800697ca  test    eax, eax
0x1800697cc  js      short loc_1800697F0
0x1800697ce  mov     rcx, [rbp+var_30]
0x1800697d2  xor     edi, edi
0x1800697d4  mov     rax, [rbp+var_28]
0x1800697d8  mov     [rcx], rax
0x1800697db  mov     qword ptr [rcx+8], 0
0x1800697e3  mov     qword ptr [rcx+10h], 0
0x1800697eb  mov     [rsi], rcx
0x1800697ee  jmp     short loc_1800697F4
0x1800697f0  mov     rdi, [rbp+var_30]
0x1800697f4  test    rdi, rdi
0x1800697f7  jz      short loc_180069830
0x1800697f9  mov     rcx, [rdi+8]; pv
0x1800697fd  test    rcx, rcx
0x180069800  jz      short loc_180069810
0x180069802  call    cs:__imp_CoTaskMemFree
0x180069808  mov     qword ptr [rdi+8], 0
0x180069810  mov     rcx, [rdi+10h]; pv
0x180069814  test    rcx, rcx
0x180069817  jz      short loc_180069827
0x180069819  call    cs:__imp_CoTaskMemFree
0x18006981f  mov     qword ptr [rdi+10h], 0
0x180069827  mov     rcx, rdi; pv
0x18006982a  call    cs:__imp_CoTaskMemFree
0x180069830  test    ebx, ebx
0x180069832  jns     short loc_180069865
0x180069834  mov     rcx, cs:WPP_GLOBAL_Control
0x18006983b  lea     rax, WPP_GLOBAL_Control
0x180069842  cmp     rcx, rax
0x180069845  jz      short loc_180069865
0x180069847  test    byte ptr [rcx+1Ch], 1
0x18006984b  jz      short loc_180069865
0x18006984d  mov     rcx, [rcx+10h]
0x180069851  lea     r8, WPP_9a072a55361f3902b023016d7eb82632_Traceguids
0x180069858  mov     edx, 3Ch ; '<'
0x18006985d  mov     r9d, ebx
0x180069860  call    WPP_SF_d
0x180069865  lea     rcx, [rbp+arg_18]
0x180069869  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x18006986e  mov     eax, ebx
0x180069870  lea     r11, [rsp+50h+var_s0]
0x180069875  mov     rbx, [r11+30h]
0x180069879  mov     rsi, [r11+38h]
0x18006987d  mov     rsp, r11
0x180069880  pop     r15
0x180069882  pop     r14
0x180069884  pop     r12
0x180069886  pop     rdi
0x180069887  pop     rbp
0x180069888  retn
```
