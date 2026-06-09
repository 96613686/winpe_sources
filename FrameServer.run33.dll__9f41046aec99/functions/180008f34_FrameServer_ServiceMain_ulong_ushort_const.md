# FrameServer::ServiceMain(ulong,ushort * * const)

- ea: `0x180008f34`
- end: `0x180009205`
- name: `?ServiceMain@FrameServer@@QEAAXKQEAPEAG@Z`
- size: `721`
- prototype: `void(FrameServer *__hidden this, unsigned int, unsigned __int16 **const)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180008940`

## callees

- `0x180008dbc`
- `0x180008e14`
- `0x180008ebc`
- `0x180008f34`
- `0x18000923c`
- `0x18000943c`
- `0x180009608`
- `0x180009658`
- `0x1800096f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800091fe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008f4b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008f4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ff0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009042`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ff0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009042`
- `api-ms-win-core-processthreads-l1-1-0!GetPriorityClass` at `0x180009096`
- `api-ms-win-core-processthreads-l1-1-0!GetPriorityClass` at `0x180009096`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x180009085`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x180009085`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180009021`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000907c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180009021`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000907c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18000902f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18000902f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180008fca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000908d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180008fca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000908d`
- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x180008fd8`
- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x180008fd8`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180009108`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180009108`

## pseudocode

```c
void __fastcall FrameServer::ServiceMain(FrameServer *this, unsigned int a2, unsigned __int16 **const a3)
{
  __int64 i; // rbx
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  HANDLE CurrentThread; // rax
  signed int v9; // eax
  HANDLE v10; // rax
  int ThreadPriority; // ebx
  HANDLE v12; // rax
  DWORD PriorityClass; // eax
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  unsigned int v15; // ebx
  __int64 v16; // rdx
  FrameServer *v17; // rcx
  FrameServer *v18; // rcx
  __int64 v19; // rdx

  EnterCriticalSection(&CriticalSection);
  if ( (unsigned __int8)byte_18010EC4D >= 0x10u )
  {
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), 12, &WPP_13b2db43ff0d357d0cad994035e5160e_Traceguids, &g_Server, a2);
    for ( i = 0; (unsigned int)i < a2; i = (unsigned int)(i + 1) )
    {
      if ( (unsigned __int8)byte_18010EC4D >= 8u )
        WPP_SF_qDS(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          13,
          (unsigned int)&WPP_13b2db43ff0d357d0cad994035e5160e_Traceguids,
          (unsigned int)&g_Server,
          i,
          (__int64)a3[i]);
    }
  }
  CurrentProcess = GetCurrentProcess();
  if ( !SetPriorityClass(CurrentProcess, 0x80u) && byte_18010EC4D )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      14,
      &WPP_13b2db43ff0d357d0cad994035e5160e_Traceguids,
      &g_Server,
      LastError);
  }
  CurrentThread = GetCurrentThread();
  if ( !SetThreadPriority(CurrentThread, 2) && byte_18010EC4D )
  {
    v9 = GetLastError();
    if ( v9 > 0 )
      v9 = (unsigned __int16)v9 | 0x80070000;
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), 15, &WPP_13b2db43ff0d357d0cad994035e5160e_Traceguids, &g_Server, v9);
  }
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v10 = GetCurrentThread();
    ThreadPriority = GetThreadPriority(v10);
    v12 = GetCurrentProcess();
    PriorityClass = GetPriorityClass(v12);
    WPP_SF_qDD(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      16,
      &WPP_13b2db43ff0d357d0cad994035e5160e_Traceguids,
      &g_Server,
      PriorityClass,
      ThreadPriority);
  }
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(&qword_18010E328, 0);
  v15 = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_29;
    v16 = 17;
    goto LABEL_28;
  }
  LODWORD(xmmword_18010E308) = 32;
  qword_18010E300 = (__int64)RegisterServiceCtrlHandlerExW(L"FrameServer", FrameServer::s_ServiceHandler, &g_Server);
  if ( qword_18010E300 )
  {
    FrameServer::ReportSvcStatus((FrameServer *)&g_Server, 2u, 0, 0x1388u);
    event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = FrameServer::SvcInitialize(v17, a2, a3);
    v15 = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
    if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_29;
      v16 = 18;
      goto LABEL_28;
    }
    FrameServer::ReportSvcStatus((FrameServer *)&g_Server, 4u, 0, 0);
    event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = FrameServer::RegisterStopCallback(v18);
    v15 = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
    if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_29;
      v16 = 19;
LABEL_28:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v16,
        &WPP_13b2db43ff0d357d0cad994035e5160e_Traceguids,
        &g_Server,
        event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z);
LABEL_29:
      FrameServer::Cleanup((FrameServer *)&g_Server);
      FrameServer::ReportSvcStatus((FrameServer *)&g_Server, 1u, v15, 0);
      if ( byte_18010EC4D )
      {
        v19 = 20;
LABEL_33:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          v19,
          &WPP_13b2db43ff0d357d0cad994035e5160e_Traceguids,
          &g_Server,
          v15);
        goto LABEL_34;
      }
      goto LABEL_34;
    }
  }
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v19 = 21;
    goto LABEL_33;
  }
LABEL_34:
  LeaveCriticalSection(&CriticalSection);
}

```

## disassembly

```asm
0x180008f34  push    rbx
0x180008f36  push    rbp
0x180008f37  push    rsi
0x180008f38  push    rdi
0x180008f39  push    r15
0x180008f3b  sub     rsp, 30h
0x180008f3f  lea     rcx, CriticalSection; lpCriticalSection
0x180008f46  mov     rsi, r8
0x180008f49  mov     edi, edx
0x180008f4b  call    cs:__imp_EnterCriticalSection
0x180008f51  cmp     cs:byte_18010EC4D, 10h
0x180008f58  lea     rbp, ?g_Server@@3VFrameServer@@A; FrameServer g_Server
0x180008f5f  lea     r15, WPP_13b2db43ff0d357d0cad994035e5160e_Traceguids
0x180008f66  jb      short loc_180008FCA
0x180008f68  mov     rcx, cs:WPP_GLOBAL_Control
0x180008f6f  mov     edx, 0Ch
0x180008f74  mov     r9, rbp
0x180008f77  mov     [rsp+58h+var_38], edi
0x180008f7b  mov     r8, r15
0x180008f7e  mov     rcx, [rcx+0D8h]
0x180008f85  call    WPP_SF_qD
0x180008f8a  xor     ebx, ebx
0x180008f8c  test    edi, edi
0x180008f8e  jz      short loc_180008FCA
0x180008f90  cmp     cs:byte_18010EC4D, 8
0x180008f97  jb      short loc_180008FC4
0x180008f99  mov     rcx, cs:WPP_GLOBAL_Control
0x180008fa0  mov     edx, 0Dh
0x180008fa5  mov     rax, [rsi+rbx*8]
0x180008fa9  mov     r9, rbp
0x180008fac  mov     [rsp+58h+var_30], rax
0x180008fb1  mov     r8, r15
0x180008fb4  mov     [rsp+58h+var_38], ebx
0x180008fb8  mov     rcx, [rcx+0D8h]
0x180008fbf  call    WPP_SF_qDS
0x180008fc4  inc     ebx
0x180008fc6  cmp     ebx, edi
0x180008fc8  jb      short loc_180008F90
0x180008fca  call    cs:__imp_GetCurrentProcess
0x180008fd0  mov     rcx, rax; hProcess
0x180008fd3  mov     edx, 80h; dwPriorityClass
0x180008fd8  call    cs:__imp_SetPriorityClass
0x180008fde  mov     ebx, 80070000h
0x180008fe3  test    eax, eax
0x180008fe5  jnz     short loc_180009021
0x180008fe7  cmp     cs:byte_18010EC4D, 1
0x180008fee  jb      short loc_180009021
0x180008ff0  call    cs:__imp_GetLastError
0x180008ff6  test    eax, eax
0x180008ff8  jle     short loc_180008FFF
0x180008ffa  movzx   eax, ax
0x180008ffd  or      eax, ebx
0x180008fff  mov     rcx, cs:WPP_GLOBAL_Control
0x180009006  mov     edx, 0Eh
0x18000900b  mov     r9, rbp
0x18000900e  mov     [rsp+58h+var_38], eax
0x180009012  mov     r8, r15
0x180009015  mov     rcx, [rcx+0D8h]
0x18000901c  call    WPP_SF_qD
0x180009021  call    cs:__imp_GetCurrentThread
0x180009027  mov     rcx, rax; hThread
0x18000902a  mov     edx, 2; nPriority
0x18000902f  call    cs:__imp_SetThreadPriority
0x180009035  test    eax, eax
0x180009037  jnz     short loc_180009073
0x180009039  cmp     cs:byte_18010EC4D, 1
0x180009040  jb      short loc_180009073
0x180009042  call    cs:__imp_GetLastError
0x180009048  test    eax, eax
0x18000904a  jle     short loc_180009051
0x18000904c  movzx   eax, ax
0x18000904f  or      eax, ebx
0x180009051  mov     rcx, cs:WPP_GLOBAL_Control
0x180009058  mov     edx, 0Fh
0x18000905d  mov     r9, rbp
0x180009060  mov     [rsp+58h+var_38], eax
0x180009064  mov     r8, r15
0x180009067  mov     rcx, [rcx+0D8h]
0x18000906e  call    WPP_SF_qD
0x180009073  cmp     cs:byte_18010EC4D, 8
0x18000907a  jb      short loc_1800090C2
0x18000907c  call    cs:__imp_GetCurrentThread
0x180009082  mov     rcx, rax; hThread
0x180009085  call    cs:__imp_GetThreadPriority
0x18000908b  mov     ebx, eax
0x18000908d  call    cs:__imp_GetCurrentProcess
0x180009093  mov     rcx, rax; hProcess
0x180009096  call    cs:__imp_GetPriorityClass
0x18000909c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800090a3  mov     edx, 10h
0x1800090a8  mov     dword ptr [rsp+58h+var_30], ebx
0x1800090ac  mov     r9, rbp
0x1800090af  mov     r8, r15
0x1800090b2  mov     [rsp+58h+var_38], eax
0x1800090b6  mov     rcx, [rcx+0D8h]
0x1800090bd  call    WPP_SF_qDD
0x1800090c2  xor     edx, edx
0x1800090c4  lea     rcx, qword_18010E328
0x1800090cb  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1800090d0  mov     ebx, eax
0x1800090d2  test    eax, eax
0x1800090d4  jns     short loc_1800090ED
0x1800090d6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800090dd  jb      loc_180009198
0x1800090e3  mov     edx, 11h
0x1800090e8  jmp     loc_18000917E
0x1800090ed  mov     r8, rbp; lpContext
0x1800090f0  mov     dword ptr cs:xmmword_18010E308, 20h ; ' '
0x1800090fa  lea     rdx, ?s_ServiceHandler@FrameServer@@KAKKKPEAX0@Z; lpHandlerProc
0x180009101  lea     rcx, ServiceName; "FrameServer"
0x180009108  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18000910e  mov     cs:qword_18010E300, rax
0x180009115  test    rax, rax
0x180009118  jz      loc_1800091C2
0x18000911e  xor     r8d, r8d; unsigned int
0x180009121  mov     r9d, 1388h; unsigned int
0x180009127  mov     rcx, rbp; this
0x18000912a  lea     edx, [r8+2]; unsigned int
0x18000912e  call    ?ReportSvcStatus@FrameServer@@IEAAXKKK@Z; FrameServer::ReportSvcStatus(ulong,ulong,ulong)
0x180009133  mov     r8, rsi; unsigned __int16 **
0x180009136  mov     edx, edi; unsigned int
0x180009138  call    ?SvcInitialize@FrameServer@@IEAAJKQEAPEAG@Z; FrameServer::SvcInitialize(ulong,ushort * * const)
0x18000913d  mov     ebx, eax
0x18000913f  test    eax, eax
0x180009141  jns     short loc_180009153
0x180009143  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000914a  jb      short loc_180009198
0x18000914c  mov     edx, 12h
0x180009151  jmp     short loc_18000917E
0x180009153  xor     r9d, r9d; unsigned int
0x180009156  xor     r8d, r8d; unsigned int
0x180009159  mov     rcx, rbp; this
0x18000915c  lea     edx, [r9+4]; unsigned int
0x180009160  call    ?ReportSvcStatus@FrameServer@@IEAAXKKK@Z; FrameServer::ReportSvcStatus(ulong,ulong,ulong)
0x180009165  call    ?RegisterStopCallback@FrameServer@@IEAAJXZ; FrameServer::RegisterStopCallback(void)
0x18000916a  mov     ebx, eax
0x18000916c  test    eax, eax
0x18000916e  jns     short loc_1800091C2
0x180009170  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180009177  jb      short loc_180009198
0x180009179  mov     edx, 13h
0x18000917e  mov     rcx, cs:WPP_GLOBAL_Control
0x180009185  mov     r9, rbp
0x180009188  mov     r8, r15
0x18000918b  mov     [rsp+58h+var_38], eax
0x18000918f  mov     rcx, [rcx+10h]
0x180009193  call    WPP_SF_qD
0x180009198  mov     rcx, rbp; this
0x18000919b  call    ?Cleanup@FrameServer@@IEAAXXZ; FrameServer::Cleanup(void)
0x1800091a0  xor     r9d, r9d; unsigned int
0x1800091a3  mov     r8d, ebx; unsigned int
0x1800091a6  mov     rcx, rbp; this
0x1800091a9  lea     edx, [r9+1]; unsigned int
0x1800091ad  call    ?ReportSvcStatus@FrameServer@@IEAAXKKK@Z; FrameServer::ReportSvcStatus(ulong,ulong,ulong)
0x1800091b2  cmp     cs:byte_18010EC4D, 1
0x1800091b9  jb      short loc_1800091ED
0x1800091bb  mov     edx, 14h
0x1800091c0  jmp     short loc_1800091D0
0x1800091c2  cmp     cs:byte_18010EC4D, 8
0x1800091c9  jb      short loc_1800091ED
0x1800091cb  mov     edx, 15h
0x1800091d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800091d7  mov     r9, rbp
0x1800091da  mov     r8, r15
0x1800091dd  mov     [rsp+58h+var_38], ebx
0x1800091e1  mov     rcx, [rcx+0D8h]
0x1800091e8  call    WPP_SF_qD
0x1800091ed  lea     rcx, CriticalSection
0x1800091f4  add     rsp, 30h
0x1800091f8  pop     r15
0x1800091fa  pop     rdi
0x1800091fb  pop     rsi
0x1800091fc  pop     rbp
0x1800091fd  pop     rbx
0x1800091fe  jmp     cs:__imp_LeaveCriticalSection
```
