# Jot::FirstRun::OpenOrCreateDefaultLocalNotebook(bool,OneNote::ProgressUI::IProgress *)

- ea: `0x180a6b380`
- end: `0x180a6cc59`
- name: `?OpenOrCreateDefaultLocalNotebook@FirstRun@Jot@@YAX_NPEAUIProgress@ProgressUI@OneNote@@@Z`
- size: `6361`
- prototype: `void __fastcall(Jot::FirstRun *__hidden this, bool, struct OneNote::ProgressUI::IProgress *)`
- caller_count: `1`
- callee_count: `45`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180a75764`

## callees

- `0x18002f7b0`
- `0x18002fb00`
- `0x180031128`
- `0x180031ec0`
- `0x1800444f8`
- `0x180073d90`
- `0x180079040`
- `0x18007b710`
- `0x18007c890`
- `0x180091cf0`
- `0x180091d40`
- `0x180096300`
- `0x1800969a4`
- `0x1800d2540`
- `0x180111308`
- `0x180133078`
- `0x18017eae0`
- `0x18017eb70`
- `0x180191120`
- `0x1801b3b00`
- `0x1801c7624`
- `0x180237b14`
- `0x180271510`
- `0x18029c158`
- `0x1802d8ba0`
- `0x1802dc400`
- `0x1802dd020`
- `0x1802dd458`
- `0x1802de200`
- `0x1802de3a0`
- `0x18038d8bc`
- `0x1803c2d70`
- `0x1804bc030`
- `0x18059f318`
- `0x1806a4660`
- `0x1806a91fc`
- `0x1807fabd0`
- `0x180815db0`
- `0x180825990`
- `0x1808c1840`
- `0x180a6874c`
- `0x180a6b380`
- `0x180c2ae40`
- `0x180cb76e0`
- `0x180cb7de8`

## import_xrefs

- `MSVCP140!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180a6c2bb`
- `MSVCP140!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180a6cbf8`
- `MSVCP140!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180a6c2bb`
- `MSVCP140!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180a6cbf8`
- `MSVCP140!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180a6bedf`
- `MSVCP140!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180a6c26d`
- `MSVCP140!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180a6cbb7`
- `MSVCP140!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180a6bedf`
- `MSVCP140!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180a6c26d`
- `MSVCP140!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180a6cbb7`
- `MSVCP140!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180a6b3f4`
- `MSVCP140!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180a6b3f4`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180a6ca66`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180a6cc08`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180a6ca66`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180a6cc08`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180a6c2a0`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180a6cbdd`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180a6c2a0`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180a6cbdd`
- `Mso20Win32Client!Mso20Win32Client_21217` at `0x180a6b451`
- `Mso20Win32Client!Mso20Win32Client_21217` at `0x180a6b886`
- `Mso20Win32Client!Mso20Win32Client_21217` at `0x180a6b451`
- `Mso20Win32Client!Mso20Win32Client_21217` at `0x180a6b886`

## string_xrefs

- `0x180a6c226`: `FirstRun: Failed to create the local notebook folder`
- `0x180a6b961`: `AttemptingMatchNotebookAgainstKnownDefaultNotebook`
- `0x180a6c342`: `FirstRun: Notebook created.`
- `0x180a6c400`: `FirstRun: Opening existing notebook...`
- `0x180a6b68e`: `ValidFilePath`
- `0x180a6bdf9`: `ValidFilePath`
- `0x180a6bfbb`: `ValidFilePath`
- `0x180a6c4d6`: `ValidFilePath`
- `0x180a6c698`: `ValidFilePath`
- `0x180a6c97d`: `FirstRunLocalQuickNoteSetupCompleted`
- `0x180a6cb9e`: `FirstRun: Quick Notes setup complete.`
- `0x180a6c183`: `NotebookStateCreatedLocalNotebook`
- `0x180a6bfd4`: `AttemptingCreateNewNotebookInDefaultLocalFolder`
- `0x180a6c6b1`: `AfterOpeningDefaultLocalNotebook`
- `0x180a6c74c`: `NotebookStateOpenedLocalNotebook`
- `0x180a6c37f`: `FirstRun: Unable to create a valid local notebook.`
- `0x180a6c4ef`: `OpeningDefaultLocalNotebook`

## pseudocode

```c
void __fastcall Jot::FirstRun::OpenOrCreateDefaultLocalNotebook(
        Jot::FirstRun *this,
        __int64 a2,
        struct OneNote::ProgressUI::IProgress *a3)
{
  __int64 StringFromTheResourceDll; // rax
  unsigned int v5; // r9d
  struct Jot::IFolderProxy **v6; // rdx
  __int64 v7; // r8
  void (__fastcall *v8)(__int64, __int64 *, _QWORD *, _QWORD, _QWORD, _BYTE); // rbx
  _QWORD *v9; // rax
  __int64 v10; // r8
  __int64 v11; // rax
  __int64 v12; // r8
  __int64 v13; // r8
  __int64 v14; // r8
  __int64 v15; // r15
  __int64 v16; // rax
  bool v17; // r8
  unsigned int v18; // r9d
  void *v19; // rbx
  __int64 v20; // rdi
  __int64 v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rsi
  __int64 v25; // rax
  unsigned __int64 v26; // rsi
  struct OneNote::ProgressUI::IProgress **v27; // rax
  void **v28; // r13
  void **v29; // rax
  void (__fastcall ***v30)(_QWORD, __int64 *, __int64 *); // rcx
  __int64 v31; // rax
  _QWORD *v32; // rax
  void (__fastcall ***v33)(_QWORD, __int64 *, _QWORD *); // rsi
  _QWORD *v34; // rax
  __int64 v35; // rax
  _QWORD *FolderProxy; // rax
  __int64 v37; // rcx
  bool v38; // si
  _QWORD *v39; // rdx
  __int128 *v40; // rcx
  __int64 v41; // rsi
  __int64 v42; // rcx
  unsigned int v43; // r9d
  _QWORD *v44; // rdx
  __int128 *v45; // rcx
  __int64 v46; // rsi
  __int64 v47; // rcx
  _QWORD *v48; // rdx
  __int128 *v49; // rcx
  __int64 v50; // rsi
  __int64 v51; // rcx
  __int64 v52; // r8
  __int64 v53; // rax
  __int64 v54; // rax
  __int64 v55; // rax
  __int64 v56; // r8
  __int64 v57; // rax
  __int64 v58; // rbx
  unsigned __int8 (__fastcall *v59)(__int64, _QWORD, _QWORD); // rdi
  _QWORD *v60; // rax
  unsigned int v61; // r9d
  const void *v62; // rax
  __int64 v63; // rax
  unsigned int v64; // r9d
  __int64 v65; // rax
  __int64 v66; // rax
  __int64 v67; // r8
  _QWORD *v68; // r8
  unsigned __int64 *v69; // rax
  unsigned __int64 v70; // rcx
  __int64 v71; // rax
  __int64 v72; // rbx
  __int64 (__fastcall *v73)(__int64, __int128 *, unsigned __int64 *, _QWORD, int, int, __int64, char); // rdi
  Jot::GraphSpaceEditor *v74; // rbx
  unsigned int v75; // r9d
  Jot::GraphSpaceEditor *v76; // rcx
  Jot::GraphSpaceEditor *v77; // rbx
  struct Jot::IGraphNode *v78; // rdx
  const void *v79; // rax
  const void *v80; // rax
  Jot::GraphSpaceEditor *v81; // rbx
  struct Jot::IGraphNode *v82; // rdx
  __int64 v83; // r8
  __int64 *v84; // rax
  __int64 v85; // rbx
  __int64 v86; // r8
  __int64 v87; // rax
  __int64 v88; // rax
  __int64 v89; // rax
  __int64 v90; // rax
  __int64 v91; // r8
  _QWORD *v92; // rax
  Jot::GraphSpaceEditor *v93; // rbx
  Jot::GraphSpaceEditor *v94; // rcx
  __int64 *v95; // rax
  __int64 v96; // rax
  __int64 v97; // rax
  char v98; // al
  __int64 v99; // rax
  __int64 v100; // r8
  Jot::GraphSpaceEditor *v101; // rdi
  struct Jot::IGraphNode *v102; // rdx
  __int64 v103; // rax
  Jot::GraphSpaceEditor *v104; // rdi
  struct Jot::IGraphNode *v105; // rdx
  __int64 v106; // rdi
  _QWORD *v107; // rax
  __int64 v108; // rax
  __int64 v109; // r8
  __int64 v110; // rax
  unsigned int v111; // r9d
  __int64 v112; // rax
  __int64 *v113; // rax
  __int64 v114; // rdi
  unsigned int v115; // r9d
  unsigned int v116; // r9d
  int v117; // [rsp+20h] [rbp-378h]
  int v118; // [rsp+20h] [rbp-378h]
  int v119; // [rsp+20h] [rbp-378h]
  int v120; // [rsp+28h] [rbp-370h]
  int v121; // [rsp+28h] [rbp-370h]
  int v122; // [rsp+28h] [rbp-370h]
  __int64 v123; // [rsp+30h] [rbp-368h]
  _BYTE v124[4]; // [rsp+50h] [rbp-348h] BYREF
  int v125; // [rsp+54h] [rbp-344h] BYREF
  __int64 v126; // [rsp+58h] [rbp-340h] BYREF
  Jot::GraphSpaceEditor *v127; // [rsp+60h] [rbp-338h] BYREF
  _QWORD v128[2]; // [rsp+68h] [rbp-330h] BYREF
  void **v129; // [rsp+78h] [rbp-320h] BYREF
  const char *v130; // [rsp+80h] [rbp-318h]
  void ***v131; // [rsp+88h] [rbp-310h]
  __int64 v132; // [rsp+90h] [rbp-308h] BYREF
  unsigned __int64 v133; // [rsp+98h] [rbp-300h] BYREF
  __int64 v134; // [rsp+A0h] [rbp-2F8h] BYREF
  __int64 v135; // [rsp+A8h] [rbp-2F0h] BYREF
  __int64 v136; // [rsp+B0h] [rbp-2E8h]
  __int128 v137; // [rsp+B8h] [rbp-2E0h] BYREF
  __m128i si128; // [rsp+C8h] [rbp-2D0h] BYREF
  __int64 v139; // [rsp+D8h] [rbp-2C0h] BYREF
  _BYTE v140[16]; // [rsp+E0h] [rbp-2B8h] BYREF
  _QWORD *v141; // [rsp+F0h] [rbp-2A8h] BYREF
  __int64 v142; // [rsp+F8h] [rbp-2A0h] BYREF
  char ***v143; // [rsp+100h] [rbp-298h] BYREF
  const char *v144; // [rsp+108h] [rbp-290h]
  _BYTE v145[48]; // [rsp+110h] [rbp-288h] BYREF
  _BYTE v146[40]; // [rsp+140h] [rbp-258h] BYREF
  _QWORD v147[2]; // [rsp+168h] [rbp-230h] BYREF
  _QWORD v148[2]; // [rsp+178h] [rbp-220h] BYREF
  _QWORD v149[2]; // [rsp+188h] [rbp-210h] BYREF
  char v150[48]; // [rsp+198h] [rbp-200h] BYREF
  char v151[8]; // [rsp+1C8h] [rbp-1D0h] BYREF
  __int128 v152; // [rsp+1D0h] [rbp-1C8h] BYREF
  __int64 v153; // [rsp+1E0h] [rbp-1B8h]
  unsigned __int64 v154; // [rsp+1E8h] [rbp-1B0h]
  void **v155; // [rsp+1F0h] [rbp-1A8h] BYREF
  void **v156; // [rsp+1F8h] [rbp-1A0h]
  __int64 *v157; // [rsp+200h] [rbp-198h]
  _QWORD v158[3]; // [rsp+210h] [rbp-188h] BYREF
  unsigned __int64 v159; // [rsp+228h] [rbp-170h]
  _QWORD v160[4]; // [rsp+230h] [rbp-168h] BYREF
  _QWORD v161[4]; // [rsp+250h] [rbp-148h] BYREF
  _BYTE pExceptionObject[80]; // [rsp+270h] [rbp-128h] BYREF
  _BYTE v163[80]; // [rsp+2C0h] [rbp-D8h] BYREF
  _BYTE v164[80]; // [rsp+310h] [rbp-88h] BYREF
  char v165; // [rsp+3A0h] [rbp+8h]

  v165 = (char)this;
  StringFromTheResourceDll = Jot::LoadStringFromTheResourceDll(v160, 2070339700, a3);
  OneNote::ProgressUI::CProgressLock::CProgressLock(v140, a2, StringFromTheResourceDll, 3);
  si128 = 0;
  __ExceptionPtrCreate(&si128);
  if ( Jot::ShouldLogTtid((Jot *)0x40A6C7, 0x10168u, 2u, v5) )
    sub_1806A91FC((Jot *)0x40A6C7, 0x10168u, 2u);
  v139 = 0;
  if ( !Jot::FGetMyDocumentsFolder((Jot *)&v139, v6) )
  {
    Mso20Win32Client_21217(20251029, 0);
    __debugbreak();
  }
  v8 = *(void (__fastcall **)(__int64, __int64 *, _QWORD *, _QWORD, _QWORD, _BYTE))(*(_QWORD *)v139 + 80LL);
  v9 = (_QWORD *)Jot::LoadStringFromTheResourceDll(&v152, 1258855830, v7);
  if ( v9[3] > 7u )
    v9 = (_QWORD *)*v9;
  v8(v139, &v135, v9, 0, 0, 0);
  sub_1802D8BA0(&v152);
  v11 = Jot::LoadStringFromTheResourceDll(&v155, 3920257527LL, v10);
  sub_18059F318(v140, v11);
  Jot::LoadStringFromTheResourceDll(v158, 3863265580LL, v12);
  Jot::LoadStringFromTheResourceDll(v160, 3427458819LL, v13);
  Jot::LoadStringFromTheResourceDll(v161, 2200353092LL, v14);
  v15 = 0;
  v136 = 0;
  v125 = 0;
  v16 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v135 + 24LL))(v135);
  if ( (*(unsigned __int8 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v16 + 80LL))(v16, 0, 600000000) )
  {
    v19 = 0;
    v134 = 0;
    v142 = 0;
    Jot::GetQuickNotesSection((Jot *)&v142, 0, v17);
    v20 = v142;
    if ( v142 )
    {
      sub_1801C7624(&v126, v142);
      v21 = v126;
      if ( v126 )
      {
        v22 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v126 + 24LL))(v126);
        sub_180031EC0(&v134, v22);
        v19 = (void *)v134;
        v21 = v126;
      }
      if ( v21 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    }
    (*(void (__fastcall **)(__int64, void ***, _QWORD))(*(_QWORD *)v135 + 32LL))(v135, &v155, 0);
    OneNote::ProgressUI::CProgressLock::MakeProgress((OneNote::ProgressUI::CProgressLock *)v140, 1u);
    v23 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v135 + 24LL))(v135);
    (*(void (__fastcall **)(__int64, __int128 *, _QWORD))(*(_QWORD *)v23 + 112LL))(v23, &v152, 0);
    v126 = v156 - v155;
    v24 = sub_180271510(v145, "NotebookCount", &v126);
    v124[0] = v153 != 0;
    v25 = sub_180237B14(v150, "ValidFilePath", v124);
    *(_QWORD *)&v137 = &off_1811F3100;
    *((_QWORD *)&v137 + 1) = "LocalNotebookFolderRetrieved";
    v128[0] = v25;
    v128[1] = v24;
    v129 = &Mso::Logging::CompositeStructuredTrace::`vftable';
    v130 = (const char *)v128;
    v131 = &v129;
    Jot::Logging::details::SendStructuredTraceTag(504903455, 50, &v137, &v129);
    sub_180133078(v151);
    sub_180133078(v146);
    sub_1802D8BA0(&v152);
    if ( v155 != v156 )
    {
      v26 = 0x64uLL / (v156 - v155);
      v133 = v26;
      v27 = (struct OneNote::ProgressUI::IProgress **)OneNote::ProgressUI::CProgressLock::CreateChildProgress(
                                                        v140,
                                                        &v141,
                                                        1);
      OneNote::ProgressUI::CProgressLock::CProgressLock((OneNote::ProgressUI::CProgressLock *)&v129, *v27, 0x64u);
      if ( v141 )
        (*(void (__fastcall **)(_QWORD *))(*v141 + 16LL))(v141);
      v28 = v155;
      v29 = v156;
      v128[0] = v156;
      while ( v28 != v29 )
      {
        OneNote::ProgressUI::CProgressLock::MakeProgress((OneNote::ProgressUI::CProgressLock *)&v129, v26);
        if ( (*(unsigned __int8 (__fastcall **)(void *))(*(_QWORD *)*v28 + 176LL))(*v28) )
        {
          if ( (*(unsigned __int8 (__fastcall **)(void *, _QWORD, __int64))(*(_QWORD *)*v28 + 80LL))(*v28, 0, 600000000) )
          {
            v30 = (void (__fastcall ***)(_QWORD, __int64 *, __int64 *))*v28;
            if ( *v28 != v19 )
            {
              v31 = 0;
              v132 = 0;
              if ( v30 )
              {
                (**v30)(v30, &qword_18109A0D8, &v132);
                v31 = v132;
              }
              if ( v31 )
              {
                v32 = (_QWORD *)sub_180031128();
                if ( !(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v32 + 152LL))(*v32) )
                {
                  Mso20Win32Client_21217(41746634, 0);
                  __debugbreak();
                }
                v33 = (void (__fastcall ***)(_QWORD, __int64 *, _QWORD *))*v28;
                v34 = (_QWORD *)sub_180031128();
                v35 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v34 + 152LL))(*v34);
                sub_1800444F8(&v126, v35, v33);
                if ( !(unsigned __int8)sub_180091CF0(&v126) )
                  goto LABEL_33;
                FolderProxy = (_QWORD *)Jot::NotebookEditor::GetFolderProxy(&v137, &v126, 0);
                v37 = v132;
                v38 = v132 != *FolderProxy;
                if ( (_QWORD)v137 )
                {
                  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v137 + 16LL))(v137);
                  v37 = v132;
                }
                if ( v38 )
                {
                  if ( v126 )
                  {
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v126 + 16LL))(v126);
                    v37 = v132;
                  }
                }
                else
                {
LABEL_33:
                  (*(void (__fastcall **)(void *, __int128 *))(*(_QWORD *)*v28 + 128LL))(*v28, &v152);
                  v143 = &off_1811F3100;
                  v144 = "AttemptingMatchNotebookAgainstKnownDefaultNotebook";
                  sub_1802DD458(504903454, &v143, 50);
                  if ( v125 < 4 )
                  {
                    v39 = v158;
                    if ( v159 > 7 )
                      v39 = (_QWORD *)v158[0];
                    v40 = &v152;
                    if ( v154 > 7 )
                      v40 = (__int128 *)v152;
                    if ( (unsigned __int8)sub_1800969A4(v40, v39, 1) )
                    {
                      v143 = &off_1811F3100;
                      v144 = "MatchedAndSelectedDefaultWebNotebook";
                      sub_1802DD458(504903453, &v143, 50);
                      v41 = v132;
                      if ( v132 )
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v132 + 8LL))(v132);
                      v42 = v15;
                      v15 = v41;
                      v136 = v41;
                      if ( v42 )
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
                      v125 = 4;
                      sub_1802D8BA0(&v152);
                      if ( v126 )
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v126 + 16LL))(v126);
                      if ( v132 )
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v132 + 16LL))(v132);
                      break;
                    }
                  }
                  if ( v125 >= 3 )
                    goto LABEL_186;
                  v44 = v161;
                  if ( v161[3] > 7u )
                    v44 = (_QWORD *)v161[0];
                  v45 = &v152;
                  if ( v154 > 7 )
                    v45 = (__int128 *)v152;
                  if ( (unsigned __int8)sub_1800969A4(v45, v44, 1) )
                  {
                    v147[0] = &off_1811F3100;
                    v147[1] = "MatchedAndSelectedDefaultWebNotebookLegacy14";
                    sub_1802DD458(504903452, v147, 50);
                    v46 = v132;
                    if ( v132 )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v132 + 8LL))(v132);
                    v47 = v15;
                    v15 = v46;
                    v136 = v46;
                    if ( v47 )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
                    v125 = 3;
                  }
                  else
                  {
LABEL_186:
                    if ( v125 >= 2 )
                      goto LABEL_74;
                    v48 = v160;
                    if ( v160[3] > 7u )
                      v48 = (_QWORD *)v160[0];
                    v49 = &v152;
                    if ( v154 > 7 )
                      v49 = (__int128 *)v152;
                    if ( (unsigned __int8)sub_1800969A4(v49, v48, 1) )
                    {
                      v148[0] = &off_1811F3100;
                      v148[1] = "MatchedAndSelectedDefaultWebNotebookLegacy15B1";
                      sub_1802DD458(504903451, v148, 50);
                      v50 = v132;
                      if ( v132 )
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v132 + 8LL))(v132);
                      v51 = v15;
                      v15 = v50;
                      v136 = v50;
                      if ( v51 )
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
                      v125 = 2;
                    }
                    else
                    {
LABEL_74:
                      v149[0] = &off_1811F3100;
                      v149[1] = "NoDefaultNotebookMatchOrBetterPreviousMatch";
                      sub_1802DD458(504903450, v149, 50);
                    }
                  }
                  sub_1802D8BA0(&v152);
                  if ( v126 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v126 + 16LL))(v126);
                  v37 = v132;
                }
                if ( v37 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
                LODWORD(v26) = v133;
              }
            }
          }
        }
        ++v28;
        v29 = (void **)v128[0];
      }
      OneNote::ProgressUI::CProgressLock::~CProgressLock((OneNote::ProgressUI::CProgressLock *)&v129);
    }
    sub_18002FB00(&v155);
    if ( v20 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    if ( v19 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v19 + 16LL))(v19);
  }
  else if ( Jot::ShouldLogTtid((Jot *)0x40A6D7, 0x10168u, 2u, v18) )
  {
    sub_1806A91FC((Jot *)0x40A6D7, 0x10168u, 2u);
  }
  v127 = 0;
  if ( v15 )
  {
    if ( Jot::ShouldLogTtid((Jot *)0x40A705, 0x10168u, 2u, v43) )
      sub_18038D8BC((Jot *)0x40A705, 0x10168u);
    v87 = Jot::LoadStringFromTheResourceDll(&v152, 288398267, v86);
    sub_18059F318(v140, v87);
    v152 = 0;
    v153 = 0;
    v154 = 7;
    LOWORD(v152) = 0;
    v88 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v15 + 24LL))(v15);
    v89 = (*(__int64 (__fastcall **)(__int64, void ***, _QWORD))(*(_QWORD *)v88 + 112LL))(v88, &v155, 0);
    sub_18007C890(&v152, v89);
    sub_1802D8BA0(&v155);
    v124[0] = v153 != 0;
    v90 = sub_180237B14(v145, "ValidFilePath", v124);
    v129 = (void **)&off_1811F3100;
    v130 = "OpeningDefaultLocalNotebook";
    sub_1804BC030(504903446, &v129, v91, v90);
    sub_180133078(v146);
    sub_1802D8BA0(&v152);
    v92 = (_QWORD *)sub_180031128();
    LOBYTE(v120) = 1;
    LOBYTE(v117) = 0;
    v93 = *(Jot::GraphSpaceEditor **)(*(__int64 (__fastcall **)(_QWORD, _QWORD *, __int64, _QWORD, int, int, char, char, _QWORD))(*(_QWORD *)*v92 + 360LL))(
                                       *v92,
                                       v128,
                                       v15,
                                       0,
                                       v117,
                                       v120,
                                       1,
                                       1,
                                       0);
    sub_18007B710(v93);
    v94 = v127;
    v127 = v93;
    if ( v94 )
      (*(void (__fastcall **)(Jot::GraphSpaceEditor *))(*(_QWORD *)v94 + 16LL))(v94);
    if ( v128[0] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v128[0] + 16LL))(v128[0]);
    v95 = (__int64 *)Jot::NotebookEditor::GetFolderProxy(v128, &v127, 0);
    v85 = *v95;
    *v95 = 0;
    v136 = v85;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    if ( v128[0] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v128[0] + 16LL))(v128[0]);
    v152 = 0;
    v153 = 0;
    v154 = 7;
    LOWORD(v152) = 0;
    if ( !v85
      || (v96 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v85 + 24LL))(v85),
          v97 = (*(__int64 (__fastcall **)(__int64, void ***, _QWORD))(*(_QWORD *)v96 + 112LL))(v96, &v155, 0),
          sub_18007C890(&v152, v97),
          sub_1802D8BA0(&v155),
          v98 = 1,
          !v153) )
    {
      v98 = 0;
    }
    v124[0] = v98;
    v99 = sub_180237B14(v145, "ValidFilePath", v124);
    v129 = (void **)&off_1811F3100;
    v130 = "AfterOpeningDefaultLocalNotebook";
    sub_1804BC030(504903445, &v129, v100, v99);
    sub_180133078(v146);
    sub_1802D8BA0(&v152);
  }
  else
  {
    if ( Jot::ShouldLogTtid((Jot *)0x40A6D9, 0x10168u, 2u, v43) )
      sub_1806A91FC((Jot *)0x40A6D9, 0x10168u, 2u);
    v53 = Jot::LoadStringFromTheResourceDll(&v152, 1715752470, v52);
    sub_18059F318(v140, v53);
    v54 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v135 + 24LL))(v135);
    (*(void (__fastcall **)(__int64, __int128 *, _QWORD))(*(_QWORD *)v54 + 112LL))(v54, &v152, 0);
    v124[0] = v153 != 0;
    v55 = sub_180237B14(v145, "ValidFilePath", v124);
    v129 = (void **)&off_1811F3100;
    v130 = "EnsureLocalNotebookFolderExist";
    sub_1804BC030(504903449, &v129, v56, v55);
    sub_180133078(v146);
    sub_1802D8BA0(&v152);
    v57 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v135 + 24LL))(v135);
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v57 + 56LL))(v57, &v126);
    v58 = v126;
    v59 = *(unsigned __int8 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v126 + 72LL);
    v60 = (_QWORD *)sub_1802DC400(v128, 600000000);
    if ( !v59(v58, *v60, 0)
      || !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v126 + 32LL))(v126)
      || (v62 = (const void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v126 + 80LL))(v126),
          __ExceptionPtrToBool(v62)) )
    {
      if ( Jot::ShouldLogTtid((Jot *)0x40A6DD, 0x10168u, 2u, v61) )
        sub_1806A91FC((Jot *)0x40A6DD, 0x10168u, 2u);
      if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v126 + 32LL))(v126) )
      {
        v79 = (const void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v126 + 80LL))(v126);
        if ( __ExceptionPtrToBool(v79) )
        {
          v80 = (const void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v126 + 80LL))(v126);
          v137 = 0;
          __ExceptionPtrCopy(&v137, v80);
          v128[0] = &v137;
          __ExceptionPtrRethrow(&v137);
        }
      }
      sub_180A6874C(v163, 17080972);
      throw (Jot::ErrNotebookManagement_NewNotebookFailed *)v163;
    }
    v63 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v135 + 24LL))(v135);
    if ( !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v63 + 64LL))(v63) )
    {
      if ( Jot::ShouldLogTtid((Jot *)0x40A6DF, 0x10168u, 2u, v64) )
        sub_1806A91FC((Jot *)0x40A6DF, 0x10168u, 2u);
      sub_180A6874C(pExceptionObject, 17080973);
      throw (Jot::ErrNotebookManagement_NewNotebookFailed *)pExceptionObject;
    }
    v65 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v135 + 24LL))(v135);
    (*(void (__fastcall **)(__int64, __int128 *, _QWORD))(*(_QWORD *)v65 + 112LL))(v65, &v152, 0);
    v124[0] = v153 != 0;
    v66 = sub_180237B14(v145, "ValidFilePath", v124);
    v129 = (void **)&off_1811F3100;
    v130 = "AttemptingCreateNewNotebookInDefaultLocalFolder";
    sub_1804BC030(504903448, &v129, v67, v66);
    sub_180133078(v146);
    sub_1802D8BA0(&v152);
    v68 = v158;
    if ( v159 > 7 )
      v68 = (_QWORD *)v158[0];
    LOBYTE(v120) = 0;
    v69 = (unsigned __int64 *)(*(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD *, _QWORD, _QWORD, int))(*(_QWORD *)v135 + 80LL))(
                                v135,
                                v128,
                                v68,
                                0,
                                0,
                                v120);
    v133 = 0;
    v70 = *v69;
    *v69 = 0;
    v133 = v70;
    if ( v128[0] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v128[0] + 16LL))(v128[0]);
    v71 = sub_180031128();
    v72 = *(_QWORD *)v71;
    v73 = *(__int64 (__fastcall **)(__int64, __int128 *, unsigned __int64 *, _QWORD, int, int, __int64, char))(**(_QWORD **)v71 + 312LL);
    v123 = *(_QWORD *)OneNote::ProgressUI::CProgressLock::CreateChildProgress(v140, &v141, 1);
    LOBYTE(v121) = 0;
    LOBYTE(v118) = 0;
    v74 = *(Jot::GraphSpaceEditor **)v73(v72, &v137, &v133, 0, v118, v121, v123, 1);
    sub_18007B710(v74);
    v76 = v127;
    v127 = v74;
    if ( v76 )
      (*(void (__fastcall **)(Jot::GraphSpaceEditor *))(*(_QWORD *)v76 + 16LL))(v76);
    if ( (_QWORD)v137 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v137 + 16LL))(v137);
    if ( v141 )
      (*(void (__fastcall **)(_QWORD *))(*v141 + 16LL))(v141);
    v77 = v127;
    if ( v127
      && (*(unsigned __int8 (__fastcall **)(Jot::GraphSpaceEditor *))(*(_QWORD *)v127 + 168LL))(v127)
      && !Jot::GraphSpaceEditor::IsMarkedForPendingDelete(v77, v78) )
    {
      v129 = (void **)&off_1811F3100;
      v130 = "NotebookStateCreatedLocalNotebook";
      sub_1802DD458(587792585, &v129, 50);
      LODWORD(v134) = Jot::ThemeColors::GetColor(9);
      BYTE4(v134) = 1;
      sub_180C2AE40(&v127, v134);
    }
    if ( v133 )
      (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v133 + 16LL))(v133);
    if ( v126 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v126 + 16LL))(v126);
    v81 = v127;
    if ( v127
      && (*(unsigned __int8 (__fastcall **)(Jot::GraphSpaceEditor *))(*(_QWORD *)v127 + 168LL))(v127)
      && !Jot::GraphSpaceEditor::IsMarkedForPendingDelete(v81, v82) )
    {
      if ( Jot::ShouldLogTtid((Jot *)0x40A701, 0x10168u, 2u, v75) )
        sub_1806A91FC((Jot *)0x40A701, 0x10168u, 2u);
    }
    else if ( Jot::ShouldLogTtid((Jot *)0x40A703, 0x10168u, 2u, v75) )
    {
      sub_18038D8BC((Jot *)0x40A703, 0x10168u);
    }
    LOBYTE(v83) = 1;
    v84 = (__int64 *)Jot::NotebookEditor::GetFolderProxy(v128, &v127, v83);
    v85 = *v84;
    *v84 = 0;
    v136 = v85;
    if ( v128[0] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v128[0] + 16LL))(v128[0]);
  }
  v101 = v127;
  if ( v127
    && (*(unsigned __int8 (__fastcall **)(Jot::GraphSpaceEditor *))(*(_QWORD *)v127 + 168LL))(v127)
    && !Jot::GraphSpaceEditor::IsMarkedForPendingDelete(v101, v102) )
  {
    v103 = sub_1801B3B00(v145, "MatchLevel", &v125);
    v129 = (void **)&off_1811F3100;
    v130 = "NotebookStateOpenedLocalNotebook";
    v134 = v103;
    v155 = &Mso::Logging::CompositeStructuredTrace::`vftable';
    v156 = (void **)&v134;
    v157 = &v135;
    Jot::Logging::details::SendStructuredTraceTag(587792584, 50, &v129, &v155);
    sub_180133078(v146);
  }
  OneNote::ProgressUI::CProgressLock::MakeProgress((OneNote::ProgressUI::CProgressLock *)v140, 1u);
  v104 = v127;
  if ( !v127
    || !(*(unsigned __int8 (__fastcall **)(Jot::GraphSpaceEditor *))(*(_QWORD *)v127 + 168LL))(v127)
    || Jot::GraphSpaceEditor::IsMarkedForPendingDelete(v104, v105) )
  {
    sub_180A6874C(v164, 17080975);
    throw (Jot::ErrNotebookManagement_NewNotebookFailed *)v164;
  }
  v141 = v128;
  v106 = sub_180091D40(v128, &v127);
  v107 = (_QWORD *)sub_180031128();
  v108 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*v107 + 160LL))(*v107, &v137);
  sub_1800D2540(v108, v106);
  v110 = Jot::LoadStringFromTheResourceDll(&v152, 1925444872, v109);
  sub_18059F318(v140, v110);
  if ( !v165 )
    goto LABEL_167;
  if ( Jot::ShouldLogTtid((Jot *)0x40A711, 0x10168u, 2u, v111) )
    sub_1806A91FC((Jot *)0x40A711, 0x10168u, 2u);
  v112 = sub_180111308(v127);
  (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v112 + 56LL))(v112, &v134);
  if ( v134 )
  {
    LOBYTE(v122) = 0;
    LOBYTE(v119) = 0;
    v113 = (__int64 *)(*(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD, _QWORD, int, int))(*(_QWORD *)v134 + 80LL))(
                        v134,
                        v128,
                        0,
                        0,
                        v119,
                        v122);
    v114 = *v113;
    *v113 = 0;
    *(_QWORD *)&v137 = v114;
    if ( v128[0] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v128[0] + 16LL))(v128[0]);
    v129 = (void **)&off_1811F3100;
    v130 = "FirstRunLocalQuickNoteSetupQueued";
    sub_1802DD458(509112527, &v129, 50);
    sub_180CB76E0(v114, &v127);
    v129 = (void **)&off_1811F3100;
    v130 = "FirstRunLocalQuickNoteSetupCompleted";
    sub_1802DD458(509112526, &v129, 50);
    if ( v114 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v114 + 16LL))(v114);
    if ( v134 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v134 + 16LL))(v134);
    if ( v127 )
      (*(void (__fastcall **)(Jot::GraphSpaceEditor *))(*(_QWORD *)v127 + 16LL))(v127);
    if ( v85 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
    sub_1802D8BA0(v161);
    sub_1802D8BA0(v160);
    sub_1802D8BA0(v158);
    if ( v135 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v135 + 16LL))(v135);
    if ( v139 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v139 + 16LL))(v139);
  }
  else
  {
LABEL_167:
    if ( v127 )
      (*(void (__fastcall **)(Jot::GraphSpaceEditor *))(*(_QWORD *)v127 + 16LL))(v127);
    if ( v85 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
    sub_1802D8BA0(v161);
    sub_1802D8BA0(v160);
    sub_1802D8BA0(v158);
    if ( v135 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v135 + 16LL))(v135);
    if ( v139 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v139 + 16LL))(v139);
    if ( Jot::ShouldLogTtid((Jot *)0x2375C782, 0x10168u, 2u, v115) )
      sub_18038D8BC((Jot *)0x2375C782, 0x10168u);
    sub_180CB7DE8(0, 0);
    if ( Jot::ShouldLogTtid((Jot *)0x2375C781, 0x10168u, 2u, v116) )
      sub_180825990((Jot *)0x2375C781);
    if ( __ExceptionPtrToBool(&si128) )
    {
      v137 = 0;
      __ExceptionPtrCopy(&v137, &si128);
      v128[0] = &v137;
      __ExceptionPtrRethrow(&v137);
    }
  }
  __ExceptionPtrDestroy(&si128);
  si128 = _mm_load_si128((const __m128i *)&xmmword_1810DD7D0);
  OneNote::ProgressUI::CProgressLock::~CProgressLock((OneNote::ProgressUI::CProgressLock *)v140);
}

```

## disassembly

```asm
0x180a6b380  mov     [rsp+arg_10], rbx
0x180a6b385  mov     [rsp+arg_18], rsi
0x180a6b38a  mov     [rsp+arg_0], cl
0x180a6b38e  push    rdi
0x180a6b38f  push    r12
0x180a6b391  push    r13
0x180a6b393  push    r14
0x180a6b395  push    r15
0x180a6b397  sub     rsp, 370h
0x180a6b39e  mov     rax, cs:__security_cookie
0x180a6b3a5  xor     rax, rsp
0x180a6b3a8  mov     [rsp+398h+var_38], rax
0x180a6b3b0  mov     rbx, rdx
0x180a6b3b3  xor     r14d, r14d
0x180a6b3b6  mov     edx, 7B66E074h
0x180a6b3bb  lea     rcx, [rsp+398h+var_168]
0x180a6b3c3  call    ?LoadStringFromTheResourceDll@Jot@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@Z; Jot::LoadStringFromTheResourceDll(uint)
0x180a6b3c8  lea     r9d, [r14+3]
0x180a6b3cc  mov     r8, rax
0x180a6b3cf  mov     rdx, rbx
0x180a6b3d2  lea     rcx, [rsp+398h+var_2B8]
0x180a6b3da  call    ??0CProgressLock@ProgressUI@OneNote@@QEAA@PEAUIProgress@12@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@Z; OneNote::ProgressUI::CProgressLock::CProgressLock(OneNote::ProgressUI::IProgress *,std::wstring,uint)
0x180a6b3df  nop
0x180a6b3e0  xorps   xmm0, xmm0
0x180a6b3e3  movdqu  [rsp+398h+var_2D0], xmm0
0x180a6b3ec  lea     rcx, [rsp+398h+var_2D0]
0x180a6b3f4  call    cs:?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180a6b3fa  mov     edx, 10168h; unsigned int
0x180a6b3ff  mov     ebx, 40A6C7h
0x180a6b404  lea     r8d, [r14+2]; unsigned int
0x180a6b408  mov     ecx, ebx; this
0x180a6b40a  call    ?ShouldLogTtid@Jot@@YA_NKII@Z; Jot::ShouldLogTtid(ulong,uint,uint)
0x180a6b40f  nop
0x180a6b410  test    al, al
0x180a6b412  jz      short loc_180A6B42C
0x180a6b414  lea     r9, aFirstrunRetrei; "FirstRun: Retreiving local notebook fol"...
0x180a6b41b  mov     edx, 10168h; unsigned int
0x180a6b420  lea     r8d, [r14+2]; unsigned int
0x180a6b424  mov     ecx, ebx; this
0x180a6b426  call    sub_1806A91FC
0x180a6b42b  nop
0x180a6b42c  jmp     short loc_180A6B431
0x180a6b42e  xor     r14d, r14d
0x180a6b431  mov     [rsp+398h+var_2C0], r14
0x180a6b439  lea     rcx, [rsp+398h+var_2C0]; this
0x180a6b441  call    ?FGetMyDocumentsFolder@Jot@@YA_NPEAPEAUIFolderProxy@1@@Z; Jot::FGetMyDocumentsFolder(Jot::IFolderProxy * *)
0x180a6b446  test    al, al
0x180a6b448  jnz     short loc_180A6B458
0x180a6b44a  xor     edx, edx
0x180a6b44c  mov     ecx, 1350195h
0x180a6b451  call    cs:Mso20Win32Client_21217
0x180a6b457  int     3; Trap to Debugger
0x180a6b458  mov     rax, [rsp+398h+var_2C0]
0x180a6b460  mov     rcx, [rax]
0x180a6b463  mov     rbx, [rcx+50h]
0x180a6b467  mov     edx, 4B089D96h
0x180a6b46c  lea     rcx, [rsp+398h+var_1C8]
0x180a6b474  call    ?LoadStringFromTheResourceDll@Jot@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@Z; Jot::LoadStringFromTheResourceDll(uint)
0x180a6b479  nop
0x180a6b47a  cmp     qword ptr [rax+18h], 7
0x180a6b47f  jbe     short loc_180A6B484
0x180a6b481  mov     rax, [rax]
0x180a6b484  mov     [rsp+398h+var_370], r14b
0x180a6b489  mov     [rsp+398h+var_378], r14
0x180a6b48e  xor     r9d, r9d
0x180a6b491  mov     r8, rax
0x180a6b494  lea     rdx, [rsp+398h+var_2F0]
0x180a6b49c  mov     rcx, [rsp+398h+var_2C0]
0x180a6b4a4  mov     rax, rbx
0x180a6b4a7  call    cs:__guard_dispatch_icall_fptr
0x180a6b4ad  nop
0x180a6b4ae  lea     rcx, [rsp+398h+var_1C8]
0x180a6b4b6  call    sub_1802D8BA0
0x180a6b4bb  mov     edx, 0E9AA61F7h
0x180a6b4c0  lea     rcx, [rsp+398h+var_1A8]
0x180a6b4c8  call    ?LoadStringFromTheResourceDll@Jot@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@Z; Jot::LoadStringFromTheResourceDll(uint)
0x180a6b4cd  mov     rdx, rax
0x180a6b4d0  lea     rcx, [rsp+398h+var_2B8]
0x180a6b4d8  call    sub_18059F318
0x180a6b4dd  mov     edx, 0E644C12Ch
0x180a6b4e2  lea     rcx, [rsp+398h+var_188]
0x180a6b4ea  call    ?LoadStringFromTheResourceDll@Jot@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@Z; Jot::LoadStringFromTheResourceDll(uint)
0x180a6b4ef  nop
0x180a6b4f0  mov     edx, 0CC4ADF03h
0x180a6b4f5  lea     rcx, [rsp+398h+var_168]
0x180a6b4fd  call    ?LoadStringFromTheResourceDll@Jot@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@Z; Jot::LoadStringFromTheResourceDll(uint)
0x180a6b502  nop
0x180a6b503  mov     edx, 8326B944h
0x180a6b508  lea     rcx, [rsp+398h+var_148]
0x180a6b510  call    ?LoadStringFromTheResourceDll@Jot@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@Z; Jot::LoadStringFromTheResourceDll(uint)
0x180a6b515  nop
0x180a6b516  mov     r15, r14
0x180a6b519  mov     [rsp+398h+var_2E8], r14
0x180a6b521  mov     [rsp+398h+var_344], r14d
0x180a6b526  mov     rcx, [rsp+398h+var_2F0]
0x180a6b52e  mov     rax, [rcx]
0x180a6b531  mov     rax, [rax+18h]
0x180a6b535  call    cs:__guard_dispatch_icall_fptr
0x180a6b53b  mov     r9, rax
0x180a6b53e  mov     rcx, [rax]
0x180a6b541  mov     rax, [rcx+50h]
0x180a6b545  xor     edx, edx
0x180a6b547  mov     r8d, 23C34600h
0x180a6b54d  mov     rcx, r9
0x180a6b550  call    cs:__guard_dispatch_icall_fptr
0x180a6b556  test    al, al
0x180a6b558  jz      loc_180A6BCEF
0x180a6b55e  mov     rbx, r14
0x180a6b561  mov     [rsp+398h+var_2F8], rbx
0x180a6b569  mov     [rsp+398h+var_2A0], r14
0x180a6b571  xor     edx, edx; struct Jot::IFileProxy **
0x180a6b573  lea     rcx, [rsp+398h+var_2A0]; this
0x180a6b57b  call    ?GetQuickNotesSection@Jot@@YAXPEAPEAUIFileProxy@1@_N@Z; Jot::GetQuickNotesSection(Jot::IFileProxy * *,bool)
0x180a6b580  mov     rdi, [rsp+398h+var_2A0]
0x180a6b588  test    rdi, rdi
0x180a6b58b  jz      short loc_180A6B5E1
0x180a6b58d  mov     rdx, rdi
0x180a6b590  lea     rcx, [rsp+398h+var_340]
0x180a6b595  call    sub_1801C7624
0x180a6b59a  nop
0x180a6b59b  mov     rcx, [rsp+398h+var_340]
0x180a6b5a0  test    rcx, rcx
0x180a6b5a3  jz      short loc_180A6B5CF
0x180a6b5a5  mov     rax, [rcx]
0x180a6b5a8  mov     rax, [rax+18h]
0x180a6b5ac  call    cs:__guard_dispatch_icall_fptr
0x180a6b5b2  mov     rdx, rax
0x180a6b5b5  lea     rcx, [rsp+398h+var_2F8]
0x180a6b5bd  call    sub_180031EC0
0x180a6b5c2  mov     rbx, [rsp+398h+var_2F8]
0x180a6b5ca  mov     rcx, [rsp+398h+var_340]
0x180a6b5cf  test    rcx, rcx
0x180a6b5d2  jz      short loc_180A6B5E1
0x180a6b5d4  mov     rax, [rcx]
0x180a6b5d7  mov     rax, [rax+10h]
0x180a6b5db  call    cs:__guard_dispatch_icall_fptr
0x180a6b5e1  mov     rcx, [rsp+398h+var_2F0]
0x180a6b5e9  mov     rax, [rcx]
0x180a6b5ec  xor     r8d, r8d
0x180a6b5ef  lea     rdx, [rsp+398h+var_1A8]
0x180a6b5f7  mov     rax, [rax+20h]
0x180a6b5fb  call    cs:__guard_dispatch_icall_fptr
0x180a6b601  nop
0x180a6b602  mov     edx, 1; unsigned int
0x180a6b607  lea     rcx, [rsp+398h+var_2B8]; this
0x180a6b60f  call    ?MakeProgress@CProgressLock@ProgressUI@OneNote@@UEAAXI@Z; OneNote::ProgressUI::CProgressLock::MakeProgress(uint)
0x180a6b614  mov     rcx, [rsp+398h+var_2F0]
0x180a6b61c  mov     rax, [rcx]
0x180a6b61f  mov     rax, [rax+18h]
0x180a6b623  call    cs:__guard_dispatch_icall_fptr
0x180a6b629  mov     r9, rax
0x180a6b62c  mov     rcx, [rax]
0x180a6b62f  mov     rax, [rcx+70h]
0x180a6b633  xor     r8d, r8d
0x180a6b636  lea     rdx, [rsp+398h+var_1C8]
0x180a6b63e  mov     rcx, r9
0x180a6b641  call    cs:__guard_dispatch_icall_fptr
0x180a6b647  mov     rax, [rsp+398h+var_1A0]
0x180a6b64f  sub     rax, [rsp+398h+var_1A8]
0x180a6b657  sar     rax, 3
0x180a6b65b  mov     [rsp+398h+var_340], rax
0x180a6b660  lea     r8, [rsp+398h+var_340]
0x180a6b665  lea     rdx, aNotebookcount_0; "NotebookCount"
0x180a6b66c  lea     rcx, [rsp+398h+var_288]
0x180a6b674  call    sub_180271510
0x180a6b679  mov     rsi, rax
0x180a6b67c  cmp     [rsp+398h+var_1B8], r14
0x180a6b684  setnz   [rsp+398h+var_348]
0x180a6b689  lea     r8, [rsp+398h+var_348]
0x180a6b68e  lea     rdx, aValidfilepath; "ValidFilePath"
0x180a6b695  lea     rcx, [rsp+398h+var_200]
0x180a6b69d  call    sub_180237B14
0x180a6b6a2  lea     r12, off_1811F3100
0x180a6b6a9  mov     qword ptr [rsp+398h+var_2E0], r12
0x180a6b6b1  lea     rcx, aLocalnotebookf_0; "LocalNotebookFolderRetrieved"
0x180a6b6b8  mov     qword ptr [rsp+398h+var_2E0+8], rcx
0x180a6b6c0  mov     [rsp+398h+var_330], rax
0x180a6b6c5  mov     [rsp+398h+var_328], rsi
0x180a6b6ca  lea     rsi, ??_7CompositeStructuredTrace@Logging@Mso@@6B@; const Mso::Logging::CompositeStructuredTrace::`vftable'
0x180a6b6d1  mov     [rsp+398h+var_320], rsi
0x180a6b6d6  lea     rax, [rsp+398h+var_330]
0x180a6b6db  mov     [rsp+398h+var_318], rax
0x180a6b6e3  lea     rax, [rsp+398h+var_320]
0x180a6b6e8  mov     [rsp+398h+var_310], rax
0x180a6b6f0  lea     r9, [rsp+398h+var_320]
0x180a6b6f5  lea     r8, [rsp+398h+var_2E0]
0x180a6b6fd  mov     edx, 32h ; '2'
0x180a6b702  mov     ecx, 1E18371Fh
0x180a6b707  call    ?SendStructuredTraceTag@details@Logging@Jot@@YAXKW4Severity@2Mso@@AEBUEventName@Telemetry@5@AEBUIStructuredTrace@25@@Z; Jot::Logging::details::SendStructuredTraceTag(ulong,Mso::Logging::Severity,Mso::Telemetry::EventName const &,Mso::Logging::IStructuredTrace const &)
0x180a6b70c  lea     rcx, [rsp+398h+var_1D0]
0x180a6b714  call    sub_180133078
0x180a6b719  lea     rcx, [rsp+398h+var_258]
0x180a6b721  call    sub_180133078
0x180a6b726  lea     rcx, [rsp+398h+var_1C8]
0x180a6b72e  call    sub_1802D8BA0
0x180a6b733  mov     rcx, [rsp+398h+var_1A0]
0x180a6b73b  cmp     [rsp+398h+var_1A8], rcx
0x180a6b743  jz      loc_180A6BA9F
0x180a6b749  sub     rcx, [rsp+398h+var_1A8]
0x180a6b751  sar     rcx, 3
0x180a6b755  xor     edx, edx
0x180a6b757  lea     r13d, [rdx+64h]
0x180a6b75b  mov     eax, r13d
0x180a6b75e  div     rcx
0x180a6b761  mov     rsi, rax
0x180a6b764  mov     [rsp+398h+var_300], rax
0x180a6b76c  lea     r8d, [r13-63h]
0x180a6b770  lea     rdx, [rsp+398h+var_2A8]
0x180a6b778  lea     rcx, [rsp+398h+var_2B8]
0x180a6b780  call    ?CreateChildProgress@CProgressLock@ProgressUI@OneNote@@UEAA?AV?$CIPtr@UIProgress@ProgressUI@OneNote@@U123@@MsoCF@@I@Z; OneNote::ProgressUI::CProgressLock::CreateChildProgress(uint)
0x180a6b785  nop
0x180a6b786  mov     r8d, r13d; unsigned int
0x180a6b789  mov     rdx, [rax]; struct OneNote::ProgressUI::IProgress *
0x180a6b78c  lea     rcx, [rsp+398h+var_320]; this
0x180a6b791  call    ??0CProgressLock@ProgressUI@OneNote@@QEAA@PEAUIProgress@12@I@Z; OneNote::ProgressUI::CProgressLock::CProgressLock(OneNote::ProgressUI::IProgress *,uint)
0x180a6b796  nop
0x180a6b797  mov     rcx, [rsp+398h+var_2A8]
0x180a6b79f  test    rcx, rcx
0x180a6b7a2  jz      short loc_180A6B7B1
0x180a6b7a4  mov     rax, [rcx]
0x180a6b7a7  mov     rax, [rax+10h]
0x180a6b7ab  call    cs:__guard_dispatch_icall_fptr
0x180a6b7b1  mov     r13, [rsp+398h+var_1A8]
0x180a6b7b9  mov     rax, [rsp+398h+var_1A0]
0x180a6b7c1  mov     [rsp+398h+var_330], rax
0x180a6b7c6  cmp     r13, rax
0x180a6b7c9  jz      loc_180A6BA8E
0x180a6b7cf  mov     edx, esi; unsigned int
0x180a6b7d1  lea     rcx, [rsp+398h+var_320]; this
0x180a6b7d6  call    ?MakeProgress@CProgressLock@ProgressUI@OneNote@@UEAAXI@Z; OneNote::ProgressUI::CProgressLock::MakeProgress(uint)
0x180a6b7db  mov     rcx, [r13+0]
0x180a6b7df  mov     rax, [rcx]
0x180a6b7e2  mov     rax, [rax+0B0h]
0x180a6b7e9  call    cs:__guard_dispatch_icall_fptr
0x180a6b7ef  test    al, al
0x180a6b7f1  jz      loc_180A6BCE1
0x180a6b7f7  mov     rcx, [r13+0]
0x180a6b7fb  mov     rax, [rcx]
0x180a6b7fe  xor     edx, edx
0x180a6b800  mov     r8d, 23C34600h
0x180a6b806  mov     rax, [rax+50h]
0x180a6b80a  call    cs:__guard_dispatch_icall_fptr
0x180a6b810  test    al, al
0x180a6b812  jz      loc_180A6BCE1
0x180a6b818  mov     rcx, [r13+0]
0x180a6b81c  cmp     rcx, rbx
0x180a6b81f  jz      loc_180A6BCE1
0x180a6b825  mov     rax, r14
0x180a6b828  mov     [rsp+398h+var_308], rax
0x180a6b830  test    rcx, rcx
0x180a6b833  jz      short loc_180A6B858
0x180a6b835  mov     rax, [rcx]
0x180a6b838  lea     r8, [rsp+398h+var_308]
0x180a6b840  lea     rdx, qword_18109A0D8
0x180a6b847  mov     rax, [rax]
0x180a6b84a  call    cs:__guard_dispatch_icall_fptr
0x180a6b850  mov     rax, [rsp+398h+var_308]
0x180a6b858  test    rax, rax
0x180a6b85b  jnz     short loc_180A6B862
0x180a6b85d  jmp     loc_180A6BCE1
0x180a6b862  call    sub_180031128
0x180a6b867  mov     rcx, [rax]
0x180a6b86a  mov     rax, [rcx]
0x180a6b86d  mov     rax, [rax+98h]
0x180a6b874  call    cs:__guard_dispatch_icall_fptr
0x180a6b87a  test    rax, rax
0x180a6b87d  jnz     short loc_180A6B88D
0x180a6b87f  xor     edx, edx
0x180a6b881  mov     ecx, 27D00CAh
0x180a6b886  call    cs:Mso20Win32Client_21217
0x180a6b88c  int     3; Trap to Debugger
0x180a6b88d  mov     rsi, [r13+0]
0x180a6b891  call    sub_180031128
0x180a6b896  mov     rcx, [rax]
0x180a6b899  mov     rax, [rcx]
0x180a6b89c  mov     rax, [rax+98h]
0x180a6b8a3  call    cs:__guard_dispatch_icall_fptr
0x180a6b8a9  mov     r8, rsi
0x180a6b8ac  mov     rdx, rax
0x180a6b8af  lea     rcx, [rsp+398h+var_340]
0x180a6b8b4  call    sub_1800444F8
0x180a6b8b9  nop
0x180a6b8ba  lea     rcx, [rsp+398h+var_340]
0x180a6b8bf  call    sub_180091CF0
0x180a6b8c4  test    al, al
0x180a6b8c6  jz      short loc_180A6B93D
0x180a6b8c8  xor     r8d, r8d
0x180a6b8cb  lea     rdx, [rsp+398h+var_340]
0x180a6b8d0  lea     rcx, [rsp+398h+var_2E0]
0x180a6b8d8  call    ?GetFolderProxy@NotebookEditor@Jot@@YA?AV?$CIPtr@UIFolderProxy@Jot@@U12@@MsoCF@@AEBV?$CNodeRef@VCSemNotebookTrait@Jot@@@2@_N@Z; Jot::NotebookEditor::GetFolderProxy(Jot::CNodeRef<Jot::CSemNotebookTrait> const &,bool)
0x180a6b8dd  mov     rcx, [rsp+398h+var_308]
0x180a6b8e5  cmp     rcx, [rax]
0x180a6b8e8  setnz   sil
0x180a6b8ec  mov     rdx, qword ptr [rsp+398h+var_2E0]
0x180a6b8f4  test    rdx, rdx
0x180a6b8f7  jz      short loc_180A6B911
0x180a6b8f9  mov     rax, [rdx]
0x180a6b8fc  mov     rcx, rdx
0x180a6b8ff  mov     rax, [rax+10h]
0x180a6b903  call    cs:__guard_dispatch_icall_fptr
  ... truncated ...
```
