# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x18000572c`
- end: `0x180005828`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `252`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180003e88`
- `0x180005db4`
- `0x180006154`

## callees

- `0x18000572c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000577b`
- `msvcrt!memcpy_s` at `0x1800057b6`
- `msvcrt!memcpy_s` at `0x1800057e7`
- `msvcrt!memcpy_s` at `0x18000577b`
- `msvcrt!memcpy_s` at `0x1800057b6`
- `msvcrt!memcpy_s` at `0x1800057e7`

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
0x18000572c  mov     rax, rsp
0x18000572f  mov     [rax+10h], rbx
0x180005733  mov     [rax+18h], rbp
0x180005737  push    rsi
0x180005738  push    rdi
0x180005739  push    r12
0x18000573b  push    r14
0x18000573d  push    r15
0x18000573f  sub     rsp, 20h
0x180005743  xor     r15d, r15d
0x180005746  mov     rsi, r8
0x180005749  cmp     byte ptr [rcx+2], 1
0x18000574d  mov     r12, rdx
0x180005750  mov     r8, [rdx]; Source
0x180005753  mov     rdi, rcx
0x180005756  jnz     short loc_180005791
0x180005758  lea     rbx, [r8+2]
0x18000575c  cmp     rbx, rsi
0x18000575f  ja      loc_180005802
0x180005765  lea     ebp, [r15+2]
0x180005769  mov     [rcx+10h], r8
0x18000576d  mov     r9d, ebp; SourceSize
0x180005770  mov     [rax+8], r15w
0x180005775  mov     edx, ebp; DestinationSize
0x180005777  lea     rcx, [rax+8]; Destination
0x18000577b  call    cs:__imp_memcpy_s
0x180005782  nop     dword ptr [rax+rax+00h]
0x180005787  movzx   eax, [rsp+48h+arg_0]
0x18000578c  mov     [rdi+4], eax
0x18000578f  jmp     short loc_1800057C2
0x180005791  mov     ebp, 2
0x180005796  mov     rbx, r8
0x180005799  cmp     [rcx+2], bpl
0x18000579d  jnz     short loc_1800057C2
0x18000579f  lea     rbx, [r8+4]
0x1800057a3  cmp     rbx, rsi
0x1800057a6  ja      short loc_180005802
0x1800057a8  lea     edx, [rbp+2]; DestinationSize
0x1800057ab  mov     [rcx+10h], r8
0x1800057af  mov     r9d, edx; SourceSize
0x1800057b2  add     rcx, 4; Destination
0x1800057b6  call    cs:__imp_memcpy_s
0x1800057bd  nop     dword ptr [rax+rax+00h]
0x1800057c2  movzx   eax, word ptr [rdi]
0x1800057c5  lea     r14, [rdi+8]
0x1800057c9  mov     [r14], ax
0x1800057cd  test    ax, ax
0x1800057d0  jnz     short loc_1800057F6
0x1800057d2  lea     r15, [rbx+2]
0x1800057d6  cmp     r15, rsi
0x1800057d9  ja      short loc_180005802
0x1800057db  mov     r9, rbp; SourceSize
0x1800057de  mov     r8, rbx; Source
0x1800057e1  mov     rdx, rbp; DestinationSize
0x1800057e4  mov     rcx, r14; Destination
0x1800057e7  call    cs:__imp_memcpy_s
0x1800057ee  nop     dword ptr [rax+rax+00h]
0x1800057f3  mov     rbx, r15
0x1800057f6  movzx   ecx, word ptr [r14]
0x1800057fa  add     rcx, rbx
0x1800057fd  cmp     rcx, rsi
0x180005800  jbe     short loc_180005806
0x180005802  xor     al, al
0x180005804  jmp     short loc_180005810
0x180005806  mov     [rdi+18h], rbx
0x18000580a  mov     al, 1
0x18000580c  mov     [r12], rcx
0x180005810  mov     rbx, [rsp+48h+arg_8]
0x180005815  mov     rbp, [rsp+48h+arg_10]
0x18000581a  add     rsp, 20h
0x18000581e  pop     r15
0x180005820  pop     r14
0x180005822  pop     r12
0x180005824  pop     rdi
0x180005825  pop     rsi
0x180005826  retn
```
