# Container::Manager::Core::Details::ContainerObject::Initialize(Container::Manager::Core::Details::ContainerConfiguration,wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>,utl::optional<Container::Manager::Core::Details::DebugConfigurationHandle>,utl::shared_ptr<Container::Manager::Core::Details::ComputeReaper> const &,utl::shared_ptr<Container::Manager::Core::Details::PolicyManager> const &,utl::shared_ptr<Container::Manager::Hns::NetworkManager> const &,utl::shared_ptr<Container::Manager::Core::Details::PdcClient> const &,utl::shared_ptr<Container::Manager::Core::Details::HeartbeatMonitor> const &,utl::shared_ptr<Container::Manager::Core::Details::HostIdleMonitor> const &,utl::shared_ptr<Container::Manager::Core::Details::MemoryManager> const &,utl::shared_ptr<Container::Manager::Core::Details::ResourceBroker> const &,utl::shared_ptr<Container::Manager::Core::Details::SystemConfigurationManager> const &,utl::shared_ptr<Container::Manager::Core::Details::ConfigurationBuilder> const &,utl::shared_ptr<Container::Manager::Core::Details::LogManager> const &,Container::Manager::Core::Details::ServicingOrchestrator &,Container::Manager::Core::Details::ContainerOrchestrator *)

- ea: `0x1800a0644`
- end: `0x1800a24b5`
- name: `?Initialize@ContainerObject@Details@Core@Manager@Container@@QEAAJUContainerConfiguration@2345@V?$unique_ptr@VResourceHandle@Core@Manager@Container@@U?$default_delete@VResourceHandle@Core@Manager@Container@@@wistd@@@wistd@@1V?$optional@VDebugConfigurationHandle@Details@Core@Manager@Container@@@utl@@AEBV?$shared_ptr@VComputeReaper@Details@Core@Manager@Container@@@utl@@AEBV?$shared_ptr@VPolicyManager@Details@Core@Manager@Container@@@utl@@AEBV?$shared_ptr@VNetworkManager@Hns@Manager@Container@@@utl@@AEBV?$shared_ptr@VPdcClient@Details@Core@Manager@Container@@@utl@@AEBV?$shared_ptr@VHeartbeatMonitor@Details@Core@Manager@Container@@@utl@@AEBV?$shared_ptr@VHostIdleMonitor@Details@Core@Manager@Container@@@utl@@AEBV?$shared_ptr@VMemoryManager@Details@Core@Manager@Container@@@utl@@AEBV?$shared_ptr@VResourceBroker@Details@Core@Manager@Container@@@utl@@AEBV?$shared_ptr@VSystemConfigurationManager@Details@Core@Manager@Container@@@utl@@AEBV?$shared_ptr@VConfigurationBuilder@Details@Core@Manager@Container@@@utl@@AEBV?$shared_ptr@VLogManager@Details@Core@Manager@Container@@@utl@@AEAVServicingOrchestrator@2345@PEAVContainerOrchestrator@2345@@Z`
- size: `7793`
- prototype: `__int64 __usercall@<rax>(PVOID pv@<rcx>, Container::Manager::Core::Details::ContainerConfiguration *this@<rdx>, Container::Manager::Core::Details::DebugConfigurationHandle *, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `49`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180078c0c`

## callees

- `0x180004bd0`
- `0x180004bf4`
- `0x180004fc4`
- `0x1800067f0`
- `0x1800068c0`
- `0x180008328`
- `0x180008c98`
- `0x18000da68`
- `0x18000da88`
- `0x18000dad8`
- `0x180016658`
- `0x1800239cc`
- `0x180023b68`
- `0x180023bec`
- `0x1800262e4`
- `0x1800393cc`
- `0x18003eb28`
- `0x1800471dc`
- `0x18004a088`
- `0x18004e750`
- `0x18004f184`
- `0x18004f1bc`
- `0x18004f25c`
- `0x18004feb4`
- `0x1800585d0`
- `0x18005a340`
- `0x180066670`
- `0x180066b40`
- `0x180066dc8`
- `0x180071c6c`
- `0x180076788`
- `0x180076918`
- `0x180076cc0`
- `0x1800783c8`
- `0x180078434`
- `0x1800787e0`
- `0x18007886c`
- `0x18007acc0`
- `0x18009798c`
- `0x180098ef8`
- `0x18009aabc`
- `0x18009ab08`
- `0x1800a0510`
- `0x1800a0644`
- `0x1800b7b58`
- `0x1800bc0c0`
- `0x1800f3888`
- `0x18011e8f0`
- `0x18012309c`

## import_xrefs

- `ntdll!RtlInitializeBitMapEx` at `0x1800a1866`
- `ntdll!RtlInitializeBitMapEx` at `0x1800a1866`
- `ntdll!RtlSetBitEx` at `0x1800a1886`
- `ntdll!RtlSetBitEx` at `0x1800a1886`
- `ntdll!RtlClearAllBitsEx` at `0x1800a1875`
- `ntdll!RtlClearAllBitsEx` at `0x1800a1875`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800a0b7b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800a0b7b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800a0c08`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800a0c31`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800a0c5b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800a0c08`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800a0c31`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800a0c5b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a0cf8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a0d07`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a0d16`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a0e27`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a0e36`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a0e45`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a0fef`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a0ffe`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a100d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a10f7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a1106`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a1115`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a131c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a132b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a133a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a1489`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a1498`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a14a7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a192b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a1940`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a1955`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a1a42`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a1a51`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a1a60`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a1b8d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a1b9c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a1bab`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a1c6b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a1c7a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a1d64`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a0cf8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a0d07`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a0d16`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a0e27`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a0e36`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a0e45`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a0fef`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a0ffe`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a100d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a10f7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a1106`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a1115`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a131c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a132b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a133a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a1489`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a1498`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a14a7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a192b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a1940`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a1955`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a1a42`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a1a51`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a1a60`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a1b8d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a1b9c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a1bab`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a1c6b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a1c7a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a1d64`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800a0bb3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800a0bb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0ba1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0ba1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a0bc1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a0bc1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a097e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a09dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a09fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a0a60`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a0a7e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a0a9c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a0d4c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a0d6a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a0d88`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a0e7b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a0e99`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a0eb7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1043`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1061`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1083`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a114b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1169`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1187`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1be2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1c00`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1c1e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1cae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1ccc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1cea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1d98`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1db6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1dd4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1ed0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1eee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1f0c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a2008`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a2026`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a2044`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a097e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a09dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a09fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a0a60`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a0a7e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a0a9c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a0d4c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a0d6a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a0d88`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a0e7b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a0e99`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a0eb7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1043`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1061`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1083`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a114b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1169`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1187`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1be2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1c00`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1c1e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1cae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1ccc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1cea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1d98`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1db6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1dd4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1ed0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1eee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a1f0c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a2008`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a2026`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a2044`
- `UMPDC!SleepstudyHelperDestroyBlocker` at `0x1800a0cd7`
- `UMPDC!SleepstudyHelperDestroyBlocker` at `0x1800a0cd7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Container::Manager::Core::Details::ContainerObject::Initialize(
        PVOID pv,
        Container::Manager::Core::Details::ContainerConfiguration *this,
        Container::Manager::Core::ResourceHandle **a3,
        Container::Manager::Core::ResourceHandle **a4,
        Container::Manager::Core::Details::DebugConfigurationHandle *a5,
        __int64 a6,
        __int64 a7,
        __int64 *a8,
        __int64 *a9,
        _QWORD *a10,
        __int64 *a11,
        _QWORD *a12,
        _QWORD *a13,
        __int64 a14,
        __int64 *a15,
        __int64 a16,
        __int64 a17,
        __int64 a18)
{
  _QWORD *v22; // rax
  int v23; // eax
  unsigned int v24; // esi
  Container::Manager::Core::ResourceHandle *v25; // rdi
  Container::Manager::Core::ResourceHandle *v26; // rdi
  Container::Manager::Core::Details::ComputeSystemReaperContext *v28; // r13
  int v29; // eax
  Container::Manager::Core::Details::ContainerConfiguration *v30; // rcx
  _QWORD *v31; // rax
  void *v32; // rsi
  int v33; // eax
  Container::Manager::Core::Details::ContainerConfiguration *v34; // rcx
  Container::Manager::Core::ResourceHandle *v35; // rdi
  Container::Manager::Core::ResourceHandle *v36; // rdi
  int v37; // eax
  unsigned int v38; // r8d
  const char *v39; // r9
  int v40; // eax
  unsigned int v41; // r8d
  const char *v42; // r9
  unsigned int v43; // r8d
  const char *v44; // r9
  int v45; // eax
  unsigned int v46; // r8d
  const char *v47; // r9
  unsigned int v48; // r8d
  const char *v49; // r9
  unsigned int v50; // r8d
  const char *v51; // r9
  unsigned int v52; // ebx
  struct _TP_TIMER *v53; // rcx
  const char *v54; // r9
  PTP_TIMER v55; // rax
  DWORD LastError; // ebx
  struct _TP_WORK *ThreadpoolTimer; // rbx
  const char *v58; // r9
  struct _TP_TIMER *v59; // rdi
  const char *v60; // r9
  struct _TP_TIMER *v61; // rsi
  const char *v62; // r9
  int v63; // eax
  void *v64; // rax
  unsigned int v65; // r8d
  const char *v66; // r9
  unsigned int v67; // r8d
  const char *v68; // r9
  unsigned int v69; // r8d
  const char *v70; // r9
  __int64 v71; // rax
  unsigned int v72; // r8d
  const char *v73; // r9
  unsigned int v74; // r8d
  const char *v75; // r9
  unsigned int v76; // r8d
  const char *v77; // r9
  Container::Manager::Core::ResourceHandle *v78; // rdi
  Container::Manager::Core::ResourceHandle *v79; // rdi
  int v80; // eax
  unsigned int v81; // r8d
  const char *v82; // r9
  unsigned int v83; // r8d
  const char *v84; // r9
  unsigned int v85; // r8d
  const char *v86; // r9
  unsigned int v87; // r8d
  const char *v88; // r9
  unsigned int v89; // r8d
  const char *v90; // r9
  unsigned int v91; // r8d
  const char *v92; // r9
  Container::Manager::Core::ResourceHandle *v93; // rdi
  Container::Manager::Core::ResourceHandle *v94; // rdi
  __int64 v95; // r15
  void *v96; // r14
  int v97; // eax
  unsigned int v98; // r14d
  char *v99; // r13
  int v100; // eax
  Container::Manager::Core::Details::ContainerConfiguration *v101; // rbx
  void *v102; // rcx
  __int64 v103; // r14
  __int64 v104; // rcx
  __int64 v105; // rdx
  utl::_RefCountBase *v106; // rcx
  Container::Manager::Core::ResourceHandle **v107; // rdi
  __int64 v108; // rcx
  __int64 v109; // rdx
  utl::_RefCountBase *v110; // rcx
  __int64 v111; // rcx
  __int64 v112; // rax
  utl::_RefCountBase *v113; // rcx
  __int64 v114; // rcx
  __int64 v115; // rdx
  utl::_RefCountBase *v116; // rcx
  __int64 v117; // rcx
  __int64 v118; // rax
  utl::_RefCountBase *v119; // rcx
  Container::Manager::Core::ResourceHandle **v120; // rsi
  __int64 v121; // rcx
  __int64 v122; // r8
  utl::_RefCountBase *v123; // rcx
  Container::Manager::Core::ResourceHandle *v124; // rdi
  Container::Manager::Core::ResourceHandle *v125; // rdi
  bool v126; // zf
  unsigned int v127; // r8d
  const char *v128; // r9
  unsigned int v129; // r8d
  const char *v130; // r9
  unsigned int v131; // r8d
  const char *v132; // r9
  unsigned int v133; // r8d
  const char *v134; // r9
  unsigned int v135; // r8d
  const char *v136; // r9
  unsigned int v137; // r8d
  const char *v138; // r9
  unsigned int v139; // r8d
  const char *v140; // r9
  unsigned int v141; // r8d
  const char *v142; // r9
  unsigned int v143; // r8d
  const char *v144; // r9
  Container::Manager::Core::ResourceHandle *v145; // rdi
  Container::Manager::Core::ResourceHandle *v146; // rdi
  unsigned int v147; // r8d
  const char *v148; // r9
  unsigned int v149; // r8d
  const char *v150; // r9
  unsigned int v151; // r8d
  const char *v152; // r9
  Container::Manager::Core::ResourceHandle *v153; // rdi
  Container::Manager::Core::ResourceHandle *v154; // rdi
  unsigned int v155; // r8d
  const char *v156; // r9
  unsigned int v157; // r8d
  const char *v158; // r9
  unsigned int v159; // r8d
  const char *v160; // r9
  Container::Manager::Core::ResourceHandle *v161; // rdi
  Container::Manager::Core::ResourceHandle *v162; // rdi
  Container::Manager::Core::ResourceHandle *v163; // rdi
  Container::Manager::Core::ResourceHandle *v164; // rdi
  Container::Manager::Core::ResourceHandle *v165; // rdi
  Container::Manager::Core::ResourceHandle *v166; // rdi
  int v167; // [rsp+20h] [rbp-E0h]
  unsigned int v168; // [rsp+20h] [rbp-E0h]
  unsigned int v169; // [rsp+20h] [rbp-E0h]
  __int64 v170; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD *v171; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE hObject; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE v173; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE v174; // [rsp+50h] [rbp-B0h] BYREF
  Container::Manager::Core::Details::ContainerConfiguration *v175; // [rsp+58h] [rbp-A8h]
  void *v176; // [rsp+60h] [rbp-A0h] BYREF
  void *v177; // [rsp+68h] [rbp-98h]
  __int64 v178; // [rsp+70h] [rbp-90h] BYREF
  __int64 v179; // [rsp+78h] [rbp-88h] BYREF
  Container::Manager::Core::ResourceHandle **v180; // [rsp+80h] [rbp-80h]
  void *v181[2]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v182; // [rsp+98h] [rbp-68h]
  void *v183; // [rsp+A0h] [rbp-60h] BYREF
  PVOID pva; // [rsp+A8h] [rbp-58h]
  Container::Manager::Core::Details::ComputeSystemReaperContext *v185; // [rsp+B0h] [rbp-50h] BYREF
  PTP_TIMER pti; // [rsp+B8h] [rbp-48h] BYREF
  PTP_TIMER v187; // [rsp+C0h] [rbp-40h] BYREF
  PTP_WORK pwk; // [rsp+C8h] [rbp-38h] BYREF
  Container::Manager::Core::ResourceHandle **v189; // [rsp+D0h] [rbp-30h]
  _QWORD *v190; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD *v191; // [rsp+E0h] [rbp-20h]
  _QWORD *v192; // [rsp+E8h] [rbp-18h]
  _QWORD *v193; // [rsp+F0h] [rbp-10h]
  __int64 v194; // [rsp+F8h] [rbp-8h]
  __int128 v195; // [rsp+100h] [rbp+0h] BYREF
  _QWORD *v196; // [rsp+110h] [rbp+10h]
  __int64 v197; // [rsp+118h] [rbp+18h]
  __int64 v198; // [rsp+120h] [rbp+20h]
  __int64 v199; // [rsp+128h] [rbp+28h]
  _TP_CALLBACK_ENVIRON_V3 pcbe; // [rsp+130h] [rbp+30h] BYREF
  _QWORD v201[3]; // [rsp+180h] [rbp+80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+E8h]

  v189 = a4;
  v180 = a3;
  v175 = this;
  pva = pv;
  v197 = a6;
  v194 = a7;
  v191 = a10;
  v192 = a12;
  v193 = a13;
  v199 = a14;
  *(_QWORD *)&v195 = a16;
  v22 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v196 = v22;
  if ( !v22 )
  {
    v171 = 0;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x224,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
      (const char *)0x8007000ELL,
      v167);
    wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(&v171, 0);
    Container::Manager::Core::Details::ContainerConfiguration::~ContainerConfiguration(this);
    v165 = *a3;
    *a3 = 0;
    if ( v165 )
    {
      Container::Manager::Core::ResourceHandle::~ResourceHandle(v165);
      operator delete(v165, (const struct std::nothrow_t *)0x58);
    }
    v166 = *a4;
    *a4 = 0;
    if ( v166 )
    {
      Container::Manager::Core::ResourceHandle::~ResourceHandle(v166);
      operator delete(v166, (const struct std::nothrow_t *)0x58);
    }
    v126 = *((_BYTE *)a5 + 24) == 0;
    goto LABEL_270;
  }
  *v22 = 0;
  v22[1] = 0;
  v22[2] = 0;
  v171 = v22;
  if ( *((_DWORD *)this + 18) != 8 )
  {
    v23 = Container::Manager::Core::Details::ServicingOrchestrator::WatchForUpdatesToComplete(a17, v22);
    v24 = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x22B,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
        (const char *)(unsigned int)v23,
        v167);
      wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(&v171, 0);
      Container::Manager::Core::Details::ContainerConfiguration::~ContainerConfiguration(this);
LABEL_5:
      v25 = *a3;
      *a3 = 0;
      if ( v25 )
      {
        Container::Manager::Core::ResourceHandle::~ResourceHandle(v25);
        operator delete(v25, (const struct std::nothrow_t *)0x58);
      }
      v26 = *a4;
      v126 = *a4 == 0;
      *a4 = 0;
      if ( !v126 )
      {
        Container::Manager::Core::ResourceHandle::~ResourceHandle(v26);
        operator delete(v26, (const struct std::nothrow_t *)0x58);
      }
      if ( *((_BYTE *)a5 + 24) )
        Container::Manager::Core::Details::DebugConfigurationHandle::~DebugConfigurationHandle(a5);
      return v24;
    }
  }
  wil::make_unique_nothrow<Container::Manager::Core::Details::ComputeSystemReaperContext,>(&v185);
  v28 = v185;
  if ( !v185 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x232,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
      (const char *)0x8007000ELL,
      v167);
LABEL_259:
    wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(&v171, 0);
    Container::Manager::Core::Details::ContainerConfiguration::~ContainerConfiguration(this);
    v163 = *a3;
    v126 = *a3 == 0;
    *a3 = 0;
    if ( !v126 )
    {
      Container::Manager::Core::ResourceHandle::~ResourceHandle(v163);
      operator delete(v163, (const struct std::nothrow_t *)0x58);
    }
    v164 = *a4;
    *a4 = 0;
    if ( v164 )
    {
      Container::Manager::Core::ResourceHandle::~ResourceHandle(v164);
      operator delete(v164, (const struct std::nothrow_t *)0x58);
    }
    v126 = *((_BYTE *)a5 + 24) == 0;
LABEL_270:
    if ( !v126 )
      Container::Manager::Core::Details::DebugConfigurationHandle::~DebugConfigurationHandle(a5);
    return 2147942414LL;
  }
  v29 = Container::Manager::Core::Details::ComputeSystemReaperContext::Initialize(v185);
  v24 = v29;
  if ( v29 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x234,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
      (const char *)(unsigned int)v29,
      v167);
    if ( v28 )
    {
      Container::Manager::Core::Details::ComputeSystemReaperContext::~ComputeSystemReaperContext(v28);
      operator delete(v28, (const struct std::nothrow_t *)0x108);
    }
    wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(&v171, 0);
    v30 = this;
LABEL_17:
    Container::Manager::Core::Details::ContainerConfiguration::~ContainerConfiguration(v30);
    goto LABEL_5;
  }
  *((_BYTE *)v28 + 65) = 1;
  v31 = operator new(8u, (const struct std::nothrow_t *)&std::nothrow);
  v32 = v31;
  v177 = v31;
  if ( !v31 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x23C,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
      (const char *)0x8007000ELL,
      v167);
    if ( v28 )
    {
      Container::Manager::Core::Details::ComputeSystemReaperContext::~ComputeSystemReaperContext(v28);
      operator delete(v28, (const struct std::nothrow_t *)0x108);
    }
    goto LABEL_259;
  }
  *v31 = 0;
  v190 = v31;
  v33 = Container::Manager::Hcs::ComputeSystem::Initialize((Container::Manager::Hcs::ComputeSystem *)v31);
  LODWORD(v170) = v33;
  if ( v33 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x23D,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
      (const char *)(unsigned int)v33,
      v167);
    goto LABEL_21;
  }
  hObject = 0;
  v37 = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
          &hObject,
          1);
  LODWORD(v170) = v37;
  if ( v37 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x242,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
      (const char *)(unsigned int)v37,
      v167);
    if ( hObject && !CloseHandle(hObject) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v38, v39);
    goto LABEL_21;
  }
  v173 = 0;
  v40 = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
          &v173,
          0);
  LODWORD(v170) = v40;
  if ( v40 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x247,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
      (const char *)(unsigned int)v40,
      v167);
    if ( v173 && !CloseHandle(v173) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v41, v42);
    if ( hObject && !CloseHandle(hObject) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v43, v44);
LABEL_21:
    wistd::unique_ptr<Container::Manager::Hcs::Details::ComputeSystemImpl,wistd::default_delete<Container::Manager::Hcs::Details::ComputeSystemImpl>>::~unique_ptr<Container::Manager::Hcs::Details::ComputeSystemImpl,wistd::default_delete<Container::Manager::Hcs::Details::ComputeSystemImpl>>(v32);
    operator delete(v32, (const struct std::nothrow_t *)8);
    if ( v28 )
    {
      Container::Manager::Core::Details::ComputeSystemReaperContext::~ComputeSystemReaperContext(v28);
      operator delete(v28, (const struct std::nothrow_t *)0x108);
    }
    wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(&v171, 0);
    v34 = this;
LABEL_24:
    Container::Manager::Core::Details::ContainerConfiguration::~ContainerConfiguration(v34);
    goto LABEL_25;
  }
  v174 = 0;
  v45 = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
          &v174,
          0);
  LODWORD(v170) = v45;
  if ( v45 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x24C,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
      (const char *)(unsigned int)v45,
      v167);
    if ( v174 && !CloseHandle(v174) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v46, v47);
    if ( v173 && !CloseHandle(v173) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v48, v49);
    if ( hObject && !CloseHandle(hObject) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v50, v51);
    wistd::unique_ptr<Container::Manager::Hcs::Details::ComputeSystemImpl,wistd::default_delete<Container::Manager::Hcs::Details::ComputeSystemImpl>>::~unique_ptr<Container::Manager::Hcs::Details::ComputeSystemImpl,wistd::default_delete<Container::Manager::Hcs::Details::ComputeSystemImpl>>(v32);
    operator delete(v32, (const struct std::nothrow_t *)8);
    if ( v28 )
    {
      Container::Manager::Core::Details::ComputeSystemReaperContext::~ComputeSystemReaperContext(v28);
      operator delete(v28, (const struct std::nothrow_t *)0x108);
    }
    wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(&v171, 0);
    Container::Manager::Core::Details::ContainerConfiguration::~ContainerConfiguration(this);
LABEL_25:
    v35 = *a3;
    *a3 = 0;
    if ( v35 )
    {
      Container::Manager::Core::ResourceHandle::~ResourceHandle(v35);
      operator delete(v35, (const struct std::nothrow_t *)0x58);
    }
    v36 = *a4;
    v126 = *a4 == 0;
    *a4 = 0;
    if ( !v126 )
    {
      Container::Manager::Core::ResourceHandle::~ResourceHandle(v36);
      operator delete(v36, (const struct std::nothrow_t *)0x58);
    }
    if ( *((_BYTE *)a5 + 24) )
      Container::Manager::Core::Details::DebugConfigurationHandle::~DebugConfigurationHandle(a5);
    return (unsigned int)v170;
  }
  `eh vector constructor iterator'(
    v201,
    8u,
    3u,
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>,
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>);
  v52 = 0;
  LODWORD(v170) = 0;
  do
  {
    *(_QWORD *)&pcbe.Version = 3;
    *(_QWORD *)&pcbe.Size = 72;
    memset(&pcbe.CleanupGroup, 0, 44);
    pcbe.CallbackPriority = TP_CALLBACK_PRIORITY_NORMAL;
    v187 = (PTP_TIMER)v52;
    pcbe.Pool = (PTP_POOL)Container::Manager::Core::Details::ContainerObject::s_workQueueThreadpools[v52];
    v53 = CreateThreadpoolWork(Container::Manager::Core::Details::ContainerObject::WorkQueueThread, pv, &pcbe);
    pti = v53;
    v55 = (PTP_TIMER)v52;
    pwk = (PTP_WORK)v201[v52];
    if ( pwk )
    {
      LastError = GetLastError();
      CloseThreadpoolWork(pwk);
      SetLastError(LastError);
      v52 = v170;
      v55 = v187;
      v53 = pti;
    }
    v201[(_QWORD)v55] = v53;
    if ( !v53 )
    {
      LODWORD(v170) = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x264,
                        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
                        v54);
      `eh vector destructor iterator'(
        v201,
        8u,
        3u,
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>);
      if ( v174 && !CloseHandle(v174) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v155, v156);
      if ( v173 && !CloseHandle(v173) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v157, v158);
      if ( hObject && !CloseHandle(hObject) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v159, v160);
      wistd::unique_ptr<Container::Manager::Hcs::Details::ComputeSystemImpl,wistd::default_delete<Container::Manager::Hcs::Details::ComputeSystemImpl>>::~unique_ptr<Container::Manager::Hcs::Details::ComputeSystemImpl,wistd::default_delete<Container::Manager::Hcs::Details::ComputeSystemImpl>>(v32);
      operator delete(v32, (const struct std::nothrow_t *)8);
      if ( v28 )
      {
        Container::Manager::Core::Details::ComputeSystemReaperContext::~ComputeSystemReaperContext(v28);
        operator delete(v28, (const struct std::nothrow_t *)0x108);
      }
      wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(&v171, 0);
      Container::Manager::Core::Details::ContainerConfiguration::~ContainerConfiguration(v175);
      v161 = *a3;
      *a3 = 0;
      if ( v161 )
      {
        Container::Manager::Core::ResourceHandle::~ResourceHandle(v161);
        operator delete(v161, (const struct std::nothrow_t *)0x58);
      }
      v162 = *a4;
      *a4 = 0;
      if ( v162 )
      {
        Container::Manager::Core::ResourceHandle::~ResourceHandle(v162);
        operator delete(v162, (const struct std::nothrow_t *)0x58);
      }
      if ( *((_BYTE *)a5 + 24) )
        Container::Manager::Core::Details::DebugConfigurationHandle::~DebugConfigurationHandle(a5);
      return (unsigned int)v170;
    }
    LODWORD(v170) = ++v52;
  }
  while ( v52 < 3 );
  ThreadpoolTimer = CreateThreadpoolTimer(
                      Container::Manager::Core::Details::ContainerObject::RetryFailedStateTransitionTimerCallback,
                      pv,
                      0);
  pwk = ThreadpoolTimer;
  if ( !ThreadpoolTimer )
  {
    LODWORD(v170) = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x26D,
                      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
                      v58);
    `eh vector destructor iterator'(
      v201,
      8u,
      3u,
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>);
    if ( v174 && !CloseHandle(v174) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v147, v148);
    if ( v173 && !CloseHandle(v173) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v149, v150);
    if ( hObject && !CloseHandle(hObject) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v151, v152);
    wistd::unique_ptr<Container::Manager::Hcs::Details::ComputeSystemImpl,wistd::default_delete<Container::Manager::Hcs::Details::ComputeSystemImpl>>::~unique_ptr<Container::Manager::Hcs::Details::ComputeSystemImpl,wistd::default_delete<Container::Manager::Hcs::Details::ComputeSystemImpl>>(v32);
    operator delete(v32, (const struct std::nothrow_t *)8);
    if ( v28 )
    {
      Container::Manager::Core::Details::ComputeSystemReaperContext::~ComputeSystemReaperContext(v28);
      operator delete(v28, (const struct std::nothrow_t *)0x108);
    }
    wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(&v171, 0);
    Container::Manager::Core::Details::ContainerConfiguration::~ContainerConfiguration(v175);
    v153 = *a3;
    *a3 = 0;
    if ( v153 )
    {
      Container::Manager::Core::ResourceHandle::~ResourceHandle(v153);
      operator delete(v153, (const struct std::nothrow_t *)0x58);
    }
    v154 = *a4;
    *a4 = 0;
    if ( v154 )
    {
      Container::Manager::Core::ResourceHandle::~ResourceHandle(v154);
      operator delete(v154, (const struct std::nothrow_t *)0x58);
    }
    if ( *((_BYTE *)a5 + 24) )
      Container::Manager::Core::Details::DebugConfigurationHandle::~DebugConfigurationHandle(a5);
    return (unsigned int)v170;
  }
  v59 = CreateThreadpoolTimer(Container::Manager::Core::Details::ContainerObject::TransitionToFullPauseCallback, pv, 0);
  v187 = v59;
  if ( !v59 )
  {
    LODWORD(v170) = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x275,
                      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
                      v60);
    CloseThreadpoolTimer(ThreadpoolTimer);
    `eh vector destructor iterator'(
      v201,
      8u,
      3u,
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>);
    if ( v174 && !CloseHandle(v174) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v139, v140);
    if ( v173 && !CloseHandle(v173) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v141, v142);
    if ( hObject && !CloseHandle(hObject) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v143, v144);
    wistd::unique_ptr<Container::Manager::Hcs::Details::ComputeSystemImpl,wistd::default_delete<Container::Manager::Hcs::Details::ComputeSystemImpl>>::~unique_ptr<Container::Manager::Hcs::Details::ComputeSystemImpl,wistd::default_delete<Container::Manager::Hcs::Details::ComputeSystemImpl>>(v32);
    operator delete(v32, (const struct std::nothrow_t *)8);
    if ( v28 )
    {
      Container::Manager::Core::Details::ComputeSystemReaperContext::~ComputeSystemReaperContext(v28);
      operator delete(v28, (const struct std::nothrow_t *)0x108);
    }
    wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(&v171, 0);
    Container::Manager::Core::Details::ContainerConfiguration::~ContainerConfiguration(v175);
    v145 = *a3;
    *a3 = 0;
    if ( v145 )
    {
      Container::Manager::Core::ResourceHandle::~ResourceHandle(v145);
      operator delete(v145, (const struct std::nothrow_t *)0x58);
    }
    v146 = *a4;
    *a4 = 0;
    if ( v146 )
    {
      Container::Manager::Core::ResourceHandle::~ResourceHandle(v146);
      operator delete(v146, (const struct std::nothrow_t *)0x58);
    }
    if ( *((_BYTE *)a5 + 24) )
      Container::Manager::Core::Details::DebugConfigurationHandle::~DebugConfigurationHandle(a5);
    return (unsigned int)v170;
  }
  v61 = CreateThreadpoolTimer(Container::Manager::Core::Details::ContainerObject::StaticDutyCycleCallback, pva, 0);
  pti = v61;
  if ( !v61 )
  {
    v24 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x27B,
            (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
            v62);
    CloseThreadpoolTimer(v59);
    CloseThreadpoolTimer(ThreadpoolTimer);
    `eh vector destructor iterator'(
      v201,
      8u,
      3u,
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>);
    if ( v174 && !CloseHandle(v174) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v133, v134);
    if ( v173 && !CloseHandle(v173) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v135, v136);
    if ( hObject && !CloseHandle(hObject) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v137, v138);
    wistd::unique_ptr<Container::Manager::Hcs::Details::ComputeSystemImpl,wistd::default_delete<Container::Manager::Hcs::Details::ComputeSystemImpl>>::~unique_ptr<Container::Manager::Hcs::Details::ComputeSystemImpl,wistd::default_delete<Container::Manager::Hcs::Details::ComputeSystemImpl>>(v177);
    operator delete(v177, (const struct std::nothrow_t *)8);
    if ( v28 )
    {
      Container::Manager::Core::Details::ComputeSystemReaperContext::~ComputeSystemReaperContext(v28);
      operator delete(v28, (const struct std::nothrow_t *)0x108);
    }
    wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(&v171, 0);
    v30 = v175;
    goto LABEL_17;
  }
  v176 = 0;
  v63 = Container::Manager::Core::Details::SleepStudy::CreateContainerBlocker(
          Container::Manager::Core::Details::g_sleepStudy,
          v175,
          (char *)v175 + 40,
          &v176);
  LODWORD(v170) = v63;
  if ( v63 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x281,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
      (const char *)(unsigned int)v63,
      v168);
    v64 = v176;
    if ( v176 )
    {
      if ( *((_QWORD *)v176 + 1) )
      {
        SleepstudyHelperDestroyBlocker();
        v64 = v176;
      }
      operator delete(v64, (const struct std::nothrow_t *)0x10);
    }
    CloseThreadpoolTimer(v61);
    CloseThreadpoolTimer(v59);
    CloseThreadpoolTimer(ThreadpoolTimer);
    `eh vector destructor iterator'(
      v201,
      8u,
      3u,
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>);
    if ( v174 && !CloseHandle(v174) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v65, v66);
    if ( v173 && !CloseHandle(v173) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v67, v68);
    if ( hObject && !CloseHandle(hObject) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v69, v70);
LABEL_71:
    wistd::unique_ptr<Container::Manager::Hcs::Details::ComputeSystemImpl,wistd::default_delete<Container::Manager::Hcs::Details::ComputeSystemImpl>>::~unique_ptr<Container::Manager::Hcs::Details::ComputeSystemImpl,wistd::default_delete<Container::Manager::Hcs::Details::ComputeSystemImpl>>(v177);
    operator delete(v177, (const struct std::nothrow_t *)8);
    if ( v28 )
    {
      Container::Manager::Core::Details::ComputeSystemReaperContext::~ComputeSystemReaperContext(v28);
      operator delete(v28, (const struct std::nothrow_t *)0x108);
    }
    wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(&v171, 0);
    v34 = v175;
    goto LABEL_24;
  }
  v71 = Container::Manager::Core::ResourceHandle::Get<Container::Manager::Core::Details::ContainerStorage>(*a4);
  if ( (*(_BYTE *)(v71 + 272) & 8) != 0 )
  {
    LODWORD(v170) = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)0x289,
                      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
                      (const char *)5,
                      v168);
    wistd::unique_ptr<Container::Manager::Core::Details::SleepStudyBlocker,wistd::default_delete<Container::Manager::Core::Details::SleepStudyBlocker>>::~unique_ptr<Container::Manager::Core::Details::SleepStudyBlocker,wistd::default_delete<Container::Manager::Core::Details::SleepStudyBlocker>>(&v176);
    CloseThreadpoolTimer(v61);
    CloseThreadpoolTimer(v59);
    CloseThreadpoolTimer(ThreadpoolTimer);
    `eh vector destructor iterator'(
      v201,
      8u,
      3u,
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>);
    if ( v174 && !CloseHandle(v174) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v72, v73);
    if ( v173 && !CloseHandle(v173) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v74, v75);
    if ( hObject && !CloseHandle(hObject) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v76, v77);
    wistd::unique_ptr<Container::Manager::Hcs::Details::ComputeSystemImpl,wistd::default_delete<Container::Manager::Hcs::Details::ComputeSystemImpl>>::~unique_ptr<Container::Manager::Hcs::Details::ComputeSystemImpl,wistd::default_delete<Container::Manager::Hcs::Details::ComputeSystemImpl>>(v177);
    operator delete(v177, (const struct std::nothrow_t *)8);
    if ( v28 )
    {
      Container::Manager::Core::Details::ComputeSystemReaperContext::~ComputeSystemReaperContext(v28);
      operator delete(v28, (const struct std::nothrow_t *)0x108);
    }
    wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(&v171, 0);
    Container::Manager::Core::Details::ContainerConfiguration::~ContainerConfiguration(v175);
    v78 = *a3;
    *a3 = 0;
    if ( v78 )
    {
      Container::Manager::Core::ResourceHandle::~ResourceHandle(v78);
      operator delete(v78, (const struct std::nothrow_t *)0x58);
    }
    v79 = *a4;
    *a4 = 0;
    if ( v79 )
    {
      Container::Manager::Core::ResourceHandle::~ResourceHandle(v79);
      operator delete(v79, (const struct std::nothrow_t *)0x58);
    }
    if ( *((_BYTE *)a5 + 24) )
      Container::Manager::Core::Details::DebugConfigurationHandle::~DebugConfigurationHandle(a5);
    return (unsigned int)v170;
  }
  *(__m128i *)v181 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v182 = -1;
  v80 = Container::Manager::Core::Details::ResourceBroker::EnumerateIncomingNeighbors(
          *v193,
          v71,
          1,
          1,
          (__int64)v181,
          0);
  LODWORD(v170) = v80;
  if ( v80 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x291,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
      (const char *)(unsigned int)v80,
      v169);
    if ( v181[0] != (void *)-1LL )
      operator delete(v181[0], (const struct std::nothrow_t *)&std::nothrow);
    wistd::unique_ptr<Container::Manager::Core::Details::SleepStudyBlocker,wistd::default_delete<Container::Manager::Core::Details::SleepStudyBlocker>>::~unique_ptr<Container::Manager::Core::Details::SleepStudyBlocker,wistd::default_delete<Container::Manager::Core::Details::SleepStudyBlocker>>(&v176);
    CloseThreadpoolTimer(v61);
    CloseThreadpoolTimer(v59);
    CloseThreadpoolTimer(ThreadpoolTimer);
    `eh vector destructor iterator'(
      v201,
      8u,
      3u,
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>);
    if ( v174 && !CloseHandle(v174) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v81, v82);
    if ( v173 && !CloseHandle(v173) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v83, v84);
    if ( hObject && !CloseHandle(hObject) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v85, v86);
    goto LABEL_71;
  }
  if ( ((char *)v181[1] - (char *)v181[0]) >> 4 )
  {
    LODWORD(v170) = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)0x297,
                      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
                      (const char *)5,
                      v169);
    if ( v181[0] != (void *)-1LL )
      operator delete(v181[0], (const struct std::nothrow_t *)&std::nothrow);
    wistd::unique_ptr<Container::Manager::Core::Details::SleepStudyBlocker,wistd::default_delete<Container::Manager::Core::Details::SleepStudyBlocker>>::~unique_ptr<Container::Manager::Core::Details::SleepStudyBlocker,wistd::default_delete<Container::Manager::Core::Details::SleepStudyBlocker>>(&v176);
    CloseThreadpoolTimer(v61);
    CloseThreadpoolTimer(v59);
    CloseThreadpoolTimer(ThreadpoolTimer);
    `eh vector destructor iterator'(
      v201,
      8u,
      3u,
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>);
    if ( v174 && !CloseHandle(v174) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v87, v88);
    if ( v173 && !CloseHandle(v173) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v89, v90);
    if ( hObject && !CloseHandle(hObject) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v91, v92);
    wistd::unique_ptr<Container::Manager::Hcs::Details::ComputeSystemImpl,wistd::default_delete<Container::Manager::Hcs::Details::ComputeSystemImpl>>::~unique_ptr<Container::Manager::Hcs::Details::ComputeSystemImpl,wistd::default_delete<Container::Manager::Hcs::Details::ComputeSystemImpl>>(v177);
    operator delete(v177, (const struct std::nothrow_t *)8);
    if ( v28 )
    {
      Container::Manager::Core::Details::ComputeSystemReaperContext::~ComputeSystemReaperContext(v28);
      operator delete(v28, (const struct std::nothrow_t *)0x108);
    }
    wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(&v171, 0);
    Container::Manager::Core::Details::ContainerConfiguration::~ContainerConfiguration(v175);
    v93 = *a3;
    *a3 = 0;
    if ( v93 )
    {
      Container::Manager::Core::ResourceHandle::~ResourceHandle(v93);
      operator delete(v93, (const struct std::nothrow_t *)0x58);
    }
    v94 = *a4;
    *a4 = 0;
    if ( v94 )
    {
      Container::Manager::Core::ResourceHandle::~ResourceHandle(v94);
      operator delete(v94, (const struct std::nothrow_t *)0x58);
    }
    if ( *((_BYTE *)a5 + 24) )
      Container::Manager::Core::Details::DebugConfigurationHandle::~DebugConfigurationHandle(a5);
    return (unsigned int)v170;
  }
  wil::make_unique_nothrow<Csl::AsyncOperation<void>,>(&v170);
  v95 = v170;
  if ( !v170 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x29B,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
      (const char *)0x8007000ELL,
      v169);
    wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(&v170, 0);
    if ( v181[0] != (void *)-1LL )
      operator delete(v181[0], (const struct std::nothrow_t *)&std::nothrow);
    wistd::unique_ptr<Container::Manager::Core::Details::SleepStudyBlocker,wistd::default_delete<Container::Manager::Core::Details::SleepStudyBlocker>>::~unique_ptr<Container::Manager::Core::Details::SleepStudyBlocker,wistd::default_delete<Container::Manager::Core::Details::SleepStudyBlocker>>(&v176);
    CloseThreadpoolTimer(v61);
    CloseThreadpoolTimer(v59);
    CloseThreadpoolTimer(ThreadpoolTimer);
    `eh vector destructor iterator'(
      v201,
      8u,
      3u,
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>);
    if ( v174 && !CloseHandle(v174) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v127, v128);
    if ( v173 && !CloseHandle(v173) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v129, v130);
    if ( hObject && !CloseHandle(hObject) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v131, v132);
    wistd::unique_ptr<Container::Manager::Hcs::Details::ComputeSystemImpl,wistd::default_delete<Container::Manager::Hcs::Details::ComputeSystemImpl>>::~unique_ptr<Container::Manager::Hcs::Details::ComputeSystemImpl,wistd::default_delete<Container::Manager::Hcs::Details::ComputeSystemImpl>>(v177);
    operator delete(v177, (const struct std::nothrow_t *)8);
    goto LABEL_187;
  }
  wil::make_unique_nothrow<Csl::AsyncOperation<void>,>(&v178);
  v198 = v178;
  if ( !v178 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x29E,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
      (const char *)0x8007000ELL,
      v169);
    wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(&v178, 0);
    wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(&v170, 0);
    if ( v181[0] != (void *)-1LL )
      operator delete(v181[0], (const struct std::nothrow_t *)&std::nothrow);
    wistd::unique_ptr<Container::Manager::Core::Details::SleepStudyBlocker,wistd::default_delete<Container::Manager::Core::Details::SleepStudyBlocker>>::~unique_ptr<Container::Manager::Core::Details::SleepStudyBlocker,wistd::default_delete<Container::Manager::Core::Details::SleepStudyBlocker>>(&v176);
    CloseThreadpoolTimer(v61);
    CloseThreadpoolTimer(v59);
    CloseThreadpoolTimer(ThreadpoolTimer);
    `eh vector destructor iterator'(
      v201,
      8u,
      3u,
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>);
    __1__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAA_XZ(&v174);
    __1__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAA_XZ(&v173);
    __1__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAA_XZ(&hObject);
    wistd::unique_ptr<Container::Manager::Hcs::Details::ComputeSystemImpl,wistd::default_delete<Container::Manager::Hcs::Details::ComputeSystemImpl>>::~unique_ptr<Container::Manager::Hcs::Details::ComputeSystemImpl,wistd::default_delete<Container::Manager::Hcs::Details::ComputeSystemImpl>>(v177);
    operator delete(v177, (const struct std::nothrow_t *)8);
LABEL_187:
    if ( v28 )
    {
      Container::Manager::Core::Details::ComputeSystemReaperContext::~ComputeSystemReaperContext(v28);
      operator delete(v28, (const struct std::nothrow_t *)0x108);
    }
    wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(&v171, 0);
    Container::Manager::Core::Details::ContainerConfiguration::~ContainerConfiguration(v175);
    v124 = *v180;
    v126 = *v180 == 0;
    *v180 = 0;
    if ( !v126 )
    {
      Container::Manager::Core::ResourceHandle::~ResourceHandle(v124);
      operator delete(v124, (const struct std::nothrow_t *)0x58);
    }
    v125 = *a4;
    *a4 = 0;
    if ( v125 )
    {
      Container::Manager::Core::ResourceHandle::~ResourceHandle(v125);
      operator delete(v125, (const struct std::nothrow_t *)0x58);
    }
    v126 = *((_BYTE *)a5 + 24) == 0;
    goto LABEL_270;
  }
  v96 = 0;
  v183 = 0;
  v179 = 0;
  if ( *((_DWORD *)v175 + 22) == 1 )
  {
    v97 = Container::Manager::Core::Details::MemoryManager::CreateContainerMemoryContext(*v192, pva, &v183);
    v98 = v97;
    if ( v97 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2AA,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
        (const char *)(unsigned int)v97,
        v169);
      wistd::unique_ptr<Container::Manager::Core::Details::ContainerHeartbeatContext,wistd::default_delete<Container::Manager::Core::Details::ContainerHeartbeatContext>>::~unique_ptr<Container::Manager::Core::Details::ContainerHeartbeatContext,wistd::default_delete<Container::Manager::Core::Details::ContainerHeartbeatContext>>(&v179);
      if ( v183 )
        operator delete(v183, (const struct std::nothrow_t *)0x88);
      wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(&v178, 0);
      wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(&v170, 0);
      if ( v181[0] != (void *)-1LL )
        operator delete(v181[0], (const struct std::nothrow_t *)&std::nothrow);
      wistd::unique_ptr<Container::Manager::Core::Details::SleepStudyBlocker,wistd::default_delete<Container::Manager::Core::Details::SleepStudyBlocker>>::~unique_ptr<Container::Manager::Core::Details::SleepStudyBlocker,wistd::default_delete<Container::Manager::Core::Details::SleepStudyBlocker>>(&v176);
      CloseThreadpoolTimer(v61);
      CloseThreadpoolTimer(v59);
      CloseThreadpoolTimer(ThreadpoolTimer);
      `eh vector destructor iterator'(
        v201,
        8u,
        3u,
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>);
      __1__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAA_XZ(&v174);
      __1__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAA_XZ(&v173);
      __1__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAA_XZ(&hObject);
      wistd::unique_ptr<Container::Manager::Hcs::Details::ComputeSystemImpl,wistd::default_delete<Container::Manager::Hcs::Details::ComputeSystemImpl>>::~unique_ptr<Container::Manager::Hcs::Details::ComputeSystemImpl,wistd::default_delete<Container::Manager::Hcs::Details::ComputeSystemImpl>>(v177);
      operator delete(v177, (const struct std::nothrow_t *)8);
      if ( v28 )
      {
        Container::Manager::Core::Details::ComputeSystemReaperContext::~ComputeSystemReaperContext(v28);
        operator delete(v28, (const struct std::nothrow_t *)0x108);
      }
LABEL_128:
      wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(&v171, 0);
      Container::Manager::Core::Details::ContainerConfiguration::~ContainerConfiguration(v175);
      wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>::~unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>(v180);
      wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>::~unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>(v189);
      if ( *((_BYTE *)a5 + 24) )
        Container::Manager::Core::Details::DebugConfigurationHandle::~DebugConfigurationHandle(a5);
      return v98;
    }
    v99 = (char *)pva;
    v100 = Container::Manager::Core::Details::HeartbeatMonitor::CreateContainerHeartbeatContext(*v191, pva, &v179);
    v98 = v100;
    if ( v100 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2AB,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
        (const char *)(unsigned int)v100,
        v169);
      wistd::unique_ptr<Container::Manager::Core::Details::ContainerHeartbeatContext,wistd::default_delete<Container::Manager::Core::Details::ContainerHeartbeatContext>>::~unique_ptr<Container::Manager::Core::Details::ContainerHeartbeatContext,wistd::default_delete<Container::Manager::Core::Details::ContainerHeartbeatContext>>(&v179);
      if ( v183 )
        operator delete(v183, (const struct std::nothrow_t *)0x88);
      wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(&v178, 0);
      wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(&v170, 0);
      if ( v181[0] != (void *)-1LL )
        operator delete(v181[0], (const struct std::nothrow_t *)&std::nothrow);
      wistd::unique_ptr<Container::Manager::Core::Details::SleepStudyBlocker,wistd::default_delete<Container::Manager::Core::Details::SleepStudyBlocker>>::~unique_ptr<Container::Manager::Core::Details::SleepStudyBlocker,wistd::default_delete<Container::Manager::Core::Details::SleepStudyBlocker>>(&v176);
      CloseThreadpoolTimer(v61);
      CloseThreadpoolTimer(v59);
      CloseThreadpoolTimer(ThreadpoolTimer);
      `eh vector destructor iterator'(
        v201,
        8u,
        3u,
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>);
      __1__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAA_XZ(&v174);
      __1__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAA_XZ(&v173);
      __1__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAA_XZ(&hObject);
      wistd::unique_ptr<Container::Manager::Hcs::ComputeSystem,wistd::default_delete<Container::Manager::Hcs::ComputeSystem>>::~unique_ptr<Container::Manager::Hcs::ComputeSystem,wistd::default_delete<Container::Manager::Hcs::ComputeSystem>>(&v190);
      wistd::unique_ptr<Container::Manager::Core::Details::ComputeSystemReaperContext,wistd::default_delete<Container::Manager::Core::Details::ComputeSystemReaperContext>>::~unique_ptr<Container::Manager::Core::Details::ComputeSystemReaperContext,wistd::default_delete<Container::Manager::Core::Details::ComputeSystemReaperContext>>(&v185);
      goto LABEL_128;
    }
    v96 = v183;
  }
  else
  {
    v99 = (char *)pva;
  }
  v101 = v175;
  Container::Manager::Core::Details::ContainerConfiguration::operator=(v99, v175);
  v102 = (void *)*((_QWORD *)v99 + 68);
  *((_QWORD *)v99 + 68) = v96;
  v103 = 0;
  if ( v102 )
    operator delete(v102, (const struct std::nothrow_t *)0x88);
  wistd::unique_ptr<Container::Manager::Core::Details::ContainerHeartbeatContext,wistd::default_delete<Container::Manager::Core::Details::ContainerHeartbeatContext>>::operator=(
    v99 + 552,
    &v179);
  v171 = 0;
  wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(v99 + 1632, v196);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,2>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>>::operator=(
    v99 + 1176,
    &pwk);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,2>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>>::operator=(
    v99 + 1192,
    &v187);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,2>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>>::operator=(
    v99 + 1168,
    &pti);
  utl::shared_ptr<Container::Manager::Core::Details::PolicyManager>::operator=(v99 + 1232, v197);
  utl::shared_ptr<Container::Manager::Core::Details::PolicyManager>::operator=(v99 + 1304, v194);
  v104 = *a8;
  v105 = a8[1];
  if ( v105 )
    _InterlockedIncrement((volatile signed __int32 *)(v105 + 8));
  *((_QWORD *)v99 + 165) = v104;
  v106 = (utl::_RefCountBase *)*((_QWORD *)v99 + 166);
  *((_QWORD *)v99 + 166) = v105;
  if ( v106 )
    utl::_RefCountBase::_DecStrong(v106);
  wistd::unique_ptr<Container::Manager::Core::Details::ComputeSystemReaperContext,wistd::default_delete<Container::Manager::Core::Details::ComputeSystemReaperContext>>::operator=(
    v99 + 1248,
    &v185);
  wistd::unique_ptr<Container::Manager::Hcs::ComputeSystem,wistd::default_delete<Container::Manager::Hcs::ComputeSystem>>::operator=(
    v99 + 1256,
    &v190);
  v107 = v189;
  wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>::operator=(
    v99 + 1280,
    v189);
  v170 = 0;
  wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(v99 + 1288, v95);
  v178 = 0;
  wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(v99 + 1296, v198);
  v108 = *a9;
  v109 = a9[1];
  if ( v109 )
    _InterlockedIncrement((volatile signed __int32 *)(v109 + 8));
  *((_QWORD *)v99 + 167) = v108;
  v110 = (utl::_RefCountBase *)*((_QWORD *)v99 + 168);
  *((_QWORD *)v99 + 168) = v109;
  if ( v110 )
    utl::_RefCountBase::_DecStrong(v110);
  v111 = *v191;
  v112 = v191[1];
  if ( v112 )
    _InterlockedIncrement((volatile signed __int32 *)(v112 + 8));
  *((_QWORD *)v99 + 169) = v111;
  v113 = (utl::_RefCountBase *)*((_QWORD *)v99 + 170);
  *((_QWORD *)v99 + 170) = v112;
  if ( v113 )
    utl::_RefCountBase::_DecStrong(v113);
  v114 = *a11;
  v115 = a11[1];
  if ( v115 )
    _InterlockedIncrement((volatile signed __int32 *)(v115 + 8));
  *((_QWORD *)v99 + 171) = v114;
  v116 = (utl::_RefCountBase *)*((_QWORD *)v99 + 172);
  *((_QWORD *)v99 + 172) = v115;
  if ( v116 )
    utl::_RefCountBase::_DecStrong(v116);
  v117 = *v192;
  v118 = v192[1];
  if ( v118 )
    _InterlockedIncrement((volatile signed __int32 *)(v118 + 8));
  *((_QWORD *)v99 + 173) = v117;
  v119 = (utl::_RefCountBase *)*((_QWORD *)v99 + 174);
  *((_QWORD *)v99 + 174) = v118;
  if ( v119 )
    utl::_RefCountBase::_DecStrong(v119);
  wistd::unique_ptr<Container::Manager::Core::Details::SleepStudyBlocker,wistd::default_delete<Container::Manager::Core::Details::SleepStudyBlocker>>::operator=(
    v99 + 1224,
    &v176);
  __4__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAAAEAV01___QEAV01__Z(
    v99 + 968,
    &hObject);
  __4__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAAAEAV01___QEAV01__Z(
    v99 + 976,
    &v173);
  __4__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAAAEAV01___QEAV01__Z(
    v99 + 984,
    &v174);
  v120 = v180;
  *((_QWORD *)v99 + 188) = Container::Manager::Core::ResourceHandle::GetLeafLayer(*v180);
  wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>::operator=(
    v99 + 1496,
    v120);
  utl::shared_ptr<Container::Manager::Core::Details::PolicyManager>::operator=(v99 + 1400, v199);
  v121 = *a15;
  v122 = a15[1];
  if ( v122 )
    _InterlockedIncrement((volatile signed __int32 *)(v122 + 8));
  *((_QWORD *)v99 + 177) = v121;
  v123 = (utl::_RefCountBase *)*((_QWORD *)v99 + 178);
  *((_QWORD *)v99 + 178) = v122;
  if ( v123 )
    utl::_RefCountBase::_DecStrong(v123);
  *((_QWORD *)v99 + 195) = a18;
  utl::shared_ptr<Container::Manager::Core::Details::PolicyManager>::operator=(v99 + 1432, v193);
  utl::optional<Container::Manager::Core::Details::DebugConfigurationHandle>::operator=((Container::Manager::Core::Details::DebugConfigurationHandle *)(v99 + 1568));
  utl::shared_ptr<Container::Manager::Core::Details::PolicyManager>::operator=(v99 + 1448, v195);
  do
  {
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>::operator=(
      &v99[8 * v103 + 1008],
      &v201[v103]);
    ++v103;
  }
  while ( v103 != 3 );
  if ( (*(_DWORD *)(*(_QWORD *)v194 + 96LL) & 0x10) != 0 )
    *((_DWORD *)v99 + 302) = 1;
  if ( *((_DWORD *)v99 + 22) == 1 )
  {
    RtlInitializeBitMapEx(v99 + 720, v99 + 712, 64);
    RtlClearAllBitsEx(v99 + 720);
    RtlSetBitEx(v99 + 720, 0);
    v101 = v175;
  }
  else if ( *((_DWORD *)v99 + 22) == 2 )
  {
    v195 = 0;
    utl::optional<Container::Manager::Core::Details::ContainerObject::ArgonRuntimeState>::operator=<Container::Manager::Core::Details::ContainerObject::ArgonRuntimeState,0>(
      v99 + 1472,
      &v195);
    Container::Manager::Core::Details::ContainerObject::ArgonRuntimeState::~ArgonRuntimeState((Container::Manager::Core::Details::ContainerObject::ArgonRuntimeState *)&v195);
  }
  *((_QWORD *)v99 + 119) = MEMORY[0x7FFE0008];
  Container::Manager::Core::Details::ContainerObject::TransitionToLogicalState(v99, 1);
  wistd::unique_ptr<Container::Manager::Core::Details::ContainerHeartbeatContext,wistd::default_delete<Container::Manager::Core::Details::ContainerHeartbeatContext>>::~unique_ptr<Container::Manager::Core::Details::ContainerHeartbeatContext,wistd::default_delete<Container::Manager::Core::Details::ContainerHeartbeatContext>>(&v179);
  wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(&v178, 0);
  wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(&v170, 0);
  if ( v181[0] != (void *)-1LL )
    operator delete(v181[0], (const struct std::nothrow_t *)&std::nothrow);
  wistd::unique_ptr<Container::Manager::Core::Details::SleepStudyBlocker,wistd::default_delete<Container::Manager::Core::Details::SleepStudyBlocker>>::~unique_ptr<Container::Manager::Core::Details::SleepStudyBlocker,wistd::default_delete<Container::Manager::Core::Details::SleepStudyBlocker>>(&v176);
  if ( pti )
    CloseThreadpoolTimer(pti);
  if ( v187 )
    CloseThreadpoolTimer(v187);
  if ( pwk )
    CloseThreadpoolTimer(pwk);
  `eh vector destructor iterator'(
    v201,
    8u,
    3u,
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>);
  __1__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAA_XZ(&v174);
  __1__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAA_XZ(&v173);
  __1__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAA_XZ(&hObject);
  wistd::unique_ptr<Container::Manager::Hcs::ComputeSystem,wistd::default_delete<Container::Manager::Hcs::ComputeSystem>>::~unique_ptr<Container::Manager::Hcs::ComputeSystem,wistd::default_delete<Container::Manager::Hcs::ComputeSystem>>(&v190);
  wistd::unique_ptr<Container::Manager::Core::Details::ComputeSystemReaperContext,wistd::default_delete<Container::Manager::Core::Details::ComputeSystemReaperContext>>::~unique_ptr<Container::Manager::Core::Details::ComputeSystemReaperContext,wistd::default_delete<Container::Manager::Core::Details::ComputeSystemReaperContext>>(&v185);
  wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(&v171, 0);
  Container::Manager::Core::Details::ContainerConfiguration::~ContainerConfiguration(v101);
  wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>::~unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>(v120);
  wistd::unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>::~unique_ptr<Container::Manager::Core::ResourceHandle,wistd::default_delete<Container::Manager::Core::ResourceHandle>>(v107);
  if ( *((_BYTE *)a5 + 24) )
    Container::Manager::Core::Details::DebugConfigurationHandle::~DebugConfigurationHandle(a5);
  return 0;
}

```

## disassembly

```asm
0x1800a0644  push    rbp
0x1800a0646  push    rbx
0x1800a0647  push    rsi
0x1800a0648  push    rdi
0x1800a0649  push    r12
0x1800a064b  push    r13
0x1800a064d  push    r14
0x1800a064f  push    r15
0x1800a0651  lea     rbp, [rsp-0A8h]
0x1800a0659  sub     rsp, 1A8h
0x1800a0660  mov     rax, cs:__security_cookie
0x1800a0667  xor     rax, rsp
0x1800a066a  mov     [rbp+0E0h+var_48], rax
0x1800a0671  mov     r14, r9
0x1800a0674  mov     [rbp+0E0h+var_110], r9
0x1800a0678  mov     r15, r8
0x1800a067b  mov     [rbp+0E0h+var_160], r8
0x1800a067f  mov     rbx, rdx
0x1800a0682  mov     [rsp+1E0h+var_188], rdx
0x1800a0687  mov     rdi, rcx
0x1800a068a  mov     [rbp+0E0h+pv], rcx
0x1800a068e  mov     r12, [rbp+0E0h+arg_20]
0x1800a0695  mov     rax, [rbp+0E0h+arg_28]
0x1800a069c  mov     [rbp+0E0h+var_C8], rax
0x1800a06a0  mov     rax, [rbp+0E0h+arg_30]
0x1800a06a7  mov     [rbp+0E0h+var_E8], rax
0x1800a06ab  mov     rax, [rbp+0E0h+arg_48]
0x1800a06b2  mov     [rbp+0E0h+var_100], rax
0x1800a06b6  mov     rax, [rbp+0E0h+arg_58]
0x1800a06bd  mov     [rbp+0E0h+var_F8], rax
0x1800a06c1  mov     rax, [rbp+0E0h+arg_60]
0x1800a06c8  mov     [rbp+0E0h+var_F0], rax
0x1800a06cc  mov     rax, [rbp+0E0h+arg_68]
0x1800a06d3  mov     [rbp+0E0h+var_B8], rax
0x1800a06d7  mov     rax, [rbp+0E0h+arg_78]
0x1800a06de  mov     qword ptr [rbp+0E0h+var_E0], rax
0x1800a06e2  mov     rsi, [rbp+0E0h+arg_80]
0x1800a06e9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800a06f0  mov     ecx, 18h; unsigned __int64
0x1800a06f5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800a06fa  mov     [rbp+0E0h+var_D0], rax
0x1800a06fe  xor     r13d, r13d
0x1800a0701  test    rax, rax
0x1800a0704  jz      loc_1800A21B4
0x1800a070a  mov     [rax], r13
0x1800a070d  mov     [rax+8], r13
0x1800a0711  mov     [rax+10h], r13
0x1800a0715  mov     [rsp+1E0h+var_1A8], rax
0x1800a071a  cmp     dword ptr [rbx+48h], 8
0x1800a071e  jz      loc_1800A07BE
0x1800a0724  mov     rdx, rax
0x1800a0727  mov     rcx, rsi
0x1800a072a  call    ?WatchForUpdatesToComplete@ServicingOrchestrator@Details@Core@Manager@Container@@QEAAJAEAV?$AsyncOperation@X@Csl@@@Z; Container::Manager::Core::Details::ServicingOrchestrator::WatchForUpdatesToComplete(Csl::AsyncOperation<void> &)
0x1800a072f  mov     esi, eax
0x1800a0731  test    eax, eax
0x1800a0733  jns     loc_1800A07BE
0x1800a0739  mov     rcx, [rbp+0E8h]; this
0x1800a0740  mov     r9d, eax; char *
0x1800a0743  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800a074a  mov     edx, 22Bh; void *
0x1800a074f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a0754  xor     edx, edx
0x1800a0756  lea     rcx, [rsp+1E0h+var_1A8]
0x1800a075b  call    ?reset@?$unique_ptr@V?$AsyncOperation@X@Csl@@U?$default_delete@V?$AsyncOperation@X@Csl@@@wistd@@@wistd@@QEAAXPEAV?$AsyncOperation@X@Csl@@@Z; wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(Csl::AsyncOperation<void> *)
0x1800a0760  mov     rcx, rbx; this
0x1800a0763  call    ??1ContainerConfiguration@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::ContainerConfiguration::~ContainerConfiguration(void)
0x1800a0768  mov     rdi, [r15]
0x1800a076b  mov     [r15], r13
0x1800a076e  mov     ebx, 58h ; 'X'
0x1800a0773  test    rdi, rdi
0x1800a0776  jz      short loc_1800A078A
0x1800a0778  mov     rcx, rdi; this
0x1800a077b  call    ??1ResourceHandle@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::ResourceHandle::~ResourceHandle(void)
0x1800a0780  mov     edx, ebx; struct std::nothrow_t *
0x1800a0782  mov     rcx, rdi; void *
0x1800a0785  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a078a  mov     rdi, [r14]
0x1800a078d  test    rdi, rdi
0x1800a0790  mov     [r14], r13
0x1800a0793  jz      short loc_1800A07A8
0x1800a0795  mov     rcx, rdi; this
0x1800a0798  call    ??1ResourceHandle@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::ResourceHandle::~ResourceHandle(void)
0x1800a079d  mov     rdx, rbx; struct std::nothrow_t *
0x1800a07a0  mov     rcx, rdi; void *
0x1800a07a3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a07a8  cmp     [r12+18h], r13b
0x1800a07ad  jz      short loc_1800A07B7
0x1800a07af  mov     rcx, r12; this
0x1800a07b2  call    ??1DebugConfigurationHandle@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::DebugConfigurationHandle::~DebugConfigurationHandle(void)
0x1800a07b7  mov     eax, esi
0x1800a07b9  jmp     loc_1800A223F
0x1800a07be  lea     rcx, [rbp+0E0h+var_130]
0x1800a07c2  call    ??$make_unique_nothrow@VComputeSystemReaperContext@Details@Core@Manager@Container@@$$V@wil@@YA?AV?$unique_ptr@VComputeSystemReaperContext@Details@Core@Manager@Container@@U?$default_delete@VComputeSystemReaperContext@Details@Core@Manager@Container@@@wistd@@@wistd@@XZ; wil::make_unique_nothrow<Container::Manager::Core::Details::ComputeSystemReaperContext,>(void)
0x1800a07c7  mov     r13, [rbp+0E0h+var_130]
0x1800a07cb  xor     esi, esi
0x1800a07cd  test    r13, r13
0x1800a07d0  jz      loc_1800A2194
0x1800a07d6  mov     rcx, r13; this
0x1800a07d9  call    ?Initialize@ComputeSystemReaperContext@Details@Core@Manager@Container@@QEAAJXZ; Container::Manager::Core::Details::ComputeSystemReaperContext::Initialize(void)
0x1800a07de  mov     esi, eax
0x1800a07e0  test    eax, eax
0x1800a07e2  jns     short loc_1800A0835
0x1800a07e4  mov     rcx, [rbp+0E8h]; this
0x1800a07eb  mov     r9d, eax; char *
0x1800a07ee  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800a07f5  mov     edx, 234h; void *
0x1800a07fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a07ff  test    r13, r13
0x1800a0802  jz      short loc_1800A0819
0x1800a0804  mov     rcx, r13; this
0x1800a0807  call    ??1ComputeSystemReaperContext@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::ComputeSystemReaperContext::~ComputeSystemReaperContext(void)
0x1800a080c  mov     edx, 108h; struct std::nothrow_t *
0x1800a0811  mov     rcx, r13; void *
0x1800a0814  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a0819  xor     edx, edx
0x1800a081b  lea     rcx, [rsp+1E0h+var_1A8]
0x1800a0820  call    ?reset@?$unique_ptr@V?$AsyncOperation@X@Csl@@U?$default_delete@V?$AsyncOperation@X@Csl@@@wistd@@@wistd@@QEAAXPEAV?$AsyncOperation@X@Csl@@@Z; wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(Csl::AsyncOperation<void> *)
0x1800a0825  mov     rcx, rbx; this
0x1800a0828  call    ??1ContainerConfiguration@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::ContainerConfiguration::~ContainerConfiguration(void)
0x1800a082d  xor     r13d, r13d
0x1800a0830  jmp     loc_1800A0768
0x1800a0835  mov     byte ptr [r13+41h], 1
0x1800a083a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800a0841  mov     ecx, 8; unsigned __int64
0x1800a0846  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800a084b  mov     rsi, rax
0x1800a084e  mov     [rsp+1E0h+var_178], rax
0x1800a0853  test    rax, rax
0x1800a0856  jz      loc_1800A20FC
0x1800a085c  mov     qword ptr [rax], 0
0x1800a0863  mov     [rbp+0E0h+var_108], rax
0x1800a0867  mov     rcx, rax; this
0x1800a086a  call    ?Initialize@ComputeSystem@Hcs@Manager@Container@@QEAAJXZ; Container::Manager::Hcs::ComputeSystem::Initialize(void)
0x1800a086f  mov     dword ptr [rsp+1E0h+var_1B0], eax
0x1800a0873  test    eax, eax
0x1800a0875  jns     loc_1800A0933
0x1800a087b  mov     rcx, [rbp+0E8h]; this
0x1800a0882  mov     r9d, eax; char *
0x1800a0885  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800a088c  mov     edx, 23Dh; void *
0x1800a0891  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a0896  mov     rcx, rsi
0x1800a0899  call    ??1?$unique_ptr@VComputeSystemImpl@Details@Hcs@Manager@Container@@U?$default_delete@VComputeSystemImpl@Details@Hcs@Manager@Container@@@wistd@@@wistd@@QEAA@XZ; wistd::unique_ptr<Container::Manager::Hcs::Details::ComputeSystemImpl,wistd::default_delete<Container::Manager::Hcs::Details::ComputeSystemImpl>>::~unique_ptr<Container::Manager::Hcs::Details::ComputeSystemImpl,wistd::default_delete<Container::Manager::Hcs::Details::ComputeSystemImpl>>(void)
0x1800a089e  mov     edx, 8; struct std::nothrow_t *
0x1800a08a3  mov     rcx, rsi; void *
0x1800a08a6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a08ab  xor     esi, esi
0x1800a08ad  test    r13, r13
0x1800a08b0  jz      short loc_1800A08C7
0x1800a08b2  mov     rcx, r13; this
0x1800a08b5  call    ??1ComputeSystemReaperContext@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::ComputeSystemReaperContext::~ComputeSystemReaperContext(void)
0x1800a08ba  mov     edx, 108h; struct std::nothrow_t *
0x1800a08bf  mov     rcx, r13; void *
0x1800a08c2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a08c7  xor     edx, edx
0x1800a08c9  lea     rcx, [rsp+1E0h+var_1A8]
0x1800a08ce  call    ?reset@?$unique_ptr@V?$AsyncOperation@X@Csl@@U?$default_delete@V?$AsyncOperation@X@Csl@@@wistd@@@wistd@@QEAAXPEAV?$AsyncOperation@X@Csl@@@Z; wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(Csl::AsyncOperation<void> *)
0x1800a08d3  mov     rcx, rbx; this
0x1800a08d6  call    ??1ContainerConfiguration@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::ContainerConfiguration::~ContainerConfiguration(void)
0x1800a08db  mov     rdi, [r15]
0x1800a08de  mov     [r15], rsi
0x1800a08e1  mov     ebx, 58h ; 'X'
0x1800a08e6  test    rdi, rdi
0x1800a08e9  jz      short loc_1800A08FD
0x1800a08eb  mov     rcx, rdi; this
0x1800a08ee  call    ??1ResourceHandle@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::ResourceHandle::~ResourceHandle(void)
0x1800a08f3  mov     edx, ebx; struct std::nothrow_t *
0x1800a08f5  mov     rcx, rdi; void *
0x1800a08f8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a08fd  mov     rdi, [r14]
0x1800a0900  test    rdi, rdi
0x1800a0903  mov     [r14], rsi
0x1800a0906  jz      short loc_1800A091B
0x1800a0908  mov     rcx, rdi; this
0x1800a090b  call    ??1ResourceHandle@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::ResourceHandle::~ResourceHandle(void)
0x1800a0910  mov     rdx, rbx; struct std::nothrow_t *
0x1800a0913  mov     rcx, rdi; void *
0x1800a0916  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a091b  cmp     [r12+18h], sil
0x1800a0920  jz      short loc_1800A092A
0x1800a0922  mov     rcx, r12; this
0x1800a0925  call    ??1DebugConfigurationHandle@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::DebugConfigurationHandle::~DebugConfigurationHandle(void)
0x1800a092a  mov     eax, dword ptr [rsp+1E0h+var_1B0]
0x1800a092e  jmp     loc_1800A223F
0x1800a0933  mov     [rsp+1E0h+hObject], 0
0x1800a093c  xor     r9d, r9d
0x1800a093f  lea     edx, [r9+1]
0x1800a0943  lea     rcx, [rsp+1E0h+hObject]
0x1800a0948  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800a094d  mov     dword ptr [rsp+1E0h+var_1B0], eax
0x1800a0951  test    eax, eax
0x1800a0953  jns     short loc_1800A0997
0x1800a0955  mov     rcx, [rbp+0E8h]; this
0x1800a095c  mov     r9d, eax; char *
0x1800a095f  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800a0966  mov     edx, 242h; void *
0x1800a096b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a0970  mov     rcx, [rsp+1E0h+hObject]; hObject
0x1800a0975  test    rcx, rcx
0x1800a0978  jz      loc_1800A0896
0x1800a097e  call    cs:__imp_CloseHandle
0x1800a0985  nop     dword ptr [rax+rax+00h]
0x1800a098a  test    eax, eax
0x1800a098c  jz      loc_1800A2275
0x1800a0992  jmp     loc_1800A0896
0x1800a0997  mov     [rsp+1E0h+var_198], 0
0x1800a09a0  xor     r9d, r9d
0x1800a09a3  xor     edx, edx
0x1800a09a5  lea     rcx, [rsp+1E0h+var_198]
0x1800a09aa  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800a09af  mov     dword ptr [rsp+1E0h+var_1B0], eax
0x1800a09b3  test    eax, eax
0x1800a09b5  jns     short loc_1800A0A17
0x1800a09b7  mov     rcx, [rbp+0E8h]; this
0x1800a09be  mov     r9d, eax; char *
0x1800a09c1  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800a09c8  mov     edx, 247h; void *
0x1800a09cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a09d2  mov     rcx, [rsp+1E0h+var_198]; hObject
0x1800a09d7  test    rcx, rcx
0x1800a09da  jz      short loc_1800A09F0
0x1800a09dc  call    cs:__imp_CloseHandle
0x1800a09e3  nop     dword ptr [rax+rax+00h]
0x1800a09e8  test    eax, eax
0x1800a09ea  jz      loc_1800A22AB
0x1800a09f0  mov     rcx, [rsp+1E0h+hObject]; hObject
0x1800a09f5  test    rcx, rcx
0x1800a09f8  jz      loc_1800A0896
0x1800a09fe  call    cs:__imp_CloseHandle
0x1800a0a05  nop     dword ptr [rax+rax+00h]
0x1800a0a0a  test    eax, eax
0x1800a0a0c  jz      loc_1800A2287
0x1800a0a12  jmp     loc_1800A0896
0x1800a0a17  mov     [rsp+1E0h+var_190], 0
0x1800a0a20  xor     r9d, r9d
0x1800a0a23  xor     edx, edx
0x1800a0a25  lea     rcx, [rsp+1E0h+var_190]
0x1800a0a2a  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800a0a2f  mov     dword ptr [rsp+1E0h+var_1B0], eax
0x1800a0a33  test    eax, eax
0x1800a0a35  jns     loc_1800A0AFA
0x1800a0a3b  mov     rcx, [rbp+0E8h]; this
0x1800a0a42  mov     r9d, eax; char *
0x1800a0a45  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800a0a4c  mov     edx, 24Ch; void *
0x1800a0a51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a0a56  mov     rcx, [rsp+1E0h+var_190]; hObject
0x1800a0a5b  test    rcx, rcx
0x1800a0a5e  jz      short loc_1800A0A74
0x1800a0a60  call    cs:__imp_CloseHandle
0x1800a0a67  nop     dword ptr [rax+rax+00h]
0x1800a0a6c  test    eax, eax
0x1800a0a6e  jz      loc_1800A22BD
0x1800a0a74  mov     rcx, [rsp+1E0h+var_198]; hObject
0x1800a0a79  test    rcx, rcx
0x1800a0a7c  jz      short loc_1800A0A92
0x1800a0a7e  call    cs:__imp_CloseHandle
0x1800a0a85  nop     dword ptr [rax+rax+00h]
0x1800a0a8a  test    eax, eax
0x1800a0a8c  jz      loc_1800A22CF
0x1800a0a92  mov     rcx, [rsp+1E0h+hObject]; hObject
0x1800a0a97  test    rcx, rcx
0x1800a0a9a  jz      short loc_1800A0AB0
0x1800a0a9c  call    cs:__imp_CloseHandle
0x1800a0aa3  nop     dword ptr [rax+rax+00h]
0x1800a0aa8  test    eax, eax
0x1800a0aaa  jz      loc_1800A22E1
0x1800a0ab0  mov     rcx, rsi
0x1800a0ab3  call    ??1?$unique_ptr@VComputeSystemImpl@Details@Hcs@Manager@Container@@U?$default_delete@VComputeSystemImpl@Details@Hcs@Manager@Container@@@wistd@@@wistd@@QEAA@XZ; wistd::unique_ptr<Container::Manager::Hcs::Details::ComputeSystemImpl,wistd::default_delete<Container::Manager::Hcs::Details::ComputeSystemImpl>>::~unique_ptr<Container::Manager::Hcs::Details::ComputeSystemImpl,wistd::default_delete<Container::Manager::Hcs::Details::ComputeSystemImpl>>(void)
0x1800a0ab8  mov     edx, 8; struct std::nothrow_t *
0x1800a0abd  mov     rcx, rsi; void *
0x1800a0ac0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a0ac5  test    r13, r13
0x1800a0ac8  jz      short loc_1800A0ADF
0x1800a0aca  mov     rcx, r13; this
0x1800a0acd  call    ??1ComputeSystemReaperContext@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::ComputeSystemReaperContext::~ComputeSystemReaperContext(void)
0x1800a0ad2  mov     edx, 108h; struct std::nothrow_t *
0x1800a0ad7  mov     rcx, r13; void *
0x1800a0ada  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a0adf  xor     edx, edx
0x1800a0ae1  lea     rcx, [rsp+1E0h+var_1A8]
0x1800a0ae6  call    ?reset@?$unique_ptr@V?$AsyncOperation@X@Csl@@U?$default_delete@V?$AsyncOperation@X@Csl@@@wistd@@@wistd@@QEAAXPEAV?$AsyncOperation@X@Csl@@@Z; wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(Csl::AsyncOperation<void> *)
0x1800a0aeb  mov     rcx, rbx; this
0x1800a0aee  call    ??1ContainerConfiguration@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::ContainerConfiguration::~ContainerConfiguration(void)
0x1800a0af3  xor     esi, esi
0x1800a0af5  jmp     loc_1800A08DB
0x1800a0afa  lea     rax, ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$01@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>(void)
0x1800a0b01  mov     [rsp+1E0h+var_1C0], rax; unsigned int
0x1800a0b06  lea     r9, ??0?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$01@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; void (*)(void *)
0x1800a0b0d  mov     edx, 8; unsigned __int64
0x1800a0b12  lea     r8d, [rdx-5]; unsigned __int64
0x1800a0b16  lea     rcx, [rbp+0E0h+var_60]; void *
0x1800a0b1d  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1800a0b22  xor     eax, eax
0x1800a0b24  mov     ebx, eax
0x1800a0b26  mov     dword ptr [rsp+1E0h+var_1B0], eax
0x1800a0b2a  mov     qword ptr [rbp+0E0h+pcbe.Version], 3
0x1800a0b32  mov     qword ptr [rbp+0E0h+pcbe.Size], 48h ; 'H'
0x1800a0b3a  mov     [rbp+0E0h+pcbe.CleanupGroup], rax
0x1800a0b3e  mov     [rbp+0E0h+pcbe.CleanupGroupCancelCallback], rax
  ... truncated ...
```
