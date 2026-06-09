# ShieldProvider::DataProtectionShield::OnWscServiceStatusChanged(void)

- ea: `0x18007913c`
- end: `0x180079620`
- name: `?OnWscServiceStatusChanged@DataProtectionShield@ShieldProvider@@QEAAJXZ`
- size: `1252`
- prototype: `__int64 __fastcall(ShieldProvider::DataProtectionShield *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `service_task, broker_com_uri`

## callers

- `0x180079630`

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
- `0x180076604`
- `0x180077ff4`
- `0x18007913c`
- `0x18007963c`
- `0x180079d48`
- `0x18007ac88`
- `0x1800d3b3c`
- `0x1800d3bf4`
- `0x1800e3e8c`
- `0x1800e7010`

## import_xrefs

- `KERNEL32!Sleep` at `0x18007935a`
- `KERNEL32!Sleep` at `0x18007935a`
- `ole32!CoTaskMemFree` at `0x18007924b`
- `ole32!CoTaskMemFree` at `0x180079255`
- `ole32!CoTaskMemFree` at `0x18007925f`
- `ole32!CoTaskMemFree` at `0x180079269`
- `ole32!CoTaskMemFree` at `0x180079273`
- `ole32!CoTaskMemFree` at `0x18007927c`
- `ole32!CoTaskMemFree` at `0x18007924b`
- `ole32!CoTaskMemFree` at `0x180079255`
- `ole32!CoTaskMemFree` at `0x18007925f`
- `ole32!CoTaskMemFree` at `0x180079269`
- `ole32!CoTaskMemFree` at `0x180079273`
- `ole32!CoTaskMemFree` at `0x18007927c`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x1800792f8`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x1800792f8`

## string_xrefs

- `0x1800791da`: `ShieldProvider::DataProtectionShield::OnWscServiceStatusChanged`
- `0x180079206`: `ShieldProvider::DataProtectionShield::OnWscServiceStatusChanged`
- `0x1800793e8`: `ShieldProvider::DataProtectionShield::OnWscServiceStatusChanged`
- `0x18007949e`: `ShieldProvider::DataProtectionShield::OnWscServiceStatusChanged`
- `0x1800794eb`: `ShieldProvider::DataProtectionShield::OnWscServiceStatusChanged`
- `0x18007957d`: `ShieldProvider::DataProtectionShield::OnWscServiceStatusChanged`
- `0x1800792d2`: `Windows.SecurityCenter.WscBrokerManager`

## pseudocode

```c
__int64 __fastcall ShieldProvider::DataProtectionShield::OnWscServiceStatusChanged(
        ShieldProvider::WscBrokerSink **this)
{
  unsigned int v2; // r13d
  char v3; // di
  __int64 v4; // rbx
  int IsWscServiceRunning; // r14d
  struct ShieldProvider::DataProtectionShield *v6; // rdx
  LPVOID *v7; // rdi
  _QWORD *v8; // rdi
  int v9; // r15d
  __int64 v10; // rcx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  _QWORD *v14; // r15
  ShieldProvider::WscBrokerSink *v15; // rcx
  int v16; // eax
  int v17; // eax
  int v18; // eax
  __int64 v19; // rbx
  int v20; // eax
  char v22; // [rsp+30h] [rbp-D0h]
  bool v23; // [rsp+31h] [rbp-CFh] BYREF
  int v24[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v25; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v26; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v27[24]; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp-98h] BYREF
  __int64 v29; // [rsp+80h] [rbp-80h]
  _BYTE v30[240]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v31[240]; // [rsp+180h] [rbp+80h] BYREF

  v2 = 0;
  v3 = 0;
  v26 = 0;
  v4 = 0;
  v22 = 0;
  v25 = 0;
  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(
    v27,
    this + 7);
  v23 = 0;
  IsWscServiceRunning = ShieldProvider::DataProtectionShield::GetIsWscServiceRunning(
                          (ShieldProvider::DataProtectionShield *)this,
                          &v23);
  if ( IsWscServiceRunning < 0 )
    goto LABEL_38;
  CommonUtil::AutoRef<IForceFieldSink>::operator=(&v26, this + 4);
  if ( !v23 )
  {
    if ( this[3] )
    {
      ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(
        (ShieldProvider::CRPCTimeoutEx *)v31,
        0x3E8u,
        L"ShieldProvider::DataProtectionShield::OnWscServiceStatusChanged");
      ShieldProvider::WscBrokerSink::SetParent(this[3], v6);
      ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx((ShieldProvider::CRPCTimeoutEx *)v31);
    }
    this[2] = 0;
    ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(
      (ShieldProvider::CRPCTimeoutEx *)v30,
      0x3E8u,
      L"ShieldProvider::DataProtectionShield::OnWscServiceStatusChanged");
    CommonUtil::AutoRef<IHardwareShield16>::operator=(this + 2);
    CommonUtil::AutoRef<ICrossContainerCommunicationManager>::operator=(this + 3);
    *((_DWORD *)this + 10) = 128;
    *((_DWORD *)this + 11) = 1;
    v7 = (LPVOID *)this[6];
    if ( v7 )
    {
      CoTaskMemFree(v7[3]);
      CoTaskMemFree(v7[4]);
      CoTaskMemFree(v7[5]);
      CoTaskMemFree(v7[6]);
      CoTaskMemFree(v7[7]);
      CoTaskMemFree(v7);
      this[6] = 0;
    }
    v3 = 1;
    ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx((ShieldProvider::CRPCTimeoutEx *)v30);
    goto LABEL_38;
  }
  v8 = this + 2;
  if ( this[2] )
  {
    v3 = 0;
    goto LABEL_38;
  }
  v9 = 0;
  while ( 1 )
  {
    if ( *v8 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v8 + 16LL))(*v8);
      *v8 = 0;
    }
    v29 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.SecurityCenter.WscBrokerManager",
      0x28u,
      0x27u);
    v10 = v29;
    *v8 = 0;
    *(_QWORD *)v24 = 0;
    IsWscServiceRunning = RoActivateInstance(v10, v24);
    if ( IsWscServiceRunning < 0 )
      goto LABEL_15;
    if ( !memcmp_0(&GUID_b529b7f5_76aa_431f_ad7f_1272feedff07, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
      break;
    IsWscServiceRunning = (***(__int64 (__fastcall ****)(_QWORD, GUID *, char *))v24)(
                            *(_QWORD *)v24,
                            &GUID_b529b7f5_76aa_431f_ad7f_1272feedff07,
                            (char *)this + 16);
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v24 + 16LL))(*(_QWORD *)v24);
LABEL_15:
    if ( IsWscServiceRunning >= 0 )
      goto LABEL_21;
    Sleep(0x3E8u);
    if ( (unsigned int)++v9 >= 5 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v12 = 53;
        v13 = (unsigned int)IsWscServiceRunning;
LABEL_33:
        WPP_SF_d(v11[2], v12, WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids, v13);
        goto LABEL_34;
      }
      goto LABEL_34;
    }
  }
  *v8 = *(_QWORD *)v24;
LABEL_21:
  v14 = this + 3;
  *(_QWORD *)v24 = this;
  v15 = this[3];
  if ( v15 )
  {
    (*(void (__fastcall **)(ShieldProvider::WscBrokerSink *))(*(_QWORD *)v15 + 16LL))(v15);
    *v14 = 0;
  }
  v16 = Microsoft::WRL::Details::MakeAndInitialize<ShieldProvider::WscBrokerSink,ShieldProvider::WscBrokerSink,ShieldProvider::DataProtectionShield *>(
          this + 3,
          v24);
  IsWscServiceRunning = v16;
  if ( v16 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v12 = 52;
      v13 = (unsigned int)v16;
      goto LABEL_33;
    }
  }
  else
  {
    CommonUtil::AutoRef<IForceFieldSink>::operator=(&v25, this + 2);
    ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(
      (ShieldProvider::CRPCTimeoutEx *)v30,
      0xBB8u,
      L"ShieldProvider::DataProtectionShield::OnWscServiceStatusChanged");
    v17 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, char *))(*(_QWORD *)*v8 + 64LL))(*v8, *v14, (char *)this + 120);
    IsWscServiceRunning = v17;
    if ( v17 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          51,
          WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids,
          (unsigned int)v17);
    }
    else
    {
      v2 = 1;
      v22 = 1;
    }
    ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx((ShieldProvider::CRPCTimeoutEx *)v30);
    v4 = v25;
  }
LABEL_34:
  if ( IsWscServiceRunning < 0 )
  {
    ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(
      (ShieldProvider::CRPCTimeoutEx *)v30,
      0x3E8u,
      L"ShieldProvider::DataProtectionShield::OnWscServiceStatusChanged");
    CommonUtil::AutoRef<IHardwareShield16>::operator=(this + 2);
    CommonUtil::AutoRef<ICrossContainerCommunicationManager>::operator=(this + 3);
    ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx((ShieldProvider::CRPCTimeoutEx *)v30);
  }
  v3 = v22;
LABEL_38:
  v27[16] = 0;
  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v27);
  if ( v4 )
  {
    ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(
      (ShieldProvider::CRPCTimeoutEx *)v30,
      0xBB8u,
      L"ShieldProvider::DataProtectionShield::OnWscServiceStatusChanged");
    v18 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 56LL))(v4);
    if ( v18 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        54,
        WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids,
        (unsigned int)v18);
    ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx((ShieldProvider::CRPCTimeoutEx *)v30);
  }
  if ( IsWscServiceRunning >= 0
    && v2
    && (int)ShieldProvider::DataProtectionShield::PopulateCloudBackupProviders((ShieldProvider::DataProtectionShield *)this) >= 0 )
  {
    ShieldProvider::DataProtectionShield::RefreshPillarStatusForUser(this, v24);
  }
  v19 = v26;
  if ( v26 && IsWscServiceRunning >= 0 && v3 )
  {
    ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(
      (ShieldProvider::CRPCTimeoutEx *)v30,
      0xBB8u,
      L"ShieldProvider::DataProtectionShield::OnWscServiceStatusChanged");
    v20 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v19 + 32LL))(v19, v2);
    if ( v20 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids, v2, v20);
    ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx((ShieldProvider::CRPCTimeoutEx *)v30);
  }
  CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&v25);
  CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&v26);
  return 0;
}

```

## disassembly

```asm
0x18007913c  mov     [rsp-8+arg_8], rbx
0x180079141  mov     [rsp-8+arg_10], rsi
0x180079146  push    rbp
0x180079147  push    rdi
0x180079148  push    r13
0x18007914a  push    r14
0x18007914c  push    r15
0x18007914e  lea     rbp, [rsp-180h]
0x180079156  sub     rsp, 280h
0x18007915d  mov     rax, cs:__security_cookie
0x180079164  xor     rax, rsp
0x180079167  mov     [rbp+1A0h+var_30], rax
0x18007916e  mov     rsi, rcx
0x180079171  lea     rdx, [rcx+38h]
0x180079175  xor     r13d, r13d
0x180079178  lea     rcx, [rsp+2A0h+var_250]
0x18007917d  xor     dil, dil
0x180079180  mov     [rsp+2A0h+var_258], r13
0x180079185  xor     ebx, ebx
0x180079187  mov     [rsp+2A0h+var_270], dil
0x18007918c  mov     [rsp+2A0h+var_260], rbx
0x180079191  call    ??0?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@AEBVCMpCriticalSection@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(CommonUtil::CMpCriticalSection const &,CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::ENUM_LOCK_INITIAL_STATE)
0x180079196  lea     rdx, [rsp+2A0h+var_26F]; bool *
0x18007919b  mov     [rsp+2A0h+var_26F], bl
0x18007919f  mov     rcx, rsi; this
0x1800791a2  call    ?GetIsWscServiceRunning@DataProtectionShield@ShieldProvider@@AEAAJPEA_N@Z; ShieldProvider::DataProtectionShield::GetIsWscServiceRunning(bool *)
0x1800791a7  lea     r15, WPP_GLOBAL_Control
0x1800791ae  mov     r14d, eax
0x1800791b1  test    eax, eax
0x1800791b3  js      loc_1800794D7
0x1800791b9  lea     rdx, [rsi+20h]
0x1800791bd  lea     rcx, [rsp+2A0h+var_258]
0x1800791c2  call    ??4?$AutoRef@UIForceFieldSink@@@CommonUtil@@QEAAAEAV01@AEBV01@@Z; CommonUtil::AutoRef<IForceFieldSink>::operator=(CommonUtil::AutoRef<IForceFieldSink> const &)
0x1800791c7  cmp     [rsp+2A0h+var_26F], bl
0x1800791cb  jnz     loc_18007929E
0x1800791d1  lea     r15, [rsi+18h]
0x1800791d5  cmp     [r15], rbx
0x1800791d8  jz      short loc_180079206
0x1800791da  lea     r8, aShieldprovider_30; "ShieldProvider::DataProtectionShield::O"...
0x1800791e1  mov     edx, 3E8h; DueTime
0x1800791e6  lea     rcx, [rbp+1A0h+var_120]; this
0x1800791ed  call    ??0CRPCTimeoutEx@ShieldProvider@@QEAA@KPEBG@Z; ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(ulong,ushort const *)
0x1800791f2  mov     rcx, [r15]; this
0x1800791f5  call    ?SetParent@WscBrokerSink@ShieldProvider@@QEAAXPEAVDataProtectionShield@2@@Z; ShieldProvider::WscBrokerSink::SetParent(ShieldProvider::DataProtectionShield *)
0x1800791fa  lea     rcx, [rbp+1A0h+var_120]; this
0x180079201  call    ??1CRPCTimeoutEx@ShieldProvider@@QEAA@XZ; ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx(void)
0x180079206  lea     r8, aShieldprovider_30; "ShieldProvider::DataProtectionShield::O"...
0x18007920d  mov     [rsi+10h], rbx
0x180079211  mov     edx, 3E8h; DueTime
0x180079216  lea     rcx, [rbp+1A0h+var_210]; this
0x18007921a  call    ??0CRPCTimeoutEx@ShieldProvider@@QEAA@KPEBG@Z; ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(ulong,ushort const *)
0x18007921f  lea     rcx, [rsi+10h]
0x180079223  call    ??4?$AutoRef@UIHardwareShield16@@@CommonUtil@@QEAAAEAV01@PEAUIHardwareShield16@@@Z; CommonUtil::AutoRef<IHardwareShield16>::operator=(IHardwareShield16 *)
0x180079228  mov     rcx, r15
0x18007922b  call    ??4?$AutoRef@UICrossContainerCommunicationManager@@@CommonUtil@@QEAAAEAV01@PEAUICrossContainerCommunicationManager@@@Z; CommonUtil::AutoRef<ICrossContainerCommunicationManager>::operator=(ICrossContainerCommunicationManager *)
0x180079230  mov     dword ptr [rsi+28h], 80h
0x180079237  mov     dword ptr [rsi+2Ch], 1
0x18007923e  mov     rdi, [rsi+30h]
0x180079242  test    rdi, rdi
0x180079245  jz      short loc_180079286
0x180079247  mov     rcx, [rdi+18h]; pv
0x18007924b  call    cs:__imp_CoTaskMemFree
0x180079251  mov     rcx, [rdi+20h]; pv
0x180079255  call    cs:__imp_CoTaskMemFree
0x18007925b  mov     rcx, [rdi+28h]; pv
0x18007925f  call    cs:__imp_CoTaskMemFree
0x180079265  mov     rcx, [rdi+30h]; pv
0x180079269  call    cs:__imp_CoTaskMemFree
0x18007926f  mov     rcx, [rdi+38h]; pv
0x180079273  call    cs:__imp_CoTaskMemFree
0x180079279  mov     rcx, rdi; pv
0x18007927c  call    cs:__imp_CoTaskMemFree
0x180079282  mov     [rsi+30h], rbx
0x180079286  lea     rcx, [rbp+1A0h+var_210]; this
0x18007928a  mov     dil, 1
0x18007928d  call    ??1CRPCTimeoutEx@ShieldProvider@@QEAA@XZ; ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx(void)
0x180079292  lea     r15, WPP_GLOBAL_Control
0x180079299  jmp     loc_1800794D7
0x18007929e  lea     rdi, [rsi+10h]
0x1800792a2  cmp     [rdi], rbx
0x1800792a5  jnz     loc_1800794D4
0x1800792ab  xor     r15d, r15d
0x1800792ae  mov     rcx, [rdi]
0x1800792b1  xor     r14d, r14d
0x1800792b4  test    rcx, rcx
0x1800792b7  jz      short loc_1800792C8
0x1800792b9  mov     rax, [rcx]
0x1800792bc  mov     rax, [rax+10h]
0x1800792c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800792c5  mov     [rdi], r14
0x1800792c8  mov     r9d, 27h ; '''; unsigned int
0x1800792ce  mov     [rbp+1A0h+var_220], r14
0x1800792d2  lea     rdx, ?RuntimeClass_Windows_SecurityCenter_WscBrokerManager@@3QBGB; "Windows.SecurityCenter.WscBrokerManager"
0x1800792d9  lea     rcx, [rsp+2A0h+hstringHeader]; hstringHeader
0x1800792de  lea     r8d, [r9+1]; unsigned int
0x1800792e2  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800792e7  mov     rcx, [rbp+1A0h+var_220]
0x1800792eb  lea     rdx, [rsp+2A0h+var_268]
0x1800792f0  mov     [rdi], r14
0x1800792f3  mov     qword ptr [rsp+2A0h+var_268], r14
0x1800792f8  call    cs:__imp_RoActivateInstance
0x1800792fe  mov     r14d, eax
0x180079301  test    eax, eax
0x180079303  js      short loc_180079350
0x180079305  mov     r8d, 10h; Size
0x18007930b  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x180079312  lea     rcx, _GUID_b529b7f5_76aa_431f_ad7f_1272feedff07; Buf1
0x180079319  call    memcmp_0
0x18007931e  test    eax, eax
0x180079320  jz      short loc_18007939B
0x180079322  mov     rcx, qword ptr [rsp+2A0h+var_268]
0x180079327  lea     rdx, _GUID_b529b7f5_76aa_431f_ad7f_1272feedff07
0x18007932e  mov     r8, rdi
0x180079331  mov     rax, [rcx]
0x180079334  mov     rax, [rax]
0x180079337  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007933c  mov     rcx, qword ptr [rsp+2A0h+var_268]
0x180079341  mov     r14d, eax
0x180079344  mov     rax, [rcx]
0x180079347  mov     rax, [rax+10h]
0x18007934b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079350  test    r14d, r14d
0x180079353  jns     short loc_1800793A3
0x180079355  mov     ecx, 3E8h; dwMilliseconds
0x18007935a  call    cs:__imp_Sleep
0x180079360  inc     r15d
0x180079363  cmp     r15d, 5
0x180079367  jb      loc_1800792AE
0x18007936d  mov     rcx, cs:WPP_GLOBAL_Control
0x180079374  lea     r15, WPP_GLOBAL_Control
0x18007937b  cmp     rcx, r15
0x18007937e  jz      loc_180079499
0x180079384  test    byte ptr [rcx+1Ch], 1
0x180079388  jz      loc_180079499
0x18007938e  mov     edx, 35h ; '5'
0x180079393  mov     r9d, r14d
0x180079396  jmp     loc_180079489
0x18007939b  mov     rax, qword ptr [rsp+2A0h+var_268]
0x1800793a0  mov     [rdi], rax
0x1800793a3  lea     r15, [rsi+18h]
0x1800793a7  mov     qword ptr [rsp+2A0h+var_268], rsi
0x1800793ac  mov     rcx, [r15]
0x1800793af  test    rcx, rcx
0x1800793b2  jz      short loc_1800793C3
0x1800793b4  mov     rax, [rcx]
0x1800793b7  mov     rax, [rax+10h]
0x1800793bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800793c0  mov     [r15], rbx
0x1800793c3  lea     rdx, [rsp+2A0h+var_268]
0x1800793c8  mov     rcx, r15
0x1800793cb  call    ??$MakeAndInitialize@VWscBrokerSink@ShieldProvider@@V12@PEAVDataProtectionShield@2@@Details@WRL@Microsoft@@YAJPEAPEAVWscBrokerSink@ShieldProvider@@$$QEAPEAVDataProtectionShield@4@@Z; Microsoft::WRL::Details::MakeAndInitialize<ShieldProvider::WscBrokerSink,ShieldProvider::WscBrokerSink,ShieldProvider::DataProtectionShield *>(ShieldProvider::WscBrokerSink * *,ShieldProvider::DataProtectionShield * &&)
0x1800793d0  mov     r14d, eax
0x1800793d3  test    eax, eax
0x1800793d5  js      loc_180079468
0x1800793db  mov     rdx, rdi
0x1800793de  lea     rcx, [rsp+2A0h+var_260]
0x1800793e3  call    ??4?$AutoRef@UIForceFieldSink@@@CommonUtil@@QEAAAEAV01@AEBV01@@Z; CommonUtil::AutoRef<IForceFieldSink>::operator=(CommonUtil::AutoRef<IForceFieldSink> const &)
0x1800793e8  lea     r8, aShieldprovider_30; "ShieldProvider::DataProtectionShield::O"...
0x1800793ef  mov     edx, 0BB8h; DueTime
0x1800793f4  lea     rcx, [rbp+1A0h+var_210]; this
0x1800793f8  call    ??0CRPCTimeoutEx@ShieldProvider@@QEAA@KPEBG@Z; ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(ulong,ushort const *)
0x1800793fd  mov     rcx, [rdi]
0x180079400  lea     r8, [rsi+78h]
0x180079404  mov     rdx, [r15]
0x180079407  mov     rax, [rcx]
0x18007940a  mov     rax, [rax+40h]
0x18007940e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079413  lea     r15, WPP_GLOBAL_Control
0x18007941a  mov     r14d, eax
0x18007941d  test    eax, eax
0x18007941f  js      short loc_18007942E
0x180079421  mov     r13d, 1
0x180079427  mov     [rsp+2A0h+var_270], r13b
0x18007942c  jmp     short loc_180079458
0x18007942e  mov     rcx, cs:WPP_GLOBAL_Control
0x180079435  cmp     rcx, r15
0x180079438  jz      short loc_180079458
0x18007943a  test    byte ptr [rcx+1Ch], 1
0x18007943e  jz      short loc_180079458
0x180079440  mov     rcx, [rcx+10h]
0x180079444  lea     r8, WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids
0x18007944b  mov     edx, 33h ; '3'
0x180079450  mov     r9d, eax
0x180079453  call    WPP_SF_d
0x180079458  lea     rcx, [rbp+1A0h+var_210]; this
0x18007945c  call    ??1CRPCTimeoutEx@ShieldProvider@@QEAA@XZ; ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx(void)
0x180079461  mov     rbx, [rsp+2A0h+var_260]
0x180079466  jmp     short loc_180079499
0x180079468  mov     rcx, cs:WPP_GLOBAL_Control
0x18007946f  lea     r15, WPP_GLOBAL_Control
0x180079476  cmp     rcx, r15
0x180079479  jz      short loc_180079499
0x18007947b  test    byte ptr [rcx+1Ch], 1
0x18007947f  jz      short loc_180079499
0x180079481  mov     edx, 34h ; '4'
0x180079486  mov     r9d, eax
0x180079489  mov     rcx, [rcx+10h]
0x18007948d  lea     r8, WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids
0x180079494  call    WPP_SF_d
0x180079499  test    r14d, r14d
0x18007949c  jns     short loc_1800794CD
0x18007949e  lea     r8, aShieldprovider_30; "ShieldProvider::DataProtectionShield::O"...
0x1800794a5  mov     edx, 3E8h; DueTime
0x1800794aa  lea     rcx, [rbp+1A0h+var_210]; this
0x1800794ae  call    ??0CRPCTimeoutEx@ShieldProvider@@QEAA@KPEBG@Z; ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(ulong,ushort const *)
0x1800794b3  mov     rcx, rdi
0x1800794b6  call    ??4?$AutoRef@UIHardwareShield16@@@CommonUtil@@QEAAAEAV01@PEAUIHardwareShield16@@@Z; CommonUtil::AutoRef<IHardwareShield16>::operator=(IHardwareShield16 *)
0x1800794bb  lea     rcx, [rsi+18h]
0x1800794bf  call    ??4?$AutoRef@UICrossContainerCommunicationManager@@@CommonUtil@@QEAAAEAV01@PEAUICrossContainerCommunicationManager@@@Z; CommonUtil::AutoRef<ICrossContainerCommunicationManager>::operator=(ICrossContainerCommunicationManager *)
0x1800794c4  lea     rcx, [rbp+1A0h+var_210]; this
0x1800794c8  call    ??1CRPCTimeoutEx@ShieldProvider@@QEAA@XZ; ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx(void)
0x1800794cd  mov     dil, [rsp+2A0h+var_270]
0x1800794d2  jmp     short loc_1800794D7
0x1800794d4  mov     dil, bl
0x1800794d7  lea     rcx, [rsp+2A0h+var_250]
0x1800794dc  mov     [rsp+2A0h+var_240], 0
0x1800794e1  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x1800794e6  test    rbx, rbx
0x1800794e9  jz      short loc_180079546
0x1800794eb  lea     r8, aShieldprovider_30; "ShieldProvider::DataProtectionShield::O"...
0x1800794f2  mov     edx, 0BB8h; DueTime
0x1800794f7  lea     rcx, [rbp+1A0h+var_210]; this
0x1800794fb  call    ??0CRPCTimeoutEx@ShieldProvider@@QEAA@KPEBG@Z; ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(ulong,ushort const *)
0x180079500  mov     rax, [rbx]
0x180079503  mov     rcx, rbx
0x180079506  mov     rax, [rax+38h]
0x18007950a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007950f  test    eax, eax
0x180079511  jns     short loc_18007953D
0x180079513  mov     rcx, cs:WPP_GLOBAL_Control
0x18007951a  cmp     rcx, r15
0x18007951d  jz      short loc_18007953D
0x18007951f  test    byte ptr [rcx+1Ch], 1
0x180079523  jz      short loc_18007953D
0x180079525  mov     rcx, [rcx+10h]
0x180079529  lea     r8, WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids
0x180079530  mov     edx, 36h ; '6'
0x180079535  mov     r9d, eax
0x180079538  call    WPP_SF_d
0x18007953d  lea     rcx, [rbp+1A0h+var_210]; this
0x180079541  call    ??1CRPCTimeoutEx@ShieldProvider@@QEAA@XZ; ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx(void)
0x180079546  test    r14d, r14d
0x180079549  js      short loc_180079569
0x18007954b  test    r13d, r13d
0x18007954e  jz      short loc_180079569
0x180079550  mov     rcx, rsi; this
0x180079553  call    ?PopulateCloudBackupProviders@DataProtectionShield@ShieldProvider@@AEAAJXZ; ShieldProvider::DataProtectionShield::PopulateCloudBackupProviders(void)
0x180079558  test    eax, eax
0x18007955a  js      short loc_180079569
0x18007955c  lea     rdx, [rsp+2A0h+var_268]; int *
0x180079561  mov     rcx, rsi; this
0x180079564  call    ?RefreshPillarStatusForUser@DataProtectionShield@ShieldProvider@@AEAAJPEAH@Z; ShieldProvider::DataProtectionShield::RefreshPillarStatusForUser(int *)
0x180079569  mov     rbx, [rsp+2A0h+var_258]
0x18007956e  test    rbx, rbx
0x180079571  jz      short loc_1800795DF
0x180079573  test    r14d, r14d
0x180079576  js      short loc_1800795DF
0x180079578  test    dil, dil
0x18007957b  jz      short loc_1800795DF
0x18007957d  lea     r8, aShieldprovider_30; "ShieldProvider::DataProtectionShield::O"...
0x180079584  mov     edx, 0BB8h; DueTime
0x180079589  lea     rcx, [rbp+1A0h+var_210]; this
0x18007958d  call    ??0CRPCTimeoutEx@ShieldProvider@@QEAA@KPEBG@Z; ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(ulong,ushort const *)
0x180079592  mov     rax, [rbx]
0x180079595  mov     edx, r13d
0x180079598  mov     rcx, rbx
0x18007959b  mov     rax, [rax+20h]
0x18007959f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800795a4  test    eax, eax
0x1800795a6  jns     short loc_1800795D6
0x1800795a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800795af  cmp     rcx, r15
0x1800795b2  jz      short loc_1800795D6
0x1800795b4  test    byte ptr [rcx+1Ch], 1
0x1800795b8  jz      short loc_1800795D6
0x1800795ba  mov     rcx, [rcx+10h]
0x1800795be  lea     r8, WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids
0x1800795c5  mov     edx, 37h ; '7'
0x1800795ca  mov     [rsp+2A0h+var_280], eax
0x1800795ce  mov     r9d, r13d
0x1800795d1  call    WPP_SF_Dd
0x1800795d6  lea     rcx, [rbp+1A0h+var_210]; this
0x1800795da  call    ??1CRPCTimeoutEx@ShieldProvider@@QEAA@XZ; ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx(void)
0x1800795df  lea     rcx, [rsp+2A0h+var_260]
0x1800795e4  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x1800795e9  lea     rcx, [rsp+2A0h+var_258]
0x1800795ee  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x1800795f3  xor     eax, eax
0x1800795f5  mov     rcx, [rbp+1A0h+var_30]
0x1800795fc  xor     rcx, rsp; StackCookie
0x1800795ff  call    __security_check_cookie
0x180079604  lea     r11, [rsp+2A0h+var_20]
0x18007960c  mov     rbx, [r11+38h]
0x180079610  mov     rsi, [r11+40h]
0x180079614  mov     rsp, r11
0x180079617  pop     r15
0x180079619  pop     r14
0x18007961b  pop     r13
0x18007961d  pop     rdi
0x18007961e  pop     rbp
  ... truncated ...
```
