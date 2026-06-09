# UbpmpLaunchAction(ushort const *,_UBPM_ACTION_EXE_LAUNCH_PARAMS *,void * *,void *,ushort const *,int,int,int,ushort const *,ulong,ushort const *,void * *,ulong *,void * *,void * *,void * *,HKEY__ * *,void * *,ulong *,void * * *,unsigned __int64 *,_UBPM_TASK_HOST_APPCONTAINER_CONTEXT * *)

- ea: `0x18001eaf4`
- end: `0x18001ff20`
- name: `?UbpmpLaunchAction@@YAKPEBGPEAU_UBPM_ACTION_EXE_LAUNCH_PARAMS@@PEAPEAXPEAX0HHH0K02PEAK222PEAPEAUHKEY__@@24PEAPEAPEAXPEA_KPEAPEAU_UBPM_TASK_HOST_APPCONTAINER_CONTEXT@@@Z`
- size: `5164`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _UBPM_ACTION_EXE_LAUNCH_PARAMS *, void **, void *, wchar_t *Str, unsigned int, int, int, unsigned __int16 *, char, const unsigned __int16 *, void **, unsigned int *, void **, void **, void **, HKEY *, void **, unsigned int *, void ***, unsigned __int64 *, struct _UBPM_TASK_HOST_APPCONTAINER_CONTEXT **)`
- caller_count: `3`
- callee_count: `20`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18001bf54`
- `0x18001da20`
- `0x18002ce98`

## callees

- `0x18000f284`
- `0x18000fbf0`
- `0x1800150c0`
- `0x1800191a0`
- `0x18001af64`
- `0x18001eaf4`
- `0x1800238a0`
- `0x180026250`
- `0x180026890`
- `0x1800275bc`
- `0x180027a30`
- `0x180027fb8`
- `0x1800319e0`
- `0x1800351ec`
- `0x1800373c0`
- `0x180037440`
- `0x18003e53c`
- `0x18003e9bc`
- `0x18003ef54`
- `0x180040260`

## import_xrefs

- `msvcrt!wcschr` at `0x18001f368`
- `msvcrt!wcschr` at `0x18001f368`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001f723`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001f81b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001f90d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001f723`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001f81b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001f90d`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18001f9f9`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18001f9f9`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001f6e1`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001f6e1`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001f780`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001f879`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001f973`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001f780`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001f879`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001f973`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001fd6e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001fe10`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001fd6e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001fe10`
- `ntdll!RtlPublishWnfStateData` at `0x18001f4cc`
- `ntdll!RtlPublishWnfStateData` at `0x18001fbc3`
- `ntdll!RtlPublishWnfStateData` at `0x18001f4cc`
- `ntdll!RtlPublishWnfStateData` at `0x18001fbc3`
- `ntdll!RtlNtStatusToDosError` at `0x18001f4da`
- `ntdll!RtlNtStatusToDosError` at `0x18001fbd1`
- `ntdll!RtlNtStatusToDosError` at `0x18001f4da`
- `ntdll!RtlNtStatusToDosError` at `0x18001fbd1`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x18001efe9`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x18001efe9`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18001f09b`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18001f09b`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x18001fe48`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x18001fe48`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18001fd0e`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18001fd0e`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18001f61d`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18001f61d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001fab9`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001fab9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ef9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eff9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f0ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f322`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f537`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f582`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f62d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f740`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f794`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f838`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f889`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f92e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f983`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fa09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001facb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fc56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fc75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fd1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ef9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eff9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f0ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f322`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f537`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f582`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f62d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f740`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f794`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f838`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f889`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f92e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f983`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fa09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001facb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fc56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fc75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fd1e`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18001f523`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18001fc2d`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18001f523`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18001fc2d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001f572`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001fc46`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001f572`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001fc46`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f593`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f5cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fc67`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fe2c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001feee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f593`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f5cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fc67`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fe2c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001feee`
- `profapi!__imp_CreateEnvBlock` at `0x18001ef74`
- `profapi!__imp_CreateEnvBlock` at `0x18001ef74`
- `profapi!__imp_DestroyEnvBlock` at `0x18001feb7`
- `profapi!__imp_DestroyEnvBlock` at `0x18001feb7`
- `profapi!__imp_LoadProfileBasic` at `0x18001ee76`
- `profapi!__imp_LoadProfileBasic` at `0x18001ee76`
- `profapi!__imp_UnloadProfileBasic` at `0x18001fed9`
- `profapi!__imp_UnloadProfileBasic` at `0x18001fed9`

## pseudocode

```c
__int64 __fastcall UbpmpLaunchAction(
        const unsigned __int16 *a1,
        struct _UBPM_ACTION_EXE_LAUNCH_PARAMS *a2,
        void **a3,
        void *a4,
        wchar_t *Str,
        unsigned int a6,
        int a7,
        int a8,
        unsigned __int16 *a9,
        char a10,
        const unsigned __int16 *a11,
        void **a12,
        unsigned int *a13,
        void **a14,
        void **a15,
        void **a16,
        HKEY *a17,
        void **a18,
        unsigned int *a19,
        void ***a20,
        unsigned __int64 *a21,
        struct _UBPM_TASK_HOST_APPCONTAINER_CONTEXT **a22)
{
  const WCHAR *lpCurrentDirectory; // r14
  const unsigned __int16 *v24; // rsi
  PVOID *v26; // rdx
  DWORD v27; // ebx
  __int64 v28; // rcx
  int v29; // eax
  unsigned int *v30; // r9
  void *v31; // r13
  int v32; // r15d
  PSID v33; // r10
  unsigned __int16 *v34; // rax
  char v35; // di
  unsigned int v36; // eax
  bool v37; // cl
  unsigned int *v38; // rcx
  void **v39; // r14
  void **v40; // rax
  __int64 v41; // rax
  unsigned __int64 v42; // rax
  HANDLE *v43; // r14
  unsigned int *v44; // rax
  int v45; // eax
  char IsEnabled; // al
  char v47; // r15
  __int64 v48; // r8
  HANDLE v49; // rdx
  char LastError; // al
  PSID v51; // r14
  _QWORD *v52; // rcx
  int v53; // edx
  __int64 v54; // r14
  __int64 v55; // r8
  unsigned __int16 *v56; // r15
  __int64 v57; // r8
  _QWORD *v58; // rcx
  int v59; // edx
  const unsigned __int16 *v60; // r15
  __int64 v61; // r8
  unsigned __int16 *v62; // r15
  __int64 v63; // rax
  unsigned int v64; // ecx
  unsigned int v65; // eax
  char v66; // al
  _QWORD *v67; // rcx
  int v68; // edx
  unsigned __int64 v69; // r14
  HANDLE *v70; // rax
  _QWORD *v71; // rcx
  __int64 v72; // rdx
  __int64 v73; // r9
  NTSTATUS v74; // eax
  HANDLE v75; // rax
  void *v76; // r14
  PSID v77; // r15
  DWORD LengthSid; // ebx
  void *v79; // rax
  PSID *v80; // r15
  DWORD v81; // ebx
  void *v82; // rax
  DWORD v83; // ebx
  HANDLE v84; // rcx
  const wchar_t **v85; // rax
  const wchar_t *v86; // r8
  BOOL v87; // eax
  unsigned __int16 *v88; // r15
  DWORD AppContainerImpersonated; // eax
  NTSTATUS v90; // eax
  HANDLE v91; // rax
  void *v92; // r14
  _QWORD *v93; // rcx
  int v94; // edx
  HANDLE v95; // rcx
  HKEY *v96; // rcx
  PSID v97; // rcx
  void **v98; // rax
  __int64 v99; // rax
  __int64 v100; // rdx
  __int64 v101; // r8
  __int64 v102; // r9
  __int64 v103; // rdx
  __int64 v104; // r8
  __int64 v105; // r9
  __int64 v106; // rdx
  __int64 v107; // r8
  __int64 v108; // r9
  __int64 v109; // rdx
  __int64 v110; // r8
  __int64 v111; // r9
  __int64 v112; // rdx
  __int64 v113; // r8
  __int64 v114; // r9
  __int64 v115; // rdx
  __int64 v116; // r8
  __int64 v117; // r9
  __int64 v118; // rdx
  __int64 v119; // r8
  __int64 v120; // r9
  __int64 v121; // rdx
  __int64 v122; // r8
  __int64 v123; // r9
  char v125; // [rsp+60h] [rbp-A0h]
  bool v126; // [rsp+61h] [rbp-9Fh]
  int v127; // [rsp+64h] [rbp-9Ch]
  HANDLE *v128; // [rsp+68h] [rbp-98h]
  const WCHAR *v129; // [rsp+70h] [rbp-90h]
  LPVOID lpEnvironment; // [rsp+78h] [rbp-88h] BYREF
  int v131; // [rsp+80h] [rbp-80h]
  unsigned __int16 *v132; // [rsp+88h] [rbp-78h]
  HANDLE hObject; // [rsp+90h] [rbp-70h]
  void *v134; // [rsp+98h] [rbp-68h] BYREF
  __int64 v135; // [rsp+A0h] [rbp-60h] BYREF
  void *phNewToken; // [rsp+A8h] [rbp-58h] BYREF
  PSID pSourceSid; // [rsp+B0h] [rbp-50h]
  LPWSTR lpCommandLine; // [rsp+B8h] [rbp-48h]
  HKEY v139; // [rsp+C0h] [rbp-40h] BYREF
  void **v140; // [rsp+C8h] [rbp-38h]
  HKEY *v141; // [rsp+D0h] [rbp-30h]
  void *v142; // [rsp+D8h] [rbp-28h] BYREF
  void **v143; // [rsp+E0h] [rbp-20h] BYREF
  int v144; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v145; // [rsp+F0h] [rbp-10h]
  PSID pSid1; // [rsp+F8h] [rbp-8h]
  void **v147; // [rsp+100h] [rbp+0h]
  unsigned int *v148; // [rsp+108h] [rbp+8h]
  void **v149; // [rsp+110h] [rbp+10h]
  void **v150; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v151; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 *v152; // [rsp+128h] [rbp+28h] BYREF
  const WCHAR *v153; // [rsp+130h] [rbp+30h] BYREF
  void *v154; // [rsp+138h] [rbp+38h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int16 *v156; // [rsp+158h] [rbp+58h]
  ULONG_PTR Size; // [rsp+160h] [rbp+60h] BYREF
  PSID pSid; // [rsp+168h] [rbp+68h]
  void **v159; // [rsp+170h] [rbp+70h]
  void ***v160; // [rsp+178h] [rbp+78h]
  struct _UBPM_TASK_HOST_APPCONTAINER_CONTEXT **v161; // [rsp+180h] [rbp+80h]
  __int128 Value; // [rsp+188h] [rbp+88h] BYREF
  __int64 v163; // [rsp+198h] [rbp+98h]
  _BYTE StartupInfo[112]; // [rsp+1A0h] [rbp+A0h] BYREF
  _OWORD v165[3]; // [rsp+210h] [rbp+110h] BYREF

  lpCurrentDirectory = a11;
  v24 = Str;
  v26 = (PVOID *)a21;
  v132 = a9;
  v27 = 0;
  v28 = *((_QWORD *)a2 + 4);
  v147 = a12;
  v148 = a13;
  v159 = a14;
  v149 = a15;
  v140 = a16;
  v141 = a17;
  v150 = a18;
  v160 = a20;
  v161 = a22;
  v29 = 0;
  pSid = a4;
  v30 = a19;
  v128 = a3;
  v129 = a11;
  lpEnvironment = 0;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  if ( v28 )
  {
    LOBYTE(v29) = *(_DWORD *)(v28 + 32) == 2;
    v127 = v29;
  }
  else
  {
    v127 = 0;
  }
  v134 = 0;
  v31 = 0;
  pSourceSid = 0;
  v139 = 0;
  v154 = 0;
  v142 = 0;
  hObject = 0;
  phNewToken = 0;
  lpCommandLine = 0;
  if ( v28 )
  {
    v32 = *(_DWORD *)(v28 + 36);
    LOBYTE(a3) = *(_BYTE *)(v28 + 49);
    v33 = *(PSID *)(*(_QWORD *)(v28 + 8) + 8LL);
  }
  else
  {
    v33 = ::pSid;
    LOBYTE(a3) = 0;
    v32 = 0;
  }
  v143 = 0;
  v151 = 0;
  v152 = 0;
  v153 = 0;
  if ( v28 )
  {
    v145 = *(_QWORD *)(v28 + 104);
    v131 = *(_DWORD *)(v28 + 96);
    v34 = *(unsigned __int16 **)(v28 + 88);
    pSid1 = *(PSID *)(v28 + 80);
    v156 = v34;
  }
  else
  {
    v145 = 0;
    v131 = 0;
    v156 = 0;
    pSid1 = 0;
  }
  v35 = 1;
  v36 = *(_DWORD *)a2 - 1;
  Size = 48;
  *(_QWORD *)StartupInfo = 112;
  v37 = v36 <= 1;
  v126 = v36 <= 1;
  v144 = 0;
  v135 = 0;
  v125 = 0;
  v163 = 0;
  memset(&StartupInfo[8], 0, 52);
  *(_DWORD *)&StartupInfo[60] = (a8 != 0) + 128;
  memset(&StartupInfo[64], 0, 48);
  memset(v165, 0, sizeof(v165));
  Value = 0;
  if ( v36 > 1 )
  {
    v62 = 0;
    goto LABEL_124;
  }
  if ( v147 )
  {
    v38 = v148;
    if ( v148 )
    {
      v39 = v149;
      if ( v149 )
      {
        if ( v140 && v141 && v150 && a21 )
        {
          *v147 = 0;
          v40 = v140;
          *v38 = 0;
          *v39 = 0;
          *v40 = 0;
          *v141 = 0;
          *v150 = 0;
          v41 = *((_QWORD *)a2 + 4);
          if ( v41 )
            v42 = *(_QWORD *)(v41 + 40);
          else
            v42 = 0;
          v43 = v128;
          *a21 = v42;
          if ( v128 )
          {
            v44 = (unsigned int *)&v144;
            if ( a19 )
              v44 = a19;
            v27 = UbpmpTokenCheckHarden(a2, a1, v33, a6, a21, (_BYTE)a3, v128, v44, &v143, &v134);
            if ( v27 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                WPP_SF_Sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  95,
                  (unsigned int)WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
                  (_DWORD)Str,
                  v27);
LABEL_28:
              v31 = v134;
LABEL_245:
              v47 = v125;
              goto LABEL_246;
            }
            if ( !v127 )
            {
              v45 = LoadProfileBasic(*v128, &v139);
              if ( v45 < 0 )
              {
                v26 = &WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  WPP_SF_SL(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    96,
                    (unsigned int)WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
                    (_DWORD)Str,
                    v45);
              }
            }
            if ( v32 || (a10 & 0x10) != 0 )
            {
              v43 = v128;
              v27 = UbpmDeriveToken(*v128);
              if ( v27 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  WPP_SF_SdL(*((_QWORD *)WPP_GLOBAL_Control + 2), (_DWORD)v26, (_DWORD)a3, (_DWORD)Str, v27, v32);
                goto LABEL_28;
              }
            }
            else
            {
              v43 = v128;
            }
            v31 = v134;
          }
          IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(
                        `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl,
                        v26,
                        a3,
                        v30);
          v47 = 0;
          v48 = 0;
          if ( IsEnabled )
          {
            v49 = hObject;
            LOBYTE(v48) = v43 == 0;
            if ( hObject )
            {
LABEL_49:
              if ( (int)CreateEnvBlock(&lpEnvironment, v49, v48) < 0
                && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                LastError = GetLastError();
                WPP_SF_Sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  98,
                  (unsigned int)WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
                  (_DWORD)Str,
                  LastError);
              }
              v51 = pSid1;
              if ( pSid1 )
              {
                if ( !InitializeProcThreadAttributeList((LPPROC_THREAD_ATTRIBUTE_LIST)v165, 1u, 0, &Size) )
                {
                  v27 = GetLastError();
                  v52 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                    goto LABEL_246;
                  v53 = 99;
                  goto LABEL_58;
                }
                *(_QWORD *)&StartupInfo[104] = v165;
                LODWORD(v163) = v131;
                *((_QWORD *)&Value + 1) = v145;
                *(_QWORD *)&Value = v51;
                if ( !UpdateProcThreadAttribute((LPPROC_THREAD_ATTRIBUTE_LIST)v165, 0, 0x20009u, &Value, 0x18u, 0, 0) )
                {
                  v27 = GetLastError();
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    WPP_SF_Sd(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      101,
                      (unsigned int)WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
                      (_DWORD)Str,
                      v27);
                  v47 = 1;
                  goto LABEL_246;
                }
                v47 = 1;
                v125 = 1;
              }
              v54 = -1;
              if ( Str )
              {
                v55 = -1;
                do
                  ++v55;
                while ( Str[v55] );
                v27 = UbpmpExpandEnvironmentStrings(lpEnvironment, Str, v55, &v151);
                if ( v27 )
                {
                  v52 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                    goto LABEL_246;
                  v53 = 102;
LABEL_58:
                  WPP_SF_Sd(
                    v52[2],
                    v53,
                    (unsigned int)WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
                    (_DWORD)Str,
                    v27);
                  goto LABEL_246;
                }
                v24 = v151;
              }
              v56 = v132;
              if ( v132 || (v56 = (unsigned __int16 *)*((_QWORD *)a2 + 2), (v132 = v56) != 0) )
              {
                v57 = -1;
                do
                  ++v57;
                while ( v56[v57] );
                v27 = UbpmpExpandEnvironmentStrings(lpEnvironment, v56, v57, &v152);
                if ( v27 )
                {
                  v58 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                    goto LABEL_245;
                  v59 = 103;
                  goto LABEL_81;
                }
                v132 = v152;
              }
              v60 = a11;
              if ( a11 || (v60 = (const unsigned __int16 *)*((_QWORD *)a2 + 3), (v129 = v60) != 0) )
              {
                v61 = -1;
                do
                  ++v61;
                while ( v60[v61] );
                v27 = UbpmpExpandEnvironmentStrings(lpEnvironment, v60, v61, &v153);
                if ( v27 )
                {
                  v58 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                    goto LABEL_245;
                  v59 = 104;
                  goto LABEL_81;
                }
                v129 = v153;
              }
              v62 = v132;
              if ( UbpmUtilsStrStartWithAnother(v132, v24) )
              {
                lpCommandLine = v62;
              }
              else
              {
                v63 = -1;
                do
                  ++v63;
                while ( v24[v63] );
                v64 = 2 * v63 + 2;
                if ( v62 )
                {
                  do
                    ++v54;
                  while ( v62[v54] );
                  v65 = v64 + 2 * (v54 + 1);
                  if ( v65 < v64 )
                  {
                    v66 = 22;
                    v27 = 534;
                    v67 = WPP_GLOBAL_Control;
                    v26 = &WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                      goto LABEL_245;
                    v68 = 105;
                    goto LABEL_102;
                  }
                }
                else
                {
                  v65 = 2 * v63 + 2;
                }
                v69 = v65 + 6;
                if ( (unsigned int)v69 < v65 )
                {
                  v66 = 22;
                  v27 = 534;
                  v67 = WPP_GLOBAL_Control;
                  v26 = &WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                    goto LABEL_245;
                  v68 = 106;
                  goto LABEL_102;
                }
                lpCommandLine = (LPWSTR)UbpmAlloc((unsigned int)v69);
                v62 = lpCommandLine;
                if ( !lpCommandLine )
                {
                  v27 = GetLastError();
                  v58 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                    goto LABEL_245;
                  v59 = 107;
                  goto LABEL_81;
                }
                if ( *v24 == 34 || !wcschr(v24, 0x20u) )
                {
                  StringCbCopyW(v62, v69, v24);
                }
                else
                {
                  StringCbCopyW(v62, v69, L"\"");
                  StringCbCatW(v62, v69, v24);
                  StringCbCatW(v62, v69, L"\"");
                }
                if ( v132 )
                {
                  StringCbCatW(v62, v69, L" ");
                  StringCbCatW(v62, v69, v132);
                }
              }
              lpCurrentDirectory = v129;
              v37 = v126;
LABEL_124:
              v70 = v128;
              if ( !v128 )
              {
                switch ( *(_DWORD *)a2 )
                {
                  case 1:
                  case 2:
                    if ( CreateProcessW(
                           0,
                           v62,
                           0,
                           0,
                           0,
                           0x84404u,
                           lpEnvironment,
                           lpCurrentDirectory,
                           (LPSTARTUPINFOW)StartupInfo,
                           &ProcessInformation) )
                    {
                      *v147 = ProcessInformation.hProcess;
                      *v148 = ProcessInformation.dwProcessId;
                      *v149 = ProcessInformation.hThread;
                      *v140 = ::pSid;
                      *v141 = 0;
                      goto LABEL_245;
                    }
                    v27 = GetLastError();
                    v58 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                      goto LABEL_245;
                    v59 = 108;
                    break;
                  case 3:
                    v75 = OpenEventW(2u, 0, v24);
                    v76 = v75;
                    if ( v75 )
                    {
                      if ( SetEvent(v75) )
                      {
                        CloseHandle(v76);
                        goto LABEL_245;
                      }
                      v27 = GetLastError();
                      CloseHandle(v76);
                      v58 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                        goto LABEL_245;
                      v59 = 110;
                    }
                    else
                    {
                      v27 = GetLastError();
                      v58 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                        goto LABEL_245;
                      v59 = 109;
                    }
                    break;
                  case 4:
                    v74 = RtlPublishWnfStateData(
                            **((_QWORD **)a2 + 1),
                            0,
                            *(_QWORD *)(*((_QWORD *)a2 + 1) + 16LL),
                            *(unsigned int *)(*((_QWORD *)a2 + 1) + 8LL),
                            0);
                    v27 = RtlNtStatusToDosError(v74);
                    if ( !v27 )
                      goto LABEL_245;
                    v71 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                      goto LABEL_245;
                    v72 = 111;
LABEL_137:
                    v73 = v27;
LABEL_132:
                    WPP_SF_d(v71[2], v72, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, v73);
                    goto LABEL_245;
                  default:
                    v27 = 87;
                    v71 = WPP_GLOBAL_Control;
                    v26 = &WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                      goto LABEL_245;
                    v72 = 112;
                    v73 = 87;
                    goto LABEL_132;
                }
LABEL_81:
                WPP_SF_Sd(v58[2], v59, (unsigned int)WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, (_DWORD)v24, v27);
                goto LABEL_245;
              }
              if ( v37 )
              {
                v70 = v128;
                *(_QWORD *)&StartupInfo[16] = (unsigned __int64)L"winsta0\\default" & -(__int64)(v127 != 0);
              }
              if ( !v31 )
              {
                v77 = pSid;
                if ( pSid )
                {
                  if ( !IsValidSid(pSid) )
                  {
                    v66 = 87;
                    v27 = 87;
                    v67 = WPP_GLOBAL_Control;
                    v26 = &WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                      goto LABEL_245;
                    v68 = 113;
LABEL_102:
                    WPP_SF_Sd(
                      v67[2],
                      v68,
                      (unsigned int)WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
                      (_DWORD)v24,
                      v66);
                    goto LABEL_245;
                  }
                  LengthSid = GetLengthSid(v77);
                  v79 = UbpmAlloc(LengthSid);
                  v31 = v79;
                  if ( !v79 )
                  {
                    v27 = GetLastError();
                    v58 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                      goto LABEL_245;
                    v59 = 114;
                    goto LABEL_81;
                  }
                  if ( !CopySid(LengthSid, v79, v77) )
                  {
                    v27 = GetLastError();
                    v58 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                      goto LABEL_245;
                    v59 = 115;
                    goto LABEL_81;
                  }
                }
                else
                {
                  UbpmUtilsQueryToken(*v70, TokenLogonSid, &v154);
                  v80 = (PSID *)v154;
                  if ( !*(_DWORD *)v154 )
                  {
                    v27 = 1168;
                    v58 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                      goto LABEL_245;
                    v59 = 116;
                    goto LABEL_81;
                  }
                  v81 = GetLengthSid(*((PSID *)v154 + 1));
                  v82 = UbpmAlloc(v81);
                  v31 = v82;
                  if ( !v82 )
                  {
                    v27 = GetLastError();
                    v58 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                      goto LABEL_245;
                    v59 = 117;
                    goto LABEL_81;
                  }
                  if ( !CopySid(v81, v82, v80[1]) )
                  {
                    v27 = GetLastError();
                    v58 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                      goto LABEL_245;
                    v59 = 118;
                    goto LABEL_81;
                  }
                }
              }
              v27 = UbpmUtilsQueryToken(*v128, TokenUser, &v142);
              if ( v27 )
              {
                v58 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                  goto LABEL_245;
                v59 = 119;
                goto LABEL_81;
              }
              v83 = GetLengthSid(*(PSID *)v142);
              pSourceSid = UbpmAlloc(v83);
              if ( !pSourceSid )
              {
                v27 = GetLastError();
                v58 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                  goto LABEL_245;
                v59 = 120;
                goto LABEL_81;
              }
              if ( !CopySid(v83, pSourceSid, *(PSID *)v142) )
              {
                v27 = GetLastError();
                v58 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                  goto LABEL_245;
                v59 = 121;
                goto LABEL_81;
              }
              v84 = hObject;
              if ( !hObject )
                v84 = *v128;
              if ( !DuplicateTokenEx(v84, 0x2000000u, 0, SecurityImpersonation, TokenImpersonation, &phNewToken) )
              {
                v27 = GetLastError();
                v71 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                  goto LABEL_245;
                v72 = 122;
                goto LABEL_137;
              }
              v27 = UbpmFileAccessCheck(phNewToken);
              if ( v27 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  v85 = (const wchar_t **)*((_QWORD *)a2 + 5);
                  if ( v85 )
                    v86 = *v85;
                  else
                    v86 = L"NULL";
                  WPP_SF_SSd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    123,
                    (unsigned int)WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
                    (_DWORD)v24,
                    (__int64)v86,
                    v27);
                }
                goto LABEL_245;
              }
              v87 = SetThreadToken(0, phNewToken);
              v26 = 0;
              if ( !v87 )
              {
                v27 = GetLastError();
                v71 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                  goto LABEL_245;
                v72 = 124;
                goto LABEL_137;
              }
              v88 = v156;
              if ( v156 )
              {
                AppContainerImpersonated = UbpmpCreateAppContainerImpersonated(
                                             v156,
                                             pSourceSid,
                                             pSid1,
                                             v145,
                                             (__int64)&v135);
                v26 = 0;
                v27 = AppContainerImpersonated;
                if ( AppContainerImpersonated )
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    WPP_SF_SSd(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      125,
                      (unsigned int)WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
                      (_DWORD)v24,
                      (__int64)v88,
                      AppContainerImpersonated);
                  goto LABEL_241;
                }
              }
              switch ( *(_DWORD *)a2 )
              {
                case 1:
                case 2:
                  v95 = hObject;
                  if ( !hObject )
                    v95 = *v128;
                  if ( CreateProcessAsUserW(
                         v95,
                         0,
                         lpCommandLine,
                         0,
                         0,
                         0,
                         (v127 != 0 ? 32 : 0x4000) | 0x80404,
                         lpEnvironment,
                         v129,
                         (LPSTARTUPINFOW)StartupInfo,
                         &ProcessInformation) )
                  {
                    goto LABEL_239;
                  }
                  v27 = GetLastError();
                  v93 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                    goto LABEL_241;
                  v94 = 126;
                  break;
                case 3:
                  v91 = OpenEventW(2u, 0, v24);
                  v27 = 0;
                  v92 = v91;
                  if ( v91 )
                  {
                    if ( !SetEvent(v91) )
                      v27 = GetLastError();
                    CloseHandle(v92);
                  }
                  else
                  {
                    v27 = GetLastError();
                  }
                  if ( !v27 )
                    goto LABEL_239;
                  v93 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                    goto LABEL_241;
                  v94 = 127;
                  break;
                case 4:
                  v90 = RtlPublishWnfStateData(
                          **((_QWORD **)a2 + 1),
                          0,
                          *(_QWORD *)(*((_QWORD *)a2 + 1) + 16LL),
                          *(unsigned int *)(*((_QWORD *)a2 + 1) + 8LL),
                          0);
                  v27 = RtlNtStatusToDosError(v90);
                  if ( v27 )
                  {
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        128,
                        WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
                        v27);
                    goto LABEL_241;
                  }
LABEL_239:
                  RevertToSelf();
                  v35 = 0;
                  if ( v126 )
                  {
                    *v147 = ProcessInformation.hProcess;
                    *v148 = ProcessInformation.dwProcessId;
                    *v149 = ProcessInformation.hThread;
                    *v159 = hObject;
                    v96 = v141;
                    *v140 = v31;
                    v31 = 0;
                    *v96 = v139;
                    v97 = pSourceSid;
                    hObject = 0;
                    v139 = 0;
                    pSourceSid = 0;
                    *v150 = v97;
                    v98 = v143;
                    v143 = 0;
                    *v160 = v98;
                    v99 = v135;
                    v135 = 0;
                    *v161 = (struct _UBPM_TASK_HOST_APPCONTAINER_CONTEXT *)v99;
                  }
                  goto LABEL_241;
                default:
                  v27 = 87;
LABEL_241:
                  if ( v135 )
                    UbpmpDeleteAppContainerImpersonated(&v135, v26);
                  if ( v35 )
                    RevertToSelf();
                  goto LABEL_245;
              }
              WPP_SF_Sd(v93[2], v94, (unsigned int)WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, (_DWORD)v24, v27);
              goto LABEL_241;
            }
          }
          else
          {
            LOBYTE(v48) = v43 == 0;
          }
          if ( v43 )
            v49 = *v43;
          else
            v49 = g_Globals;
          goto LABEL_49;
        }
      }
    }
  }
  v27 = 87;
  v26 = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    goto LABEL_250;
  WPP_SF_Sd(
    *((_QWORD *)WPP_GLOBAL_Control + 2),
    94,
    (unsigned int)WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids,
    (_DWORD)Str,
    87);
  v47 = 0;
LABEL_246:
  if ( phNewToken )
  {
    CloseHandle(phNewToken);
    phNewToken = 0;
  }
  if ( v47 )
    DeleteProcThreadAttributeList((LPPROC_THREAD_ATTRIBUTE_LIST)v165);
LABEL_250:
  UBPM_MIDL_user_free(v151, v26, a3, v30);
  UBPM_MIDL_user_free(v152, v100, v101, v102);
  UBPM_MIDL_user_free(v153, v103, v104, v105);
  UBPM_MIDL_user_free(v31, v106, v107, v108);
  UBPM_MIDL_user_free(pSourceSid, v109, v110, v111);
  UBPM_MIDL_user_free(v154, v112, v113, v114);
  UBPM_MIDL_user_free(v142, v115, v116, v117);
  UBPM_MIDL_user_free(v143, v118, v119, v120);
  if ( lpCommandLine != v132 )
    UBPM_MIDL_user_free(lpCommandLine, v121, v122, v123);
  if ( lpEnvironment )
    DestroyEnvBlock();
  if ( v139 && *v128 )
    UnloadProfileBasic();
  if ( hObject )
    CloseHandle(hObject);
  return v27;
}

```

## disassembly

```asm
0x18001eaf4  push    rbp
0x18001eaf6  push    rbx
0x18001eaf7  push    rsi
0x18001eaf8  push    rdi
0x18001eaf9  push    r12
0x18001eafb  push    r13
0x18001eafd  push    r14
0x18001eaff  push    r15
0x18001eb01  lea     rbp, [rsp-158h]
0x18001eb09  sub     rsp, 258h
0x18001eb10  mov     rax, cs:__security_cookie
0x18001eb17  xor     rax, rsp
0x18001eb1a  mov     [rbp+190h+var_50], rax
0x18001eb21  mov     rax, [rbp+190h+arg_40]
0x18001eb28  xor     edi, edi
0x18001eb2a  mov     r14, [rbp+190h+arg_50]
0x18001eb31  mov     r12, rdx
0x18001eb34  mov     rsi, [rbp+190h+Str]
0x18001eb3b  mov     r11, rcx
0x18001eb3e  mov     rdx, [rbp+190h+arg_A0]
0x18001eb45  xorps   xmm0, xmm0
0x18001eb48  mov     [rbp+190h+var_208], rax
0x18001eb4c  mov     ebx, edi
0x18001eb4e  mov     rax, [rbp+190h+arg_58]
0x18001eb55  mov     rcx, [r12+20h]
0x18001eb5a  mov     [rbp+190h+var_190], rax
0x18001eb5e  mov     rax, [rbp+190h+arg_60]
0x18001eb65  mov     [rbp+190h+var_188], rax
0x18001eb69  mov     rax, [rbp+190h+arg_68]
0x18001eb70  mov     [rbp+190h+var_120], rax
0x18001eb74  mov     rax, [rbp+190h+arg_70]
0x18001eb7b  mov     [rbp+190h+var_180], rax
0x18001eb7f  mov     rax, [rbp+190h+arg_78]
0x18001eb86  mov     [rbp+190h+var_1C8], rax
0x18001eb8a  mov     rax, [rbp+190h+arg_80]
0x18001eb91  mov     [rbp+190h+var_1C0], rax
0x18001eb95  mov     rax, [rbp+190h+arg_88]
0x18001eb9c  mov     [rbp+190h+var_178], rax
0x18001eba0  mov     rax, [rbp+190h+arg_98]
0x18001eba7  mov     [rbp+190h+var_118], rax
0x18001ebab  mov     rax, [rbp+190h+arg_A8]
0x18001ebb2  mov     [rbp+190h+var_110], rax
0x18001ebb9  xor     eax, eax
0x18001ebbb  mov     [rbp+190h+pSid], r9
0x18001ebbf  mov     r9, [rbp+190h+arg_90]
0x18001ebc6  mov     [rsp+290h+var_228], r8
0x18001ebcb  mov     [rsp+290h+var_220], r14
0x18001ebd0  mov     qword ptr [rbp+190h+ProcessInformation.dwProcessId], rax
0x18001ebd4  mov     [rsp+290h+lpEnvironment], rdi
0x18001ebd9  movups  xmmword ptr [rbp+190h+ProcessInformation.hProcess], xmm0
0x18001ebdd  test    rcx, rcx
0x18001ebe0  jz      short loc_18001EBEF
0x18001ebe2  cmp     dword ptr [rcx+20h], 2
0x18001ebe6  setz    al
0x18001ebe9  mov     [rsp+290h+var_22C], eax
0x18001ebed  jmp     short loc_18001EBF3
0x18001ebef  mov     [rsp+290h+var_22C], edi
0x18001ebf3  mov     [rbp+190h+var_1F8], rdi
0x18001ebf7  mov     r13, rdi
0x18001ebfa  mov     [rbp+190h+pSourceSid], rdi
0x18001ebfe  mov     [rbp+190h+var_1D0], rdi
0x18001ec02  mov     [rbp+190h+var_158], rdi
0x18001ec06  mov     [rbp+190h+var_1B8], rdi
0x18001ec0a  mov     [rbp+190h+hObject], rdi
0x18001ec0e  mov     [rbp+190h+phNewToken], rdi
0x18001ec12  mov     [rbp+190h+lpCommandLine], rdi
0x18001ec16  test    rcx, rcx
0x18001ec19  jz      short loc_18001EC2D
0x18001ec1b  mov     rax, [rcx+8]
0x18001ec1f  mov     r15d, [rcx+24h]
0x18001ec23  mov     r8b, [rcx+31h]
0x18001ec27  mov     r10, [rax+8]
0x18001ec2b  jmp     short loc_18001EC3A
0x18001ec2d  mov     r10, cs:pSid
0x18001ec34  mov     r8b, dil
0x18001ec37  mov     r15d, edi
0x18001ec3a  mov     [rbp+190h+var_1B0], rdi
0x18001ec3e  mov     [rbp+190h+var_170], rdi
0x18001ec42  mov     [rbp+190h+var_168], rdi
0x18001ec46  mov     [rbp+190h+var_160], rdi
0x18001ec4a  test    rcx, rcx
0x18001ec4d  jz      short loc_18001EC6F
0x18001ec4f  mov     rax, [rcx+68h]
0x18001ec53  mov     [rbp+190h+var_1A0], rax
0x18001ec57  mov     eax, [rcx+60h]
0x18001ec5a  mov     [rbp+190h+var_210], eax
0x18001ec5d  mov     rax, [rcx+58h]
0x18001ec61  mov     rcx, [rcx+50h]
0x18001ec65  mov     [rbp+190h+pSid1], rcx
0x18001ec69  mov     [rbp+190h+var_138], rax
0x18001ec6d  jmp     short loc_18001EC7E
0x18001ec6f  mov     [rbp+190h+var_1A0], rdi
0x18001ec73  mov     [rbp+190h+var_210], edi
0x18001ec76  mov     [rbp+190h+var_138], rdi
0x18001ec7a  mov     [rbp+190h+pSid1], rdi
0x18001ec7e  mov     eax, [r12]
0x18001ec82  mov     edi, 1
0x18001ec87  sub     eax, edi
0x18001ec89  mov     [rbp+190h+Size], 30h ; '0'
0x18001ec91  cmp     eax, edi
0x18001ec93  mov     qword ptr [rbp+190h+StartupInfo], 70h ; 'p'
0x18001ec9e  xorps   xmm1, xmm1
0x18001eca1  movdqa  xmmword ptr [rbp+190h+StartupInfo+10h], xmm0
0x18001eca9  setbe   cl
0x18001ecac  movdqa  xmmword ptr [rbp+190h+StartupInfo+50h], xmm0
0x18001ecb4  xor     eax, eax
0x18001ecb6  mov     [rsp+290h+var_22F], cl
0x18001ecba  neg     [rbp+190h+arg_38]
0x18001ecc0  mov     [rbp+190h+var_1A8], eax
0x18001ecc3  mov     [rbp+190h+var_1F0], rax
0x18001ecc7  mov     [rsp+290h+var_230], al
0x18001eccb  mov     [rbp+190h+var_F8], rax
0x18001ecd2  mov     qword ptr [rbp+190h+StartupInfo+8], rax
0x18001ecd9  mov     qword ptr [rbp+190h+StartupInfo+20h], rax
0x18001ece0  mov     qword ptr [rbp+190h+StartupInfo+28h], rax
0x18001ece7  mov     qword ptr [rbp+190h+StartupInfo+30h], rax
0x18001ecee  mov     dword ptr [rbp+190h+StartupInfo+38h], eax
0x18001ecf4  sbb     eax, eax
0x18001ecf6  neg     eax
0x18001ecf8  movdqa  xmmword ptr [rbp+190h+StartupInfo+60h], xmm1
0x18001ed00  sub     eax, 0FFFFFF80h
0x18001ed03  mov     dword ptr [rbp+190h+StartupInfo+3Ch], eax
0x18001ed09  xor     eax, eax
0x18001ed0b  mov     qword ptr [rbp+190h+StartupInfo+40h], rax
0x18001ed12  mov     qword ptr [rbp+190h+StartupInfo+48h], rax
0x18001ed19  movups  [rbp+190h+var_80], xmm0
0x18001ed20  movups  [rbp+190h+var_70], xmm0
0x18001ed27  movups  [rbp+190h+var_60], xmm0
0x18001ed2e  movups  [rbp+190h+Value], xmm0
0x18001ed35  test    cl, cl
0x18001ed37  jz      loc_18001F43E
0x18001ed3d  mov     rax, [rbp+190h+var_190]
0x18001ed41  test    rax, rax
0x18001ed44  jz      loc_18001F3F4
0x18001ed4a  mov     rcx, [rbp+190h+var_188]
0x18001ed4e  test    rcx, rcx
0x18001ed51  jz      loc_18001F3F4
0x18001ed57  mov     r14, [rbp+190h+var_180]
0x18001ed5b  test    r14, r14
0x18001ed5e  jz      loc_18001F3F4
0x18001ed64  cmp     [rbp+190h+var_1C8], rbx
0x18001ed68  jz      loc_18001F3F4
0x18001ed6e  cmp     [rbp+190h+var_1C0], rbx
0x18001ed72  jz      loc_18001F3F4
0x18001ed78  cmp     [rbp+190h+var_178], rbx
0x18001ed7c  jz      loc_18001F3F4
0x18001ed82  test    rdx, rdx
0x18001ed85  jz      loc_18001F3F4
0x18001ed8b  mov     [rax], rbx
0x18001ed8e  mov     rax, [rbp+190h+var_1C8]
0x18001ed92  mov     [rcx], ebx
0x18001ed94  xor     ecx, ecx
0x18001ed96  mov     [r14], rcx
0x18001ed99  mov     [rax], rcx
0x18001ed9c  mov     rax, [rbp+190h+var_1C0]
0x18001eda0  mov     [rax], rcx
0x18001eda3  mov     rax, [rbp+190h+var_178]
0x18001eda7  mov     [rax], rcx
0x18001edaa  mov     rax, [r12+20h]
0x18001edaf  test    rax, rax
0x18001edb2  jz      short loc_18001EDBA
0x18001edb4  mov     rax, [rax+28h]
0x18001edb8  jmp     short loc_18001EDBD
0x18001edba  mov     rax, rcx
0x18001edbd  mov     r14, [rsp+290h+var_228]
0x18001edc2  mov     [rdx], rax
0x18001edc5  test    r14, r14
0x18001edc8  jz      loc_18001EF2F
0x18001edce  test    r9, r9
0x18001edd1  lea     rcx, [rbp+190h+var_1F8]
0x18001edd5  mov     [rsp+290h+lpProcessInformation], rcx
0x18001edda  lea     rax, [rbp+190h+var_1A8]
0x18001edde  cmovnz  rax, r9
0x18001ede2  lea     rcx, [rbp+190h+var_1B0]
0x18001ede6  mov     r9d, [rbp+190h+arg_28]
0x18001eded  mov     [rsp+290h+lpStartupInfo], rcx
0x18001edf2  mov     rcx, r12
0x18001edf5  mov     [rsp+290h+lpCurrentDirectory], rax
0x18001edfa  mov     [rsp+290h+lpReturnSize], r14
0x18001edff  mov     byte ptr [rsp+290h+lpPreviousValue], r8b
0x18001ee04  mov     r8, r10
0x18001ee07  mov     [rsp+290h+cbSize], rdx
0x18001ee0c  mov     rdx, r11
0x18001ee0f  call    UbpmpTokenCheckHarden
0x18001ee14  mov     ebx, eax
0x18001ee16  test    eax, eax
0x18001ee18  jz      short loc_18001EE58
0x18001ee1a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ee21  lea     rax, WPP_GLOBAL_Control
0x18001ee28  cmp     rcx, rax
0x18001ee2b  jz      short loc_18001EE4F
0x18001ee2d  test    [rcx+1Ch], dil
0x18001ee31  jz      short loc_18001EE4F
0x18001ee33  mov     rcx, [rcx+10h]
0x18001ee37  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x18001ee3e  mov     edx, 5Fh ; '_'
0x18001ee43  mov     dword ptr [rsp+290h+cbSize], ebx
0x18001ee47  mov     r9, rsi
0x18001ee4a  call    WPP_SF_Sd
0x18001ee4f  mov     r13, [rbp+190h+var_1F8]
0x18001ee53  jmp     loc_18001FE1C
0x18001ee58  mov     r14d, dword ptr [rbp+190h+arg_48]
0x18001ee5f  and     r14d, 10h
0x18001ee63  cmp     [rsp+290h+var_22C], r13d
0x18001ee68  jnz     short loc_18001EEBB
0x18001ee6a  mov     rcx, [rsp+290h+var_228]
0x18001ee6f  lea     rdx, [rbp+190h+var_1D0]
0x18001ee73  mov     rcx, [rcx]
0x18001ee76  call    cs:__imp_LoadProfileBasic
0x18001ee7d  nop     dword ptr [rax+rax+00h]
0x18001ee82  test    eax, eax
0x18001ee84  jns     short loc_18001EEBB
0x18001ee86  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ee8d  lea     rdx, WPP_GLOBAL_Control
0x18001ee94  cmp     rcx, rdx
0x18001ee97  jz      short loc_18001EEBB
0x18001ee99  test    [rcx+1Ch], dil
0x18001ee9d  jz      short loc_18001EEBB
0x18001ee9f  mov     rcx, [rcx+10h]
0x18001eea3  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x18001eeaa  mov     edx, 60h ; '`'
0x18001eeaf  mov     dword ptr [rsp+290h+cbSize], eax
0x18001eeb3  mov     r9, rsi
0x18001eeb6  call    WPP_SF_SL
0x18001eebb  test    r15d, r15d
0x18001eebe  jnz     short loc_18001EEC5
0x18001eec0  test    r14d, r14d
0x18001eec3  jz      short loc_18001EF26
0x18001eec5  test    dil, r15b
0x18001eec8  jnz     short loc_18001EED2
0x18001eeca  mov     edx, r13d
0x18001eecd  test    r14d, r14d
0x18001eed0  jz      short loc_18001EED4
0x18001eed2  mov     edx, edi
0x18001eed4  mov     r14, [rsp+290h+var_228]
0x18001eed9  lea     r8, [rbp+190h+hObject]
0x18001eedd  mov     rcx, [r14]; ExistingTokenHandle
0x18001eee0  call    UbpmDeriveToken
0x18001eee5  mov     ebx, eax
0x18001eee7  test    eax, eax
0x18001eee9  jz      short loc_18001EF2B
0x18001eeeb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eef2  lea     rax, WPP_GLOBAL_Control
0x18001eef9  cmp     rcx, rax
0x18001eefc  jz      loc_18001EE4F
0x18001ef02  test    [rcx+1Ch], dil
0x18001ef06  jz      loc_18001EE4F
0x18001ef0c  mov     rcx, [rcx+10h]
0x18001ef10  mov     r9, rsi
0x18001ef13  mov     dword ptr [rsp+290h+lpPreviousValue], r15d
0x18001ef18  mov     dword ptr [rsp+290h+cbSize], ebx
0x18001ef1c  call    WPP_SF_SdL
0x18001ef21  jmp     loc_18001EE4F
0x18001ef26  mov     r14, [rsp+290h+var_228]
0x18001ef2b  mov     r13, [rbp+190h+var_1F8]
0x18001ef2f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShadowAdmin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin> `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl(void)'::`2'::impl
0x18001ef36  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(void)
0x18001ef3b  xor     r15d, r15d
0x18001ef3e  mov     r8d, r15d
0x18001ef41  test    al, al
0x18001ef43  jz      short loc_18001EF57
0x18001ef45  mov     rdx, [rbp+190h+hObject]
0x18001ef49  test    r14, r14
0x18001ef4c  setz    r8b
0x18001ef50  test    rdx, rdx
0x18001ef53  jz      short loc_18001EF5E
0x18001ef55  jmp     short loc_18001EF6F
0x18001ef57  test    r14, r14
0x18001ef5a  setz    r8b
0x18001ef5e  test    r14, r14
0x18001ef61  jz      short loc_18001EF68
0x18001ef63  mov     rdx, [r14]
0x18001ef66  jmp     short loc_18001EF6F
0x18001ef68  mov     rdx, cs:?g_Globals@@3U_UBPM_GLOBAL_DATA@@A; _UBPM_GLOBAL_DATA g_Globals
0x18001ef6f  lea     rcx, [rsp+290h+lpEnvironment]
0x18001ef74  call    cs:__imp_CreateEnvBlock
0x18001ef7b  nop     dword ptr [rax+rax+00h]
0x18001ef80  test    eax, eax
0x18001ef82  jns     short loc_18001EFCC
0x18001ef84  mov     rax, cs:WPP_GLOBAL_Control
0x18001ef8b  lea     rcx, WPP_GLOBAL_Control
0x18001ef92  cmp     rax, rcx
0x18001ef95  jz      short loc_18001EFCC
0x18001ef97  test    [rax+1Ch], dil
0x18001ef9b  jz      short loc_18001EFCC
0x18001ef9d  call    cs:__imp_GetLastError
0x18001efa4  nop     dword ptr [rax+rax+00h]
0x18001efa9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001efb0  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x18001efb7  mov     edx, 62h ; 'b'
0x18001efbc  mov     dword ptr [rsp+290h+cbSize], eax
0x18001efc0  mov     r9, rsi
0x18001efc3  mov     rcx, [rcx+10h]
0x18001efc7  call    WPP_SF_Sd
0x18001efcc  mov     r14, [rbp+190h+pSid1]
0x18001efd0  test    r14, r14
0x18001efd3  jz      loc_18001F0FE
0x18001efd9  lea     r9, [rbp+190h+Size]; lpSize
0x18001efdd  xor     r8d, r8d; dwFlags
0x18001efe0  mov     edx, edi; dwAttributeCount
  ... truncated ...
```
