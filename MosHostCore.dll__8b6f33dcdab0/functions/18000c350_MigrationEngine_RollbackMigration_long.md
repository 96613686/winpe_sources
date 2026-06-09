# MigrationEngine::RollbackMigration(long)

- ea: `0x18000c350`
- end: `0x18000c412`
- name: `?RollbackMigration@MigrationEngine@@IEAAJJ@Z`
- size: `194`
- prototype: `__int64 __fastcall(MigrationEngine *__hidden this, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000b61c`
- `0x180015200`

## callees

- `0x18000b8d4`
- `0x18000c350`
- `0x180025010`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000c40a`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000c40a`
- `ZTrace_Maps!ZTraceHelper` at `0x18000c3ba`
- `ZTrace_Maps!ZTraceHelper` at `0x18000c3ba`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18000c384`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18000c384`

## string_xrefs

- `0x18000c365`: `MigrationEngine::RollbackMigration`
- `0x18000c3fb`: `MigrationEngine::RollbackMigration`

## pseudocode

```c
int __fastcall MigrationEngine::RollbackMigration(MigrationEngine *this, int a2)
{
  int v4; // ecx
  unsigned __int64 v6; // rdx
  bool v7; // zf
  int v8; // eax

  v4 = *((_DWORD *)this + 828);
  if ( ((v4 - 3) & 0xFFFFFFFD) != 0 )
    return ZTraceReportOrigination(-2147019873, "MigrationEngine::RollbackMigration", 248, this);
  ZTraceHelper(
    3,
    "MigrationEngine::RollbackMigration",
    250,
    this,
    "[Migration] Rolling back migration. Flags: %d - State: %d - Target: %ls",
    *((_DWORD *)this + 2),
    v4,
    (const wchar_t *)this + 1102);
  v7 = (*((_BYTE *)this + 8) & 1) == 0;
  *((_DWORD *)this + 837) = a2;
  if ( !v7 )
  {
    (*(void (__fastcall **)(MigrationEngine *, __int64 (__fastcall *)(MigrationEngine *, int)))(*(_QWORD *)this + 24LL))(
      this,
      MigrationEngine::DeleteNewMapData);
    return 0;
  }
  v8 = MigrationEngine::CompleteMigration(this, v6);
  if ( v8 >= 0 )
    return 0;
  return ZTraceReportPropagation(v8, "MigrationEngine::RollbackMigration", 260, this);
}

```

## disassembly

```asm
0x18000c350  mov     [rsp+arg_0], rbx
0x18000c355  push    rdi
0x18000c356  sub     rsp, 40h
0x18000c35a  mov     rbx, rcx
0x18000c35d  mov     edi, edx
0x18000c35f  mov     ecx, [rcx+0CF0h]
0x18000c365  lea     rdx, aMigrationengin_2; "MigrationEngine::RollbackMigration"
0x18000c36c  mov     r9, rbx
0x18000c36f  lea     eax, [rcx-3]
0x18000c372  test    eax, 0FFFFFFFDh
0x18000c377  jz      short loc_18000C38C
0x18000c379  mov     r8d, 0F8h
0x18000c37f  mov     ecx, 8007139Fh
0x18000c384  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x18000c38a  jmp     short loc_18000C3E4
0x18000c38c  lea     rax, [rbx+89Ch]
0x18000c393  mov     r8d, 0FAh
0x18000c399  mov     [rsp+48h+var_10], rax
0x18000c39e  mov     eax, [rbx+8]
0x18000c3a1  mov     [rsp+48h+var_18], ecx
0x18000c3a5  mov     ecx, 3
0x18000c3aa  mov     [rsp+48h+var_20], eax
0x18000c3ae  lea     rax, aMigrationRolli; "[Migration] Rolling back migration. Fla"...
0x18000c3b5  mov     [rsp+48h+var_28], rax
0x18000c3ba  call    cs:__imp_?ZTraceHelper@@YAXW4ZTraceLevel@@PEBDHPEBX1ZZ; ZTraceHelper(ZTraceLevel,char const *,int,void const *,char const *,...)
0x18000c3c0  test    byte ptr [rbx+8], 1
0x18000c3c4  mov     rcx, rbx; this
0x18000c3c7  mov     [rbx+0D14h], edi
0x18000c3cd  jz      short loc_18000C3EF
0x18000c3cf  mov     rax, [rbx]
0x18000c3d2  lea     rdx, ?DeleteNewMapData@MigrationEngine@@AEAAJXZ; MigrationEngine::DeleteNewMapData(void)
0x18000c3d9  mov     rax, [rax+18h]
0x18000c3dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3e2  xor     eax, eax
0x18000c3e4  mov     rbx, [rsp+48h+arg_0]
0x18000c3e9  add     rsp, 40h
0x18000c3ed  pop     rdi
0x18000c3ee  retn
0x18000c3ef  call    ?CompleteMigration@MigrationEngine@@AEAAJXZ; MigrationEngine::CompleteMigration(void)
0x18000c3f4  test    eax, eax
0x18000c3f6  jns     short loc_18000C3E2
0x18000c3f8  mov     r9, rbx
0x18000c3fb  lea     rdx, aMigrationengin_2; "MigrationEngine::RollbackMigration"
0x18000c402  mov     r8d, 104h
0x18000c408  mov     ecx, eax
0x18000c40a  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18000c410  jmp     short loc_18000C3E4
```
