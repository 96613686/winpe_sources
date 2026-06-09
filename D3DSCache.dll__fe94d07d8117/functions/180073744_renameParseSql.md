# renameParseSql

- ea: `0x180073744`
- end: `0x18007383f`
- name: `renameParseSql`
- size: `251`
- prototype: ``
- caller_count: `5`
- callee_count: `6`
- tags: ``

## callers

- `0x180042520`
- `0x180042820`
- `0x18005d050`
- `0x180072d70`
- `0x180073c30`

## callees

- `0x18001b670`
- `0x1800367a0`
- `0x180038a64`
- `0x18003a860`
- `0x180073744`
- `0x1800881a8`

## string_xrefs

- `0x180073777`: `CREATE `

## pseudocode

```c
__int64 __fastcall renameParseSql(__int64 a1, __int64 a2, __int64 a3, _BYTE *a4, int a5)
{
  unsigned int v10; // ebx
  char DbName; // al
  unsigned int v12; // eax

  sqlite3ParseObjectInit(a1, a3);
  if ( !a4 )
    return 7;
  v10 = 7;
  if ( (unsigned int)sqlite3_strnicmp(a4, "CREATE ", 7) )
    return sqlite3ReportError(11, 117284, "database corruption");
  if ( a5 )
    DbName = 1;
  else
    DbName = sqlite3FindDbName(a3, a2);
  *(_BYTE *)(a3 + 196) = DbName;
  *(_BYTE *)(a1 + 308) = 2;
  *(_QWORD *)a1 = a3;
  *(_WORD *)(a1 + 224) = 1;
  v12 = sqlite3RunParser((__int64 *)a1, a4);
  if ( !*(_BYTE *)(a3 + 103) )
  {
    v10 = v12;
    if ( !v12 && !*(_QWORD *)(a1 + 352) && !*(_QWORD *)(a1 + 360) && !*(_QWORD *)(a1 + 368) )
      v10 = sqlite3ReportError(11, 117295, "database corruption");
  }
  *(_BYTE *)(a3 + 196) = 0;
  return v10;
}

```

## disassembly

```asm
0x180073744  push    rbx
0x180073746  push    rbp
0x180073747  push    rsi
0x180073748  push    rdi
0x180073749  push    r12
0x18007374b  push    r14
0x18007374d  sub     rsp, 28h
0x180073751  mov     r14, rdx
0x180073754  mov     rbp, r9
0x180073757  mov     rdx, r8
0x18007375a  mov     rsi, r8
0x18007375d  mov     rdi, rcx
0x180073760  call    sqlite3ParseObjectInit
0x180073765  test    rbp, rbp
0x180073768  jnz     short loc_180073772
0x18007376a  lea     eax, [rbp+7]
0x18007376d  jmp     loc_180073832
0x180073772  mov     ebx, 7
0x180073777  lea     rdx, aCreate; "CREATE "
0x18007377e  mov     r8d, ebx
0x180073781  mov     rcx, rbp
0x180073784  call    sqlite3_strnicmp
0x180073789  test    eax, eax
0x18007378b  jz      short loc_1800737A6
0x18007378d  lea     r8, aDatabaseCorrup; "database corruption"
0x180073794  mov     edx, 1CA24h
0x180073799  lea     ecx, [rbx+4]
0x18007379c  call    sqlite3ReportError
0x1800737a1  jmp     loc_180073832
0x1800737a6  cmp     [rsp+58h+arg_20], 0
0x1800737ae  mov     r12d, 1
0x1800737b4  jz      short loc_1800737BB
0x1800737b6  mov     eax, r12d
0x1800737b9  jmp     short loc_1800737C6
0x1800737bb  mov     rdx, r14
0x1800737be  mov     rcx, rsi
0x1800737c1  call    sqlite3FindDbName
0x1800737c6  mov     [rsi+0C4h], al
0x1800737cc  mov     rdx, rbp
0x1800737cf  mov     rcx, rdi
0x1800737d2  mov     byte ptr [rdi+134h], 2
0x1800737d9  mov     [rdi], rsi
0x1800737dc  mov     [rdi+0E0h], r12w
0x1800737e4  call    sqlite3RunParser
0x1800737e9  cmp     byte ptr [rsi+67h], 0
0x1800737ed  jnz     short loc_180073829
0x1800737ef  mov     ebx, eax
0x1800737f1  test    eax, eax
0x1800737f3  jnz     short loc_180073829
0x1800737f5  cmp     qword ptr [rdi+160h], 0
0x1800737fd  jnz     short loc_180073829
0x1800737ff  cmp     qword ptr [rdi+168h], 0
0x180073807  jnz     short loc_180073829
0x180073809  cmp     qword ptr [rdi+170h], 0
0x180073811  jnz     short loc_180073829
0x180073813  lea     r8, aDatabaseCorrup; "database corruption"
0x18007381a  mov     edx, 1CA2Fh
0x18007381f  lea     ecx, [rax+0Bh]
0x180073822  call    sqlite3ReportError
0x180073827  mov     ebx, eax
0x180073829  mov     byte ptr [rsi+0C4h], 0
0x180073830  mov     eax, ebx
0x180073832  add     rsp, 28h
0x180073836  pop     r14
0x180073838  pop     r12
0x18007383a  pop     rdi
0x18007383b  pop     rsi
0x18007383c  pop     rbp
0x18007383d  pop     rbx
0x18007383e  retn
```
