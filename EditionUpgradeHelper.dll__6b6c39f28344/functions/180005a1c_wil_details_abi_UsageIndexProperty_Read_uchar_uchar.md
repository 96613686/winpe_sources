# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180005a1c`
- end: `0x180005b14`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `248`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800042ec`
- `0x180006060`
- `0x180006434`

## callees

- `0x180002472`
- `0x180005a1c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005a59`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005a9b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005ada`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005a59`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005a9b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005ada`

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
0x180005a1c  push    rbx
0x180005a1e  push    rbp
0x180005a1f  push    rsi
0x180005a20  push    rdi
0x180005a21  push    r14
0x180005a23  push    r15
0x180005a25  sub     rsp, 28h
0x180005a29  mov     rax, [rdx]
0x180005a2c  xor     r15d, r15d
0x180005a2f  cmp     byte ptr [rcx+2], 1
0x180005a33  mov     rbp, r8
0x180005a36  mov     r14, rdx
0x180005a39  mov     rdi, rcx
0x180005a3c  jnz     short loc_180005A75
0x180005a3e  lea     rbx, [rax+2]
0x180005a42  cmp     rbx, r8
0x180005a45  ja      loc_180005AFA
0x180005a4b  mov     [rcx+10h], rax
0x180005a4f  test    rax, rax
0x180005a52  jz      short loc_180005A59
0x180005a54  movzx   ecx, word ptr [rax]
0x180005a57  jmp     short loc_180005A6D
0x180005a59  call    cs:__imp__o__errno
0x180005a5f  mov     dword ptr [rax], 16h
0x180005a65  call    _invalid_parameter_noinfo
0x180005a6a  mov     ecx, r15d
0x180005a6d  movzx   eax, cx
0x180005a70  mov     [rdi+4], eax
0x180005a73  jmp     short loc_180005AB1
0x180005a75  cmp     byte ptr [rcx+2], 2
0x180005a79  jnz     short loc_180005AAE
0x180005a7b  lea     rbx, [rax+4]
0x180005a7f  cmp     rbx, rbp
0x180005a82  ja      short loc_180005AFA
0x180005a84  mov     [rcx+10h], rax
0x180005a88  add     rcx, 4
0x180005a8c  jz      short loc_180005A9B
0x180005a8e  test    rax, rax
0x180005a91  jz      short loc_180005A99
0x180005a93  mov     eax, [rax]
0x180005a95  mov     [rcx], eax
0x180005a97  jmp     short loc_180005AB1
0x180005a99  mov     [rcx], eax
0x180005a9b  call    cs:__imp__o__errno
0x180005aa1  mov     dword ptr [rax], 16h
0x180005aa7  call    _invalid_parameter_noinfo
0x180005aac  jmp     short loc_180005AB1
0x180005aae  mov     rbx, rax
0x180005ab1  movzx   eax, word ptr [rdi]
0x180005ab4  mov     [rdi+8], ax
0x180005ab8  test    ax, ax
0x180005abb  jnz     short loc_180005AEE
0x180005abd  lea     rsi, [rbx+2]
0x180005ac1  cmp     rsi, rbp
0x180005ac4  ja      short loc_180005AFA
0x180005ac6  test    rbx, rbx
0x180005ac9  jz      short loc_180005AD4
0x180005acb  movzx   eax, word ptr [rbx]
0x180005ace  mov     [rdi+8], ax
0x180005ad2  jmp     short loc_180005AEB
0x180005ad4  xor     eax, eax
0x180005ad6  mov     [rdi+8], ax
0x180005ada  call    cs:__imp__o__errno
0x180005ae0  mov     dword ptr [rax], 16h
0x180005ae6  call    _invalid_parameter_noinfo
0x180005aeb  mov     rbx, rsi
0x180005aee  movzx   ecx, word ptr [rdi+8]
0x180005af2  add     rcx, rbx
0x180005af5  cmp     rcx, rbp
0x180005af8  jbe     short loc_180005AFE
0x180005afa  xor     al, al
0x180005afc  jmp     short loc_180005B07
0x180005afe  mov     [rdi+18h], rbx
0x180005b02  mov     al, 1
0x180005b04  mov     [r14], rcx
0x180005b07  add     rsp, 28h
0x180005b0b  pop     r15
0x180005b0d  pop     r14
0x180005b0f  pop     rdi
0x180005b10  pop     rsi
0x180005b11  pop     rbp
0x180005b12  pop     rbx
0x180005b13  retn
```
