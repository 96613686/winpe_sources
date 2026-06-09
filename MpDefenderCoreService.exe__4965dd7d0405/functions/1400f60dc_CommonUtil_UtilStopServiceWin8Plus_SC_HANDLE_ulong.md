# CommonUtil::UtilStopServiceWin8Plus(SC_HANDLE__ *,ulong)

- ea: `0x1400f60dc`
- end: `0x1400f6646`
- name: `?UtilStopServiceWin8Plus@CommonUtil@@YAJPEAUSC_HANDLE__@@K@Z`
- size: `1386`
- prototype: `__int64 __fastcall(SC_HANDLE hService, struct SC_HANDLE__ *, unsigned int)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400c49c8`

## callees

- `0x14000b2f0`
- `0x14000b460`
- `0x1400130b0`
- `0x1400144dc`
- `0x140015e60`
- `0x1400162c0`
- `0x140017738`
- `0x140017990`
- `0x14003a5c0`
- `0x14007d210`
- `0x140085d94`
- `0x1400934f8`
- `0x1400bb460`
- `0x1400f5934`
- `0x1400f60dc`
- `0x1400f6648`
- `0x1400f677c`
- `0x140166990`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1400f6612`
- `KERNEL32!CloseHandle` at `0x1400f6612`
- `ADVAPI32!QueryServiceConfigW` at `0x1400f627d`
- `ADVAPI32!QueryServiceConfigW` at `0x1400f6392`
- `ADVAPI32!QueryServiceConfigW` at `0x1400f6485`
- `ADVAPI32!QueryServiceConfigW` at `0x1400f651f`
- `ADVAPI32!QueryServiceConfigW` at `0x1400f65a8`
- `ADVAPI32!QueryServiceConfigW` at `0x1400f627d`
- `ADVAPI32!QueryServiceConfigW` at `0x1400f6392`
- `ADVAPI32!QueryServiceConfigW` at `0x1400f6485`
- `ADVAPI32!QueryServiceConfigW` at `0x1400f651f`
- `ADVAPI32!QueryServiceConfigW` at `0x1400f65a8`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilStopServiceWin8Plus(SC_HANDLE hService, struct SC_HANDLE__ *a2)
{
  __int64 v2; // r13
  int Event; // eax
  signed int v5; // ebx
  int v6; // eax
  CommonUtil *v7; // rcx
  struct SC_HANDLE__ *v8; // r8
  unsigned __int64 v9; // r15
  LPWSTR v10; // rdi
  unsigned int v11; // edx
  unsigned int v12; // r8d
  struct _SERVICE_STATUS *v13; // r9
  __int64 v14; // rcx
  const wchar_t *v15; // rbx
  int v16; // eax
  LPWSTR lpDisplayName; // rax
  unsigned __int64 SystemTimeAsUlong64; // rax
  char v19; // r13
  unsigned __int64 v20; // rdx
  int v21; // r8d
  unsigned int v22; // edx
  unsigned int v23; // eax
  const struct _SECURITY_ATTRIBUTES *v25; // [rsp+28h] [rbp-D8h]
  struct _QUERY_SERVICE_CONFIGW ServiceConfig[8]; // [rsp+60h] [rbp-A0h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+260h] [rbp+160h] BYREF
  DWORD v28; // [rsp+280h] [rbp+180h] BYREF
  DWORD pcbBytesNeeded; // [rsp+284h] [rbp+184h] BYREF
  HANDLE hObject; // [rsp+288h] [rbp+188h] BYREF
  __int64 v31; // [rsp+290h] [rbp+190h] BYREF

  v2 = (unsigned int)a2;
  v28 = (unsigned int)a2;
  hObject = 0;
  Event = CommonUtil::UtilCreateEvent((CommonUtil *)&hObject, 0, 0, 0, 0, v25);
  v5 = Event;
  if ( Event >= 0 )
  {
    v31 = 0;
    v6 = SubscribeServiceChangeNotifications(
           (_DWORD)hService,
           2,
           (unsigned int)&lambda_63c8dcfed8987a08204630dc55e143ad_::_lambda_invoker_cdecl_,
           (_DWORD)hObject,
           (__int64)&v31);
    v5 = v6;
    if ( v6 )
    {
      if ( v6 > 0 )
        v5 = (unsigned __int16)v6 | 0x80070000;
    }
    else
    {
      if ( (_DWORD)v2 == -1 )
        v9 = -1;
      else
        v9 = CommonUtil::UtilGetSystemTimeAsUlong64(v7) + 10000 * v2;
      memset(&ServiceStatus, 0, sizeof(ServiceStatus));
      v10 = (LPWSTR)L"<unknown>";
      while ( 1 )
      {
        v5 = CommonUtil::HrQueryServiceStatus(&ServiceStatus, hService, v8);
        if ( v5 < 0 )
          break;
        v14 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        {
          v15 = CommonUtil::ServiceStateToString((CommonUtil *)ServiceStatus.dwCurrentState, v11);
          memset(ServiceConfig, 0, sizeof(ServiceConfig));
          pcbBytesNeeded = 0;
          if ( !QueryServiceConfigW(hService, ServiceConfig, 0x200u, &pcbBytesNeeded) )
          {
            HrGetLastFailure();
            ServiceConfig[0].lpDisplayName = (LPWSTR)L"<unknown>";
          }
          WPP_SF_SLSLLLLL(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            ServiceStatus.dwServiceType,
            (__int64)v15,
            ServiceStatus.dwControlsAccepted,
            ServiceStatus.dwWin32ExitCode,
            ServiceStatus.dwServiceSpecificExitCode,
            ServiceStatus.dwCheckPoint,
            ServiceStatus.dwWaitHint);
          v14 = WPP_GLOBAL_Control;
        }
        if ( ServiceStatus.dwCurrentState == 4 )
        {
          if ( (ServiceStatus.dwControlsAccepted & 1) == 0 )
          {
            v5 = -2147019873;
            if ( (_UNKNOWN *)v14 != &WPP_GLOBAL_Control && (*(_BYTE *)(v14 + 28) & 1) != 0 )
            {
              memset(ServiceConfig, 0, sizeof(ServiceConfig));
              v28 = 0;
              if ( QueryServiceConfigW(hService, ServiceConfig, 0x200u, &v28) )
              {
                LODWORD(v10) = ServiceConfig[0].lpDisplayName;
              }
              else
              {
                HrGetLastFailure();
                ServiceConfig[0].lpDisplayName = (LPWSTR)L"<unknown>";
              }
              WPP_SF_Sd(
                *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                13,
                (unsigned int)&WPP_1a07eea27bbb3806b3fdf6b25f88669e_Traceguids,
                (_DWORD)v10,
                ServiceStatus.dwControlsAccepted);
            }
            break;
          }
          v16 = CommonUtil::HrControlService(hService, (struct SC_HANDLE__ *)1, &ServiceStatus, v13);
          v5 = v16;
          if ( v16 < 0 )
          {
            if ( (unsigned int)(v16 + 2147023835) > 1 && v16 != -2147023781 )
              break;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
            {
              memset(ServiceConfig, 0, sizeof(ServiceConfig));
              pcbBytesNeeded = 0;
              if ( QueryServiceConfigW(hService, ServiceConfig, 0x200u, &pcbBytesNeeded) )
              {
                lpDisplayName = ServiceConfig[0].lpDisplayName;
              }
              else
              {
                HrGetLastFailure();
                lpDisplayName = (LPWSTR)L"<unknown>";
                ServiceConfig[0].lpDisplayName = (LPWSTR)L"<unknown>";
              }
              WPP_SF_dS(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), (__int64)lpDisplayName);
            }
          }
        }
        else
        {
          if ( ServiceStatus.dwCurrentState == 1 )
          {
            v5 = 0;
            break;
          }
          if ( ServiceStatus.dwCurrentState - 2 > 1 )
          {
            v5 = -2147019873;
            if ( (_UNKNOWN *)v14 != &WPP_GLOBAL_Control && (*(_BYTE *)(v14 + 28) & 1) != 0 )
            {
              memset(ServiceConfig, 0, sizeof(ServiceConfig));
              v28 = 0;
              if ( QueryServiceConfigW(hService, ServiceConfig, 0x200u, &v28) )
              {
                v10 = ServiceConfig[0].lpDisplayName;
              }
              else
              {
                HrGetLastFailure();
                ServiceConfig[0].lpDisplayName = (LPWSTR)L"<unknown>";
              }
              v23 = (unsigned int)CommonUtil::ServiceStateToString((CommonUtil *)ServiceStatus.dwCurrentState, v22);
              WPP_SF_SS(
                *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                15,
                (unsigned int)&WPP_1a07eea27bbb3806b3fdf6b25f88669e_Traceguids,
                v23,
                (__int64)v10);
            }
            break;
          }
        }
        if ( (_DWORD)v2 == -1 )
        {
          v20 = 0xFFFFFFFFLL;
        }
        else
        {
          SystemTimeAsUlong64 = CommonUtil::UtilGetSystemTimeAsUlong64((CommonUtil *)v14);
          v19 = SystemTimeAsUlong64;
          if ( SystemTimeAsUlong64 > v9 )
          {
            v5 = -2147023436;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            {
              _mm_lfence();
              memset(ServiceConfig, 0, sizeof(ServiceConfig));
              v28 = 0;
              if ( QueryServiceConfigW(hService, ServiceConfig, 0x200u, &v28) )
              {
                LODWORD(v10) = ServiceConfig[0].lpDisplayName;
              }
              else
              {
                HrGetLastFailure();
                ServiceConfig[0].lpDisplayName = (LPWSTR)L"<unknown>";
              }
              WPP_SF_Siid(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 16, v21, (_DWORD)v10, v19, v9, 180);
            }
            break;
          }
          LODWORD(v2) = v28;
          v20 = (v9 - SystemTimeAsUlong64 + 9999) / 0x2710;
        }
        CommonUtil::UtilWaitForSingleObject((CommonUtil *)hObject, (void *)v20, v12);
      }
    }
    if ( v31 )
      AddressOfUnsubscribeServiceChangeNotifications();
  }
  else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      10,
      &WPP_1a07eea27bbb3806b3fdf6b25f88669e_Traceguids,
      (unsigned int)Event);
  }
  if ( hObject )
    CloseHandle(hObject);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1400f60dc  mov     [rsp-8+arg_10], rbx
0x1400f60e1  mov     [rsp-8+arg_18], rdi
0x1400f60e6  push    rbp
0x1400f60e7  push    r12
0x1400f60e9  push    r13
0x1400f60eb  push    r14
0x1400f60ed  push    r15
0x1400f60ef  lea     rbp, [rsp-1A0h]
0x1400f60f7  sub     rsp, 2A0h
0x1400f60fe  mov     rax, cs:__security_cookie
0x1400f6105  xor     rax, rsp
0x1400f6108  mov     [rbp+1C0h+var_28], rax
0x1400f610f  mov     r13d, edx
0x1400f6112  mov     r12, rcx
0x1400f6115  xor     edi, edi
0x1400f6117  mov     [rbp+1C0h+var_40], r13d
0x1400f611e  xor     edx, edx; void **
0x1400f6120  mov     [rbp+1C0h+hObject], rdi
0x1400f6127  lea     rcx, [rbp+1C0h+hObject]; this
0x1400f612e  mov     [rsp+2C0h+lpEventAttributes], rdi; lpEventAttributes
0x1400f6133  xor     r9d, r9d; int
0x1400f6136  xor     r8d, r8d; int
0x1400f6139  call    ?UtilCreateEvent@CommonUtil@@YAJPEAPEAXHHPEB_WPEBU_SECURITY_ATTRIBUTES@@@Z; CommonUtil::UtilCreateEvent(void * *,int,int,wchar_t const *,_SECURITY_ATTRIBUTES const *)
0x1400f613e  mov     ebx, eax
0x1400f6140  test    eax, eax
0x1400f6142  jns     short loc_1400F6180
0x1400f6144  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f614b  lea     r14, WPP_GLOBAL_Control
0x1400f6152  cmp     rcx, r14
0x1400f6155  jz      loc_1400F6606
0x1400f615b  test    byte ptr [rcx+1Ch], 1
0x1400f615f  jz      loc_1400F6606
0x1400f6165  mov     rcx, [rcx+10h]
0x1400f6169  lea     edx, [rdi+0Ah]
0x1400f616c  mov     r9d, eax
0x1400f616f  lea     r8, WPP_1a07eea27bbb3806b3fdf6b25f88669e_Traceguids
0x1400f6176  call    WPP_SF_d
0x1400f617b  jmp     loc_1400F6606
0x1400f6180  mov     r9, [rbp+1C0h+hObject]
0x1400f6187  lea     rax, [rbp+1C0h+var_30]
0x1400f618e  lea     r8, _lambda_63c8dcfed8987a08204630dc55e143ad____lambda_invoker_cdecl_
0x1400f6195  mov     [rsp+2C0h+lpEventAttributes], rax
0x1400f619a  mov     edx, 2
0x1400f619f  mov     [rbp+1C0h+var_30], rdi
0x1400f61a6  mov     rcx, r12
0x1400f61a9  call    cs:__imp_SubscribeServiceChangeNotifications
0x1400f61af  mov     ebx, eax
0x1400f61b1  test    eax, eax
0x1400f61b3  jz      short loc_1400F61C9
0x1400f61b5  jle     loc_1400F65F4
0x1400f61bb  movzx   ebx, ax
0x1400f61be  or      ebx, 80070000h
0x1400f61c4  jmp     loc_1400F65F4
0x1400f61c9  cmp     r13d, 0FFFFFFFFh
0x1400f61cd  jnz     short loc_1400F61D5
0x1400f61cf  or      r15, 0FFFFFFFFFFFFFFFFh
0x1400f61d3  jmp     short loc_1400F61E4
0x1400f61d5  call    ?UtilGetSystemTimeAsUlong64@CommonUtil@@YA_KXZ; CommonUtil::UtilGetSystemTimeAsUlong64(void)
0x1400f61da  imul    r15, r13, 2710h
0x1400f61e1  add     r15, rax
0x1400f61e4  xor     eax, eax
0x1400f61e6  lea     r14, WPP_GLOBAL_Control
0x1400f61ed  xorps   xmm0, xmm0
0x1400f61f0  mov     qword ptr [rbp+1C0h+ServiceStatus.dwServiceSpecificExitCode], rax
0x1400f61f7  movups  xmmword ptr [rbp+1C0h+ServiceStatus.dwServiceType], xmm0
0x1400f61fe  mov     [rbp+1C0h+ServiceStatus.dwWaitHint], eax
0x1400f6204  lea     rdi, aUnknown_1; "<unknown>"
0x1400f620b  mov     rdx, r12; hService
0x1400f620e  lea     rcx, [rbp+1C0h+ServiceStatus]; lpServiceStatus
0x1400f6215  call    ?HrQueryServiceStatus@CommonUtil@@YAJPEAU_SERVICE_STATUS@@PEAUSC_HANDLE__@@@Z; CommonUtil::HrQueryServiceStatus(_SERVICE_STATUS *,SC_HANDLE__ *)
0x1400f621a  mov     ebx, eax
0x1400f621c  test    eax, eax
0x1400f621e  js      loc_1400F65F4
0x1400f6224  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f622b  cmp     rcx, r14
0x1400f622e  jz      loc_1400F62F6
0x1400f6234  test    byte ptr [rcx+1Ch], 4
0x1400f6238  jz      loc_1400F62F6
0x1400f623e  mov     ecx, [rbp+1C0h+ServiceStatus.dwCurrentState]; this
0x1400f6244  call    ?ServiceStateToString@CommonUtil@@YAPEB_WK@Z; CommonUtil::ServiceStateToString(ulong)
0x1400f6249  xor     edx, edx; Val
0x1400f624b  lea     rcx, [rsp+2C0h+ServiceConfig]; void *
0x1400f6250  mov     r8d, 200h; Size
0x1400f6256  mov     rbx, rax
0x1400f6259  call    memset
0x1400f625e  lea     r9, [rbp+1C0h+pcbBytesNeeded]; pcbBytesNeeded
0x1400f6265  mov     [rbp+1C0h+pcbBytesNeeded], 0
0x1400f626f  mov     r8d, 200h; cbBufSize
0x1400f6275  lea     rdx, [rsp+2C0h+ServiceConfig]; lpServiceConfig
0x1400f627a  mov     rcx, r12; hService
0x1400f627d  call    cs:__imp_QueryServiceConfigW
0x1400f6283  test    eax, eax
0x1400f6285  jnz     short loc_1400F6295
0x1400f6287  call    HrGetLastFailure
0x1400f628c  mov     r9, rdi
0x1400f628f  mov     [rbp+1C0h+ServiceConfig.lpDisplayName], rdi
0x1400f6293  jmp     short loc_1400F6299
0x1400f6295  mov     r9, [rbp+1C0h+ServiceConfig.lpDisplayName]
0x1400f6299  mov     eax, [rbp+1C0h+ServiceStatus.dwWaitHint]
0x1400f629f  mov     edx, 0Ch
0x1400f62a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f62ab  mov     dword ptr [rsp+2C0h+var_270], eax; char
0x1400f62af  mov     eax, [rbp+1C0h+ServiceStatus.dwCheckPoint]
0x1400f62b5  mov     dword ptr [rsp+2C0h+var_278], eax; char
0x1400f62b9  mov     eax, [rbp+1C0h+ServiceStatus.dwServiceSpecificExitCode]
0x1400f62bf  mov     rcx, [rcx+10h]; LoggerHandle
0x1400f62c3  mov     dword ptr [rsp+2C0h+var_280], eax; char
0x1400f62c7  mov     eax, [rbp+1C0h+ServiceStatus.dwWin32ExitCode]
0x1400f62cd  mov     dword ptr [rsp+2C0h+var_288], eax; char
0x1400f62d1  mov     eax, [rbp+1C0h+ServiceStatus.dwControlsAccepted]
0x1400f62d7  mov     dword ptr [rsp+2C0h+var_290], eax; char
0x1400f62db  mov     eax, [rbp+1C0h+ServiceStatus.dwServiceType]
0x1400f62e1  mov     [rsp+2C0h+var_298], rbx; __int64
0x1400f62e6  mov     dword ptr [rsp+2C0h+lpEventAttributes], eax; char
0x1400f62ea  call    WPP_SF_SLSLLLLL
0x1400f62ef  mov     rcx, cs:WPP_GLOBAL_Control; this
0x1400f62f6  mov     eax, [rbp+1C0h+ServiceStatus.dwCurrentState]
0x1400f62fc  cmp     eax, 4
0x1400f62ff  jnz     loc_1400F63D4
0x1400f6305  mov     eax, [rbp+1C0h+ServiceStatus.dwControlsAccepted]
0x1400f630b  test    al, 1
0x1400f630d  jz      loc_1400F643C
0x1400f6313  lea     r8, [rbp+1C0h+ServiceStatus]; lpServiceStatus
0x1400f631a  mov     edx, 1; this
0x1400f631f  mov     rcx, r12; hService
0x1400f6322  call    ?HrControlService@CommonUtil@@YAJPEAUSC_HANDLE__@@KPEAU_SERVICE_STATUS@@@Z; CommonUtil::HrControlService(SC_HANDLE__ *,ulong,_SERVICE_STATUS *)
0x1400f6327  mov     ebx, eax
0x1400f6329  test    eax, eax
0x1400f632b  jns     loc_1400F63E9
0x1400f6331  add     eax, 7FF8FBDBh
0x1400f6336  cmp     eax, 1
0x1400f6339  jbe     short loc_1400F6347
0x1400f633b  cmp     ebx, 8007045Bh
0x1400f6341  jnz     loc_1400F65F4
0x1400f6347  mov     rax, cs:WPP_GLOBAL_Control
0x1400f634e  cmp     rax, r14
0x1400f6351  jz      loc_1400F63E9
0x1400f6357  test    byte ptr [rax+1Ch], 2
0x1400f635b  jz      loc_1400F63E9
0x1400f6361  xor     edx, edx; Val
0x1400f6363  lea     rcx, [rsp+2C0h+ServiceConfig]; void *
0x1400f6368  mov     r8d, 200h; Size
0x1400f636e  call    memset
0x1400f6373  lea     r9, [rbp+1C0h+pcbBytesNeeded]; pcbBytesNeeded
0x1400f637a  mov     [rbp+1C0h+pcbBytesNeeded], 0
0x1400f6384  mov     r8d, 200h; cbBufSize
0x1400f638a  lea     rdx, [rsp+2C0h+ServiceConfig]; lpServiceConfig
0x1400f638f  mov     rcx, r12; hService
0x1400f6392  call    cs:__imp_QueryServiceConfigW
0x1400f6398  test    eax, eax
0x1400f639a  jnz     short loc_1400F63AA
0x1400f639c  call    HrGetLastFailure
0x1400f63a1  mov     rax, rdi
0x1400f63a4  mov     [rbp+1C0h+ServiceConfig.lpDisplayName], rax
0x1400f63a8  jmp     short loc_1400F63AE
0x1400f63aa  mov     rax, [rbp+1C0h+ServiceConfig.lpDisplayName]
0x1400f63ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f63b5  lea     r8, WPP_1a07eea27bbb3806b3fdf6b25f88669e_Traceguids
0x1400f63bc  mov     edx, 0Eh
0x1400f63c1  mov     [rsp+2C0h+lpEventAttributes], rax; __int64
0x1400f63c6  mov     r9d, ebx
0x1400f63c9  mov     rcx, [rcx+10h]; LoggerHandle
0x1400f63cd  call    WPP_SF_dS
0x1400f63d2  jmp     short loc_1400F63E9
0x1400f63d4  cmp     eax, 1
0x1400f63d7  jz      loc_1400F65F2
0x1400f63dd  add     eax, 0FFFFFFFEh
0x1400f63e0  cmp     eax, 1
0x1400f63e3  ja      loc_1400F6563
0x1400f63e9  or      eax, 0FFFFFFFFh
0x1400f63ec  cmp     r13d, eax
0x1400f63ef  jz      short loc_1400F6429
0x1400f63f1  call    ?UtilGetSystemTimeAsUlong64@CommonUtil@@YA_KXZ; CommonUtil::UtilGetSystemTimeAsUlong64(void)
0x1400f63f6  mov     r13, rax
0x1400f63f9  cmp     rax, r15
0x1400f63fc  ja      loc_1400F64CC
0x1400f6402  mov     r13d, [rbp+1C0h+var_40]
0x1400f6409  mov     rcx, r15
0x1400f640c  sub     rcx, rax
0x1400f640f  mov     rax, 346DC5D63886594Bh
0x1400f6419  add     rcx, 270Fh
0x1400f6420  mul     rcx
0x1400f6423  shr     rdx, 0Bh
0x1400f6427  jmp     short loc_1400F642B
0x1400f6429  mov     edx, eax; void *
0x1400f642b  mov     rcx, [rbp+1C0h+hObject]; this
0x1400f6432  call    ?UtilWaitForSingleObject@CommonUtil@@YA_NPEAXK@Z; CommonUtil::UtilWaitForSingleObject(void *,ulong)
0x1400f6437  jmp     loc_1400F620B
0x1400f643c  mov     ebx, 8007139Fh
0x1400f6441  cmp     rcx, r14
0x1400f6444  jz      loc_1400F65F4
0x1400f644a  test    byte ptr [rcx+1Ch], 1
0x1400f644e  jz      loc_1400F65F4
0x1400f6454  xor     edx, edx; Val
0x1400f6456  lea     rcx, [rsp+2C0h+ServiceConfig]; void *
0x1400f645b  mov     r8d, 200h; Size
0x1400f6461  call    memset
0x1400f6466  lea     r9, [rbp+1C0h+var_40]; pcbBytesNeeded
0x1400f646d  mov     [rbp+1C0h+var_40], 0
0x1400f6477  mov     r8d, 200h; cbBufSize
0x1400f647d  lea     rdx, [rsp+2C0h+ServiceConfig]; lpServiceConfig
0x1400f6482  mov     rcx, r12; hService
0x1400f6485  call    cs:__imp_QueryServiceConfigW
0x1400f648b  test    eax, eax
0x1400f648d  jnz     short loc_1400F649A
0x1400f648f  call    HrGetLastFailure
0x1400f6494  mov     [rbp+1C0h+ServiceConfig.lpDisplayName], rdi
0x1400f6498  jmp     short loc_1400F649E
0x1400f649a  mov     rdi, [rbp+1C0h+ServiceConfig.lpDisplayName]
0x1400f649e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f64a5  lea     r8, WPP_1a07eea27bbb3806b3fdf6b25f88669e_Traceguids
0x1400f64ac  mov     eax, [rbp+1C0h+ServiceStatus.dwControlsAccepted]
0x1400f64b2  mov     edx, 0Dh
0x1400f64b7  mov     r9, rdi
0x1400f64ba  mov     dword ptr [rsp+2C0h+lpEventAttributes], eax
0x1400f64be  mov     rcx, [rcx+10h]
0x1400f64c2  call    WPP_SF_Sd
0x1400f64c7  jmp     loc_1400F65F4
0x1400f64cc  mov     ebx, 800705B4h
0x1400f64d1  mov     rax, cs:WPP_GLOBAL_Control
0x1400f64d8  cmp     rax, r14
0x1400f64db  jz      loc_1400F65F4
0x1400f64e1  test    byte ptr [rax+1Ch], 1
0x1400f64e5  jz      loc_1400F65F4
0x1400f64eb  lfence
0x1400f64ee  xor     edx, edx; Val
0x1400f64f0  lea     rcx, [rsp+2C0h+ServiceConfig]; void *
0x1400f64f5  mov     r8d, 200h; Size
0x1400f64fb  call    memset
0x1400f6500  lea     r9, [rbp+1C0h+var_40]; pcbBytesNeeded
0x1400f6507  mov     [rbp+1C0h+var_40], 0
0x1400f6511  mov     r8d, 200h; cbBufSize
0x1400f6517  lea     rdx, [rsp+2C0h+ServiceConfig]; lpServiceConfig
0x1400f651c  mov     rcx, r12; hService
0x1400f651f  call    cs:__imp_QueryServiceConfigW
0x1400f6525  test    eax, eax
0x1400f6527  jnz     short loc_1400F6534
0x1400f6529  call    HrGetLastFailure
0x1400f652e  mov     [rbp+1C0h+ServiceConfig.lpDisplayName], rdi
0x1400f6532  jmp     short loc_1400F6538
0x1400f6534  mov     rdi, [rbp+1C0h+ServiceConfig.lpDisplayName]
0x1400f6538  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f653f  mov     edx, 10h
0x1400f6544  mov     dword ptr [rsp+2C0h+var_290], ebx
0x1400f6548  mov     r9, rdi
0x1400f654b  mov     [rsp+2C0h+var_298], r15
0x1400f6550  mov     [rsp+2C0h+lpEventAttributes], r13
0x1400f6555  mov     rcx, [rcx+10h]
0x1400f6559  call    WPP_SF_Siid
0x1400f655e  jmp     loc_1400F65F4
0x1400f6563  mov     ebx, 8007139Fh
0x1400f6568  cmp     rcx, r14
0x1400f656b  jz      loc_1400F65F4
0x1400f6571  test    byte ptr [rcx+1Ch], 1
0x1400f6575  jz      short loc_1400F65F4
0x1400f6577  xor     edx, edx; Val
0x1400f6579  lea     rcx, [rsp+2C0h+ServiceConfig]; void *
0x1400f657e  mov     r8d, 200h; Size
0x1400f6584  call    memset
0x1400f6589  lea     r9, [rbp+1C0h+var_40]; pcbBytesNeeded
0x1400f6590  mov     [rbp+1C0h+var_40], 0
0x1400f659a  mov     r8d, 200h; cbBufSize
0x1400f65a0  lea     rdx, [rsp+2C0h+ServiceConfig]; lpServiceConfig
0x1400f65a5  mov     rcx, r12; hService
0x1400f65a8  call    cs:__imp_QueryServiceConfigW
0x1400f65ae  test    eax, eax
0x1400f65b0  jnz     short loc_1400F65BD
0x1400f65b2  call    HrGetLastFailure
0x1400f65b7  mov     [rbp+1C0h+ServiceConfig.lpDisplayName], rdi
0x1400f65bb  jmp     short loc_1400F65C1
0x1400f65bd  mov     rdi, [rbp+1C0h+ServiceConfig.lpDisplayName]
0x1400f65c1  mov     ecx, [rbp+1C0h+ServiceStatus.dwCurrentState]; this
0x1400f65c7  call    ?ServiceStateToString@CommonUtil@@YAPEB_WK@Z; CommonUtil::ServiceStateToString(ulong)
0x1400f65cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f65d3  lea     r8, WPP_1a07eea27bbb3806b3fdf6b25f88669e_Traceguids
0x1400f65da  mov     r9, rax
0x1400f65dd  mov     [rsp+2C0h+lpEventAttributes], rdi
0x1400f65e2  mov     edx, 0Fh
0x1400f65e7  mov     rcx, [rcx+10h]
0x1400f65eb  call    WPP_SF_SS
0x1400f65f0  jmp     short loc_1400F65F4
0x1400f65f2  xor     ebx, ebx
0x1400f65f4  mov     rcx, [rbp+1C0h+var_30]
0x1400f65fb  test    rcx, rcx
0x1400f65fe  jz      short loc_1400F6606
0x1400f6600  call    cs:AddressOfUnsubscribeServiceChangeNotifications
0x1400f6606  mov     rcx, [rbp+1C0h+hObject]; hObject
0x1400f660d  test    rcx, rcx
0x1400f6610  jz      short loc_1400F6618
0x1400f6612  call    cs:__imp_CloseHandle
0x1400f6618  mov     eax, ebx
0x1400f661a  mov     rcx, [rbp+1C0h+var_28]
0x1400f6621  xor     rcx, rsp; StackCookie
0x1400f6624  call    __security_check_cookie
0x1400f6629  lea     r11, [rsp+2C0h+var_20]
0x1400f6631  mov     rbx, [r11+40h]
0x1400f6635  mov     rdi, [r11+48h]
0x1400f6639  mov     rsp, r11
0x1400f663c  pop     r15
0x1400f663e  pop     r14
  ... truncated ...
```
