# BCryptFree

- ea: `0x1800041d0`
- end: `0x1800041f4`
- name: `BCryptFree`
- size: `36`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `27`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001dd0`
- `0x1800023f0`
- `0x180002bd0`
- `0x1800030a0`
- `0x180004230`
- `0x18000997c`
- `0x18000e910`
- `0x180012780`
- `0x180012f40`
- `0x180013330`
- `0x180013510`
- `0x180013720`
- `0x1800138c0`
- `0x180015a7c`
- `0x180015db4`
- `0x1800186e0`
- `0x180018860`
- `0x180018a00`
- `0x180018b80`
- `0x180018d90`
- `0x180018e90`
- `0x180019070`
- `0x1800192a0`
- `0x1800195e0`
- `0x180019770`
- `0x180019a00`
- `0x180019b1c`

## callees

- `0x1800041d0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800041e7`

## pseudocode

```c
BOOLEAN __fastcall BCryptFree(void *a1)
{
  BOOLEAN result; // al

  if ( a1 )
    return RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, a1);
  return result;
}

```

## disassembly

```asm
0x1800041d0  test    rcx, rcx
0x1800041d3  jz      short locret_1800041F3
0x1800041d5  mov     rax, gs:60h
0x1800041de  mov     r8, rcx
0x1800041e1  xor     edx, edx
0x1800041e3  mov     rcx, [rax+30h]
0x1800041e7  jmp     cs:__imp_RtlFreeHeap
0x1800041f3  retn
```
