# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x1800081cc`
- end: `0x1800082a5`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180006844`

## callees

- `0x1800081cc`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000822c`
- `msvcrt!memcpy_s` at `0x180008257`
- `msvcrt!memcpy_s` at `0x180008284`
- `msvcrt!memcpy_s` at `0x18000822c`
- `msvcrt!memcpy_s` at `0x180008257`
- `msvcrt!memcpy_s` at `0x180008284`

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
0x1800081cc  push    rbx
0x1800081ce  push    rsi
0x1800081cf  push    rdi
0x1800081d0  push    r12
0x1800081d2  push    r14
0x1800081d4  push    r15
0x1800081d6  sub     rsp, 28h
0x1800081da  mov     rsi, rcx
0x1800081dd  mov     rdi, r8
0x1800081e0  mov     rcx, [rdx]; Destination
0x1800081e3  mov     r12, rdx
0x1800081e6  cmp     byte ptr [rsi+2], 1
0x1800081ea  jnz     short loc_18000820E
0x1800081ec  lea     rbx, [rcx+2]
0x1800081f0  cmp     rbx, r8
0x1800081f3  ja      short loc_180008273
0x1800081f5  movzx   eax, word ptr [rsi+4]
0x1800081f9  lea     r8, [rsp+58h+arg_0]
0x1800081fe  mov     r9d, 2
0x180008204  mov     [rsp+58h+arg_0], ax
0x180008209  mov     edx, r9d
0x18000820c  jmp     short loc_18000822C
0x18000820e  cmp     byte ptr [rsi+2], 2
0x180008212  mov     rbx, rcx
0x180008215  jnz     short loc_180008232
0x180008217  lea     rbx, [rcx+4]
0x18000821b  cmp     rbx, rdi
0x18000821e  ja      short loc_180008273
0x180008220  mov     edx, 4; DestinationSize
0x180008225  lea     r8, [rsi+4]; Source
0x180008229  mov     r9d, edx; SourceSize
0x18000822c  call    cs:__imp_memcpy_s
0x180008232  cmp     word ptr [rsi], 0
0x180008236  jnz     short loc_180008262
0x180008238  lea     r15, [rbx+2]
0x18000823c  cmp     r15, rdi
0x18000823f  ja      short loc_180008273
0x180008241  lea     r14, [rsi+8]
0x180008245  mov     rdx, rdi
0x180008248  sub     rdx, rbx; DestinationSize
0x18000824b  mov     r8, r14; Source
0x18000824e  mov     r9d, 2; SourceSize
0x180008254  mov     rcx, rbx; Destination
0x180008257  call    cs:__imp_memcpy_s
0x18000825d  mov     rbx, r15
0x180008260  jmp     short loc_180008266
0x180008262  lea     r14, [rsi+8]
0x180008266  movzx   r9d, word ptr [r14]; SourceSize
0x18000826a  lea     rax, [r9+rbx]
0x18000826e  cmp     rax, rdi
0x180008271  jbe     short loc_180008277
0x180008273  xor     al, al
0x180008275  jmp     short loc_180008297
0x180008277  mov     r8, [rsi+18h]; Source
0x18000827b  sub     rdi, rbx
0x18000827e  mov     rdx, rdi; DestinationSize
0x180008281  mov     rcx, rbx; Destination
0x180008284  call    cs:__imp_memcpy_s
0x18000828a  movzx   ecx, word ptr [r14]
0x18000828e  mov     al, 1
0x180008290  add     rcx, rbx
0x180008293  mov     [r12], rcx
0x180008297  add     rsp, 28h
0x18000829b  pop     r15
0x18000829d  pop     r14
0x18000829f  pop     r12
0x1800082a1  pop     rdi
0x1800082a2  pop     rsi
0x1800082a3  pop     rbx
0x1800082a4  retn
```
