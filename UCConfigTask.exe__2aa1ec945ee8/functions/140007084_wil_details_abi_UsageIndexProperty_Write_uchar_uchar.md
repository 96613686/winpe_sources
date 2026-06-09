# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x140007084`
- end: `0x14000715a`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `214`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *this, char **, char *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400059f4`

## callees

- `0x140007084`
- `0x140007a00`

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
0x140007084  push    rbx
0x140007086  push    rsi
0x140007087  push    rdi
0x140007088  push    r12
0x14000708a  push    r14
0x14000708c  push    r15
0x14000708e  sub     rsp, 28h
0x140007092  mov     rsi, rcx
0x140007095  mov     rdi, r8
0x140007098  mov     rcx, [rdx]; Destination
0x14000709b  mov     r12, rdx
0x14000709e  cmp     byte ptr [rsi+2], 1
0x1400070a2  jnz     short loc_1400070C6
0x1400070a4  lea     rbx, [rcx+2]
0x1400070a8  cmp     rbx, r8
0x1400070ab  ja      short loc_140007129
0x1400070ad  movzx   eax, word ptr [rsi+4]
0x1400070b1  lea     r8, [rsp+58h+arg_0]
0x1400070b6  mov     r9d, 2
0x1400070bc  mov     [rsp+58h+arg_0], ax
0x1400070c1  mov     edx, r9d
0x1400070c4  jmp     short loc_1400070E4
0x1400070c6  cmp     byte ptr [rsi+2], 2
0x1400070ca  mov     rbx, rcx
0x1400070cd  jnz     short loc_1400070E9
0x1400070cf  lea     rbx, [rcx+4]
0x1400070d3  cmp     rbx, rdi
0x1400070d6  ja      short loc_140007129
0x1400070d8  mov     edx, 4; DestinationSize
0x1400070dd  lea     r8, [rsi+4]; Source
0x1400070e1  mov     r9d, edx; SourceSize
0x1400070e4  call    memcpy_s
0x1400070e9  cmp     word ptr [rsi], 0
0x1400070ed  jnz     short loc_140007118
0x1400070ef  lea     r15, [rbx+2]
0x1400070f3  cmp     r15, rdi
0x1400070f6  ja      short loc_140007129
0x1400070f8  lea     r14, [rsi+8]
0x1400070fc  mov     rdx, rdi
0x1400070ff  sub     rdx, rbx; DestinationSize
0x140007102  mov     r8, r14; Source
0x140007105  mov     r9d, 2; SourceSize
0x14000710b  mov     rcx, rbx; Destination
0x14000710e  call    memcpy_s
0x140007113  mov     rbx, r15
0x140007116  jmp     short loc_14000711C
0x140007118  lea     r14, [rsi+8]
0x14000711c  movzx   r9d, word ptr [r14]; SourceSize
0x140007120  lea     rax, [r9+rbx]
0x140007124  cmp     rax, rdi
0x140007127  jbe     short loc_14000712D
0x140007129  xor     al, al
0x14000712b  jmp     short loc_14000714C
0x14000712d  mov     r8, [rsi+18h]; Source
0x140007131  sub     rdi, rbx
0x140007134  mov     rdx, rdi; DestinationSize
0x140007137  mov     rcx, rbx; Destination
0x14000713a  call    memcpy_s
0x14000713f  movzx   ecx, word ptr [r14]
0x140007143  mov     al, 1
0x140007145  add     rcx, rbx
0x140007148  mov     [r12], rcx
0x14000714c  add     rsp, 28h
0x140007150  pop     r15
0x140007152  pop     r14
0x140007154  pop     r12
0x140007156  pop     rdi
0x140007157  pop     rsi
0x140007158  pop     rbx
0x140007159  retn
```
