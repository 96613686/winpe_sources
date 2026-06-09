# AuthHostWebInstance::GetSecurityManager(IWebPlatformSecurityManager * *)

- ea: `0x1400053f0`
- end: `0x140005410`
- name: `?GetSecurityManager@AuthHostWebInstance@@UEAAJPEAPEAUIWebPlatformSecurityManager@@@Z`
- size: `32`
- prototype: `__int64 __fastcall(AuthHostWebInstance *__hidden this, struct IWebPlatformSecurityManager **)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140014010`

## pseudocode

```c
__int64 __fastcall AuthHostWebInstance::GetSecurityManager(
        AuthHostWebInstance *this,
        struct IWebPlatformSecurityManager **a2)
{
  (**(void (__fastcall ***)(AuthHostWebInstance *, GUID *, struct IWebPlatformSecurityManager **))this)(
    this,
    &GUID_49d33aad_f985_4b70_97a0_28eceb6523bf,
    a2);
  return 0;
}

```

## disassembly

```asm
0x1400053f0  sub     rsp, 28h
0x1400053f4  mov     rax, [rcx]
0x1400053f7  mov     r8, rdx
0x1400053fa  lea     rdx, _GUID_49d33aad_f985_4b70_97a0_28eceb6523bf
0x140005401  mov     rax, [rax]
0x140005404  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005409  xor     eax, eax
0x14000540b  add     rsp, 28h
0x14000540f  retn
```
