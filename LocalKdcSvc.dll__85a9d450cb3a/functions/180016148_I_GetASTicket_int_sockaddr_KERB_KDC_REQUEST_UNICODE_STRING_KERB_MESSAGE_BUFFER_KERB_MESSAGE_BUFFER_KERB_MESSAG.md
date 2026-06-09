# I_GetASTicket(int,sockaddr *,KERB_KDC_REQUEST *,_UNICODE_STRING *,_KERB_MESSAGE_BUFFER *,_KERB_MESSAGE_BUFFER *,_KERB_MESSAGE_BUFFER *,KERB_EXT_ERROR *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,KrbFastReq *,_KERB_ENCRYPTION_KEY *,KERB_KDC_REQUEST_preauth_data_s * *,_KDC_AP_REQUEST_INFO *,_PDC_RSO *)

- ea: `0x180016148`
- end: `0x18001ab4f`
- name: `?I_GetASTicket@@YAJHPEAUsockaddr@@PEAUKERB_KDC_REQUEST@@PEAU_UNICODE_STRING@@PEAU_KERB_MESSAGE_BUFFER@@33PEAUKERB_EXT_ERROR@@222PEAUKrbFastReq@@PEAU_KERB_ENCRYPTION_KEY@@PEAPEAUKERB_KDC_REQUEST_preauth_data_s@@PEAU_KDC_AP_REQUEST_INFO@@PEAU_PDC_RSO@@@Z`
- size: `18951`
- prototype: `__int64 __fastcall(unsigned int, struct sockaddr *, struct KERB_KDC_REQUEST *, struct _UNICODE_STRING *, struct _KERB_MESSAGE_BUFFER *, struct _KERB_MESSAGE_BUFFER *, struct _KERB_MESSAGE_BUFFER *, struct KERB_EXT_ERROR *, PUNICODE_STRING DestinationString, struct _UNICODE_STRING *, struct _UNICODE_STRING *, struct KrbFastReq *, struct _KERB_ENCRYPTION_KEY *, struct KERB_KDC_REQUEST_preauth_data_s **, struct _KDC_AP_REQUEST_INFO *, struct _PDC_RSO *)`
- caller_count: `1`
- callee_count: `106`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001e930`

## callees

- `0x180001010`
- `0x1800010f0`
- `0x180002ad0`
- `0x180003908`
- `0x180005cc0`
- `0x18000a8d8`
- `0x18000ab24`
- `0x18000ab40`
- `0x18000add0`
- `0x18000b6ac`
- `0x18000be4c`
- `0x18000c25c`
- `0x18000c3d4`
- `0x18000cc5c`
- `0x18000e9a4`
- `0x1800101c4`
- `0x1800101ec`
- `0x18001022c`
- `0x180010f88`
- `0x180011a04`
- `0x18001318c`
- `0x18001371c`
- `0x1800138c4`
- `0x180013c1c`
- `0x180013d1c`
- `0x180013f24`
- `0x180014554`
- `0x180014c9c`
- `0x180015acc`
- `0x180016148`
- `0x18001ab58`
- `0x18001b3a0`
- `0x18001b5fc`
- `0x18001bb2c`
- `0x18001bd3c`
- `0x18001bf18`
- `0x18001c43c`
- `0x18001c848`
- `0x18001c944`
- `0x18001ca90`
- `0x18001cdc4`
- `0x18001ce44`
- `0x18001d260`
- `0x18001e194`
- `0x18001e41c`
- `0x18001e84c`
- `0x18001e888`
- `0x18001fc3c`
- `0x18001fc94`
- `0x18001fd80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017548`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017548`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001aaec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001aaec`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180018ea5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180018ea5`
- `CRYPT32!CertFreeCertificateChain` at `0x18001a8e7`
- `CRYPT32!CertFreeCertificateChain` at `0x18001a8e7`
- `CRYPT32!CertCloseStore` at `0x18001a9e6`
- `CRYPT32!CertCloseStore` at `0x18001a9e6`
- `CRYPT32!CertFreeCertificateContext` at `0x18001a8f5`
- `CRYPT32!CertFreeCertificateContext` at `0x18001a8f5`
- `CRYPT32!CertCreateCertificateContext` at `0x180016bca`
- `CRYPT32!CertCreateCertificateContext` at `0x180016bca`
- `ntdll!RtlEqualUnicodeString` at `0x1800170d0`
- `ntdll!RtlEqualUnicodeString` at `0x180018a6d`
- `ntdll!RtlEqualUnicodeString` at `0x180018a97`
- `ntdll!RtlEqualUnicodeString` at `0x1800170d0`
- `ntdll!RtlEqualUnicodeString` at `0x180018a6d`
- `ntdll!RtlEqualUnicodeString` at `0x180018a97`
- `ntdll!RtlInitUnicodeString` at `0x1800165bb`
- `ntdll!RtlInitUnicodeString` at `0x1800165bb`
- `ntdll!RtlAcquireResourceShared` at `0x180018e0c`
- `ntdll!RtlAcquireResourceShared` at `0x180018e0c`
- `ntdll!RtlReleaseResource` at `0x180018e20`
- `ntdll!RtlReleaseResource` at `0x180018e20`
- `ntdll!EtwLogTraceEvent` at `0x180016641`
- `ntdll!EtwLogTraceEvent` at `0x18001a71a`
- `ntdll!EtwLogTraceEvent` at `0x180016641`
- `ntdll!EtwLogTraceEvent` at `0x18001a71a`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x180016c07`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x180016e38`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x1800173b5`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x18001a907`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x18001a911`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x180016c07`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x180016e38`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x1800173b5`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x18001a907`
- `SAMSRV!SamIFree_UserInternal6Information` at `0x18001a911`
- `SAMSRV!SamrCloseHandle` at `0x180016c6b`
- `SAMSRV!SamrCloseHandle` at `0x180016e9c`
- `SAMSRV!SamrCloseHandle` at `0x18001741d`
- `SAMSRV!SamrCloseHandle` at `0x18001a8b0`
- `SAMSRV!SamrCloseHandle` at `0x180016c6b`
- `SAMSRV!SamrCloseHandle` at `0x180016e9c`
- `SAMSRV!SamrCloseHandle` at `0x18001741d`
- `SAMSRV!SamrCloseHandle` at `0x18001a8b0`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x180016c1c`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x180016e4d`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x1800173ca`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x18001a91e`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x180016c1c`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x180016e4d`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x1800173ca`
- `SAMSRV!SamIFreeSidAndAttributesList` at `0x18001a91e`
- `LSASRV!LsaIModifyPerformanceCounter` at `0x180016dc3`
- `LSASRV!LsaIModifyPerformanceCounter` at `0x1800190fa`
- `LSASRV!LsaIModifyPerformanceCounter` at `0x180016dc3`
- `LSASRV!LsaIModifyPerformanceCounter` at `0x1800190fa`
- `LSASRV!LsaIAuditKdcEvent` at `0x1800181e4`
- `LSASRV!LsaIAuditKdcEvent` at `0x1800187c6`
- `LSASRV!LsaIAuditKdcEvent` at `0x180019d94`
- `LSASRV!LsaIAuditKdcEvent` at `0x180019edc`
- `LSASRV!LsaIAuditKdcEvent` at `0x18001a33e`
- `LSASRV!LsaIAuditKdcEvent` at `0x1800181e4`
- `LSASRV!LsaIAuditKdcEvent` at `0x1800187c6`
- `LSASRV!LsaIAuditKdcEvent` at `0x180019d94`
- `LSASRV!LsaIAuditKdcEvent` at `0x180019edc`
- `LSASRV!LsaIAuditKdcEvent` at `0x18001a33e`
- `LSASRV!LsaIIsLastInteractiveLogonInfoEnabled` at `0x18001647a`
- `LSASRV!LsaIIsLastInteractiveLogonInfoEnabled` at `0x18001647a`

## pseudocode

```c
__int64 __fastcall I_GetASTicket(
        unsigned int a1,
        struct sockaddr *a2,
        struct KERB_KDC_REQUEST *a3,
        struct _UNICODE_STRING *a4,
        struct _KERB_MESSAGE_BUFFER *a5,
        struct _KERB_MESSAGE_BUFFER *a6,
        struct _KERB_MESSAGE_BUFFER *a7,
        struct KERB_EXT_ERROR *a8,
        PUNICODE_STRING DestinationString,
        struct _UNICODE_STRING *a10,
        struct _UNICODE_STRING *a11,
        struct KrbFastReq *a12,
        struct _KERB_ENCRYPTION_KEY *a13,
        struct KERB_KDC_REQUEST_preauth_data_s **a14,
        struct _KDC_AP_REQUEST_INFO *a15,
        struct _PDC_RSO *a16)
{
  int v17; // r14d
  __int64 v18; // rdx
  unsigned int v19; // esi
  struct KERB_KDC_REQUEST *v20; // rax
  __int64 v21; // r15
  char *v22; // rbx
  unsigned int v23; // eax
  struct KrbFastReq *v24; // r15
  struct _KERB_MESSAGE_BUFFER *v25; // r12
  struct _UNICODE_STRING *v26; // r13
  _QWORD *v27; // rsi
  int v28; // eax
  struct _UNICODE_STRING *v29; // rdi
  struct _KERB_INTERNAL_NAME *v30; // rbx
  int v31; // edi
  CSecurityData *v32; // r10
  struct KERB_PA_DATA *PreAuthDataEntry; // rax
  CSecurityData *v34; // r10
  struct KERB_ENCRYPTED_KDC_REPLY_encrypted_pa_data_s *v35; // r14
  unsigned int v36; // eax
  unsigned __int8 v37; // bl
  int v38; // r8d
  unsigned __int8 v39; // r13
  int v40; // r12d
  __m128i si128; // xmm6
  __m128i v42; // xmm7
  unsigned int v43; // r14d
  int v44; // eax
  CSecurityData *v45; // rcx
  struct KERB_EXT_ERROR *v46; // r8
  struct KERB_EXT_ERROR *v47; // r8
  struct KERB_KDC_REQUEST_preauth_data_s *v48; // r10
  struct KERB_EXT_ERROR *v49; // rax
  unsigned int v50; // edi
  int v51; // eax
  char v52; // al
  int v53; // eax
  __int64 v54; // rbx
  unsigned __int32 v55; // esi
  int v56; // eax
  struct KERB_EXT_ERROR *v57; // rax
  int v58; // eax
  int v59; // edi
  PCCERT_CONTEXT v60; // r15
  unsigned __int32 v61; // esi
  int v62; // eax
  CSecurityData *v63; // rcx
  unsigned int v64; // ebx
  __int64 v65; // rcx
  int v66; // eax
  struct KrbFastReq *v67; // rdx
  PCCERT_CONTEXT v68; // r15
  struct KERB_EXT_ERROR *v69; // r14
  char v70; // al
  const struct _CERT_CHAIN_CONTEXT *v71; // r12
  CSecurityData *v72; // rcx
  int v73; // eax
  DWORD LastError; // eax
  __int64 v75; // rdx
  __int64 v76; // r9
  CSecurityData *v77; // rcx
  unsigned int v78; // eax
  CSecurityData *v79; // rcx
  __int64 v80; // rdx
  __int64 v81; // r9
  CSecurityData *v82; // rcx
  int v83; // eax
  CSecurityData *v84; // rcx
  struct KERB_EXT_ERROR *v85; // r8
  CSecurityData *v86; // rcx
  __int64 v87; // rdx
  __int64 v88; // r9
  unsigned int v89; // eax
  int v90; // edx
  struct _UNICODE_STRING *v91; // rax
  int v92; // r9d
  __int64 *v93; // rax
  Ntlmless::Kerberos *v94; // rcx
  KerberosCryptoPolicy *v95; // rsi
  CSecurityData *v96; // rcx
  __int64 v97; // rdx
  struct _KERB_INTERNAL_NAME *v98; // r9
  struct _USER_INTERNAL6_INFORMATION *v99; // r8
  struct KERB_KDC_REQUEST_preauth_data_s *v100; // r13
  struct _PDC_RSO *v101; // r14
  const CERT_CONTEXT *v102; // r12
  int v103; // r14d
  struct _KERB_INTERNAL_NAME *v104; // r15
  struct _KDC_S4U_TICKET_INFO *v105; // r9
  int v106; // ebx
  int v107; // r8d
  unsigned __int8 *v108; // rdx
  struct KERB_ENCRYPTED_TICKET *v109; // rax
  int v110; // eax
  CSecurityData *v111; // r10
  int v112; // ecx
  struct KERB_EXT_ERROR *v113; // r14
  struct KERB_KDC_REQUEST_BODY *v114; // rsi
  struct sockaddr *v115; // r15
  int v116; // edi
  int v117; // r10d
  CSecurityData *v118; // rcx
  int v119; // r8d
  struct sockaddr_storage *v120; // rax
  struct _PDC_RSO *v121; // rbx
  struct KERB_EXT_ERROR *v122; // r14
  struct KERB_KDC_REQUEST_BODY *v123; // rbx
  struct _PDC_RSO *v124; // rdi
  int v125; // ecx
  struct sockaddr *v126; // rdi
  struct sockaddr *v127; // rax
  int v128; // r8d
  bool v129; // bl
  bool v130; // dl
  struct _USER_INTERNAL6_INFORMATION **v131; // rcx
  int v132; // eax
  CSecurityData *v133; // rcx
  __int64 v134; // rdx
  __int64 v135; // r9
  __int64 *v136; // rax
  KerberosCryptoPolicy *v137; // rdi
  struct KERB_KDC_REQUEST_BODY *v138; // rbx
  _QWORD *i; // rcx
  _DWORD *v140; // rax
  union _LARGE_INTEGER v141; // rbx
  CSecurityData *v142; // rcx
  struct _USER_ALL_INFORMATION *v143; // rdx
  union _LARGE_INTEGER v144; // rcx
  union _LARGE_INTEGER v145; // rax
  __int64 v146; // rcx
  union _LARGE_INTEGER v147; // rcx
  union _LARGE_INTEGER v148; // rax
  struct KERB_EXT_ERROR *v149; // rbx
  int v150; // eax
  int v151; // r8d
  CSecurityData *v152; // rcx
  __int64 v153; // rdx
  __int64 v154; // r9
  int v155; // r14d
  struct _KDC_S4U_TICKET_INFO *v156; // r9
  CSecurityData *v157; // rcx
  int v158; // ebx
  bool IsAnyKrbtgt; // r8
  char v160; // bl
  char v161; // cl
  int PacAuthData; // eax
  unsigned int v163; // ebx
  CSecurityData *v164; // rcx
  __int64 v165; // rdx
  __int64 v166; // r9
  unsigned __int8 *v167; // rdx
  int v168; // eax
  struct PKERB_HOST_ADDRESSES_s *v169; // rax
  unsigned int v170; // edx
  _DWORD *v171; // rax
  _DWORD *v172; // rbx
  _DWORD *v173; // rax
  struct KERB_KDC_REQUEST_preauth_data_s *v174; // rax
  unsigned int v175; // ebx
  unsigned int v176; // eax
  struct KERB_KDC_REQUEST_preauth_data_s *v177; // r12
  __int64 v178; // rcx
  unsigned __int8 v179; // bl
  KerberosCryptoPolicy *v180; // rdx
  int v181; // eax
  struct _KERB_ENCRYPTION_KEY *v182; // rdi
  struct _KERB_ENCRYPTION_KEY *Key; // rax
  __int64 *v184; // rdx
  __int64 *v185; // rax
  struct KerberosCryptoPolicy *v186; // rbx
  unsigned int v187; // r8d
  unsigned int v188; // r8d
  void *v189; // rbx
  unsigned int v190; // edi
  CSecurityData *v191; // rcx
  struct sockaddr *v192; // rcx
  struct sockaddr *v193; // rax
  CSecurityData *v194; // rcx
  __int64 v195; // rdx
  struct sockaddr *v196; // rbx
  struct sockaddr *v197; // rcx
  struct _KERB_INTERNAL_NAME *v198; // rdx
  int v199; // edi
  int v200; // ecx
  struct KERB_KDC_REQUEST_preauth_data_s *v201; // rcx
  struct KERB_KDC_REQUEST_preauth_data_s *v202; // rax
  _DWORD *v203; // rdi
  void **v204; // rbx
  unsigned int v205; // r9d
  struct _UNICODE_STRING *v206; // rdi
  USHORT Length; // cx
  struct _UNICODE_STRING *v208; // rax
  struct _UNICODE_STRING *v209; // rbx
  USHORT v210; // cx
  struct _UNICODE_STRING *v211; // rax
  struct _UNICODE_STRING *v212; // rax
  USHORT v213; // cx
  unsigned int v214; // r9d
  BOOL v215; // ebx
  __int64 v216; // rcx
  __int64 v217; // r8
  void *v218; // rcx
  void **v219; // r14
  struct KERB_ENCRYPTED_KDC_REPLY_encrypted_pa_data_s *v220; // rbx
  HLOCAL v221; // rcx
  bool v222; // zf
  union _LARGE_INTEGER *v224; // [rsp+28h] [rbp-150h]
  union _LARGE_INTEGER *v225; // [rsp+30h] [rbp-148h]
  struct _UNICODE_STRING *v226; // [rsp+38h] [rbp-140h]
  struct _KDC_AP_REQUEST_INFO *v227; // [rsp+40h] [rbp-138h]
  struct _KDC_PKI_AUDIT_INFO *v228; // [rsp+48h] [rbp-130h]
  unsigned int v229; // [rsp+50h] [rbp-128h]
  struct KERB_EXT_ERROR *v230; // [rsp+58h] [rbp-120h]
  unsigned int v231; // [rsp+68h] [rbp-110h]
  unsigned int v232; // [rsp+68h] [rbp-110h]
  unsigned int v233; // [rsp+70h] [rbp-108h]
  struct _UNICODE_STRING *v234; // [rsp+78h] [rbp-100h]
  int ClientNetbiosAddress; // [rsp+F8h] [rbp-80h] BYREF
  struct _UNICODE_STRING *v236; // [rsp+100h] [rbp-78h]
  void *v237; // [rsp+108h] [rbp-70h]
  struct _KERB_MESSAGE_BUFFER *v238; // [rsp+110h] [rbp-68h]
  struct KrbFastReq *v239; // [rsp+118h] [rbp-60h]
  char v240[8]; // [rsp+120h] [rbp-58h] BYREF
  char v241; // [rsp+128h] [rbp-50h]
  char v242; // [rsp+129h] [rbp-4Fh]
  struct _USER_INTERNAL6_INFORMATION *v243; // [rsp+130h] [rbp-48h] BYREF
  struct _KERB_INTERNAL_NAME *v244; // [rsp+138h] [rbp-40h] BYREF
  char v245; // [rsp+140h] [rbp-38h]
  char v246; // [rsp+141h] [rbp-37h]
  __int64 v247; // [rsp+144h] [rbp-34h] BYREF
  void *v248; // [rsp+150h] [rbp-28h] BYREF
  char v249; // [rsp+158h] [rbp-20h]
  unsigned int v250[3]; // [rsp+15Ch] [rbp-1Ch] BYREF
  struct KERB_EXT_ERROR *v251; // [rsp+168h] [rbp-10h]
  PCCERT_CONTEXT pCertContext; // [rsp+170h] [rbp-8h] BYREF
  __int16 v253; // [rsp+178h] [rbp+0h] BYREF
  unsigned int v254; // [rsp+17Ch] [rbp+4h] BYREF
  struct KERB_KDC_REQUEST_preauth_data_s *v255; // [rsp+180h] [rbp+8h] BYREF
  struct sockaddr *v256; // [rsp+188h] [rbp+10h]
  unsigned int v257; // [rsp+190h] [rbp+18h]
  int v258; // [rsp+194h] [rbp+1Ch] BYREF
  int v259; // [rsp+198h] [rbp+20h] BYREF
  unsigned int v260; // [rsp+19Ch] [rbp+24h] BYREF
  struct _UNICODE_STRING *v261; // [rsp+1A0h] [rbp+28h]
  unsigned int v262; // [rsp+1A8h] [rbp+30h] BYREF
  int v263; // [rsp+1ACh] [rbp+34h]
  unsigned __int8 v264[8]; // [rsp+1B0h] [rbp+38h] BYREF
  __int64 v265; // [rsp+1B8h] [rbp+40h] BYREF
  struct KERB_KDC_REQUEST_BODY *v266; // [rsp+1C0h] [rbp+48h]
  unsigned int v267; // [rsp+1C8h] [rbp+50h] BYREF
  struct _UNICODE_STRING *v268; // [rsp+1D0h] [rbp+58h]
  unsigned int v269; // [rsp+1D8h] [rbp+60h] BYREF
  struct _PDC_RSO *v270; // [rsp+1E0h] [rbp+68h]
  struct KerberosCryptoPolicy *v271; // [rsp+1E8h] [rbp+70h] BYREF
  __int64 v272; // [rsp+1F0h] [rbp+78h] BYREF
  union _LARGE_INTEGER v273; // [rsp+1F8h] [rbp+80h] BYREF
  struct _KERB_MESSAGE_BUFFER *v274; // [rsp+200h] [rbp+88h]
  __int64 v275; // [rsp+208h] [rbp+90h] BYREF
  __int16 *v276; // [rsp+210h] [rbp+98h]
  char v277; // [rsp+218h] [rbp+A0h]
  unsigned int v278; // [rsp+220h] [rbp+A8h]
  _DWORD v279[3]; // [rsp+224h] [rbp+ACh] BYREF
  struct _KERB_ENCRYPTION_KEY *v280; // [rsp+230h] [rbp+B8h]
  struct _UNICODE_STRING v281; // [rsp+238h] [rbp+C0h] BYREF
  PCCERT_CHAIN_CONTEXT pChainContext; // [rsp+248h] [rbp+D0h] BYREF
  HCERTSTORE hCertStore; // [rsp+250h] [rbp+D8h] BYREF
  struct KERB_ENCRYPTED_KDC_REPLY_encrypted_pa_data_s *v284; // [rsp+258h] [rbp+E0h] BYREF
  struct _UNICODE_STRING v285; // [rsp+260h] [rbp+E8h] BYREF
  unsigned int v286; // [rsp+270h] [rbp+F8h]
  unsigned int v287; // [rsp+274h] [rbp+FCh]
  unsigned int Target; // [rsp+278h] [rbp+100h]
  union _LARGE_INTEGER v289; // [rsp+280h] [rbp+108h] BYREF
  union _LARGE_INTEGER v290; // [rsp+288h] [rbp+110h] BYREF
  struct _UNICODE_STRING *v291; // [rsp+290h] [rbp+118h]
  void *v292; // [rsp+298h] [rbp+120h]
  struct _UNICODE_STRING *v293; // [rsp+2A0h] [rbp+128h] BYREF
  KerberosCryptoPolicy *v294; // [rsp+2A8h] [rbp+130h] BYREF
  KerberosCryptoPolicy *v295; // [rsp+2B0h] [rbp+138h] BYREF
  __int128 v296; // [rsp+2B8h] [rbp+140h] BYREF
  union _LARGE_INTEGER v297; // [rsp+2C8h] [rbp+150h] BYREF
  void *v298; // [rsp+2D0h] [rbp+158h]
  struct KERB_KDC_REQUEST_preauth_data_s *v299; // [rsp+2D8h] [rbp+160h] BYREF
  __int64 v300; // [rsp+2E0h] [rbp+168h] BYREF
  struct _KERB_INTERNAL_NAME *v301; // [rsp+2E8h] [rbp+170h] BYREF
  struct _KERB_INTERNAL_NAME *v302; // [rsp+2F0h] [rbp+178h] BYREF
  __m128i v303; // [rsp+2F8h] [rbp+180h] BYREF
  struct _UNICODE_STRING v304; // [rsp+308h] [rbp+190h] BYREF
  char v305[28]; // [rsp+318h] [rbp+1A0h] BYREF
  int v306; // [rsp+334h] [rbp+1BCh]
  unsigned int v307; // [rsp+338h] [rbp+1C0h]
  int v308; // [rsp+344h] [rbp+1CCh]
  struct _KERB_STORED_CREDENTIAL *v309; // [rsp+348h] [rbp+1D0h]
  int v310; // [rsp+359h] [rbp+1E1h]
  __int16 v311; // [rsp+35Dh] [rbp+1E5h]
  char v312; // [rsp+35Fh] [rbp+1E7h]
  unsigned int v313; // [rsp+368h] [rbp+1F0h]
  __int16 v314; // [rsp+371h] [rbp+1F9h]
  char v315; // [rsp+373h] [rbp+1FBh]
  int v316; // [rsp+378h] [rbp+200h]
  int v317; // [rsp+37Ch] [rbp+204h]
  __int64 v318; // [rsp+380h] [rbp+208h]
  __int64 v319; // [rsp+3A0h] [rbp+228h] BYREF
  __int128 v320; // [rsp+3A8h] [rbp+230h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+3B8h] [rbp+240h] BYREF
  __int64 v322; // [rsp+3C0h] [rbp+248h]
  __int64 v323; // [rsp+3C8h] [rbp+250h]
  unsigned __int8 *v324; // [rsp+3D0h] [rbp+258h] BYREF
  int v325; // [rsp+3D8h] [rbp+260h] BYREF
  int v326; // [rsp+3DCh] [rbp+264h] BYREF
  __int64 v327[2]; // [rsp+3E0h] [rbp+268h] BYREF
  HLOCAL hMem; // [rsp+3F0h] [rbp+278h]
  union _LARGE_INTEGER v329; // [rsp+3F8h] [rbp+280h] BYREF
  void *v330; // [rsp+400h] [rbp+288h]
  __int64 v331[2]; // [rsp+408h] [rbp+290h] BYREF
  __int128 v332; // [rsp+418h] [rbp+2A0h]
  __int64 v333; // [rsp+428h] [rbp+2B0h]
  __int16 v334; // [rsp+438h] [rbp+2C0h] BYREF
  _BYTE v335[14]; // [rsp+43Ah] [rbp+2C2h] BYREF
  _BYTE v336[16]; // [rsp+448h] [rbp+2D0h] BYREF
  _BYTE v337[48]; // [rsp+458h] [rbp+2E0h] BYREF
  __int128 v338; // [rsp+488h] [rbp+310h] BYREF
  void *v339[2]; // [rsp+498h] [rbp+320h] BYREF
  struct _UNICODE_STRING v340; // [rsp+4A8h] [rbp+330h] BYREF
  __int64 v341[2]; // [rsp+4B8h] [rbp+340h] BYREF
  __int128 v342; // [rsp+4C8h] [rbp+350h]
  __int64 v343; // [rsp+4D8h] [rbp+360h]
  __int128 v344; // [rsp+4E0h] [rbp+368h] BYREF
  __int128 v345; // [rsp+4F0h] [rbp+378h]
  __m128i v346; // [rsp+500h] [rbp+388h] BYREF
  __m128i v347; // [rsp+510h] [rbp+398h]
  __int64 v348[2]; // [rsp+528h] [rbp+3B0h] BYREF
  char v349[32]; // [rsp+538h] [rbp+3C0h] BYREF
  unsigned int v350; // [rsp+558h] [rbp+3E0h]
  int v351; // [rsp+564h] [rbp+3ECh]
  int v352; // [rsp+579h] [rbp+401h]
  __int16 v353; // [rsp+57Dh] [rbp+405h]
  char v354; // [rsp+57Fh] [rbp+407h]
  unsigned int v355[2]; // [rsp+588h] [rbp+410h] BYREF
  char v356; // [rsp+590h] [rbp+418h]
  __int16 v357; // [rsp+591h] [rbp+419h]
  char v358; // [rsp+593h] [rbp+41Bh]
  int v359; // [rsp+594h] [rbp+41Ch]
  int v360; // [rsp+598h] [rbp+420h]
  int v361; // [rsp+59Ch] [rbp+424h]
  __int64 v362; // [rsp+5C0h] [rbp+448h] BYREF
  __int128 v363; // [rsp+5C8h] [rbp+450h]
  __int128 v364; // [rsp+5D8h] [rbp+460h] BYREF
  void *v365; // [rsp+5E8h] [rbp+470h]
  struct _UNICODE_STRING v366; // [rsp+5F0h] [rbp+478h] BYREF
  __int16 v367; // [rsp+608h] [rbp+490h] BYREF
  char v368[2]; // [rsp+60Ah] [rbp+492h] BYREF
  char v369; // [rsp+60Ch] [rbp+494h]
  __int128 v370; // [rsp+620h] [rbp+4A8h]
  int v371; // [rsp+634h] [rbp+4BCh]
  int *p_ClientNetbiosAddress; // [rsp+638h] [rbp+4C0h]
  int v373; // [rsp+640h] [rbp+4C8h]
  struct _UNICODE_STRING *v374; // [rsp+648h] [rbp+4D0h]
  int v375; // [rsp+650h] [rbp+4D8h]
  PWSTR Buffer; // [rsp+658h] [rbp+4E0h]
  int v377; // [rsp+660h] [rbp+4E8h]
  struct _UNICODE_STRING *v378; // [rsp+668h] [rbp+4F0h]
  int v379; // [rsp+670h] [rbp+4F8h]
  PWSTR v380; // [rsp+678h] [rbp+500h]
  int v381; // [rsp+680h] [rbp+508h]
  struct _UNICODE_STRING *v382; // [rsp+688h] [rbp+510h]
  int v383; // [rsp+690h] [rbp+518h]
  PWSTR v384; // [rsp+698h] [rbp+520h]
  int v385; // [rsp+6A0h] [rbp+528h]
  _OWORD v386[2]; // [rsp+6A8h] [rbp+530h] BYREF
  __int64 v387; // [rsp+6C8h] [rbp+550h]
  _WORD v388[2]; // [rsp+6D8h] [rbp+560h] BYREF
  int v389; // [rsp+6DCh] [rbp+564h]
  int v390; // [rsp+6E0h] [rbp+568h]
  void *v391; // [rsp+6E8h] [rbp+570h]
  __int64 v392; // [rsp+6F0h] [rbp+578h]
  __int128 v393; // [rsp+6F8h] [rbp+580h]
  __int64 v394[4]; // [rsp+708h] [rbp+590h] BYREF
  int v395; // [rsp+72Ch] [rbp+5B4h]
  unsigned int v396; // [rsp+738h] [rbp+5C0h]
  unsigned __int8 *v397; // [rsp+740h] [rbp+5C8h]
  char v398[4]; // [rsp+750h] [rbp+5D8h] BYREF
  unsigned int v399; // [rsp+754h] [rbp+5DCh]
  _OWORD v400[2]; // [rsp+778h] [rbp+600h] BYREF
  __int64 v401; // [rsp+798h] [rbp+620h]
  char v402[8]; // [rsp+7A8h] [rbp+630h] BYREF
  char *v403; // [rsp+7B0h] [rbp+638h]
  char v404[20]; // [rsp+7B8h] [rbp+640h] BYREF
  unsigned int v405; // [rsp+7CCh] [rbp+654h]
  __int16 *v406; // [rsp+7E0h] [rbp+668h]
  _QWORD v407[2]; // [rsp+7F8h] [rbp+680h] BYREF
  char v408[44]; // [rsp+808h] [rbp+690h] BYREF
  int v409; // [rsp+834h] [rbp+6BCh]
  int v410; // [rsp+849h] [rbp+6D1h]
  __int16 v411; // [rsp+84Dh] [rbp+6D5h]
  char v412; // [rsp+84Fh] [rbp+6D7h]
  __int16 v413; // [rsp+861h] [rbp+6E9h]
  char v414; // [rsp+863h] [rbp+6EBh]
  int v415; // [rsp+86Ch] [rbp+6F4h]
  struct KERB_ENCRYPTED_KDC_REPLY_encrypted_pa_data_s *v416; // [rsp+890h] [rbp+718h] BYREF
  __int128 v417; // [rsp+898h] [rbp+720h]
  _BYTE v418[48]; // [rsp+8A8h] [rbp+730h] BYREF
  __int64 v419; // [rsp+8D8h] [rbp+760h]
  _BYTE v420[48]; // [rsp+8E0h] [rbp+768h] BYREF
  __int64 v421; // [rsp+910h] [rbp+798h]
  __int64 v422; // [rsp+918h] [rbp+7A0h] BYREF
  int v423; // [rsp+920h] [rbp+7A8h]
  int v424; // [rsp+958h] [rbp+7E0h]
  int *v425; // [rsp+960h] [rbp+7E8h]
  struct KERB_KDC_REQUEST_preauth_data_s *v426; // [rsp+9C0h] [rbp+848h]
  __int16 v427; // [rsp+9C8h] [rbp+850h] BYREF
  int v428; // [rsp+9D0h] [rbp+858h]
  int *v429; // [rsp+9D8h] [rbp+860h]
  __int64 v430; // [rsp+9F8h] [rbp+880h]
  __int128 v431; // [rsp+A00h] [rbp+888h]
  void *v432; // [rsp+A68h] [rbp+8F0h]
  unsigned __int8 Sid[48]; // [rsp+A78h] [rbp+900h] BYREF
  __int64 v434; // [rsp+AA8h] [rbp+930h]
  __int64 v435[10]; // [rsp+AC8h] [rbp+950h] BYREF
  int v436[20]; // [rsp+B18h] [rbp+9A0h] BYREF
  _BYTE v437[80]; // [rsp+B68h] [rbp+9F0h] BYREF

  v261 = a4;
  v256 = a2;
  v267 = a1;
  v239 = a12;
  v236 = a11;
  v291 = a10;
  v322 = (__int64)a7;
  v274 = a5;
  v270 = a16;
  v251 = a8;
  v238 = a6;
  v268 = DestinationString;
  v280 = a13;
  v323 = (__int64)a14;
  v275 = (__int64)a15;
  ClientNetbiosAddress = 0;
  v247 = 0;
  *(_DWORD *)&v240[4] = 0;
  *(_QWORD *)&v304.Length = 0;
  v304.Buffer = 0;
  v308 = 0;
  v310 = 0;
  v311 = 0;
  v312 = 0;
  v314 = 0;
  v315 = 0;
  v317 = 0;
  memset_0(v305, 0, 0x88u);
  v319 = 0;
  v320 = 0;
  v348[0] = 0;
  v348[1] = 0;
  v351 = 0;
  v352 = 0;
  v353 = 0;
  v354 = 0;
  v357 = 0;
  v358 = 0;
  v361 = 0;
  memset_0(v349, 0, 0x88u);
  v362 = 0;
  v363 = 0;
  v248 = 0;
  v243 = 0;
  v300 = 0;
  v296 = 0;
  *(_OWORD *)v331 = 0;
  v332 = 0;
  v333 = 0;
  memset(v386, 0, sizeof(v386));
  v387 = 0;
  memset(v400, 0, sizeof(v400));
  v401 = 0;
  v254 = 0;
  memset_0(v402, 0, 0x48u);
  memset_0(&v427, 0, 0xA8u);
  memset_0(&v422, 0, 0xB0u);
  memset_0(v388, 0, 0x98u);
  v292 = 0;
  v298 = 0;
  v255 = 0;
  v284 = 0;
  v334 = 0;
  memset_0(v335, 0, 0x4Eu);
  v265 = 0x3C00000000LL;
  v244 = 0;
  v301 = 0;
  v302 = 0;
  *(_OWORD *)v341 = 0;
  v342 = 0;
  LOBYTE(v341[0]) = 0;
  v343 = 0;
  v285 = 0;
  v366 = 0;
  v340 = 0;
  v290.QuadPart = 0;
  v289.QuadPart = 0;
  v329.QuadPart = 0;
  v273.QuadPart = 0;
  v297.QuadPart = 0;
  SystemTimeAsFileTime = 0;
  v250[0] = 0;
  v326 = 0;
  v325 = 0;
  v17 = 0;
  v260 = 0;
  v250[1] = 0;
  v262 = 0;
  if ( (unsigned int)KdcIsLHFunctionalLevel()
    && ((unsigned int)LsaIIsLastInteractiveLogonInfoEnabled() || KdcGlobalEmitLILI) )
  {
    v19 = 570425857;
  }
  else
  {
    v19 = 570425345;
  }
  v257 = v19;
  LOBYTE(v18) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_DMSAKDC>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_DMSAKDC>::GetImpl'::`2'::impl,
    v18);
  v241 = 0;
  v245 = 0;
  v240[1] = 0;
  v264[0] = 0;
  v246 = 0;
  LOBYTE(v253) = 0;
  v240[0] = 0;
  v242 = 0;
  v367 = 0;
  memset_0(v368, 0, 0x9Eu);
  pCertContext = 0;
  pChainContext = 0;
  *(_OWORD *)v327 = 0;
  hMem = 0;
  hCertStore = 0;
  v330 = 0;
  v338 = 0;
  *(_OWORD *)v339 = 0;
  v364 = 0;
  v365 = 0;
  v344 = 0;
  v345 = 0;
  v237 = 0;
  v299 = 0;
  v324 = 0;
  v269 = 0;
  v293 = 0;
  Target = 1;
  v258 = 0;
  v286 = 0;
  v287 = 0;
  v278 = 0;
  v295 = 0;
  v294 = 0;
  v271 = 0;
  v429 = &v326;
  v428 = 32;
  v425 = &v325;
  v424 = 32;
  RtlInitUnicodeString(DestinationString, 0);
  v406 = &v427;
  v20 = a12;
  if ( !a12 )
    v20 = a3;
  v21 = *((_QWORD *)v20 + 2);
  *(_QWORD *)&v279[1] = v21;
  v22 = (char *)v20 + 24;
  v266 = (struct KERB_KDC_REQUEST *)((char *)v20 + 24);
  v23 = KerbConvertFlagsToUlong((struct KERB_KDC_REQUEST *)((char *)v20 + 32));
  HIDWORD(v247) = v23;
  if ( KdcEventTraceFlag )
  {
    v370 = KdcGetASTicketGuid;
    v369 = 1;
    v371 = 0x20000;
    v367 = 52;
    LODWORD(p_ClientNetbiosAddress) = v23;
    EtwLogTraceEvent(KdcTraceLoggerHandle, &v367);
  }
  if ( (*v22 & 8) != 0 && !*((_QWORD *)v22 + 15) )
    goto LABEL_12;
  if ( *v22 >= 0 )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 89, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids, 67310020);
    ClientNetbiosAddress = 6;
    goto LABEL_647;
  }
  ClientNetbiosAddress = KerbConvertPrincipalNameToKdcName(&v244, (struct KERB_PRINCIPAL_NAME *)(v22 + 24));
  if ( ClientNetbiosAddress )
    goto LABEL_647;
  v29 = v291;
  ClientNetbiosAddress = KerbConvertKdcNameToString(v291, v244, 0);
  if ( ClientNetbiosAddress )
    goto LABEL_647;
  if ( (v247 & 0xA940000B00000000uLL) != 0 )
  {
LABEL_12:
    ClientNetbiosAddress = 13;
    goto LABEL_13;
  }
  if ( (*v22 & 0x40) == 0 )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_DZ(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        90,
        (unsigned int)WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids,
        67310048,
        (__int64)v29);
    if ( (KDCInfoLevel & 0x10000000) != 0 )
    {
      *(_DWORD *)a8 = -1073741061;
      *((_DWORD *)a8 + 1) = 67310049;
      *((_DWORD *)a8 + 2) = 2;
    }
    goto LABEL_12;
  }
  ClientNetbiosAddress = KerbConvertPrincipalNameToKdcName(&v302, (struct KERB_PRINCIPAL_NAME *)(v22 + 48));
  if ( ClientNetbiosAddress )
    goto LABEL_647;
  v30 = v302;
  ClientNetbiosAddress = KerbConvertKdcNameToString(a11, v302, 0);
  if ( ClientNetbiosAddress )
    goto LABEL_647;
  v31 = (HIDWORD(v247) >> 12) & 0x10;
  v32 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF__KERB_NAME_(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids, v30);
      v32 = WPP_GLOBAL_Control;
    }
    if ( v32 != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)v32 + 28) & 4) != 0 )
      WPP_SF__KERB_NAME_(*((_QWORD *)v32 + 2), 92, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids, v244);
  }
  PreAuthDataEntry = (struct KERB_PA_DATA *)KerbFindPreAuthDataEntry(167, v21);
  if ( PreAuthDataEntry )
  {
    ClientNetbiosAddress = KerbCheckPacOptionsPreAuthData(PreAuthDataEntry, &v250[1]);
    v34 = WPP_GLOBAL_Control;
    v17 = v250[1];
    v260 = v250[1];
  }
  if ( ClientNetbiosAddress )
  {
    if ( v34 != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)v34 + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)v34 + 2), 93, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids);
    goto LABEL_647;
  }
  if ( KdcGlobalCDC && (v17 & 0x20000000) != 0 )
  {
    if ( v34 != (CSecurityData *)&WPP_GLOBAL_Control && (*((_DWORD *)v34 + 7) & 0x40000) != 0 )
      WPP_SF_(*((_QWORD *)v34 + 2), 94, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids);
    v25 = v238;
    ClientNetbiosAddress = KdcForwardMessage(2, 0, 0, v274, v238);
    LODWORD(v35) = 0;
    if ( ClientNetbiosAddress )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 95, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids);
      ClientNetbiosAddress = 29;
    }
    goto LABEL_649;
  }
  v36 = KdcGlobalDomainClaimsLevel;
  if ( KdcGlobalDomainClaimsLevel == 2 )
  {
    if ( (unsigned int)KdcIsWin8FunctionalLevel() )
    {
LABEL_55:
      v37 = 1;
      v249 = 1;
      goto LABEL_56;
    }
    v36 = KdcGlobalDomainClaimsLevel;
  }
  v37 = 0;
  v249 = 0;
  if ( v36 && v17 < 0 )
    goto LABEL_55;
LABEL_56:
  if ( KerbFindPreAuthDataEntry(15, v21) || KerbFindPreAuthDataEntry(16, v21) )
  {
    v259 = v38;
    v19 |= 0x80u;
    v39 = v38;
  }
  else
  {
    v259 = 0;
    v39 = 0;
    if ( !KerbFindPreAuthDataEntry(138, v21) && !KerbFindPreAuthDataEntry(2, v21) )
    {
      v31 |= 0x40u;
      v259 = 7;
      goto LABEL_63;
    }
  }
  v257 = v19;
LABEL_63:
  v263 = v31;
  if ( (*(_BYTE *)v266 & 8) != 0 )
  {
    ClientNetbiosAddress = KerbGetClientNetbiosAddress(&v285, *((struct PKERB_HOST_ADDRESSES_s **)v266 + 15));
    if ( ClientNetbiosAddress )
      goto LABEL_647;
  }
  v40 = 0;
  *(_QWORD *)&v281.Length = KerbFindPreAuthDataEntry(130, v21);
  v250[1] = 8 * v37;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v42 = _mm_load_si128((const __m128i *)&_xmm);
  while ( 1 )
  {
    v43 = IsSubAuthFilterPresent() ? 0x3FFFFFFF : 557838287;
    v44 = KdcNormalize(
            v244,
            0,
            v261,
            0,
            v31 | (v242 != 0 ? 533 : 21),
            v250[1] | (4 * v39),
            (struct _SAM_MAPPED_ATTRIBUTE_SET *)v293,
            (unsigned __int8 *)&v240[1],
            v268,
            (struct _KDC_TICKET_INFO *)&v304,
            v251,
            &v248,
            v43,
            v19,
            &v243,
            (struct _SID_AND_ATTRIBUTES_LIST *)&v296);
    ClientNetbiosAddress = v44;
    if ( KdcGlobalCDC && v44 == -2147483642 )
    {
      v72 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control )
      {
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 96, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids);
          v72 = WPP_GLOBAL_Control;
        }
        if ( v72 != (CSecurityData *)&WPP_GLOBAL_Control && (*((_DWORD *)v72 + 7) & 0x40000) != 0 )
          WPP_SF__KERB_NAME_(*((_QWORD *)v72 + 2), 97, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids, v244);
      }
      v231 = v43;
      LODWORD(v35) = 0;
      v73 = KdcNormalize(
              v244,
              0,
              v261,
              0,
              v31 | 0x15u,
              2u,
              0,
              (unsigned __int8 *)&v240[1],
              v268,
              (struct _KDC_TICKET_INFO *)&v304,
              v251,
              &v248,
              v231,
              0,
              &v243,
              0);
      v27 = v237;
      v26 = v236;
      v24 = v239;
      v25 = v238;
      if ( v73 )
        ClientNetbiosAddress = v73;
      goto LABEL_652;
    }
    if ( !v44 )
    {
      v66 = v316;
      v45 = WPP_GLOBAL_Control;
      LODWORD(v35) = 0;
      goto LABEL_143;
    }
    v45 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          98,
          WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids,
          67310277,
          ClientNetbiosAddress);
        v45 = WPP_GLOBAL_Control;
      }
      if ( v45 != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)v45 + 28) & 1) != 0 )
      {
        WPP_SF__KERB_NAME_(*((_QWORD *)v45 + 2), 99, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids, v244);
        v45 = WPP_GLOBAL_Control;
      }
    }
    if ( ClientNetbiosAddress == 6 )
    {
      if ( *(_WORD *)v244 != 6 )
        goto LABEL_13;
      v46 = v251;
      *(_QWORD *)v251 = 0;
      *((_DWORD *)v46 + 2) = 0;
      if ( pCertContext )
        goto LABEL_83;
      if ( KerbFindPreAuthDataEntry(16, *(_QWORD *)&v279[1]) )
      {
        ClientNetbiosAddress = KdcVerifyAuthPackSignature(
                                 v48,
                                 0,
                                 &pCertContext,
                                 (struct KdcPackedAuthenticator *)v327,
                                 v47,
                                 &hCertStore,
                                 &v255);
        if ( ClientNetbiosAddress )
          goto LABEL_647;
        goto LABEL_83;
      }
      if ( *(_QWORD *)&v281.Length )
      {
        pCertContext = CertCreateCertificateContext(
                         0x10001u,
                         *(const BYTE **)(*(_QWORD *)&v281.Length + 16LL),
                         *(_DWORD *)(*(_QWORD *)&v281.Length + 8LL));
        if ( pCertContext )
        {
LABEL_83:
          KerbFreeSid(&v244);
          ClientNetbiosAddress = KerbGetCertificatePublicKey(pCertContext, &v244);
          if ( ClientNetbiosAddress )
            goto LABEL_647;
          if ( v243 )
          {
            ((void (*)(void))SamIFree_UserInternal6Information)();
            v243 = 0;
          }
          SamIFreeSidAndAttributesList(&v296);
          v296 = 0;
          FreeTicketInfo((struct _KDC_TICKET_INFO *)&v304);
          memset_0(&v304, 0, 0xB0u);
          KerbFreeString(v268);
          v49 = v251;
          *(_QWORD *)v251 = 0;
          *((_DWORD *)v49 + 2) = 0;
          if ( v248 )
          {
            SamrCloseHandle(&v248);
            v248 = 0;
          }
          if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
          {
            WPP_SF__KERB_NAME_(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              103,
              WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids,
              v244);
          }
          v50 = v31 | 0x215;
          v51 = KdcNormalize(
                  v244,
                  0,
                  v261,
                  0,
                  v50,
                  v250[1] | (4 * v39),
                  (struct _SAM_MAPPED_ATTRIBUTE_SET *)v293,
                  (unsigned __int8 *)&v240[1],
                  v268,
                  (struct _KDC_TICKET_INFO *)&v304,
                  v251,
                  &v248,
                  v43,
                  v19,
                  &v243,
                  (struct _SID_AND_ATTRIBUTES_LIST *)&v296);
          ClientNetbiosAddress = v51;
          if ( KdcGlobalCDC && v51 == -2147483642 )
          {
            v82 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control )
            {
              if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids);
                v82 = WPP_GLOBAL_Control;
              }
              if ( v82 != (CSecurityData *)&WPP_GLOBAL_Control && (*((_DWORD *)v82 + 7) & 0x40000) != 0 )
                WPP_SF__KERB_NAME_(*((_QWORD *)v82 + 2), 105, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids, v244);
            }
            v233 = v19;
LABEL_210:
            v232 = v43;
            LODWORD(v35) = 0;
            v83 = KdcNormalize(
                    v244,
                    0,
                    v261,
                    0,
                    v50,
                    2u,
                    0,
                    (unsigned __int8 *)&v240[1],
                    v268,
                    (struct _KDC_TICKET_INFO *)&v304,
                    v251,
                    &v248,
                    v232,
                    v233,
                    &v243,
                    0);
            if ( v83 )
              ClientNetbiosAddress = v83;
            goto LABEL_648;
          }
          if ( v51 )
          {
            ClientNetbiosAddress = 6;
            v346 = v42;
            v347 = si128;
            v54 = 0;
            while ( 1 )
            {
              KerbFreeSid(&v244);
              v55 = v346.m128i_u32[v54];
              v56 = KerbBuildX509AltSecId(v55, pCertContext, &v244);
              if ( v56 != -1073741275 )
              {
                if ( v56 < 0 )
                {
                  if ( (KDCInfoLevel & 0x10000000) != 0 )
                  {
                    v85 = v251;
                    *(_DWORD *)v251 = v56;
                    *((_DWORD *)v85 + 1) = 67310512;
                    *((_DWORD *)v85 + 2) = 2;
                  }
                  goto LABEL_225;
                }
                if ( v243 )
                {
                  ((void (*)(void))SamIFree_UserInternal6Information)();
                  v243 = 0;
                }
                SamIFreeSidAndAttributesList(&v296);
                v296 = 0;
                FreeTicketInfo((struct _KDC_TICKET_INFO *)&v304);
                memset_0(&v304, 0, 0xB0u);
                KerbFreeString(v268);
                v57 = v251;
                *(_QWORD *)v251 = 0;
                *((_DWORD *)v57 + 2) = 0;
                if ( v248 )
                {
                  SamrCloseHandle(&v248);
                  v248 = 0;
                }
                v50 = v263 | 0x95;
                v58 = KdcNormalize(
                        v244,
                        0,
                        v261,
                        0,
                        v263 | 0x95u,
                        v250[1] | (4 * v39),
                        (struct _SAM_MAPPED_ATTRIBUTE_SET *)v293,
                        (unsigned __int8 *)&v240[1],
                        v268,
                        (struct _KDC_TICKET_INFO *)&v304,
                        v251,
                        &v248,
                        v43,
                        v257,
                        &v243,
                        (struct _SID_AND_ATTRIBUTES_LIST *)&v296);
                ClientNetbiosAddress = v58;
                if ( KdcGlobalCDC && v58 == -2147483642 )
                {
                  v84 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control )
                  {
                    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
                    {
                      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 108, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids);
                      v84 = WPP_GLOBAL_Control;
                    }
                    if ( v84 != (CSecurityData *)&WPP_GLOBAL_Control && (*((_DWORD *)v84 + 7) & 0x40000) != 0 )
                      WPP_SF__KERB_NAME_(
                        *((_QWORD *)v84 + 2),
                        109,
                        WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids,
                        v244);
                  }
                  v233 = v257;
                  goto LABEL_210;
                }
                if ( !v58 )
                {
                  LODWORD(v35) = 0;
                  if ( !(unsigned __int8)_KDC_TICKET_INFO::AddAltSecIdMapping(&v304, v55) )
                    goto LABEL_225;
                  if ( v55 - 1 <= 2 )
                    v316 |= 4u;
                  v63 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control )
                  {
                    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
                    {
                      WPP_SF__KERB_NAME_(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        110,
                        WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids,
                        v244);
                      v63 = WPP_GLOBAL_Control;
                    }
                    if ( v63 != (CSecurityData *)&WPP_GLOBAL_Control && (*((_DWORD *)v63 + 7) & 0x1000) != 0 )
                      WPP_SF_Zd(
                        *((_QWORD *)v63 + 2),
                        111,
                        (unsigned int)WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids,
                        (unsigned int)&v304,
                        v316);
                  }
                  ClientNetbiosAddress = KerbAddAltSecIdMapping(v55, v244, &v304, &v265);
                  if ( ClientNetbiosAddress )
                    goto LABEL_648;
LABEL_113:
                  v53 = v316;
                  if ( (v316 & 0x800) != 0 || !v318 || !*(_DWORD *)(v318 + 4) )
                  {
                    v19 = v257;
                    goto LABEL_99;
                  }
                  ClientNetbiosAddress = 75;
                  v59 = 0;
                  v60 = pCertContext;
                  while ( 1 )
                  {
                    v272 = 0;
                    v303.m128i_i64[0] = (__int64)&v272;
                    v303.m128i_i8[8] = 1;
                    v61 = v346.m128i_u32[v59];
                    v62 = KerbBuildX509AltSecId(v61, v60, &v272);
                    if ( v62 != -1073741275 )
                    {
                      if ( v62 < 0 )
                      {
                        ClientNetbiosAddress = 60;
                        goto LABEL_226;
                      }
                      v64 = 0;
                      v65 = v318;
                      if ( *(_DWORD *)(v318 + 4) )
                        break;
                    }
LABEL_135:
                    v303.m128i_i8[8] = 0;
                    KerbFreeSid(&v272);
                    if ( (unsigned int)++v59 >= 8 )
                    {
                      v45 = WPP_GLOBAL_Control;
                      v19 = v257;
                      v31 = v263;
                      goto LABEL_139;
                    }
                  }
                  while ( 1 )
                  {
                    if ( RtlEqualUnicodeString(
                           (PCUNICODE_STRING)(16LL * v64 + 8 + v65),
                           (PCUNICODE_STRING)(v272 + 8),
                           1u) )
                    {
                      ClientNetbiosAddress = KerbAddAltSecIdMapping(v61, v272, &v304, &v265);
                      if ( ClientNetbiosAddress )
                        break;
                    }
                    ++v64;
                    v65 = v318;
                    if ( v64 >= *(_DWORD *)(v318 + 4) )
                      goto LABEL_135;
                  }
LABEL_226:
                  KerbFreeSid(&v272);
                  goto LABEL_648;
                }
                if ( v58 != 6 )
                  goto LABEL_647;
              }
              v54 = (unsigned int)(v54 + 1);
              if ( (unsigned int)v54 >= 8 )
              {
                LODWORD(v35) = 0;
                goto LABEL_113;
              }
            }
          }
          LODWORD(v35) = 0;
          if ( !(unsigned __int8)KerbCompareStringToPrincipalName((char *)v266 + 24, &v304) )
          {
            if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
            {
              WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids, &v304);
            }
            ClientNetbiosAddress = 75;
            goto LABEL_13;
          }
          v52 = v316 | 0x84;
          v316 |= 0x84u;
          if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
          {
            WPP_SF_Zd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              106,
              (unsigned int)WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids,
              (unsigned int)&v304,
              v52);
          }
          LsaIModifyPerformanceCounter(19, 0, 0);
          v53 = v316 | 0x800;
          v316 |= 0x800u;
LABEL_99:
          v45 = WPP_GLOBAL_Control;
          v31 = v263;
          goto LABEL_140;
        }
        if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          LastError = GetLastError();
          v75 = 100;
          v76 = LastError;
          v77 = WPP_GLOBAL_Control;
          goto LABEL_192;
        }
LABEL_647:
        LODWORD(v35) = 0;
        goto LABEL_648;
      }
      LODWORD(v35) = 0;
      v24 = v239;
      if ( !KerbFindPreAuthDataEntry(150, v48) )
        goto LABEL_14;
      ClientNetbiosAddress = 25;
      v78 = KdcBuildPreauthTypeList(v239 != 0, KdcGlobalRequireFreshness != 0, &v255);
      LODWORD(v247) = v78;
      if ( v78 )
      {
        ClientNetbiosAddress = v78;
        v79 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_199;
        }
        v80 = 101;
        v81 = v78;
      }
      else
      {
        v79 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0 )
        {
          goto LABEL_199;
        }
        v80 = 102;
        v81 = 67310342;
      }
      WPP_SF_d(*((_QWORD *)v79 + 2), v80, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids, v81);
LABEL_199:
      v25 = v238;
LABEL_650:
      v26 = v236;
      goto LABEL_651;
    }
    LODWORD(v35) = 0;
LABEL_139:
    v53 = v316;
LABEL_140:
    if ( ClientNetbiosAddress )
    {
      v27 = v237;
      v26 = v236;
      v24 = v239;
      v25 = v238;
      goto LABEL_653;
    }
    v66 = v53 | 1;
LABEL_143:
    v316 = v40 | v66;
    v67 = v239;
    if ( !v239 && KdcGlobalDomainFastLevel == 2 )
    {
      if ( (unsigned int)KdcIsWin8FunctionalLevel() && (v306 & 0x80u) == 0 && (v306 & 0x100) == 0 )
      {
        ClientNetbiosAddress = 12;
        FillExtendedError(-1073741061, 3, 1027, 5220, v251);
        v86 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_13;
        }
        v87 = 112;
        v88 = 12;
LABEL_232:
        WPP_SF_d(*((_QWORD *)v86 + 2), v87, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids, v88);
        goto LABEL_648;
      }
      v45 = WPP_GLOBAL_Control;
      v67 = v239;
    }
    if ( v240[1] )
    {
      ClientNetbiosAddress = 68;
      v241 = 1;
      if ( v45 == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)v45 + 28) & 2) == 0 )
        goto LABEL_13;
      v90 = 113;
      v91 = v268;
      v92 = 67310714;
LABEL_241:
      WPP_SF_DZ(
        *((_QWORD *)v45 + 2),
        v90,
        (unsigned int)WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids,
        v92,
        (__int64)v91);
      goto LABEL_648;
    }
    if ( *(_WORD *)v244 == 6 && *(_QWORD *)&v281.Length )
    {
      ClientNetbiosAddress = 25;
      v89 = KdcBuildPreauthTypeList(v67 != 0, 0, &v255);
      LODWORD(v247) = v89;
      if ( !v89 )
      {
        v45 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0 )
        {
          goto LABEL_648;
        }
        v90 = 115;
        v91 = &v304;
        v92 = 67310737;
        goto LABEL_241;
      }
      ClientNetbiosAddress = v89;
      v86 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_648;
      v87 = 114;
LABEL_237:
      v88 = v89;
      goto LABEL_232;
    }
    if ( !v39 )
      break;
    v68 = pCertContext;
    v69 = v251;
    if ( !pCertContext )
    {
      ClientNetbiosAddress = KdcVerifyAuthPackSignature(
                               *(struct KERB_KDC_REQUEST_preauth_data_s **)&v279[1],
                               1,
                               &pCertContext,
                               (struct KdcPackedAuthenticator *)v327,
                               v251,
                               &hCertStore,
                               &v255);
      if ( ClientNetbiosAddress )
        goto LABEL_647;
      v68 = pCertContext;
    }
    ClientNetbiosAddress = KdcCheckClientCertificateAndBuildChain(
                             &v304,
                             v68,
                             hCertStore,
                             &pChainContext,
                             v69,
                             (struct KERB_ERR_REASON *)&v265);
    if ( ClientNetbiosAddress )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          116,
          WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids,
          (unsigned int)ClientNetbiosAddress);
      LODWORD(v35) = 0;
      if ( !*(_QWORD *)&v335[6] )
        KdcFillPkiAuditInfo(v68, (struct _KDC_PKI_AUDIT_INFO *)&v334);
      LODWORD(v265) = 1;
      HIDWORD(v265) = ClientNetbiosAddress;
      goto LABEL_648;
    }
    v70 = v316;
    if ( (v316 & 0x80u) == 0 || (v316 & 0x200) != 0 )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 117, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids);
      v71 = pChainContext;
      ClientNetbiosAddress = KdcBuildIssuancePolicyInfo(pChainContext, (struct _SAM_MAPPED_ATTRIBUTE_SET **)&v293);
      if ( ClientNetbiosAddress )
        goto LABEL_647;
      v70 = v316;
    }
    else
    {
      v71 = pChainContext;
    }
    if ( v70 < 0 )
    {
      v301 = v244;
      ClientNetbiosAddress = KerbGetCertificatePublicKey(v68, &v244);
      if ( ClientNetbiosAddress )
        goto LABEL_647;
      v242 = 1;
    }
    else
    {
      KerbFreeSid(&v244);
      ClientNetbiosAddress = KerbConvertStringToKdcName(&v244, &v304);
      if ( ClientNetbiosAddress )
        goto LABEL_647;
    }
    if ( KdcGlobalEnforceStrongCertificateMapping >= 1 )
    {
      if ( v68 )
      {
        ClientNetbiosAddress = KdcSanityCheckCertMapping(
                                 v68,
                                 (struct _KDC_TICKET_INFO *)&v304,
                                 v71,
                                 (struct KERB_ERR_REASON *)&v265);
        if ( ClientNetbiosAddress )
        {
          v77 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v75 = 118;
            v76 = (unsigned int)ClientNetbiosAddress;
LABEL_192:
            WPP_SF_d(*((_QWORD *)v77 + 2), v75, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids, v76);
          }
          goto LABEL_647;
        }
      }
    }
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_DZ(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        119,
        (unsigned int)WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids,
        67310871,
        (__int64)&v304);
    if ( v243 )
    {
      ((void (*)(void))SamIFree_UserInternal6Information)();
      v243 = 0;
    }
    SamIFreeSidAndAttributesList(&v296);
    v296 = 0;
    v40 = v316;
    FreeTicketInfo((struct _KDC_TICKET_INFO *)&v304);
    memset_0(&v304, 0, 0xB0u);
    KerbFreeString(v268);
    *(_QWORD *)v69 = 0;
    *((_DWORD *)v69 + 2) = 0;
    if ( v248 )
    {
      SamrCloseHandle(&v248);
      v248 = 0;
    }
    v39 = 0;
  }
  v93 = (__int64 *)KerberosCryptoPolicy::FromKdcTicketInfo(
                     (KerberosCryptoPolicy **)&v281,
                     (const struct _KDC_TICKET_INFO *)&v304);
  utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::operator=((__int64 *)&v295, v93);
  utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&v281);
  v95 = v295;
  if ( !v295 )
  {
    v194 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_225;
    v195 = 120;
    goto LABEL_627;
  }
  if ( v309 )
  {
    LOBYTE(v253) = 1;
    if ( *((_WORD *)v309 + 2) <= 1u )
    {
      ClientNetbiosAddress = 14;
      v96 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control )
        goto LABEL_13;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 121, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids, 67310930);
        v96 = WPP_GLOBAL_Control;
      }
      if ( v96 == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)v96 + 28) & 1) == 0 )
        goto LABEL_648;
      v97 = 122;
      goto LABEL_260;
    }
  }
  if ( !Ntlmless::Kerberos::IsEnabled(v94) )
  {
    if ( v248 )
    {
      v99 = v243;
      if ( v243 )
        goto LABEL_273;
    }
    ClientNetbiosAddress = 6;
    v96 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control )
      goto LABEL_13;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 125, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids, 67310959);
      v96 = WPP_GLOBAL_Control;
    }
    if ( v96 == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)v96 + 28) & 1) == 0 )
      goto LABEL_648;
    v97 = 126;
LABEL_260:
    v98 = v244;
    goto LABEL_261;
  }
  if ( !v243 || _KDC_TICKET_INFO::IsAnyKrbtgt((_KDC_TICKET_INFO *)&v304) )
  {
    ClientNetbiosAddress = 6;
    v96 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control )
      goto LABEL_13;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 123, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids, 67310945);
      v96 = WPP_GLOBAL_Control;
    }
    if ( v96 == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)v96 + 28) & 1) == 0 )
      goto LABEL_648;
    v97 = 124;
    goto LABEL_260;
  }
LABEL_273:
  v100 = *(struct KERB_KDC_REQUEST_preauth_data_s **)&v279[1];
  if ( v267 && KerbFindPreAuthDataEntry(128, *(_QWORD *)&v279[1]) )
  {
    ClientNetbiosAddress = 52;
    v27 = v237;
    v25 = v238;
    goto LABEL_276;
  }
  v103 = v259;
  if ( (v31 & 0x40) != 0 && (*((_DWORD *)v99 + 70) & 0x10000) != 0 )
    v103 = 0;
  v104 = v302;
  v106 = v103 | 2;
  if ( !KerbEqualKdcNames(v302, GlobalKpasswdName) )
    v106 = v103;
  LODWORD(v35) = 0;
  ClientNetbiosAddress = 0;
  v107 = (int)v243;
  v108 = (unsigned __int8 *)*((_QWORD *)v243 + 74);
  if ( !v108 || *((_DWORD *)v243 + 68) == 500 )
    goto LABEL_306;
  if ( !v275 || (v109 = *(struct KERB_ENCRYPTED_TICKET **)(v275 + 16), (*(_BYTE *)v109 & 0x10) == 0) )
  {
    if ( !*((_BYTE *)v243 + 568) )
      goto LABEL_306;
    ClientNetbiosAddress = 12;
    *(_DWORD *)&v240[4] = -1073741712;
    goto LABEL_321;
  }
  v110 = KdcPerformA2AFromAccessCheck((struct _KDC_TICKET_INFO *)(v275 + 144), v108, v109, v105, (int *)&v240[4]);
  ClientNetbiosAddress = v110;
  v107 = (int)v243;
  if ( !v110 )
  {
LABEL_304:
    v110 = 0;
    goto LABEL_305;
  }
  if ( !*((_BYTE *)v243 + 568) )
  {
    ClientNetbiosAddress = 0;
    *(_DWORD *)&v240[4] = 0;
    goto LABEL_304;
  }
  if ( v110 == 12 && (*(_DWORD *)&v240[4] == -1073740781 || *(_DWORD *)&v240[4] == -1073741413) )
    *(_DWORD *)&v240[4] = -1073741712;
LABEL_305:
  if ( !v110 )
  {
LABEL_306:
    ClientNetbiosAddress = KerbCheckLogonRestrictions(
                             (_DWORD)v248,
                             (unsigned int)&v285,
                             v107,
                             v106,
                             (__int64)&v290,
                             (__int64)&v289,
                             (__int64)&v240[4]);
    goto LABEL_307;
  }
LABEL_321:
  v289 = tsInfinity;
  v290 = tsInfinity;
LABEL_307:
  LOBYTE(v108) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_DMSAKDC>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_DMSAKDC>::GetImpl'::`2'::impl,
    v108);
  KdcCheckIfServiceAccountSuperseded(v243, &v284, &v255, *(_DWORD *)&v240[4] == -1073741710);
  if ( ClientNetbiosAddress )
  {
    v111 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        127,
        WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids,
        *(unsigned int *)&v240[4],
        ClientNetbiosAddress);
      v111 = WPP_GLOBAL_Control;
    }
    v112 = *(_DWORD *)&v240[4];
    if ( *(_DWORD *)&v240[4] != -1073741260
      && *(_DWORD *)&v240[4] != -1073741276
      && *(_DWORD *)&v240[4] != -1073741711
      && *(_DWORD *)&v240[4] != -1073741730 )
    {
      if ( v111 != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)v111 + 28) & 2) != 0 )
      {
        WPP_SF_DDD(
          *((_QWORD *)v111 + 2),
          133,
          WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids,
          67311375,
          *(_DWORD *)&v240[4],
          ClientNetbiosAddress);
        v112 = *(_DWORD *)&v240[4];
      }
      FillExtendedError(v112, 1, 1027, 5905, v251);
      goto LABEL_648;
    }
    memset_0(Sid, 0, 0x48u);
    KdcMakeAccountSid(Sid, v307);
    v113 = v251;
    v234 = (struct _UNICODE_STRING *)v95;
    v102 = pCertContext;
    v114 = v266;
    v115 = v256;
    v116 = KdcCheckPreAuthData(
             (int)v274,
             (int)&v304,
             (int)v248,
             (int)v243,
             (int)v224,
             (int)v225,
             (__int64)v256,
             v100,
             (__int64)v266,
             (__int64)v280,
             (__int64)pCertContext,
             (__int64)v327,
             (__int64)hCertStore,
             (__int64)pChainContext,
             (__int64)v234,
             (__int64)v250,
             &v255,
             v323,
             (enum PacRequestType *)&v258,
             (__int64)&v262,
             (__int64)v331,
             (__int64)&v340,
             (__int64)&v334,
             v322,
             (__int64)v251,
             (__int64)v240,
             (__int64)&v254,
             (__int64)v341,
             (__int64)&v265);
    v117 = *(_DWORD *)&v240[4];
    if ( *(_DWORD *)&v240[4] == -1073741260 && v255 )
    {
      KerbFreeAuthData(v255);
      v255 = 0;
      v117 = *(_DWORD *)&v240[4];
    }
    if ( v116 )
    {
      if ( v117 != -1073741260 )
        ClientNetbiosAddress = v116;
      v118 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_DDD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          128,
          WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids,
          67311223,
          v117,
          ClientNetbiosAddress);
        v117 = *(_DWORD *)&v240[4];
        v118 = WPP_GLOBAL_Control;
      }
      if ( !*(_BYTE *)v270 )
      {
        v119 = ClientNetbiosAddress;
        if ( (unsigned int)(ClientNetbiosAddress + 2147483642) <= 1 )
        {
          LODWORD(v247) = -1073740943;
          v119 = -1073740943;
        }
        else
        {
          LODWORD(v247) = ClientNetbiosAddress;
        }
        if ( (qword_1800B2E50 & 0x200000000LL) == 0 || v119 == -1073740943 )
        {
          v26 = v236;
        }
        else
        {
          v120 = (struct sockaddr_storage *)v115;
          if ( !v115 )
            v120 = &GlobalLocalhostAddress;
          v26 = v236;
          LsaIAuditKdcEvent(
            675,
            &v304,
            0,
            Sid,
            v236,
            0,
            (char *)&v247 + 4,
            &v247,
            0,
            v250,
            v120,
            0,
            0,
            &v334,
            v336,
            v337,
            0,
            0,
            0,
            0,
            0,
            0,
            0,
            0,
            0,
            0,
            0,
            0);
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExtendedAuditingForKerberos>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ExtendedAuditingForKerberos>::GetImpl'::`2'::impl) )
        {
          LogGetAsExtendedAudit(
            (int)&v304,
            0,
            (int)Sid,
            (int)v26,
            0,
            (__int64)&v247 + 4,
            (__int64)&v247,
            0,
            (__int64)v250,
            v115,
            (__int64)&v334,
            0,
            0,
            (__int64)v114,
            (__int64)&v285,
            (__int64)v113,
            0,
            0,
            (__int64)v280,
            (__int64)v341,
            (__int64)v240,
            (__int64)&v254,
            (__int64)&v258,
            (__int64)&v262,
            (__int64)&v240[4],
            (__int64)v243,
            (__int64)v102);
          v245 = 1;
        }
        v241 = 1;
        v117 = *(_DWORD *)&v240[4];
        v118 = WPP_GLOBAL_Control;
LABEL_346:
        if ( ClientNetbiosAddress != 24 && v117 != -1073741276 && v117 != -1073741711 && v117 != -1073741260 )
        {
          if ( v117 == -1073741730 )
          {
            if ( v118 != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)v118 + 28) & 2) != 0 )
              WPP_SF_d(*((_QWORD *)v118 + 2), 131, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids, 67311358);
            KdcHandleNoLogonServers(v248, v115);
          }
          else
          {
            if ( v118 != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)v118 + 28) & 2) != 0 )
            {
              WPP_SF_DDD(
                *((_QWORD *)v118 + 2),
                132,
                WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids,
                67311367,
                v117,
                ClientNetbiosAddress);
              v117 = *(_DWORD *)&v240[4];
            }
            FillExtendedError(v117, 1, 1027, 5896, v113);
          }
          v25 = v238;
          goto LABEL_356;
        }
        if ( v118 != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)v118 + 28) & 2) != 0 )
        {
          WPP_SF_DDDD(
            *((_QWORD *)v118 + 2),
            129,
            WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids,
            67311310,
            v117,
            ClientNetbiosAddress,
            v116);
          v117 = *(_DWORD *)&v240[4];
        }
        v121 = v270;
        FailedLogon(
          v248,
          v243,
          (struct sockaddr_storage *)v115,
          v114,
          Sid,
          0x48u,
          (struct _KDC_TICKET_INFO *)&v304,
          (void **)v274,
          v238,
          &v285,
          ClientNetbiosAddress,
          v117,
          v240[0],
          0,
          v270);
        if ( *(_BYTE *)v121 )
        {
          ClientNetbiosAddress = 0;
          v27 = v237;
          goto LABEL_717;
        }
        v246 = 1;
        if ( !*((_QWORD *)v238 + 1) && *(int *)&v240[4] < 0 )
        {
          FillExtendedError(*(int *)&v240[4], 1, 1027, 5875, v113);
          if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              130,
              WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids,
              67311350);
          }
        }
        v25 = v238;
LABEL_356:
        v24 = v239;
        LODWORD(v35) = 0;
LABEL_651:
        v27 = v237;
LABEL_652:
        if ( ClientNetbiosAddress != (_DWORD)v35 )
        {
LABEL_653:
          if ( ClientNetbiosAddress != 52 )
          {
            if ( (unsigned int)(ClientNetbiosAddress + 2147483642) <= 1 )
            {
              v28 = -1073740943;
              goto LABEL_656;
            }
LABEL_15:
            v28 = ClientNetbiosAddress;
LABEL_656:
            LODWORD(v247) = v28;
            v101 = v270;
            v196 = v256;
            if ( *(_BYTE *)v270 || v241 || (qword_1800B2E50 & 0x200000000LL) == 0 || !v244 || v28 == -1073740943 )
            {
              v199 = (int)v261;
            }
            else
            {
              v197 = v256;
              if ( !v256 )
                v197 = (struct sockaddr *)&GlobalLocalhostAddress;
              v198 = v301;
              if ( !v242 )
                v198 = v244;
              v199 = (int)v261;
              LsaIAuditKdcEvent(
                672,
                (char *)v198 + 8,
                v261,
                0,
                v26,
                0,
                (char *)&v247 + 4,
                &v247,
                0,
                0,
                v197,
                0,
                0,
                &v334,
                v336,
                v337,
                0,
                0,
                0,
                0,
                0,
                0,
                0,
                0,
                0,
                0,
                0,
                0);
            }
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExtendedAuditingForKerberos>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ExtendedAuditingForKerberos>::GetImpl'::`2'::impl)
              && !*(_BYTE *)v101
              && !v245 )
            {
              v200 = 0;
              if ( v244 )
              {
                if ( v242 )
                  v200 = (_DWORD)v301 + 8;
                else
                  v200 = (_DWORD)v244 + 8;
              }
              LogGetAsExtendedAudit(
                v200,
                v199,
                0,
                (int)v26,
                0,
                (__int64)&v247 + 4,
                (__int64)&v247,
                0,
                (__int64)v250,
                v196,
                (__int64)&v334,
                0,
                0,
                (__int64)v266,
                (__int64)&v285,
                (__int64)v251,
                0,
                0,
                (__int64)v280,
                (__int64)v341,
                (__int64)v240,
                (__int64)&v254,
                (__int64)&v258,
                (__int64)&v262,
                (__int64)&v240[4],
                (__int64)v243,
                (__int64)pCertContext);
            }
            if ( v24 )
            {
              v201 = (struct KERB_KDC_REQUEST_preauth_data_s *)v237;
              if ( v237 )
              {
                *(_QWORD *)v237 = v255;
                v202 = v201;
                v255 = v201;
                v27 = 0;
LABEL_680:
                if ( v202 )
                {
                  v203 = (_DWORD *)v322;
                  v204 = (void **)(v322 + 8);
                  if ( *(_QWORD *)(v322 + 8) )
                  {
                    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    {
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        160,
                        WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids,
                        67312670);
                    }
                    MIDL_user_free(*v204);
                    *v204 = 0;
                    *v203 = 0;
                  }
                  KerbPackData(&v255, 3, v203, v204);
                  if ( v24 )
                  {
                    *(_QWORD *)v323 = v255;
                    v255 = 0;
                  }
                }
LABEL_277:
                if ( v248 && ClientNetbiosAddress != 52 )
                {
                  if ( ClientNetbiosAddress )
                  {
                    if ( !v246 && ((_BYTE)v253 || ClientNetbiosAddress == -2147483642) )
                    {
                      memset_0(Sid, 0, 0x48u);
                      KdcMakeAccountSid(Sid, v307);
                      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                      {
                        WPP_SF_DDD(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          161,
                          WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids,
                          67312709,
                          *(_DWORD *)&v240[4],
                          ClientNetbiosAddress);
                      }
                      FailedLogon(
                        v248,
                        v243,
                        (struct sockaddr_storage *)v256,
                        v266,
                        Sid,
                        0x48u,
                        (struct _KDC_TICKET_INFO *)&v304,
                        (void **)v274,
                        v25,
                        &v285,
                        ClientNetbiosAddress,
                        *(int *)&v240[4],
                        v240[0],
                        0,
                        v101);
                      if ( *(_BYTE *)v101 )
                      {
                        ClientNetbiosAddress = 0;
                        v102 = pCertContext;
                        goto LABEL_717;
                      }
                    }
                  }
                  else
                  {
                    memset_0(Sid, 0, 0x48u);
                    KdcMakeAccountSid(Sid, v307);
                    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                    {
                      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 162, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids);
                    }
                    SuccessfulLogon(
                      v248,
                      v256,
                      Sid,
                      v205,
                      (struct _KDC_TICKET_INFO *)v224,
                      (struct _KDC_TICKET_INFO *)v225,
                      v226,
                      v227,
                      v228,
                      v229,
                      v274,
                      &v285,
                      v243,
                      v101);
                  }
                }
                v206 = v291;
                if ( KdcEventTraceFlag )
                {
                  v253 = 0;
                  v275 = 131074;
                  v276 = &v253;
                  v369 = 2;
                  v371 = 1179648;
                  p_ClientNetbiosAddress = &ClientNetbiosAddress;
                  v373 = 4;
                  if ( v291->Buffer && (Length = v291->Length) != 0 )
                  {
                    v208 = v291;
                  }
                  else
                  {
                    v208 = (struct _UNICODE_STRING *)&v275;
                    Length = 2;
                  }
                  v374 = v208;
                  v375 = 2;
                  Buffer = v208->Buffer;
                  v377 = Length;
                  v209 = v236;
                  if ( v236->Buffer && (v210 = v236->Length) != 0 )
                  {
                    v211 = v236;
                  }
                  else
                  {
                    v211 = (struct _UNICODE_STRING *)&v275;
                    v210 = 2;
                  }
                  v378 = v211;
                  v379 = 2;
                  v380 = v211->Buffer;
                  v381 = v210;
                  v212 = v261;
                  if ( !v261->Buffer || (v213 = v261->Length) == 0 )
                  {
                    v212 = (struct _UNICODE_STRING *)&v275;
                    v213 = 2;
                  }
                  v382 = v212;
                  v383 = 2;
                  v384 = v212->Buffer;
                  v385 = v213;
                  v367 = 160;
                  EtwLogTraceEvent(KdcTraceLoggerHandle, &v367);
                }
                else
                {
                  v209 = v236;
                }
                if ( !ClientNetbiosAddress )
                {
                  v214 = KdcGlobalTicketSizeThreshold - (KdcGlobalTicketSizeThreshold >> 3);
                  if ( v269 >= v214 )
                    KdcReportLargeTicket(v206, v209, v269, v214, v324);
                }
                if ( (_DWORD)v265 )
                {
                  v215 = KdcGlobalEnforceStrongCertificateMapping == 2;
                  if ( (unsigned int)dword_1800B20C0 > 5
                    && (unsigned __int8)tlgKeywordOn(&dword_1800B20C0, 0x400000000000LL) )
                  {
                    v275 = 0x1000000;
                    v267 = v215;
                    v250[1] = HIDWORD(v265);
                    v269 = v265;
                    v259 = (v306 & 0x180) == 0;
                    v260 = 1;
                    *(_QWORD *)&v281.Length = 1;
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
                      v216,
                      (int)byte_1800A5B39,
                      v217,
                      (__int64)&v281,
                      (__int64)&v260,
                      (__int64)&v259,
                      (__int64)&v250[1],
                      (__int64)&v269,
                      (__int64)&v267,
                      (__int64)&v275);
                  }
                  if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                  {
                    WPP_SF_DDDD(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      163,
                      WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids,
                      HIDWORD(v265),
                      v265,
                      v215,
                      (v306 & 0x180) == 0);
                  }
                }
LABEL_716:
                v102 = pCertContext;
LABEL_717:
                KdcTelemetry::MessageOperation(0, Target, v287, v286, v278, ClientNetbiosAddress);
                if ( v248 )
                  SamrCloseHandle(&v248);
                if ( v324 )
                  MIDL_user_free(v324);
                if ( v327[0] )
                  NetpMemoryFree();
                if ( pChainContext )
                  CertFreeCertificateChain(pChainContext);
                if ( v102 )
                  CertFreeCertificateContext(v102);
                if ( v300 )
                  ((void (*)(void))SamIFree_UserInternal6Information)();
                SamIFree_UserInternal6Information(v243);
                SamIFreeSidAndAttributesList(&v296);
                KerbFreeAuthData(v292);
                FreeTicketInfo((struct _KDC_TICKET_INFO *)&v304);
                FreeTicketInfo((struct _KDC_TICKET_INFO *)v348);
                KdcFreeCertLogInfo((struct _KDC_CERT_LOG_INFO *)&v334);
                KdcFreeInternalTicket((struct KERB_TICKET *)v402);
                KerbFreeKey(v386);
                KerbFreeSid(&v244);
                KerbFreeSid(&v301);
                KerbFreeString(&v340);
                KerbFreeString(&v366);
                KerbFreeSid(&v302);
                KerbFreeString(&v285);
                KdcFreeKdcReplyBody((struct KERB_ENCRYPTED_KDC_REPLY *)&v422);
                KdcFreeKdcReply((struct KERB_KDC_REPLY *)v388);
                KerbFreeAuthData(v255);
                if ( hCertStore )
                  CertCloseStore(hCertStore, 1u);
                if ( v339[1] )
                  MIDL_user_free(v339[1]);
                if ( v365 )
                  MIDL_user_free(v365);
                if ( v330 )
                  KerbFreeAuthData(v330);
                if ( v27 )
                {
                  v218 = (void *)v27[3];
                  if ( v218 )
                    MIDL_user_free(v218);
                  MIDL_user_free(v27);
                }
                if ( v284 )
                {
                  do
                  {
                    v219 = (void **)v284;
                    v284 = *(struct KERB_ENCRYPTED_KDC_REPLY_encrypted_pa_data_s **)v284;
                    v220 = v284;
                    MIDL_user_free(v219[3]);
                    MIDL_user_free(v219);
                  }
                  while ( v220 );
                }
                if ( v293 )
                  MIDL_user_free(v293);
                v164 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
                  && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0 )
                {
                  v165 = 164;
                  v166 = (unsigned int)ClientNetbiosAddress;
LABEL_748:
                  WPP_SF_d(*((_QWORD *)v164 + 2), v165, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids, v166);
                }
                v163 = ClientNetbiosAddress;
                goto LABEL_750;
              }
              v27 = 0;
            }
            v202 = v255;
            goto LABEL_680;
          }
        }
LABEL_276:
        v101 = v270;
        goto LABEL_277;
      }
    }
    else
    {
      v118 = WPP_GLOBAL_Control;
    }
    v26 = v236;
    goto LABEL_346;
  }
  v122 = v251;
  v123 = v266;
  ClientNetbiosAddress = KdcCheckPreAuthData(
                           (int)v274,
                           (int)&v304,
                           (int)v248,
                           (int)v243,
                           (int)v224,
                           (int)v225,
                           (__int64)v256,
                           v100,
                           (__int64)v266,
                           (__int64)v280,
                           (__int64)pCertContext,
                           (__int64)v327,
                           (__int64)hCertStore,
                           (__int64)pChainContext,
                           (__int64)v95,
                           (__int64)v250,
                           &v255,
                           v323,
                           (enum PacRequestType *)&v258,
                           (__int64)&v262,
                           (__int64)v331,
                           (__int64)&v340,
                           (__int64)&v334,
                           v322,
                           (__int64)v251,
                           (__int64)v240,
                           (__int64)&v254,
                           (__int64)v341,
                           (__int64)&v265);
  v287 = HIDWORD(v331[1]);
  if ( ClientNetbiosAddress )
  {
    memset_0(Sid, 0, 0x48u);
    KdcMakeAccountSid(Sid, v307);
    v124 = v270;
    if ( *(_BYTE *)v270 )
    {
      v26 = v236;
    }
    else
    {
      v125 = ClientNetbiosAddress;
      if ( (unsigned int)(ClientNetbiosAddress + 2147483642) <= 1 )
      {
        LODWORD(v247) = -1073740943;
        v125 = -1073740943;
      }
      else
      {
        LODWORD(v247) = ClientNetbiosAddress;
      }
      v126 = v256;
      if ( (qword_1800B2E50 & 0x200000000LL) == 0 || v125 == 25 || v125 == -1073740943 )
      {
        v26 = v236;
      }
      else
      {
        v127 = v256;
        if ( !v256 )
          v127 = (struct sockaddr *)&GlobalLocalhostAddress;
        v26 = v236;
        LsaIAuditKdcEvent(
          675,
          &v304,
          0,
          Sid,
          v236,
          0,
          (char *)&v247 + 4,
          &v247,
          0,
          v250,
          v127,
          0,
          0,
          &v334,
          v336,
          v337,
          0,
          0,
          0,
          0,
          0,
          0,
          0,
          0,
          0,
          0,
          0,
          0);
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExtendedAuditingForKerberos>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ExtendedAuditingForKerberos>::GetImpl'::`2'::impl) )
      {
        LogGetAsExtendedAudit(
          (int)&v304,
          (int)v261,
          (int)Sid,
          (int)v26,
          0,
          (__int64)&v247 + 4,
          (__int64)&v247,
          0,
          (__int64)v250,
          v126,
          (__int64)&v334,
          0,
          0,
          (__int64)v123,
          (__int64)&v285,
          (__int64)v122,
          0,
          0,
          (__int64)v280,
          (__int64)v341,
          (__int64)v240,
          (__int64)&v254,
          (__int64)&v258,
          (__int64)&v262,
          (__int64)&v240[4],
          (__int64)v243,
          (__int64)pCertContext);
        v245 = 1;
      }
      v241 = 1;
      v124 = v270;
    }
    if ( ClientNetbiosAddress == 24 )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_DDD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          135,
          WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids,
          67311538,
          *(_DWORD *)&v240[4],
          24);
      LODWORD(v35) = 0;
      v25 = v238;
      FailedLogon(
        v248,
        v243,
        (struct sockaddr_storage *)v256,
        v123,
        Sid,
        0x48u,
        (struct _KDC_TICKET_INFO *)&v304,
        (void **)v274,
        v238,
        &v285,
        ClientNetbiosAddress,
        *(int *)&v240[4],
        v240[0],
        0,
        v124);
      if ( *(_BYTE *)v124 )
      {
        ClientNetbiosAddress = 0;
        v27 = v237;
        goto LABEL_716;
      }
    }
    else
    {
      v25 = v238;
      LODWORD(v35) = 0;
    }
    v246 = 1;
    v24 = v239;
    goto LABEL_651;
  }
  v128 = KdcCallSubAuthRoutine((struct _KDC_TICKET_INFO *)&v304, v243, &v285, &v290, &v289, v122);
  ClientNetbiosAddress = v128;
  if ( v128 )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        136,
        WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids,
        67311587,
        v128);
      goto LABEL_647;
    }
    LODWORD(v35) = 0;
LABEL_474:
    v26 = v236;
LABEL_430:
    v24 = v239;
    v25 = v238;
    goto LABEL_651;
  }
  v129 = !*((_WORD *)v104 + 1) || !RtlEqualUnicodeString((PCUNICODE_STRING)((char *)v104 + 8), &String2, 1u);
  v130 = *((_WORD *)v104 + 1) && RtlEqualUnicodeString((PCUNICODE_STRING)((char *)v104 + 8), &String2, 1u);
  v131 = (struct _USER_INTERNAL6_INFORMATION **)&v300;
  if ( v130 )
    v131 = 0;
  v230 = v122;
  v35 = 0;
  v132 = KdcNormalize(
           v104,
           0,
           0,
           0,
           v31 | 2u,
           v129,
           0,
           v264,
           &v366,
           (struct _KDC_TICKET_INFO *)v348,
           v230,
           0,
           0x10000000u,
           4 * (unsigned int)v129 + 33556480,
           v131,
           0);
  ClientNetbiosAddress = v132;
  if ( v132 )
  {
    v96 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control )
      goto LABEL_474;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        137,
        WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids,
        67311640,
        v132);
      v96 = WPP_GLOBAL_Control;
    }
    if ( v96 == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)v96 + 28) & 1) == 0 )
      goto LABEL_474;
    v97 = 138;
    v98 = v104;
LABEL_261:
    WPP_SF__KERB_NAME_(*((_QWORD *)v96 + 2), v97, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids, v98);
    goto LABEL_648;
  }
  if ( !*((_QWORD *)&v332 + 1) )
  {
    if ( v254 )
    {
      if ( !KerberosCryptoPolicy::SetRequestCiphers(v95, &v254, 1u) )
        ClientNetbiosAddress = 14;
      if ( !(unsigned __int8)KerberosCryptoPolicy::HasCandidateKey(v95, 3) )
      {
        ClientNetbiosAddress = 14;
        v86 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_13;
        }
        v87 = 139;
        v88 = 67311671;
        goto LABEL_232;
      }
      goto LABEL_431;
    }
    if ( (unsigned __int8)KerberosCryptoPolicy::HasCandidateKey(v95, 3) )
      goto LABEL_431;
    v26 = v236;
    v133 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_430;
    v134 = 140;
    v135 = 67311698;
LABEL_429:
    WPP_SF_Dd(*((_QWORD *)v133 + 2), v134, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids, v135, ClientNetbiosAddress);
    goto LABEL_430;
  }
LABEL_431:
  v136 = (__int64 *)KerberosCryptoPolicy::FromKdcTicketInfo(
                      (KerberosCryptoPolicy **)&v275,
                      (const struct _KDC_TICKET_INFO *)v348);
  utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::operator=((__int64 *)&v294, v136);
  utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&v275);
  v137 = v294;
  if ( !v294
    || (v138 = v266,
        !KerberosCryptoPolicy::SetRequestCiphers(v294, *((struct KERB_KDC_REQUEST_BODY_encryption_type_s **)v266 + 14))) )
  {
    v194 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_225;
    v195 = 141;
    goto LABEL_627;
  }
  if ( ClientNetbiosAddress )
  {
    KerberosCryptoPolicy::GetEncryptionAlgorithms(v137, &v281);
    v26 = v236;
    if ( *(_QWORD *)&v281.Length )
      KdcReportKeyErrorETypes(
        (int)v291,
        (int)v236,
        5,
        -1073741810,
        *(void **)&v281.Length,
        (__int64)v348,
        (__int64)v226);
    utl::unique_ptr<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>,utl::default_delete<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>>>::~unique_ptr<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>,utl::default_delete<utl::vector<Kerb3961::EncryptionAlgorithm *,utl::allocator<Kerb3961::EncryptionAlgorithm *>>>>(&v281);
    v133 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_430;
    v134 = 142;
    v135 = 67311739;
    goto LABEL_429;
  }
  v329 = *(union _LARGE_INTEGER *)((char *)v243 + 24);
  if ( KdcUseClientAddresses )
  {
    for ( i = (_QWORD *)*((_QWORD *)v138 + 15); i; i = (_QWORD *)*i )
    {
      v140 = i + 1;
      if ( KdcUseClientNetBIOSAddresses && *v140 == 20 || *v140 == 2 || *v140 == 24 )
      {
        v35 = (struct KERB_ENCRYPTED_KDC_REPLY_encrypted_pa_data_s *)*((_QWORD *)v138 + 15);
        break;
      }
    }
  }
  RtlAcquireResourceShared(&Resource, 1u);
  v141.QuadPart = qword_1800B2E38;
  RtlReleaseResource(&Resource);
  v273 = v141;
  v297 = **(union _LARGE_INTEGER **)&CSecurityData::KdcTicketRenewSpan(v142);
  v143 = (struct _USER_ALL_INFORMATION *)v243;
  if ( *((_BYTE *)v243 + 568) && (v144 = *(union _LARGE_INTEGER *)((char *)v243 + 576), v144.QuadPart) )
  {
LABEL_453:
    v145 = v273;
    if ( v273.QuadPart >= v144.QuadPart )
    {
      v273 = v144;
      v145 = v144;
    }
    v297 = v145;
  }
  else if ( (v316 & 0x40) != 0 )
  {
    v144.QuadPart = 144000000000LL;
    goto LABEL_453;
  }
  if ( *((_BYTE *)v243 + 608) && *((_QWORD *)v243 + 77) )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v143 = (struct _USER_ALL_INFORMATION *)v243;
    v146 = *((_QWORD *)v243 + 77);
    if ( v146 > *(_QWORD *)&SystemTimeAsFileTime )
    {
      v147.QuadPart = v146 - *(_QWORD *)&SystemTimeAsFileTime;
      v148 = v273;
      if ( v273.QuadPart >= v147.QuadPart )
      {
        v148 = v147;
        v273 = v147;
      }
      v297 = v148;
      goto LABEL_462;
    }
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v224 = (union _LARGE_INTEGER *)*((_QWORD *)v243 + 77);
      WPP_SF_Dq(*((_QWORD *)WPP_GLOBAL_Control + 2), 143, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids, 67311841);
    }
LABEL_225:
    ClientNetbiosAddress = 60;
    goto LABEL_13;
  }
LABEL_462:
  if ( *(_BYTE *)v270 )
    v143 = 0;
  v149 = v251;
  v150 = BuildTicketAS(
           (struct _KDC_TICKET_INFO *)&v304,
           (struct KERB_KDC_REQUEST_BODY *)((char *)v266 + 24),
           (struct _KDC_TICKET_INFO *)v348,
           (struct KERB_KDC_REQUEST_BODY *)((char *)v266 + 48),
           v35,
           &v290,
           &v289,
           &v329,
           v143,
           &v273,
           &v297,
           v266,
           v137,
           v250[0],
           &v340,
           (struct KERB_TICKET *)v402,
           v251);
  v151 = v150;
  ClientNetbiosAddress = v150;
  LODWORD(v35) = 0;
  if ( v150 )
  {
    if ( v150 == 23 )
    {
      *(_DWORD *)&v240[4] = -1073741711;
      goto LABEL_648;
    }
    v152 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_474;
    v153 = 144;
    v154 = 67311872;
LABEL_469:
    WPP_SF_Dd(*((_QWORD *)v152 + 2), v153, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids, v154, v151);
    goto LABEL_648;
  }
  Target = KdcTelemetry::GetTarget(v348);
  v286 = v405;
  v155 = v258;
  if ( !v258 )
    v155 = 2;
  v258 = v155;
  if ( v155 == 3 && !_KDC_TICKET_INFO::IsAnyKrbtgt((_KDC_TICKET_INFO *)v348) && (v360 & 0x400) == 0 )
    goto LABEL_512;
  if ( !v249 )
  {
    v157 = WPP_GLOBAL_Control;
    goto LABEL_486;
  }
  v157 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control )
  {
LABEL_486:
    v158 = v260;
    goto LABEL_487;
  }
  v158 = v260;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 145, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids, v260);
    v157 = WPP_GLOBAL_Control;
  }
LABEL_487:
  if ( v158 < 0 )
  {
    LsaIModifyPerformanceCounter(14, 0, 0);
    v157 = WPP_GLOBAL_Control;
  }
  if ( v157 != (CSecurityData *)&WPP_GLOBAL_Control && (*((_DWORD *)v157 + 7) & 0x8000) != 0 )
    WPP_SF_d(*((_QWORD *)v157 + 2), 146, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids, 67311922);
  memset_0(v437, 0, 0x48u);
  KdcMakeAccountSid(v437, *((_DWORD *)v243 + 68));
  IsAnyKrbtgt = _KDC_TICKET_INFO::IsAnyKrbtgt((_KDC_TICKET_INFO *)v348);
  if ( IsAnyKrbtgt || (v160 = 1, (v360 & 0x400) != 0) )
    v160 = 0;
  if ( (_BYTE)KdcGlobalDisableResourceGroupsFields || (v161 = 0, (v359 & 0x80000) != 0) )
    v161 = 1;
  LOBYTE(v229) = v160;
  LOBYTE(v228) = BYTE1(v316) & 1;
  LOBYTE(v227) = v161;
  LOBYTE(v226) = !IsAnyKrbtgt;
  v225 = (union _LARGE_INTEGER *)v348;
  v224 = 0;
  PacAuthData = KdcGetPacAuthData(v243, &v296, v137, v331);
  ClientNetbiosAddress = PacAuthData;
  if ( PacAuthData )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_DZD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        147,
        (unsigned int)WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids,
        67311960,
        (__int64)&v304,
        PacAuthData);
    v292 = v298;
    goto LABEL_647;
  }
  v292 = v298;
  if ( !v298 )
  {
    v100 = *(struct KERB_KDC_REQUEST_preauth_data_s **)&v279[1];
    v149 = v251;
LABEL_512:
    LODWORD(v35) = 0;
    goto LABEL_513;
  }
  v432 = v298;
  LODWORD(v35) = 0;
  v292 = 0;
  v427 |= 0x10u;
  if ( !v160 )
  {
    v100 = *(struct KERB_KDC_REQUEST_preauth_data_s **)&v279[1];
    v149 = v251;
LABEL_513:
    if ( v300 )
    {
      ClientNetbiosAddress = 0;
      v167 = *(unsigned __int8 **)(v300 + 584);
      if ( v167 )
      {
        if ( *(_DWORD *)(v300 + 272) != 500 )
        {
          if ( (v427 & 0x10) != 0 )
          {
            v168 = KdcPerformA2AFromAccessCheck(
                     (struct _KDC_TICKET_INFO *)v348,
                     v167,
                     (struct KERB_ENCRYPTED_TICKET *)&v427,
                     v156,
                     (int *)&v240[4]);
            ClientNetbiosAddress = v168;
            if ( v168 )
            {
              if ( *(_BYTE *)(v300 + 568) )
              {
                if ( v168 == 12 && (*(_DWORD *)&v240[4] == -1073740781 || *(_DWORD *)&v240[4] == -1073741413) )
                  FillExtendedError(*(int *)&v240[4], 1, 1027, 6551, v149);
                goto LABEL_648;
              }
              ClientNetbiosAddress = 0;
              *(_DWORD *)&v240[4] = 0;
            }
          }
          else if ( *(_BYTE *)(v300 + 568) )
          {
            ClientNetbiosAddress = 12;
            *(_DWORD *)&v240[4] = -1073740781;
          }
        }
      }
    }
    if ( (*(_BYTE *)v266 & 8) != 0 )
      v169 = (struct PKERB_HOST_ADDRESSES_s *)*((_QWORD *)v266 + 15);
    else
      v169 = 0;
    v170 = v262;
    if ( !v262 )
      v170 = *((_DWORD *)v266 + 27);
    ClientNetbiosAddress = BuildReply(
                             (struct _KDC_TICKET_INFO *)&v304,
                             v170,
                             (struct KERB_PRINCIPAL_NAME *)v404,
                             v403,
                             v169,
                             (struct KERB_TICKET *)v402,
                             (struct KERB_ENCRYPTED_KDC_REPLY *)&v422);
    if ( ClientNetbiosAddress )
    {
LABEL_648:
      v25 = v238;
LABEL_649:
      v24 = v239;
      goto LABEL_650;
    }
    if ( (v247 & 0x1000000000000LL) != 0 )
    {
      if ( KdcGlobalRequestCompoundId )
        v359 |= 0x20000u;
      v171 = MIDL_user_allocate(0x20u);
      v172 = v171;
      v330 = v171;
      if ( !v171 )
        goto LABEL_225;
      v171[2] = 165;
      v173 = MIDL_user_allocate(4u);
      *((_QWORD *)v172 + 3) = v173;
      if ( !v173 )
        goto LABEL_225;
      *v173 = v359;
      v172[4] = 4;
      v174 = (struct KERB_KDC_REQUEST_preauth_data_s *)v172;
      v426 = (struct KERB_KDC_REQUEST_preauth_data_s *)v172;
      LOWORD(v422) = v422 | 8;
    }
    else
    {
      v174 = v426;
    }
    v175 = v260 & 0xF0000000;
    if ( (v260 & 0xF0000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 149, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids);
      }
      v176 = KdcCreatePacOptionsPaDataList(v175, &v299);
      ClientNetbiosAddress = v176;
      if ( v176 )
      {
        if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 150, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids, v176);
          v237 = v299;
          goto LABEL_648;
        }
        v27 = v299;
        v237 = v299;
        v26 = v236;
        v24 = v239;
        v25 = v238;
        goto LABEL_652;
      }
      v177 = v299;
      v237 = v299;
      *(_QWORD *)v299 = v426;
      v174 = v177;
      v426 = v177;
      LOWORD(v422) = v422 | 8;
    }
    v35 = v284;
    if ( v284 )
    {
      *(_QWORD *)v284 = v174;
      v426 = v35;
      LOWORD(v422) = v422 | 8;
      v35 = 0;
      v284 = 0;
    }
    v389 = 5;
    v390 = 11;
    v391 = v35;
    v388[0] = (_WORD)v35;
    v392 = v430;
    ClientNetbiosAddress = KdcBuildPADataAsReply(v309, v95, &v255);
    if ( ClientNetbiosAddress )
      goto LABEL_648;
    if ( v255 )
    {
      v178 = 128;
      v388[0] |= 0x80u;
      v391 = v255;
      v255 = v35;
    }
    if ( v350 == 502 || v356 != (_BYTE)v35 )
    {
      v179 = 1;
      v180 = (KerberosCryptoPolicy *)*((_QWORD *)v137 + 6);
      *((_QWORD *)v137 + 6) = v35;
      if ( v180 )
        utl::default_delete<KerberosCryptoPolicy>::operator()(v178, v180);
    }
    else
    {
      v179 = (unsigned __int8)v35;
    }
    v181 = KerbPackTicketEx((struct KERB_TICKET *)v402, v137, v355[0], v179, (struct KERB_TICKET *)v394, &v324, &v269);
    ClientNetbiosAddress = v181;
    v152 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        151,
        WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids,
        v355[0],
        v181);
      v152 = WPP_GLOBAL_Control;
    }
    v151 = ClientNetbiosAddress;
    if ( ClientNetbiosAddress )
    {
      if ( v152 == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)v152 + 28) & 1) == 0 )
        goto LABEL_648;
      v153 = 152;
      v154 = 67312255;
      goto LABEL_469;
    }
    v393 = v431;
    v182 = v280;
    if ( v280 )
    {
      if ( *((struct KERB_ENCRYPTED_KDC_REPLY_encrypted_pa_data_s **)&v332 + 1) == v35 )
      {
        Key = (struct _KERB_ENCRYPTION_KEY *)KerberosCryptoPolicy::GetKey(v95, 52, 0);
        if ( !Key )
        {
          ClientNetbiosAddress = 14;
          if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 153, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids);
            goto LABEL_648;
          }
LABEL_13:
          v24 = v239;
LABEL_14:
          v25 = v238;
          v26 = v236;
          v27 = v237;
          goto LABEL_15;
        }
        v89 = KdcBuildStrengthenedReplyKey(
                Key,
                (struct _KERB_ENCRYPTION_KEY *)v386,
                (struct _KERB_ENCRYPTION_KEY *)v400);
        ClientNetbiosAddress = v89;
        if ( v89 )
        {
          v86 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_648;
          }
          v87 = 154;
          goto LABEL_237;
        }
        v184 = (__int64 *)v400;
        goto LABEL_580;
      }
    }
    else if ( *((struct KERB_ENCRYPTED_KDC_REPLY_encrypted_pa_data_s **)&v332 + 1) == v35 )
    {
      utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::operator=(
        (__int64 *)&v271,
        (__int64 *)&v295);
LABEL_581:
      v186 = v271;
      if ( v271 )
      {
        if ( KerbFindPreAuthDataEntry(149, v100) )
        {
          v303.m128i_i64[0] = *(unsigned int *)v274;
          v303.m128i_i64[1] = *((_QWORD *)v274 + 1);
          if ( !KerberosCryptoPolicy::GetMic((__int64)v186, 56, (__int64)&v303, (__int64)&v364) )
          {
            ClientNetbiosAddress = 60;
            if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_Dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                156,
                WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids,
                60,
                -1073741069);
              goto LABEL_648;
            }
            goto LABEL_13;
          }
          DWORD2(v338) = 149;
          *(_QWORD *)&v338 = v35;
          v187 = KerbPackData(&v364, 9, v339, &v339[1]);
          ClientNetbiosAddress = v187;
          if ( v187 )
          {
            v86 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            {
              goto LABEL_648;
            }
            v87 = 157;
            v88 = v187;
            goto LABEL_232;
          }
          DWORD2(v344) = 136;
          LODWORD(v345) = (_DWORD)v35;
          *((_QWORD *)&v345 + 1) = v35;
          *(_QWORD *)&v344 = v35;
          if ( KdcGlobalAdvertiseFast == (_DWORD)v35 || !(unsigned int)KdcIsWin8FunctionalLevel() )
          {
            *(_QWORD *)&v338 = v426;
          }
          else
          {
            *(_QWORD *)&v338 = &v344;
            *(_QWORD *)&v344 = v426;
          }
          v426 = (struct KERB_KDC_REQUEST_preauth_data_s *)&v338;
          LOWORD(v422) = v422 | 8;
        }
        v188 = v313;
        if ( *((struct KERB_ENCRYPTED_KDC_REPLY_encrypted_pa_data_s **)&v332 + 1) != v35 )
          v188 = (unsigned int)v35;
        v151 = KerbPackKdcReplyBody(
                 (struct KERB_ENCRYPTED_KDC_REPLY *)&v422,
                 v186,
                 v188,
                 3u,
                 0x4Bu,
                 (struct KERB_ENCRYPTED_DATA *)v398);
        ClientNetbiosAddress = v151;
        v278 = v399;
        v250[1] = v399;
        if ( v151 )
        {
          v152 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_648;
          }
          v153 = 158;
          v154 = 67312396;
          goto LABEL_469;
        }
        if ( v239 )
        {
          v189 = v391;
          v190 = KdcBuildFastArmoredKdcReply(
                   v239,
                   (struct KERB_KDC_REPLY *)v388,
                   v182,
                   (struct _KERB_ENCRYPTION_KEY *)v386);
          KerbFreeAuthData(v189);
          ClientNetbiosAddress = v190;
          if ( v190 )
          {
            v86 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            {
              goto LABEL_648;
            }
            v87 = 159;
            v88 = v190;
            goto LABEL_232;
          }
          v182 = v280;
        }
        KdcMakeAccountSid(v436, v307);
        KdcMakeAccountSid(v435, v350);
        v279[0] = v395;
        if ( (qword_1800B2E50 & 0x100000000LL) != 0 )
        {
          v281 = 0;
          v407[0] = 0;
          v407[1] = v35;
          v409 = 0;
          v410 = 0;
          v411 = 0;
          v412 = 0;
          v413 = 0;
          v414 = 0;
          v415 = 0;
          memset_0(v408, 0, 0x88u);
          v416 = v35;
          v417 = 0;
          v275 = (__int64)&v281;
          v276 = (__int16 *)v407;
          v277 = 1;
          KdcHashTicketEncryptedPart(v397, v396, &v281);
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnhancedAuditingForKerberosEtypes>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnhancedAuditingForKerberosEtypes>::GetImpl'::`2'::impl) )
          {
            CSecurityData::GetKrbtgtTicketInfo(v191, (struct _KDC_TICKET_INFO *)v407);
            KerberosCryptoPolicy::FromKdcTicketInfo(
              (KerberosCryptoPolicy **)&v275,
              (const struct _KDC_TICKET_INFO *)v407);
            KdcEventPrincipal::KdcEventPrincipal((__int64)Sid, &v271);
            KdcEventPrincipal::KdcEventPrincipal((__int64)v420, &v294);
            KdcEventPrincipal::ForDomainController(v418);
            v303 = 0;
            KerberosCryptoPolicy::EtypeListToString(&v346, *((_QWORD *)v266 + 14));
            if ( v347.m128i_i8[0] != (_BYTE)v35 )
              v303 = v346;
            v259 = v423;
            v267 = v254;
            v192 = v256;
            if ( !v256 )
              v192 = (struct sockaddr *)&GlobalLocalhostAddress;
            LsaIAuditKdcEvent(
              672,
              &v304,
              v261,
              v436,
              v348,
              v435,
              (char *)&v247 + 4,
              v35,
              v279,
              v250,
              v192,
              v35,
              v35,
              &v334,
              v336,
              v337,
              v35,
              v35,
              v35,
              v35,
              v35,
              &v281,
              v434,
              v421,
              v419,
              &v303,
              &v259,
              &v267);
            utl::_OptionalData1<wil::unique_struct<_UNICODE_STRING,void (_UNICODE_STRING *),&void KerbFreeString(_UNICODE_STRING *),std::nullptr_t,0>,0>::~_OptionalData1<wil::unique_struct<_UNICODE_STRING,void (_UNICODE_STRING *),&void KerbFreeString(_UNICODE_STRING *),std::nullptr_t,0>,0>(&v346);
            KdcEventPrincipal::~KdcEventPrincipal((KdcEventPrincipal *)v418);
            KdcEventPrincipal::~KdcEventPrincipal((KdcEventPrincipal *)v420);
            KdcEventPrincipal::~KdcEventPrincipal((KdcEventPrincipal *)Sid);
            utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&v275);
          }
          else
          {
            v193 = v256;
            if ( !v256 )
              v193 = (struct sockaddr *)&GlobalLocalhostAddress;
            LsaIAuditKdcEvent(
              672,
              &v304,
              v261,
              v436,
              v348,
              v435,
              (char *)&v247 + 4,
              v35,
              v279,
              v250,
              v193,
              v35,
              v35,
              &v334,
              v336,
              v337,
              v35,
              v35,
              v35,
              v35,
              v35,
              &v281,
              v35,
              v35,
              v35,
              v35,
              v35,
              v35);
          }
          if ( v281.Buffer )
            MIDL_user_free(v281.Buffer);
          FreeTicketInfo((struct _KDC_TICKET_INFO *)v407);
          std::vector<unsigned int>::_Tidy((__int64)&v416);
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExtendedAuditingForKerberos>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ExtendedAuditingForKerberos>::GetImpl'::`2'::impl) )
        {
          LogGetAsExtendedAudit(
            (int)&v304,
            (int)v261,
            (int)v436,
            (int)v348,
            (__int64)v435,
            (__int64)&v247 + 4,
            (__int64)&v247,
            (__int64)v279,
            (__int64)v250,
            v256,
            (__int64)&v334,
            (__int64)v394,
            (__int64)&v422,
            (__int64)v266,
            (__int64)&v285,
            (__int64)v251,
            (__int64)v355,
            (__int64)&v250[1],
            (__int64)v182,
            (__int64)v341,
            (__int64)v240,
            (__int64)&v254,
            (__int64)&v258,
            (__int64)&v262,
            (__int64)&v240[4],
            (__int64)v243,
            (__int64)pCertContext);
          v278 = v250[1];
        }
        ClientNetbiosAddress = KerbPackData(v388, 73, v238, (char *)v238 + 8);
        v25 = v238;
        goto LABEL_649;
      }
      v194 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_225;
      v195 = 155;
LABEL_627:
      WPP_SF_(*((_QWORD *)v194 + 2), v195, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids);
      goto LABEL_225;
    }
    v184 = v331;
LABEL_580:
    v185 = (__int64 *)KerberosCryptoPolicy::FromKerberosKey(
                        (KerberosCryptoPolicy **)&v275,
                        (struct _KERB_ENCRYPTION_KEY *)v184,
                        1,
                        0);
    utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::operator=((__int64 *)&v271, v185);
    utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&v275);
    goto LABEL_581;
  }
  v163 = KdcAddTicketSignatureToPac((struct KERB_ENCRYPTED_TICKET *)&v427, v137, PacAuthData);
  ClientNetbiosAddress = v163;
  if ( !v163 )
  {
    v100 = *(struct KERB_KDC_REQUEST_preauth_data_s **)&v279[1];
    v149 = v251;
    goto LABEL_513;
  }
  v164 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v165 = 148;
    v166 = v163;
    goto LABEL_748;
  }
LABEL_750:
  utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&v271);
  utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&v294);
  utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&v295);
  v221 = hMem;
  v222 = hMem == 0;
  hMem = 0;
  if ( !v222 )
    LocalFree(v221);
  utl::_OptionalData1<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,0>::~_OptionalData1<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,0>(v341);
  std::vector<unsigned int>::_Tidy((__int64)&v362);
  std::vector<unsigned int>::_Tidy((__int64)&v319);
  return v163;
}

```

## disassembly

```asm
0x180016148  mov     rax, rsp
0x18001614b  mov     [rax+8], rbx
0x18001614f  push    rbp
0x180016150  push    rsi
0x180016151  push    rdi
0x180016152  push    r12
0x180016154  push    r13
0x180016156  push    r14
0x180016158  push    r15
0x18001615a  lea     rbp, [rax-0AA8h]
0x180016161  sub     rsp, 0BE0h
0x180016168  movaps  xmmword ptr [rax-48h], xmm6
0x18001616c  movaps  xmmword ptr [rax-58h], xmm7
0x180016170  mov     rax, cs:__security_cookie
0x180016177  xor     rax, rsp
0x18001617a  mov     [rbp+0AA0h+var_60], rax
0x180016181  mov     [rbp+0AA0h+var_A78], r9
0x180016185  mov     rbx, r8
0x180016188  mov     [rbp+0AA0h+var_A90], rdx
0x18001618c  mov     [rbp+0AA0h+var_A50], ecx
0x18001618f  mov     r15, [rbp+0AA0h+arg_58]
0x180016196  mov     [rbp+0AA0h+var_B00], r15
0x18001619a  mov     r13, [rbp+0AA0h+arg_50]
0x1800161a1  mov     [rbp+0AA0h+var_B18], r13
0x1800161a5  mov     rax, [rbp+0AA0h+arg_48]
0x1800161ac  mov     [rbp+0AA0h+var_988], rax
0x1800161b3  mov     rax, [rbp+0AA0h+arg_30]
0x1800161ba  mov     [rbp+0AA0h+var_858], rax
0x1800161c1  mov     rax, [rbp+0AA0h+arg_20]
0x1800161c8  mov     [rbp+0AA0h+var_A18], rax
0x1800161cf  mov     rax, [rbp+0AA0h+arg_78]
0x1800161d6  mov     [rbp+0AA0h+var_A38], rax
0x1800161da  mov     r12, [rbp+0AA0h+arg_38]
0x1800161e1  mov     [rbp+0AA0h+var_AB0], r12
0x1800161e5  mov     rax, [rbp+0AA0h+arg_28]
0x1800161ec  mov     [rbp+0AA0h+var_B08], rax
0x1800161f0  mov     rdi, [rbp+0AA0h+DestinationString]
0x1800161f7  mov     [rbp+0AA0h+var_A48], rdi
0x1800161fb  mov     rax, [rbp+0AA0h+arg_60]
0x180016202  mov     [rbp+0AA0h+var_9E8], rax
0x180016209  mov     rax, [rbp+0AA0h+arg_68]
0x180016210  mov     [rbp+0AA0h+var_850], rax
0x180016217  mov     rax, [rbp+0AA0h+arg_70]
0x18001621e  mov     [rbp+0AA0h+var_A10], rax
0x180016225  xor     esi, esi
0x180016227  mov     [rbp+0AA0h+var_B20], esi
0x18001622a  mov     dword ptr [rbp+0AA0h+var_AD4], esi
0x18001622d  mov     dword ptr [rbp+0AA0h+var_AF8+4], esi
0x180016230  mov     qword ptr [rbp+0AA0h+var_910.Length], rsi
0x180016237  mov     [rbp+0AA0h+var_910.Buffer], rsi
0x18001623e  xor     eax, eax
0x180016240  mov     [rbp+0AA0h+var_8D4], eax
0x180016246  mov     [rbp+0AA0h+var_8BF], eax
0x18001624c  mov     [rbp+0AA0h+var_8BB], ax
0x180016253  mov     [rbp+0AA0h+var_8B9], al
0x180016259  mov     [rbp+0AA0h+var_8A7], ax
0x180016260  mov     [rbp+0AA0h+var_8A5], al
0x180016266  mov     [rbp+0AA0h+var_89C], eax
0x18001626c  mov     r14d, 88h
0x180016272  mov     r8d, r14d; Size
0x180016275  xor     edx, edx; Val
0x180016277  lea     rcx, [rbp+0AA0h+var_900]; void *
0x18001627e  call    memset_0
0x180016283  mov     [rbp+0AA0h+var_878], rsi
0x18001628a  xorps   xmm0, xmm0
0x18001628d  movdqa  [rbp+0AA0h+var_870], xmm0
0x180016295  mov     [rbp+0AA0h+var_6F0], rsi
0x18001629c  mov     [rbp+0AA0h+var_6E8], rsi
0x1800162a3  xor     eax, eax
0x1800162a5  mov     [rbp+0AA0h+var_6B4], eax
0x1800162ab  mov     [rbp+0AA0h+var_69F], eax
0x1800162b1  mov     [rbp+0AA0h+var_69B], ax
0x1800162b8  mov     [rbp+0AA0h+var_699], al
0x1800162be  mov     [rbp+0AA0h+var_687], ax
0x1800162c5  mov     [rbp+0AA0h+var_685], al
0x1800162cb  mov     [rbp+0AA0h+var_67C], eax
0x1800162d1  mov     r8d, r14d; Size
0x1800162d4  xor     edx, edx; Val
0x1800162d6  lea     rcx, [rbp+0AA0h+var_6E0]; void *
0x1800162dd  call    memset_0
0x1800162e2  mov     [rbp+0AA0h+var_658], rsi
0x1800162e9  xorps   xmm0, xmm0
0x1800162ec  movdqa  [rbp+0AA0h+var_650], xmm0
0x1800162f4  mov     [rbp+0AA0h+var_AC8], rsi
0x1800162f8  mov     [rbp+0AA0h+var_AE8], rsi
0x1800162fc  mov     [rbp+0AA0h+var_938], rsi
0x180016303  movups  [rbp+0AA0h+var_960], xmm0
0x18001630a  xorps   xmm1, xmm1
0x18001630d  xor     eax, eax
0x18001630f  movups  xmmword ptr [rbp+0AA0h+var_810], xmm1
0x180016316  movups  [rbp+0AA0h+var_800], xmm1
0x18001631d  mov     [rbp+0AA0h+var_7F0], rax
0x180016324  movups  [rbp+0AA0h+var_570], xmm0
0x18001632b  movups  [rbp+0AA0h+var_560], xmm0
0x180016332  mov     [rbp+0AA0h+var_550], rax
0x180016339  movups  [rbp+0AA0h+var_4A0], xmm1
0x180016340  movups  [rbp+0AA0h+var_490], xmm1
0x180016347  mov     [rbp+0AA0h+var_480], rax
0x18001634e  mov     [rbp+0AA0h+var_A9C], esi
0x180016351  xor     edx, edx; Val
0x180016353  lea     r8d, [rsi+48h]; Size
0x180016357  lea     rcx, [rbp+0AA0h+var_470]; void *
0x18001635e  call    memset_0
0x180016363  xor     edx, edx; Val
0x180016365  lea     r8d, [r14+20h]; Size
0x180016369  lea     rcx, [rbp+0AA0h+var_250]; void *
0x180016370  call    memset_0
0x180016375  xor     edx, edx; Val
0x180016377  lea     r8d, [r14+28h]; Size
0x18001637b  lea     rcx, [rbp+0AA0h+var_300]; void *
0x180016382  call    memset_0
0x180016387  xor     edx, edx; Val
0x180016389  lea     r8d, [r14+10h]; Size
0x18001638d  lea     rcx, [rbp+0AA0h+var_540]; void *
0x180016394  call    memset_0
0x180016399  mov     eax, esi
0x18001639b  mov     [rbp+0AA0h+var_980], rax
0x1800163a2  mov     [rbp+0AA0h+var_948], rax
0x1800163a9  mov     [rbp+0AA0h+var_A98], rsi
0x1800163ad  mov     [rbp+0AA0h+var_9C0], rsi
0x1800163b4  mov     word ptr [rbp+0AA0h+var_7E0], si
0x1800163bb  xor     edx, edx; Val
0x1800163bd  lea     r8d, [rsi+4Eh]; Size
0x1800163c1  lea     rcx, [rbp+0AA0h+var_7E0+2]; void *
0x1800163c8  call    memset_0
0x1800163cd  mov     dword ptr [rbp+0AA0h+var_A60], esi
0x1800163d0  mov     dword ptr [rbp+0AA0h+var_A60+4], 3Ch ; '<'
0x1800163d7  mov     [rbp+0AA0h+var_AE0], rsi
0x1800163db  mov     [rbp+0AA0h+var_930], rsi
0x1800163e2  mov     [rbp+0AA0h+var_928], rsi
0x1800163e9  xorps   xmm0, xmm0
0x1800163ec  xor     eax, eax
0x1800163ee  movups  xmmword ptr [rbp+0AA0h+var_760], xmm0
0x1800163f5  movups  [rbp+0AA0h+var_750], xmm0
0x1800163fc  mov     [rbp+0AA0h+var_740], rax
0x180016403  mov     byte ptr [rbp+0AA0h+var_760], sil
0x18001640a  mov     byte ptr [rbp+0AA0h+var_740], sil
0x180016411  movups  xmmword ptr [rbp+0AA0h+var_9B8.Length], xmm0
0x180016418  xorps   xmm1, xmm1
0x18001641b  movups  xmmword ptr [rbp+0AA0h+var_628.Length], xmm1
0x180016422  movups  xmmword ptr [rbp+0AA0h+var_770.Length], xmm0
0x180016429  mov     qword ptr [rbp+0AA0h+var_990], rsi
0x180016430  mov     qword ptr [rbp+0AA0h+var_998], rsi
0x180016437  mov     qword ptr [rbp+0AA0h+var_820], rsi
0x18001643e  mov     qword ptr [rbp+0AA0h+var_A20], rsi
0x180016445  mov     qword ptr [rbp+0AA0h+var_950], rsi
0x18001644c  mov     qword ptr [rbp+0AA0h+SystemTimeAsFileTime.dwLowDateTime], rsi
0x180016453  mov     [rbp+0AA0h+var_ABC], esi
0x180016456  mov     dword ptr [rbp+0AA0h+var_AD4+4], esi
0x180016459  mov     [rbp+0AA0h+var_83C], esi
0x18001645f  mov     [rbp+0AA0h+var_840], esi
0x180016465  mov     r14d, esi
0x180016468  mov     [rbp+0AA0h+var_A7C], esi
0x18001646b  mov     [rbp+0AA0h+var_ABC+4], esi
0x18001646e  mov     dword ptr [rbp+0AA0h+var_A70], esi
0x180016471  call    ?KdcIsLHFunctionalLevel@@YAHXZ; KdcIsLHFunctionalLevel(void)
0x180016476  test    eax, eax
0x180016478  jz      short loc_180016493
0x18001647a  call    cs:__imp_LsaIIsLastInteractiveLogonInfoEnabled
0x180016480  test    eax, eax
0x180016482  jnz     short loc_18001648C
0x180016484  cmp     cs:?KdcGlobalEmitLILI@@3KA, esi; ulong KdcGlobalEmitLILI
0x18001648a  jz      short loc_180016493
0x18001648c  mov     esi, 22000201h
0x180016491  jmp     short loc_180016498
0x180016493  mov     esi, 22000001h
0x180016498  mov     [rbp+0AA0h+var_A88], esi
0x18001649b  mov     dl, 1
0x18001649d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DMSAKDC@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DMSAKDC@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DMSAKDC> `wil::Feature<__WilFeatureTraits_Feature_DMSAKDC>::GetImpl(void)'::`2'::impl
0x1800164a4  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_DMSAKDC@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DMSAKDC>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800164a9  xor     eax, eax
0x1800164ab  mov     [rbp+0AA0h+var_AF0], al
0x1800164ae  mov     [rbp+0AA0h+var_AD8], al
0x1800164b1  mov     [rbp+0AA0h+var_AF8+1], al
0x1800164b4  mov     [rbp+0AA0h+var_A68], al
0x1800164b7  mov     [rbp+0AA0h+var_AD7], al
0x1800164ba  mov     byte ptr [rbp+0AA0h+var_AA0], al
0x1800164bd  mov     [rbp+0AA0h+var_AF8], al
0x1800164c0  mov     [rbp+0AA0h+var_AEF], al
0x1800164c3  mov     [rbp+0AA0h+var_610], ax
0x1800164ca  xor     edx, edx; Val
0x1800164cc  mov     r8d, 9Eh; Size
0x1800164d2  lea     rcx, [rbp+0AA0h+var_60E]; void *
0x1800164d9  call    memset_0
0x1800164de  xor     ecx, ecx
0x1800164e0  mov     [rbp+0AA0h+pCertContext], rcx
0x1800164e4  mov     [rbp+0AA0h+pChainContext], rcx
0x1800164eb  xorps   xmm0, xmm0
0x1800164ee  movups  xmmword ptr [rbp+0AA0h+var_838], xmm0
0x1800164f5  mov     [rbp+0AA0h+hMem], rcx
0x1800164fc  mov     [rbp+0AA0h+hCertStore], rcx
0x180016503  mov     [rbp+0AA0h+var_818], rcx
0x18001650a  movups  [rbp+0AA0h+var_790], xmm0
0x180016511  movups  xmmword ptr [rbp+0AA0h+var_780], xmm0
0x180016518  xorps   xmm1, xmm1
0x18001651b  xor     eax, eax
0x18001651d  movups  [rbp+0AA0h+var_640], xmm1
0x180016524  mov     [rbp+0AA0h+var_630], rax
0x18001652b  movups  [rbp+0AA0h+var_738], xmm0
0x180016532  movups  [rbp+0AA0h+var_728], xmm0
0x180016539  mov     [rbp+0AA0h+var_B10], rcx
0x18001653d  mov     [rbp+0AA0h+var_940], rcx
0x180016544  mov     [rbp+0AA0h+var_848], rcx
0x18001654b  mov     [rbp+0AA0h+var_A40], ecx
0x18001654e  mov     [rbp+0AA0h+var_978], rcx
0x180016555  mov     [rbp+0AA0h+var_9A0], 1
0x18001655f  mov     dword ptr [rbp+0AA0h+var_A84], ecx
0x180016562  mov     [rbp+0AA0h+var_9A8], ecx
0x180016568  mov     [rbp+0AA0h+var_9A4], ecx
0x18001656e  mov     [rbp+0AA0h+var_9F8], ecx
0x180016574  mov     [rbp+0AA0h+var_968], rcx
0x18001657b  mov     [rbp+0AA0h+var_970], rcx
0x180016582  mov     [rbp+0AA0h+var_A30], rcx
0x180016586  lea     rax, [rbp+0AA0h+var_83C]
0x18001658d  mov     [rbp+0AA0h+var_240], rax
0x180016594  mov     [rbp+0AA0h+var_248], 20h ; ' '
0x18001659e  lea     rax, [rbp+0AA0h+var_840]
0x1800165a5  mov     [rbp+0AA0h+var_2B8], rax
0x1800165ac  mov     [rbp+0AA0h+var_2C0], 20h ; ' '
0x1800165b6  xor     edx, edx; SourceString
0x1800165b8  mov     rcx, rdi; DestinationString
0x1800165bb  call    cs:__imp_RtlInitUnicodeString
0x1800165c1  lea     rax, [rbp+0AA0h+var_250]
0x1800165c8  mov     [rbp+0AA0h+var_438], rax
0x1800165cf  mov     rax, r15
0x1800165d2  test    r15, r15
0x1800165d5  cmovz   rax, rbx
0x1800165d9  mov     r15, [rax+10h]
0x1800165dd  mov     qword ptr [rbp+0AA0h+var_9F4+4], r15
0x1800165e4  lea     rbx, [rax+18h]
0x1800165e8  mov     [rbp+0AA0h+var_A58], rbx
0x1800165ec  lea     rcx, [rbx+8]; struct tagASN1bitstring_t *
0x1800165f0  call    ?KerbConvertFlagsToUlong@@YAKPEBUtagASN1bitstring_t@@@Z; KerbConvertFlagsToUlong(tagASN1bitstring_t const *)
0x1800165f5  mov     dword ptr [rbp+0AA0h+var_AD4+4], eax
0x1800165f8  mov     ecx, 34h ; '4'
0x1800165fd  cmp     cs:KdcEventTraceFlag, 0
0x180016604  jz      short loc_180016647
0x180016606  movups  xmm0, cs:KdcGetASTicketGuid
0x18001660d  movdqu  [rbp+0AA0h+var_5F8], xmm0
0x180016615  mov     [rbp+0AA0h+var_60C], 1
0x18001661c  mov     [rbp+0AA0h+var_5E4], 20000h
0x180016626  mov     [rbp+0AA0h+var_610], cx
0x18001662d  mov     dword ptr [rbp+0AA0h+var_5E0], eax
0x180016633  lea     rdx, [rbp+0AA0h+var_610]
0x18001663a  mov     rcx, cs:KdcTraceLoggerHandle
0x180016641  call    cs:__imp_EtwLogTraceEvent
0x180016647  lea     rdi, WPP_GLOBAL_Control
0x18001664e  test    byte ptr [rbx], 8
0x180016651  jz      short loc_180016679
0x180016653  cmp     qword ptr [rbx+78h], 0
0x180016658  jnz     short loc_180016679
0x18001665a  mov     [rbp+0AA0h+var_B20], 0Dh
0x180016661  mov     r15, [rbp+0AA0h+var_B00]
0x180016665  mov     r12, [rbp+0AA0h+var_B08]
0x180016669  mov     r13, [rbp+0AA0h+var_B18]
0x18001666d  mov     rsi, [rbp+0AA0h+var_B10]
0x180016671  mov     eax, [rbp+0AA0h+var_B20]
0x180016674  jmp     loc_18001A20D
0x180016679  test    byte ptr [rbx], 80h
0x18001667c  jz      loc_18001A199
0x180016682  lea     rdx, [rbx+18h]; struct KERB_PRINCIPAL_NAME *
0x180016686  lea     rcx, [rbp+0AA0h+var_AE0]; struct _KERB_INTERNAL_NAME **
0x18001668a  call    ?KerbConvertPrincipalNameToKdcName@@YAJPEAPEAU_KERB_INTERNAL_NAME@@PEAUKERB_PRINCIPAL_NAME@@@Z; KerbConvertPrincipalNameToKdcName(_KERB_INTERNAL_NAME * *,KERB_PRINCIPAL_NAME *)
0x18001668f  mov     [rbp+0AA0h+var_B20], eax
0x180016692  test    eax, eax
0x180016694  jnz     loc_18001A1CD
0x18001669a  xor     r8d, r8d; struct _UNICODE_STRING *
0x18001669d  mov     rdx, [rbp+0AA0h+var_AE0]; struct _KERB_INTERNAL_NAME *
0x1800166a1  mov     rdi, [rbp+0AA0h+var_988]
0x1800166a8  mov     rcx, rdi; struct _UNICODE_STRING *
0x1800166ab  call    ?KerbConvertKdcNameToString@@YAJPEAU_UNICODE_STRING@@PEAU_KERB_INTERNAL_NAME@@0@Z; KerbConvertKdcNameToString(_UNICODE_STRING *,_KERB_INTERNAL_NAME *,_UNICODE_STRING *)
0x1800166b0  mov     [rbp+0AA0h+var_B20], eax
0x1800166b3  test    eax, eax
0x1800166b5  jnz     loc_18001A1CD
0x1800166bb  test    dword ptr [rbp+0AA0h+var_AD4+4], 0A940000Bh
0x1800166c2  jnz     short loc_18001665A
0x1800166c4  test    byte ptr [rbx], 40h
0x1800166c7  jnz     short loc_18001672F
0x1800166c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800166d0  lea     rbx, WPP_GLOBAL_Control
0x1800166d7  cmp     rcx, rbx
0x1800166da  jz      short loc_180016700
0x1800166dc  test    byte ptr [rcx+1Ch], 1
0x1800166e0  jz      short loc_180016700
0x1800166e2  lea     edx, [rax+5Ah]
0x1800166e5  mov     [rsp+0C10h+var_BF0], rdi
0x1800166ea  mov     r9d, 40311E0h
0x1800166f0  lea     r8, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids
0x1800166f7  mov     rcx, [rcx+10h]
0x1800166fb  call    WPP_SF_DZ
0x180016700  test    cs:?KDCInfoLevel@@3KA, 10000000h; ulong KDCInfoLevel
0x18001670a  jz      loc_18001665A
0x180016710  mov     dword ptr [r12], 0C00002FBh
0x180016718  mov     dword ptr [r12+4], 40311E1h
0x180016721  mov     dword ptr [r12+8], 2
0x18001672a  jmp     loc_18001665A
0x18001672f  lea     rdx, [rbx+30h]; struct KERB_PRINCIPAL_NAME *
0x180016733  lea     rcx, [rbp+0AA0h+var_928]; struct _KERB_INTERNAL_NAME **
0x18001673a  call    ?KerbConvertPrincipalNameToKdcName@@YAJPEAPEAU_KERB_INTERNAL_NAME@@PEAUKERB_PRINCIPAL_NAME@@@Z; KerbConvertPrincipalNameToKdcName(_KERB_INTERNAL_NAME * *,KERB_PRINCIPAL_NAME *)
0x18001673f  mov     [rbp+0AA0h+var_B20], eax
  ... truncated ...
```
