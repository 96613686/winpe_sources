# wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter>::~unique_ptr<_TOKEN_USER,wil::details::token_info_deleter>(void)

- ea: `0x1800099b0`
- end: `0x1800099d0`
- name: `??1?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000ce04`
- `0x18000ce9c`

## callees

- `0x180001c90`
- `0x1800099b0`

## pseudocode

```c
void __fastcall wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter>::~unique_ptr<_TOKEN_USER,wil::details::token_info_deleter>(
        void **a1)
{
  void *v1; // rax

  v1 = *a1;
  *a1 = 0;
  if ( v1 )
    operator delete(v1);
}

```

## disassembly

```asm
0x1800099b0  sub     rsp, 28h
0x1800099b4  mov     rax, [rcx]
0x1800099b7  mov     qword ptr [rcx], 0
0x1800099be  test    rax, rax
0x1800099c1  jz      short loc_1800099CB
0x1800099c3  mov     rcx, rax; Block
0x1800099c6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800099cb  add     rsp, 28h
0x1800099cf  retn
```
