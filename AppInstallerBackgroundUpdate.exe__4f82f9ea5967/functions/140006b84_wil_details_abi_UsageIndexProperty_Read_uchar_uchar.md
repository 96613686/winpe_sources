# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x140006b84`
- end: `0x140006c7c`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `248`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1400065ec`
- `0x14000715c`
- `0x140007530`

## callees

- `0x140001eae`
- `0x140006b84`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140006bc1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140006c03`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140006c42`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140006bc1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140006c03`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140006c42`

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
0x140006b84  push    rbx
0x140006b86  push    rbp
0x140006b87  push    rsi
0x140006b88  push    rdi
0x140006b89  push    r14
0x140006b8b  push    r15
0x140006b8d  sub     rsp, 28h
0x140006b91  mov     rax, [rdx]
0x140006b94  xor     r15d, r15d
0x140006b97  cmp     byte ptr [rcx+2], 1
0x140006b9b  mov     rbp, r8
0x140006b9e  mov     r14, rdx
0x140006ba1  mov     rdi, rcx
0x140006ba4  jnz     short loc_140006BDD
0x140006ba6  lea     rbx, [rax+2]
0x140006baa  cmp     rbx, r8
0x140006bad  ja      loc_140006C62
0x140006bb3  mov     [rcx+10h], rax
0x140006bb7  test    rax, rax
0x140006bba  jz      short loc_140006BC1
0x140006bbc  movzx   ecx, word ptr [rax]
0x140006bbf  jmp     short loc_140006BD5
0x140006bc1  call    cs:__imp__o__errno
0x140006bc7  mov     dword ptr [rax], 16h
0x140006bcd  call    _invalid_parameter_noinfo
0x140006bd2  mov     ecx, r15d
0x140006bd5  movzx   eax, cx
0x140006bd8  mov     [rdi+4], eax
0x140006bdb  jmp     short loc_140006C19
0x140006bdd  cmp     byte ptr [rcx+2], 2
0x140006be1  jnz     short loc_140006C16
0x140006be3  lea     rbx, [rax+4]
0x140006be7  cmp     rbx, rbp
0x140006bea  ja      short loc_140006C62
0x140006bec  mov     [rcx+10h], rax
0x140006bf0  add     rcx, 4
0x140006bf4  jz      short loc_140006C03
0x140006bf6  test    rax, rax
0x140006bf9  jz      short loc_140006C01
0x140006bfb  mov     eax, [rax]
0x140006bfd  mov     [rcx], eax
0x140006bff  jmp     short loc_140006C19
0x140006c01  mov     [rcx], eax
0x140006c03  call    cs:__imp__o__errno
0x140006c09  mov     dword ptr [rax], 16h
0x140006c0f  call    _invalid_parameter_noinfo
0x140006c14  jmp     short loc_140006C19
0x140006c16  mov     rbx, rax
0x140006c19  movzx   eax, word ptr [rdi]
0x140006c1c  mov     [rdi+8], ax
0x140006c20  test    ax, ax
0x140006c23  jnz     short loc_140006C56
0x140006c25  lea     rsi, [rbx+2]
0x140006c29  cmp     rsi, rbp
0x140006c2c  ja      short loc_140006C62
0x140006c2e  test    rbx, rbx
0x140006c31  jz      short loc_140006C3C
0x140006c33  movzx   eax, word ptr [rbx]
0x140006c36  mov     [rdi+8], ax
0x140006c3a  jmp     short loc_140006C53
0x140006c3c  xor     eax, eax
0x140006c3e  mov     [rdi+8], ax
0x140006c42  call    cs:__imp__o__errno
0x140006c48  mov     dword ptr [rax], 16h
0x140006c4e  call    _invalid_parameter_noinfo
0x140006c53  mov     rbx, rsi
0x140006c56  movzx   ecx, word ptr [rdi+8]
0x140006c5a  add     rcx, rbx
0x140006c5d  cmp     rcx, rbp
0x140006c60  jbe     short loc_140006C66
0x140006c62  xor     al, al
0x140006c64  jmp     short loc_140006C6F
0x140006c66  mov     [rdi+18h], rbx
0x140006c6a  mov     al, 1
0x140006c6c  mov     [r14], rcx
0x140006c6f  add     rsp, 28h
0x140006c73  pop     r15
0x140006c75  pop     r14
0x140006c77  pop     rdi
0x140006c78  pop     rsi
0x140006c79  pop     rbp
0x140006c7a  pop     rbx
0x140006c7b  retn
```
