# ShieldProvider::ForceFieldShield::OnForceFieldAction(Windows::SecurityCenter::BrokerSecurityAppAction,Windows::SecurityCenter::BrokerSecurityAppDetails)

- ea: `0x1800bfab8`
- end: `0x1800bfd6e`
- name: `?OnForceFieldAction@ForceFieldShield@ShieldProvider@@QEAAJW4BrokerSecurityAppAction@SecurityCenter@Windows@@UBrokerSecurityAppDetails@45@@Z`
- size: `694`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800c0270`

## callees

- `0x180004710`
- `0x18000ccb0`
- `0x18000d7fc`
- `0x18000f02c`
- `0x18000f094`
- `0x180067a7c`
- `0x1800bebd8`
- `0x1800bfab8`
- `0x1800c0e30`
- `0x1800c16c8`
- `0x1800c18cc`
- `0x1800d3b3c`
- `0x1800d3bf4`
- `0x1800e7010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1800bfb2a`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1800bfb2a`
- `ole32!CoTaskMemFree` at `0x1800bfcec`
- `ole32!CoTaskMemFree` at `0x1800bfcf6`
- `ole32!CoTaskMemFree` at `0x1800bfd00`
- `ole32!CoTaskMemFree` at `0x1800bfd09`
- `ole32!CoTaskMemFree` at `0x1800bfd18`
- `ole32!CoTaskMemFree` at `0x1800bfd22`
- `ole32!CoTaskMemFree` at `0x1800bfd2c`
- `ole32!CoTaskMemFree` at `0x1800bfd35`
- `ole32!CoTaskMemFree` at `0x1800bfcec`
- `ole32!CoTaskMemFree` at `0x1800bfcf6`
- `ole32!CoTaskMemFree` at `0x1800bfd00`
- `ole32!CoTaskMemFree` at `0x1800bfd09`
- `ole32!CoTaskMemFree` at `0x1800bfd18`
- `ole32!CoTaskMemFree` at `0x1800bfd22`
- `ole32!CoTaskMemFree` at `0x1800bfd2c`
- `ole32!CoTaskMemFree` at `0x1800bfd35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bfb10`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bfb10`

## pseudocode

```c
__int64 __fastcall ShieldProvider::ForceFieldShield::OnForceFieldAction(__int64 a1, unsigned int a2, __int64 a3)
{
  char i; // al
  const wchar_t *StringRawBuffer; // rax
  const wchar_t *v8; // rcx
  int v9; // eax
  LPVOID *v10; // r14
  int v11; // r12d
  int updated; // edi
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rbx
  LPVOID *v16; // rsi
  struct Shield_ForceFieldProviderInfo *v17; // rcx
  __int64 v18; // rdi
  int v19; // eax
  int v21; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v23; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v24[16]; // [rsp+48h] [rbp-B8h] BYREF
  char v25; // [rsp+58h] [rbp-A8h]
  _BYTE v26[240]; // [rsp+60h] [rbp-A0h] BYREF

  v23 = 0;
  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(
    v24,
    a1 + 56);
  for ( i = 1; ; i = 0 )
  {
    v25 = i;
    if ( !i )
      break;
    StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)(a3 + 56), 0);
    v8 = *(const wchar_t **)(a1 + 128);
    if ( !v8 || !StringRawBuffer || _wcsicmp(v8, StringRawBuffer) || *(_DWORD *)(a3 + 40) != *(_DWORD *)(a1 + 168) )
    {
      CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v24);
      goto LABEL_30;
    }
    CommonUtil::AutoRef<IForceFieldSink>::operator=(&v23, a1 + 32);
  }
  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v24);
  v21 = 0;
  pv = 0;
  v9 = ShieldProvider::ForceFieldShield::TranslateForceFieldProviderInfoEx(
         (struct Windows::SecurityCenter::BrokerSecurityAppDetails *)a3,
         (struct Shield_ForceFieldProviderInfo **)&pv);
  v10 = (LPVOID *)pv;
  v11 = v9;
  if ( v9 >= 0 )
  {
    updated = ShieldProvider::ForceFieldShield::UpdateForceFieldProviders(a1, a2, pv);
    if ( updated < 0 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v14 = 54;
        goto LABEL_18;
      }
    }
    else
    {
      updated = ShieldProvider::ForceFieldShield::RefreshPillarStatusForUser(
                  (struct Shield_ForceFieldProviderInfo **)a1,
                  &v21);
      if ( updated < 0 )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v14 = 53;
LABEL_18:
          WPP_SF_d(v13[2], v14, WPP_3533d4a562073f930570ad4a944aa956_Traceguids, (unsigned int)updated);
        }
      }
    }
    v15 = v23;
    if ( v23 )
    {
      ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(
        (ShieldProvider::CRPCTimeoutEx *)v26,
        0xBB8u,
        L"ShieldProvider::ForceFieldShield::OnForceFieldAction");
      (*(void (__fastcall **)(__int64, _QWORD, LPVOID *))(*(_QWORD *)v15 + 24LL))(v15, a2, v10);
      ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx((ShieldProvider::CRPCTimeoutEx *)v26);
      if ( updated >= 0 )
      {
        if ( v21 )
        {
          v16 = 0;
          pv = 0;
          CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(
            v24,
            a1 + 56);
          v17 = *(struct Shield_ForceFieldProviderInfo **)(a1 + 48);
          v18 = *(_QWORD *)(a1 + 40);
          if ( v17 )
          {
            v19 = ShieldProvider::ForceFieldShield::DuplicateForceFieldProviderInfoEx(
                    v17,
                    (struct Shield_ForceFieldProviderInfo **)&pv);
            v16 = (LPVOID *)pv;
            v11 = v19;
          }
          v25 = 0;
          CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v24);
          if ( v11 >= 0 )
          {
            ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(
              (ShieldProvider::CRPCTimeoutEx *)v26,
              0xBB8u,
              L"ShieldProvider::ForceFieldShield::OnForceFieldAction");
            (*(void (__fastcall **)(__int64, _QWORD, __int64, LPVOID *))(*(_QWORD *)v15 + 40LL))(
              v15,
              *(unsigned int *)(a1 + 164),
              v18,
              v16);
            ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx((ShieldProvider::CRPCTimeoutEx *)v26);
          }
          if ( v16 )
          {
            CoTaskMemFree(v16[2]);
            CoTaskMemFree(v16[3]);
            CoTaskMemFree(v16[4]);
            CoTaskMemFree(v16);
          }
        }
      }
    }
  }
  if ( v10 )
  {
    CoTaskMemFree(v10[2]);
    CoTaskMemFree(v10[3]);
    CoTaskMemFree(v10[4]);
    CoTaskMemFree(v10);
  }
LABEL_30:
  CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&v23);
  return 0;
}

```

## disassembly

```asm
0x1800bfab8  mov     [rsp-8+arg_18], rbx
0x1800bfabd  push    rbp
0x1800bfabe  push    rsi
0x1800bfabf  push    rdi
0x1800bfac0  push    r12
0x1800bfac2  push    r13
0x1800bfac4  push    r14
0x1800bfac6  push    r15
0x1800bfac8  lea     rbp, [rsp-60h]
0x1800bfacd  sub     rsp, 160h
0x1800bfad4  mov     rax, cs:__security_cookie
0x1800bfadb  xor     rax, rsp
0x1800bfade  mov     [rbp+90h+var_40], rax
0x1800bfae2  mov     esi, edx
0x1800bfae4  mov     r15, rcx
0x1800bfae7  lea     rdx, [rcx+38h]
0x1800bfaeb  xor     r14d, r14d
0x1800bfaee  lea     rcx, [rsp+190h+var_148]
0x1800bfaf3  mov     [rsp+190h+var_150], r14
0x1800bfaf8  mov     rbx, r8
0x1800bfafb  call    ??0?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@AEBVCMpCriticalSection@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(CommonUtil::CMpCriticalSection const &,CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::ENUM_LOCK_INITIAL_STATE)
0x1800bfb00  mov     al, 1
0x1800bfb02  mov     [rsp+190h+var_138], al
0x1800bfb06  test    al, al
0x1800bfb08  jz      short loc_1800BFB62
0x1800bfb0a  mov     rcx, [rbx+38h]; string
0x1800bfb0e  xor     edx, edx; length
0x1800bfb10  call    cs:__imp_WindowsGetStringRawBuffer
0x1800bfb16  mov     rcx, [r15+80h]; String1
0x1800bfb1d  test    rcx, rcx
0x1800bfb20  jz      short loc_1800BFB53
0x1800bfb22  test    rax, rax
0x1800bfb25  jz      short loc_1800BFB53
0x1800bfb27  mov     rdx, rax; String2
0x1800bfb2a  call    cs:__imp__wcsicmp
0x1800bfb30  test    eax, eax
0x1800bfb32  jnz     short loc_1800BFB53
0x1800bfb34  mov     eax, [r15+0A8h]
0x1800bfb3b  cmp     [rbx+28h], eax
0x1800bfb3e  jnz     short loc_1800BFB53
0x1800bfb40  lea     rdx, [r15+20h]
0x1800bfb44  lea     rcx, [rsp+190h+var_150]
0x1800bfb49  call    ??4?$AutoRef@UIForceFieldSink@@@CommonUtil@@QEAAAEAV01@AEBV01@@Z; CommonUtil::AutoRef<IForceFieldSink>::operator=(CommonUtil::AutoRef<IForceFieldSink> const &)
0x1800bfb4e  mov     al, r14b
0x1800bfb51  jmp     short loc_1800BFB02
0x1800bfb53  lea     rcx, [rsp+190h+var_148]
0x1800bfb58  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x1800bfb5d  jmp     loc_1800BFD3B
0x1800bfb62  lea     rcx, [rsp+190h+var_148]
0x1800bfb67  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x1800bfb6c  lea     rdx, [rsp+190h+pv]; struct Shield_ForceFieldProviderInfo **
0x1800bfb71  mov     [rsp+190h+var_160], r14d
0x1800bfb76  mov     rcx, rbx; struct Windows::SecurityCenter::BrokerSecurityAppDetails *
0x1800bfb79  mov     [rsp+190h+pv], r14
0x1800bfb7e  call    ?TranslateForceFieldProviderInfoEx@ForceFieldShield@ShieldProvider@@CAJPEAUBrokerSecurityAppDetails@SecurityCenter@Windows@@PEAPEAUShield_ForceFieldProviderInfo@@@Z; ShieldProvider::ForceFieldShield::TranslateForceFieldProviderInfoEx(Windows::SecurityCenter::BrokerSecurityAppDetails *,Shield_ForceFieldProviderInfo * *)
0x1800bfb83  mov     r14, [rsp+190h+pv]
0x1800bfb88  mov     r12d, eax
0x1800bfb8b  test    eax, eax
0x1800bfb8d  js      loc_1800BFD0F
0x1800bfb93  mov     r8, r14
0x1800bfb96  mov     edx, esi
0x1800bfb98  mov     rcx, r15
0x1800bfb9b  call    ?UpdateForceFieldProviders@ForceFieldShield@ShieldProvider@@AEAAJW4Shield_ForceFieldProviderAction@@PEAUShield_ForceFieldProviderInfo@@@Z; ShieldProvider::ForceFieldShield::UpdateForceFieldProviders(Shield_ForceFieldProviderAction,Shield_ForceFieldProviderInfo *)
0x1800bfba0  mov     edi, eax
0x1800bfba2  test    eax, eax
0x1800bfba4  js      short loc_1800BFBD9
0x1800bfba6  lea     rdx, [rsp+190h+var_160]; int *
0x1800bfbab  mov     rcx, r15; this
0x1800bfbae  call    ?RefreshPillarStatusForUser@ForceFieldShield@ShieldProvider@@AEAAJPEAH@Z; ShieldProvider::ForceFieldShield::RefreshPillarStatusForUser(int *)
0x1800bfbb3  mov     edi, eax
0x1800bfbb5  test    eax, eax
0x1800bfbb7  jns     short loc_1800BFC0A
0x1800bfbb9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bfbc0  lea     rax, WPP_GLOBAL_Control
0x1800bfbc7  cmp     rcx, rax
0x1800bfbca  jz      short loc_1800BFC0A
0x1800bfbcc  test    byte ptr [rcx+1Ch], 1
0x1800bfbd0  jz      short loc_1800BFC0A
0x1800bfbd2  mov     edx, 35h ; '5'
0x1800bfbd7  jmp     short loc_1800BFBF7
0x1800bfbd9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bfbe0  lea     rax, WPP_GLOBAL_Control
0x1800bfbe7  cmp     rcx, rax
0x1800bfbea  jz      short loc_1800BFC0A
0x1800bfbec  test    byte ptr [rcx+1Ch], 1
0x1800bfbf0  jz      short loc_1800BFC0A
0x1800bfbf2  mov     edx, 36h ; '6'
0x1800bfbf7  mov     rcx, [rcx+10h]
0x1800bfbfb  lea     r8, WPP_3533d4a562073f930570ad4a944aa956_Traceguids
0x1800bfc02  mov     r9d, edi
0x1800bfc05  call    WPP_SF_d
0x1800bfc0a  mov     rbx, [rsp+190h+var_150]
0x1800bfc0f  test    rbx, rbx
0x1800bfc12  jz      loc_1800BFD0F
0x1800bfc18  lea     r8, aShieldprovider_28; "ShieldProvider::ForceFieldShield::OnFor"...
0x1800bfc1f  mov     edx, 0BB8h; DueTime
0x1800bfc24  lea     rcx, [rsp+190h+var_130]; this
0x1800bfc29  call    ??0CRPCTimeoutEx@ShieldProvider@@QEAA@KPEBG@Z; ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(ulong,ushort const *)
0x1800bfc2e  mov     rax, [rbx]
0x1800bfc31  mov     r8, r14
0x1800bfc34  mov     edx, esi
0x1800bfc36  mov     rcx, rbx
0x1800bfc39  mov     rax, [rax+18h]
0x1800bfc3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bfc42  lea     rcx, [rsp+190h+var_130]; this
0x1800bfc47  call    ??1CRPCTimeoutEx@ShieldProvider@@QEAA@XZ; ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx(void)
0x1800bfc4c  test    edi, edi
0x1800bfc4e  js      loc_1800BFD0F
0x1800bfc54  cmp     [rsp+190h+var_160], 0
0x1800bfc59  jz      loc_1800BFD0F
0x1800bfc5f  xor     esi, esi
0x1800bfc61  lea     rdx, [r15+38h]
0x1800bfc65  lea     rcx, [rsp+190h+var_148]
0x1800bfc6a  mov     [rsp+190h+pv], rsi
0x1800bfc6f  call    ??0?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@AEBVCMpCriticalSection@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(CommonUtil::CMpCriticalSection const &,CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::ENUM_LOCK_INITIAL_STATE)
0x1800bfc74  mov     rcx, [r15+30h]; struct Shield_ForceFieldProviderInfo *
0x1800bfc78  mov     rdi, [r15+28h]
0x1800bfc7c  test    rcx, rcx
0x1800bfc7f  jz      short loc_1800BFC93
0x1800bfc81  lea     rdx, [rsp+190h+pv]; struct Shield_ForceFieldProviderInfo **
0x1800bfc86  call    ?DuplicateForceFieldProviderInfoEx@ForceFieldShield@ShieldProvider@@CAJPEAUShield_ForceFieldProviderInfo@@PEAPEAU3@@Z; ShieldProvider::ForceFieldShield::DuplicateForceFieldProviderInfoEx(Shield_ForceFieldProviderInfo *,Shield_ForceFieldProviderInfo * *)
0x1800bfc8b  mov     rsi, [rsp+190h+pv]
0x1800bfc90  mov     r12d, eax
0x1800bfc93  lea     rcx, [rsp+190h+var_148]
0x1800bfc98  mov     [rsp+190h+var_138], 0
0x1800bfc9d  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x1800bfca2  test    r12d, r12d
0x1800bfca5  js      short loc_1800BFCE3
0x1800bfca7  lea     r8, aShieldprovider_28; "ShieldProvider::ForceFieldShield::OnFor"...
0x1800bfcae  mov     edx, 0BB8h; DueTime
0x1800bfcb3  lea     rcx, [rsp+190h+var_130]; this
0x1800bfcb8  call    ??0CRPCTimeoutEx@ShieldProvider@@QEAA@KPEBG@Z; ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(ulong,ushort const *)
0x1800bfcbd  mov     rax, [rbx]
0x1800bfcc0  mov     r9, rsi
0x1800bfcc3  mov     edx, [r15+0A4h]
0x1800bfcca  mov     r8, rdi
0x1800bfccd  mov     rcx, rbx
0x1800bfcd0  mov     rax, [rax+28h]
0x1800bfcd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bfcd9  lea     rcx, [rsp+190h+var_130]; this
0x1800bfcde  call    ??1CRPCTimeoutEx@ShieldProvider@@QEAA@XZ; ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx(void)
0x1800bfce3  test    rsi, rsi
0x1800bfce6  jz      short loc_1800BFD0F
0x1800bfce8  mov     rcx, [rsi+10h]; pv
0x1800bfcec  call    cs:__imp_CoTaskMemFree
0x1800bfcf2  mov     rcx, [rsi+18h]; pv
0x1800bfcf6  call    cs:__imp_CoTaskMemFree
0x1800bfcfc  mov     rcx, [rsi+20h]; pv
0x1800bfd00  call    cs:__imp_CoTaskMemFree
0x1800bfd06  mov     rcx, rsi; pv
0x1800bfd09  call    cs:__imp_CoTaskMemFree
0x1800bfd0f  test    r14, r14
0x1800bfd12  jz      short loc_1800BFD3B
0x1800bfd14  mov     rcx, [r14+10h]; pv
0x1800bfd18  call    cs:__imp_CoTaskMemFree
0x1800bfd1e  mov     rcx, [r14+18h]; pv
0x1800bfd22  call    cs:__imp_CoTaskMemFree
0x1800bfd28  mov     rcx, [r14+20h]; pv
0x1800bfd2c  call    cs:__imp_CoTaskMemFree
0x1800bfd32  mov     rcx, r14; pv
0x1800bfd35  call    cs:__imp_CoTaskMemFree
0x1800bfd3b  lea     rcx, [rsp+190h+var_150]
0x1800bfd40  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x1800bfd45  xor     eax, eax
0x1800bfd47  mov     rcx, [rbp+90h+var_40]
0x1800bfd4b  xor     rcx, rsp; StackCookie
0x1800bfd4e  call    __security_check_cookie
0x1800bfd53  mov     rbx, [rsp+190h+arg_18]
0x1800bfd5b  add     rsp, 160h
0x1800bfd62  pop     r15
0x1800bfd64  pop     r14
0x1800bfd66  pop     r13
0x1800bfd68  pop     r12
0x1800bfd6a  pop     rdi
0x1800bfd6b  pop     rsi
0x1800bfd6c  pop     rbp
0x1800bfd6d  retn
```
