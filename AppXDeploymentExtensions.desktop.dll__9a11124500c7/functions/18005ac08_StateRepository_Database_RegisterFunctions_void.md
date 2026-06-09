# StateRepository::Database::RegisterFunctions(void)

- ea: `0x18005ac08`
- end: `0x18005b2d5`
- name: `?RegisterFunctions@Database@StateRepository@@QEAAJXZ`
- size: `1741`
- prototype: `__int64 __fastcall(StateRepository::Database *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18007aeec`
- `0x180122c78`

## callees

- `0x18001adb4`
- `0x18005ac08`

## import_xrefs

- `StateRepository.Core!sqlite3_create_function_v2` at `0x18005ac75`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x18005accd`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x18005ad0d`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x18005ad51`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x18005ad98`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x18005addc`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x18005ae20`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x18005ae6d`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x18005aeb1`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x18005aef7`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x18005af3d`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x18005af82`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x18005afc7`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x18005b00f`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x18005b053`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x18005b097`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x18005b0db`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x18005b11f`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x18005b167`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x18005b1a0`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x18005b1ea`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x18005b232`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x18005b26b`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x18005b2b5`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x18005ac75`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x18005accd`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x18005ad0d`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x18005ad51`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x18005ad98`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x18005addc`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x18005ae20`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x18005ae6d`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x18005aeb1`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x18005aef7`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x18005af3d`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x18005af82`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x18005afc7`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x18005b00f`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x18005b053`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x18005b097`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x18005b0db`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x18005b11f`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x18005b167`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x18005b1a0`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x18005b1ea`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x18005b232`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x18005b26b`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x18005b2b5`

## string_xrefs

- `0x18005ac25`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x18005af2c`: `uncompress`
- `0x18005aedd`: `compress`
- `0x18005aff3`: `compare_uint`

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
0x18005ac08  push    rbx
0x18005ac0a  push    rbp
0x18005ac0b  push    rsi
0x18005ac0c  push    rdi
0x18005ac0d  push    r14
0x18005ac0f  sub     rsp, 50h
0x18005ac13  mov     rbx, rcx
0x18005ac16  xor     edi, edi
0x18005ac18  mov     rcx, [rcx]
0x18005ac1b  test    rcx, rcx
0x18005ac1e  jnz     short loc_18005AC45
0x18005ac20  mov     rcx, [rsp+78h]; this
0x18005ac25  lea     r8, aOnecoreBaseApp_69; "onecore\\base\\appmodel\\staterepositor"...
0x18005ac2c  mov     ebx, 8007139Fh
0x18005ac31  mov     edx, 0CA2h; void *
0x18005ac36  mov     r9d, ebx; char *
0x18005ac39  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ac3e  mov     eax, ebx
0x18005ac40  jmp     loc_18005B2C9
0x18005ac45  mov     [rsp+78h+var_38], rdi
0x18005ac4a  lea     rax, ?dal_function_changeid_next_value@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_changeid_next_value(sqlite3_context *,int,sqlite3_value * *)
0x18005ac51  mov     [rsp+78h+var_40], rdi
0x18005ac56  lea     rdx, aChangeidNextVa_0; "changeid_next_value"
0x18005ac5d  mov     [rsp+78h+var_48], rdi
0x18005ac62  mov     r9d, 5
0x18005ac68  mov     [rsp+78h+var_50], rax
0x18005ac6d  xor     r8d, r8d
0x18005ac70  mov     [rsp+78h+var_58], rbx
0x18005ac75  call    cs:__imp_sqlite3_create_function_v2
0x18005ac7c  nop     dword ptr [rax+rax+00h]
0x18005ac81  test    eax, eax
0x18005ac83  jz      short loc_18005AC98
0x18005ac85  jle     loc_18005B2C9
0x18005ac8b  movzx   eax, ax
0x18005ac8e  or      eax, 87AF0000h
0x18005ac93  jmp     loc_18005B2C9
0x18005ac98  mov     rcx, [rbx]
0x18005ac9b  lea     rax, ?dal_function_execution_flags@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_execution_flags(sqlite3_context *,int,sqlite3_value * *)
0x18005aca2  mov     [rsp+78h+var_38], rdi
0x18005aca7  lea     rdx, aExecutionFlags; "execution_flags"
0x18005acae  mov     [rsp+78h+var_40], rdi
0x18005acb3  mov     esi, 200805h
0x18005acb8  mov     [rsp+78h+var_48], rdi
0x18005acbd  mov     r9d, esi
0x18005acc0  mov     [rsp+78h+var_50], rax
0x18005acc5  xor     r8d, r8d
0x18005acc8  mov     [rsp+78h+var_58], rbx
0x18005accd  call    cs:__imp_sqlite3_create_function_v2
0x18005acd4  nop     dword ptr [rax+rax+00h]
0x18005acd9  test    eax, eax
0x18005acdb  jnz     short loc_18005AC85
0x18005acdd  mov     rcx, [rbx]
0x18005ace0  lea     rax, ?dal_function_is_triggers_enabled@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_is_triggers_enabled(sqlite3_context *,int,sqlite3_value * *)
0x18005ace7  mov     [rsp+78h+var_38], rdi
0x18005acec  lea     rdx, aIsTriggersEnab; "is_triggers_enabled"
0x18005acf3  mov     [rsp+78h+var_40], rdi
0x18005acf8  mov     r9d, esi
0x18005acfb  mov     [rsp+78h+var_48], rdi
0x18005ad00  xor     r8d, r8d
0x18005ad03  mov     [rsp+78h+var_50], rax
0x18005ad08  mov     [rsp+78h+var_58], rbx
0x18005ad0d  call    cs:__imp_sqlite3_create_function_v2
0x18005ad14  nop     dword ptr [rax+rax+00h]
0x18005ad19  test    eax, eax
0x18005ad1b  jnz     loc_18005AC85
0x18005ad21  mov     rcx, [rbx]
0x18005ad24  lea     rax, ?dal_function_is_srjournal_enabled@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_is_srjournal_enabled(sqlite3_context *,int,sqlite3_value * *)
0x18005ad2b  mov     [rsp+78h+var_38], rdi
0x18005ad30  lea     rdx, aIsSrjournalEna; "is_srjournal_enabled"
0x18005ad37  mov     [rsp+78h+var_40], rdi
0x18005ad3c  mov     r9d, esi
0x18005ad3f  mov     [rsp+78h+var_48], rdi
0x18005ad44  xor     r8d, r8d
0x18005ad47  mov     [rsp+78h+var_50], rax
0x18005ad4c  mov     [rsp+78h+var_58], rbx
0x18005ad51  call    cs:__imp_sqlite3_create_function_v2
0x18005ad58  nop     dword ptr [rax+rax+00h]
0x18005ad5d  test    eax, eax
0x18005ad5f  jnz     loc_18005AC85
0x18005ad65  mov     rcx, [rbx]
0x18005ad68  lea     rax, ?dal_function_now@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_now(sqlite3_context *,int,sqlite3_value * *)
0x18005ad6f  mov     [rsp+78h+var_38], rdi
0x18005ad74  lea     rdx, aNow; "now"
0x18005ad7b  mov     [rsp+78h+var_40], rdi
0x18005ad80  mov     r9d, 200005h
0x18005ad86  mov     [rsp+78h+var_48], rdi
0x18005ad8b  xor     r8d, r8d
0x18005ad8e  mov     [rsp+78h+var_50], rax
0x18005ad93  mov     [rsp+78h+var_58], rdi
0x18005ad98  call    cs:__imp_sqlite3_create_function_v2
0x18005ad9f  nop     dword ptr [rax+rax+00h]
0x18005ada4  test    eax, eax
0x18005ada6  jnz     loc_18005AC85
0x18005adac  mov     rcx, [rbx]
0x18005adaf  lea     rax, ?dal_function_sroptions@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_sroptions(sqlite3_context *,int,sqlite3_value * *)
0x18005adb6  mov     [rsp+78h+var_38], rdi
0x18005adbb  lea     rdx, aSroptions; "sroptions"
0x18005adc2  mov     [rsp+78h+var_40], rdi
0x18005adc7  mov     r9d, esi
0x18005adca  mov     [rsp+78h+var_48], rdi
0x18005adcf  xor     r8d, r8d
0x18005add2  mov     [rsp+78h+var_50], rax
0x18005add7  mov     [rsp+78h+var_58], rbx
0x18005addc  call    cs:__imp_sqlite3_create_function_v2
0x18005ade3  nop     dword ptr [rax+rax+00h]
0x18005ade8  test    eax, eax
0x18005adea  jnz     loc_18005AC85
0x18005adf0  mov     rcx, [rbx]
0x18005adf3  lea     rax, ?dal_function_workid@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_workid(sqlite3_context *,int,sqlite3_value * *)
0x18005adfa  mov     [rsp+78h+var_38], rdi
0x18005adff  lea     rdx, aWorkid; "workid"
0x18005ae06  mov     [rsp+78h+var_40], rdi
0x18005ae0b  mov     r9d, esi
0x18005ae0e  mov     [rsp+78h+var_48], rdi
0x18005ae13  xor     r8d, r8d
0x18005ae16  mov     [rsp+78h+var_50], rax
0x18005ae1b  mov     [rsp+78h+var_58], rbx
0x18005ae20  call    cs:__imp_sqlite3_create_function_v2
0x18005ae27  nop     dword ptr [rax+rax+00h]
0x18005ae2c  test    eax, eax
0x18005ae2e  jnz     loc_18005AC85
0x18005ae34  mov     rcx, [rbx]
0x18005ae37  lea     rax, ?dal_function_startswith@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_startswith(sqlite3_context *,int,sqlite3_value * *)
0x18005ae3e  mov     [rsp+78h+var_38], rdi
0x18005ae43  lea     r14d, [rsi-1]
0x18005ae47  mov     [rsp+78h+var_40], rdi
0x18005ae4c  lea     rdx, aStartswith; "startswith"
0x18005ae53  mov     [rsp+78h+var_48], rdi
0x18005ae58  mov     ebp, 2
0x18005ae5d  mov     [rsp+78h+var_50], rax
0x18005ae62  mov     r9d, r14d
0x18005ae65  mov     r8d, ebp
0x18005ae68  mov     [rsp+78h+var_58], rdi
0x18005ae6d  call    cs:__imp_sqlite3_create_function_v2
0x18005ae74  nop     dword ptr [rax+rax+00h]
0x18005ae79  test    eax, eax
0x18005ae7b  jnz     loc_18005AC85
0x18005ae81  mov     rcx, [rbx]
0x18005ae84  lea     rax, ?dal_function_endswith@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_endswith(sqlite3_context *,int,sqlite3_value * *)
0x18005ae8b  mov     [rsp+78h+var_38], rdi
0x18005ae90  lea     rdx, aEndswith; "endswith"
0x18005ae97  mov     [rsp+78h+var_40], rdi
0x18005ae9c  mov     r9d, r14d
0x18005ae9f  mov     [rsp+78h+var_48], rdi
0x18005aea4  mov     r8d, ebp
0x18005aea7  mov     [rsp+78h+var_50], rax
0x18005aeac  mov     [rsp+78h+var_58], rdi
0x18005aeb1  call    cs:__imp_sqlite3_create_function_v2
0x18005aeb8  nop     dword ptr [rax+rax+00h]
0x18005aebd  test    eax, eax
0x18005aebf  jnz     loc_18005AC85
0x18005aec5  mov     rcx, [rbx]
0x18005aec8  lea     rax, ?dal_function_compress@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_compress(sqlite3_context *,int,sqlite3_value * *)
0x18005aecf  mov     [rsp+78h+var_38], rdi
0x18005aed4  lea     r9d, [rsi-4]
0x18005aed8  mov     [rsp+78h+var_40], rdi
0x18005aedd  lea     rdx, aCompress; "compress"
0x18005aee4  mov     [rsp+78h+var_48], rdi
0x18005aee9  or      r8d, 0FFFFFFFFh
0x18005aeed  mov     [rsp+78h+var_50], rax
0x18005aef2  mov     [rsp+78h+var_58], rdi
0x18005aef7  call    cs:__imp_sqlite3_create_function_v2
0x18005aefe  nop     dword ptr [rax+rax+00h]
0x18005af03  test    eax, eax
0x18005af05  jnz     loc_18005AC85
0x18005af0b  mov     rcx, [rbx]
0x18005af0e  lea     rax, ?dal_function_uncompress@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_uncompress(sqlite3_context *,int,sqlite3_value * *)
0x18005af15  mov     [rsp+78h+var_38], rdi
0x18005af1a  lea     r9d, [rsi-4]
0x18005af1e  mov     [rsp+78h+var_40], rdi
0x18005af23  lea     r8d, [rbp-1]
0x18005af27  mov     [rsp+78h+var_48], rdi
0x18005af2c  lea     rdx, aUncompress; "uncompress"
0x18005af33  mov     [rsp+78h+var_50], rax
0x18005af38  mov     [rsp+78h+var_58], rdi
0x18005af3d  call    cs:__imp_sqlite3_create_function_v2
0x18005af44  nop     dword ptr [rax+rax+00h]
0x18005af49  test    eax, eax
0x18005af4b  jnz     loc_18005AC85
0x18005af51  mov     rcx, [rbx]
0x18005af54  lea     rax, ?dal_function_hash_base32@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_hash_base32(sqlite3_context *,int,sqlite3_value * *)
0x18005af5b  mov     [rsp+78h+var_38], rdi
0x18005af60  lea     rdx, aHashBase32; "hash_base32"
0x18005af67  mov     [rsp+78h+var_40], rdi
0x18005af6c  mov     r9d, r14d
0x18005af6f  mov     [rsp+78h+var_48], rdi
0x18005af74  or      r8d, 0FFFFFFFFh
0x18005af78  mov     [rsp+78h+var_50], rax
0x18005af7d  mov     [rsp+78h+var_58], rdi
0x18005af82  call    cs:__imp_sqlite3_create_function_v2
0x18005af89  nop     dword ptr [rax+rax+00h]
0x18005af8e  test    eax, eax
0x18005af90  jnz     loc_18005AC85
0x18005af96  mov     rcx, [rbx]
0x18005af99  lea     rax, ?dal_function_log@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_log(sqlite3_context *,int,sqlite3_value * *)
0x18005afa0  mov     [rsp+78h+var_38], rdi
0x18005afa5  lea     r9d, [rsi-4]
0x18005afa9  mov     [rsp+78h+var_40], rdi
0x18005afae  lea     rdx, aLog; "log"
0x18005afb5  mov     [rsp+78h+var_48], rdi
0x18005afba  mov     r8d, ebp
0x18005afbd  mov     [rsp+78h+var_50], rax
0x18005afc2  mov     [rsp+78h+var_58], rdi
0x18005afc7  call    cs:__imp_sqlite3_create_function_v2
0x18005afce  nop     dword ptr [rax+rax+00h]
0x18005afd3  test    eax, eax
0x18005afd5  jnz     loc_18005AC85
0x18005afdb  mov     rcx, [rbx]
0x18005afde  lea     rax, ?dal_function_compare_uint@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_compare_uint(sqlite3_context *,int,sqlite3_value * *)
0x18005afe5  mov     [rsp+78h+var_38], rdi
0x18005afea  lea     r14d, [rsi-5]
0x18005afee  mov     [rsp+78h+var_40], rdi
0x18005aff3  lea     rdx, aCompareUint; "compare_uint"
0x18005affa  mov     [rsp+78h+var_48], rdi
0x18005afff  mov     r9d, r14d
0x18005b002  mov     [rsp+78h+var_50], rax
0x18005b007  mov     r8d, ebp
0x18005b00a  mov     [rsp+78h+var_58], rdi
0x18005b00f  call    cs:__imp_sqlite3_create_function_v2
0x18005b016  nop     dword ptr [rax+rax+00h]
0x18005b01b  test    eax, eax
0x18005b01d  jnz     loc_18005AC85
0x18005b023  mov     rcx, [rbx]
0x18005b026  lea     rax, ?dal_function_ge_uint@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_ge_uint(sqlite3_context *,int,sqlite3_value * *)
0x18005b02d  mov     [rsp+78h+var_38], rdi
0x18005b032  lea     rdx, aGeUint; "ge_uint"
0x18005b039  mov     [rsp+78h+var_40], rdi
0x18005b03e  mov     r9d, r14d
0x18005b041  mov     [rsp+78h+var_48], rdi
0x18005b046  mov     r8d, ebp
0x18005b049  mov     [rsp+78h+var_50], rax
0x18005b04e  mov     [rsp+78h+var_58], rdi
0x18005b053  call    cs:__imp_sqlite3_create_function_v2
0x18005b05a  nop     dword ptr [rax+rax+00h]
0x18005b05f  test    eax, eax
0x18005b061  jnz     loc_18005AC85
0x18005b067  mov     rcx, [rbx]
0x18005b06a  lea     rax, ?dal_function_gt_uint@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_gt_uint(sqlite3_context *,int,sqlite3_value * *)
0x18005b071  mov     [rsp+78h+var_38], rdi
0x18005b076  lea     rdx, aGtUint; "gt_uint"
0x18005b07d  mov     [rsp+78h+var_40], rdi
0x18005b082  mov     r9d, r14d
0x18005b085  mov     [rsp+78h+var_48], rdi
0x18005b08a  mov     r8d, ebp
0x18005b08d  mov     [rsp+78h+var_50], rax
0x18005b092  mov     [rsp+78h+var_58], rdi
0x18005b097  call    cs:__imp_sqlite3_create_function_v2
0x18005b09e  nop     dword ptr [rax+rax+00h]
0x18005b0a3  test    eax, eax
0x18005b0a5  jnz     loc_18005AC85
0x18005b0ab  mov     rcx, [rbx]
0x18005b0ae  lea     rax, ?dal_function_le_uint@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_le_uint(sqlite3_context *,int,sqlite3_value * *)
0x18005b0b5  mov     [rsp+78h+var_38], rdi
0x18005b0ba  lea     rdx, aLeUint; "le_uint"
0x18005b0c1  mov     [rsp+78h+var_40], rdi
0x18005b0c6  mov     r9d, r14d
0x18005b0c9  mov     [rsp+78h+var_48], rdi
0x18005b0ce  mov     r8d, ebp
0x18005b0d1  mov     [rsp+78h+var_50], rax
0x18005b0d6  mov     [rsp+78h+var_58], rdi
0x18005b0db  call    cs:__imp_sqlite3_create_function_v2
0x18005b0e2  nop     dword ptr [rax+rax+00h]
0x18005b0e7  test    eax, eax
0x18005b0e9  jnz     loc_18005AC85
0x18005b0ef  mov     rcx, [rbx]
0x18005b0f2  lea     rax, ?dal_function_lt_uint@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_lt_uint(sqlite3_context *,int,sqlite3_value * *)
0x18005b0f9  mov     [rsp+78h+var_38], rdi
0x18005b0fe  lea     rdx, aLtUint; "lt_uint"
0x18005b105  mov     [rsp+78h+var_40], rdi
0x18005b10a  mov     r9d, r14d
0x18005b10d  mov     [rsp+78h+var_48], rdi
0x18005b112  mov     r8d, ebp
0x18005b115  mov     [rsp+78h+var_50], rax
0x18005b11a  mov     [rsp+78h+var_58], rdi
0x18005b11f  call    cs:__imp_sqlite3_create_function_v2
0x18005b126  nop     dword ptr [rax+rax+00h]
0x18005b12b  test    eax, eax
0x18005b12d  jnz     loc_18005AC85
0x18005b133  mov     rcx, [rbx]
0x18005b136  lea     rax, ?dal_function_min_uint@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_min_uint(sqlite3_context *,int,sqlite3_value * *)
0x18005b13d  mov     [rsp+78h+var_38], rdi
0x18005b142  lea     rbp, aMinUint; "min_uint"
0x18005b149  mov     [rsp+78h+var_40], rdi
0x18005b14e  mov     r9d, esi
0x18005b151  mov     [rsp+78h+var_48], rdi
0x18005b156  or      r8d, 0FFFFFFFFh
0x18005b15a  mov     [rsp+78h+var_50], rax
0x18005b15f  mov     rdx, rbp
0x18005b162  mov     [rsp+78h+var_58], rdi
0x18005b167  call    cs:__imp_sqlite3_create_function_v2
0x18005b16e  nop     dword ptr [rax+rax+00h]
0x18005b173  test    eax, eax
0x18005b175  jnz     loc_18005AC85
0x18005b17b  mov     rcx, [rbx]
0x18005b17e  mov     r9d, esi
0x18005b181  mov     [rsp+78h+var_38], rdi
0x18005b186  xor     r8d, r8d
0x18005b189  mov     [rsp+78h+var_40], rdi
0x18005b18e  mov     rdx, rbp
0x18005b191  mov     [rsp+78h+var_48], rdi
  ... truncated ...
```
