# wil::details::MaybeGetExceptionString(exception const &,ushort *,unsigned __int64)

- ea: `0x180004880`
- end: `0x1800048c2`
- name: `?MaybeGetExceptionString@details@wil@@YAXAEBVexception@@PEAG_K@Z`
- size: `66`
- prototype: `void(wil::details *__hidden this, const struct exception *, unsigned __int16 *, unsigned __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a368`
- `0x18000a43a`
- `0x18000a548`
- `0x18000a593`

## callees

- `0x180004880`
- `0x1800053c8`
- `0x18000b010`

## pseudocode

```c
void __fastcall wil::details::MaybeGetExceptionString(
        wil::details *this,
        const struct exception *a2,
        unsigned __int16 *a3)
{
  __int64 v5; // rax

  if ( a2 )
  {
    v5 = (*(__int64 (__fastcall **)(wil::details *))(*(_QWORD *)this + 8LL))(this);
    StringCchPrintfW((unsigned __int16 *)a2, (size_t)a3, (size_t *)L"std::exception: %hs", v5);
  }
}

```

## disassembly

```asm
0x180004880  test    rdx, rdx
0x180004883  jz      short locret_1800048C0
0x180004885  mov     [rsp+arg_0], rbx
0x18000488a  push    rdi
0x18000488b  sub     rsp, 20h
0x18000488f  mov     rax, [rcx]
0x180004892  mov     rdi, r8
0x180004895  mov     rbx, rdx
0x180004898  mov     rax, [rax+8]
0x18000489c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048a1  mov     r9, rax
0x1800048a4  lea     r8, aStdExceptionHs; "std::exception: %hs"
0x1800048ab  mov     rdx, rdi; unsigned __int64
0x1800048ae  mov     rcx, rbx; unsigned __int16 *
0x1800048b1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800048b6  mov     rbx, [rsp+28h+arg_0]
0x1800048bb  add     rsp, 20h
0x1800048bf  pop     rdi
0x1800048c0  retn
```
