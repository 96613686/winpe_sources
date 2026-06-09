# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x140005ffc`
- end: `0x1400060f4`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `248`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140004730`
- `0x140006848`
- `0x140006c1c`

## callees

- `0x14000216a`
- `0x140005ffc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140006039`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000607b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400060ba`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140006039`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000607b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400060ba`

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
0x140005ffc  push    rbx
0x140005ffe  push    rbp
0x140005fff  push    rsi
0x140006000  push    rdi
0x140006001  push    r14
0x140006003  push    r15
0x140006005  sub     rsp, 28h
0x140006009  mov     rax, [rdx]
0x14000600c  xor     r15d, r15d
0x14000600f  cmp     byte ptr [rcx+2], 1
0x140006013  mov     rbp, r8
0x140006016  mov     r14, rdx
0x140006019  mov     rdi, rcx
0x14000601c  jnz     short loc_140006055
0x14000601e  lea     rbx, [rax+2]
0x140006022  cmp     rbx, r8
0x140006025  ja      loc_1400060DA
0x14000602b  mov     [rcx+10h], rax
0x14000602f  test    rax, rax
0x140006032  jz      short loc_140006039
0x140006034  movzx   ecx, word ptr [rax]
0x140006037  jmp     short loc_14000604D
0x140006039  call    cs:__imp__o__errno
0x14000603f  mov     dword ptr [rax], 16h
0x140006045  call    _invalid_parameter_noinfo
0x14000604a  mov     ecx, r15d
0x14000604d  movzx   eax, cx
0x140006050  mov     [rdi+4], eax
0x140006053  jmp     short loc_140006091
0x140006055  cmp     byte ptr [rcx+2], 2
0x140006059  jnz     short loc_14000608E
0x14000605b  lea     rbx, [rax+4]
0x14000605f  cmp     rbx, rbp
0x140006062  ja      short loc_1400060DA
0x140006064  mov     [rcx+10h], rax
0x140006068  add     rcx, 4
0x14000606c  jz      short loc_14000607B
0x14000606e  test    rax, rax
0x140006071  jz      short loc_140006079
0x140006073  mov     eax, [rax]
0x140006075  mov     [rcx], eax
0x140006077  jmp     short loc_140006091
0x140006079  mov     [rcx], eax
0x14000607b  call    cs:__imp__o__errno
0x140006081  mov     dword ptr [rax], 16h
0x140006087  call    _invalid_parameter_noinfo
0x14000608c  jmp     short loc_140006091
0x14000608e  mov     rbx, rax
0x140006091  movzx   eax, word ptr [rdi]
0x140006094  mov     [rdi+8], ax
0x140006098  test    ax, ax
0x14000609b  jnz     short loc_1400060CE
0x14000609d  lea     rsi, [rbx+2]
0x1400060a1  cmp     rsi, rbp
0x1400060a4  ja      short loc_1400060DA
0x1400060a6  test    rbx, rbx
0x1400060a9  jz      short loc_1400060B4
0x1400060ab  movzx   eax, word ptr [rbx]
0x1400060ae  mov     [rdi+8], ax
0x1400060b2  jmp     short loc_1400060CB
0x1400060b4  xor     eax, eax
0x1400060b6  mov     [rdi+8], ax
0x1400060ba  call    cs:__imp__o__errno
0x1400060c0  mov     dword ptr [rax], 16h
0x1400060c6  call    _invalid_parameter_noinfo
0x1400060cb  mov     rbx, rsi
0x1400060ce  movzx   ecx, word ptr [rdi+8]
0x1400060d2  add     rcx, rbx
0x1400060d5  cmp     rcx, rbp
0x1400060d8  jbe     short loc_1400060DE
0x1400060da  xor     al, al
0x1400060dc  jmp     short loc_1400060E7
0x1400060de  mov     [rdi+18h], rbx
0x1400060e2  mov     al, 1
0x1400060e4  mov     [r14], rcx
0x1400060e7  add     rsp, 28h
0x1400060eb  pop     r15
0x1400060ed  pop     r14
0x1400060ef  pop     rdi
0x1400060f0  pop     rsi
0x1400060f1  pop     rbp
0x1400060f2  pop     rbx
0x1400060f3  retn
```
