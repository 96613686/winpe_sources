# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x14000c530`
- end: `0x14000c619`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `233`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000a728`

## callees

- `0x14000c530`
- `0x14000cad8`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x14000c59f`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x14000c59f`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x14000c593`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x14000c593`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Write(
        wil::details_abi::UsageIndexProperty *this,
        unsigned __int8 **a2,
        unsigned __int8 *a3)
{
  char v3; // al
  _WORD *v4; // r9
  _WORD *v8; // rbx
  _DWORD *v9; // rax
  unsigned __int16 *v10; // rbp
  rsize_t v11; // r9
  bool result; // al

  v3 = *((_BYTE *)this + 2);
  v4 = *a2;
  if ( v3 == 1 )
  {
    v8 = v4 + 1;
    if ( v4 + 1 > (_WORD *)a3 )
      return 0;
    if ( v4 )
    {
      *v4 = *((_WORD *)this + 2);
      goto LABEL_13;
    }
LABEL_11:
    *_errno() = 22;
    _invalid_parameter_noinfo();
    goto LABEL_13;
  }
  if ( v3 == 2 )
  {
    v8 = v4 + 2;
    if ( v4 + 2 > (_WORD *)a3 )
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
    if ( v8 + 1 <= (_WORD *)a3 )
    {
      v10 = (unsigned __int16 *)((char *)this + 8);
      memcpy_s(v8, a3 - (unsigned __int8 *)v8, (char *)this + 8, 2u);
      ++v8;
      goto LABEL_17;
    }
    return 0;
  }
  v10 = (unsigned __int16 *)((char *)this + 8);
LABEL_17:
  v11 = *v10;
  if ( (unsigned __int8 *)((char *)v8 + v11) > a3 )
    return 0;
  memcpy_s(v8, a3 - (unsigned __int8 *)v8, *((const void *const *)this + 3), v11);
  result = 1;
  *a2 = (unsigned __int8 *)v8 + *v10;
  return result;
}

```

## disassembly

```asm
0x14000c530  push    rbx
0x14000c532  push    rbp
0x14000c533  push    rsi
0x14000c534  push    rdi
0x14000c535  push    r14
0x14000c537  push    r15
0x14000c539  sub     rsp, 28h
0x14000c53d  mov     al, [rcx+2]
0x14000c540  xor     ebp, ebp
0x14000c542  mov     r9, [rdx]
0x14000c545  mov     rdi, r8
0x14000c548  mov     r15, rdx
0x14000c54b  mov     rsi, rcx
0x14000c54e  cmp     al, 1
0x14000c550  jnz     short loc_14000C56E
0x14000c552  lea     rbx, [r9+2]
0x14000c556  cmp     rbx, r8
0x14000c559  ja      loc_14000C5EA
0x14000c55f  test    r9, r9
0x14000c562  jz      short loc_14000C593
0x14000c564  movzx   eax, word ptr [rcx+4]
0x14000c568  mov     [r9], ax
0x14000c56c  jmp     short loc_14000C5AA
0x14000c56e  cmp     al, 2
0x14000c570  jnz     short loc_14000C5A7
0x14000c572  lea     rbx, [r9+4]
0x14000c576  cmp     rbx, rdi
0x14000c579  ja      short loc_14000C5EA
0x14000c57b  test    r9, r9
0x14000c57e  jz      short loc_14000C593
0x14000c580  lea     rax, [rcx+4]
0x14000c584  test    rax, rax
0x14000c587  jz      short loc_14000C590
0x14000c589  mov     eax, [rax]
0x14000c58b  mov     [r9], eax
0x14000c58e  jmp     short loc_14000C5AA
0x14000c590  mov     [r9], eax
0x14000c593  call    cs:__imp__errno
0x14000c599  mov     dword ptr [rax], 16h
0x14000c59f  call    cs:__imp__invalid_parameter_noinfo
0x14000c5a5  jmp     short loc_14000C5AA
0x14000c5a7  mov     rbx, r9
0x14000c5aa  cmp     [rsi], bp
0x14000c5ad  jnz     short loc_14000C5D8
0x14000c5af  lea     r14, [rbx+2]
0x14000c5b3  cmp     r14, rdi
0x14000c5b6  ja      short loc_14000C5EA
0x14000c5b8  lea     rbp, [rsi+8]
0x14000c5bc  mov     rdx, rdi
0x14000c5bf  sub     rdx, rbx; DestinationSize
0x14000c5c2  mov     r8, rbp; Source
0x14000c5c5  mov     r9d, 2; SourceSize
0x14000c5cb  mov     rcx, rbx; Destination
0x14000c5ce  call    memcpy_s
0x14000c5d3  mov     rbx, r14
0x14000c5d6  jmp     short loc_14000C5DC
0x14000c5d8  lea     rbp, [rsi+8]
0x14000c5dc  movzx   r9d, word ptr [rbp+0]; SourceSize
0x14000c5e1  lea     rax, [r9+rbx]
0x14000c5e5  cmp     rax, rdi
0x14000c5e8  jbe     short loc_14000C5EE
0x14000c5ea  xor     al, al
0x14000c5ec  jmp     short loc_14000C60C
0x14000c5ee  mov     r8, [rsi+18h]; Source
0x14000c5f2  sub     rdi, rbx
0x14000c5f5  mov     rdx, rdi; DestinationSize
0x14000c5f8  mov     rcx, rbx; Destination
0x14000c5fb  call    memcpy_s
0x14000c600  movzx   ecx, word ptr [rbp+0]
0x14000c604  mov     al, 1
0x14000c606  add     rcx, rbx
0x14000c609  mov     [r15], rcx
0x14000c60c  add     rsp, 28h
0x14000c610  pop     r15
0x14000c612  pop     r14
0x14000c614  pop     rdi
0x14000c615  pop     rsi
0x14000c616  pop     rbp
0x14000c617  pop     rbx
0x14000c618  retn
```
