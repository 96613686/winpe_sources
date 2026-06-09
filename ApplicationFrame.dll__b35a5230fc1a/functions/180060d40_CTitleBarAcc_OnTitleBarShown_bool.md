# CTitleBarAcc::OnTitleBarShown(bool)

- ea: `0x180060d40`
- end: `0x180060eb3`
- name: `?OnTitleBarShown@CTitleBarAcc@@UEAAX_N@Z`
- size: `371`
- prototype: `void __fastcall(CTitleBarAcc *__hidden this, bool)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180031a20`
- `0x18005be70`
- `0x180060d40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180060d7e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180060d7e`
- `OLEAUT32!__imp_VariantInit` at `0x180060daf`
- `OLEAUT32!__imp_VariantInit` at `0x180060dc9`
- `OLEAUT32!__imp_VariantInit` at `0x180060e0f`
- `OLEAUT32!__imp_VariantInit` at `0x180060e29`
- `OLEAUT32!__imp_VariantInit` at `0x180060daf`
- `OLEAUT32!__imp_VariantInit` at `0x180060dc9`
- `OLEAUT32!__imp_VariantInit` at `0x180060e0f`
- `OLEAUT32!__imp_VariantInit` at `0x180060e29`
- `OLEAUT32!__imp_VariantClear` at `0x180060e6d`
- `OLEAUT32!__imp_VariantClear` at `0x180060e98`
- `OLEAUT32!__imp_VariantClear` at `0x180060e6d`
- `OLEAUT32!__imp_VariantClear` at `0x180060e98`
- `UIAutomationCore!UiaRaiseStructureChangedEvent` at `0x180060e80`
- `UIAutomationCore!UiaRaiseStructureChangedEvent` at `0x180060e80`
- `UIAutomationCore!UiaRaiseAutomationEvent` at `0x180060e8e`
- `UIAutomationCore!UiaRaiseAutomationEvent` at `0x180060e8e`
- `UIAutomationCore!UiaClientsAreListening` at `0x180060d9d`
- `UIAutomationCore!UiaClientsAreListening` at `0x180060dfd`
- `UIAutomationCore!UiaClientsAreListening` at `0x180060d9d`
- `UIAutomationCore!UiaClientsAreListening` at `0x180060dfd`
- `UIAutomationCore!UiaRaiseAutomationPropertyChangedEvent` at `0x180060e63`
- `UIAutomationCore!UiaRaiseAutomationPropertyChangedEvent` at `0x180060e63`

## pseudocode

```c
void __fastcall CTitleBarAcc::OnTitleBarShown(CTitleBarAcc *this, char a2)
{
  RTL_SRWLOCK *v4; // rcx
  IRawElementProviderSimple *v5; // rbx
  VARIANT *p_newValue; // r9
  VARIANT *p_oldValue; // r8
  VARIANTARG pvarg; // [rsp+20h] [rbp-19h] BYREF
  VARIANTARG v9; // [rsp+38h] [rbp-1h] BYREF
  VARIANT oldValue; // [rsp+50h] [rbp+17h] BYREF
  VARIANT newValue; // [rsp+70h] [rbp+37h] BYREF
  PSRWLOCK SRWLock; // [rsp+A0h] [rbp+67h] BYREF

  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, (char *)this - 8);
  v4 = SRWLock;
  v5 = (IRawElementProviderSimple *)((char *)this - 136);
  LOBYTE(v5[15].lpVtbl) = 1;
  if ( v4 )
    ReleaseSRWLockExclusive(v4);
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SuppressUIANotificationsInQuietMode>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SuppressUIANotificationsInQuietMode>::GetImpl'::`2'::impl) )
  {
    if ( !UiaClientsAreListening() )
      return;
    VariantInit(&pvarg);
    pvarg.vt = 11;
    pvarg.iVal = -1;
    VariantInit(&v9);
    p_newValue = &newValue;
    p_oldValue = &oldValue;
    newValue = pvarg;
    oldValue = v9;
    goto LABEL_9;
  }
  if ( a2 && UiaClientsAreListening() )
  {
    VariantInit(&pvarg);
    pvarg.vt = 11;
    pvarg.iVal = -1;
    VariantInit(&v9);
    p_newValue = &oldValue;
    p_oldValue = &newValue;
    oldValue = pvarg;
    newValue = v9;
LABEL_9:
    UiaRaiseAutomationPropertyChangedEvent(v5, 30010, p_oldValue, p_newValue);
    VariantClear(&v9);
    UiaRaiseStructureChangedEvent(v5, StructureChangeType_ChildrenBulkAdded, 0, 0);
    UiaRaiseAutomationEvent(v5, 20002);
    VariantClear(&pvarg);
  }
}

```

## disassembly

```asm
0x180060d40  mov     [rsp-8+arg_8], rbx
0x180060d45  mov     [rsp-8+arg_10], rdi
0x180060d4a  push    rbp
0x180060d4b  lea     rbp, [rsp-57h]
0x180060d50  sub     rsp, 90h
0x180060d57  mov     dil, dl
0x180060d5a  mov     rbx, rcx
0x180060d5d  lea     rdx, [rcx-8]
0x180060d61  lea     rcx, [rbp+57h+SRWLock]
0x180060d65  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x180060d6a  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180060d6e  add     rbx, 0FFFFFFFFFFFFFF78h
0x180060d75  mov     byte ptr [rbx+78h], 1
0x180060d79  test    rcx, rcx
0x180060d7c  jz      short loc_180060D84
0x180060d7e  call    cs:__imp_ReleaseSRWLockExclusive
0x180060d84  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SuppressUIANotificationsInQuietMode@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SuppressUIANotificationsInQuietMode@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SuppressUIANotificationsInQuietMode> `wil::Feature<__WilFeatureTraits_Feature_SuppressUIANotificationsInQuietMode>::GetImpl(void)'::`2'::impl
0x180060d8b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SuppressUIANotificationsInQuietMode@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SuppressUIANotificationsInQuietMode>::__private_IsEnabled(void)
0x180060d90  test    al, al
0x180060d92  jz      short loc_180060DFD
0x180060d94  test    dil, dil
0x180060d97  jz      loc_180060E9E
0x180060d9d  call    cs:__imp_UiaClientsAreListening
0x180060da3  test    eax, eax
0x180060da5  jz      loc_180060E9E
0x180060dab  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180060daf  call    cs:__imp_VariantInit
0x180060db5  mov     eax, 0Bh
0x180060dba  lea     rcx, [rbp+57h+var_58]; pvarg
0x180060dbe  mov     word ptr [rbp+57h+pvarg], ax
0x180060dc2  or      eax, 0FFFFFFFFh
0x180060dc5  mov     word ptr [rbp+57h+pvarg+8], ax
0x180060dc9  call    cs:__imp_VariantInit
0x180060dcf  movups  xmm2, xmmword ptr [rbp+57h+var_58]
0x180060dd3  lea     r9, [rbp+57h+oldValue]
0x180060dd7  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x180060ddb  lea     r8, [rbp+57h+newValue]
0x180060ddf  movsd   xmm3, qword ptr [rbp+57h+var_58+10h]
0x180060de4  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x180060de9  movaps  xmmword ptr [rbp+57h+oldValue], xmm0
0x180060ded  movaps  xmmword ptr [rbp+57h+newValue], xmm2
0x180060df1  movsd   qword ptr [rbp+57h+oldValue+10h], xmm1
0x180060df6  movsd   qword ptr [rbp+57h+newValue+10h], xmm3
0x180060dfb  jmp     short loc_180060E5B
0x180060dfd  call    cs:__imp_UiaClientsAreListening
0x180060e03  test    eax, eax
0x180060e05  jz      loc_180060E9E
0x180060e0b  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180060e0f  call    cs:__imp_VariantInit
0x180060e15  mov     eax, 0Bh
0x180060e1a  lea     rcx, [rbp+57h+var_58]; pvarg
0x180060e1e  mov     word ptr [rbp+57h+pvarg], ax
0x180060e22  or      eax, 0FFFFFFFFh
0x180060e25  mov     word ptr [rbp+57h+pvarg+8], ax
0x180060e29  call    cs:__imp_VariantInit
0x180060e2f  movups  xmm2, xmmword ptr [rbp+57h+var_58]
0x180060e33  lea     r9, [rbp+57h+newValue]; newValue
0x180060e37  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x180060e3b  lea     r8, [rbp+57h+oldValue]; oldValue
0x180060e3f  movsd   xmm3, qword ptr [rbp+57h+var_58+10h]
0x180060e44  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x180060e49  movaps  xmmword ptr [rbp+57h+newValue], xmm0
0x180060e4d  movaps  xmmword ptr [rbp+57h+oldValue], xmm2
0x180060e51  movsd   qword ptr [rbp+57h+newValue+10h], xmm1
0x180060e56  movsd   qword ptr [rbp+57h+oldValue+10h], xmm3
0x180060e5b  mov     edx, 753Ah; id
0x180060e60  mov     rcx, rbx; pProvider
0x180060e63  call    cs:__imp_UiaRaiseAutomationPropertyChangedEvent
0x180060e69  lea     rcx, [rbp+57h+var_58]; pvarg
0x180060e6d  call    cs:__imp_VariantClear
0x180060e73  xor     r9d, r9d; cRuntimeIdLen
0x180060e76  xor     r8d, r8d; pRuntimeId
0x180060e79  mov     rcx, rbx; pProvider
0x180060e7c  lea     edx, [r9+3]; structureChangeType
0x180060e80  call    cs:__imp_UiaRaiseStructureChangedEvent
0x180060e86  mov     edx, 4E22h; id
0x180060e8b  mov     rcx, rbx; pProvider
0x180060e8e  call    cs:__imp_UiaRaiseAutomationEvent
0x180060e94  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180060e98  call    cs:__imp_VariantClear
0x180060e9e  lea     r11, [rsp+90h+var_s0]
0x180060ea6  mov     rbx, [r11+18h]
0x180060eaa  mov     rdi, [r11+20h]
0x180060eae  mov     rsp, r11
0x180060eb1  pop     rbp
0x180060eb2  retn
```
