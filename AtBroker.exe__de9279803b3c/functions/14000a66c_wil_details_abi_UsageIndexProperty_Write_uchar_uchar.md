# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x14000a66c`
- end: `0x14000a745`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *this, char **, char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140008344`

## callees

- `0x14000a66c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x14000a6cc`
- `msvcrt!memcpy_s` at `0x14000a6f7`
- `msvcrt!memcpy_s` at `0x14000a724`
- `msvcrt!memcpy_s` at `0x14000a6cc`
- `msvcrt!memcpy_s` at `0x14000a6f7`
- `msvcrt!memcpy_s` at `0x14000a724`

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
0x14000a66c  push    rbx
0x14000a66e  push    rsi
0x14000a66f  push    rdi
0x14000a670  push    r12
0x14000a672  push    r14
0x14000a674  push    r15
0x14000a676  sub     rsp, 28h
0x14000a67a  mov     rsi, rcx
0x14000a67d  mov     rdi, r8
0x14000a680  mov     rcx, [rdx]; Destination
0x14000a683  mov     r12, rdx
0x14000a686  cmp     byte ptr [rsi+2], 1
0x14000a68a  jnz     short loc_14000A6AE
0x14000a68c  lea     rbx, [rcx+2]
0x14000a690  cmp     rbx, r8
0x14000a693  ja      short loc_14000A713
0x14000a695  movzx   eax, word ptr [rsi+4]
0x14000a699  lea     r8, [rsp+58h+arg_0]
0x14000a69e  mov     r9d, 2
0x14000a6a4  mov     [rsp+58h+arg_0], ax
0x14000a6a9  mov     edx, r9d
0x14000a6ac  jmp     short loc_14000A6CC
0x14000a6ae  cmp     byte ptr [rsi+2], 2
0x14000a6b2  mov     rbx, rcx
0x14000a6b5  jnz     short loc_14000A6D2
0x14000a6b7  lea     rbx, [rcx+4]
0x14000a6bb  cmp     rbx, rdi
0x14000a6be  ja      short loc_14000A713
0x14000a6c0  mov     edx, 4; DestinationSize
0x14000a6c5  lea     r8, [rsi+4]; Source
0x14000a6c9  mov     r9d, edx; SourceSize
0x14000a6cc  call    cs:__imp_memcpy_s
0x14000a6d2  cmp     word ptr [rsi], 0
0x14000a6d6  jnz     short loc_14000A702
0x14000a6d8  lea     r15, [rbx+2]
0x14000a6dc  cmp     r15, rdi
0x14000a6df  ja      short loc_14000A713
0x14000a6e1  lea     r14, [rsi+8]
0x14000a6e5  mov     rdx, rdi
0x14000a6e8  sub     rdx, rbx; DestinationSize
0x14000a6eb  mov     r8, r14; Source
0x14000a6ee  mov     r9d, 2; SourceSize
0x14000a6f4  mov     rcx, rbx; Destination
0x14000a6f7  call    cs:__imp_memcpy_s
0x14000a6fd  mov     rbx, r15
0x14000a700  jmp     short loc_14000A706
0x14000a702  lea     r14, [rsi+8]
0x14000a706  movzx   r9d, word ptr [r14]; SourceSize
0x14000a70a  lea     rax, [r9+rbx]
0x14000a70e  cmp     rax, rdi
0x14000a711  jbe     short loc_14000A717
0x14000a713  xor     al, al
0x14000a715  jmp     short loc_14000A737
0x14000a717  mov     r8, [rsi+18h]; Source
0x14000a71b  sub     rdi, rbx
0x14000a71e  mov     rdx, rdi; DestinationSize
0x14000a721  mov     rcx, rbx; Destination
0x14000a724  call    cs:__imp_memcpy_s
0x14000a72a  movzx   ecx, word ptr [r14]
0x14000a72e  mov     al, 1
0x14000a730  add     rcx, rbx
0x14000a733  mov     [r12], rcx
0x14000a737  add     rsp, 28h
0x14000a73b  pop     r15
0x14000a73d  pop     r14
0x14000a73f  pop     r12
0x14000a741  pop     rdi
0x14000a742  pop     rsi
0x14000a743  pop     rbx
0x14000a744  retn
```
