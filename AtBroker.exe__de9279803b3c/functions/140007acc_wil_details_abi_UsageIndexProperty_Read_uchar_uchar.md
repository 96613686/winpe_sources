# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x140007acc`
- end: `0x140007bb5`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140005408`
- `0x140008344`
- `0x1400086cc`

## callees

- `0x140007acc`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140007b1b`
- `msvcrt!memcpy_s` at `0x140007b50`
- `msvcrt!memcpy_s` at `0x140007b7b`
- `msvcrt!memcpy_s` at `0x140007b1b`
- `msvcrt!memcpy_s` at `0x140007b50`
- `msvcrt!memcpy_s` at `0x140007b7b`

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
0x140007acc  mov     rax, rsp
0x140007acf  mov     [rax+10h], rbx
0x140007ad3  mov     [rax+18h], rbp
0x140007ad7  push    rsi
0x140007ad8  push    rdi
0x140007ad9  push    r12
0x140007adb  push    r14
0x140007add  push    r15
0x140007adf  sub     rsp, 20h
0x140007ae3  xor     r15d, r15d
0x140007ae6  mov     rsi, r8
0x140007ae9  cmp     byte ptr [rcx+2], 1
0x140007aed  mov     r12, rdx
0x140007af0  mov     r8, [rdx]; Source
0x140007af3  mov     rdi, rcx
0x140007af6  jnz     short loc_140007B2B
0x140007af8  lea     rbx, [r8+2]
0x140007afc  cmp     rbx, rsi
0x140007aff  ja      loc_140007B90
0x140007b05  lea     ebp, [r15+2]
0x140007b09  mov     [rcx+10h], r8
0x140007b0d  mov     r9d, ebp; SourceSize
0x140007b10  mov     [rax+8], r15w
0x140007b15  mov     edx, ebp; DestinationSize
0x140007b17  lea     rcx, [rax+8]; Destination
0x140007b1b  call    cs:__imp_memcpy_s
0x140007b21  movzx   eax, [rsp+48h+arg_0]
0x140007b26  mov     [rdi+4], eax
0x140007b29  jmp     short loc_140007B56
0x140007b2b  mov     ebp, 2
0x140007b30  mov     rbx, r8
0x140007b33  cmp     [rcx+2], bpl
0x140007b37  jnz     short loc_140007B56
0x140007b39  lea     rbx, [r8+4]
0x140007b3d  cmp     rbx, rsi
0x140007b40  ja      short loc_140007B90
0x140007b42  lea     edx, [rbp+2]; DestinationSize
0x140007b45  mov     [rcx+10h], r8
0x140007b49  mov     r9d, edx; SourceSize
0x140007b4c  add     rcx, 4; Destination
0x140007b50  call    cs:__imp_memcpy_s
0x140007b56  movzx   eax, word ptr [rdi]
0x140007b59  lea     r14, [rdi+8]
0x140007b5d  mov     [r14], ax
0x140007b61  test    ax, ax
0x140007b64  jnz     short loc_140007B84
0x140007b66  lea     r15, [rbx+2]
0x140007b6a  cmp     r15, rsi
0x140007b6d  ja      short loc_140007B90
0x140007b6f  mov     r9, rbp; SourceSize
0x140007b72  mov     r8, rbx; Source
0x140007b75  mov     rdx, rbp; DestinationSize
0x140007b78  mov     rcx, r14; Destination
0x140007b7b  call    cs:__imp_memcpy_s
0x140007b81  mov     rbx, r15
0x140007b84  movzx   ecx, word ptr [r14]
0x140007b88  add     rcx, rbx
0x140007b8b  cmp     rcx, rsi
0x140007b8e  jbe     short loc_140007B94
0x140007b90  xor     al, al
0x140007b92  jmp     short loc_140007B9E
0x140007b94  mov     [rdi+18h], rbx
0x140007b98  mov     al, 1
0x140007b9a  mov     [r12], rcx
0x140007b9e  mov     rbx, [rsp+48h+arg_8]
0x140007ba3  mov     rbp, [rsp+48h+arg_10]
0x140007ba8  add     rsp, 20h
0x140007bac  pop     r15
0x140007bae  pop     r14
0x140007bb0  pop     r12
0x140007bb2  pop     rdi
0x140007bb3  pop     rsi
0x140007bb4  retn
```
