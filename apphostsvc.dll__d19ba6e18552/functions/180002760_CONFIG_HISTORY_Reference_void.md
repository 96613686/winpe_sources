# CONFIG_HISTORY::Reference(void)

- ea: `0x180002760`
- end: `0x180002770`
- name: `?Reference@CONFIG_HISTORY@@UEAAXXZ`
- size: `16`
- prototype: `void __fastcall(CONFIG_HISTORY *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000a010`

## pseudocode

```c
void __fastcall CONFIG_HISTORY::Reference(CONFIG_HISTORY *this)
{
  (*(void (__fastcall **)(char *))(*((_QWORD *)this - 1) + 8LL))((char *)this - 8);
}

```

## disassembly

```asm
0x180002760  add     rcx, 0FFFFFFFFFFFFFFF8h
0x180002764  mov     rax, [rcx]
0x180002767  mov     rax, [rax+8]
0x18000276b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
