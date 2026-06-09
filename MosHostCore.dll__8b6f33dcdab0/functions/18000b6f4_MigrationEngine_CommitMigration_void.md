# MigrationEngine::CommitMigration(void)

- ea: `0x18000b6f4`
- end: `0x18000b8cc`
- name: `?CommitMigration@MigrationEngine@@IEAAJXZ`
- size: `472`
- prototype: `__int64 __fastcall(MigrationEngine *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180015200`

## callees

- `0x180009d0c`
- `0x180009db4`
- `0x18000b6f4`
- `0x18000b8d4`
- `0x18000c1ec`
- `0x18000c8f4`
- `0x180025010`

## import_xrefs

- `MosStorage!MosStorageSetLocation` at `0x18000b7aa`
- `MosStorage!MosStorageSetLocation` at `0x18000b83d`
- `MosStorage!MosStorageSetLocation` at `0x18000b7aa`
- `MosStorage!MosStorageSetLocation` at `0x18000b83d`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18000b855`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18000b855`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000b82d`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000b82d`
- `ZTrace_Maps!ZTraceHelper` at `0x18000b773`
- `ZTrace_Maps!ZTraceHelper` at `0x18000b773`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18000b731`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18000b731`

## string_xrefs

- `0x18000b711`: `MigrationEngine::CommitMigration`
- `0x18000b75e`: `[Migration] Migration is committing. Flags: %d - State: %d - Target: %ls`

## pseudocode

```c
__int64 __fastcall MigrationEngine::CommitMigration(MigrationEngine *this)
{
  int v2; // eax
  int v3; // eax
  int v4; // r8d
  __int64 v5; // rax
  bool v6; // zf
  unsigned int v7; // edi
  int v9; // eax
  unsigned __int64 v10; // rdx
  unsigned __int8 v11; // cl
  unsigned int v12; // esi
  bool v13; // bp
  bool v14; // r14
  OfflineMapsTelemetry *v15; // rax
  unsigned int v16; // [rsp+28h] [rbp-50h]

  *((_DWORD *)this + 829) = 90;
  if ( *((_DWORD *)this + 828) != 3 )
  {
    v2 = ZTraceReportOrigination(-2147024875, "MigrationEngine::CommitMigration", 168, this);
    goto LABEL_17;
  }
  v16 = *((_DWORD *)this + 2);
  *((_DWORD *)this + 828) = 4;
  ZTraceHelper(
    3,
    "MigrationEngine::CommitMigration",
    172,
    this,
    "[Migration] Migration is committing. Flags: %d - State: %d - Target: %ls",
    v16,
    4,
    (const wchar_t *)this + 1102);
  if ( *((_BYTE *)this + 3320) && (v3 = MigrationEngine::MigrateMapDataInternal(this), v3 < 0) )
  {
    v4 = 179;
  }
  else
  {
    *((_DWORD *)this + 829) = 100;
    v3 = MosStorageSetLocation((MigrationEngine *)((char *)this + 1664));
    if ( v3 >= 0 )
    {
      v5 = *(_QWORD *)this;
      *((_DWORD *)this + 829) = 110;
      v3 = (*(__int64 (__fastcall **)(MigrationEngine *))(v5 + 8))(this);
      if ( v3 >= 0 )
      {
        v6 = (*((_BYTE *)this + 8) & 2) == 0;
        *((_DWORD *)this + 837) = 0;
        if ( v6 )
        {
          v3 = MigrationEngine::CompleteMigration(this);
          if ( v3 < 0 )
          {
            v4 = 199;
            goto LABEL_16;
          }
        }
        else
        {
          (*(void (__fastcall **)(MigrationEngine *, __int64 (__fastcall *)(MigrationEngine *__hidden)))(*(_QWORD *)this + 24LL))(
            this,
            MigrationEngine::DeleteOldMapData);
        }
        return 0;
      }
      v4 = 188;
    }
    else
    {
      v4 = 184;
    }
  }
LABEL_16:
  v2 = ZTraceReportPropagation(v3, "MigrationEngine::CommitMigration", v4, this);
LABEL_17:
  v7 = v2;
  if ( v2 < 0 )
  {
    v9 = MosStorageSetLocation((MigrationEngine *)((char *)this + 16));
    if ( v9 < 0 )
      ZTraceReportIgnore(v9, "MigrationEngine::CommitMigration", 205, this);
    v12 = *((_DWORD *)this + 829);
    v13 = *((_DWORD *)this + 417) != 0;
    *((_DWORD *)this + 828) = 5;
    v14 = *((_DWORD *)this + 5) != 0;
    if ( OfflineMapsTelemetry::IsEnabled(v11, v10) )
    {
      v15 = OfflineMapsTelemetry::Instance();
      OfflineMapsTelemetry::StorageMigrationCommitFailedMosHost_(
        v15,
        v14,
        *((_DWORD *)this + 137),
        v13,
        *((_DWORD *)this + 549),
        *((_DWORD *)this + 412),
        *((_DWORD *)this + 824),
        v7,
        v12);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18000b6f4  push    rbx
0x18000b6f6  push    rbp
0x18000b6f7  push    rsi
0x18000b6f8  push    rdi
0x18000b6f9  push    r14
0x18000b6fb  sub     rsp, 50h
0x18000b6ff  mov     rbx, rcx
0x18000b702  mov     dword ptr [rcx+0CF4h], 5Ah ; 'Z'
0x18000b70c  mov     ecx, 3
0x18000b711  lea     rsi, aMigrationengin; "MigrationEngine::CommitMigration"
0x18000b718  mov     r9, rbx
0x18000b71b  cmp     [rbx+0CF0h], ecx
0x18000b721  jz      short loc_18000B73C
0x18000b723  mov     r8d, 0A8h
0x18000b729  mov     rdx, rsi
0x18000b72c  mov     ecx, 80070015h
0x18000b731  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x18000b737  jmp     loc_18000B833
0x18000b73c  lea     rax, [rbx+89Ch]
0x18000b743  mov     edx, 4
0x18000b748  mov     qword ptr [rsp+78h+var_40], rax
0x18000b74d  mov     r8d, 0ACh
0x18000b753  mov     eax, [rbx+8]
0x18000b756  mov     [rsp+78h+var_48], edx
0x18000b75a  mov     [rsp+78h+var_50], eax
0x18000b75e  lea     rax, aMigrationMigra_1; "[Migration] Migration is committing. Fl"...
0x18000b765  mov     [rbx+0CF0h], edx
0x18000b76b  mov     rdx, rsi
0x18000b76e  mov     qword ptr [rsp+78h+var_58], rax
0x18000b773  call    cs:__imp_?ZTraceHelper@@YAXW4ZTraceLevel@@PEBDHPEBX1ZZ; ZTraceHelper(ZTraceLevel,char const *,int,void const *,char const *,...)
0x18000b779  cmp     byte ptr [rbx+0CF8h], 0
0x18000b780  jz      short loc_18000B799
0x18000b782  mov     rcx, rbx; this
0x18000b785  call    ?MigrateMapDataInternal@MigrationEngine@@AEAAJXZ; MigrationEngine::MigrateMapDataInternal(void)
0x18000b78a  test    eax, eax
0x18000b78c  jns     short loc_18000B799
0x18000b78e  mov     r8d, 0B3h
0x18000b794  jmp     loc_18000B825
0x18000b799  lea     rcx, [rbx+680h]
0x18000b7a0  mov     dword ptr [rbx+0CF4h], 64h ; 'd'
0x18000b7aa  call    cs:__imp_?MosStorageSetLocation@@YAJAEBU_STORAGE_DEVICE_DATA@@@Z; MosStorageSetLocation(_STORAGE_DEVICE_DATA const &)
0x18000b7b0  test    eax, eax
0x18000b7b2  jns     short loc_18000B7BC
0x18000b7b4  mov     r8d, 0B8h
0x18000b7ba  jmp     short loc_18000B825
0x18000b7bc  mov     rax, [rbx]
0x18000b7bf  mov     rcx, rbx
0x18000b7c2  mov     dword ptr [rbx+0CF4h], 6Eh ; 'n'
0x18000b7cc  mov     rax, [rax+8]
0x18000b7d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b7d5  test    eax, eax
0x18000b7d7  jns     short loc_18000B7E1
0x18000b7d9  mov     r8d, 0BCh
0x18000b7df  jmp     short loc_18000B825
0x18000b7e1  test    byte ptr [rbx+8], 2
0x18000b7e5  mov     rcx, rbx; this
0x18000b7e8  mov     dword ptr [rbx+0D14h], 0
0x18000b7f2  jz      short loc_18000B816
0x18000b7f4  mov     rax, [rbx]
0x18000b7f7  lea     rdx, ?DeleteOldMapData@MigrationEngine@@AEAAJXZ; MigrationEngine::DeleteOldMapData(void)
0x18000b7fe  mov     rax, [rax+18h]
0x18000b802  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b807  xor     edi, edi
0x18000b809  mov     eax, edi
0x18000b80b  add     rsp, 50h
0x18000b80f  pop     r14
0x18000b811  pop     rdi
0x18000b812  pop     rsi
0x18000b813  pop     rbp
0x18000b814  pop     rbx
0x18000b815  retn
0x18000b816  call    ?CompleteMigration@MigrationEngine@@AEAAJXZ; MigrationEngine::CompleteMigration(void)
0x18000b81b  test    eax, eax
0x18000b81d  jns     short loc_18000B807
0x18000b81f  mov     r8d, 0C7h
0x18000b825  mov     r9, rbx
0x18000b828  mov     rdx, rsi
0x18000b82b  mov     ecx, eax
0x18000b82d  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18000b833  mov     edi, eax
0x18000b835  test    eax, eax
0x18000b837  jns     short loc_18000B809
0x18000b839  lea     rcx, [rbx+10h]
0x18000b83d  call    cs:__imp_?MosStorageSetLocation@@YAJAEBU_STORAGE_DEVICE_DATA@@@Z; MosStorageSetLocation(_STORAGE_DEVICE_DATA const &)
0x18000b843  test    eax, eax
0x18000b845  jns     short loc_18000B85B
0x18000b847  mov     r9, rbx
0x18000b84a  mov     r8d, 0CDh
0x18000b850  mov     rdx, rsi
0x18000b853  mov     ecx, eax
0x18000b855  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x18000b85b  cmp     dword ptr [rbx+684h], 0
0x18000b862  mov     esi, [rbx+0CF4h]
0x18000b868  setnz   bpl
0x18000b86c  mov     dword ptr [rbx+0CF0h], 5
0x18000b876  cmp     dword ptr [rbx+14h], 0
0x18000b87a  setnz   r14b
0x18000b87e  call    ?IsEnabled@OfflineMapsTelemetry@@SA_NE_K@Z; OfflineMapsTelemetry::IsEnabled(uchar,unsigned __int64)
0x18000b883  test    al, al
0x18000b885  jz      short loc_18000B809
0x18000b887  call    ?Instance@OfflineMapsTelemetry@@KAPEAV1@XZ; OfflineMapsTelemetry::Instance(void)
0x18000b88c  mov     ecx, [rbx+0CE0h]
0x18000b892  mov     r9b, bpl; bool
0x18000b895  mov     r8d, [rbx+224h]; unsigned int
0x18000b89c  mov     dl, r14b; bool
0x18000b89f  mov     [rsp+78h+var_38], esi; unsigned int
0x18000b8a3  mov     [rsp+78h+var_40], edi; int
0x18000b8a7  mov     [rsp+78h+var_48], ecx; unsigned int
0x18000b8ab  mov     ecx, [rbx+670h]
0x18000b8b1  mov     [rsp+78h+var_50], ecx; unsigned int
0x18000b8b5  mov     ecx, [rbx+894h]
0x18000b8bb  mov     [rsp+78h+var_58], ecx; unsigned int
0x18000b8bf  mov     rcx, rax; this
0x18000b8c2  call    ?StorageMigrationCommitFailedMosHost_@OfflineMapsTelemetry@@QEAAX_NI0IIIJI@Z; OfflineMapsTelemetry::StorageMigrationCommitFailedMosHost_(bool,uint,bool,uint,uint,uint,long,uint)
0x18000b8c7  jmp     loc_18000B809
```
