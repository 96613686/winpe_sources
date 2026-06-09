# CPbList<CHookThreadItem>::~CPbList<CHookThreadItem>(void)

- ea: `0x18000bf8c`
- end: `0x18000bff9`
- name: `??1?$CPbList@UCHookThreadItem@@@@QEAA@XZ`
- size: `109`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000f310`

## callees

- `0x18000bf8c`
- `0x18000ce0c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CPbList<CHookThreadItem>::~CPbList<CHookThreadItem>(_QWORD *a1)
{
  _QWORD *v2; // rbx
  _QWORD *v3; // rsi
  _QWORD *v4; // rcx

  v2 = (_QWORD *)*a1;
  while ( v2 )
  {
    v3 = v2;
    v2 = (_QWORD *)v2[14];
    v4 = (_QWORD *)v3[5];
    if ( v4 && v4 != v3 + 3 )
      operator delete(v4);
    operator delete(v3);
  }
  a1[1] = 0;
  *a1 = 0;
}

```

## disassembly

```asm
0x18000bf8c  mov     [rsp+arg_10], rbx
0x18000bf91  mov     [rsp+arg_18], rsi
0x18000bf96  push    rdi
0x18000bf97  sub     rsp, 20h
0x18000bf9b  mov     rdi, rcx
0x18000bf9e  mov     rbx, [rcx]
0x18000bfa1  jmp     short loc_18000BFDD
0x18000bfa3  mov     rsi, rbx
0x18000bfa6  mov     rbx, [rbx+70h]
0x18000bfaa  mov     [rsp+28h+arg_0], rsi
0x18000bfaf  mov     [rsp+28h+arg_8], rsi
0x18000bfb4  lea     rax, [rsi+18h]
0x18000bfb8  mov     rcx, [rax+10h]; Block
0x18000bfbc  test    rcx, rcx
0x18000bfbf  jz      short loc_18000BFD0
0x18000bfc1  cmp     rcx, rax
0x18000bfc4  jz      short loc_18000BFD0
0x18000bfc6  mov     edx, 8
0x18000bfcb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000bfd0  mov     edx, 78h ; 'x'
0x18000bfd5  mov     rcx, rsi; Block
0x18000bfd8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000bfdd  test    rbx, rbx
0x18000bfe0  jnz     short loc_18000BFA3
0x18000bfe2  and     [rdi+8], rbx
0x18000bfe6  and     [rdi], rbx
0x18000bfe9  mov     rbx, [rsp+28h+arg_10]
0x18000bfee  mov     rsi, [rsp+28h+arg_18]
0x18000bff3  add     rsp, 20h
0x18000bff7  pop     rdi
0x18000bff8  retn
```
