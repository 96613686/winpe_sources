# wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)

- ea: `0x18000747c`
- end: `0x180007574`
- name: `?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z`
- size: `248`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180005ac0`
- `0x180007c98`
- `0x18000806c`

## callees

- `0x18000321a`
- `0x18000747c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800074b9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800074fb`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000753a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800074b9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800074fb`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000753a`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Read(
        wil::details_abi::UsageIndexProperty *this,
        unsigned __int8 **a2,
        unsigned __int8 *a3)
{
  _DWORD *v3; // rax
  wil::details_abi::UsageIndexProperty *v6; // rdi
  _WORD *v7; // rbx
  __int16 v8; // ax
  unsigned __int8 *v9; // rcx
  bool result; // al

  v3 = *a2;
  v6 = this;
  if ( *((_BYTE *)this + 2) == 1 )
  {
    v7 = (_WORD *)v3 + 1;
    if ( (unsigned __int8 *)((char *)v3 + 2) > a3 )
      return 0;
    *((_QWORD *)this + 2) = v3;
    if ( v3 )
    {
      this = (wil::details_abi::UsageIndexProperty *)*(unsigned __int16 *)v3;
    }
    else
    {
      *(_DWORD *)_o__errno(this) = 22;
      invalid_parameter_noinfo();
      this = 0;
    }
    *((_DWORD *)v6 + 1) = (unsigned __int16)this;
  }
  else if ( *((_BYTE *)this + 2) == 2 )
  {
    v7 = v3 + 1;
    if ( v3 + 1 > (_DWORD *)a3 )
      return 0;
    *((_QWORD *)this + 2) = v3;
    this = (wil::details_abi::UsageIndexProperty *)((char *)this + 4);
    if ( this )
    {
      if ( v3 )
      {
        *(_DWORD *)this = *v3;
        goto LABEL_15;
      }
      *(_DWORD *)this = 0;
    }
    *(_DWORD *)_o__errno(this) = 22;
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
  if ( v7 + 1 > (_WORD *)a3 )
    return 0;
  if ( v7 )
  {
    *((_WORD *)v6 + 4) = *v7;
  }
  else
  {
    *((_WORD *)v6 + 4) = 0;
    *(_DWORD *)_o__errno(this) = 22;
    invalid_parameter_noinfo();
  }
  ++v7;
LABEL_21:
  v9 = (unsigned __int8 *)v7 + *((unsigned __int16 *)v6 + 4);
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
0x18000747c  push    rbx
0x18000747e  push    rbp
0x18000747f  push    rsi
0x180007480  push    rdi
0x180007481  push    r14
0x180007483  push    r15
0x180007485  sub     rsp, 28h
0x180007489  mov     rax, [rdx]
0x18000748c  xor     r15d, r15d
0x18000748f  cmp     byte ptr [rcx+2], 1
0x180007493  mov     rbp, r8
0x180007496  mov     r14, rdx
0x180007499  mov     rdi, rcx
0x18000749c  jnz     short loc_1800074D5
0x18000749e  lea     rbx, [rax+2]
0x1800074a2  cmp     rbx, r8
0x1800074a5  ja      loc_18000755A
0x1800074ab  mov     [rcx+10h], rax
0x1800074af  test    rax, rax
0x1800074b2  jz      short loc_1800074B9
0x1800074b4  movzx   ecx, word ptr [rax]
0x1800074b7  jmp     short loc_1800074CD
0x1800074b9  call    cs:__imp__o__errno
0x1800074bf  mov     dword ptr [rax], 16h
0x1800074c5  call    _invalid_parameter_noinfo
0x1800074ca  mov     ecx, r15d
0x1800074cd  movzx   eax, cx
0x1800074d0  mov     [rdi+4], eax
0x1800074d3  jmp     short loc_180007511
0x1800074d5  cmp     byte ptr [rcx+2], 2
0x1800074d9  jnz     short loc_18000750E
0x1800074db  lea     rbx, [rax+4]
0x1800074df  cmp     rbx, rbp
0x1800074e2  ja      short loc_18000755A
0x1800074e4  mov     [rcx+10h], rax
0x1800074e8  add     rcx, 4
0x1800074ec  jz      short loc_1800074FB
0x1800074ee  test    rax, rax
0x1800074f1  jz      short loc_1800074F9
0x1800074f3  mov     eax, [rax]
0x1800074f5  mov     [rcx], eax
0x1800074f7  jmp     short loc_180007511
0x1800074f9  mov     [rcx], eax
0x1800074fb  call    cs:__imp__o__errno
0x180007501  mov     dword ptr [rax], 16h
0x180007507  call    _invalid_parameter_noinfo
0x18000750c  jmp     short loc_180007511
0x18000750e  mov     rbx, rax
0x180007511  movzx   eax, word ptr [rdi]
0x180007514  mov     [rdi+8], ax
0x180007518  test    ax, ax
0x18000751b  jnz     short loc_18000754E
0x18000751d  lea     rsi, [rbx+2]
0x180007521  cmp     rsi, rbp
0x180007524  ja      short loc_18000755A
0x180007526  test    rbx, rbx
0x180007529  jz      short loc_180007534
0x18000752b  movzx   eax, word ptr [rbx]
0x18000752e  mov     [rdi+8], ax
0x180007532  jmp     short loc_18000754B
0x180007534  xor     eax, eax
0x180007536  mov     [rdi+8], ax
0x18000753a  call    cs:__imp__o__errno
0x180007540  mov     dword ptr [rax], 16h
0x180007546  call    _invalid_parameter_noinfo
0x18000754b  mov     rbx, rsi
0x18000754e  movzx   ecx, word ptr [rdi+8]
0x180007552  add     rcx, rbx
0x180007555  cmp     rcx, rbp
0x180007558  jbe     short loc_18000755E
0x18000755a  xor     al, al
0x18000755c  jmp     short loc_180007567
0x18000755e  mov     [rdi+18h], rbx
0x180007562  mov     al, 1
0x180007564  mov     [r14], rcx
0x180007567  add     rsp, 28h
0x18000756b  pop     r15
0x18000756d  pop     r14
0x18000756f  pop     rdi
0x180007570  pop     rsi
0x180007571  pop     rbp
0x180007572  pop     rbx
0x180007573  retn
```
