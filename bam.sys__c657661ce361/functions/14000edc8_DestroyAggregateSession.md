# DestroyAggregateSession

- ea: `0x14000edc8`
- end: `0x14000ee0c`
- name: `DestroyAggregateSession`
- size: `68`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14000ec90`
- `0x14000ef90`
- `0x14000f0c0`

## callees

- `0x14000eb58`
- `0x14000edc8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000ede8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000edf9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ede8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000edf9`

## pseudocode

```c
void __fastcall DestroyAggregateSession(_QWORD *P, __int64 a2, __int64 a3)
{
  void *v4; // rcx

  if ( P )
  {
    CancelTimerCallbacksAndDeleteTimer((__int64)P, a2, a3);
    v4 = (void *)P[33];
    if ( v4 )
      ExFreePoolWithTag(v4, 0);
    ExFreePoolWithTag(P, 0);
  }
}

```

## disassembly

```asm
0x14000edc8  test    rcx, rcx
0x14000edcb  jz      short locret_14000EE0A
0x14000edcd  push    rbx
0x14000edce  sub     rsp, 20h
0x14000edd2  mov     rbx, rcx
0x14000edd5  call    CancelTimerCallbacksAndDeleteTimer
0x14000edda  mov     rcx, [rbx+108h]; P
0x14000ede1  test    rcx, rcx
0x14000ede4  jz      short loc_14000EDF4
0x14000ede6  xor     edx, edx; Tag
0x14000ede8  call    cs:__imp_ExFreePoolWithTag
0x14000edef  nop     dword ptr [rax+rax+00h]
0x14000edf4  xor     edx, edx; Tag
0x14000edf6  mov     rcx, rbx; P
0x14000edf9  call    cs:__imp_ExFreePoolWithTag
0x14000ee00  nop     dword ptr [rax+rax+00h]
0x14000ee05  add     rsp, 20h
0x14000ee09  pop     rbx
0x14000ee0a  retn
```
