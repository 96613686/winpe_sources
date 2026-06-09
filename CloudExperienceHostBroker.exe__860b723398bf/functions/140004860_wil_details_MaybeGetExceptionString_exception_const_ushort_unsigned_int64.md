# wil::details::MaybeGetExceptionString(exception const &,ushort *,unsigned __int64)

- ea: `0x140004860`
- end: `0x1400048a1`
- name: `?MaybeGetExceptionString@details@wil@@YAXAEBVexception@@PEAG_K@Z`
- size: `65`
- prototype: `void __fastcall(wil::details *this, const struct exception *, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140009686`
- `0x140009758`
- `0x140009866`
- `0x1400098b1`

## callees

- `0x140004860`
- `0x1400052c8`
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
0x140004860  test    rdx, rdx
0x140004863  jz      short locret_1400048A0
0x140004865  mov     [rsp+arg_0], rbx
0x14000486a  push    rdi
0x14000486b  sub     rsp, 20h
0x14000486f  mov     rax, [rcx]
0x140004872  mov     rdi, r8
0x140004875  mov     rbx, rdx
0x140004878  mov     rax, [rax+8]
0x14000487c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004881  mov     r9, rax
0x140004884  lea     r8, aStdExceptionHs; "std::exception: %hs"
0x14000488b  mov     rdx, rdi; unsigned __int64
0x14000488e  mov     rcx, rbx; unsigned __int16 *
0x140004891  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140004896  mov     rbx, [rsp+28h+arg_0]
0x14000489b  add     rsp, 20h
0x14000489f  pop     rdi
0x1400048a0  retn
```
