# StateRepository::Database::dal_function_compare_uint(sqlite3_context *,int,sqlite3_value * *)

- ea: `0x1800fdb00`
- end: `0x1800fdc54`
- name: `?dal_function_compare_uint@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z`
- size: `340`
- prototype: `void __fastcall(struct sqlite3_context *, int, struct sqlite3_value **)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180003060`
- `0x180003a40`
- `0x18000a7f0`
- `0x18000aaf0`
- `0x18000c150`
- `0x18000c240`
- `0x18000d7c0`
- `0x1800f7630`
- `0x1800fc60c`
- `0x1800fdb00`

## string_xrefs

- `0x1800fdb8e`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1800fdb6a`: `Compare_UInt(left,right) error: Invalid type (left=%d)`
- `0x1800fdbec`: `Compare_UInt(left,right) error: Invalid type (right=%d)`

## pseudocode

```c
void __fastcall StateRepository::Database::dal_function_compare_uint(
        struct sqlite3_context *a1,
        int a2,
        struct sqlite3_value **a3)
{
  int v5; // eax
  int v6; // esi
  int v7; // eax
  __int64 v8; // rdx
  unsigned __int64 v9; // rbp
  int v10; // eax
  int v11; // esi
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // rdx
  char v14[112]; // [rsp+20h] [rbp-98h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  if ( a2 != 2 )
  {
    sqlite3_result_error_code(a1, 21);
    return;
  }
  v5 = sqlite3_value_type(*a3);
  v6 = v5;
  if ( v5 != 5 )
  {
    if ( v5 != 1 )
    {
      memset_0(v14, 0, 0x64u);
      v7 = StringCchPrintfA(v14, 0x64u, "Compare_UInt(left,right) error: Invalid type (left=%d)", v6);
      if ( v7 < 0 )
      {
        v8 = 3820;
LABEL_7:
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)v8,
          (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
          (const char *)(unsigned int)v7);
        return;
      }
LABEL_8:
      sqlite3_result_error(a1, v14, 0xFFFFFFFFLL);
      return;
    }
    v9 = sqlite3_value_int64(*a3);
    v10 = sqlite3_value_type(a3[1]);
    v11 = v10;
    if ( v10 != 5 )
    {
      if ( v10 != 1 )
      {
        memset_0(v14, 0, 0x64u);
        v7 = StringCchPrintfA(v14, 0x64u, "Compare_UInt(left,right) error: Invalid type (right=%d)", v11);
        if ( v7 < 0 )
        {
          v8 = 3836;
          goto LABEL_7;
        }
        goto LABEL_8;
      }
      v12 = sqlite3_value_int64(a3[1]);
      if ( v9 == v12 )
        v13 = 0;
      else
        v13 = (-(__int64)(v9 < v12) & 0xFFFFFFFFFFFFFFFEuLL) + 1;
      sqlite3_result_int64(a1, v13);
    }
  }
}

```

## disassembly

```asm
0x1800fdb00  mov     [rsp+arg_8], rbx
0x1800fdb05  push    rbp
0x1800fdb06  push    rsi
0x1800fdb07  push    rdi
0x1800fdb08  sub     rsp, 0A0h
0x1800fdb0f  mov     rax, cs:__security_cookie
0x1800fdb16  xor     rax, rsp
0x1800fdb19  mov     [rsp+0B8h+var_28], rax
0x1800fdb21  mov     rdi, r8
0x1800fdb24  mov     rbx, rcx
0x1800fdb27  cmp     edx, 2
0x1800fdb2a  jz      short loc_1800FDB3B
0x1800fdb2c  mov     edx, 15h
0x1800fdb31  call    sqlite3_result_error_code
0x1800fdb36  jmp     loc_1800FDC31
0x1800fdb3b  mov     rcx, [r8]
0x1800fdb3e  call    sqlite3_value_type
0x1800fdb43  mov     esi, eax
0x1800fdb45  cmp     eax, 5
0x1800fdb48  jz      loc_1800FDC31
0x1800fdb4e  cmp     eax, 1
0x1800fdb51  jz      short loc_1800FDBB5
0x1800fdb53  mov     edi, 64h ; 'd'
0x1800fdb58  lea     rcx, [rsp+0B8h+var_98]; void *
0x1800fdb5d  mov     r8d, edi; Size
0x1800fdb60  xor     edx, edx; Val
0x1800fdb62  call    memset_0
0x1800fdb67  mov     r9d, esi
0x1800fdb6a  lea     r8, aCompareUintLef_0; "Compare_UInt(left,right) error: Invalid"...
0x1800fdb71  mov     edx, edi; unsigned __int64
0x1800fdb73  lea     rcx, [rsp+0B8h+var_98]; char *
0x1800fdb78  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800fdb7d  test    eax, eax
0x1800fdb7f  jns     short loc_1800FDBA2
0x1800fdb81  mov     edx, 0EECh; void *
0x1800fdb86  mov     rcx, [rsp+0B8h]; this
0x1800fdb8e  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800fdb95  mov     r9d, eax; char *
0x1800fdb98  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800fdb9d  jmp     loc_1800FDC31
0x1800fdba2  or      r8d, 0FFFFFFFFh
0x1800fdba6  lea     rdx, [rsp+0B8h+var_98]
0x1800fdbab  mov     rcx, rbx
0x1800fdbae  call    sqlite3_result_error
0x1800fdbb3  jmp     short loc_1800FDC31
0x1800fdbb5  mov     rcx, [rdi]
0x1800fdbb8  call    sqlite3_value_int64
0x1800fdbbd  mov     rcx, [rdi+8]
0x1800fdbc1  mov     rbp, rax
0x1800fdbc4  call    sqlite3_value_type
0x1800fdbc9  mov     esi, eax
0x1800fdbcb  cmp     eax, 5
0x1800fdbce  jz      short loc_1800FDC31
0x1800fdbd0  cmp     eax, 1
0x1800fdbd3  jz      short loc_1800FDC0D
0x1800fdbd5  mov     edi, 64h ; 'd'
0x1800fdbda  lea     rcx, [rsp+0B8h+var_98]; void *
0x1800fdbdf  mov     r8d, edi; Size
0x1800fdbe2  xor     edx, edx; Val
0x1800fdbe4  call    memset_0
0x1800fdbe9  mov     r9d, esi
0x1800fdbec  lea     r8, aCompareUintLef; "Compare_UInt(left,right) error: Invalid"...
0x1800fdbf3  mov     edx, edi; unsigned __int64
0x1800fdbf5  lea     rcx, [rsp+0B8h+var_98]; char *
0x1800fdbfa  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800fdbff  test    eax, eax
0x1800fdc01  jns     short loc_1800FDBA2
0x1800fdc03  mov     edx, 0EFCh
0x1800fdc08  jmp     loc_1800FDB86
0x1800fdc0d  mov     rcx, [rdi+8]
0x1800fdc11  call    sqlite3_value_int64
0x1800fdc16  cmp     rbp, rax
0x1800fdc19  jnz     short loc_1800FDC1F
0x1800fdc1b  xor     edx, edx
0x1800fdc1d  jmp     short loc_1800FDC29
0x1800fdc1f  sbb     rdx, rdx
0x1800fdc22  and     rdx, 0FFFFFFFFFFFFFFFEh
0x1800fdc26  inc     rdx
0x1800fdc29  mov     rcx, rbx
0x1800fdc2c  call    sqlite3_result_int64
0x1800fdc31  mov     rcx, [rsp+0B8h+var_28]
0x1800fdc39  xor     rcx, rsp; StackCookie
0x1800fdc3c  call    __security_check_cookie
0x1800fdc41  mov     rbx, [rsp+0B8h+arg_8]
0x1800fdc49  add     rsp, 0A0h
0x1800fdc50  pop     rdi
0x1800fdc51  pop     rsi
0x1800fdc52  pop     rbp
0x1800fdc53  retn
```
