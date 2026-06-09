# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x18000b17c`
- end: `0x18000b252`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `214`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180009f68`

## callees

- `0x180007b30`
- `0x18000b17c`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Write(
        wil::details_abi::UsageIndexProperty *this,
        char **a2,
        char *a3)
{
  char *v5; // rcx
  char *v7; // rbx
  char *v8; // r8
  rsize_t v9; // r9
  rsize_t v10; // rdx
  unsigned __int16 *v11; // r14
  rsize_t v12; // r9
  bool result; // al
  __int16 v14; // [rsp+60h] [rbp+8h] BYREF

  v5 = *a2;
  if ( *((_BYTE *)this + 2) == 1 )
  {
    v7 = v5 + 2;
    if ( v5 + 2 > a3 )
      return 0;
    v8 = (char *)&v14;
    v9 = 2;
    v14 = *((_WORD *)this + 2);
    v10 = 2;
  }
  else
  {
    v7 = *a2;
    if ( *((_BYTE *)this + 2) != 2 )
      goto LABEL_8;
    v7 = v5 + 4;
    if ( v5 + 4 > a3 )
      return 0;
    v10 = 4;
    v8 = (char *)this + 4;
    v9 = 4;
  }
  memcpy_s(v5, v10, v8, v9);
LABEL_8:
  if ( !*(_WORD *)this )
  {
    if ( v7 + 2 <= a3 )
    {
      v11 = (unsigned __int16 *)((char *)this + 8);
      memcpy_s(v7, a3 - v7, (char *)this + 8, 2u);
      v7 += 2;
      goto LABEL_12;
    }
    return 0;
  }
  v11 = (unsigned __int16 *)((char *)this + 8);
LABEL_12:
  v12 = *v11;
  if ( &v7[v12] > a3 )
    return 0;
  memcpy_s(v7, a3 - v7, *((const void *const *)this + 3), v12);
  result = 1;
  *a2 = &v7[*v11];
  return result;
}

```

## disassembly

```asm
0x18000b17c  push    rbx
0x18000b17e  push    rsi
0x18000b17f  push    rdi
0x18000b180  push    r12
0x18000b182  push    r14
0x18000b184  push    r15
0x18000b186  sub     rsp, 28h
0x18000b18a  mov     rsi, rcx
0x18000b18d  mov     rdi, r8
0x18000b190  mov     rcx, [rdx]; Destination
0x18000b193  mov     r12, rdx
0x18000b196  cmp     byte ptr [rsi+2], 1
0x18000b19a  jnz     short loc_18000B1BE
0x18000b19c  lea     rbx, [rcx+2]
0x18000b1a0  cmp     rbx, r8
0x18000b1a3  ja      short loc_18000B221
0x18000b1a5  movzx   eax, word ptr [rsi+4]
0x18000b1a9  lea     r8, [rsp+58h+arg_0]
0x18000b1ae  mov     r9d, 2
0x18000b1b4  mov     [rsp+58h+arg_0], ax
0x18000b1b9  mov     edx, r9d
0x18000b1bc  jmp     short loc_18000B1DC
0x18000b1be  cmp     byte ptr [rsi+2], 2
0x18000b1c2  mov     rbx, rcx
0x18000b1c5  jnz     short loc_18000B1E1
0x18000b1c7  lea     rbx, [rcx+4]
0x18000b1cb  cmp     rbx, rdi
0x18000b1ce  ja      short loc_18000B221
0x18000b1d0  mov     edx, 4; DestinationSize
0x18000b1d5  lea     r8, [rsi+4]; Source
0x18000b1d9  mov     r9d, edx; SourceSize
0x18000b1dc  call    memcpy_s
0x18000b1e1  cmp     word ptr [rsi], 0
0x18000b1e5  jnz     short loc_18000B210
0x18000b1e7  lea     r15, [rbx+2]
0x18000b1eb  cmp     r15, rdi
0x18000b1ee  ja      short loc_18000B221
0x18000b1f0  lea     r14, [rsi+8]
0x18000b1f4  mov     rdx, rdi
0x18000b1f7  sub     rdx, rbx; DestinationSize
0x18000b1fa  mov     r8, r14; Source
0x18000b1fd  mov     r9d, 2; SourceSize
0x18000b203  mov     rcx, rbx; Destination
0x18000b206  call    memcpy_s
0x18000b20b  mov     rbx, r15
0x18000b20e  jmp     short loc_18000B214
0x18000b210  lea     r14, [rsi+8]
0x18000b214  movzx   r9d, word ptr [r14]; SourceSize
0x18000b218  lea     rax, [r9+rbx]
0x18000b21c  cmp     rax, rdi
0x18000b21f  jbe     short loc_18000B225
0x18000b221  xor     al, al
0x18000b223  jmp     short loc_18000B244
0x18000b225  mov     r8, [rsi+18h]; Source
0x18000b229  sub     rdi, rbx
0x18000b22c  mov     rdx, rdi; DestinationSize
0x18000b22f  mov     rcx, rbx; Destination
0x18000b232  call    memcpy_s
0x18000b237  movzx   ecx, word ptr [r14]
0x18000b23b  mov     al, 1
0x18000b23d  add     rcx, rbx
0x18000b240  mov     [r12], rcx
0x18000b244  add     rsp, 28h
0x18000b248  pop     r15
0x18000b24a  pop     r14
0x18000b24c  pop     r12
0x18000b24e  pop     rdi
0x18000b24f  pop     rsi
0x18000b250  pop     rbx
0x18000b251  retn
```
