# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x140014884`
- end: `0x14001497c`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `248`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1400141bc`
- `0x140014e5c`
- `0x140015230`

## callees

- `0x14000903a`
- `0x140014884`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400148c1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140014903`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140014942`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400148c1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140014903`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140014942`

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
0x140014884  push    rbx
0x140014886  push    rbp
0x140014887  push    rsi
0x140014888  push    rdi
0x140014889  push    r14
0x14001488b  push    r15
0x14001488d  sub     rsp, 28h
0x140014891  mov     rax, [rdx]
0x140014894  xor     r15d, r15d
0x140014897  cmp     byte ptr [rcx+2], 1
0x14001489b  mov     rbp, r8
0x14001489e  mov     r14, rdx
0x1400148a1  mov     rdi, rcx
0x1400148a4  jnz     short loc_1400148DD
0x1400148a6  lea     rbx, [rax+2]
0x1400148aa  cmp     rbx, r8
0x1400148ad  ja      loc_140014962
0x1400148b3  mov     [rcx+10h], rax
0x1400148b7  test    rax, rax
0x1400148ba  jz      short loc_1400148C1
0x1400148bc  movzx   ecx, word ptr [rax]
0x1400148bf  jmp     short loc_1400148D5
0x1400148c1  call    cs:__imp__o__errno
0x1400148c7  mov     dword ptr [rax], 16h
0x1400148cd  call    _invalid_parameter_noinfo
0x1400148d2  mov     ecx, r15d
0x1400148d5  movzx   eax, cx
0x1400148d8  mov     [rdi+4], eax
0x1400148db  jmp     short loc_140014919
0x1400148dd  cmp     byte ptr [rcx+2], 2
0x1400148e1  jnz     short loc_140014916
0x1400148e3  lea     rbx, [rax+4]
0x1400148e7  cmp     rbx, rbp
0x1400148ea  ja      short loc_140014962
0x1400148ec  mov     [rcx+10h], rax
0x1400148f0  add     rcx, 4
0x1400148f4  jz      short loc_140014903
0x1400148f6  test    rax, rax
0x1400148f9  jz      short loc_140014901
0x1400148fb  mov     eax, [rax]
0x1400148fd  mov     [rcx], eax
0x1400148ff  jmp     short loc_140014919
0x140014901  mov     [rcx], eax
0x140014903  call    cs:__imp__o__errno
0x140014909  mov     dword ptr [rax], 16h
0x14001490f  call    _invalid_parameter_noinfo
0x140014914  jmp     short loc_140014919
0x140014916  mov     rbx, rax
0x140014919  movzx   eax, word ptr [rdi]
0x14001491c  mov     [rdi+8], ax
0x140014920  test    ax, ax
0x140014923  jnz     short loc_140014956
0x140014925  lea     rsi, [rbx+2]
0x140014929  cmp     rsi, rbp
0x14001492c  ja      short loc_140014962
0x14001492e  test    rbx, rbx
0x140014931  jz      short loc_14001493C
0x140014933  movzx   eax, word ptr [rbx]
0x140014936  mov     [rdi+8], ax
0x14001493a  jmp     short loc_140014953
0x14001493c  xor     eax, eax
0x14001493e  mov     [rdi+8], ax
0x140014942  call    cs:__imp__o__errno
0x140014948  mov     dword ptr [rax], 16h
0x14001494e  call    _invalid_parameter_noinfo
0x140014953  mov     rbx, rsi
0x140014956  movzx   ecx, word ptr [rdi+8]
0x14001495a  add     rcx, rbx
0x14001495d  cmp     rcx, rbp
0x140014960  jbe     short loc_140014966
0x140014962  xor     al, al
0x140014964  jmp     short loc_14001496F
0x140014966  mov     [rdi+18h], rbx
0x14001496a  mov     al, 1
0x14001496c  mov     [r14], rcx
0x14001496f  add     rsp, 28h
0x140014973  pop     r15
0x140014975  pop     r14
0x140014977  pop     rdi
0x140014978  pop     rsi
0x140014979  pop     rbp
0x14001497a  pop     rbx
0x14001497b  retn
```
