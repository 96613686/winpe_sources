# CommandParamReceiver::operator()(CreateParams const &)

- ea: `0x140008784`
- end: `0x14000942b`
- name: `??RCommandParamReceiver@@QEAAXAEBVCreateParams@@@Z`
- size: `3239`
- prototype: `__int64 __fastcall(Output **, __int64 *)`
- caller_count: `1`
- callee_count: `26`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x14000ded8`

## callees

- `0x1400016a0`
- `0x140001934`
- `0x140001990`
- `0x140006064`
- `0x14000641c`
- `0x1400066fc`
- `0x140006d94`
- `0x140007210`
- `0x1400076b4`
- `0x140007778`
- `0x140007dc0`
- `0x140008150`
- `0x140008454`
- `0x140008530`
- `0x140008784`
- `0x1400098b0`
- `0x140009dd8`
- `0x140009e94`
- `0x140009f58`
- `0x140009fa4`
- `0x14000a388`
- `0x14000a75c`
- `0x14000b16c`
- `0x14000b5b4`
- `0x14000cf20`
- `0x140013010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x140008e45`
- `KERNEL32!SetLastError` at `0x140009002`
- `KERNEL32!SetLastError` at `0x140009178`
- `KERNEL32!SetLastError` at `0x140008e45`
- `KERNEL32!SetLastError` at `0x140009002`
- `KERNEL32!SetLastError` at `0x140009178`
- `KERNEL32!GetLastError` at `0x140008e32`
- `KERNEL32!GetLastError` at `0x140008fef`
- `KERNEL32!GetLastError` at `0x140009165`
- `KERNEL32!GetLastError` at `0x140008e32`
- `KERNEL32!GetLastError` at `0x140008fef`
- `KERNEL32!GetLastError` at `0x140009165`
- `KERNEL32!GetModuleHandleW` at `0x140009271`
- `KERNEL32!GetModuleHandleW` at `0x140009271`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x140009317`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x140009317`
- `msvcp_win!?wcout@std@@3V?$basic_ostream@GU?$char_traits@G@std@@@1@A` at `0x1400092d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140008e3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140008ffa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140009170`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400093f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140008e3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140008ffa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140009170`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400093f1`

## pseudocode

```c
__int64 __fastcall CommandParamReceiver::operator()(Output **a1, __int64 *a2)
{
  __int64 *v2; // rdi
  __int64 v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // rcx
  _QWORD *v7; // rsi
  char v8; // cl
  _QWORD *v9; // rdx
  char *v10; // rbx
  __int64 v11; // rbx
  __int64 v12; // rsi
  __int64 v13; // r14
  __int64 Kcv; // rbx
  __int64 v15; // r13
  unsigned int v16; // edx
  _QWORD *v17; // rsi
  char v18; // cl
  _QWORD *v19; // rdx
  char *v20; // rbx
  __int64 *v21; // rbx
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rax
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rsi
  __int64 v28; // r14
  _QWORD *v29; // rsi
  char v30; // cl
  _QWORD *v31; // rdx
  char *v32; // rbx
  __int64 v33; // rbx
  __int64 v34; // rcx
  void *v35; // r12
  Output *v36; // rcx
  const struct _GUID *v37; // r8
  __int64 v38; // r8
  int v39; // ebx
  __int64 (__fastcall **v40)(void *, GUID *, __int64 *); // rax
  Output *v41; // rcx
  void *v42; // r15
  DWORD LastError; // ebx
  unsigned int v44; // edx
  __int64 v45; // r8
  int v46; // r15d
  __int64 v47; // r13
  int v48; // esi
  __int64 v49; // rax
  __int64 v50; // r10
  int v51; // r9d
  int v52; // ecx
  __int64 v53; // rax
  __int64 (__fastcall **v54)(void *, GUID *, __int64 *); // rax
  unsigned int v55; // edx
  Output *v56; // rcx
  void *v57; // r15
  DWORD v58; // ebx
  char v59; // al
  int v60; // r15d
  unsigned __int64 v61; // rcx
  int v62; // esi
  __int64 v63; // r13
  __int64 v64; // r9
  __int64 v65; // r8
  unsigned int v66; // eax
  __int64 v67; // rax
  void *v68; // r15
  DWORD v69; // ebx
  unsigned int v70; // ecx
  int v71; // esi
  __int64 v72; // r15
  __int64 v73; // rdx
  int v74; // r13d
  __int64 v75; // rax
  HMODULE ModuleHandleW; // rax
  _QWORD *v77; // rdx
  __int64 v78; // rax
  unsigned __int64 v79; // rdx
  Output *v80; // rcx
  int v81; // edx
  int v83; // [rsp+30h] [rbp-E0h]
  int v84; // [rsp+68h] [rbp-A8h]
  int v85; // [rsp+90h] [rbp-80h] BYREF
  int v86; // [rsp+94h] [rbp-7Ch]
  int v87; // [rsp+98h] [rbp-78h] BYREF
  unsigned int v88; // [rsp+9Ch] [rbp-74h] BYREF
  const wchar_t *v89; // [rsp+A0h] [rbp-70h] BYREF
  const wchar_t *v90; // [rsp+A8h] [rbp-68h] BYREF
  wchar_t *v91; // [rsp+B0h] [rbp-60h]
  LPVOID pv; // [rsp+B8h] [rbp-58h] BYREF
  __int64 v93; // [rsp+C0h] [rbp-50h]
  __int64 v94; // [rsp+C8h] [rbp-48h] BYREF
  int v95; // [rsp+D0h] [rbp-40h] BYREF
  unsigned int v96; // [rsp+D4h] [rbp-3Ch]
  unsigned int v97[2]; // [rsp+D8h] [rbp-38h]
  __int128 v98; // [rsp+E0h] [rbp-30h] BYREF
  __int64 v99; // [rsp+F0h] [rbp-20h]
  __int128 v100; // [rsp+100h] [rbp-10h] BYREF
  __int64 (__fastcall ***v101)(void *, GUID *, __int64 *); // [rsp+110h] [rbp+0h] BYREF
  __int128 v102; // [rsp+118h] [rbp+8h] BYREF
  __int64 v103; // [rsp+128h] [rbp+18h]
  __int64 (__fastcall *v104)(_QWORD, __int64 *, __int64, _QWORD, unsigned int, __int64, int, __int64, int, __int64, int, unsigned __int64, int, unsigned int, void *, LPVOID *, int *); // [rsp+130h] [rbp+20h]
  __int128 v105; // [rsp+138h] [rbp+28h] BYREF
  __int64 v106; // [rsp+148h] [rbp+38h]
  void *v107; // [rsp+150h] [rbp+40h]
  Output **v108; // [rsp+158h] [rbp+48h]
  void *v109; // [rsp+160h] [rbp+50h] BYREF
  int v110; // [rsp+168h] [rbp+58h]
  __int64 v111; // [rsp+170h] [rbp+60h] BYREF
  __int64 v112; // [rsp+178h] [rbp+68h]
  __int64 v113; // [rsp+180h] [rbp+70h]
  char v114; // [rsp+188h] [rbp+78h]
  __int64 *v115; // [rsp+190h] [rbp+80h]
  unsigned __int64 v116; // [rsp+198h] [rbp+88h] BYREF
  int v117; // [rsp+1A0h] [rbp+90h]
  char v118; // [rsp+1B0h] [rbp+A0h]
  void **v119; // [rsp+1B8h] [rbp+A8h]
  _BYTE v120[40]; // [rsp+1C0h] [rbp+B0h] BYREF
  _QWORD v121[9]; // [rsp+1E8h] [rbp+D8h] BYREF

  v2 = a2;
  v108 = a1;
  v85 = 0;
  v86 = 1;
  pv = 0;
  v98 = 0;
  v99 = 0;
  v105 = 0;
  v106 = 0;
  v114 = 0;
  v115 = &v111;
  v102 = 0;
  v103 = 0;
  v118 = 0;
  v119 = (void **)&v116;
  if ( !*((_BYTE *)a2 + 32) )
  {
    v87 = -2147024809;
    errorlib::scoped_error<hresult_error::tag>::receive<long>(&v85, &v87);
    v89 = L"/name";
    v90 = L"parameterName";
    v91 = L"";
    v86 = 3;
    if ( v85 >= 0 )
      goto LABEL_11;
    v5 = 421;
    goto LABEL_10;
  }
  if ( (unsigned __int64)a2[2] > 0x100 )
    goto LABEL_143;
  if ( !*((_BYTE *)a2 + 32) )
    TpmVscMgrMeta::FailFast((TpmVscMgrMeta *)0x80004004LL, (unsigned int)a2);
  if ( !v2[2] )
  {
LABEL_143:
    v87 = -2147024809;
    errorlib::scoped_error<hresult_error::tag>::receive<long>(&v85, &v87);
    v89 = L"/name";
    v90 = L"parameterName";
    v91 = L"";
    v86 = 3;
    if ( v85 < 0 )
    {
      v5 = 422;
LABEL_10:
      Output::DisplayErrorResource<unsigned short const *>(v4, v5, &v89);
      errorlib::scoped_error<hresult_error::tag>::throwfailed(&v85);
    }
  }
LABEL_11:
  if ( *((_BYTE *)v2 + 80) )
  {
    v7 = v2 + 6;
    v8 = *((_BYTE *)v2 + 80);
    if ( !v8 )
    {
      TpmVscMgrMeta::FailFast((TpmVscMgrMeta *)0x80004004LL, (unsigned int)a2);
      v8 = *((_BYTE *)v2 + 80);
    }
    if ( (unsigned __int64)v2[9] <= 7 )
      v9 = v2 + 6;
    else
      v9 = (_QWORD *)*v7;
    v10 = (char *)v9 + 2 * v2[8];
    if ( !v8 )
      TpmVscMgrMeta::FailFast((TpmVscMgrMeta *)0x80004004LL, (unsigned int)v9);
    if ( (unsigned __int64)v2[9] > 7 )
      v7 = (_QWORD *)*v7;
    v11 = ByteifyString<std::vector<unsigned char,wil::secure_allocator<unsigned char>>,std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>(
            &v89,
            v7,
            v10);
    if ( &v98 == (__int128 *)v11 )
    {
      v13 = *((_QWORD *)&v98 + 1);
      v12 = v98;
    }
    else
    {
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v98);
      v12 = *(_QWORD *)v11;
      *(_QWORD *)&v98 = *(_QWORD *)v11;
      v13 = *(_QWORD *)(v11 + 8);
      *((_QWORD *)&v98 + 1) = v13;
      v99 = *(_QWORD *)(v11 + 16);
      *(_QWORD *)v11 = 0;
      *(_QWORD *)(v11 + 8) = 0;
      *(_QWORD *)(v11 + 16) = 0;
    }
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v89);
    if ( v12 == v13 )
    {
      v87 = -2147024809;
      errorlib::scoped_error<hresult_error::tag>::receive<long>(&v85, &v87);
      v89 = L"/adminkey";
      v90 = L"parameterName";
      v91 = L"";
      v86 = 3;
      if ( v85 < 0 )
      {
        Output::DisplayErrorResource<unsigned short const *>(v6, 422, &v89);
        errorlib::scoped_error<hresult_error::tag>::throwfailed(&v85);
      }
    }
  }
  else
  {
    v87 = -2147024809;
    errorlib::scoped_error<hresult_error::tag>::receive<long>(&v85, &v87);
    v89 = L"/adminkey";
    v90 = L"parameterName";
    v91 = L"";
    v86 = 3;
    if ( v85 < 0 )
    {
      Output::DisplayErrorResource<unsigned short const *>(v6, 421, &v89);
      errorlib::scoped_error<hresult_error::tag>::throwfailed(&v85);
    }
  }
  Kcv = CommandParamReceiver::GetKcv(v6, &v89, &v98);
  if ( &v105 == (__int128 *)Kcv )
  {
    v15 = *((_QWORD *)&v105 + 1);
    *(_QWORD *)v97 = v105;
  }
  else
  {
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v105);
    *(_QWORD *)v97 = *(_QWORD *)Kcv;
    *(_QWORD *)&v105 = *(_QWORD *)v97;
    v15 = *(_QWORD *)(Kcv + 8);
    *((_QWORD *)&v105 + 1) = v15;
    v106 = *(_QWORD *)(Kcv + 16);
    *(_QWORD *)Kcv = 0;
    *(_QWORD *)(Kcv + 8) = 0;
    *(_QWORD *)(Kcv + 16) = 0;
  }
  v93 = v15;
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v89);
  if ( *((_BYTE *)v2 + 176) )
  {
    v17 = v2 + 18;
    v18 = *((_BYTE *)v2 + 176);
    if ( !v18 )
    {
      TpmVscMgrMeta::FailFast((TpmVscMgrMeta *)0x80004004LL, v16);
      v18 = *((_BYTE *)v2 + 176);
    }
    if ( (unsigned __int64)v2[21] <= 7 )
      v19 = v2 + 18;
    else
      v19 = (_QWORD *)*v17;
    v20 = (char *)v19 + 2 * v2[20];
    if ( !v18 )
      TpmVscMgrMeta::FailFast((TpmVscMgrMeta *)0x80004004LL, (unsigned int)v19);
    if ( (unsigned __int64)v2[21] > 7 )
      v17 = (_QWORD *)*v17;
    v21 = (__int64 *)StringToAsciiVector<std::vector<unsigned char,wil::secure_allocator<unsigned char>>,std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>(
                       &v89,
                       v17,
                       v20);
    if ( v114 )
    {
      v114 = 0;
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v111);
    }
    v22 = v21[2];
    v21[2] = 0;
    v23 = v21[1];
    v21[1] = 0;
    v24 = *v21;
    *v21 = 0;
    v111 = v24;
    v112 = v23;
    v113 = v22;
    v114 = 1;
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v89);
    if ( !v114 )
      TpmVscMgrMeta::FailFast((TpmVscMgrMeta *)0x80004004LL, v16);
    if ( v111 == v112 )
    {
      v87 = -2147024809;
      errorlib::scoped_error<hresult_error::tag>::receive<long>(&v85, &v87);
      v89 = L"/puk";
      v90 = L"parameterName";
      v91 = L"";
      v86 = 3;
      if ( v85 < 0 )
      {
        Output::DisplayErrorResource<unsigned short const *>(v25, 422, &v89);
        errorlib::scoped_error<hresult_error::tag>::throwfailed(&v85);
      }
    }
  }
  if ( *((_BYTE *)v2 + 128) )
  {
    v29 = v2 + 12;
    v30 = *((_BYTE *)v2 + 128);
    if ( !v30 )
    {
      TpmVscMgrMeta::FailFast((TpmVscMgrMeta *)0x80004004LL, v16);
      v30 = *((_BYTE *)v2 + 128);
    }
    if ( (unsigned __int64)v2[15] <= 7 )
      v31 = v2 + 12;
    else
      v31 = (_QWORD *)*v29;
    v32 = (char *)v31 + 2 * v2[14];
    if ( !v30 )
      TpmVscMgrMeta::FailFast((TpmVscMgrMeta *)0x80004004LL, (unsigned int)v31);
    if ( (unsigned __int64)v2[15] > 7 )
      v29 = (_QWORD *)*v29;
    v33 = StringToAsciiVector<std::vector<unsigned char,wil::secure_allocator<unsigned char>>,std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>(
            &v89,
            v29,
            v32);
    if ( &v102 == (__int128 *)v33 )
    {
      v27 = *((_QWORD *)&v102 + 1);
      v28 = v102;
    }
    else
    {
      std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v102);
      v28 = *(_QWORD *)v33;
      *(_QWORD *)&v102 = *(_QWORD *)v33;
      v27 = *(_QWORD *)(v33 + 8);
      *((_QWORD *)&v102 + 1) = v27;
      v103 = *(_QWORD *)(v33 + 16);
      *(_QWORD *)v33 = 0;
      *(_QWORD *)(v33 + 8) = 0;
      *(_QWORD *)(v33 + 16) = 0;
    }
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v89);
    if ( v28 == v27 )
    {
      v87 = -2147024809;
      errorlib::scoped_error<hresult_error::tag>::receive<long>(&v85, &v87);
      v89 = L"/pin";
      v90 = L"parameterName";
      v91 = L"";
      v86 = 3;
      if ( v85 < 0 )
      {
        Output::DisplayErrorResource<unsigned short const *>(v34, 422, &v89);
        errorlib::scoped_error<hresult_error::tag>::throwfailed(&v85);
      }
    }
  }
  else
  {
    v87 = -2147024809;
    errorlib::scoped_error<hresult_error::tag>::receive<long>(&v85, &v87);
    v89 = L"/pin";
    v90 = L"parameterName";
    v91 = L"";
    v86 = 3;
    if ( v85 < 0 )
    {
      Output::DisplayErrorResource<unsigned short const *>(v26, 421, &v89);
      errorlib::scoped_error<hresult_error::tag>::throwfailed(&v85);
    }
    LODWORD(v27) = DWORD2(v102);
    v28 = v102;
  }
  if ( *((_BYTE *)v2 + 216) )
  {
    if ( v118 )
    {
      v118 = 0;
      std::vector<unsigned char>::~vector<unsigned char>(&v116);
    }
    std::vector<unsigned char>::vector<unsigned char>(&v116, v2 + 24);
    v118 = 1;
  }
  Output::DisplayStatusResource(*a1, 500);
  v107 = 0;
  v35 = operator new(0x18u);
  v109 = v35;
  v36 = *a1;
  *(_QWORD *)v35 = &StatusCallbackImpl::`vftable';
  *((_DWORD *)v35 + 2) = 1;
  *((_QWORD *)v35 + 2) = v36;
  v107 = v35;
  CommandParamReceiver::CreateInstance((HWND)a1, (struct _GUID *)&v101, v37);
  v39 = 0;
  v95 = 0;
  if ( *((_DWORD *)v2 + 59) )
  {
    v94 = 0;
    v40 = *v101;
    v94 = 0;
    v87 = (*v40)(v101, &GUID_3c745a97_f375_4150_be17_5950f694c699, &v94);
    errorlib::scoped_error<hresult_error::tag>::receive<long>(&v85, &v87);
    v86 = 3;
    if ( v85 < 0 )
    {
      if ( v85 == -2147467262 )
        Output::DisplayErrorResource(v41, 520);
      errorlib::scoped_error<hresult_error::tag>::throwfailed(&v85);
    }
    *(_QWORD *)&v100 = v94;
    v109 = *(void **)(*(_QWORD *)v94 + 48LL);
    v42 = pv;
    if ( pv )
    {
      LastError = GetLastError();
      CoTaskMemFree(v42);
      SetLastError(LastError);
      v39 = 0;
    }
    pv = 0;
    v44 = *((unsigned __int8 *)v2 + 232);
    v96 = v44;
    v45 = *((unsigned int *)v2 + 59);
    v88 = *((_DWORD *)v2 + 59);
    if ( v118 )
      v46 = v117 - v116;
    else
      v46 = 0;
    v47 = v116 & -(__int64)(v118 != 0);
    v48 = v27 - v28;
    if ( v114 )
      v39 = v112 - v111;
    v49 = v111 & -(__int64)(v114 != 0);
    v104 = (__int64 (__fastcall *)(_QWORD, __int64 *, __int64, _QWORD, unsigned int, __int64, int, __int64, int, __int64, int, unsigned __int64, int, unsigned int, void *, LPVOID *, int *))v49;
    v50 = *(_QWORD *)v97;
    v51 = v93 - v97[0];
    v93 = (unsigned int)(v93 - v97[0]);
    v52 = DWORD2(v98) - v98;
    v87 = DWORD2(v98) - v98;
    if ( !*((_BYTE *)v2 + 32) )
    {
      TpmVscMgrMeta::FailFast((TpmVscMgrMeta *)0x80004004LL, v44);
      v49 = (__int64)v104;
      v52 = v87;
      v44 = v96;
      v45 = v88;
      v51 = v93;
      v50 = *(_QWORD *)v97;
    }
    if ( (unsigned __int64)v2[3] > 7 )
      v2 = (__int64 *)*v2;
    v84 = v45;
    LOBYTE(v45) = -126;
    v88 = ((__int64 (__fastcall *)(_QWORD, __int64 *, __int64, _QWORD, int, __int64, int, __int64, int, __int64, int, __int64, int, int, unsigned int, void *, LPVOID *))v109)(
            v100,
            v2,
            v45,
            v98,
            v52,
            v50,
            v51,
            v49,
            v39,
            v28,
            v48,
            v47,
            v46,
            v84,
            v44,
            v35,
            &pv);
    v53 = errorlib::scoped_error<hresult_error::tag>::receive<long>(&v85, &v88);
    errorlib::scoped_error<hresult_error::tag>::throwfailed(v53);
LABEL_107:
    if ( v94 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
    goto LABEL_119;
  }
  if ( v118 )
  {
    v94 = 0;
    v54 = *v101;
    v94 = 0;
    v88 = (*v54)(v101, &GUID_fdf8a2b9_02de_47f4_bc26_aa85ab5e5267, &v94);
    errorlib::scoped_error<hresult_error::tag>::receive<long>(&v85, &v88);
    v86 = 3;
    if ( v85 < 0 )
    {
      if ( v85 == -2147467262 )
        Output::DisplayErrorResource(v56, 519);
      errorlib::scoped_error<hresult_error::tag>::throwfailed(&v85);
    }
    *(_QWORD *)&v100 = v94;
    v104 = *(__int64 (__fastcall **)(_QWORD, __int64 *, __int64, _QWORD, unsigned int, __int64, int, __int64, int, __int64, int, unsigned __int64, int, unsigned int, void *, LPVOID *, int *))(*(_QWORD *)v94 + 40LL);
    v57 = pv;
    if ( pv )
    {
      v58 = GetLastError();
      CoTaskMemFree(v57);
      SetLastError(v58);
      v39 = 0;
    }
    pv = 0;
    v96 = *((unsigned __int8 *)v2 + 232);
    v59 = v118;
    if ( !v118 )
    {
      TpmVscMgrMeta::FailFast((TpmVscMgrMeta *)0x80004004LL, v55);
      v59 = v118;
    }
    v60 = v117 - v116;
    if ( !v59 )
      TpmVscMgrMeta::FailFast((TpmVscMgrMeta *)0x80004004LL, v55);
    v61 = v116;
    v109 = (void *)v116;
    v62 = v27 - v28;
    if ( v114 )
      v39 = v112 - v111;
    v63 = v111 & -(__int64)(v114 != 0);
    v64 = *(_QWORD *)v97;
    v65 = (unsigned int)(v93 - v97[0]);
    v93 = v65;
    v66 = DWORD2(v98) - v98;
    v88 = DWORD2(v98) - v98;
    if ( !*((_BYTE *)v2 + 32) )
    {
      TpmVscMgrMeta::FailFast((TpmVscMgrMeta *)0x80004004LL, v55);
      v66 = v88;
      v61 = (unsigned __int64)v109;
      v65 = v93;
      v64 = *(_QWORD *)v97;
    }
    if ( (unsigned __int64)v2[3] > 7 )
      v2 = (__int64 *)*v2;
    v83 = v65;
    LOBYTE(v65) = -126;
    v88 = v104(v100, v2, v65, v98, v66, v64, v83, v63, v39, v28, v62, v61, v60, v96, v35, &pv, &v95);
    v67 = errorlib::scoped_error<hresult_error::tag>::receive<long>(&v85, &v88);
    errorlib::scoped_error<hresult_error::tag>::throwfailed(v67);
    goto LABEL_107;
  }
  v109 = v101;
  *(_QWORD *)&v100 = (*v101)[3];
  v68 = pv;
  if ( pv )
  {
    v69 = GetLastError();
    CoTaskMemFree(v68);
    SetLastError(v69);
    v39 = 0;
  }
  pv = 0;
  v70 = *((unsigned __int8 *)v2 + 232);
  v88 = v70;
  v71 = v27 - v28;
  if ( v114 )
    v39 = v112 - v111;
  v72 = v111 & -(__int64)(v114 != 0);
  v73 = *(_QWORD *)v97;
  v93 = (unsigned int)(v15 - v97[0]);
  v74 = DWORD2(v98) - v98;
  if ( !*((_BYTE *)v2 + 32) )
  {
    TpmVscMgrMeta::FailFast((TpmVscMgrMeta *)0x80004004LL, v97[0]);
    v70 = v88;
    v73 = *(_QWORD *)v97;
  }
  if ( (unsigned __int64)v2[3] > 7 )
    v2 = (__int64 *)*v2;
  LOBYTE(v38) = -126;
  v88 = ((__int64 (__fastcall *)(void *, __int64 *, __int64, _QWORD, int, __int64, _DWORD, __int64, int, __int64, int, unsigned int, void *, LPVOID *, int *))v100)(
          v109,
          v2,
          v38,
          v98,
          v74,
          v73,
          v93,
          v72,
          v39,
          v28,
          v71,
          v70,
          v35,
          &pv,
          &v95);
  v75 = errorlib::scoped_error<hresult_error::tag>::receive<long>(&v85, &v88);
  errorlib::scoped_error<hresult_error::tag>::throwfailed(v75);
LABEL_119:
  v89 = (const wchar_t *)pv;
  v90 = L"deviceInstanceId";
  v91 = L"";
  v100 = 0;
  ModuleHandleW = GetModuleHandleW(0);
  LoadStringNoThrow(&v109, ModuleHandleW, 513, &v100);
  if ( !v110 )
  {
    HIDWORD(v109) = 3;
    if ( (_DWORD)v109 )
      goto LABEL_124;
  }
  TpmVscMgrMeta::basic_formatter<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_formatter<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(
    v120,
    &v100);
  TpmVscMgrMeta::basic_formatter<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::insert<unsigned short const *>(
    v120,
    &v90,
    &v89);
  TpmVscMgrMeta::basic_formatter<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::gather(v120);
  v77 = v121;
  if ( v121[3] > 7u )
    v77 = (_QWORD *)v121[0];
  v78 = std::_Insert_string<unsigned short,std::char_traits<unsigned short>,unsigned __int64>(std::wcout, v77, v121[2]);
  std::basic_ostream<unsigned short>::operator<<(v78, std::endl<unsigned short,std::char_traits<unsigned short>>);
  TpmVscMgrMeta::basic_formatter<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::~basic_formatter<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v120);
  if ( v110 )
  {
    if ( v110 == 1 )
    {
      v80 = (Output *)v109;
      if ( v109 )
        operator delete(v109, v79);
    }
  }
  else
  {
LABEL_124:
    errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(&v109);
  }
  if ( v95 )
  {
    v81 = 514;
    if ( *((_BYTE *)*v108 + 40) )
      v81 = 515;
    Output::PromptUser(v80, v81);
  }
  if ( v101 )
    ((void (__fastcall *)(__int64 (__fastcall ***)(void *, GUID *, __int64 *)))(*v101)[2])(v101);
  (*(void (__fastcall **)(void *))(*(_QWORD *)v35 + 16LL))(v35);
  if ( v118 )
  {
    v118 = 0;
    std::vector<unsigned char>::~vector<unsigned char>(&v116);
  }
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v102);
  if ( v114 )
  {
    v114 = 0;
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v111);
  }
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v105);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v98);
  if ( pv )
    CoTaskMemFree(pv);
  return errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(&v85);
}

```

## disassembly

```asm
0x140008784  mov     [rsp-8+arg_10], rbx
0x140008789  push    rbp
0x14000878a  push    rsi
0x14000878b  push    rdi
0x14000878c  push    r12
0x14000878e  push    r13
0x140008790  push    r14
0x140008792  push    r15
0x140008794  lea     rbp, [rsp-130h]
0x14000879c  sub     rsp, 240h
0x1400087a3  mov     rax, cs:__security_cookie
0x1400087aa  xor     rax, rsp
0x1400087ad  mov     [rbp+160h+var_40], rax
0x1400087b4  mov     rdi, rdx
0x1400087b7  mov     r15, rcx
0x1400087ba  mov     [rbp+160h+var_118], rcx
0x1400087be  xor     r12d, r12d
0x1400087c1  mov     [rbp+160h+var_1E0], r12d
0x1400087c5  mov     [rbp+160h+var_1DC], 1
0x1400087cc  mov     [rbp+160h+pv], r12
0x1400087d0  xorps   xmm0, xmm0
0x1400087d3  movdqu  [rbp+160h+var_190], xmm0
0x1400087d8  mov     [rbp+160h+var_180], r12
0x1400087dc  movdqu  [rbp+160h+var_138], xmm0
0x1400087e1  mov     [rbp+160h+var_128], r12
0x1400087e5  mov     [rbp+160h+var_E8], r12b
0x1400087e9  lea     rax, [rbp+160h+var_100]
0x1400087ed  mov     [rbp+160h+var_E0], rax
0x1400087f4  movdqu  [rbp+160h+var_158], xmm0
0x1400087f9  mov     [rbp+160h+var_148], r12
0x1400087fd  mov     [rbp+160h+var_C0], r12b
0x140008804  lea     rax, [rbp+160h+var_D8]
0x14000880b  mov     [rbp+160h+var_B8], rax
0x140008812  mov     r14d, 80004004h
0x140008818  mov     r13d, 80070057h
0x14000881e  lea     rbx, aParametername; "parameterName"
0x140008825  lea     rsi, aParametername+1Ah; ""
0x14000882c  cmp     [rdx+20h], r12b
0x140008830  jnz     short loc_14000886A
0x140008832  mov     [rbp+160h+var_1D8], r13d
0x140008836  lea     rdx, [rbp+160h+var_1D8]
0x14000883a  lea     rcx, [rbp+160h+var_1E0]
0x14000883e  call    ??$receive@J@?$scoped_error@Utag@hresult_error@@@errorlib@@QEAAAEAV01@$$QEAJ@Z; errorlib::scoped_error<hresult_error::tag>::receive<long>(long &&)
0x140008843  mov     rax, cs:off_140014158; "/name"
0x14000884a  mov     [rbp+160h+var_1D0], rax
0x14000884e  mov     [rbp+160h+var_1C8], rbx
0x140008852  mov     [rbp+160h+var_1C0], rsi
0x140008856  mov     [rbp+160h+var_1DC], 3
0x14000885d  cmp     [rbp+160h+var_1E0], r12d
0x140008861  jge     short loc_1400088D0
0x140008863  mov     edx, 1A5h; unsigned int
0x140008868  jmp     short loc_1400088BE
0x14000886a  cmp     qword ptr [rdx+10h], 100h
0x140008872  ja      short loc_140008888
0x140008874  cmp     [rdx+20h], r12b
0x140008878  jnz     short loc_140008882
0x14000887a  mov     ecx, r14d; this
0x14000887d  call    ?FailFast@TpmVscMgrMeta@@YAXK@Z; TpmVscMgrMeta::FailFast(ulong)
0x140008882  cmp     [rdi+10h], r12
0x140008886  jnz     short loc_1400088D0
0x140008888  mov     [rbp+160h+var_1D8], r13d
0x14000888c  lea     rdx, [rbp+160h+var_1D8]
0x140008890  lea     rcx, [rbp+160h+var_1E0]
0x140008894  call    ??$receive@J@?$scoped_error@Utag@hresult_error@@@errorlib@@QEAAAEAV01@$$QEAJ@Z; errorlib::scoped_error<hresult_error::tag>::receive<long>(long &&)
0x140008899  mov     rax, cs:off_140014158; "/name"
0x1400088a0  mov     [rbp+160h+var_1D0], rax
0x1400088a4  mov     [rbp+160h+var_1C8], rbx
0x1400088a8  mov     [rbp+160h+var_1C0], rsi
0x1400088ac  mov     [rbp+160h+var_1DC], 3
0x1400088b3  cmp     [rbp+160h+var_1E0], r12d
0x1400088b7  jge     short loc_1400088D0
0x1400088b9  mov     edx, 1A6h
0x1400088be  lea     r8, [rbp+160h+var_1D0]
0x1400088c2  call    ??$DisplayErrorResource@PEBG@Output@@QEBAXHAEBV?$tuple@V?$range@PEBG@rangelib@@PEBG@std@@@Z; Output::DisplayErrorResource<ushort const *>(int,std::tuple<rangelib::range<ushort const *>,ushort const *> const &)
0x1400088c7  lea     rcx, [rbp+160h+var_1E0]
0x1400088cb  call    ?throwfailed@?$scoped_error@Utag@hresult_error@@@errorlib@@QEBAXXZ; errorlib::scoped_error<hresult_error::tag>::throwfailed(void)
0x1400088d0  cmp     [rdi+50h], r12b
0x1400088d4  jnz     short loc_140008927
0x1400088d6  mov     [rbp+160h+var_1D8], r13d
0x1400088da  lea     rdx, [rbp+160h+var_1D8]
0x1400088de  lea     rcx, [rbp+160h+var_1E0]
0x1400088e2  call    ??$receive@J@?$scoped_error@Utag@hresult_error@@@errorlib@@QEAAAEAV01@$$QEAJ@Z; errorlib::scoped_error<hresult_error::tag>::receive<long>(long &&)
0x1400088e7  mov     rax, cs:off_140014150; "/adminkey"
0x1400088ee  mov     [rbp+160h+var_1D0], rax
0x1400088f2  mov     [rbp+160h+var_1C8], rbx
0x1400088f6  mov     [rbp+160h+var_1C0], rsi
0x1400088fa  mov     [rbp+160h+var_1DC], 3
0x140008901  cmp     [rbp+160h+var_1E0], r12d
0x140008905  jge     loc_140008A24
0x14000890b  lea     r8, [rbp+160h+var_1D0]
0x14000890f  mov     edx, 1A5h
0x140008914  call    ??$DisplayErrorResource@PEBG@Output@@QEBAXHAEBV?$tuple@V?$range@PEBG@rangelib@@PEBG@std@@@Z; Output::DisplayErrorResource<ushort const *>(int,std::tuple<rangelib::range<ushort const *>,ushort const *> const &)
0x140008919  lea     rcx, [rbp+160h+var_1E0]
0x14000891d  call    ?throwfailed@?$scoped_error@Utag@hresult_error@@@errorlib@@QEBAXXZ; errorlib::scoped_error<hresult_error::tag>::throwfailed(void)
0x140008922  jmp     loc_140008A24
0x140008927  lea     rsi, [rdi+30h]
0x14000892b  mov     cl, [rsi+20h]
0x14000892e  test    cl, cl
0x140008930  jnz     short loc_14000893D
0x140008932  mov     ecx, r14d; this
0x140008935  call    ?FailFast@TpmVscMgrMeta@@YAXK@Z; TpmVscMgrMeta::FailFast(ulong)
0x14000893a  mov     cl, [rsi+20h]
0x14000893d  cmp     qword ptr [rsi+18h], 7
0x140008942  jbe     short loc_140008949
0x140008944  mov     rdx, [rsi]
0x140008947  jmp     short loc_14000894C
0x140008949  mov     rdx, rsi; unsigned int
0x14000894c  mov     rax, [rsi+10h]
0x140008950  lea     rbx, [rdx+rax*2]
0x140008954  test    cl, cl
0x140008956  jnz     short loc_140008960
0x140008958  mov     ecx, r14d; this
0x14000895b  call    ?FailFast@TpmVscMgrMeta@@YAXK@Z; TpmVscMgrMeta::FailFast(ulong)
0x140008960  cmp     qword ptr [rsi+18h], 7
0x140008965  jbe     short loc_14000896A
0x140008967  mov     rsi, [rsi]
0x14000896a  mov     r8, rbx
0x14000896d  mov     rdx, rsi
0x140008970  lea     rcx, [rbp+160h+var_1D0]
0x140008974  call    ??$ByteifyString@V?$vector@EU?$secure_allocator@E@wil@@@std@@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@@@YA?AV?$vector@EU?$secure_allocator@E@wil@@@std@@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@1@0@Z; ByteifyString<std::vector<uchar,wil::secure_allocator<uchar>>,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>(std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>)
0x140008979  mov     rbx, rax
0x14000897c  lea     rax, [rbp+160h+var_190]
0x140008980  cmp     rax, rbx
0x140008983  jz      short loc_1400089B2
0x140008985  lea     rcx, [rbp+160h+var_190]
0x140008989  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x14000898e  mov     rsi, [rbx]
0x140008991  mov     qword ptr [rbp+160h+var_190], rsi
0x140008995  mov     r14, [rbx+8]
0x140008999  mov     qword ptr [rbp+160h+var_190+8], r14
0x14000899d  mov     rcx, [rbx+10h]
0x1400089a1  mov     [rbp+160h+var_180], rcx
0x1400089a5  mov     [rbx], r12
0x1400089a8  mov     [rbx+8], r12
0x1400089ac  mov     [rbx+10h], r12
0x1400089b0  jmp     short loc_1400089BA
0x1400089b2  mov     r14, qword ptr [rbp+160h+var_190+8]
0x1400089b6  mov     rsi, qword ptr [rbp+160h+var_190]
0x1400089ba  lea     rcx, [rbp+160h+var_1D0]
0x1400089be  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x1400089c3  cmp     rsi, r14
0x1400089c6  jnz     short loc_140008A1E
0x1400089c8  mov     [rbp+160h+var_1D8], r13d
0x1400089cc  lea     rdx, [rbp+160h+var_1D8]
0x1400089d0  lea     rcx, [rbp+160h+var_1E0]
0x1400089d4  call    ??$receive@J@?$scoped_error@Utag@hresult_error@@@errorlib@@QEAAAEAV01@$$QEAJ@Z; errorlib::scoped_error<hresult_error::tag>::receive<long>(long &&)
0x1400089d9  mov     rax, cs:off_140014150; "/adminkey"
0x1400089e0  mov     [rbp+160h+var_1D0], rax
0x1400089e4  lea     rax, aParametername; "parameterName"
0x1400089eb  mov     [rbp+160h+var_1C8], rax
0x1400089ef  lea     rax, aParametername+1Ah; ""
0x1400089f6  mov     [rbp+160h+var_1C0], rax
0x1400089fa  mov     [rbp+160h+var_1DC], 3
0x140008a01  cmp     [rbp+160h+var_1E0], r12d
0x140008a05  jge     short loc_140008A1E
0x140008a07  lea     r8, [rbp+160h+var_1D0]
0x140008a0b  mov     edx, 1A6h
0x140008a10  call    ??$DisplayErrorResource@PEBG@Output@@QEBAXHAEBV?$tuple@V?$range@PEBG@rangelib@@PEBG@std@@@Z; Output::DisplayErrorResource<ushort const *>(int,std::tuple<rangelib::range<ushort const *>,ushort const *> const &)
0x140008a15  lea     rcx, [rbp+160h+var_1E0]
0x140008a19  call    ?throwfailed@?$scoped_error@Utag@hresult_error@@@errorlib@@QEBAXXZ; errorlib::scoped_error<hresult_error::tag>::throwfailed(void)
0x140008a1e  mov     r14d, 80004004h
0x140008a24  lea     r8, [rbp+160h+var_190]
0x140008a28  lea     rdx, [rbp+160h+var_1D0]
0x140008a2c  call    ?GetKcv@CommandParamReceiver@@AEAA?AV?$vector@EU?$secure_allocator@E@wil@@@std@@AEBV23@@Z; CommandParamReceiver::GetKcv(std::vector<uchar,wil::secure_allocator<uchar>> const &)
0x140008a31  mov     rbx, rax
0x140008a34  lea     rax, [rbp+160h+var_138]
0x140008a38  cmp     rax, rbx
0x140008a3b  jz      short loc_140008A6E
0x140008a3d  lea     rcx, [rbp+160h+var_138]
0x140008a41  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x140008a46  mov     rsi, [rbx]
0x140008a49  mov     qword ptr [rbp+160h+var_198], rsi
0x140008a4d  mov     qword ptr [rbp+160h+var_138], rsi
0x140008a51  mov     r13, [rbx+8]
0x140008a55  mov     qword ptr [rbp+160h+var_138+8], r13
0x140008a59  mov     rcx, [rbx+10h]
0x140008a5d  mov     [rbp+160h+var_128], rcx
0x140008a61  mov     [rbx], r12
0x140008a64  mov     [rbx+8], r12
0x140008a68  mov     [rbx+10h], r12
0x140008a6c  jmp     short loc_140008A7A
0x140008a6e  mov     r13, qword ptr [rbp+160h+var_138+8]
0x140008a72  mov     rax, qword ptr [rbp+160h+var_138]
0x140008a76  mov     qword ptr [rbp+160h+var_198], rax
0x140008a7a  mov     [rbp+160h+var_1B0], r13
0x140008a7e  lea     rcx, [rbp+160h+var_1D0]
0x140008a82  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x140008a87  cmp     [rdi+0B0h], r12b
0x140008a8e  jz      loc_140008BA1
0x140008a94  lea     rsi, [rdi+90h]
0x140008a9b  mov     cl, [rsi+20h]
0x140008a9e  test    cl, cl
0x140008aa0  jnz     short loc_140008AAD
0x140008aa2  mov     ecx, r14d; this
0x140008aa5  call    ?FailFast@TpmVscMgrMeta@@YAXK@Z; TpmVscMgrMeta::FailFast(ulong)
0x140008aaa  mov     cl, [rsi+20h]
0x140008aad  cmp     qword ptr [rsi+18h], 7
0x140008ab2  jbe     short loc_140008AB9
0x140008ab4  mov     rdx, [rsi]
0x140008ab7  jmp     short loc_140008ABC
0x140008ab9  mov     rdx, rsi; unsigned int
0x140008abc  mov     rax, [rsi+10h]
0x140008ac0  lea     rbx, [rdx+rax*2]
0x140008ac4  test    cl, cl
0x140008ac6  jnz     short loc_140008AD0
0x140008ac8  mov     ecx, r14d; this
0x140008acb  call    ?FailFast@TpmVscMgrMeta@@YAXK@Z; TpmVscMgrMeta::FailFast(ulong)
0x140008ad0  cmp     qword ptr [rsi+18h], 7
0x140008ad5  jbe     short loc_140008ADA
0x140008ad7  mov     rsi, [rsi]
0x140008ada  mov     r8, rbx
0x140008add  mov     rdx, rsi
0x140008ae0  lea     rcx, [rbp+160h+var_1D0]
0x140008ae4  call    ??$StringToAsciiVector@V?$vector@EU?$secure_allocator@E@wil@@@std@@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@@@YA?AV?$vector@EU?$secure_allocator@E@wil@@@std@@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@1@0@Z; StringToAsciiVector<std::vector<uchar,wil::secure_allocator<uchar>>,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>(std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>)
0x140008ae9  mov     rbx, rax
0x140008aec  cmp     [rbp+160h+var_E8], r12b
0x140008af0  jz      short loc_140008AFF
0x140008af2  mov     [rbp+160h+var_E8], r12b
0x140008af6  lea     rcx, [rbp+160h+var_100]
0x140008afa  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x140008aff  mov     rdx, [rbx+10h]
0x140008b03  mov     [rbx+10h], r12
0x140008b07  mov     rcx, [rbx+8]
0x140008b0b  mov     [rbx+8], r12
0x140008b0f  mov     rax, [rbx]
0x140008b12  mov     [rbx], r12
0x140008b15  mov     [rbp+160h+var_100], rax
0x140008b19  mov     [rbp+160h+var_F8], rcx
0x140008b1d  mov     [rbp+160h+var_F0], rdx
0x140008b21  mov     [rbp+160h+var_E8], 1
0x140008b25  lea     rcx, [rbp+160h+var_1D0]
0x140008b29  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x140008b2e  cmp     [rbp+160h+var_E8], r12b
0x140008b32  jnz     short loc_140008B3C
0x140008b34  mov     ecx, r14d; this
0x140008b37  call    ?FailFast@TpmVscMgrMeta@@YAXK@Z; TpmVscMgrMeta::FailFast(ulong)
0x140008b3c  mov     rax, [rbp+160h+var_F8]
0x140008b40  cmp     [rbp+160h+var_100], rax
0x140008b44  jnz     short loc_140008BA1
0x140008b46  mov     [rbp+160h+var_1D8], 80070057h
0x140008b4d  lea     rdx, [rbp+160h+var_1D8]
0x140008b51  lea     rcx, [rbp+160h+var_1E0]
0x140008b55  call    ??$receive@J@?$scoped_error@Utag@hresult_error@@@errorlib@@QEAAAEAV01@$$QEAJ@Z; errorlib::scoped_error<hresult_error::tag>::receive<long>(long &&)
0x140008b5a  mov     rax, cs:off_140014148; "/puk"
0x140008b61  mov     [rbp+160h+var_1D0], rax
0x140008b65  lea     rbx, aParametername; "parameterName"
0x140008b6c  mov     [rbp+160h+var_1C8], rbx
0x140008b70  lea     rsi, aParametername+1Ah; ""
0x140008b77  mov     [rbp+160h+var_1C0], rsi
0x140008b7b  mov     [rbp+160h+var_1DC], 3
0x140008b82  cmp     [rbp+160h+var_1E0], r12d
0x140008b86  jge     short loc_140008BAF
0x140008b88  lea     r8, [rbp+160h+var_1D0]
0x140008b8c  mov     edx, 1A6h
0x140008b91  call    ??$DisplayErrorResource@PEBG@Output@@QEBAXHAEBV?$tuple@V?$range@PEBG@rangelib@@PEBG@std@@@Z; Output::DisplayErrorResource<ushort const *>(int,std::tuple<rangelib::range<ushort const *>,ushort const *> const &)
0x140008b96  lea     rcx, [rbp+160h+var_1E0]
0x140008b9a  call    ?throwfailed@?$scoped_error@Utag@hresult_error@@@errorlib@@QEBAXXZ; errorlib::scoped_error<hresult_error::tag>::throwfailed(void)
0x140008b9f  jmp     short loc_140008BAF
0x140008ba1  lea     rsi, aParametername+1Ah; ""
0x140008ba8  lea     rbx, aParametername; "parameterName"
0x140008baf  cmp     [rdi+80h], r12b
0x140008bb6  jnz     short loc_140008C10
0x140008bb8  mov     [rbp+160h+var_1D8], 80070057h
0x140008bbf  lea     rdx, [rbp+160h+var_1D8]
0x140008bc3  lea     rcx, [rbp+160h+var_1E0]
0x140008bc7  call    ??$receive@J@?$scoped_error@Utag@hresult_error@@@errorlib@@QEAAAEAV01@$$QEAJ@Z; errorlib::scoped_error<hresult_error::tag>::receive<long>(long &&)
0x140008bcc  mov     rax, cs:off_140014140; "/pin"
0x140008bd3  mov     [rbp+160h+var_1D0], rax
0x140008bd7  mov     [rbp+160h+var_1C8], rbx
0x140008bdb  mov     [rbp+160h+var_1C0], rsi
0x140008bdf  mov     [rbp+160h+var_1DC], 3
0x140008be6  cmp     [rbp+160h+var_1E0], r12d
0x140008bea  jge     short loc_140008C03
0x140008bec  lea     r8, [rbp+160h+var_1D0]
0x140008bf0  mov     edx, 1A5h
0x140008bf5  call    ??$DisplayErrorResource@PEBG@Output@@QEBAXHAEBV?$tuple@V?$range@PEBG@rangelib@@PEBG@std@@@Z; Output::DisplayErrorResource<ushort const *>(int,std::tuple<rangelib::range<ushort const *>,ushort const *> const &)
0x140008bfa  lea     rcx, [rbp+160h+var_1E0]
0x140008bfe  call    ?throwfailed@?$scoped_error@Utag@hresult_error@@@errorlib@@QEBAXXZ; errorlib::scoped_error<hresult_error::tag>::throwfailed(void)
0x140008c03  mov     rsi, qword ptr [rbp+160h+var_158+8]
0x140008c07  mov     r14, qword ptr [rbp+160h+var_158]
0x140008c0b  jmp     loc_140008D0A
0x140008c10  lea     rsi, [rdi+60h]
0x140008c14  mov     cl, [rsi+20h]
0x140008c17  test    cl, cl
0x140008c19  jnz     short loc_140008C26
0x140008c1b  mov     ecx, r14d; this
0x140008c1e  call    ?FailFast@TpmVscMgrMeta@@YAXK@Z; TpmVscMgrMeta::FailFast(ulong)
0x140008c23  mov     cl, [rsi+20h]
0x140008c26  cmp     qword ptr [rsi+18h], 7
0x140008c2b  jbe     short loc_140008C32
0x140008c2d  mov     rdx, [rsi]
0x140008c30  jmp     short loc_140008C35
0x140008c32  mov     rdx, rsi; unsigned int
0x140008c35  mov     rax, [rsi+10h]
0x140008c39  lea     rbx, [rdx+rax*2]
0x140008c3d  test    cl, cl
0x140008c3f  jnz     short loc_140008C49
0x140008c41  mov     ecx, r14d; this
0x140008c44  call    ?FailFast@TpmVscMgrMeta@@YAXK@Z; TpmVscMgrMeta::FailFast(ulong)
0x140008c49  cmp     qword ptr [rsi+18h], 7
  ... truncated ...
```
