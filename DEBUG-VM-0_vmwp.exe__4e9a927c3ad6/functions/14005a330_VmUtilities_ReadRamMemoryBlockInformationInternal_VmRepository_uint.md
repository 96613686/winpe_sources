# VmUtilities::ReadRamMemoryBlockInformationInternal(VmRepository *,uint)

- ea: `0x14005a330`
- end: `0x14005abf6`
- name: `?ReadRamMemoryBlockInformationInternal@VmUtilities@@YA?AV?$optional@URamMemoryBlockInformation@VmUtilities@@@std@@PEAVVmRepository@@I@Z`
- size: `2246`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1401e5de4`

## callees

- `0x140031c88`
- `0x140034ef8`
- `0x1400586c4`
- `0x140058c78`
- `0x140058ca0`
- `0x140058d2c`
- `0x1400595cc`
- `0x14005a2d4`
- `0x14005a330`
- `0x14005bc80`
- `0x14005ddd0`
- `0x14005e6d8`
- `0x14006af38`
- `0x14009b150`
- `0x14009b180`
- `0x14009b23c`
- `0x14009b2dc`
- `0x14009d7ac`
- `0x140132940`
- `0x1401335fc`
- `0x1402c2010`

## import_xrefs

- `ntdll!RtlInitializeBitMapEx` at `0x14005a924`
- `ntdll!RtlInitializeBitMapEx` at `0x14005a924`
- `ntdll!RtlNumberOfSetBitsEx` at `0x14005a934`
- `ntdll!RtlNumberOfSetBitsEx` at `0x14005a934`

## string_xrefs

- `0x14005a3bc`: `onecore\vm\common\mgmt\utility\vmutilities.cpp`
- `0x14005a4a8`: `onecore\vm\common\mgmt\utility\vmutilities.cpp`
- `0x14005a4d7`: `onecore\vm\common\mgmt\utility\vmutilities.cpp`
- `0x14005a51b`: `onecore\vm\common\mgmt\utility\vmutilities.cpp`
- `0x14005a5c7`: `onecore\vm\common\mgmt\utility\vmutilities.cpp`
- `0x14005a5fa`: `onecore\vm\common\mgmt\utility\vmutilities.cpp`
- `0x14005a6bf`: `onecore\vm\common\mgmt\utility\vmutilities.cpp`
- `0x14005a75c`: `onecore\vm\common\mgmt\utility\vmutilities.cpp`
- `0x14005a7a5`: `onecore\vm\common\mgmt\utility\vmutilities.cpp`
- `0x14005a8fa`: `onecore\vm\common\mgmt\utility\vmutilities.cpp`
- `0x14005a956`: `onecore\vm\common\mgmt\utility\vmutilities.cpp`
- `0x14005aa10`: `onecore\vm\common\mgmt\utility\vmutilities.cpp`
- `0x14005aa2f`: `onecore\vm\common\mgmt\utility\vmutilities.cpp`
- `0x14005aa58`: `onecore\vm\common\mgmt\utility\vmutilities.cpp`
- `0x14005aab1`: `onecore\vm\common\mgmt\utility\vmutilities.cpp`
- `0x14005aad7`: `onecore\vm\common\mgmt\utility\vmutilities.cpp`
- `0x14005ab74`: `onecore\vm\common\mgmt\utility\vmutilities.cpp`
- `0x14005abc5`: `onecore\vm\common\mgmt\utility\vmutilities.cpp`
- `0x14005abe4`: `onecore\vm\common\mgmt\utility\vmutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall VmUtilities::ReadRamMemoryBlockInformationInternal(__int64 a1, __int64 a2, unsigned int a3)
{
  int v6; // eax
  const unsigned __int16 *v7; // rdx
  __int128 *v8; // rdx
  int v9; // eax
  __int128 *v11; // rdx
  int v12; // eax
  unsigned __int64 v13; // r14
  __int64 *v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r8
  bool AzureFeatureSetEnabled; // al
  unsigned int v19; // eax
  unsigned __int64 v20; // rcx
  __int64 *v21; // rax
  __int64 v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // r8
  bool v25; // bl
  const unsigned __int16 *v26; // rdx
  __int128 *v27; // rdx
  int v28; // eax
  unsigned __int64 v29; // rax
  __int128 *v30; // rdx
  int v31; // eax
  const unsigned __int16 *v32; // rdx
  __int128 *v33; // rdx
  int v34; // eax
  unsigned int v35; // r9d
  __int64 (__fastcall *v36)(__int64, __int128 *, _QWORD, _QWORD); // rdi
  unsigned int v37; // ebx
  __m128i v38; // xmm6
  __int64 v39; // rax
  __int128 *v40; // rdx
  int v41; // eax
  unsigned __int64 v42; // rax
  __int128 *v43; // rdx
  int v44; // eax
  __int128 *v45; // rdx
  int v46; // eax
  __int128 *v47; // rdx
  int v48; // eax
  __int64 (__fastcall *v49)(__int64, __int128 *, _QWORD, _QWORD); // rdi
  unsigned int v50; // ebx
  __int64 v51; // rax
  __int128 *v52; // rdx
  int v53; // eax
  unsigned int v54; // [rsp+20h] [rbp-E0h]
  _QWORD v55[2]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v56; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v57; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v58; // [rsp+50h] [rbp-B0h] BYREF
  __m128i si128; // [rsp+60h] [rbp-A0h]
  __m128i v60; // [rsp+70h] [rbp-90h] BYREF
  int v61; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v62; // [rsp+84h] [rbp-7Ch] BYREF
  __int128 v63; // [rsp+88h] [rbp-78h] BYREF
  __int128 v64; // [rsp+98h] [rbp-68h] BYREF
  __int64 v65; // [rsp+A8h] [rbp-58h]
  unsigned int v66; // [rsp+B0h] [rbp-50h] BYREF
  int v67; // [rsp+B4h] [rbp-4Ch]
  unsigned __int64 v68; // [rsp+B8h] [rbp-48h]
  unsigned __int8 v69; // [rsp+D0h] [rbp-30h]
  _QWORD v70[2]; // [rsp+E0h] [rbp-20h] BYREF
  _OWORD v71[3]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v72; // [rsp+120h] [rbp+20h]
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  v55[0] = a1;
  memset_0(&v66, 0, 0x40u);
  memset(v71, 0, sizeof(v71));
  v72 = 0;
  v56 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)a2 + 288LL))(a2, &v56);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xDE,
      (unsigned int)"onecore\\vm\\common\\mgmt\\utility\\vmutilities.cpp",
      (const char *)(unsigned int)v6,
      v54);
  v58 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v58) = 0;
  v61 = 0;
  v7 = L"RamMemoryBlock%d";
  if ( v56 < 0x600 )
    v7 = L"RamMemoryBlock/%d/";
  Vml::FormatString(&v58, v7, a3);
  v8 = &v58;
  if ( si128.m128i_i64[1] > 7uLL )
    v8 = (__int128 *)v58;
  v9 = (*(__int64 (__fastcall **)(__int64, __int128 *, int *))(*(_QWORD *)a2 + 80LL))(a2, v8, &v61);
  if ( (unsigned int)RepositoryKeyFound(v9) )
  {
    if ( v56 == 1024 )
    {
      if ( v61 != 40 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xF5,
          (unsigned int)"onecore\\vm\\common\\mgmt\\utility\\vmutilities.cpp",
          (const char *)0x80048007LL,
          v54);
    }
    else if ( v56 >= 0x500 && v61 != 48 )
    {
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xFC,
        (unsigned int)"onecore\\vm\\common\\mgmt\\utility\\vmutilities.cpp",
        (const char *)0x80048007LL,
        v54);
    }
    v11 = &v58;
    if ( si128.m128i_i64[1] > 7uLL )
      v11 = (__int128 *)v58;
    v12 = (*(__int64 (__fastcall **)(__int64, __int128 *, unsigned int *))(*(_QWORD *)a2 + 88LL))(a2, v11, &v66);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x106,
        (unsigned int)"onecore\\vm\\common\\mgmt\\utility\\vmutilities.cpp",
        (const char *)(unsigned int)v12,
        v54);
    v13 = v68;
    if ( !v68 || v66 > 3 || (v67 & 0xFFFFFFF0) != 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x10A,
        (unsigned int)"onecore\\vm\\common\\mgmt\\utility\\vmutilities.cpp",
        (const char *)0x80048007LL,
        v54);
    if ( (v67 & 2) != 0 )
    {
      v60 = 0;
      v14 = (__int64 *)std::make_unique<Vml::VmMachineLocalSettingsStore,,0>(v55);
      v15 = *v14;
      *v14 = 0;
      *(_QWORD *)&v63 = v15;
      VirtualizationSettings::VirtualizationSettings(&v60, v16, v17, &v63);
      std::unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,unsigned int,Migration::Parameters::Worker::MigrationTargetInit &&>>::~unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,unsigned int,Migration::Parameters::Worker::MigrationTargetInit &&>>(&v63);
      std::unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,unsigned int,Migration::Parameters::Worker::MigrationTargetInit &&>>::~unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,unsigned int,Migration::Parameters::Worker::MigrationTargetInit &&>>(v55);
      AzureFeatureSetEnabled = VirtualizationSettings::GetAzureFeatureSetEnabled((VirtualizationSettings *)&v60);
      if ( v56 < !AzureFeatureSetEnabled + 2048 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x115,
          (unsigned int)"onecore\\vm\\common\\mgmt\\utility\\vmutilities.cpp",
          (const char *)0x80048007LL,
          v54);
      std::unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,unsigned int,Migration::Parameters::Worker::MigrationTargetInit &&>>::~unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,unsigned int,Migration::Parameters::Worker::MigrationTargetInit &&>>(&v60.m128i_u64[1]);
      v13 = v68;
    }
    if ( v69 >= 0x40u )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x11F,
        (unsigned int)"onecore\\vm\\common\\mgmt\\utility\\vmutilities.cpp",
        (const char *)0x8007000DLL,
        v54);
    v19 = v56;
    if ( v56 >= 0x901 )
    {
      if ( v56 == 2305 )
      {
        v60 = 0;
        v21 = (__int64 *)std::make_unique<Vml::VmMachineLocalSettingsStore,,0>(v55);
        v22 = *v21;
        *v21 = 0;
        *(_QWORD *)&v63 = v22;
        VirtualizationSettings::VirtualizationSettings(&v60, v23, v24, &v63);
        std::unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,unsigned int,Migration::Parameters::Worker::MigrationTargetInit &&>>::~unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,unsigned int,Migration::Parameters::Worker::MigrationTargetInit &&>>(&v63);
        std::unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,unsigned int,Migration::Parameters::Worker::MigrationTargetInit &&>>::~unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,unsigned int,Migration::Parameters::Worker::MigrationTargetInit &&>>(v55);
        v25 = VirtualizationSettings::GetAzureFeatureSetEnabled((VirtualizationSettings *)&v60);
        std::unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,unsigned int,Migration::Parameters::Worker::MigrationTargetInit &&>>::~unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,unsigned int,Migration::Parameters::Worker::MigrationTargetInit &&>>(&v60.m128i_u64[1]);
        v20 = (-(__int64)v25 & 0xFF00000008LL) + 4294967288LL;
        v13 = v68;
        v19 = v56;
      }
      else
      {
        v20 = 0x10000000000LL;
      }
    }
    else
    {
      v20 = 4294967288LL;
    }
    if ( v13 > v20 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x13C,
        (unsigned int)"onecore\\vm\\common\\mgmt\\utility\\vmutilities.cpp",
        (const char *)0x8007000DLL,
        v54);
    v26 = L"RamMemoryBlockPageCountValid%d";
    if ( v19 < 0x600 )
      v26 = L"RamMemoryBlockPageCountValid/%d/";
    Vml::FormatString(&v58, v26, a3);
    v27 = &v58;
    if ( si128.m128i_i64[1] > 7uLL )
      v27 = (__int128 *)v58;
    v28 = (*(__int64 (__fastcall **)(__int64, __int128 *, int *))(*(_QWORD *)a2 + 80LL))(a2, v27, &v61);
    if ( (unsigned int)RepositoryKeyFound(v28) )
    {
      v30 = &v58;
      if ( si128.m128i_i64[1] > 7uLL )
        v30 = (__int128 *)v58;
      v31 = (*(__int64 (__fastcall **)(__int64, __int128 *, _QWORD *))(*(_QWORD *)a2 + 120LL))(a2, v30, v70);
      if ( v31 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x155,
          (unsigned int)"onecore\\vm\\common\\mgmt\\utility\\vmutilities.cpp",
          (const char *)(unsigned int)v31,
          v54);
      v29 = v70[0];
    }
    else
    {
      v29 = v13;
      v70[0] = v13;
    }
    if ( !v13 || v29 > v13 || !v29 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x162,
        (unsigned int)"onecore\\vm\\common\\mgmt\\utility\\vmutilities.cpp",
        (const char *)0x8007000DLL,
        v54);
    if ( v29 != v13 && (v67 & 1) == 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x169,
        (unsigned int)"onecore\\vm\\common\\mgmt\\utility\\vmutilities.cpp",
        (const char *)0x8007000DLL,
        v54);
    v32 = L"RamMemoryBlockBackingBitmap%d";
    if ( v56 < 0x600 )
      v32 = L"RamMemoryBlockBackingBitmap/%d/";
    Vml::FormatString(&v58, v32, a3);
    v62 = 0;
    v33 = &v58;
    if ( si128.m128i_i64[1] > 7uLL )
      v33 = (__int128 *)v58;
    v34 = (*(__int64 (__fastcall **)(__int64, __int128 *, unsigned int *))(*(_QWORD *)a2 + 80LL))(a2, v33, &v62);
    if ( (unsigned int)RepositoryKeyFound(v34) )
    {
      v35 = 8;
      if ( v56 <= 0x900 )
        v35 = 4;
      if ( v62 % v35 || v62 / v35 != (v13 + 8 * v35 - 1) / (8 * v35) )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x181,
          (unsigned int)"onecore\\vm\\common\\mgmt\\utility\\vmutilities.cpp",
          (const char *)0x80004005LL,
          v54);
      v64 = 0;
      v65 = 0;
      v55[0] = 0;
      std::vector<unsigned __int64>::vector<unsigned __int64>(&v64, ((unsigned __int64)v62 + 7) >> 3, v55);
      v60 = 0;
      gsl::span<unsigned __int64,-1>::span<unsigned __int64,-1>(&v60, &v64);
      v36 = *(__int64 (__fastcall **)(__int64, __int128 *, _QWORD, _QWORD))(*(_QWORD *)a2 + 88LL);
      v37 = v62;
      v38 = v60;
      v39 = gsl::as_writable_bytes<unsigned __int64,-1,0>(v55, &v60);
      v40 = &v58;
      if ( si128.m128i_i64[1] > 7uLL )
        v40 = (__int128 *)v58;
      v41 = v36(a2, v40, *(_QWORD *)(v39 + 8), v37);
      if ( v41 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x18C,
          (unsigned int)"onecore\\vm\\common\\mgmt\\utility\\vmutilities.cpp",
          (const char *)(unsigned int)v41,
          v54);
      v63 = 0;
      RtlInitializeBitMapEx(&v63, _mm_srli_si128(v38, 8).m128i_u64[0], v13);
      v42 = RtlNumberOfSetBitsEx(&v63);
      if ( v42 > v70[0] )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x19F,
          (unsigned int)"onecore\\vm\\common\\mgmt\\utility\\vmutilities.cpp",
          (const char *)0x8007000DLL,
          v54);
      v70[1] = v70[0] - v42;
      std::vector<__int64>::operator=(v71, &v64);
      std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,std::shared_ptr<MigrationTransferEndpointTarget>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,std::shared_ptr<MigrationTransferEndpointTarget>>>>>>>(&v64);
    }
    Vml::FormatString(&v58, L"RamMemoryBlockFaultClusterSizeShift%d", a3);
    v57 = 0;
    v43 = &v58;
    if ( si128.m128i_i64[1] > 7uLL )
      v43 = (__int128 *)v58;
    v44 = (*(__int64 (__fastcall **)(__int64, __int128 *, unsigned int *))(*(_QWORD *)a2 + 80LL))(a2, v43, &v57);
    if ( (unsigned int)RepositoryKeyFound(v44) )
    {
      *(_QWORD *)&v63 = 0;
      v45 = &v58;
      if ( si128.m128i_i64[1] > 7uLL )
        v45 = (__int128 *)v58;
      v46 = (*(__int64 (__fastcall **)(__int64, __int128 *, __int128 *))(*(_QWORD *)a2 + 120LL))(a2, v45, &v63);
      if ( v46 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1BA,
          (unsigned int)"onecore\\vm\\common\\mgmt\\utility\\vmutilities.cpp",
          (const char *)(unsigned int)v46,
          v54);
      if ( (unsigned __int64)v63 > 0xFF )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x1BE,
          (unsigned int)"onecore\\vm\\common\\mgmt\\utility\\vmutilities.cpp",
          (const char *)0x570,
          v54);
      Vml::FormatString(&v58, L"RamMemoryBlockFaultClusterBitmap%d", a3);
      v47 = &v58;
      if ( si128.m128i_i64[1] > 7uLL )
        v47 = (__int128 *)v58;
      v48 = (*(__int64 (__fastcall **)(__int64, __int128 *, unsigned int *))(*(_QWORD *)a2 + 80LL))(a2, v47, &v57);
      if ( v48 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1CC,
          (unsigned int)"onecore\\vm\\common\\mgmt\\utility\\vmutilities.cpp",
          (const char *)(unsigned int)v48,
          v54);
      if ( (v57 & 7) != 0 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x1D0,
          (unsigned int)"onecore\\vm\\common\\mgmt\\utility\\vmutilities.cpp",
          (const char *)0x570,
          v54);
      v64 = 0;
      v65 = 0;
      std::vector<unsigned __int64>::vector<unsigned __int64>(&v64);
      v60 = 0;
      gsl::span<unsigned __int64,-1>::span<unsigned __int64,-1>(&v60, &v64);
      v49 = *(__int64 (__fastcall **)(__int64, __int128 *, _QWORD, _QWORD))(*(_QWORD *)a2 + 88LL);
      v50 = v57;
      v51 = gsl::as_writable_bytes<unsigned __int64,-1,0>(v55, &v60);
      v52 = &v58;
      if ( si128.m128i_i64[1] > 7uLL )
        v52 = (__int128 *)v58;
      v53 = v49(a2, v52, *(_QWORD *)(v51 + 8), v50);
      if ( v53 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1D9,
          (unsigned int)"onecore\\vm\\common\\mgmt\\utility\\vmutilities.cpp",
          (const char *)(unsigned int)v53,
          v54);
      std::vector<__int64>::operator=((char *)&v71[1] + 8, &v64);
      LOBYTE(v72) = v63;
      std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,std::shared_ptr<MigrationTransferEndpointTarget>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,std::shared_ptr<MigrationTransferEndpointTarget>>>>>>>(&v64);
    }
    VmUtilities::RamMemoryBlockInformation::RamMemoryBlockInformation(a1, &v66);
    *(_BYTE *)(a1 + 120) = 1;
  }
  else
  {
    *(_BYTE *)(a1 + 120) = 0;
  }
  std::wstring::_Tidy_deallocate(&v58);
  VmUtilities::RamMemoryBlockInformation::~RamMemoryBlockInformation((VmUtilities::RamMemoryBlockInformation *)&v66);
  return a1;
}

```

## disassembly

```asm
0x14005a330  mov     rax, rsp
0x14005a333  push    rbp
0x14005a334  push    rbx
0x14005a335  push    rsi
0x14005a336  push    rdi
0x14005a337  push    r12
0x14005a339  push    r14
0x14005a33b  push    r15
0x14005a33d  lea     rbp, [rsp-50h]
0x14005a342  sub     rsp, 150h
0x14005a349  movaps  xmmword ptr [rax-48h], xmm6
0x14005a34d  mov     rax, cs:__security_cookie
0x14005a354  xor     rax, rsp
0x14005a357  mov     [rbp+80h+var_50], rax
0x14005a35b  mov     r12d, r8d
0x14005a35e  mov     rsi, rdx
0x14005a361  mov     r15, rcx
0x14005a364  mov     [rsp+180h+var_150], rcx
0x14005a369  xor     edx, edx; Val
0x14005a36b  lea     r8d, [rdx+40h]; Size
0x14005a36f  lea     rcx, [rbp+80h+var_D0]; void *
0x14005a373  call    memset_0
0x14005a378  xorps   xmm0, xmm0
0x14005a37b  movdqa  [rbp+80h+var_90], xmm0
0x14005a380  xorps   xmm1, xmm1
0x14005a383  movdqa  [rbp+80h+var_80], xmm1
0x14005a388  movdqa  [rbp+80h+var_70], xmm0
0x14005a38d  xor     eax, eax
0x14005a38f  mov     [rbp+80h+var_60], rax
0x14005a393  mov     [rsp+180h+var_13C], eax
0x14005a397  mov     rax, [rsi]
0x14005a39a  lea     rdx, [rsp+180h+var_13C]
0x14005a39f  mov     rcx, rsi
0x14005a3a2  mov     rax, [rax+120h]
0x14005a3a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005a3ae  mov     rcx, [rbp+88h]; this
0x14005a3b5  test    eax, eax
0x14005a3b7  jns     short loc_14005A3CE
0x14005a3b9  mov     r9d, eax; char *
0x14005a3bc  lea     r8, aOnecoreVmCommo_80; "onecore\\vm\\common\\mgmt\\utility\\vmu"...
0x14005a3c3  mov     edx, 0DEh; void *
0x14005a3c8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14005a3ce  xorps   xmm0, xmm0
0x14005a3d1  movups  [rsp+180h+var_130], xmm0
0x14005a3d6  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x14005a3de  movdqu  [rsp+180h+var_120], xmm1
0x14005a3e4  xor     eax, eax
0x14005a3e6  mov     word ptr [rsp+180h+var_130], ax
0x14005a3eb  mov     [rbp+80h+var_100], eax
0x14005a3ee  lea     rdx, ?MEMORY_BLOCK_KEY_FORMAT_V2@@3QBGB; "RamMemoryBlock%d"
0x14005a3f5  lea     rax, ?MEMORY_BLOCK_KEY_FORMAT@@3QBGB; "RamMemoryBlock/%d/"
0x14005a3fc  mov     edi, 600h
0x14005a401  cmp     [rsp+180h+var_13C], edi
0x14005a405  cmovb   rdx, rax
0x14005a409  mov     r8d, r12d
0x14005a40c  lea     rcx, [rsp+180h+var_130]
0x14005a411  call    ?FormatString@Vml@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; Vml::FormatString(std::wstring &,ushort const *,...)
0x14005a416  mov     rax, [rsi]
0x14005a419  lea     rdx, [rsp+180h+var_130]
0x14005a41e  cmp     qword ptr [rsp+180h+var_120+8], 7
0x14005a424  cmova   rdx, qword ptr [rsp+180h+var_130]
0x14005a42a  lea     r8, [rbp+80h+var_100]
0x14005a42e  mov     rcx, rsi
0x14005a431  mov     rax, [rax+50h]
0x14005a435  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005a43a  mov     ecx, eax; int
0x14005a43c  call    ?RepositoryKeyFound@@YAHJ@Z; RepositoryKeyFound(long)
0x14005a441  test    eax, eax
0x14005a443  jnz     short loc_14005A487
0x14005a445  mov     [r15+78h], al
0x14005a449  lea     rcx, [rsp+180h+var_130]
0x14005a44e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14005a453  nop
0x14005a454  lea     rcx, [rbp+80h+var_D0]; this
0x14005a458  call    ??1RamMemoryBlockInformation@VmUtilities@@QEAA@XZ; VmUtilities::RamMemoryBlockInformation::~RamMemoryBlockInformation(void)
0x14005a45d  mov     rax, r15
0x14005a460  mov     rcx, [rbp+80h+var_50]
0x14005a464  xor     rcx, rsp; StackCookie
0x14005a467  call    __security_check_cookie
0x14005a46c  movaps  xmm6, [rsp+180h+var_40]
0x14005a474  add     rsp, 150h
0x14005a47b  pop     r15
0x14005a47d  pop     r14
0x14005a47f  pop     r12
0x14005a481  pop     rdi
0x14005a482  pop     rsi
0x14005a483  pop     rbx
0x14005a484  pop     rbp
0x14005a485  retn
0x14005a487  mov     r9d, [rbp+80h+var_100]
0x14005a48b  cmp     [rsp+180h+var_13C], 400h
0x14005a493  jnz     short loc_14005A4BA
0x14005a495  cmp     r9d, 28h ; '('
0x14005a499  jz      short loc_14005A4E9
0x14005a49b  mov     rcx, [rbp+88h]; this
0x14005a4a2  mov     r9d, 80048007h; char *
0x14005a4a8  lea     r8, aOnecoreVmCommo_80; "onecore\\vm\\common\\mgmt\\utility\\vmu"...
0x14005a4af  mov     edx, 0F5h; void *
0x14005a4b4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14005a4ba  cmp     [rsp+180h+var_13C], 500h
0x14005a4c2  jb      short loc_14005A4E9
0x14005a4c4  cmp     r9d, 30h ; '0'
0x14005a4c8  jz      short loc_14005A4E9
0x14005a4ca  mov     rcx, [rbp+88h]; this
0x14005a4d1  mov     r9d, 80048007h; char *
0x14005a4d7  lea     r8, aOnecoreVmCommo_80; "onecore\\vm\\common\\mgmt\\utility\\vmu"...
0x14005a4de  mov     edx, 0FCh; void *
0x14005a4e3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14005a4e9  mov     rax, [rsi]
0x14005a4ec  lea     rdx, [rsp+180h+var_130]
0x14005a4f1  cmp     qword ptr [rsp+180h+var_120+8], 7
0x14005a4f7  cmova   rdx, qword ptr [rsp+180h+var_130]
0x14005a4fd  lea     r8, [rbp+80h+var_D0]
0x14005a501  mov     rcx, rsi
0x14005a504  mov     rax, [rax+58h]
0x14005a508  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005a50d  mov     rcx, [rbp+88h]; this
0x14005a514  test    eax, eax
0x14005a516  jns     short loc_14005A52D
0x14005a518  mov     r9d, eax; char *
0x14005a51b  lea     r8, aOnecoreVmCommo_80; "onecore\\vm\\common\\mgmt\\utility\\vmu"...
0x14005a522  mov     edx, 106h; void *
0x14005a527  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14005a52d  mov     r14, [rbp+80h+var_C8]
0x14005a531  test    r14, r14
0x14005a534  jz      loc_14005ABD7
0x14005a53a  cmp     [rbp+80h+var_D0], 3
0x14005a53e  ja      loc_14005ABD7
0x14005a544  test    [rbp+80h+var_CC], 0FFFFFFF0h
0x14005a54b  jnz     loc_14005ABD7
0x14005a551  test    byte ptr [rbp+80h+var_CC], 2
0x14005a555  jz      loc_14005A5E7
0x14005a55b  xorps   xmm0, xmm0
0x14005a55e  movups  [rsp+180h+var_110], xmm0
0x14005a563  lea     rcx, [rsp+180h+var_150]
0x14005a568  call    ??$make_unique@VVmMachineLocalSettingsStore@Vml@@$$V$0A@@std@@YA?AV?$unique_ptr@VVmMachineLocalSettingsStore@Vml@@U?$default_delete@VVmMachineLocalSettingsStore@Vml@@@std@@@0@XZ; std::make_unique<Vml::VmMachineLocalSettingsStore,,0>(void)
0x14005a56d  nop
0x14005a56e  mov     rcx, [rax]
0x14005a571  mov     qword ptr [rax], 0
0x14005a578  mov     qword ptr [rbp+80h+var_F8], rcx
0x14005a57c  lea     r9, [rbp+80h+var_F8]
0x14005a580  lea     rcx, [rsp+180h+var_110]
0x14005a585  call    ??0VirtualizationSettings@@QEAA@_NPEBG$$QEAV?$unique_ptr@VISettingsStore@@U?$default_delete@VISettingsStore@@@std@@@std@@@Z; VirtualizationSettings::VirtualizationSettings(bool,ushort const *,std::unique_ptr<ISettingsStore> &&)
0x14005a58a  nop
0x14005a58b  lea     rcx, [rbp+80h+var_F8]
0x14005a58f  call    ??1?$unique_ptr@V?$VmDispatchContextWithParams@XPEAUIVmSimpleTask@@I$$QEAUMigrationTargetInit@Worker@Parameters@Migration@@@Vml@@U?$default_delete@V?$VmDispatchContextWithParams@XPEAUIVmSimpleTask@@I$$QEAUMigrationTargetInit@Worker@Parameters@Migration@@@Vml@@@std@@@std@@QEAA@XZ; std::unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,uint,Migration::Parameters::Worker::MigrationTargetInit &&>>::~unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,uint,Migration::Parameters::Worker::MigrationTargetInit &&>>(void)
0x14005a594  nop
0x14005a595  lea     rcx, [rsp+180h+var_150]
0x14005a59a  call    ??1?$unique_ptr@V?$VmDispatchContextWithParams@XPEAUIVmSimpleTask@@I$$QEAUMigrationTargetInit@Worker@Parameters@Migration@@@Vml@@U?$default_delete@V?$VmDispatchContextWithParams@XPEAUIVmSimpleTask@@I$$QEAUMigrationTargetInit@Worker@Parameters@Migration@@@Vml@@@std@@@std@@QEAA@XZ; std::unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,uint,Migration::Parameters::Worker::MigrationTargetInit &&>>::~unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,uint,Migration::Parameters::Worker::MigrationTargetInit &&>>(void)
0x14005a59f  lea     rcx, [rsp+180h+var_110]; this
0x14005a5a4  call    ?GetAzureFeatureSetEnabled@VirtualizationSettings@@UEBA_NXZ; VirtualizationSettings::GetAzureFeatureSetEnabled(void)
0x14005a5a9  movzx   eax, al
0x14005a5ac  xor     eax, 1
0x14005a5af  add     eax, 800h
0x14005a5b4  cmp     [rsp+180h+var_13C], eax
0x14005a5b8  jnb     short loc_14005A5D9
0x14005a5ba  mov     rcx, [rbp+88h]; this
0x14005a5c1  mov     r9d, 80048007h; char *
0x14005a5c7  lea     r8, aOnecoreVmCommo_80; "onecore\\vm\\common\\mgmt\\utility\\vmu"...
0x14005a5ce  mov     edx, 115h; void *
0x14005a5d3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14005a5d9  lea     rcx, [rsp+180h+var_110+8]
0x14005a5de  call    ??1?$unique_ptr@V?$VmDispatchContextWithParams@XPEAUIVmSimpleTask@@I$$QEAUMigrationTargetInit@Worker@Parameters@Migration@@@Vml@@U?$default_delete@V?$VmDispatchContextWithParams@XPEAUIVmSimpleTask@@I$$QEAUMigrationTargetInit@Worker@Parameters@Migration@@@Vml@@@std@@@std@@QEAA@XZ; std::unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,uint,Migration::Parameters::Worker::MigrationTargetInit &&>>::~unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,uint,Migration::Parameters::Worker::MigrationTargetInit &&>>(void)
0x14005a5e3  mov     r14, [rbp+80h+var_C8]
0x14005a5e7  cmp     [rbp+80h+var_B0], 40h ; '@'
0x14005a5eb  jb      short loc_14005A60C
0x14005a5ed  mov     rcx, [rbp+88h]; this
0x14005a5f4  mov     r9d, 8007000Dh; char *
0x14005a5fa  lea     r8, aOnecoreVmCommo_80; "onecore\\vm\\common\\mgmt\\utility\\vmu"...
0x14005a601  mov     edx, 11Fh; void *
0x14005a606  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14005a60c  mov     eax, [rsp+180h+var_13C]
0x14005a610  mov     ecx, 901h
0x14005a615  cmp     eax, ecx
0x14005a617  jnb     short loc_14005A623
0x14005a619  mov     ecx, 0FFFFFFF8h
0x14005a61e  jmp     loc_14005A6AD
0x14005a623  jnz     short loc_14005A6A3
0x14005a625  xorps   xmm0, xmm0
0x14005a628  movups  [rsp+180h+var_110], xmm0
0x14005a62d  lea     rcx, [rsp+180h+var_150]
0x14005a632  call    ??$make_unique@VVmMachineLocalSettingsStore@Vml@@$$V$0A@@std@@YA?AV?$unique_ptr@VVmMachineLocalSettingsStore@Vml@@U?$default_delete@VVmMachineLocalSettingsStore@Vml@@@std@@@0@XZ; std::make_unique<Vml::VmMachineLocalSettingsStore,,0>(void)
0x14005a637  nop
0x14005a638  mov     rcx, [rax]
0x14005a63b  mov     qword ptr [rax], 0
0x14005a642  mov     qword ptr [rbp+80h+var_F8], rcx
0x14005a646  lea     r9, [rbp+80h+var_F8]
0x14005a64a  lea     rcx, [rsp+180h+var_110]
0x14005a64f  call    ??0VirtualizationSettings@@QEAA@_NPEBG$$QEAV?$unique_ptr@VISettingsStore@@U?$default_delete@VISettingsStore@@@std@@@std@@@Z; VirtualizationSettings::VirtualizationSettings(bool,ushort const *,std::unique_ptr<ISettingsStore> &&)
0x14005a654  nop
0x14005a655  lea     rcx, [rbp+80h+var_F8]
0x14005a659  call    ??1?$unique_ptr@V?$VmDispatchContextWithParams@XPEAUIVmSimpleTask@@I$$QEAUMigrationTargetInit@Worker@Parameters@Migration@@@Vml@@U?$default_delete@V?$VmDispatchContextWithParams@XPEAUIVmSimpleTask@@I$$QEAUMigrationTargetInit@Worker@Parameters@Migration@@@Vml@@@std@@@std@@QEAA@XZ; std::unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,uint,Migration::Parameters::Worker::MigrationTargetInit &&>>::~unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,uint,Migration::Parameters::Worker::MigrationTargetInit &&>>(void)
0x14005a65e  nop
0x14005a65f  lea     rcx, [rsp+180h+var_150]
0x14005a664  call    ??1?$unique_ptr@V?$VmDispatchContextWithParams@XPEAUIVmSimpleTask@@I$$QEAUMigrationTargetInit@Worker@Parameters@Migration@@@Vml@@U?$default_delete@V?$VmDispatchContextWithParams@XPEAUIVmSimpleTask@@I$$QEAUMigrationTargetInit@Worker@Parameters@Migration@@@Vml@@@std@@@std@@QEAA@XZ; std::unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,uint,Migration::Parameters::Worker::MigrationTargetInit &&>>::~unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,uint,Migration::Parameters::Worker::MigrationTargetInit &&>>(void)
0x14005a669  lea     rcx, [rsp+180h+var_110]; this
0x14005a66e  call    ?GetAzureFeatureSetEnabled@VirtualizationSettings@@UEBA_NXZ; VirtualizationSettings::GetAzureFeatureSetEnabled(void)
0x14005a673  mov     bl, al
0x14005a675  lea     rcx, [rsp+180h+var_110+8]
0x14005a67a  call    ??1?$unique_ptr@V?$VmDispatchContextWithParams@XPEAUIVmSimpleTask@@I$$QEAUMigrationTargetInit@Worker@Parameters@Migration@@@Vml@@U?$default_delete@V?$VmDispatchContextWithParams@XPEAUIVmSimpleTask@@I$$QEAUMigrationTargetInit@Worker@Parameters@Migration@@@Vml@@@std@@@std@@QEAA@XZ; std::unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,uint,Migration::Parameters::Worker::MigrationTargetInit &&>>::~unique_ptr<Vml::VmDispatchContextWithParams<void,IVmSimpleTask *,uint,Migration::Parameters::Worker::MigrationTargetInit &&>>(void)
0x14005a67f  neg     bl
0x14005a681  sbb     rax, rax
0x14005a684  mov     rcx, 0FF00000008h
0x14005a68e  and     rax, rcx
0x14005a691  mov     ecx, 0FFFFFFF8h
0x14005a696  add     rcx, rax
0x14005a699  mov     r14, [rbp+80h+var_C8]
0x14005a69d  mov     eax, [rsp+180h+var_13C]
0x14005a6a1  jmp     short loc_14005A6AD
0x14005a6a3  mov     rcx, 10000000000h
0x14005a6ad  cmp     r14, rcx
0x14005a6b0  jbe     short loc_14005A6D1
0x14005a6b2  mov     rcx, [rbp+88h]; this
0x14005a6b9  mov     r9d, 8007000Dh; char *
0x14005a6bf  lea     r8, aOnecoreVmCommo_80; "onecore\\vm\\common\\mgmt\\utility\\vmu"...
0x14005a6c6  mov     edx, 13Ch; void *
0x14005a6cb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14005a6d1  lea     rdx, ?MEMORY_BLOCK_PAGE_COUNT_VALID_FORMAT_V2@@3QBGB; "RamMemoryBlockPageCountValid%d"
0x14005a6d8  lea     rcx, ?MEMORY_BLOCK_PAGE_COUNT_VALID_FORMAT@@3QBGB; "RamMemoryBlockPageCountValid/%d/"
0x14005a6df  cmp     eax, edi
0x14005a6e1  cmovb   rdx, rcx
0x14005a6e5  mov     r8d, r12d
0x14005a6e8  lea     rcx, [rsp+180h+var_130]
0x14005a6ed  call    ?FormatString@Vml@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; Vml::FormatString(std::wstring &,ushort const *,...)
0x14005a6f2  mov     rax, [rsi]
0x14005a6f5  lea     rdx, [rsp+180h+var_130]
0x14005a6fa  cmp     qword ptr [rsp+180h+var_120+8], 7
0x14005a700  cmova   rdx, qword ptr [rsp+180h+var_130]
0x14005a706  lea     r8, [rbp+80h+var_100]
0x14005a70a  mov     rcx, rsi
0x14005a70d  mov     rax, [rax+50h]
0x14005a711  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005a716  mov     ecx, eax; int
0x14005a718  call    ?RepositoryKeyFound@@YAHJ@Z; RepositoryKeyFound(long)
0x14005a71d  test    eax, eax
0x14005a71f  jnz     short loc_14005A72A
0x14005a721  mov     rax, r14
0x14005a724  mov     [rbp+80h+var_A0], rax
0x14005a728  jmp     short loc_14005A772
0x14005a72a  mov     rax, [rsi]
0x14005a72d  lea     rdx, [rsp+180h+var_130]
0x14005a732  cmp     qword ptr [rsp+180h+var_120+8], 7
0x14005a738  cmova   rdx, qword ptr [rsp+180h+var_130]
0x14005a73e  lea     r8, [rbp+80h+var_A0]
0x14005a742  mov     rcx, rsi
0x14005a745  mov     rax, [rax+78h]
0x14005a749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005a74e  mov     rcx, [rbp+88h]; this
0x14005a755  test    eax, eax
0x14005a757  jns     short loc_14005A76E
0x14005a759  mov     r9d, eax; char *
0x14005a75c  lea     r8, aOnecoreVmCommo_80; "onecore\\vm\\common\\mgmt\\utility\\vmu"...
0x14005a763  mov     edx, 155h; void *
0x14005a768  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14005a76e  mov     rax, [rbp+80h+var_A0]
0x14005a772  test    r14, r14
0x14005a775  jz      loc_14005ABB8
0x14005a77b  cmp     rax, r14
0x14005a77e  ja      loc_14005ABB8
0x14005a784  test    rax, rax
0x14005a787  jz      loc_14005ABB8
0x14005a78d  cmp     rax, r14
0x14005a790  jz      short loc_14005A7B7
0x14005a792  test    byte ptr [rbp+80h+var_CC], 1
0x14005a796  jnz     short loc_14005A7B7
0x14005a798  mov     rcx, [rbp+88h]; this
0x14005a79f  mov     r9d, 8007000Dh; char *
0x14005a7a5  lea     r8, aOnecoreVmCommo_80; "onecore\\vm\\common\\mgmt\\utility\\vmu"...
0x14005a7ac  mov     edx, 169h; void *
0x14005a7b1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14005a7b7  lea     rdx, ?MEMORY_BLOCK_BACKING_BITMAP_FORMAT_V2@@3QBGB; "RamMemoryBlockBackingBitmap%d"
0x14005a7be  lea     rax, ?MEMORY_BLOCK_BACKING_BITMAP_FORMAT@@3QBGB; "RamMemoryBlockBackingBitmap/%d/"
0x14005a7c5  cmp     [rsp+180h+var_13C], edi
0x14005a7c9  cmovb   rdx, rax
0x14005a7cd  mov     r8d, r12d
0x14005a7d0  lea     rcx, [rsp+180h+var_130]
0x14005a7d5  call    ?FormatString@Vml@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; Vml::FormatString(std::wstring &,ushort const *,...)
0x14005a7da  mov     [rbp+80h+var_FC], 0
0x14005a7e1  mov     rax, [rsi]
0x14005a7e4  lea     rdx, [rsp+180h+var_130]
0x14005a7e9  cmp     qword ptr [rsp+180h+var_120+8], 7
0x14005a7ef  cmova   rdx, qword ptr [rsp+180h+var_130]
0x14005a7f5  lea     r8, [rbp+80h+var_FC]
0x14005a7f9  mov     rcx, rsi
0x14005a7fc  mov     rax, [rax+50h]
0x14005a800  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005a805  mov     ecx, eax; int
0x14005a807  call    ?RepositoryKeyFound@@YAHJ@Z; RepositoryKeyFound(long)
0x14005a80c  test    eax, eax
0x14005a80e  jz      loc_14005A986
0x14005a814  mov     eax, 4
0x14005a819  lea     r9d, [rax+4]
0x14005a81d  cmp     [rsp+180h+var_13C], 900h
0x14005a825  cmovbe  r9d, eax
0x14005a829  xor     edx, edx
0x14005a82b  mov     r10d, [rbp+80h+var_FC]
0x14005a82f  mov     eax, r10d
0x14005a832  div     r9d
0x14005a835  test    edx, edx
0x14005a837  jnz     loc_14005AA22
  ... truncated ...
```
