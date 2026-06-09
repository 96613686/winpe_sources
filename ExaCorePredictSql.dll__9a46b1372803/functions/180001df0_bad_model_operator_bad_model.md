# bad_model::operator=(bad_model &&)

- ea: `0x180001df0`
- end: `0x180001e35`
- name: `??4bad_model@@QEAAAEAV0@$$QEAV0@@Z`
- size: `69`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180001df0`

## import_xrefs

- `VCRUNTIME140!__std_exception_destroy` at `0x180001e0e`
- `VCRUNTIME140!__std_exception_destroy` at `0x180001e0e`
- `VCRUNTIME140!__std_exception_copy` at `0x180001e1c`
- `VCRUNTIME140!__std_exception_copy` at `0x180001e1c`

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
0x180001df0  mov     [rsp+arg_8], rsi; public: class bad_model & bad_model::operator=(class bad_model &&)
0x180001df5  push    rdi
0x180001df6  sub     rsp, 20h
0x180001dfa  mov     rsi, rdx
0x180001dfd  mov     rdi, rcx
0x180001e00  cmp     rcx, rdx
0x180001e03  jz      short loc_180001E27
0x180001e05  add     rcx, 8
0x180001e09  mov     [rsp+28h+arg_0], rbx
0x180001e0e  call    cs:__imp___std_exception_destroy
0x180001e14  lea     rcx, [rsi+8]
0x180001e18  lea     rdx, [rdi+8]
0x180001e1c  call    cs:__imp___std_exception_copy
0x180001e22  mov     rbx, [rsp+28h+arg_0]
0x180001e27  mov     rax, rdi
0x180001e2a  mov     rsi, [rsp+28h+arg_8]
0x180001e2f  add     rsp, 20h
0x180001e33  pop     rdi
0x180001e34  retn
```
