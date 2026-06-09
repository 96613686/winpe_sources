# ShouldSkipPackage(ushort const *)

- ea: `0x18000eaec`
- end: `0x18000ee1c`
- name: `?ShouldSkipPackage@@YA_NPEBG@Z`
- size: `816`
- prototype: `bool __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180006f7c`

## callees

- `0x180001960`
- `0x1800052a8`
- `0x180006d54`
- `0x1800073e8`
- `0x18000e534`
- `0x18000e71c`
- `0x18000eaec`
- `0x18000efb4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000eb5a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000eb5a`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x18000eb28`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x18000eb28`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18000ebfb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18000edce`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18000ebfb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18000edce`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000ed74`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000ed9b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000ed74`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000ed9b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18000ecf2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18000ecf2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000ed33`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000ed33`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x18000eca7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x18000eca7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18000ebd7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18000ebd7`

## string_xrefs

- `0x18000edfd`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Manager.hpp`
- `0x18000ecb6`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18000ed01`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18000ec34`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-package.hpp`
- `0x18000ed45`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-package.hpp`
- `0x18000ed59`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-package.hpp`
- `0x18000ece6`: `InstalledLocation`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall ShouldSkipPackage(const unsigned __int16 *a1)
{
  __int64 v2; // rbx
  char v3; // bl
  int v4; // ebx
  int v5; // r9d
  __int64 v6; // rcx
  bool v7; // si
  int v8; // eax
  int v9; // r9d
  unsigned __int64 v10; // r8
  __int64 v11; // rcx
  __int64 v12; // rdi
  int v13; // eax
  int v14; // r9d
  unsigned int v15; // ebx
  unsigned __int64 v16; // r8
  __int64 v17; // rcx
  __int64 v18; // rcx
  int Field_UInt32; // eax
  int v20; // r9d
  int v21; // r9d
  __int64 v22; // rcx
  int Field_String; // eax
  __int64 v24; // rcx
  bool v25; // zf
  __int64 v26; // rcx
  unsigned int v28; // edx
  int v29; // r9d
  bool v30; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v31; // [rsp+38h] [rbp-C8h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v33; // [rsp+48h] [rbp-B8h] BYREF
  __int64 *v34; // [rsp+50h] [rbp-B0h]
  __int64 v35; // [rsp+58h] [rbp-A8h] BYREF
  char v36; // [rsp+60h] [rbp-A0h]
  __int64 v37; // [rsp+68h] [rbp-98h] BYREF
  __int128 v38; // [rsp+70h] [rbp-90h] BYREF
  __int64 v39; // [rsp+80h] [rbp-80h]
  _QWORD v40[4]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v41; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v42; // [rsp+B0h] [rbp-50h]
  int v43; // [rsp+C0h] [rbp-40h]
  __int64 v44; // [rsp+C8h] [rbp-38h]
  __int64 v45; // [rsp+D0h] [rbp-30h]
  WCHAR packageFamilyName[72]; // [rsp+E0h] [rbp-20h] BYREF

  packageFamilyNameLength = 65;
  if ( PackageFamilyNameFromFullName(a1, &packageFamilyNameLength, packageFamilyName) )
  {
LABEL_5:
    v3 = 0;
    if ( !IsCapabilityLicensedApp(a1) )
      return v3;
    v33 = 0;
    v38 = 0;
    v39 = 0;
    memset(v40, 0, sizeof(v40));
    v41 = 0;
    v42 = 0;
    v43 = 0;
    v44 = 0;
    v45 = 0;
    v34 = &v33;
    v35 = 0;
    v36 = 1;
    v4 = SRCacheManager_Open(0, &v35);
    if ( v36 )
    {
      v6 = *v34;
      *v34 = v35;
      if ( v6 )
        SRCacheManager_Close();
    }
    if ( v4 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        (wil::details::in1diag3 *)0xA5,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Manager.hpp",
        (wil::details *)(unsigned int)v4,
        v5);
      wil::details::in1diag3::_Throw_Hr((wil::details::in1diag3 *)0x68, v28, (const char *)(unsigned int)v4, v29);
    }
    v7 = 0;
    v30 = 0;
    v37 = 0;
    v8 = StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(
           (struct StateRepository::Cache::Manager_NoThrow *)&v33,
           a1,
           &v37);
    if ( v8 < 0 )
    {
      v10 = (unsigned int)v8;
      v11 = 1165;
LABEL_12:
      wil::details::in1diag3::Return_Hr(
        (wil::details::in1diag3 *)v11,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-package.hpp",
        (wil::details *)v10,
        v9);
      goto LABEL_37;
    }
    v12 = v37;
    if ( v37 )
    {
      v31 = 0;
      v13 = StateRepository::Cache::Entity::Package_NoThrow::Open(
              (struct StateRepository::Cache::Manager_NoThrow *)&v33,
              v37,
              (struct StateRepository::Cache::Context_NoThrow *)&v31,
              &v30);
      v15 = v13;
      if ( v13 < 0 )
      {
        v16 = (unsigned int)v13;
        v17 = 1110;
LABEL_29:
        wil::details::in1diag3::Return_Hr(
          (wil::details::in1diag3 *)v17,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-package.hpp",
          (wil::details *)v16,
          v14);
        v25 = v31 == 0;
        v31 = 0;
        if ( !v25 )
          SRCacheContext_Close();
        v10 = v15;
        v11 = 1168;
        goto LABEL_12;
      }
      v7 = v30;
      v18 = v31;
      if ( v30 )
      {
        Field_UInt32 = SRCacheContext_GetField_UInt32(v31, L"Flags", (char *)v40 + 4);
        v15 = Field_UInt32;
        if ( Field_UInt32 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            (wil::details::in1diag3 *)0x221,
            (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
            (wil::details *)(unsigned int)Field_UInt32,
            v20);
          v22 = 2103;
LABEL_28:
          wil::details::in1diag3::Return_Hr(
            (wil::details::in1diag3 *)v22,
            (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-package.hpp",
            (wil::details *)v15,
            v21);
          v16 = v15;
          v17 = 1115;
          goto LABEL_29;
        }
        v34 = &v41;
        v35 = 0;
        v36 = 1;
        Field_String = SRCacheContext_GetField_String(v31, L"InstalledLocation", &v35);
        v15 = Field_String;
        if ( Field_String >= 0 )
          v15 = 0;
        else
          wil::details::in1diag3::Return_Hr(
            (wil::details::in1diag3 *)0x246,
            (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
            (wil::details *)(unsigned int)Field_String,
            v21);
        if ( v36 )
        {
          v24 = *v34;
          *v34 = v35;
          if ( v24 )
            SRCache_Free();
        }
        if ( (v15 & 0x80000000) != 0 )
        {
          v22 = 2123;
          goto LABEL_28;
        }
        *(_QWORD *)&v38 = v12;
        v18 = v31;
      }
      v31 = 0;
      if ( v18 )
        SRCacheContext_Close();
    }
    if ( v7 )
    {
      v3 = 1;
      if ( (v40[0] & 0x80000000000LL) != 0 )
      {
LABEL_38:
        StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v38);
        v26 = v33;
        v33 = 0;
        if ( v26 )
          SRCacheManager_Close();
        return v3;
      }
    }
LABEL_37:
    v3 = 0;
    goto LABEL_38;
  }
  v2 = 0;
  while ( CompareStringOrdinal(off_180014130[v2], -1, packageFamilyName, packageFamilyNameLength - 1, 1) != 2 )
  {
    if ( (unsigned __int64)++v2 >= 2 )
      goto LABEL_5;
  }
  return 1;
}

```

## disassembly

```asm
0x18000eaec  mov     [rsp-8+arg_8], rbx
0x18000eaf1  mov     [rsp-8+arg_10], rsi
0x18000eaf6  push    rbp
0x18000eaf7  push    rdi
0x18000eaf8  push    r14
0x18000eafa  lea     rbp, [rsp-80h]
0x18000eaff  sub     rsp, 180h
0x18000eb06  mov     rax, cs:__security_cookie
0x18000eb0d  xor     rax, rsp
0x18000eb10  mov     [rbp+90h+var_20], rax
0x18000eb14  mov     rdi, rcx
0x18000eb17  mov     [rsp+190h+packageFamilyNameLength], 41h ; 'A'
0x18000eb1f  lea     r8, [rbp+90h+packageFamilyName]; packageFamilyName
0x18000eb23  lea     rdx, [rsp+190h+packageFamilyNameLength]; packageFamilyNameLength
0x18000eb28  call    cs:__imp_PackageFamilyNameFromFullName
0x18000eb2e  xor     r14d, r14d
0x18000eb31  test    eax, eax
0x18000eb33  jnz     short loc_18000EB72
0x18000eb35  mov     ebx, r14d
0x18000eb38  mov     r9d, [rsp+190h+packageFamilyNameLength]
0x18000eb3d  dec     r9d; cchCount2
0x18000eb40  lea     rcx, off_180014130; "Microsoft.AAD.BrokerPlugin_8wekyb3d8bbw"...
0x18000eb47  mov     [rsp+190h+bIgnoreCase], 1; bIgnoreCase
0x18000eb4f  lea     r8, [rbp+90h+packageFamilyName]; lpString2
0x18000eb53  or      edx, 0FFFFFFFFh; cchCount1
0x18000eb56  mov     rcx, [rcx+rbx*8]; lpString1
0x18000eb5a  call    cs:__imp_CompareStringOrdinal
0x18000eb60  cmp     eax, 2
0x18000eb63  jz      loc_18000EC45
0x18000eb69  inc     rbx
0x18000eb6c  cmp     rbx, 2
0x18000eb70  jb      short loc_18000EB38
0x18000eb72  mov     bl, r14b
0x18000eb75  mov     rcx, rdi; unsigned __int16 *
0x18000eb78  call    ?IsCapabilityLicensedApp@@YA_NPEBG@Z; IsCapabilityLicensedApp(ushort const *)
0x18000eb7d  test    al, al
0x18000eb7f  jz      loc_18000EDD4
0x18000eb85  mov     [rsp+190h+var_148], r14
0x18000eb8a  xorps   xmm0, xmm0
0x18000eb8d  movdqa  [rsp+190h+var_120], xmm0
0x18000eb93  mov     [rbp+90h+var_110], r14
0x18000eb97  mov     [rbp+90h+var_108], r14
0x18000eb9b  mov     [rbp+90h+var_100], r14
0x18000eb9f  mov     [rbp+90h+var_F8], r14
0x18000eba3  mov     [rbp+90h+var_F0], r14
0x18000eba7  mov     [rbp+90h+var_E8], r14
0x18000ebab  movdqa  [rbp+90h+var_E0], xmm0
0x18000ebb0  mov     [rbp+90h+var_D0], r14d
0x18000ebb4  mov     [rbp+90h+var_C8], r14
0x18000ebb8  mov     [rbp+90h+var_C0], r14
0x18000ebbc  lea     rax, [rsp+190h+var_148]
0x18000ebc1  mov     [rsp+190h+var_140], rax
0x18000ebc6  mov     [rsp+190h+var_138], r14
0x18000ebcb  mov     [rsp+190h+var_130], 1
0x18000ebd0  lea     rdx, [rsp+190h+var_138]
0x18000ebd5  xor     ecx, ecx
0x18000ebd7  call    cs:__imp_SRCacheManager_Open
0x18000ebdd  mov     ebx, eax
0x18000ebdf  cmp     [rsp+190h+var_130], r14b
0x18000ebe4  jz      short loc_18000EC01
0x18000ebe6  mov     r8, [rsp+190h+var_140]
0x18000ebeb  mov     rcx, [r8]
0x18000ebee  mov     rdx, [rsp+190h+var_138]
0x18000ebf3  mov     [r8], rdx
0x18000ebf6  test    rcx, rcx
0x18000ebf9  jz      short loc_18000EC01
0x18000ebfb  call    cs:__imp_SRCacheManager_Close
0x18000ec01  test    ebx, ebx
0x18000ec03  js      loc_18000EDFA
0x18000ec09  mov     sil, r14b
0x18000ec0c  mov     [rsp+190h+var_160], r14b
0x18000ec11  mov     [rsp+190h+var_128], r14
0x18000ec16  lea     r8, [rsp+190h+var_128]; __int64 *
0x18000ec1b  mov     rdx, rdi; unsigned __int16 *
0x18000ec1e  lea     rcx, [rsp+190h+var_148]; struct StateRepository::Cache::Manager_NoThrow *
0x18000ec23  call    ?GetByPackageFullName@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z; StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)
0x18000ec28  test    eax, eax
0x18000ec2a  jns     short loc_18000EC4C
0x18000ec2c  mov     r8d, eax; wil::details *
0x18000ec2f  mov     ecx, 48Dh; this
0x18000ec34  lea     rdx, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000ec3b  call    ?Return_Hr@in1diag3@details@wil@@YAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(uint,char const *,long)
0x18000ec40  jmp     loc_18000EDB1
0x18000ec45  mov     bl, 1
0x18000ec47  jmp     loc_18000EDD4
0x18000ec4c  mov     rdi, [rsp+190h+var_128]
0x18000ec51  test    rdi, rdi
0x18000ec54  jz      loc_18000EDA1
0x18000ec5a  mov     [rsp+190h+var_158], r14
0x18000ec5f  lea     r9, [rsp+190h+var_160]; bool *
0x18000ec64  lea     r8, [rsp+190h+var_158]; struct StateRepository::Cache::Context_NoThrow *
0x18000ec69  mov     rdx, rdi; __int64
0x18000ec6c  lea     rcx, [rsp+190h+var_148]; struct StateRepository::Cache::Manager_NoThrow *
0x18000ec71  call    ?Open@Package_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::Package_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x18000ec76  mov     ebx, eax
0x18000ec78  test    eax, eax
0x18000ec7a  jns     short loc_18000EC89
0x18000ec7c  mov     r8d, eax
0x18000ec7f  mov     ecx, 456h
0x18000ec84  jmp     loc_18000ED59
0x18000ec89  mov     sil, [rsp+190h+var_160]
0x18000ec8e  mov     rcx, [rsp+190h+var_158]
0x18000ec93  test    sil, sil
0x18000ec96  jz      loc_18000ED91
0x18000ec9c  lea     r8, [rbp+90h+var_108+4]
0x18000eca0  lea     rdx, aFlags; "Flags"
0x18000eca7  call    cs:__imp_SRCacheContext_GetField_UInt32
0x18000ecad  mov     ebx, eax
0x18000ecaf  test    eax, eax
0x18000ecb1  jns     short loc_18000ECCE
0x18000ecb3  mov     r8d, eax; wil::details *
0x18000ecb6  lea     rdx, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000ecbd  mov     ecx, 221h; this
0x18000ecc2  call    ?Return_Hr@in1diag3@details@wil@@YAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(uint,char const *,long)
0x18000ecc7  mov     ecx, 837h
0x18000eccc  jmp     short loc_18000ED42
0x18000ecce  lea     rax, [rbp+90h+var_E8]
0x18000ecd2  mov     [rsp+190h+var_140], rax
0x18000ecd7  mov     [rsp+190h+var_138], r14
0x18000ecdc  mov     [rsp+190h+var_130], 1
0x18000ece1  lea     r8, [rsp+190h+var_138]
0x18000ece6  lea     rdx, aInstalledlocat; "InstalledLocation"
0x18000eced  mov     rcx, [rsp+190h+var_158]
0x18000ecf2  call    cs:__imp_SRCacheContext_GetField_String
0x18000ecf8  mov     ebx, eax
0x18000ecfa  test    eax, eax
0x18000ecfc  jns     short loc_18000ED14
0x18000ecfe  mov     r8d, eax; wil::details *
0x18000ed01  lea     rdx, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000ed08  mov     ecx, 246h; this
0x18000ed0d  call    ?Return_Hr@in1diag3@details@wil@@YAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(uint,char const *,long)
0x18000ed12  jmp     short loc_18000ED17
0x18000ed14  mov     ebx, r14d
0x18000ed17  cmp     [rsp+190h+var_130], r14b
0x18000ed1c  jz      short loc_18000ED39
0x18000ed1e  mov     rdx, [rsp+190h+var_140]
0x18000ed23  mov     rcx, [rdx]
0x18000ed26  mov     rax, [rsp+190h+var_138]
0x18000ed2b  mov     [rdx], rax
0x18000ed2e  test    rcx, rcx
0x18000ed31  jz      short loc_18000ED39
0x18000ed33  call    cs:__imp_SRCache_Free
0x18000ed39  test    ebx, ebx
0x18000ed3b  jns     short loc_18000ED87
0x18000ed3d  mov     ecx, 84Bh; this
0x18000ed42  mov     r8d, ebx; wil::details *
0x18000ed45  lea     rdx, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000ed4c  call    ?Return_Hr@in1diag3@details@wil@@YAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(uint,char const *,long)
0x18000ed51  mov     r8d, ebx; wil::details *
0x18000ed54  mov     ecx, 45Bh; this
0x18000ed59  lea     rdx, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000ed60  call    ?Return_Hr@in1diag3@details@wil@@YAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(uint,char const *,long)
0x18000ed65  mov     rcx, [rsp+190h+var_158]
0x18000ed6a  test    rcx, rcx
0x18000ed6d  mov     [rsp+190h+var_158], r14
0x18000ed72  jz      short loc_18000ED7A
0x18000ed74  call    cs:__imp_SRCacheContext_Close
0x18000ed7a  mov     r8d, ebx
0x18000ed7d  mov     ecx, 490h
0x18000ed82  jmp     loc_18000EC34
0x18000ed87  mov     qword ptr [rsp+190h+var_120], rdi
0x18000ed8c  mov     rcx, [rsp+190h+var_158]
0x18000ed91  test    rcx, rcx
0x18000ed94  mov     [rsp+190h+var_158], r14
0x18000ed99  jz      short loc_18000EDA1
0x18000ed9b  call    cs:__imp_SRCacheContext_Close
0x18000eda1  test    sil, sil
0x18000eda4  jz      short loc_18000EDB1
0x18000eda6  test    dword ptr [rbp+90h+var_108+4], 800h
0x18000edad  mov     bl, 1
0x18000edaf  jnz     short loc_18000EDB4
0x18000edb1  mov     bl, r14b
0x18000edb4  lea     rcx, [rsp+190h+var_120]; this
0x18000edb9  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18000edbe  nop
0x18000edbf  mov     rcx, [rsp+190h+var_148]
0x18000edc4  mov     [rsp+190h+var_148], r14
0x18000edc9  test    rcx, rcx
0x18000edcc  jz      short loc_18000EDD4
0x18000edce  call    cs:__imp_SRCacheManager_Close
0x18000edd4  mov     al, bl
0x18000edd6  mov     rcx, [rbp+90h+var_20]
0x18000edda  xor     rcx, rsp; StackCookie
0x18000eddd  call    __security_check_cookie
0x18000ede2  lea     r11, [rsp+190h+var_10]
0x18000edea  mov     rbx, [r11+28h]
0x18000edee  mov     rsi, [r11+30h]
0x18000edf2  mov     rsp, r11
0x18000edf5  pop     r14
0x18000edf7  pop     rdi
0x18000edf8  pop     rbp
0x18000edf9  retn
0x18000edfa  mov     r8d, ebx; wil::details *
0x18000edfd  lea     rdx, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000ee04  mov     ecx, 0A5h; this
0x18000ee09  call    ?Return_Hr@in1diag3@details@wil@@YAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(uint,char const *,long)
0x18000ee0e  mov     r8d, ebx; char *
0x18000ee11  mov     ecx, 68h ; 'h'; this
0x18000ee16  call    ?_Throw_Hr@in1diag3@details@wil@@YAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(uint,char const *,long)
```
