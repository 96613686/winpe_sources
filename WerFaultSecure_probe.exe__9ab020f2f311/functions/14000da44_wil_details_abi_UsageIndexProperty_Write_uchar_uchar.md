# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x14000da44`
- end: `0x14000db2c`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000b430`

## callees

- `0x140002f1a`
- `0x140004978`
- `0x14000da44`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000daa7`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000daa7`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Write(
        wil::details_abi::UsageIndexProperty *this,
        unsigned __int8 **a2,
        unsigned __int8 *a3)
{
  char v3; // al
  unsigned __int8 *v4; // r9
  unsigned __int8 *v8; // rbx
  _DWORD *v9; // rax
  unsigned __int16 *v10; // rbp
  rsize_t v11; // r9
  bool result; // al

  v3 = *((_BYTE *)this + 2);
  v4 = *a2;
  if ( v3 == 1 )
  {
    v8 = v4 + 2;
    if ( v4 + 2 > a3 )
      return 0;
    if ( v4 )
    {
      *(_WORD *)v4 = *((_WORD *)this + 2);
      goto LABEL_13;
    }
LABEL_11:
    *(_DWORD *)_o__errno(this, a2, a3) = 22;
    invalid_parameter_noinfo();
    goto LABEL_13;
  }
  if ( v3 == 2 )
  {
    v8 = v4 + 4;
    if ( v4 + 4 > a3 )
      return 0;
    if ( v4 )
    {
      v9 = (_DWORD *)((char *)this + 4);
      if ( this != (wil::details_abi::UsageIndexProperty *)-4LL )
      {
        *(_DWORD *)v4 = *v9;
        goto LABEL_13;
      }
      *(_DWORD *)v4 = (_DWORD)v9;
    }
    goto LABEL_11;
  }
  v8 = *a2;
LABEL_13:
  if ( !*(_WORD *)this )
  {
    if ( v8 + 2 <= a3 )
    {
      v10 = (unsigned __int16 *)((char *)this + 8);
      memcpy_s(v8, a3 - v8, (char *)this + 8, 2u);
      v8 += 2;
      goto LABEL_17;
    }
    return 0;
  }
  v10 = (unsigned __int16 *)((char *)this + 8);
LABEL_17:
  v11 = *v10;
  if ( &v8[v11] > a3 )
    return 0;
  memcpy_s(v8, a3 - v8, *((const void *const *)this + 3), v11);
  result = 1;
  *a2 = &v8[*v10];
  return result;
}

```

## disassembly

```asm
0x14000da44  push    rbx
0x14000da46  push    rbp
0x14000da47  push    rsi
0x14000da48  push    rdi
0x14000da49  push    r14
0x14000da4b  push    r15
0x14000da4d  sub     rsp, 28h
0x14000da51  mov     al, [rcx+2]
0x14000da54  xor     ebp, ebp
0x14000da56  mov     r9, [rdx]
0x14000da59  mov     rdi, r8
0x14000da5c  mov     r15, rdx
0x14000da5f  mov     rsi, rcx
0x14000da62  cmp     al, 1
0x14000da64  jnz     short loc_14000DA82
0x14000da66  lea     rbx, [r9+2]
0x14000da6a  cmp     rbx, r8
0x14000da6d  ja      loc_14000DAFD
0x14000da73  test    r9, r9
0x14000da76  jz      short loc_14000DAA7
0x14000da78  movzx   eax, word ptr [rcx+4]
0x14000da7c  mov     [r9], ax
0x14000da80  jmp     short loc_14000DABD
0x14000da82  cmp     al, 2
0x14000da84  jnz     short loc_14000DABA
0x14000da86  lea     rbx, [r9+4]
0x14000da8a  cmp     rbx, rdi
0x14000da8d  ja      short loc_14000DAFD
0x14000da8f  test    r9, r9
0x14000da92  jz      short loc_14000DAA7
0x14000da94  lea     rax, [rcx+4]
0x14000da98  test    rax, rax
0x14000da9b  jz      short loc_14000DAA4
0x14000da9d  mov     eax, [rax]
0x14000da9f  mov     [r9], eax
0x14000daa2  jmp     short loc_14000DABD
0x14000daa4  mov     [r9], eax
0x14000daa7  call    cs:__imp__o__errno
0x14000daad  mov     dword ptr [rax], 16h
0x14000dab3  call    _invalid_parameter_noinfo
0x14000dab8  jmp     short loc_14000DABD
0x14000daba  mov     rbx, r9
0x14000dabd  cmp     [rsi], bp
0x14000dac0  jnz     short loc_14000DAEB
0x14000dac2  lea     r14, [rbx+2]
0x14000dac6  cmp     r14, rdi
0x14000dac9  ja      short loc_14000DAFD
0x14000dacb  lea     rbp, [rsi+8]
0x14000dacf  mov     rdx, rdi
0x14000dad2  sub     rdx, rbx; DestinationSize
0x14000dad5  mov     r8, rbp; Source
0x14000dad8  mov     r9d, 2; SourceSize
0x14000dade  mov     rcx, rbx; Destination
0x14000dae1  call    memcpy_s
0x14000dae6  mov     rbx, r14
0x14000dae9  jmp     short loc_14000DAEF
0x14000daeb  lea     rbp, [rsi+8]
0x14000daef  movzx   r9d, word ptr [rbp+0]; SourceSize
0x14000daf4  lea     rax, [r9+rbx]
0x14000daf8  cmp     rax, rdi
0x14000dafb  jbe     short loc_14000DB01
0x14000dafd  xor     al, al
0x14000daff  jmp     short loc_14000DB1F
0x14000db01  mov     r8, [rsi+18h]; Source
0x14000db05  sub     rdi, rbx
0x14000db08  mov     rdx, rdi; DestinationSize
0x14000db0b  mov     rcx, rbx; Destination
0x14000db0e  call    memcpy_s
0x14000db13  movzx   ecx, word ptr [rbp+0]
0x14000db17  mov     al, 1
0x14000db19  add     rcx, rbx
0x14000db1c  mov     [r15], rcx
0x14000db1f  add     rsp, 28h
0x14000db23  pop     r15
0x14000db25  pop     r14
0x14000db27  pop     rdi
0x14000db28  pop     rsi
0x14000db29  pop     rbp
0x14000db2a  pop     rbx
0x14000db2b  retn
```
