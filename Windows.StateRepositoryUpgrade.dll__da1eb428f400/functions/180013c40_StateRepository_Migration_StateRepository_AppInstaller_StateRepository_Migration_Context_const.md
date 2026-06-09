# StateRepository::Migration::StateRepository_AppInstaller(StateRepository::Migration::Context const &)

- ea: `0x180013c40`
- end: `0x1800141e7`
- name: `?StateRepository_AppInstaller@Migration@StateRepository@@YAJAEBVContext@12@@Z`
- size: `1447`
- prototype: `__int64 __fastcall(StateRepository::Migration *__hidden this, const struct StateRepository::Migration::Context *)`
- caller_count: `0`
- callee_count: `26`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x18000a3c0`
- `0x18000b81c`
- `0x18000b964`
- `0x18000ba20`
- `0x18000ba60`
- `0x18000bab4`
- `0x18000c1f4`
- `0x180013154`
- `0x180013244`
- `0x180013b98`
- `0x180013bc0`
- `0x180013c40`
- `0x1800182b0`
- `0x180018310`
- `0x18001849c`
- `0x180018e80`
- `0x18001b4d8`
- `0x18001b5a8`
- `0x1800224dc`
- `0x1800251a0`
- `0x180025840`
- `0x1800258d4`
- `0x180025994`
- `0x180025fb4`
- `0x180026080`
- `0x18002a08c`

## string_xrefs

- `0x180013cad`: `onecore\base\appmodel\staterepository\upgrade\lib\migrator-staterepository.appinstaller.cpp`
- `0x180013d50`: `onecore\base\appmodel\staterepository\upgrade\lib\migrator-staterepository.appinstaller.cpp`
- `0x180013dbc`: `onecore\base\appmodel\staterepository\upgrade\lib\migrator-staterepository.appinstaller.cpp`
- `0x180013e1f`: `onecore\base\appmodel\staterepository\upgrade\lib\migrator-staterepository.appinstaller.cpp`
- `0x180013fbc`: `onecore\base\appmodel\staterepository\upgrade\lib\migrator-staterepository.appinstaller.cpp`
- `0x180013fed`: `onecore\base\appmodel\staterepository\upgrade\lib\migrator-staterepository.appinstaller.cpp`
- `0x180014069`: `onecore\base\appmodel\staterepository\upgrade\lib\migrator-staterepository.appinstaller.cpp`
- `0x180014046`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-packageappinstaller.cpp`
- `0x18001402d`: `SELECT _PackageAppInstallerID, _Revision, _WorkId, Package, AppInstaller, _Dictionary FROM PackageAppInstaller WHERE _WorkId=0;`
- `0x18001401f`: `SELECT _PackageAppInstallerID, _Revision, _WorkId, Package, AppInstaller, _Dictionary FROM PackageAppInstaller WHERE (_WorkId=0 OR _WorkId=?);`
- `0x180013f9e`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-appinstaller.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Migration::StateRepository_AppInstaller(
        StateRepository::Migration *this,
        const struct StateRepository::Migration::Context *a2)
{
  __int64 v3; // rcx
  int v4; // eax
  __int64 v5; // rcx
  unsigned int v6; // ebx
  __int64 v7; // rdx
  const char *v8; // rdx
  const char *Filename; // rax
  const char *v10; // r8
  int v11; // eax
  __int64 v12; // rdx
  int HighestVersionPackagesPerFamilyByPackageTypeAndInPackageAppInstaller; // eax
  int Next; // eax
  int v15; // eax
  int v16; // eax
  unsigned __int64 v17; // r9
  __int64 v18; // rdx
  __int64 v19; // rdx
  __int64 v20; // rdx
  char *v21; // rcx
  int v22; // eax
  unsigned __int64 v23; // r9
  __int64 v24; // rdx
  int v25; // eax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  int v29; // eax
  StateRepository::Migration::Context *v30; // rcx
  int v31; // eax
  StateRepository::Migration::Context *v32; // rcx
  int v33; // eax
  struct StateRepository::Statement *v35; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE *v36; // [rsp+28h] [rbp-D8h] BYREF
  char v37[8]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v38; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v39[2]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v40[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v41; // [rsp+60h] [rbp-A0h]
  __int64 v42[2]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v43; // [rsp+80h] [rbp-80h]
  _QWORD v44[2]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v45; // [rsp+A0h] [rbp-60h]
  __int64 v46; // [rsp+B0h] [rbp-50h]
  __int64 v47; // [rsp+B8h] [rbp-48h]
  __int64 v48; // [rsp+C0h] [rbp-40h]
  __int64 v49; // [rsp+C8h] [rbp-38h]
  __int64 v50; // [rsp+D0h] [rbp-30h]
  __int64 v51; // [rsp+D8h] [rbp-28h]
  __int128 v52; // [rsp+E0h] [rbp-20h]
  int v53[32]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v54[34]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v55[144]; // [rsp+280h] [rbp+180h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+218h]
  bool v57; // [rsp+328h] [rbp+228h] BYREF
  bool v58; // [rsp+330h] [rbp+230h] BYREF
  __int64 v59; // [rsp+338h] [rbp+238h] BYREF

  StateRepository::Database::Database((StateRepository::Database *)v55);
  StateRepository::Database::Database((StateRepository::Database *)v53);
  v4 = StateRepository::Migration::Context::Open(v3, 1, v55);
  v6 = v4;
  if ( v4 < 0 )
  {
    v7 = 17;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-staterepository.appinstaller.cpp",
      (const char *)(unsigned int)v4,
      (int)v35);
    goto LABEL_59;
  }
  v4 = StateRepository::Migration::Context::Open(v5, 2, v53);
  v6 = v4;
  if ( v4 < 0 )
  {
    v7 = 18;
    goto LABEL_5;
  }
  StateRepository::Migration::Context::ExecuteInProgressCallback(this);
  v4 = StateRepository::Database::BeginTransaction(
         (StateRepository::Database *)v55,
         &stru_18003C440,
         *((int (**)(void *))this + 3),
         *((void **)this + 4));
  v6 = v4;
  if ( v4 < 0 )
  {
    v7 = 22;
    goto LABEL_5;
  }
  v4 = StateRepository::Database::BeginTransaction(
         (StateRepository::Database *)v53,
         &stru_18003C440,
         *((int (**)(void *))this + 3),
         *((void **)this + 4));
  v6 = v4;
  if ( v4 < 0 )
  {
    v7 = 23;
    goto LABEL_5;
  }
  v36 = v55;
  v35 = (struct StateRepository::Statement *)v53;
  Filename = StateRepository::Database::GetFilename((StateRepository::Database *)v53, v8);
  v11 = StateRepository::Database::AttachDatabase((StateRepository::Database *)v55, Filename, v10);
  v6 = v11;
  if ( v11 >= 0 )
  {
    v59 = 0;
    v39[0] = v55;
    v39[1] = "Deployment";
    HighestVersionPackagesPerFamilyByPackageTypeAndInPackageAppInstaller = StateRepository::Entity::Package::FindHighestVersionPackagesPerFamilyByPackageTypeAndInPackageAppInstaller(
                                                                             v55,
                                                                             v12,
                                                                             &v59);
    v6 = HighestVersionPackagesPerFamilyByPackageTypeAndInPackageAppInstaller;
    if ( HighestVersionPackagesPerFamilyByPackageTypeAndInPackageAppInstaller >= 0 )
    {
      StateRepository::Entity::Package::Package((StateRepository::Entity::Package *)v54);
      v57 = 0;
      Next = StateRepository::Entity::Package::FindNext(
               (struct StateRepository::Statement *)&v59,
               (struct StateRepository::Entity::Package *)v54,
               &v57);
      v6 = Next;
      if ( Next >= 0 )
      {
        while ( 1 )
        {
          v41 = 0;
          v43 = 0;
          *(_OWORD *)v42 = 0;
          v40[0] = 0;
          v40[1] = 0;
          if ( !v57 )
            break;
          v38 = 0;
          v58 = 0;
          v15 = StateRepository::Entity::PackageAppInstaller::FindByPackage(
                  (struct StateRepository::Database *)v53,
                  v54[0],
                  (struct StateRepository::Statement *)&v38);
          v6 = v15;
          if ( v15 < 0 )
          {
            v20 = 46;
            goto LABEL_37;
          }
          v15 = StateRepository::Entity::PackageAppInstaller::FindNext(
                  (struct StateRepository::Statement *)&v38,
                  (struct StateRepository::Entity::PackageAppInstaller *)v40,
                  &v58);
          v6 = v15;
          if ( v15 < 0 )
          {
            v20 = 47;
LABEL_37:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v20,
              (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-staterepository.appinstaller.cpp",
              (const char *)(unsigned int)v15,
              (int)v35);
            goto LABEL_38;
          }
          if ( v58 )
          {
            v44[0] = 0;
            v45 = 0;
            v48 = 0;
            v50 = 0;
            v52 = 0;
            v44[1] = 0;
            v46 = 0;
            v47 = 0;
            v49 = 0;
            v51 = 0;
            v58 = 0;
            v6 = StateRepository::Entity::AppInstaller::TryGet(
                   (struct StateRepository::Database *)v53,
                   v42[0],
                   (struct StateRepository::Entity::AppInstaller *)v44,
                   &v58);
            if ( (v6 & 0x80000000) != 0 )
            {
              v19 = 358;
              goto LABEL_32;
            }
            if ( !v58 )
            {
              v6 = -2147023728;
              v19 = 359;
LABEL_32:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v19,
                (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-appinstaller.cpp",
                (const char *)v6,
                (int)v35);
              v17 = v6;
              v18 = 53;
LABEL_33:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v18,
                (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-staterepository.appinstaller.cpp",
                (const char *)v17,
                (int)v35);
              StateRepository::Entity::AppInstaller::~AppInstaller((StateRepository::Entity::AppInstaller *)v44);
LABEL_38:
              StateRepository::Blob::Reset((StateRepository::Blob *)&v42[1]);
              v21 = (char *)&v38;
LABEL_39:
              StateRepository::Statement::~Statement((StateRepository::Statement *)v21);
              goto LABEL_18;
            }
            *(_QWORD *)&v45 = v54[3];
            v16 = StateRepository::Entity::AppInstaller::Update(v44, v53);
            v6 = v16;
            if ( v16 < 0 )
            {
              v17 = (unsigned int)v16;
              v18 = 55;
              goto LABEL_33;
            }
            StateRepository::Entity::AppInstaller::~AppInstaller((StateRepository::Entity::AppInstaller *)v44);
          }
          v15 = StateRepository::Entity::Package::FindNext(
                  (struct StateRepository::Statement *)&v59,
                  (struct StateRepository::Entity::Package *)v54,
                  &v57);
          v6 = v15;
          if ( v15 < 0 )
          {
            v20 = 58;
            goto LABEL_37;
          }
          StateRepository::Blob::Reset((StateRepository::Blob *)&v42[1]);
          StateRepository::Statement::~Statement((StateRepository::Statement *)&v38);
        }
        *(_QWORD *)v37 = 0;
        v57 = 0;
        v22 = StateRepository::StatementExecution::PrepareAndBindAndFind(
                (StateRepository::StatementExecution *)v53,
                (struct StateRepository::Database *)"SELECT _PackageAppInstallerID, _Revision, _WorkId, Package, AppInsta"
                                                    "ller, _Dictionary FROM PackageAppInstaller WHERE _WorkId=0;",
                "SELECT _PackageAppInstallerID, _Revision, _WorkId, Package, AppInstaller, _Dictionary FROM PackageAppIns"
                "taller WHERE (_WorkId=0 OR _WorkId=?);",
                v37,
                v35);
        v6 = v22;
        if ( v22 >= 0 )
        {
          v25 = StateRepository::Entity::PackageAppInstaller::FindNext(
                  (struct StateRepository::Statement *)v37,
                  (struct StateRepository::Entity::PackageAppInstaller *)v40,
                  &v57);
          v6 = v25;
          if ( v25 >= 0 )
          {
            while ( v57 )
            {
              v26 = StateRepository::Entity::PackageAppInstaller::Delete(v53, v40[0]);
              v6 = v26;
              if ( v26 < 0 )
              {
                v23 = (unsigned int)v26;
                v24 = 69;
                goto LABEL_42;
              }
              v27 = StateRepository::Entity::PackageAppInstaller::FindNext(
                      (struct StateRepository::Statement *)v37,
                      (struct StateRepository::Entity::PackageAppInstaller *)v40,
                      &v57);
              v6 = v27;
              if ( v27 < 0 )
              {
                v23 = (unsigned int)v27;
                v24 = 70;
                goto LABEL_42;
              }
            }
            v28 = StateRepository::AutoTransaction::Commit((StateRepository::AutoTransaction *)&v36);
            v6 = v28;
            if ( v28 >= 0 )
            {
              v29 = StateRepository::AutoTransaction::Commit((StateRepository::AutoTransaction *)&v35);
              v6 = v29;
              if ( v29 >= 0 )
              {
                v31 = StateRepository::Migration::Context::Close(v30, (struct StateRepository::Database *)v55);
                v6 = v31;
                if ( v31 >= 0 )
                {
                  v33 = StateRepository::Migration::Context::Close(v32, (struct StateRepository::Database *)v53);
                  v6 = v33;
                  if ( v33 >= 0 )
                  {
                    StateRepository::Blob::Reset((StateRepository::Blob *)&v42[1]);
                    StateRepository::Statement::~Statement((StateRepository::Statement *)v37);
                    StateRepository::Entity::Package::~Package((StateRepository::Entity::Package *)v54);
                    StateRepository::Statement::~Statement((StateRepository::Statement *)&v59);
                    StateRepository::AutoDetachDatabase::~AutoDetachDatabase((StateRepository::AutoDetachDatabase *)v39);
                    StateRepository::AutoTransaction::~AutoTransaction((StateRepository::AutoTransaction *)&v35);
                    StateRepository::AutoTransaction::~AutoTransaction((StateRepository::AutoTransaction *)&v36);
                    v6 = 0;
                    goto LABEL_59;
                  }
                  v23 = (unsigned int)v33;
                  v24 = 76;
                }
                else
                {
                  v23 = (unsigned int)v31;
                  v24 = 75;
                }
              }
              else
              {
                v23 = (unsigned int)v29;
                v24 = 74;
              }
            }
            else
            {
              v23 = (unsigned int)v28;
              v24 = 73;
            }
          }
          else
          {
            v23 = (unsigned int)v25;
            v24 = 66;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x15F,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-packageappinstaller.cpp",
            (const char *)(unsigned int)v22,
            (int)v35);
          v23 = v6;
          v24 = 65;
        }
LABEL_42:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v24,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-staterepository.appinstaller.cpp",
          (const char *)v23,
          (int)v35);
        StateRepository::Blob::Reset((StateRepository::Blob *)&v42[1]);
        v21 = v37;
        goto LABEL_39;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x26,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-staterepository.appinstaller.cpp",
        (const char *)(unsigned int)Next,
        (int)v35);
LABEL_18:
      StateRepository::Entity::Package::~Package((StateRepository::Entity::Package *)v54);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x21,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-staterepository.appinstaller.cpp",
        (const char *)(unsigned int)HighestVersionPackagesPerFamilyByPackageTypeAndInPackageAppInstaller,
        (int)v35);
    }
    StateRepository::Statement::~Statement((StateRepository::Statement *)&v59);
    StateRepository::AutoDetachDatabase::~AutoDetachDatabase((StateRepository::AutoDetachDatabase *)v39);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1D,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-staterepository.appinstaller.cpp",
      (const char *)(unsigned int)v11,
      (int)v35);
  }
  StateRepository::AutoTransaction::~AutoTransaction((StateRepository::AutoTransaction *)&v35);
  StateRepository::AutoTransaction::~AutoTransaction((StateRepository::AutoTransaction *)&v36);
LABEL_59:
  StateRepository::Database::~Database((StateRepository::Database *)v53);
  StateRepository::Database::~Database((StateRepository::Database *)v55);
  return v6;
}

```

## disassembly

```asm
0x180013c40  mov     [rsp-8+arg_0], rbx
0x180013c45  push    rbp
0x180013c46  push    rsi
0x180013c47  push    rdi
0x180013c48  lea     rbp, [rsp-200h]
0x180013c50  sub     rsp, 300h
0x180013c57  mov     rdi, rcx
0x180013c5a  lea     rcx, [rbp+210h+var_90]; this
0x180013c61  call    ??0Database@StateRepository@@QEAA@XZ; StateRepository::Database::Database(void)
0x180013c66  lea     rcx, [rbp+210h+var_220]; this
0x180013c6a  call    ??0Database@StateRepository@@QEAA@XZ; StateRepository::Database::Database(void)
0x180013c6f  lea     r8, [rbp+210h+var_90]
0x180013c76  mov     edx, 1
0x180013c7b  call    ?Open@Context@Migration@StateRepository@@QEBAJW4Partition@3@AEAVDatabase@3@@Z; StateRepository::Migration::Context::Open(StateRepository::Partition,StateRepository::Database &)
0x180013c80  xor     esi, esi
0x180013c82  mov     ebx, eax
0x180013c84  test    eax, eax
0x180013c86  jns     short loc_180013C8D
0x180013c88  lea     edx, [rsi+11h]
0x180013c8b  jmp     short loc_180013CA6
0x180013c8d  lea     r8, [rbp+210h+var_220]
0x180013c91  mov     edx, 2
0x180013c96  call    ?Open@Context@Migration@StateRepository@@QEBAJW4Partition@3@AEAVDatabase@3@@Z; StateRepository::Migration::Context::Open(StateRepository::Partition,StateRepository::Database &)
0x180013c9b  mov     ebx, eax
0x180013c9d  test    eax, eax
0x180013c9f  jns     short loc_180013CC1
0x180013ca1  mov     edx, 12h; void *
0x180013ca6  mov     rcx, [rbp+218h]; this
0x180013cad  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appmodel\\staterepositor"...
0x180013cb4  mov     r9d, eax; char *
0x180013cb7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013cbc  jmp     loc_1800141BD
0x180013cc1  mov     rcx, rdi; this
0x180013cc4  call    ?ExecuteInProgressCallback@Context@Migration@StateRepository@@QEBAXXZ; StateRepository::Migration::Context::ExecuteInProgressCallback(void)
0x180013cc9  mov     r9, [rdi+20h]; void *
0x180013ccd  lea     rdx, stru_18003C440; struct _GUID *
0x180013cd4  mov     r8, [rdi+18h]; int (*)(void *)
0x180013cd8  lea     rcx, [rbp+210h+var_90]; this
0x180013cdf  call    ?BeginTransaction@Database@StateRepository@@QEAAJAEBU_GUID@@P6AJPEAX@Z1@Z; StateRepository::Database::BeginTransaction(_GUID const &,long (*)(void *),void *)
0x180013ce4  mov     ebx, eax
0x180013ce6  test    eax, eax
0x180013ce8  jns     short loc_180013CF1
0x180013cea  mov     edx, 16h
0x180013cef  jmp     short loc_180013CA6
0x180013cf1  mov     r9, [rdi+20h]; void *
0x180013cf5  lea     rdx, stru_18003C440; struct _GUID *
0x180013cfc  mov     r8, [rdi+18h]; int (*)(void *)
0x180013d00  lea     rcx, [rbp+210h+var_220]; this
0x180013d04  call    ?BeginTransaction@Database@StateRepository@@QEAAJAEBU_GUID@@P6AJPEAX@Z1@Z; StateRepository::Database::BeginTransaction(_GUID const &,long (*)(void *),void *)
0x180013d09  mov     ebx, eax
0x180013d0b  test    eax, eax
0x180013d0d  jns     short loc_180013D16
0x180013d0f  mov     edx, 17h
0x180013d14  jmp     short loc_180013CA6
0x180013d16  lea     rax, [rbp+210h+var_90]
0x180013d1d  mov     [rsp+310h+var_2E8], rax
0x180013d22  lea     rcx, [rbp+210h+var_220]; this
0x180013d26  lea     rax, [rbp+210h+var_220]
0x180013d2a  mov     [rsp+310h+var_2F0], rax; int
0x180013d2f  call    ?GetFilename@Database@StateRepository@@QEBAPEBDPEBD@Z; StateRepository::Database::GetFilename(char const *)
0x180013d34  mov     rdx, rax; char *
0x180013d37  lea     rcx, [rbp+210h+var_90]; this
0x180013d3e  call    ?AttachDatabase@Database@StateRepository@@QEAAJPEBD0@Z; StateRepository::Database::AttachDatabase(char const *,char const *)
0x180013d43  mov     ebx, eax
0x180013d45  test    eax, eax
0x180013d47  jns     short loc_180013D7D
0x180013d49  mov     rcx, [rbp+218h]; this
0x180013d50  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appmodel\\staterepositor"...
0x180013d57  mov     r9d, eax; char *
0x180013d5a  mov     edx, 1Dh; void *
0x180013d5f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013d64  lea     rcx, [rsp+310h+var_2F0]; this
0x180013d69  call    ??1AutoTransaction@StateRepository@@QEAA@XZ; StateRepository::AutoTransaction::~AutoTransaction(void)
0x180013d6e  lea     rcx, [rsp+310h+var_2E8]; this
0x180013d73  call    ??1AutoTransaction@StateRepository@@QEAA@XZ; StateRepository::AutoTransaction::~AutoTransaction(void)
0x180013d78  jmp     loc_1800141BD
0x180013d7d  lea     rax, [rbp+210h+var_90]
0x180013d84  mov     [rbp+210h+arg_18], rsi
0x180013d8b  mov     [rsp+310h+var_2D0], rax
0x180013d90  lea     r8, [rbp+210h+arg_18]
0x180013d97  lea     rax, aDeployment; "Deployment"
0x180013d9e  lea     rcx, [rbp+210h+var_90]
0x180013da5  mov     [rsp+310h+var_2C8], rax
0x180013daa  call    ?FindHighestVersionPackagesPerFamilyByPackageTypeAndInPackageAppInstaller@Package@Entity@StateRepository@@SAJAEAVDatabase@3@W4PackageType@3@AEAVStatement@3@@Z; StateRepository::Entity::Package::FindHighestVersionPackagesPerFamilyByPackageTypeAndInPackageAppInstaller(StateRepository::Database &,StateRepository::PackageType,StateRepository::Statement &)
0x180013daf  mov     ebx, eax
0x180013db1  test    eax, eax
0x180013db3  jns     short loc_180013DEB
0x180013db5  mov     rcx, [rbp+218h]; this
0x180013dbc  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appmodel\\staterepositor"...
0x180013dc3  mov     r9d, eax; char *
0x180013dc6  mov     edx, 21h ; '!'; void *
0x180013dcb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013dd0  lea     rcx, [rbp+210h+arg_18]; this
0x180013dd7  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x180013ddc  lea     rcx, [rsp+310h+var_2D0]; this
0x180013de1  call    ??1AutoDetachDatabase@StateRepository@@QEAA@XZ; StateRepository::AutoDetachDatabase::~AutoDetachDatabase(void)
0x180013de6  jmp     loc_180013D64
0x180013deb  lea     rcx, [rbp+210h+var_1A0]; this
0x180013def  call    ??0Package@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::Package::Package(void)
0x180013df4  lea     r8, [rbp+210h+arg_8]; bool *
0x180013dfb  mov     [rbp+210h+arg_8], sil
0x180013e02  lea     rdx, [rbp+210h+var_1A0]; struct StateRepository::Entity::Package *
0x180013e06  lea     rcx, [rbp+210h+arg_18]; struct StateRepository::Statement *
0x180013e0d  call    ?FindNext@Package@Entity@StateRepository@@SAJAEAVStatement@3@AEAV123@AEA_N@Z; StateRepository::Entity::Package::FindNext(StateRepository::Statement &,StateRepository::Entity::Package &,bool &)
0x180013e12  mov     ebx, eax
0x180013e14  test    eax, eax
0x180013e16  jns     short loc_180013E3E
0x180013e18  mov     rcx, [rbp+218h]; this
0x180013e1f  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appmodel\\staterepositor"...
0x180013e26  mov     r9d, eax; char *
0x180013e29  mov     edx, 26h ; '&'; void *
0x180013e2e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013e33  lea     rcx, [rbp+210h+var_1A0]; this
0x180013e37  call    ??1Package@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::Package::~Package(void)
0x180013e3c  jmp     short loc_180013DD0
0x180013e3e  lea     rcx, [rbp+210h+var_220]; this
0x180013e42  xorps   xmm0, xmm0
0x180013e45  xorps   xmm1, xmm1
0x180013e48  movdqa  [rsp+310h+var_2B0], xmm0
0x180013e4e  movdqa  [rbp+210h+var_290], xmm0
0x180013e53  movdqa  xmmword ptr [rsp+310h+var_2A0], xmm1
0x180013e59  mov     [rsp+310h+var_2C0], rsi
0x180013e5e  mov     [rsp+310h+var_2B8], rsi
0x180013e63  cmp     [rbp+210h+arg_8], sil
0x180013e6a  jz      loc_180014015
0x180013e70  mov     rdx, [rbp+210h+var_1A0]; __int64
0x180013e74  lea     r8, [rsp+310h+var_2D8]; struct StateRepository::Statement *
0x180013e79  mov     [rsp+310h+var_2D8], rsi
0x180013e7e  mov     [rbp+210h+arg_10], sil
0x180013e85  call    ?FindByPackage@PackageAppInstaller@Entity@StateRepository@@SAJAEAVDatabase@3@_JAEAVStatement@3@@Z; StateRepository::Entity::PackageAppInstaller::FindByPackage(StateRepository::Database &,__int64,StateRepository::Statement &)
0x180013e8a  mov     ebx, eax
0x180013e8c  test    eax, eax
0x180013e8e  js      loc_180013FE1
0x180013e94  lea     r8, [rbp+210h+arg_10]; bool *
0x180013e9b  lea     rdx, [rsp+310h+var_2C0]; struct StateRepository::Entity::PackageAppInstaller *
0x180013ea0  lea     rcx, [rsp+310h+var_2D8]; struct StateRepository::Statement *
0x180013ea5  call    ?FindNext@PackageAppInstaller@Entity@StateRepository@@SAJAEAVStatement@3@AEAV123@AEA_N@Z; StateRepository::Entity::PackageAppInstaller::FindNext(StateRepository::Statement &,StateRepository::Entity::PackageAppInstaller &,bool &)
0x180013eaa  mov     ebx, eax
0x180013eac  test    eax, eax
0x180013eae  js      loc_180013FDA
0x180013eb4  cmp     [rbp+210h+arg_10], sil
0x180013ebb  jz      loc_180013F46
0x180013ec1  mov     rdx, [rsp+310h+var_2A0]; __int64
0x180013ec6  lea     r9, [rbp+210h+arg_10]; bool *
0x180013ecd  xorps   xmm0, xmm0
0x180013ed0  mov     [rbp+210h+var_280], rsi
0x180013ed4  xor     eax, eax
0x180013ed6  movdqa  [rbp+210h+var_270], xmm0
0x180013edb  lea     r8, [rbp+210h+var_280]; struct StateRepository::Entity::AppInstaller *
0x180013edf  mov     [rbp+210h+var_250], rax
0x180013ee3  lea     rcx, [rbp+210h+var_220]; this
0x180013ee7  mov     [rbp+210h+var_240], rax
0x180013eeb  movdqa  [rbp+210h+var_230], xmm0
0x180013ef0  mov     [rbp+210h+var_278], rsi
0x180013ef4  mov     [rbp+210h+var_260], rsi
0x180013ef8  mov     [rbp+210h+var_258], rsi
0x180013efc  mov     [rbp+210h+var_248], rsi
0x180013f00  mov     [rbp+210h+var_238], rsi
0x180013f04  mov     [rbp+210h+arg_10], sil
0x180013f0b  call    ?TryGet@AppInstaller@Entity@StateRepository@@SAJAEAVDatabase@3@_JAEAV123@AEA_N@Z; StateRepository::Entity::AppInstaller::TryGet(StateRepository::Database &,__int64,StateRepository::Entity::AppInstaller &,bool &)
0x180013f10  mov     ebx, eax
0x180013f12  test    eax, eax
0x180013f14  js      short loc_180013F92
0x180013f16  cmp     [rbp+210h+arg_10], sil
0x180013f1d  jz      short loc_180013F86
0x180013f1f  mov     rax, [rbp+210h+var_188]
0x180013f26  lea     rdx, [rbp+210h+var_220]
0x180013f2a  lea     rcx, [rbp+210h+var_280]
0x180013f2e  mov     qword ptr [rbp+210h+var_270], rax
0x180013f32  call    ?Update@AppInstaller@Entity@StateRepository@@QEAAJAEAVDatabase@3@W4ExecutionFlags@3@@Z; StateRepository::Entity::AppInstaller::Update(StateRepository::Database &,StateRepository::ExecutionFlags)
0x180013f37  mov     ebx, eax
0x180013f39  test    eax, eax
0x180013f3b  js      short loc_180013F7C
0x180013f3d  lea     rcx, [rbp+210h+var_280]; this
0x180013f41  call    ??1AppInstaller@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::AppInstaller::~AppInstaller(void)
0x180013f46  lea     r8, [rbp+210h+arg_8]; bool *
0x180013f4d  lea     rdx, [rbp+210h+var_1A0]; struct StateRepository::Entity::Package *
0x180013f51  lea     rcx, [rbp+210h+arg_18]; struct StateRepository::Statement *
0x180013f58  call    ?FindNext@Package@Entity@StateRepository@@SAJAEAVStatement@3@AEAV123@AEA_N@Z; StateRepository::Entity::Package::FindNext(StateRepository::Statement &,StateRepository::Entity::Package &,bool &)
0x180013f5d  mov     ebx, eax
0x180013f5f  test    eax, eax
0x180013f61  js      short loc_180013FD3
0x180013f63  lea     rcx, [rsp+310h+var_2A0+8]; this
0x180013f68  call    ?Reset@Blob@StateRepository@@QEAAXXZ; StateRepository::Blob::Reset(void)
0x180013f6d  lea     rcx, [rsp+310h+var_2D8]; this
0x180013f72  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x180013f77  jmp     loc_180013E3E
0x180013f7c  mov     r9d, eax
0x180013f7f  mov     edx, 37h ; '7'
0x180013f84  jmp     short loc_180013FB5
0x180013f86  mov     ebx, 80070490h
0x180013f8b  mov     edx, 167h
0x180013f90  jmp     short loc_180013F97
0x180013f92  mov     edx, 166h; void *
0x180013f97  mov     rcx, [rbp+218h]; this
0x180013f9e  lea     r8, aOnecoreBaseApp_49; "onecore\\base\\appmodel\\staterepositor"...
0x180013fa5  mov     r9d, ebx; char *
0x180013fa8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013fad  mov     r9d, ebx; char *
0x180013fb0  mov     edx, 35h ; '5'; void *
0x180013fb5  mov     rcx, [rbp+218h]; this
0x180013fbc  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appmodel\\staterepositor"...
0x180013fc3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013fc8  lea     rcx, [rbp+210h+var_280]; this
0x180013fcc  call    ??1AppInstaller@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::AppInstaller::~AppInstaller(void)
0x180013fd1  jmp     short loc_180013FFC
0x180013fd3  mov     edx, 3Ah ; ':'
0x180013fd8  jmp     short loc_180013FE6
0x180013fda  mov     edx, 2Fh ; '/'
0x180013fdf  jmp     short loc_180013FE6
0x180013fe1  mov     edx, 2Eh ; '.'; void *
0x180013fe6  mov     rcx, [rbp+218h]; this
0x180013fed  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appmodel\\staterepositor"...
0x180013ff4  mov     r9d, eax; char *
0x180013ff7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013ffc  lea     rcx, [rsp+310h+var_2A0+8]; this
0x180014001  call    ?Reset@Blob@StateRepository@@QEAAXXZ; StateRepository::Blob::Reset(void)
0x180014006  lea     rcx, [rsp+310h+var_2D8]; this
0x18001400b  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x180014010  jmp     loc_180013E33
0x180014015  lea     r9, [rsp+310h+var_2E0]; char *
0x18001401a  mov     qword ptr [rsp+310h+var_2E0], rsi
0x18001401f  lea     r8, aSelectPackagea; "SELECT _PackageAppInstallerID, _Revisio"...
0x180014026  mov     [rbp+210h+arg_8], sil
0x18001402d  lea     rdx, aSelectPackagea_1; "SELECT _PackageAppInstallerID, _Revisio"...
0x180014034  call    ?PrepareAndBindAndFind@StatementExecution@StateRepository@@YAJAEAVDatabase@2@PEBD1AEAVStatement@2@@Z; StateRepository::StatementExecution::PrepareAndBindAndFind(StateRepository::Database &,char const *,char const *,StateRepository::Statement &)
0x180014039  mov     ebx, eax
0x18001403b  test    eax, eax
0x18001403d  jns     short loc_180014086
0x18001403f  mov     rcx, [rbp+218h]; this
0x180014046  lea     r8, aOnecoreBaseApp_5; "onecore\\base\\appmodel\\staterepositor"...
0x18001404d  mov     r9d, eax; char *
0x180014050  mov     edx, 15Fh; void *
0x180014055  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001405a  mov     r9d, ebx; char *
0x18001405d  mov     edx, 41h ; 'A'; void *
0x180014062  mov     rcx, [rbp+218h]; this
0x180014069  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appmodel\\staterepositor"...
0x180014070  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014075  lea     rcx, [rsp+310h+var_2A0+8]; this
0x18001407a  call    ?Reset@Blob@StateRepository@@QEAAXXZ; StateRepository::Blob::Reset(void)
0x18001407f  lea     rcx, [rsp+310h+var_2E0]
0x180014084  jmp     short loc_18001400B
0x180014086  lea     r8, [rbp+210h+arg_8]; bool *
0x18001408d  lea     rdx, [rsp+310h+var_2C0]; struct StateRepository::Entity::PackageAppInstaller *
0x180014092  lea     rcx, [rsp+310h+var_2E0]; struct StateRepository::Statement *
0x180014097  call    ?FindNext@PackageAppInstaller@Entity@StateRepository@@SAJAEAVStatement@3@AEAV123@AEA_N@Z; StateRepository::Entity::PackageAppInstaller::FindNext(StateRepository::Statement &,StateRepository::Entity::PackageAppInstaller &,bool &)
0x18001409c  mov     ebx, eax
0x18001409e  test    eax, eax
0x1800140a0  jns     short loc_1800140AC
0x1800140a2  mov     r9d, eax
0x1800140a5  mov     edx, 42h ; 'B'
0x1800140aa  jmp     short loc_180014062
0x1800140ac  cmp     [rbp+210h+arg_8], sil
0x1800140b3  jz      short loc_1800140FF
0x1800140b5  mov     rdx, [rsp+310h+var_2C0]
0x1800140ba  lea     rcx, [rbp+210h+var_220]
0x1800140be  call    ?Delete@PackageAppInstaller@Entity@StateRepository@@SAJAEAVDatabase@3@_JW4ExecutionFlags@3@@Z; StateRepository::Entity::PackageAppInstaller::Delete(StateRepository::Database &,__int64,StateRepository::ExecutionFlags)
0x1800140c3  mov     ebx, eax
0x1800140c5  test    eax, eax
0x1800140c7  js      short loc_1800140F2
0x1800140c9  lea     r8, [rbp+210h+arg_8]; bool *
0x1800140d0  lea     rdx, [rsp+310h+var_2C0]; struct StateRepository::Entity::PackageAppInstaller *
0x1800140d5  lea     rcx, [rsp+310h+var_2E0]; struct StateRepository::Statement *
0x1800140da  call    ?FindNext@PackageAppInstaller@Entity@StateRepository@@SAJAEAVStatement@3@AEAV123@AEA_N@Z; StateRepository::Entity::PackageAppInstaller::FindNext(StateRepository::Statement &,StateRepository::Entity::PackageAppInstaller &,bool &)
0x1800140df  mov     ebx, eax
0x1800140e1  test    eax, eax
0x1800140e3  jns     short loc_1800140AC
0x1800140e5  mov     r9d, eax
0x1800140e8  mov     edx, 46h ; 'F'
0x1800140ed  jmp     loc_180014062
0x1800140f2  mov     r9d, eax
0x1800140f5  mov     edx, 45h ; 'E'
0x1800140fa  jmp     loc_180014062
0x1800140ff  lea     rcx, [rsp+310h+var_2E8]; this
0x180014104  call    ?Commit@AutoTransaction@StateRepository@@QEAAJXZ; StateRepository::AutoTransaction::Commit(void)
0x180014109  mov     ebx, eax
0x18001410b  test    eax, eax
0x18001410d  jns     short loc_18001411C
0x18001410f  mov     r9d, eax
0x180014112  mov     edx, 49h ; 'I'
0x180014117  jmp     loc_180014062
0x18001411c  lea     rcx, [rsp+310h+var_2F0]; this
0x180014121  call    ?Commit@AutoTransaction@StateRepository@@QEAAJXZ; StateRepository::AutoTransaction::Commit(void)
0x180014126  mov     ebx, eax
0x180014128  test    eax, eax
0x18001412a  jns     short loc_180014139
0x18001412c  mov     r9d, eax
0x18001412f  mov     edx, 4Ah ; 'J'
0x180014134  jmp     loc_180014062
0x180014139  lea     rdx, [rbp+210h+var_90]; struct StateRepository::Database *
0x180014140  call    ?Close@Context@Migration@StateRepository@@QEBAJAEAVDatabase@3@@Z; StateRepository::Migration::Context::Close(StateRepository::Database &)
0x180014145  mov     ebx, eax
0x180014147  test    eax, eax
0x180014149  jns     short loc_180014158
0x18001414b  mov     r9d, eax
0x18001414e  mov     edx, 4Bh ; 'K'
0x180014153  jmp     loc_180014062
0x180014158  lea     rdx, [rbp+210h+var_220]; struct StateRepository::Database *
0x18001415c  call    ?Close@Context@Migration@StateRepository@@QEBAJAEAVDatabase@3@@Z; StateRepository::Migration::Context::Close(StateRepository::Database &)
  ... truncated ...
```
