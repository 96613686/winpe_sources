# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x14000b868`
- end: `0x14000b941`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140008f40`

## callees

- `0x14000b868`

## import_xrefs

- `msvcrt!memcpy_s` at `0x14000b8c8`
- `msvcrt!memcpy_s` at `0x14000b8f3`
- `msvcrt!memcpy_s` at `0x14000b920`
- `msvcrt!memcpy_s` at `0x14000b8c8`
- `msvcrt!memcpy_s` at `0x14000b8f3`
- `msvcrt!memcpy_s` at `0x14000b920`

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
0x14000b868  push    rbx
0x14000b86a  push    rsi
0x14000b86b  push    rdi
0x14000b86c  push    r12
0x14000b86e  push    r14
0x14000b870  push    r15
0x14000b872  sub     rsp, 28h
0x14000b876  mov     rsi, rcx
0x14000b879  mov     rdi, r8
0x14000b87c  mov     rcx, [rdx]; Destination
0x14000b87f  mov     r12, rdx
0x14000b882  cmp     byte ptr [rsi+2], 1
0x14000b886  jnz     short loc_14000B8AA
0x14000b888  lea     rbx, [rcx+2]
0x14000b88c  cmp     rbx, r8
0x14000b88f  ja      short loc_14000B90F
0x14000b891  movzx   eax, word ptr [rsi+4]
0x14000b895  lea     r8, [rsp+58h+arg_0]
0x14000b89a  mov     r9d, 2
0x14000b8a0  mov     [rsp+58h+arg_0], ax
0x14000b8a5  mov     edx, r9d
0x14000b8a8  jmp     short loc_14000B8C8
0x14000b8aa  cmp     byte ptr [rsi+2], 2
0x14000b8ae  mov     rbx, rcx
0x14000b8b1  jnz     short loc_14000B8CE
0x14000b8b3  lea     rbx, [rcx+4]
0x14000b8b7  cmp     rbx, rdi
0x14000b8ba  ja      short loc_14000B90F
0x14000b8bc  mov     edx, 4; DestinationSize
0x14000b8c1  lea     r8, [rsi+4]; Source
0x14000b8c5  mov     r9d, edx; SourceSize
0x14000b8c8  call    cs:__imp_memcpy_s
0x14000b8ce  cmp     word ptr [rsi], 0
0x14000b8d2  jnz     short loc_14000B8FE
0x14000b8d4  lea     r15, [rbx+2]
0x14000b8d8  cmp     r15, rdi
0x14000b8db  ja      short loc_14000B90F
0x14000b8dd  lea     r14, [rsi+8]
0x14000b8e1  mov     rdx, rdi
0x14000b8e4  sub     rdx, rbx; DestinationSize
0x14000b8e7  mov     r8, r14; Source
0x14000b8ea  mov     r9d, 2; SourceSize
0x14000b8f0  mov     rcx, rbx; Destination
0x14000b8f3  call    cs:__imp_memcpy_s
0x14000b8f9  mov     rbx, r15
0x14000b8fc  jmp     short loc_14000B902
0x14000b8fe  lea     r14, [rsi+8]
0x14000b902  movzx   r9d, word ptr [r14]; SourceSize
0x14000b906  lea     rax, [r9+rbx]
0x14000b90a  cmp     rax, rdi
0x14000b90d  jbe     short loc_14000B913
0x14000b90f  xor     al, al
0x14000b911  jmp     short loc_14000B933
0x14000b913  mov     r8, [rsi+18h]; Source
0x14000b917  sub     rdi, rbx
0x14000b91a  mov     rdx, rdi; DestinationSize
0x14000b91d  mov     rcx, rbx; Destination
0x14000b920  call    cs:__imp_memcpy_s
0x14000b926  movzx   ecx, word ptr [r14]
0x14000b92a  mov     al, 1
0x14000b92c  add     rcx, rbx
0x14000b92f  mov     [r12], rcx
0x14000b933  add     rsp, 28h
0x14000b937  pop     r15
0x14000b939  pop     r14
0x14000b93b  pop     r12
0x14000b93d  pop     rdi
0x14000b93e  pop     rsi
0x14000b93f  pop     rbx
0x14000b940  retn
```
