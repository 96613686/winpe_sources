# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x1400118c8`
- end: `0x14001199f`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `215`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000d290`

## callees

- `0x140008200`
- `0x1400118c8`

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
0x1400118c8  push    rbx
0x1400118ca  push    rsi
0x1400118cb  push    rdi
0x1400118cc  push    r12
0x1400118ce  push    r14
0x1400118d0  push    r15
0x1400118d2  sub     rsp, 28h
0x1400118d6  mov     rsi, rcx
0x1400118d9  mov     rdi, r8
0x1400118dc  mov     rcx, [rdx]; Destination
0x1400118df  mov     r12, rdx
0x1400118e2  cmp     byte ptr [rsi+2], 1
0x1400118e6  jnz     short loc_14001190A
0x1400118e8  lea     rbx, [rcx+2]
0x1400118ec  cmp     rbx, r8
0x1400118ef  ja      short loc_14001196D
0x1400118f1  movzx   eax, word ptr [rsi+4]
0x1400118f5  lea     r8, [rsp+58h+arg_0]
0x1400118fa  mov     r9d, 2
0x140011900  mov     [rsp+58h+arg_0], ax
0x140011905  mov     edx, r9d
0x140011908  jmp     short loc_140011928
0x14001190a  cmp     byte ptr [rsi+2], 2
0x14001190e  mov     rbx, rcx
0x140011911  jnz     short loc_14001192D
0x140011913  lea     rbx, [rcx+4]
0x140011917  cmp     rbx, rdi
0x14001191a  ja      short loc_14001196D
0x14001191c  mov     edx, 4; DestinationSize
0x140011921  lea     r8, [rsi+4]; Source
0x140011925  mov     r9d, edx; SourceSize
0x140011928  call    memcpy_s
0x14001192d  cmp     word ptr [rsi], 0
0x140011931  jnz     short loc_14001195C
0x140011933  lea     r15, [rbx+2]
0x140011937  cmp     r15, rdi
0x14001193a  ja      short loc_14001196D
0x14001193c  lea     r14, [rsi+8]
0x140011940  mov     rdx, rdi
0x140011943  sub     rdx, rbx; DestinationSize
0x140011946  mov     r8, r14; Source
0x140011949  mov     r9d, 2; SourceSize
0x14001194f  mov     rcx, rbx; Destination
0x140011952  call    memcpy_s
0x140011957  mov     rbx, r15
0x14001195a  jmp     short loc_140011960
0x14001195c  lea     r14, [rsi+8]
0x140011960  movzx   r9d, word ptr [r14]; SourceSize
0x140011964  lea     rax, [r9+rbx]
0x140011968  cmp     rax, rdi
0x14001196b  jbe     short loc_140011971
0x14001196d  xor     al, al
0x14001196f  jmp     short loc_140011990
0x140011971  mov     r8, [rsi+18h]; Source
0x140011975  sub     rdi, rbx
0x140011978  mov     rdx, rdi; DestinationSize
0x14001197b  mov     rcx, rbx; Destination
0x14001197e  call    memcpy_s
0x140011983  movzx   ecx, word ptr [r14]
0x140011987  mov     al, 1
0x140011989  add     rcx, rbx
0x14001198c  mov     [r12], rcx
0x140011990  add     rsp, 28h
0x140011994  pop     r15
0x140011996  pop     r14
0x140011998  pop     r12
0x14001199a  pop     rdi
0x14001199b  pop     rsi
0x14001199c  pop     rbx
0x14001199d  retn
```
