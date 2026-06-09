# MyRemoveRTMemorySection

- ea: `0x18000bf40`
- end: `0x18000bf70`
- name: `MyRemoveRTMemorySection`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000be78`

## callees

- `0x18000bf40`
- `0x18000dd80`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall MyRemoveRTMemorySection(__int64 a1)
{
  if ( pRemoveRTMemorySection )
    return ((__int64 (__fastcall *)(__int64))pRemoveRTMemorySection)(a1);
  InitAVRTMemory();
  return ((__int64 (__fastcall *)(__int64))pRemoveRTMemorySection)(a1);
}

```

## disassembly

```asm
0x18000bf40  push    rbx
0x18000bf42  sub     rsp, 20h
0x18000bf46  mov     rax, cs:?pRemoveRTMemorySection@@3P6AJPEAX@ZEA; long (*pRemoveRTMemorySection)(void *)
0x18000bf4d  mov     rbx, rcx
0x18000bf50  test    rax, rax
0x18000bf53  jz      short loc_18000BF62
0x18000bf55  mov     rcx, rbx
0x18000bf58  add     rsp, 20h
0x18000bf5c  pop     rbx
0x18000bf5d  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf62  call    ?InitAVRTMemory@@YAXXZ; InitAVRTMemory(void)
0x18000bf67  mov     rax, cs:?pRemoveRTMemorySection@@3P6AJPEAX@ZEA; long (*pRemoveRTMemorySection)(void *)
0x18000bf6e  jmp     short loc_18000BF55
```
