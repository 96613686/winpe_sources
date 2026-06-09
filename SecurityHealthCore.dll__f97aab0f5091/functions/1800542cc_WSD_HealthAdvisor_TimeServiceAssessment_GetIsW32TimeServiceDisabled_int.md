# WSD::HealthAdvisor::TimeServiceAssessment::GetIsW32TimeServiceDisabled(int *)

- ea: `0x1800542cc`
- end: `0x1800544d5`
- name: `?GetIsW32TimeServiceDisabled@TimeServiceAssessment@HealthAdvisor@WSD@@QEAAJPEAH@Z`
- size: `521`
- prototype: `__int64 __fastcall(WSD::HealthAdvisor::TimeServiceAssessment *__hidden this, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180054520`

## callees

- `0x180004710`
- `0x18000d7fc`
- `0x1800542cc`
- `0x1800e1a1c`
- `0x1800e1a88`
- `0x1800e3e20`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180054418`
- `KERNEL32!GetLastError` at `0x180054418`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180054366`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800543d1`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800543e1`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18005446a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180054478`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180054498`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800544a6`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180054366`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800543d1`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800543e1`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18005446a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180054478`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180054498`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800544a6`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18005440e`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18005440e`

## pseudocode

```c
__int64 __fastcall WSD::HealthAdvisor::TimeServiceAssessment::GetIsW32TimeServiceDisabled(
        WSD::HealthAdvisor::TimeServiceAssessment *this,
        int *a2,
        unsigned int a3,
        const unsigned __int16 *a4)
{
  int v5; // eax
  unsigned int v6; // ebx
  SC_HANDLE v8; // rbx
  int v9; // eax
  unsigned int v10; // edi
  SC_HANDLE v11; // rdi
  signed int LastError; // eax
  unsigned int v13; // esi
  const unsigned __int16 *pcbBytesNeeded; // [rsp+20h] [rbp-E0h] BYREF
  SC_HANDLE hSCObject; // [rsp+28h] [rbp-D8h] BYREF
  SC_HANDLE hService[2]; // [rsp+30h] [rbp-D0h] BYREF
  _QUERY_SERVICE_CONFIGW ServiceConfig; // [rsp+40h] [rbp-C0h] BYREF

  *a2 = 0;
  hService[0] = 0;
  hSCObject = 0;
  v5 = CommonUtil::HrOpenSCManager((CommonUtil *)&hSCObject, (struct SC_HANDLE__ **)a2, a3, a4, pcbBytesNeeded);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v8 = hSCObject;
    v9 = CommonUtil::HrOpenService(
           (CommonUtil *)hService,
           (struct SC_HANDLE__ **)hSCObject,
           (struct SC_HANDLE__ *)L"w32time",
           (const unsigned __int16 *)5,
           (unsigned int)pcbBytesNeeded);
    v10 = v9;
    if ( v9 >= 0 )
    {
      v11 = hService[0];
      LODWORD(pcbBytesNeeded) = 0;
      if ( QueryServiceConfigW(hService[0], &ServiceConfig, 0x2000u, (LPDWORD)&pcbBytesNeeded) )
        goto LABEL_29;
      LastError = GetLastError();
      v13 = LastError;
      if ( LastError > 0 )
        v13 = (unsigned __int16)LastError | 0x80070000;
      if ( (v13 & 0x80000000) == 0 )
      {
LABEL_29:
        if ( ServiceConfig.dwStartType == 4 )
          *a2 = 1;
        if ( v8 )
          CloseServiceHandle(v8);
        if ( v11 )
          CloseServiceHandle(v11);
        return 0;
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_9b08f8b0759d3d135b02c3b820815f14_Traceguids, v13);
        if ( v8 )
          CloseServiceHandle(v8);
        if ( v11 )
          CloseServiceHandle(v11);
        return v13;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          WPP_9b08f8b0759d3d135b02c3b820815f14_Traceguids,
          (unsigned int)v9);
      if ( v8 )
        CloseServiceHandle(v8);
      if ( hService[0] )
        CloseServiceHandle(hService[0]);
      return v10;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        WPP_9b08f8b0759d3d135b02c3b820815f14_Traceguids,
        (unsigned int)v5);
    if ( hSCObject )
      CloseServiceHandle(hSCObject);
    return v6;
  }
}

```

## disassembly

```asm
0x1800542cc  mov     [rsp-8+arg_0], rbx
0x1800542d1  mov     [rsp-8+arg_10], rsi
0x1800542d6  push    rbp
0x1800542d7  push    rdi
0x1800542d8  push    r14
0x1800542da  lea     rbp, [rsp-1F50h]
0x1800542e2  mov     eax, 2050h
0x1800542e7  call    _alloca_probe
0x1800542ec  sub     rsp, rax
0x1800542ef  mov     rax, cs:__security_cookie
0x1800542f6  xor     rax, rsp
0x1800542f9  mov     [rbp+1F60h+var_20], rax
0x180054300  lea     rcx, [rsp+2060h+hSCObject]; this
0x180054305  mov     dword ptr [rdx], 0
0x18005430b  mov     r14, rdx
0x18005430e  mov     [rsp+2060h+hService], 0
0x180054317  mov     [rsp+2060h+hSCObject], 0
0x180054320  call    ?HrOpenSCManager@CommonUtil@@YAJPEAPEAUSC_HANDLE__@@KPEBG1@Z; CommonUtil::HrOpenSCManager(SC_HANDLE__ * *,ulong,ushort const *,ushort const *)
0x180054325  mov     ebx, eax
0x180054327  test    eax, eax
0x180054329  jns     short loc_180054373
0x18005432b  mov     rcx, cs:WPP_GLOBAL_Control
0x180054332  lea     rdx, WPP_GLOBAL_Control
0x180054339  cmp     rcx, rdx
0x18005433c  jz      short loc_18005435C
0x18005433e  test    byte ptr [rcx+1Ch], 1
0x180054342  jz      short loc_18005435C
0x180054344  mov     rcx, [rcx+10h]
0x180054348  lea     r8, WPP_9b08f8b0759d3d135b02c3b820815f14_Traceguids
0x18005434f  mov     edx, 0Fh
0x180054354  mov     r9d, eax
0x180054357  call    WPP_SF_d
0x18005435c  mov     rcx, [rsp+2060h+hSCObject]; hSCObject
0x180054361  test    rcx, rcx
0x180054364  jz      short loc_18005436C
0x180054366  call    cs:__imp_CloseServiceHandle
0x18005436c  mov     eax, ebx
0x18005436e  jmp     loc_1800544AE
0x180054373  mov     rbx, [rsp+2060h+hSCObject]
0x180054378  lea     r8, ServiceName; "w32time"
0x18005437f  mov     rdx, rbx; struct SC_HANDLE__ **
0x180054382  lea     rcx, [rsp+2060h+hService]; this
0x180054387  mov     r9d, 5; unsigned __int16 *
0x18005438d  call    ?HrOpenService@CommonUtil@@YAJPEAPEAUSC_HANDLE__@@PEAU2@PEBGK@Z; CommonUtil::HrOpenService(SC_HANDLE__ * *,SC_HANDLE__ *,ushort const *,ulong)
0x180054392  mov     edi, eax
0x180054394  test    eax, eax
0x180054396  jns     short loc_1800543EE
0x180054398  mov     rcx, cs:WPP_GLOBAL_Control
0x18005439f  lea     rdx, WPP_GLOBAL_Control
0x1800543a6  cmp     rcx, rdx
0x1800543a9  jz      short loc_1800543C9
0x1800543ab  test    byte ptr [rcx+1Ch], 1
0x1800543af  jz      short loc_1800543C9
0x1800543b1  mov     rcx, [rcx+10h]
0x1800543b5  lea     r8, WPP_9b08f8b0759d3d135b02c3b820815f14_Traceguids
0x1800543bc  mov     edx, 10h
0x1800543c1  mov     r9d, eax
0x1800543c4  call    WPP_SF_d
0x1800543c9  test    rbx, rbx
0x1800543cc  jz      short loc_1800543D7
0x1800543ce  mov     rcx, rbx; hSCObject
0x1800543d1  call    cs:__imp_CloseServiceHandle
0x1800543d7  mov     rcx, [rsp+2060h+hService]; hSCObject
0x1800543dc  test    rcx, rcx
0x1800543df  jz      short loc_1800543E7
0x1800543e1  call    cs:__imp_CloseServiceHandle
0x1800543e7  mov     eax, edi
0x1800543e9  jmp     loc_1800544AE
0x1800543ee  mov     rdi, [rsp+2060h+hService]
0x1800543f3  lea     r9, [rsp+2060h+pcbBytesNeeded]; pcbBytesNeeded
0x1800543f8  mov     rcx, rdi; hService
0x1800543fb  mov     dword ptr [rsp+2060h+pcbBytesNeeded], 0
0x180054403  mov     r8d, 2000h; cbBufSize
0x180054409  lea     rdx, [rsp+2060h+ServiceConfig]; lpServiceConfig
0x18005440e  call    cs:__imp_QueryServiceConfigW
0x180054414  test    eax, eax
0x180054416  jnz     short loc_180054482
0x180054418  call    cs:__imp_GetLastError
0x18005441e  mov     esi, eax
0x180054420  test    eax, eax
0x180054422  jle     short loc_18005442D
0x180054424  movzx   esi, ax
0x180054427  or      esi, 80070000h
0x18005442d  test    esi, esi
0x18005442f  jns     short loc_180054482
0x180054431  mov     rcx, cs:WPP_GLOBAL_Control
0x180054438  lea     rdx, WPP_GLOBAL_Control
0x18005443f  cmp     rcx, rdx
0x180054442  jz      short loc_180054462
0x180054444  test    byte ptr [rcx+1Ch], 1
0x180054448  jz      short loc_180054462
0x18005444a  mov     rcx, [rcx+10h]
0x18005444e  lea     r8, WPP_9b08f8b0759d3d135b02c3b820815f14_Traceguids
0x180054455  mov     edx, 11h
0x18005445a  mov     r9d, esi
0x18005445d  call    WPP_SF_d
0x180054462  test    rbx, rbx
0x180054465  jz      short loc_180054470
0x180054467  mov     rcx, rbx; hSCObject
0x18005446a  call    cs:__imp_CloseServiceHandle
0x180054470  test    rdi, rdi
0x180054473  jz      short loc_18005447E
0x180054475  mov     rcx, rdi; hSCObject
0x180054478  call    cs:__imp_CloseServiceHandle
0x18005447e  mov     eax, esi
0x180054480  jmp     short loc_1800544AE
0x180054482  cmp     [rsp+2060h+ServiceConfig.dwStartType], 4
0x180054487  jnz     short loc_180054490
0x180054489  mov     dword ptr [r14], 1
0x180054490  test    rbx, rbx
0x180054493  jz      short loc_18005449E
0x180054495  mov     rcx, rbx; hSCObject
0x180054498  call    cs:__imp_CloseServiceHandle
0x18005449e  test    rdi, rdi
0x1800544a1  jz      short loc_1800544AC
0x1800544a3  mov     rcx, rdi; hSCObject
0x1800544a6  call    cs:__imp_CloseServiceHandle
0x1800544ac  xor     eax, eax
0x1800544ae  mov     rcx, [rbp+1F60h+var_20]
0x1800544b5  xor     rcx, rsp; StackCookie
0x1800544b8  call    __security_check_cookie
0x1800544bd  lea     r11, [rsp+2060h+var_10]
0x1800544c5  mov     rbx, [r11+20h]
0x1800544c9  mov     rsi, [r11+30h]
0x1800544cd  mov     rsp, r11
0x1800544d0  pop     r14
0x1800544d2  pop     rdi
0x1800544d3  pop     rbp
0x1800544d4  retn
```
