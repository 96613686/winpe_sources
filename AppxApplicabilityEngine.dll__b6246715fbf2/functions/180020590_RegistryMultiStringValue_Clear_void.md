# RegistryMultiStringValue::Clear(void)

- ea: `0x180020590`
- end: `0x1800205b1`
- name: `?Clear@RegistryMultiStringValue@@UEAAXXZ`
- size: `33`
- prototype: `void __fastcall(RegistryMultiStringValue *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180020590`
- `0x180025010`

## pseudocode

```c
void __fastcall RegistryMultiStringValue::Clear(RegistryMultiStringValue *this)
{
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 32LL))(*((_QWORD *)this + 1));
}

```

## disassembly

```asm
0x180020590  mov     r8, [rcx+8]
0x180020594  lea     rdx, [rcx+10h]
0x180020598  cmp     qword ptr [rdx+18h], 8
0x18002059d  mov     rax, [r8]
0x1800205a0  jb      short loc_1800205A5
0x1800205a2  mov     rdx, [rdx]
0x1800205a5  mov     rax, [rax+20h]
0x1800205a9  mov     rcx, r8
0x1800205ac  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
