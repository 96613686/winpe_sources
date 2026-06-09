# ShieldProvider::ForceFieldShield::OnWscServiceStatusChanged(void)

- ea: `0x1800c0374`
- end: `0x1800c07a6`
- name: `?OnWscServiceStatusChanged@ForceFieldShield@ShieldProvider@@QEAAJXZ`
- size: `1074`
- prototype: `__int64 __fastcall(ShieldProvider::ForceFieldShield *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800c07b0`

## callees

- `0x180004710`
- `0x18000ccb0`
- `0x18000d7fc`
- `0x18000d83c`
- `0x18000f02c`
- `0x18000f094`
- `0x180029b38`
- `0x18004ea1c`
- `0x180067a7c`
- `0x18006e0a4`
- `0x18007ac88`
- `0x1800be2e8`
- `0x1800bf504`
- `0x1800c0374`
- `0x1800c07bc`
- `0x1800c0e30`
- `0x1800d3b3c`
- `0x1800d3bf4`
- `0x1800e3e8c`
- `0x1800e7010`

## import_xrefs

- `KERNEL32!Sleep` at `0x1800c056b`
- `KERNEL32!Sleep` at `0x1800c056b`
- `ole32!CoTaskMemFree` at `0x1800c0472`
- `ole32!CoTaskMemFree` at `0x1800c047c`
- `ole32!CoTaskMemFree` at `0x1800c0486`
- `ole32!CoTaskMemFree` at `0x1800c048f`
- `ole32!CoTaskMemFree` at `0x1800c0472`
- `ole32!CoTaskMemFree` at `0x1800c047c`
- `ole32!CoTaskMemFree` at `0x1800c0486`
- `ole32!CoTaskMemFree` at `0x1800c048f`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x1800c050c`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x1800c050c`

## string_xrefs

- `0x1800c0407`: `ShieldProvider::ForceFieldShield::OnWscServiceStatusChanged`
- `0x1800c042d`: `ShieldProvider::ForceFieldShield::OnWscServiceStatusChanged`
- `0x1800c05e7`: `ShieldProvider::ForceFieldShield::OnWscServiceStatusChanged`
- `0x1800c069a`: `ShieldProvider::ForceFieldShield::OnWscServiceStatusChanged`
- `0x1800c070d`: `ShieldProvider::ForceFieldShield::OnWscServiceStatusChanged`
- `0x1800c04e5`: `Windows.SecurityCenter.SecurityAppBroker`

## pseudocode

```c
__int64 __fastcall ShieldProvider::ForceFieldShield::OnWscServiceStatusChanged(ShieldProvider::WscBrokerSink **this)
{
  unsigned int v2; // r15d
  char v3; // r13
  int IsWscServiceRunning; // esi
  struct ShieldProvider::DataProtectionShield *v5; // rdx
  LPVOID *v6; // rbx
  _QWORD *v7; // rbx
  int v8; // r14d
  __int64 v9; // rcx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  _QWORD *v13; // r14
  ShieldProvider::WscBrokerSink *v14; // rcx
  int v15; // eax
  int v16; // eax
  __int64 v17; // rbx
  int v18; // eax
  bool v20; // [rsp+30h] [rbp-D0h] BYREF
  int v21[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v22; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v23[24]; // [rsp+48h] [rbp-B8h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v25; // [rsp+78h] [rbp-88h]
  _BYTE v26[240]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v27[240]; // [rsp+170h] [rbp+70h] BYREF

  v2 = 0;
  v22 = 0;
  v3 = 0;
  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(
    v23,
    this + 7);
  v20 = 0;
  IsWscServiceRunning = ShieldProvider::ForceFieldShield::GetIsWscServiceRunning(
                          (ShieldProvider::ForceFieldShield *)this,
                          &v20);
  if ( IsWscServiceRunning < 0 )
    goto LABEL_36;
  CommonUtil::AutoRef<IForceFieldSink>::operator=(&v22, this + 4);
  if ( !v20 )
  {
    if ( this[3] )
    {
      ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(
        (ShieldProvider::CRPCTimeoutEx *)v27,
        0x3E8u,
        L"ShieldProvider::ForceFieldShield::OnWscServiceStatusChanged");
      ShieldProvider::WscBrokerSink::SetParent(this[3], v5);
      ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx((ShieldProvider::CRPCTimeoutEx *)v27);
    }
    this[2] = 0;
    ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(
      (ShieldProvider::CRPCTimeoutEx *)v26,
      0x3E8u,
      L"ShieldProvider::ForceFieldShield::OnWscServiceStatusChanged");
    CommonUtil::AutoRef<IHardwareShield16>::operator=(this + 2);
    CommonUtil::AutoRef<ICrossContainerCommunicationManager>::operator=(this + 3);
    *((_DWORD *)this + 10) = 138;
    *((_DWORD *)this + 11) = 1;
    v6 = (LPVOID *)this[6];
    if ( v6 )
    {
      CoTaskMemFree(v6[2]);
      CoTaskMemFree(v6[3]);
      CoTaskMemFree(v6[4]);
      CoTaskMemFree(v6);
      this[6] = 0;
    }
    v3 = 1;
    ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx((ShieldProvider::CRPCTimeoutEx *)v26);
    goto LABEL_36;
  }
  v7 = this + 2;
  if ( this[2] )
    goto LABEL_36;
  v8 = 0;
  while ( 1 )
  {
    if ( *v7 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v7 + 16LL))(*v7);
      *v7 = 0;
    }
    v25 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.SecurityCenter.SecurityAppBroker",
      0x29u,
      0x28u);
    v9 = v25;
    *v7 = 0;
    *(_QWORD *)v21 = 0;
    IsWscServiceRunning = RoActivateInstance(v9, v21);
    if ( IsWscServiceRunning < 0 )
      goto LABEL_15;
    if ( !memcmp_0(&GUID_e8ce0994_d686_46f8_a719_9eb1436ec690, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
      break;
    IsWscServiceRunning = (***(__int64 (__fastcall ****)(_QWORD, GUID *, char *))v21)(
                            *(_QWORD *)v21,
                            &GUID_e8ce0994_d686_46f8_a719_9eb1436ec690,
                            (char *)this + 16);
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v21 + 16LL))(*(_QWORD *)v21);
LABEL_15:
    if ( IsWscServiceRunning >= 0 )
      goto LABEL_21;
    Sleep(0x3E8u);
    if ( (unsigned int)++v8 >= 5 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v11 = 51;
        v12 = (unsigned int)IsWscServiceRunning;
LABEL_33:
        WPP_SF_d(v10[2], v11, WPP_3533d4a562073f930570ad4a944aa956_Traceguids, v12);
        goto LABEL_34;
      }
      goto LABEL_34;
    }
  }
  *v7 = *(_QWORD *)v21;
LABEL_21:
  v13 = this + 3;
  *(_QWORD *)v21 = this;
  v14 = this[3];
  if ( v14 )
  {
    (*(void (__fastcall **)(ShieldProvider::WscBrokerSink *))(*(_QWORD *)v14 + 16LL))(v14);
    *v13 = 0;
  }
  v15 = Microsoft::WRL::Details::MakeAndInitialize<ShieldProvider::WscForceFieldBrokerSink,ShieldProvider::WscForceFieldBrokerSink,ShieldProvider::ForceFieldShield *>(
          this + 3,
          v21);
  IsWscServiceRunning = v15;
  if ( v15 < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v11 = 50;
      v12 = (unsigned int)v15;
      goto LABEL_33;
    }
  }
  else
  {
    ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(
      (ShieldProvider::CRPCTimeoutEx *)v26,
      0xBB8u,
      L"ShieldProvider::ForceFieldShield::OnWscServiceStatusChanged");
    v16 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, char *))(*(_QWORD *)*v7 + 64LL))(
            *v7,
            *((unsigned int *)this + 42),
            *v13,
            (char *)this + 120);
    IsWscServiceRunning = v16;
    if ( v16 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          49,
          WPP_3533d4a562073f930570ad4a944aa956_Traceguids,
          (unsigned int)v16);
    }
    else
    {
      v2 = 1;
      v3 = 1;
    }
    ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx((ShieldProvider::CRPCTimeoutEx *)v26);
  }
LABEL_34:
  if ( IsWscServiceRunning < 0 )
  {
    ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(
      (ShieldProvider::CRPCTimeoutEx *)v26,
      0x3E8u,
      L"ShieldProvider::ForceFieldShield::OnWscServiceStatusChanged");
    CommonUtil::AutoRef<IHardwareShield16>::operator=(this + 2);
    CommonUtil::AutoRef<ICrossContainerCommunicationManager>::operator=(this + 3);
    ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx((ShieldProvider::CRPCTimeoutEx *)v26);
  }
LABEL_36:
  v23[16] = 0;
  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v23);
  if ( IsWscServiceRunning >= 0
    && v2
    && (int)ShieldProvider::ForceFieldShield::PopulateForceFieldProviders((ShieldProvider::ForceFieldShield *)this) >= 0 )
  {
    ShieldProvider::ForceFieldShield::RefreshPillarStatusForUser(this, v21);
  }
  v17 = v22;
  if ( v22 && IsWscServiceRunning >= 0 && v3 )
  {
    ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(
      (ShieldProvider::CRPCTimeoutEx *)v26,
      0xBB8u,
      L"ShieldProvider::ForceFieldShield::OnWscServiceStatusChanged");
    v18 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v17 + 32LL))(v17, v2);
    if ( v18 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_3533d4a562073f930570ad4a944aa956_Traceguids, v2, v18);
    ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx((ShieldProvider::CRPCTimeoutEx *)v26);
  }
  CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&v22);
  return 0;
}

```

## disassembly

```asm
0x1800c0374  mov     [rsp-8+arg_8], rbx
0x1800c0379  mov     [rsp-8+arg_10], rsi
0x1800c037e  push    rbp
0x1800c037f  push    rdi
0x1800c0380  push    r13
0x1800c0382  push    r14
0x1800c0384  push    r15
0x1800c0386  lea     rbp, [rsp-170h]
0x1800c038e  sub     rsp, 270h
0x1800c0395  mov     rax, cs:__security_cookie
0x1800c039c  xor     rax, rsp
0x1800c039f  mov     [rbp+190h+var_30], rax
0x1800c03a6  mov     rdi, rcx
0x1800c03a9  lea     rdx, [rcx+38h]
0x1800c03ad  xor     r15d, r15d
0x1800c03b0  lea     rcx, [rsp+290h+var_248]
0x1800c03b5  mov     [rsp+290h+var_250], r15
0x1800c03ba  xor     r13b, r13b
0x1800c03bd  call    ??0?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@AEBVCMpCriticalSection@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(CommonUtil::CMpCriticalSection const &,CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::ENUM_LOCK_INITIAL_STATE)
0x1800c03c2  lea     rdx, [rsp+290h+var_260]; bool *
0x1800c03c7  mov     [rsp+290h+var_260], r13b
0x1800c03cc  mov     rcx, rdi; this
0x1800c03cf  call    ?GetIsWscServiceRunning@ForceFieldShield@ShieldProvider@@AEAAJPEA_N@Z; ShieldProvider::ForceFieldShield::GetIsWscServiceRunning(bool *)
0x1800c03d4  lea     r14, WPP_GLOBAL_Control
0x1800c03db  mov     esi, eax
0x1800c03dd  test    eax, eax
0x1800c03df  js      loc_1800C06C9
0x1800c03e5  lea     rdx, [rdi+20h]
0x1800c03e9  lea     rcx, [rsp+290h+var_250]
0x1800c03ee  call    ??4?$AutoRef@UIForceFieldSink@@@CommonUtil@@QEAAAEAV01@AEBV01@@Z; CommonUtil::AutoRef<IForceFieldSink>::operator=(CommonUtil::AutoRef<IForceFieldSink> const &)
0x1800c03f3  cmp     [rsp+290h+var_260], r13b
0x1800c03f8  jnz     loc_1800C04B1
0x1800c03fe  lea     r14, [rdi+18h]
0x1800c0402  cmp     [r14], r15
0x1800c0405  jz      short loc_1800C042D
0x1800c0407  lea     r8, aShieldprovider_49; "ShieldProvider::ForceFieldShield::OnWsc"...
0x1800c040e  mov     edx, 3E8h; DueTime
0x1800c0413  lea     rcx, [rbp+190h+var_120]; this
0x1800c0417  call    ??0CRPCTimeoutEx@ShieldProvider@@QEAA@KPEBG@Z; ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(ulong,ushort const *)
0x1800c041c  mov     rcx, [r14]; this
0x1800c041f  call    ?SetParent@WscBrokerSink@ShieldProvider@@QEAAXPEAVDataProtectionShield@2@@Z; ShieldProvider::WscBrokerSink::SetParent(ShieldProvider::DataProtectionShield *)
0x1800c0424  lea     rcx, [rbp+190h+var_120]; this
0x1800c0428  call    ??1CRPCTimeoutEx@ShieldProvider@@QEAA@XZ; ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx(void)
0x1800c042d  lea     r8, aShieldprovider_49; "ShieldProvider::ForceFieldShield::OnWsc"...
0x1800c0434  mov     [rdi+10h], r15
0x1800c0438  mov     edx, 3E8h; DueTime
0x1800c043d  lea     rcx, [rbp+190h+var_210]; this
0x1800c0441  call    ??0CRPCTimeoutEx@ShieldProvider@@QEAA@KPEBG@Z; ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(ulong,ushort const *)
0x1800c0446  lea     rcx, [rdi+10h]
0x1800c044a  call    ??4?$AutoRef@UIHardwareShield16@@@CommonUtil@@QEAAAEAV01@PEAUIHardwareShield16@@@Z; CommonUtil::AutoRef<IHardwareShield16>::operator=(IHardwareShield16 *)
0x1800c044f  mov     rcx, r14
0x1800c0452  call    ??4?$AutoRef@UICrossContainerCommunicationManager@@@CommonUtil@@QEAAAEAV01@PEAUICrossContainerCommunicationManager@@@Z; CommonUtil::AutoRef<ICrossContainerCommunicationManager>::operator=(ICrossContainerCommunicationManager *)
0x1800c0457  mov     dword ptr [rdi+28h], 8Ah
0x1800c045e  mov     dword ptr [rdi+2Ch], 1
0x1800c0465  mov     rbx, [rdi+30h]
0x1800c0469  test    rbx, rbx
0x1800c046c  jz      short loc_1800C0499
0x1800c046e  mov     rcx, [rbx+10h]; pv
0x1800c0472  call    cs:__imp_CoTaskMemFree
0x1800c0478  mov     rcx, [rbx+18h]; pv
0x1800c047c  call    cs:__imp_CoTaskMemFree
0x1800c0482  mov     rcx, [rbx+20h]; pv
0x1800c0486  call    cs:__imp_CoTaskMemFree
0x1800c048c  mov     rcx, rbx; pv
0x1800c048f  call    cs:__imp_CoTaskMemFree
0x1800c0495  mov     [rdi+30h], r15
0x1800c0499  lea     rcx, [rbp+190h+var_210]; this
0x1800c049d  mov     r13b, 1
0x1800c04a0  call    ??1CRPCTimeoutEx@ShieldProvider@@QEAA@XZ; ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx(void)
0x1800c04a5  lea     r14, WPP_GLOBAL_Control
0x1800c04ac  jmp     loc_1800C06C9
0x1800c04b1  lea     rbx, [rdi+10h]
0x1800c04b5  cmp     [rbx], r15
0x1800c04b8  jnz     loc_1800C06C9
0x1800c04be  xor     r14d, r14d
0x1800c04c1  mov     rcx, [rbx]
0x1800c04c4  xor     esi, esi
0x1800c04c6  test    rcx, rcx
0x1800c04c9  jz      short loc_1800C04DA
0x1800c04cb  mov     rax, [rcx]
0x1800c04ce  mov     rax, [rax+10h]
0x1800c04d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c04d7  mov     [rbx], rsi
0x1800c04da  mov     r9d, 28h ; '('; unsigned int
0x1800c04e0  mov     [rsp+290h+var_218], rsi
0x1800c04e5  lea     rdx, ?RuntimeClass_Windows_SecurityCenter_SecurityAppBroker@@3QBGB; "Windows.SecurityCenter.SecurityAppBroke"...
0x1800c04ec  lea     rcx, [rsp+290h+hstringHeader]; hstringHeader
0x1800c04f1  lea     r8d, [r9+1]; unsigned int
0x1800c04f5  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800c04fa  mov     rcx, [rsp+290h+var_218]
0x1800c04ff  lea     rdx, [rsp+290h+var_258]
0x1800c0504  mov     [rbx], rsi
0x1800c0507  mov     qword ptr [rsp+290h+var_258], rsi
0x1800c050c  call    cs:__imp_RoActivateInstance
0x1800c0512  mov     esi, eax
0x1800c0514  test    eax, eax
0x1800c0516  js      short loc_1800C0562
0x1800c0518  mov     r8d, 10h; Size
0x1800c051e  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x1800c0525  lea     rcx, _GUID_e8ce0994_d686_46f8_a719_9eb1436ec690; Buf1
0x1800c052c  call    memcmp_0
0x1800c0531  test    eax, eax
0x1800c0533  jz      short loc_1800C05AC
0x1800c0535  mov     rcx, qword ptr [rsp+290h+var_258]
0x1800c053a  lea     rdx, _GUID_e8ce0994_d686_46f8_a719_9eb1436ec690
0x1800c0541  mov     r8, rbx
0x1800c0544  mov     rax, [rcx]
0x1800c0547  mov     rax, [rax]
0x1800c054a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c054f  mov     rcx, qword ptr [rsp+290h+var_258]
0x1800c0554  mov     esi, eax
0x1800c0556  mov     rax, [rcx]
0x1800c0559  mov     rax, [rax+10h]
0x1800c055d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0562  test    esi, esi
0x1800c0564  jns     short loc_1800C05B4
0x1800c0566  mov     ecx, 3E8h; dwMilliseconds
0x1800c056b  call    cs:__imp_Sleep
0x1800c0571  inc     r14d
0x1800c0574  cmp     r14d, 5
0x1800c0578  jb      loc_1800C04C1
0x1800c057e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c0585  lea     r14, WPP_GLOBAL_Control
0x1800c058c  cmp     rcx, r14
0x1800c058f  jz      loc_1800C0696
0x1800c0595  test    byte ptr [rcx+1Ch], 1
0x1800c0599  jz      loc_1800C0696
0x1800c059f  mov     edx, 33h ; '3'
0x1800c05a4  mov     r9d, esi
0x1800c05a7  jmp     loc_1800C0686
0x1800c05ac  mov     rax, qword ptr [rsp+290h+var_258]
0x1800c05b1  mov     [rbx], rax
0x1800c05b4  lea     r14, [rdi+18h]
0x1800c05b8  mov     qword ptr [rsp+290h+var_258], rdi
0x1800c05bd  mov     rcx, [r14]
0x1800c05c0  test    rcx, rcx
0x1800c05c3  jz      short loc_1800C05D4
0x1800c05c5  mov     rax, [rcx]
0x1800c05c8  mov     rax, [rax+10h]
0x1800c05cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c05d1  mov     [r14], r15
0x1800c05d4  lea     rdx, [rsp+290h+var_258]
0x1800c05d9  mov     rcx, r14
0x1800c05dc  call    ??$MakeAndInitialize@VWscForceFieldBrokerSink@ShieldProvider@@V12@PEAVForceFieldShield@2@@Details@WRL@Microsoft@@YAJPEAPEAVWscForceFieldBrokerSink@ShieldProvider@@$$QEAPEAVForceFieldShield@4@@Z; Microsoft::WRL::Details::MakeAndInitialize<ShieldProvider::WscForceFieldBrokerSink,ShieldProvider::WscForceFieldBrokerSink,ShieldProvider::ForceFieldShield *>(ShieldProvider::WscForceFieldBrokerSink * *,ShieldProvider::ForceFieldShield * &&)
0x1800c05e1  mov     esi, eax
0x1800c05e3  test    eax, eax
0x1800c05e5  js      short loc_1800C0665
0x1800c05e7  lea     r8, aShieldprovider_49; "ShieldProvider::ForceFieldShield::OnWsc"...
0x1800c05ee  mov     edx, 0BB8h; DueTime
0x1800c05f3  lea     rcx, [rbp+190h+var_210]; this
0x1800c05f7  call    ??0CRPCTimeoutEx@ShieldProvider@@QEAA@KPEBG@Z; ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(ulong,ushort const *)
0x1800c05fc  mov     rcx, [rbx]
0x1800c05ff  lea     r9, [rdi+78h]
0x1800c0603  mov     r8, [r14]
0x1800c0606  mov     edx, [rdi+0A8h]
0x1800c060c  mov     rax, [rcx]
0x1800c060f  mov     rax, [rax+40h]
0x1800c0613  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0618  lea     r14, WPP_GLOBAL_Control
0x1800c061f  mov     esi, eax
0x1800c0621  test    eax, eax
0x1800c0623  js      short loc_1800C0630
0x1800c0625  mov     r15d, 1
0x1800c062b  mov     r13b, r15b
0x1800c062e  jmp     short loc_1800C065A
0x1800c0630  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c0637  cmp     rcx, r14
0x1800c063a  jz      short loc_1800C065A
0x1800c063c  test    byte ptr [rcx+1Ch], 1
0x1800c0640  jz      short loc_1800C065A
0x1800c0642  mov     rcx, [rcx+10h]
0x1800c0646  lea     r8, WPP_3533d4a562073f930570ad4a944aa956_Traceguids
0x1800c064d  mov     edx, 31h ; '1'
0x1800c0652  mov     r9d, eax
0x1800c0655  call    WPP_SF_d
0x1800c065a  lea     rcx, [rbp+190h+var_210]; this
0x1800c065e  call    ??1CRPCTimeoutEx@ShieldProvider@@QEAA@XZ; ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx(void)
0x1800c0663  jmp     short loc_1800C0696
0x1800c0665  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c066c  lea     r14, WPP_GLOBAL_Control
0x1800c0673  cmp     rcx, r14
0x1800c0676  jz      short loc_1800C0696
0x1800c0678  test    byte ptr [rcx+1Ch], 1
0x1800c067c  jz      short loc_1800C0696
0x1800c067e  mov     edx, 32h ; '2'
0x1800c0683  mov     r9d, eax
0x1800c0686  mov     rcx, [rcx+10h]
0x1800c068a  lea     r8, WPP_3533d4a562073f930570ad4a944aa956_Traceguids
0x1800c0691  call    WPP_SF_d
0x1800c0696  test    esi, esi
0x1800c0698  jns     short loc_1800C06C9
0x1800c069a  lea     r8, aShieldprovider_49; "ShieldProvider::ForceFieldShield::OnWsc"...
0x1800c06a1  mov     edx, 3E8h; DueTime
0x1800c06a6  lea     rcx, [rbp+190h+var_210]; this
0x1800c06aa  call    ??0CRPCTimeoutEx@ShieldProvider@@QEAA@KPEBG@Z; ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(ulong,ushort const *)
0x1800c06af  mov     rcx, rbx
0x1800c06b2  call    ??4?$AutoRef@UIHardwareShield16@@@CommonUtil@@QEAAAEAV01@PEAUIHardwareShield16@@@Z; CommonUtil::AutoRef<IHardwareShield16>::operator=(IHardwareShield16 *)
0x1800c06b7  lea     rcx, [rdi+18h]
0x1800c06bb  call    ??4?$AutoRef@UICrossContainerCommunicationManager@@@CommonUtil@@QEAAAEAV01@PEAUICrossContainerCommunicationManager@@@Z; CommonUtil::AutoRef<ICrossContainerCommunicationManager>::operator=(ICrossContainerCommunicationManager *)
0x1800c06c0  lea     rcx, [rbp+190h+var_210]; this
0x1800c06c4  call    ??1CRPCTimeoutEx@ShieldProvider@@QEAA@XZ; ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx(void)
0x1800c06c9  lea     rcx, [rsp+290h+var_248]
0x1800c06ce  mov     [rsp+290h+var_238], 0
0x1800c06d3  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x1800c06d8  test    esi, esi
0x1800c06da  js      short loc_1800C06FA
0x1800c06dc  test    r15d, r15d
0x1800c06df  jz      short loc_1800C06FA
0x1800c06e1  mov     rcx, rdi; this
0x1800c06e4  call    ?PopulateForceFieldProviders@ForceFieldShield@ShieldProvider@@AEAAJXZ; ShieldProvider::ForceFieldShield::PopulateForceFieldProviders(void)
0x1800c06e9  test    eax, eax
0x1800c06eb  js      short loc_1800C06FA
0x1800c06ed  lea     rdx, [rsp+290h+var_258]; int *
0x1800c06f2  mov     rcx, rdi; this
0x1800c06f5  call    ?RefreshPillarStatusForUser@ForceFieldShield@ShieldProvider@@AEAAJPEAH@Z; ShieldProvider::ForceFieldShield::RefreshPillarStatusForUser(int *)
0x1800c06fa  mov     rbx, [rsp+290h+var_250]
0x1800c06ff  test    rbx, rbx
0x1800c0702  jz      short loc_1800C076F
0x1800c0704  test    esi, esi
0x1800c0706  js      short loc_1800C076F
0x1800c0708  test    r13b, r13b
0x1800c070b  jz      short loc_1800C076F
0x1800c070d  lea     r8, aShieldprovider_49; "ShieldProvider::ForceFieldShield::OnWsc"...
0x1800c0714  mov     edx, 0BB8h; DueTime
0x1800c0719  lea     rcx, [rbp+190h+var_210]; this
0x1800c071d  call    ??0CRPCTimeoutEx@ShieldProvider@@QEAA@KPEBG@Z; ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(ulong,ushort const *)
0x1800c0722  mov     rax, [rbx]
0x1800c0725  mov     edx, r15d
0x1800c0728  mov     rcx, rbx
0x1800c072b  mov     rax, [rax+20h]
0x1800c072f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0734  test    eax, eax
0x1800c0736  jns     short loc_1800C0766
0x1800c0738  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c073f  cmp     rcx, r14
0x1800c0742  jz      short loc_1800C0766
0x1800c0744  test    byte ptr [rcx+1Ch], 1
0x1800c0748  jz      short loc_1800C0766
0x1800c074a  mov     rcx, [rcx+10h]
0x1800c074e  lea     r8, WPP_3533d4a562073f930570ad4a944aa956_Traceguids
0x1800c0755  mov     edx, 34h ; '4'
0x1800c075a  mov     [rsp+290h+var_270], eax
0x1800c075e  mov     r9d, r15d
0x1800c0761  call    WPP_SF_Dd
0x1800c0766  lea     rcx, [rbp+190h+var_210]; this
0x1800c076a  call    ??1CRPCTimeoutEx@ShieldProvider@@QEAA@XZ; ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx(void)
0x1800c076f  lea     rcx, [rsp+290h+var_250]
0x1800c0774  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x1800c0779  xor     eax, eax
0x1800c077b  mov     rcx, [rbp+190h+var_30]
0x1800c0782  xor     rcx, rsp; StackCookie
0x1800c0785  call    __security_check_cookie
0x1800c078a  lea     r11, [rsp+290h+var_20]
0x1800c0792  mov     rbx, [r11+38h]
0x1800c0796  mov     rsi, [r11+40h]
0x1800c079a  mov     rsp, r11
0x1800c079d  pop     r15
0x1800c079f  pop     r14
0x1800c07a1  pop     r13
0x1800c07a3  pop     rdi
0x1800c07a4  pop     rbp
0x1800c07a5  retn
```
