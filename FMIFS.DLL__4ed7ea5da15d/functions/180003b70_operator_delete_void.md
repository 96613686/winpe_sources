# operator delete(void *)

- ea: `0x180003b70`
- end: `0x180003b8f`
- name: `??3@YAXPEAX@Z`
- size: `31`
- prototype: `void __fastcall(void *)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x1800048c0`
- `0x180006d90`
- `0x180008ac0`
- `0x180008de0`

## callees

- `0x180003b70`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180003b87`

## pseudocode

```c
void __fastcall operator delete(void *a1)
{
  if ( a1 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, a1);
}

```

## disassembly

```asm
0x180003b70  test    rcx, rcx
0x180003b73  jz      short locret_180003B8E
0x180003b75  mov     rax, gs:60h
0x180003b7e  mov     r8, rcx
0x180003b81  xor     edx, edx
0x180003b83  mov     rcx, [rax+30h]
0x180003b87  jmp     cs:__imp_RtlFreeHeap
0x180003b8e  retn
```
