# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x180015a7c`
- end: `0x180015b55`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `217`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180013c08`

## callees

- `0x180015a7c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180015adc`
- `msvcrt!memcpy_s` at `0x180015b07`
- `msvcrt!memcpy_s` at `0x180015b34`
- `msvcrt!memcpy_s` at `0x180015adc`
- `msvcrt!memcpy_s` at `0x180015b07`
- `msvcrt!memcpy_s` at `0x180015b34`

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
0x180015a7c  push    rbx
0x180015a7e  push    rsi
0x180015a7f  push    rdi
0x180015a80  push    r12
0x180015a82  push    r14
0x180015a84  push    r15
0x180015a86  sub     rsp, 28h
0x180015a8a  mov     rsi, rcx
0x180015a8d  mov     rdi, r8
0x180015a90  mov     rcx, [rdx]; Destination
0x180015a93  mov     r12, rdx
0x180015a96  cmp     byte ptr [rsi+2], 1
0x180015a9a  jnz     short loc_180015ABE
0x180015a9c  lea     rbx, [rcx+2]
0x180015aa0  cmp     rbx, r8
0x180015aa3  ja      short loc_180015B23
0x180015aa5  movzx   eax, word ptr [rsi+4]
0x180015aa9  lea     r8, [rsp+58h+arg_0]
0x180015aae  mov     r9d, 2
0x180015ab4  mov     [rsp+58h+arg_0], ax
0x180015ab9  mov     edx, r9d
0x180015abc  jmp     short loc_180015ADC
0x180015abe  cmp     byte ptr [rsi+2], 2
0x180015ac2  mov     rbx, rcx
0x180015ac5  jnz     short loc_180015AE2
0x180015ac7  lea     rbx, [rcx+4]
0x180015acb  cmp     rbx, rdi
0x180015ace  ja      short loc_180015B23
0x180015ad0  mov     edx, 4; DestinationSize
0x180015ad5  lea     r8, [rsi+4]; Source
0x180015ad9  mov     r9d, edx; SourceSize
0x180015adc  call    cs:__imp_memcpy_s
0x180015ae2  cmp     word ptr [rsi], 0
0x180015ae6  jnz     short loc_180015B12
0x180015ae8  lea     r15, [rbx+2]
0x180015aec  cmp     r15, rdi
0x180015aef  ja      short loc_180015B23
0x180015af1  lea     r14, [rsi+8]
0x180015af5  mov     rdx, rdi
0x180015af8  sub     rdx, rbx; DestinationSize
0x180015afb  mov     r8, r14; Source
0x180015afe  mov     r9d, 2; SourceSize
0x180015b04  mov     rcx, rbx; Destination
0x180015b07  call    cs:__imp_memcpy_s
0x180015b0d  mov     rbx, r15
0x180015b10  jmp     short loc_180015B16
0x180015b12  lea     r14, [rsi+8]
0x180015b16  movzx   r9d, word ptr [r14]; SourceSize
0x180015b1a  lea     rax, [r9+rbx]
0x180015b1e  cmp     rax, rdi
0x180015b21  jbe     short loc_180015B27
0x180015b23  xor     al, al
0x180015b25  jmp     short loc_180015B47
0x180015b27  mov     r8, [rsi+18h]; Source
0x180015b2b  sub     rdi, rbx
0x180015b2e  mov     rdx, rdi; DestinationSize
0x180015b31  mov     rcx, rbx; Destination
0x180015b34  call    cs:__imp_memcpy_s
0x180015b3a  movzx   ecx, word ptr [r14]
0x180015b3e  mov     al, 1
0x180015b40  add     rcx, rbx
0x180015b43  mov     [r12], rcx
0x180015b47  add     rsp, 28h
0x180015b4b  pop     r15
0x180015b4d  pop     r14
0x180015b4f  pop     r12
0x180015b51  pop     rdi
0x180015b52  pop     rsi
0x180015b53  pop     rbx
0x180015b54  retn
```
