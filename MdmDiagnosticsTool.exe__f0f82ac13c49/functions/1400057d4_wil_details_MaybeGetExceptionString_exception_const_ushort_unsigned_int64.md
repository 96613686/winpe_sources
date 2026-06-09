# wil::details::MaybeGetExceptionString(exception const &,ushort *,unsigned __int64)

- ea: `0x1400057d4`
- end: `0x140005815`
- name: `?MaybeGetExceptionString@details@wil@@YAXAEBVexception@@PEAG_K@Z`
- size: `65`
- prototype: `void __fastcall(wil::details *this, const struct exception *, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x14000996d`
- `0x140009a3f`
- `0x140009b4d`
- `0x140009b98`

## callees

- `0x1400057d4`
- `0x1400067b8`
- `0x14000a010`

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
    StringCchPrintfW((unsigned __int16 *)a2, (unsigned __int64)a3, L"std::exception: %hs", v5);
  }
}

```

## disassembly

```asm
0x1400057d4  test    rdx, rdx
0x1400057d7  jz      short locret_140005814
0x1400057d9  mov     [rsp+arg_0], rbx
0x1400057de  push    rdi
0x1400057df  sub     rsp, 20h
0x1400057e3  mov     rax, [rcx]
0x1400057e6  mov     rdi, r8
0x1400057e9  mov     rbx, rdx
0x1400057ec  mov     rax, [rax+8]
0x1400057f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400057f5  mov     r9, rax
0x1400057f8  lea     r8, aStdExceptionHs; "std::exception: %hs"
0x1400057ff  mov     rdx, rdi; unsigned __int64
0x140005802  mov     rcx, rbx; unsigned __int16 *
0x140005805  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000580a  mov     rbx, [rsp+28h+arg_0]
0x14000580f  add     rsp, 20h
0x140005813  pop     rdi
0x140005814  retn
```
