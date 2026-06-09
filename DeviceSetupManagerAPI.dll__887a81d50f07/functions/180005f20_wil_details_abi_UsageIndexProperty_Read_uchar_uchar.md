# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180005f20`
- end: `0x180006018`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `248`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800047ec`
- `0x180006568`
- `0x18000693c`

## callees

- `0x1800024f6`
- `0x180005f20`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005f5d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005f9f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005fde`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005f5d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005f9f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005fde`

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
0x180005f20  push    rbx
0x180005f22  push    rbp
0x180005f23  push    rsi
0x180005f24  push    rdi
0x180005f25  push    r14
0x180005f27  push    r15
0x180005f29  sub     rsp, 28h
0x180005f2d  mov     rax, [rdx]
0x180005f30  xor     r15d, r15d
0x180005f33  cmp     byte ptr [rcx+2], 1
0x180005f37  mov     rbp, r8
0x180005f3a  mov     r14, rdx
0x180005f3d  mov     rdi, rcx
0x180005f40  jnz     short loc_180005F79
0x180005f42  lea     rbx, [rax+2]
0x180005f46  cmp     rbx, r8
0x180005f49  ja      loc_180005FFE
0x180005f4f  mov     [rcx+10h], rax
0x180005f53  test    rax, rax
0x180005f56  jz      short loc_180005F5D
0x180005f58  movzx   ecx, word ptr [rax]
0x180005f5b  jmp     short loc_180005F71
0x180005f5d  call    cs:__imp__o__errno
0x180005f63  mov     dword ptr [rax], 16h
0x180005f69  call    _invalid_parameter_noinfo
0x180005f6e  mov     ecx, r15d
0x180005f71  movzx   eax, cx
0x180005f74  mov     [rdi+4], eax
0x180005f77  jmp     short loc_180005FB5
0x180005f79  cmp     byte ptr [rcx+2], 2
0x180005f7d  jnz     short loc_180005FB2
0x180005f7f  lea     rbx, [rax+4]
0x180005f83  cmp     rbx, rbp
0x180005f86  ja      short loc_180005FFE
0x180005f88  mov     [rcx+10h], rax
0x180005f8c  add     rcx, 4
0x180005f90  jz      short loc_180005F9F
0x180005f92  test    rax, rax
0x180005f95  jz      short loc_180005F9D
0x180005f97  mov     eax, [rax]
0x180005f99  mov     [rcx], eax
0x180005f9b  jmp     short loc_180005FB5
0x180005f9d  mov     [rcx], eax
0x180005f9f  call    cs:__imp__o__errno
0x180005fa5  mov     dword ptr [rax], 16h
0x180005fab  call    _invalid_parameter_noinfo
0x180005fb0  jmp     short loc_180005FB5
0x180005fb2  mov     rbx, rax
0x180005fb5  movzx   eax, word ptr [rdi]
0x180005fb8  mov     [rdi+8], ax
0x180005fbc  test    ax, ax
0x180005fbf  jnz     short loc_180005FF2
0x180005fc1  lea     rsi, [rbx+2]
0x180005fc5  cmp     rsi, rbp
0x180005fc8  ja      short loc_180005FFE
0x180005fca  test    rbx, rbx
0x180005fcd  jz      short loc_180005FD8
0x180005fcf  movzx   eax, word ptr [rbx]
0x180005fd2  mov     [rdi+8], ax
0x180005fd6  jmp     short loc_180005FEF
0x180005fd8  xor     eax, eax
0x180005fda  mov     [rdi+8], ax
0x180005fde  call    cs:__imp__o__errno
0x180005fe4  mov     dword ptr [rax], 16h
0x180005fea  call    _invalid_parameter_noinfo
0x180005fef  mov     rbx, rsi
0x180005ff2  movzx   ecx, word ptr [rdi+8]
0x180005ff6  add     rcx, rbx
0x180005ff9  cmp     rcx, rbp
0x180005ffc  jbe     short loc_180006002
0x180005ffe  xor     al, al
0x180006000  jmp     short loc_18000600B
0x180006002  mov     [rdi+18h], rbx
0x180006006  mov     al, 1
0x180006008  mov     [r14], rcx
0x18000600b  add     rsp, 28h
0x18000600f  pop     r15
0x180006011  pop     r14
0x180006013  pop     rdi
0x180006014  pop     rsi
0x180006015  pop     rbp
0x180006016  pop     rbx
0x180006017  retn
```
