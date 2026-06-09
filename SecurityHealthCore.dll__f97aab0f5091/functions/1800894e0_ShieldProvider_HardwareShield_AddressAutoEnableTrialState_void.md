# ShieldProvider::HardwareShield::AddressAutoEnableTrialState(void)

- ea: `0x1800894e0`
- end: `0x18008980d`
- name: `?AddressAutoEnableTrialState@HardwareShield@ShieldProvider@@AEAAJXZ`
- size: `813`
- prototype: `__int64 __fastcall(ShieldProvider::HardwareShield *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800bc710`

## callees

- `0x18000d7fc`
- `0x18000f02c`
- `0x18000f094`
- `0x18001c9f8`
- `0x1800894e0`
- `0x1800898e0`
- `0x1800945f8`
- `0x1800b2f6c`
- `0x1800b3980`
- `0x1800b4a00`
- `0x1800bdd14`
- `0x1800cf7bc`
- `0x1800de1bc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180089727`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800897b0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800897f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180089727`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800897b0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800897f6`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800896a7`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800896a7`

## string_xrefs

- `0x1800897da`: `onecore\amcore\antimalware\source\shieldprovider\shieldproviderservice\hardwareshield\hardwareshield.cpp`

## pseudocode

```c
__int64 __fastcall ShieldProvider::HardwareShield::AddressAutoEnableTrialState(ShieldProvider::HardwareShield *this)
{
  ShieldProvider::HardwareShield *v2; // rcx
  int IsLsaPplInAutoEnableTrialPeriod; // ebx
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  ShieldProvider::HardwareShield *v7; // rcx
  ShieldProvider::HardwareShield *v8; // rcx
  int v9; // esi
  int v10; // r12d
  int v11; // r15d
  int v12; // edi
  unsigned int v13; // r9d
  int v14; // eax
  HKEY v15; // rbx
  int v16; // eax
  ShieldProvider::HardwareShield *v17; // rcx
  unsigned int v18; // r14d
  int v19; // eax
  int v20; // [rsp+20h] [rbp-30h]
  const void *v21; // [rsp+28h] [rbp-28h]
  int v22; // [rsp+30h] [rbp-20h] BYREF
  int v23; // [rsp+34h] [rbp-1Ch] BYREF
  _BYTE v24[24]; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]
  unsigned int v26; // [rsp+98h] [rbp+48h] BYREF
  HKEY hKey; // [rsp+A0h] [rbp+50h] BYREF
  int v28; // [rsp+A8h] [rbp+58h] BYREF

  v26 = 0;
  v28 = 1;
  LODWORD(hKey) = 1;
  v22 = 0;
  v23 = 0;
  IsLsaPplInAutoEnableTrialPeriod = ShieldProvider::HardwareShield::IsLsaPplInAutoEnableTrialPeriod(this, (int *)&v26);
  if ( IsLsaPplInAutoEnableTrialPeriod < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return (unsigned int)IsLsaPplInAutoEnableTrialPeriod;
    v5 = 382;
LABEL_5:
    WPP_SF_d(v4[2], v5, &WPP_60a6be03328e3dc19e58859635691dd5_Traceguids, (unsigned int)IsLsaPplInAutoEnableTrialPeriod);
    return (unsigned int)IsLsaPplInAutoEnableTrialPeriod;
  }
  IsLsaPplInAutoEnableTrialPeriod = ShieldProvider::HardwareShield::WasPplConfigured(v2, (int *)&hKey);
  if ( IsLsaPplInAutoEnableTrialPeriod < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return (unsigned int)IsLsaPplInAutoEnableTrialPeriod;
    v5 = 383;
    goto LABEL_5;
  }
  if ( v26 || (_DWORD)hKey )
    return 0;
  IsLsaPplInAutoEnableTrialPeriod = ShieldProvider::HardwareShield::IsHvciCapable(this, &v28, &v26);
  if ( IsLsaPplInAutoEnableTrialPeriod < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return (unsigned int)IsLsaPplInAutoEnableTrialPeriod;
    v5 = 384;
    goto LABEL_5;
  }
  IsLsaPplInAutoEnableTrialPeriod = ShieldProvider::HardwareShield::IsClientSku(v7, &v22);
  if ( IsLsaPplInAutoEnableTrialPeriod < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return (unsigned int)IsLsaPplInAutoEnableTrialPeriod;
    v5 = 385;
    goto LABEL_5;
  }
  IsLsaPplInAutoEnableTrialPeriod = ShieldProvider::HardwareShield::CheckUnsignedDllLoads(v8, &v23);
  if ( IsLsaPplInAutoEnableTrialPeriod < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return (unsigned int)IsLsaPplInAutoEnableTrialPeriod;
    v5 = 386;
    goto LABEL_5;
  }
  if ( !v23 && v28 && v22 )
  {
    v9 = 1;
LABEL_29:
    v10 = 0;
    goto LABEL_30;
  }
  v9 = 0;
  if ( !v23 )
    goto LABEL_29;
  v10 = 16;
LABEL_30:
  v11 = v28 != 0 ? 0 : 8;
  v12 = v22 != 0 ? 0 : 0x20;
  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(
    v24,
    &stru_18013A040);
  if ( ShieldProvider::HardwareShield::m_lsaPplSubscription )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion();
    ShieldProvider::HardwareShield::m_lsaPplSubscription = 0;
  }
  v24[16] = 0;
  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v24);
  hKey = 0;
  v14 = ShieldProvider::ShieldUtilRegOpenKey(
          (ShieldProvider *)&hKey,
          (HKEY *)L"System\\CurrentControlSet\\Control\\Lsa",
          (const unsigned __int16 *)0x20006,
          v13);
  IsLsaPplInAutoEnableTrialPeriod = v14;
  if ( v14 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        387,
        &WPP_60a6be03328e3dc19e58859635691dd5_Traceguids,
        (unsigned int)v14);
    if ( hKey )
      RegCloseKey(hKey);
    return (unsigned int)IsLsaPplInAutoEnableTrialPeriod;
  }
  v15 = hKey;
  v26 = 2 * v9;
  v16 = CommonUtil::UtilRegSetValueInternal(
          (CommonUtil *)hKey,
          (HKEY)L"RunAsPPL",
          (const unsigned __int16 *)4,
          4u,
          (unsigned __int64)&v26,
          v21);
  v18 = v16;
  if ( v16 >= 0 )
  {
    v19 = ShieldProvider::HardwareShield::AutoEnableRegKeyCleanUp(v17, v10 | v11 | v12 | (2 * (v9 ^ 1u) + 2));
    if ( v19 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x15C8,
        (unsigned int)"onecore\\amcore\\antimalware\\source\\shieldprovider\\shieldproviderservice\\hardwareshield\\hardwareshield.cpp",
        (const char *)(unsigned int)v19,
        v20);
    if ( v15 )
      RegCloseKey(v15);
    return 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      388,
      &WPP_60a6be03328e3dc19e58859635691dd5_Traceguids,
      (unsigned int)v16);
  if ( v15 )
    RegCloseKey(v15);
  return v18;
}

```

## disassembly

```asm
0x1800894e0  push    rbp
0x1800894e2  push    rbx
0x1800894e3  push    rsi
0x1800894e4  push    rdi
0x1800894e5  push    r12
0x1800894e7  push    r14
0x1800894e9  push    r15
0x1800894eb  mov     rbp, rsp
0x1800894ee  sub     rsp, 50h
0x1800894f2  mov     r14d, 1
0x1800894f8  mov     [rbp+arg_8], 0
0x1800894ff  lea     rdx, [rbp+arg_8]; int *
0x180089503  mov     [rbp+arg_18], r14d
0x180089507  mov     dword ptr [rbp+hKey], r14d
0x18008950b  mov     rdi, rcx
0x18008950e  mov     [rbp+var_20], 0
0x180089515  mov     [rbp+var_1C], 0
0x18008951c  call    ?IsLsaPplInAutoEnableTrialPeriod@HardwareShield@ShieldProvider@@AEAAJPEAH@Z; ShieldProvider::HardwareShield::IsLsaPplInAutoEnableTrialPeriod(int *)
0x180089521  mov     ebx, eax
0x180089523  test    eax, eax
0x180089525  jns     short loc_18008955F
0x180089527  mov     rcx, cs:WPP_GLOBAL_Control
0x18008952e  lea     rdx, WPP_GLOBAL_Control
0x180089535  cmp     rcx, rdx
0x180089538  jz      short loc_180089558
0x18008953a  test    [rcx+1Ch], r14b
0x18008953e  jz      short loc_180089558
0x180089540  mov     edx, 17Eh
0x180089545  mov     rcx, [rcx+10h]
0x180089549  lea     r8, WPP_60a6be03328e3dc19e58859635691dd5_Traceguids
0x180089550  mov     r9d, ebx
0x180089553  call    WPP_SF_d
0x180089558  mov     eax, ebx
0x18008955a  jmp     loc_1800897FE
0x18008955f  lea     rdx, [rbp+hKey]; int *
0x180089563  call    ?WasPplConfigured@HardwareShield@ShieldProvider@@AEAAJPEAH@Z; ShieldProvider::HardwareShield::WasPplConfigured(int *)
0x180089568  mov     ebx, eax
0x18008956a  test    eax, eax
0x18008956c  jns     short loc_18008958E
0x18008956e  mov     rcx, cs:WPP_GLOBAL_Control
0x180089575  lea     rdx, WPP_GLOBAL_Control
0x18008957c  cmp     rcx, rdx
0x18008957f  jz      short loc_180089558
0x180089581  test    [rcx+1Ch], r14b
0x180089585  jz      short loc_180089558
0x180089587  mov     edx, 17Fh
0x18008958c  jmp     short loc_180089545
0x18008958e  cmp     [rbp+arg_8], 0
0x180089592  jnz     loc_1800897FC
0x180089598  cmp     dword ptr [rbp+hKey], 0
0x18008959c  jnz     loc_1800897FC
0x1800895a2  lea     r8, [rbp+arg_8]; unsigned int *
0x1800895a6  mov     rcx, rdi; this
0x1800895a9  lea     rdx, [rbp+arg_18]; int *
0x1800895ad  call    ?IsHvciCapable@HardwareShield@ShieldProvider@@UEAAJPEAHPEAI@Z; ShieldProvider::HardwareShield::IsHvciCapable(int *,uint *)
0x1800895b2  mov     ebx, eax
0x1800895b4  test    eax, eax
0x1800895b6  jns     short loc_1800895DB
0x1800895b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800895bf  lea     rdx, WPP_GLOBAL_Control
0x1800895c6  cmp     rcx, rdx
0x1800895c9  jz      short loc_180089558
0x1800895cb  test    [rcx+1Ch], r14b
0x1800895cf  jz      short loc_180089558
0x1800895d1  mov     edx, 180h
0x1800895d6  jmp     loc_180089545
0x1800895db  lea     rdx, [rbp+var_20]; int *
0x1800895df  call    ?IsClientSku@HardwareShield@ShieldProvider@@AEAAJPEAH@Z; ShieldProvider::HardwareShield::IsClientSku(int *)
0x1800895e4  mov     ebx, eax
0x1800895e6  test    eax, eax
0x1800895e8  jns     short loc_180089615
0x1800895ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800895f1  lea     rdx, WPP_GLOBAL_Control
0x1800895f8  cmp     rcx, rdx
0x1800895fb  jz      loc_180089558
0x180089601  test    [rcx+1Ch], r14b
0x180089605  jz      loc_180089558
0x18008960b  mov     edx, 181h
0x180089610  jmp     loc_180089545
0x180089615  lea     rdx, [rbp+var_1C]; int *
0x180089619  call    ?CheckUnsignedDllLoads@HardwareShield@ShieldProvider@@AEAAJPEAH@Z; ShieldProvider::HardwareShield::CheckUnsignedDllLoads(int *)
0x18008961e  mov     ebx, eax
0x180089620  test    eax, eax
0x180089622  jns     short loc_18008964F
0x180089624  mov     rcx, cs:WPP_GLOBAL_Control
0x18008962b  lea     rdx, WPP_GLOBAL_Control
0x180089632  cmp     rcx, rdx
0x180089635  jz      loc_180089558
0x18008963b  test    [rcx+1Ch], r14b
0x18008963f  jz      loc_180089558
0x180089645  mov     edx, 182h
0x18008964a  jmp     loc_180089545
0x18008964f  mov     eax, [rbp+var_1C]
0x180089652  mov     ecx, [rbp+arg_18]
0x180089655  mov     edx, [rbp+var_20]
0x180089658  test    eax, eax
0x18008965a  jnz     loc_180089732
0x180089660  test    ecx, ecx
0x180089662  jz      loc_180089732
0x180089668  test    edx, edx
0x18008966a  jz      loc_180089732
0x180089670  mov     esi, r14d
0x180089673  xor     r12d, r12d
0x180089676  neg     ecx
0x180089678  lea     rcx, [rbp+var_18]
0x18008967c  sbb     r15d, r15d
0x18008967f  not     r15d
0x180089682  and     r15d, 8
0x180089686  neg     edx
0x180089688  lea     rdx, stru_18013A040
0x18008968f  sbb     edi, edi
0x180089691  not     edi
0x180089693  and     edi, 20h
0x180089696  call    ??0?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@AEBVCMpCriticalSection@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(CommonUtil::CMpCriticalSection const &,CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::ENUM_LOCK_INITIAL_STATE)
0x18008969b  mov     rcx, cs:?m_lsaPplSubscription@HardwareShield@ShieldProvider@@0PEAU_WNF_USER_SUBSCRIPTION@@EA; _WNF_USER_SUBSCRIPTION * ShieldProvider::HardwareShield::m_lsaPplSubscription
0x1800896a2  test    rcx, rcx
0x1800896a5  jz      short loc_1800896B8
0x1800896a7  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x1800896ad  mov     cs:?m_lsaPplSubscription@HardwareShield@ShieldProvider@@0PEAU_WNF_USER_SUBSCRIPTION@@EA, 0; _WNF_USER_SUBSCRIPTION * ShieldProvider::HardwareShield::m_lsaPplSubscription
0x1800896b8  lea     rcx, [rbp+var_18]
0x1800896bc  mov     [rbp+var_8], 0
0x1800896c0  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x1800896c5  mov     r8d, 20006h; unsigned __int16 *
0x1800896cb  mov     [rbp+hKey], 0
0x1800896d3  lea     rdx, aSystemCurrentc_5; "System\\CurrentControlSet\\Control\\Lsa"
0x1800896da  lea     rcx, [rbp+hKey]; this
0x1800896de  call    ?ShieldUtilRegOpenKey@ShieldProvider@@YAJPEAPEAUHKEY__@@PEBGK@Z; ShieldProvider::ShieldUtilRegOpenKey(HKEY__ * *,ushort const *,ulong)
0x1800896e3  mov     ebx, eax
0x1800896e5  test    eax, eax
0x1800896e7  jns     short loc_180089745
0x1800896e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800896f0  lea     rdx, WPP_GLOBAL_Control
0x1800896f7  cmp     rcx, rdx
0x1800896fa  jz      short loc_18008971A
0x1800896fc  test    [rcx+1Ch], r14b
0x180089700  jz      short loc_18008971A
0x180089702  mov     rcx, [rcx+10h]
0x180089706  lea     r8, WPP_60a6be03328e3dc19e58859635691dd5_Traceguids
0x18008970d  mov     edx, 183h
0x180089712  mov     r9d, eax
0x180089715  call    WPP_SF_d
0x18008971a  mov     rcx, [rbp+hKey]; hKey
0x18008971e  test    rcx, rcx
0x180089721  jz      loc_180089558
0x180089727  call    cs:__imp_RegCloseKey
0x18008972d  jmp     loc_180089558
0x180089732  xor     esi, esi
0x180089734  test    eax, eax
0x180089736  jz      loc_180089673
0x18008973c  lea     r12d, [rsi+10h]
0x180089740  jmp     loc_180089676
0x180089745  mov     rbx, [rbp+hKey]
0x180089749  lea     eax, [rsi+rsi]
0x18008974c  mov     [rbp+arg_8], eax
0x18008974f  lea     rdx, aRunasppl; "RunAsPPL"
0x180089756  mov     r8d, 4; unsigned __int16 *
0x18008975c  lea     rax, [rbp+arg_8]
0x180089760  mov     r9d, r8d; unsigned int
0x180089763  mov     [rsp+50h+var_30], rax; int
0x180089768  mov     rcx, rbx; this
0x18008976b  call    ?UtilRegSetValueInternal@CommonUtil@@YAJPEAUHKEY__@@PEBGK_KPEBX@Z; CommonUtil::UtilRegSetValueInternal(HKEY__ *,ushort const *,ulong,unsigned __int64,void const *)
0x180089770  mov     r14d, eax
0x180089773  test    eax, eax
0x180089775  jns     short loc_1800897BB
0x180089777  mov     rcx, cs:WPP_GLOBAL_Control
0x18008977e  lea     rdx, WPP_GLOBAL_Control
0x180089785  cmp     rcx, rdx
0x180089788  jz      short loc_1800897A8
0x18008978a  test    byte ptr [rcx+1Ch], 1
0x18008978e  jz      short loc_1800897A8
0x180089790  mov     rcx, [rcx+10h]
0x180089794  lea     r8, WPP_60a6be03328e3dc19e58859635691dd5_Traceguids
0x18008979b  mov     edx, 184h
0x1800897a0  mov     r9d, eax
0x1800897a3  call    WPP_SF_d
0x1800897a8  test    rbx, rbx
0x1800897ab  jz      short loc_1800897B6
0x1800897ad  mov     rcx, rbx; hKey
0x1800897b0  call    cs:__imp_RegCloseKey
0x1800897b6  mov     eax, r14d
0x1800897b9  jmp     short loc_1800897FE
0x1800897bb  xor     esi, 1
0x1800897be  or      edi, r15d
0x1800897c1  or      edi, r12d
0x1800897c4  lea     edx, ds:2[rsi*2]
0x1800897cb  or      edx, edi; unsigned int
0x1800897cd  call    ?AutoEnableRegKeyCleanUp@HardwareShield@ShieldProvider@@AEAAJK@Z; ShieldProvider::HardwareShield::AutoEnableRegKeyCleanUp(ulong)
0x1800897d2  test    eax, eax
0x1800897d4  jns     short loc_1800897EE
0x1800897d6  mov     rcx, [rbp+38h]; this
0x1800897da  lea     r8, aOnecoreAmcoreA_0; "onecore\\amcore\\antimalware\\source\\s"...
0x1800897e1  mov     r9d, eax; char *
0x1800897e4  mov     edx, 15C8h; void *
0x1800897e9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800897ee  test    rbx, rbx
0x1800897f1  jz      short loc_1800897FC
0x1800897f3  mov     rcx, rbx; hKey
0x1800897f6  call    cs:__imp_RegCloseKey
0x1800897fc  xor     eax, eax
0x1800897fe  add     rsp, 50h
0x180089802  pop     r15
0x180089804  pop     r14
0x180089806  pop     r12
0x180089808  pop     rdi
0x180089809  pop     rsi
0x18008980a  pop     rbx
0x18008980b  pop     rbp
0x18008980c  retn
```
