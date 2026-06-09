# checked_srwlock::holder<checked_srwlock::ExclusiveTag,checked_srwlock::AcquireTag,1>::~holder<checked_srwlock::ExclusiveTag,checked_srwlock::AcquireTag,1>(void)

- ea: `0x18003be84`
- end: `0x18003bed5`
- name: `??1?$holder@UExclusiveTag@checked_srwlock@@UAcquireTag@2@$00@checked_srwlock@@QEAA@XZ`
- size: `81`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180065a92`
- `0x180065c7e`
- `0x180065d20`

## callees

- `0x1800075e4`
- `0x18003be84`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003bea5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003bea5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003be96`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003be96`

## string_xrefs

- `0x18003bec3`: `onecoreuap\windows\core\isoenvbroker\inc\checked_srwlock.h`

## pseudocode

```c
void __fastcall checked_srwlock::holder<checked_srwlock::ExclusiveTag,checked_srwlock::AcquireTag,1>::~holder<checked_srwlock::ExclusiveTag,checked_srwlock::AcquireTag,1>(
        __int64 *a1)
{
  __int64 v1; // rdi
  int v3; // ebx
  DWORD CurrentThreadId; // ebp
  const char *v5; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v1 = *a1;
  v3 = *(_DWORD *)(*a1 + 8);
  CurrentThreadId = GetCurrentThreadId();
  if ( v3 == CurrentThreadId )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x2C,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\inc\\checked_srwlock.h",
      v5);
  AcquireSRWLockExclusive((PSRWLOCK)v1);
  *(_DWORD *)(v1 + 8) = CurrentThreadId;
  *a1 = -1;
}

```

## disassembly

```asm
0x18003be84  push    rbx
0x18003be86  push    rbp
0x18003be87  push    rsi
0x18003be88  push    rdi
0x18003be89  sub     rsp, 28h
0x18003be8d  mov     rdi, [rcx]
0x18003be90  mov     rsi, rcx
0x18003be93  mov     ebx, [rdi+8]
0x18003be96  call    cs:__imp_GetCurrentThreadId
0x18003be9c  mov     ebp, eax
0x18003be9e  cmp     ebx, eax
0x18003bea0  jz      short loc_18003BEBE
0x18003bea2  mov     rcx, rdi; SRWLock
0x18003bea5  call    cs:__imp_AcquireSRWLockExclusive
0x18003beab  mov     [rdi+8], ebp
0x18003beae  mov     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x18003beb5  add     rsp, 28h
0x18003beb9  pop     rdi
0x18003beba  pop     rsi
0x18003bebb  pop     rbp
0x18003bebc  pop     rbx
0x18003bebd  retn
0x18003bebe  mov     rcx, [rsp+48h]; this
0x18003bec3  lea     r8, aOnecoreuapWind_13; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18003beca  mov     edx, 2Ch ; ','; void *
0x18003becf  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
