# BlackScreenDiagnostics::GetDwmFrontBufferBitsColor

- ea: `0x14000e534`
- end: `0x14000e6cf`
- name: `BlackScreenDiagnostics::GetDwmFrontBufferBitsColor`
- size: `411`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000e6d8`

## callees

- `0x14000381c`
- `0x1400076d0`
- `0x14000bb94`
- `0x14000e194`
- `0x14000e534`
- `0x14000f608`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000e557`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000e557`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14000e682`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14000e682`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e58c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e610`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e58c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e610`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x14000e5db`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x14000e5db`
- `win32u!NtDesktopCaptureBits` at `0x14000e670`
- `win32u!NtDesktopCaptureBits` at `0x14000e670`
- `ntdll!RtlNtStatusToDosError` at `0x14000e69a`
- `ntdll!RtlNtStatusToDosError` at `0x14000e69a`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x14000e5a5`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x14000e5b2`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x14000e5a5`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x14000e5b2`

## pseudocode

```c
__int64 __fastcall BlackScreenDiagnostics::GetDwmFrontBufferBitsColor(__int64 a1, __int64 a2, __int64 a3, int *a4)
{
  HANDLE EventW; // rax
  HANDLE v6; // rdi
  bool v7; // bl
  __int64 LastError; // rbx
  __int64 v9; // rcx
  int SystemMetrics; // ebp
  int v11; // r15d
  HANDLE FileMappingW; // rbx
  __int64 v13; // rcx
  NTSTATUS v14; // eax
  ULONG v15; // edi
  int IsSectionAllBlackPixels; // eax
  HANDLE hHandle; // [rsp+40h] [rbp-58h] BYREF
  HANDLE v19; // [rsp+48h] [rbp-50h] BYREF
  _QWORD v20[9]; // [rsp+50h] [rbp-48h] BYREF

  hHandle = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &hHandle,
    EventW);
  v6 = hHandle;
  v19 = 0;
  v7 = hHandle == 0;
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
  if ( !v7 )
  {
    SystemMetrics = GetSystemMetrics(0);
    v11 = GetSystemMetrics(1);
    FileMappingW = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0x8000004u, 0, 0x75300u, 0);
    v19 = FileMappingW;
    v20[0] = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v20);
    if ( (((unsigned __int64)FileMappingW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      LastError = GetLastError();
      MicrosoftTelemetryAssertTriggeredArgs(v13, LastError, 0);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v19);
      goto LABEL_11;
    }
    v14 = NtDesktopCaptureBits(
            0,
            (unsigned int)(SystemMetrics / 2 - 200),
            (unsigned int)(v11 / 2 - 150),
            400,
            300,
            87,
            v6,
            FileMappingW);
    if ( v14 < 0 )
    {
      v15 = RtlNtStatusToDosError(v14);
    }
    else
    {
      v15 = WaitForSingleObject(v6, 0x1388u);
      if ( !v15 )
      {
        IsSectionAllBlackPixels = BlackScreenDiagnostics::IsSectionAllBlackPixels(FileMappingW);
LABEL_10:
        *a4 = IsSectionAllBlackPixels;
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v19);
        LODWORD(LastError) = v15;
        goto LABEL_11;
      }
    }
    IsSectionAllBlackPixels = 3;
    goto LABEL_10;
  }
  LODWORD(LastError) = GetLastError();
  MicrosoftTelemetryAssertTriggeredArgs(v9, (unsigned int)LastError, 0);
LABEL_11:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hHandle);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x14000e534  push    rbx
0x14000e536  push    rbp
0x14000e537  push    rsi
0x14000e538  push    rdi
0x14000e539  push    r14
0x14000e53b  push    r15
0x14000e53d  sub     rsp, 68h
0x14000e541  mov     r14, r9
0x14000e544  mov     [rsp+98h+hHandle], 0
0x14000e54d  xor     r9d, r9d; lpName
0x14000e550  xor     r8d, r8d; bInitialState
0x14000e553  xor     edx, edx; bManualReset
0x14000e555  xor     ecx, ecx; lpEventAttributes
0x14000e557  call    cs:__imp_CreateEventW
0x14000e55d  mov     rdx, rax
0x14000e560  lea     rcx, [rsp+98h+hHandle]
0x14000e565  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x14000e56a  mov     rdi, [rsp+98h+hHandle]
0x14000e56f  lea     rcx, [rsp+98h+var_50]
0x14000e574  test    rdi, rdi
0x14000e577  mov     [rsp+98h+var_50], 0
0x14000e580  setz    bl
0x14000e583  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000e588  test    bl, bl
0x14000e58a  jz      short loc_14000E5A3
0x14000e58c  call    cs:__imp_GetLastError
0x14000e592  mov     ebx, eax
0x14000e594  xor     r8d, r8d
0x14000e597  mov     edx, eax
0x14000e599  call    MicrosoftTelemetryAssertTriggeredArgs
0x14000e59e  jmp     loc_14000E6B6
0x14000e5a3  xor     ecx, ecx; nIndex
0x14000e5a5  call    cs:__imp_GetSystemMetrics
0x14000e5ab  mov     ecx, 1; nIndex
0x14000e5b0  mov     ebp, eax
0x14000e5b2  call    cs:__imp_GetSystemMetrics
0x14000e5b8  xor     r9d, r9d; dwMaximumSizeHigh
0x14000e5bb  mov     [rsp+98h+lpName], 0; lpName
0x14000e5c4  xor     edx, edx; lpFileMappingAttributes
0x14000e5c6  mov     [rsp+98h+dwMaximumSizeLow], 75300h; dwMaximumSizeLow
0x14000e5ce  mov     r8d, 8000004h; flProtect
0x14000e5d4  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x14000e5d8  mov     r15d, eax
0x14000e5db  call    cs:__imp_CreateFileMappingW
0x14000e5e1  mov     rbx, rax
0x14000e5e4  mov     [rsp+98h+var_50], rax
0x14000e5e9  mov     [rsp+98h+var_48], 0
0x14000e5f2  lea     rcx, [rax+1]
0x14000e5f6  test    rcx, 0FFFFFFFFFFFFFFFEh
0x14000e5fd  lea     rcx, [rsp+98h+var_48]
0x14000e602  setz    sil
0x14000e606  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14000e60b  test    sil, sil
0x14000e60e  jz      short loc_14000E631
0x14000e610  call    cs:__imp_GetLastError
0x14000e616  mov     ebx, eax
0x14000e618  xor     r8d, r8d
0x14000e61b  mov     edx, eax
0x14000e61d  call    MicrosoftTelemetryAssertTriggeredArgs
0x14000e622  lea     rcx, [rsp+98h+var_50]
0x14000e627  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14000e62c  jmp     loc_14000E6B6
0x14000e631  mov     eax, r15d
0x14000e634  mov     [rsp+98h+var_60], rbx
0x14000e639  cdq
0x14000e63a  mov     [rsp+98h+var_68], rdi
0x14000e63f  mov     ecx, 2
0x14000e644  mov     dword ptr [rsp+98h+lpName], 57h ; 'W'
0x14000e64c  idiv    ecx
0x14000e64e  mov     r9d, 190h
0x14000e654  mov     [rsp+98h+dwMaximumSizeLow], 12Ch
0x14000e65c  lea     r8d, [rax-96h]
0x14000e663  mov     eax, ebp
0x14000e665  cdq
0x14000e666  idiv    ecx
0x14000e668  xor     ecx, ecx
0x14000e66a  lea     edx, [rax-0C8h]
0x14000e670  call    cs:__imp_NtDesktopCaptureBits
0x14000e676  test    eax, eax
0x14000e678  js      short loc_14000E698
0x14000e67a  mov     edx, 1388h; dwMilliseconds
0x14000e67f  mov     rcx, rdi; hHandle
0x14000e682  call    cs:__imp_WaitForSingleObject
0x14000e688  mov     edi, eax
0x14000e68a  test    eax, eax
0x14000e68c  jnz     short loc_14000E6A2
0x14000e68e  mov     rcx, rbx
0x14000e691  call    BlackScreenDiagnostics__IsSectionAllBlackPixels
0x14000e696  jmp     short loc_14000E6A7
0x14000e698  mov     ecx, eax; Status
0x14000e69a  call    cs:__imp_RtlNtStatusToDosError
0x14000e6a0  mov     edi, eax
0x14000e6a2  mov     eax, 3
0x14000e6a7  lea     rcx, [rsp+98h+var_50]
0x14000e6ac  mov     [r14], eax
0x14000e6af  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14000e6b4  mov     ebx, edi
0x14000e6b6  lea     rcx, [rsp+98h+hHandle]
0x14000e6bb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000e6c0  mov     eax, ebx
0x14000e6c2  add     rsp, 68h
0x14000e6c6  pop     r15
0x14000e6c8  pop     r14
0x14000e6ca  pop     rdi
0x14000e6cb  pop     rsi
0x14000e6cc  pop     rbp
0x14000e6cd  pop     rbx
0x14000e6ce  retn
```
