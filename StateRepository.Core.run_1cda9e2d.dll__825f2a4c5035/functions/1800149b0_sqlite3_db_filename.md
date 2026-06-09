# sqlite3_db_filename

- ea: `0x1800149b0`
- end: `0x180014ae9`
- name: `sqlite3_db_filename`
- size: `313`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800143f0`
- `0x1800149b0`
- `0x180014b90`
- `0x1800275f0`
- `0x18004d3f8`
- `0x180060134`

## string_xrefs

- `0x180014ab4`: `unopened`

## pseudocode

```c
void *__fastcall sqlite3_db_filename(__int64 a1, __int64 a2)
{
  int v4; // esi
  __int64 v5; // rax
  __int64 *v6; // rax
  __int64 v7; // rcx
  _QWORD *i; // r14
  const char *v10; // r8

  if ( !a1 )
  {
    v10 = "NULL";
    goto LABEL_22;
  }
  if ( *(_BYTE *)(a1 + 113) != 118 )
  {
    if ( !(unsigned int)sqlite3SafetyCheckSickOrOk() )
    {
LABEL_23:
      sqlite3ReportError(21, 185983, "misuse");
      return 0;
    }
    v10 = "unopened";
LABEL_22:
    sqlite3_log(21, "API call with %s database connection pointer", v10);
    goto LABEL_23;
  }
  if ( a2 )
  {
    v4 = *(_DWORD *)(a1 + 40) - 1;
    for ( i = (_QWORD *)(*(_QWORD *)(a1 + 32) + 32LL * v4); v4 >= 0; --v4 )
    {
      if ( !(unsigned int)sqlite3_stricmp(*i, a2) || !v4 && !(unsigned int)sqlite3StrICmp("main", a2) )
        break;
      i -= 4;
    }
    if ( v4 < 0 )
      return 0;
  }
  else
  {
    v4 = 0;
  }
  _mm_lfence();
  v5 = *(_QWORD *)(32LL * (unsigned int)v4 + *(_QWORD *)(a1 + 32) + 8);
  if ( !v5 )
    return 0;
  v6 = *(__int64 **)(v5 + 8);
  v7 = *v6;
  if ( *(_BYTE *)(*v6 + 19) || *(_UNKNOWN **)v7 == &unk_1800B2000 )
    return &unk_18009E87C;
  else
    return *(void **)(v7 + 216);
}

```

## disassembly

```asm
0x1800149b0  mov     [rsp+arg_10], rbx
0x1800149b5  push    rdi
0x1800149b6  sub     rsp, 20h
0x1800149ba  mov     rdi, rdx
0x1800149bd  mov     rbx, rcx
0x1800149c0  test    rcx, rcx
0x1800149c3  jz      loc_180014AA2
0x1800149c9  cmp     byte ptr [rcx+71h], 76h ; 'v'
0x1800149cd  jnz     loc_180014AAB
0x1800149d3  mov     [rsp+28h+arg_0], rsi
0x1800149d8  test    rdx, rdx
0x1800149db  jnz     short loc_180014A41
0x1800149dd  xor     esi, esi
0x1800149df  lfence
0x1800149e2  mov     rax, [rbx+20h]
0x1800149e6  mov     ecx, esi
0x1800149e8  shl     rcx, 5
0x1800149ec  mov     rax, [rcx+rax+8]
0x1800149f1  test    rax, rax
0x1800149f4  jz      loc_180014A89
0x1800149fa  mov     rax, [rax+8]
0x1800149fe  mov     rcx, [rax]
0x180014a01  cmp     byte ptr [rcx+13h], 0
0x180014a05  jz      short loc_180014A1E
0x180014a07  lea     rax, unk_18009E87C
0x180014a0e  mov     rsi, [rsp+28h+arg_0]
0x180014a13  mov     rbx, [rsp+28h+arg_10]
0x180014a18  add     rsp, 20h
0x180014a1c  pop     rdi
0x180014a1d  retn
0x180014a1e  lea     rax, unk_1800B2000
0x180014a25  cmp     [rcx], rax
0x180014a28  jz      short loc_180014A07
0x180014a2a  mov     rax, [rcx+0D8h]
0x180014a31  mov     rsi, [rsp+28h+arg_0]
0x180014a36  mov     rbx, [rsp+28h+arg_10]
0x180014a3b  add     rsp, 20h
0x180014a3f  pop     rdi
0x180014a40  retn
0x180014a41  mov     esi, [rcx+28h]
0x180014a44  mov     [rsp+28h+arg_8], r14
0x180014a49  dec     esi
0x180014a4b  movsxd  r14, esi
0x180014a4e  shl     r14, 5
0x180014a52  add     r14, [rcx+20h]
0x180014a56  test    esi, esi
0x180014a58  js      short loc_180014A7C
0x180014a5a  nop     word ptr [rax+rax+00h]
0x180014a60  mov     rcx, [r14]
0x180014a63  mov     rdx, rdi
0x180014a66  call    sqlite3_stricmp
0x180014a6b  test    eax, eax
0x180014a6d  jz      short loc_180014A7C
0x180014a6f  test    esi, esi
0x180014a71  jz      short loc_180014A8D
0x180014a73  sub     r14, 20h ; ' '
0x180014a77  sub     esi, 1
0x180014a7a  jns     short loc_180014A60
0x180014a7c  mov     r14, [rsp+28h+arg_8]
0x180014a81  test    esi, esi
0x180014a83  jns     loc_1800149DF
0x180014a89  xor     eax, eax
0x180014a8b  jmp     short loc_180014A0E
0x180014a8d  mov     rdx, rdi
0x180014a90  lea     rcx, aMain; "main"
0x180014a97  call    sqlite3StrICmp
0x180014a9c  test    eax, eax
0x180014a9e  jz      short loc_180014A7C
0x180014aa0  jmp     short loc_180014A73
0x180014aa2  lea     r8, aNull_1; "NULL"
0x180014aa9  jmp     short loc_180014ABB
0x180014aab  call    sqlite3SafetyCheckSickOrOk
0x180014ab0  test    eax, eax
0x180014ab2  jz      short loc_180014ACC
0x180014ab4  lea     r8, aUnopened; "unopened"
0x180014abb  lea     rdx, aApiCallWithSDa; "API call with %s database connection po"...
0x180014ac2  mov     ecx, 15h
0x180014ac7  call    sqlite3_log
0x180014acc  lea     r8, aMisuse; "misuse"
0x180014ad3  mov     edx, 2D67Fh
0x180014ad8  mov     ecx, 15h
0x180014add  call    sqlite3ReportError
0x180014ae2  xor     eax, eax
0x180014ae4  jmp     loc_180014A13
```
