# sqlite3CreateFunc

- ea: `0x140052ac0`
- end: `0x140052dab`
- name: `sqlite3CreateFunc`
- size: `747`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1400267b8`
- `0x140052ac0`
- `0x14006b228`
- `0x140089010`

## callees

- `0x140052ac0`
- `0x140053e3c`
- `0x140056170`
- `0x14005622c`
- `0x14005a62c`
- `0x140063280`
- `0x1400a8010`

## string_xrefs

- `0x140052cc6`: `unable to delete/modify user-function due to active statements`

## pseudocode

```c
__int64 __fastcall sqlite3CreateFunc(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        _DWORD *a11)
{
  __int64 v14; // rsi
  __int64 v15; // rax
  int v16; // ebx
  int v17; // r12d
  __int64 result; // rax
  char *Function; // rax
  __int64 v20; // r9
  __int64 v21; // rax
  __int64 v22; // rbx
  __int64 v23; // rdi
  int v25; // [rsp+20h] [rbp-88h]
  int v26; // [rsp+20h] [rbp-88h]

  if ( !a2 )
    return sqlite3MisuseError(178251);
  v14 = a6;
  if ( a6 )
  {
    if ( a8 )
      return sqlite3MisuseError(178251);
  }
  if ( (a8 == 0) != (a7 == 0) )
    return sqlite3MisuseError(178251);
  if ( (a9 == 0) != (a10 == 0) )
    return sqlite3MisuseError(178251);
  if ( a3 + 1 > 0x80 )
    return sqlite3MisuseError(178251);
  v15 = -1;
  do
    ++v15;
  while ( *(_BYTE *)(a2 + v15) );
  if ( ((unsigned int)v15 & 0x3FFFFFFF) > 0xFF )
    return sqlite3MisuseError(178251);
  v16 = a4 & 7;
  v17 = a4 & 0x380800 ^ 0x200000;
  if ( v16 == 1 || (a4 & 7) == 2 || (a4 & 7) == 3 )
  {
LABEL_20:
    LOBYTE(a4) = v16;
    LOBYTE(v25) = 0;
    Function = (char *)sqlite3FindFunction(a1, a2, a3, a4, v25);
    if ( Function && (*((_DWORD *)Function + 1) & 3) == v16 && *Function == a3 )
    {
      if ( *(_DWORD *)(a1 + 216) )
      {
        sqlite3ErrorWithMsg(a1, 5, "unable to delete/modify user-function due to active statements");
        return 5;
      }
      sqlite3ExpirePreparedStatements(a1, 0);
    }
    else if ( !a6 && !a8 )
    {
      return 0;
    }
    LOBYTE(v20) = v16;
    LOBYTE(v26) = 1;
    v21 = sqlite3FindFunction(a1, a2, a3, v20, v26);
    v22 = v21;
    if ( !v21 )
      return 7;
    v23 = *(_QWORD *)(v21 + 64);
    if ( v23 )
    {
      if ( (*(_DWORD *)v23)-- == 1 )
      {
        (*(void (__fastcall **)(_QWORD))(v23 + 8))(*(_QWORD *)(v23 + 16));
        sqlite3DbFreeNN(a1);
      }
    }
    if ( a11 )
      ++*a11;
    *(_DWORD *)(v22 + 4) &= 3u;
    *(_DWORD *)(v22 + 4) |= v17;
    *(_QWORD *)(v22 + 40) = a9;
    if ( !a6 )
      v14 = a7;
    *(_QWORD *)(v22 + 48) = a10;
    *(_QWORD *)(v22 + 24) = v14;
    *(_QWORD *)(v22 + 8) = a5;
    *(_QWORD *)(v22 + 64) = a11;
    *(_QWORD *)(v22 + 32) = a8;
    *(_BYTE *)v22 = a3;
    return 0;
  }
  if ( (a4 & 7) == 4 )
  {
    v16 = 2;
    goto LABEL_20;
  }
  if ( (a4 & 7) != 5 )
  {
    v16 = 1;
    goto LABEL_20;
  }
  result = sqlite3CreateFunc(a1, a2, a3, (v17 | 1) ^ 0x200000u, a5, a6, a7, a8, a9, a10, (__int64)a11);
  if ( !(_DWORD)result )
  {
    result = sqlite3CreateFunc(a1, a2, a3, (v17 | 2) ^ 0x200000u, a5, a6, a7, a8, a9, a10, (__int64)a11);
    if ( !(_DWORD)result )
    {
      v16 = 3;
      goto LABEL_20;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140052ac0  push    rbx
0x140052ac2  push    rbp
0x140052ac3  push    rsi
0x140052ac4  push    rdi
0x140052ac5  push    r12
0x140052ac7  push    r13
0x140052ac9  push    r14
0x140052acb  push    r15
0x140052acd  sub     rsp, 68h
0x140052ad1  mov     ebx, r9d
0x140052ad4  mov     r13d, r8d
0x140052ad7  mov     rdi, rdx
0x140052ada  mov     rbp, rcx
0x140052add  test    rdx, rdx
0x140052ae0  jz      loc_140052D90
0x140052ae6  mov     rsi, [rsp+0A8h+arg_28]
0x140052aee  mov     r14, [rsp+0A8h+arg_38]
0x140052af6  test    rsi, rsi
0x140052af9  jz      short loc_140052B04
0x140052afb  test    r14, r14
0x140052afe  jnz     loc_140052D90
0x140052b04  mov     rdx, [rsp+0A8h+arg_30]
0x140052b0c  xor     ecx, ecx
0x140052b0e  test    rdx, rdx
0x140052b11  setz    cl
0x140052b14  xor     eax, eax
0x140052b16  test    r14, r14
0x140052b19  setz    al
0x140052b1c  cmp     eax, ecx
0x140052b1e  jnz     loc_140052D90
0x140052b24  mov     r8, [rsp+0A8h+arg_40]
0x140052b2c  xor     ecx, ecx
0x140052b2e  mov     r10, [rsp+0A8h+arg_48]
0x140052b36  test    r8, r8
0x140052b39  setz    cl
0x140052b3c  xor     eax, eax
0x140052b3e  test    r10, r10
0x140052b41  setz    al
0x140052b44  cmp     ecx, eax
0x140052b46  jnz     loc_140052D90
0x140052b4c  lea     eax, [r13+1]
0x140052b50  cmp     eax, 80h
0x140052b55  ja      loc_140052D90
0x140052b5b  or      rax, 0FFFFFFFFFFFFFFFFh
0x140052b5f  inc     rax
0x140052b62  cmp     byte ptr [rdi+rax], 0
0x140052b66  jnz     short loc_140052B5F
0x140052b68  and     eax, 3FFFFFFFh
0x140052b6d  cmp     eax, 0FFh
0x140052b72  ja      loc_140052D90
0x140052b78  mov     r15, [rsp+0A8h+arg_50]
0x140052b80  mov     r12d, ebx
0x140052b83  and     r12d, 380800h
0x140052b8a  and     ebx, 7
0x140052b8d  mov     r11d, 200000h
0x140052b93  mov     ecx, ebx
0x140052b95  xor     r12d, r11d
0x140052b98  sub     ecx, 1
0x140052b9b  jz      loc_140052C85
0x140052ba1  sub     ecx, 1
0x140052ba4  jz      loc_140052C85
0x140052baa  sub     ecx, 1
0x140052bad  jz      loc_140052C85
0x140052bb3  sub     ecx, 1
0x140052bb6  jz      loc_140052C80
0x140052bbc  cmp     ecx, 1
0x140052bbf  jz      short loc_140052BCB
0x140052bc1  mov     ebx, 1
0x140052bc6  jmp     loc_140052C85
0x140052bcb  mov     rax, [rsp+0A8h+arg_20]
0x140052bd3  mov     r9d, r12d
0x140052bd6  mov     [rsp+0A8h+var_58], r15
0x140052bdb  or      r9d, 1
0x140052bdf  mov     [rsp+0A8h+var_60], r10
0x140052be4  xor     r9d, r11d
0x140052be7  mov     [rsp+0A8h+var_68], r8
0x140052bec  mov     rcx, rbp
0x140052bef  mov     [rsp+0A8h+var_70], r14
0x140052bf4  mov     r8d, r13d
0x140052bf7  mov     [rsp+0A8h+var_78], rdx
0x140052bfc  mov     rdx, rdi
0x140052bff  mov     [rsp+0A8h+var_80], rsi
0x140052c04  mov     [rsp+0A8h+var_88], rax
0x140052c09  call    sqlite3CreateFunc
0x140052c0e  test    eax, eax
0x140052c10  jnz     loc_140052D9A
0x140052c16  mov     rax, [rsp+0A8h+arg_48]
0x140052c1e  mov     r9d, r12d
0x140052c21  mov     [rsp+0A8h+var_58], r15
0x140052c26  or      r9d, 2
0x140052c2a  mov     [rsp+0A8h+var_60], rax
0x140052c2f  btc     r9d, 15h
0x140052c34  mov     rax, [rsp+0A8h+arg_40]
0x140052c3c  mov     r8d, r13d
0x140052c3f  mov     [rsp+0A8h+var_68], rax
0x140052c44  mov     rdx, rdi
0x140052c47  mov     rax, [rsp+0A8h+arg_30]
0x140052c4f  mov     rcx, rbp
0x140052c52  mov     [rsp+0A8h+var_70], r14
0x140052c57  mov     [rsp+0A8h+var_78], rax
0x140052c5c  mov     rax, [rsp+0A8h+arg_20]
0x140052c64  mov     [rsp+0A8h+var_80], rsi
0x140052c69  mov     [rsp+0A8h+var_88], rax
0x140052c6e  call    sqlite3CreateFunc
0x140052c73  test    eax, eax
0x140052c75  jnz     loc_140052D9A
0x140052c7b  lea     ebx, [rax+3]
0x140052c7e  jmp     short loc_140052C85
0x140052c80  mov     ebx, 2
0x140052c85  mov     r9b, bl
0x140052c88  mov     byte ptr [rsp+0A8h+var_88], 0
0x140052c8d  mov     r8d, r13d
0x140052c90  mov     rdx, rdi
0x140052c93  mov     rcx, rbp
0x140052c96  call    sqlite3FindFunction
0x140052c9b  mov     rcx, rax
0x140052c9e  test    rax, rax
0x140052ca1  jz      short loc_140052D08
0x140052ca3  mov     eax, [rax+4]
0x140052ca6  and     eax, 3
0x140052ca9  cmp     eax, ebx
0x140052cab  jnz     short loc_140052D08
0x140052cad  movsx   eax, byte ptr [rcx]
0x140052cb0  cmp     eax, r13d
0x140052cb3  jnz     short loc_140052D08
0x140052cb5  cmp     dword ptr [rbp+0D8h], 0
0x140052cbc  mov     rcx, rbp
0x140052cbf  jz      short loc_140052CDB
0x140052cc1  mov     ebx, 5
0x140052cc6  lea     r8, aUnableToDelete_0; "unable to delete/modify user-function d"...
0x140052ccd  mov     edx, ebx
0x140052ccf  call    sqlite3ErrorWithMsg
0x140052cd4  mov     eax, ebx
0x140052cd6  jmp     loc_140052D9A
0x140052cdb  xor     edx, edx
0x140052cdd  call    sqlite3ExpirePreparedStatements
0x140052ce2  mov     r9b, bl
0x140052ce5  mov     byte ptr [rsp+0A8h+var_88], 1
0x140052cea  mov     r8d, r13d
0x140052ced  mov     rdx, rdi
0x140052cf0  mov     rcx, rbp
0x140052cf3  call    sqlite3FindFunction
0x140052cf8  mov     rbx, rax
0x140052cfb  test    rax, rax
0x140052cfe  jnz     short loc_140052D19
0x140052d00  lea     eax, [rbx+7]
0x140052d03  jmp     loc_140052D9A
0x140052d08  test    rsi, rsi
0x140052d0b  jnz     short loc_140052CE2
0x140052d0d  test    r14, r14
0x140052d10  jnz     short loc_140052CE2
0x140052d12  xor     eax, eax
0x140052d14  jmp     loc_140052D9A
0x140052d19  mov     rdi, [rax+40h]
0x140052d1d  test    rdi, rdi
0x140052d20  jz      short loc_140052D3F
0x140052d22  sub     dword ptr [rdi], 1
0x140052d25  jnz     short loc_140052D3F
0x140052d27  mov     rcx, [rdi+10h]
0x140052d2b  mov     rax, [rdi+8]
0x140052d2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140052d34  mov     rdx, rdi
0x140052d37  mov     rcx, rbp
0x140052d3a  call    sqlite3DbFreeNN
0x140052d3f  test    r15, r15
0x140052d42  jz      short loc_140052D47
0x140052d44  inc     dword ptr [r15]
0x140052d47  and     dword ptr [rbx+4], 3
0x140052d4b  mov     rax, [rsp+0A8h+arg_40]
0x140052d53  or      [rbx+4], r12d
0x140052d57  mov     [rbx+28h], rax
0x140052d5b  test    rsi, rsi
0x140052d5e  mov     rax, [rsp+0A8h+arg_48]
0x140052d66  cmovz   rsi, [rsp+0A8h+arg_30]
0x140052d6f  mov     [rbx+30h], rax
0x140052d73  mov     rax, [rsp+0A8h+arg_20]
0x140052d7b  mov     [rbx+18h], rsi
0x140052d7f  mov     [rbx+8], rax
0x140052d83  mov     [rbx+40h], r15
0x140052d87  mov     [rbx+20h], r14
0x140052d8b  mov     [rbx], r13b
0x140052d8e  jmp     short loc_140052D12
0x140052d90  mov     ecx, 2B84Bh
0x140052d95  call    sqlite3MisuseError
0x140052d9a  add     rsp, 68h
0x140052d9e  pop     r15
0x140052da0  pop     r14
0x140052da2  pop     r13
0x140052da4  pop     r12
0x140052da6  pop     rdi
0x140052da7  pop     rsi
0x140052da8  pop     rbp
0x140052da9  pop     rbx
0x140052daa  retn
```
