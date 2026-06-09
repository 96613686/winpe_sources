# wil::details::MaybeGetExceptionString(std::exception const &,ushort *,unsigned __int64)

- ea: `0x180008954`
- end: `0x180008995`
- name: `?MaybeGetExceptionString@details@wil@@YAXAEBVexception@std@@PEAG_K@Z`
- size: `65`
- prototype: `void(wil::details *__hidden this, const struct std::exception *, unsigned __int16 *, unsigned __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b42d`
- `0x18000b4ff`
- `0x18000b60d`
- `0x18000b658`

## callees

- `0x180008954`
- `0x180009728`
- `0x18000c010`

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
0x180008954  test    rdx, rdx
0x180008957  jz      short locret_180008994
0x180008959  mov     [rsp+arg_0], rbx
0x18000895e  push    rdi
0x18000895f  sub     rsp, 20h
0x180008963  mov     rax, [rcx]
0x180008966  mov     rdi, r8
0x180008969  mov     rbx, rdx
0x18000896c  mov     rax, [rax+8]
0x180008970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008975  mov     r9, rax
0x180008978  lea     r8, aStdExceptionHs; "std::exception: %hs"
0x18000897f  mov     rdx, rdi; unsigned __int64
0x180008982  mov     rcx, rbx; unsigned __int16 *
0x180008985  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000898a  mov     rbx, [rsp+28h+arg_0]
0x18000898f  add     rsp, 20h
0x180008993  pop     rdi
0x180008994  retn
```
