# renameParseSql

- ea: `0x18007e074`
- end: `0x18007e16f`
- name: `renameParseSql`
- size: `251`
- prototype: ``
- caller_count: `5`
- callee_count: `6`
- tags: ``

## callers

- `0x180065620`
- `0x1800659c0`
- `0x18006dff0`
- `0x18007d6a0`
- `0x18007e570`

## callees

- `0x180014928`
- `0x180030d98`
- `0x18004b050`
- `0x180060134`
- `0x18007e074`
- `0x180085fe8`

## string_xrefs

- `0x18007e0a7`: `CREATE `

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
  if ( (unsigned int)sqlite3_strnicmp(a4, "CREATE ") )
    return sqlite3ReportError(11, 117868, "database corruption");
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
      v10 = sqlite3ReportError(11, 117879, "database corruption");
  }
  *(_BYTE *)(a3 + 196) = 0;
  return v10;
}

```

## disassembly

```asm
0x18007e074  push    rbx
0x18007e076  push    rbp
0x18007e077  push    rsi
0x18007e078  push    rdi
0x18007e079  push    r12
0x18007e07b  push    r14
0x18007e07d  sub     rsp, 28h
0x18007e081  mov     r14, rdx
0x18007e084  mov     rbp, r9
0x18007e087  mov     rdx, r8
0x18007e08a  mov     rsi, r8
0x18007e08d  mov     rdi, rcx
0x18007e090  call    sqlite3ParseObjectInit
0x18007e095  test    rbp, rbp
0x18007e098  jnz     short loc_18007E0A2
0x18007e09a  lea     eax, [rbp+7]
0x18007e09d  jmp     loc_18007E162
0x18007e0a2  mov     ebx, 7
0x18007e0a7  lea     rdx, aCreate; "CREATE "
0x18007e0ae  mov     r8d, ebx
0x18007e0b1  mov     rcx, rbp
0x18007e0b4  call    sqlite3_strnicmp
0x18007e0b9  test    eax, eax
0x18007e0bb  jz      short loc_18007E0D6
0x18007e0bd  lea     r8, aDatabaseCorrup; "database corruption"
0x18007e0c4  mov     edx, 1CC6Ch
0x18007e0c9  lea     ecx, [rbx+4]
0x18007e0cc  call    sqlite3ReportError
0x18007e0d1  jmp     loc_18007E162
0x18007e0d6  cmp     [rsp+58h+arg_20], 0
0x18007e0de  mov     r12d, 1
0x18007e0e4  jz      short loc_18007E0EB
0x18007e0e6  mov     eax, r12d
0x18007e0e9  jmp     short loc_18007E0F6
0x18007e0eb  mov     rdx, r14
0x18007e0ee  mov     rcx, rsi
0x18007e0f1  call    sqlite3FindDbName
0x18007e0f6  mov     [rsi+0C4h], al
0x18007e0fc  mov     rdx, rbp
0x18007e0ff  mov     rcx, rdi
0x18007e102  mov     byte ptr [rdi+134h], 2
0x18007e109  mov     [rdi], rsi
0x18007e10c  mov     [rdi+0E0h], r12w
0x18007e114  call    sqlite3RunParser
0x18007e119  cmp     byte ptr [rsi+67h], 0
0x18007e11d  jnz     short loc_18007E159
0x18007e11f  mov     ebx, eax
0x18007e121  test    eax, eax
0x18007e123  jnz     short loc_18007E159
0x18007e125  cmp     qword ptr [rdi+160h], 0
0x18007e12d  jnz     short loc_18007E159
0x18007e12f  cmp     qword ptr [rdi+168h], 0
0x18007e137  jnz     short loc_18007E159
0x18007e139  cmp     qword ptr [rdi+170h], 0
0x18007e141  jnz     short loc_18007E159
0x18007e143  lea     r8, aDatabaseCorrup; "database corruption"
0x18007e14a  mov     edx, 1CC77h
0x18007e14f  lea     ecx, [rax+0Bh]
0x18007e152  call    sqlite3ReportError
0x18007e157  mov     ebx, eax
0x18007e159  mov     byte ptr [rsi+0C4h], 0
0x18007e160  mov     eax, ebx
0x18007e162  add     rsp, 28h
0x18007e166  pop     r14
0x18007e168  pop     r12
0x18007e16a  pop     rdi
0x18007e16b  pop     rsi
0x18007e16c  pop     rbp
0x18007e16d  pop     rbx
0x18007e16e  retn
```
