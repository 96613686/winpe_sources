# jsonFunctionArgToBlob

- ea: `0x18004f658`
- end: `0x18004f880`
- name: `jsonFunctionArgToBlob`
- size: `552`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x18004f97c`

## callees

- `0x180002cf8`
- `0x18004ddbc`
- `0x18004e400`
- `0x18004f598`
- `0x18004f658`
- `0x1800716fc`
- `0x180092290`
- `0x18009b4ec`
- `0x18009c204`
- `0x1800ab280`
- `0x1800ae6c0`
- `0x1800ae720`

## string_xrefs

- `0x18004f6f8`: `JSON cannot hold BLOB values`
- `0x18004f761`: `malformed JSON`

## pseudocode

```c
__int64 __fastcall jsonFunctionArgToBlob(_DWORD *a1, __int64 a2, _QWORD *a3)
{
  int v6; // esi
  __int64 v7; // rdx
  int v8; // esi
  int v9; // esi
  int v10; // esi
  __int64 v12; // r9
  __int64 v13; // rcx
  __int64 v14; // rsi
  unsigned int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // r9
  __int64 v18; // rcx
  __int64 v19; // r9
  __int64 v20; // r8
  double v21; // xmm0_8
  unsigned int v22; // esi
  const char *v23; // rax
  unsigned int v24; // eax
  __int64 v25; // rdx
  unsigned int v26; // eax
  __int64 v27; // rdx

  v6 = *((unsigned __int8 *)qword_1800FE430 + (*(_WORD *)(a2 + 20) & 0x3F));
  memset_0(a3, 0, 0x48u);
  v7 = *(_QWORD *)(*(_QWORD *)a1 + 24LL);
  a3[3] = v7;
  v8 = v6 - 1;
  if ( !v8 )
  {
    v26 = sqlite3_value_bytes(a2);
    LOBYTE(v27) = 1;
    v22 = v26;
    v23 = (const char *)sqlite3ValueText(a2, v27);
    if ( !v23 )
      return 1;
    LOBYTE(v16) = 3;
LABEL_30:
    v20 = v22;
    v19 = (__int64)v23;
LABEL_31:
    jsonBlobAppendNode(a3, v16, v20, v19);
    goto LABEL_32;
  }
  v9 = v8 - 1;
  if ( !v9 )
  {
    v21 = sqlite3VdbeRealValue(a2);
    v16 = 0x7FF0000000000000LL;
    if ( (*(_QWORD *)&v21 & 0xFFFFFFFFFFFFFLL) != 0 && (*(_QWORD *)&v21 & 0x7FF0000000000000LL) == 0x7FF0000000000000LL )
    {
      LOBYTE(v16) = 0;
      v22 = 0;
      v23 = 0;
    }
    else
    {
      v24 = sqlite3_value_bytes(a2);
      LOBYTE(v25) = 1;
      v22 = v24;
      v23 = (const char *)sqlite3ValueText(a2, v25);
      if ( !v23 )
        return 1;
      if ( *v23 == 73 )
      {
        v16 = 5;
        v23 = "9e999";
        v22 = 5;
      }
      else
      {
        if ( *v23 == 45 && v23[1] == 73 )
        {
          v22 = 6;
          v23 = "-9e999";
        }
        v16 = 5;
      }
    }
    goto LABEL_30;
  }
  v10 = v9 - 1;
  if ( !v10 )
  {
    LOBYTE(v7) = 1;
    v14 = sqlite3ValueText(a2, v7);
    v15 = sqlite3_value_bytes(a2);
    if ( !v14 )
      return 1;
    if ( (*(_WORD *)(a2 + 20) & 0x800) != 0 && *(_BYTE *)(a2 + 23) == 74 )
    {
      a3[2] = v14;
      *((_DWORD *)a3 + 8) = v15;
      if ( (unsigned int)jsonConvertTextToBlob(a3, a1) )
      {
        v18 = *(_QWORD *)a1;
        a1[9] = 1;
        LOBYTE(v17) = 1;
        sqlite3VdbeMemSetStr(v18, "malformed JSON", -1, v17, -1);
        if ( *a3 )
          sqlite3DbFreeNN(a3[3]);
        memset_0(a3, 0, 0x48u);
        return 1;
      }
      goto LABEL_32;
    }
    v19 = v14;
    v20 = v15;
    LOBYTE(v16) = 10;
    goto LABEL_31;
  }
  if ( v10 != 1 )
  {
    *((_DWORD *)a3 + 2) = 1;
    *a3 = qword_18010F8A0;
    return 0;
  }
  if ( !(unsigned int)jsonFuncArgMightBeBinary(a2) )
  {
    v13 = *(_QWORD *)a1;
    a1[9] = 1;
    LOBYTE(v12) = 1;
    sqlite3VdbeMemSetStr(v13, "JSON cannot hold BLOB values", -1, v12, -1);
    return 1;
  }
  *a3 = sqlite3_value_blob(a2);
  *((_DWORD *)a3 + 2) = sqlite3_value_bytes(a2);
LABEL_32:
  if ( !*((_BYTE *)a3 + 47) )
    return 0;
  sqlite3_result_error_nomem(a1);
  return 1;
}

```

## disassembly

```asm
0x18004f658  push    rbx
0x18004f65a  push    rbp
0x18004f65b  push    rsi
0x18004f65c  push    rdi
0x18004f65d  push    r14
0x18004f65f  sub     rsp, 30h
0x18004f663  movzx   eax, word ptr [rdx+14h]
0x18004f667  mov     r14, rcx
0x18004f66a  mov     rbx, r8
0x18004f66d  lea     rcx, qword_1800FE430
0x18004f674  and     eax, 3Fh
0x18004f677  mov     rdi, rdx
0x18004f67a  xor     edx, edx; Val
0x18004f67c  movzx   esi, byte ptr [rax+rcx]
0x18004f680  mov     rcx, rbx; void *
0x18004f683  lea     r8d, [rdx+48h]; Size
0x18004f687  call    memset_0
0x18004f68c  mov     rax, [r14]
0x18004f68f  mov     ebp, 1
0x18004f694  mov     rdx, [rax+18h]
0x18004f698  mov     [rbx+18h], rdx
0x18004f69c  sub     esi, ebp
0x18004f69e  jz      loc_18004F83B
0x18004f6a4  sub     esi, ebp
0x18004f6a6  jz      loc_18004F7AE
0x18004f6ac  sub     esi, ebp
0x18004f6ae  jz      short loc_18004F718
0x18004f6b0  cmp     esi, ebp
0x18004f6b2  jz      short loc_18004F6CE
0x18004f6b4  lea     rax, qword_18010F8A0
0x18004f6bb  mov     [rbx+8], ebp
0x18004f6be  mov     [rbx], rax
0x18004f6c1  xor     eax, eax
0x18004f6c3  add     rsp, 30h
0x18004f6c7  pop     r14
0x18004f6c9  pop     rdi
0x18004f6ca  pop     rsi
0x18004f6cb  pop     rbp
0x18004f6cc  pop     rbx
0x18004f6cd  retn
0x18004f6ce  mov     rcx, rdi
0x18004f6d1  call    jsonFuncArgMightBeBinary
0x18004f6d6  test    eax, eax
0x18004f6d8  jz      short loc_18004F6F5
0x18004f6da  mov     rcx, rdi
0x18004f6dd  call    sqlite3_value_blob
0x18004f6e2  mov     rcx, rdi
0x18004f6e5  mov     [rbx], rax
0x18004f6e8  call    sqlite3_value_bytes
0x18004f6ed  mov     [rbx+8], eax
0x18004f6f0  jmp     loc_18004F869
0x18004f6f5  mov     rcx, [r14]
0x18004f6f8  lea     rdx, aJsonCannotHold; "JSON cannot hold BLOB values"
0x18004f6ff  or      r8, 0FFFFFFFFFFFFFFFFh
0x18004f703  mov     [r14+24h], ebp
0x18004f707  mov     r9b, bpl
0x18004f70a  mov     [rsp+58h+var_38], r8
0x18004f70f  call    sqlite3VdbeMemSetStr
0x18004f714  mov     eax, ebp
0x18004f716  jmp     short loc_18004F6C3
0x18004f718  mov     dl, bpl
0x18004f71b  mov     rcx, rdi
0x18004f71e  call    sqlite3ValueText
0x18004f723  mov     rcx, rdi
0x18004f726  mov     rsi, rax
0x18004f729  call    sqlite3_value_bytes
0x18004f72e  test    rsi, rsi
0x18004f731  jz      short loc_18004F714
0x18004f733  mov     ecx, 800h
0x18004f738  test    [rdi+14h], cx
0x18004f73c  jz      short loc_18004F7A1
0x18004f73e  cmp     byte ptr [rdi+17h], 4Ah ; 'J'
0x18004f742  jnz     short loc_18004F7A1
0x18004f744  mov     rdx, r14
0x18004f747  mov     [rbx+10h], rsi
0x18004f74b  mov     rcx, rbx
0x18004f74e  mov     [rbx+20h], eax
0x18004f751  call    jsonConvertTextToBlob
0x18004f756  test    eax, eax
0x18004f758  jz      loc_18004F869
0x18004f75e  mov     rcx, [r14]
0x18004f761  lea     rdx, aMalformedJson; "malformed JSON"
0x18004f768  or      r8, 0FFFFFFFFFFFFFFFFh
0x18004f76c  mov     [r14+24h], ebp
0x18004f770  mov     r9b, bpl
0x18004f773  mov     [rsp+58h+var_38], r8
0x18004f778  call    sqlite3VdbeMemSetStr
0x18004f77d  mov     rdx, [rbx]
0x18004f780  test    rdx, rdx
0x18004f783  jz      short loc_18004F78E
0x18004f785  mov     rcx, [rbx+18h]
0x18004f789  call    sqlite3DbFreeNN
0x18004f78e  xor     edx, edx; Val
0x18004f790  mov     rcx, rbx; void *
0x18004f793  lea     r8d, [rdx+48h]; Size
0x18004f797  call    memset_0
0x18004f79c  jmp     loc_18004F714
0x18004f7a1  mov     r9, rsi
0x18004f7a4  mov     r8d, eax
0x18004f7a7  mov     dl, 0Ah
0x18004f7a9  jmp     loc_18004F861
0x18004f7ae  mov     rcx, rdi
0x18004f7b1  call    sqlite3VdbeRealValue
0x18004f7b6  movq    rax, xmm0
0x18004f7bb  mov     rcx, 0FFFFFFFFFFFFFh
0x18004f7c5  test    rcx, rax
0x18004f7c8  mov     rdx, 7FF0000000000000h
0x18004f7d2  setnz   cl
0x18004f7d5  and     rax, rdx
0x18004f7d8  cmp     rax, rdx
0x18004f7db  setz    al
0x18004f7de  test    al, cl
0x18004f7e0  jz      short loc_18004F7EA
0x18004f7e2  xor     dl, dl
0x18004f7e4  xor     esi, esi
0x18004f7e6  xor     eax, eax
0x18004f7e8  jmp     short loc_18004F85B
0x18004f7ea  mov     rcx, rdi
0x18004f7ed  call    sqlite3_value_bytes
0x18004f7f2  mov     dl, bpl
0x18004f7f5  mov     rcx, rdi
0x18004f7f8  mov     esi, eax
0x18004f7fa  call    sqlite3ValueText
0x18004f7ff  test    rax, rax
0x18004f802  jz      loc_18004F714
0x18004f808  cmp     byte ptr [rax], 49h ; 'I'
0x18004f80b  jnz     short loc_18004F81D
0x18004f80d  mov     edx, 5
0x18004f812  lea     rax, a9e999_0; "9e999"
0x18004f819  mov     esi, edx
0x18004f81b  jmp     short loc_18004F85B
0x18004f81d  cmp     byte ptr [rax], 2Dh ; '-'
0x18004f820  jnz     short loc_18004F834
0x18004f822  cmp     byte ptr [rax+1], 49h ; 'I'
0x18004f826  jnz     short loc_18004F834
0x18004f828  mov     esi, 6
0x18004f82d  lea     rax, a9e999; "-9e999"
0x18004f834  mov     edx, 5
0x18004f839  jmp     short loc_18004F85B
0x18004f83b  mov     rcx, rdi
0x18004f83e  call    sqlite3_value_bytes
0x18004f843  mov     dl, bpl
0x18004f846  mov     rcx, rdi
0x18004f849  mov     esi, eax
0x18004f84b  call    sqlite3ValueText
0x18004f850  test    rax, rax
0x18004f853  jz      loc_18004F714
0x18004f859  mov     dl, 3
0x18004f85b  mov     r8d, esi
0x18004f85e  mov     r9, rax
0x18004f861  mov     rcx, rbx
0x18004f864  call    jsonBlobAppendNode
0x18004f869  cmp     byte ptr [rbx+2Fh], 0
0x18004f86d  jz      loc_18004F6C1
0x18004f873  mov     rcx, r14
0x18004f876  call    sqlite3_result_error_nomem
0x18004f87b  jmp     loc_18004F714
```
