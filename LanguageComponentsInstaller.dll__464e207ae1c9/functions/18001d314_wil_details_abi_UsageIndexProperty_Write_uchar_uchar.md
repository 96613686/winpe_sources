# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x18001d314`
- end: `0x18001d3fc`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001a200`

## callees

- `0x180004086`
- `0x18000ab68`
- `0x18001d314`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001d377`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001d377`

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
0x18001d314  push    rbx
0x18001d316  push    rbp
0x18001d317  push    rsi
0x18001d318  push    rdi
0x18001d319  push    r14
0x18001d31b  push    r15
0x18001d31d  sub     rsp, 28h
0x18001d321  mov     al, [rcx+2]
0x18001d324  xor     ebp, ebp
0x18001d326  mov     r9, [rdx]
0x18001d329  mov     rdi, r8
0x18001d32c  mov     r15, rdx
0x18001d32f  mov     rsi, rcx
0x18001d332  cmp     al, 1
0x18001d334  jnz     short loc_18001D352
0x18001d336  lea     rbx, [r9+2]
0x18001d33a  cmp     rbx, r8
0x18001d33d  ja      loc_18001D3CD
0x18001d343  test    r9, r9
0x18001d346  jz      short loc_18001D377
0x18001d348  movzx   eax, word ptr [rcx+4]
0x18001d34c  mov     [r9], ax
0x18001d350  jmp     short loc_18001D38D
0x18001d352  cmp     al, 2
0x18001d354  jnz     short loc_18001D38A
0x18001d356  lea     rbx, [r9+4]
0x18001d35a  cmp     rbx, rdi
0x18001d35d  ja      short loc_18001D3CD
0x18001d35f  test    r9, r9
0x18001d362  jz      short loc_18001D377
0x18001d364  lea     rax, [rcx+4]
0x18001d368  test    rax, rax
0x18001d36b  jz      short loc_18001D374
0x18001d36d  mov     eax, [rax]
0x18001d36f  mov     [r9], eax
0x18001d372  jmp     short loc_18001D38D
0x18001d374  mov     [r9], eax
0x18001d377  call    cs:__imp__o__errno
0x18001d37d  mov     dword ptr [rax], 16h
0x18001d383  call    _invalid_parameter_noinfo
0x18001d388  jmp     short loc_18001D38D
0x18001d38a  mov     rbx, r9
0x18001d38d  cmp     [rsi], bp
0x18001d390  jnz     short loc_18001D3BB
0x18001d392  lea     r14, [rbx+2]
0x18001d396  cmp     r14, rdi
0x18001d399  ja      short loc_18001D3CD
0x18001d39b  lea     rbp, [rsi+8]
0x18001d39f  mov     rdx, rdi
0x18001d3a2  sub     rdx, rbx; DestinationSize
0x18001d3a5  mov     r8, rbp; Source
0x18001d3a8  mov     r9d, 2; SourceSize
0x18001d3ae  mov     rcx, rbx; Destination
0x18001d3b1  call    memcpy_s
0x18001d3b6  mov     rbx, r14
0x18001d3b9  jmp     short loc_18001D3BF
0x18001d3bb  lea     rbp, [rsi+8]
0x18001d3bf  movzx   r9d, word ptr [rbp+0]; SourceSize
0x18001d3c4  lea     rax, [r9+rbx]
0x18001d3c8  cmp     rax, rdi
0x18001d3cb  jbe     short loc_18001D3D1
0x18001d3cd  xor     al, al
0x18001d3cf  jmp     short loc_18001D3EF
0x18001d3d1  mov     r8, [rsi+18h]; Source
0x18001d3d5  sub     rdi, rbx
0x18001d3d8  mov     rdx, rdi; DestinationSize
0x18001d3db  mov     rcx, rbx; Destination
0x18001d3de  call    memcpy_s
0x18001d3e3  movzx   ecx, word ptr [rbp+0]
0x18001d3e7  mov     al, 1
0x18001d3e9  add     rcx, rbx
0x18001d3ec  mov     [r15], rcx
0x18001d3ef  add     rsp, 28h
0x18001d3f3  pop     r15
0x18001d3f5  pop     r14
0x18001d3f7  pop     rdi
0x18001d3f8  pop     rsi
0x18001d3f9  pop     rbp
0x18001d3fa  pop     rbx
0x18001d3fb  retn
```
