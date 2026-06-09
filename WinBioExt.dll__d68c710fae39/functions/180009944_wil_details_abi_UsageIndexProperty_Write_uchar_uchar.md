# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x180009944`
- end: `0x180009a2c`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000890c`

## callees

- `0x18000201a`
- `0x180005d78`
- `0x180009944`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800099a7`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800099a7`

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
0x180009944  push    rbx
0x180009946  push    rbp
0x180009947  push    rsi
0x180009948  push    rdi
0x180009949  push    r14
0x18000994b  push    r15
0x18000994d  sub     rsp, 28h
0x180009951  mov     al, [rcx+2]
0x180009954  xor     ebp, ebp
0x180009956  mov     r9, [rdx]
0x180009959  mov     rdi, r8
0x18000995c  mov     r15, rdx
0x18000995f  mov     rsi, rcx
0x180009962  cmp     al, 1
0x180009964  jnz     short loc_180009982
0x180009966  lea     rbx, [r9+2]
0x18000996a  cmp     rbx, r8
0x18000996d  ja      loc_1800099FD
0x180009973  test    r9, r9
0x180009976  jz      short loc_1800099A7
0x180009978  movzx   eax, word ptr [rcx+4]
0x18000997c  mov     [r9], ax
0x180009980  jmp     short loc_1800099BD
0x180009982  cmp     al, 2
0x180009984  jnz     short loc_1800099BA
0x180009986  lea     rbx, [r9+4]
0x18000998a  cmp     rbx, rdi
0x18000998d  ja      short loc_1800099FD
0x18000998f  test    r9, r9
0x180009992  jz      short loc_1800099A7
0x180009994  lea     rax, [rcx+4]
0x180009998  test    rax, rax
0x18000999b  jz      short loc_1800099A4
0x18000999d  mov     eax, [rax]
0x18000999f  mov     [r9], eax
0x1800099a2  jmp     short loc_1800099BD
0x1800099a4  mov     [r9], eax
0x1800099a7  call    cs:__imp__o__errno
0x1800099ad  mov     dword ptr [rax], 16h
0x1800099b3  call    _invalid_parameter_noinfo
0x1800099b8  jmp     short loc_1800099BD
0x1800099ba  mov     rbx, r9
0x1800099bd  cmp     [rsi], bp
0x1800099c0  jnz     short loc_1800099EB
0x1800099c2  lea     r14, [rbx+2]
0x1800099c6  cmp     r14, rdi
0x1800099c9  ja      short loc_1800099FD
0x1800099cb  lea     rbp, [rsi+8]
0x1800099cf  mov     rdx, rdi
0x1800099d2  sub     rdx, rbx; DestinationSize
0x1800099d5  mov     r8, rbp; Source
0x1800099d8  mov     r9d, 2; SourceSize
0x1800099de  mov     rcx, rbx; Destination
0x1800099e1  call    memcpy_s
0x1800099e6  mov     rbx, r14
0x1800099e9  jmp     short loc_1800099EF
0x1800099eb  lea     rbp, [rsi+8]
0x1800099ef  movzx   r9d, word ptr [rbp+0]; SourceSize
0x1800099f4  lea     rax, [r9+rbx]
0x1800099f8  cmp     rax, rdi
0x1800099fb  jbe     short loc_180009A01
0x1800099fd  xor     al, al
0x1800099ff  jmp     short loc_180009A1F
0x180009a01  mov     r8, [rsi+18h]; Source
0x180009a05  sub     rdi, rbx
0x180009a08  mov     rdx, rdi; DestinationSize
0x180009a0b  mov     rcx, rbx; Destination
0x180009a0e  call    memcpy_s
0x180009a13  movzx   ecx, word ptr [rbp+0]
0x180009a17  mov     al, 1
0x180009a19  add     rcx, rbx
0x180009a1c  mov     [r15], rcx
0x180009a1f  add     rsp, 28h
0x180009a23  pop     r15
0x180009a25  pop     r14
0x180009a27  pop     rdi
0x180009a28  pop     rsi
0x180009a29  pop     rbp
0x180009a2a  pop     rbx
0x180009a2b  retn
```
