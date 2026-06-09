# AuthHostWebInstance::GetSecurityHandler(IHttpSecurity * *)

- ea: `0x1400053b0`
- end: `0x1400053d0`
- name: `?GetSecurityHandler@AuthHostWebInstance@@UEAAJPEAPEAUIHttpSecurity@@@Z`
- size: `32`
- prototype: `__int64 __fastcall(AuthHostWebInstance *__hidden this, struct IHttpSecurity **)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140014010`

## pseudocode

```c
__int64 __fastcall AuthHostWebInstance::GetSecurityHandler(AuthHostWebInstance *this, struct IHttpSecurity **a2)
{
  (**(void (__fastcall ***)(AuthHostWebInstance *, GUID *, struct IHttpSecurity **))this)(
    this,
    &GUID_79eac9d7_bafa_11ce_8c82_00aa004ba90b,
    a2);
  return 0;
}

```

## disassembly

```asm
0x1400053b0  sub     rsp, 28h
0x1400053b4  mov     rax, [rcx]
0x1400053b7  mov     r8, rdx
0x1400053ba  lea     rdx, _GUID_79eac9d7_bafa_11ce_8c82_00aa004ba90b
0x1400053c1  mov     rax, [rax]
0x1400053c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400053c9  xor     eax, eax
0x1400053cb  add     rsp, 28h
0x1400053cf  retn
```
