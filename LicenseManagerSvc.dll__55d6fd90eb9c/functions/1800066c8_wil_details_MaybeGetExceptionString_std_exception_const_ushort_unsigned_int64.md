# wil::details::MaybeGetExceptionString(std::exception const &,ushort *,unsigned __int64)

- ea: `0x1800066c8`
- end: `0x180006709`
- name: `?MaybeGetExceptionString@details@wil@@YAXAEBVexception@std@@PEAG_K@Z`
- size: `65`
- prototype: `void(wil::details *__hidden this, const struct std::exception *, unsigned __int16 *, unsigned __int64)`
- caller_count: `11`
- callee_count: `3`
- tags: ``

## callers

- `0x18001763f`
- `0x1800176ed`
- `0x1800177fb`
- `0x180017846`
- `0x1800179c8`
- `0x180017a04`
- `0x180017a40`
- `0x180017b6f`
- `0x180017bab`
- `0x180017be7`
- `0x180017c23`

## callees

- `0x180002cd4`
- `0x1800066c8`
- `0x180018010`

## pseudocode

```c
void __fastcall wil::details::MaybeGetExceptionString(
        wil::details *this,
        const struct std::exception *a2,
        unsigned __int16 *a3)
{
  __int64 v5; // rax

  if ( a2 )
  {
    v5 = (*(__int64 (__fastcall **)(wil::details *))(*(_QWORD *)this + 8LL))(this);
    StringCchPrintfW((unsigned __int16 *)a2, (unsigned __int64)a3, L"std::exception: %hs", v5);
  }
}

```

## disassembly

```asm
0x1800066c8  test    rdx, rdx
0x1800066cb  jz      short locret_180006708
0x1800066cd  mov     [rsp+arg_0], rbx
0x1800066d2  push    rdi
0x1800066d3  sub     rsp, 20h
0x1800066d7  mov     rax, [rcx]
0x1800066da  mov     rdi, r8
0x1800066dd  mov     rbx, rdx
0x1800066e0  mov     rax, [rax+8]
0x1800066e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066e9  mov     r9, rax
0x1800066ec  lea     r8, aStdExceptionHs; "std::exception: %hs"
0x1800066f3  mov     rdx, rdi; unsigned __int64
0x1800066f6  mov     rcx, rbx; unsigned __int16 *
0x1800066f9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800066fe  mov     rbx, [rsp+28h+arg_0]
0x180006703  add     rsp, 20h
0x180006707  pop     rdi
0x180006708  retn
```
