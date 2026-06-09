# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x18000830c`
- end: `0x1800083f4`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800061c8`

## callees

- `0x18000212a`
- `0x18000830c`
- `0x180008998`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000836f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000836f`

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
0x18000830c  push    rbx
0x18000830e  push    rbp
0x18000830f  push    rsi
0x180008310  push    rdi
0x180008311  push    r14
0x180008313  push    r15
0x180008315  sub     rsp, 28h
0x180008319  mov     al, [rcx+2]
0x18000831c  xor     ebp, ebp
0x18000831e  mov     r9, [rdx]
0x180008321  mov     rdi, r8
0x180008324  mov     r15, rdx
0x180008327  mov     rsi, rcx
0x18000832a  cmp     al, 1
0x18000832c  jnz     short loc_18000834A
0x18000832e  lea     rbx, [r9+2]
0x180008332  cmp     rbx, r8
0x180008335  ja      loc_1800083C5
0x18000833b  test    r9, r9
0x18000833e  jz      short loc_18000836F
0x180008340  movzx   eax, word ptr [rcx+4]
0x180008344  mov     [r9], ax
0x180008348  jmp     short loc_180008385
0x18000834a  cmp     al, 2
0x18000834c  jnz     short loc_180008382
0x18000834e  lea     rbx, [r9+4]
0x180008352  cmp     rbx, rdi
0x180008355  ja      short loc_1800083C5
0x180008357  test    r9, r9
0x18000835a  jz      short loc_18000836F
0x18000835c  lea     rax, [rcx+4]
0x180008360  test    rax, rax
0x180008363  jz      short loc_18000836C
0x180008365  mov     eax, [rax]
0x180008367  mov     [r9], eax
0x18000836a  jmp     short loc_180008385
0x18000836c  mov     [r9], eax
0x18000836f  call    cs:__imp__o__errno
0x180008375  mov     dword ptr [rax], 16h
0x18000837b  call    _invalid_parameter_noinfo
0x180008380  jmp     short loc_180008385
0x180008382  mov     rbx, r9
0x180008385  cmp     [rsi], bp
0x180008388  jnz     short loc_1800083B3
0x18000838a  lea     r14, [rbx+2]
0x18000838e  cmp     r14, rdi
0x180008391  ja      short loc_1800083C5
0x180008393  lea     rbp, [rsi+8]
0x180008397  mov     rdx, rdi
0x18000839a  sub     rdx, rbx; DestinationSize
0x18000839d  mov     r8, rbp; Source
0x1800083a0  mov     r9d, 2; SourceSize
0x1800083a6  mov     rcx, rbx; Destination
0x1800083a9  call    memcpy_s
0x1800083ae  mov     rbx, r14
0x1800083b1  jmp     short loc_1800083B7
0x1800083b3  lea     rbp, [rsi+8]
0x1800083b7  movzx   r9d, word ptr [rbp+0]; SourceSize
0x1800083bc  lea     rax, [r9+rbx]
0x1800083c0  cmp     rax, rdi
0x1800083c3  jbe     short loc_1800083C9
0x1800083c5  xor     al, al
0x1800083c7  jmp     short loc_1800083E7
0x1800083c9  mov     r8, [rsi+18h]; Source
0x1800083cd  sub     rdi, rbx
0x1800083d0  mov     rdx, rdi; DestinationSize
0x1800083d3  mov     rcx, rbx; Destination
0x1800083d6  call    memcpy_s
0x1800083db  movzx   ecx, word ptr [rbp+0]
0x1800083df  mov     al, 1
0x1800083e1  add     rcx, rbx
0x1800083e4  mov     [r15], rcx
0x1800083e7  add     rsp, 28h
0x1800083eb  pop     r15
0x1800083ed  pop     r14
0x1800083ef  pop     rdi
0x1800083f0  pop     rsi
0x1800083f1  pop     rbp
0x1800083f2  pop     rbx
0x1800083f3  retn
```
