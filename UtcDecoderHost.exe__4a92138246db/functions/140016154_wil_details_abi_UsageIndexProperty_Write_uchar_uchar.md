# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x140016154`
- end: `0x14001623c`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140014e5c`

## callees

- `0x14000903a`
- `0x14000d608`
- `0x140016154`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400161b7`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400161b7`

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
0x140016154  push    rbx
0x140016156  push    rbp
0x140016157  push    rsi
0x140016158  push    rdi
0x140016159  push    r14
0x14001615b  push    r15
0x14001615d  sub     rsp, 28h
0x140016161  mov     al, [rcx+2]
0x140016164  xor     ebp, ebp
0x140016166  mov     r9, [rdx]
0x140016169  mov     rdi, r8
0x14001616c  mov     r15, rdx
0x14001616f  mov     rsi, rcx
0x140016172  cmp     al, 1
0x140016174  jnz     short loc_140016192
0x140016176  lea     rbx, [r9+2]
0x14001617a  cmp     rbx, r8
0x14001617d  ja      loc_14001620D
0x140016183  test    r9, r9
0x140016186  jz      short loc_1400161B7
0x140016188  movzx   eax, word ptr [rcx+4]
0x14001618c  mov     [r9], ax
0x140016190  jmp     short loc_1400161CD
0x140016192  cmp     al, 2
0x140016194  jnz     short loc_1400161CA
0x140016196  lea     rbx, [r9+4]
0x14001619a  cmp     rbx, rdi
0x14001619d  ja      short loc_14001620D
0x14001619f  test    r9, r9
0x1400161a2  jz      short loc_1400161B7
0x1400161a4  lea     rax, [rcx+4]
0x1400161a8  test    rax, rax
0x1400161ab  jz      short loc_1400161B4
0x1400161ad  mov     eax, [rax]
0x1400161af  mov     [r9], eax
0x1400161b2  jmp     short loc_1400161CD
0x1400161b4  mov     [r9], eax
0x1400161b7  call    cs:__imp__o__errno
0x1400161bd  mov     dword ptr [rax], 16h
0x1400161c3  call    _invalid_parameter_noinfo
0x1400161c8  jmp     short loc_1400161CD
0x1400161ca  mov     rbx, r9
0x1400161cd  cmp     [rsi], bp
0x1400161d0  jnz     short loc_1400161FB
0x1400161d2  lea     r14, [rbx+2]
0x1400161d6  cmp     r14, rdi
0x1400161d9  ja      short loc_14001620D
0x1400161db  lea     rbp, [rsi+8]
0x1400161df  mov     rdx, rdi
0x1400161e2  sub     rdx, rbx; DestinationSize
0x1400161e5  mov     r8, rbp; Source
0x1400161e8  mov     r9d, 2; SourceSize
0x1400161ee  mov     rcx, rbx; Destination
0x1400161f1  call    memcpy_s
0x1400161f6  mov     rbx, r14
0x1400161f9  jmp     short loc_1400161FF
0x1400161fb  lea     rbp, [rsi+8]
0x1400161ff  movzx   r9d, word ptr [rbp+0]; SourceSize
0x140016204  lea     rax, [r9+rbx]
0x140016208  cmp     rax, rdi
0x14001620b  jbe     short loc_140016211
0x14001620d  xor     al, al
0x14001620f  jmp     short loc_14001622F
0x140016211  mov     r8, [rsi+18h]; Source
0x140016215  sub     rdi, rbx
0x140016218  mov     rdx, rdi; DestinationSize
0x14001621b  mov     rcx, rbx; Destination
0x14001621e  call    memcpy_s
0x140016223  movzx   ecx, word ptr [rbp+0]
0x140016227  mov     al, 1
0x140016229  add     rcx, rbx
0x14001622c  mov     [r15], rcx
0x14001622f  add     rsp, 28h
0x140016233  pop     r15
0x140016235  pop     r14
0x140016237  pop     rdi
0x140016238  pop     rsi
0x140016239  pop     rbp
0x14001623a  pop     rbx
0x14001623b  retn
```
