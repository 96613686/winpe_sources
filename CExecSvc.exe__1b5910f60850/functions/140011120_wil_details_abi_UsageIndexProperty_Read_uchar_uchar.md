# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x140011120`
- end: `0x14001121f`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `255`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14001067c`
- `0x14001178c`
- `0x140011b70`

## callees

- `0x140002e22`
- `0x140011120`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140011160`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400111a2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400111e1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140011160`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400111a2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400111e1`

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
0x140011120  mov     [rsp+arg_10], rbx
0x140011125  push    rbp
0x140011126  push    rsi
0x140011127  push    rdi
0x140011128  push    r14
0x14001112a  push    r15
0x14001112c  sub     rsp, 20h
0x140011130  mov     rax, [rdx]
0x140011133  xor     r15d, r15d
0x140011136  cmp     byte ptr [rcx+2], 1
0x14001113a  mov     rbp, r8
0x14001113d  mov     r14, rdx
0x140011140  mov     rdi, rcx
0x140011143  jnz     short loc_14001117C
0x140011145  lea     rbx, [rax+2]
0x140011149  cmp     rbx, r8
0x14001114c  ja      loc_140011201
0x140011152  mov     [rcx+10h], rax
0x140011156  test    rax, rax
0x140011159  jz      short loc_140011160
0x14001115b  movzx   ecx, word ptr [rax]
0x14001115e  jmp     short loc_140011174
0x140011160  call    cs:__imp__o__errno
0x140011166  mov     dword ptr [rax], 16h
0x14001116c  call    _invalid_parameter_noinfo
0x140011171  mov     ecx, r15d
0x140011174  movzx   eax, cx
0x140011177  mov     [rdi+4], eax
0x14001117a  jmp     short loc_1400111B8
0x14001117c  cmp     byte ptr [rcx+2], 2
0x140011180  jnz     short loc_1400111B5
0x140011182  lea     rbx, [rax+4]
0x140011186  cmp     rbx, rbp
0x140011189  ja      short loc_140011201
0x14001118b  mov     [rcx+10h], rax
0x14001118f  add     rcx, 4
0x140011193  jz      short loc_1400111A2
0x140011195  test    rax, rax
0x140011198  jz      short loc_1400111A0
0x14001119a  mov     eax, [rax]
0x14001119c  mov     [rcx], eax
0x14001119e  jmp     short loc_1400111B8
0x1400111a0  mov     [rcx], eax
0x1400111a2  call    cs:__imp__o__errno
0x1400111a8  mov     dword ptr [rax], 16h
0x1400111ae  call    _invalid_parameter_noinfo
0x1400111b3  jmp     short loc_1400111B8
0x1400111b5  mov     rbx, rax
0x1400111b8  movzx   eax, word ptr [rdi]
0x1400111bb  mov     [rdi+8], ax
0x1400111bf  test    ax, ax
0x1400111c2  jnz     short loc_1400111F5
0x1400111c4  lea     rsi, [rbx+2]
0x1400111c8  cmp     rsi, rbp
0x1400111cb  ja      short loc_140011201
0x1400111cd  test    rbx, rbx
0x1400111d0  jz      short loc_1400111DB
0x1400111d2  movzx   eax, word ptr [rbx]
0x1400111d5  mov     [rdi+8], ax
0x1400111d9  jmp     short loc_1400111F2
0x1400111db  xor     eax, eax
0x1400111dd  mov     [rdi+8], ax
0x1400111e1  call    cs:__imp__o__errno
0x1400111e7  mov     dword ptr [rax], 16h
0x1400111ed  call    _invalid_parameter_noinfo
0x1400111f2  mov     rbx, rsi
0x1400111f5  movzx   ecx, word ptr [rdi+8]
0x1400111f9  add     rcx, rbx
0x1400111fc  cmp     rcx, rbp
0x1400111ff  jbe     short loc_140011205
0x140011201  xor     al, al
0x140011203  jmp     short loc_14001120E
0x140011205  mov     [rdi+18h], rbx
0x140011209  mov     al, 1
0x14001120b  mov     [r14], rcx
0x14001120e  mov     rbx, [rsp+48h+arg_10]
0x140011213  add     rsp, 20h
0x140011217  pop     r15
0x140011219  pop     r14
0x14001121b  pop     rdi
0x14001121c  pop     rsi
0x14001121d  pop     rbp
0x14001121e  retn
```
