# jsonExtractFunc

- ea: `0x18004f190`
- end: `0x18004f592`
- name: `jsonExtractFunc`
- size: `1026`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config`

## callees

- `0x180002250`
- `0x180002cf8`
- `0x18004d338`
- `0x18004d4e8`
- `0x18004d538`
- `0x18004d584`
- `0x18004dd50`
- `0x18004f190`
- `0x18004fca4`
- `0x180050b30`
- `0x180050b6c`
- `0x180051394`
- `0x18005194c`
- `0x180051dfc`
- `0x180051e54`
- `0x180052118`
- `0x180092290`
- `0x18009b4ec`

## string_xrefs

- `0x18004f52b`: `malformed JSON`

## pseudocode

```c
__int64 __fastcall jsonExtractFunc(__int64 *a1, int a2, __int64 *a3)
{
  __int64 *v3; // rdi
  __int64 result; // rax
  __int64 v7; // rdx
  __int64 v8; // r14
  int v9; // r13d
  int v10; // eax
  __int64 v11; // r12
  _BYTE *v12; // rax
  _BYTE *v13; // rsi
  __int64 v14; // rdi
  unsigned int v15; // edi
  __int64 v16; // r9
  __int64 v17; // rdi
  __int64 v18; // r8
  const char *v19; // rdx
  int v20; // ecx
  __int64 v21; // rdx
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rcx
  int v25; // [rsp+30h] [rbp-89h]
  __int64 *v27; // [rsp+40h] [rbp-79h] BYREF
  _BYTE *v28; // [rsp+48h] [rbp-71h]
  unsigned __int64 v29; // [rsp+50h] [rbp-69h]
  unsigned __int64 v30; // [rsp+58h] [rbp-61h]
  __int16 v31; // [rsp+60h] [rbp-59h]
  _BYTE v32[110]; // [rsp+62h] [rbp-57h] BYREF

  v3 = a3;
  result = (__int64)memset_0(&v27, 0, 0x88u);
  if ( a2 >= 2 )
  {
    result = jsonParseFuncArg(a1, *v3, 0);
    v8 = result;
    if ( result )
    {
      v9 = *(_DWORD *)(a1[1] + 8);
      v28 = v32;
      v10 = 1;
      v27 = a1;
      v31 = 1;
      v29 = 100;
      v30 = 0;
      if ( a2 > 2 )
      {
        v32[0] = 91;
        v30 = 1;
      }
      v25 = 1;
      while ( 1 )
      {
        v11 = v10;
        LOBYTE(v7) = 1;
        v12 = (_BYTE *)sqlite3ValueText(v3[v10], v7);
        v13 = v12;
        if ( !v12 )
        {
LABEL_50:
          jsonStringReset(&v27);
          return jsonParseFree(v8);
        }
        v14 = -1;
        do
          ++v14;
        while ( v12[v14] );
        if ( *v12 == 36 )
        {
          v15 = jsonLookupStep(v8, 0, v12 + 1, 0);
          goto LABEL_27;
        }
        if ( (v9 & 3) == 0 )
          goto LABEL_49;
        v27 = a1;
        v28 = v32;
        v17 = v14 & 0x3FFFFFFF;
        v31 = 1;
        v29 = 100;
        v30 = 0;
        if ( *((_BYTE *)qword_1800FE430 + (*(_WORD *)(a3[v11] + 20) & 0x3F)) == 1 )
        {
          jsonAppendRawNZ(&v27, "[", 1);
          jsonAppendRaw(&v27, v13, (unsigned int)v17);
          v18 = 2;
          v19 = "]";
LABEL_25:
          jsonAppendRawNZ(&v27, v19, v18);
          goto LABEL_26;
        }
        v20 = 0;
        if ( (_DWORD)v17 )
        {
          while ( 1 )
          {
            v21 = (unsigned __int8)v12[v20];
            if ( (*((_BYTE *)&qword_1800FB500 + v21) & 6) == 0 && (_BYTE)v21 != 95 )
              break;
            if ( ++v20 >= (int)v17 )
              goto LABEL_18;
          }
        }
        else
        {
LABEL_18:
          if ( v20 == (_DWORD)v17 )
          {
            jsonAppendRawNZ(&v27, ".", 1);
            goto LABEL_23;
          }
        }
        if ( *v12 != 91 || (unsigned int)v17 < 3 || v12[v17 - 1] != 93 )
        {
          jsonAppendRawNZ(&v27, ".\"", 2);
          jsonAppendRaw(&v27, v13, (unsigned int)v17);
          v18 = 1;
          v19 = "\"";
          goto LABEL_25;
        }
LABEL_23:
        jsonAppendRaw(&v27, v13, (unsigned int)v17);
LABEL_26:
        jsonStringTerminate(&v27);
        v15 = jsonLookupStep(v8, 0, v28, 0);
        jsonStringReset(&v27);
LABEL_27:
        if ( v15 >= *(_DWORD *)(v8 + 8) )
        {
          if ( v15 != -2 )
          {
            if ( v15 == -1 )
            {
              v24 = *a1;
              *((_DWORD *)a1 + 9) = 1;
              LOBYTE(v16) = 1;
              sqlite3VdbeMemSetStr(v24, "malformed JSON", -1, v16, -1);
              goto LABEL_50;
            }
LABEL_49:
            jsonBadPathError(a1, v13);
            goto LABEL_50;
          }
          if ( a2 == 2 )
            goto LABEL_50;
          jsonAppendSeparator(&v27);
          jsonAppendRawNZ(&v27, "null", 4);
          goto LABEL_32;
        }
        if ( a2 == 2 )
        {
          if ( (v9 & 1) != 0 )
          {
            v27 = a1;
            v28 = v32;
            v31 = 1;
            v29 = 100;
            v30 = 0;
            jsonTranslateBlobToText(v8, v15, &v27);
            jsonReturnString(&v27, 0, 0);
            jsonStringReset(&v27);
          }
          else
          {
            jsonReturnFromBlob((char **)v8, v15, a1, 0);
            if ( (v9 & 0xA) != 0 || (*(_BYTE *)(v15 + *(_QWORD *)v8) & 0xFu) < 0xB )
              goto LABEL_32;
          }
          v22 = *a1;
          *(_BYTE *)(v22 + 23) = 74;
          *(_WORD *)(v22 + 20) |= 0x800u;
        }
        else
        {
          jsonAppendSeparator(&v27);
          jsonTranslateBlobToText(v8, v15, &v27);
        }
LABEL_32:
        v3 = a3;
        v10 = v25 + 1;
        v25 = v10;
        if ( v10 >= a2 )
        {
          if ( a2 > 2 )
          {
            if ( v30 < v29 )
            {
              v28[v30++] = 93;
            }
            else
            {
              LOBYTE(v7) = 93;
              jsonAppendCharExpand(&v27, v7);
            }
            jsonReturnString(&v27, 0, 0);
            if ( (v9 & 8) == 0 )
            {
              v23 = *a1;
              *(_WORD *)(v23 + 20) |= 0x800u;
              *(_BYTE *)(v23 + 23) = 74;
            }
          }
          goto LABEL_50;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18004f190  mov     [rsp-8+arg_8], rbx
0x18004f195  push    rbp
0x18004f196  push    rsi
0x18004f197  push    rdi
0x18004f198  push    r12
0x18004f19a  push    r13
0x18004f19c  push    r14
0x18004f19e  push    r15
0x18004f1a0  lea     rbp, [rsp-27h]
0x18004f1a5  sub     rsp, 0E0h
0x18004f1ac  mov     rax, cs:__security_cookie
0x18004f1b3  xor     rax, rsp
0x18004f1b6  mov     [rbp+57h+var_40], rax
0x18004f1ba  mov     rdi, r8
0x18004f1bd  mov     [rsp+110h+var_D8], r8
0x18004f1c2  mov     r15d, edx
0x18004f1c5  mov     rbx, rcx
0x18004f1c8  xor     edx, edx; Val
0x18004f1ca  lea     rcx, [rbp+57h+var_D0]; void *
0x18004f1ce  mov     r8d, 88h; Size
0x18004f1d4  call    memset_0
0x18004f1d9  cmp     r15d, 2
0x18004f1dd  jl      loc_18004F56B
0x18004f1e3  mov     rdx, [rdi]
0x18004f1e6  xor     r8d, r8d
0x18004f1e9  mov     rcx, rbx
0x18004f1ec  call    jsonParseFuncArg
0x18004f1f1  mov     r14, rax
0x18004f1f4  test    rax, rax
0x18004f1f7  jz      loc_18004F56B
0x18004f1fd  mov     rcx, [rbx+8]
0x18004f201  lea     rax, [rbp+57h+var_AE]
0x18004f205  mov     r13d, [rcx+8]
0x18004f209  mov     [rbp+57h+var_C8], rax
0x18004f20d  mov     eax, 1
0x18004f212  mov     [rbp+57h+var_D0], rbx
0x18004f216  mov     [rbp+57h+var_B0], 1
0x18004f21c  mov     [rbp+57h+var_C0], 64h ; 'd'
0x18004f224  mov     [rbp+57h+var_B8], 0
0x18004f22c  cmp     r15d, 2
0x18004f230  jle     short loc_18004F23A
0x18004f232  mov     [rbp+57h+var_AE], 5Bh ; '['
0x18004f236  mov     [rbp+57h+var_B8], rax
0x18004f23a  mov     [rsp+110h+var_E0], eax
0x18004f23e  movsxd  r12, eax
0x18004f241  mov     dl, 1
0x18004f243  mov     rcx, [rdi+r12*8]
0x18004f247  call    sqlite3ValueText
0x18004f24c  xor     edx, edx
0x18004f24e  mov     rsi, rax
0x18004f251  test    rax, rax
0x18004f254  jz      loc_18004F55A
0x18004f25a  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18004f25e  inc     rdi
0x18004f261  cmp     [rax+rdi], dl
0x18004f264  jnz     short loc_18004F25E
0x18004f266  cmp     byte ptr [rax], 24h ; '$'
0x18004f269  jnz     short loc_18004F281
0x18004f26b  lea     r8, [rax+1]
0x18004f26f  xor     r9d, r9d
0x18004f272  mov     rcx, r14
0x18004f275  call    jsonLookupStep
0x18004f27a  mov     edi, eax
0x18004f27c  jmp     loc_18004F3C8
0x18004f281  test    r13b, 3
0x18004f285  jz      loc_18004F54F
0x18004f28b  lea     rax, [rbp+57h+var_AE]
0x18004f28f  mov     [rbp+57h+var_D0], rbx
0x18004f293  mov     [rbp+57h+var_C8], rax
0x18004f297  lea     r8, cs:180000000h
0x18004f29e  mov     rax, [rsp+110h+var_D8]
0x18004f2a3  and     edi, 3FFFFFFFh
0x18004f2a9  mov     [rbp+57h+var_B0], 1
0x18004f2af  mov     [rbp+57h+var_C0], 64h ; 'd'
0x18004f2b7  mov     [rbp+57h+var_B8], rdx
0x18004f2bb  mov     rax, [rax+r12*8]
0x18004f2bf  movzx   ecx, word ptr [rax+14h]
0x18004f2c3  and     ecx, 3Fh
0x18004f2c6  cmp     byte ptr [rcx+r8+0FE430h], 1
0x18004f2cf  jnz     short loc_18004F308
0x18004f2d1  mov     r8d, 1
0x18004f2d7  lea     rdx, asc_1800FA114; "["
0x18004f2de  lea     rcx, [rbp+57h+var_D0]
0x18004f2e2  call    jsonAppendRawNZ
0x18004f2e7  mov     r8d, edi
0x18004f2ea  lea     rcx, [rbp+57h+var_D0]
0x18004f2ee  mov     rdx, rsi
0x18004f2f1  call    jsonAppendRaw
0x18004f2f6  mov     r8d, 2
0x18004f2fc  lea     rdx, asc_1800F48FC; "]"
0x18004f303  jmp     loc_18004F39A
0x18004f308  mov     ecx, edx
0x18004f30a  test    edi, edi
0x18004f30c  jz      short loc_18004F32A
0x18004f30e  mov     eax, ecx
0x18004f310  movzx   edx, byte ptr [rax+rsi]
0x18004f314  test    byte ptr [rdx+r8+0FB500h], 6
0x18004f31d  jnz     short loc_18004F324
0x18004f31f  cmp     dl, 5Fh ; '_'
0x18004f322  jnz     short loc_18004F346
0x18004f324  inc     ecx
0x18004f326  cmp     ecx, edi
0x18004f328  jl      short loc_18004F30E
0x18004f32a  cmp     ecx, edi
0x18004f32c  jnz     short loc_18004F346
0x18004f32e  mov     r8d, 1
0x18004f334  lea     rdx, asc_1800F31A8; "."
0x18004f33b  lea     rcx, [rbp+57h+var_D0]
0x18004f33f  call    jsonAppendRawNZ
0x18004f344  jmp     short loc_18004F357
0x18004f346  cmp     byte ptr [rsi], 5Bh ; '['
0x18004f349  jnz     short loc_18004F368
0x18004f34b  cmp     edi, 3
0x18004f34e  jb      short loc_18004F368
0x18004f350  cmp     byte ptr [rdi+rsi-1], 5Dh ; ']'
0x18004f355  jnz     short loc_18004F368
0x18004f357  mov     r8d, edi
0x18004f35a  lea     rcx, [rbp+57h+var_D0]
0x18004f35e  mov     rdx, rsi
0x18004f361  call    jsonAppendRaw
0x18004f366  jmp     short loc_18004F3A3
0x18004f368  mov     r8d, 2
0x18004f36e  lea     rdx, asc_1800FA108; ".\""
0x18004f375  lea     rcx, [rbp+57h+var_D0]
0x18004f379  call    jsonAppendRawNZ
0x18004f37e  mov     r8d, edi
0x18004f381  lea     rcx, [rbp+57h+var_D0]
0x18004f385  mov     rdx, rsi
0x18004f388  call    jsonAppendRaw
0x18004f38d  mov     r8d, 1
0x18004f393  lea     rdx, asc_1800FA10C; "\""
0x18004f39a  lea     rcx, [rbp+57h+var_D0]
0x18004f39e  call    jsonAppendRawNZ
0x18004f3a3  lea     rcx, [rbp+57h+var_D0]
0x18004f3a7  call    jsonStringTerminate
0x18004f3ac  mov     r8, [rbp+57h+var_C8]
0x18004f3b0  xor     r9d, r9d
0x18004f3b3  xor     edx, edx
0x18004f3b5  mov     rcx, r14
0x18004f3b8  call    jsonLookupStep
0x18004f3bd  lea     rcx, [rbp+57h+var_D0]
0x18004f3c1  mov     edi, eax
0x18004f3c3  call    jsonStringReset
0x18004f3c8  cmp     edi, [r14+8]
0x18004f3cc  jnb     loc_18004F4C6
0x18004f3d2  cmp     r15d, 2
0x18004f3d6  jnz     loc_18004F4A5
0x18004f3dc  mov     edx, edi
0x18004f3de  mov     rcx, r14
0x18004f3e1  test    r13b, 1
0x18004f3e5  jz      loc_18004F47D
0x18004f3eb  lea     rax, [rbp+57h+var_AE]
0x18004f3ef  mov     [rbp+57h+var_D0], rbx
0x18004f3f3  lea     r8, [rbp+57h+var_D0]
0x18004f3f7  mov     [rbp+57h+var_C8], rax
0x18004f3fb  mov     [rbp+57h+var_B0], 1
0x18004f401  mov     [rbp+57h+var_C0], 64h ; 'd'
0x18004f409  mov     [rbp+57h+var_B8], 0
0x18004f411  call    jsonTranslateBlobToText
0x18004f416  xor     r8d, r8d
0x18004f419  lea     rcx, [rbp+57h+var_D0]
0x18004f41d  xor     edx, edx
0x18004f41f  call    jsonReturnString
0x18004f424  lea     rcx, [rbp+57h+var_D0]
0x18004f428  call    jsonStringReset
0x18004f42d  mov     esi, 800h
0x18004f432  mov     rax, [rbx]
0x18004f435  mov     byte ptr [rax+17h], 4Ah ; 'J'
0x18004f439  or      [rax+14h], si
0x18004f43d  mov     eax, [rsp+110h+var_E0]
0x18004f441  mov     rdi, [rsp+110h+var_D8]
0x18004f446  inc     eax
0x18004f448  mov     [rsp+110h+var_E0], eax
0x18004f44c  cmp     eax, r15d
0x18004f44f  jl      loc_18004F23E
0x18004f455  cmp     r15d, 2
0x18004f459  jle     loc_18004F55A
0x18004f45f  mov     rcx, [rbp+57h+var_B8]
0x18004f463  cmp     rcx, [rbp+57h+var_C0]
0x18004f467  jb      loc_18004F4F6
0x18004f46d  mov     dl, 5Dh ; ']'
0x18004f46f  lea     rcx, [rbp+57h+var_D0]
0x18004f473  call    jsonAppendCharExpand
0x18004f478  jmp     loc_18004F502
0x18004f47d  xor     r9d, r9d
0x18004f480  mov     r8, rbx
0x18004f483  call    jsonReturnFromBlob
0x18004f488  mov     esi, 800h
0x18004f48d  test    r13b, 0Ah
0x18004f491  jnz     short loc_18004F43D
0x18004f493  mov     rax, [r14]
0x18004f496  mov     ecx, edi
0x18004f498  mov     dl, [rcx+rax]
0x18004f49b  and     dl, 0Fh
0x18004f49e  cmp     dl, 0Bh
0x18004f4a1  jb      short loc_18004F43D
0x18004f4a3  jmp     short loc_18004F432
0x18004f4a5  lea     rcx, [rbp+57h+var_D0]
0x18004f4a9  call    jsonAppendSeparator
0x18004f4ae  lea     r8, [rbp+57h+var_D0]
0x18004f4b2  mov     edx, edi
0x18004f4b4  mov     rcx, r14
0x18004f4b7  call    jsonTranslateBlobToText
0x18004f4bc  mov     esi, 800h
0x18004f4c1  jmp     loc_18004F43D
0x18004f4c6  cmp     edi, 0FFFFFFFEh
0x18004f4c9  jnz     short loc_18004F523
0x18004f4cb  cmp     r15d, 2
0x18004f4cf  jz      loc_18004F55A
0x18004f4d5  lea     rcx, [rbp+57h+var_D0]
0x18004f4d9  call    jsonAppendSeparator
0x18004f4de  mov     r8d, 4
0x18004f4e4  lea     rdx, aNull_2; "null"
0x18004f4eb  lea     rcx, [rbp+57h+var_D0]
0x18004f4ef  call    jsonAppendRawNZ
0x18004f4f4  jmp     short loc_18004F4BC
0x18004f4f6  mov     rax, [rbp+57h+var_C8]
0x18004f4fa  mov     byte ptr [rcx+rax], 5Dh ; ']'
0x18004f4fe  inc     [rbp+57h+var_B8]
0x18004f502  xor     r8d, r8d
0x18004f505  lea     rcx, [rbp+57h+var_D0]
0x18004f509  xor     edx, edx
0x18004f50b  call    jsonReturnString
0x18004f510  test    r13b, 8
0x18004f514  jnz     short loc_18004F55A
0x18004f516  mov     rax, [rbx]
0x18004f519  or      [rax+14h], si
0x18004f51d  mov     byte ptr [rax+17h], 4Ah ; 'J'
0x18004f521  jmp     short loc_18004F55A
0x18004f523  cmp     edi, 0FFFFFFFFh
0x18004f526  jnz     short loc_18004F54F
0x18004f528  mov     rcx, [rbx]
0x18004f52b  lea     rdx, aMalformedJson; "malformed JSON"
0x18004f532  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004f536  mov     dword ptr [rbx+24h], 1
0x18004f53d  mov     r8, rax
0x18004f540  mov     [rsp+110h+var_F0], rax
0x18004f545  mov     r9b, 1
0x18004f548  call    sqlite3VdbeMemSetStr
0x18004f54d  jmp     short loc_18004F55A
0x18004f54f  mov     rdx, rsi
0x18004f552  mov     rcx, rbx
0x18004f555  call    jsonBadPathError
0x18004f55a  lea     rcx, [rbp+57h+var_D0]
0x18004f55e  call    jsonStringReset
0x18004f563  mov     rcx, r14
0x18004f566  call    jsonParseFree
0x18004f56b  mov     rcx, [rbp+57h+var_40]
0x18004f56f  xor     rcx, rsp; StackCookie
0x18004f572  call    __security_check_cookie
0x18004f577  mov     rbx, [rsp+110h+arg_8]
0x18004f57f  add     rsp, 0E0h
0x18004f586  pop     r15
0x18004f588  pop     r14
0x18004f58a  pop     r13
0x18004f58c  pop     r12
0x18004f58e  pop     rdi
0x18004f58f  pop     rsi
0x18004f590  pop     rbp
0x18004f591  retn
```
