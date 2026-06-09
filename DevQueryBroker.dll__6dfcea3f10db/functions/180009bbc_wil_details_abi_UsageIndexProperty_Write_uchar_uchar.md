# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x180009bbc`
- end: `0x180009c95`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *this, char **, char *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800082c0`

## callees

- `0x180009bbc`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180009c1c`
- `msvcrt!memcpy_s` at `0x180009c47`
- `msvcrt!memcpy_s` at `0x180009c74`
- `msvcrt!memcpy_s` at `0x180009c1c`
- `msvcrt!memcpy_s` at `0x180009c47`
- `msvcrt!memcpy_s` at `0x180009c74`

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
0x180009bbc  push    rbx
0x180009bbe  push    rsi
0x180009bbf  push    rdi
0x180009bc0  push    r12
0x180009bc2  push    r14
0x180009bc4  push    r15
0x180009bc6  sub     rsp, 28h
0x180009bca  mov     rsi, rcx
0x180009bcd  mov     rdi, r8
0x180009bd0  mov     rcx, [rdx]; Destination
0x180009bd3  mov     r12, rdx
0x180009bd6  cmp     byte ptr [rsi+2], 1
0x180009bda  jnz     short loc_180009BFE
0x180009bdc  lea     rbx, [rcx+2]
0x180009be0  cmp     rbx, r8
0x180009be3  ja      short loc_180009C63
0x180009be5  movzx   eax, word ptr [rsi+4]
0x180009be9  lea     r8, [rsp+58h+arg_0]
0x180009bee  mov     r9d, 2
0x180009bf4  mov     [rsp+58h+arg_0], ax
0x180009bf9  mov     edx, r9d
0x180009bfc  jmp     short loc_180009C1C
0x180009bfe  cmp     byte ptr [rsi+2], 2
0x180009c02  mov     rbx, rcx
0x180009c05  jnz     short loc_180009C22
0x180009c07  lea     rbx, [rcx+4]
0x180009c0b  cmp     rbx, rdi
0x180009c0e  ja      short loc_180009C63
0x180009c10  mov     edx, 4; DestinationSize
0x180009c15  lea     r8, [rsi+4]; Source
0x180009c19  mov     r9d, edx; SourceSize
0x180009c1c  call    cs:__imp_memcpy_s
0x180009c22  cmp     word ptr [rsi], 0
0x180009c26  jnz     short loc_180009C52
0x180009c28  lea     r15, [rbx+2]
0x180009c2c  cmp     r15, rdi
0x180009c2f  ja      short loc_180009C63
0x180009c31  lea     r14, [rsi+8]
0x180009c35  mov     rdx, rdi
0x180009c38  sub     rdx, rbx; DestinationSize
0x180009c3b  mov     r8, r14; Source
0x180009c3e  mov     r9d, 2; SourceSize
0x180009c44  mov     rcx, rbx; Destination
0x180009c47  call    cs:__imp_memcpy_s
0x180009c4d  mov     rbx, r15
0x180009c50  jmp     short loc_180009C56
0x180009c52  lea     r14, [rsi+8]
0x180009c56  movzx   r9d, word ptr [r14]; SourceSize
0x180009c5a  lea     rax, [r9+rbx]
0x180009c5e  cmp     rax, rdi
0x180009c61  jbe     short loc_180009C67
0x180009c63  xor     al, al
0x180009c65  jmp     short loc_180009C87
0x180009c67  mov     r8, [rsi+18h]; Source
0x180009c6b  sub     rdi, rbx
0x180009c6e  mov     rdx, rdi; DestinationSize
0x180009c71  mov     rcx, rbx; Destination
0x180009c74  call    cs:__imp_memcpy_s
0x180009c7a  movzx   ecx, word ptr [r14]
0x180009c7e  mov     al, 1
0x180009c80  add     rcx, rbx
0x180009c83  mov     [r12], rcx
0x180009c87  add     rsp, 28h
0x180009c8b  pop     r15
0x180009c8d  pop     r14
0x180009c8f  pop     r12
0x180009c91  pop     rdi
0x180009c92  pop     rsi
0x180009c93  pop     rbx
0x180009c94  retn
```
