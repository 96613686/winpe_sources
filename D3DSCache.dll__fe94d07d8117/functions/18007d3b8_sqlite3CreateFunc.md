# sqlite3CreateFunc

- ea: `0x18007d3b8`
- end: `0x18007d685`
- name: `sqlite3CreateFunc`
- size: `717`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18005b974`
- `0x18007d3b8`
- `0x1800895b0`
- `0x1800947e0`

## callees

- `0x18002b610`
- `0x18002b81c`
- `0x180038dc0`
- `0x18003a860`
- `0x18007d3b8`
- `0x18007edf0`
- `0x18007f0b4`

## string_xrefs

- `0x18007d5b1`: `unable to delete/modify user-function due to active statements`

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
  __int64 result; // rax
  char *Function; // rax
  __int64 v25; // r8
  __int64 v26; // r9
  __int64 v27; // rax
  __int64 v28; // rbx
  int v29; // [rsp+20h] [rbp-88h]
  int v30; // [rsp+20h] [rbp-88h]

  if ( !a2 )
    return sqlite3ReportError(21, 181688, "misuse");
  v15 = a6;
  if ( a6 )
  {
    if ( a8 )
      return sqlite3ReportError(21, 181688, "misuse");
  }
  if ( (a8 == 0) != (a7 == 0) || (a9 == 0) != (a10 == 0) || a3 + 1 > 0x80 || (int)sqlite3Strlen30(a2, a7, a9) > 255 )
    return sqlite3ReportError(21, 181688, "misuse");
  v20 = a4 & 0x1380800;
  v21 = a4 & 7;
  v22 = v20 ^ 0x200000;
  if ( v21 == 1 || v21 == 2 || v21 == 3 )
  {
LABEL_18:
    LOBYTE(v18) = v21;
    LOBYTE(v29) = 0;
    Function = (char *)sqlite3FindFunction(a1, a2, a3, v18, v29);
    if ( Function && (*((_DWORD *)Function + 1) & 3) == v21 && *Function == a3 )
    {
      if ( *(_DWORD *)(a1 + 216) )
      {
        sqlite3ErrorWithMsg(a1, 5, "unable to delete/modify user-function due to active statements", v26);
        return 5;
      }
      sqlite3ExpirePreparedStatements(a1, 0, v25);
    }
    else if ( !a6 && !a8 )
    {
      return 0;
    }
    LOBYTE(v26) = v21;
    LOBYTE(v30) = 1;
    v27 = sqlite3FindFunction(a1, a2, a3, v26, v30);
    v28 = v27;
    if ( !v27 )
      return 7;
    functionDestroy(a1, v27);
    if ( a11 )
      ++*a11;
    *(_DWORD *)(v28 + 4) &= 3u;
    *(_DWORD *)(v28 + 4) |= v22;
    *(_QWORD *)(v28 + 40) = a9;
    if ( !a6 )
      v15 = a7;
    *(_QWORD *)(v28 + 48) = a10;
    *(_QWORD *)(v28 + 24) = v15;
    *(_QWORD *)(v28 + 8) = a5;
    *(_QWORD *)(v28 + 64) = a11;
    *(_QWORD *)(v28 + 32) = a8;
    *(_BYTE *)v28 = a3;
    return 0;
  }
  if ( v21 == 4 )
  {
    v21 = 2;
    goto LABEL_18;
  }
  if ( v21 != 5 )
  {
    v21 = 1;
    goto LABEL_18;
  }
  result = sqlite3CreateFunc(a1, a2, a3, (v22 | 1) ^ 0x200000u, a5, a6, v16, a8, v17, v19, (__int64)a11);
  if ( !(_DWORD)result )
  {
    result = sqlite3CreateFunc(a1, a2, a3, (v22 | 2) ^ 0x200000u, a5, a6, a7, a8, a9, a10, (__int64)a11);
    if ( !(_DWORD)result )
    {
      v21 = 3;
      goto LABEL_18;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18007d3b8  push    rbx
0x18007d3ba  push    rbp
0x18007d3bb  push    rsi
0x18007d3bc  push    rdi
0x18007d3bd  push    r12
0x18007d3bf  push    r13
0x18007d3c1  push    r14
0x18007d3c3  push    r15
0x18007d3c5  sub     rsp, 68h
0x18007d3c9  mov     ebx, r9d
0x18007d3cc  mov     r14d, r8d
0x18007d3cf  mov     r15, rdx
0x18007d3d2  mov     rsi, rcx
0x18007d3d5  test    rdx, rdx
0x18007d3d8  jz      loc_18007D65E
0x18007d3de  mov     rdi, [rsp+0A8h+arg_28]
0x18007d3e6  mov     rbp, [rsp+0A8h+arg_38]
0x18007d3ee  test    rdi, rdi
0x18007d3f1  jz      short loc_18007D3FC
0x18007d3f3  test    rbp, rbp
0x18007d3f6  jnz     loc_18007D65E
0x18007d3fc  mov     rdx, [rsp+0A8h+arg_30]
0x18007d404  xor     ecx, ecx
0x18007d406  test    rdx, rdx
0x18007d409  setz    cl
0x18007d40c  xor     eax, eax
0x18007d40e  test    rbp, rbp
0x18007d411  setz    al
0x18007d414  cmp     eax, ecx
0x18007d416  jnz     loc_18007D65E
0x18007d41c  mov     r8, [rsp+0A8h+arg_40]
0x18007d424  xor     ecx, ecx
0x18007d426  mov     r10, [rsp+0A8h+arg_48]
0x18007d42e  test    r8, r8
0x18007d431  setz    cl
0x18007d434  xor     eax, eax
0x18007d436  test    r10, r10
0x18007d439  setz    al
0x18007d43c  cmp     ecx, eax
0x18007d43e  jnz     loc_18007D65E
0x18007d444  lea     eax, [r14+1]
0x18007d448  cmp     eax, 80h
0x18007d44d  ja      loc_18007D65E
0x18007d453  mov     rcx, r15
0x18007d456  call    sqlite3Strlen30
0x18007d45b  cmp     eax, 0FFh
0x18007d460  jg      loc_18007D65E
0x18007d466  mov     r12, [rsp+0A8h+arg_50]
0x18007d46e  mov     r13d, ebx
0x18007d471  and     r13d, 1380800h
0x18007d478  and     ebx, 7
0x18007d47b  mov     r11d, 200000h
0x18007d481  mov     ecx, ebx
0x18007d483  xor     r13d, r11d
0x18007d486  sub     ecx, 1
0x18007d489  jz      loc_18007D573
0x18007d48f  sub     ecx, 1
0x18007d492  jz      loc_18007D573
0x18007d498  sub     ecx, 1
0x18007d49b  jz      loc_18007D573
0x18007d4a1  sub     ecx, 1
0x18007d4a4  jz      loc_18007D56E
0x18007d4aa  cmp     ecx, 1
0x18007d4ad  jz      short loc_18007D4B9
0x18007d4af  mov     ebx, 1
0x18007d4b4  jmp     loc_18007D573
0x18007d4b9  mov     rax, [rsp+0A8h+arg_20]
0x18007d4c1  mov     r9d, r13d
0x18007d4c4  mov     [rsp+0A8h+var_58], r12
0x18007d4c9  or      r9d, 1
0x18007d4cd  mov     [rsp+0A8h+var_60], r10
0x18007d4d2  xor     r9d, r11d
0x18007d4d5  mov     [rsp+0A8h+var_68], r8
0x18007d4da  mov     rcx, rsi
0x18007d4dd  mov     [rsp+0A8h+var_70], rbp
0x18007d4e2  mov     r8d, r14d
0x18007d4e5  mov     [rsp+0A8h+var_78], rdx
0x18007d4ea  mov     rdx, r15
0x18007d4ed  mov     [rsp+0A8h+var_80], rdi
0x18007d4f2  mov     [rsp+0A8h+var_88], rax
0x18007d4f7  call    sqlite3CreateFunc
0x18007d4fc  test    eax, eax
0x18007d4fe  jnz     loc_18007D674
0x18007d504  mov     rax, [rsp+0A8h+arg_48]
0x18007d50c  mov     r9d, r13d
0x18007d50f  mov     [rsp+0A8h+var_58], r12
0x18007d514  or      r9d, 2
0x18007d518  mov     [rsp+0A8h+var_60], rax
0x18007d51d  btc     r9d, 15h
0x18007d522  mov     rax, [rsp+0A8h+arg_40]
0x18007d52a  mov     r8d, r14d
0x18007d52d  mov     [rsp+0A8h+var_68], rax
0x18007d532  mov     rdx, r15
0x18007d535  mov     rax, [rsp+0A8h+arg_30]
0x18007d53d  mov     rcx, rsi
0x18007d540  mov     [rsp+0A8h+var_70], rbp
0x18007d545  mov     [rsp+0A8h+var_78], rax
0x18007d54a  mov     rax, [rsp+0A8h+arg_20]
0x18007d552  mov     [rsp+0A8h+var_80], rdi
0x18007d557  mov     [rsp+0A8h+var_88], rax
0x18007d55c  call    sqlite3CreateFunc
0x18007d561  test    eax, eax
0x18007d563  jnz     loc_18007D674
0x18007d569  lea     ebx, [rax+3]
0x18007d56c  jmp     short loc_18007D573
0x18007d56e  mov     ebx, 2
0x18007d573  mov     r9b, bl
0x18007d576  mov     byte ptr [rsp+0A8h+var_88], 0
0x18007d57b  mov     r8d, r14d
0x18007d57e  mov     rdx, r15
0x18007d581  mov     rcx, rsi
0x18007d584  call    sqlite3FindFunction
0x18007d589  test    rax, rax
0x18007d58c  jz      short loc_18007D5F3
0x18007d58e  mov     ecx, [rax+4]
0x18007d591  and     ecx, 3
0x18007d594  cmp     ecx, ebx
0x18007d596  jnz     short loc_18007D5F3
0x18007d598  movsx   eax, byte ptr [rax]
0x18007d59b  cmp     eax, r14d
0x18007d59e  jnz     short loc_18007D5F3
0x18007d5a0  cmp     dword ptr [rsi+0D8h], 0
0x18007d5a7  mov     rcx, rsi
0x18007d5aa  jz      short loc_18007D5C6
0x18007d5ac  mov     ebx, 5
0x18007d5b1  lea     r8, aUnableToDelete_0; "unable to delete/modify user-function d"...
0x18007d5b8  mov     edx, ebx
0x18007d5ba  call    sqlite3ErrorWithMsg
0x18007d5bf  mov     eax, ebx
0x18007d5c1  jmp     loc_18007D674
0x18007d5c6  xor     edx, edx
0x18007d5c8  call    sqlite3ExpirePreparedStatements
0x18007d5cd  mov     r9b, bl
0x18007d5d0  mov     byte ptr [rsp+0A8h+var_88], 1
0x18007d5d5  mov     r8d, r14d
0x18007d5d8  mov     rdx, r15
0x18007d5db  mov     rcx, rsi
0x18007d5de  call    sqlite3FindFunction
0x18007d5e3  mov     rbx, rax
0x18007d5e6  test    rax, rax
0x18007d5e9  jnz     short loc_18007D601
0x18007d5eb  lea     eax, [rbx+7]
0x18007d5ee  jmp     loc_18007D674
0x18007d5f3  test    rdi, rdi
0x18007d5f6  jnz     short loc_18007D5CD
0x18007d5f8  test    rbp, rbp
0x18007d5fb  jnz     short loc_18007D5CD
0x18007d5fd  xor     eax, eax
0x18007d5ff  jmp     short loc_18007D674
0x18007d601  mov     rdx, rbx
0x18007d604  mov     rcx, rsi
0x18007d607  call    functionDestroy
0x18007d60c  test    r12, r12
0x18007d60f  jz      short loc_18007D615
0x18007d611  inc     dword ptr [r12]
0x18007d615  and     dword ptr [rbx+4], 3
0x18007d619  mov     rax, [rsp+0A8h+arg_40]
0x18007d621  or      [rbx+4], r13d
0x18007d625  mov     [rbx+28h], rax
0x18007d629  test    rdi, rdi
0x18007d62c  mov     rax, [rsp+0A8h+arg_48]
0x18007d634  cmovz   rdi, [rsp+0A8h+arg_30]
0x18007d63d  mov     [rbx+30h], rax
0x18007d641  mov     rax, [rsp+0A8h+arg_20]
0x18007d649  mov     [rbx+18h], rdi
0x18007d64d  mov     [rbx+8], rax
0x18007d651  mov     [rbx+40h], r12
0x18007d655  mov     [rbx+20h], rbp
0x18007d659  mov     [rbx], r14b
0x18007d65c  jmp     short loc_18007D5FD
0x18007d65e  lea     r8, aMisuse; "misuse"
0x18007d665  mov     edx, 2C5B8h
0x18007d66a  mov     ecx, 15h
0x18007d66f  call    sqlite3ReportError
0x18007d674  add     rsp, 68h
0x18007d678  pop     r15
0x18007d67a  pop     r14
0x18007d67c  pop     r13
0x18007d67e  pop     r12
0x18007d680  pop     rdi
0x18007d681  pop     rsi
0x18007d682  pop     rbp
0x18007d683  pop     rbx
0x18007d684  retn
```
