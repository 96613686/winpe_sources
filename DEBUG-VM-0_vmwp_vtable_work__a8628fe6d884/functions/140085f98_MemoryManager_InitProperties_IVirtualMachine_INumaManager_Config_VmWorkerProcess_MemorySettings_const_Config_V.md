# MemoryManager::InitProperties(IVirtualMachine *,INumaManager *,Config::VmWorkerProcess::MemorySettings const &,Config::VmWorkerProcess::NumaSettings const &,Config::VmWorkerProcess::CompatibilitySettings const &,Config::VmWorkerProcess::TopologySettings const &,bool)

- ea: `0x140085f98`
- end: `0x140086a7f`
- name: `?InitProperties@MemoryManager@@AEAAXPEAUIVirtualMachine@@PEAUINumaManager@@AEBUMemorySettings@VmWorkerProcess@Config@@AEBUNumaSettings@56@AEBUCompatibilitySettings@56@AEBUTopologySettings@56@_N@Z`
- size: `2791`
- prototype: `void __fastcall(MemoryManager *__hidden this, struct IVirtualMachine *, struct INumaManager *, const struct Config::VmWorkerProcess::MemorySettings *, const struct Config::VmWorkerProcess::NumaSettings *, const struct Config::VmWorkerProcess::CompatibilitySettings *, const struct Config::VmWorkerProcess::TopologySettings *, bool)`
- caller_count: `1`
- callee_count: `40`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140068010`

## callees

- `0x140033614`
- `0x140033678`
- `0x140033b7c`
- `0x140042240`
- `0x140047ab8`
- `0x140054508`
- `0x140054630`
- `0x140054af0`
- `0x140055de0`
- `0x14005606c`
- `0x14005b628`
- `0x14005eca0`
- `0x14006405c`
- `0x140066760`
- `0x14006af38`
- `0x14007e580`
- `0x140085d04`
- `0x140085f98`
- `0x140086a88`
- `0x140086aa8`
- `0x140086bc0`
- `0x1400996b8`
- `0x14009d7ac`
- `0x1400c5a1c`
- `0x1400d4954`
- `0x1400e52d4`
- `0x1400e758c`
- `0x140120064`
- `0x140123f88`
- `0x140132940`
- `0x140132cec`
- `0x1401335fc`
- `0x14014c5e8`
- `0x14016186c`
- `0x140172cf0`
- `0x1401897b0`
- `0x1401fd5ec`
- `0x140202614`
- `0x140203998`
- `0x1402c2010`

## import_xrefs

- `ntdll!NtPowerInformation` at `0x1400869ba`
- `ntdll!NtPowerInformation` at `0x1400869ba`
- `vid!VidOpenStatisticsHandle` at `0x1400868be`
- `vid!VidOpenStatisticsHandle` at `0x1400868be`
- `vid!VidGetSystemInformation` at `0x140086958`
- `vid!VidGetSystemInformation` at `0x140086958`
- `vid!VidGetPartitionProperty` at `0x140086885`
- `vid!VidGetPartitionProperty` at `0x140086885`

## string_xrefs

- `0x1400868e6`: `Failed to open VID statistics handle`
- `0x14008647c`: `/configuration/settings/topology/shared_memory_mb`
- `0x1400863f6`: `/configuration/settings/topology/direct_file_mapping_mb`
- `0x1400861c9`: `UseSystemPartitionForHvDeposits`
- `0x1400861f7`: `UseSystemPartitionForPhysicalBuffers`
- `0x140086169`: `System\CurrentControlSet\Services\Vid\Parameters\MemoryReserve\Primary`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall MemoryManager::InitProperties(
        MemoryManager *this,
        struct IVirtualMachine *a2,
        struct INumaManager *a3,
        const struct Config::VmWorkerProcess::MemorySettings *a4,
        const struct Config::VmWorkerProcess::NumaSettings *a5,
        const struct Config::VmWorkerProcess::CompatibilitySettings *a6,
        const struct Config::VmWorkerProcess::TopologySettings *a7,
        bool a8)
{
  const struct Config::VmWorkerProcess::MemorySettings *v8; // rsi
  struct IVirtualMachine *v10; // r13
  const struct Config::VmWorkerProcess::NumaSettings *v11; // r15
  __int64 v12; // rax
  std::_Ref_count_base *v13; // r12
  __int64 *v14; // rax
  __int64 v15; // rdx
  const char *v16; // r9
  __int64 v17; // rbx
  __int64 v18; // r8
  const char *v19; // r9
  int v20; // eax
  int v21; // eax
  __int64 v22; // r14
  __int64 v23; // rax
  int v24; // eax
  HKEY v25; // rax
  int v26; // eax
  __int64 v27; // rdx
  __int64 **v28; // rax
  __int64 v29; // rcx
  GpaSpaceBestFitAllocator *v30; // rdx
  _DWORD *v31; // rax
  void **v32; // rbx
  unsigned __int8 VirtualNumaNodeCount; // al
  int v34; // eax
  _QWORD *v35; // rbx
  const unsigned __int16 *v36; // rdx
  unsigned __int64 v37; // rbx
  char *v38; // r14
  __int64 v39; // r8
  unsigned __int64 v40; // rcx
  char *v41; // rax
  size_t v42; // rbx
  unsigned int *v43; // r9
  unsigned int *v44; // rdx
  const struct _GUID *v45; // r8
  const char *v46; // r9
  std::_Ref_count_base *v47; // rbx
  const char *v48; // r9
  bool v49; // bl
  NTSTATUS v50; // eax
  int OutputBufferLength; // [rsp+20h] [rbp-118h]
  int OutputBufferLengtha; // [rsp+20h] [rbp-118h]
  char *v53; // [rsp+28h] [rbp-110h]
  char *v54; // [rsp+28h] [rbp-110h]
  char *v55; // [rsp+28h] [rbp-110h]
  char *v56; // [rsp+30h] [rbp-108h]
  __int64 v57; // [rsp+38h] [rbp-100h]
  std::_Ref_count_base *v58[2]; // [rsp+50h] [rbp-E8h] BYREF
  const struct Config::VmWorkerProcess::MemorySettings *v59; // [rsp+60h] [rbp-D8h]
  const struct Config::VmWorkerProcess::NumaSettings *v60; // [rsp+70h] [rbp-C8h]
  char v61[64]; // [rsp+80h] [rbp-B8h] BYREF
  char OutputBuffer[8]; // [rsp+C0h] [rbp-78h] BYREF
  HKEY phkResult; // [rsp+C8h] [rbp-70h] BYREF
  char *v64; // [rsp+D0h] [rbp-68h] BYREF
  struct IVirtualMachine *v65; // [rsp+D8h] [rbp-60h] BYREF
  __int64 v66; // [rsp+E0h] [rbp-58h] BYREF
  char v67; // [rsp+E8h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  v8 = a4;
  v10 = a2;
  v65 = a2;
  v59 = a4;
  v11 = a5;
  v60 = a5;
  Vml::VmReferencePtr<IVirtualMachine,Vml::VmWeakReferenceTraits>::Reset(&qword_1403C0370);
  Vml::VmReferencePtr<VndCompletionThread,Vml::VmUserReferenceTraits>::Reset(&qword_1403C0378, a3);
  v12 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)qword_1403C0370 + 56LL))(qword_1403C0370, &v66);
  Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>::operator=(&qword_1403C0380, v12);
  Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>::~VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>(&v66);
  byte_1403C05F8 = *((_DWORD *)a7 + 17) == 3;
  v13 = (std::_Ref_count_base *)*((_QWORD *)v8 + 4);
  v58[0] = v13;
  if ( byte_1403C05F8 && *((_QWORD *)a7 + 3) > (unsigned __int64)v13 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x506,
      (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
      (const char *)0x80070057LL,
      OutputBufferLength);
  v14 = Vml::CreateComObject<MemoryBalancerInterface,>(&v66);
  v15 = *v14;
  *v14 = 0;
  Vml::VmComPtr<MemoryBalancerInterface>::Attach<MemoryBalancerInterface>(&qword_1403C0458, v15);
  Vml::VmComPtr<TdxStateMigrationTransfer::TdxStateMigrationTransferObjectSourceImpl>::~VmComPtr<TdxStateMigrationTransfer::TdxStateMigrationTransferObjectSourceImpl>(&v66);
  v17 = qword_1403C0458;
  if ( !qword_1403C0458 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x50A,
      (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
      v16);
  Vml::VmReferencePtr<VndCompletionThread,Vml::VmUserReferenceTraits>::Reset(qword_1403C0458 + 32, qword_1403C0378);
  *(_QWORD *)(v17 + 128) = 0;
  std::wstring::operator=((char ***)(v17 + 88), (char ***)v8 + 6, v18);
  if ( a8 )
  {
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)qword_1403C0370 + 408LL))(qword_1403C0370, &v66);
    *(__int16 *)((char *)&word_1403C0428 + 1) = 257;
    qword_1403C0430 = v66;
    byte_1403C0438 = (v66 & 8) != 0;
    if ( v67 )
    {
      if ( (v66 & 0x60) == 0x20 )
        qword_1403C0430 = v66 & 0xFFFFFFFFFFFFFFF7uLL;
    }
  }
  try
  {
    phkResult = 0;
    if ( (unsigned int)Vml::VmRegistryKey::Open(
                         &phkResult,
                         HKEY_LOCAL_MACHINE,
                         L"System\\CurrentControlSet\\Services\\Vid\\Parameters\\MemoryReserve\\Primary",
                         0x20019u) )
    {
      LODWORD(v64) = 0;
      if ( Vml::VmRegistryKey::QueryValue(
             (Vml::VmRegistryKey *)&phkResult,
             L"AllowSpillingForHvDeposits",
             (unsigned int *)&v64) )
      {
        BYTE1(dword_1403C0658) = (_DWORD)v64 != 0;
      }
      if ( Vml::VmRegistryKey::QueryValue(
             (Vml::VmRegistryKey *)&phkResult,
             L"UseSystemPartitionForHvDeposits",
             (unsigned int *)&v64) )
      {
        BYTE2(dword_1403C0658) = (_DWORD)v64 != 0;
      }
      if ( Vml::VmRegistryKey::QueryValue(
             (Vml::VmRegistryKey *)&phkResult,
             L"UseSystemPartitionForPhysicalBuffers",
             (unsigned int *)&v64) )
      {
        HIBYTE(dword_1403C0658) = (_DWORD)v64 != 0;
      }
    }
    Vml::VmRegistryKey::Close((Vml::VmRegistryKey *)&phkResult);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x548,
      (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
      v19);
    v10 = v65;
    v8 = v59;
    v11 = v60;
    v13 = v58[0];
  }
  *(_OWORD *)v58 = 0;
  VmRepositoryAutoLock::VmRepositoryAutoLock(v58, qword_1403C0380, 0);
  if ( SLODWORD(v58[1]) < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x54D,
      (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
      (const char *)LODWORD(v58[1]),
      OutputBufferLength);
  v20 = (*(__int64 (__fastcall **)(__int64, char **))(*(_QWORD *)qword_1403C0380 + 288LL))(
          qword_1403C0380,
          &dword_1403C03E0);
  if ( v20 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x552,
      (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
      (const char *)(unsigned int)v20,
      OutputBufferLength);
  v21 = (*(__int64 (__fastcall **)(__int64, char **))(*(_QWORD *)qword_1403C0380 + 320LL))(
          qword_1403C0380,
          &dword_1403C03E4);
  if ( v21 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x553,
      (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
      (const char *)(unsigned int)v21,
      OutputBufferLength);
  v22 = 0;
  if ( *((_BYTE *)v8 + 256) )
  {
    BYTE4(qword_1403C05AC) = 1;
    v22 = *((_QWORD *)v8 + 33);
  }
  if ( *((_BYTE *)v8 + 312) )
    BYTE5(qword_1403C05AC) = 1;
  HIBYTE(qword_1403C05AC) = (*(_DWORD *)a6 & 0x80) != 0;
  qword_1403C03A0 = *((_QWORD *)v8 + 5);
  v23 = 0x40000;
  if ( *((_QWORD *)v8 + 23) == 0x40000 )
  {
    if ( (unsigned int)dword_1403C03E0 < 0x803 )
    {
      if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
        VmlDebugTrace(16416, L"Only RS4 or above VMs support huge page.\n");
      LODWORD(v53) = (_DWORD)dword_1403C03E0;
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0x574,
        (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
        (const char *)0x80048016LL,
        (int)"VM version %x does not support huge page.",
        v53);
    }
  }
  else
  {
    v23 = 512;
  }
  qword_1403C05D8 = v23;
  v24 = (int)dword_1403C03E4;
  if ( (_DWORD)dword_1403C03E4 == 8 || (_DWORD)dword_1403C03E4 == 1 )
  {
    phkResult = 0;
    if ( (*(int (__fastcall **)(__int64, const unsigned __int16 *, HKEY *))(*(_QWORD *)qword_1403C0380 + 120LL))(
           qword_1403C0380,
           L"/configuration/settings/topology/direct_file_mapping_mb",
           &phkResult) >= 0 )
    {
      v25 = phkResult;
      if ( ((unsigned __int8)phkResult & 1) != 0 )
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          (void *)0x58A,
          (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
          (const char *)0x80070057LL,
          (int)"directFileMappingMb = %I64u",
          (const char *)phkResult);
      if ( (unsigned __int64)phkResult > 0x10000 )
        v25 = (HKEY)0x10000;
      phkResult = v25;
    }
    v64 = 0;
    v26 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, char **))(*(_QWORD *)qword_1403C0380 + 120LL))(
            qword_1403C0380,
            L"/configuration/settings/topology/shared_memory_mb",
            &v64);
    v27 = (__int64)v64;
    if ( v26 >= 0 )
    {
      if ( ((unsigned __int8)v64 & 1) != 0 )
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          (void *)0x59C,
          (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
          (const char *)0x80070057LL,
          (int)"sharedMemoryMb = %I64u",
          v64);
      if ( (unsigned __int64)v64 > 0x10000 )
        v27 = 0x10000;
    }
    qword_1403C04D8 = (_QWORD)phkResult << 8;
    qword_1403C04E0 = v27 << 8;
    qword_1403C04E8 = (v27 << 8) + ((_QWORD)phkResult << 8);
    v24 = (int)dword_1403C03E4;
  }
  if ( (unsigned int)dword_1403C03E0 >= 0x701 && v24 == 1 )
    byte_1403C05A8 = 0;
  VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v58);
  v28 = std::make_unique<GpaSpaceBestFitAllocator,unsigned __int64 const &,0>((__int64 **)v58);
  v29 = (__int64)*v28;
  *v28 = 0;
  v30 = (GpaSpaceBestFitAllocator *)qword_1403C0518;
  qword_1403C0518 = v29;
  if ( v30 )
    std::default_delete<GpaSpaceBestFitAllocator>::operator()(v29, v30);
  std::unique_ptr<GpaSpaceBestFitAllocator>::~unique_ptr<GpaSpaceBestFitAllocator>(v58);
  v31 = operator new(0x48u);
  *(_OWORD *)v31 = 0;
  v31[2] = 1;
  v31[3] = 1;
  *(_QWORD *)v31 = &std::_Ref_count_obj2<RamUsage>::`vftable';
  *((_QWORD *)v31 + 3) = 0;
  *((_QWORD *)v31 + 4) = 0;
  *((_QWORD *)v31 + 5) = 0;
  *((_QWORD *)v31 + 6) = 0;
  *((_QWORD *)v31 + 7) = 0;
  *((_QWORD *)v31 + 8) = 0;
  v58[0] = (std::_Ref_count_base *)(v31 + 4);
  v58[1] = (std::_Ref_count_base *)v31;
  __4__shared_ptr___CBX_std__QEAAAEAV01___QEAV01__Z(&qword_1403C04B8, v58);
  if ( v58[1] )
    std::_Ref_count_base::_Decref(v58[1]);
  v32 = (void **)qword_1403C04B8;
  VirtualNumaNodeCount = MemoryManager::GetVirtualNumaNodeCount((MemoryManager *)&MemoryManager::m_Instance);
  v34 = RamUsage::Initialize(v32, VirtualNumaNodeCount);
  if ( v34 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5B8,
      (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
      (const char *)(unsigned int)v34,
      OutputBufferLength);
  v35 = operator new(0x498u);
  v58[0] = (std::_Ref_count_base *)v35;
  memset_0(v35, 0, 0x498u);
  *v35 = &MemoryConfiguration::`vftable';
  v35[1] = 0;
  v35[2] = 0;
  v35[3] = 0;
  v35[4] = 0;
  Vml::VmSlimReaderWriterLock::VmSlimReaderWriterLock((Vml::VmSlimReaderWriterLock *)(v35 + 13), v36);
  v35[15] = 0;
  v35[16] = 0;
  v35[81] = 0;
  v35[146] = 0;
  qword_1403C0400 = (__int64)v35;
  v57 = qword_1403C05D8;
  v56 = (char *)(v22 << 8);
  v54 = (char *)((_QWORD)v13 << 8);
  (*(void (__fastcall **)(_QWORD *, struct IVirtualMachine *, __int64, __int64))*v35)(
    v35,
    v10,
    qword_1403C0378,
    (qword_1403C0458 + 24) & -(__int64)(qword_1403C0458 != 0));
  if ( qword_1403C03A0 == 3 )
  {
    if ( *(_DWORD *)(*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)qword_1403C0400 + 40LL))(
                      qword_1403C0400,
                      v61) )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x5CE,
        (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
        (const char *)0x32,
        (unsigned int)v11);
    v37 = 0x6DB6DB6DB6DB6DB7LL * ((__int64)(*((_QWORD *)v11 + 2) - *((_QWORD *)v11 + 1)) >> 3);
    v38 = (char *)xmmword_1403C03B0;
    v39 = qword_1403C03A8;
    v40 = ((__int64)xmmword_1403C03B0 - qword_1403C03A8) >> 2;
    if ( v37 >= v40 )
    {
      if ( v37 <= v40 )
        goto LABEL_67;
      if ( v37 > ((__int64)*(&xmmword_1403C03B0 + 1) - qword_1403C03A8) >> 2 )
      {
        std::vector<enum Schema::VirtualMachines::Resources::Compute::MemoryBackingType>::_Resize_reallocate<std::_Value_init_tag>(
          (const void **)&qword_1403C03A8,
          0x6DB6DB6DB6DB6DB7LL * ((__int64)(*((_QWORD *)v11 + 2) - *((_QWORD *)v11 + 1)) >> 3));
        v39 = qword_1403C03A8;
        goto LABEL_67;
      }
      v42 = 4 * (v37 - v40);
      memset_0(xmmword_1403C03B0, 0, v42);
      v41 = &v38[v42];
      v39 = qword_1403C03A8;
    }
    else
    {
      v41 = (char *)(qword_1403C03A8
                   - 0x4924924924924924LL * ((__int64)(*((_QWORD *)v11 + 2) - *((_QWORD *)v11 + 1)) >> 3));
    }
    xmmword_1403C03B0 = v41;
LABEL_67:
    v43 = (unsigned int *)*((_QWORD *)v11 + 2);
    v44 = (unsigned int *)*((_QWORD *)v11 + 1);
    if ( v44 != v43 )
    {
      while ( 1 )
      {
        *(_DWORD *)(v39 + 4LL * *v44) = v44[6];
        v44 += 14;
        if ( v44 == v43 )
          break;
        v39 = qword_1403C03A8;
      }
    }
  }
  if ( *((_BYTE *)v8 + 344) )
  {
    if ( (_DWORD)dword_1403C03E4 != 1 )
    {
      if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
        VmlDebugTrace(16416, L"Only generation 2 VMs support memory encryption");
      LODWORD(v54) = (_DWORD)dword_1403C03E4;
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0x608,
        (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
        (const char *)0x80048017LL,
        (int)"virtualSystemSubType = %u",
        v54,
        v56,
        v57);
    }
    LODWORD(v56) = (_DWORD)dword_1403C03E0;
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0x60F,
      (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
      (const char *)0x80048016LL,
      (unsigned int)dword_1403C03E0 < 0xA00,
      (bool)"VM version %x does not support memory encryption.",
      v56,
      v57);
    v65 = 0;
    if ( !(unsigned int)VidGetPartitionProperty(-1, 393216, &v65) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x61D,
        (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
        v46);
    if ( v65 != (struct IVirtualMachine *)1 )
      goto LABEL_88;
    v47 = (std::_Ref_count_base *)VidOpenStatisticsHandle(retaddr);
    v58[0] = v47;
    wil::details::in1diag3::Throw_GetLastErrorIfMsg(
      retaddr,
      (void *)0x624,
      (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
      (const char *)((((unsigned __int64)v47 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0),
      (bool)"Failed to open VID statistics handle",
      v55);
    LODWORD(v64) = 0;
    v66 = 0;
    LODWORD(phkResult) = 13;
    LODWORD(v55) = 8;
    if ( !(unsigned int)VidGetSystemInformation(v47, 10, &phkResult) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x632,
        (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
        v48);
    v49 = 0;
    if ( v66 )
    {
      v49 = 1;
      if ( (unsigned int)Vml::VmOsVersion::IsOsClientVersion() )
      {
        OutputBuffer[0] = 0;
        v50 = NtPowerInformation((POWER_INFORMATION_LEVEL)66, 0, 0, OutputBuffer, 1u);
        if ( v50 < 0 )
          wil::details::in1diag3::_Throw_NtStatus(
            retaddr,
            (void *)0x645,
            (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
            (const char *)(unsigned int)v50,
            OutputBufferLengtha);
        v49 = OutputBuffer[0] != 0;
      }
    }
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int VidCloseStatisticsHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int VidCloseStatisticsHandle(void *)>>(v58);
    if ( v49 )
    {
      byte_1403C06C8 = 1;
    }
    else
    {
LABEL_88:
      if ( *((_BYTE *)v8 + 344) == 2 )
      {
        VmEventWriteAndReport(
          &MSVML_WP_INIT_MEMORY_ENCRYPTION_NOT_SUPPORTED_ERROR,
          5u,
          v45,
          (const unsigned __int16 *)v46);
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          (void *)0x65C,
          (unsigned int)"onecore\\vm\\worker\\memory\\memorymanager.cpp",
          (const char *)0x80070032LL,
          (int)"Memory encryption not supported",
          v55);
      }
    }
  }
  BYTE6(qword_1403C05AC) = *((_BYTE *)v8 + 317);
}

```

## disassembly

```asm
0x140085f98  push    rbx
0x140085f9a  push    rsi
0x140085f9b  push    rdi
0x140085f9c  push    r12
0x140085f9e  push    r13
0x140085fa0  push    r14
0x140085fa2  push    r15
0x140085fa4  sub     rsp, 100h
0x140085fab  mov     rax, cs:__security_cookie
0x140085fb2  xor     rax, rsp
0x140085fb5  mov     [rsp+138h+var_48], rax
0x140085fbd  mov     rsi, r9
0x140085fc0  mov     rbx, r8
0x140085fc3  mov     r13, rdx
0x140085fc6  mov     [rsp+138h+var_60], rdx
0x140085fce  mov     [rsp+138h+var_D8], r9
0x140085fd3  mov     r15, [rsp+138h+arg_20]
0x140085fdb  mov     [rsp+138h+var_C8], r15
0x140085fe0  xor     edi, edi
0x140085fe2  lea     rcx, qword_1403C0370
0x140085fe9  call    ?Reset@?$VmReferencePtr@UIVirtualMachine@@VVmWeakReferenceTraits@Vml@@@Vml@@QEAAXPEAUIVirtualMachine@@@Z; Vml::VmReferencePtr<IVirtualMachine,Vml::VmWeakReferenceTraits>::Reset(IVirtualMachine *)
0x140085fee  mov     rdx, rbx
0x140085ff1  lea     rcx, qword_1403C0378
0x140085ff8  call    ?Reset@?$VmReferencePtr@VVndCompletionThread@@VVmUserReferenceTraits@Vml@@@Vml@@QEAAXPEAVVndCompletionThread@@@Z; Vml::VmReferencePtr<VndCompletionThread,Vml::VmUserReferenceTraits>::Reset(VndCompletionThread *)
0x140085ffd  mov     rcx, cs:qword_1403C0370
0x140086004  mov     rax, [rcx]
0x140086007  lea     rdx, [rsp+138h+var_58]
0x14008600f  mov     rax, [rax+38h]
0x140086013  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140086018  mov     rdx, rax
0x14008601b  lea     rcx, qword_1403C0380
0x140086022  call    ??4?$VmReferencePtr@VVmRepository@@VVmUserReferenceTraits@Vml@@@Vml@@QEAAAEBV01@$$QEAV01@@Z; Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>::operator=(Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits> &&)
0x140086027  lea     rcx, [rsp+138h+var_58]
0x14008602f  call    ??1?$VmReferencePtr@VVmRepository@@VVmUserReferenceTraits@Vml@@@Vml@@QEAA@XZ; Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>::~VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>(void)
0x140086034  mov     rcx, [rsp+138h+arg_30]
0x14008603c  cmp     dword ptr [rcx+44h], 3
0x140086040  setz    cs:byte_1403C05F8
0x140086047  mov     r12, [rsi+20h]
0x14008604b  mov     [rsp+138h+var_E8], r12
0x140086050  jnz     short loc_140086078
0x140086052  cmp     [rcx+18h], r12
0x140086056  jbe     short loc_140086078
0x140086058  mov     rcx, [rsp+138h]; this
0x140086060  mov     r9d, 80070057h; char *
0x140086066  lea     r8, aOnecoreVmWorke_9; "onecore\\vm\\worker\\memory\\memorymana"...
0x14008606d  mov     edx, 506h; void *
0x140086072  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140086078  lea     rcx, [rsp+138h+var_58]
0x140086080  call    ??$CreateComObject@VMemoryBalancerInterface@@$$V@Vml@@YA?AV?$VmComPtr@VMemoryBalancerInterface@@@0@XZ; Vml::CreateComObject<MemoryBalancerInterface,>(void)
0x140086085  mov     rdx, [rax]
0x140086088  mov     [rax], rdi
0x14008608b  lea     rcx, qword_1403C0458
0x140086092  call    ??$Attach@VMemoryBalancerInterface@@@?$VmComPtr@VMemoryBalancerInterface@@@Vml@@QEAAXPEAVMemoryBalancerInterface@@@Z; Vml::VmComPtr<MemoryBalancerInterface>::Attach<MemoryBalancerInterface>(MemoryBalancerInterface *)
0x140086097  lea     rcx, [rsp+138h+var_58]
0x14008609f  call    ??1?$VmComPtr@VTdxStateMigrationTransferObjectSourceImpl@TdxStateMigrationTransfer@@@Vml@@QEAA@XZ; Vml::VmComPtr<TdxStateMigrationTransfer::TdxStateMigrationTransferObjectSourceImpl>::~VmComPtr<TdxStateMigrationTransfer::TdxStateMigrationTransferObjectSourceImpl>(void)
0x1400860a4  mov     rcx, [rsp+138h]; this
0x1400860ac  mov     rbx, cs:qword_1403C0458
0x1400860b3  test    rbx, rbx
0x1400860b6  jnz     short loc_1400860CA
0x1400860b8  lea     r8, aOnecoreVmWorke_9; "onecore\\vm\\worker\\memory\\memorymana"...
0x1400860bf  mov     edx, 50Ah; void *
0x1400860c4  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1400860ca  lea     rcx, [rbx+20h]
0x1400860ce  mov     rdx, cs:qword_1403C0378
0x1400860d5  call    ?Reset@?$VmReferencePtr@VVndCompletionThread@@VVmUserReferenceTraits@Vml@@@Vml@@QEAAXPEAVVndCompletionThread@@@Z; Vml::VmReferencePtr<VndCompletionThread,Vml::VmUserReferenceTraits>::Reset(VndCompletionThread *)
0x1400860da  mov     [rbx+80h], rdi
0x1400860e1  lea     rdx, [rsi+30h]
0x1400860e5  lea     rcx, [rbx+58h]
0x1400860e9  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1400860ee  cmp     [rsp+138h+arg_38], dil
0x1400860f6  jz      short loc_14008615B
0x1400860f8  mov     rcx, cs:qword_1403C0370
0x1400860ff  mov     rax, [rcx]
0x140086102  lea     rdx, [rsp+138h+var_58]
0x14008610a  mov     rax, [rax+198h]
0x140086111  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140086116  mov     cs:word_1403C0428+1, 101h
0x14008611f  mov     rax, [rsp+138h+var_58]
0x140086127  mov     cs:qword_1403C0430, rax
0x14008612e  mov     cl, al
0x140086130  shr     cl, 3
0x140086133  and     cl, 1
0x140086136  mov     cs:byte_1403C0438, cl
0x14008613c  cmp     [rsp+138h+var_50], dil
0x140086144  jz      short loc_14008615B
0x140086146  mov     cl, al
0x140086148  and     cl, 60h
0x14008614b  cmp     cl, 20h ; ' '
0x14008614e  jnz     short loc_14008615B
0x140086150  and     rax, 0FFFFFFFFFFFFFFF7h
0x140086154  mov     cs:qword_1403C0430, rax
0x14008615b  mov     [rsp+138h+phkResult], rdi
0x140086163  mov     r9d, 20019h; unsigned int
0x140086169  lea     r8, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\Vi"...
0x140086170  mov     rdx, 0FFFFFFFF80000002h; hKey
0x140086177  lea     rcx, [rsp+138h+phkResult]; phkResult
0x14008617f  call    ?Open@VmRegistryKey@Vml@@QEAAHPEAUHKEY__@@PEBGK@Z; Vml::VmRegistryKey::Open(HKEY__ *,ushort const *,ulong)
0x140086184  test    eax, eax
0x140086186  jz      loc_14008621D
0x14008618c  mov     dword ptr [rsp+138h+var_68], edi
0x140086193  lea     r8, [rsp+138h+var_68]; unsigned int *
0x14008619b  lea     rdx, aAllowspillingf; "AllowSpillingForHvDeposits"
0x1400861a2  lea     rcx, [rsp+138h+phkResult]; this
0x1400861aa  call    ?QueryValue@VmRegistryKey@Vml@@QEBAHPEBGAEAK@Z; Vml::VmRegistryKey::QueryValue(ushort const *,ulong &)
0x1400861af  test    eax, eax
0x1400861b1  jz      short loc_1400861C1
0x1400861b3  cmp     dword ptr [rsp+138h+var_68], edi
0x1400861ba  setnz   byte ptr cs:dword_1403C0658+1
0x1400861c1  lea     r8, [rsp+138h+var_68]; unsigned int *
0x1400861c9  lea     rdx, aUsesystemparti; "UseSystemPartitionForHvDeposits"
0x1400861d0  lea     rcx, [rsp+138h+phkResult]; this
0x1400861d8  call    ?QueryValue@VmRegistryKey@Vml@@QEBAHPEBGAEAK@Z; Vml::VmRegistryKey::QueryValue(ushort const *,ulong &)
0x1400861dd  test    eax, eax
0x1400861df  jz      short loc_1400861EF
0x1400861e1  cmp     dword ptr [rsp+138h+var_68], edi
0x1400861e8  setnz   byte ptr cs:dword_1403C0658+2
0x1400861ef  lea     r8, [rsp+138h+var_68]; unsigned int *
0x1400861f7  lea     rdx, aUsesystemparti_0; "UseSystemPartitionForPhysicalBuffers"
0x1400861fe  lea     rcx, [rsp+138h+phkResult]; this
0x140086206  call    ?QueryValue@VmRegistryKey@Vml@@QEBAHPEBGAEAK@Z; Vml::VmRegistryKey::QueryValue(ushort const *,ulong &)
0x14008620b  test    eax, eax
0x14008620d  jz      short loc_14008621D
0x14008620f  cmp     dword ptr [rsp+138h+var_68], edi
0x140086216  setnz   byte ptr cs:dword_1403C0658+3
0x14008621d  lea     rcx, [rsp+138h+phkResult]; this
0x140086225  call    ?Close@VmRegistryKey@Vml@@QEAAXXZ; Vml::VmRegistryKey::Close(void)
0x14008622a  nop
0x14008622b  jmp     short loc_140086246
0x14008622d  xor     edi, edi
0x14008622f  mov     r13, [rsp+138h+var_60]
0x140086237  mov     rsi, [rsp+138h+var_D8]
0x14008623c  mov     r15, [rsp+138h+var_C8]
0x140086241  mov     r12, [rsp+138h+var_E8]
0x140086246  xorps   xmm0, xmm0
0x140086249  movups  xmmword ptr [rsp+138h+var_E8], xmm0
0x14008624e  xor     r8d, r8d
0x140086251  mov     rdx, cs:qword_1403C0380
0x140086258  lea     rcx, [rsp+138h+var_E8]
0x14008625d  call    ??0VmRepositoryAutoLock@@QEAA@PEAVVmRepository@@W4VmRepositoryLockFlags@@@Z; VmRepositoryAutoLock::VmRepositoryAutoLock(VmRepository *,VmRepositoryLockFlags)
0x140086262  nop
0x140086263  mov     r9d, dword ptr [rsp+138h+var_E8+8]; char *
0x140086268  mov     rcx, [rsp+138h]; this
0x140086270  test    r9d, r9d
0x140086273  jns     short loc_140086287
0x140086275  lea     r8, aOnecoreVmWorke_9; "onecore\\vm\\worker\\memory\\memorymana"...
0x14008627c  mov     edx, 54Dh; void *
0x140086281  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140086287  mov     rcx, cs:qword_1403C0380
0x14008628e  mov     rax, [rcx]
0x140086291  lea     rdx, dword_1403C03E0
0x140086298  mov     rax, [rax+120h]
0x14008629f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400862a4  mov     rcx, [rsp+138h]; this
0x1400862ac  test    eax, eax
0x1400862ae  jns     short loc_1400862C5
0x1400862b0  mov     r9d, eax; char *
0x1400862b3  lea     r8, aOnecoreVmWorke_9; "onecore\\vm\\worker\\memory\\memorymana"...
0x1400862ba  mov     edx, 552h; void *
0x1400862bf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400862c5  mov     rcx, cs:qword_1403C0380
0x1400862cc  mov     rax, [rcx]
0x1400862cf  lea     rdx, dword_1403C03E4
0x1400862d6  mov     rax, [rax+140h]
0x1400862dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400862e2  mov     rcx, [rsp+138h]; this
0x1400862ea  test    eax, eax
0x1400862ec  jns     short loc_140086303
0x1400862ee  mov     r9d, eax; char *
0x1400862f1  lea     r8, aOnecoreVmWorke_9; "onecore\\vm\\worker\\memory\\memorymana"...
0x1400862f8  mov     edx, 553h; void *
0x1400862fd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140086303  mov     r14, rdi
0x140086306  cmp     [rsi+100h], dil
0x14008630d  jz      short loc_14008631D
0x14008630f  mov     byte ptr cs:qword_1403C05AC+4, 1
0x140086316  mov     r14, [rsi+108h]
0x14008631d  cmp     [rsi+138h], dil
0x140086324  jz      short loc_14008632D
0x140086326  mov     byte ptr cs:qword_1403C05AC+5, 1
0x14008632d  mov     rax, [rsp+138h+arg_28]
0x140086335  mov     ecx, [rax]
0x140086337  shr     ecx, 7
0x14008633a  and     cl, 1
0x14008633d  mov     byte ptr cs:qword_1403C05AC+7, cl
0x140086343  mov     rax, [rsi+28h]
0x140086347  mov     cs:qword_1403C03A0, rax
0x14008634e  mov     eax, 40000h
0x140086353  cmp     [rsi+0B8h], rax
0x14008635a  jnz     short loc_1400863BC
0x14008635c  cmp     cs:dword_1403C03E0, 803h
0x140086366  jnb     short loc_1400863C1
0x140086368  mov     ebx, 4020h
0x14008636d  mov     ecx, ebx
0x14008636f  call    VmlIsDebugTraceEnabled
0x140086374  test    eax, eax
0x140086376  jz      short loc_140086386
0x140086378  lea     rdx, aOnlyRs4OrAbove; "Only RS4 or above VMs support huge page"...
0x14008637f  mov     ecx, ebx
0x140086381  call    VmlDebugTrace
0x140086386  mov     rcx, [rsp+138h]; this
0x14008638e  mov     eax, cs:dword_1403C03E0
0x140086394  mov     dword ptr [rsp+138h+var_110], eax; char *
0x140086398  lea     rax, aVmVersionXDoes_1; "VM version %x does not support huge pag"...
0x14008639f  mov     qword ptr [rsp+138h+OutputBufferLength], rax; int
0x1400863a4  mov     r9d, 80048016h; char *
0x1400863aa  lea     r8, aOnecoreVmWorke_9; "onecore\\vm\\worker\\memory\\memorymana"...
0x1400863b1  mov     edx, 574h; void *
0x1400863b6  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x1400863bc  mov     eax, 200h
0x1400863c1  mov     cs:qword_1403C05D8, rax
0x1400863c8  mov     eax, cs:dword_1403C03E4
0x1400863ce  cmp     eax, 8
0x1400863d1  jz      short loc_1400863DC
0x1400863d3  cmp     eax, 1
0x1400863d6  jnz     loc_140086503
0x1400863dc  mov     [rsp+138h+phkResult], rdi
0x1400863e4  mov     rcx, cs:qword_1403C0380
0x1400863eb  mov     rax, [rcx]
0x1400863ee  lea     r8, [rsp+138h+phkResult]
0x1400863f6  lea     rdx, ?VIRTUAL_MACHINE_TOPOLOGY_DIRECT_FILE_MAPPING_XPATH@@3QBGB; "/configuration/settings/topology/direct"...
0x1400863fd  mov     rax, [rax+78h]
0x140086401  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140086406  test    eax, eax
0x140086408  js      short loc_14008645D
0x14008640a  mov     rax, [rsp+138h+phkResult]
0x140086412  test    al, 1
0x140086414  jz      short loc_140086447
0x140086416  mov     rcx, [rsp+138h]; this
0x14008641e  mov     [rsp+138h+var_110], rax; char *
0x140086423  lea     rax, aDirectfilemapp; "directFileMappingMb = %I64u"
0x14008642a  mov     qword ptr [rsp+138h+OutputBufferLength], rax; int
0x14008642f  mov     r9d, 80070057h; char *
0x140086435  lea     r8, aOnecoreVmWorke_9; "onecore\\vm\\worker\\memory\\memorymana"...
0x14008643c  mov     edx, 58Ah; void *
0x140086441  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x140086447  mov     ebx, 10000h
0x14008644c  cmp     rax, rbx
0x14008644f  cmova   rax, rbx
0x140086453  mov     [rsp+138h+phkResult], rax
0x14008645b  jmp     short loc_140086462
0x14008645d  mov     ebx, 10000h
0x140086462  mov     [rsp+138h+var_68], rdi
0x14008646a  mov     rcx, cs:qword_1403C0380
0x140086471  mov     rax, [rcx]
0x140086474  lea     r8, [rsp+138h+var_68]
0x14008647c  lea     rdx, ?VIRTUAL_MACHINE_TOPOLOGY_SHARED_MEMORY_XPATH@@3QBGB; "/configuration/settings/topology/shared"...
0x140086483  mov     rax, [rax+78h]
0x140086487  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008648c  mov     rdx, [rsp+138h+var_68]
0x140086494  test    eax, eax
0x140086496  js      short loc_1400864D5
0x140086498  test    dl, 1
0x14008649b  jz      short loc_1400864CE
0x14008649d  mov     rcx, [rsp+138h]; this
0x1400864a5  mov     [rsp+138h+var_110], rdx; char *
0x1400864aa  lea     rax, aSharedmemorymb; "sharedMemoryMb = %I64u"
0x1400864b1  mov     qword ptr [rsp+138h+OutputBufferLength], rax; int
0x1400864b6  mov     r9d, 80070057h; char *
0x1400864bc  lea     r8, aOnecoreVmWorke_9; "onecore\\vm\\worker\\memory\\memorymana"...
0x1400864c3  mov     edx, 59Ch; void *
0x1400864c8  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x1400864ce  cmp     rdx, rbx
0x1400864d1  cmova   rdx, rbx
0x1400864d5  mov     rax, [rsp+138h+phkResult]
0x1400864dd  shl     rax, 8
0x1400864e1  mov     cs:qword_1403C04D8, rax
0x1400864e8  shl     rdx, 8
0x1400864ec  mov     cs:qword_1403C04E0, rdx
0x1400864f3  add     rax, rdx
0x1400864f6  mov     cs:qword_1403C04E8, rax
0x1400864fd  mov     eax, cs:dword_1403C03E4
0x140086503  cmp     cs:dword_1403C03E0, 701h
0x14008650d  jb      short loc_14008651B
0x14008650f  cmp     eax, 1
0x140086512  jnz     short loc_14008651B
0x140086514  mov     cs:byte_1403C05A8, dil
0x14008651b  lea     rcx, [rsp+138h+var_E8]; this
0x140086520  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x140086525  lea     rcx, [rsp+138h+var_E8]
0x14008652a  call    ??$make_unique@VGpaSpaceBestFitAllocator@@AEB_K$0A@@std@@YA?AV?$unique_ptr@VGpaSpaceBestFitAllocator@@U?$default_delete@VGpaSpaceBestFitAllocator@@@std@@@0@AEB_K@Z; std::make_unique<GpaSpaceBestFitAllocator,unsigned __int64 const &,0>(unsigned __int64 const &)
0x14008652f  mov     rcx, [rax]
0x140086532  mov     [rax], rdi
0x140086535  mov     rdx, cs:qword_1403C0518
0x14008653c  mov     cs:qword_1403C0518, rcx
0x140086543  test    rdx, rdx
0x140086546  jz      short loc_14008654D
0x140086548  call    ??R?$default_delete@VGpaSpaceBestFitAllocator@@@std@@QEBAXPEAVGpaSpaceBestFitAllocator@@@Z; std::default_delete<GpaSpaceBestFitAllocator>::operator()(GpaSpaceBestFitAllocator *)
0x14008654d  lea     rcx, [rsp+138h+var_E8]
0x140086552  call    ??1?$unique_ptr@VGpaSpaceBestFitAllocator@@U?$default_delete@VGpaSpaceBestFitAllocator@@@std@@@std@@QEAA@XZ; std::unique_ptr<GpaSpaceBestFitAllocator>::~unique_ptr<GpaSpaceBestFitAllocator>(void)
0x140086557  mov     ecx, 48h ; 'H'; Size
0x14008655c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140086561  mov     [rsp+138h+var_E8], rax
0x140086566  xorps   xmm0, xmm0
0x140086569  movups  xmmword ptr [rax], xmm0
0x14008656c  mov     dword ptr [rax+8], 1
0x140086573  mov     dword ptr [rax+0Ch], 1
0x14008657a  lea     rcx, ??_7?$_Ref_count_obj2@VRamUsage@@@std@@6B@; const std::_Ref_count_obj2<RamUsage>::`vftable'
0x140086581  mov     [rax], rcx
0x140086584  lea     rcx, [rax+10h]
0x140086588  mov     [rcx+8], rdi
  ... truncated ...
```
