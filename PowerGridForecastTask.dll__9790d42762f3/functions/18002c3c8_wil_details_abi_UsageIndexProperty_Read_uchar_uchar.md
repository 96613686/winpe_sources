# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x18002c3c8`
- end: `0x18002c4b1`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18002a0ec`
- `0x18002cbf8`
- `0x18002cf80`

## callees

- `0x18002c3c8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18002c417`
- `msvcrt!memcpy_s` at `0x18002c44c`
- `msvcrt!memcpy_s` at `0x18002c477`
- `msvcrt!memcpy_s` at `0x18002c417`
- `msvcrt!memcpy_s` at `0x18002c44c`
- `msvcrt!memcpy_s` at `0x18002c477`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Read(
        wil::details_abi::UsageIndexProperty *this,
        unsigned __int8 **a2,
        unsigned __int8 *a3)
{
  char *v5; // r8
  char *v7; // rbx
  __int16 v8; // ax
  unsigned __int8 *v9; // rcx
  bool result; // al
  unsigned __int16 v11; // [rsp+50h] [rbp+8h] BYREF

  v5 = (char *)*a2;
  if ( *((_BYTE *)this + 2) == 1 )
  {
    v7 = v5 + 2;
    if ( v5 + 2 > (char *)a3 )
      return 0;
    *((_QWORD *)this + 2) = v5;
    v11 = 0;
    memcpy_s(&v11, 2u, v5, 2u);
    *((_DWORD *)this + 1) = v11;
  }
  else
  {
    v7 = (char *)*a2;
    if ( *((_BYTE *)this + 2) == 2 )
    {
      v7 = v5 + 4;
      if ( v5 + 4 > (char *)a3 )
        return 0;
      *((_QWORD *)this + 2) = v5;
      memcpy_s((char *)this + 4, 4u, v5, 4u);
    }
  }
  v8 = *(_WORD *)this;
  *((_WORD *)this + 4) = *(_WORD *)this;
  if ( v8 )
    goto LABEL_10;
  if ( v7 + 2 > (char *)a3 )
    return 0;
  memcpy_s((char *)this + 8, 2u, v7, 2u);
  v7 += 2;
LABEL_10:
  v9 = (unsigned __int8 *)&v7[*((unsigned __int16 *)this + 4)];
  if ( v9 > a3 )
    return 0;
  *((_QWORD *)this + 3) = v7;
  result = 1;
  *a2 = v9;
  return result;
}

```

## disassembly

```asm
0x18002c3c8  mov     rax, rsp
0x18002c3cb  mov     [rax+10h], rbx
0x18002c3cf  mov     [rax+18h], rbp
0x18002c3d3  push    rsi
0x18002c3d4  push    rdi
0x18002c3d5  push    r12
0x18002c3d7  push    r14
0x18002c3d9  push    r15
0x18002c3db  sub     rsp, 20h
0x18002c3df  xor     r15d, r15d
0x18002c3e2  mov     rsi, r8
0x18002c3e5  cmp     byte ptr [rcx+2], 1
0x18002c3e9  mov     r12, rdx
0x18002c3ec  mov     r8, [rdx]; Source
0x18002c3ef  mov     rdi, rcx
0x18002c3f2  jnz     short loc_18002C427
0x18002c3f4  lea     rbx, [r8+2]
0x18002c3f8  cmp     rbx, rsi
0x18002c3fb  ja      loc_18002C48C
0x18002c401  lea     ebp, [r15+2]
0x18002c405  mov     [rcx+10h], r8
0x18002c409  mov     r9d, ebp; SourceSize
0x18002c40c  mov     [rax+8], r15w
0x18002c411  mov     edx, ebp; DestinationSize
0x18002c413  lea     rcx, [rax+8]; Destination
0x18002c417  call    cs:__imp_memcpy_s
0x18002c41d  movzx   eax, [rsp+48h+arg_0]
0x18002c422  mov     [rdi+4], eax
0x18002c425  jmp     short loc_18002C452
0x18002c427  mov     ebp, 2
0x18002c42c  mov     rbx, r8
0x18002c42f  cmp     [rcx+2], bpl
0x18002c433  jnz     short loc_18002C452
0x18002c435  lea     rbx, [r8+4]
0x18002c439  cmp     rbx, rsi
0x18002c43c  ja      short loc_18002C48C
0x18002c43e  lea     edx, [rbp+2]; DestinationSize
0x18002c441  mov     [rcx+10h], r8
0x18002c445  mov     r9d, edx; SourceSize
0x18002c448  add     rcx, 4; Destination
0x18002c44c  call    cs:__imp_memcpy_s
0x18002c452  movzx   eax, word ptr [rdi]
0x18002c455  lea     r14, [rdi+8]
0x18002c459  mov     [r14], ax
0x18002c45d  test    ax, ax
0x18002c460  jnz     short loc_18002C480
0x18002c462  lea     r15, [rbx+2]
0x18002c466  cmp     r15, rsi
0x18002c469  ja      short loc_18002C48C
0x18002c46b  mov     r9, rbp; SourceSize
0x18002c46e  mov     r8, rbx; Source
0x18002c471  mov     rdx, rbp; DestinationSize
0x18002c474  mov     rcx, r14; Destination
0x18002c477  call    cs:__imp_memcpy_s
0x18002c47d  mov     rbx, r15
0x18002c480  movzx   ecx, word ptr [r14]
0x18002c484  add     rcx, rbx
0x18002c487  cmp     rcx, rsi
0x18002c48a  jbe     short loc_18002C490
0x18002c48c  xor     al, al
0x18002c48e  jmp     short loc_18002C49A
0x18002c490  mov     [rdi+18h], rbx
0x18002c494  mov     al, 1
0x18002c496  mov     [r12], rcx
0x18002c49a  mov     rbx, [rsp+48h+arg_8]
0x18002c49f  mov     rbp, [rsp+48h+arg_10]
0x18002c4a4  add     rsp, 20h
0x18002c4a8  pop     r15
0x18002c4aa  pop     r14
0x18002c4ac  pop     r12
0x18002c4ae  pop     rdi
0x18002c4af  pop     rsi
0x18002c4b0  retn
```
