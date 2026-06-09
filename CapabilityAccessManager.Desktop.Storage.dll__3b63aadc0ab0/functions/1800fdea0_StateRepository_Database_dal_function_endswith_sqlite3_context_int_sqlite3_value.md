# StateRepository::Database::dal_function_endswith(sqlite3_context *,int,sqlite3_value * *)

- ea: `0x1800fdea0`
- end: `0x1800fe02f`
- name: `?dal_function_endswith@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z`
- size: `399`
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
- `0x1800fdea0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800fdff2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800fdff2`

## string_xrefs

- `0x1800fdf2f`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`

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
  int v10; // ebx
  __int64 v11; // r14
  const WCHAR *v12; // rax
  unsigned __int64 v13; // rdx
  unsigned __int64 v14; // rcx
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
      v7 = StringCchPrintfA(v16, 0x64u, "EndsWith(*string*,suffix) error: Invalid type (%d)", v6);
      if ( v7 < 0 )
      {
        v8 = 3489;
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
        v7 = StringCchPrintfA(v16, 0x64u, "EndsWith(string,*suffix*) error: Invalid type (%d)", v10);
        if ( v7 < 0 )
        {
          v8 = 3504;
          goto LABEL_7;
        }
        goto LABEL_8;
      }
      v11 = sqlite3_value_text16le(*a3);
      v12 = (const WCHAR *)sqlite3_value_text16le(a3[1]);
      v13 = -1;
      v14 = -1;
      do
        ++v14;
      while ( *(_WORD *)(v11 + 2 * v14) );
      do
        ++v13;
      while ( v12[v13] );
      if ( v13 > v14 || (v15 = 1, CompareStringOrdinal((LPCWCH)(v11 + 2 * (v14 - v13)), v13, v12, v13, 1) != 2) )
        v15 = 0;
      sqlite3_result_int64(a1, v15);
    }
  }
}

```

## disassembly

```asm
0x1800fdea0  mov     [rsp+arg_8], rbx
0x1800fdea5  push    rsi
0x1800fdea6  push    rdi
0x1800fdea7  push    r14
0x1800fdea9  sub     rsp, 0B0h
0x1800fdeb0  mov     rax, cs:__security_cookie
0x1800fdeb7  xor     rax, rsp
0x1800fdeba  mov     [rsp+0C8h+var_28], rax
0x1800fdec2  mov     rsi, r8
0x1800fdec5  mov     rdi, rcx
0x1800fdec8  cmp     edx, 2
0x1800fdecb  jz      short loc_1800FDEDC
0x1800fdecd  mov     edx, 15h
0x1800fded2  call    sqlite3_result_error_code
0x1800fded7  jmp     loc_1800FE00B
0x1800fdedc  mov     rcx, [r8]
0x1800fdedf  call    sqlite3_value_type
0x1800fdee4  mov     ebx, eax
0x1800fdee6  cmp     eax, 5
0x1800fdee9  jz      loc_1800FE00B
0x1800fdeef  cmp     eax, 3
0x1800fdef2  jz      short loc_1800FDF59
0x1800fdef4  mov     esi, 64h ; 'd'
0x1800fdef9  lea     rcx, [rsp+0C8h+var_98]; void *
0x1800fdefe  mov     r8d, esi; Size
0x1800fdf01  xor     edx, edx; Val
0x1800fdf03  call    memset_0
0x1800fdf08  mov     r9d, ebx
0x1800fdf0b  lea     r8, aEndswithString_0; "EndsWith(*string*,suffix) error: Invali"...
0x1800fdf12  mov     edx, esi; unsigned __int64
0x1800fdf14  lea     rcx, [rsp+0C8h+var_98]; char *
0x1800fdf19  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800fdf1e  test    eax, eax
0x1800fdf20  jns     short loc_1800FDF43
0x1800fdf22  mov     edx, 0DA1h; void *
0x1800fdf27  mov     rcx, [rsp+0C8h]; this
0x1800fdf2f  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800fdf36  mov     r9d, eax; char *
0x1800fdf39  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800fdf3e  jmp     loc_1800FE00B
0x1800fdf43  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800fdf47  lea     rdx, [rsp+0C8h+var_98]
0x1800fdf4c  mov     rcx, rdi
0x1800fdf4f  call    sqlite3_result_error
0x1800fdf54  jmp     loc_1800FE00B
0x1800fdf59  mov     rcx, [rsi+8]
0x1800fdf5d  call    sqlite3_value_type
0x1800fdf62  mov     ebx, eax
0x1800fdf64  cmp     eax, 5
0x1800fdf67  jz      loc_1800FE00B
0x1800fdf6d  cmp     eax, 3
0x1800fdf70  jz      short loc_1800FDFA7
0x1800fdf72  mov     esi, 64h ; 'd'
0x1800fdf77  lea     rcx, [rsp+0C8h+var_98]; void *
0x1800fdf7c  mov     r8d, esi; Size
0x1800fdf7f  xor     edx, edx; Val
0x1800fdf81  call    memset_0
0x1800fdf86  mov     r9d, ebx
0x1800fdf89  lea     r8, aEndswithString; "EndsWith(string,*suffix*) error: Invali"...
0x1800fdf90  mov     edx, esi; unsigned __int64
0x1800fdf92  lea     rcx, [rsp+0C8h+var_98]; char *
0x1800fdf97  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800fdf9c  test    eax, eax
0x1800fdf9e  jns     short loc_1800FDF43
0x1800fdfa0  mov     edx, 0DB0h
0x1800fdfa5  jmp     short loc_1800FDF27
0x1800fdfa7  mov     rcx, [rsi]
0x1800fdfaa  call    sqlite3_value_text16le
0x1800fdfaf  mov     rcx, [rsi+8]
0x1800fdfb3  mov     r14, rax
0x1800fdfb6  call    sqlite3_value_text16le
0x1800fdfbb  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800fdfbf  mov     rcx, rdx
0x1800fdfc2  xor     ebx, ebx
0x1800fdfc4  inc     rcx
0x1800fdfc7  cmp     [r14+rcx*2], bx
0x1800fdfcc  jnz     short loc_1800FDFC4
0x1800fdfce  inc     rdx; cchCount1
0x1800fdfd1  cmp     [rax+rdx*2], bx
0x1800fdfd5  jnz     short loc_1800FDFCE
0x1800fdfd7  cmp     rdx, rcx
0x1800fdfda  ja      short loc_1800FDFFD
0x1800fdfdc  sub     rcx, rdx
0x1800fdfdf  mov     esi, 1
0x1800fdfe4  mov     r9d, edx; cchCount2
0x1800fdfe7  mov     [rsp+0C8h+bIgnoreCase], esi; bIgnoreCase
0x1800fdfeb  mov     r8, rax; lpString2
0x1800fdfee  lea     rcx, [r14+rcx*2]; lpString1
0x1800fdff2  call    cs:__imp_CompareStringOrdinal
0x1800fdff8  cmp     eax, 2
0x1800fdffb  jz      short loc_1800FE000
0x1800fdffd  mov     rsi, rbx
0x1800fe000  mov     rdx, rsi
0x1800fe003  mov     rcx, rdi
0x1800fe006  call    sqlite3_result_int64
0x1800fe00b  mov     rcx, [rsp+0C8h+var_28]
0x1800fe013  xor     rcx, rsp; StackCookie
0x1800fe016  call    __security_check_cookie
0x1800fe01b  mov     rbx, [rsp+0C8h+arg_8]
0x1800fe023  add     rsp, 0B0h
0x1800fe02a  pop     r14
0x1800fe02c  pop     rdi
0x1800fe02d  pop     rsi
0x1800fe02e  retn
```
