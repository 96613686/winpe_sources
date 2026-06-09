# ShieldProvider::DataProtectionShield::~DataProtectionShield(void)

- ea: `0x180076894`
- end: `0x180076b8e`
- name: `??1DataProtectionShield@ShieldProvider@@MEAA@XZ`
- size: `762`
- prototype: `void __fastcall(ShieldProvider::DataProtectionShield *__hidden this)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180076c00`

## callees

- `0x180004710`
- `0x180004ae0`
- `0x18000ccb0`
- `0x18000f02c`
- `0x18000f094`
- `0x18000f1f8`
- `0x180016d08`
- `0x18001e128`
- `0x180029b38`
- `0x180076894`
- `0x180077130`
- `0x180077ff4`
- `0x180078328`
- `0x18007ac88`
- `0x1800cf6f8`
- `0x1800d3b3c`
- `0x1800d3bf4`
- `0x1800db9f8`
- `0x1800dd4ec`
- `0x1800de1bc`
- `0x1800de2d8`
- `0x1800e7010`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x180076a6b`
- `KERNEL32!WaitForSingleObject` at `0x180076a6b`
- `KERNEL32!CloseHandle` at `0x180076a93`
- `KERNEL32!CloseHandle` at `0x180076aa5`
- `KERNEL32!CloseHandle` at `0x180076a93`
- `KERNEL32!CloseHandle` at `0x180076aa5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180076a43`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180076a43`
- `ole32!CoTaskMemFree` at `0x180076b09`
- `ole32!CoTaskMemFree` at `0x180076b13`
- `ole32!CoTaskMemFree` at `0x180076b1d`
- `ole32!CoTaskMemFree` at `0x180076b27`
- `ole32!CoTaskMemFree` at `0x180076b31`
- `ole32!CoTaskMemFree` at `0x180076b3a`
- `ole32!CoTaskMemFree` at `0x180076b09`
- `ole32!CoTaskMemFree` at `0x180076b13`
- `ole32!CoTaskMemFree` at `0x180076b1d`
- `ole32!CoTaskMemFree` at `0x180076b27`
- `ole32!CoTaskMemFree` at `0x180076b31`
- `ole32!CoTaskMemFree` at `0x180076b3a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180076ab7`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180076ab7`

## string_xrefs

- `0x1800769eb`: `SOFTWARE\Microsoft\Windows Security Health\State\Persist`

## pseudocode

```c
void __fastcall ShieldProvider::DataProtectionShield::~DataProtectionShield(CommonUtil **this, void *a2)
{
  struct ShieldProvider::DataProtectionShield *v3; // rdx
  int v4; // r14d
  const struct std::nothrow_t *v5; // rdx
  unsigned __int16 **v6; // r9
  int Key; // eax
  const unsigned __int16 *v8; // r8
  HKEY v9; // rbx
  CommonUtil *v10; // rcx
  CommonUtil *v11; // rcx
  const unsigned __int16 *v12; // r8
  const struct std::nothrow_t *v13; // rdx
  CommonUtil *v14; // rcx
  CommonUtil *v15; // rcx
  SC_HANDLE v16; // rcx
  CommonUtil *v17; // rcx
  CommonUtil *v18; // rcx
  LPVOID *v19; // rbx
  const void *v20; // [rsp+28h] [rbp-D8h]
  bool v21; // [rsp+30h] [rbp-D0h] BYREF
  HKEY v22; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v24[24]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v25[240]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v26[240]; // [rsp+150h] [rbp+50h] BYREF

  *this = (CommonUtil *)&ShieldProvider::DataProtectionShield::`vftable';
  CommonUtil::UtilSetEvent(this[19], a2);
  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(
    v24,
    this + 7);
  v21 = 0;
  if ( (int)ShieldProvider::DataProtectionShield::GetIsWscServiceRunning(
              (ShieldProvider::DataProtectionShield *)this,
              &v21) >= 0 )
  {
    if ( this[3] )
    {
      ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(
        (ShieldProvider::CRPCTimeoutEx *)v25,
        0x3E8u,
        L"ShieldProvider::DataProtectionShield::~DataProtectionShield");
      ShieldProvider::WscBrokerSink::SetParent(this[3], v3);
      ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx((ShieldProvider::CRPCTimeoutEx *)v25);
    }
    if ( v21 )
    {
      if ( this[2] )
      {
        ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(
          (ShieldProvider::CRPCTimeoutEx *)v25,
          0x3E8u,
          L"ShieldProvider::DataProtectionShield::~DataProtectionShield");
        (*(void (__fastcall **)(CommonUtil *, _QWORD))(*(_QWORD *)this[2] + 72LL))(
          this[2],
          *((unsigned int *)this + 30));
        ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx((ShieldProvider::CRPCTimeoutEx *)v25);
      }
    }
    else
    {
      this[2] = 0;
    }
  }
  v4 = *((_DWORD *)this + 10);
  ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(
    (ShieldProvider::CRPCTimeoutEx *)v26,
    0x3E8u,
    L"ShieldProvider::DataProtectionShield::~DataProtectionShield");
  CommonUtil::AutoRef<ICrossContainerCommunicationManager>::operator=(this + 3);
  CommonUtil::AutoRef<IHardwareNotificationsSink3>::operator=(this + 4, 0);
  ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx((ShieldProvider::CRPCTimeoutEx *)v26);
  v24[16] = 0;
  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v24);
  v22 = 0;
  if ( (int)ShieldProvider::DataProtectionShield::GetStatePersistenceNameForProviderId(this, &GUID_NULL, 132, &v22) >= 0 )
  {
    hKey = 0;
    Key = ShieldProvider::ShieldUtilRegCreateKey(
            (ShieldProvider *)&hKey,
            (HKEY *)L"SOFTWARE\\Microsoft\\Windows Security Health\\State\\Persist",
            (const unsigned __int16 *)0x2001F,
            v6);
    v9 = hKey;
    if ( Key >= 0 )
    {
      v10 = (CommonUtil *)hKey;
      if ( v4 == 132 )
      {
        LODWORD(hKey) = 0;
        CommonUtil::UtilRegSetValueInternal(v10, v22, (const unsigned __int16 *)4, 4u, (unsigned __int64)&hKey, v20);
      }
      else
      {
        CommonUtil::UtilRegDeleteValue((CommonUtil *)hKey, v22, v8);
      }
    }
    if ( v9 )
      RegCloseKey(v9);
  }
  if ( v22 )
    operator delete(v22, v5);
  v11 = this[18];
  if ( v11 )
    WaitForSingleObject(v11, 0xFFFFFFFF);
  ShieldProvider::DataProtectionShield::ClearCloudBackupProviderList((ShieldProvider::DataProtectionShield *)this);
  ShieldProvider::AddToLifetimeReference(0, (bool)L"DataProtectionShield", v12);
  v14 = this[19];
  if ( v14 )
    CloseHandle(v14);
  v15 = this[18];
  if ( v15 )
    CloseHandle(v15);
  v16 = (SC_HANDLE)this[17];
  if ( v16 )
    CloseServiceHandle(v16);
  v17 = this[16];
  if ( v17 )
    operator delete(v17, v13);
  v18 = this[12];
  if ( v18 )
  {
    std::_Deallocate<16>(v18, (this[14] - v18) & 0xFFFFFFFFFFFFFFF8uLL);
    this[12] = 0;
    this[13] = 0;
    this[14] = 0;
  }
  CommonUtil::CMpCriticalSection::~CMpCriticalSection((CommonUtil::CMpCriticalSection *)(this + 7));
  v19 = (LPVOID *)this[6];
  if ( v19 )
  {
    CoTaskMemFree(v19[3]);
    CoTaskMemFree(v19[4]);
    CoTaskMemFree(v19[5]);
    CoTaskMemFree(v19[6]);
    CoTaskMemFree(v19[7]);
    CoTaskMemFree(v19);
  }
  CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(this + 4);
  CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(this + 3);
  CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(this + 2);
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x180076894  mov     [rsp-8+arg_8], rbx
0x180076899  mov     [rsp-8+arg_10], rsi
0x18007689e  push    rbp
0x18007689f  push    r12
0x1800768a1  push    r13
0x1800768a3  push    r14
0x1800768a5  push    r15
0x1800768a7  lea     rbp, [rsp-150h]
0x1800768af  sub     rsp, 250h
0x1800768b6  mov     rax, cs:__security_cookie
0x1800768bd  xor     rax, rsp
0x1800768c0  mov     [rbp+170h+var_30], rax
0x1800768c7  mov     rsi, rcx
0x1800768ca  lea     rax, ??_7DataProtectionShield@ShieldProvider@@6B@; const ShieldProvider::DataProtectionShield::`vftable'
0x1800768d1  mov     [rcx], rax
0x1800768d4  mov     rcx, [rcx+98h]; this
0x1800768db  call    ?UtilSetEvent@CommonUtil@@YAXPEAX@Z; CommonUtil::UtilSetEvent(void *)
0x1800768e0  lea     rdx, [rsi+38h]
0x1800768e4  lea     rcx, [rsp+270h+var_228]
0x1800768e9  call    ??0?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@AEBVCMpCriticalSection@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(CommonUtil::CMpCriticalSection const &,CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::ENUM_LOCK_INITIAL_STATE)
0x1800768ee  xor     ebx, ebx
0x1800768f0  mov     [rsp+270h+var_240], bl
0x1800768f4  lea     rdx, [rsp+270h+var_240]; bool *
0x1800768f9  mov     rcx, rsi; this
0x1800768fc  call    ?GetIsWscServiceRunning@DataProtectionShield@ShieldProvider@@AEAAJPEA_N@Z; ShieldProvider::DataProtectionShield::GetIsWscServiceRunning(bool *)
0x180076901  mov     r12d, 3E8h
0x180076907  test    eax, eax
0x180076909  js      short loc_18007697B
0x18007690b  cmp     [rsi+18h], rbx
0x18007690f  jz      short loc_180076938
0x180076911  lea     r8, aShieldprovider_47; "ShieldProvider::DataProtectionShield::~"...
0x180076918  mov     edx, r12d; DueTime
0x18007691b  lea     rcx, [rsp+270h+var_210]; this
0x180076920  call    ??0CRPCTimeoutEx@ShieldProvider@@QEAA@KPEBG@Z; ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(ulong,ushort const *)
0x180076925  mov     rcx, [rsi+18h]; this
0x180076929  call    ?SetParent@WscBrokerSink@ShieldProvider@@QEAAXPEAVDataProtectionShield@2@@Z; ShieldProvider::WscBrokerSink::SetParent(ShieldProvider::DataProtectionShield *)
0x18007692e  lea     rcx, [rsp+270h+var_210]; this
0x180076933  call    ??1CRPCTimeoutEx@ShieldProvider@@QEAA@XZ; ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx(void)
0x180076938  cmp     [rsp+270h+var_240], bl
0x18007693c  jz      short loc_180076977
0x18007693e  cmp     [rsi+10h], rbx
0x180076942  jz      short loc_18007697B
0x180076944  lea     r8, aShieldprovider_47; "ShieldProvider::DataProtectionShield::~"...
0x18007694b  mov     edx, r12d; DueTime
0x18007694e  lea     rcx, [rsp+270h+var_210]; this
0x180076953  call    ??0CRPCTimeoutEx@ShieldProvider@@QEAA@KPEBG@Z; ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(ulong,ushort const *)
0x180076958  mov     rcx, [rsi+10h]
0x18007695c  mov     rax, [rcx]
0x18007695f  mov     edx, [rsi+78h]
0x180076962  mov     rax, [rax+48h]
0x180076966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007696b  lea     rcx, [rsp+270h+var_210]; this
0x180076970  call    ??1CRPCTimeoutEx@ShieldProvider@@QEAA@XZ; ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx(void)
0x180076975  jmp     short loc_18007697B
0x180076977  mov     [rsi+10h], rbx
0x18007697b  mov     r14d, [rsi+28h]
0x18007697f  lea     r8, aShieldprovider_47; "ShieldProvider::DataProtectionShield::~"...
0x180076986  mov     edx, r12d; DueTime
0x180076989  lea     rcx, [rbp+170h+var_120]; this
0x18007698d  call    ??0CRPCTimeoutEx@ShieldProvider@@QEAA@KPEBG@Z; ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(ulong,ushort const *)
0x180076992  lea     rcx, [rsi+18h]
0x180076996  call    ??4?$AutoRef@UICrossContainerCommunicationManager@@@CommonUtil@@QEAAAEAV01@PEAUICrossContainerCommunicationManager@@@Z; CommonUtil::AutoRef<ICrossContainerCommunicationManager>::operator=(ICrossContainerCommunicationManager *)
0x18007699b  xor     edx, edx
0x18007699d  lea     rcx, [rsi+20h]
0x1800769a1  call    ??4?$AutoRef@UIHardwareNotificationsSink3@@@CommonUtil@@QEAAAEAV01@PEAUIHardwareNotificationsSink3@@@Z; CommonUtil::AutoRef<IHardwareNotificationsSink3>::operator=(IHardwareNotificationsSink3 *)
0x1800769a6  lea     rcx, [rbp+170h+var_120]; this
0x1800769aa  call    ??1CRPCTimeoutEx@ShieldProvider@@QEAA@XZ; ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx(void)
0x1800769af  mov     [rsp+270h+var_218], bl
0x1800769b3  lea     rcx, [rsp+270h+var_228]
0x1800769b8  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x1800769bd  mov     [rsp+270h+var_238], rbx
0x1800769c2  lea     r9, [rsp+270h+var_238]
0x1800769c7  mov     r8d, 84h
0x1800769cd  lea     rdx, GUID_NULL
0x1800769d4  mov     rcx, rsi
0x1800769d7  call    ?GetStatePersistenceNameForProviderId@DataProtectionShield@ShieldProvider@@AEAAJAEBU_GUID@@W4PillarStatusFlag@@PEAPEAG@Z; ShieldProvider::DataProtectionShield::GetStatePersistenceNameForProviderId(_GUID const &,PillarStatusFlag,ushort * *)
0x1800769dc  test    eax, eax
0x1800769de  js      short loc_180076A4B
0x1800769e0  mov     [rsp+270h+hKey], rbx
0x1800769e5  mov     r8d, 2001Fh; unsigned __int16 *
0x1800769eb  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows Security H"...
0x1800769f2  lea     rcx, [rsp+270h+hKey]; this
0x1800769f7  call    ?ShieldUtilRegCreateKey@ShieldProvider@@YAJPEAPEAUHKEY__@@PEBGK@Z; ShieldProvider::ShieldUtilRegCreateKey(HKEY__ * *,ushort const *,ulong)
0x1800769fc  mov     rbx, [rsp+270h+hKey]
0x180076a01  test    eax, eax
0x180076a03  js      short loc_180076A3B
0x180076a05  mov     rdx, [rsp+270h+var_238]; HKEY
0x180076a0a  mov     rcx, rbx; this
0x180076a0d  cmp     r14d, 84h
0x180076a14  jnz     short loc_180076A36
0x180076a16  mov     dword ptr [rsp+270h+hKey], 0
0x180076a1e  lea     rax, [rsp+270h+hKey]
0x180076a23  mov     [rsp+270h+var_250], rax; unsigned __int64
0x180076a28  lea     r8d, [r14-80h]; unsigned __int16 *
0x180076a2c  mov     r9d, r8d; unsigned int
0x180076a2f  call    ?UtilRegSetValueInternal@CommonUtil@@YAJPEAUHKEY__@@PEBGK_KPEBX@Z; CommonUtil::UtilRegSetValueInternal(HKEY__ *,ushort const *,ulong,unsigned __int64,void const *)
0x180076a34  jmp     short loc_180076A3B
0x180076a36  call    ?UtilRegDeleteValue@CommonUtil@@YAJPEAUHKEY__@@PEBG@Z; CommonUtil::UtilRegDeleteValue(HKEY__ *,ushort const *)
0x180076a3b  test    rbx, rbx
0x180076a3e  jz      short loc_180076A49
0x180076a40  mov     rcx, rbx; hKey
0x180076a43  call    cs:__imp_RegCloseKey
0x180076a49  xor     ebx, ebx
0x180076a4b  cmp     [rsp+270h+var_238], rbx
0x180076a50  jz      short loc_180076A5C
0x180076a52  mov     rcx, [rsp+270h+var_238]; void *
0x180076a57  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180076a5c  mov     rcx, [rsi+90h]; hHandle
0x180076a63  test    rcx, rcx
0x180076a66  jz      short loc_180076A71
0x180076a68  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180076a6b  call    cs:__imp_WaitForSingleObject
0x180076a71  mov     rcx, rsi; this
0x180076a74  call    ?ClearCloudBackupProviderList@DataProtectionShield@ShieldProvider@@AEAAXXZ; ShieldProvider::DataProtectionShield::ClearCloudBackupProviderList(void)
0x180076a79  lea     rdx, aDataprotection_2; "DataProtectionShield"
0x180076a80  xor     ecx, ecx; this
0x180076a82  call    ?AddToLifetimeReference@ShieldProvider@@YAX_NPEBG@Z; ShieldProvider::AddToLifetimeReference(bool,ushort const *)
0x180076a87  mov     rcx, [rsi+98h]; hObject
0x180076a8e  test    rcx, rcx
0x180076a91  jz      short loc_180076A99
0x180076a93  call    cs:__imp_CloseHandle
0x180076a99  mov     rcx, [rsi+90h]; hObject
0x180076aa0  test    rcx, rcx
0x180076aa3  jz      short loc_180076AAB
0x180076aa5  call    cs:__imp_CloseHandle
0x180076aab  mov     rcx, [rsi+88h]; hSCObject
0x180076ab2  test    rcx, rcx
0x180076ab5  jz      short loc_180076ABD
0x180076ab7  call    cs:__imp_CloseServiceHandle
0x180076abd  mov     rcx, [rsi+80h]; void *
0x180076ac4  test    rcx, rcx
0x180076ac7  jz      short loc_180076ACE
0x180076ac9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180076ace  mov     rcx, [rsi+60h]
0x180076ad2  test    rcx, rcx
0x180076ad5  jz      short loc_180076AF3
0x180076ad7  mov     rdx, [rsi+70h]
0x180076adb  sub     rdx, rcx
0x180076ade  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180076ae2  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180076ae7  mov     [rsi+60h], rbx
0x180076aeb  mov     [rsi+68h], rbx
0x180076aef  mov     [rsi+70h], rbx
0x180076af3  lea     rcx, [rsi+38h]; this
0x180076af7  call    ??1CMpCriticalSection@CommonUtil@@QEAA@XZ; CommonUtil::CMpCriticalSection::~CMpCriticalSection(void)
0x180076afc  mov     rbx, [rsi+30h]
0x180076b00  test    rbx, rbx
0x180076b03  jz      short loc_180076B40
0x180076b05  mov     rcx, [rbx+18h]; pv
0x180076b09  call    cs:__imp_CoTaskMemFree
0x180076b0f  mov     rcx, [rbx+20h]; pv
0x180076b13  call    cs:__imp_CoTaskMemFree
0x180076b19  mov     rcx, [rbx+28h]; pv
0x180076b1d  call    cs:__imp_CoTaskMemFree
0x180076b23  mov     rcx, [rbx+30h]; pv
0x180076b27  call    cs:__imp_CoTaskMemFree
0x180076b2d  mov     rcx, [rbx+38h]; pv
0x180076b31  call    cs:__imp_CoTaskMemFree
0x180076b37  mov     rcx, rbx; pv
0x180076b3a  call    cs:__imp_CoTaskMemFree
0x180076b40  lea     rcx, [rsi+20h]
0x180076b44  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x180076b49  lea     rcx, [rsi+18h]
0x180076b4d  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x180076b52  lea     rcx, [rsi+10h]
0x180076b56  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x180076b5b  mov     dword ptr [rsi+0Ch], 0C0000001h
0x180076b62  mov     rcx, [rbp+170h+var_30]
0x180076b69  xor     rcx, rsp; StackCookie
0x180076b6c  call    __security_check_cookie
0x180076b71  lea     r11, [rsp+270h+var_20]
0x180076b79  mov     rbx, [r11+38h]
0x180076b7d  mov     rsi, [r11+40h]
0x180076b81  mov     rsp, r11
0x180076b84  pop     r15
0x180076b86  pop     r14
0x180076b88  pop     r13
0x180076b8a  pop     r12
0x180076b8c  pop     rbp
0x180076b8d  retn
```
