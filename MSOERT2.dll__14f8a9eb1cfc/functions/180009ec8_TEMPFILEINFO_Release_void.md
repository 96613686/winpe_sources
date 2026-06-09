# TEMPFILEINFO::Release(void)

- ea: `0x180009ec8`
- end: `0x180009ee6`
- name: `?Release@TEMPFILEINFO@@QEAAXXZ`
- size: `30`
- prototype: `void __fastcall(TEMPFILEINFO *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180009220`
- `0x180009240`

## callees

- `0x180009ec8`
- `0x180014010`

## pseudocode

```c
void __fastcall TEMPFILEINFO::Release(TEMPFILEINFO *this)
{
  if ( this )
    (**(void (__fastcall ***)(TEMPFILEINFO *, __int64))this)(this, 1);
}

```

## disassembly

```asm
0x180009ec8  sub     rsp, 28h
0x180009ecc  test    rcx, rcx
0x180009ecf  jz      short loc_180009EE1
0x180009ed1  mov     rax, [rcx]
0x180009ed4  mov     edx, 1
0x180009ed9  mov     rax, [rax]
0x180009edc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ee1  add     rsp, 28h
0x180009ee5  retn
```
