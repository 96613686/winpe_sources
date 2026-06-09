# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x140006edc`
- end: `0x140006fc5`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140005358`
- `0x1400061e4`
- `0x140006684`
- `0x1400074f4`
- `0x140007fc0`

## callees

- `0x140006edc`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140006f2b`
- `msvcrt!memcpy_s` at `0x140006f60`
- `msvcrt!memcpy_s` at `0x140006f8b`
- `msvcrt!memcpy_s` at `0x140006f2b`
- `msvcrt!memcpy_s` at `0x140006f60`
- `msvcrt!memcpy_s` at `0x140006f8b`

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
0x140006edc  mov     rax, rsp
0x140006edf  mov     [rax+10h], rbx
0x140006ee3  mov     [rax+18h], rbp
0x140006ee7  push    rsi
0x140006ee8  push    rdi
0x140006ee9  push    r12
0x140006eeb  push    r14
0x140006eed  push    r15
0x140006eef  sub     rsp, 20h
0x140006ef3  xor     r15d, r15d
0x140006ef6  mov     rsi, r8
0x140006ef9  cmp     byte ptr [rcx+2], 1
0x140006efd  mov     r12, rdx
0x140006f00  mov     r8, [rdx]; Source
0x140006f03  mov     rdi, rcx
0x140006f06  jnz     short loc_140006F3B
0x140006f08  lea     rbx, [r8+2]
0x140006f0c  cmp     rbx, rsi
0x140006f0f  ja      loc_140006FA0
0x140006f15  lea     ebp, [r15+2]
0x140006f19  mov     [rcx+10h], r8
0x140006f1d  mov     r9d, ebp; SourceSize
0x140006f20  mov     [rax+8], r15w
0x140006f25  mov     edx, ebp; DestinationSize
0x140006f27  lea     rcx, [rax+8]; Destination
0x140006f2b  call    cs:__imp_memcpy_s
0x140006f31  movzx   eax, [rsp+48h+arg_0]
0x140006f36  mov     [rdi+4], eax
0x140006f39  jmp     short loc_140006F66
0x140006f3b  mov     ebp, 2
0x140006f40  mov     rbx, r8
0x140006f43  cmp     [rcx+2], bpl
0x140006f47  jnz     short loc_140006F66
0x140006f49  lea     rbx, [r8+4]
0x140006f4d  cmp     rbx, rsi
0x140006f50  ja      short loc_140006FA0
0x140006f52  lea     edx, [rbp+2]; DestinationSize
0x140006f55  mov     [rcx+10h], r8
0x140006f59  mov     r9d, edx; SourceSize
0x140006f5c  add     rcx, 4; Destination
0x140006f60  call    cs:__imp_memcpy_s
0x140006f66  movzx   eax, word ptr [rdi]
0x140006f69  lea     r14, [rdi+8]
0x140006f6d  mov     [r14], ax
0x140006f71  test    ax, ax
0x140006f74  jnz     short loc_140006F94
0x140006f76  lea     r15, [rbx+2]
0x140006f7a  cmp     r15, rsi
0x140006f7d  ja      short loc_140006FA0
0x140006f7f  mov     r9, rbp; SourceSize
0x140006f82  mov     r8, rbx; Source
0x140006f85  mov     rdx, rbp; DestinationSize
0x140006f88  mov     rcx, r14; Destination
0x140006f8b  call    cs:__imp_memcpy_s
0x140006f91  mov     rbx, r15
0x140006f94  movzx   ecx, word ptr [r14]
0x140006f98  add     rcx, rbx
0x140006f9b  cmp     rcx, rsi
0x140006f9e  jbe     short loc_140006FA4
0x140006fa0  xor     al, al
0x140006fa2  jmp     short loc_140006FAE
0x140006fa4  mov     [rdi+18h], rbx
0x140006fa8  mov     al, 1
0x140006faa  mov     [r12], rcx
0x140006fae  mov     rbx, [rsp+48h+arg_8]
0x140006fb3  mov     rbp, [rsp+48h+arg_10]
0x140006fb8  add     rsp, 20h
0x140006fbc  pop     r15
0x140006fbe  pop     r14
0x140006fc0  pop     r12
0x140006fc2  pop     rdi
0x140006fc3  pop     rsi
0x140006fc4  retn
```
