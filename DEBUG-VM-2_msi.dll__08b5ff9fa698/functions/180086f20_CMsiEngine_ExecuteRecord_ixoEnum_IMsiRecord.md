# CMsiEngine::ExecuteRecord(ixoEnum,IMsiRecord &)

- ea: `0x180086f20`
- end: `0x1800888e2`
- name: `?ExecuteRecord@CMsiEngine@@UEAA?AW4iesEnum@@W4ixoEnum@@AEAVIMsiRecord@@@Z`
- size: `6594`
- prototype: ``
- caller_count: `0`
- callee_count: `26`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180025904`
- `0x180035a8c`
- `0x18003a9c0`
- `0x180061334`
- `0x1800620e4`
- `0x180066074`
- `0x180068680`
- `0x180076e28`
- `0x180079dd0`
- `0x18007b894`
- `0x180085dcc`
- `0x180086f20`
- `0x1800888e8`
- `0x1800b79bc`
- `0x1800ca914`
- `0x1800e80a4`
- `0x180131640`
- `0x180136c78`
- `0x18013a05c`
- `0x18013a830`
- `0x18014e4d4`
- `0x180154294`
- `0x180166ff0`
- `0x1802077f4`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180087655`
- `KERNEL32!CloseHandle` at `0x180088461`
- `KERNEL32!CloseHandle` at `0x180087655`
- `KERNEL32!CloseHandle` at `0x180088461`
- `KERNEL32!GetLastError` at `0x180088089`
- `KERNEL32!GetLastError` at `0x180088409`
- `KERNEL32!GetLastError` at `0x180088089`
- `KERNEL32!GetLastError` at `0x180088409`
- `KERNEL32!GlobalFree` at `0x180087d4d`
- `KERNEL32!GlobalFree` at `0x180087d66`
- `KERNEL32!GlobalFree` at `0x180087e02`
- `KERNEL32!GlobalFree` at `0x180087d4d`
- `KERNEL32!GlobalFree` at `0x180087d66`
- `KERNEL32!GlobalFree` at `0x180087e02`
- `KERNEL32!CreateFileW` at `0x1800883fd`
- `KERNEL32!CreateFileW` at `0x1800883fd`

## string_xrefs

- `0x1800874b9`: `Rollback`
- `0x18008752c`: `Rollback`
- `0x180087543`: `RollbackCleanup`
- `0x1800875b3`: `RollbackCleanup`

## pseudocode

```c
__int64 __fastcall CMsiEngine::ExecuteRecord(__int64 *a1, unsigned int a2, _QWORD *a3)
{
  _QWORD *v3; // r15
  unsigned int v4; // r14d
  struct IMsiMessage *v5; // r13
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 result; // rax
  struct IMsiRecord *v10; // rbx
  unsigned int v11; // edi
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rsi
  _QWORD *v15; // r12
  void (__fastcall *v16)(__int64, __int64, __int64); // rdi
  __int64 v17; // rbx
  __int64 v18; // rsi
  void (__fastcall *v19)(__int64, __int64, __int64); // rdi
  __int64 v20; // rbx
  __int64 v21; // rsi
  void (__fastcall *v22)(__int64, __int64, __int64); // rdi
  __int64 v23; // rbx
  unsigned int v24; // esi
  _QWORD *v25; // rbx
  __int64 v26; // rdi
  int v27; // eax
  void (__fastcall **v28)(_QWORD *, __int64, __int64); // r9
  __int64 v29; // rax
  __int64 v30; // rax
  _QWORD *v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // r15
  void (__fastcall *v34)(__int64, __int64, _QWORD); // rdi
  unsigned int v35; // eax
  void *v36; // r12
  __int64 v37; // r14
  unsigned int (__fastcall *v38)(struct IMsiMessage *, const WCHAR *, void **, void **); // rdi
  unsigned int (__fastcall *v39)(struct IMsiMessage *, const WCHAR *, void **, void **); // rdi
  __int64 v40; // rax
  __int64 v41; // rdi
  __int64 v42; // rcx
  unsigned __int16 *v43; // rax
  void *v44; // rax
  void *v45; // rcx
  __int64 v46; // rsi
  __int64 v47; // rcx
  __int64 v48; // rax
  __int64 v49; // rax
  __int64 v50; // r13
  char v51; // al
  __int64 v52; // r14
  struct IMsiRecord *v53; // rax
  __int64 v54; // r13
  unsigned int CurrentDateTime; // eax
  __int64 v56; // rcx
  __int64 v57; // rax
  __int64 v58; // rax
  __int64 v59; // r14
  __int64 v60; // rbx
  __int64 (__fastcall *v61)(__int64, __int64, struct IMsiMessage **); // rdi
  __int64 v62; // rax
  __int64 v63; // rdi
  __int64 (__fastcall *v64)(_QWORD, _QWORD, _QWORD, _QWORD); // r8
  struct IMsiMessage *v65; // rsi
  __int64 (__fastcall *v66)(struct IMsiMessage *, __int64, struct IMsiRecord **); // rdi
  __int64 v67; // rax
  __int64 v68; // rax
  __int64 v69; // rcx
  __int64 v70; // rbx
  unsigned int (__fastcall *v71)(struct IMsiMessage *, const WCHAR *, void **, void **); // rdi
  __int64 v72; // rax
  int v73; // edi
  int v74; // eax
  void *v75; // rcx
  __int64 v76; // rax
  unsigned int ProductInfoRec; // ebx
  int v78; // ecx
  __int64 v79; // rax
  void (__fastcall *v80)(void *, __int64, __int64); // r14
  __int64 v81; // rdi
  struct IMsiRecord *v82; // rax
  unsigned __int16 *v83; // rsi
  DWORD v84; // eax
  __int64 v85; // rcx
  unsigned __int16 *v86; // rax
  __int64 v87; // rsi
  void (__fastcall *v88)(struct IMsiMessage *, _QWORD, __int64); // r13
  MsiString *v89; // rax
  __int64 v90; // r8
  struct IMsiMessage *v91; // rsi
  __int64 (__fastcall *v92)(struct IMsiRecord *, __int64, __int64, __int64); // r13
  __int64 v93; // rsi
  __int64 v94; // rax
  __int64 v95; // rax
  const WCHAR *v96; // rax
  HANDLE FileW; // rax
  DWORD LastError; // esi
  const unsigned __int16 *v99; // rax
  struct IMsiRecord *v100; // rax
  const WCHAR *v101; // rax
  __int64 v102; // rdx
  struct IMsiRecord *v103; // rax
  __int64 (__fastcall *v104)(void (__fastcall **)(_QWORD *, __int64, __int64), __int64, __int64, __int64); // r13
  __int64 v105; // rsi
  __int64 v106; // rax
  __int64 v107; // rax
  __int64 v108; // r13
  unsigned int v109; // eax
  __int64 v110; // rax
  void **v111; // rcx
  unsigned int v112; // eax
  __int64 v113; // rbx
  __int64 v114; // rbx
  int v115; // ebx
  void *v116; // [rsp+40h] [rbp-C0h] BYREF
  void *v117; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v118; // [rsp+50h] [rbp-B0h] BYREF
  void *v119; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD *v120; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v121; // [rsp+68h] [rbp-98h] BYREF
  __int64 v122; // [rsp+70h] [rbp-90h] BYREF
  char v123; // [rsp+78h] [rbp-88h]
  __int64 (__fastcall *v124)(__int64, __int64, __int64, __int64 *); // [rsp+80h] [rbp-80h] BYREF
  struct IMsiMessage *v125; // [rsp+88h] [rbp-78h] BYREF
  struct IMsiRecord *v126; // [rsp+90h] [rbp-70h] BYREF
  int v127; // [rsp+98h] [rbp-68h] BYREF
  void *v128; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v129; // [rsp+A8h] [rbp-58h]
  void (__fastcall **v130)(_QWORD *, __int64, __int64); // [rsp+B0h] [rbp-50h] BYREF
  void *v131; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD *v132; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD *v133; // [rsp+C8h] [rbp-38h]
  unsigned __int16 *v134; // [rsp+D0h] [rbp-30h] BYREF
  int v135; // [rsp+D8h] [rbp-28h]
  HGLOBAL hMem; // [rsp+F0h] [rbp-10h] BYREF
  int v137; // [rsp+F8h] [rbp-8h]
  int v138; // [rsp+FCh] [rbp-4h]
  _BYTE v139[528]; // [rsp+100h] [rbp+0h] BYREF

  v132 = a3;
  LODWORD(v126) = 0;
  v3 = a3;
  v4 = a2;
  v129 = a2;
  v5 = (struct IMsiMessage *)a1;
  v125 = (struct IMsiMessage *)a1;
  v124 = 0;
  if ( !*((_DWORD *)a1 + 22) )
  {
    v10 = PostError(2762);
    v11 = (*(__int64 (__fastcall **)(struct IMsiMessage *, struct IMsiRecord *))(*(_QWORD *)v5 + 208LL))(v5, v10);
    if ( !v10 )
      return v11;
LABEL_20:
    (*(void (__fastcall **)(struct IMsiRecord *))(*(_QWORD *)v10 + 16LL))(v10);
    return v11;
  }
  LODWORD(qword_180309704) = qword_180309704 + 1;
  if ( *((_DWORD *)a1 + 20) )
  {
    if ( (*((_BYTE *)a1 + 36) & 0x40) == 0 )
    {
      (*(void (__fastcall **)(__int64 *, __int64, __int64))(*a1 + 104))(a1, 64, 1);
      v121 = 0;
      v76 = CComPointer<IEnumMsiRecord>::operator=(&v121);
      ProductInfoRec = CMsiEngine::CreateProductInfoRec(v5, v76);
      if ( ProductInfoRec != 1
        || (ProductInfoRec = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(**((_QWORD **)v5 + 22) + 128LL))(
                               *((_QWORD *)v5 + 22),
                               4,
                               v121),
            ProductInfoRec != 1) )
      {
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v121);
        CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v124);
        return ProductInfoRec;
      }
      if ( *((_QWORD *)v5 + 116) )
      {
        v24 = CMsiBaselineManager::SendBaselineDefinitionOpcodes();
        if ( v24 != ProductInfoRec )
        {
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v121);
          goto LABEL_118;
        }
      }
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v121);
    }
    v24 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD *))(**((_QWORD **)v5 + 22) + 128LL))(
            *((_QWORD *)v5 + 22),
            v4,
            v3);
    goto LABEL_118;
  }
  if ( a2 == 8 && !*((_DWORD *)a1 + 122) )
  {
    v13 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1[16] + 48LL))(a1[16], 3);
    CComPointer<IMsiDatabase>::operator=((char *)v5 + 464, v13);
    v14 = *((_QWORD *)v5 + 58);
    v15 = v132;
    v16 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v14 + 120LL);
    v17 = (*(__int64 (__fastcall **)(_QWORD *, __int64))(*v132 + 72LL))(v132, 1);
    v16(v14, 1, v17);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    v18 = *((_QWORD *)v5 + 58);
    v19 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v18 + 120LL);
    v20 = (*(__int64 (__fastcall **)(_QWORD *, __int64))(*v15 + 72LL))(v15, 2);
    v19(v18, 2, v20);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    v21 = *((_QWORD *)v5 + 58);
    v22 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v21 + 120LL);
    v23 = (*(__int64 (__fastcall **)(_QWORD *, __int64))(*v15 + 72LL))(v15, 3);
    v22(v21, 3, v23);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    v24 = 1;
LABEL_118:
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v124);
    return v24;
  }
  if ( *((_DWORD *)a1 + 124)
    || *((_DWORD *)a1 + 122)
    || !a1[58]
    || (v12 = *a1,
        *((_DWORD *)a1 + 122) = 1,
        result = (*(__int64 (__fastcall **)(__int64 *, __int64))(v12 + 128))(a1, 8),
        *((_DWORD *)v5 + 122) = 0,
        *((_DWORD *)v5 + 124) = 1,
        (_DWORD)result == 1) )
  {
    if ( ((*(__int64 (__fastcall **)(struct IMsiMessage *))(*(_QWORD *)v5 + 96LL))(v5) & 0x40) != 0 )
      goto LABEL_6;
    v10 = (struct IMsiRecord *)(*(__int64 (__fastcall **)(struct IMsiMessage *, const wchar_t *))(*(_QWORD *)v5 + 184LL))(
                                 v5,
                                 L"EXECUTEMODE");
    if ( (*(unsigned int (__fastcall **)(struct IMsiRecord *))(*(_QWORD *)v10 + 56LL))(v10) )
    {
      v78 = *(_WORD *)(*(__int64 (__fastcall **)(struct IMsiRecord *))(*(_QWORD *)v10 + 80LL))(v10) & 0xDF;
      if ( v78 == 78 )
      {
        *((_DWORD *)v5 + 15) = 1;
      }
      else if ( v78 == 83 )
      {
        *((_DWORD *)v5 + 15) = 0;
      }
    }
    v32 = *((_QWORD *)v5 + 55);
    v133 = (_QWORD *)((char *)v5 + 440);
    if ( v32 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    *((_QWORD *)v5 + 55) = (*(__int64 (__fastcall **)(struct IMsiMessage *, const unsigned __int16 *))(*(_QWORD *)v5 + 184LL))(
                             v5,
                             L"SCRIPTFILE");
    (*(void (__fastcall **)(struct IMsiMessage *, __int64, __int64))(*(_QWORD *)v5 + 104LL))(v5, 64, 1);
    *((_QWORD *)v5 + 69) = 0;
    v122 = 0;
    v11 = CMsiEngine::CreateProductInfoRec(v5, &v122);
    if ( v11 == 1 )
    {
      v33 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)v5 + 16) + 48LL))(*((_QWORD *)v5 + 16), 3);
      v120 = (_QWORD *)v33;
      (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v33 + 104LL))(v33, 1, 0);
      (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v33 + 104LL))(
        v33,
        2,
        *((unsigned __int16 *)v5 + 16));
      v34 = *(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v33 + 104LL);
      v35 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v5 + 19) + 216LL))(*((_QWORD *)v5 + 19));
      v34(v33, 3, v35);
      v36 = 0;
      v119 = 0;
      if ( *((_QWORD *)v5 + 35) )
      {
        v79 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)v5 + 16) + 48LL))(*((_QWORD *)v5 + 16), 2);
        CComPointer<IMsiDatabase>::operator=(&v119, v79);
        v36 = v119;
        (*(void (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)v119 + 104LL))(v119, 1, 1);
        v80 = *(void (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)v36 + 120LL);
        v81 = (*(__int64 (__fastcall **)(struct IMsiMessage *, _QWORD))(*(_QWORD *)v5 + 144LL))(
                v5,
                *((_QWORD *)v5 + 35));
        v80(v36, 2, v81);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v81 + 16LL))(v81);
      }
      v37 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)v5 + 16) + 48LL))(*((_QWORD *)v5 + 16), 7);
      v121 = v37;
      v117 = &MsiString::s_NullString;
      v116 = &MsiString::s_NullString;
      (*(void (__fastcall **)(__int64, __int64, const WCHAR *))(*(_QWORD *)v37 + 128LL))(v37, 2, L"Rollback");
      v38 = *(unsigned int (__fastcall **)(struct IMsiMessage *, const WCHAR *, void **, void **))(*(_QWORD *)v5 + 792LL);
      (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
      v116 = &MsiString::s_NullString;
      (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
      v117 = &MsiString::s_NullString;
      if ( v38(v5, L"Rollback", &v117, &v116) )
      {
        (*(void (__fastcall **)(__int64, __int64, void *))(*(_QWORD *)v37 + 120LL))(v37, 3, v117);
        (*(void (__fastcall **)(__int64, __int64, void *))(*(_QWORD *)v37 + 120LL))(v37, 4, v116);
      }
      (*(void (__fastcall **)(__int64, __int64, const WCHAR *))(*(_QWORD *)v37 + 128LL))(v37, 5, L"RollbackCleanup");
      v39 = *(unsigned int (__fastcall **)(struct IMsiMessage *, const WCHAR *, void **, void **))(*(_QWORD *)v5 + 792LL);
      (*(void (__fastcall **)(void *))(*(_QWORD *)v116 + 16LL))(v116);
      v116 = &MsiString::s_NullString;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v117 + 16LL))(v117);
      v117 = &MsiString::s_NullString;
      if ( v39(v5, L"RollbackCleanup", &v117, &v116) )
      {
        (*(void (__fastcall **)(__int64, __int64, void *))(*(_QWORD *)v37 + 120LL))(v37, 6, v117);
        (*(void (__fastcall **)(__int64, __int64, void *))(*(_QWORD *)v37 + 120LL))(v37, 7, v116);
      }
      v40 = (*(__int64 (__fastcall **)(struct IMsiMessage *, const unsigned __int16 *))(*(_QWORD *)v5 + 184LL))(
              v5,
              L"IsAdminPackage");
      v41 = v40;
      if ( (*((_BYTE *)v5 + 36) & 2) != 0 )
      {
        LODWORD(v128) = 3;
      }
      else if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v40 + 56LL))(v40) )
      {
        LODWORD(v128) = 4;
      }
      else
      {
        LODWORD(v128) = (4 * (*((_BYTE *)v5 + 36) & 1)) | 1;
      }
      v118 = 0;
      if ( *((_DWORD *)v5 + 15) )
        goto LABEL_90;
      v42 = *((_QWORD *)v5 + 54);
      if ( v42 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
        *((_QWORD *)v5 + 54) = 0;
      }
      CElevate::CElevate((CElevate *)&v127, 1);
      v135 = 260;
      v43 = (unsigned __int16 *)operator new(0x208u);
      v134 = v43;
      if ( v43 )
      {
        v44 = OpenSecuredTempFile(1, v43);
        if ( v44 != (void *)-1LL )
        {
          CloseHandle(v44);
          v131 = &MsiString::s_NullString;
          (*(void (__fastcall **)(void *, unsigned __int16 *, void **))(MsiString::s_NullString + 96LL))(
            &MsiString::s_NullString,
            v134,
            &v131);
          v45 = v131;
          *((_QWORD *)v5 + 54) = v131;
          (*(void (__fastcall **)(void *))(*(_QWORD *)v45 + 8LL))(v45);
          v46 = *((_QWORD *)v5 + 16);
          v124 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *))(*(_QWORD *)v46 + 296LL);
          if ( v118 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v118 + 16LL))(v118);
          v47 = *((_QWORD *)v5 + 54);
          v118 = 0;
          v48 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v47 + 80LL))(v47);
          v49 = v124(v46, v48, 1, &v118);
          v124 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64 *))v49;
          if ( v49 )
          {
            (*(void (__fastcall **)(struct IMsiMessage *, __int64, __int64))(*(_QWORD *)v5 + 24LL))(v5, 0x1000000, v49);
            (*(void (__fastcall **)(void *))(*(_QWORD *)v131 + 16LL))(v131);
            CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>(&v134);
            CElevate::~CElevate((CElevate *)&v127);
            goto LABEL_117;
          }
          (*(void (__fastcall **)(void *))(*(_QWORD *)v131 + 16LL))(v131);
          if ( v135 > 1 )
            operator delete(v134);
          CElevate::~CElevate((CElevate *)&v127);
          v127 = *((_BYTE *)v5 + 579) != 0;
          if ( !(unsigned int)IsTerminalServerInstalled()
            || ((*(__int64 (__fastcall **)(struct IMsiMessage *))(*(_QWORD *)v5 + 96LL))(v5) & 3) != 0 )
          {
            v50 = (__int64)v130;
          }
          else
          {
            v50 = (*(__int64 (__fastcall **)(struct IMsiMessage *, const unsigned __int16 *))(*(_QWORD *)v5 + 184LL))(
                    v5,
                    L"ALLUSERS");
            LODWORD(v126) = 1;
            if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v50 + 56LL))(v50) )
            {
              v123 = 1;
              v51 = 1;
LABEL_62:
              if ( (v51 & 1) != 0 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
              if ( v123 )
                v127 |= 2u;
              v53 = (struct IMsiRecord *)operator new(0x38u);
              v126 = v53;
              if ( v53 )
              {
                v54 = *((_QWORD *)v125 + 16);
                CurrentDateTime = GetCurrentDateTime();
                v53 = (struct IMsiRecord *)CScriptGenerate::CScriptGenerate(
                                             v126,
                                             v118,
                                             *((unsigned __int16 *)v125 + 16),
                                             CurrentDateTime,
                                             (_DWORD)v128,
                                             v127,
                                             v54);
              }
              v5 = v125;
              *((_QWORD *)v125 + 13) = v53;
              if ( !v53 )
              {
                if ( v118 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v118 + 16LL))(v118);
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
                (*(void (__fastcall **)(void *))(*(_QWORD *)v116 + 16LL))(v116);
                (*(void (__fastcall **)(void *))(*(_QWORD *)v117 + 16LL))(v117);
                if ( v37 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
                if ( v36 )
                  (*(void (__fastcall **)(void *))(*(_QWORD *)v36 + 16LL))(v36);
                if ( v33 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
                if ( v122 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v122 + 16LL))(v122);
                (*(void (__fastcall **)(struct IMsiRecord *))(*(_QWORD *)v10 + 16LL))(v10);
                return 3;
              }
              while ( !CScriptGenerate::InitializeScript(*((CScriptGenerate **)v5 + 13), *((_WORD *)v5 + 302)) )
              {
                if ( !PostScriptWriteError(v5) )
                  goto LABEL_117;
              }
              if ( (!v122 || (unsigned __int8)WriteScriptRecord(*((_QWORD *)v5 + 13), 4, v122, 0, v5))
                && (!v33 || (unsigned __int8)WriteScriptRecord(*((_QWORD *)v5 + 13), 5, v33, 0, v5))
                && (!v36 || (unsigned __int8)WriteScriptRecord(*((_QWORD *)v5 + 13), 5, v36, 0, v5))
                && (!v37 || (unsigned __int8)WriteScriptRecord(*((_QWORD *)v5 + 13), 6, v37, 0, v5)) )
              {
LABEL_90:
                v56 = *((_QWORD *)v5 + 55);
                if ( !v56
                  || !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v56 + 56LL))(v56)
                  || *((_QWORD *)v5 + 14) )
                {
                  goto LABEL_91;
                }
                v137 = 260;
                v138 = 260;
                v85 = *((_QWORD *)v5 + 55);
                hMem = v139;
                v86 = (unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v85 + 80LL))(v85);
                ExpandPath(v86, (__int64)&hMem, 0);
                (*(void (__fastcall **)(_QWORD, HGLOBAL, __int64))(**((_QWORD **)v5 + 55) + 96LL))(
                  *((_QWORD *)v5 + 55),
                  hMem,
                  (__int64)v5 + 440);
                v87 = *((_QWORD *)v5 + 55);
                v88 = *(void (__fastcall **)(struct IMsiMessage *, _QWORD, __int64))(*(_QWORD *)v5 + 160LL);
                v89 = MsiString::MsiString((MsiString *)&v126, L"SCRIPTFILE");
                v90 = v87;
                v91 = v125;
                v88(v125, *(_QWORD *)v89, v90);
                (*(void (__fastcall **)(struct IMsiRecord *))(*(_QWORD *)v126 + 16LL))(v126);
                if ( (_DWORD)v128 == 3 )
                {
                  v126 = (struct IMsiRecord *)*((_QWORD *)v91 + 16);
                  v92 = *(__int64 (__fastcall **)(struct IMsiRecord *, __int64, __int64, __int64))(*(_QWORD *)v126
                                                                                                 + 296LL);
                  v93 = CComPointer<IEnumMsiRecord>::operator=(&v118);
                  v94 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v133 + 80LL))(*v133);
                  v95 = v92(v126, v94, 1, v93);
                  CComPointer<IMsiDatabase>::operator=(&v124, v95);
LABEL_168:
                  if ( v124 )
                  {
                    (*(void (__fastcall **)(struct IMsiMessage *, __int64, __int64 (__fastcall *)(__int64, __int64, __int64, __int64 *)))(*(_QWORD *)v125 + 24LL))(
                      v125,
                      0x1000000,
                      v124);
LABEL_119:
                    if ( v137 > 260 )
                      GlobalFree(hMem);
                    v137 = 260;
                    hMem = v139;
                    goto LABEL_117;
                  }
                  v130 = (void (__fastcall **)(_QWORD *, __int64, __int64))operator new(0x38u);
                  if ( !v130 )
                  {
                    *((_QWORD *)v125 + 14) = 0;
                    goto LABEL_119;
                  }
                  v108 = *((_QWORD *)v125 + 16);
                  v109 = GetCurrentDateTime();
                  v110 = CScriptGenerate::CScriptGenerate(
                           v130,
                           v118,
                           *((unsigned __int16 *)v125 + 16),
                           v109,
                           (_DWORD)v128,
                           0,
                           v108);
                  v5 = v125;
                  *((_QWORD *)v125 + 14) = v110;
                  if ( !v110 )
                    goto LABEL_119;
                  while ( !CScriptGenerate::InitializeScript(*((CScriptGenerate **)v5 + 14), *((_WORD *)v5 + 302)) )
                  {
                    if ( !PostScriptWriteError(v5) )
                      goto LABEL_119;
                  }
                  if ( v122 && !(unsigned __int8)WriteScriptRecord(*((_QWORD *)v5 + 14), 4, v122, 0, v5)
                    || v33 && !(unsigned __int8)WriteScriptRecord(*((_QWORD *)v5 + 14), 5, v33, 0, v5)
                    || v36 && !(unsigned __int8)WriteScriptRecord(*((_QWORD *)v5 + 14), 5, v36, 0, v5)
                    || v37 && !(unsigned __int8)WriteScriptRecord(*((_QWORD *)v5 + 14), 6, v37, 0, v5) )
                  {
                    goto LABEL_119;
                  }
                  if ( v137 > 260 )
                    GlobalFree(hMem);
LABEL_91:
                  if ( *((_QWORD *)v5 + 116) )
                  {
                    LODWORD(v126) = CMsiBaselineManager::SendBaselineDefinitionOpcodes();
                    if ( (_DWORD)v126 != 1 )
                    {
                      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v118);
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
                      (*(void (__fastcall **)(void *))(*(_QWORD *)v116 + 16LL))(v116);
                      (*(void (__fastcall **)(void *))(*(_QWORD *)v117 + 16LL))(v117);
                      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v121);
                      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v119);
                      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v120);
                      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v122);
                      (*(void (__fastcall **)(struct IMsiRecord *))(*(_QWORD *)v10 + 16LL))(v10);
                      v24 = (unsigned int)v126;
                      goto LABEL_118;
                    }
                  }
                  if ( v118 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v118 + 16LL))(v118);
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
                  (*(void (__fastcall **)(void *))(*(_QWORD *)v116 + 16LL))(v116);
                  (*(void (__fastcall **)(void *))(*(_QWORD *)v117 + 16LL))(v117);
                  if ( v37 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
                  if ( v36 )
                    (*(void (__fastcall **)(void *))(*(_QWORD *)v36 + 16LL))(v36);
                  if ( v33 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
                  if ( v122 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v122 + 16LL))(v122);
                  (*(void (__fastcall **)(struct IMsiRecord *))(*(_QWORD *)v10 + 16LL))(v10);
                  v3 = v132;
                  v4 = v129;
LABEL_6:
                  if ( !*((_QWORD *)v5 + 13) && !*((_QWORD *)v5 + 14) )
                    return 1;
                  if ( *((_DWORD *)v5 + 120) != 1 )
                  {
                    v69 = *((_QWORD *)v5 + 16);
                    *((_DWORD *)v5 + 120) = 1;
                    v70 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v69 + 48LL))(v69, 3);
                    v130 = (void (__fastcall **)(_QWORD *, __int64, __int64))v70;
                    v128 = &MsiString::s_NullString;
                    v119 = &MsiString::s_NullString;
                    (*(void (__fastcall **)(__int64, __int64, const WCHAR *))(*(_QWORD *)v70 + 128LL))(
                      v70,
                      1,
                      L"GenerateScript");
                    v71 = *(unsigned int (__fastcall **)(struct IMsiMessage *, const WCHAR *, void **, void **))(*(_QWORD *)v5 + 792LL);
                    (*(void (__fastcall **)(void *))(*(_QWORD *)v119 + 16LL))(v119);
                    v119 = &MsiString::s_NullString;
                    (*(void (__fastcall **)(void *))(*(_QWORD *)v128 + 16LL))(v128);
                    v128 = &MsiString::s_NullString;
                    if ( v71(v5, L"GenerateScript", &v128, &v119) )
                    {
                      (*(void (__fastcall **)(__int64, __int64, void *))(*(_QWORD *)v70 + 120LL))(v70, 2, v128);
                      (*(void (__fastcall **)(__int64, __int64, void *))(*(_QWORD *)v70 + 120LL))(v70, 3, v119);
                    }
                    v72 = *(_QWORD *)v5;
                    v73 = *((_DWORD *)v5 + 122);
                    *((_DWORD *)v5 + 122) = 1;
                    v74 = (*(__int64 (__fastcall **)(struct IMsiMessage *, __int64, __int64))(v72 + 24))(
                            v5,
                            0x8000000,
                            v70);
                    v75 = v119;
                    if ( v74 == 2 )
                    {
                      (*(void (__fastcall **)(void *))(*(_QWORD *)v119 + 16LL))(v119);
                      (*(void (__fastcall **)(void *))(*(_QWORD *)v128 + 16LL))(v128);
                      v111 = (void **)&v130;
                      goto LABEL_189;
                    }
                    *((_DWORD *)v5 + 122) = v73;
                    *((_DWORD *)v5 + 123) = 0;
                    (*(void (__fastcall **)(void *))(*(_QWORD *)v75 + 16LL))(v75);
                    (*(void (__fastcall **)(void *))(*(_QWORD *)v128 + 16LL))(v128);
                    if ( v70 )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 16LL))(v70);
                  }
                  if ( v4 == 25 )
                  {
                    v112 = (*(__int64 (__fastcall **)(_QWORD *, __int64))(*v3 + 56LL))(v3, 2);
                    if ( v112 <= 1 )
                    {
                      v115 = (*(__int64 (__fastcall **)(_QWORD *, __int64))(*v3 + 56LL))(v3, 1);
                      *((_QWORD *)v5 + 69) += (int)(v115
                                                  * (*(__int64 (__fastcall **)(_QWORD *, __int64))(*v3 + 56LL))(v3, 3));
                      goto LABEL_10;
                    }
                    if ( v112 == 2 )
                    {
                      v113 = (__int64)(*(int (__fastcall **)(_QWORD *, __int64))(*v3 + 56LL))(v3, 1) << 32;
                      v114 = (*(unsigned int (__fastcall **)(_QWORD *, __int64))(*v3 + 56LL))(v3, 3) + v113;
                      *((_QWORD *)v5 + 69) += v114;
                      (*(void (__fastcall **)(_QWORD *, __int64))(*v3 + 104LL))(v3, 2);
                      (*(void (__fastcall **)(_QWORD *, __int64, __int64))(*v3 + 104LL))(v3, 3, 1);
                      (*(void (__fastcall **)(_QWORD *, __int64, _QWORD))(*v3 + 104LL))(v3, 1, (unsigned int)v114);
                      goto LABEL_11;
                    }
                  }
                  else
                  {
                    if ( v4 != 72 )
                    {
LABEL_10:
                      if ( v4 != 8 )
                      {
LABEL_11:
                        v6 = *((_QWORD *)v5 + 71);
                        if ( !v6
                          || ((*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v6 + 104LL))(v6, 1, 2),
                              (*(void (__fastcall **)(_QWORD, __int64, __int64))(**((_QWORD **)v5 + 71) + 104LL))(
                                *((_QWORD *)v5 + 71),
                                2,
                                1),
                              (*(unsigned int (__fastcall **)(struct IMsiMessage *, __int64, _QWORD))(*(_QWORD *)v5 + 24LL))(
                                v5,
                                167772160,
                                *((_QWORD *)v5 + 71)) != 2) )
                        {
                          v7 = *((_QWORD *)v5 + 13);
                          if ( v7 && !(unsigned __int8)WriteScriptRecord(v7, v4, v3, 0, v5) )
                            return 3;
                          v8 = *((_QWORD *)v5 + 14);
                          if ( v8 && !(unsigned __int8)WriteScriptRecord(v8, v4, v3, 0, v5) )
                            goto LABEL_199;
                          return 1;
                        }
LABEL_190:
                        v24 = 2;
                        goto LABEL_118;
                      }
                      v25 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)v5 + 16) + 48LL))(
                                        *((_QWORD *)v5 + 16),
                                        1);
                      v132 = v25;
                      v26 = (*(__int64 (__fastcall **)(_QWORD *, __int64))(*v3 + 72LL))(v3, 2);
                      v27 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 56LL))(v26);
                      v28 = (void (__fastcall **)(_QWORD *, __int64, __int64))*v25;
                      v130 = (void (__fastcall **)(_QWORD *, __int64, __int64))*v25;
                      if ( v27 )
                      {
                        v28[15](v25, 1, v26);
                      }
                      else
                      {
                        v52 = (*(__int64 (__fastcall **)(_QWORD *, __int64))(*v3 + 72LL))(v3, 1);
                        v130[15](v25, 1, v52);
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
                      }
                      v29 = *(_QWORD *)v5;
                      *((_DWORD *)v5 + 122) = 1;
                      if ( (*(unsigned int (__fastcall **)(struct IMsiMessage *, __int64, _QWORD *))(v29 + 24))(
                             v5,
                             150994944,
                             v25) != 2 )
                      {
                        *((_DWORD *)v5 + 122) = 0;
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
                        if ( !v25 )
                        {
LABEL_36:
                          v4 = v129;
                          goto LABEL_11;
                        }
                        v30 = *v25;
                        v31 = v25;
LABEL_35:
                        (*(void (__fastcall **)(_QWORD *))(v30 + 16))(v31);
                        goto LABEL_36;
                      }
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
                      v111 = (void **)&v132;
LABEL_189:
                      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(v111);
                      goto LABEL_190;
                    }
                    if ( !(*(unsigned int (__fastcall **)(_QWORD *, __int64))(*v3 + 32LL))(v3, 3) )
                      goto LABEL_11;
                    v57 = (*(__int64 (__fastcall **)(_QWORD *, __int64))(*v3 + 80LL))(v3, 1);
                    v120 = &MsiString::s_NullString;
                    (*(void (__fastcall **)(void *, __int64, _QWORD **))(MsiString::s_NullString + 96LL))(
                      &MsiString::s_NullString,
                      v57,
                      &v120);
                    v58 = (*(__int64 (__fastcall **)(_QWORD *, __int64, __int64))(*v120 + 176LL))(v120, 6, 92);
                    v59 = *((_QWORD *)v5 + 16);
                    v60 = v58;
                    v125 = 0;
                    v61 = *(__int64 (__fastcall **)(__int64, __int64, struct IMsiMessage **))(*(_QWORD *)v59 + 120LL);
                    v62 = (*(__int64 (__fastcall **)(_QWORD *))(*v120 + 80LL))(v120);
                    v63 = v61(v59, v62, &v125);
                    v124 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64 *))v63;
                    if ( v63 )
                    {
                      v64 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))v63;
                    }
                    else
                    {
                      v124 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64 *))(*(__int64 (__fastcall **)(struct IMsiMessage *))(*(_QWORD *)v125 + 112LL))(v125);
                      v64 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))v124;
                      if ( !v124 )
                      {
                        v65 = v125;
                        LODWORD(v126) = 0;
                        v66 = *(__int64 (__fastcall **)(struct IMsiMessage *, __int64, struct IMsiRecord **))(*(_QWORD *)v125 + 168LL);
                        v67 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v60 + 80LL))(v60);
                        v68 = v66(v65, v67, &v126);
                        v124 = (__int64 (__fastcall *)(__int64, __int64, __int64, __int64 *))v68;
                        if ( !v68 )
                        {
                          *((_QWORD *)v5 + 69) += (unsigned int)v126;
                          if ( v125 )
                            (*(void (__fastcall **)(struct IMsiMessage *))(*(_QWORD *)v125 + 16LL))(v125);
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
                          v31 = v120;
                          v30 = *v120;
                          goto LABEL_35;
                        }
                        v64 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))v68;
                      }
                    }
                    (*(void (__fastcall **)(struct IMsiMessage *, __int64, __int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD)))(*(_QWORD *)v5 + 24LL))(
                      v5,
                      0x1000000,
                      v64);
                    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v125);
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
                    (*(void (__fastcall **)(_QWORD *))(*v120 + 16LL))(v120);
                  }
LABEL_199:
                  v24 = 3;
                  goto LABEL_118;
                }
                v96 = (const WCHAR *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v91 + 55) + 80LL))(*((_QWORD *)v91 + 55));
                FileW = CreateFileW(v96, 0x40000000u, 1u, 0, 2u, 0x100000u, 0);
                if ( FileW == (HANDLE)-1LL )
                {
                  LastError = GetLastError();
                  v99 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v133 + 80LL))(*v133);
                  v100 = PostError(1101, v99, LastError);
                  CComPointer<IMsiDatabase>::operator=(&v124, v100);
                  (*(void (__fastcall **)(struct IMsiMessage *, __int64, __int64 (__fastcall *)(__int64, __int64, __int64, __int64 *)))(*(_QWORD *)v125 + 24LL))(
                    v125,
                    0x1000000,
                    v124);
                }
                else
                {
                  CloseHandle(FileW);
                  CElevate::CElevate((CElevate *)&v127, 1);
                  v101 = (const WCHAR *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v91 + 55) + 80LL))(*((_QWORD *)v91 + 55));
                  LOBYTE(v102) = 1;
                  v103 = LockdownPath(v101, v102);
                  v126 = v103;
                  if ( !v103 )
                  {
                    v130 = (void (__fastcall **)(_QWORD *, __int64, __int64))*((_QWORD *)v91 + 16);
                    v104 = (__int64 (__fastcall *)(void (__fastcall **)(_QWORD *, __int64, __int64), __int64, __int64, __int64))*((_QWORD *)*v130 + 37);
                    v105 = CComPointer<IEnumMsiRecord>::operator=(&v118);
                    v106 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v133 + 80LL))(*v133);
                    v107 = v104(v130, v106, 1, v105);
                    CComPointer<IMsiDatabase>::operator=(&v124, v107);
                    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v126);
                    CElevate::~CElevate((CElevate *)&v127);
                    goto LABEL_168;
                  }
                  (*(void (__fastcall **)(struct IMsiMessage *, __int64, struct IMsiRecord *))(*(_QWORD *)v91 + 24LL))(
                    v91,
                    0x1000000,
                    v103);
                  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v126);
                  CElevate::~CElevate((CElevate *)&v127);
                }
                if ( v137 > 260 )
                  GlobalFree(hMem);
                v137 = 260;
                hMem = v139;
                CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v118);
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
                (*(void (__fastcall **)(void *))(*(_QWORD *)v116 + 16LL))(v116);
                (*(void (__fastcall **)(void *))(*(_QWORD *)v117 + 16LL))(v117);
                CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v121);
                CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v119);
                CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v120);
                CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v122);
                (*(void (__fastcall **)(struct IMsiRecord *))(*(_QWORD *)v10 + 16LL))(v10);
                v24 = 3;
                goto LABEL_118;
              }
LABEL_117:
              CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v118);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
              (*(void (__fastcall **)(void *))(*(_QWORD *)v116 + 16LL))(v116);
              (*(void (__fastcall **)(void *))(*(_QWORD *)v117 + 16LL))(v117);
              CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v121);
              CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v119);
              CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v120);
              CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v122);
              (*(void (__fastcall **)(struct IMsiRecord *))(*(_QWORD *)v10 + 16LL))(v10);
              v24 = 3;
              goto LABEL_118;
            }
          }
          v51 = (char)v126;
          v123 = 0;
          goto LABEL_62;
        }
        v83 = v134;
        v84 = GetLastError();
        v82 = PostError(1336, v84, v83);
      }
      else
      {
        v135 = 0;
        v82 = PostError(2346);
      }
      CComPointer<IMsiDatabase>::operator=(&v124, v82);
      v24 = (*(__int64 (__fastcall **)(struct IMsiMessage *, __int64 (__fastcall *)(__int64, __int64, __int64, __int64 *)))(*(_QWORD *)v5 + 208LL))(
              v5,
              v124);
      CTempBuffer<unsigned short,1>::~CTempBuffer<unsigned short,1>(&v134);
      CElevate::~CElevate((CElevate *)&v127);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v118);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
      (*(void (__fastcall **)(void *))(*(_QWORD *)v116 + 16LL))(v116);
      (*(void (__fastcall **)(void *))(*(_QWORD *)v117 + 16LL))(v117);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v121);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v119);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v120);
      CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v122);
      (*(void (__fastcall **)(struct IMsiRecord *))(*(_QWORD *)v10 + 16LL))(v10);
      goto LABEL_118;
    }
    if ( v122 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v122 + 16LL))(v122);
    goto LABEL_20;
  }
  return result;
}

```

## disassembly

```asm
0x180086f20  mov     [rsp-8+arg_18], rbx
0x180086f25  push    rbp
0x180086f26  push    rsi
0x180086f27  push    rdi
0x180086f28  push    r12
0x180086f2a  push    r13
0x180086f2c  push    r14
0x180086f2e  push    r15
0x180086f30  lea     rbp, [rsp-220h]
0x180086f38  sub     rsp, 320h
0x180086f3f  mov     rax, cs:__security_cookie
0x180086f46  xor     rax, rsp
0x180086f49  mov     [rbp+250h+var_40], rax
0x180086f50  xor     edi, edi
0x180086f52  mov     [rbp+250h+var_290], r8
0x180086f56  mov     dword ptr [rbp+250h+var_2C0], edi
0x180086f59  mov     r15, r8
0x180086f5c  mov     r14d, edx
0x180086f5f  mov     [rbp+250h+var_2A8], edx
0x180086f62  mov     r13, rcx
0x180086f65  mov     [rbp+250h+var_2C8], rcx
0x180086f69  mov     esi, edi
0x180086f6b  mov     [rbp+250h+var_2D0], rdi
0x180086f6f  cmp     [rcx+58h], edi
0x180086f72  jz      loc_1800870DD
0x180086f78  lea     ebx, [rdi+1]
0x180086f7b  add     dword ptr cs:qword_180309704, ebx
0x180086f81  cmp     [rcx+50h], edi
0x180086f84  jnz     loc_180087E0D
0x180086f8a  cmp     edx, 8
0x180086f8d  jz      loc_18008717A
0x180086f93  cmp     [rcx+1F0h], edi
0x180086f99  jz      loc_180087129
0x180086f9f  mov     rax, [r13+0]
0x180086fa3  mov     rcx, r13
0x180086fa6  mov     rax, [rax+60h]
0x180086faa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086faf  mov     r12d, 3
0x180086fb5  test    al, 40h
0x180086fb7  jz      loc_180087354
0x180086fbd  cmp     [r13+68h], rdi
0x180086fc1  jz      loc_18008711A
0x180086fc7  cmp     [r13+1E0h], ebx
0x180086fce  jnz     loc_180087B6F
0x180086fd4  cmp     r14d, 19h
0x180086fd8  jz      loc_180088792
0x180086fde  cmp     r14d, 48h ; 'H'
0x180086fe2  jz      loc_180087A0A
0x180086fe8  cmp     r14d, 8
0x180086fec  jz      loc_180087285
0x180086ff2  mov     rcx, [r13+238h]
0x180086ff9  test    rcx, rcx
0x180086ffc  jz      short loc_180087054
0x180086ffe  mov     rax, [rcx]
0x180087001  mov     edx, 1
0x180087006  mov     rax, [rax+68h]
0x18008700a  lea     r8d, [rdx+1]
0x18008700e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087013  mov     rcx, [r13+238h]
0x18008701a  mov     edx, 2
0x18008701f  mov     rax, [rcx]
0x180087022  lea     r8d, [rdx-1]
0x180087026  mov     rax, [rax+68h]
0x18008702a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008702f  mov     rax, [r13+0]
0x180087033  mov     edx, 0A000000h
0x180087038  mov     r8, [r13+238h]
0x18008703f  mov     rcx, r13
0x180087042  mov     rax, [rax+18h]
0x180087046  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008704b  cmp     eax, 2
0x18008704e  jz      loc_180088788
0x180087054  mov     rcx, [r13+68h]
0x180087058  test    rcx, rcx
0x18008705b  jz      short loc_180087074
0x18008705d  xor     r9d, r9d
0x180087060  mov     qword ptr [rsp+350h+dwCreationDisposition], r13
0x180087065  mov     r8, r15
0x180087068  mov     edx, r14d
0x18008706b  call    ?WriteScriptRecord@@YA_NPEAVCScriptGenerate@@W4ixoEnum@@AEAVIMsiRecord@@_NAEAUIMsiMessage@@@Z; WriteScriptRecord(CScriptGenerate *,ixoEnum,IMsiRecord &,bool,IMsiMessage &)
0x180087070  test    al, al
0x180087072  jz      short loc_1800870C4
0x180087074  mov     rcx, [r13+70h]
0x180087078  test    rcx, rcx
0x18008707b  jnz     loc_1800888BF
0x180087081  test    rsi, rsi
0x180087084  jz      short loc_180087095
0x180087086  mov     rcx, [rsi]
0x180087089  mov     rax, [rcx+10h]
0x18008708d  mov     rcx, rsi
0x180087090  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087095  mov     eax, 1
0x18008709a  mov     rcx, [rbp+250h+var_40]
0x1800870a1  xor     rcx, rsp; StackCookie
0x1800870a4  call    __security_check_cookie
0x1800870a9  mov     rbx, [rsp+350h+arg_18]
0x1800870b1  add     rsp, 320h
0x1800870b8  pop     r15
0x1800870ba  pop     r14
0x1800870bc  pop     r13
0x1800870be  pop     r12
0x1800870c0  pop     rdi
0x1800870c1  pop     rsi
0x1800870c2  pop     rbp
0x1800870c3  retn
0x1800870c4  test    rsi, rsi
0x1800870c7  jz      short loc_1800870D8
0x1800870c9  mov     rax, [rsi]
0x1800870cc  mov     rcx, rsi
0x1800870cf  mov     rax, [rax+10h]
0x1800870d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800870d8  mov     eax, r12d
0x1800870db  jmp     short loc_18008709A
0x1800870dd  mov     ecx, 0ACAh; int
0x1800870e2  call    ?PostError@@YAPEAVIMsiRecord@@H@Z; PostError(int)
0x1800870e7  mov     rdx, [r13+0]
0x1800870eb  mov     rbx, rax
0x1800870ee  mov     rcx, r13
0x1800870f1  mov     rax, [rdx+0D0h]
0x1800870f8  mov     rdx, rbx
0x1800870fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087100  mov     edi, eax
0x180087102  test    rbx, rbx
0x180087105  jz      short loc_180087116
0x180087107  mov     rcx, [rbx]
0x18008710a  mov     rax, [rcx+10h]
0x18008710e  mov     rcx, rbx
0x180087111  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087116  mov     eax, edi
0x180087118  jmp     short loc_18008709A
0x18008711a  cmp     [r13+70h], rdi
0x18008711e  jz      loc_180087081
0x180087124  jmp     loc_180086FC7
0x180087129  cmp     [rcx+1E8h], edi
0x18008712f  jnz     loc_180086F9F
0x180087135  mov     r8, [rcx+1D0h]
0x18008713c  test    r8, r8
0x18008713f  jz      loc_180086F9F
0x180087145  mov     rax, [rcx]
0x180087148  mov     edx, 8
0x18008714d  mov     [rcx+1E8h], ebx
0x180087153  mov     rax, [rax+80h]
0x18008715a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008715f  mov     [r13+1E8h], edi
0x180087166  mov     [r13+1F0h], ebx
0x18008716d  cmp     eax, ebx
0x18008716f  jnz     loc_18008709A
0x180087175  jmp     loc_180086F9F
0x18008717a  cmp     [rcx+1E8h], edi
0x180087180  jnz     loc_180086F93
0x180087186  mov     rcx, [rcx+80h]
0x18008718d  lea     r14, [r13+1D0h]
0x180087194  mov     r15d, 3
0x18008719a  mov     edx, r15d
0x18008719d  mov     rax, [rcx]
0x1800871a0  mov     rax, [rax+30h]
0x1800871a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800871a9  mov     rdx, rax
0x1800871ac  mov     rcx, r14
0x1800871af  call    ??4?$CComPointer@VIMsiDatabase@@@@QEAAAEAV0@PEAVIMsiDatabase@@@Z; CComPointer<IMsiDatabase>::operator=(IMsiDatabase *)
0x1800871b4  mov     rsi, [r14]
0x1800871b7  mov     r12, [rbp+250h+var_290]
0x1800871bb  mov     rcx, r12
0x1800871be  mov     rax, [rsi]
0x1800871c1  mov     rdx, [r12]
0x1800871c5  mov     rdi, [rax+78h]
0x1800871c9  mov     rax, [rdx+48h]
0x1800871cd  mov     edx, ebx
0x1800871cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800871d4  mov     rbx, rax
0x1800871d7  lea     edx, [r15-2]
0x1800871db  mov     r8, rax
0x1800871de  mov     rcx, rsi
0x1800871e1  mov     rax, rdi
0x1800871e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800871e9  mov     rcx, [rbx]
0x1800871ec  mov     rax, [rcx+10h]
0x1800871f0  mov     rcx, rbx
0x1800871f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800871f8  mov     rdx, [r12]
0x1800871fc  lea     r13d, [r15-1]
0x180087200  mov     rsi, [r14]
0x180087203  mov     rcx, r12
0x180087206  mov     rax, [rsi]
0x180087209  mov     rdi, [rax+78h]
0x18008720d  mov     rax, [rdx+48h]
0x180087211  mov     edx, r13d
0x180087214  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087219  mov     rbx, rax
0x18008721c  mov     r8, rax
0x18008721f  mov     rax, rdi
0x180087222  mov     edx, r13d
0x180087225  mov     rcx, rsi
0x180087228  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008722d  mov     rcx, [rbx]
0x180087230  mov     rax, [rcx+10h]
0x180087234  mov     rcx, rbx
0x180087237  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008723c  mov     rsi, [r14]
0x18008723f  mov     edx, r15d
0x180087242  mov     r8, [r12]
0x180087246  mov     rcx, r12
0x180087249  mov     rax, [rsi]
0x18008724c  mov     rdi, [rax+78h]
0x180087250  mov     rax, [r8+48h]
0x180087254  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087259  mov     rbx, rax
0x18008725c  mov     r8, rax
0x18008725f  mov     rax, rdi
0x180087262  mov     edx, r15d
0x180087265  mov     rcx, rsi
0x180087268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008726d  mov     rcx, [rbx]
0x180087270  mov     rax, [rcx+10h]
0x180087274  mov     rcx, rbx
0x180087277  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008727c  lea     esi, [r15-2]
0x180087280  jmp     loc_180087D2B
0x180087285  mov     rcx, [r13+80h]
0x18008728c  mov     r14d, 1
0x180087292  mov     edx, r14d
0x180087295  mov     rax, [rcx]
0x180087298  mov     rax, [rax+30h]
0x18008729c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800872a1  mov     rbx, rax
0x1800872a4  mov     [rbp+250h+var_290], rax
0x1800872a8  mov     rax, [r15]
0x1800872ab  lea     edx, [r14+1]
0x1800872af  mov     rcx, r15
0x1800872b2  mov     rax, [rax+48h]
0x1800872b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800872bb  mov     rdi, rax
0x1800872be  mov     rcx, rdi
0x1800872c1  mov     rax, [rax]
0x1800872c4  mov     rax, [rax+38h]
0x1800872c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800872cd  mov     r9, [rbx]
0x1800872d0  mov     edx, r14d
0x1800872d3  mov     [rbp+250h+var_2A0], r9
0x1800872d7  test    eax, eax
0x1800872d9  jz      loc_18008776D
0x1800872df  mov     rax, [r9+78h]
0x1800872e3  mov     r8, rdi
0x1800872e6  mov     rcx, rbx
0x1800872e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800872ee  mov     rax, [r13+0]
0x1800872f2  mov     r8, rbx
0x1800872f5  mov     edx, 9000000h
0x1800872fa  mov     dword ptr [r13+1E8h], 1
0x180087305  mov     rcx, r13
0x180087308  mov     r14, rbx
0x18008730b  mov     rax, [rax+18h]
0x18008730f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087314  mov     rcx, rdi
0x180087317  cmp     eax, 2
0x18008731a  jz      loc_180088773
0x180087320  mov     dword ptr [r13+1E8h], 0
0x18008732b  mov     rax, [rdi]
0x18008732e  mov     rax, [rax+10h]
0x180087332  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087337  test    rbx, rbx
0x18008733a  jz      short loc_18008734B
0x18008733c  mov     rax, [rbx]
0x18008733f  mov     rcx, rbx
0x180087342  mov     rax, [rax+10h]
0x180087346  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008734b  mov     r14d, [rbp+250h+var_2A8]
0x18008734f  jmp     loc_180086FF2
0x180087354  mov     rax, [r13+0]
0x180087358  lea     rdx, aExecutemode; "EXECUTEMODE"
0x18008735f  mov     rcx, r13
0x180087362  mov     rax, [rax+0B8h]
0x180087369  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008736e  mov     rbx, rax
0x180087371  mov     rcx, rbx
0x180087374  mov     rax, [rax]
0x180087377  mov     rax, [rax+38h]
0x18008737b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087380  test    eax, eax
0x180087382  jnz     loc_180087EDE
0x180087388  lea     rdi, [r13+1B8h]
0x18008738f  xor     r14d, r14d
0x180087392  mov     rcx, [rdi]
0x180087395  mov     [rbp+250h+var_288], rdi
0x180087399  test    rcx, rcx
0x18008739c  jnz     loc_180087F1A
0x1800873a2  mov     rax, [r13+0]
0x1800873a6  lea     rdx, aScriptfile_0; "SCRIPTFILE"
0x1800873ad  mov     rcx, r13
0x1800873b0  mov     rax, [rax+0B8h]
0x1800873b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800873bc  mov     [rdi], rax
0x1800873bf  mov     edx, 40h ; '@'
0x1800873c4  mov     rax, [r13+0]
0x1800873c8  mov     rcx, r13
0x1800873cb  lea     r8d, [rdx-3Fh]
0x1800873cf  mov     rax, [rax+68h]
0x1800873d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800873d8  lea     rdx, [rsp+350h+var_2E0]
0x1800873dd  mov     [r13+228h], r14
  ... truncated ...
```
