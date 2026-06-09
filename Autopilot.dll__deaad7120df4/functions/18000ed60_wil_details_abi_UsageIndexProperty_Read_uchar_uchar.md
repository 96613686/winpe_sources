# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x18000ed60`
- end: `0x18000ee6f`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `271`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000cd44`
- `0x18000f5c4`
- `0x18000f9b8`

## callees

- `0x180005356`
- `0x18000ed60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ed9d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ede9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ee2e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ed9d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ede9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ee2e`

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
0x18000ed60  push    rbx
0x18000ed62  push    rbp
0x18000ed63  push    rsi
0x18000ed64  push    rdi
0x18000ed65  push    r14
0x18000ed67  push    r15
0x18000ed69  sub     rsp, 28h
0x18000ed6d  mov     rax, [rdx]
0x18000ed70  xor     r15d, r15d
0x18000ed73  cmp     byte ptr [rcx+2], 1
0x18000ed77  mov     rbp, r8
0x18000ed7a  mov     r14, rdx
0x18000ed7d  mov     rdi, rcx
0x18000ed80  jnz     short loc_18000EDBF
0x18000ed82  lea     rbx, [rax+2]
0x18000ed86  cmp     rbx, r8
0x18000ed89  ja      loc_18000EE54
0x18000ed8f  mov     [rcx+10h], rax
0x18000ed93  test    rax, rax
0x18000ed96  jz      short loc_18000ED9D
0x18000ed98  movzx   ecx, word ptr [rax]
0x18000ed9b  jmp     short loc_18000EDB7
0x18000ed9d  call    cs:__imp__o__errno
0x18000eda4  nop     dword ptr [rax+rax+00h]
0x18000eda9  mov     dword ptr [rax], 16h
0x18000edaf  call    _invalid_parameter_noinfo
0x18000edb4  mov     ecx, r15d
0x18000edb7  movzx   eax, cx
0x18000edba  mov     [rdi+4], eax
0x18000edbd  jmp     short loc_18000EE05
0x18000edbf  cmp     byte ptr [rcx+2], 2
0x18000edc3  jnz     short loc_18000EE02
0x18000edc5  lea     rbx, [rax+4]
0x18000edc9  cmp     rbx, rbp
0x18000edcc  ja      loc_18000EE54
0x18000edd2  mov     [rcx+10h], rax
0x18000edd6  add     rcx, 4
0x18000edda  jz      short loc_18000EDE9
0x18000eddc  test    rax, rax
0x18000eddf  jz      short loc_18000EDE7
0x18000ede1  mov     eax, [rax]
0x18000ede3  mov     [rcx], eax
0x18000ede5  jmp     short loc_18000EE05
0x18000ede7  mov     [rcx], eax
0x18000ede9  call    cs:__imp__o__errno
0x18000edf0  nop     dword ptr [rax+rax+00h]
0x18000edf5  mov     dword ptr [rax], 16h
0x18000edfb  call    _invalid_parameter_noinfo
0x18000ee00  jmp     short loc_18000EE05
0x18000ee02  mov     rbx, rax
0x18000ee05  movzx   eax, word ptr [rdi]
0x18000ee08  mov     [rdi+8], ax
0x18000ee0c  test    ax, ax
0x18000ee0f  jnz     short loc_18000EE48
0x18000ee11  lea     rsi, [rbx+2]
0x18000ee15  cmp     rsi, rbp
0x18000ee18  ja      short loc_18000EE54
0x18000ee1a  test    rbx, rbx
0x18000ee1d  jz      short loc_18000EE28
0x18000ee1f  movzx   eax, word ptr [rbx]
0x18000ee22  mov     [rdi+8], ax
0x18000ee26  jmp     short loc_18000EE45
0x18000ee28  xor     eax, eax
0x18000ee2a  mov     [rdi+8], ax
0x18000ee2e  call    cs:__imp__o__errno
0x18000ee35  nop     dword ptr [rax+rax+00h]
0x18000ee3a  mov     dword ptr [rax], 16h
0x18000ee40  call    _invalid_parameter_noinfo
0x18000ee45  mov     rbx, rsi
0x18000ee48  movzx   ecx, word ptr [rdi+8]
0x18000ee4c  add     rcx, rbx
0x18000ee4f  cmp     rcx, rbp
0x18000ee52  jbe     short loc_18000EE58
0x18000ee54  xor     al, al
0x18000ee56  jmp     short loc_18000EE61
0x18000ee58  mov     [rdi+18h], rbx
0x18000ee5c  mov     al, 1
0x18000ee5e  mov     [r14], rcx
0x18000ee61  add     rsp, 28h
0x18000ee65  pop     r15
0x18000ee67  pop     r14
0x18000ee69  pop     rdi
0x18000ee6a  pop     rsi
0x18000ee6b  pop     rbp
0x18000ee6c  pop     rbx
0x18000ee6d  retn
```
