# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x18001cdf0`
- end: `0x18001ced9`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18001c668`
- `0x18001c898`
- `0x18001c9d8`
- `0x18001d320`
- `0x18001d8f8`

## callees

- `0x18001cdf0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18001ce3f`
- `msvcrt!memcpy_s` at `0x18001ce74`
- `msvcrt!memcpy_s` at `0x18001ce9f`
- `msvcrt!memcpy_s` at `0x18001ce3f`
- `msvcrt!memcpy_s` at `0x18001ce74`
- `msvcrt!memcpy_s` at `0x18001ce9f`

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
0x18001cdf0  mov     rax, rsp
0x18001cdf3  mov     [rax+10h], rbx
0x18001cdf7  mov     [rax+18h], rbp
0x18001cdfb  push    rsi
0x18001cdfc  push    rdi
0x18001cdfd  push    r12
0x18001cdff  push    r14
0x18001ce01  push    r15
0x18001ce03  sub     rsp, 20h
0x18001ce07  xor     r15d, r15d
0x18001ce0a  mov     rsi, r8
0x18001ce0d  cmp     byte ptr [rcx+2], 1
0x18001ce11  mov     r12, rdx
0x18001ce14  mov     r8, [rdx]; Source
0x18001ce17  mov     rdi, rcx
0x18001ce1a  jnz     short loc_18001CE4F
0x18001ce1c  lea     rbx, [r8+2]
0x18001ce20  cmp     rbx, rsi
0x18001ce23  ja      loc_18001CEB4
0x18001ce29  lea     ebp, [r15+2]
0x18001ce2d  mov     [rcx+10h], r8
0x18001ce31  mov     r9d, ebp; SourceSize
0x18001ce34  mov     [rax+8], r15w
0x18001ce39  mov     edx, ebp; DestinationSize
0x18001ce3b  lea     rcx, [rax+8]; Destination
0x18001ce3f  call    cs:__imp_memcpy_s
0x18001ce45  movzx   eax, [rsp+48h+arg_0]
0x18001ce4a  mov     [rdi+4], eax
0x18001ce4d  jmp     short loc_18001CE7A
0x18001ce4f  mov     ebp, 2
0x18001ce54  mov     rbx, r8
0x18001ce57  cmp     [rcx+2], bpl
0x18001ce5b  jnz     short loc_18001CE7A
0x18001ce5d  lea     rbx, [r8+4]
0x18001ce61  cmp     rbx, rsi
0x18001ce64  ja      short loc_18001CEB4
0x18001ce66  lea     edx, [rbp+2]; DestinationSize
0x18001ce69  mov     [rcx+10h], r8
0x18001ce6d  mov     r9d, edx; SourceSize
0x18001ce70  add     rcx, 4; Destination
0x18001ce74  call    cs:__imp_memcpy_s
0x18001ce7a  movzx   eax, word ptr [rdi]
0x18001ce7d  lea     r14, [rdi+8]
0x18001ce81  mov     [r14], ax
0x18001ce85  test    ax, ax
0x18001ce88  jnz     short loc_18001CEA8
0x18001ce8a  lea     r15, [rbx+2]
0x18001ce8e  cmp     r15, rsi
0x18001ce91  ja      short loc_18001CEB4
0x18001ce93  mov     r9, rbp; SourceSize
0x18001ce96  mov     r8, rbx; Source
0x18001ce99  mov     rdx, rbp; DestinationSize
0x18001ce9c  mov     rcx, r14; Destination
0x18001ce9f  call    cs:__imp_memcpy_s
0x18001cea5  mov     rbx, r15
0x18001cea8  movzx   ecx, word ptr [r14]
0x18001ceac  add     rcx, rbx
0x18001ceaf  cmp     rcx, rsi
0x18001ceb2  jbe     short loc_18001CEB8
0x18001ceb4  xor     al, al
0x18001ceb6  jmp     short loc_18001CEC2
0x18001ceb8  mov     [rdi+18h], rbx
0x18001cebc  mov     al, 1
0x18001cebe  mov     [r12], rcx
0x18001cec2  mov     rbx, [rsp+48h+arg_8]
0x18001cec7  mov     rbp, [rsp+48h+arg_10]
0x18001cecc  add     rsp, 20h
0x18001ced0  pop     r15
0x18001ced2  pop     r14
0x18001ced4  pop     r12
0x18001ced6  pop     rdi
0x18001ced7  pop     rsi
0x18001ced8  retn
```
