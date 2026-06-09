# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x14000f198`
- end: `0x14000f281`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x14000b4b4`
- `0x14000dce4`
- `0x14000de14`
- `0x14000f718`
- `0x14001096c`

## callees

- `0x14000f198`

## import_xrefs

- `msvcrt!memcpy_s` at `0x14000f1e7`
- `msvcrt!memcpy_s` at `0x14000f21c`
- `msvcrt!memcpy_s` at `0x14000f247`
- `msvcrt!memcpy_s` at `0x14000f1e7`
- `msvcrt!memcpy_s` at `0x14000f21c`
- `msvcrt!memcpy_s` at `0x14000f247`

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
0x14000f198  mov     rax, rsp
0x14000f19b  mov     [rax+10h], rbx
0x14000f19f  mov     [rax+18h], rbp
0x14000f1a3  push    rsi
0x14000f1a4  push    rdi
0x14000f1a5  push    r12
0x14000f1a7  push    r14
0x14000f1a9  push    r15
0x14000f1ab  sub     rsp, 20h
0x14000f1af  xor     r15d, r15d
0x14000f1b2  mov     rsi, r8
0x14000f1b5  cmp     byte ptr [rcx+2], 1
0x14000f1b9  mov     r12, rdx
0x14000f1bc  mov     r8, [rdx]; Source
0x14000f1bf  mov     rdi, rcx
0x14000f1c2  jnz     short loc_14000F1F7
0x14000f1c4  lea     rbx, [r8+2]
0x14000f1c8  cmp     rbx, rsi
0x14000f1cb  ja      loc_14000F25C
0x14000f1d1  lea     ebp, [r15+2]
0x14000f1d5  mov     [rcx+10h], r8
0x14000f1d9  mov     r9d, ebp; SourceSize
0x14000f1dc  mov     [rax+8], r15w
0x14000f1e1  mov     edx, ebp; DestinationSize
0x14000f1e3  lea     rcx, [rax+8]; Destination
0x14000f1e7  call    cs:__imp_memcpy_s
0x14000f1ed  movzx   eax, [rsp+48h+arg_0]
0x14000f1f2  mov     [rdi+4], eax
0x14000f1f5  jmp     short loc_14000F222
0x14000f1f7  mov     ebp, 2
0x14000f1fc  mov     rbx, r8
0x14000f1ff  cmp     [rcx+2], bpl
0x14000f203  jnz     short loc_14000F222
0x14000f205  lea     rbx, [r8+4]
0x14000f209  cmp     rbx, rsi
0x14000f20c  ja      short loc_14000F25C
0x14000f20e  lea     edx, [rbp+2]; DestinationSize
0x14000f211  mov     [rcx+10h], r8
0x14000f215  mov     r9d, edx; SourceSize
0x14000f218  add     rcx, 4; Destination
0x14000f21c  call    cs:__imp_memcpy_s
0x14000f222  movzx   eax, word ptr [rdi]
0x14000f225  lea     r14, [rdi+8]
0x14000f229  mov     [r14], ax
0x14000f22d  test    ax, ax
0x14000f230  jnz     short loc_14000F250
0x14000f232  lea     r15, [rbx+2]
0x14000f236  cmp     r15, rsi
0x14000f239  ja      short loc_14000F25C
0x14000f23b  mov     r9, rbp; SourceSize
0x14000f23e  mov     r8, rbx; Source
0x14000f241  mov     rdx, rbp; DestinationSize
0x14000f244  mov     rcx, r14; Destination
0x14000f247  call    cs:__imp_memcpy_s
0x14000f24d  mov     rbx, r15
0x14000f250  movzx   ecx, word ptr [r14]
0x14000f254  add     rcx, rbx
0x14000f257  cmp     rcx, rsi
0x14000f25a  jbe     short loc_14000F260
0x14000f25c  xor     al, al
0x14000f25e  jmp     short loc_14000F26A
0x14000f260  mov     [rdi+18h], rbx
0x14000f264  mov     al, 1
0x14000f266  mov     [r12], rcx
0x14000f26a  mov     rbx, [rsp+48h+arg_8]
0x14000f26f  mov     rbp, [rsp+48h+arg_10]
0x14000f274  add     rsp, 20h
0x14000f278  pop     r15
0x14000f27a  pop     r14
0x14000f27c  pop     r12
0x14000f27e  pop     rdi
0x14000f27f  pop     rsi
0x14000f280  retn
```
