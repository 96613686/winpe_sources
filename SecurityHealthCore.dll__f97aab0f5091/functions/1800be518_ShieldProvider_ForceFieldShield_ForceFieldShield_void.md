# ShieldProvider::ForceFieldShield::~ForceFieldShield(void)

- ea: `0x1800be518`
- end: `0x1800be766`
- name: `??1ForceFieldShield@ShieldProvider@@MEAA@XZ`
- size: `590`
- prototype: `void __fastcall(ShieldProvider::ForceFieldShield *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800be770`

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
- `0x18007ac88`
- `0x1800be518`
- `0x1800be8dc`
- `0x1800bf504`
- `0x1800d3b3c`
- `0x1800d3bf4`
- `0x1800db9f8`
- `0x1800de2d8`
- `0x1800e7010`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x1800be650`
- `KERNEL32!WaitForSingleObject` at `0x1800be650`
- `KERNEL32!CloseHandle` at `0x1800be678`
- `KERNEL32!CloseHandle` at `0x1800be68a`
- `KERNEL32!CloseHandle` at `0x1800be678`
- `KERNEL32!CloseHandle` at `0x1800be68a`
- `ole32!CoTaskMemFree` at `0x1800be6fa`
- `ole32!CoTaskMemFree` at `0x1800be704`
- `ole32!CoTaskMemFree` at `0x1800be70e`
- `ole32!CoTaskMemFree` at `0x1800be717`
- `ole32!CoTaskMemFree` at `0x1800be6fa`
- `ole32!CoTaskMemFree` at `0x1800be704`
- `ole32!CoTaskMemFree` at `0x1800be70e`
- `ole32!CoTaskMemFree` at `0x1800be717`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800be69c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800be69c`

## pseudocode

```c
void __fastcall ShieldProvider::ForceFieldShield::~ForceFieldShield(CommonUtil **this, void *a2)
{
  struct ShieldProvider::DataProtectionShield *v3; // rdx
  CommonUtil *v4; // rcx
  const unsigned __int16 *v5; // r8
  const struct std::nothrow_t *v6; // rdx
  CommonUtil *v7; // rcx
  CommonUtil *v8; // rcx
  SC_HANDLE v9; // rcx
  CommonUtil *v10; // rcx
  CommonUtil *v11; // rcx
  LPVOID *v12; // rdi
  bool v13; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v14[24]; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v15[240]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v16[240]; // [rsp+130h] [rbp+30h] BYREF

  *this = (CommonUtil *)&ShieldProvider::ForceFieldShield::`vftable';
  CommonUtil::UtilSetEvent(this[19], a2);
  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(
    v14,
    this + 7);
  v13 = 0;
  if ( (int)ShieldProvider::ForceFieldShield::GetIsWscServiceRunning((ShieldProvider::ForceFieldShield *)this, &v13) >= 0 )
  {
    if ( this[3] )
    {
      ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(
        (ShieldProvider::CRPCTimeoutEx *)v15,
        0x3E8u,
        L"ShieldProvider::ForceFieldShield::~ForceFieldShield");
      ShieldProvider::WscBrokerSink::SetParent(this[3], v3);
      ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx((ShieldProvider::CRPCTimeoutEx *)v15);
    }
    if ( v13 )
    {
      if ( this[2] )
      {
        ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(
          (ShieldProvider::CRPCTimeoutEx *)v15,
          0x3E8u,
          L"ShieldProvider::ForceFieldShield::~ForceFieldShield");
        (*(void (__fastcall **)(CommonUtil *, _QWORD, _QWORD))(*(_QWORD *)this[2] + 72LL))(
          this[2],
          *((unsigned int *)this + 42),
          *((unsigned int *)this + 30));
        ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx((ShieldProvider::CRPCTimeoutEx *)v15);
      }
    }
    else
    {
      this[2] = 0;
    }
  }
  ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(
    (ShieldProvider::CRPCTimeoutEx *)v16,
    0x3E8u,
    L"ShieldProvider::ForceFieldShield::~ForceFieldShield");
  CommonUtil::AutoRef<ICrossContainerCommunicationManager>::operator=(this + 3);
  CommonUtil::AutoRef<IHardwareNotificationsSink3>::operator=(this + 4, 0);
  ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx((ShieldProvider::CRPCTimeoutEx *)v16);
  v14[16] = 0;
  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v14);
  v4 = this[18];
  if ( v4 )
    WaitForSingleObject(v4, 0xFFFFFFFF);
  ShieldProvider::ForceFieldShield::ClearForceFieldProviderList((ShieldProvider::ForceFieldShield *)this);
  ShieldProvider::AddToLifetimeReference(0, (bool)L"ForceFieldShield", v5);
  v7 = this[19];
  if ( v7 )
    CloseHandle(v7);
  v8 = this[18];
  if ( v8 )
    CloseHandle(v8);
  v9 = (SC_HANDLE)this[17];
  if ( v9 )
    CloseServiceHandle(v9);
  v10 = this[16];
  if ( v10 )
    operator delete(v10, v6);
  v11 = this[12];
  if ( v11 )
  {
    std::_Deallocate<16>(v11, (this[14] - v11) & 0xFFFFFFFFFFFFFFF8uLL);
    this[12] = 0;
    this[13] = 0;
    this[14] = 0;
  }
  CommonUtil::CMpCriticalSection::~CMpCriticalSection((CommonUtil::CMpCriticalSection *)(this + 7));
  v12 = (LPVOID *)this[6];
  if ( v12 )
  {
    CoTaskMemFree(v12[2]);
    CoTaskMemFree(v12[3]);
    CoTaskMemFree(v12[4]);
    CoTaskMemFree(v12);
  }
  CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(this + 4);
  CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(this + 3);
  CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(this + 2);
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x1800be518  mov     [rsp-8+arg_8], rbx
0x1800be51d  mov     [rsp-8+arg_10], rsi
0x1800be522  push    rbp
0x1800be523  push    rdi
0x1800be524  push    r14
0x1800be526  lea     rbp, [rsp-130h]
0x1800be52e  sub     rsp, 230h
0x1800be535  mov     rax, cs:__security_cookie
0x1800be53c  xor     rax, rsp
0x1800be53f  mov     [rbp+140h+var_20], rax
0x1800be546  mov     rbx, rcx
0x1800be549  lea     rax, ??_7ForceFieldShield@ShieldProvider@@6B@; const ShieldProvider::ForceFieldShield::`vftable'
0x1800be550  mov     [rcx], rax
0x1800be553  mov     rcx, [rcx+98h]; this
0x1800be55a  call    ?UtilSetEvent@CommonUtil@@YAXPEAX@Z; CommonUtil::UtilSetEvent(void *)
0x1800be55f  lea     rdx, [rbx+38h]
0x1800be563  lea     rcx, [rsp+240h+var_218]
0x1800be568  call    ??0?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@AEBVCMpCriticalSection@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(CommonUtil::CMpCriticalSection const &,CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::ENUM_LOCK_INITIAL_STATE)
0x1800be56d  mov     [rsp+240h+var_220], 0
0x1800be572  lea     rdx, [rsp+240h+var_220]; bool *
0x1800be577  mov     rcx, rbx; this
0x1800be57a  call    ?GetIsWscServiceRunning@ForceFieldShield@ShieldProvider@@AEAAJPEA_N@Z; ShieldProvider::ForceFieldShield::GetIsWscServiceRunning(bool *)
0x1800be57f  lea     rsi, aShieldprovider_61; "ShieldProvider::ForceFieldShield::~Forc"...
0x1800be586  mov     r14d, 3E8h
0x1800be58c  test    eax, eax
0x1800be58e  js      short loc_1800BE606
0x1800be590  cmp     qword ptr [rbx+18h], 0
0x1800be595  jz      short loc_1800BE5BA
0x1800be597  mov     r8, rsi; unsigned __int16 *
0x1800be59a  mov     edx, r14d; DueTime
0x1800be59d  lea     rcx, [rsp+240h+var_200]; this
0x1800be5a2  call    ??0CRPCTimeoutEx@ShieldProvider@@QEAA@KPEBG@Z; ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(ulong,ushort const *)
0x1800be5a7  mov     rcx, [rbx+18h]; this
0x1800be5ab  call    ?SetParent@WscBrokerSink@ShieldProvider@@QEAAXPEAVDataProtectionShield@2@@Z; ShieldProvider::WscBrokerSink::SetParent(ShieldProvider::DataProtectionShield *)
0x1800be5b0  lea     rcx, [rsp+240h+var_200]; this
0x1800be5b5  call    ??1CRPCTimeoutEx@ShieldProvider@@QEAA@XZ; ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx(void)
0x1800be5ba  cmp     [rsp+240h+var_220], 0
0x1800be5bf  jz      short loc_1800BE5FE
0x1800be5c1  cmp     qword ptr [rbx+10h], 0
0x1800be5c6  jz      short loc_1800BE606
0x1800be5c8  mov     r8, rsi; unsigned __int16 *
0x1800be5cb  mov     edx, r14d; DueTime
0x1800be5ce  lea     rcx, [rsp+240h+var_200]; this
0x1800be5d3  call    ??0CRPCTimeoutEx@ShieldProvider@@QEAA@KPEBG@Z; ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(ulong,ushort const *)
0x1800be5d8  mov     rcx, [rbx+10h]
0x1800be5dc  mov     rax, [rcx]
0x1800be5df  mov     r8d, [rbx+78h]
0x1800be5e3  mov     edx, [rbx+0A8h]
0x1800be5e9  mov     rax, [rax+48h]
0x1800be5ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be5f2  lea     rcx, [rsp+240h+var_200]; this
0x1800be5f7  call    ??1CRPCTimeoutEx@ShieldProvider@@QEAA@XZ; ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx(void)
0x1800be5fc  jmp     short loc_1800BE606
0x1800be5fe  mov     qword ptr [rbx+10h], 0
0x1800be606  mov     r8, rsi; unsigned __int16 *
0x1800be609  mov     edx, r14d; DueTime
0x1800be60c  lea     rcx, [rbp+140h+var_110]; this
0x1800be610  call    ??0CRPCTimeoutEx@ShieldProvider@@QEAA@KPEBG@Z; ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(ulong,ushort const *)
0x1800be615  lea     rcx, [rbx+18h]
0x1800be619  call    ??4?$AutoRef@UICrossContainerCommunicationManager@@@CommonUtil@@QEAAAEAV01@PEAUICrossContainerCommunicationManager@@@Z; CommonUtil::AutoRef<ICrossContainerCommunicationManager>::operator=(ICrossContainerCommunicationManager *)
0x1800be61e  xor     edx, edx
0x1800be620  lea     rcx, [rbx+20h]
0x1800be624  call    ??4?$AutoRef@UIHardwareNotificationsSink3@@@CommonUtil@@QEAAAEAV01@PEAUIHardwareNotificationsSink3@@@Z; CommonUtil::AutoRef<IHardwareNotificationsSink3>::operator=(IHardwareNotificationsSink3 *)
0x1800be629  lea     rcx, [rbp+140h+var_110]; this
0x1800be62d  call    ??1CRPCTimeoutEx@ShieldProvider@@QEAA@XZ; ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx(void)
0x1800be632  mov     [rsp+240h+var_208], 0
0x1800be637  lea     rcx, [rsp+240h+var_218]
0x1800be63c  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x1800be641  mov     rcx, [rbx+90h]; hHandle
0x1800be648  test    rcx, rcx
0x1800be64b  jz      short loc_1800BE656
0x1800be64d  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800be650  call    cs:__imp_WaitForSingleObject
0x1800be656  mov     rcx, rbx; this
0x1800be659  call    ?ClearForceFieldProviderList@ForceFieldShield@ShieldProvider@@AEAAXXZ; ShieldProvider::ForceFieldShield::ClearForceFieldProviderList(void)
0x1800be65e  lea     rdx, aForcefieldshie; "ForceFieldShield"
0x1800be665  xor     ecx, ecx; this
0x1800be667  call    ?AddToLifetimeReference@ShieldProvider@@YAX_NPEBG@Z; ShieldProvider::AddToLifetimeReference(bool,ushort const *)
0x1800be66c  mov     rcx, [rbx+98h]; hObject
0x1800be673  test    rcx, rcx
0x1800be676  jz      short loc_1800BE67E
0x1800be678  call    cs:__imp_CloseHandle
0x1800be67e  mov     rcx, [rbx+90h]; hObject
0x1800be685  test    rcx, rcx
0x1800be688  jz      short loc_1800BE690
0x1800be68a  call    cs:__imp_CloseHandle
0x1800be690  mov     rcx, [rbx+88h]; hSCObject
0x1800be697  test    rcx, rcx
0x1800be69a  jz      short loc_1800BE6A2
0x1800be69c  call    cs:__imp_CloseServiceHandle
0x1800be6a2  mov     rcx, [rbx+80h]; void *
0x1800be6a9  test    rcx, rcx
0x1800be6ac  jz      short loc_1800BE6B3
0x1800be6ae  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800be6b3  mov     rcx, [rbx+60h]
0x1800be6b7  test    rcx, rcx
0x1800be6ba  jz      short loc_1800BE6E4
0x1800be6bc  mov     rdx, [rbx+70h]
0x1800be6c0  sub     rdx, rcx
0x1800be6c3  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1800be6c7  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800be6cc  mov     qword ptr [rbx+60h], 0
0x1800be6d4  mov     qword ptr [rbx+68h], 0
0x1800be6dc  mov     qword ptr [rbx+70h], 0
0x1800be6e4  lea     rcx, [rbx+38h]; this
0x1800be6e8  call    ??1CMpCriticalSection@CommonUtil@@QEAA@XZ; CommonUtil::CMpCriticalSection::~CMpCriticalSection(void)
0x1800be6ed  mov     rdi, [rbx+30h]
0x1800be6f1  test    rdi, rdi
0x1800be6f4  jz      short loc_1800BE71D
0x1800be6f6  mov     rcx, [rdi+10h]; pv
0x1800be6fa  call    cs:__imp_CoTaskMemFree
0x1800be700  mov     rcx, [rdi+18h]; pv
0x1800be704  call    cs:__imp_CoTaskMemFree
0x1800be70a  mov     rcx, [rdi+20h]; pv
0x1800be70e  call    cs:__imp_CoTaskMemFree
0x1800be714  mov     rcx, rdi; pv
0x1800be717  call    cs:__imp_CoTaskMemFree
0x1800be71d  lea     rcx, [rbx+20h]
0x1800be721  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x1800be726  lea     rcx, [rbx+18h]
0x1800be72a  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x1800be72f  lea     rcx, [rbx+10h]
0x1800be733  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x1800be738  mov     dword ptr [rbx+0Ch], 0C0000001h
0x1800be73f  mov     rcx, [rbp+140h+var_20]
0x1800be746  xor     rcx, rsp; StackCookie
0x1800be749  call    __security_check_cookie
0x1800be74e  lea     r11, [rsp+240h+var_10]
0x1800be756  mov     rbx, [r11+28h]
0x1800be75a  mov     rsi, [r11+30h]
0x1800be75e  mov     rsp, r11
0x1800be761  pop     r14
0x1800be763  pop     rdi
0x1800be764  pop     rbp
0x1800be765  retn
```
