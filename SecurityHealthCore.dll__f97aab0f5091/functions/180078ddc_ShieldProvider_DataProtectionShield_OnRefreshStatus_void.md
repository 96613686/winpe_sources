# ShieldProvider::DataProtectionShield::OnRefreshStatus(void)

- ea: `0x180078ddc`
- end: `0x180078f3d`
- name: `?OnRefreshStatus@DataProtectionShield@ShieldProvider@@QEAAJXZ`
- size: `353`
- prototype: `__int64 __fastcall(ShieldProvider::DataProtectionShield *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x180079090`

## callees

- `0x180004710`
- `0x18000ccb0`
- `0x18000f02c`
- `0x18000f094`
- `0x180067a7c`
- `0x1800775dc`
- `0x180078ddc`
- `0x180079d48`
- `0x1800d3b3c`
- `0x1800d3bf4`
- `0x1800e7010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180078ed6`
- `ole32!CoTaskMemFree` at `0x180078ee0`
- `ole32!CoTaskMemFree` at `0x180078eea`
- `ole32!CoTaskMemFree` at `0x180078ef4`
- `ole32!CoTaskMemFree` at `0x180078efe`
- `ole32!CoTaskMemFree` at `0x180078f07`
- `ole32!CoTaskMemFree` at `0x180078ed6`
- `ole32!CoTaskMemFree` at `0x180078ee0`
- `ole32!CoTaskMemFree` at `0x180078eea`
- `ole32!CoTaskMemFree` at `0x180078ef4`
- `ole32!CoTaskMemFree` at `0x180078efe`
- `ole32!CoTaskMemFree` at `0x180078f07`

## pseudocode

```c
__int64 __fastcall ShieldProvider::DataProtectionShield::OnRefreshStatus(struct Shield_CloudBackupProviderInfo **this)
{
  int refreshed; // r14d
  LPVOID *v3; // rsi
  struct Shield_CloudBackupProviderInfo *v4; // rcx
  struct Shield_CloudBackupProviderInfo *v5; // rdi
  int v6; // eax
  __int64 v7; // rbx
  int v9[2]; // [rsp+20h] [rbp-E0h] BYREF
  struct Shield_CloudBackupProviderInfo *v10; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v11[32]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v12[240]; // [rsp+50h] [rbp-B0h] BYREF

  v9[0] = 0;
  refreshed = ShieldProvider::DataProtectionShield::RefreshPillarStatusForUser(this, v9);
  if ( refreshed >= 0 && v9[0] )
  {
    v3 = 0;
    *(_QWORD *)v9 = 0;
    v10 = 0;
    CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(
      v11,
      this + 7);
    CommonUtil::AutoRef<IForceFieldSink>::operator=(v9, this + 4);
    v4 = this[6];
    v5 = this[5];
    if ( v4 )
    {
      v6 = ShieldProvider::DataProtectionShield::DuplicateCloudBackupProviderInfoEx(v4, (LPVOID **)&v10);
      v3 = (LPVOID *)v10;
      refreshed = v6;
    }
    v11[16] = 0;
    CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v11);
    if ( refreshed >= 0 )
    {
      v7 = *(_QWORD *)v9;
      if ( *(_QWORD *)v9 )
      {
        ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(
          (ShieldProvider::CRPCTimeoutEx *)v12,
          0xBB8u,
          L"ShieldProvider::DataProtectionShield::OnRefreshStatus");
        (*(void (__fastcall **)(__int64, struct Shield_CloudBackupProviderInfo *, LPVOID *))(*(_QWORD *)v7 + 40LL))(
          v7,
          v5,
          v3);
        ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx((ShieldProvider::CRPCTimeoutEx *)v12);
      }
    }
    if ( v3 )
    {
      CoTaskMemFree(v3[3]);
      CoTaskMemFree(v3[4]);
      CoTaskMemFree(v3[5]);
      CoTaskMemFree(v3[6]);
      CoTaskMemFree(v3[7]);
      CoTaskMemFree(v3);
    }
    CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(v9);
  }
  return 0;
}

```

## disassembly

```asm
0x180078ddc  mov     [rsp-8+arg_8], rbx
0x180078de1  mov     [rsp-8+arg_10], rsi
0x180078de6  push    rbp
0x180078de7  push    rdi
0x180078de8  push    r14
0x180078dea  lea     rbp, [rsp-50h]
0x180078def  sub     rsp, 150h
0x180078df6  mov     rax, cs:__security_cookie
0x180078dfd  xor     rax, rsp
0x180078e00  mov     [rbp+60h+var_20], rax
0x180078e04  lea     rdx, [rsp+160h+var_140]; int *
0x180078e09  mov     [rsp+160h+var_140], 0
0x180078e11  mov     rbx, rcx
0x180078e14  call    ?RefreshPillarStatusForUser@DataProtectionShield@ShieldProvider@@AEAAJPEAH@Z; ShieldProvider::DataProtectionShield::RefreshPillarStatusForUser(int *)
0x180078e19  mov     r14d, eax
0x180078e1c  test    eax, eax
0x180078e1e  js      loc_180078F17
0x180078e24  cmp     [rsp+160h+var_140], 0
0x180078e29  jz      loc_180078F17
0x180078e2f  xor     esi, esi
0x180078e31  mov     qword ptr [rsp+160h+var_140], 0
0x180078e3a  lea     rdx, [rbx+38h]
0x180078e3e  mov     [rsp+160h+var_138], rsi
0x180078e43  lea     rcx, [rsp+160h+var_130]
0x180078e48  call    ??0?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@AEBVCMpCriticalSection@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(CommonUtil::CMpCriticalSection const &,CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::ENUM_LOCK_INITIAL_STATE)
0x180078e4d  lea     rdx, [rbx+20h]
0x180078e51  lea     rcx, [rsp+160h+var_140]
0x180078e56  call    ??4?$AutoRef@UIForceFieldSink@@@CommonUtil@@QEAAAEAV01@AEBV01@@Z; CommonUtil::AutoRef<IForceFieldSink>::operator=(CommonUtil::AutoRef<IForceFieldSink> const &)
0x180078e5b  mov     rcx, [rbx+30h]; struct Shield_CloudBackupProviderInfo *
0x180078e5f  mov     rdi, [rbx+28h]
0x180078e63  test    rcx, rcx
0x180078e66  jz      short loc_180078E7A
0x180078e68  lea     rdx, [rsp+160h+var_138]; struct Shield_CloudBackupProviderInfo **
0x180078e6d  call    ?DuplicateCloudBackupProviderInfoEx@DataProtectionShield@ShieldProvider@@CAJPEAUShield_CloudBackupProviderInfo@@PEAPEAU3@@Z; ShieldProvider::DataProtectionShield::DuplicateCloudBackupProviderInfoEx(Shield_CloudBackupProviderInfo *,Shield_CloudBackupProviderInfo * *)
0x180078e72  mov     rsi, [rsp+160h+var_138]
0x180078e77  mov     r14d, eax
0x180078e7a  lea     rcx, [rsp+160h+var_130]
0x180078e7f  mov     [rsp+160h+var_120], 0
0x180078e84  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x180078e89  test    r14d, r14d
0x180078e8c  js      short loc_180078ECD
0x180078e8e  mov     rbx, qword ptr [rsp+160h+var_140]
0x180078e93  test    rbx, rbx
0x180078e96  jz      short loc_180078ECD
0x180078e98  lea     r8, aShieldprovider_13; "ShieldProvider::DataProtectionShield::O"...
0x180078e9f  mov     edx, 0BB8h; DueTime
0x180078ea4  lea     rcx, [rsp+160h+var_110]; this
0x180078ea9  call    ??0CRPCTimeoutEx@ShieldProvider@@QEAA@KPEBG@Z; ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(ulong,ushort const *)
0x180078eae  mov     rax, [rbx]
0x180078eb1  mov     r8, rsi
0x180078eb4  mov     rdx, rdi
0x180078eb7  mov     rcx, rbx
0x180078eba  mov     rax, [rax+28h]
0x180078ebe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078ec3  lea     rcx, [rsp+160h+var_110]; this
0x180078ec8  call    ??1CRPCTimeoutEx@ShieldProvider@@QEAA@XZ; ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx(void)
0x180078ecd  test    rsi, rsi
0x180078ed0  jz      short loc_180078F0D
0x180078ed2  mov     rcx, [rsi+18h]; pv
0x180078ed6  call    cs:__imp_CoTaskMemFree
0x180078edc  mov     rcx, [rsi+20h]; pv
0x180078ee0  call    cs:__imp_CoTaskMemFree
0x180078ee6  mov     rcx, [rsi+28h]; pv
0x180078eea  call    cs:__imp_CoTaskMemFree
0x180078ef0  mov     rcx, [rsi+30h]; pv
0x180078ef4  call    cs:__imp_CoTaskMemFree
0x180078efa  mov     rcx, [rsi+38h]; pv
0x180078efe  call    cs:__imp_CoTaskMemFree
0x180078f04  mov     rcx, rsi; pv
0x180078f07  call    cs:__imp_CoTaskMemFree
0x180078f0d  lea     rcx, [rsp+160h+var_140]
0x180078f12  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x180078f17  xor     eax, eax
0x180078f19  mov     rcx, [rbp+60h+var_20]
0x180078f1d  xor     rcx, rsp; StackCookie
0x180078f20  call    __security_check_cookie
0x180078f25  lea     r11, [rsp+160h+var_10]
0x180078f2d  mov     rbx, [r11+28h]
0x180078f31  mov     rsi, [r11+30h]
0x180078f35  mov     rsp, r11
0x180078f38  pop     r14
0x180078f3a  pop     rdi
0x180078f3b  pop     rbp
0x180078f3c  retn
```
