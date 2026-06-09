# ShieldProvider::DashboardEx::GetThreatPillarStatus(PillarStatus *)

- ea: `0x180069498`
- end: `0x1800696bd`
- name: `?GetThreatPillarStatus@DashboardEx@ShieldProvider@@AEAAJPEAUPillarStatus@@@Z`
- size: `549`
- prototype: `__int64 __fastcall(ShieldProvider::DashboardEx *__hidden this, struct PillarStatus *)`
- caller_count: `2`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x180068df0`
- `0x180069890`

## callees

- `0x18000ccb0`
- `0x18000d7fc`
- `0x18000f02c`
- `0x18000f094`
- `0x18001b7d4`
- `0x180067a7c`
- `0x180068508`
- `0x180069498`
- `0x180069c94`
- `0x1800e7010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180069636`
- `ole32!CoTaskMemFree` at `0x18006964d`
- `ole32!CoTaskMemFree` at `0x18006965e`
- `ole32!CoTaskMemFree` at `0x180069636`
- `ole32!CoTaskMemFree` at `0x18006964d`
- `ole32!CoTaskMemFree` at `0x18006965e`

## pseudocode

```c
__int64 __fastcall ShieldProvider::DashboardEx::GetThreatPillarStatus(
        ShieldProvider::DashboardEx *this,
        struct PillarStatus *a2)
{
  _QWORD *v5; // r15
  int v6; // esi
  char i; // al
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  unsigned int DefenderPillarStatus; // ebx
  char j; // al
  __int64 v12; // rcx
  int v13; // eax
  int *v14; // rbx
  int v15; // eax
  void *v16; // rcx
  void *v17; // rcx
  LPVOID pv; // [rsp+20h] [rbp-20h] BYREF
  _BYTE v19[16]; // [rsp+28h] [rbp-18h] BYREF
  char v20; // [rsp+38h] [rbp-8h]
  int v21; // [rsp+80h] [rbp+40h] BYREF
  __int64 v22; // [rsp+88h] [rbp+48h] BYREF

  if ( (unsigned int)ShieldProvider::IsShieldProviderSvcStopPending(this) )
    return 2147942421LL;
  v21 = 0;
  v22 = 0;
  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(
    v19,
    (char *)this + 112);
  v5 = (_QWORD *)((char *)this + 168);
  CommonUtil::AutoRef<IForceFieldSink>::operator=(&v22, (char *)this + 168);
  v20 = 0;
  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v19);
  if ( v22 )
  {
    v6 = 0;
    CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(
      v19,
      (char *)this + 112);
    for ( i = 1; ; i = 0 )
    {
      v20 = i;
      if ( !i )
        break;
      if ( !*v5 )
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v9 = 57;
LABEL_11:
          WPP_SF_d(v8[2], v9, WPP_9a072a55361f3902b023016d7eb82632_Traceguids, 2147942421LL);
        }
LABEL_12:
        CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v19);
        DefenderPillarStatus = -2147024875;
        goto LABEL_36;
      }
      v6 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*v5 + 56LL))(*v5, &v21);
    }
    CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v19);
    if ( v6 >= 0 )
    {
      if ( v21 )
      {
        CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(
          v19,
          (char *)this + 112);
        for ( j = 1; ; j = 0 )
        {
          v20 = j;
          if ( !j )
          {
            CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v19);
            goto LABEL_35;
          }
          v12 = *v5;
          if ( !*v5 )
            break;
          pv = 0;
          v13 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v12 + 72LL))(v12, &pv);
          v14 = (int *)pv;
          v6 = v13;
          if ( v13 < 0 )
          {
            *((_DWORD *)a2 + 1) = 1;
            v15 = 2;
          }
          else
          {
            *((_DWORD *)a2 + 1) = *((_DWORD *)pv + 1);
            v15 = *v14;
          }
          *(_DWORD *)a2 = v15;
          if ( v14 )
          {
            v16 = (void *)*((_QWORD *)v14 + 1);
            if ( v16 )
            {
              CoTaskMemFree(v16);
              *((_QWORD *)v14 + 1) = 0;
            }
            v17 = (void *)*((_QWORD *)v14 + 2);
            if ( v17 )
            {
              CoTaskMemFree(v17);
              *((_QWORD *)v14 + 2) = 0;
            }
            CoTaskMemFree(v14);
          }
        }
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v9 = 58;
          goto LABEL_11;
        }
        goto LABEL_12;
      }
    }
    else if ( !ShieldProvider::DashboardEx::IsDefenderPrimaryAV(this) )
    {
      *((_DWORD *)a2 + 1) = 1;
      *(_DWORD *)a2 = 143;
LABEL_35:
      DefenderPillarStatus = v6;
      goto LABEL_36;
    }
  }
  DefenderPillarStatus = ShieldProvider::DashboardEx::GetDefenderPillarStatus(this, a2);
LABEL_36:
  CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&v22);
  return DefenderPillarStatus;
}

```

## disassembly

```asm
0x180069498  mov     [rsp-28h+arg_0], rbx
0x18006949d  push    rbp
0x18006949e  push    rsi
0x18006949f  push    rdi
0x1800694a0  push    r14
0x1800694a2  push    r15
0x1800694a4  mov     rbp, rsp
0x1800694a7  sub     rsp, 40h
0x1800694ab  mov     rdi, rdx
0x1800694ae  mov     rbx, rcx
0x1800694b1  call    ?IsShieldProviderSvcStopPending@ShieldProvider@@YAHXZ; ShieldProvider::IsShieldProviderSvcStopPending(void)
0x1800694b6  test    eax, eax
0x1800694b8  jz      short loc_1800694C4
0x1800694ba  mov     eax, 80070015h
0x1800694bf  jmp     loc_1800696AC
0x1800694c4  lea     r14, [rbx+70h]
0x1800694c8  mov     [rbp+arg_10], 0
0x1800694cf  mov     rdx, r14
0x1800694d2  mov     [rbp+arg_18], 0
0x1800694da  lea     rcx, [rbp+var_18]
0x1800694de  call    ??0?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@AEBVCMpCriticalSection@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(CommonUtil::CMpCriticalSection const &,CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::ENUM_LOCK_INITIAL_STATE)
0x1800694e3  lea     r15, [rbx+0A8h]
0x1800694ea  mov     rdx, r15
0x1800694ed  lea     rcx, [rbp+arg_18]
0x1800694f1  call    ??4?$AutoRef@UIForceFieldSink@@@CommonUtil@@QEAAAEAV01@AEBV01@@Z; CommonUtil::AutoRef<IForceFieldSink>::operator=(CommonUtil::AutoRef<IForceFieldSink> const &)
0x1800694f6  lea     rcx, [rbp+var_18]
0x1800694fa  mov     [rbp+var_8], 0
0x1800694fe  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x180069503  cmp     [rbp+arg_18], 0
0x180069508  jz      loc_1800695A3
0x18006950e  xor     esi, esi
0x180069510  lea     rcx, [rbp+var_18]
0x180069514  mov     rdx, r14
0x180069517  call    ??0?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@AEBVCMpCriticalSection@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(CommonUtil::CMpCriticalSection const &,CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::ENUM_LOCK_INITIAL_STATE)
0x18006951c  mov     al, 1
0x18006951e  mov     [rbp+var_8], al
0x180069521  test    al, al
0x180069523  jz      short loc_18006958A
0x180069525  mov     rcx, [r15]
0x180069528  test    rcx, rcx
0x18006952b  jz      short loc_180069543
0x18006952d  mov     rax, [rcx]
0x180069530  lea     rdx, [rbp+arg_10]
0x180069534  mov     rax, [rax+38h]
0x180069538  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006953d  mov     esi, eax
0x18006953f  xor     al, al
0x180069541  jmp     short loc_18006951E
0x180069543  mov     rcx, cs:WPP_GLOBAL_Control
0x18006954a  lea     rax, WPP_GLOBAL_Control
0x180069551  cmp     rcx, rax
0x180069554  jz      short loc_180069577
0x180069556  test    byte ptr [rcx+1Ch], 1
0x18006955a  jz      short loc_180069577
0x18006955c  mov     edx, 39h ; '9'
0x180069561  mov     rcx, [rcx+10h]
0x180069565  lea     r8, WPP_9a072a55361f3902b023016d7eb82632_Traceguids
0x18006956c  mov     r9d, 80070015h
0x180069572  call    WPP_SF_d
0x180069577  lea     rcx, [rbp+var_18]
0x18006957b  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x180069580  mov     ebx, 80070015h
0x180069585  jmp     loc_1800696A1
0x18006958a  lea     rcx, [rbp+var_18]
0x18006958e  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x180069593  test    esi, esi
0x180069595  jns     short loc_1800695C7
0x180069597  mov     rcx, rbx; this
0x18006959a  call    ?IsDefenderPrimaryAV@DashboardEx@ShieldProvider@@AEAA_NXZ; ShieldProvider::DashboardEx::IsDefenderPrimaryAV(void)
0x18006959f  test    al, al
0x1800695a1  jz      short loc_1800695B5
0x1800695a3  mov     rdx, rdi; struct PillarStatus *
0x1800695a6  mov     rcx, rbx; this
0x1800695a9  call    ?GetDefenderPillarStatus@DashboardEx@ShieldProvider@@AEAAJPEAUPillarStatus@@@Z; ShieldProvider::DashboardEx::GetDefenderPillarStatus(PillarStatus *)
0x1800695ae  mov     ebx, eax
0x1800695b0  jmp     loc_1800696A1
0x1800695b5  mov     dword ptr [rdi+4], 1
0x1800695bc  mov     dword ptr [rdi], 8Fh
0x1800695c2  jmp     loc_18006969F
0x1800695c7  cmp     [rbp+arg_10], 0
0x1800695cb  jz      short loc_1800695A3
0x1800695cd  mov     rdx, r14
0x1800695d0  lea     rcx, [rbp+var_18]
0x1800695d4  call    ??0?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@AEBVCMpCriticalSection@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(CommonUtil::CMpCriticalSection const &,CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::ENUM_LOCK_INITIAL_STATE)
0x1800695d9  mov     al, 1
0x1800695db  mov     [rbp+var_8], al
0x1800695de  test    al, al
0x1800695e0  jz      loc_180069696
0x1800695e6  mov     rcx, [r15]
0x1800695e9  test    rcx, rcx
0x1800695ec  jz      short loc_18006966B
0x1800695ee  mov     [rbp+pv], 0
0x1800695f6  lea     rdx, [rbp+pv]
0x1800695fa  mov     rax, [rcx]
0x1800695fd  mov     rax, [rax+48h]
0x180069601  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069606  mov     rbx, [rbp+pv]
0x18006960a  mov     esi, eax
0x18006960c  test    eax, eax
0x18006960e  js      short loc_18006961A
0x180069610  mov     eax, [rbx+4]
0x180069613  mov     [rdi+4], eax
0x180069616  mov     eax, [rbx]
0x180069618  jmp     short loc_180069626
0x18006961a  mov     dword ptr [rdi+4], 1
0x180069621  mov     eax, 2
0x180069626  mov     [rdi], eax
0x180069628  test    rbx, rbx
0x18006962b  jz      short loc_180069664
0x18006962d  mov     rcx, [rbx+8]; pv
0x180069631  test    rcx, rcx
0x180069634  jz      short loc_180069644
0x180069636  call    cs:__imp_CoTaskMemFree
0x18006963c  mov     qword ptr [rbx+8], 0
0x180069644  mov     rcx, [rbx+10h]; pv
0x180069648  test    rcx, rcx
0x18006964b  jz      short loc_18006965B
0x18006964d  call    cs:__imp_CoTaskMemFree
0x180069653  mov     qword ptr [rbx+10h], 0
0x18006965b  mov     rcx, rbx; pv
0x18006965e  call    cs:__imp_CoTaskMemFree
0x180069664  xor     al, al
0x180069666  jmp     loc_1800695DB
0x18006966b  mov     rcx, cs:WPP_GLOBAL_Control
0x180069672  lea     rax, WPP_GLOBAL_Control
0x180069679  cmp     rcx, rax
0x18006967c  jz      loc_180069577
0x180069682  test    byte ptr [rcx+1Ch], 1
0x180069686  jz      loc_180069577
0x18006968c  mov     edx, 3Ah ; ':'
0x180069691  jmp     loc_180069561
0x180069696  lea     rcx, [rbp+var_18]
0x18006969a  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x18006969f  mov     ebx, esi
0x1800696a1  lea     rcx, [rbp+arg_18]
0x1800696a5  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x1800696aa  mov     eax, ebx
0x1800696ac  mov     rbx, [rsp+40h+arg_0]
0x1800696b1  add     rsp, 40h
0x1800696b5  pop     r15
0x1800696b7  pop     r14
0x1800696b9  pop     rdi
0x1800696ba  pop     rsi
0x1800696bb  pop     rbp
0x1800696bc  retn
```
