# win_musl::consumption::ZipConsumptionPart::AddZipFileSender(win_musl::consumption::PartType::Enum,uint,__MIDL___MIDL_itf_opc2Eio_0000_0000_0002,win_musl::OptionalValue<__MIDL___MIDL_itf_dox2Ebase_0000_0000_0002,unsigned __int64> const &,win_scope::scope<win_musl::ZipFileSender *,win_scope::const_policies<win_scope::shared_policies>>,__MIDL___MIDL_itf_win72Edox2Ebase_0000_0000_0005 const *)

- ea: `0x180017e6c`
- end: `0x1800186b0`
- name: `?AddZipFileSender@ZipConsumptionPart@consumption@win_musl@@QEAAXW4Enum@PartType@23@IW4__MIDL___MIDL_itf_opc2Eio_0000_0000_0002@@AEBV?$OptionalValue@U__MIDL___MIDL_itf_dox2Ebase_0000_0000_0002@@_K@3@V?$scope@PEAVZipFileSender@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@PEBU__MIDL___MIDL_itf_win72Edox2Ebase_0000_0000_0005@@@Z`
- size: `2116`
- prototype: `__int64 __usercall@<rax>(win_musl::consumption::ZipConsumptionPart *this@<rcx>, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013d80`

## callees

- `0x1800016b0`
- `0x1800037a8`
- `0x18000405c`
- `0x18000f008`
- `0x18000fc14`
- `0x180012fa0`
- `0x180015114`
- `0x180017e6c`
- `0x180018c2c`
- `0x18001a810`
- `0x1800460f0`
- `0x18004d004`
- `0x1800517a0`
- `0x1800654b0`
- `0x1800696e4`
- `0x18009c21c`
- `0x1800cd38c`
- `0x1800d04d8`
- `0x18010b29c`
- `0x18011371c`
- `0x180117740`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017eec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017eec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018166`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018166`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017ed9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017ed9`

## string_xrefs

- `0x180018607`: `During streamed consumption found invalid piece in part. %{part}`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
void __fastcall win_musl::consumption::ZipConsumptionPart::AddZipFileSender(
        struct _RTL_CRITICAL_SECTION *this,
        int a2,
        int a3,
        unsigned int a4,
        _OWORD *a5,
        _QWORD *a6,
        struct __MIDL___MIDL_itf_win72Edox2Ebase_0000_0000_0005 *a7)
{
  struct _RTL_CRITICAL_SECTION *v11; // rdi
  bool v12; // dl
  win_dox *DebugInfo_high; // rcx
  _QWORD *v14; // rax
  int v15; // edx
  const char *v16; // r8
  unsigned int v17; // r9d
  __int64 v18; // rsi
  volatile signed __int32 *v19; // r15
  unsigned __int32 v20; // r8d
  char v21; // cl
  bool v22; // r12
  __int64 *v23; // rcx
  __int64 *v24; // rax
  __m128i *v25; // rdx
  __m128i *v26; // rcx
  __m128i *v27; // rax
  __m128i *v28; // r9
  __int8 v29; // r10
  __m128i *v30; // rbx
  __m128i v31; // xmm0
  _QWORD *v33; // rbx
  __int64 v34; // r8
  __int64 v35; // r9
  __int64 v36; // rcx
  __int64 v37; // rdx
  void *v38; // rax
  __int64 v39; // rcx
  __int64 v40; // r8
  _QWORD *v41; // rax
  int v42; // edx
  const char *v43; // r8
  unsigned int v44; // r9d
  _QWORD *v45; // r15
  __int64 v46; // rcx
  __int64 v47; // rcx
  __m128i v48; // xmm0
  __int64 v49; // rbx
  __int64 v50; // r12
  __int64 v51; // rax
  int v52; // edx
  __int64 v53; // r8
  HANDLE *p_LockSemaphore; // r9
  __int64 *v55; // rdx
  __int64 *v56; // rax
  __int64 v57; // rbx
  win_musl::Formatter *v58; // rax
  struct win_musl::TStringEllipseBase *v59; // rax
  __int128 v60; // [rsp+48h] [rbp-C0h] BYREF
  __int128 v61; // [rsp+58h] [rbp-B0h] BYREF
  __m128i v62; // [rsp+68h] [rbp-A0h] BYREF
  __int128 v63; // [rsp+78h] [rbp-90h] BYREF
  __m128i v64; // [rsp+88h] [rbp-80h] BYREF
  __int128 v65; // [rsp+98h] [rbp-70h] BYREF
  struct __MIDL___MIDL_itf_win72Edox2Ebase_0000_0000_0005 *v66; // [rsp+A8h] [rbp-60h]
  _QWORD *v67; // [rsp+B0h] [rbp-58h]
  __int64 v68; // [rsp+B8h] [rbp-50h]
  _QWORD *v69; // [rsp+C0h] [rbp-48h]
  struct _RTL_CRITICAL_SECTION *v70; // [rsp+C8h] [rbp-40h]
  _QWORD *v71; // [rsp+D0h] [rbp-38h]
  unsigned __int32 v72; // [rsp+D8h] [rbp-30h] BYREF
  __int128 v73; // [rsp+E0h] [rbp-28h] BYREF
  _BYTE v74[40]; // [rsp+100h] [rbp-8h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+128h] [rbp+20h] BYREF
  _BYTE v76[160]; // [rsp+1C8h] [rbp+C0h] BYREF

  v68 = -2;
  v67 = a6;
  v69 = a6;
  v66 = a7;
  v11 = this + 4;
  v70 = this + 4;
  EnterCriticalSection(this + 4);
  DebugInfo_high = (win_dox *)HIDWORD(v11[1].DebugInfo);
  HIDWORD(v11[1].DebugInfo) = (_DWORD)DebugInfo_high + 1;
  if ( !(_DWORD)DebugInfo_high )
    LODWORD(v11[1].DebugInfo) = GetCurrentThreadId();
  LOBYTE(DebugInfo_high) = this[5].OwningThread;
  win_dox::ThrowIfFailed(DebugInfo_high, v12);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0 )
  {
    v51 = win_musl::StringOfCompressionOptions(a4);
    p_LockSemaphore = &this->LockSemaphore;
    if ( *(_QWORD *)&this[1].LockCount >= 8u )
      p_LockSemaphore = (HANDLE *)*p_LockSemaphore;
    WPP_SF_SDS(*(_QWORD *)(v53 + 56), v52, v53, (_DWORD)p_LockSemaphore, a3, v51);
  }
  if ( LODWORD(this[1].OwningThread) == -1 && a4 != -1 )
    LODWORD(this[1].OwningThread) = a4;
  *(_OWORD *)&this[1].LockSemaphore = *a5;
  v14 = operator new(0x58u, (const struct std::nothrow_t *)&std::nothrow);
  v18 = (__int64)v14;
  if ( !v14 )
    SplException::RealThrowFromHR((SplException *)0x8007000ELL, v15, v16, v17);
  v71 = v14;
  *(_QWORD *)&v65 = &v63;
  v63 = 0;
  v36 = *a6;
  if ( *a6 )
  {
    v37 = a6[1];
    if ( _InterlockedIncrement((volatile signed __int32 *)(v36 + 8)) == 1 )
      _InterlockedAdd((volatile signed __int32 *)(v36 + 12), 1u);
    *(_QWORD *)&v63 = v36;
    *((_QWORD *)&v63 + 1) = v37;
  }
  v64.m128i_i64[0] = (__int64)&v63;
  v61 = 0;
  v62.m128i_i64[0] = (__int64)this;
  if ( this )
  {
    v46 = *(_QWORD *)&this->LockCount;
    *(_QWORD *)&v61 = v46;
    if ( !v46 )
      goto LABEL_81;
    if ( _InterlockedIncrement((volatile signed __int32 *)(v46 + 8)) == 1 )
      _InterlockedAdd((volatile signed __int32 *)(v46 + 12), 1u);
    *((_QWORD *)&v61 + 1) = this;
    if ( !(_QWORD)v61 )
    {
LABEL_81:
      win_scope::close_delete::close<win_musl::CallingThread>(&v62);
      win_scope::report_policy_throw::report_init_failure();
    }
  }
  *(_QWORD *)&v65 = &v61;
  v14[1] = 0;
  *v14 = &win_scope::intrusive_shared_weak<win_scope::scope<win_dox::OpcRelationshipImplementation *,win_scope::const_policies<win_scope::shared_policies>>>::`vftable';
  v38 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v38 )
  {
    *((_QWORD *)v38 + 1) = 0;
    *(_QWORD *)v38 = &win_scope::counted_strong_weak<win_musl::consumption::ZipConsumptionPart *,win_scope::const_policies<win_scope::resource_policies>>::`vftable';
    *((_QWORD *)v38 + 2) = v18;
    *(_QWORD *)(v18 + 8) = v38;
    _InterlockedAdd((volatile signed __int32 *)v38 + 3, 1u);
  }
  else
  {
    *(_QWORD *)(v18 + 8) = 0;
  }
  *(_QWORD *)v18 = &win_musl::consumption::ZipConsumptionPart::Piece::`vftable';
  *(_DWORD *)(v18 + 16) = a2;
  *(_OWORD *)(v18 + 24) = *(_OWORD *)&this[1].LockSemaphore;
  *(_DWORD *)(v18 + 40) = a3;
  *(_QWORD *)(v18 + 48) = 0;
  *(_QWORD *)(v18 + 56) = 0;
  v39 = v63;
  if ( (_QWORD)v63 )
  {
    v40 = *((_QWORD *)&v63 + 1);
    if ( _InterlockedIncrement((volatile signed __int32 *)(v63 + 8)) == 1 )
      _InterlockedAdd((volatile signed __int32 *)(v39 + 12), 1u);
    *(_QWORD *)(v18 + 48) = v39;
    *(_QWORD *)(v18 + 56) = v40;
  }
  *(_BYTE *)(v18 + 64) = 0;
  *(_QWORD *)(v18 + 72) = 0;
  *(_QWORD *)(v18 + 80) = 0;
  v41 = operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
  v45 = v41;
  if ( !v41 )
    SplException::RealThrowFromHR((SplException *)0x8007000ELL, v42, v43, v44);
  v62.m128i_i64[0] = (__int64)v41;
  v60 = 0;
  v49 = v61;
  if ( (_QWORD)v61 )
  {
    v50 = *((_QWORD *)&v61 + 1);
    if ( _InterlockedIncrement((volatile signed __int32 *)(v61 + 8)) == 1 )
      _InterlockedAdd((volatile signed __int32 *)(v49 + 12), 1u);
    *(_QWORD *)&v60 = v49;
    *((_QWORD *)&v60 + 1) = v50;
  }
  else
  {
    v50 = *((_QWORD *)&v60 + 1);
    v49 = v60;
  }
  win_scope::intrusive_shared_weak<win_scope::scope<win_musl::consumption::PieceReceiver *,win_scope::const_policies<win_scope::shared_policies>>>::intrusive_shared_weak<win_scope::scope<win_musl::consumption::PieceReceiver *,win_scope::const_policies<win_scope::shared_policies>>>(v41);
  *v45 = &win_musl::consumption::PieceReceiver::`vftable';
  v45[2] = 0;
  v45[3] = 0;
  if ( v49 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v49 + 12));
    v45[2] = v49;
    v45[3] = v50;
  }
  *((_DWORD *)v45 + 8) = a3;
  v45[6] = 0;
  v45[5] = &win_dox::OpcRelationshipCollection::`vftable';
  if ( v49 && v50 )
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(&v60);
  v62.m128i_i64[0] = (__int64)v45;
  v47 = v45[1];
  if ( !v47 )
  {
    win_scope::close_delete::close<win_musl::CallingThread>(&v62);
    win_scope::report_policy_throw::report_init_failure();
  }
  if ( _InterlockedIncrement((volatile signed __int32 *)(v47 + 8)) == 1 )
    _InterlockedAdd((volatile signed __int32 *)(v47 + 12), 1u);
  v62 = *(__m128i *)(v18 + 72);
  v48 = v62;
  *(_QWORD *)(v18 + 72) = v47;
  *(_QWORD *)(v18 + 80) = v45;
  if ( v48.m128i_i64[0] && _mm_srli_si128(v48, 8).m128i_u64[0] )
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(&v62);
  if ( *((_QWORD *)&v61 + 1) && (_QWORD)v61 )
  {
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(&v61);
    v61 = 0;
  }
  if ( *((_QWORD *)&v63 + 1) && (_QWORD)v63 )
  {
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(&v63);
    v63 = 0;
  }
  v65 = 0;
  v62.m128i_i64[0] = v18;
  v19 = *(volatile signed __int32 **)(v18 + 8);
  *(_QWORD *)&v65 = v19;
  if ( !v19 )
  {
    win_scope::close_delete::close<win_musl::CallingThread>(&v62);
    win_scope::report_policy_throw::report_init_failure();
  }
  if ( _InterlockedIncrement(v19 + 2) == 1 )
    _InterlockedAdd(v19 + 3, 1u);
  *((_QWORD *)&v65 + 1) = v18;
  v20 = *(_DWORD *)(v18 + 40);
  v21 = BYTE4(this[3].DebugInfo);
  if ( (*(_DWORD *)(v18 + 16) & 0xFFFFFFFD) != 0 )
  {
    v22 = 0;
    if ( v21 && v20 > LODWORD(this[3].DebugInfo) )
    {
LABEL_120:
      if ( !*(_BYTE *)(this[2].SpinCount + 57) )
      {
        std::wstring::wstring(&v72, L"During streamed consumption found invalid piece in part. %{part}");
        v57 = win_musl::Formatter::Formatter(pExceptionObject, &v72);
        std::wstring::wstring(v74, L"part");
        v58 = (win_musl::Formatter *)win_musl::Formatter::insert<std::wstring>(v57, v74, &this->OwningThread);
        v59 = (struct win_musl::TStringEllipseBase *)win_musl::Formatter::c_str(v58);
        win_musl::detail::ThrowBuilder<SplException::THResultException>(
          (SplException::TSystemException *)v76,
          0xD7u,
          0x80510016,
          v59);
        throw (SplException::THResultException *)v76;
      }
      BYTE1(this[3].SpinCount) = 1;
      goto LABEL_42;
    }
  }
  else
  {
    v22 = v21 != 0;
    v23 = *(__int64 **)&this[2].LockCount;
    v24 = (__int64 *)*v23;
    if ( (__int64 *)*v23 != v23 )
    {
      if ( *((_BYTE *)v23 + 49) )
      {
        v24 = (__int64 *)v23[2];
      }
      else if ( *((_BYTE *)v24 + 49) )
      {
        v55 = (__int64 *)v23[1];
        if ( !*((_BYTE *)v55 + 49) )
        {
          v56 = *(__int64 **)&this[2].LockCount;
          do
          {
            if ( v56 != (__int64 *)*v55 )
              break;
            v56 = v55;
            v23 = v55;
            v55 = (__int64 *)v55[1];
          }
          while ( !*((_BYTE *)v55 + 49) );
        }
        v24 = v23;
        if ( !*((_BYTE *)v23 + 49) )
          v24 = v55;
      }
      else
      {
        while ( !*(_BYTE *)(v24[2] + 49) )
          v24 = (__int64 *)v24[2];
      }
      if ( *(_DWORD *)(v24[5] + 40) > v20 )
        v22 = 1;
    }
    BYTE4(this[3].DebugInfo) = 1;
    LODWORD(this[3].DebugInfo) = v20;
  }
  v25 = *(__m128i **)&this[2].LockCount;
  v26 = (__m128i *)v25->m128i_i64[1];
  v27 = v26;
  v28 = v25;
  v29 = v26[3].m128i_i8[1];
  if ( !v29 )
  {
    do
    {
      if ( v27[1].m128i_i32[2] < v20 )
      {
        v27 = (__m128i *)v27[1].m128i_i64[0];
      }
      else
      {
        v28 = v27;
        v27 = (__m128i *)v27->m128i_i64[0];
      }
    }
    while ( !v27[3].m128i_i8[1] );
    if ( v28 != v25 && v20 >= v28[1].m128i_i32[2] )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0xC7u,
        0x80510015,
        (struct win_musl::TStringEllipseBase *)L"The same piece number existed twice in the same part");
      throw (SplException::THResultException *)pExceptionObject;
    }
  }
  v30 = *(__m128i **)&this[2].LockCount;
  if ( v29 )
    goto LABEL_34;
  do
  {
    if ( v26[1].m128i_i32[2] < v20 )
    {
      v26 = (__m128i *)v26[1].m128i_i64[0];
    }
    else
    {
      v30 = v26;
      v26 = (__m128i *)v26->m128i_i64[0];
    }
  }
  while ( !v26[3].m128i_i8[1] );
  if ( v30 == v25 || v20 < v30[1].m128i_i32[2] )
  {
LABEL_34:
    v64 = 0;
    v72 = v20;
    v73 = 0;
    v30 = *(__m128i **)std::_Tree<std::_Tmap_traits<unsigned int,win_scope::scope<win_musl::consumption::ZipConsumptionPart::Piece *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>>>>,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,win_scope::scope<win_musl::consumption::ZipConsumptionPart::Piece *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>>>>>>,0>>::insert(
                         &this[2],
                         &v60,
                         v30,
                         &v72);
    if ( *((_QWORD *)&v73 + 1) )
    {
      if ( (_QWORD)v73 )
        win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(&v73);
    }
  }
  v64 = 0;
  if ( _InterlockedIncrement(v19 + 2) == 1 )
    _InterlockedAdd(v19 + 3, 1u);
  v64.m128i_i64[0] = (__int64)v19;
  v64.m128i_i64[1] = v18;
  v31 = v30[2];
  v30[2] = _mm_load_si128(&v64);
  v64 = v31;
  if ( v31.m128i_i64[0] && _mm_srli_si128(v31, 8).m128i_u64[0] )
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(&v64);
  if ( v22 )
    goto LABEL_120;
LABEL_42:
  if ( *(_DWORD *)(v18 + 16) )
  {
    v60 = 0;
    win_scope::counted_strong_weak_base::AddRef((win_scope::counted_strong_weak_base *)v19);
    *(_QWORD *)&v60 = v19;
    *((_QWORD *)&v60 + 1) = v18;
    win_musl::consumption::ZipConsumptionPart::NotifyAboutNewPiece(this, &v60, v34, v35);
  }
  if ( !*(_BYTE *)(this[2].SpinCount + 57) || !*(_DWORD *)(v18 + 16) )
    win_musl::consumption::ZipConsumptionPart::AddPartToReceiver((win_musl::consumption::ZipConsumptionPart *)this, v66);
  if ( v18 )
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(&v65);
  if ( v11 )
  {
    if ( HIDWORD(v11[1].DebugInfo)-- == 1 )
      LODWORD(v11[1].DebugInfo) = 0;
    LeaveCriticalSection(v11);
  }
  v33 = v67;
  if ( *v67 )
  {
    if ( v67[1] )
    {
      win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(v67);
      *v33 = 0;
      v33[1] = 0;
    }
  }
}

```

## disassembly

```asm
0x180017e6c  mov     rax, rsp
0x180017e6f  push    rbp
0x180017e70  push    rsi
0x180017e71  push    rdi
0x180017e72  push    r12
0x180017e74  push    r13
0x180017e76  push    r14
0x180017e78  push    r15
0x180017e7a  lea     rbp, [rax-1A8h]
0x180017e81  sub     rsp, 270h
0x180017e88  mov     [rbp+1A0h+var_1F0], 0FFFFFFFFFFFFFFFEh
0x180017e90  mov     [rax+10h], rbx
0x180017e94  mov     rax, cs:__security_cookie
0x180017e9b  xor     rax, rsp
0x180017e9e  mov     [rbp+1A0h+var_40], rax
0x180017ea5  mov     ebx, r9d
0x180017ea8  mov     r13d, r8d
0x180017eab  mov     r15d, edx
0x180017eae  mov     r14, rcx
0x180017eb1  mov     r12, [rbp+1A0h+arg_28]
0x180017eb8  mov     [rbp+1A0h+var_1F8], r12
0x180017ebc  mov     [rbp+1A0h+var_1E8], r12
0x180017ec0  mov     rax, [rbp+1A0h+arg_30]
0x180017ec7  mov     [rbp+1A0h+var_200], rax
0x180017ecb  lea     rdi, [rcx+0A0h]
0x180017ed2  mov     [rbp+1A0h+var_1E0], rdi
0x180017ed6  mov     rcx, rdi; lpCriticalSection
0x180017ed9  call    cs:__imp_EnterCriticalSection
0x180017edf  mov     ecx, [rdi+2Ch]
0x180017ee2  lea     eax, [rcx+1]
0x180017ee5  mov     [rdi+2Ch], eax
0x180017ee8  test    ecx, ecx
0x180017eea  jnz     short loc_180017EF5
0x180017eec  call    cs:__imp_GetCurrentThreadId
0x180017ef2  mov     [rdi+28h], eax
0x180017ef5  mov     cl, [r14+0D8h]; this
0x180017efc  call    ?ThrowIfFailed@win_dox@@YAX_N@Z; win_dox::ThrowIfFailed(bool)
0x180017f01  lea     rax, WPP_GLOBAL_Control
0x180017f08  mov     r8, cs:WPP_GLOBAL_Control
0x180017f0f  cmp     r8, rax
0x180017f12  jz      short loc_180017F1F
0x180017f14  test    byte ptr [r8+44h], 4
0x180017f19  jnz     loc_180018561
0x180017f1f  cmp     dword ptr [r14+38h], 0FFFFFFFFh
0x180017f24  jnz     short loc_180017F2F
0x180017f26  cmp     ebx, 0FFFFFFFFh
0x180017f29  jz      short loc_180017F2F
0x180017f2b  mov     [r14+38h], ebx
0x180017f2f  mov     rax, [rbp+1A0h+arg_20]
0x180017f36  movups  xmm0, xmmword ptr [rax]
0x180017f39  movdqu  xmmword ptr [r14+40h], xmm0
0x180017f3f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180017f46  mov     ecx, 58h ; 'X'; unsigned __int64
0x180017f4b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180017f50  mov     rsi, rax
0x180017f53  xor     ebx, ebx
0x180017f55  test    rax, rax
0x180017f58  jnz     loc_180018283
0x180017f5e  mov     ecx, 8007000Eh; this
0x180017f63  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x180017f69  cmp     qword ptr [rsp+2A0h+var_238+8], r13
0x180017f6e  jz      short loc_180017F83
0x180017f70  lea     rcx, [rsp+2A0h+var_238+8]
0x180017f75  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x180017f7a  xorps   xmm0, xmm0
0x180017f7d  movdqu  xmmword ptr [rsp+2A0h+var_238+8], xmm0
0x180017f83  xorps   xmm0, xmm0
0x180017f86  movdqu  [rbp+1A0h+var_210], xmm0
0x180017f8b  mov     qword ptr [rsp+2A0h+var_248+8], rsi
0x180017f90  mov     r15, [rsi+8]
0x180017f94  mov     qword ptr [rbp+1A0h+var_210], r15
0x180017f98  test    r15, r15
0x180017f9b  jz      loc_1800186A0
0x180017fa1  mov     r11d, 1
0x180017fa7  mov     eax, r11d
0x180017faa  lock xadd [r15+8], eax
0x180017fb0  add     eax, r11d
0x180017fb3  cmp     eax, r11d
0x180017fb6  jz      loc_1800181B5
0x180017fbc  mov     qword ptr [rbp+1A0h+var_210+8], rsi
0x180017fc0  mov     r8d, [rsi+28h]
0x180017fc4  test    dword ptr [rsi+10h], 0FFFFFFFDh
0x180017fcb  setz    al
0x180017fce  mov     cl, [r14+7Ch]
0x180017fd2  test    al, al
0x180017fd4  jz      loc_180018269
0x180017fda  test    cl, cl
0x180017fdc  setnz   r12b
0x180017fe0  mov     rcx, [r14+58h]
0x180017fe4  mov     rax, [rcx]
0x180017fe7  cmp     rax, rcx
0x180017fea  jz      short loc_18001800A
0x180017fec  cmp     [rcx+31h], r13b
0x180017ff0  jz      loc_1800185A8
0x180017ff6  mov     rax, [rcx+10h]
0x180017ffa  mov     rcx, [rax+28h]
0x180017ffe  movzx   r12d, r12b
0x180018002  cmp     [rcx+28h], r8d
0x180018006  cmova   r12d, r11d
0x18001800a  mov     [r14+7Ch], r11b
0x18001800e  mov     [r14+78h], r8d
0x180018012  mov     rdx, [r14+58h]
0x180018016  mov     rcx, [rdx+8]
0x18001801a  mov     rax, rcx
0x18001801d  mov     r9, rdx
0x180018020  mov     r10b, [rcx+31h]
0x180018024  test    r10b, r10b
0x180018027  jnz     short loc_180018048
0x180018029  cmp     [rax+18h], r8d
0x18001802d  jb      loc_180018225
0x180018033  mov     r9, rax
0x180018036  mov     rax, [rax]
0x180018039  cmp     [rax+31h], r13b
0x18001803d  jz      short loc_180018029
0x18001803f  cmp     r9, rdx
0x180018042  jnz     loc_1800181BF
0x180018048  mov     rbx, rdx
0x18001804b  test    r10b, r10b
0x18001804e  jnz     short loc_180018071
0x180018050  cmp     [rcx+18h], r8d
0x180018054  jb      loc_18001822E
0x18001805a  mov     rbx, rcx
0x18001805d  mov     rcx, [rcx]
0x180018060  cmp     [rcx+31h], r13b
0x180018064  jz      short loc_180018050
0x180018066  cmp     rbx, rdx
0x180018069  jz      short loc_180018071
0x18001806b  cmp     r8d, [rbx+18h]
0x18001806f  jnb     short loc_1800180B6
0x180018071  lea     rcx, [r14+50h]
0x180018075  xorps   xmm0, xmm0
0x180018078  movdqu  [rbp+1A0h+var_220], xmm0
0x18001807d  mov     [rbp+1A0h+var_1D0], r8d
0x180018081  movdqu  [rbp+1A0h+var_1C8], xmm0
0x180018086  lea     r9, [rbp+1A0h+var_1D0]
0x18001808a  mov     r8, rbx
0x18001808d  lea     rdx, [rsp+2A0h+var_268+8]
0x180018092  call    ?insert@?$_Tree@V?$_Tmap_traits@IV?$scope@PEAVPiece@ZipConsumptionPart@consumption@win_musl@@U?$const_policies@U?$types_1@U?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@U?$less@I@std@@V?$allocator@U?$pair@$$CBIV?$scope@PEAVPiece@ZipConsumptionPart@consumption@win_musl@@U?$const_policies@U?$types_1@U?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@@std@@@4@$0A@@std@@@std@@QEAA?AViterator@12@V312@AEBU?$pair@$$CBIV?$scope@PEAVPiece@ZipConsumptionPart@consumption@win_musl@@U?$const_policies@U?$types_1@U?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@@2@@Z; std::_Tree<std::_Tmap_traits<uint,win_scope::scope<win_musl::consumption::ZipConsumptionPart::Piece *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>>>>,std::less<uint>,std::allocator<std::pair<uint const,win_scope::scope<win_musl::consumption::ZipConsumptionPart::Piece *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>>>>>>,0>>::insert(std::_Tree<std::_Tmap_traits<uint,win_scope::scope<win_musl::consumption::ZipConsumptionPart::Piece *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>>>>,std::less<uint>,std::allocator<std::pair<uint const,win_scope::scope<win_musl::consumption::ZipConsumptionPart::Piece *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>>>>>>,0>>::iterator,std::pair<uint const,win_scope::scope<win_musl::consumption::ZipConsumptionPart::Piece *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>>>>> const &)
0x180018097  mov     rbx, [rax]
0x18001809a  cmp     qword ptr [rbp+1A0h+var_1C8+8], r13
0x18001809e  jz      short loc_1800180B0
0x1800180a0  cmp     qword ptr [rbp+1A0h+var_1C8], r13
0x1800180a4  jz      short loc_1800180B0
0x1800180a6  lea     rcx, [rbp+1A0h+var_1C8]
0x1800180aa  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x1800180af  nop
0x1800180b0  mov     r11d, 1
0x1800180b6  xorps   xmm1, xmm1
0x1800180b9  movdqa  [rbp+1A0h+var_220], xmm1
0x1800180be  test    r15, r15
0x1800180c1  jz      short loc_1800180E5
0x1800180c3  mov     eax, r11d
0x1800180c6  lock xadd [r15+8], eax
0x1800180cc  add     eax, r11d
0x1800180cf  cmp     eax, r11d
0x1800180d2  jz      loc_18001820D
0x1800180d8  mov     qword ptr [rbp+1A0h+var_220], r15
0x1800180dc  mov     qword ptr [rbp+1A0h+var_220+8], rsi
0x1800180e0  movdqa  xmm1, [rbp+1A0h+var_220]
0x1800180e5  movups  xmm0, xmmword ptr [rbx+20h]
0x1800180e9  movdqu  xmmword ptr [rbx+20h], xmm1
0x1800180ee  movdqa  [rbp+1A0h+var_220], xmm0
0x1800180f3  movq    rax, xmm0
0x1800180f8  test    rax, rax
0x1800180fb  jz      short loc_180018110
0x1800180fd  psrldq  xmm0, 8
0x180018102  movq    rax, xmm0
0x180018107  test    rax, rax
0x18001810a  jnz     loc_180018217
0x180018110  test    r12b, r12b
0x180018113  jnz     loc_1800185F3
0x180018119  cmp     [rsi+10h], r13d
0x18001811d  jnz     loc_180018237
0x180018123  mov     rax, [r14+70h]
0x180018127  cmp     [rax+39h], r13b
0x18001812b  jz      short loc_180018133
0x18001812d  cmp     [rsi+10h], r13d
0x180018131  jnz     short loc_180018140
0x180018133  mov     rdx, [rbp+1A0h+var_200]; struct __MIDL___MIDL_itf_win72Edox2Ebase_0000_0000_0005 *
0x180018137  mov     rcx, r14; this
0x18001813a  call    ?AddPartToReceiver@ZipConsumptionPart@consumption@win_musl@@AEAAXPEBU__MIDL___MIDL_itf_win72Edox2Ebase_0000_0000_0005@@@Z; win_musl::consumption::ZipConsumptionPart::AddPartToReceiver(__MIDL___MIDL_itf_win72Edox2Ebase_0000_0000_0005 const *)
0x18001813f  nop
0x180018140  test    r15, r15
0x180018143  jz      short loc_180018154
0x180018145  test    rsi, rsi
0x180018148  jz      short loc_180018154
0x18001814a  lea     rcx, [rbp+1A0h+var_210]
0x18001814e  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x180018153  nop
0x180018154  test    rdi, rdi
0x180018157  jz      short loc_18001816D
0x180018159  add     dword ptr [rdi+2Ch], 0FFFFFFFFh
0x18001815d  jnz     short loc_180018163
0x18001815f  mov     [rdi+28h], r13d
0x180018163  mov     rcx, rdi; lpCriticalSection
0x180018166  call    cs:__imp_LeaveCriticalSection
0x18001816c  nop
0x18001816d  mov     rbx, [rbp+1A0h+var_1F8]
0x180018171  cmp     [rbx], r13
0x180018174  jz      short loc_18001818B
0x180018176  cmp     [rbx+8], r13
0x18001817a  jz      short loc_18001818B
0x18001817c  mov     rcx, rbx
0x18001817f  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x180018184  mov     [rbx], r13
0x180018187  mov     [rbx+8], r13
0x18001818b  mov     rcx, [rbp+1A0h+var_40]
0x180018192  xor     rcx, rsp; StackCookie
0x180018195  call    __security_check_cookie
0x18001819a  mov     rbx, [rsp+2A0h+arg_8]
0x1800181a2  add     rsp, 270h
0x1800181a9  pop     r15
0x1800181ab  pop     r14
0x1800181ad  pop     r13
0x1800181af  pop     r12
0x1800181b1  pop     rdi
0x1800181b2  pop     rsi
0x1800181b3  pop     rbp
0x1800181b4  retn
0x1800181b5  lock add [r15+0Ch], r11d
0x1800181ba  jmp     loc_180017FBC
0x1800181bf  cmp     r8d, [r9+18h]
0x1800181c3  jb      loc_180018048
0x1800181c9  lea     rax, aTheSamePieceNu; "The same piece number existed twice in "...
0x1800181d0  mov     [rsp+30h], rax; struct win_musl::TStringEllipseBase *
0x1800181d5  mov     [rsp+2A0h+var_278], 80510015h; unsigned int
0x1800181dd  mov     [rsp+2A0h+var_280], 0C7h; unsigned int
0x1800181e5  lea     r9, word_18013A0B6
0x1800181ec  lea     r8, aNoFilename; "(no filename)"
0x1800181f3  lea     rcx, [rbp+1A0h+pExceptionObject]; this
0x1800181f7  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800181fc  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180018203  lea     rcx, [rbp+1A0h+pExceptionObject]; pExceptionObject
0x180018207  call    _CxxThrowException_0
0x18001820d  lock add [r15+0Ch], r11d
0x180018212  jmp     loc_1800180D8
0x180018217  lea     rcx, [rbp+1A0h+var_220]
0x18001821b  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x180018220  jmp     loc_180018110
0x180018225  mov     rax, [rax+10h]
0x180018229  jmp     loc_180018039
0x18001822e  mov     rcx, [rcx+10h]
0x180018232  jmp     loc_180018060
0x180018237  xorps   xmm0, xmm0
0x18001823a  movdqu  [rsp+2A0h+var_268+8], xmm0
0x180018240  test    r15, r15
0x180018243  jz      short loc_180018257
0x180018245  mov     rcx, r15; this
0x180018248  call    ?AddRef@counted_strong_weak_base@win_scope@@QEAAKXZ; win_scope::counted_strong_weak_base::AddRef(void)
0x18001824d  mov     qword ptr [rsp+2A0h+var_268+8], r15
0x180018252  mov     qword ptr [rsp+2A0h+var_258], rsi
0x180018257  lea     rdx, [rsp+2A0h+var_268+8]
0x18001825c  mov     rcx, r14
0x18001825f  call    ?NotifyAboutNewPiece@ZipConsumptionPart@consumption@win_musl@@AEAAXV?$scope@PEAVPiece@ZipConsumptionPart@consumption@win_musl@@U?$const_policies@U?$types_1@U?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@@win_scope@@@Z; win_musl::consumption::ZipConsumptionPart::NotifyAboutNewPiece(win_scope::scope<win_musl::consumption::ZipConsumptionPart::Piece *,win_scope::const_policies<win_scope::types_1<win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>>>>)
0x180018264  jmp     loc_180018123
0x180018269  mov     r12b, r13b
0x18001826c  test    cl, cl
0x18001826e  jz      loc_180018012
0x180018274  cmp     r8d, [r14+78h]
0x180018278  ja      loc_1800185F9
0x18001827e  jmp     loc_180018012
0x180018283  mov     [rbp+1A0h+var_1D8], rsi
0x180018287  lea     rax, [rsp+2A0h+var_238+8]
0x18001828c  mov     qword ptr [rbp+1A0h+var_210], rax
0x180018290  xorps   xmm0, xmm0
0x180018293  movdqu  xmmword ptr [rsp+2A0h+var_238+8], xmm0
0x180018299  mov     rcx, [r12]
0x18001829d  test    rcx, rcx
0x1800182a0  jz      loc_18001858E
0x1800182a6  mov     rdx, [r12+8]
0x1800182ab  mov     r12d, 1
0x1800182b1  mov     eax, r12d
0x1800182b4  lock xadd [rcx+8], eax
0x1800182b9  add     eax, r12d
0x1800182bc  cmp     eax, r12d
0x1800182bf  jz      loc_1800183B6
0x1800182c5  mov     qword ptr [rsp+2A0h+var_238+8], rcx
0x1800182ca  mov     qword ptr [rsp+2A0h+var_238+10h], rdx
0x1800182cf  lea     rax, [rsp+2A0h+var_238+8]
0x1800182d4  mov     qword ptr [rbp+1A0h+var_220], rax
0x1800182d8  movdqu  [rsp+2A0h+var_258+8], xmm0
0x1800182de  mov     qword ptr [rsp+2A0h+var_248+8], r14
0x1800182e3  test    r14, r14
0x1800182e6  jnz     loc_1800183C7
0x1800182ec  lea     rax, [rsp+2A0h+var_258+8]
0x1800182f1  mov     qword ptr [rbp+1A0h+var_210], rax
0x1800182f5  mov     [rsi+8], rbx
0x1800182f9  lea     rax, ??_7?$intrusive_shared_weak@V?$scope@PEAVOpcRelationshipImplementation@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@win_scope@@6B@; const win_scope::intrusive_shared_weak<win_scope::scope<win_dox::OpcRelationshipImplementation *,win_scope::const_policies<win_scope::shared_policies>>>::`vftable'
0x180018300  mov     [rsi], rax
0x180018303  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001830a  mov     ecx, 18h; unsigned __int64
0x18001830f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180018314  test    rax, rax
0x180018317  jz      loc_18001840F
0x18001831d  mov     [rax+8], rbx
0x180018321  lea     rcx, ??_7?$counted_strong_weak@PEAVZipConsumptionPart@consumption@win_musl@@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@6B@; const win_scope::counted_strong_weak<win_musl::consumption::ZipConsumptionPart *,win_scope::const_policies<win_scope::resource_policies>>::`vftable'
0x180018328  mov     [rax], rcx
0x18001832b  mov     [rax+10h], rsi
0x18001832f  mov     [rsi+8], rax
0x180018333  lock add [rax+0Ch], r12d
  ... truncated ...
```
