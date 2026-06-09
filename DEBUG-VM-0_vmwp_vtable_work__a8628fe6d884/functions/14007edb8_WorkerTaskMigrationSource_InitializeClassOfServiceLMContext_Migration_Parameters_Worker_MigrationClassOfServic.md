# WorkerTaskMigrationSource::InitializeClassOfServiceLMContext(Migration::Parameters::Worker::MigrationClassOfServiceParams)

- ea: `0x14007edb8`
- end: `0x14007f3e4`
- name: `?InitializeClassOfServiceLMContext@WorkerTaskMigrationSource@@AEAAXUMigrationClassOfServiceParams@Worker@Parameters@Migration@@@Z`
- size: `1580`
- prototype: `__int64 __fastcall(__int64, _BOOL8)`
- caller_count: `1`
- callee_count: `24`
- tags: `reparse_path, registry_config, loader_planting, service_task`

## callers

- `0x14021d59c`

## callees

- `0x140031c88`
- `0x140042240`
- `0x1400549dc`
- `0x14005b628`
- `0x140066760`
- `0x14006af38`
- `0x14007e580`
- `0x14007edb8`
- `0x14007f3f0`
- `0x14007f44c`
- `0x1400c5a1c`
- `0x140111070`
- `0x14011ffc8`
- `0x140120064`
- `0x140120090`
- `0x140132940`
- `0x1401335fc`
- `0x14014d700`
- `0x14014db50`
- `0x14014db80`
- `0x140219cc4`
- `0x14021bdc8`
- `0x14021ca80`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x14007ef58`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x14007ef96`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x14007ef58`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x14007ef96`
- `vid!VidOpenStatisticsHandle` at `0x14007ee36`
- `vid!VidOpenStatisticsHandle` at `0x14007ee36`
- `vid!VidGetSystemInformation` at `0x14007efe0`
- `vid!VidGetSystemInformation` at `0x14007f079`
- `vid!VidGetSystemInformation` at `0x14007efe0`
- `vid!VidGetSystemInformation` at `0x14007f079`

## string_xrefs

- `0x14007eecd`: `onecore\vm\worker\migration\workertaskmigrationsource.cpp`
- `0x14007eeb7`: `Class Of Service Index is undefined`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall WorkerTaskMigrationSource::InitializeClassOfServiceLMContext(__int64 a1, _BOOL8 a2)
{
  __int64 v2; // r14
  __int64 v4; // rcx
  void *v5; // rbx
  __int64 ClassOfServiceIndex; // rax
  int v7; // eax
  int MbaInitialThrottlePercentage; // r15d
  char **MbaThrottleStrategy; // rax
  char **v10; // rcx
  int v11; // eax
  char **v12; // rcx
  const char *v13; // r9
  const char *v14; // r9
  unsigned int v15; // eax
  char v16; // r8
  __int64 v17; // rcx
  unsigned __int64 v18; // rdx
  __int64 v19; // rcx
  double v20; // xmm1_8
  int v21; // eax
  const struct Vml::ExceptionTraceParameters *v22; // r8
  const char *v23; // rax
  int v25; // [rsp+20h] [rbp-518h]
  char *v26; // [rsp+30h] [rbp-508h]
  char *v27; // [rsp+30h] [rbp-508h]
  __int64 v28; // [rsp+38h] [rbp-500h]
  void *v29; // [rsp+50h] [rbp-4E8h] BYREF
  _BYTE *v30; // [rsp+58h] [rbp-4E0h]
  _BYTE v31[8]; // [rsp+60h] [rbp-4D8h] BYREF
  char *v32[4]; // [rsp+68h] [rbp-4D0h] BYREF
  _BOOL8 v33; // [rsp+88h] [rbp-4B0h]
  __int128 v34; // [rsp+90h] [rbp-4A8h] BYREF
  char *v35[3]; // [rsp+A0h] [rbp-498h] BYREF
  unsigned __int64 v36; // [rsp+B8h] [rbp-480h]
  __int128 v37; // [rsp+C0h] [rbp-478h] BYREF
  char *v38[2]; // [rsp+D0h] [rbp-468h]
  __int128 v39; // [rsp+E0h] [rbp-458h] BYREF
  _QWORD v40[130]; // [rsp+F0h] [rbp-448h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+538h] [rbp+0h]

  v2 = a2;
  v33 = a2;
  v34 = 0;
  VmMigrationSettings::VmMigrationSettings((VmMigrationSettings *)&v34, a2);
  LOBYTE(v4) = VmMigrationSettings::IsMemoryBandwidthAllocationEnabled((VmMigrationSettings *)&v34);
  if ( *(_BYTE *)(v2 + 9) )
    LOBYTE(v4) = *(_BYTE *)(v2 + 8);
  v30 = (_BYTE *)(a1 + 696);
  *(_BYTE *)(a1 + 696) = v4;
  if ( (_BYTE)v4 )
  {
    v5 = (void *)VidOpenStatisticsHandle(v4);
    v29 = v5;
    v37 = 0;
    *(_OWORD *)v38 = 0;
    v39 = 0;
    memset_0(v40, 0, 0x408u);
    try
    {
      ClassOfServiceIndex = VmMigrationSettings::GetClassOfServiceIndex(&v34, v31);
      if ( *(_BYTE *)(ClassOfServiceIndex + 4) )
        v7 = *(_DWORD *)ClassOfServiceIndex;
      else
        v7 = -1;
      if ( *(_BYTE *)(v2 + 4) )
        v7 = *(_DWORD *)v2;
      *(_DWORD *)(a1 + 700) = v7;
      wil::details::in1diag3::Throw_HrIfMsg(
        retaddr,
        (void *)0x1137,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
        (const char *)0x8007000DLL,
        v7 == -1,
        (bool)"Class Of Service Index is undefined",
        v26);
      MbaInitialThrottlePercentage = VmMigrationSettings::GetMbaInitialThrottlePercentage((VmMigrationSettings *)&v34);
      if ( *(_BYTE *)(v2 + 60) )
        MbaInitialThrottlePercentage = *(_DWORD *)(v2 + 56);
      MbaThrottleStrategy = VmMigrationSettings::GetMbaThrottleStrategy((__int64)&v34, v32);
      vmstd::optional<std::wstring>::value_or<std::wstring>(v2 + 16, v35, MbaThrottleStrategy);
      std::wstring::_Tidy_deallocate(v32);
      v10 = v35;
      if ( v36 > 7 )
        v10 = (char **)v35[0];
      if ( (unsigned int)_o__wcsnicmp(v10, L"Linear", 7) )
      {
        v12 = v35;
        if ( v36 > 7 )
          v12 = (char **)v35[0];
        if ( (unsigned int)_o__wcsnicmp(v12, L"Adaptive", 9) )
        {
          v23 = (const char *)v35;
          if ( v36 > 7 )
            v23 = v35[0];
          wil::details::in1diag3::Throw_HrMsg(
            retaddr,
            (void *)0x1146,
            (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
            (const char *)0x80070057LL,
            (int)"Invalid MBA throttle strategy:%ws",
            v23);
        }
        v11 = 2;
      }
      else
      {
        v11 = 1;
      }
      *(_DWORD *)(a1 + 704) = v11;
      if ( !(unsigned int)VidGetSystemInformation(v5, 3, 0) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x114E,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
          v13);
      wil::details::in1diag3::Throw_HrIfMsg(
        retaddr,
        (void *)0x1153,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
        (const char *)0x80070032LL,
        (v37 & 0x20) == 0,
        (bool)"MBA is not supported on this system",
        0);
      LODWORD(v39) = 1;
      if ( !(unsigned int)VidGetSystemInformation(v5, 4, &v39) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x115E,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
          v14);
      wil::details::in1diag3::Throw_HrIfMsg(
        retaddr,
        (void *)0x1164,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
        (const char *)0x80004005LL,
        HIDWORD(v38[0]) != LODWORD(v40[0]),
        (bool)"The number of MBA slots is not equal to the number of HV resource control value count. MemoryBandwidthSlot"
              "s:%u, HVResourceControlNumValues:%u",
        (const char *)HIDWORD(v38[0]),
        LODWORD(v40[0]));
      v15 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)(a1 + 16) + 1040LL) + 680LL))(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 1040LL));
      *(_DWORD *)(a1 + 708) = v15;
      v16 = *(_DWORD *)(a1 + 700) >= HIDWORD(v38[0]) || v15 >= HIDWORD(v38[0]);
      LODWORD(v28) = v15;
      LODWORD(v27) = *(_DWORD *)(a1 + 700);
      wil::details::in1diag3::Throw_HrIfMsg(
        retaddr,
        (void *)0x116E,
        (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
        (const char *)0x80004005LL,
        v16,
        (bool)"The LM CLOS or VM allocation id is beyond the MBA slots. LMClosIndex:%u, OriginalVMAllocationId:%u, Memory"
              "BandwidthSlots:%u",
        v27,
        v28,
        HIDWORD(v38[0]));
      v18 = v40[*(unsigned int *)(a1 + 708) + 1];
      *(_QWORD *)(a1 + 728) = v18;
      *(_BYTE *)(a1 + 712) = BYTE4(v38[1]) & 1;
      *(_QWORD *)(a1 + 720) = LODWORD(v38[1]);
      if ( MbaInitialThrottlePercentage )
        v18 = WorkerTaskMigrationSource::CalculateMbaThrottleValue(
                (WorkerTaskMigrationSource *)a1,
                (double)MbaInitialThrottlePercentage);
      *(_QWORD *)(a1 + 752) = v18;
      if ( *(_DWORD *)(a1 + 704) == 1 )
      {
        v19 = *(_QWORD *)(a1 + 720) - v18;
        if ( v19 < 0 )
          v20 = (double)(int)(v19 & 1 | ((unsigned __int64)v19 >> 1))
              + (double)(int)(v19 & 1 | ((unsigned __int64)v19 >> 1));
        else
          v20 = (double)(int)v19;
        *(_QWORD *)(a1 + 744) = WorkerTaskMigrationSource::GetNormalizedMBAThrottleValue(
                                  (WorkerTaskMigrationSource *)a1,
                                  v20 / (double)(*(_DWORD *)(a1 + 672) - *(_DWORD *)(a1 + 680) + 1));
      }
      WorkerTaskMigrationSource::SetHVResourceControl(v17, 1, *(unsigned int *)(a1 + 700), *(_QWORD *)(a1 + 728));
      if ( (v37 & 1) != 0 )
        WorkerTaskMigrationSource::SetProcessorCacheAllocationOnLMClos(
          (WorkerTaskMigrationSource *)a1,
          (struct _HV_RESOURCE_CONTROL_SUPPORT_PROPERTY *)&v37,
          v5);
      v21 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*(_QWORD *)(a1 + 16) + 1040LL) + 688LL))(
              *(_QWORD *)(*(_QWORD *)(a1 + 16) + 1040LL),
              *(unsigned int *)(a1 + 700));
      if ( v21 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1195,
          (unsigned int)"onecore\\vm\\worker\\migration\\workertaskmigrationsource.cpp",
          (const char *)(unsigned int)v21,
          v25);
      if ( (unsigned int)VmlIsDebugTraceEnabled(53730) )
        VmlDebugTraceEx(53730, &off_1402DAEC0);
      std::wstring::_Tidy_deallocate(v35);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int VidCloseStatisticsHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int VidCloseStatisticsHandle(void *)>>(&v29);
    }
    catch ( ... )
    {
      LODWORD(v29) = Vml::GetHResultFromThrownExceptionAndTrace((Vml *)0x41E2, (unsigned __int16)&off_1402DAF68, v22);
      if ( (int)v29 < 0 )
      {
        if ( (unsigned int)VmlIsDebugTraceEnabled(16866) )
          VmlDebugTraceWithError(16866, &off_1402DB0C0, (unsigned int)v29);
        *v30 = 0;
      }
      v2 = v33;
    }
  }
  Vml::VmRegistryKey::Close((Vml::VmRegistryKey *)((char *)&v34 + 8));
  return std::wstring::_Tidy_deallocate(v2 + 16);
}

```

## disassembly

```asm
0x14007edb8  mov     [rsp+arg_10], rbx
0x14007edbd  push    rsi
0x14007edbe  push    r12
0x14007edc0  push    r13
0x14007edc2  push    r14
0x14007edc4  push    r15
0x14007edc6  sub     rsp, 510h
0x14007edcd  mov     rax, cs:__security_cookie
0x14007edd4  xor     rax, rsp
0x14007edd7  mov     [rsp+538h+var_38], rax
0x14007eddf  mov     r14, rdx
0x14007ede2  mov     rsi, rcx
0x14007ede5  mov     [rsp+538h+var_4B0], rdx
0x14007eded  xorps   xmm0, xmm0
0x14007edf0  movups  [rsp+538h+var_4A8], xmm0
0x14007edf8  lea     rcx, [rsp+538h+var_4A8]; this
0x14007ee00  call    ??0VmMigrationSettings@@QEAA@_N@Z; VmMigrationSettings::VmMigrationSettings(bool)
0x14007ee05  nop
0x14007ee06  lea     rcx, [rsp+538h+var_4A8]; this
0x14007ee0e  call    ?IsMemoryBandwidthAllocationEnabled@VmMigrationSettings@@UEBA_NXZ; VmMigrationSettings::IsMemoryBandwidthAllocationEnabled(void)
0x14007ee13  mov     cl, al
0x14007ee15  cmp     byte ptr [r14+9], 0
0x14007ee1a  jz      short loc_14007EE20
0x14007ee1c  mov     cl, [r14+8]
0x14007ee20  lea     rax, [rsi+2B8h]
0x14007ee27  mov     [rsp+538h+var_4E0], rax
0x14007ee2c  mov     [rax], cl
0x14007ee2e  test    cl, cl
0x14007ee30  jz      loc_14007F3A3
0x14007ee36  call    cs:__imp_VidOpenStatisticsHandle
0x14007ee3d  nop     dword ptr [rax+rax+00h]
0x14007ee42  mov     rbx, rax
0x14007ee45  mov     [rsp+538h+var_4E8], rax
0x14007ee4a  xorps   xmm0, xmm0
0x14007ee4d  movups  [rsp+538h+var_478], xmm0
0x14007ee55  movups  xmmword ptr [rsp+538h+var_468], xmm0
0x14007ee5d  movups  [rsp+538h+var_458], xmm0
0x14007ee65  xor     edx, edx; Val
0x14007ee67  mov     r8d, 408h; Size
0x14007ee6d  lea     rcx, [rsp+538h+var_448]; void *
0x14007ee75  call    memset_0
0x14007ee7a  lea     rdx, [rsp+538h+var_4D8]
0x14007ee7f  lea     rcx, [rsp+538h+var_4A8]
0x14007ee87  call    ?GetClassOfServiceIndex@VmMigrationSettings@@UEBA?AV?$optional@I@std@@XZ; VmMigrationSettings::GetClassOfServiceIndex(void)
0x14007ee8c  cmp     byte ptr [rax+4], 0
0x14007ee90  jz      short loc_14007EE96
0x14007ee92  mov     eax, [rax]
0x14007ee94  jmp     short loc_14007EE99
0x14007ee96  or      eax, 0FFFFFFFFh
0x14007ee99  cmp     byte ptr [r14+4], 0
0x14007ee9e  jz      short loc_14007EEA3
0x14007eea0  mov     eax, [r14]
0x14007eea3  mov     [rsi+2BCh], eax
0x14007eea9  cmp     eax, 0FFFFFFFFh
0x14007eeac  setz    al
0x14007eeaf  mov     rcx, [rsp+538h]; this
0x14007eeb7  lea     rdx, aClassOfService; "Class Of Service Index is undefined"
0x14007eebe  mov     [rsp+538h+var_510], rdx; bool
0x14007eec3  mov     [rsp+538h+var_518], al; char
0x14007eec7  mov     r9d, 8007000Dh; char *
0x14007eecd  lea     r13, aOnecoreVmWorke_0; "onecore\\vm\\worker\\migration\\workert"...
0x14007eed4  mov     r8, r13; unsigned int
0x14007eed7  mov     edx, 1137h; void *
0x14007eedc  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x14007eee1  lea     rcx, [rsp+538h+var_4A8]; this
0x14007eee9  call    ?GetMbaInitialThrottlePercentage@VmMigrationSettings@@UEBAIXZ; VmMigrationSettings::GetMbaInitialThrottlePercentage(void)
0x14007eeee  mov     r15d, eax
0x14007eef1  cmp     byte ptr [r14+3Ch], 0
0x14007eef6  jz      short loc_14007EEFC
0x14007eef8  mov     r15d, [r14+38h]
0x14007eefc  lea     rdx, [rsp+538h+var_4D0]
0x14007ef01  lea     rcx, [rsp+538h+var_4A8]
0x14007ef09  call    ?GetMbaThrottleStrategy@VmMigrationSettings@@UEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; VmMigrationSettings::GetMbaThrottleStrategy(void)
0x14007ef0e  nop
0x14007ef0f  lea     rcx, [r14+10h]
0x14007ef13  mov     r8, rax
0x14007ef16  lea     rdx, [rsp+538h+var_498]
0x14007ef1e  call    ??$value_or@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@vmstd@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$QEAV23@@Z; vmstd::optional<std::wstring>::value_or<std::wstring>(std::wstring &&)
0x14007ef23  nop
0x14007ef24  lea     rcx, [rsp+538h+var_4D0]
0x14007ef29  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14007ef2e  lea     rcx, [rsp+538h+var_498]
0x14007ef36  cmp     [rsp+538h+var_480], 7
0x14007ef3f  cmova   rcx, [rsp+538h+var_498]
0x14007ef48  mov     r8d, 7
0x14007ef4e  lea     r12, aLinear; "Linear"
0x14007ef55  mov     rdx, r12
0x14007ef58  call    cs:__imp__o__wcsnicmp
0x14007ef5f  nop     dword ptr [rax+rax+00h]
0x14007ef64  test    eax, eax
0x14007ef66  jnz     short loc_14007EF6F
0x14007ef68  mov     eax, 1
0x14007ef6d  jmp     short loc_14007EFAF
0x14007ef6f  lea     rcx, [rsp+538h+var_498]
0x14007ef77  cmp     [rsp+538h+var_480], 7
0x14007ef80  cmova   rcx, [rsp+538h+var_498]
0x14007ef89  mov     r8d, 9
0x14007ef8f  lea     rdx, aAdaptive; "Adaptive"
0x14007ef96  call    cs:__imp__o__wcsnicmp
0x14007ef9d  nop     dword ptr [rax+rax+00h]
0x14007efa2  test    eax, eax
0x14007efa4  jnz     loc_14007F322
0x14007efaa  mov     eax, 2
0x14007efaf  mov     [rsi+2C0h], eax
0x14007efb5  mov     [rsp+538h+var_508], 0; char *
0x14007efbe  mov     dword ptr [rsp+538h+var_510], 20h ; ' '
0x14007efc6  lea     rax, [rsp+538h+var_478]
0x14007efce  mov     qword ptr [rsp+538h+var_518], rax
0x14007efd3  xor     r9d, r9d
0x14007efd6  xor     r8d, r8d
0x14007efd9  lea     edx, [r9+3]
0x14007efdd  mov     rcx, rbx
0x14007efe0  call    cs:__imp_VidGetSystemInformation
0x14007efe7  nop     dword ptr [rax+rax+00h]
0x14007efec  mov     rcx, [rsp+538h]; this
0x14007eff4  mov     r8, r13; unsigned int
0x14007eff7  test    eax, eax
0x14007eff9  jnz     short loc_14007F005
0x14007effb  mov     edx, 114Eh; void *
0x14007f000  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14007f005  mov     eax, dword ptr [rsp+538h+var_478]
0x14007f00c  shr     eax, 5
0x14007f00f  not     al
0x14007f011  and     al, 1
0x14007f013  mov     rcx, [rsp+538h]; this
0x14007f01b  lea     rdx, aMbaIsNotSuppor; "MBA is not supported on this system"
0x14007f022  mov     [rsp+538h+var_510], rdx; bool
0x14007f027  mov     [rsp+538h+var_518], al; char
0x14007f02b  mov     r9d, 80070032h; char *
0x14007f031  mov     edx, 1153h; void *
0x14007f036  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x14007f03b  mov     dword ptr [rsp+538h+var_458], 1
0x14007f046  mov     [rsp+538h+var_508], 0
0x14007f04f  mov     dword ptr [rsp+538h+var_510], 408h
0x14007f057  lea     rax, [rsp+538h+var_448]
0x14007f05f  mov     qword ptr [rsp+538h+var_518], rax
0x14007f064  mov     r9d, 10h
0x14007f06a  lea     r8, [rsp+538h+var_458]
0x14007f072  lea     edx, [r9-0Ch]
0x14007f076  mov     rcx, rbx
0x14007f079  call    cs:__imp_VidGetSystemInformation
0x14007f080  nop     dword ptr [rax+rax+00h]
0x14007f085  mov     rcx, [rsp+538h]; this
0x14007f08d  test    eax, eax
0x14007f08f  jnz     short loc_14007F09E
0x14007f091  mov     r8, r13; unsigned int
0x14007f094  mov     edx, 115Eh; void *
0x14007f099  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14007f09e  mov     edx, dword ptr [rsp+538h+var_468+4]
0x14007f0a5  mov     rax, [rsp+538h+var_448]
0x14007f0ad  cmp     edx, eax
0x14007f0af  setnz   r8b
0x14007f0b3  mov     rcx, [rsp+538h]; this
0x14007f0bb  mov     dword ptr [rsp+538h+var_500], eax
0x14007f0bf  mov     dword ptr [rsp+538h+var_508], edx; char *
0x14007f0c3  lea     rax, aTheNumberOfMba; "The number of MBA slots is not equal to"...
0x14007f0ca  mov     [rsp+538h+var_510], rax; bool
0x14007f0cf  mov     [rsp+538h+var_518], r8b; char
0x14007f0d4  mov     r9d, 80004005h; char *
0x14007f0da  mov     r8, r13; unsigned int
0x14007f0dd  mov     edx, 1164h; void *
0x14007f0e2  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x14007f0e7  mov     rax, [rsi+10h]
0x14007f0eb  mov     rcx, [rax+410h]
0x14007f0f2  mov     rax, [rcx]
0x14007f0f5  mov     rax, [rax+2A8h]
0x14007f0fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007f101  mov     [rsi+2C4h], eax
0x14007f107  mov     r9d, [rsi+2BCh]
0x14007f10e  mov     edx, dword ptr [rsp+538h+var_468+4]
0x14007f115  cmp     r9d, edx
0x14007f118  jnb     short loc_14007F123
0x14007f11a  cmp     eax, edx
0x14007f11c  jnb     short loc_14007F123
0x14007f11e  xor     r8d, r8d
0x14007f121  jmp     short loc_14007F126
0x14007f123  mov     r8b, 1
0x14007f126  mov     rcx, [rsp+538h]; this
0x14007f12e  mov     dword ptr [rsp+538h+var_4F8], edx
0x14007f132  mov     dword ptr [rsp+538h+var_500], eax
0x14007f136  mov     dword ptr [rsp+538h+var_508], r9d; char *
0x14007f13b  lea     rax, aTheLmClosOrVmA; "The LM CLOS or VM allocation id is beyo"...
0x14007f142  mov     [rsp+538h+var_510], rax; bool
0x14007f147  mov     [rsp+538h+var_518], r8b; int
0x14007f14c  mov     r9d, 80004005h; char *
0x14007f152  mov     r8, r13; unsigned int
0x14007f155  mov     edx, 116Eh; void *
0x14007f15a  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x14007f15f  mov     eax, [rsi+2C4h]
0x14007f165  mov     rdx, [rsp+rax*8+538h+var_440]
0x14007f16d  mov     [rsi+2D8h], rdx
0x14007f174  mov     al, byte ptr [rsp+538h+var_468+0Ch]
0x14007f17b  and     al, 1
0x14007f17d  mov     [rsi+2C8h], al
0x14007f183  mov     eax, dword ptr [rsp+538h+var_468+8]
0x14007f18a  mov     [rsi+2D0h], rax
0x14007f191  test    r15d, r15d
0x14007f194  jz      short loc_14007F1AC
0x14007f196  mov     eax, r15d
0x14007f199  xorps   xmm1, xmm1
0x14007f19c  cvtsi2sd xmm1, rax; double
0x14007f1a1  mov     rcx, rsi; this
0x14007f1a4  call    ?CalculateMbaThrottleValue@WorkerTaskMigrationSource@@AEAA_KN@Z; WorkerTaskMigrationSource::CalculateMbaThrottleValue(double)
0x14007f1a9  mov     rdx, rax
0x14007f1ac  mov     [rsi+2F0h], rdx
0x14007f1b3  cmp     dword ptr [rsi+2C0h], 1
0x14007f1ba  jnz     short loc_14007F210
0x14007f1bc  mov     rcx, [rsi+2D0h]
0x14007f1c3  sub     rcx, rdx
0x14007f1c6  xorps   xmm1, xmm1
0x14007f1c9  js      short loc_14007F1D2
0x14007f1cb  cvtsi2sd xmm1, rcx
0x14007f1d0  jmp     short loc_14007F1E7
0x14007f1d2  mov     rax, rcx
0x14007f1d5  shr     rax, 1
0x14007f1d8  and     ecx, 1
0x14007f1db  or      rax, rcx
0x14007f1de  cvtsi2sd xmm1, rax
0x14007f1e3  addsd   xmm1, xmm1
0x14007f1e7  mov     eax, [rsi+2A0h]
0x14007f1ed  sub     eax, [rsi+2A8h]
0x14007f1f3  inc     eax
0x14007f1f5  xorps   xmm0, xmm0
0x14007f1f8  cvtsi2sd xmm0, rax
0x14007f1fd  divsd   xmm1, xmm0; double
0x14007f201  mov     rcx, rsi; this
0x14007f204  call    ?GetNormalizedMBAThrottleValue@WorkerTaskMigrationSource@@AEAA_KN@Z; WorkerTaskMigrationSource::GetNormalizedMBAThrottleValue(double)
0x14007f209  mov     [rsi+2E8h], rax
0x14007f210  mov     r9, [rsi+2D8h]
0x14007f217  mov     r8d, [rsi+2BCh]
0x14007f21e  mov     edx, 1
0x14007f223  call    ?SetHVResourceControl@WorkerTaskMigrationSource@@AEAAXW4_HV_RESOURCE_CONTROL_TYPE@@I_K@Z; WorkerTaskMigrationSource::SetHVResourceControl(_HV_RESOURCE_CONTROL_TYPE,uint,unsigned __int64)
0x14007f228  test    byte ptr [rsp+538h+var_478], 1
0x14007f230  jz      short loc_14007F245
0x14007f232  mov     r8, rbx; void *
0x14007f235  lea     rdx, [rsp+538h+var_478]; struct _HV_RESOURCE_CONTROL_SUPPORT_PROPERTY *
0x14007f23d  mov     rcx, rsi; this
0x14007f240  call    ?SetProcessorCacheAllocationOnLMClos@WorkerTaskMigrationSource@@AEAAXAEAU_HV_RESOURCE_CONTROL_SUPPORT_PROPERTY@@PEAX@Z; WorkerTaskMigrationSource::SetProcessorCacheAllocationOnLMClos(_HV_RESOURCE_CONTROL_SUPPORT_PROPERTY &,void *)
0x14007f245  mov     rax, [rsi+10h]
0x14007f249  mov     rcx, [rax+410h]
0x14007f250  mov     rax, [rcx]
0x14007f253  mov     edx, [rsi+2BCh]
0x14007f259  mov     rax, [rax+2B0h]
0x14007f260  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007f265  mov     rcx, [rsp+538h]; this
0x14007f26d  test    eax, eax
0x14007f26f  jns     short loc_14007F281
0x14007f271  mov     r9d, eax; char *
0x14007f274  mov     r8, r13; unsigned int
0x14007f277  mov     edx, 1195h; void *
0x14007f27c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14007f281  mov     ebx, 0D1E2h
0x14007f286  mov     ecx, ebx
0x14007f288  call    VmlIsDebugTraceEnabled
0x14007f28d  test    eax, eax
0x14007f28f  jz      short loc_14007F304
0x14007f291  lea     rax, [rsp+538h+var_498]
0x14007f299  cmp     [rsp+538h+var_480], 7
0x14007f2a2  cmova   rax, [rsp+538h+var_498]
0x14007f2ab  lea     rdx, aNonlinear; "NonLinear"
0x14007f2b2  cmp     byte ptr [rsi+2C8h], 0
0x14007f2b9  cmovz   r12, rdx
0x14007f2bd  mov     [rsp+538h+var_4F8], rax
0x14007f2c2  mov     rax, [rsi+2D0h]
0x14007f2c9  mov     [rsp+538h+var_500], rax
0x14007f2ce  mov     rax, [rsi+2F0h]
0x14007f2d5  mov     [rsp+538h+var_508], rax
0x14007f2da  mov     rax, [rsi+2D8h]
0x14007f2e1  mov     [rsp+538h+var_510], rax
0x14007f2e6  mov     qword ptr [rsp+538h+var_518], r12
0x14007f2eb  mov     r9d, r15d
0x14007f2ee  mov     r8d, [rsi+2BCh]
0x14007f2f5  lea     rdx, off_1402DAEC0; "MBA is enabled. Index:%u,InitialThrottl"...
0x14007f2fc  mov     ecx, ebx
0x14007f2fe  call    VmlDebugTraceEx
0x14007f303  nop
0x14007f304  lea     rcx, [rsp+538h+var_498]
0x14007f30c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14007f311  nop
0x14007f312  lea     rcx, [rsp+538h+var_4E8]
0x14007f317  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?VidCloseStatisticsHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&VidCloseStatisticsHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&VidCloseStatisticsHandle(void *)>>(void)
0x14007f31c  nop
0x14007f31d  jmp     loc_14007F3A3
0x14007f322  lea     rax, [rsp+538h+var_498]
0x14007f32a  cmp     [rsp+538h+var_480], 7
0x14007f333  cmova   rax, [rsp+538h+var_498]
0x14007f33c  mov     rcx, [rsp+538h]; this
0x14007f344  mov     [rsp+538h+var_510], rax; char *
0x14007f349  lea     rax, aInvalidMbaThro_0; "Invalid MBA throttle strategy:%ws"
0x14007f350  mov     qword ptr [rsp+538h+var_518], rax; int
0x14007f355  mov     r9d, 80070057h; char *
0x14007f35b  mov     r8, r13; unsigned int
0x14007f35e  mov     edx, 1146h; void *
0x14007f363  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x14007f369  cmp     dword ptr [rsp+538h+var_4E8], 0
0x14007f36e  jge     short loc_14007F39B
0x14007f370  mov     ebx, 41E2h
0x14007f375  mov     ecx, ebx
0x14007f377  call    VmlIsDebugTraceEnabled
0x14007f37c  test    eax, eax
  ... truncated ...
```
