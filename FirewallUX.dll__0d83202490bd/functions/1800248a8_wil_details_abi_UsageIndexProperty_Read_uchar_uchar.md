# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x1800248a8`
- end: `0x1800249a0`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `248`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18002436c`
- `0x180024e8c`
- `0x180025260`

## callees

- `0x180002b9a`
- `0x1800248a8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800248e5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180024927`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180024966`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800248e5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180024927`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180024966`

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
0x1800248a8  push    rbx
0x1800248aa  push    rbp
0x1800248ab  push    rsi
0x1800248ac  push    rdi
0x1800248ad  push    r14
0x1800248af  push    r15
0x1800248b1  sub     rsp, 28h
0x1800248b5  mov     rax, [rdx]
0x1800248b8  xor     r15d, r15d
0x1800248bb  cmp     byte ptr [rcx+2], 1
0x1800248bf  mov     rbp, r8
0x1800248c2  mov     r14, rdx
0x1800248c5  mov     rdi, rcx
0x1800248c8  jnz     short loc_180024901
0x1800248ca  lea     rbx, [rax+2]
0x1800248ce  cmp     rbx, r8
0x1800248d1  ja      loc_180024986
0x1800248d7  mov     [rcx+10h], rax
0x1800248db  test    rax, rax
0x1800248de  jz      short loc_1800248E5
0x1800248e0  movzx   ecx, word ptr [rax]
0x1800248e3  jmp     short loc_1800248F9
0x1800248e5  call    cs:__imp__o__errno
0x1800248eb  mov     dword ptr [rax], 16h
0x1800248f1  call    _invalid_parameter_noinfo
0x1800248f6  mov     ecx, r15d
0x1800248f9  movzx   eax, cx
0x1800248fc  mov     [rdi+4], eax
0x1800248ff  jmp     short loc_18002493D
0x180024901  cmp     byte ptr [rcx+2], 2
0x180024905  jnz     short loc_18002493A
0x180024907  lea     rbx, [rax+4]
0x18002490b  cmp     rbx, rbp
0x18002490e  ja      short loc_180024986
0x180024910  mov     [rcx+10h], rax
0x180024914  add     rcx, 4
0x180024918  jz      short loc_180024927
0x18002491a  test    rax, rax
0x18002491d  jz      short loc_180024925
0x18002491f  mov     eax, [rax]
0x180024921  mov     [rcx], eax
0x180024923  jmp     short loc_18002493D
0x180024925  mov     [rcx], eax
0x180024927  call    cs:__imp__o__errno
0x18002492d  mov     dword ptr [rax], 16h
0x180024933  call    _invalid_parameter_noinfo
0x180024938  jmp     short loc_18002493D
0x18002493a  mov     rbx, rax
0x18002493d  movzx   eax, word ptr [rdi]
0x180024940  mov     [rdi+8], ax
0x180024944  test    ax, ax
0x180024947  jnz     short loc_18002497A
0x180024949  lea     rsi, [rbx+2]
0x18002494d  cmp     rsi, rbp
0x180024950  ja      short loc_180024986
0x180024952  test    rbx, rbx
0x180024955  jz      short loc_180024960
0x180024957  movzx   eax, word ptr [rbx]
0x18002495a  mov     [rdi+8], ax
0x18002495e  jmp     short loc_180024977
0x180024960  xor     eax, eax
0x180024962  mov     [rdi+8], ax
0x180024966  call    cs:__imp__o__errno
0x18002496c  mov     dword ptr [rax], 16h
0x180024972  call    _invalid_parameter_noinfo
0x180024977  mov     rbx, rsi
0x18002497a  movzx   ecx, word ptr [rdi+8]
0x18002497e  add     rcx, rbx
0x180024981  cmp     rcx, rbp
0x180024984  jbe     short loc_18002498A
0x180024986  xor     al, al
0x180024988  jmp     short loc_180024993
0x18002498a  mov     [rdi+18h], rbx
0x18002498e  mov     al, 1
0x180024990  mov     [r14], rcx
0x180024993  add     rsp, 28h
0x180024997  pop     r15
0x180024999  pop     r14
0x18002499b  pop     rdi
0x18002499c  pop     rsi
0x18002499d  pop     rbp
0x18002499e  pop     rbx
0x18002499f  retn
```
