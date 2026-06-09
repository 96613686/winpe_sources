# ShieldProvider::AccountProtectionShield::UnregisterListeners(void)

- ea: `0x1800cac7c`
- end: `0x1800cad39`
- name: `?UnregisterListeners@AccountProtectionShield@ShieldProvider@@AEAAXXZ`
- size: `189`
- prototype: `void __fastcall(ShieldProvider::AccountProtectionShield *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800c4ddc`
- `0x1800ca0d0`

## callees

- `0x18000f02c`
- `0x18000f094`
- `0x1800cac7c`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800cac9f`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800cacbc`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800cacd9`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800cacf6`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800cad13`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800cac9f`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800cacbc`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800cacd9`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800cacf6`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800cad13`

## pseudocode

```c
void __fastcall ShieldProvider::AccountProtectionShield::UnregisterListeners(
        ShieldProvider::AccountProtectionShield *this)
{
  _BYTE v2[40]; // [rsp+20h] [rbp-28h] BYREF

  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(
    v2,
    (char *)this + 24);
  if ( *((_QWORD *)this + 19) )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion();
    *((_QWORD *)this + 19) = 0;
  }
  if ( *((_QWORD *)this + 20) )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion();
    *((_QWORD *)this + 20) = 0;
  }
  if ( *((_QWORD *)this + 27) )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion();
    *((_QWORD *)this + 27) = 0;
  }
  if ( *((_QWORD *)this + 30) )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion();
    *((_QWORD *)this + 30) = 0;
  }
  if ( *((_QWORD *)this + 16) )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion();
    *((_QWORD *)this + 16) = 0;
  }
  v2[16] = 0;
  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v2);
}

```

## disassembly

```asm
0x1800cac7c  push    rbx
0x1800cac7e  sub     rsp, 40h
0x1800cac82  mov     rbx, rcx
0x1800cac85  lea     rdx, [rcx+18h]
0x1800cac89  lea     rcx, [rsp+48h+var_28]
0x1800cac8e  call    ??0?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@AEBVCMpCriticalSection@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(CommonUtil::CMpCriticalSection const &,CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::ENUM_LOCK_INITIAL_STATE)
0x1800cac93  mov     rcx, [rbx+98h]
0x1800cac9a  test    rcx, rcx
0x1800cac9d  jz      short loc_1800CACB0
0x1800cac9f  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x1800caca5  mov     qword ptr [rbx+98h], 0
0x1800cacb0  mov     rcx, [rbx+0A0h]
0x1800cacb7  test    rcx, rcx
0x1800cacba  jz      short loc_1800CACCD
0x1800cacbc  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x1800cacc2  mov     qword ptr [rbx+0A0h], 0
0x1800caccd  mov     rcx, [rbx+0D8h]
0x1800cacd4  test    rcx, rcx
0x1800cacd7  jz      short loc_1800CACEA
0x1800cacd9  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x1800cacdf  mov     qword ptr [rbx+0D8h], 0
0x1800cacea  mov     rcx, [rbx+0F0h]
0x1800cacf1  test    rcx, rcx
0x1800cacf4  jz      short loc_1800CAD07
0x1800cacf6  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x1800cacfc  mov     qword ptr [rbx+0F0h], 0
0x1800cad07  mov     rcx, [rbx+80h]
0x1800cad0e  test    rcx, rcx
0x1800cad11  jz      short loc_1800CAD24
0x1800cad13  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x1800cad19  mov     qword ptr [rbx+80h], 0
0x1800cad24  lea     rcx, [rsp+48h+var_28]
0x1800cad29  mov     [rsp+48h+var_18], 0
0x1800cad2e  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x1800cad33  add     rsp, 40h
0x1800cad37  pop     rbx
0x1800cad38  retn
```
