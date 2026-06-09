# jsonFunctionArgToBlob

- ea: `0x180074dcc`
- end: `0x180074fe0`
- name: `jsonFunctionArgToBlob`
- size: `532`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x180075144`

## callees

- `0x18000a9e0`
- `0x180027a20`
- `0x180028540`
- `0x180048d20`
- `0x180048d38`
- `0x180068190`
- `0x18006910e`
- `0x180073548`
- `0x180073c34`
- `0x180074d08`
- `0x180074dcc`
- `0x18008924c`
- `0x18008f3f0`
- `0x180090e20`

## string_xrefs

- `0x180074e73`: `JSON cannot hold BLOB values`
- `0x180074ed4`: `malformed JSON`

## pseudocode

```c
__int64 __fastcall jsonFunctionArgToBlob(__int64 a1, __int64 a2, __int64 *a3)
{
  int v6; // edi
  __int64 v7; // rdx
  int v8; // edi
  int v9; // edi
  int v10; // edi
  __int64 v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rdi
  unsigned int v17; // r14d
  int v18; // eax
  __int64 v19; // rdx
  __int64 *v20; // rcx
  const char *v21; // r9
  __int64 v22; // r8
  double v23; // xmm0_8
  unsigned int v24; // edi
  const char *v25; // rax
  unsigned int v26; // eax
  __int64 v27; // rdx
  unsigned int v28; // eax
  __int64 v29; // rdx

  v6 = byte_18009EC50[*(_WORD *)(a2 + 20) & 0x3F];
  memset_0(a3, 0, 0x48u);
  a3[3] = sqlite3_context_db_handle(a1);
  v8 = v6 - 1;
  if ( !v8 )
  {
    LOBYTE(v7) = 1;
    v28 = sqlite3ValueBytes(a2, v7);
    LOBYTE(v29) = 1;
    v24 = v28;
    v25 = (const char *)sqlite3ValueText(a2, v29);
    if ( !v25 )
      return 1;
    LOBYTE(v19) = 3;
LABEL_27:
    v20 = a3;
    v22 = v24;
    v21 = v25;
LABEL_28:
    jsonBlobAppendNode(v20, v19, v22, v21);
    goto LABEL_29;
  }
  v9 = v8 - 1;
  if ( !v9 )
  {
    v23 = sqlite3VdbeRealValue(a2);
    v19 = 0x7FF0000000000000LL;
    if ( (*(_QWORD *)&v23 & 0xFFFFFFFFFFFFFLL) != 0 && (*(_QWORD *)&v23 & 0x7FF0000000000000LL) == 0x7FF0000000000000LL )
    {
      LOBYTE(v19) = 0;
      v24 = 0;
      v25 = 0;
    }
    else
    {
      LOBYTE(v19) = 1;
      v26 = sqlite3ValueBytes(a2, v19);
      LOBYTE(v27) = 1;
      v24 = v26;
      v25 = (const char *)sqlite3ValueText(a2, v27);
      if ( !v25 )
        return 1;
      if ( *v25 == 73 )
      {
        v19 = 5;
        v25 = "9e999";
        v24 = 5;
      }
      else
      {
        if ( *v25 == 45 && v25[1] == 73 )
        {
          v24 = 6;
          v25 = "-9e999";
        }
        v19 = 5;
      }
    }
    goto LABEL_27;
  }
  v10 = v9 - 1;
  if ( !v10 )
  {
    LOBYTE(v7) = 1;
    v14 = sqlite3ValueText(a2, v7);
    LOBYTE(v15) = 1;
    v16 = v14;
    v17 = sqlite3ValueBytes(a2, v15);
    if ( !v16 )
      return 1;
    v18 = sqlite3_value_subtype(a2);
    v20 = a3;
    if ( v18 == 74 )
    {
      a3[2] = v16;
      *((_DWORD *)a3 + 8) = v17;
      if ( (unsigned int)jsonConvertTextToBlob(a3, a1) )
      {
        sqlite3_result_error(a1, "malformed JSON", 0xFFFFFFFFLL);
        sqlite3DbFree(a3[3], *a3);
        memset_0(a3, 0, 0x48u);
        return 1;
      }
      goto LABEL_29;
    }
    v21 = (const char *)v16;
    v22 = v17;
    LOBYTE(v19) = 10;
    goto LABEL_28;
  }
  if ( v10 != 1 )
  {
    *((_DWORD *)a3 + 2) = 1;
    *a3 = (__int64)&unk_1800B5B38;
    return 0;
  }
  if ( !(unsigned int)jsonFuncArgMightBeBinary(a2) )
  {
    sqlite3_result_error(a1, "JSON cannot hold BLOB values", 0xFFFFFFFFLL);
    return 1;
  }
  v12 = sqlite3_value_blob(a2);
  LOBYTE(v13) = 1;
  *a3 = v12;
  *((_DWORD *)a3 + 2) = sqlite3ValueBytes(a2, v13);
LABEL_29:
  if ( !*((_BYTE *)a3 + 47) )
    return 0;
  sqlite3_result_error_nomem(a1);
  return 1;
}

```

## disassembly

```asm
0x180074dcc  push    rbx
0x180074dce  push    rbp
0x180074dcf  push    rsi
0x180074dd0  push    rdi
0x180074dd1  push    r14
0x180074dd3  sub     rsp, 20h
0x180074dd7  movzx   eax, word ptr [rdx+14h]
0x180074ddb  mov     rbp, rcx
0x180074dde  mov     rbx, r8
0x180074de1  lea     rcx, byte_18009EC50
0x180074de8  and     eax, 3Fh
0x180074deb  mov     rsi, rdx
0x180074dee  xor     edx, edx; Val
0x180074df0  movzx   edi, byte ptr [rax+rcx]
0x180074df4  mov     rcx, rbx; void *
0x180074df7  lea     r8d, [rdx+48h]; Size
0x180074dfb  call    memset_0
0x180074e00  mov     rcx, rbp
0x180074e03  call    sqlite3_context_db_handle
0x180074e08  mov     [rbx+18h], rax
0x180074e0c  sub     edi, 1
0x180074e0f  jz      loc_180074F9A
0x180074e15  sub     edi, 1
0x180074e18  jz      loc_180074F0C
0x180074e1e  sub     edi, 1
0x180074e21  jz      short loc_180074E89
0x180074e23  cmp     edi, 1
0x180074e26  jz      short loc_180074E46
0x180074e28  lea     rax, unk_1800B5B38
0x180074e2f  mov     dword ptr [rbx+8], 1
0x180074e36  mov     [rbx], rax
0x180074e39  xor     eax, eax
0x180074e3b  add     rsp, 20h
0x180074e3f  pop     r14
0x180074e41  pop     rdi
0x180074e42  pop     rsi
0x180074e43  pop     rbp
0x180074e44  pop     rbx
0x180074e45  retn
0x180074e46  mov     rcx, rsi
0x180074e49  call    jsonFuncArgMightBeBinary
0x180074e4e  test    eax, eax
0x180074e50  jz      short loc_180074E6F
0x180074e52  mov     rcx, rsi
0x180074e55  call    sqlite3_value_blob
0x180074e5a  mov     dl, 1
0x180074e5c  mov     [rbx], rax
0x180074e5f  mov     rcx, rsi
0x180074e62  call    sqlite3ValueBytes
0x180074e67  mov     [rbx+8], eax
0x180074e6a  jmp     loc_180074FC9
0x180074e6f  or      r8d, 0FFFFFFFFh
0x180074e73  lea     rdx, aJsonCannotHold; "JSON cannot hold BLOB values"
0x180074e7a  mov     rcx, rbp
0x180074e7d  call    sqlite3_result_error
0x180074e82  mov     eax, 1
0x180074e87  jmp     short loc_180074E3B
0x180074e89  mov     dl, 1
0x180074e8b  mov     rcx, rsi
0x180074e8e  call    sqlite3ValueText
0x180074e93  mov     dl, 1
0x180074e95  mov     rcx, rsi
0x180074e98  mov     rdi, rax
0x180074e9b  call    sqlite3ValueBytes
0x180074ea0  mov     r14d, eax
0x180074ea3  test    rdi, rdi
0x180074ea6  jz      short loc_180074E82
0x180074ea8  mov     rcx, rsi
0x180074eab  call    sqlite3_value_subtype
0x180074eb0  mov     rcx, rbx
0x180074eb3  cmp     eax, 4Ah ; 'J'
0x180074eb6  jnz     short loc_180074EFF
0x180074eb8  mov     rdx, rbp
0x180074ebb  mov     [rbx+10h], rdi
0x180074ebf  mov     [rbx+20h], r14d
0x180074ec3  call    jsonConvertTextToBlob
0x180074ec8  test    eax, eax
0x180074eca  jz      loc_180074FC9
0x180074ed0  or      r8d, 0FFFFFFFFh
0x180074ed4  lea     rdx, aMalformedJson; "malformed JSON"
0x180074edb  mov     rcx, rbp
0x180074ede  call    sqlite3_result_error
0x180074ee3  mov     rdx, [rbx]
0x180074ee6  mov     rcx, [rbx+18h]
0x180074eea  call    sqlite3DbFree
0x180074eef  xor     edx, edx; Val
0x180074ef1  mov     rcx, rbx; void *
0x180074ef4  lea     r8d, [rdx+48h]; Size
0x180074ef8  call    memset_0
0x180074efd  jmp     short loc_180074E82
0x180074eff  mov     r9, rdi
0x180074f02  mov     r8d, r14d
0x180074f05  mov     dl, 0Ah
0x180074f07  jmp     loc_180074FC4
0x180074f0c  mov     rcx, rsi
0x180074f0f  call    sqlite3VdbeRealValue
0x180074f14  movq    rax, xmm0
0x180074f19  mov     rcx, 0FFFFFFFFFFFFFh
0x180074f23  test    rcx, rax
0x180074f26  mov     rdx, 7FF0000000000000h
0x180074f30  setnz   cl
0x180074f33  and     rax, rdx
0x180074f36  cmp     rax, rdx
0x180074f39  setz    al
0x180074f3c  test    al, cl
0x180074f3e  jz      short loc_180074F48
0x180074f40  xor     dl, dl
0x180074f42  xor     edi, edi
0x180074f44  xor     eax, eax
0x180074f46  jmp     short loc_180074FBB
0x180074f48  mov     dl, 1
0x180074f4a  mov     rcx, rsi
0x180074f4d  call    sqlite3ValueBytes
0x180074f52  mov     dl, 1
0x180074f54  mov     rcx, rsi
0x180074f57  mov     edi, eax
0x180074f59  call    sqlite3ValueText
0x180074f5e  test    rax, rax
0x180074f61  jz      loc_180074E82
0x180074f67  cmp     byte ptr [rax], 49h ; 'I'
0x180074f6a  jnz     short loc_180074F7C
0x180074f6c  mov     edx, 5
0x180074f71  lea     rax, a9e999_0; "9e999"
0x180074f78  mov     edi, edx
0x180074f7a  jmp     short loc_180074FBB
0x180074f7c  cmp     byte ptr [rax], 2Dh ; '-'
0x180074f7f  jnz     short loc_180074F93
0x180074f81  cmp     byte ptr [rax+1], 49h ; 'I'
0x180074f85  jnz     short loc_180074F93
0x180074f87  mov     edi, 6
0x180074f8c  lea     rax, a9e999; "-9e999"
0x180074f93  mov     edx, 5
0x180074f98  jmp     short loc_180074FBB
0x180074f9a  mov     dl, 1
0x180074f9c  mov     rcx, rsi
0x180074f9f  call    sqlite3ValueBytes
0x180074fa4  mov     dl, 1
0x180074fa6  mov     rcx, rsi
0x180074fa9  mov     edi, eax
0x180074fab  call    sqlite3ValueText
0x180074fb0  test    rax, rax
0x180074fb3  jz      loc_180074E82
0x180074fb9  mov     dl, 3
0x180074fbb  mov     rcx, rbx
0x180074fbe  mov     r8d, edi
0x180074fc1  mov     r9, rax
0x180074fc4  call    jsonBlobAppendNode
0x180074fc9  cmp     byte ptr [rbx+2Fh], 0
0x180074fcd  jz      loc_180074E39
0x180074fd3  mov     rcx, rbp
0x180074fd6  call    sqlite3_result_error_nomem
0x180074fdb  jmp     loc_180074E82
```
