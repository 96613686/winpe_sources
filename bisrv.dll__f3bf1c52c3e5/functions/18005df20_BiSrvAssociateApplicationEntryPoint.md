# BiSrvAssociateApplicationEntryPoint

- ea: `0x18005df20`
- end: `0x18005f143`
- name: `BiSrvAssociateApplicationEntryPoint`
- size: `4643`
- prototype: `__int64 __fastcall(int, int, int, int, void *Buf1, unsigned int, unsigned int, __int64, __int64, int, __int64, int, __int64, __int64, __int64, unsigned int, __int64, __int64, int, __int64, size_t, __int64)`
- caller_count: `7`
- callee_count: `24`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800486fc`
- `0x18004e610`
- `0x18004ef80`
- `0x180065324`
- `0x180069890`
- `0x180087cc4`
- `0x180090d20`

## callees

- `0x1800056fc`
- `0x1800075f8`
- `0x180008598`
- `0x180009430`
- `0x1800095b0`
- `0x18000b9d0`
- `0x18000d7c0`
- `0x18000da50`
- `0x18001027c`
- `0x18002bcb8`
- `0x1800304e8`
- `0x180037500`
- `0x18004df58`
- `0x180053db0`
- `0x180057614`
- `0x18005df20`
- `0x1800789b8`
- `0x180078e24`
- `0x180084180`
- `0x1800845c0`
- `0x180094656`
- `0x180094662`
- `0x18009467a`
- `0x1800946a0`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18005e017`
- `ntdll!RtlInitUnicodeString` at `0x18005e023`
- `ntdll!RtlInitUnicodeString` at `0x18005e017`
- `ntdll!RtlInitUnicodeString` at `0x18005e023`
- `ntdll!RtlCompareUnicodeStrings` at `0x18005e3e8`
- `ntdll!RtlCompareUnicodeStrings` at `0x18005e4c8`
- `ntdll!RtlCompareUnicodeStrings` at `0x18005e3e8`
- `ntdll!RtlCompareUnicodeStrings` at `0x18005e4c8`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18005e5df`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18005e697`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18005e737`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18005e5df`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18005e697`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18005e737`
- `ntdll!RtlWaitOnAddress` at `0x18005e2f2`
- `ntdll!RtlWaitOnAddress` at `0x18005e2f2`
- `ntdll!RtlFreeHeap` at `0x18005e53b`
- `ntdll!RtlFreeHeap` at `0x18005e61f`
- `ntdll!RtlFreeHeap` at `0x18005f0a5`
- `ntdll!RtlFreeHeap` at `0x18005f0ad`
- `ntdll!RtlFreeHeap` at `0x18005f0e9`
- `ntdll!RtlFreeHeap` at `0x18005e53b`
- `ntdll!RtlFreeHeap` at `0x18005e61f`
- `ntdll!RtlFreeHeap` at `0x18005f0a5`
- `ntdll!RtlFreeHeap` at `0x18005f0ad`
- `ntdll!RtlFreeHeap` at `0x18005f0e9`
- `ntdll!RtlAllocateHeap` at `0x18005e563`
- `ntdll!RtlAllocateHeap` at `0x18005e640`
- `ntdll!RtlAllocateHeap` at `0x18005e886`
- `ntdll!RtlAllocateHeap` at `0x18005e563`
- `ntdll!RtlAllocateHeap` at `0x18005e640`
- `ntdll!RtlAllocateHeap` at `0x18005e886`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18005f104`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18005f104`
- `ntdll!RtlEqualSid` at `0x18005e390`
- `ntdll!RtlEqualSid` at `0x18005e470`
- `ntdll!RtlEqualSid` at `0x18005e390`
- `ntdll!RtlEqualSid` at `0x18005e470`
- `ntdll!RtlLengthSid` at `0x18005e54f`
- `ntdll!RtlLengthSid` at `0x18005e62c`
- `ntdll!RtlLengthSid` at `0x18005e54f`
- `ntdll!RtlLengthSid` at `0x18005e62c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18005e2b4`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18005ee2c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18005f073`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18005e2b4`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18005ee2c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18005f073`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18005e963`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18005ea95`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18005e963`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18005ea95`

## pseudocode

```c
__int64 __fastcall BiSrvAssociateApplicationEntryPoint(
        struct _GUID *a1,
        __int64 *a2,
        const WCHAR *a3,
        void *a4,
        void *Buf1,
        unsigned int a6,
        unsigned int a7,
        struct _GUID *a8,
        WCHAR *a9,
        int a10,
        WCHAR *a11,
        int a12,
        void *a13,
        struct _BI_CONDITIONAL_EVENT_INFORMATION *a14,
        __int64 a15,
        unsigned int a16,
        const UNICODE_STRING *a17,
        __int64 a18,
        int a19,
        __int64 a20,
        size_t a21,
        __int64 a22)
{
  __int64 *v23; // r13
  __int64 *Buffer; // r12
  unsigned int v25; // r15d
  char v26; // bl
  __int64 *v27; // rcx
  __int64 v28; // rax
  bool v29; // zf
  unsigned int v30; // eax
  __int64 *v31; // rcx
  __int64 v32; // rax
  unsigned int v33; // eax
  void *v34; // rsi
  int v35; // eax
  char *v36; // r14
  NTSTATUS SignedInUserSidForHoloLens; // esi
  int v38; // ebx
  char *v39; // rdi
  __int64 v40; // r13
  void *v41; // rdx
  PVOID v42; // rcx
  void *v43; // r8
  void *v44; // rbx
  SIZE_T v45; // rdi
  PVOID Heap; // rax
  struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *v47; // rcx
  _QWORD *ThreadLocalStoragePointer; // rax
  int v49; // edi
  __int64 v50; // rbx
  void *v51; // r8
  SIZE_T v52; // rbx
  PVOID v53; // rax
  struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *v54; // rcx
  _QWORD *v55; // rax
  int v56; // edi
  __int64 v57; // rbx
  _QWORD *v58; // rax
  int v59; // edi
  __int64 v60; // rbx
  PSID v61; // rbx
  unsigned int v62; // ecx
  _OWORD *packageRelativeApplicationId; // rax
  LPCWCH v64; // rax
  __int64 v65; // rax
  int v66; // r8d
  int v67; // ecx
  __int64 v68; // rsi
  int v69; // ebx
  int v70; // edx
  int v71; // eax
  __int64 *v72; // rcx
  __int64 v73; // rax
  int v74; // eax
  __int64 *v75; // rcx
  __int64 v76; // rax
  int v77; // eax
  __int64 v78; // rax
  int v79; // eax
  __int64 v80; // rax
  unsigned int v81; // eax
  _DWORD *v82; // rbx
  signed int v83; // eax
  int UserDataCount; // [rsp+20h] [rbp-E0h]
  int v86; // [rsp+48h] [rbp-B8h]
  int v87; // [rsp+48h] [rbp-B8h]
  size_t v88; // [rsp+70h] [rbp-90h]
  _BYTE v89[8]; // [rsp+80h] [rbp-80h] BYREF
  __int64 *v90; // [rsp+88h] [rbp-78h]
  int v91; // [rsp+90h] [rbp-70h] BYREF
  int v92; // [rsp+94h] [rbp-6Ch] BYREF
  int v93; // [rsp+98h] [rbp-68h] BYREF
  _DWORD v94[3]; // [rsp+9Ch] [rbp-64h] BYREF
  PSID Sid1; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v96; // [rsp+B0h] [rbp-50h] BYREF
  struct _GUID *v97; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v98; // [rsp+C0h] [rbp-40h] BYREF
  int v99[2]; // [rsp+C8h] [rbp-38h] BYREF
  void *Source1; // [rsp+D0h] [rbp-30h]
  LPCWCH lpString1; // [rsp+D8h] [rbp-28h]
  struct _UNICODE_STRING v102; // [rsp+E0h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+F0h] [rbp-10h] BYREF
  PVOID P; // [rsp+100h] [rbp+0h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+108h] [rbp+8h] BYREF
  __int64 v106; // [rsp+118h] [rbp+18h] BYREF
  PCUNICODE_STRING SourceString; // [rsp+120h] [rbp+20h]
  __int64 v108; // [rsp+128h] [rbp+28h]
  struct _BI_CONDITIONAL_EVENT_INFORMATION *v109; // [rsp+130h] [rbp+30h]
  struct _GUID *v110; // [rsp+138h] [rbp+38h]
  EVENT_DESCRIPTOR v111; // [rsp+140h] [rbp+40h] BYREF
  __int64 v112[2]; // [rsp+150h] [rbp+50h] BYREF
  __int128 v113; // [rsp+160h] [rbp+60h]
  __int64 v114; // [rsp+170h] [rbp+70h]
  _BYTE v115[400]; // [rsp+180h] [rbp+80h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+310h] [rbp+210h] BYREF
  __int16 *v117; // [rsp+320h] [rbp+220h]
  int v118; // [rsp+328h] [rbp+228h]
  int v119; // [rsp+32Ch] [rbp+22Ch]
  void *p_Sid1; // [rsp+330h] [rbp+230h]
  __int64 v121; // [rsp+338h] [rbp+238h]
  int *v122; // [rsp+340h] [rbp+240h]
  __int64 v123; // [rsp+348h] [rbp+248h]
  const unsigned __int16 *v124; // [rsp+350h] [rbp+250h]
  __int64 v125; // [rsp+358h] [rbp+258h]
  __int64 *v126; // [rsp+360h] [rbp+260h]
  __int64 v127; // [rsp+368h] [rbp+268h]
  PWSTR v128; // [rsp+370h] [rbp+270h]
  __int64 v129; // [rsp+378h] [rbp+278h] BYREF
  PWSTR v130; // [rsp+380h] [rbp+280h]
  int v131; // [rsp+388h] [rbp+288h] BYREF
  int v132; // [rsp+38Ch] [rbp+28Ch]
  __int64 *v133; // [rsp+390h] [rbp+290h]
  __int64 v134; // [rsp+398h] [rbp+298h]
  PWSTR v135; // [rsp+3A0h] [rbp+2A0h]
  __int64 v136; // [rsp+3A8h] [rbp+2A8h] BYREF
  void *v137; // [rsp+3B0h] [rbp+2B0h]
  __int64 Length; // [rsp+3B8h] [rbp+2B8h] BYREF
  struct _GUID **v139; // [rsp+3C0h] [rbp+2C0h]
  __int64 v140; // [rsp+3C8h] [rbp+2C8h]
  int *v141; // [rsp+3D0h] [rbp+2D0h]
  __int64 v142; // [rsp+3D8h] [rbp+2D8h]
  struct _EVENT_DATA_DESCRIPTOR v143; // [rsp+3E0h] [rbp+2E0h] BYREF
  __int16 *v144; // [rsp+3F0h] [rbp+2F0h]
  int v145; // [rsp+3F8h] [rbp+2F8h]
  int v146; // [rsp+3FCh] [rbp+2FCh]
  void *v147; // [rsp+400h] [rbp+300h]
  __int64 v148; // [rsp+408h] [rbp+308h]
  struct _GUID *v149; // [rsp+410h] [rbp+310h]
  __int64 v150; // [rsp+418h] [rbp+318h]
  const unsigned __int16 *v151; // [rsp+420h] [rbp+320h]
  __int64 v152; // [rsp+428h] [rbp+328h]
  PVOID *p_P; // [rsp+430h] [rbp+330h]
  __int64 v154; // [rsp+438h] [rbp+338h]
  int *v155; // [rsp+440h] [rbp+340h]
  __int64 v156; // [rsp+448h] [rbp+348h]
  __int64 *v157; // [rsp+450h] [rbp+350h]
  int v158; // [rsp+458h] [rbp+358h]
  int v159; // [rsp+45Ch] [rbp+35Ch]
  _DWORD *v160; // [rsp+460h] [rbp+360h]
  __int64 v161; // [rsp+468h] [rbp+368h]
  PWSTR v162; // [rsp+470h] [rbp+370h]
  _DWORD v163[2]; // [rsp+478h] [rbp+378h] BYREF
  __int64 *v164; // [rsp+480h] [rbp+380h]
  int v165; // [rsp+488h] [rbp+388h]
  int v166; // [rsp+48Ch] [rbp+38Ch]
  _DWORD *v167; // [rsp+490h] [rbp+390h]
  __int64 v168; // [rsp+498h] [rbp+398h]
  PWSTR v169; // [rsp+4A0h] [rbp+3A0h]
  _DWORD v170[2]; // [rsp+4A8h] [rbp+3A8h] BYREF
  unsigned int *v171; // [rsp+4B0h] [rbp+3B0h]
  __int64 v172; // [rsp+4B8h] [rbp+3B8h]
  int *v173; // [rsp+4C0h] [rbp+3C0h]
  __int64 v174; // [rsp+4C8h] [rbp+3C8h]
  _BYTE Sid2[80]; // [rsp+4D0h] [rbp+3D0h] BYREF

  v23 = a2;
  v110 = a8;
  Source1 = a13;
  v109 = a14;
  v108 = a15;
  *(_QWORD *)&v111.Id = a20;
  lpString1 = a3;
  v90 = a2;
  v97 = a1;
  v114 = a22;
  Sid1 = a4;
  SourceString = a17;
  *(_QWORD *)v99 = a9;
  v98 = (__int64)a11;
  *(_OWORD *)v112 = 0;
  v89[0] = 0;
  v113 = 0;
  v106 = 0;
  v102 = 0;
  memset_0(v115, 0, 0x182u);
  *(_QWORD *)&v94[1] = a3;
  v94[0] = 0;
  P = 0;
  v91 = 0;
  DestinationString = 0;
  Buffer = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  RtlInitUnicodeString(&v102, 0);
  if ( a17 && a17->Length )
    Buffer = (__int64 *)a17->Buffer;
  if ( a9 && a10 )
  {
    DestinationString.Buffer = a9;
    DestinationString.Length = a10;
    DestinationString.MaximumLength = a10;
  }
  if ( a11 && a12 )
  {
    v102.Buffer = a11;
    v102.Length = a12;
    v102.MaximumLength = a12;
  }
  v25 = a7;
  if ( (unsigned int)dword_1800C3098 > 4 && (qword_1800C30A8 & 2) != 0 && (qword_1800C30B0 & 2) == qword_1800C30B0 )
  {
    v26 = a6;
    v141 = &v92;
    v139 = (struct _GUID **)&v96;
    v135 = (PWSTR)&Length;
    v137 = v102.Buffer;
    Length = v102.Length;
    v92 = a7;
    v96 = a6;
    v142 = 4;
    v140 = 4;
    v136 = 2;
    if ( Buffer )
    {
      v27 = Buffer;
      v28 = -1;
      do
        v29 = *((_WORD *)Buffer + ++v28) == 0;
      while ( !v29 );
      v30 = 2 * v28 + 2;
    }
    else
    {
      v27 = &qword_1800A1670;
      v30 = 2;
    }
    v134 = v30;
    v128 = (PWSTR)&v131;
    v130 = DestinationString.Buffer;
    v131 = DestinationString.Length;
    v133 = v27;
    v129 = 2;
    v132 = 0;
    if ( v23 )
    {
      v31 = v23;
      v32 = -1;
      do
        v29 = *((_WORD *)v23 + ++v32) == 0;
      while ( !v29 );
      v33 = 2 * v32 + 2;
    }
    else
    {
      v31 = &qword_1800A1670;
      v33 = 2;
    }
    v34 = Source1;
    v127 = v33;
    *(_DWORD *)&EventDescriptor.Level = 260;
    UserData.Ptr = (ULONGLONG)off_1800C30A0;
    v126 = v31;
    v124 = &qword_1800A1850;
    v125 = 1;
    v122 = (int *)&qword_1800A1850;
    v123 = 1;
    p_Sid1 = Source1;
    v121 = 16;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 2;
    UserData.Size = *(unsigned __int16 *)off_1800C30A0;
    v117 = (__int16 *)byte_1800B43B5;
    v119 = 1;
    UserData.Reserved = 2;
    v118 = 155;
    v93 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 0xDu, &UserData);
  }
  else
  {
    v26 = a6;
    v34 = Source1;
  }
  v93 = v26 & 1;
  if ( (v26 & 1) == 0 )
  {
    while ( 1 )
    {
      v92 = dword_1800C4340;
      if ( (unsigned int)dword_1800C4340 > 1 )
        break;
      RtlWaitOnAddress(&dword_1800C4340, &v92, 4, 0);
    }
  }
  v35 = BipLookupEventByGuid(v34);
  v36 = (char *)P;
  SignedInUserSidForHoloLens = v35;
  if ( v35 < 0 )
  {
    v38 = 10;
    goto LABEL_133;
  }
  if ( !*((_QWORD *)P + 21) )
  {
    v38 = 20;
LABEL_132:
    SignedInUserSidForHoloLens = -1073741811;
    goto LABEL_133;
  }
  v39 = (char *)P + 192;
  if ( !*((_WORD *)P + 96) )
  {
    v38 = 30;
    goto LABEL_132;
  }
  SignedInUserSidForHoloLens = BipPackageIdFromOptionalFullName(&v106, v115, v23);
  if ( SignedInUserSidForHoloLens < 0 )
  {
    v38 = 40;
    goto LABEL_133;
  }
  v40 = v106;
  if ( !Sid1 || (v41 = (void *)*((_QWORD *)v36 + 21)) != 0 && RtlEqualSid(Sid1, v41) )
  {
    SignedInUserSidForHoloLens = 0;
    if ( v40
      && (LOBYTE(UserDataCount) = 1, (unsigned int)RtlCompareUnicodeStrings(v40 + 256, 65, v36 + 448, 65, UserDataCount))
      && (SignedInUserSidForHoloLens = -1073741823, (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0)
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_17ca5d936c503bb31ad083a275fee47e_Traceguids);
    }
    else if ( SignedInUserSidForHoloLens >= 0 )
    {
      goto LABEL_81;
    }
  }
  else
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_17ca5d936c503bb31ad083a275fee47e_Traceguids);
    SignedInUserSidForHoloLens = -1073741823;
  }
  if ( !(unsigned __int8)BipIsDeviceHoloLens() )
  {
    v23 = v90;
    v38 = 90;
    goto LABEL_133;
  }
  SignedInUserSidForHoloLens = BipGetSignedInUserSidForHoloLens(Sid2);
  if ( SignedInUserSidForHoloLens < 0 )
  {
    v23 = v90;
    v38 = 50;
    goto LABEL_133;
  }
  if ( Sid1 && !RtlEqualSid(Sid1, Sid2) )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_17ca5d936c503bb31ad083a275fee47e_Traceguids);
    SignedInUserSidForHoloLens = -1073741823;
    goto LABEL_64;
  }
  SignedInUserSidForHoloLens = 0;
  if ( v40 )
  {
    LOBYTE(UserDataCount) = 1;
    if ( (unsigned int)RtlCompareUnicodeStrings(v40 + 256, 65, v36 + 448, 65, UserDataCount) )
    {
      SignedInUserSidForHoloLens = -1073741823;
      v42 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_17ca5d936c503bb31ad083a275fee47e_Traceguids);
LABEL_64:
        v23 = v90;
        v38 = 60;
        goto LABEL_133;
      }
    }
  }
  if ( SignedInUserSidForHoloLens < 0 )
    goto LABEL_64;
  BipAcquireGlobalLock(v42);
  v43 = (void *)*((_QWORD *)v36 + 23);
  v44 = (void *)*((_QWORD *)v36 + 21);
  if ( v43 )
  {
    RtlFreeHeap(BipHeap, 0, v43);
    *((_QWORD *)v36 + 23) = 0;
  }
  v45 = RtlLengthSid(v44);
  Heap = RtlAllocateHeap(BipHeap, 0, v45);
  *((_QWORD *)v36 + 23) = Heap;
  if ( !Heap )
  {
    SignedInUserSidForHoloLens = -1073741801;
LABEL_71:
    BipLockWatchdogContextDisarmWatchdog(v47);
    ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
    v49 = ~(1 << dword_1800C3CB0);
    dword_1800C3CB4 = 0;
    v50 = ThreadLocalStoragePointer[(unsigned int)tls_index];
    *(_DWORD *)(v50 + 8) &= v49;
    RtlReleaseSRWLockExclusive(&BipGlobalLock);
    v23 = v90;
    *(_DWORD *)(v50 + 4) &= v49;
    v38 = 70;
    goto LABEL_133;
  }
  memcpy_0(Heap, v44, v45);
  if ( (v36[24] & 2) == 0 )
  {
    SignedInUserSidForHoloLens = BipUpdateEventCreationSidInStore(v36);
    if ( SignedInUserSidForHoloLens < 0 )
      goto LABEL_71;
  }
  BipRemoveEventFromPackage(v36);
  v51 = (void *)*((_QWORD *)v36 + 21);
  if ( v51 )
    RtlFreeHeap(BipHeap, 0, v51);
  v52 = RtlLengthSid(Sid2);
  v53 = RtlAllocateHeap(BipHeap, 0, v52);
  *((_QWORD *)v36 + 21) = v53;
  if ( !v53 )
  {
    SignedInUserSidForHoloLens = -1073741801;
LABEL_76:
    BipLockWatchdogContextDisarmWatchdog(v54);
    v55 = NtCurrentTeb()->ThreadLocalStoragePointer;
    v56 = ~(1 << dword_1800C3CB0);
    dword_1800C3CB4 = 0;
    v57 = v55[(unsigned int)tls_index];
    *(_DWORD *)(v57 + 8) &= v56;
    RtlReleaseSRWLockExclusive(&BipGlobalLock);
    v23 = v90;
    *(_DWORD *)(v57 + 4) &= v56;
    v38 = 80;
    goto LABEL_133;
  }
  memcpy_0(v53, Sid2, v52);
  SignedInUserSidForHoloLens = BipAddEventToPackage(v36);
  if ( SignedInUserSidForHoloLens < 0 )
    goto LABEL_76;
  if ( (v36[24] & 2) == 0 )
  {
    SignedInUserSidForHoloLens = BipUpdateEventUserSidInStore(v36);
    if ( SignedInUserSidForHoloLens < 0 )
      goto LABEL_76;
  }
  BipLockWatchdogContextDisarmWatchdog(v54);
  v58 = NtCurrentTeb()->ThreadLocalStoragePointer;
  v59 = ~(1 << dword_1800C3CB0);
  dword_1800C3CB4 = 0;
  v60 = v58[(unsigned int)tls_index];
  *(_DWORD *)(v60 + 8) &= v59;
  RtlReleaseSRWLockExclusive(&BipGlobalLock);
  *(_DWORD *)(v60 + 4) &= v59;
  v39 = v36 + 192;
LABEL_81:
  v61 = Sid1;
  if ( !v40 )
    v40 = (__int64)v39;
  if ( !Sid1 )
  {
    v61 = (PSID)*((_QWORD *)v36 + 21);
    Sid1 = v61;
  }
  if ( (a6 & 2) != 0 )
  {
    if ( (v36[24] & 2) != 0 )
      v25 = a7 | 2;
    else
      v25 = a7 & 0xFFFFFFFD;
  }
  v62 = v25 | 1;
  if ( (a6 & 0x80u) == 0 )
    v62 = v25;
  v25 = v62;
  SignedInUserSidForHoloLens = BipValidateAssociateParameters(
                                 v97,
                                 a6,
                                 v62,
                                 v110,
                                 (struct _BI_EVENT *)v36,
                                 v109,
                                 a16,
                                 (struct _UNICODE_STRING *)SourceString);
  if ( SignedInUserSidForHoloLens < 0 )
  {
    v23 = v90;
    v38 = 100;
    goto LABEL_133;
  }
  if ( !*(_QWORD *)v99 )
  {
    v38 = 110;
LABEL_131:
    v23 = v90;
    goto LABEL_132;
  }
  if ( (unsigned int)(a10 - 1) > 0x3FF )
  {
    v38 = 120;
    goto LABEL_131;
  }
  if ( v98 && (unsigned int)(a12 - 1) > 0x3FF )
  {
    v38 = 130;
    goto LABEL_131;
  }
  if ( v93 )
  {
    v69 = a19;
    v68 = *(_QWORD *)&v94[1];
    goto LABEL_122;
  }
  BipPackageCheckUpdateStaleFullName(v40, v61);
  BipPackageEnsureIsRegistered(0xFFFFFFFF, v61);
  LODWORD(a18) = 4;
  if ( lpString1 )
  {
    packageRelativeApplicationId = *(_OWORD **)&v94[1];
  }
  else
  {
    packageRelativeApplicationId = RtlAllocateHeap(BipHeap, 0, 0x82u);
    *(_QWORD *)&v94[1] = packageRelativeApplicationId;
    if ( !packageRelativeApplicationId )
    {
      v23 = v90;
      SignedInUserSidForHoloLens = -1073741801;
      v38 = 140;
      goto LABEL_133;
    }
    LODWORD(v61) = (_DWORD)Sid1;
    *packageRelativeApplicationId = 0;
    packageRelativeApplicationId[1] = 0;
    packageRelativeApplicationId[2] = 0;
    packageRelativeApplicationId[3] = 0;
    packageRelativeApplicationId[4] = 0;
    packageRelativeApplicationId[5] = 0;
    packageRelativeApplicationId[6] = 0;
    packageRelativeApplicationId[7] = 0;
    *((_WORD *)packageRelativeApplicationId + 64) = 0;
  }
  SignedInUserSidForHoloLens = BipGetTaskInfo(
                                 (int)v61,
                                 0,
                                 v99[0],
                                 a10,
                                 v98,
                                 a12,
                                 v40,
                                 (PCWSTR)packageRelativeApplicationId,
                                 (__int64)&a18,
                                 v86,
                                 (__int64)v94,
                                 (__int64)&v91);
  if ( SignedInUserSidForHoloLens < 0 )
  {
    v64 = lpString1;
    if ( !lpString1 )
      goto LABEL_111;
    if ( CompareStringOrdinal(lpString1, -1, L"ppleae38af2e007f4358a809ac99a64a67c1", -1, 1) == 2 )
      goto LABEL_110;
    v65 = *(_QWORD *)&v94[1];
    v66 = v99[0];
    **(_OWORD **)&v94[1] = *(_OWORD *)L"ppleae38af2e007f4358a809ac99a64a67c1";
    *(_OWORD *)(v65 + 16) = *(_OWORD *)L"af2e007f4358a809ac99a64a67c1";
    *(_OWORD *)(v65 + 32) = *(_OWORD *)L"4358a809ac99a64a67c1";
    v67 = (int)Sid1;
    *(_OWORD *)(v65 + 48) = *(_OWORD *)L"ac99a64a67c1";
    *(_OWORD *)(v65 + 58) = *(_OWORD *)L"64a67c1";
    SignedInUserSidForHoloLens = BipGetTaskInfo(
                                   v67,
                                   0,
                                   v66,
                                   a10,
                                   v98,
                                   a12,
                                   v40,
                                   (PCWSTR)v65,
                                   (__int64)&a18,
                                   v87,
                                   (__int64)v94,
                                   (__int64)&v91);
    if ( SignedInUserSidForHoloLens < 0 )
    {
LABEL_110:
      v64 = lpString1;
LABEL_111:
      if ( (v25 & 0x20) == 0 || !v64 )
      {
        v23 = v90;
        v38 = 150;
        goto LABEL_133;
      }
      LODWORD(a18) = 4;
      v94[0] = 0;
      v91 = 0;
      goto LABEL_114;
    }
  }
  if ( (_DWORD)a18 == 1 && memcmp_0(Buf1, &GUID_NULL, 0x10u) )
  {
    v68 = *(_QWORD *)&v94[1];
    if ( CompareStringOrdinal(*(LPCWCH *)&v94[1], -1, L"ppleae38af2e007f4358a809ac99a64a67c1", -1, 1) != 2 )
    {
      v38 = 160;
      goto LABEL_131;
    }
    goto LABEL_115;
  }
LABEL_114:
  v68 = *(_QWORD *)&v94[1];
LABEL_115:
  v69 = (v94[0] & 1) != 0;
LABEL_122:
  if ( v108 )
  {
    v70 = *(_DWORD *)v108;
    if ( (*(_DWORD *)v108 == 718 || (unsigned int)(v70 - 300) <= 0xC7 || v70 == 702)
      && (int)BipIsVoipPackage(v40, v89, &v91) >= 0
      && v89[0] )
    {
      v69 |= 2u;
    }
  }
  v25 &= ~0x20u;
  v112[0] = *(_QWORD *)v99;
  *(_QWORD *)&v113 = __PAIR64__(a12, a10);
  v112[1] = v98;
  *((_QWORD *)&v113 + 1) = __PAIR64__(v69, a18);
  LODWORD(v88) = a21;
  v71 = BipWorkItemCreate(
          (int)v97,
          a6,
          v25,
          (int)v110,
          0,
          (__int64)v112,
          (__int64)v36,
          (__int64)v109,
          v108,
          a16,
          SourceString,
          v68,
          v69,
          *(__int64 *)&v111.Id,
          v88);
  v23 = v90;
  SignedInUserSidForHoloLens = v71;
  v38 = (v71 >> 31) & 0xAA;
LABEL_133:
  if ( (unsigned int)dword_1800C3098 > 4 && (qword_1800C30A8 & 3) != 0 && (qword_1800C30B0 & 3) == qword_1800C30B0 )
  {
    v96 = a6;
    v173 = &v93;
    v171 = &v96;
    v167 = v170;
    v169 = v102.Buffer;
    v170[0] = v102.Length;
    v93 = v25;
    v92 = v38;
    LODWORD(P) = SignedInUserSidForHoloLens;
    v174 = 4;
    v172 = 4;
    v168 = 2;
    v170[1] = 0;
    if ( Buffer )
    {
      v72 = Buffer;
      v73 = -1;
      do
        v29 = *((_WORD *)Buffer + ++v73) == 0;
      while ( !v29 );
      v74 = 2 * v73 + 2;
    }
    else
    {
      v72 = &qword_1800A1670;
      v74 = 2;
    }
    v165 = v74;
    v160 = v163;
    v162 = DestinationString.Buffer;
    v163[0] = DestinationString.Length;
    v164 = v72;
    v166 = 0;
    v161 = 2;
    v163[1] = 0;
    if ( v23 )
    {
      v75 = v23;
      v76 = -1;
      do
        v29 = *((_WORD *)v23 + ++v76) == 0;
      while ( !v29 );
      v77 = 2 * v76 + 2;
    }
    else
    {
      v75 = &qword_1800A1670;
      v77 = 2;
    }
    v158 = v77;
    v157 = v75;
    v155 = &v92;
    v152 = 1;
    p_P = &P;
    v159 = 0;
    v151 = &qword_1800A1850;
    v149 = v97;
    v147 = Source1;
    *(_DWORD *)&EventDescriptor.Level = 516;
    v143.Ptr = (ULONGLONG)off_1800C30A0;
    v156 = 4;
    v154 = 4;
    v150 = 16;
    v148 = 16;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 3;
    v143.Size = *(unsigned __int16 *)off_1800C30A0;
    v144 = &word_1800B3F7E;
    v146 = 1;
    v143.Reserved = 2;
    v145 = 179;
    LODWORD(v97) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 0xFu, &v143);
  }
  if ( SignedInUserSidForHoloLens < 0
    && (unsigned int)dword_1800C3098 > 2
    && (qword_1800C30A8 & 0x400000000000LL) != 0
    && (qword_1800C30B0 & 0x400000000000LL) == qword_1800C30B0 )
  {
    LODWORD(v98) = a6;
    v141 = (int *)Source1;
    v139 = &v97;
    v137 = &v98;
    v133 = &v136;
    v135 = v102.Buffer;
    v136 = v102.Length;
    LODWORD(v97) = v25;
    v99[0] = v38;
    LODWORD(Sid1) = SignedInUserSidForHoloLens;
    v142 = 16;
    v140 = 4;
    Length = 4;
    v134 = 2;
    if ( Buffer )
    {
      v78 = -1;
      do
        v29 = *((_WORD *)Buffer + ++v78) == 0;
      while ( !v29 );
      v79 = 2 * v78 + 2;
    }
    else
    {
      Buffer = &qword_1800A1670;
      v79 = 2;
    }
    v131 = v79;
    v126 = &v129;
    v128 = DestinationString.Buffer;
    v129 = DestinationString.Length;
    v130 = (PWSTR)Buffer;
    v132 = 0;
    v127 = 2;
    if ( v23 )
    {
      v80 = -1;
      do
        v29 = *((_WORD *)v23 + ++v80) == 0;
      while ( !v29 );
      v81 = 2 * v80 + 2;
    }
    else
    {
      v23 = &qword_1800A1670;
      v81 = 2;
    }
    v125 = v81;
    v122 = v99;
    v111.Keyword = 0x400000000000LL;
    p_Sid1 = &Sid1;
    *(_DWORD *)&v111.Level = 2;
    UserData.Ptr = (ULONGLONG)off_1800C30A0;
    v124 = (const unsigned __int16 *)v23;
    v123 = 4;
    v121 = 4;
    *(_DWORD *)&v111.Id = 184549376;
    UserData.Size = *(unsigned __int16 *)off_1800C30A0;
    v117 = &word_1800B408E;
    UserData.Reserved = 2;
    v118 = 159;
    v119 = 1;
    LODWORD(v90) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &v111, 0, 0, 0xDu, &UserData);
  }
  if ( v36 && _InterlockedExchangeAdd((volatile signed __int32 *)v36 + 7, 0xFFFFFFFF) == 1 )
  {
    if ( *((_DWORD *)v36 + 12) == 1 )
    {
      BipEventQueueDestroy((struct _BI_LOCK *)&qword_1800C4600);
    }
    else if ( *((_DWORD *)v36 + 12) == 2 )
    {
      BipWorkItemCheckQueueDestroy((struct _BI_WORK_ITEM *)v36);
    }
    else
    {
      RtlFreeHeap(BipHeap, 0, v36);
    }
  }
  if ( *(_QWORD *)&v94[1] && *(LPCWCH *)&v94[1] != lpString1 )
    RtlFreeHeap(BipHeap, 0, *(PVOID *)&v94[1]);
  v82 = (_DWORD *)v114;
  if ( v114 )
  {
    if ( SignedInUserSidForHoloLens < 0 && v91 >= 0 )
    {
      v83 = RtlNtStatusToDosErrorNoTeb(SignedInUserSidForHoloLens);
      if ( v83 > 0 )
        v83 = (unsigned __int16)v83 | 0x80070000;
      v91 = v83;
    }
    *v82 = v91;
  }
  return (unsigned int)SignedInUserSidForHoloLens;
}

```

## disassembly

```asm
0x18005df20  push    rbp
0x18005df22  push    rbx
0x18005df23  push    rsi
0x18005df24  push    rdi
0x18005df25  push    r12
0x18005df27  push    r13
0x18005df29  push    r14
0x18005df2b  push    r15
0x18005df2d  lea     rbp, [rsp-438h]
0x18005df35  sub     rsp, 538h
0x18005df3c  mov     rax, cs:__security_cookie
0x18005df43  xor     rax, rsp
0x18005df46  mov     [rbp+470h+var_50], rax
0x18005df4d  mov     rax, [rbp+470h+arg_38]
0x18005df54  xorps   xmm0, xmm0
0x18005df57  mov     rsi, [rbp+470h+arg_80]
0x18005df5e  mov     r14, r8
0x18005df61  mov     rbx, [rbp+470h+arg_40]
0x18005df68  mov     r13, rdx
0x18005df6b  mov     rdi, [rbp+470h+arg_50]
0x18005df72  xor     r15d, r15d
0x18005df75  mov     [rbp+470h+var_438], rax
0x18005df79  mov     rax, [rbp+470h+arg_60]
0x18005df80  mov     [rbp+470h+Source1], rax
0x18005df84  mov     rax, [rbp+470h+arg_68]
0x18005df8b  mov     [rbp+470h+var_440], rax
0x18005df8f  mov     rax, [rbp+470h+arg_70]
0x18005df96  mov     [rbp+470h+var_448], rax
0x18005df9a  mov     rax, [rbp+470h+arg_98]
0x18005dfa1  mov     qword ptr [rbp+470h+var_430.Id], rax
0x18005dfa5  mov     rax, [rbp+470h+arg_A8]
0x18005dfac  mov     [rbp+470h+lpString1], r8
0x18005dfb0  mov     r8d, 182h; Size
0x18005dfb6  mov     [rbp+470h+var_4E8], rdx
0x18005dfba  xor     edx, edx; Val
0x18005dfbc  mov     [rbp+470h+var_4B8], rcx
0x18005dfc0  lea     rcx, [rbp+470h+var_3F0]; void *
0x18005dfc7  mov     [rbp+470h+var_400], rax
0x18005dfcb  mov     [rbp+470h+Sid1], r9
0x18005dfcf  mov     [rbp+470h+var_450], rsi
0x18005dfd3  mov     qword ptr [rbp+470h+var_4A8], rbx
0x18005dfd7  mov     [rbp+470h+var_4B0], rdi
0x18005dfdb  movups  xmmword ptr [rbp+470h+var_420], xmm0
0x18005dfdf  mov     [rbp+470h+var_4F0], 0
0x18005dfe3  movups  [rbp+470h+var_410], xmm0
0x18005dfe7  mov     [rbp+470h+var_458], r15
0x18005dfeb  movups  xmmword ptr [rbp+470h+var_490.Length], xmm0
0x18005dfef  call    memset_0
0x18005dff4  xorps   xmm0, xmm0
0x18005dff7  mov     qword ptr [rbp+470h+var_4D4+4], r14
0x18005dffb  xor     r14d, r14d
0x18005dffe  mov     dword ptr [rbp+470h+var_4D4], r15d
0x18005e002  xor     edx, edx; SourceString
0x18005e004  mov     [rbp+470h+P], r14
0x18005e008  lea     rcx, [rbp+470h+DestinationString]; DestinationString
0x18005e00c  mov     dword ptr [rbp+470h+var_4E0], r14d
0x18005e010  movups  xmmword ptr [rbp+470h+DestinationString.Length], xmm0
0x18005e014  mov     r12d, r14d
0x18005e017  call    cs:__imp_RtlInitUnicodeString
0x18005e01d  xor     edx, edx; SourceString
0x18005e01f  lea     rcx, [rbp+470h+var_490]; DestinationString
0x18005e023  call    cs:__imp_RtlInitUnicodeString
0x18005e029  test    rsi, rsi
0x18005e02c  jz      short loc_18005E038
0x18005e02e  cmp     [rsi], r14w
0x18005e032  jbe     short loc_18005E038
0x18005e034  mov     r12, [rsi+8]
0x18005e038  test    rbx, rbx
0x18005e03b  jz      short loc_18005E053
0x18005e03d  mov     eax, [rbp+470h+arg_48]
0x18005e043  test    eax, eax
0x18005e045  jz      short loc_18005E053
0x18005e047  mov     [rbp+470h+DestinationString.Buffer], rbx
0x18005e04b  mov     [rbp+470h+DestinationString.Length], ax
0x18005e04f  mov     [rbp+470h+DestinationString.MaximumLength], ax
0x18005e053  test    rdi, rdi
0x18005e056  jz      short loc_18005E06E
0x18005e058  mov     eax, [rbp+470h+arg_58]
0x18005e05e  test    eax, eax
0x18005e060  jz      short loc_18005E06E
0x18005e062  mov     [rbp+470h+var_490.Buffer], rdi
0x18005e066  mov     [rbp+470h+var_490.Length], ax
0x18005e06a  mov     [rbp+470h+var_490.MaximumLength], ax
0x18005e06e  mov     eax, cs:dword_1800C3098
0x18005e074  lea     r8, qword_1800A1850
0x18005e07b  mov     r15d, [rbp+470h+arg_30]
0x18005e082  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18005e089  lea     r9, _TraceLoggingMetadata
0x18005e090  mov     edx, 1
0x18005e095  cmp     eax, 4
0x18005e098  jbe     loc_18005E2BC
0x18005e09e  mov     rcx, cs:qword_1800C30B0
0x18005e0a5  mov     rax, cs:qword_1800C30A8
0x18005e0ac  test    al, 2
0x18005e0ae  jz      loc_18005E2BC
0x18005e0b4  mov     rax, rcx
0x18005e0b7  and     eax, 2
0x18005e0ba  cmp     rax, rcx
0x18005e0bd  jnz     loc_18005E2BC
0x18005e0c3  mov     ebx, [rbp+470h+arg_28]
0x18005e0c9  lea     rax, [rbp+470h+var_4E0+4]
0x18005e0cd  mov     [rbp+470h+var_1A0], rax
0x18005e0d4  lea     rax, [rbp+470h+var_4C0]
0x18005e0d8  mov     [rbp+470h+var_1B0], rax
0x18005e0df  lea     rax, [rbp+470h+var_1B8]
0x18005e0e6  mov     [rbp+470h+var_1D0], rax
0x18005e0ed  mov     rax, [rbp+470h+var_490.Buffer]
0x18005e0f1  mov     [rbp+470h+var_1C0], rax
0x18005e0f8  movzx   eax, [rbp+470h+var_490.Length]
0x18005e0fc  mov     dword ptr [rbp+470h+var_1B8], eax
0x18005e102  mov     dword ptr [rbp+470h+var_4E0+4], r15d
0x18005e106  mov     [rbp+470h+var_4C0], ebx
0x18005e109  mov     [rbp+470h+var_198], 4
0x18005e114  mov     [rbp+470h+var_1A8], 4
0x18005e11f  mov     [rbp+470h+var_1C8], 2
0x18005e12a  mov     dword ptr [rbp+470h+var_1B8+4], r14d
0x18005e131  test    r12, r12
0x18005e134  jz      short loc_18005E155
0x18005e136  mov     rcx, r12
0x18005e139  mov     rax, rdi
0x18005e13c  nop     dword ptr [rax+00h]
0x18005e140  cmp     [r12+rax*2+2], r14w
0x18005e146  lea     rax, [rax+1]
0x18005e14a  jnz     short loc_18005E140
0x18005e14c  lea     eax, ds:2[rax*2]
0x18005e153  jmp     short loc_18005E161
0x18005e155  lea     rcx, qword_1800A1670
0x18005e15c  mov     eax, 2
0x18005e161  mov     dword ptr [rbp+470h+var_1D8], eax
0x18005e167  lea     rax, [rbp+470h+var_1E8]
0x18005e16e  mov     [rbp+470h+var_200], rax
0x18005e175  mov     rax, [rbp+470h+DestinationString.Buffer]
0x18005e179  mov     [rbp+470h+var_1F0], rax
0x18005e180  movzx   eax, [rbp+470h+DestinationString.Length]
0x18005e184  mov     [rbp+470h+var_1E8], eax
0x18005e18a  mov     [rbp+470h+var_1E0], rcx
0x18005e191  mov     dword ptr [rbp+470h+var_1D8+4], r14d
0x18005e198  mov     [rbp+470h+var_1F8], 2
0x18005e1a3  mov     [rbp+470h+var_1E4], r14d
0x18005e1aa  test    r13, r13
0x18005e1ad  jz      short loc_18005E1D5
0x18005e1af  mov     rcx, r13
0x18005e1b2  mov     rax, rdi
0x18005e1b5  nop     word ptr [rax+rax+00000000h]
0x18005e1c0  cmp     [r13+rax*2+2], r14w
0x18005e1c6  lea     rax, [rax+1]
0x18005e1ca  jnz     short loc_18005E1C0
0x18005e1cc  lea     eax, ds:2[rax*2]
0x18005e1d3  jmp     short loc_18005E1E1
0x18005e1d5  lea     rcx, qword_1800A1670
0x18005e1dc  mov     eax, 2
0x18005e1e1  mov     rsi, [rbp+470h+Source1]
0x18005e1e5  mov     dword ptr [rbp+470h+var_208], eax
0x18005e1eb  movzx   eax, cs:word_1800B43AB
0x18005e1f2  mov     dword ptr [rbp+470h+EventDescriptor.Level], eax
0x18005e1f5  mov     rax, cs:off_1800C30A0
0x18005e1fc  mov     [rbp+470h+var_260.Ptr], rax
0x18005e203  mov     [rbp+470h+var_210], rcx
0x18005e20a  mov     [rbp+470h+var_220], r8
0x18005e211  mov     [rbp+470h+var_218], rdx
0x18005e218  mov     [rbp+470h+var_230], r8
0x18005e21f  xor     r8d, r8d; ActivityId
0x18005e222  mov     [rbp+470h+var_228], rdx
0x18005e229  mov     dword ptr [rbp+470h+var_208+4], r14d
0x18005e230  mov     [rbp+470h+var_240], rsi
0x18005e237  mov     [rbp+470h+var_238], 10h
0x18005e242  mov     dword ptr [rbp+470h+EventDescriptor.Id], 0B000000h
0x18005e249  mov     [rbp+470h+EventDescriptor.Keyword], 2
0x18005e251  movzx   eax, word ptr [rax]
0x18005e254  mov     [rbp+470h+var_260.Size], eax
0x18005e25a  lea     rax, byte_1800B43B5
0x18005e261  mov     [rbp+470h+var_250], rax
0x18005e268  lea     rax, _TraceLoggingMetadataEnd
0x18005e26f  sub     eax, r9d
0x18005e272  mov     [rbp+470h+var_244], edx
0x18005e278  mov     dword ptr [rbp+470h+var_260.0Ch], 2
0x18005e282  lea     rdx, [rbp+470h+EventDescriptor]; EventDescriptor
0x18005e286  mov     [rbp+470h+var_248], 9Bh
0x18005e290  xor     r9d, r9d; RelatedActivityId
0x18005e293  mov     [rbp+470h+var_4D8], eax
0x18005e296  mov     eax, [rbp+470h+var_4D8]
0x18005e299  mov     rcx, cs:RegHandle; RegHandle
0x18005e2a0  lea     rax, [rbp+470h+var_260]
0x18005e2a7  mov     [rsp+570h+UserData], rax; UserData
0x18005e2ac  mov     [rsp+570h+UserDataCount], 0Dh; UserDataCount
0x18005e2b4  call    cs:__imp_EventWriteTransfer
0x18005e2ba  jmp     short loc_18005E2C6
0x18005e2bc  mov     ebx, [rbp+470h+arg_28]
0x18005e2c2  mov     rsi, [rbp+470h+Source1]
0x18005e2c6  mov     eax, ebx
0x18005e2c8  and     eax, 1
0x18005e2cb  mov     [rbp+470h+var_4D8], eax
0x18005e2ce  jnz     short loc_18005E2FA
0x18005e2d0  mov     eax, cs:dword_1800C4340
0x18005e2d6  mov     dword ptr [rbp+470h+var_4E0+4], eax
0x18005e2d9  cmp     eax, 1
0x18005e2dc  ja      short loc_18005E2FA
0x18005e2de  xor     r9d, r9d
0x18005e2e1  lea     rdx, [rbp+470h+var_4E0+4]
0x18005e2e5  mov     r8d, 4
0x18005e2eb  lea     rcx, dword_1800C4340
0x18005e2f2  call    cs:__imp_RtlWaitOnAddress
0x18005e2f8  jmp     short loc_18005E2D0
0x18005e2fa  lea     rdx, [rbp+470h+P]
0x18005e2fe  mov     rcx, rsi; Source1
0x18005e301  call    BipLookupEventByGuid
0x18005e306  mov     r14, [rbp+470h+P]
0x18005e30a  mov     esi, eax
0x18005e30c  test    eax, eax
0x18005e30e  jns     short loc_18005E31A
0x18005e310  mov     ebx, 0Ah
0x18005e315  jmp     loc_18005EBC1
0x18005e31a  cmp     qword ptr [r14+0A8h], 0
0x18005e322  jnz     short loc_18005E32E
0x18005e324  mov     ebx, 14h
0x18005e329  jmp     loc_18005EBBC
0x18005e32e  lea     rdi, [r14+0C0h]
0x18005e335  cmp     word ptr [rdi], 0
0x18005e339  jnz     short loc_18005E345
0x18005e33b  mov     ebx, 1Eh
0x18005e340  jmp     loc_18005EBB5
0x18005e345  mov     r8, r13
0x18005e348  lea     rdx, [rbp+470h+var_3F0]
0x18005e34f  lea     rcx, [rbp+470h+var_458]
0x18005e353  call    BipPackageIdFromOptionalFullName
0x18005e358  mov     esi, eax
0x18005e35a  test    eax, eax
0x18005e35c  jns     short loc_18005E36F
0x18005e35e  mov     ebx, 28h ; '('
0x18005e363  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18005e36a  jmp     loc_18005EBC1
0x18005e36f  mov     rax, [rbp+470h+Sid1]
0x18005e373  mov     ebx, 0Ah
0x18005e378  mov     r13, [rbp+470h+var_458]
0x18005e37c  test    rax, rax
0x18005e37f  jz      short loc_18005E3C6
0x18005e381  mov     rdx, [r14+0A8h]; Sid2
0x18005e388  test    rdx, rdx
0x18005e38b  jz      short loc_18005E39A
0x18005e38d  mov     rcx, rax; Sid1
0x18005e390  call    cs:__imp_RtlEqualSid
0x18005e396  test    al, al
0x18005e398  jnz     short loc_18005E3C6
0x18005e39a  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e3a1  test    byte ptr [rcx+1Ch], 40h
0x18005e3a5  jz      short loc_18005E3BF
0x18005e3a7  cmp     byte ptr [rcx+19h], 2
0x18005e3ab  jb      short loc_18005E3BF
0x18005e3ad  mov     rcx, [rcx+10h]
0x18005e3b1  lea     r8, WPP_17ca5d936c503bb31ad083a275fee47e_Traceguids
0x18005e3b8  mov     edx, ebx
0x18005e3ba  call    WPP_SF_
0x18005e3bf  mov     esi, 0C0000001h
0x18005e3c4  jmp     short loc_18005E429
0x18005e3c6  xor     esi, esi
0x18005e3c8  test    r13, r13
0x18005e3cb  jz      short loc_18005E421
0x18005e3cd  mov     edx, 41h ; 'A'
0x18005e3d2  mov     byte ptr [rsp+570h+UserDataCount], 1
0x18005e3d7  mov     r9d, edx
0x18005e3da  lea     r8, [rdi+100h]
0x18005e3e1  lea     rcx, [r13+100h]
0x18005e3e8  call    cs:__imp_RtlCompareUnicodeStrings
0x18005e3ee  test    eax, eax
0x18005e3f0  jz      short loc_18005E421
0x18005e3f2  mov     esi, 0C0000001h
0x18005e3f7  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e3fe  test    byte ptr [rcx+1Ch], 40h
0x18005e402  jz      short loc_18005E421
0x18005e404  cmp     byte ptr [rcx+19h], 2
0x18005e408  jb      short loc_18005E421
0x18005e40a  mov     rcx, [rcx+10h]
0x18005e40e  lea     r8, WPP_17ca5d936c503bb31ad083a275fee47e_Traceguids
0x18005e415  mov     edx, 0Bh
0x18005e41a  call    WPP_SF_
0x18005e41f  jmp     short loc_18005E429
0x18005e421  test    esi, esi
0x18005e423  jns     loc_18005E74C
0x18005e429  call    BipIsDeviceHoloLens
0x18005e42e  test    al, al
0x18005e430  jz      loc_18005E77F
0x18005e436  lea     rcx, [rbp+470h+Sid2]; void *
0x18005e43d  call    BipGetSignedInUserSidForHoloLens
0x18005e442  mov     esi, eax
0x18005e444  test    eax, eax
0x18005e446  jns     short loc_18005E45D
0x18005e448  mov     r13, [rbp+470h+var_4E8]
0x18005e44c  mov     ebx, 32h ; '2'
0x18005e451  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18005e458  jmp     loc_18005EBC1
0x18005e45d  mov     rax, [rbp+470h+Sid1]
0x18005e461  test    rax, rax
0x18005e464  jz      short loc_18005E4A6
0x18005e466  lea     rdx, [rbp+470h+Sid2]; Sid2
0x18005e46d  mov     rcx, rax; Sid1
0x18005e470  call    cs:__imp_RtlEqualSid
0x18005e476  test    al, al
0x18005e478  jnz     short loc_18005E4A6
0x18005e47a  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e481  test    byte ptr [rcx+1Ch], 40h
  ... truncated ...
```
