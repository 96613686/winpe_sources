# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x14000d308`
- end: `0x14000d400`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `248`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14000cbdc`
- `0x14000d8f0`
- `0x14000dcc4`

## callees

- `0x1400035ea`
- `0x14000d308`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000d345`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000d387`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000d3c6`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000d345`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000d387`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000d3c6`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Read(
        wil::details_abi::UsageIndexProperty *this,
        unsigned __int8 **a2,
        unsigned __int8 *a3)
{
  _DWORD *v3; // rax
  wil::details_abi::UsageIndexProperty *v6; // rdi
  _WORD *v7; // rbx
  __int16 v8; // ax
  unsigned __int8 *v9; // rcx
  bool result; // al

  v3 = *a2;
  v6 = this;
  if ( *((_BYTE *)this + 2) == 1 )
  {
    v7 = (_WORD *)v3 + 1;
    if ( (unsigned __int8 *)((char *)v3 + 2) > a3 )
      return 0;
    *((_QWORD *)this + 2) = v3;
    if ( v3 )
    {
      this = (wil::details_abi::UsageIndexProperty *)*(unsigned __int16 *)v3;
    }
    else
    {
      *(_DWORD *)_o__errno(this) = 22;
      invalid_parameter_noinfo();
      this = 0;
    }
    *((_DWORD *)v6 + 1) = (unsigned __int16)this;
  }
  else if ( *((_BYTE *)this + 2) == 2 )
  {
    v7 = v3 + 1;
    if ( v3 + 1 > (_DWORD *)a3 )
      return 0;
    *((_QWORD *)this + 2) = v3;
    this = (wil::details_abi::UsageIndexProperty *)((char *)this + 4);
    if ( this )
    {
      if ( v3 )
      {
        *(_DWORD *)this = *v3;
        goto LABEL_15;
      }
      *(_DWORD *)this = 0;
    }
    *(_DWORD *)_o__errno(this) = 22;
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
  if ( v7 + 1 > (_WORD *)a3 )
    return 0;
  if ( v7 )
  {
    *((_WORD *)v6 + 4) = *v7;
  }
  else
  {
    *((_WORD *)v6 + 4) = 0;
    *(_DWORD *)_o__errno(this) = 22;
    invalid_parameter_noinfo();
  }
  ++v7;
LABEL_21:
  v9 = (unsigned __int8 *)v7 + *((unsigned __int16 *)v6 + 4);
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
0x14000d308  push    rbx
0x14000d30a  push    rbp
0x14000d30b  push    rsi
0x14000d30c  push    rdi
0x14000d30d  push    r14
0x14000d30f  push    r15
0x14000d311  sub     rsp, 28h
0x14000d315  mov     rax, [rdx]
0x14000d318  xor     r15d, r15d
0x14000d31b  cmp     byte ptr [rcx+2], 1
0x14000d31f  mov     rbp, r8
0x14000d322  mov     r14, rdx
0x14000d325  mov     rdi, rcx
0x14000d328  jnz     short loc_14000D361
0x14000d32a  lea     rbx, [rax+2]
0x14000d32e  cmp     rbx, r8
0x14000d331  ja      loc_14000D3E6
0x14000d337  mov     [rcx+10h], rax
0x14000d33b  test    rax, rax
0x14000d33e  jz      short loc_14000D345
0x14000d340  movzx   ecx, word ptr [rax]
0x14000d343  jmp     short loc_14000D359
0x14000d345  call    cs:__imp__o__errno
0x14000d34b  mov     dword ptr [rax], 16h
0x14000d351  call    _invalid_parameter_noinfo
0x14000d356  mov     ecx, r15d
0x14000d359  movzx   eax, cx
0x14000d35c  mov     [rdi+4], eax
0x14000d35f  jmp     short loc_14000D39D
0x14000d361  cmp     byte ptr [rcx+2], 2
0x14000d365  jnz     short loc_14000D39A
0x14000d367  lea     rbx, [rax+4]
0x14000d36b  cmp     rbx, rbp
0x14000d36e  ja      short loc_14000D3E6
0x14000d370  mov     [rcx+10h], rax
0x14000d374  add     rcx, 4
0x14000d378  jz      short loc_14000D387
0x14000d37a  test    rax, rax
0x14000d37d  jz      short loc_14000D385
0x14000d37f  mov     eax, [rax]
0x14000d381  mov     [rcx], eax
0x14000d383  jmp     short loc_14000D39D
0x14000d385  mov     [rcx], eax
0x14000d387  call    cs:__imp__o__errno
0x14000d38d  mov     dword ptr [rax], 16h
0x14000d393  call    _invalid_parameter_noinfo
0x14000d398  jmp     short loc_14000D39D
0x14000d39a  mov     rbx, rax
0x14000d39d  movzx   eax, word ptr [rdi]
0x14000d3a0  mov     [rdi+8], ax
0x14000d3a4  test    ax, ax
0x14000d3a7  jnz     short loc_14000D3DA
0x14000d3a9  lea     rsi, [rbx+2]
0x14000d3ad  cmp     rsi, rbp
0x14000d3b0  ja      short loc_14000D3E6
0x14000d3b2  test    rbx, rbx
0x14000d3b5  jz      short loc_14000D3C0
0x14000d3b7  movzx   eax, word ptr [rbx]
0x14000d3ba  mov     [rdi+8], ax
0x14000d3be  jmp     short loc_14000D3D7
0x14000d3c0  xor     eax, eax
0x14000d3c2  mov     [rdi+8], ax
0x14000d3c6  call    cs:__imp__o__errno
0x14000d3cc  mov     dword ptr [rax], 16h
0x14000d3d2  call    _invalid_parameter_noinfo
0x14000d3d7  mov     rbx, rsi
0x14000d3da  movzx   ecx, word ptr [rdi+8]
0x14000d3de  add     rcx, rbx
0x14000d3e1  cmp     rcx, rbp
0x14000d3e4  jbe     short loc_14000D3EA
0x14000d3e6  xor     al, al
0x14000d3e8  jmp     short loc_14000D3F3
0x14000d3ea  mov     [rdi+18h], rbx
0x14000d3ee  mov     al, 1
0x14000d3f0  mov     [r14], rcx
0x14000d3f3  add     rsp, 28h
0x14000d3f7  pop     r15
0x14000d3f9  pop     r14
0x14000d3fb  pop     rdi
0x14000d3fc  pop     rsi
0x14000d3fd  pop     rbp
0x14000d3fe  pop     rbx
0x14000d3ff  retn
```
