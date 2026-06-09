# CTitleBarSysMenuItem::SetExpandCollapseState(ExpandCollapseState,bool)

- ea: `0x180061250`
- end: `0x18006138f`
- name: `?SetExpandCollapseState@CTitleBarSysMenuItem@@AEAAJW4ExpandCollapseState@@_N@Z`
- size: `319`
- prototype: `__int64 __fastcall(CTitleBarSysMenuItem *__hidden this, enum ExpandCollapseState, bool)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005fb10`
- `0x18005fc80`
- `0x1800613a0`

## callees

- `0x180031a20`
- `0x1800335e8`
- `0x180061250`
- `0x180072010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800612b4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800612b4`
- `OLEAUT32!__imp_VariantInit` at `0x1800612e2`
- `OLEAUT32!__imp_VariantInit` at `0x180061302`
- `OLEAUT32!__imp_VariantInit` at `0x1800612e2`
- `OLEAUT32!__imp_VariantInit` at `0x180061302`
- `OLEAUT32!__imp_VariantClear` at `0x180061350`
- `OLEAUT32!__imp_VariantClear` at `0x18006135a`
- `OLEAUT32!__imp_VariantClear` at `0x180061350`
- `OLEAUT32!__imp_VariantClear` at `0x18006135a`
- `UIAutomationCore!UiaClientsAreListening` at `0x1800612e8`
- `UIAutomationCore!UiaClientsAreListening` at `0x1800612e8`
- `UIAutomationCore!UiaRaiseAutomationPropertyChangedEvent` at `0x180061346`
- `UIAutomationCore!UiaRaiseAutomationPropertyChangedEvent` at `0x180061346`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CTitleBarSysMenuItem::SetExpandCollapseState(CTitleBarSysMenuItem *this, unsigned int a2, char a3)
{
  char v6; // r14
  __int64 v7; // rbx
  VARIANTARG pvarg; // [rsp+20h] [rbp-39h] BYREF
  VARIANTARG v10; // [rsp+38h] [rbp-21h] BYREF
  VARIANT newValue; // [rsp+50h] [rbp-9h] BYREF
  VARIANT oldValue; // [rsp+70h] [rbp+17h] BYREF
  __int64 v13; // [rsp+C0h] [rbp+67h] BYREF
  PSRWLOCK SRWLock; // [rsp+D8h] [rbp+7Fh] BYREF

  v6 = 0;
  v7 = 0;
  v13 = 0;
  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, (char *)this + 144);
  if ( *((_DWORD *)this + 40) != a2 )
  {
    *((_DWORD *)this + 40) = a2;
    v6 = 1;
    Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccRootInternal>::operator=(&v13, (char *)this + 56);
    v7 = v13;
  }
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( a3 && v7 )
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v7 + 32LL))(v7, a2);
  if ( v6 )
  {
    VariantInit(&pvarg);
    if ( UiaClientsAreListening() )
    {
      pvarg.vt = 3;
      pvarg.lVal = a2;
      VariantInit(&v10);
      newValue = pvarg;
      oldValue = v10;
      UiaRaiseAutomationPropertyChangedEvent(
        (IRawElementProviderSimple *)(((unsigned __int64)this + 16) & -(__int64)(this != 0)),
        30070,
        &oldValue,
        &newValue);
      VariantClear(&v10);
    }
    VariantClear(&pvarg);
  }
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  return 0;
}

```

## disassembly

```asm
0x180061250  mov     [rsp-8+arg_8], rbx
0x180061255  push    rbp
0x180061256  push    rsi
0x180061257  push    rdi
0x180061258  push    r14
0x18006125a  push    r15
0x18006125c  lea     rbp, [rsp-37h]
0x180061261  sub     rsp, 90h
0x180061268  mov     r15b, r8b
0x18006126b  mov     esi, edx
0x18006126d  mov     rdi, rcx
0x180061270  xor     r14b, r14b
0x180061273  xor     ebx, ebx
0x180061275  mov     [rbp+57h+arg_0], rbx
0x180061279  lea     rdx, [rcx+90h]
0x180061280  lea     rcx, [rbp+57h+SRWLock]
0x180061284  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x180061289  cmp     [rdi+0A0h], esi
0x18006128f  jz      short loc_1800612AB
0x180061291  mov     [rdi+0A0h], esi
0x180061297  mov     r14b, 1
0x18006129a  lea     rdx, [rdi+38h]
0x18006129e  lea     rcx, [rbp+57h+arg_0]
0x1800612a2  call    ??4?$ComPtr@UIApplicationFrameTitleBarAccRootInternal@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccRootInternal>::operator=(Microsoft::WRL::ComPtr<IApplicationFrameTitleBarAccRootInternal> const &)
0x1800612a7  mov     rbx, [rbp+57h+arg_0]
0x1800612ab  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1800612af  test    rcx, rcx
0x1800612b2  jz      short loc_1800612BA
0x1800612b4  call    cs:__imp_ReleaseSRWLockExclusive
0x1800612ba  test    r15b, r15b
0x1800612bd  jz      short loc_1800612D5
0x1800612bf  test    rbx, rbx
0x1800612c2  jz      short loc_1800612D5
0x1800612c4  mov     rax, [rbx]
0x1800612c7  mov     edx, esi
0x1800612c9  mov     rcx, rbx
0x1800612cc  mov     rax, [rax+20h]
0x1800612d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800612d5  test    r14b, r14b
0x1800612d8  jz      loc_180061361
0x1800612de  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800612e2  call    cs:__imp_VariantInit
0x1800612e8  call    cs:__imp_UiaClientsAreListening
0x1800612ee  test    eax, eax
0x1800612f0  jz      short loc_180061356
0x1800612f2  mov     eax, 3
0x1800612f7  mov     word ptr [rbp+57h+pvarg], ax
0x1800612fb  mov     dword ptr [rbp+57h+pvarg+8], esi
0x1800612fe  lea     rcx, [rbp+57h+var_78]; pvarg
0x180061302  call    cs:__imp_VariantInit
0x180061308  movups  xmm2, xmmword ptr [rbp+57h+var_78]
0x18006130c  movsd   xmm3, qword ptr [rbp+57h+var_78+10h]
0x180061311  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x180061315  movaps  xmmword ptr [rbp+57h+newValue], xmm0
0x180061319  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x18006131e  movsd   qword ptr [rbp+57h+newValue+10h], xmm1
0x180061323  movaps  xmmword ptr [rbp+57h+oldValue], xmm2
0x180061327  movsd   qword ptr [rbp+57h+oldValue+10h], xmm3
0x18006132c  lea     rax, [rdi+10h]
0x180061330  neg     rdi
0x180061333  sbb     rcx, rcx
0x180061336  and     rcx, rax; pProvider
0x180061339  lea     r9, [rbp+57h+newValue]; newValue
0x18006133d  lea     r8, [rbp+57h+oldValue]; oldValue
0x180061341  mov     edx, 7576h; id
0x180061346  call    cs:__imp_UiaRaiseAutomationPropertyChangedEvent
0x18006134c  lea     rcx, [rbp+57h+var_78]; pvarg
0x180061350  call    cs:__imp_VariantClear
0x180061356  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18006135a  call    cs:__imp_VariantClear
0x180061360  nop
0x180061361  test    rbx, rbx
0x180061364  jz      short loc_180061376
0x180061366  mov     rax, [rbx]
0x180061369  mov     rcx, rbx
0x18006136c  mov     rax, [rax+10h]
0x180061370  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061375  nop
0x180061376  xor     eax, eax
0x180061378  mov     rbx, [rsp+0B0h+arg_8]
0x180061380  add     rsp, 90h
0x180061387  pop     r15
0x180061389  pop     r14
0x18006138b  pop     rdi
0x18006138c  pop     rsi
0x18006138d  pop     rbp
0x18006138e  retn
```
