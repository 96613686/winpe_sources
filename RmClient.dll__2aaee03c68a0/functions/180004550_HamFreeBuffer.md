# HamFreeBuffer

- ea: `0x180004550`
- end: `0x180004569`
- name: `HamFreeBuffer`
- size: `25`
- prototype: `BOOLEAN __fastcall(void *)`
- caller_count: `14`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800011a0`
- `0x180003af0`
- `0x180003b50`
- `0x180003c1c`
- `0x180003de0`
- `0x1800041e0`
- `0x1800042d0`
- `0x180009ad0`
- `0x18000bed0`
- `0x18000dd40`
- `0x180010650`
- `0x180011f30`
- `0x180019620`
- `0x18001ab44`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180004562`

## pseudocode

```c
BOOLEAN __fastcall HamFreeBuffer(void *a1)
{
  return RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, a1);
}

```

## disassembly

```asm
0x180004550  mov     rax, gs:60h; CrmActivityFreeWindowClosedReasons
0x180004559  mov     r8, rcx
0x18000455c  xor     edx, edx
0x18000455e  mov     rcx, [rax+30h]
0x180004562  jmp     cs:__imp_RtlFreeHeap
```
