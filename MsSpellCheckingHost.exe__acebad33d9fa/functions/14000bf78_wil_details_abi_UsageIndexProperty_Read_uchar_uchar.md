# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x14000bf78`
- end: `0x14000c061`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140009f90`
- `0x14000c7a8`
- `0x14000cb30`

## callees

- `0x14000bf78`

## import_xrefs

- `msvcrt!memcpy_s` at `0x14000bfc7`
- `msvcrt!memcpy_s` at `0x14000bffc`
- `msvcrt!memcpy_s` at `0x14000c027`
- `msvcrt!memcpy_s` at `0x14000bfc7`
- `msvcrt!memcpy_s` at `0x14000bffc`
- `msvcrt!memcpy_s` at `0x14000c027`

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
0x14000bf78  mov     rax, rsp
0x14000bf7b  mov     [rax+10h], rbx
0x14000bf7f  mov     [rax+18h], rbp
0x14000bf83  push    rsi
0x14000bf84  push    rdi
0x14000bf85  push    r12
0x14000bf87  push    r14
0x14000bf89  push    r15
0x14000bf8b  sub     rsp, 20h
0x14000bf8f  xor     r15d, r15d
0x14000bf92  mov     rsi, r8
0x14000bf95  cmp     byte ptr [rcx+2], 1
0x14000bf99  mov     r12, rdx
0x14000bf9c  mov     r8, [rdx]; Source
0x14000bf9f  mov     rdi, rcx
0x14000bfa2  jnz     short loc_14000BFD7
0x14000bfa4  lea     rbx, [r8+2]
0x14000bfa8  cmp     rbx, rsi
0x14000bfab  ja      loc_14000C03C
0x14000bfb1  lea     ebp, [r15+2]
0x14000bfb5  mov     [rcx+10h], r8
0x14000bfb9  mov     r9d, ebp; SourceSize
0x14000bfbc  mov     [rax+8], r15w
0x14000bfc1  mov     edx, ebp; DestinationSize
0x14000bfc3  lea     rcx, [rax+8]; Destination
0x14000bfc7  call    cs:__imp_memcpy_s
0x14000bfcd  movzx   eax, [rsp+48h+arg_0]
0x14000bfd2  mov     [rdi+4], eax
0x14000bfd5  jmp     short loc_14000C002
0x14000bfd7  mov     ebp, 2
0x14000bfdc  mov     rbx, r8
0x14000bfdf  cmp     [rcx+2], bpl
0x14000bfe3  jnz     short loc_14000C002
0x14000bfe5  lea     rbx, [r8+4]
0x14000bfe9  cmp     rbx, rsi
0x14000bfec  ja      short loc_14000C03C
0x14000bfee  lea     edx, [rbp+2]; DestinationSize
0x14000bff1  mov     [rcx+10h], r8
0x14000bff5  mov     r9d, edx; SourceSize
0x14000bff8  add     rcx, 4; Destination
0x14000bffc  call    cs:__imp_memcpy_s
0x14000c002  movzx   eax, word ptr [rdi]
0x14000c005  lea     r14, [rdi+8]
0x14000c009  mov     [r14], ax
0x14000c00d  test    ax, ax
0x14000c010  jnz     short loc_14000C030
0x14000c012  lea     r15, [rbx+2]
0x14000c016  cmp     r15, rsi
0x14000c019  ja      short loc_14000C03C
0x14000c01b  mov     r9, rbp; SourceSize
0x14000c01e  mov     r8, rbx; Source
0x14000c021  mov     rdx, rbp; DestinationSize
0x14000c024  mov     rcx, r14; Destination
0x14000c027  call    cs:__imp_memcpy_s
0x14000c02d  mov     rbx, r15
0x14000c030  movzx   ecx, word ptr [r14]
0x14000c034  add     rcx, rbx
0x14000c037  cmp     rcx, rsi
0x14000c03a  jbe     short loc_14000C040
0x14000c03c  xor     al, al
0x14000c03e  jmp     short loc_14000C04A
0x14000c040  mov     [rdi+18h], rbx
0x14000c044  mov     al, 1
0x14000c046  mov     [r12], rcx
0x14000c04a  mov     rbx, [rsp+48h+arg_8]
0x14000c04f  mov     rbp, [rsp+48h+arg_10]
0x14000c054  add     rsp, 20h
0x14000c058  pop     r15
0x14000c05a  pop     r14
0x14000c05c  pop     r12
0x14000c05e  pop     rdi
0x14000c05f  pop     rsi
0x14000c060  retn
```
