# SSPI_SECURITY_CONTEXT::CleanupStoredContext(void)

- ea: `0x180001d50`
- end: `0x180001d6f`
- name: `?CleanupStoredContext@SSPI_SECURITY_CONTEXT@@UEAAXXZ`
- size: `31`
- prototype: `void __fastcall(SSPI_SECURITY_CONTEXT *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180001d50`
- `0x180007010`

## pseudocode

```c
void __fastcall SSPI_SECURITY_CONTEXT::CleanupStoredContext(SSPI_SECURITY_CONTEXT *this)
{
  if ( this )
    (*(void (__fastcall **)(SSPI_SECURITY_CONTEXT *, __int64))(*(_QWORD *)this + 8LL))(this, 1);
}

```

## disassembly

```asm
0x180001d50  sub     rsp, 28h
0x180001d54  test    rcx, rcx
0x180001d57  jz      short loc_180001D6A
0x180001d59  mov     rax, [rcx]
0x180001d5c  mov     edx, 1
0x180001d61  mov     rax, [rax+8]
0x180001d65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d6a  add     rsp, 28h
0x180001d6e  retn
```
