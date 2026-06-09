# operator delete[](void *,ISOSHost_MemObj *,char const * const,int)

- ea: `0x1004012d0`
- end: `0x1004012e0`
- name: `??_V@YAXPEAXPEAUISOSHost_MemObj@@QEBDH@Z`
- size: `16`
- prototype: `void __fastcall(void *, struct ISOSHost_MemObj *, const char *const, int)`
- caller_count: `4`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x100475470`
- `0x100475570`
- `0x1004755d0`
- `0x100475ba0`

## pseudocode

```c
void __fastcall operator delete[](void *a1, struct ISOSHost_MemObj *a2, const char *const a3)
{
  (*(void (__fastcall **)(struct ISOSHost_MemObj *, void *))(*(_QWORD *)a2 + 104LL))(a2, a1);
}

```

## disassembly

```asm
0x1004012d0  mov     rax, [rdx]
0x1004012d3  mov     r8, rdx
0x1004012d6  mov     rdx, rcx
0x1004012d9  mov     rcx, r8
0x1004012dc  jmp     qword ptr [rax+68h]
```
