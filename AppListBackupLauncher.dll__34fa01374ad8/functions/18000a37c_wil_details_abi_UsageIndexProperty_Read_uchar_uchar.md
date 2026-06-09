# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x18000a37c`
- end: `0x18000a474`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `248`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180007a1c`
- `0x18000ac08`
- `0x18000afdc`

## callees

- `0x180002d6a`
- `0x18000a37c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a3b9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a3fb`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a43a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a3b9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a3fb`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a43a`

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
0x18000a37c  push    rbx
0x18000a37e  push    rbp
0x18000a37f  push    rsi
0x18000a380  push    rdi
0x18000a381  push    r14
0x18000a383  push    r15
0x18000a385  sub     rsp, 28h
0x18000a389  mov     rax, [rdx]
0x18000a38c  xor     r15d, r15d
0x18000a38f  cmp     byte ptr [rcx+2], 1
0x18000a393  mov     rbp, r8
0x18000a396  mov     r14, rdx
0x18000a399  mov     rdi, rcx
0x18000a39c  jnz     short loc_18000A3D5
0x18000a39e  lea     rbx, [rax+2]
0x18000a3a2  cmp     rbx, r8
0x18000a3a5  ja      loc_18000A45A
0x18000a3ab  mov     [rcx+10h], rax
0x18000a3af  test    rax, rax
0x18000a3b2  jz      short loc_18000A3B9
0x18000a3b4  movzx   ecx, word ptr [rax]
0x18000a3b7  jmp     short loc_18000A3CD
0x18000a3b9  call    cs:__imp__o__errno
0x18000a3bf  mov     dword ptr [rax], 16h
0x18000a3c5  call    _invalid_parameter_noinfo
0x18000a3ca  mov     ecx, r15d
0x18000a3cd  movzx   eax, cx
0x18000a3d0  mov     [rdi+4], eax
0x18000a3d3  jmp     short loc_18000A411
0x18000a3d5  cmp     byte ptr [rcx+2], 2
0x18000a3d9  jnz     short loc_18000A40E
0x18000a3db  lea     rbx, [rax+4]
0x18000a3df  cmp     rbx, rbp
0x18000a3e2  ja      short loc_18000A45A
0x18000a3e4  mov     [rcx+10h], rax
0x18000a3e8  add     rcx, 4
0x18000a3ec  jz      short loc_18000A3FB
0x18000a3ee  test    rax, rax
0x18000a3f1  jz      short loc_18000A3F9
0x18000a3f3  mov     eax, [rax]
0x18000a3f5  mov     [rcx], eax
0x18000a3f7  jmp     short loc_18000A411
0x18000a3f9  mov     [rcx], eax
0x18000a3fb  call    cs:__imp__o__errno
0x18000a401  mov     dword ptr [rax], 16h
0x18000a407  call    _invalid_parameter_noinfo
0x18000a40c  jmp     short loc_18000A411
0x18000a40e  mov     rbx, rax
0x18000a411  movzx   eax, word ptr [rdi]
0x18000a414  mov     [rdi+8], ax
0x18000a418  test    ax, ax
0x18000a41b  jnz     short loc_18000A44E
0x18000a41d  lea     rsi, [rbx+2]
0x18000a421  cmp     rsi, rbp
0x18000a424  ja      short loc_18000A45A
0x18000a426  test    rbx, rbx
0x18000a429  jz      short loc_18000A434
0x18000a42b  movzx   eax, word ptr [rbx]
0x18000a42e  mov     [rdi+8], ax
0x18000a432  jmp     short loc_18000A44B
0x18000a434  xor     eax, eax
0x18000a436  mov     [rdi+8], ax
0x18000a43a  call    cs:__imp__o__errno
0x18000a440  mov     dword ptr [rax], 16h
0x18000a446  call    _invalid_parameter_noinfo
0x18000a44b  mov     rbx, rsi
0x18000a44e  movzx   ecx, word ptr [rdi+8]
0x18000a452  add     rcx, rbx
0x18000a455  cmp     rcx, rbp
0x18000a458  jbe     short loc_18000A45E
0x18000a45a  xor     al, al
0x18000a45c  jmp     short loc_18000A467
0x18000a45e  mov     [rdi+18h], rbx
0x18000a462  mov     al, 1
0x18000a464  mov     [r14], rcx
0x18000a467  add     rsp, 28h
0x18000a46b  pop     r15
0x18000a46d  pop     r14
0x18000a46f  pop     rdi
0x18000a470  pop     rsi
0x18000a471  pop     rbp
0x18000a472  pop     rbx
0x18000a473  retn
```
