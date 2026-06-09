# sqlite3CreateFunc

- ea: `0x1800309c0`
- end: `0x180030cba`
- name: `sqlite3CreateFunc`
- size: `762`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180030858`
- `0x1800309c0`
- `0x180097ac8`
- `0x18009b560`

## callees

- `0x18001eb90`
- `0x180020928`
- `0x1800257e0`
- `0x1800309c0`
- `0x180030cc0`
- `0x180031058`
- `0x180031f78`

## string_xrefs

- `0x180030c9b`: `unable to delete/modify user-function due to active statements`

## pseudocode

```c
__int64 __fastcall sqlite3CreateFunc(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        int a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        _DWORD *a11)
{
  __int64 v15; // rdi
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r9
  __int64 v19; // r10
  int v20; // r13d
  int v21; // ebx
  int v22; // r13d
  char *Function; // rax
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 v26; // rax
  __int64 v27; // rbx
  __int64 result; // rax
  unsigned int v29; // ebx
  int v30; // [rsp+20h] [rbp-88h]
  int v31; // [rsp+20h] [rbp-88h]

  if ( !a2
    || (v15 = a6) != 0 && a8
    || (a8 == 0) != (a7 == 0)
    || (a9 == 0) != (a10 == 0)
    || a3 + 1 > 0x80
    || (int)sqlite3Strlen30(a2) > 255 )
  {
    v29 = 21;
    sqlite3_log(
      21,
      "%s at line %d of [%.10s]",
      "misuse",
      182119,
      "18a3cf29885901ce73120761875ccdd0e3704e39307ee4f79d503ddacc55c7af");
    return v29;
  }
  v20 = a4 & 0x1380800;
  v21 = a4 & 7;
  v22 = v20 ^ 0x200000;
  if ( v21 == 1 || v21 == 2 || v21 == 3 )
  {
LABEL_11:
    LOBYTE(v18) = v21;
    LOBYTE(v30) = 0;
    Function = (char *)sqlite3FindFunction(a1, a2, a3, v18, v30);
    if ( Function && (*((_DWORD *)Function + 1) & 3) == v21 && *Function == a3 )
    {
      if ( *(_DWORD *)(a1 + 216) )
      {
        v29 = 5;
        sqlite3ErrorWithMsg(a1, 5, "unable to delete/modify user-function due to active statements");
        return v29;
      }
      sqlite3ExpirePreparedStatements(a1, 0, v24);
    }
    else if ( !a6 && !a8 )
    {
      return 0;
    }
    LOBYTE(v25) = v21;
    LOBYTE(v31) = 1;
    v26 = sqlite3FindFunction(a1, a2, a3, v25, v31);
    v27 = v26;
    if ( !v26 )
      return 7;
    functionDestroy(a1, v26);
    if ( a11 )
      ++*a11;
    *(_DWORD *)(v27 + 4) &= 3u;
    *(_DWORD *)(v27 + 4) |= v22;
    *(_QWORD *)(v27 + 40) = a9;
    if ( !a6 )
      v15 = a7;
    *(_QWORD *)(v27 + 48) = a10;
    *(_QWORD *)(v27 + 24) = v15;
    *(_QWORD *)(v27 + 8) = a5;
    *(_QWORD *)(v27 + 64) = a11;
    *(_QWORD *)(v27 + 32) = a8;
    *(_BYTE *)v27 = a3;
    return 0;
  }
  if ( v21 == 4 )
  {
    v21 = 2;
    goto LABEL_11;
  }
  if ( v21 != 5 )
  {
    v21 = 1;
    goto LABEL_11;
  }
  result = sqlite3CreateFunc(a1, a2, a3, (v22 | 1) ^ 0x200000u, a5, a6, v16, a8, v17, v19, (__int64)a11);
  if ( !(_DWORD)result )
  {
    result = sqlite3CreateFunc(a1, a2, a3, (v22 | 2) ^ 0x200000u, a5, a6, a7, a8, a9, a10, (__int64)a11);
    if ( !(_DWORD)result )
    {
      v21 = 3;
      goto LABEL_11;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800309c0  push    rbx
0x1800309c2  push    rbp
0x1800309c3  push    rsi
0x1800309c4  push    rdi
0x1800309c5  push    r12
0x1800309c7  push    r13
0x1800309c9  push    r14
0x1800309cb  push    r15
0x1800309cd  sub     rsp, 68h
0x1800309d1  mov     ebx, r9d
0x1800309d4  mov     r14d, r8d
0x1800309d7  mov     r15, rdx
0x1800309da  mov     rsi, rcx
0x1800309dd  test    rdx, rdx
0x1800309e0  jz      loc_180030B66
0x1800309e6  mov     rdi, [rsp+0A8h+arg_28]
0x1800309ee  mov     rbp, [rsp+0A8h+arg_38]
0x1800309f6  test    rdi, rdi
0x1800309f9  jz      short loc_180030A04
0x1800309fb  test    rbp, rbp
0x1800309fe  jnz     loc_180030B66
0x180030a04  mov     rdx, [rsp+0A8h+arg_30]
0x180030a0c  xor     ecx, ecx
0x180030a0e  test    rdx, rdx
0x180030a11  setz    cl
0x180030a14  xor     eax, eax
0x180030a16  test    rbp, rbp
0x180030a19  setz    al
0x180030a1c  cmp     eax, ecx
0x180030a1e  jnz     loc_180030B66
0x180030a24  mov     r8, [rsp+0A8h+arg_40]
0x180030a2c  xor     ecx, ecx
0x180030a2e  mov     r10, [rsp+0A8h+arg_48]
0x180030a36  test    r8, r8
0x180030a39  setz    cl
0x180030a3c  xor     eax, eax
0x180030a3e  test    r10, r10
0x180030a41  setz    al
0x180030a44  cmp     ecx, eax
0x180030a46  jnz     loc_180030B66
0x180030a4c  lea     eax, [r14+1]
0x180030a50  cmp     eax, 80h
0x180030a55  ja      loc_180030B66
0x180030a5b  mov     rcx, r15
0x180030a5e  call    sqlite3Strlen30
0x180030a63  cmp     eax, 0FFh
0x180030a68  jg      loc_180030B66
0x180030a6e  mov     r12, [rsp+0A8h+arg_50]
0x180030a76  mov     r13d, ebx
0x180030a79  and     r13d, 1380800h
0x180030a80  and     ebx, 7
0x180030a83  mov     r11d, 200000h
0x180030a89  mov     ecx, ebx
0x180030a8b  xor     r13d, r11d
0x180030a8e  sub     ecx, 1
0x180030a91  jz      short loc_180030AA1
0x180030a93  sub     ecx, 1
0x180030a96  jz      short loc_180030AA1
0x180030a98  sub     ecx, 1
0x180030a9b  jnz     loc_180030B96
0x180030aa1  mov     r9b, bl
0x180030aa4  mov     byte ptr [rsp+0A8h+var_88], 0
0x180030aa9  mov     r8d, r14d
0x180030aac  mov     rdx, r15
0x180030aaf  mov     rcx, rsi
0x180030ab2  call    sqlite3FindFunction
0x180030ab7  test    rax, rax
0x180030aba  jnz     loc_180030C70
0x180030ac0  test    rdi, rdi
0x180030ac3  jz      loc_180030B5C
0x180030ac9  mov     r9b, bl
0x180030acc  mov     byte ptr [rsp+0A8h+var_88], 1
0x180030ad1  mov     r8d, r14d
0x180030ad4  mov     rdx, r15
0x180030ad7  mov     rcx, rsi
0x180030ada  call    sqlite3FindFunction
0x180030adf  mov     rbx, rax
0x180030ae2  test    rax, rax
0x180030ae5  jz      short loc_180030B55
0x180030ae7  mov     rdx, rax
0x180030aea  mov     rcx, rsi
0x180030aed  call    functionDestroy
0x180030af2  test    r12, r12
0x180030af5  jz      short loc_180030AFB
0x180030af7  inc     dword ptr [r12]
0x180030afb  and     dword ptr [rbx+4], 3
0x180030aff  mov     rax, [rsp+0A8h+arg_40]
0x180030b07  or      [rbx+4], r13d
0x180030b0b  mov     [rbx+28h], rax
0x180030b0f  test    rdi, rdi
0x180030b12  mov     rax, [rsp+0A8h+arg_48]
0x180030b1a  cmovz   rdi, [rsp+0A8h+arg_30]
0x180030b23  mov     [rbx+30h], rax
0x180030b27  mov     rax, [rsp+0A8h+arg_20]
0x180030b2f  mov     [rbx+18h], rdi
0x180030b33  mov     [rbx+8], rax
0x180030b37  mov     [rbx+40h], r12
0x180030b3b  mov     [rbx+20h], rbp
0x180030b3f  mov     [rbx], r14b
0x180030b42  xor     eax, eax
0x180030b44  add     rsp, 68h
0x180030b48  pop     r15
0x180030b4a  pop     r14
0x180030b4c  pop     r13
0x180030b4e  pop     r12
0x180030b50  pop     rdi
0x180030b51  pop     rsi
0x180030b52  pop     rbp
0x180030b53  pop     rbx
0x180030b54  retn
0x180030b55  mov     eax, 7
0x180030b5a  jmp     short loc_180030B44
0x180030b5c  test    rbp, rbp
0x180030b5f  jz      short loc_180030B42
0x180030b61  jmp     loc_180030AC9
0x180030b66  lea     rax, a20240523134606+14h; "18a3cf29885901ce73120761875ccdd0e3704e3"...
0x180030b6d  mov     ebx, 15h
0x180030b72  mov     ecx, ebx
0x180030b74  mov     [rsp+0A8h+var_88], rax
0x180030b79  mov     r9d, 2C767h
0x180030b7f  lea     r8, aMisuse; "misuse"
0x180030b86  lea     rdx, aSAtLineDOf10s; "%s at line %d of [%.10s]"
0x180030b8d  call    sqlite3_log
0x180030b92  mov     eax, ebx
0x180030b94  jmp     short loc_180030B44
0x180030b96  sub     ecx, 1
0x180030b99  jz      loc_180030C66
0x180030b9f  cmp     ecx, 1
0x180030ba2  jz      short loc_180030BAE
0x180030ba4  mov     ebx, 1
0x180030ba9  jmp     loc_180030AA1
0x180030bae  mov     rax, [rsp+0A8h+arg_20]
0x180030bb6  mov     r9d, r13d
0x180030bb9  mov     [rsp+0A8h+var_58], r12
0x180030bbe  or      r9d, 1
0x180030bc2  mov     [rsp+0A8h+var_60], r10
0x180030bc7  xor     r9d, r11d
0x180030bca  mov     [rsp+0A8h+var_68], r8
0x180030bcf  mov     rcx, rsi
0x180030bd2  mov     [rsp+0A8h+var_70], rbp
0x180030bd7  mov     r8d, r14d
0x180030bda  mov     [rsp+0A8h+var_78], rdx
0x180030bdf  mov     rdx, r15
0x180030be2  mov     [rsp+0A8h+var_80], rdi
0x180030be7  mov     [rsp+0A8h+var_88], rax
0x180030bec  call    sqlite3CreateFunc
0x180030bf1  test    eax, eax
0x180030bf3  jnz     loc_180030B44
0x180030bf9  mov     rax, [rsp+0A8h+arg_48]
0x180030c01  mov     r9d, r13d
0x180030c04  mov     [rsp+0A8h+var_58], r12
0x180030c09  or      r9d, 2
0x180030c0d  mov     [rsp+0A8h+var_60], rax
0x180030c12  btc     r9d, 15h
0x180030c17  mov     rax, [rsp+0A8h+arg_40]
0x180030c1f  mov     r8d, r14d
0x180030c22  mov     [rsp+0A8h+var_68], rax
0x180030c27  mov     rdx, r15
0x180030c2a  mov     rax, [rsp+0A8h+arg_30]
0x180030c32  mov     rcx, rsi
0x180030c35  mov     [rsp+0A8h+var_70], rbp
0x180030c3a  mov     [rsp+0A8h+var_78], rax
0x180030c3f  mov     rax, [rsp+0A8h+arg_20]
0x180030c47  mov     [rsp+0A8h+var_80], rdi
0x180030c4c  mov     [rsp+0A8h+var_88], rax
0x180030c51  call    sqlite3CreateFunc
0x180030c56  test    eax, eax
0x180030c58  jnz     loc_180030B44
0x180030c5e  lea     ebx, [rax+3]
0x180030c61  jmp     loc_180030AA1
0x180030c66  mov     ebx, 2
0x180030c6b  jmp     loc_180030AA1
0x180030c70  mov     ecx, [rax+4]
0x180030c73  and     ecx, 3
0x180030c76  cmp     ecx, ebx
0x180030c78  jnz     loc_180030AC0
0x180030c7e  movsx   eax, byte ptr [rax]
0x180030c81  cmp     eax, r14d
0x180030c84  jnz     loc_180030AC0
0x180030c8a  cmp     dword ptr [rsi+0D8h], 0
0x180030c91  mov     rcx, rsi
0x180030c94  jz      short loc_180030CAE
0x180030c96  mov     ebx, 5
0x180030c9b  lea     r8, aUnableToDelete_0; "unable to delete/modify user-function d"...
0x180030ca2  mov     edx, ebx
0x180030ca4  call    sqlite3ErrorWithMsg
0x180030ca9  jmp     loc_180030B92
0x180030cae  xor     edx, edx
0x180030cb0  call    sqlite3ExpirePreparedStatements
0x180030cb5  jmp     loc_180030AC9
```
