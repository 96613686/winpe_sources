# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180026aa4`
- end: `0x180026bb3`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `271`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180025140`
- `0x18002715c`
- `0x180027550`

## callees

- `0x180002836`
- `0x180026aa4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180026ae1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180026b2d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180026b72`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180026ae1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180026b2d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180026b72`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Read(
        wil::details_abi::UsageIndexProperty *this,
        unsigned __int8 **a2,
        unsigned __int8 *a3)
{
  _DWORD *v3; // rax
  wil::details_abi::UsageIndexProperty *v6; // rdi
  _WORD *v7; // rbx
  __int16 v8; // ax
  unsigned __int8 *v9; // rcx
  bool result; // al

  v3 = *a2;
  v6 = this;
  if ( *((_BYTE *)this + 2) == 1 )
  {
    v7 = (_WORD *)v3 + 1;
    if ( (unsigned __int8 *)((char *)v3 + 2) > a3 )
      return 0;
    *((_QWORD *)this + 2) = v3;
    if ( v3 )
    {
      this = (wil::details_abi::UsageIndexProperty *)*(unsigned __int16 *)v3;
    }
    else
    {
      *(_DWORD *)_o__errno(this) = 22;
      invalid_parameter_noinfo();
      this = 0;
    }
    *((_DWORD *)v6 + 1) = (unsigned __int16)this;
  }
  else if ( *((_BYTE *)this + 2) == 2 )
  {
    v7 = v3 + 1;
    if ( v3 + 1 > (_DWORD *)a3 )
      return 0;
    *((_QWORD *)this + 2) = v3;
    this = (wil::details_abi::UsageIndexProperty *)((char *)this + 4);
    if ( this )
    {
      if ( v3 )
      {
        *(_DWORD *)this = *v3;
        goto LABEL_15;
      }
      *(_DWORD *)this = 0;
    }
    *(_DWORD *)_o__errno(this) = 22;
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
  if ( v7 + 1 > (_WORD *)a3 )
    return 0;
  if ( v7 )
  {
    *((_WORD *)v6 + 4) = *v7;
  }
  else
  {
    *((_WORD *)v6 + 4) = 0;
    *(_DWORD *)_o__errno(this) = 22;
    invalid_parameter_noinfo();
  }
  ++v7;
LABEL_21:
  v9 = (unsigned __int8 *)v7 + *((unsigned __int16 *)v6 + 4);
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
0x180026aa4  push    rbx
0x180026aa6  push    rbp
0x180026aa7  push    rsi
0x180026aa8  push    rdi
0x180026aa9  push    r14
0x180026aab  push    r15
0x180026aad  sub     rsp, 28h
0x180026ab1  mov     rax, [rdx]
0x180026ab4  xor     r15d, r15d
0x180026ab7  cmp     byte ptr [rcx+2], 1
0x180026abb  mov     rbp, r8
0x180026abe  mov     r14, rdx
0x180026ac1  mov     rdi, rcx
0x180026ac4  jnz     short loc_180026B03
0x180026ac6  lea     rbx, [rax+2]
0x180026aca  cmp     rbx, r8
0x180026acd  ja      loc_180026B98
0x180026ad3  mov     [rcx+10h], rax
0x180026ad7  test    rax, rax
0x180026ada  jz      short loc_180026AE1
0x180026adc  movzx   ecx, word ptr [rax]
0x180026adf  jmp     short loc_180026AFB
0x180026ae1  call    cs:__imp__o__errno
0x180026ae8  nop     dword ptr [rax+rax+00h]
0x180026aed  mov     dword ptr [rax], 16h
0x180026af3  call    _invalid_parameter_noinfo
0x180026af8  mov     ecx, r15d
0x180026afb  movzx   eax, cx
0x180026afe  mov     [rdi+4], eax
0x180026b01  jmp     short loc_180026B49
0x180026b03  cmp     byte ptr [rcx+2], 2
0x180026b07  jnz     short loc_180026B46
0x180026b09  lea     rbx, [rax+4]
0x180026b0d  cmp     rbx, rbp
0x180026b10  ja      loc_180026B98
0x180026b16  mov     [rcx+10h], rax
0x180026b1a  add     rcx, 4
0x180026b1e  jz      short loc_180026B2D
0x180026b20  test    rax, rax
0x180026b23  jz      short loc_180026B2B
0x180026b25  mov     eax, [rax]
0x180026b27  mov     [rcx], eax
0x180026b29  jmp     short loc_180026B49
0x180026b2b  mov     [rcx], eax
0x180026b2d  call    cs:__imp__o__errno
0x180026b34  nop     dword ptr [rax+rax+00h]
0x180026b39  mov     dword ptr [rax], 16h
0x180026b3f  call    _invalid_parameter_noinfo
0x180026b44  jmp     short loc_180026B49
0x180026b46  mov     rbx, rax
0x180026b49  movzx   eax, word ptr [rdi]
0x180026b4c  mov     [rdi+8], ax
0x180026b50  test    ax, ax
0x180026b53  jnz     short loc_180026B8C
0x180026b55  lea     rsi, [rbx+2]
0x180026b59  cmp     rsi, rbp
0x180026b5c  ja      short loc_180026B98
0x180026b5e  test    rbx, rbx
0x180026b61  jz      short loc_180026B6C
0x180026b63  movzx   eax, word ptr [rbx]
0x180026b66  mov     [rdi+8], ax
0x180026b6a  jmp     short loc_180026B89
0x180026b6c  xor     eax, eax
0x180026b6e  mov     [rdi+8], ax
0x180026b72  call    cs:__imp__o__errno
0x180026b79  nop     dword ptr [rax+rax+00h]
0x180026b7e  mov     dword ptr [rax], 16h
0x180026b84  call    _invalid_parameter_noinfo
0x180026b89  mov     rbx, rsi
0x180026b8c  movzx   ecx, word ptr [rdi+8]
0x180026b90  add     rcx, rbx
0x180026b93  cmp     rcx, rbp
0x180026b96  jbe     short loc_180026B9C
0x180026b98  xor     al, al
0x180026b9a  jmp     short loc_180026BA5
0x180026b9c  mov     [rdi+18h], rbx
0x180026ba0  mov     al, 1
0x180026ba2  mov     [r14], rcx
0x180026ba5  add     rsp, 28h
0x180026ba9  pop     r15
0x180026bab  pop     r14
0x180026bad  pop     rdi
0x180026bae  pop     rsi
0x180026baf  pop     rbp
0x180026bb0  pop     rbx
0x180026bb1  retn
```
