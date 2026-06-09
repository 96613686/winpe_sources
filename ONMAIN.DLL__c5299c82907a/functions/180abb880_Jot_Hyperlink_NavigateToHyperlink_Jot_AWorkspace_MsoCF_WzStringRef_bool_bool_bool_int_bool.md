# Jot::Hyperlink::NavigateToHyperlink(Jot::AWorkspace *,MsoCF::WzStringRef,bool,bool,bool,int,bool)

- ea: `0x180abb880`
- end: `0x180abc904`
- name: `?NavigateToHyperlink@Hyperlink@Jot@@YA?AW4HyperlinkError@2@PEAUAWorkspace@2@VWzStringRef@MsoCF@@_N22H2@Z`
- size: `4228`
- prototype: ``
- caller_count: `9`
- callee_count: `60`
- tags: `broker_com_uri`

## callers

- `0x18092ee54`
- `0x180997568`
- `0x180a22c98`
- `0x180abc910`
- `0x180abcf60`
- `0x180ac0390`
- `0x180c45a60`
- `0x180d2fe70`
- `0x180e5e83c`

## callees

- `0x18002df5c`
- `0x18002e050`
- `0x18002f61c`
- `0x18002f670`
- `0x18002fbd4`
- `0x1800575ac`
- `0x180057670`
- `0x18005989c`
- `0x18007c890`
- `0x18007c8fc`
- `0x180092008`
- `0x1800963b0`
- `0x1800969a4`
- `0x1800f1930`
- `0x180114134`
- `0x18012cf18`
- `0x1801b3e90`
- `0x1801b3f10`
- `0x1801c4c80`
- `0x1801c59a0`
- `0x18022ce2c`
- `0x18023142c`
- `0x180269f54`
- `0x1802d8ba0`
- `0x1802dc400`
- `0x1802dd458`
- `0x1802de200`
- `0x1802de3a0`
- `0x180305f10`
- `0x180376d7c`
- `0x180377440`
- `0x1803cb030`
- `0x1803e64b8`
- `0x1803f6240`
- `0x1803f7390`
- `0x18043b940`
- `0x180596d5c`
- `0x1805a4530`
- `0x180643730`
- `0x18064399c`
- `0x1806449b4`
- `0x180644ed4`
- `0x180645310`
- `0x180645c48`
- `0x180661630`
- `0x1806617f0`
- `0x18071d2f4`
- `0x1808c9a70`
- `0x1808d3b14`
- `0x1808d83ac`

## import_xrefs

- `MSVCP140!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180abc733`
- `MSVCP140!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180abc733`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180abc11c`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180abc2cf`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180abc4c7`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180abc741`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180abc7b3`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180abc11c`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180abc2cf`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180abc4c7`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180abc741`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180abc7b3`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180abc729`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180abc729`
- `MSO!MSO_34927` at `0x180abbbc6`
- `MSO!MSO_34927` at `0x180abbbc6`
- `mso40uiWin32Client!mso40uiWin32Client_3064` at `0x180abbb24`
- `mso40uiWin32Client!mso40uiWin32Client_3064` at `0x180abbb24`
- `mso40uiWin32Client!mso40uiWin32Client_61286` at `0x180abbaae`
- `mso40uiWin32Client!mso40uiWin32Client_61286` at `0x180abbaae`
- `Mso30Win32Client!Mso30Win32Client_13797` at `0x180abbe6e`
- `Mso30Win32Client!Mso30Win32Client_13797` at `0x180abbe6e`
- `Mso30Win32Client!Mso30Win32Client_58935` at `0x180abbb94`
- `Mso30Win32Client!Mso30Win32Client_58935` at `0x180abbb94`
- `Mso20Win32Client!Mso20Win32Client_9342` at `0x180abbe45`
- `Mso20Win32Client!Mso20Win32Client_9342` at `0x180abbe45`
- `Mso20Win32Client!Mso20Win32Client_54299` at `0x180abbed3`
- `Mso20Win32Client!Mso20Win32Client_54299` at `0x180abbed3`

## string_xrefs

- `0x180abb8d1`: `NavigateToHyperlink`
- `0x180abbdf2`: `NavigateToWXPSharedLinkFailed`
- `0x180abc1b4`: `HyperlinkFailureDueToDOSAttackPrevention`
- `0x180abc395`: `CompletedHyperlinkNavigationToUnifiedUrlInApp`
- `0x180abc899`: `CompletedHyperlinkNavigation`
- `0x180abbc80`: `NavigateToWXPSharedLinkDuration`
- `0x180abbdb2`: `NavigateToWXPSharedLinkDuration`
- `0x180abbcc0`: `NavigateToWXPSharedLink`
- `0x180abc4d9`: `OutlookHyperLinkNavigationNotSupported`
- `0x180abc55e`: `OneNoteHyperlinkOld`

## pseudocode

```c
__int64 __fastcall Jot::Hyperlink::NavigateToHyperlink(
        __int64 a1,
        __int64 a2,
        char a3,
        char a4,
        char a5,
        int a6,
        bool a7)
{
  Jot *v9; // rcx
  bool v10; // r12
  unsigned int v11; // r14d
  void **v12; // rcx
  __int64 v13; // rax
  unsigned int v14; // r13d
  __int64 v15; // rbx
  void **v16; // rcx
  char v17; // al
  char v18; // si
  __int64 v19; // rax
  Jot *v20; // rcx
  void **v21; // rdx
  unsigned int v22; // ebx
  void **v23; // rcx
  _QWORD *v24; // rax
  __int64 v25; // kr00_8
  __int64 v26; // rbx
  __int64 v27; // rax
  __int64 v28; // rcx
  _QWORD *v29; // rax
  __int64 v30; // kr08_8
  __int64 v31; // rbx
  __int64 v32; // rax
  const struct Mso::Telemetry::EventName *v33; // r8
  __int64 v34; // rcx
  char v35; // al
  void **v36; // rcx
  void **v37; // rcx
  void **v38; // rdx
  __int64 v39; // rbx
  void (__fastcall *v40)(__int64, __int64, char ****); // rsi
  _QWORD *v41; // rax
  __int64 v42; // rax
  __int128 *v43; // rcx
  __int128 *v44; // rcx
  __int128 *v45; // rcx
  __int64 v46; // rax
  void **v47; // rcx
  bool v48; // zf
  __int64 v49; // rax
  __int64 v50; // rax
  __int128 v51; // xmm6
  Jot *v52; // rax
  char v53; // si
  void **v54; // rcx
  __int128 v55; // xmm6
  _QWORD *v56; // rbx
  __int64 v57; // rax
  void **v58; // rcx
  void **v59; // rcx
  __int64 v60; // r8
  void **v61; // rcx
  void **v62; // rcx
  __int128 v63; // xmm6
  __int64 v64; // rcx
  int v65; // r8d
  __int64 v66; // rcx
  void *v67; // rax
  __int64 v68; // rax
  char ***v69; // rbx
  __int64 v70; // rax
  int v71; // r9d
  void **v72; // r8
  char *v73; // rsi
  __int64 v74; // rdx
  const void *v75; // rax
  __int64 v77; // r8
  __int64 v78; // r9
  void **v79; // rdx
  void **v80; // rdx
  __int64 v81; // rcx
  int v82; // [rsp+28h] [rbp-E0h]
  int v83; // [rsp+30h] [rbp-D8h]
  int v84; // [rsp+38h] [rbp-D0h]
  unsigned int v86[2]; // [rsp+60h] [rbp-A8h] BYREF
  const char *v87; // [rsp+68h] [rbp-A0h]
  _BYTE v88[8]; // [rsp+70h] [rbp-98h] BYREF
  char ***v89; // [rsp+78h] [rbp-90h] BYREF
  const char *v90; // [rsp+80h] [rbp-88h]
  __int64 v91; // [rsp+88h] [rbp-80h] BYREF
  __int64 v92; // [rsp+90h] [rbp-78h] BYREF
  __m128i v93; // [rsp+98h] [rbp-70h] BYREF
  _BYTE v94[448]; // [rsp+A8h] [rbp-60h] BYREF
  void *v95[3]; // [rsp+268h] [rbp+160h] BYREF
  unsigned __int64 v96; // [rsp+280h] [rbp+178h]
  __int128 v97; // [rsp+288h] [rbp+180h] BYREF
  __m128i si128; // [rsp+298h] [rbp+190h]
  _OWORD v99[2]; // [rsp+2A8h] [rbp+1A0h] BYREF
  void *Buf2[3]; // [rsp+2C8h] [rbp+1C0h] BYREF
  unsigned __int64 v101; // [rsp+2E0h] [rbp+1D8h]
  __int64 v102[5]; // [rsp+2E8h] [rbp+1E0h] BYREF
  __int16 v103; // [rsp+310h] [rbp+208h]
  __int64 v104; // [rsp+320h] [rbp+218h]
  _BYTE v105[48]; // [rsp+338h] [rbp+230h] BYREF
  _QWORD v106[12]; // [rsp+368h] [rbp+260h] BYREF
  _BYTE v107[528]; // [rsp+3C8h] [rbp+2C0h] BYREF

  v88[0] = a3;
  *(_QWORD *)v86 = &off_1810C0070;
  v87 = "NavigateToHyperlink";
  sub_1802DD458(526726050, v86, 50);
  sub_1803E64B8(a2, v95);
  if ( dword_1815A5298 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)TlsIndex)
                                   + 16LL) )
  {
    sub_18002E050(&dword_1815A5298);
    if ( dword_1815A5298 == -1 )
    {
      qword_1815A52A0 = *(_QWORD *)sub_18002F670(v86);
      sub_18002DF5C(&dword_1815A5298);
    }
  }
  sub_18002F670(v86);
  v10 = a7;
  v11 = 0;
  if ( !a7 && Jot::IsHostedWorkspaceEnabledAndVisible(v9) )
  {
    v12 = v95;
    if ( v96 > 7 )
      v12 = (void **)v95[0];
    if ( (unsigned __int8)sub_180AB0BD0(v12) )
    {
      if ( qword_1815304B0 )
      {
        if ( a1 || (a1 = (*(__int64 (**)(void))(*(_QWORD *)qword_1815304B0 + 528LL))()) != 0 )
        {
          v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 344LL))(a1);
          if ( v13 )
          {
            (*(void (__fastcall **)(__int64, void **))(*(_QWORD *)v13 + 176LL))(v13, v95);
LABEL_138:
            sub_1802D8BA0(v95);
            return 0;
          }
        }
      }
    }
  }
  v14 = 2;
  if ( (unsigned __int8)sub_180092008(&qword_181547C00) )
  {
    v15 = sub_180376D7C(v95, L"/:o:/", 0);
    v16 = v95;
    if ( v96 > 7 )
      v16 = (void **)v95[0];
    v17 = sub_1806449B4(v16);
    v18 = v17;
    if ( !a1 )
    {
      v19 = v17 || v15 != -1
          ? (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)qword_1815304B0 + 536LL))(qword_1815304B0, 0)
          : (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)qword_1815304B0 + 528LL))(qword_1815304B0);
      a1 = v19;
      if ( !v19 )
      {
LABEL_81:
        v11 = 9;
LABEL_125:
        sub_1802D8BA0(v95);
        return v11;
      }
    }
    if ( (unsigned int)mso40uiWin32Client_61286() == 2 && !a7 )
      v10 = v18 == 0;
    if ( v15 != -1 && a1 && !v10 )
    {
      sub_180ABCDE0(a1, v95);
      goto LABEL_138;
    }
    if ( Jot::NavigateToWXPLinksInApp(v20) )
    {
      v21 = v95;
      if ( v96 > 7 )
        v21 = (void **)v95[0];
      sub_18007C8FC(&v97, v21);
      v22 = mso40uiWin32Client_3064(&v97);
      sub_1802D8BA0(&v97);
      if ( v22 <= 2 )
      {
        sub_18002FBD4(&v91);
        v92 = 0;
        v23 = v95;
        if ( v96 > 7 )
          v23 = (void **)v95[0];
        if ( (int)Mso30Win32Client_58935(v23, 0, 0, 0, 0, 0, qword_181200608, &v92, 503685958) >= 0
          && v92
          && (int)MSO_34927(v92, 0, 0, 0, 0, 0, 0) >= 0 )
        {
          v24 = (_QWORD *)sub_18002FBD4(v86);
          v25 = *v24 - v91;
          sub_1801B3E90(&v97, "Handled");
          v26 = sub_180114134(v102, "Result", &v97, 4);
          *(_QWORD *)v86 = v25 / 1000000;
          sub_1800F1930(v106, "DurationInMs", v86, 4);
          v106[0] = &Mso::Telemetry::DataField<unsigned __int64>::`vftable';
          v27 = sub_18002F61C(&v91, 4);
          v89 = &off_1810C0070;
          v90 = "NavigateToWXPSharedLinkDuration";
          sub_180AB545C(&v89, v27, v106, v26);
          sub_1801B3F10(v105);
          sub_1801B3F10(&v97);
          *(_QWORD *)v86 = &off_1810C0070;
          v87 = "NavigateToWXPSharedLink";
          sub_1802DD458(503691278, v86, 50);
          v28 = v92;
          if ( v92 )
          {
            v92 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
          }
          goto LABEL_125;
        }
        v29 = (_QWORD *)sub_18002FBD4(v86);
        v30 = *v29 - v91;
        sub_1801B3E90(&v97, "FailedFallbackToOneNoteNavigationCodeNext");
        v31 = sub_180114134(v102, "Result", &v97, 4);
        *(_QWORD *)v86 = v30 / 1000000;
        sub_1800F1930(v106, "DurationInMs", v86, 4);
        v106[0] = &Mso::Telemetry::DataField<unsigned __int64>::`vftable';
        v32 = sub_18002F61C(&v91, 4);
        v89 = &off_1810C0070;
        v90 = "NavigateToWXPSharedLinkDuration";
        sub_180AB545C(&v89, v32, v106, v31);
        sub_1801B3F10(v105);
        sub_1801B3F10(&v97);
        *(_QWORD *)v86 = &off_1810C0070;
        v87 = "NavigateToWXPSharedLinkFailed";
        Jot::Logging::LogUnexpectedTag((Jot::Logging *)0x1E05B80D, (unsigned int)v86, v33);
        v34 = v92;
        if ( v92 )
        {
          v92 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
        }
      }
    }
  }
  if ( byte_181547BA0 < 0 )
    v35 = Mso20Win32Client_9342(&byte_181547BA0);
  else
    v35 = byte_181547BA0 != 0;
  if ( v35 )
  {
    v36 = v95;
    if ( v96 > 7 )
      v36 = (void **)v95[0];
    if ( (int)Mso30Win32Client_13797(v36, 0, 0, 2) < 0 )
      goto LABEL_81;
  }
  v37 = v95;
  if ( v96 > 7 )
    v37 = (void **)v95[0];
  if ( !(unsigned __int8)sub_1806449B4(v37) )
  {
    v91 = 0;
    v38 = v95;
    if ( v96 > 7 )
      v38 = (void **)v95[0];
    if ( (int)Mso20Win32Client_54299(&v91, v38, 0, 0, 16778752, 0) < 0 )
    {
      *(_QWORD *)v86 = v102;
      v104 = 0;
      v51 = *(_OWORD *)Jot::CDialogButtonSet::CDialogButtonSet(&v97, 1, 0);
      v52 = (Jot *)sub_1803F7390(&v89, 3, 22062480);
      v99[0] = v51;
      Jot::DisplayErrorDialogForError(v52, 0, 0, (__int64)v102);
      __ExceptionPtrDestroy(&v89);
      if ( v91 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
      v11 = 4;
      goto LABEL_125;
    }
    v39 = v91;
    if ( v91 )
    {
      v97 = 0;
      si128 = _mm_load_si128((const __m128i *)&xmmword_18103FC60);
      LOWORD(v97) = 0;
      LODWORD(v89) = 128;
      v40 = *(void (__fastcall **)(__int64, __int64, char ****))(*(_QWORD *)v91 + 240LL);
      v41 = (_QWORD *)sub_18012CF18(v86, &v97, 129);
      v42 = sub_180057670(*v41, 0);
      v40(v39, v42, &v89);
      sub_1800575AC(v86);
      v43 = &v97;
      if ( si128.m128i_i64[1] > 7uLL )
        v43 = (__int128 *)v97;
      if ( (unsigned __int8)sub_1800969A4(v43, L"one", 1) )
        goto LABEL_66;
      v44 = &v97;
      if ( si128.m128i_i64[1] > 7uLL )
        v44 = (__int128 *)v97;
      if ( (unsigned __int8)sub_1800969A4(v44, L"onetoc", 1) )
        goto LABEL_66;
      v45 = &v97;
      if ( si128.m128i_i64[1] > 7uLL )
        v45 = (__int128 *)v97;
      if ( (unsigned __int8)sub_1800969A4(v45, L"onetoc2", 1) )
      {
LABEL_66:
        v46 = sub_18005989C(v99);
        sub_18007C890(v95, v46);
        sub_1802D8BA0(v99);
      }
      sub_1802D8BA0(&v97);
      v39 = v91;
    }
    if ( v39 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
  }
  if ( !(unsigned __int8)sub_180092008(&qword_181547C00) && !a1 )
  {
    v47 = v95;
    if ( v96 > 7 )
      v47 = (void **)v95[0];
    v48 = (unsigned __int8)sub_1806449B4(v47) == 0;
    v49 = *(_QWORD *)qword_1815304B0;
    v50 = v48
        ? (*(__int64 (**)(void))(v49 + 528))()
        : (*(__int64 (__fastcall **)(__int64, _QWORD))(v49 + 536))(qword_1815304B0, 0);
    a1 = v50;
    if ( !v50 )
      goto LABEL_81;
  }
  v53 = v88[0];
  if ( v88[0] )
  {
    *(_QWORD *)v86 = *(_QWORD *)sub_18002F670(v86);
    if ( byte_1815A1028 && *(__int64 *)sub_1805A4530(v86, &v89, qword_1815A52A0) < 10000000 )
    {
      *(_QWORD *)v86 = &off_1810C0070;
      v87 = "HyperlinkFailureDueToDOSAttackPrevention";
      sub_1802DD458(507647943, v86, 50);
      v11 = 6;
      goto LABEL_125;
    }
    qword_1815A52A0 = *(_QWORD *)sub_18002F670(v86);
    byte_1815A1028 = 1;
    v54 = v95;
    if ( v96 > 7 )
      v54 = (void **)v95[0];
    if ( !(unsigned __int8)sub_1806449B4(v54) )
    {
      if ( !a4 )
      {
        *(_QWORD *)v86 = v102;
        v104 = 0;
        v55 = *(_OWORD *)Jot::CDialogButtonSet::CDialogButtonSet(&v97, 1, 0);
        v56 = (_QWORD *)sub_1808D3B14(v106, 22062481);
        sub_18071D2F4(&v89, v56, &_TI3_AUErrNotOneNoteFile_Jot__);
        *v56 = &off_1810DCC60;
        sub_18022CE2C(v56);
        v99[0] = v55;
        Jot::DisplayErrorDialogForError((Jot *)&v89, 0, 0, (__int64)v102);
        __ExceptionPtrDestroy(&v89);
      }
      v11 = 3;
      goto LABEL_125;
    }
  }
  v57 = sub_180269F54(&v97, v95);
  Jot::LowerCultureTag(Buf2, v57, &WindowName);
  if ( v10 )
  {
LABEL_129:
    v78 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 224LL))(a1);
    v79 = v95;
    if ( v96 > 7 )
      v79 = (void **)v95[0];
    LOBYTE(v77) = 1;
    if ( (*(unsigned __int8 (__fastcall **)(__int64, void **, __int64))(*(_QWORD *)v78 + 608LL))(v78, v79, v77) )
    {
      v80 = v95;
      if ( v96 > 7 )
        v80 = (void **)v95[0];
      LOBYTE(v84) = v53;
      LOBYTE(v83) = 0;
      sub_180645C48(a1, v80, 0, 0, 0, v83, v84, 0);
      v81 = 41556123;
    }
    else
    {
      v81 = 504189889;
    }
    *(_QWORD *)&v99[0] = &off_1810C0070;
    *((_QWORD *)&v99[0] + 1) = "CompletedHyperlinkNavigation";
    sub_1802DD458(v81, v99, 50);
    goto LABEL_137;
  }
  v58 = Buf2;
  if ( v101 > 7 )
    v58 = (void **)Buf2[0];
  if ( !(unsigned __int8)sub_180644ED4(v58) )
  {
    v59 = Buf2;
    if ( v101 > 7 )
      v59 = (void **)Buf2[0];
    if ( !(unsigned __int8)sub_180645310(v59) )
    {
      if ( (unsigned __int8)sub_180092008(&qword_181547C00) )
      {
        LOBYTE(v60) = 1;
        if ( (unsigned __int8)Jot::Hyperlink::HandleNavigationToUnifiedUrlInApp(a1, v95, v60) )
        {
          *(_QWORD *)v86 = &off_1810C0070;
          v87 = "CompletedHyperlinkNavigationToUnifiedUrlInApp";
          sub_1802DD458(41556122, v86, 50);
LABEL_124:
          sub_1802D8BA0(Buf2);
          goto LABEL_125;
        }
      }
      goto LABEL_129;
    }
  }
  v61 = v95;
  if ( v96 > 7 )
    v61 = (void **)v95[0];
  if ( (unsigned __int8)sub_180596D5C(v61) )
  {
    v62 = v95;
    if ( v96 > 7 )
      v62 = (void **)v95[0];
    if ( !(unsigned __int8)sub_180ABE3F8(v62) )
    {
      if ( !a4 )
      {
        *(_QWORD *)v86 = v102;
        v104 = 0;
        v63 = *(_OWORD *)Jot::CDialogButtonSet::CDialogButtonSet(&v97, 1, 0);
        sub_18023142C(v106, 16913486);
        v106[0] = &off_1810EBF50;
        sub_18071D2F4(&v89, v106, &_TI3_AUErrFeatureNotAvailable_Jot__);
        v106[0] = &off_1810DCC60;
        sub_18022CE2C(v106);
        v99[0] = v63;
        Jot::DisplayErrorDialogForError((Jot *)&v89, 0, 0, (__int64)v102);
        __ExceptionPtrDestroy(&v89);
      }
      *(_QWORD *)v86 = &off_1810C0070;
      v87 = "OutlookHyperLinkNavigationNotSupported";
      sub_1802DD458(41556124, v86, 50);
      sub_1802D8BA0(Buf2);
      v11 = 5;
      goto LABEL_125;
    }
LABEL_137:
    sub_1802D8BA0(Buf2);
    goto LABEL_138;
  }
  if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a1 + 440LL))(a1) )
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a1 + 456LL))(a1, 0);
  v64 = *(_QWORD *)Jot::Logging::Activity::GetThreadCurrentParenter(v86);
  v88[1] = 0;
  *(_QWORD *)&v99[0] = &off_1810C0070;
  *((_QWORD *)&v99[0] + 1) = "OneNoteHyperlinkOld";
  LOBYTE(v65) = 1;
  Jot::Logging::Activity::Activity((unsigned int)v94, (unsigned int)v99, v65, 6, (__int64)v88, v64);
  v66 = *(_QWORD *)v86;
  if ( *(_QWORD *)v86 )
  {
    *(_QWORD *)v86 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
  }
  v67 = (void *)Jot::UrlDecode(&v97, v95);
  LODWORD(v89) = *(_DWORD *)(sub_18064399C(v107, v67) + 468);
  v102[0] = (__int64)off_18106B9A8;
  v102[1] = (__int64)off_1810C1730;
  v102[2] = (__int64)L"StatusFlags";
  v102[3] = -1;
  v102[4] = (__int64)&v89;
  v103 = 4;
  sub_1801C59A0(v94, v102);
  sub_180643730(v107);
  sub_1802D8BA0(&v97);
  v68 = sub_1808F9F18();
  v69 = (char ***)v68;
  if ( v68 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 8LL))(v68);
  v89 = v69;
  v70 = Jot::Logging::Activity::Detach(v94, v86);
  v72 = v95;
  if ( v96 > 7 )
    LODWORD(v72) = v95[0];
  sub_1808D83AC((_DWORD)v69, a1, (_DWORD)v72, v71, v82, v53, a5, v70);
  *((_BYTE *)v69 + 400) = a4;
  v73 = (*v69)[9];
  if ( a6 <= 0 )
    v74 = -1;
  else
    v74 = *(_QWORD *)sub_1802DC400(v86, 10000LL * a6);
  ((void (__fastcall *)(char ***, __int64, _QWORD))v73)(v69, v74, 0);
  sub_18002F670(v86);
  v75 = (const void *)((__int64 (__fastcall *)(char ***))(*v69)[10])(v69);
  v93 = 0;
  __ExceptionPtrCopy(&v93, v75);
  if ( !__ExceptionPtrToBool(&v93) )
  {
    __ExceptionPtrDestroy(&v93);
    v93 = _mm_load_si128((const __m128i *)&xmmword_1810DD7D0);
    ((void (__fastcall *)(char ***))(*v69)[2])(v69);
    Jot::Logging::Activity::~Activity((Jot::Logging::Activity *)v94);
    goto LABEL_124;
  }
  if ( !(unsigned __int8)sub_180AB5134(&v93) )
    v14 = (unsigned __int8)sub_180AB5180(&v93) != 0;
  __ExceptionPtrDestroy(&v93);
  v93 = _mm_load_si128((const __m128i *)&xmmword_1810DD7D0);
  ((void (__fastcall *)(char ***))(*v69)[2])(v69);
  Jot::Logging::Activity::~Activity((Jot::Logging::Activity *)v94);
  sub_1802D8BA0(Buf2);
  sub_1802D8BA0(v95);
  return v14;
}

```

## disassembly

```asm
0x180abb880  mov     rax, rsp
0x180abb883  mov     [rax+20h], rbx
0x180abb887  push    rbp
0x180abb888  push    rsi
0x180abb889  push    rdi
0x180abb88a  push    r12
0x180abb88c  push    r13
0x180abb88e  push    r14
0x180abb890  push    r15
0x180abb892  lea     rbp, [rax-528h]
0x180abb899  sub     rsp, 5F0h
0x180abb8a0  movaps  xmmword ptr [rax-48h], xmm6
0x180abb8a4  mov     rax, cs:__security_cookie
0x180abb8ab  xor     rax, rsp
0x180abb8ae  mov     [rbp+520h+var_50], rax
0x180abb8b5  mov     byte ptr [rsp+620h+var_5D0], r9b
0x180abb8ba  mov     byte ptr [rsp+620h+var_5B8], r8b
0x180abb8bf  mov     rbx, rdx
0x180abb8c2  mov     r15, rcx
0x180abb8c5  lea     rsi, off_1810C0070
0x180abb8cc  mov     qword ptr [rsp+620h+var_5C8], rsi
0x180abb8d1  lea     rax, aNavigatetohype_1; "NavigateToHyperlink"
0x180abb8d8  mov     [rsp+620h+var_5C0], rax
0x180abb8dd  mov     r8d, 32h ; '2'
0x180abb8e3  lea     rdx, [rsp+620h+var_5C8]
0x180abb8e8  mov     ecx, 1F6533A2h
0x180abb8ed  call    sub_1802DD458
0x180abb8f2  lea     rdx, [rbp+520h+var_3C0]
0x180abb8f9  mov     rcx, rbx
0x180abb8fc  call    sub_1803E64B8
0x180abb901  mov     ecx, cs:TlsIndex
0x180abb907  mov     rax, gs:58h
0x180abb910  mov     edx, 10h
0x180abb915  mov     rax, [rax+rcx*8]
0x180abb919  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180abb91d  mov     eax, [rdx+rax]
0x180abb920  cmp     cs:dword_1815A5298, eax
0x180abb926  jle     short loc_180ABB95C
0x180abb928  lea     rcx, dword_1815A5298
0x180abb92f  call    sub_18002E050
0x180abb934  cmp     cs:dword_1815A5298, edi
0x180abb93a  jnz     short loc_180ABB95C
0x180abb93c  lea     rcx, [rsp+620h+var_5C8]
0x180abb941  call    sub_18002F670
0x180abb946  mov     rdx, [rax]
0x180abb949  mov     cs:qword_1815A52A0, rdx
0x180abb950  lea     rcx, dword_1815A5298
0x180abb957  call    sub_18002DF5C
0x180abb95c  lea     rcx, [rsp+620h+var_5C8]
0x180abb961  call    sub_18002F670
0x180abb966  movzx   r12d, [rbp+520h+arg_30]
0x180abb96e  xor     r14d, r14d
0x180abb971  test    r12b, r12b
0x180abb974  jnz     loc_180ABBA0A
0x180abb97a  call    ?IsHostedWorkspaceEnabledAndVisible@Jot@@YA_NXZ; Jot::IsHostedWorkspaceEnabledAndVisible(void)
0x180abb97f  test    al, al
0x180abb981  jz      loc_180ABBA0A
0x180abb987  lea     rcx, [rbp+520h+var_3C0]
0x180abb98e  cmp     [rbp+520h+var_3A8], 7
0x180abb996  cmova   rcx, [rbp+520h+var_3C0]
0x180abb99e  call    sub_180AB0BD0
0x180abb9a3  test    al, al
0x180abb9a5  jz      short loc_180ABBA0A
0x180abb9a7  mov     rcx, cs:qword_1815304B0
0x180abb9ae  test    rcx, rcx
0x180abb9b1  jz      short loc_180ABBA0A
0x180abb9b3  test    r15, r15
0x180abb9b6  jnz     short loc_180ABB9D0
0x180abb9b8  mov     rax, [rcx]
0x180abb9bb  mov     rax, [rax+210h]
0x180abb9c2  call    cs:__guard_dispatch_icall_fptr
0x180abb9c8  mov     r15, rax
0x180abb9cb  test    rax, rax
0x180abb9ce  jz      short loc_180ABBA0A
0x180abb9d0  mov     rcx, [r15]
0x180abb9d3  mov     rax, [rcx+158h]
0x180abb9da  mov     rcx, r15
0x180abb9dd  call    cs:__guard_dispatch_icall_fptr
0x180abb9e3  mov     r8, rax
0x180abb9e6  test    rax, rax
0x180abb9e9  jz      short loc_180ABBA0A
0x180abb9eb  mov     rcx, [rax]
0x180abb9ee  mov     rax, [rcx+0B0h]
0x180abb9f5  lea     rdx, [rbp+520h+var_3C0]
0x180abb9fc  mov     rcx, r8
0x180abb9ff  call    cs:__guard_dispatch_icall_fptr
0x180abba05  jmp     loc_180ABC8C7
0x180abba0a  lea     rcx, qword_181547C00
0x180abba11  call    sub_180092008
0x180abba16  mov     esi, 4
0x180abba1b  lea     ebx, [rsi-3]
0x180abba1e  lea     r13d, [rsi-2]
0x180abba22  test    al, al
0x180abba24  jz      loc_180ABBE2F
0x180abba2a  xor     r8d, r8d
0x180abba2d  lea     rdx, aO_0; "/:o:/"
0x180abba34  lea     rcx, [rbp+520h+var_3C0]
0x180abba3b  call    sub_180376D7C
0x180abba40  mov     rbx, rax
0x180abba43  lea     rcx, [rbp+520h+var_3C0]
0x180abba4a  cmp     [rbp+520h+var_3A8], 7
0x180abba52  cmova   rcx, [rbp+520h+var_3C0]; Buf2
0x180abba5a  call    sub_1806449B4
0x180abba5f  mov     sil, al
0x180abba62  test    r15, r15
0x180abba65  jnz     short loc_180ABBAAE
0x180abba67  test    al, al
0x180abba69  jnz     short loc_180ABBA89
0x180abba6b  cmp     rbx, rdi
0x180abba6e  jnz     short loc_180ABBA89
0x180abba70  mov     rcx, cs:qword_1815304B0
0x180abba77  mov     rdx, [rcx]
0x180abba7a  mov     rax, [rdx+210h]
0x180abba81  call    cs:__guard_dispatch_icall_fptr
0x180abba87  jmp     short loc_180ABBAA2
0x180abba89  mov     rcx, cs:qword_1815304B0
0x180abba90  mov     rax, [rcx]
0x180abba93  xor     edx, edx
0x180abba95  mov     rax, [rax+218h]
0x180abba9c  call    cs:__guard_dispatch_icall_fptr
0x180abbaa2  mov     r15, rax
0x180abbaa5  test    rax, rax
0x180abbaa8  jz      loc_180ABC155
0x180abbaae  call    cs:mso40uiWin32Client_61286
0x180abbab4  cmp     eax, r13d
0x180abbab7  jnz     short loc_180ABBACA
0x180abbab9  test    r12b, r12b
0x180abbabc  jnz     short loc_180ABBACA
0x180abbabe  test    sil, sil
0x180abbac1  mov     eax, 1
0x180abbac6  cmovz   r12d, eax
0x180abbaca  cmp     rbx, rdi
0x180abbacd  jz      short loc_180ABBAED
0x180abbacf  test    r15, r15
0x180abbad2  jz      short loc_180ABBAED
0x180abbad4  test    r12b, r12b
0x180abbad7  jnz     short loc_180ABBAED
0x180abbad9  lea     rdx, [rbp+520h+var_3C0]
0x180abbae0  mov     rcx, r15
0x180abbae3  call    sub_180ABCDE0
0x180abbae8  jmp     loc_180ABC8C7
0x180abbaed  call    ?NavigateToWXPLinksInApp@Jot@@YA_NXZ; Jot::NavigateToWXPLinksInApp(void)
0x180abbaf2  test    al, al
0x180abbaf4  jz      loc_180ABBE27
0x180abbafa  lea     rdx, [rbp+520h+var_3C0]
0x180abbb01  cmp     [rbp+520h+var_3A8], 7
0x180abbb09  cmova   rdx, [rbp+520h+var_3C0]
0x180abbb11  lea     rcx, [rbp+520h+var_3A0]
0x180abbb18  call    sub_18007C8FC
0x180abbb1d  lea     rcx, [rbp+520h+var_3A0]
0x180abbb24  call    cs:mso40uiWin32Client_3064
0x180abbb2a  mov     ebx, eax
0x180abbb2c  lea     rcx, [rbp+520h+var_3A0]
0x180abbb33  call    sub_1802D8BA0
0x180abbb38  cmp     ebx, r13d
0x180abbb3b  ja      loc_180ABBE27
0x180abbb41  lea     rcx, [rbp+520h+var_5A0]
0x180abbb45  call    sub_18002FBD4
0x180abbb4a  mov     [rbp+520h+var_598], r14
0x180abbb4e  lea     rcx, [rbp+520h+var_3C0]
0x180abbb55  cmp     [rbp+520h+var_3A8], 7
0x180abbb5d  cmova   rcx, [rbp+520h+var_3C0]
0x180abbb65  mov     [rsp+620h+var_5E0], 1E05A346h
0x180abbb6d  lea     rax, [rbp+520h+var_598]
0x180abbb71  mov     qword ptr [rsp+620h+var_5E8], rax
0x180abbb76  lea     rax, qword_181200608
0x180abbb7d  mov     [rsp+620h+var_5F0], rax
0x180abbb82  mov     qword ptr [rsp+620h+var_5F8], r14
0x180abbb87  mov     [rsp+620h+var_600], r14d
0x180abbb8c  xor     r9d, r9d
0x180abbb8f  xor     r8d, r8d
0x180abbb92  xor     edx, edx
0x180abbb94  call    cs:Mso30Win32Client_58935
0x180abbb9a  test    eax, eax
0x180abbb9c  js      loc_180ABBD03
0x180abbba2  mov     rcx, [rbp+520h+var_598]
0x180abbba6  test    rcx, rcx
0x180abbba9  jz      loc_180ABBD03
0x180abbbaf  mov     dword ptr [rsp+620h+var_5F0], r14d
0x180abbbb4  mov     qword ptr [rsp+620h+var_5F8], r14
0x180abbbb9  mov     qword ptr [rsp+620h+var_600], r14
0x180abbbbe  xor     r9d, r9d
0x180abbbc1  xor     r8d, r8d
0x180abbbc4  xor     edx, edx
0x180abbbc6  call    cs:MSO_34927
0x180abbbcc  test    eax, eax
0x180abbbce  js      loc_180ABBD03
0x180abbbd4  lea     rcx, [rsp+620h+var_5C8]
0x180abbbd9  call    sub_18002FBD4
0x180abbbde  mov     rcx, [rax]
0x180abbbe1  sub     rcx, [rbp+520h+var_5A0]
0x180abbbe5  mov     rax, 431BDE82D7B634DBh
0x180abbbef  imul    rcx
0x180abbbf2  mov     rdi, rdx
0x180abbbf5  sar     rdi, 12h
0x180abbbf9  mov     rax, rdi
0x180abbbfc  shr     rax, 3Fh
0x180abbc00  add     rdi, rax
0x180abbc03  lea     rdx, aHandled_0; "Handled"
0x180abbc0a  lea     rcx, [rbp+520h+var_3A0]
0x180abbc11  call    sub_1801B3E90
0x180abbc16  mov     esi, 4
0x180abbc1b  mov     r9d, esi
0x180abbc1e  lea     r8, [rbp+520h+var_3A0]
0x180abbc25  lea     rdx, aResult_1; "Result"
0x180abbc2c  lea     rcx, [rbp+520h+var_340]
0x180abbc33  call    sub_180114134
0x180abbc38  mov     rbx, rax
0x180abbc3b  mov     qword ptr [rsp+620h+var_5C8], rdi
0x180abbc40  mov     r9d, esi
0x180abbc43  lea     r8, [rsp+620h+var_5C8]
0x180abbc48  lea     rdx, aDurationinms; "DurationInMs"
0x180abbc4f  lea     rcx, [rbp+520h+var_2C0]
0x180abbc56  call    sub_1800F1930
0x180abbc5b  lea     rax, ??_7?$DataField@_K@Telemetry@Mso@@6B@; const Mso::Telemetry::DataField<unsigned __int64>::`vftable'
0x180abbc62  mov     [rbp+520h+var_2C0], rax
0x180abbc69  mov     edx, esi
0x180abbc6b  lea     rcx, [rbp+520h+var_5A0]
0x180abbc6f  call    sub_18002F61C
0x180abbc74  lea     rdi, off_1810C0070
0x180abbc7b  mov     [rsp+620h+var_5B0], rdi
0x180abbc80  lea     rcx, aNavigatetowxps; "NavigateToWXPSharedLinkDuration"
0x180abbc87  mov     [rsp+620h+var_5A8], rcx
0x180abbc8c  mov     r9, rbx
0x180abbc8f  lea     r8, [rbp+520h+var_2C0]
0x180abbc96  mov     rdx, rax
0x180abbc99  lea     rcx, [rsp+620h+var_5B0]
0x180abbc9e  call    sub_180AB545C
0x180abbca3  lea     rcx, [rbp+520h+var_2F0]
0x180abbcaa  call    sub_1801B3F10
0x180abbcaf  lea     rcx, [rbp+520h+var_3A0]
0x180abbcb6  call    sub_1801B3F10
0x180abbcbb  mov     qword ptr [rsp+620h+var_5C8], rdi
0x180abbcc0  lea     rax, aNavigatetowxps_0; "NavigateToWXPSharedLink"
0x180abbcc7  mov     [rsp+620h+var_5C0], rax
0x180abbccc  lea     r8d, [rsi+2Eh]
0x180abbcd0  lea     rdx, [rsp+620h+var_5C8]
0x180abbcd5  mov     ecx, 1E05B80Eh
0x180abbcda  call    sub_1802DD458
0x180abbcdf  nop
0x180abbce0  mov     rcx, [rbp+520h+var_598]
0x180abbce4  test    rcx, rcx
0x180abbce7  jz      loc_180ABC77B
0x180abbced  mov     [rbp+520h+var_598], r14
0x180abbcf1  mov     rax, [rcx]
0x180abbcf4  mov     rax, [rax+10h]
0x180abbcf8  call    cs:__guard_dispatch_icall_fptr
0x180abbcfe  jmp     loc_180ABC77B
0x180abbd03  lea     rcx, [rsp+620h+var_5C8]
0x180abbd08  call    sub_18002FBD4
0x180abbd0d  mov     rcx, [rax]
0x180abbd10  sub     rcx, [rbp+520h+var_5A0]
0x180abbd14  mov     rax, 431BDE82D7B634DBh
0x180abbd1e  imul    rcx
0x180abbd21  mov     rsi, rdx
0x180abbd24  sar     rsi, 12h
0x180abbd28  mov     rax, rsi
0x180abbd2b  shr     rax, 3Fh
0x180abbd2f  add     rsi, rax
0x180abbd32  lea     rdx, aFailedfallback_0; "FailedFallbackToOneNoteNavigationCodeNe"...
0x180abbd39  lea     rcx, [rbp+520h+var_3A0]
0x180abbd40  call    sub_1801B3E90
0x180abbd45  mov     r9d, 4
0x180abbd4b  lea     r8, [rbp+520h+var_3A0]
0x180abbd52  lea     rdx, aResult_1; "Result"
0x180abbd59  lea     rcx, [rbp+520h+var_340]
0x180abbd60  call    sub_180114134
0x180abbd65  mov     rbx, rax
0x180abbd68  mov     qword ptr [rsp+620h+var_5C8], rsi
0x180abbd6d  mov     esi, 4
0x180abbd72  mov     r9d, esi
0x180abbd75  lea     r8, [rsp+620h+var_5C8]
0x180abbd7a  lea     rdx, aDurationinms; "DurationInMs"
0x180abbd81  lea     rcx, [rbp+520h+var_2C0]
0x180abbd88  call    sub_1800F1930
0x180abbd8d  lea     rax, ??_7?$DataField@_K@Telemetry@Mso@@6B@; const Mso::Telemetry::DataField<unsigned __int64>::`vftable'
0x180abbd94  mov     [rbp+520h+var_2C0], rax
0x180abbd9b  mov     edx, esi
0x180abbd9d  lea     rcx, [rbp+520h+var_5A0]
0x180abbda1  call    sub_18002F61C
0x180abbda6  lea     rsi, off_1810C0070
0x180abbdad  mov     [rsp+620h+var_5B0], rsi
0x180abbdb2  lea     rcx, aNavigatetowxps; "NavigateToWXPSharedLinkDuration"
0x180abbdb9  mov     [rsp+620h+var_5A8], rcx
0x180abbdbe  mov     r9, rbx
0x180abbdc1  lea     r8, [rbp+520h+var_2C0]
0x180abbdc8  mov     rdx, rax
0x180abbdcb  lea     rcx, [rsp+620h+var_5B0]
0x180abbdd0  call    sub_180AB545C
0x180abbdd5  lea     rcx, [rbp+520h+var_2F0]
0x180abbddc  call    sub_1801B3F10
0x180abbde1  lea     rcx, [rbp+520h+var_3A0]
0x180abbde8  call    sub_1801B3F10
0x180abbded  mov     qword ptr [rsp+620h+var_5C8], rsi
0x180abbdf2  lea     rax, aNavigatetowxps_1; "NavigateToWXPSharedLinkFailed"
0x180abbdf9  mov     [rsp+620h+var_5C0], rax
0x180abbdfe  lea     rdx, [rsp+620h+var_5C8]; unsigned int
0x180abbe03  mov     ecx, 1E05B80Dh; this
0x180abbe08  call    ?LogUnexpectedTag@Logging@Jot@@YAXKAEBUEventName@Telemetry@Mso@@@Z; Jot::Logging::LogUnexpectedTag(ulong,Mso::Telemetry::EventName const &)
0x180abbe0d  mov     rcx, [rbp+520h+var_598]
  ... truncated ...
```
