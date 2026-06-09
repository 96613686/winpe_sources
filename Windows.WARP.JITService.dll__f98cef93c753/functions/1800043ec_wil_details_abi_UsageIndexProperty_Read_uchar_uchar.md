# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x1800043ec`
- end: `0x1800044e4`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `248`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004888`
- `0x180004f04`

## callees

- `0x1800043ec`
- `0x1800093ca`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180004429`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000446b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800044aa`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180004429`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000446b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800044aa`

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
      *(_DWORD *)_o__errno() = 22;
      invalid_parameter_noinfo();
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
    *(_DWORD *)_o__errno() = 22;
    invalid_parameter_noinfo();
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
    *(_DWORD *)_o__errno() = 22;
    invalid_parameter_noinfo();
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
0x1800043ec  push    rbx
0x1800043ee  push    rbp
0x1800043ef  push    rsi
0x1800043f0  push    rdi
0x1800043f1  push    r14
0x1800043f3  push    r15
0x1800043f5  sub     rsp, 28h
0x1800043f9  mov     rax, [rdx]
0x1800043fc  xor     r15d, r15d
0x1800043ff  cmp     byte ptr [rcx+2], 1
0x180004403  mov     rbp, r8
0x180004406  mov     r14, rdx
0x180004409  mov     rdi, rcx
0x18000440c  jnz     short loc_180004445
0x18000440e  lea     rbx, [rax+2]
0x180004412  cmp     rbx, r8
0x180004415  ja      loc_1800044CA
0x18000441b  mov     [rcx+10h], rax
0x18000441f  test    rax, rax
0x180004422  jz      short loc_180004429
0x180004424  movzx   ecx, word ptr [rax]
0x180004427  jmp     short loc_18000443D
0x180004429  call    cs:__imp__o__errno
0x18000442f  mov     dword ptr [rax], 16h
0x180004435  call    _invalid_parameter_noinfo
0x18000443a  mov     ecx, r15d
0x18000443d  movzx   eax, cx
0x180004440  mov     [rdi+4], eax
0x180004443  jmp     short loc_180004481
0x180004445  cmp     byte ptr [rcx+2], 2
0x180004449  jnz     short loc_18000447E
0x18000444b  lea     rbx, [rax+4]
0x18000444f  cmp     rbx, rbp
0x180004452  ja      short loc_1800044CA
0x180004454  mov     [rcx+10h], rax
0x180004458  add     rcx, 4
0x18000445c  jz      short loc_18000446B
0x18000445e  test    rax, rax
0x180004461  jz      short loc_180004469
0x180004463  mov     eax, [rax]
0x180004465  mov     [rcx], eax
0x180004467  jmp     short loc_180004481
0x180004469  mov     [rcx], eax
0x18000446b  call    cs:__imp__o__errno
0x180004471  mov     dword ptr [rax], 16h
0x180004477  call    _invalid_parameter_noinfo
0x18000447c  jmp     short loc_180004481
0x18000447e  mov     rbx, rax
0x180004481  movzx   eax, word ptr [rdi]
0x180004484  mov     [rdi+8], ax
0x180004488  test    ax, ax
0x18000448b  jnz     short loc_1800044BE
0x18000448d  lea     rsi, [rbx+2]
0x180004491  cmp     rsi, rbp
0x180004494  ja      short loc_1800044CA
0x180004496  test    rbx, rbx
0x180004499  jz      short loc_1800044A4
0x18000449b  movzx   eax, word ptr [rbx]
0x18000449e  mov     [rdi+8], ax
0x1800044a2  jmp     short loc_1800044BB
0x1800044a4  xor     eax, eax
0x1800044a6  mov     [rdi+8], ax
0x1800044aa  call    cs:__imp__o__errno
0x1800044b0  mov     dword ptr [rax], 16h
0x1800044b6  call    _invalid_parameter_noinfo
0x1800044bb  mov     rbx, rsi
0x1800044be  movzx   ecx, word ptr [rdi+8]
0x1800044c2  add     rcx, rbx
0x1800044c5  cmp     rcx, rbp
0x1800044c8  jbe     short loc_1800044CE
0x1800044ca  xor     al, al
0x1800044cc  jmp     short loc_1800044D7
0x1800044ce  mov     [rdi+18h], rbx
0x1800044d2  mov     al, 1
0x1800044d4  mov     [r14], rcx
0x1800044d7  add     rsp, 28h
0x1800044db  pop     r15
0x1800044dd  pop     r14
0x1800044df  pop     rdi
0x1800044e0  pop     rsi
0x1800044e1  pop     rbp
0x1800044e2  pop     rbx
0x1800044e3  retn
```
