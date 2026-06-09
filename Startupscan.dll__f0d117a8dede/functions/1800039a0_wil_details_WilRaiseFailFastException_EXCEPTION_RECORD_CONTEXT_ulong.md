# wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x1800039a0`
- end: `0x1800039c3`
- name: `?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `35`
- prototype: `void __fastcall __noreturn(struct _EXCEPTION_RECORD *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800038f0`

## callees

- `0x1800039a0`
- `0x180005010`

## pseudocode

```c
void __fastcall __noreturn wil::details::WilRaiseFailFastException(
        struct _EXCEPTION_RECORD *this,
        struct _EXCEPTION_RECORD *a2,
        struct _CONTEXT *a3)
{
  if ( wil::details::g_pfnRaiseFailFastException )
    wil::details::g_pfnRaiseFailFastException(this, 0, (unsigned int)a3);
  __fastfail(7u);
}

```

## disassembly

```asm
0x1800039a0  sub     rsp, 28h
0x1800039a4  mov     rax, cs:?g_pfnRaiseFailFastException@details@wil@@3P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZEA; void (*wil::details::g_pfnRaiseFailFastException)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x1800039ab  test    rax, rax
0x1800039ae  jz      short loc_1800039B7
0x1800039b0  xor     edx, edx
0x1800039b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039b7  mov     ecx, 7
0x1800039bc  int     29h; Win8: RtlFailFast(ecx)
0x1800039be  add     rsp, 28h
0x1800039c2  retn
```
