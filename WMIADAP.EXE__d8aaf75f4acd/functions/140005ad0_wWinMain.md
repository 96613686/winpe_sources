# wWinMain

- ea: `0x140005ad0`
- end: `0x14000607b`
- name: `wWinMain`
- size: `1451`
- prototype: `int __stdcall(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400012a0`

## callees

- `0x140001a6f`
- `0x140001c28`
- `0x140004c84`
- `0x140004d50`
- `0x140004d74`
- `0x140004e24`
- `0x140004f7c`
- `0x140005140`
- `0x140005498`
- `0x140005810`
- `0x140005968`
- `0x140005a48`
- `0x140005ad0`
- `0x140006bb4`
- `0x140014ad0`

## import_xrefs

- `msvcrt!towupper` at `0x140005f4e`
- `msvcrt!towupper` at `0x140005f65`
- `msvcrt!towupper` at `0x140005f7c`
- `msvcrt!towupper` at `0x140005f93`
- `msvcrt!towupper` at `0x140005fa2`
- `msvcrt!towupper` at `0x140005f4e`
- `msvcrt!towupper` at `0x140005f65`
- `msvcrt!towupper` at `0x140005f7c`
- `msvcrt!towupper` at `0x140005f93`
- `msvcrt!towupper` at `0x140005fa2`
- `msvcrt!iswspace` at `0x140005f20`
- `msvcrt!iswspace` at `0x140005fad`
- `msvcrt!iswspace` at `0x140005f20`
- `msvcrt!iswspace` at `0x140005fad`
- `wbemcomn!?anyFailure@CStaticCritSec@@SAHXZ` at `0x140005b12`
- `wbemcomn!?anyFailure@CStaticCritSec@@SAHXZ` at `0x140005b12`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140005c3b`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140005c3b`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x140005c6f`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x140005c6f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140005c7b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140005ec5`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000603e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140005c7b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140005ec5`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000603e`
- `api-ms-win-core-console-l1-1-0!SetConsoleCtrlHandler` at `0x140005ba0`
- `api-ms-win-core-console-l1-1-0!SetConsoleCtrlHandler` at `0x140005ba0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140005dba`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140005eeb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140005dba`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140005eeb`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140005d1d`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140005d1d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140005ff2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140005ff2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140005bb0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140005bb0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x140005e35`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x140005e35`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x140005dd6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x140005e9b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x14000600a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x140005dd6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x140005e9b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x14000600a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005bd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005d4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005d56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005d82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005e66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005bd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005d4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005d56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005d82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005e66`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x140005c31`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x140005c31`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140005eaa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140005ebe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140006023`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140006037`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140005eaa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140005ebe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140006023`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140006037`
- `api-ms-win-core-heap-l1-1-0!HeapSetInformation` at `0x140005b0c`
- `api-ms-win-core-heap-l1-1-0!HeapSetInformation` at `0x140005b0c`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x140005c04`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x140005c04`

## pseudocode

```c
int __stdcall wWinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)
{
  int v5; // r12d
  ShutdownControlHandler *v6; // rcx
  signed int LastError; // eax
  HRESULT v8; // edi
  unsigned int ExecPid; // esi
  void *SD; // rdi
  HANDLE v11; // r14
  DWORD v12; // eax
  __int64 v13; // rdx
  void *v14; // r15
  HANDLE v15; // rax
  void *v16; // rsi
  DWORD v17; // eax
  DWORD v19; // eax
  unsigned int v20; // r13d
  int v21; // r15d
  wint_t v22; // ax
  _BYTE v23[4]; // [rsp+50h] [rbp-B0h] BYREF
  int PreviousCount; // [rsp+54h] [rbp-ACh] BYREF
  _SECURITY_ATTRIBUTES SemaphoreAttributes; // [rsp+58h] [rbp-A8h] BYREF
  int v26; // [rsp+70h] [rbp-90h] BYREF
  int v27; // [rsp+74h] [rbp-8Ch] BYREF
  void *v28; // [rsp+78h] [rbp-88h]
  HANDLE v29; // [rsp+80h] [rbp-80h] BYREF
  void *v30; // [rsp+88h] [rbp-78h]
  HANDLE v31[2]; // [rsp+90h] [rbp-70h] BYREF
  struct _OSVERSIONINFOW VersionInformation; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR Name[260]; // [rsp+1C0h] [rbp+C0h] BYREF

  HeapSetInformation(0, HeapEnableTerminationOnCorruption, 0, 0);
  v5 = 0;
  if ( !(unsigned int)CStaticCritSec::anyFailure() )
  {
    qword_140024F30 = 0;
    WPP_MAIN_CB = (__int64)&qword_140024F48;
    qword_140024F38 = 1;
    qword_140024F58 = 0;
    qword_140024F48 = 0;
    qword_140024F60 = 1;
    WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_WMI_Tracing_Guid;
    qword_140024F78 = (__int64)WPP_ThisDir_CTLGUID_WMI_Tracing_Client_Operations_Info_Guid;
    WPP_GLOBAL_Control = &WPP_MAIN_CB;
    WppInitUm();
    if ( (unsigned __int8)IsCreateWindowExWPresent() )
    {
      SetConsoleCtrlHandler(ShutdownControlHandler::ConsoleControlHandlerRoutine, 1);
      ShutdownControlHandler::mg_hReadyEvent = CreateEventW(0, 0, 0, 0);
      if ( ShutdownControlHandler::mg_hReadyEvent )
      {
        ShutdownControlHandler::mg_hrInit = 0;
        ShutdownControlHandler::CreateHiddenMsgWnd(v6);
      }
      else
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        ShutdownControlHandler::mg_hrInit = LastError;
      }
    }
    memset_0(&VersionInformation.dwMajorVersion, 0, 0x110u);
    VersionInformation.dwOSVersionInfoSize = 276;
    if ( GetVersionExW(&VersionInformation)
      && VersionInformation.dwPlatformId == 2
      && VersionInformation.dwMajorVersion >= 5 )
    {
      SetErrorMode(0x8003u);
      v8 = CoInitializeEx(0, 0);
      if ( v8 < 0 )
      {
LABEL_42:
        ShutdownControlHandler::~ShutdownControlHandler((ShutdownControlHandler *)v23);
        return v8;
      }
      v8 = CoInitializeSecurity(0, -1, 0, 0, 0, 2u, 0, 2u, 0);
      if ( v8 < 0 )
      {
        CoUninitialize();
        goto LABEL_42;
      }
      ExecPid = GetExecPid();
      PreviousCount = 0;
      SD = CreateSD(0x1F0003u, (unsigned int *)&PreviousCount);
      v30 = SD;
      *(&SemaphoreAttributes.nLength + 1) = 0;
      *(&SemaphoreAttributes.bInheritHandle + 1) = 0;
      if ( SD )
      {
        SemaphoreAttributes.nLength = PreviousCount;
        SemaphoreAttributes.lpSecurityDescriptor = SD;
      }
      else
      {
        SemaphoreAttributes.nLength = 128;
        SemaphoreAttributes.lpSecurityDescriptor = &g_PreCompSD;
      }
      SemaphoreAttributes.bInheritHandle = 0;
      StringCchPrintfW(Name, 0x100u, L"Global\\WMI_SysEvent_Semaphore_%d", ExecPid);
      v11 = CreateSemaphoreExW(&SemaphoreAttributes, 2, 2, Name, 0, 0x1F0003u);
      if ( !v11 )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
        {
          goto LABEL_28;
        }
        v12 = GetLastError();
        v13 = 11;
LABEL_27:
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, &WPP_5be32fbe0360308afd691b549c1e060e_Traceguids, v12);
LABEL_28:
        WppCleanupUm();
LABEL_41:
        LocalFree(SD);
        CoUninitialize();
        v8 = 0;
        goto LABEL_42;
      }
      if ( GetLastError() == 183 )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
        {
          goto LABEL_28;
        }
        v12 = GetLastError();
        v13 = 12;
        goto LABEL_27;
      }
      v29 = v11;
      if ( WaitForSingleObject(v11, 0) )
      {
        PreviousCount = 0;
        ReleaseSemaphore(v11, 1, &PreviousCount);
        WppCleanupUm();
LABEL_40:
        CCloseMe::~CCloseMe((CCloseMe *)&v29);
        goto LABEL_41;
      }
      v14 = CreateSD(0x1F0001u, (unsigned int *)&PreviousCount);
      v28 = v14;
      if ( v14 )
      {
        SemaphoreAttributes.nLength = PreviousCount;
        SemaphoreAttributes.lpSecurityDescriptor = SD;
      }
      else
      {
        SemaphoreAttributes.nLength = 128;
        SemaphoreAttributes.lpSecurityDescriptor = &g_PreCompSD;
      }
      SemaphoreAttributes.bInheritHandle = 0;
      v15 = CreateMutexW(&SemaphoreAttributes, 0, L"Global\\ADAP_WMI_ENTRY");
      v16 = v15;
      if ( !v15 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          v17 = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_5be32fbe0360308afd691b549c1e060e_Traceguids, v17);
        }
        v26 = 0;
        ReleaseSemaphore(v11, 1, &v26);
        WppCleanupUm();
        LocalFree(v14);
        goto LABEL_40;
      }
      v31[0] = v15;
      v19 = WaitForSingleObject(v15, 0x61A80u);
      if ( !v19 || v19 == 128 )
      {
        if ( lpCmdLine )
        {
          v20 = 0;
          v21 = 0;
          if ( *lpCmdLine )
          {
            do
            {
              v22 = *lpCmdLine;
              do
              {
                if ( !iswspace(v22) )
                  break;
                v22 = *++lpCmdLine;
              }
              while ( *lpCmdLine );
              if ( ((*lpCmdLine - 45) & 0xFFFD) == 0 )
              {
                if ( towupper(*++lpCmdLine) == 84 )
                {
                  v20 = 1;
                }
                else if ( towupper(*lpCmdLine) == 82 )
                {
                  v5 = 1;
                }
                else if ( towupper(*lpCmdLine) == 70 )
                {
                  v21 = 1;
                }
                else if ( towupper(*lpCmdLine) != 68 )
                {
                  towupper(*lpCmdLine);
                }
              }
              while ( *lpCmdLine && !iswspace(*lpCmdLine) )
                ++lpCmdLine;
            }
            while ( *lpCmdLine );
            SD = v30;
            if ( v21 )
              CheckAndUpdateWMI();
            if ( v5 )
              DoReverseAdapterMaintenanceInternal(v20);
          }
          v14 = v28;
        }
        ReleaseMutex(v16);
      }
      v27 = 0;
      ReleaseSemaphore(v11, 1, &v27);
      WppCleanupUm();
      CCloseMe::~CCloseMe((CCloseMe *)v31);
      LocalFree(v14);
      CCloseMe::~CCloseMe((CCloseMe *)&v29);
      LocalFree(SD);
      CoUninitialize();
    }
    else
    {
      WppCleanupUm();
    }
    ShutdownControlHandler::~ShutdownControlHandler((ShutdownControlHandler *)v23);
  }
  return 0;
}

```

## disassembly

```asm
0x140005ad0  push    rbp
0x140005ad2  push    rbx
0x140005ad3  push    rsi
0x140005ad4  push    rdi
0x140005ad5  push    r12
0x140005ad7  push    r13
0x140005ad9  push    r14
0x140005adb  push    r15
0x140005add  lea     rbp, [rsp-2D8h]
0x140005ae5  sub     rsp, 3D8h
0x140005aec  mov     rax, cs:__security_cookie
0x140005af3  xor     rax, rsp
0x140005af6  mov     [rbp+310h+var_48], rax
0x140005afd  mov     rbx, r8
0x140005b00  xor     r9d, r9d; HeapInformationLength
0x140005b03  xor     r8d, r8d; HeapInformation
0x140005b06  lea     edx, [r9+1]; HeapInformationClass
0x140005b0a  xor     ecx, ecx; HeapHandle
0x140005b0c  call    cs:__imp_HeapSetInformation
0x140005b12  call    cs:__imp_?anyFailure@CStaticCritSec@@SAHXZ; CStaticCritSec::anyFailure(void)
0x140005b18  xor     r12d, r12d
0x140005b1b  test    eax, eax
0x140005b1d  jnz     loc_140006056
0x140005b23  mov     cs:qword_140024F30, r12
0x140005b2a  lea     rax, qword_140024F48
0x140005b31  mov     cs:WPP_MAIN_CB, rax
0x140005b38  mov     cs:qword_140024F38, 1
0x140005b43  mov     cs:qword_140024F58, r12
0x140005b4a  mov     cs:qword_140024F48, r12
0x140005b51  mov     cs:qword_140024F60, 1
0x140005b5c  lea     rax, WPP_ThisDir_CTLGUID_WMI_Tracing_Guid
0x140005b63  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x140005b6a  lea     rax, WPP_ThisDir_CTLGUID_WMI_Tracing_Client_Operations_Info_Guid
0x140005b71  mov     cs:qword_140024F78, rax
0x140005b78  lea     rax, WPP_MAIN_CB
0x140005b7f  mov     cs:WPP_GLOBAL_Control, rax
0x140005b86  call    WppInitUm
0x140005b8b  call    IsCreateWindowExWPresent
0x140005b90  test    al, al
0x140005b92  jz      short loc_140005BE8
0x140005b94  lea     edx, [r12+1]; Add
0x140005b99  lea     rcx, ?ConsoleControlHandlerRoutine@ShutdownControlHandler@@CAHK@Z; HandlerRoutine
0x140005ba0  call    cs:__imp_SetConsoleCtrlHandler
0x140005ba6  xor     r9d, r9d; lpName
0x140005ba9  xor     r8d, r8d; bInitialState
0x140005bac  xor     edx, edx; bManualReset
0x140005bae  xor     ecx, ecx; lpEventAttributes
0x140005bb0  call    cs:__imp_CreateEventW
0x140005bb6  mov     cs:?mg_hReadyEvent@ShutdownControlHandler@@0PEAXEA, rax; void * ShutdownControlHandler::mg_hReadyEvent
0x140005bbd  test    rax, rax
0x140005bc0  jz      short loc_140005BD0
0x140005bc2  mov     cs:?mg_hrInit@ShutdownControlHandler@@0JA, r12d; long ShutdownControlHandler::mg_hrInit
0x140005bc9  call    ?CreateHiddenMsgWnd@ShutdownControlHandler@@AEAAXXZ; ShutdownControlHandler::CreateHiddenMsgWnd(void)
0x140005bce  jmp     short loc_140005BE8
0x140005bd0  call    cs:__imp_GetLastError
0x140005bd6  test    eax, eax
0x140005bd8  jle     short loc_140005BE2
0x140005bda  movzx   eax, ax
0x140005bdd  or      eax, 80070000h
0x140005be2  mov     cs:?mg_hrInit@ShutdownControlHandler@@0JA, eax; long ShutdownControlHandler::mg_hrInit
0x140005be8  xor     edx, edx; Val
0x140005bea  mov     r8d, 110h; Size
0x140005bf0  lea     rcx, [rbp+310h+VersionInformation.dwMajorVersion]; void *
0x140005bf4  call    memset_0
0x140005bf9  mov     [rbp+310h+VersionInformation.dwOSVersionInfoSize], 114h
0x140005c00  lea     rcx, [rbp+310h+VersionInformation]; lpVersionInformation
0x140005c04  call    cs:__imp_GetVersionExW
0x140005c0a  test    eax, eax
0x140005c0c  jz      loc_140006046
0x140005c12  mov     r14d, 2
0x140005c18  cmp     [rbp+310h+VersionInformation.dwPlatformId], r14d
0x140005c1c  jnz     loc_140006046
0x140005c22  cmp     [rbp+310h+VersionInformation.dwMajorVersion], 5
0x140005c26  jb      loc_140006046
0x140005c2c  mov     ecx, 8003h; uMode
0x140005c31  call    cs:__imp_SetErrorMode
0x140005c37  xor     edx, edx; dwCoInit
0x140005c39  xor     ecx, ecx; pvReserved
0x140005c3b  call    cs:__imp_CoInitializeEx
0x140005c41  mov     edi, eax
0x140005c43  test    eax, eax
0x140005c45  js      loc_140005ECE
0x140005c4b  mov     [rsp+410h+pReserved3], r12; pReserved3
0x140005c50  mov     [rsp+410h+dwCapabilities], r14d; dwCapabilities
0x140005c55  mov     [rsp+410h+pAuthList], r12; pAuthList
0x140005c5a  mov     [rsp+410h+dwImpLevel], r14d; dwImpLevel
0x140005c5f  mov     [rsp+410h+dwAuthnLevel], r12d; dwAuthnLevel
0x140005c64  xor     r9d, r9d; pReserved1
0x140005c67  xor     r8d, r8d; asAuthSvc
0x140005c6a  or      edx, 0FFFFFFFFh; cAuthSvc
0x140005c6d  xor     ecx, ecx; pSecDesc
0x140005c6f  call    cs:__imp_CoInitializeSecurity
0x140005c75  mov     edi, eax
0x140005c77  test    eax, eax
0x140005c79  jns     short loc_140005C86
0x140005c7b  call    cs:__imp_CoUninitialize
0x140005c81  jmp     loc_140005ECE
0x140005c86  call    ?GetExecPid@@YAKXZ; GetExecPid(void)
0x140005c8b  mov     esi, eax
0x140005c8d  mov     [rsp+410h+PreviousCount], r12d
0x140005c92  lea     rdx, [rsp+410h+PreviousCount]; unsigned int *
0x140005c97  mov     r15d, 1F0003h
0x140005c9d  mov     ecx, r15d; unsigned int
0x140005ca0  call    ?CreateSD@@YAPEAXKAEAK@Z; CreateSD(ulong,ulong &)
0x140005ca5  mov     rdi, rax
0x140005ca8  mov     [rbp+310h+var_388], rax
0x140005cac  mov     dword ptr [rsp+410h+SemaphoreAttributes+4], r12d
0x140005cb1  mov     dword ptr [rsp+410h+SemaphoreAttributes+14h], r12d
0x140005cb6  mov     r13d, 80h
0x140005cbc  lea     rax, ?g_PreCompSD@@3PAKA; ulong near * g_PreCompSD
0x140005cc3  test    rdi, rdi
0x140005cc6  jz      short loc_140005CD7
0x140005cc8  mov     ecx, [rsp+410h+PreviousCount]
0x140005ccc  mov     [rsp+410h+SemaphoreAttributes.nLength], ecx
0x140005cd0  mov     [rsp+410h+SemaphoreAttributes.lpSecurityDescriptor], rdi
0x140005cd5  jmp     short loc_140005CE1
0x140005cd7  mov     [rsp+410h+SemaphoreAttributes.nLength], r13d
0x140005cdc  mov     [rsp+410h+SemaphoreAttributes.lpSecurityDescriptor], rax
0x140005ce1  mov     [rsp+410h+SemaphoreAttributes.bInheritHandle], r12d
0x140005ce6  mov     r9d, esi
0x140005ce9  lea     r8, aGlobalWmiSysev; "Global\\WMI_SysEvent_Semaphore_%d"
0x140005cf0  mov     edx, 100h; unsigned __int64
0x140005cf5  lea     rcx, [rbp+310h+Name]; unsigned __int16 *
0x140005cfc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140005d01  mov     [rsp+410h+dwImpLevel], r15d; dwDesiredAccess
0x140005d06  mov     [rsp+410h+dwAuthnLevel], r12d; dwFlags
0x140005d0b  lea     r9, [rbp+310h+Name]; lpName
0x140005d12  mov     r8d, r14d; lMaximumCount
0x140005d15  mov     edx, r14d; lInitialCount
0x140005d18  lea     rcx, [rsp+410h+SemaphoreAttributes]; lpSemaphoreAttributes
0x140005d1d  call    cs:__imp_CreateSemaphoreExW
0x140005d23  mov     r14, rax
0x140005d26  test    rax, rax
0x140005d29  jnz     short loc_140005D56
0x140005d2b  lea     rax, WPP_GLOBAL_Control
0x140005d32  mov     rcx, cs:WPP_GLOBAL_Control
0x140005d39  cmp     rcx, rax
0x140005d3c  jz      short loc_140005DA7
0x140005d3e  test    byte ptr [rcx+1Ch], 1
0x140005d42  jz      short loc_140005DA7
0x140005d44  cmp     byte ptr [rcx+19h], 5
0x140005d48  jb      short loc_140005DA7
0x140005d4a  call    cs:__imp_GetLastError
0x140005d50  lea     edx, [r14+0Bh]
0x140005d54  jmp     short loc_140005D8D
0x140005d56  call    cs:__imp_GetLastError
0x140005d5c  cmp     eax, 0B7h
0x140005d61  jnz     short loc_140005DB1
0x140005d63  lea     rax, WPP_GLOBAL_Control
0x140005d6a  mov     rcx, cs:WPP_GLOBAL_Control
0x140005d71  cmp     rcx, rax
0x140005d74  jz      short loc_140005DA7
0x140005d76  test    byte ptr [rcx+1Ch], 1
0x140005d7a  jz      short loc_140005DA7
0x140005d7c  cmp     byte ptr [rcx+19h], 5
0x140005d80  jb      short loc_140005DA7
0x140005d82  call    cs:__imp_GetLastError
0x140005d88  mov     edx, 0Ch
0x140005d8d  mov     rcx, cs:WPP_GLOBAL_Control
0x140005d94  mov     r9d, eax
0x140005d97  lea     r8, WPP_5be32fbe0360308afd691b549c1e060e_Traceguids
0x140005d9e  mov     rcx, [rcx+10h]
0x140005da2  call    WPP_SF_d
0x140005da7  call    WppCleanupUm
0x140005dac  jmp     loc_140005EBB
0x140005db1  mov     [rbp+310h+var_390], r14
0x140005db5  xor     edx, edx; dwMilliseconds
0x140005db7  mov     rcx, r14; hHandle
0x140005dba  call    cs:__imp_WaitForSingleObject
0x140005dc0  test    eax, eax
0x140005dc2  jz      short loc_140005DE6
0x140005dc4  mov     [rsp+410h+PreviousCount], r12d
0x140005dc9  lea     r8, [rsp+410h+PreviousCount]; lpPreviousCount
0x140005dce  mov     edx, 1; lReleaseCount
0x140005dd3  mov     rcx, r14; hSemaphore
0x140005dd6  call    cs:__imp_ReleaseSemaphore
0x140005ddc  call    WppCleanupUm
0x140005de1  jmp     loc_140005EB1
0x140005de6  lea     rdx, [rsp+410h+PreviousCount]; unsigned int *
0x140005deb  mov     ecx, 1F0001h; unsigned int
0x140005df0  call    ?CreateSD@@YAPEAXKAEAK@Z; CreateSD(ulong,ulong &)
0x140005df5  mov     r15, rax
0x140005df8  mov     [rsp+410h+var_398], rax
0x140005dfd  test    rax, rax
0x140005e00  jz      short loc_140005E11
0x140005e02  mov     ecx, [rsp+410h+PreviousCount]
0x140005e06  mov     [rsp+410h+SemaphoreAttributes.nLength], ecx
0x140005e0a  mov     [rsp+410h+SemaphoreAttributes.lpSecurityDescriptor], rdi
0x140005e0f  jmp     short loc_140005E22
0x140005e11  mov     [rsp+410h+SemaphoreAttributes.nLength], r13d
0x140005e16  lea     rax, ?g_PreCompSD@@3PAKA; ulong near * g_PreCompSD
0x140005e1d  mov     [rsp+410h+SemaphoreAttributes.lpSecurityDescriptor], rax
0x140005e22  mov     [rsp+410h+SemaphoreAttributes.bInheritHandle], r12d
0x140005e27  lea     r8, Name; "Global\\ADAP_WMI_ENTRY"
0x140005e2e  xor     edx, edx; bInitialOwner
0x140005e30  lea     rcx, [rsp+410h+SemaphoreAttributes]; lpMutexAttributes
0x140005e35  call    cs:__imp_CreateMutexW
0x140005e3b  mov     rsi, rax
0x140005e3e  test    rax, rax
0x140005e41  jnz     loc_140005EDF
0x140005e47  lea     rax, WPP_GLOBAL_Control
0x140005e4e  mov     rcx, cs:WPP_GLOBAL_Control
0x140005e55  cmp     rcx, rax
0x140005e58  jz      short loc_140005E89
0x140005e5a  test    byte ptr [rcx+1Ch], 1
0x140005e5e  jz      short loc_140005E89
0x140005e60  cmp     byte ptr [rcx+19h], 5
0x140005e64  jb      short loc_140005E89
0x140005e66  call    cs:__imp_GetLastError
0x140005e6c  lea     edx, [rsi+0Dh]
0x140005e6f  mov     r9d, eax
0x140005e72  lea     r8, WPP_5be32fbe0360308afd691b549c1e060e_Traceguids
0x140005e79  mov     rcx, cs:WPP_GLOBAL_Control
0x140005e80  mov     rcx, [rcx+10h]
0x140005e84  call    WPP_SF_d
0x140005e89  mov     [rsp+410h+var_3A0], r12d
0x140005e8e  lea     r8, [rsp+410h+var_3A0]; lpPreviousCount
0x140005e93  mov     edx, 1; lReleaseCount
0x140005e98  mov     rcx, r14; hSemaphore
0x140005e9b  call    cs:__imp_ReleaseSemaphore
0x140005ea1  call    WppCleanupUm
0x140005ea6  nop
0x140005ea7  mov     rcx, r15; hMem
0x140005eaa  call    cs:__imp_LocalFree
0x140005eb0  nop
0x140005eb1  lea     rcx, [rbp+310h+var_390]; this
0x140005eb5  call    ??1CCloseMe@@QEAA@XZ; CCloseMe::~CCloseMe(void)
0x140005eba  nop
0x140005ebb  mov     rcx, rdi; hMem
0x140005ebe  call    cs:__imp_LocalFree
0x140005ec4  nop
0x140005ec5  call    cs:__imp_CoUninitialize
0x140005ecb  mov     edi, r12d
0x140005ece  lea     rcx, [rsp+410h+var_3C0]; this
0x140005ed3  call    ??1ShutdownControlHandler@@QEAA@XZ; ShutdownControlHandler::~ShutdownControlHandler(void)
0x140005ed8  mov     eax, edi
0x140005eda  jmp     loc_140006058
0x140005edf  mov     [rbp+310h+var_380], rsi
0x140005ee3  mov     edx, 61A80h; dwMilliseconds
0x140005ee8  mov     rcx, rsi; hHandle
0x140005eeb  call    cs:__imp_WaitForSingleObject
0x140005ef1  test    eax, eax
0x140005ef3  jz      short loc_140005EFE
0x140005ef5  cmp     eax, r13d
0x140005ef8  jnz     loc_140005FF8
0x140005efe  test    rbx, rbx
0x140005f01  jz      loc_140005FEF
0x140005f07  mov     r13d, r12d
0x140005f0a  mov     r15d, r12d
0x140005f0d  xor     eax, eax
0x140005f0f  cmp     [rbx], ax
0x140005f12  jz      loc_140005FE7
0x140005f18  xor     edi, edi
0x140005f1a  movzx   eax, word ptr [rbx]
0x140005f1d  movzx   ecx, ax; C
0x140005f20  call    cs:__imp_iswspace
0x140005f26  test    eax, eax
0x140005f28  jz      short loc_140005F36
0x140005f2a  add     rbx, 2
0x140005f2e  movzx   eax, word ptr [rbx]
0x140005f31  test    ax, ax
0x140005f34  jnz     short loc_140005F1D
0x140005f36  movzx   eax, word ptr [rbx]
0x140005f39  sub     ax, 2Dh ; '-'
0x140005f3d  mov     ecx, 0FFFDh
0x140005f42  test    cx, ax
0x140005f45  jnz     short loc_140005FBB
0x140005f47  add     rbx, 2
0x140005f4b  movzx   ecx, word ptr [rbx]; C
0x140005f4e  call    cs:__imp_towupper
0x140005f54  cmp     ax, 54h ; 'T'
0x140005f58  jnz     short loc_140005F62
0x140005f5a  mov     r13d, 1
0x140005f60  jmp     short loc_140005FBB
0x140005f62  movzx   ecx, word ptr [rbx]; C
0x140005f65  call    cs:__imp_towupper
0x140005f6b  cmp     ax, 52h ; 'R'
0x140005f6f  jnz     short loc_140005F79
0x140005f71  mov     r12d, 1
0x140005f77  jmp     short loc_140005FBB
0x140005f79  movzx   ecx, word ptr [rbx]; C
0x140005f7c  call    cs:__imp_towupper
0x140005f82  cmp     ax, 46h ; 'F'
0x140005f86  jnz     short loc_140005F90
0x140005f88  mov     r15d, 1
0x140005f8e  jmp     short loc_140005FBB
0x140005f90  movzx   ecx, word ptr [rbx]; C
0x140005f93  call    cs:__imp_towupper
0x140005f99  cmp     ax, 44h ; 'D'
0x140005f9d  jz      short loc_140005FBB
0x140005f9f  movzx   ecx, word ptr [rbx]; C
0x140005fa2  call    cs:__imp_towupper
0x140005fa8  jmp     short loc_140005FBB
0x140005faa  movzx   ecx, ax; C
0x140005fad  call    cs:__imp_iswspace
0x140005fb3  test    eax, eax
0x140005fb5  jnz     short loc_140005FC3
0x140005fb7  add     rbx, 2
0x140005fbb  movzx   eax, word ptr [rbx]
0x140005fbe  test    ax, ax
  ... truncated ...
```
