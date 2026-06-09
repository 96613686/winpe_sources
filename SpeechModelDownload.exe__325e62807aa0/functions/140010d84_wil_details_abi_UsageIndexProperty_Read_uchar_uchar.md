# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x140010d84`
- end: `0x140010e7c`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `248`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14000eb8c`
- `0x140011558`
- `0x14001192c`

## callees

- `0x140003026`
- `0x140010d84`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140010dc1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140010e03`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140010e42`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140010dc1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140010e03`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140010e42`

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
0x140010d84  push    rbx
0x140010d86  push    rbp
0x140010d87  push    rsi
0x140010d88  push    rdi
0x140010d89  push    r14
0x140010d8b  push    r15
0x140010d8d  sub     rsp, 28h
0x140010d91  mov     rax, [rdx]
0x140010d94  xor     r15d, r15d
0x140010d97  cmp     byte ptr [rcx+2], 1
0x140010d9b  mov     rbp, r8
0x140010d9e  mov     r14, rdx
0x140010da1  mov     rdi, rcx
0x140010da4  jnz     short loc_140010DDD
0x140010da6  lea     rbx, [rax+2]
0x140010daa  cmp     rbx, r8
0x140010dad  ja      loc_140010E62
0x140010db3  mov     [rcx+10h], rax
0x140010db7  test    rax, rax
0x140010dba  jz      short loc_140010DC1
0x140010dbc  movzx   ecx, word ptr [rax]
0x140010dbf  jmp     short loc_140010DD5
0x140010dc1  call    cs:__imp__o__errno
0x140010dc7  mov     dword ptr [rax], 16h
0x140010dcd  call    _invalid_parameter_noinfo
0x140010dd2  mov     ecx, r15d
0x140010dd5  movzx   eax, cx
0x140010dd8  mov     [rdi+4], eax
0x140010ddb  jmp     short loc_140010E19
0x140010ddd  cmp     byte ptr [rcx+2], 2
0x140010de1  jnz     short loc_140010E16
0x140010de3  lea     rbx, [rax+4]
0x140010de7  cmp     rbx, rbp
0x140010dea  ja      short loc_140010E62
0x140010dec  mov     [rcx+10h], rax
0x140010df0  add     rcx, 4
0x140010df4  jz      short loc_140010E03
0x140010df6  test    rax, rax
0x140010df9  jz      short loc_140010E01
0x140010dfb  mov     eax, [rax]
0x140010dfd  mov     [rcx], eax
0x140010dff  jmp     short loc_140010E19
0x140010e01  mov     [rcx], eax
0x140010e03  call    cs:__imp__o__errno
0x140010e09  mov     dword ptr [rax], 16h
0x140010e0f  call    _invalid_parameter_noinfo
0x140010e14  jmp     short loc_140010E19
0x140010e16  mov     rbx, rax
0x140010e19  movzx   eax, word ptr [rdi]
0x140010e1c  mov     [rdi+8], ax
0x140010e20  test    ax, ax
0x140010e23  jnz     short loc_140010E56
0x140010e25  lea     rsi, [rbx+2]
0x140010e29  cmp     rsi, rbp
0x140010e2c  ja      short loc_140010E62
0x140010e2e  test    rbx, rbx
0x140010e31  jz      short loc_140010E3C
0x140010e33  movzx   eax, word ptr [rbx]
0x140010e36  mov     [rdi+8], ax
0x140010e3a  jmp     short loc_140010E53
0x140010e3c  xor     eax, eax
0x140010e3e  mov     [rdi+8], ax
0x140010e42  call    cs:__imp__o__errno
0x140010e48  mov     dword ptr [rax], 16h
0x140010e4e  call    _invalid_parameter_noinfo
0x140010e53  mov     rbx, rsi
0x140010e56  movzx   ecx, word ptr [rdi+8]
0x140010e5a  add     rcx, rbx
0x140010e5d  cmp     rcx, rbp
0x140010e60  jbe     short loc_140010E66
0x140010e62  xor     al, al
0x140010e64  jmp     short loc_140010E6F
0x140010e66  mov     [rdi+18h], rbx
0x140010e6a  mov     al, 1
0x140010e6c  mov     [r14], rcx
0x140010e6f  add     rsp, 28h
0x140010e73  pop     r15
0x140010e75  pop     r14
0x140010e77  pop     rdi
0x140010e78  pop     rsi
0x140010e79  pop     rbp
0x140010e7a  pop     rbx
0x140010e7b  retn
```
