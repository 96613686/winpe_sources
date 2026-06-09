# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x1800140f4`
- end: `0x1800141ca`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `214`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000dd5c`

## callees

- `0x18000dbd8`
- `0x1800140f4`

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
0x1800140f4  push    rbx
0x1800140f6  push    rsi
0x1800140f7  push    rdi
0x1800140f8  push    r12
0x1800140fa  push    r14
0x1800140fc  push    r15
0x1800140fe  sub     rsp, 28h
0x180014102  mov     rsi, rcx
0x180014105  mov     rdi, r8
0x180014108  mov     rcx, [rdx]; Destination
0x18001410b  mov     r12, rdx
0x18001410e  cmp     byte ptr [rsi+2], 1
0x180014112  jnz     short loc_180014136
0x180014114  lea     rbx, [rcx+2]
0x180014118  cmp     rbx, r8
0x18001411b  ja      short loc_180014199
0x18001411d  movzx   eax, word ptr [rsi+4]
0x180014121  lea     r8, [rsp+58h+arg_0]
0x180014126  mov     r9d, 2
0x18001412c  mov     [rsp+58h+arg_0], ax
0x180014131  mov     edx, r9d
0x180014134  jmp     short loc_180014154
0x180014136  cmp     byte ptr [rsi+2], 2
0x18001413a  mov     rbx, rcx
0x18001413d  jnz     short loc_180014159
0x18001413f  lea     rbx, [rcx+4]
0x180014143  cmp     rbx, rdi
0x180014146  ja      short loc_180014199
0x180014148  mov     edx, 4; DestinationSize
0x18001414d  lea     r8, [rsi+4]; Source
0x180014151  mov     r9d, edx; SourceSize
0x180014154  call    memcpy_s
0x180014159  cmp     word ptr [rsi], 0
0x18001415d  jnz     short loc_180014188
0x18001415f  lea     r15, [rbx+2]
0x180014163  cmp     r15, rdi
0x180014166  ja      short loc_180014199
0x180014168  lea     r14, [rsi+8]
0x18001416c  mov     rdx, rdi
0x18001416f  sub     rdx, rbx; DestinationSize
0x180014172  mov     r8, r14; Source
0x180014175  mov     r9d, 2; SourceSize
0x18001417b  mov     rcx, rbx; Destination
0x18001417e  call    memcpy_s
0x180014183  mov     rbx, r15
0x180014186  jmp     short loc_18001418C
0x180014188  lea     r14, [rsi+8]
0x18001418c  movzx   r9d, word ptr [r14]; SourceSize
0x180014190  lea     rax, [r9+rbx]
0x180014194  cmp     rax, rdi
0x180014197  jbe     short loc_18001419D
0x180014199  xor     al, al
0x18001419b  jmp     short loc_1800141BC
0x18001419d  mov     r8, [rsi+18h]; Source
0x1800141a1  sub     rdi, rbx
0x1800141a4  mov     rdx, rdi; DestinationSize
0x1800141a7  mov     rcx, rbx; Destination
0x1800141aa  call    memcpy_s
0x1800141af  movzx   ecx, word ptr [r14]
0x1800141b3  mov     al, 1
0x1800141b5  add     rcx, rbx
0x1800141b8  mov     [r12], rcx
0x1800141bc  add     rsp, 28h
0x1800141c0  pop     r15
0x1800141c2  pop     r14
0x1800141c4  pop     r12
0x1800141c6  pop     rdi
0x1800141c7  pop     rsi
0x1800141c8  pop     rbx
0x1800141c9  retn
```
