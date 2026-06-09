# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x1400089d4`
- end: `0x140008abd`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140005fd8`
- `0x140007570`
- `0x140007cc8`
- `0x140008f40`
- `0x14000a878`

## callees

- `0x1400089d4`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140008a23`
- `msvcrt!memcpy_s` at `0x140008a58`
- `msvcrt!memcpy_s` at `0x140008a83`
- `msvcrt!memcpy_s` at `0x140008a23`
- `msvcrt!memcpy_s` at `0x140008a58`
- `msvcrt!memcpy_s` at `0x140008a83`

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
0x1400089d4  mov     rax, rsp
0x1400089d7  mov     [rax+10h], rbx
0x1400089db  mov     [rax+18h], rbp
0x1400089df  push    rsi
0x1400089e0  push    rdi
0x1400089e1  push    r12
0x1400089e3  push    r14
0x1400089e5  push    r15
0x1400089e7  sub     rsp, 20h
0x1400089eb  xor     r15d, r15d
0x1400089ee  mov     rsi, r8
0x1400089f1  cmp     byte ptr [rcx+2], 1
0x1400089f5  mov     r12, rdx
0x1400089f8  mov     r8, [rdx]; Source
0x1400089fb  mov     rdi, rcx
0x1400089fe  jnz     short loc_140008A33
0x140008a00  lea     rbx, [r8+2]
0x140008a04  cmp     rbx, rsi
0x140008a07  ja      loc_140008A98
0x140008a0d  lea     ebp, [r15+2]
0x140008a11  mov     [rcx+10h], r8
0x140008a15  mov     r9d, ebp; SourceSize
0x140008a18  mov     [rax+8], r15w
0x140008a1d  mov     edx, ebp; DestinationSize
0x140008a1f  lea     rcx, [rax+8]; Destination
0x140008a23  call    cs:__imp_memcpy_s
0x140008a29  movzx   eax, [rsp+48h+arg_0]
0x140008a2e  mov     [rdi+4], eax
0x140008a31  jmp     short loc_140008A5E
0x140008a33  mov     ebp, 2
0x140008a38  mov     rbx, r8
0x140008a3b  cmp     [rcx+2], bpl
0x140008a3f  jnz     short loc_140008A5E
0x140008a41  lea     rbx, [r8+4]
0x140008a45  cmp     rbx, rsi
0x140008a48  ja      short loc_140008A98
0x140008a4a  lea     edx, [rbp+2]; DestinationSize
0x140008a4d  mov     [rcx+10h], r8
0x140008a51  mov     r9d, edx; SourceSize
0x140008a54  add     rcx, 4; Destination
0x140008a58  call    cs:__imp_memcpy_s
0x140008a5e  movzx   eax, word ptr [rdi]
0x140008a61  lea     r14, [rdi+8]
0x140008a65  mov     [r14], ax
0x140008a69  test    ax, ax
0x140008a6c  jnz     short loc_140008A8C
0x140008a6e  lea     r15, [rbx+2]
0x140008a72  cmp     r15, rsi
0x140008a75  ja      short loc_140008A98
0x140008a77  mov     r9, rbp; SourceSize
0x140008a7a  mov     r8, rbx; Source
0x140008a7d  mov     rdx, rbp; DestinationSize
0x140008a80  mov     rcx, r14; Destination
0x140008a83  call    cs:__imp_memcpy_s
0x140008a89  mov     rbx, r15
0x140008a8c  movzx   ecx, word ptr [r14]
0x140008a90  add     rcx, rbx
0x140008a93  cmp     rcx, rsi
0x140008a96  jbe     short loc_140008A9C
0x140008a98  xor     al, al
0x140008a9a  jmp     short loc_140008AA6
0x140008a9c  mov     [rdi+18h], rbx
0x140008aa0  mov     al, 1
0x140008aa2  mov     [r12], rcx
0x140008aa6  mov     rbx, [rsp+48h+arg_8]
0x140008aab  mov     rbp, [rsp+48h+arg_10]
0x140008ab0  add     rsp, 20h
0x140008ab4  pop     r15
0x140008ab6  pop     r14
0x140008ab8  pop     r12
0x140008aba  pop     rdi
0x140008abb  pop     rsi
0x140008abc  retn
```
