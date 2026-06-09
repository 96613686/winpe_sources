# KdcGetTicketInfoFull(_UNICODE_STRING *,ulong,ulong,_KERB_INTERNAL_NAME *,char * *,_KDC_TICKET_INFO *,KERB_EXT_ERROR *,void * *,ulong,ulong,_USER_INTERNAL6_INFORMATION * *,_SID_AND_ATTRIBUTES_LIST *,_SAM_MAPPED_ATTRIBUTE_SET *)

- ea: `0x180060c24`
- end: `0x180061bb5`
- name: `?KdcGetTicketInfoFull@@YAJPEAU_UNICODE_STRING@@KKPEAU_KERB_INTERNAL_NAME@@PEAPEADPEAU_KDC_TICKET_INFO@@PEAUKERB_EXT_ERROR@@PEAPEAXKKPEAPEAU_USER_INTERNAL6_INFORMATION@@PEAU_SID_AND_ATTRIBUTES_LIST@@PEAU_SAM_MAPPED_ATTRIBUTE_SET@@@Z`
- size: `3985`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, unsigned int, unsigned int, struct _KERB_INTERNAL_NAME *, char **, struct _KDC_TICKET_INFO *, struct KERB_EXT_ERROR *, void **, unsigned int, unsigned int, struct _USER_INTERNAL6_INFORMATION **, struct _SID_AND_ATTRIBUTES_LIST *, struct _SAM_MAPPED_ATTRIBUTE_SET *)`
- caller_count: `1`
- callee_count: `32`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18006cb60`

## callees

- `0x180002ad0`
- `0x180003210`
- `0x1800038f0`
- `0x180003908`
- `0x180003980`
- `0x180005cc0`
- `0x18000ab40`
- `0x18000b6e0`
- `0x18000e440`
- `0x18000e9a4`
- `0x1800101c4`
- `0x1800101ec`
- `0x18001fc94`
- `0x18001ff94`
- `0x18002005c`
- `0x180020380`
- `0x180020fa8`
- `0x1800210a8`
- `0x18002b348`
- `0x18003669c`
- `0x18005a060`
- `0x18005a3a4`
- `0x18005bc6c`
- `0x1800600c4`
- `0x180060c24`
- `0x180061bbc`
- `0x180067458`
- `0x180072288`
- `0x18007c4d4`
- `0x18007c974`
- `0x180081bec`
- `0x18009c010`

## import_xrefs

- `ntdll!RtlEqualUnicodeString` at `0x180060f73`
- `ntdll!RtlEqualUnicodeString` at `0x1800619e4`
- `ntdll!RtlEqualUnicodeString` at `0x180060f73`
- `ntdll!RtlEqualUnicodeString` at `0x1800619e4`
- `ntdll!RtlGUIDFromString` at `0x180060ffd`
- `ntdll!RtlGUIDFromString` at `0x180060ffd`
- `SAMSRV!SamIGetUserLogonInformation2` at `0x18006123e`
- `SAMSRV!SamIGetUserLogonInformation2` at `0x18006123e`
- `SAMSRV!SamIGetUserLogonInformation3` at `0x180061087`
- `SAMSRV!SamIGetUserLogonInformation3` at `0x180061189`
- `SAMSRV!SamIGetUserLogonInformation3` at `0x180061087`
- `SAMSRV!SamIGetUserLogonInformation3` at `0x180061189`

## string_xrefs

- `0x1800612f3`: `kdcsvc.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall KdcGetTicketInfoFull(
        struct _UNICODE_STRING *a1,
        unsigned int a2,
        int a3,
        struct _KERB_INTERNAL_NAME *a4,
        char **a5,
        struct _KDC_TICKET_INFO *a6,
        struct KERB_EXT_ERROR *a7,
        void **a8,
        unsigned int a9,
        unsigned int a10,
        struct _USER_INTERNAL6_INFORMATION **a11,
        struct _SID_AND_ATTRIBUTES_LIST *a12,
        struct _SAM_MAPPED_ATTRIBUTE_SET *a13)
{
  char v14; // r13
  int v17; // r8d
  unsigned int v18; // ebx
  CSecurityData *v19; // rcx
  const char *v20; // r9
  unsigned int v21; // edi
  unsigned int v22; // ebx
  UNICODE_STRING *v23; // r14
  char v24; // al
  unsigned int v25; // ecx
  unsigned int v26; // r13d
  struct _USER_INTERNAL6_INFORMATION *v27; // rdi
  unsigned int v28; // r14d
  char v29; // bl
  unsigned __int8 v30; // r8
  CSecurityData *v31; // rcx
  unsigned __int64 v32; // r12
  int v33; // eax
  int v34; // ebx
  struct _SAM_MAPPED_ATTRIBUTE_SET *v35; // r12
  unsigned int v36; // edi
  CSecurityData *v37; // rcx
  struct KERB_EXT_ERROR *v38; // rax
  struct _UNICODE_STRING *p_String2; // rax
  USHORT Length; // cx
  _OWORD *v41; // rax
  __int64 v42; // rdi
  unsigned __int64 v43; // rdi
  unsigned __int16 *v44; // rcx
  __int64 v45; // rdx
  unsigned int v46; // r10d
  size_t v47; // r11
  wchar_t *v48; // rax
  CSecurityData *v49; // rcx
  int v50; // r9d
  __int64 v52; // rax
  unsigned int UserKeys; // eax
  unsigned int v54; // r13d
  struct IKdcBackend *v55; // rax
  unsigned int v56; // ecx
  __int64 v57; // rdx
  char v58; // al
  int v59; // ecx
  CSecurityData *v60; // rcx
  int v61; // eax
  char v62; // dl
  struct _USER_INTERNAL6_INFORMATION *i; // r8
  BOOLEAN v64; // al
  unsigned int *v65; // rax
  _QWORD *v66; // rax
  unsigned int v67; // r9d
  unsigned __int64 v68; // [rsp+50h] [rbp-B0h]
  __int64 v69; // [rsp+60h] [rbp-A0h] BYREF
  struct _USER_INTERNAL6_INFORMATION *v70; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v71; // [rsp+70h] [rbp-90h]
  UNICODE_STRING String2; // [rsp+78h] [rbp-88h] BYREF
  unsigned int KrbtgtTicketInfo; // [rsp+88h] [rbp-78h]
  struct _SAM_MAPPED_ATTRIBUTE_SET *v74; // [rsp+90h] [rbp-70h]
  PCUNICODE_STRING String1; // [rsp+98h] [rbp-68h]
  void *v76; // [rsp+A0h] [rbp-60h] BYREF
  int v77; // [rsp+A8h] [rbp-58h]
  struct KERB_EXT_ERROR *v78; // [rsp+B0h] [rbp-50h]
  struct _UNICODE_STRING v79; // [rsp+B8h] [rbp-48h] BYREF
  __int64 *v80; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v81; // [rsp+D0h] [rbp-30h] BYREF
  struct _SID_AND_ATTRIBUTES_LIST *v82; // [rsp+E0h] [rbp-20h]
  struct _KDC_TICKET_INFO *v83; // [rsp+E8h] [rbp-18h]
  struct _UNICODE_STRING v84; // [rsp+F0h] [rbp-10h] BYREF
  struct _KERB_INTERNAL_NAME *v85; // [rsp+100h] [rbp+0h]
  struct _USER_INTERNAL6_INFORMATION **v86; // [rsp+108h] [rbp+8h]
  void **v87; // [rsp+110h] [rbp+10h]
  struct _UNICODE_STRING v88; // [rsp+120h] [rbp+20h] BYREF
  __int64 v89; // [rsp+140h] [rbp+40h]
  int v90; // [rsp+148h] [rbp+48h]
  int v91; // [rsp+14Ch] [rbp+4Ch]
  int v92; // [rsp+150h] [rbp+50h]
  int v93; // [rsp+15Ch] [rbp+5Ch]
  struct _KERB_STORED_CREDENTIAL *v94; // [rsp+160h] [rbp+60h] BYREF
  struct _KERB_STORED_CREDENTIAL *v95; // [rsp+168h] [rbp+68h] BYREF
  int v96; // [rsp+171h] [rbp+71h]
  __int16 v97; // [rsp+175h] [rbp+75h]
  char v98; // [rsp+177h] [rbp+77h]
  int v99; // [rsp+180h] [rbp+80h]
  int v100; // [rsp+184h] [rbp+84h]
  bool v101; // [rsp+188h] [rbp+88h]
  __int16 v102; // [rsp+189h] [rbp+89h]
  char v103; // [rsp+18Bh] [rbp+8Bh]
  int v104; // [rsp+18Ch] [rbp+8Ch]
  int v105; // [rsp+190h] [rbp+90h]
  int v106; // [rsp+194h] [rbp+94h]
  _QWORD *v107; // [rsp+198h] [rbp+98h]
  char v108; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v109; // [rsp+1B0h] [rbp+B0h]
  __int64 v110; // [rsp+1B8h] [rbp+B8h] BYREF
  __int128 v111; // [rsp+1C0h] [rbp+C0h]
  char **v112; // [rsp+1D0h] [rbp+D0h]
  _QWORD v113[6]; // [rsp+1D8h] [rbp+D8h] BYREF
  char v114; // [rsp+208h] [rbp+108h]
  GUID Guid; // [rsp+210h] [rbp+110h] BYREF
  wchar_t Buffer[16]; // [rsp+220h] [rbp+120h] BYREF
  unsigned __int16 v117[30]; // [rsp+240h] [rbp+140h] BYREF
  int v118; // [rsp+27Ch] [rbp+17Ch]
  int v119; // [rsp+291h] [rbp+191h]
  __int16 v120; // [rsp+295h] [rbp+195h]
  char v121; // [rsp+297h] [rbp+197h]
  __int16 v122; // [rsp+2A9h] [rbp+1A9h]
  char v123; // [rsp+2ABh] [rbp+1ABh]
  int v124; // [rsp+2B4h] [rbp+1B4h]
  __int128 v125; // [rsp+2D8h] [rbp+1D8h] BYREF
  __int64 v126; // [rsp+2E8h] [rbp+1E8h]
  __int16 v127; // [rsp+448h] [rbp+348h]

  v85 = a4;
  v14 = a3;
  v77 = a3;
  String1 = a1;
  v78 = a7;
  v112 = a5;
  v83 = a6;
  v87 = a8;
  v86 = a11;
  v82 = a12;
  v74 = a13;
  LODWORD(v69) = -1073741275;
  v81 = 0;
  v76 = 0;
  v93 = 0;
  v96 = 0;
  v97 = 0;
  v98 = 0;
  v102 = 0;
  v103 = 0;
  v106 = 0;
  memset_0(&v88, 0, 0x98u);
  v110 = 0;
  v111 = 0;
  v70 = 0;
  Guid = 0;
  String2 = 0;
  v84 = 0;
  v79 = 0;
  v113[0] = &v79;
  v113[1] = &v84;
  v113[2] = &v70;
  v113[3] = &v76;
  v113[4] = &v81;
  v113[5] = &v88;
  v114 = 1;
  KerberosCryptoPolicy::Create(&v80);
  if ( !v80 )
    goto LABEL_139;
  if ( (!a1 || !a1->Length) && !a4 )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 110, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids);
    goto LABEL_8;
  }
  KrbtgtTicketInfo = 0;
  BYTE4(v69) = v14 & 1;
  v19 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0 )
    {
      v20 = "true";
      if ( (v14 & 1) == 0 )
        v20 = "false";
      WPP_SF_sDDZDqqD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (unsigned int)"false",
        v17,
        (_DWORD)v20,
        a9,
        a10,
        (__int64)String1,
        a2,
        (char)a4,
        (char)v74,
        v14);
      v19 = WPP_GLOBAL_Control;
    }
    if ( v19 != (CSecurityData *)&WPP_GLOBAL_Control && (*((_DWORD *)v19 + 7) & 0x2000) != 0 )
    {
      WPP_SF__KERB_NAME_(*((_QWORD *)v19 + 2), 112, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids, a4);
      v19 = WPP_GLOBAL_Control;
    }
  }
  if ( (v14 & 4) == 0 )
  {
    v21 = a9 | 0x25120005;
    v22 = a10 | 0x15A;
    goto LABEL_22;
  }
  v21 = 1048581;
  v22 = 448;
  v74 = 0;
  a2 |= 8u;
  if ( v19 == (CSecurityData *)&WPP_GLOBAL_Control )
  {
LABEL_22:
    v23 = (UNICODE_STRING *)String1;
    goto LABEL_23;
  }
  v23 = (UNICODE_STRING *)String1;
  if ( (*((_BYTE *)v19 + 28) & 4) != 0 )
    WPP_SF_Z(*((_QWORD *)v19 + 2), 113, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids, String1);
LABEL_23:
  if ( KdcGlobalEnforceStrongCertificateMapping >= 1 )
    v22 |= 0x10000080u;
  v24 = v14;
  v25 = v21 & 0xDAFFFFFF;
  if ( (v14 & 2) == 0 )
    v25 = v21;
  v71 = v25;
  v26 = v22 & 0xFFFFFEFF;
  if ( (v24 & 2) == 0 )
    v26 = v22;
  String2 = *v23;
  memset_0(v83, 0, 0xB0u);
  v81 = 0;
  v27 = (struct _USER_INTERNAL6_INFORMATION *)v86;
  if ( v86 )
    *v86 = 0;
  v28 = a2 | 8;
  if ( v82 )
    v28 = a2;
  v29 = v77;
  if ( (v77 & 0x10) != 0 )
    v26 &= 0xFFFFFFB7;
  if ( RtlEqualUnicodeString(&::String2, &String2, 1u) )
  {
    if ( KdcGlobalCDC )
      v28 |= 0x1000u;
    v26 |= 0x20u;
    if ( !v87 && !v27 && !v82 && g_kdcState == 2 )
    {
      v31 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 114, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids);
      }
      KrbtgtTicketInfo = CSecurityData::GetKrbtgtTicketInfo(v31, v83);
      if ( !KrbtgtTicketInfo )
        goto LABEL_197;
    }
  }
  if ( (v28 & 0x100) != 0 && RtlGUIDFromString(&String2, &Guid) >= 0 )
  {
    *(_DWORD *)&String2.Length = 1048592;
    String2.Buffer = (PWSTR)&Guid;
  }
  if ( !String2.Length )
  {
    v34 = v69;
LABEL_62:
    v36 = v71;
    v35 = v74;
    goto LABEL_63;
  }
  v32 = (unsigned __int64)&v108 & -(__int64)((v29 & 8) != 0);
  v33 = ((__int64 (__fastcall *)(void *, _QWORD, UNICODE_STRING *, _QWORD, unsigned int, struct _SAM_MAPPED_ATTRIBUTE_SET *, _QWORD, _QWORD, struct _USER_INTERNAL6_INFORMATION **, __int128 *, unsigned __int64, void **, __int64))SamIGetUserLogonInformation3)(
          GlobalAccountDomainHandle,
          v28,
          &String2,
          v71,
          v26,
          v74,
          0,
          0,
          &v70,
          &v81,
          v32,
          &v76,
          v69);
  v34 = v33;
  LODWORD(v69) = v33;
  if ( v33 != -1073741275 && v33 != -1073741724
    || (v28 & 0x100) != 0
    || (v28 & 0xFFFFFFF7) != 0
    || String2.Length < 2u
    || String2.Buffer[((unsigned __int64)String2.Length >> 1) - 1] == 36 )
  {
    goto LABEL_62;
  }
  LODWORD(v69) = KerbDuplicateStringEx(&v79, &String2, v30);
  if ( (int)v69 < 0 )
    goto LABEL_139;
  v79.Buffer[(unsigned __int64)v79.Length >> 1] = 36;
  v79.Length += 2;
  if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2), 115, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids, &v79);
  v68 = v32;
  v35 = v74;
  v36 = v71;
  v34 = ((__int64 (__fastcall *)(void *, _QWORD, struct _UNICODE_STRING *, _QWORD, unsigned int, struct _SAM_MAPPED_ATTRIBUTE_SET *, _QWORD, _QWORD, struct _USER_INTERNAL6_INFORMATION **, __int128 *, unsigned __int64, void **, __int64))SamIGetUserLogonInformation3)(
          GlobalAccountDomainHandle,
          v28,
          &v79,
          v71,
          v26,
          v74,
          0,
          0,
          &v70,
          &v81,
          v68,
          &v76,
          v69);
  LODWORD(v69) = v34;
LABEL_63:
  if ( (v34 == -1073741275 || v34 == -1073741724) && v85 )
  {
    KrbtgtTicketInfo = KerbBuildAltSecId(&v84, v85, v112);
    if ( KrbtgtTicketInfo )
    {
      v34 = v69;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2), 116, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids, &v84);
      v28 |= 0x10u;
      v34 = SamIGetUserLogonInformation2(GlobalAccountDomainHandle, v28, &v84, v36, v26, v35, &v70, &v81, &v76);
      LODWORD(v69) = v34;
    }
  }
  if ( v34 < 0 )
  {
    v37 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) != 0 )
    {
      WPP_SF_Zd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        117,
        (unsigned int)WPP_b168486f65343579948eb0cc9cf7c178_Traceguids,
        (unsigned int)&String2,
        v34);
      v34 = v69;
      v37 = WPP_GLOBAL_Control;
    }
    if ( v34 != -1073741724 )
    {
      if ( v34 != -1073741275
        && (unsigned int)(v34 + 1073741772) > 1
        && v34 != -1073741730
        && v34 != -1073741389
        && (unsigned int)(v34 + 1073741604) > 1
        && v34 != -1073741058
        && v34 != -1073740795
        && v34 != -1073740943 )
      {
        MicrosoftTelemetryAssertTriggeredArgs("kdcsvc.dll", (unsigned int)v34, v28);
        v34 = v69;
        v37 = WPP_GLOBAL_Control;
      }
      if ( v34 != -1073741724 && v34 != -1073741275 && v34 != -1073741772 )
      {
        if ( v34 == -1073741730 )
        {
          if ( (KDCInfoLevel & 0x10000000) != 0 )
          {
            v38 = v78;
            *(_DWORD *)v78 = -1073741730;
            *((_DWORD *)v38 + 1) = 68097683;
            *((_DWORD *)v38 + 2) = 2;
          }
        }
        else
        {
          if ( KdcGlobalCDC && v34 == -1073740943 )
          {
            if ( v37 != (CSecurityData *)&WPP_GLOBAL_Control && (*((_DWORD *)v37 + 7) & 0x40000) != 0 )
              WPP_SF_Z(*((_QWORD *)v37 + 2), 118, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids, &String2);
            v18 = -2147483642;
            goto LABEL_155;
          }
          if ( v34 == -1073741389 )
          {
            if ( v37 != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)v37 + 28) & 1) != 0 )
            {
              WPP_SF_Z(*((_QWORD *)v37 + 2), 119, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids, &String2);
              v34 = v69;
            }
            FillExtendedError(v34, 1, 1039, 5800, v78);
            v18 = 12;
            goto LABEL_155;
          }
          if ( v34 != -1073741604 && v34 != -1073741058 && v34 != -1073741603 )
          {
            memset(Buffer, 0, 22);
            memset_0(v117, 0, 0x20Au);
            if ( v84.Buffer )
            {
              p_String2 = &v84;
              Length = v84.Length;
            }
            else if ( v79.Buffer )
            {
              p_String2 = &v79;
              Length = v79.Length;
            }
            else
            {
              p_String2 = &String2;
              Length = String2.Length;
            }
            if ( (v28 & 0x20000) != 0 )
            {
              KdcFormatKeyIdForLogging(p_String2, v117);
              v34 = v69;
            }
            else
            {
              v41 = p_String2->Buffer;
              if ( Length >= 0x208u )
              {
                v44 = v117;
                v45 = 4;
                do
                {
                  *(_OWORD *)v44 = *v41;
                  *((_OWORD *)v44 + 1) = v41[1];
                  *((_OWORD *)v44 + 2) = v41[2];
                  *((_OWORD *)v44 + 3) = v41[3];
                  *((_OWORD *)v44 + 4) = v41[4];
                  *((_OWORD *)v44 + 5) = v41[5];
                  *((_OWORD *)v44 + 6) = v41[6];
                  *((_OWORD *)v44 + 7) = v41[7];
                  v44 += 64;
                  v41 += 8;
                  --v45;
                }
                while ( v45 );
                *(_QWORD *)v44 = *(_QWORD *)v41;
                v127 = 0;
              }
              else
              {
                v42 = Length;
                memcpy_0(v117, v41, Length);
                v43 = v42 & 0xFFFFFFFFFFFFFFFEuLL;
                if ( v43 >= 0x20A )
                  _report_rangecheckfailure();
                *(unsigned __int16 *)((char *)v117 + v43) = 0;
              }
            }
            if ( v34 == -1073741771 || v34 == -1073740795 )
            {
              FillExtendedError(v34, 1, 1039, 5872, v78);
              if ( (v28 & 0x20000) != 0 )
              {
                v48 = L"KEY ID";
              }
              else
              {
                v48 = (wchar_t *)(&KdcGlobalNameTypes)[v46];
                if ( !v48 )
                {
                  swprintf_s(Buffer, v47, L"%d", v46);
                  v48 = Buffer;
                }
              }
              ReportServiceEvent(1u, 0xC000000B, 0, 0, 2u, v117, v48);
              v18 = 8;
            }
            else
            {
              swprintf_s(Buffer, 0xAu, L"0x%x", v28);
              ReportServiceEvent(1u, 0xC0000007, 4u, &v69, 2u, v117, Buffer);
              v18 = 60;
            }
            goto LABEL_155;
          }
          FillExtendedError(v34, 1, 1039, 5921, v78);
        }
        v18 = 29;
LABEL_155:
        utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&v80);
        v114 = 0;
        lambda_026b74bcb782224f7565c8bc6310a4ff_::operator()((__int64)v113);
        std::vector<unsigned int>::_Tidy((__int64)&v110);
        return v18;
      }
    }
LABEL_8:
    v18 = 6;
    goto LABEL_155;
  }
  v49 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 120, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids);
    v49 = WPP_GLOBAL_Control;
  }
  v27 = v70;
  if ( BYTE4(v69) )
  {
    v50 = *((_DWORD *)v70 + 70);
    if ( (v50 & 0x1C0) == 0 && !*((_DWORD *)v70 + 94) )
    {
      if ( (v26 & 4) == 0 )
      {
        if ( v49 != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)v49 + 28) & 1) != 0 )
          WPP_SF_(*((_QWORD *)v49 + 2), 121, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids);
        goto LABEL_139;
      }
      v52 = *((_QWORD *)v70 + 45);
      if ( !v52 || !*(_DWORD *)(v52 + 4) )
      {
        if ( v49 != (CSecurityData *)&WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)v49 + 28) & 1) != 0 )
          {
            WPP_SF_DZ(
              *((_QWORD *)v49 + 2),
              122,
              (unsigned int)WPP_b168486f65343579948eb0cc9cf7c178_Traceguids,
              v50,
              (__int64)String1);
            v49 = WPP_GLOBAL_Control;
          }
          if ( v49 != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)v49 + 28) & 1) != 0 )
            WPP_SF__KERB_NAME_(*((_QWORD *)v49 + 2), 123, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids, v85);
        }
        v18 = 27;
        goto LABEL_155;
      }
    }
  }
  if ( (v77 & 6) != 0 )
  {
    v54 = KrbtgtTicketInfo;
  }
  else
  {
    UserKeys = KdcGetUserKeys(v76, v70, &v94, &v95, v78);
    v54 = UserKeys;
    if ( UserKeys )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 124, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids, UserKeys);
      v18 = v54;
      goto LABEL_155;
    }
  }
  if ( (int)KerbDuplicateStringEx(&v88, (const struct _UNICODE_STRING *)v27 + 3, v30) < 0 )
    goto LABEL_139;
  if ( (v28 & 8) != 0
    || *((_DWORD *)v27 + 68) == 500
    || (v55 = GlobalKdcService::Get(), (*(int (__fastcall **)(struct IKdcBackend *))(*(_QWORD *)v55 + 136LL))(v55) < 6)
    || (v56 = 0, !(_DWORD)v81) )
  {
LABEL_165:
    v58 = v105;
  }
  else
  {
    while ( 1 )
    {
      v57 = *(_QWORD *)(*((_QWORD *)&v81 + 1) + 16LL * v56);
      if ( *(_BYTE *)(v57 + 1) == 5 && *(_DWORD *)(v57 + 24) == 525 )
        break;
      if ( ++v56 >= (unsigned int)v81 )
        goto LABEL_165;
    }
    v58 = v105 | 0x40;
    v105 |= 0x40u;
  }
  v59 = v90;
  if ( (*((_DWORD *)v27 + 70) & 0x2000) != 0 )
  {
    v59 = v90 | 0x100;
    v90 |= 0x100u;
  }
  if ( (*((_DWORD *)v27 + 70) & 0x4000) == 0 && (v58 & 0x40) == 0 )
  {
    v59 |= 3u;
    v90 = v59;
  }
  if ( (*((_DWORD *)v27 + 70) & 0x40000) == 0 )
  {
    if ( !KdcGlobalA2DFProtocolTransition || *((_QWORD *)v70 + 44) )
      goto LABEL_178;
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 125, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids);
      v59 = v90;
    }
  }
  v59 |= 0x800u;
LABEL_178:
  v60 = (CSecurityData *)(v59 | 0x78u);
  v90 = (int)v60;
  v61 = CSecurityData::KdcFlags(v60);
  v90 &= v61;
  v89 = *((_QWORD *)v27 + 5);
  v99 = *((_DWORD *)v70 + 92);
  v100 = *((_DWORD *)v70 + 93);
  v91 = *((_DWORD *)v27 + 70);
  v104 = *((_DWORD *)v70 + 95);
  v92 = *((_DWORD *)v27 + 68);
  LOBYTE(v27) = 0;
  v101 = *((_DWORD *)v70 + 94) != 0;
  v109 = *((_QWORD *)v70 + 81);
  if ( _KDC_TICKET_INFO::IsLocalKrbtgt((_KDC_TICKET_INFO *)&v88) || (v105 & 0x400) == 0 && v62 )
  {
    v64 = RtlEqualUnicodeString(String1, &stru_1800B2E10, 1u);
    i = v70;
    if ( v64 )
      v105 |= 0x400u;
  }
  v65 = (unsigned int *)*((_QWORD *)i + 48);
  if ( !v65 || !v65[1] )
    goto LABEL_188;
  v66 = MIDL_user_allocate(*v65);
  v107 = v66;
  if ( !v66 )
  {
LABEL_139:
    utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&v80);
    v114 = 0;
    lambda_026b74bcb782224f7565c8bc6310a4ff_::operator()((__int64)v113);
    std::vector<unsigned int>::_Tidy((__int64)&v110);
    return 60;
  }
  memcpy_0(v66, *((const void **)v70 + 48), **((unsigned int **)v70 + 48));
  v67 = 0;
  for ( i = v70; v67 < *(_DWORD *)(*((_QWORD *)v70 + 48) + 4LL); i = v70 )
  {
    v107[2 * v67 + 2] = (char *)v107 + *(_QWORD *)(*((_QWORD *)i + 48) + 16LL * v67 + 16) - *((_QWORD *)i + 48);
    ++v67;
  }
LABEL_188:
  if ( v86 )
  {
    *v86 = i;
    v70 = 0;
  }
  if ( v82 )
  {
    *(_OWORD *)v82 = v81;
    v81 = 0;
  }
  if ( v87 )
  {
    *v87 = v76;
    v76 = 0;
  }
  _KDC_TICKET_INFO::operator=(v83, &v88);
  v118 = 0;
  v119 = 0;
  v120 = 0;
  v121 = 0;
  v122 = 0;
  v123 = 0;
  v124 = 0;
  memset_0(v117, 0, 0x98u);
  v125 = 0;
  v126 = 0;
  _KDC_TICKET_INFO::operator=(&v88, v117);
  std::vector<unsigned int>::_Tidy((__int64)&v125);
  if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 126, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids, v54);
LABEL_197:
  utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&v80);
  v114 = (char)v27;
  lambda_026b74bcb782224f7565c8bc6310a4ff_::operator()((__int64)v113);
  std::vector<unsigned int>::_Tidy((__int64)&v110);
  return 0;
}

```

## disassembly

```asm
0x180060c24  mov     [rsp-8+arg_10], rbx
0x180060c29  push    rbp
0x180060c2a  push    rsi
0x180060c2b  push    rdi
0x180060c2c  push    r12
0x180060c2e  push    r13
0x180060c30  push    r14
0x180060c32  push    r15
0x180060c34  lea     rbp, [rsp-360h]
0x180060c3c  sub     rsp, 460h
0x180060c43  mov     rax, cs:__security_cookie
0x180060c4a  xor     rax, rsp
0x180060c4d  mov     [rbp+390h+var_40], rax
0x180060c54  mov     r14, r9
0x180060c57  mov     [rbp+390h+var_390], r9
0x180060c5b  mov     r13d, r8d
0x180060c5e  mov     [rbp+390h+var_3E8], r8d
0x180060c62  mov     r12d, edx
0x180060c65  mov     rbx, rcx
0x180060c68  mov     [rbp+390h+String1], rcx
0x180060c6c  mov     rax, [rbp+390h+arg_30]
0x180060c73  mov     [rbp+390h+var_3E0], rax
0x180060c77  mov     rax, [rbp+390h+arg_20]
0x180060c7e  mov     [rbp+390h+var_2C0], rax
0x180060c85  mov     rax, [rbp+390h+arg_28]
0x180060c8c  mov     [rbp+390h+var_3A8], rax
0x180060c90  mov     rax, [rbp+390h+arg_38]
0x180060c97  mov     [rbp+390h+var_380], rax
0x180060c9b  mov     rax, [rbp+390h+arg_50]
0x180060ca2  mov     [rbp+390h+var_388], rax
0x180060ca6  mov     rax, [rbp+390h+arg_58]
0x180060cad  mov     [rbp+390h+var_3B0], rax
0x180060cb1  mov     rax, [rbp+390h+arg_60]
0x180060cb8  mov     [rbp+390h+var_400], rax
0x180060cbc  mov     [rsp+490h+var_430], 0C0000225h
0x180060cc4  xorps   xmm0, xmm0
0x180060cc7  movups  [rbp+390h+var_3C0], xmm0
0x180060ccb  xor     edi, edi
0x180060ccd  mov     [rbp+390h+var_3F0], rdi
0x180060cd1  xor     eax, eax
0x180060cd3  mov     [rbp+390h+var_334], eax
0x180060cd6  mov     [rbp+390h+var_31F], eax
0x180060cd9  mov     [rbp+390h+var_31B], ax
0x180060cdd  mov     [rbp+390h+var_319], al
0x180060ce0  mov     [rbp+390h+var_307], ax
0x180060ce7  mov     [rbp+390h+var_305], al
0x180060ced  mov     [rbp+390h+var_2FC], eax
0x180060cf3  xor     edx, edx; Val
0x180060cf5  mov     r8d, 98h; Size
0x180060cfb  lea     rcx, [rbp+390h+var_370]; void *
0x180060cff  call    memset_0
0x180060d04  mov     [rbp+390h+var_2D8], rdi
0x180060d0b  xorps   xmm0, xmm0
0x180060d0e  movdqa  [rbp+390h+var_2D0], xmm0
0x180060d16  mov     [rsp+490h+var_428], rdi
0x180060d1b  movups  xmmword ptr [rbp+390h+Guid.Data1], xmm0
0x180060d22  xorps   xmm1, xmm1
0x180060d25  movups  xmmword ptr [rsp+490h+String2.Length], xmm1
0x180060d2a  movups  xmmword ptr [rbp+390h+var_3A0.Length], xmm0
0x180060d2e  movups  xmmword ptr [rbp+390h+var_3D8.Length], xmm1
0x180060d32  lea     rax, [rbp+390h+var_3D8]
0x180060d36  mov     [rbp+390h+var_2B8], rax
0x180060d3d  lea     rax, [rbp+390h+var_3A0]
0x180060d41  mov     [rbp+390h+var_2B0], rax
0x180060d48  lea     rax, [rsp+490h+var_428]
0x180060d4d  mov     [rbp+390h+var_2A8], rax
0x180060d54  lea     rax, [rbp+390h+var_3F0]
0x180060d58  mov     [rbp+390h+var_2A0], rax
0x180060d5f  lea     rax, [rbp+390h+var_3C0]
0x180060d63  mov     [rbp+390h+var_298], rax
0x180060d6a  lea     rax, [rbp+390h+var_370]
0x180060d6e  mov     [rbp+390h+var_290], rax
0x180060d75  lea     r15d, [rdi+1]
0x180060d79  mov     [rbp+390h+var_288], r15b
0x180060d80  lea     rcx, [rbp+390h+var_3C8]
0x180060d84  call    ?Create@KerberosCryptoPolicy@@SA?AV?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@W4Kerb3961PolicyType@@@Z; KerberosCryptoPolicy::Create(Kerb3961PolicyType)
0x180060d89  nop
0x180060d8a  cmp     [rbp+390h+var_3C8], rdi
0x180060d8e  jz      loc_1800616FB
0x180060d94  test    rbx, rbx
0x180060d97  jz      short loc_180060D9E
0x180060d99  cmp     [rbx], di
0x180060d9c  jnz     short loc_180060DDA
0x180060d9e  test    r14, r14
0x180060da1  jnz     short loc_180060DDA
0x180060da3  lea     rsi, WPP_GLOBAL_Control
0x180060daa  mov     rcx, cs:WPP_GLOBAL_Control
0x180060db1  cmp     rcx, rsi
0x180060db4  jz      short loc_180060DD0
0x180060db6  test    [rcx+1Ch], r15b
0x180060dba  jz      short loc_180060DD0
0x180060dbc  lea     edx, [r14+6Eh]
0x180060dc0  lea     r8, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids
0x180060dc7  mov     rcx, [rcx+10h]
0x180060dcb  call    WPP_SF_
0x180060dd0  mov     ebx, 6
0x180060dd5  jmp     loc_18006180F
0x180060dda  mov     [rbp+390h+var_408], edi
0x180060ddd  mov     al, r13b
0x180060de0  and     al, r15b
0x180060de3  mov     [rsp+490h+var_42C], al
0x180060de7  lea     rsi, WPP_GLOBAL_Control
0x180060dee  lea     r15, WPP_b168486f65343579948eb0cc9cf7c178_Traceguids
0x180060df5  mov     ebx, [rbp+390h+arg_48]
0x180060dfb  mov     edi, [rbp+390h+arg_40]
0x180060e01  mov     rcx, cs:WPP_GLOBAL_Control
0x180060e08  cmp     rcx, rsi
0x180060e0b  jz      short loc_180060E8C
0x180060e0d  test    dword ptr [rcx+1Ch], 2000h
0x180060e14  jz      short loc_180060E63
0x180060e16  lea     rdx, aFalse; "false"
0x180060e1d  lea     r9, aTrue; "true"
0x180060e24  test    al, al
0x180060e26  cmovz   r9, rdx
0x180060e2a  mov     dword ptr [rsp+490h+var_440], r13d
0x180060e2f  mov     rax, [rbp+390h+var_400]
0x180060e33  mov     [rsp+490h+var_448], rax
0x180060e38  mov     [rsp+490h+var_450], r14
0x180060e3d  mov     dword ptr [rsp+490h+var_458], r12d
0x180060e42  mov     rax, [rbp+390h+String1]
0x180060e46  mov     [rsp+490h+var_460], rax
0x180060e4b  mov     dword ptr [rsp+490h+var_468], ebx
0x180060e4f  mov     dword ptr [rsp+490h+var_470], edi
0x180060e53  mov     rcx, [rcx+10h]
0x180060e57  call    WPP_SF_sDDZDqqD
0x180060e5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180060e63  cmp     rcx, rsi
0x180060e66  jz      short loc_180060E8C
0x180060e68  test    dword ptr [rcx+1Ch], 2000h
0x180060e6f  jz      short loc_180060E8C
0x180060e71  mov     edx, 70h ; 'p'
0x180060e76  mov     r9, r14
0x180060e79  mov     r8, r15
0x180060e7c  mov     rcx, [rcx+10h]
0x180060e80  call    WPP_SF__KERB_NAME_
0x180060e85  mov     rcx, cs:WPP_GLOBAL_Control
0x180060e8c  test    r13b, 4
0x180060e90  jz      short loc_180060ECD
0x180060e92  mov     edi, 100005h
0x180060e97  mov     ebx, 1C0h
0x180060e9c  mov     [rbp+390h+var_400], 0
0x180060ea4  or      r12d, 8
0x180060ea8  cmp     rcx, rsi
0x180060eab  jz      short loc_180060ED9
0x180060ead  mov     r14, [rbp+390h+String1]
0x180060eb1  test    byte ptr [rcx+1Ch], 4
0x180060eb5  jz      short loc_180060EDD
0x180060eb7  mov     edx, 71h ; 'q'
0x180060ebc  mov     r9, r14
0x180060ebf  mov     r8, r15
0x180060ec2  mov     rcx, [rcx+10h]
0x180060ec6  call    WPP_SF_Z
0x180060ecb  jmp     short loc_180060EDD
0x180060ecd  or      edi, 25120005h
0x180060ed3  or      ebx, 15Ah
0x180060ed9  mov     r14, [rbp+390h+String1]
0x180060edd  cmp     cs:?KdcGlobalEnforceStrongCertificateMapping@@3W4KerbStrongCertificateMappingEnforcement@@A, 1; KerbStrongCertificateMappingEnforcement KdcGlobalEnforceStrongCertificateMapping
0x180060ee4  jl      short loc_180060EEC
0x180060ee6  or      ebx, 10000080h
0x180060eec  mov     eax, r13d
0x180060eef  mov     ecx, edi
0x180060ef1  and     ecx, 0DAFFFFFFh
0x180060ef7  bt      r13d, 1
0x180060efc  cmovnb  ecx, edi
0x180060eff  mov     [rsp+490h+var_420], ecx
0x180060f03  mov     r13d, ebx
0x180060f06  btr     r13d, 8
0x180060f0b  bt      eax, 1
0x180060f0f  cmovnb  r13d, ebx
0x180060f13  movups  xmm0, xmmword ptr [r14]
0x180060f17  movdqu  xmmword ptr [rsp+490h+String2.Length], xmm0
0x180060f1d  xor     edx, edx; Val
0x180060f1f  mov     r8d, 0B0h; Size
0x180060f25  mov     rcx, [rbp+390h+var_3A8]; void *
0x180060f29  call    memset_0
0x180060f2e  xorps   xmm0, xmm0
0x180060f31  movups  [rbp+390h+var_3C0], xmm0
0x180060f35  mov     rdi, [rbp+390h+var_388]
0x180060f39  xor     eax, eax
0x180060f3b  test    rdi, rdi
0x180060f3e  jz      short loc_180060F43
0x180060f40  mov     [rdi], rax
0x180060f43  mov     r14d, r12d
0x180060f46  or      r14d, 8
0x180060f4a  cmp     [rbp+390h+var_3B0], rax
0x180060f4e  cmovnz  r14d, r12d
0x180060f52  mov     r12d, 10h
0x180060f58  mov     ebx, [rbp+390h+var_3E8]
0x180060f5b  test    r12b, bl
0x180060f5e  jz      short loc_180060F64
0x180060f60  and     r13d, 0FFFFFFB7h
0x180060f64  mov     r8b, 1; CaseInsensitive
0x180060f67  lea     rdx, [rsp+490h+String2]; String2
0x180060f6c  lea     rcx, String2; String1
0x180060f73  call    cs:__imp_RtlEqualUnicodeString
0x180060f79  xor     ecx, ecx
0x180060f7b  test    al, al
0x180060f7d  jz      short loc_180060FE6
0x180060f7f  cmp     cs:?KdcGlobalCDC@@3HA, ecx; int KdcGlobalCDC
0x180060f85  jz      short loc_180060F8C
0x180060f87  bts     r14d, 0Ch
0x180060f8c  or      r13d, 20h
0x180060f90  cmp     [rbp+390h+var_380], rcx
0x180060f94  jnz     short loc_180060FE6
0x180060f96  test    rdi, rdi
0x180060f99  jnz     short loc_180060FE6
0x180060f9b  cmp     [rbp+390h+var_3B0], rdi
0x180060f9f  jnz     short loc_180060FE6
0x180060fa1  cmp     cs:?g_kdcState@@3W4KdcState@@A, 2; KdcState g_kdcState
0x180060fa8  jnz     short loc_180060FE6
0x180060faa  mov     rcx, cs:WPP_GLOBAL_Control
0x180060fb1  cmp     rcx, rsi
0x180060fb4  jz      short loc_180060FD0
0x180060fb6  test    dword ptr [rcx+1Ch], 2000h
0x180060fbd  jz      short loc_180060FD0
0x180060fbf  mov     edx, 72h ; 'r'
0x180060fc4  mov     r8, r15
0x180060fc7  mov     rcx, [rcx+10h]
0x180060fcb  call    WPP_SF_
0x180060fd0  mov     rdx, [rbp+390h+var_3A8]; struct _KDC_TICKET_INFO *
0x180060fd4  call    ?GetKrbtgtTicketInfo@CSecurityData@@QEAAJPEAU_KDC_TICKET_INFO@@@Z; CSecurityData::GetKrbtgtTicketInfo(_KDC_TICKET_INFO *)
0x180060fd9  mov     [rbp+390h+var_408], eax
0x180060fdc  test    eax, eax
0x180060fde  jz      loc_180061B6A
0x180060fe4  xor     ecx, ecx
0x180060fe6  mov     edi, r14d
0x180060fe9  and     edi, 100h
0x180060fef  jz      short loc_18006101C
0x180060ff1  lea     rdx, [rbp+390h+Guid]; Guid
0x180060ff8  lea     rcx, [rsp+490h+String2]; GuidString
0x180060ffd  call    cs:__imp_RtlGUIDFromString
0x180061003  xor     ecx, ecx
0x180061005  test    eax, eax
0x180061007  js      short loc_18006101C
0x180061009  mov     dword ptr [rsp+490h+String2.Length], 100010h
0x180061011  lea     rax, [rbp+390h+Guid]
0x180061018  mov     [rbp+390h+String2.Buffer], rax
0x18006101c  cmp     [rsp+490h+String2.Length], cx
0x180061021  jbe     loc_180061197
0x180061027  mov     eax, ebx
0x180061029  and     al, 8
0x18006102b  neg     al
0x18006102d  sbb     r12, r12
0x180061030  lea     rax, [rbp+390h+var_2F0]
0x180061037  and     r12, rax
0x18006103a  lea     rax, [rbp+390h+var_3F0]
0x18006103e  mov     [rsp+490h+var_438], rax
0x180061043  mov     [rsp+490h+var_440], r12
0x180061048  lea     rax, [rbp+390h+var_3C0]
0x18006104c  mov     [rsp+490h+var_448], rax
0x180061051  lea     rax, [rsp+490h+var_428]
0x180061056  mov     [rsp+490h+var_450], rax
0x18006105b  mov     [rsp+490h+var_458], rcx
0x180061060  mov     [rsp+490h+var_460], rcx
0x180061065  mov     rax, [rbp+390h+var_400]
0x180061069  mov     [rsp+490h+var_468], rax
0x18006106e  mov     dword ptr [rsp+490h+var_470], r13d
0x180061073  mov     r9d, [rsp+490h+var_420]
0x180061078  lea     r8, [rsp+490h+String2]
0x18006107d  mov     edx, r14d
0x180061080  mov     rcx, cs:?GlobalAccountDomainHandle@@3PEAXEA; void * GlobalAccountDomainHandle
0x180061087  call    cs:__imp_SamIGetUserLogonInformation3
0x18006108d  mov     ebx, eax
0x18006108f  mov     [rsp+490h+var_430], eax
0x180061093  cmp     eax, 0C0000225h
0x180061098  jz      short loc_1800610A5
0x18006109a  cmp     eax, 0C0000064h
0x18006109f  jnz     loc_18006119B
0x1800610a5  test    edi, edi
0x1800610a7  jnz     loc_18006119B
0x1800610ad  test    r14d, 0FFFFFFF7h
0x1800610b4  jnz     loc_18006119B
0x1800610ba  lea     eax, [rdi+2]
0x1800610bd  cmp     [rsp+490h+String2.Length], ax
0x1800610c2  jb      loc_18006119B
0x1800610c8  movzx   ecx, [rsp+490h+String2.Length]
0x1800610cd  shr     rcx, 1
0x1800610d0  lea     edx, [rdi+24h]
0x1800610d3  mov     rax, [rbp+390h+String2.Buffer]
0x1800610d7  cmp     [rax+rcx*2-2], dx
0x1800610dc  jz      loc_18006119B
0x1800610e2  lea     rdx, [rsp+490h+String2]; struct _UNICODE_STRING *
0x1800610e7  lea     rcx, [rbp+390h+var_3D8]; struct _UNICODE_STRING *
0x1800610eb  call    ?KerbDuplicateStringEx@@YAJPEAU_UNICODE_STRING@@PEBU1@E@Z; KerbDuplicateStringEx(_UNICODE_STRING *,_UNICODE_STRING const *,uchar)
0x1800610f0  mov     [rsp+490h+var_430], eax
0x1800610f4  xor     edi, edi
0x1800610f6  test    eax, eax
0x1800610f8  js      loc_1800616FB
0x1800610fe  movzx   ecx, [rbp+390h+var_3D8.Length]
0x180061102  shr     rcx, 1
0x180061105  mov     rax, [rbp+390h+var_3D8.Buffer]
0x180061109  mov     word ptr [rax+rcx*2], 24h ; '$'
0x18006110f  lea     eax, [rdi+2]
0x180061112  add     [rbp+390h+var_3D8.Length], ax
0x180061116  mov     rcx, cs:WPP_GLOBAL_Control
0x18006111d  cmp     rcx, rsi
0x180061120  jz      short loc_18006113B
0x180061122  test    byte ptr [rcx+1Ch], 4
0x180061126  jz      short loc_18006113B
0x180061128  lea     edx, [rdi+73h]
  ... truncated ...
```
