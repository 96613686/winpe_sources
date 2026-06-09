# CSmsDeviceManager::StartMonitoringWwanService(void)

- ea: `0x180042294`
- end: `0x180042439`
- name: `?StartMonitoringWwanService@CSmsDeviceManager@@AEAAJXZ`
- size: `421`
- prototype: `__int64 __fastcall(CSmsDeviceManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800442e0`

## callees

- `0x180003a60`
- `0x180042294`
- `0x180051420`
- `0x180051628`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800422e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042320`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800422e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042320`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180042312`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180042312`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180042401`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004240f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180042401`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004240f`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800422d6`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800422d6`
- `api-ms-win-service-private-l1-1-0!UnsubscribeServiceChangeNotifications` at `0x1800423f3`
- `api-ms-win-service-private-l1-1-0!UnsubscribeServiceChangeNotifications` at `0x1800423f3`
- `api-ms-win-service-private-l1-1-0!SubscribeServiceChangeNotifications` at `0x180042371`
- `api-ms-win-service-private-l1-1-0!SubscribeServiceChangeNotifications` at `0x180042371`

## string_xrefs

- `0x180042344`: `CSmsDeviceManager::StartMonitoringWwanService`
- `0x1800423dd`: `CSmsDeviceManager::StartMonitoringWwanService`
- `0x180042335`: `OpenService for Wwan Service failed`
- `0x1800423d1`: `Wwan Service change monitor running`
- `0x180042388`: `NotifyServiceStatusChange failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSmsDeviceManager::StartMonitoringWwanService(CSmsDeviceManager *this)
{
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // rbp
  SC_HANDLE v4; // rdi
  signed int v5; // eax
  unsigned int v6; // ebx
  signed int LastError; // eax
  int v8; // eax
  __int64 v9; // rdx
  __int64 v11; // [rsp+30h] [rbp-38h] BYREF
  WCHAR ServiceName[8]; // [rsp+38h] [rbp-30h] BYREF

  wcscpy(ServiceName, L"wwansvc");
  v11 = 0;
  v2 = OpenSCManagerW(0, 0, 1u);
  v3 = v2;
  if ( v2 )
  {
    v4 = OpenServiceW(v2, ServiceName, 0x14u);
    if ( v4 )
    {
      v8 = SubscribeServiceChangeNotifications(v4, 2, CSmsDeviceManager::s_ServiceStatusNotification, this, &v11);
      v6 = v8;
      if ( v8 )
      {
        if ( v8 > 0 )
          v6 = (unsigned __int16)v8 | 0x80070000;
        LogSmsRouterError(
          "CSmsDeviceManager::StartMonitoringWwanService",
          0x25Bu,
          v6,
          "NotifyServiceStatusChange failed");
      }
      else
      {
        v6 = 0;
        (**((void (__fastcall ***)(char *))this + 12))((char *)this + 96);
        if ( !*((_DWORD *)this + 11) )
        {
          v9 = *((_QWORD *)this + 11);
          *((_QWORD *)this + 11) = v11;
          v11 = v9;
        }
        (*(void (__fastcall **)(char *))(*((_QWORD *)this + 12) + 8LL))((char *)this + 96);
        LogSmsRouterInfo("CSmsDeviceManager::StartMonitoringWwanService", 0x269u, "Wwan Service change monitor running");
      }
    }
    else
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      LogSmsRouterError(
        "CSmsDeviceManager::StartMonitoringWwanService",
        0x24Du,
        v6,
        "OpenService for Wwan Service failed");
    }
  }
  else
  {
    v4 = 0;
    v5 = GetLastError();
    v6 = v5;
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
  }
  if ( v11 )
    UnsubscribeServiceChangeNotifications();
  if ( v4 )
    CloseServiceHandle(v4);
  if ( v3 )
    CloseServiceHandle(v3);
  return v6;
}

```

## disassembly

```asm
0x180042294  mov     [rsp+arg_8], rbx
0x180042299  mov     [rsp+arg_10], rbp
0x18004229e  push    rsi
0x18004229f  push    rdi
0x1800422a0  push    r14
0x1800422a2  sub     rsp, 50h
0x1800422a6  mov     rax, cs:__security_cookie
0x1800422ad  xor     rax, rsp
0x1800422b0  mov     [rsp+68h+var_20], rax
0x1800422b5  mov     rsi, rcx
0x1800422b8  movups  xmm0, xmmword ptr cs:aWwansvc; "wwansvc"
0x1800422bf  movdqu  xmmword ptr [rsp+68h+ServiceName], xmm0
0x1800422c5  mov     [rsp+68h+var_38], 0
0x1800422ce  xor     edx, edx; lpDatabaseName
0x1800422d0  xor     ecx, ecx; lpMachineName
0x1800422d2  lea     r8d, [rdx+1]; dwDesiredAccess
0x1800422d6  call    cs:__imp_OpenSCManagerW
0x1800422dc  mov     rbp, rax
0x1800422df  test    rax, rax
0x1800422e2  jnz     short loc_180042304
0x1800422e4  xor     edi, edi
0x1800422e6  call    cs:__imp_GetLastError
0x1800422ec  mov     ebx, eax
0x1800422ee  test    eax, eax
0x1800422f0  jle     loc_1800423E9
0x1800422f6  movzx   ebx, ax
0x1800422f9  or      ebx, 80070000h
0x1800422ff  jmp     loc_1800423E9
0x180042304  mov     r8d, 14h; dwDesiredAccess
0x18004230a  lea     rdx, [rsp+68h+ServiceName]; lpServiceName
0x18004230f  mov     rcx, rbp; hSCManager
0x180042312  call    cs:__imp_OpenServiceW
0x180042318  mov     rdi, rax
0x18004231b  test    rax, rax
0x18004231e  jnz     short loc_180042355
0x180042320  call    cs:__imp_GetLastError
0x180042326  mov     ebx, eax
0x180042328  test    eax, eax
0x18004232a  jle     short loc_180042335
0x18004232c  movzx   ebx, ax
0x18004232f  or      ebx, 80070000h
0x180042335  lea     r9, aOpenserviceFor; "OpenService for Wwan Service failed"
0x18004233c  mov     edx, 24Dh; unsigned int
0x180042341  mov     r8d, ebx; int
0x180042344  lea     rcx, aCsmsdevicemana; "CSmsDeviceManager::StartMonitoringWwanS"...
0x18004234b  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x180042350  jmp     loc_1800423E9
0x180042355  lea     rax, [rsp+68h+var_38]
0x18004235a  mov     [rsp+68h+var_48], rax
0x18004235f  mov     r9, rsi
0x180042362  lea     r8, ?s_ServiceStatusNotification@CSmsDeviceManager@@CAXKPEAX@Z; CSmsDeviceManager::s_ServiceStatusNotification(ulong,void *)
0x180042369  mov     edx, 2
0x18004236e  mov     rcx, rdi
0x180042371  call    cs:__imp_SubscribeServiceChangeNotifications
0x180042377  mov     ebx, eax
0x180042379  test    eax, eax
0x18004237b  jz      short loc_180042396
0x18004237d  jle     short loc_180042388
0x18004237f  movzx   ebx, ax
0x180042382  or      ebx, 80070000h
0x180042388  lea     r9, aNotifyservices; "NotifyServiceStatusChange failed"
0x18004238f  mov     edx, 25Bh
0x180042394  jmp     short loc_180042341
0x180042396  xor     ebx, ebx
0x180042398  lea     r14, [rsi+60h]
0x18004239c  mov     rax, [r14]
0x18004239f  mov     rcx, r14
0x1800423a2  mov     rax, [rax]
0x1800423a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800423aa  cmp     [rsi+2Ch], ebx
0x1800423ad  jnz     short loc_1800423C1
0x1800423af  mov     rdx, [rsi+58h]
0x1800423b3  mov     rax, [rsp+68h+var_38]
0x1800423b8  mov     [rsi+58h], rax
0x1800423bc  mov     [rsp+68h+var_38], rdx
0x1800423c1  mov     rax, [r14]
0x1800423c4  mov     rcx, r14
0x1800423c7  mov     rax, [rax+8]
0x1800423cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800423d0  nop
0x1800423d1  lea     r8, aWwanServiceCha; "Wwan Service change monitor running"
0x1800423d8  mov     edx, 269h; unsigned int
0x1800423dd  lea     rcx, aCsmsdevicemana; "CSmsDeviceManager::StartMonitoringWwanS"...
0x1800423e4  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x1800423e9  mov     rcx, [rsp+68h+var_38]
0x1800423ee  test    rcx, rcx
0x1800423f1  jz      short loc_1800423F9
0x1800423f3  call    cs:__imp_UnsubscribeServiceChangeNotifications
0x1800423f9  test    rdi, rdi
0x1800423fc  jz      short loc_180042407
0x1800423fe  mov     rcx, rdi; hSCObject
0x180042401  call    cs:__imp_CloseServiceHandle
0x180042407  test    rbp, rbp
0x18004240a  jz      short loc_180042415
0x18004240c  mov     rcx, rbp; hSCObject
0x18004240f  call    cs:__imp_CloseServiceHandle
0x180042415  mov     eax, ebx
0x180042417  mov     rcx, [rsp+68h+var_20]
0x18004241c  xor     rcx, rsp; StackCookie
0x18004241f  call    __security_check_cookie
0x180042424  lea     r11, [rsp+68h+var_18]
0x180042429  mov     rbx, [r11+28h]
0x18004242d  mov     rbp, [r11+30h]
0x180042431  mov     rsp, r11
0x180042434  pop     r14
0x180042436  pop     rdi
0x180042437  pop     rsi
0x180042438  retn
```
