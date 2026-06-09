# sub_1801ACBE4

- ea: `0x1801acbe4`
- end: `0x1801accf0`
- name: `sub_1801ACBE4`
- size: `268`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1801ace54`

## callees

- `0x1801ac0a8`
- `0x1801acbe4`

## string_xrefs

- `0x1801accb6`: `Auth_RefreshToken=`
- `0x1801acc88`: `Auth_AccessToken=`

## pseudocode

```c
__int64 __fastcall sub_1801ACBE4(__int64 a1, __int64 a2)
{
  _DWORD *v2; // rbx
  _DWORD *v4; // r14
  __int64 v7; // [rsp+50h] [rbp+30h] BYREF

  v2 = (_DWORD *)(a1 + 8);
  *(_QWORD *)a1 = 0;
  v4 = (_DWORD *)(a1 + 40);
  *(_QWORD *)(a1 + 16) = 0;
  *(_DWORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  *(_DWORD *)(a1 + 56) = 0;
  *(_WORD *)(a1 + 60) = 0;
  *(_DWORD *)(a1 + 8) = 0;
  *(_DWORD *)(a1 + 40) = 0;
  v7 = 0;
  sub_1801AC0A8(a2, L"UID=", &v7, a1 + 8);
  *(_QWORD *)a1 = v7;
  v7 = 0;
  if ( *v2 )
  {
    sub_1801AC0A8(a2, L"PWD=", &v7, a1 + 24);
    *(_QWORD *)(a1 + 16) = v7;
    *(_BYTE *)(a1 + 61) = 1;
  }
  else
  {
    sub_1801AC0A8(a2, L"Auth_AccessToken=", &v7, v4);
    *(_QWORD *)(a1 + 32) = v7;
    if ( *v4 )
    {
      v7 = 0;
      sub_1801AC0A8(a2, L"Auth_RefreshToken=", &v7, a1 + 56);
      *(_QWORD *)(a1 + 48) = v7;
      *(_WORD *)(a1 + 60) = 257;
    }
    else
    {
      *(_QWORD *)(a1 + 32) = 0;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x1801acbe4  mov     [rsp-28h+arg_8], rbx
0x1801acbe9  mov     [rsp-28h+arg_10], rsi
0x1801acbee  mov     [rsp-28h+arg_18], rdi
0x1801acbf3  push    rbp
0x1801acbf4  push    r12
0x1801acbf6  push    r13
0x1801acbf8  push    r14
0x1801acbfa  push    r15
0x1801acbfc  mov     rbp, rsp
0x1801acbff  sub     rsp, 20h
0x1801acc03  xor     r13d, r13d
0x1801acc06  lea     rbx, [rcx+8]
0x1801acc0a  mov     rsi, rdx
0x1801acc0d  mov     [rcx], r13
0x1801acc10  lea     r14, [rcx+28h]
0x1801acc14  mov     [rcx+10h], r13
0x1801acc18  mov     [rcx+18h], r13d
0x1801acc1c  lea     r8, [rbp+arg_0]
0x1801acc20  mov     [rcx+20h], r13
0x1801acc24  lea     rdx, aUid; "UID="
0x1801acc2b  mov     [rcx+30h], r13
0x1801acc2f  mov     rdi, rcx
0x1801acc32  mov     [rcx+38h], r13d
0x1801acc36  mov     r9, rbx
0x1801acc39  mov     [rcx+3Ch], r13w
0x1801acc3e  mov     rcx, rsi
0x1801acc41  mov     [rbx], r13d
0x1801acc44  mov     [r14], r13d
0x1801acc47  mov     [rbp+arg_0], r13
0x1801acc4b  call    sub_1801AC0A8
0x1801acc50  lea     r8, [rbp+arg_0]
0x1801acc54  mov     rax, [rbp+arg_0]
0x1801acc58  mov     rcx, rsi
0x1801acc5b  mov     [rdi], rax
0x1801acc5e  mov     [rbp+arg_0], r13
0x1801acc62  cmp     [rbx], r13d
0x1801acc65  jbe     short loc_1801ACC85
0x1801acc67  lea     r9, [rdi+18h]
0x1801acc6b  lea     rdx, aPwd_2; "PWD="
0x1801acc72  call    sub_1801AC0A8
0x1801acc77  mov     rax, [rbp+arg_0]
0x1801acc7b  mov     [rdi+10h], rax
0x1801acc7f  mov     byte ptr [rdi+3Dh], 1
0x1801acc83  jmp     short loc_1801ACCD0
0x1801acc85  mov     r9, r14
0x1801acc88  lea     rdx, aAuthAccesstoke; "Auth_AccessToken="
0x1801acc8f  call    sub_1801AC0A8
0x1801acc94  mov     rax, [rbp+arg_0]
0x1801acc98  mov     [rdi+20h], rax
0x1801acc9c  cmp     [r14], r13d
0x1801acc9f  jnz     short loc_1801ACCA7
0x1801acca1  mov     [rdi+20h], r13
0x1801acca5  jmp     short loc_1801ACCD0
0x1801acca7  lea     r9, [rdi+38h]
0x1801accab  mov     [rbp+arg_0], r13
0x1801accaf  lea     r8, [rbp+arg_0]
0x1801accb3  mov     rcx, rsi
0x1801accb6  lea     rdx, aAuthRefreshtok; "Auth_RefreshToken="
0x1801accbd  call    sub_1801AC0A8
0x1801accc2  mov     rax, [rbp+arg_0]
0x1801accc6  mov     [rdi+30h], rax
0x1801accca  mov     word ptr [rdi+3Ch], 101h
0x1801accd0  mov     rbx, [rsp+20h+arg_8]
0x1801accd5  mov     rax, rdi
0x1801accd8  mov     rdi, [rsp+20h+arg_18]
0x1801accdd  mov     rsi, [rsp+20h+arg_10]
0x1801acce2  add     rsp, 20h
0x1801acce6  pop     r15
0x1801acce8  pop     r14
0x1801accea  pop     r13
0x1801accec  pop     r12
0x1801accee  pop     rbp
0x1801accef  retn
```
