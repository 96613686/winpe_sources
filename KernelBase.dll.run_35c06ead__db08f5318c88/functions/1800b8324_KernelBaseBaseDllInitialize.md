# _KernelBaseBaseDllInitialize

- ea: `0x1800b8324`
- end: `0x1800b8859`
- name: `_KernelBaseBaseDllInitialize`
- size: `1333`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800b82ac`

## callees

- `0x18003d204`
- `0x18008a9f8`
- `0x1800b8324`
- `0x1800b88a4`
- `0x1800b8cbc`
- `0x1800b8d4c`
- `0x1800b8de4`
- `0x1800b93d0`
- `0x1800b960c`
- `0x1800e5560`
- `0x180107c5c`
- `0x18011238c`
- `0x180117adc`
- `0x18012163c`
- `0x180182e50`
- `0x180188f10`

## import_xrefs

- `ntdll!RtlFreeAnsiString` at `0x18019318e`
- `ntdll!RtlFreeAnsiString` at `0x18019318e`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x1800b85df`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x1800b85df`
- `ntdll!RtlDeleteCriticalSection` at `0x1800b8847`
- `ntdll!RtlDeleteCriticalSection` at `0x1800b8847`
- `ntdll!RtlInitializeCriticalSection` at `0x1800b8641`
- `ntdll!RtlInitializeCriticalSection` at `0x1800b8641`
- `ntdll!NtQuerySystemInformation` at `0x1800b8479`
- `ntdll!NtQuerySystemInformation` at `0x1800b8479`
- `ntdll!RtlEncodePointer` at `0x1800b85fc`
- `ntdll!RtlEncodePointer` at `0x1800b85fc`
- `ntdll!RtlRandomEx` at `0x1800b848c`
- `ntdll!RtlRandomEx` at `0x1800b84a4`
- `ntdll!RtlRandomEx` at `0x1800b848c`
- `ntdll!RtlRandomEx` at `0x1800b84a4`
- `ntdll!RtlFreeHeap` at `0x1800b87c3`
- `ntdll!RtlFreeHeap` at `0x1801931b3`
- `ntdll!RtlFreeHeap` at `0x1800b87c3`
- `ntdll!RtlFreeHeap` at `0x1801931b3`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x1800b842e`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x1800b842e`
- `ntdll!RtlCreateTagHeap` at `0x1800b841c`
- `ntdll!RtlCreateTagHeap` at `0x1800b841c`
- `ntdll!RtlSetUnhandledExceptionFilter` at `0x1800b85f4`
- `ntdll!RtlSetUnhandledExceptionFilter` at `0x1800b85f4`
- `ntdll!RtlCleanUpTEBLangLists` at `0x1800b83c2`
- `ntdll!RtlCleanUpTEBLangLists` at `0x1800b83c2`
- `ntdll!CsrClientConnectToServer` at `0x1800b8500`
- `ntdll!CsrClientConnectToServer` at `0x1800b8500`

## string_xrefs

- `0x1800b840f`: `BASEDLL!`

## pseudocode

```c
char __fastcall KernelBaseBaseDllInitialize(__int64 a1, unsigned int a2, __int64 a3)
{
  struct _PEB *v5; // rbx
  char result; // al
  struct _RTL_USER_PROCESS_PARAMETERS *ProcessParameters; // rax
  ULONG SessionId; // edi
  char *v9; // r9
  __int16 v10; // ax
  WCHAR *v11; // r10
  WCHAR *v12; // rcx
  WCHAR *v13; // r10
  WCHAR *v14; // rcx
  PVOID v15; // rax
  __int16 v16; // ax
  unsigned __int8 ServerToServerCall[4]; // [rsp+30h] [rbp-D0h] BYREF
  ULONG Seed; // [rsp+34h] [rbp-CCh] BYREF
  HMODULE (__stdcall *ConnectionInfo)(LPCWSTR, HANDLE, DWORD); // [rsp+38h] [rbp-C8h] BYREF
  wchar_t pszDest[256]; // [rsp+40h] [rbp-C0h] BYREF

  Seed = 0;
  ServerToServerCall[0] = 0;
  v5 = NtCurrentPeb();
  Seed = (ULONG)NtCurrentTeb()->ClientId.UniqueProcess;
  if ( !a2 )
  {
    TraceLoggingUnregister_EtwEventUnregister();
    if ( !a3 )
    {
      v16 = BasepInitializationStage;
      if ( (unsigned __int16)BasepInitializationStage > 0x258u )
      {
        ConsoleCleanupConnectionState(&ConsoleConnectionState);
        RtlDeleteCriticalSection(&ConsoleStateLock);
        v16 = BasepInitializationStage;
      }
      if ( (unsigned __int16)v16 > 0x1F4u )
      {
        BasepUnInitComputerNameCache();
        v16 = BasepInitializationStage;
      }
      a1 = 400;
      if ( (unsigned __int16)v16 > 0x190u )
        BaseNlsDllInitialize(400, 0, 0);
      if ( BaseAnsiCommandLine.Buffer )
        RtlFreeAnsiString(&BaseAnsiCommandLine);
    }
    if ( BasepFilterInfo )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, BasepFilterInfo);
    ConnectionInfo = LoadLibraryExW;
    return RegKrnInitialize(a1, a2, a3);
  }
  if ( a2 != 1 )
  {
    if ( a2 == 2 )
    {
      if ( ConsoleIsConsoleApplication )
        SetTEBLangID();
    }
    else if ( a2 == 3 )
    {
      RtlCleanUpTEBLangLists();
      if ( NtCurrentTeb()->SavedPriorityState )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtCurrentTeb()->SavedPriorityState);
      BaseNlsThreadCleanup();
    }
    return RegKrnInitialize(a1, a2, a3);
  }
  ProcessParameters = v5->ProcessParameters;
  BaseDllHandle = a1;
  if ( (ProcessParameters->Flags & 0x80000000) != 0 )
    BasepIsSecureProcess = 1;
  KernelBaseDllInitializeMemoryManager();
  KernelBaseGlobalData = RtlCreateTagHeap(NtCurrentPeb()->ProcessHeap, 0, (PWSTR)L"BASEDLL!", (PWSTR)L"TMP");
  SessionId = v5->SessionId;
  if ( SessionId == (unsigned int)RtlGetCurrentServiceSessionId() )
    StringCbCopyW(pszDest, 0x200u, L"\\Windows");
  else
    StringCbPrintfW(pszDest, 0x200u, L"%ws\\%ld%ws", L"\\Sessions", SessionId, L"\\Windows");
  if ( NtQuerySystemInformation(SystemBasicInformation, &SysInfo, 0x40u, 0) < 0 )
    return 0;
  BasepFiberCookie = (unsigned __int64)RtlRandomEx(&Seed) << 32;
  BasepFiberCookie = RtlRandomEx(&Seed) | (unsigned __int64)BasepFiberCookie;
  BasepInitializationStage = 100;
  ConnectionInfo = (HMODULE (__stdcall *)(LPCWSTR, HANDLE, DWORD))CtrlRoutine;
  if ( (NtCurrentPeb()->ProcessParameters->Flags & 0x80000000) == 0 )
  {
    if ( CsrClientConnectToServer(pszDest, 1u, &ConnectionInfo, (PULONG)8, ServerToServerCall) >= 0 )
      goto LABEL_17;
    return 0;
  }
  if ( (int)CsrpLocalSetupForSecureProcess() < 0 )
    return 0;
  ServerToServerCall[0] = 0;
LABEL_17:
  BasepInitializationStage = 200;
  v9 = (char *)NtCurrentPeb()->ReadOnlySharedMemoryBase
     + *((_QWORD *)NtCurrentPeb()->ReadOnlyStaticServerData + 1)
     - (unsigned __int64)NtCurrentPeb()[1].Ldr;
  BaseStaticServerData = (__int64)v9;
  v10 = *((_WORD *)v9 + 28);
  byte_1803A2DC4 = ServerToServerCall[0] != 0;
  BaseRCNumber = v10;
  qword_1803A2DC8 = *(_QWORD *)v9;
  v11 = (WCHAR *)*((_QWORD *)v9 + 1);
  UnicodeString = v11;
  if ( v11 )
    v12 = (WCHAR *)((char *)v11
                  + (unsigned __int64)NtCurrentPeb()->ReadOnlySharedMemoryBase
                  + *((_QWORD *)NtCurrentPeb()->ReadOnlyStaticServerData + 1)
                  - *(_QWORD *)((char *)NtCurrentPeb()->ReadOnlySharedMemoryBase
                              + *((_QWORD *)NtCurrentPeb()->ReadOnlyStaticServerData + 1)
                              - (unsigned __int64)NtCurrentPeb()[1].Ldr
                              + 2536)
                  - (unsigned __int64)NtCurrentPeb()[1].Ldr);
  else
    v12 = 0;
  UnicodeString = v12;
  qword_1803A2DD8 = *((_QWORD *)v9 + 2);
  v13 = (WCHAR *)*((_QWORD *)v9 + 3);
  Src = v13;
  if ( v13 )
    v14 = (WCHAR *)((char *)v13
                  + (unsigned __int64)NtCurrentPeb()->ReadOnlySharedMemoryBase
                  + *((_QWORD *)NtCurrentPeb()->ReadOnlyStaticServerData + 1)
                  - *(_QWORD *)((char *)NtCurrentPeb()->ReadOnlySharedMemoryBase
                              + *((_QWORD *)NtCurrentPeb()->ReadOnlyStaticServerData + 1)
                              - (unsigned __int64)NtCurrentPeb()[1].Ldr
                              + 2536)
                  - (unsigned __int64)NtCurrentPeb()[1].Ldr);
  else
    v14 = 0;
  Src = v14;
  BaseUnicodeCommandLine = v5->ProcessParameters->CommandLine;
  if ( RtlUnicodeStringToAnsiString(&BaseAnsiCommandLine, &BaseUnicodeCommandLine, 1u) < 0 )
  {
    BaseAnsiCommandLine.Buffer = 0;
    *(_DWORD *)&BaseAnsiCommandLine.Length = 0;
  }
  RtlSetUnhandledExceptionFilter((PRTLP_UNHANDLED_EXCEPTION_FILTER)UnhandledExceptionFilter);
  v15 = RtlEncodePointer(0);
  BasepInitializationStage = 400;
  BasepCurrentTopLevelFilter = v15;
  if ( !(unsigned __int8)BaseNlsDllInitialize(400, 1, BaseStaticServerData) )
    return 0;
  BasepInitializationStage = 500;
  if ( RtlInitializeCriticalSection(&stru_1803A2E70) < 0 )
    return 0;
  BasepInitializationStage = 600;
  result = ConsoleInitialize();
  if ( result )
  {
    TraceLoggingRegisterEx_EtwEventRegister_EtwEventSetInformation();
    BasepDiscountProcessFreezeTimeFromUnbiasedTime = (unsigned int)Feature_DiscountProcessFreezeTimeFromUnbiasedInterruptTimePrecise__private_IsEnabledDeviceUsageNoInline() != 0;
    BasepInitializationStage = 700;
    return RegKrnInitialize(a1, a2, a3);
  }
  return result;
}

```

## disassembly

```asm
0x1800b8324  push    rbp
0x1800b8326  push    rbx
0x1800b8327  push    rsi
0x1800b8328  push    rdi
0x1800b8329  push    r14
0x1800b832b  push    r15
0x1800b832d  lea     rbp, [rsp-158h]
0x1800b8335  sub     rsp, 258h
0x1800b833c  mov     rax, cs:__security_cookie
0x1800b8343  xor     rax, rsp
0x1800b8346  mov     [rbp+180h+var_40], rax
0x1800b834d  xor     r15d, r15d
0x1800b8350  mov     rsi, r8
0x1800b8353  mov     [rsp+280h+Seed], r15d
0x1800b8358  mov     r14d, edx
0x1800b835b  mov     [rsp+280h+var_250], r15b
0x1800b8360  mov     rbx, gs:60h
0x1800b8369  mov     rax, gs:30h
0x1800b8372  mov     r9d, [rax+40h]
0x1800b8376  mov     eax, edx
0x1800b8378  mov     [rsp+280h+Seed], r9d
0x1800b837d  test    edx, edx
0x1800b837f  jz      loc_1800B8811
0x1800b8385  sub     eax, 1
0x1800b8388  jz      short loc_1800B83E5
0x1800b838a  sub     eax, 1
0x1800b838d  jz      loc_1800B8695
0x1800b8393  cmp     eax, 1
0x1800b8396  jz      short loc_1800B83C2
0x1800b8398  mov     r8, rsi
0x1800b839b  mov     edx, r14d
0x1800b839e  call    RegKrnInitialize
0x1800b83a3  mov     rcx, [rbp+180h+var_40]
0x1800b83aa  xor     rcx, rsp; StackCookie
0x1800b83ad  call    __security_check_cookie
0x1800b83b2  add     rsp, 258h
0x1800b83b9  pop     r15
0x1800b83bb  pop     r14
0x1800b83bd  pop     rdi
0x1800b83be  pop     rsi
0x1800b83bf  pop     rbx
0x1800b83c0  pop     rbp
0x1800b83c1  retn
0x1800b83c2  call    cs:__imp_RtlCleanUpTEBLangLists
0x1800b83c8  mov     rax, gs:30h
0x1800b83d1  cmp     [rax+1768h], r15
0x1800b83d8  jnz     loc_1800B87A4
0x1800b83de  call    BaseNlsThreadCleanup
0x1800b83e3  jmp     short loc_1800B8398
0x1800b83e5  mov     rax, [rbx+20h]
0x1800b83e9  mov     cs:BaseDllHandle, rcx
0x1800b83f0  cmp     [rax+8], r15d
0x1800b83f4  jl      loc_1800B87CE
0x1800b83fa  call    KernelBaseDllInitializeMemoryManager
0x1800b83ff  mov     rcx, gs:60h
0x1800b8408  lea     r9, TagSubName; "TMP"
0x1800b840f  lea     r8, TagName; "BASEDLL!"
0x1800b8416  xor     edx, edx; Flags
0x1800b8418  mov     rcx, [rcx+30h]; HeapHandle
0x1800b841c  call    cs:__imp_RtlCreateTagHeap
0x1800b8422  mov     cs:KernelBaseGlobalData, eax
0x1800b8428  mov     edi, [rbx+2C0h]
0x1800b842e  call    cs:__imp_RtlGetCurrentServiceSessionId
0x1800b8434  mov     edx, 200h; cbDest
0x1800b8439  lea     rcx, [rsp+280h+pszDest]; pszDest
0x1800b843e  cmp     edi, eax
0x1800b8440  jz      loc_1800B87DA
0x1800b8446  lea     rax, aWindows; "\\Windows"
0x1800b844d  mov     [rsp+280h+var_258], rax
0x1800b8452  lea     r9, aSessions; "\\Sessions"
0x1800b8459  lea     r8, aWsLdWs; "%ws\\%ld%ws"
0x1800b8460  mov     dword ptr [rsp+280h+ServerToServerCall], edi
0x1800b8464  call    StringCbPrintfW
0x1800b8469  xor     r9d, r9d; ReturnLength
0x1800b846c  lea     rdx, SysInfo; SystemInformation
0x1800b8473  xor     ecx, ecx; SystemInformationClass
0x1800b8475  lea     r8d, [r9+40h]; SystemInformationLength
0x1800b8479  call    cs:__imp_NtQuerySystemInformation
0x1800b847f  test    eax, eax
0x1800b8481  js      loc_1800B879C
0x1800b8487  lea     rcx, [rsp+280h+Seed]; Seed
0x1800b848c  call    cs:__imp_RtlRandomEx
0x1800b8492  mov     eax, eax
0x1800b8494  lea     rcx, [rsp+280h+Seed]; Seed
0x1800b8499  shl     rax, 20h
0x1800b849d  mov     cs:BasepFiberCookie, rax
0x1800b84a4  call    cs:__imp_RtlRandomEx
0x1800b84aa  mov     eax, eax
0x1800b84ac  or      cs:BasepFiberCookie, rax
0x1800b84b3  mov     eax, 64h ; 'd'
0x1800b84b8  mov     cs:BasepInitializationStage, ax
0x1800b84bf  lea     rax, CtrlRoutine
0x1800b84c6  mov     [rsp+280h+ConnectionInfo], rax
0x1800b84cb  mov     rax, gs:60h
0x1800b84d4  mov     rcx, [rax+20h]
0x1800b84d8  cmp     [rcx+8], r15d
0x1800b84dc  jl      loc_1800B87EB
0x1800b84e2  mov     r9d, 8; ConnectionInfoSize
0x1800b84e8  lea     rax, [rsp+280h+var_250]
0x1800b84ed  lea     r8, [rsp+280h+ConnectionInfo]; ConnectionInfo
0x1800b84f2  mov     [rsp+280h+ServerToServerCall], rax; ServerToServerCall
0x1800b84f7  lea     rcx, [rsp+280h+pszDest]; ObjectDirectory
0x1800b84fc  lea     edx, [r9-7]; ServerId
0x1800b8500  call    cs:__imp_CsrClientConnectToServer
0x1800b8506  test    eax, eax
0x1800b8508  js      loc_1800B879C
0x1800b850e  mov     eax, 0C8h
0x1800b8513  mov     cs:BasepInitializationStage, ax
0x1800b851a  mov     rax, gs:60h
0x1800b8523  mov     rcx, [rax+98h]
0x1800b852a  mov     rax, gs:60h
0x1800b8533  mov     r9, [rcx+8]
0x1800b8537  sub     r9, [rax+380h]
0x1800b853e  mov     rax, gs:60h
0x1800b8547  add     r9, [rax+88h]
0x1800b854e  cmp     [rsp+280h+var_250], r15b
0x1800b8553  mov     cs:BaseStaticServerData, r9
0x1800b855a  movzx   eax, word ptr [r9+38h]
0x1800b855f  setnz   cs:byte_1803A2DC4
0x1800b8566  mov     cs:BaseRCNumber, ax
0x1800b856d  mov     rax, [r9]
0x1800b8570  mov     cs:qword_1803A2DC8, rax
0x1800b8577  mov     r10, [r9+8]
0x1800b857b  mov     cs:UnicodeString, r10
0x1800b8582  test    r10, r10
0x1800b8585  jnz     loc_1800B86AC
0x1800b858b  mov     rcx, r15
0x1800b858e  mov     cs:UnicodeString, rcx
0x1800b8595  mov     rax, [r9+10h]
0x1800b8599  mov     cs:qword_1803A2DD8, rax
0x1800b85a0  mov     r10, [r9+18h]
0x1800b85a4  mov     cs:Src, r10
0x1800b85ab  test    r10, r10
0x1800b85ae  jnz     loc_1800B8724
0x1800b85b4  mov     rcx, r15
0x1800b85b7  mov     cs:Src, rcx
0x1800b85be  lea     rdx, BaseUnicodeCommandLine; SourceString
0x1800b85c5  mov     rax, [rbx+20h]
0x1800b85c9  lea     rcx, BaseAnsiCommandLine; DestinationString
0x1800b85d0  mov     r8b, 1; AllocateDestinationString
0x1800b85d3  movups  xmm0, xmmword ptr [rax+70h]
0x1800b85d7  movdqu  xmmword ptr cs:BaseUnicodeCommandLine.Length, xmm0
0x1800b85df  call    cs:__imp_RtlUnicodeStringToAnsiString
0x1800b85e5  test    eax, eax
0x1800b85e7  js      loc_1800B87FE
0x1800b85ed  lea     rcx, UnhandledExceptionFilter; TopLevelExceptionFilter
0x1800b85f4  call    cs:__imp_RtlSetUnhandledExceptionFilter
0x1800b85fa  xor     ecx, ecx; Pointer
0x1800b85fc  call    cs:__imp_RtlEncodePointer
0x1800b8602  mov     r8, cs:BaseStaticServerData
0x1800b8609  mov     ecx, 190h
0x1800b860e  mov     edx, 1
0x1800b8613  mov     cs:BasepInitializationStage, cx
0x1800b861a  mov     cs:BasepCurrentTopLevelFilter, rax
0x1800b8621  call    BaseNlsDllInitialize
0x1800b8626  test    al, al
0x1800b8628  jz      loc_1800B879C
0x1800b862e  mov     ecx, 1F4h
0x1800b8633  mov     cs:BasepInitializationStage, cx
0x1800b863a  lea     rcx, stru_1803A2E70; CriticalSection
0x1800b8641  call    cs:__imp_RtlInitializeCriticalSection
0x1800b8647  test    eax, eax
0x1800b8649  js      loc_1800B879C
0x1800b864f  mov     ecx, 258h
0x1800b8654  mov     cs:BasepInitializationStage, cx
0x1800b865b  call    ConsoleInitialize
0x1800b8660  test    al, al
0x1800b8662  jz      loc_1800B83A3
0x1800b8668  call    TraceLoggingRegisterEx_EtwEventRegister_EtwEventSetInformation
0x1800b866d  mov     cs:BasepDiscountProcessFreezeTimeFromUnbiasedTime, r15b
0x1800b8674  call    Feature_DiscountProcessFreezeTimeFromUnbiasedInterruptTimePrecise__private_IsEnabledDeviceUsageNoInline
0x1800b8679  test    eax, eax
0x1800b867b  jz      short loc_1800B8684
0x1800b867d  mov     cs:BasepDiscountProcessFreezeTimeFromUnbiasedTime, 1
0x1800b8684  mov     eax, 2BCh
0x1800b8689  mov     cs:BasepInitializationStage, ax
0x1800b8690  jmp     loc_1800B8398
0x1800b8695  cmp     cs:ConsoleIsConsoleApplication, r15b
0x1800b869c  jz      loc_1800B8398
0x1800b86a2  call    SetTEBLangID
0x1800b86a7  jmp     loc_1800B8398
0x1800b86ac  mov     rax, gs:60h
0x1800b86b5  mov     rcx, [rax+98h]
0x1800b86bc  mov     rax, gs:60h
0x1800b86c5  mov     r8, [rcx+8]
0x1800b86c9  sub     r8, [rax+380h]
0x1800b86d0  mov     rax, gs:60h
0x1800b86d9  mov     rdx, [rax+88h]
0x1800b86e0  mov     rax, gs:60h
0x1800b86e9  mov     rcx, [rax+98h]
0x1800b86f0  mov     rax, gs:60h
0x1800b86f9  mov     rcx, [rcx+8]
0x1800b86fd  sub     rcx, [r8+rdx+9E8h]
0x1800b8705  sub     rcx, [rax+380h]
0x1800b870c  mov     rax, gs:60h
0x1800b8715  add     rcx, [rax+88h]
0x1800b871c  add     rcx, r10
0x1800b871f  jmp     loc_1800B858E
0x1800b8724  mov     rax, gs:60h
0x1800b872d  mov     rcx, [rax+98h]
0x1800b8734  mov     rax, gs:60h
0x1800b873d  mov     r8, [rcx+8]
0x1800b8741  sub     r8, [rax+380h]
0x1800b8748  mov     rax, gs:60h
0x1800b8751  mov     rdx, [rax+88h]
0x1800b8758  mov     rax, gs:60h
0x1800b8761  mov     rcx, [rax+98h]
0x1800b8768  mov     rax, gs:60h
0x1800b8771  mov     rcx, [rcx+8]
0x1800b8775  sub     rcx, [r8+rdx+9E8h]
0x1800b877d  sub     rcx, [rax+380h]
0x1800b8784  mov     rax, gs:60h
0x1800b878d  add     rcx, [rax+88h]
0x1800b8794  add     rcx, r10
0x1800b8797  jmp     loc_1800B85B7
0x1800b879c  mov     al, r15b
0x1800b879f  jmp     loc_1800B83A3
0x1800b87a4  mov     r8, gs:30h
0x1800b87ad  xor     edx, edx; Flags
0x1800b87af  mov     rcx, gs:60h
0x1800b87b8  mov     r8, [r8+1768h]; P
0x1800b87bf  mov     rcx, [rcx+30h]; HeapHandle
0x1800b87c3  call    cs:__imp_RtlFreeHeap
0x1800b87c9  jmp     loc_1800B83DE
0x1800b87ce  mov     cs:BasepIsSecureProcess, 1
0x1800b87d5  jmp     loc_1800B83FA
0x1800b87da  lea     r8, aWindows; "\\Windows"
0x1800b87e1  call    StringCbCopyW
0x1800b87e6  jmp     loc_1800B8469
0x1800b87eb  call    CsrpLocalSetupForSecureProcess
0x1800b87f0  test    eax, eax
0x1800b87f2  js      short loc_1800B879C
0x1800b87f4  mov     [rsp+280h+var_250], r15b
0x1800b87f9  jmp     loc_1800B850E
0x1800b87fe  mov     cs:BaseAnsiCommandLine.Buffer, r15
0x1800b8805  mov     dword ptr cs:BaseAnsiCommandLine.Length, r15d
0x1800b880c  jmp     loc_1800B85ED
0x1800b8811  call    TraceLoggingUnregister_EtwEventUnregister
0x1800b8816  test    rsi, rsi
0x1800b8819  jnz     loc_180193194
0x1800b881f  movzx   eax, cs:BasepInitializationStage
0x1800b8826  mov     ecx, 258h
0x1800b882b  cmp     ax, cx
0x1800b882e  jbe     loc_180193154
0x1800b8834  lea     rcx, ConsoleConnectionState
0x1800b883b  call    ConsoleCleanupConnectionState
0x1800b8840  lea     rcx, ConsoleStateLock; CriticalSection
0x1800b8847  call    cs:__imp_RtlDeleteCriticalSection
0x1800b884d  movzx   eax, cs:BasepInitializationStage
0x1800b8854  jmp     loc_180193154
0x180193154  mov     ecx, 1F4h
0x180193159  cmp     ax, cx
0x18019315c  jbe     short loc_18019316A
0x18019315e  call    BasepUnInitComputerNameCache
0x180193163  movzx   eax, cs:BasepInitializationStage
0x18019316a  mov     ecx, 190h
0x18019316f  cmp     ax, cx
0x180193172  jbe     short loc_18019317E
0x180193174  xor     r8d, r8d
0x180193177  xor     edx, edx
0x180193179  call    BaseNlsDllInitialize
0x18019317e  cmp     cs:BaseAnsiCommandLine.Buffer, r15
0x180193185  jz      short loc_180193194
0x180193187  lea     rcx, BaseAnsiCommandLine; AnsiString
0x18019318e  call    cs:__imp_RtlFreeAnsiString
0x180193194  cmp     cs:BasepFilterInfo, r15
0x18019319b  jz      short loc_1801931B9
0x18019319d  mov     rcx, gs:60h
0x1801931a6  xor     edx, edx; Flags
0x1801931a8  mov     r8, cs:BasepFilterInfo; P
0x1801931af  mov     rcx, [rcx+30h]; HeapHandle
0x1801931b3  call    cs:__imp_RtlFreeHeap
0x1801931b9  lea     rax, LoadLibraryA
0x1801931c0  mov     [rsp+280h+ConnectionInfo], rax
0x1801931c5  lea     rax, LoadLibraryW
0x1801931cc  mov     [rsp+280h+ConnectionInfo], rax
0x1801931d1  lea     rax, LoadLibraryExA
0x1801931d8  mov     [rsp+280h+ConnectionInfo], rax
0x1801931dd  lea     rax, LoadLibraryExW
0x1801931e4  mov     [rsp+280h+ConnectionInfo], rax
0x1801931e9  jmp     loc_1800B8398
```
