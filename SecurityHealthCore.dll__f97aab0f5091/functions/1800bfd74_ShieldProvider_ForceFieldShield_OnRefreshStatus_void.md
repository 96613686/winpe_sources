# ShieldProvider::ForceFieldShield::OnRefreshStatus(void)

- ea: `0x1800bfd74`
- end: `0x1800bfec5`
- name: `?OnRefreshStatus@ForceFieldShield@ShieldProvider@@QEAAJXZ`
- size: `337`
- prototype: `__int64 __fastcall(ShieldProvider::ForceFieldShield *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800c0010`

## callees

- `0x180004710`
- `0x18000ccb0`
- `0x18000f02c`
- `0x18000f094`
- `0x180067a7c`
- `0x1800bebd8`
- `0x1800bfd74`
- `0x1800c0e30`
- `0x1800d3b3c`
- `0x1800d3bf4`
- `0x1800e7010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800bfe72`
- `ole32!CoTaskMemFree` at `0x1800bfe7c`
- `ole32!CoTaskMemFree` at `0x1800bfe86`
- `ole32!CoTaskMemFree` at `0x1800bfe8f`
- `ole32!CoTaskMemFree` at `0x1800bfe72`
- `ole32!CoTaskMemFree` at `0x1800bfe7c`
- `ole32!CoTaskMemFree` at `0x1800bfe86`
- `ole32!CoTaskMemFree` at `0x1800bfe8f`

## pseudocode

```c
__int64 __fastcall ShieldProvider::ForceFieldShield::OnRefreshStatus(struct Shield_ForceFieldProviderInfo **this)
{
  int refreshed; // ebx
  LPVOID *v3; // rsi
  struct Shield_ForceFieldProviderInfo *v4; // rcx
  struct Shield_ForceFieldProviderInfo *v5; // rdi
  int v6; // eax
  __int64 v7; // rbx
  int v9[2]; // [rsp+30h] [rbp-D0h] BYREF
  struct Shield_ForceFieldProviderInfo *v10; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v11[32]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v12[240]; // [rsp+60h] [rbp-A0h] BYREF

  v9[0] = 0;
  refreshed = ShieldProvider::ForceFieldShield::RefreshPillarStatusForUser(this, v9);
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
      v6 = ShieldProvider::ForceFieldShield::DuplicateForceFieldProviderInfoEx(v4, &v10);
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
          L"ShieldProvider::ForceFieldShield::OnRefreshStatus");
        (*(void (__fastcall **)(__int64, _QWORD, struct Shield_ForceFieldProviderInfo *, LPVOID *))(*(_QWORD *)v7 + 40LL))(
          v7,
          *((unsigned int *)this + 41),
          v5,
          v3);
        ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx((ShieldProvider::CRPCTimeoutEx *)v12);
      }
    }
    if ( v3 )
    {
      CoTaskMemFree(v3[2]);
      CoTaskMemFree(v3[3]);
      CoTaskMemFree(v3[4]);
      CoTaskMemFree(v3);
    }
    CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(v9);
  }
  return 0;
}

```

## disassembly

```asm
0x1800bfd74  mov     [rsp-8+arg_8], rbx
0x1800bfd79  mov     [rsp-8+arg_10], rsi
0x1800bfd7e  push    rbp
0x1800bfd7f  push    rdi
0x1800bfd80  push    r14
0x1800bfd82  lea     rbp, [rsp-60h]
0x1800bfd87  sub     rsp, 160h
0x1800bfd8e  mov     rax, cs:__security_cookie
0x1800bfd95  xor     rax, rsp
0x1800bfd98  mov     [rbp+70h+var_20], rax
0x1800bfd9c  lea     rdx, [rsp+170h+var_140]; int *
0x1800bfda1  mov     [rsp+170h+var_140], 0
0x1800bfda9  mov     r14, rcx
0x1800bfdac  call    ?RefreshPillarStatusForUser@ForceFieldShield@ShieldProvider@@AEAAJPEAH@Z; ShieldProvider::ForceFieldShield::RefreshPillarStatusForUser(int *)
0x1800bfdb1  mov     ebx, eax
0x1800bfdb3  test    eax, eax
0x1800bfdb5  js      loc_1800BFE9F
0x1800bfdbb  cmp     [rsp+170h+var_140], 0
0x1800bfdc0  jz      loc_1800BFE9F
0x1800bfdc6  xor     esi, esi
0x1800bfdc8  mov     qword ptr [rsp+170h+var_140], 0
0x1800bfdd1  lea     rdx, [r14+38h]
0x1800bfdd5  mov     [rsp+170h+var_138], rsi
0x1800bfdda  lea     rcx, [rsp+170h+var_130]
0x1800bfddf  call    ??0?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@AEBVCMpCriticalSection@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(CommonUtil::CMpCriticalSection const &,CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::ENUM_LOCK_INITIAL_STATE)
0x1800bfde4  lea     rdx, [r14+20h]
0x1800bfde8  lea     rcx, [rsp+170h+var_140]
0x1800bfded  call    ??4?$AutoRef@UIForceFieldSink@@@CommonUtil@@QEAAAEAV01@AEBV01@@Z; CommonUtil::AutoRef<IForceFieldSink>::operator=(CommonUtil::AutoRef<IForceFieldSink> const &)
0x1800bfdf2  mov     rcx, [r14+30h]; struct Shield_ForceFieldProviderInfo *
0x1800bfdf6  mov     rdi, [r14+28h]
0x1800bfdfa  test    rcx, rcx
0x1800bfdfd  jz      short loc_1800BFE10
0x1800bfdff  lea     rdx, [rsp+170h+var_138]; struct Shield_ForceFieldProviderInfo **
0x1800bfe04  call    ?DuplicateForceFieldProviderInfoEx@ForceFieldShield@ShieldProvider@@CAJPEAUShield_ForceFieldProviderInfo@@PEAPEAU3@@Z; ShieldProvider::ForceFieldShield::DuplicateForceFieldProviderInfoEx(Shield_ForceFieldProviderInfo *,Shield_ForceFieldProviderInfo * *)
0x1800bfe09  mov     rsi, [rsp+170h+var_138]
0x1800bfe0e  mov     ebx, eax
0x1800bfe10  lea     rcx, [rsp+170h+var_130]
0x1800bfe15  mov     [rsp+170h+var_120], 0
0x1800bfe1a  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x1800bfe1f  test    ebx, ebx
0x1800bfe21  js      short loc_1800BFE69
0x1800bfe23  mov     rbx, qword ptr [rsp+170h+var_140]
0x1800bfe28  test    rbx, rbx
0x1800bfe2b  jz      short loc_1800BFE69
0x1800bfe2d  lea     r8, aShieldprovider_0; "ShieldProvider::ForceFieldShield::OnRef"...
0x1800bfe34  mov     edx, 0BB8h; DueTime
0x1800bfe39  lea     rcx, [rsp+170h+var_110]; this
0x1800bfe3e  call    ??0CRPCTimeoutEx@ShieldProvider@@QEAA@KPEBG@Z; ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(ulong,ushort const *)
0x1800bfe43  mov     rax, [rbx]
0x1800bfe46  mov     r9, rsi
0x1800bfe49  mov     edx, [r14+0A4h]
0x1800bfe50  mov     r8, rdi
0x1800bfe53  mov     rcx, rbx
0x1800bfe56  mov     rax, [rax+28h]
0x1800bfe5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bfe5f  lea     rcx, [rsp+170h+var_110]; this
0x1800bfe64  call    ??1CRPCTimeoutEx@ShieldProvider@@QEAA@XZ; ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx(void)
0x1800bfe69  test    rsi, rsi
0x1800bfe6c  jz      short loc_1800BFE95
0x1800bfe6e  mov     rcx, [rsi+10h]; pv
0x1800bfe72  call    cs:__imp_CoTaskMemFree
0x1800bfe78  mov     rcx, [rsi+18h]; pv
0x1800bfe7c  call    cs:__imp_CoTaskMemFree
0x1800bfe82  mov     rcx, [rsi+20h]; pv
0x1800bfe86  call    cs:__imp_CoTaskMemFree
0x1800bfe8c  mov     rcx, rsi; pv
0x1800bfe8f  call    cs:__imp_CoTaskMemFree
0x1800bfe95  lea     rcx, [rsp+170h+var_140]
0x1800bfe9a  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x1800bfe9f  xor     eax, eax
0x1800bfea1  mov     rcx, [rbp+70h+var_20]
0x1800bfea5  xor     rcx, rsp; StackCookie
0x1800bfea8  call    __security_check_cookie
0x1800bfead  lea     r11, [rsp+170h+var_10]
0x1800bfeb5  mov     rbx, [r11+28h]
0x1800bfeb9  mov     rsi, [r11+30h]
0x1800bfebd  mov     rsp, r11
0x1800bfec0  pop     r14
0x1800bfec2  pop     rdi
0x1800bfec3  pop     rbp
0x1800bfec4  retn
```
