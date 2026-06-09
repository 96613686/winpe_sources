# Windows::Usage::RestartAcceptable(uint,std::optional<double>,uchar)

- ea: `0x180055c40`
- end: `0x180056c7e`
- name: `?RestartAcceptable@Usage@Windows@@UEBA?AUDeferReasons@SystemInterface@@IV?$optional@N@std@@E@Z`
- size: `4158`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `service_task, installer_update`

## callees

- `0x180007660`
- `0x180008560`
- `0x18000856c`
- `0x18001ba70`
- `0x18001ee04`
- `0x1800209fc`
- `0x18002127c`
- `0x1800239c4`
- `0x180023a58`
- `0x180045140`
- `0x180045278`
- `0x1800455dc`
- `0x180045bd4`
- `0x180054c08`
- `0x180055614`
- `0x180055c40`
- `0x180071010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180056bb4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180056bb4`
- `OLEAUT32!__imp_SysFreeString` at `0x180056690`
- `OLEAUT32!__imp_SysFreeString` at `0x1800566a1`
- `OLEAUT32!__imp_SysFreeString` at `0x180056690`
- `OLEAUT32!__imp_SysFreeString` at `0x1800566a1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180056b55`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180056b55`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180056b08`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180056b08`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180056b47`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180056b47`

## string_xrefs

- `0x180056a32`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\usage.cpp`
- `0x180056c66`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\usage.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
char *__fastcall Windows::Usage::RestartAcceptable(__int64 a1, char *a2, int a3, __int64 a4, unsigned __int8 a5)
{
  char *v6; // rdi
  int v8; // r15d
  __int64 v9; // r12
  _QWORD *v10; // rax
  __int64 v11; // r8
  volatile signed __int32 *v12; // rbx
  _WORD *v13; // rbx
  _WORD *v14; // rbx
  _WORD *v15; // rbx
  volatile signed __int32 *v16; // rbx
  int v17; // r14d
  _QWORD *v18; // rax
  bool v19; // di
  volatile signed __int32 *v20; // rbx
  __int64 v21; // rax
  __int64 v22; // rdi
  void (__fastcall *v23)(__int64, __int128 *, __int64); // rbx
  volatile signed __int32 *v24; // rbx
  char v25; // di
  _QWORD *v26; // rax
  volatile signed __int32 *v27; // rbx
  __int64 v28; // rax
  __int64 v29; // rdi
  void (__fastcall *v30)(__int64, __int128 *, __int64); // rbx
  volatile signed __int32 *v31; // rbx
  __int64 v32; // rax
  __int64 v33; // rdi
  void (__fastcall *v34)(__int64, __int128 *, __int64); // rbx
  volatile signed __int32 *v35; // rbx
  __int64 v36; // rax
  __int64 v37; // rdi
  void (__fastcall *v38)(__int64, __int128 *, __int64); // rbx
  volatile signed __int32 *v39; // rbx
  __int64 v40; // rax
  __int64 v41; // rdi
  void (__fastcall *v42)(__int64, __int128 *, __int64); // rbx
  volatile signed __int32 *v43; // rbx
  __int64 v44; // rax
  int v45; // eax
  __int64 v46; // rbx
  __int64 v47; // rbx
  __int64 v48; // rax
  __int64 v49; // rdi
  void (__fastcall *v50)(__int64, __int128 *, __int64); // rbx
  volatile signed __int32 *v51; // rbx
  __int64 v52; // rax
  __int64 v53; // rdi
  void (__fastcall *v54)(__int64, __int128 *, __int64); // rbx
  volatile signed __int32 *v55; // rbx
  unsigned int UserDisplayState; // eax
  unsigned int v57; // r15d
  __int64 v58; // rax
  __int64 v59; // rdi
  void (__fastcall *v60)(__int64, __int128 *, _QWORD); // rbx
  volatile signed __int32 *v61; // rbx
  __int64 v62; // rax
  __int64 v63; // rdi
  void (__fastcall *v64)(__int64, __int128 *, __int64); // rbx
  volatile signed __int32 *v65; // rbx
  __int64 v66; // rax
  __int64 v67; // rdi
  void (__fastcall *v68)(__int64, __int128 *, __int64); // rbx
  volatile signed __int32 *v69; // rbx
  __int64 v70; // rax
  __int64 v71; // rdi
  void (__fastcall *v72)(__int64, __int128 *, __int64); // rbx
  volatile signed __int32 *v73; // rbx
  int v74; // eax
  __int64 v75; // rax
  __int64 v76; // rdi
  void (__fastcall *v77)(__int64, __int128 *, __int64); // rbx
  volatile signed __int32 *v78; // rbx
  char *v79; // rbx
  LPWSTR FileNameW; // rax
  __int64 v81; // r8
  unsigned __int64 v82; // rdx
  void **v83; // rsi
  __int64 v84; // rdi
  BSTR bstrString; // [rsp+20h] [rbp-E0h] BYREF
  char *v87; // [rsp+28h] [rbp-D8h] BYREF
  volatile signed __int32 *v88; // [rsp+30h] [rbp-D0h]
  BSTR v89; // [rsp+38h] [rbp-C8h] BYREF
  char v90[4]; // [rsp+40h] [rbp-C0h] BYREF
  int v91; // [rsp+44h] [rbp-BCh]
  char *v92; // [rsp+48h] [rbp-B8h]
  __int64 v93; // [rsp+50h] [rbp-B0h] BYREF
  volatile signed __int32 *v94; // [rsp+58h] [rbp-A8h]
  __int128 v95; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v96; // [rsp+70h] [rbp-90h]
  __int128 v97; // [rsp+80h] [rbp-80h] BYREF
  __int128 v98; // [rsp+90h] [rbp-70h]
  __int64 v99; // [rsp+A0h] [rbp-60h] BYREF
  void *v100[2]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v101; // [rsp+B8h] [rbp-48h]
  unsigned __int64 v102; // [rsp+C0h] [rbp-40h]
  void *v103[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v104; // [rsp+D8h] [rbp-28h]
  unsigned __int64 v105; // [rsp+E0h] [rbp-20h]
  __int128 v106; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v107; // [rsp+F8h] [rbp-8h]
  __int64 v108; // [rsp+100h] [rbp+0h]
  void *v109[2]; // [rsp+108h] [rbp+8h] BYREF
  __int64 v110; // [rsp+118h] [rbp+18h]
  unsigned __int64 v111; // [rsp+120h] [rbp+20h]
  WCHAR ExeName[264]; // [rsp+130h] [rbp+30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+388h] [rbp+288h]

  v6 = a2;
  v92 = a2;
  v87 = a2;
  v8 = 0;
  v91 = 0;
  v99 = 0;
  *(_OWORD *)v100 = 0;
  v101 = 0;
  v102 = 7;
  LOWORD(v100[0]) = 0;
  *(_OWORD *)v103 = 0;
  v104 = 0;
  v105 = 7;
  LOWORD(v103[0]) = 0;
  v106 = 0;
  v107 = 0;
  v108 = 7;
  LOWORD(v106) = 0;
  *(_OWORD *)v109 = 0;
  v110 = 0;
  v111 = 7;
  LOWORD(v109[0]) = 0;
  SystemInterface::Service::GetSystem(&v93);
  v9 = v93;
  v10 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, char **))(*(_QWORD *)v93 + 48LL))(v93, &v87);
  (*(void (__fastcall **)(_QWORD, BSTR *))(*(_QWORD *)*v10 + 72LL))(*v10, &bstrString);
  v12 = v88;
  if ( v88 )
  {
    if ( !_InterlockedDecrement(v88 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
      if ( !_InterlockedDecrement(v12 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
    }
  }
  if ( BYTE4(bstrString) )
  {
    if ( ((unsigned __int16)bstrString & 0x400) != 0 )
    {
      if ( v111 < 0x1B )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
          v109,
          27,
          27,
          L"TestOverride_gameModeReason");
      }
      else
      {
        v13 = v109[0];
        v110 = 27;
        memmove_0(v109[0], L"TestOverride_gameModeReason", 0x36u);
        v13[27] = 0;
      }
    }
    if ( !BYTE4(bstrString) )
      goto LABEL_148;
    if ( ((unsigned __int8)bstrString & 2) != 0 )
    {
      if ( v105 < 0x1A )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
          v103,
          26,
          v11,
          L"TestOverride_displayReason");
      }
      else
      {
        v14 = v103[0];
        v104 = 26;
        memmove_0(v103[0], L"TestOverride_displayReason", 0x34u);
        v14[26] = 0;
      }
    }
    if ( !BYTE4(bstrString) )
      goto LABEL_148;
    if ( ((unsigned __int8)bstrString & 0x10) != 0 )
    {
      if ( v102 < 0x19 )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
          v100,
          25,
          v11,
          L"TestOverride_systemReason");
      }
      else
      {
        v15 = v100[0];
        v101 = 25;
        memmove_0(v100[0], L"TestOverride_systemReason", 0x32u);
        v15[25] = 0;
      }
    }
    if ( !BYTE4(bstrString) )
LABEL_148:
      std::_Throw_bad_optional_access();
    LODWORD(v99) = (unsigned int)bstrString & ~a3;
    SystemInterface::DeferReasons::DeferReasons(v6, &v99);
    v16 = v94;
    if ( v94 && _InterlockedExchangeAdd(v94 + 2, 0xFFFFFFFF) == 1 )
    {
LABEL_144:
      (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
      if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
    }
  }
  else
  {
    v17 = 0;
    v19 = 0;
    if ( (a3 & 4) == 0 )
    {
      v18 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, char **))(*(_QWORD *)v9 + 56LL))(v9, &v87);
      v8 = 2;
      v91 = 2;
      if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*v18 + 16LL))(*v18) < a5 )
        v19 = 1;
    }
    if ( (v8 & 2) != 0 )
    {
      v8 &= ~2u;
      v20 = v88;
      if ( v88 )
      {
        if ( _InterlockedExchangeAdd(v88 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
          if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
        }
      }
    }
    if ( v19 )
    {
      v17 = 4;
      v21 = (*(__int64 (__fastcall **)(__int64, char **))(*(_QWORD *)v9 + 96LL))(v9, &v87);
      v22 = *(_QWORD *)v21;
      v23 = *(void (__fastcall **)(__int64, __int128 *, __int64))(**(_QWORD **)v21 + 112LL);
      v95 = 0;
      v96 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v95, L"Defer reason: low battery");
      v23(v22, &v95, 1);
      std::wstring::_Tidy_deallocate(&v95);
      v24 = v88;
      v25 = 0;
      if ( v88 )
      {
        if ( _InterlockedExchangeAdd(v88 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v24)(v24);
          if ( _InterlockedExchangeAdd(v24 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 8LL))(v24);
        }
      }
    }
    else
    {
      v25 = 0;
    }
    if ( (a3 & 0x40) == 0 )
    {
      v26 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, char **))(*(_QWORD *)v9 + 56LL))(v9, &v87);
      v8 |= 4u;
      v91 = v8;
      if ( !(*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*v26 + 40LL))(*v26) )
        v25 = 1;
    }
    if ( (v8 & 4) != 0 )
    {
      v27 = v88;
      if ( v88 )
      {
        if ( _InterlockedExchangeAdd(v88 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v27)(v27);
          if ( _InterlockedExchangeAdd(v27 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v27 + 8LL))(v27);
        }
      }
    }
    if ( v25 )
    {
      v17 |= 0x40u;
      v28 = (*(__int64 (__fastcall **)(__int64, char **))(*(_QWORD *)v9 + 96LL))(v9, &v87);
      v29 = *(_QWORD *)v28;
      v30 = *(void (__fastcall **)(__int64, __int128 *, __int64))(**(_QWORD **)v28 + 112LL);
      v95 = 0;
      v96 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v95, L"Defer reason: not on AC");
      v30(v29, &v95, 1);
      std::wstring::_Tidy_deallocate(&v95);
      v31 = v88;
      if ( v88 )
      {
        if ( _InterlockedExchangeAdd(v88 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v31)(v31);
          if ( _InterlockedExchangeAdd(v31 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v31 + 8LL))(v31);
        }
      }
    }
    if ( (a3 & 1) == 0 )
    {
      if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1) )
      {
        v17 |= 1u;
        v32 = (*(__int64 (__fastcall **)(__int64, char **))(*(_QWORD *)v9 + 96LL))(v9, &v87);
        v33 = *(_QWORD *)v32;
        v34 = *(void (__fastcall **)(__int64, __int128 *, __int64))(**(_QWORD **)v32 + 112LL);
        v95 = 0;
        v96 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v95, L"Defer reason: user active");
        v34(v33, &v95, 1);
        std::wstring::_Tidy_deallocate(&v95);
        v35 = v88;
        if ( v88 )
        {
          if ( _InterlockedExchangeAdd(v88 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v35)(v35);
            if ( _InterlockedExchangeAdd(v35 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v35 + 8LL))(v35);
          }
        }
      }
    }
    if ( (a3 & 0x12) != 0x12 )
    {
      if ( (a3 & 2) == 0 )
      {
        if ( (*(unsigned __int8 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a1 + 40LL))(a1, 0) )
        {
          v17 |= 2u;
          v36 = (*(__int64 (__fastcall **)(__int64, char **))(*(_QWORD *)v9 + 96LL))(v9, &v87);
          v37 = *(_QWORD *)v36;
          v38 = *(void (__fastcall **)(__int64, __int128 *, __int64))(**(_QWORD **)v36 + 112LL);
          v95 = 0;
          v96 = 0;
          std::wstring::_Construct<1,unsigned short const *>(&v95, L"Defer reason: display needed");
          v38(v37, &v95, 1);
          std::wstring::_Tidy_deallocate(&v95);
          v39 = v88;
          if ( v88 )
          {
            if ( !_InterlockedDecrement(v88 + 2) )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v39)(v39);
              if ( !_InterlockedDecrement(v39 + 3) )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v39 + 8LL))(v39);
            }
          }
        }
      }
      if ( (a3 & 0x10) == 0 )
      {
        if ( (*(unsigned __int8 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a1 + 48LL))(a1, 0) )
        {
          v17 |= 0x10u;
          v40 = (*(__int64 (__fastcall **)(__int64, char **))(*(_QWORD *)v9 + 96LL))(v9, &v87);
          v41 = *(_QWORD *)v40;
          v42 = *(void (__fastcall **)(__int64, __int128 *, __int64))(**(_QWORD **)v40 + 112LL);
          v95 = 0;
          v96 = 0;
          std::wstring::_Construct<1,unsigned short const *>(&v95, L"Defer reason: system needed");
          v42(v41, &v95, 1);
          std::wstring::_Tidy_deallocate(&v95);
          v43 = v88;
          if ( v88 )
          {
            if ( !_InterlockedDecrement(v88 + 2) )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v43)(v43);
              if ( !_InterlockedDecrement(v43 + 3) )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v43 + 8LL))(v43);
            }
          }
        }
      }
      if ( (v17 & 0x12) != 0 )
      {
        Windows::DockedHelpers::GetDockedUsage(&v87);
        v89 = 0;
        bstrString = 0;
        v44 = *(_QWORD *)v87;
        bstrString = 0;
        v89 = 0;
        v45 = (*(__int64 (__fastcall **)(char *, BSTR *, BSTR *))(v44 + 56))(v87, &v89, &bstrString);
        if ( v45 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x192,
            (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\usage.cpp",
            (const char *)(unsigned int)v45,
            (int)bstrString);
        v46 = Windows::Strings::to_wstring(&v97, &v89);
        if ( v100 != (void **)v46 )
        {
          std::wstring::_Tidy_deallocate(v100);
          v100[0] = *(void **)v46;
          v100[1] = *(void **)(v46 + 8);
          v101 = *(_QWORD *)(v46 + 16);
          v102 = *(_QWORD *)(v46 + 24);
          *(_QWORD *)(v46 + 16) = 0;
          *(_QWORD *)(v46 + 24) = 7;
          *(_WORD *)v46 = 0;
        }
        std::wstring::_Tidy_deallocate(&v97);
        v47 = Windows::Strings::to_wstring(&v97, &bstrString);
        if ( v103 != (void **)v47 )
        {
          std::wstring::_Tidy_deallocate(v103);
          v103[0] = *(void **)v47;
          v103[1] = *(void **)(v47 + 8);
          v104 = *(_QWORD *)(v47 + 16);
          v105 = *(_QWORD *)(v47 + 24);
          *(_QWORD *)(v47 + 16) = 0;
          *(_QWORD *)(v47 + 24) = 7;
          *(_WORD *)v47 = 0;
        }
        std::wstring::_Tidy_deallocate(&v97);
        if ( (v17 & 0x10) != 0 && !v101 )
        {
          v48 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v9 + 96LL))(v9, &v95);
          v49 = *(_QWORD *)v48;
          v50 = *(void (__fastcall **)(__int64, __int128 *, __int64))(**(_QWORD **)v48 + 112LL);
          v97 = 0;
          v98 = 0;
          std::wstring::_Construct<1,unsigned short const *>(&v97, L"Defer reason: ignoring system needed");
          v50(v49, &v97, 1);
          std::wstring::_Tidy_deallocate(&v97);
          v51 = (volatile signed __int32 *)*((_QWORD *)&v95 + 1);
          if ( *((_QWORD *)&v95 + 1) )
          {
            if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v95 + 1) + 8LL)) )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v51)(v51);
              if ( !_InterlockedDecrement(v51 + 3) )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v51 + 8LL))(v51);
            }
          }
          v17 &= ~0x10u;
        }
        if ( (v17 & 2) != 0 && !v104 )
        {
          v52 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v9 + 96LL))(v9, &v95);
          v53 = *(_QWORD *)v52;
          v54 = *(void (__fastcall **)(__int64, __int128 *, __int64))(**(_QWORD **)v52 + 112LL);
          v97 = 0;
          v98 = 0;
          std::wstring::_Construct<1,unsigned short const *>(&v97, L"Defer reason: ignoring display needed");
          v54(v53, &v97, 1);
          std::wstring::_Tidy_deallocate(&v97);
          v55 = (volatile signed __int32 *)*((_QWORD *)&v95 + 1);
          if ( *((_QWORD *)&v95 + 1) )
          {
            if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v95 + 1) + 8LL)) )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v55)(v55);
              if ( !_InterlockedDecrement(v55 + 3) )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v55 + 8LL))(v55);
            }
          }
          v17 &= ~2u;
        }
        if ( bstrString )
          SysFreeString(bstrString);
        if ( v89 )
          SysFreeString(v89);
        if ( v87 )
          (*(void (__fastcall **)(char *))(*(_QWORD *)v87 + 16LL))(v87);
      }
    }
    if ( (a3 & 0x80) == 0 || (a3 & 0x100) == 0 )
    {
      UserDisplayState = Windows::Usage::GetUserDisplayState();
      v57 = UserDisplayState;
      if ( (a3 & 0x80) == 0 && UserDisplayState == 1 )
      {
        v17 |= 0x80u;
        v58 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v9 + 96LL))(v9, &v95);
        v59 = *(_QWORD *)v58;
        v60 = *(void (__fastcall **)(__int64, __int128 *, _QWORD))(**(_QWORD **)v58 + 112LL);
        v97 = 0;
        v98 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v97, L"Defer reason: presenting");
        v60(v59, &v97, v57);
        std::wstring::_Tidy_deallocate(&v97);
        v61 = (volatile signed __int32 *)*((_QWORD *)&v95 + 1);
        if ( *((_QWORD *)&v95 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v95 + 1) + 8LL), 0xFFFFFFFF) == v57 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v61)(v61);
            if ( _InterlockedExchangeAdd(v61 + 3, 0xFFFFFFFF) == v57 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v61 + 8LL))(v61);
          }
        }
      }
      if ( (a3 & 0x100) == 0 && v57 - 2 <= 1 )
      {
        v17 |= 0x100u;
        v62 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v9 + 96LL))(v9, &v95);
        v63 = *(_QWORD *)v62;
        v64 = *(void (__fastcall **)(__int64, __int128 *, __int64))(**(_QWORD **)v62 + 112LL);
        v97 = 0;
        v98 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v97, L"Defer reason: full-screen");
        v64(v63, &v97, 1);
        std::wstring::_Tidy_deallocate(&v97);
        v65 = (volatile signed __int32 *)*((_QWORD *)&v95 + 1);
        if ( *((_QWORD *)&v95 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v95 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v65)(v65);
            if ( _InterlockedExchangeAdd(v65 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v65 + 8LL))(v65);
          }
        }
      }
    }
    if ( (a3 & 8) == 0 )
    {
      if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a1 + 64LL))(a1) )
      {
        v17 |= 8u;
        v66 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v9 + 96LL))(v9, &v95);
        v67 = *(_QWORD *)v66;
        v68 = *(void (__fastcall **)(__int64, __int128 *, __int64))(**(_QWORD **)v66 + 112LL);
        v97 = 0;
        v98 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v97, L"Defer reason: phone call");
        v68(v67, &v97, 1);
        std::wstring::_Tidy_deallocate(&v97);
        v69 = (volatile signed __int32 *)*((_QWORD *)&v95 + 1);
        if ( *((_QWORD *)&v95 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v95 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v69)(v69);
            if ( _InterlockedExchangeAdd(v69 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v69 + 8LL))(v69);
          }
        }
      }
    }
    if ( (a3 & 0x200) == 0 )
    {
      if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a1 + 56LL))(a1) )
      {
        v17 |= 0x200u;
        v70 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v9 + 96LL))(v9, &v95);
        v71 = *(_QWORD *)v70;
        v72 = *(void (__fastcall **)(__int64, __int128 *, __int64))(**(_QWORD **)v70 + 112LL);
        v97 = 0;
        v98 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v97, L"Defer reason: block requested");
        v72(v71, &v97, 1);
        std::wstring::_Tidy_deallocate(&v97);
        v73 = (volatile signed __int32 *)*((_QWORD *)&v95 + 1);
        if ( *((_QWORD *)&v95 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v95 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v73)(v73);
            if ( _InterlockedExchangeAdd(v73 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v73 + 8LL))(v73);
          }
        }
      }
    }
    if ( (a3 & 0x400) == 0 )
    {
      LODWORD(v89) = 0;
      v74 = wil::wnf_query_nothrow<unsigned long>(&WNF_RM_GAME_MODE_ACTIVE, v90, &v89);
      if ( v74 >= 0 )
      {
        if ( (_DWORD)v89 )
        {
          v17 |= 0x400u;
          v75 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v9 + 96LL))(v9, &v95);
          v76 = *(_QWORD *)v75;
          v77 = *(void (__fastcall **)(__int64, __int128 *, __int64))(**(_QWORD **)v75 + 112LL);
          v97 = 0;
          v98 = 0;
          std::wstring::_Construct<1,unsigned short const *>(&v97, L"Defer reason: game active");
          v77(v76, &v97, 1);
          std::wstring::_Tidy_deallocate(&v97);
          v78 = (volatile signed __int32 *)*((_QWORD *)&v95 + 1);
          if ( *((_QWORD *)&v95 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v95 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v78)(v78);
              if ( _InterlockedExchangeAdd(v78 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v78 + 8LL))(v78);
            }
          }
          v79 = (char *)OpenProcess(0x400u, 0, (DWORD)v89);
          v87 = v79;
          memset_0(ExeName, 0, 0x208u);
          LODWORD(bstrString) = 260;
          if ( (unsigned __int64)(v79 - 1) <= 0xFFFFFFFFFFFFFFFDuLL
            && QueryFullProcessImageNameW(v79, 0, ExeName, (PDWORD)&bstrString) )
          {
            FileNameW = PathFindFileNameW(ExeName);
            v82 = -1;
            do
              ++v82;
            while ( FileNameW[v82] );
            if ( v82 > v111 )
            {
              std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
                v109,
                v82,
                v81,
                FileNameW);
            }
            else
            {
              v83 = v109;
              if ( v111 > 7 )
                v83 = (void **)v109[0];
              v110 = v82;
              v84 = 2 * v82;
              memmove_0(v83, FileNameW, 2 * v82);
              *(_WORD *)((char *)v83 + v84) = 0;
            }
          }
          if ( (unsigned __int64)(v79 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
            CloseHandle(v79);
        }
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1CA,
          (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\usage.cpp",
          (const char *)(unsigned int)v74,
          (int)bstrString);
      }
    }
    LODWORD(v99) = v17;
    v6 = v92;
    SystemInterface::DeferReasons::DeferReasons(v92, &v99);
    v16 = v94;
    if ( v94 && _InterlockedExchangeAdd(v94 + 2, 0xFFFFFFFF) == 1 )
      goto LABEL_144;
  }
  std::wstring::_Tidy_deallocate(v109);
  std::wstring::_Tidy_deallocate(&v106);
  std::wstring::_Tidy_deallocate(v103);
  std::wstring::_Tidy_deallocate(v100);
  return v6;
}

```

## disassembly

```asm
0x180055c40  mov     [rsp-8+arg_18], rbx
0x180055c45  push    rbp
0x180055c46  push    rsi
0x180055c47  push    rdi
0x180055c48  push    r12
0x180055c4a  push    r13
0x180055c4c  push    r14
0x180055c4e  push    r15
0x180055c50  lea     rbp, [rsp-250h]
0x180055c58  sub     rsp, 350h
0x180055c5f  mov     rax, cs:__security_cookie
0x180055c66  xor     rax, rsp
0x180055c69  mov     [rbp+280h+var_40], rax
0x180055c70  mov     esi, r8d
0x180055c73  mov     rdi, rdx
0x180055c76  mov     [rsp+380h+var_338], rdx
0x180055c7b  mov     r13, rcx
0x180055c7e  mov     [rsp+380h+var_358], rdx
0x180055c83  xor     ecx, ecx
0x180055c85  mov     r15d, ecx
0x180055c88  mov     [rsp+380h+var_33C], ecx
0x180055c8c  xor     eax, eax
0x180055c8e  mov     [rbp+280h+var_2E0], rax
0x180055c92  xorps   xmm0, xmm0
0x180055c95  movups  xmmword ptr [rbp+280h+var_2D8], xmm0
0x180055c99  mov     [rbp+280h+var_2C8], rcx
0x180055c9d  lea     edx, [rcx+7]
0x180055ca0  mov     [rbp+280h+var_2C0], rdx
0x180055ca4  mov     word ptr [rbp+280h+var_2D8], cx
0x180055ca8  movups  xmmword ptr [rbp+280h+var_2B8], xmm0
0x180055cac  mov     [rbp+280h+var_2A8], rcx
0x180055cb0  mov     [rbp+280h+var_2A0], rdx
0x180055cb4  mov     word ptr [rbp+280h+var_2B8], cx
0x180055cb8  movups  [rbp+280h+var_298], xmm0
0x180055cbc  mov     [rbp+280h+var_288], rcx
0x180055cc0  mov     [rbp+280h+var_280], rdx
0x180055cc4  mov     word ptr [rbp+280h+var_298], cx
0x180055cc8  movups  xmmword ptr [rbp+280h+var_278], xmm0
0x180055ccc  mov     [rbp+280h+var_268], rcx
0x180055cd0  mov     [rbp+280h+var_260], rdx
0x180055cd4  mov     word ptr [rbp+280h+var_278], cx
0x180055cd8  lea     rcx, [rsp+380h+var_330]
0x180055cdd  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x180055ce2  nop
0x180055ce3  mov     r12, [rsp+380h+var_330]
0x180055ce8  mov     rax, [r12]
0x180055cec  lea     rdx, [rsp+380h+var_358]
0x180055cf1  mov     rcx, r12
0x180055cf4  mov     rax, [rax+30h]
0x180055cf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055cfd  nop
0x180055cfe  mov     rcx, [rax]
0x180055d01  mov     rax, [rcx]
0x180055d04  lea     rdx, [rsp+380h+bstrString]
0x180055d09  mov     rax, [rax+48h]
0x180055d0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055d12  nop
0x180055d13  or      r14, 0FFFFFFFFFFFFFFFFh
0x180055d17  mov     rbx, [rsp+380h+var_350]
0x180055d1c  test    rbx, rbx
0x180055d1f  jz      short loc_180055D58
0x180055d21  mov     eax, r14d
0x180055d24  lock xadd [rbx+8], eax
0x180055d29  add     eax, r14d
0x180055d2c  jnz     short loc_180055D58
0x180055d2e  mov     rax, [rbx]
0x180055d31  mov     rcx, rbx
0x180055d34  mov     rax, [rax]
0x180055d37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055d3c  mov     eax, r14d
0x180055d3f  lock xadd [rbx+0Ch], eax
0x180055d44  add     eax, r14d
0x180055d47  jnz     short loc_180055D58
0x180055d49  mov     rax, [rbx]
0x180055d4c  mov     rcx, rbx
0x180055d4f  mov     rax, [rax+8]
0x180055d53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055d58  cmp     byte ptr [rsp+380h+bstrString+4], 0
0x180055d5d  jz      loc_180055ED6
0x180055d63  mov     r15d, 400h
0x180055d69  test    dword ptr [rsp+380h+bstrString], r15d
0x180055d6e  jz      short loc_180055DC0
0x180055d70  mov     r8d, 1Bh
0x180055d76  cmp     [rbp+280h+var_260], r8
0x180055d7a  jb      short loc_180055DAD
0x180055d7c  lea     rbx, [rbp+280h+var_278]
0x180055d80  cmp     [rbp+280h+var_260], 7
0x180055d85  cmova   rbx, [rbp+280h+var_278]
0x180055d8a  mov     [rbp+280h+var_268], r8
0x180055d8e  mov     r8d, 36h ; '6'; Size
0x180055d94  lea     rdx, aTestoverrideGa; "TestOverride_gameModeReason"
0x180055d9b  mov     rcx, rbx; void *
0x180055d9e  call    memmove_0
0x180055da3  xor     r15d, r15d
0x180055da6  mov     [rbx+36h], r15w
0x180055dab  jmp     short loc_180055DC3
0x180055dad  lea     r9, aTestoverrideGa; "TestOverride_gameModeReason"
0x180055db4  mov     rdx, r8
0x180055db7  lea     rcx, [rbp+280h+var_278]
0x180055dbb  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180055dc0  xor     r15d, r15d
0x180055dc3  cmp     byte ptr [rsp+380h+bstrString+4], r15b
0x180055dc8  jz      loc_180056C78
0x180055dce  test    byte ptr [rsp+380h+bstrString], 2
0x180055dd3  jz      short loc_180055E1C
0x180055dd5  mov     edx, 1Ah
0x180055dda  cmp     [rbp+280h+var_2A0], rdx
0x180055dde  jb      short loc_180055E0C
0x180055de0  lea     rbx, [rbp+280h+var_2B8]
0x180055de4  cmp     [rbp+280h+var_2A0], 7
0x180055de9  cmova   rbx, [rbp+280h+var_2B8]
0x180055dee  mov     [rbp+280h+var_2A8], rdx
0x180055df2  lea     r8d, [rdx+1Ah]; Size
0x180055df6  lea     rdx, aTestoverrideDi; "TestOverride_displayReason"
0x180055dfd  mov     rcx, rbx; void *
0x180055e00  call    memmove_0
0x180055e05  mov     [rbx+34h], r15w
0x180055e0a  jmp     short loc_180055E1C
0x180055e0c  lea     r9, aTestoverrideDi; "TestOverride_displayReason"
0x180055e13  lea     rcx, [rbp+280h+var_2B8]
0x180055e17  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180055e1c  cmp     byte ptr [rsp+380h+bstrString+4], r15b
0x180055e21  jz      loc_180056C78
0x180055e27  test    byte ptr [rsp+380h+bstrString], 10h
0x180055e2c  jz      short loc_180055E78
0x180055e2e  mov     eax, 19h
0x180055e33  cmp     [rbp+280h+var_2C0], rax
0x180055e37  jb      short loc_180055E65
0x180055e39  lea     rbx, [rbp+280h+var_2D8]
0x180055e3d  cmp     [rbp+280h+var_2C0], 7
0x180055e42  cmova   rbx, [rbp+280h+var_2D8]
0x180055e47  mov     [rbp+280h+var_2C8], rax
0x180055e4b  lea     r8d, [rax+19h]; Size
0x180055e4f  lea     rdx, aTestoverrideSy; "TestOverride_systemReason"
0x180055e56  mov     rcx, rbx; void *
0x180055e59  call    memmove_0
0x180055e5e  mov     [rbx+32h], r15w
0x180055e63  jmp     short loc_180055E78
0x180055e65  lea     r9, aTestoverrideSy; "TestOverride_systemReason"
0x180055e6c  mov     rdx, rax
0x180055e6f  lea     rcx, [rbp+280h+var_2D8]
0x180055e73  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180055e78  cmp     byte ptr [rsp+380h+bstrString+4], r15b
0x180055e7d  jz      loc_180056C78
0x180055e83  not     esi
0x180055e85  and     esi, dword ptr [rsp+380h+bstrString]
0x180055e89  mov     dword ptr [rbp+280h+var_2E0], esi
0x180055e8c  lea     rdx, [rbp+280h+var_2E0]
0x180055e90  mov     rcx, rdi
0x180055e93  call    ??0DeferReasons@SystemInterface@@QEAA@$$QEAU01@@Z; SystemInterface::DeferReasons::DeferReasons(SystemInterface::DeferReasons &&)
0x180055e98  nop
0x180055e99  mov     rbx, [rsp+380h+var_328]
0x180055e9e  test    rbx, rbx
0x180055ea1  jz      loc_180056C12
0x180055ea7  mov     eax, r14d
0x180055eaa  lock xadd [rbx+8], eax
0x180055eaf  add     eax, r14d
0x180055eb2  jnz     loc_180056C12
0x180055eb8  mov     rax, [rbx]
0x180055ebb  mov     rcx, rbx
0x180055ebe  mov     rax, [rax]
0x180055ec1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055ec6  mov     eax, r14d
0x180055ec9  lock xadd [rbx+0Ch], eax
0x180055ece  add     eax, r14d
0x180055ed1  jmp     loc_180056C00
0x180055ed6  xor     r14d, r14d
0x180055ed9  test    sil, 4
0x180055edd  jnz     short loc_180055F1A
0x180055edf  mov     rax, [r12]
0x180055ee3  lea     rdx, [rsp+380h+var_358]
0x180055ee8  mov     rcx, r12
0x180055eeb  mov     rax, [rax+38h]
0x180055eef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055ef4  nop
0x180055ef5  lea     r15d, [r14+2]
0x180055ef9  mov     [rsp+380h+var_33C], r15d
0x180055efe  mov     rcx, [rax]
0x180055f01  mov     rax, [rcx]
0x180055f04  mov     rax, [rax+10h]
0x180055f08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055f0d  cmp     al, [rbp+280h+arg_20]
0x180055f13  jnb     short loc_180055F1A
0x180055f15  mov     dil, 1
0x180055f18  jmp     short loc_180055F1D
0x180055f1a  xor     dil, dil
0x180055f1d  test    r15b, 2
0x180055f21  jz      short loc_180055F68
0x180055f23  and     r15d, 0FFFFFFFDh
0x180055f27  mov     rbx, [rsp+380h+var_350]
0x180055f2c  test    rbx, rbx
0x180055f2f  jz      short loc_180055F68
0x180055f31  or      eax, 0FFFFFFFFh
0x180055f34  lock xadd [rbx+8], eax
0x180055f39  cmp     eax, 1
0x180055f3c  jnz     short loc_180055F68
0x180055f3e  mov     rax, [rbx]
0x180055f41  mov     rcx, rbx
0x180055f44  mov     rax, [rax]
0x180055f47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055f4c  or      eax, 0FFFFFFFFh
0x180055f4f  lock xadd [rbx+0Ch], eax
0x180055f54  cmp     eax, 1
0x180055f57  jnz     short loc_180055F68
0x180055f59  mov     rax, [rbx]
0x180055f5c  mov     rcx, rbx
0x180055f5f  mov     rax, [rax+8]
0x180055f63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055f68  test    dil, dil
0x180055f6b  jz      loc_180056023
0x180055f71  mov     r14d, 4
0x180055f77  mov     rax, [r12]
0x180055f7b  lea     rdx, [rsp+380h+var_358]
0x180055f80  mov     rcx, r12
0x180055f83  mov     rax, [rax+60h]
0x180055f87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055f8c  nop
0x180055f8d  mov     rdi, [rax]
0x180055f90  mov     rax, [rdi]
0x180055f93  mov     rbx, [rax+70h]
0x180055f97  xorps   xmm0, xmm0
0x180055f9a  movups  [rsp+380h+var_320], xmm0
0x180055f9f  xorps   xmm1, xmm1
0x180055fa2  movdqu  [rsp+380h+var_310], xmm1
0x180055fa8  lea     r8d, [r14+15h]
0x180055fac  lea     rdx, aDeferReasonLow; "Defer reason: low battery"
0x180055fb3  lea     rcx, [rsp+380h+var_320]
0x180055fb8  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180055fbd  nop
0x180055fbe  lea     r8d, [r14-3]
0x180055fc2  lea     rdx, [rsp+380h+var_320]
0x180055fc7  mov     rcx, rdi
0x180055fca  mov     rax, rbx
0x180055fcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055fd2  nop
0x180055fd3  lea     rcx, [rsp+380h+var_320]
0x180055fd8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180055fdd  nop
0x180055fde  mov     rbx, [rsp+380h+var_350]
0x180055fe3  xor     edi, edi
0x180055fe5  test    rbx, rbx
0x180055fe8  jz      short loc_180056025
0x180055fea  or      eax, 0FFFFFFFFh
0x180055fed  lock xadd [rbx+8], eax
0x180055ff2  cmp     eax, 1
0x180055ff5  jnz     short loc_180056025
0x180055ff7  mov     rax, [rbx]
0x180055ffa  mov     rcx, rbx
0x180055ffd  mov     rax, [rax]
0x180056000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056005  or      eax, 0FFFFFFFFh
0x180056008  lock xadd [rbx+0Ch], eax
0x18005600d  cmp     eax, 1
0x180056010  jnz     short loc_180056025
0x180056012  mov     rax, [rbx]
0x180056015  mov     rcx, rbx
0x180056018  mov     rax, [rax+8]
0x18005601c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056021  jmp     short loc_180056025
0x180056023  xor     edi, edi
0x180056025  test    sil, 40h
0x180056029  jnz     short loc_180056060
0x18005602b  mov     rax, [r12]
0x18005602f  lea     rdx, [rsp+380h+var_358]
0x180056034  mov     rcx, r12
0x180056037  mov     rax, [rax+38h]
0x18005603b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056040  nop
0x180056041  or      r15d, 4
0x180056045  mov     [rsp+380h+var_33C], r15d
0x18005604a  mov     rcx, [rax]
0x18005604d  mov     rax, [rcx]
0x180056050  mov     rax, [rax+28h]
0x180056054  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056059  test    al, al
0x18005605b  jnz     short loc_180056060
0x18005605d  mov     dil, 1
0x180056060  test    r15b, 4
0x180056064  jz      short loc_1800560AD
0x180056066  mov     rbx, [rsp+380h+var_350]
0x18005606b  or      r15, 0FFFFFFFFFFFFFFFFh
0x18005606f  test    rbx, rbx
0x180056072  jz      short loc_1800560B1
0x180056074  mov     eax, r15d
0x180056077  lock xadd [rbx+8], eax
0x18005607c  add     eax, r15d
0x18005607f  jnz     short loc_1800560B1
0x180056081  mov     rax, [rbx]
0x180056084  mov     rcx, rbx
0x180056087  mov     rax, [rax]
0x18005608a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005608f  mov     eax, r15d
0x180056092  lock xadd [rbx+0Ch], eax
0x180056097  add     eax, r15d
0x18005609a  jnz     short loc_1800560B1
0x18005609c  mov     rax, [rbx]
0x18005609f  mov     rcx, rbx
0x1800560a2  mov     rax, [rax+8]
0x1800560a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800560ab  jmp     short loc_1800560B1
  ... truncated ...
```
