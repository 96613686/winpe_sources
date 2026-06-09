# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x140011c3c`
- end: `0x140011d15`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *this, char **, char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140010714`

## callees

- `0x140011c3c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140011c9c`
- `msvcrt!memcpy_s` at `0x140011cc7`
- `msvcrt!memcpy_s` at `0x140011cf4`
- `msvcrt!memcpy_s` at `0x140011c9c`
- `msvcrt!memcpy_s` at `0x140011cc7`
- `msvcrt!memcpy_s` at `0x140011cf4`

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
0x140011c3c  push    rbx
0x140011c3e  push    rsi
0x140011c3f  push    rdi
0x140011c40  push    r12
0x140011c42  push    r14
0x140011c44  push    r15
0x140011c46  sub     rsp, 28h
0x140011c4a  mov     rsi, rcx
0x140011c4d  mov     rdi, r8
0x140011c50  mov     rcx, [rdx]; Destination
0x140011c53  mov     r12, rdx
0x140011c56  cmp     byte ptr [rsi+2], 1
0x140011c5a  jnz     short loc_140011C7E
0x140011c5c  lea     rbx, [rcx+2]
0x140011c60  cmp     rbx, r8
0x140011c63  ja      short loc_140011CE3
0x140011c65  movzx   eax, word ptr [rsi+4]
0x140011c69  lea     r8, [rsp+58h+arg_0]
0x140011c6e  mov     r9d, 2
0x140011c74  mov     [rsp+58h+arg_0], ax
0x140011c79  mov     edx, r9d
0x140011c7c  jmp     short loc_140011C9C
0x140011c7e  cmp     byte ptr [rsi+2], 2
0x140011c82  mov     rbx, rcx
0x140011c85  jnz     short loc_140011CA2
0x140011c87  lea     rbx, [rcx+4]
0x140011c8b  cmp     rbx, rdi
0x140011c8e  ja      short loc_140011CE3
0x140011c90  mov     edx, 4; DestinationSize
0x140011c95  lea     r8, [rsi+4]; Source
0x140011c99  mov     r9d, edx; SourceSize
0x140011c9c  call    cs:__imp_memcpy_s
0x140011ca2  cmp     word ptr [rsi], 0
0x140011ca6  jnz     short loc_140011CD2
0x140011ca8  lea     r15, [rbx+2]
0x140011cac  cmp     r15, rdi
0x140011caf  ja      short loc_140011CE3
0x140011cb1  lea     r14, [rsi+8]
0x140011cb5  mov     rdx, rdi
0x140011cb8  sub     rdx, rbx; DestinationSize
0x140011cbb  mov     r8, r14; Source
0x140011cbe  mov     r9d, 2; SourceSize
0x140011cc4  mov     rcx, rbx; Destination
0x140011cc7  call    cs:__imp_memcpy_s
0x140011ccd  mov     rbx, r15
0x140011cd0  jmp     short loc_140011CD6
0x140011cd2  lea     r14, [rsi+8]
0x140011cd6  movzx   r9d, word ptr [r14]; SourceSize
0x140011cda  lea     rax, [r9+rbx]
0x140011cde  cmp     rax, rdi
0x140011ce1  jbe     short loc_140011CE7
0x140011ce3  xor     al, al
0x140011ce5  jmp     short loc_140011D07
0x140011ce7  mov     r8, [rsi+18h]; Source
0x140011ceb  sub     rdi, rbx
0x140011cee  mov     rdx, rdi; DestinationSize
0x140011cf1  mov     rcx, rbx; Destination
0x140011cf4  call    cs:__imp_memcpy_s
0x140011cfa  movzx   ecx, word ptr [r14]
0x140011cfe  mov     al, 1
0x140011d00  add     rcx, rbx
0x140011d03  mov     [r12], rcx
0x140011d07  add     rsp, 28h
0x140011d0b  pop     r15
0x140011d0d  pop     r14
0x140011d0f  pop     r12
0x140011d11  pop     rdi
0x140011d12  pop     rsi
0x140011d13  pop     rbx
0x140011d14  retn
```
