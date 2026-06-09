# UpdateSessionOrchestrator::ReportPolicies(int *)

- ea: `0x18000e120`
- end: `0x18000eb10`
- name: `?ReportPolicies@UpdateSessionOrchestrator@@UEAAJPEAH@Z`
- size: `2544`
- prototype: `__int64 __fastcall(UpdateSessionOrchestrator *__hidden this, int *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180008e64`
- `0x18000c3ac`
- `0x18000c480`
- `0x18000c524`
- `0x18000e120`
- `0x180010890`
- `0x180011680`
- `0x1800420e0`
- `0x18006ea28`
- `0x1800dd930`
- `0x1800e4630`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x18000e627`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x18000e68d`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x18000e8e5`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x18000e627`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x18000e68d`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x18000e8e5`

## string_xrefs

- `0x18000ea7b`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x18000ea95`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x18000eaaf`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x18000eac9`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x18000eae3`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x18000eafd`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=29
__int64 __fastcall UpdateSessionOrchestrator::ReportPolicies(UpdateSessionOrchestrator *this, int *a2)
{
  _QWORD *v4; // rax
  volatile signed __int32 *v5; // rdi
  __int16 *traits_2_unsigned_short; // rax
  const char *v7; // r9
  int v8; // r11d
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 SystemValueOrDefault; // r15
  char v12; // di
  unsigned __int8 v13; // r13
  unsigned __int8 (__fastcall *v14)(__int64, __int128 *, __int128 *, __int128 *); // rsi
  int *v15; // rax
  const char *v16; // r9
  __int64 v17; // r11
  __int64 v18; // rax
  __int64 v19; // rdx
  int *v20; // rax
  const char *v21; // r9
  int v22; // r11d
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 (__fastcall *v25)(__int64, __int128 *, __int128 *); // rdi
  int *v26; // rax
  const char *v27; // r9
  __int64 v28; // r11
  __int64 v29; // rax
  volatile signed __int32 *v30; // rdi
  _QWORD *v31; // rax
  char v32; // si
  volatile signed __int32 *v33; // rdi
  __int64 **v34; // rax
  __int64 *v35; // rcx
  __int64 v36; // rax
  volatile signed __int32 *v37; // rdi
  signed __int64 v38; // rcx
  char v39; // dl
  signed __int64 v40; // rdi
  _QWORD *v41; // rdx
  __int64 v42; // rsi
  unsigned __int64 i; // rcx
  __int64 **v44; // rax
  __int64 *v45; // rcx
  __int64 v46; // rax
  _QWORD *v47; // rdx
  volatile signed __int32 *v48; // rdi
  void (__fastcall *v49)(__int64, __int128 *, __int128 *, __int128 *, _QWORD *); // rdi
  __int16 *v50; // rax
  const char *v51; // r9
  __int64 v52; // r11
  __int64 v53; // rax
  __int64 v54; // rax
  __int64 v55; // rdi
  int *v56; // rax
  const char *v57; // r9
  __int64 v58; // r11
  __int64 v59; // rax
  __int64 v60; // rax
  volatile signed __int32 *v61; // rdi
  volatile signed __int32 *v62; // rdi
  int v63; // [rsp+20h] [rbp-108h]
  __int128 v64; // [rsp+30h] [rbp-F8h] BYREF
  __int128 v65; // [rsp+40h] [rbp-E8h] BYREF
  __int128 v66; // [rsp+50h] [rbp-D8h] BYREF
  __int128 v67; // [rsp+60h] [rbp-C8h] BYREF
  __int128 v68; // [rsp+70h] [rbp-B8h] BYREF
  _QWORD v69[4]; // [rsp+80h] [rbp-A8h] BYREF
  char v70; // [rsp+A0h] [rbp-88h]
  int v71; // [rsp+A8h] [rbp-80h] BYREF
  __int128 v72; // [rsp+B0h] [rbp-78h] BYREF
  _QWORD v73[2]; // [rsp+C0h] [rbp-68h] BYREF
  __int64 v74; // [rsp+D0h] [rbp-58h]
  unsigned __int64 v75; // [rsp+D8h] [rbp-50h]
  __int64 v76; // [rsp+E0h] [rbp-48h]
  unsigned int v77; // [rsp+E8h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  if ( a2 )
  {
    v68 = 0;
    SystemInterface::Service::GetSystem((__int64 *)&v68);
    v4 = (_QWORD *)(**(__int64 (__fastcall ***)(_QWORD, __int128 *))v68)(v68, &v64);
    (*(void (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)*v4 + 360LL))(*v4, v73);
    v5 = (volatile signed __int32 *)*((_QWORD *)&v64 + 1);
    if ( *((_QWORD *)&v64 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v64 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v5)(v5);
        if ( _InterlockedExchangeAdd(v5 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 8LL))(v5);
      }
    }
    v72 = 0;
    (*(void (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)v68 + 32LL))(v68, &v72);
    *(_QWORD *)&v66 = 0;
    traits_2_unsigned_short = (__int16 *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                           L"PolicyReportHash",
                                           word_1800F9CE2,
                                           0);
    if ( traits_2_unsigned_short == word_1800F9CE2
      || (v9 = ((char *)traits_2_unsigned_short - (char *)L"PolicyReportHash") >> 1, v9 == -1) )
    {
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC9,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
        v7);
    }
    *(_QWORD *)&v67 = L"PolicyReportHash";
    *((_QWORD *)&v67 + 1) = v9;
    v65 = 0u;
    *(_QWORD *)&v64 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
    v10 = -1;
    do
      ++v10;
    while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v10] );
    *((_QWORD *)&v64 + 1) = v10;
    SystemValueOrDefault = SystemInterface::Registry::GetSystemValueOrDefault(
                             v8,
                             (unsigned int)&v64,
                             (unsigned int)&v65,
                             (unsigned int)&v67,
                             (__int64)&v66);
    v12 = 1;
    v13 = 0;
    v14 = *(unsigned __int8 (__fastcall **)(__int64, __int128 *, __int128 *, __int128 *))(*(_QWORD *)v72 + 32LL);
    v15 = (int *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                   L"PolicyReportTimestamp",
                   &dword_1800F9D14,
                   0);
    if ( v15 == &dword_1800F9D14 || (v18 = ((char *)v15 - (char *)L"PolicyReportTimestamp") >> 1, v18 == -1) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC9,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
        v16);
    *(_QWORD *)&v64 = L"PolicyReportTimestamp";
    *((_QWORD *)&v64 + 1) = v18;
    v65 = 0u;
    *(_QWORD *)&v67 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
    v19 = -1;
    do
      ++v19;
    while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v19] );
    *((_QWORD *)&v67 + 1) = v19;
    if ( v14(v17, &v67, &v65, &v64) )
    {
      v20 = (int *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                     L"PolicyReportTimestamp",
                     &dword_1800F9D14,
                     0);
      if ( v20 == &dword_1800F9D14 || (v23 = ((char *)v20 - (char *)L"PolicyReportTimestamp") >> 1, v23 == -1) )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xC9,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
          v21);
      *(_QWORD *)&v64 = L"PolicyReportTimestamp";
      *((_QWORD *)&v64 + 1) = v23;
      v65 = 0u;
      *(_QWORD *)&v67 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
      v24 = -1;
      do
        ++v24;
      while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v24] );
      *((_QWORD *)&v67 + 1) = v24;
      v66 = v67;
      SystemInterface::Registry::GetSystemTime(
        v22,
        (unsigned int)&v67,
        (unsigned int)&v66,
        (unsigned int)&v65,
        (__int64)&v64);
      v25 = *(__int64 (__fastcall **)(__int64, __int128 *, __int128 *))(**(_QWORD **)(*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)v68 + 40LL))(
                                                                                       v68,
                                                                                       &v65)
                                                                      + 56LL);
      LODWORD(v66) = 7;
      v26 = (int *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                     L"PolicyReportingIntervalInDays",
                     &dword_1800F9D54,
                     0);
      if ( v26 == &dword_1800F9D54 || (v29 = ((char *)v26 - (char *)L"PolicyReportingIntervalInDays") >> 1, v29 == -1) )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xC9,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
          v27);
      *(_QWORD *)&v64 = L"PolicyReportingIntervalInDays";
      *((_QWORD *)&v64 + 1) = v29;
      v71 = v25(v28, &v64, &v66);
      v30 = (volatile signed __int32 *)*((_QWORD *)&v65 + 1);
      if ( *((_QWORD *)&v65 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v65 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v30)(v30);
          if ( _InterlockedExchangeAdd(v30 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v30 + 8LL))(v30);
        }
      }
      v31 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)v68 + 64LL))(v68, &v64);
      v32 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v31 + 168LL))(*v31);
      v33 = (volatile signed __int32 *)*((_QWORD *)&v64 + 1);
      if ( *((_QWORD *)&v64 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v64 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v33)(v33);
          if ( _InterlockedExchangeAdd(v33 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v33 + 8LL))(v33);
        }
      }
      if ( v32 )
        v71 = 1;
      v34 = (__int64 **)(*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)v68 + 24LL))(v68, &v64);
      v35 = *v34;
      v36 = **v34;
      LODWORD(v66) = 2 * v71;
      (*(void (__fastcall **)(__int64 *, int *, __int128 *))(v36 + 56))(v35, &v71, &v66);
      v37 = (volatile signed __int32 *)*((_QWORD *)&v64 + 1);
      if ( *((_QWORD *)&v64 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v64 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v37)(v37);
          if ( _InterlockedExchangeAdd(v37 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v37 + 8LL))(v37);
        }
      }
      *(_QWORD *)&v66 = 0;
      GetSystemTimePreciseAsFileTime(&v66);
      v38 = ((unsigned __int64)DWORD1(v66) << 32) - 116444736000000000LL + (unsigned int)v66;
      if ( (_QWORD)v67 != v38 )
      {
        v39 = 1;
        if ( (__int64)v67 < v38 )
          v39 = -1;
        if ( v39 > 0 )
          goto LABEL_41;
      }
      v40 = v67 + 864000000000LL * v71;
      *(_QWORD *)&v66 = 0;
      GetSystemTimePreciseAsFileTime(&v66);
      if ( v40 >= (__int64)((unsigned int)v66 + ((unsigned __int64)DWORD1(v66) << 32) - 116444736000000000LL) )
        v12 = 0;
      else
LABEL_41:
        v12 = 1;
    }
    v41 = v73;
    if ( v75 > 7 )
      v41 = (_QWORD *)v73[0];
    v42 = 0xCBF29CE484222325uLL;
    for ( i = 0; i < 2 * v74; ++i )
      v42 = 0x100000001B3LL * (*((unsigned __int8 *)v41 + i) ^ (unsigned __int64)v42);
    if ( v12 || v42 != SystemValueOrDefault )
    {
      v13 = 1;
      v44 = (__int64 **)(*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)v68 + 104LL))(v68, &v65);
      v45 = *v44;
      v46 = **v44;
      v47 = v73;
      if ( v75 > 7 )
        v47 = (_QWORD *)v73[0];
      *(_QWORD *)&v64 = v47;
      *((_QWORD *)&v64 + 1) = v74;
      (*(void (__fastcall **)(__int64 *, __int128 *, __int64, _QWORD))(v46 + 224))(v45, &v64, v76, v77);
      v48 = (volatile signed __int32 *)*((_QWORD *)&v65 + 1);
      if ( *((_QWORD *)&v65 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v65 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v48)(v48);
          if ( _InterlockedExchangeAdd(v48 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v48 + 8LL))(v48);
        }
      }
      v49 = *(void (__fastcall **)(__int64, __int128 *, __int128 *, __int128 *, _QWORD *))(*(_QWORD *)v72 + 64LL);
      v69[0] = v42;
      v70 = 1;
      v50 = (__int16 *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                         L"PolicyReportHash",
                         word_1800F9CE2,
                         0);
      if ( v50 == word_1800F9CE2 || (v53 = ((char *)v50 - (char *)L"PolicyReportHash") >> 1, v53 == -1) )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xC9,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
          v51);
      *(_QWORD *)&v64 = L"PolicyReportHash";
      *((_QWORD *)&v64 + 1) = v53;
      v65 = 0u;
      *(_QWORD *)&v67 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
      v54 = -1;
      do
        ++v54;
      while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v54] );
      *((_QWORD *)&v67 + 1) = v54;
      v49(v52, &v67, &v65, &v64, v69);
      if ( v70 != -1 && v70 && v70 != 1 )
        std::wstring::~wstring(v69);
      v55 = v72;
      *(_QWORD *)&v66 = 0;
      GetSystemTimePreciseAsFileTime(&v66);
      *(_QWORD *)&v67 = ((unsigned __int64)DWORD1(v66) << 32) - 116444736000000000LL + (unsigned int)v66;
      v56 = (int *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                     L"PolicyReportTimestamp",
                     &dword_1800F9D14,
                     0);
      if ( v56 == &dword_1800F9D14 || (v59 = ((__int64)v56 - v58) >> 1, v59 == -1) )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xC9,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
          v57);
      *(_QWORD *)&v64 = v58;
      *((_QWORD *)&v64 + 1) = v59;
      v65 = 0u;
      *(_QWORD *)&v66 = SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
      v60 = -1;
      do
        ++v60;
      while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v60] );
      *((_QWORD *)&v66 + 1) = v60;
      SystemInterface::Registry::SetSystemTime(v55, &v66, &v65, &v64, &v67);
    }
    *a2 = v13;
    v61 = (volatile signed __int32 *)*((_QWORD *)&v72 + 1);
    if ( *((_QWORD *)&v72 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v72 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *, _QWORD *))v61)(v61, v41);
        if ( _InterlockedExchangeAdd(v61 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v61 + 8LL))(v61);
      }
    }
    std::wstring::~wstring(v73);
    v62 = (volatile signed __int32 *)*((_QWORD *)&v68 + 1);
    if ( *((_QWORD *)&v68 + 1)
      && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v68 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v62)(v62);
      if ( _InterlockedExchangeAdd(v62 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v62 + 8LL))(v62);
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x280,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\Orchestrator.cpp",
      (const char *)0x80070057LL,
      v63);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18000e120  mov     [rsp+arg_0], rbx
0x18000e125  mov     [rsp+arg_10], rsi
0x18000e12a  push    rdi
0x18000e12b  push    r12
0x18000e12d  push    r13
0x18000e12f  push    r14
0x18000e131  push    r15
0x18000e133  sub     rsp, 100h
0x18000e13a  mov     rax, cs:__security_cookie
0x18000e141  xor     rax, rsp
0x18000e144  mov     [rsp+128h+var_38], rax
0x18000e14c  mov     r12, rdx
0x18000e14f  xor     r14d, r14d
0x18000e152  test    rdx, rdx
0x18000e155  jnz     short loc_18000E17F
0x18000e157  mov     rcx, [rsp+128h]; this
0x18000e15f  mov     ebx, 80070057h
0x18000e164  mov     r9d, ebx; char *
0x18000e167  lea     r8, aCW1SSrcOrchest_14; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x18000e16e  mov     edx, 280h; void *
0x18000e173  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e178  mov     eax, ebx
0x18000e17a  jmp     loc_18000EA46
0x18000e17f  xorps   xmm0, xmm0
0x18000e182  movups  [rsp+128h+var_B8], xmm0
0x18000e187  lea     rcx, [rsp+128h+var_B8]
0x18000e18c  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x18000e191  nop
0x18000e192  mov     rcx, qword ptr [rsp+128h+var_B8]
0x18000e197  mov     rax, [rcx]
0x18000e19a  lea     rdx, [rsp+128h+var_F8]
0x18000e19f  mov     rax, [rax]
0x18000e1a2  call    _guard_dispatch_icall
0x18000e1a7  nop
0x18000e1a8  mov     rcx, [rax]
0x18000e1ab  mov     rax, [rcx]
0x18000e1ae  lea     rdx, [rsp+128h+var_68]
0x18000e1b6  mov     rax, [rax+168h]
0x18000e1bd  call    _guard_dispatch_icall
0x18000e1c2  nop
0x18000e1c3  mov     rdi, qword ptr [rsp+128h+var_F8+8]
0x18000e1c8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000e1cc  test    rdi, rdi
0x18000e1cf  jz      short loc_18000E204
0x18000e1d1  mov     eax, ebx
0x18000e1d3  lock xadd [rdi+8], eax
0x18000e1d8  add     eax, ebx
0x18000e1da  jnz     short loc_18000E204
0x18000e1dc  mov     rax, [rdi]
0x18000e1df  mov     rcx, rdi
0x18000e1e2  mov     rax, [rax]
0x18000e1e5  call    _guard_dispatch_icall
0x18000e1ea  mov     eax, ebx
0x18000e1ec  lock xadd [rdi+0Ch], eax
0x18000e1f1  add     eax, ebx
0x18000e1f3  jnz     short loc_18000E204
0x18000e1f5  mov     rax, [rdi]
0x18000e1f8  mov     rcx, rdi
0x18000e1fb  mov     rax, [rax+8]
0x18000e1ff  call    _guard_dispatch_icall
0x18000e204  xorps   xmm0, xmm0
0x18000e207  movups  [rsp+128h+var_78], xmm0
0x18000e20f  mov     rcx, qword ptr [rsp+128h+var_B8]
0x18000e214  mov     rax, [rcx]
0x18000e217  lea     rdx, [rsp+128h+var_78]
0x18000e21f  mov     rax, [rax+20h]
0x18000e223  call    _guard_dispatch_icall
0x18000e228  nop
0x18000e229  mov     r11, qword ptr [rsp+128h+var_78]
0x18000e231  mov     qword ptr [rsp+128h+var_D8], r14
0x18000e236  xor     r8d, r8d
0x18000e239  lea     rsi, word_1800F9CE2
0x18000e240  mov     rdx, rsi
0x18000e243  lea     rdi, aPolicyreportha; "PolicyReportHash"
0x18000e24a  mov     rcx, rdi
0x18000e24d  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x18000e252  cmp     rax, rsi
0x18000e255  jz      loc_18000EAF5
0x18000e25b  sub     rax, rdi
0x18000e25e  sar     rax, 1
0x18000e261  cmp     rax, rbx
0x18000e264  jz      loc_18000EAF5
0x18000e26a  mov     qword ptr [rsp+128h+var_C8], rdi
0x18000e26f  mov     qword ptr [rsp+128h+var_C8+8], rax
0x18000e274  mov     qword ptr [rsp+128h+var_E8], r14
0x18000e279  mov     qword ptr [rsp+128h+var_E8+8], r14
0x18000e27e  mov     rcx, cs:?USOCURRENTVERSIONROOT_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID
0x18000e285  mov     qword ptr [rsp+128h+var_F8], rcx
0x18000e28a  mov     rax, rbx
0x18000e28d  inc     rax
0x18000e290  cmp     [rcx+rax*2], r14w
0x18000e295  jnz     short loc_18000E28D
0x18000e297  mov     qword ptr [rsp+128h+var_F8+8], rax
0x18000e29c  movups  xmm0, [rsp+128h+var_C8]
0x18000e2a1  movdqu  [rsp+128h+var_C8], xmm0
0x18000e2a7  movaps  xmm1, [rsp+128h+var_E8]
0x18000e2ac  movdqa  [rsp+128h+var_E8], xmm1
0x18000e2b2  movaps  xmm0, [rsp+128h+var_F8]
0x18000e2b7  movdqa  [rsp+128h+var_F8], xmm0
0x18000e2bd  lea     rax, [rsp+128h+var_D8]
0x18000e2c2  mov     qword ptr [rsp+128h+var_108], rax
0x18000e2c7  lea     r9, [rsp+128h+var_C8]
0x18000e2cc  lea     r8, [rsp+128h+var_E8]
0x18000e2d1  lea     rdx, [rsp+128h+var_F8]
0x18000e2d6  mov     rcx, r11
0x18000e2d9  call    ?GetSystemValueOrDefault@Registry@SystemInterface@@QEAA_KV?$basic_zstring_view@_W@wil@@00AEB_K@Z; SystemInterface::Registry::GetSystemValueOrDefault(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,unsigned __int64 const &)
0x18000e2de  mov     r15, rax
0x18000e2e1  mov     dil, 1
0x18000e2e4  mov     r13b, r14b
0x18000e2e7  mov     r11, qword ptr [rsp+128h+var_78]
0x18000e2ef  mov     rcx, [r11]
0x18000e2f2  mov     rsi, [rcx+20h]
0x18000e2f6  xor     r8d, r8d
0x18000e2f9  lea     rdx, dword_1800F9D14
0x18000e300  lea     rcx, aPolicyreportti; "PolicyReportTimestamp"
0x18000e307  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x18000e30c  lea     rcx, dword_1800F9D14
0x18000e313  cmp     rax, rcx
0x18000e316  jz      loc_18000EADB
0x18000e31c  lea     rcx, aPolicyreportti; "PolicyReportTimestamp"
0x18000e323  sub     rax, rcx
0x18000e326  sar     rax, 1
0x18000e329  cmp     rax, rbx
0x18000e32c  jz      loc_18000EADB
0x18000e332  mov     qword ptr [rsp+128h+var_F8], rcx
0x18000e337  mov     qword ptr [rsp+128h+var_F8+8], rax
0x18000e33c  mov     qword ptr [rsp+128h+var_E8], r14
0x18000e341  mov     qword ptr [rsp+128h+var_E8+8], r14
0x18000e346  mov     rax, cs:?USOCURRENTVERSIONROOT_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID
0x18000e34d  mov     qword ptr [rsp+128h+var_C8], rax
0x18000e352  mov     rdx, rbx
0x18000e355  inc     rdx
0x18000e358  cmp     [rax+rdx*2], r14w
0x18000e35d  jnz     short loc_18000E355
0x18000e35f  mov     qword ptr [rsp+128h+var_C8+8], rdx
0x18000e364  movups  xmm0, [rsp+128h+var_F8]
0x18000e369  movdqu  [rsp+128h+var_F8], xmm0
0x18000e36f  movaps  xmm1, [rsp+128h+var_E8]
0x18000e374  movdqa  [rsp+128h+var_E8], xmm1
0x18000e37a  movaps  xmm0, [rsp+128h+var_C8]
0x18000e37f  movdqa  [rsp+128h+var_C8], xmm0
0x18000e385  lea     r9, [rsp+128h+var_F8]
0x18000e38a  lea     r8, [rsp+128h+var_E8]
0x18000e38f  lea     rdx, [rsp+128h+var_C8]
0x18000e394  mov     rcx, r11
0x18000e397  mov     rax, rsi
0x18000e39a  call    _guard_dispatch_icall
0x18000e39f  test    al, al
0x18000e3a1  jz      loc_18000E6B4
0x18000e3a7  mov     r11, qword ptr [rsp+128h+var_78]
0x18000e3af  xor     r8d, r8d
0x18000e3b2  lea     rsi, dword_1800F9D14
0x18000e3b9  mov     rdx, rsi
0x18000e3bc  lea     rdi, aPolicyreportti; "PolicyReportTimestamp"
0x18000e3c3  mov     rcx, rdi
0x18000e3c6  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x18000e3cb  cmp     rax, rsi
0x18000e3ce  jz      loc_18000EA8D
0x18000e3d4  sub     rax, rdi
0x18000e3d7  sar     rax, 1
0x18000e3da  cmp     rax, rbx
0x18000e3dd  jz      loc_18000EA8D
0x18000e3e3  mov     qword ptr [rsp+128h+var_F8], rdi
0x18000e3e8  mov     qword ptr [rsp+128h+var_F8+8], rax
0x18000e3ed  mov     qword ptr [rsp+128h+var_E8], r14
0x18000e3f2  mov     qword ptr [rsp+128h+var_E8+8], r14
0x18000e3f7  mov     rcx, cs:?USOCURRENTVERSIONROOT_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID
0x18000e3fe  mov     qword ptr [rsp+128h+var_C8], rcx
0x18000e403  mov     rax, rbx
0x18000e406  inc     rax
0x18000e409  cmp     [rcx+rax*2], r14w
0x18000e40e  jnz     short loc_18000E406
0x18000e410  mov     qword ptr [rsp+128h+var_C8+8], rax
0x18000e415  movups  xmm0, [rsp+128h+var_F8]
0x18000e41a  movdqu  [rsp+128h+var_F8], xmm0
0x18000e420  movaps  xmm1, [rsp+128h+var_E8]
0x18000e425  movdqa  [rsp+128h+var_E8], xmm1
0x18000e42b  movaps  xmm0, [rsp+128h+var_C8]
0x18000e430  movdqa  [rsp+128h+var_D8], xmm0
0x18000e436  lea     rax, [rsp+128h+var_F8]
0x18000e43b  mov     qword ptr [rsp+128h+var_108], rax
0x18000e440  lea     r9, [rsp+128h+var_E8]
0x18000e445  lea     r8, [rsp+128h+var_D8]
0x18000e44a  lea     rdx, [rsp+128h+var_C8]
0x18000e44f  mov     rcx, r11
0x18000e452  call    ?GetSystemTime@Registry@SystemInterface@@QEAA?AV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@V?$basic_zstring_view@_W@wil@@00@Z; SystemInterface::Registry::GetSystemTime(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x18000e457  mov     rcx, qword ptr [rsp+128h+var_B8]
0x18000e45c  mov     rax, [rcx]
0x18000e45f  lea     rdx, [rsp+128h+var_E8]
0x18000e464  mov     rax, [rax+28h]
0x18000e468  call    _guard_dispatch_icall
0x18000e46d  nop
0x18000e46e  mov     r11, [rax]
0x18000e471  mov     rax, [r11]
0x18000e474  mov     rdi, [rax+38h]
0x18000e478  mov     dword ptr [rsp+128h+var_D8], 7
0x18000e480  xor     r8d, r8d
0x18000e483  lea     rsi, dword_1800F9D54
0x18000e48a  mov     rdx, rsi
0x18000e48d  lea     rcx, aPolicyreportin; "PolicyReportingIntervalInDays"
0x18000e494  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x18000e499  cmp     rax, rsi
0x18000e49c  jz      loc_18000EA73
0x18000e4a2  lea     rcx, aPolicyreportin; "PolicyReportingIntervalInDays"
0x18000e4a9  sub     rax, rcx
0x18000e4ac  sar     rax, 1
0x18000e4af  cmp     rax, rbx
0x18000e4b2  jz      loc_18000EA73
0x18000e4b8  mov     qword ptr [rsp+128h+var_F8], rcx
0x18000e4bd  mov     qword ptr [rsp+128h+var_F8+8], rax
0x18000e4c2  movaps  xmm0, [rsp+128h+var_F8]
0x18000e4c7  movdqa  [rsp+128h+var_F8], xmm0
0x18000e4cd  lea     r8, [rsp+128h+var_D8]
0x18000e4d2  lea     rdx, [rsp+128h+var_F8]
0x18000e4d7  mov     rcx, r11
0x18000e4da  mov     rax, rdi
0x18000e4dd  call    _guard_dispatch_icall
0x18000e4e2  mov     [rsp+128h+var_80], eax
0x18000e4e9  mov     rdi, qword ptr [rsp+128h+var_E8+8]
0x18000e4ee  test    rdi, rdi
0x18000e4f1  jz      short loc_18000E526
0x18000e4f3  mov     eax, ebx
0x18000e4f5  lock xadd [rdi+8], eax
0x18000e4fa  add     eax, ebx
0x18000e4fc  jnz     short loc_18000E526
0x18000e4fe  mov     rax, [rdi]
0x18000e501  mov     rcx, rdi
0x18000e504  mov     rax, [rax]
0x18000e507  call    _guard_dispatch_icall
0x18000e50c  mov     eax, ebx
0x18000e50e  lock xadd [rdi+0Ch], eax
0x18000e513  add     eax, ebx
0x18000e515  jnz     short loc_18000E526
0x18000e517  mov     rax, [rdi]
0x18000e51a  mov     rcx, rdi
0x18000e51d  mov     rax, [rax+8]
0x18000e521  call    _guard_dispatch_icall
0x18000e526  mov     rcx, qword ptr [rsp+128h+var_B8]
0x18000e52b  mov     rax, [rcx]
0x18000e52e  lea     rdx, [rsp+128h+var_F8]
0x18000e533  mov     rax, [rax+40h]
0x18000e537  call    _guard_dispatch_icall
0x18000e53c  nop
0x18000e53d  mov     rcx, [rax]
0x18000e540  mov     rax, [rcx]
0x18000e543  mov     rax, [rax+0A8h]
0x18000e54a  call    _guard_dispatch_icall
0x18000e54f  mov     sil, al
0x18000e552  mov     rdi, qword ptr [rsp+128h+var_F8+8]
0x18000e557  test    rdi, rdi
0x18000e55a  jz      short loc_18000E58F
0x18000e55c  mov     ecx, ebx
0x18000e55e  lock xadd [rdi+8], ecx
0x18000e563  add     ecx, ebx
0x18000e565  jnz     short loc_18000E58F
0x18000e567  mov     rax, [rdi]
0x18000e56a  mov     rcx, rdi
0x18000e56d  mov     rax, [rax]
0x18000e570  call    _guard_dispatch_icall
0x18000e575  mov     eax, ebx
0x18000e577  lock xadd [rdi+0Ch], eax
0x18000e57c  add     eax, ebx
0x18000e57e  jnz     short loc_18000E58F
0x18000e580  mov     rax, [rdi]
0x18000e583  mov     rcx, rdi
0x18000e586  mov     rax, [rax+8]
0x18000e58a  call    _guard_dispatch_icall
0x18000e58f  test    sil, sil
0x18000e592  jz      short loc_18000E59F
0x18000e594  mov     [rsp+128h+var_80], 1
0x18000e59f  mov     rcx, qword ptr [rsp+128h+var_B8]
0x18000e5a4  mov     rax, [rcx]
0x18000e5a7  lea     rdx, [rsp+128h+var_F8]
0x18000e5ac  mov     rax, [rax+18h]
0x18000e5b0  call    _guard_dispatch_icall
0x18000e5b5  nop
0x18000e5b6  mov     rcx, [rax]
0x18000e5b9  mov     rax, [rcx]
0x18000e5bc  mov     edx, [rsp+128h+var_80]
0x18000e5c3  add     edx, edx
0x18000e5c5  mov     dword ptr [rsp+128h+var_D8], edx
0x18000e5c9  lea     r8, [rsp+128h+var_D8]
0x18000e5ce  lea     rdx, [rsp+128h+var_80]
0x18000e5d6  mov     rax, [rax+38h]
0x18000e5da  call    _guard_dispatch_icall
0x18000e5df  nop
0x18000e5e0  mov     rdi, qword ptr [rsp+128h+var_F8+8]
0x18000e5e5  test    rdi, rdi
0x18000e5e8  jz      short loc_18000E61D
0x18000e5ea  mov     eax, ebx
0x18000e5ec  lock xadd [rdi+8], eax
0x18000e5f1  add     eax, ebx
0x18000e5f3  jnz     short loc_18000E61D
0x18000e5f5  mov     rax, [rdi]
0x18000e5f8  mov     rcx, rdi
0x18000e5fb  mov     rax, [rax]
0x18000e5fe  call    _guard_dispatch_icall
0x18000e603  mov     eax, ebx
0x18000e605  lock xadd [rdi+0Ch], eax
0x18000e60a  add     eax, ebx
  ... truncated ...
```
