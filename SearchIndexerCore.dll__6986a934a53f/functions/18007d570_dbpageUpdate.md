# dbpageUpdate

- ea: `0x18007d570`
- end: `0x18007d72a`
- name: `dbpageUpdate`
- size: `442`
- prototype: `__int64 __fastcall(__int64, int, _QWORD *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, installer_update`

## callees

- `0x180024b60`
- `0x1800263c0`
- `0x180028090`
- `0x1800310a0`
- `0x180041eb0`
- `0x1800531c0`
- `0x180053e08`
- `0x1800543d0`
- `0x180054e70`
- `0x180054ef4`
- `0x18007d570`
- `0x1800af620`

## string_xrefs

- `0x18007d5a0`: `read-only`
- `0x18007d5b1`: `cannot delete`

## pseudocode

```c
__int64 __fastcall dbpageUpdate(__int64 a1, int a2, _QWORD *a3)
{
  __int64 v3; // rax
  const char *v6; // rbx
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // rax
  int DbName; // eax
  __int64 v11; // rbp
  __int64 v12; // rdx
  __int64 v13; // rcx
  size_t v14; // r14
  unsigned int v15; // ebx
  const void *v16; // rdi
  __int64 v18; // [rsp+40h] [rbp+8h] BYREF

  v3 = *(_QWORD *)(a1 + 24);
  v18 = 0;
  if ( (*(_DWORD *)(v3 + 48) & 0x10000000) != 0 )
  {
    v6 = "read-only";
LABEL_23:
    sqlite3_free(*(_QWORD *)(a1 + 16));
    *(_QWORD *)(a1 + 16) = sqlite3_mprintf("%s", v6);
    return 1;
  }
  if ( a2 == 1 )
  {
    v6 = "cannot delete";
    goto LABEL_23;
  }
  v7 = sqlite3VdbeIntValue(*a3);
  if ( *((_BYTE *)qword_1800B5270 + (*(_WORD *)(*a3 + 20LL) & 0x3F)) == 5
    || (unsigned int)sqlite3VdbeIntValue(a3[1]) != v7 )
  {
    v6 = "cannot insert";
    goto LABEL_23;
  }
  LOBYTE(v8) = 1;
  v9 = sqlite3ValueText(a3[4], v8);
  if ( !v9 || (DbName = sqlite3FindDbName(*(_QWORD *)(a1 + 24), v9), DbName < 0) )
  {
    v6 = "no such schema";
    goto LABEL_23;
  }
  _mm_lfence();
  if ( !v7
    || (v11 = *(_QWORD *)(32LL * DbName + *(_QWORD *)(*(_QWORD *)(a1 + 24) + 32LL) + 8)) == 0
    || (v12 = *(_QWORD *)(v11 + 8), v7 > *(_DWORD *)(v12 + 64)) )
  {
    v6 = "bad page number";
    goto LABEL_23;
  }
  v13 = a3[3];
  if ( *((_BYTE *)qword_1800B5270 + (*(_WORD *)(v13 + 20) & 0x3F)) != 4
    || (v14 = *(int *)(v12 + 52), LOBYTE(v12) = 1, (unsigned int)sqlite3ValueBytes(v13, v12) != (_DWORD)v14) )
  {
    v6 = "bad page value";
    goto LABEL_23;
  }
  v15 = sqlite3PagerGet(**(_QWORD **)(v11 + 8), v7, &v18, 0);
  if ( !v15 )
  {
    v16 = (const void *)sqlite3_value_blob(a3[3]);
    if ( v16 )
    {
      v15 = sqlite3PagerWrite(v18);
      if ( !v15 )
        memcpy_0(*(void **)(v18 + 8), v16, v14);
    }
  }
  sqlite3PagerUnref(v18);
  return v15;
}

```

## disassembly

```asm
0x18007d570  mov     [rsp+arg_8], rbx
0x18007d575  mov     [rsp+arg_10], rbp
0x18007d57a  push    rsi
0x18007d57b  push    rdi
0x18007d57c  push    r14
0x18007d57e  sub     rsp, 20h
0x18007d582  mov     rax, [rcx+18h]
0x18007d586  mov     rdi, r8
0x18007d589  mov     [rsp+38h+arg_0], 0
0x18007d592  mov     rsi, rcx
0x18007d595  mov     r9d, [rax+30h]
0x18007d599  bt      r9, 1Ch
0x18007d59e  jnb     short loc_18007D5AC
0x18007d5a0  lea     rbx, aReadOnly; "read-only"
0x18007d5a7  jmp     loc_18007D6F6
0x18007d5ac  cmp     edx, 1
0x18007d5af  jnz     short loc_18007D5BD
0x18007d5b1  lea     rbx, aCannotDelete; "cannot delete"
0x18007d5b8  jmp     loc_18007D6F6
0x18007d5bd  mov     rcx, [r8]
0x18007d5c0  call    sqlite3VdbeIntValue
0x18007d5c5  mov     rbx, rax
0x18007d5c8  lea     r14, qword_1800B5270
0x18007d5cf  mov     rax, [rdi]
0x18007d5d2  movzx   ecx, word ptr [rax+14h]
0x18007d5d6  and     ecx, 3Fh
0x18007d5d9  cmp     byte ptr [rcx+r14], 5
0x18007d5de  jz      loc_18007D6EF
0x18007d5e4  mov     rcx, [rdi+8]
0x18007d5e8  call    sqlite3VdbeIntValue
0x18007d5ed  cmp     eax, ebx
0x18007d5ef  jnz     loc_18007D6EF
0x18007d5f5  mov     rcx, [rdi+20h]
0x18007d5f9  mov     dl, 1
0x18007d5fb  call    sqlite3ValueText
0x18007d600  test    rax, rax
0x18007d603  jz      loc_18007D6E6
0x18007d609  mov     rcx, [rsi+18h]
0x18007d60d  mov     rdx, rax
0x18007d610  call    sqlite3FindDbName
0x18007d615  test    eax, eax
0x18007d617  js      loc_18007D6E6
0x18007d61d  lfence
0x18007d620  cmp     ebx, 1
0x18007d623  jb      loc_18007D6DD
0x18007d629  movsxd  rdx, eax
0x18007d62c  mov     rax, [rsi+18h]
0x18007d630  shl     rdx, 5
0x18007d634  mov     rcx, [rax+20h]
0x18007d638  mov     rbp, [rdx+rcx+8]
0x18007d63d  test    rbp, rbp
0x18007d640  jz      loc_18007D6DD
0x18007d646  mov     rdx, [rbp+8]
0x18007d64a  cmp     ebx, [rdx+40h]
0x18007d64d  ja      loc_18007D6DD
0x18007d653  mov     rcx, [rdi+18h]
0x18007d657  movzx   eax, word ptr [rcx+14h]
0x18007d65b  and     eax, 3Fh
0x18007d65e  cmp     byte ptr [rax+r14], 4
0x18007d663  jnz     short loc_18007D6D4
0x18007d665  movsxd  r14, dword ptr [rdx+34h]
0x18007d669  mov     dl, 1
0x18007d66b  call    sqlite3ValueBytes
0x18007d670  cmp     eax, r14d
0x18007d673  jnz     short loc_18007D6D4
0x18007d675  mov     rcx, [rbp+8]
0x18007d679  lea     r8, [rsp+38h+arg_0]
0x18007d67e  xor     r9d, r9d
0x18007d681  mov     edx, ebx
0x18007d683  mov     rcx, [rcx]
0x18007d686  call    sqlite3PagerGet
0x18007d68b  mov     ebx, eax
0x18007d68d  test    eax, eax
0x18007d68f  jnz     short loc_18007D6C6
0x18007d691  mov     rcx, [rdi+18h]
0x18007d695  call    sqlite3_value_blob
0x18007d69a  mov     rdi, rax
0x18007d69d  test    rax, rax
0x18007d6a0  jz      short loc_18007D6C6
0x18007d6a2  mov     rcx, [rsp+38h+arg_0]
0x18007d6a7  call    sqlite3PagerWrite
0x18007d6ac  mov     ebx, eax
0x18007d6ae  test    eax, eax
0x18007d6b0  jnz     short loc_18007D6C6
0x18007d6b2  mov     rcx, [rsp+38h+arg_0]
0x18007d6b7  mov     r8, r14; Size
0x18007d6ba  mov     rdx, rdi; Src
0x18007d6bd  mov     rcx, [rcx+8]; void *
0x18007d6c1  call    memcpy_0
0x18007d6c6  mov     rcx, [rsp+38h+arg_0]
0x18007d6cb  call    sqlite3PagerUnref
0x18007d6d0  mov     eax, ebx
0x18007d6d2  jmp     short loc_18007D717
0x18007d6d4  lea     rbx, aBadPageValue; "bad page value"
0x18007d6db  jmp     short loc_18007D6F6
0x18007d6dd  lea     rbx, aBadPageNumber; "bad page number"
0x18007d6e4  jmp     short loc_18007D6F6
0x18007d6e6  lea     rbx, aNoSuchSchema; "no such schema"
0x18007d6ed  jmp     short loc_18007D6F6
0x18007d6ef  lea     rbx, aCannotInsert; "cannot insert"
0x18007d6f6  mov     rcx, [rsi+10h]
0x18007d6fa  call    sqlite3_free
0x18007d6ff  mov     rdx, rbx
0x18007d702  lea     rcx, aS_7; "%s"
0x18007d709  call    sqlite3_mprintf
0x18007d70e  mov     [rsi+10h], rax
0x18007d712  mov     eax, 1
0x18007d717  mov     rbx, [rsp+38h+arg_8]
0x18007d71c  mov     rbp, [rsp+38h+arg_10]
0x18007d721  add     rsp, 20h
0x18007d725  pop     r14
0x18007d727  pop     rdi
0x18007d728  pop     rsi
0x18007d729  retn
```
