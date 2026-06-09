# StateRepository::Database::dal_function_endswith(sqlite3_context *,int,sqlite3_value * *)

- ea: `0x1800a7810`
- end: `0x1800a79a9`
- name: `?dal_function_endswith@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z`
- size: `409`
- prototype: `void __fastcall(struct sqlite3_context *, int, struct sqlite3_value **)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800094c0`
- `0x18000a0bc`
- `0x1800210d4`
- `0x1800a626c`
- `0x1800a7810`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800a796b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800a796b`
- `winsqlite3!sqlite3_result_int64` at `0x1800a797f`
- `winsqlite3!sqlite3_result_int64` at `0x1800a797f`
- `winsqlite3!sqlite3_result_error_code` at `0x1800a7842`
- `winsqlite3!sqlite3_result_error_code` at `0x1800a7842`
- `winsqlite3!sqlite3_value_type` at `0x1800a7850`
- `winsqlite3!sqlite3_value_type` at `0x1800a78d0`
- `winsqlite3!sqlite3_value_type` at `0x1800a7850`
- `winsqlite3!sqlite3_value_type` at `0x1800a78d0`
- `winsqlite3!sqlite3_result_error` at `0x1800a78c1`
- `winsqlite3!sqlite3_result_error` at `0x1800a78c1`
- `winsqlite3!sqlite3_value_text16` at `0x1800a7921`
- `winsqlite3!sqlite3_value_text16` at `0x1800a792e`
- `winsqlite3!sqlite3_value_text16` at `0x1800a7921`
- `winsqlite3!sqlite3_value_text16` at `0x1800a792e`

## string_xrefs

- `0x1800a78a1`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`

## pseudocode

```c
void __fastcall StateRepository::Database::dal_function_endswith(
        struct sqlite3_context *a1,
        int a2,
        struct sqlite3_value **a3)
{
  int v5; // eax
  int v6; // ebx
  int v7; // eax
  __int64 v8; // rdx
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  int v12; // ebx
  __int64 v13; // r14
  __int64 v14; // rdx
  __int64 v15; // r8
  const WCHAR *v16; // rax
  unsigned __int64 v17; // rdx
  unsigned __int64 v18; // rcx
  __int64 v19; // rsi
  BOOL bIgnoreCase; // [rsp+20h] [rbp-A8h]
  char v21[112]; // [rsp+30h] [rbp-98h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  if ( a2 != 2 )
  {
    sqlite3_result_error_code(a1, 21);
    return;
  }
  v5 = sqlite3_value_type(*a3);
  v6 = v5;
  if ( v5 != 5 )
  {
    if ( v5 != 3 )
    {
      memset_0(v21, 0, 0x64u);
      v7 = StringCchPrintfA(v21, 0x64u, "EndsWith(*string*,suffix) error: Invalid type (%d)", v6);
      if ( v7 < 0 )
      {
        v8 = 3489;
LABEL_7:
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)v8,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
          (const char *)(unsigned int)v7,
          bIgnoreCase);
        return;
      }
LABEL_8:
      sqlite3_result_error(a1, v21, -1);
      return;
    }
    v9 = sqlite3_value_type(a3[1]);
    v12 = v9;
    if ( v9 != 5 )
    {
      if ( v9 != 3 )
      {
        memset_0(v21, 0, 0x64u);
        v7 = StringCchPrintfA(v21, 0x64u, "EndsWith(string,*suffix*) error: Invalid type (%d)", v12);
        if ( v7 < 0 )
        {
          v8 = 3504;
          goto LABEL_7;
        }
        goto LABEL_8;
      }
      v13 = sqlite3_value_text16(*a3, v10, v11);
      v16 = (const WCHAR *)sqlite3_value_text16(a3[1], v14, v15);
      v17 = -1;
      v18 = -1;
      do
        ++v18;
      while ( *(_WORD *)(v13 + 2 * v18) );
      do
        ++v17;
      while ( v16[v17] );
      if ( v17 > v18 || (v19 = 1, CompareStringOrdinal((LPCWCH)(v13 + 2 * (v18 - v17)), v17, v16, v17, 1) != 2) )
        v19 = 0;
      sqlite3_result_int64(a1, v19);
    }
  }
}

```

## disassembly

```asm
0x1800a7810  mov     [rsp+arg_8], rbx
0x1800a7815  push    rsi
0x1800a7816  push    rdi
0x1800a7817  push    r14
0x1800a7819  sub     rsp, 0B0h
0x1800a7820  mov     rax, cs:__security_cookie
0x1800a7827  xor     rax, rsp
0x1800a782a  mov     [rsp+0C8h+var_28], rax
0x1800a7832  mov     rsi, r8
0x1800a7835  mov     rdi, rcx
0x1800a7838  cmp     edx, 2
0x1800a783b  jz      short loc_1800A784D
0x1800a783d  mov     edx, 15h
0x1800a7842  call    cs:__imp_sqlite3_result_error_code
0x1800a7848  jmp     loc_1800A7985
0x1800a784d  mov     rcx, [r8]
0x1800a7850  call    cs:__imp_sqlite3_value_type
0x1800a7856  mov     ebx, eax
0x1800a7858  cmp     eax, 5
0x1800a785b  jz      loc_1800A7985
0x1800a7861  cmp     eax, 3
0x1800a7864  jz      short loc_1800A78CC
0x1800a7866  mov     esi, 64h ; 'd'
0x1800a786b  lea     rcx, [rsp+0C8h+var_98]; void *
0x1800a7870  mov     r8d, esi; Size
0x1800a7873  xor     edx, edx; Val
0x1800a7875  call    memset_0
0x1800a787a  mov     r9d, ebx
0x1800a787d  lea     r8, aEndswithString_0; "EndsWith(*string*,suffix) error: Invali"...
0x1800a7884  mov     edx, esi; unsigned __int64
0x1800a7886  lea     rcx, [rsp+0C8h+var_98]; char *
0x1800a788b  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800a7890  test    eax, eax
0x1800a7892  jns     short loc_1800A78B5
0x1800a7894  mov     edx, 0DA1h; void *
0x1800a7899  mov     rcx, [rsp+0C8h]; this
0x1800a78a1  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800a78a8  mov     r9d, eax; char *
0x1800a78ab  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800a78b0  jmp     loc_1800A7985
0x1800a78b5  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800a78b9  lea     rdx, [rsp+0C8h+var_98]
0x1800a78be  mov     rcx, rdi
0x1800a78c1  call    cs:__imp_sqlite3_result_error
0x1800a78c7  jmp     loc_1800A7985
0x1800a78cc  mov     rcx, [rsi+8]
0x1800a78d0  call    cs:__imp_sqlite3_value_type
0x1800a78d6  mov     ebx, eax
0x1800a78d8  cmp     eax, 5
0x1800a78db  jz      loc_1800A7985
0x1800a78e1  cmp     eax, 3
0x1800a78e4  jz      short loc_1800A791E
0x1800a78e6  mov     esi, 64h ; 'd'
0x1800a78eb  lea     rcx, [rsp+0C8h+var_98]; void *
0x1800a78f0  mov     r8d, esi; Size
0x1800a78f3  xor     edx, edx; Val
0x1800a78f5  call    memset_0
0x1800a78fa  mov     r9d, ebx
0x1800a78fd  lea     r8, aEndswithString; "EndsWith(string,*suffix*) error: Invali"...
0x1800a7904  mov     edx, esi; unsigned __int64
0x1800a7906  lea     rcx, [rsp+0C8h+var_98]; char *
0x1800a790b  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800a7910  test    eax, eax
0x1800a7912  jns     short loc_1800A78B5
0x1800a7914  mov     edx, 0DB0h
0x1800a7919  jmp     loc_1800A7899
0x1800a791e  mov     rcx, [rsi]
0x1800a7921  call    cs:__imp_sqlite3_value_text16
0x1800a7927  mov     rcx, [rsi+8]
0x1800a792b  mov     r14, rax
0x1800a792e  call    cs:__imp_sqlite3_value_text16
0x1800a7934  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800a7938  mov     rcx, rdx
0x1800a793b  xor     ebx, ebx
0x1800a793d  inc     rcx
0x1800a7940  cmp     [r14+rcx*2], bx
0x1800a7945  jnz     short loc_1800A793D
0x1800a7947  inc     rdx; cchCount1
0x1800a794a  cmp     [rax+rdx*2], bx
0x1800a794e  jnz     short loc_1800A7947
0x1800a7950  cmp     rdx, rcx
0x1800a7953  ja      short loc_1800A7976
0x1800a7955  sub     rcx, rdx
0x1800a7958  mov     esi, 1
0x1800a795d  mov     r9d, edx; cchCount2
0x1800a7960  mov     [rsp+0C8h+bIgnoreCase], esi; bIgnoreCase
0x1800a7964  mov     r8, rax; lpString2
0x1800a7967  lea     rcx, [r14+rcx*2]; lpString1
0x1800a796b  call    cs:__imp_CompareStringOrdinal
0x1800a7971  cmp     eax, 2
0x1800a7974  jz      short loc_1800A7979
0x1800a7976  mov     rsi, rbx
0x1800a7979  mov     rdx, rsi
0x1800a797c  mov     rcx, rdi
0x1800a797f  call    cs:__imp_sqlite3_result_int64
0x1800a7985  mov     rcx, [rsp+0C8h+var_28]
0x1800a798d  xor     rcx, rsp; StackCookie
0x1800a7990  call    __security_check_cookie
0x1800a7995  mov     rbx, [rsp+0C8h+arg_8]
0x1800a799d  add     rsp, 0B0h
0x1800a79a4  pop     r14
0x1800a79a6  pop     rdi
0x1800a79a7  pop     rsi
0x1800a79a8  retn
```
