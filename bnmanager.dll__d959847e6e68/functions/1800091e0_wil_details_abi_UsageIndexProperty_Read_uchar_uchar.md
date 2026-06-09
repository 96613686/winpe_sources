# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x1800091e0`
- end: `0x1800092d8`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `248`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000787c`
- `0x180009828`
- `0x180009bfc`

## callees

- `0x18000221a`
- `0x1800091e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000921d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000925f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000929e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000921d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000925f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000929e`

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
0x1800091e0  push    rbx
0x1800091e2  push    rbp
0x1800091e3  push    rsi
0x1800091e4  push    rdi
0x1800091e5  push    r14
0x1800091e7  push    r15
0x1800091e9  sub     rsp, 28h
0x1800091ed  mov     rax, [rdx]
0x1800091f0  xor     r15d, r15d
0x1800091f3  cmp     byte ptr [rcx+2], 1
0x1800091f7  mov     rbp, r8
0x1800091fa  mov     r14, rdx
0x1800091fd  mov     rdi, rcx
0x180009200  jnz     short loc_180009239
0x180009202  lea     rbx, [rax+2]
0x180009206  cmp     rbx, r8
0x180009209  ja      loc_1800092BE
0x18000920f  mov     [rcx+10h], rax
0x180009213  test    rax, rax
0x180009216  jz      short loc_18000921D
0x180009218  movzx   ecx, word ptr [rax]
0x18000921b  jmp     short loc_180009231
0x18000921d  call    cs:__imp__o__errno
0x180009223  mov     dword ptr [rax], 16h
0x180009229  call    _invalid_parameter_noinfo
0x18000922e  mov     ecx, r15d
0x180009231  movzx   eax, cx
0x180009234  mov     [rdi+4], eax
0x180009237  jmp     short loc_180009275
0x180009239  cmp     byte ptr [rcx+2], 2
0x18000923d  jnz     short loc_180009272
0x18000923f  lea     rbx, [rax+4]
0x180009243  cmp     rbx, rbp
0x180009246  ja      short loc_1800092BE
0x180009248  mov     [rcx+10h], rax
0x18000924c  add     rcx, 4
0x180009250  jz      short loc_18000925F
0x180009252  test    rax, rax
0x180009255  jz      short loc_18000925D
0x180009257  mov     eax, [rax]
0x180009259  mov     [rcx], eax
0x18000925b  jmp     short loc_180009275
0x18000925d  mov     [rcx], eax
0x18000925f  call    cs:__imp__o__errno
0x180009265  mov     dword ptr [rax], 16h
0x18000926b  call    _invalid_parameter_noinfo
0x180009270  jmp     short loc_180009275
0x180009272  mov     rbx, rax
0x180009275  movzx   eax, word ptr [rdi]
0x180009278  mov     [rdi+8], ax
0x18000927c  test    ax, ax
0x18000927f  jnz     short loc_1800092B2
0x180009281  lea     rsi, [rbx+2]
0x180009285  cmp     rsi, rbp
0x180009288  ja      short loc_1800092BE
0x18000928a  test    rbx, rbx
0x18000928d  jz      short loc_180009298
0x18000928f  movzx   eax, word ptr [rbx]
0x180009292  mov     [rdi+8], ax
0x180009296  jmp     short loc_1800092AF
0x180009298  xor     eax, eax
0x18000929a  mov     [rdi+8], ax
0x18000929e  call    cs:__imp__o__errno
0x1800092a4  mov     dword ptr [rax], 16h
0x1800092aa  call    _invalid_parameter_noinfo
0x1800092af  mov     rbx, rsi
0x1800092b2  movzx   ecx, word ptr [rdi+8]
0x1800092b6  add     rcx, rbx
0x1800092b9  cmp     rcx, rbp
0x1800092bc  jbe     short loc_1800092C2
0x1800092be  xor     al, al
0x1800092c0  jmp     short loc_1800092CB
0x1800092c2  mov     [rdi+18h], rbx
0x1800092c6  mov     al, 1
0x1800092c8  mov     [r14], rcx
0x1800092cb  add     rsp, 28h
0x1800092cf  pop     r15
0x1800092d1  pop     r14
0x1800092d3  pop     rdi
0x1800092d4  pop     rsi
0x1800092d5  pop     rbp
0x1800092d6  pop     rbx
0x1800092d7  retn
```
