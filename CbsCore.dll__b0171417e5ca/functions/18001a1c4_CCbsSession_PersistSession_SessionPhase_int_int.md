# CCbsSession::PersistSession(SessionPhase *,int,int)

- ea: `0x18001a1c4`
- end: `0x18001d158`
- name: `?PersistSession@CCbsSession@@QEAAJPEAUSessionPhase@@HH@Z`
- size: `12180`
- prototype: `__int64 __fastcall(CCbsSession *__hidden this, struct SessionPhase *, int, int)`
- caller_count: `16`
- callee_count: `36`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800aea00`
- `0x1800e23c4`
- `0x1800e43ec`
- `0x1801d13c8`
- `0x1801d14e8`
- `0x1801d1668`
- `0x1801d1784`
- `0x1801d1838`
- `0x1801d1b14`
- `0x1801d1bd0`
- `0x1801d1c90`
- `0x1801d1d44`
- `0x1801d1f78`
- `0x1801d203c`
- `0x1801d2174`
- `0x1801d23c0`

## callees

- `0x180010b60`
- `0x180013250`
- `0x180019bdc`
- `0x18001a160`
- `0x18001a1c4`
- `0x18001d160`
- `0x180042130`
- `0x180043840`
- `0x18004b304`
- `0x18004bf9c`
- `0x18004d564`
- `0x180051c8c`
- `0x18005a2a0`
- `0x1800653d8`
- `0x18006a764`
- `0x18008f908`
- `0x180093c4c`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800a26b0`
- `0x1800a8678`
- `0x1800ad504`
- `0x1800b2990`
- `0x1800b851c`
- `0x1800d0588`
- `0x1800eb920`
- `0x1800ec920`
- `0x1800fe364`
- `0x180128c10`
- `0x18012b5e4`
- `0x1801d5f70`
- `0x1801d6150`
- `0x1801fc814`
- `0x1802d5010`

## string_xrefs

- `0x18001c15c`: `update`
- `0x18001b6c2`: `Complete`
- `0x18001cbd0`: `Failed to open actions.`
- `0x18001ccd4`: `Failed to open actions.`
- `0x18001ba61`: `Failed to open tasks element.`
- `0x18001ba16`: `Tasks`
- `0x18001cc18`: `Tasks`
- `0x18001b9cf`: `Failed to close update element.`
- `0x18001bad0`: `Failed to close update element.`
- `0x18001c758`: `Failed to close update element.`
- `0x18001a53d`: `Failed to open session element.`
- `0x18001a4a3`: `Failed to create XML writter.`
- `0x18001a41b`: `Failed to create string builder.`
- `0x18001c808`: `Failed to emit update name.`
- `0x18001c860`: `Failed to open update element.`
- `0x18001c6a8`: `Failed to open package element.`
- `0x18001ca70`: `Failed to open package element.`
- `0x18001cc46`: `Failed to close tasks.`
- `0x18001b0fd`: `Failed to emit finalize WinRE Command.`
- `0x18001b0bb`: `finalizeWinRECommand`
- `0x18001a390`: `Failed to mark session complete on session: {}`

## pseudocode

```c
__int64 __fastcall CCbsSession::PersistSession(CCbsSession *this, struct SessionPhase *a2, int a3, int a4)
{
  unsigned __int64 v7; // r15
  __int64 v9; // r9
  unsigned int v10; // eax
  __int64 v11; // r8
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx
  unsigned int v15; // edi
  int v17; // eax
  __int64 v18; // rdx
  unsigned __int64 v19; // r9
  int v20; // eax
  int v21; // edi
  int v22; // edx
  __int64 v23; // rdx
  int v24; // eax
  int v25; // edx
  struct Windows::Microdom::Rtl::IRtlXmlWriter *v26; // rbx
  __int64 v27; // rax
  int v28; // eax
  int v29; // edx
  __int64 (__fastcall *v30)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  __int64 v31; // rax
  __int64 v32; // xmm1_8
  int v33; // eax
  int v34; // edx
  __int64 (__fastcall *v35)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  __int64 v36; // rax
  __int64 v37; // xmm1_8
  int v38; // eax
  int v39; // edx
  __int64 (__fastcall *v40)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  __int64 v41; // rax
  __int64 v42; // xmm1_8
  int v43; // eax
  int v44; // edx
  __int64 (__fastcall *v45)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  wchar_t *v46; // rax
  __int64 v47; // rax
  __int64 v48; // xmm1_8
  int v49; // eax
  int v50; // edx
  __int64 (__fastcall *v51)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  wchar_t *v52; // rax
  __int64 v53; // rax
  __int64 v54; // xmm1_8
  int v55; // eax
  int v56; // edx
  __int64 (__fastcall *v57)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  __int64 v58; // rax
  __int64 v59; // rax
  __int64 v60; // xmm1_8
  int v61; // eax
  int v62; // edx
  const wchar_t *v63; // rdx
  __int64 (__fastcall *v64)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  __int64 v65; // rax
  __int64 v66; // xmm1_8
  int v67; // eax
  int v68; // edx
  const wchar_t *v69; // rdx
  __int64 (__fastcall *v70)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  __int64 v71; // rax
  __int64 v72; // xmm1_8
  int v73; // eax
  int v74; // edx
  unsigned int v75; // ecx
  __int64 (__fastcall *v76)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  wchar_t *v77; // rax
  __int64 v78; // rax
  __int64 v79; // xmm1_8
  int v80; // eax
  int v81; // edx
  int v82; // eax
  __int64 (__fastcall *v83)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  __int64 v84; // rax
  __int64 v85; // xmm1_8
  int v86; // eax
  unsigned int v87; // edi
  int v88; // edx
  __int64 (__fastcall *v89)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  wchar_t *v90; // rax
  __int64 v91; // rax
  __int64 v92; // xmm1_8
  int v93; // eax
  int v94; // edx
  volatile signed __int64 *v95; // rcx
  int v96; // eax
  __int64 (__fastcall *v97)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  __int64 v98; // rax
  __int64 v99; // xmm1_8
  int v100; // eax
  int v101; // edx
  __int64 v102; // rdx
  struct Windows::Microdom::Rtl::IRtlXmlWriter *v103; // rsi
  __int64 (__fastcall *v104)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  __int64 v105; // rax
  __int64 v106; // xmm1_8
  int v107; // eax
  int v108; // edx
  __int64 v109; // rdx
  __int64 (__fastcall *v110)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  __int64 v111; // rax
  __int64 v112; // xmm1_8
  int v113; // eax
  int v114; // edx
  __int64 (__fastcall *v115)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  __int64 v116; // rax
  __int64 v117; // xmm1_8
  int v118; // eax
  int v119; // edx
  __int64 (__fastcall *v120)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  __int64 v121; // rax
  __int64 v122; // xmm1_8
  int v123; // eax
  int v124; // edx
  __int64 (__fastcall *v125)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  __int64 v126; // rax
  __int64 v127; // xmm1_8
  int v128; // eax
  int v129; // edx
  __int64 (__fastcall *v130)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  wchar_t *v131; // rax
  __int64 v132; // rax
  __int64 v133; // xmm1_8
  int v134; // eax
  int v135; // edx
  __int64 v136; // rdx
  __int64 (__fastcall *v137)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  __int64 v138; // rax
  __int64 v139; // xmm1_8
  int v140; // eax
  int v141; // edx
  __int64 v142; // rdx
  __int64 (__fastcall *v143)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  __int64 v144; // rax
  __int64 v145; // xmm1_8
  int v146; // eax
  int v147; // edx
  const wchar_t *v148; // rax
  const wchar_t *v149; // rax
  int LocalTimeString; // edi
  __int64 (__fastcall *v151)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  __int64 v152; // rax
  __int64 v153; // xmm1_8
  int v154; // eax
  int v155; // edx
  __int64 (__fastcall *v156)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  wchar_t *v157; // rax
  __int64 v158; // rax
  __int64 v159; // xmm1_8
  int v160; // eax
  int v161; // edx
  __int64 v162; // rdx
  __int64 (__fastcall *v163)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  __int64 v164; // rax
  __int64 v165; // xmm1_8
  int v166; // eax
  int v167; // edx
  __int64 v168; // rdx
  __int64 (__fastcall *v169)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  __int64 v170; // rax
  __int64 v171; // xmm1_8
  int v172; // eax
  int v173; // edx
  int v174; // eax
  int v175; // edx
  __int64 v176; // rax
  int v177; // eax
  int v178; // edx
  int v179; // eax
  int v180; // edx
  unsigned __int64 i; // r13
  __int64 v182; // rax
  __int64 (__fastcall *v183)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *); // rax
  __int64 (__fastcall *v184)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  wchar_t *v185; // rax
  __int64 v186; // rax
  __int64 v187; // xmm1_8
  unsigned __int64 v188; // rdx
  __int64 v189; // rax
  __int64 v190; // rsi
  __int64 v191; // rax
  __int64 v192; // rcx
  __int64 (__fastcall *v193)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  wchar_t *FastCbsIdentityString; // rax
  __int64 v195; // rax
  __int64 v196; // xmm1_8
  __int64 v197; // rdx
  __int64 (__fastcall *v198)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  __int64 v199; // rax
  __int64 v200; // xmm1_8
  __int64 v201; // rdx
  __int64 (__fastcall *v202)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  __int64 v203; // rax
  __int64 v204; // xmm1_8
  __int64 (__fastcall *v205)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  __int64 v206; // rax
  __int64 v207; // rax
  __int64 v208; // xmm1_8
  __int64 (__fastcall *v209)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  wchar_t *v210; // rax
  __int64 v211; // rax
  __int64 v212; // xmm1_8
  wchar_t *v213; // r12
  unsigned __int64 v214; // rdx
  __int64 v215; // rax
  __int64 v216; // rsi
  __int64 v217; // rax
  __int64 (__fastcall *v218)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  __int64 v219; // rax
  const wchar_t *v220; // rdx
  __int64 v221; // rax
  __int64 v222; // xmm1_8
  const wchar_t **v223; // r15
  __int64 v224; // rcx
  const wchar_t *v225; // rdx
  __int64 (__fastcall *v226)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  __int64 v227; // rax
  __int64 v228; // xmm1_8
  __int64 (__fastcall *v229)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  __int64 v230; // rax
  __int64 v231; // rax
  __int64 v232; // xmm1_8
  __int64 (__fastcall *v233)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  wchar_t *v234; // rax
  __int64 v235; // rax
  __int64 v236; // xmm1_8
  unsigned __int64 j; // r15
  unsigned __int64 v238; // rax
  __int64 v239; // r12
  __int64 v240; // rax
  __int64 (__fastcall *v241)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  __int64 v242; // rax
  __int64 v243; // xmm1_8
  __int64 (__fastcall *v244)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  __int64 v245; // rax
  __int64 v246; // rax
  __int64 v247; // xmm1_8
  unsigned int v248; // ecx
  __int64 (__fastcall *v249)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  wchar_t *v250; // rax
  __int64 v251; // rax
  __int64 v252; // xmm1_8
  int v253; // eax
  int v254; // edx
  bool v255; // zf
  __int64 v256; // rax
  __int64 (__fastcall *v257)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *); // rax
  int v258; // eax
  int v259; // edx
  __int64 v260; // rax
  int v261; // edx
  int v262; // edx
  int v263; // edx
  int v264; // edx
  int v265; // edx
  int v266; // edx
  int v267; // edx
  int v268; // edx
  int v269; // edx
  int v270; // edx
  int v271; // edx
  int v272; // edx
  int v273; // edx
  int v274; // edx
  int v275; // edx
  int v276; // edx
  int v277; // edx
  int v278; // edx
  int v279; // edx
  int v280; // edx
  int v281; // edx
  int v282; // edx
  __int64 (__fastcall *v283)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *); // rax
  int v284; // eax
  int v285; // edx
  __int64 v286; // rax
  int v287; // eax
  int v288; // edx
  int v289; // eax
  int v290; // edx
  int v291; // r12d
  unsigned __int64 k; // rsi
  struct SessionPhase *v293; // r15
  struct SessionPhase *v294; // r8
  struct SessionPhase *v295; // r8
  int v296; // eax
  __int64 v297; // rax
  int v298; // eax
  int v299; // edx
  __int64 v300; // rax
  int v301; // eax
  int v302; // edx
  int v303; // eax
  int v304; // edx
  int v305; // eax
  int v306; // [rsp+20h] [rbp-E0h]
  int *v307; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v308; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v309; // [rsp+40h] [rbp-C0h]
  const wchar_t *v310; // [rsp+48h] [rbp-B8h]
  wchar_t *v311; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v312; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v313; // [rsp+68h] [rbp-98h]
  _BYTE v314[24]; // [rsp+70h] [rbp-90h] BYREF
  wchar_t *v315; // [rsp+88h] [rbp-78h] BYREF
  struct Windows::Microdom::Rtl::IRtlXmlWriter *v316; // [rsp+90h] [rbp-70h] BYREF
  __int64 v317; // [rsp+98h] [rbp-68h] BYREF
  __int64 v318; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v319; // [rsp+A8h] [rbp-58h] BYREF
  int *v320; // [rsp+B0h] [rbp-50h] BYREF
  int v321; // [rsp+B8h] [rbp-48h] BYREF
  int v322[2]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int64 v323[2]; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int8 *v324; // [rsp+D8h] [rbp-28h]
  char v325[144]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  v322[0] = a4;
  v7 = 0;
  v315 = 0;
  v319 = 0;
  memset_0(v325, 0, 0x81u);
  v318 = 0;
  v317 = 0;
  v316 = 0;
  v9 = 208;
  v324 = 0;
  *(_OWORD *)v323 = 0;
  if ( !a4 )
    v9 = *((unsigned int *)this + 192);
  v10 = *((_DWORD *)a2 + 80);
  v11 = v10 + 10000;
  if ( !*((_DWORD *)a2 + 82) )
    v11 = v10;
  v12 = PackageStorePersistSessionState(this, 0, v11, v9);
  v15 = v12;
  if ( v12 >= 0 )
  {
    if ( a3 )
    {
      if ( !a4 )
      {
LABEL_12:
        v15 = 0;
LABEL_13:
        Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(v323);
        Windows::Auto<Windows::Rtl::IRtlIniFile *>::~Auto<Windows::Rtl::IRtlIniFile *>(&v316);
        Windows::Auto<Windows::Rtl::IRtlIniFile *>::~Auto<Windows::Rtl::IRtlIniFile *>(&v317);
        Windows::Auto<Windows::Rtl::IRtlIniFile *>::~Auto<Windows::Rtl::IRtlIniFile *>(&v318);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v319);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v315);
        return v15;
      }
    }
    else if ( !a4 )
    {
      goto LABEL_22;
    }
    v17 = PackageStoreMarkSessionComplete(this, 0);
    v15 = v17;
    if ( v17 < 0 )
    {
      v321 = v17;
      if ( LogAdapter::g_Logger )
      {
        v311 = (wchar_t *)*((_QWORD *)this + 80);
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (__int64)"Failed to mark session complete on session: {}",
          (__int64)&v311);
        *(_QWORD *)v322 = &v321;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v322);
      }
      v18 = 415;
      goto LABEL_20;
    }
LABEL_22:
    v20 = RtlCreateUtf8UCSStringBuilder(v14, v13, &v318, &v317);
    v21 = v20;
    if ( v20 < 0 )
    {
      v321 = v20;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to create string builder.");
        v311 = (wchar_t *)&v321;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v22,
          3,
          (unsigned int)": {}",
          (__int64)&v311);
      }
      v23 = 420;
      goto LABEL_26;
    }
    v24 = RtlCreateDefaultXmlWriter(10, v317, &v316);
    v21 = v24;
    if ( v24 < 0 )
    {
      v321 = v24;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to create XML writter.");
        v311 = (wchar_t *)&v321;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v25,
          3,
          (unsigned int)": {}",
          (__int64)&v311);
      }
      v23 = 427;
      goto LABEL_26;
    }
    v26 = v316;
    v27 = *(_QWORD *)v316;
    v310 = L"Session";
    v308 = 14;
    v309 = 16;
    v28 = (*(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *))(v27 + 16))(
            v316,
            0,
            &v308);
    v21 = v28;
    if ( v28 < 0 )
    {
      v321 = v28;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to open session element.");
        v311 = (wchar_t *)&v321;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v29,
          3,
          (unsigned int)": {}",
          (__int64)&v311);
      }
      v23 = 464;
      goto LABEL_26;
    }
    v30 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v26 + 88LL);
    v31 = StringToUnicodeString(v314, L"8.0");
    v312 = *(_OWORD *)v31;
    v32 = *(_QWORD *)(v31 + 16);
    v310 = L"version";
    v313 = v32;
    v308 = 14;
    v309 = 16;
    v33 = v30(v26, 0, &v308, &v312);
    v21 = v33;
    if ( v33 < 0 )
    {
      v321 = v33;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to emit version.");
        v311 = (wchar_t *)&v321;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v34,
          3,
          (unsigned int)": {}",
          (__int64)&v311);
      }
      v23 = 468;
      goto LABEL_26;
    }
    v35 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v26 + 88LL);
    v36 = StringToUnicodeString(v314, *((_QWORD *)this + 80));
    v312 = *(_OWORD *)v36;
    v37 = *(_QWORD *)(v36 + 16);
    v310 = L"id";
    v313 = v37;
    v308 = 4;
    v309 = 6;
    v38 = v35(v26, 0, &v308, &v312);
    v21 = v38;
    if ( v38 < 0 )
    {
      v321 = v38;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to emit session id.");
        v311 = (wchar_t *)&v321;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v39,
          3,
          (unsigned int)": {}",
          (__int64)&v311);
      }
      v23 = 471;
      goto LABEL_26;
    }
    v40 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v26 + 88LL);
    v41 = StringToUnicodeString(v314, *((_QWORD *)this + 81));
    v312 = *(_OWORD *)v41;
    v42 = *(_QWORD *)(v41 + 16);
    v310 = L"client";
    v313 = v42;
    v308 = 12;
    v309 = 14;
    v43 = v40(v26, 0, &v308, &v312);
    v21 = v43;
    if ( v43 < 0 )
    {
      v321 = v43;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to emit client.");
        v311 = (wchar_t *)&v321;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v44,
          3,
          (unsigned int)": {}",
          (__int64)&v311);
      }
      v23 = 475;
      goto LABEL_26;
    }
    v45 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v26 + 88LL);
    v46 = numToString(*((_DWORD *)this + 172));
    v47 = StringToUnicodeString(v314, v46);
    v312 = *(_OWORD *)v47;
    v48 = *(_QWORD *)(v47 + 16);
    v310 = L"options";
    v313 = v48;
    v308 = 14;
    v309 = 16;
    v49 = v45(v26, 0, &v308, &v312);
    v21 = v49;
    if ( v49 < 0 )
    {
      v321 = v49;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to emit options.");
        v311 = (wchar_t *)&v321;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v50,
          3,
          (unsigned int)": {}",
          (__int64)&v311);
      }
      v23 = 479;
      goto LABEL_26;
    }
    v51 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v26 + 88LL);
    v52 = numToString(*((_DWORD *)this + 254));
    v53 = StringToUnicodeString(v314, v52);
    v312 = *(_OWORD *)v53;
    v54 = *(_QWORD *)(v53 + 16);
    v310 = L"currentPhase";
    v313 = v54;
    v308 = 24;
    v309 = 26;
    v55 = v51(v26, 0, &v308, &v312);
    v21 = v55;
    if ( v55 < 0 )
    {
      v321 = v55;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to emit currentPhase.");
        v311 = (wchar_t *)&v321;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v56,
          3,
          (unsigned int)": {}",
          (__int64)&v311);
      }
      v23 = 486;
      goto LABEL_26;
    }
    v57 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v26 + 88LL);
    v58 = CbsSessionStateToString(*((unsigned int *)this + 192));
    v59 = StringToUnicodeString(v314, v58);
    v312 = *(_OWORD *)v59;
    v60 = *(_QWORD *)(v59 + 16);
    v310 = L"lastSuccessfulState";
    v313 = v60;
    v308 = 38;
    v309 = 40;
    v61 = v57(v26, 0, &v308, &v312);
    v21 = v61;
    if ( v61 < 0 )
    {
      v321 = v61;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to emit lastSuccessfulState.");
        v311 = (wchar_t *)&v321;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v62,
          3,
          (unsigned int)": {}",
          (__int64)&v311);
      }
      v23 = 493;
      goto LABEL_26;
    }
    v63 = L"true";
    if ( !*((_DWORD *)this + 220) )
      v63 = L"false";
    v64 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v26 + 88LL);
    v65 = StringToUnicodeString(v314, v63);
    v312 = *(_OWORD *)v65;
    v66 = *(_QWORD *)(v65 + 16);
    v310 = L"pendingFollower";
    v313 = v66;
    v308 = 30;
    v309 = 32;
    v67 = v64(v26, 0, &v308, &v312);
    v21 = v67;
    if ( v67 < 0 )
    {
      v321 = v67;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to emit pendingFollower.");
        v311 = (wchar_t *)&v321;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v68,
          3,
          (unsigned int)": {}",
          (__int64)&v311);
      }
      v23 = 500;
      goto LABEL_26;
    }
    v69 = L"true";
    if ( !*((_DWORD *)this + 264) )
      v69 = L"false";
    v70 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v26 + 88LL);
    v71 = StringToUnicodeString(v314, v69);
    v312 = *(_OWORD *)v71;
    v72 = *(_QWORD *)(v71 + 16);
    v310 = L"retry";
    v313 = v72;
    v308 = 10;
    v309 = 12;
    v73 = v70(v26, 0, &v308, &v312);
    v21 = v73;
    if ( v73 < 0 )
    {
      v321 = v73;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to emit retry.");
        v311 = (wchar_t *)&v321;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v74,
          3,
          (unsigned int)": {}",
          (__int64)&v311);
      }
      v23 = 507;
      goto LABEL_26;
    }
    v75 = *((_DWORD *)this + 553);
    if ( v75 )
    {
      v76 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v26 + 88LL);
      v77 = numToString(v75);
      v78 = StringToUnicodeString(v314, v77);
      v312 = *(_OWORD *)v78;
      v79 = *(_QWORD *)(v78 + 16);
      v310 = L"UUPOperation";
      v313 = v79;
      v308 = 24;
      v309 = 26;
      v80 = v76(v26, 0, &v308, &v312);
      v21 = v80;
      if ( v80 < 0 )
      {
        v321 = v80;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to emit UUP operation.");
          v311 = (wchar_t *)&v321;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v81,
            3,
            (unsigned int)": {}",
            (__int64)&v311);
        }
        v23 = 516;
        goto LABEL_26;
      }
    }
    if ( *((_QWORD *)this + 231) )
    {
      v311 = 0;
      v82 = CCbsStringArray::SaveAsStringList((CCbsSession *)((char *)this + 1824), L";", &v311);
      v15 = v82;
      if ( v82 < 0 )
      {
        v321 = v82;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Out of memory");
          *(_QWORD *)v322 = &v321;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)v322);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x20A,
          (unsigned int)"onecore\\base\\cbs\\core\\cbssessionpersistence.cpp",
          (const char *)v15,
          v306);
LABEL_81:
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v311);
        goto LABEL_13;
      }
      v83 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v26 + 88LL);
      v84 = StringToUnicodeString(v314, v311);
      v312 = *(_OWORD *)v84;
      v85 = *(_QWORD *)(v84 + 16);
      v310 = L"onDemandFeatureList";
      v313 = v85;
      v308 = 38;
      v309 = 40;
      v86 = v83(v26, 0, &v308, &v312);
      v87 = v86;
      if ( v86 < 0 )
      {
        v321 = v86;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to emit client.");
          *(_QWORD *)v322 = &v321;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v88,
            3,
            (unsigned int)": {}",
            (__int64)v322);
        }
        v15 = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)0x20D,
                (unsigned int)"onecore\\base\\cbs\\core\\cbssessionpersistence.cpp",
                (const char *)v87,
                v306);
        goto LABEL_81;
      }
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v311);
    }
    v89 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v26 + 88LL);
    v90 = numToString(*((_DWORD *)this + 552));
    v91 = StringToUnicodeString(v314, v90);
    v312 = *(_OWORD *)v91;
    v92 = *(_QWORD *)(v91 + 16);
    v310 = L"operationCovered";
    v313 = v92;
    v308 = 32;
    v309 = 34;
    v93 = v89(v26, 0, &v308, &v312);
    v21 = v93;
    if ( v93 < 0 )
    {
      v321 = v93;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to emit operation covered.");
        v311 = (wchar_t *)&v321;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v94,
          3,
          (unsigned int)": {}",
          (__int64)&v311);
      }
      v23 = 533;
      goto LABEL_26;
    }
    v95 = (volatile signed __int64 *)*((_QWORD *)this + 82);
    if ( v95
      && TraceLoggingCorrelationVector::ToStringImpl(
           (TraceLoggingCorrelationVector *)v95,
           _InterlockedExchangeAdd64(v95 + 17, 0),
           v325) )
    {
      v96 = SczAllocFromAnsiSz(&v319, v325);
      v15 = v96;
      if ( v96 < 0 )
      {
        v19 = (unsigned int)v96;
        v18 = 537;
        goto LABEL_21;
      }
      v97 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v26 + 88LL);
      v98 = StringToUnicodeString(v314, v319);
      v312 = *(_OWORD *)v98;
      v99 = *(_QWORD *)(v98 + 16);
      v310 = L"correlationVector";
      v313 = v99;
      v308 = 34;
      v309 = 36;
      v100 = v97(v26, 0, &v308, &v312);
      v21 = v100;
      if ( v100 < 0 )
      {
        v321 = v100;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to emit correlationVector.");
          v311 = (wchar_t *)&v321;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v101,
            3,
            (unsigned int)": {}",
            (__int64)&v311);
        }
        v23 = 541;
        goto LABEL_26;
      }
    }
    else
    {
      LogAdapter::TraceAtLevel<>(1, "Unable to get correlation vector string");
    }
    v102 = *((_QWORD *)this + 277);
    v103 = v26;
    if ( v102 )
    {
      v104 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v26 + 88LL);
      v105 = StringToUnicodeString(v314, v102);
      v312 = *(_OWORD *)v105;
      v106 = *(_QWORD *)(v105 + 16);
      v310 = L"usoCorrelationVector";
      v313 = v106;
      v308 = 40;
      v309 = 42;
      v107 = v104(v26, 0, &v308, &v312);
      v21 = v107;
      if ( v107 < 0 )
      {
        v321 = v107;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to emit correlationVector.");
          v311 = (wchar_t *)&v321;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v108,
            3,
            (unsigned int)": {}",
            (__int64)&v311);
        }
        v23 = 555;
        goto LABEL_26;
      }
    }
    v109 = *((_QWORD *)this + 216);
    if ( v109 )
    {
      v110 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v26 + 88LL);
      v111 = StringToUnicodeString(v314, v109);
      v312 = *(_OWORD *)v111;
      v112 = *(_QWORD *)(v111 + 16);
      v310 = L"finalizeWinRECommand";
      v313 = v112;
      v308 = 40;
      v309 = 42;
      v113 = v110(v26, 0, &v308, &v312);
      v21 = v113;
      if ( v113 < 0 )
      {
        v321 = v113;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to emit finalize WinRE Command.");
          v311 = (wchar_t *)&v321;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v114,
            3,
            (unsigned int)": {}",
            (__int64)&v311);
        }
        v23 = 566;
        goto LABEL_26;
      }
    }
    if ( *((_BYTE *)this + 2272) )
    {
      v115 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v26 + 88LL);
      v116 = StringToUnicodeString(v314, L"true");
      v312 = *(_OWORD *)v116;
      v117 = *(_QWORD *)(v116 + 16);
      v310 = L"onePackageSession";
      v313 = v117;
      v308 = 34;
      v309 = 36;
      v118 = v115(v26, 0, &v308, &v312);
      v21 = v118;
      if ( v118 < 0 )
      {
        v321 = v118;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to emit Onepackage session.");
          v311 = (wchar_t *)&v321;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v119,
            3,
            (unsigned int)": {}",
            (__int64)&v311);
        }
        v23 = 575;
        goto LABEL_26;
      }
      v120 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v26 + 88LL);
      v121 = StringToUnicodeString(v314, *((_QWORD *)this + 288));
      v312 = *(_OWORD *)v121;
      v122 = *(_QWORD *)(v121 + 16);
      v310 = L"onePackageSandbox";
      v313 = v122;
      v308 = 34;
      v309 = 36;
      v123 = v120(v26, 0, &v308, &v312);
      v21 = v123;
      if ( v123 < 0 )
      {
        v321 = v123;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to emit Onepackage sandbox.");
          v311 = (wchar_t *)&v321;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v124,
            3,
            (unsigned int)": {}",
            (__int64)&v311);
        }
        v23 = 582;
        goto LABEL_26;
      }
      v125 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v26 + 88LL);
      v126 = StringToUnicodeString(v314, *((_QWORD *)this + 287));
      v312 = *(_OWORD *)v126;
      v127 = *(_QWORD *)(v126 + 16);
      v310 = L"onePackageCab";
      v313 = v127;
      v308 = 26;
      v309 = 28;
      v128 = v125(v26, 0, &v308, &v312);
      v21 = v128;
      if ( v128 < 0 )
      {
        v321 = v128;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to emit Onepackage cab location.");
          v311 = (wchar_t *)&v321;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v129,
            3,
            (unsigned int)": {}",
            (__int64)&v311);
        }
        v23 = 589;
        goto LABEL_26;
      }
      v130 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v26 + 88LL);
      v131 = numToString(*((_DWORD *)this + 572));
      v132 = StringToUnicodeString(v314, v131);
      v312 = *(_OWORD *)v132;
      v133 = *(_QWORD *)(v132 + 16);
      v310 = L"onePackagePackageType";
      v313 = v133;
      v308 = 42;
      v309 = 44;
      v134 = v130(v26, 0, &v308, &v312);
      v21 = v134;
      if ( v134 < 0 )
      {
        v321 = v134;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to emit Onepackage package type.");
          v311 = (wchar_t *)&v321;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v135,
            3,
            (unsigned int)": {}",
            (__int64)&v311);
        }
        v23 = 596;
        goto LABEL_26;
      }
    }
    v136 = *((_QWORD *)this + 289);
    if ( v136 )
    {
      v137 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v26 + 88LL);
      v138 = StringToUnicodeString(v314, v136);
      v312 = *(_OWORD *)v138;
      v139 = *(_QWORD *)(v138 + 16);
      v310 = L"childMuV6SessionId";
      v313 = v139;
      v308 = 36;
      v309 = 38;
      v140 = v137(v26, 0, &v308, &v312);
      v21 = v140;
      if ( v140 < 0 )
      {
        v321 = v140;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to emit child MuV6 session id.");
          v311 = (wchar_t *)&v321;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v141,
            3,
            (unsigned int)": {}",
            (__int64)&v311);
        }
        v23 = 605;
        goto LABEL_26;
      }
    }
    v142 = *((_QWORD *)this + 292);
    if ( v142 )
    {
      v143 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v26 + 88LL);
      v144 = StringToUnicodeString(v314, v142);
      v312 = *(_OWORD *)v144;
      v145 = *(_QWORD *)(v144 + 16);
      v310 = L"containerTransactionId";
      v313 = v145;
      v308 = 44;
      v309 = 46;
      v146 = v143(v26, 0, &v308, &v312);
      v21 = v146;
      if ( v146 < 0 )
      {
        v321 = v146;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to emit child container transaction id.");
          v311 = (wchar_t *)&v321;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v147,
            3,
            (unsigned int)": {}",
            (__int64)&v311);
        }
        v23 = 614;
        goto LABEL_26;
      }
      v320 = (int *)*((_QWORD *)this + 80);
      v307 = (int *)*((_QWORD *)this + 292);
      if ( LogAdapter::g_Logger )
        LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
          (__int64)LogAdapter::g_Logger,
          1,
          1,
          (__int64)"Preserving '{}' as the container transaction id for session '{}'",
          (__int64)&v307,
          (__int64)&v320);
    }
    if ( a4 )
    {
      v148 = (const wchar_t *)CbsSessionStateToString(32);
      CCbsSession::EmitAttribute(this, v26, v148, 1u, 0);
      v149 = (const wchar_t *)CbsSessionStateToString(48);
      CCbsSession::EmitAttribute(this, v26, v149, 1u, 0);
      LocalTimeString = GetLocalTimeString(&v315);
      LogAdapter::TraceAtLevelIfFailed<long,>(1, (unsigned int)LocalTimeString, "Unable to get local time");
      if ( LocalTimeString >= 0 )
      {
        v151 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v26 + 88LL);
        v152 = StringToUnicodeString(v314, v315);
        v312 = *(_OWORD *)v152;
        v153 = *(_QWORD *)(v152 + 16);
        v310 = L"Complete";
        v313 = v153;
        v308 = 16;
        v309 = 18;
        v154 = v151(v26, 0, &v308, &v312);
        v21 = v154;
        if ( v154 < 0 )
        {
          v321 = v154;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to emit version.");
            v307 = &v321;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v155,
              3,
              (unsigned int)": {}",
              (__int64)&v307);
          }
          v23 = 634;
          goto LABEL_26;
        }
      }
      v156 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v26 + 88LL);
      v157 = numToHexString(*((_DWORD *)this + 258));
      v158 = StringToUnicodeString(v314, v157);
      v312 = *(_OWORD *)v158;
      v159 = *(_QWORD *)(v158 + 16);
      v310 = L"status";
      v313 = v159;
      v308 = 12;
      v309 = 14;
      v160 = v156(v26, 0, &v308, &v312);
      v21 = v160;
      if ( v160 < 0 )
      {
        v321 = v160;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to persist status.");
          v307 = &v321;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v161,
            3,
            (unsigned int)": {}",
            (__int64)&v307);
        }
        v23 = 639;
        goto LABEL_26;
      }
      v162 = *((_QWORD *)this + 133);
      if ( v162 )
      {
        v163 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v26 + 88LL);
        v164 = StringToUnicodeString(v314, v162);
        v312 = *(_OWORD *)v164;
        v165 = *(_QWORD *)(v164 + 16);
        v310 = L"Culprit";
        v313 = v165;
        v308 = 14;
        v309 = 16;
        v166 = v163(v26, 0, &v308, &v312);
        v21 = v166;
        if ( v166 < 0 )
        {
          v321 = v166;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to emit culprit package.");
            v307 = &v321;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v167,
              3,
              (unsigned int)": {}",
              (__int64)&v307);
          }
          v23 = 645;
          goto LABEL_26;
        }
      }
      v168 = *((_QWORD *)this + 134);
      if ( v168 )
      {
        v169 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v26 + 88LL);
        v170 = StringToUnicodeString(v314, v168);
        v312 = *(_OWORD *)v170;
        v171 = *(_QWORD *)(v170 + 16);
        v310 = L"ErrorDetail";
        v313 = v171;
        v308 = 22;
        v309 = 24;
        v172 = v169(v26, 0, &v308, &v312);
        v21 = v172;
        if ( v172 < 0 )
        {
          v321 = v172;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to emit error detail.");
            v307 = &v321;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v173,
              3,
              (unsigned int)": {}",
              (__int64)&v307);
          }
          v23 = 652;
          goto LABEL_26;
        }
      }
    }
    v174 = (*(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD))(*(_QWORD *)v26 + 48LL))(
             v26,
             0);
    v21 = v174;
    if ( v174 < 0 )
    {
      v321 = v174;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to close update element.");
        v307 = &v321;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v175,
          3,
          (unsigned int)": {}",
          (__int64)&v307);
      }
      v23 = 656;
      goto LABEL_26;
    }
    v176 = *(_QWORD *)v26;
    v310 = L"Tasks";
    v308 = 10;
    v309 = 12;
    v177 = (*(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *))(v176 + 16))(
             v26,
             0,
             &v308);
    v21 = v177;
    if ( v177 < 0 )
    {
      v321 = v177;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to open tasks element.");
        v307 = &v321;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v178,
          3,
          (unsigned int)": {}",
          (__int64)&v307);
      }
      v23 = 659;
      goto LABEL_26;
    }
    v179 = (*(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD))(*(_QWORD *)v26 + 48LL))(
             v26,
             0);
    v21 = v179;
    if ( v179 < 0 )
    {
      v321 = v179;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to close update element.");
        v307 = &v321;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v180,
          3,
          (unsigned int)": {}",
          (__int64)&v307);
      }
      v23 = 661;
      goto LABEL_26;
    }
    for ( i = 0; ; ++i )
    {
      v182 = *(_QWORD *)v103;
      v308 = 10;
      v309 = 12;
      if ( i >= *((_QWORD *)this + 122) )
        break;
      v183 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *))(v182 + 16);
      v310 = L"Phase";
      v21 = v183(v103, 0, &v308);
      if ( v21 < 0 )
      {
        v321 = v21;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to open actions.");
          v307 = &v321;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v282,
            3,
            (unsigned int)": {}",
            (__int64)&v307);
        }
        v23 = 665;
        goto LABEL_26;
      }
      v184 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v103 + 88LL);
      v185 = numToString((int)i + 1);
      v186 = StringToUnicodeString(v314, v185);
      v312 = *(_OWORD *)v186;
      v187 = *(_QWORD *)(v186 + 16);
      v310 = L"seq";
      v313 = v187;
      v308 = 6;
      v309 = 8;
      v21 = v184(v103, 0, &v308, &v312);
      if ( v21 < 0 )
      {
        v321 = v21;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to emit phase.");
          v307 = &v321;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v281,
            3,
            (unsigned int)": {}",
            (__int64)&v307);
        }
        v23 = 672;
        goto LABEL_26;
      }
      v21 = (*(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD))(*(_QWORD *)v103 + 48LL))(
              v103,
              0);
      if ( v21 < 0 )
      {
        v321 = v21;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to end phase.");
          v307 = &v321;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v280,
            3,
            (unsigned int)": {}",
            (__int64)&v307);
        }
        v23 = 674;
        goto LABEL_26;
      }
      while ( 1 )
      {
        v188 = *((_QWORD *)this + 122);
        if ( i >= v188 )
          __fastfail(8u);
        v189 = *(_QWORD *)(*((_QWORD *)this + 124) + 8 * i);
        if ( v7 >= *(_QWORD *)(v189 + 88) )
          break;
        if ( i >= v188 )
          __fastfail(8u);
        v190 = *(_QWORD *)(*(_QWORD *)(v189 + 104) + 8 * v7);
        v191 = *(_QWORD *)v26;
        v310 = L"capability";
        v308 = 20;
        v309 = 22;
        v21 = (*(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *))(v191 + 16))(
                v26,
                0,
                &v308);
        if ( v21 < 0 )
        {
          v321 = v21;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to open package element.");
            v307 = &v321;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v267,
              3,
              (unsigned int)": {}",
              (__int64)&v307);
          }
          v23 = 681;
          goto LABEL_26;
        }
        v192 = *(_QWORD *)(v190 + 16);
        v193 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v26 + 88LL);
        if ( v192 )
          FastCbsIdentityString = GetFastCbsIdentityString(*(const struct CCbsIdentity **)(v192 + 136));
        else
          FastCbsIdentityString = *(wchar_t **)(v190 + 8);
        v195 = StringToUnicodeString(v314, FastCbsIdentityString);
        v312 = *(_OWORD *)v195;
        v196 = *(_QWORD *)(v195 + 16);
        v310 = L"id";
        v313 = v196;
        v308 = 4;
        v309 = 6;
        v21 = v193(v26, 0, &v308, &v312);
        if ( v21 < 0 )
        {
          v321 = v21;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to emit package id.");
            v307 = &v321;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v266,
              3,
              (unsigned int)": {}",
              (__int64)&v307);
          }
          v23 = 691;
          goto LABEL_26;
        }
        v197 = *(_QWORD *)(v190 + 32);
        if ( v197 )
        {
          v198 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v26 + 88LL);
          v199 = StringToUnicodeString(v314, v197);
          v312 = *(_OWORD *)v199;
          v200 = *(_QWORD *)(v199 + 16);
          v310 = L"displayName";
          v313 = v200;
          v308 = 22;
          v309 = 24;
          v21 = v198(v26, 0, &v308, &v312);
          if ( v21 < 0 )
          {
            v321 = v21;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to emit package displayName.");
              v307 = &v321;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v261,
                3,
                (unsigned int)": {}",
                (__int64)&v307);
            }
            v23 = 700;
            goto LABEL_26;
          }
        }
        v201 = *(_QWORD *)(v190 + 40);
        if ( v201 )
        {
          v202 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v26 + 88LL);
          v203 = StringToUnicodeString(v314, v201);
          v312 = *(_OWORD *)v203;
          v204 = *(_QWORD *)(v203 + 16);
          v310 = L"description";
          v313 = v204;
          v308 = 22;
          v309 = 24;
          v21 = v202(v26, 0, &v308, &v312);
          if ( v21 < 0 )
          {
            v321 = v21;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to emit package description.");
              v307 = &v321;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v262,
                3,
                (unsigned int)": {}",
                (__int64)&v307);
            }
            v23 = 710;
            goto LABEL_26;
          }
        }
        v205 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v26 + 88LL);
        v206 = CbsStateToString(*(unsigned int *)(v190 + 24));
        v207 = StringToUnicodeString(v314, v206);
        v312 = *(_OWORD *)v207;
        v208 = *(_QWORD *)(v207 + 16);
        v310 = L"targetState";
        v313 = v208;
        v308 = 22;
        v309 = 24;
        v21 = v205(v26, 0, &v308, &v312);
        if ( v21 < 0 )
        {
          v321 = v21;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to emit target state.");
            v307 = &v321;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v265,
              3,
              (unsigned int)": {}",
              (__int64)&v307);
          }
          v23 = 719;
          goto LABEL_26;
        }
        v209 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v26 + 88LL);
        v210 = numToString(*(_DWORD *)v190);
        v211 = StringToUnicodeString(v314, v210);
        v312 = *(_OWORD *)v211;
        v212 = *(_QWORD *)(v211 + 16);
        v310 = L"options";
        v313 = v212;
        v308 = 14;
        v309 = 16;
        v21 = v209(v26, 0, &v308, &v312);
        if ( v21 < 0 )
        {
          v321 = v21;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to emit package option.");
            v307 = &v321;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v264,
              3,
              (unsigned int)": {}",
              (__int64)&v307);
          }
          v23 = 726;
          goto LABEL_26;
        }
        v21 = (*(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, __int64))(*(_QWORD *)v26 + 48LL))(
                v26,
                1);
        if ( v21 < 0 )
        {
          v321 = v21;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to close capability element.");
            v307 = &v321;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v263,
              3,
              (unsigned int)": {}",
              (__int64)&v307);
          }
          v23 = 730;
          goto LABEL_26;
        }
        ++v7;
      }
      v7 = 0;
      v213 = 0;
      while ( 2 )
      {
        v214 = *((_QWORD *)this + 122);
        v311 = v213;
        if ( i >= v214 )
          __fastfail(8u);
        v215 = *(_QWORD *)(*((_QWORD *)this + 124) + 8 * i);
        if ( (unsigned __int64)v213 < *(_QWORD *)(v215 + 24) )
        {
          if ( i >= v214 )
            __fastfail(8u);
          v216 = *(_QWORD *)(*(_QWORD *)(v215 + 40) + 8LL * (_QWORD)v213);
          v217 = *(_QWORD *)v26;
          v310 = L"package";
          v308 = 14;
          v309 = 16;
          v21 = (*(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *))(v217 + 16))(
                  v26,
                  0,
                  &v308);
          if ( v21 < 0 )
          {
            v321 = v21;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to open package element.");
              v307 = &v321;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v278,
                3,
                (unsigned int)": {}",
                (__int64)&v307);
            }
            v23 = 738;
          }
          else
          {
            v218 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v26 + 88LL);
            v219 = *(_QWORD *)(v216 + 24);
            if ( v219 )
            {
              v220 = &qword_1802EB518;
              if ( *(_QWORD *)(v219 + 120) )
                v220 = *(const wchar_t **)(v219 + 120);
            }
            else
            {
              v220 = *(const wchar_t **)(v216 + 8);
            }
            v221 = StringToUnicodeString(v314, v220);
            v312 = *(_OWORD *)v221;
            v222 = *(_QWORD *)(v221 + 16);
            v310 = L"id";
            v313 = v222;
            v308 = 4;
            v309 = 6;
            v21 = v218(v26, 0, &v308, &v312);
            if ( v21 < 0 )
            {
              v321 = v21;
              if ( LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<>(
                  (__int64)LogAdapter::g_Logger,
                  0,
                  3,
                  (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to emit package id.");
                v307 = &v321;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
                  (_DWORD)LogAdapter::g_Logger,
                  v277,
                  3,
                  (unsigned int)": {}",
                  (__int64)&v307);
              }
              v23 = 748;
            }
            else
            {
              v223 = (const wchar_t **)(v216 + 16);
              if ( !*(_QWORD *)(v216 + 16) )
              {
                v224 = *(_QWORD *)(v216 + 24);
                if ( v224 )
                {
                  v306 = v216 + 16;
                  CCbsPackage::GetPropertyInternal(v224, 7, 0, 0);
                }
              }
              v225 = &qword_1802EB518;
              if ( *v223 )
                v225 = *v223;
              v226 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v26 + 88LL);
              v227 = StringToUnicodeString(v314, v225);
              v312 = *(_OWORD *)v227;
              v228 = *(_QWORD *)(v227 + 16);
              v310 = L"name";
              v313 = v228;
              v308 = 8;
              v309 = 10;
              v21 = v226(v26, 0, &v308, &v312);
              if ( v21 < 0 )
              {
                v321 = v21;
                if ( LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(
                    (__int64)LogAdapter::g_Logger,
                    0,
                    3,
                    (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to emit package name.");
                  v307 = &v321;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
                    (_DWORD)LogAdapter::g_Logger,
                    v276,
                    3,
                    (unsigned int)": {}",
                    (__int64)&v307);
                }
                v23 = 766;
              }
              else
              {
                v229 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v26 + 88LL);
                v230 = CbsStateToString(*(unsigned int *)(v216 + 32));
                v231 = StringToUnicodeString(v314, v230);
                v312 = *(_OWORD *)v231;
                v232 = *(_QWORD *)(v231 + 16);
                v310 = L"targetState";
                v313 = v232;
                v308 = 22;
                v309 = 24;
                v21 = v229(v26, 0, &v308, &v312);
                if ( v21 < 0 )
                {
                  v321 = v21;
                  if ( LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogNumObjects<>(
                      (__int64)LogAdapter::g_Logger,
                      0,
                      3,
                      (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to emit target state.");
                    v307 = &v321;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
                      (_DWORD)LogAdapter::g_Logger,
                      v275,
                      3,
                      (unsigned int)": {}",
                      (__int64)&v307);
                  }
                  v23 = 774;
                }
                else
                {
                  v233 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v26 + 88LL);
                  v234 = numToString(*(_DWORD *)v216);
                  v235 = StringToUnicodeString(v314, v234);
                  v312 = *(_OWORD *)v235;
                  v236 = *(_QWORD *)(v235 + 16);
                  v310 = L"options";
                  v313 = v236;
                  v308 = 14;
                  v309 = 16;
                  v21 = v233(v26, 0, &v308, &v312);
                  if ( v21 < 0 )
                  {
                    v321 = v21;
                    if ( LogAdapter::g_Logger )
                    {
                      LogAdapter::Logger::LogNumObjects<>(
                        (__int64)LogAdapter::g_Logger,
                        0,
                        3,
                        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to emit package option.");
                      v307 = &v321;
                      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
                        (_DWORD)LogAdapter::g_Logger,
                        v274,
                        3,
                        (unsigned int)": {}",
                        (__int64)&v307);
                    }
                    v23 = 781;
                  }
                  else if ( *(_QWORD *)(v216 + 64)
                         && (v21 = (*(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD))(*(_QWORD *)v26 + 48LL))(
                                     v26,
                                     0),
                             v21 < 0) )
                  {
                    v321 = v21;
                    if ( LogAdapter::g_Logger )
                    {
                      LogAdapter::Logger::LogNumObjects<>(
                        (__int64)LogAdapter::g_Logger,
                        0,
                        3,
                        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to end phase.");
                      v307 = &v321;
                      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
                        (_DWORD)LogAdapter::g_Logger,
                        v268,
                        3,
                        (unsigned int)": {}",
                        (__int64)&v307);
                    }
                    v23 = 785;
                  }
                  else
                  {
                    for ( j = 0; ; ++j )
                    {
                      v238 = *(_QWORD *)(v216 + 64);
                      if ( j >= v238 )
                        break;
                      v239 = *(_QWORD *)(*(_QWORD *)(v216 + 80) + 8 * j);
                      v240 = *(_QWORD *)v26;
                      v310 = L"update";
                      v308 = 12;
                      v309 = 14;
                      v21 = (*(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *))(v240 + 16))(
                              v26,
                              0,
                              &v308);
                      if ( v21 < 0 )
                      {
                        v321 = v21;
                        if ( LogAdapter::g_Logger )
                        {
                          LogAdapter::Logger::LogNumObjects<>(
                            (__int64)LogAdapter::g_Logger,
                            0,
                            3,
                            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to open update element.");
                          v307 = &v321;
                          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
                            (_DWORD)LogAdapter::g_Logger,
                            v272,
                            3,
                            (unsigned int)": {}",
                            (__int64)&v307);
                        }
                        v23 = 795;
                        goto LABEL_26;
                      }
                      v241 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v26 + 88LL);
                      v242 = StringToUnicodeString(v314, *(_QWORD *)v239);
                      v312 = *(_OWORD *)v242;
                      v243 = *(_QWORD *)(v242 + 16);
                      v310 = L"name";
                      v313 = v243;
                      v308 = 8;
                      v309 = 10;
                      v21 = v241(v26, 0, &v308, &v312);
                      if ( v21 < 0 )
                      {
                        v321 = v21;
                        if ( LogAdapter::g_Logger )
                        {
                          LogAdapter::Logger::LogNumObjects<>(
                            (__int64)LogAdapter::g_Logger,
                            0,
                            3,
                            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to emit update name.");
                          v307 = &v321;
                          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
                            (_DWORD)LogAdapter::g_Logger,
                            v271,
                            3,
                            (unsigned int)": {}",
                            (__int64)&v307);
                        }
                        v23 = 802;
                        goto LABEL_26;
                      }
                      v244 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v26 + 88LL);
                      v245 = CbsSelectionToString(*(unsigned int *)(v239 + 8));
                      v246 = StringToUnicodeString(v314, v245);
                      v312 = *(_OWORD *)v246;
                      v247 = *(_QWORD *)(v246 + 16);
                      v310 = L"select";
                      v313 = v247;
                      v308 = 12;
                      v309 = 14;
                      v21 = v244(v26, 0, &v308, &v312);
                      if ( v21 < 0 )
                      {
                        v321 = v21;
                        if ( LogAdapter::g_Logger )
                        {
                          LogAdapter::Logger::LogNumObjects<>(
                            (__int64)LogAdapter::g_Logger,
                            0,
                            3,
                            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to select.");
                          v307 = &v321;
                          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
                            (_DWORD)LogAdapter::g_Logger,
                            v270,
                            3,
                            (unsigned int)": {}",
                            (__int64)&v307);
                        }
                        v23 = 809;
                        goto LABEL_26;
                      }
                      v248 = *(_DWORD *)(v239 + 12);
                      if ( v248 )
                      {
                        v249 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v26 + 88LL);
                        v250 = numToString(v248);
                        v251 = StringToUnicodeString(v314, v250);
                        v312 = *(_OWORD *)v251;
                        v252 = *(_QWORD *)(v251 + 16);
                        v310 = L"options";
                        v313 = v252;
                        v308 = 14;
                        v309 = 16;
                        v253 = v249(v26, 0, &v308, &v312);
                        v21 = v253;
                        if ( v253 < 0 )
                        {
                          v321 = v253;
                          if ( LogAdapter::g_Logger )
                          {
                            LogAdapter::Logger::LogNumObjects<>(
                              (__int64)LogAdapter::g_Logger,
                              0,
                              3,
                              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to emit option.");
                            v307 = &v321;
                            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
                              (_DWORD)LogAdapter::g_Logger,
                              v254,
                              3,
                              (unsigned int)": {}",
                              (__int64)&v307);
                          }
                          v23 = 819;
                          goto LABEL_26;
                        }
                      }
                      v21 = (*(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, __int64))(*(_QWORD *)v26 + 48LL))(
                              v26,
                              1);
                      if ( v21 < 0 )
                      {
                        v321 = v21;
                        if ( LogAdapter::g_Logger )
                        {
                          LogAdapter::Logger::LogNumObjects<>(
                            (__int64)LogAdapter::g_Logger,
                            0,
                            3,
                            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to close update element.");
                          v307 = &v321;
                          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
                            (_DWORD)LogAdapter::g_Logger,
                            v269,
                            3,
                            (unsigned int)": {}",
                            (__int64)&v307);
                        }
                        v23 = 824;
                        goto LABEL_26;
                      }
                    }
                    v7 = 0;
                    v255 = v238 == 0;
                    v256 = *(_QWORD *)v26;
                    if ( !v255 )
                    {
                      v257 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *))(v256 + 56);
                      v310 = L"package";
                      v308 = 14;
                      v309 = 16;
                      v258 = v257(v26, 0, &v308);
                      v21 = v258;
                      if ( v258 < 0 )
                      {
                        v321 = v258;
                        if ( LogAdapter::g_Logger )
                        {
                          LogAdapter::Logger::LogNumObjects<>(
                            (__int64)LogAdapter::g_Logger,
                            0,
                            3,
                            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to close package element.");
                          v307 = &v321;
                          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
                            (_DWORD)LogAdapter::g_Logger,
                            v259,
                            3,
                            (unsigned int)": {}",
                            (__int64)&v307);
                        }
                        v23 = 830;
                        goto LABEL_26;
                      }
LABEL_235:
                      v213 = (wchar_t *)((char *)v311 + 1);
                      continue;
                    }
                    v21 = (*(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, __int64))(v256 + 48))(
                            v26,
                            1);
                    if ( v21 >= 0 )
                      goto LABEL_235;
                    v321 = v21;
                    if ( LogAdapter::g_Logger )
                    {
                      LogAdapter::Logger::LogNumObjects<>(
                        (__int64)LogAdapter::g_Logger,
                        0,
                        3,
                        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to end package element.");
                      v307 = &v321;
                      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
                        (_DWORD)LogAdapter::g_Logger,
                        v273,
                        3,
                        (unsigned int)": {}",
                        (__int64)&v307);
                    }
                    v23 = 835;
                  }
                }
              }
            }
          }
          goto LABEL_26;
        }
        break;
      }
      v260 = *(_QWORD *)v26;
      v310 = L"Phase";
      v308 = 10;
      v309 = 12;
      v103 = v26;
      v21 = (*(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *))(v260 + 56))(
              v26,
              0,
              &v308);
      if ( v21 < 0 )
      {
        v321 = v21;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to close Phase");
          v307 = &v321;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v279,
            3,
            (unsigned int)": {}",
            (__int64)&v307);
        }
        v23 = 839;
LABEL_26:
        v15 = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)v23,
                (unsigned int)"onecore\\base\\cbs\\core\\cbssessionpersistence.cpp",
                (const char *)(unsigned int)v21,
                v306);
        goto LABEL_13;
      }
    }
    v283 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *))(v182 + 56);
    v310 = L"Tasks";
    v284 = v283(v103, 0, &v308);
    v21 = v284;
    if ( v284 < 0 )
    {
      v321 = v284;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to close tasks.");
        v307 = &v321;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v285,
          3,
          (unsigned int)": {}",
          (__int64)&v307);
      }
      v23 = 842;
      goto LABEL_26;
    }
    v286 = *(_QWORD *)v103;
    v308 = 14;
    v309 = 16;
    v310 = L"Actions";
    v287 = (*(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *))(v286 + 16))(
             v103,
             0,
             &v308);
    v21 = v287;
    if ( v287 < 0 )
    {
      v321 = v287;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to open actions.");
        v307 = &v321;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v288,
          3,
          (unsigned int)": {}",
          (__int64)&v307);
      }
      v23 = 846;
      goto LABEL_26;
    }
    v289 = (*(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD))(*(_QWORD *)v103 + 48LL))(
             v103,
             0);
    v21 = v289;
    if ( v289 < 0 )
    {
      v321 = v289;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to end action.");
        v307 = &v321;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v290,
          3,
          (unsigned int)": {}",
          (__int64)&v307);
      }
      v23 = 848;
      goto LABEL_26;
    }
    v291 = v322[0];
    for ( k = 0; k < *((_QWORD *)this + 114) && k < *((unsigned int *)this + 254); ++k )
    {
      v293 = *(struct SessionPhase **)(*((_QWORD *)this + 116) + 8 * k);
      v15 = CCbsSession::PersistActionPhase(this, v26, v293, v291, 0);
      if ( (v15 & 0x80000000) != 0 )
      {
        v322[0] = v15;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to persist action phase");
          v307 = v322;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)&v307);
        }
        v18 = 855;
        goto LABEL_20;
      }
      v294 = (struct SessionPhase *)*((_QWORD *)v293 + 42);
      if ( v294 )
      {
        v15 = CCbsSession::PersistActionPhase(this, v26, v294, v291, 1);
        if ( (v15 & 0x80000000) != 0 )
        {
          v322[0] = v15;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to persist retry action phase");
            v307 = v322;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)&v307);
          }
          v18 = 860;
          goto LABEL_20;
        }
      }
    }
    if ( v291
      && (v295 = (struct SessionPhase *)*((_QWORD *)this + 139)) != 0
      && (v296 = CCbsSession::PersistActionPhase(this, v26, v295, v291, 0), v15 = v296, v296 < 0) )
    {
      v322[0] = v296;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to persist post transaction phase.");
        v307 = v322;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)&v307);
      }
      v18 = 868;
    }
    else
    {
      v297 = *(_QWORD *)v26;
      v309 = 16;
      v308 = 14;
      v310 = L"Actions";
      v298 = (*(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *))(v297 + 56))(
               v26,
               0,
               &v308);
      v21 = v298;
      if ( v298 < 0 )
      {
        v322[0] = v298;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to close Actions");
          v307 = v322;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v299,
            3,
            (unsigned int)": {}",
            (__int64)&v307);
        }
        v23 = 871;
        goto LABEL_26;
      }
      v300 = *(_QWORD *)v26;
      v310 = L"Session";
      v308 = 14;
      v309 = 16;
      v301 = (*(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *))(v300 + 56))(
               v26,
               0,
               &v308);
      v21 = v301;
      if ( v301 < 0 )
      {
        v322[0] = v301;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to close session.");
          v307 = v322;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v302,
            3,
            (unsigned int)": {}",
            (__int64)&v307);
        }
        v23 = 874;
        goto LABEL_26;
      }
      v303 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int64 *))(*(_QWORD *)v318 + 16LL))(v318, 0, v323);
      v21 = v303;
      if ( v303 < 0 )
      {
        v322[0] = v303;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get data out of builder.");
          v307 = v322;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v304,
            3,
            (unsigned int)": {}",
            (__int64)&v307);
        }
        v23 = 876;
        goto LABEL_26;
      }
      v305 = PackageStorePersistSession(this, v291, v324, v323[0]);
      v15 = v305;
      if ( v305 >= 0 )
        goto LABEL_12;
      v322[0] = v305;
      if ( LogAdapter::g_Logger )
      {
        v307 = (int *)*((_QWORD *)this + 80);
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (__int64)"Failed to store persist session: {}",
          (__int64)&v307);
        v320 = v322;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)&v320);
      }
      v18 = 879;
    }
LABEL_20:
    v19 = v15;
LABEL_21:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecore\\base\\cbs\\core\\cbssessionpersistence.cpp",
      (const char *)v19,
      v306);
    goto LABEL_13;
  }
  v321 = v12;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(
      (__int64)LogAdapter::g_Logger,
      0,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to persist session state.");
    v315 = (wchar_t *)&v321;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (__int64)LogAdapter::g_Logger,
      1,
      3,
      (__int64)": {}",
      (__int64)&v315);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x195,
    (unsigned int)"onecore\\base\\cbs\\core\\cbssessionpersistence.cpp",
    (const char *)v15,
    v306);
  if ( v324 )
    RtlFreeLBlob(v323);
  return v15;
}

```

## disassembly

```asm
0x18001a1c4  mov     [rsp-8+arg_10], rbx
0x18001a1c9  push    rbp
0x18001a1ca  push    rsi
0x18001a1cb  push    rdi
0x18001a1cc  push    r12
0x18001a1ce  push    r13
0x18001a1d0  push    r14
0x18001a1d2  push    r15
0x18001a1d4  lea     rbp, [rsp-80h]
0x18001a1d9  sub     rsp, 180h
0x18001a1e0  mov     rax, cs:__security_cookie
0x18001a1e7  xor     rax, rsp
0x18001a1ea  mov     [rbp+0B0h+var_40], rax
0x18001a1ee  mov     esi, r8d
0x18001a1f1  mov     [rbp+0B0h+var_F0], r9d
0x18001a1f5  mov     rbx, rdx
0x18001a1f8  mov     r14, rcx
0x18001a1fb  xor     r15d, r15d
0x18001a1fe  lea     rcx, [rbp+0B0h+var_D0]; void *
0x18001a202  xor     edx, edx; Val
0x18001a204  mov     [rbp+0B0h+var_128], r15
0x18001a208  mov     r8d, 81h; Size
0x18001a20e  mov     [rbp+0B0h+var_108], r15
0x18001a212  mov     r12d, r9d
0x18001a215  call    memset_0
0x18001a21a  xor     eax, eax
0x18001a21c  mov     [rbp+0B0h+var_110], r15
0x18001a220  mov     [rbp+0B0h+var_118], r15
0x18001a224  xorps   xmm0, xmm0
0x18001a227  mov     [rbp+0B0h+var_120], r15
0x18001a22b  mov     r9d, 0D0h
0x18001a231  mov     [rbp+0B0h+var_D8], rax
0x18001a235  movups  xmmword ptr [rbp+0B0h+var_E8], xmm0
0x18001a239  test    r12d, r12d
0x18001a23c  jnz     short loc_18001A245
0x18001a23e  mov     r9d, [r14+300h]
0x18001a245  mov     eax, [rbx+140h]
0x18001a24b  mov     rcx, r14
0x18001a24e  cmp     [rbx+148h], r15d
0x18001a255  lea     r8d, [rax+2710h]
0x18001a25c  cmovz   r8d, eax
0x18001a260  xor     edx, edx
0x18001a262  call    ?PackageStorePersistSessionState@@YAJPEAVCCbsSession@@PEB_WIW4_CbsSessionState@@@Z; PackageStorePersistSessionState(CCbsSession *,wchar_t const *,uint,_CbsSessionState)
0x18001a267  mov     edi, eax
0x18001a269  test    eax, eax
0x18001a26b  jns     short loc_18001A2E7
0x18001a26d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18001a274  mov     [rbp+0B0h+var_F8], eax
0x18001a277  test    rcx, rcx
0x18001a27a  jz      short loc_18001A2BB
0x18001a27c  mov     ebx, 3
0x18001a281  lea     r9, aFailedToPersis; "Failed to persist session state."
0x18001a288  mov     r8d, ebx
0x18001a28b  xor     edx, edx
0x18001a28d  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18001a292  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18001a299  lea     rax, [rbp+0B0h+var_F8]
0x18001a29d  mov     [rbp+0B0h+var_128], rax
0x18001a2a1  lea     r9, asc_1802EE7AC; ": {}"
0x18001a2a8  lea     rax, [rbp+0B0h+var_128]
0x18001a2ac  mov     r8d, ebx
0x18001a2af  mov     dl, 1
0x18001a2b1  mov     qword ptr [rsp+1B0h+var_190], rax; int
0x18001a2b6  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18001a2bb  mov     rcx, [rbp+0B8h]; this
0x18001a2c2  lea     r8, aOnecoreBaseCbs_114; "onecore\\base\\cbs\\core\\cbssessionper"...
0x18001a2c9  mov     r9d, edi; char *
0x18001a2cc  mov     edx, 195h; void *
0x18001a2d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a2d6  cmp     [rbp+0B0h+var_D8], r15
0x18001a2da  jz      short loc_18001A329
0x18001a2dc  lea     rcx, [rbp+0B0h+var_E8]
0x18001a2e0  call    RtlFreeLBlob
0x18001a2e5  jmp     short loc_18001A329
0x18001a2e7  test    esi, esi
0x18001a2e9  jz      short loc_18001A353
0x18001a2eb  test    r12d, r12d
0x18001a2ee  jnz     short loc_18001A35C
0x18001a2f0  mov     edi, r15d
0x18001a2f3  lea     rcx, [rbp+0B0h+var_E8]
0x18001a2f7  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x18001a2fc  lea     rcx, [rbp+0B0h+var_120]
0x18001a300  call    ??1?$Auto@PEAUIRtlIniFile@Rtl@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Rtl::IRtlIniFile *>::~Auto<Windows::Rtl::IRtlIniFile *>(void)
0x18001a305  lea     rcx, [rbp+0B0h+var_118]
0x18001a309  call    ??1?$Auto@PEAUIRtlIniFile@Rtl@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Rtl::IRtlIniFile *>::~Auto<Windows::Rtl::IRtlIniFile *>(void)
0x18001a30e  lea     rcx, [rbp+0B0h+var_110]
0x18001a312  call    ??1?$Auto@PEAUIRtlIniFile@Rtl@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Rtl::IRtlIniFile *>::~Auto<Windows::Rtl::IRtlIniFile *>(void)
0x18001a317  lea     rcx, [rbp+0B0h+var_108]
0x18001a31b  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18001a320  lea     rcx, [rbp+0B0h+var_128]
0x18001a324  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18001a329  mov     eax, edi
0x18001a32b  mov     rcx, [rbp+0B0h+var_40]
0x18001a32f  xor     rcx, rsp; StackCookie
0x18001a332  call    __security_check_cookie
0x18001a337  mov     rbx, [rsp+1B0h+arg_10]
0x18001a33f  add     rsp, 180h
0x18001a346  pop     r15
0x18001a348  pop     r14
0x18001a34a  pop     r13
0x18001a34c  pop     r12
0x18001a34e  pop     rdi
0x18001a34f  pop     rsi
0x18001a350  pop     rbp
0x18001a351  retn
0x18001a353  test    r12d, r12d
0x18001a356  jz      loc_18001A3F4
0x18001a35c  xor     edx, edx; wchar_t *
0x18001a35e  mov     rcx, r14; struct CCbsSession *
0x18001a361  call    ?PackageStoreMarkSessionComplete@@YAJPEAVCCbsSession@@PEB_W@Z; PackageStoreMarkSessionComplete(CCbsSession *,wchar_t const *)
0x18001a366  mov     edi, eax
0x18001a368  test    eax, eax
0x18001a36a  jns     loc_18001A3F4
0x18001a370  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18001a377  mov     [rbp+0B0h+var_F8], eax
0x18001a37a  test    rcx, rcx
0x18001a37d  jz      short loc_18001A3D4
0x18001a37f  mov     rdx, [r14+280h]
0x18001a386  lea     rax, [rsp+1B0h+var_160]
0x18001a38b  mov     [rsp+1B0h+var_160], rdx
0x18001a390  lea     r9, aFailedToMarkSe; "Failed to mark session complete on sess"...
0x18001a397  mov     ebx, 3
0x18001a39c  mov     qword ptr [rsp+1B0h+var_190], rax
0x18001a3a1  xor     edx, edx
0x18001a3a3  mov     r8d, ebx
0x18001a3a6  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18001a3ab  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18001a3b2  lea     rax, [rbp+0B0h+var_F8]
0x18001a3b6  mov     qword ptr [rbp+0B0h+var_F0], rax
0x18001a3ba  lea     r9, asc_1802EE7AC; ": {}"
0x18001a3c1  lea     rax, [rbp+0B0h+var_F0]
0x18001a3c5  mov     r8d, ebx
0x18001a3c8  mov     dl, 1
0x18001a3ca  mov     qword ptr [rsp+1B0h+var_190], rax; int
0x18001a3cf  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18001a3d4  mov     edx, 19Fh; void *
0x18001a3d9  mov     r9d, edi; char *
0x18001a3dc  mov     rcx, [rbp+0B8h]; this
0x18001a3e3  lea     r8, aOnecoreBaseCbs_114; "onecore\\base\\cbs\\core\\cbssessionper"...
0x18001a3ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a3ef  jmp     loc_18001A2F3
0x18001a3f4  lea     r9, [rbp+0B0h+var_118]
0x18001a3f8  lea     r8, [rbp+0B0h+var_110]
0x18001a3fc  call    RtlCreateUtf8UCSStringBuilder
0x18001a401  mov     edi, eax
0x18001a403  test    eax, eax
0x18001a405  jns     short loc_18001A477
0x18001a407  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18001a40e  mov     [rbp+0B0h+var_F8], eax
0x18001a411  test    rcx, rcx
0x18001a414  jz      short loc_18001A455
0x18001a416  mov     ebx, 3
0x18001a41b  lea     r9, aFailedToCreate_90; "Failed to create string builder."
0x18001a422  mov     r8d, ebx
0x18001a425  xor     edx, edx
0x18001a427  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18001a42c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18001a433  lea     rax, [rbp+0B0h+var_F8]
0x18001a437  mov     [rsp+1B0h+var_160], rax
0x18001a43c  lea     r9, asc_1802EE7AC; ": {}"
0x18001a443  lea     rax, [rsp+1B0h+var_160]
0x18001a448  mov     r8d, ebx
0x18001a44b  mov     qword ptr [rsp+1B0h+var_190], rax; int
0x18001a450  call    ??$LogNumObjects@U?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatNtStatusWrapper<long> const &)
0x18001a455  mov     edx, 1A4h; void *
0x18001a45a  mov     rcx, [rbp+0B8h]; this
0x18001a461  lea     r8, aOnecoreBaseCbs_114; "onecore\\base\\cbs\\core\\cbssessionper"...
0x18001a468  mov     r9d, edi; char *
0x18001a46b  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18001a470  mov     edi, eax
0x18001a472  jmp     loc_18001A2F3
0x18001a477  mov     rdx, [rbp+0B0h+var_118]
0x18001a47b  lea     r8, [rbp+0B0h+var_120]
0x18001a47f  mov     ecx, 0Ah
0x18001a484  call    RtlCreateDefaultXmlWriter
0x18001a489  mov     edi, eax
0x18001a48b  test    eax, eax
0x18001a48d  jns     short loc_18001A4E7
0x18001a48f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18001a496  mov     [rbp+0B0h+var_F8], eax
0x18001a499  test    rcx, rcx
0x18001a49c  jz      short loc_18001A4DD
0x18001a49e  mov     ebx, 3
0x18001a4a3  lea     r9, aFailedToCreate_6; "Failed to create XML writter."
0x18001a4aa  mov     r8d, ebx
0x18001a4ad  xor     edx, edx
0x18001a4af  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18001a4b4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18001a4bb  lea     rax, [rbp+0B0h+var_F8]
0x18001a4bf  mov     [rsp+1B0h+var_160], rax
0x18001a4c4  lea     r9, asc_1802EE7AC; ": {}"
0x18001a4cb  lea     rax, [rsp+1B0h+var_160]
0x18001a4d0  mov     r8d, ebx
0x18001a4d3  mov     qword ptr [rsp+1B0h+var_190], rax
0x18001a4d8  call    ??$LogNumObjects@U?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatNtStatusWrapper<long> const &)
0x18001a4dd  mov     edx, 1ABh
0x18001a4e2  jmp     loc_18001A45A
0x18001a4e7  mov     rbx, [rbp+0B0h+var_120]
0x18001a4eb  lea     rcx, aSession; "Session"
0x18001a4f2  mov     esi, 0Eh
0x18001a4f7  lea     r8, [rsp+1B0h+var_178]
0x18001a4fc  xor     edx, edx
0x18001a4fe  mov     rax, [rbx]
0x18001a501  mov     [rsp+1B0h+var_168], rcx
0x18001a506  lea     r13d, [rsi+2]
0x18001a50a  mov     rcx, rbx
0x18001a50d  mov     [rsp+1B0h+var_178], rsi
0x18001a512  mov     [rsp+1B0h+var_170], r13
0x18001a517  mov     rax, [rax+10h]
0x18001a51b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a520  mov     edi, eax
0x18001a522  test    eax, eax
0x18001a524  jns     short loc_18001A57C
0x18001a526  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18001a52d  mov     [rbp+0B0h+var_F8], eax
0x18001a530  test    rcx, rcx
0x18001a533  jz      short loc_18001A572
0x18001a535  lea     ebx, [rsi-0Bh]
0x18001a538  xor     edx, edx
0x18001a53a  mov     r8d, ebx
0x18001a53d  lea     r9, aFailedToOpenSe_1; "Failed to open session element."
0x18001a544  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18001a549  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18001a550  lea     rax, [rbp+0B0h+var_F8]
0x18001a554  mov     [rsp+1B0h+var_160], rax
0x18001a559  lea     r9, asc_1802EE7AC; ": {}"
0x18001a560  lea     rax, [rsp+1B0h+var_160]
0x18001a565  mov     r8d, ebx
0x18001a568  mov     qword ptr [rsp+1B0h+var_190], rax
0x18001a56d  call    ??$LogNumObjects@U?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatNtStatusWrapper<long> const &)
0x18001a572  mov     edx, 1D0h
0x18001a577  jmp     loc_18001A45A
0x18001a57c  mov     rax, [rbx]
0x18001a57f  lea     rdx, a80; "8.0"
0x18001a586  lea     rcx, [rsp+1B0h+var_140]
0x18001a58b  mov     rdi, [rax+58h]
0x18001a58f  call    ?StringToUnicodeString@@YA?AU_LUNICODE_STRING@@PEB_W@Z; StringToUnicodeString(wchar_t const *)
0x18001a594  lea     r9, [rsp+1B0h+var_158]
0x18001a599  xor     edx, edx
0x18001a59b  lea     r8, [rsp+1B0h+var_178]
0x18001a5a0  mov     rcx, rbx
0x18001a5a3  movups  xmm0, xmmword ptr [rax]
0x18001a5a6  movups  [rsp+1B0h+var_158], xmm0
0x18001a5ab  movsd   xmm1, qword ptr [rax+10h]
0x18001a5b0  lea     rax, aVersion; "version"
0x18001a5b7  mov     [rsp+1B0h+var_168], rax
0x18001a5bc  mov     rax, rdi
0x18001a5bf  movsd   [rsp+1B0h+var_148], xmm1
0x18001a5c5  mov     [rsp+1B0h+var_178], rsi
0x18001a5ca  mov     [rsp+1B0h+var_170], r13
0x18001a5cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a5d4  mov     edi, eax
0x18001a5d6  test    eax, eax
0x18001a5d8  jns     short loc_18001A632
0x18001a5da  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18001a5e1  mov     [rbp+0B0h+var_F8], eax
0x18001a5e4  test    rcx, rcx
0x18001a5e7  jz      short loc_18001A628
0x18001a5e9  mov     ebx, 3
0x18001a5ee  lea     r9, aFailedToEmitVe; "Failed to emit version."
0x18001a5f5  mov     r8d, ebx
0x18001a5f8  xor     edx, edx
0x18001a5fa  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18001a5ff  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18001a606  lea     rax, [rbp+0B0h+var_F8]
0x18001a60a  mov     [rsp+1B0h+var_160], rax
0x18001a60f  lea     r9, asc_1802EE7AC; ": {}"
0x18001a616  lea     rax, [rsp+1B0h+var_160]
0x18001a61b  mov     r8d, ebx
0x18001a61e  mov     qword ptr [rsp+1B0h+var_190], rax
0x18001a623  call    ??$LogNumObjects@U?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatNtStatusWrapper<long> const &)
0x18001a628  mov     edx, 1D4h
0x18001a62d  jmp     loc_18001A45A
0x18001a632  mov     rax, [rbx]
0x18001a635  lea     rcx, [rsp+1B0h+var_140]
0x18001a63a  mov     rdx, [r14+280h]
0x18001a641  mov     rdi, [rax+58h]
0x18001a645  call    ?StringToUnicodeString@@YA?AU_LUNICODE_STRING@@PEB_W@Z; StringToUnicodeString(wchar_t const *)
0x18001a64a  lea     r9, [rsp+1B0h+var_158]
0x18001a64f  xor     edx, edx
0x18001a651  lea     r8, [rsp+1B0h+var_178]
0x18001a656  mov     rcx, rbx
0x18001a659  movups  xmm0, xmmword ptr [rax]
0x18001a65c  movups  [rsp+1B0h+var_158], xmm0
0x18001a661  movsd   xmm1, qword ptr [rax+10h]
0x18001a666  lea     rax, aId_2; "id"
0x18001a66d  mov     [rsp+1B0h+var_168], rax
0x18001a672  mov     rax, rdi
0x18001a675  movsd   [rsp+1B0h+var_148], xmm1
0x18001a67b  mov     [rsp+1B0h+var_178], 4
0x18001a684  mov     [rsp+1B0h+var_170], 6
0x18001a68d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a692  mov     edi, eax
0x18001a694  test    eax, eax
0x18001a696  jns     short loc_18001A6F0
0x18001a698  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18001a69f  mov     [rbp+0B0h+var_F8], eax
0x18001a6a2  test    rcx, rcx
0x18001a6a5  jz      short loc_18001A6E6
0x18001a6a7  mov     ebx, 3
  ... truncated ...
```
