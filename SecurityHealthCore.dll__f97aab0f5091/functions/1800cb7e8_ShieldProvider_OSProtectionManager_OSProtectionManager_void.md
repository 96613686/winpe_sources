# ShieldProvider::OSProtectionManager::~OSProtectionManager(void)

- ea: `0x1800cb7e8`
- end: `0x1800cb90d`
- name: `??1OSProtectionManager@ShieldProvider@@UEAA@XZ`
- size: `293`
- prototype: `void __fastcall(ShieldProvider::OSProtectionManager *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800cb934`

## callees

- `0x180004710`
- `0x18000ccb0`
- `0x18000f02c`
- `0x18000f094`
- `0x18001e128`
- `0x1800cb7e8`
- `0x1800d3b3c`
- `0x1800d3bf4`
- `0x1800de2d8`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800cb849`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800cb860`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800cb849`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800cb860`

## pseudocode

```c
void __fastcall ShieldProvider::OSProtectionManager::~OSProtectionManager(ShieldProvider::OSProtectionManager *this)
{
  __int64 v2; // rdx
  _BYTE v3[32]; // [rsp+20h] [rbp-148h] BYREF
  _BYTE v4[240]; // [rsp+40h] [rbp-128h] BYREF

  *(_QWORD *)((char *)this + *(int *)(*((_QWORD *)this - 14) + 4LL) - 112) = &ShieldProvider::OSProtectionManager::`vftable';
  v2 = *(int *)(*((_QWORD *)this - 14) + 4LL);
  *(_DWORD *)((char *)this + v2 - 116) = v2 - 112;
  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(
    v3,
    (char *)this - 96);
  *((_BYTE *)this - 56) = 1;
  if ( *((_QWORD *)this - 5) )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion();
    *((_QWORD *)this - 5) = 0;
  }
  if ( *((_QWORD *)this - 4) )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion();
    *((_QWORD *)this - 4) = 0;
  }
  ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(
    (ShieldProvider::CRPCTimeoutEx *)v4,
    0x3E8u,
    L"ShieldProvider::OSProtectionManager::~OSProtectionManager");
  CommonUtil::AutoRef<IHardwareNotificationsSink3>::operator=((char *)this - 24, 0);
  CommonUtil::AutoRef<IHardwareNotificationsSink3>::operator=((char *)this - 16, 0);
  ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx((ShieldProvider::CRPCTimeoutEx *)v4);
  v3[16] = 0;
  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v3);
  CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>((char *)this - 16);
  CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>((char *)this - 24);
  CommonUtil::CMpCriticalSection::~CMpCriticalSection((ShieldProvider::OSProtectionManager *)((char *)this - 96));
  *(_QWORD *)((char *)this + *(int *)(*((_QWORD *)this - 14) + 4LL) - 112) = &CRefCountedBaseX::`vftable';
  *(_DWORD *)((char *)this + *(int *)(*((_QWORD *)this - 14) + 4LL) - 116) = *(_DWORD *)(*((_QWORD *)this - 14) + 4LL)
                                                                           - 24;
}

```

## disassembly

```asm
0x1800cb7e8  push    rbx
0x1800cb7ea  push    rbp
0x1800cb7eb  push    rsi
0x1800cb7ec  push    rdi
0x1800cb7ed  sub     rsp, 148h
0x1800cb7f4  mov     rax, cs:__security_cookie
0x1800cb7fb  xor     rax, rsp
0x1800cb7fe  mov     [rsp+168h+var_38], rax
0x1800cb806  mov     rax, [rcx-70h]
0x1800cb80a  mov     rsi, rcx
0x1800cb80d  movsxd  rdx, dword ptr [rax+4]
0x1800cb811  lea     rax, ??_7OSProtectionManager@ShieldProvider@@6B@; const ShieldProvider::OSProtectionManager::`vftable'
0x1800cb818  mov     [rdx+rcx-70h], rax
0x1800cb81d  mov     rax, [rcx-70h]
0x1800cb821  movsxd  rdx, dword ptr [rax+4]
0x1800cb825  lea     r8d, [rdx-70h]
0x1800cb829  mov     [rdx+rcx-74h], r8d
0x1800cb82e  lea     rdx, [rcx-60h]
0x1800cb832  lea     rcx, [rsp+168h+var_148]
0x1800cb837  call    ??0?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@AEBVCMpCriticalSection@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(CommonUtil::CMpCriticalSection const &,CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::ENUM_LOCK_INITIAL_STATE)
0x1800cb83c  mov     byte ptr [rsi-38h], 1
0x1800cb840  mov     rcx, [rsi-28h]
0x1800cb844  test    rcx, rcx
0x1800cb847  jz      short loc_1800CB857
0x1800cb849  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x1800cb84f  mov     qword ptr [rsi-28h], 0
0x1800cb857  mov     rcx, [rsi-20h]
0x1800cb85b  test    rcx, rcx
0x1800cb85e  jz      short loc_1800CB86E
0x1800cb860  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x1800cb866  mov     qword ptr [rsi-20h], 0
0x1800cb86e  lea     r8, aShieldprovider_29; "ShieldProvider::OSProtectionManager::~O"...
0x1800cb875  mov     edx, 3E8h; DueTime
0x1800cb87a  lea     rcx, [rsp+168h+var_128]; this
0x1800cb87f  call    ??0CRPCTimeoutEx@ShieldProvider@@QEAA@KPEBG@Z; ShieldProvider::CRPCTimeoutEx::CRPCTimeoutEx(ulong,ushort const *)
0x1800cb884  xor     edx, edx
0x1800cb886  lea     rcx, [rsi-18h]
0x1800cb88a  call    ??4?$AutoRef@UIHardwareNotificationsSink3@@@CommonUtil@@QEAAAEAV01@PEAUIHardwareNotificationsSink3@@@Z; CommonUtil::AutoRef<IHardwareNotificationsSink3>::operator=(IHardwareNotificationsSink3 *)
0x1800cb88f  xor     edx, edx
0x1800cb891  lea     rcx, [rsi-10h]
0x1800cb895  call    ??4?$AutoRef@UIHardwareNotificationsSink3@@@CommonUtil@@QEAAAEAV01@PEAUIHardwareNotificationsSink3@@@Z; CommonUtil::AutoRef<IHardwareNotificationsSink3>::operator=(IHardwareNotificationsSink3 *)
0x1800cb89a  lea     rcx, [rsp+168h+var_128]; this
0x1800cb89f  call    ??1CRPCTimeoutEx@ShieldProvider@@QEAA@XZ; ShieldProvider::CRPCTimeoutEx::~CRPCTimeoutEx(void)
0x1800cb8a4  lea     rcx, [rsp+168h+var_148]
0x1800cb8a9  mov     [rsp+168h+var_138], 0
0x1800cb8ae  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x1800cb8b3  lea     rcx, [rsi-10h]
0x1800cb8b7  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x1800cb8bc  lea     rcx, [rsi-18h]
0x1800cb8c0  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x1800cb8c5  lea     rcx, [rsi-60h]; this
0x1800cb8c9  call    ??1CMpCriticalSection@CommonUtil@@QEAA@XZ; CommonUtil::CMpCriticalSection::~CMpCriticalSection(void)
0x1800cb8ce  mov     rax, [rsi-70h]
0x1800cb8d2  movsxd  rcx, dword ptr [rax+4]
0x1800cb8d6  lea     rax, ??_7CRefCountedBaseX@@6B@; const CRefCountedBaseX::`vftable'
0x1800cb8dd  mov     [rcx+rsi-70h], rax
0x1800cb8e2  mov     rax, [rsi-70h]
0x1800cb8e6  movsxd  rcx, dword ptr [rax+4]
0x1800cb8ea  lea     edx, [rcx-18h]
0x1800cb8ed  mov     [rcx+rsi-74h], edx
0x1800cb8f1  mov     rcx, [rsp+168h+var_38]
0x1800cb8f9  xor     rcx, rsp; StackCookie
0x1800cb8fc  call    __security_check_cookie
0x1800cb901  add     rsp, 148h
0x1800cb908  pop     rdi
0x1800cb909  pop     rsi
0x1800cb90a  pop     rbp
0x1800cb90b  pop     rbx
0x1800cb90c  retn
```
