# bad_model::operator=(bad_model &&)

- ea: `0x182dc2af0`
- end: `0x182dc2b35`
- name: `??4bad_model@@QEAAAEAV0@$$QEAV0@@Z`
- size: `69`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x182dc2af0`

## import_xrefs

- `VCRUNTIME140!__std_exception_destroy` at `0x182dc2b0e`
- `VCRUNTIME140!__std_exception_destroy` at `0x182dc2b0e`
- `VCRUNTIME140!__std_exception_copy` at `0x182dc2b1c`
- `VCRUNTIME140!__std_exception_copy` at `0x182dc2b1c`

## pseudocode

```c
__int64 __fastcall bad_model::operator=(__int64 a1, __int64 a2)
{
  if ( a1 != a2 )
  {
    __std_exception_destroy(a1 + 8);
    __std_exception_copy(a2 + 8);
  }
  return a1;
}

```

## disassembly

```asm
0x182dc2af0  mov     [rsp+arg_8], rsi; public: class bad_model & bad_model::operator=(class bad_model &&)
0x182dc2af5  push    rdi
0x182dc2af6  sub     rsp, 20h
0x182dc2afa  mov     rsi, rdx
0x182dc2afd  mov     rdi, rcx
0x182dc2b00  cmp     rcx, rdx
0x182dc2b03  jz      short loc_182DC2B27
0x182dc2b05  add     rcx, 8
0x182dc2b09  mov     [rsp+28h+arg_0], rbx
0x182dc2b0e  call    cs:__imp___std_exception_destroy
0x182dc2b14  lea     rcx, [rsi+8]
0x182dc2b18  lea     rdx, [rdi+8]
0x182dc2b1c  call    cs:__imp___std_exception_copy
0x182dc2b22  mov     rbx, [rsp+28h+arg_0]
0x182dc2b27  mov     rax, rdi
0x182dc2b2a  mov     rsi, [rsp+28h+arg_8]
0x182dc2b2f  add     rsp, 20h
0x182dc2b33  pop     rdi
0x182dc2b34  retn
```
