# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x140008234`
- end: `0x14000832c`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `248`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140004ba8`
- `0x140008a78`
- `0x140008e4c`

## callees

- `0x1400020b2`
- `0x140008234`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140008271`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400082b3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400082f2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140008271`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400082b3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400082f2`

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
0x140008234  push    rbx
0x140008236  push    rbp
0x140008237  push    rsi
0x140008238  push    rdi
0x140008239  push    r14
0x14000823b  push    r15
0x14000823d  sub     rsp, 28h
0x140008241  mov     rax, [rdx]
0x140008244  xor     r15d, r15d
0x140008247  cmp     byte ptr [rcx+2], 1
0x14000824b  mov     rbp, r8
0x14000824e  mov     r14, rdx
0x140008251  mov     rdi, rcx
0x140008254  jnz     short loc_14000828D
0x140008256  lea     rbx, [rax+2]
0x14000825a  cmp     rbx, r8
0x14000825d  ja      loc_140008312
0x140008263  mov     [rcx+10h], rax
0x140008267  test    rax, rax
0x14000826a  jz      short loc_140008271
0x14000826c  movzx   ecx, word ptr [rax]
0x14000826f  jmp     short loc_140008285
0x140008271  call    cs:__imp__o__errno
0x140008277  mov     dword ptr [rax], 16h
0x14000827d  call    _invalid_parameter_noinfo
0x140008282  mov     ecx, r15d
0x140008285  movzx   eax, cx
0x140008288  mov     [rdi+4], eax
0x14000828b  jmp     short loc_1400082C9
0x14000828d  cmp     byte ptr [rcx+2], 2
0x140008291  jnz     short loc_1400082C6
0x140008293  lea     rbx, [rax+4]
0x140008297  cmp     rbx, rbp
0x14000829a  ja      short loc_140008312
0x14000829c  mov     [rcx+10h], rax
0x1400082a0  add     rcx, 4
0x1400082a4  jz      short loc_1400082B3
0x1400082a6  test    rax, rax
0x1400082a9  jz      short loc_1400082B1
0x1400082ab  mov     eax, [rax]
0x1400082ad  mov     [rcx], eax
0x1400082af  jmp     short loc_1400082C9
0x1400082b1  mov     [rcx], eax
0x1400082b3  call    cs:__imp__o__errno
0x1400082b9  mov     dword ptr [rax], 16h
0x1400082bf  call    _invalid_parameter_noinfo
0x1400082c4  jmp     short loc_1400082C9
0x1400082c6  mov     rbx, rax
0x1400082c9  movzx   eax, word ptr [rdi]
0x1400082cc  mov     [rdi+8], ax
0x1400082d0  test    ax, ax
0x1400082d3  jnz     short loc_140008306
0x1400082d5  lea     rsi, [rbx+2]
0x1400082d9  cmp     rsi, rbp
0x1400082dc  ja      short loc_140008312
0x1400082de  test    rbx, rbx
0x1400082e1  jz      short loc_1400082EC
0x1400082e3  movzx   eax, word ptr [rbx]
0x1400082e6  mov     [rdi+8], ax
0x1400082ea  jmp     short loc_140008303
0x1400082ec  xor     eax, eax
0x1400082ee  mov     [rdi+8], ax
0x1400082f2  call    cs:__imp__o__errno
0x1400082f8  mov     dword ptr [rax], 16h
0x1400082fe  call    _invalid_parameter_noinfo
0x140008303  mov     rbx, rsi
0x140008306  movzx   ecx, word ptr [rdi+8]
0x14000830a  add     rcx, rbx
0x14000830d  cmp     rcx, rbp
0x140008310  jbe     short loc_140008316
0x140008312  xor     al, al
0x140008314  jmp     short loc_14000831F
0x140008316  mov     [rdi+18h], rbx
0x14000831a  mov     al, 1
0x14000831c  mov     [r14], rcx
0x14000831f  add     rsp, 28h
0x140008323  pop     r15
0x140008325  pop     r14
0x140008327  pop     rdi
0x140008328  pop     rsi
0x140008329  pop     rbp
0x14000832a  pop     rbx
0x14000832b  retn
```
