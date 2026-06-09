# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x14000ff5c`
- end: `0x140010045`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140006e4c`
- `0x140010714`
- `0x140010a9c`

## callees

- `0x14000ff5c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x14000ffab`
- `msvcrt!memcpy_s` at `0x14000ffe0`
- `msvcrt!memcpy_s` at `0x14001000b`
- `msvcrt!memcpy_s` at `0x14000ffab`
- `msvcrt!memcpy_s` at `0x14000ffe0`
- `msvcrt!memcpy_s` at `0x14001000b`

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
0x14000ff5c  mov     rax, rsp
0x14000ff5f  mov     [rax+10h], rbx
0x14000ff63  mov     [rax+18h], rbp
0x14000ff67  push    rsi
0x14000ff68  push    rdi
0x14000ff69  push    r12
0x14000ff6b  push    r14
0x14000ff6d  push    r15
0x14000ff6f  sub     rsp, 20h
0x14000ff73  xor     r15d, r15d
0x14000ff76  mov     rsi, r8
0x14000ff79  cmp     byte ptr [rcx+2], 1
0x14000ff7d  mov     r12, rdx
0x14000ff80  mov     r8, [rdx]; Source
0x14000ff83  mov     rdi, rcx
0x14000ff86  jnz     short loc_14000FFBB
0x14000ff88  lea     rbx, [r8+2]
0x14000ff8c  cmp     rbx, rsi
0x14000ff8f  ja      loc_140010020
0x14000ff95  lea     ebp, [r15+2]
0x14000ff99  mov     [rcx+10h], r8
0x14000ff9d  mov     r9d, ebp; SourceSize
0x14000ffa0  mov     [rax+8], r15w
0x14000ffa5  mov     edx, ebp; DestinationSize
0x14000ffa7  lea     rcx, [rax+8]; Destination
0x14000ffab  call    cs:__imp_memcpy_s
0x14000ffb1  movzx   eax, [rsp+48h+arg_0]
0x14000ffb6  mov     [rdi+4], eax
0x14000ffb9  jmp     short loc_14000FFE6
0x14000ffbb  mov     ebp, 2
0x14000ffc0  mov     rbx, r8
0x14000ffc3  cmp     [rcx+2], bpl
0x14000ffc7  jnz     short loc_14000FFE6
0x14000ffc9  lea     rbx, [r8+4]
0x14000ffcd  cmp     rbx, rsi
0x14000ffd0  ja      short loc_140010020
0x14000ffd2  lea     edx, [rbp+2]; DestinationSize
0x14000ffd5  mov     [rcx+10h], r8
0x14000ffd9  mov     r9d, edx; SourceSize
0x14000ffdc  add     rcx, 4; Destination
0x14000ffe0  call    cs:__imp_memcpy_s
0x14000ffe6  movzx   eax, word ptr [rdi]
0x14000ffe9  lea     r14, [rdi+8]
0x14000ffed  mov     [r14], ax
0x14000fff1  test    ax, ax
0x14000fff4  jnz     short loc_140010014
0x14000fff6  lea     r15, [rbx+2]
0x14000fffa  cmp     r15, rsi
0x14000fffd  ja      short loc_140010020
0x14000ffff  mov     r9, rbp; SourceSize
0x140010002  mov     r8, rbx; Source
0x140010005  mov     rdx, rbp; DestinationSize
0x140010008  mov     rcx, r14; Destination
0x14001000b  call    cs:__imp_memcpy_s
0x140010011  mov     rbx, r15
0x140010014  movzx   ecx, word ptr [r14]
0x140010018  add     rcx, rbx
0x14001001b  cmp     rcx, rsi
0x14001001e  jbe     short loc_140010024
0x140010020  xor     al, al
0x140010022  jmp     short loc_14001002E
0x140010024  mov     [rdi+18h], rbx
0x140010028  mov     al, 1
0x14001002a  mov     [r12], rcx
0x14001002e  mov     rbx, [rsp+48h+arg_8]
0x140010033  mov     rbp, [rsp+48h+arg_10]
0x140010038  add     rsp, 20h
0x14001003c  pop     r15
0x14001003e  pop     r14
0x140010040  pop     r12
0x140010042  pop     rdi
0x140010043  pop     rsi
0x140010044  retn
```
