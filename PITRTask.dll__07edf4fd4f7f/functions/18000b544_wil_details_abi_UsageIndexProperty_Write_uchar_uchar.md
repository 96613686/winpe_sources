# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x18000b544`
- end: `0x18000b62c`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *this, char **, char *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180007c84`

## callees

- `0x18000b544`
- `0x1800107c0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000b5b1`
- `msvcrt!memcpy_s` at `0x18000b5d9`
- `msvcrt!memcpy_s` at `0x18000b601`
- `msvcrt!memcpy_s` at `0x18000b5b1`
- `msvcrt!memcpy_s` at `0x18000b5d9`
- `msvcrt!memcpy_s` at `0x18000b601`

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
  rsize_t v11; // r9
  bool result; // al
  __int16 v13; // [rsp+20h] [rbp-38h] BYREF

  v5 = *a2;
  if ( *((_BYTE *)this + 2) == 1 )
  {
    v7 = v5 + 2;
    if ( v5 + 2 > a3 )
      return 0;
    v8 = (char *)&v13;
    v9 = 2;
    v13 = *((_WORD *)this + 2);
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
  if ( *(_WORD *)this )
    goto LABEL_11;
  if ( v7 + 2 > a3 )
    return 0;
  memcpy_s(v7, a3 - v7, (char *)this + 8, 2u);
  v7 += 2;
LABEL_11:
  v11 = *((unsigned __int16 *)this + 4);
  if ( &v7[v11] > a3 )
    return 0;
  memcpy_s(v7, a3 - v7, *((const void *const *)this + 3), v11);
  result = 1;
  *a2 = &v7[*((unsigned __int16 *)this + 4)];
  return result;
}

```

## disassembly

```asm
0x18000b544  push    rbx
0x18000b546  push    rsi
0x18000b547  push    rdi
0x18000b548  push    r14
0x18000b54a  push    r15
0x18000b54c  sub     rsp, 30h
0x18000b550  mov     rax, cs:__security_cookie
0x18000b557  xor     rax, rsp
0x18000b55a  mov     [rsp+58h+var_30], rax
0x18000b55f  mov     rsi, rcx
0x18000b562  mov     rdi, r8
0x18000b565  mov     rcx, [rdx]; Destination
0x18000b568  mov     r15, rdx
0x18000b56b  cmp     byte ptr [rsi+2], 1
0x18000b56f  jnz     short loc_18000B593
0x18000b571  lea     rbx, [rcx+2]
0x18000b575  cmp     rbx, r8
0x18000b578  ja      short loc_18000B5F0
0x18000b57a  movzx   eax, word ptr [rsi+4]
0x18000b57e  lea     r8, [rsp+58h+var_38]
0x18000b583  mov     r9d, 2
0x18000b589  mov     [rsp+58h+var_38], ax
0x18000b58e  mov     edx, r9d
0x18000b591  jmp     short loc_18000B5B1
0x18000b593  cmp     byte ptr [rsi+2], 2
0x18000b597  mov     rbx, rcx
0x18000b59a  jnz     short loc_18000B5B7
0x18000b59c  lea     rbx, [rcx+4]
0x18000b5a0  cmp     rbx, rdi
0x18000b5a3  ja      short loc_18000B5F0
0x18000b5a5  mov     edx, 4; DestinationSize
0x18000b5aa  lea     r8, [rsi+4]; Source
0x18000b5ae  mov     r9d, edx; SourceSize
0x18000b5b1  call    cs:__imp_memcpy_s
0x18000b5b7  cmp     word ptr [rsi], 0
0x18000b5bb  jnz     short loc_18000B5E2
0x18000b5bd  lea     r14, [rbx+2]
0x18000b5c1  cmp     r14, rdi
0x18000b5c4  ja      short loc_18000B5F0
0x18000b5c6  mov     rdx, rdi
0x18000b5c9  lea     r8, [rsi+8]; Source
0x18000b5cd  sub     rdx, rbx; DestinationSize
0x18000b5d0  mov     r9d, 2; SourceSize
0x18000b5d6  mov     rcx, rbx; Destination
0x18000b5d9  call    cs:__imp_memcpy_s
0x18000b5df  mov     rbx, r14
0x18000b5e2  movzx   r9d, word ptr [rsi+8]; SourceSize
0x18000b5e7  lea     rax, [r9+rbx]
0x18000b5eb  cmp     rax, rdi
0x18000b5ee  jbe     short loc_18000B5F4
0x18000b5f0  xor     al, al
0x18000b5f2  jmp     short loc_18000B613
0x18000b5f4  mov     r8, [rsi+18h]; Source
0x18000b5f8  sub     rdi, rbx
0x18000b5fb  mov     rdx, rdi; DestinationSize
0x18000b5fe  mov     rcx, rbx; Destination
0x18000b601  call    cs:__imp_memcpy_s
0x18000b607  movzx   ecx, word ptr [rsi+8]
0x18000b60b  mov     al, 1
0x18000b60d  add     rcx, rbx
0x18000b610  mov     [r15], rcx
0x18000b613  mov     rcx, [rsp+58h+var_30]
0x18000b618  xor     rcx, rsp; StackCookie
0x18000b61b  call    __security_check_cookie
0x18000b620  add     rsp, 30h
0x18000b624  pop     r15
0x18000b626  pop     r14
0x18000b628  pop     rdi
0x18000b629  pop     rsi
0x18000b62a  pop     rbx
0x18000b62b  retn
```
