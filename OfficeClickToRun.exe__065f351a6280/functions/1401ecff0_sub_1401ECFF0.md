# sub_1401ECFF0

- ea: `0x1401ecff0`
- end: `0x1401edc83`
- name: `sub_1401ECFF0`
- size: `3219`
- prototype: ``
- caller_count: `2`
- callee_count: `38`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1401ece90`
- `0x1401ecff0`

## callees

- `0x14001aa0c`
- `0x14001c280`
- `0x14001e270`
- `0x14001e4f4`
- `0x140021ab8`
- `0x1400255c0`
- `0x140026f64`
- `0x1400279b0`
- `0x140028300`
- `0x140028cc8`
- `0x140028ed8`
- `0x1400292f8`
- `0x140029440`
- `0x140029790`
- `0x14002bda4`
- `0x140044404`
- `0x140045380`
- `0x140056308`
- `0x140057bb0`
- `0x14005b0e0`
- `0x14009e200`
- `0x1400a0650`
- `0x1400dc390`
- `0x14012f5f8`
- `0x140141978`
- `0x1401ecff0`
- `0x1401edda4`
- `0x1401ee210`
- `0x1401ee238`
- `0x1401ee358`
- `0x1401eef50`
- `0x14020dbdc`
- `0x1402a00bc`
- `0x14034c744`
- `0x1403e1680`
- `0x1403e60fd`
- `0x14053855c`
- `0x1407b0e20`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x1401ed1fb`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1401ed390`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1401ed3d9`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1401ed422`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1401ed4d9`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1401edbc0`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1401edbfd`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1401edc3a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1401edc77`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1401ed1fb`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1401ed390`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1401ed3d9`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1401ed422`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1401ed4d9`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1401edbc0`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1401edbfd`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1401edc3a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1401edc77`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1401ed6b2`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1401ed6cf`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1401ed6e5`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1401ed6fb`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1401ed711`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1401ed6b2`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1401ed6cf`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1401ed6e5`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1401ed6fb`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1401ed711`
- `ole32!CLSIDFromString` at `0x1401ed17c`
- `ole32!CLSIDFromString` at `0x1401ed17c`

## string_xrefs

- `0x1401ed8c0`: `TaskFactory::CreateTask`
- `0x1401edafc`: `TaskFactory::CreateTask`
- `0x1401ed239`: `TaskFactory::CreateTask - Attempting to create task. (Task type: %s, GUID: %s)`
- `0x1401ed322`: `TaskFactory::CreateTask - Successfully created task. (Task type: %s, GUID: %s)`
- `0x1401edb64`: `Invalid taskTypeString`
- `0x1401ed9a0`: `Invalid Task type. {'TaskType':'%s'}`

## pseudocode

```c
_QWORD *__fastcall sub_1401ECFF0(__int128 *a1, _QWORD *a2, __int64 a3, __int64 a4, char a5)
{
  int v8; // r14d
  __m128i si128; // xmm6
  char v10; // bl
  _QWORD *v11; // rdx
  __int64 v12; // rax
  const OLECHAR *v13; // rcx
  HRESULT v14; // ebx
  __int64 v15; // rax
  int v16; // r9d
  char *v17; // rcx
  __int128 *v18; // rax
  __int128 *v19; // rax
  int v20; // ecx
  __int64 v21; // rax
  __int64 v22; // rax
  char *i; // rbx
  _QWORD *v24; // rax
  char v25; // al
  __int64 v26; // r8
  int v27; // r9d
  __m128i v28; // xmm6
  __int128 *v29; // rax
  __int128 *v30; // rax
  void *v31; // rcx
  __m128i v32; // xmm0
  OLECHAR *v33; // rcx
  void *v34; // rcx
  __int64 v36; // rax
  __int64 v37; // r8
  void *v38; // rcx
  int v39; // ebx
  __int64 v40; // rdx
  __int64 v41; // rdx
  LPCOLESTR *v42; // rax
  _QWORD *v43; // rax
  __int128 *v44; // rax
  _QWORD *v45; // rax
  __int64 v46; // rdi
  LPCOLESTR *v47; // rcx
  LPCOLESTR *v48; // rcx
  LPCOLESTR *v49; // rcx
  LPCOLESTR *v50; // rcx
  LPCOLESTR *v51; // [rsp+48h] [rbp-C0h] BYREF
  GUID v52; // [rsp+58h] [rbp-B0h] BYREF
  __int128 *v53; // [rsp+68h] [rbp-A0h]
  __int64 v54; // [rsp+70h] [rbp-98h] BYREF
  __int128 *v55; // [rsp+78h] [rbp-90h] BYREF
  int v56; // [rsp+80h] [rbp-88h] BYREF
  int v57; // [rsp+84h] [rbp-84h]
  __m128i v58; // [rsp+88h] [rbp-80h] BYREF
  __int64 v59; // [rsp+98h] [rbp-70h]
  _QWORD *v60; // [rsp+A0h] [rbp-68h]
  __int128 v61; // [rsp+A8h] [rbp-60h] BYREF
  __m128i v62; // [rsp+B8h] [rbp-50h]
  __int128 v63; // [rsp+C8h] [rbp-40h] BYREF
  __m128i v64; // [rsp+D8h] [rbp-30h]
  LPCOLESTR lpsz[2]; // [rsp+E8h] [rbp-20h] BYREF
  __m128i v66; // [rsp+F8h] [rbp-10h]
  __int128 v67; // [rsp+108h] [rbp+0h] BYREF
  __m128i v68; // [rsp+118h] [rbp+10h]
  void **v69; // [rsp+128h] [rbp+20h] BYREF
  __int128 v70; // [rsp+130h] [rbp+28h] BYREF
  __m128i v71; // [rsp+140h] [rbp+38h]
  __int64 v72; // [rsp+150h] [rbp+48h]
  int v73; // [rsp+158h] [rbp+50h]
  int v74; // [rsp+160h] [rbp+58h]
  __int128 v75; // [rsp+168h] [rbp+60h] BYREF
  __m128i v76; // [rsp+178h] [rbp+70h]
  __int128 v77; // [rsp+188h] [rbp+80h] BYREF
  __m128i v78; // [rsp+198h] [rbp+90h]
  __int128 v79; // [rsp+1A8h] [rbp+A0h] BYREF
  __m128i v80; // [rsp+1B8h] [rbp+B0h]
  __int128 v81; // [rsp+1C8h] [rbp+C0h] BYREF
  __m128i v82; // [rsp+1D8h] [rbp+D0h]
  __int128 v83; // [rsp+1E8h] [rbp+E0h] BYREF
  __m128i v84; // [rsp+1F8h] [rbp+F0h]
  _QWORD *v85[3]; // [rsp+208h] [rbp+100h] BYREF
  unsigned __int64 v86; // [rsp+220h] [rbp+118h]
  GUID pclsid; // [rsp+228h] [rbp+120h] BYREF
  _QWORD v88[7]; // [rsp+238h] [rbp+130h] BYREF
  _QWORD *v89; // [rsp+270h] [rbp+168h]
  void **pExceptionObject; // [rsp+278h] [rbp+170h] BYREF
  __int64 (__fastcall **v91)(); // [rsp+280h] [rbp+178h]
  __int64 v92; // [rsp+288h] [rbp+180h] BYREF
  int v93; // [rsp+290h] [rbp+188h]
  int v94; // [rsp+298h] [rbp+190h]
  __int64 v95; // [rsp+2A0h] [rbp+198h]
  __int64 v96; // [rsp+2A8h] [rbp+1A0h] BYREF
  int v97; // [rsp+2B0h] [rbp+1A8h]
  int v98; // [rsp+2B8h] [rbp+1B0h]
  _QWORD v99[4]; // [rsp+2C8h] [rbp+1C0h] BYREF
  _QWORD v100[100]; // [rsp+2E8h] [rbp+1E0h] BYREF

  v8 = (int)a1;
  v55 = a1;
  v60 = a2;
  v57 = 0;
  v67 = 0;
  si128 = _mm_load_si128((const __m128i *)&xmmword_14082E430);
  v68 = si128;
  LOWORD(v67) = 0;
  sub_1401EE238(a3, &v67);
  v56 = 51;
  v88[0] = ___7___Func_impl_no_alloc_V_lambda_1___1__CreateTask_TaskFactory_C2R__AEAA_AV__shared_ptr_VTask_C2R___std__AEBVOXmlElement__AEBV56__N_Z__NPEB_WW4TaskType_4__std__6B_;
  v88[1] = &v67;
  v88[2] = &v56;
  v89 = v88;
  v10 = sub_1401EE358((__int64)v88);
  if ( v89 )
  {
    v11 = v88;
    LOBYTE(v11) = v89 != v88;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v89 + 32LL))(v89, v11);
  }
  if ( !v10 )
  {
    v44 = &v67;
    if ( v68.m128i_i64[1] > 7uLL )
      v44 = (__int128 *)v67;
    v55 = v44;
    v45 = (_QWORD *)sub_1400DC390(v85, L"Invalid Task type. {'TaskType':'%s'}", &v55);
    if ( v45[3] > 7u )
      v45 = (_QWORD *)*v45;
    *(_QWORD *)&v83 = &Mso::Logging::StructuredObject<wchar_t const *,1>::`vftable';
    *((_QWORD *)&v83 + 1) = L"ContextData";
    v84.m128i_i64[0] = (__int64)v45;
    v84.m128i_i16[4] = 0;
    v63 = 0;
    v64 = si128;
    LOWORD(v63) = 0;
    v77 = 0;
    v78 = si128;
    LOWORD(v77) = 0;
    v79 = 0;
    v80 = si128;
    LOWORD(v79) = 0;
    v81 = 0;
    v82 = si128;
    LOWORD(v81) = 0;
    LODWORD(v51) = 44;
    v46 = sub_1402A00BC(&pExceptionObject, &v51, &v81, &v79, &v77, &v63);
    v69 = &C2R::CommonTelemetry::`vftable';
    v70 = 0;
    v71 = si128;
    LOWORD(v70) = 0;
    if ( sub_140057BB0(3462427, 0x3AEu, 0xAu, 0) )
    {
      *(_QWORD *)&v52.Data1 = &v69;
      *(_QWORD *)v52.Data4 = v46;
      v53 = &v83;
      *(_QWORD *)&v61 = &Mso::Logging::CompositeStructuredTrace::`vftable';
      *((_QWORD *)&v61 + 1) = &v52;
      v62.m128i_i64[0] = (__int64)&v54;
      sub_140141978(3462427, 942, 10, 0, (__int64)L"TaskFactory::CreateTask", (__int64)&v61);
    }
    sub_140045380(&v70);
    sub_14034C744(&pExceptionObject);
    sub_140045380(&v81);
    sub_140045380(&v79);
    sub_140045380(&v77);
    sub_140045380(&v63);
    sub_140045380(v85);
    sub_14053855C(&pExceptionObject, 44, L"Invalid taskTypeString");
    throw (OException *)&pExceptionObject;
  }
  *(_OWORD *)lpsz = 0;
  v66 = si128;
  LOWORD(lpsz[0]) = 0;
  sub_140021AB8((__int64)&v63, L"id");
  sub_140028ED8(a3, (char *)&v63, lpsz);
  if ( v64.m128i_i64[1] > 7uLL )
    sub_14001E270((_QWORD *)v63, 2 * v64.m128i_i64[1] + 2);
  v12 = sub_140028CC8(&v63, L"{%s}", lpsz);
  sub_14001AA0C(lpsz, v12);
  if ( v64.m128i_i64[1] > 7uLL )
    sub_14001E270((_QWORD *)v63, 2 * v64.m128i_i64[1] + 2);
  v13 = (const OLECHAR *)lpsz;
  if ( v66.m128i_i64[1] > 7uLL )
    v13 = lpsz[0];
  v14 = CLSIDFromString(v13, &pclsid);
  if ( v14 < 0 )
  {
    v42 = lpsz;
    if ( v66.m128i_i64[1] > 7uLL )
      v42 = (LPCOLESTR *)lpsz[0];
    v51 = v42;
    v43 = (_QWORD *)sub_1400DC390(v85, L"Invalid Guid string {'ID':'%s'}", &v51);
    if ( v43[3] > 7u )
      v43 = (_QWORD *)*v43;
    *(_QWORD *)&v63 = &Mso::Logging::StructuredObject<wchar_t const *,1>::`vftable';
    *((_QWORD *)&v63 + 1) = L"ContextData";
    v64.m128i_i64[0] = (__int64)v43;
    v64.m128i_i16[4] = 0;
    v83 = 0;
    v84 = si128;
    LOWORD(v83) = 0;
    v81 = 0;
    v82 = si128;
    LOWORD(v81) = 0;
    v79 = 0;
    v80 = si128;
    LOWORD(v79) = 0;
    v77 = 0;
    v78 = si128;
    LOWORD(v77) = 0;
    pExceptionObject = &C2R::ErrorTelemetry::`vftable';
    LODWORD(v91) = v14;
    sub_14001C280(&v92, &v77);
    sub_14001C280(&v96, &v79);
    sub_14001C280(v99, &v81);
    sub_14001C280(v100, &v83);
    v69 = &C2R::CommonTelemetry::`vftable';
    v70 = 0;
    v71 = si128;
    LOWORD(v70) = 0;
    if ( sub_140057BB0(3702924, 0x3AEu, 0xAu, 0) )
    {
      *(_QWORD *)&v52.Data1 = &v69;
      *(_QWORD *)v52.Data4 = &pExceptionObject;
      v53 = &v63;
      *(_QWORD *)&v61 = &Mso::Logging::CompositeStructuredTrace::`vftable';
      *((_QWORD *)&v61 + 1) = &v52;
      v62.m128i_i64[0] = (__int64)&v54;
      sub_140141978(3702924, 942, 10, 0, (__int64)L"TaskFactory::CreateTask", (__int64)&v61);
    }
    sub_140045380(&v70);
    sub_140045380(v100);
    sub_140045380(v99);
    sub_140045380(&v96);
    sub_140045380(&v92);
    if ( v78.m128i_i64[1] > 7uLL )
    {
      *(_QWORD *)&v52.Data1 = 2 * v78.m128i_i64[1] + 2;
      v47 = (LPCOLESTR *)v77;
      v51 = (LPCOLESTR *)v77;
      if ( *(_QWORD *)&v52.Data1 >= 0x1000u )
      {
        sub_14020DBDC(&v51, &v52);
        v47 = v51;
      }
      free(v47);
    }
    if ( v80.m128i_i64[1] > 7uLL )
    {
      *(_QWORD *)&v52.Data1 = 2 * v80.m128i_i64[1] + 2;
      v48 = (LPCOLESTR *)v79;
      v51 = (LPCOLESTR *)v79;
      if ( *(_QWORD *)&v52.Data1 >= 0x1000u )
      {
        sub_14020DBDC(&v51, &v52);
        v48 = v51;
      }
      free(v48);
    }
    if ( v82.m128i_i64[1] > 7uLL )
    {
      *(_QWORD *)&v52.Data1 = 2 * v82.m128i_i64[1] + 2;
      v49 = (LPCOLESTR *)v81;
      v51 = (LPCOLESTR *)v81;
      if ( *(_QWORD *)&v52.Data1 >= 0x1000u )
      {
        sub_14020DBDC(&v51, &v52);
        v49 = v51;
      }
      free(v49);
    }
    if ( v84.m128i_i64[1] > 7uLL )
    {
      *(_QWORD *)&v52.Data1 = 2 * v84.m128i_i64[1] + 2;
      v50 = (LPCOLESTR *)v83;
      v51 = (LPCOLESTR *)v83;
      if ( *(_QWORD *)&v52.Data1 >= 0x1000u )
      {
        sub_14020DBDC(&v51, &v52);
        v50 = v51;
      }
      free(v50);
    }
    if ( v86 > 7 )
      sub_14001E270(v85[0], 2 * v86 + 2);
    v8 = (int)v55;
  }
  v75 = 0;
  v76 = si128;
  LOWORD(v75) = 0;
  v15 = sub_140028300(v85, &pclsid, 0);
  sub_14001AA0C(&v75, v15);
  if ( v86 > 7 )
  {
    v17 = (char *)v85[0];
    if ( 2 * v86 + 2 >= 0x1000 )
    {
      v17 = (char *)*(v85[0] - 1);
      if ( (unsigned __int64)((char *)v85[0] - v17 - 8) > 0x1F )
        invoke_watson(0, 0, 0, 0, 0);
    }
    free(v17);
  }
  v18 = &v75;
  if ( v76.m128i_i64[1] > 7uLL )
    v18 = (__int128 *)v75;
  *(_QWORD *)&v52.Data1 = v18;
  v19 = &v67;
  if ( v68.m128i_i64[1] > 7uLL )
    v19 = (__int128 *)v67;
  v55 = v19;
  sub_140056308(
    3462429,
    14,
    100,
    v16,
    (__int64)L"TaskFactory::CreateTask - Attempting to create task. (Task type: %s, GUID: %s)",
    &v55,
    &v52);
  v52 = pclsid;
  sub_14009E200(v20, (_DWORD)a2, (unsigned int)&v56, (unsigned int)&v52, a4);
  v57 = 1;
  v21 = sub_1401EE210();
  v22 = sub_1401EDDA4(v21, &v56);
  sub_14005B0E0(&v58, v22 + 48);
  v57 = 3;
  for ( i = (char *)v58.m128i_i64[0]; i != (char *)v58.m128i_i64[1]; i += 32 )
  {
    v61 = 0;
    v62 = si128;
    LOWORD(v61) = 0;
    sub_140028ED8(a3, i, &v61);
    if ( v62.m128i_i64[0] )
    {
      v36 = sub_1400255C0(*a2 + 240LL, &v52, i);
      sub_1400279B0((char *)(*(_QWORD *)v36 + 64LL), (char *)&v61, v37);
    }
    if ( v62.m128i_i64[1] > 7uLL )
    {
      v38 = (void *)v61;
      if ( (unsigned __int64)(2 * v62.m128i_i64[1] + 2) >= 0x1000 )
      {
        v38 = *(void **)(v61 - 8);
        if ( (unsigned __int64)(v61 - (_QWORD)v38 - 8) > 0x1F )
          invoke_watson(0, 0, 0, 0, 0);
      }
      free(v38);
    }
  }
  if ( a5 )
    sub_14012F5F8(*a2, 0);
  v24 = sub_140026F64(&v52, a2);
  v25 = sub_1400A0650(v24);
  v28 = _mm_load_si128((const __m128i *)&xmmword_14084AF40);
  if ( v25 )
  {
    *(_QWORD *)&v61 = off_14082EF40;
    *((_QWORD *)&v61 + 1) = 0;
    v62.m128i_i32[0] = 147;
    v62.m128i_i32[2] = 167;
    sub_1401EEF50(a3, &v61, v26);
    v39 = 0;
    if ( (int)sub_140029440((__int64)&v61, v40) > 0 )
    {
      do
      {
        v69 = (void **)off_14082DEC0;
        *(_QWORD *)&v70 = off_14082DEA8;
        *((_QWORD *)&v70 + 1) = 0;
        v71.m128i_i32[0] = 147;
        v71.m128i_i32[2] = 165;
        v72 = 0;
        v73 = 147;
        v74 = 166;
        sub_1400292F8((__int64)&v61, v39, (__int64)&v69);
        v91 = off_14082DEA8;
        v92 = 0;
        v93 = 147;
        v94 = 165;
        v95 = 0;
        LODWORD(v96) = 147;
        v97 = 166;
        pExceptionObject = &OXmlElement::`vftable';
        v98 = 164;
        sub_140029790((__int64)&pExceptionObject, (__int64 *)&v69);
        sub_1401ECFF0(v8, (unsigned int)&v52, (unsigned int)&pExceptionObject, (_DWORD)a2, a5);
        if ( *(_QWORD *)v52.Data4 )
          sub_14001E4F4(*(std::_Ref_count_base **)v52.Data4);
        v52 = (GUID)v28;
        pExceptionObject = (void **)off_14082DEC0;
        if ( v95 )
          sub_14002BDA4(v95);
        v91 = off_14082DEA8;
        if ( v92 )
          sub_14002BDA4(v92);
        v69 = (void **)off_14082DEC0;
        if ( v72 )
          sub_14002BDA4(v72);
        *(_QWORD *)&v70 = off_14082DEA8;
        if ( *((_QWORD *)&v70 + 1) )
          sub_14002BDA4(*((_QWORD *)&v70 + 1));
        ++v39;
      }
      while ( v39 < (int)sub_140029440((__int64)&v61, v41) );
    }
    *(_QWORD *)&v61 = off_14082EF40;
    if ( *((_QWORD *)&v61 + 1) )
      sub_14002BDA4(*((_QWORD *)&v61 + 1));
  }
  v29 = &v75;
  if ( v76.m128i_i64[1] > 7uLL )
    v29 = (__int128 *)v75;
  *(_QWORD *)&v52.Data1 = v29;
  v30 = &v67;
  if ( v68.m128i_i64[1] > 7uLL )
    v30 = (__int128 *)v67;
  v55 = v30;
  sub_140056308(
    3462430,
    14,
    100,
    v27,
    (__int64)L"TaskFactory::CreateTask - Successfully created task. (Task type: %s, GUID: %s)",
    &v55,
    &v52);
  sub_140044404(&v58);
  v58 = v28;
  v59 = 19937;
  if ( v76.m128i_i64[1] > 7uLL )
  {
    v31 = (void *)v75;
    if ( (unsigned __int64)(2 * v76.m128i_i64[1] + 2) >= 0x1000 )
    {
      v31 = *(void **)(v75 - 8);
      if ( (unsigned __int64)(v75 - (_QWORD)v31 - 8) > 0x1F )
        invoke_watson(0, 0, 0, 0, 0);
    }
    free(v31);
  }
  *(_QWORD *)&v75 = 19937;
  v32 = _mm_load_si128((const __m128i *)&xmmword_14082E580);
  v76 = v32;
  if ( v66.m128i_i64[1] > 7uLL )
  {
    v33 = (OLECHAR *)lpsz[0];
    if ( (unsigned __int64)(2 * v66.m128i_i64[1] + 2) >= 0x1000 )
    {
      v33 = (OLECHAR *)*((_QWORD *)lpsz[0] - 1);
      if ( (unsigned __int64)((char *)lpsz[0] - (char *)v33 - 8) > 0x1F )
        invoke_watson(0, 0, 0, 0, 0);
    }
    free(v33);
    v32 = _mm_load_si128((const __m128i *)&xmmword_14082E580);
  }
  lpsz[0] = (LPCOLESTR)19937;
  v66 = v32;
  if ( v68.m128i_i64[1] > 7uLL )
  {
    v34 = (void *)v67;
    if ( (unsigned __int64)(2 * v68.m128i_i64[1] + 2) >= 0x1000 )
    {
      v34 = *(void **)(v67 - 8);
      if ( (unsigned __int64)(v67 - (_QWORD)v34 - 8) > 0x1F )
        invoke_watson(0, 0, 0, 0, 0);
    }
    free(v34);
  }
  return a2;
}

```

## disassembly

```asm
0x1401ecff0  mov     rax, rsp
0x1401ecff3  push    rbp
0x1401ecff4  push    rbx
0x1401ecff5  push    rsi
0x1401ecff6  push    rdi
0x1401ecff7  push    r12
0x1401ecff9  push    r13
0x1401ecffb  push    r14
0x1401ecffd  push    r15
0x1401ecfff  lea     rbp, [rax-568h]
0x1401ed006  sub     rsp, 628h
0x1401ed00d  movaps  xmmword ptr [rax-58h], xmm6
0x1401ed011  mov     rax, cs:__security_cookie
0x1401ed018  xor     rax, rsp
0x1401ed01b  mov     [rbp+560h+var_60], rax
0x1401ed022  mov     r12, r9
0x1401ed025  mov     r15, r8
0x1401ed028  mov     rsi, rdx
0x1401ed02b  mov     r14, rcx
0x1401ed02e  mov     qword ptr [rsp+660h+var_5F0], rcx
0x1401ed033  mov     [rbp+560h+var_5C8], rdx
0x1401ed037  mov     r13b, [rbp+560h+arg_20]
0x1401ed03e  xor     edi, edi
0x1401ed040  mov     [rsp+660h+var_5E4], edi
0x1401ed044  xorps   xmm0, xmm0
0x1401ed047  movups  [rbp+560h+var_560], xmm0
0x1401ed04b  movdqa  xmm6, cs:xmmword_14082E430
0x1401ed053  movdqu  [rbp+560h+var_550], xmm6
0x1401ed058  mov     word ptr [rbp+560h+var_560], di
0x1401ed05c  lea     rdx, [rbp+560h+var_560]
0x1401ed060  mov     rcx, r8
0x1401ed063  call    sub_1401EE238
0x1401ed068  mov     [rsp+660h+var_5E8], 33h ; '3'
0x1401ed070  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_1_@?1??CreateTask@TaskFactory@C2R@@AEAA?AV?$shared_ptr@VTask@C2R@@@std@@AEBVOXmlElement@@AEBV56@_N@Z@_NPEB_WW4TaskType@4@@std@@6B@; const std::_Func_impl_no_alloc<`C2R::TaskFactory::CreateTask(OXmlElement const &,std::shared_ptr<C2R::Task> const &,bool)'::`2'::_lambda_1_,bool,wchar_t const *,C2R::TaskType>::`vftable'
0x1401ed077  mov     [rbp+560h+var_430], rax
0x1401ed07e  lea     rax, [rbp+560h+var_560]
0x1401ed082  mov     [rbp+560h+var_428], rax
0x1401ed089  lea     rax, [rsp+660h+var_5E8]
0x1401ed08e  mov     [rbp+560h+var_420], rax
0x1401ed095  lea     rax, [rbp+560h+var_430]
0x1401ed09c  mov     [rbp+560h+var_3F8], rax
0x1401ed0a3  lea     rcx, [rbp+560h+var_430]
0x1401ed0aa  call    sub_1401EE358
0x1401ed0af  mov     bl, al
0x1401ed0b1  mov     rcx, [rbp+560h+var_3F8]
0x1401ed0b8  test    rcx, rcx
0x1401ed0bb  jz      short loc_1401ED0D7
0x1401ed0bd  mov     rax, [rcx]
0x1401ed0c0  lea     rdx, [rbp+560h+var_430]
0x1401ed0c7  cmp     rcx, rdx
0x1401ed0ca  setnz   dl
0x1401ed0cd  mov     rax, [rax+20h]
0x1401ed0d1  call    cs:__guard_dispatch_icall_fptr
0x1401ed0d7  test    bl, bl
0x1401ed0d9  jz      loc_1401ED984
0x1401ed0df  xorps   xmm0, xmm0
0x1401ed0e2  movups  xmmword ptr [rbp+560h+lpsz], xmm0
0x1401ed0e6  movdqu  [rbp+560h+var_570], xmm6
0x1401ed0eb  mov     word ptr [rbp+560h+lpsz], di
0x1401ed0ef  lea     rdx, aId_4; "id"
0x1401ed0f6  lea     rcx, [rbp+560h+var_5A0]
0x1401ed0fa  call    sub_140021AB8
0x1401ed0ff  lea     r8, [rbp+560h+lpsz]
0x1401ed103  lea     rdx, [rbp+560h+var_5A0]
0x1401ed107  mov     rcx, r15
0x1401ed10a  call    sub_140028ED8
0x1401ed10f  mov     rdx, qword ptr [rbp+560h+var_590+8]
0x1401ed113  mov     edi, 7
0x1401ed118  cmp     rdx, rdi
0x1401ed11b  jbe     short loc_1401ED12E
0x1401ed11d  lea     rdx, ds:2[rdx*2]
0x1401ed125  mov     rcx, qword ptr [rbp+560h+var_5A0]
0x1401ed129  call    sub_14001E270
0x1401ed12e  lea     r8, [rbp+560h+lpsz]
0x1401ed132  lea     rdx, aS; "{%s}"
0x1401ed139  lea     rcx, [rbp+560h+var_5A0]
0x1401ed13d  call    sub_140028CC8
0x1401ed142  mov     rdx, rax
0x1401ed145  lea     rcx, [rbp+560h+lpsz]
0x1401ed149  call    sub_14001AA0C
0x1401ed14e  mov     rdx, qword ptr [rbp+560h+var_590+8]
0x1401ed152  cmp     rdx, rdi
0x1401ed155  jbe     short loc_1401ED168
0x1401ed157  lea     rdx, ds:2[rdx*2]
0x1401ed15f  mov     rcx, qword ptr [rbp+560h+var_5A0]
0x1401ed163  call    sub_14001E270
0x1401ed168  lea     rcx, [rbp+560h+lpsz]
0x1401ed16c  cmp     qword ptr [rbp+560h+var_570+8], rdi
0x1401ed170  cmova   rcx, [rbp+560h+lpsz]; lpsz
0x1401ed175  lea     rdx, [rbp+560h+pclsid]; pclsid
0x1401ed17c  call    cs:CLSIDFromString
0x1401ed182  mov     ebx, eax
0x1401ed184  test    eax, eax
0x1401ed186  js      loc_1401ED727
0x1401ed18c  xorps   xmm0, xmm0
0x1401ed18f  movups  [rbp+560h+var_500], xmm0
0x1401ed193  movdqu  [rbp+560h+var_4F0], xmm6
0x1401ed198  xor     ebx, ebx
0x1401ed19a  mov     word ptr [rbp+560h+var_500], bx
0x1401ed19e  xor     r8d, r8d
0x1401ed1a1  lea     rdx, [rbp+560h+pclsid]
0x1401ed1a8  lea     rcx, [rbp+560h+var_460]
0x1401ed1af  call    sub_140028300
0x1401ed1b4  mov     rdx, rax
0x1401ed1b7  lea     rcx, [rbp+560h+var_500]
0x1401ed1bb  call    sub_14001AA0C
0x1401ed1c0  mov     rax, [rbp+560h+var_448]
0x1401ed1c7  cmp     rax, rdi
0x1401ed1ca  jbe     short loc_1401ED201
0x1401ed1cc  mov     rcx, [rbp+560h+var_460]
0x1401ed1d3  mov     rdx, rcx
0x1401ed1d6  lea     rax, ds:2[rax*2]
0x1401ed1de  cmp     rax, 1000h
0x1401ed1e4  jb      short loc_1401ED1FB
0x1401ed1e6  mov     rcx, [rcx-8]; Block
0x1401ed1ea  sub     rdx, rcx
0x1401ed1ed  lea     rax, [rdx-8]
0x1401ed1f1  cmp     rax, 1Fh
0x1401ed1f5  ja      loc_1401ED6A3
0x1401ed1fb  call    cs:__imp_free
0x1401ed201  lea     rax, [rbp+560h+var_500]
0x1401ed205  cmp     qword ptr [rbp+560h+var_4F0+8], rdi
0x1401ed209  cmova   rax, qword ptr [rbp+560h+var_500]
0x1401ed20e  mov     qword ptr [rsp+660h+var_618+8], rax
0x1401ed213  lea     rax, [rbp+560h+var_560]
0x1401ed217  cmp     qword ptr [rbp+560h+var_550+8], rdi
0x1401ed21b  cmova   rax, qword ptr [rbp+560h+var_560]
0x1401ed220  mov     qword ptr [rsp+660h+var_5F0], rax
0x1401ed225  lea     rax, [rsp+660h+var_618+8]
0x1401ed22a  mov     [rsp+30h], rax
0x1401ed22f  lea     rax, [rsp+660h+var_5F0]
0x1401ed234  mov     [rsp+660h+var_638], rax
0x1401ed239  lea     rax, aTaskfactoryCre_0; "TaskFactory::CreateTask - Attempting to"...
0x1401ed240  mov     [rsp+660h+Reserved], rax
0x1401ed245  mov     edx, 0Eh
0x1401ed24a  mov     ecx, 34D51Dh
0x1401ed24f  lea     r8d, [rdx+56h]
0x1401ed253  call    sub_140056308
0x1401ed258  movaps  xmm0, xmmword ptr [rbp+560h+pclsid.Data1]
0x1401ed25f  movdqa  [rsp+660h+var_618+8], xmm0
0x1401ed265  mov     [rsp+660h+Reserved], r12
0x1401ed26a  lea     r9, [rsp+660h+var_618+8]
0x1401ed26f  lea     r8, [rsp+660h+var_5E8]
0x1401ed274  mov     rdx, rsi
0x1401ed277  call    sub_14009E200
0x1401ed27c  mov     [rsp+660h+var_5E4], 1
0x1401ed284  call    sub_1401EE210
0x1401ed289  lea     rdx, [rsp+660h+var_5E8]
0x1401ed28e  mov     rcx, rax
0x1401ed291  call    sub_1401EDDA4
0x1401ed296  lea     rdx, [rax+30h]
0x1401ed29a  lea     rcx, [rbp+560h+var_5E0]
0x1401ed29e  call    sub_14005B0E0
0x1401ed2a3  mov     [rsp+660h+var_5E4], 3
0x1401ed2ab  mov     rbx, qword ptr [rbp+560h+var_5E0]
0x1401ed2af  xor     r12d, r12d
0x1401ed2b2  cmp     rbx, qword ptr [rbp+560h+var_5E0+8]
0x1401ed2b6  jnz     loc_1401ED456
0x1401ed2bc  test    r13b, r13b
0x1401ed2bf  jnz     loc_1401ED718
0x1401ed2c5  mov     rdx, rsi
0x1401ed2c8  lea     rcx, [rsp+660h+var_618+8]
0x1401ed2cd  call    sub_140026F64
0x1401ed2d2  mov     rcx, rax; void *
0x1401ed2d5  call    sub_1400A0650
0x1401ed2da  movdqa  xmm6, cs:xmmword_14084AF40
0x1401ed2e2  test    al, al
0x1401ed2e4  jnz     loc_1401ED4E8
0x1401ed2ea  lea     rax, [rbp+560h+var_500]
0x1401ed2ee  cmp     qword ptr [rbp+560h+var_4F0+8], rdi
0x1401ed2f2  cmova   rax, qword ptr [rbp+560h+var_500]
0x1401ed2f7  mov     qword ptr [rsp+660h+var_618+8], rax
0x1401ed2fc  lea     rax, [rbp+560h+var_560]
0x1401ed300  cmp     qword ptr [rbp+560h+var_550+8], rdi
0x1401ed304  cmova   rax, qword ptr [rbp+560h+var_560]
0x1401ed309  mov     qword ptr [rsp+660h+var_5F0], rax
0x1401ed30e  lea     rax, [rsp+660h+var_618+8]
0x1401ed313  mov     [rsp+30h], rax
0x1401ed318  lea     rax, [rsp+660h+var_5F0]
0x1401ed31d  mov     [rsp+660h+var_638], rax
0x1401ed322  lea     rax, aTaskfactoryCre_1; "TaskFactory::CreateTask - Successfully "...
0x1401ed329  mov     [rsp+660h+Reserved], rax
0x1401ed32e  mov     edx, 0Eh
0x1401ed333  mov     ecx, 34D51Eh
0x1401ed338  lea     r8d, [rdx+56h]
0x1401ed33c  call    sub_140056308
0x1401ed341  lea     rcx, [rbp+560h+var_5E0]
0x1401ed345  call    sub_140044404
0x1401ed34a  movdqu  [rbp+560h+var_5E0], xmm6
0x1401ed34f  mov     r14d, 4DE1h
0x1401ed355  mov     [rbp+560h+var_5D0], r14
0x1401ed359  mov     rax, qword ptr [rbp+560h+var_4F0+8]
0x1401ed35d  mov     ebx, 1000h
0x1401ed362  cmp     rax, rdi
0x1401ed365  jbe     short loc_1401ED396
0x1401ed367  mov     rcx, qword ptr [rbp+560h+var_500]
0x1401ed36b  mov     rdx, rcx
0x1401ed36e  lea     rax, ds:2[rax*2]
0x1401ed376  cmp     rax, rbx
0x1401ed379  jb      short loc_1401ED390
0x1401ed37b  mov     rcx, [rcx-8]; Block
0x1401ed37f  sub     rdx, rcx
0x1401ed382  lea     rax, [rdx-8]
0x1401ed386  cmp     rax, 1Fh
0x1401ed38a  ja      loc_1401ED6C0
0x1401ed390  call    cs:__imp_free
0x1401ed396  mov     qword ptr [rbp+560h+var_500], r14
0x1401ed39a  movdqa  xmm0, cs:xmmword_14082E580
0x1401ed3a2  movdqu  [rbp+560h+var_4F0], xmm0
0x1401ed3a7  mov     rax, qword ptr [rbp+560h+var_570+8]
0x1401ed3ab  cmp     rax, rdi
0x1401ed3ae  jbe     short loc_1401ED3E7
0x1401ed3b0  mov     rcx, [rbp+560h+lpsz]
0x1401ed3b4  mov     rdx, rcx
0x1401ed3b7  lea     rax, ds:2[rax*2]
0x1401ed3bf  cmp     rax, rbx
0x1401ed3c2  jb      short loc_1401ED3D9
0x1401ed3c4  mov     rcx, [rcx-8]; Block
0x1401ed3c8  sub     rdx, rcx
0x1401ed3cb  lea     rax, [rdx-8]
0x1401ed3cf  cmp     rax, 1Fh
0x1401ed3d3  ja      loc_1401ED6D6
0x1401ed3d9  call    cs:__imp_free
0x1401ed3df  movdqa  xmm0, cs:xmmword_14082E580
0x1401ed3e7  mov     [rbp+560h+lpsz], r14
0x1401ed3eb  movdqu  [rbp+560h+var_570], xmm0
0x1401ed3f0  mov     rax, qword ptr [rbp+560h+var_550+8]
0x1401ed3f4  cmp     rax, rdi
0x1401ed3f7  jbe     short loc_1401ED428
0x1401ed3f9  mov     rcx, qword ptr [rbp+560h+var_560]
0x1401ed3fd  mov     rdx, rcx
0x1401ed400  lea     rax, ds:2[rax*2]
0x1401ed408  cmp     rax, rbx
0x1401ed40b  jb      short loc_1401ED422
0x1401ed40d  mov     rcx, [rcx-8]; Block
0x1401ed411  sub     rdx, rcx
0x1401ed414  lea     rax, [rdx-8]
0x1401ed418  cmp     rax, 1Fh
0x1401ed41c  ja      loc_1401ED6EC
0x1401ed422  call    cs:__imp_free
0x1401ed428  mov     rax, rsi
0x1401ed42b  mov     rcx, [rbp+560h+var_60]
0x1401ed432  xor     rcx, rsp; StackCookie
0x1401ed435  call    __security_check_cookie
0x1401ed43a  movaps  xmm6, [rsp+660h+var_58+8]
0x1401ed442  add     rsp, 628h
0x1401ed449  pop     r15
0x1401ed44b  pop     r14
0x1401ed44d  pop     r13
0x1401ed44f  pop     r12
0x1401ed451  pop     rdi
0x1401ed452  pop     rsi
0x1401ed453  pop     rbx
0x1401ed454  pop     rbp
0x1401ed455  retn
0x1401ed456  xorps   xmm0, xmm0
0x1401ed459  movups  [rbp+560h+var_5C0], xmm0
0x1401ed45d  movdqu  [rbp+560h+var_5B0], xmm6
0x1401ed462  mov     word ptr [rbp+560h+var_5C0], r12w
0x1401ed467  lea     r8, [rbp+560h+var_5C0]
0x1401ed46b  mov     rdx, rbx
0x1401ed46e  mov     rcx, r15
0x1401ed471  call    sub_140028ED8
0x1401ed476  cmp     qword ptr [rbp+560h+var_5B0], r12
0x1401ed47a  jbe     short loc_1401ED4A4
0x1401ed47c  mov     rcx, [rsi]
0x1401ed47f  add     rcx, 0F0h
0x1401ed486  mov     r8, rbx
0x1401ed489  lea     rdx, [rsp+660h+var_618+8]
0x1401ed48e  call    sub_1400255C0
0x1401ed493  mov     rcx, [rax]
0x1401ed496  add     rcx, 40h ; '@'; void *
0x1401ed49a  lea     rdx, [rbp+560h+var_5C0]
0x1401ed49e  call    sub_1400279B0
0x1401ed4a3  nop
0x1401ed4a4  mov     rax, qword ptr [rbp+560h+var_5B0+8]
0x1401ed4a8  cmp     rax, rdi
0x1401ed4ab  jbe     short loc_1401ED4DF
0x1401ed4ad  mov     rcx, qword ptr [rbp+560h+var_5C0]
0x1401ed4b1  mov     rdx, rcx
0x1401ed4b4  lea     rax, ds:2[rax*2]
0x1401ed4bc  cmp     rax, 1000h
0x1401ed4c2  jb      short loc_1401ED4D9
0x1401ed4c4  mov     rcx, [rcx-8]; Block
0x1401ed4c8  sub     rdx, rcx
0x1401ed4cb  lea     rax, [rdx-8]
0x1401ed4cf  cmp     rax, 1Fh
0x1401ed4d3  ja      loc_1401ED702
0x1401ed4d9  call    cs:__imp_free
0x1401ed4df  add     rbx, 20h ; ' '
0x1401ed4e3  jmp     loc_1401ED2B2
0x1401ed4e8  lea     rax, off_14082EF40
0x1401ed4ef  mov     qword ptr [rbp+560h+var_5C0], rax
0x1401ed4f3  mov     qword ptr [rbp+560h+var_5C0+8], r12
0x1401ed4f7  mov     dword ptr [rbp+560h+var_5B0], 93h
0x1401ed4fe  mov     dword ptr [rbp+560h+var_5B0+8], 0A7h
0x1401ed505  lea     rdx, [rbp+560h+var_5C0]
0x1401ed509  mov     rcx, r15
0x1401ed50c  call    sub_1401EEF50
0x1401ed511  mov     ebx, r12d
  ... truncated ...
```
