# RunAnAssessment

- ea: `0x140010258`
- end: `0x14001115e`
- name: `RunAnAssessment`
- size: `3846`
- prototype: ``
- caller_count: `1`
- callee_count: `50`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x1400100a4`

## callees

- `0x140001a70`
- `0x140001abc`
- `0x140004170`
- `0x140004348`
- `0x14000449c`
- `0x1400045d4`
- `0x14000543c`
- `0x140005b80`
- `0x140005d78`
- `0x140005f4c`
- `0x1400063ac`
- `0x140006544`
- `0x1400069ec`
- `0x140006c44`
- `0x140006d74`
- `0x1400085b4`
- `0x140008654`
- `0x1400086f8`
- `0x14000a920`
- `0x14000ad20`
- `0x14000b048`
- `0x14000e6cc`
- `0x14000f858`
- `0x140010258`
- `0x1400117f4`
- `0x140011b30`
- `0x1400120ac`
- `0x140016480`
- `0x140016d04`
- `0x140017af0`
- `0x14001827c`
- `0x1400182f8`
- `0x140019a1c`
- `0x1400342b4`
- `0x14003eb64`
- `0x14003ec14`
- `0x14003f8e0`
- `0x14003fa8c`
- `0x140043c78`
- `0x140043f14`
- `0x14004bbb8`
- `0x14004bd20`
- `0x14004bdb8`
- `0x14004eb34`
- `0x14004fe00`
- `0x1400530a8`
- `0x1400640c8`
- `0x140079b4c`
- `0x140113220`
- `0x14011a010`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x1400108fc`
- `KERNEL32!GetTickCount` at `0x140010b6a`
- `KERNEL32!GetTickCount` at `0x1400108fc`
- `KERNEL32!GetTickCount` at `0x140010b6a`
- `KERNEL32!GetLastError` at `0x140010d3d`
- `KERNEL32!GetLastError` at `0x140010ea4`
- `KERNEL32!GetLastError` at `0x140010d3d`
- `KERNEL32!GetLastError` at `0x140010ea4`
- `KERNEL32!Sleep` at `0x140010ab2`
- `KERNEL32!Sleep` at `0x140010ab2`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x140010ada`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x140010ada`

## string_xrefs

- `0x140010f17`: `For assessment %s : wait for completion event was abandoned.`
- `0x140010f2b`: `> For assessment %ws : wait for completion event was abandoned.`
- `0x140010eea`: `For assessment %s : wait for completion event timed out.`
- `0x140010efe`: `> %ws : wait for completion event timed out.`
- `0x1400110bd`: `We have waited for the operation to complete, but it has not completed in a timely manner.  We must return control of the machine to the user and cannot wait any longer.`
- `0x1400110d8`: `We will now end WinSAT execution to return control of the machine.  We will not free resources on the still running thread as this would cause an AV.  We may see notices `
- `0x1400110ec`: `of unfreed resources in APIs that were called by this thread. This is to be expected, and is not an issue in this situation.`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall RunAnAssessment(StatusUpdate *a1, __int64 a2, char a3, mlib::XmlStream *a4)
{
  __int64 v5; // r12
  unsigned int v6; // edx
  StatusUpdate *v7; // rcx
  unsigned int v8; // ebx
  __int64 v10; // rbx
  unsigned __int16 v11; // r9
  const unsigned __int16 *v12; // rax
  __int64 v13; // rax
  unsigned int v14; // r14d
  _QWORD *v15; // rax
  char v16; // dl
  int v17; // r9d
  int v18; // r8d
  __int64 v19; // rsi
  void *v20; // rax
  char v21; // dl
  int v22; // r9d
  int v23; // r8d
  WinSAT::DiskProfiler *v24; // r11
  char v25; // dl
  char v26; // r10
  __int64 v27; // rcx
  void *v28; // rax
  char v29; // dl
  char v30; // r10
  int v31; // r9d
  int v32; // r8d
  void *v33; // rax
  char v34; // dl
  char v35; // r10
  int v36; // r9d
  int v37; // r8d
  void *v38; // rax
  char v39; // dl
  char v40; // r9
  int v41; // r8d
  _QWORD *v42; // rax
  __int64 v43; // rax
  volatile signed __int32 *v44; // r13
  __int64 v45; // rbx
  mlib::MEvent *v46; // rax
  int v47; // r8d
  __int64 v48; // rbx
  unsigned __int16 v49; // r9
  const unsigned __int16 *v50; // rax
  __int64 v51; // rax
  _QWORD *v52; // rax
  __int64 v53; // rax
  __int64 v54; // rax
  __int64 v55; // rbx
  unsigned __int16 v56; // r9
  const unsigned __int16 *v57; // rax
  __int64 v58; // rax
  __int64 v59; // rax
  __int64 v60; // rbx
  __int64 v61; // rax
  __int64 v62; // rax
  __int64 v63; // rax
  __int64 v64; // r13
  __int64 v65; // rax
  __int64 v66; // rax
  __int64 v67; // rax
  __int64 v68; // rax
  __int64 v69; // rax
  __int64 v70; // rax
  __int64 (__fastcall *v71)(__int64, char *, __int64 *); // rbx
  StatusUpdate *v72; // rcx
  unsigned __int16 v73; // ax
  unsigned __int16 v74; // r9
  const unsigned __int16 *v75; // rax
  StatusUpdate *v76; // rcx
  int v77; // edx
  const char *v78; // r8
  char v79; // r13
  __int64 v80; // rax
  __int64 v81; // rcx
  unsigned __int64 v82; // rbx
  DWORD v83; // r13d
  HANDLE v84; // rax
  void **v85; // r9
  mlib::MHandle *v86; // rax
  int v87; // ebx
  int v88; // eax
  const char *v89; // r8
  __int64 v90; // rbx
  unsigned __int16 v91; // r9
  const unsigned __int16 *v92; // rax
  __int64 v93; // rax
  __int64 v94; // rbx
  unsigned __int16 v95; // r9
  const unsigned __int16 *v96; // rax
  __int64 v97; // rax
  __int64 v98; // rax
  __int64 v99; // rax
  __int64 v100; // rbx
  unsigned __int16 v101; // r9
  const unsigned __int16 *v102; // rax
  __int64 v103; // rax
  unsigned int v104; // ebx
  int v105; // eax
  __int64 v106; // rbx
  const char *v107; // r8
  int v108; // edx
  __int64 v109; // rbx
  unsigned __int16 v110; // r9
  const unsigned __int16 *v111; // rax
  __int64 v112; // rax
  mlib::MHandle *v113; // rax
  __int64 v114; // r9
  unsigned int v115; // edx
  StatusUpdate *v116; // rcx
  BOOL bAlertable[2]; // [rsp+20h] [rbp-E0h]
  char v118; // [rsp+31h] [rbp-CFh]
  _QWORD *v119; // [rsp+38h] [rbp-C8h] BYREF
  char v120; // [rsp+40h] [rbp-C0h]
  __int64 v121; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v122[2]; // [rsp+50h] [rbp-B0h] BYREF
  mlib::XmlStream *v123; // [rsp+60h] [rbp-A0h]
  HANDLE *lpHandles[2]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v125; // [rsp+78h] [rbp-88h]
  int v126; // [rsp+80h] [rbp-80h]
  _QWORD v127[2]; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v128[4]; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v129[2]; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v130[2]; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v131[2]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v132[24]; // [rsp+E8h] [rbp-18h] BYREF
  _QWORD Buffer[64]; // [rsp+100h] [rbp+0h] BYREF
  DWORD LastError; // [rsp+300h] [rbp+200h]
  char v135; // [rsp+304h] [rbp+204h]
  __int64 v136; // [rsp+308h] [rbp+208h]
  char v137[8]; // [rsp+310h] [rbp+210h] BYREF
  char v138[552]; // [rsp+318h] [rbp+218h] BYREF

  v123 = a4;
  v120 = a3;
  v121 = a2;
  v5 = (int)a1;
  if ( (unsigned int)a1 > 7 )
  {
    StatusUpdate::IncrementTick(a1, a2);
    return 1;
  }
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v119,
    1024);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::spf(
    &v119,
    L"Run Assessment, %s, %s",
    qword_140166A90[5 * v5],
    *(_QWORD *)(*(_QWORD *)a2 + 24LL));
  LogNextPhase((unsigned int)(v5 + 1000), v119[3]);
  Log_Text_F(
    (__int64)"base\\winsat\\exe\\main.cpp",
    1764,
    "> Run Assessment %ws %ws",
    qword_140166A90[5 * v5],
    *(_QWORD *)(*(_QWORD *)a2 + 24LL));
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v119);
  v8 = CheckSystemStatus((unsigned int)v5);
  if ( v8 )
  {
    StatusUpdate::IncrementTick(v7, v6);
    return v8;
  }
  v118 = 0;
  if ( BYTE6(qword_140166A90[5 * v5 + 1]) )
  {
    if ( !*(_BYTE *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&theKeyInfo)
                   + 493) )
    {
      v118 = 1;
      Log_Text_F((__int64)"base\\winsat\\exe\\main.cpp", 1782, "> Not D3D9 or better - skipping assessment.");
      if ( byte_1401687D0 )
      {
        byte_1401687D0 = 0;
        v10 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&mlib::stderrw)
            + 240;
        v12 = mlib::MUIStr_((mlib *)"base\\winsat\\exe\\main.cpp", (const char *)0x6F9, 10051, v11);
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v10, v12);
        std::endl(v13);
      }
    }
  }
  dword_1401C1280 = v5;
  v14 = 2;
  switch ( (_DWORD)v5 )
  {
    case 1:
      v38 = operator new(0x68u);
      v122[0] = v38;
      if ( v38 )
      {
        v39 = App::s_VVerbose;
        v40 = App::s_Verbose;
        v41 = qword_1401C6728;
        v131[1] = qword_1401C6258;
        _InterlockedAdd((volatile signed __int32 *)theKeyInfo, 1u);
        v131[0] = theKeyInfo;
        v19 = WinSAT::FeatureEnumeration::FeatureEnumeration((_DWORD)v38, (unsigned int)v131, v41, v41, v40, v39);
      }
      else
      {
        v19 = 0;
      }
      goto LABEL_36;
    case 2:
      v33 = operator new(0x2120u);
      v122[0] = v33;
      if ( v33 )
      {
        v34 = App::s_VVerbose;
        v35 = App::s_Verbose;
        v36 = qword_1401C6728;
        v37 = qword_1401C66F8;
        v130[1] = qword_1401C6258;
        _InterlockedAdd((volatile signed __int32 *)theKeyInfo, 1u);
        v130[0] = theKeyInfo;
        v19 = WinSAT::CPUAssessment::CPUAssessment((_DWORD)v33, (unsigned int)v130, v37, v36, v35, v34);
      }
      else
      {
        v19 = 0;
      }
      goto LABEL_36;
    case 3:
      v28 = operator new(0x488u);
      v122[0] = v28;
      if ( v28 )
      {
        v29 = App::s_VVerbose;
        v30 = App::s_Verbose;
        v31 = qword_1401C6728;
        v32 = qword_1401C66F8;
        v129[1] = qword_1401C6258;
        _InterlockedAdd((volatile signed __int32 *)theKeyInfo, 1u);
        v129[0] = theKeyInfo;
        v19 = WinSAT::MemAssessment1::MemAssessment1((_DWORD)v28, (unsigned int)v129, v32, v31, v30, v29);
      }
      else
      {
        v19 = 0;
      }
      goto LABEL_36;
    case 4:
      v24 = (WinSAT::DiskProfiler *)operator new(0x1F0u);
      v122[0] = v24;
      if ( v24 )
      {
        v25 = App::s_VVerbose;
        v26 = App::s_Verbose;
        v128[3] = qword_1401C6258;
        _InterlockedAdd((volatile signed __int32 *)theKeyInfo, 1u);
        v128[2] = theKeyInfo;
        v27 = WinSAT::DiskProfiler::DiskProfiler(v24, v26, v25);
      }
      else
      {
        v27 = 0;
      }
      v19 = (v27 + 8) & -(__int64)(v27 != 0);
LABEL_36:
      v42 = operator new(8u);
      if ( v42 )
        *v42 = 0;
      else
        v42 = 0;
      v43 = CSmartPtr<mlib::MEvent>::CSmartPtr<mlib::MEvent>(v122, v42);
      v44 = *(volatile signed __int32 **)v43;
      if ( AssessmentDone != *(_QWORD *)v43 )
      {
        v45 = *(_QWORD *)(v43 + 8);
        CSmartPtr<mlib::MEvent>::Release(&AssessmentDone);
        _InterlockedAdd(v44, 1u);
        qword_1401C6268 = v45;
        AssessmentDone = (__int64)v44;
      }
      CSmartPtr<mlib::MEvent>::Release(v122);
      v46 = (mlib::MEvent *)CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&AssessmentDone);
      if ( !mlib::MEvent::Create(v46, 1, v47) )
      {
        v48 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&mlib::stderrw)
            + 240;
        v50 = mlib::MUIStr_((mlib *)"base\\winsat\\exe\\main.cpp", (const char *)0x726, 10074, v49);
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v48, v50);
        std::endl(v51);
        return 1;
      }
      *(_OWORD *)lpHandles = 0;
      v125 = 0;
      v126 = -1;
      v52 = (_QWORD *)CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&AssessmentDone);
      mlib::MWaitList::operator+=(lpHandles, *v52);
      mlib::MWaitList::operator+=(lpHandles, qword_1401C6270);
      if ( App::s_CanceLEventHandle )
        mlib::MWaitList::operator+=(lpHandles, App::s_CanceLEventHandle);
      v53 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&mlib::stdoutw);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v53 + 240, L"> ");
      v55 = v54;
      v57 = mlib::MUIStr_((mlib *)"base\\winsat\\exe\\main.cpp", (const char *)0x735, 10077, v56);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v55, v57);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v58, L" ");
      v60 = v59;
      v61 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 88LL))(v19);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v60, v61);
      v63 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v62, " '");
      v64 = v121;
      mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v63, v121);
      v66 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v65, "'");
      std::endl(v66);
      v67 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&mlib::stdoutw);
      std::basic_ostream<unsigned short>::flush(v67 + 240);
      v68 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&mlib::stderrw);
      std::basic_ostream<unsigned short>::flush(v68 + 240);
      v69 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&mlib::stdouta);
      std::basic_ostream<unsigned short>::flush(v69 + 240);
      v70 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(mlib::stderra);
      std::basic_ostream<unsigned short>::flush(v70 + 240);
      std::basic_ostream<unsigned short>::flush(*(_QWORD *)v123);
      WinSAT::OpStatus::OpStatus((WinSAT::OpStatus *)v137);
      LODWORD(v119) = GetTickCount();
      v71 = *(__int64 (__fastcall **)(__int64, char *, __int64 *))(*(_QWORD *)v19 + 24LL);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v121,
        *(_QWORD *)(*(_QWORD *)v64 + 24LL));
      LOBYTE(v71) = v71(v19, v137, &v121);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v121);
      StatusUpdate::WaitForContinueEvent(v72);
      v73 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 32LL))(v19);
      v75 = mlib::MUIStr_((mlib *)"base\\winsat\\exe\\main.cpp", (const char *)0x750, v73, v74);
      StatusUpdate::SetStatusString(v76, v75);
      if ( (_BYTE)v71 )
      {
        v77 = 1881;
LABEL_47:
        v78 = "ERROR: Could not start assessment.";
LABEL_48:
        v14 = 1;
        Log_Text_F((__int64)"base\\winsat\\exe\\main.cpp", v77, v78);
        v79 = 1;
LABEL_102:
        SaveAssessmentFailureInfo((unsigned int)v5, v19);
LABEL_104:
        dword_1401C1280 = 0;
        if ( v79 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 72LL))(v19);
          (**(void (__fastcall ***)(__int64, __int64))v19)(v19, 1);
        }
        else
        {
          Log_Text_F(
            (__int64)"base\\winsat\\exe\\main.cpp",
            2099,
            "We have waited for the operation to complete, but it has not completed in a timely manner.  We must return c"
            "ontrol of the machine to the user and cannot wait any longer.");
          Log_Text_F(
            (__int64)"base\\winsat\\exe\\main.cpp",
            2100,
            "We will now end WinSAT execution to return control of the machine.  We will not free resources on the still "
            "running thread as this would cause an AV.  We may see notices ");
          Log_Text_F(
            (__int64)"base\\winsat\\exe\\main.cpp",
            2101,
            "of unfreed resources in APIs that were called by this thread. This is to be expected, and is not an issue in"
            " this situation.");
        }
        StatusUpdate::IncrementTick(v116, v115);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v138);
        if ( lpHandles[0] )
          operator delete(lpHandles[0]);
        return v14;
      }
      if ( v118 )
      {
LABEL_63:
        GetTickCount();
        if ( (_DWORD)v5 == 5 && v120 )
        {
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            &v119,
            4096);
          mlib::fundamental_ostringstream<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_ostringstream<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            Buffer,
            &v119);
          mlib::XmlStream::XmlStream(v132, Buffer, 0);
          v87 = OutputXMLForAssessment((mlib::XmlStream *)v132);
          std::flush(Buffer);
          v88 = ProcessDWMResultsFromString(&v119);
          v89 = "> DWM Assessment results processing FAILED";
          if ( v88 >= 0 )
            v89 = "> DWM Assessment results processing SUCCESS";
          Log_Text_F((__int64)"base\\winsat\\exe\\main.cpp", ((v88 >> 31) & 0xFFFFFFFE) + 2039, v89);
          byte_1401C1248 = 1;
          v121 = 0;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
            &v121,
            v119);
          mlib::XmlStream::operator<<<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>(v123);
          mlib::fundamental_ostringstream<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(Buffer);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v119);
        }
        else
        {
          v87 = OutputXMLForAssessment(v123);
        }
        if ( v87 < 0 )
        {
          v114 = qword_140166A90[5 * v5];
          if ( v87 == -2147221502 )
          {
            Log_Text_F(
              (__int64)"base\\winsat\\exe\\main.cpp",
              2053,
              "> %ws Assessment FAILED - too much interference",
              v114);
          }
          else if ( v87 == -2147221503 )
          {
            v14 = 21;
            Log_Text_F((__int64)"base\\winsat\\exe\\main.cpp", 2058, "> %ws Assessment FAILED due to an error", v114);
          }
          else
          {
            v14 = 22;
            bAlertable[0] = v87;
            Log_Text_F(
              (__int64)"base\\winsat\\exe\\main.cpp",
              2062,
              "> %ws Assessment FAILED: error = %08X",
              v114,
              *(_QWORD *)bAlertable);
          }
          goto LABEL_101;
        }
        goto LABEL_103;
      }
      v80 = *(_QWORD *)v19;
      v122[1] = qword_1401C6268;
      _InterlockedAdd((volatile signed __int32 *)AssessmentDone, 1u);
      v122[0] = AssessmentDone;
      if ( (*(unsigned __int8 (__fastcall **)(__int64, char *, _QWORD *))(v80 + 40))(v19, v137, v122) )
      {
        v77 = 1888;
        goto LABEL_47;
      }
      SetWatchDogTimeout(1);
      SetWatchDogTimeout(0);
      if ( App::s_IsPrivateBld )
      {
        LODWORD(v121) = 0;
        if ( !(unsigned int)RegHelper::ReadDWORDValue(v81, L"PrivateError2", &v121, 0) )
        {
          if ( (_DWORD)v121 == 1 )
          {
            Log_Text_F(
              (__int64)"base\\winsat\\exe\\main.cpp",
              1898,
              "PRIVATE: Simulate Assessment Hang (PrivateError2==%u)",
              1);
            SetWatchDogTimeout(1);
          }
          if ( (_DWORD)v121 == 2 )
          {
            Log_Text_F(
              (__int64)"base\\winsat\\exe\\main.cpp",
              1902,
              "PRIVATE: Simulate Bad Hang (PrivateError2==%u)",
              2);
            CancelWatchDogTimer(1);
            SetWatchDogTimeout(0);
            while ( 1 )
              Sleep(0xFu);
          }
        }
      }
      v82 = lpHandles[1] - lpHandles[0];
      v83 = WaitForMultipleObjectsEx(v82, lpHandles[0], 0, 0xFFFFFFFF, 1);
      v126 = v83;
      SetWatchDogTimeout(0);
      CancelWatchDogTimer(1);
      CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&AssessmentDone);
      v84 = mlib::MWaitList::SignaledHandle((mlib::MWaitList *)lpHandles);
      if ( v84 == *v85 )
      {
        if ( *(_QWORD *)CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&AssessmentDone)
          && *(_QWORD *)CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&AssessmentDone) != -1 )
        {
          v86 = (mlib::MHandle *)CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&AssessmentDone);
          mlib::MHandle::Close(v86);
        }
        goto LABEL_63;
      }
      if ( v84 == qword_1401C6270 )
      {
        if ( App::s_isMoobe && qword_1401C6668 )
          qword_1401C6668(qword_1401689B8, 1939, 1);
      }
      else if ( v84 != App::s_CanceLEventHandle )
      {
        if ( v83 == -1 )
        {
          LastError = GetLastError();
          v135 = 1;
          v136 = 0;
          mlib::WinErrorT<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>>::fmt_desc(Buffer);
          v98 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&mlib::stderrw);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v98 + 240, Buffer);
          std::endl(v99);
          v78 = "ERROR: wait list failed.";
          v77 = 1993;
          goto LABEL_48;
        }
        if ( v83 == 258 )
        {
          v90 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&mlib::stderrw)
              + 240;
          v92 = mlib::MUIStr_((mlib *)"base\\winsat\\exe\\main.cpp", (const char *)0x7CC, 10081, v91);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v90, v92);
          std::endl(v93);
          v14 = 12;
          Log_Text_F((__int64)"base\\winsat\\exe\\main.cpp", 1998, "ERROR: wait list timed out.");
LABEL_101:
          v79 = 1;
          goto LABEL_102;
        }
        if ( v83 - 128 < v82 )
        {
          v94 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&mlib::stderrw)
              + 240;
          v96 = mlib::MUIStr_((mlib *)"base\\winsat\\exe\\main.cpp", (const char *)0x7D1, 10081, v95);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v94, v96);
          std::endl(v97);
          v78 = "ERROR: wait list abandoned.";
          v77 = 2003;
          goto LABEL_48;
        }
LABEL_103:
        v79 = 1;
        v14 = CheckSystemStatus((unsigned int)v5);
        goto LABEL_104;
      }
      if ( (*(unsigned __int8 (__fastcall **)(__int64, char *))(*(_QWORD *)v19 + 48LL))(v19, v137) )
      {
        v100 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&mlib::stderrw)
             + 240;
        v102 = mlib::MUIStr_((mlib *)"base\\winsat\\exe\\main.cpp", (const char *)0x792, 10079, v101);
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v100, v102);
        std::endl(v103);
      }
      v104 = (int)(App::s_CancelWaitTimeS * 1000.0);
      Log_Text_F(
        (__int64)"base\\winsat\\exe\\main.cpp",
        1945,
        "> Cancel received, waiting %ums for %ws to cancel",
        v104,
        qword_140166A90[5 * v5]);
      v105 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v19 + 56LL))(v19, v104);
      if ( v105 )
      {
        v79 = 0;
        if ( v105 == 128 )
        {
          Record_InternalError_w("base\\winsat\\exe\\main.cpp");
          v107 = "> For assessment %ws : wait for completion event was abandoned.";
          v108 = 1963;
        }
        else
        {
          if ( v105 != 258 )
          {
            if ( v105 == -1 )
            {
              v106 = qword_140166A90[5 * v5];
              GetLastError();
              Record_Win32Error_w("base\\winsat\\exe\\main.cpp", v106);
              Log_Text_F(
                (__int64)"base\\winsat\\exe\\main.cpp",
                1973,
                "> %ws : cannot determine the status of the assessment wait event.",
                qword_140166A90[5 * v5]);
            }
            goto LABEL_90;
          }
          Record_InternalError_w("base\\winsat\\exe\\main.cpp");
          v107 = "> %ws : wait for completion event timed out.";
          v108 = 1968;
        }
        Log_Text_F((__int64)"base\\winsat\\exe\\main.cpp", v108, v107, qword_140166A90[5 * v5]);
      }
      else
      {
        Log_Text_F(
          (__int64)"base\\winsat\\exe\\main.cpp",
          1955,
          "> %ws assessment succesfully canceled.",
          qword_140166A90[5 * v5]);
        v109 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&mlib::stdoutw)
             + 240;
        v111 = mlib::MUIStr_((mlib *)"base\\winsat\\exe\\main.cpp", (const char *)0x7A4, 10080, v110);
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v109, v111);
        std::endl(v112);
        v79 = 1;
      }
LABEL_90:
      v14 = byte_1401C34A8 != 0 ? 12 : 3;
      if ( *(_QWORD *)CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&AssessmentDone)
        && *(_QWORD *)CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&AssessmentDone) != -1 )
      {
        v113 = (mlib::MHandle *)CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&AssessmentDone);
        mlib::MHandle::Close(v113);
      }
      goto LABEL_102;
    case 5:
      v20 = operator new(0x150u);
      v122[0] = v20;
      if ( v20 )
      {
        v21 = App::s_Verbose;
        v22 = qword_1401C6728;
        v23 = qword_1401C66F8;
        v128[1] = qword_1401C6258;
        _InterlockedAdd((volatile signed __int32 *)theKeyInfo, 1u);
        v128[0] = theKeyInfo;
        v19 = WinSAT::GraphicsOp::GraphicsOp((_DWORD)v20, (unsigned int)v128, v23, v22, 2, v21);
      }
      else
      {
        v19 = 0;
      }
      goto LABEL_36;
    case 6:
      v15 = operator new(0x150u);
      v119 = v15;
      if ( v15 )
      {
        v16 = App::s_Verbose;
        v17 = qword_1401C6728;
        v18 = qword_1401C66F8;
        v127[1] = qword_1401C6258;
        _InterlockedAdd((volatile signed __int32 *)theKeyInfo, 1u);
        v127[0] = theKeyInfo;
        v19 = WinSAT::GraphicsOp::GraphicsOp((_DWORD)v15, (unsigned int)v127, v18, v17, 1, v16);
      }
      else
      {
        v19 = 0;
      }
      goto LABEL_36;
  }
  if ( (_DWORD)v5 != 7 )
    return 1;
  SendMoobeGoSignal();
  return 0;
}

```

## disassembly

```asm
0x140010258  mov     [rsp-8+arg_10], rbx
0x14001025d  push    rbp
0x14001025e  push    rsi
0x14001025f  push    rdi
0x140010260  push    r12
0x140010262  push    r13
0x140010264  push    r14
0x140010266  push    r15
0x140010268  lea     rbp, [rsp-450h]
0x140010270  sub     rsp, 550h
0x140010277  mov     rax, cs:__security_cookie
0x14001027e  xor     rax, rsp
0x140010281  mov     [rbp+480h+var_40], rax
0x140010288  mov     [rsp+580h+var_520], r9
0x14001028d  mov     [rsp+580h+var_540], r8b
0x140010292  mov     rbx, rdx
0x140010295  mov     [rsp+580h+var_538], rdx
0x14001029a  movsxd  r12, ecx
0x14001029d  cmp     r12d, 7
0x1400102a1  ja      loc_14001112A
0x1400102a7  lea     r15, [r12+r12*4]
0x1400102ab  lea     r14, qword_140166A90
0x1400102b2  mov     edx, 400h
0x1400102b7  lea     rcx, [rsp+580h+var_548]
0x1400102bc  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@_K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(unsigned __int64)
0x1400102c1  nop
0x1400102c2  mov     r9, [rbx]
0x1400102c5  mov     r9, [r9+18h]
0x1400102c9  mov     r8, [r14+r15*8]
0x1400102cd  lea     rdx, aRunAssessmentS; "Run Assessment, %s, %s"
0x1400102d4  lea     rcx, [rsp+580h+var_548]
0x1400102d9  call    ?spf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXPEBGZZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::spf(ushort const *,...)
0x1400102de  mov     ecx, 3E8h
0x1400102e3  add     ecx, r12d
0x1400102e6  mov     rdx, [rsp+580h+var_548]
0x1400102eb  mov     rdx, [rdx+18h]
0x1400102ef  call    LogNextPhase
0x1400102f4  mov     rax, [rbx]
0x1400102f7  mov     rcx, [rax+18h]
0x1400102fb  mov     qword ptr [rsp+580h+bAlertable], rcx
0x140010300  mov     r9, [r14+r15*8]
0x140010304  lea     r8, aRunAssessmentW; "> Run Assessment %ws %ws"
0x14001030b  mov     edx, 6E4h
0x140010310  lea     rsi, aBaseWinsatExeM; "base\\winsat\\exe\\main.cpp"
0x140010317  mov     rcx, rsi
0x14001031a  call    Log_Text_F
0x14001031f  nop
0x140010320  lea     rcx, [rsp+580h+var_548]
0x140010325  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14001032a  mov     ecx, r12d
0x14001032d  call    CheckSystemStatus
0x140010332  mov     ebx, eax
0x140010334  xor     r13d, r13d
0x140010337  test    eax, eax
0x140010339  jz      short loc_140010347
0x14001033b  call    ?IncrementTick@StatusUpdate@@QEAAXI@Z; StatusUpdate::IncrementTick(uint)
0x140010340  mov     eax, ebx
0x140010342  jmp     loc_140011134
0x140010347  mov     [rsp+580h+var_54F], r13b
0x14001034c  mov     edi, 1
0x140010351  cmp     [r14+r15*8+0Eh], r13b
0x140010356  jz      short loc_1400103CF
0x140010358  lea     rcx, ?theKeyInfo@@3V?$CSmartPtr@VKeyInfo@@@@A; CSmartPtr<KeyInfo> theKeyInfo
0x14001035f  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x140010364  cmp     [rax+1EDh], r13b
0x14001036b  jnz     short loc_1400103CF
0x14001036d  mov     [rsp+580h+var_54F], dil
0x140010372  lea     r8, aNotD3d9OrBette; "> Not D3D9 or better - skipping assessm"...
0x140010379  mov     edx, 6F6h
0x14001037e  mov     rcx, rsi
0x140010381  call    Log_Text_F
0x140010386  cmp     cs:byte_1401687D0, r13b
0x14001038d  jz      short loc_1400103CF
0x14001038f  mov     cs:byte_1401687D0, r13b
0x140010396  lea     rcx, ?stderrw@mlib@@3V?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@A; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>> mlib::stderrw
0x14001039d  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x1400103a2  lea     rbx, [rax+0F0h]
0x1400103a9  mov     edx, 6F9h; char *
0x1400103ae  mov     r8d, 2743h; int
0x1400103b4  mov     rcx, rsi; this
0x1400103b7  call    ?MUIStr_@mlib@@YAPEBGPEBDHG@Z; mlib::MUIStr_(char const *,int,ushort)
0x1400103bc  mov     rdx, rax
0x1400103bf  mov     rcx, rbx
0x1400103c2  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1400103c7  mov     rcx, rax
0x1400103ca  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x1400103cf  mov     cs:dword_1401C1280, r12d
0x1400103d6  mov     ecx, r12d
0x1400103d9  mov     r14d, 2
0x1400103df  sub     ecx, edi
0x1400103e1  jz      loc_140010661
0x1400103e7  sub     ecx, edi
0x1400103e9  jz      loc_1400105F0
0x1400103ef  sub     ecx, edi
0x1400103f1  jz      loc_14001057C
0x1400103f7  sub     ecx, edi
0x1400103f9  jz      loc_1400104FB
0x1400103ff  sub     ecx, edi
0x140010401  jz      loc_14001048E
0x140010407  sub     ecx, edi
0x140010409  jz      short loc_140010422
0x14001040b  cmp     ecx, edi
0x14001040d  jz      short loc_140010416
0x14001040f  mov     eax, edi
0x140010411  jmp     loc_140011134
0x140010416  call    ?SendMoobeGoSignal@@YAXXZ; SendMoobeGoSignal(void)
0x14001041b  xor     eax, eax
0x14001041d  jmp     loc_140011134
0x140010422  mov     ecx, 150h; Size
0x140010427  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001042c  mov     r10, rax
0x14001042f  mov     [rsp+580h+var_548], rax
0x140010434  test    rax, rax
0x140010437  jz      short loc_140010486
0x140010439  mov     dl, cs:?s_Verbose@App@@2_NA; bool App::s_Verbose
0x14001043f  mov     r9, cs:qword_1401C6728
0x140010446  mov     r8, cs:qword_1401C66F8
0x14001044d  mov     rcx, cs:qword_1401C6258
0x140010454  mov     [rbp+480h+var_4F0], rcx
0x140010458  mov     rcx, cs:?theKeyInfo@@3V?$CSmartPtr@VKeyInfo@@@@A; CSmartPtr<KeyInfo> theKeyInfo
0x14001045f  lock add [rcx], edi
0x140010462  mov     rax, cs:?theKeyInfo@@3V?$CSmartPtr@VKeyInfo@@@@A; CSmartPtr<KeyInfo> theKeyInfo
0x140010469  mov     [rbp+480h+var_4F8], rax
0x14001046d  mov     [rsp+580h+var_558], dl
0x140010471  mov     [rsp+580h+bAlertable], edi
0x140010475  lea     rdx, [rbp+480h+var_4F8]
0x140010479  mov     rcx, r10
0x14001047c  call    ??0GraphicsOp@WinSAT@@QEAA@V?$CSmartPtr@VKeyInfo@@@@AEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@1W4_AssessmentType@01@_N@Z; WinSAT::GraphicsOp::GraphicsOp(CSmartPtr<KeyInfo>,mlib::handle_ostreamT<ushort,std::char_traits<ushort>> &,mlib::handle_ostreamT<ushort,std::char_traits<ushort>> &,WinSAT::GraphicsOp::_AssessmentType,bool)
0x140010481  mov     rsi, rax
0x140010484  jmp     short loc_140010489
0x140010486  mov     rsi, r13
0x140010489  jmp     loc_1400106CC
0x14001048e  mov     ecx, 150h; Size
0x140010493  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140010498  mov     r10, rax
0x14001049b  mov     [rsp+580h+var_530], rax
0x1400104a0  test    rax, rax
0x1400104a3  jz      short loc_1400104F3
0x1400104a5  mov     dl, cs:?s_Verbose@App@@2_NA; bool App::s_Verbose
0x1400104ab  mov     r9, cs:qword_1401C6728
0x1400104b2  mov     r8, cs:qword_1401C66F8
0x1400104b9  mov     rcx, cs:qword_1401C6258
0x1400104c0  mov     [rbp+480h+var_4E0], rcx
0x1400104c4  mov     rcx, cs:?theKeyInfo@@3V?$CSmartPtr@VKeyInfo@@@@A; CSmartPtr<KeyInfo> theKeyInfo
0x1400104cb  lock add [rcx], edi
0x1400104ce  mov     rax, cs:?theKeyInfo@@3V?$CSmartPtr@VKeyInfo@@@@A; CSmartPtr<KeyInfo> theKeyInfo
0x1400104d5  mov     [rbp+480h+var_4E8], rax
0x1400104d9  mov     [rsp+580h+var_558], dl
0x1400104dd  mov     [rsp+580h+bAlertable], r14d
0x1400104e2  lea     rdx, [rbp+480h+var_4E8]
0x1400104e6  mov     rcx, r10
0x1400104e9  call    ??0GraphicsOp@WinSAT@@QEAA@V?$CSmartPtr@VKeyInfo@@@@AEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@1W4_AssessmentType@01@_N@Z; WinSAT::GraphicsOp::GraphicsOp(CSmartPtr<KeyInfo>,mlib::handle_ostreamT<ushort,std::char_traits<ushort>> &,mlib::handle_ostreamT<ushort,std::char_traits<ushort>> &,WinSAT::GraphicsOp::_AssessmentType,bool)
0x1400104ee  mov     rsi, rax
0x1400104f1  jmp     short loc_1400104F6
0x1400104f3  mov     rsi, r13
0x1400104f6  jmp     loc_1400106CC
0x1400104fb  mov     ecx, 1F0h; Size
0x140010500  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140010505  mov     r11, rax
0x140010508  mov     [rsp+580h+var_530], rax
0x14001050d  test    rax, rax
0x140010510  jz      short loc_140010567
0x140010512  mov     dl, cs:?s_VVerbose@App@@2_NA; bool App::s_VVerbose
0x140010518  mov     r10b, cs:?s_Verbose@App@@2_NA; bool App::s_Verbose
0x14001051f  mov     r9, cs:qword_1401C6728
0x140010526  mov     r8, cs:qword_1401C66F8
0x14001052d  mov     rcx, cs:qword_1401C6258
0x140010534  mov     [rbp+480h+var_4D0], rcx
0x140010538  mov     rax, cs:?theKeyInfo@@3V?$CSmartPtr@VKeyInfo@@@@A; CSmartPtr<KeyInfo> theKeyInfo
0x14001053f  lock add [rax], edi
0x140010542  mov     rax, cs:?theKeyInfo@@3V?$CSmartPtr@VKeyInfo@@@@A; CSmartPtr<KeyInfo> theKeyInfo
0x140010549  mov     [rbp+480h+var_4D8], rax
0x14001054d  mov     [rsp+580h+var_558], dl; char
0x140010551  mov     byte ptr [rsp+580h+bAlertable], r10b; char
0x140010556  lea     rdx, [rbp+480h+var_4D8]
0x14001055a  mov     rcx, r11; this
0x14001055d  call    ??0DiskProfiler@WinSAT@@QEAA@V?$CSmartPtr@VKeyInfo@@@@AEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@1_N2@Z; WinSAT::DiskProfiler::DiskProfiler(CSmartPtr<KeyInfo>,mlib::handle_ostreamT<ushort,std::char_traits<ushort>> &,mlib::handle_ostreamT<ushort,std::char_traits<ushort>> &,bool,bool)
0x140010562  mov     rcx, rax
0x140010565  jmp     short loc_14001056A
0x140010567  mov     rcx, r13
0x14001056a  lea     rax, [rcx+8]
0x14001056e  neg     rcx
0x140010571  sbb     rsi, rsi
0x140010574  and     rsi, rax
0x140010577  jmp     loc_1400106CC
0x14001057c  mov     ecx, 488h; Size
0x140010581  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140010586  mov     r11, rax
0x140010589  mov     [rsp+580h+var_530], rax
0x14001058e  test    rax, rax
0x140010591  jz      short loc_1400105E8
0x140010593  mov     dl, cs:?s_VVerbose@App@@2_NA; bool App::s_VVerbose
0x140010599  mov     r10b, cs:?s_Verbose@App@@2_NA; bool App::s_Verbose
0x1400105a0  mov     r9, cs:qword_1401C6728
0x1400105a7  mov     r8, cs:qword_1401C66F8
0x1400105ae  mov     rcx, cs:qword_1401C6258
0x1400105b5  mov     [rbp+480h+var_4C0], rcx
0x1400105b9  mov     rax, cs:?theKeyInfo@@3V?$CSmartPtr@VKeyInfo@@@@A; CSmartPtr<KeyInfo> theKeyInfo
0x1400105c0  lock add [rax], edi
0x1400105c3  mov     rax, cs:?theKeyInfo@@3V?$CSmartPtr@VKeyInfo@@@@A; CSmartPtr<KeyInfo> theKeyInfo
0x1400105ca  mov     [rbp+480h+var_4C8], rax
0x1400105ce  mov     [rsp+580h+var_558], dl
0x1400105d2  mov     byte ptr [rsp+580h+bAlertable], r10b
0x1400105d7  lea     rdx, [rbp+480h+var_4C8]
0x1400105db  mov     rcx, r11
0x1400105de  call    ??0MemAssessment1@WinSAT@@QEAA@V?$CSmartPtr@VKeyInfo@@@@AEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@1_N2@Z; WinSAT::MemAssessment1::MemAssessment1(CSmartPtr<KeyInfo>,mlib::handle_ostreamT<ushort,std::char_traits<ushort>> &,mlib::handle_ostreamT<ushort,std::char_traits<ushort>> &,bool,bool)
0x1400105e3  mov     rsi, rax
0x1400105e6  jmp     short loc_1400105EB
0x1400105e8  mov     rsi, r13
0x1400105eb  jmp     loc_1400106CC
0x1400105f0  mov     ecx, 2120h; Size
0x1400105f5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400105fa  mov     r11, rax
0x1400105fd  mov     [rsp+580h+var_530], rax
0x140010602  test    rax, rax
0x140010605  jz      short loc_14001065C
0x140010607  mov     dl, cs:?s_VVerbose@App@@2_NA; bool App::s_VVerbose
0x14001060d  mov     r10b, cs:?s_Verbose@App@@2_NA; bool App::s_Verbose
0x140010614  mov     r9, cs:qword_1401C6728
0x14001061b  mov     r8, cs:qword_1401C66F8
0x140010622  mov     rcx, cs:qword_1401C6258
0x140010629  mov     [rbp+480h+var_4B0], rcx
0x14001062d  mov     rax, cs:?theKeyInfo@@3V?$CSmartPtr@VKeyInfo@@@@A; CSmartPtr<KeyInfo> theKeyInfo
0x140010634  lock add [rax], edi
0x140010637  mov     rax, cs:?theKeyInfo@@3V?$CSmartPtr@VKeyInfo@@@@A; CSmartPtr<KeyInfo> theKeyInfo
0x14001063e  mov     [rbp+480h+var_4B8], rax
0x140010642  mov     [rsp+580h+var_558], dl
0x140010646  mov     byte ptr [rsp+580h+bAlertable], r10b
0x14001064b  lea     rdx, [rbp+480h+var_4B8]
0x14001064f  mov     rcx, r11
0x140010652  call    ??0CPUAssessment@WinSAT@@QEAA@V?$CSmartPtr@VKeyInfo@@@@AEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@1_N2@Z; WinSAT::CPUAssessment::CPUAssessment(CSmartPtr<KeyInfo>,mlib::handle_ostreamT<ushort,std::char_traits<ushort>> &,mlib::handle_ostreamT<ushort,std::char_traits<ushort>> &,bool,bool)
0x140010657  mov     rsi, rax
0x14001065a  jmp     short loc_14001065F
0x14001065c  mov     rsi, r13
0x14001065f  jmp     short loc_1400106CC
0x140010661  mov     ecx, 68h ; 'h'; Size
0x140010666  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001066b  mov     r10, rax
0x14001066e  mov     [rsp+580h+var_530], rax
0x140010673  test    rax, rax
0x140010676  jz      short loc_1400106C9
0x140010678  mov     dl, cs:?s_VVerbose@App@@2_NA; bool App::s_VVerbose
0x14001067e  mov     r9b, cs:?s_Verbose@App@@2_NA; bool App::s_Verbose
0x140010685  mov     r8, cs:qword_1401C6728
0x14001068c  mov     rcx, cs:qword_1401C6258
0x140010693  mov     [rbp+480h+var_4A0], rcx
0x140010697  mov     rcx, cs:?theKeyInfo@@3V?$CSmartPtr@VKeyInfo@@@@A; CSmartPtr<KeyInfo> theKeyInfo
0x14001069e  lock add [rcx], edi
0x1400106a1  mov     rax, cs:?theKeyInfo@@3V?$CSmartPtr@VKeyInfo@@@@A; CSmartPtr<KeyInfo> theKeyInfo
0x1400106a8  mov     [rbp+480h+var_4A8], rax
0x1400106ac  mov     [rsp+580h+var_558], dl
0x1400106b0  mov     byte ptr [rsp+580h+bAlertable], r9b
0x1400106b5  mov     r9, r8
0x1400106b8  lea     rdx, [rbp+480h+var_4A8]
0x1400106bc  mov     rcx, r10
0x1400106bf  call    ??0FeatureEnumeration@WinSAT@@QEAA@V?$CSmartPtr@VKeyInfo@@@@AEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@1_N2@Z; WinSAT::FeatureEnumeration::FeatureEnumeration(CSmartPtr<KeyInfo>,mlib::handle_ostreamT<ushort,std::char_traits<ushort>> &,mlib::handle_ostreamT<ushort,std::char_traits<ushort>> &,bool,bool)
0x1400106c4  mov     rsi, rax
0x1400106c7  jmp     short loc_1400106CC
0x1400106c9  mov     rsi, r13
0x1400106cc  mov     ecx, 8; Size
0x1400106d1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400106d6  test    rax, rax
0x1400106d9  jz      short loc_1400106E0
0x1400106db  mov     [rax], r13
0x1400106de  jmp     short loc_1400106E3
0x1400106e0  mov     rax, r13
0x1400106e3  mov     rdx, rax
0x1400106e6  lea     rcx, [rsp+580h+var_530]
0x1400106eb  call    ??0?$CSmartPtr@VMEvent@mlib@@@@QEAA@PEAVMEvent@mlib@@@Z; CSmartPtr<mlib::MEvent>::CSmartPtr<mlib::MEvent>(mlib::MEvent *)
0x1400106f0  mov     r13, [rax]
0x1400106f3  cmp     cs:?AssessmentDone@@3V?$CSmartPtr@VMEvent@mlib@@@@A, r13; CSmartPtr<mlib::MEvent> AssessmentDone
0x1400106fa  jz      short loc_14001071F
0x1400106fc  mov     rbx, [rax+8]
0x140010700  lea     rcx, ?AssessmentDone@@3V?$CSmartPtr@VMEvent@mlib@@@@A; CSmartPtr<mlib::MEvent> AssessmentDone
0x140010707  call    ?Release@?$CSmartPtr@VMEvent@mlib@@@@AEAAXXZ; CSmartPtr<mlib::MEvent>::Release(void)
0x14001070c  lock add [r13+0], edi
0x140010711  mov     cs:qword_1401C6268, rbx
0x140010718  mov     cs:?AssessmentDone@@3V?$CSmartPtr@VMEvent@mlib@@@@A, r13; CSmartPtr<mlib::MEvent> AssessmentDone
0x14001071f  lea     rcx, [rsp+580h+var_530]
0x140010724  call    ?Release@?$CSmartPtr@VMEvent@mlib@@@@AEAAXXZ; CSmartPtr<mlib::MEvent>::Release(void)
0x140010729  lea     rcx, ?AssessmentDone@@3V?$CSmartPtr@VMEvent@mlib@@@@A; CSmartPtr<mlib::MEvent> AssessmentDone
0x140010730  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x140010735  mov     edx, edi; int
0x140010737  mov     rcx, rax; this
0x14001073a  call    ?Create@MEvent@mlib@@QEAA_NHH@Z; mlib::MEvent::Create(int,int)
0x14001073f  test    al, al
0x140010741  jnz     short loc_140010785
0x140010743  lea     rcx, ?stderrw@mlib@@3V?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@A; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>> mlib::stderrw
0x14001074a  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14001074f  lea     rbx, [rax+0F0h]
0x140010756  mov     edx, 726h; char *
0x14001075b  mov     r8d, 275Ah; int
0x140010761  lea     rcx, aBaseWinsatExeM; "base\\winsat\\exe\\main.cpp"
0x140010768  call    ?MUIStr_@mlib@@YAPEBGPEBDHG@Z; mlib::MUIStr_(char const *,int,ushort)
0x14001076d  mov     rdx, rax
0x140010770  mov     rcx, rbx
0x140010773  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140010778  mov     rcx, rax
0x14001077b  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x140010780  jmp     loc_14001040F
  ... truncated ...
```
