# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180008328`
- end: `0x180008420`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `248`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180007d90`
- `0x18000890c`
- `0x180008ce0`

## callees

- `0x18000201a`
- `0x180008328`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008365`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800083a7`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800083e6`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008365`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800083a7`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800083e6`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Read(
        wil::details_abi::UsageIndexProperty *this,
        unsigned __int8 **a2,
        unsigned __int8 *a3)
{
  unsigned __int8 *v3; // rax
  wil::details_abi::UsageIndexProperty *v6; // rdi
  unsigned __int8 *v7; // rbx
  __int16 v8; // ax
  unsigned __int8 *v9; // rcx
  bool result; // al

  v3 = *a2;
  v6 = this;
  if ( *((_BYTE *)this + 2) == 1 )
  {
    v7 = v3 + 2;
    if ( v3 + 2 > a3 )
      return 0;
    *((_QWORD *)this + 2) = v3;
    if ( v3 )
    {
      this = (wil::details_abi::UsageIndexProperty *)*(unsigned __int16 *)v3;
    }
    else
    {
      *(_DWORD *)_o__errno(this, a2, a3) = 22;
      invalid_parameter_noinfo();
      this = 0;
    }
    *((_DWORD *)v6 + 1) = (unsigned __int16)this;
  }
  else if ( *((_BYTE *)this + 2) == 2 )
  {
    v7 = v3 + 4;
    if ( v3 + 4 > a3 )
      return 0;
    *((_QWORD *)this + 2) = v3;
    this = (wil::details_abi::UsageIndexProperty *)((char *)this + 4);
    if ( this )
    {
      if ( v3 )
      {
        *(_DWORD *)this = *(_DWORD *)v3;
        goto LABEL_15;
      }
      *(_DWORD *)this = 0;
    }
    *(_DWORD *)_o__errno(this, a2, a3) = 22;
    invalid_parameter_noinfo();
  }
  else
  {
    v7 = *a2;
  }
LABEL_15:
  v8 = *(_WORD *)v6;
  *((_WORD *)v6 + 4) = *(_WORD *)v6;
  if ( v8 )
    goto LABEL_21;
  if ( v7 + 2 > a3 )
    return 0;
  if ( v7 )
  {
    *((_WORD *)v6 + 4) = *(_WORD *)v7;
  }
  else
  {
    *((_WORD *)v6 + 4) = 0;
    *(_DWORD *)_o__errno(this, a2, a3) = 22;
    invalid_parameter_noinfo();
  }
  v7 += 2;
LABEL_21:
  v9 = &v7[*((unsigned __int16 *)v6 + 4)];
  if ( v9 > a3 )
    return 0;
  *((_QWORD *)v6 + 3) = v7;
  result = 1;
  *a2 = v9;
  return result;
}

```

## disassembly

```asm
0x180008328  push    rbx
0x18000832a  push    rbp
0x18000832b  push    rsi
0x18000832c  push    rdi
0x18000832d  push    r14
0x18000832f  push    r15
0x180008331  sub     rsp, 28h
0x180008335  mov     rax, [rdx]
0x180008338  xor     r15d, r15d
0x18000833b  cmp     byte ptr [rcx+2], 1
0x18000833f  mov     rbp, r8
0x180008342  mov     r14, rdx
0x180008345  mov     rdi, rcx
0x180008348  jnz     short loc_180008381
0x18000834a  lea     rbx, [rax+2]
0x18000834e  cmp     rbx, r8
0x180008351  ja      loc_180008406
0x180008357  mov     [rcx+10h], rax
0x18000835b  test    rax, rax
0x18000835e  jz      short loc_180008365
0x180008360  movzx   ecx, word ptr [rax]
0x180008363  jmp     short loc_180008379
0x180008365  call    cs:__imp__o__errno
0x18000836b  mov     dword ptr [rax], 16h
0x180008371  call    _invalid_parameter_noinfo
0x180008376  mov     ecx, r15d
0x180008379  movzx   eax, cx
0x18000837c  mov     [rdi+4], eax
0x18000837f  jmp     short loc_1800083BD
0x180008381  cmp     byte ptr [rcx+2], 2
0x180008385  jnz     short loc_1800083BA
0x180008387  lea     rbx, [rax+4]
0x18000838b  cmp     rbx, rbp
0x18000838e  ja      short loc_180008406
0x180008390  mov     [rcx+10h], rax
0x180008394  add     rcx, 4
0x180008398  jz      short loc_1800083A7
0x18000839a  test    rax, rax
0x18000839d  jz      short loc_1800083A5
0x18000839f  mov     eax, [rax]
0x1800083a1  mov     [rcx], eax
0x1800083a3  jmp     short loc_1800083BD
0x1800083a5  mov     [rcx], eax
0x1800083a7  call    cs:__imp__o__errno
0x1800083ad  mov     dword ptr [rax], 16h
0x1800083b3  call    _invalid_parameter_noinfo
0x1800083b8  jmp     short loc_1800083BD
0x1800083ba  mov     rbx, rax
0x1800083bd  movzx   eax, word ptr [rdi]
0x1800083c0  mov     [rdi+8], ax
0x1800083c4  test    ax, ax
0x1800083c7  jnz     short loc_1800083FA
0x1800083c9  lea     rsi, [rbx+2]
0x1800083cd  cmp     rsi, rbp
0x1800083d0  ja      short loc_180008406
0x1800083d2  test    rbx, rbx
0x1800083d5  jz      short loc_1800083E0
0x1800083d7  movzx   eax, word ptr [rbx]
0x1800083da  mov     [rdi+8], ax
0x1800083de  jmp     short loc_1800083F7
0x1800083e0  xor     eax, eax
0x1800083e2  mov     [rdi+8], ax
0x1800083e6  call    cs:__imp__o__errno
0x1800083ec  mov     dword ptr [rax], 16h
0x1800083f2  call    _invalid_parameter_noinfo
0x1800083f7  mov     rbx, rsi
0x1800083fa  movzx   ecx, word ptr [rdi+8]
0x1800083fe  add     rcx, rbx
0x180008401  cmp     rcx, rbp
0x180008404  jbe     short loc_18000840A
0x180008406  xor     al, al
0x180008408  jmp     short loc_180008413
0x18000840a  mov     [rdi+18h], rbx
0x18000840e  mov     al, 1
0x180008410  mov     [r14], rcx
0x180008413  add     rsp, 28h
0x180008417  pop     r15
0x180008419  pop     r14
0x18000841b  pop     rdi
0x18000841c  pop     rsi
0x18000841d  pop     rbp
0x18000841e  pop     rbx
0x18000841f  retn
```
