# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x180006644`
- end: `0x18000673c`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `248`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800047e0`
- `0x180006e74`
- `0x180007248`

## callees

- `0x180001f32`
- `0x180006644`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006681`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800066c3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006702`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006681`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800066c3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006702`

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
0x180006644  push    rbx
0x180006646  push    rbp
0x180006647  push    rsi
0x180006648  push    rdi
0x180006649  push    r14
0x18000664b  push    r15
0x18000664d  sub     rsp, 28h
0x180006651  mov     rax, [rdx]
0x180006654  xor     r15d, r15d
0x180006657  cmp     byte ptr [rcx+2], 1
0x18000665b  mov     rbp, r8
0x18000665e  mov     r14, rdx
0x180006661  mov     rdi, rcx
0x180006664  jnz     short loc_18000669D
0x180006666  lea     rbx, [rax+2]
0x18000666a  cmp     rbx, r8
0x18000666d  ja      loc_180006722
0x180006673  mov     [rcx+10h], rax
0x180006677  test    rax, rax
0x18000667a  jz      short loc_180006681
0x18000667c  movzx   ecx, word ptr [rax]
0x18000667f  jmp     short loc_180006695
0x180006681  call    cs:__imp__o__errno
0x180006687  mov     dword ptr [rax], 16h
0x18000668d  call    _invalid_parameter_noinfo
0x180006692  mov     ecx, r15d
0x180006695  movzx   eax, cx
0x180006698  mov     [rdi+4], eax
0x18000669b  jmp     short loc_1800066D9
0x18000669d  cmp     byte ptr [rcx+2], 2
0x1800066a1  jnz     short loc_1800066D6
0x1800066a3  lea     rbx, [rax+4]
0x1800066a7  cmp     rbx, rbp
0x1800066aa  ja      short loc_180006722
0x1800066ac  mov     [rcx+10h], rax
0x1800066b0  add     rcx, 4
0x1800066b4  jz      short loc_1800066C3
0x1800066b6  test    rax, rax
0x1800066b9  jz      short loc_1800066C1
0x1800066bb  mov     eax, [rax]
0x1800066bd  mov     [rcx], eax
0x1800066bf  jmp     short loc_1800066D9
0x1800066c1  mov     [rcx], eax
0x1800066c3  call    cs:__imp__o__errno
0x1800066c9  mov     dword ptr [rax], 16h
0x1800066cf  call    _invalid_parameter_noinfo
0x1800066d4  jmp     short loc_1800066D9
0x1800066d6  mov     rbx, rax
0x1800066d9  movzx   eax, word ptr [rdi]
0x1800066dc  mov     [rdi+8], ax
0x1800066e0  test    ax, ax
0x1800066e3  jnz     short loc_180006716
0x1800066e5  lea     rsi, [rbx+2]
0x1800066e9  cmp     rsi, rbp
0x1800066ec  ja      short loc_180006722
0x1800066ee  test    rbx, rbx
0x1800066f1  jz      short loc_1800066FC
0x1800066f3  movzx   eax, word ptr [rbx]
0x1800066f6  mov     [rdi+8], ax
0x1800066fa  jmp     short loc_180006713
0x1800066fc  xor     eax, eax
0x1800066fe  mov     [rdi+8], ax
0x180006702  call    cs:__imp__o__errno
0x180006708  mov     dword ptr [rax], 16h
0x18000670e  call    _invalid_parameter_noinfo
0x180006713  mov     rbx, rsi
0x180006716  movzx   ecx, word ptr [rdi+8]
0x18000671a  add     rcx, rbx
0x18000671d  cmp     rcx, rbp
0x180006720  jbe     short loc_180006726
0x180006722  xor     al, al
0x180006724  jmp     short loc_18000672F
0x180006726  mov     [rdi+18h], rbx
0x18000672a  mov     al, 1
0x18000672c  mov     [r14], rcx
0x18000672f  add     rsp, 28h
0x180006733  pop     r15
0x180006735  pop     r14
0x180006737  pop     rdi
0x180006738  pop     rsi
0x180006739  pop     rbp
0x18000673a  pop     rbx
0x18000673b  retn
```
