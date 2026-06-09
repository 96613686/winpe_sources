# SID_MAPPER::Dereference(void)

- ea: `0x180002330`
- end: `0x180002340`
- name: `?Dereference@SID_MAPPER@@UEAAXXZ`
- size: `16`
- prototype: `void __fastcall(SID_MAPPER *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x18000a010`

## pseudocode

```c
void __fastcall SID_MAPPER::Dereference(SID_MAPPER *this)
{
  (*(void (__fastcall **)(char *))(*((_QWORD *)this - 1) + 16LL))((char *)this - 8);
}

```

## disassembly

```asm
0x180002330  add     rcx, 0FFFFFFFFFFFFFFF8h
0x180002334  mov     rax, [rcx]
0x180002337  mov     rax, [rax+10h]
0x18000233b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
