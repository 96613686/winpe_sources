# CUserTileBroker::_SetUserTileInternal(ushort const *,IStream *,IStream *,IStream *,DEVICE_SCALE_FACTOR)

- ea: `0x18002ddf0`
- end: `0x18002e6ae`
- name: `?_SetUserTileInternal@CUserTileBroker@@AEAAJPEBGPEAUIStream@@11W4DEVICE_SCALE_FACTOR@@@Z`
- size: `2238`
- prototype: `__int64 __fastcall(CUserTileBroker *__hidden this, const unsigned __int16 *, struct IStream *, struct IStream *, struct IStream *, enum DEVICE_SCALE_FACTOR)`
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800ca1d0`
- `0x1800ca200`

## callees

- `0x18002ddf0`
- `0x18003217c`
- `0x18003a7b8`
- `0x18003d858`
- `0x18003de98`
- `0x180050ba0`
- `0x1800ca398`
- `0x1800d18a8`
- `0x1800e5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002dec4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002dec4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002de8f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002de9a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002de8f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002de9a`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18002e668`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18002e668`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18002df18`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18002df18`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x18002e652`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x18002e652`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x18002dee2`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x18002dee2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e632`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e632`

## string_xrefs

- `0x18002deae`: `shell\windowsuiimmersive\userinfo\usertiletask.cpp`
- `0x18002df76`: `shell\windowsuiimmersive\userinfo\usertiletask.cpp`
- `0x18002e60a`: `shell\windowsuiimmersive\userinfo\usertiletask.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CUserTileBroker::_SetUserTileInternal(
        CUserTileBroker *this,
        unsigned __int16 *a2,
        struct IStream *a3,
        struct IStream *a4,
        struct IStream *a5,
        enum DEVICE_SCALE_FACTOR a6)
{
  int inited; // edi
  int v10; // eax
  unsigned __int64 i; // rbx
  wil::details::in1diag3 *v12; // rcx
  unsigned __int64 v13; // r9
  __int64 v14; // rdx
  int v15; // eax
  unsigned __int64 j; // rsi
  __int64 v17; // rcx
  int DueTime; // [rsp+20h] [rbp-E0h]
  HANDLE *DueTimea; // [rsp+20h] [rbp-E0h]
  int v21[2]; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE hObject; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE v23; // [rsp+50h] [rbp-B0h] BYREF
  DWORD Parameter; // [rsp+58h] [rbp-A8h] BYREF
  char v25; // [rsp+5Ch] [rbp-A4h]
  HRESULT v26; // [rsp+60h] [rbp-A0h]
  void *phNewTimer; // [rsp+68h] [rbp-98h] BYREF
  __int64 v28; // [rsp+70h] [rbp-90h]
  __int64 v29; // [rsp+80h] [rbp-80h] BYREF
  struct IStream *v30; // [rsp+88h] [rbp-78h]
  _QWORD v31[2]; // [rsp+90h] [rbp-70h] BYREF
  wchar_t v32; // [rsp+A0h] [rbp-60h]
  __int64 v33; // [rsp+A2h] [rbp-5Eh]
  __int16 v34; // [rsp+AAh] [rbp-56h]
  __int128 v35; // [rsp+ACh] [rbp-54h]
  __int128 v36; // [rsp+BCh] [rbp-44h]
  __int64 v37; // [rsp+CCh] [rbp-34h]
  LPVOID pv; // [rsp+D8h] [rbp-28h]
  int v39; // [rsp+E0h] [rbp-20h]
  int v40; // [rsp+E4h] [rbp-1Ch]
  struct IStream *v41; // [rsp+E8h] [rbp-18h]
  HANDLE v42; // [rsp+F0h] [rbp-10h]
  __int64 v43; // [rsp+F8h] [rbp-8h]
  wchar_t v44; // [rsp+100h] [rbp+0h]
  __int64 v45; // [rsp+102h] [rbp+2h]
  __int16 v46; // [rsp+10Ah] [rbp+Ah]
  __int128 v47; // [rsp+10Ch] [rbp+Ch]
  wchar_t v48; // [rsp+11Ch] [rbp+1Ch]
  _BYTE v49[22]; // [rsp+11Eh] [rbp+1Eh] BYREF
  __int64 v50; // [rsp+138h] [rbp+38h]
  int v51; // [rsp+140h] [rbp+40h]
  int v52; // [rsp+144h] [rbp+44h]
  struct IStream *v53; // [rsp+148h] [rbp+48h]
  __int64 v54; // [rsp+150h] [rbp+50h]
  __int64 v55; // [rsp+158h] [rbp+58h]
  wchar_t v56; // [rsp+160h] [rbp+60h]
  __int64 v57; // [rsp+162h] [rbp+62h]
  __int16 v58; // [rsp+16Ah] [rbp+6Ah]
  __int128 v59; // [rsp+16Ch] [rbp+6Ch]
  wchar_t v60; // [rsp+17Ch] [rbp+7Ch]
  _BYTE v61[22]; // [rsp+17Eh] [rbp+7Eh] BYREF
  __int64 v62; // [rsp+198h] [rbp+98h]
  int v63; // [rsp+1A0h] [rbp+A0h]
  int v64; // [rsp+1A4h] [rbp+A4h]
  HANDLE v65; // [rsp+1A8h] [rbp+A8h]
  __int64 v66; // [rsp+1B0h] [rbp+B0h]
  __int64 v67; // [rsp+1B8h] [rbp+B8h]
  wchar_t v68; // [rsp+1C0h] [rbp+C0h]
  __int64 v69; // [rsp+1C2h] [rbp+C2h]
  __int16 v70; // [rsp+1CAh] [rbp+CAh]
  __int128 v71; // [rsp+1CCh] [rbp+CCh]
  __int128 v72; // [rsp+1DCh] [rbp+DCh]
  __int64 v73; // [rsp+1ECh] [rbp+ECh]
  __int64 v74; // [rsp+1F8h] [rbp+F8h]
  int v75; // [rsp+200h] [rbp+100h]
  int v76; // [rsp+204h] [rbp+104h]
  HANDLE v77; // [rsp+208h] [rbp+108h]
  __int64 v78; // [rsp+210h] [rbp+110h]
  __int64 v79; // [rsp+218h] [rbp+118h]
  wchar_t v80; // [rsp+220h] [rbp+120h]
  __int64 v81; // [rsp+222h] [rbp+122h]
  __int16 v82; // [rsp+22Ah] [rbp+12Ah]
  __int128 v83; // [rsp+22Ch] [rbp+12Ch]
  __int128 v84; // [rsp+23Ch] [rbp+13Ch]
  __int64 v85; // [rsp+24Ch] [rbp+14Ch]
  __int64 v86; // [rsp+258h] [rbp+158h]
  int v87; // [rsp+260h] [rbp+160h]
  int v88; // [rsp+264h] [rbp+164h]
  HANDLE v89; // [rsp+268h] [rbp+168h]
  __int64 v90; // [rsp+270h] [rbp+170h]
  __int64 v91; // [rsp+278h] [rbp+178h]
  wchar_t v92; // [rsp+280h] [rbp+180h]
  __int64 v93; // [rsp+282h] [rbp+182h]
  __int16 v94; // [rsp+28Ah] [rbp+18Ah]
  __int128 v95; // [rsp+28Ch] [rbp+18Ch]
  __int128 v96; // [rsp+29Ch] [rbp+19Ch]
  __int64 v97; // [rsp+2ACh] [rbp+1ACh]
  __int64 v98; // [rsp+2B8h] [rbp+1B8h]
  int v99; // [rsp+2C0h] [rbp+1C0h]
  int v100; // [rsp+2C4h] [rbp+1C4h]
  HANDLE v101; // [rsp+2C8h] [rbp+1C8h]
  __int64 v102; // [rsp+2D0h] [rbp+1D0h]
  __int64 v103; // [rsp+2D8h] [rbp+1D8h]
  wchar_t v104; // [rsp+2E0h] [rbp+1E0h]
  __int64 v105; // [rsp+2E2h] [rbp+1E2h]
  __int16 v106; // [rsp+2EAh] [rbp+1EAh]
  __int128 v107; // [rsp+2ECh] [rbp+1ECh]
  WCHAR v108; // [rsp+2FCh] [rbp+1FCh]
  _BYTE v109[22]; // [rsp+2FEh] [rbp+1FEh] BYREF
  __int64 v110; // [rsp+318h] [rbp+218h]
  int v111; // [rsp+320h] [rbp+220h]
  int v112; // [rsp+324h] [rbp+224h]
  struct IStream *v113; // [rsp+328h] [rbp+228h]
  __int64 v114; // [rsp+330h] [rbp+230h]
  __int64 v115; // [rsp+338h] [rbp+238h]
  wchar_t v116; // [rsp+340h] [rbp+240h]
  __int64 v117; // [rsp+342h] [rbp+242h]
  __int16 v118; // [rsp+34Ah] [rbp+24Ah]
  __int128 v119; // [rsp+34Ch] [rbp+24Ch]
  wchar_t v120; // [rsp+35Ch] [rbp+25Ch]
  _BYTE v121[22]; // [rsp+35Eh] [rbp+25Eh] BYREF
  __int64 v122; // [rsp+378h] [rbp+278h]
  int v123; // [rsp+380h] [rbp+280h]
  int v124; // [rsp+384h] [rbp+284h]
  HANDLE v125; // [rsp+388h] [rbp+288h]
  __int64 v126; // [rsp+390h] [rbp+290h]
  __int64 v127; // [rsp+398h] [rbp+298h]
  wchar_t v128; // [rsp+3A0h] [rbp+2A0h]
  __int64 v129; // [rsp+3A2h] [rbp+2A2h]
  __int16 v130; // [rsp+3AAh] [rbp+2AAh]
  __int128 v131; // [rsp+3ACh] [rbp+2ACh]
  wchar_t v132; // [rsp+3BCh] [rbp+2BCh]
  _BYTE v133[22]; // [rsp+3BEh] [rbp+2BEh] BYREF
  __int64 v134; // [rsp+3D8h] [rbp+2D8h]
  int v135; // [rsp+3E0h] [rbp+2E0h]
  int v136; // [rsp+3E4h] [rbp+2E4h]
  struct IStream *v137; // [rsp+3E8h] [rbp+2E8h]
  __int64 v138; // [rsp+3F0h] [rbp+2F0h]
  __int64 v139; // [rsp+3F8h] [rbp+2F8h]
  wchar_t v140; // [rsp+400h] [rbp+300h]
  __int64 v141; // [rsp+402h] [rbp+302h]
  __int16 v142; // [rsp+40Ah] [rbp+30Ah]
  __int128 v143; // [rsp+40Ch] [rbp+30Ch]
  wchar_t v144; // [rsp+41Ch] [rbp+31Ch]
  _BYTE v145[22]; // [rsp+41Eh] [rbp+31Eh] BYREF
  __int64 v146; // [rsp+438h] [rbp+338h]
  int v147; // [rsp+440h] [rbp+340h]
  int v148; // [rsp+444h] [rbp+344h]
  HANDLE v149; // [rsp+448h] [rbp+348h]
  __int64 v150; // [rsp+450h] [rbp+350h]
  __int64 v151; // [rsp+458h] [rbp+358h]
  wchar_t v152; // [rsp+460h] [rbp+360h]
  __int64 v153; // [rsp+462h] [rbp+362h]
  __int16 v154; // [rsp+46Ah] [rbp+36Ah]
  __int128 v155; // [rsp+46Ch] [rbp+36Ch]
  __int128 v156; // [rsp+47Ch] [rbp+37Ch]
  __int64 v157; // [rsp+48Ch] [rbp+38Ch]
  __int64 v158; // [rsp+498h] [rbp+398h]
  int v159; // [rsp+4A0h] [rbp+3A0h]
  int v160; // [rsp+4A4h] [rbp+3A4h]
  HANDLE v161; // [rsp+4A8h] [rbp+3A8h]
  __int64 v162; // [rsp+4B0h] [rbp+3B0h]
  __int64 v163; // [rsp+4B8h] [rbp+3B8h]
  wchar_t v164; // [rsp+4C0h] [rbp+3C0h]
  __int64 v165; // [rsp+4C2h] [rbp+3C2h]
  __int16 v166; // [rsp+4CAh] [rbp+3CAh]
  __int128 v167; // [rsp+4CCh] [rbp+3CCh]
  wchar_t v168; // [rsp+4DCh] [rbp+3DCh]
  _BYTE v169[22]; // [rsp+4DEh] [rbp+3DEh] BYREF
  __int64 v170; // [rsp+4F8h] [rbp+3F8h]
  int v171; // [rsp+500h] [rbp+400h]
  int v172; // [rsp+504h] [rbp+404h]
  HANDLE v173; // [rsp+508h] [rbp+408h]
  __int64 v174; // [rsp+510h] [rbp+410h]
  __int64 v175; // [rsp+518h] [rbp+418h]
  wchar_t v176; // [rsp+520h] [rbp+420h]
  __int64 v177; // [rsp+522h] [rbp+422h]
  __int16 v178; // [rsp+52Ah] [rbp+42Ah]
  __int128 v179; // [rsp+52Ch] [rbp+42Ch]
  wchar_t v180; // [rsp+53Ch] [rbp+43Ch]
  _BYTE v181[22]; // [rsp+53Eh] [rbp+43Eh] BYREF
  __int64 v182; // [rsp+558h] [rbp+458h]
  int v183; // [rsp+560h] [rbp+460h]
  int v184; // [rsp+564h] [rbp+464h]
  HANDLE v185; // [rsp+568h] [rbp+468h]
  __int64 v186; // [rsp+570h] [rbp+470h]
  __int64 v187; // [rsp+578h] [rbp+478h]
  wchar_t v188; // [rsp+580h] [rbp+480h]
  __int64 v189; // [rsp+582h] [rbp+482h]
  __int16 v190; // [rsp+58Ah] [rbp+48Ah]
  __int128 v191; // [rsp+58Ch] [rbp+48Ch]
  int v192; // [rsp+59Ch] [rbp+49Ch]
  __int128 v193; // [rsp+5A0h] [rbp+4A0h]
  int v194; // [rsp+5B0h] [rbp+4B0h]
  __int64 v195; // [rsp+5B8h] [rbp+4B8h]
  wil::details::in1diag3 *retaddr; // [rsp+608h] [rbp+508h]

  *(_QWORD *)v21 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v21);
  *(_QWORD *)v21 = 0;
  hObject = 0;
  v23 = 0;
  inited = _InitRestrictedProcess(&hObject, &v23);
  if ( inited >= 0 )
  {
    inited = CreateInstanceInProcess(hObject, v21);
    CloseHandle(hObject);
    CloseHandle(v23);
  }
  if ( inited < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1F3,
      (unsigned int)"shell\\windowsuiimmersive\\userinfo\\usertiletask.cpp",
      (const char *)(unsigned int)inited,
      DueTime);
    goto LABEL_25;
  }
  Parameter = GetCurrentThreadId();
  v25 = 0;
  v26 = -2147467259;
  phNewTimer = 0;
  v26 = CoEnableCallCancellation(0);
  if ( v26 >= 0 )
    CreateTimerQueueTimer(&phNewTimer, 0, CBaseRPCTimeout::s_Callback, &Parameter, 0x1D4C0u, 0x3E8u, 0);
  v23 = 0;
  hObject = 0;
  v28 = 0;
  DueTimea = &v23;
  v10 = (*(__int64 (__fastcall **)(_QWORD, struct IStream *, struct IStream *, struct IStream *))(**(_QWORD **)v21 + 24LL))(
          *(_QWORD *)v21,
          a3,
          a4,
          a5);
  inited = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1F9,
      (unsigned int)"shell\\windowsuiimmersive\\userinfo\\usertiletask.cpp",
      (const char *)(unsigned int)v10,
      (int)&v23);
    goto LABEL_22;
  }
  v29 = 96;
  v30 = a3;
  v31[0] = v23;
  v31[1] = *(_QWORD *)L".jpg";
  v32 = aJpg[4];
  v33 = 0;
  v34 = 0;
  v35 = *(_OWORD *)L"Image96";
  v36 = 0;
  v37 = 0;
  pv = 0;
  v39 = 448;
  v40 = 1;
  v41 = a4;
  v42 = hObject;
  v43 = *(_QWORD *)L".jpg";
  v44 = aJpg[4];
  v45 = 0;
  v46 = 0;
  v47 = *(_OWORD *)L"Image448";
  v48 = aImage448[8];
  memset(v49, 0, sizeof(v49));
  v50 = 0;
  v51 = 448;
  v52 = 2;
  v53 = a5;
  v54 = v28;
  v55 = *(_QWORD *)L".mp4";
  v56 = aMp4[4];
  v57 = 0;
  v58 = 0;
  v59 = *(_OWORD *)L"Video448";
  v60 = aVideo448[8];
  memset(v61, 0, sizeof(v61));
  v62 = 0;
  v63 = 32;
  v64 = 4;
  v65 = v23;
  v66 = 0;
  v67 = *(_QWORD *)L".jpg";
  v68 = aJpg[4];
  v69 = 0;
  v70 = 0;
  v71 = *(_OWORD *)L"Image32";
  v72 = 0;
  v73 = 0;
  v74 = 0;
  v75 = 40;
  v76 = 5;
  v77 = v23;
  v78 = 0;
  v79 = *(_QWORD *)L".jpg";
  v80 = aJpg[4];
  v81 = 0;
  v82 = 0;
  v83 = *(_OWORD *)L"Image40";
  v84 = 0;
  v85 = 0;
  v86 = 0;
  v87 = 48;
  v88 = 6;
  v89 = v23;
  v90 = 0;
  v91 = *(_QWORD *)L".jpg";
  v92 = aJpg[4];
  v93 = 0;
  v94 = 0;
  v95 = *(_OWORD *)L"Image48";
  v96 = 0;
  v97 = 0;
  v98 = 0;
  v99 = 192;
  v100 = 7;
  v101 = hObject;
  v102 = 0;
  v103 = *(_QWORD *)L".jpg";
  v104 = aJpg[4];
  v105 = 0;
  v106 = 0;
  v107 = *(_OWORD *)L"Image192";
  v108 = aImage192[8];
  memset(v109, 0, sizeof(v109));
  v110 = 0;
  v111 = 192;
  v112 = 8;
  v113 = a5;
  v114 = 0;
  v115 = *(_QWORD *)L".mp4";
  v116 = aMp4[4];
  v117 = 0;
  v118 = 0;
  v119 = *(_OWORD *)L"Video192";
  v120 = aVideo192[8];
  memset(v121, 0, sizeof(v121));
  v122 = 0;
  v123 = 240;
  v124 = 9;
  v125 = hObject;
  v126 = 0;
  v127 = *(_QWORD *)L".jpg";
  v128 = aJpg[4];
  v129 = 0;
  v130 = 0;
  v131 = *(_OWORD *)L"Image240";
  v132 = aImage240[8];
  memset(v133, 0, sizeof(v133));
  v134 = 0;
  v135 = 240;
  v136 = 10;
  v137 = a5;
  v138 = 0;
  v139 = *(_QWORD *)L".mp4";
  v140 = aMp4[4];
  v141 = 0;
  v142 = 0;
  v143 = *(_OWORD *)L"Video240";
  v144 = aVideo240[8];
  memset(v145, 0, sizeof(v145));
  v146 = 0;
  v147 = 64;
  v148 = 11;
  v149 = v23;
  v150 = 0;
  v151 = *(_QWORD *)L".jpg";
  v152 = aJpg[4];
  v153 = 0;
  v154 = 0;
  v155 = *(_OWORD *)L"Image64";
  v156 = 0;
  v157 = 0;
  v158 = 0;
  v159 = 208;
  v160 = 12;
  v161 = hObject;
  v162 = 0;
  v163 = *(_QWORD *)L".jpg";
  v164 = aJpg[4];
  v165 = 0;
  v166 = 0;
  v167 = *(_OWORD *)L"Image208";
  v168 = aImage208[8];
  memset(v169, 0, sizeof(v169));
  v170 = 0;
  v171 = 424;
  v172 = 13;
  v173 = hObject;
  v174 = 0;
  v175 = *(_QWORD *)L".jpg";
  v176 = aJpg[4];
  v177 = 0;
  v178 = 0;
  v179 = *(_OWORD *)L"Image424";
  v180 = aImage424[8];
  memset(v181, 0, sizeof(v181));
  v182 = 0;
  v183 = 1080;
  v184 = 14;
  v185 = hObject;
  v186 = 0;
  v187 = *(_QWORD *)L".jpg";
  v188 = aJpg[4];
  v189 = 0;
  v190 = 0;
  v191 = *(_OWORD *)L"Image1080";
  v192 = *(_DWORD *)L"0";
  v193 = 0;
  v194 = 0;
  v195 = 0;
  if ( hObject )
  {
    for ( i = 3; i < 0xE; ++i )
    {
      if ( inited < 0 )
        break;
      if ( v31[12 * i - 1] )
      {
        DueTimea = (HANDLE *)&v31[12 * i];
        inited = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**(_QWORD **)v21 + 32LL))(
                   *(_QWORD *)v21,
                   *((unsigned int *)&v29 + 24 * i + 1),
                   (unsigned int)(int)(float)((float)((float)*((int *)&v29 + 24 * i) * (float)a6) / 100.0));
      }
    }
  }
  v12 = retaddr;
  if ( inited >= 0 )
  {
    v15 = CUserTileBroker::_SaveImages(retaddr, a2, (struct USERTILE_SIZE_MAPPING *)&v29);
    inited = v15;
    v12 = retaddr;
    if ( v15 >= 0 )
      goto LABEL_20;
    v13 = (unsigned int)v15;
    v14 = 543;
  }
  else
  {
    v13 = (unsigned int)inited;
    v14 = 540;
  }
  wil::details::in1diag3::_Log_Hr(
    v12,
    (void *)v14,
    (unsigned int)"shell\\windowsuiimmersive\\userinfo\\usertiletask.cpp",
    (const char *)v13,
    (int)DueTimea);
LABEL_20:
  for ( j = 0; j < 0xE; ++j )
  {
    SafeRelease<IPopupCommand>(&v31[12 * j]);
    CoTaskMemFree(*(&pv + 12 * j));
  }
LABEL_22:
  if ( v26 >= 0 )
  {
    v26 = -2147467259;
    CoDisableCallCancellation(0);
    if ( phNewTimer )
      DeleteTimerQueueTimer(0, phNewTimer, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  }
LABEL_25:
  v17 = *(_QWORD *)v21;
  if ( *(_QWORD *)v21 )
  {
    *(_QWORD *)v21 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18002ddf0  push    rbp
0x18002ddf2  push    rbx
0x18002ddf3  push    rsi
0x18002ddf4  push    rdi
0x18002ddf5  push    r12
0x18002ddf7  push    r14
0x18002ddf9  push    r15
0x18002ddfb  lea     rbp, [rsp-4D0h]
0x18002de03  sub     rsp, 5D0h
0x18002de0a  mov     rax, cs:__security_cookie
0x18002de11  xor     rax, rsp
0x18002de14  mov     [rbp+500h+var_40], rax
0x18002de1b  mov     r14, r9
0x18002de1e  mov     rsi, r8
0x18002de21  mov     r15, rdx
0x18002de24  mov     rbx, [rbp+500h+arg_20]
0x18002de2b  xor     r12d, r12d
0x18002de2e  mov     qword ptr [rsp+600h+var_5C0], r12
0x18002de33  lea     rcx, [rsp+600h+var_5C0]
0x18002de38  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002de3d  mov     qword ptr [rsp+600h+var_5C0], r12
0x18002de42  mov     [rsp+600h+hObject], r12
0x18002de47  mov     [rsp+600h+var_5B0], r12
0x18002de4c  lea     rdx, [rsp+600h+var_5B0]; void **
0x18002de51  lea     rcx, [rsp+600h+hObject]; void **
0x18002de56  call    ?_InitRestrictedProcess@@YAJPEAPEAX0@Z; _InitRestrictedProcess(void * *,void * *)
0x18002de5b  mov     edi, eax
0x18002de5d  test    eax, eax
0x18002de5f  js      short loc_18002DEA0
0x18002de61  lea     rax, [rsp+600h+var_5C0]
0x18002de66  mov     qword ptr [rsp+600h+DueTime], rax; int
0x18002de6b  lea     r9, _GUID_0406e498_0916_49c2_a1c4_10db7bf76766
0x18002de72  lea     r8, CLSID_UserTileValidator
0x18002de79  mov     rdx, [rsp+600h+var_5B0]
0x18002de7e  mov     rcx, [rsp+600h+hObject]; ProcessHandle
0x18002de83  call    _CreateInstanceInProcess
0x18002de88  mov     edi, eax
0x18002de8a  mov     rcx, [rsp+600h+hObject]; hObject
0x18002de8f  call    cs:__imp_CloseHandle
0x18002de95  mov     rcx, [rsp+600h+var_5B0]; hObject
0x18002de9a  call    cs:__imp_CloseHandle
0x18002dea0  mov     rcx, [rbp+508h]; this
0x18002dea7  test    edi, edi
0x18002dea9  jns     short loc_18002DEC4
0x18002deab  mov     r9d, edi; char *
0x18002deae  lea     r8, aShellWindowsui_4; "shell\\windowsuiimmersive\\userinfo\\us"...
0x18002deb5  mov     edx, 1F3h; void *
0x18002deba  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002debf  jmp     loc_18002E66F
0x18002dec4  call    cs:__imp_GetCurrentThreadId
0x18002deca  mov     [rsp+600h+Parameter], eax
0x18002dece  mov     [rsp+600h+var_5A4], r12b
0x18002ded3  mov     [rsp+600h+var_5A0], 80004005h
0x18002dedb  mov     [rsp+600h+phNewTimer], r12
0x18002dee0  xor     ecx, ecx; pReserved
0x18002dee2  call    cs:__imp_CoEnableCallCancellation
0x18002dee8  mov     [rsp+600h+var_5A0], eax
0x18002deec  test    eax, eax
0x18002deee  js      short loc_18002DF1F
0x18002def0  mov     [rsp+600h+Flags], r12d; Flags
0x18002def5  mov     [rsp+600h+Period], 3E8h; Period
0x18002defd  mov     [rsp+600h+DueTime], 1D4C0h; DueTime
0x18002df05  lea     r9, [rsp+600h+Parameter]; Parameter
0x18002df0a  lea     r8, ?s_Callback@CBaseRPCTimeout@@CAXPEAXE@Z; Callback
0x18002df11  xor     edx, edx; TimerQueue
0x18002df13  lea     rcx, [rsp+600h+phNewTimer]; phNewTimer
0x18002df18  call    cs:__imp_CreateTimerQueueTimer
0x18002df1e  nop
0x18002df1f  mov     [rsp+600h+var_5B0], r12
0x18002df24  mov     [rsp+600h+hObject], r12
0x18002df29  mov     [rsp+600h+var_590], r12
0x18002df2e  mov     rcx, qword ptr [rsp+600h+var_5C0]
0x18002df33  mov     rax, [rcx]
0x18002df36  lea     rdx, [rsp+600h+var_590]
0x18002df3b  mov     qword ptr [rsp+600h+Flags], rdx
0x18002df40  lea     rdx, [rsp+600h+hObject]
0x18002df45  mov     qword ptr [rsp+600h+Period], rdx
0x18002df4a  lea     rdx, [rsp+600h+var_5B0]
0x18002df4f  mov     qword ptr [rsp+600h+DueTime], rdx; int
0x18002df54  mov     r9, rbx
0x18002df57  mov     r8, r14
0x18002df5a  mov     rdx, rsi
0x18002df5d  mov     rax, [rax+18h]
0x18002df61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002df66  mov     edi, eax
0x18002df68  mov     rcx, [rbp+508h]; this
0x18002df6f  test    eax, eax
0x18002df71  jns     short loc_18002DF8C
0x18002df73  mov     r9d, eax; char *
0x18002df76  lea     r8, aShellWindowsui_4; "shell\\windowsuiimmersive\\userinfo\\us"...
0x18002df7d  mov     edx, 1F9h; void *
0x18002df82  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002df87  jmp     loc_18002E641
0x18002df8c  mov     [rbp+500h+var_580], 60h ; '`'
0x18002df94  mov     [rbp+500h+var_578], rsi
0x18002df98  mov     rdx, [rsp+600h+var_5B0]
0x18002df9d  mov     [rbp+500h+var_570], rdx
0x18002dfa1  movsd   xmm3, qword ptr cs:aJpg; ".jpg"
0x18002dfa9  movsd   [rbp+500h+var_568], xmm3
0x18002dfae  movzx   r9d, word ptr cs:aJpg+8; ""
0x18002dfb6  mov     [rbp+500h+var_560], r9w
0x18002dfbb  xor     eax, eax
0x18002dfbd  mov     [rbp+500h+var_55E], rax
0x18002dfc1  mov     [rbp+500h+var_556], ax
0x18002dfc5  movups  xmm0, xmmword ptr cs:aImage96; "Image96"
0x18002dfcc  movdqu  [rbp+500h+var_554], xmm0
0x18002dfd1  xorps   xmm1, xmm1
0x18002dfd4  movups  [rbp+500h+var_544], xmm1
0x18002dfd8  mov     [rbp+500h+var_534], rax
0x18002dfdc  mov     [rbp+500h+pv], r12
0x18002dfe0  mov     ecx, 1C0h
0x18002dfe5  mov     [rbp+500h+var_520], ecx
0x18002dfe8  mov     [rbp+500h+var_51C], 1
0x18002dfef  mov     [rbp+500h+var_518], r14
0x18002dff3  mov     r8, [rsp+600h+hObject]
0x18002dff8  mov     [rbp+500h+var_510], r8
0x18002dffc  movsd   [rbp+500h+var_508], xmm3
0x18002e001  mov     [rbp+500h+var_500], r9w
0x18002e006  mov     [rbp+500h+var_4FE], rax
0x18002e00a  mov     [rbp+500h+var_4F6], ax
0x18002e00e  movups  xmm0, xmmword ptr cs:aImage448; "Image448"
0x18002e015  movups  [rbp+500h+var_4F4], xmm0
0x18002e019  movzx   eax, word ptr cs:aImage448+10h; ""
0x18002e020  mov     [rbp+500h+var_4E4], ax
0x18002e024  xorps   xmm0, xmm0
0x18002e027  xor     eax, eax
0x18002e029  movups  xmmword ptr [rbp+500h+var_4E2], xmm0
0x18002e02d  mov     qword ptr [rbp+500h+var_4E2+0Eh], rax
0x18002e031  mov     [rbp+500h+var_4C8], r12
0x18002e035  mov     [rbp+500h+var_4C0], ecx
0x18002e038  mov     [rbp+500h+var_4BC], 2
0x18002e03f  mov     [rbp+500h+var_4B8], rbx
0x18002e043  mov     rax, [rsp+600h+var_590]
0x18002e048  mov     [rbp+500h+var_4B0], rax
0x18002e04c  movsd   xmm2, qword ptr cs:aMp4; ".mp4"
0x18002e054  movsd   [rbp+500h+var_4A8], xmm2
0x18002e059  movzx   ecx, word ptr cs:aMp4+8; ""
0x18002e060  mov     [rbp+500h+var_4A0], cx
0x18002e064  xor     eax, eax
0x18002e066  mov     [rbp+500h+var_49E], rax
0x18002e06a  mov     [rbp+500h+var_496], ax
0x18002e06e  movups  xmm0, xmmword ptr cs:aVideo448; "Video448"
0x18002e075  movups  [rbp+500h+var_494], xmm0
0x18002e079  movzx   eax, word ptr cs:aVideo448+10h; ""
0x18002e080  mov     [rbp+500h+var_484], ax
0x18002e084  xorps   xmm0, xmm0
0x18002e087  xor     eax, eax
0x18002e089  movups  xmmword ptr [rbp+500h+var_482], xmm0
0x18002e08d  mov     qword ptr [rbp+500h+var_482+0Eh], rax
0x18002e094  mov     [rbp+500h+var_468], r12
0x18002e09b  mov     [rbp+500h+var_460], 20h ; ' '
0x18002e0a5  mov     [rbp+500h+var_45C], 4
0x18002e0af  mov     [rbp+500h+var_458], rdx
0x18002e0b6  mov     [rbp+500h+var_450], r12
0x18002e0bd  movsd   [rbp+500h+var_448], xmm3
0x18002e0c5  mov     [rbp+500h+var_440], r9w
0x18002e0cd  mov     [rbp+500h+var_43E], rax
0x18002e0d4  mov     [rbp+500h+var_436], ax
0x18002e0db  movups  xmm0, xmmword ptr cs:aImage32; "Image32"
0x18002e0e2  movdqu  [rbp+500h+var_434], xmm0
0x18002e0ea  movups  [rbp+500h+var_424], xmm1
0x18002e0f1  mov     [rbp+500h+var_414], rax
0x18002e0f8  mov     [rbp+500h+var_408], r12
0x18002e0ff  mov     [rbp+500h+var_400], 28h ; '('
0x18002e109  mov     [rbp+500h+var_3FC], 5
0x18002e113  mov     [rbp+500h+var_3F8], rdx
0x18002e11a  mov     [rbp+500h+var_3F0], r12
0x18002e121  movsd   [rbp+500h+var_3E8], xmm3
0x18002e129  mov     [rbp+500h+var_3E0], r9w
0x18002e131  mov     [rbp+500h+var_3DE], rax
0x18002e138  mov     [rbp+500h+var_3D6], ax
0x18002e13f  movups  xmm0, xmmword ptr cs:aImage40; "Image40"
0x18002e146  movdqu  [rbp+500h+var_3D4], xmm0
0x18002e14e  movups  [rbp+500h+var_3C4], xmm1
0x18002e155  mov     [rbp+500h+var_3B4], rax
0x18002e15c  mov     [rbp+500h+var_3A8], r12
0x18002e163  mov     [rbp+500h+var_3A0], 30h ; '0'
0x18002e16d  mov     [rbp+500h+var_39C], 6
0x18002e177  mov     [rbp+500h+var_398], rdx
0x18002e17e  mov     [rbp+500h+var_390], r12
0x18002e185  movsd   [rbp+500h+var_388], xmm3
0x18002e18d  mov     [rbp+500h+var_380], r9w
0x18002e195  mov     [rbp+500h+var_37E], rax
0x18002e19c  mov     [rbp+500h+var_376], ax
0x18002e1a3  movups  xmm0, xmmword ptr cs:aImage48; "Image48"
0x18002e1aa  movdqu  [rbp+500h+var_374], xmm0
0x18002e1b2  movups  [rbp+500h+var_364], xmm1
0x18002e1b9  mov     [rbp+500h+var_354], rax
0x18002e1c0  mov     [rbp+500h+var_348], r12
0x18002e1c7  mov     r10d, 0C0h
0x18002e1cd  mov     [rbp+500h+var_340], r10d
0x18002e1d4  mov     [rbp+500h+var_33C], 7
0x18002e1de  mov     [rbp+500h+var_338], r8
0x18002e1e5  mov     [rbp+500h+var_330], r12
0x18002e1ec  movsd   [rbp+500h+var_328], xmm3
0x18002e1f4  mov     [rbp+500h+var_320], r9w
0x18002e1fc  mov     [rbp+500h+var_31E], rax
0x18002e203  mov     [rbp+500h+var_316], ax
0x18002e20a  movups  xmm0, xmmword ptr cs:aImage192; "Image192"
0x18002e211  movups  [rbp+500h+var_314], xmm0
0x18002e218  movzx   eax, word ptr cs:aImage192+10h; ""
0x18002e21f  mov     [rbp+500h+var_304], ax
0x18002e226  xorps   xmm0, xmm0
0x18002e229  xor     eax, eax
0x18002e22b  movups  xmmword ptr [rbp+500h+var_302], xmm0
0x18002e232  mov     qword ptr [rbp+500h+var_302+0Eh], rax
0x18002e239  mov     [rbp+500h+var_2E8], r12
0x18002e240  mov     [rbp+500h+var_2E0], r10d
0x18002e247  mov     [rbp+500h+var_2DC], 8
0x18002e251  mov     [rbp+500h+var_2D8], rbx
0x18002e258  mov     [rbp+500h+var_2D0], r12
0x18002e25f  movsd   [rbp+500h+var_2C8], xmm2
0x18002e267  mov     [rbp+500h+var_2C0], cx
0x18002e26e  mov     [rbp+500h+var_2BE], rax
0x18002e275  mov     [rbp+500h+var_2B6], ax
0x18002e27c  movups  xmm0, xmmword ptr cs:aVideo192; "Video192"
0x18002e283  movups  [rbp+500h+var_2B4], xmm0
0x18002e28a  movzx   eax, word ptr cs:aVideo192+10h; ""
0x18002e291  mov     [rbp+500h+var_2A4], ax
0x18002e298  xorps   xmm0, xmm0
0x18002e29b  xor     eax, eax
0x18002e29d  movups  xmmword ptr [rbp+500h+var_2A2], xmm0
0x18002e2a4  mov     qword ptr [rbp+500h+var_2A2+0Eh], rax
0x18002e2ab  mov     [rbp+500h+var_288], r12
0x18002e2b2  mov     r10d, 0F0h
0x18002e2b8  mov     [rbp+500h+var_280], r10d
0x18002e2bf  mov     [rbp+500h+var_27C], 9
0x18002e2c9  mov     [rbp+500h+var_278], r8
0x18002e2d0  mov     [rbp+500h+var_270], r12
0x18002e2d7  movsd   [rbp+500h+var_268], xmm3
0x18002e2df  mov     [rbp+500h+var_260], r9w
0x18002e2e7  mov     [rbp+500h+var_25E], rax
0x18002e2ee  mov     [rbp+500h+var_256], ax
0x18002e2f5  movups  xmm0, xmmword ptr cs:aImage240; "Image240"
0x18002e2fc  movups  [rbp+500h+var_254], xmm0
0x18002e303  movzx   eax, word ptr cs:aImage240+10h; ""
0x18002e30a  mov     [rbp+500h+var_244], ax
0x18002e311  xorps   xmm0, xmm0
0x18002e314  xor     eax, eax
0x18002e316  movups  xmmword ptr [rbp+500h+var_242], xmm0
0x18002e31d  mov     qword ptr [rbp+500h+var_242+0Eh], rax
0x18002e324  mov     [rbp+500h+var_228], r12
0x18002e32b  mov     [rbp+500h+var_220], r10d
0x18002e332  mov     [rbp+500h+var_21C], 0Ah
0x18002e33c  mov     [rbp+500h+var_218], rbx
0x18002e343  mov     [rbp+500h+var_210], r12
0x18002e34a  movsd   [rbp+500h+var_208], xmm2
0x18002e352  mov     [rbp+500h+var_200], cx
0x18002e359  mov     [rbp+500h+var_1FE], rax
0x18002e360  mov     [rbp+500h+var_1F6], ax
0x18002e367  movups  xmm0, xmmword ptr cs:aVideo240; "Video240"
0x18002e36e  movups  [rbp+500h+var_1F4], xmm0
0x18002e375  movzx   eax, word ptr cs:aVideo240+10h; ""
0x18002e37c  mov     [rbp+500h+var_1E4], ax
0x18002e383  xorps   xmm0, xmm0
0x18002e386  xor     eax, eax
0x18002e388  movups  xmmword ptr [rbp+500h+var_1E2], xmm0
0x18002e38f  mov     qword ptr [rbp+500h+var_1E2+0Eh], rax
0x18002e396  mov     [rbp+500h+var_1C8], r12
0x18002e39d  mov     [rbp+500h+var_1C0], 40h ; '@'
0x18002e3a7  mov     [rbp+500h+var_1BC], 0Bh
0x18002e3b1  mov     [rbp+500h+var_1B8], rdx
0x18002e3b8  mov     [rbp+500h+var_1B0], r12
0x18002e3bf  movsd   [rbp+500h+var_1A8], xmm3
0x18002e3c7  mov     [rbp+500h+var_1A0], r9w
0x18002e3cf  mov     [rbp+500h+var_19E], rax
0x18002e3d6  mov     [rbp+500h+var_196], ax
0x18002e3dd  movups  xmm0, xmmword ptr cs:aImage64; "Image64"
0x18002e3e4  movdqu  [rbp+500h+var_194], xmm0
0x18002e3ec  movups  [rbp+500h+var_184], xmm1
0x18002e3f3  mov     [rbp+500h+var_174], rax
0x18002e3fa  mov     [rbp+500h+var_168], r12
0x18002e401  mov     [rbp+500h+var_160], 0D0h
0x18002e40b  mov     [rbp+500h+var_15C], 0Ch
0x18002e415  mov     [rbp+500h+var_158], r8
0x18002e41c  mov     [rbp+500h+var_150], r12
0x18002e423  movsd   [rbp+500h+var_148], xmm3
0x18002e42b  mov     [rbp+500h+var_140], r9w
0x18002e433  mov     [rbp+500h+var_13E], rax
0x18002e43a  mov     [rbp+500h+var_136], ax
0x18002e441  movups  xmm0, xmmword ptr cs:aImage208; "Image208"
0x18002e448  movups  [rbp+500h+var_134], xmm0
0x18002e44f  movzx   eax, word ptr cs:aImage208+10h; ""
0x18002e456  mov     [rbp+500h+var_124], ax
0x18002e45d  xorps   xmm0, xmm0
0x18002e460  xor     eax, eax
0x18002e462  movups  xmmword ptr [rbp+500h+var_122], xmm0
0x18002e469  mov     qword ptr [rbp+500h+var_122+0Eh], rax
0x18002e470  mov     [rbp+500h+var_108], r12
0x18002e477  mov     [rbp+500h+var_100], 1A8h
0x18002e481  mov     [rbp+500h+var_FC], 0Dh
0x18002e48b  mov     [rbp+500h+var_F8], r8
0x18002e492  mov     [rbp+500h+var_F0], r12
0x18002e499  movsd   [rbp+500h+var_E8], xmm3
0x18002e4a1  mov     [rbp+500h+var_E0], r9w
0x18002e4a9  mov     [rbp+500h+var_DE], rax
0x18002e4b0  mov     [rbp+500h+var_D6], ax
0x18002e4b7  movups  xmm0, xmmword ptr cs:aImage424; "Image424"
0x18002e4be  movups  [rbp+500h+var_D4], xmm0
0x18002e4c5  movzx   eax, word ptr cs:aImage424+10h; ""
  ... truncated ...
```
