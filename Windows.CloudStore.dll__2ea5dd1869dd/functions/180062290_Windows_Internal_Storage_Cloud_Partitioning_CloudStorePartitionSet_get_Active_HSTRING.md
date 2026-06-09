# Windows::Internal::Storage::Cloud::Partitioning::CloudStorePartitionSet::get_Active(HSTRING__ * *)

- ea: `0x180062290`
- end: `0x1800626df`
- name: `?get_Active@CloudStorePartitionSet@Partitioning@Cloud@Storage@Internal@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `1103`
- prototype: `int(Windows::Internal::Storage::Cloud::Partitioning::CloudStorePartitionSet *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting`

## callees

- `0x180023fd4`
- `0x180024fd0`
- `0x18004ffb4`
- `0x18005b244`
- `0x18005de38`
- `0x18005ded4`
- `0x180062290`
- `0x1800626e8`
- `0x1800627a8`
- `0x1800629f8`
- `0x18008dd08`
- `0x18009c748`
- `0x1800c8458`
- `0x1801201a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18006234b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18006234b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006246e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800625c4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006246e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800625c4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800623c0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180062433`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800625fc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800623c0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180062433`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800625fc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180062591`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800625ee`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006268a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180062591`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800625ee`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006268a`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180062312`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180062312`
- `ntdll!RtlIsMultiSessionSku` at `0x180062318`
- `ntdll!RtlIsMultiSessionSku` at `0x180062318`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18006237e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800624f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18006237e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800624f8`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Windows::Internal::Storage::Cloud::Partitioning::CloudStorePartitionSet::get_Active(
        Windows::Internal::Storage::Cloud::Partitioning::CloudStorePartitionSet *this,
        HSTRING *a2)
{
  __int64 v4; // rcx
  int v5; // ecx
  const unsigned __int16 *v6; // rsi
  const WCHAR *v7; // rcx
  HRESULT String; // eax
  unsigned int v9; // edi
  const char *v10; // r9
  __int64 result; // rax
  const WCHAR *v12; // rcx
  HRESULT v13; // eax
  unsigned int v14; // ebx
  __m128i v15; // xmm0
  const unsigned __int16 *v16; // rbx
  __m128i si128; // xmm0
  int v18[2]; // [rsp+20h] [rbp-1E8h] BYREF
  RTL_SRWLOCK *v19; // [rsp+28h] [rbp-1E0h]
  PCNZWCH sourceString[2]; // [rsp+30h] [rbp-1D8h] BYREF
  UINT32 length[4]; // [rsp+40h] [rbp-1C8h]
  void *v22; // [rsp+50h] [rbp-1B8h] BYREF
  __m128i v23; // [rsp+60h] [rbp-1A8h]
  void *v24[3]; // [rsp+70h] [rbp-198h] BYREF
  unsigned __int64 v25; // [rsp+88h] [rbp-180h]
  _QWORD v26[42]; // [rsp+90h] [rbp-178h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+0h]

  *a2 = 0;
  wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v26,
    "GetActivePartition");
  v26[0] = &Windows::Internal::Storage::Cloud::CloudStoreTelemetry::GetActivePartition::`vftable';
  Windows::Internal::Storage::Cloud::CloudStoreTelemetry::GetActivePartition::StartActivity((Windows::Internal::Storage::Cloud::CloudStoreTelemetry::GetActivePartition *)v26);
  try
  {
    if ( *((_DWORD *)this + 16) == 2 )
    {
      v18[0] = 17;
      RtlGetDeviceFamilyInfoEnum(0, v18, 0);
      if ( (unsigned __int8)RtlIsMultiSessionSku(v4) )
      {
        if ( v18[0] <= 6u )
        {
          v5 = 74;
          if ( _bittest(&v5, v18[0]) )
          {
            AcquireSRWLockShared(&Windows::Internal::Storage::Cloud::Partitioning::CloudStorePartitionSet::s_activeDeviceExperienceParitionPartitionLock);
            if ( *(_QWORD *)&::length )
            {
              v6 = (const unsigned __int16 *)&Windows::Internal::Storage::Cloud::Partitioning::CloudStorePartitionSet::s_activeDeviceExpereincePartitionId;
              v7 = (const WCHAR *)&Windows::Internal::Storage::Cloud::Partitioning::CloudStorePartitionSet::s_activeDeviceExpereincePartitionId;
              if ( (unsigned __int64)qword_180281FB8 > 7 )
                v7 = Windows::Internal::Storage::Cloud::Partitioning::CloudStorePartitionSet::s_activeDeviceExpereincePartitionId;
              String = WindowsCreateString(v7, ::length, a2);
              v9 = String;
              if ( String < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x53,
                  (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstorepartitionset.cpp",
                  (const char *)(unsigned int)String,
                  v18[0]);
                ReleaseSRWLockShared(&Windows::Internal::Storage::Cloud::Partitioning::CloudStorePartitionSet::s_activeDeviceExperienceParitionPartitionLock);
                v26[0] = &Windows::Internal::Storage::Cloud::CloudStoreTelemetry::GetActivePartition::`vftable';
                wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v26);
                wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v26);
                return v9;
              }
              else
              {
                if ( (unsigned __int64)qword_180281FB8 > 7 )
                  v6 = Windows::Internal::Storage::Cloud::Partitioning::CloudStorePartitionSet::s_activeDeviceExpereincePartitionId;
                wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
                  v26,
                  0);
                Windows::Internal::Storage::Cloud::CloudStoreTelemetry::GetActivePartition::Stop(
                  (Windows::Internal::Storage::Cloud::CloudStoreTelemetry::GetActivePartition *)v26,
                  v6);
                ReleaseSRWLockShared(&Windows::Internal::Storage::Cloud::Partitioning::CloudStorePartitionSet::s_activeDeviceExperienceParitionPartitionLock);
                v26[0] = &Windows::Internal::Storage::Cloud::CloudStoreTelemetry::GetActivePartition::`vftable';
                wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v26);
                wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v26);
                return 0;
              }
            }
            ReleaseSRWLockShared(&Windows::Internal::Storage::Cloud::Partitioning::CloudStorePartitionSet::s_activeDeviceExperienceParitionPartitionLock);
          }
        }
      }
    }
    AcquireSRWLockExclusive((PSRWLOCK)this + 9);
    *(_QWORD *)v18 = (char *)this + 72;
    Windows::Internal::Storage::Cloud::Partitioning::CloudStorePartitionSet::LoadActivePartitionId(this, &v22);
    std::wstring::wstring(v24);
    Windows::Internal::Storage::Cloud::Partitioning::CloudStorePartitionSet::ReconcileActivePartition(
      this,
      sourceString,
      v24);
    if ( v25 > 7 )
      std::_Deallocate<16>(v24[0], (const struct std::nothrow_t *)(2 * v25 + 2));
    if ( *((_DWORD *)this + 16) == 2 )
    {
      AcquireSRWLockExclusive(&Windows::Internal::Storage::Cloud::Partitioning::CloudStorePartitionSet::s_activeDeviceExperienceParitionPartitionLock);
      v19 = &Windows::Internal::Storage::Cloud::Partitioning::CloudStorePartitionSet::s_activeDeviceExperienceParitionPartitionLock;
      if ( !*(_QWORD *)&::length )
        std::wstring::operator=(
          &Windows::Internal::Storage::Cloud::Partitioning::CloudStorePartitionSet::s_activeDeviceExpereincePartitionId,
          sourceString);
      ReleaseSRWLockExclusive(&Windows::Internal::Storage::Cloud::Partitioning::CloudStorePartitionSet::s_activeDeviceExperienceParitionPartitionLock);
    }
    v12 = (const WCHAR *)sourceString;
    if ( *(_QWORD *)&length[2] > 7u )
      v12 = sourceString[0];
    v13 = WindowsCreateString(v12, length[0], a2);
    v14 = v13;
    if ( v13 >= 0 )
    {
      v16 = (const unsigned __int16 *)sourceString;
      if ( *(_QWORD *)&length[2] > 7u )
        v16 = sourceString[0];
      wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
        v26,
        0);
      Windows::Internal::Storage::Cloud::CloudStoreTelemetry::GetActivePartition::Stop(
        (Windows::Internal::Storage::Cloud::CloudStoreTelemetry::GetActivePartition *)v26,
        v16);
      if ( *(_QWORD *)&length[2] > 7u )
        std::_Deallocate<16>((void *)sourceString[0], (const struct std::nothrow_t *)(2LL * *(_QWORD *)&length[2] + 2));
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      *(__m128i *)length = si128;
      LOWORD(sourceString[0]) = 0;
      if ( v23.m128i_i64[1] > 7uLL )
      {
        std::_Deallocate<16>(v22, (const struct std::nothrow_t *)(2 * v23.m128i_i64[1] + 2));
        si128 = _mm_load_si128((const __m128i *)&_xmm);
      }
      v23 = si128;
      LOWORD(v22) = 0;
      if ( this != (Windows::Internal::Storage::Cloud::Partitioning::CloudStorePartitionSet *)-72LL )
        ReleaseSRWLockExclusive((PSRWLOCK)this + 9);
      v26[0] = &Windows::Internal::Storage::Cloud::CloudStoreTelemetry::GetActivePartition::`vftable';
      wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v26);
      wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v26);
      result = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6F,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstorepartitionset.cpp",
        (const char *)(unsigned int)v13,
        v18[0]);
      if ( *(_QWORD *)&length[2] > 7u )
        std::_Deallocate<16>((void *)sourceString[0], (const struct std::nothrow_t *)(2LL * *(_QWORD *)&length[2] + 2));
      v15 = _mm_load_si128((const __m128i *)&_xmm);
      *(__m128i *)length = v15;
      LOWORD(sourceString[0]) = 0;
      if ( v23.m128i_i64[1] > 7uLL )
      {
        std::_Deallocate<16>(v22, (const struct std::nothrow_t *)(2 * v23.m128i_i64[1] + 2));
        v15 = _mm_load_si128((const __m128i *)&_xmm);
      }
      v23 = v15;
      LOWORD(v22) = 0;
      if ( this != (Windows::Internal::Storage::Cloud::Partitioning::CloudStorePartitionSet *)-72LL )
        ReleaseSRWLockExclusive((PSRWLOCK)this + 9);
      v26[0] = &Windows::Internal::Storage::Cloud::CloudStoreTelemetry::GetActivePartition::`vftable';
      wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v26);
      wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v26);
      result = v14;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x73,
                           (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstorepartitionset.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x180062290  mov     [rsp+arg_10], rbx
0x180062295  mov     [rsp+arg_18], rsi
0x18006229a  push    rdi
0x18006229b  push    r14
0x18006229d  push    r15
0x18006229f  sub     rsp, 1F0h
0x1800622a6  mov     rax, cs:__security_cookie
0x1800622ad  xor     rax, rsp
0x1800622b0  mov     [rsp+208h+var_28], rax
0x1800622b8  mov     r14, rdx
0x1800622bb  mov     rsi, rcx
0x1800622be  mov     qword ptr [rdx], 0
0x1800622c5  lea     rdx, aGetactiveparti; "GetActivePartition"
0x1800622cc  lea     rcx, [rsp+208h+var_178]
0x1800622d4  call    ??0?$ActivityBase@VCloudStoreTelemetry@Cloud@Storage@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800622d9  lea     r15, ??_7GetActivePartition@CloudStoreTelemetry@Cloud@Storage@Internal@Windows@@6B@; const Windows::Internal::Storage::Cloud::CloudStoreTelemetry::GetActivePartition::`vftable'
0x1800622e0  mov     [rsp+208h+var_178], r15
0x1800622e8  lea     rcx, [rsp+208h+var_178]; this
0x1800622f0  call    ?StartActivity@GetActivePartition@CloudStoreTelemetry@Cloud@Storage@Internal@Windows@@QEAAXXZ; Windows::Internal::Storage::Cloud::CloudStoreTelemetry::GetActivePartition::StartActivity(void)
0x1800622f5  nop
0x1800622f6  cmp     dword ptr [rsi+40h], 2
0x1800622fa  jnz     loc_180062460
0x180062300  mov     [rsp+208h+var_1E8], 11h; int
0x180062308  xor     r8d, r8d
0x18006230b  lea     rdx, [rsp+208h+var_1E8]
0x180062310  xor     ecx, ecx
0x180062312  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x180062318  call    cs:__imp_RtlIsMultiSessionSku
0x18006231e  test    al, al
0x180062320  jz      loc_180062460
0x180062326  mov     eax, [rsp+208h+var_1E8]
0x18006232a  cmp     eax, 6
0x18006232d  ja      loc_180062460
0x180062333  mov     ecx, 4Ah ; 'J'
0x180062338  bt      ecx, eax
0x18006233b  jnb     loc_180062460
0x180062341  lea     rbx, ?s_activeDeviceExperienceParitionPartitionLock@CloudStorePartitionSet@Partitioning@Cloud@Storage@Internal@Windows@@0Vsrwlock@wil@@A; wil::srwlock Windows::Internal::Storage::Cloud::Partitioning::CloudStorePartitionSet::s_activeDeviceExperienceParitionPartitionLock
0x180062348  mov     rcx, rbx; SRWLock
0x18006234b  call    cs:__imp_AcquireSRWLockShared
0x180062351  mov     rdx, cs:length; length
0x180062358  test    rdx, rdx
0x18006235b  jz      loc_1800625F9
0x180062361  lea     rsi, ?s_activeDeviceExpereincePartitionId@CloudStorePartitionSet@Partitioning@Cloud@Storage@Internal@Windows@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring Windows::Internal::Storage::Cloud::Partitioning::CloudStorePartitionSet::s_activeDeviceExpereincePartitionId
0x180062368  mov     rcx, rsi
0x18006236b  cmp     cs:qword_180281FB8, 7
0x180062373  cmova   rcx, cs:?s_activeDeviceExpereincePartitionId@CloudStorePartitionSet@Partitioning@Cloud@Storage@Internal@Windows@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; sourceString
0x18006237b  mov     r8, r14; string
0x18006237e  call    cs:__imp_WindowsCreateString
0x180062384  mov     edi, eax
0x180062386  test    eax, eax
0x180062388  js      loc_180062414
0x18006238e  cmp     cs:qword_180281FB8, 7
0x180062396  cmova   rsi, cs:?s_activeDeviceExpereincePartitionId@CloudStorePartitionSet@Partitioning@Cloud@Storage@Internal@Windows@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring Windows::Internal::Storage::Cloud::Partitioning::CloudStorePartitionSet::s_activeDeviceExpereincePartitionId
0x18006239e  xor     edx, edx
0x1800623a0  lea     rcx, [rsp+208h+var_178]
0x1800623a8  call    ?SetStopResult@?$ActivityBase@VCloudStoreTelemetry@Cloud@Storage@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXJPEAJ@Z; wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x1800623ad  mov     rdx, rsi; unsigned __int16 *
0x1800623b0  lea     rcx, [rsp+208h+var_178]; this
0x1800623b8  call    ?Stop@GetActivePartition@CloudStoreTelemetry@Cloud@Storage@Internal@Windows@@QEAAXPEBG@Z; Windows::Internal::Storage::Cloud::CloudStoreTelemetry::GetActivePartition::Stop(ushort const *)
0x1800623bd  mov     rcx, rbx; SRWLock
0x1800623c0  call    cs:__imp_ReleaseSRWLockShared
0x1800623c6  nop
0x1800623c7  mov     [rsp+208h+var_178], r15
0x1800623cf  lea     rcx, [rsp+208h+var_178]
0x1800623d7  call    ?Destroy@?$ActivityBase@VCloudStoreTelemetry@Cloud@Storage@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800623dc  lea     rcx, [rsp+208h+var_178]
0x1800623e4  call    ??1?$ActivityBase@VCloudStoreTelemetry@Cloud@Storage@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800623e9  xor     eax, eax
0x1800623eb  mov     rcx, [rsp+208h+var_28]
0x1800623f3  xor     rcx, rsp; StackCookie
0x1800623f6  call    __security_check_cookie
0x1800623fb  lea     r11, [rsp+208h+var_18]
0x180062403  mov     rbx, [r11+30h]
0x180062407  mov     rsi, [r11+38h]
0x18006240b  mov     rsp, r11
0x18006240e  pop     r15
0x180062410  pop     r14
0x180062412  pop     rdi
0x180062413  retn
0x180062414  mov     rcx, [rsp+208h]; this
0x18006241c  mov     r9d, edi; char *
0x18006241f  lea     r8, aOnecoreuapShel_100; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x180062426  mov     edx, 53h ; 'S'; void *
0x18006242b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180062430  mov     rcx, rbx; SRWLock
0x180062433  call    cs:__imp_ReleaseSRWLockShared
0x180062439  nop
0x18006243a  mov     [rsp+208h+var_178], r15
0x180062442  lea     rcx, [rsp+208h+var_178]
0x18006244a  call    ?Destroy@?$ActivityBase@VCloudStoreTelemetry@Cloud@Storage@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18006244f  lea     rcx, [rsp+208h+var_178]
0x180062457  call    ??1?$ActivityBase@VCloudStoreTelemetry@Cloud@Storage@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18006245c  mov     eax, edi
0x18006245e  jmp     short loc_1800623EB
0x180062460  lea     rbx, ?s_activeDeviceExperienceParitionPartitionLock@CloudStorePartitionSet@Partitioning@Cloud@Storage@Internal@Windows@@0Vsrwlock@wil@@A; wil::srwlock Windows::Internal::Storage::Cloud::Partitioning::CloudStorePartitionSet::s_activeDeviceExperienceParitionPartitionLock
0x180062467  lea     rdi, [rsi+48h]
0x18006246b  mov     rcx, rdi; SRWLock
0x18006246e  call    cs:__imp_AcquireSRWLockExclusive
0x180062474  mov     qword ptr [rsp+208h+var_1E8], rdi; int
0x180062479  lea     rdx, [rsp+208h+var_1B8]
0x18006247e  mov     rcx, rsi
0x180062481  call    ?LoadActivePartitionId@CloudStorePartitionSet@Partitioning@Cloud@Storage@Internal@Windows@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Windows::Internal::Storage::Cloud::Partitioning::CloudStorePartitionSet::LoadActivePartitionId(void)
0x180062486  nop
0x180062487  lea     rdx, [rsp+208h+var_1B8]
0x18006248c  cmp     [rsp+208h+var_1A0], 7
0x180062492  cmova   rdx, [rsp+208h+var_1B8]
0x180062498  lea     rcx, [rsp+208h+var_198]
0x18006249d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800624a2  nop
0x1800624a3  lea     r8, [rsp+208h+var_198]
0x1800624a8  lea     rdx, [rsp+208h+sourceString]
0x1800624ad  mov     rcx, rsi
0x1800624b0  call    ?ReconcileActivePartition@CloudStorePartitionSet@Partitioning@Cloud@Storage@Internal@Windows@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV78@@Z; Windows::Internal::Storage::Cloud::Partitioning::CloudStorePartitionSet::ReconcileActivePartition(std::wstring const &)
0x1800624b5  nop
0x1800624b6  mov     rdx, [rsp+208h+var_180]
0x1800624be  cmp     rdx, 7
0x1800624c2  jbe     short loc_1800624D6
0x1800624c4  lea     rdx, ds:2[rdx*2]
0x1800624cc  mov     rcx, [rsp+208h+var_198]
0x1800624d1  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800624d6  cmp     dword ptr [rsi+40h], 2
0x1800624da  jz      loc_1800625C1
0x1800624e0  lea     rcx, [rsp+208h+sourceString]
0x1800624e5  cmp     qword ptr [rsp+208h+length+8], 7
0x1800624eb  cmova   rcx, [rsp+208h+sourceString]; sourceString
0x1800624f1  mov     r8, r14; string
0x1800624f4  mov     edx, [rsp+208h+length]; length
0x1800624f8  call    cs:__imp_WindowsCreateString
0x1800624fe  mov     ebx, eax
0x180062500  test    eax, eax
0x180062502  jns     loc_180062607
0x180062508  mov     rcx, [rsp+208h]; this
0x180062510  mov     r9d, eax; char *
0x180062513  lea     r8, aOnecoreuapShel_100; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18006251a  mov     edx, 6Fh ; 'o'; void *
0x18006251f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180062524  nop
0x180062525  mov     rdx, qword ptr [rsp+208h+length+8]
0x18006252a  cmp     rdx, 7
0x18006252e  jbe     short loc_180062542
0x180062530  lea     rdx, ds:2[rdx*2]
0x180062538  mov     rcx, [rsp+208h+sourceString]
0x18006253d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180062542  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18006254a  movdqu  xmmword ptr [rsp+208h+length], xmm0
0x180062550  xor     eax, eax
0x180062552  mov     word ptr [rsp+208h+sourceString], ax
0x180062557  mov     rdx, [rsp+208h+var_1A0]
0x18006255c  cmp     rdx, 7
0x180062560  jbe     short loc_18006257C
0x180062562  lea     rdx, ds:2[rdx*2]
0x18006256a  mov     rcx, [rsp+208h+var_1B8]
0x18006256f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180062574  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18006257c  movdqu  xmmword ptr [rsp+60h], xmm0
0x180062582  xor     eax, eax
0x180062584  mov     word ptr [rsp+208h+var_1B8], ax
0x180062589  test    rdi, rdi
0x18006258c  jz      short loc_180062598
0x18006258e  mov     rcx, rdi; SRWLock
0x180062591  call    cs:__imp_ReleaseSRWLockExclusive
0x180062597  nop
0x180062598  mov     [rsp+208h+var_178], r15
0x1800625a0  lea     rcx, [rsp+208h+var_178]
0x1800625a8  call    ?Destroy@?$ActivityBase@VCloudStoreTelemetry@Cloud@Storage@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800625ad  lea     rcx, [rsp+208h+var_178]
0x1800625b5  call    ??1?$ActivityBase@VCloudStoreTelemetry@Cloud@Storage@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800625ba  mov     eax, ebx
0x1800625bc  jmp     loc_1800623EB
0x1800625c1  mov     rcx, rbx; SRWLock
0x1800625c4  call    cs:__imp_AcquireSRWLockExclusive
0x1800625ca  mov     [rsp+208h+var_1E0], rbx
0x1800625cf  cmp     cs:length, 0
0x1800625d7  jnz     short loc_1800625EB
0x1800625d9  lea     rdx, [rsp+208h+sourceString]
0x1800625de  lea     rcx, ?s_activeDeviceExpereincePartitionId@CloudStorePartitionSet@Partitioning@Cloud@Storage@Internal@Windows@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring Windows::Internal::Storage::Cloud::Partitioning::CloudStorePartitionSet::s_activeDeviceExpereincePartitionId
0x1800625e5  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800625ea  nop
0x1800625eb  mov     rcx, rbx; SRWLock
0x1800625ee  call    cs:__imp_ReleaseSRWLockExclusive
0x1800625f4  jmp     loc_1800624E0
0x1800625f9  mov     rcx, rbx; SRWLock
0x1800625fc  call    cs:__imp_ReleaseSRWLockShared
0x180062602  jmp     loc_180062467
0x180062607  lea     rbx, [rsp+208h+sourceString]
0x18006260c  cmp     qword ptr [rsp+208h+length+8], 7
0x180062612  cmova   rbx, [rsp+208h+sourceString]
0x180062618  xor     edx, edx
0x18006261a  lea     rcx, [rsp+208h+var_178]
0x180062622  call    ?SetStopResult@?$ActivityBase@VCloudStoreTelemetry@Cloud@Storage@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXJPEAJ@Z; wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x180062627  mov     rdx, rbx; unsigned __int16 *
0x18006262a  lea     rcx, [rsp+208h+var_178]; this
0x180062632  call    ?Stop@GetActivePartition@CloudStoreTelemetry@Cloud@Storage@Internal@Windows@@QEAAXPEBG@Z; Windows::Internal::Storage::Cloud::CloudStoreTelemetry::GetActivePartition::Stop(ushort const *)
0x180062637  nop
0x180062638  mov     rdx, qword ptr [rsp+208h+length+8]
0x18006263d  cmp     rdx, 7
0x180062641  jbe     short loc_180062655
0x180062643  lea     rdx, ds:2[rdx*2]
0x18006264b  mov     rcx, [rsp+208h+sourceString]
0x180062650  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180062655  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18006265d  movdqu  xmmword ptr [rsp+208h+length], xmm0
0x180062663  xor     eax, eax
0x180062665  mov     word ptr [rsp+208h+sourceString], ax
0x18006266a  mov     rdx, [rsp+208h+var_1A0]
0x18006266f  cmp     rdx, 7
0x180062673  ja      short loc_1800626BA
0x180062675  movdqu  xmmword ptr [rsp+60h], xmm0
0x18006267b  xor     eax, eax
0x18006267d  mov     word ptr [rsp+208h+var_1B8], ax
0x180062682  test    rdi, rdi
0x180062685  jz      short loc_180062691
0x180062687  mov     rcx, rdi; SRWLock
0x18006268a  call    cs:__imp_ReleaseSRWLockExclusive
0x180062690  nop
0x180062691  mov     [rsp+208h+var_178], r15
0x180062699  lea     rcx, [rsp+208h+var_178]
0x1800626a1  call    ?Destroy@?$ActivityBase@VCloudStoreTelemetry@Cloud@Storage@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800626a6  lea     rcx, [rsp+208h+var_178]
0x1800626ae  call    ??1?$ActivityBase@VCloudStoreTelemetry@Cloud@Storage@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800626b3  xor     eax, eax
0x1800626b5  jmp     loc_1800623EB
0x1800626ba  lea     rdx, ds:2[rdx*2]
0x1800626c2  mov     rcx, [rsp+208h+var_1B8]
0x1800626c7  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800626cc  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x1800626d4  jmp     short loc_180062675
0x1800626d6  mov     eax, [rsp+208h+var_1E8]
0x1800626da  jmp     loc_1800623EB
```
