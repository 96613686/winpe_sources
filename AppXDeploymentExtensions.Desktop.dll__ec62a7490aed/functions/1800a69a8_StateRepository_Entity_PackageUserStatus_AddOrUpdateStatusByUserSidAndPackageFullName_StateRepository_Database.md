# StateRepository::Entity::PackageUserStatus::AddOrUpdateStatusByUserSidAndPackageFullName(StateRepository::Database &,void *,ushort const *,StateRepository::PackageStatus,StateRepository::PackageStatus,StateRepository::ExecutionFlags)

- ea: `0x1800a69a8`
- end: `0x1800a6ec6`
- name: `?AddOrUpdateStatusByUserSidAndPackageFullName@PackageUserStatus@Entity@StateRepository@@SAJAEAVDatabase@3@PEAXPEBGW4PackageStatus@3@3W4ExecutionFlags@3@@Z`
- size: `1310`
- prototype: ``
- caller_count: `1`
- callee_count: `28`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180187540`

## callees

- `0x180012fc8`
- `0x18001adb4`
- `0x180046124`
- `0x180046a14`
- `0x180046c60`
- `0x180047410`
- `0x18004749c`
- `0x18005d5f8`
- `0x18005df00`
- `0x180069eb4`
- `0x180074ef0`
- `0x18008b698`
- `0x1800a6804`
- `0x1800a69a8`
- `0x1800a7a44`
- `0x1800aa0e4`
- `0x1800af918`
- `0x180119a48`
- `0x18011b9a4`
- `0x18011e11c`
- `0x1801207b0`
- `0x180122a60`
- `0x18012e13c`
- `0x18013105c`
- `0x180131104`
- `0x180131398`
- `0x1801324e0`
- `0x1801ac010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800a6a32`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800a6a32`
- `api-ms-win-appmodel-runtime-l1-1-1!VerifyPackageFullName` at `0x1800a6b7b`
- `api-ms-win-appmodel-runtime-l1-1-1!VerifyPackageFullName` at `0x1800a6b7b`

## string_xrefs

- `0x1800a69e8`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-packageuserstatus-custom.cpp`
- `0x1800a6ac0`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-packageuserstatus-custom.cpp`
- `0x1800a6af1`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-packageuserstatus-custom.cpp`
- `0x1800a6b4f`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-packageuserstatus-custom.cpp`
- `0x1800a6b95`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-packageuserstatus-custom.cpp`
- `0x1800a6bf3`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-packageuserstatus-custom.cpp`
- `0x1800a6c46`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-packageuserstatus-custom.cpp`
- `0x1800a6cbf`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-packageuserstatus-custom.cpp`
- `0x1800a6e09`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-packageuserstatus-custom.cpp`
- `0x1800a6e61`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-packageuserstatus-custom.cpp`
- `0x1800a6db8`: `UPDATE PackageUserStatus SET Status=?3 WHERE PackageIdentity IN (SELECT _PackageIdentityID FROM PackageIdentity WHERE PackageFullName=?2) AND User IN (SELECT _UserID FROM User WHERE UserSid=?1);`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall StateRepository::Entity::PackageUserStatus::AddOrUpdateStatusByUserSidAndPackageFullName(
        StateRepository::Database *a1,
        void *a2,
        const WCHAR *a3,
        int a4,
        int a5,
        int a6)
{
  unsigned int v8; // ebx
  __int64 v9; // rdx
  int v11; // esi
  int v12; // eax
  int StatusByUserSidAndPackageFullName; // r14d
  __int64 v14; // rdx
  unsigned int v15; // eax
  int v16; // eax
  int v17; // eax
  __int64 v18; // rdx
  int v19; // eax
  int v20; // ebx
  __int64 v21; // rax
  int NoRow; // eax
  __int64 v23; // rdx
  int v24; // eax
  struct StateRepository::Statement *v25; // [rsp+28h] [rbp-E0h] BYREF
  int v26; // [rsp+30h] [rbp-D8h] BYREF
  __int64 v27; // [rsp+38h] [rbp-D0h] BYREF
  _QWORD v28[3]; // [rsp+40h] [rbp-C8h] BYREF
  _OWORD v29[4]; // [rsp+58h] [rbp-B0h] BYREF
  _QWORD v30[4]; // [rsp+98h] [rbp-70h] BYREF
  int v31; // [rsp+B8h] [rbp-50h]
  __int64 v32; // [rsp+C0h] [rbp-48h] BYREF
  __int128 v33; // [rsp+C8h] [rbp-40h]
  _QWORD v34[2]; // [rsp+D8h] [rbp-30h] BYREF
  __int128 v35; // [rsp+E8h] [rbp-20h]
  __int128 v36; // [rsp+F8h] [rbp-10h]
  __int128 v37; // [rsp+108h] [rbp+0h]
  _QWORD v38[10]; // [rsp+118h] [rbp+10h] BYREF
  int v39; // [rsp+16Ch] [rbp+64h]
  wil::details::in1diag3 *retaddr; // [rsp+250h] [rbp+148h]
  PSID pSid; // [rsp+260h] [rbp+158h] BYREF
  PCWSTR packageFullName; // [rsp+268h] [rbp+160h] BYREF

  packageFullName = a3;
  pSid = a2;
  if ( StateRepository::Database::IsInAutoCommitMode(a1) )
  {
    v8 = -2140733429;
    v9 = 234;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-packageuserstatus-custom.cpp",
      (const char *)v8,
      (int)v25);
    return v8;
  }
  if ( !packageFullName )
  {
    v8 = -2147024809;
    v9 = 236;
    goto LABEL_3;
  }
  if ( !pSid )
  {
    v8 = -2147024809;
    v9 = 237;
    goto LABEL_3;
  }
  if ( !IsValidSid(pSid) )
  {
    v8 = -2147024809;
    v9 = 238;
    goto LABEL_3;
  }
  v11 = a5;
  if ( (a5 & 0xEB7FE05F) != 0 )
  {
    v8 = -2147024809;
    v9 = 239;
    goto LABEL_3;
  }
  if ( (a5 & 0xC00) != 0 )
  {
    memset_0(v38, 0, 0x110u);
    StateRepository::Entity::Package::Package((StateRepository::Entity::Package *)v38);
    LOBYTE(a6) = 0;
    v12 = StateRepository::Entity::Package::TryGetByPackageFullName(
            a1,
            packageFullName,
            (struct StateRepository::Entity::Package *)v38,
            (bool *)&a6);
    StatusByUserSidAndPackageFullName = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF7,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-packageuserstatus-custom.cpp",
        (const char *)(unsigned int)v12,
        (int)v25);
LABEL_19:
      StateRepository::Entity::Package::~Package((StateRepository::Entity::Package *)v38);
      return (unsigned int)StatusByUserSidAndPackageFullName;
    }
    if ( (_BYTE)a6 && v39 == 2 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xFB,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-packageuserstatus-custom.cpp",
        (const char *)0x80070057LL,
        (int)v25);
      StatusByUserSidAndPackageFullName = -2147024809;
      goto LABEL_19;
    }
    StateRepository::Entity::Package::~Package((StateRepository::Entity::Package *)v38);
  }
  LOBYTE(a6) = 0;
  StatusByUserSidAndPackageFullName = StateRepository::Entity::PackageUserStatus::ExistsByUserSidAndPackageFullName(
                                        a1,
                                        pSid,
                                        packageFullName,
                                        (bool *)&a6);
  if ( StatusByUserSidAndPackageFullName < 0 )
  {
    v14 = 256;
LABEL_24:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-packageuserstatus-custom.cpp",
      (const char *)(unsigned int)StatusByUserSidAndPackageFullName,
      (int)v25);
    return (unsigned int)StatusByUserSidAndPackageFullName;
  }
  if ( (_BYTE)a6 )
  {
    a6 = 0;
    StatusByUserSidAndPackageFullName = StateRepository::Entity::PackageUserStatus::GetStatusByUserSidAndPackageFullName(
                                          a1,
                                          pSid,
                                          packageFullName,
                                          (enum StateRepository::PackageStatus *)&a6);
    if ( StatusByUserSidAndPackageFullName < 0 )
    {
      v14 = 280;
      goto LABEL_24;
    }
    v20 = v11 | a6 & ~a4;
    v26 = v20;
    if ( v20 == a6 )
      return 0;
    if ( !v20 )
    {
      v8 = StateRepository::Entity::PackageUserStatus::DeleteByUserSidAndPackageFullName(a1, pSid, packageFullName);
      if ( (v8 & 0x80000000) != 0 )
      {
        v9 = 315;
        goto LABEL_3;
      }
      return 0;
    }
    StateRepository::DatabaseTriggers::Disable(&v27, a1, 0);
    v21 = _lambda_454331550775a661471245d7d7e1e5b3_::_lambda_454331550775a661471245d7d7e1e5b3_(
            v28,
            &pSid,
            &packageFullName,
            &v26);
    StateRepository::StatementExecution::StatementBinderFunc::StatementBinderFunc__lambda_0eea3193c0e0e0c31eda4019c1b8b6aa___(
      v38,
      v21);
    v28[0] = "UPDATE PackageUserStatus SET Status=?3 WHERE PackageIdentity IN (SELECT _PackageIdentityID FROM PackageIden"
             "tity WHERE PackageFullName=?2) AND User IN (SELECT _UserID FROM User WHERE UserSid=?1);";
    v28[1] = 0;
    v28[2] = 0;
    NoRow = StateRepository::StatementExecution::PrepareAndBind(
              a1,
              (struct StateRepository::Database *)v28,
              (const struct StateRepository::StatementExecution::StatementDefinition *)v38,
              (struct StateRepository::StatementExecution::StatementBinderFunc *)&v25,
              0);
    v8 = NoRow;
    if ( NoRow >= 0 )
    {
      NoRow = StateRepository::Statement::FetchNoRow((StateRepository::Statement *)&v25);
      v8 = NoRow;
      if ( NoRow >= 0 )
      {
        v24 = StateRepository::Database::AddToCache(a1, (struct StateRepository::Statement *)&v25);
        if ( v24 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x137,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-packageuserstatus-custom.cpp",
            (const char *)(unsigned int)v24,
            (int)v25);
        (**(void (__fastcall ***)(_QWORD, _QWORD))v38[0])(v38[0], 0);
        StateRepository::Statement::~Statement((StateRepository::Statement *)&v25);
        StateRepository::AutoEnableTriggersScopeExit::~AutoEnableTriggersScopeExit((StateRepository::AutoEnableTriggersScopeExit *)&v27);
        return 0;
      }
      v23 = 309;
    }
    else
    {
      v23 = 308;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v23,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-packageuserstatus-custom.cpp",
      (const char *)(unsigned int)NoRow,
      (int)v25);
    (**(void (__fastcall ***)(_QWORD, _QWORD))v38[0])(v38[0], 0);
    StateRepository::Statement::~Statement((StateRepository::Statement *)&v25);
    StateRepository::AutoEnableTriggersScopeExit::~AutoEnableTriggersScopeExit((StateRepository::AutoEnableTriggersScopeExit *)&v27);
    return v8;
  }
  v15 = VerifyPackageFullName(packageFullName);
  if ( v15 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x104,
             (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-packageuserstatus-custom.cpp",
             (const char *)v15,
             (unsigned int)v25);
  if ( v11 )
  {
    v34[0] = 0;
    v34[1] = 0;
    v35 = 0;
    v36 = 0;
    v37 = 0;
    v16 = StateRepository::Entity::PackageIdentity::GetOrAddIfNotExistByPackageFullName(a1, packageFullName, v34);
    v8 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x109,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-packageuserstatus-custom.cpp",
        (const char *)(unsigned int)v16,
        (int)v25);
LABEL_39:
      StateRepository::Entity::PackageIdentity::~PackageIdentity((StateRepository::Entity::PackageIdentity *)v34);
      return v8;
    }
    memset(v29, 0, sizeof(v29));
    v17 = StateRepository::Entity::User::SetUserSid((StateRepository::Entity::User *)v29, pSid);
    v8 = v17;
    if ( v17 < 0 )
    {
      v18 = 267;
LABEL_33:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v18,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-packageuserstatus-custom.cpp",
        (const char *)(unsigned int)v17,
        (int)v25);
LABEL_38:
      StateRepository::Entity::User::~User((StateRepository::Entity::User *)v29);
      goto LABEL_39;
    }
    v17 = StateRepository::Entity::User::GetOrAddIfNotExist(v29, a1, 0);
    v8 = v17;
    if ( v17 < 0 )
    {
      v18 = 268;
      goto LABEL_33;
    }
    v30[0] = 0;
    v30[1] = 0;
    v32 = 0;
    v33 = 0;
    v30[2] = v34[0];
    v30[3] = *(_QWORD *)&v29[0];
    v31 = v11;
    v19 = StateRepository::Entity::PackageUserStatus::Add(v30, a1);
    v8 = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x112,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-packageuserstatus-custom.cpp",
        (const char *)(unsigned int)v19,
        (int)v25);
      StateRepository::Blob::Reset((StateRepository::Blob *)&v32);
      goto LABEL_38;
    }
    StateRepository::Blob::Reset((StateRepository::Blob *)&v32);
    StateRepository::Entity::User::~User((StateRepository::Entity::User *)v29);
    StateRepository::Entity::PackageIdentity::~PackageIdentity((StateRepository::Entity::PackageIdentity *)v34);
  }
  return 0;
}

```

## disassembly

```asm
0x1800a69a8  mov     rax, rsp
0x1800a69ab  mov     [rax+8], rbx
0x1800a69af  mov     [rax+18h], r8
0x1800a69b3  mov     [rax+10h], rdx
0x1800a69b7  push    rbp
0x1800a69b8  push    rsi
0x1800a69b9  push    rdi
0x1800a69ba  push    r14
0x1800a69bc  push    r15
0x1800a69be  lea     rbp, [rax-148h]
0x1800a69c5  sub     rsp, 220h
0x1800a69cc  mov     ebx, r9d
0x1800a69cf  mov     rdi, rcx
0x1800a69d2  call    ?IsInAutoCommitMode@Database@StateRepository@@QEAA_NXZ; StateRepository::Database::IsInAutoCommitMode(void)
0x1800a69d7  xor     r15d, r15d
0x1800a69da  test    al, al
0x1800a69dc  jz      short loc_1800A6A05
0x1800a69de  mov     ebx, 8067000Bh
0x1800a69e3  mov     edx, 0EAh; void *
0x1800a69e8  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appmodel\\staterepositor"...
0x1800a69ef  mov     r9d, ebx; char *
0x1800a69f2  mov     rcx, [rbp+148h]; this
0x1800a69f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a69fe  mov     eax, ebx
0x1800a6a00  jmp     loc_1800A6D0F
0x1800a6a05  cmp     [rbp+140h+packageFullName], r15
0x1800a6a0c  jnz     short loc_1800A6A1A
0x1800a6a0e  mov     ebx, 80070057h
0x1800a6a13  mov     edx, 0ECh
0x1800a6a18  jmp     short loc_1800A69E8
0x1800a6a1a  mov     rcx, [rbp+140h+pSid]; pSid
0x1800a6a21  test    rcx, rcx
0x1800a6a24  jnz     short loc_1800A6A32
0x1800a6a26  mov     ebx, 80070057h
0x1800a6a2b  mov     edx, 0EDh
0x1800a6a30  jmp     short loc_1800A69E8
0x1800a6a32  call    cs:__imp_IsValidSid
0x1800a6a39  nop     dword ptr [rax+rax+00h]
0x1800a6a3e  test    eax, eax
0x1800a6a40  jnz     short loc_1800A6A4E
0x1800a6a42  mov     ebx, 80070057h
0x1800a6a47  mov     edx, 0EEh
0x1800a6a4c  jmp     short loc_1800A69E8
0x1800a6a4e  mov     esi, [rbp+140h+arg_20]
0x1800a6a54  test    esi, 0EB7FE05Fh
0x1800a6a5a  jz      short loc_1800A6A68
0x1800a6a5c  mov     ebx, 80070057h
0x1800a6a61  mov     edx, 0EFh
0x1800a6a66  jmp     short loc_1800A69E8
0x1800a6a68  test    esi, 0C00h
0x1800a6a6e  jz      loc_1800A6B1F
0x1800a6a74  xor     edx, edx; Val
0x1800a6a76  mov     r8d, 110h; Size
0x1800a6a7c  lea     rcx, [rbp+140h+var_130]; void *
0x1800a6a80  call    memset_0
0x1800a6a85  lea     rcx, [rbp+140h+var_130]; this
0x1800a6a89  call    ??0Package@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::Package::Package(void)
0x1800a6a8e  mov     byte ptr [rbp+140h+arg_28], r15b
0x1800a6a95  lea     r9, [rbp+140h+arg_28]; bool *
0x1800a6a9c  lea     r8, [rbp+140h+var_130]; struct StateRepository::Entity::Package *
0x1800a6aa0  mov     rdx, [rbp+140h+packageFullName]; unsigned __int16 *
0x1800a6aa7  mov     rcx, rdi; struct StateRepository::Database *
0x1800a6aaa  call    ?TryGetByPackageFullName@Package@Entity@StateRepository@@SAJAEAVDatabase@3@PEBGAEAV123@AEA_N@Z; StateRepository::Entity::Package::TryGetByPackageFullName(StateRepository::Database &,ushort const *,StateRepository::Entity::Package &,bool &)
0x1800a6aaf  mov     r14d, eax
0x1800a6ab2  test    eax, eax
0x1800a6ab4  jns     short loc_1800A6AD3
0x1800a6ab6  mov     rcx, [rbp+148h]; this
0x1800a6abd  mov     r9d, eax; char *
0x1800a6ac0  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appmodel\\staterepositor"...
0x1800a6ac7  mov     edx, 0F7h; void *
0x1800a6acc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6ad1  jmp     short loc_1800A6B05
0x1800a6ad3  cmp     byte ptr [rbp+140h+arg_28], r15b
0x1800a6ada  jz      short loc_1800A6B16
0x1800a6adc  cmp     [rbp+140h+var_DC], 2
0x1800a6ae0  jnz     short loc_1800A6B16
0x1800a6ae2  mov     rcx, [rbp+148h]; this
0x1800a6ae9  mov     ebx, 80070057h
0x1800a6aee  mov     r9d, ebx; char *
0x1800a6af1  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appmodel\\staterepositor"...
0x1800a6af8  mov     edx, 0FBh; void *
0x1800a6afd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6b02  mov     r14d, ebx
0x1800a6b05  lea     rcx, [rbp+140h+var_130]; this
0x1800a6b09  call    ??1Package@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::Package::~Package(void)
0x1800a6b0e  mov     eax, r14d
0x1800a6b11  jmp     loc_1800A6D0F
0x1800a6b16  lea     rcx, [rbp+140h+var_130]; this
0x1800a6b1a  call    ??1Package@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::Package::~Package(void)
0x1800a6b1f  mov     byte ptr [rbp+140h+arg_28], r15b
0x1800a6b26  lea     r9, [rbp+140h+arg_28]; bool *
0x1800a6b2d  mov     r8, [rbp+140h+packageFullName]; unsigned __int16 *
0x1800a6b34  mov     rdx, [rbp+140h+pSid]; pSid
0x1800a6b3b  mov     rcx, rdi; this
0x1800a6b3e  call    ?ExistsByUserSidAndPackageFullName@PackageUserStatus@Entity@StateRepository@@SAJAEAVDatabase@3@PEAXPEBGAEA_N@Z; StateRepository::Entity::PackageUserStatus::ExistsByUserSidAndPackageFullName(StateRepository::Database &,void *,ushort const *,bool &)
0x1800a6b43  mov     r14d, eax
0x1800a6b46  test    eax, eax
0x1800a6b48  jns     short loc_1800A6B67
0x1800a6b4a  mov     edx, 100h; void *
0x1800a6b4f  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appmodel\\staterepositor"...
0x1800a6b56  mov     r9d, r14d; char *
0x1800a6b59  mov     rcx, [rbp+148h]; this
0x1800a6b60  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6b65  jmp     short loc_1800A6B0E
0x1800a6b67  cmp     byte ptr [rbp+140h+arg_28], r15b
0x1800a6b6e  jnz     loc_1800A6D27
0x1800a6b74  mov     rcx, [rbp+140h+packageFullName]; packageFullName
0x1800a6b7b  call    cs:__imp_VerifyPackageFullName
0x1800a6b82  nop     dword ptr [rax+rax+00h]
0x1800a6b87  test    eax, eax
0x1800a6b89  jz      short loc_1800A6BAB
0x1800a6b8b  mov     rcx, [rbp+148h]; this
0x1800a6b92  mov     r9d, eax; char *
0x1800a6b95  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appmodel\\staterepositor"...
0x1800a6b9c  mov     edx, 104h; void *
0x1800a6ba1  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800a6ba6  jmp     loc_1800A6D0F
0x1800a6bab  test    esi, esi
0x1800a6bad  jz      loc_1800A6D0D
0x1800a6bb3  mov     [rbp+140h+var_170], r15
0x1800a6bb7  mov     [rbp+140h+var_168], r15
0x1800a6bbb  xorps   xmm0, xmm0
0x1800a6bbe  movdqa  [rbp+140h+var_160], xmm0
0x1800a6bc3  xorps   xmm1, xmm1
0x1800a6bc6  movdqa  [rbp+140h+var_150], xmm1
0x1800a6bcb  movdqa  [rbp+140h+var_140], xmm0
0x1800a6bd0  lea     r8, [rbp+140h+var_170]
0x1800a6bd4  mov     rdx, [rbp+140h+packageFullName]
0x1800a6bdb  mov     rcx, rdi
0x1800a6bde  call    ?GetOrAddIfNotExistByPackageFullName@PackageIdentity@Entity@StateRepository@@SAJAEAVDatabase@3@PEBGAEAV123@W4ExecutionFlags@3@@Z; StateRepository::Entity::PackageIdentity::GetOrAddIfNotExistByPackageFullName(StateRepository::Database &,ushort const *,StateRepository::Entity::PackageIdentity &,StateRepository::ExecutionFlags)
0x1800a6be3  mov     ebx, eax
0x1800a6be5  test    eax, eax
0x1800a6be7  jns     short loc_1800A6C09
0x1800a6be9  mov     rcx, [rbp+148h]; this
0x1800a6bf0  mov     r9d, eax; char *
0x1800a6bf3  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appmodel\\staterepositor"...
0x1800a6bfa  mov     edx, 109h; void *
0x1800a6bff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6c04  jmp     loc_1800A6CE3
0x1800a6c09  mov     [rsp+240h+var_1F0], r15
0x1800a6c0e  mov     qword ptr [rsp+240h+var_1E8], r15
0x1800a6c13  xorps   xmm0, xmm0
0x1800a6c16  movdqa  [rsp+240h+var_1E8+8], xmm0
0x1800a6c1c  xorps   xmm1, xmm1
0x1800a6c1f  movdqa  xmmword ptr [rsp+240h+var_1D8+8], xmm1
0x1800a6c25  movdqa  [rbp+140h+var_1C0], xmm0
0x1800a6c2a  mov     rdx, [rbp+140h+pSid]; void *
0x1800a6c31  lea     rcx, [rsp+240h+var_1F0]; this
0x1800a6c36  call    ?SetUserSid@User@Entity@StateRepository@@QEAAJPEAX@Z; StateRepository::Entity::User::SetUserSid(void *)
0x1800a6c3b  mov     ebx, eax
0x1800a6c3d  test    eax, eax
0x1800a6c3f  jns     short loc_1800A6C5E
0x1800a6c41  mov     edx, 10Bh; void *
0x1800a6c46  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appmodel\\staterepositor"...
0x1800a6c4d  mov     r9d, eax; char *
0x1800a6c50  mov     rcx, [rbp+148h]; this
0x1800a6c57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6c5c  jmp     short loc_1800A6CD9
0x1800a6c5e  xor     r8d, r8d
0x1800a6c61  mov     rdx, rdi
0x1800a6c64  lea     rcx, [rsp+240h+var_1F0]
0x1800a6c69  call    ?GetOrAddIfNotExist@User@Entity@StateRepository@@QEAAJAEAVDatabase@3@W4ExecutionFlags@3@@Z; StateRepository::Entity::User::GetOrAddIfNotExist(StateRepository::Database &,StateRepository::ExecutionFlags)
0x1800a6c6e  mov     ebx, eax
0x1800a6c70  test    eax, eax
0x1800a6c72  jns     short loc_1800A6C7B
0x1800a6c74  mov     edx, 10Ch
0x1800a6c79  jmp     short loc_1800A6C46
0x1800a6c7b  mov     [rbp+140h+var_1B0], r15
0x1800a6c7f  mov     [rbp+140h+var_1A8], r15
0x1800a6c83  mov     [rbp+140h+var_188], r15
0x1800a6c87  xorps   xmm0, xmm0
0x1800a6c8a  movdqa  [rbp+140h+var_180], xmm0
0x1800a6c8f  mov     rax, [rbp+140h+var_170]
0x1800a6c93  mov     [rbp+140h+var_1A0], rax
0x1800a6c97  mov     rax, [rsp+240h+var_1F0]
0x1800a6c9c  mov     [rbp+140h+var_198], rax
0x1800a6ca0  mov     [rbp+140h+var_190], esi
0x1800a6ca3  mov     rdx, rdi
0x1800a6ca6  lea     rcx, [rbp+140h+var_1B0]
0x1800a6caa  call    ?Add@PackageUserStatus@Entity@StateRepository@@QEAAJAEAVDatabase@3@W4ExecutionFlags@3@@Z; StateRepository::Entity::PackageUserStatus::Add(StateRepository::Database &,StateRepository::ExecutionFlags)
0x1800a6caf  mov     ebx, eax
0x1800a6cb1  test    eax, eax
0x1800a6cb3  jns     short loc_1800A6CF1
0x1800a6cb5  mov     rcx, [rbp+148h]; this
0x1800a6cbc  mov     r9d, eax; char *
0x1800a6cbf  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appmodel\\staterepositor"...
0x1800a6cc6  mov     edx, 112h; void *
0x1800a6ccb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6cd0  lea     rcx, [rbp+140h+var_188]; this
0x1800a6cd4  call    ?Reset@Blob@StateRepository@@QEAAXXZ; StateRepository::Blob::Reset(void)
0x1800a6cd9  lea     rcx, [rsp+240h+var_1F0]; this
0x1800a6cde  call    ??1User@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::User::~User(void)
0x1800a6ce3  lea     rcx, [rbp+140h+var_170]; this
0x1800a6ce7  call    ??1PackageIdentity@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::PackageIdentity::~PackageIdentity(void)
0x1800a6cec  jmp     loc_1800A69FE
0x1800a6cf1  lea     rcx, [rbp+140h+var_188]; this
0x1800a6cf5  call    ?Reset@Blob@StateRepository@@QEAAXXZ; StateRepository::Blob::Reset(void)
0x1800a6cfa  lea     rcx, [rsp+240h+var_1F0]; this
0x1800a6cff  call    ??1User@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::User::~User(void)
0x1800a6d04  lea     rcx, [rbp+140h+var_170]; this
0x1800a6d08  call    ??1PackageIdentity@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::PackageIdentity::~PackageIdentity(void)
0x1800a6d0d  xor     eax, eax
0x1800a6d0f  mov     rbx, [rsp+240h+arg_0]
0x1800a6d17  add     rsp, 220h
0x1800a6d1e  pop     r15
0x1800a6d20  pop     r14
0x1800a6d22  pop     rdi
0x1800a6d23  pop     rsi
0x1800a6d24  pop     rbp
0x1800a6d25  retn
0x1800a6d27  mov     [rbp+140h+arg_28], r15d
0x1800a6d2e  lea     r9, [rbp+140h+arg_28]; enum StateRepository::PackageStatus *
0x1800a6d35  mov     r8, [rbp+140h+packageFullName]; unsigned __int16 *
0x1800a6d3c  mov     rdx, [rbp+140h+pSid]; pSid
0x1800a6d43  mov     rcx, rdi; this
0x1800a6d46  call    ?GetStatusByUserSidAndPackageFullName@PackageUserStatus@Entity@StateRepository@@SAJAEAVDatabase@3@PEAXPEBGAEAW4PackageStatus@3@@Z; StateRepository::Entity::PackageUserStatus::GetStatusByUserSidAndPackageFullName(StateRepository::Database &,void *,ushort const *,StateRepository::PackageStatus &)
0x1800a6d4b  mov     r14d, eax
0x1800a6d4e  test    eax, eax
0x1800a6d50  jns     short loc_1800A6D5C
0x1800a6d52  mov     edx, 118h
0x1800a6d57  jmp     loc_1800A6B4F
0x1800a6d5c  not     ebx
0x1800a6d5e  and     ebx, [rbp+140h+arg_28]
0x1800a6d64  or      ebx, esi
0x1800a6d66  mov     [rsp+240h+var_218], ebx
0x1800a6d6a  cmp     ebx, [rbp+140h+arg_28]
0x1800a6d70  jz      short loc_1800A6D0D
0x1800a6d72  test    ebx, ebx
0x1800a6d74  jz      loc_1800A6E9C
0x1800a6d7a  xor     r8d, r8d
0x1800a6d7d  mov     rdx, rdi
0x1800a6d80  lea     rcx, [rsp+240h+var_210]
0x1800a6d85  call    ?Disable@DatabaseTriggers@StateRepository@@SA?AVAutoEnableTriggersScopeExit@2@PEAVDatabase@2@W4ExecutionFlags@2@@Z; StateRepository::DatabaseTriggers::Disable(StateRepository::Database *,StateRepository::ExecutionFlags)
0x1800a6d8a  mov     [rsp+240h+var_220], r15; int
0x1800a6d8f  lea     r9, [rsp+240h+var_218]
0x1800a6d94  lea     r8, [rbp+140h+packageFullName]
0x1800a6d9b  lea     rdx, [rbp+140h+pSid]
0x1800a6da2  lea     rcx, [rsp+240h+var_208]
0x1800a6da7  call    ??0_lambda_454331550775a661471245d7d7e1e5b3_@@QEAA@AEAPEAV?$Array@VContentTypeHelper@Internal@DEH@OSIntegration@@V?$ContainerOperations@VContentTypeHelper@Internal@DEH@OSIntegration@@V1234@@Common@@VNoKey@6@V?$ContainerOperations@VNoKey@Common@@VContentTypeHelper@Internal@DEH@OSIntegration@@@6@V?$ArrayOperations@VContentTypeHelper@Internal@DEH@OSIntegration@@VNoKey@Common@@@6@@Common@@0PEAV?$BaseLastOrFirstWriterWinsHandler@VContentTypeHandler@DEH@OSIntegration@@VContentTypeHelper@Internal@23@$0A@@Internal@DEH@OSIntegration@@@Z; _lambda_454331550775a661471245d7d7e1e5b3_::_lambda_454331550775a661471245d7d7e1e5b3_(Common::Array<OSIntegration::DEH::Internal::ContentTypeHelper,Common::ContainerOperations<OSIntegration::DEH::Internal::ContentTypeHelper,OSIntegration::DEH::Internal::ContentTypeHelper>,Common::NoKey,Common::ContainerOperations<Common::NoKey,OSIntegration::DEH::Internal::ContentTypeHelper>,Common::ArrayOperations<OSIntegration::DEH::Internal::ContentTypeHelper,Common::NoKey>> * &,Common::Array<OSIntegration::DEH::Internal::ContentTypeHelper,Common::ContainerOperations<OSIntegration::DEH::Internal::ContentTypeHelper,OSIntegration::DEH::Internal::ContentTypeHelper>,Common::NoKey,Common::ContainerOperations<Common::NoKey,OSIntegration::DEH::Internal::ContentTypeHelper>,Common::ArrayOperations<OSIntegration::DEH::Internal::ContentTypeHelper,Common::NoKey>> * &,OSIntegration::DEH::Internal::BaseLastOrFirstWriterWinsHandler<OSIntegration::DEH::ContentTypeHandler,OSIntegration::DEH::Internal::ContentTypeHelper,0> *)
0x1800a6dac  mov     rdx, rax
0x1800a6daf  lea     rcx, [rbp+140h+var_130]
0x1800a6db3  call    StateRepository__StatementExecution__StatementBinderFunc__StatementBinderFunc__lambda_0eea3193c0e0e0c31eda4019c1b8b6aa___
0x1800a6db8  lea     rcx, aUpdatePackageu; "UPDATE PackageUserStatus SET Status=?3 "...
0x1800a6dbf  mov     [rsp+240h+var_208], rcx
0x1800a6dc4  mov     [rsp+240h+var_200], r15
0x1800a6dc9  mov     [rsp+240h+var_1F8], r15
0x1800a6dce  lea     r9, [rsp+240h+var_220]; struct StateRepository::StatementExecution::StatementBinderFunc *
0x1800a6dd3  lea     r8, [rbp+140h+var_130]; struct StateRepository::StatementExecution::StatementDefinition *
0x1800a6dd7  lea     rdx, [rsp+240h+var_208]; struct StateRepository::Database *
0x1800a6ddc  mov     rcx, rdi; this
0x1800a6ddf  call    ?PrepareAndBind@StatementExecution@StateRepository@@YAJAEAVDatabase@2@AEBUStatementDefinition@12@AEAVStatementBinderFunc@12@AEAVStatement@2@@Z; StateRepository::StatementExecution::PrepareAndBind(StateRepository::Database &,StateRepository::StatementExecution::StatementDefinition const &,StateRepository::StatementExecution::StatementBinderFunc &,StateRepository::Statement &)
0x1800a6de4  mov     ebx, eax
0x1800a6de6  test    eax, eax
0x1800a6de8  jns     short loc_1800A6DF1
0x1800a6dea  mov     edx, 134h
0x1800a6def  jmp     short loc_1800A6E06
0x1800a6df1  lea     rcx, [rsp+240h+var_220]; this
0x1800a6df6  call    ?FetchNoRow@Statement@StateRepository@@QEAAJXZ; StateRepository::Statement::FetchNoRow(void)
0x1800a6dfb  mov     ebx, eax
0x1800a6dfd  test    eax, eax
0x1800a6dff  jns     short loc_1800A6E46
0x1800a6e01  mov     edx, 135h; void *
0x1800a6e06  mov     r9d, eax; char *
0x1800a6e09  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appmodel\\staterepositor"...
0x1800a6e10  mov     rcx, [rbp+148h]; this
0x1800a6e17  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6e1c  mov     rcx, [rbp+140h+var_130]
0x1800a6e20  mov     rdx, [rcx]
0x1800a6e23  mov     rax, [rdx]
0x1800a6e26  xor     edx, edx
0x1800a6e28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6e2d  lea     rcx, [rsp+240h+var_220]; this
0x1800a6e32  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x1800a6e37  lea     rcx, [rsp+240h+var_210]; this
0x1800a6e3c  call    ??1AutoEnableTriggersScopeExit@StateRepository@@QEAA@XZ; StateRepository::AutoEnableTriggersScopeExit::~AutoEnableTriggersScopeExit(void)
0x1800a6e41  jmp     loc_1800A69FE
0x1800a6e46  lea     rdx, [rsp+240h+var_220]; struct StateRepository::Statement *
0x1800a6e4b  mov     rcx, rdi; this
0x1800a6e4e  call    ?AddToCache@Database@StateRepository@@QEAAJAEAVStatement@2@@Z; StateRepository::Database::AddToCache(StateRepository::Statement &)
0x1800a6e53  test    eax, eax
0x1800a6e55  jns     short loc_1800A6E72
0x1800a6e57  mov     rcx, [rbp+148h]; this
0x1800a6e5e  mov     r9d, eax; char *
0x1800a6e61  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appmodel\\staterepositor"...
0x1800a6e68  mov     edx, 137h; void *
0x1800a6e6d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800a6e72  mov     rcx, [rbp+140h+var_130]
0x1800a6e76  mov     rax, [rcx]
0x1800a6e79  xor     edx, edx
0x1800a6e7b  mov     rax, [rax]
0x1800a6e7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6e83  lea     rcx, [rsp+240h+var_220]; this
0x1800a6e88  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x1800a6e8d  lea     rcx, [rsp+240h+var_210]; this
0x1800a6e92  call    ??1AutoEnableTriggersScopeExit@StateRepository@@QEAA@XZ; StateRepository::AutoEnableTriggersScopeExit::~AutoEnableTriggersScopeExit(void)
0x1800a6e97  jmp     loc_1800A6D0D
0x1800a6e9c  mov     r8, [rbp+140h+packageFullName]
0x1800a6ea3  mov     rdx, [rbp+140h+pSid]
0x1800a6eaa  mov     rcx, rdi
0x1800a6ead  call    ?DeleteByUserSidAndPackageFullName@PackageUserStatus@Entity@StateRepository@@SAJAEAVDatabase@3@PEAXPEBGW4ExecutionFlags@3@@Z; StateRepository::Entity::PackageUserStatus::DeleteByUserSidAndPackageFullName(StateRepository::Database &,void *,ushort const *,StateRepository::ExecutionFlags)
  ... truncated ...
```
