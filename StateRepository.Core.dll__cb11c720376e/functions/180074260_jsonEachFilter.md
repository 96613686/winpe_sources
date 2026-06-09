# jsonEachFilter

- ea: `0x180074260`
- end: `0x1800744f1`
- name: `jsonEachFilter`
- size: `657`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config`

## callees

- `0x180001110`
- `0x180005810`
- `0x18000aac0`
- `0x18000f720`
- `0x180027a20`
- `0x180028540`
- `0x180048d38`
- `0x18006910e`
- `0x180072cd8`
- `0x1800734f0`
- `0x180073c34`
- `0x1800741d0`
- `0x180074260`
- `0x180074d08`
- `0x1800754f0`
- `0x180078a58`

## string_xrefs

- `0x1800743ab`: `malformed JSON`

## pseudocode

```c
__int64 __fastcall jsonEachFilter(__int64 a1, int a2, __int64 a3, __int64 a4, _QWORD *a5)
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
  jsonEachCursorReset(a1);
  if ( !a2 )
    return 0;
  v7 = (__int64 *)(a1 + 192);
  memset_0((void *)(a1 + 192), 0, 0x48u);
  v8 = *(_QWORD *)(a1 + 48);
  v9 = a5;
  *(_DWORD *)(a1 + 228) = 1;
  *(_QWORD *)(a1 + 216) = v8;
  v10 = jsonFuncArgMightBeBinary(*v9);
  v11 = *v9;
  LOBYTE(v12) = 1;
  if ( v10 )
  {
    *(_DWORD *)(a1 + 200) = sqlite3ValueBytes(v11, v12);
    *v7 = sqlite3_value_blob(*v9);
  }
  else
  {
    *(_QWORD *)(a1 + 208) = sqlite3ValueText(v11, v12);
    LOBYTE(v19) = 1;
    *(_DWORD *)(a1 + 224) = sqlite3ValueBytes(*v9, v19);
    if ( !*(_QWORD *)(a1 + 208) )
    {
      *(_QWORD *)(a1 + 12) = 0;
      return 0;
    }
    if ( (unsigned int)jsonConvertTextToBlob(a1 + 192, 0) )
    {
      if ( !*(_BYTE *)(a1 + 239) )
      {
        sqlite3_free(*(_QWORD *)(*(_QWORD *)a1 + 16LL));
        v16 = *(_QWORD *)a1;
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
      sqlite3_free(*(_QWORD *)(*(_QWORD *)a1 + 16LL));
      v16 = *(_QWORD *)a1;
      v17 = jsonBadPathError(0);
LABEL_8:
      *(_QWORD *)(v16 + 16) = v17;
      jsonEachCursorReset(a1);
      return *(_QWORD *)(*(_QWORD *)a1 + 16LL) != 0 ? 1 : 7;
    }
    *(_DWORD *)(a1 + 20) = sqlite3Strlen30(v14);
    if ( v15[1] )
    {
      v23 = jsonLookupStep(a1 + 192, 0, v15 + 1, 0);
      v21 = v23;
      if ( v23 >= 0xFFFFFFFD )
      {
        if ( v23 != -2 )
          goto LABEL_7;
        *(_QWORD *)(a1 + 12) = 0;
        *(_BYTE *)(a1 + 24) = 0;
        return 0;
      }
      v22 = *(_DWORD *)(a1 + 252);
      v20 = (_BYTE *)(a1 + 24);
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
      v20 = (_BYTE *)(a1 + 24);
      v21 = 0;
      *(_BYTE *)(a1 + 24) = 0;
      v22 = 0;
    }
    *(_DWORD *)(a1 + 12) = v22;
    v24 = *(_DWORD *)(a1 + 20);
  }
  else
  {
    v20 = (_BYTE *)(a1 + 24);
    *(_DWORD *)(a1 + 12) = 0;
    *(_BYTE *)(a1 + 24) = 0;
    v15 = "$";
    v21 = 0;
    *(_DWORD *)(a1 + 20) = 1;
    v24 = 1;
  }
  jsonAppendRaw((_QWORD *)(a1 + 56), v15, v24);
  *(_DWORD *)(a1 + 28) = 0;
  v25 = jsonbPayloadSize((__int64 *)(a1 + 192), v21, &v29);
  v26 = *v7;
  *(_DWORD *)(a1 + 16) = v21 + v25 + v29;
  if ( (*(_BYTE *)(v21 + v26) & 0xFu) >= 0xB && !*(_BYTE *)(a1 + 25) )
  {
    v27 = *(_QWORD *)(a1 + 48);
    *(_DWORD *)(a1 + 12) = v21 + v25;
    *v20 = *(_BYTE *)(v21 + v26) & 0xF;
    v28 = sqlite3DbMallocZero(v27, 24);
    *(_QWORD *)(a1 + 40) = v28;
    if ( !v28 )
      return 7;
    *(_DWORD *)(a1 + 28) = 1;
    *(_DWORD *)(a1 + 32) = 1;
    *(_QWORD *)(v28 + 16) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 40) + 8LL) = *(_DWORD *)(a1 + 16);
    **(_DWORD **)(a1 + 40) = *(_DWORD *)(a1 + 12);
    *(_DWORD *)(*(_QWORD *)(a1 + 40) + 4LL) = v21;
  }
  return 0;
}

```

## disassembly

```asm
0x180074260  mov     [rsp+arg_0], rbx
0x180074265  mov     [rsp+arg_10], rbp
0x18007426a  push    rsi
0x18007426b  push    rdi
0x18007426c  push    r12
0x18007426e  push    r14
0x180074270  push    r15
0x180074272  sub     rsp, 20h
0x180074276  xor     r15d, r15d
0x180074279  mov     esi, edx
0x18007427b  mov     [rsp+48h+arg_8], r15d
0x180074280  mov     rdi, rcx
0x180074283  call    jsonEachCursorReset
0x180074288  test    esi, esi
0x18007428a  jz      loc_1800744D8
0x180074290  lea     r14, [rdi+0C0h]
0x180074297  xor     edx, edx; Val
0x180074299  mov     rcx, r14; void *
0x18007429c  lea     r8d, [r15+48h]; Size
0x1800742a0  call    memset_0
0x1800742a5  mov     rax, [rdi+30h]
0x1800742a9  lea     r12d, [r15+1]
0x1800742ad  mov     rbx, [rsp+48h+arg_20]
0x1800742b2  mov     [rdi+0E4h], r12d
0x1800742b9  mov     [rdi+0D8h], rax
0x1800742c0  mov     rcx, [rbx]
0x1800742c3  call    jsonFuncArgMightBeBinary
0x1800742c8  mov     rcx, [rbx]
0x1800742cb  mov     dl, r12b
0x1800742ce  test    eax, eax
0x1800742d0  jz      short loc_18007434E
0x1800742d2  call    sqlite3ValueBytes
0x1800742d7  mov     [rdi+0C8h], eax
0x1800742dd  mov     rcx, [rbx]
0x1800742e0  call    sqlite3_value_blob
0x1800742e5  mov     [r14], rax
0x1800742e8  cmp     esi, 3
0x1800742eb  jnz     loc_18007442A
0x1800742f1  mov     rcx, [rbx+8]
0x1800742f5  mov     dl, r12b
0x1800742f8  call    sqlite3ValueText
0x1800742fd  mov     rbp, rax
0x180074300  test    rax, rax
0x180074303  jz      loc_1800744D8
0x180074309  cmp     byte ptr [rax], 24h ; '$'
0x18007430c  jz      loc_1800743BC
0x180074312  mov     rcx, [rdi]
0x180074315  mov     rcx, [rcx+10h]
0x180074319  call    sqlite3_free
0x18007431e  mov     rbx, [rdi]
0x180074321  mov     rdx, rbp
0x180074324  xor     ecx, ecx
0x180074326  call    jsonBadPathError
0x18007432b  mov     rcx, rdi
0x18007432e  mov     [rbx+10h], rax
0x180074332  call    jsonEachCursorReset
0x180074337  mov     rax, [rdi]
0x18007433a  mov     rcx, [rax+10h]
0x18007433e  neg     rcx
0x180074341  sbb     eax, eax
0x180074343  and     eax, 0FFFFFFFAh
0x180074346  add     eax, 7
0x180074349  jmp     loc_1800744DA
0x18007434e  call    sqlite3ValueText
0x180074353  mov     [rdi+0D0h], rax
0x18007435a  mov     dl, r12b
0x18007435d  mov     rcx, [rbx]
0x180074360  call    sqlite3ValueBytes
0x180074365  mov     [rdi+0E0h], eax
0x18007436b  cmp     [rdi+0D0h], r15
0x180074372  jnz     short loc_18007437D
0x180074374  mov     [rdi+0Ch], r15
0x180074378  jmp     loc_1800744D8
0x18007437d  xor     edx, edx
0x18007437f  mov     rcx, r14
0x180074382  call    jsonConvertTextToBlob
0x180074387  test    eax, eax
0x180074389  jz      loc_1800742E8
0x18007438f  cmp     [rdi+0EFh], r15b
0x180074396  jnz     loc_1800744AB
0x18007439c  mov     rcx, [rdi]
0x18007439f  mov     rcx, [rcx+10h]
0x1800743a3  call    sqlite3_free
0x1800743a8  mov     rbx, [rdi]
0x1800743ab  lea     rcx, aMalformedJson; "malformed JSON"
0x1800743b2  call    sqlite3_mprintf
0x1800743b7  jmp     loc_18007432B
0x1800743bc  mov     rcx, rbp
0x1800743bf  call    sqlite3Strlen30
0x1800743c4  lea     r8, [rbp+1]
0x1800743c8  mov     [rdi+14h], eax
0x1800743cb  cmp     [r8], r15b
0x1800743ce  jnz     short loc_1800743DF
0x1800743d0  lea     rbx, [rdi+18h]
0x1800743d4  mov     esi, r15d
0x1800743d7  mov     [rbx], r15b
0x1800743da  mov     eax, r15d
0x1800743dd  jmp     short loc_180074421
0x1800743df  xor     r9d, r9d
0x1800743e2  xor     edx, edx
0x1800743e4  mov     rcx, r14
0x1800743e7  call    jsonLookupStep
0x1800743ec  mov     esi, eax
0x1800743ee  cmp     eax, 0FFFFFFFDh
0x1800743f1  jb      short loc_180074409
0x1800743f3  cmp     eax, 0FFFFFFFEh
0x1800743f6  jnz     loc_180074312
0x1800743fc  mov     [rdi+0Ch], r15
0x180074400  mov     [rdi+18h], r15b
0x180074404  jmp     loc_1800744D8
0x180074409  mov     eax, [rdi+0FCh]
0x18007440f  lea     rbx, [rdi+18h]
0x180074413  test    eax, eax
0x180074415  jz      short loc_18007441C
0x180074417  mov     byte ptr [rbx], 0Ch
0x18007441a  jmp     short loc_180074421
0x18007441c  mov     byte ptr [rbx], 0Bh
0x18007441f  mov     eax, esi
0x180074421  mov     [rdi+0Ch], eax
0x180074424  mov     r8d, [rdi+14h]
0x180074428  jmp     short loc_180074446
0x18007442a  lea     rbx, [rdi+18h]
0x18007442e  mov     [rdi+0Ch], r15d
0x180074432  mov     [rbx], r15b
0x180074435  lea     rbp, asc_1800A6360; "$"
0x18007443c  mov     esi, r15d
0x18007443f  mov     [rdi+14h], r12d
0x180074443  mov     r8d, r12d
0x180074446  lea     rcx, [rdi+38h]
0x18007444a  mov     rdx, rbp
0x18007444d  call    jsonAppendRaw
0x180074452  lea     r8, [rsp+48h+arg_8]
0x180074457  mov     [rdi+1Ch], r15d
0x18007445b  mov     edx, esi
0x18007445d  mov     rcx, r14
0x180074460  call    jsonbPayloadSize
0x180074465  mov     edx, [rsp+48h+arg_8]
0x180074469  mov     r8, [r14]
0x18007446c  add     edx, eax
0x18007446e  add     edx, esi
0x180074470  mov     [rdi+10h], edx
0x180074473  mov     edx, esi
0x180074475  mov     cl, [rdx+r8]
0x180074479  and     cl, 0Fh
0x18007447c  cmp     cl, 0Bh
0x18007447f  jb      short loc_1800744D8
0x180074481  cmp     [rdi+19h], r15b
0x180074485  jnz     short loc_1800744D8
0x180074487  mov     rcx, [rdi+30h]
0x18007448b  add     eax, esi
0x18007448d  mov     [rdi+0Ch], eax
0x180074490  mov     al, [rdx+r8]
0x180074494  mov     edx, 18h
0x180074499  and     al, 0Fh
0x18007449b  mov     [rbx], al
0x18007449d  call    sqlite3DbMallocZero
0x1800744a2  mov     [rdi+28h], rax
0x1800744a6  test    rax, rax
0x1800744a9  jnz     short loc_1800744B2
0x1800744ab  mov     eax, 7
0x1800744b0  jmp     short loc_1800744DA
0x1800744b2  mov     [rdi+1Ch], r12d
0x1800744b6  mov     [rdi+20h], r12d
0x1800744ba  mov     [rax+10h], r15
0x1800744be  mov     eax, [rdi+10h]
0x1800744c1  mov     rcx, [rdi+28h]
0x1800744c5  mov     [rcx+8], eax
0x1800744c8  mov     eax, [rdi+0Ch]
0x1800744cb  mov     rcx, [rdi+28h]
0x1800744cf  mov     [rcx], eax
0x1800744d1  mov     rax, [rdi+28h]
0x1800744d5  mov     [rax+4], esi
0x1800744d8  xor     eax, eax
0x1800744da  mov     rbx, [rsp+48h+arg_0]
0x1800744df  mov     rbp, [rsp+48h+arg_10]
0x1800744e4  add     rsp, 20h
0x1800744e8  pop     r15
0x1800744ea  pop     r14
0x1800744ec  pop     r12
0x1800744ee  pop     rdi
0x1800744ef  pop     rsi
0x1800744f0  retn
```
