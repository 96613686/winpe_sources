# BdeSvcRecoveryTelemetryTriggerWorkerThread(void *)

- ea: `0x18001e900`
- end: `0x18001ee36`
- name: `?BdeSvcRecoveryTelemetryTriggerWorkerThread@@YAIPEAX@Z`
- size: `1334`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180009c30`
- `0x180009f30`
- `0x180009f60`
- `0x18001b890`
- `0x18001e900`
- `0x18001ee3c`
- `0x180034070`
- `0x180040fac`
- `0x180044578`
- `0x18006c39c`

## import_xrefs

- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18001ebf7`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18001ebf7`
- `ntdll!NtQuerySystemEnvironmentValueEx` at `0x18001ea21`
- `ntdll!NtQuerySystemEnvironmentValueEx` at `0x18001ea21`
- `ntdll!RtlInitUnicodeString` at `0x18001e9f5`
- `ntdll!RtlInitUnicodeString` at `0x18001e9f5`
- `ntdll!RtlNtStatusToDosError` at `0x18001ea2f`
- `ntdll!RtlNtStatusToDosError` at `0x18001ea2f`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18001ed73`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18001ed73`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001ebb1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001ebb1`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001ec59`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001ec59`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001eb97`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001eb97`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001eb30`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001eb30`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001edac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001edac`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001eb08`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001eb08`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001eaf1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ed98`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001eaf1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ed98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eb3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ec86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ecca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eb3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ec86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ecca`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001edf7`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001edf7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ed87`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ee0b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ed87`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ee0b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall BdeSvcRecoveryTelemetryTriggerWorkerThread(void *a1)
{
  HANDLE EventW; // rsi
  _DWORD *v2; // rdi
  unsigned int v3; // eax
  signed int v4; // ebx
  NTSTATUS v5; // eax
  signed int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  unsigned int v9; // eax
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  HANDLE ProcessHeap; // rax
  signed int LastError; // eax
  HANDLE v15; // rbx
  int v16; // eax
  unsigned int v17; // eax
  DWORD v18; // eax
  signed int v19; // eax
  signed int v20; // eax
  _QWORD *v21; // rcx
  __int64 v22; // rdx
  BdeSvcWorkTracking *v23; // rcx
  HANDLE v24; // rax
  HANDLE v25; // rdi
  int v27; // [rsp+40h] [rbp-49h] BYREF
  HANDLE Token; // [rsp+48h] [rbp-41h] BYREF
  char v29; // [rsp+50h] [rbp-39h]
  int v30; // [rsp+54h] [rbp-35h]
  BdeSvcWorkTracking *v31; // [rsp+58h] [rbp-31h] BYREF
  unsigned int Value; // [rsp+60h] [rbp-29h] BYREF
  ULONG ReturnLength; // [rsp+64h] [rbp-25h] BYREF
  GUID VendorGuid; // [rsp+68h] [rbp-21h] BYREF
  ULONG Attributes; // [rsp+78h] [rbp-11h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-9h] BYREF
  HANDLE Handles[2]; // [rsp+90h] [rbp+7h] BYREF

  ReturnLength = 0;
  Attributes = 0;
  Value = 0;
  DestinationString = 0;
  VendorGuid.Data1 = 2012912317;
  *(_DWORD *)&VendorGuid.Data2 = 1295123289;
  *(_DWORD *)VendorGuid.Data4 = -198680387;
  *(_DWORD *)&VendorGuid.Data4[4] = 1266192359;
  v31 = 0;
  EventW = 0;
  *(_OWORD *)Handles = 0;
  Token = 0;
  v29 = 0;
  v30 = 0;
  v2 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 283, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
  v27 = 22;
  v3 = CNgscbScopedPrivilege::AcquirePrivileges((CNgscbScopedPrivilege *)&Token, &v27);
  v4 = v3;
  if ( !v3 )
    goto LABEL_12;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 284, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids, v3);
  if ( v4 >= 0 )
  {
LABEL_12:
    RtlInitUnicodeString(&DestinationString, L"BLRecovery");
    ReturnLength = 4;
    v5 = NtQuerySystemEnvironmentValueEx(&DestinationString, &VendorGuid, &Value, &ReturnLength, &Attributes);
    v6 = RtlNtStatusToDosError(v5);
    v4 = v6;
    if ( v6 > 0 )
      v4 = (unsigned __int16)v6 | 0x80070000;
    if ( v4 >= 0 && ReturnLength == 4 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, v8, Value, v4);
      if ( (unsigned int)FveCanProvisionDE(&FVE_GUID_PROV_SCENARIO_DECHECK_NVRAMRECTEL, 0) )
      {
        v9 = FireNVRAMRecoveryTelemetry(Value);
        v4 = v9;
        if ( v9 )
        {
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          {
            v11 = 286;
            v12 = v9;
LABEL_54:
            WPP_SF_d(v10[2], v11, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids, v12);
          }
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 287, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
        ProcessHeap = GetProcessHeap();
        v2 = HeapAlloc(ProcessHeap, 0, 0x10u);
        if ( !v2 )
        {
          v4 = -2147024882;
          goto LABEL_65;
        }
        EventW = CreateEventW(0, 0, 0, 0);
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
        if ( !v4 )
          goto LABEL_37;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            288,
            &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids,
            (unsigned int)v4);
        if ( v4 >= 0 )
        {
LABEL_37:
          AcquireSRWLockShared(&g_srwlStopEvent);
          v15 = g_hStopEvent;
          ReleaseSRWLockShared(&g_srwlStopEvent);
          Handles[0] = v15;
          Handles[1] = EventW;
          *(_QWORD *)v2 = EventW;
          v2[2] = Value;
          v16 = RtlSubscribeWnfStateChangeNotification(
                  &v31,
                  WNF_SHEL_OOBE_USER_LOGON_COMPLETE,
                  0,
                  FireNVRAMRecoveryTelemetryCallBack,
                  v2,
                  0,
                  0,
                  0);
          v17 = FromNtStatus(v16);
          v4 = v17;
          if ( !v17 )
            goto LABEL_38;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 289, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids, v17);
          if ( v4 >= 0 )
          {
LABEL_38:
            v18 = WaitForMultipleObjectsEx(2u, Handles, 0, 0x124F80u, 0);
            if ( v18 )
            {
              if ( v18 == 1 )
              {
                v21 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
                  goto LABEL_65;
                v22 = 291;
              }
              else
              {
                if ( v18 != 258 )
                {
                  if ( v18 == -1 )
                  {
                    v20 = GetLastError();
                    v4 = v20;
                    if ( v20 > 0 )
                      v4 = (unsigned __int16)v20 | 0x80070000;
                    v10 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
                      goto LABEL_65;
                    v11 = 293;
                  }
                  else
                  {
                    v19 = GetLastError();
                    v4 = v19;
                    if ( v19 > 0 )
                      v4 = (unsigned __int16)v19 | 0x80070000;
                    if ( !v4 )
                      goto LABEL_65;
                    v10 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
                      goto LABEL_65;
                    v11 = 294;
                  }
                  v12 = (unsigned int)v4;
                  goto LABEL_54;
                }
                v21 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
                  goto LABEL_65;
                v22 = 292;
              }
            }
            else
            {
              v21 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
                goto LABEL_65;
              v22 = 290;
            }
            WPP_SF_(v21[2], v22, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
          }
        }
      }
    }
  }
LABEL_65:
  v23 = v31;
  if ( v31 )
    RtlUnsubscribeWnfNotificationWaitForCompletion(v31);
  if ( EventW )
    CloseHandle(EventW);
  if ( v2 )
  {
    v24 = GetProcessHeap();
    HeapFree(v24, 0, v2);
  }
  BdeSvcWorkTracking::FinishWorkImpl(v23);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      295,
      &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids,
      (unsigned int)v4);
  v25 = Token;
  if ( v29 )
    SetThreadToken(0, Token);
  if ( v25 )
    CloseHandle(v25);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001e900  push    rbp
0x18001e902  push    rbx
0x18001e903  push    rsi
0x18001e904  push    rdi
0x18001e905  push    r14
0x18001e907  push    r15
0x18001e909  lea     rbp, [rsp-2Fh]
0x18001e90e  sub     rsp, 0B8h
0x18001e915  mov     rax, cs:__security_cookie
0x18001e91c  xor     rax, rsp
0x18001e91f  mov     [rbp+57h+var_40], rax
0x18001e923  xor     r14d, r14d
0x18001e926  mov     [rbp+57h+ReturnLength], r14d
0x18001e92a  mov     [rbp+57h+var_68], r14d
0x18001e92e  mov     [rbp+57h+Value], r14d
0x18001e932  xorps   xmm0, xmm0
0x18001e935  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18001e939  mov     [rbp+57h+VendorGuid.Data1], 77FA9ABDh
0x18001e940  mov     dword ptr [rbp+57h+VendorGuid.Data2], 4D320359h
0x18001e947  mov     dword ptr [rbp+57h+VendorGuid.Data4], 0F42860BDh
0x18001e94e  mov     dword ptr [rbp+57h+VendorGuid.Data4+4], 4B788FE7h
0x18001e955  mov     [rbp+57h+var_88], r14
0x18001e959  mov     esi, r14d
0x18001e95c  movdqu  xmmword ptr [rbp+57h+Handles], xmm0
0x18001e961  mov     [rbp+57h+Token], r14
0x18001e965  mov     [rbp+57h+var_90], sil
0x18001e969  mov     [rbp+57h+var_8C], r14d
0x18001e96d  mov     edi, r14d
0x18001e970  lea     r15, WPP_GLOBAL_Control
0x18001e977  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e97e  cmp     rcx, r15
0x18001e981  jz      short loc_18001E99E
0x18001e983  test    byte ptr [rcx+1Ch], 20h
0x18001e987  jz      short loc_18001E99E
0x18001e989  mov     edx, 11Bh
0x18001e98e  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x18001e995  mov     rcx, [rcx+10h]
0x18001e999  call    WPP_SF_
0x18001e99e  mov     [rbp+57h+var_A0], 16h
0x18001e9a5  lea     rdx, [rbp+57h+var_A0]; int *
0x18001e9a9  lea     rcx, [rbp+57h+Token]; this
0x18001e9ad  call    ?AcquirePrivileges@CNgscbScopedPrivilege@@QEAAJPEAJK@Z; CNgscbScopedPrivilege::AcquirePrivileges(long *,ulong)
0x18001e9b2  mov     ebx, eax
0x18001e9b4  test    eax, eax
0x18001e9b6  jz      short loc_18001E9EA
0x18001e9b8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e9bf  cmp     rcx, r15
0x18001e9c2  jz      short loc_18001E9E2
0x18001e9c4  test    byte ptr [rcx+1Ch], 40h
0x18001e9c8  jz      short loc_18001E9E2
0x18001e9ca  mov     edx, 11Ch
0x18001e9cf  mov     r9d, eax
0x18001e9d2  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x18001e9d9  mov     rcx, [rcx+10h]
0x18001e9dd  call    WPP_SF_d
0x18001e9e2  test    ebx, ebx
0x18001e9e4  js      loc_18001ED6A
0x18001e9ea  lea     rdx, SourceString; "BLRecovery"
0x18001e9f1  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18001e9f5  call    cs:__imp_RtlInitUnicodeString
0x18001e9fc  nop     dword ptr [rax+rax+00h]
0x18001ea01  mov     [rbp+57h+ReturnLength], 4
0x18001ea08  lea     rax, [rbp+57h+var_68]
0x18001ea0c  mov     [rsp+0E0h+Attributes], rax; Attributes
0x18001ea11  lea     r9, [rbp+57h+ReturnLength]; ReturnLength
0x18001ea15  lea     r8, [rbp+57h+Value]; Value
0x18001ea19  lea     rdx, [rbp+57h+VendorGuid]; VendorGuid
0x18001ea1d  lea     rcx, [rbp+57h+DestinationString]; VariableName
0x18001ea21  call    cs:__imp_NtQuerySystemEnvironmentValueEx
0x18001ea28  nop     dword ptr [rax+rax+00h]
0x18001ea2d  mov     ecx, eax; Status
0x18001ea2f  call    cs:__imp_RtlNtStatusToDosError
0x18001ea36  nop     dword ptr [rax+rax+00h]
0x18001ea3b  mov     ebx, eax
0x18001ea3d  test    eax, eax
0x18001ea3f  jle     short loc_18001EA4A
0x18001ea41  movzx   ebx, ax
0x18001ea44  or      ebx, 80070000h
0x18001ea4a  test    ebx, ebx
0x18001ea4c  js      loc_18001ED6A
0x18001ea52  cmp     [rbp+57h+ReturnLength], 4
0x18001ea56  jnz     loc_18001ED6A
0x18001ea5c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ea63  cmp     rcx, r15
0x18001ea66  jz      short loc_18001EA7F
0x18001ea68  test    byte ptr [rcx+1Ch], 8
0x18001ea6c  jz      short loc_18001EA7F
0x18001ea6e  mov     dword ptr [rsp+0E0h+Attributes], ebx
0x18001ea72  mov     r9d, [rbp+57h+Value]
0x18001ea76  mov     rcx, [rcx+10h]
0x18001ea7a  call    WPP_SF_Dd
0x18001ea7f  xor     edx, edx; unsigned __int64 *
0x18001ea81  lea     rcx, FVE_GUID_PROV_SCENARIO_DECHECK_NVRAMRECTEL; struct _GUID *
0x18001ea88  call    ?FveCanProvisionDE@@YAHPEBU_GUID@@PEA_K@Z; FveCanProvisionDE(_GUID const *,unsigned __int64 *)
0x18001ea8d  test    eax, eax
0x18001ea8f  jz      short loc_18001EACA
0x18001ea91  mov     ecx, [rbp+57h+Value]; unsigned int
0x18001ea94  call    ?FireNVRAMRecoveryTelemetry@@YAJK@Z; FireNVRAMRecoveryTelemetry(ulong)
0x18001ea99  mov     ebx, eax
0x18001ea9b  test    eax, eax
0x18001ea9d  jz      loc_18001ED6A
0x18001eaa3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eaaa  cmp     rcx, r15
0x18001eaad  jz      loc_18001ED6A
0x18001eab3  test    byte ptr [rcx+1Ch], 40h
0x18001eab7  jz      loc_18001ED6A
0x18001eabd  mov     edx, 11Eh
0x18001eac2  mov     r9d, eax
0x18001eac5  jmp     loc_18001ECFF
0x18001eaca  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ead1  cmp     rcx, r15
0x18001ead4  jz      short loc_18001EAF1
0x18001ead6  test    byte ptr [rcx+1Ch], 8
0x18001eada  jz      short loc_18001EAF1
0x18001eadc  mov     edx, 11Fh
0x18001eae1  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x18001eae8  mov     rcx, [rcx+10h]
0x18001eaec  call    WPP_SF_
0x18001eaf1  call    cs:__imp_GetProcessHeap
0x18001eaf8  nop     dword ptr [rax+rax+00h]
0x18001eafd  mov     rcx, rax; hHeap
0x18001eb00  xor     edx, edx; dwFlags
0x18001eb02  mov     r8d, 10h; dwBytes
0x18001eb08  call    cs:__imp_HeapAlloc
0x18001eb0f  nop     dword ptr [rax+rax+00h]
0x18001eb14  mov     rdi, rax
0x18001eb17  test    rax, rax
0x18001eb1a  jnz     short loc_18001EB26
0x18001eb1c  mov     ebx, 8007000Eh
0x18001eb21  jmp     loc_18001ED6A
0x18001eb26  xor     r9d, r9d; lpName
0x18001eb29  xor     r8d, r8d; bInitialState
0x18001eb2c  xor     edx, edx; bManualReset
0x18001eb2e  xor     ecx, ecx; lpEventAttributes
0x18001eb30  call    cs:__imp_CreateEventW
0x18001eb37  nop     dword ptr [rax+rax+00h]
0x18001eb3c  mov     rsi, rax
0x18001eb3f  call    cs:__imp_GetLastError
0x18001eb46  nop     dword ptr [rax+rax+00h]
0x18001eb4b  mov     ebx, eax
0x18001eb4d  test    eax, eax
0x18001eb4f  jle     short loc_18001EB5A
0x18001eb51  movzx   ebx, ax
0x18001eb54  or      ebx, 80070000h
0x18001eb5a  test    ebx, ebx
0x18001eb5c  jz      short loc_18001EB90
0x18001eb5e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eb65  cmp     rcx, r15
0x18001eb68  jz      short loc_18001EB88
0x18001eb6a  test    byte ptr [rcx+1Ch], 40h
0x18001eb6e  jz      short loc_18001EB88
0x18001eb70  mov     edx, 120h
0x18001eb75  mov     r9d, ebx
0x18001eb78  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x18001eb7f  mov     rcx, [rcx+10h]
0x18001eb83  call    WPP_SF_d
0x18001eb88  test    ebx, ebx
0x18001eb8a  js      loc_18001ED6A
0x18001eb90  lea     rcx, ?g_srwlStopEvent@@3U_RTL_SRWLOCK@@A; SRWLock
0x18001eb97  call    cs:__imp_AcquireSRWLockShared
0x18001eb9e  nop     dword ptr [rax+rax+00h]
0x18001eba3  mov     rbx, cs:?g_hStopEvent@@3REAXEA; void * g_hStopEvent
0x18001ebaa  lea     rcx, ?g_srwlStopEvent@@3U_RTL_SRWLOCK@@A; SRWLock
0x18001ebb1  call    cs:__imp_ReleaseSRWLockShared
0x18001ebb8  nop     dword ptr [rax+rax+00h]
0x18001ebbd  mov     [rbp+57h+Handles], rbx
0x18001ebc1  mov     [rbp+57h+Handles+8], rsi
0x18001ebc5  mov     [rdi], rsi
0x18001ebc8  mov     eax, [rbp+57h+Value]
0x18001ebcb  mov     [rdi+8], eax
0x18001ebce  mov     [rsp+0E0h+var_A8], r14d
0x18001ebd3  mov     [rsp+0E0h+var_B0], r14d
0x18001ebd8  mov     [rsp+0E0h+var_B8], r14
0x18001ebdd  mov     [rsp+0E0h+Attributes], rdi
0x18001ebe2  lea     r9, ?FireNVRAMRecoveryTelemetryCallBack@@YAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; FireNVRAMRecoveryTelemetryCallBack(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x18001ebe9  xor     r8d, r8d
0x18001ebec  mov     rdx, cs:WNF_SHEL_OOBE_USER_LOGON_COMPLETE
0x18001ebf3  lea     rcx, [rbp+57h+var_88]
0x18001ebf7  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x18001ebfe  nop     dword ptr [rax+rax+00h]
0x18001ec03  mov     ecx, eax; int
0x18001ec05  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18001ec0a  mov     ebx, eax
0x18001ec0c  test    eax, eax
0x18001ec0e  jz      short loc_18001EC42
0x18001ec10  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ec17  cmp     rcx, r15
0x18001ec1a  jz      short loc_18001EC3A
0x18001ec1c  test    byte ptr [rcx+1Ch], 40h
0x18001ec20  jz      short loc_18001EC3A
0x18001ec22  mov     edx, 121h
0x18001ec27  mov     r9d, eax
0x18001ec2a  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x18001ec31  mov     rcx, [rcx+10h]
0x18001ec35  call    WPP_SF_d
0x18001ec3a  test    ebx, ebx
0x18001ec3c  js      loc_18001ED6A
0x18001ec42  mov     dword ptr [rsp+0E0h+Attributes], r14d; bAlertable
0x18001ec47  mov     r9d, 124F80h; dwMilliseconds
0x18001ec4d  xor     r8d, r8d; bWaitAll
0x18001ec50  lea     rdx, [rbp+57h+Handles]; lpHandles
0x18001ec54  mov     ecx, 2; nCount
0x18001ec59  call    cs:__imp_WaitForMultipleObjectsEx
0x18001ec60  nop     dword ptr [rax+rax+00h]
0x18001ec65  test    eax, eax
0x18001ec67  jz      loc_18001ED43
0x18001ec6d  cmp     eax, 1
0x18001ec70  jz      loc_18001ED2A
0x18001ec76  cmp     eax, 102h
0x18001ec7b  jz      loc_18001ED11
0x18001ec81  cmp     eax, 0FFFFFFFFh
0x18001ec84  jz      short loc_18001ECCA
0x18001ec86  call    cs:__imp_GetLastError
0x18001ec8d  nop     dword ptr [rax+rax+00h]
0x18001ec92  mov     ebx, eax
0x18001ec94  test    eax, eax
0x18001ec96  jle     short loc_18001ECA1
0x18001ec98  movzx   ebx, ax
0x18001ec9b  or      ebx, 80070000h
0x18001eca1  test    ebx, ebx
0x18001eca3  jz      loc_18001ED6A
0x18001eca9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ecb0  cmp     rcx, r15
0x18001ecb3  jz      loc_18001ED6A
0x18001ecb9  test    byte ptr [rcx+1Ch], 40h
0x18001ecbd  jz      loc_18001ED6A
0x18001ecc3  mov     edx, 126h
0x18001ecc8  jmp     short loc_18001ECFC
0x18001ecca  call    cs:__imp_GetLastError
0x18001ecd1  nop     dword ptr [rax+rax+00h]
0x18001ecd6  mov     ebx, eax
0x18001ecd8  test    eax, eax
0x18001ecda  jle     short loc_18001ECE5
0x18001ecdc  movzx   ebx, ax
0x18001ecdf  or      ebx, 80070000h
0x18001ece5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ecec  cmp     rcx, r15
0x18001ecef  jz      short loc_18001ED6A
0x18001ecf1  test    byte ptr [rcx+1Ch], 8
0x18001ecf5  jz      short loc_18001ED6A
0x18001ecf7  mov     edx, 125h
0x18001ecfc  mov     r9d, ebx
0x18001ecff  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x18001ed06  mov     rcx, [rcx+10h]
0x18001ed0a  call    WPP_SF_d
0x18001ed0f  jmp     short loc_18001ED6A
0x18001ed11  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ed18  cmp     rcx, r15
0x18001ed1b  jz      short loc_18001ED6A
0x18001ed1d  test    byte ptr [rcx+1Ch], 8
0x18001ed21  jz      short loc_18001ED6A
0x18001ed23  mov     edx, 124h
0x18001ed28  jmp     short loc_18001ED5A
0x18001ed2a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ed31  cmp     rcx, r15
0x18001ed34  jz      short loc_18001ED6A
0x18001ed36  test    byte ptr [rcx+1Ch], 8
0x18001ed3a  jz      short loc_18001ED6A
0x18001ed3c  mov     edx, 123h
0x18001ed41  jmp     short loc_18001ED5A
0x18001ed43  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ed4a  cmp     rcx, r15
0x18001ed4d  jz      short loc_18001ED6A
0x18001ed4f  test    byte ptr [rcx+1Ch], 8
0x18001ed53  jz      short loc_18001ED6A
0x18001ed55  mov     edx, 122h
0x18001ed5a  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x18001ed61  mov     rcx, [rcx+10h]
0x18001ed65  call    WPP_SF_
0x18001ed6a  mov     rcx, [rbp+57h+var_88]
0x18001ed6e  test    rcx, rcx
0x18001ed71  jz      short loc_18001ED7F
0x18001ed73  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18001ed7a  nop     dword ptr [rax+rax+00h]
0x18001ed7f  test    rsi, rsi
0x18001ed82  jz      short loc_18001ED93
0x18001ed84  mov     rcx, rsi; hObject
0x18001ed87  call    cs:__imp_CloseHandle
0x18001ed8e  nop     dword ptr [rax+rax+00h]
0x18001ed93  test    rdi, rdi
0x18001ed96  jz      short loc_18001EDB8
0x18001ed98  call    cs:__imp_GetProcessHeap
0x18001ed9f  nop     dword ptr [rax+rax+00h]
0x18001eda4  mov     rcx, rax; hHeap
0x18001eda7  mov     r8, rdi; lpMem
0x18001edaa  xor     edx, edx; dwFlags
0x18001edac  call    cs:__imp_HeapFree
0x18001edb3  nop     dword ptr [rax+rax+00h]
0x18001edb8  call    ?FinishWorkImpl@BdeSvcWorkTracking@@AEAAXXZ; BdeSvcWorkTracking::FinishWorkImpl(void)
0x18001edbd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001edc4  cmp     rcx, r15
0x18001edc7  jz      short loc_18001EDE8
0x18001edc9  test    byte ptr [rcx+1Ch], 20h
0x18001edcd  jz      short loc_18001EDE8
0x18001edcf  mov     edx, 127h
0x18001edd4  mov     r9d, ebx
0x18001edd7  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x18001edde  mov     rcx, [rcx+10h]
0x18001ede2  call    WPP_SF_d
0x18001ede7  nop
  ... truncated ...
```
