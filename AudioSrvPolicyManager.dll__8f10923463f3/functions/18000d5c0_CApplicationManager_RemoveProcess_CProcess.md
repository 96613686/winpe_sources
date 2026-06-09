# CApplicationManager::RemoveProcess(CProcess *)

- ea: `0x18000d5c0`
- end: `0x18000d6ad`
- name: `?RemoveProcess@CApplicationManager@@QEAAJPEAVCProcess@@@Z`
- size: `237`
- prototype: `int(CApplicationManager *__hidden this, struct CProcess *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000d328`
- `0x18000d87c`

## callees

- `0x1800088d0`
- `0x18000ccc0`
- `0x18000d5c0`
- `0x18000f5f4`
- `0x180038798`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d5e9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d5e9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d697`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d697`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d659`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d659`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d622`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d622`

## string_xrefs

- `0x18000d682`: `CApplicationManager::RemoveProcess`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CApplicationManager::RemoveProcess(CApplicationManager *this, struct CProcess *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rsi
  char *v5; // r12
  __int64 *i; // r14
  RTL_SRWLOCK *v7; // r15

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  v5 = (char *)this + 128;
  for ( i = (__int64 *)*((_QWORD *)this + 16); i; i = (__int64 *)*i )
  {
    if ( (struct CProcess *)i[2] == a2 )
    {
      v7 = (RTL_SRWLOCK *)((char *)this + 120);
      AcquireSRWLockExclusive(v7);
      ATL::CAtlList<CProcess *,ATL::CElementTraits<CProcess *>>::RemoveAt(v5, i);
      if ( v7 )
        ReleaseSRWLockExclusive(v7);
      if ( a2 )
      {
        CProcess::Cleanup(a2, 0);
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IAudioProcess,IAudioProcessInternal>::Release(a2);
      }
      break;
    }
  }
  if ( v4 )
    LeaveCriticalSection(v4);
  return 0;
}

```

## disassembly

```asm
0x18000d5c0  mov     [rsp+arg_8], rdx
0x18000d5c5  push    rbx
0x18000d5c6  push    rsi
0x18000d5c7  push    rdi
0x18000d5c8  push    r12
0x18000d5ca  push    r14
0x18000d5cc  push    r15
0x18000d5ce  sub     rsp, 38h
0x18000d5d2  mov     rbx, rdx
0x18000d5d5  mov     r15, rcx
0x18000d5d8  xor     edi, edi
0x18000d5da  lea     rsi, [rcx+20h]
0x18000d5de  mov     [rsp+68h+arg_10], rsi
0x18000d5e6  mov     rcx, rsi; lpCriticalSection
0x18000d5e9  call    cs:__imp_EnterCriticalSection
0x18000d5ef  mov     [rsp+68h+var_48], rsi
0x18000d5f4  lea     r12, [r15+80h]
0x18000d5fb  mov     r14, [r12]
0x18000d5ff  test    r14, r14
0x18000d602  jz      loc_18000D68F
0x18000d608  cmp     [r14+10h], rbx
0x18000d60c  jz      short loc_18000D613
0x18000d60e  mov     r14, [r14]
0x18000d611  jmp     short loc_18000D5FF
0x18000d613  add     r15, 78h ; 'x'
0x18000d617  mov     [rsp+68h+arg_18], r15
0x18000d61f  mov     rcx, r15; SRWLock
0x18000d622  call    cs:__imp_AcquireSRWLockExclusive
0x18000d628  xor     edi, edi
0x18000d62a  mov     rdx, r14
0x18000d62d  mov     rcx, r12
0x18000d630  call    ?RemoveAt@?$CAtlList@PEAVCProcess@@V?$CElementTraits@PEAVCProcess@@@ATL@@@ATL@@QEAAXPEAU__POSITION@@@Z; ATL::CAtlList<CProcess *,ATL::CElementTraits<CProcess *>>::RemoveAt(__POSITION *)
0x18000d635  nop
0x18000d636  jmp     short loc_18000D651
0x18000d638  mov     rbx, [rsp+68h+arg_8]
0x18000d63d  mov     edi, [rsp+68h+arg_0]
0x18000d641  mov     rsi, [rsp+68h+arg_10]
0x18000d649  mov     r15, [rsp+68h+arg_18]
0x18000d651  test    r15, r15
0x18000d654  jz      short loc_18000D65F
0x18000d656  mov     rcx, r15; SRWLock
0x18000d659  call    cs:__imp_ReleaseSRWLockExclusive
0x18000d65f  test    rbx, rbx
0x18000d662  jz      short loc_18000D676
0x18000d664  xor     edx, edx; int
0x18000d666  mov     rcx, rbx; this
0x18000d669  call    ?Cleanup@CProcess@@QEAAJH@Z; CProcess::Cleanup(int)
0x18000d66e  mov     rcx, rbx
0x18000d671  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIAudioProcess@@UIAudioProcessInternal@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IAudioProcess,IAudioProcessInternal>::Release(void)
0x18000d676  test    edi, edi
0x18000d678  jns     short loc_18000D68F
0x18000d67a  mov     r8d, edi; int
0x18000d67d  mov     edx, 4F1h; int
0x18000d682  lea     rcx, aCapplicationma_8; "CApplicationManager::RemoveProcess"
0x18000d689  call    ?AudPolicyLogError@@YAXPEBDHJ@Z; AudPolicyLogError(char const *,int,long)
0x18000d68e  nop
0x18000d68f  test    rsi, rsi
0x18000d692  jz      short loc_18000D69D
0x18000d694  mov     rcx, rsi; lpCriticalSection
0x18000d697  call    cs:__imp_LeaveCriticalSection
0x18000d69d  mov     eax, edi
0x18000d69f  add     rsp, 38h
0x18000d6a3  pop     r15
0x18000d6a5  pop     r14
0x18000d6a7  pop     r12
0x18000d6a9  pop     rdi
0x18000d6aa  pop     rsi
0x18000d6ab  pop     rbx
0x18000d6ac  retn
```
