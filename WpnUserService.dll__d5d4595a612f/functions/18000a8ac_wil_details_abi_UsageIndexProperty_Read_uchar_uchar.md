# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x18000a8ac`
- end: `0x18000a9a4`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `248`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000952c`
- `0x18000ae90`
- `0x18000b264`

## callees

- `0x1800034fe`
- `0x18000a8ac`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a8e9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a92b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a96a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a8e9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a92b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a96a`

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
0x18000a8ac  push    rbx
0x18000a8ae  push    rbp
0x18000a8af  push    rsi
0x18000a8b0  push    rdi
0x18000a8b1  push    r14
0x18000a8b3  push    r15
0x18000a8b5  sub     rsp, 28h
0x18000a8b9  mov     rax, [rdx]
0x18000a8bc  xor     r15d, r15d
0x18000a8bf  cmp     byte ptr [rcx+2], 1
0x18000a8c3  mov     rbp, r8
0x18000a8c6  mov     r14, rdx
0x18000a8c9  mov     rdi, rcx
0x18000a8cc  jnz     short loc_18000A905
0x18000a8ce  lea     rbx, [rax+2]
0x18000a8d2  cmp     rbx, r8
0x18000a8d5  ja      loc_18000A98A
0x18000a8db  mov     [rcx+10h], rax
0x18000a8df  test    rax, rax
0x18000a8e2  jz      short loc_18000A8E9
0x18000a8e4  movzx   ecx, word ptr [rax]
0x18000a8e7  jmp     short loc_18000A8FD
0x18000a8e9  call    cs:__imp__o__errno
0x18000a8ef  mov     dword ptr [rax], 16h
0x18000a8f5  call    _invalid_parameter_noinfo
0x18000a8fa  mov     ecx, r15d
0x18000a8fd  movzx   eax, cx
0x18000a900  mov     [rdi+4], eax
0x18000a903  jmp     short loc_18000A941
0x18000a905  cmp     byte ptr [rcx+2], 2
0x18000a909  jnz     short loc_18000A93E
0x18000a90b  lea     rbx, [rax+4]
0x18000a90f  cmp     rbx, rbp
0x18000a912  ja      short loc_18000A98A
0x18000a914  mov     [rcx+10h], rax
0x18000a918  add     rcx, 4
0x18000a91c  jz      short loc_18000A92B
0x18000a91e  test    rax, rax
0x18000a921  jz      short loc_18000A929
0x18000a923  mov     eax, [rax]
0x18000a925  mov     [rcx], eax
0x18000a927  jmp     short loc_18000A941
0x18000a929  mov     [rcx], eax
0x18000a92b  call    cs:__imp__o__errno
0x18000a931  mov     dword ptr [rax], 16h
0x18000a937  call    _invalid_parameter_noinfo
0x18000a93c  jmp     short loc_18000A941
0x18000a93e  mov     rbx, rax
0x18000a941  movzx   eax, word ptr [rdi]
0x18000a944  mov     [rdi+8], ax
0x18000a948  test    ax, ax
0x18000a94b  jnz     short loc_18000A97E
0x18000a94d  lea     rsi, [rbx+2]
0x18000a951  cmp     rsi, rbp
0x18000a954  ja      short loc_18000A98A
0x18000a956  test    rbx, rbx
0x18000a959  jz      short loc_18000A964
0x18000a95b  movzx   eax, word ptr [rbx]
0x18000a95e  mov     [rdi+8], ax
0x18000a962  jmp     short loc_18000A97B
0x18000a964  xor     eax, eax
0x18000a966  mov     [rdi+8], ax
0x18000a96a  call    cs:__imp__o__errno
0x18000a970  mov     dword ptr [rax], 16h
0x18000a976  call    _invalid_parameter_noinfo
0x18000a97b  mov     rbx, rsi
0x18000a97e  movzx   ecx, word ptr [rdi+8]
0x18000a982  add     rcx, rbx
0x18000a985  cmp     rcx, rbp
0x18000a988  jbe     short loc_18000A98E
0x18000a98a  xor     al, al
0x18000a98c  jmp     short loc_18000A997
0x18000a98e  mov     [rdi+18h], rbx
0x18000a992  mov     al, 1
0x18000a994  mov     [r14], rcx
0x18000a997  add     rsp, 28h
0x18000a99b  pop     r15
0x18000a99d  pop     r14
0x18000a99f  pop     rdi
0x18000a9a0  pop     rsi
0x18000a9a1  pop     rbp
0x18000a9a2  pop     rbx
0x18000a9a3  retn
```
