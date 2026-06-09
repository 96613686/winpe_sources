# wil::details::MaybeGetExceptionString(exception const &,ushort *,unsigned __int64)

- ea: `0x140005ac0`
- end: `0x140005b02`
- name: `?MaybeGetExceptionString@details@wil@@YAXAEBVexception@@PEAG_K@Z`
- size: `66`
- prototype: `void(wil::details *__hidden this, const struct exception *, unsigned __int16 *, unsigned __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140009fa2`
- `0x14000a074`
- `0x14000a182`
- `0x14000a1cd`

## callees

- `0x140005ac0`
- `0x140006b88`
- `0x14000b010`

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
0x140005ac0  test    rdx, rdx
0x140005ac3  jz      short locret_140005B00
0x140005ac5  mov     [rsp+arg_0], rbx
0x140005aca  push    rdi
0x140005acb  sub     rsp, 20h
0x140005acf  mov     rax, [rcx]
0x140005ad2  mov     rdi, r8
0x140005ad5  mov     rbx, rdx
0x140005ad8  mov     rax, [rax+8]
0x140005adc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005ae1  mov     r9, rax
0x140005ae4  lea     r8, aStdExceptionHs; "std::exception: %hs"
0x140005aeb  mov     rdx, rdi; unsigned __int64
0x140005aee  mov     rcx, rbx; unsigned __int16 *
0x140005af1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140005af6  mov     rbx, [rsp+28h+arg_0]
0x140005afb  add     rsp, 20h
0x140005aff  pop     rdi
0x140005b00  retn
```
