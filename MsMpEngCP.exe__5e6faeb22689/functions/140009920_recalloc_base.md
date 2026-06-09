# _recalloc_base

- ea: `0x140009920`
- end: `0x1400099b5`
- name: `_recalloc_base`
- size: `149`
- prototype: `void *__cdecl(void *Block, size_t Count, size_t Size)`
- caller_count: `4`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x14000542c`
- `0x140006db4`
- `0x140007d40`
- `0x1400099c0`

## callees

- `0x14000689c`
- `0x140009920`
- `0x14000b490`
- `0x14000b4e0`
- `0x14000d030`

## pseudocode

```c
void *__cdecl recalloc_base(void *Block, size_t Count, size_t Size)
{
  size_t v7; // rdi
  size_t v8; // rbx
  char *v9; // rax
  void *v10; // rsi

  if ( Count && 0xFFFFFFFFFFFFFFE0uLL / Count < Size )
  {
    *(_DWORD *)sub_14000689C() = 12;
    return 0;
  }
  else
  {
    if ( Block )
      v7 = msize(Block);
    else
      v7 = 0;
    v8 = Size * Count;
    v9 = (char *)realloc_base(Block, v8);
    v10 = v9;
    if ( v9 )
    {
      if ( v7 < v8 )
        sub_14000D030((__m128i *)&v9[v7], 0, v8 - v7);
    }
    return v10;
  }
}

```

## disassembly

```asm
0x140009920  mov     [rsp+arg_0], rbx
0x140009925  mov     [rsp+arg_8], rbp
0x14000992a  mov     [rsp+arg_10], rsi
0x14000992f  push    rdi
0x140009930  sub     rsp, 20h
0x140009934  mov     rbp, r8
0x140009937  mov     rbx, rdx
0x14000993a  mov     rsi, rcx
0x14000993d  test    rdx, rdx
0x140009940  jz      short loc_14000995F
0x140009942  xor     edx, edx
0x140009944  lea     rax, [rdx-20h]
0x140009948  div     rbx
0x14000994b  cmp     rax, r8
0x14000994e  jnb     short loc_14000995F
0x140009950  call    sub_14000689C
0x140009955  mov     dword ptr [rax], 0Ch
0x14000995b  xor     eax, eax
0x14000995d  jmp     short loc_1400099A0
0x14000995f  test    rsi, rsi
0x140009962  jz      short loc_14000996E
0x140009964  call    _msize
0x140009969  mov     rdi, rax
0x14000996c  jmp     short loc_140009970
0x14000996e  xor     edi, edi
0x140009970  imul    rbx, rbp
0x140009974  mov     rcx, rsi; Block
0x140009977  mov     rdx, rbx; Size
0x14000997a  call    _realloc_base
0x14000997f  mov     rsi, rax
0x140009982  test    rax, rax
0x140009985  jz      short loc_14000999D
0x140009987  cmp     rdi, rbx
0x14000998a  jnb     short loc_14000999D
0x14000998c  sub     rbx, rdi
0x14000998f  lea     rcx, [rax+rdi]
0x140009993  mov     r8, rbx
0x140009996  xor     edx, edx
0x140009998  call    sub_14000D030
0x14000999d  mov     rax, rsi
0x1400099a0  mov     rbx, [rsp+28h+arg_0]
0x1400099a5  mov     rbp, [rsp+28h+arg_8]
0x1400099aa  mov     rsi, [rsp+28h+arg_10]
0x1400099af  add     rsp, 20h
0x1400099b3  pop     rdi
0x1400099b4  retn
```
