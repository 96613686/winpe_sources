# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x18000a924`
- end: `0x18000aa0c`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *this, char **, char *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180007b94`

## callees

- `0x18000a924`
- `0x18000c610`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000a991`
- `msvcrt!memcpy_s` at `0x18000a9b9`
- `msvcrt!memcpy_s` at `0x18000a9e1`
- `msvcrt!memcpy_s` at `0x18000a991`
- `msvcrt!memcpy_s` at `0x18000a9b9`
- `msvcrt!memcpy_s` at `0x18000a9e1`

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
0x18000a924  push    rbx
0x18000a926  push    rsi
0x18000a927  push    rdi
0x18000a928  push    r14
0x18000a92a  push    r15
0x18000a92c  sub     rsp, 30h
0x18000a930  mov     rax, cs:__security_cookie
0x18000a937  xor     rax, rsp
0x18000a93a  mov     [rsp+58h+var_30], rax
0x18000a93f  mov     rsi, rcx
0x18000a942  mov     rdi, r8
0x18000a945  mov     rcx, [rdx]; Destination
0x18000a948  mov     r15, rdx
0x18000a94b  cmp     byte ptr [rsi+2], 1
0x18000a94f  jnz     short loc_18000A973
0x18000a951  lea     rbx, [rcx+2]
0x18000a955  cmp     rbx, r8
0x18000a958  ja      short loc_18000A9D0
0x18000a95a  movzx   eax, word ptr [rsi+4]
0x18000a95e  lea     r8, [rsp+58h+var_38]
0x18000a963  mov     r9d, 2
0x18000a969  mov     [rsp+58h+var_38], ax
0x18000a96e  mov     edx, r9d
0x18000a971  jmp     short loc_18000A991
0x18000a973  cmp     byte ptr [rsi+2], 2
0x18000a977  mov     rbx, rcx
0x18000a97a  jnz     short loc_18000A997
0x18000a97c  lea     rbx, [rcx+4]
0x18000a980  cmp     rbx, rdi
0x18000a983  ja      short loc_18000A9D0
0x18000a985  mov     edx, 4; DestinationSize
0x18000a98a  lea     r8, [rsi+4]; Source
0x18000a98e  mov     r9d, edx; SourceSize
0x18000a991  call    cs:__imp_memcpy_s
0x18000a997  cmp     word ptr [rsi], 0
0x18000a99b  jnz     short loc_18000A9C2
0x18000a99d  lea     r14, [rbx+2]
0x18000a9a1  cmp     r14, rdi
0x18000a9a4  ja      short loc_18000A9D0
0x18000a9a6  mov     rdx, rdi
0x18000a9a9  lea     r8, [rsi+8]; Source
0x18000a9ad  sub     rdx, rbx; DestinationSize
0x18000a9b0  mov     r9d, 2; SourceSize
0x18000a9b6  mov     rcx, rbx; Destination
0x18000a9b9  call    cs:__imp_memcpy_s
0x18000a9bf  mov     rbx, r14
0x18000a9c2  movzx   r9d, word ptr [rsi+8]; SourceSize
0x18000a9c7  lea     rax, [r9+rbx]
0x18000a9cb  cmp     rax, rdi
0x18000a9ce  jbe     short loc_18000A9D4
0x18000a9d0  xor     al, al
0x18000a9d2  jmp     short loc_18000A9F3
0x18000a9d4  mov     r8, [rsi+18h]; Source
0x18000a9d8  sub     rdi, rbx
0x18000a9db  mov     rdx, rdi; DestinationSize
0x18000a9de  mov     rcx, rbx; Destination
0x18000a9e1  call    cs:__imp_memcpy_s
0x18000a9e7  movzx   ecx, word ptr [rsi+8]
0x18000a9eb  mov     al, 1
0x18000a9ed  add     rcx, rbx
0x18000a9f0  mov     [r15], rcx
0x18000a9f3  mov     rcx, [rsp+58h+var_30]
0x18000a9f8  xor     rcx, rsp; StackCookie
0x18000a9fb  call    __security_check_cookie
0x18000aa00  add     rsp, 30h
0x18000aa04  pop     r15
0x18000aa06  pop     r14
0x18000aa08  pop     rdi
0x18000aa09  pop     rsi
0x18000aa0a  pop     rbx
0x18000aa0b  retn
```
