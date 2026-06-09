# win_musl::consumption::ZipDeinterleaver::AddFile(std::basic_string<char,std::char_traits<char>,std::allocator<char>,_STL70> const &,__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0010,__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0011,win_scope::scope<win_musl::ZipFileSender *,win_scope::const_policies<win_scope::shared_policies>>)

- ea: `0x180013d80`
- end: `0x180014d9f`
- name: `?AddFile@ZipDeinterleaver@consumption@win_musl@@QEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@W4__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0010@@U__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0011@@V?$scope@PEAVZipFileSender@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@Z`
- size: `4127`
- prototype: `void __fastcall(__int64, __int64, int, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `37`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180015250`

## callees

- `0x1800016b0`
- `0x1800037a8`
- `0x18000405c`
- `0x18000d53c`
- `0x18000fb88`
- `0x18000fbbc`
- `0x180012fa0`
- `0x180013d80`
- `0x180015114`
- `0x1800172f4`
- `0x180017dd0`
- `0x180017e6c`
- `0x180018c2c`
- `0x18001a810`
- `0x18001c5d0`
- `0x18001ca9c`
- `0x18001e280`
- `0x18001ee8c`
- `0x18002f13c`
- `0x18003268c`
- `0x180034c90`
- `0x1800460f0`
- `0x1800514d4`
- `0x1800517a0`
- `0x1800654b0`
- `0x18007dbe0`
- `0x18009c21c`
- `0x1800ca570`
- `0x1800cce54`
- `0x1800cd38c`
- `0x1800cdb60`
- `0x1800d04d8`
- `0x1800e81b8`
- `0x180110854`
- `0x180110898`
- `0x180112eec`
- `0x180117740`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180013f1b`
- `msvcrt!memcpy_s` at `0x180014259`
- `msvcrt!memcpy_s` at `0x18001473a`
- `msvcrt!memcpy_s` at `0x180014913`
- `msvcrt!memcpy_s` at `0x180013f1b`
- `msvcrt!memcpy_s` at `0x180014259`
- `msvcrt!memcpy_s` at `0x18001473a`
- `msvcrt!memcpy_s` at `0x180014913`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013e01`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013e01`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180013e73`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180013e73`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001417a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014493`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001417a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014493`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013dec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013dec`

## string_xrefs

- `0x180013e6c`: `/[Content_Types].xml`
- `0x180014d0e`: `Compression method %{method} is unknown`

## pseudocode

```c
void __fastcall win_musl::consumption::ZipDeinterleaver::AddFile(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 a4,
        _QWORD *a5)
{
  __int64 v9; // r13
  bool v10; // dl
  win_dox *v11; // rcx
  const WCHAR *v12; // r8
  LPCWCH *v13; // rcx
  __int64 v14; // rdx
  unsigned __int64 v15; // rdx
  unsigned __int64 v16; // rsi
  LPCWCH *v17; // r8
  void **v18; // rcx
  void **v19; // rcx
  void **v20; // rcx
  void **v21; // rcx
  void **v22; // rax
  __int16 v23; // r8
  __int64 v24; // rdx
  __int64 v25; // rax
  void **v26; // r10
  unsigned __int64 v27; // r9
  _QWORD *v28; // rcx
  bool v29; // cf
  _QWORD *v30; // rax
  unsigned __int64 v31; // rcx
  void **v32; // r8
  bool v33; // cf
  void *v34; // rax
  int v35; // edx
  const char *v36; // r8
  unsigned int v37; // r9d
  __int64 v38; // rsi
  __m128i v39; // xmm1
  win_scope::counted_strong_weak_base *v40; // rcx
  __int64 v41; // rcx
  __int64 v42; // r12
  bool v43; // zf
  unsigned __int64 v44; // rdx
  unsigned __int64 v45; // r13
  const void *p_Source; // r8
  void **v47; // rcx
  void **v48; // rcx
  __int64 v49; // rdx
  __int64 v50; // r8
  __int64 v51; // r8
  volatile signed __int32 *v52; // rcx
  win_scope::counted_strong_weak_base *v53; // rdx
  int v54; // eax
  __int64 v55; // r8
  unsigned int i; // ecx
  __int64 v57; // rbx
  win_musl::Formatter *v58; // rax
  struct win_musl::TStringEllipseBase *v59; // rax
  __int64 v60; // rcx
  __int64 v61; // rdx
  _QWORD *v62; // r12
  unsigned __int64 v63; // r13
  LPCWCH *v64; // r8
  unsigned __int64 v65; // rdx
  _QWORD *v66; // rcx
  __int64 v67; // rax
  __int64 v68; // rcx
  __int64 v69; // rdx
  unsigned int v70; // edx
  unsigned __int64 v71; // rdx
  unsigned __int64 v72; // r13
  void **v73; // r8
  void **v74; // rcx
  void **v75; // rcx
  __int64 v76; // rcx
  __int64 v77; // rdx
  __int64 v78; // rdx
  __int64 v79; // rax
  __int64 v80; // rdx
  __int64 v81; // rax
  __int64 v82; // r11
  __int64 v83; // r8
  __int64 v84; // r10
  __int64 v85; // rdx
  __int64 v86; // r8
  __int64 v87; // rax
  __int64 v88; // r10
  __int64 v89; // r11
  LPCWCH *v90; // r8
  __int64 v91; // rax
  __int64 v92; // r8
  __int64 v93; // rax
  __int64 v94; // rdx
  __int64 v95; // r10
  LPCWCH *v96; // r8
  __int64 v97; // rbx
  win_musl::Formatter *v98; // rax
  struct win_musl::TStringEllipseBase *v99; // rax
  int v100; // [rsp+48h] [rbp-C0h] BYREF
  win_scope::counted_strong_weak_base *v101[2]; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v102[2]; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v103; // [rsp+78h] [rbp-90h] BYREF
  __m128i v104; // [rsp+88h] [rbp-80h] BYREF
  __int64 v105; // [rsp+98h] [rbp-70h] BYREF
  win_scope::counted_strong_weak_base **v106; // [rsp+A0h] [rbp-68h]
  __int64 v107; // [rsp+A8h] [rbp-60h] BYREF
  __int64 *v108; // [rsp+B0h] [rbp-58h]
  __int64 v109; // [rsp+B8h] [rbp-50h]
  __int64 v110; // [rsp+C0h] [rbp-48h]
  _QWORD *v111; // [rsp+C8h] [rbp-40h]
  char v112[8]; // [rsp+D0h] [rbp-38h] BYREF
  void *Destination[2]; // [rsp+D8h] [rbp-30h] BYREF
  unsigned __int64 v114; // [rsp+E8h] [rbp-20h]
  unsigned __int64 v115; // [rsp+F0h] [rbp-18h]
  char v116[8]; // [rsp+F8h] [rbp-10h] BYREF
  void *v117[2]; // [rsp+100h] [rbp-8h] BYREF
  unsigned __int64 v118; // [rsp+110h] [rbp+8h]
  unsigned __int64 v119; // [rsp+118h] [rbp+10h]
  int v120; // [rsp+120h] [rbp+18h] BYREF
  char v121[8]; // [rsp+128h] [rbp+20h] BYREF
  LPCWCH lpString2[2]; // [rsp+130h] [rbp+28h] BYREF
  unsigned __int64 v123; // [rsp+140h] [rbp+38h]
  unsigned __int64 v124; // [rsp+148h] [rbp+40h]
  char v125[8]; // [rsp+150h] [rbp+48h]
  char v126[8]; // [rsp+158h] [rbp+50h] BYREF
  void *Block; // [rsp+160h] [rbp+58h]
  __int64 v128; // [rsp+170h] [rbp+68h]
  unsigned __int64 v129; // [rsp+178h] [rbp+70h]
  char v130[8]; // [rsp+180h] [rbp+78h] BYREF
  void *v131[2]; // [rsp+188h] [rbp+80h] BYREF
  unsigned __int64 v132; // [rsp+198h] [rbp+90h]
  unsigned __int64 v133; // [rsp+1A0h] [rbp+98h]
  __int128 v134; // [rsp+1A8h] [rbp+A0h]
  __int64 v135; // [rsp+1B8h] [rbp+B0h] BYREF
  __int64 v136; // [rsp+1C0h] [rbp+B8h]
  __int64 v137; // [rsp+1C8h] [rbp+C0h]
  __int64 v138; // [rsp+1D0h] [rbp+C8h]
  char pExceptionObject[8]; // [rsp+1D8h] [rbp+D0h] BYREF
  void *Source; // [rsp+1E0h] [rbp+D8h] BYREF
  unsigned __int64 v141; // [rsp+1F0h] [rbp+E8h]
  unsigned __int64 v142; // [rsp+1F8h] [rbp+F0h]
  __int128 v143; // [rsp+200h] [rbp+F8h]
  _BYTE v144[160]; // [rsp+278h] [rbp+170h] BYREF

  v110 = -2;
  v103 = a4;
  v111 = a5;
  v100 = 0;
  v9 = a1 + 56;
  v107 = a1 + 56;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 56));
  v11 = (win_dox *)*(unsigned int *)(v9 + 44);
  *(_DWORD *)(v9 + 44) = (_DWORD)v11 + 1;
  if ( !(_DWORD)v11 )
    *(_DWORD *)(v9 + 40) = GetCurrentThreadId();
  LOBYTE(v11) = *(_BYTE *)(a1 + 156);
  win_dox::ThrowIfFailed(v11, v10);
  win_musl::Unicode8ToUnicodeWide(v126, a2);
  if ( a3 == 2 )
  {
    win_musl::consumption::ZipDeinterleaver::PartNameFromZipPart((__int64)&v120, a2);
    if ( *(_DWORD *)(a1 + 152) == 1 && v120 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x99u,
        0x80080201,
        (struct win_musl::TStringEllipseBase *)L"An APPX package must not contain interleaved parts.");
      throw (SplException::THResultException *)pExceptionObject;
    }
    v12 = (const WCHAR *)lpString2;
    if ( v124 >= 8 )
      v12 = lpString2[0];
    if ( CompareStringOrdinal(L"/[Content_Types].xml", -1, v12, -1, 1) == 2 )
      goto LABEL_12;
    v13 = lpString2;
    if ( v124 >= 8 )
      v13 = (LPCWCH *)lpString2[0];
    if ( (unsigned __int8)win_dox::IsValidPartUriInternal(v13) )
    {
LABEL_12:
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0 )
      {
        v91 = win_musl::StringOfZipDeflateOption(*(unsigned int *)(a4 + 8));
        v93 = win_musl::StringOfZipFileCompressionMethod(*(unsigned int *)(a4 + 12), v91, v92);
        v96 = lpString2;
        if ( v124 >= 8 )
          v96 = (LPCWCH *)lpString2[0];
        WPP_SF_SSDSS(*(_QWORD *)(v95 + 56), (__int64)v96, v125[0], v93, v94);
      }
      v15 = 7;
      v115 = 7;
      v114 = 0;
      LOWORD(Destination[0]) = 0;
      v16 = v123;
      if ( v123 > 0x7FFFFFFFFFFFFFFELL )
        std::_String_base::_Xlen();
      if ( v123 > 7 )
      {
        std::wstring::_Copy(v112, v123, v114);
        v15 = v115;
        if ( !v16 )
        {
LABEL_24:
          v100 = 5;
          v20 = Destination;
          if ( v15 >= 8 )
            v20 = (void **)Destination[0];
          v21 = (void **)((char *)v20 + 2 * v114);
          v22 = Destination;
          if ( v15 >= 8 )
            v22 = (void **)Destination[0];
          while ( v22 != v21 )
          {
            v23 = *(_WORD *)v22;
            if ( (unsigned __int16)(*(_WORD *)v22 - 97) <= 0x19u )
              v23 -= 32;
            *(_WORD *)v22 = v23;
            v22 = (void **)((char *)v22 + 2);
          }
          v109 = a1 + 32;
          v24 = *(_QWORD *)(a1 + 40);
          v25 = *(_QWORD *)(v24 + 8);
          while ( !*(_BYTE *)(v25 + 81) )
          {
            v26 = Destination;
            if ( v115 >= 8 )
              v26 = (void **)Destination[0];
            v27 = v114;
            if ( *(_QWORD *)(v25 + 48) < v114 )
              v27 = *(_QWORD *)(v25 + 48);
            v28 = (_QWORD *)(v25 + 32);
            if ( *(_QWORD *)(v25 + 56) >= 8u )
              v28 = (_QWORD *)*v28;
            while ( v27 )
            {
              v29 = *(_WORD *)v28 < *(_WORD *)v26;
              if ( *(_WORD *)v28 != *(_WORD *)v26 )
                goto LABEL_43;
              v28 = (_QWORD *)((char *)v28 + 2);
              v26 = (void **)((char *)v26 + 2);
              --v27;
            }
            v29 = *(_QWORD *)(v25 + 48) < v114;
LABEL_43:
            if ( v29 )
            {
              v25 = *(_QWORD *)(v25 + 16);
            }
            else
            {
              v24 = v25;
              v25 = *(_QWORD *)v25;
            }
          }
          if ( v24 == *(_QWORD *)(a1 + 40) )
            goto LABEL_56;
          v30 = (_QWORD *)(v24 + 32);
          if ( *(_QWORD *)(v24 + 56) >= 8u )
            v30 = (_QWORD *)*v30;
          v31 = *(_QWORD *)(v24 + 48);
          if ( v114 < v31 )
            v31 = v114;
          v32 = Destination;
          if ( v115 >= 8 )
            v32 = (void **)Destination[0];
          while ( v31 )
          {
            v33 = *(_WORD *)v32 < *(_WORD *)v30;
            if ( *(_WORD *)v32 != *(_WORD *)v30 )
              goto LABEL_132;
            v32 = (void **)((char *)v32 + 2);
            v30 = (_QWORD *)((char *)v30 + 2);
            --v31;
          }
          v33 = v114 < *(_QWORD *)(v24 + 48);
LABEL_132:
          if ( v33 )
LABEL_56:
            v24 = *(_QWORD *)(a1 + 40);
          v104 = 0;
          if ( v24 != *(_QWORD *)(a1 + 40) )
          {
            v39 = 0;
            v104 = 0;
            v40 = *(win_scope::counted_strong_weak_base **)(v24 + 64);
            if ( v40 )
            {
              win_scope::counted_strong_weak_base::AddRef(v40);
              v104.m128i_i64[0] = v41;
              v104.m128i_i64[1] = v24;
              v39 = _mm_load_si128(&v104);
            }
            v104 = v39;
            v38 = _mm_srli_si128(v39, 8).m128i_u64[0];
            v42 = v39.m128i_i64[0];
            goto LABEL_93;
          }
          v34 = operator new(0xE0u, (const struct std::nothrow_t *)&std::nothrow);
          v38 = (__int64)v34;
          if ( !v34 )
            SplException::RealThrowFromHR((SplException *)0x8007000ELL, v35, v36, v37);
          v105 = (__int64)v34;
          *(_OWORD *)v102 = 0;
          v60 = *(_QWORD *)(a1 + 112);
          if ( v60 )
          {
            v61 = *(_QWORD *)(a1 + 120);
            if ( !_InterlockedExchangeAdd((volatile signed __int32 *)(v60 + 8), 1u) )
              _InterlockedAdd((volatile signed __int32 *)(v60 + 12), 1u);
            v102[0] = v60;
            v102[1] = v61;
          }
          v108 = v102;
          win_scope::intrusive_shared_weak<win_scope::scope<win_musl::consumption::PieceReceiver *,win_scope::const_policies<win_scope::shared_policies>>>::intrusive_shared_weak<win_scope::scope<win_musl::consumption::PieceReceiver *,win_scope::const_policies<win_scope::shared_policies>>>(v34);
          *(_QWORD *)v38 = &win_musl::consumption::ZipConsumptionPart::`vftable';
          *(_QWORD *)(v38 + 48) = 7;
          v62 = (_QWORD *)(v38 + 24);
          *(_QWORD *)(v38 + 40) = 0;
          *(_WORD *)(v38 + 24) = 0;
          v63 = v123;
          if ( (char *)(v38 + 16) == v121 )
          {
            std::wstring::erase(v38 + 16, v123, -1);
            std::wstring::erase(v38 + 16, 0, 0);
            goto LABEL_152;
          }
          if ( v123 > 0x7FFFFFFFFFFFFFFELL )
            std::_String_base::_Xlen();
          if ( *(_QWORD *)(v38 + 48) < v123 )
          {
            std::wstring::_Copy(v38 + 16, v123, *(_QWORD *)(v38 + 40));
            if ( !v63 )
              goto LABEL_152;
          }
          else if ( !v123 )
          {
            if ( *(_QWORD *)(v38 + 48) >= 8u )
              v62 = (_QWORD *)*v62;
            *(_QWORD *)(v38 + 40) = 0;
            *(_WORD *)v62 = 0;
LABEL_152:
            *(_DWORD *)(v38 + 56) = -1;
            *(_QWORD *)(v38 + 64) = 1;
            *(_QWORD *)(v38 + 72) = -1;
            v67 = std::_Tree<std::_Tmap_traits<unsigned int,win_scope::scope<win_musl::consumption::ZipConsumptionPart::Piece *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>>>>,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,win_scope::scope<win_musl::consumption::ZipConsumptionPart::Piece *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>>>>>>,0>>::_Buynode();
            *(_QWORD *)(v38 + 88) = v67;
            *(_BYTE *)(v67 + 49) = 1;
            *(_QWORD *)(*(_QWORD *)(v38 + 88) + 8LL) = *(_QWORD *)(v38 + 88);
            **(_QWORD **)(v38 + 88) = *(_QWORD *)(v38 + 88);
            *(_QWORD *)(*(_QWORD *)(v38 + 88) + 16LL) = *(_QWORD *)(v38 + 88);
            *(_QWORD *)(v38 + 96) = 0;
            *(_QWORD *)(v38 + 104) = 0;
            *(_QWORD *)(v38 + 112) = 0;
            v68 = v102[0];
            if ( v102[0] )
            {
              v69 = v102[1];
              if ( !_InterlockedExchangeAdd((volatile signed __int32 *)(v102[0] + 8), 1u) )
                _InterlockedAdd((volatile signed __int32 *)(v68 + 12), 1u);
              *(_QWORD *)(v38 + 104) = v68;
              *(_QWORD *)(v38 + 112) = v69;
            }
            *(_DWORD *)(v38 + 120) = 0;
            *(_BYTE *)(v38 + 124) = 0;
            *(_QWORD *)(v38 + 136) = std::list<win_scope::scope<win_musl::consumption::ZipConsumptionByteSender *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>>>>>::_Buynode();
            *(_QWORD *)(v38 + 144) = 0;
            *(_WORD *)(v38 + 152) = 0;
            win_musl::CriticalSection::CriticalSection((win_musl::CriticalSection *)(v38 + 160), v70);
            *(_BYTE *)(v38 + 216) = 0;
            if ( v102[1] && v102[0] )
            {
              win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(v102);
              *(_OWORD *)v102 = 0;
            }
            v105 = v38;
            v42 = *(_QWORD *)(v38 + 8);
            if ( !v42 )
            {
              win_scope::close_delete::close<win_musl::CallingThread>(&v105);
              win_scope::report_policy_throw::report_init_failure();
            }
            if ( !_InterlockedExchangeAdd((volatile signed __int32 *)(v42 + 8), 1u) )
              _InterlockedAdd((volatile signed __int32 *)(v42 + 12), 1u);
            v104.m128i_i64[0] = v42;
            v104.m128i_i64[1] = v38;
            v106 = v101;
            *(_OWORD *)v101 = 0;
            if ( !_InterlockedExchangeAdd((volatile signed __int32 *)(v42 + 8), 1u) )
              _InterlockedAdd((volatile signed __int32 *)(v42 + 12), 1u);
            v101[0] = (win_scope::counted_strong_weak_base *)v42;
            v101[1] = (win_scope::counted_strong_weak_base *)v38;
            v108 = (__int64 *)v101;
            v71 = 7;
            v119 = 7;
            v118 = 0;
            LOWORD(v117[0]) = 0;
            v72 = v114;
            if ( v114 > 0x7FFFFFFFFFFFFFFELL )
              std::_String_base::_Xlen();
            if ( v114 > 7 )
            {
              std::wstring::_Copy(v116, v114, 0);
              v71 = v119;
              if ( !v72 )
                goto LABEL_174;
            }
            else if ( !v114 )
            {
              v118 = 0;
              LOWORD(v117[0]) = 0;
              goto LABEL_174;
            }
            v73 = Destination;
            if ( v115 >= 8 )
              v73 = (void **)Destination[0];
            v74 = v117;
            if ( v71 >= 8 )
              v74 = (void **)v117[0];
            memcpy_s(v74, 2 * v71, v73, 2 * v72);
            v75 = v117;
            if ( v119 >= 8 )
              v75 = (void **)v117[0];
            v118 = v72;
            *((_WORD *)v75 + v72) = 0;
LABEL_174:
            v106 = (win_scope::counted_strong_weak_base **)v116;
            std::wstring::wstring(pExceptionObject, v116);
            v143 = 0;
            if ( v101[0] )
            {
              win_scope::counted_strong_weak_base::AddRef(v101[0]);
              *(_QWORD *)&v143 = v76;
              *((_QWORD *)&v143 + 1) = v77;
            }
            v100 = 13;
            if ( v119 >= 8 )
              operator delete(v117[0]);
            v119 = 7;
            v118 = 0;
            LOWORD(v117[0]) = 0;
            if ( v101[1] && v101[0] )
            {
              win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(v101);
              *(_OWORD *)v101 = 0;
            }
            v44 = 7;
            v133 = 7;
            v132 = 0;
            LOWORD(v131[0]) = 0;
            v45 = v141;
            if ( v141 > 0x7FFFFFFFFFFFFFFELL )
              std::_String_base::_Xlen();
            if ( v141 > 7 )
            {
              std::wstring::_Copy(v130, v141, 0);
              v44 = v133;
              if ( v45 )
                goto LABEL_81;
            }
            else
            {
              if ( v141 )
              {
LABEL_81:
                p_Source = &Source;
                if ( v142 >= 8 )
                  p_Source = Source;
                v47 = v131;
                if ( v44 >= 8 )
                  v47 = (void **)v131[0];
                memcpy_s(v47, 2 * v44, p_Source, 2 * v45);
                v48 = v131;
                if ( v133 >= 8 )
                  v48 = (void **)v131[0];
                v132 = v45;
                *((_WORD *)v48 + v45) = 0;
                goto LABEL_88;
              }
              v132 = 0;
              LOWORD(v131[0]) = 0;
            }
LABEL_88:
            v134 = 0;
            v49 = v143;
            if ( (_QWORD)v143 )
            {
              v50 = *((_QWORD *)&v143 + 1);
              if ( !_InterlockedExchangeAdd((volatile signed __int32 *)(v143 + 8), 1u) )
                _InterlockedAdd((volatile signed __int32 *)(v49 + 12), 1u);
              *(_QWORD *)&v134 = v49;
              *((_QWORD *)&v134 + 1) = v50;
            }
            std::_Tree<std::_Tmap_traits<std::wstring,win_scope::scope<win_musl::consumption::ZipConsumptionPart *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>>>>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,win_scope::scope<win_musl::consumption::ZipConsumptionPart *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>>>>>>,0>>::insert(
              v109,
              v102,
              v130);
            std::pair<std::wstring,win_scope::scope<win_musl::consumption::ZipConsumptionPart *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>>>>>::~pair<std::wstring,win_scope::scope<win_musl::consumption::ZipConsumptionPart *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>>>>>(v130);
            std::pair<std::wstring,win_scope::scope<win_musl::consumption::ZipConsumptionPart *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>>>>>::~pair<std::wstring,win_scope::scope<win_musl::consumption::ZipConsumptionPart *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>>>>>(pExceptionObject);
            v9 = v107;
LABEL_93:
            *(_OWORD *)v102 = 0;
            v51 = v103;
            v135 = *(_QWORD *)(v103 + 56);
            v136 = 0;
            v137 = 0;
            v138 = 0;
            if ( *(_DWORD *)(v103 + 40) )
              v136 = *(_QWORD *)(v103 + 48);
            if ( *(_DWORD *)(v103 + 24) )
            {
              v137 = *(_QWORD *)(v103 + 32);
              v102[0] = 1;
              v102[1] = v137;
            }
            if ( *(_DWORD *)(v103 + 64) )
            {
              LODWORD(v138) = win_musl::get_value(
                                (win_musl *)(v103 + 64),
                                (const struct __MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0009 *)v24);
              v51 = v103;
            }
            v106 = v101;
            *(_OWORD *)v101 = 0;
            v52 = (volatile signed __int32 *)*a5;
            if ( *a5 )
            {
              v53 = (win_scope::counted_strong_weak_base *)a5[1];
              if ( !_InterlockedExchangeAdd(v52 + 2, 1u) )
                _InterlockedAdd(v52 + 3, 1u);
              v101[0] = (win_scope::counted_strong_weak_base *)v52;
              v101[1] = v53;
            }
            v54 = *(_DWORD *)(v51 + 12);
            LODWORD(v103) = v54;
            v55 = *(unsigned int *)(v51 + 8);
            v100 = v55;
            if ( v54 )
            {
              if ( v54 == 9 )
              {
                win_musl::detail::ThrowBuilder<SplException::THResultException>(
                  (SplException::TSystemException *)pExceptionObject,
                  0x67u,
                  0x80511008,
                  (struct win_musl::TStringEllipseBase *)L"Deflate64 is not supported");
                throw (SplException::THResultException *)pExceptionObject;
              }
              if ( v54 != 8 )
              {
                std::wstring::wstring(v130, L"Compression method %{method} is unknown");
                v97 = win_musl::Formatter::Formatter(pExceptionObject, v130);
                std::wstring::wstring(v116, L"method");
                v98 = (win_musl::Formatter *)win_musl::Formatter::insert<enum win_musl::consumption::ZipFileState::type>(
                                               v97,
                                               v116,
                                               &v103);
                v99 = (struct win_musl::TStringEllipseBase *)win_musl::Formatter::c_str(v98);
                win_musl::detail::ThrowBuilder<SplException::THResultException>(
                  (SplException::TSystemException *)v144,
                  0x85u,
                  0x80511008,
                  v99);
                throw (SplException::THResultException *)v144;
              }
              for ( i = 0; ; ++i )
              {
                if ( i >= 5 )
                {
                  std::wstring::wstring(
                    v116,
                    L"Deflate option %{option} is unknown",
                    v55,
                    &win_musl::ZipTranslations::msc_zipOptionsMap);
                  v57 = win_musl::Formatter::Formatter(pExceptionObject, v116);
                  std::wstring::wstring(v130, L"option");
                  v58 = (win_musl::Formatter *)win_musl::Formatter::insert<enum win_musl::consumption::ZipFileState::type>(
                                                 v57,
                                                 v130,
                                                 &v100);
                  v59 = (struct win_musl::TStringEllipseBase *)win_musl::Formatter::c_str(v58);
                  win_musl::detail::ThrowBuilder<SplException::THResultException>(
                    (SplException::TSystemException *)v144,
                    0x7Cu,
                    0x80511008,
                    v59);
                  throw (SplException::THResultException *)v144;
                }
                if ( *((_DWORD *)&win_musl::ZipTranslations::msc_zipOptionsMap + 3 * (int)i + 1) == (_DWORD)v55 )
                  break;
              }
            }
            win_musl::consumption::ZipConsumptionPart::AddZipFileSender(
              (win_musl::consumption::ZipConsumptionPart *)v38,
              (__int64)v102,
              (__int64)v101,
              (__int64)&v135);
            if ( v42 && v38 )
              win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(&v104);
            if ( v115 >= 8 )
              operator delete(Destination[0]);
            v115 = 7;
            v114 = 0;
            LOWORD(Destination[0]) = 0;
            if ( v124 >= 8 )
              operator delete((void *)lpString2[0]);
            v124 = 7;
            v123 = 0;
            LOWORD(lpString2[0]) = 0;
            if ( v129 >= 8 )
              operator delete(Block);
            v129 = 7;
            v128 = 0;
            LOWORD(Block) = 0;
            if ( v9 )
            {
              v43 = (*(_DWORD *)(v9 + 44))-- == 1;
              if ( v43 )
                *(_DWORD *)(v9 + 40) = 0;
              LeaveCriticalSection((LPCRITICAL_SECTION)v9);
            }
            if ( *a5 && a5[1] )
            {
              win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(a5);
              *a5 = 0;
              a5[1] = 0;
            }
            return;
          }
          v64 = lpString2;
          if ( v124 >= 8 )
            v64 = (LPCWCH *)lpString2[0];
          v65 = *(_QWORD *)(v38 + 48);
          if ( v65 < 8 )
            v66 = (_QWORD *)(v38 + 24);
          else
            v66 = (_QWORD *)*v62;
          memcpy_s(v66, 2 * v65, v64, 2 * v63);
          if ( *(_QWORD *)(v38 + 48) >= 8u )
            v62 = (_QWORD *)*v62;
          *(_QWORD *)(v38 + 40) = v63;
          *((_WORD *)v62 + v63) = 0;
          goto LABEL_152;
        }
      }
      else if ( !v123 )
      {
        v114 = 0;
        LOWORD(Destination[0]) = 0;
LABEL_23:
        v15 = v115;
        goto LABEL_24;
      }
      v17 = lpString2;
      if ( v124 >= 8 )
        v17 = (LPCWCH *)lpString2[0];
      v18 = Destination;
      if ( v15 >= 8 )
        v18 = (void **)Destination[0];
      memcpy_s(v18, 2 * v15, v17, 2 * v16);
      v19 = Destination;
      if ( v115 >= 8 )
        v19 = (void **)Destination[0];
      v114 = v16;
      *((_WORD *)v19 + v16) = 0;
      goto LABEL_23;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x40) != 0 )
    {
      win_musl::StringOfZipDeflateOption(*(unsigned int *)(a4 + 8));
      v87 = win_musl::StringOfZipFileCompressionMethod(*(unsigned int *)(a4 + 12), v85, v86);
      v90 = lpString2;
      if ( v124 >= 8 )
        v90 = (LPCWCH *)lpString2[0];
      WPP_SF_SSSS(*(_QWORD *)(v89 + 56), (__int64)v90, v87, v88);
    }
    LOBYTE(v14) = 1;
    std::wstring::_Tidy(v121, v14, 0);
    LOBYTE(v78) = 1;
    std::wstring::_Tidy(v126, v78, 0);
    win_musl::Locker<win_musl::CriticalSection *>::~Locker<win_musl::CriticalSection *>(&v107);
    if ( *a5 && a5[1] )
    {
      win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(a5);
      *a5 = 0;
      a5[1] = 0;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x40) != 0 )
    {
      v79 = win_musl::StringOfZipDeflateOption(*(unsigned int *)(a4 + 8));
      v81 = win_musl::StringOfZipFileCompressionMethod(*(unsigned int *)(a4 + 12), v80, v79);
      WPP_SF_SSSS(*(_QWORD *)(v82 + 56), v81, v83, v84);
    }
    if ( !*(_BYTE *)(*(_QWORD *)(a1 + 120) + 57LL) )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x90u,
        0x80511008,
        (struct win_musl::TStringEllipseBase *)L"Zip item is not a file - all Zip items must be files when streaming a package in-order");
      throw (SplException::THResultException *)pExceptionObject;
    }
    if ( v129 >= 8 )
      operator delete(Block);
    v129 = 7;
    v128 = 0;
    LOWORD(Block) = 0;
    if ( v9 )
    {
      v43 = (*(_DWORD *)(v9 + 44))-- == 1;
      if ( v43 )
        *(_DWORD *)(v9 + 40) = 0;
      LeaveCriticalSection((LPCRITICAL_SECTION)v9);
    }
    if ( *a5 && a5[1] )
    {
      win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(a5);
      *a5 = 0;
      a5[1] = 0;
    }
  }
}

```

## disassembly

```asm
0x180013d80  mov     rax, rsp
0x180013d83  push    rbp
0x180013d84  push    rsi
0x180013d85  push    rdi
0x180013d86  push    r12
0x180013d88  push    r13
0x180013d8a  push    r14
0x180013d8c  push    r15
0x180013d8e  lea     rbp, [rax-268h]
0x180013d95  sub     rsp, 330h
0x180013d9c  mov     [rbp+260h+var_2A8], 0FFFFFFFFFFFFFFFEh
0x180013da4  mov     [rax+18h], rbx
0x180013da8  movaps  xmmword ptr [rax-48h], xmm6
0x180013dac  mov     rax, cs:__security_cookie
0x180013db3  xor     rax, rsp
0x180013db6  mov     [rbp+260h+var_50], rax
0x180013dbd  mov     rsi, r9
0x180013dc0  mov     [rsp+360h+var_2F0], r9
0x180013dc5  mov     ebx, r8d
0x180013dc8  mov     rdi, rdx
0x180013dcb  mov     r12, rcx
0x180013dce  mov     r15, [rbp+260h+arg_20]
0x180013dd5  mov     [rbp+260h+var_2A0], r15
0x180013dd9  mov     [rsp+360h+var_320], 0
0x180013de1  lea     r13, [rcx+38h]
0x180013de5  mov     [rbp+260h+var_2C0], r13
0x180013de9  mov     rcx, r13; lpCriticalSection
0x180013dec  call    cs:__imp_EnterCriticalSection
0x180013df2  mov     ecx, [r13+2Ch]
0x180013df6  lea     eax, [rcx+1]
0x180013df9  mov     [r13+2Ch], eax
0x180013dfd  test    ecx, ecx
0x180013dff  jnz     short loc_180013E0B
0x180013e01  call    cs:__imp_GetCurrentThreadId
0x180013e07  mov     [r13+28h], eax
0x180013e0b  mov     cl, [r12+9Ch]; this
0x180013e13  call    ?ThrowIfFailed@win_dox@@YAX_N@Z; win_dox::ThrowIfFailed(bool)
0x180013e18  mov     rdx, rdi
0x180013e1b  lea     rcx, [rbp+260h+var_210]
0x180013e1f  call    ?Unicode8ToUnicodeWide@win_musl@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@3@@Z; win_musl::Unicode8ToUnicodeWide(std::string const &)
0x180013e24  nop
0x180013e25  cmp     ebx, 2
0x180013e28  jnz     loc_180014120
0x180013e2e  mov     rdx, rdi
0x180013e31  lea     rcx, [rbp+260h+var_248]
0x180013e35  call    ?PartNameFromZipPart@ZipDeinterleaver@consumption@win_musl@@KA?AUPartData@123@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@@Z; win_musl::consumption::ZipDeinterleaver::PartNameFromZipPart(std::string const &)
0x180013e3a  nop
0x180013e3b  lea     edi, [rbx-1]
0x180013e3e  cmp     [r12+98h], edi
0x180013e46  jz      loc_1800140CC
0x180013e4c  lea     r8, [rbp+260h+lpString2]
0x180013e50  mov     r14d, 8
0x180013e56  cmp     [rbp+260h+var_220], r14
0x180013e5a  cmovnb  r8, [rbp+260h+lpString2]; lpString2
0x180013e5f  mov     [rsp+360h+bIgnoreCase], edi; bIgnoreCase
0x180013e63  or      rax, 0FFFFFFFFFFFFFFFFh
0x180013e67  mov     r9d, eax; cchCount2
0x180013e6a  mov     edx, eax; cchCount1
0x180013e6c  lea     rcx, ?gc_contentTypePart@win_musl@@3QB_WB; "/[Content_Types].xml"
0x180013e73  call    cs:__imp_CompareStringOrdinal
0x180013e79  cmp     eax, 2
0x180013e7c  jz      short loc_180013E9A
0x180013e7e  lea     rcx, [rbp+260h+lpString2]
0x180013e82  cmp     [rbp+260h+var_220], r14
0x180013e86  cmovnb  rcx, [rbp+260h+lpString2]; Source
0x180013e8b  xor     edx, edx
0x180013e8d  call    ?IsValidPartUriInternal@win_dox@@YA_NPEB_WPEAV?$scope@PEAVOpcPartUri@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@Z; win_dox::IsValidPartUriInternal(wchar_t const *,win_scope::scope<win_dox::OpcPartUri *,win_scope::const_policies<win_scope::shared_policies>> *)
0x180013e92  test    al, al
0x180013e94  jz      loc_180014B86
0x180013e9a  lea     rax, WPP_GLOBAL_Control
0x180013ea1  mov     r10, cs:WPP_GLOBAL_Control
0x180013ea8  cmp     r10, rax
0x180013eab  jz      short loc_180013EB8
0x180013ead  test    byte ptr [r10+44h], 4
0x180013eb2  jnz     loc_180014BFE
0x180013eb8  mov     edx, 7
0x180013ebd  mov     [rbp+260h+var_278], rdx
0x180013ec1  mov     [rbp+260h+var_280], 0
0x180013ec9  xor     eax, eax
0x180013ecb  mov     word ptr [rbp+260h+Destination], ax
0x180013ecf  mov     rsi, [rbp+260h+var_228]
0x180013ed3  mov     rax, 7FFFFFFFFFFFFFFEh
0x180013edd  cmp     rsi, rax
0x180013ee0  ja      loc_180014C4F
0x180013ee6  cmp     rdx, rsi
0x180013ee9  jb      loc_180014522
0x180013eef  test    rsi, rsi
0x180013ef2  jz      loc_180014592
0x180013ef8  lea     r8, [rbp+260h+lpString2]
0x180013efc  cmp     [rbp+260h+var_220], r14
0x180013f00  cmovnb  r8, [rbp+260h+lpString2]; Source
0x180013f05  lea     rcx, [rbp+260h+Destination]
0x180013f09  cmp     rdx, r14
0x180013f0c  cmovnb  rcx, [rbp+260h+Destination]; Destination
0x180013f11  lea     rbx, [rsi+rsi]
0x180013f15  add     rdx, rdx; DestinationSize
0x180013f18  mov     r9, rbx; SourceSize
0x180013f1b  call    cs:__imp_memcpy_s
0x180013f21  lea     rcx, [rbp+260h+Destination]
0x180013f25  cmp     [rbp+260h+var_278], r14
0x180013f29  cmovnb  rcx, [rbp+260h+Destination]
0x180013f2e  mov     [rbp+260h+var_280], rsi
0x180013f32  xor     eax, eax
0x180013f34  mov     [rbx+rcx], ax
0x180013f38  mov     rdx, [rbp+260h+var_278]
0x180013f3c  mov     [rsp+360h+var_320], 5
0x180013f44  lea     rcx, [rbp+260h+Destination]
0x180013f48  cmp     rdx, r14
0x180013f4b  cmovnb  rcx, [rbp+260h+Destination]
0x180013f50  mov     rax, [rbp+260h+var_280]
0x180013f54  lea     rcx, [rcx+rax*2]
0x180013f58  lea     rax, [rbp+260h+Destination]
0x180013f5c  cmovnb  rax, [rbp+260h+Destination]
0x180013f61  cmp     rax, rcx
0x180013f64  jz      short loc_180013F7E
0x180013f66  movzx   r8d, word ptr [rax]
0x180013f6a  lea     edx, [r8-61h]
0x180013f6e  cmp     dx, 19h
0x180013f72  jbe     short loc_180013FEF
0x180013f74  mov     [rax], r8w
0x180013f78  add     rax, 2
0x180013f7c  jmp     short loc_180013F61
0x180013f7e  lea     rax, [r12+20h]
0x180013f83  mov     [rbp+260h+var_2B0], rax
0x180013f87  mov     rdx, [rax+8]
0x180013f8b  mov     rax, [rdx+8]
0x180013f8f  mov     r8, [rbp+260h+var_280]
0x180013f93  cmp     byte ptr [rax+51h], 0
0x180013f97  jnz     short loc_180013FF9
0x180013f99  lea     r10, [rbp+260h+Destination]
0x180013f9d  cmp     [rbp+260h+var_278], r14
0x180013fa1  cmovnb  r10, [rbp+260h+Destination]
0x180013fa6  mov     r9, r8
0x180013fa9  cmp     [rax+30h], r8
0x180013fad  cmovb   r9, [rax+30h]
0x180013fb2  lea     rcx, [rax+20h]
0x180013fb6  cmp     [rax+38h], r14
0x180013fba  jb      short loc_180013FBF
0x180013fbc  mov     rcx, [rcx]
0x180013fbf  test    r9, r9
0x180013fc2  jz      loc_180014C5D
0x180013fc8  movzx   r11d, word ptr [rcx]
0x180013fcc  cmp     r11w, [r10]
0x180013fd0  jnz     short loc_180013FDF
0x180013fd2  add     rcx, 2
0x180013fd6  add     r10, 2
0x180013fda  sub     r9, rdi
0x180013fdd  jmp     short loc_180013FBF
0x180013fdf  jb      short loc_180013FE9
0x180013fe1  mov     rdx, rax
0x180013fe4  mov     rax, [rax]
0x180013fe7  jmp     short loc_180013F93
0x180013fe9  mov     rax, [rax+10h]
0x180013fed  jmp     short loc_180013F93
0x180013fef  sub     r8w, 20h ; ' '
0x180013ff4  jmp     loc_180013F74
0x180013ff9  cmp     rdx, [r12+28h]
0x180013ffe  jz      short loc_18001404C
0x180014000  lea     rax, [rdx+20h]
0x180014004  mov     r11, r8
0x180014007  cmp     [rdx+38h], r14
0x18001400b  jb      short loc_180014010
0x18001400d  mov     rax, [rax]
0x180014010  mov     rcx, [rdx+30h]
0x180014014  cmp     r8, rcx
0x180014017  cmovb   rcx, r8
0x18001401b  lea     r8, [rbp+260h+Destination]
0x18001401f  cmp     [rbp+260h+var_278], r14
0x180014023  cmovnb  r8, [rbp+260h+Destination]
0x180014028  test    rcx, rcx
0x18001402b  jz      loc_180014C66
0x180014031  movzx   r9d, word ptr [r8]
0x180014035  cmp     r9w, [rax]
0x180014039  jnz     loc_180014587
0x18001403f  add     r8, 2
0x180014043  add     rax, 2
0x180014047  sub     rcx, rdi
0x18001404a  jmp     short loc_180014028
0x18001404c  mov     rdx, [r12+28h]
0x180014051  xorps   xmm6, xmm6
0x180014054  movdqa  [rbp+260h+var_2E0], xmm6
0x180014059  cmp     rdx, [r12+28h]
0x18001405e  jnz     short loc_180014088
0x180014060  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180014067  mov     ecx, 0E0h; unsigned __int64
0x18001406c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180014071  mov     rsi, rax
0x180014074  test    rax, rax
0x180014077  jnz     loc_180014668
0x18001407d  mov     ecx, 8007000Eh; this
0x180014082  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x180014088  xorps   xmm1, xmm1
0x18001408b  movdqa  [rbp+260h+var_2E0], xmm1
0x180014090  mov     rcx, [rdx+40h]; this
0x180014094  test    rcx, rcx
0x180014097  jz      short loc_1800140AF
0x180014099  mov     rdx, [rdx+48h]
0x18001409d  call    ?AddRef@counted_strong_weak_base@win_scope@@QEAAKXZ; win_scope::counted_strong_weak_base::AddRef(void)
0x1800140a2  mov     qword ptr [rbp+260h+var_2E0], rcx
0x1800140a6  mov     qword ptr [rbp+260h+var_2E0+8], rdx
0x1800140aa  movdqa  xmm1, [rbp+260h+var_2E0]
0x1800140af  movdqa  [rbp+260h+var_2E0], xmm1
0x1800140b4  movdqa  xmm0, xmm1
0x1800140b8  psrldq  xmm0, 8
0x1800140bd  movq    rsi, xmm0
0x1800140c2  movq    r12, xmm1
0x1800140c7  jmp     loc_1800142EC
0x1800140cc  cmp     [rbp+260h+var_248], 0
0x1800140d0  jz      loc_180013E4C
0x1800140d6  lea     rax, aAnAppxPackageM; "An APPX package must not contain interl"...
0x1800140dd  mov     [rsp+360h+var_330], rax; struct win_musl::TStringEllipseBase *
0x1800140e2  mov     dword ptr [rsp+360h+var_338], 80080201h; unsigned int
0x1800140ea  mov     [rsp+360h+bIgnoreCase], 99h; unsigned int
0x1800140f2  lea     r9, word_18013A0B6
0x1800140f9  lea     r8, aNoFilename; "(no filename)"
0x180014100  lea     rcx, [rbp+260h+pExceptionObject]; this
0x180014107  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18001410c  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180014113  lea     rcx, [rbp+260h+pExceptionObject]; pExceptionObject
0x18001411a  call    _CxxThrowException_0
0x180014120  lea     rax, WPP_GLOBAL_Control
0x180014127  mov     r14d, 8
0x18001412d  mov     r11, cs:WPP_GLOBAL_Control
0x180014134  cmp     r11, rax
0x180014137  jnz     loc_180014AC2
0x18001413d  mov     rax, [r12+78h]
0x180014142  xor     ebx, ebx
0x180014144  cmp     [rax+39h], bl
0x180014147  jz      loc_180014B3C
0x18001414d  cmp     [rbp+260h+var_1F0], r14
0x180014151  jnb     loc_180014579
0x180014157  mov     [rbp+260h+var_1F0], 7
0x18001415f  mov     [rbp+260h+var_1F8], rbx
0x180014163  mov     word ptr [rbp+260h+Block], bx
0x180014167  test    r13, r13
0x18001416a  jz      short loc_180014181
0x18001416c  add     dword ptr [r13+2Ch], 0FFFFFFFFh
0x180014171  jnz     short loc_180014177
0x180014173  mov     [r13+28h], ebx
0x180014177  mov     rcx, r13; lpCriticalSection
0x18001417a  call    cs:__imp_LeaveCriticalSection
0x180014180  nop
0x180014181  cmp     [r15], rbx
0x180014184  jz      short loc_180014190
0x180014186  cmp     [r15+8], rbx
0x18001418a  jnz     loc_180014544
0x180014190  mov     rcx, [rbp+260h+var_50]
0x180014197  xor     rcx, rsp; StackCookie
0x18001419a  call    __security_check_cookie
0x18001419f  lea     r11, [rsp+360h+var_30]
0x1800141a7  mov     rbx, [r11+50h]
0x1800141ab  movaps  xmm6, xmmword ptr [r11-10h]
0x1800141b0  mov     rsp, r11
0x1800141b3  pop     r15
0x1800141b5  pop     r14
0x1800141b7  pop     r13
0x1800141b9  pop     r12
0x1800141bb  pop     rdi
0x1800141bc  pop     rsi
0x1800141bd  pop     rbp
0x1800141be  retn
0x1800141bf  cmp     [rsp+360h+var_318+8], 0
0x1800141c5  jz      short loc_1800141DA
0x1800141c7  lea     rcx, [rsp+360h+var_318+8]
0x1800141cc  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x1800141d1  xorps   xmm0, xmm0
0x1800141d4  movdqu  xmmword ptr [rsp+360h+var_318+8], xmm0
0x1800141da  mov     rdx, rbx
0x1800141dd  mov     [rbp+260h+var_1C8], rbx
0x1800141e4  xor     r8d, r8d
0x1800141e7  mov     [rbp+260h+var_1D0], r8
0x1800141ee  xor     eax, eax
0x1800141f0  mov     word ptr [rbp+260h+var_1E0], ax
0x1800141f7  mov     r13, [rbp+260h+var_178]
0x1800141fe  mov     rax, 7FFFFFFFFFFFFFFEh
0x180014208  cmp     r13, rax
0x18001420b  ja      loc_180014CAC
0x180014211  cmp     rdx, r13
0x180014214  jb      loc_180014558
0x18001421a  test    r13, r13
0x18001421d  jz      loc_1800145B0
0x180014223  lea     r8, [rbp+260h+Source]
0x18001422a  cmp     [rbp+260h+var_170], r14
0x180014231  cmovnb  r8, [rbp+260h+Source]; Source
0x180014239  lea     rcx, [rbp+260h+var_1E0]
0x180014240  cmp     rdx, r14
0x180014243  cmovnb  rcx, [rbp+260h+var_1E0]; Destination
0x18001424b  lea     rbx, ds:0[r13*2]
0x180014253  add     rdx, rdx; DestinationSize
0x180014256  mov     r9, rbx; SourceSize
0x180014259  call    cs:__imp_memcpy_s
0x18001425f  lea     rcx, [rbp+260h+var_1E0]
0x180014266  cmp     [rbp+260h+var_1C8], r14
0x18001426d  cmovnb  rcx, [rbp+260h+var_1E0]
0x180014275  mov     [rbp+260h+var_1D0], r13
0x18001427c  xor     eax, eax
0x18001427e  mov     [rbx+rcx], ax
0x180014282  xorps   xmm0, xmm0
0x180014285  movdqu  [rbp+260h+var_1C0], xmm0
0x18001428d  mov     rdx, qword ptr [rbp+260h+var_168]
  ... truncated ...
```
