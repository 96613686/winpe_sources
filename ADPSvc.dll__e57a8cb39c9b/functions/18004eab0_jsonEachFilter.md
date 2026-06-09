# jsonEachFilter

- ea: `0x18004eab0`
- end: `0x18004ed55`
- name: `jsonEachFilter`
- size: `677`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config`

## callees

- `0x180002cf8`
- `0x18004d4e8`
- `0x18004e400`
- `0x18004ea00`
- `0x18004eab0`
- `0x18004f598`
- `0x18004fca4`
- `0x1800539e0`
- `0x1800718ac`
- `0x180092290`
- `0x1800a98a0`
- `0x1800aa540`
- `0x1800ae6c0`
- `0x1800ae720`

## string_xrefs

- `0x18004ec01`: `malformed JSON`
- `0x18004eb72`: `bad JSON path: %Q`

## pseudocode

```c
__int64 __fastcall jsonEachFilter(__int64 *a1, int a2, __int64 a3, __int64 a4, _QWORD *a5)
{
  __int64 *v7; // r14
  __int64 v8; // rax
  _QWORD *v9; // rbx
  int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rdx
  const char *v14; // rax
  const char *v15; // rbp
  __int64 v17; // rbx
  __int64 v18; // rax
  _BYTE *v19; // rbx
  unsigned int v20; // esi
  unsigned int v21; // eax
  unsigned int v22; // eax
  __int64 v23; // r8
  int v24; // eax
  __int64 v25; // r8
  __int64 v26; // rcx
  __int64 v27; // rax
  int v28; // [rsp+58h] [rbp+10h] BYREF

  v28 = 0;
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
  v12 = *v9;
  if ( v10 )
  {
    *((_DWORD *)a1 + 50) = sqlite3_value_bytes(v12);
    *v7 = sqlite3_value_blob(*v9);
  }
  else
  {
    LOBYTE(v11) = 1;
    a1[26] = sqlite3ValueText(v12, v11);
    *((_DWORD *)a1 + 56) = sqlite3_value_bytes(*v9);
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
        v17 = *a1;
        *(_QWORD *)(v17 + 16) = sqlite3_mprintf("malformed JSON");
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
      *(_QWORD *)(*a1 + 16) = sqlite3_mprintf("bad JSON path: %Q", v15);
LABEL_8:
      jsonEachCursorReset(a1);
      return *(_QWORD *)(*a1 + 16) != 0 ? 1 : 7;
    }
    v18 = -1;
    do
      ++v18;
    while ( v15[v18] );
    *((_DWORD *)a1 + 5) = v18 & 0x3FFFFFFF;
    if ( v15[1] )
    {
      v22 = jsonLookupStep(a1 + 24, 0, v15 + 1, 0);
      v20 = v22;
      if ( v22 >= 0xFFFFFFFD )
      {
        if ( v22 != -2 )
          goto LABEL_7;
        *(__int64 *)((char *)a1 + 12) = 0;
        *((_BYTE *)a1 + 24) = 0;
        return 0;
      }
      v21 = *((_DWORD *)a1 + 63);
      v19 = a1 + 3;
      if ( v21 )
      {
        *v19 = 12;
      }
      else
      {
        *v19 = 11;
        v21 = v20;
      }
    }
    else
    {
      v19 = a1 + 3;
      v20 = 0;
      *((_BYTE *)a1 + 24) = 0;
      v21 = 0;
    }
    *((_DWORD *)a1 + 3) = v21;
    v23 = *((unsigned int *)a1 + 5);
  }
  else
  {
    v19 = a1 + 3;
    *((_DWORD *)a1 + 3) = 0;
    *((_BYTE *)a1 + 24) = 0;
    v15 = "$";
    v20 = 0;
    *((_DWORD *)a1 + 5) = 1;
    v23 = 1;
  }
  jsonAppendRaw(a1 + 7, v15, v23);
  *((_DWORD *)a1 + 7) = 0;
  v24 = jsonbPayloadSize(a1 + 24, v20, &v28);
  v25 = *v7;
  *((_DWORD *)a1 + 4) = v20 + v24 + v28;
  if ( (*(_BYTE *)(v20 + v25) & 0xFu) >= 0xB && !*((_BYTE *)a1 + 25) )
  {
    v26 = a1[6];
    *((_DWORD *)a1 + 3) = v20 + v24;
    *v19 = *(_BYTE *)(v20 + v25) & 0xF;
    v27 = sqlite3DbMallocZero(v26, 24);
    a1[5] = v27;
    if ( !v27 )
      return 7;
    *((_DWORD *)a1 + 7) = 1;
    *((_DWORD *)a1 + 8) = 1;
    *(_QWORD *)(v27 + 16) = 0;
    *(_DWORD *)(a1[5] + 8) = *((_DWORD *)a1 + 4);
    *(_DWORD *)a1[5] = *((_DWORD *)a1 + 3);
    *(_DWORD *)(a1[5] + 4) = v20;
  }
  return 0;
}

```

## disassembly

```asm
0x18004eab0  mov     [rsp+arg_0], rbx
0x18004eab5  mov     [rsp+arg_10], rbp
0x18004eaba  push    rsi
0x18004eabb  push    rdi
0x18004eabc  push    r12
0x18004eabe  push    r14
0x18004eac0  push    r15
0x18004eac2  sub     rsp, 20h
0x18004eac6  xor     r15d, r15d
0x18004eac9  mov     esi, edx
0x18004eacb  mov     [rsp+48h+arg_8], r15d
0x18004ead0  mov     rdi, rcx
0x18004ead3  call    jsonEachCursorReset
0x18004ead8  test    esi, esi
0x18004eada  jz      loc_18004ED3C
0x18004eae0  lea     r14, [rdi+0C0h]
0x18004eae7  xor     edx, edx; Val
0x18004eae9  mov     rcx, r14; void *
0x18004eaec  lea     r8d, [r15+48h]; Size
0x18004eaf0  call    memset_0
0x18004eaf5  mov     rax, [rdi+30h]
0x18004eaf9  lea     r12d, [r15+1]
0x18004eafd  mov     rbx, [rsp+48h+arg_20]
0x18004eb02  mov     [rdi+0E4h], r12d
0x18004eb09  mov     [rdi+0D8h], rax
0x18004eb10  mov     rcx, [rbx]
0x18004eb13  call    jsonFuncArgMightBeBinary
0x18004eb18  mov     rcx, [rbx]
0x18004eb1b  test    eax, eax
0x18004eb1d  jz      loc_18004EBA4
0x18004eb23  call    sqlite3_value_bytes
0x18004eb28  mov     [rdi+0C8h], eax
0x18004eb2e  mov     rcx, [rbx]
0x18004eb31  call    sqlite3_value_blob
0x18004eb36  mov     [r14], rax
0x18004eb39  cmp     esi, 3
0x18004eb3c  jnz     loc_18004EC8E
0x18004eb42  mov     rcx, [rbx+8]
0x18004eb46  mov     dl, r12b
0x18004eb49  call    sqlite3ValueText
0x18004eb4e  mov     rbp, rax
0x18004eb51  test    rax, rax
0x18004eb54  jz      loc_18004ED3C
0x18004eb5a  cmp     byte ptr [rax], 24h ; '$'
0x18004eb5d  jz      loc_18004EC16
0x18004eb63  mov     rcx, [rdi]
0x18004eb66  mov     rcx, [rcx+10h]
0x18004eb6a  call    sqlite3_free
0x18004eb6f  mov     rdx, rbp
0x18004eb72  lea     rcx, aBadJsonPathQ; "bad JSON path: %Q"
0x18004eb79  call    sqlite3_mprintf
0x18004eb7e  mov     rcx, [rdi]
0x18004eb81  mov     [rcx+10h], rax
0x18004eb85  mov     rcx, rdi
0x18004eb88  call    jsonEachCursorReset
0x18004eb8d  mov     rax, [rdi]
0x18004eb90  mov     rcx, [rax+10h]
0x18004eb94  neg     rcx
0x18004eb97  sbb     eax, eax
0x18004eb99  and     eax, 0FFFFFFFAh
0x18004eb9c  add     eax, 7
0x18004eb9f  jmp     loc_18004ED3E
0x18004eba4  mov     dl, r12b
0x18004eba7  call    sqlite3ValueText
0x18004ebac  mov     [rdi+0D0h], rax
0x18004ebb3  mov     rcx, [rbx]
0x18004ebb6  call    sqlite3_value_bytes
0x18004ebbb  mov     [rdi+0E0h], eax
0x18004ebc1  cmp     [rdi+0D0h], r15
0x18004ebc8  jnz     short loc_18004EBD3
0x18004ebca  mov     [rdi+0Ch], r15
0x18004ebce  jmp     loc_18004ED3C
0x18004ebd3  xor     edx, edx
0x18004ebd5  mov     rcx, r14
0x18004ebd8  call    jsonConvertTextToBlob
0x18004ebdd  test    eax, eax
0x18004ebdf  jz      loc_18004EB39
0x18004ebe5  cmp     [rdi+0EFh], r15b
0x18004ebec  jnz     loc_18004ED0F
0x18004ebf2  mov     rcx, [rdi]
0x18004ebf5  mov     rcx, [rcx+10h]
0x18004ebf9  call    sqlite3_free
0x18004ebfe  mov     rbx, [rdi]
0x18004ec01  lea     rcx, aMalformedJson; "malformed JSON"
0x18004ec08  call    sqlite3_mprintf
0x18004ec0d  mov     [rbx+10h], rax
0x18004ec11  jmp     loc_18004EB85
0x18004ec16  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004ec1a  inc     rax
0x18004ec1d  cmp     [rax+rbp], r15b
0x18004ec21  jnz     short loc_18004EC1A
0x18004ec23  and     eax, 3FFFFFFFh
0x18004ec28  lea     r8, [rbp+1]
0x18004ec2c  mov     [rdi+14h], eax
0x18004ec2f  cmp     [r8], r15b
0x18004ec32  jnz     short loc_18004EC43
0x18004ec34  lea     rbx, [rdi+18h]
0x18004ec38  mov     esi, r15d
0x18004ec3b  mov     [rbx], r15b
0x18004ec3e  mov     eax, r15d
0x18004ec41  jmp     short loc_18004EC85
0x18004ec43  xor     r9d, r9d
0x18004ec46  xor     edx, edx
0x18004ec48  mov     rcx, r14
0x18004ec4b  call    jsonLookupStep
0x18004ec50  mov     esi, eax
0x18004ec52  cmp     eax, 0FFFFFFFDh
0x18004ec55  jb      short loc_18004EC6D
0x18004ec57  cmp     eax, 0FFFFFFFEh
0x18004ec5a  jnz     loc_18004EB63
0x18004ec60  mov     [rdi+0Ch], r15
0x18004ec64  mov     [rdi+18h], r15b
0x18004ec68  jmp     loc_18004ED3C
0x18004ec6d  mov     eax, [rdi+0FCh]
0x18004ec73  lea     rbx, [rdi+18h]
0x18004ec77  test    eax, eax
0x18004ec79  jz      short loc_18004EC80
0x18004ec7b  mov     byte ptr [rbx], 0Ch
0x18004ec7e  jmp     short loc_18004EC85
0x18004ec80  mov     byte ptr [rbx], 0Bh
0x18004ec83  mov     eax, esi
0x18004ec85  mov     [rdi+0Ch], eax
0x18004ec88  mov     r8d, [rdi+14h]
0x18004ec8c  jmp     short loc_18004ECAA
0x18004ec8e  lea     rbx, [rdi+18h]
0x18004ec92  mov     [rdi+0Ch], r15d
0x18004ec96  mov     [rbx], r15b
0x18004ec99  lea     rbp, asc_1800FA264; "$"
0x18004eca0  mov     esi, r15d
0x18004eca3  mov     [rdi+14h], r12d
0x18004eca7  mov     r8d, r12d
0x18004ecaa  lea     rcx, [rdi+38h]
0x18004ecae  mov     rdx, rbp
0x18004ecb1  call    jsonAppendRaw
0x18004ecb6  lea     r8, [rsp+48h+arg_8]
0x18004ecbb  mov     [rdi+1Ch], r15d
0x18004ecbf  mov     edx, esi
0x18004ecc1  mov     rcx, r14
0x18004ecc4  call    jsonbPayloadSize
0x18004ecc9  mov     edx, [rsp+48h+arg_8]
0x18004eccd  mov     r8, [r14]
0x18004ecd0  add     edx, eax
0x18004ecd2  add     edx, esi
0x18004ecd4  mov     [rdi+10h], edx
0x18004ecd7  mov     edx, esi
0x18004ecd9  mov     cl, [rdx+r8]
0x18004ecdd  and     cl, 0Fh
0x18004ece0  cmp     cl, 0Bh
0x18004ece3  jb      short loc_18004ED3C
0x18004ece5  cmp     [rdi+19h], r15b
0x18004ece9  jnz     short loc_18004ED3C
0x18004eceb  mov     rcx, [rdi+30h]
0x18004ecef  add     eax, esi
0x18004ecf1  mov     [rdi+0Ch], eax
0x18004ecf4  mov     al, [rdx+r8]
0x18004ecf8  mov     edx, 18h
0x18004ecfd  and     al, 0Fh
0x18004ecff  mov     [rbx], al
0x18004ed01  call    sqlite3DbMallocZero
0x18004ed06  mov     [rdi+28h], rax
0x18004ed0a  test    rax, rax
0x18004ed0d  jnz     short loc_18004ED16
0x18004ed0f  mov     eax, 7
0x18004ed14  jmp     short loc_18004ED3E
0x18004ed16  mov     [rdi+1Ch], r12d
0x18004ed1a  mov     [rdi+20h], r12d
0x18004ed1e  mov     [rax+10h], r15
0x18004ed22  mov     eax, [rdi+10h]
0x18004ed25  mov     rcx, [rdi+28h]
0x18004ed29  mov     [rcx+8], eax
0x18004ed2c  mov     eax, [rdi+0Ch]
0x18004ed2f  mov     rcx, [rdi+28h]
0x18004ed33  mov     [rcx], eax
0x18004ed35  mov     rax, [rdi+28h]
0x18004ed39  mov     [rax+4], esi
0x18004ed3c  xor     eax, eax
0x18004ed3e  mov     rbx, [rsp+48h+arg_0]
0x18004ed43  mov     rbp, [rsp+48h+arg_10]
0x18004ed48  add     rsp, 20h
0x18004ed4c  pop     r15
0x18004ed4e  pop     r14
0x18004ed50  pop     r12
0x18004ed52  pop     rdi
0x18004ed53  pop     rsi
0x18004ed54  retn
```
