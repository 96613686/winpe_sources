# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x18001419c`
- end: `0x180014285`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18001203c`
- `0x180014964`
- `0x180014cec`

## callees

- `0x18001419c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800141eb`
- `msvcrt!memcpy_s` at `0x180014220`
- `msvcrt!memcpy_s` at `0x18001424b`
- `msvcrt!memcpy_s` at `0x1800141eb`
- `msvcrt!memcpy_s` at `0x180014220`
- `msvcrt!memcpy_s` at `0x18001424b`

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
0x18001419c  mov     rax, rsp
0x18001419f  mov     [rax+10h], rbx
0x1800141a3  mov     [rax+18h], rbp
0x1800141a7  push    rsi
0x1800141a8  push    rdi
0x1800141a9  push    r12
0x1800141ab  push    r14
0x1800141ad  push    r15
0x1800141af  sub     rsp, 20h
0x1800141b3  xor     r15d, r15d
0x1800141b6  mov     rsi, r8
0x1800141b9  cmp     byte ptr [rcx+2], 1
0x1800141bd  mov     r12, rdx
0x1800141c0  mov     r8, [rdx]; Source
0x1800141c3  mov     rdi, rcx
0x1800141c6  jnz     short loc_1800141FB
0x1800141c8  lea     rbx, [r8+2]
0x1800141cc  cmp     rbx, rsi
0x1800141cf  ja      loc_180014260
0x1800141d5  lea     ebp, [r15+2]
0x1800141d9  mov     [rcx+10h], r8
0x1800141dd  mov     r9d, ebp; SourceSize
0x1800141e0  mov     [rax+8], r15w
0x1800141e5  mov     edx, ebp; DestinationSize
0x1800141e7  lea     rcx, [rax+8]; Destination
0x1800141eb  call    cs:__imp_memcpy_s
0x1800141f1  movzx   eax, [rsp+48h+arg_0]
0x1800141f6  mov     [rdi+4], eax
0x1800141f9  jmp     short loc_180014226
0x1800141fb  mov     ebp, 2
0x180014200  mov     rbx, r8
0x180014203  cmp     [rcx+2], bpl
0x180014207  jnz     short loc_180014226
0x180014209  lea     rbx, [r8+4]
0x18001420d  cmp     rbx, rsi
0x180014210  ja      short loc_180014260
0x180014212  lea     edx, [rbp+2]; DestinationSize
0x180014215  mov     [rcx+10h], r8
0x180014219  mov     r9d, edx; SourceSize
0x18001421c  add     rcx, 4; Destination
0x180014220  call    cs:__imp_memcpy_s
0x180014226  movzx   eax, word ptr [rdi]
0x180014229  lea     r14, [rdi+8]
0x18001422d  mov     [r14], ax
0x180014231  test    ax, ax
0x180014234  jnz     short loc_180014254
0x180014236  lea     r15, [rbx+2]
0x18001423a  cmp     r15, rsi
0x18001423d  ja      short loc_180014260
0x18001423f  mov     r9, rbp; SourceSize
0x180014242  mov     r8, rbx; Source
0x180014245  mov     rdx, rbp; DestinationSize
0x180014248  mov     rcx, r14; Destination
0x18001424b  call    cs:__imp_memcpy_s
0x180014251  mov     rbx, r15
0x180014254  movzx   ecx, word ptr [r14]
0x180014258  add     rcx, rbx
0x18001425b  cmp     rcx, rsi
0x18001425e  jbe     short loc_180014264
0x180014260  xor     al, al
0x180014262  jmp     short loc_18001426E
0x180014264  mov     [rdi+18h], rbx
0x180014268  mov     al, 1
0x18001426a  mov     [r12], rcx
0x18001426e  mov     rbx, [rsp+48h+arg_8]
0x180014273  mov     rbp, [rsp+48h+arg_10]
0x180014278  add     rsp, 20h
0x18001427c  pop     r15
0x18001427e  pop     r14
0x180014280  pop     r12
0x180014282  pop     rdi
0x180014283  pop     rsi
0x180014284  retn
```
