# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180013c00`
- end: `0x180013ce9`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180012264`
- `0x180013074`
- `0x180013518`
- `0x1800141a4`
- `0x180014db4`

## callees

- `0x180013c00`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180013c4f`
- `msvcrt!memcpy_s` at `0x180013c84`
- `msvcrt!memcpy_s` at `0x180013caf`
- `msvcrt!memcpy_s` at `0x180013c4f`
- `msvcrt!memcpy_s` at `0x180013c84`
- `msvcrt!memcpy_s` at `0x180013caf`

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
0x180013c00  mov     rax, rsp
0x180013c03  mov     [rax+10h], rbx
0x180013c07  mov     [rax+18h], rbp
0x180013c0b  push    rsi
0x180013c0c  push    rdi
0x180013c0d  push    r12
0x180013c0f  push    r14
0x180013c11  push    r15
0x180013c13  sub     rsp, 20h
0x180013c17  xor     r15d, r15d
0x180013c1a  mov     rsi, r8
0x180013c1d  cmp     byte ptr [rcx+2], 1
0x180013c21  mov     r12, rdx
0x180013c24  mov     r8, [rdx]; Source
0x180013c27  mov     rdi, rcx
0x180013c2a  jnz     short loc_180013C5F
0x180013c2c  lea     rbx, [r8+2]
0x180013c30  cmp     rbx, rsi
0x180013c33  ja      loc_180013CC4
0x180013c39  lea     ebp, [r15+2]
0x180013c3d  mov     [rcx+10h], r8
0x180013c41  mov     r9d, ebp; SourceSize
0x180013c44  mov     [rax+8], r15w
0x180013c49  mov     edx, ebp; DestinationSize
0x180013c4b  lea     rcx, [rax+8]; Destination
0x180013c4f  call    cs:__imp_memcpy_s
0x180013c55  movzx   eax, [rsp+48h+arg_0]
0x180013c5a  mov     [rdi+4], eax
0x180013c5d  jmp     short loc_180013C8A
0x180013c5f  mov     ebp, 2
0x180013c64  mov     rbx, r8
0x180013c67  cmp     [rcx+2], bpl
0x180013c6b  jnz     short loc_180013C8A
0x180013c6d  lea     rbx, [r8+4]
0x180013c71  cmp     rbx, rsi
0x180013c74  ja      short loc_180013CC4
0x180013c76  lea     edx, [rbp+2]; DestinationSize
0x180013c79  mov     [rcx+10h], r8
0x180013c7d  mov     r9d, edx; SourceSize
0x180013c80  add     rcx, 4; Destination
0x180013c84  call    cs:__imp_memcpy_s
0x180013c8a  movzx   eax, word ptr [rdi]
0x180013c8d  lea     r14, [rdi+8]
0x180013c91  mov     [r14], ax
0x180013c95  test    ax, ax
0x180013c98  jnz     short loc_180013CB8
0x180013c9a  lea     r15, [rbx+2]
0x180013c9e  cmp     r15, rsi
0x180013ca1  ja      short loc_180013CC4
0x180013ca3  mov     r9, rbp; SourceSize
0x180013ca6  mov     r8, rbx; Source
0x180013ca9  mov     rdx, rbp; DestinationSize
0x180013cac  mov     rcx, r14; Destination
0x180013caf  call    cs:__imp_memcpy_s
0x180013cb5  mov     rbx, r15
0x180013cb8  movzx   ecx, word ptr [r14]
0x180013cbc  add     rcx, rbx
0x180013cbf  cmp     rcx, rsi
0x180013cc2  jbe     short loc_180013CC8
0x180013cc4  xor     al, al
0x180013cc6  jmp     short loc_180013CD2
0x180013cc8  mov     [rdi+18h], rbx
0x180013ccc  mov     al, 1
0x180013cce  mov     [r12], rcx
0x180013cd2  mov     rbx, [rsp+48h+arg_8]
0x180013cd7  mov     rbp, [rsp+48h+arg_10]
0x180013cdc  add     rsp, 20h
0x180013ce0  pop     r15
0x180013ce2  pop     r14
0x180013ce4  pop     r12
0x180013ce6  pop     rdi
0x180013ce7  pop     rsi
0x180013ce8  retn
```
