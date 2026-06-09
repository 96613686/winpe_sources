# StateRepository::Database::dal_function_startswith(sqlite3_context *,int,sqlite3_value * *)

- ea: `0x1800a8920`
- end: `0x1800a8ab4`
- name: `?dal_function_startswith@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z`
- size: `404`
- prototype: `void __fastcall(struct sqlite3_context *, int, struct sqlite3_value **)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800094c0`
- `0x18000a0bc`
- `0x1800210d4`
- `0x1800a626c`
- `0x1800a8920`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800a8a77`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800a8a77`
- `winsqlite3!sqlite3_result_int64` at `0x1800a8a8b`
- `winsqlite3!sqlite3_result_int64` at `0x1800a8a8b`
- `winsqlite3!sqlite3_result_error_code` at `0x1800a8951`
- `winsqlite3!sqlite3_result_error_code` at `0x1800a8951`
- `winsqlite3!sqlite3_value_type` at `0x1800a895f`
- `winsqlite3!sqlite3_value_type` at `0x1800a89df`
- `winsqlite3!sqlite3_value_type` at `0x1800a895f`
- `winsqlite3!sqlite3_value_type` at `0x1800a89df`
- `winsqlite3!sqlite3_result_error` at `0x1800a89d0`
- `winsqlite3!sqlite3_result_error` at `0x1800a89d0`
- `winsqlite3!sqlite3_value_text16` at `0x1800a8a30`
- `winsqlite3!sqlite3_value_text16` at `0x1800a8a3d`
- `winsqlite3!sqlite3_value_text16` at `0x1800a8a30`
- `winsqlite3!sqlite3_value_text16` at `0x1800a8a3d`

## string_xrefs

- `0x1800a89b0`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`

## pseudocode

```c
void __fastcall StateRepository::Database::dal_function_startswith(
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
  const WCHAR *v13; // rbp
  __int64 v14; // rdx
  __int64 v15; // r8
  const WCHAR *v16; // r8
  unsigned __int64 v17; // rax
  unsigned __int64 v18; // rdx
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
      v7 = StringCchPrintfA(v21, 0x64u, "StartsWith(*string*,prefix) error: Invalid type (%d)", v6);
      if ( v7 < 0 )
      {
        v8 = 3437;
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
        v7 = StringCchPrintfA(v21, 0x64u, "StartsWith(string,*prefix*) error: Invalid type (%d)", v12);
        if ( v7 < 0 )
        {
          v8 = 3452;
          goto LABEL_7;
        }
        goto LABEL_8;
      }
      v13 = (const WCHAR *)sqlite3_value_text16(*a3, v10, v11);
      v16 = (const WCHAR *)sqlite3_value_text16(a3[1], v14, v15);
      v17 = -1;
      v18 = -1;
      do
        ++v18;
      while ( v16[v18] );
      do
        ++v17;
      while ( v13[v17] );
      if ( v18 > v17 || (v19 = 1, CompareStringOrdinal(v13, v18, v16, v18, 1) != 2) )
        v19 = 0;
      sqlite3_result_int64(a1, v19);
    }
  }
}

```

## disassembly

```asm
0x1800a8920  mov     [rsp+arg_8], rbx
0x1800a8925  push    rbp
0x1800a8926  push    rsi
0x1800a8927  push    rdi
0x1800a8928  sub     rsp, 0B0h
0x1800a892f  mov     rax, cs:__security_cookie
0x1800a8936  xor     rax, rsp
0x1800a8939  mov     [rsp+0C8h+var_28], rax
0x1800a8941  mov     rsi, r8
0x1800a8944  mov     rdi, rcx
0x1800a8947  cmp     edx, 2
0x1800a894a  jz      short loc_1800A895C
0x1800a894c  mov     edx, 15h
0x1800a8951  call    cs:__imp_sqlite3_result_error_code
0x1800a8957  jmp     loc_1800A8A91
0x1800a895c  mov     rcx, [r8]
0x1800a895f  call    cs:__imp_sqlite3_value_type
0x1800a8965  mov     ebx, eax
0x1800a8967  cmp     eax, 5
0x1800a896a  jz      loc_1800A8A91
0x1800a8970  cmp     eax, 3
0x1800a8973  jz      short loc_1800A89DB
0x1800a8975  mov     esi, 64h ; 'd'
0x1800a897a  lea     rcx, [rsp+0C8h+var_98]; void *
0x1800a897f  mov     r8d, esi; Size
0x1800a8982  xor     edx, edx; Val
0x1800a8984  call    memset_0
0x1800a8989  mov     r9d, ebx
0x1800a898c  lea     r8, aStartswithStri; "StartsWith(*string*,prefix) error: Inva"...
0x1800a8993  mov     edx, esi; unsigned __int64
0x1800a8995  lea     rcx, [rsp+0C8h+var_98]; char *
0x1800a899a  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800a899f  test    eax, eax
0x1800a89a1  jns     short loc_1800A89C4
0x1800a89a3  mov     edx, 0D6Dh; void *
0x1800a89a8  mov     rcx, [rsp+0C8h]; this
0x1800a89b0  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800a89b7  mov     r9d, eax; char *
0x1800a89ba  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800a89bf  jmp     loc_1800A8A91
0x1800a89c4  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800a89c8  lea     rdx, [rsp+0C8h+var_98]
0x1800a89cd  mov     rcx, rdi
0x1800a89d0  call    cs:__imp_sqlite3_result_error
0x1800a89d6  jmp     loc_1800A8A91
0x1800a89db  mov     rcx, [rsi+8]
0x1800a89df  call    cs:__imp_sqlite3_value_type
0x1800a89e5  mov     ebx, eax
0x1800a89e7  cmp     eax, 5
0x1800a89ea  jz      loc_1800A8A91
0x1800a89f0  cmp     eax, 3
0x1800a89f3  jz      short loc_1800A8A2D
0x1800a89f5  mov     esi, 64h ; 'd'
0x1800a89fa  lea     rcx, [rsp+0C8h+var_98]; void *
0x1800a89ff  mov     r8d, esi; Size
0x1800a8a02  xor     edx, edx; Val
0x1800a8a04  call    memset_0
0x1800a8a09  mov     r9d, ebx
0x1800a8a0c  lea     r8, aStartswithStri_0; "StartsWith(string,*prefix*) error: Inva"...
0x1800a8a13  mov     edx, esi; unsigned __int64
0x1800a8a15  lea     rcx, [rsp+0C8h+var_98]; char *
0x1800a8a1a  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800a8a1f  test    eax, eax
0x1800a8a21  jns     short loc_1800A89C4
0x1800a8a23  mov     edx, 0D7Ch
0x1800a8a28  jmp     loc_1800A89A8
0x1800a8a2d  mov     rcx, [rsi]
0x1800a8a30  call    cs:__imp_sqlite3_value_text16
0x1800a8a36  mov     rcx, [rsi+8]
0x1800a8a3a  mov     rbp, rax
0x1800a8a3d  call    cs:__imp_sqlite3_value_text16
0x1800a8a43  mov     r8, rax; lpString2
0x1800a8a46  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800a8a4a  mov     rdx, rax
0x1800a8a4d  xor     ebx, ebx
0x1800a8a4f  inc     rdx; cchCount1
0x1800a8a52  cmp     [r8+rdx*2], bx
0x1800a8a57  jnz     short loc_1800A8A4F
0x1800a8a59  inc     rax
0x1800a8a5c  cmp     [rbp+rax*2+0], bx
0x1800a8a61  jnz     short loc_1800A8A59
0x1800a8a63  cmp     rdx, rax
0x1800a8a66  ja      short loc_1800A8A82
0x1800a8a68  mov     esi, 1
0x1800a8a6d  mov     r9d, edx; cchCount2
0x1800a8a70  mov     rcx, rbp; lpString1
0x1800a8a73  mov     [rsp+0C8h+bIgnoreCase], esi; bIgnoreCase
0x1800a8a77  call    cs:__imp_CompareStringOrdinal
0x1800a8a7d  cmp     eax, 2
0x1800a8a80  jz      short loc_1800A8A85
0x1800a8a82  mov     rsi, rbx
0x1800a8a85  mov     rdx, rsi
0x1800a8a88  mov     rcx, rdi
0x1800a8a8b  call    cs:__imp_sqlite3_result_int64
0x1800a8a91  mov     rcx, [rsp+0C8h+var_28]
0x1800a8a99  xor     rcx, rsp; StackCookie
0x1800a8a9c  call    __security_check_cookie
0x1800a8aa1  mov     rbx, [rsp+0C8h+arg_8]
0x1800a8aa9  add     rsp, 0B0h
0x1800a8ab0  pop     rdi
0x1800a8ab1  pop     rsi
0x1800a8ab2  pop     rbp
0x1800a8ab3  retn
```
