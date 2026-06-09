# StateRepository::Database::dal_function_startswith(sqlite3_context *,int,sqlite3_value * *)

- ea: `0x1800ff190`
- end: `0x1800ff31a`
- name: `?dal_function_startswith@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z`
- size: `394`
- prototype: `void __fastcall(struct sqlite3_context *, int, struct sqlite3_value **)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180003060`
- `0x180003a40`
- `0x18000a8e0`
- `0x18000aaf0`
- `0x18000c150`
- `0x18000c240`
- `0x18000d7c0`
- `0x1800f7630`
- `0x1800fc60c`
- `0x1800ff190`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800ff2de`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800ff2de`

## string_xrefs

- `0x1800ff21e`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`

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
  int v10; // ebx
  const WCHAR *v11; // rbp
  const WCHAR *v12; // r8
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // rdx
  __int64 v15; // rsi
  char v16[112]; // [rsp+30h] [rbp-98h] BYREF
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
      memset_0(v16, 0, 0x64u);
      v7 = StringCchPrintfA(v16, 0x64u, "StartsWith(*string*,prefix) error: Invalid type (%d)", v6);
      if ( v7 < 0 )
      {
        v8 = 3437;
LABEL_7:
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)v8,
          (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
          (const char *)(unsigned int)v7);
        return;
      }
LABEL_8:
      sqlite3_result_error(a1, v16, -1);
      return;
    }
    v9 = sqlite3_value_type(a3[1]);
    v10 = v9;
    if ( v9 != 5 )
    {
      if ( v9 != 3 )
      {
        memset_0(v16, 0, 0x64u);
        v7 = StringCchPrintfA(v16, 0x64u, "StartsWith(string,*prefix*) error: Invalid type (%d)", v10);
        if ( v7 < 0 )
        {
          v8 = 3452;
          goto LABEL_7;
        }
        goto LABEL_8;
      }
      v11 = (const WCHAR *)sqlite3_value_text16le(*a3);
      v12 = (const WCHAR *)sqlite3_value_text16le(a3[1]);
      v13 = -1;
      v14 = -1;
      do
        ++v14;
      while ( v12[v14] );
      do
        ++v13;
      while ( v11[v13] );
      if ( v14 > v13 || (v15 = 1, CompareStringOrdinal(v11, v14, v12, v14, 1) != 2) )
        v15 = 0;
      sqlite3_result_int64(a1, v15);
    }
  }
}

```

## disassembly

```asm
0x1800ff190  mov     [rsp+arg_8], rbx
0x1800ff195  push    rbp
0x1800ff196  push    rsi
0x1800ff197  push    rdi
0x1800ff198  sub     rsp, 0B0h
0x1800ff19f  mov     rax, cs:__security_cookie
0x1800ff1a6  xor     rax, rsp
0x1800ff1a9  mov     [rsp+0C8h+var_28], rax
0x1800ff1b1  mov     rsi, r8
0x1800ff1b4  mov     rdi, rcx
0x1800ff1b7  cmp     edx, 2
0x1800ff1ba  jz      short loc_1800FF1CB
0x1800ff1bc  mov     edx, 15h
0x1800ff1c1  call    sqlite3_result_error_code
0x1800ff1c6  jmp     loc_1800FF2F7
0x1800ff1cb  mov     rcx, [r8]
0x1800ff1ce  call    sqlite3_value_type
0x1800ff1d3  mov     ebx, eax
0x1800ff1d5  cmp     eax, 5
0x1800ff1d8  jz      loc_1800FF2F7
0x1800ff1de  cmp     eax, 3
0x1800ff1e1  jz      short loc_1800FF248
0x1800ff1e3  mov     esi, 64h ; 'd'
0x1800ff1e8  lea     rcx, [rsp+0C8h+var_98]; void *
0x1800ff1ed  mov     r8d, esi; Size
0x1800ff1f0  xor     edx, edx; Val
0x1800ff1f2  call    memset_0
0x1800ff1f7  mov     r9d, ebx
0x1800ff1fa  lea     r8, aStartswithStri; "StartsWith(*string*,prefix) error: Inva"...
0x1800ff201  mov     edx, esi; unsigned __int64
0x1800ff203  lea     rcx, [rsp+0C8h+var_98]; char *
0x1800ff208  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800ff20d  test    eax, eax
0x1800ff20f  jns     short loc_1800FF232
0x1800ff211  mov     edx, 0D6Dh; void *
0x1800ff216  mov     rcx, [rsp+0C8h]; this
0x1800ff21e  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800ff225  mov     r9d, eax; char *
0x1800ff228  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800ff22d  jmp     loc_1800FF2F7
0x1800ff232  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800ff236  lea     rdx, [rsp+0C8h+var_98]
0x1800ff23b  mov     rcx, rdi
0x1800ff23e  call    sqlite3_result_error
0x1800ff243  jmp     loc_1800FF2F7
0x1800ff248  mov     rcx, [rsi+8]
0x1800ff24c  call    sqlite3_value_type
0x1800ff251  mov     ebx, eax
0x1800ff253  cmp     eax, 5
0x1800ff256  jz      loc_1800FF2F7
0x1800ff25c  cmp     eax, 3
0x1800ff25f  jz      short loc_1800FF296
0x1800ff261  mov     esi, 64h ; 'd'
0x1800ff266  lea     rcx, [rsp+0C8h+var_98]; void *
0x1800ff26b  mov     r8d, esi; Size
0x1800ff26e  xor     edx, edx; Val
0x1800ff270  call    memset_0
0x1800ff275  mov     r9d, ebx
0x1800ff278  lea     r8, aStartswithStri_0; "StartsWith(string,*prefix*) error: Inva"...
0x1800ff27f  mov     edx, esi; unsigned __int64
0x1800ff281  lea     rcx, [rsp+0C8h+var_98]; char *
0x1800ff286  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800ff28b  test    eax, eax
0x1800ff28d  jns     short loc_1800FF232
0x1800ff28f  mov     edx, 0D7Ch
0x1800ff294  jmp     short loc_1800FF216
0x1800ff296  mov     rcx, [rsi]
0x1800ff299  call    sqlite3_value_text16le
0x1800ff29e  mov     rcx, [rsi+8]
0x1800ff2a2  mov     rbp, rax
0x1800ff2a5  call    sqlite3_value_text16le
0x1800ff2aa  mov     r8, rax; lpString2
0x1800ff2ad  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800ff2b1  mov     rdx, rax
0x1800ff2b4  xor     ebx, ebx
0x1800ff2b6  inc     rdx; cchCount1
0x1800ff2b9  cmp     [r8+rdx*2], bx
0x1800ff2be  jnz     short loc_1800FF2B6
0x1800ff2c0  inc     rax
0x1800ff2c3  cmp     [rbp+rax*2+0], bx
0x1800ff2c8  jnz     short loc_1800FF2C0
0x1800ff2ca  cmp     rdx, rax
0x1800ff2cd  ja      short loc_1800FF2E9
0x1800ff2cf  mov     esi, 1
0x1800ff2d4  mov     r9d, edx; cchCount2
0x1800ff2d7  mov     rcx, rbp; lpString1
0x1800ff2da  mov     [rsp+0C8h+bIgnoreCase], esi; bIgnoreCase
0x1800ff2de  call    cs:__imp_CompareStringOrdinal
0x1800ff2e4  cmp     eax, 2
0x1800ff2e7  jz      short loc_1800FF2EC
0x1800ff2e9  mov     rsi, rbx
0x1800ff2ec  mov     rdx, rsi
0x1800ff2ef  mov     rcx, rdi
0x1800ff2f2  call    sqlite3_result_int64
0x1800ff2f7  mov     rcx, [rsp+0C8h+var_28]
0x1800ff2ff  xor     rcx, rsp; StackCookie
0x1800ff302  call    __security_check_cookie
0x1800ff307  mov     rbx, [rsp+0C8h+arg_8]
0x1800ff30f  add     rsp, 0B0h
0x1800ff316  pop     rdi
0x1800ff317  pop     rsi
0x1800ff318  pop     rbp
0x1800ff319  retn
```
