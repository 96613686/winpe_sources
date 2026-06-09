# DeviceRegistrationStateApi::PopulateJoinInfo(_JOIN_TYPE,_CERT_CONTEXT const *,ushort const *,int,int,_DSREG_ACCOUNT_INFO_2 *)

- ea: `0x18001c2a0`
- end: `0x18001e48b`
- name: `?PopulateJoinInfo@DeviceRegistrationStateApi@@SAJW4_JOIN_TYPE@@PEBU_CERT_CONTEXT@@PEBGHHPEAU_DSREG_ACCOUNT_INFO_2@@@Z`
- size: `8683`
- prototype: `static int __high(enum _JOIN_TYPE, const struct _CERT_CONTEXT *, const unsigned __int16 *, int, int, struct _DSREG_ACCOUNT_INFO_2 *)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18001be10`

## callees

- `0x18001b65c`
- `0x18001b74c`
- `0x18001b8f0`
- `0x18001c2a0`
- `0x18001ea7c`
- `0x18001eb00`
- `0x18001eb60`
- `0x18001f17c`
- `0x18001f854`
- `0x180020d28`
- `0x180021378`
- `0x18002161c`
- `0x180035970`
- `0x18004a8ec`
- `0x18004aa08`
- `0x18004d79c`
- `0x18005366c`
- `0x18005cee0`
- `0x18005d60c`
- `0x18005db30`
- `0x18005dd44`
- `0x1800606dc`
- `0x1800aaf1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c512`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c527`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c512`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c527`
- `RPCRT4!UuidToStringW` at `0x18001e308`
- `RPCRT4!UuidToStringW` at `0x18001e308`
- `RPCRT4!RpcStringFreeW` at `0x18001e439`
- `RPCRT4!RpcStringFreeW` at `0x18001e439`
- `RPCRT4!UuidIsNil` at `0x18001e02c`
- `RPCRT4!UuidIsNil` at `0x18001e02c`
- `CRYPT32!CertFreeCertificateContext` at `0x18001e3da`
- `CRYPT32!CertFreeCertificateContext` at `0x18001e3da`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18001c504`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18001c504`

## string_xrefs

- `0x18001c831`: `CopyStringSafeW`
- `0x18001c8eb`: `CopyStringSafeW`
- `0x18001c9a2`: `CopyStringSafeW`
- `0x18001ca59`: `CopyStringSafeW`
- `0x18001cb10`: `CopyStringSafeW`
- `0x18001cbc7`: `CopyStringSafeW`
- `0x18001cc7e`: `CopyStringSafeW`
- `0x18001cd35`: `CopyStringSafeW`
- `0x18001cdec`: `CopyStringSafeW`
- `0x18001cea3`: `CopyStringSafeW`
- `0x18001cf5d`: `CopyStringSafeW`
- `0x18001d017`: `CopyStringSafeW`
- `0x18001d0d1`: `CopyStringSafeW`
- `0x18001d18b`: `CopyStringSafeW`
- `0x18001d248`: `CopyStringSafeW`
- `0x18001d305`: `CopyStringSafeW`
- `0x18001d3c2`: `CopyStringSafeW`
- `0x18001d47f`: `CopyStringSafeW`
- `0x18001d53c`: `CopyStringSafeW`
- `0x18001d5f9`: `CopyStringSafeW`
- `0x18001d6b6`: `CopyStringSafeW`
- `0x18001d773`: `CopyStringSafeW`
- `0x18001d830`: `CopyStringSafeW`
- `0x18001d8ed`: `CopyStringSafeW`
- `0x18001d9aa`: `CopyStringSafeW`
- `0x18001da90`: `CopyStringSafeW`
- `0x18001db4d`: `CopyStringSafeW`
- `0x18001dc0a`: `CopyStringSafeW`
- `0x18001dce8`: `CopyStringSafeW`
- `0x18001dda5`: `CopyStringSafeW`
- `0x18001de62`: `CopyStringSafeW`
- `0x18001df22`: `CopyStringSafeW`
- `0x18001c63d`: `JoinStatusStorage::ReadJoinStatus`
- `0x18001c3c3`: `Logger::WriteNullOrEmptyParameterFailureEvent`
- `0x18001c3bc`: `EventWriteNullOrEmptyParameterFailureEvent`
- `0x18001e085`: `StringCompare`
- `0x18001e19a`: `StringCompare`
- `0x18001c7ee`: `CopyStringNullSafeW`
- `0x18001c808`: `CopyStringNullSafeW`
- `0x18001c838`: `CopyStringNullSafeW`
- `0x18001c865`: `CopyStringNullSafeW`
- `0x18001c8a5`: `CopyStringNullSafeW`
- `0x18001c8bf`: `CopyStringNullSafeW`
- `0x18001c8f2`: `CopyStringNullSafeW`
- `0x18001c91f`: `CopyStringNullSafeW`
- `0x18001c95f`: `CopyStringNullSafeW`
- `0x18001c979`: `CopyStringNullSafeW`
- `0x18001c9a9`: `CopyStringNullSafeW`
- `0x18001c9d6`: `CopyStringNullSafeW`
- `0x18001ca16`: `CopyStringNullSafeW`
- `0x18001ca30`: `CopyStringNullSafeW`
- `0x18001ca60`: `CopyStringNullSafeW`
- `0x18001ca8d`: `CopyStringNullSafeW`
- `0x18001cacd`: `CopyStringNullSafeW`
- `0x18001cae7`: `CopyStringNullSafeW`
- `0x18001cb17`: `CopyStringNullSafeW`
- `0x18001cb44`: `CopyStringNullSafeW`
- `0x18001cb84`: `CopyStringNullSafeW`
- `0x18001cb9e`: `CopyStringNullSafeW`
- `0x18001cbce`: `CopyStringNullSafeW`
- `0x18001cbfb`: `CopyStringNullSafeW`
- `0x18001cc3b`: `CopyStringNullSafeW`
- `0x18001cc55`: `CopyStringNullSafeW`
- `0x18001cc85`: `CopyStringNullSafeW`
- `0x18001ccb2`: `CopyStringNullSafeW`
- `0x18001ccf2`: `CopyStringNullSafeW`
- `0x18001cd0c`: `CopyStringNullSafeW`
- `0x18001cd3c`: `CopyStringNullSafeW`
- `0x18001cd69`: `CopyStringNullSafeW`
- `0x18001cda9`: `CopyStringNullSafeW`
- `0x18001cdc3`: `CopyStringNullSafeW`
- `0x18001cdf3`: `CopyStringNullSafeW`
- `0x18001ce20`: `CopyStringNullSafeW`
- `0x18001ce60`: `CopyStringNullSafeW`
- `0x18001ce7a`: `CopyStringNullSafeW`
- `0x18001ceaa`: `CopyStringNullSafeW`
- `0x18001ced7`: `CopyStringNullSafeW`
- `0x18001cf1a`: `CopyStringNullSafeW`
- `0x18001cf34`: `CopyStringNullSafeW`
- `0x18001cf64`: `CopyStringNullSafeW`
- `0x18001cf91`: `CopyStringNullSafeW`
- `0x18001cfd4`: `CopyStringNullSafeW`
- `0x18001cfee`: `CopyStringNullSafeW`
- `0x18001d01e`: `CopyStringNullSafeW`
- `0x18001d04b`: `CopyStringNullSafeW`
- `0x18001d08e`: `CopyStringNullSafeW`
- `0x18001d0a8`: `CopyStringNullSafeW`
- `0x18001d0d8`: `CopyStringNullSafeW`
- `0x18001d105`: `CopyStringNullSafeW`
- `0x18001d148`: `CopyStringNullSafeW`
- `0x18001d162`: `CopyStringNullSafeW`
- `0x18001d192`: `CopyStringNullSafeW`
- `0x18001d1bf`: `CopyStringNullSafeW`
- `0x18001d202`: `CopyStringNullSafeW`
- `0x18001d21c`: `CopyStringNullSafeW`
- `0x18001d24f`: `CopyStringNullSafeW`
- `0x18001d27c`: `CopyStringNullSafeW`
- `0x18001d2bf`: `CopyStringNullSafeW`
- `0x18001d2d9`: `CopyStringNullSafeW`
- `0x18001d30c`: `CopyStringNullSafeW`
- `0x18001d339`: `CopyStringNullSafeW`
- `0x18001d37c`: `CopyStringNullSafeW`
- `0x18001d396`: `CopyStringNullSafeW`
- `0x18001d3c9`: `CopyStringNullSafeW`
- `0x18001d3f6`: `CopyStringNullSafeW`
- `0x18001d439`: `CopyStringNullSafeW`
- `0x18001d453`: `CopyStringNullSafeW`
- `0x18001d486`: `CopyStringNullSafeW`
- `0x18001d4b3`: `CopyStringNullSafeW`
- `0x18001d4f6`: `CopyStringNullSafeW`
- `0x18001d510`: `CopyStringNullSafeW`
- `0x18001d543`: `CopyStringNullSafeW`
- `0x18001d570`: `CopyStringNullSafeW`
- `0x18001d5b3`: `CopyStringNullSafeW`
- `0x18001d5cd`: `CopyStringNullSafeW`
- `0x18001d600`: `CopyStringNullSafeW`
- `0x18001d62d`: `CopyStringNullSafeW`
- `0x18001d670`: `CopyStringNullSafeW`
- `0x18001d68a`: `CopyStringNullSafeW`
- `0x18001d6bd`: `CopyStringNullSafeW`
- `0x18001d6ea`: `CopyStringNullSafeW`
- `0x18001d72d`: `CopyStringNullSafeW`
- `0x18001d747`: `CopyStringNullSafeW`
- `0x18001d77a`: `CopyStringNullSafeW`
- `0x18001d7a7`: `CopyStringNullSafeW`
- `0x18001d7ea`: `CopyStringNullSafeW`
- `0x18001d804`: `CopyStringNullSafeW`
- `0x18001d837`: `CopyStringNullSafeW`
- `0x18001d864`: `CopyStringNullSafeW`
- `0x18001d8a7`: `CopyStringNullSafeW`
- `0x18001d8c1`: `CopyStringNullSafeW`
- `0x18001d8f4`: `CopyStringNullSafeW`
- `0x18001d921`: `CopyStringNullSafeW`
- `0x18001d964`: `CopyStringNullSafeW`
- `0x18001d97e`: `CopyStringNullSafeW`
- `0x18001d9b1`: `CopyStringNullSafeW`
- `0x18001d9de`: `CopyStringNullSafeW`
- `0x18001da4a`: `CopyStringNullSafeW`
- `0x18001da64`: `CopyStringNullSafeW`
- `0x18001da97`: `CopyStringNullSafeW`
- `0x18001dac4`: `CopyStringNullSafeW`
- `0x18001db07`: `CopyStringNullSafeW`
- `0x18001db21`: `CopyStringNullSafeW`
- `0x18001db54`: `CopyStringNullSafeW`
- `0x18001db81`: `CopyStringNullSafeW`
- `0x18001dbc4`: `CopyStringNullSafeW`
- `0x18001dbde`: `CopyStringNullSafeW`
- `0x18001dc11`: `CopyStringNullSafeW`
- `0x18001dc3e`: `CopyStringNullSafeW`
- `0x18001dca2`: `CopyStringNullSafeW`
- `0x18001dcbc`: `CopyStringNullSafeW`
- `0x18001dcef`: `CopyStringNullSafeW`
- `0x18001dd1c`: `CopyStringNullSafeW`
- `0x18001dd5f`: `CopyStringNullSafeW`
- `0x18001dd79`: `CopyStringNullSafeW`
- `0x18001ddac`: `CopyStringNullSafeW`
- `0x18001ddd9`: `CopyStringNullSafeW`
- `0x18001de1c`: `CopyStringNullSafeW`
- `0x18001de36`: `CopyStringNullSafeW`
- `0x18001de69`: `CopyStringNullSafeW`
- `0x18001de96`: `CopyStringNullSafeW`
- `0x18001ded9`: `CopyStringNullSafeW`
- `0x18001def3`: `CopyStringNullSafeW`
- `0x18001df29`: `CopyStringNullSafeW`
- `0x18001df59`: `CopyStringNullSafeW`
- `0x18001dfcc`: `CopyStringNullSafeW`
- `0x18001e282`: `CopyStringNullSafeW`
- `0x18001e2d8`: `CopyStringNullSafeW`
- `0x18001e364`: `CopyStringNullSafeW`

## pseudocode

```c
__int64 __fastcall DeviceRegistrationStateApi::PopulateJoinInfo(
        unsigned int a1,
        const struct _CERT_CONTEXT *a2,
        unsigned __int16 *a3,
        int a4,
        int a5,
        __int64 a6)
{
  void *v8; // r12
  struct struct_join_status *v9; // rbx
  NgcStatusStorage *v10; // r13
  unsigned __int16 *ExtensionGuidValueByOid; // rsi
  __int64 v12; // r8
  unsigned int v13; // eax
  void *v14; // rcx
  __int128 *v15; // rax
  __int128 *v16; // rcx
  __int64 v17; // rdx
  __int128 v18; // xmm0
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int128 v26; // xmm1
  __int128 v27; // xmm0
  __int128 v28; // xmm1
  __int128 v29; // xmm0
  const unsigned __int16 *v30; // rcx
  __int64 v31; // r8
  const CERT_CONTEXT *v32; // r14
  signed int LastError; // eax
  int TenantId; // eax
  struct_join_status *v35; // rax
  unsigned int v36; // r12d
  const wchar_t *v37; // rax
  const wchar_t *v38; // rax
  __int64 v39; // rcx
  unsigned int v40; // eax
  __int128 v41; // xmm1
  __m128i v42; // xmm2
  __m128i v43; // xmm3
  __int128 v44; // xmm0
  unsigned __int16 **v45; // rdx
  __int64 v46; // xmm1_8
  bool v47; // zf
  BOOL v48; // eax
  unsigned int v49; // r14d
  const unsigned __int16 *v50; // rcx
  int v51; // eax
  const wchar_t *v52; // rcx
  unsigned int v53; // r14d
  const unsigned __int16 *v54; // rcx
  int v55; // eax
  const wchar_t *v56; // rcx
  unsigned __int16 **v57; // rdx
  unsigned int v58; // r14d
  const unsigned __int16 *v59; // rcx
  int v60; // eax
  const wchar_t *v61; // rcx
  unsigned __int16 **v62; // rdx
  unsigned int v63; // r14d
  const unsigned __int16 *v64; // rcx
  int v65; // eax
  const wchar_t *v66; // rcx
  unsigned __int16 **v67; // rdx
  unsigned int v68; // r14d
  const unsigned __int16 *v69; // rcx
  int v70; // eax
  const wchar_t *v71; // rcx
  unsigned __int16 **v72; // rdx
  unsigned int v73; // r14d
  const unsigned __int16 *v74; // rcx
  int v75; // eax
  const wchar_t *v76; // rcx
  unsigned __int16 **v77; // rdx
  unsigned int v78; // r14d
  const unsigned __int16 *v79; // rcx
  int v80; // eax
  const wchar_t *v81; // rcx
  unsigned __int16 **v82; // rdx
  unsigned int v83; // r14d
  const unsigned __int16 *v84; // rcx
  int v85; // eax
  const wchar_t *v86; // rcx
  unsigned __int16 **v87; // rdx
  unsigned int v88; // r14d
  const unsigned __int16 *v89; // rcx
  int v90; // eax
  const wchar_t *v91; // rcx
  unsigned __int16 **v92; // rdx
  unsigned int v93; // r14d
  const unsigned __int16 *v94; // rcx
  int v95; // eax
  const wchar_t *v96; // rcx
  unsigned __int16 **v97; // rdx
  unsigned int v98; // r14d
  const unsigned __int16 *v99; // rcx
  int v100; // eax
  const wchar_t *v101; // rcx
  unsigned __int16 **v102; // rdx
  unsigned int v103; // r14d
  const unsigned __int16 *v104; // rcx
  int v105; // eax
  const wchar_t *v106; // rcx
  unsigned __int16 **v107; // rdx
  unsigned int v108; // r14d
  const unsigned __int16 *v109; // rcx
  int v110; // eax
  const wchar_t *v111; // rcx
  unsigned __int16 **v112; // rdx
  unsigned int v113; // r14d
  const unsigned __int16 *v114; // rcx
  int v115; // eax
  const wchar_t *v116; // rcx
  unsigned __int16 **v117; // rdx
  unsigned int v118; // r14d
  const unsigned __int16 *v119; // rcx
  int v120; // eax
  const wchar_t *v121; // rcx
  unsigned __int16 **v122; // rdx
  unsigned int v123; // r14d
  const unsigned __int16 *v124; // rcx
  int v125; // eax
  const wchar_t *v126; // rcx
  unsigned __int16 **v127; // rdx
  unsigned int v128; // r14d
  const unsigned __int16 *v129; // rcx
  int v130; // eax
  const wchar_t *v131; // rcx
  unsigned __int16 **v132; // rdx
  unsigned int v133; // r14d
  const unsigned __int16 *v134; // rcx
  int v135; // eax
  const wchar_t *v136; // rcx
  unsigned __int16 **v137; // rdx
  unsigned int v138; // r14d
  const unsigned __int16 *v139; // rcx
  int v140; // eax
  const wchar_t *v141; // rcx
  unsigned __int16 **v142; // rdx
  unsigned int v143; // r14d
  const unsigned __int16 *v144; // rcx
  int v145; // eax
  const wchar_t *v146; // rcx
  unsigned __int16 **v147; // rdx
  unsigned int v148; // r14d
  const unsigned __int16 *v149; // rcx
  int v150; // eax
  const wchar_t *v151; // rcx
  unsigned __int16 **v152; // rdx
  unsigned int v153; // r14d
  const unsigned __int16 *v154; // rcx
  int v155; // eax
  const wchar_t *v156; // rcx
  unsigned __int16 **v157; // rdx
  unsigned int v158; // r14d
  const unsigned __int16 *v159; // rcx
  int v160; // eax
  const wchar_t *v161; // rcx
  unsigned __int16 **v162; // rdx
  unsigned int v163; // r14d
  const unsigned __int16 *v164; // rcx
  int v165; // eax
  const wchar_t *v166; // rcx
  unsigned __int16 **v167; // rdx
  unsigned int v168; // r14d
  const unsigned __int16 *v169; // rcx
  int v170; // eax
  const wchar_t *v171; // rcx
  _WORD *v172; // rax
  BOOL v173; // eax
  unsigned __int16 **v174; // rdx
  unsigned int v175; // r14d
  const unsigned __int16 *v176; // rcx
  int v177; // eax
  const wchar_t *v178; // rcx
  unsigned __int16 **v179; // rdx
  unsigned int v180; // r14d
  const unsigned __int16 *v181; // rcx
  int v182; // eax
  const wchar_t *v183; // rcx
  unsigned __int16 **v184; // rdx
  unsigned int v185; // r14d
  const unsigned __int16 *v186; // rcx
  int v187; // eax
  const wchar_t *v188; // rcx
  unsigned __int16 **v189; // rdx
  unsigned int v190; // r14d
  const unsigned __int16 *v191; // rcx
  int v192; // eax
  const wchar_t *v193; // rcx
  unsigned __int16 **v194; // rdx
  unsigned int v195; // r14d
  const unsigned __int16 *v196; // rcx
  int v197; // eax
  const wchar_t *v198; // rcx
  unsigned __int16 **v199; // rdx
  unsigned int v200; // r14d
  const unsigned __int16 *v201; // rcx
  int v202; // eax
  const wchar_t *v203; // rcx
  unsigned __int16 **v204; // rdx
  unsigned int v205; // r14d
  const unsigned __int16 *v206; // rcx
  int v207; // eax
  const wchar_t *v208; // rcx
  int v209; // r14d
  const wchar_t *v210; // rax
  int v211; // r14d
  unsigned int v212; // r8d
  const unsigned __int16 *v213; // r15
  const unsigned __int16 *v214; // rcx
  const unsigned __int16 *v215; // rdx
  unsigned int v216; // r8d
  const wchar_t *v217; // rax
  const wchar_t *v218; // r9
  unsigned __int16 *v219; // r8
  const unsigned __int16 *v220; // rcx
  const wchar_t *v221; // rax
  _QWORD *v222; // rax
  unsigned __int16 **v223; // rdx
  const unsigned __int16 *v224; // rcx
  const wchar_t *v225; // rax
  const wchar_t *v226; // rax
  unsigned int v227; // eax
  const wchar_t *v228; // rax
  RPC_STATUS Status; // [rsp+34h] [rbp-CCh] BYREF
  void *Block; // [rsp+38h] [rbp-C8h]
  unsigned __int16 *v233; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v234; // [rsp+48h] [rbp-B8h]
  RPC_WSTR StringUuid; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v236; // [rsp+58h] [rbp-A8h]
  _BYTE v237[28]; // [rsp+84h] [rbp-7Ch] BYREF
  _BYTE v238[336]; // [rsp+A0h] [rbp-60h] BYREF
  UUID v239[4]; // [rsp+1F0h] [rbp+F0h] BYREF
  UUID Uuid; // [rsp+230h] [rbp+130h] BYREF
  _BYTE v241[4]; // [rsp+240h] [rbp+140h] BYREF
  _BYTE v242[48]; // [rsp+244h] [rbp+144h]

  v234 = a1;
  v236 = a3;
  *(_QWORD *)&Uuid.Data1 = 0;
  v8 = 0;
  Block = 0;
  v9 = 0;
  v233 = 0;
  v10 = 0;
  StringUuid = 0;
  memset(v239, 0, sizeof(v239));
  Status = 0;
  if ( a6 )
  {
    memset_0(v238, 0, sizeof(v238));
    v15 = (__int128 *)a6;
    v16 = (__int128 *)v238;
    v17 = 2;
    do
    {
      v15 += 8;
      v18 = *v16;
      v19 = v16[1];
      v16 += 8;
      *(v15 - 8) = v18;
      v20 = *(v16 - 6);
      *(v15 - 7) = v19;
      v21 = *(v16 - 5);
      *(v15 - 6) = v20;
      v22 = *(v16 - 4);
      *(v15 - 5) = v21;
      v23 = *(v16 - 3);
      *(v15 - 4) = v22;
      v24 = *(v16 - 2);
      *(v15 - 3) = v23;
      v25 = *(v16 - 1);
      *(v15 - 2) = v24;
      *(v15 - 1) = v25;
      --v17;
    }
    while ( v17 );
    v26 = v16[1];
    *v15 = *v16;
    v27 = v16[2];
    v15[1] = v26;
    v28 = v16[3];
    v15[2] = v27;
    v29 = v16[4];
    v15[3] = v28;
    v15[4] = v29;
    if ( !a2 )
    {
      LODWORD(ExtensionGuidValueByOid) = -2147024809;
      Logger::TraceError(
        L"%s: \"%s\" should not be null.",
        L"DeviceRegistrationStateApi::PopulateJoinInfo",
        &stru_1800EA828);
      Logger::WriteNullOrEmptyParameterFailureEvent(
        L"DeviceRegistrationStateApi::PopulateJoinInfo",
        (const unsigned __int16 *)&stru_1800EA828);
      operator delete(0);
      v14 = Block;
      goto LABEL_394;
    }
    if ( ((a1 - 1) & 0xFFFFFFFB) != 0 )
    {
      LODWORD(ExtensionGuidValueByOid) = -2147024809;
      v30 = L"%s: Invalid join type %d. Only DEVICE and WORKPLACE are allowed.";
      v31 = a1;
LABEL_12:
      Logger::TraceError(v30, L"DeviceRegistrationStateApi::PopulateJoinInfo", v31);
      operator delete(0);
      v14 = Block;
      goto LABEL_394;
    }
    v32 = CertDuplicateCertificateContext(a2);
    if ( !v32 )
    {
      LastError = GetLastError();
      LODWORD(ExtensionGuidValueByOid) = LastError;
      if ( LastError > 0 )
        LODWORD(ExtensionGuidValueByOid) = (unsigned __int16)LastError | 0x80070000;
      v31 = GetLastError();
      v30 = L"%s: CertDuplicateCertificateContext failed with error code: 0x%08x";
      goto LABEL_12;
    }
    TenantId = RegistrationCertStatus::GetTenantId(a2, (unsigned __int16 **)&Uuid, &Status);
    LODWORD(ExtensionGuidValueByOid) = TenantId;
    if ( TenantId < 0 )
    {
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"DeviceRegistrationStateApi::PopulateJoinInfo",
        L"RegistrationCertStatus::GetTenantId",
        (unsigned int)TenantId);
LABEL_389:
      CertFreeCertificateContext(v32);
      v8 = *(void **)&Uuid.Data1;
      goto LABEL_390;
    }
    ExtensionGuidValueByOid = (unsigned __int16 *)(unsigned int)CertificateUtil::FindExtensionGuidValueByOid(
                                                                  "1.2.840.113556.1.5.284.2",
                                                                  a2,
                                                                  &v233);
    Logger::TraceVerbose(L"%s - hr: 0x%08x", L"RegistrationCertStatus::GetDeviceId", ExtensionGuidValueByOid);
    if ( (int)ExtensionGuidValueByOid < 0 )
    {
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"DeviceRegistrationStateApi::PopulateJoinInfo",
        L"RegistrationCertStatus::GetDeviceId",
        (unsigned int)ExtensionGuidValueByOid);
LABEL_388:
      Block = v233;
      goto LABEL_389;
    }
    v35 = (struct_join_status *)operator new(0x140u, (const struct std::nothrow_t *)&std::nothrow);
    v9 = v35;
    if ( v35 )
    {
      struct_join_status::Clear(v35);
      v36 = v234;
      LODWORD(ExtensionGuidValueByOid) = JoinStatusStorage::ReadJoinStatus(v234 == 1, a2, a4, v9, a5);
      if ( (int)ExtensionGuidValueByOid < 0 )
      {
        v37 = L"TRUE";
        if ( !a4 )
          v37 = L"FALSE";
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
          L"DeviceRegistrationStateApi::PopulateJoinInfo",
          L"JoinStatusStorage::ReadJoinStatus",
          (unsigned int)ExtensionGuidValueByOid,
          v37);
        if ( !a4 )
          goto LABEL_388;
      }
      v10 = (NgcStatusStorage *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
      if ( v10 )
      {
        *(_QWORD *)v10 = 0;
        *((_QWORD *)v10 + 1) = 0;
        LODWORD(ExtensionGuidValueByOid) = NgcStatusStorage::Load(v10);
        if ( (int)ExtensionGuidValueByOid < 0 )
        {
          v38 = L"TRUE";
          if ( !a4 )
            v38 = L"FALSE";
          Logger::TraceError(
            L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
            L"DeviceRegistrationStateApi::PopulateJoinInfo",
            L"NgcStatusStorage::Load",
            (unsigned int)ExtensionGuidValueByOid,
            v38);
          if ( !a4 )
            goto LABEL_388;
        }
        if ( *((_QWORD *)v10 + 1) && (v39 = *(_QWORD *)v10) != 0 )
        {
          v40 = *(_DWORD *)v39;
          v41 = *(_OWORD *)(v39 + 36);
          v42 = *(__m128i *)(v39 + 4);
          v43 = *(__m128i *)(v39 + 48);
          *(_OWORD *)&v242[16] = *(_OWORD *)(v39 + 20);
          *(_OWORD *)&v242[32] = v41;
        }
        else
        {
          v42 = 0;
          v43 = 0;
          memset(v237, 0, sizeof(v237));
          v40 = 0;
          *(_OWORD *)&v242[16] = 0;
          *(_OWORD *)&v242[32] = *(_OWORD *)v237;
        }
        v44 = *(_OWORD *)&v242[20];
        v45 = (unsigned __int16 **)(a6 + 24);
        v239[0].Data1 = v40;
        v46 = *(_QWORD *)&v242[36];
        v47 = v36 == 1;
        *(__m128i *)v242 = v42;
        v8 = 0;
        *(_QWORD *)&v239[1].Data1 = *(_QWORD *)&v242[12];
        LODWORD(ExtensionGuidValueByOid) = -2147024809;
        *(_QWORD *)&v239[0].Data2 = v42.m128i_i64[0];
        v48 = !v47;
        *(_QWORD *)&v239[3].Data1 = v43.m128i_i64[0];
        v47 = Status == 0;
        *(_DWORD *)a6 = v48 + 1;
        *(_QWORD *)(a6 + 16) = v233;
        *(_QWORD *)(a6 + 32) = *(_QWORD *)&Uuid.Data1;
        *(_DWORD *)(a6 + 60) = !v47;
        *(_DWORD *)&v239[0].Data4[4] = _mm_cvtsi128_si32(_mm_srli_si128(v42, 8));
        *(_QWORD *)v239[2].Data4 = v46;
        *(_QWORD *)v239[3].Data4 = _mm_srli_si128(v43, 8).m128i_u64[0];
        *(_QWORD *)(a6 + 8) = v32;
        Block = 0;
        *(_OWORD *)v239[1].Data4 = v44;
        if ( a6 == -24 )
        {
          v49 = -2147024809;
          Logger::TraceError(L"%s: \"%s\" should not be null.", L"CopyStringNullSafeW", L"ppszOut");
          Logger::WriteNullOrEmptyParameterFailureEvent(L"CopyStringNullSafeW", L"ppszOut");
        }
        else
        {
          v50 = (const unsigned __int16 *)*((_QWORD *)v9 + 1);
          *v45 = 0;
          if ( !v50 )
            goto LABEL_44;
          v51 = CopyStringSafeW(v50, v45);
          v49 = v51;
          if ( v51 >= 0 )
            goto LABEL_44;
          Logger::TraceError(
            L"%s: %s failed with error code: 0x%08x.",
            L"CopyStringNullSafeW",
            L"CopyStringSafeW",
            (unsigned int)v51);
        }
        v52 = L"TRUE";
        if ( !a4 )
          v52 = L"FALSE";
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
          L"DeviceRegistrationStateApi::PopulateJoinInfo",
          L"CopyStringNullSafeW",
          v49,
          v52);
        if ( !a4 )
        {
          LODWORD(ExtensionGuidValueByOid) = v49;
          goto LABEL_390;
        }
LABEL_44:
        if ( a6 == -40 )
        {
          v53 = -2147024809;
          Logger::TraceError(L"%s: \"%s\" should not be null.", L"CopyStringNullSafeW", L"ppszOut");
          Logger::WriteNullOrEmptyParameterFailureEvent(L"CopyStringNullSafeW", L"ppszOut");
        }
        else
        {
          v54 = (const unsigned __int16 *)*((_QWORD *)v9 + 3);
          *(_QWORD *)(a6 + 40) = 0;
          if ( !v54 )
            goto LABEL_53;
          v55 = CopyStringSafeW(v54, (unsigned __int16 **)(a6 + 40));
          v53 = v55;
          if ( v55 >= 0 )
            goto LABEL_53;
          Logger::TraceError(
            L"%s: %s failed with error code: 0x%08x.",
            L"CopyStringNullSafeW",
            L"CopyStringSafeW",
            (unsigned int)v55);
        }
        v56 = L"TRUE";
        if ( !a4 )
          v56 = L"FALSE";
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
          L"DeviceRegistrationStateApi::PopulateJoinInfo",
          L"CopyStringNullSafeW",
          v53,
          v56);
        if ( !a4 )
        {
          LODWORD(ExtensionGuidValueByOid) = v53;
          goto LABEL_390;
        }
LABEL_53:
        v57 = (unsigned __int16 **)(a6 + 64);
        if ( a6 == -64 )
        {
          v58 = -2147024809;
          Logger::TraceError(L"%s: \"%s\" should not be null.", L"CopyStringNullSafeW", L"ppszOut");
          Logger::WriteNullOrEmptyParameterFailureEvent(L"CopyStringNullSafeW", L"ppszOut");
        }
        else
        {
          v59 = (const unsigned __int16 *)*((_QWORD *)v9 + 4);
          *v57 = 0;
          if ( !v59 )
            goto LABEL_62;
          v60 = CopyStringSafeW(v59, v57);
          v58 = v60;
          if ( v60 >= 0 )
            goto LABEL_62;
          Logger::TraceError(
            L"%s: %s failed with error code: 0x%08x.",
            L"CopyStringNullSafeW",
            L"CopyStringSafeW",
            (unsigned int)v60);
        }
        v61 = L"TRUE";
        if ( !a4 )
          v61 = L"FALSE";
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
          L"DeviceRegistrationStateApi::PopulateJoinInfo",
          L"CopyStringNullSafeW",
          v58,
          v61);
        if ( !a4 )
        {
          LODWORD(ExtensionGuidValueByOid) = v58;
          goto LABEL_390;
        }
LABEL_62:
        v62 = (unsigned __int16 **)(a6 + 72);
        if ( a6 == -72 )
        {
          v63 = -2147024809;
          Logger::TraceError(L"%s: \"%s\" should not be null.", L"CopyStringNullSafeW", L"ppszOut");
          Logger::WriteNullOrEmptyParameterFailureEvent(L"CopyStringNullSafeW", L"ppszOut");
        }
        else
        {
          v64 = (const unsigned __int16 *)*((_QWORD *)v9 + 5);
          *v62 = 0;
          if ( !v64 )
            goto LABEL_71;
          v65 = CopyStringSafeW(v64, v62);
          v63 = v65;
          if ( v65 >= 0 )
            goto LABEL_71;
          Logger::TraceError(
            L"%s: %s failed with error code: 0x%08x.",
            L"CopyStringNullSafeW",
            L"CopyStringSafeW",
            (unsigned int)v65);
        }
        v66 = L"TRUE";
        if ( !a4 )
          v66 = L"FALSE";
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
          L"DeviceRegistrationStateApi::PopulateJoinInfo",
          L"CopyStringNullSafeW",
          v63,
          v66);
        if ( !a4 )
        {
          LODWORD(ExtensionGuidValueByOid) = v63;
          goto LABEL_390;
        }
LABEL_71:
        v67 = (unsigned __int16 **)(a6 + 80);
        if ( a6 == -80 )
        {
          v68 = -2147024809;
          Logger::TraceError(L"%s: \"%s\" should not be null.", L"CopyStringNullSafeW", L"ppszOut");
          Logger::WriteNullOrEmptyParameterFailureEvent(L"CopyStringNullSafeW", L"ppszOut");
        }
        else
        {
          v69 = (const unsigned __int16 *)*((_QWORD *)v9 + 6);
          *v67 = 0;
          if ( !v69 )
            goto LABEL_80;
          v70 = CopyStringSafeW(v69, v67);
          v68 = v70;
          if ( v70 >= 0 )
            goto LABEL_80;
          Logger::TraceError(
            L"%s: %s failed with error code: 0x%08x.",
            L"CopyStringNullSafeW",
            L"CopyStringSafeW",
            (unsigned int)v70);
        }
        v71 = L"TRUE";
        if ( !a4 )
          v71 = L"FALSE";
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
          L"DeviceRegistrationStateApi::PopulateJoinInfo",
          L"CopyStringNullSafeW",
          v68,
          v71);
        if ( !a4 )
        {
          LODWORD(ExtensionGuidValueByOid) = v68;
          goto LABEL_390;
        }
LABEL_80:
        v72 = (unsigned __int16 **)(a6 + 88);
        if ( a6 == -88 )
        {
          v73 = -2147024809;
          Logger::TraceError(L"%s: \"%s\" should not be null.", L"CopyStringNullSafeW", L"ppszOut");
          Logger::WriteNullOrEmptyParameterFailureEvent(L"CopyStringNullSafeW", L"ppszOut");
        }
        else
        {
          v74 = (const unsigned __int16 *)*((_QWORD *)v9 + 7);
          *v72 = 0;
          if ( !v74 )
            goto LABEL_89;
          v75 = CopyStringSafeW(v74, v72);
          v73 = v75;
          if ( v75 >= 0 )
            goto LABEL_89;
          Logger::TraceError(
            L"%s: %s failed with error code: 0x%08x.",
            L"CopyStringNullSafeW",
            L"CopyStringSafeW",
            (unsigned int)v75);
        }
        v76 = L"TRUE";
        if ( !a4 )
          v76 = L"FALSE";
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
          L"DeviceRegistrationStateApi::PopulateJoinInfo",
          L"CopyStringNullSafeW",
          v73,
          v76);
        if ( !a4 )
        {
          LODWORD(ExtensionGuidValueByOid) = v73;
          goto LABEL_390;
        }
LABEL_89:
        v77 = (unsigned __int16 **)(a6 + 96);
        if ( a6 == -96 )
        {
          v78 = -2147024809;
          Logger::TraceError(L"%s: \"%s\" should not be null.", L"CopyStringNullSafeW", L"ppszOut");
          Logger::WriteNullOrEmptyParameterFailureEvent(L"CopyStringNullSafeW", L"ppszOut");
        }
        else
        {
          v79 = (const unsigned __int16 *)*((_QWORD *)v9 + 8);
          *v77 = 0;
          if ( !v79 )
            goto LABEL_98;
          v80 = CopyStringSafeW(v79, v77);
          v78 = v80;
          if ( v80 >= 0 )
            goto LABEL_98;
          Logger::TraceError(
            L"%s: %s failed with error code: 0x%08x.",
            L"CopyStringNullSafeW",
            L"CopyStringSafeW",
            (unsigned int)v80);
        }
        v81 = L"TRUE";
        if ( !a4 )
          v81 = L"FALSE";
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
          L"DeviceRegistrationStateApi::PopulateJoinInfo",
          L"CopyStringNullSafeW",
          v78,
          v81);
        if ( !a4 )
        {
          LODWORD(ExtensionGuidValueByOid) = v78;
          goto LABEL_390;
        }
LABEL_98:
        v82 = (unsigned __int16 **)(a6 + 104);
        if ( a6 == -104 )
        {
          v83 = -2147024809;
          Logger::TraceError(L"%s: \"%s\" should not be null.", L"CopyStringNullSafeW", L"ppszOut");
          Logger::WriteNullOrEmptyParameterFailureEvent(L"CopyStringNullSafeW", L"ppszOut");
        }
        else
        {
          v84 = (const unsigned __int16 *)*((_QWORD *)v9 + 9);
          *v82 = 0;
          if ( !v84 )
            goto LABEL_107;
          v85 = CopyStringSafeW(v84, v82);
          v83 = v85;
          if ( v85 >= 0 )
            goto LABEL_107;
          Logger::TraceError(
            L"%s: %s failed with error code: 0x%08x.",
            L"CopyStringNullSafeW",
            L"CopyStringSafeW",
            (unsigned int)v85);
        }
        v86 = L"TRUE";
        if ( !a4 )
          v86 = L"FALSE";
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
          L"DeviceRegistrationStateApi::PopulateJoinInfo",
          L"CopyStringNullSafeW",
          v83,
          v86);
        if ( !a4 )
        {
          LODWORD(ExtensionGuidValueByOid) = v83;
          goto LABEL_390;
        }
LABEL_107:
        v87 = (unsigned __int16 **)(a6 + 112);
        if ( a6 == -112 )
        {
          v88 = -2147024809;
          Logger::TraceError(L"%s: \"%s\" should not be null.", L"CopyStringNullSafeW", L"ppszOut");
          Logger::WriteNullOrEmptyParameterFailureEvent(L"CopyStringNullSafeW", L"ppszOut");
        }
        else
        {
          v89 = (const unsigned __int16 *)*((_QWORD *)v9 + 10);
          *v87 = 0;
          if ( !v89 )
            goto LABEL_116;
          v90 = CopyStringSafeW(v89, v87);
          v88 = v90;
          if ( v90 >= 0 )
            goto LABEL_116;
          Logger::TraceError(
            L"%s: %s failed with error code: 0x%08x.",
            L"CopyStringNullSafeW",
            L"CopyStringSafeW",
            (unsigned int)v90);
        }
        v91 = L"TRUE";
        if ( !a4 )
          v91 = L"FALSE";
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
          L"DeviceRegistrationStateApi::PopulateJoinInfo",
          L"CopyStringNullSafeW",
          v88,
          v91);
        if ( !a4 )
        {
          LODWORD(ExtensionGuidValueByOid) = v88;
          goto LABEL_390;
        }
LABEL_116:
        v92 = (unsigned __int16 **)(a6 + 120);
        if ( a6 == -120 )
        {
          v93 = -2147024809;
          Logger::TraceError(L"%s: \"%s\" should not be null.", L"CopyStringNullSafeW", L"ppszOut");
          Logger::WriteNullOrEmptyParameterFailureEvent(L"CopyStringNullSafeW", L"ppszOut");
        }
        else
        {
          v94 = (const unsigned __int16 *)*((_QWORD *)v9 + 11);
          *v92 = 0;
          if ( !v94 )
            goto LABEL_125;
          v95 = CopyStringSafeW(v94, v92);
          v93 = v95;
          if ( v95 >= 0 )
            goto LABEL_125;
          Logger::TraceError(
            L"%s: %s failed with error code: 0x%08x.",
            L"CopyStringNullSafeW",
            L"CopyStringSafeW",
            (unsigned int)v95);
        }
        v96 = L"TRUE";
        if ( !a4 )
          v96 = L"FALSE";
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
          L"DeviceRegistrationStateApi::PopulateJoinInfo",
          L"CopyStringNullSafeW",
          v93,
          v96);
        if ( !a4 )
        {
          LODWORD(ExtensionGuidValueByOid) = v93;
          goto LABEL_390;
        }
LABEL_125:
        v97 = (unsigned __int16 **)(a6 + 128);
        if ( a6 == -128 )
        {
          v98 = -2147024809;
          Logger::TraceError(L"%s: \"%s\" should not be null.", L"CopyStringNullSafeW", L"ppszOut");
          Logger::WriteNullOrEmptyParameterFailureEvent(L"CopyStringNullSafeW", L"ppszOut");
        }
        else
        {
          v99 = (const unsigned __int16 *)*((_QWORD *)v9 + 12);
          *v97 = 0;
          if ( !v99 )
            goto LABEL_134;
          v100 = CopyStringSafeW(v99, v97);
          v98 = v100;
          if ( v100 >= 0 )
            goto LABEL_134;
          Logger::TraceError(
            L"%s: %s failed with error code: 0x%08x.",
            L"CopyStringNullSafeW",
            L"CopyStringSafeW",
            (unsigned int)v100);
        }
        v101 = L"TRUE";
        if ( !a4 )
          v101 = L"FALSE";
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
          L"DeviceRegistrationStateApi::PopulateJoinInfo",
          L"CopyStringNullSafeW",
          v98,
          v101);
        if ( !a4 )
        {
          LODWORD(ExtensionGuidValueByOid) = v98;
          goto LABEL_390;
        }
LABEL_134:
        v102 = (unsigned __int16 **)(a6 + 136);
        if ( a6 == -136 )
        {
          v103 = -2147024809;
          Logger::TraceError(L"%s: \"%s\" should not be null.", L"CopyStringNullSafeW", L"ppszOut");
          Logger::WriteNullOrEmptyParameterFailureEvent(L"CopyStringNullSafeW", L"ppszOut");
        }
        else
        {
          v104 = (const unsigned __int16 *)*((_QWORD *)v9 + 13);
          *v102 = 0;
          if ( !v104 )
            goto LABEL_143;
          v105 = CopyStringSafeW(v104, v102);
          v103 = v105;
          if ( v105 >= 0 )
            goto LABEL_143;
          Logger::TraceError(
            L"%s: %s failed with error code: 0x%08x.",
            L"CopyStringNullSafeW",
            L"CopyStringSafeW",
            (unsigned int)v105);
        }
        v106 = L"TRUE";
        if ( !a4 )
          v106 = L"FALSE";
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
          L"DeviceRegistrationStateApi::PopulateJoinInfo",
          L"CopyStringNullSafeW",
          v103,
          v106);
        if ( !a4 )
        {
          LODWORD(ExtensionGuidValueByOid) = v103;
          goto LABEL_390;
        }
LABEL_143:
        v107 = (unsigned __int16 **)(a6 + 144);
        if ( a6 == -144 )
        {
          v108 = -2147024809;
          Logger::TraceError(L"%s: \"%s\" should not be null.", L"CopyStringNullSafeW", L"ppszOut");
          Logger::WriteNullOrEmptyParameterFailureEvent(L"CopyStringNullSafeW", L"ppszOut");
        }
        else
        {
          v109 = (const unsigned __int16 *)*((_QWORD *)v9 + 14);
          *v107 = 0;
          if ( !v109 )
            goto LABEL_152;
          v110 = CopyStringSafeW(v109, v107);
          v108 = v110;
          if ( v110 >= 0 )
            goto LABEL_152;
          Logger::TraceError(
            L"%s: %s failed with error code: 0x%08x.",
            L"CopyStringNullSafeW",
            L"CopyStringSafeW",
            (unsigned int)v110);
        }
        v111 = L"TRUE";
        if ( !a4 )
          v111 = L"FALSE";
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
          L"DeviceRegistrationStateApi::PopulateJoinInfo",
          L"CopyStringNullSafeW",
          v108,
          v111);
        if ( !a4 )
        {
          LODWORD(ExtensionGuidValueByOid) = v108;
          goto LABEL_390;
        }
LABEL_152:
        v112 = (unsigned __int16 **)(a6 + 152);
        if ( a6 == -152 )
        {
          v113 = -2147024809;
          Logger::TraceError(L"%s: \"%s\" should not be null.", L"CopyStringNullSafeW", L"ppszOut");
          Logger::WriteNullOrEmptyParameterFailureEvent(L"CopyStringNullSafeW", L"ppszOut");
        }
        else
        {
          v114 = (const unsigned __int16 *)*((_QWORD *)v9 + 15);
          *v112 = 0;
          if ( !v114 )
            goto LABEL_161;
          v115 = CopyStringSafeW(v114, v112);
          v113 = v115;
          if ( v115 >= 0 )
            goto LABEL_161;
          Logger::TraceError(
            L"%s: %s failed with error code: 0x%08x.",
            L"CopyStringNullSafeW",
            L"CopyStringSafeW",
            (unsigned int)v115);
        }
        v116 = L"TRUE";
        if ( !a4 )
          v116 = L"FALSE";
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
          L"DeviceRegistrationStateApi::PopulateJoinInfo",
          L"CopyStringNullSafeW",
          v113,
          v116);
        if ( !a4 )
        {
          LODWORD(ExtensionGuidValueByOid) = v113;
          goto LABEL_390;
        }
LABEL_161:
        v117 = (unsigned __int16 **)(a6 + 160);
        if ( a6 == -160 )
        {
          v118 = -2147024809;
          Logger::TraceError(L"%s: \"%s\" should not be null.", L"CopyStringNullSafeW", L"ppszOut");
          Logger::WriteNullOrEmptyParameterFailureEvent(L"CopyStringNullSafeW", L"ppszOut");
        }
        else
        {
          v119 = (const unsigned __int16 *)*((_QWORD *)v9 + 16);
          *v117 = 0;
          if ( !v119 )
            goto LABEL_170;
          v120 = CopyStringSafeW(v119, v117);
          v118 = v120;
          if ( v120 >= 0 )
            goto LABEL_170;
          Logger::TraceError(
            L"%s: %s failed with error code: 0x%08x.",
            L"CopyStringNullSafeW",
            L"CopyStringSafeW",
            (unsigned int)v120);
        }
        v121 = L"TRUE";
        if ( !a4 )
          v121 = L"FALSE";
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
          L"DeviceRegistrationStateApi::PopulateJoinInfo",
          L"CopyStringNullSafeW",
          v118,
          v121);
        if ( !a4 )
        {
          LODWORD(ExtensionGuidValueByOid) = v118;
          goto LABEL_390;
        }
LABEL_170:
        v122 = (unsigned __int16 **)(a6 + 168);
        if ( a6 == -168 )
        {
          v123 = -2147024809;
          Logger::TraceError(L"%s: \"%s\" should not be null.", L"CopyStringNullSafeW", L"ppszOut");
          Logger::WriteNullOrEmptyParameterFailureEvent(L"CopyStringNullSafeW", L"ppszOut");
        }
        else
        {
          v124 = (const unsigned __int16 *)*((_QWORD *)v9 + 17);
          *v122 = 0;
          if ( !v124 )
            goto LABEL_179;
          v125 = CopyStringSafeW(v124, v122);
          v123 = v125;
          if ( v125 >= 0 )
            goto LABEL_179;
          Logger::TraceError(
            L"%s: %s failed with error code: 0x%08x.",
            L"CopyStringNullSafeW",
            L"CopyStringSafeW",
            (unsigned int)v125);
        }
        v126 = L"TRUE";
        if ( !a4 )
          v126 = L"FALSE";
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
          L"DeviceRegistrationStateApi::PopulateJoinInfo",
          L"CopyStringNullSafeW",
          v123,
          v126);
        if ( !a4 )
        {
          LODWORD(ExtensionGuidValueByOid) = v123;
          goto LABEL_390;
        }
LABEL_179:
        v127 = (unsigned __int16 **)(a6 + 176);
        if ( a6 == -176 )
        {
          v128 = -2147024809;
          Logger::TraceError(L"%s: \"%s\" should not be null.", L"CopyStringNullSafeW", L"ppszOut");
          Logger::WriteNullOrEmptyParameterFailureEvent(L"CopyStringNullSafeW", L"ppszOut");
        }
        else
        {
          v129 = (const unsigned __int16 *)*((_QWORD *)v9 + 18);
          *v127 = 0;
          if ( !v129 )
            goto LABEL_188;
          v130 = CopyStringSafeW(v129, v127);
          v128 = v130;
          if ( v130 >= 0 )
            goto LABEL_188;
          Logger::TraceError(
            L"%s: %s failed with error code: 0x%08x.",
            L"CopyStringNullSafeW",
            L"CopyStringSafeW",
            (unsigned int)v130);
        }
        v131 = L"TRUE";
        if ( !a4 )
          v131 = L"FALSE";
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
          L"DeviceRegistrationStateApi::PopulateJoinInfo",
          L"CopyStringNullSafeW",
          v128,
          v131);
        if ( !a4 )
        {
          LODWORD(ExtensionGuidValueByOid) = v128;
          goto LABEL_390;
        }
LABEL_188:
        v132 = (unsigned __int16 **)(a6 + 184);
        if ( a6 == -184 )
        {
          v133 = -2147024809;
          Logger::TraceError(L"%s: \"%s\" should not be null.", L"CopyStringNullSafeW", L"ppszOut");
          Logger::WriteNullOrEmptyParameterFailureEvent(L"CopyStringNullSafeW", L"ppszOut");
        }
        else
        {
          v134 = (const unsigned __int16 *)*((_QWORD *)v9 + 19);
          *v132 = 0;
          if ( !v134 )
            goto LABEL_197;
          v135 = CopyStringSafeW(v134, v132);
          v133 = v135;
          if ( v135 >= 0 )
            goto LABEL_197;
          Logger::TraceError(
            L"%s: %s failed with error code: 0x%08x.",
            L"CopyStringNullSafeW",
            L"CopyStringSafeW",
            (unsigned int)v135);
        }
        v136 = L"TRUE";
        if ( !a4 )
          v136 = L"FALSE";
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
          L"DeviceRegistrationStateApi::PopulateJoinInfo",
          L"CopyStringNullSafeW",
          v133,
          v136);
        if ( !a4 )
        {
          LODWORD(ExtensionGuidValueByOid) = v133;
          goto LABEL_390;
        }
LABEL_197:
        v137 = (unsigned __int16 **)(a6 + 192);
        if ( a6 == -192 )
        {
          v138 = -2147024809;
          Logger::TraceError(L"%s: \"%s\" should not be null.", L"CopyStringNullSafeW", L"ppszOut");
          Logger::WriteNullOrEmptyParameterFailureEvent(L"CopyStringNullSafeW", L"ppszOut");
        }
        else
        {
          v139 = (const unsigned __int16 *)*((_QWORD *)v9 + 20);
          *v137 = 0;
          if ( !v139 )
            goto LABEL_206;
          v140 = CopyStringSafeW(v139, v137);
          v138 = v140;
          if ( v140 >= 0 )
            goto LABEL_206;
          Logger::TraceError(
            L"%s: %s failed with error code: 0x%08x.",
            L"CopyStringNullSafeW",
            L"CopyStringSafeW",
            (unsigned int)v140);
        }
        v141 = L"TRUE";
        if ( !a4 )
          v141 = L"FALSE";
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
          L"DeviceRegistrationStateApi::PopulateJoinInfo",
          L"CopyStringNullSafeW",
          v138,
          v141);
        if ( !a4 )
        {
          LODWORD(ExtensionGuidValueByOid) = v138;
          goto LABEL_390;
        }
LABEL_206:
        v142 = (unsigned __int16 **)(a6 + 200);
        if ( a6 == -200 )
        {
          v143 = -2147024809;
          Logger::TraceError(L"%s: \"%s\" should not be null.", L"CopyStringNullSafeW", L"ppszOut");
          Logger::WriteNullOrEmptyParameterFailureEvent(L"CopyStringNullSafeW", L"ppszOut");
        }
        else
        {
          v144 = (const unsigned __int16 *)*((_QWORD *)v9 + 21);
          *v142 = 0;
          if ( !v144 )
            goto LABEL_215;
          v145 = CopyStringSafeW(v144, v142);
          v143 = v145;
          if ( v145 >= 0 )
            goto LABEL_215;
          Logger::TraceError(
            L"%s: %s failed with error code: 0x%08x.",
            L"CopyStringNullSafeW",
            L"CopyStringSafeW",
            (unsigned int)v145);
        }
        v146 = L"TRUE";
        if ( !a4 )
          v146 = L"FALSE";
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
          L"DeviceRegistrationStateApi::PopulateJoinInfo",
          L"CopyStringNullSafeW",
          v143,
          v146);
        if ( !a4 )
        {
          LODWORD(ExtensionGuidValueByOid) = v143;
          goto LABEL_390;
        }
LABEL_215:
        v147 = (unsigned __int16 **)(a6 + 208);
        if ( a6 == -208 )
        {
          v148 = -2147024809;
          Logger::TraceError(L"%s: \"%s\" should not be null.", L"CopyStringNullSafeW", L"ppszOut");
          Logger::WriteNullOrEmptyParameterFailureEvent(L"CopyStringNullSafeW", L"ppszOut");
        }
        else
        {
          v149 = (const unsigned __int16 *)*((_QWORD *)v9 + 22);
          *v147 = 0;
          if ( !v149 )
            goto LABEL_224;
          v150 = CopyStringSafeW(v149, v147);
          v148 = v150;
          if ( v150 >= 0 )
            goto LABEL_224;
          Logger::TraceError(
            L"%s: %s failed with error code: 0x%08x.",
            L"CopyStringNullSafeW",
            L"CopyStringSafeW",
            (unsigned int)v150);
        }
        v151 = L"TRUE";
        if ( !a4 )
          v151 = L"FALSE";
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
          L"DeviceRegistrationStateApi::PopulateJoinInfo",
          L"CopyStringNullSafeW",
          v148,
          v151);
        if ( !a4 )
        {
          LODWORD(ExtensionGuidValueByOid) = v148;
          goto LABEL_390;
        }
LABEL_224:
        v152 = (unsigned __int16 **)(a6 + 216);
        if ( a6 == -216 )
        {
          v153 = -2147024809;
          Logger::TraceError(L"%s: \"%s\" should not be null.", L"CopyStringNullSafeW", L"ppszOut");
          Logger::WriteNullOrEmptyParameterFailureEvent(L"CopyStringNullSafeW", L"ppszOut");
        }
        else
        {
          v154 = (const unsigned __int16 *)*((_QWORD *)v9 + 23);
          *v152 = 0;
          if ( !v154 )
            goto LABEL_233;
          v155 = CopyStringSafeW(v154, v152);
          v153 = v155;
          if ( v155 >= 0 )
            goto LABEL_233;
          Logger::TraceError(
            L"%s: %s failed with error code: 0x%08x.",
            L"CopyStringNullSafeW",
            L"CopyStringSafeW",
            (unsigned int)v155);
        }
        v156 = L"TRUE";
        if ( !a4 )
          v156 = L"FALSE";
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
          L"DeviceRegistrationStateApi::PopulateJoinInfo",
          L"CopyStringNullSafeW",
          v153,
          v156);
        if ( !a4 )
        {
          LODWORD(ExtensionGuidValueByOid) = v153;
          goto LABEL_390;
        }
LABEL_233:
        v157 = (unsigned __int16 **)(a6 + 224);
        if ( a6 == -224 )
        {
          v158 = -2147024809;
          Logger::TraceError(L"%s: \"%s\" should not be null.", L"CopyStringNullSafeW", L"ppszOut");
          Logger::WriteNullOrEmptyParameterFailureEvent(L"CopyStringNullSafeW", L"ppszOut");
        }
        else
        {
          v159 = (const unsigned __int16 *)*((_QWORD *)v9 + 24);
          *v157 = 0;
          if ( !v159 )
            goto LABEL_242;
          v160 = CopyStringSafeW(v159, v157);
          v158 = v160;
          if ( v160 >= 0 )
            goto LABEL_242;
          Logger::TraceError(
            L"%s: %s failed with error code: 0x%08x.",
            L"CopyStringNullSafeW",
            L"CopyStringSafeW",
            (unsigned int)v160);
        }
        v161 = L"TRUE";
        if ( !a4 )
          v161 = L"FALSE";
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
          L"DeviceRegistrationStateApi::PopulateJoinInfo",
          L"CopyStringNullSafeW",
          v158,
          v161);
        if ( !a4 )
        {
          LODWORD(ExtensionGuidValueByOid) = v158;
          goto LABEL_390;
        }
LABEL_242:
        v162 = (unsigned __int16 **)(a6 + 232);
        if ( a6 == -232 )
        {
          v163 = -2147024809;
          Logger::TraceError(L"%s: \"%s\" should not be null.", L"CopyStringNullSafeW", L"ppszOut");
          Logger::WriteNullOrEmptyParameterFailureEvent(L"CopyStringNullSafeW", L"ppszOut");
        }
        else
        {
          v164 = (const unsigned __int16 *)*((_QWORD *)v9 + 25);
          *v162 = 0;
          if ( !v164 )
            goto LABEL_251;
          v165 = CopyStringSafeW(v164, v162);
          v163 = v165;
          if ( v165 >= 0 )
            goto LABEL_251;
          Logger::TraceError(
            L"%s: %s failed with error code: 0x%08x.",
            L"CopyStringNullSafeW",
            L"CopyStringSafeW",
            (unsigned int)v165);
        }
        v166 = L"TRUE";
        if ( !a4 )
          v166 = L"FALSE";
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
          L"DeviceRegistrationStateApi::PopulateJoinInfo",
          L"CopyStringNullSafeW",
          v163,
          v166);
        if ( !a4 )
        {
          LODWORD(ExtensionGuidValueByOid) = v163;
          goto LABEL_390;
        }
LABEL_251:
        v167 = (unsigned __int16 **)(a6 + 240);
        if ( a6 == -240 )
        {
          v168 = -2147024809;
          Logger::TraceError(L"%s: \"%s\" should not be null.", L"CopyStringNullSafeW", L"ppszOut");
          Logger::WriteNullOrEmptyParameterFailureEvent(L"CopyStringNullSafeW", L"ppszOut");
        }
        else
        {
          v169 = (const unsigned __int16 *)*((_QWORD *)v9 + 28);
          *v167 = 0;
          if ( !v169 )
            goto LABEL_260;
          v170 = CopyStringSafeW(v169, v167);
          v168 = v170;
          if ( v170 >= 0 )
            goto LABEL_260;
          Logger::TraceError(
            L"%s: %s failed with error code: 0x%08x.",
            L"CopyStringNullSafeW",
            L"CopyStringSafeW",
            (unsigned int)v170);
        }
        v171 = L"TRUE";
        if ( !a4 )
          v171 = L"FALSE";
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
          L"DeviceRegistrationStateApi::PopulateJoinInfo",
          L"CopyStringNullSafeW",
          v168,
          v171);
        if ( !a4 )
        {
          LODWORD(ExtensionGuidValueByOid) = v168;
          goto LABEL_390;
        }
LABEL_260:
        *(_DWORD *)(a6 + 248) = 0;
        v172 = (_WORD *)*((_QWORD *)v9 + 29);
        v173 = v172 && *v172;
        v174 = (unsigned __int16 **)(a6 + 256);
        *(_DWORD *)(a6 + 248) = v173;
        if ( a6 == -256 )
        {
          v175 = -2147024809;
          Logger::TraceError(L"%s: \"%s\" should not be null.", L"CopyStringNullSafeW", L"ppszOut");
          Logger::WriteNullOrEmptyParameterFailureEvent(L"CopyStringNullSafeW", L"ppszOut");
        }
        else
        {
          v176 = (const unsigned __int16 *)*((_QWORD *)v9 + 30);
          *v174 = 0;
          if ( !v176 )
            goto LABEL_273;
          v177 = CopyStringSafeW(v176, v174);
          v175 = v177;
          if ( v177 >= 0 )
            goto LABEL_273;
          Logger::TraceError(
            L"%s: %s failed with error code: 0x%08x.",
            L"CopyStringNullSafeW",
            L"CopyStringSafeW",
            (unsigned int)v177);
        }
        v178 = L"TRUE";
        if ( !a4 )
          v178 = L"FALSE";
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
          L"DeviceRegistrationStateApi::PopulateJoinInfo",
          L"CopyStringNullSafeW",
          v175,
          v178);
        if ( !a4 )
        {
          LODWORD(ExtensionGuidValueByOid) = v175;
          goto LABEL_390;
        }
LABEL_273:
        v179 = (unsigned __int16 **)(a6 + 264);
        if ( a6 == -264 )
        {
          v180 = -2147024809;
          Logger::TraceError(L"%s: \"%s\" should not be null.", L"CopyStringNullSafeW", L"ppszOut");
          Logger::WriteNullOrEmptyParameterFailureEvent(L"CopyStringNullSafeW", L"ppszOut");
        }
        else
        {
          v181 = (const unsigned __int16 *)*((_QWORD *)v9 + 31);
          *v179 = 0;
          if ( !v181 )
            goto LABEL_282;
          v182 = CopyStringSafeW(v181, v179);
          v180 = v182;
          if ( v182 >= 0 )
            goto LABEL_282;
          Logger::TraceError(
            L"%s: %s failed with error code: 0x%08x.",
            L"CopyStringNullSafeW",
            L"CopyStringSafeW",
            (unsigned int)v182);
        }
        v183 = L"TRUE";
        if ( !a4 )
          v183 = L"FALSE";
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
          L"DeviceRegistrationStateApi::PopulateJoinInfo",
          L"CopyStringNullSafeW",
          v180,
          v183);
        if ( !a4 )
        {
          LODWORD(ExtensionGuidValueByOid) = v180;
          goto LABEL_390;
        }
LABEL_282:
        v184 = (unsigned __int16 **)(a6 + 288);
        if ( a6 == -288 )
        {
          v185 = -2147024809;
          Logger::TraceError(L"%s: \"%s\" should not be null.", L"CopyStringNullSafeW", L"ppszOut");
          Logger::WriteNullOrEmptyParameterFailureEvent(L"CopyStringNullSafeW", L"ppszOut");
        }
        else
        {
          v186 = (const unsigned __int16 *)*((_QWORD *)v9 + 34);
          *v184 = 0;
          if ( !v186 )
            goto LABEL_291;
          v187 = CopyStringSafeW(v186, v184);
          v185 = v187;
          if ( v187 >= 0 )
            goto LABEL_291;
          Logger::TraceError(
            L"%s: %s failed with error code: 0x%08x.",
            L"CopyStringNullSafeW",
            L"CopyStringSafeW",
            (unsigned int)v187);
        }
        v188 = L"TRUE";
        if ( !a4 )
          v188 = L"FALSE";
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
          L"DeviceRegistrationStateApi::PopulateJoinInfo",
          L"CopyStringNullSafeW",
          v185,
          v188);
        if ( !a4 )
        {
          LODWORD(ExtensionGuidValueByOid) = v185;
          goto LABEL_390;
        }
LABEL_291:
        v189 = (unsigned __int16 **)(a6 + 296);
        *(_DWORD *)(a6 + 272) = *((_DWORD *)v9 + 64) != 0;
        *(_QWORD *)(a6 + 280) = *((_QWORD *)v9 + 33);
        if ( a6 == -296 )
        {
          v190 = -2147024809;
          Logger::TraceError(L"%s: \"%s\" should not be null.", L"CopyStringNullSafeW", L"ppszOut");
          Logger::WriteNullOrEmptyParameterFailureEvent(L"CopyStringNullSafeW", L"ppszOut");
        }
        else
        {
          v191 = (const unsigned __int16 *)*((_QWORD *)v9 + 35);
          *v189 = 0;
          if ( !v191 )
            goto LABEL_300;
          v192 = CopyStringSafeW(v191, v189);
          v190 = v192;
          if ( v192 >= 0 )
            goto LABEL_300;
          Logger::TraceError(
            L"%s: %s failed with error code: 0x%08x.",
            L"CopyStringNullSafeW",
            L"CopyStringSafeW",
            (unsigned int)v192);
        }
        v193 = L"TRUE";
        if ( !a4 )
          v193 = L"FALSE";
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
          L"DeviceRegistrationStateApi::PopulateJoinInfo",
          L"CopyStringNullSafeW",
          v190,
          v193);
        if ( !a4 )
        {
          LODWORD(ExtensionGuidValueByOid) = v190;
          goto LABEL_390;
        }
LABEL_300:
        v194 = (unsigned __int16 **)(a6 + 304);
        if ( a6 == -304 )
        {
          v195 = -2147024809;
          Logger::TraceError(L"%s: \"%s\" should not be null.", L"CopyStringNullSafeW", L"ppszOut");
          Logger::WriteNullOrEmptyParameterFailureEvent(L"CopyStringNullSafeW", L"ppszOut");
        }
        else
        {
          v196 = (const unsigned __int16 *)*((_QWORD *)v9 + 36);
          *v194 = 0;
          if ( !v196 )
            goto LABEL_309;
          v197 = CopyStringSafeW(v196, v194);
          v195 = v197;
          if ( v197 >= 0 )
            goto LABEL_309;
          Logger::TraceError(
            L"%s: %s failed with error code: 0x%08x.",
            L"CopyStringNullSafeW",
            L"CopyStringSafeW",
            (unsigned int)v197);
        }
        v198 = L"TRUE";
        if ( !a4 )
          v198 = L"FALSE";
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
          L"DeviceRegistrationStateApi::PopulateJoinInfo",
          L"CopyStringNullSafeW",
          v195,
          v198);
        if ( !a4 )
        {
          LODWORD(ExtensionGuidValueByOid) = v195;
          goto LABEL_390;
        }
LABEL_309:
        v199 = (unsigned __int16 **)(a6 + 312);
        if ( a6 == -312 )
        {
          v200 = -2147024809;
          Logger::TraceError(L"%s: \"%s\" should not be null.", L"CopyStringNullSafeW", L"ppszOut");
          Logger::WriteNullOrEmptyParameterFailureEvent(L"CopyStringNullSafeW", L"ppszOut");
        }
        else
        {
          v201 = (const unsigned __int16 *)*((_QWORD *)v9 + 37);
          *v199 = 0;
          if ( !v201 )
            goto LABEL_318;
          v202 = CopyStringSafeW(v201, v199);
          v200 = v202;
          if ( v202 >= 0 )
            goto LABEL_318;
          Logger::TraceError(
            L"%s: %s failed with error code: 0x%08x.",
            L"CopyStringNullSafeW",
            L"CopyStringSafeW",
            (unsigned int)v202);
        }
        v203 = L"TRUE";
        if ( !a4 )
          v203 = L"FALSE";
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
          L"DeviceRegistrationStateApi::PopulateJoinInfo",
          L"CopyStringNullSafeW",
          v200,
          v203);
        if ( !a4 )
        {
          LODWORD(ExtensionGuidValueByOid) = v200;
          goto LABEL_390;
        }
LABEL_318:
        v204 = (unsigned __int16 **)(a6 + 320);
        if ( a6 == -320 )
        {
          v205 = -2147024809;
          Logger::TraceError(L"%s: \"%s\" should not be null.", L"CopyStringNullSafeW", L"ppszOut");
          Logger::WriteNullOrEmptyParameterFailureEvent(L"CopyStringNullSafeW", L"ppszOut");
        }
        else
        {
          v206 = (const unsigned __int16 *)*((_QWORD *)v9 + 38);
          v205 = 0;
          *v204 = 0;
          if ( !v206 || (v207 = CopyStringSafeW(v206, v204), v205 = v207, v207 >= 0) )
          {
            LODWORD(ExtensionGuidValueByOid) = v205;
            v209 = a4;
            goto LABEL_328;
          }
          Logger::TraceError(
            L"%s: %s failed with error code: 0x%08x.",
            L"CopyStringNullSafeW",
            L"CopyStringSafeW",
            (unsigned int)v207);
          LODWORD(ExtensionGuidValueByOid) = v205;
        }
        v208 = L"TRUE";
        if ( !a4 )
          v208 = L"FALSE";
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
          L"DeviceRegistrationStateApi::PopulateJoinInfo",
          L"CopyStringNullSafeW",
          v205,
          v208);
        v209 = a4;
        if ( !a4 )
          goto LABEL_390;
LABEL_328:
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_RAforMTRW>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_RAforMTRW>::GetImpl'::`2'::impl) )
        {
          LODWORD(ExtensionGuidValueByOid) = CopyStringNullSafeW(
                                               *((const unsigned __int16 **)v9 + 39),
                                               (unsigned __int16 **)(a6 + 328));
          if ( (int)ExtensionGuidValueByOid < 0 )
          {
            v210 = L"TRUE";
            if ( !v209 )
              v210 = L"FALSE";
            Logger::TraceError(
              L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
              L"DeviceRegistrationStateApi::PopulateJoinInfo",
              L"CopyStringNullSafeW",
              (unsigned int)ExtensionGuidValueByOid,
              v210);
            if ( !v209 )
              goto LABEL_390;
          }
        }
        Uuid = v239[0];
        v211 = 0;
        Status = 0;
        if ( UuidIsNil(&Uuid, &Status) )
          goto LABEL_344;
        v213 = &sourceString;
        v214 = *(const unsigned __int16 **)(a6 + 32);
        Status = 0;
        v215 = &sourceString;
        if ( *(_QWORD *)&v239[3].Data1 )
          v215 = *(const unsigned __int16 **)&v239[3].Data1;
        LODWORD(ExtensionGuidValueByOid) = StringCompare(v214, v215, v212, &Status);
        if ( (int)ExtensionGuidValueByOid < 0 )
        {
          v217 = L"TRUE";
          if ( !a4 )
            v217 = L"FALSE";
          Logger::TraceError(
            L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
            L"DeviceRegistrationStateApi::PopulateJoinInfo",
            L"StringCompare",
            (unsigned int)ExtensionGuidValueByOid,
            v217);
          if ( !a4 )
            goto LABEL_390;
        }
        if ( !Status )
        {
          v218 = L"<NULL>";
          v219 = *(unsigned __int16 **)(a6 + 32);
          v220 = L"%s: The NGC key is not for the given tenant %s. Key tenant: %s. Return no key.";
          if ( *(_QWORD *)&v239[3].Data1 )
            v218 = *(const wchar_t **)&v239[3].Data1;
LABEL_343:
          Logger::TraceVerbose(v220, L"DeviceRegistrationStateApi::PopulateJoinInfo", v219, v218);
          goto LABEL_344;
        }
        ExtensionGuidValueByOid = v236;
        if ( v236 && *v236 )
          goto LABEL_354;
        if ( v234 == 5 )
        {
          ExtensionGuidValueByOid = *(unsigned __int16 **)(a6 + 40);
          v236 = ExtensionGuidValueByOid;
          if ( !ExtensionGuidValueByOid || !*ExtensionGuidValueByOid )
            goto LABEL_364;
          Logger::TraceVerbose(
            L"%s: No explicit UPN given. Using the work account's UPN for matching. UPN: %s.",
            L"DeviceRegistrationStateApi::PopulateJoinInfo",
            ExtensionGuidValueByOid);
        }
        else if ( !v236 )
        {
          goto LABEL_364;
        }
        if ( *ExtensionGuidValueByOid )
        {
LABEL_354:
          if ( *(_QWORD *)v239[3].Data4 )
            v213 = *(const unsigned __int16 **)v239[3].Data4;
          LODWORD(ExtensionGuidValueByOid) = StringCompare(ExtensionGuidValueByOid, v213, v216, &Status);
          if ( (int)ExtensionGuidValueByOid < 0 )
          {
            v221 = L"TRUE";
            if ( !a4 )
              v221 = L"FALSE";
            Logger::TraceError(
              L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
              L"DeviceRegistrationStateApi::PopulateJoinInfo",
              L"StringCompare",
              (unsigned int)ExtensionGuidValueByOid,
              v221);
            if ( !a4 )
              goto LABEL_390;
          }
          if ( !Status )
          {
            v218 = L"<NULL>";
            v219 = v236;
            v220 = L"%s: The NGC key is not for the given UPN %s. Key UPN: %s. Return no key.";
            if ( *(_QWORD *)v239[3].Data4 )
              v218 = *(const wchar_t **)v239[3].Data4;
            goto LABEL_343;
          }
        }
LABEL_364:
        v222 = operator new[](0x18u, (const struct std::nothrow_t *)&std::nothrow);
        *(_QWORD *)(a6 + 48) = v222;
        if ( !v222 )
        {
          LODWORD(ExtensionGuidValueByOid) = -2147024882;
          Logger::TraceCritical(
            L"%s: Out of memory. Allocation failed.",
            L"DeviceRegistrationStateApi::PopulateJoinInfo");
          goto LABEL_366;
        }
        *(_OWORD *)v222 = 0;
        v222[2] = 0;
        v223 = *(unsigned __int16 ***)(a6 + 48);
        v224 = *(const unsigned __int16 **)v239[3].Data4;
        *(_DWORD *)(a6 + 56) = 1;
        LODWORD(ExtensionGuidValueByOid) = CopyStringNullSafeW(v224, v223);
        if ( (int)ExtensionGuidValueByOid < 0 )
        {
          v225 = L"TRUE";
          if ( !a4 )
            v225 = L"FALSE";
          Logger::TraceError(
            L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
            L"DeviceRegistrationStateApi::PopulateJoinInfo",
            L"CopyStringNullSafeW",
            (unsigned int)ExtensionGuidValueByOid,
            v225);
          if ( !a4 )
            goto LABEL_390;
        }
        LODWORD(ExtensionGuidValueByOid) = CopyStringNullSafeW(
                                             *(const unsigned __int16 **)&v239[1].Data1,
                                             (unsigned __int16 **)(*(_QWORD *)(a6 + 48) + 16LL));
        if ( (int)ExtensionGuidValueByOid < 0 )
        {
          v226 = L"TRUE";
          if ( !a4 )
            v226 = L"FALSE";
          Logger::TraceError(
            L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
            L"DeviceRegistrationStateApi::PopulateJoinInfo",
            L"CopyStringNullSafeW",
            (unsigned int)ExtensionGuidValueByOid,
            v226);
          if ( !a4 )
            goto LABEL_390;
        }
        v227 = UuidToStringW(v239, &StringUuid);
        v211 = v227;
        if ( v227 )
        {
          Logger::TraceError(
            L"%s: UuidToStringW failed with RPC_STATUS error code: 0x%08x",
            L"DeviceRegistrationStateApi::PopulateJoinInfo",
            v227);
          if ( !a4 )
          {
LABEL_382:
            if ( v211 > 0 )
              LODWORD(ExtensionGuidValueByOid) = (unsigned __int16)v211 | 0x80070000;
            else
              LODWORD(ExtensionGuidValueByOid) = v211;
            goto LABEL_366;
          }
        }
        LODWORD(ExtensionGuidValueByOid) = CopyStringNullSafeW(
                                             StringUuid,
                                             (unsigned __int16 **)(*(_QWORD *)(a6 + 48) + 8LL));
        if ( (int)ExtensionGuidValueByOid < 0 )
        {
          v228 = L"TRUE";
          if ( !a4 )
            v228 = L"FALSE";
          Logger::TraceError(
            L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
            L"DeviceRegistrationStateApi::PopulateJoinInfo",
            L"CopyStringNullSafeW",
            (unsigned int)ExtensionGuidValueByOid,
            v228);
          if ( a4 )
            goto LABEL_345;
LABEL_381:
          if ( !v211 )
            goto LABEL_390;
          goto LABEL_382;
        }
LABEL_344:
        if ( a4 )
        {
LABEL_345:
          LODWORD(ExtensionGuidValueByOid) = 0;
LABEL_366:
          operator delete(0);
          operator delete(Block);
LABEL_391:
          struct_join_status::~struct_join_status(v9);
          operator delete(v9);
          goto LABEL_392;
        }
        goto LABEL_381;
      }
      v10 = 0;
    }
    else
    {
      v9 = 0;
    }
    LODWORD(ExtensionGuidValueByOid) = -2147024882;
    Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"DeviceRegistrationStateApi::PopulateJoinInfo");
    goto LABEL_388;
  }
  LODWORD(ExtensionGuidValueByOid) = -2147024809;
  Logger::TraceError(L"%s: \"%s\" should not be null.", L"DeviceRegistrationStateApi::PopulateJoinInfo", L"pJoinInfo");
  if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) == 0 )
  {
LABEL_5:
    operator delete(0);
    v14 = Block;
    goto LABEL_394;
  }
  *(_QWORD *)&v242[12] = L"DeviceRegistrationStateApi::PopulateJoinInfo";
  *(_QWORD *)&v242[20] = 90;
  *(_QWORD *)&v242[28] = L"pJoinInfo";
  *(_QWORD *)&v242[36] = 20;
  v13 = McGenEventWrite_EventWriteTransfer(
          &UserDeviceRegistrationEventProvider_Context,
          NullOrEmptyParameterFailureEvent,
          v12,
          3,
          v241);
  if ( v13 )
  {
    Logger::TraceError(
      L"%s: %s failed with win32 error code: 0x%08x.",
      L"Logger::WriteNullOrEmptyParameterFailureEvent",
      L"EventWriteNullOrEmptyParameterFailureEvent",
      v13);
    goto LABEL_5;
  }
LABEL_390:
  operator delete(v8);
  operator delete(Block);
  if ( v9 )
    goto LABEL_391;
LABEL_392:
  if ( !v10 )
    goto LABEL_395;
  NgcStatusStorage::Cleanup(v10);
  v14 = v10;
LABEL_394:
  operator delete(v14);
LABEL_395:
  if ( StringUuid )
  {
    RpcStringFreeW(&StringUuid);
    StringUuid = 0;
  }
  if ( (int)ExtensionGuidValueByOid < 0 )
    DsrFreeAccountInfoContent(a6);
  Logger::TraceVerbose(
    L"%s - hr: 0x%08x",
    L"DeviceRegistrationStateApi::PopulateJoinInfo",
    (unsigned int)ExtensionGuidValueByOid);
  return (unsigned int)ExtensionGuidValueByOid;
}

```

## disassembly

```asm
0x18001c2a0  push    rbp
0x18001c2a2  push    rbx
0x18001c2a3  push    rsi
0x18001c2a4  push    rdi
0x18001c2a5  push    r12
0x18001c2a7  push    r13
0x18001c2a9  push    r14
0x18001c2ab  push    r15
0x18001c2ad  lea     rbp, [rsp-198h]
0x18001c2b5  sub     rsp, 298h
0x18001c2bc  mov     rax, cs:__security_cookie
0x18001c2c3  xor     rax, rsp
0x18001c2c6  mov     [rbp+1D0h+var_50], rax
0x18001c2cd  mov     rdi, [rbp+1D0h+arg_28]
0x18001c2d4  xorps   xmm0, xmm0
0x18001c2d7  mov     r14d, ecx
0x18001c2da  mov     [rsp+2D0h+var_288], ecx
0x18001c2de  xor     ecx, ecx
0x18001c2e0  mov     [rsp+2D0h+var_2A0], r9d
0x18001c2e5  mov     [rsp+2D0h+var_278], r8
0x18001c2ea  mov     r15, rdx
0x18001c2ed  mov     qword ptr [rbp+1D0h+Uuid.Data1], rcx
0x18001c2f4  mov     r12d, ecx
0x18001c2f7  mov     [rsp+2D0h+Block], rcx
0x18001c2fc  mov     ebx, ecx
0x18001c2fe  mov     [rsp+2D0h+var_290], rcx
0x18001c303  mov     r13d, ecx
0x18001c306  mov     [rsp+2D0h+StringUuid], rcx
0x18001c30b  mov     [rbp+1D0h+var_E0.Data1], ecx
0x18001c311  mov     [rsp+2D0h+Status], ecx
0x18001c315  movups  xmmword ptr [rbp+1D0h+var_BC], xmm0
0x18001c31c  movups  xmmword ptr [rbp+1D0h+var_E0.Data2], xmm0
0x18001c323  movups  [rbp+1D0h+var_CC], xmm0
0x18001c32a  movups  xmmword ptr [rbp+1D0h+var_BC+0Ch], xmm0
0x18001c331  test    rdi, rdi
0x18001c334  jnz     loc_18001C3E8
0x18001c33a  lea     r14, aPjoininfo; "pJoinInfo"
0x18001c341  mov     esi, 80070057h
0x18001c346  lea     r15, aDeviceregistra_0; "DeviceRegistrationStateApi::PopulateJoi"...
0x18001c34d  mov     r8, r14
0x18001c350  mov     rdx, r15
0x18001c353  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18001c35a  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001c35f  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x18001c366  jz      short loc_18001C3D6
0x18001c368  lea     rax, [rbp+1D0h+var_90]
0x18001c36f  mov     qword ptr [rbp+1D0h+var_80], r15
0x18001c376  mov     r9d, 3
0x18001c37c  mov     qword ptr [rsp+2D0h+var_2B0], rax
0x18001c381  lea     rdx, NullOrEmptyParameterFailureEvent
0x18001c388  mov     qword ptr [rbp+1D0h+var_80+8], 5Ah ; 'Z'
0x18001c393  lea     rcx, UserDeviceRegistrationEventProvider_Context
0x18001c39a  mov     qword ptr [rbp+1D0h+var_70], r14
0x18001c3a1  mov     qword ptr [rbp+1D0h+var_70+8], 14h
0x18001c3ac  call    McGenEventWrite_EventWriteTransfer
0x18001c3b1  test    eax, eax
0x18001c3b3  jz      loc_18001E3F0
0x18001c3b9  mov     r9d, eax
0x18001c3bc  lea     r8, aEventwritenull; "EventWriteNullOrEmptyParameterFailureEv"...
0x18001c3c3  lea     rdx, aLoggerWritenul; "Logger::WriteNullOrEmptyParameterFailur"...
0x18001c3ca  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x18001c3d1  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001c3d6  mov     rcx, r12; Block
0x18001c3d9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001c3de  mov     rcx, [rsp+2D0h+Block]
0x18001c3e3  jmp     loc_18001E427
0x18001c3e8  xor     edx, edx; Val
0x18001c3ea  lea     rcx, [rbp+1D0h+var_230]; void *
0x18001c3ee  mov     r8d, 150h; Size
0x18001c3f4  call    memset_0
0x18001c3f9  mov     rax, rdi
0x18001c3fc  lea     rcx, [rbp+1D0h+var_230]
0x18001c400  mov     edx, 2
0x18001c405  lea     rax, [rax+80h]
0x18001c40c  movups  xmm0, xmmword ptr [rcx]
0x18001c40f  movups  xmm1, xmmword ptr [rcx+10h]
0x18001c413  lea     rcx, [rcx+80h]
0x18001c41a  movups  xmmword ptr [rax-80h], xmm0
0x18001c41e  movups  xmm0, xmmword ptr [rcx-60h]
0x18001c422  movups  xmmword ptr [rax-70h], xmm1
0x18001c426  movups  xmm1, xmmword ptr [rcx-50h]
0x18001c42a  movups  xmmword ptr [rax-60h], xmm0
0x18001c42e  movups  xmm0, xmmword ptr [rcx-40h]
0x18001c432  movups  xmmword ptr [rax-50h], xmm1
0x18001c436  movups  xmm1, xmmword ptr [rcx-30h]
0x18001c43a  movups  xmmword ptr [rax-40h], xmm0
0x18001c43e  movups  xmm0, xmmword ptr [rcx-20h]
0x18001c442  movups  xmmword ptr [rax-30h], xmm1
0x18001c446  movups  xmm1, xmmword ptr [rcx-10h]
0x18001c44a  movups  xmmword ptr [rax-20h], xmm0
0x18001c44e  movups  xmmword ptr [rax-10h], xmm1
0x18001c452  sub     rdx, 1
0x18001c456  jnz     short loc_18001C405
0x18001c458  movups  xmm0, xmmword ptr [rcx]
0x18001c45b  movups  xmm1, xmmword ptr [rcx+10h]
0x18001c45f  movups  xmmword ptr [rax], xmm0
0x18001c462  movups  xmm0, xmmword ptr [rcx+20h]
0x18001c466  movups  xmmword ptr [rax+10h], xmm1
0x18001c46a  movups  xmm1, xmmword ptr [rcx+30h]
0x18001c46e  movups  xmmword ptr [rax+20h], xmm0
0x18001c472  movups  xmm0, xmmword ptr [rcx+40h]
0x18001c476  movups  xmmword ptr [rax+30h], xmm1
0x18001c47a  movups  xmmword ptr [rax+40h], xmm0
0x18001c47e  test    r15, r15
0x18001c481  jnz     short loc_18001C4C6
0x18001c483  lea     r15, aDeviceregistra_0; "DeviceRegistrationStateApi::PopulateJoi"...
0x18001c48a  mov     esi, 80070057h
0x18001c48f  mov     rdx, r15
0x18001c492  lea     r8, stru_1800EA828
0x18001c499  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18001c4a0  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001c4a5  lea     rdx, stru_1800EA828; unsigned __int16 *
0x18001c4ac  mov     rcx, r15; unsigned __int16 *
0x18001c4af  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18001c4b4  mov     rcx, r12; Block
0x18001c4b7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001c4bc  mov     rcx, [rsp+2D0h+Block]
0x18001c4c1  jmp     loc_18001E427
0x18001c4c6  lea     eax, [r14-1]
0x18001c4ca  test    eax, 0FFFFFFFBh
0x18001c4cf  jz      short loc_18001C501
0x18001c4d1  mov     esi, 80070057h
0x18001c4d6  lea     rcx, aSInvalidJoinTy; "%s: Invalid join type %d. Only DEVICE a"...
0x18001c4dd  mov     r8d, r14d
0x18001c4e0  lea     r15, aDeviceregistra_0; "DeviceRegistrationStateApi::PopulateJoi"...
0x18001c4e7  mov     rdx, r15
0x18001c4ea  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001c4ef  mov     rcx, r12; Block
0x18001c4f2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001c4f7  mov     rcx, [rsp+2D0h+Block]
0x18001c4fc  jmp     loc_18001E427
0x18001c501  mov     rcx, r15; pCertContext
0x18001c504  call    cs:__imp_CertDuplicateCertificateContext
0x18001c50a  mov     r14, rax
0x18001c50d  test    rax, rax
0x18001c510  jnz     short loc_18001C539
0x18001c512  call    cs:__imp_GetLastError
0x18001c518  mov     esi, eax
0x18001c51a  test    eax, eax
0x18001c51c  jle     short loc_18001C527
0x18001c51e  movzx   esi, ax
0x18001c521  or      esi, 80070000h
0x18001c527  call    cs:__imp_GetLastError
0x18001c52d  mov     r8d, eax
0x18001c530  lea     rcx, aSCertduplicate; "%s: CertDuplicateCertificateContext fai"...
0x18001c537  jmp     short loc_18001C4E0
0x18001c539  lea     r8, [rsp+2D0h+Status]; int *
0x18001c53e  mov     rcx, r15; struct _CERT_CONTEXT *
0x18001c541  lea     rdx, [rbp+1D0h+Uuid]; unsigned __int16 **
0x18001c548  call    ?GetTenantId@RegistrationCertStatus@@SAJPEBU_CERT_CONTEXT@@PEAPEAGPEAH@Z; RegistrationCertStatus::GetTenantId(_CERT_CONTEXT const *,ushort * *,int *)
0x18001c54d  mov     esi, eax
0x18001c54f  test    eax, eax
0x18001c551  jns     short loc_18001C578
0x18001c553  lea     r15, aDeviceregistra_0; "DeviceRegistrationStateApi::PopulateJoi"...
0x18001c55a  mov     r9d, eax
0x18001c55d  mov     rdx, r15
0x18001c560  lea     r8, aRegistrationce_5; "RegistrationCertStatus::GetTenantId"
0x18001c567  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18001c56e  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001c573  jmp     loc_18001E3D7
0x18001c578  lea     r8, [rsp+2D0h+var_290]; unsigned __int16 **
0x18001c57d  mov     rdx, r15; struct _CERT_CONTEXT *
0x18001c580  lea     rcx, a12840113556152_0; "1.2.840.113556.1.5.284.2"
0x18001c587  call    ?FindExtensionGuidValueByOid@CertificateUtil@@SAJPEBDPEBU_CERT_CONTEXT@@PEAPEAG@Z; CertificateUtil::FindExtensionGuidValueByOid(char const *,_CERT_CONTEXT const *,ushort * *)
0x18001c58c  mov     esi, eax
0x18001c58e  mov     r8d, eax
0x18001c591  lea     rdx, aRegistrationce_6; "RegistrationCertStatus::GetDeviceId"
0x18001c598  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x18001c59f  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18001c5a4  test    esi, esi
0x18001c5a6  jns     short loc_18001C5CD
0x18001c5a8  lea     r15, aDeviceregistra_0; "DeviceRegistrationStateApi::PopulateJoi"...
0x18001c5af  mov     r9d, esi
0x18001c5b2  mov     rdx, r15
0x18001c5b5  lea     r8, aRegistrationce_6; "RegistrationCertStatus::GetDeviceId"
0x18001c5bc  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18001c5c3  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001c5c8  jmp     loc_18001E3CD
0x18001c5cd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001c5d4  mov     ecx, 140h; unsigned __int64
0x18001c5d9  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001c5de  mov     rbx, rax
0x18001c5e1  test    rax, rax
0x18001c5e4  jz      loc_18001E3B0
0x18001c5ea  mov     rcx, rax; this
0x18001c5ed  call    ?Clear@struct_join_status@@QEAAXXZ; struct_join_status::Clear(void)
0x18001c5f2  mov     eax, [rbp+1D0h+arg_20]
0x18001c5f8  xor     ecx, ecx
0x18001c5fa  mov     r12d, [rsp+2D0h+var_288]
0x18001c5ff  mov     r9, rbx; struct struct_join_status *
0x18001c602  mov     r8d, [rsp+2D0h+var_2A0]; int
0x18001c607  cmp     r12d, 1
0x18001c60b  mov     rdx, r15; struct _CERT_CONTEXT *
0x18001c60e  mov     [rsp+2D0h+var_2B0], eax; int
0x18001c612  setz    cl; int
0x18001c615  call    ?ReadJoinStatus@JoinStatusStorage@@SAJHPEBU_CERT_CONTEXT@@HPEAUstruct_join_status@@H@Z; JoinStatusStorage::ReadJoinStatus(int,_CERT_CONTEXT const *,int,struct_join_status *,int)
0x18001c61a  lea     r15, aDeviceregistra_0; "DeviceRegistrationStateApi::PopulateJoi"...
0x18001c621  mov     esi, eax
0x18001c623  lea     rcx, aFalse; "FALSE"
0x18001c62a  test    eax, eax
0x18001c62c  jns     short loc_18001C667
0x18001c62e  cmp     [rsp+2D0h+var_2A0], r13d
0x18001c633  lea     rax, aTrue; "TRUE"
0x18001c63a  mov     r9d, esi
0x18001c63d  lea     r8, aJoinstatusstor_1; "JoinStatusStorage::ReadJoinStatus"
0x18001c644  cmovz   rax, rcx
0x18001c648  mov     rdx, r15
0x18001c64b  lea     rcx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x. "...
0x18001c652  mov     qword ptr [rsp+2D0h+var_2B0], rax
0x18001c657  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001c65c  cmp     [rsp+2D0h+var_2A0], r13d
0x18001c661  jz      loc_18001E3CD
0x18001c667  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001c66e  mov     ecx, 10h; unsigned __int64
0x18001c673  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001c678  mov     r13, rax
0x18001c67b  test    rax, rax
0x18001c67e  jz      loc_18001E3AB
0x18001c684  xor     eax, eax
0x18001c686  mov     rcx, r13; this
0x18001c689  mov     [r13+0], rax
0x18001c68d  mov     [r13+8], rax
0x18001c691  call    ?Load@NgcStatusStorage@@QEAAJXZ; NgcStatusStorage::Load(void)
0x18001c696  mov     esi, eax
0x18001c698  test    eax, eax
0x18001c69a  jns     short loc_18001C6DC
0x18001c69c  cmp     [rsp+2D0h+var_2A0], 0
0x18001c6a1  lea     rcx, aFalse; "FALSE"
0x18001c6a8  lea     rax, aTrue; "TRUE"
0x18001c6af  mov     r9d, esi
0x18001c6b2  cmovz   rax, rcx
0x18001c6b6  lea     r8, aNgcstatusstora; "NgcStatusStorage::Load"
0x18001c6bd  lea     rcx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x. "...
0x18001c6c4  mov     qword ptr [rsp+2D0h+var_2B0], rax
0x18001c6c9  mov     rdx, r15
0x18001c6cc  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001c6d1  cmp     [rsp+2D0h+var_2A0], 0
0x18001c6d6  jz      loc_18001E3CD
0x18001c6dc  cmp     qword ptr [r13+8], 0
0x18001c6e1  jbe     short loc_18001C711
0x18001c6e3  mov     rcx, [r13+0]
0x18001c6e7  test    rcx, rcx
0x18001c6ea  jz      short loc_18001C711
0x18001c6ec  movups  xmm0, xmmword ptr [rcx+14h]
0x18001c6f0  mov     eax, [rcx]
0x18001c6f2  xor     r8d, r8d
0x18001c6f5  movups  xmm1, xmmword ptr [rcx+24h]
0x18001c6f9  movups  xmm2, xmmword ptr [rcx+4]
0x18001c6fd  movups  xmm3, xmmword ptr [rcx+30h]
0x18001c701  movups  [rbp+1D0h+var_80+4], xmm0
0x18001c708  movups  [rbp+1D0h+var_70+4], xmm1
0x18001c70f  jmp     short loc_18001C737
0x18001c711  xorps   xmm2, xmm2
0x18001c714  xorps   xmm3, xmm3
0x18001c717  movups  xmmword ptr [rbp+1D0h+var_24C], xmm2
0x18001c71b  xor     r8d, r8d
0x18001c71e  movaps  xmmword ptr [rbp+1D0h+var_24C+0Ch], xmm3
0x18001c722  mov     eax, r8d
0x18001c725  movups  xmm0, xmmword ptr [rbp+1D0h+var_24C]
0x18001c729  movups  [rbp+1D0h+var_80+4], xmm2
0x18001c730  movups  [rbp+1D0h+var_70+4], xmm0
0x18001c737  movups  xmm0, [rbp+1D0h+var_80+8]
0x18001c73e  lea     rdx, [rdi+18h]; unsigned __int16 **
0x18001c742  mov     [rbp+1D0h+var_E0.Data1], eax
0x18001c748  movsd   xmm1, qword ptr [rbp+1D0h+var_70+8]
0x18001c750  cmp     r12d, 1
0x18001c754  movups  xmmword ptr [rbp+144h], xmm2
0x18001c75b  mov     rax, qword ptr [rbp+1D0h+var_80]
0x18001c762  mov     r12, r8
0x18001c765  mov     [rbp+100h], rax
0x18001c76c  mov     esi, 80070057h
0x18001c771  mov     eax, r8d
0x18001c774  movsd   qword ptr [rbp+1D0h+var_E0.Data2], xmm2
0x18001c77c  setnz   al
0x18001c77f  movsd   [rbp+1D0h+var_BC+0Ch], xmm3
0x18001c787  inc     eax
0x18001c789  psrldq  xmm2, 8
0x18001c78e  cmp     [rsp+2D0h+Status], 0
0x18001c793  mov     [rdi], eax
0x18001c795  mov     rax, [rsp+2D0h+var_290]
0x18001c79a  mov     [rdi+10h], rax
0x18001c79e  mov     rax, qword ptr [rbp+1D0h+Uuid.Data1]
0x18001c7a5  mov     [rdi+20h], rax
0x18001c7a9  mov     eax, r8d
0x18001c7ac  setnz   al
0x18001c7af  psrldq  xmm3, 8
0x18001c7b4  mov     [rdi+3Ch], eax
0x18001c7b7  movd    dword ptr [rbp+1D0h+var_E0.Data4+4], xmm2
0x18001c7bf  movsd   [rbp+1D0h+var_BC+4], xmm1
0x18001c7c7  movq    [rbp+1D0h+var_A8], xmm3
0x18001c7cf  mov     [rdi+8], r14
0x18001c7d3  mov     [rsp+2D0h+Block], r8
0x18001c7d8  movups  [rbp+1D0h+var_CC+4], xmm0
0x18001c7df  test    rdx, rdx
0x18001c7e2  jnz     short loc_18001C816
0x18001c7e4  lea     r8, aPpszout; "ppszOut"
0x18001c7eb  mov     r14d, esi
0x18001c7ee  lea     rdx, aCopystringnull; "CopyStringNullSafeW"
0x18001c7f5  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18001c7fc  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
  ... truncated ...
```
