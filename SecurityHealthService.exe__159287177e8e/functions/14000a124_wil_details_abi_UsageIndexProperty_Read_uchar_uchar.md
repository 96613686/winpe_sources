# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x14000a124`
- end: `0x14000a21f`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `251`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14000937c`
- `0x14000a728`
- `0x14000ab00`

## callees

- `0x14000a124`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x14000a16d`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x14000a1b0`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x14000a1f0`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x14000a16d`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x14000a1b0`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x14000a1f0`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x14000a161`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x14000a1a4`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x14000a1e4`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x14000a161`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x14000a1a4`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x14000a1e4`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Read(
        wil::details_abi::UsageIndexProperty *this,
        unsigned __int8 **a2,
        unsigned __int8 *a3)
{
  unsigned __int16 *v3; // rax
  unsigned __int16 *v7; // rbx
  unsigned __int16 v8; // cx
  _DWORD *v9; // rcx
  __int16 v10; // ax
  unsigned __int8 *v11; // rcx
  bool result; // al

  v3 = (unsigned __int16 *)*a2;
  if ( *((_BYTE *)this + 2) == 1 )
  {
    v7 = v3 + 1;
    if ( v3 + 1 > (unsigned __int16 *)a3 )
      return 0;
    *((_QWORD *)this + 2) = v3;
    if ( v3 )
    {
      v8 = *v3;
    }
    else
    {
      *_errno() = 22;
      _invalid_parameter_noinfo();
      v8 = 0;
    }
    *((_DWORD *)this + 1) = v8;
  }
  else if ( *((_BYTE *)this + 2) == 2 )
  {
    v7 = v3 + 2;
    if ( v3 + 2 > (unsigned __int16 *)a3 )
      return 0;
    *((_QWORD *)this + 2) = v3;
    v9 = (_DWORD *)((char *)this + 4);
    if ( v9 )
    {
      if ( v3 )
      {
        *v9 = *(_DWORD *)v3;
        goto LABEL_15;
      }
      *v9 = 0;
    }
    *_errno() = 22;
    _invalid_parameter_noinfo();
  }
  else
  {
    v7 = (unsigned __int16 *)*a2;
  }
LABEL_15:
  v10 = *(_WORD *)this;
  *((_WORD *)this + 4) = *(_WORD *)this;
  if ( v10 )
    goto LABEL_21;
  if ( v7 + 1 > (unsigned __int16 *)a3 )
    return 0;
  if ( v7 )
  {
    *((_WORD *)this + 4) = *v7;
  }
  else
  {
    *((_WORD *)this + 4) = 0;
    *_errno() = 22;
    _invalid_parameter_noinfo();
  }
  ++v7;
LABEL_21:
  v11 = (unsigned __int8 *)v7 + *((unsigned __int16 *)this + 4);
  if ( v11 > a3 )
    return 0;
  *((_QWORD *)this + 3) = v7;
  result = 1;
  *a2 = v11;
  return result;
}

```

## disassembly

```asm
0x14000a124  push    rbx
0x14000a126  push    rbp
0x14000a127  push    rsi
0x14000a128  push    rdi
0x14000a129  push    r14
0x14000a12b  push    r15
0x14000a12d  sub     rsp, 28h
0x14000a131  mov     rax, [rdx]
0x14000a134  xor     r15d, r15d
0x14000a137  cmp     byte ptr [rcx+2], 1
0x14000a13b  mov     rbp, r8
0x14000a13e  mov     r14, rdx
0x14000a141  mov     rdi, rcx
0x14000a144  jnz     short loc_14000A17E
0x14000a146  lea     rbx, [rax+2]
0x14000a14a  cmp     rbx, r8
0x14000a14d  ja      loc_14000A205
0x14000a153  mov     [rcx+10h], rax
0x14000a157  test    rax, rax
0x14000a15a  jz      short loc_14000A161
0x14000a15c  movzx   ecx, word ptr [rax]
0x14000a15f  jmp     short loc_14000A176
0x14000a161  call    cs:__imp__errno
0x14000a167  mov     dword ptr [rax], 16h
0x14000a16d  call    cs:__imp__invalid_parameter_noinfo
0x14000a173  mov     ecx, r15d
0x14000a176  movzx   eax, cx
0x14000a179  mov     [rdi+4], eax
0x14000a17c  jmp     short loc_14000A1BB
0x14000a17e  cmp     byte ptr [rcx+2], 2
0x14000a182  jnz     short loc_14000A1B8
0x14000a184  lea     rbx, [rax+4]
0x14000a188  cmp     rbx, rbp
0x14000a18b  ja      short loc_14000A205
0x14000a18d  mov     [rcx+10h], rax
0x14000a191  add     rcx, 4
0x14000a195  jz      short loc_14000A1A4
0x14000a197  test    rax, rax
0x14000a19a  jz      short loc_14000A1A2
0x14000a19c  mov     eax, [rax]
0x14000a19e  mov     [rcx], eax
0x14000a1a0  jmp     short loc_14000A1BB
0x14000a1a2  mov     [rcx], eax
0x14000a1a4  call    cs:__imp__errno
0x14000a1aa  mov     dword ptr [rax], 16h
0x14000a1b0  call    cs:__imp__invalid_parameter_noinfo
0x14000a1b6  jmp     short loc_14000A1BB
0x14000a1b8  mov     rbx, rax
0x14000a1bb  movzx   eax, word ptr [rdi]
0x14000a1be  mov     [rdi+8], ax
0x14000a1c2  test    ax, ax
0x14000a1c5  jnz     short loc_14000A1F9
0x14000a1c7  lea     rsi, [rbx+2]
0x14000a1cb  cmp     rsi, rbp
0x14000a1ce  ja      short loc_14000A205
0x14000a1d0  test    rbx, rbx
0x14000a1d3  jz      short loc_14000A1DE
0x14000a1d5  movzx   eax, word ptr [rbx]
0x14000a1d8  mov     [rdi+8], ax
0x14000a1dc  jmp     short loc_14000A1F6
0x14000a1de  xor     eax, eax
0x14000a1e0  mov     [rdi+8], ax
0x14000a1e4  call    cs:__imp__errno
0x14000a1ea  mov     dword ptr [rax], 16h
0x14000a1f0  call    cs:__imp__invalid_parameter_noinfo
0x14000a1f6  mov     rbx, rsi
0x14000a1f9  movzx   ecx, word ptr [rdi+8]
0x14000a1fd  add     rcx, rbx
0x14000a200  cmp     rcx, rbp
0x14000a203  jbe     short loc_14000A209
0x14000a205  xor     al, al
0x14000a207  jmp     short loc_14000A212
0x14000a209  mov     [rdi+18h], rbx
0x14000a20d  mov     al, 1
0x14000a20f  mov     [r14], rcx
0x14000a212  add     rsp, 28h
0x14000a216  pop     r15
0x14000a218  pop     r14
0x14000a21a  pop     rdi
0x14000a21b  pop     rsi
0x14000a21c  pop     rbp
0x14000a21d  pop     rbx
0x14000a21e  retn
```
