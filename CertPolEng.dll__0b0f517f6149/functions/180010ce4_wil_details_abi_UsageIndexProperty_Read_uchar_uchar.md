# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180010ce4`
- end: `0x180010dcd`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18000fa84`
- `0x180010590`
- `0x1800106c0`
- `0x180010f1c`
- `0x180011a5c`

## callees

- `0x180010ce4`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180010d33`
- `msvcrt!memcpy_s` at `0x180010d68`
- `msvcrt!memcpy_s` at `0x180010d93`
- `msvcrt!memcpy_s` at `0x180010d33`
- `msvcrt!memcpy_s` at `0x180010d68`
- `msvcrt!memcpy_s` at `0x180010d93`

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
0x180010ce4  mov     rax, rsp
0x180010ce7  mov     [rax+10h], rbx
0x180010ceb  mov     [rax+18h], rbp
0x180010cef  push    rsi
0x180010cf0  push    rdi
0x180010cf1  push    r12
0x180010cf3  push    r14
0x180010cf5  push    r15
0x180010cf7  sub     rsp, 20h
0x180010cfb  xor     r15d, r15d
0x180010cfe  mov     rsi, r8
0x180010d01  cmp     byte ptr [rcx+2], 1
0x180010d05  mov     r12, rdx
0x180010d08  mov     r8, [rdx]; Source
0x180010d0b  mov     rdi, rcx
0x180010d0e  jnz     short loc_180010D43
0x180010d10  lea     rbx, [r8+2]
0x180010d14  cmp     rbx, rsi
0x180010d17  ja      loc_180010DA8
0x180010d1d  lea     ebp, [r15+2]
0x180010d21  mov     [rcx+10h], r8
0x180010d25  mov     r9d, ebp; SourceSize
0x180010d28  mov     [rax+8], r15w
0x180010d2d  mov     edx, ebp; DestinationSize
0x180010d2f  lea     rcx, [rax+8]; Destination
0x180010d33  call    cs:__imp_memcpy_s
0x180010d39  movzx   eax, [rsp+48h+arg_0]
0x180010d3e  mov     [rdi+4], eax
0x180010d41  jmp     short loc_180010D6E
0x180010d43  mov     ebp, 2
0x180010d48  mov     rbx, r8
0x180010d4b  cmp     [rcx+2], bpl
0x180010d4f  jnz     short loc_180010D6E
0x180010d51  lea     rbx, [r8+4]
0x180010d55  cmp     rbx, rsi
0x180010d58  ja      short loc_180010DA8
0x180010d5a  lea     edx, [rbp+2]; DestinationSize
0x180010d5d  mov     [rcx+10h], r8
0x180010d61  mov     r9d, edx; SourceSize
0x180010d64  add     rcx, 4; Destination
0x180010d68  call    cs:__imp_memcpy_s
0x180010d6e  movzx   eax, word ptr [rdi]
0x180010d71  lea     r14, [rdi+8]
0x180010d75  mov     [r14], ax
0x180010d79  test    ax, ax
0x180010d7c  jnz     short loc_180010D9C
0x180010d7e  lea     r15, [rbx+2]
0x180010d82  cmp     r15, rsi
0x180010d85  ja      short loc_180010DA8
0x180010d87  mov     r9, rbp; SourceSize
0x180010d8a  mov     r8, rbx; Source
0x180010d8d  mov     rdx, rbp; DestinationSize
0x180010d90  mov     rcx, r14; Destination
0x180010d93  call    cs:__imp_memcpy_s
0x180010d99  mov     rbx, r15
0x180010d9c  movzx   ecx, word ptr [r14]
0x180010da0  add     rcx, rbx
0x180010da3  cmp     rcx, rsi
0x180010da6  jbe     short loc_180010DAC
0x180010da8  xor     al, al
0x180010daa  jmp     short loc_180010DB6
0x180010dac  mov     [rdi+18h], rbx
0x180010db0  mov     al, 1
0x180010db2  mov     [r12], rcx
0x180010db6  mov     rbx, [rsp+48h+arg_8]
0x180010dbb  mov     rbp, [rsp+48h+arg_10]
0x180010dc0  add     rsp, 20h
0x180010dc4  pop     r15
0x180010dc6  pop     r14
0x180010dc8  pop     r12
0x180010dca  pop     rdi
0x180010dcb  pop     rsi
0x180010dcc  retn
```
