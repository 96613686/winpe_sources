# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x18001118c`
- end: `0x180011284`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `248`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800101b4`
- `0x180011764`
- `0x180011b38`

## callees

- `0x180003ca6`
- `0x18001118c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800111c9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001120b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001124a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800111c9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001120b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001124a`

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
0x18001118c  push    rbx
0x18001118e  push    rbp
0x18001118f  push    rsi
0x180011190  push    rdi
0x180011191  push    r14
0x180011193  push    r15
0x180011195  sub     rsp, 28h
0x180011199  mov     rax, [rdx]
0x18001119c  xor     r15d, r15d
0x18001119f  cmp     byte ptr [rcx+2], 1
0x1800111a3  mov     rbp, r8
0x1800111a6  mov     r14, rdx
0x1800111a9  mov     rdi, rcx
0x1800111ac  jnz     short loc_1800111E5
0x1800111ae  lea     rbx, [rax+2]
0x1800111b2  cmp     rbx, r8
0x1800111b5  ja      loc_18001126A
0x1800111bb  mov     [rcx+10h], rax
0x1800111bf  test    rax, rax
0x1800111c2  jz      short loc_1800111C9
0x1800111c4  movzx   ecx, word ptr [rax]
0x1800111c7  jmp     short loc_1800111DD
0x1800111c9  call    cs:__imp__o__errno
0x1800111cf  mov     dword ptr [rax], 16h
0x1800111d5  call    _invalid_parameter_noinfo
0x1800111da  mov     ecx, r15d
0x1800111dd  movzx   eax, cx
0x1800111e0  mov     [rdi+4], eax
0x1800111e3  jmp     short loc_180011221
0x1800111e5  cmp     byte ptr [rcx+2], 2
0x1800111e9  jnz     short loc_18001121E
0x1800111eb  lea     rbx, [rax+4]
0x1800111ef  cmp     rbx, rbp
0x1800111f2  ja      short loc_18001126A
0x1800111f4  mov     [rcx+10h], rax
0x1800111f8  add     rcx, 4
0x1800111fc  jz      short loc_18001120B
0x1800111fe  test    rax, rax
0x180011201  jz      short loc_180011209
0x180011203  mov     eax, [rax]
0x180011205  mov     [rcx], eax
0x180011207  jmp     short loc_180011221
0x180011209  mov     [rcx], eax
0x18001120b  call    cs:__imp__o__errno
0x180011211  mov     dword ptr [rax], 16h
0x180011217  call    _invalid_parameter_noinfo
0x18001121c  jmp     short loc_180011221
0x18001121e  mov     rbx, rax
0x180011221  movzx   eax, word ptr [rdi]
0x180011224  mov     [rdi+8], ax
0x180011228  test    ax, ax
0x18001122b  jnz     short loc_18001125E
0x18001122d  lea     rsi, [rbx+2]
0x180011231  cmp     rsi, rbp
0x180011234  ja      short loc_18001126A
0x180011236  test    rbx, rbx
0x180011239  jz      short loc_180011244
0x18001123b  movzx   eax, word ptr [rbx]
0x18001123e  mov     [rdi+8], ax
0x180011242  jmp     short loc_18001125B
0x180011244  xor     eax, eax
0x180011246  mov     [rdi+8], ax
0x18001124a  call    cs:__imp__o__errno
0x180011250  mov     dword ptr [rax], 16h
0x180011256  call    _invalid_parameter_noinfo
0x18001125b  mov     rbx, rsi
0x18001125e  movzx   ecx, word ptr [rdi+8]
0x180011262  add     rcx, rbx
0x180011265  cmp     rcx, rbp
0x180011268  jbe     short loc_18001126E
0x18001126a  xor     al, al
0x18001126c  jmp     short loc_180011277
0x18001126e  mov     [rdi+18h], rbx
0x180011272  mov     al, 1
0x180011274  mov     [r14], rcx
0x180011277  add     rsp, 28h
0x18001127b  pop     r15
0x18001127d  pop     r14
0x18001127f  pop     rdi
0x180011280  pop     rsi
0x180011281  pop     rbp
0x180011282  pop     rbx
0x180011283  retn
```
