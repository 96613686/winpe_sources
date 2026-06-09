# _anonymous_namespace_::LazyData::LazyData

- ea: `0x1800491e4`
- end: `0x180049eea`
- name: `_anonymous_namespace_::LazyData::LazyData`
- size: `3334`
- prototype: `_QWORD *__fastcall(_OWORD *, LPVOID *, LPVOID *)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004c510`

## callees

- `0x1800060a0`
- `0x180006ee0`
- `0x180007ed9`
- `0x180008d50`
- `0x18000947c`
- `0x180009a80`
- `0x180009de0`
- `0x18000e93c`
- `0x18000ecc0`
- `0x1800157f8`
- `0x180035048`
- `0x180035af4`
- `0x180035e0c`
- `0x1800491e4`
- `0x18004a764`
- `0x18004ad00`
- `0x18004b1e0`
- `0x1800591d4`
- `0x180059228`
- `0x180059820`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800499d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800499eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049a5d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049ae1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049af5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800499d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800499eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049a5d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049ae1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049af5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800493db`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004966a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800493db`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004966a`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x180049388`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x180049388`

## string_xrefs

- `0x180049332`: `AppxManifest.xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall anonymous_namespace_::LazyData::LazyData(_OWORD *a1, LPVOID *a2, LPVOID *a3)
{
  LPVOID *v3; // r15
  _QWORD *v4; // r13
  unsigned __int64 *v5; // rcx
  _QWORD *v6; // r12
  __int64 v7; // rax
  HRESULT v8; // ebx
  HRESULT v9; // ebx
  int v10; // ebx
  int v11; // ebx
  int v12; // ebx
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, __int64); // rbx
  __int64 v15; // rdx
  int v16; // ebx
  _BYTE *v17; // rdx
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, __int64); // rbx
  __int64 v20; // rdx
  int v21; // ebx
  _BYTE *v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rcx
  LPVOID v25; // rcx
  IStream *v26; // rcx
  HRESULT v27; // ebx
  LPVOID *v28; // rbx
  _QWORD *v29; // rdx
  LPVOID v30; // rdi
  _QWORD *v31; // rax
  int v32; // edi
  int v33; // edi
  __int64 v34; // rcx
  __int64 v35; // rbx
  _QWORD *v36; // rdi
  __int64 v37; // rax
  __int64 v38; // rax
  void *v39; // r9
  unsigned __int64 v40; // rdi
  unsigned __int64 v41; // rdx
  char *v42; // r14
  __int64 v43; // rbx
  __int64 v44; // r8
  void *v45; // r9
  void **v46; // rax
  void *v47; // rdx
  void *v48; // rcx
  __int64 v49; // rax
  __int64 v50; // rcx
  __int64 v51; // rcx
  LPVOID v52; // rcx
  __int64 v53; // rcx
  __int64 v55; // rax
  int v56; // eax
  __int64 v57; // r10
  __int64 v58; // rax
  int v59; // eax
  __int64 v60; // r10
  __int64 v61; // rax
  int v62; // eax
  __int64 v63; // r10
  __int64 v64; // rax
  int v65; // eax
  __int64 v66; // r10
  __int64 v67; // rax
  int v68; // eax
  __int64 v69; // r10
  int v70; // eax
  __int64 v71; // r10
  unsigned int v72; // eax
  LPVOID v73; // rcx
  __int64 v74; // rcx
  __int64 v75; // rax
  __int64 v76; // rax
  __int64 v77; // r8
  LPVOID v78; // [rsp+30h] [rbp-3B8h] BYREF
  __int64 v79; // [rsp+38h] [rbp-3B0h] BYREF
  __int64 v80; // [rsp+40h] [rbp-3A8h] BYREF
  __int64 v81; // [rsp+48h] [rbp-3A0h] BYREF
  __int64 v82; // [rsp+50h] [rbp-398h] BYREF
  __int64 v83; // [rsp+58h] [rbp-390h] BYREF
  __int64 v84; // [rsp+60h] [rbp-388h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-380h] BYREF
  IStream *ppstm; // [rsp+70h] [rbp-378h] BYREF
  LPVOID pv; // [rsp+78h] [rbp-370h] BYREF
  LPVOID *v88; // [rsp+80h] [rbp-368h]
  _OWORD *v89; // [rsp+88h] [rbp-360h]
  _QWORD *v90; // [rsp+90h] [rbp-358h]
  void *Src; // [rsp+98h] [rbp-350h] BYREF
  void *v92; // [rsp+A0h] [rbp-348h] BYREF
  _QWORD *v93; // [rsp+A8h] [rbp-340h]
  _QWORD *v94; // [rsp+B0h] [rbp-338h]
  _QWORD *v95; // [rsp+B8h] [rbp-330h]
  _QWORD *v96; // [rsp+C0h] [rbp-328h]
  LPVOID *v97; // [rsp+C8h] [rbp-320h]
  unsigned __int64 *v98; // [rsp+D0h] [rbp-318h]
  unsigned __int64 *v99; // [rsp+D8h] [rbp-310h]
  unsigned __int64 *v100; // [rsp+E0h] [rbp-308h]
  LPVOID v101[2]; // [rsp+E8h] [rbp-300h] BYREF
  _QWORD v102[3]; // [rsp+F8h] [rbp-2F0h] BYREF
  const std::exception *v103; // [rsp+110h] [rbp-2D8h] BYREF
  const std::exception *v104; // [rsp+118h] [rbp-2D0h] BYREF
  const std::exception *v105; // [rsp+120h] [rbp-2C8h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+128h] [rbp-2C0h] BYREF
  _BYTE v107[40]; // [rsp+150h] [rbp-298h] BYREF
  _BYTE v108[40]; // [rsp+178h] [rbp-270h] BYREF
  _BYTE v109[40]; // [rsp+1A0h] [rbp-248h] BYREF
  _BYTE v110[40]; // [rsp+1C8h] [rbp-220h] BYREF
  _BYTE v111[40]; // [rsp+1F0h] [rbp-1F8h] BYREF
  _BYTE v112[40]; // [rsp+218h] [rbp-1D0h] BYREF
  _BYTE v113[40]; // [rsp+240h] [rbp-1A8h] BYREF
  _BYTE v114[40]; // [rsp+268h] [rbp-180h] BYREF
  _BYTE v115[40]; // [rsp+290h] [rbp-158h] BYREF
  LPVOID *v116; // [rsp+2B8h] [rbp-130h]
  __int128 v117; // [rsp+2C0h] [rbp-128h] BYREF
  LPVOID *p_pv; // [rsp+2D0h] [rbp-118h]
  LPVOID *v119; // [rsp+2D8h] [rbp-110h]
  _BYTE v120[32]; // [rsp+2E0h] [rbp-108h] BYREF
  __int64 v121; // [rsp+300h] [rbp-E8h] BYREF
  _BYTE v122[56]; // [rsp+308h] [rbp-E0h] BYREF
  _BYTE *v123; // [rsp+340h] [rbp-A8h]
  __int64 v124; // [rsp+350h] [rbp-98h] BYREF
  _BYTE v125[56]; // [rsp+358h] [rbp-90h] BYREF
  _BYTE *v126; // [rsp+390h] [rbp-58h]

  v3 = a3;
  v88 = a2;
  v4 = a1;
  v89 = a1;
  v97 = a2;
  v116 = a3;
  *a1 = 0;
  v99 = (unsigned __int64 *)(a1 + 1);
  v5 = (unsigned __int64 *)a1 + 3;
  v98 = v5;
  *v99 = 0;
  *v5 = 7;
  *(_WORD *)v4 = 0;
  v94 = v4 + 4;
  *((_OWORD *)v4 + 2) = 0;
  v4[6] = 0;
  v4[7] = 7;
  *((_WORD *)v4 + 16) = 0;
  *((_OWORD *)v4 + 4) = 0;
  v4[10] = 0;
  v4[11] = 7;
  *((_WORD *)v4 + 32) = 0;
  v6 = v4 + 12;
  v90 = v4 + 12;
  *((_OWORD *)v4 + 6) = 0;
  v101[0] = v4 + 14;
  v100 = v4 + 15;
  v4[14] = 0;
  v4[15] = 7;
  *((_WORD *)v4 + 48) = 0;
  v95 = v4 + 16;
  v117 = 0;
  p_pv = 0;
  v119 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v117, &SubKey, 0);
  IO::Path::Path(v4 + 16, &v117);
  v92 = 0;
  Src = 0;
  v81 = 0;
  ppstm = 0;
  std::wstring::wstring(&v117, L"AppxManifest.xml");
  v7 = IO::operator/(v120, v3, &v117);
  if ( *(_QWORD *)(v7 + 24) > 7u )
    v7 = *(_QWORD *)v7;
  v8 = SHCreateStreamOnFileEx((LPCWSTR)v7, 0x20u, 0x80u, 0, 0, &ppstm);
  std::wstring::~wstring(v120);
  std::wstring::~wstring(&v117);
  if ( v8 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v55 = std::array<unsigned short,16>::data(v3);
      v56 = std::wstring::c_str(v55);
      WPP_SF_Sd(*(_QWORD *)(v57 + 16), 31, (int)WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids, v56, v8);
    }
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v8);
    throw (ErrorCodeException *)pExceptionObject;
  }
  ppv = 0;
  v9 = CoCreateInstance(
         &GUID_5842a140_ff9f_4166_8f5c_62f5b7b0c781,
         0,
         1u,
         &GUID_beb94909_e451_438b_b5a7_d79e767b75d8,
         &ppv);
  if ( v9 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        32,
        WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids,
        (unsigned int)v9);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)v107, v9);
    throw (ErrorCodeException *)v107;
  }
  v83 = 0;
  v10 = (*(__int64 (__fastcall **)(LPVOID, IStream *, __int64 *))(*(_QWORD *)ppv + 40LL))(ppv, ppstm, &v83);
  if ( v10 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v58 = std::array<unsigned short,16>::data(v3);
      v59 = std::wstring::c_str(v58);
      WPP_SF_Sd(*(_QWORD *)(v60 + 16), 33, (int)WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids, v59, v10);
    }
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)v108, v10);
    throw (ErrorCodeException *)v108;
  }
  v11 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v83 + 32LL))(v83, &v81);
  if ( v11 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v61 = std::array<unsigned short,16>::data(v3);
      v62 = std::wstring::c_str(v61);
      WPP_SF_Sd(*(_QWORD *)(v63 + 16), 34, (int)WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids, v62, v11);
    }
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)v109, v11);
    throw (ErrorCodeException *)v109;
  }
  v82 = 0;
  v12 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v83 + 24LL))(v83, &v82);
  if ( v12 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v64 = std::array<unsigned short,16>::data(v3);
      v65 = std::wstring::c_str(v64);
      WPP_SF_Sd(*(_QWORD *)(v66 + 16), 35, (int)WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids, v65, v12);
    }
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)v110, v12);
    throw (ErrorCodeException *)v110;
  }
  v13 = v82;
  v14 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v82 + 24LL);
  v15 = stdext::get_pointer<std::unique_ptr<unsigned short,ComDeallocator>>(&v121, &Src);
  v16 = v14(v13, v15);
  if ( v123 )
  {
    v84 = v121;
    (*(void (__fastcall **)(_BYTE *, __int64 *))(*(_QWORD *)v123 + 16LL))(v123, &v84);
    if ( v123 )
    {
      v17 = v122;
      LOBYTE(v17) = v123 != v122;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v123 + 32LL))(v123, v17);
    }
  }
  if ( v16 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        36,
        WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids,
        (unsigned int)v16);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)v111, v16);
    throw (ErrorCodeException *)v111;
  }
  v18 = v82;
  v19 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v82 + 40LL);
  v20 = stdext::get_pointer<std::unique_ptr<unsigned short,ComDeallocator>>(&v124, &v92);
  v21 = v19(v18, v20);
  if ( v126 )
  {
    v84 = v124;
    (*(void (__fastcall **)(_BYTE *, __int64 *))(*(_QWORD *)v126 + 16LL))(v126, &v84);
    if ( v126 )
    {
      v22 = v125;
      LOBYTE(v22) = v126 != v125;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v126 + 32LL))(v126, v22);
    }
  }
  if ( v21 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        37,
        WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids,
        (unsigned int)v21);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)v112, v21);
    throw (ErrorCodeException *)v112;
  }
  v96 = v94;
  v93 = v4 + 8;
  v23 = v82;
  if ( v82 )
  {
    v82 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  }
  v24 = v83;
  if ( v83 )
  {
    v83 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  }
  v25 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v25 + 16LL))(v25);
  }
  v26 = ppstm;
  if ( ppstm )
  {
    ppstm = 0;
    (*(void (__fastcall **)(IStream *))(*(_QWORD *)v26 + 16LL))(v26);
  }
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v78 = 0;
    v80 = 0;
    v79 = 0;
    v27 = CoCreateInstance(
            &GUID_dbce7e40_7345_439d_b12c_114a11819a09,
            0,
            1u,
            &GUID_130a2f65_2be7_4309_9a58_a9052ff2b61c,
            &v78);
    if ( v27 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          38,
          WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids,
          (unsigned int)v27);
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)v113, v27);
      throw (ErrorCodeException *)v113;
    }
    v28 = v88;
    if ( (unsigned __int64)v88[3] <= 7 )
      v29 = v88;
    else
      v29 = *v88;
    if ( (*(int (__fastcall **)(LPVOID, _QWORD *))(*(_QWORD *)v78 + 40LL))(v78, v29) < 0 )
    {
      v30 = v78;
      v84 = *(_QWORD *)v78;
      std::wstring::wstring(&v117, L"resources.pri");
      v31 = (_QWORD *)IO::operator/(v120, v3, &v117);
      if ( v31[3] > 7u )
        v31 = (_QWORD *)*v31;
      v32 = (*(__int64 (__fastcall **)(LPVOID, _QWORD *))(v84 + 48))(v30, v31);
      std::wstring::~wstring(v120);
      std::wstring::~wstring(&v117);
      if ( v32 < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v67 = std::array<unsigned short,16>::data(v3);
          v68 = std::wstring::c_str(v67);
          WPP_SF_Sd(*(_QWORD *)(v69 + 16), 39, (int)WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids, v68, v32);
        }
        ErrorCodeException::ErrorCodeException((ErrorCodeException *)v114, v32);
        throw (ErrorCodeException *)v114;
      }
    }
    v33 = (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64 *))(*(_QWORD *)v78 + 56LL))(
            v78,
            &GUID_6e21e72b_b9b0_42ae_a686_983cf784edcd,
            &v80);
    if ( v33 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v70 = std::wstring::c_str(v28);
        WPP_SF_Sd(*(_QWORD *)(v71 + 16), 40, (int)WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids, v70, v33);
      }
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)v115, v33);
      throw (ErrorCodeException *)v115;
    }
    if ( (*(int (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v80 + 32LL))(v80, L"Resources", &v79) < 0 )
    {
      v34 = v79;
      v35 = v80;
      if ( v79 != v80 )
      {
        if ( v80 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 8LL))(v80);
          v34 = v79;
        }
        v79 = v35;
        if ( v34 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
      }
      v28 = v88;
    }
    v36 = v94;
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &std::exception `RTTI Type Descriptor', &v103) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v72 = ErrorCodeFromException(v103);
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids, v72);
      }
      v73 = v78;
      if ( v78 )
      {
        v78 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v73 + 16LL))(v73);
      }
      v74 = v79;
      if ( v79 )
      {
        v79 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
      }
      v36 = v96;
      v28 = v97;
      v4 = v89;
      v3 = v116;
      v6 = v90;
      __eh34_try_continuation(0, &std::exception `RTTI Type Descriptor', &loc_1800497C4);
    }
  }
  if ( __eh34_try(-1, 2) )
  {
    __eh34_scope_strut(2);
    v102[0] = &v81;
    v102[1] = v28;
    v102[2] = &v78;
    *(_QWORD *)&v117 = v102;
    *((_QWORD *)&v117 + 1) = &v80;
    p_pv = v28;
    v119 = &v78;
    v37 = lambda_71aecd3417d7b7ddb55d9f1c3553005b_::operator()(&v117, v120, L"DisplayName");
    std::wstring::operator=(v36, v37);
    std::wstring::~wstring(v120);
  }
  if ( __eh34_catch(2) )
  {
    if ( __eh34_catch_type(2, &std::exception `RTTI Type Descriptor', &v104) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v75 = (*(__int64 (__fastcall **)(const std::exception *))(*(_QWORD *)v104 + 8LL))(v104);
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids, v75);
      }
      v4 = v89;
      v3 = v116;
      v6 = v90;
      __eh34_try_continuation(2, &std::exception `RTTI Type Descriptor', &loc_180049879);
    }
  }
  if ( __eh34_try(-1, 4) )
  {
    __eh34_scope_strut(4);
    v38 = lambda_71aecd3417d7b7ddb55d9f1c3553005b_::operator()(&v117, v120, L"PublisherDisplayName");
    std::wstring::operator=(v93, v38);
    std::wstring::~wstring(v120);
  }
  if ( __eh34_catch(4) )
  {
    if ( __eh34_catch_type(4, &std::exception `RTTI Type Descriptor', &v105) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v76 = (*(__int64 (__fastcall **)(const std::exception *))(*(_QWORD *)v105 + 8LL))(v105);
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids, v76);
      }
      v4 = v89;
      v3 = v116;
      v6 = v90;
      __eh34_try_continuation(4, &std::exception `RTTI Type Descriptor', &loc_1800498CF);
    }
  }
  v39 = Src;
  v40 = -1;
  v41 = -1;
  do
    ++v41;
  while ( *((_WORD *)Src + v41) );
  if ( v41 > *v98 )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v4, v41, v77, Src);
  }
  else
  {
    if ( *v98 <= 7 )
      v42 = (char *)v4;
    else
      v42 = (char *)*v4;
    *v99 = v41;
    v43 = 2 * v41;
    memmove_0(v42, v39, 2 * v41);
    *(_WORD *)&v42[v43] = 0;
  }
  v45 = v92;
  do
    ++v40;
  while ( *((_WORD *)v92 + v40) );
  if ( v40 > *v100 )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v6, v40, v44, v92);
  }
  else
  {
    if ( *v100 > 7 )
      v6 = (_QWORD *)*v6;
    *(_QWORD *)v101[0] = v40;
    memmove_0(v6, v45, 2 * v40);
    *((_WORD *)v6 + v40) = 0;
  }
  pv = 0;
  v46 = (void **)lambda_d40de2733d855246ee074aa8c091e9f3_::operator()(v102, v101, L"Logo");
  v47 = *v46;
  *v46 = 0;
  v48 = pv;
  pv = v47;
  if ( v48 )
    CoTaskMemFree(v48);
  if ( v101[0] )
    CoTaskMemFree(v101[0]);
  *(_QWORD *)&v117 = &v78;
  *((_QWORD *)&v117 + 1) = &v80;
  p_pv = &pv;
  v119 = v3;
  v49 = lambda_522f252fccf6755638ce70b922f17e30_::operator()(&v117, v120);
  std::wstring::operator=(v95, v49);
  std::wstring::~wstring(v120);
  if ( pv )
    CoTaskMemFree(pv);
  v50 = v79;
  if ( v79 )
  {
    v79 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
  }
  v51 = v80;
  if ( v80 )
  {
    v80 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
  }
  v52 = v78;
  if ( v78 )
  {
    v78 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v52 + 16LL))(v52);
  }
  v53 = v81;
  if ( v81 )
  {
    v81 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
  }
  if ( Src )
    CoTaskMemFree(Src);
  if ( v92 )
    CoTaskMemFree(v92);
  std::wstring::~wstring(v3);
  return v4;
}

```

## disassembly

```asm
0x1800491e4  mov     r11, rsp
0x1800491e7  push    rbx
0x1800491e8  push    rsi
0x1800491e9  push    rdi
0x1800491ea  push    r12
0x1800491ec  push    r13
0x1800491ee  push    r14
0x1800491f0  push    r15
0x1800491f2  sub     rsp, 3B0h
0x1800491f9  mov     rax, cs:__security_cookie
0x180049200  xor     rax, rsp
0x180049203  mov     [rsp+3E8h+var_48], rax
0x18004920b  mov     r15, r8
0x18004920e  mov     [rsp+3E8h+var_368], rdx
0x180049216  mov     r13, rcx
0x180049219  mov     [r11-360h], rcx
0x180049220  mov     [rsp+3E8h+var_320], rdx
0x180049228  mov     [r11-130h], r8
0x18004922f  xorps   xmm0, xmm0
0x180049232  movups  xmmword ptr [rcx], xmm0
0x180049235  lea     rax, [rcx+10h]
0x180049239  mov     [rsp+3E8h+var_310], rax
0x180049241  add     rcx, 18h
0x180049245  mov     [rsp+3E8h+var_318], rcx
0x18004924d  xor     esi, esi
0x18004924f  mov     [rax], rsi
0x180049252  mov     qword ptr [rcx], 7
0x180049259  mov     [r13+0], si
0x18004925e  lea     rax, [r13+20h]
0x180049262  mov     [rsp+3E8h+var_338], rax
0x18004926a  movups  xmmword ptr [rax], xmm0
0x18004926d  mov     [rax+10h], rsi
0x180049271  mov     qword ptr [rax+18h], 7
0x180049279  mov     [rax], si
0x18004927c  movups  xmmword ptr [r13+40h], xmm0
0x180049281  mov     [r13+50h], rsi
0x180049285  mov     qword ptr [r13+58h], 7
0x18004928d  mov     [r13+40h], si
0x180049292  lea     r12, [r13+60h]
0x180049296  mov     [rsp+3E8h+var_358], r12
0x18004929e  movups  xmmword ptr [r12], xmm0
0x1800492a3  lea     rcx, [r12+10h]
0x1800492a8  mov     [rsp+3E8h+var_300], rcx
0x1800492b0  lea     rax, [r12+18h]
0x1800492b5  mov     [rsp+3E8h+var_308], rax
0x1800492bd  mov     [rcx], rsi
0x1800492c0  mov     qword ptr [rax], 7
0x1800492c7  mov     [r12], si
0x1800492cc  lea     rbx, [r13+80h]
0x1800492d3  mov     [rsp+3E8h+var_330], rbx
0x1800492db  movups  [rsp+3E8h+var_128], xmm0
0x1800492e3  mov     [r11-118h], rsi
0x1800492ea  mov     [r11-110h], rsi
0x1800492f1  xor     r8d, r8d
0x1800492f4  lea     rdx, SubKey
0x1800492fb  lea     rcx, [r11-128h]
0x180049302  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180049307  lea     rdx, [rsp+3E8h+var_128]
0x18004930f  mov     rcx, rbx
0x180049312  call    ??0Path@IO@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; IO::Path::Path(std::wstring)
0x180049317  nop
0x180049318  mov     [rsp+3E8h+var_348], rsi
0x180049320  mov     [rsp+3E8h+Src], rsi
0x180049328  mov     [rsp+3E8h+var_3A0], rsi
0x18004932d  mov     [rsp+3E8h+var_378], rsi
0x180049332  lea     rdx, aAppxmanifestXm; "AppxManifest.xml"
0x180049339  lea     rcx, [rsp+3E8h+var_128]
0x180049341  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180049346  nop
0x180049347  lea     r8, [rsp+3E8h+var_128]
0x18004934f  mov     rdx, r15
0x180049352  lea     rcx, [rsp+3E8h+var_108]
0x18004935a  call    ??KIO@@YA?AVPath@0@AEBV10@0@Z; IO::operator/(IO::Path const &,IO::Path const &)
0x18004935f  cmp     qword ptr [rax+18h], 7
0x180049364  jbe     short loc_180049369
0x180049366  mov     rax, [rax]
0x180049369  lea     rcx, [rsp+3E8h+var_378]
0x18004936e  mov     [rsp+3E8h+ppstm], rcx; ppstm
0x180049373  mov     [rsp+3E8h+pstmTemplate], rsi; pstmTemplate
0x180049378  xor     r9d, r9d; fCreate
0x18004937b  lea     edi, [r9+20h]
0x18004937f  lea     r8d, [rdi+60h]; dwAttributes
0x180049383  mov     edx, edi; grfMode
0x180049385  mov     rcx, rax; pszFile
0x180049388  call    cs:__imp_SHCreateStreamOnFileEx
0x18004938e  mov     ebx, eax
0x180049390  lea     rcx, [rsp+3E8h+var_108]
0x180049398  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004939d  nop
0x18004939e  lea     rcx, [rsp+3E8h+var_128]
0x1800493a6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800493ab  test    ebx, ebx
0x1800493ad  js      loc_180049B2A
0x1800493b3  mov     [rsp+3E8h+ppv], rsi
0x1800493b8  lea     rax, [rsp+3E8h+ppv]
0x1800493bd  mov     [rsp+3E8h+pstmTemplate], rax; ppv
0x1800493c2  lea     r9, _GUID_beb94909_e451_438b_b5a7_d79e767b75d8; riid
0x1800493c9  mov     r14d, 1
0x1800493cf  mov     r8d, r14d; dwClsContext
0x1800493d2  xor     edx, edx; pUnkOuter
0x1800493d4  lea     rcx, _GUID_5842a140_ff9f_4166_8f5c_62f5b7b0c781; rclsid
0x1800493db  call    cs:__imp_CoCreateInstance
0x1800493e1  mov     ebx, eax
0x1800493e3  test    eax, eax
0x1800493e5  js      loc_180049B95
0x1800493eb  mov     [rsp+3E8h+var_390], rsi
0x1800493f0  mov     rcx, [rsp+3E8h+ppv]
0x1800493f5  mov     rax, [rcx]
0x1800493f8  lea     r8, [rsp+3E8h+var_390]
0x1800493fd  mov     rdx, [rsp+3E8h+var_378]
0x180049402  mov     rax, [rax+28h]
0x180049406  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004940b  mov     ebx, eax
0x18004940d  test    eax, eax
0x18004940f  js      loc_180049BE7
0x180049415  mov     rbx, [rsp+3E8h+var_390]
0x18004941a  mov     rax, [rbx]
0x18004941d  mov     rdi, [rax+20h]
0x180049421  mov     rcx, [rsp+3E8h+var_3A0]
0x180049426  test    rcx, rcx
0x180049429  jz      short loc_18004943D
0x18004942b  mov     [rsp+3E8h+var_3A0], rsi
0x180049430  mov     rax, [rcx]
0x180049433  mov     rax, [rax+10h]
0x180049437  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004943c  nop
0x18004943d  lea     rdx, [rsp+3E8h+var_3A0]
0x180049442  mov     rcx, rbx
0x180049445  mov     rax, rdi
0x180049448  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004944d  mov     ebx, eax
0x18004944f  test    eax, eax
0x180049451  js      loc_180049C50
0x180049457  mov     [rsp+3E8h+var_398], rsi
0x18004945c  mov     rcx, [rsp+3E8h+var_390]
0x180049461  mov     rax, [rcx]
0x180049464  lea     rdx, [rsp+3E8h+var_398]
0x180049469  mov     rax, [rax+18h]
0x18004946d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049472  mov     ebx, eax
0x180049474  test    eax, eax
0x180049476  js      loc_180049CB9
0x18004947c  mov     rdi, [rsp+3E8h+var_398]
0x180049481  mov     rax, [rdi]
0x180049484  mov     rbx, [rax+18h]
0x180049488  lea     rdx, [rsp+3E8h+Src]
0x180049490  lea     rcx, [rsp+3E8h+var_E8]
0x180049498  call    ??$get_pointer@V?$unique_ptr@GUComDeallocator@@@std@@@stdext@@YA?AV?$GetPointer@PEAG@0@AEAV?$unique_ptr@GUComDeallocator@@@std@@@Z; stdext::get_pointer<std::unique_ptr<ushort,ComDeallocator>>(std::unique_ptr<ushort,ComDeallocator> &)
0x18004949d  nop
0x18004949e  mov     rdx, rax
0x1800494a1  mov     rcx, rdi
0x1800494a4  mov     rax, rbx
0x1800494a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800494ac  mov     ebx, eax
0x1800494ae  mov     rcx, [rsp+3E8h+var_A8]
0x1800494b6  test    rcx, rcx
0x1800494b9  jz      short loc_180049501
0x1800494bb  mov     rax, [rsp+3E8h+var_E8]
0x1800494c3  mov     [rsp+3E8h+var_388], rax
0x1800494c8  mov     rax, [rcx]
0x1800494cb  lea     rdx, [rsp+3E8h+var_388]
0x1800494d0  mov     rax, [rax+10h]
0x1800494d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800494d9  mov     rcx, [rsp+3E8h+var_A8]
0x1800494e1  test    rcx, rcx
0x1800494e4  jz      short loc_180049501
0x1800494e6  mov     rax, [rcx]
0x1800494e9  lea     rdx, [rsp+3E8h+var_E0]
0x1800494f1  cmp     rcx, rdx
0x1800494f4  setnz   dl
0x1800494f7  mov     rax, [rax+20h]
0x1800494fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049500  nop
0x180049501  test    ebx, ebx
0x180049503  js      loc_180049D22
0x180049509  mov     rdi, [rsp+3E8h+var_398]
0x18004950e  mov     rax, [rdi]
0x180049511  mov     rbx, [rax+28h]
0x180049515  lea     rdx, [rsp+3E8h+var_348]
0x18004951d  lea     rcx, [rsp+3E8h+var_98]
0x180049525  call    ??$get_pointer@V?$unique_ptr@GUComDeallocator@@@std@@@stdext@@YA?AV?$GetPointer@PEAG@0@AEAV?$unique_ptr@GUComDeallocator@@@std@@@Z; stdext::get_pointer<std::unique_ptr<ushort,ComDeallocator>>(std::unique_ptr<ushort,ComDeallocator> &)
0x18004952a  nop
0x18004952b  mov     rdx, rax
0x18004952e  mov     rcx, rdi
0x180049531  mov     rax, rbx
0x180049534  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049539  mov     ebx, eax
0x18004953b  mov     rcx, [rsp+3E8h+var_58]
0x180049543  test    rcx, rcx
0x180049546  jz      short loc_18004958E
0x180049548  mov     rax, [rsp+3E8h+var_98]
0x180049550  mov     [rsp+3E8h+var_388], rax
0x180049555  mov     rax, [rcx]
0x180049558  lea     rdx, [rsp+3E8h+var_388]
0x18004955d  mov     rax, [rax+10h]
0x180049561  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049566  mov     rcx, [rsp+3E8h+var_58]
0x18004956e  test    rcx, rcx
0x180049571  jz      short loc_18004958E
0x180049573  mov     rax, [rcx]
0x180049576  lea     rdx, [rsp+3E8h+var_90]
0x18004957e  cmp     rcx, rdx
0x180049581  setnz   dl
0x180049584  mov     rax, [rax+20h]
0x180049588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004958d  nop
0x18004958e  test    ebx, ebx
0x180049590  js      loc_180049D77
0x180049596  mov     rax, [rsp+3E8h+var_338]
0x18004959e  mov     [rsp+3E8h+var_328], rax
0x1800495a6  lea     rax, [r13+40h]
0x1800495aa  mov     [rsp+3E8h+var_340], rax
0x1800495b2  mov     rcx, [rsp+3E8h+var_398]
0x1800495b7  test    rcx, rcx
0x1800495ba  jz      short loc_1800495CE
0x1800495bc  mov     [rsp+3E8h+var_398], rsi
0x1800495c1  mov     rax, [rcx]
0x1800495c4  mov     rax, [rax+10h]
0x1800495c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800495cd  nop
0x1800495ce  mov     rcx, [rsp+3E8h+var_390]
0x1800495d3  test    rcx, rcx
0x1800495d6  jz      short loc_1800495EA
0x1800495d8  mov     [rsp+3E8h+var_390], rsi
0x1800495dd  mov     rax, [rcx]
0x1800495e0  mov     rax, [rax+10h]
0x1800495e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800495e9  nop
0x1800495ea  mov     rcx, [rsp+3E8h+ppv]
0x1800495ef  test    rcx, rcx
0x1800495f2  jz      short loc_180049606
0x1800495f4  mov     [rsp+3E8h+ppv], rsi
0x1800495f9  mov     rax, [rcx]
0x1800495fc  mov     rax, [rax+10h]
0x180049600  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049605  nop
0x180049606  mov     rcx, [rsp+3E8h+var_378]
0x18004960b  test    rcx, rcx
0x18004960e  jz      short loc_180049622
0x180049610  mov     [rsp+3E8h+var_378], rsi
0x180049615  mov     rax, [rcx]
0x180049618  mov     rax, [rax+10h]
0x18004961c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049621  nop
0x180049622  mov     [rsp+3E8h+var_3B8], rsi
0x180049627  mov     [rsp+3E8h+var_3A8], rsi
0x18004962c  mov     [rsp+3E8h+var_3B0], rsi
0x180049631  mov     rcx, [rsp+3E8h+var_3B8]
0x180049636  test    rcx, rcx
0x180049639  jz      short loc_18004964D
0x18004963b  mov     [rsp+3E8h+var_3B8], rsi
0x180049640  mov     rax, [rcx]
0x180049643  mov     rax, [rax+10h]
0x180049647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004964c  nop
0x18004964d  lea     rax, [rsp+3E8h+var_3B8]
0x180049652  mov     [rsp+3E8h+pstmTemplate], rax; ppv
0x180049657  lea     r9, _GUID_130a2f65_2be7_4309_9a58_a9052ff2b61c; riid
0x18004965e  mov     r8d, r14d; dwClsContext
0x180049661  xor     edx, edx; pUnkOuter
0x180049663  lea     rcx, _GUID_dbce7e40_7345_439d_b12c_114a11819a09; rclsid
0x18004966a  call    cs:__imp_CoCreateInstance
0x180049670  mov     ebx, eax
0x180049672  test    eax, eax
0x180049674  js      loc_180049DCC
0x18004967a  mov     rcx, [rsp+3E8h+var_3B8]
0x18004967f  mov     rax, [rcx]
0x180049682  mov     rbx, [rsp+3E8h+var_368]
0x18004968a  cmp     qword ptr [rbx+18h], 7
0x18004968f  jbe     short loc_180049696
0x180049691  mov     rdx, [rbx]
0x180049694  jmp     short loc_180049699
0x180049696  mov     rdx, rbx
0x180049699  mov     rax, [rax+28h]
0x18004969d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800496a2  test    eax, eax
0x1800496a4  jns     loc_18004972B
0x1800496aa  mov     rdi, [rsp+3E8h+var_3B8]
0x1800496af  mov     rax, [rdi]
0x1800496b2  mov     [rsp+3E8h+var_388], rax
0x1800496b7  lea     rdx, aResourcesPri; "resources.pri"
0x1800496be  lea     rcx, [rsp+3E8h+var_128]
0x1800496c6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800496cb  nop
0x1800496cc  lea     r8, [rsp+3E8h+var_128]
0x1800496d4  mov     rdx, r15
0x1800496d7  lea     rcx, [rsp+3E8h+var_108]
0x1800496df  call    ??KIO@@YA?AVPath@0@AEBV10@0@Z; IO::operator/(IO::Path const &,IO::Path const &)
0x1800496e4  nop
0x1800496e5  mov     rcx, [rsp+3E8h+var_388]
0x1800496ea  mov     r8, [rcx+30h]
0x1800496ee  cmp     qword ptr [rax+18h], 7
0x1800496f3  jbe     short loc_1800496F8
0x1800496f5  mov     rax, [rax]
0x1800496f8  mov     rdx, rax
0x1800496fb  mov     rcx, rdi
0x1800496fe  mov     rax, r8
0x180049701  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049706  mov     edi, eax
0x180049708  lea     rcx, [rsp+3E8h+var_108]
  ... truncated ...
```
