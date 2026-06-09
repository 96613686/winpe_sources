# Mso::Experiment::FeatureQueryLogger::LogEventBatch(std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<Mso::Experiment::QueryLog>>> const &,std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<Mso::Experiment::QueryLog>>> const &)

- ea: `0x180060710`
- end: `0x180061b7e`
- name: `?LogEventBatch@FeatureQueryLogger@Experiment@Mso@@AEBAXAEBV?$_Deque_const_iterator@V?$_Deque_val@U?$_Deque_simple_types@UQueryLog@Experiment@Mso@@@std@@@std@@@std@@0@Z`
- size: `5230`
- prototype: ``
- caller_count: `2`
- callee_count: `32`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005fe58`
- `0x180060290`

## callees

- `0x1800125c0`
- `0x1800126a0`
- `0x180012940`
- `0x180012a50`
- `0x180012aa0`
- `0x180012ccc`
- `0x180013080`
- `0x18001397c`
- `0x180017198`
- `0x18002fc5c`
- `0x180031150`
- `0x180031338`
- `0x180037ca4`
- `0x18003a2d4`
- `0x18005cb98`
- `0x18005d2ec`
- `0x180060710`
- `0x18006f500`
- `0x1800ca2f4`
- `0x180137a84`
- `0x180137ad4`
- `0x180137c2c`
- `0x180137d78`
- `0x180137dd0`
- `0x180137ee8`
- `0x180137f38`
- `0x180137f84`
- `0x180137fd4`
- `0x18013804c`
- `0x180138178`
- `0x18056bd00`
- `0x18056dce0`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800613d2`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800613d2`
- `VCRUNTIME140!__std_type_info_compare` at `0x180060a49`
- `VCRUNTIME140!__std_type_info_compare` at `0x180060b96`
- `VCRUNTIME140!__std_type_info_compare` at `0x180060c69`
- `VCRUNTIME140!__std_type_info_compare` at `0x180060d52`
- `VCRUNTIME140!__std_type_info_compare` at `0x180060a49`
- `VCRUNTIME140!__std_type_info_compare` at `0x180060b96`
- `VCRUNTIME140!__std_type_info_compare` at `0x180060c69`
- `VCRUNTIME140!__std_type_info_compare` at `0x180060d52`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180060a67`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180060a67`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800608fb`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800609ed`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180060b42`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180061572`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180061af0`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800608fb`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800609ed`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180060b42`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180061572`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180061af0`
- `api-ms-win-crt-string-l1-1-0!strncpy_s` at `0x18006180d`
- `api-ms-win-crt-string-l1-1-0!strncpy_s` at `0x18006184e`
- `api-ms-win-crt-string-l1-1-0!strncpy_s` at `0x180061889`
- `api-ms-win-crt-string-l1-1-0!strncpy_s` at `0x18006180d`
- `api-ms-win-crt-string-l1-1-0!strncpy_s` at `0x18006184e`
- `api-ms-win-crt-string-l1-1-0!strncpy_s` at `0x180061889`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800608f4`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800609e6`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180060b3b`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18006156b`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180061ae9`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800608f4`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800609e6`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180060b3b`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18006156b`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180061ae9`

## pseudocode

```c
// Hidden C++ exception states: #wind=56
void __fastcall Mso::Experiment::FeatureQueryLogger::LogEventBatch(
        volatile signed __int32 *a1,
        const char *a2,
        __int64 a3)
{
  __int64 v4; // rax
  __int64 v5; // r13
  int v6; // edx
  __int64 *v7; // rbx
  __int64 *v8; // rax
  __int64 v9; // rdx
  void *v10; // rcx
  __int64 *v11; // rbx
  __int64 *v12; // rax
  __int64 v13; // rdx
  void *v14; // rcx
  _QWORD *v15; // rbx
  __int64 v16; // rax
  int v17; // eax
  char v18; // r15
  _BYTE *v19; // rbx
  _QWORD *v20; // rax
  _BYTE *v21; // rcx
  void *v22; // rcx
  __int64 v23; // rax
  int *v24; // rax
  __int64 *v25; // rbx
  __int64 *v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rax
  __int64 *v29; // rax
  __int64 *v30; // rbx
  __int64 *v31; // rax
  __int64 v32; // rdx
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 *v36; // rbx
  __int64 *v37; // rax
  __int64 v38; // rcx
  __int64 v39; // rdx
  __int64 v40; // rcx
  void **v41; // rcx
  const wchar_t *v42; // rdx
  __int64 *v43; // rbx
  __int64 *v44; // rax
  __int64 v45; // rdx
  __int64 *v46; // rbx
  __int64 *v47; // rax
  __int64 v48; // rdx
  __int64 *v49; // rbx
  __int64 *v50; // rax
  __int64 v51; // rdx
  __int64 *v52; // rbx
  __int64 *v53; // rax
  __int64 v54; // rdx
  struct Mso::Experiment::ExperimentationFactory *v55; // rax
  __int64 *v56; // rbx
  __int64 *v57; // rax
  __int64 v58; // rdx
  __int64 *v59; // rbx
  __int64 *v60; // rax
  __int64 v61; // rdx
  __int64 *v62; // rbx
  __int64 *v63; // rax
  __int64 v64; // rdx
  __int64 v65; // rbx
  __int64 *v66; // rbx
  __int64 *v67; // rax
  __int64 v68; // rdx
  __int64 *v69; // rbx
  __int64 *v70; // rax
  __int64 v71; // r8
  __int64 v72; // rdx
  void *v73; // rcx
  __int64 v74; // rax
  char *v75; // rdx
  char *v76; // rcx
  __int64 *v77; // rbx
  __int64 *v78; // rax
  __int64 v79; // rdx
  __int64 v80; // rax
  __int64 v81; // r13
  __int64 v82; // r12
  __m128i si128; // xmm6
  __m128i v84; // xmm7
  double v85; // xmm8_8
  __int64 *v86; // rcx
  int v87; // r15d
  __int64 v88; // rax
  volatile signed __int32 *v89; // rbx
  volatile signed __int32 *v90; // rbx
  void *v91; // rcx
  __int64 v92; // rax
  __int64 v93; // rax
  int v94; // edx
  int v95; // r8d
  int v96; // r9d
  __int64 v97; // rcx
  __int64 v98; // rax
  int v99; // r9d
  __int64 v100; // [rsp+0h] [rbp-3E8h] BYREF
  __int64 v101; // [rsp+50h] [rbp-398h] BYREF
  int v102; // [rsp+58h] [rbp-390h]
  __int64 v103; // [rsp+5Ch] [rbp-38Ch] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+68h] [rbp-380h] BYREF
  const char *v105; // [rsp+70h] [rbp-378h] BYREF
  __int64 v106; // [rsp+78h] [rbp-370h] BYREF
  const char *v107; // [rsp+80h] [rbp-368h] BYREF
  int v108[2]; // [rsp+88h] [rbp-360h] BYREF
  const char *v109; // [rsp+90h] [rbp-358h]
  __int64 v110; // [rsp+98h] [rbp-350h] BYREF
  __int64 v111; // [rsp+A0h] [rbp-348h] BYREF
  __int64 v112; // [rsp+A8h] [rbp-340h] BYREF
  __int64 v113; // [rsp+B0h] [rbp-338h] BYREF
  __int64 v114; // [rsp+B8h] [rbp-330h] BYREF
  __int64 v115; // [rsp+C0h] [rbp-328h] BYREF
  __int64 v116; // [rsp+C8h] [rbp-320h] BYREF
  __int64 v117; // [rsp+D0h] [rbp-318h] BYREF
  __int64 v118; // [rsp+D8h] [rbp-310h] BYREF
  __int64 v119; // [rsp+E0h] [rbp-308h] BYREF
  __int64 v120; // [rsp+E8h] [rbp-300h] BYREF
  __int64 v121; // [rsp+F0h] [rbp-2F8h] BYREF
  __int64 v122; // [rsp+F8h] [rbp-2F0h]
  __int64 *v123; // [rsp+100h] [rbp-2E8h]
  __int64 v124; // [rsp+108h] [rbp-2E0h] BYREF
  __int64 v125; // [rsp+110h] [rbp-2D8h]
  __int64 v126; // [rsp+118h] [rbp-2D0h] BYREF
  __int64 v127; // [rsp+120h] [rbp-2C8h] BYREF
  _QWORD *v128; // [rsp+128h] [rbp-2C0h]
  __int64 v129; // [rsp+130h] [rbp-2B8h]
  _QWORD v130[3]; // [rsp+138h] [rbp-2B0h] BYREF
  __int16 v131; // [rsp+150h] [rbp-298h] BYREF
  int v132; // [rsp+152h] [rbp-296h] BYREF
  __int16 v133; // [rsp+156h] [rbp-292h]
  int v134[4]; // [rsp+158h] [rbp-290h] BYREF
  int v135[4]; // [rsp+168h] [rbp-280h] BYREF
  const std::bad_cast *v136; // [rsp+178h] [rbp-270h] BYREF
  const Mso::Json::Json_exception *v137; // [rsp+180h] [rbp-268h] BYREF
  void *Block[2]; // [rsp+188h] [rbp-260h] BYREF
  __m128i v139; // [rsp+198h] [rbp-250h]
  __int128 v140; // [rsp+1A8h] [rbp-240h] BYREF
  __int128 v141; // [rsp+1B8h] [rbp-230h]
  __int128 v142; // [rsp+1C8h] [rbp-220h] BYREF
  __m128i v143; // [rsp+1D8h] [rbp-210h] BYREF
  void **v144; // [rsp+1F0h] [rbp-1F8h] BYREF
  const char *v145; // [rsp+1F8h] [rbp-1F0h]
  __int64 v146; // [rsp+200h] [rbp-1E8h]
  __int16 v147; // [rsp+208h] [rbp-1E0h]
  __int128 v148; // [rsp+210h] [rbp-1D8h] BYREF
  __int64 v149; // [rsp+220h] [rbp-1C8h]
  unsigned __int64 v150; // [rsp+228h] [rbp-1C0h]
  void **v151; // [rsp+230h] [rbp-1B8h] BYREF
  char Destination[72]; // [rsp+238h] [rbp-1B0h] BYREF
  void *v153[2]; // [rsp+280h] [rbp-168h]
  __m128i v154; // [rsp+290h] [rbp-158h]
  __int16 v155; // [rsp+2A0h] [rbp-148h]
  void **v156; // [rsp+2B0h] [rbp-138h] BYREF
  char v157[8]; // [rsp+2B8h] [rbp-130h] BYREF
  __int64 v158; // [rsp+2C0h] [rbp-128h] BYREF
  _DWORD v159[6]; // [rsp+2E8h] [rbp-100h] BYREF
  __int16 v160; // [rsp+300h] [rbp-E8h]
  void **v161; // [rsp+310h] [rbp-D8h] BYREF
  char v162[68]; // [rsp+318h] [rbp-D0h] BYREF
  int v163; // [rsp+35Ch] [rbp-8Ch]
  __int16 v164; // [rsp+360h] [rbp-88h]

  try
  {
    v105 = a2;
    *(_QWORD *)v108 = a2;
    v87 = 0;
    v102 = 0;
    LODWORD(v103) = _InterlockedExchangeAdd(a1, 1u);
    v128 = (_QWORD *)(a3 + 16);
    v81 = *(_QWORD *)(a3 + 16) - *((_QWORD *)a2 + 2);
    v122 = v81;
    v129 = v81;
    Mso::Json::value::array(&v106, v81);
    v86 = *(__int64 **)a2;
    v123 = *(__int64 **)a2;
    v82 = *((_QWORD *)a2 + 2);
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v84 = _mm_load_si128((const __m128i *)&_xmm);
    v85 = DOUBLE_1000000_0;
    while ( 1 )
    {
      v125 = v82;
      if ( v82 == *v128 )
        break;
      if ( v86 )
        v4 = *v86;
      else
        v4 = 0;
      v5 = *(_QWORD *)(*(_QWORD *)(v4 + 8) + 8 * (v82 & (*(_QWORD *)(v4 + 16) - 1LL)));
      v107 = (const char *)v5;
      Mso::Json::value::object(&v101);
      v6 = -2;
      if ( qword_1806BB470 && *(_DWORD *)qword_1806BB470 == 1 && qword_1806BB348 )
        v6 = (*(__int64 (__fastcall **)(Mso::Experiment::Orchestration::Async::Private *, __int64))(*(_QWORD *)qword_1806BB348
                                                                                                  + 16LL))(
               qword_1806BB348,
               4294967294LL);
      v7 = (__int64 *)Mso::Json::value::value((Mso::Json::value *)&v124, v6);
      *(_OWORD *)Block = 0;
      v139 = 0;
      std::wstring::_Construct<1,wchar_t *>(Block, L"ID", 2);
      v8 = (__int64 *)Mso::Json::value::operator[](&v101, Block);
      if ( v8 != v7 )
      {
        v9 = *v8;
        *v8 = *v7;
        *v7 = v9;
      }
      if ( v139.m128i_i64[1] > 7uLL )
      {
        v10 = Block[0];
        if ( (unsigned __int64)(2 * v139.m128i_i64[1] + 2) >= 0x1000 )
        {
          v10 = (void *)*((_QWORD *)Block[0] - 1);
          if ( (unsigned __int64)((char *)Block[0] - (char *)v10 - 8) > 0x1F )
            _invoke_watson(0, 0, 0, 0, 0);
        }
        free(v10);
      }
      Block[0] = (void *)19937;
      v139 = si128;
      if ( v124 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v124 + 168LL))(v124, 1);
      v124 = 19937;
      v11 = (__int64 *)Mso::Json::value::value(&v126, v5);
      *(_OWORD *)Block = 0;
      v139 = 0;
      std::wstring::_Construct<1,wchar_t *>(Block, L"N", 1);
      v12 = (__int64 *)Mso::Json::value::operator[](&v101, Block);
      if ( v12 != v11 )
      {
        v13 = *v12;
        *v12 = *v11;
        *v11 = v13;
      }
      if ( v139.m128i_i64[1] > 7uLL )
      {
        v14 = Block[0];
        if ( (unsigned __int64)(2 * v139.m128i_i64[1] + 2) >= 0x1000 )
        {
          v14 = (void *)*((_QWORD *)Block[0] - 1);
          if ( (unsigned __int64)((char *)Block[0] - (char *)v14 - 8) > 0x1F )
            _invoke_watson(0, 0, 0, 0, 0);
        }
        free(v14);
      }
      Block[0] = (void *)19937;
      v139 = si128;
      if ( v126 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v126 + 168LL))(v126, 1);
      v126 = 19937;
      v15 = (_QWORD *)(v5 + 32);
      v16 = (***(__int64 (__fastcall ****)(_QWORD))(v5 + 32))(*(_QWORD *)(v5 + 32));
      v17 = __std_type_info_compare(v16 + 8, &qword_1806A3A70);
      try
      {
        if ( v17 )
        {
          v23 = (**(__int64 (__fastcall ***)(_QWORD))*v15)(*v15);
          if ( (unsigned int)__std_type_info_compare(v23 + 8, &qword_1806A3978) )
          {
            v28 = (**(__int64 (__fastcall ***)(_QWORD))*v15)(*v15);
            if ( (unsigned int)__std_type_info_compare(v28 + 8, &qword_1806A3C28) )
            {
              *(_OWORD *)Block = 0;
              v139 = v84;
              LOWORD(Block[0]) = 0;
              v33 = (**(__int64 (__fastcall ***)(_QWORD))*v15)(*v15);
              if ( (unsigned int)__std_type_info_compare(v33 + 8, &qword_1806A39E8) )
              {
                (*(void (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*v15 + 24LL))(*v15, &v140);
                v102 = v87 | 2;
                std::wstring::operator=(Block, &v140);
                std::wstring::~wstring(&v140);
              }
              else
              {
                v34 = Mso::AnyCast<std::string>(v5 + 32);
                std::string::string(&v140, v34);
                v35 = Mso::Experiment::utf8_to_wstr(&v142, &v140);
                std::wstring::operator=(Block, v35);
                std::wstring::~wstring(&v142);
                std::string::~string(&v140);
              }
              if ( v139.m128i_i64[0] > 0x80uLL )
              {
                v142 = 0;
                v143 = v84;
                LOWORD(v142) = 0;
                v41 = Block;
                if ( v139.m128i_i64[1] > 7uLL )
                  v41 = (void **)Block[0];
                if ( (int)Mso::Experiment::GetFlightName(v41, &v142) < 0 )
                {
                  v46 = (__int64 *)Mso::Json::value::value((Mso::Json::value *)&v113, v42);
                  v140 = 0;
                  v141 = 0;
                  std::wstring::_Construct<1,wchar_t *>(&v140, L"V", 1);
                  v47 = (__int64 *)Mso::Json::value::operator[](&v101, &v140);
                  if ( v47 != v46 )
                  {
                    v48 = *v47;
                    *v47 = *v46;
                    *v46 = v48;
                  }
                  std::wstring::~wstring(&v140);
                  if ( v113 )
                    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v113 + 168LL))(v113, 1);
                  v113 = 19937;
                }
                else
                {
                  v43 = (__int64 *)Mso::Json::value::value(&v112, &v142);
                  v140 = 0;
                  v141 = 0;
                  std::wstring::_Construct<1,wchar_t *>(&v140, L"V", 1);
                  v44 = (__int64 *)Mso::Json::value::operator[](&v101, &v140);
                  if ( v44 != v43 )
                  {
                    v45 = *v44;
                    *v44 = *v43;
                    *v43 = v45;
                  }
                  std::wstring::~wstring(&v140);
                  if ( v112 )
                    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v112 + 168LL))(v112, 1);
                  v112 = 19937;
                }
                std::wstring::~wstring(&v142);
              }
              else
              {
                v36 = (__int64 *)Mso::Json::value::value(&v111, Block);
                v142 = 0;
                v143 = 0;
                std::wstring::_Construct<1,wchar_t *>(&v142, L"V", 1);
                v37 = (__int64 *)Mso::Json::value::operator[](&v101, &v142);
                if ( v37 != v36 )
                {
                  v39 = *v37;
                  v38 = *v36;
                  *v37 = *v36;
                  *v36 = v39;
                }
                if ( v143.m128i_i64[1] > 7uLL )
                  std::wstring::_Deallocate_for_capacity(v38, v142);
                *(_QWORD *)&v142 = 19937;
                v143 = si128;
                v40 = v111;
                if ( v111 )
                  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v111 + 168LL))(v111, 1);
                v111 = 19937;
              }
              if ( v139.m128i_i64[1] > 7uLL )
                std::wstring::_Deallocate_for_capacity(v40, Block[0]);
            }
            else
            {
              v29 = (__int64 *)Mso::AnyCast<__int64>(v5 + 32);
              v30 = (__int64 *)Mso::Json::value::value((Mso::Json::value *)&v110, *v29);
              *(_OWORD *)Block = 0;
              v139 = 0;
              std::wstring::_Construct<1,wchar_t *>(Block, L"V", 1);
              v31 = (__int64 *)Mso::Json::value::operator[](&v101, Block);
              if ( v31 != v30 )
              {
                v32 = *v31;
                *v31 = *v30;
                *v30 = v32;
              }
              std::wstring::~wstring(Block);
              if ( v110 )
                (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v110 + 168LL))(v110, 1);
              v110 = 19937;
            }
          }
          else
          {
            v24 = (int *)Mso::AnyCast<int>(v5 + 32);
            v25 = (__int64 *)Mso::Json::value::value((Mso::Json::value *)&v127, *v24);
            *(_OWORD *)Block = 0;
            v139 = 0;
            std::wstring::_Construct<1,wchar_t *>(Block, L"V", 1);
            v26 = (__int64 *)Mso::Json::value::operator[](&v101, Block);
            if ( v26 != v25 )
            {
              v27 = *v26;
              *v26 = *v25;
              *v25 = v27;
            }
            std::wstring::~wstring(Block);
            if ( v127 )
              (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v127 + 168LL))(v127, 1);
            v127 = 19937;
          }
        }
        else
        {
          v18 = *(_BYTE *)Mso::AnyCast<bool>(v5 + 32);
          v19 = malloc(0x10u);
          if ( !v19 )
            ThrowOOM();
          *(_QWORD *)v19 = &Mso::Json::details::_Boolean::`vftable';
          v19[8] = v18;
          v102 |= 1u;
          v130[0] = v19;
          *(_OWORD *)Block = 0;
          v139 = 0;
          std::wstring::_Construct<1,wchar_t *>(Block, L"V", 1);
          v20 = (_QWORD *)Mso::Json::value::operator[](&v101, Block);
          if ( v20 != v130 )
          {
            v21 = (_BYTE *)*v20;
            *v20 = v19;
            v19 = v21;
          }
          if ( v139.m128i_i64[1] > 7uLL )
          {
            v22 = Block[0];
            if ( (unsigned __int64)(2 * v139.m128i_i64[1] + 2) >= 0x1000 )
            {
              v22 = (void *)*((_QWORD *)Block[0] - 1);
              if ( (unsigned __int64)((char *)Block[0] - (char *)v22 - 8) > 0x1F )
                _invoke_watson(0, 0, 0, 0, 0);
            }
            free(v22);
          }
          Block[0] = (void *)19937;
          v139 = si128;
          if ( v19 )
            (*(void (__fastcall **)(_BYTE *, __int64))(*(_QWORD *)v19 + 168LL))(v19, 1);
        }
        v49 = (__int64 *)Mso::Json::value::value((Mso::Json::value *)&v114, *(unsigned __int8 *)(v5 + 48));
        v140 = 0;
        v141 = 0;
        std::wstring::_Construct<1,wchar_t *>(&v140, L"S", 1);
        v50 = (__int64 *)Mso::Json::value::operator[](&v101, &v140);
        if ( v50 != v49 )
        {
          v51 = *v50;
          *v50 = *v49;
          *v49 = v51;
        }
        std::wstring::~wstring(&v140);
        if ( v114 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v114 + 168LL))(v114, 1);
        v114 = 19937;
        v52 = (__int64 *)Mso::Json::value::value((Mso::Json::value *)&v115, *(unsigned __int16 *)(v5 + 50));
        v140 = 0;
        v141 = 0;
        std::wstring::_Construct<1,wchar_t *>(&v140, L"P", 1);
        v53 = (__int64 *)Mso::Json::value::operator[](&v101, &v140);
        if ( v53 != v52 )
        {
          v54 = *v53;
          *v53 = *v52;
          *v52 = v54;
        }
        std::wstring::~wstring(&v140);
        if ( v115 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v115 + 168LL))(v115, 1);
        v115 = 19937;
        v55 = Mso::Experiment::ExperimentationFactory::Instance();
        (***((void (__fastcall ****)(_QWORD, void **, __int64))v55 + 3))(*((_QWORD *)v55 + 3), Block, v5 + 88);
        v56 = (__int64 *)Mso::Json::value::value(&v116, Block);
        v140 = 0;
        v141 = 0;
        std::wstring::_Construct<1,wchar_t *>(&v140, L"T", 1);
        v57 = (__int64 *)Mso::Json::value::operator[](&v101, &v140);
        if ( v57 != v56 )
        {
          v58 = *v57;
          *v57 = *v56;
          *v56 = v58;
        }
        std::wstring::~wstring(&v140);
        if ( v116 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v116 + 168LL))(v116, 1);
        v116 = 19937;
        std::wstring::~wstring(Block);
        v59 = (__int64 *)Mso::Json::value::value(&v117, v5 + 96);
        v140 = 0;
        v141 = 0;
        std::wstring::_Construct<1,wchar_t *>(&v140, L"C", 1);
        v60 = (__int64 *)Mso::Json::value::operator[](&v101, &v140);
        if ( v60 != v59 )
        {
          v61 = *v60;
          *v60 = *v59;
          *v59 = v61;
        }
        std::wstring::~wstring(&v140);
        if ( v117 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v117 + 168LL))(v117, 1);
        v117 = 19937;
        v62 = (__int64 *)Mso::Json::value::value((Mso::Json::value *)&v118, (double)(int)(*(double *)(v5 + 128) * v85));
        v140 = 0;
        v141 = 0;
        std::wstring::_Construct<1,wchar_t *>(&v140, L"Q", 1);
        v63 = (__int64 *)Mso::Json::value::operator[](&v101, &v140);
        if ( v63 != v62 )
        {
          v64 = *v63;
          *v63 = *v62;
          *v62 = v64;
        }
        std::wstring::~wstring(&v140);
        if ( v118 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v118 + 168LL))(v118, 1);
        v118 = 19937;
        v65 = qword_1806BB3E0;
        SystemTimeAsFileTime = 0;
        GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
        if ( *(__int64 *)&SystemTimeAsFileTime < 0 )
          CrashWithRecovery(0x61C8D8u, 0);
        v66 = (__int64 *)Mso::Json::value::value(
                           (Mso::Json::value *)&v119,
                           (*(_QWORD *)&SystemTimeAsFileTime - v65) / 600000000);
        v140 = 0;
        v141 = 0;
        std::wstring::_Construct<1,wchar_t *>(&v140, L"M", 1);
        v67 = (__int64 *)Mso::Json::value::operator[](&v101, &v140);
        if ( v67 != v66 )
        {
          v68 = *v67;
          *v67 = *v66;
          *v66 = v68;
        }
        std::wstring::~wstring(&v140);
        if ( v119 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v119 + 168LL))(v119, 1);
        v119 = 19937;
        v69 = (__int64 *)Mso::Json::value::value((Mso::Json::value *)&v120, *(_DWORD *)(v5 + 136));
        *(_OWORD *)Block = 0;
        v139 = 0;
        std::wstring::_Construct<1,wchar_t *>(Block, L"F", 1);
        v70 = (__int64 *)Mso::Json::value::operator[](&v101, Block);
        if ( v70 != v69 )
        {
          v72 = *v70;
          *v70 = *v69;
          *v69 = v72;
        }
        if ( v139.m128i_i64[1] > 7uLL )
        {
          v73 = Block[0];
          if ( (unsigned __int64)(2 * v139.m128i_i64[1] + 2) >= 0x1000 )
          {
            v73 = (void *)*((_QWORD *)Block[0] - 1);
            if ( (unsigned __int64)((char *)Block[0] - (char *)v73 - 8) > 0x1F )
              _invoke_watson(0, 0, 0, 0, 0);
          }
          free(v73);
        }
        Block[0] = (void *)19937;
        v139 = si128;
        if ( v120 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v120 + 168LL))(v120, 1);
        v120 = 19937;
        v74 = *(_QWORD *)(v5 + 72);
        if ( v74 )
        {
          v75 = (char *)(v5 + 56);
          v76 = (char *)(v5 + 56);
          if ( *(_QWORD *)(v5 + 80) > 0xFu )
          {
            v76 = *(char **)v75;
            v75 = *(char **)v75;
          }
          *(_OWORD *)Block = 0;
          v139 = 0;
          if ( v75 == &v76[v74] )
          {
            v139 = v84;
            LOWORD(Block[0]) = 0;
          }
          else
          {
            std::wstring::_Construct_from_iter<char const *,char const *,unsigned __int64>(
              Block,
              v75,
              v71,
              &v76[v74] - v75);
          }
          v77 = (__int64 *)Mso::Json::value::value(&v121, Block);
          v140 = 0;
          v141 = 0;
          std::wstring::_Construct<1,wchar_t *>(&v140, L"G", 1);
          v78 = (__int64 *)Mso::Json::value::operator[](&v101, &v140);
          if ( v78 != v77 )
          {
            v79 = *v78;
            *v78 = *v77;
            *v77 = v79;
          }
          std::wstring::~wstring(&v140);
          if ( v121 )
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v121 + 168LL))(v121, 1);
          v121 = 19937;
          std::wstring::~wstring(Block);
        }
      }
      catch ( const std::bad_cast *v136 )
      {
        v92 = (*(__int64 (__fastcall **)(const std::bad_cast *))(*(_QWORD *)v136 + 8LL))(v136);
        v144 = &Mso::Diagnostics::ClassifiedStructuredObject<char const *>::`vftable';
        v145 = "Message";
        v146 = v92;
        v147 = 4;
        v148 = 0;
        v149 = 0;
        v150 = 7;
        LOWORD(v148) = 0;
        v105 = "FeatureName";
        v93 = Mso::Diagnostics::ClassifiedStructuredObject<std::wstring>::ClassifiedStructuredObject<std::wstring>(
                &v156,
                &v105,
                v107,
                4);
        v107 = "FeatureQueryLogger::LogEventBatch > Cast Failed";
        Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<std::wstring>,Mso::Diagnostics::ClassifiedStructuredObject<char const *>>(
          (unsigned int)&v100 + 496,
          v94,
          v95,
          v96,
          (__int64)&v107,
          v93,
          (__int64)&v144);
        std::wstring::~wstring(v159);
        std::wstring::~wstring(&v158);
        if ( v150 > 7 )
          std::wstring::_Deallocate_for_capacity(v97, v148);
        if ( v101 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v101 + 168LL))(v101, 1);
        LODWORD(v81) = v129;
        v122 = v129;
        v82 = v125;
        v105 = *(const char **)v108;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        v84 = _mm_load_si128((const __m128i *)&_xmm);
        v85 = DOUBLE_1000000_0;
        goto LABEL_130;
      }
      v80 = Mso::Json::value::operator[](&v106, v82 - *((_QWORD *)v105 + 2));
      Mso::Json::value::operator=(v80, &v101);
      if ( v101 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v101 + 168LL))(v101, 1);
      LODWORD(v81) = v122;
LABEL_130:
      v86 = v123;
      v101 = 19937;
      ++v82;
      v87 = v102;
    }
    v88 = Mso::Json::value::to_string(&v106, &v140);
    v151 = &Mso::Telemetry::DataField<std::wstring>::`vftable';
    *(_OWORD *)v153 = 0;
    v154 = 0;
    *(_OWORD *)v153 = *(_OWORD *)v88;
    v154 = *(__m128i *)(v88 + 16);
    *(_WORD *)v88 = 0;
    *(_QWORD *)(v88 + 16) = 0;
    *(_QWORD *)(v88 + 24) = 7;
    v155 = 4;
    strncpy_s(Destination, 0x41u, "Features", 0xFFFFFFFFFFFFFFFFuLL);
    v156 = &Mso::Telemetry::DataField<unsigned int>::`vftable';
    v159[5] = v81;
    v160 = 4;
    strncpy_s(v157, 0x41u, "Count", 0xFFFFFFFFFFFFFFFFuLL);
    v161 = &Mso::Telemetry::DataField<unsigned int>::`vftable';
    v163 = v103;
    v164 = 4;
    strncpy_s(v162, 0x41u, "Sequence", 0xFFFFFFFFFFFFFFFFuLL);
    v101 = 0x78000201010101LL;
    *(_QWORD *)v108 = &off_1805BCED0;
    v109 = "FeatureQueryBatched";
    BYTE1(v102) = 0;
    v130[1] = v108;
    v130[2] = &v101;
    v131 = (unsigned __int8)v102;
    v132 = v103;
    v133 = BYTE4(v103);
    *(_OWORD *)v134 = 0;
    *(_OWORD *)v135 = 0;
    *(_QWORD *)&v142 = &v161;
    *((_QWORD *)&v142 + 1) = &v156;
    v143.m128i_i64[0] = (__int64)&v151;
    Block[0] = &Mso::Telemetry::Details::CompositeDataField::`vftable';
    Block[1] = &v142;
    v139.m128i_i64[0] = (__int64)&v143.m128i_i64[1];
    LOBYTE(v149) = 0;
    LOBYTE(v103) = 1;
    *(_DWORD *)((char *)&v103 + 2) = 0;
    Mso::Telemetry::Details::SendEventWithContentType(
      (int)v108,
      (int)v134,
      (int)v135,
      (__int64)&v101,
      (__int64)Block,
      (__int64)&v103,
      (__int64)&v131,
      (__int64)&v132,
      (struct Mso::Telemetry::TraceContext::TraceContext *)&v144);
    if ( (_BYTE)v149 )
      std::list<std::pair<Mso::Telemetry::TraceContext::TraceState::Key,Mso::Telemetry::TraceContext::TraceState::Value>>::~list<std::pair<Mso::Telemetry::TraceContext::TraceState::Key,Mso::Telemetry::TraceContext::TraceState::Value>>(&v148);
    v89 = *(volatile signed __int32 **)&v135[2];
    if ( *(_QWORD *)&v135[2] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v135[2] + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v89)(v89);
        if ( _InterlockedExchangeAdd(v89 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v89 + 8LL))(v89);
      }
    }
    v90 = *(volatile signed __int32 **)&v134[2];
    if ( *(_QWORD *)&v134[2] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v134[2] + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v90)(v90);
        if ( _InterlockedExchangeAdd(v90 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v90 + 8LL))(v90);
      }
    }
    if ( v154.m128i_i64[1] > 7uLL )
    {
      v91 = v153[0];
      if ( (unsigned __int64)(2 * v154.m128i_i64[1] + 2) >= 0x1000 )
      {
        v91 = (void *)*((_QWORD *)v153[0] - 1);
        if ( (unsigned __int64)((char *)v153[0] - (char *)v91 - 8) > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v91);
    }
    v153[0] = (void *)19937;
    v154 = si128;
    std::wstring::~wstring(&v140);
    if ( v106 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v106 + 168LL))(v106, 1);
  }
  catch ( const Mso::Json::Json_exception *v137 )
  {
    v98 = (*(__int64 (__fastcall **)(const Mso::Json::Json_exception *))(*(_QWORD *)v137 + 8LL))(v137);
    v144 = &Mso::Diagnostics::ClassifiedStructuredObject<char const *>::`vftable';
    v145 = "Error";
    v146 = v98;
    v147 = 4;
    v148 = 0;
    v149 = 0;
    v150 = 7;
    LOWORD(v148) = 0;
    *(_QWORD *)v108 = "FeatureQueryLogger::LogEventBatch > Json Exception.";
    Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>>(
      593359310,
      1083,
      10,
      v99,
      (__int64)v108,
      (__int64)&v144);
    std::wstring::~wstring(&v148);
  }
}

```

## disassembly

```asm
0x180060710  mov     rax, rsp
0x180060713  push    rbx
0x180060714  push    rsi
0x180060715  push    rdi
0x180060716  push    r12
0x180060718  push    r13
0x18006071a  push    r14
0x18006071c  push    r15
0x18006071e  sub     rsp, 3B0h
0x180060725  movaps  xmmword ptr [rax-48h], xmm6
0x180060729  movaps  xmmword ptr [rax-58h], xmm7
0x18006072d  movaps  xmmword ptr [rax-68h], xmm8
0x180060732  mov     rax, cs:__security_cookie
0x180060739  xor     rax, rsp
0x18006073c  mov     [rsp+3E8h+var_78], rax
0x180060744  mov     rbx, rdx
0x180060747  mov     [rsp+3E8h+var_378], rdx
0x18006074c  mov     qword ptr [rsp+3E8h+var_360], rdx
0x180060754  xor     edi, edi
0x180060756  mov     r15d, edi
0x180060759  mov     [rsp+3E8h+var_390], edi
0x18006075d  lea     esi, [rdi+1]
0x180060760  mov     eax, esi
0x180060762  lock xadd [rcx], eax
0x180060766  dec     eax
0x180060768  add     eax, esi
0x18006076a  mov     dword ptr [rsp+3E8h+var_38C], eax
0x18006076e  lea     rax, [r8+10h]
0x180060772  mov     [rsp+3E8h+var_2C0], rax
0x18006077a  mov     r13, [rax]
0x18006077d  sub     r13, [rdx+10h]
0x180060781  mov     [rsp+3E8h+var_2F0], r13
0x180060789  mov     [rsp+3E8h+var_2B8], r13
0x180060791  mov     rdx, r13
0x180060794  lea     rcx, [rsp+3E8h+var_370]
0x180060799  call    ?array@value@Json@Mso@@SA?AV123@_K@Z; Mso::Json::value::array(unsigned __int64)
0x18006079e  mov     rcx, [rbx]
0x1800607a1  mov     [rsp+3E8h+var_2E8], rcx
0x1800607a9  mov     r12, [rbx+10h]
0x1800607ad  mov     r14d, 4DE1h
0x1800607b3  movdqa  xmm6, cs:__xmm@000000000000000f0000000000000000
0x1800607bb  movdqa  xmm7, cs:__xmm@00000000000000070000000000000000
0x1800607c3  movsd   xmm8, cs:__real@412e848000000000
0x1800607cc  mov     [rsp+3E8h+var_2D8], r12
0x1800607d4  mov     rax, [rsp+3E8h+var_2C0]
0x1800607dc  cmp     r12, [rax]
0x1800607df  jz      loc_180061788
0x1800607e5  test    rcx, rcx
0x1800607e8  jz      short loc_1800607EF
0x1800607ea  mov     rax, [rcx]
0x1800607ed  jmp     short loc_1800607F2
0x1800607ef  mov     rax, rdi
0x1800607f2  mov     rcx, [rax+10h]
0x1800607f6  sub     rcx, rsi
0x1800607f9  and     rcx, r12
0x1800607fc  mov     rax, [rax+8]
0x180060800  mov     r13, [rax+rcx*8]
0x180060804  mov     [rsp+3E8h+var_368], r13
0x18006080c  lea     rcx, [rsp+3E8h+var_398]
0x180060811  call    ?object@value@Json@Mso@@SA?AV123@XZ; Mso::Json::value::object(void)
0x180060816  mov     edx, 0FFFFFFFEh
0x18006081b  mov     rax, cs:qword_1806BB470
0x180060822  test    rax, rax
0x180060825  jz      short loc_180060847
0x180060827  cmp     dword ptr [rax], 1
0x18006082a  jnz     short loc_180060847
0x18006082c  mov     rcx, cs:qword_1806BB348
0x180060833  test    rcx, rcx
0x180060836  jz      short loc_180060847
0x180060838  mov     rax, [rcx]
0x18006083b  mov     rax, [rax+10h]
0x18006083f  call    cs:__guard_dispatch_icall_fptr
0x180060845  mov     edx, eax; int
0x180060847  lea     rcx, [rsp+3E8h+var_2E0]; this
0x18006084f  call    ??0value@Json@Mso@@QEAA@H@Z; Mso::Json::value::value(int)
0x180060854  mov     rbx, rax
0x180060857  xorps   xmm0, xmm0
0x18006085a  movups  xmmword ptr [rsp+3E8h+Block], xmm0
0x180060862  xorps   xmm1, xmm1
0x180060865  movdqu  [rsp+3E8h+var_250], xmm1
0x18006086e  mov     r8d, 2
0x180060874  lea     rdx, aId_0; "ID"
0x18006087b  lea     rcx, [rsp+3E8h+Block]
0x180060883  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x180060888  lea     rdx, [rsp+3E8h+Block]
0x180060890  lea     rcx, [rsp+3E8h+var_398]
0x180060895  call    ??Avalue@Json@Mso@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Mso::Json::value::operator[](std::wstring const &)
0x18006089a  cmp     rax, rbx
0x18006089d  jz      short loc_1800608AB
0x18006089f  mov     rdx, [rax]
0x1800608a2  mov     rcx, [rbx]
0x1800608a5  mov     [rax], rcx
0x1800608a8  mov     [rbx], rdx
0x1800608ab  mov     rax, qword ptr [rsp+3E8h+var_250+8]
0x1800608b3  cmp     rax, 7
0x1800608b7  jbe     short loc_180060901
0x1800608b9  mov     rcx, [rsp+3E8h+Block]; Block
0x1800608c1  mov     rdx, rcx
0x1800608c4  lea     rax, ds:2[rax*2]
0x1800608cc  cmp     rax, 1000h
0x1800608d2  jb      short loc_1800608FB
0x1800608d4  mov     rcx, [rcx-8]
0x1800608d8  sub     rdx, rcx
0x1800608db  lea     rax, [rdx-8]
0x1800608df  cmp     rax, 1Fh
0x1800608e3  jbe     short loc_1800608FB
0x1800608e5  mov     [rsp+3E8h+Reserved], rdi; Reserved
0x1800608ea  xor     r9d, r9d; LineNo
0x1800608ed  xor     r8d, r8d; FileName
0x1800608f0  xor     edx, edx; FunctionName
0x1800608f2  xor     ecx, ecx; Expression
0x1800608f4  call    cs:__imp__invoke_watson
0x1800608fb  call    cs:__imp_free
0x180060901  mov     [rsp+3E8h+Block], r14
0x180060909  movdqu  [rsp+3E8h+var_250], xmm6
0x180060912  mov     rcx, [rsp+3E8h+var_2E0]
0x18006091a  test    rcx, rcx
0x18006091d  jz      short loc_180060931
0x18006091f  mov     rax, [rcx]
0x180060922  mov     edx, esi
0x180060924  mov     rax, [rax+0A8h]
0x18006092b  call    cs:__guard_dispatch_icall_fptr
0x180060931  mov     [rsp+3E8h+var_2E0], r14
0x180060939  mov     rdx, r13
0x18006093c  lea     rcx, [rsp+3E8h+var_2D0]
0x180060944  call    ??0value@Json@Mso@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Mso::Json::value::value(std::wstring const &)
0x180060949  mov     rbx, rax
0x18006094c  xorps   xmm0, xmm0
0x18006094f  movups  xmmword ptr [rsp+3E8h+Block], xmm0
0x180060957  xorps   xmm1, xmm1
0x18006095a  movdqu  [rsp+3E8h+var_250], xmm1
0x180060963  mov     r8, rsi
0x180060966  lea     rdx, aN; "N"
0x18006096d  lea     rcx, [rsp+3E8h+Block]
0x180060975  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x18006097a  lea     rdx, [rsp+3E8h+Block]
0x180060982  lea     rcx, [rsp+3E8h+var_398]
0x180060987  call    ??Avalue@Json@Mso@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Mso::Json::value::operator[](std::wstring const &)
0x18006098c  cmp     rax, rbx
0x18006098f  jz      short loc_18006099D
0x180060991  mov     rdx, [rax]
0x180060994  mov     rcx, [rbx]
0x180060997  mov     [rax], rcx
0x18006099a  mov     [rbx], rdx
0x18006099d  mov     rax, qword ptr [rsp+3E8h+var_250+8]
0x1800609a5  cmp     rax, 7
0x1800609a9  jbe     short loc_1800609F3
0x1800609ab  mov     rcx, [rsp+3E8h+Block]; Block
0x1800609b3  mov     rdx, rcx
0x1800609b6  lea     rax, ds:2[rax*2]
0x1800609be  cmp     rax, 1000h
0x1800609c4  jb      short loc_1800609ED
0x1800609c6  mov     rcx, [rcx-8]
0x1800609ca  sub     rdx, rcx
0x1800609cd  lea     rax, [rdx-8]
0x1800609d1  cmp     rax, 1Fh
0x1800609d5  jbe     short loc_1800609ED
0x1800609d7  mov     [rsp+3E8h+Reserved], rdi; Reserved
0x1800609dc  xor     r9d, r9d; LineNo
0x1800609df  xor     r8d, r8d; FileName
0x1800609e2  xor     edx, edx; FunctionName
0x1800609e4  xor     ecx, ecx; Expression
0x1800609e6  call    cs:__imp__invoke_watson
0x1800609ed  call    cs:__imp_free
0x1800609f3  mov     [rsp+3E8h+Block], r14
0x1800609fb  movdqu  [rsp+3E8h+var_250], xmm6
0x180060a04  mov     rcx, [rsp+3E8h+var_2D0]
0x180060a0c  test    rcx, rcx
0x180060a0f  jz      short loc_180060A23
0x180060a11  mov     rax, [rcx]
0x180060a14  mov     edx, esi
0x180060a16  mov     rax, [rax+0A8h]
0x180060a1d  call    cs:__guard_dispatch_icall_fptr
0x180060a23  mov     [rsp+3E8h+var_2D0], r14
0x180060a2b  lea     rbx, [r13+20h]
0x180060a2f  mov     rcx, [rbx]
0x180060a32  mov     rax, [rcx]
0x180060a35  mov     rax, [rax]
0x180060a38  call    cs:__guard_dispatch_icall_fptr
0x180060a3e  lea     rcx, [rax+8]
0x180060a42  lea     rdx, qword_1806A3A70
0x180060a49  call    cs:__imp___std_type_info_compare
0x180060a4f  test    eax, eax
0x180060a51  jnz     loc_180060B7C
0x180060a57  mov     rcx, rbx
0x180060a5a  call    ??$AnyCast@_N@Mso@@YAAEA_NAEAVAnyType@0@@Z; Mso::AnyCast<bool>(Mso::AnyType &)
0x180060a5f  mov     r15b, [rax]
0x180060a62  mov     ecx, 10h; Size
0x180060a67  call    cs:__imp_malloc
0x180060a6d  mov     rbx, rax
0x180060a70  test    rax, rax
0x180060a73  jz      loc_180061B67
0x180060a79  lea     rax, ??_7_Boolean@details@Json@Mso@@6B@; const Mso::Json::details::_Boolean::`vftable'
0x180060a80  mov     [rbx], rax
0x180060a83  mov     [rbx+8], r15b
0x180060a87  mov     r15d, [rsp+3E8h+var_390]
0x180060a8c  or      r15d, esi
0x180060a8f  mov     [rsp+3E8h+var_390], r15d
0x180060a94  mov     [rsp+3E8h+var_2B0], rbx
0x180060a9c  xorps   xmm0, xmm0
0x180060a9f  movups  xmmword ptr [rsp+3E8h+Block], xmm0
0x180060aa7  xorps   xmm1, xmm1
0x180060aaa  movdqu  [rsp+3E8h+var_250], xmm1
0x180060ab3  mov     r8, rsi
0x180060ab6  lea     rdx, aV; "V"
0x180060abd  lea     rcx, [rsp+3E8h+Block]
0x180060ac5  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x180060aca  lea     rdx, [rsp+3E8h+Block]
0x180060ad2  lea     rcx, [rsp+3E8h+var_398]
0x180060ad7  call    ??Avalue@Json@Mso@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Mso::Json::value::operator[](std::wstring const &)
0x180060adc  lea     rcx, [rsp+3E8h+var_2B0]
0x180060ae4  cmp     rax, rcx
0x180060ae7  jz      short loc_180060AF2
0x180060ae9  mov     rcx, [rax]
0x180060aec  mov     [rax], rbx
0x180060aef  mov     rbx, rcx
0x180060af2  mov     rax, qword ptr [rsp+3E8h+var_250+8]
0x180060afa  cmp     rax, 7
0x180060afe  jbe     short loc_180060B48
0x180060b00  mov     rcx, [rsp+3E8h+Block]; Block
0x180060b08  mov     rdx, rcx
0x180060b0b  lea     rax, ds:2[rax*2]
0x180060b13  cmp     rax, 1000h
0x180060b19  jb      short loc_180060B42
0x180060b1b  mov     rcx, [rcx-8]
0x180060b1f  sub     rdx, rcx
0x180060b22  lea     rax, [rdx-8]
0x180060b26  cmp     rax, 1Fh
0x180060b2a  jbe     short loc_180060B42
0x180060b2c  mov     [rsp+3E8h+Reserved], rdi; Reserved
0x180060b31  xor     r9d, r9d; LineNo
0x180060b34  xor     r8d, r8d; FileName
0x180060b37  xor     edx, edx; FunctionName
0x180060b39  xor     ecx, ecx; Expression
0x180060b3b  call    cs:__imp__invoke_watson
0x180060b42  call    cs:__imp_free
0x180060b48  mov     [rsp+3E8h+Block], r14
0x180060b50  movdqu  [rsp+3E8h+var_250], xmm6
0x180060b59  test    rbx, rbx
0x180060b5c  jz      loc_180061079
0x180060b62  mov     rax, [rbx]
0x180060b65  mov     edx, esi
0x180060b67  mov     rcx, rbx
0x180060b6a  mov     rax, [rax+0A8h]
0x180060b71  call    cs:__guard_dispatch_icall_fptr
0x180060b77  jmp     loc_180061079
0x180060b7c  mov     rcx, [rbx]
0x180060b7f  mov     rax, [rcx]
0x180060b82  mov     rax, [rax]
0x180060b85  call    cs:__guard_dispatch_icall_fptr
0x180060b8b  lea     rcx, [rax+8]
0x180060b8f  lea     rdx, qword_1806A3978
0x180060b96  call    cs:__imp___std_type_info_compare
0x180060b9c  test    eax, eax
0x180060b9e  jnz     loc_180060C4F
0x180060ba4  mov     rcx, rbx
0x180060ba7  call    ??$AnyCast@H@Mso@@YAAEAHAEAVAnyType@0@@Z; Mso::AnyCast<int>(Mso::AnyType &)
0x180060bac  mov     edx, [rax]; int
0x180060bae  lea     rcx, [rsp+3E8h+var_2C8]; this
0x180060bb6  call    ??0value@Json@Mso@@QEAA@H@Z; Mso::Json::value::value(int)
0x180060bbb  mov     rbx, rax
0x180060bbe  xorps   xmm0, xmm0
0x180060bc1  movups  xmmword ptr [rsp+3E8h+Block], xmm0
0x180060bc9  xorps   xmm1, xmm1
0x180060bcc  movdqu  [rsp+3E8h+var_250], xmm1
0x180060bd5  mov     r8, rsi
0x180060bd8  lea     rdx, aV; "V"
0x180060bdf  lea     rcx, [rsp+3E8h+Block]
0x180060be7  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x180060bec  lea     rdx, [rsp+3E8h+Block]
0x180060bf4  lea     rcx, [rsp+3E8h+var_398]
0x180060bf9  call    ??Avalue@Json@Mso@@QEAAAEAV012@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Mso::Json::value::operator[](std::wstring const &)
0x180060bfe  cmp     rax, rbx
0x180060c01  jz      short loc_180060C0F
0x180060c03  mov     rdx, [rax]
0x180060c06  mov     rcx, [rbx]
0x180060c09  mov     [rax], rcx
0x180060c0c  mov     [rbx], rdx
0x180060c0f  lea     rcx, [rsp+3E8h+Block]; void *
0x180060c17  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180060c1c  mov     rcx, [rsp+3E8h+var_2C8]
0x180060c24  test    rcx, rcx
0x180060c27  jz      short loc_180060C42
0x180060c29  nop     dword ptr [rax+00000000h]
0x180060c30  mov     rax, [rcx]
0x180060c33  mov     edx, esi
0x180060c35  mov     rax, [rax+0A8h]
0x180060c3c  call    cs:__guard_dispatch_icall_fptr
0x180060c42  mov     [rsp+3E8h+var_2C8], r14
0x180060c4a  jmp     loc_180061079
0x180060c4f  mov     rcx, [rbx]
0x180060c52  mov     rax, [rcx]
0x180060c55  mov     rax, [rax]
0x180060c58  call    cs:__guard_dispatch_icall_fptr
0x180060c5e  lea     rcx, [rax+8]
0x180060c62  lea     rdx, qword_1806A3C28
0x180060c69  call    cs:__imp___std_type_info_compare
0x180060c6f  test    eax, eax
0x180060c71  jnz     loc_180060D1C
0x180060c77  mov     rcx, rbx
  ... truncated ...
```
