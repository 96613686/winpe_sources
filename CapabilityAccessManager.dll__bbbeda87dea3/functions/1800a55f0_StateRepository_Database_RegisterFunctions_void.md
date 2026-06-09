# StateRepository::Database::RegisterFunctions(void)

- ea: `0x1800a55f0`
- end: `0x1800a5b73`
- name: `?RegisterFunctions@Database@StateRepository@@QEAAJXZ`
- size: `1411`
- prototype: `__int64 __fastcall(StateRepository::Database *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800a4e00`
- `0x1800af620`

## callees

- `0x18001ab9c`
- `0x1800a55f0`

## import_xrefs

- `winsqlite3!sqlite3_create_function_v2` at `0x1800a565f`
- `winsqlite3!sqlite3_create_function_v2` at `0x1800a56ac`
- `winsqlite3!sqlite3_create_function_v2` at `0x1800a56e9`
- `winsqlite3!sqlite3_create_function_v2` at `0x1800a5727`
- `winsqlite3!sqlite3_create_function_v2` at `0x1800a5770`
- `winsqlite3!sqlite3_create_function_v2` at `0x1800a57ae`
- `winsqlite3!sqlite3_create_function_v2` at `0x1800a57ee`
- `winsqlite3!sqlite3_create_function_v2` at `0x1800a582e`
- `winsqlite3!sqlite3_create_function_v2` at `0x1800a586d`
- `winsqlite3!sqlite3_create_function_v2` at `0x1800a58ac`
- `winsqlite3!sqlite3_create_function_v2` at `0x1800a58f0`
- `winsqlite3!sqlite3_create_function_v2` at `0x1800a592e`
- `winsqlite3!sqlite3_create_function_v2` at `0x1800a596c`
- `winsqlite3!sqlite3_create_function_v2` at `0x1800a59aa`
- `winsqlite3!sqlite3_create_function_v2` at `0x1800a59e8`
- `winsqlite3!sqlite3_create_function_v2` at `0x1800a5a2a`
- `winsqlite3!sqlite3_create_function_v2` at `0x1800a5a5d`
- `winsqlite3!sqlite3_create_function_v2` at `0x1800a5aa1`
- `winsqlite3!sqlite3_create_function_v2` at `0x1800a5ae3`
- `winsqlite3!sqlite3_create_function_v2` at `0x1800a5b16`
- `winsqlite3!sqlite3_create_function_v2` at `0x1800a5b5a`
- `winsqlite3!sqlite3_create_function_v2` at `0x1800a565f`
- `winsqlite3!sqlite3_create_function_v2` at `0x1800a56ac`
- `winsqlite3!sqlite3_create_function_v2` at `0x1800a56e9`
- `winsqlite3!sqlite3_create_function_v2` at `0x1800a5727`
- `winsqlite3!sqlite3_create_function_v2` at `0x1800a5770`
- `winsqlite3!sqlite3_create_function_v2` at `0x1800a57ae`
- `winsqlite3!sqlite3_create_function_v2` at `0x1800a57ee`
- `winsqlite3!sqlite3_create_function_v2` at `0x1800a582e`
- `winsqlite3!sqlite3_create_function_v2` at `0x1800a586d`
- `winsqlite3!sqlite3_create_function_v2` at `0x1800a58ac`
- `winsqlite3!sqlite3_create_function_v2` at `0x1800a58f0`
- `winsqlite3!sqlite3_create_function_v2` at `0x1800a592e`
- `winsqlite3!sqlite3_create_function_v2` at `0x1800a596c`
- `winsqlite3!sqlite3_create_function_v2` at `0x1800a59aa`
- `winsqlite3!sqlite3_create_function_v2` at `0x1800a59e8`
- `winsqlite3!sqlite3_create_function_v2` at `0x1800a5a2a`
- `winsqlite3!sqlite3_create_function_v2` at `0x1800a5a5d`
- `winsqlite3!sqlite3_create_function_v2` at `0x1800a5aa1`
- `winsqlite3!sqlite3_create_function_v2` at `0x1800a5ae3`
- `winsqlite3!sqlite3_create_function_v2` at `0x1800a5b16`
- `winsqlite3!sqlite3_create_function_v2` at `0x1800a5b5a`

## string_xrefs

- `0x1800a560d`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1800a57d4`: `compress`
- `0x1800a58c9`: `compare_uint`
- `0x1800a581d`: `uncompress`

## pseudocode

```c
__int64 __fastcall StateRepository::Database::RegisterFunctions(StateRepository::Database *this)
{
  __int64 v2; // rcx
  __int64 result; // rax
  bool v4; // cc
  int v5; // [rsp+20h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v2 = *(_QWORD *)this;
  if ( v2 )
  {
    result = sqlite3_create_function_v2(
               v2,
               "execution_flags",
               0,
               2099205,
               this,
               StateRepository::Database::dal_function_execution_flags,
               0,
               0,
               0);
    v4 = (int)result <= 0;
    if ( (_DWORD)result )
      goto LABEL_4;
    result = sqlite3_create_function_v2(
               *(_QWORD *)this,
               "is_triggers_enabled",
               0,
               2099205,
               this,
               StateRepository::Database::dal_function_is_triggers_enabled,
               0,
               0,
               0);
    v4 = (int)result <= 0;
    if ( (_DWORD)result )
      goto LABEL_4;
    result = sqlite3_create_function_v2(
               *(_QWORD *)this,
               "now",
               0,
               2097157,
               0,
               StateRepository::Database::dal_function_now,
               0,
               0,
               0);
    v4 = (int)result <= 0;
    if ( (_DWORD)result )
      goto LABEL_4;
    result = sqlite3_create_function_v2(
               *(_QWORD *)this,
               "workid",
               0,
               2099205,
               this,
               StateRepository::Database::dal_function_workid,
               0,
               0,
               0);
    v4 = (int)result <= 0;
    if ( (_DWORD)result )
      goto LABEL_4;
    result = sqlite3_create_function_v2(
               *(_QWORD *)this,
               "startswith",
               2,
               2099204,
               0,
               StateRepository::Database::dal_function_startswith,
               0,
               0,
               0);
    v4 = (int)result <= 0;
    if ( (_DWORD)result )
      goto LABEL_4;
    result = sqlite3_create_function_v2(
               *(_QWORD *)this,
               "endswith",
               2,
               2099204,
               0,
               StateRepository::Database::dal_function_endswith,
               0,
               0,
               0);
    v4 = (int)result <= 0;
    if ( (_DWORD)result )
      goto LABEL_4;
    result = sqlite3_create_function_v2(
               *(_QWORD *)this,
               "compress",
               0xFFFFFFFFLL,
               2099201,
               0,
               StateRepository::Database::dal_function_compress,
               0,
               0,
               0);
    v4 = (int)result <= 0;
    if ( (_DWORD)result )
      goto LABEL_4;
    result = sqlite3_create_function_v2(
               *(_QWORD *)this,
               "uncompress",
               1,
               2099201,
               0,
               StateRepository::Database::dal_function_uncompress,
               0,
               0,
               0);
    v4 = (int)result <= 0;
    if ( (_DWORD)result )
      goto LABEL_4;
    result = sqlite3_create_function_v2(
               *(_QWORD *)this,
               "hash_base32",
               0xFFFFFFFFLL,
               2099204,
               0,
               StateRepository::Database::dal_function_hash_base32,
               0,
               0,
               0);
    v4 = (int)result <= 0;
    if ( (_DWORD)result )
      goto LABEL_4;
    result = sqlite3_create_function_v2(
               *(_QWORD *)this,
               "log",
               2,
               2099201,
               0,
               StateRepository::Database::dal_function_log,
               0,
               0,
               0);
    v4 = (int)result <= 0;
    if ( (_DWORD)result )
      goto LABEL_4;
    result = sqlite3_create_function_v2(
               *(_QWORD *)this,
               "compare_uint",
               2,
               2099200,
               0,
               StateRepository::Database::dal_function_compare_uint,
               0,
               0,
               0);
    v4 = (int)result <= 0;
    if ( (_DWORD)result )
      goto LABEL_4;
    result = sqlite3_create_function_v2(
               *(_QWORD *)this,
               "ge_uint",
               2,
               2099200,
               0,
               StateRepository::Database::dal_function_ge_uint,
               0,
               0,
               0);
    v4 = (int)result <= 0;
    if ( (_DWORD)result )
      goto LABEL_4;
    result = sqlite3_create_function_v2(
               *(_QWORD *)this,
               "gt_uint",
               2,
               2099200,
               0,
               StateRepository::Database::dal_function_gt_uint,
               0,
               0,
               0);
    v4 = (int)result <= 0;
    if ( (_DWORD)result )
      goto LABEL_4;
    result = sqlite3_create_function_v2(
               *(_QWORD *)this,
               "le_uint",
               2,
               2099200,
               0,
               StateRepository::Database::dal_function_le_uint,
               0,
               0,
               0);
    v4 = (int)result <= 0;
    if ( (_DWORD)result )
      goto LABEL_4;
    result = sqlite3_create_function_v2(
               *(_QWORD *)this,
               "lt_uint",
               2,
               2099200,
               0,
               StateRepository::Database::dal_function_lt_uint,
               0,
               0,
               0);
    v4 = (int)result <= 0;
    if ( (_DWORD)result )
      goto LABEL_4;
    result = sqlite3_create_function_v2(
               *(_QWORD *)this,
               "min_uint",
               0xFFFFFFFFLL,
               2099205,
               0,
               StateRepository::Database::dal_function_min_uint,
               0,
               0,
               0);
    v4 = (int)result <= 0;
    if ( (_DWORD)result )
      goto LABEL_4;
    result = sqlite3_create_function_v2(*(_QWORD *)this, "min_uint", 0, 2099205, 0, 0, 0, 0, 0);
    v4 = (int)result <= 0;
    if ( (_DWORD)result )
      goto LABEL_4;
    result = sqlite3_create_function_v2(
               *(_QWORD *)this,
               "min_uint",
               1,
               2099205,
               0,
               0,
               StateRepository::Database::dal_function_min_uint_Step,
               StateRepository::Database::dal_function_max_uint_Finalize,
               0);
    v4 = (int)result <= 0;
    if ( (_DWORD)result
      || (result = sqlite3_create_function_v2(
                     *(_QWORD *)this,
                     "max_uint",
                     0xFFFFFFFFLL,
                     2099205,
                     0,
                     StateRepository::Database::dal_function_max_uint,
                     0,
                     0,
                     0),
          v4 = (int)result <= 0,
          (_DWORD)result)
      || (result = sqlite3_create_function_v2(*(_QWORD *)this, "max_uint", 0, 2099205, 0, 0, 0, 0, 0),
          v4 = (int)result <= 0,
          (_DWORD)result)
      || (result = sqlite3_create_function_v2(
                     *(_QWORD *)this,
                     "max_uint",
                     1,
                     2099205,
                     0,
                     0,
                     StateRepository::Database::dal_function_max_uint_Step,
                     StateRepository::Database::dal_function_max_uint_Finalize,
                     0),
          v4 = (int)result <= 0,
          (_DWORD)result) )
    {
LABEL_4:
      if ( !v4 )
        return (unsigned __int16)result | 0x87AF0000;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCA2,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
      (const char *)0x8007139FLL,
      v5);
    return 2147947423LL;
  }
  return result;
}

```

## disassembly

```asm
0x1800a55f0  push    rbx
0x1800a55f2  push    rbp
0x1800a55f3  push    rsi
0x1800a55f4  push    rdi
0x1800a55f5  push    r14
0x1800a55f7  sub     rsp, 50h
0x1800a55fb  mov     rbx, rcx
0x1800a55fe  xor     edi, edi
0x1800a5600  mov     rcx, [rcx]
0x1800a5603  test    rcx, rcx
0x1800a5606  jnz     short loc_1800A562D
0x1800a5608  mov     rcx, [rsp+78h]; this
0x1800a560d  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800a5614  mov     ebx, 8007139Fh
0x1800a5619  mov     edx, 0CA2h; void *
0x1800a561e  mov     r9d, ebx; char *
0x1800a5621  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a5626  mov     eax, ebx
0x1800a5628  jmp     loc_1800A5B68
0x1800a562d  mov     [rsp+78h+var_38], rdi
0x1800a5632  lea     rax, ?dal_function_execution_flags@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_execution_flags(sqlite3_context *,int,sqlite3_value * *)
0x1800a5639  mov     [rsp+78h+var_40], rdi
0x1800a563e  lea     rdx, aExecutionFlags; "execution_flags"
0x1800a5645  mov     [rsp+78h+var_48], rdi
0x1800a564a  mov     esi, 200805h
0x1800a564f  mov     [rsp+78h+var_50], rax
0x1800a5654  mov     r9d, esi
0x1800a5657  xor     r8d, r8d
0x1800a565a  mov     [rsp+78h+var_58], rbx
0x1800a565f  call    cs:__imp_sqlite3_create_function_v2
0x1800a5665  test    eax, eax
0x1800a5667  jz      short loc_1800A567C
0x1800a5669  jle     loc_1800A5B68
0x1800a566f  movzx   eax, ax
0x1800a5672  or      eax, 87AF0000h
0x1800a5677  jmp     loc_1800A5B68
0x1800a567c  mov     rcx, [rbx]
0x1800a567f  lea     rax, ?dal_function_is_triggers_enabled@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_is_triggers_enabled(sqlite3_context *,int,sqlite3_value * *)
0x1800a5686  mov     [rsp+78h+var_38], rdi
0x1800a568b  lea     rdx, aIsTriggersEnab; "is_triggers_enabled"
0x1800a5692  mov     [rsp+78h+var_40], rdi
0x1800a5697  mov     r9d, esi
0x1800a569a  mov     [rsp+78h+var_48], rdi
0x1800a569f  xor     r8d, r8d
0x1800a56a2  mov     [rsp+78h+var_50], rax
0x1800a56a7  mov     [rsp+78h+var_58], rbx
0x1800a56ac  call    cs:__imp_sqlite3_create_function_v2
0x1800a56b2  test    eax, eax
0x1800a56b4  jnz     short loc_1800A5669
0x1800a56b6  mov     rcx, [rbx]
0x1800a56b9  lea     rax, ?dal_function_now@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_now(sqlite3_context *,int,sqlite3_value * *)
0x1800a56c0  mov     [rsp+78h+var_38], rdi
0x1800a56c5  lea     rdx, aNow; "now"
0x1800a56cc  mov     [rsp+78h+var_40], rdi
0x1800a56d1  mov     r9d, 200005h
0x1800a56d7  mov     [rsp+78h+var_48], rdi
0x1800a56dc  xor     r8d, r8d
0x1800a56df  mov     [rsp+78h+var_50], rax
0x1800a56e4  mov     [rsp+78h+var_58], rdi
0x1800a56e9  call    cs:__imp_sqlite3_create_function_v2
0x1800a56ef  test    eax, eax
0x1800a56f1  jnz     loc_1800A5669
0x1800a56f7  mov     rcx, [rbx]
0x1800a56fa  lea     rax, ?dal_function_workid@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_workid(sqlite3_context *,int,sqlite3_value * *)
0x1800a5701  mov     [rsp+78h+var_38], rdi
0x1800a5706  lea     rdx, aWorkid; "workid"
0x1800a570d  mov     [rsp+78h+var_40], rdi
0x1800a5712  mov     r9d, esi
0x1800a5715  mov     [rsp+78h+var_48], rdi
0x1800a571a  xor     r8d, r8d
0x1800a571d  mov     [rsp+78h+var_50], rax
0x1800a5722  mov     [rsp+78h+var_58], rbx
0x1800a5727  call    cs:__imp_sqlite3_create_function_v2
0x1800a572d  test    eax, eax
0x1800a572f  jnz     loc_1800A5669
0x1800a5735  mov     rcx, [rbx]
0x1800a5738  lea     rax, ?dal_function_startswith@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_startswith(sqlite3_context *,int,sqlite3_value * *)
0x1800a573f  mov     [rsp+78h+var_38], rdi
0x1800a5744  lea     rdx, aStartswith; "startswith"
0x1800a574b  mov     [rsp+78h+var_40], rdi
0x1800a5750  mov     r14d, 200804h
0x1800a5756  mov     [rsp+78h+var_48], rdi
0x1800a575b  mov     ebp, 2
0x1800a5760  mov     [rsp+78h+var_50], rax
0x1800a5765  mov     r9d, r14d
0x1800a5768  mov     r8d, ebp
0x1800a576b  mov     [rsp+78h+var_58], rdi
0x1800a5770  call    cs:__imp_sqlite3_create_function_v2
0x1800a5776  test    eax, eax
0x1800a5778  jnz     loc_1800A5669
0x1800a577e  mov     rcx, [rbx]
0x1800a5781  lea     rax, ?dal_function_endswith@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_endswith(sqlite3_context *,int,sqlite3_value * *)
0x1800a5788  mov     [rsp+78h+var_38], rdi
0x1800a578d  lea     rdx, aEndswith; "endswith"
0x1800a5794  mov     [rsp+78h+var_40], rdi
0x1800a5799  mov     r9d, r14d
0x1800a579c  mov     [rsp+78h+var_48], rdi
0x1800a57a1  mov     r8d, ebp
0x1800a57a4  mov     [rsp+78h+var_50], rax
0x1800a57a9  mov     [rsp+78h+var_58], rdi
0x1800a57ae  call    cs:__imp_sqlite3_create_function_v2
0x1800a57b4  test    eax, eax
0x1800a57b6  jnz     loc_1800A5669
0x1800a57bc  mov     rcx, [rbx]
0x1800a57bf  lea     rax, ?dal_function_compress@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_compress(sqlite3_context *,int,sqlite3_value * *)
0x1800a57c6  mov     [rsp+78h+var_38], rdi
0x1800a57cb  lea     r9d, [r14-3]
0x1800a57cf  mov     [rsp+78h+var_40], rdi
0x1800a57d4  lea     rdx, aCompress; "compress"
0x1800a57db  mov     [rsp+78h+var_48], rdi
0x1800a57e0  or      r8d, 0FFFFFFFFh
0x1800a57e4  mov     [rsp+78h+var_50], rax
0x1800a57e9  mov     [rsp+78h+var_58], rdi
0x1800a57ee  call    cs:__imp_sqlite3_create_function_v2
0x1800a57f4  test    eax, eax
0x1800a57f6  jnz     loc_1800A5669
0x1800a57fc  mov     rcx, [rbx]
0x1800a57ff  lea     rax, ?dal_function_uncompress@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_uncompress(sqlite3_context *,int,sqlite3_value * *)
0x1800a5806  mov     [rsp+78h+var_38], rdi
0x1800a580b  lea     r9d, [r14-3]
0x1800a580f  mov     [rsp+78h+var_40], rdi
0x1800a5814  lea     r8d, [rbp-1]
0x1800a5818  mov     [rsp+78h+var_48], rdi
0x1800a581d  lea     rdx, aUncompress; "uncompress"
0x1800a5824  mov     [rsp+78h+var_50], rax
0x1800a5829  mov     [rsp+78h+var_58], rdi
0x1800a582e  call    cs:__imp_sqlite3_create_function_v2
0x1800a5834  test    eax, eax
0x1800a5836  jnz     loc_1800A5669
0x1800a583c  mov     rcx, [rbx]
0x1800a583f  lea     rax, ?dal_function_hash_base32@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_hash_base32(sqlite3_context *,int,sqlite3_value * *)
0x1800a5846  mov     [rsp+78h+var_38], rdi
0x1800a584b  lea     rdx, aHashBase32; "hash_base32"
0x1800a5852  mov     [rsp+78h+var_40], rdi
0x1800a5857  mov     r9d, r14d
0x1800a585a  mov     [rsp+78h+var_48], rdi
0x1800a585f  or      r8d, 0FFFFFFFFh
0x1800a5863  mov     [rsp+78h+var_50], rax
0x1800a5868  mov     [rsp+78h+var_58], rdi
0x1800a586d  call    cs:__imp_sqlite3_create_function_v2
0x1800a5873  test    eax, eax
0x1800a5875  jnz     loc_1800A5669
0x1800a587b  mov     rcx, [rbx]
0x1800a587e  lea     rax, ?dal_function_log@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_log(sqlite3_context *,int,sqlite3_value * *)
0x1800a5885  mov     [rsp+78h+var_38], rdi
0x1800a588a  lea     r9d, [r14-3]
0x1800a588e  mov     [rsp+78h+var_40], rdi
0x1800a5893  lea     rdx, aLog; "log"
0x1800a589a  mov     [rsp+78h+var_48], rdi
0x1800a589f  mov     r8d, ebp
0x1800a58a2  mov     [rsp+78h+var_50], rax
0x1800a58a7  mov     [rsp+78h+var_58], rdi
0x1800a58ac  call    cs:__imp_sqlite3_create_function_v2
0x1800a58b2  test    eax, eax
0x1800a58b4  jnz     loc_1800A5669
0x1800a58ba  mov     rcx, [rbx]
0x1800a58bd  lea     rax, ?dal_function_compare_uint@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_compare_uint(sqlite3_context *,int,sqlite3_value * *)
0x1800a58c4  mov     [rsp+78h+var_38], rdi
0x1800a58c9  lea     rdx, aCompareUint; "compare_uint"
0x1800a58d0  mov     [rsp+78h+var_40], rdi
0x1800a58d5  mov     r14d, 200800h
0x1800a58db  mov     [rsp+78h+var_48], rdi
0x1800a58e0  mov     r9d, r14d
0x1800a58e3  mov     [rsp+78h+var_50], rax
0x1800a58e8  mov     r8d, ebp
0x1800a58eb  mov     [rsp+78h+var_58], rdi
0x1800a58f0  call    cs:__imp_sqlite3_create_function_v2
0x1800a58f6  test    eax, eax
0x1800a58f8  jnz     loc_1800A5669
0x1800a58fe  mov     rcx, [rbx]
0x1800a5901  lea     rax, ?dal_function_ge_uint@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_ge_uint(sqlite3_context *,int,sqlite3_value * *)
0x1800a5908  mov     [rsp+78h+var_38], rdi
0x1800a590d  lea     rdx, aGeUint; "ge_uint"
0x1800a5914  mov     [rsp+78h+var_40], rdi
0x1800a5919  mov     r9d, r14d
0x1800a591c  mov     [rsp+78h+var_48], rdi
0x1800a5921  mov     r8d, ebp
0x1800a5924  mov     [rsp+78h+var_50], rax
0x1800a5929  mov     [rsp+78h+var_58], rdi
0x1800a592e  call    cs:__imp_sqlite3_create_function_v2
0x1800a5934  test    eax, eax
0x1800a5936  jnz     loc_1800A5669
0x1800a593c  mov     rcx, [rbx]
0x1800a593f  lea     rax, ?dal_function_gt_uint@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_gt_uint(sqlite3_context *,int,sqlite3_value * *)
0x1800a5946  mov     [rsp+78h+var_38], rdi
0x1800a594b  lea     rdx, aGtUint; "gt_uint"
0x1800a5952  mov     [rsp+78h+var_40], rdi
0x1800a5957  mov     r9d, r14d
0x1800a595a  mov     [rsp+78h+var_48], rdi
0x1800a595f  mov     r8d, ebp
0x1800a5962  mov     [rsp+78h+var_50], rax
0x1800a5967  mov     [rsp+78h+var_58], rdi
0x1800a596c  call    cs:__imp_sqlite3_create_function_v2
0x1800a5972  test    eax, eax
0x1800a5974  jnz     loc_1800A5669
0x1800a597a  mov     rcx, [rbx]
0x1800a597d  lea     rax, ?dal_function_le_uint@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_le_uint(sqlite3_context *,int,sqlite3_value * *)
0x1800a5984  mov     [rsp+78h+var_38], rdi
0x1800a5989  lea     rdx, aLeUint; "le_uint"
0x1800a5990  mov     [rsp+78h+var_40], rdi
0x1800a5995  mov     r9d, r14d
0x1800a5998  mov     [rsp+78h+var_48], rdi
0x1800a599d  mov     r8d, ebp
0x1800a59a0  mov     [rsp+78h+var_50], rax
0x1800a59a5  mov     [rsp+78h+var_58], rdi
0x1800a59aa  call    cs:__imp_sqlite3_create_function_v2
0x1800a59b0  test    eax, eax
0x1800a59b2  jnz     loc_1800A5669
0x1800a59b8  mov     rcx, [rbx]
0x1800a59bb  lea     rax, ?dal_function_lt_uint@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_lt_uint(sqlite3_context *,int,sqlite3_value * *)
0x1800a59c2  mov     [rsp+78h+var_38], rdi
0x1800a59c7  lea     rdx, aLtUint; "lt_uint"
0x1800a59ce  mov     [rsp+78h+var_40], rdi
0x1800a59d3  mov     r9d, r14d
0x1800a59d6  mov     [rsp+78h+var_48], rdi
0x1800a59db  mov     r8d, ebp
0x1800a59de  mov     [rsp+78h+var_50], rax
0x1800a59e3  mov     [rsp+78h+var_58], rdi
0x1800a59e8  call    cs:__imp_sqlite3_create_function_v2
0x1800a59ee  test    eax, eax
0x1800a59f0  jnz     loc_1800A5669
0x1800a59f6  mov     rcx, [rbx]
0x1800a59f9  lea     rax, ?dal_function_min_uint@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_min_uint(sqlite3_context *,int,sqlite3_value * *)
0x1800a5a00  mov     [rsp+78h+var_38], rdi
0x1800a5a05  lea     rbp, aMinUint; "min_uint"
0x1800a5a0c  mov     [rsp+78h+var_40], rdi
0x1800a5a11  mov     r9d, esi
0x1800a5a14  mov     [rsp+78h+var_48], rdi
0x1800a5a19  or      r8d, 0FFFFFFFFh
0x1800a5a1d  mov     [rsp+78h+var_50], rax
0x1800a5a22  mov     rdx, rbp
0x1800a5a25  mov     [rsp+78h+var_58], rdi
0x1800a5a2a  call    cs:__imp_sqlite3_create_function_v2
0x1800a5a30  test    eax, eax
0x1800a5a32  jnz     loc_1800A5669
0x1800a5a38  mov     rcx, [rbx]
0x1800a5a3b  mov     r9d, esi
0x1800a5a3e  mov     [rsp+78h+var_38], rdi
0x1800a5a43  xor     r8d, r8d
0x1800a5a46  mov     [rsp+78h+var_40], rdi
0x1800a5a4b  mov     rdx, rbp
0x1800a5a4e  mov     [rsp+78h+var_48], rdi
0x1800a5a53  mov     [rsp+78h+var_50], rdi
0x1800a5a58  mov     [rsp+78h+var_58], rdi
0x1800a5a5d  call    cs:__imp_sqlite3_create_function_v2
0x1800a5a63  test    eax, eax
0x1800a5a65  jnz     loc_1800A5669
0x1800a5a6b  mov     rcx, [rbx]
0x1800a5a6e  lea     rax, ?dal_function_max_uint_Finalize@Database@StateRepository@@CAXPEAUsqlite3_context@@@Z; StateRepository::Database::dal_function_max_uint_Finalize(sqlite3_context *)
0x1800a5a75  mov     [rsp+78h+var_38], rdi
0x1800a5a7a  mov     r9d, esi
0x1800a5a7d  mov     [rsp+78h+var_40], rax
0x1800a5a82  mov     r8d, 1
0x1800a5a88  lea     rax, ?dal_function_min_uint_Step@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_min_uint_Step(sqlite3_context *,int,sqlite3_value * *)
0x1800a5a8f  mov     rdx, rbp
0x1800a5a92  mov     [rsp+78h+var_48], rax
0x1800a5a97  mov     [rsp+78h+var_50], rdi
0x1800a5a9c  mov     [rsp+78h+var_58], rdi
0x1800a5aa1  call    cs:__imp_sqlite3_create_function_v2
0x1800a5aa7  test    eax, eax
0x1800a5aa9  jnz     loc_1800A5669
0x1800a5aaf  mov     rcx, [rbx]
0x1800a5ab2  lea     rax, ?dal_function_max_uint@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_max_uint(sqlite3_context *,int,sqlite3_value * *)
0x1800a5ab9  mov     [rsp+78h+var_38], rdi
0x1800a5abe  lea     rbp, aMaxUint; "max_uint"
0x1800a5ac5  mov     [rsp+78h+var_40], rdi
0x1800a5aca  mov     r9d, esi
0x1800a5acd  mov     [rsp+78h+var_48], rdi
0x1800a5ad2  or      r8d, 0FFFFFFFFh
0x1800a5ad6  mov     [rsp+78h+var_50], rax
0x1800a5adb  mov     rdx, rbp
0x1800a5ade  mov     [rsp+78h+var_58], rdi
0x1800a5ae3  call    cs:__imp_sqlite3_create_function_v2
0x1800a5ae9  test    eax, eax
0x1800a5aeb  jnz     loc_1800A5669
0x1800a5af1  mov     rcx, [rbx]
0x1800a5af4  mov     r9d, esi
0x1800a5af7  mov     [rsp+78h+var_38], rdi
0x1800a5afc  xor     r8d, r8d
0x1800a5aff  mov     [rsp+78h+var_40], rdi
0x1800a5b04  mov     rdx, rbp
0x1800a5b07  mov     [rsp+78h+var_48], rdi
0x1800a5b0c  mov     [rsp+78h+var_50], rdi
0x1800a5b11  mov     [rsp+78h+var_58], rdi
0x1800a5b16  call    cs:__imp_sqlite3_create_function_v2
0x1800a5b1c  test    eax, eax
0x1800a5b1e  jnz     loc_1800A5669
0x1800a5b24  mov     rcx, [rbx]
0x1800a5b27  lea     rax, ?dal_function_max_uint_Finalize@Database@StateRepository@@CAXPEAUsqlite3_context@@@Z; StateRepository::Database::dal_function_max_uint_Finalize(sqlite3_context *)
0x1800a5b2e  mov     [rsp+78h+var_38], rdi
0x1800a5b33  mov     r9d, esi
0x1800a5b36  mov     [rsp+78h+var_40], rax
0x1800a5b3b  mov     r8d, 1
0x1800a5b41  lea     rax, ?dal_function_max_uint_Step@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_max_uint_Step(sqlite3_context *,int,sqlite3_value * *)
0x1800a5b48  mov     rdx, rbp
0x1800a5b4b  mov     [rsp+78h+var_48], rax
0x1800a5b50  mov     [rsp+78h+var_50], rdi
0x1800a5b55  mov     [rsp+78h+var_58], rdi
0x1800a5b5a  call    cs:__imp_sqlite3_create_function_v2
0x1800a5b60  test    eax, eax
  ... truncated ...
```
