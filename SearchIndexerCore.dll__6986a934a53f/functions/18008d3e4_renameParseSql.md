# renameParseSql

- ea: `0x18008d3e4`
- end: `0x18008d4df`
- name: `renameParseSql`
- size: `251`
- prototype: ``
- caller_count: `5`
- callee_count: `6`
- tags: ``

## callers

- `0x1800774f0`
- `0x1800777f0`
- `0x18007dcb0`
- `0x18008ca10`
- `0x18008d8d0`

## callees

- `0x180021404`
- `0x18002619c`
- `0x18003d760`
- `0x180053e08`
- `0x18008d3e4`
- `0x180093b3c`

## string_xrefs

- `0x18008d417`: `CREATE `

## pseudocode

```c
__int64 __fastcall renameParseSql(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5)
{
  unsigned int v10; // ebx
  char DbName; // al
  unsigned int v12; // eax

  sqlite3ParseObjectInit(a1, a3);
  if ( !a4 )
    return 7;
  v10 = 7;
  if ( (unsigned int)sqlite3_strnicmp(a4, "CREATE ", 7) )
    return sqlite3ReportError(11, 117565, "database corruption");
  if ( a5 )
    DbName = 1;
  else
    DbName = sqlite3FindDbName(a3, a2);
  *(_BYTE *)(a3 + 196) = DbName;
  *(_BYTE *)(a1 + 308) = 2;
  *(_QWORD *)a1 = a3;
  *(_WORD *)(a1 + 224) = 1;
  v12 = sqlite3RunParser(a1, a4);
  if ( !*(_BYTE *)(a3 + 103) )
  {
    v10 = v12;
    if ( !v12 && !*(_QWORD *)(a1 + 352) && !*(_QWORD *)(a1 + 360) && !*(_QWORD *)(a1 + 368) )
      v10 = sqlite3ReportError(11, 117576, "database corruption");
  }
  *(_BYTE *)(a3 + 196) = 0;
  return v10;
}

```

## disassembly

```asm
0x18008d3e4  push    rbx
0x18008d3e6  push    rbp
0x18008d3e7  push    rsi
0x18008d3e8  push    rdi
0x18008d3e9  push    r12
0x18008d3eb  push    r14
0x18008d3ed  sub     rsp, 28h
0x18008d3f1  mov     r14, rdx
0x18008d3f4  mov     rbp, r9
0x18008d3f7  mov     rdx, r8
0x18008d3fa  mov     rsi, r8
0x18008d3fd  mov     rdi, rcx
0x18008d400  call    sqlite3ParseObjectInit
0x18008d405  test    rbp, rbp
0x18008d408  jnz     short loc_18008D412
0x18008d40a  lea     eax, [rbp+7]
0x18008d40d  jmp     loc_18008D4D2
0x18008d412  mov     ebx, 7
0x18008d417  lea     rdx, aCreate; "CREATE "
0x18008d41e  mov     r8d, ebx
0x18008d421  mov     rcx, rbp
0x18008d424  call    sqlite3_strnicmp
0x18008d429  test    eax, eax
0x18008d42b  jz      short loc_18008D446
0x18008d42d  lea     r8, aDatabaseCorrup; "database corruption"
0x18008d434  mov     edx, 1CB3Dh
0x18008d439  lea     ecx, [rbx+4]
0x18008d43c  call    sqlite3ReportError
0x18008d441  jmp     loc_18008D4D2
0x18008d446  cmp     [rsp+58h+arg_20], 0
0x18008d44e  mov     r12d, 1
0x18008d454  jz      short loc_18008D45B
0x18008d456  mov     eax, r12d
0x18008d459  jmp     short loc_18008D466
0x18008d45b  mov     rdx, r14
0x18008d45e  mov     rcx, rsi
0x18008d461  call    sqlite3FindDbName
0x18008d466  mov     [rsi+0C4h], al
0x18008d46c  mov     rdx, rbp
0x18008d46f  mov     rcx, rdi
0x18008d472  mov     byte ptr [rdi+134h], 2
0x18008d479  mov     [rdi], rsi
0x18008d47c  mov     [rdi+0E0h], r12w
0x18008d484  call    sqlite3RunParser
0x18008d489  cmp     byte ptr [rsi+67h], 0
0x18008d48d  jnz     short loc_18008D4C9
0x18008d48f  mov     ebx, eax
0x18008d491  test    eax, eax
0x18008d493  jnz     short loc_18008D4C9
0x18008d495  cmp     qword ptr [rdi+160h], 0
0x18008d49d  jnz     short loc_18008D4C9
0x18008d49f  cmp     qword ptr [rdi+168h], 0
0x18008d4a7  jnz     short loc_18008D4C9
0x18008d4a9  cmp     qword ptr [rdi+170h], 0
0x18008d4b1  jnz     short loc_18008D4C9
0x18008d4b3  lea     r8, aDatabaseCorrup; "database corruption"
0x18008d4ba  mov     edx, 1CB48h
0x18008d4bf  lea     ecx, [rax+0Bh]
0x18008d4c2  call    sqlite3ReportError
0x18008d4c7  mov     ebx, eax
0x18008d4c9  mov     byte ptr [rsi+0C4h], 0
0x18008d4d0  mov     eax, ebx
0x18008d4d2  add     rsp, 28h
0x18008d4d6  pop     r14
0x18008d4d8  pop     r12
0x18008d4da  pop     rdi
0x18008d4db  pop     rsi
0x18008d4dc  pop     rbp
0x18008d4dd  pop     rbx
0x18008d4de  retn
```
