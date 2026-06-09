# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x18000cda4`
- end: `0x18000ce9c`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `248`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b39c`
- `0x18000d5e8`
- `0x18000d9bc`

## callees

- `0x180003392`
- `0x18000cda4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000cde1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ce23`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ce62`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000cde1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ce23`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ce62`

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
0x18000cda4  push    rbx
0x18000cda6  push    rbp
0x18000cda7  push    rsi
0x18000cda8  push    rdi
0x18000cda9  push    r14
0x18000cdab  push    r15
0x18000cdad  sub     rsp, 28h
0x18000cdb1  mov     rax, [rdx]
0x18000cdb4  xor     r15d, r15d
0x18000cdb7  cmp     byte ptr [rcx+2], 1
0x18000cdbb  mov     rbp, r8
0x18000cdbe  mov     r14, rdx
0x18000cdc1  mov     rdi, rcx
0x18000cdc4  jnz     short loc_18000CDFD
0x18000cdc6  lea     rbx, [rax+2]
0x18000cdca  cmp     rbx, r8
0x18000cdcd  ja      loc_18000CE82
0x18000cdd3  mov     [rcx+10h], rax
0x18000cdd7  test    rax, rax
0x18000cdda  jz      short loc_18000CDE1
0x18000cddc  movzx   ecx, word ptr [rax]
0x18000cddf  jmp     short loc_18000CDF5
0x18000cde1  call    cs:__imp__o__errno
0x18000cde7  mov     dword ptr [rax], 16h
0x18000cded  call    _invalid_parameter_noinfo
0x18000cdf2  mov     ecx, r15d
0x18000cdf5  movzx   eax, cx
0x18000cdf8  mov     [rdi+4], eax
0x18000cdfb  jmp     short loc_18000CE39
0x18000cdfd  cmp     byte ptr [rcx+2], 2
0x18000ce01  jnz     short loc_18000CE36
0x18000ce03  lea     rbx, [rax+4]
0x18000ce07  cmp     rbx, rbp
0x18000ce0a  ja      short loc_18000CE82
0x18000ce0c  mov     [rcx+10h], rax
0x18000ce10  add     rcx, 4
0x18000ce14  jz      short loc_18000CE23
0x18000ce16  test    rax, rax
0x18000ce19  jz      short loc_18000CE21
0x18000ce1b  mov     eax, [rax]
0x18000ce1d  mov     [rcx], eax
0x18000ce1f  jmp     short loc_18000CE39
0x18000ce21  mov     [rcx], eax
0x18000ce23  call    cs:__imp__o__errno
0x18000ce29  mov     dword ptr [rax], 16h
0x18000ce2f  call    _invalid_parameter_noinfo
0x18000ce34  jmp     short loc_18000CE39
0x18000ce36  mov     rbx, rax
0x18000ce39  movzx   eax, word ptr [rdi]
0x18000ce3c  mov     [rdi+8], ax
0x18000ce40  test    ax, ax
0x18000ce43  jnz     short loc_18000CE76
0x18000ce45  lea     rsi, [rbx+2]
0x18000ce49  cmp     rsi, rbp
0x18000ce4c  ja      short loc_18000CE82
0x18000ce4e  test    rbx, rbx
0x18000ce51  jz      short loc_18000CE5C
0x18000ce53  movzx   eax, word ptr [rbx]
0x18000ce56  mov     [rdi+8], ax
0x18000ce5a  jmp     short loc_18000CE73
0x18000ce5c  xor     eax, eax
0x18000ce5e  mov     [rdi+8], ax
0x18000ce62  call    cs:__imp__o__errno
0x18000ce68  mov     dword ptr [rax], 16h
0x18000ce6e  call    _invalid_parameter_noinfo
0x18000ce73  mov     rbx, rsi
0x18000ce76  movzx   ecx, word ptr [rdi+8]
0x18000ce7a  add     rcx, rbx
0x18000ce7d  cmp     rcx, rbp
0x18000ce80  jbe     short loc_18000CE86
0x18000ce82  xor     al, al
0x18000ce84  jmp     short loc_18000CE8F
0x18000ce86  mov     [rdi+18h], rbx
0x18000ce8a  mov     al, 1
0x18000ce8c  mov     [r14], rcx
0x18000ce8f  add     rsp, 28h
0x18000ce93  pop     r15
0x18000ce95  pop     r14
0x18000ce97  pop     rdi
0x18000ce98  pop     rsi
0x18000ce99  pop     rbp
0x18000ce9a  pop     rbx
0x18000ce9b  retn
```
