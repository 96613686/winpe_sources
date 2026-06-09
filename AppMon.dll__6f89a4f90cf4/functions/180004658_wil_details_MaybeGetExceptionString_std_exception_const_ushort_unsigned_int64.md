# wil::details::MaybeGetExceptionString(std::exception const &,ushort *,unsigned __int64)

- ea: `0x180004658`
- end: `0x180004699`
- name: `?MaybeGetExceptionString@details@wil@@YAXAEBVexception@std@@PEAG_K@Z`
- size: `65`
- prototype: `void(wil::details *__hidden this, const struct std::exception *, unsigned __int16 *, unsigned __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18000eff6`
- `0x18000f0c8`
- `0x18000f1d6`
- `0x18000f221`

## callees

- `0x180004658`
- `0x18000516c`
- `0x180010010`

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
0x180004658  test    rdx, rdx
0x18000465b  jz      short locret_180004698
0x18000465d  mov     [rsp+arg_0], rbx
0x180004662  push    rdi
0x180004663  sub     rsp, 20h
0x180004667  mov     rax, [rcx]
0x18000466a  mov     rdi, r8
0x18000466d  mov     rbx, rdx
0x180004670  mov     rax, [rax+8]
0x180004674  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004679  mov     r9, rax
0x18000467c  lea     r8, aStdExceptionHs; "std::exception: %hs"
0x180004683  mov     rdx, rdi; unsigned __int64
0x180004686  mov     rcx, rbx; unsigned __int16 *
0x180004689  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000468e  mov     rbx, [rsp+28h+arg_0]
0x180004693  add     rsp, 20h
0x180004697  pop     rdi
0x180004698  retn
```
