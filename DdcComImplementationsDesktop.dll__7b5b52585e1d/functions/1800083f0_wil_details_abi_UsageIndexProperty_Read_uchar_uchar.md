# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x1800083f0`
- end: `0x1800084e8`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `248`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180006cbc`
- `0x180008a38`
- `0x180008e0c`

## callees

- `0x1800020d0`
- `0x1800083f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000842d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000846f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800084ae`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000842d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000846f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800084ae`

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
0x1800083f0  push    rbx
0x1800083f2  push    rbp
0x1800083f3  push    rsi
0x1800083f4  push    rdi
0x1800083f5  push    r14
0x1800083f7  push    r15
0x1800083f9  sub     rsp, 28h
0x1800083fd  mov     rax, [rdx]
0x180008400  xor     r15d, r15d
0x180008403  cmp     byte ptr [rcx+2], 1
0x180008407  mov     rbp, r8
0x18000840a  mov     r14, rdx
0x18000840d  mov     rdi, rcx
0x180008410  jnz     short loc_180008449
0x180008412  lea     rbx, [rax+2]
0x180008416  cmp     rbx, r8
0x180008419  ja      loc_1800084CE
0x18000841f  mov     [rcx+10h], rax
0x180008423  test    rax, rax
0x180008426  jz      short loc_18000842D
0x180008428  movzx   ecx, word ptr [rax]
0x18000842b  jmp     short loc_180008441
0x18000842d  call    cs:__imp__o__errno
0x180008433  mov     dword ptr [rax], 16h
0x180008439  call    _invalid_parameter_noinfo
0x18000843e  mov     ecx, r15d
0x180008441  movzx   eax, cx
0x180008444  mov     [rdi+4], eax
0x180008447  jmp     short loc_180008485
0x180008449  cmp     byte ptr [rcx+2], 2
0x18000844d  jnz     short loc_180008482
0x18000844f  lea     rbx, [rax+4]
0x180008453  cmp     rbx, rbp
0x180008456  ja      short loc_1800084CE
0x180008458  mov     [rcx+10h], rax
0x18000845c  add     rcx, 4
0x180008460  jz      short loc_18000846F
0x180008462  test    rax, rax
0x180008465  jz      short loc_18000846D
0x180008467  mov     eax, [rax]
0x180008469  mov     [rcx], eax
0x18000846b  jmp     short loc_180008485
0x18000846d  mov     [rcx], eax
0x18000846f  call    cs:__imp__o__errno
0x180008475  mov     dword ptr [rax], 16h
0x18000847b  call    _invalid_parameter_noinfo
0x180008480  jmp     short loc_180008485
0x180008482  mov     rbx, rax
0x180008485  movzx   eax, word ptr [rdi]
0x180008488  mov     [rdi+8], ax
0x18000848c  test    ax, ax
0x18000848f  jnz     short loc_1800084C2
0x180008491  lea     rsi, [rbx+2]
0x180008495  cmp     rsi, rbp
0x180008498  ja      short loc_1800084CE
0x18000849a  test    rbx, rbx
0x18000849d  jz      short loc_1800084A8
0x18000849f  movzx   eax, word ptr [rbx]
0x1800084a2  mov     [rdi+8], ax
0x1800084a6  jmp     short loc_1800084BF
0x1800084a8  xor     eax, eax
0x1800084aa  mov     [rdi+8], ax
0x1800084ae  call    cs:__imp__o__errno
0x1800084b4  mov     dword ptr [rax], 16h
0x1800084ba  call    _invalid_parameter_noinfo
0x1800084bf  mov     rbx, rsi
0x1800084c2  movzx   ecx, word ptr [rdi+8]
0x1800084c6  add     rcx, rbx
0x1800084c9  cmp     rcx, rbp
0x1800084cc  jbe     short loc_1800084D2
0x1800084ce  xor     al, al
0x1800084d0  jmp     short loc_1800084DB
0x1800084d2  mov     [rdi+18h], rbx
0x1800084d6  mov     al, 1
0x1800084d8  mov     [r14], rcx
0x1800084db  add     rsp, 28h
0x1800084df  pop     r15
0x1800084e1  pop     r14
0x1800084e3  pop     rdi
0x1800084e4  pop     rsi
0x1800084e5  pop     rbp
0x1800084e6  pop     rbx
0x1800084e7  retn
```
