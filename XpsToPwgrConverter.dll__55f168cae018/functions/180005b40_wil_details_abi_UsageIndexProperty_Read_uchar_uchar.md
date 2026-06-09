# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180005b40`
- end: `0x180005c38`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `248`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000440c`
- `0x1800061c8`
- `0x18000659c`

## callees

- `0x18000212a`
- `0x180005b40`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005b7d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005bbf`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005bfe`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005b7d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005bbf`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005bfe`

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
0x180005b40  push    rbx
0x180005b42  push    rbp
0x180005b43  push    rsi
0x180005b44  push    rdi
0x180005b45  push    r14
0x180005b47  push    r15
0x180005b49  sub     rsp, 28h
0x180005b4d  mov     rax, [rdx]
0x180005b50  xor     r15d, r15d
0x180005b53  cmp     byte ptr [rcx+2], 1
0x180005b57  mov     rbp, r8
0x180005b5a  mov     r14, rdx
0x180005b5d  mov     rdi, rcx
0x180005b60  jnz     short loc_180005B99
0x180005b62  lea     rbx, [rax+2]
0x180005b66  cmp     rbx, r8
0x180005b69  ja      loc_180005C1E
0x180005b6f  mov     [rcx+10h], rax
0x180005b73  test    rax, rax
0x180005b76  jz      short loc_180005B7D
0x180005b78  movzx   ecx, word ptr [rax]
0x180005b7b  jmp     short loc_180005B91
0x180005b7d  call    cs:__imp__o__errno
0x180005b83  mov     dword ptr [rax], 16h
0x180005b89  call    _invalid_parameter_noinfo
0x180005b8e  mov     ecx, r15d
0x180005b91  movzx   eax, cx
0x180005b94  mov     [rdi+4], eax
0x180005b97  jmp     short loc_180005BD5
0x180005b99  cmp     byte ptr [rcx+2], 2
0x180005b9d  jnz     short loc_180005BD2
0x180005b9f  lea     rbx, [rax+4]
0x180005ba3  cmp     rbx, rbp
0x180005ba6  ja      short loc_180005C1E
0x180005ba8  mov     [rcx+10h], rax
0x180005bac  add     rcx, 4
0x180005bb0  jz      short loc_180005BBF
0x180005bb2  test    rax, rax
0x180005bb5  jz      short loc_180005BBD
0x180005bb7  mov     eax, [rax]
0x180005bb9  mov     [rcx], eax
0x180005bbb  jmp     short loc_180005BD5
0x180005bbd  mov     [rcx], eax
0x180005bbf  call    cs:__imp__o__errno
0x180005bc5  mov     dword ptr [rax], 16h
0x180005bcb  call    _invalid_parameter_noinfo
0x180005bd0  jmp     short loc_180005BD5
0x180005bd2  mov     rbx, rax
0x180005bd5  movzx   eax, word ptr [rdi]
0x180005bd8  mov     [rdi+8], ax
0x180005bdc  test    ax, ax
0x180005bdf  jnz     short loc_180005C12
0x180005be1  lea     rsi, [rbx+2]
0x180005be5  cmp     rsi, rbp
0x180005be8  ja      short loc_180005C1E
0x180005bea  test    rbx, rbx
0x180005bed  jz      short loc_180005BF8
0x180005bef  movzx   eax, word ptr [rbx]
0x180005bf2  mov     [rdi+8], ax
0x180005bf6  jmp     short loc_180005C0F
0x180005bf8  xor     eax, eax
0x180005bfa  mov     [rdi+8], ax
0x180005bfe  call    cs:__imp__o__errno
0x180005c04  mov     dword ptr [rax], 16h
0x180005c0a  call    _invalid_parameter_noinfo
0x180005c0f  mov     rbx, rsi
0x180005c12  movzx   ecx, word ptr [rdi+8]
0x180005c16  add     rcx, rbx
0x180005c19  cmp     rcx, rbp
0x180005c1c  jbe     short loc_180005C22
0x180005c1e  xor     al, al
0x180005c20  jmp     short loc_180005C2B
0x180005c22  mov     [rdi+18h], rbx
0x180005c26  mov     al, 1
0x180005c28  mov     [r14], rcx
0x180005c2b  add     rsp, 28h
0x180005c2f  pop     r15
0x180005c31  pop     r14
0x180005c33  pop     rdi
0x180005c34  pop     rsi
0x180005c35  pop     rbp
0x180005c36  pop     rbx
0x180005c37  retn
```
