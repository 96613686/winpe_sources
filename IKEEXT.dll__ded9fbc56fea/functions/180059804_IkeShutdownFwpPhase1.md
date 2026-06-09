# IkeShutdownFwpPhase1

- ea: `0x180059804`
- end: `0x18005b280`
- name: `IkeShutdownFwpPhase1`
- size: `6780`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180058100`

## callees

- `0x180001008`
- `0x1800010c8`
- `0x1800488f0`
- `0x18004890c`
- `0x18004aa3c`
- `0x180050850`
- `0x180059804`
- `0x18005bc40`
- `0x18005bce4`

## import_xrefs

- `fwpuclnt!IPsecKeyModuleDelete0` at `0x180059928`
- `fwpuclnt!IPsecKeyModuleDelete0` at `0x180059ae4`
- `fwpuclnt!IPsecKeyModuleDelete0` at `0x180059ca0`
- `fwpuclnt!IPsecKeyModuleDelete0` at `0x180059928`
- `fwpuclnt!IPsecKeyModuleDelete0` at `0x180059ae4`
- `fwpuclnt!IPsecKeyModuleDelete0` at `0x180059ca0`
- `fwpuclnt!FwpmProviderContextUnsubscribeChanges0` at `0x18005a54c`
- `fwpuclnt!FwpmProviderContextUnsubscribeChanges0` at `0x18005a708`
- `fwpuclnt!FwpmProviderContextUnsubscribeChanges0` at `0x18005a8c4`
- `fwpuclnt!FwpmProviderContextUnsubscribeChanges0` at `0x18005aa80`
- `fwpuclnt!FwpmProviderContextUnsubscribeChanges0` at `0x18005ac3c`
- `fwpuclnt!FwpmProviderContextUnsubscribeChanges0` at `0x18005adf8`
- `fwpuclnt!FwpmProviderContextUnsubscribeChanges0` at `0x18005afb4`
- `fwpuclnt!FwpmProviderContextUnsubscribeChanges0` at `0x18005b170`
- `fwpuclnt!FwpmProviderContextUnsubscribeChanges0` at `0x18005a54c`
- `fwpuclnt!FwpmProviderContextUnsubscribeChanges0` at `0x18005a708`
- `fwpuclnt!FwpmProviderContextUnsubscribeChanges0` at `0x18005a8c4`
- `fwpuclnt!FwpmProviderContextUnsubscribeChanges0` at `0x18005aa80`
- `fwpuclnt!FwpmProviderContextUnsubscribeChanges0` at `0x18005ac3c`
- `fwpuclnt!FwpmProviderContextUnsubscribeChanges0` at `0x18005adf8`
- `fwpuclnt!FwpmProviderContextUnsubscribeChanges0` at `0x18005afb4`
- `fwpuclnt!FwpmProviderContextUnsubscribeChanges0` at `0x18005b170`
- `fwpuclnt!FwpmFilterUnsubscribeChanges0` at `0x180059e5c`
- `fwpuclnt!FwpmFilterUnsubscribeChanges0` at `0x18005a018`
- `fwpuclnt!FwpmFilterUnsubscribeChanges0` at `0x18005a1d4`
- `fwpuclnt!FwpmFilterUnsubscribeChanges0` at `0x18005a390`
- `fwpuclnt!FwpmFilterUnsubscribeChanges0` at `0x180059e5c`
- `fwpuclnt!FwpmFilterUnsubscribeChanges0` at `0x18005a018`
- `fwpuclnt!FwpmFilterUnsubscribeChanges0` at `0x18005a1d4`
- `fwpuclnt!FwpmFilterUnsubscribeChanges0` at `0x18005a390`

## pseudocode

```c
__int64 IkeShutdownFwpPhase1()
{
  __int64 v0; // rcx
  LPCRITICAL_SECTION v1; // rax
  __int64 v2; // rdi
  __int64 TlsPeerAddr; // rbx
  int TlsMmLuid; // eax
  __int64 v5; // rcx
  __int64 v6; // rax
  int v7; // r8d
  int v8; // r9d
  int v9; // esi
  __int64 v10; // rdi
  __int64 v11; // rbx
  int v12; // eax
  __int64 v13; // rcx
  __int64 v14; // rax
  int v15; // r8d
  int v16; // r9d
  __int64 v17; // rdi
  __int64 v18; // rbx
  int v19; // eax
  __int64 v20; // rcx
  __int64 v21; // rax
  int v22; // r8d
  int v23; // r9d
  int v24; // esi
  __int64 v25; // rdi
  __int64 v26; // rbx
  int v27; // eax
  __int64 v28; // rcx
  __int64 v29; // rax
  int v30; // r8d
  int v31; // r9d
  __int64 v32; // rdi
  __int64 v33; // rbx
  int v34; // eax
  __int64 v35; // rcx
  __int64 v36; // rax
  int v37; // r8d
  int v38; // r9d
  int v39; // esi
  __int64 v40; // rdi
  __int64 v41; // rbx
  int v42; // eax
  __int64 v43; // rcx
  __int64 v44; // rax
  int v45; // r8d
  int v46; // r9d
  __int64 v47; // rdi
  __int64 v48; // rbx
  int v49; // eax
  __int64 v50; // rcx
  __int64 v51; // rax
  int v52; // r8d
  int v53; // r9d
  DWORD v54; // esi
  __int64 v55; // rdi
  __int64 v56; // rbx
  int v57; // eax
  __int64 v58; // rcx
  __int64 v59; // rax
  int v60; // r8d
  int v61; // r9d
  __int64 v62; // rdi
  __int64 v63; // rbx
  int v64; // eax
  __int64 v65; // rcx
  __int64 v66; // rax
  int v67; // r8d
  int v68; // r9d
  DWORD v69; // esi
  __int64 v70; // rdi
  __int64 v71; // rbx
  int v72; // eax
  __int64 v73; // rcx
  __int64 v74; // rax
  int v75; // r8d
  int v76; // r9d
  __int64 v77; // rdi
  __int64 v78; // rbx
  int v79; // eax
  __int64 v80; // rcx
  __int64 v81; // rax
  int v82; // r8d
  int v83; // r9d
  DWORD v84; // esi
  __int64 v85; // rdi
  __int64 v86; // rbx
  int v87; // eax
  __int64 v88; // rcx
  __int64 v89; // rax
  int v90; // r8d
  int v91; // r9d
  __int64 v92; // rdi
  __int64 v93; // rbx
  int v94; // eax
  __int64 v95; // rcx
  __int64 v96; // rax
  int v97; // r8d
  int v98; // r9d
  DWORD v99; // esi
  __int64 v100; // rdi
  __int64 v101; // rbx
  int v102; // eax
  __int64 v103; // rcx
  __int64 v104; // rax
  int v105; // r8d
  int v106; // r9d
  __int64 v107; // rdi
  __int64 v108; // rbx
  int v109; // eax
  __int64 v110; // rcx
  __int64 v111; // rax
  int v112; // r8d
  int v113; // r9d
  DWORD v114; // esi
  __int64 v115; // rdi
  __int64 v116; // rbx
  int v117; // eax
  __int64 v118; // rcx
  __int64 v119; // rax
  int v120; // r8d
  int v121; // r9d
  __int64 v122; // rdi
  __int64 v123; // rbx
  int v124; // eax
  __int64 v125; // rcx
  __int64 v126; // rax
  int v127; // r8d
  int v128; // r9d
  DWORD v129; // esi
  __int64 v130; // rdi
  __int64 v131; // rbx
  int v132; // eax
  __int64 v133; // rcx
  __int64 v134; // rax
  int v135; // r8d
  int v136; // r9d
  __int64 v137; // rdi
  __int64 v138; // rbx
  int v139; // eax
  __int64 v140; // rcx
  __int64 v141; // rax
  int v142; // r8d
  int v143; // r9d
  DWORD v144; // esi
  __int64 v145; // rdi
  __int64 v146; // rbx
  int v147; // eax
  __int64 v148; // rcx
  __int64 v149; // rax
  int v150; // r8d
  int v151; // r9d
  __int64 v152; // rdi
  __int64 v153; // rbx
  int v154; // eax
  __int64 v155; // rcx
  __int64 v156; // rax
  int v157; // r8d
  int v158; // r9d
  DWORD v159; // esi
  __int64 v160; // rdi
  __int64 v161; // rbx
  int v162; // eax
  __int64 v163; // rcx
  __int64 v164; // rax
  int v165; // r8d
  int v166; // r9d
  __int64 v167; // rdi
  __int64 v168; // rbx
  int v169; // eax
  __int64 v170; // rcx
  __int64 v171; // rax
  int v172; // r8d
  int v173; // r9d
  DWORD v174; // esi
  __int64 v175; // rdi
  __int64 v176; // rbx
  int v177; // eax
  __int64 v178; // rcx
  __int64 v179; // rax
  int v180; // r8d
  int v181; // r9d
  __int64 v182; // rdi
  __int64 v183; // rbx
  int v184; // eax
  __int64 v185; // rcx
  __int64 v186; // rax
  int v187; // r8d
  int v188; // r9d
  DWORD v189; // esi
  __int64 v190; // rdi
  __int64 v191; // rbx
  int v192; // eax
  __int64 v193; // rcx
  __int64 v194; // rax
  int v195; // r8d
  int v196; // r9d
  __int64 v197; // rdi
  __int64 v198; // rbx
  int v199; // eax
  __int64 v200; // rcx
  __int64 v201; // rax
  int v202; // r8d
  int v203; // r9d
  DWORD v204; // esi
  __int64 v205; // rdi
  __int64 v206; // rbx
  int v207; // eax
  __int64 v208; // rcx
  __int64 v209; // rax
  int v210; // r8d
  int v211; // r9d
  __int64 v212; // rdi
  __int64 v213; // rbx
  int v214; // eax
  __int64 v215; // rcx
  __int64 v216; // rax
  int v217; // r8d
  int v218; // r9d
  __int64 v219; // rcx
  DWORD v220; // esi
  __int64 v221; // rdi
  __int64 v222; // rbx
  int v223; // eax
  __int64 v224; // rcx
  __int64 v225; // rax
  int v226; // r8d
  int v227; // r9d
  __int64 v229; // [rsp+28h] [rbp-71h]
  __int64 v230; // [rsp+30h] [rbp-69h] BYREF
  __int64 v231; // [rsp+38h] [rbp-61h] BYREF
  _BYTE v232[32]; // [rsp+40h] [rbp-59h] BYREF
  __int64 *v233; // [rsp+60h] [rbp-39h]
  __int64 v234; // [rsp+68h] [rbp-31h]
  _BYTE v235[16]; // [rsp+70h] [rbp-29h] BYREF
  const char *v236; // [rsp+80h] [rbp-19h]
  __int64 v237; // [rsp+88h] [rbp-11h]
  __int64 *v238; // [rsp+90h] [rbp-9h]
  __int64 v239; // [rsp+98h] [rbp-1h]

  TraceLogHelper("IkeShutdownFwpPhase1", 1);
  v1 = gIkeExtGlobals;
  if ( gIkeExtGlobals[68].LockSemaphore )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v2 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      TlsPeerAddr = IkeGetTlsPeerAddr(v0);
      TlsMmLuid = IkeGetTlsMmLuid();
      WPP_SF_iS(v2, 46, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, TlsMmLuid, TlsPeerAddr);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v231 = IkeGetTlsMmLuid();
      v233 = &v231;
      v234 = 8;
      v6 = IkeGetTlsPeerAddr(v5);
      tlgCreate1Sz_wchar_t(v235, v6);
      v237 = 32;
      v236 = "Deregistering IKE keying module";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (unsigned int)&dword_180173278,
        (unsigned int)&byte_18014ED4F,
        v7,
        v8,
        5,
        (__int64)v232);
    }
    v9 = IPsecKeyModuleDelete0(gIkeExtGlobals[68].OwningThread, gIkeExtGlobals[68].LockSemaphore);
    if ( v9 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v10 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v11 = IkeGetTlsPeerAddr(v0);
        v12 = IkeGetTlsMmLuid();
        LODWORD(v229) = v9;
        WPP_SF_iSL(v10, 47, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v12, v11, v229);
      }
      if ( (unsigned int)dword_180173278 > 4 )
      {
        v230 = IkeGetTlsMmLuid();
        v233 = &v230;
        v234 = 8;
        v14 = IkeGetTlsPeerAddr(v13);
        tlgCreate1Sz_wchar_t(v235, v14);
        v237 = 39;
        v238 = &v231;
        v236 = "Deregistering IKE keying module failed";
        LODWORD(v231) = v9;
        v239 = 4;
        tlgWriteTransfer_EtwEventWriteTransfer(
          (unsigned int)&dword_180173278,
          (unsigned int)word_18014ED02,
          v15,
          v16,
          6,
          (__int64)v232);
      }
    }
    gIkeExtGlobals[68].LockSemaphore = 0;
    v1 = gIkeExtGlobals;
  }
  if ( v1[68].SpinCount )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v17 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v18 = IkeGetTlsPeerAddr(v0);
      v19 = IkeGetTlsMmLuid();
      WPP_SF_iS(v17, 48, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v19, v18);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v230 = IkeGetTlsMmLuid();
      v233 = &v230;
      v234 = 8;
      v21 = IkeGetTlsPeerAddr(v20);
      tlgCreate1Sz_wchar_t(v235, v21);
      v237 = 36;
      v236 = "Deregistering Authip keying modulee";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (unsigned int)&dword_180173278,
        (unsigned int)&byte_18014ECBF,
        v22,
        v23,
        5,
        (__int64)v232);
    }
    v24 = IPsecKeyModuleDelete0(gIkeExtGlobals[68].OwningThread, gIkeExtGlobals[68].SpinCount);
    if ( v24 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v25 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v26 = IkeGetTlsPeerAddr(v0);
        v27 = IkeGetTlsMmLuid();
        LODWORD(v229) = v24;
        WPP_SF_iSL(v25, 49, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v27, v26, v229);
      }
      if ( (unsigned int)dword_180173278 > 4 )
      {
        v230 = IkeGetTlsMmLuid();
        v233 = &v230;
        v234 = 8;
        v29 = IkeGetTlsPeerAddr(v28);
        tlgCreate1Sz_wchar_t(v235, v29);
        v237 = 42;
        v238 = &v231;
        v236 = "Deregistering Authip keying module failed";
        LODWORD(v231) = v24;
        v239 = 4;
        tlgWriteTransfer_EtwEventWriteTransfer(
          (unsigned int)&dword_180173278,
          (unsigned int)word_18014EC72,
          v30,
          v31,
          6,
          (__int64)v232);
      }
    }
    gIkeExtGlobals[68].SpinCount = 0;
    v1 = gIkeExtGlobals;
  }
  if ( v1[69].DebugInfo )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v32 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v33 = IkeGetTlsPeerAddr(v0);
      v34 = IkeGetTlsMmLuid();
      WPP_SF_iS(v32, 50, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v34, v33);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v230 = IkeGetTlsMmLuid();
      v233 = &v230;
      v234 = 8;
      v36 = IkeGetTlsPeerAddr(v35);
      tlgCreate1Sz_wchar_t(v235, v36);
      v237 = 34;
      v236 = "Deregistering IKEv2 keying module";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (unsigned int)&dword_180173278,
        (unsigned int)&byte_18014EC2F,
        v37,
        v38,
        5,
        (__int64)v232);
    }
    v39 = IPsecKeyModuleDelete0(gIkeExtGlobals[68].OwningThread, gIkeExtGlobals[69].DebugInfo);
    if ( v39 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v40 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v41 = IkeGetTlsPeerAddr(v0);
        v42 = IkeGetTlsMmLuid();
        LODWORD(v229) = v39;
        WPP_SF_iSL(v40, 51, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v42, v41, v229);
      }
      if ( (unsigned int)dword_180173278 > 4 )
      {
        v230 = IkeGetTlsMmLuid();
        v233 = &v230;
        v234 = 8;
        v44 = IkeGetTlsPeerAddr(v43);
        tlgCreate1Sz_wchar_t(v235, v44);
        v237 = 41;
        v238 = &v231;
        v236 = "Deregistering IKEv2 keying module failed";
        LODWORD(v231) = v39;
        v239 = 4;
        tlgWriteTransfer_EtwEventWriteTransfer(
          (unsigned int)&dword_180173278,
          (unsigned int)word_18014EBE2,
          v45,
          v46,
          6,
          (__int64)v232);
      }
    }
    gIkeExtGlobals[69].DebugInfo = 0;
    v1 = gIkeExtGlobals;
  }
  if ( *(_QWORD *)&v1[69].LockCount )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v47 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v48 = IkeGetTlsPeerAddr(v0);
      v49 = IkeGetTlsMmLuid();
      WPP_SF_iS(v47, 52, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v49, v48);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v230 = IkeGetTlsMmLuid();
      v233 = &v230;
      v234 = 8;
      v51 = IkeGetTlsPeerAddr(v50);
      tlgCreate1Sz_wchar_t(v235, v51);
      v237 = 47;
      v236 = "Unsubscribing MM V4 filter change notification";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (unsigned int)&dword_180173278,
        (unsigned int)&byte_18014EB9F,
        v52,
        v53,
        5,
        (__int64)v232);
    }
    v54 = FwpmFilterUnsubscribeChanges0(gIkeExtGlobals[68].OwningThread, *(HANDLE *)&gIkeExtGlobals[69].LockCount);
    if ( v54 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v55 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v56 = IkeGetTlsPeerAddr(v0);
        v57 = IkeGetTlsMmLuid();
        LODWORD(v229) = v54;
        WPP_SF_iSL(v55, 53, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v57, v56, v229);
      }
      if ( (unsigned int)dword_180173278 > 4 )
      {
        v230 = IkeGetTlsMmLuid();
        v233 = &v230;
        v234 = 8;
        v59 = IkeGetTlsPeerAddr(v58);
        tlgCreate1Sz_wchar_t(v235, v59);
        v237 = 54;
        v238 = &v231;
        v236 = "Unsubscribing MM V4 filter change notification failed";
        LODWORD(v231) = v54;
        v239 = 4;
        tlgWriteTransfer_EtwEventWriteTransfer(
          (unsigned int)&dword_180173278,
          (unsigned int)word_18014EB52,
          v60,
          v61,
          6,
          (__int64)v232);
      }
    }
    *(_QWORD *)&gIkeExtGlobals[69].LockCount = 0;
    v1 = gIkeExtGlobals;
  }
  if ( v1[69].LockSemaphore )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v62 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v63 = IkeGetTlsPeerAddr(v0);
      v64 = IkeGetTlsMmLuid();
      WPP_SF_iS(v62, 54, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v64, v63);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v230 = IkeGetTlsMmLuid();
      v233 = &v230;
      v234 = 8;
      v66 = IkeGetTlsPeerAddr(v65);
      tlgCreate1Sz_wchar_t(v235, v66);
      v237 = 47;
      v236 = "Unsubscribing MM V6 filter change notification";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (unsigned int)&dword_180173278,
        (unsigned int)&byte_18014EB0F,
        v67,
        v68,
        5,
        (__int64)v232);
    }
    v69 = FwpmFilterUnsubscribeChanges0(gIkeExtGlobals[68].OwningThread, gIkeExtGlobals[69].LockSemaphore);
    if ( v69 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v70 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v71 = IkeGetTlsPeerAddr(v0);
        v72 = IkeGetTlsMmLuid();
        LODWORD(v229) = v69;
        WPP_SF_iSL(v70, 55, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v72, v71, v229);
      }
      if ( (unsigned int)dword_180173278 > 4 )
      {
        v230 = IkeGetTlsMmLuid();
        v233 = &v230;
        v234 = 8;
        v74 = IkeGetTlsPeerAddr(v73);
        tlgCreate1Sz_wchar_t(v235, v74);
        v237 = 54;
        v238 = &v231;
        v236 = "Unsubscribing MM V6 filter change notification failed";
        LODWORD(v231) = v69;
        v239 = 4;
        tlgWriteTransfer_EtwEventWriteTransfer(
          (unsigned int)&dword_180173278,
          (unsigned int)word_18014EAC2,
          v75,
          v76,
          6,
          (__int64)v232);
      }
    }
    gIkeExtGlobals[69].LockSemaphore = 0;
    v1 = gIkeExtGlobals;
  }
  if ( v1[69].OwningThread )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v77 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v78 = IkeGetTlsPeerAddr(v0);
      v79 = IkeGetTlsMmLuid();
      WPP_SF_iS(v77, 56, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v79, v78);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v230 = IkeGetTlsMmLuid();
      v233 = &v230;
      v234 = 8;
      v81 = IkeGetTlsPeerAddr(v80);
      tlgCreate1Sz_wchar_t(v235, v81);
      v237 = 47;
      v236 = "Unsubscribing QM V4 filter change notification";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (unsigned int)&dword_180173278,
        (unsigned int)&byte_18014EA7F,
        v82,
        v83,
        5,
        (__int64)v232);
    }
    v84 = FwpmFilterUnsubscribeChanges0(gIkeExtGlobals[68].OwningThread, gIkeExtGlobals[69].OwningThread);
    if ( v84 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v85 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v86 = IkeGetTlsPeerAddr(v0);
        v87 = IkeGetTlsMmLuid();
        LODWORD(v229) = v84;
        WPP_SF_iSL(v85, 57, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v87, v86, v229);
      }
      if ( (unsigned int)dword_180173278 > 4 )
      {
        v230 = IkeGetTlsMmLuid();
        v233 = &v230;
        v234 = 8;
        v89 = IkeGetTlsPeerAddr(v88);
        tlgCreate1Sz_wchar_t(v235, v89);
        v237 = 54;
        v238 = &v231;
        v236 = "Unsubscribing QM V4 filter change notification failed";
        LODWORD(v231) = v84;
        v239 = 4;
        tlgWriteTransfer_EtwEventWriteTransfer(
          (unsigned int)&dword_180173278,
          (unsigned int)word_18014EA32,
          v90,
          v91,
          6,
          (__int64)v232);
      }
    }
    gIkeExtGlobals[69].OwningThread = 0;
    v1 = gIkeExtGlobals;
  }
  if ( v1[69].SpinCount )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v92 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v93 = IkeGetTlsPeerAddr(v0);
      v94 = IkeGetTlsMmLuid();
      WPP_SF_iS(v92, 58, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v94, v93);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v230 = IkeGetTlsMmLuid();
      v233 = &v230;
      v234 = 8;
      v96 = IkeGetTlsPeerAddr(v95);
      tlgCreate1Sz_wchar_t(v235, v96);
      v237 = 47;
      v236 = "Unsubscribing QM V6 filter change notification";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (unsigned int)&dword_180173278,
        (unsigned int)&byte_18014E9EF,
        v97,
        v98,
        5,
        (__int64)v232);
    }
    v99 = FwpmFilterUnsubscribeChanges0(gIkeExtGlobals[68].OwningThread, (HANDLE)gIkeExtGlobals[69].SpinCount);
    if ( v99 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v100 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v101 = IkeGetTlsPeerAddr(v0);
        v102 = IkeGetTlsMmLuid();
        LODWORD(v229) = v99;
        WPP_SF_iSL(v100, 59, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v102, v101, v229);
      }
      if ( (unsigned int)dword_180173278 > 4 )
      {
        v230 = IkeGetTlsMmLuid();
        v233 = &v230;
        v234 = 8;
        v104 = IkeGetTlsPeerAddr(v103);
        tlgCreate1Sz_wchar_t(v235, v104);
        v237 = 54;
        v238 = &v231;
        v236 = "Unsubscribing QM V6 filter change notification failed";
        LODWORD(v231) = v99;
        v239 = 4;
        tlgWriteTransfer_EtwEventWriteTransfer(
          (unsigned int)&dword_180173278,
          (unsigned int)word_18014E9A2,
          v105,
          v106,
          6,
          (__int64)v232);
      }
    }
    gIkeExtGlobals[69].SpinCount = 0;
    v1 = gIkeExtGlobals;
  }
  if ( v1[70].DebugInfo )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v107 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v108 = IkeGetTlsPeerAddr(v0);
      v109 = IkeGetTlsMmLuid();
      WPP_SF_iS(v107, 60, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v109, v108);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v230 = IkeGetTlsMmLuid();
      v233 = &v230;
      v234 = 8;
      v111 = IkeGetTlsPeerAddr(v110);
      tlgCreate1Sz_wchar_t(v235, v111);
      v237 = 48;
      v236 = "Unsubscribing IKE MM policy change notification";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (unsigned int)&dword_180173278,
        (unsigned int)&byte_18014E95F,
        v112,
        v113,
        5,
        (__int64)v232);
    }
    v114 = FwpmProviderContextUnsubscribeChanges0(gIkeExtGlobals[68].OwningThread, gIkeExtGlobals[70].DebugInfo);
    if ( v114 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v115 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v116 = IkeGetTlsPeerAddr(v0);
        v117 = IkeGetTlsMmLuid();
        LODWORD(v229) = v114;
        WPP_SF_iSL(v115, 61, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v117, v116, v229);
      }
      if ( (unsigned int)dword_180173278 > 4 )
      {
        v230 = IkeGetTlsMmLuid();
        v233 = &v230;
        v234 = 8;
        v119 = IkeGetTlsPeerAddr(v118);
        tlgCreate1Sz_wchar_t(v235, v119);
        v237 = 55;
        v238 = &v231;
        v236 = "Unsubscribing IKE MM policy change notification failed";
        LODWORD(v231) = v114;
        v239 = 4;
        tlgWriteTransfer_EtwEventWriteTransfer(
          (unsigned int)&dword_180173278,
          (unsigned int)word_18014E912,
          v120,
          v121,
          6,
          (__int64)v232);
      }
    }
    gIkeExtGlobals[70].DebugInfo = 0;
    v1 = gIkeExtGlobals;
  }
  if ( v1[70].LockSemaphore )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v122 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v123 = IkeGetTlsPeerAddr(v0);
      v124 = IkeGetTlsMmLuid();
      WPP_SF_iS(v122, 62, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v124, v123);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v230 = IkeGetTlsMmLuid();
      v233 = &v230;
      v234 = 8;
      v126 = IkeGetTlsPeerAddr(v125);
      tlgCreate1Sz_wchar_t(v235, v126);
      v237 = 51;
      v236 = "Unsubscribing Authip MM policy change notification";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (unsigned int)&dword_180173278,
        (unsigned int)&byte_18014E8CF,
        v127,
        v128,
        5,
        (__int64)v232);
    }
    v129 = FwpmProviderContextUnsubscribeChanges0(gIkeExtGlobals[68].OwningThread, gIkeExtGlobals[70].LockSemaphore);
    if ( v129 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v130 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v131 = IkeGetTlsPeerAddr(v0);
        v132 = IkeGetTlsMmLuid();
        LODWORD(v229) = v129;
        WPP_SF_iSL(v130, 63, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v132, v131, v229);
      }
      if ( (unsigned int)dword_180173278 > 4 )
      {
        v230 = IkeGetTlsMmLuid();
        v233 = &v230;
        v234 = 8;
        v134 = IkeGetTlsPeerAddr(v133);
        tlgCreate1Sz_wchar_t(v235, v134);
        v237 = 58;
        v238 = &v231;
        v236 = "Unsubscribing Authip MM policy change notification failed";
        LODWORD(v231) = v129;
        v239 = 4;
        tlgWriteTransfer_EtwEventWriteTransfer(
          (unsigned int)&dword_180173278,
          (unsigned int)word_18014E882,
          v135,
          v136,
          6,
          (__int64)v232);
      }
    }
    gIkeExtGlobals[70].LockSemaphore = 0;
    v1 = gIkeExtGlobals;
  }
  if ( v1[70].SpinCount )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v137 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v138 = IkeGetTlsPeerAddr(v0);
      v139 = IkeGetTlsMmLuid();
      WPP_SF_iS(v137, 64, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v139, v138);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v230 = IkeGetTlsMmLuid();
      v233 = &v230;
      v234 = 8;
      v141 = IkeGetTlsPeerAddr(v140);
      tlgCreate1Sz_wchar_t(v235, v141);
      v237 = 50;
      v236 = "Unsubscribing IKEv2 MM policy change notification";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (unsigned int)&dword_180173278,
        (unsigned int)&byte_18014E83F,
        v142,
        v143,
        5,
        (__int64)v232);
    }
    v144 = FwpmProviderContextUnsubscribeChanges0(gIkeExtGlobals[68].OwningThread, (HANDLE)gIkeExtGlobals[70].SpinCount);
    if ( v144 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v145 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v146 = IkeGetTlsPeerAddr(v0);
        v147 = IkeGetTlsMmLuid();
        LODWORD(v229) = v144;
        WPP_SF_iSL(v145, 65, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v147, v146, v229);
      }
      if ( (unsigned int)dword_180173278 > 4 )
      {
        v230 = IkeGetTlsMmLuid();
        v233 = &v230;
        v234 = 8;
        v149 = IkeGetTlsPeerAddr(v148);
        tlgCreate1Sz_wchar_t(v235, v149);
        v237 = 57;
        v238 = &v231;
        v236 = "Unsubscribing IKEv2 MM policy change notification failed";
        LODWORD(v231) = v144;
        v239 = 4;
        tlgWriteTransfer_EtwEventWriteTransfer(
          (unsigned int)&dword_180173278,
          (unsigned int)word_18014E7F2,
          v150,
          v151,
          6,
          (__int64)v232);
      }
    }
    gIkeExtGlobals[70].SpinCount = 0;
    v1 = gIkeExtGlobals;
  }
  if ( *(_QWORD *)&v1[70].LockCount )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v152 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v153 = IkeGetTlsPeerAddr(v0);
      v154 = IkeGetTlsMmLuid();
      WPP_SF_iS(v152, 66, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v154, v153);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v230 = IkeGetTlsMmLuid();
      v233 = &v230;
      v234 = 8;
      v156 = IkeGetTlsPeerAddr(v155);
      tlgCreate1Sz_wchar_t(v235, v156);
      v237 = 54;
      v236 = "Unsubscribing IKE QM Trans policy change notification";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (unsigned int)&dword_180173278,
        (unsigned int)&byte_18014E7AF,
        v157,
        v158,
        5,
        (__int64)v232);
    }
    v159 = FwpmProviderContextUnsubscribeChanges0(
             gIkeExtGlobals[68].OwningThread,
             *(HANDLE *)&gIkeExtGlobals[70].LockCount);
    if ( v159 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v160 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v161 = IkeGetTlsPeerAddr(v0);
        v162 = IkeGetTlsMmLuid();
        LODWORD(v229) = v159;
        WPP_SF_iSL(v160, 67, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v162, v161, v229);
      }
      if ( (unsigned int)dword_180173278 > 4 )
      {
        v230 = IkeGetTlsMmLuid();
        v233 = &v230;
        v234 = 8;
        v164 = IkeGetTlsPeerAddr(v163);
        tlgCreate1Sz_wchar_t(v235, v164);
        v237 = 61;
        v238 = &v231;
        v236 = "Unsubscribing IKE QM Trans policy change notification failed";
        LODWORD(v231) = v159;
        v239 = 4;
        tlgWriteTransfer_EtwEventWriteTransfer(
          (unsigned int)&dword_180173278,
          (unsigned int)word_18014E762,
          v165,
          v166,
          6,
          (__int64)v232);
      }
    }
    *(_QWORD *)&gIkeExtGlobals[70].LockCount = 0;
    v1 = gIkeExtGlobals;
  }
  if ( v1[70].OwningThread )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v167 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v168 = IkeGetTlsPeerAddr(v0);
      v169 = IkeGetTlsMmLuid();
      WPP_SF_iS(v167, 68, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v169, v168);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v230 = IkeGetTlsMmLuid();
      v233 = &v230;
      v234 = 8;
      v171 = IkeGetTlsPeerAddr(v170);
      tlgCreate1Sz_wchar_t(v235, v171);
      v237 = 55;
      v236 = "Unsubscribing IKE QM Tunnel policy change notification";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (unsigned int)&dword_180173278,
        (unsigned int)&byte_18014E71F,
        v172,
        v173,
        5,
        (__int64)v232);
    }
    v174 = FwpmProviderContextUnsubscribeChanges0(gIkeExtGlobals[68].OwningThread, gIkeExtGlobals[70].OwningThread);
    if ( v174 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v175 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v176 = IkeGetTlsPeerAddr(v0);
        v177 = IkeGetTlsMmLuid();
        LODWORD(v229) = v174;
        WPP_SF_iSL(v175, 69, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v177, v176, v229);
      }
      if ( (unsigned int)dword_180173278 > 4 )
      {
        v230 = IkeGetTlsMmLuid();
        v233 = &v230;
        v234 = 8;
        v179 = IkeGetTlsPeerAddr(v178);
        tlgCreate1Sz_wchar_t(v235, v179);
        v237 = 62;
        v238 = &v231;
        v236 = "Unsubscribing IKE QM Tunnel policy change notification failed";
        LODWORD(v231) = v174;
        v239 = 4;
        tlgWriteTransfer_EtwEventWriteTransfer(
          (unsigned int)&dword_180173278,
          (unsigned int)word_18014E6D2,
          v180,
          v181,
          6,
          (__int64)v232);
      }
    }
    gIkeExtGlobals[70].OwningThread = 0;
    v1 = gIkeExtGlobals;
  }
  if ( v1[71].DebugInfo )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v182 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v183 = IkeGetTlsPeerAddr(v0);
      v184 = IkeGetTlsMmLuid();
      WPP_SF_iS(v182, 70, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v184, v183);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v230 = IkeGetTlsMmLuid();
      v233 = &v230;
      v234 = 8;
      v186 = IkeGetTlsPeerAddr(v185);
      tlgCreate1Sz_wchar_t(v235, v186);
      v237 = 57;
      v236 = "Unsubscribing Authip QM Trans policy change notification";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (unsigned int)&dword_180173278,
        (unsigned int)&byte_18014E68F,
        v187,
        v188,
        5,
        (__int64)v232);
    }
    v189 = FwpmProviderContextUnsubscribeChanges0(gIkeExtGlobals[68].OwningThread, gIkeExtGlobals[71].DebugInfo);
    if ( v189 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v190 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v191 = IkeGetTlsPeerAddr(v0);
        v192 = IkeGetTlsMmLuid();
        LODWORD(v229) = v189;
        WPP_SF_iSL(v190, 71, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v192, v191, v229);
      }
      if ( (unsigned int)dword_180173278 > 4 )
      {
        v230 = IkeGetTlsMmLuid();
        v233 = &v230;
        v234 = 8;
        v194 = IkeGetTlsPeerAddr(v193);
        tlgCreate1Sz_wchar_t(v235, v194);
        v237 = 64;
        v238 = &v231;
        v236 = "Unsubscribing Authip QM Trans policy change notification failed";
        LODWORD(v231) = v189;
        v239 = 4;
        tlgWriteTransfer_EtwEventWriteTransfer(
          (unsigned int)&dword_180173278,
          (unsigned int)word_18014E642,
          v195,
          v196,
          6,
          (__int64)v232);
      }
    }
    gIkeExtGlobals[71].DebugInfo = 0;
    v1 = gIkeExtGlobals;
  }
  if ( *(_QWORD *)&v1[71].LockCount )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v197 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v198 = IkeGetTlsPeerAddr(v0);
      v199 = IkeGetTlsMmLuid();
      WPP_SF_iS(v197, 72, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v199, v198);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v230 = IkeGetTlsMmLuid();
      v233 = &v230;
      v234 = 8;
      v201 = IkeGetTlsPeerAddr(v200);
      tlgCreate1Sz_wchar_t(v235, v201);
      v237 = 58;
      v236 = "Unsubscribing Authip QM Tunnel policy change notification";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (unsigned int)&dword_180173278,
        (unsigned int)&byte_18014E5FF,
        v202,
        v203,
        5,
        (__int64)v232);
    }
    v204 = FwpmProviderContextUnsubscribeChanges0(
             gIkeExtGlobals[68].OwningThread,
             *(HANDLE *)&gIkeExtGlobals[71].LockCount);
    if ( v204 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v205 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v206 = IkeGetTlsPeerAddr(v0);
        v207 = IkeGetTlsMmLuid();
        LODWORD(v229) = v204;
        WPP_SF_iSL(v205, 73, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v207, v206, v229);
      }
      if ( (unsigned int)dword_180173278 > 4 )
      {
        v230 = IkeGetTlsMmLuid();
        v233 = &v230;
        v234 = 8;
        v209 = IkeGetTlsPeerAddr(v208);
        tlgCreate1Sz_wchar_t(v235, v209);
        v237 = 65;
        v238 = &v231;
        v236 = "Unsubscribing Authip QM Tunnel policy change notification failed";
        LODWORD(v231) = v204;
        v239 = 4;
        tlgWriteTransfer_EtwEventWriteTransfer(
          (unsigned int)&dword_180173278,
          (unsigned int)word_18014E5B2,
          v210,
          v211,
          6,
          (__int64)v232);
      }
    }
    *(_QWORD *)&gIkeExtGlobals[71].LockCount = 0;
    v1 = gIkeExtGlobals;
  }
  if ( v1[71].OwningThread )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v212 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v213 = IkeGetTlsPeerAddr(v0);
      v214 = IkeGetTlsMmLuid();
      WPP_SF_iS(v212, 74, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v214, v213);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v230 = IkeGetTlsMmLuid();
      v233 = &v230;
      v234 = 8;
      v216 = IkeGetTlsPeerAddr(v215);
      tlgCreate1Sz_wchar_t(v235, v216);
      v237 = 57;
      v236 = "Unsubscribing IKEv2 QM Tunnel policy change notification";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (unsigned int)&dword_180173278,
        (unsigned int)&byte_18014E56F,
        v217,
        v218,
        5,
        (__int64)v232);
    }
    v220 = FwpmProviderContextUnsubscribeChanges0(gIkeExtGlobals[68].OwningThread, gIkeExtGlobals[71].OwningThread);
    if ( v220 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v221 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v222 = IkeGetTlsPeerAddr(v219);
        v223 = IkeGetTlsMmLuid();
        LODWORD(v229) = v220;
        WPP_SF_iSL(v221, 75, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v223, v222, v229);
      }
      if ( (unsigned int)dword_180173278 > 4 )
      {
        v230 = IkeGetTlsMmLuid();
        v233 = &v230;
        v234 = 8;
        v225 = IkeGetTlsPeerAddr(v224);
        tlgCreate1Sz_wchar_t(v235, v225);
        v237 = 64;
        v238 = &v231;
        v236 = "Unsubscribing IKEv2 QM Tunnel policy change notification failed";
        LODWORD(v231) = v220;
        v239 = 4;
        tlgWriteTransfer_EtwEventWriteTransfer(
          (unsigned int)&dword_180173278,
          (unsigned int)word_18014E522,
          v226,
          v227,
          6,
          (__int64)v232);
      }
    }
    gIkeExtGlobals[71].OwningThread = 0;
  }
  return TraceLogHelper("IkeShutdownFwpPhase1", 0);
}

```

## disassembly

```asm
0x180059804  push    rbp
0x180059806  push    rbx
0x180059807  push    rsi
0x180059808  push    rdi
0x180059809  push    r12
0x18005980b  push    r13
0x18005980d  push    r14
0x18005980f  push    r15
0x180059811  lea     rbp, [rsp-1Fh]
0x180059816  sub     rsp, 0B8h
0x18005981d  mov     rax, cs:__security_cookie
0x180059824  xor     rax, rsp
0x180059827  mov     [rbp+57h+var_50], rax
0x18005982b  mov     edx, 1
0x180059830  lea     rcx, aIkeshutdownfwp_0; "IkeShutdownFwpPhase1"
0x180059837  call    TraceLogHelper
0x18005983c  mov     rax, cs:gIkeExtGlobals
0x180059843  lea     r12, WPP_GLOBAL_Control
0x18005984a  xor     r14d, r14d
0x18005984d  mov     r15d, 4
0x180059853  mov     r13b, 10h
0x180059856  cmp     [rax+0AB8h], r14
0x18005985d  jz      loc_180059A11
0x180059863  mov     rdi, cs:WPP_GLOBAL_Control
0x18005986a  cmp     rdi, r12
0x18005986d  jz      short loc_1800598A7
0x18005986f  cmp     [rdi+19h], r15b
0x180059873  jb      short loc_1800598A7
0x180059875  test    [rdi+1Ch], r13b
0x180059879  jz      short loc_1800598A7
0x18005987b  mov     rdi, [rdi+10h]
0x18005987f  call    IkeGetTlsPeerAddr
0x180059884  mov     rbx, rax
0x180059887  call    IkeGetTlsMmLuid
0x18005988c  mov     r9, rax
0x18005988f  mov     [rsp+0F0h+var_D0], rbx
0x180059894  lea     edx, [r15+2Ah]
0x180059898  mov     rcx, rdi
0x18005989b  lea     r8, WPP_c3da8f174801358a223b58501d21a257_Traceguids
0x1800598a2  call    WPP_SF_iS
0x1800598a7  mov     eax, cs:dword_180173278
0x1800598ad  cmp     eax, r15d
0x1800598b0  jbe     short loc_180059913
0x1800598b2  call    IkeGetTlsMmLuid
0x1800598b7  mov     [rbp+57h+var_B8], rax
0x1800598bb  lea     rax, [rbp+57h+var_B8]
0x1800598bf  mov     [rbp+57h+var_90], rax
0x1800598c3  mov     [rbp+57h+var_88], 8
0x1800598cb  call    IkeGetTlsPeerAddr
0x1800598d0  mov     rdx, rax
0x1800598d3  lea     rcx, [rbp+57h+var_80]
0x1800598d7  call    _tlgCreate1Sz_wchar_t
0x1800598dc  lea     rcx, aDeregisteringI_0; "Deregistering IKE keying module"
0x1800598e3  mov     [rbp+57h+var_68], 20h ; ' '
0x1800598eb  lea     rax, [rbp+57h+var_B0]
0x1800598ef  mov     [rbp+57h+var_70], rcx
0x1800598f3  mov     [rsp+0F0h+var_C8], rax
0x1800598f8  lea     rcx, dword_180173278
0x1800598ff  lea     rdx, byte_18014ED4F
0x180059906  mov     dword ptr [rsp+0F0h+var_D0], 5
0x18005990e  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180059913  mov     rcx, cs:gIkeExtGlobals
0x18005991a  mov     rdx, [rcx+0AB8h]
0x180059921  mov     rcx, [rcx+0AB0h]
0x180059928  call    cs:__imp_IPsecKeyModuleDelete0
0x18005992e  mov     esi, eax
0x180059930  test    eax, eax
0x180059932  jz      loc_1800599FC
0x180059938  mov     rdi, cs:WPP_GLOBAL_Control
0x18005993f  cmp     rdi, r12
0x180059942  jz      short loc_180059981
0x180059944  cmp     [rdi+19h], r15b
0x180059948  jb      short loc_180059981
0x18005994a  test    [rdi+1Ch], r13b
0x18005994e  jz      short loc_180059981
0x180059950  mov     rdi, [rdi+10h]
0x180059954  call    IkeGetTlsPeerAddr
0x180059959  mov     rbx, rax
0x18005995c  call    IkeGetTlsMmLuid
0x180059961  mov     r9, rax
0x180059964  mov     dword ptr [rsp+0F0h+var_C8], esi
0x180059968  mov     edx, 2Fh ; '/'
0x18005996d  mov     [rsp+0F0h+var_D0], rbx
0x180059972  lea     r8, WPP_c3da8f174801358a223b58501d21a257_Traceguids
0x180059979  mov     rcx, rdi
0x18005997c  call    WPP_SF_iSL
0x180059981  mov     eax, cs:dword_180173278
0x180059987  cmp     eax, r15d
0x18005998a  jbe     short loc_1800599FC
0x18005998c  call    IkeGetTlsMmLuid
0x180059991  mov     [rbp+57h+var_C0], rax
0x180059995  lea     rax, [rbp+57h+var_C0]
0x180059999  mov     [rbp+57h+var_90], rax
0x18005999d  mov     [rbp+57h+var_88], 8
0x1800599a5  call    IkeGetTlsPeerAddr
0x1800599aa  mov     rdx, rax
0x1800599ad  lea     rcx, [rbp+57h+var_80]
0x1800599b1  call    _tlgCreate1Sz_wchar_t
0x1800599b6  lea     rax, [rbp+57h+var_B8]
0x1800599ba  mov     [rbp+57h+var_68], 27h ; '''
0x1800599c2  mov     [rbp+57h+var_60], rax
0x1800599c6  lea     rcx, aDeregisteringI_2; "Deregistering IKE keying module failed"
0x1800599cd  lea     rax, [rbp+57h+var_B0]
0x1800599d1  mov     [rbp+57h+var_70], rcx
0x1800599d5  mov     [rsp+0F0h+var_C8], rax
0x1800599da  lea     rdx, word_18014ED02
0x1800599e1  lea     rcx, dword_180173278
0x1800599e8  mov     dword ptr [rsp+0F0h+var_D0], 6
0x1800599f0  mov     dword ptr [rbp+57h+var_B8], esi
0x1800599f3  mov     [rbp+57h+var_58], r15
0x1800599f7  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x1800599fc  mov     rax, cs:gIkeExtGlobals
0x180059a03  mov     [rax+0AB8h], r14
0x180059a0a  mov     rax, cs:gIkeExtGlobals
0x180059a11  cmp     [rax+0AC0h], r14
0x180059a18  jz      loc_180059BCD
0x180059a1e  mov     rdi, cs:WPP_GLOBAL_Control
0x180059a25  cmp     rdi, r12
0x180059a28  jz      short loc_180059A63
0x180059a2a  cmp     [rdi+19h], r15b
0x180059a2e  jb      short loc_180059A63
0x180059a30  test    [rdi+1Ch], r13b
0x180059a34  jz      short loc_180059A63
0x180059a36  mov     rdi, [rdi+10h]
0x180059a3a  call    IkeGetTlsPeerAddr
0x180059a3f  mov     rbx, rax
0x180059a42  call    IkeGetTlsMmLuid
0x180059a47  mov     r9, rax
0x180059a4a  mov     [rsp+0F0h+var_D0], rbx
0x180059a4f  mov     edx, 30h ; '0'
0x180059a54  lea     r8, WPP_c3da8f174801358a223b58501d21a257_Traceguids
0x180059a5b  mov     rcx, rdi
0x180059a5e  call    WPP_SF_iS
0x180059a63  mov     eax, cs:dword_180173278
0x180059a69  cmp     eax, r15d
0x180059a6c  jbe     short loc_180059ACF
0x180059a6e  call    IkeGetTlsMmLuid
0x180059a73  mov     [rbp+57h+var_C0], rax
0x180059a77  lea     rax, [rbp+57h+var_C0]
0x180059a7b  mov     [rbp+57h+var_90], rax
0x180059a7f  mov     [rbp+57h+var_88], 8
0x180059a87  call    IkeGetTlsPeerAddr
0x180059a8c  mov     rdx, rax
0x180059a8f  lea     rcx, [rbp+57h+var_80]
0x180059a93  call    _tlgCreate1Sz_wchar_t
0x180059a98  lea     rcx, aDeregisteringA; "Deregistering Authip keying modulee"
0x180059a9f  mov     [rbp+57h+var_68], 24h ; '$'
0x180059aa7  lea     rax, [rbp+57h+var_B0]
0x180059aab  mov     [rbp+57h+var_70], rcx
0x180059aaf  mov     [rsp+0F0h+var_C8], rax
0x180059ab4  lea     rcx, dword_180173278
0x180059abb  lea     rdx, byte_18014ECBF
0x180059ac2  mov     dword ptr [rsp+0F0h+var_D0], 5
0x180059aca  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180059acf  mov     rcx, cs:gIkeExtGlobals
0x180059ad6  mov     rdx, [rcx+0AC0h]
0x180059add  mov     rcx, [rcx+0AB0h]
0x180059ae4  call    cs:__imp_IPsecKeyModuleDelete0
0x180059aea  mov     esi, eax
0x180059aec  test    eax, eax
0x180059aee  jz      loc_180059BB8
0x180059af4  mov     rdi, cs:WPP_GLOBAL_Control
0x180059afb  cmp     rdi, r12
0x180059afe  jz      short loc_180059B3D
0x180059b00  cmp     [rdi+19h], r15b
0x180059b04  jb      short loc_180059B3D
0x180059b06  test    [rdi+1Ch], r13b
0x180059b0a  jz      short loc_180059B3D
0x180059b0c  mov     rdi, [rdi+10h]
0x180059b10  call    IkeGetTlsPeerAddr
0x180059b15  mov     rbx, rax
0x180059b18  call    IkeGetTlsMmLuid
0x180059b1d  mov     r9, rax
0x180059b20  mov     dword ptr [rsp+0F0h+var_C8], esi
0x180059b24  mov     edx, 31h ; '1'
0x180059b29  mov     [rsp+0F0h+var_D0], rbx
0x180059b2e  lea     r8, WPP_c3da8f174801358a223b58501d21a257_Traceguids
0x180059b35  mov     rcx, rdi
0x180059b38  call    WPP_SF_iSL
0x180059b3d  mov     eax, cs:dword_180173278
0x180059b43  cmp     eax, r15d
0x180059b46  jbe     short loc_180059BB8
0x180059b48  call    IkeGetTlsMmLuid
0x180059b4d  mov     [rbp+57h+var_C0], rax
0x180059b51  lea     rax, [rbp+57h+var_C0]
0x180059b55  mov     [rbp+57h+var_90], rax
0x180059b59  mov     [rbp+57h+var_88], 8
0x180059b61  call    IkeGetTlsPeerAddr
0x180059b66  mov     rdx, rax
0x180059b69  lea     rcx, [rbp+57h+var_80]
0x180059b6d  call    _tlgCreate1Sz_wchar_t
0x180059b72  lea     rax, [rbp+57h+var_B8]
0x180059b76  mov     [rbp+57h+var_68], 2Ah ; '*'
0x180059b7e  mov     [rbp+57h+var_60], rax
0x180059b82  lea     rcx, aDeregisteringA_0; "Deregistering Authip keying module fail"...
0x180059b89  lea     rax, [rbp+57h+var_B0]
0x180059b8d  mov     [rbp+57h+var_70], rcx
0x180059b91  mov     [rsp+0F0h+var_C8], rax
0x180059b96  lea     rdx, word_18014EC72
0x180059b9d  lea     rcx, dword_180173278
0x180059ba4  mov     dword ptr [rsp+0F0h+var_D0], 6
0x180059bac  mov     dword ptr [rbp+57h+var_B8], esi
0x180059baf  mov     [rbp+57h+var_58], r15
0x180059bb3  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180059bb8  mov     rax, cs:gIkeExtGlobals
0x180059bbf  mov     [rax+0AC0h], r14
0x180059bc6  mov     rax, cs:gIkeExtGlobals
0x180059bcd  cmp     [rax+0AC8h], r14
0x180059bd4  jz      loc_180059D89
0x180059bda  mov     rdi, cs:WPP_GLOBAL_Control
0x180059be1  cmp     rdi, r12
0x180059be4  jz      short loc_180059C1F
0x180059be6  cmp     [rdi+19h], r15b
0x180059bea  jb      short loc_180059C1F
0x180059bec  test    [rdi+1Ch], r13b
0x180059bf0  jz      short loc_180059C1F
0x180059bf2  mov     rdi, [rdi+10h]
0x180059bf6  call    IkeGetTlsPeerAddr
0x180059bfb  mov     rbx, rax
0x180059bfe  call    IkeGetTlsMmLuid
0x180059c03  mov     r9, rax
0x180059c06  mov     [rsp+0F0h+var_D0], rbx
0x180059c0b  mov     edx, 32h ; '2'
0x180059c10  lea     r8, WPP_c3da8f174801358a223b58501d21a257_Traceguids
0x180059c17  mov     rcx, rdi
0x180059c1a  call    WPP_SF_iS
0x180059c1f  mov     eax, cs:dword_180173278
0x180059c25  cmp     eax, r15d
0x180059c28  jbe     short loc_180059C8B
0x180059c2a  call    IkeGetTlsMmLuid
0x180059c2f  mov     [rbp+57h+var_C0], rax
0x180059c33  lea     rax, [rbp+57h+var_C0]
0x180059c37  mov     [rbp+57h+var_90], rax
0x180059c3b  mov     [rbp+57h+var_88], 8
0x180059c43  call    IkeGetTlsPeerAddr
0x180059c48  mov     rdx, rax
0x180059c4b  lea     rcx, [rbp+57h+var_80]
0x180059c4f  call    _tlgCreate1Sz_wchar_t
0x180059c54  lea     rcx, aDeregisteringI_1; "Deregistering IKEv2 keying module"
0x180059c5b  mov     [rbp+57h+var_68], 22h ; '"'
0x180059c63  lea     rax, [rbp+57h+var_B0]
0x180059c67  mov     [rbp+57h+var_70], rcx
0x180059c6b  mov     [rsp+0F0h+var_C8], rax
0x180059c70  lea     rcx, dword_180173278
0x180059c77  lea     rdx, byte_18014EC2F
0x180059c7e  mov     dword ptr [rsp+0F0h+var_D0], 5
0x180059c86  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180059c8b  mov     rcx, cs:gIkeExtGlobals
0x180059c92  mov     rdx, [rcx+0AC8h]
0x180059c99  mov     rcx, [rcx+0AB0h]
0x180059ca0  call    cs:__imp_IPsecKeyModuleDelete0
0x180059ca6  mov     esi, eax
0x180059ca8  test    eax, eax
0x180059caa  jz      loc_180059D74
0x180059cb0  mov     rdi, cs:WPP_GLOBAL_Control
0x180059cb7  cmp     rdi, r12
0x180059cba  jz      short loc_180059CF9
0x180059cbc  cmp     [rdi+19h], r15b
0x180059cc0  jb      short loc_180059CF9
0x180059cc2  test    [rdi+1Ch], r13b
0x180059cc6  jz      short loc_180059CF9
0x180059cc8  mov     rdi, [rdi+10h]
0x180059ccc  call    IkeGetTlsPeerAddr
0x180059cd1  mov     rbx, rax
0x180059cd4  call    IkeGetTlsMmLuid
0x180059cd9  mov     r9, rax
0x180059cdc  mov     dword ptr [rsp+0F0h+var_C8], esi
0x180059ce0  mov     edx, 33h ; '3'
0x180059ce5  mov     [rsp+0F0h+var_D0], rbx
0x180059cea  lea     r8, WPP_c3da8f174801358a223b58501d21a257_Traceguids
0x180059cf1  mov     rcx, rdi
0x180059cf4  call    WPP_SF_iSL
0x180059cf9  mov     eax, cs:dword_180173278
0x180059cff  cmp     eax, r15d
0x180059d02  jbe     short loc_180059D74
0x180059d04  call    IkeGetTlsMmLuid
0x180059d09  mov     [rbp+57h+var_C0], rax
0x180059d0d  lea     rax, [rbp+57h+var_C0]
0x180059d11  mov     [rbp+57h+var_90], rax
0x180059d15  mov     [rbp+57h+var_88], 8
0x180059d1d  call    IkeGetTlsPeerAddr
0x180059d22  mov     rdx, rax
0x180059d25  lea     rcx, [rbp+57h+var_80]
0x180059d29  call    _tlgCreate1Sz_wchar_t
0x180059d2e  lea     rax, [rbp+57h+var_B8]
0x180059d32  mov     [rbp+57h+var_68], 29h ; ')'
0x180059d3a  mov     [rbp+57h+var_60], rax
0x180059d3e  lea     rcx, aDeregisteringI; "Deregistering IKEv2 keying module faile"...
0x180059d45  lea     rax, [rbp+57h+var_B0]
0x180059d49  mov     [rbp+57h+var_70], rcx
0x180059d4d  mov     [rsp+0F0h+var_C8], rax
0x180059d52  lea     rdx, word_18014EBE2
0x180059d59  lea     rcx, dword_180173278
0x180059d60  mov     dword ptr [rsp+0F0h+var_D0], 6
0x180059d68  mov     dword ptr [rbp+57h+var_B8], esi
0x180059d6b  mov     [rbp+57h+var_58], r15
0x180059d6f  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180059d74  mov     rax, cs:gIkeExtGlobals
0x180059d7b  mov     [rax+0AC8h], r14
0x180059d82  mov     rax, cs:gIkeExtGlobals
  ... truncated ...
```
