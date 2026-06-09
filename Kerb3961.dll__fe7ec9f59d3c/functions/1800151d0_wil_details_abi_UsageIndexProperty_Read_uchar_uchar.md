# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x1800151d0`
- end: `0x1800152c8`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `248`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180013724`
- `0x180015994`
- `0x180015d68`

## callees

- `0x1800028c8`
- `0x1800151d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001520d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001524f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001528e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001520d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001524f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001528e`

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
0x1800151d0  push    rbx
0x1800151d2  push    rbp
0x1800151d3  push    rsi
0x1800151d4  push    rdi
0x1800151d5  push    r14
0x1800151d7  push    r15
0x1800151d9  sub     rsp, 28h
0x1800151dd  mov     rax, [rdx]
0x1800151e0  xor     r15d, r15d
0x1800151e3  cmp     byte ptr [rcx+2], 1
0x1800151e7  mov     rbp, r8
0x1800151ea  mov     r14, rdx
0x1800151ed  mov     rdi, rcx
0x1800151f0  jnz     short loc_180015229
0x1800151f2  lea     rbx, [rax+2]
0x1800151f6  cmp     rbx, r8
0x1800151f9  ja      loc_1800152AE
0x1800151ff  mov     [rcx+10h], rax
0x180015203  test    rax, rax
0x180015206  jz      short loc_18001520D
0x180015208  movzx   ecx, word ptr [rax]
0x18001520b  jmp     short loc_180015221
0x18001520d  call    cs:__imp__o__errno
0x180015213  mov     dword ptr [rax], 16h
0x180015219  call    _invalid_parameter_noinfo
0x18001521e  mov     ecx, r15d
0x180015221  movzx   eax, cx
0x180015224  mov     [rdi+4], eax
0x180015227  jmp     short loc_180015265
0x180015229  cmp     byte ptr [rcx+2], 2
0x18001522d  jnz     short loc_180015262
0x18001522f  lea     rbx, [rax+4]
0x180015233  cmp     rbx, rbp
0x180015236  ja      short loc_1800152AE
0x180015238  mov     [rcx+10h], rax
0x18001523c  add     rcx, 4
0x180015240  jz      short loc_18001524F
0x180015242  test    rax, rax
0x180015245  jz      short loc_18001524D
0x180015247  mov     eax, [rax]
0x180015249  mov     [rcx], eax
0x18001524b  jmp     short loc_180015265
0x18001524d  mov     [rcx], eax
0x18001524f  call    cs:__imp__o__errno
0x180015255  mov     dword ptr [rax], 16h
0x18001525b  call    _invalid_parameter_noinfo
0x180015260  jmp     short loc_180015265
0x180015262  mov     rbx, rax
0x180015265  movzx   eax, word ptr [rdi]
0x180015268  mov     [rdi+8], ax
0x18001526c  test    ax, ax
0x18001526f  jnz     short loc_1800152A2
0x180015271  lea     rsi, [rbx+2]
0x180015275  cmp     rsi, rbp
0x180015278  ja      short loc_1800152AE
0x18001527a  test    rbx, rbx
0x18001527d  jz      short loc_180015288
0x18001527f  movzx   eax, word ptr [rbx]
0x180015282  mov     [rdi+8], ax
0x180015286  jmp     short loc_18001529F
0x180015288  xor     eax, eax
0x18001528a  mov     [rdi+8], ax
0x18001528e  call    cs:__imp__o__errno
0x180015294  mov     dword ptr [rax], 16h
0x18001529a  call    _invalid_parameter_noinfo
0x18001529f  mov     rbx, rsi
0x1800152a2  movzx   ecx, word ptr [rdi+8]
0x1800152a6  add     rcx, rbx
0x1800152a9  cmp     rcx, rbp
0x1800152ac  jbe     short loc_1800152B2
0x1800152ae  xor     al, al
0x1800152b0  jmp     short loc_1800152BB
0x1800152b2  mov     [rdi+18h], rbx
0x1800152b6  mov     al, 1
0x1800152b8  mov     [r14], rcx
0x1800152bb  add     rsp, 28h
0x1800152bf  pop     r15
0x1800152c1  pop     r14
0x1800152c3  pop     rdi
0x1800152c4  pop     rsi
0x1800152c5  pop     rbp
0x1800152c6  pop     rbx
0x1800152c7  retn
```
