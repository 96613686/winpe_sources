# jsonEachFilter

- ea: `0x180066440`
- end: `0x1800666d1`
- name: `jsonEachFilter`
- size: `657`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config`

## callees

- `0x180012470`
- `0x18002b81c`
- `0x18002b8ec`
- `0x180042dc4`
- `0x180045374`
- `0x180064f30`
- `0x180065750`
- `0x180065e14`
- `0x1800663b0`
- `0x180066440`
- `0x180066ed4`
- `0x1800676c0`
- `0x18006ac38`
- `0x18008c97c`
- `0x180096550`
- `0x180098a80`

## string_xrefs

- `0x18006658b`: `malformed JSON`

## pseudocode

```c
__int64 __fastcall jsonEachFilter(__int64 *a1, int a2, __int64 a3, __int64 a4, _QWORD *a5)
{
  __int64 *v7; // r14
  __int64 v8; // rax
  _QWORD *v9; // rbx
  int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rdx
  const char *v14; // rax
  __int64 v15; // rdx
  __int64 v16; // r8
  const char *v17; // rbp
  __int64 v18; // rbx
  __int64 v19; // rax
  __int64 v21; // rdx
  _BYTE *v22; // rbx
  unsigned int v23; // esi
  unsigned int v24; // eax
  unsigned int v25; // eax
  __int64 v26; // r8
  int v27; // eax
  __int64 v28; // r8
  __int64 v29; // rcx
  __int64 v30; // rax
  int v31; // [rsp+58h] [rbp+10h] BYREF

  v31 = 0;
  ((void (*)(void))jsonEachCursorReset)();
  if ( !a2 )
    return 0;
  v7 = a1 + 24;
  memset_0(a1 + 24, 0, 0x48u);
  v8 = a1[6];
  v9 = a5;
  *((_DWORD *)a1 + 57) = 1;
  a1[27] = v8;
  v10 = jsonFuncArgMightBeBinary(*v9);
  v11 = *v9;
  LOBYTE(v12) = 1;
  if ( v10 )
  {
    *((_DWORD *)a1 + 50) = sqlite3ValueBytes(v11, v12);
    *v7 = sqlite3_value_blob(*v9);
  }
  else
  {
    a1[26] = sqlite3ValueText(v11, v12);
    LOBYTE(v21) = 1;
    *((_DWORD *)a1 + 56) = sqlite3ValueBytes(*v9, v21);
    if ( !a1[26] )
    {
      *(__int64 *)((char *)a1 + 12) = 0;
      return 0;
    }
    if ( (unsigned int)jsonConvertTextToBlob(a1 + 24, 0) )
    {
      if ( !*((_BYTE *)a1 + 239) )
      {
        sqlite3_free(*(_QWORD *)(*a1 + 16));
        v18 = *a1;
        v19 = sqlite3_mprintf("malformed JSON");
        goto LABEL_8;
      }
      return 7;
    }
  }
  if ( a2 == 3 )
  {
    LOBYTE(v13) = 1;
    v14 = (const char *)sqlite3ValueText(v9[1], v13);
    v17 = v14;
    if ( !v14 )
      return 0;
    if ( *v14 != 36 )
    {
LABEL_7:
      sqlite3_free(*(_QWORD *)(*a1 + 16));
      v18 = *a1;
      v19 = jsonBadPathError(0, v17);
LABEL_8:
      *(_QWORD *)(v18 + 16) = v19;
      jsonEachCursorReset(a1);
      return *(_QWORD *)(*a1 + 16) != 0 ? 1 : 7;
    }
    *((_DWORD *)a1 + 5) = sqlite3Strlen30(v14, v15, v16);
    if ( v17[1] )
    {
      v25 = jsonLookupStep(a1 + 24, 0, v17 + 1, 0);
      v23 = v25;
      if ( v25 >= 0xFFFFFFFD )
      {
        if ( v25 != -2 )
          goto LABEL_7;
        *(__int64 *)((char *)a1 + 12) = 0;
        *((_BYTE *)a1 + 24) = 0;
        return 0;
      }
      v24 = *((_DWORD *)a1 + 63);
      v22 = a1 + 3;
      if ( v24 )
      {
        *v22 = 12;
      }
      else
      {
        *v22 = 11;
        v24 = v23;
      }
    }
    else
    {
      v22 = a1 + 3;
      v23 = 0;
      *((_BYTE *)a1 + 24) = 0;
      v24 = 0;
    }
    *((_DWORD *)a1 + 3) = v24;
    v26 = *((unsigned int *)a1 + 5);
  }
  else
  {
    v22 = a1 + 3;
    *((_DWORD *)a1 + 3) = 0;
    *((_BYTE *)a1 + 24) = 0;
    v17 = "$";
    v23 = 0;
    *((_DWORD *)a1 + 5) = 1;
    v26 = 1;
  }
  jsonAppendRaw(a1 + 7, v17, v26);
  *((_DWORD *)a1 + 7) = 0;
  v27 = jsonbPayloadSize(a1 + 24, v23, &v31);
  v28 = *v7;
  *((_DWORD *)a1 + 4) = v23 + v27 + v31;
  if ( (*(_BYTE *)(v23 + v28) & 0xFu) >= 0xB && !*((_BYTE *)a1 + 25) )
  {
    v29 = a1[6];
    *((_DWORD *)a1 + 3) = v23 + v27;
    *v22 = *(_BYTE *)(v23 + v28) & 0xF;
    v30 = sqlite3DbMallocZero(v29, 24);
    a1[5] = v30;
    if ( !v30 )
      return 7;
    *((_DWORD *)a1 + 7) = 1;
    *((_DWORD *)a1 + 8) = 1;
    *(_QWORD *)(v30 + 16) = 0;
    *(_DWORD *)(a1[5] + 8) = *((_DWORD *)a1 + 4);
    *(_DWORD *)a1[5] = *((_DWORD *)a1 + 3);
    *(_DWORD *)(a1[5] + 4) = v23;
  }
  return 0;
}

```

## disassembly

```asm
0x180066440  mov     [rsp+arg_0], rbx
0x180066445  mov     [rsp+arg_10], rbp
0x18006644a  push    rsi
0x18006644b  push    rdi
0x18006644c  push    r12
0x18006644e  push    r14
0x180066450  push    r15
0x180066452  sub     rsp, 20h
0x180066456  xor     r15d, r15d
0x180066459  mov     esi, edx
0x18006645b  mov     [rsp+48h+arg_8], r15d
0x180066460  mov     rdi, rcx
0x180066463  call    jsonEachCursorReset
0x180066468  test    esi, esi
0x18006646a  jz      loc_1800666B8
0x180066470  lea     r14, [rdi+0C0h]
0x180066477  xor     edx, edx; Val
0x180066479  mov     rcx, r14; void *
0x18006647c  lea     r8d, [r15+48h]; Size
0x180066480  call    memset_0
0x180066485  mov     rax, [rdi+30h]
0x180066489  lea     r12d, [r15+1]
0x18006648d  mov     rbx, [rsp+48h+arg_20]
0x180066492  mov     [rdi+0E4h], r12d
0x180066499  mov     [rdi+0D8h], rax
0x1800664a0  mov     rcx, [rbx]
0x1800664a3  call    jsonFuncArgMightBeBinary
0x1800664a8  mov     rcx, [rbx]
0x1800664ab  mov     dl, r12b
0x1800664ae  test    eax, eax
0x1800664b0  jz      short loc_18006652E
0x1800664b2  call    sqlite3ValueBytes
0x1800664b7  mov     [rdi+0C8h], eax
0x1800664bd  mov     rcx, [rbx]
0x1800664c0  call    sqlite3_value_blob
0x1800664c5  mov     [r14], rax
0x1800664c8  cmp     esi, 3
0x1800664cb  jnz     loc_18006660A
0x1800664d1  mov     rcx, [rbx+8]
0x1800664d5  mov     dl, r12b
0x1800664d8  call    sqlite3ValueText
0x1800664dd  mov     rbp, rax
0x1800664e0  test    rax, rax
0x1800664e3  jz      loc_1800666B8
0x1800664e9  cmp     byte ptr [rax], 24h ; '$'
0x1800664ec  jz      loc_18006659C
0x1800664f2  mov     rcx, [rdi]
0x1800664f5  mov     rcx, [rcx+10h]
0x1800664f9  call    sqlite3_free
0x1800664fe  mov     rbx, [rdi]
0x180066501  mov     rdx, rbp
0x180066504  xor     ecx, ecx
0x180066506  call    jsonBadPathError
0x18006650b  mov     rcx, rdi
0x18006650e  mov     [rbx+10h], rax
0x180066512  call    jsonEachCursorReset
0x180066517  mov     rax, [rdi]
0x18006651a  mov     rcx, [rax+10h]
0x18006651e  neg     rcx
0x180066521  sbb     eax, eax
0x180066523  and     eax, 0FFFFFFFAh
0x180066526  add     eax, 7
0x180066529  jmp     loc_1800666BA
0x18006652e  call    sqlite3ValueText
0x180066533  mov     [rdi+0D0h], rax
0x18006653a  mov     dl, r12b
0x18006653d  mov     rcx, [rbx]
0x180066540  call    sqlite3ValueBytes
0x180066545  mov     [rdi+0E0h], eax
0x18006654b  cmp     [rdi+0D0h], r15
0x180066552  jnz     short loc_18006655D
0x180066554  mov     [rdi+0Ch], r15
0x180066558  jmp     loc_1800666B8
0x18006655d  xor     edx, edx
0x18006655f  mov     rcx, r14
0x180066562  call    jsonConvertTextToBlob
0x180066567  test    eax, eax
0x180066569  jz      loc_1800664C8
0x18006656f  cmp     [rdi+0EFh], r15b
0x180066576  jnz     loc_18006668B
0x18006657c  mov     rcx, [rdi]
0x18006657f  mov     rcx, [rcx+10h]
0x180066583  call    sqlite3_free
0x180066588  mov     rbx, [rdi]
0x18006658b  lea     rcx, aMalformedJson; "malformed JSON"
0x180066592  call    sqlite3_mprintf
0x180066597  jmp     loc_18006650B
0x18006659c  mov     rcx, rbp
0x18006659f  call    sqlite3Strlen30
0x1800665a4  lea     r8, [rbp+1]
0x1800665a8  mov     [rdi+14h], eax
0x1800665ab  cmp     [r8], r15b
0x1800665ae  jnz     short loc_1800665BF
0x1800665b0  lea     rbx, [rdi+18h]
0x1800665b4  mov     esi, r15d
0x1800665b7  mov     [rbx], r15b
0x1800665ba  mov     eax, r15d
0x1800665bd  jmp     short loc_180066601
0x1800665bf  xor     r9d, r9d
0x1800665c2  xor     edx, edx
0x1800665c4  mov     rcx, r14
0x1800665c7  call    jsonLookupStep
0x1800665cc  mov     esi, eax
0x1800665ce  cmp     eax, 0FFFFFFFDh
0x1800665d1  jb      short loc_1800665E9
0x1800665d3  cmp     eax, 0FFFFFFFEh
0x1800665d6  jnz     loc_1800664F2
0x1800665dc  mov     [rdi+0Ch], r15
0x1800665e0  mov     [rdi+18h], r15b
0x1800665e4  jmp     loc_1800666B8
0x1800665e9  mov     eax, [rdi+0FCh]
0x1800665ef  lea     rbx, [rdi+18h]
0x1800665f3  test    eax, eax
0x1800665f5  jz      short loc_1800665FC
0x1800665f7  mov     byte ptr [rbx], 0Ch
0x1800665fa  jmp     short loc_180066601
0x1800665fc  mov     byte ptr [rbx], 0Bh
0x1800665ff  mov     eax, esi
0x180066601  mov     [rdi+0Ch], eax
0x180066604  mov     r8d, [rdi+14h]
0x180066608  jmp     short loc_180066626
0x18006660a  lea     rbx, [rdi+18h]
0x18006660e  mov     [rdi+0Ch], r15d
0x180066612  mov     [rbx], r15b
0x180066615  lea     rbp, asc_1800B5FC0; "$"
0x18006661c  mov     esi, r15d
0x18006661f  mov     [rdi+14h], r12d
0x180066623  mov     r8d, r12d
0x180066626  lea     rcx, [rdi+38h]
0x18006662a  mov     rdx, rbp
0x18006662d  call    jsonAppendRaw
0x180066632  lea     r8, [rsp+48h+arg_8]
0x180066637  mov     [rdi+1Ch], r15d
0x18006663b  mov     edx, esi
0x18006663d  mov     rcx, r14
0x180066640  call    jsonbPayloadSize
0x180066645  mov     edx, [rsp+48h+arg_8]
0x180066649  mov     r8, [r14]
0x18006664c  add     edx, eax
0x18006664e  add     edx, esi
0x180066650  mov     [rdi+10h], edx
0x180066653  mov     edx, esi
0x180066655  mov     cl, [rdx+r8]
0x180066659  and     cl, 0Fh
0x18006665c  cmp     cl, 0Bh
0x18006665f  jb      short loc_1800666B8
0x180066661  cmp     [rdi+19h], r15b
0x180066665  jnz     short loc_1800666B8
0x180066667  mov     rcx, [rdi+30h]
0x18006666b  add     eax, esi
0x18006666d  mov     [rdi+0Ch], eax
0x180066670  mov     al, [rdx+r8]
0x180066674  mov     edx, 18h
0x180066679  and     al, 0Fh
0x18006667b  mov     [rbx], al
0x18006667d  call    sqlite3DbMallocZero
0x180066682  mov     [rdi+28h], rax
0x180066686  test    rax, rax
0x180066689  jnz     short loc_180066692
0x18006668b  mov     eax, 7
0x180066690  jmp     short loc_1800666BA
0x180066692  mov     [rdi+1Ch], r12d
0x180066696  mov     [rdi+20h], r12d
0x18006669a  mov     [rax+10h], r15
0x18006669e  mov     eax, [rdi+10h]
0x1800666a1  mov     rcx, [rdi+28h]
0x1800666a5  mov     [rcx+8], eax
0x1800666a8  mov     eax, [rdi+0Ch]
0x1800666ab  mov     rcx, [rdi+28h]
0x1800666af  mov     [rcx], eax
0x1800666b1  mov     rax, [rdi+28h]
0x1800666b5  mov     [rax+4], esi
0x1800666b8  xor     eax, eax
0x1800666ba  mov     rbx, [rsp+48h+arg_0]
0x1800666bf  mov     rbp, [rsp+48h+arg_10]
0x1800666c4  add     rsp, 20h
0x1800666c8  pop     r15
0x1800666ca  pop     r14
0x1800666cc  pop     r12
0x1800666ce  pop     rdi
0x1800666cf  pop     rsi
0x1800666d0  retn
```
