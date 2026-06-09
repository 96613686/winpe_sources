# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x18000cea0`
- end: `0x18000cf89`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a628`
- `0x18000d468`
- `0x18000d7f0`

## callees

- `0x18000cea0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000ceef`
- `msvcrt!memcpy_s` at `0x18000cf24`
- `msvcrt!memcpy_s` at `0x18000cf4f`
- `msvcrt!memcpy_s` at `0x18000ceef`
- `msvcrt!memcpy_s` at `0x18000cf24`
- `msvcrt!memcpy_s` at `0x18000cf4f`

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
0x18000cea0  mov     rax, rsp
0x18000cea3  mov     [rax+10h], rbx
0x18000cea7  mov     [rax+18h], rbp
0x18000ceab  push    rsi
0x18000ceac  push    rdi
0x18000cead  push    r12
0x18000ceaf  push    r14
0x18000ceb1  push    r15
0x18000ceb3  sub     rsp, 20h
0x18000ceb7  xor     r15d, r15d
0x18000ceba  mov     rsi, r8
0x18000cebd  cmp     byte ptr [rcx+2], 1
0x18000cec1  mov     r12, rdx
0x18000cec4  mov     r8, [rdx]; Source
0x18000cec7  mov     rdi, rcx
0x18000ceca  jnz     short loc_18000CEFF
0x18000cecc  lea     rbx, [r8+2]
0x18000ced0  cmp     rbx, rsi
0x18000ced3  ja      loc_18000CF64
0x18000ced9  lea     ebp, [r15+2]
0x18000cedd  mov     [rcx+10h], r8
0x18000cee1  mov     r9d, ebp; SourceSize
0x18000cee4  mov     [rax+8], r15w
0x18000cee9  mov     edx, ebp; DestinationSize
0x18000ceeb  lea     rcx, [rax+8]; Destination
0x18000ceef  call    cs:__imp_memcpy_s
0x18000cef5  movzx   eax, [rsp+48h+arg_0]
0x18000cefa  mov     [rdi+4], eax
0x18000cefd  jmp     short loc_18000CF2A
0x18000ceff  mov     ebp, 2
0x18000cf04  mov     rbx, r8
0x18000cf07  cmp     [rcx+2], bpl
0x18000cf0b  jnz     short loc_18000CF2A
0x18000cf0d  lea     rbx, [r8+4]
0x18000cf11  cmp     rbx, rsi
0x18000cf14  ja      short loc_18000CF64
0x18000cf16  lea     edx, [rbp+2]; DestinationSize
0x18000cf19  mov     [rcx+10h], r8
0x18000cf1d  mov     r9d, edx; SourceSize
0x18000cf20  add     rcx, 4; Destination
0x18000cf24  call    cs:__imp_memcpy_s
0x18000cf2a  movzx   eax, word ptr [rdi]
0x18000cf2d  lea     r14, [rdi+8]
0x18000cf31  mov     [r14], ax
0x18000cf35  test    ax, ax
0x18000cf38  jnz     short loc_18000CF58
0x18000cf3a  lea     r15, [rbx+2]
0x18000cf3e  cmp     r15, rsi
0x18000cf41  ja      short loc_18000CF64
0x18000cf43  mov     r9, rbp; SourceSize
0x18000cf46  mov     r8, rbx; Source
0x18000cf49  mov     rdx, rbp; DestinationSize
0x18000cf4c  mov     rcx, r14; Destination
0x18000cf4f  call    cs:__imp_memcpy_s
0x18000cf55  mov     rbx, r15
0x18000cf58  movzx   ecx, word ptr [r14]
0x18000cf5c  add     rcx, rbx
0x18000cf5f  cmp     rcx, rsi
0x18000cf62  jbe     short loc_18000CF68
0x18000cf64  xor     al, al
0x18000cf66  jmp     short loc_18000CF72
0x18000cf68  mov     [rdi+18h], rbx
0x18000cf6c  mov     al, 1
0x18000cf6e  mov     [r12], rcx
0x18000cf72  mov     rbx, [rsp+48h+arg_8]
0x18000cf77  mov     rbp, [rsp+48h+arg_10]
0x18000cf7c  add     rsp, 20h
0x18000cf80  pop     r15
0x18000cf82  pop     r14
0x18000cf84  pop     r12
0x18000cf86  pop     rdi
0x18000cf87  pop     rsi
0x18000cf88  retn
```
