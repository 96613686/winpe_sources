# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180006408`
- end: `0x180006500`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `248`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800047c0`
- `0x180006c48`
- `0x18000701c`

## callees

- `0x180001fca`
- `0x180006408`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006445`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006487`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800064c6`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006445`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006487`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800064c6`

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
0x180006408  push    rbx
0x18000640a  push    rbp
0x18000640b  push    rsi
0x18000640c  push    rdi
0x18000640d  push    r14
0x18000640f  push    r15
0x180006411  sub     rsp, 28h
0x180006415  mov     rax, [rdx]
0x180006418  xor     r15d, r15d
0x18000641b  cmp     byte ptr [rcx+2], 1
0x18000641f  mov     rbp, r8
0x180006422  mov     r14, rdx
0x180006425  mov     rdi, rcx
0x180006428  jnz     short loc_180006461
0x18000642a  lea     rbx, [rax+2]
0x18000642e  cmp     rbx, r8
0x180006431  ja      loc_1800064E6
0x180006437  mov     [rcx+10h], rax
0x18000643b  test    rax, rax
0x18000643e  jz      short loc_180006445
0x180006440  movzx   ecx, word ptr [rax]
0x180006443  jmp     short loc_180006459
0x180006445  call    cs:__imp__o__errno
0x18000644b  mov     dword ptr [rax], 16h
0x180006451  call    _invalid_parameter_noinfo
0x180006456  mov     ecx, r15d
0x180006459  movzx   eax, cx
0x18000645c  mov     [rdi+4], eax
0x18000645f  jmp     short loc_18000649D
0x180006461  cmp     byte ptr [rcx+2], 2
0x180006465  jnz     short loc_18000649A
0x180006467  lea     rbx, [rax+4]
0x18000646b  cmp     rbx, rbp
0x18000646e  ja      short loc_1800064E6
0x180006470  mov     [rcx+10h], rax
0x180006474  add     rcx, 4
0x180006478  jz      short loc_180006487
0x18000647a  test    rax, rax
0x18000647d  jz      short loc_180006485
0x18000647f  mov     eax, [rax]
0x180006481  mov     [rcx], eax
0x180006483  jmp     short loc_18000649D
0x180006485  mov     [rcx], eax
0x180006487  call    cs:__imp__o__errno
0x18000648d  mov     dword ptr [rax], 16h
0x180006493  call    _invalid_parameter_noinfo
0x180006498  jmp     short loc_18000649D
0x18000649a  mov     rbx, rax
0x18000649d  movzx   eax, word ptr [rdi]
0x1800064a0  mov     [rdi+8], ax
0x1800064a4  test    ax, ax
0x1800064a7  jnz     short loc_1800064DA
0x1800064a9  lea     rsi, [rbx+2]
0x1800064ad  cmp     rsi, rbp
0x1800064b0  ja      short loc_1800064E6
0x1800064b2  test    rbx, rbx
0x1800064b5  jz      short loc_1800064C0
0x1800064b7  movzx   eax, word ptr [rbx]
0x1800064ba  mov     [rdi+8], ax
0x1800064be  jmp     short loc_1800064D7
0x1800064c0  xor     eax, eax
0x1800064c2  mov     [rdi+8], ax
0x1800064c6  call    cs:__imp__o__errno
0x1800064cc  mov     dword ptr [rax], 16h
0x1800064d2  call    _invalid_parameter_noinfo
0x1800064d7  mov     rbx, rsi
0x1800064da  movzx   ecx, word ptr [rdi+8]
0x1800064de  add     rcx, rbx
0x1800064e1  cmp     rcx, rbp
0x1800064e4  jbe     short loc_1800064EA
0x1800064e6  xor     al, al
0x1800064e8  jmp     short loc_1800064F3
0x1800064ea  mov     [rdi+18h], rbx
0x1800064ee  mov     al, 1
0x1800064f0  mov     [r14], rcx
0x1800064f3  add     rsp, 28h
0x1800064f7  pop     r15
0x1800064f9  pop     r14
0x1800064fb  pop     rdi
0x1800064fc  pop     rsi
0x1800064fd  pop     rbp
0x1800064fe  pop     rbx
0x1800064ff  retn
```
