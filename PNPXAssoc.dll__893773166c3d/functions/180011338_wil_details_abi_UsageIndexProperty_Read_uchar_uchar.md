# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180011338`
- end: `0x180011421`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180010dbc`
- `0x1800118f8`
- `0x180011c80`

## callees

- `0x180011338`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180011387`
- `msvcrt!memcpy_s` at `0x1800113bc`
- `msvcrt!memcpy_s` at `0x1800113e7`
- `msvcrt!memcpy_s` at `0x180011387`
- `msvcrt!memcpy_s` at `0x1800113bc`
- `msvcrt!memcpy_s` at `0x1800113e7`

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
0x180011338  mov     rax, rsp
0x18001133b  mov     [rax+10h], rbx
0x18001133f  mov     [rax+18h], rbp
0x180011343  push    rsi
0x180011344  push    rdi
0x180011345  push    r12
0x180011347  push    r14
0x180011349  push    r15
0x18001134b  sub     rsp, 20h
0x18001134f  xor     r15d, r15d
0x180011352  mov     rsi, r8
0x180011355  cmp     byte ptr [rcx+2], 1
0x180011359  mov     r12, rdx
0x18001135c  mov     r8, [rdx]; Source
0x18001135f  mov     rdi, rcx
0x180011362  jnz     short loc_180011397
0x180011364  lea     rbx, [r8+2]
0x180011368  cmp     rbx, rsi
0x18001136b  ja      loc_1800113FC
0x180011371  lea     ebp, [r15+2]
0x180011375  mov     [rcx+10h], r8
0x180011379  mov     r9d, ebp; SourceSize
0x18001137c  mov     [rax+8], r15w
0x180011381  mov     edx, ebp; DestinationSize
0x180011383  lea     rcx, [rax+8]; Destination
0x180011387  call    cs:__imp_memcpy_s
0x18001138d  movzx   eax, [rsp+48h+arg_0]
0x180011392  mov     [rdi+4], eax
0x180011395  jmp     short loc_1800113C2
0x180011397  mov     ebp, 2
0x18001139c  mov     rbx, r8
0x18001139f  cmp     [rcx+2], bpl
0x1800113a3  jnz     short loc_1800113C2
0x1800113a5  lea     rbx, [r8+4]
0x1800113a9  cmp     rbx, rsi
0x1800113ac  ja      short loc_1800113FC
0x1800113ae  lea     edx, [rbp+2]; DestinationSize
0x1800113b1  mov     [rcx+10h], r8
0x1800113b5  mov     r9d, edx; SourceSize
0x1800113b8  add     rcx, 4; Destination
0x1800113bc  call    cs:__imp_memcpy_s
0x1800113c2  movzx   eax, word ptr [rdi]
0x1800113c5  lea     r14, [rdi+8]
0x1800113c9  mov     [r14], ax
0x1800113cd  test    ax, ax
0x1800113d0  jnz     short loc_1800113F0
0x1800113d2  lea     r15, [rbx+2]
0x1800113d6  cmp     r15, rsi
0x1800113d9  ja      short loc_1800113FC
0x1800113db  mov     r9, rbp; SourceSize
0x1800113de  mov     r8, rbx; Source
0x1800113e1  mov     rdx, rbp; DestinationSize
0x1800113e4  mov     rcx, r14; Destination
0x1800113e7  call    cs:__imp_memcpy_s
0x1800113ed  mov     rbx, r15
0x1800113f0  movzx   ecx, word ptr [r14]
0x1800113f4  add     rcx, rbx
0x1800113f7  cmp     rcx, rsi
0x1800113fa  jbe     short loc_180011400
0x1800113fc  xor     al, al
0x1800113fe  jmp     short loc_18001140A
0x180011400  mov     [rdi+18h], rbx
0x180011404  mov     al, 1
0x180011406  mov     [r12], rcx
0x18001140a  mov     rbx, [rsp+48h+arg_8]
0x18001140f  mov     rbp, [rsp+48h+arg_10]
0x180011414  add     rsp, 20h
0x180011418  pop     r15
0x18001141a  pop     r14
0x18001141c  pop     r12
0x18001141e  pop     rdi
0x18001141f  pop     rsi
0x180011420  retn
```
