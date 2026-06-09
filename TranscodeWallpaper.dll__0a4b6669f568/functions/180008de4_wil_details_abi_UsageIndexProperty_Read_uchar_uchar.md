# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180008de4`
- end: `0x180008edc`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `248`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000870c`
- `0x1800093bc`
- `0x180009790`

## callees

- `0x180002c4a`
- `0x180008de4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008e21`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008e63`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008ea2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008e21`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008e63`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180008ea2`

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
0x180008de4  push    rbx
0x180008de6  push    rbp
0x180008de7  push    rsi
0x180008de8  push    rdi
0x180008de9  push    r14
0x180008deb  push    r15
0x180008ded  sub     rsp, 28h
0x180008df1  mov     rax, [rdx]
0x180008df4  xor     r15d, r15d
0x180008df7  cmp     byte ptr [rcx+2], 1
0x180008dfb  mov     rbp, r8
0x180008dfe  mov     r14, rdx
0x180008e01  mov     rdi, rcx
0x180008e04  jnz     short loc_180008E3D
0x180008e06  lea     rbx, [rax+2]
0x180008e0a  cmp     rbx, r8
0x180008e0d  ja      loc_180008EC2
0x180008e13  mov     [rcx+10h], rax
0x180008e17  test    rax, rax
0x180008e1a  jz      short loc_180008E21
0x180008e1c  movzx   ecx, word ptr [rax]
0x180008e1f  jmp     short loc_180008E35
0x180008e21  call    cs:__imp__o__errno
0x180008e27  mov     dword ptr [rax], 16h
0x180008e2d  call    _invalid_parameter_noinfo
0x180008e32  mov     ecx, r15d
0x180008e35  movzx   eax, cx
0x180008e38  mov     [rdi+4], eax
0x180008e3b  jmp     short loc_180008E79
0x180008e3d  cmp     byte ptr [rcx+2], 2
0x180008e41  jnz     short loc_180008E76
0x180008e43  lea     rbx, [rax+4]
0x180008e47  cmp     rbx, rbp
0x180008e4a  ja      short loc_180008EC2
0x180008e4c  mov     [rcx+10h], rax
0x180008e50  add     rcx, 4
0x180008e54  jz      short loc_180008E63
0x180008e56  test    rax, rax
0x180008e59  jz      short loc_180008E61
0x180008e5b  mov     eax, [rax]
0x180008e5d  mov     [rcx], eax
0x180008e5f  jmp     short loc_180008E79
0x180008e61  mov     [rcx], eax
0x180008e63  call    cs:__imp__o__errno
0x180008e69  mov     dword ptr [rax], 16h
0x180008e6f  call    _invalid_parameter_noinfo
0x180008e74  jmp     short loc_180008E79
0x180008e76  mov     rbx, rax
0x180008e79  movzx   eax, word ptr [rdi]
0x180008e7c  mov     [rdi+8], ax
0x180008e80  test    ax, ax
0x180008e83  jnz     short loc_180008EB6
0x180008e85  lea     rsi, [rbx+2]
0x180008e89  cmp     rsi, rbp
0x180008e8c  ja      short loc_180008EC2
0x180008e8e  test    rbx, rbx
0x180008e91  jz      short loc_180008E9C
0x180008e93  movzx   eax, word ptr [rbx]
0x180008e96  mov     [rdi+8], ax
0x180008e9a  jmp     short loc_180008EB3
0x180008e9c  xor     eax, eax
0x180008e9e  mov     [rdi+8], ax
0x180008ea2  call    cs:__imp__o__errno
0x180008ea8  mov     dword ptr [rax], 16h
0x180008eae  call    _invalid_parameter_noinfo
0x180008eb3  mov     rbx, rsi
0x180008eb6  movzx   ecx, word ptr [rdi+8]
0x180008eba  add     rcx, rbx
0x180008ebd  cmp     rcx, rbp
0x180008ec0  jbe     short loc_180008EC6
0x180008ec2  xor     al, al
0x180008ec4  jmp     short loc_180008ECF
0x180008ec6  mov     [rdi+18h], rbx
0x180008eca  mov     al, 1
0x180008ecc  mov     [r14], rcx
0x180008ecf  add     rsp, 28h
0x180008ed3  pop     r15
0x180008ed5  pop     r14
0x180008ed7  pop     rdi
0x180008ed8  pop     rsi
0x180008ed9  pop     rbp
0x180008eda  pop     rbx
0x180008edb  retn
```
