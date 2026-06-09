# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180006f1c`
- end: `0x180007014`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `248`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000565c`
- `0x1800077a8`
- `0x180007b7c`

## callees

- `0x1800029ca`
- `0x180006f1c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006f59`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006f9b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006fda`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006f59`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006f9b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006fda`

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
0x180006f1c  push    rbx
0x180006f1e  push    rbp
0x180006f1f  push    rsi
0x180006f20  push    rdi
0x180006f21  push    r14
0x180006f23  push    r15
0x180006f25  sub     rsp, 28h
0x180006f29  mov     rax, [rdx]
0x180006f2c  xor     r15d, r15d
0x180006f2f  cmp     byte ptr [rcx+2], 1
0x180006f33  mov     rbp, r8
0x180006f36  mov     r14, rdx
0x180006f39  mov     rdi, rcx
0x180006f3c  jnz     short loc_180006F75
0x180006f3e  lea     rbx, [rax+2]
0x180006f42  cmp     rbx, r8
0x180006f45  ja      loc_180006FFA
0x180006f4b  mov     [rcx+10h], rax
0x180006f4f  test    rax, rax
0x180006f52  jz      short loc_180006F59
0x180006f54  movzx   ecx, word ptr [rax]
0x180006f57  jmp     short loc_180006F6D
0x180006f59  call    cs:__imp__o__errno
0x180006f5f  mov     dword ptr [rax], 16h
0x180006f65  call    _invalid_parameter_noinfo
0x180006f6a  mov     ecx, r15d
0x180006f6d  movzx   eax, cx
0x180006f70  mov     [rdi+4], eax
0x180006f73  jmp     short loc_180006FB1
0x180006f75  cmp     byte ptr [rcx+2], 2
0x180006f79  jnz     short loc_180006FAE
0x180006f7b  lea     rbx, [rax+4]
0x180006f7f  cmp     rbx, rbp
0x180006f82  ja      short loc_180006FFA
0x180006f84  mov     [rcx+10h], rax
0x180006f88  add     rcx, 4
0x180006f8c  jz      short loc_180006F9B
0x180006f8e  test    rax, rax
0x180006f91  jz      short loc_180006F99
0x180006f93  mov     eax, [rax]
0x180006f95  mov     [rcx], eax
0x180006f97  jmp     short loc_180006FB1
0x180006f99  mov     [rcx], eax
0x180006f9b  call    cs:__imp__o__errno
0x180006fa1  mov     dword ptr [rax], 16h
0x180006fa7  call    _invalid_parameter_noinfo
0x180006fac  jmp     short loc_180006FB1
0x180006fae  mov     rbx, rax
0x180006fb1  movzx   eax, word ptr [rdi]
0x180006fb4  mov     [rdi+8], ax
0x180006fb8  test    ax, ax
0x180006fbb  jnz     short loc_180006FEE
0x180006fbd  lea     rsi, [rbx+2]
0x180006fc1  cmp     rsi, rbp
0x180006fc4  ja      short loc_180006FFA
0x180006fc6  test    rbx, rbx
0x180006fc9  jz      short loc_180006FD4
0x180006fcb  movzx   eax, word ptr [rbx]
0x180006fce  mov     [rdi+8], ax
0x180006fd2  jmp     short loc_180006FEB
0x180006fd4  xor     eax, eax
0x180006fd6  mov     [rdi+8], ax
0x180006fda  call    cs:__imp__o__errno
0x180006fe0  mov     dword ptr [rax], 16h
0x180006fe6  call    _invalid_parameter_noinfo
0x180006feb  mov     rbx, rsi
0x180006fee  movzx   ecx, word ptr [rdi+8]
0x180006ff2  add     rcx, rbx
0x180006ff5  cmp     rcx, rbp
0x180006ff8  jbe     short loc_180006FFE
0x180006ffa  xor     al, al
0x180006ffc  jmp     short loc_180007007
0x180006ffe  mov     [rdi+18h], rbx
0x180007002  mov     al, 1
0x180007004  mov     [r14], rcx
0x180007007  add     rsp, 28h
0x18000700b  pop     r15
0x18000700d  pop     r14
0x18000700f  pop     rdi
0x180007010  pop     rsi
0x180007011  pop     rbp
0x180007012  pop     rbx
0x180007013  retn
```
