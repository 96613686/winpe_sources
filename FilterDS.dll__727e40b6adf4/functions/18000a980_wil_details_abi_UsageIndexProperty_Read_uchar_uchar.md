# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x18000a980`
- end: `0x18000aa69`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180009d2c`
- `0x18000af54`
- `0x18000b2dc`

## callees

- `0x18000a980`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000a9cf`
- `msvcrt!memcpy_s` at `0x18000aa04`
- `msvcrt!memcpy_s` at `0x18000aa2f`
- `msvcrt!memcpy_s` at `0x18000a9cf`
- `msvcrt!memcpy_s` at `0x18000aa04`
- `msvcrt!memcpy_s` at `0x18000aa2f`

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
0x18000a980  mov     rax, rsp
0x18000a983  mov     [rax+10h], rbx
0x18000a987  mov     [rax+18h], rbp
0x18000a98b  push    rsi
0x18000a98c  push    rdi
0x18000a98d  push    r12
0x18000a98f  push    r14
0x18000a991  push    r15
0x18000a993  sub     rsp, 20h
0x18000a997  xor     r15d, r15d
0x18000a99a  mov     rsi, r8
0x18000a99d  cmp     byte ptr [rcx+2], 1
0x18000a9a1  mov     r12, rdx
0x18000a9a4  mov     r8, [rdx]; Source
0x18000a9a7  mov     rdi, rcx
0x18000a9aa  jnz     short loc_18000A9DF
0x18000a9ac  lea     rbx, [r8+2]
0x18000a9b0  cmp     rbx, rsi
0x18000a9b3  ja      loc_18000AA44
0x18000a9b9  lea     ebp, [r15+2]
0x18000a9bd  mov     [rcx+10h], r8
0x18000a9c1  mov     r9d, ebp; SourceSize
0x18000a9c4  mov     [rax+8], r15w
0x18000a9c9  mov     edx, ebp; DestinationSize
0x18000a9cb  lea     rcx, [rax+8]; Destination
0x18000a9cf  call    cs:__imp_memcpy_s
0x18000a9d5  movzx   eax, [rsp+48h+arg_0]
0x18000a9da  mov     [rdi+4], eax
0x18000a9dd  jmp     short loc_18000AA0A
0x18000a9df  mov     ebp, 2
0x18000a9e4  mov     rbx, r8
0x18000a9e7  cmp     [rcx+2], bpl
0x18000a9eb  jnz     short loc_18000AA0A
0x18000a9ed  lea     rbx, [r8+4]
0x18000a9f1  cmp     rbx, rsi
0x18000a9f4  ja      short loc_18000AA44
0x18000a9f6  lea     edx, [rbp+2]; DestinationSize
0x18000a9f9  mov     [rcx+10h], r8
0x18000a9fd  mov     r9d, edx; SourceSize
0x18000aa00  add     rcx, 4; Destination
0x18000aa04  call    cs:__imp_memcpy_s
0x18000aa0a  movzx   eax, word ptr [rdi]
0x18000aa0d  lea     r14, [rdi+8]
0x18000aa11  mov     [r14], ax
0x18000aa15  test    ax, ax
0x18000aa18  jnz     short loc_18000AA38
0x18000aa1a  lea     r15, [rbx+2]
0x18000aa1e  cmp     r15, rsi
0x18000aa21  ja      short loc_18000AA44
0x18000aa23  mov     r9, rbp; SourceSize
0x18000aa26  mov     r8, rbx; Source
0x18000aa29  mov     rdx, rbp; DestinationSize
0x18000aa2c  mov     rcx, r14; Destination
0x18000aa2f  call    cs:__imp_memcpy_s
0x18000aa35  mov     rbx, r15
0x18000aa38  movzx   ecx, word ptr [r14]
0x18000aa3c  add     rcx, rbx
0x18000aa3f  cmp     rcx, rsi
0x18000aa42  jbe     short loc_18000AA48
0x18000aa44  xor     al, al
0x18000aa46  jmp     short loc_18000AA52
0x18000aa48  mov     [rdi+18h], rbx
0x18000aa4c  mov     al, 1
0x18000aa4e  mov     [r12], rcx
0x18000aa52  mov     rbx, [rsp+48h+arg_8]
0x18000aa57  mov     rbp, [rsp+48h+arg_10]
0x18000aa5c  add     rsp, 20h
0x18000aa60  pop     r15
0x18000aa62  pop     r14
0x18000aa64  pop     r12
0x18000aa66  pop     rdi
0x18000aa67  pop     rsi
0x18000aa68  retn
```
