# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x140009470`
- end: `0x14000956b`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `251`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14000855c`
- `0x140009a4c`
- `0x140009e24`

## callees

- `0x140009470`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1400094b9`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1400094fc`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x14000953c`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1400094b9`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1400094fc`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x14000953c`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1400094ad`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1400094f0`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x140009530`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1400094ad`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1400094f0`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x140009530`

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
      *_errno() = 22;
      _invalid_parameter_noinfo();
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
    *_errno() = 22;
    _invalid_parameter_noinfo();
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
    *_errno() = 22;
    _invalid_parameter_noinfo();
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
0x140009470  push    rbx
0x140009472  push    rbp
0x140009473  push    rsi
0x140009474  push    rdi
0x140009475  push    r14
0x140009477  push    r15
0x140009479  sub     rsp, 28h
0x14000947d  mov     rax, [rdx]
0x140009480  xor     r15d, r15d
0x140009483  cmp     byte ptr [rcx+2], 1
0x140009487  mov     rbp, r8
0x14000948a  mov     r14, rdx
0x14000948d  mov     rdi, rcx
0x140009490  jnz     short loc_1400094CA
0x140009492  lea     rbx, [rax+2]
0x140009496  cmp     rbx, r8
0x140009499  ja      loc_140009551
0x14000949f  mov     [rcx+10h], rax
0x1400094a3  test    rax, rax
0x1400094a6  jz      short loc_1400094AD
0x1400094a8  movzx   ecx, word ptr [rax]
0x1400094ab  jmp     short loc_1400094C2
0x1400094ad  call    cs:__imp__errno
0x1400094b3  mov     dword ptr [rax], 16h
0x1400094b9  call    cs:__imp__invalid_parameter_noinfo
0x1400094bf  mov     ecx, r15d
0x1400094c2  movzx   eax, cx
0x1400094c5  mov     [rdi+4], eax
0x1400094c8  jmp     short loc_140009507
0x1400094ca  cmp     byte ptr [rcx+2], 2
0x1400094ce  jnz     short loc_140009504
0x1400094d0  lea     rbx, [rax+4]
0x1400094d4  cmp     rbx, rbp
0x1400094d7  ja      short loc_140009551
0x1400094d9  mov     [rcx+10h], rax
0x1400094dd  add     rcx, 4
0x1400094e1  jz      short loc_1400094F0
0x1400094e3  test    rax, rax
0x1400094e6  jz      short loc_1400094EE
0x1400094e8  mov     eax, [rax]
0x1400094ea  mov     [rcx], eax
0x1400094ec  jmp     short loc_140009507
0x1400094ee  mov     [rcx], eax
0x1400094f0  call    cs:__imp__errno
0x1400094f6  mov     dword ptr [rax], 16h
0x1400094fc  call    cs:__imp__invalid_parameter_noinfo
0x140009502  jmp     short loc_140009507
0x140009504  mov     rbx, rax
0x140009507  movzx   eax, word ptr [rdi]
0x14000950a  mov     [rdi+8], ax
0x14000950e  test    ax, ax
0x140009511  jnz     short loc_140009545
0x140009513  lea     rsi, [rbx+2]
0x140009517  cmp     rsi, rbp
0x14000951a  ja      short loc_140009551
0x14000951c  test    rbx, rbx
0x14000951f  jz      short loc_14000952A
0x140009521  movzx   eax, word ptr [rbx]
0x140009524  mov     [rdi+8], ax
0x140009528  jmp     short loc_140009542
0x14000952a  xor     eax, eax
0x14000952c  mov     [rdi+8], ax
0x140009530  call    cs:__imp__errno
0x140009536  mov     dword ptr [rax], 16h
0x14000953c  call    cs:__imp__invalid_parameter_noinfo
0x140009542  mov     rbx, rsi
0x140009545  movzx   ecx, word ptr [rdi+8]
0x140009549  add     rcx, rbx
0x14000954c  cmp     rcx, rbp
0x14000954f  jbe     short loc_140009555
0x140009551  xor     al, al
0x140009553  jmp     short loc_14000955E
0x140009555  mov     [rdi+18h], rbx
0x140009559  mov     al, 1
0x14000955b  mov     [r14], rcx
0x14000955e  add     rsp, 28h
0x140009562  pop     r15
0x140009564  pop     r14
0x140009566  pop     rdi
0x140009567  pop     rsi
0x140009568  pop     rbp
0x140009569  pop     rbx
0x14000956a  retn
```
