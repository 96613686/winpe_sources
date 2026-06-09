# jsonEachFilter

- ea: `0x1800834b0`
- end: `0x180083741`
- name: `jsonEachFilter`
- size: `657`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config`

## callees

- `0x18001eb90`
- `0x180024b60`
- `0x1800310a0`
- `0x18003d380`
- `0x180041eb0`
- `0x180054e70`
- `0x180054ef4`
- `0x180078968`
- `0x180081f40`
- `0x180082760`
- `0x180082ea4`
- `0x180083440`
- `0x1800834b0`
- `0x180083f44`
- `0x180084730`
- `0x180087c68`

## string_xrefs

- `0x1800835fb`: `malformed JSON`

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
  const char *v15; // rbp
  __int64 v16; // rbx
  __int64 v17; // rax
  __int64 v19; // rdx
  _BYTE *v20; // rbx
  unsigned int v21; // esi
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // r8d
  int v25; // eax
  __int64 v26; // r8
  __int64 v27; // rcx
  __int64 v28; // rax
  unsigned int v29; // [rsp+58h] [rbp+10h] BYREF

  v29 = 0;
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
    LOBYTE(v19) = 1;
    *((_DWORD *)a1 + 56) = sqlite3ValueBytes(*v9, v19);
    if ( !a1[26] )
    {
      *(__int64 *)((char *)a1 + 12) = 0;
      return 0;
    }
    if ( (unsigned int)jsonConvertTextToBlob((__int64)(a1 + 24), 0) )
    {
      if ( !*((_BYTE *)a1 + 239) )
      {
        sqlite3_free(*(_QWORD *)(*a1 + 16));
        v16 = *a1;
        v17 = sqlite3_mprintf("malformed JSON");
        goto LABEL_8;
      }
      return 7;
    }
  }
  if ( a2 == 3 )
  {
    LOBYTE(v13) = 1;
    v14 = (const char *)sqlite3ValueText(v9[1], v13);
    v15 = v14;
    if ( !v14 )
      return 0;
    if ( *v14 != 36 )
    {
LABEL_7:
      sqlite3_free(*(_QWORD *)(*a1 + 16));
      v16 = *a1;
      v17 = jsonBadPathError(0);
LABEL_8:
      *(_QWORD *)(v16 + 16) = v17;
      jsonEachCursorReset(a1);
      return *(_QWORD *)(*a1 + 16) != 0 ? 1 : 7;
    }
    *((_DWORD *)a1 + 5) = sqlite3Strlen30(v14);
    if ( v15[1] )
    {
      v23 = jsonLookupStep(a1 + 24, 0, v15 + 1, 0);
      v21 = v23;
      if ( v23 >= 0xFFFFFFFD )
      {
        if ( v23 != -2 )
          goto LABEL_7;
        *(__int64 *)((char *)a1 + 12) = 0;
        *((_BYTE *)a1 + 24) = 0;
        return 0;
      }
      v22 = *((_DWORD *)a1 + 63);
      v20 = a1 + 3;
      if ( v22 )
      {
        *v20 = 12;
      }
      else
      {
        *v20 = 11;
        v22 = v21;
      }
    }
    else
    {
      v20 = a1 + 3;
      v21 = 0;
      *((_BYTE *)a1 + 24) = 0;
      v22 = 0;
    }
    *((_DWORD *)a1 + 3) = v22;
    v24 = *((_DWORD *)a1 + 5);
  }
  else
  {
    v20 = a1 + 3;
    *((_DWORD *)a1 + 3) = 0;
    *((_BYTE *)a1 + 24) = 0;
    v15 = "$";
    v21 = 0;
    *((_DWORD *)a1 + 5) = 1;
    v24 = 1;
  }
  jsonAppendRaw(a1 + 7, v15, v24);
  *((_DWORD *)a1 + 7) = 0;
  v25 = jsonbPayloadSize(a1 + 24, v21, &v29);
  v26 = *v7;
  *((_DWORD *)a1 + 4) = v21 + v25 + v29;
  if ( (*(_BYTE *)(v21 + v26) & 0xFu) >= 0xB && !*((_BYTE *)a1 + 25) )
  {
    v27 = a1[6];
    *((_DWORD *)a1 + 3) = v21 + v25;
    *v20 = *(_BYTE *)(v21 + v26) & 0xF;
    v28 = sqlite3DbMallocZero(v27, 24);
    a1[5] = v28;
    if ( !v28 )
      return 7;
    *((_DWORD *)a1 + 7) = 1;
    *((_DWORD *)a1 + 8) = 1;
    *(_QWORD *)(v28 + 16) = 0;
    *(_DWORD *)(a1[5] + 8) = *((_DWORD *)a1 + 4);
    *(_DWORD *)a1[5] = *((_DWORD *)a1 + 3);
    *(_DWORD *)(a1[5] + 4) = v21;
  }
  return 0;
}

```

## disassembly

```asm
0x1800834b0  mov     [rsp+arg_0], rbx
0x1800834b5  mov     [rsp+arg_10], rbp
0x1800834ba  push    rsi
0x1800834bb  push    rdi
0x1800834bc  push    r12
0x1800834be  push    r14
0x1800834c0  push    r15
0x1800834c2  sub     rsp, 20h
0x1800834c6  xor     r15d, r15d
0x1800834c9  mov     esi, edx
0x1800834cb  mov     [rsp+48h+arg_8], r15d
0x1800834d0  mov     rdi, rcx
0x1800834d3  call    jsonEachCursorReset
0x1800834d8  test    esi, esi
0x1800834da  jz      loc_180083728
0x1800834e0  lea     r14, [rdi+0C0h]
0x1800834e7  xor     edx, edx; Val
0x1800834e9  mov     rcx, r14; void *
0x1800834ec  lea     r8d, [r15+48h]; Size
0x1800834f0  call    memset_0
0x1800834f5  mov     rax, [rdi+30h]
0x1800834f9  lea     r12d, [r15+1]
0x1800834fd  mov     rbx, [rsp+48h+arg_20]
0x180083502  mov     [rdi+0E4h], r12d
0x180083509  mov     [rdi+0D8h], rax
0x180083510  mov     rcx, [rbx]
0x180083513  call    jsonFuncArgMightBeBinary
0x180083518  mov     rcx, [rbx]
0x18008351b  mov     dl, r12b
0x18008351e  test    eax, eax
0x180083520  jz      short loc_18008359E
0x180083522  call    sqlite3ValueBytes
0x180083527  mov     [rdi+0C8h], eax
0x18008352d  mov     rcx, [rbx]
0x180083530  call    sqlite3_value_blob
0x180083535  mov     [r14], rax
0x180083538  cmp     esi, 3
0x18008353b  jnz     loc_18008367A
0x180083541  mov     rcx, [rbx+8]
0x180083545  mov     dl, r12b
0x180083548  call    sqlite3ValueText
0x18008354d  mov     rbp, rax
0x180083550  test    rax, rax
0x180083553  jz      loc_180083728
0x180083559  cmp     byte ptr [rax], 24h ; '$'
0x18008355c  jz      loc_18008360C
0x180083562  mov     rcx, [rdi]
0x180083565  mov     rcx, [rcx+10h]
0x180083569  call    sqlite3_free
0x18008356e  mov     rbx, [rdi]
0x180083571  mov     rdx, rbp
0x180083574  xor     ecx, ecx
0x180083576  call    jsonBadPathError
0x18008357b  mov     rcx, rdi
0x18008357e  mov     [rbx+10h], rax
0x180083582  call    jsonEachCursorReset
0x180083587  mov     rax, [rdi]
0x18008358a  mov     rcx, [rax+10h]
0x18008358e  neg     rcx
0x180083591  sbb     eax, eax
0x180083593  and     eax, 0FFFFFFFAh
0x180083596  add     eax, 7
0x180083599  jmp     loc_18008372A
0x18008359e  call    sqlite3ValueText
0x1800835a3  mov     [rdi+0D0h], rax
0x1800835aa  mov     dl, r12b
0x1800835ad  mov     rcx, [rbx]
0x1800835b0  call    sqlite3ValueBytes
0x1800835b5  mov     [rdi+0E0h], eax
0x1800835bb  cmp     [rdi+0D0h], r15
0x1800835c2  jnz     short loc_1800835CD
0x1800835c4  mov     [rdi+0Ch], r15
0x1800835c8  jmp     loc_180083728
0x1800835cd  xor     edx, edx
0x1800835cf  mov     rcx, r14
0x1800835d2  call    jsonConvertTextToBlob
0x1800835d7  test    eax, eax
0x1800835d9  jz      loc_180083538
0x1800835df  cmp     [rdi+0EFh], r15b
0x1800835e6  jnz     loc_1800836FB
0x1800835ec  mov     rcx, [rdi]
0x1800835ef  mov     rcx, [rcx+10h]
0x1800835f3  call    sqlite3_free
0x1800835f8  mov     rbx, [rdi]
0x1800835fb  lea     rcx, aMalformedJson; "malformed JSON"
0x180083602  call    sqlite3_mprintf
0x180083607  jmp     loc_18008357B
0x18008360c  mov     rcx, rbp
0x18008360f  call    sqlite3Strlen30
0x180083614  lea     r8, [rbp+1]
0x180083618  mov     [rdi+14h], eax
0x18008361b  cmp     [r8], r15b
0x18008361e  jnz     short loc_18008362F
0x180083620  lea     rbx, [rdi+18h]
0x180083624  mov     esi, r15d
0x180083627  mov     [rbx], r15b
0x18008362a  mov     eax, r15d
0x18008362d  jmp     short loc_180083671
0x18008362f  xor     r9d, r9d
0x180083632  xor     edx, edx
0x180083634  mov     rcx, r14
0x180083637  call    jsonLookupStep
0x18008363c  mov     esi, eax
0x18008363e  cmp     eax, 0FFFFFFFDh
0x180083641  jb      short loc_180083659
0x180083643  cmp     eax, 0FFFFFFFEh
0x180083646  jnz     loc_180083562
0x18008364c  mov     [rdi+0Ch], r15
0x180083650  mov     [rdi+18h], r15b
0x180083654  jmp     loc_180083728
0x180083659  mov     eax, [rdi+0FCh]
0x18008365f  lea     rbx, [rdi+18h]
0x180083663  test    eax, eax
0x180083665  jz      short loc_18008366C
0x180083667  mov     byte ptr [rbx], 0Ch
0x18008366a  jmp     short loc_180083671
0x18008366c  mov     byte ptr [rbx], 0Bh
0x18008366f  mov     eax, esi
0x180083671  mov     [rdi+0Ch], eax
0x180083674  mov     r8d, [rdi+14h]
0x180083678  jmp     short loc_180083696
0x18008367a  lea     rbx, [rdi+18h]
0x18008367e  mov     [rdi+0Ch], r15d
0x180083682  mov     [rbx], r15b
0x180083685  lea     rbp, asc_1800BCFF0; "$"
0x18008368c  mov     esi, r15d
0x18008368f  mov     [rdi+14h], r12d
0x180083693  mov     r8d, r12d
0x180083696  lea     rcx, [rdi+38h]
0x18008369a  mov     rdx, rbp
0x18008369d  call    jsonAppendRaw
0x1800836a2  lea     r8, [rsp+48h+arg_8]
0x1800836a7  mov     [rdi+1Ch], r15d
0x1800836ab  mov     edx, esi
0x1800836ad  mov     rcx, r14
0x1800836b0  call    jsonbPayloadSize
0x1800836b5  mov     edx, [rsp+48h+arg_8]
0x1800836b9  mov     r8, [r14]
0x1800836bc  add     edx, eax
0x1800836be  add     edx, esi
0x1800836c0  mov     [rdi+10h], edx
0x1800836c3  mov     edx, esi
0x1800836c5  mov     cl, [rdx+r8]
0x1800836c9  and     cl, 0Fh
0x1800836cc  cmp     cl, 0Bh
0x1800836cf  jb      short loc_180083728
0x1800836d1  cmp     [rdi+19h], r15b
0x1800836d5  jnz     short loc_180083728
0x1800836d7  mov     rcx, [rdi+30h]
0x1800836db  add     eax, esi
0x1800836dd  mov     [rdi+0Ch], eax
0x1800836e0  mov     al, [rdx+r8]
0x1800836e4  mov     edx, 18h
0x1800836e9  and     al, 0Fh
0x1800836eb  mov     [rbx], al
0x1800836ed  call    sqlite3DbMallocZero
0x1800836f2  mov     [rdi+28h], rax
0x1800836f6  test    rax, rax
0x1800836f9  jnz     short loc_180083702
0x1800836fb  mov     eax, 7
0x180083700  jmp     short loc_18008372A
0x180083702  mov     [rdi+1Ch], r12d
0x180083706  mov     [rdi+20h], r12d
0x18008370a  mov     [rax+10h], r15
0x18008370e  mov     eax, [rdi+10h]
0x180083711  mov     rcx, [rdi+28h]
0x180083715  mov     [rcx+8], eax
0x180083718  mov     eax, [rdi+0Ch]
0x18008371b  mov     rcx, [rdi+28h]
0x18008371f  mov     [rcx], eax
0x180083721  mov     rax, [rdi+28h]
0x180083725  mov     [rax+4], esi
0x180083728  xor     eax, eax
0x18008372a  mov     rbx, [rsp+48h+arg_0]
0x18008372f  mov     rbp, [rsp+48h+arg_10]
0x180083734  add     rsp, 20h
0x180083738  pop     r15
0x18008373a  pop     r14
0x18008373c  pop     r12
0x18008373e  pop     rdi
0x18008373f  pop     rsi
0x180083740  retn
```
