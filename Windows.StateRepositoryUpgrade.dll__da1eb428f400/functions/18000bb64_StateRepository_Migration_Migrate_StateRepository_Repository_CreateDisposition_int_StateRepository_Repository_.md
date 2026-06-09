# StateRepository::Migration::Migrate(StateRepository::Repository::CreateDisposition,int,StateRepository::Repository::CreateDisposition,int,long (*)(void *),void *)

- ea: `0x18000bb64`
- end: `0x18000c1eb`
- name: `?Migrate@Migration@StateRepository@@YAJW4CreateDisposition@Repository@2@H0HP6AJPEAX@Z1@Z`
- size: `1671`
- prototype: `__int64 __fastcall(int, int, int, int, int (*)(void *), void *)`
- caller_count: `1`
- callee_count: `26`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18000b6f0`

## callees

- `0x18000a3c0`
- `0x18000b81c`
- `0x18000b8e8`
- `0x18000b964`
- `0x18000ba20`
- `0x18000ba60`
- `0x18000bab4`
- `0x18000baf4`
- `0x18000bb64`
- `0x18000c1f4`
- `0x18000c2fc`
- `0x18000c3bc`
- `0x18000c444`
- `0x18000c4e0`
- `0x18000c584`
- `0x18000c61c`
- `0x18000c69c`
- `0x18000c6d4`
- `0x18000c708`
- `0x18000c984`
- `0x180016dcc`
- `0x1800182b0`
- `0x18001849c`
- `0x180018f78`
- `0x180019a44`
- `0x18002f010`

## string_xrefs

- `0x18000be30`: `Error 0x%X opening the Machine partition to record StateRepository migration patches`
- `0x18000be4f`: `RecordPatchIsApplied.Open`
- `0x18000bf61`: `Commit`
- `0x18000bfbe`: `Error 0x%X opening the Machine partition to record StateRepository schema version`
- `0x18000bfdd`: `Machine.SetSchemaVersion.Open`
- `0x18000c0ba`: `Error 0x%X opening the Deployment partition to record StateRepository schema version`
- `0x18000c0dd`: `Deployment.SetSchemaVersion.Open`
- `0x18000bbd2`: `onecore\base\appmodel\staterepository\dataaccesslayer\repository.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Migration::Migrate(int a1, int a2, int a3, int a4, int (*a5)(void *), void *a6)
{
  int v6; // r13d
  int v7; // r14d
  int v8; // r12d
  const struct _tlgProvider_t *v10; // rax
  __int64 v11; // rcx
  int v12; // eax
  StateRepository::Migration *v13; // rcx
  unsigned __int64 v14; // rsi
  unsigned int v15; // ebx
  const struct StateRepository::Migration::MigratorListEntry *MigratorList; // rdi
  StateRepository::Migration *v17; // rcx
  unsigned __int64 MigratorListCount; // rax
  unsigned __int64 v19; // rbx
  unsigned __int64 v20; // rdx
  __int64 v21; // rcx
  int v22; // eax
  __int64 v23; // rcx
  int v24; // r14d
  wil::filetime *v25; // rcx
  struct _FILETIME v26; // rcx
  const char *v27; // rdx
  StateRepository::Migration::Context *v28; // rcx
  __int64 v29; // r8
  unsigned __int64 v30; // rax
  __int64 v31; // rbx
  const struct _FILETIME *v32; // r12
  int v33; // eax
  unsigned int v34; // r12d
  __int64 v35; // rcx
  const wchar_t *v36; // r9
  int v37; // eax
  StateRepository::Migration::Context *v38; // rcx
  int IsApplied; // eax
  __int64 v40; // rcx
  int v41; // eax
  int v42; // eax
  unsigned int v43; // ebx
  int v44; // eax
  unsigned int v45; // ebx
  int v46; // eax
  __int64 v47; // rcx
  int v48; // eax
  const char *v49; // rdx
  __int64 v50; // r8
  unsigned int v51; // ebx
  __int64 v52; // rcx
  int v53; // eax
  StateRepository::Migration::Context *v54; // rcx
  unsigned int v55; // ebx
  int v56; // eax
  __int64 *v57; // rdx
  int v59; // [rsp+28h] [rbp-E0h]
  char *v60; // [rsp+30h] [rbp-D8h]
  unsigned __int64 v61; // [rsp+88h] [rbp-80h]
  int v62; // [rsp+90h] [rbp-78h]
  StateRepository::Migration::Context *v63; // [rsp+98h] [rbp-70h]
  _QWORD *v64; // [rsp+A0h] [rbp-68h] BYREF
  _DWORD v65[2]; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v66; // [rsp+B0h] [rbp-58h]
  _DWORD v67[4]; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v68; // [rsp+C8h] [rbp-40h]
  int (*v69)(void *); // [rsp+D0h] [rbp-38h]
  void *v70; // [rsp+D8h] [rbp-30h]
  _QWORD v71[16]; // [rsp+E8h] [rbp-20h] BYREF
  _BYTE v72[176]; // [rsp+168h] [rbp+60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+220h] [rbp+118h]

  v6 = a4;
  v7 = a3;
  v8 = a2;
  if ( (Microsoft_Windows_StateRepositoryEnableBits & 2) != 0 )
    McTemplateU0dddd_EventWriteTransfer(a1, a2, a1, a2, a3, a4);
  v10 = StateRepository::Tracing::Service::Provider();
  v12 = StateRepository::Initialize(v11, v10);
  v14 = 0;
  v15 = v12;
  if ( v12 >= 0 )
    v15 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8B,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\repository.cpp",
      (const char *)(unsigned int)v12,
      v59);
  v65[0] = v15;
  v65[1] = 2;
  v66 = 0;
  if ( (v15 & 0x80000000) == 0 )
  {
    v69 = a5;
    v70 = a6;
    v67[0] = a1;
    v67[1] = v8;
    v67[2] = v7;
    v67[3] = v6;
    v68 = 0;
    MigratorList = StateRepository::Migration::GetMigratorList(v13);
    MigratorListCount = StateRepository::Migration::GetMigratorListCount(v17);
    v63 = (StateRepository::Migration::Context *)MigratorListCount;
    v19 = MigratorListCount;
    v62 = 0;
    v20 = 0;
    if ( MigratorListCount )
    {
      do
      {
        v21 = 3 * v20++;
        v21 *= 2;
        *((_DWORD *)MigratorList + 2 * v21 + 9) = 0;
        *((_QWORD *)MigratorList + v21 + 5) = 0;
      }
      while ( v20 < MigratorListCount );
      v22 = a1;
      do
      {
        if ( v22 != 1
          && *((_DWORD *)MigratorList + 12 * v14 + 5) <= v8
          && v8 <= *((_DWORD *)MigratorList + 12 * v14 + 4)
          || v7 != 1 && *((_DWORD *)MigratorList + 12 * v14 + 7) <= v6 && v6 <= *((_DWORD *)MigratorList + 12 * v14 + 6) )
        {
          StateRepository::Migration::Context::ExecuteInProgressCallback((StateRepository::Migration::Context *)v67);
          v68 = *((_QWORD *)MigratorList + 6 * v14);
          if ( (Microsoft_Windows_StateRepositoryEnableBits & 2) != 0 )
            McTemplateU0z_EventWriteTransfer(v23, MigratorBefore, *((_QWORD *)MigratorList + 6 * v14));
          v24 = (*((__int64 (__fastcall **)(_DWORD *))MigratorList + 6 * v14 + 1))(v67);
          *((_DWORD *)MigratorList + 12 * v14 + 9) = v24;
          *((struct _FILETIME *)MigratorList + 6 * v14 + 5) = wil::filetime::get_system_time(v25);
          if ( v24 < 0 )
          {
            ++v62;
            if ( (Microsoft_Windows_StateRepositoryEnableBits & 0x40) != 0 )
              ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))McTemplateU0dz_EventWriteTransfer)(
                v26,
                MigratorAfterError,
                (unsigned int)v24,
                *((_QWORD *)MigratorList + 6 * v14));
          }
          else if ( (Microsoft_Windows_StateRepositoryEnableBits & 2) != 0 )
          {
            ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))McTemplateU0z_EventWriteTransfer)(
              v26,
              MigratorAfterSuccess,
              *((_QWORD *)MigratorList + 6 * v14));
          }
          v22 = a1;
          v7 = a3;
        }
        v19 = (unsigned __int64)v63;
        ++v14;
      }
      while ( v14 < (unsigned __int64)v63 );
    }
    StateRepository::Database::Database((StateRepository::Database *)v71);
    v64 = v71;
    v30 = 0;
    v61 = 0;
    if ( v19 )
    {
      v28 = v63;
      while ( 1 )
      {
        v31 = 48 * v30;
        v32 = (const struct _FILETIME *)((char *)MigratorList + 48 * v30 + 40);
        if ( !v32->dwLowDateTime && !*(_DWORD *)((char *)MigratorList + v31 + 44) )
          goto LABEL_51;
        if ( *(int *)((char *)MigratorList + v31 + 36) >= 0 )
          break;
        if ( (*((_BYTE *)MigratorList + v31 + 32) & 2) == 0 )
          goto LABEL_36;
LABEL_51:
        v61 = ++v30;
        if ( v30 >= (unsigned __int64)v28 )
        {
          v6 = a4;
          v8 = a2;
          goto LABEL_53;
        }
      }
      if ( (*((_BYTE *)MigratorList + v31 + 32) & 1) != 0 )
        goto LABEL_51;
LABEL_36:
      if ( v71[0] )
        goto LABEL_45;
      v33 = StateRepository::Migration::Context::Open(v28, 1, v71);
      v34 = v33;
      if ( v33 >= 0 )
      {
        v37 = StateRepository::Database::BeginTransaction((StateRepository::Database *)v71, &stru_180035870, a5, a6);
        v34 = v37;
        if ( v37 >= 0
          || (LODWORD(v60) = v37,
              wil::details::in1diag3::Log_HrMsg(
                retaddr,
                (void *)0x64,
                (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrate.cpp",
                (const char *)(unsigned int)v37,
                (int)"Error 0x%X in BeginTransaction recording StateRepository migration patches",
                v60),
              (Microsoft_Windows_StateRepositoryEnableBits & 0x40) == 0) )
        {
LABEL_44:
          v30 = v61;
          v32 = (const struct _FILETIME *)((char *)MigratorList + v31 + 40);
          if ( !v71[0] )
          {
LABEL_50:
            v28 = v63;
            goto LABEL_51;
          }
LABEL_45:
          if ( !StateRepository::Database::IsInAutoCommitMode((StateRepository::Database *)v71) )
          {
            IsApplied = StateRepository::Migration::Context::RecordPatchIsApplied(
                          v38,
                          (struct StateRepository::Database *)v71,
                          *(const unsigned __int16 *const *)((char *)MigratorList + v31),
                          *(_DWORD *)((char *)MigratorList + v31 + 36),
                          v32);
            if ( IsApplied < 0 && (Microsoft_Windows_StateRepositoryEnableBits & 0x40) != 0 )
              McTemplateU0dz_EventWriteTransfer(
                v40,
                MigrateError,
                (unsigned int)IsApplied,
                L"context.RecordPatchIsApplied");
          }
          v30 = v61;
          goto LABEL_50;
        }
        v36 = L"RecordPatchIsApplied.BeginTransaction";
      }
      else
      {
        LODWORD(v60) = v33;
        wil::details::in1diag3::Log_HrMsg(
          retaddr,
          (void *)0x5C,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrate.cpp",
          (const char *)(unsigned int)v33,
          (int)"Error 0x%X opening the Machine partition to record StateRepository migration patches",
          v60);
        if ( (Microsoft_Windows_StateRepositoryEnableBits & 0x40) == 0 )
          goto LABEL_44;
        v36 = L"RecordPatchIsApplied.Open";
      }
      McTemplateU0dz_EventWriteTransfer(v35, MigrateError, v34, v36);
      goto LABEL_44;
    }
LABEL_53:
    if ( v71[0] )
    {
      if ( !StateRepository::Database::IsInAutoCommitMode((StateRepository::Database *)v71) )
      {
        v41 = StateRepository::AutoTransaction::Commit((StateRepository::AutoTransaction *)&v64);
        if ( v41 < 0 && (Microsoft_Windows_StateRepositoryEnableBits & 0x40) != 0 )
          McTemplateU0dz_EventWriteTransfer(v28, MigrateError, (unsigned int)v41, L"Commit");
      }
      v64 = 0;
    }
    if ( (v8 & 0xFF00) == 0x7500 && v8 != 29952 )
    {
      if ( !v71[0] )
      {
        v42 = StateRepository::Migration::Context::Open(v28, 1, v71);
        v43 = v42;
        if ( v42 < 0 )
        {
          LODWORD(v60) = v42;
          wil::details::in1diag3::Log_HrMsg(
            retaddr,
            (void *)0xB3,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrate.cpp",
            (const char *)(unsigned int)v42,
            (int)"Error 0x%X opening the Machine partition to record StateRepository schema version",
            v60);
          if ( (Microsoft_Windows_StateRepositoryEnableBits & 0x40) != 0 )
            McTemplateU0dz_EventWriteTransfer(v28, MigrateError, v43, L"Machine.SetSchemaVersion.Open");
        }
        if ( !v71[0] )
        {
LABEL_72:
          if ( (v6 & 0xFF00) == 0x7500 && v6 != 29952 )
          {
            StateRepository::Database::Database((StateRepository::Database *)v72);
            v48 = StateRepository::Migration::Context::Open(v47, 2, v72);
            v51 = v48;
            if ( v48 >= 0 )
            {
              v53 = StateRepository::Database::SetPragma((StateRepository::Database *)v72, v49, v50);
              v55 = v53;
              if ( v53 < 0 )
              {
                LODWORD(v60) = v53;
                wil::details::in1diag3::Log_HrMsg(
                  retaddr,
                  (void *)0xD7,
                  (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrate.cpp",
                  (const char *)(unsigned int)v53,
                  (int)"Error 0x%X setting the Deployment partition StateRepository schema version",
                  v60);
                if ( (Microsoft_Windows_StateRepositoryEnableBits & 0x40) != 0 )
                  McTemplateU0dz_EventWriteTransfer(
                    v54,
                    MigrateError,
                    v55,
                    L"Deployment.SetSchemaVersion.SetSchemaVersion");
              }
              v56 = StateRepository::Migration::Context::Close(v54, (struct StateRepository::Database *)v72);
              if ( v56 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0xDA,
                  (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrate.cpp",
                  (const char *)(unsigned int)v56,
                  v59);
            }
            else
            {
              LODWORD(v60) = v48;
              wil::details::in1diag3::Log_HrMsg(
                retaddr,
                (void *)0xCF,
                (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrate.cpp",
                (const char *)(unsigned int)v48,
                (int)"Error 0x%X opening the Deployment partition to record StateRepository schema version",
                v60);
              if ( (Microsoft_Windows_StateRepositoryEnableBits & 0x40) != 0 )
                McTemplateU0dz_EventWriteTransfer(v52, MigrateError, v51, L"Deployment.SetSchemaVersion.Open");
            }
            StateRepository::Database::~Database((StateRepository::Database *)v72);
          }
          if ( v62 <= 0 )
          {
            if ( (Microsoft_Windows_StateRepositoryEnableBits & 2) != 0 )
            {
              v57 = MigrationAfterSuccess;
              goto LABEL_88;
            }
          }
          else if ( (byte_18004BB81 & 2) != 0 )
          {
            v57 = MigrationAfterError;
LABEL_88:
            McTemplateU0ddddd_EventWriteTransfer((_DWORD)v28, (_DWORD)v57, a1, v8, a3, v6, v62);
          }
          StateRepository::AutoTransaction::~AutoTransaction((StateRepository::AutoTransaction *)&v64);
          StateRepository::Database::~Database((StateRepository::Database *)v71);
          v15 = 0;
          goto LABEL_90;
        }
      }
      v44 = StateRepository::Database::SetPragma((StateRepository::Database *)v71, v27, v29);
      v45 = v44;
      if ( v44 < 0 )
      {
        LODWORD(v60) = v44;
        wil::details::in1diag3::Log_HrMsg(
          retaddr,
          (void *)0xBC,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrate.cpp",
          (const char *)(unsigned int)v44,
          (int)"Error 0x%X setting the Machine partition StateRepository schema version",
          v60);
        if ( (Microsoft_Windows_StateRepositoryEnableBits & 0x40) != 0 )
          McTemplateU0dz_EventWriteTransfer(v28, MigrateError, v45, L"Machine.SetSchemaVersion.SetSchemaVersion");
      }
    }
    if ( v71[0] )
    {
      v46 = StateRepository::Migration::Context::Close(v28, (struct StateRepository::Database *)v71);
      if ( v46 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xC3,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrate.cpp",
          (const char *)(unsigned int)v46,
          v59);
    }
    goto LABEL_72;
  }
  if ( (Microsoft_Windows_StateRepositoryEnableBits & 0x40) != 0 )
    McTemplateU0dz_EventWriteTransfer(v13, MigrateError, v15, L"DAL.Initialize");
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1B,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrate.cpp",
    (const char *)v15,
    v59);
LABEL_90:
  StateRepository::AutoRepositoryShutdownScopeExit::~AutoRepositoryShutdownScopeExit((StateRepository::AutoRepositoryShutdownScopeExit *)v65);
  return v15;
}

```

## disassembly

```asm
0x18000bb64  mov     rax, rsp
0x18000bb67  mov     [rax+20h], r9d
0x18000bb6b  mov     [rax+18h], r8d
0x18000bb6f  mov     [rax+10h], edx
0x18000bb72  mov     [rax+8], ecx
0x18000bb75  push    rbp
0x18000bb76  push    rbx
0x18000bb77  push    rsi
0x18000bb78  push    rdi
0x18000bb79  push    r12
0x18000bb7b  push    r13
0x18000bb7d  push    r14
0x18000bb7f  lea     rbp, [rax-118h]
0x18000bb86  sub     rsp, 1E0h
0x18000bb8d  test    cs:Microsoft_Windows_StateRepositoryEnableBits, 2
0x18000bb94  mov     r13d, r9d
0x18000bb97  mov     r14d, r8d
0x18000bb9a  mov     r12d, edx
0x18000bb9d  mov     edi, ecx
0x18000bb9f  jz      short loc_18000BBB6
0x18000bba1  mov     dword ptr [rsp+210h+var_1E8], r9d
0x18000bba6  mov     r9d, edx
0x18000bba9  mov     dword ptr [rsp+210h+var_1F0], r8d; int
0x18000bbae  mov     r8d, ecx
0x18000bbb1  call    McTemplateU0dddd_EventWriteTransfer
0x18000bbb6  call    ?Provider@Service@Tracing@StateRepository@@SAPEBU_tlgProvider_t@@XZ; StateRepository::Tracing::Service::Provider(void)
0x18000bbbb  mov     rdx, rax
0x18000bbbe  call    ?Initialize@StateRepository@@YAJP6AXXZPEBU_tlgProvider_t@@PEBGP6AXHPEBD@Z4444P6AXPEAX3@ZP6AX53I@ZHP6AJW4Partition@1@PEAPEAG@Z222W4InitializeFlags@1@@Z; StateRepository::Initialize(void (*)(void),_tlgProvider_t const *,ushort const *,void (*)(int,char const *),void (*)(int,char const *),void (*)(int,char const *),void (*)(int,char const *),void (*)(int,char const *),void (*)(void *,char const *),void (*)(void *,char const *,uint),int,long (*)(StateRepository::Partition,ushort * *),ushort const *,ushort const *,ushort const *,StateRepository::InitializeFlags)
0x18000bbc3  xor     esi, esi
0x18000bbc5  mov     ebx, eax
0x18000bbc7  test    eax, eax
0x18000bbc9  jns     short loc_18000BBE8
0x18000bbcb  mov     rcx, [rbp+118h]; this
0x18000bbd2  lea     r8, aOnecoreBaseApp_10; "onecore\\base\\appmodel\\staterepositor"...
0x18000bbd9  mov     r9d, eax; char *
0x18000bbdc  mov     edx, 8Bh; void *
0x18000bbe1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bbe6  jmp     short loc_18000BBEA
0x18000bbe8  mov     ebx, esi
0x18000bbea  mov     [rbp+110h+var_170], ebx
0x18000bbed  mov     [rbp+110h+var_16C], 2
0x18000bbf4  mov     [rbp+110h+var_168], rsi
0x18000bbf8  test    ebx, ebx
0x18000bbfa  jns     short loc_18000BC3B
0x18000bbfc  test    cs:Microsoft_Windows_StateRepositoryEnableBits, 40h
0x18000bc03  jz      short loc_18000BC1B
0x18000bc05  lea     r9, aDalInitialize; "DAL.Initialize"
0x18000bc0c  mov     r8d, ebx
0x18000bc0f  lea     rdx, MigrateError
0x18000bc16  call    McTemplateU0dz_EventWriteTransfer
0x18000bc1b  mov     rcx, [rbp+118h]; this
0x18000bc22  lea     r8, aOnecoreBaseApp_37; "onecore\\base\\appmodel\\staterepositor"...
0x18000bc29  mov     r9d, ebx; char *
0x18000bc2c  mov     edx, 1Bh; void *
0x18000bc31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bc36  jmp     loc_18000C1CE
0x18000bc3b  mov     rax, [rbp+110h+arg_20]
0x18000bc42  mov     [rbp+110h+var_148], rax
0x18000bc46  mov     rax, [rbp+110h+arg_28]
0x18000bc4d  mov     [rbp+110h+var_140], rax
0x18000bc51  mov     [rbp+110h+var_160], edi
0x18000bc54  mov     [rbp+110h+var_15C], r12d
0x18000bc58  mov     [rbp+110h+var_158], r14d
0x18000bc5c  mov     [rbp+110h+var_154], r13d
0x18000bc60  mov     [rbp+110h+var_150], rsi
0x18000bc64  call    ?GetMigratorList@Migration@StateRepository@@YAPEBUMigratorListEntry@12@XZ; StateRepository::Migration::GetMigratorList(void)
0x18000bc69  mov     rdi, rax
0x18000bc6c  call    ?GetMigratorListCount@Migration@StateRepository@@YA_KXZ; StateRepository::Migration::GetMigratorListCount(void)
0x18000bc71  mov     [rbp+110h+var_180], rax
0x18000bc75  mov     rbx, rax
0x18000bc78  mov     [rbp+110h+var_188], esi
0x18000bc7b  mov     rdx, rsi
0x18000bc7e  test    rax, rax
0x18000bc81  jz      loc_18000BD86
0x18000bc87  lea     rcx, [rdx+rdx*2]
0x18000bc8b  inc     rdx
0x18000bc8e  add     rcx, rcx
0x18000bc91  mov     [rdi+rcx*8+24h], esi
0x18000bc95  mov     [rdi+rcx*8+28h], rsi
0x18000bc9a  cmp     rdx, rax
0x18000bc9d  jb      short loc_18000BC87
0x18000bc9f  mov     eax, [rbp+110h+arg_0]
0x18000bca5  lea     rbx, [rsi+rsi*2]
0x18000bca9  add     rbx, rbx
0x18000bcac  cmp     eax, 1
0x18000bcaf  jz      short loc_18000BCBF
0x18000bcb1  cmp     [rdi+rbx*8+14h], r12d
0x18000bcb6  jg      short loc_18000BCBF
0x18000bcb8  cmp     r12d, [rdi+rbx*8+10h]
0x18000bcbd  jle     short loc_18000BCDF
0x18000bcbf  cmp     r14d, 1
0x18000bcc3  jz      loc_18000BD74
0x18000bcc9  cmp     [rdi+rbx*8+1Ch], r13d
0x18000bcce  jg      loc_18000BD74
0x18000bcd4  cmp     r13d, [rdi+rbx*8+18h]
0x18000bcd9  jg      loc_18000BD74
0x18000bcdf  lea     rcx, [rbp+110h+var_160]; this
0x18000bce3  call    ?ExecuteInProgressCallback@Context@Migration@StateRepository@@QEBAXXZ; StateRepository::Migration::Context::ExecuteInProgressCallback(void)
0x18000bce8  test    cs:Microsoft_Windows_StateRepositoryEnableBits, 2
0x18000bcef  mov     rax, [rdi+rbx*8]
0x18000bcf3  mov     [rbp+110h+var_150], rax
0x18000bcf7  jz      short loc_18000BD09
0x18000bcf9  mov     r8, [rdi+rbx*8]
0x18000bcfd  lea     rdx, MigratorBefore
0x18000bd04  call    McTemplateU0z_EventWriteTransfer
0x18000bd09  mov     rax, [rdi+rbx*8+8]
0x18000bd0e  lea     rcx, [rbp+110h+var_160]
0x18000bd12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd17  mov     r14d, eax
0x18000bd1a  mov     [rdi+rbx*8+24h], eax
0x18000bd1e  call    ?get_system_time@filetime@wil@@YA?AU_FILETIME@@XZ; wil::filetime::get_system_time(void)
0x18000bd23  mov     [rdi+rbx*8+28h], rax
0x18000bd28  test    r14d, r14d
0x18000bd2b  js      short loc_18000BD48
0x18000bd2d  test    cs:Microsoft_Windows_StateRepositoryEnableBits, 2
0x18000bd34  jz      short loc_18000BD67
0x18000bd36  mov     r8, [rdi+rbx*8]
0x18000bd3a  lea     rdx, MigratorAfterSuccess
0x18000bd41  call    McTemplateU0z_EventWriteTransfer
0x18000bd46  jmp     short loc_18000BD67
0x18000bd48  inc     [rbp+110h+var_188]
0x18000bd4b  test    cs:Microsoft_Windows_StateRepositoryEnableBits, 40h
0x18000bd52  jz      short loc_18000BD67
0x18000bd54  mov     r9, [rdi+rbx*8]
0x18000bd58  lea     rdx, MigratorAfterError
0x18000bd5f  mov     r8d, r14d
0x18000bd62  call    McTemplateU0dz_EventWriteTransfer
0x18000bd67  mov     eax, [rbp+110h+arg_0]
0x18000bd6d  mov     r14d, [rbp+110h+arg_10]
0x18000bd74  mov     rbx, [rbp+110h+var_180]
0x18000bd78  inc     rsi
0x18000bd7b  cmp     rsi, rbx
0x18000bd7e  jb      loc_18000BCA5
0x18000bd84  xor     esi, esi
0x18000bd86  lea     rcx, [rbp+110h+var_130]; this
0x18000bd8a  call    ??0Database@StateRepository@@QEAA@XZ; StateRepository::Database::Database(void)
0x18000bd8f  lea     rax, [rbp+110h+var_130]
0x18000bd93  mov     [rbp+110h+var_178], rax
0x18000bd97  mov     rax, rsi
0x18000bd9a  mov     [rbp+110h+var_190], rax
0x18000bd9e  lea     rsi, MigrateError
0x18000bda5  lea     r14, aOnecoreBaseApp_37; "onecore\\base\\appmodel\\staterepositor"...
0x18000bdac  test    rbx, rbx
0x18000bdaf  jz      loc_18000BF36
0x18000bdb5  mov     rcx, [rbp+110h+var_180]
0x18000bdb9  mov     r13, [rbp+110h+arg_20]
0x18000bdc0  lea     rbx, [rax+rax*2]
0x18000bdc4  shl     rbx, 4
0x18000bdc8  lea     r12, [rdi+28h]
0x18000bdcc  add     r12, rbx
0x18000bdcf  cmp     dword ptr [r12], 0
0x18000bdd4  jnz     short loc_18000BDE1
0x18000bdd6  cmp     dword ptr [rbx+rdi+2Ch], 0
0x18000bddb  jz      loc_18000BF18
0x18000bde1  cmp     dword ptr [rbx+rdi+24h], 0
0x18000bde6  jl      short loc_18000BDF4
0x18000bde8  test    byte ptr [rbx+rdi+20h], 1
0x18000bded  jz      short loc_18000BDFF
0x18000bdef  jmp     loc_18000BF18
0x18000bdf4  test    byte ptr [rbx+rdi+20h], 2
0x18000bdf9  jnz     loc_18000BF18
0x18000bdff  cmp     [rbp+110h+var_130], 0
0x18000be04  jnz     loc_18000BECD
0x18000be0a  lea     r8, [rbp+110h+var_130]
0x18000be0e  mov     edx, 1
0x18000be13  call    ?Open@Context@Migration@StateRepository@@QEBAJW4Partition@3@AEAVDatabase@3@@Z; StateRepository::Migration::Context::Open(StateRepository::Partition,StateRepository::Database &)
0x18000be18  mov     r12d, eax
0x18000be1b  test    eax, eax
0x18000be1d  jns     short loc_18000BE58
0x18000be1f  mov     rcx, [rbp+118h]; this
0x18000be26  mov     r9d, r12d; char *
0x18000be29  mov     dword ptr [rsp+210h+var_1E8], eax; char *
0x18000be2d  mov     r8, r14; unsigned int
0x18000be30  lea     rax, aError0xXOpenin; "Error 0x%X opening the Machine partitio"...
0x18000be37  mov     edx, 5Ch ; '\'; void *
0x18000be3c  mov     [rsp+210h+var_1F0], rax; int
0x18000be41  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000be46  test    cs:Microsoft_Windows_StateRepositoryEnableBits, 40h
0x18000be4d  jz      short loc_18000BEBB
0x18000be4f  lea     r9, aRecordpatchisa_0; "RecordPatchIsApplied.Open"
0x18000be56  jmp     short loc_18000BEB0
0x18000be58  mov     r9, [rbp+110h+arg_28]; void *
0x18000be5f  lea     rdx, stru_180035870; struct _GUID *
0x18000be66  mov     r8, r13; int (*)(void *)
0x18000be69  lea     rcx, [rbp+110h+var_130]; this
0x18000be6d  call    ?BeginTransaction@Database@StateRepository@@QEAAJAEBU_GUID@@P6AJPEAX@Z1@Z; StateRepository::Database::BeginTransaction(_GUID const &,long (*)(void *),void *)
0x18000be72  mov     r12d, eax
0x18000be75  test    eax, eax
0x18000be77  jns     short loc_18000BEBB
0x18000be79  mov     rcx, [rbp+118h]; this
0x18000be80  mov     r9d, r12d; char *
0x18000be83  mov     dword ptr [rsp+210h+var_1E8], eax; char *
0x18000be87  mov     r8, r14; unsigned int
0x18000be8a  lea     rax, aError0xXInBegi; "Error 0x%X in BeginTransaction recordin"...
0x18000be91  mov     edx, 64h ; 'd'; void *
0x18000be96  mov     [rsp+210h+var_1F0], rax; int
0x18000be9b  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000bea0  test    cs:Microsoft_Windows_StateRepositoryEnableBits, 40h
0x18000bea7  jz      short loc_18000BEBB
0x18000bea9  lea     r9, aRecordpatchisa; "RecordPatchIsApplied.BeginTransaction"
0x18000beb0  mov     r8d, r12d
0x18000beb3  mov     rdx, rsi
0x18000beb6  call    McTemplateU0dz_EventWriteTransfer
0x18000bebb  mov     rax, [rbp+110h+var_190]
0x18000bebf  lea     r12, [rdi+28h]
0x18000bec3  add     r12, rbx
0x18000bec6  cmp     [rbp+110h+var_130], 0
0x18000becb  jz      short loc_18000BF14
0x18000becd  lea     rcx, [rbp+110h+var_130]; this
0x18000bed1  call    ?IsInAutoCommitMode@Database@StateRepository@@QEAA_NXZ; StateRepository::Database::IsInAutoCommitMode(void)
0x18000bed6  test    al, al
0x18000bed8  jnz     short loc_18000BF10
0x18000beda  mov     r9d, [rbx+rdi+24h]; int
0x18000bedf  lea     rdx, [rbp+110h+var_130]; struct StateRepository::Database *
0x18000bee3  mov     r8, [rbx+rdi]; unsigned __int16 *
0x18000bee7  mov     [rsp+210h+var_1F0], r12; struct _FILETIME *
0x18000beec  call    ?RecordPatchIsApplied@Context@Migration@StateRepository@@QEBAJAEAVDatabase@3@QEBGJAEBU_FILETIME@@@Z; StateRepository::Migration::Context::RecordPatchIsApplied(StateRepository::Database &,ushort const * const,long,_FILETIME const &)
0x18000bef1  test    eax, eax
0x18000bef3  jns     short loc_18000BF10
0x18000bef5  test    cs:Microsoft_Windows_StateRepositoryEnableBits, 40h
0x18000befc  jz      short loc_18000BF10
0x18000befe  lea     r9, aContextRecordp; "context.RecordPatchIsApplied"
0x18000bf05  mov     r8d, eax
0x18000bf08  mov     rdx, rsi
0x18000bf0b  call    McTemplateU0dz_EventWriteTransfer
0x18000bf10  mov     rax, [rbp+110h+var_190]
0x18000bf14  mov     rcx, [rbp+110h+var_180]
0x18000bf18  inc     rax
0x18000bf1b  mov     [rbp+110h+var_190], rax
0x18000bf1f  cmp     rax, rcx
0x18000bf22  jb      loc_18000BDC0
0x18000bf28  mov     r13d, [rbp+110h+arg_18]
0x18000bf2f  mov     r12d, [rbp+110h+arg_8]
0x18000bf36  xor     edi, edi
0x18000bf38  cmp     [rbp+110h+var_130], rdi
0x18000bf3c  jz      short loc_18000BF77
0x18000bf3e  lea     rcx, [rbp+110h+var_130]; this
0x18000bf42  call    ?IsInAutoCommitMode@Database@StateRepository@@QEAA_NXZ; StateRepository::Database::IsInAutoCommitMode(void)
0x18000bf47  test    al, al
0x18000bf49  jnz     short loc_18000BF73
0x18000bf4b  lea     rcx, [rbp+110h+var_178]; this
0x18000bf4f  call    ?Commit@AutoTransaction@StateRepository@@QEAAJXZ; StateRepository::AutoTransaction::Commit(void)
0x18000bf54  test    eax, eax
0x18000bf56  jns     short loc_18000BF73
0x18000bf58  test    cs:Microsoft_Windows_StateRepositoryEnableBits, 40h
0x18000bf5f  jz      short loc_18000BF73
0x18000bf61  lea     r9, aCommit; "Commit"
0x18000bf68  mov     r8d, eax
0x18000bf6b  mov     rdx, rsi
0x18000bf6e  call    McTemplateU0dz_EventWriteTransfer
0x18000bf73  mov     [rbp+110h+var_178], rdi
0x18000bf77  mov     eax, r12d
0x18000bf7a  and     eax, 0FF00h
0x18000bf7f  cmp     eax, 7500h
0x18000bf84  jnz     loc_18000C046
0x18000bf8a  cmp     r12d, eax
0x18000bf8d  jz      loc_18000C046
0x18000bf93  cmp     [rbp+110h+var_130], rdi
0x18000bf97  jnz     short loc_18000BFF5
0x18000bf99  lea     r8, [rbp+110h+var_130]
0x18000bf9d  mov     edx, 1
0x18000bfa2  call    ?Open@Context@Migration@StateRepository@@QEBAJW4Partition@3@AEAVDatabase@3@@Z; StateRepository::Migration::Context::Open(StateRepository::Partition,StateRepository::Database &)
0x18000bfa7  mov     ebx, eax
0x18000bfa9  test    eax, eax
0x18000bfab  jns     short loc_18000BFEF
0x18000bfad  mov     rcx, [rbp+118h]; this
0x18000bfb4  mov     r9d, ebx; char *
0x18000bfb7  mov     dword ptr [rsp+210h+var_1E8], eax; char *
0x18000bfbb  mov     r8, r14; unsigned int
0x18000bfbe  lea     rax, aError0xXOpenin_1; "Error 0x%X opening the Machine partitio"...
0x18000bfc5  mov     edx, 0B3h; void *
0x18000bfca  mov     [rsp+210h+var_1F0], rax; int
0x18000bfcf  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000bfd4  test    cs:Microsoft_Windows_StateRepositoryEnableBits, 40h
0x18000bfdb  jz      short loc_18000BFEF
0x18000bfdd  lea     r9, aMachineSetsche_0; "Machine.SetSchemaVersion.Open"
0x18000bfe4  mov     r8d, ebx
0x18000bfe7  mov     rdx, rsi
0x18000bfea  call    McTemplateU0dz_EventWriteTransfer
0x18000bfef  cmp     [rbp+110h+var_130], rdi
0x18000bff3  jz      short loc_18000C070
0x18000bff5  lea     rcx, [rbp+110h+var_130]; this
0x18000bff9  call    ?SetPragma@Database@StateRepository@@QEAAJPEBD_J@Z; StateRepository::Database::SetPragma(char const *,__int64)
0x18000bffe  mov     ebx, eax
0x18000c000  test    eax, eax
0x18000c002  jns     short loc_18000C046
0x18000c004  mov     rcx, [rbp+118h]; this
0x18000c00b  mov     r9d, ebx; char *
0x18000c00e  mov     dword ptr [rsp+210h+var_1E8], eax; char *
0x18000c012  mov     r8, r14; unsigned int
0x18000c015  lea     rax, aError0xXSettin_0; "Error 0x%X setting the Machine partitio"...
0x18000c01c  mov     edx, 0BCh; void *
0x18000c021  mov     [rsp+210h+var_1F0], rax; int
0x18000c026  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000c02b  test    cs:Microsoft_Windows_StateRepositoryEnableBits, 40h
0x18000c032  jz      short loc_18000C046
0x18000c034  lea     r9, aMachineSetsche; "Machine.SetSchemaVersion.SetSchemaVersi"...
0x18000c03b  mov     r8d, ebx
0x18000c03e  mov     rdx, rsi
0x18000c041  call    McTemplateU0dz_EventWriteTransfer
  ... truncated ...
```
