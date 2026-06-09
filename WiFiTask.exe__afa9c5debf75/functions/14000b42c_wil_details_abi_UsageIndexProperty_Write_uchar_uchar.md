# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x14000b42c`
- end: `0x14000b514`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140008a78`

## callees

- `0x1400020b2`
- `0x14000b42c`
- `0x14000c1a4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000b48f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000b48f`

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
0x14000b42c  push    rbx
0x14000b42e  push    rbp
0x14000b42f  push    rsi
0x14000b430  push    rdi
0x14000b431  push    r14
0x14000b433  push    r15
0x14000b435  sub     rsp, 28h
0x14000b439  mov     al, [rcx+2]
0x14000b43c  xor     ebp, ebp
0x14000b43e  mov     r9, [rdx]
0x14000b441  mov     rdi, r8
0x14000b444  mov     r15, rdx
0x14000b447  mov     rsi, rcx
0x14000b44a  cmp     al, 1
0x14000b44c  jnz     short loc_14000B46A
0x14000b44e  lea     rbx, [r9+2]
0x14000b452  cmp     rbx, r8
0x14000b455  ja      loc_14000B4E5
0x14000b45b  test    r9, r9
0x14000b45e  jz      short loc_14000B48F
0x14000b460  movzx   eax, word ptr [rcx+4]
0x14000b464  mov     [r9], ax
0x14000b468  jmp     short loc_14000B4A5
0x14000b46a  cmp     al, 2
0x14000b46c  jnz     short loc_14000B4A2
0x14000b46e  lea     rbx, [r9+4]
0x14000b472  cmp     rbx, rdi
0x14000b475  ja      short loc_14000B4E5
0x14000b477  test    r9, r9
0x14000b47a  jz      short loc_14000B48F
0x14000b47c  lea     rax, [rcx+4]
0x14000b480  test    rax, rax
0x14000b483  jz      short loc_14000B48C
0x14000b485  mov     eax, [rax]
0x14000b487  mov     [r9], eax
0x14000b48a  jmp     short loc_14000B4A5
0x14000b48c  mov     [r9], eax
0x14000b48f  call    cs:__imp__o__errno
0x14000b495  mov     dword ptr [rax], 16h
0x14000b49b  call    _invalid_parameter_noinfo
0x14000b4a0  jmp     short loc_14000B4A5
0x14000b4a2  mov     rbx, r9
0x14000b4a5  cmp     [rsi], bp
0x14000b4a8  jnz     short loc_14000B4D3
0x14000b4aa  lea     r14, [rbx+2]
0x14000b4ae  cmp     r14, rdi
0x14000b4b1  ja      short loc_14000B4E5
0x14000b4b3  lea     rbp, [rsi+8]
0x14000b4b7  mov     rdx, rdi
0x14000b4ba  sub     rdx, rbx; DestinationSize
0x14000b4bd  mov     r8, rbp; Source
0x14000b4c0  mov     r9d, 2; SourceSize
0x14000b4c6  mov     rcx, rbx; Destination
0x14000b4c9  call    memcpy_s
0x14000b4ce  mov     rbx, r14
0x14000b4d1  jmp     short loc_14000B4D7
0x14000b4d3  lea     rbp, [rsi+8]
0x14000b4d7  movzx   r9d, word ptr [rbp+0]; SourceSize
0x14000b4dc  lea     rax, [r9+rbx]
0x14000b4e0  cmp     rax, rdi
0x14000b4e3  jbe     short loc_14000B4E9
0x14000b4e5  xor     al, al
0x14000b4e7  jmp     short loc_14000B507
0x14000b4e9  mov     r8, [rsi+18h]; Source
0x14000b4ed  sub     rdi, rbx
0x14000b4f0  mov     rdx, rdi; DestinationSize
0x14000b4f3  mov     rcx, rbx; Destination
0x14000b4f6  call    memcpy_s
0x14000b4fb  movzx   ecx, word ptr [rbp+0]
0x14000b4ff  mov     al, 1
0x14000b501  add     rcx, rbx
0x14000b504  mov     [r15], rcx
0x14000b507  add     rsp, 28h
0x14000b50b  pop     r15
0x14000b50d  pop     r14
0x14000b50f  pop     rdi
0x14000b510  pop     rsi
0x14000b511  pop     rbp
0x14000b512  pop     rbx
0x14000b513  retn
```
