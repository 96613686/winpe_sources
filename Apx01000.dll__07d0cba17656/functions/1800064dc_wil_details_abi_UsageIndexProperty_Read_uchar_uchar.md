# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x1800064dc`
- end: `0x1800065d4`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `248`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180004c10`
- `0x180006d28`
- `0x1800070fc`

## callees

- `0x180002766`
- `0x1800064dc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006519`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000655b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000659a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006519`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000655b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000659a`

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
0x1800064dc  push    rbx
0x1800064de  push    rbp
0x1800064df  push    rsi
0x1800064e0  push    rdi
0x1800064e1  push    r14
0x1800064e3  push    r15
0x1800064e5  sub     rsp, 28h
0x1800064e9  mov     rax, [rdx]
0x1800064ec  xor     r15d, r15d
0x1800064ef  cmp     byte ptr [rcx+2], 1
0x1800064f3  mov     rbp, r8
0x1800064f6  mov     r14, rdx
0x1800064f9  mov     rdi, rcx
0x1800064fc  jnz     short loc_180006535
0x1800064fe  lea     rbx, [rax+2]
0x180006502  cmp     rbx, r8
0x180006505  ja      loc_1800065BA
0x18000650b  mov     [rcx+10h], rax
0x18000650f  test    rax, rax
0x180006512  jz      short loc_180006519
0x180006514  movzx   ecx, word ptr [rax]
0x180006517  jmp     short loc_18000652D
0x180006519  call    cs:__imp__o__errno
0x18000651f  mov     dword ptr [rax], 16h
0x180006525  call    _invalid_parameter_noinfo
0x18000652a  mov     ecx, r15d
0x18000652d  movzx   eax, cx
0x180006530  mov     [rdi+4], eax
0x180006533  jmp     short loc_180006571
0x180006535  cmp     byte ptr [rcx+2], 2
0x180006539  jnz     short loc_18000656E
0x18000653b  lea     rbx, [rax+4]
0x18000653f  cmp     rbx, rbp
0x180006542  ja      short loc_1800065BA
0x180006544  mov     [rcx+10h], rax
0x180006548  add     rcx, 4
0x18000654c  jz      short loc_18000655B
0x18000654e  test    rax, rax
0x180006551  jz      short loc_180006559
0x180006553  mov     eax, [rax]
0x180006555  mov     [rcx], eax
0x180006557  jmp     short loc_180006571
0x180006559  mov     [rcx], eax
0x18000655b  call    cs:__imp__o__errno
0x180006561  mov     dword ptr [rax], 16h
0x180006567  call    _invalid_parameter_noinfo
0x18000656c  jmp     short loc_180006571
0x18000656e  mov     rbx, rax
0x180006571  movzx   eax, word ptr [rdi]
0x180006574  mov     [rdi+8], ax
0x180006578  test    ax, ax
0x18000657b  jnz     short loc_1800065AE
0x18000657d  lea     rsi, [rbx+2]
0x180006581  cmp     rsi, rbp
0x180006584  ja      short loc_1800065BA
0x180006586  test    rbx, rbx
0x180006589  jz      short loc_180006594
0x18000658b  movzx   eax, word ptr [rbx]
0x18000658e  mov     [rdi+8], ax
0x180006592  jmp     short loc_1800065AB
0x180006594  xor     eax, eax
0x180006596  mov     [rdi+8], ax
0x18000659a  call    cs:__imp__o__errno
0x1800065a0  mov     dword ptr [rax], 16h
0x1800065a6  call    _invalid_parameter_noinfo
0x1800065ab  mov     rbx, rsi
0x1800065ae  movzx   ecx, word ptr [rdi+8]
0x1800065b2  add     rcx, rbx
0x1800065b5  cmp     rcx, rbp
0x1800065b8  jbe     short loc_1800065BE
0x1800065ba  xor     al, al
0x1800065bc  jmp     short loc_1800065C7
0x1800065be  mov     [rdi+18h], rbx
0x1800065c2  mov     al, 1
0x1800065c4  mov     [r14], rcx
0x1800065c7  add     rsp, 28h
0x1800065cb  pop     r15
0x1800065cd  pop     r14
0x1800065cf  pop     rdi
0x1800065d0  pop     rsi
0x1800065d1  pop     rbp
0x1800065d2  pop     rbx
0x1800065d3  retn
```
