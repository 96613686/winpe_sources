# StateRepository::Database::RegisterFunctions(void)

- ea: `0x1800e0620`
- end: `0x1800e0c5c`
- name: `?RegisterFunctions@Database@StateRepository@@QEAAJXZ`
- size: `1596`
- prototype: `__int64 __fastcall(StateRepository::Database *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180096c08`
- `0x1800e0598`

## callees

- `0x180098bf4`
- `0x1800e0620`

## import_xrefs

- `StateRepository.Core!sqlite3_create_function_v2` at `0x1800e068d`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x1800e06df`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x1800e0719`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x1800e0757`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x1800e0798`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x1800e07d6`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x1800e0814`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x1800e085b`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x1800e0899`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x1800e08d9`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x1800e0919`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x1800e0958`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x1800e0997`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x1800e09d9`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x1800e0a17`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x1800e0a55`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x1800e0a93`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x1800e0ad1`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x1800e0b13`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x1800e0b46`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x1800e0b8a`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x1800e0bcc`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x1800e0bff`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x1800e0c43`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x1800e068d`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x1800e06df`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x1800e0719`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x1800e0757`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x1800e0798`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x1800e07d6`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x1800e0814`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x1800e085b`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x1800e0899`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x1800e08d9`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x1800e0919`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x1800e0958`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x1800e0997`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x1800e09d9`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x1800e0a17`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x1800e0a55`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x1800e0a93`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x1800e0ad1`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x1800e0b13`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x1800e0b46`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x1800e0b8a`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x1800e0bcc`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x1800e0bff`
- `StateRepository.Core!sqlite3_create_function_v2` at `0x1800e0c43`

## string_xrefs

- `0x1800e063d`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1800e08bf`: `compress`
- `0x1800e0908`: `uncompress`
- `0x1800e09bd`: `compare_uint`

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
0x1800e0620  push    rbx
0x1800e0622  push    rbp
0x1800e0623  push    rsi
0x1800e0624  push    rdi
0x1800e0625  push    r14
0x1800e0627  sub     rsp, 50h
0x1800e062b  mov     rbx, rcx
0x1800e062e  xor     edi, edi
0x1800e0630  mov     rcx, [rcx]
0x1800e0633  test    rcx, rcx
0x1800e0636  jnz     short loc_1800E065D
0x1800e0638  mov     rcx, [rsp+78h]; this
0x1800e063d  lea     r8, aOnecoreBaseApp_92; "onecore\\base\\appmodel\\staterepositor"...
0x1800e0644  mov     ebx, 8007139Fh
0x1800e0649  mov     edx, 0CA2h; void *
0x1800e064e  mov     r9d, ebx; char *
0x1800e0651  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e0656  mov     eax, ebx
0x1800e0658  jmp     loc_1800E0C51
0x1800e065d  mov     [rsp+78h+var_38], rdi
0x1800e0662  lea     rax, ?dal_function_changeid_next_value@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_changeid_next_value(sqlite3_context *,int,sqlite3_value * *)
0x1800e0669  mov     [rsp+78h+var_40], rdi
0x1800e066e  lea     rdx, aChangeidNextVa_0; "changeid_next_value"
0x1800e0675  mov     [rsp+78h+var_48], rdi
0x1800e067a  mov     r9d, 5
0x1800e0680  mov     [rsp+78h+var_50], rax
0x1800e0685  xor     r8d, r8d
0x1800e0688  mov     [rsp+78h+var_58], rbx
0x1800e068d  call    cs:__imp_sqlite3_create_function_v2
0x1800e0693  test    eax, eax
0x1800e0695  jz      short loc_1800E06AA
0x1800e0697  jle     loc_1800E0C51
0x1800e069d  movzx   eax, ax
0x1800e06a0  or      eax, 87AF0000h
0x1800e06a5  jmp     loc_1800E0C51
0x1800e06aa  mov     rcx, [rbx]
0x1800e06ad  lea     rax, ?dal_function_execution_flags@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_execution_flags(sqlite3_context *,int,sqlite3_value * *)
0x1800e06b4  mov     [rsp+78h+var_38], rdi
0x1800e06b9  lea     rdx, aExecutionFlags; "execution_flags"
0x1800e06c0  mov     [rsp+78h+var_40], rdi
0x1800e06c5  mov     esi, 200805h
0x1800e06ca  mov     [rsp+78h+var_48], rdi
0x1800e06cf  mov     r9d, esi
0x1800e06d2  mov     [rsp+78h+var_50], rax
0x1800e06d7  xor     r8d, r8d
0x1800e06da  mov     [rsp+78h+var_58], rbx
0x1800e06df  call    cs:__imp_sqlite3_create_function_v2
0x1800e06e5  test    eax, eax
0x1800e06e7  jnz     short loc_1800E0697
0x1800e06e9  mov     rcx, [rbx]
0x1800e06ec  lea     rax, ?dal_function_is_triggers_enabled@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_is_triggers_enabled(sqlite3_context *,int,sqlite3_value * *)
0x1800e06f3  mov     [rsp+78h+var_38], rdi
0x1800e06f8  lea     rdx, aIsTriggersEnab; "is_triggers_enabled"
0x1800e06ff  mov     [rsp+78h+var_40], rdi
0x1800e0704  mov     r9d, esi
0x1800e0707  mov     [rsp+78h+var_48], rdi
0x1800e070c  xor     r8d, r8d
0x1800e070f  mov     [rsp+78h+var_50], rax
0x1800e0714  mov     [rsp+78h+var_58], rbx
0x1800e0719  call    cs:__imp_sqlite3_create_function_v2
0x1800e071f  test    eax, eax
0x1800e0721  jnz     loc_1800E0697
0x1800e0727  mov     rcx, [rbx]
0x1800e072a  lea     rax, ?dal_function_is_srjournal_enabled@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_is_srjournal_enabled(sqlite3_context *,int,sqlite3_value * *)
0x1800e0731  mov     [rsp+78h+var_38], rdi
0x1800e0736  lea     rdx, aIsSrjournalEna; "is_srjournal_enabled"
0x1800e073d  mov     [rsp+78h+var_40], rdi
0x1800e0742  mov     r9d, esi
0x1800e0745  mov     [rsp+78h+var_48], rdi
0x1800e074a  xor     r8d, r8d
0x1800e074d  mov     [rsp+78h+var_50], rax
0x1800e0752  mov     [rsp+78h+var_58], rbx
0x1800e0757  call    cs:__imp_sqlite3_create_function_v2
0x1800e075d  test    eax, eax
0x1800e075f  jnz     loc_1800E0697
0x1800e0765  mov     rcx, [rbx]
0x1800e0768  lea     rax, ?dal_function_now@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_now(sqlite3_context *,int,sqlite3_value * *)
0x1800e076f  mov     [rsp+78h+var_38], rdi
0x1800e0774  lea     rdx, aNow; "now"
0x1800e077b  mov     [rsp+78h+var_40], rdi
0x1800e0780  mov     r9d, 200005h
0x1800e0786  mov     [rsp+78h+var_48], rdi
0x1800e078b  xor     r8d, r8d
0x1800e078e  mov     [rsp+78h+var_50], rax
0x1800e0793  mov     [rsp+78h+var_58], rdi
0x1800e0798  call    cs:__imp_sqlite3_create_function_v2
0x1800e079e  test    eax, eax
0x1800e07a0  jnz     loc_1800E0697
0x1800e07a6  mov     rcx, [rbx]
0x1800e07a9  lea     rax, ?dal_function_sroptions@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_sroptions(sqlite3_context *,int,sqlite3_value * *)
0x1800e07b0  mov     [rsp+78h+var_38], rdi
0x1800e07b5  lea     rdx, aSroptions; "sroptions"
0x1800e07bc  mov     [rsp+78h+var_40], rdi
0x1800e07c1  mov     r9d, esi
0x1800e07c4  mov     [rsp+78h+var_48], rdi
0x1800e07c9  xor     r8d, r8d
0x1800e07cc  mov     [rsp+78h+var_50], rax
0x1800e07d1  mov     [rsp+78h+var_58], rbx
0x1800e07d6  call    cs:__imp_sqlite3_create_function_v2
0x1800e07dc  test    eax, eax
0x1800e07de  jnz     loc_1800E0697
0x1800e07e4  mov     rcx, [rbx]
0x1800e07e7  lea     rax, ?dal_function_workid@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_workid(sqlite3_context *,int,sqlite3_value * *)
0x1800e07ee  mov     [rsp+78h+var_38], rdi
0x1800e07f3  lea     rdx, aWorkid; "workid"
0x1800e07fa  mov     [rsp+78h+var_40], rdi
0x1800e07ff  mov     r9d, esi
0x1800e0802  mov     [rsp+78h+var_48], rdi
0x1800e0807  xor     r8d, r8d
0x1800e080a  mov     [rsp+78h+var_50], rax
0x1800e080f  mov     [rsp+78h+var_58], rbx
0x1800e0814  call    cs:__imp_sqlite3_create_function_v2
0x1800e081a  test    eax, eax
0x1800e081c  jnz     loc_1800E0697
0x1800e0822  mov     rcx, [rbx]
0x1800e0825  lea     rax, ?dal_function_startswith@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_startswith(sqlite3_context *,int,sqlite3_value * *)
0x1800e082c  mov     [rsp+78h+var_38], rdi
0x1800e0831  lea     r14d, [rsi-1]
0x1800e0835  mov     [rsp+78h+var_40], rdi
0x1800e083a  lea     rdx, aStartswith; "startswith"
0x1800e0841  mov     [rsp+78h+var_48], rdi
0x1800e0846  mov     ebp, 2
0x1800e084b  mov     [rsp+78h+var_50], rax
0x1800e0850  mov     r9d, r14d
0x1800e0853  mov     r8d, ebp
0x1800e0856  mov     [rsp+78h+var_58], rdi
0x1800e085b  call    cs:__imp_sqlite3_create_function_v2
0x1800e0861  test    eax, eax
0x1800e0863  jnz     loc_1800E0697
0x1800e0869  mov     rcx, [rbx]
0x1800e086c  lea     rax, ?dal_function_endswith@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_endswith(sqlite3_context *,int,sqlite3_value * *)
0x1800e0873  mov     [rsp+78h+var_38], rdi
0x1800e0878  lea     rdx, aEndswith; "endswith"
0x1800e087f  mov     [rsp+78h+var_40], rdi
0x1800e0884  mov     r9d, r14d
0x1800e0887  mov     [rsp+78h+var_48], rdi
0x1800e088c  mov     r8d, ebp
0x1800e088f  mov     [rsp+78h+var_50], rax
0x1800e0894  mov     [rsp+78h+var_58], rdi
0x1800e0899  call    cs:__imp_sqlite3_create_function_v2
0x1800e089f  test    eax, eax
0x1800e08a1  jnz     loc_1800E0697
0x1800e08a7  mov     rcx, [rbx]
0x1800e08aa  lea     rax, ?dal_function_compress@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_compress(sqlite3_context *,int,sqlite3_value * *)
0x1800e08b1  mov     [rsp+78h+var_38], rdi
0x1800e08b6  lea     r9d, [rsi-4]
0x1800e08ba  mov     [rsp+78h+var_40], rdi
0x1800e08bf  lea     rdx, aCompress; "compress"
0x1800e08c6  mov     [rsp+78h+var_48], rdi
0x1800e08cb  or      r8d, 0FFFFFFFFh
0x1800e08cf  mov     [rsp+78h+var_50], rax
0x1800e08d4  mov     [rsp+78h+var_58], rdi
0x1800e08d9  call    cs:__imp_sqlite3_create_function_v2
0x1800e08df  test    eax, eax
0x1800e08e1  jnz     loc_1800E0697
0x1800e08e7  mov     rcx, [rbx]
0x1800e08ea  lea     rax, ?dal_function_uncompress@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_uncompress(sqlite3_context *,int,sqlite3_value * *)
0x1800e08f1  mov     [rsp+78h+var_38], rdi
0x1800e08f6  lea     r9d, [rsi-4]
0x1800e08fa  mov     [rsp+78h+var_40], rdi
0x1800e08ff  lea     r8d, [rbp-1]
0x1800e0903  mov     [rsp+78h+var_48], rdi
0x1800e0908  lea     rdx, aUncompress; "uncompress"
0x1800e090f  mov     [rsp+78h+var_50], rax
0x1800e0914  mov     [rsp+78h+var_58], rdi
0x1800e0919  call    cs:__imp_sqlite3_create_function_v2
0x1800e091f  test    eax, eax
0x1800e0921  jnz     loc_1800E0697
0x1800e0927  mov     rcx, [rbx]
0x1800e092a  lea     rax, ?dal_function_hash_base32@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_hash_base32(sqlite3_context *,int,sqlite3_value * *)
0x1800e0931  mov     [rsp+78h+var_38], rdi
0x1800e0936  lea     rdx, aHashBase32; "hash_base32"
0x1800e093d  mov     [rsp+78h+var_40], rdi
0x1800e0942  mov     r9d, r14d
0x1800e0945  mov     [rsp+78h+var_48], rdi
0x1800e094a  or      r8d, 0FFFFFFFFh
0x1800e094e  mov     [rsp+78h+var_50], rax
0x1800e0953  mov     [rsp+78h+var_58], rdi
0x1800e0958  call    cs:__imp_sqlite3_create_function_v2
0x1800e095e  test    eax, eax
0x1800e0960  jnz     loc_1800E0697
0x1800e0966  mov     rcx, [rbx]
0x1800e0969  lea     rax, ?dal_function_log@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_log(sqlite3_context *,int,sqlite3_value * *)
0x1800e0970  mov     [rsp+78h+var_38], rdi
0x1800e0975  lea     r9d, [rsi-4]
0x1800e0979  mov     [rsp+78h+var_40], rdi
0x1800e097e  lea     rdx, aLog; "log"
0x1800e0985  mov     [rsp+78h+var_48], rdi
0x1800e098a  mov     r8d, ebp
0x1800e098d  mov     [rsp+78h+var_50], rax
0x1800e0992  mov     [rsp+78h+var_58], rdi
0x1800e0997  call    cs:__imp_sqlite3_create_function_v2
0x1800e099d  test    eax, eax
0x1800e099f  jnz     loc_1800E0697
0x1800e09a5  mov     rcx, [rbx]
0x1800e09a8  lea     rax, ?dal_function_compare_uint@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_compare_uint(sqlite3_context *,int,sqlite3_value * *)
0x1800e09af  mov     [rsp+78h+var_38], rdi
0x1800e09b4  lea     r14d, [rsi-5]
0x1800e09b8  mov     [rsp+78h+var_40], rdi
0x1800e09bd  lea     rdx, aCompareUint; "compare_uint"
0x1800e09c4  mov     [rsp+78h+var_48], rdi
0x1800e09c9  mov     r9d, r14d
0x1800e09cc  mov     [rsp+78h+var_50], rax
0x1800e09d1  mov     r8d, ebp
0x1800e09d4  mov     [rsp+78h+var_58], rdi
0x1800e09d9  call    cs:__imp_sqlite3_create_function_v2
0x1800e09df  test    eax, eax
0x1800e09e1  jnz     loc_1800E0697
0x1800e09e7  mov     rcx, [rbx]
0x1800e09ea  lea     rax, ?dal_function_ge_uint@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_ge_uint(sqlite3_context *,int,sqlite3_value * *)
0x1800e09f1  mov     [rsp+78h+var_38], rdi
0x1800e09f6  lea     rdx, aGeUint; "ge_uint"
0x1800e09fd  mov     [rsp+78h+var_40], rdi
0x1800e0a02  mov     r9d, r14d
0x1800e0a05  mov     [rsp+78h+var_48], rdi
0x1800e0a0a  mov     r8d, ebp
0x1800e0a0d  mov     [rsp+78h+var_50], rax
0x1800e0a12  mov     [rsp+78h+var_58], rdi
0x1800e0a17  call    cs:__imp_sqlite3_create_function_v2
0x1800e0a1d  test    eax, eax
0x1800e0a1f  jnz     loc_1800E0697
0x1800e0a25  mov     rcx, [rbx]
0x1800e0a28  lea     rax, ?dal_function_gt_uint@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_gt_uint(sqlite3_context *,int,sqlite3_value * *)
0x1800e0a2f  mov     [rsp+78h+var_38], rdi
0x1800e0a34  lea     rdx, aGtUint; "gt_uint"
0x1800e0a3b  mov     [rsp+78h+var_40], rdi
0x1800e0a40  mov     r9d, r14d
0x1800e0a43  mov     [rsp+78h+var_48], rdi
0x1800e0a48  mov     r8d, ebp
0x1800e0a4b  mov     [rsp+78h+var_50], rax
0x1800e0a50  mov     [rsp+78h+var_58], rdi
0x1800e0a55  call    cs:__imp_sqlite3_create_function_v2
0x1800e0a5b  test    eax, eax
0x1800e0a5d  jnz     loc_1800E0697
0x1800e0a63  mov     rcx, [rbx]
0x1800e0a66  lea     rax, ?dal_function_le_uint@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_le_uint(sqlite3_context *,int,sqlite3_value * *)
0x1800e0a6d  mov     [rsp+78h+var_38], rdi
0x1800e0a72  lea     rdx, aLeUint; "le_uint"
0x1800e0a79  mov     [rsp+78h+var_40], rdi
0x1800e0a7e  mov     r9d, r14d
0x1800e0a81  mov     [rsp+78h+var_48], rdi
0x1800e0a86  mov     r8d, ebp
0x1800e0a89  mov     [rsp+78h+var_50], rax
0x1800e0a8e  mov     [rsp+78h+var_58], rdi
0x1800e0a93  call    cs:__imp_sqlite3_create_function_v2
0x1800e0a99  test    eax, eax
0x1800e0a9b  jnz     loc_1800E0697
0x1800e0aa1  mov     rcx, [rbx]
0x1800e0aa4  lea     rax, ?dal_function_lt_uint@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_lt_uint(sqlite3_context *,int,sqlite3_value * *)
0x1800e0aab  mov     [rsp+78h+var_38], rdi
0x1800e0ab0  lea     rdx, aLtUint; "lt_uint"
0x1800e0ab7  mov     [rsp+78h+var_40], rdi
0x1800e0abc  mov     r9d, r14d
0x1800e0abf  mov     [rsp+78h+var_48], rdi
0x1800e0ac4  mov     r8d, ebp
0x1800e0ac7  mov     [rsp+78h+var_50], rax
0x1800e0acc  mov     [rsp+78h+var_58], rdi
0x1800e0ad1  call    cs:__imp_sqlite3_create_function_v2
0x1800e0ad7  test    eax, eax
0x1800e0ad9  jnz     loc_1800E0697
0x1800e0adf  mov     rcx, [rbx]
0x1800e0ae2  lea     rax, ?dal_function_min_uint@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_min_uint(sqlite3_context *,int,sqlite3_value * *)
0x1800e0ae9  mov     [rsp+78h+var_38], rdi
0x1800e0aee  lea     rbp, aMinUint; "min_uint"
0x1800e0af5  mov     [rsp+78h+var_40], rdi
0x1800e0afa  mov     r9d, esi
0x1800e0afd  mov     [rsp+78h+var_48], rdi
0x1800e0b02  or      r8d, 0FFFFFFFFh
0x1800e0b06  mov     [rsp+78h+var_50], rax
0x1800e0b0b  mov     rdx, rbp
0x1800e0b0e  mov     [rsp+78h+var_58], rdi
0x1800e0b13  call    cs:__imp_sqlite3_create_function_v2
0x1800e0b19  test    eax, eax
0x1800e0b1b  jnz     loc_1800E0697
0x1800e0b21  mov     rcx, [rbx]
0x1800e0b24  mov     r9d, esi
0x1800e0b27  mov     [rsp+78h+var_38], rdi
0x1800e0b2c  xor     r8d, r8d
0x1800e0b2f  mov     [rsp+78h+var_40], rdi
0x1800e0b34  mov     rdx, rbp
0x1800e0b37  mov     [rsp+78h+var_48], rdi
0x1800e0b3c  mov     [rsp+78h+var_50], rdi
0x1800e0b41  mov     [rsp+78h+var_58], rdi
0x1800e0b46  call    cs:__imp_sqlite3_create_function_v2
0x1800e0b4c  test    eax, eax
0x1800e0b4e  jnz     loc_1800E0697
0x1800e0b54  mov     rcx, [rbx]
0x1800e0b57  lea     rax, ?dal_function_max_uint_Finalize@Database@StateRepository@@CAXPEAUsqlite3_context@@@Z; StateRepository::Database::dal_function_max_uint_Finalize(sqlite3_context *)
0x1800e0b5e  mov     [rsp+78h+var_38], rdi
0x1800e0b63  mov     r9d, esi
0x1800e0b66  mov     [rsp+78h+var_40], rax
0x1800e0b6b  mov     r8d, 1
0x1800e0b71  lea     rax, ?dal_function_min_uint_Step@Database@StateRepository@@CAXPEAUsqlite3_context@@HPEAPEAUsqlite3_value@@@Z; StateRepository::Database::dal_function_min_uint_Step(sqlite3_context *,int,sqlite3_value * *)
0x1800e0b78  mov     rdx, rbp
0x1800e0b7b  mov     [rsp+78h+var_48], rax
0x1800e0b80  mov     [rsp+78h+var_50], rdi
0x1800e0b85  mov     [rsp+78h+var_58], rdi
0x1800e0b8a  call    cs:__imp_sqlite3_create_function_v2
0x1800e0b90  test    eax, eax
0x1800e0b92  jnz     loc_1800E0697
  ... truncated ...
```
