# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x1800170d0`
- end: `0x1800171c8`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `248`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180015994`
- `0x180017718`
- `0x180017aec`

## callees

- `0x180001fe6`
- `0x1800170d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001710d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001714f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001718e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001710d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001714f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001718e`

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
0x1800170d0  push    rbx
0x1800170d2  push    rbp
0x1800170d3  push    rsi
0x1800170d4  push    rdi
0x1800170d5  push    r14
0x1800170d7  push    r15
0x1800170d9  sub     rsp, 28h
0x1800170dd  mov     rax, [rdx]
0x1800170e0  xor     r15d, r15d
0x1800170e3  cmp     byte ptr [rcx+2], 1
0x1800170e7  mov     rbp, r8
0x1800170ea  mov     r14, rdx
0x1800170ed  mov     rdi, rcx
0x1800170f0  jnz     short loc_180017129
0x1800170f2  lea     rbx, [rax+2]
0x1800170f6  cmp     rbx, r8
0x1800170f9  ja      loc_1800171AE
0x1800170ff  mov     [rcx+10h], rax
0x180017103  test    rax, rax
0x180017106  jz      short loc_18001710D
0x180017108  movzx   ecx, word ptr [rax]
0x18001710b  jmp     short loc_180017121
0x18001710d  call    cs:__imp__o__errno
0x180017113  mov     dword ptr [rax], 16h
0x180017119  call    _invalid_parameter_noinfo
0x18001711e  mov     ecx, r15d
0x180017121  movzx   eax, cx
0x180017124  mov     [rdi+4], eax
0x180017127  jmp     short loc_180017165
0x180017129  cmp     byte ptr [rcx+2], 2
0x18001712d  jnz     short loc_180017162
0x18001712f  lea     rbx, [rax+4]
0x180017133  cmp     rbx, rbp
0x180017136  ja      short loc_1800171AE
0x180017138  mov     [rcx+10h], rax
0x18001713c  add     rcx, 4
0x180017140  jz      short loc_18001714F
0x180017142  test    rax, rax
0x180017145  jz      short loc_18001714D
0x180017147  mov     eax, [rax]
0x180017149  mov     [rcx], eax
0x18001714b  jmp     short loc_180017165
0x18001714d  mov     [rcx], eax
0x18001714f  call    cs:__imp__o__errno
0x180017155  mov     dword ptr [rax], 16h
0x18001715b  call    _invalid_parameter_noinfo
0x180017160  jmp     short loc_180017165
0x180017162  mov     rbx, rax
0x180017165  movzx   eax, word ptr [rdi]
0x180017168  mov     [rdi+8], ax
0x18001716c  test    ax, ax
0x18001716f  jnz     short loc_1800171A2
0x180017171  lea     rsi, [rbx+2]
0x180017175  cmp     rsi, rbp
0x180017178  ja      short loc_1800171AE
0x18001717a  test    rbx, rbx
0x18001717d  jz      short loc_180017188
0x18001717f  movzx   eax, word ptr [rbx]
0x180017182  mov     [rdi+8], ax
0x180017186  jmp     short loc_18001719F
0x180017188  xor     eax, eax
0x18001718a  mov     [rdi+8], ax
0x18001718e  call    cs:__imp__o__errno
0x180017194  mov     dword ptr [rax], 16h
0x18001719a  call    _invalid_parameter_noinfo
0x18001719f  mov     rbx, rsi
0x1800171a2  movzx   ecx, word ptr [rdi+8]
0x1800171a6  add     rcx, rbx
0x1800171a9  cmp     rcx, rbp
0x1800171ac  jbe     short loc_1800171B2
0x1800171ae  xor     al, al
0x1800171b0  jmp     short loc_1800171BB
0x1800171b2  mov     [rdi+18h], rbx
0x1800171b6  mov     al, 1
0x1800171b8  mov     [r14], rcx
0x1800171bb  add     rsp, 28h
0x1800171bf  pop     r15
0x1800171c1  pop     r14
0x1800171c3  pop     rdi
0x1800171c4  pop     rsi
0x1800171c5  pop     rbp
0x1800171c6  pop     rbx
0x1800171c7  retn
```
