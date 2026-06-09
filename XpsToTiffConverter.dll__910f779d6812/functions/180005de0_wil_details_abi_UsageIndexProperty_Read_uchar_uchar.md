# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180005de0`
- end: `0x180005ed8`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `248`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800046ac`
- `0x180006468`
- `0x18000683c`

## callees

- `0x18000207a`
- `0x180005de0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005e1d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005e5f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005e9e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005e1d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005e5f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005e9e`

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
0x180005de0  push    rbx
0x180005de2  push    rbp
0x180005de3  push    rsi
0x180005de4  push    rdi
0x180005de5  push    r14
0x180005de7  push    r15
0x180005de9  sub     rsp, 28h
0x180005ded  mov     rax, [rdx]
0x180005df0  xor     r15d, r15d
0x180005df3  cmp     byte ptr [rcx+2], 1
0x180005df7  mov     rbp, r8
0x180005dfa  mov     r14, rdx
0x180005dfd  mov     rdi, rcx
0x180005e00  jnz     short loc_180005E39
0x180005e02  lea     rbx, [rax+2]
0x180005e06  cmp     rbx, r8
0x180005e09  ja      loc_180005EBE
0x180005e0f  mov     [rcx+10h], rax
0x180005e13  test    rax, rax
0x180005e16  jz      short loc_180005E1D
0x180005e18  movzx   ecx, word ptr [rax]
0x180005e1b  jmp     short loc_180005E31
0x180005e1d  call    cs:__imp__o__errno
0x180005e23  mov     dword ptr [rax], 16h
0x180005e29  call    _invalid_parameter_noinfo
0x180005e2e  mov     ecx, r15d
0x180005e31  movzx   eax, cx
0x180005e34  mov     [rdi+4], eax
0x180005e37  jmp     short loc_180005E75
0x180005e39  cmp     byte ptr [rcx+2], 2
0x180005e3d  jnz     short loc_180005E72
0x180005e3f  lea     rbx, [rax+4]
0x180005e43  cmp     rbx, rbp
0x180005e46  ja      short loc_180005EBE
0x180005e48  mov     [rcx+10h], rax
0x180005e4c  add     rcx, 4
0x180005e50  jz      short loc_180005E5F
0x180005e52  test    rax, rax
0x180005e55  jz      short loc_180005E5D
0x180005e57  mov     eax, [rax]
0x180005e59  mov     [rcx], eax
0x180005e5b  jmp     short loc_180005E75
0x180005e5d  mov     [rcx], eax
0x180005e5f  call    cs:__imp__o__errno
0x180005e65  mov     dword ptr [rax], 16h
0x180005e6b  call    _invalid_parameter_noinfo
0x180005e70  jmp     short loc_180005E75
0x180005e72  mov     rbx, rax
0x180005e75  movzx   eax, word ptr [rdi]
0x180005e78  mov     [rdi+8], ax
0x180005e7c  test    ax, ax
0x180005e7f  jnz     short loc_180005EB2
0x180005e81  lea     rsi, [rbx+2]
0x180005e85  cmp     rsi, rbp
0x180005e88  ja      short loc_180005EBE
0x180005e8a  test    rbx, rbx
0x180005e8d  jz      short loc_180005E98
0x180005e8f  movzx   eax, word ptr [rbx]
0x180005e92  mov     [rdi+8], ax
0x180005e96  jmp     short loc_180005EAF
0x180005e98  xor     eax, eax
0x180005e9a  mov     [rdi+8], ax
0x180005e9e  call    cs:__imp__o__errno
0x180005ea4  mov     dword ptr [rax], 16h
0x180005eaa  call    _invalid_parameter_noinfo
0x180005eaf  mov     rbx, rsi
0x180005eb2  movzx   ecx, word ptr [rdi+8]
0x180005eb6  add     rcx, rbx
0x180005eb9  cmp     rcx, rbp
0x180005ebc  jbe     short loc_180005EC2
0x180005ebe  xor     al, al
0x180005ec0  jmp     short loc_180005ECB
0x180005ec2  mov     [rdi+18h], rbx
0x180005ec6  mov     al, 1
0x180005ec8  mov     [r14], rcx
0x180005ecb  add     rsp, 28h
0x180005ecf  pop     r15
0x180005ed1  pop     r14
0x180005ed3  pop     rdi
0x180005ed4  pop     rsi
0x180005ed5  pop     rbp
0x180005ed6  pop     rbx
0x180005ed7  retn
```
