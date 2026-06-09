# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x14000ae58`
- end: `0x14000af50`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `248`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14000a0dc`
- `0x14000b430`
- `0x14000b804`

## callees

- `0x140002f1a`
- `0x14000ae58`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000ae95`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000aed7`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000af16`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000ae95`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000aed7`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000af16`

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
0x14000ae58  push    rbx
0x14000ae5a  push    rbp
0x14000ae5b  push    rsi
0x14000ae5c  push    rdi
0x14000ae5d  push    r14
0x14000ae5f  push    r15
0x14000ae61  sub     rsp, 28h
0x14000ae65  mov     rax, [rdx]
0x14000ae68  xor     r15d, r15d
0x14000ae6b  cmp     byte ptr [rcx+2], 1
0x14000ae6f  mov     rbp, r8
0x14000ae72  mov     r14, rdx
0x14000ae75  mov     rdi, rcx
0x14000ae78  jnz     short loc_14000AEB1
0x14000ae7a  lea     rbx, [rax+2]
0x14000ae7e  cmp     rbx, r8
0x14000ae81  ja      loc_14000AF36
0x14000ae87  mov     [rcx+10h], rax
0x14000ae8b  test    rax, rax
0x14000ae8e  jz      short loc_14000AE95
0x14000ae90  movzx   ecx, word ptr [rax]
0x14000ae93  jmp     short loc_14000AEA9
0x14000ae95  call    cs:__imp__o__errno
0x14000ae9b  mov     dword ptr [rax], 16h
0x14000aea1  call    _invalid_parameter_noinfo
0x14000aea6  mov     ecx, r15d
0x14000aea9  movzx   eax, cx
0x14000aeac  mov     [rdi+4], eax
0x14000aeaf  jmp     short loc_14000AEED
0x14000aeb1  cmp     byte ptr [rcx+2], 2
0x14000aeb5  jnz     short loc_14000AEEA
0x14000aeb7  lea     rbx, [rax+4]
0x14000aebb  cmp     rbx, rbp
0x14000aebe  ja      short loc_14000AF36
0x14000aec0  mov     [rcx+10h], rax
0x14000aec4  add     rcx, 4
0x14000aec8  jz      short loc_14000AED7
0x14000aeca  test    rax, rax
0x14000aecd  jz      short loc_14000AED5
0x14000aecf  mov     eax, [rax]
0x14000aed1  mov     [rcx], eax
0x14000aed3  jmp     short loc_14000AEED
0x14000aed5  mov     [rcx], eax
0x14000aed7  call    cs:__imp__o__errno
0x14000aedd  mov     dword ptr [rax], 16h
0x14000aee3  call    _invalid_parameter_noinfo
0x14000aee8  jmp     short loc_14000AEED
0x14000aeea  mov     rbx, rax
0x14000aeed  movzx   eax, word ptr [rdi]
0x14000aef0  mov     [rdi+8], ax
0x14000aef4  test    ax, ax
0x14000aef7  jnz     short loc_14000AF2A
0x14000aef9  lea     rsi, [rbx+2]
0x14000aefd  cmp     rsi, rbp
0x14000af00  ja      short loc_14000AF36
0x14000af02  test    rbx, rbx
0x14000af05  jz      short loc_14000AF10
0x14000af07  movzx   eax, word ptr [rbx]
0x14000af0a  mov     [rdi+8], ax
0x14000af0e  jmp     short loc_14000AF27
0x14000af10  xor     eax, eax
0x14000af12  mov     [rdi+8], ax
0x14000af16  call    cs:__imp__o__errno
0x14000af1c  mov     dword ptr [rax], 16h
0x14000af22  call    _invalid_parameter_noinfo
0x14000af27  mov     rbx, rsi
0x14000af2a  movzx   ecx, word ptr [rdi+8]
0x14000af2e  add     rcx, rbx
0x14000af31  cmp     rcx, rbp
0x14000af34  jbe     short loc_14000AF3A
0x14000af36  xor     al, al
0x14000af38  jmp     short loc_14000AF43
0x14000af3a  mov     [rdi+18h], rbx
0x14000af3e  mov     al, 1
0x14000af40  mov     [r14], rcx
0x14000af43  add     rsp, 28h
0x14000af47  pop     r15
0x14000af49  pop     r14
0x14000af4b  pop     rdi
0x14000af4c  pop     rsi
0x14000af4d  pop     rbp
0x14000af4e  pop     rbx
0x14000af4f  retn
```
