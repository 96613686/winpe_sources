# HandleTGSRequest(sockaddr *,KERB_KDC_REQUEST *,_UNICODE_STRING *,_KERB_MESSAGE_BUFFER *,_KERB_MESSAGE_BUFFER *,KERB_EXT_ERROR *,_UNICODE_STRING *,_UNICODE_STRING *,KrbFastReq *,_KDC_AP_REQUEST_INFO *,_KERB_ENCRYPTION_KEY *,KERB_KDC_REQUEST_preauth_data_s * *,_PDC_RSO *)

- ea: `0x180021eb4`
- end: `0x180024ff3`
- name: `?HandleTGSRequest@@YAJPEAUsockaddr@@PEAUKERB_KDC_REQUEST@@PEAU_UNICODE_STRING@@PEAU_KERB_MESSAGE_BUFFER@@3PEAUKERB_EXT_ERROR@@22PEAUKrbFastReq@@PEAU_KDC_AP_REQUEST_INFO@@PEAU_KERB_ENCRYPTION_KEY@@PEAPEAUKERB_KDC_REQUEST_preauth_data_s@@PEAU_PDC_RSO@@@Z`
- size: `12607`
- prototype: `__int64 __fastcall(struct sockaddr *, struct KERB_KDC_REQUEST *, struct _UNICODE_STRING *, struct _KERB_MESSAGE_BUFFER *, void **, struct KERB_EXT_ERROR *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, struct KrbFastReq *, struct _KDC_AP_REQUEST_INFO *, struct _KERB_ENCRYPTION_KEY *, struct KERB_KDC_REQUEST_preauth_data_s **, struct _PDC_RSO *)`
- caller_count: `1`
- callee_count: `95`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001e930`

## callees

- `0x180002ad0`
- `0x180003908`
- `0x180005cc0`
- `0x18000ab40`
- `0x18000add0`
- `0x18000c3d4`
- `0x18000d42c`
- `0x18000e9a4`
- `0x1800101c4`
- `0x1800101ec`
- `0x18001022c`
- `0x180010f88`
- `0x180011a04`
- `0x18001371c`
- `0x1800138c4`
- `0x180013c1c`
- `0x180015acc`
- `0x18001c848`
- `0x18001c944`
- `0x18001cdc4`
- `0x18001e84c`
- `0x18001e888`
- `0x18001fc94`
- `0x18001ff94`
- `0x180020380`
- `0x180021eb4`
- `0x180024ffc`
- `0x180026d04`
- `0x1800271fc`
- `0x180027220`
- `0x1800280ac`
- `0x1800286c0`
- `0x180029844`
- `0x18002b348`
- `0x18002e6c4`
- `0x1800304d8`
- `0x1800305d0`
- `0x1800309bc`
- `0x18005a060`
- `0x18005a090`
- `0x18005a3a4`
- `0x18005bfc0`
- `0x18005c2a4`
- `0x18005c334`
- `0x18005f034`
- `0x1800604c4`
- `0x180060598`
- `0x1800605ec`
- `0x180060624`
- `0x1800606f8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800222da`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800222da`
- `ntdll!EtwGetTraceEnableFlags` at `0x1800223a1`
- `ntdll!EtwGetTraceEnableFlags` at `0x1800223a1`
- `ntdll!RtlAcquireResourceShared` at `0x180022de9`
- `ntdll!RtlAcquireResourceShared` at `0x180022de9`
- `ntdll!RtlReleaseResource` at `0x180022dfd`
- `ntdll!RtlReleaseResource` at `0x180022dfd`
- `ntdll!EtwLogTraceEvent` at `0x1800223ea`
- `ntdll!EtwLogTraceEvent` at `0x180024a0c`
- `ntdll!EtwLogTraceEvent` at `0x1800223ea`
- `ntdll!EtwLogTraceEvent` at `0x180024a0c`
- `ntdll!NtQuerySystemTime` at `0x180022db5`
- `ntdll!NtQuerySystemTime` at `0x180022db5`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x180024bc2`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x180024bc2`
- `SAMSRV!SamIUpdateLogonStatistics` at `0x1800246f2`
- `SAMSRV!SamIUpdateLogonStatistics` at `0x1800246f2`
- `SAMSRV!SamrCloseHandle` at `0x180024dcb`
- `SAMSRV!SamrCloseHandle` at `0x180024de1`
- `SAMSRV!SamrCloseHandle` at `0x180024dcb`
- `SAMSRV!SamrCloseHandle` at `0x180024de1`
- `LSASRV!LsaIModifyPerformanceCounter` at `0x18002256f`
- `LSASRV!LsaIModifyPerformanceCounter` at `0x18002471c`
- `LSASRV!LsaIModifyPerformanceCounter` at `0x180024731`
- `LSASRV!LsaIModifyPerformanceCounter` at `0x18002256f`
- `LSASRV!LsaIModifyPerformanceCounter` at `0x18002471c`
- `LSASRV!LsaIModifyPerformanceCounter` at `0x180024731`
- `LSASRV!LsaIAuditKdcEvent` at `0x1800242be`
- `LSASRV!LsaIAuditKdcEvent` at `0x180024548`
- `LSASRV!LsaIAuditKdcEvent` at `0x180024f70`
- `LSASRV!LsaIAuditKdcEvent` at `0x1800242be`
- `LSASRV!LsaIAuditKdcEvent` at `0x180024548`
- `LSASRV!LsaIAuditKdcEvent` at `0x180024f70`
- `LSASRV!LsaIGetLogonGuid` at `0x180023f6e`
- `LSASRV!LsaIGetLogonGuid` at `0x180023f6e`

## pseudocode

```c
__int64 __fastcall HandleTGSRequest(
        struct sockaddr *a1,
        struct KERB_KDC_REQUEST *a2,
        struct _UNICODE_STRING *a3,
        struct _KERB_MESSAGE_BUFFER *a4,
        void **a5,
        struct KERB_EXT_ERROR *a6,
        struct _UNICODE_STRING *a7,
        struct _UNICODE_STRING *a8,
        struct KrbFastReq *a9,
        struct _KDC_AP_REQUEST_INFO *a10,
        struct _KERB_ENCRYPTION_KEY *a11,
        struct KERB_KDC_REQUEST_preauth_data_s **a12,
        struct _PDC_RSO *a13)
{
  struct _KERB_INTERNAL_NAME *v15; // r15
  KerberosCryptoPolicy *v16; // rdi
  struct KERB_KDC_REQUEST *v17; // rax
  struct KERB_KDC_REQUEST_preauth_data_s *v18; // rsi
  struct KERB_KDC_REQUEST_BODY *v19; // rdx
  char v20; // al
  BOOL v21; // eax
  struct KERB_KDC_REQUEST_preauth_data_s *v22; // r15
  struct KERB_PA_DATA *PreAuthDataEntry; // rax
  CSecurityData *v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // r9
  unsigned __int8 v27; // r12
  int v28; // eax
  __int64 v29; // rax
  struct KERB_EXT_ERROR *v30; // rax
  CSecurityData *v31; // rcx
  char v32; // bl
  struct _KERB_MESSAGE_BUFFER *v33; // rdi
  int v34; // eax
  CSecurityData *v35; // rcx
  __int64 v36; // rdx
  __int64 v37; // r9
  struct KERB_EXT_ERROR *v38; // rdi
  struct KERB_KDC_REQUEST_BODY *v39; // rbx
  struct KdcAuditEngine *v40; // rdi
  struct KERB_ENCRYPTED_TICKET *v41; // rax
  struct KERB_KDC_REQUEST_BODY *v42; // r15
  struct _KERB_INTERNAL_NAME *v43; // r13
  struct _KERB_ENCRYPTION_KEY *Key; // rax
  int v45; // eax
  char v46; // bl
  CSecurityData *v47; // rcx
  __int64 v48; // rdx
  __int64 v49; // r9
  LONGLONG v50; // rbx
  int v51; // eax
  CSecurityData *v52; // rcx
  CSecurityData *v53; // rcx
  __int64 v54; // rdx
  struct _KERB_INTERNAL_NAME *v55; // r9
  __int64 v56; // rax
  __int64 v57; // r8
  __int64 v58; // rax
  __int64 v59; // rax
  int v60; // r8d
  int v61; // r9d
  int v62; // ebx
  unsigned int v63; // eax
  CSecurityData *v64; // rcx
  __int64 v65; // rdx
  int v66; // eax
  struct KERB_KDC_REQUEST_preauth_data_s *v67; // rax
  struct KERB_KDC_REQUEST_preauth_data_s *v68; // rbx
  _DWORD *v69; // rcx
  struct KERB_KDC_REQUEST_preauth_data_s *v70; // r9
  unsigned int v71; // eax
  unsigned int v72; // eax
  __int64 v73; // rax
  __int16 v74; // cx
  int v75; // eax
  __int64 v76; // rax
  __int64 v77; // rbx
  _OWORD *v78; // rax
  CSecurityData *v79; // rcx
  __int128 v80; // xmm0
  struct KerberosCryptoPolicy *v81; // rdx
  unsigned __int8 v82; // bl
  KerberosCryptoPolicy *v83; // rax
  unsigned int v84; // r8d
  int v85; // eax
  unsigned int v86; // ebx
  struct _KERB_ENCRYPTION_KEY *v87; // rax
  int v88; // eax
  void *v89; // rbx
  unsigned int v90; // edi
  struct _LSA_ADT_STRING_LIST *v91; // rax
  struct _LSA_ADT_STRING_LIST *v92; // rbx
  struct _LSA_ADT_STRING_LIST *v93; // r8
  unsigned int i; // r9d
  CSecurityData *v95; // rcx
  struct KERB_KDC_REQUEST_BODY *v96; // rdi
  struct sockaddr *v97; // rdx
  struct KdcAuditEngine *v98; // rbx
  struct sockaddr *v99; // rax
  unsigned int Target; // eax
  unsigned int v101; // r10d
  unsigned int PacOptionsPaDataList; // eax
  struct _UNICODE_STRING *v103; // r15
  USHORT Length; // cx
  struct _UNICODE_STRING *v105; // rax
  struct _UNICODE_STRING *v106; // r12
  USHORT v107; // cx
  struct _UNICODE_STRING *v108; // rax
  USHORT v109; // cx
  struct _UNICODE_STRING *v110; // rax
  int v111; // edx
  struct sockaddr *v112; // r13
  unsigned int v113; // r9d
  _QWORD *v114; // rcx
  CSecurityData *v115; // r10
  unsigned int j; // ebx
  unsigned int v117; // ebx
  struct sockaddr *v119; // rax
  struct _UNICODE_STRING *v120; // rdx
  unsigned __int8 v121; // [rsp+E0h] [rbp-80h]
  int ClientNetbiosAddress; // [rsp+E4h] [rbp-7Ch] BYREF
  struct KERB_EXT_ERROR *v123; // [rsp+E8h] [rbp-78h]
  char v124[8]; // [rsp+F0h] [rbp-70h] BYREF
  struct KERB_KDC_REQUEST_preauth_data_s *v125; // [rsp+F8h] [rbp-68h] BYREF
  unsigned int v126; // [rsp+100h] [rbp-60h] BYREF
  struct KERB_KDC_REQUEST_BODY *v127; // [rsp+108h] [rbp-58h]
  unsigned __int8 v128; // [rsp+110h] [rbp-50h] BYREF
  char v129; // [rsp+111h] [rbp-4Fh] BYREF
  unsigned __int8 v130; // [rsp+112h] [rbp-4Eh] BYREF
  _BYTE v131[13]; // [rsp+113h] [rbp-4Dh] BYREF
  __int16 v132; // [rsp+120h] [rbp-40h] BYREF
  struct KERB_ENCRYPTED_TICKET *v133; // [rsp+128h] [rbp-38h] BYREF
  unsigned int v134; // [rsp+130h] [rbp-30h] BYREF
  unsigned int v135; // [rsp+134h] [rbp-2Ch] BYREF
  int v136; // [rsp+138h] [rbp-28h] BYREF
  struct KERB_KDC_REQUEST_preauth_data_s *v137; // [rsp+140h] [rbp-20h] BYREF
  struct sockaddr *v138; // [rsp+148h] [rbp-18h]
  struct KERB_KDC_REQUEST_preauth_data_s *v139; // [rsp+150h] [rbp-10h] BYREF
  void *v140; // [rsp+158h] [rbp-8h] BYREF
  struct KerberosCryptoPolicy *v141[2]; // [rsp+160h] [rbp+0h] BYREF
  struct _UNICODE_STRING v142; // [rsp+170h] [rbp+10h] BYREF
  unsigned int v143; // [rsp+180h] [rbp+20h]
  struct _UNICODE_STRING *v144; // [rsp+188h] [rbp+28h]
  KerberosCryptoPolicy *v145; // [rsp+190h] [rbp+30h] BYREF
  struct _UNICODE_STRING v146; // [rsp+198h] [rbp+38h] BYREF
  union _LARGE_INTEGER Time; // [rsp+1A8h] [rbp+48h] BYREF
  struct _UNICODE_STRING *v148; // [rsp+1B0h] [rbp+50h]
  struct KERB_AP_REQUEST *v149; // [rsp+1B8h] [rbp+58h] BYREF
  struct _UNICODE_STRING v150; // [rsp+1C0h] [rbp+60h] BYREF
  unsigned int v151; // [rsp+1D0h] [rbp+70h] BYREF
  struct _KERB_INTERNAL_NAME *v152; // [rsp+1D8h] [rbp+78h] BYREF
  struct KERB_AUTHENTICATOR *v153; // [rsp+1E0h] [rbp+80h] BYREF
  struct KrbFastReq *v154[2]; // [rsp+1E8h] [rbp+88h] BYREF
  __int128 v155; // [rsp+1F8h] [rbp+98h] BYREF
  __int128 v156; // [rsp+208h] [rbp+A8h]
  __int64 v157; // [rsp+218h] [rbp+B8h]
  struct _LSA_ADT_STRING_LIST *v158; // [rsp+220h] [rbp+C0h]
  struct _USER_INTERNAL6_INFORMATION *v159; // [rsp+228h] [rbp+C8h] BYREF
  struct _PDC_RSO *v160; // [rsp+230h] [rbp+D0h] BYREF
  struct _PDC_RSO *v161; // [rsp+238h] [rbp+D8h]
  _QWORD *v162; // [rsp+240h] [rbp+E0h]
  char v163; // [rsp+248h] [rbp+E8h]
  __int64 v164; // [rsp+250h] [rbp+F0h] BYREF
  int v165; // [rsp+258h] [rbp+F8h] BYREF
  int v166; // [rsp+25Ch] [rbp+FCh] BYREF
  struct _UNICODE_STRING v167; // [rsp+260h] [rbp+100h] BYREF
  union _LARGE_INTEGER SystemTime; // [rsp+270h] [rbp+110h] BYREF
  struct _KERB_ENCRYPTION_KEY *v169; // [rsp+278h] [rbp+118h]
  unsigned __int8 *v170; // [rsp+280h] [rbp+120h] BYREF
  struct _KERB_INTERNAL_NAME *v171; // [rsp+288h] [rbp+128h] BYREF
  __int64 v172[2]; // [rsp+290h] [rbp+130h] BYREF
  __int64 v173; // [rsp+2A0h] [rbp+140h] BYREF
  struct sockaddr *TlsValue; // [rsp+2A8h] [rbp+148h] BYREF
  char v175; // [rsp+2B0h] [rbp+150h]
  struct _UNICODE_STRING v176; // [rsp+2B8h] [rbp+158h] BYREF
  struct _UNICODE_STRING v177; // [rsp+2D0h] [rbp+170h] BYREF
  _BYTE v178[32]; // [rsp+2E0h] [rbp+180h] BYREF
  unsigned int v179; // [rsp+300h] [rbp+1A0h]
  int v180; // [rsp+30Ch] [rbp+1ACh]
  int v181; // [rsp+321h] [rbp+1C1h]
  __int16 v182; // [rsp+325h] [rbp+1C5h]
  char v183; // [rsp+327h] [rbp+1C7h]
  unsigned int v184; // [rsp+330h] [rbp+1D0h] BYREF
  char v185; // [rsp+338h] [rbp+1D8h]
  __int16 v186; // [rsp+339h] [rbp+1D9h]
  char v187; // [rsp+33Bh] [rbp+1DBh]
  int v188; // [rsp+33Ch] [rbp+1DCh]
  int v189; // [rsp+340h] [rbp+1E0h]
  int v190; // [rsp+344h] [rbp+1E4h]
  __int64 v191; // [rsp+368h] [rbp+208h] BYREF
  __int128 v192; // [rsp+370h] [rbp+210h]
  __int128 v193; // [rsp+380h] [rbp+220h] BYREF
  __int128 v194; // [rsp+390h] [rbp+230h] BYREF
  __int128 v195; // [rsp+3A0h] [rbp+240h]
  __int64 v196; // [rsp+3B0h] [rbp+250h]
  __int64 v197; // [rsp+3C0h] [rbp+260h]
  int v198; // [rsp+3D0h] [rbp+270h] BYREF
  int v199; // [rsp+3D4h] [rbp+274h] BYREF
  _BYTE v200[16]; // [rsp+3D8h] [rbp+278h] BYREF
  _BYTE v201[24]; // [rsp+3E8h] [rbp+288h] BYREF
  int v202; // [rsp+400h] [rbp+2A0h]
  struct KERB_KDC_REQUEST_preauth_data_s **v203; // [rsp+408h] [rbp+2A8h]
  void *v204; // [rsp+420h] [rbp+2C0h]
  __int128 v205; // [rsp+430h] [rbp+2D0h] BYREF
  __int128 v206; // [rsp+440h] [rbp+2E0h] BYREF
  __int128 v207; // [rsp+450h] [rbp+2F0h] BYREF
  __int64 v208; // [rsp+460h] [rbp+300h]
  _WORD v209[2]; // [rsp+470h] [rbp+310h] BYREF
  int v210; // [rsp+474h] [rbp+314h]
  int v211; // [rsp+478h] [rbp+318h]
  void *v212; // [rsp+480h] [rbp+320h]
  __int64 v213; // [rsp+488h] [rbp+328h]
  __int128 v214; // [rsp+490h] [rbp+330h]
  _BYTE v215[36]; // [rsp+4A0h] [rbp+340h] BYREF
  unsigned int v216; // [rsp+4C4h] [rbp+364h]
  unsigned int v217; // [rsp+4D0h] [rbp+370h]
  unsigned __int8 *v218; // [rsp+4D8h] [rbp+378h]
  _BYTE v219[4]; // [rsp+4E8h] [rbp+388h] BYREF
  int v220; // [rsp+4ECh] [rbp+38Ch]
  __int16 v221; // [rsp+510h] [rbp+3B0h] BYREF
  _BYTE v222[2]; // [rsp+512h] [rbp+3B2h] BYREF
  char v223; // [rsp+514h] [rbp+3B4h]
  __int128 v224; // [rsp+528h] [rbp+3C8h]
  int v225; // [rsp+53Ch] [rbp+3DCh]
  int *p_ClientNetbiosAddress; // [rsp+540h] [rbp+3E0h]
  int v227; // [rsp+548h] [rbp+3E8h]
  struct _UNICODE_STRING *v228; // [rsp+550h] [rbp+3F0h]
  int v229; // [rsp+558h] [rbp+3F8h]
  PWSTR Buffer; // [rsp+560h] [rbp+400h]
  int v231; // [rsp+568h] [rbp+408h]
  struct _UNICODE_STRING *v232; // [rsp+570h] [rbp+410h]
  int v233; // [rsp+578h] [rbp+418h]
  PWSTR v234; // [rsp+580h] [rbp+420h]
  int v235; // [rsp+588h] [rbp+428h]
  struct _UNICODE_STRING *v236; // [rsp+590h] [rbp+430h]
  int v237; // [rsp+598h] [rbp+438h]
  PWSTR v238; // [rsp+5A0h] [rbp+440h]
  int v239; // [rsp+5A8h] [rbp+448h]
  _OWORD v240[2]; // [rsp+5B0h] [rbp+450h] BYREF
  __int64 v241; // [rsp+5D0h] [rbp+470h]
  _OWORD v242[2]; // [rsp+5D8h] [rbp+478h] BYREF
  __int64 v243; // [rsp+5F8h] [rbp+498h]
  _OWORD v244[2]; // [rsp+600h] [rbp+4A0h] BYREF
  __int64 v245; // [rsp+620h] [rbp+4C0h]
  struct _KERB_INTERNAL_NAME *v246[2]; // [rsp+630h] [rbp+4D0h] BYREF
  __int64 v247; // [rsp+640h] [rbp+4E0h]
  _BYTE v248[48]; // [rsp+648h] [rbp+4E8h] BYREF
  int v249; // [rsp+678h] [rbp+518h]
  int v250; // [rsp+684h] [rbp+524h]
  int v251; // [rsp+699h] [rbp+539h]
  __int16 v252; // [rsp+69Dh] [rbp+53Dh]
  char v253; // [rsp+69Fh] [rbp+53Fh]
  __int16 v254; // [rsp+6B1h] [rbp+551h]
  char v255; // [rsp+6B3h] [rbp+553h]
  int v256; // [rsp+6BCh] [rbp+55Ch]
  __int128 v257; // [rsp+6E0h] [rbp+580h] BYREF
  __int64 v258; // [rsp+6F0h] [rbp+590h]
  _BYTE v259[8]; // [rsp+6F8h] [rbp+598h] BYREF
  _BYTE v260[16]; // [rsp+700h] [rbp+5A0h] BYREF
  struct _KERB_INTERNAL_NAME *v261; // [rsp+710h] [rbp+5B0h]
  _BYTE v262[64]; // [rsp+718h] [rbp+5B8h] BYREF
  int v263; // [rsp+758h] [rbp+5F8h]
  int v264; // [rsp+75Ch] [rbp+5FCh]
  __int64 v265; // [rsp+760h] [rbp+600h]
  int v266; // [rsp+77Ch] [rbp+61Ch]
  __int64 v267[2]; // [rsp+790h] [rbp+630h] BYREF
  _BYTE v268[40]; // [rsp+7A0h] [rbp+640h] BYREF
  _BYTE *v269; // [rsp+7C8h] [rbp+668h]
  struct _KERB_INTERNAL_NAME *v270[2]; // [rsp+7E0h] [rbp+680h] BYREF
  __int128 v271; // [rsp+7F0h] [rbp+690h]
  _BYTE v272[48]; // [rsp+800h] [rbp+6A0h] BYREF
  int v273; // [rsp+830h] [rbp+6D0h]
  int v274; // [rsp+83Ch] [rbp+6DCh]
  int v275; // [rsp+851h] [rbp+6F1h]
  __int16 v276; // [rsp+855h] [rbp+6F5h]
  char v277; // [rsp+857h] [rbp+6F7h]
  __int16 v278; // [rsp+869h] [rbp+709h]
  char v279; // [rsp+86Bh] [rbp+70Bh]
  int v280; // [rsp+874h] [rbp+714h]
  __int64 v281; // [rsp+898h] [rbp+738h] BYREF
  __int128 v282; // [rsp+8A0h] [rbp+740h]
  __int64 v283; // [rsp+8B0h] [rbp+750h]
  _OWORD v284[2]; // [rsp+8C0h] [rbp+760h] BYREF
  __int64 v285; // [rsp+8E0h] [rbp+780h]
  _OWORD v286[2]; // [rsp+8E8h] [rbp+788h] BYREF
  __int64 v287; // [rsp+908h] [rbp+7A8h]
  int v288[4]; // [rsp+910h] [rbp+7B0h] BYREF
  __int128 v289; // [rsp+920h] [rbp+7C0h]
  __int128 v290; // [rsp+930h] [rbp+7D0h]
  __int128 v291; // [rsp+940h] [rbp+7E0h]
  __int64 v292; // [rsp+950h] [rbp+7F0h]
  _BYTE v293[16]; // [rsp+960h] [rbp+800h] BYREF
  _BYTE v294[16]; // [rsp+970h] [rbp+810h] BYREF
  _BYTE v295[16]; // [rsp+980h] [rbp+820h] BYREF
  _BYTE v296[32]; // [rsp+990h] [rbp+830h] BYREF
  _BYTE v297[48]; // [rsp+9B0h] [rbp+850h] BYREF
  __int64 v298; // [rsp+9E0h] [rbp+880h]
  _BYTE v299[48]; // [rsp+9E8h] [rbp+888h] BYREF
  __int64 v300; // [rsp+A18h] [rbp+8B8h]
  _QWORD v301[2]; // [rsp+A20h] [rbp+8C0h] BYREF
  _BYTE v302[40]; // [rsp+A30h] [rbp+8D0h] BYREF
  int v303; // [rsp+A58h] [rbp+8F8h]
  int v304; // [rsp+A5Ch] [rbp+8FCh]
  __int64 v305; // [rsp+A60h] [rbp+900h]
  int v306; // [rsp+A71h] [rbp+911h]
  __int16 v307; // [rsp+A75h] [rbp+915h]
  char v308; // [rsp+A77h] [rbp+917h]
  __int16 v309; // [rsp+A89h] [rbp+929h]
  char v310; // [rsp+A8Bh] [rbp+92Bh]
  int v311; // [rsp+A94h] [rbp+934h]
  struct KERB_KDC_REQUEST_preauth_data_s *v312; // [rsp+AB8h] [rbp+958h] BYREF
  __int128 v313; // [rsp+AC0h] [rbp+960h]
  __int16 v314; // [rsp+AE0h] [rbp+980h] BYREF
  int v315; // [rsp+AE8h] [rbp+988h]
  int v316; // [rsp+B20h] [rbp+9C0h]
  int *v317; // [rsp+B28h] [rbp+9C8h]
  struct KERB_KDC_REQUEST_preauth_data_s *v318; // [rsp+B88h] [rbp+A28h]
  _BYTE v319[8]; // [rsp+B90h] [rbp+A30h] BYREF
  int v320; // [rsp+B98h] [rbp+A38h]
  int *v321; // [rsp+BA0h] [rbp+A40h]
  __int64 v322; // [rsp+C28h] [rbp+AC8h]
  struct _GUID v323; // [rsp+C40h] [rbp+AE0h] BYREF
  _BYTE Sid[80]; // [rsp+C50h] [rbp+AF0h] BYREF

  *(_QWORD *)&v131[5] = a4;
  *(_QWORD *)&v142.Length = a3;
  v138 = a1;
  v144 = a7;
  v154[0] = a9;
  v148 = a8;
  v160 = a13;
  v123 = a6;
  *(_QWORD *)&v167.Length = a10;
  v169 = a11;
  *(_QWORD *)&v150.Length = a12;
  ClientNetbiosAddress = 0;
  v136 = 0;
  *(_QWORD *)&v177.Length = 0;
  v177.Buffer = 0;
  v180 = 0;
  v181 = 0;
  v182 = 0;
  v183 = 0;
  v186 = 0;
  v187 = 0;
  v190 = 0;
  memset_0(v178, 0, 0x88u);
  v191 = 0;
  v192 = 0;
  *(_OWORD *)v270 = 0;
  v271 = 0;
  v274 = 0;
  v275 = 0;
  v276 = 0;
  v277 = 0;
  v278 = 0;
  v279 = 0;
  v280 = 0;
  memset_0(v272, 0, 0x98u);
  v281 = 0;
  v282 = 0;
  v283 = 0;
  *(_OWORD *)v246 = 0;
  v247 = 0;
  v250 = 0;
  v251 = 0;
  v252 = 0;
  v253 = 0;
  v254 = 0;
  v255 = 0;
  v256 = 0;
  memset_0(v248, 0, 0x98u);
  v257 = 0;
  v258 = 0;
  v266 = 0;
  memset_0(v259, 0, 0x90u);
  memset_0(v293, 0, 0x48u);
  v205 = 0;
  v206 = 0;
  v207 = 0;
  v208 = 0;
  memset_0(v288, 0, 0x48u);
  memset_0(v267, 0, 0x48u);
  memset_0(v319, 0, 0xA8u);
  v133 = 0;
  memset_0(v209, 0, 0x98u);
  memset_0(&v314, 0, 0xB0u);
  v149 = 0;
  v153 = 0;
  v139 = 0;
  memset(v242, 0, sizeof(v242));
  v243 = 0;
  memset(v244, 0, sizeof(v244));
  v245 = 0;
  v15 = 0;
  v152 = 0;
  v171 = 0;
  v146 = 0;
  v176 = 0;
  v135 = 0;
  v126 = 0;
  v165 = 0;
  v166 = 0;
  v134 = 0;
  v164 = 0;
  v193 = 0;
  v130 = 0;
  v140 = 0;
  v221 = 0;
  memset_0(v222, 0, 0x9Eu);
  v124[0] = 0;
  v198 = 0;
  memset_0(&v199, 0, 0x54u);
  *(_OWORD *)v172 = 0;
  v173 = 0;
  v137 = 0;
  memset(v240, 0, sizeof(v240));
  v241 = 0;
  memset(v286, 0, sizeof(v286));
  v287 = 0;
  v128 = 0;
  v170 = 0;
  v151 = 0;
  v159 = 0;
  v131[0] = 0;
  KerberosCryptoPolicy::Create((__int64 **)&v145);
  v16 = v145;
  if ( !v145 )
  {
    utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&v145);
    std::vector<unsigned int>::_Tidy((__int64)&v257);
    std::vector<unsigned int>::_Tidy((__int64)&v281);
    std::vector<unsigned int>::_Tidy((__int64)&v191);
    return 60;
  }
  v143 = 0;
  v158 = 0;
  v141[0] = 0;
  memset(v284, 0, sizeof(v284));
  v285 = 0;
  v17 = a9;
  if ( !a9 )
    v17 = a2;
  v18 = (struct KERB_KDC_REQUEST_preauth_data_s *)*((_QWORD *)v17 + 2);
  v125 = v18;
  v19 = (struct KERB_KDC_REQUEST *)((char *)v17 + 24);
  v127 = (struct KERB_KDC_REQUEST *)((char *)v17 + 24);
  TlsValue = a1;
  v175 = 0;
  v20 = 0;
  if ( KdcThreadContext::s_tlsIndex != -1 )
  {
    v21 = TlsSetValue(KdcThreadContext::s_tlsIndex, &TlsValue);
    v19 = v127;
    if ( v21 )
    {
      v175 = 1;
      v20 = 1;
    }
    else
    {
      v175 = 0;
      v20 = 0;
    }
  }
  if ( !v20 )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 281, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids);
    ClientNetbiosAddress = 29;
    goto LABEL_13;
  }
  v269 = v319;
  v321 = &v165;
  v320 = 32;
  v317 = &v166;
  v316 = 32;
  v126 = KerbConvertFlagsToUlong((struct KERB_KDC_REQUEST_BODY *)((char *)v19 + 8));
  if ( KdcEventTraceFlag )
  {
    EtwGetTraceEnableFlags(KdcTraceLoggerHandle);
    v224 = KdcHandleTGSRequestGuid;
    v223 = 1;
    v225 = 0x20000;
    v221 = 52;
    LODWORD(p_ClientNetbiosAddress) = v126;
    EtwLogTraceEvent(KdcTraceLoggerHandle, &v221);
  }
  if ( *(char *)a2 >= 0 )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 282, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids, 67379172);
LABEL_20:
    ClientNetbiosAddress = 16;
LABEL_13:
    LODWORD(v22) = 0;
LABEL_441:
    v39 = v127;
    goto LABEL_442;
  }
  LOBYTE(v132) = 0;
  v121 = 0;
  PreAuthDataEntry = (struct KERB_PA_DATA *)KerbFindPreAuthDataEntry(167, v18);
  if ( PreAuthDataEntry )
    ClientNetbiosAddress = KerbCheckPacOptionsPreAuthData(PreAuthDataEntry, &v134);
  if ( ClientNetbiosAddress )
  {
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_28;
    v25 = 283;
    v26 = 67379195;
    goto LABEL_27;
  }
  v143 = v134 & 0xF0000000;
  if ( KdcGlobalCDC && (v134 & 0x20000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 284, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids);
    }
    v28 = KdcForwardMessage(2, 0, 0, *(_QWORD *)&v131[5], a5);
    ClientNetbiosAddress = v28;
    LODWORD(v22) = 0;
    if ( v28 )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          285,
          WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids,
          67379212,
          v28);
      ClientNetbiosAddress = 29;
    }
    goto LABEL_39;
  }
  if ( (v134 & 0x10000000) != 0 )
    v263 |= 0x80000u;
  if ( (v134 & 0x80000000) != 0 )
    LsaIModifyPerformanceCounter(18, 0, 0);
  v29 = KerbFindPreAuthDataEntry(1, *((_QWORD *)a2 + 2));
  if ( !v29 )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 286, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids, 67379244);
    if ( (KDCInfoLevel & 0x10000000) != 0 )
    {
      v30 = v123;
      *(_DWORD *)v123 = -1073741064;
      *((_DWORD *)v30 + 1) = 67379245;
      *((_DWORD *)v30 + 2) = 2;
    }
    goto LABEL_20;
  }
  ClientNetbiosAddress = KdcVerifyKdcRequest(
                           *(unsigned __int8 **)(v29 + 16),
                           *(_DWORD *)(v29 + 8),
                           v138,
                           0xCu,
                           7u,
                           &v149,
                           &v153,
                           &v133,
                           (struct _KERB_ENCRYPTION_KEY *)v284,
                           (struct _KERB_ENCRYPTION_KEY *)v242,
                           (struct _KERB_ENCRYPTION_KEY *)v244,
                           (struct _KDC_TICKET_INFO *)&v177,
                           &v130,
                           &v128,
                           (unsigned __int8 *)v124,
                           v123);
  KerberosCryptoPolicy::SetKey(v16, (struct _KERB_ENCRYPTION_KEY *)v284, 1);
  if ( ClientNetbiosAddress == 41 )
  {
    v31 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 287, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids);
      v31 = WPP_GLOBAL_Control;
    }
    ClientNetbiosAddress = 31;
  }
  else
  {
    v31 = WPP_GLOBAL_Control;
  }
  if ( (v134 & 0x80000000) != 0 )
  {
    v189 |= 0x10u;
    if ( a10 )
    {
      *((_DWORD *)a10 + 64) |= 0x10u;
      v31 = WPP_GLOBAL_Control;
    }
  }
  if ( KdcGlobalCDC )
  {
    if ( ClientNetbiosAddress == -2147483641 )
    {
      v32 = 1;
      LODWORD(v22) = 0;
      goto LABEL_64;
    }
    if ( ClientNetbiosAddress == -2147483642 )
    {
      LODWORD(v22) = 0;
      v32 = 0;
LABEL_64:
      if ( v31 != (CSecurityData *)&WPP_GLOBAL_Control && (*((_DWORD *)v31 + 7) & 0x40000) != 0 )
        WPP_SF_(*((_QWORD *)v31 + 2), 288, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids);
      v33 = *(struct _KERB_MESSAGE_BUFFER **)&v131[5];
      v34 = KdcForwardMessage(2, 0, 0, *(_QWORD *)&v131[5], a5);
      ClientNetbiosAddress = v34;
      if ( v34 )
      {
        v35 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_72;
        }
        v36 = 289;
        v37 = 67379334;
LABEL_71:
        WPP_SF_Dd(*((_QWORD *)v35 + 2), v36, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids, v37, v34);
LABEL_72:
        ClientNetbiosAddress = 29;
        goto LABEL_441;
      }
      if ( v32 )
      {
        if ( KdcShouldFallback(v33, (struct _KERB_MESSAGE_BUFFER *)a5) )
        {
          if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 290, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids);
          }
          MIDL_user_free(a5[1]);
          a5[1] = 0;
          *(_DWORD *)a5 = 0;
          ClientNetbiosAddress = 20;
          goto LABEL_79;
        }
LABEL_353:
        v27 = v121;
        goto LABEL_91;
      }
LABEL_79:
      v27 = 0;
      goto LABEL_91;
    }
  }
  if ( ClientNetbiosAddress
    || v153
    && *(char *)v153 < 0
    && (ClientNetbiosAddress = KdcVerifyTgsChecksum(
                                 (struct KERB_KDC_REQUEST *)((char *)a2 + 24),
                                 (struct _KERB_ENCRYPTION_KEY *)v242,
                                 (struct KERB_AUTHENTICATOR *)((char *)v153 + 32)),
        v31 = WPP_GLOBAL_Control,
        ClientNetbiosAddress) )
  {
    if ( v31 != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)v31 + 28) & 1) != 0 )
      WPP_SF_Dd(
        *((_QWORD *)v31 + 2),
        291,
        WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids,
        67379382,
        ClientNetbiosAddress);
    v38 = v123;
    v27 = 0;
    LODWORD(v22) = 0;
    if ( (KDCInfoLevel & 0x10000000) != 0 )
    {
      *(_DWORD *)v123 = -1073741061;
      *((_DWORD *)v38 + 1) = 67379383;
      *((_DWORD *)v38 + 2) = 2;
    }
    goto LABEL_92;
  }
  if ( v128 && !v154[0] )
  {
    ClientNetbiosAddress = 60;
    if ( v31 == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)v31 + 28) & 1) == 0 )
    {
      LODWORD(v22) = 0;
      goto LABEL_441;
    }
    WPP_SF_d(*((_QWORD *)v31 + 2), 292, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids, 60);
    goto LABEL_89;
  }
  v39 = v127;
  if ( (*(_BYTE *)v127 & 8) != 0 )
  {
    ClientNetbiosAddress = KerbGetClientNetbiosAddress(&v176, *((struct PKERB_HOST_ADDRESSES_s **)v127 + 15));
    if ( ClientNetbiosAddress )
      goto LABEL_89;
  }
  if ( (*(_BYTE *)v39 & 0x40) != 0 )
  {
    ClientNetbiosAddress = KerbConvertPrincipalNameToKdcName(&v152, (struct KERB_KDC_REQUEST_BODY *)((char *)v39 + 48));
    LODWORD(v22) = 0;
    if ( ClientNetbiosAddress )
      goto LABEL_79;
    v15 = v152;
    ClientNetbiosAddress = KerbConvertKdcNameToString(v148, v152, 0);
    if ( ClientNetbiosAddress )
    {
LABEL_89:
      v27 = 0;
      goto LABEL_90;
    }
  }
  ClientNetbiosAddress = KerbConvertPrincipalNameToKdcName(&v171, (struct KERB_ENCRYPTED_TICKET *)((char *)v133 + 56));
  if ( ClientNetbiosAddress )
    goto LABEL_28;
  ClientNetbiosAddress = KerbConvertRealmToUnicodeString(&v146, (char *)v133 + 48);
  if ( ClientNetbiosAddress )
    goto LABEL_28;
  v43 = v171;
  if ( (*(_BYTE *)v39 & 2) != 0 )
  {
    Key = (struct _KERB_ENCRYPTION_KEY *)KerberosCryptoPolicy::GetKey(v16, 2, 0);
    if ( !Key )
    {
      ClientNetbiosAddress = 14;
      v27 = 0;
      LODWORD(v22) = 0;
LABEL_94:
      v40 = KdcAuditEngine::Get();
      if ( (unsigned __int8)KdcAuditEngine::ContainsDeprecationAttribute(v40, 128)
        && !KdcAuditEngine::PolicyHasDDSetDefined()
        && KdcAuditEngine::IsTargetSubjectToDDSet((const struct _KDC_TICKET_INFO *)&v177) )
      {
        if ( !v39 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        v41 = v133;
        if ( !v133 )
        {
          MicrosoftTelemetryAssertTriggeredNoArgs();
          v41 = v133;
        }
        if ( v39 && v41 )
        {
          KerberosCryptoPolicy::FromKdcTicketInfo(
            (KerberosCryptoPolicy **)&v131[5],
            (const struct _KDC_TICKET_INFO *)&v177);
          KdcAuditEngine::GetETypeInformationInPhase(v40, &v155, *((_QWORD *)v39 + 14), 128);
          if ( (_BYTE)v156 == (_BYTE)v22 || (_QWORD)v155 != *((_QWORD *)&v155 + 1) )
          {
            v42 = v127;
          }
          else
          {
            KerberosCryptoPolicy::Create((__int64 **)v154);
            v42 = v127;
            *(_QWORD *)&v142.Length = v127;
            v142.Buffer = (PWSTR)v133;
            KdcAuditEngine::LogEvent(v40, 1, &v142, &v177, &v145, &v131[5], v154, 0);
            utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(v154);
          }
          if ( (unsigned __int8)KdcAuditEngine::PolicyOnlyHasAssumedDisabledKeys(v40, &v131[5]) )
          {
            KerberosCryptoPolicy::Create((__int64 **)v154);
            *(_QWORD *)&v142.Length = v42;
            v142.Buffer = (PWSTR)v133;
            KdcAuditEngine::LogEvent(v40, 3, &v142, &v177, &v145, &v131[5], v154, 0);
            utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(v154);
          }
          utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&v131[5]);
          v38 = v123;
          LODWORD(v22) = 0;
          goto LABEL_265;
        }
      }
      goto LABEL_264;
    }
    v45 = KdcUnpackAdditionalTickets(
            *((struct KERB_KDC_REQUEST_BODY_additional_tickets_s **)v39 + 20),
            v126,
            v148,
            v43,
            &v146,
            Key,
            (struct _KDC_U2U_TICKET_INFO *)v270,
            (struct _KDC_S4U_TICKET_INFO *)v246,
            v123,
            (struct _KDC_U2U_TICKET_AUDIT_INFO *)v293,
            (struct _KDC_S4U_TICKET_AUDIT_INFO *)&v205);
    ClientNetbiosAddress = v45;
    if ( v45 )
    {
      LODWORD(v22) = 0;
      if ( !KdcGlobalCDC || (unsigned int)(v45 + 2147483642) > 1 )
        goto LABEL_39;
      if ( (v134 & 0x40000000) != 0 )
      {
        if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 293, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids);
        }
        ClientNetbiosAddress = 7;
        v38 = v123;
        FillExtendedError(-1073740943, 3, 1028, 8506, v123);
        goto LABEL_443;
      }
      if ( v45 == -2147483642 )
      {
        v46 = 1;
        v47 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
        {
          v48 = 294;
LABEL_131:
          WPP_SF_(*((_QWORD *)v47 + 2), v48, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids);
        }
      }
      else
      {
        v46 = 0;
        v47 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
        {
          v48 = 295;
          goto LABEL_131;
        }
      }
      v34 = KdcForwardMessage(2, 0, 0, *(_QWORD *)&v131[5], a5);
      ClientNetbiosAddress = v34;
      if ( v34 )
      {
        v35 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_72;
        }
        v36 = 296;
        v37 = 67379537;
        goto LABEL_71;
      }
      if ( v46 )
      {
        if ( (int)KdcClearSecretsIfRequired((struct _KERB_MESSAGE_BUFFER *)a5, v133) >= 0 )
          goto LABEL_353;
        ClientNetbiosAddress = 12;
      }
LABEL_39:
      v27 = 0;
LABEL_91:
      v38 = v123;
      goto LABEL_92;
    }
  }
  if ( (*(_BYTE *)v39 & 0x40) == 0 )
  {
    if ( (v283 & 0x10) == 0 )
    {
      ClientNetbiosAddress = 7;
      LODWORD(v22) = 0;
LABEL_442:
      v38 = v123;
      goto LABEL_443;
    }
    ClientNetbiosAddress = KerbDuplicateKdcName(&v152, v270[1]);
    LODWORD(v22) = 0;
    if ( ClientNetbiosAddress )
      goto LABEL_39;
    v15 = v152;
    ClientNetbiosAddress = KerbConvertKdcNameToString(v148, v152, 0);
    if ( ClientNetbiosAddress )
      goto LABEL_28;
  }
  ClientNetbiosAddress = KerbConvertKdcNameToString(v144, v43, &v146);
  if ( ClientNetbiosAddress )
    goto LABEL_28;
  ClientNetbiosAddress = KdcFindS4UClientAndRealm(
                           v125,
                           v15,
                           v16,
                           v133,
                           (struct _KERB_ENCRYPTION_KEY *)v244,
                           v43,
                           &v146,
                           v246,
                           v123,
                           (struct _KDC_S4U_TICKET_AUDIT_INFO *)&v205);
  if ( ClientNetbiosAddress )
  {
    v27 = 0;
    goto LABEL_90;
  }
  if ( v265 )
  {
    v49 = *((unsigned int *)v39 + 27);
    if ( (_DWORD)v49 != v264 )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 297, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids, v49, v264);
      ClientNetbiosAddress = 60;
      v38 = v123;
      FillExtendedError(-1073741198, 3, 1028, 8644, v123);
      LODWORD(v22) = 0;
      goto LABEL_443;
    }
  }
  if ( (CSecurityData::KdcFlags(0) & 0x80u) != 0 )
  {
    Time.QuadPart = 0;
    SystemTime.QuadPart = 0;
    NtQuerySystemTime(&SystemTime);
    KerbConvertGeneralizedTimeToLargeInt(&Time);
    if ( SystemTime.QuadPart > Time.QuadPart )
    {
      RtlAcquireResourceShared(&Resource, 1u);
      v50 = qword_1800B2E48;
      RtlReleaseResource(&Resource);
      if ( SystemTime.QuadPart - Time.QuadPart > v50 )
      {
        v51 = KdcCheckTgsLogonRestrictions(v43, &v146, v123);
        ClientNetbiosAddress = v51;
        if ( v51 )
        {
          v52 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control )
          {
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              WPP_SF_Dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                298,
                WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids,
                67379689,
                v51);
              v52 = WPP_GLOBAL_Control;
            }
            if ( v52 != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)v52 + 28) & 2) != 0 )
              WPP_SF__KERB_NAME_(*((_QWORD *)v52 + 2), 299, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids, v43);
          }
          goto LABEL_28;
        }
      }
      v39 = v127;
    }
  }
  *(_OWORD *)v288 = *(_OWORD *)((char *)v149 + 24);
  v289 = *(_OWORD *)((char *)v149 + 40);
  v290 = *(_OWORD *)((char *)v149 + 56);
  v291 = *(_OWORD *)((char *)v149 + 72);
  v292 = *((_QWORD *)v149 + 11);
  *((_QWORD *)&v291 + 1) = v133;
  if ( (v263 & 0x1000) != 0 )
  {
    v53 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000) != 0 )
      {
        WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2), 300, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids, &v146);
        v53 = WPP_GLOBAL_Control;
      }
      if ( v53 != (CSecurityData *)&WPP_GLOBAL_Control )
      {
        if ( (*((_DWORD *)v53 + 7) & 0x20000) != 0 )
        {
          WPP_SF__KERB_NAME_(*((_QWORD *)v53 + 2), 301, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids, v43);
          v53 = WPP_GLOBAL_Control;
        }
        if ( v53 != (CSecurityData *)&WPP_GLOBAL_Control )
        {
          if ( (*((_DWORD *)v53 + 7) & 0x20000) != 0 )
          {
            WPP_SF_Z(*((_QWORD *)v53 + 2), 302, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids, v262);
            v53 = WPP_GLOBAL_Control;
          }
          if ( v53 != (CSecurityData *)&WPP_GLOBAL_Control )
          {
            if ( (*((_DWORD *)v53 + 7) & 0x20000) != 0 )
            {
              WPP_SF__KERB_NAME_(*((_QWORD *)v53 + 2), 303, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids, v261);
              v53 = WPP_GLOBAL_Control;
            }
            if ( v53 != (CSecurityData *)&WPP_GLOBAL_Control )
            {
              if ( (*((_DWORD *)v53 + 7) & 0x20000) != 0 )
              {
                WPP_SF_Z(*((_QWORD *)v53 + 2), 304, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids, v260);
                v53 = WPP_GLOBAL_Control;
              }
              if ( v53 != (CSecurityData *)&WPP_GLOBAL_Control && (*((_DWORD *)v53 + 7) & 0x20000) != 0 )
              {
                v54 = 305;
                v55 = v15;
LABEL_191:
                WPP_SF__KERB_NAME_(*((_QWORD *)v53 + 2), v54, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids, v55);
                v53 = WPP_GLOBAL_Control;
              }
            }
          }
        }
      }
    }
  }
  else
  {
    v53 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF__KERB_NAME_(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          306,
          WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids,
          v15);
        v53 = WPP_GLOBAL_Control;
      }
      if ( v53 != (CSecurityData *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)v53 + 28) & 4) != 0 )
        {
          WPP_SF_Z(*((_QWORD *)v53 + 2), 307, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids, &v146);
          v53 = WPP_GLOBAL_Control;
        }
        if ( v53 != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)v53 + 28) & 4) != 0 )
        {
          v54 = 308;
          v55 = v43;
          goto LABEL_191;
        }
      }
    }
  }
  if ( (v126 & 2) != 0 )
  {
    v155 = 0;
    v156 = 0;
    v157 = 0;
    if ( v53 != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)v53 + 28) & 0x40) != 0 )
      WPP_SF_(*((_QWORD *)v53 + 2), 309, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids);
    if ( v153 && (*(_BYTE *)v153 & 0x40) != 0 )
    {
      *(_QWORD *)&v155 = 0;
      DWORD2(v155) = 1;
      HIDWORD(v155) = *((_DWORD *)v153 + 20);
      LODWORD(v156) = *((_DWORD *)v153 + 22);
      v56 = *((_QWORD *)v153 + 12);
      *((_QWORD *)&v156 + 1) = v56;
      LODWORD(v157) = 0;
    }
    else
    {
      v56 = *((_QWORD *)&v156 + 1);
    }
    v121 = 1;
    ClientNetbiosAddress = I_RenewTicket(
                             (struct KERB_TICKET *)v288,
                             (struct _KDC_TICKET_INFO *)&v177,
                             v39,
                             (unsigned __int64)&v155 & -(__int64)(v56 != 0),
                             v124[0],
                             (struct KERB_TICKET *)v267,
                             (__int64)v141,
                             v123);
LABEL_201:
    v22 = v125;
    goto LABEL_202;
  }
  if ( (v126 & 1) != 0 )
  {
    if ( v53 != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)v53 + 28) & 0x40) != 0 )
    {
      WPP_SF_(*((_QWORD *)v53 + 2), 310, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids);
      v53 = WPP_GLOBAL_Control;
    }
    ClientNetbiosAddress = 13;
    LOBYTE(v132) = 1;
    goto LABEL_204;
  }
  v194 = 0;
  v195 = 0;
  v196 = 0;
  v155 = 0;
  v156 = 0;
  v157 = 0;
  if ( v53 != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)v53 + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)v53 + 2), 311, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids);
  if ( (v283 & 0x10) != 0 )
  {
    *(_QWORD *)&v194 = 0;
    DWORD2(v194) = 1;
    HIDWORD(v194) = *((_DWORD *)v270[0] + 6);
    LODWORD(v195) = *((_DWORD *)v270[0] + 8);
    v57 = *((_QWORD *)v270[0] + 5);
    *((_QWORD *)&v195 + 1) = v57;
    LODWORD(v196) = 0;
  }
  else
  {
    v57 = *((_QWORD *)&v195 + 1);
  }
  if ( v153 && (*(_BYTE *)v153 & 0x40) != 0 )
  {
    *(_QWORD *)&v155 = 0;
    DWORD2(v155) = 1;
    HIDWORD(v155) = *((_DWORD *)v153 + 20);
    LODWORD(v156) = *((_DWORD *)v153 + 22);
    v58 = *((_QWORD *)v153 + 12);
    *((_QWORD *)&v156 + 1) = v58;
    LODWORD(v157) = 0;
  }
  else
  {
    v58 = *((_QWORD *)&v156 + 1);
  }
  ClientNetbiosAddress = I_GetTGSTicket(
                           (int)v288,
                           (int)v138,
                           (int)v144,
                           (int)v148,
                           v15,
                           *(__int64 *)&v142.Length,
                           (__int64)v39,
                           (__int64)&v177,
                           (unsigned __int64)&v194 & -(__int64)(v57 != 0),
                           (struct _KDC_S4U_TICKET_INFO *)v246,
                           (unsigned __int64)&v155 & -(__int64)(v58 != 0),
                           v124[0],
                           *(__int64 *)&v167.Length,
                           (__int64)v267,
                           (__int64)v141,
                           (__int64)&v139,
                           v123,
                           (__int64)&v140,
                           (__int64)v172,
                           (__int64)&v159,
                           (__int64)v131);
  if ( ClientNetbiosAddress || !v124[0] || !KerbEqualKdcNames(v15, xmmword_1800B2E20) )
    goto LABEL_201;
  v22 = v125;
  v59 = KerbFindPreAuthDataEntry(161, v125);
  v62 = v59;
  if ( v59 )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 312, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids);
    v63 = KdcCheckKeyListReqPreAuthData(
            (int)v43,
            v62,
            v60,
            v61,
            (__int64)v138,
            (__int64)v127,
            *(__int64 *)&v131[5],
            (struct _KERB_MESSAGE_BUFFER *)a5,
            (__int64)&v176,
            v160,
            (__int64)&v137,
            v123);
    ClientNetbiosAddress = v63;
    LODWORD(v22) = 0;
    if ( v63 )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 313, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids, v63);
      goto LABEL_39;
    }
    if ( a5[1] )
    {
      v64 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_39;
      v65 = 314;
    }
    else
    {
      if ( !*(_BYTE *)v160 )
      {
        if ( v137 )
        {
          if ( v139 )
            KerbConcatenatePaDataList(&v139, &v137);
          else
            v139 = v137;
          v137 = 0;
          if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 316, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids);
          }
        }
        KerbFreeAuthData(v137);
        v39 = v127;
        goto LABEL_201;
      }
      v64 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_39;
      v65 = 315;
    }
    WPP_SF_(*((_QWORD *)v64 + 2), v65, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids);
    goto LABEL_39;
  }
  v39 = v127;
LABEL_202:
  if ( !ClientNetbiosAddress )
  {
    if ( (v283 & 1) != 0 && v179 != v273 )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_DZDZD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          320,
          v179,
          67379956,
          (__int64)v272,
          v179,
          (__int64)&v177,
          v273);
LABEL_274:
      ClientNetbiosAddress = 36;
LABEL_275:
      v27 = v121;
      LODWORD(v22) = 0;
      goto LABEL_264;
    }
    if ( (v263 & 0x1001) == 0x1001 && v249 != v179 )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_DZDZD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          321,
          v179,
          67379969,
          (__int64)v248,
          v179,
          (__int64)&v177,
          v249);
      goto LABEL_274;
    }
    ClientNetbiosAddress = BuildReply(
                             0,
                             *((_DWORD *)v39 + 27),
                             (struct KERB_PRINCIPAL_NAME *)v268,
                             (char *)v267[1],
                             (struct PKERB_HOST_ADDRESSES_s *)(v322 & -(__int64)((v319[0] & 0x20) != 0)),
                             (struct KERB_TICKET *)v267,
                             (struct KERB_ENCRYPTED_KDC_REPLY *)&v314);
    if ( ClientNetbiosAddress )
      goto LABEL_28;
    if ( (v126 & 0x10000) != 0 )
    {
      if ( (v179 == 502 || v185) && KdcGlobalRequestCompoundId )
        v188 |= 0x20000u;
      v67 = (struct KERB_KDC_REQUEST_preauth_data_s *)MIDL_user_allocate(0x20u);
      v68 = v67;
      v137 = v67;
      if ( !v67 || (*((_DWORD *)v67 + 2) = 165, v69 = MIDL_user_allocate(4u), *((_QWORD *)v68 + 3) = v69, v70 = 0, !v69) )
      {
        ClientNetbiosAddress = 60;
        goto LABEL_275;
      }
      *v69 = v188;
      *((_DWORD *)v68 + 4) = 4;
      if ( v139 )
        KerbConcatenatePaDataList(&v139, &v137);
      else
        v139 = v137;
      v137 = v70;
      v39 = v127;
    }
    v71 = v143;
    if ( v143 )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 322, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids);
        v71 = v143;
      }
      v72 = KdcCreatePacOptionsPaDataList(v71, &v137);
      ClientNetbiosAddress = v72;
      if ( v72 )
      {
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_28;
        }
        v25 = 323;
        goto LABEL_302;
      }
      KerbConcatenatePaDataList(&v139, &v137);
    }
    v210 = 5;
    v211 = 13;
    v73 = KerbFindPreAuthDataEntry(130, v22);
    LODWORD(v22) = 0;
    if ( v73 )
    {
      LODWORD(v125) = 0;
      if ( (v263 & 0x10) == 0 || (v263 & 0x1000) == 0 )
        goto LABEL_306;
      ClientNetbiosAddress = KerbConvertKdcNameToPrincipalName((struct KERB_PRINCIPAL_NAME *)v200, v261);
      if ( ClientNetbiosAddress )
        goto LABEL_353;
      LOWORD(v198) = v198 | 0x80;
      ClientNetbiosAddress = KerbConvertUnicodeStringToRealm(v201, v262);
      if ( ClientNetbiosAddress )
        goto LABEL_353;
      v74 = v198 | 0x40;
      LOWORD(v198) = v198 | 0x40;
      v199 = *((_DWORD *)v39 + 27);
      if ( (v263 & 0x4000) != 0 )
      {
        v75 = 32;
        LODWORD(v125) = 32;
      }
      else
      {
        v75 = (int)v125;
      }
      if ( (v263 & 0x8000) != 0 )
      {
        v75 |= 0x10u;
        LODWORD(v125) = v75;
        if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 324, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids);
          v74 = v198;
          v75 = (int)v125;
        }
      }
      if ( v75 )
      {
        LOWORD(v198) = v74 | 0x10;
        v202 = 32;
        v203 = &v125;
      }
      v76 = KerberosCryptoPolicy::GetKey(v16, 0x200000011LL, 0);
      v77 = v76;
      if ( !v76 )
      {
        ClientNetbiosAddress = 14;
        v27 = v121;
        goto LABEL_93;
      }
      if ( (int)KerbSignS4UPreauthData(v76, (v263 & 0x4000) == 0, &v198) < 0 )
      {
        if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 325, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids);
        }
        goto LABEL_306;
      }
      v78 = MIDL_user_allocate(0x20u);
      v212 = v78;
      if ( !v78 )
      {
LABEL_306:
        ClientNetbiosAddress = 60;
LABEL_263:
        v27 = v121;
LABEL_264:
        v38 = v123;
        goto LABEL_265;
      }
      *v78 = 0;
      v78[1] = 0;
      *((_DWORD *)v212 + 2) = 130;
      ClientNetbiosAddress = KerbPackData(&v198, 67, (char *)v212 + 16, (char *)v212 + 24);
      if ( ClientNetbiosAddress )
        goto LABEL_353;
      *(_QWORD *)v212 = 0;
      v209[0] = 128;
      v129 = 0;
      if ( (int)KerberosCryptoPolicy::CipherHasAttribute(*(unsigned int *)(v77 + 12), 0x40000000, &v129) >= 0 )
      {
        if ( v129 )
        {
          ClientNetbiosAddress = KdcAddEncryptedS4uPadaData(
                                   (struct _KDC_S4U_TICKET_INFO *)v246,
                                   (struct PA_S4U_X509_USER *)&v198,
                                   &v139);
          if ( ClientNetbiosAddress )
            goto LABEL_353;
        }
      }
    }
    else
    {
      v212 = 0;
      v209[0] = 0;
    }
    if ( v139 )
    {
      v318 = v139;
      v314 |= 8u;
    }
    if ( (v263 & 0x3000) != 0 && (v263 & 4) != 0 )
    {
      ClientNetbiosAddress = KerbConvertKdcNameToPrincipalName((struct KERB_PRINCIPAL_NAME *)&v193, v261);
      if ( ClientNetbiosAddress )
        goto LABEL_353;
      ClientNetbiosAddress = KerbConvertUnicodeStringToRealm(&v164, v262);
      if ( ClientNetbiosAddress )
        goto LABEL_353;
      v79 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control )
      {
        if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 326, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids);
          v79 = WPP_GLOBAL_Control;
        }
        if ( v79 != (CSecurityData *)&WPP_GLOBAL_Control )
        {
          if ( *((char *)v79 + 28) < 0 )
          {
            WPP_SF__KERB_NAME_(*((_QWORD *)v79 + 2), 327, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids, v261);
            v79 = WPP_GLOBAL_Control;
          }
          if ( v79 != (CSecurityData *)&WPP_GLOBAL_Control && *((char *)v79 + 28) < 0 )
          {
            WPP_SF_Z(*((_QWORD *)v79 + 2), 328, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids, v262);
            v79 = WPP_GLOBAL_Control;
          }
        }
      }
      v213 = v164;
      v80 = v193;
    }
    else
    {
      v213 = *((_QWORD *)v133 + 6);
      v80 = *(_OWORD *)((char *)v133 + 56);
      v79 = WPP_GLOBAL_Control;
    }
    v214 = v80;
    v81 = v141[0];
    if ( !v141[0] )
    {
      if ( v79 != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)v79 + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)v79 + 2), 329, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids);
      goto LABEL_353;
    }
    if ( v179 == 502 || v185 )
    {
      v82 = 1;
      v83 = (KerberosCryptoPolicy *)*((_QWORD *)v141[0] + 6);
      *((_QWORD *)v141[0] + 6) = 0;
      if ( v83 )
        utl::default_delete<KerberosCryptoPolicy>::operator()((__int64)v79, v83);
      v81 = v141[0];
    }
    else
    {
      v82 = 0;
    }
    v84 = v184;
    if ( (v283 & 0x10) != 0 )
      v84 = 0;
    v85 = KerbPackTicketEx((struct KERB_TICKET *)v267, v81, v84, v82, (struct KERB_TICKET *)v215, &v170, &v151);
    ClientNetbiosAddress = v85;
    if ( v85 )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          330,
          WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids,
          67380287,
          v85);
      goto LABEL_353;
    }
    v86 = 8;
    if ( v130 == 1 )
      v86 = 9;
    v22 = v154[0];
    if ( v154[0] )
    {
      v87 = (struct _KERB_ENCRYPTION_KEY *)KerberosCryptoPolicy::GetKey(v16, 51, 0);
      if ( !v87 )
      {
        ClientNetbiosAddress = 14;
        if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          v27 = v121;
          LODWORD(v22) = 0;
          goto LABEL_93;
        }
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 331, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids);
        goto LABEL_28;
      }
      v72 = KdcBuildStrengthenedReplyKey(v87, (struct _KERB_ENCRYPTION_KEY *)v240, (struct _KERB_ENCRYPTION_KEY *)v286);
      ClientNetbiosAddress = v72;
      if ( v72 )
      {
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v25 = 332;
LABEL_302:
          v26 = v72;
LABEL_27:
          WPP_SF_d(*((_QWORD *)v24 + 2), v25, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids, v26);
LABEL_28:
          v27 = v121;
LABEL_90:
          LODWORD(v22) = 0;
          goto LABEL_91;
        }
LABEL_388:
        LODWORD(v22) = 0;
        goto LABEL_353;
      }
      KerberosCryptoPolicy::SetKey(v16, (struct _KERB_ENCRYPTION_KEY *)v286, 1);
    }
    v88 = KerbPackKdcReplyBody(
            (struct KERB_ENCRYPTED_KDC_REPLY *)&v314,
            v16,
            0,
            v86,
            0x4Cu,
            (struct KERB_ENCRYPTED_DATA *)v219);
    ClientNetbiosAddress = v88;
    if ( !v88 )
    {
      if ( v22
        && (v89 = v212,
            v90 = KdcBuildFastArmoredKdcReply(
                    v22,
                    (struct KERB_KDC_REPLY *)v209,
                    v169,
                    (struct _KERB_ENCRYPTION_KEY *)v240),
            KerbFreeAuthData(v89),
            ClientNetbiosAddress = v90,
            v22 = 0,
            v90) )
      {
        if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 334, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids, v90);
        }
      }
      else
      {
        ClientNetbiosAddress = KerbPackData(v209, 74, a5, a5 + 1);
        if ( !ClientNetbiosAddress )
        {
          v135 = KerberosCryptoPolicy::SelectEncryptionType(v141[0], 2);
          v323 = 0;
          LsaIGetLogonGuid((char *)v43 + 8, &v146, v269 + 110, 14, &v323);
          if ( v140 )
          {
            v91 = (struct _LSA_ADT_STRING_LIST *)MIDL_user_allocate(24LL * *((unsigned int *)v140 + 4) + 16);
            v92 = v91;
            v158 = v91;
            if ( v91 )
            {
              v93 = v91 + 1;
              v91->cStrings = *((_DWORD *)v140 + 4);
              v91->Strings = (PLSA_ADT_STRING_LIST_ENTRY)&v91[1];
              for ( i = (unsigned int)v22; i < *((_DWORD *)v140 + 4); ++i )
              {
                v93->cStrings = (unsigned int)v22;
                LOWORD(v93->Strings) = *(_WORD *)(*((_QWORD *)v140 + 3) + 16LL * i);
                WORD1(v93->Strings) = *(_WORD *)(*((_QWORD *)v140 + 3) + 16LL * i + 2);
                *(_QWORD *)&v93[1].cStrings = *(_QWORD *)(*((_QWORD *)v140 + 3) + 16LL * i + 8);
                v93 = (struct _LSA_ADT_STRING_LIST *)((char *)v93 + 24);
              }
            }
          }
          else
          {
            v92 = v158;
          }
          KdcMakeAccountSid(Sid, v179);
          if ( (qword_1800B2E50 & 0x400000000LL) != 0 )
          {
            v142 = 0;
            if ( v149 )
              KdcHashTicketEncryptedPart(*((unsigned __int8 **)v149 + 10), *((_DWORD *)v149 + 18), &v142);
            v167 = 0;
            KdcHashTicketEncryptedPart(v218, v217, &v167);
            v301[0] = 0;
            v301[1] = v22;
            v304 = 0;
            v306 = 0;
            v307 = 0;
            v308 = 0;
            v309 = 0;
            v310 = 0;
            v311 = 0;
            memset_0(v302, 0, 0x88u);
            v312 = v22;
            v313 = 0;
            v160 = (struct _PDC_RSO *)&v142;
            v161 = (struct _PDC_RSO *)&v167;
            v162 = v301;
            v163 = 1;
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnhancedAuditingForKerberosEtypes>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnhancedAuditingForKerberosEtypes>::GetImpl'::`2'::impl) )
            {
              CSecurityData::GetKrbtgtTicketInfo(v95, (struct _KDC_TICKET_INFO *)v301);
              KerberosCryptoPolicy::FromKdcTicketInfo(
                (KerberosCryptoPolicy **)&Time,
                (const struct _KDC_TICKET_INFO *)v301);
              KdcEventPrincipal::KdcEventPrincipal((__int64)v299, &v145);
              KdcEventPrincipal::KdcEventPrincipal((__int64)v297, v141);
              KdcEventPrincipal::ForDomainController(&v194);
              *(_OWORD *)v154 = 0;
              v96 = v127;
              KerberosCryptoPolicy::EtypeListToString(&v155, *((_QWORD *)v127 + 14));
              if ( (_BYTE)v156 != (_BYTE)v22 )
                *(_OWORD *)v154 = v155;
              LODWORD(v125) = v315;
              v97 = v138;
              if ( !v138 )
                v97 = (struct sockaddr *)&GlobalLocalhostAddress;
              v27 = v121;
              LODWORD(v22) = 0;
              LsaIAuditKdcEvent(
                (unsigned int)v121 + 673,
                v144,
                &v146,
                0,
                &v177,
                Sid,
                &v126,
                0,
                &v135,
                0,
                v97,
                &v323,
                v92,
                0,
                0,
                0,
                0,
                0,
                0,
                0,
                &v142,
                &v167,
                v300,
                v298,
                v197,
                v154,
                &v125,
                0);
              v98 = KdcAuditEngine::Get();
              if ( (unsigned __int8)KdcAuditEngine::ContainsDeprecationAttribute(v98, 64)
                && !KdcAuditEngine::PolicyHasDDSetDefined()
                && KdcAuditEngine::IsTargetSubjectToDDSet((const struct _KDC_TICKET_INFO *)&v177) )
              {
                KdcAuditEngine::GetETypeInformationInPhase(v98, &v160, *((_QWORD *)v96 + 14), 64);
                if ( (_BYTE)v162 && v160 == v161 )
                {
                  *(_DWORD *)&v131[5] = (_DWORD)v125;
                  v131[9] = 1;
                  *(_WORD *)&v131[10] = *(USHORT *)((char *)&v142.MaximumLength + 3);
                  v131[12] = *((_BYTE *)&v142.MaximumLength + 5);
                  v160 = v96;
                  v161 = v133;
                  KdcAuditEngine::LogEvent(v98, 0, &v160, &v177, &v145, v141, &Time, *(_QWORD *)&v131[5]);
                }
                if ( (unsigned __int8)KdcAuditEngine::PolicyOnlyHasAuditedKeys(v98, v141) )
                {
                  *(_DWORD *)&v131[5] = v135;
                  v131[9] = 1;
                  *(_WORD *)&v131[10] = *(USHORT *)((char *)&v142.MaximumLength + 3);
                  v131[12] = *((_BYTE *)&v142.MaximumLength + 5);
                  v160 = v96;
                  v161 = v133;
                  KdcAuditEngine::LogEvent(v98, 2, &v160, &v177, &v145, v141, &Time, *(_QWORD *)&v131[5]);
                }
              }
              utl::_OptionalData1<wil::unique_struct<_UNICODE_STRING,void (_UNICODE_STRING *),&void KerbFreeString(_UNICODE_STRING *),std::nullptr_t,0>,0>::~_OptionalData1<wil::unique_struct<_UNICODE_STRING,void (_UNICODE_STRING *),&void KerbFreeString(_UNICODE_STRING *),std::nullptr_t,0>,0>(&v155);
              KdcEventPrincipal::~KdcEventPrincipal((KdcEventPrincipal *)&v194);
              KdcEventPrincipal::~KdcEventPrincipal((KdcEventPrincipal *)v297);
              KdcEventPrincipal::~KdcEventPrincipal((KdcEventPrincipal *)v299);
              utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&Time);
              v92 = v158;
            }
            else
            {
              v99 = v138;
              if ( !v138 )
                v99 = (struct sockaddr *)&GlobalLocalhostAddress;
              v27 = v121;
              LsaIAuditKdcEvent(
                (unsigned int)v121 + 673,
                v144,
                &v146,
                0,
                &v177,
                Sid,
                &v126,
                v22,
                &v135,
                v22,
                v99,
                &v323,
                v92,
                v22,
                v22,
                v22,
                v22,
                v22,
                v22,
                v22,
                &v142,
                &v167,
                v22,
                v22,
                v22,
                v22,
                v22,
                v22);
            }
            if ( v142.Buffer )
              MIDL_user_free(v142.Buffer);
            if ( v167.Buffer )
              MIDL_user_free(v167.Buffer);
            FreeTicketInfo((struct _KDC_TICKET_INFO *)v301);
            std::vector<unsigned int>::_Tidy((__int64)&v312);
          }
          else
          {
            v27 = v121;
          }
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExtendedAuditingForKerberos>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ExtendedAuditingForKerberos>::GetImpl'::`2'::impl) )
          {
            LODWORD(v22) = 0;
            LogGetTgsExtendedAudit(
              v144,
              &v146,
              &v177,
              Sid,
              &v126,
              0,
              &v135,
              v138,
              &v323,
              v92,
              v149,
              v127,
              (struct KERB_TICKET *)v215,
              (struct KERB_ENCRYPTED_KDC_REPLY *)&v314,
              &v176,
              v123,
              &v134,
              &v184,
              v169,
              (struct _KDC_U2U_TICKET_INFO *)v270,
              (struct _KDC_S4U_TICKET_INFO *)v246,
              (struct _KDC_U2U_TICKET_AUDIT_INFO *)v293,
              (struct _KDC_S4U_TICKET_AUDIT_INFO *)&v205,
              v159);
          }
          if ( (v172[0] & 1) != 0 )
          {
            memset_0(v301, 0, 0xC0u);
            LODWORD(v301[0]) = 0x20000;
            v303 = 2;
            v305 = v173;
            SamIUpdateLogonStatistics(v172[1], v301);
          }
          if ( (v263 & 0x2000) != 0 )
          {
            if ( (v263 & 0x40000) != 0 )
            {
              LsaIModifyPerformanceCounter(17, 0, 0);
              KerbSqmKdcA2DFIncrement();
            }
            else
            {
              LsaIModifyPerformanceCounter(16, 0, 0);
              KerbSqmKdcA2D2Increment();
            }
          }
          goto LABEL_91;
        }
      }
      goto LABEL_353;
    }
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        333,
        WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids,
        67380336,
        v88);
      goto LABEL_28;
    }
    goto LABEL_388;
  }
  v53 = WPP_GLOBAL_Control;
LABEL_204:
  LODWORD(v22) = 0;
  if ( !KdcGlobalCDC || (unsigned int)(ClientNetbiosAddress + 2147483642) > 1 )
    goto LABEL_353;
  if ( (v134 & 0x40000000) != 0 )
  {
    if ( v53 != (CSecurityData *)&WPP_GLOBAL_Control && (*((_DWORD *)v53 + 7) & 0x40000) != 0 )
      WPP_SF_(*((_QWORD *)v53 + 2), 317, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids);
    ClientNetbiosAddress = 7;
    v38 = v123;
    FillExtendedError(-1073740943, 3, 1028, 8881, v123);
    v27 = v121;
    goto LABEL_265;
  }
  if ( v53 != (CSecurityData *)&WPP_GLOBAL_Control && (*((_DWORD *)v53 + 7) & 0x40000) != 0 )
    WPP_SF_(*((_QWORD *)v53 + 2), 318, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids);
  v66 = KdcForwardMessage(2, 0, 0, *(_QWORD *)&v131[5], a5);
  ClientNetbiosAddress = v66;
  if ( v66 )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        319,
        WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids,
        67379903,
        v66);
    ClientNetbiosAddress = 29;
    goto LABEL_263;
  }
  v38 = v123;
  v27 = v121;
  if ( (int)KdcClearSecretsIfRequired((struct _KERB_MESSAGE_BUFFER *)a5, v133) < 0 )
    ClientNetbiosAddress = 12;
LABEL_92:
  if ( ClientNetbiosAddress == 14 )
  {
LABEL_93:
    v39 = v127;
    goto LABEL_94;
  }
LABEL_265:
  if ( !v27 )
    goto LABEL_441;
  v39 = v127;
LABEL_443:
  Target = KdcTelemetry::GetTarget(&v177);
  KdcTelemetry::MessageOperation(v101, Target, 0, v216, v220, ClientNetbiosAddress);
  if ( ClientNetbiosAddress != (_DWORD)v22 )
  {
    if ( v143 )
    {
      if ( *(_QWORD *)&v150.Length )
      {
        PacOptionsPaDataList = KdcCreatePacOptionsPaDataList(
                                 v143,
                                 *(struct KERB_KDC_REQUEST_preauth_data_s ***)&v150.Length);
        v136 = PacOptionsPaDataList;
        if ( PacOptionsPaDataList )
        {
          if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              335,
              WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids,
              PacOptionsPaDataList);
            PacOptionsPaDataList = v136;
          }
          ClientNetbiosAddress = PacOptionsPaDataList;
        }
      }
    }
  }
  KerbFreeKey(v240);
  if ( KdcEventTraceFlag == (_DWORD)v22 )
  {
    v103 = v144;
    v106 = v148;
  }
  else
  {
    v132 = (__int16)v22;
    *(_QWORD *)&v150.Length = 131074;
    v150.Buffer = (PWSTR)&v132;
    v223 = 2;
    v225 = 1179648;
    p_ClientNetbiosAddress = &ClientNetbiosAddress;
    v227 = 4;
    v103 = v144;
    if ( v144->Buffer && (Length = v144->Length) != 0 )
    {
      v105 = v144;
    }
    else
    {
      v105 = &v150;
      Length = 2;
    }
    v228 = v105;
    v229 = 2;
    Buffer = v105->Buffer;
    v231 = Length;
    v106 = v148;
    if ( v148->Buffer && (v107 = v148->Length) != 0 )
    {
      v108 = v148;
    }
    else
    {
      v108 = &v150;
      v107 = 2;
    }
    v232 = v108;
    v233 = 2;
    v234 = v108->Buffer;
    v235 = v107;
    if ( v146.Buffer && (v109 = v146.Length) != 0 )
    {
      v110 = &v146;
    }
    else
    {
      v110 = &v150;
      v109 = 2;
    }
    v236 = v110;
    v237 = 2;
    v238 = v110->Buffer;
    v239 = v109;
    v221 = 160;
    EtwLogTraceEvent(KdcTraceLoggerHandle, &v221);
  }
  if ( ClientNetbiosAddress )
  {
    if ( (unsigned int)(ClientNetbiosAddress + 2147483642) <= 1 )
    {
      v136 = -1073740943;
      v111 = -1073740943;
    }
    else
    {
      v136 = ClientNetbiosAddress;
      v111 = ClientNetbiosAddress;
    }
    if ( (qword_1800B2E50 & 0x800000000LL) == 0 )
      goto LABEL_475;
    if ( ClientNetbiosAddress == 7 )
    {
      if ( (KdcExtraLogLevel & 1) == 0 )
        goto LABEL_475;
    }
    else if ( (unsigned int)(ClientNetbiosAddress - 13) <= 1 && (v126 & 0x20000) != 0 && (KdcExtraLogLevel & 0x10) == 0 )
    {
      goto LABEL_475;
    }
    if ( v111 != -1073740943 )
    {
      v150 = 0;
      if ( v149 )
        KdcHashTicketEncryptedPart(*((unsigned __int8 **)v149 + 10), *((_DWORD *)v149 + 18), &v150);
      v142 = 0;
      KdcHashTicketEncryptedPart(v218, v217, &v142);
      v112 = v138;
      v119 = v138;
      if ( !v138 )
        v119 = (struct sockaddr *)&GlobalLocalhostAddress;
      v120 = v103;
      if ( !v103->Buffer )
        v120 = &KdcNullString;
      LsaIAuditKdcEvent(
        673,
        v120,
        &v146,
        0,
        v106,
        0,
        &v126,
        &v136,
        0,
        0,
        v119,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        &v150,
        &v142,
        0,
        0,
        0,
        0,
        0,
        0);
      if ( v150.Buffer )
        MIDL_user_free(v150.Buffer);
      if ( v142.Buffer )
        MIDL_user_free(v142.Buffer);
LABEL_476:
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExtendedAuditingForKerberos>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ExtendedAuditingForKerberos>::GetImpl'::`2'::impl) )
        LogGetTgsExtendedAudit(
          v103,
          &v146,
          v106,
          0,
          &v126,
          &v136,
          &v135,
          v112,
          0,
          0,
          v149,
          v39,
          0,
          0,
          &v176,
          v38,
          &v134,
          0,
          v169,
          (struct _KDC_U2U_TICKET_INFO *)v270,
          (struct _KDC_S4U_TICKET_INFO *)v246,
          (struct _KDC_U2U_TICKET_AUDIT_INFO *)v293,
          (struct _KDC_S4U_TICKET_AUDIT_INFO *)&v205,
          v159);
      if ( ClientNetbiosAddress )
        goto LABEL_481;
      goto LABEL_479;
    }
LABEL_475:
    v112 = v138;
    goto LABEL_476;
  }
LABEL_479:
  v113 = KdcGlobalTicketSizeThreshold - (KdcGlobalTicketSizeThreshold >> 3);
  if ( v151 >= v113 )
    KdcReportLargeTicket(v103, v106, v151, v113, v170);
LABEL_481:
  if ( v170 )
    MIDL_user_free(v170);
  if ( v159 )
    SamIFree_UserInternal6Information();
  KerbFreeSid(&v171);
  KerbFreeString(&v146);
  KerbFreeString(&v176);
  KerbFreeSid(&v152);
  KerbFreeKey(v242);
  KerbFreeKey(v244);
  KdcFreeKdcReplyBody((struct KERB_ENCRYPTED_KDC_REPLY *)&v314);
  KerbFreePrincipalName(&v193);
  KerbFreeRealm(&v164);
  KdcFreeU2UTicketInfo((struct _KDC_U2U_TICKET_INFO *)v270);
  KdcFreeS4UTicketInfo((struct _KDC_S4U_TICKET_INFO *)v246);
  KerbFreeString(v294);
  KerbFreeString(v295);
  KerbFreeString(v296);
  KerbFreeString(&v206);
  KerbFreeString(&v207);
  if ( v139 )
    KerbFreeAuthData(v139);
  if ( v137 )
    KerbFreeAuthData(v137);
  KerbFreeData(53, v149);
  KerbFreeData(52, v153);
  KerbFreeData(51, v133);
  KdcFreeInternalTicket((struct KERB_TICKET *)v267);
  FreeTicketInfo((struct _KDC_TICKET_INFO *)&v177);
  KdcFreeKdcReply((struct KERB_KDC_REPLY *)v209);
  if ( v158 )
    MIDL_user_free(v158);
  v114 = v140;
  if ( v140 )
  {
    v115 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
    {
      WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2), 336, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids, v140);
      v115 = WPP_GLOBAL_Control;
      v114 = v140;
    }
    for ( j = 0; j < *((_DWORD *)v114 + 4); ++j )
    {
      if ( v115 != (CSecurityData *)&WPP_GLOBAL_Control && (*((_DWORD *)v115 + 7) & 0x8000) != 0 )
      {
        WPP_SF_DZ(
          *((_QWORD *)v115 + 2),
          337,
          (unsigned int)WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids,
          j,
          v114[3] + 16LL * j);
        v115 = WPP_GLOBAL_Control;
        v114 = v140;
      }
    }
    MIDL_user_free(v114);
  }
  KerbFreePrincipalName(v200);
  KerbFreeRealm(v201);
  MIDL_user_free(v204);
  if ( v173 )
    SamrCloseHandle(&v173);
  if ( v172[1] )
    SamrCloseHandle(&v172[1]);
  v117 = ClientNetbiosAddress;
  KdcThreadContext::~KdcThreadContext((KdcThreadContext *)&TlsValue);
  utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(v141);
  utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&v145);
  std::vector<unsigned int>::_Tidy((__int64)&v257);
  std::vector<unsigned int>::_Tidy((__int64)&v281);
  std::vector<unsigned int>::_Tidy((__int64)&v191);
  return v117;
}

```

## disassembly

```asm
0x180021eb4  push    rbp
0x180021eb6  push    rbx
0x180021eb7  push    rsi
0x180021eb8  push    rdi
0x180021eb9  push    r12
0x180021ebb  push    r13
0x180021ebd  push    r14
0x180021ebf  push    r15
0x180021ec1  lea     rbp, [rsp-0B58h]
0x180021ec9  sub     rsp, 0CB8h
0x180021ed0  mov     rax, cs:__security_cookie
0x180021ed7  xor     rax, rsp
0x180021eda  mov     [rbp+0B90h+var_50], rax
0x180021ee1  mov     qword ptr [rbp+0B90h+var_BDD+5], r9
0x180021ee5  mov     qword ptr [rbp+0B90h+var_B80.Length], r8
0x180021ee9  mov     rbx, rdx
0x180021eec  mov     r14, rcx
0x180021eef  mov     [rbp+0B90h+var_BA8], rcx
0x180021ef3  mov     rax, [rbp+0B90h+arg_30]
0x180021efa  mov     [rbp+0B90h+var_B68], rax
0x180021efe  mov     rsi, [rbp+0B90h+arg_40]
0x180021f05  mov     [rbp+0B90h+var_B08], rsi
0x180021f0c  mov     rax, [rbp+0B90h+arg_38]
0x180021f13  mov     [rbp+0B90h+var_B40], rax
0x180021f17  mov     rax, [rbp+0B90h+arg_60]
0x180021f1e  mov     [rbp+0B90h+var_AC0], rax
0x180021f25  mov     r12, [rbp+0B90h+arg_20]
0x180021f2c  mov     rax, [rbp+0B90h+arg_28]
0x180021f33  mov     [rbp+0B90h+var_C08], rax
0x180021f37  mov     r13, [rbp+0B90h+arg_48]
0x180021f3e  mov     qword ptr [rbp+0B90h+var_A90.Length], r13
0x180021f45  mov     rax, [rbp+0B90h+arg_50]
0x180021f4c  mov     [rbp+0B90h+var_A78], rax
0x180021f53  mov     rax, [rbp+0B90h+arg_58]
0x180021f5a  mov     qword ptr [rbp+0B90h+var_B30.Length], rax
0x180021f5e  xor     edi, edi
0x180021f60  mov     [rbp+0B90h+var_C0C], edi
0x180021f63  mov     [rbp+0B90h+var_BB8], edi
0x180021f66  mov     qword ptr [rbp+0B90h+var_A20.Length], rdi
0x180021f6d  mov     [rbp+0B90h+var_A20.Buffer], rdi
0x180021f74  xor     eax, eax
0x180021f76  mov     [rbp+0B90h+var_9E4], eax
0x180021f7c  mov     [rbp+0B90h+var_9CF], eax
0x180021f82  mov     [rbp+0B90h+var_9CB], ax
0x180021f89  mov     [rbp+0B90h+var_9C9], al
0x180021f8f  mov     [rbp+0B90h+var_9B7], ax
0x180021f96  mov     [rbp+0B90h+var_9B5], al
0x180021f9c  mov     [rbp+0B90h+var_9AC], eax
0x180021fa2  xor     edx, edx; Val
0x180021fa4  mov     r8d, 88h; Size
0x180021faa  lea     rcx, [rbp+0B90h+var_A10]; void *
0x180021fb1  call    memset_0
0x180021fb6  mov     [rbp+0B90h+var_988], rdi
0x180021fbd  xorps   xmm0, xmm0
0x180021fc0  movdqa  [rbp+0B90h+var_980], xmm0
0x180021fc8  movups  xmmword ptr [rbp+0B90h+var_510], xmm0
0x180021fcf  movups  [rbp+0B90h+var_500], xmm0
0x180021fd6  xor     eax, eax
0x180021fd8  mov     [rbp+0B90h+var_4B4], eax
0x180021fde  mov     [rbp+0B90h+var_49F], eax
0x180021fe4  mov     [rbp+0B90h+var_49B], ax
0x180021feb  mov     [rbp+0B90h+var_499], al
0x180021ff1  mov     [rbp+0B90h+var_487], ax
0x180021ff8  mov     [rbp+0B90h+var_485], al
0x180021ffe  mov     [rbp+0B90h+var_47C], eax
0x180022004  mov     r15d, 98h
0x18002200a  mov     r8d, r15d; Size
0x18002200d  xor     edx, edx; Val
0x18002200f  lea     rcx, [rbp+0B90h+var_4F0]; void *
0x180022016  call    memset_0
0x18002201b  mov     [rbp+0B90h+var_458], rdi
0x180022022  xorps   xmm0, xmm0
0x180022025  movdqa  [rbp+0B90h+var_450], xmm0
0x18002202d  xor     eax, eax
0x18002202f  mov     [rbp+0B90h+var_440], rax
0x180022036  movups  xmmword ptr [rbp+0B90h+var_6C0], xmm0
0x18002203d  mov     [rbp+0B90h+var_6B0], rax
0x180022044  mov     [rbp+0B90h+var_66C], eax
0x18002204a  mov     [rbp+0B90h+var_657], eax
0x180022050  mov     [rbp+0B90h+var_653], ax
0x180022057  mov     [rbp+0B90h+var_651], al
0x18002205d  mov     [rbp+0B90h+var_63F], ax
0x180022064  mov     [rbp+0B90h+var_63D], al
0x18002206a  mov     [rbp+0B90h+var_634], eax
0x180022070  mov     r8d, r15d; Size
0x180022073  xor     edx, edx; Val
0x180022075  lea     rcx, [rbp+0B90h+var_6A8]; void *
0x18002207c  call    memset_0
0x180022081  xorps   xmm0, xmm0
0x180022084  movdqa  [rbp+0B90h+var_610], xmm0
0x18002208c  mov     [rbp+0B90h+var_600], rdi
0x180022093  xor     eax, eax
0x180022095  mov     [rbp+0B90h+var_574], eax
0x18002209b  xor     edx, edx; Val
0x18002209d  lea     r8d, [r15-8]; Size
0x1800220a1  lea     rcx, [rbp+0B90h+var_5F8]; void *
0x1800220a8  call    memset_0
0x1800220ad  lea     edi, [r15-50h]
0x1800220b1  mov     r8d, edi; Size
0x1800220b4  xor     edx, edx; Val
0x1800220b6  lea     rcx, [rbp+0B90h+var_390]; void *
0x1800220bd  call    memset_0
0x1800220c2  xorps   xmm0, xmm0
0x1800220c5  xor     eax, eax
0x1800220c7  movups  [rbp+0B90h+var_8C0], xmm0
0x1800220ce  movups  [rbp+0B90h+var_8B0], xmm0
0x1800220d5  movups  [rbp+0B90h+var_8A0], xmm0
0x1800220dc  mov     [rbp+0B90h+var_890], rax
0x1800220e3  mov     r8d, edi; Size
0x1800220e6  xor     edx, edx; Val
0x1800220e8  lea     rcx, [rbp+0B90h+var_3E0]; void *
0x1800220ef  call    memset_0
0x1800220f4  mov     r8d, edi; Size
0x1800220f7  xor     edx, edx; Val
0x1800220f9  lea     rcx, [rbp+0B90h+var_560]; void *
0x180022100  call    memset_0
0x180022105  xor     edx, edx; Val
0x180022107  lea     r8d, [r15+10h]; Size
0x18002210b  lea     rcx, [rbp+0B90h+var_160]; void *
0x180022112  call    memset_0
0x180022117  xor     edi, edi
0x180022119  mov     [rbp+0B90h+var_BC8], rdi
0x18002211d  mov     r8d, r15d; Size
0x180022120  xor     edx, edx; Val
0x180022122  lea     rcx, [rbp+0B90h+var_880]; void *
0x180022129  call    memset_0
0x18002212e  xor     edx, edx; Val
0x180022130  lea     r8d, [r15+18h]; Size
0x180022134  lea     rcx, [rbp+0B90h+var_210]; void *
0x18002213b  call    memset_0
0x180022140  mov     [rbp+0B90h+var_B38], rdi
0x180022144  mov     [rbp+0B90h+var_B10], rdi
0x18002214b  mov     [rbp+0B90h+var_BA0], rdi
0x18002214f  xorps   xmm0, xmm0
0x180022152  xor     eax, eax
0x180022154  movups  [rbp+0B90h+var_718], xmm0
0x18002215b  movups  [rbp+0B90h+var_708], xmm0
0x180022162  mov     [rbp+0B90h+var_6F8], rax
0x180022169  xorps   xmm1, xmm1
0x18002216c  movups  [rbp+0B90h+var_6F0], xmm1
0x180022173  movups  [rbp+0B90h+var_6E0], xmm1
0x18002217a  mov     [rbp+0B90h+var_6D0], rax
0x180022181  mov     r15d, edi
0x180022184  mov     [rbp+0B90h+var_B18], rdi
0x180022188  mov     [rbp+0B90h+var_A68], rdi
0x18002218f  movups  xmmword ptr [rbp+0B90h+var_B58.Length], xmm0
0x180022193  movups  xmmword ptr [rbp+0B90h+var_A38.Length], xmm1
0x18002219a  mov     [rbp+0B90h+var_BBC], edi
0x18002219d  mov     [rbp+0B90h+var_BF0], edi
0x1800221a0  mov     [rbp+0B90h+var_A98], edi
0x1800221a6  mov     [rbp+0B90h+var_A94], edi
0x1800221ac  mov     [rbp+0B90h+var_BC0], edi
0x1800221af  mov     [rbp+0B90h+var_AA0], rdi
0x1800221b6  movups  [rbp+0B90h+var_970], xmm0
0x1800221bd  mov     [rbp+0B90h+var_BDE], dil
0x1800221c1  mov     [rbp+0B90h+var_B98], rdi
0x1800221c5  mov     [rbp+0B90h+var_7E0], di
0x1800221cc  xor     edx, edx; Val
0x1800221ce  mov     r8d, 9Eh; Size
0x1800221d4  lea     rcx, [rbp+0B90h+var_7DE]; void *
0x1800221db  call    memset_0
0x1800221e0  mov     [rbp+0B90h+var_C00], dil
0x1800221e4  mov     [rbp+0B90h+var_920], edi
0x1800221ea  xor     edx, edx; Val
0x1800221ec  lea     r8d, [rdi+54h]; Size
0x1800221f0  lea     rcx, [rbp+0B90h+var_91C]; void *
0x1800221f7  call    memset_0
0x1800221fc  xorps   xmm0, xmm0
0x1800221ff  xor     eax, eax
0x180022201  movups  xmmword ptr [rbp+0B90h+var_A60], xmm0
0x180022208  mov     [rbp+0B90h+var_A50], rax
0x18002220f  mov     [rbp+0B90h+var_BB0], rdi
0x180022213  movups  [rbp+0B90h+var_740], xmm0
0x18002221a  movups  [rbp+0B90h+var_730], xmm0
0x180022221  mov     [rbp+0B90h+var_720], rax
0x180022228  xorps   xmm1, xmm1
0x18002222b  movups  [rbp+0B90h+var_408], xmm1
0x180022232  movups  [rbp+0B90h+var_3F8], xmm1
0x180022239  mov     [rbp+0B90h+var_3E8], rax
0x180022240  mov     [rbp+0B90h+var_BE0], dil
0x180022244  mov     [rbp+0B90h+var_A70], rdi
0x18002224b  mov     [rbp+0B90h+var_B20], edi
0x18002224e  mov     [rbp+0B90h+var_AC8], rdi
0x180022255  mov     [rbp+0B90h+var_BDD], dil
0x180022259  lea     rcx, [rbp+0B90h+var_B60]
0x18002225d  call    ?Create@KerberosCryptoPolicy@@SA?AV?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@W4Kerb3961PolicyType@@@Z; KerberosCryptoPolicy::Create(Kerb3961PolicyType)
0x180022262  nop
0x180022263  mov     rdi, [rbp+0B90h+var_B60]
0x180022267  xor     ecx, ecx
0x180022269  test    rdi, rdi
0x18002226c  jz      loc_180024F9B
0x180022272  mov     [rbp+0B90h+var_B70], ecx
0x180022275  mov     [rbp+0B90h+var_AD0], rcx
0x18002227c  mov     [rbp+0B90h+var_B90], rcx
0x180022280  xorps   xmm0, xmm0
0x180022283  xor     eax, eax
0x180022285  movups  [rbp+0B90h+var_430], xmm0
0x18002228c  movups  [rbp+0B90h+var_420], xmm0
0x180022293  mov     [rbp+0B90h+var_410], rax
0x18002229a  mov     rax, rsi
0x18002229d  test    rsi, rsi
0x1800222a0  cmovz   rax, rbx
0x1800222a4  mov     rsi, [rax+10h]
0x1800222a8  mov     [rbp+0B90h+var_BF8], rsi
0x1800222ac  lea     rdx, [rax+18h]
0x1800222b0  mov     [rbp+0B90h+var_BE8], rdx
0x1800222b4  mov     [rbp+0B90h+TlsValue], r14
0x1800222bb  xor     r14d, r14d
0x1800222be  mov     [rbp+0B90h+var_A40], r14b
0x1800222c5  mov     al, r14b
0x1800222c8  mov     ecx, cs:?s_tlsIndex@KdcThreadContext@@0KA; dwTlsIndex
0x1800222ce  cmp     ecx, 0FFFFFFFFh
0x1800222d1  jz      short loc_1800222FD
0x1800222d3  lea     rdx, [rbp+0B90h+TlsValue]; lpTlsValue
0x1800222da  call    cs:__imp_TlsSetValue
0x1800222e0  mov     rdx, [rbp+0B90h+var_BE8]
0x1800222e4  test    eax, eax
0x1800222e6  jz      short loc_1800222F3
0x1800222e8  mov     [rbp+0B90h+var_A40], 1
0x1800222ef  mov     al, 1
0x1800222f1  jmp     short loc_1800222FD
0x1800222f3  mov     [rbp+0B90h+var_A40], r14b
0x1800222fa  mov     al, r14b
0x1800222fd  test    al, al
0x1800222ff  jnz     short loc_180022347
0x180022301  lea     rsi, WPP_GLOBAL_Control
0x180022308  lea     r14, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids
0x18002230f  mov     rcx, cs:WPP_GLOBAL_Control
0x180022316  cmp     rcx, rsi
0x180022319  jz      short loc_180022332
0x18002231b  test    byte ptr [rcx+1Ch], 1
0x18002231f  jz      short loc_180022332
0x180022321  mov     edx, 119h
0x180022326  mov     r8, r14
0x180022329  mov     rcx, [rcx+10h]
0x18002232d  call    WPP_SF_
0x180022332  mov     [rbp+0B90h+var_C0C], 1Dh
0x180022339  mov     r10d, 1
0x18002233f  xor     r15d, r15d
0x180022342  jmp     loc_180024850
0x180022347  lea     rax, [rbp+0B90h+var_160]
0x18002234e  mov     [rbp+0B90h+var_528], rax
0x180022355  lea     rax, [rbp+0B90h+var_A98]
0x18002235c  mov     [rbp+0B90h+var_150], rax
0x180022363  mov     [rbp+0B90h+var_158], 20h ; ' '
0x18002236d  lea     rax, [rbp+0B90h+var_A94]
0x180022374  mov     [rbp+0B90h+var_1C8], rax
0x18002237b  mov     [rbp+0B90h+var_1D0], 20h ; ' '
0x180022385  lea     rcx, [rdx+8]; struct tagASN1bitstring_t *
0x180022389  call    ?KerbConvertFlagsToUlong@@YAKPEBUtagASN1bitstring_t@@@Z; KerbConvertFlagsToUlong(tagASN1bitstring_t const *)
0x18002238e  mov     [rbp+0B90h+var_BF0], eax
0x180022391  cmp     cs:KdcEventTraceFlag, r14d
0x180022398  jz      short loc_1800223F0
0x18002239a  mov     rcx, cs:KdcTraceLoggerHandle
0x1800223a1  call    cs:__imp_EtwGetTraceEnableFlags
0x1800223a7  movups  xmm0, cs:KdcHandleTGSRequestGuid
0x1800223ae  movdqu  [rbp+0B90h+var_7C8], xmm0
0x1800223b6  mov     [rbp+0B90h+var_7DC], 1
0x1800223bd  mov     [rbp+0B90h+var_7B4], 20000h
0x1800223c7  mov     eax, 34h ; '4'
0x1800223cc  mov     [rbp+0B90h+var_7E0], ax
0x1800223d3  mov     eax, [rbp+0B90h+var_BF0]
0x1800223d6  mov     dword ptr [rbp+0B90h+var_7B0], eax
0x1800223dc  lea     rdx, [rbp+0B90h+var_7E0]
0x1800223e3  mov     rcx, cs:KdcTraceLoggerHandle
0x1800223ea  call    cs:__imp_EtwLogTraceEvent
0x1800223f0  test    byte ptr [rbx], 80h
0x1800223f3  jnz     short loc_180022438
0x1800223f5  lea     rsi, WPP_GLOBAL_Control
0x1800223fc  lea     r14, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids
0x180022403  mov     rcx, cs:WPP_GLOBAL_Control
0x18002240a  cmp     rcx, rsi
0x18002240d  jz      short loc_18002242C
0x18002240f  test    byte ptr [rcx+1Ch], 1
0x180022413  jz      short loc_18002242C
0x180022415  mov     edx, 11Ah
0x18002241a  mov     r9d, 4041FE4h
0x180022420  mov     r8, r14
0x180022423  mov     rcx, [rcx+10h]
0x180022427  call    WPP_SF_d
0x18002242c  mov     [rbp+0B90h+var_C0C], 10h
0x180022433  jmp     loc_180022339
0x180022438  mov     byte ptr [rbp+0B90h+var_BD0], r14b
0x18002243c  mov     [rbp+0B90h+var_C10], r14b
0x180022440  mov     rdx, rsi
0x180022443  mov     ecx, 0A7h
0x180022448  call    KerbFindPreAuthDataEntry
0x18002244d  test    rax, rax
0x180022450  jz      short loc_180022461
0x180022452  lea     rdx, [rbp+0B90h+var_BC0]; unsigned int *
0x180022456  mov     rcx, rax; struct KERB_PA_DATA *
0x180022459  call    ?KerbCheckPacOptionsPreAuthData@@YAJPEAUKERB_PA_DATA@@PEAK@Z; KerbCheckPacOptionsPreAuthData(KERB_PA_DATA *,ulong *)
0x18002245e  mov     [rbp+0B90h+var_C0C], eax
0x180022461  lea     r14, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids
0x180022468  xor     esi, esi
0x18002246a  cmp     [rbp+0B90h+var_C0C], esi
0x18002246d  jz      short loc_1800224A8
0x18002246f  lea     rsi, WPP_GLOBAL_Control
0x180022476  mov     rcx, cs:WPP_GLOBAL_Control
0x18002247d  cmp     rcx, rsi
  ... truncated ...
```
