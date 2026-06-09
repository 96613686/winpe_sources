# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x18000abbc`
- end: `0x18000aca2`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `230`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1800091f4`
- `0x180009ff8`
- `0x18000a488`
- `0x18000b1a4`
- `0x18000bec0`

## callees

- `0x18000abbc`
- `0x18000d374`

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
0x18000abbc  mov     rax, rsp
0x18000abbf  mov     [rax+10h], rbx
0x18000abc3  mov     [rax+18h], rbp
0x18000abc7  push    rsi
0x18000abc8  push    rdi
0x18000abc9  push    r12
0x18000abcb  push    r14
0x18000abcd  push    r15
0x18000abcf  sub     rsp, 20h
0x18000abd3  xor     r15d, r15d
0x18000abd6  mov     rsi, r8
0x18000abd9  cmp     byte ptr [rcx+2], 1
0x18000abdd  mov     r12, rdx
0x18000abe0  mov     r8, [rdx]; Source
0x18000abe3  mov     rdi, rcx
0x18000abe6  jnz     short loc_18000AC1A
0x18000abe8  lea     rbx, [r8+2]
0x18000abec  cmp     rbx, rsi
0x18000abef  ja      loc_18000AC7D
0x18000abf5  lea     ebp, [r15+2]
0x18000abf9  mov     [rcx+10h], r8
0x18000abfd  mov     r9d, ebp; SourceSize
0x18000ac00  mov     [rax+8], r15w
0x18000ac05  mov     edx, ebp; DestinationSize
0x18000ac07  lea     rcx, [rax+8]; Destination
0x18000ac0b  call    memcpy_s
0x18000ac10  movzx   eax, [rsp+48h+arg_0]
0x18000ac15  mov     [rdi+4], eax
0x18000ac18  jmp     short loc_18000AC44
0x18000ac1a  mov     ebp, 2
0x18000ac1f  mov     rbx, r8
0x18000ac22  cmp     [rcx+2], bpl
0x18000ac26  jnz     short loc_18000AC44
0x18000ac28  lea     rbx, [r8+4]
0x18000ac2c  cmp     rbx, rsi
0x18000ac2f  ja      short loc_18000AC7D
0x18000ac31  lea     edx, [rbp+2]; DestinationSize
0x18000ac34  mov     [rcx+10h], r8
0x18000ac38  mov     r9d, edx; SourceSize
0x18000ac3b  add     rcx, 4; Destination
0x18000ac3f  call    memcpy_s
0x18000ac44  movzx   eax, word ptr [rdi]
0x18000ac47  lea     r14, [rdi+8]
0x18000ac4b  mov     [r14], ax
0x18000ac4f  test    ax, ax
0x18000ac52  jnz     short loc_18000AC71
0x18000ac54  lea     r15, [rbx+2]
0x18000ac58  cmp     r15, rsi
0x18000ac5b  ja      short loc_18000AC7D
0x18000ac5d  mov     r9, rbp; SourceSize
0x18000ac60  mov     r8, rbx; Source
0x18000ac63  mov     rdx, rbp; DestinationSize
0x18000ac66  mov     rcx, r14; Destination
0x18000ac69  call    memcpy_s
0x18000ac6e  mov     rbx, r15
0x18000ac71  movzx   ecx, word ptr [r14]
0x18000ac75  add     rcx, rbx
0x18000ac78  cmp     rcx, rsi
0x18000ac7b  jbe     short loc_18000AC81
0x18000ac7d  xor     al, al
0x18000ac7f  jmp     short loc_18000AC8B
0x18000ac81  mov     [rdi+18h], rbx
0x18000ac85  mov     al, 1
0x18000ac87  mov     [r12], rcx
0x18000ac8b  mov     rbx, [rsp+48h+arg_8]
0x18000ac90  mov     rbp, [rsp+48h+arg_10]
0x18000ac95  add     rsp, 20h
0x18000ac99  pop     r15
0x18000ac9b  pop     r14
0x18000ac9d  pop     r12
0x18000ac9f  pop     rdi
0x18000aca0  pop     rsi
0x18000aca1  retn
```
