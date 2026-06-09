# StateRepository::Database::RegisterFunctions(void)

- ea: `0x180017a88`
- end: `0x1800180c4`
- name: `?RegisterFunctions@Database@StateRepository@@QEAAJXZ`
- size: `1596`
- prototype: `__int64 __fastcall(StateRepository::Database *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180017920`
- `0x1800179d0`
- `0x180208564`

## callees

- `0x180017a88`
- `0x18001a9e0`

## import_xrefs

- `StateRepository.Core!sqlite3_create_function_v2` at `0x180017af5`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x180017b47`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x180017b81`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x180017bbf`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x180017c00`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x180017c3e`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x180017c7c`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x180017cc3`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x180017d01`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x180017d41`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x180017d81`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x180017dc0`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x180017dff`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x180017e41`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x180017e7f`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x180017ebd`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x180017efb`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x180017f39`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x180017f7b`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x180017fae`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x180017ff2`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x180018034`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x180018067`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x1800180ab`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x180017af5`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x180017b47`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x180017b81`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x180017bbf`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x180017c00`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x180017c3e`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x180017c7c`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x180017cc3`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x180017d01`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x180017d41`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x180017d81`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x180017dc0`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x180017dff`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x180017e41`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x180017e7f`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x180017ebd`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x180017efb`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x180017f39`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x180017f7b`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x180017fae`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x180017ff2`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x180018034`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x180018067`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x1800180ab`

## string_xrefs

- `0x180017aa5`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x180017d27`: `compress`
- `0x180017e25`: `compare_uint`
- `0x180017d70`: `uncompress`

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
               "changeid_next_value",
               0,
               5,
               this,
               StateRepository::Database::dal_function_changeid_next_value,
               0,
               0,
               0);
    v4 = (int)result <= 0;
    if ( (_DWORD)result )
      goto LABEL_4;
    result = sqlite3_create_function_v2(
               *(_QWORD *)this,
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
               "is_srjournal_enabled",
               0,
               2099205,
               this,
               StateRepository::Database::dal_function_is_srjournal_enabled,
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
               "sroptions",
               0,
               2099205,
               this,
               StateRepository::Database::dal_function_sroptions,
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
0x180017a88  push    rbx
0x180017a8a  push    rbp
0x180017a8b  push    rsi
0x180017a8c  push    rdi
0x180017a8d  push    r14
0x180017a8f  sub     rsp, 50h
0x180017a93  mov     rbx, rcx
0x180017a96  xor     edi, edi
0x180017a98  mov     rcx, [rcx]
0x180017a9b  test    rcx, rcx
0x180017a9e  jnz     short loc_180017AC5
0x180017aa0  mov     rcx, [rsp+78h]; this
0x180017aa5  lea     r8, aOnecoreBaseApp_370; "onecore\\base\\appmodel\\staterepositor"...
0x180017aac  mov     ebx, 8007139Fh
0x180017ab1  mov     edx, 0CA2h; void *
0x180017ab6  mov     r9d, ebx; char *
0x180017ab9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017abe  mov     eax, ebx
0x180017ac0  jmp     loc_1800180B9
0x180017ac5  mov     [rsp+78h+var_38], rdi
0x180017aca  lea     rax, ?dal_function_changeid_next_value@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_changeid_next_value(sqlite3_context *,int,sqlite3_value * *)
0x180017ad1  mov     [rsp+78h+var_40], rdi
0x180017ad6  lea     rdx, aChangeidNextVa_0; "changeid_next_value"
0x180017add  mov     [rsp+78h+var_48], rdi
0x180017ae2  mov     r9d, 5
0x180017ae8  mov     [rsp+78h+var_50], rax
0x180017aed  xor     r8d, r8d
0x180017af0  mov     [rsp+78h+var_58], rbx
0x180017af5  call    cs:__imp_sqlite3_create_function_v2
0x180017afb  test    eax, eax
0x180017afd  jz      short loc_180017B12
0x180017aff  jle     loc_1800180B9
0x180017b05  movzx   eax, ax
0x180017b08  or      eax, 87AF0000h
0x180017b0d  jmp     loc_1800180B9
0x180017b12  mov     rcx, [rbx]
0x180017b15  lea     rax, ?dal_function_execution_flags@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_execution_flags(sqlite3_context *,int,sqlite3_value * *)
0x180017b1c  mov     [rsp+78h+var_38], rdi
0x180017b21  lea     rdx, aExecutionFlags; "execution_flags"
0x180017b28  mov     [rsp+78h+var_40], rdi
0x180017b2d  mov     esi, 200805h
0x180017b32  mov     [rsp+78h+var_48], rdi
0x180017b37  mov     r9d, esi
0x180017b3a  mov     [rsp+78h+var_50], rax
0x180017b3f  xor     r8d, r8d
0x180017b42  mov     [rsp+78h+var_58], rbx
0x180017b47  call    cs:__imp_sqlite3_create_function_v2
0x180017b4d  test    eax, eax
0x180017b4f  jnz     short loc_180017AFF
0x180017b51  mov     rcx, [rbx]
0x180017b54  lea     rax, ?dal_function_is_triggers_enabled@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_is_triggers_enabled(sqlite3_context *,int,sqlite3_value * *)
0x180017b5b  mov     [rsp+78h+var_38], rdi
0x180017b60  lea     rdx, aIsTriggersEnab; "is_triggers_enabled"
0x180017b67  mov     [rsp+78h+var_40], rdi
0x180017b6c  mov     r9d, esi
0x180017b6f  mov     [rsp+78h+var_48], rdi
0x180017b74  xor     r8d, r8d
0x180017b77  mov     [rsp+78h+var_50], rax
0x180017b7c  mov     [rsp+78h+var_58], rbx
0x180017b81  call    cs:__imp_sqlite3_create_function_v2
0x180017b87  test    eax, eax
0x180017b89  jnz     loc_180017AFF
0x180017b8f  mov     rcx, [rbx]
0x180017b92  lea     rax, ?dal_function_is_srjournal_enabled@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_is_srjournal_enabled(sqlite3_context *,int,sqlite3_value * *)
0x180017b99  mov     [rsp+78h+var_38], rdi
0x180017b9e  lea     rdx, aIsSrjournalEna; "is_srjournal_enabled"
0x180017ba5  mov     [rsp+78h+var_40], rdi
0x180017baa  mov     r9d, esi
0x180017bad  mov     [rsp+78h+var_48], rdi
0x180017bb2  xor     r8d, r8d
0x180017bb5  mov     [rsp+78h+var_50], rax
0x180017bba  mov     [rsp+78h+var_58], rbx
0x180017bbf  call    cs:__imp_sqlite3_create_function_v2
0x180017bc5  test    eax, eax
0x180017bc7  jnz     loc_180017AFF
0x180017bcd  mov     rcx, [rbx]
0x180017bd0  lea     rax, ?dal_function_now@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_now(sqlite3_context *,int,sqlite3_value * *)
0x180017bd7  mov     [rsp+78h+var_38], rdi
0x180017bdc  lea     rdx, aNow; "now"
0x180017be3  mov     [rsp+78h+var_40], rdi
0x180017be8  mov     r9d, 200005h
0x180017bee  mov     [rsp+78h+var_48], rdi
0x180017bf3  xor     r8d, r8d
0x180017bf6  mov     [rsp+78h+var_50], rax
0x180017bfb  mov     [rsp+78h+var_58], rdi
0x180017c00  call    cs:__imp_sqlite3_create_function_v2
0x180017c06  test    eax, eax
0x180017c08  jnz     loc_180017AFF
0x180017c0e  mov     rcx, [rbx]
0x180017c11  lea     rax, ?dal_function_sroptions@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_sroptions(sqlite3_context *,int,sqlite3_value * *)
0x180017c18  mov     [rsp+78h+var_38], rdi
0x180017c1d  lea     rdx, aSroptions; "sroptions"
0x180017c24  mov     [rsp+78h+var_40], rdi
0x180017c29  mov     r9d, esi
0x180017c2c  mov     [rsp+78h+var_48], rdi
0x180017c31  xor     r8d, r8d
0x180017c34  mov     [rsp+78h+var_50], rax
0x180017c39  mov     [rsp+78h+var_58], rbx
0x180017c3e  call    cs:__imp_sqlite3_create_function_v2
0x180017c44  test    eax, eax
0x180017c46  jnz     loc_180017AFF
0x180017c4c  mov     rcx, [rbx]
0x180017c4f  lea     rax, ?dal_function_workid@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_workid(sqlite3_context *,int,sqlite3_value * *)
0x180017c56  mov     [rsp+78h+var_38], rdi
0x180017c5b  lea     rdx, aWorkid; "workid"
0x180017c62  mov     [rsp+78h+var_40], rdi
0x180017c67  mov     r9d, esi
0x180017c6a  mov     [rsp+78h+var_48], rdi
0x180017c6f  xor     r8d, r8d
0x180017c72  mov     [rsp+78h+var_50], rax
0x180017c77  mov     [rsp+78h+var_58], rbx
0x180017c7c  call    cs:__imp_sqlite3_create_function_v2
0x180017c82  test    eax, eax
0x180017c84  jnz     loc_180017AFF
0x180017c8a  mov     rcx, [rbx]
0x180017c8d  lea     rax, ?dal_function_startswith@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_startswith(sqlite3_context *,int,sqlite3_value * *)
0x180017c94  mov     [rsp+78h+var_38], rdi
0x180017c99  lea     r14d, [rsi-1]
0x180017c9d  mov     [rsp+78h+var_40], rdi
0x180017ca2  lea     rdx, aStartswith; "startswith"
0x180017ca9  mov     [rsp+78h+var_48], rdi
0x180017cae  mov     ebp, 2
0x180017cb3  mov     [rsp+78h+var_50], rax
0x180017cb8  mov     r9d, r14d
0x180017cbb  mov     r8d, ebp
0x180017cbe  mov     [rsp+78h+var_58], rdi
0x180017cc3  call    cs:__imp_sqlite3_create_function_v2
0x180017cc9  test    eax, eax
0x180017ccb  jnz     loc_180017AFF
0x180017cd1  mov     rcx, [rbx]
0x180017cd4  lea     rax, ?dal_function_endswith@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_endswith(sqlite3_context *,int,sqlite3_value * *)
0x180017cdb  mov     [rsp+78h+var_38], rdi
0x180017ce0  lea     rdx, aEndswith; "endswith"
0x180017ce7  mov     [rsp+78h+var_40], rdi
0x180017cec  mov     r9d, r14d
0x180017cef  mov     [rsp+78h+var_48], rdi
0x180017cf4  mov     r8d, ebp
0x180017cf7  mov     [rsp+78h+var_50], rax
0x180017cfc  mov     [rsp+78h+var_58], rdi
0x180017d01  call    cs:__imp_sqlite3_create_function_v2
0x180017d07  test    eax, eax
0x180017d09  jnz     loc_180017AFF
0x180017d0f  mov     rcx, [rbx]
0x180017d12  lea     rax, ?dal_function_compress@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_compress(sqlite3_context *,int,sqlite3_value * *)
0x180017d19  mov     [rsp+78h+var_38], rdi
0x180017d1e  lea     r9d, [rsi-4]
0x180017d22  mov     [rsp+78h+var_40], rdi
0x180017d27  lea     rdx, aCompress; "compress"
0x180017d2e  mov     [rsp+78h+var_48], rdi
0x180017d33  or      r8d, 0FFFFFFFFh
0x180017d37  mov     [rsp+78h+var_50], rax
0x180017d3c  mov     [rsp+78h+var_58], rdi
0x180017d41  call    cs:__imp_sqlite3_create_function_v2
0x180017d47  test    eax, eax
0x180017d49  jnz     loc_180017AFF
0x180017d4f  mov     rcx, [rbx]
0x180017d52  lea     rax, ?dal_function_uncompress@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_uncompress(sqlite3_context *,int,sqlite3_value * *)
0x180017d59  mov     [rsp+78h+var_38], rdi
0x180017d5e  lea     r9d, [rsi-4]
0x180017d62  mov     [rsp+78h+var_40], rdi
0x180017d67  lea     r8d, [rbp-1]
0x180017d6b  mov     [rsp+78h+var_48], rdi
0x180017d70  lea     rdx, aUncompress; "uncompress"
0x180017d77  mov     [rsp+78h+var_50], rax
0x180017d7c  mov     [rsp+78h+var_58], rdi
0x180017d81  call    cs:__imp_sqlite3_create_function_v2
0x180017d87  test    eax, eax
0x180017d89  jnz     loc_180017AFF
0x180017d8f  mov     rcx, [rbx]
0x180017d92  lea     rax, ?dal_function_hash_base32@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_hash_base32(sqlite3_context *,int,sqlite3_value * *)
0x180017d99  mov     [rsp+78h+var_38], rdi
0x180017d9e  lea     rdx, aHashBase32; "hash_base32"
0x180017da5  mov     [rsp+78h+var_40], rdi
0x180017daa  mov     r9d, r14d
0x180017dad  mov     [rsp+78h+var_48], rdi
0x180017db2  or      r8d, 0FFFFFFFFh
0x180017db6  mov     [rsp+78h+var_50], rax
0x180017dbb  mov     [rsp+78h+var_58], rdi
0x180017dc0  call    cs:__imp_sqlite3_create_function_v2
0x180017dc6  test    eax, eax
0x180017dc8  jnz     loc_180017AFF
0x180017dce  mov     rcx, [rbx]
0x180017dd1  lea     rax, ?dal_function_log@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_log(sqlite3_context *,int,sqlite3_value * *)
0x180017dd8  mov     [rsp+78h+var_38], rdi
0x180017ddd  lea     r9d, [rsi-4]
0x180017de1  mov     [rsp+78h+var_40], rdi
0x180017de6  lea     rdx, aLog; "log"
0x180017ded  mov     [rsp+78h+var_48], rdi
0x180017df2  mov     r8d, ebp
0x180017df5  mov     [rsp+78h+var_50], rax
0x180017dfa  mov     [rsp+78h+var_58], rdi
0x180017dff  call    cs:__imp_sqlite3_create_function_v2
0x180017e05  test    eax, eax
0x180017e07  jnz     loc_180017AFF
0x180017e0d  mov     rcx, [rbx]
0x180017e10  lea     rax, ?dal_function_compare_uint@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_compare_uint(sqlite3_context *,int,sqlite3_value * *)
0x180017e17  mov     [rsp+78h+var_38], rdi
0x180017e1c  lea     r14d, [rsi-5]
0x180017e20  mov     [rsp+78h+var_40], rdi
0x180017e25  lea     rdx, aCompareUint; "compare_uint"
0x180017e2c  mov     [rsp+78h+var_48], rdi
0x180017e31  mov     r9d, r14d
0x180017e34  mov     [rsp+78h+var_50], rax
0x180017e39  mov     r8d, ebp
0x180017e3c  mov     [rsp+78h+var_58], rdi
0x180017e41  call    cs:__imp_sqlite3_create_function_v2
0x180017e47  test    eax, eax
0x180017e49  jnz     loc_180017AFF
0x180017e4f  mov     rcx, [rbx]
0x180017e52  lea     rax, ?dal_function_ge_uint@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_ge_uint(sqlite3_context *,int,sqlite3_value * *)
0x180017e59  mov     [rsp+78h+var_38], rdi
0x180017e5e  lea     rdx, aGeUint; "ge_uint"
0x180017e65  mov     [rsp+78h+var_40], rdi
0x180017e6a  mov     r9d, r14d
0x180017e6d  mov     [rsp+78h+var_48], rdi
0x180017e72  mov     r8d, ebp
0x180017e75  mov     [rsp+78h+var_50], rax
0x180017e7a  mov     [rsp+78h+var_58], rdi
0x180017e7f  call    cs:__imp_sqlite3_create_function_v2
0x180017e85  test    eax, eax
0x180017e87  jnz     loc_180017AFF
0x180017e8d  mov     rcx, [rbx]
0x180017e90  lea     rax, ?dal_function_gt_uint@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_gt_uint(sqlite3_context *,int,sqlite3_value * *)
0x180017e97  mov     [rsp+78h+var_38], rdi
0x180017e9c  lea     rdx, aGtUint; "gt_uint"
0x180017ea3  mov     [rsp+78h+var_40], rdi
0x180017ea8  mov     r9d, r14d
0x180017eab  mov     [rsp+78h+var_48], rdi
0x180017eb0  mov     r8d, ebp
0x180017eb3  mov     [rsp+78h+var_50], rax
0x180017eb8  mov     [rsp+78h+var_58], rdi
0x180017ebd  call    cs:__imp_sqlite3_create_function_v2
0x180017ec3  test    eax, eax
0x180017ec5  jnz     loc_180017AFF
0x180017ecb  mov     rcx, [rbx]
0x180017ece  lea     rax, ?dal_function_le_uint@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_le_uint(sqlite3_context *,int,sqlite3_value * *)
0x180017ed5  mov     [rsp+78h+var_38], rdi
0x180017eda  lea     rdx, aLeUint; "le_uint"
0x180017ee1  mov     [rsp+78h+var_40], rdi
0x180017ee6  mov     r9d, r14d
0x180017ee9  mov     [rsp+78h+var_48], rdi
0x180017eee  mov     r8d, ebp
0x180017ef1  mov     [rsp+78h+var_50], rax
0x180017ef6  mov     [rsp+78h+var_58], rdi
0x180017efb  call    cs:__imp_sqlite3_create_function_v2
0x180017f01  test    eax, eax
0x180017f03  jnz     loc_180017AFF
0x180017f09  mov     rcx, [rbx]
0x180017f0c  lea     rax, ?dal_function_lt_uint@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_lt_uint(sqlite3_context *,int,sqlite3_value * *)
0x180017f13  mov     [rsp+78h+var_38], rdi
0x180017f18  lea     rdx, aLtUint; "lt_uint"
0x180017f1f  mov     [rsp+78h+var_40], rdi
0x180017f24  mov     r9d, r14d
0x180017f27  mov     [rsp+78h+var_48], rdi
0x180017f2c  mov     r8d, ebp
0x180017f2f  mov     [rsp+78h+var_50], rax
0x180017f34  mov     [rsp+78h+var_58], rdi
0x180017f39  call    cs:__imp_sqlite3_create_function_v2
0x180017f3f  test    eax, eax
0x180017f41  jnz     loc_180017AFF
0x180017f47  mov     rcx, [rbx]
0x180017f4a  lea     rax, ?dal_function_min_uint@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_min_uint(sqlite3_context *,int,sqlite3_value * *)
0x180017f51  mov     [rsp+78h+var_38], rdi
0x180017f56  lea     rbp, aMinUint; "min_uint"
0x180017f5d  mov     [rsp+78h+var_40], rdi
0x180017f62  mov     r9d, esi
0x180017f65  mov     [rsp+78h+var_48], rdi
0x180017f6a  or      r8d, 0FFFFFFFFh
0x180017f6e  mov     [rsp+78h+var_50], rax
0x180017f73  mov     rdx, rbp
0x180017f76  mov     [rsp+78h+var_58], rdi
0x180017f7b  call    cs:__imp_sqlite3_create_function_v2
0x180017f81  test    eax, eax
0x180017f83  jnz     loc_180017AFF
0x180017f89  mov     rcx, [rbx]
0x180017f8c  mov     r9d, esi
0x180017f8f  mov     [rsp+78h+var_38], rdi
0x180017f94  xor     r8d, r8d
0x180017f97  mov     [rsp+78h+var_40], rdi
0x180017f9c  mov     rdx, rbp
0x180017f9f  mov     [rsp+78h+var_48], rdi
0x180017fa4  mov     [rsp+78h+var_50], rdi
0x180017fa9  mov     [rsp+78h+var_58], rdi
0x180017fae  call    cs:__imp_sqlite3_create_function_v2
0x180017fb4  test    eax, eax
0x180017fb6  jnz     loc_180017AFF
0x180017fbc  mov     rcx, [rbx]
0x180017fbf  lea     rax, ?dal_function_max_uint_Finalize@Database@StateRepository@@CAXPEAUsqlite3_context@@@Z; StateRepository::Database::dal_function_max_uint_Finalize(sqlite3_context *)
0x180017fc6  mov     [rsp+78h+var_38], rdi
0x180017fcb  mov     r9d, esi
0x180017fce  mov     [rsp+78h+var_40], rax
0x180017fd3  mov     r8d, 1
0x180017fd9  lea     rax, ?dal_function_min_uint_Step@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_min_uint_Step(sqlite3_context *,int,sqlite3_value * *)
0x180017fe0  mov     rdx, rbp
0x180017fe3  mov     [rsp+78h+var_48], rax
0x180017fe8  mov     [rsp+78h+var_50], rdi
0x180017fed  mov     [rsp+78h+var_58], rdi
0x180017ff2  call    cs:__imp_sqlite3_create_function_v2
0x180017ff8  test    eax, eax
0x180017ffa  jnz     loc_180017AFF
  ... truncated ...
```
