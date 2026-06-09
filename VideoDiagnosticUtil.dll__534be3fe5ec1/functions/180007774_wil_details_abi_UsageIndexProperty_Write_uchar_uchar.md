# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x180007774`
- end: `0x180007864`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `240`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180005db4`

## callees

- `0x180007774`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800077d8`
- `msvcrt!memcpy_s` at `0x180007809`
- `msvcrt!memcpy_s` at `0x18000783c`
- `msvcrt!memcpy_s` at `0x1800077d8`
- `msvcrt!memcpy_s` at `0x180007809`
- `msvcrt!memcpy_s` at `0x18000783c`

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
0x180007774  push    rbx
0x180007776  push    rsi
0x180007777  push    rdi
0x180007778  push    r12
0x18000777a  push    r14
0x18000777c  push    r15
0x18000777e  sub     rsp, 28h
0x180007782  mov     rsi, rcx
0x180007785  mov     rdi, r8
0x180007788  mov     rcx, [rdx]; Destination
0x18000778b  mov     r12, rdx
0x18000778e  cmp     byte ptr [rsi+2], 1
0x180007792  jnz     short loc_1800077BA
0x180007794  lea     rbx, [rcx+2]
0x180007798  cmp     rbx, r8
0x18000779b  ja      loc_18000782B
0x1800077a1  movzx   eax, word ptr [rsi+4]
0x1800077a5  lea     r8, [rsp+58h+arg_0]
0x1800077aa  mov     r9d, 2
0x1800077b0  mov     [rsp+58h+arg_0], ax
0x1800077b5  mov     edx, r9d
0x1800077b8  jmp     short loc_1800077D8
0x1800077ba  cmp     byte ptr [rsi+2], 2
0x1800077be  mov     rbx, rcx
0x1800077c1  jnz     short loc_1800077E4
0x1800077c3  lea     rbx, [rcx+4]
0x1800077c7  cmp     rbx, rdi
0x1800077ca  ja      short loc_18000782B
0x1800077cc  mov     edx, 4; DestinationSize
0x1800077d1  lea     r8, [rsi+4]; Source
0x1800077d5  mov     r9d, edx; SourceSize
0x1800077d8  call    cs:__imp_memcpy_s
0x1800077df  nop     dword ptr [rax+rax+00h]
0x1800077e4  cmp     word ptr [rsi], 0
0x1800077e8  jnz     short loc_18000781A
0x1800077ea  lea     r15, [rbx+2]
0x1800077ee  cmp     r15, rdi
0x1800077f1  ja      short loc_18000782B
0x1800077f3  lea     r14, [rsi+8]
0x1800077f7  mov     rdx, rdi
0x1800077fa  sub     rdx, rbx; DestinationSize
0x1800077fd  mov     r8, r14; Source
0x180007800  mov     r9d, 2; SourceSize
0x180007806  mov     rcx, rbx; Destination
0x180007809  call    cs:__imp_memcpy_s
0x180007810  nop     dword ptr [rax+rax+00h]
0x180007815  mov     rbx, r15
0x180007818  jmp     short loc_18000781E
0x18000781a  lea     r14, [rsi+8]
0x18000781e  movzx   r9d, word ptr [r14]; SourceSize
0x180007822  lea     rax, [r9+rbx]
0x180007826  cmp     rax, rdi
0x180007829  jbe     short loc_18000782F
0x18000782b  xor     al, al
0x18000782d  jmp     short loc_180007855
0x18000782f  mov     r8, [rsi+18h]; Source
0x180007833  sub     rdi, rbx
0x180007836  mov     rdx, rdi; DestinationSize
0x180007839  mov     rcx, rbx; Destination
0x18000783c  call    cs:__imp_memcpy_s
0x180007843  nop     dword ptr [rax+rax+00h]
0x180007848  movzx   ecx, word ptr [r14]
0x18000784c  mov     al, 1
0x18000784e  add     rcx, rbx
0x180007851  mov     [r12], rcx
0x180007855  add     rsp, 28h
0x180007859  pop     r15
0x18000785b  pop     r14
0x18000785d  pop     r12
0x18000785f  pop     rdi
0x180007860  pop     rsi
0x180007861  pop     rbx
0x180007862  retn
```
