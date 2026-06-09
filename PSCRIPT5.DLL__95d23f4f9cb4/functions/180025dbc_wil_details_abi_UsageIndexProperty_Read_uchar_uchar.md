# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180025dbc`
- end: `0x180025eb4`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `248`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18002454c`
- `0x180026400`
- `0x1800267d4`

## callees

- `0x1800027d6`
- `0x180025dbc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180025df9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180025e3b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180025e7a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180025df9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180025e3b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180025e7a`

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
0x180025dbc  push    rbx
0x180025dbe  push    rbp
0x180025dbf  push    rsi
0x180025dc0  push    rdi
0x180025dc1  push    r14
0x180025dc3  push    r15
0x180025dc5  sub     rsp, 28h
0x180025dc9  mov     rax, [rdx]
0x180025dcc  xor     r15d, r15d
0x180025dcf  cmp     byte ptr [rcx+2], 1
0x180025dd3  mov     rbp, r8
0x180025dd6  mov     r14, rdx
0x180025dd9  mov     rdi, rcx
0x180025ddc  jnz     short loc_180025E15
0x180025dde  lea     rbx, [rax+2]
0x180025de2  cmp     rbx, r8
0x180025de5  ja      loc_180025E9A
0x180025deb  mov     [rcx+10h], rax
0x180025def  test    rax, rax
0x180025df2  jz      short loc_180025DF9
0x180025df4  movzx   ecx, word ptr [rax]
0x180025df7  jmp     short loc_180025E0D
0x180025df9  call    cs:__imp__o__errno
0x180025dff  mov     dword ptr [rax], 16h
0x180025e05  call    _invalid_parameter_noinfo
0x180025e0a  mov     ecx, r15d
0x180025e0d  movzx   eax, cx
0x180025e10  mov     [rdi+4], eax
0x180025e13  jmp     short loc_180025E51
0x180025e15  cmp     byte ptr [rcx+2], 2
0x180025e19  jnz     short loc_180025E4E
0x180025e1b  lea     rbx, [rax+4]
0x180025e1f  cmp     rbx, rbp
0x180025e22  ja      short loc_180025E9A
0x180025e24  mov     [rcx+10h], rax
0x180025e28  add     rcx, 4
0x180025e2c  jz      short loc_180025E3B
0x180025e2e  test    rax, rax
0x180025e31  jz      short loc_180025E39
0x180025e33  mov     eax, [rax]
0x180025e35  mov     [rcx], eax
0x180025e37  jmp     short loc_180025E51
0x180025e39  mov     [rcx], eax
0x180025e3b  call    cs:__imp__o__errno
0x180025e41  mov     dword ptr [rax], 16h
0x180025e47  call    _invalid_parameter_noinfo
0x180025e4c  jmp     short loc_180025E51
0x180025e4e  mov     rbx, rax
0x180025e51  movzx   eax, word ptr [rdi]
0x180025e54  mov     [rdi+8], ax
0x180025e58  test    ax, ax
0x180025e5b  jnz     short loc_180025E8E
0x180025e5d  lea     rsi, [rbx+2]
0x180025e61  cmp     rsi, rbp
0x180025e64  ja      short loc_180025E9A
0x180025e66  test    rbx, rbx
0x180025e69  jz      short loc_180025E74
0x180025e6b  movzx   eax, word ptr [rbx]
0x180025e6e  mov     [rdi+8], ax
0x180025e72  jmp     short loc_180025E8B
0x180025e74  xor     eax, eax
0x180025e76  mov     [rdi+8], ax
0x180025e7a  call    cs:__imp__o__errno
0x180025e80  mov     dword ptr [rax], 16h
0x180025e86  call    _invalid_parameter_noinfo
0x180025e8b  mov     rbx, rsi
0x180025e8e  movzx   ecx, word ptr [rdi+8]
0x180025e92  add     rcx, rbx
0x180025e95  cmp     rcx, rbp
0x180025e98  jbe     short loc_180025E9E
0x180025e9a  xor     al, al
0x180025e9c  jmp     short loc_180025EA7
0x180025e9e  mov     [rdi+18h], rbx
0x180025ea2  mov     al, 1
0x180025ea4  mov     [r14], rcx
0x180025ea7  add     rsp, 28h
0x180025eab  pop     r15
0x180025ead  pop     r14
0x180025eaf  pop     rdi
0x180025eb0  pop     rsi
0x180025eb1  pop     rbp
0x180025eb2  pop     rbx
0x180025eb3  retn
```
