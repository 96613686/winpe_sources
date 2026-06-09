# SafeAllocaAllocateFromHeap

- ea: `0x180004200`
- end: `0x180004219`
- name: `SafeAllocaAllocateFromHeap`
- size: `25`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `51`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001590`
- `0x180001dd0`
- `0x180002bd0`
- `0x180002de0`
- `0x1800030a0`
- `0x180006bd0`
- `0x1800070d0`
- `0x180008890`
- `0x1800090a0`
- `0x180009570`
- `0x18000997c`
- `0x18000a230`
- `0x18000a3e8`
- `0x18000b680`
- `0x18000dac4`
- `0x18000e368`
- `0x18000e628`
- `0x18000e910`
- `0x18000edac`
- `0x18000f1fc`
- `0x180012780`
- `0x180012a70`
- `0x180012cc4`
- `0x180012f40`
- `0x180013330`
- `0x180013510`
- `0x180013720`
- `0x1800138c0`
- `0x180013fd4`
- `0x180014990`
- `0x180014f98`
- `0x180015a7c`
- `0x180015db4`
- `0x1800164bc`
- `0x180016564`
- `0x1800168c8`
- `0x180016b60`
- `0x180016efc`
- `0x1800171b4`
- `0x180017420`
- `0x1800186e0`
- `0x180018860`
- `0x180018a00`
- `0x180018b80`
- `0x180018e90`
- `0x180019070`
- `0x1800192a0`
- `0x1800195e0`
- `0x180019770`
- `0x180019a00`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180004212`

## pseudocode

```c
PVOID __fastcall SafeAllocaAllocateFromHeap(SIZE_T a1)
{
  return RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, a1);
}

```

## disassembly

```asm
0x180004200  mov     rax, gs:60h
0x180004209  mov     r8, rcx
0x18000420c  xor     edx, edx
0x18000420e  mov     rcx, [rax+30h]
0x180004212  jmp     cs:__imp_RtlAllocateHeap
```
