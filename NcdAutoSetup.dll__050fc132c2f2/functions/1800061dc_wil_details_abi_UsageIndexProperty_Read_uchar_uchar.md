# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x1800061dc`
- end: `0x1800062c5`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180004870`
- `0x180006810`
- `0x180006b98`

## callees

- `0x1800061dc`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000622b`
- `msvcrt!memcpy_s` at `0x180006260`
- `msvcrt!memcpy_s` at `0x18000628b`
- `msvcrt!memcpy_s` at `0x18000622b`
- `msvcrt!memcpy_s` at `0x180006260`
- `msvcrt!memcpy_s` at `0x18000628b`

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
0x1800061dc  mov     rax, rsp
0x1800061df  mov     [rax+10h], rbx
0x1800061e3  mov     [rax+18h], rbp
0x1800061e7  push    rsi
0x1800061e8  push    rdi
0x1800061e9  push    r12
0x1800061eb  push    r14
0x1800061ed  push    r15
0x1800061ef  sub     rsp, 20h
0x1800061f3  xor     r15d, r15d
0x1800061f6  mov     rsi, r8
0x1800061f9  cmp     byte ptr [rcx+2], 1
0x1800061fd  mov     r12, rdx
0x180006200  mov     r8, [rdx]; Source
0x180006203  mov     rdi, rcx
0x180006206  jnz     short loc_18000623B
0x180006208  lea     rbx, [r8+2]
0x18000620c  cmp     rbx, rsi
0x18000620f  ja      loc_1800062A0
0x180006215  lea     ebp, [r15+2]
0x180006219  mov     [rcx+10h], r8
0x18000621d  mov     r9d, ebp; SourceSize
0x180006220  mov     [rax+8], r15w
0x180006225  mov     edx, ebp; DestinationSize
0x180006227  lea     rcx, [rax+8]; Destination
0x18000622b  call    cs:__imp_memcpy_s
0x180006231  movzx   eax, [rsp+48h+arg_0]
0x180006236  mov     [rdi+4], eax
0x180006239  jmp     short loc_180006266
0x18000623b  mov     ebp, 2
0x180006240  mov     rbx, r8
0x180006243  cmp     [rcx+2], bpl
0x180006247  jnz     short loc_180006266
0x180006249  lea     rbx, [r8+4]
0x18000624d  cmp     rbx, rsi
0x180006250  ja      short loc_1800062A0
0x180006252  lea     edx, [rbp+2]; DestinationSize
0x180006255  mov     [rcx+10h], r8
0x180006259  mov     r9d, edx; SourceSize
0x18000625c  add     rcx, 4; Destination
0x180006260  call    cs:__imp_memcpy_s
0x180006266  movzx   eax, word ptr [rdi]
0x180006269  lea     r14, [rdi+8]
0x18000626d  mov     [r14], ax
0x180006271  test    ax, ax
0x180006274  jnz     short loc_180006294
0x180006276  lea     r15, [rbx+2]
0x18000627a  cmp     r15, rsi
0x18000627d  ja      short loc_1800062A0
0x18000627f  mov     r9, rbp; SourceSize
0x180006282  mov     r8, rbx; Source
0x180006285  mov     rdx, rbp; DestinationSize
0x180006288  mov     rcx, r14; Destination
0x18000628b  call    cs:__imp_memcpy_s
0x180006291  mov     rbx, r15
0x180006294  movzx   ecx, word ptr [r14]
0x180006298  add     rcx, rbx
0x18000629b  cmp     rcx, rsi
0x18000629e  jbe     short loc_1800062A4
0x1800062a0  xor     al, al
0x1800062a2  jmp     short loc_1800062AE
0x1800062a4  mov     [rdi+18h], rbx
0x1800062a8  mov     al, 1
0x1800062aa  mov     [r12], rcx
0x1800062ae  mov     rbx, [rsp+48h+arg_8]
0x1800062b3  mov     rbp, [rsp+48h+arg_10]
0x1800062b8  add     rsp, 20h
0x1800062bc  pop     r15
0x1800062be  pop     r14
0x1800062c0  pop     r12
0x1800062c2  pop     rdi
0x1800062c3  pop     rsi
0x1800062c4  retn
```
