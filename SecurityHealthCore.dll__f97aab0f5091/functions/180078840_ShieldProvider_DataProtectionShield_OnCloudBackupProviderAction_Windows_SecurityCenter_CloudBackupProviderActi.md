# ShieldProvider::DataProtectionShield::OnCloudBackupProviderAction(Windows::SecurityCenter::CloudBackupProviderAction,Windows::SecurityCenter::CloudBackupProviderNamespaceDetails)

- ea: `0x180078840`
- end: `0x180078b0b`
- name: `?OnCloudBackupProviderAction@DataProtectionShield@ShieldProvider@@QEAAJW4CloudBackupProviderAction@SecurityCenter@Windows@@UCloudBackupProviderNamespaceDetails@45@@Z`
- size: `715`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180078cd0`

## callees

- `0x180004710`
- `0x18000ccb0`
- `0x18000d7fc`
- `0x18000f02c`
- `0x18000f094`
- `0x180067a7c`
- `0x1800775dc`
- `0x180078840`
- `0x180079d48`
- `0x18007acc4`
- `0x18007afdc`
- `0x1800d3b3c`
- `0x1800d3bf4`
- `0x1800e7010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1800788b2`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1800788b2`
- `ole32!CoTaskMemFree` at `0x180078a61`
- `ole32!CoTaskMemFree` at `0x180078a6b`
- `ole32!CoTaskMemFree` at `0x180078a75`
- `ole32!CoTaskMemFree` at `0x180078a7f`
- `ole32!CoTaskMemFree` at `0x180078a89`
- `ole32!CoTaskMemFree` at `0x180078a92`
- `ole32!CoTaskMemFree` at `0x180078aa1`
- `ole32!CoTaskMemFree` at `0x180078aab`
- `ole32!CoTaskMemFree` at `0x180078ab5`
- `ole32!CoTaskMemFree` at `0x180078abf`
- `ole32!CoTaskMemFree` at `0x180078ac9`
- `ole32!CoTaskMemFree` at `0x180078ad2`
- `ole32!CoTaskMemFree` at `0x180078a61`
- `ole32!CoTaskMemFree` at `0x180078a6b`
- `ole32!CoTaskMemFree` at `0x180078a75`
- `ole32!CoTaskMemFree` at `0x180078a7f`
- `ole32!CoTaskMemFree` at `0x180078a89`
- `ole32!CoTaskMemFree` at `0x180078a92`
- `ole32!CoTaskMemFree` at `0x180078aa1`
- `ole32!CoTaskMemFree` at `0x180078aab`
- `ole32!CoTaskMemFree` at `0x180078ab5`
- `ole32!CoTaskMemFree` at `0x180078abf`
- `ole32!CoTaskMemFree` at `0x180078ac9`
- `ole32!CoTaskMemFree` at `0x180078ad2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180078898`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180078898`

## pseudocode

```c
__int64 __fastcall ShieldProvider::DataProtectionShield::OnCloudBackupProviderAction(
        __int64 a1,
        unsigned int a2,
        __int64 a3)
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
  struct Shield_CloudBackupProviderInfo *v17; // rcx
  __int64 v18; // rdi
  int v19; // eax
  int v21; // [rsp+20h] [rbp-E0h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v23; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v24[16]; // [rsp+38h] [rbp-C8h] BYREF
  char v25; // [rsp+48h] [rbp-B8h]
  _BYTE v26[240]; // [rsp+50h] [rbp-B0h] BYREF

  v23 = 0;
  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(
    v24,
    a1 + 56);
  for ( i = 1; ; i = 0 )
  {
    v25 = i;
    if ( !i )
      break;
    StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)(a3 + 80), 0);
    v8 = *(const wchar_t **)(a1 + 128);
    if ( !v8 || !StringRawBuffer || _wcsicmp(v8, StringRawBuffer) )
    {
      CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v24);
      goto LABEL_29;
    }
    CommonUtil::AutoRef<IForceFieldSink>::operator=(&v23, a1 + 32);
  }
  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v24);
  v21 = 0;
  pv = 0;
  v9 = ShieldProvider::DataProtectionShield::TranslateCloudBackupProviderInfoEx(
         (struct Windows::SecurityCenter::CloudBackupProviderNamespaceDetails *)a3,
         (struct Shield_CloudBackupProviderInfo **)&pv);
  v10 = (LPVOID *)pv;
  v11 = v9;
  if ( v9 >= 0 )
  {
    updated = ShieldProvider::DataProtectionShield::UpdateCloudBackupProviders(a1, a2, pv);
    if ( updated < 0 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v14 = 57;
        goto LABEL_17;
      }
    }
    else
    {
      updated = ShieldProvider::DataProtectionShield::RefreshPillarStatusForUser(
                  (struct Shield_CloudBackupProviderInfo **)a1,
                  &v21);
      if ( updated < 0 )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v14 = 56;
LABEL_17:
          WPP_SF_d(v13[2], v14, WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids, (unsigned int)updated);
        }
      }
    }
    v15 = v23;
    if ( v23 )
    {
      ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(
        (ShieldProvider::CRPCTimeoutEx *)v26,
        0xBB8u,
        L"ShieldProvider::DataProtectionShield::OnCloudBackupProviderAction");
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
          v17 = *(struct Shield_CloudBackupProviderInfo **)(a1 + 48);
          v18 = *(_QWORD *)(a1 + 40);
          if ( v17 )
          {
            v19 = ShieldProvider::DataProtectionShield::DuplicateCloudBackupProviderInfoEx(
                    v17,
                    (struct Shield_CloudBackupProviderInfo **)&pv);
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
              L"ShieldProvider::DataProtectionShield::OnCloudBackupProviderAction");
            (*(void (__fastcall **)(__int64, __int64, LPVOID *))(*(_QWORD *)v15 + 40LL))(v15, v18, v16);
            ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx((ShieldProvider::CRPCTimeoutEx *)v26);
          }
          if ( v16 )
          {
            CoTaskMemFree(v16[3]);
            CoTaskMemFree(v16[4]);
            CoTaskMemFree(v16[5]);
            CoTaskMemFree(v16[6]);
            CoTaskMemFree(v16[7]);
            CoTaskMemFree(v16);
          }
        }
      }
    }
  }
  if ( v10 )
  {
    CoTaskMemFree(v10[3]);
    CoTaskMemFree(v10[4]);
    CoTaskMemFree(v10[5]);
    CoTaskMemFree(v10[6]);
    CoTaskMemFree(v10[7]);
    CoTaskMemFree(v10);
  }
LABEL_29:
  CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&v23);
  return 0;
}

```

## disassembly

```asm
0x180078840  mov     [rsp-8+arg_18], rbx
0x180078845  push    rbp
0x180078846  push    rsi
0x180078847  push    rdi
0x180078848  push    r12
0x18007884a  push    r13
0x18007884c  push    r14
0x18007884e  push    r15
0x180078850  lea     rbp, [rsp-50h]
0x180078855  sub     rsp, 150h
0x18007885c  mov     rax, cs:__security_cookie
0x180078863  xor     rax, rsp
0x180078866  mov     [rbp+80h+var_40], rax
0x18007886a  mov     esi, edx
0x18007886c  mov     r15, rcx
0x18007886f  lea     rdx, [rcx+38h]
0x180078873  xor     r14d, r14d
0x180078876  lea     rcx, [rsp+180h+var_148]
0x18007887b  mov     [rsp+180h+var_150], r14
0x180078880  mov     rbx, r8
0x180078883  call    ??0?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@AEBVCMpCriticalSection@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(CommonUtil::CMpCriticalSection const &,CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::ENUM_LOCK_INITIAL_STATE)
0x180078888  mov     al, 1
0x18007888a  mov     [rsp+180h+var_138], al
0x18007888e  test    al, al
0x180078890  jz      short loc_1800788DE
0x180078892  mov     rcx, [rbx+50h]; string
0x180078896  xor     edx, edx; length
0x180078898  call    cs:__imp_WindowsGetStringRawBuffer
0x18007889e  mov     rcx, [r15+80h]; String1
0x1800788a5  test    rcx, rcx
0x1800788a8  jz      short loc_1800788CF
0x1800788aa  test    rax, rax
0x1800788ad  jz      short loc_1800788CF
0x1800788af  mov     rdx, rax; String2
0x1800788b2  call    cs:__imp__wcsicmp
0x1800788b8  test    eax, eax
0x1800788ba  jnz     short loc_1800788CF
0x1800788bc  lea     rdx, [r15+20h]
0x1800788c0  lea     rcx, [rsp+180h+var_150]
0x1800788c5  call    ??4?$AutoRef@UIForceFieldSink@@@CommonUtil@@QEAAAEAV01@AEBV01@@Z; CommonUtil::AutoRef<IForceFieldSink>::operator=(CommonUtil::AutoRef<IForceFieldSink> const &)
0x1800788ca  mov     al, r14b
0x1800788cd  jmp     short loc_18007888A
0x1800788cf  lea     rcx, [rsp+180h+var_148]
0x1800788d4  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x1800788d9  jmp     loc_180078AD8
0x1800788de  lea     rcx, [rsp+180h+var_148]
0x1800788e3  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x1800788e8  lea     rdx, [rsp+180h+pv]; struct Shield_CloudBackupProviderInfo **
0x1800788ed  mov     [rsp+180h+var_160], r14d
0x1800788f2  mov     rcx, rbx; struct Windows::SecurityCenter::CloudBackupProviderNamespaceDetails *
0x1800788f5  mov     [rsp+180h+pv], r14
0x1800788fa  call    ?TranslateCloudBackupProviderInfoEx@DataProtectionShield@ShieldProvider@@CAJPEAUCloudBackupProviderNamespaceDetails@SecurityCenter@Windows@@PEAPEAUShield_CloudBackupProviderInfo@@@Z; ShieldProvider::DataProtectionShield::TranslateCloudBackupProviderInfoEx(Windows::SecurityCenter::CloudBackupProviderNamespaceDetails *,Shield_CloudBackupProviderInfo * *)
0x1800788ff  mov     r14, [rsp+180h+pv]
0x180078904  mov     r12d, eax
0x180078907  test    eax, eax
0x180078909  js      loc_180078A98
0x18007890f  mov     r8, r14
0x180078912  mov     edx, esi
0x180078914  mov     rcx, r15
0x180078917  call    ?UpdateCloudBackupProviders@DataProtectionShield@ShieldProvider@@AEAAJW4Shield_CloudBackupProviderAction@@PEAUShield_CloudBackupProviderInfo@@@Z; ShieldProvider::DataProtectionShield::UpdateCloudBackupProviders(Shield_CloudBackupProviderAction,Shield_CloudBackupProviderInfo *)
0x18007891c  mov     edi, eax
0x18007891e  test    eax, eax
0x180078920  js      short loc_180078955
0x180078922  lea     rdx, [rsp+180h+var_160]; int *
0x180078927  mov     rcx, r15; this
0x18007892a  call    ?RefreshPillarStatusForUser@DataProtectionShield@ShieldProvider@@AEAAJPEAH@Z; ShieldProvider::DataProtectionShield::RefreshPillarStatusForUser(int *)
0x18007892f  mov     edi, eax
0x180078931  test    eax, eax
0x180078933  jns     short loc_180078986
0x180078935  mov     rcx, cs:WPP_GLOBAL_Control
0x18007893c  lea     rax, WPP_GLOBAL_Control
0x180078943  cmp     rcx, rax
0x180078946  jz      short loc_180078986
0x180078948  test    byte ptr [rcx+1Ch], 1
0x18007894c  jz      short loc_180078986
0x18007894e  mov     edx, 38h ; '8'
0x180078953  jmp     short loc_180078973
0x180078955  mov     rcx, cs:WPP_GLOBAL_Control
0x18007895c  lea     rax, WPP_GLOBAL_Control
0x180078963  cmp     rcx, rax
0x180078966  jz      short loc_180078986
0x180078968  test    byte ptr [rcx+1Ch], 1
0x18007896c  jz      short loc_180078986
0x18007896e  mov     edx, 39h ; '9'
0x180078973  mov     rcx, [rcx+10h]
0x180078977  lea     r8, WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids
0x18007897e  mov     r9d, edi
0x180078981  call    WPP_SF_d
0x180078986  mov     rbx, [rsp+180h+var_150]
0x18007898b  test    rbx, rbx
0x18007898e  jz      loc_180078A98
0x180078994  lea     r8, aShieldprovider_55; "ShieldProvider::DataProtectionShield::O"...
0x18007899b  mov     edx, 0BB8h; DueTime
0x1800789a0  lea     rcx, [rsp+180h+var_130]; this
0x1800789a5  call    ??0CRPCTimeoutEx@ShieldProvider@@QEAA@KPEBG@Z; ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(ulong,ushort const *)
0x1800789aa  mov     rax, [rbx]
0x1800789ad  mov     r8, r14
0x1800789b0  mov     edx, esi
0x1800789b2  mov     rcx, rbx
0x1800789b5  mov     rax, [rax+18h]
0x1800789b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800789be  lea     rcx, [rsp+180h+var_130]; this
0x1800789c3  call    ??1CRPCTimeoutEx@ShieldProvider@@QEAA@XZ; ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx(void)
0x1800789c8  test    edi, edi
0x1800789ca  js      loc_180078A98
0x1800789d0  cmp     [rsp+180h+var_160], 0
0x1800789d5  jz      loc_180078A98
0x1800789db  xor     esi, esi
0x1800789dd  lea     rdx, [r15+38h]
0x1800789e1  lea     rcx, [rsp+180h+var_148]
0x1800789e6  mov     [rsp+180h+pv], rsi
0x1800789eb  call    ??0?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@AEBVCMpCriticalSection@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(CommonUtil::CMpCriticalSection const &,CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::ENUM_LOCK_INITIAL_STATE)
0x1800789f0  mov     rcx, [r15+30h]; struct Shield_CloudBackupProviderInfo *
0x1800789f4  mov     rdi, [r15+28h]
0x1800789f8  test    rcx, rcx
0x1800789fb  jz      short loc_180078A0F
0x1800789fd  lea     rdx, [rsp+180h+pv]; struct Shield_CloudBackupProviderInfo **
0x180078a02  call    ?DuplicateCloudBackupProviderInfoEx@DataProtectionShield@ShieldProvider@@CAJPEAUShield_CloudBackupProviderInfo@@PEAPEAU3@@Z; ShieldProvider::DataProtectionShield::DuplicateCloudBackupProviderInfoEx(Shield_CloudBackupProviderInfo *,Shield_CloudBackupProviderInfo * *)
0x180078a07  mov     rsi, [rsp+180h+pv]
0x180078a0c  mov     r12d, eax
0x180078a0f  lea     rcx, [rsp+180h+var_148]
0x180078a14  mov     [rsp+180h+var_138], 0
0x180078a19  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x180078a1e  test    r12d, r12d
0x180078a21  js      short loc_180078A58
0x180078a23  lea     r8, aShieldprovider_55; "ShieldProvider::DataProtectionShield::O"...
0x180078a2a  mov     edx, 0BB8h; DueTime
0x180078a2f  lea     rcx, [rsp+180h+var_130]; this
0x180078a34  call    ??0CRPCTimeoutEx@ShieldProvider@@QEAA@KPEBG@Z; ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(ulong,ushort const *)
0x180078a39  mov     rax, [rbx]
0x180078a3c  mov     r8, rsi
0x180078a3f  mov     rdx, rdi
0x180078a42  mov     rcx, rbx
0x180078a45  mov     rax, [rax+28h]
0x180078a49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078a4e  lea     rcx, [rsp+180h+var_130]; this
0x180078a53  call    ??1CRPCTimeoutEx@ShieldProvider@@QEAA@XZ; ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx(void)
0x180078a58  test    rsi, rsi
0x180078a5b  jz      short loc_180078A98
0x180078a5d  mov     rcx, [rsi+18h]; pv
0x180078a61  call    cs:__imp_CoTaskMemFree
0x180078a67  mov     rcx, [rsi+20h]; pv
0x180078a6b  call    cs:__imp_CoTaskMemFree
0x180078a71  mov     rcx, [rsi+28h]; pv
0x180078a75  call    cs:__imp_CoTaskMemFree
0x180078a7b  mov     rcx, [rsi+30h]; pv
0x180078a7f  call    cs:__imp_CoTaskMemFree
0x180078a85  mov     rcx, [rsi+38h]; pv
0x180078a89  call    cs:__imp_CoTaskMemFree
0x180078a8f  mov     rcx, rsi; pv
0x180078a92  call    cs:__imp_CoTaskMemFree
0x180078a98  test    r14, r14
0x180078a9b  jz      short loc_180078AD8
0x180078a9d  mov     rcx, [r14+18h]; pv
0x180078aa1  call    cs:__imp_CoTaskMemFree
0x180078aa7  mov     rcx, [r14+20h]; pv
0x180078aab  call    cs:__imp_CoTaskMemFree
0x180078ab1  mov     rcx, [r14+28h]; pv
0x180078ab5  call    cs:__imp_CoTaskMemFree
0x180078abb  mov     rcx, [r14+30h]; pv
0x180078abf  call    cs:__imp_CoTaskMemFree
0x180078ac5  mov     rcx, [r14+38h]; pv
0x180078ac9  call    cs:__imp_CoTaskMemFree
0x180078acf  mov     rcx, r14; pv
0x180078ad2  call    cs:__imp_CoTaskMemFree
0x180078ad8  lea     rcx, [rsp+180h+var_150]
0x180078add  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x180078ae2  xor     eax, eax
0x180078ae4  mov     rcx, [rbp+80h+var_40]
0x180078ae8  xor     rcx, rsp; StackCookie
0x180078aeb  call    __security_check_cookie
0x180078af0  mov     rbx, [rsp+180h+arg_18]
0x180078af8  add     rsp, 150h
0x180078aff  pop     r15
0x180078b01  pop     r14
0x180078b03  pop     r13
0x180078b05  pop     r12
0x180078b07  pop     rdi
0x180078b08  pop     rsi
0x180078b09  pop     rbp
0x180078b0a  retn
```
