# StateRepository::Database::RegisterFunctions(void)

- ea: `0x1800fb1f4`
- end: `0x1800fb762`
- name: `?RegisterFunctions@Database@StateRepository@@QEAAJXZ`
- size: `1390`
- prototype: `__int64 __fastcall(StateRepository::Database *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800fa944`
- `0x180108668`

## callees

- `0x18000a5f0`
- `0x1800eabf4`
- `0x1800fb1f4`

## string_xrefs

- `0x1800fb211`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1800fb3d2`: `compress`
- `0x1800fb41a`: `uncompress`
- `0x1800fb4c3`: `compare_uint`

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
               (unsigned int)"execution_flags",
               0,
               2099205,
               (__int64)this,
               (__int64)StateRepository::Database::dal_function_execution_flags,
               0,
               0,
               0);
    v4 = (int)result <= 0;
    if ( (_DWORD)result )
      goto LABEL_4;
    result = sqlite3_create_function_v2(
               *(_QWORD *)this,
               (unsigned int)"is_triggers_enabled",
               0,
               2099205,
               (__int64)this,
               (__int64)StateRepository::Database::dal_function_is_triggers_enabled,
               0,
               0,
               0);
    v4 = (int)result <= 0;
    if ( (_DWORD)result )
      goto LABEL_4;
    result = sqlite3_create_function_v2(
               *(_QWORD *)this,
               (unsigned int)"now",
               0,
               2097157,
               0,
               (__int64)StateRepository::Database::dal_function_now,
               0,
               0,
               0);
    v4 = (int)result <= 0;
    if ( (_DWORD)result )
      goto LABEL_4;
    result = sqlite3_create_function_v2(
               *(_QWORD *)this,
               (unsigned int)"workid",
               0,
               2099205,
               (__int64)this,
               (__int64)StateRepository::Database::dal_function_workid,
               0,
               0,
               0);
    v4 = (int)result <= 0;
    if ( (_DWORD)result )
      goto LABEL_4;
    result = sqlite3_create_function_v2(
               *(_QWORD *)this,
               (unsigned int)"startswith",
               2,
               2099204,
               0,
               (__int64)StateRepository::Database::dal_function_startswith,
               0,
               0,
               0);
    v4 = (int)result <= 0;
    if ( (_DWORD)result )
      goto LABEL_4;
    result = sqlite3_create_function_v2(
               *(_QWORD *)this,
               (unsigned int)"endswith",
               2,
               2099204,
               0,
               (__int64)StateRepository::Database::dal_function_endswith,
               0,
               0,
               0);
    v4 = (int)result <= 0;
    if ( (_DWORD)result )
      goto LABEL_4;
    result = sqlite3_create_function_v2(
               *(_QWORD *)this,
               (unsigned int)"compress",
               -1,
               2099201,
               0,
               (__int64)StateRepository::Database::dal_function_compress,
               0,
               0,
               0);
    v4 = (int)result <= 0;
    if ( (_DWORD)result )
      goto LABEL_4;
    result = sqlite3_create_function_v2(
               *(_QWORD *)this,
               (unsigned int)"uncompress",
               1,
               2099201,
               0,
               (__int64)StateRepository::Database::dal_function_uncompress,
               0,
               0,
               0);
    v4 = (int)result <= 0;
    if ( (_DWORD)result )
      goto LABEL_4;
    result = sqlite3_create_function_v2(
               *(_QWORD *)this,
               (unsigned int)"hash_base32",
               -1,
               2099204,
               0,
               (__int64)StateRepository::Database::dal_function_hash_base32,
               0,
               0,
               0);
    v4 = (int)result <= 0;
    if ( (_DWORD)result )
      goto LABEL_4;
    result = sqlite3_create_function_v2(
               *(_QWORD *)this,
               (unsigned int)"log",
               2,
               2099201,
               0,
               (__int64)StateRepository::Database::dal_function_log,
               0,
               0,
               0);
    v4 = (int)result <= 0;
    if ( (_DWORD)result )
      goto LABEL_4;
    result = sqlite3_create_function_v2(
               *(_QWORD *)this,
               (unsigned int)"compare_uint",
               2,
               2099200,
               0,
               (__int64)StateRepository::Database::dal_function_compare_uint,
               0,
               0,
               0);
    v4 = (int)result <= 0;
    if ( (_DWORD)result )
      goto LABEL_4;
    result = sqlite3_create_function_v2(
               *(_QWORD *)this,
               (unsigned int)"ge_uint",
               2,
               2099200,
               0,
               (__int64)StateRepository::Database::dal_function_ge_uint,
               0,
               0,
               0);
    v4 = (int)result <= 0;
    if ( (_DWORD)result )
      goto LABEL_4;
    result = sqlite3_create_function_v2(
               *(_QWORD *)this,
               (unsigned int)"gt_uint",
               2,
               2099200,
               0,
               (__int64)StateRepository::Database::dal_function_gt_uint,
               0,
               0,
               0);
    v4 = (int)result <= 0;
    if ( (_DWORD)result )
      goto LABEL_4;
    result = sqlite3_create_function_v2(
               *(_QWORD *)this,
               (unsigned int)"le_uint",
               2,
               2099200,
               0,
               (__int64)StateRepository::Database::dal_function_le_uint,
               0,
               0,
               0);
    v4 = (int)result <= 0;
    if ( (_DWORD)result )
      goto LABEL_4;
    result = sqlite3_create_function_v2(
               *(_QWORD *)this,
               (unsigned int)"lt_uint",
               2,
               2099200,
               0,
               (__int64)StateRepository::Database::dal_function_lt_uint,
               0,
               0,
               0);
    v4 = (int)result <= 0;
    if ( (_DWORD)result )
      goto LABEL_4;
    result = sqlite3_create_function_v2(
               *(_QWORD *)this,
               (unsigned int)"min_uint",
               -1,
               2099205,
               0,
               (__int64)StateRepository::Database::dal_function_min_uint,
               0,
               0,
               0);
    v4 = (int)result <= 0;
    if ( (_DWORD)result )
      goto LABEL_4;
    result = sqlite3_create_function_v2(*(_QWORD *)this, (unsigned int)"min_uint", 0, 2099205, 0, 0, 0, 0, 0);
    v4 = (int)result <= 0;
    if ( (_DWORD)result )
      goto LABEL_4;
    result = sqlite3_create_function_v2(
               *(_QWORD *)this,
               (unsigned int)"min_uint",
               1,
               2099205,
               0,
               0,
               (__int64)StateRepository::Database::dal_function_min_uint_Step,
               (__int64)StateRepository::Database::dal_function_max_uint_Finalize,
               0);
    v4 = (int)result <= 0;
    if ( (_DWORD)result
      || (result = sqlite3_create_function_v2(
                     *(_QWORD *)this,
                     (unsigned int)"max_uint",
                     -1,
                     2099205,
                     0,
                     (__int64)StateRepository::Database::dal_function_max_uint,
                     0,
                     0,
                     0),
          v4 = (int)result <= 0,
          (_DWORD)result)
      || (result = sqlite3_create_function_v2(*(_QWORD *)this, (unsigned int)"max_uint", 0, 2099205, 0, 0, 0, 0, 0),
          v4 = (int)result <= 0,
          (_DWORD)result)
      || (result = sqlite3_create_function_v2(
                     *(_QWORD *)this,
                     (unsigned int)"max_uint",
                     1,
                     2099205,
                     0,
                     0,
                     (__int64)StateRepository::Database::dal_function_max_uint_Step,
                     (__int64)StateRepository::Database::dal_function_max_uint_Finalize,
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
0x1800fb1f4  push    rbx
0x1800fb1f6  push    rbp
0x1800fb1f7  push    rsi
0x1800fb1f8  push    rdi
0x1800fb1f9  push    r14
0x1800fb1fb  sub     rsp, 50h
0x1800fb1ff  mov     rbx, rcx
0x1800fb202  xor     edi, edi
0x1800fb204  mov     rcx, [rcx]
0x1800fb207  test    rcx, rcx
0x1800fb20a  jnz     short loc_1800FB231
0x1800fb20c  mov     rcx, [rsp+78h]; this
0x1800fb211  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800fb218  mov     ebx, 8007139Fh
0x1800fb21d  mov     edx, 0CA2h; void *
0x1800fb222  mov     r9d, ebx; char *
0x1800fb225  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fb22a  mov     eax, ebx
0x1800fb22c  jmp     loc_1800FB757
0x1800fb231  mov     [rsp+78h+var_38], rdi
0x1800fb236  lea     rax, ?dal_function_execution_flags@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_execution_flags(sqlite3_context *,int,sqlite3_value * *)
0x1800fb23d  mov     [rsp+78h+var_40], rdi
0x1800fb242  lea     rdx, aExecutionFlags; "execution_flags"
0x1800fb249  mov     [rsp+78h+var_48], rdi
0x1800fb24e  mov     esi, 200805h
0x1800fb253  mov     [rsp+78h+var_50], rax
0x1800fb258  mov     r9d, esi
0x1800fb25b  xor     r8d, r8d
0x1800fb25e  mov     [rsp+78h+var_58], rbx
0x1800fb263  call    sqlite3_create_function_v2
0x1800fb268  test    eax, eax
0x1800fb26a  jz      short loc_1800FB27F
0x1800fb26c  jle     loc_1800FB757
0x1800fb272  movzx   eax, ax
0x1800fb275  or      eax, 87AF0000h
0x1800fb27a  jmp     loc_1800FB757
0x1800fb27f  mov     rcx, [rbx]
0x1800fb282  lea     rax, ?dal_function_is_triggers_enabled@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_is_triggers_enabled(sqlite3_context *,int,sqlite3_value * *)
0x1800fb289  mov     [rsp+78h+var_38], rdi
0x1800fb28e  lea     rdx, aIsTriggersEnab; "is_triggers_enabled"
0x1800fb295  mov     [rsp+78h+var_40], rdi
0x1800fb29a  mov     r9d, esi
0x1800fb29d  mov     [rsp+78h+var_48], rdi
0x1800fb2a2  xor     r8d, r8d
0x1800fb2a5  mov     [rsp+78h+var_50], rax
0x1800fb2aa  mov     [rsp+78h+var_58], rbx
0x1800fb2af  call    sqlite3_create_function_v2
0x1800fb2b4  test    eax, eax
0x1800fb2b6  jnz     short loc_1800FB26C
0x1800fb2b8  mov     rcx, [rbx]
0x1800fb2bb  lea     rax, ?dal_function_now@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_now(sqlite3_context *,int,sqlite3_value * *)
0x1800fb2c2  mov     [rsp+78h+var_38], rdi
0x1800fb2c7  lea     rdx, aNow; "now"
0x1800fb2ce  mov     [rsp+78h+var_40], rdi
0x1800fb2d3  mov     r9d, 200005h
0x1800fb2d9  mov     [rsp+78h+var_48], rdi
0x1800fb2de  xor     r8d, r8d
0x1800fb2e1  mov     [rsp+78h+var_50], rax
0x1800fb2e6  mov     [rsp+78h+var_58], rdi
0x1800fb2eb  call    sqlite3_create_function_v2
0x1800fb2f0  test    eax, eax
0x1800fb2f2  jnz     loc_1800FB26C
0x1800fb2f8  mov     rcx, [rbx]
0x1800fb2fb  lea     rax, ?dal_function_workid@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_workid(sqlite3_context *,int,sqlite3_value * *)
0x1800fb302  mov     [rsp+78h+var_38], rdi
0x1800fb307  lea     rdx, aWorkid; "workid"
0x1800fb30e  mov     [rsp+78h+var_40], rdi
0x1800fb313  mov     r9d, esi
0x1800fb316  mov     [rsp+78h+var_48], rdi
0x1800fb31b  xor     r8d, r8d
0x1800fb31e  mov     [rsp+78h+var_50], rax
0x1800fb323  mov     [rsp+78h+var_58], rbx
0x1800fb328  call    sqlite3_create_function_v2
0x1800fb32d  test    eax, eax
0x1800fb32f  jnz     loc_1800FB26C
0x1800fb335  mov     rcx, [rbx]
0x1800fb338  lea     rax, ?dal_function_startswith@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_startswith(sqlite3_context *,int,sqlite3_value * *)
0x1800fb33f  mov     [rsp+78h+var_38], rdi
0x1800fb344  lea     rdx, aStartswith; "startswith"
0x1800fb34b  mov     [rsp+78h+var_40], rdi
0x1800fb350  mov     r14d, 200804h
0x1800fb356  mov     [rsp+78h+var_48], rdi
0x1800fb35b  mov     ebp, 2
0x1800fb360  mov     [rsp+78h+var_50], rax
0x1800fb365  mov     r9d, r14d
0x1800fb368  mov     r8d, ebp
0x1800fb36b  mov     [rsp+78h+var_58], rdi
0x1800fb370  call    sqlite3_create_function_v2
0x1800fb375  test    eax, eax
0x1800fb377  jnz     loc_1800FB26C
0x1800fb37d  mov     rcx, [rbx]
0x1800fb380  lea     rax, ?dal_function_endswith@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_endswith(sqlite3_context *,int,sqlite3_value * *)
0x1800fb387  mov     [rsp+78h+var_38], rdi
0x1800fb38c  lea     rdx, aEndswith; "endswith"
0x1800fb393  mov     [rsp+78h+var_40], rdi
0x1800fb398  mov     r9d, r14d
0x1800fb39b  mov     [rsp+78h+var_48], rdi
0x1800fb3a0  mov     r8d, ebp
0x1800fb3a3  mov     [rsp+78h+var_50], rax
0x1800fb3a8  mov     [rsp+78h+var_58], rdi
0x1800fb3ad  call    sqlite3_create_function_v2
0x1800fb3b2  test    eax, eax
0x1800fb3b4  jnz     loc_1800FB26C
0x1800fb3ba  mov     rcx, [rbx]
0x1800fb3bd  lea     rax, ?dal_function_compress@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_compress(sqlite3_context *,int,sqlite3_value * *)
0x1800fb3c4  mov     [rsp+78h+var_38], rdi
0x1800fb3c9  lea     r9d, [r14-3]
0x1800fb3cd  mov     [rsp+78h+var_40], rdi
0x1800fb3d2  lea     rdx, aCompress; "compress"
0x1800fb3d9  mov     [rsp+78h+var_48], rdi
0x1800fb3de  or      r8d, 0FFFFFFFFh
0x1800fb3e2  mov     [rsp+78h+var_50], rax
0x1800fb3e7  mov     [rsp+78h+var_58], rdi
0x1800fb3ec  call    sqlite3_create_function_v2
0x1800fb3f1  test    eax, eax
0x1800fb3f3  jnz     loc_1800FB26C
0x1800fb3f9  mov     rcx, [rbx]
0x1800fb3fc  lea     rax, ?dal_function_uncompress@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_uncompress(sqlite3_context *,int,sqlite3_value * *)
0x1800fb403  mov     [rsp+78h+var_38], rdi
0x1800fb408  lea     r9d, [r14-3]
0x1800fb40c  mov     [rsp+78h+var_40], rdi
0x1800fb411  lea     r8d, [rbp-1]
0x1800fb415  mov     [rsp+78h+var_48], rdi
0x1800fb41a  lea     rdx, aUncompress; "uncompress"
0x1800fb421  mov     [rsp+78h+var_50], rax
0x1800fb426  mov     [rsp+78h+var_58], rdi
0x1800fb42b  call    sqlite3_create_function_v2
0x1800fb430  test    eax, eax
0x1800fb432  jnz     loc_1800FB26C
0x1800fb438  mov     rcx, [rbx]
0x1800fb43b  lea     rax, ?dal_function_hash_base32@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_hash_base32(sqlite3_context *,int,sqlite3_value * *)
0x1800fb442  mov     [rsp+78h+var_38], rdi
0x1800fb447  lea     rdx, aHashBase32; "hash_base32"
0x1800fb44e  mov     [rsp+78h+var_40], rdi
0x1800fb453  mov     r9d, r14d
0x1800fb456  mov     [rsp+78h+var_48], rdi
0x1800fb45b  or      r8d, 0FFFFFFFFh
0x1800fb45f  mov     [rsp+78h+var_50], rax
0x1800fb464  mov     [rsp+78h+var_58], rdi
0x1800fb469  call    sqlite3_create_function_v2
0x1800fb46e  test    eax, eax
0x1800fb470  jnz     loc_1800FB26C
0x1800fb476  mov     rcx, [rbx]
0x1800fb479  lea     rax, ?dal_function_log@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_log(sqlite3_context *,int,sqlite3_value * *)
0x1800fb480  mov     [rsp+78h+var_38], rdi
0x1800fb485  lea     r9d, [r14-3]
0x1800fb489  mov     [rsp+78h+var_40], rdi
0x1800fb48e  lea     rdx, aLog; "log"
0x1800fb495  mov     [rsp+78h+var_48], rdi
0x1800fb49a  mov     r8d, ebp
0x1800fb49d  mov     [rsp+78h+var_50], rax
0x1800fb4a2  mov     [rsp+78h+var_58], rdi
0x1800fb4a7  call    sqlite3_create_function_v2
0x1800fb4ac  test    eax, eax
0x1800fb4ae  jnz     loc_1800FB26C
0x1800fb4b4  mov     rcx, [rbx]
0x1800fb4b7  lea     rax, ?dal_function_compare_uint@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_compare_uint(sqlite3_context *,int,sqlite3_value * *)
0x1800fb4be  mov     [rsp+78h+var_38], rdi
0x1800fb4c3  lea     rdx, aCompareUint; "compare_uint"
0x1800fb4ca  mov     [rsp+78h+var_40], rdi
0x1800fb4cf  mov     r14d, 200800h
0x1800fb4d5  mov     [rsp+78h+var_48], rdi
0x1800fb4da  mov     r9d, r14d
0x1800fb4dd  mov     [rsp+78h+var_50], rax
0x1800fb4e2  mov     r8d, ebp
0x1800fb4e5  mov     [rsp+78h+var_58], rdi
0x1800fb4ea  call    sqlite3_create_function_v2
0x1800fb4ef  test    eax, eax
0x1800fb4f1  jnz     loc_1800FB26C
0x1800fb4f7  mov     rcx, [rbx]
0x1800fb4fa  lea     rax, ?dal_function_ge_uint@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_ge_uint(sqlite3_context *,int,sqlite3_value * *)
0x1800fb501  mov     [rsp+78h+var_38], rdi
0x1800fb506  lea     rdx, aGeUint; "ge_uint"
0x1800fb50d  mov     [rsp+78h+var_40], rdi
0x1800fb512  mov     r9d, r14d
0x1800fb515  mov     [rsp+78h+var_48], rdi
0x1800fb51a  mov     r8d, ebp
0x1800fb51d  mov     [rsp+78h+var_50], rax
0x1800fb522  mov     [rsp+78h+var_58], rdi
0x1800fb527  call    sqlite3_create_function_v2
0x1800fb52c  test    eax, eax
0x1800fb52e  jnz     loc_1800FB26C
0x1800fb534  mov     rcx, [rbx]
0x1800fb537  lea     rax, ?dal_function_gt_uint@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_gt_uint(sqlite3_context *,int,sqlite3_value * *)
0x1800fb53e  mov     [rsp+78h+var_38], rdi
0x1800fb543  lea     rdx, aGtUint; "gt_uint"
0x1800fb54a  mov     [rsp+78h+var_40], rdi
0x1800fb54f  mov     r9d, r14d
0x1800fb552  mov     [rsp+78h+var_48], rdi
0x1800fb557  mov     r8d, ebp
0x1800fb55a  mov     [rsp+78h+var_50], rax
0x1800fb55f  mov     [rsp+78h+var_58], rdi
0x1800fb564  call    sqlite3_create_function_v2
0x1800fb569  test    eax, eax
0x1800fb56b  jnz     loc_1800FB26C
0x1800fb571  mov     rcx, [rbx]
0x1800fb574  lea     rax, ?dal_function_le_uint@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_le_uint(sqlite3_context *,int,sqlite3_value * *)
0x1800fb57b  mov     [rsp+78h+var_38], rdi
0x1800fb580  lea     rdx, aLeUint; "le_uint"
0x1800fb587  mov     [rsp+78h+var_40], rdi
0x1800fb58c  mov     r9d, r14d
0x1800fb58f  mov     [rsp+78h+var_48], rdi
0x1800fb594  mov     r8d, ebp
0x1800fb597  mov     [rsp+78h+var_50], rax
0x1800fb59c  mov     [rsp+78h+var_58], rdi
0x1800fb5a1  call    sqlite3_create_function_v2
0x1800fb5a6  test    eax, eax
0x1800fb5a8  jnz     loc_1800FB26C
0x1800fb5ae  mov     rcx, [rbx]
0x1800fb5b1  lea     rax, ?dal_function_lt_uint@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_lt_uint(sqlite3_context *,int,sqlite3_value * *)
0x1800fb5b8  mov     [rsp+78h+var_38], rdi
0x1800fb5bd  lea     rdx, aLtUint; "lt_uint"
0x1800fb5c4  mov     [rsp+78h+var_40], rdi
0x1800fb5c9  mov     r9d, r14d
0x1800fb5cc  mov     [rsp+78h+var_48], rdi
0x1800fb5d1  mov     r8d, ebp
0x1800fb5d4  mov     [rsp+78h+var_50], rax
0x1800fb5d9  mov     [rsp+78h+var_58], rdi
0x1800fb5de  call    sqlite3_create_function_v2
0x1800fb5e3  test    eax, eax
0x1800fb5e5  jnz     loc_1800FB26C
0x1800fb5eb  mov     rcx, [rbx]
0x1800fb5ee  lea     rax, ?dal_function_min_uint@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_min_uint(sqlite3_context *,int,sqlite3_value * *)
0x1800fb5f5  mov     [rsp+78h+var_38], rdi
0x1800fb5fa  lea     rbp, aMinUint; "min_uint"
0x1800fb601  mov     [rsp+78h+var_40], rdi
0x1800fb606  mov     r9d, esi
0x1800fb609  mov     [rsp+78h+var_48], rdi
0x1800fb60e  or      r8d, 0FFFFFFFFh
0x1800fb612  mov     [rsp+78h+var_50], rax
0x1800fb617  mov     rdx, rbp
0x1800fb61a  mov     [rsp+78h+var_58], rdi
0x1800fb61f  call    sqlite3_create_function_v2
0x1800fb624  test    eax, eax
0x1800fb626  jnz     loc_1800FB26C
0x1800fb62c  mov     rcx, [rbx]
0x1800fb62f  mov     r9d, esi
0x1800fb632  mov     [rsp+78h+var_38], rdi
0x1800fb637  xor     r8d, r8d
0x1800fb63a  mov     [rsp+78h+var_40], rdi
0x1800fb63f  mov     rdx, rbp
0x1800fb642  mov     [rsp+78h+var_48], rdi
0x1800fb647  mov     [rsp+78h+var_50], rdi
0x1800fb64c  mov     [rsp+78h+var_58], rdi
0x1800fb651  call    sqlite3_create_function_v2
0x1800fb656  test    eax, eax
0x1800fb658  jnz     loc_1800FB26C
0x1800fb65e  mov     rcx, [rbx]
0x1800fb661  lea     rax, ?dal_function_max_uint_Finalize@Database@StateRepository@@CAXPEAUsqlite3_context@@@Z; StateRepository::Database::dal_function_max_uint_Finalize(sqlite3_context *)
0x1800fb668  mov     [rsp+78h+var_38], rdi
0x1800fb66d  mov     r9d, esi
0x1800fb670  mov     [rsp+78h+var_40], rax
0x1800fb675  mov     r8d, 1
0x1800fb67b  lea     rax, ?dal_function_min_uint_Step@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_min_uint_Step(sqlite3_context *,int,sqlite3_value * *)
0x1800fb682  mov     rdx, rbp
0x1800fb685  mov     [rsp+78h+var_48], rax
0x1800fb68a  mov     [rsp+78h+var_50], rdi
0x1800fb68f  mov     [rsp+78h+var_58], rdi
0x1800fb694  call    sqlite3_create_function_v2
0x1800fb699  test    eax, eax
0x1800fb69b  jnz     loc_1800FB26C
0x1800fb6a1  mov     rcx, [rbx]
0x1800fb6a4  lea     rax, ?dal_function_max_uint@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_max_uint(sqlite3_context *,int,sqlite3_value * *)
0x1800fb6ab  mov     [rsp+78h+var_38], rdi
0x1800fb6b0  lea     rbp, aMaxUint; "max_uint"
0x1800fb6b7  mov     [rsp+78h+var_40], rdi
0x1800fb6bc  mov     r9d, esi
0x1800fb6bf  mov     [rsp+78h+var_48], rdi
0x1800fb6c4  or      r8d, 0FFFFFFFFh
0x1800fb6c8  mov     [rsp+78h+var_50], rax
0x1800fb6cd  mov     rdx, rbp
0x1800fb6d0  mov     [rsp+78h+var_58], rdi
0x1800fb6d5  call    sqlite3_create_function_v2
0x1800fb6da  test    eax, eax
0x1800fb6dc  jnz     loc_1800FB26C
0x1800fb6e2  mov     rcx, [rbx]
0x1800fb6e5  mov     r9d, esi
0x1800fb6e8  mov     [rsp+78h+var_38], rdi
0x1800fb6ed  xor     r8d, r8d
0x1800fb6f0  mov     [rsp+78h+var_40], rdi
0x1800fb6f5  mov     rdx, rbp
0x1800fb6f8  mov     [rsp+78h+var_48], rdi
0x1800fb6fd  mov     [rsp+78h+var_50], rdi
0x1800fb702  mov     [rsp+78h+var_58], rdi
0x1800fb707  call    sqlite3_create_function_v2
0x1800fb70c  test    eax, eax
0x1800fb70e  jnz     loc_1800FB26C
0x1800fb714  mov     rcx, [rbx]
0x1800fb717  lea     rax, ?dal_function_max_uint_Finalize@Database@StateRepository@@CAXPEAUsqlite3_context@@@Z; StateRepository::Database::dal_function_max_uint_Finalize(sqlite3_context *)
0x1800fb71e  mov     [rsp+78h+var_38], rdi
0x1800fb723  mov     r9d, esi
0x1800fb726  mov     [rsp+78h+var_40], rax
0x1800fb72b  mov     r8d, 1
0x1800fb731  lea     rax, ?dal_function_max_uint_Step@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_max_uint_Step(sqlite3_context *,int,sqlite3_value * *)
0x1800fb738  mov     rdx, rbp
0x1800fb73b  mov     [rsp+78h+var_48], rax
0x1800fb740  mov     [rsp+78h+var_50], rdi
0x1800fb745  mov     [rsp+78h+var_58], rdi
0x1800fb74a  call    sqlite3_create_function_v2
0x1800fb74f  test    eax, eax
  ... truncated ...
```
