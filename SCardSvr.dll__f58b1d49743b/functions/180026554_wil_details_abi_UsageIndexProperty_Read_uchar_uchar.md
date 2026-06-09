# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180026554`
- end: `0x18002663d`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180019860`
- `0x180024ed8`
- `0x180025b3c`
- `0x180025fdc`
- `0x1800275dc`

## callees

- `0x180026554`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800265a3`
- `msvcrt!memcpy_s` at `0x1800265d8`
- `msvcrt!memcpy_s` at `0x180026603`
- `msvcrt!memcpy_s` at `0x1800265a3`
- `msvcrt!memcpy_s` at `0x1800265d8`
- `msvcrt!memcpy_s` at `0x180026603`

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
0x180026554  mov     rax, rsp
0x180026557  mov     [rax+10h], rbx
0x18002655b  mov     [rax+18h], rbp
0x18002655f  push    rsi
0x180026560  push    rdi
0x180026561  push    r12
0x180026563  push    r14
0x180026565  push    r15
0x180026567  sub     rsp, 20h
0x18002656b  xor     r15d, r15d
0x18002656e  mov     rsi, r8
0x180026571  cmp     byte ptr [rcx+2], 1
0x180026575  mov     r12, rdx
0x180026578  mov     r8, [rdx]; Source
0x18002657b  mov     rdi, rcx
0x18002657e  jnz     short loc_1800265B3
0x180026580  lea     rbx, [r8+2]
0x180026584  cmp     rbx, rsi
0x180026587  ja      loc_180026618
0x18002658d  lea     ebp, [r15+2]
0x180026591  mov     [rcx+10h], r8
0x180026595  mov     r9d, ebp; SourceSize
0x180026598  mov     [rax+8], r15w
0x18002659d  mov     edx, ebp; DestinationSize
0x18002659f  lea     rcx, [rax+8]; Destination
0x1800265a3  call    cs:__imp_memcpy_s
0x1800265a9  movzx   eax, [rsp+48h+arg_0]
0x1800265ae  mov     [rdi+4], eax
0x1800265b1  jmp     short loc_1800265DE
0x1800265b3  mov     ebp, 2
0x1800265b8  mov     rbx, r8
0x1800265bb  cmp     [rcx+2], bpl
0x1800265bf  jnz     short loc_1800265DE
0x1800265c1  lea     rbx, [r8+4]
0x1800265c5  cmp     rbx, rsi
0x1800265c8  ja      short loc_180026618
0x1800265ca  lea     edx, [rbp+2]; DestinationSize
0x1800265cd  mov     [rcx+10h], r8
0x1800265d1  mov     r9d, edx; SourceSize
0x1800265d4  add     rcx, 4; Destination
0x1800265d8  call    cs:__imp_memcpy_s
0x1800265de  movzx   eax, word ptr [rdi]
0x1800265e1  lea     r14, [rdi+8]
0x1800265e5  mov     [r14], ax
0x1800265e9  test    ax, ax
0x1800265ec  jnz     short loc_18002660C
0x1800265ee  lea     r15, [rbx+2]
0x1800265f2  cmp     r15, rsi
0x1800265f5  ja      short loc_180026618
0x1800265f7  mov     r9, rbp; SourceSize
0x1800265fa  mov     r8, rbx; Source
0x1800265fd  mov     rdx, rbp; DestinationSize
0x180026600  mov     rcx, r14; Destination
0x180026603  call    cs:__imp_memcpy_s
0x180026609  mov     rbx, r15
0x18002660c  movzx   ecx, word ptr [r14]
0x180026610  add     rcx, rbx
0x180026613  cmp     rcx, rsi
0x180026616  jbe     short loc_18002661C
0x180026618  xor     al, al
0x18002661a  jmp     short loc_180026626
0x18002661c  mov     [rdi+18h], rbx
0x180026620  mov     al, 1
0x180026622  mov     [r12], rcx
0x180026626  mov     rbx, [rsp+48h+arg_8]
0x18002662b  mov     rbp, [rsp+48h+arg_10]
0x180026630  add     rsp, 20h
0x180026634  pop     r15
0x180026636  pop     r14
0x180026638  pop     r12
0x18002663a  pop     rdi
0x18002663b  pop     rsi
0x18002663c  retn
```
