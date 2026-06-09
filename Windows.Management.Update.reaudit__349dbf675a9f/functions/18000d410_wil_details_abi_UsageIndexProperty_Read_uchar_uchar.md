# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x18000d410`
- end: `0x18000d534`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `292`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b930`
- `0x18000dca0`
- `0x18000e094`

## callees

- `0x180003582`
- `0x18000d410`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000d45c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000d4a6`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000d4ed`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000d45c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000d4a6`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000d4ed`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Read(
        wil::details_abi::UsageIndexProperty *this,
        unsigned __int8 **a2,
        unsigned __int8 *a3)
{
  char v3; // al
  unsigned __int16 *v4; // r9
  unsigned __int16 *v8; // rdi
  unsigned __int16 v9; // ax
  _DWORD *v10; // rcx
  __int16 v11; // ax
  unsigned __int16 *v12; // rdi
  unsigned __int16 *v13; // rsi
  unsigned __int8 *v14; // rcx
  bool result; // al

  v3 = *((_BYTE *)this + 2);
  v4 = (unsigned __int16 *)*a2;
  if ( v3 == 1 )
  {
    v8 = v4 + 1;
    if ( v4 + 1 > (unsigned __int16 *)a3 )
      return 0;
    *((_QWORD *)this + 2) = v4;
    if ( v4 )
    {
      v9 = *v4;
    }
    else
    {
      *(_DWORD *)_o__errno() = 22;
      invalid_parameter_noinfo();
      v9 = 0;
    }
    *((_DWORD *)this + 1) = v9;
    goto LABEL_14;
  }
  if ( v3 != 2 )
    goto LABEL_15;
  v8 = v4 + 2;
  if ( v4 + 2 > (unsigned __int16 *)a3 )
    return 0;
  *((_QWORD *)this + 2) = v4;
  v10 = (_DWORD *)((char *)this + 4);
  if ( !v10 )
    goto LABEL_13;
  if ( !v4 )
  {
    *v10 = 0;
LABEL_13:
    *(_DWORD *)_o__errno() = 22;
    invalid_parameter_noinfo();
    goto LABEL_14;
  }
  *v10 = *(_DWORD *)v4;
LABEL_14:
  v4 = v8;
LABEL_15:
  v11 = *(_WORD *)this;
  v12 = (unsigned __int16 *)((char *)this + 8);
  *((_WORD *)this + 4) = *(_WORD *)this;
  if ( v11 )
    goto LABEL_23;
  v13 = v4 + 1;
  if ( v4 + 1 > (unsigned __int16 *)a3 )
    return 0;
  if ( this == (wil::details_abi::UsageIndexProperty *)-8LL )
  {
LABEL_21:
    *(_DWORD *)_o__errno() = 22;
    invalid_parameter_noinfo();
    goto LABEL_22;
  }
  if ( !v4 )
  {
    *v12 = 0;
    goto LABEL_21;
  }
  *v12 = *v4;
LABEL_22:
  v4 = v13;
LABEL_23:
  v14 = (unsigned __int8 *)v4 + *v12;
  if ( v14 > a3 )
    return 0;
  *((_QWORD *)this + 3) = v4;
  result = 1;
  *a2 = v14;
  return result;
}

```

## disassembly

```asm
0x18000d410  mov     [rsp+arg_8], rbx
0x18000d415  mov     [rsp+arg_10], rbp
0x18000d41a  push    rsi
0x18000d41b  push    rdi
0x18000d41c  push    r12
0x18000d41e  push    r14
0x18000d420  push    r15
0x18000d422  sub     rsp, 20h
0x18000d426  mov     al, [rcx+2]
0x18000d429  xor     r15d, r15d
0x18000d42c  mov     r9, [rdx]
0x18000d42f  mov     rbp, r8
0x18000d432  mov     r14, rdx
0x18000d435  mov     rbx, rcx
0x18000d438  lea     r12d, [r15+16h]
0x18000d43c  cmp     al, 1
0x18000d43e  jnz     short loc_18000D47B
0x18000d440  lea     rdi, [r9+2]
0x18000d444  cmp     rdi, r8
0x18000d447  ja      loc_18000D50F
0x18000d44d  mov     [rcx+10h], r9
0x18000d451  test    r9, r9
0x18000d454  jz      short loc_18000D45C
0x18000d456  movzx   eax, word ptr [r9]
0x18000d45a  jmp     short loc_18000D473
0x18000d45c  call    cs:__imp__o__errno
0x18000d463  nop     dword ptr [rax+rax+00h]
0x18000d468  mov     [rax], r12d
0x18000d46b  call    _invalid_parameter_noinfo
0x18000d470  mov     eax, r15d
0x18000d473  movzx   eax, ax
0x18000d476  mov     [rbx+4], eax
0x18000d479  jmp     short loc_18000D4BA
0x18000d47b  cmp     al, 2
0x18000d47d  jnz     short loc_18000D4BD
0x18000d47f  lea     rdi, [r9+4]
0x18000d483  cmp     rdi, rbp
0x18000d486  ja      loc_18000D50F
0x18000d48c  mov     [rcx+10h], r9
0x18000d490  add     rcx, 4
0x18000d494  jz      short loc_18000D4A6
0x18000d496  test    r9, r9
0x18000d499  jz      short loc_18000D4A2
0x18000d49b  mov     eax, [r9]
0x18000d49e  mov     [rcx], eax
0x18000d4a0  jmp     short loc_18000D4BA
0x18000d4a2  xor     eax, eax
0x18000d4a4  mov     [rcx], eax
0x18000d4a6  call    cs:__imp__o__errno
0x18000d4ad  nop     dword ptr [rax+rax+00h]
0x18000d4b2  mov     [rax], r12d
0x18000d4b5  call    _invalid_parameter_noinfo
0x18000d4ba  mov     r9, rdi
0x18000d4bd  movzx   eax, word ptr [rbx]
0x18000d4c0  lea     rdi, [rbx+8]
0x18000d4c4  mov     [rdi], ax
0x18000d4c7  test    ax, ax
0x18000d4ca  jnz     short loc_18000D504
0x18000d4cc  lea     rsi, [r9+2]
0x18000d4d0  cmp     rsi, rbp
0x18000d4d3  ja      short loc_18000D50F
0x18000d4d5  test    rdi, rdi
0x18000d4d8  jz      short loc_18000D4ED
0x18000d4da  test    r9, r9
0x18000d4dd  jz      short loc_18000D4E8
0x18000d4df  movzx   eax, word ptr [r9]
0x18000d4e3  mov     [rdi], ax
0x18000d4e6  jmp     short loc_18000D501
0x18000d4e8  xor     eax, eax
0x18000d4ea  mov     [rdi], ax
0x18000d4ed  call    cs:__imp__o__errno
0x18000d4f4  nop     dword ptr [rax+rax+00h]
0x18000d4f9  mov     [rax], r12d
0x18000d4fc  call    _invalid_parameter_noinfo
0x18000d501  mov     r9, rsi
0x18000d504  movzx   ecx, word ptr [rdi]
0x18000d507  add     rcx, r9
0x18000d50a  cmp     rcx, rbp
0x18000d50d  jbe     short loc_18000D513
0x18000d50f  xor     al, al
0x18000d511  jmp     short loc_18000D51C
0x18000d513  mov     [rbx+18h], r9
0x18000d517  mov     al, 1
0x18000d519  mov     [r14], rcx
0x18000d51c  mov     rbx, [rsp+48h+arg_8]
0x18000d521  mov     rbp, [rsp+48h+arg_10]
0x18000d526  add     rsp, 20h
0x18000d52a  pop     r15
0x18000d52c  pop     r14
0x18000d52e  pop     r12
0x18000d530  pop     rdi
0x18000d531  pop     rsi
0x18000d532  retn
```
