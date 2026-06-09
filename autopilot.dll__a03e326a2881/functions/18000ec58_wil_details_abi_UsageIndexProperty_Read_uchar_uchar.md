# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x18000ec58`
- end: `0x18000ed50`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `248`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000cca4`
- `0x18000f4f4`
- `0x18000f8c8`

## callees

- `0x180005306`
- `0x18000ec58`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ec95`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ecd7`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ed16`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ec95`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ecd7`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ed16`

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
0x18000ec58  push    rbx
0x18000ec5a  push    rbp
0x18000ec5b  push    rsi
0x18000ec5c  push    rdi
0x18000ec5d  push    r14
0x18000ec5f  push    r15
0x18000ec61  sub     rsp, 28h
0x18000ec65  mov     rax, [rdx]
0x18000ec68  xor     r15d, r15d
0x18000ec6b  cmp     byte ptr [rcx+2], 1
0x18000ec6f  mov     rbp, r8
0x18000ec72  mov     r14, rdx
0x18000ec75  mov     rdi, rcx
0x18000ec78  jnz     short loc_18000ECB1
0x18000ec7a  lea     rbx, [rax+2]
0x18000ec7e  cmp     rbx, r8
0x18000ec81  ja      loc_18000ED36
0x18000ec87  mov     [rcx+10h], rax
0x18000ec8b  test    rax, rax
0x18000ec8e  jz      short loc_18000EC95
0x18000ec90  movzx   ecx, word ptr [rax]
0x18000ec93  jmp     short loc_18000ECA9
0x18000ec95  call    cs:__imp__o__errno
0x18000ec9b  mov     dword ptr [rax], 16h
0x18000eca1  call    _invalid_parameter_noinfo
0x18000eca6  mov     ecx, r15d
0x18000eca9  movzx   eax, cx
0x18000ecac  mov     [rdi+4], eax
0x18000ecaf  jmp     short loc_18000ECED
0x18000ecb1  cmp     byte ptr [rcx+2], 2
0x18000ecb5  jnz     short loc_18000ECEA
0x18000ecb7  lea     rbx, [rax+4]
0x18000ecbb  cmp     rbx, rbp
0x18000ecbe  ja      short loc_18000ED36
0x18000ecc0  mov     [rcx+10h], rax
0x18000ecc4  add     rcx, 4
0x18000ecc8  jz      short loc_18000ECD7
0x18000ecca  test    rax, rax
0x18000eccd  jz      short loc_18000ECD5
0x18000eccf  mov     eax, [rax]
0x18000ecd1  mov     [rcx], eax
0x18000ecd3  jmp     short loc_18000ECED
0x18000ecd5  mov     [rcx], eax
0x18000ecd7  call    cs:__imp__o__errno
0x18000ecdd  mov     dword ptr [rax], 16h
0x18000ece3  call    _invalid_parameter_noinfo
0x18000ece8  jmp     short loc_18000ECED
0x18000ecea  mov     rbx, rax
0x18000eced  movzx   eax, word ptr [rdi]
0x18000ecf0  mov     [rdi+8], ax
0x18000ecf4  test    ax, ax
0x18000ecf7  jnz     short loc_18000ED2A
0x18000ecf9  lea     rsi, [rbx+2]
0x18000ecfd  cmp     rsi, rbp
0x18000ed00  ja      short loc_18000ED36
0x18000ed02  test    rbx, rbx
0x18000ed05  jz      short loc_18000ED10
0x18000ed07  movzx   eax, word ptr [rbx]
0x18000ed0a  mov     [rdi+8], ax
0x18000ed0e  jmp     short loc_18000ED27
0x18000ed10  xor     eax, eax
0x18000ed12  mov     [rdi+8], ax
0x18000ed16  call    cs:__imp__o__errno
0x18000ed1c  mov     dword ptr [rax], 16h
0x18000ed22  call    _invalid_parameter_noinfo
0x18000ed27  mov     rbx, rsi
0x18000ed2a  movzx   ecx, word ptr [rdi+8]
0x18000ed2e  add     rcx, rbx
0x18000ed31  cmp     rcx, rbp
0x18000ed34  jbe     short loc_18000ED3A
0x18000ed36  xor     al, al
0x18000ed38  jmp     short loc_18000ED43
0x18000ed3a  mov     [rdi+18h], rbx
0x18000ed3e  mov     al, 1
0x18000ed40  mov     [r14], rcx
0x18000ed43  add     rsp, 28h
0x18000ed47  pop     r15
0x18000ed49  pop     r14
0x18000ed4b  pop     rdi
0x18000ed4c  pop     rsi
0x18000ed4d  pop     rbp
0x18000ed4e  pop     rbx
0x18000ed4f  retn
```
