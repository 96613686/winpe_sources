# MonitorAutoConfigService(void)

- ea: `0x18001b9d8`
- end: `0x18001bc48`
- name: `?MonitorAutoConfigService@@YAXXZ`
- size: `624`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18001b2b4`

## callees

- `0x180001790`
- `0x180011194`
- `0x18001afc0`
- `0x18001b628`
- `0x18001b9d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ba61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bb0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bb82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ba61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bb0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bb82`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001bab1`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001bab1`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001bc1d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001bc1d`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001ba1d`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001ba1d`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18001bb42`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18001bb42`

## pseudocode

```c
void MonitorAutoConfigService(void)
{
  char v0; // bl
  SC_HANDLE v1; // rax
  SC_HANDLE v2; // rsi
  bool v3; // di
  int v4; // r8d
  int v5; // edx
  SC_HANDLE v6; // rcx
  bool v7; // di
  int v8; // edx
  int v9; // r8d
  int pcbBytesNeeded; // [rsp+20h] [rbp-78h]
  int v11; // [rsp+28h] [rbp-70h]
  __int16 v12; // [rsp+30h] [rbp-68h]
  DWORD v13; // [rsp+50h] [rbp-48h] BYREF
  BYTE Buffer[16]; // [rsp+58h] [rbp-40h] BYREF
  __int128 v15; // [rsp+68h] [rbp-30h]
  int v16; // [rsp+78h] [rbp-20h]

  v16 = 0;
  v13 = 0;
  *(_OWORD *)Buffer = 0;
  v0 = 1;
  v15 = 0;
  v1 = OpenSCManagerW(0, 0, 1u);
  v2 = v1;
  if ( v1 )
  {
    *((_QWORD *)pInterfaceGuid + 13) = OpenServiceW(v1, L"wlansvc", 4u);
    v6 = (SC_HANDLE)*((_QWORD *)pInterfaceGuid + 13);
    if ( v6 )
    {
      if ( QueryServiceStatusEx(v6, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &v13) )
      {
        *((_DWORD *)pInterfaceGuid + 4) = 2;
        *((_QWORD *)pInterfaceGuid + 4) = 0;
        *((_QWORD *)pInterfaceGuid + 3) = AutoConfigServiceStatusChangeCallback;
        *((_DWORD *)pInterfaceGuid + 12) = *(_DWORD *)&Buffer[4];
        *((_DWORD *)pInterfaceGuid + 10) = 0;
        AutoConfigServiceStatusChangeCallback((char *)pInterfaceGuid + 16);
        goto LABEL_26;
      }
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
        v0 = 0;
      v7 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( !v0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
LABEL_24:
        BthServStopAutoConfigServiceMonitor();
LABEL_26:
        CloseServiceHandle(v2);
        return;
      }
      GetLastError();
      v12 = 18;
    }
    else
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
        v0 = 0;
      v7 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( !v0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_24;
      GetLastError();
      v12 = 17;
    }
    LOBYTE(v9) = v7;
    LOBYTE(v8) = v0;
    WPP_RECORDER_AND_TRACE_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v8,
      v9,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      pcbBytesNeeded,
      v11,
      v12,
      (__int64)WPP_3ced9c3b7bc93563dc6bccedf26a5837_Traceguids);
    goto LABEL_24;
  }
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
    v0 = 0;
  v3 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    GetLastError();
    LOBYTE(v4) = v3;
    LOBYTE(v5) = v0;
    WPP_RECORDER_AND_TRACE_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v5,
      v4,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      pcbBytesNeeded,
      v11,
      16,
      (__int64)WPP_3ced9c3b7bc93563dc6bccedf26a5837_Traceguids);
  }
  BthServStopAutoConfigServiceMonitor();
}

```

## disassembly

```asm
0x18001b9d8  mov     [rsp+arg_0], rbx
0x18001b9dd  mov     [rsp+arg_8], rsi
0x18001b9e2  push    rdi
0x18001b9e3  sub     rsp, 90h
0x18001b9ea  mov     rax, cs:__security_cookie
0x18001b9f1  xor     rax, rsp
0x18001b9f4  mov     [rsp+98h+var_18], rax
0x18001b9fc  xor     eax, eax
0x18001b9fe  xorps   xmm0, xmm0
0x18001ba01  xor     edx, edx; lpDatabaseName
0x18001ba03  mov     [rsp+98h+var_20], eax
0x18001ba07  xor     ecx, ecx; lpMachineName
0x18001ba09  mov     [rsp+98h+var_48], eax
0x18001ba0d  movups  xmmword ptr [rsp+98h+Buffer], xmm0
0x18001ba12  lea     ebx, [rax+1]
0x18001ba15  mov     r8d, ebx; dwDesiredAccess
0x18001ba18  movups  [rsp+98h+var_30], xmm0
0x18001ba1d  call    cs:__imp_OpenSCManagerW
0x18001ba23  mov     rsi, rax
0x18001ba26  test    rax, rax
0x18001ba29  jnz     short loc_18001BAA1
0x18001ba2b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ba32  lea     rax, WPP_GLOBAL_Control
0x18001ba39  cmp     rcx, rax
0x18001ba3c  jz      short loc_18001BA44
0x18001ba3e  cmp     byte ptr [rcx+19h], 3
0x18001ba42  jnb     short loc_18001BA46
0x18001ba44  xor     bl, bl
0x18001ba46  lea     rax, WPP_RECORDER_INITIALIZED
0x18001ba4d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18001ba54  setnz   dil
0x18001ba58  test    bl, bl
0x18001ba5a  jnz     short loc_18001BA61
0x18001ba5c  test    dil, dil
0x18001ba5f  jz      short loc_18001BA97
0x18001ba61  call    cs:__imp_GetLastError
0x18001ba67  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ba6e  mov     r8b, dil
0x18001ba71  mov     [rsp+98h+var_50], eax
0x18001ba75  mov     dl, bl
0x18001ba77  lea     rax, WPP_3ced9c3b7bc93563dc6bccedf26a5837_Traceguids
0x18001ba7e  mov     [rsp+98h+var_60], rax
0x18001ba83  mov     r9, [rcx+28h]
0x18001ba87  mov     rcx, [rcx+10h]
0x18001ba8b  mov     [rsp+98h+var_68], 10h
0x18001ba92  call    WPP_RECORDER_AND_TRACE_SF_sd
0x18001ba97  call    ?BthServStopAutoConfigServiceMonitor@@YAXXZ; BthServStopAutoConfigServiceMonitor(void)
0x18001ba9c  jmp     loc_18001BC23
0x18001baa1  mov     r8d, 4; dwDesiredAccess
0x18001baa7  lea     rdx, aWlansvc; "wlansvc"
0x18001baae  mov     rcx, rsi; hSCManager
0x18001bab1  call    cs:__imp_OpenServiceW
0x18001bab7  mov     rcx, cs:pInterfaceGuid
0x18001babe  mov     [rcx+68h], rax
0x18001bac2  mov     rax, cs:pInterfaceGuid
0x18001bac9  mov     rcx, [rax+68h]; hService
0x18001bacd  test    rcx, rcx
0x18001bad0  jnz     short loc_18001BB2B
0x18001bad2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bad9  lea     rax, WPP_GLOBAL_Control
0x18001bae0  cmp     rcx, rax
0x18001bae3  jz      short loc_18001BAEB
0x18001bae5  cmp     byte ptr [rcx+19h], 3
0x18001bae9  jnb     short loc_18001BAED
0x18001baeb  xor     bl, bl
0x18001baed  lea     rax, WPP_RECORDER_INITIALIZED
0x18001baf4  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18001bafb  setnz   dil
0x18001baff  test    bl, bl
0x18001bb01  jnz     short loc_18001BB0C
0x18001bb03  test    dil, dil
0x18001bb06  jz      loc_18001BBB8
0x18001bb0c  call    cs:__imp_GetLastError
0x18001bb12  mov     [rsp+98h+var_50], eax
0x18001bb16  lea     rax, WPP_3ced9c3b7bc93563dc6bccedf26a5837_Traceguids
0x18001bb1d  mov     [rsp+98h+var_60], rax
0x18001bb22  mov     [rsp+98h+var_68], 11h
0x18001bb29  jmp     short loc_18001BB9F
0x18001bb2b  lea     rax, [rsp+98h+var_48]
0x18001bb30  mov     r9d, 24h ; '$'; cbBufSize
0x18001bb36  lea     r8, [rsp+98h+Buffer]; lpBuffer
0x18001bb3b  mov     [rsp+98h+pcbBytesNeeded], rax; pcbBytesNeeded
0x18001bb40  xor     edx, edx; InfoLevel
0x18001bb42  call    cs:__imp_QueryServiceStatusEx
0x18001bb48  test    eax, eax
0x18001bb4a  jnz     short loc_18001BBBF
0x18001bb4c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bb53  lea     rax, WPP_GLOBAL_Control
0x18001bb5a  cmp     rcx, rax
0x18001bb5d  jz      short loc_18001BB65
0x18001bb5f  cmp     byte ptr [rcx+19h], 3
0x18001bb63  jnb     short loc_18001BB67
0x18001bb65  xor     bl, bl
0x18001bb67  lea     rax, WPP_RECORDER_INITIALIZED
0x18001bb6e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18001bb75  setnz   dil
0x18001bb79  test    bl, bl
0x18001bb7b  jnz     short loc_18001BB82
0x18001bb7d  test    dil, dil
0x18001bb80  jz      short loc_18001BBB8
0x18001bb82  call    cs:__imp_GetLastError
0x18001bb88  mov     [rsp+98h+var_50], eax
0x18001bb8c  lea     rax, WPP_3ced9c3b7bc93563dc6bccedf26a5837_Traceguids
0x18001bb93  mov     [rsp+98h+var_60], rax
0x18001bb98  mov     [rsp+98h+var_68], 12h
0x18001bb9f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bba6  mov     r8b, dil
0x18001bba9  mov     dl, bl
0x18001bbab  mov     r9, [rcx+28h]
0x18001bbaf  mov     rcx, [rcx+10h]
0x18001bbb3  call    WPP_RECORDER_AND_TRACE_SF_sd
0x18001bbb8  call    ?BthServStopAutoConfigServiceMonitor@@YAXXZ; BthServStopAutoConfigServiceMonitor(void)
0x18001bbbd  jmp     short loc_18001BC1A
0x18001bbbf  mov     rax, cs:pInterfaceGuid
0x18001bbc6  lea     rcx, ?AutoConfigServiceStatusChangeCallback@@YAXPEAX@Z; AutoConfigServiceStatusChangeCallback(void *)
0x18001bbcd  mov     dword ptr [rax+10h], 2
0x18001bbd4  mov     rax, cs:pInterfaceGuid
0x18001bbdb  mov     qword ptr [rax+20h], 0
0x18001bbe3  mov     rax, cs:pInterfaceGuid
0x18001bbea  mov     [rax+18h], rcx
0x18001bbee  mov     rax, cs:pInterfaceGuid
0x18001bbf5  mov     ecx, dword ptr [rsp+98h+Buffer+4]
0x18001bbf9  mov     [rax+30h], ecx
0x18001bbfc  mov     rax, cs:pInterfaceGuid
0x18001bc03  mov     dword ptr [rax+28h], 0
0x18001bc0a  mov     rcx, cs:pInterfaceGuid
0x18001bc11  add     rcx, 10h; void *
0x18001bc15  call    ?AutoConfigServiceStatusChangeCallback@@YAXPEAX@Z; AutoConfigServiceStatusChangeCallback(void *)
0x18001bc1a  mov     rcx, rsi; hSCObject
0x18001bc1d  call    cs:__imp_CloseServiceHandle
0x18001bc23  mov     rcx, [rsp+98h+var_18]
0x18001bc2b  xor     rcx, rsp; StackCookie
0x18001bc2e  call    __security_check_cookie
0x18001bc33  lea     r11, [rsp+98h+var_8]
0x18001bc3b  mov     rbx, [r11+10h]
0x18001bc3f  mov     rsi, [r11+18h]
0x18001bc43  mov     rsp, r11
0x18001bc46  pop     rdi
0x18001bc47  retn
```
