# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180007c8c`
- end: `0x180007d75`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000656c`
- `0x1800082c0`
- `0x180008648`

## callees

- `0x180007c8c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180007cdb`
- `msvcrt!memcpy_s` at `0x180007d10`
- `msvcrt!memcpy_s` at `0x180007d3b`
- `msvcrt!memcpy_s` at `0x180007cdb`
- `msvcrt!memcpy_s` at `0x180007d10`
- `msvcrt!memcpy_s` at `0x180007d3b`

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
0x180007c8c  mov     rax, rsp
0x180007c8f  mov     [rax+10h], rbx
0x180007c93  mov     [rax+18h], rbp
0x180007c97  push    rsi
0x180007c98  push    rdi
0x180007c99  push    r12
0x180007c9b  push    r14
0x180007c9d  push    r15
0x180007c9f  sub     rsp, 20h
0x180007ca3  xor     r15d, r15d
0x180007ca6  mov     rsi, r8
0x180007ca9  cmp     byte ptr [rcx+2], 1
0x180007cad  mov     r12, rdx
0x180007cb0  mov     r8, [rdx]; Source
0x180007cb3  mov     rdi, rcx
0x180007cb6  jnz     short loc_180007CEB
0x180007cb8  lea     rbx, [r8+2]
0x180007cbc  cmp     rbx, rsi
0x180007cbf  ja      loc_180007D50
0x180007cc5  lea     ebp, [r15+2]
0x180007cc9  mov     [rcx+10h], r8
0x180007ccd  mov     r9d, ebp; SourceSize
0x180007cd0  mov     [rax+8], r15w
0x180007cd5  mov     edx, ebp; DestinationSize
0x180007cd7  lea     rcx, [rax+8]; Destination
0x180007cdb  call    cs:__imp_memcpy_s
0x180007ce1  movzx   eax, [rsp+48h+arg_0]
0x180007ce6  mov     [rdi+4], eax
0x180007ce9  jmp     short loc_180007D16
0x180007ceb  mov     ebp, 2
0x180007cf0  mov     rbx, r8
0x180007cf3  cmp     [rcx+2], bpl
0x180007cf7  jnz     short loc_180007D16
0x180007cf9  lea     rbx, [r8+4]
0x180007cfd  cmp     rbx, rsi
0x180007d00  ja      short loc_180007D50
0x180007d02  lea     edx, [rbp+2]; DestinationSize
0x180007d05  mov     [rcx+10h], r8
0x180007d09  mov     r9d, edx; SourceSize
0x180007d0c  add     rcx, 4; Destination
0x180007d10  call    cs:__imp_memcpy_s
0x180007d16  movzx   eax, word ptr [rdi]
0x180007d19  lea     r14, [rdi+8]
0x180007d1d  mov     [r14], ax
0x180007d21  test    ax, ax
0x180007d24  jnz     short loc_180007D44
0x180007d26  lea     r15, [rbx+2]
0x180007d2a  cmp     r15, rsi
0x180007d2d  ja      short loc_180007D50
0x180007d2f  mov     r9, rbp; SourceSize
0x180007d32  mov     r8, rbx; Source
0x180007d35  mov     rdx, rbp; DestinationSize
0x180007d38  mov     rcx, r14; Destination
0x180007d3b  call    cs:__imp_memcpy_s
0x180007d41  mov     rbx, r15
0x180007d44  movzx   ecx, word ptr [r14]
0x180007d48  add     rcx, rbx
0x180007d4b  cmp     rcx, rsi
0x180007d4e  jbe     short loc_180007D54
0x180007d50  xor     al, al
0x180007d52  jmp     short loc_180007D5E
0x180007d54  mov     [rdi+18h], rbx
0x180007d58  mov     al, 1
0x180007d5a  mov     [r12], rcx
0x180007d5e  mov     rbx, [rsp+48h+arg_8]
0x180007d63  mov     rbp, [rsp+48h+arg_10]
0x180007d68  add     rsp, 20h
0x180007d6c  pop     r15
0x180007d6e  pop     r14
0x180007d70  pop     r12
0x180007d72  pop     rdi
0x180007d73  pop     rsi
0x180007d74  retn
```
