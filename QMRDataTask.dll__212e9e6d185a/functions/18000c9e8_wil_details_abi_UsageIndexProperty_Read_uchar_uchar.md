# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x18000c9e8`
- end: `0x18000cad1`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180007a44`
- `0x18000d218`
- `0x18000d5a0`

## callees

- `0x18000c9e8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000ca37`
- `msvcrt!memcpy_s` at `0x18000ca6c`
- `msvcrt!memcpy_s` at `0x18000ca97`
- `msvcrt!memcpy_s` at `0x18000ca37`
- `msvcrt!memcpy_s` at `0x18000ca6c`
- `msvcrt!memcpy_s` at `0x18000ca97`

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
0x18000c9e8  mov     rax, rsp
0x18000c9eb  mov     [rax+10h], rbx
0x18000c9ef  mov     [rax+18h], rbp
0x18000c9f3  push    rsi
0x18000c9f4  push    rdi
0x18000c9f5  push    r12
0x18000c9f7  push    r14
0x18000c9f9  push    r15
0x18000c9fb  sub     rsp, 20h
0x18000c9ff  xor     r15d, r15d
0x18000ca02  mov     rsi, r8
0x18000ca05  cmp     byte ptr [rcx+2], 1
0x18000ca09  mov     r12, rdx
0x18000ca0c  mov     r8, [rdx]; Source
0x18000ca0f  mov     rdi, rcx
0x18000ca12  jnz     short loc_18000CA47
0x18000ca14  lea     rbx, [r8+2]
0x18000ca18  cmp     rbx, rsi
0x18000ca1b  ja      loc_18000CAAC
0x18000ca21  lea     ebp, [r15+2]
0x18000ca25  mov     [rcx+10h], r8
0x18000ca29  mov     r9d, ebp; SourceSize
0x18000ca2c  mov     [rax+8], r15w
0x18000ca31  mov     edx, ebp; DestinationSize
0x18000ca33  lea     rcx, [rax+8]; Destination
0x18000ca37  call    cs:__imp_memcpy_s
0x18000ca3d  movzx   eax, [rsp+48h+arg_0]
0x18000ca42  mov     [rdi+4], eax
0x18000ca45  jmp     short loc_18000CA72
0x18000ca47  mov     ebp, 2
0x18000ca4c  mov     rbx, r8
0x18000ca4f  cmp     [rcx+2], bpl
0x18000ca53  jnz     short loc_18000CA72
0x18000ca55  lea     rbx, [r8+4]
0x18000ca59  cmp     rbx, rsi
0x18000ca5c  ja      short loc_18000CAAC
0x18000ca5e  lea     edx, [rbp+2]; DestinationSize
0x18000ca61  mov     [rcx+10h], r8
0x18000ca65  mov     r9d, edx; SourceSize
0x18000ca68  add     rcx, 4; Destination
0x18000ca6c  call    cs:__imp_memcpy_s
0x18000ca72  movzx   eax, word ptr [rdi]
0x18000ca75  lea     r14, [rdi+8]
0x18000ca79  mov     [r14], ax
0x18000ca7d  test    ax, ax
0x18000ca80  jnz     short loc_18000CAA0
0x18000ca82  lea     r15, [rbx+2]
0x18000ca86  cmp     r15, rsi
0x18000ca89  ja      short loc_18000CAAC
0x18000ca8b  mov     r9, rbp; SourceSize
0x18000ca8e  mov     r8, rbx; Source
0x18000ca91  mov     rdx, rbp; DestinationSize
0x18000ca94  mov     rcx, r14; Destination
0x18000ca97  call    cs:__imp_memcpy_s
0x18000ca9d  mov     rbx, r15
0x18000caa0  movzx   ecx, word ptr [r14]
0x18000caa4  add     rcx, rbx
0x18000caa7  cmp     rcx, rsi
0x18000caaa  jbe     short loc_18000CAB0
0x18000caac  xor     al, al
0x18000caae  jmp     short loc_18000CABA
0x18000cab0  mov     [rdi+18h], rbx
0x18000cab4  mov     al, 1
0x18000cab6  mov     [r12], rcx
0x18000caba  mov     rbx, [rsp+48h+arg_8]
0x18000cabf  mov     rbp, [rsp+48h+arg_10]
0x18000cac4  add     rsp, 20h
0x18000cac8  pop     r15
0x18000caca  pop     r14
0x18000cacc  pop     r12
0x18000cace  pop     rdi
0x18000cacf  pop     rsi
0x18000cad0  retn
```
