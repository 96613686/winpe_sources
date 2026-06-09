# FltpCompletePhase2Init

- ea: `0x180051060`
- end: `0x1800510f4`
- name: `FltpCompletePhase2Init`
- size: `148`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18008c078`

## callees

- `0x180051060`
- `0x180051278`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x1800510e0`
- `ntoskrnl!KeInitializeSpinLock` at `0x1800510e0`
- `ntoskrnl!ExAllocateCacheAwarePushLock` at `0x180051069`
- `ntoskrnl!ExAllocateCacheAwarePushLock` at `0x180051069`
- `ntoskrnl!ExInitializeFastResource` at `0x1800510a3`
- `ntoskrnl!ExInitializeFastResource` at `0x1800510a3`

## pseudocode

```c
__int64 FltpCompletePhase2Init()
{
  qword_18003EF20 = ExAllocateCacheAwarePushLock(1);
  if ( !qword_18003EF20 )
    return 3221225626LL;
  FltpInitLookasideLists();
  dword_18003ED90 = 0;
  ExInitializeFastResource(qword_18003ED18, 8);
  qword_18003ED88 = (__int64)&qword_18003ED80;
  qword_18003ED80 = (__int64)&qword_18003ED80;
  qword_180040300 = (__int64)&qword_1800402F8;
  qword_1800402F8 = (__int64)&qword_1800402F8;
  KeInitializeSpinLock(&qword_180040308);
  return 0;
}

```

## disassembly

```asm
0x180051060  sub     rsp, 28h
0x180051064  mov     ecx, 1
0x180051069  call    cs:__imp_ExAllocateCacheAwarePushLock
0x180051070  nop     dword ptr [rax+rax+00h]
0x180051075  mov     cs:qword_18003EF20, rax
0x18005107c  test    rax, rax
0x18005107f  jnz     short loc_180051088
0x180051081  mov     eax, 0C000009Ah
0x180051086  jmp     short loc_1800510EE
0x180051088  call    FltpInitLookasideLists
0x18005108d  mov     edx, 8
0x180051092  mov     cs:dword_18003ED90, 0
0x18005109c  lea     rcx, qword_18003ED18
0x1800510a3  call    cs:__imp_ExInitializeFastResource
0x1800510aa  nop     dword ptr [rax+rax+00h]
0x1800510af  lea     rax, qword_18003ED80
0x1800510b6  mov     cs:qword_18003ED88, rax
0x1800510bd  lea     rcx, qword_180040308; SpinLock
0x1800510c4  mov     cs:qword_18003ED80, rax
0x1800510cb  lea     rax, qword_1800402F8
0x1800510d2  mov     cs:qword_180040300, rax
0x1800510d9  mov     cs:qword_1800402F8, rax
0x1800510e0  call    cs:__imp_KeInitializeSpinLock
0x1800510e7  nop     dword ptr [rax+rax+00h]
0x1800510ec  xor     eax, eax
0x1800510ee  add     rsp, 28h
0x1800510f2  retn
```
