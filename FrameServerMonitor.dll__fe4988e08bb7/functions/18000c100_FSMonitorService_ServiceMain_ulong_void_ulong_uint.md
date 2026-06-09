# FSMonitorService::ServiceMain(ulong,void *,ulong,uint)

- ea: `0x18000c100`
- end: `0x18000c67b`
- name: `?ServiceMain@FSMonitorService@@UEAAJKPEAXKI@Z`
- size: `1403`
- prototype: `__int64 __usercall@<rax>(FSMonitorService *__hidden this@<rcx>, unsigned int@<edx>, void *@<r8>, unsigned int@<r9d>, unsigned int)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800056a8`
- `0x180005f98`
- `0x180006a14`
- `0x180006a68`
- `0x180006a98`
- `0x180006b84`
- `0x1800071e4`
- `0x180009090`
- `0x18000950c`
- `0x18000985c`
- `0x18000c100`
- `0x18000ede0`
- `0x180018a20`
- `0x180031008`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c13d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c38f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c13d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c38f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c2e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c30c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c39d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c624`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c2e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c30c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c39d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c624`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c22d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c2a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c22d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c2a5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000c293`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000c293`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c301`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c301`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000c1eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000c1f4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000c1eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000c1f4`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000c21e`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000c21e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18000c3a7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18000c3a7`
- `MFPlat!MFStartup` at `0x18000c26b`
- `MFPlat!MFStartup` at `0x18000c26b`
- `MFPlat!MFRegisterPlatformWithMMCSS` at `0x18000c407`
- `MFPlat!MFRegisterPlatformWithMMCSS` at `0x18000c407`
- `MFPlat!MFPutWorkItem` at `0x18000c428`
- `MFPlat!MFPutWorkItem` at `0x18000c523`
- `MFPlat!MFPutWorkItem` at `0x18000c428`
- `MFPlat!MFPutWorkItem` at `0x18000c523`
- `MFPlat!MFSetMinimumMemoryAlignment` at `0x18000c3d3`
- `MFPlat!MFSetMinimumMemoryAlignment` at `0x18000c3d3`

## pseudocode

```c
__int64 __fastcall FSMonitorService::ServiceMain(FSMonitorService *this, __int64 a2, void *a3, int a4, unsigned int a5)
{
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  unsigned int v9; // r13d
  signed int v10; // edi
  __int64 v11; // rdx
  HANDLE CurrentProcess; // rdi
  HANDLE v13; // rax
  signed int LastError; // eax
  HRESULT started; // eax
  struct _TP_TIMER *ThreadpoolTimer; // rax
  signed int v17; // eax
  __int64 v18; // rdx
  struct CallStackTracing *v19; // rsi
  int v20; // r15d
  __int64 v21; // rsi
  char *v22; // r12
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  void **v24; // rsi
  __int64 (__fastcall *v25)(struct IFSMService *, const struct _GUID *, void **); // rdi
  __int64 (__fastcall ***v26)(_QWORD, GUID *, struct _FILETIME *); // rsi
  __int64 (__fastcall *v27)(_QWORD, GUID *, struct _FILETIME *); // rdi
  const unsigned __int16 *v28; // rdx
  __int64 v29; // rdx
  _SYSTEM_INFO SystemInfo; // [rsp+40h] [rbp-30h] BYREF
  DWORD pdwTaskId; // [rsp+B0h] [rbp+40h] BYREF
  struct _FILETIME pftDueTime; // [rsp+C0h] [rbp+50h] BYREF

  pdwTaskId = 0;
  v5 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 48);
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  v9 = a5;
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
    WPP_SF_qDD(*((_QWORD *)WPP_GLOBAL_Control + 27), 16, &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids, this, a4, a5);
  if ( !a3 )
  {
    v10 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_72;
    v11 = 17;
    goto LABEL_6;
  }
  if ( *((_DWORD *)this + 23) )
  {
    v10 = -1072871856;
    if ( !g_wppLevels )
      goto LABEL_72;
    v11 = 18;
    goto LABEL_6;
  }
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    (char *)this + 128,
    0);
  CurrentProcess = GetCurrentProcess();
  v13 = GetCurrentProcess();
  if ( !DuplicateHandle(v13, a3, CurrentProcess, (LPHANDLE)this + 16, 0, 0, 2u) )
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    if ( v10 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_72;
      v11 = 19;
      goto LABEL_6;
    }
  }
  *((_DWORD *)this + 30) = a4;
  *((_DWORD *)this + 86) = v9;
  started = MFStartup(0x20070u, 0);
  v10 = started;
  if ( started != -2147467263 )
  {
    if ( started < 0 )
    {
      if ( g_wppLevels )
      {
        v18 = 21;
        goto LABEL_32;
      }
      goto LABEL_72;
    }
    v19 = CallStackTracing::s_wpInstance;
    *((_BYTE *)this + 88) = 1;
    if ( v19 || (CallStackTracing::InitInstance(), (v19 = CallStackTracing::s_wpInstance) != 0) )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)v19 + 16));
      *((_BYTE *)v19 + 8) = 0;
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v19 + 16));
    }
    GetSystemInfo(&SystemInfo);
    if ( ((SystemInfo.dwPageSize - 1) & SystemInfo.dwPageSize) == 0 )
    {
      started = MFSetMinimumMemoryAlignment();
      v10 = started;
      if ( started < 0 )
      {
        if ( g_wppLevels )
        {
          v18 = 23;
          goto LABEL_32;
        }
        goto LABEL_72;
      }
      if ( MFRegisterPlatformWithMMCSS(L"Audio", &pdwTaskId, -2) >= 0 )
      {
        *((_DWORD *)this + 26) = pdwTaskId;
        *((_BYTE *)this + 89) = 1;
      }
      started = MFPutWorkItem(5u, (IMFAsyncCallback *)this + 2, 0);
      v10 = started;
      if ( started < 0 )
      {
        if ( g_wppLevels )
        {
          v18 = 24;
          goto LABEL_32;
        }
        goto LABEL_72;
      }
      v20 = 0;
      while ( 1 )
      {
        pftDueTime = 0;
        v21 = 16LL * v20;
        v22 = (char *)this + v21;
        event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((__int64)this + v21 + 176);
        v10 = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
        if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
          break;
        v24 = (void **)((char *)this + v21);
        v25 = funcs_18000C4A9[v20];
        wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(v24 + 21);
        event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = v25(this, &GUID_d97fb26a_db7e_414f_8776_cec04d293a0f, v24 + 21);
        v10 = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
        if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_71;
          v29 = 26;
LABEL_70:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v29,
            &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids,
            this,
            event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z);
          goto LABEL_71;
        }
        v10 = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)v24[21] + 24LL))(
                v24[21],
                *((_QWORD *)this + 2 * v20 + 22));
        if ( v10 < 0 )
        {
          __4__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAAAEAV01___T_Z(v22 + 176);
          if ( g_wppLevels )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              27,
              &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids,
              this,
              v10);
          goto LABEL_71;
        }
        v26 = (__int64 (__fastcall ***)(_QWORD, GUID *, struct _FILETIME *))v24[21];
        v27 = **v26;
        wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&pftDueTime);
        event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = v27(v26, &GUID_00000000_0000_0000_c000_000000000046, &pftDueTime);
        v10 = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
        if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
        {
          if ( g_wppLevels )
          {
            v29 = 28;
            goto LABEL_70;
          }
LABEL_71:
          wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&pftDueTime);
          goto LABEL_72;
        }
        event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = MFPutWorkItem(5u, (IMFAsyncCallback *)this + 1, *(IUnknown **)&pftDueTime);
        v10 = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
        if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
        {
          if ( g_wppLevels )
          {
            v29 = 29;
            goto LABEL_70;
          }
          goto LABEL_71;
        }
        wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&pftDueTime);
        if ( ++v20 >= 2 )
        {
          started = FSMonitorService::InternalRegisterRpcEndpoint(this, v28);
          v10 = started;
          if ( started >= 0 )
          {
            *((_DWORD *)this + 23) = 1;
            started = FSMonitorService::InternalStartIdleTimer(this);
            v10 = started;
            if ( started >= 0 )
              goto LABEL_26;
            if ( g_wppLevels )
            {
              v18 = 31;
              goto LABEL_32;
            }
          }
          else
          {
            if ( !g_wppLevels )
              goto LABEL_72;
            v18 = 30;
LABEL_32:
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v18,
              &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids,
              this,
              started);
          }
LABEL_72:
          LeaveCriticalSection(v5);
LABEL_73:
          if ( byte_18005E5A5 )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 27),
              32,
              &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids,
              this,
              v10);
          FSMonitorService::InternalShutdown(this);
          return (unsigned int)v10;
        }
      }
      if ( !g_wppLevels )
        goto LABEL_71;
      v29 = 25;
      goto LABEL_70;
    }
    v10 = -2147418113;
    if ( !g_wppLevels )
      goto LABEL_72;
    v11 = 22;
LABEL_6:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids, this, v10);
    goto LABEL_72;
  }
  pftDueTime = (struct _FILETIME)-50000000LL;
  ThreadpoolTimer = CreateThreadpoolTimer(FSMonitorService::TimerCallback, this, 0);
  *((_QWORD *)this + 17) = ThreadpoolTimer;
  if ( ThreadpoolTimer )
  {
    SetThreadpoolTimer(ThreadpoolTimer, &pftDueTime, 0, 0);
    v10 = 0;
LABEL_26:
    LeaveCriticalSection(v5);
  }
  else
  {
    v17 = GetLastError();
    v10 = v17;
    if ( v17 > 0 )
      v10 = (unsigned __int16)v17 | 0x80070000;
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids, this, v10);
    LeaveCriticalSection(v5);
    if ( v10 < 0 )
      goto LABEL_73;
  }
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), 33, &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids, this, v10);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000c100  mov     [rsp-38h+arg_8], rbx
0x18000c105  push    rbp
0x18000c106  push    rsi
0x18000c107  push    rdi
0x18000c108  push    r12
0x18000c10a  push    r13
0x18000c10c  push    r14
0x18000c10e  push    r15
0x18000c110  mov     rbp, rsp
0x18000c113  sub     rsp, 70h
0x18000c117  xorps   xmm0, xmm0
0x18000c11a  mov     [rbp+pdwTaskId], 0
0x18000c121  lea     rbx, [rcx+30h]
0x18000c125  mov     r14, rcx
0x18000c128  mov     rcx, rbx; lpCriticalSection
0x18000c12b  mov     r12d, r9d
0x18000c12e  mov     r15, r8
0x18000c131  movups  xmmword ptr [rbp+SystemInfo], xmm0
0x18000c135  movups  xmmword ptr [rbp+SystemInfo.lpMaximumApplicationAddress], xmm0
0x18000c139  movups  xmmword ptr [rbp+SystemInfo.dwNumberOfProcessors], xmm0
0x18000c13d  call    cs:__imp_EnterCriticalSection
0x18000c143  cmp     cs:byte_18005E5A5, 8
0x18000c14a  mov     r13d, [rbp+arg_20]
0x18000c14e  jb      short loc_18000C17C
0x18000c150  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c157  lea     r8, WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids
0x18000c15e  mov     edx, 10h
0x18000c163  mov     [rsp+70h+bInheritHandle], r13d
0x18000c168  mov     r9, r14
0x18000c16b  mov     [rsp+70h+dwDesiredAccess], r12d
0x18000c170  mov     rcx, [rcx+0D8h]
0x18000c177  call    WPP_SF_qDD
0x18000c17c  test    r15, r15
0x18000c17f  jnz     short loc_18000C1BA
0x18000c181  mov     edi, 80070057h
0x18000c186  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000c18d  jb      loc_18000C621
0x18000c193  lea     edx, [r15+11h]
0x18000c197  mov     [rsp+70h+dwDesiredAccess], edi
0x18000c19b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c1a2  lea     r8, WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids
0x18000c1a9  mov     r9, r14
0x18000c1ac  mov     rcx, [rcx+10h]
0x18000c1b0  call    WPP_SF_qD
0x18000c1b5  jmp     loc_18000C621
0x18000c1ba  cmp     dword ptr [r14+5Ch], 0
0x18000c1bf  jz      short loc_18000C1DA
0x18000c1c1  mov     edi, 0C00D4650h
0x18000c1c6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000c1cd  jb      loc_18000C621
0x18000c1d3  mov     edx, 12h
0x18000c1d8  jmp     short loc_18000C197
0x18000c1da  lea     rsi, [r14+80h]
0x18000c1e1  xor     edx, edx
0x18000c1e3  mov     rcx, rsi
0x18000c1e6  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000c1eb  call    cs:__imp_GetCurrentProcess
0x18000c1f1  mov     rdi, rax
0x18000c1f4  call    cs:__imp_GetCurrentProcess
0x18000c1fa  mov     [rsp+70h+dwOptions], 2; dwOptions
0x18000c202  mov     r9, rsi; lpTargetHandle
0x18000c205  mov     rcx, rax; hSourceProcessHandle
0x18000c208  mov     [rsp+70h+bInheritHandle], 0; bInheritHandle
0x18000c210  mov     r8, rdi; hTargetProcessHandle
0x18000c213  mov     [rsp+70h+dwDesiredAccess], 0; dwDesiredAccess
0x18000c21b  mov     rdx, r15; hSourceHandle
0x18000c21e  call    cs:__imp_DuplicateHandle
0x18000c224  mov     esi, 80070000h
0x18000c229  test    eax, eax
0x18000c22b  jnz     short loc_18000C259
0x18000c22d  call    cs:__imp_GetLastError
0x18000c233  mov     edi, eax
0x18000c235  test    eax, eax
0x18000c237  jle     short loc_18000C23E
0x18000c239  movzx   edi, ax
0x18000c23c  or      edi, esi
0x18000c23e  test    edi, edi
0x18000c240  jns     short loc_18000C259
0x18000c242  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000c249  jb      loc_18000C621
0x18000c24f  mov     edx, 13h
0x18000c254  jmp     loc_18000C197
0x18000c259  xor     edx, edx; dwFlags
0x18000c25b  mov     [r14+78h], r12d
0x18000c25f  mov     ecx, 20070h; Version
0x18000c264  mov     [r14+158h], r13d
0x18000c26b  call    cs:__imp_MFStartup
0x18000c271  mov     edi, eax
0x18000c273  cmp     eax, 80004001h
0x18000c278  jnz     loc_18000C34A
0x18000c27e  xor     r8d, r8d; pcbe
0x18000c281  mov     qword ptr [rbp+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x18000c289  mov     rdx, r14; pv
0x18000c28c  lea     rcx, ?TimerCallback@FSMonitorService@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000c293  call    cs:__imp_CreateThreadpoolTimer
0x18000c299  mov     [r14+88h], rax
0x18000c2a0  test    rax, rax
0x18000c2a3  jnz     short loc_18000C2F4
0x18000c2a5  call    cs:__imp_GetLastError
0x18000c2ab  mov     edi, eax
0x18000c2ad  test    eax, eax
0x18000c2af  jle     short loc_18000C2B6
0x18000c2b1  movzx   edi, ax
0x18000c2b4  or      edi, esi
0x18000c2b6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000c2bd  jb      short loc_18000C2E2
0x18000c2bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c2c6  lea     r8, WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids
0x18000c2cd  mov     edx, 14h
0x18000c2d2  mov     [rsp+70h+dwDesiredAccess], edi
0x18000c2d6  mov     r9, r14
0x18000c2d9  mov     rcx, [rcx+10h]
0x18000c2dd  call    WPP_SF_qD
0x18000c2e2  mov     rcx, rbx; lpCriticalSection
0x18000c2e5  call    cs:__imp_LeaveCriticalSection
0x18000c2eb  test    edi, edi
0x18000c2ed  jns     short loc_18000C312
0x18000c2ef  jmp     loc_18000C62A
0x18000c2f4  xor     r9d, r9d; msWindowLength
0x18000c2f7  lea     rdx, [rbp+pftDueTime]; pftDueTime
0x18000c2fb  xor     r8d, r8d; msPeriod
0x18000c2fe  mov     rcx, rax; pti
0x18000c301  call    cs:__imp_SetThreadpoolTimer
0x18000c307  xor     edi, edi
0x18000c309  mov     rcx, rbx; lpCriticalSection
0x18000c30c  call    cs:__imp_LeaveCriticalSection
0x18000c312  cmp     cs:byte_18005E5A5, 8
0x18000c319  jb      loc_18000C661
0x18000c31f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c326  lea     r8, WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids
0x18000c32d  mov     edx, 21h ; '!'
0x18000c332  mov     [rsp+70h+dwDesiredAccess], edi
0x18000c336  mov     r9, r14
0x18000c339  mov     rcx, [rcx+0D8h]
0x18000c340  call    WPP_SF_qD
0x18000c345  jmp     loc_18000C661
0x18000c34a  test    eax, eax
0x18000c34c  jns     short loc_18000C369
0x18000c34e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000c355  jb      loc_18000C621
0x18000c35b  mov     edx, 15h
0x18000c360  mov     [rsp+70h+dwDesiredAccess], eax
0x18000c364  jmp     loc_18000C19B
0x18000c369  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000c370  mov     byte ptr [r14+58h], 1
0x18000c375  test    rsi, rsi
0x18000c378  jnz     short loc_18000C38B
0x18000c37a  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18000c37f  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000c386  test    rsi, rsi
0x18000c389  jz      short loc_18000C3A3
0x18000c38b  lea     rcx, [rsi+10h]; lpCriticalSection
0x18000c38f  call    cs:__imp_EnterCriticalSection
0x18000c395  lea     rcx, [rsi+10h]; lpCriticalSection
0x18000c399  mov     byte ptr [rsi+8], 0
0x18000c39d  call    cs:__imp_LeaveCriticalSection
0x18000c3a3  lea     rcx, [rbp+SystemInfo]; lpSystemInfo
0x18000c3a7  call    cs:__imp_GetSystemInfo
0x18000c3ad  mov     ecx, [rbp+SystemInfo.dwPageSize]
0x18000c3b0  lea     eax, [rcx-1]
0x18000c3b3  test    ecx, eax
0x18000c3b5  jz      short loc_18000C3D3
0x18000c3b7  mov     edi, 8000FFFFh
0x18000c3bc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000c3c3  jb      loc_18000C621
0x18000c3c9  mov     edx, 16h
0x18000c3ce  jmp     loc_18000C197
0x18000c3d3  call    cs:__imp_MFSetMinimumMemoryAlignment
0x18000c3d9  mov     edi, eax
0x18000c3db  test    eax, eax
0x18000c3dd  jns     short loc_18000C3F6
0x18000c3df  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000c3e6  jb      loc_18000C621
0x18000c3ec  mov     edx, 17h
0x18000c3f1  jmp     loc_18000C360
0x18000c3f6  mov     r8d, 0FFFFFFFEh; lPriority
0x18000c3fc  lea     rdx, [rbp+pdwTaskId]; pdwTaskId
0x18000c400  lea     rcx, wszClass; "Audio"
0x18000c407  call    cs:__imp_MFRegisterPlatformWithMMCSS
0x18000c40d  test    eax, eax
0x18000c40f  js      short loc_18000C41D
0x18000c411  mov     eax, [rbp+pdwTaskId]
0x18000c414  mov     [r14+68h], eax
0x18000c418  mov     byte ptr [r14+59h], 1
0x18000c41d  xor     r8d, r8d; pState
0x18000c420  lea     rdx, [r14+10h]; pCallback
0x18000c424  lea     ecx, [r8+5]; dwQueue
0x18000c428  call    cs:__imp_MFPutWorkItem
0x18000c42e  mov     edi, eax
0x18000c430  test    eax, eax
0x18000c432  jns     short loc_18000C44B
0x18000c434  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000c43b  jb      loc_18000C621
0x18000c441  mov     edx, 18h
0x18000c446  jmp     loc_18000C360
0x18000c44b  xor     r15d, r15d
0x18000c44e  movsxd  r13, r15d
0x18000c451  mov     rsi, r13
0x18000c454  mov     qword ptr [rbp+pftDueTime.dwLowDateTime], 0
0x18000c45c  shl     rsi, 4
0x18000c460  lea     r12, [r14+rsi]
0x18000c464  lea     rcx, [r12+0B0h]
0x18000c46c  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000c471  mov     edi, eax
0x18000c473  test    eax, eax
0x18000c475  js      loc_18000C5EC
0x18000c47b  add     rsi, r14
0x18000c47e  lea     rdi, funcs_18000C4A9
0x18000c485  mov     rdi, ds:(funcs_18000C4A9 - 18004E230h)[rdi+r13*8]
0x18000c489  lea     rcx, [rsi+0A8h]
0x18000c490  call    ?reset@?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(void)
0x18000c495  lea     r8, [rsi+0A8h]; void **
0x18000c49c  mov     rcx, r14; struct IFSMService *
0x18000c49f  lea     rdx, _GUID_d97fb26a_db7e_414f_8776_cec04d293a0f; struct _GUID *
0x18000c4a6  mov     rax, rdi
0x18000c4a9  call    _guard_dispatch_icall$thunk$10345483385596137414; FSMDeviceWatcher::CreateFSMDeviceWatcher(IFSMService *,_GUID const &,void * *)
0x18000c4ae  mov     edi, eax
0x18000c4b0  test    eax, eax
0x18000c4b2  js      loc_18000C5DC
0x18000c4b8  mov     rcx, [rsi+0A8h]
0x18000c4bf  lea     rdx, [r13+0Bh]
0x18000c4c3  add     rdx, rdx
0x18000c4c6  mov     rax, [rcx]
0x18000c4c9  mov     rdx, [r14+rdx*8]
0x18000c4cd  mov     rax, [rax+18h]
0x18000c4d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c4d6  mov     edi, eax
0x18000c4d8  test    eax, eax
0x18000c4da  js      loc_18000C5BB
0x18000c4e0  mov     rsi, [rsi+0A8h]
0x18000c4e7  lea     rcx, [rbp+pftDueTime]
0x18000c4eb  mov     rax, [rsi]
0x18000c4ee  mov     rdi, [rax]
0x18000c4f1  call    ?reset@?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(void)
0x18000c4f6  lea     r8, [rbp+pftDueTime]
0x18000c4fa  mov     rcx, rsi
0x18000c4fd  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18000c504  mov     rax, rdi
0x18000c507  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c50c  mov     edi, eax
0x18000c50e  test    eax, eax
0x18000c510  js      loc_18000C5AB
0x18000c516  mov     r8, qword ptr [rbp+pftDueTime.dwLowDateTime]; pState
0x18000c51a  lea     rdx, [r14+8]; pCallback
0x18000c51e  mov     ecx, 5; dwQueue
0x18000c523  call    cs:__imp_MFPutWorkItem
0x18000c529  mov     edi, eax
0x18000c52b  test    eax, eax
0x18000c52d  js      short loc_18000C59B
0x18000c52f  lea     rcx, [rbp+pftDueTime]
0x18000c533  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x18000c538  inc     r15d
0x18000c53b  cmp     r15d, 2
0x18000c53f  jl      loc_18000C44E
0x18000c545  mov     rcx, r14; this
0x18000c548  call    ?InternalRegisterRpcEndpoint@FSMonitorService@@IEAAJPEBG@Z; FSMonitorService::InternalRegisterRpcEndpoint(ushort const *)
0x18000c54d  mov     edi, eax
0x18000c54f  test    eax, eax
0x18000c551  jns     short loc_18000C56A
0x18000c553  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000c55a  jb      loc_18000C621
0x18000c560  mov     edx, 1Eh
0x18000c565  jmp     loc_18000C360
0x18000c56a  mov     rcx, r14; this
0x18000c56d  mov     dword ptr [r14+5Ch], 1
0x18000c575  call    ?InternalStartIdleTimer@FSMonitorService@@IEAAJXZ; FSMonitorService::InternalStartIdleTimer(void)
0x18000c57a  mov     edi, eax
0x18000c57c  test    eax, eax
0x18000c57e  jns     loc_18000C309
0x18000c584  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000c58b  jb      loc_18000C621
0x18000c591  mov     edx, 1Fh
0x18000c596  jmp     loc_18000C360
0x18000c59b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000c5a2  jb      short loc_18000C618
0x18000c5a4  mov     edx, 1Dh
0x18000c5a9  jmp     short loc_18000C5FA
0x18000c5ab  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000c5b2  jb      short loc_18000C618
0x18000c5b4  mov     edx, 1Ch
0x18000c5b9  jmp     short loc_18000C5FA
0x18000c5bb  lea     rcx, [r12+0B0h]
0x18000c5c3  call    ??4?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@QEAAAEAV01@$$T@Z
0x18000c5c8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000c5cf  jb      short loc_18000C618
0x18000c5d1  mov     edx, 1Bh
0x18000c5d6  mov     [rsp+70h+dwDesiredAccess], edi
0x18000c5da  jmp     short loc_18000C5FE
0x18000c5dc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000c5e3  jb      short loc_18000C618
0x18000c5e5  mov     edx, 1Ah
0x18000c5ea  jmp     short loc_18000C5FA
0x18000c5ec  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000c5f3  jb      short loc_18000C618
0x18000c5f5  mov     edx, 19h
0x18000c5fa  mov     [rsp+70h+dwDesiredAccess], eax
0x18000c5fe  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c605  lea     r8, WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids
0x18000c60c  mov     r9, r14
0x18000c60f  mov     rcx, [rcx+10h]
  ... truncated ...
```
