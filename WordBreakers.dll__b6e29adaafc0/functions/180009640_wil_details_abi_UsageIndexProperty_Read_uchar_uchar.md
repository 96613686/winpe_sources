# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180009640`
- end: `0x180009729`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000882c`
- `0x180009c08`
- `0x180009f90`

## callees

- `0x180009640`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000968f`
- `msvcrt!memcpy_s` at `0x1800096c4`
- `msvcrt!memcpy_s` at `0x1800096ef`
- `msvcrt!memcpy_s` at `0x18000968f`
- `msvcrt!memcpy_s` at `0x1800096c4`
- `msvcrt!memcpy_s` at `0x1800096ef`

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
0x180009640  mov     rax, rsp
0x180009643  mov     [rax+10h], rbx
0x180009647  mov     [rax+18h], rbp
0x18000964b  push    rsi
0x18000964c  push    rdi
0x18000964d  push    r12
0x18000964f  push    r14
0x180009651  push    r15
0x180009653  sub     rsp, 20h
0x180009657  xor     r15d, r15d
0x18000965a  mov     rsi, r8
0x18000965d  cmp     byte ptr [rcx+2], 1
0x180009661  mov     r12, rdx
0x180009664  mov     r8, [rdx]; Source
0x180009667  mov     rdi, rcx
0x18000966a  jnz     short loc_18000969F
0x18000966c  lea     rbx, [r8+2]
0x180009670  cmp     rbx, rsi
0x180009673  ja      loc_180009704
0x180009679  lea     ebp, [r15+2]
0x18000967d  mov     [rcx+10h], r8
0x180009681  mov     r9d, ebp; SourceSize
0x180009684  mov     [rax+8], r15w
0x180009689  mov     edx, ebp; DestinationSize
0x18000968b  lea     rcx, [rax+8]; Destination
0x18000968f  call    cs:__imp_memcpy_s
0x180009695  movzx   eax, [rsp+48h+arg_0]
0x18000969a  mov     [rdi+4], eax
0x18000969d  jmp     short loc_1800096CA
0x18000969f  mov     ebp, 2
0x1800096a4  mov     rbx, r8
0x1800096a7  cmp     [rcx+2], bpl
0x1800096ab  jnz     short loc_1800096CA
0x1800096ad  lea     rbx, [r8+4]
0x1800096b1  cmp     rbx, rsi
0x1800096b4  ja      short loc_180009704
0x1800096b6  lea     edx, [rbp+2]; DestinationSize
0x1800096b9  mov     [rcx+10h], r8
0x1800096bd  mov     r9d, edx; SourceSize
0x1800096c0  add     rcx, 4; Destination
0x1800096c4  call    cs:__imp_memcpy_s
0x1800096ca  movzx   eax, word ptr [rdi]
0x1800096cd  lea     r14, [rdi+8]
0x1800096d1  mov     [r14], ax
0x1800096d5  test    ax, ax
0x1800096d8  jnz     short loc_1800096F8
0x1800096da  lea     r15, [rbx+2]
0x1800096de  cmp     r15, rsi
0x1800096e1  ja      short loc_180009704
0x1800096e3  mov     r9, rbp; SourceSize
0x1800096e6  mov     r8, rbx; Source
0x1800096e9  mov     rdx, rbp; DestinationSize
0x1800096ec  mov     rcx, r14; Destination
0x1800096ef  call    cs:__imp_memcpy_s
0x1800096f5  mov     rbx, r15
0x1800096f8  movzx   ecx, word ptr [r14]
0x1800096fc  add     rcx, rbx
0x1800096ff  cmp     rcx, rsi
0x180009702  jbe     short loc_180009708
0x180009704  xor     al, al
0x180009706  jmp     short loc_180009712
0x180009708  mov     [rdi+18h], rbx
0x18000970c  mov     al, 1
0x18000970e  mov     [r12], rcx
0x180009712  mov     rbx, [rsp+48h+arg_8]
0x180009717  mov     rbp, [rsp+48h+arg_10]
0x18000971c  add     rsp, 20h
0x180009720  pop     r15
0x180009722  pop     r14
0x180009724  pop     r12
0x180009726  pop     rdi
0x180009727  pop     rsi
0x180009728  retn
```
