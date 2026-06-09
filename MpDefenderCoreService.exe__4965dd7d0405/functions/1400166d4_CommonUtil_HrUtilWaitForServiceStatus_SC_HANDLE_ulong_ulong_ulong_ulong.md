# CommonUtil::HrUtilWaitForServiceStatus(SC_HANDLE__ *,ulong,ulong,ulong,ulong)

- ea: `0x1400166d4`
- end: `0x1400169f5`
- name: `?HrUtilWaitForServiceStatus@CommonUtil@@YAJPEAUSC_HANDLE__@@KKKK@Z`
- size: `801`
- prototype: `__int64 __usercall@<rax>(SC_HANDLE hService@<rcx>, struct SC_HANDLE__ *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140016538`
- `0x140016f34`

## callees

- `0x1400162c0`
- `0x1400166d4`
- `0x140017004`
- `0x1400171d8`
- `0x140017738`
- `0x140017990`
- `0x14003a5c0`
- `0x1400f5934`
- `0x140166990`

## import_xrefs

- `KERNEL32!Sleep` at `0x1400167d0`
- `KERNEL32!Sleep` at `0x1400167d0`
- `ADVAPI32!QueryServiceConfigW` at `0x140016898`
- `ADVAPI32!QueryServiceConfigW` at `0x140016948`
- `ADVAPI32!QueryServiceConfigW` at `0x140016898`
- `ADVAPI32!QueryServiceConfigW` at `0x140016948`

## pseudocode

```c
__int64 __fastcall CommonUtil::HrUtilWaitForServiceStatus(
        SC_HANDLE hService,
        struct SC_HANDLE__ *a2,
        struct SC_HANDLE__ *a3,
        DWORD a4,
        unsigned int a5)
{
  __int64 v5; // rsi
  unsigned int v7; // r15d
  __int64 result; // rax
  unsigned __int64 v9; // rdi
  DWORD *dwCurrentState; // rcx
  DWORD *v11; // rax
  DWORD v12; // r13d
  unsigned int v13; // edx
  struct SC_HANDLE__ *v14; // r8
  unsigned int dwWin32ExitCode; // ebx
  wchar_t *String; // r14
  wchar_t *lpDisplayName; // r9
  wchar_t *v18; // rsi
  int v19; // [rsp+60h] [rbp-A0h] BYREF
  DWORD v20; // [rsp+64h] [rbp-9Ch] BYREF
  int v21; // [rsp+68h] [rbp-98h] BYREF
  struct _QUERY_SERVICE_CONFIGW ServiceConfig[8]; // [rsp+70h] [rbp-90h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+270h] [rbp+170h] BYREF
  DWORD pcbBytesNeeded; // [rsp+290h] [rbp+190h] BYREF

  v5 = (unsigned int)a2;
  pcbBytesNeeded = a4;
  v7 = (unsigned int)a3;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  result = CommonUtil::HrQueryServiceStatus(&ServiceStatus, hService, a3);
  if ( (int)result >= 0 && ServiceStatus.dwCurrentState != v7 )
  {
    if ( (_DWORD)v5 == -1 )
      v9 = -1;
    else
      v9 = CommonUtil::UtilGetSystemTimeAsUlong64((CommonUtil *)((unsigned int)result >> 31)) + 10000 * v5;
    dwCurrentState = (DWORD *)&v19;
    v19 = 250;
    v21 = 3000;
    v20 = ServiceStatus.dwWaitHint / 0xA;
    if ( ServiceStatus.dwWaitHint / 0xA >= 0xFA )
      dwCurrentState = &v20;
    v11 = (DWORD *)&v21;
    if ( ServiceStatus.dwWaitHint / 0xA <= 0xBB8 )
      v11 = dwCurrentState;
    v12 = *v11;
    while ( (_DWORD)v5 == -1 || CommonUtil::UtilGetSystemTimeAsUlong64((CommonUtil *)dwCurrentState) <= v9 )
    {
      Sleep(v12);
      dwWin32ExitCode = CommonUtil::HrQueryServiceStatus(&ServiceStatus, hService, v14);
      if ( (dwWin32ExitCode & 0x80000000) != 0 )
        return dwWin32ExitCode;
      dwCurrentState = (DWORD *)ServiceStatus.dwCurrentState;
      if ( ServiceStatus.dwCurrentState == v7 )
        return dwWin32ExitCode;
      if ( (!a5 || ServiceStatus.dwCurrentState != a5) && ServiceStatus.dwCurrentState != pcbBytesNeeded )
      {
        if ( ServiceStatus.dwWin32ExitCode )
        {
          dwWin32ExitCode = LOWORD(ServiceStatus.dwWin32ExitCode) | 0x80070000;
          if ( (int)ServiceStatus.dwWin32ExitCode <= 0 )
            dwWin32ExitCode = ServiceStatus.dwWin32ExitCode;
        }
        else
        {
          dwWin32ExitCode = -2147019873;
        }
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          v18 = (wchar_t *)CommonUtil::ServiceStateToString(
                             (CommonUtil *)ServiceStatus.dwCurrentState,
                             WPP_GLOBAL_Control);
          memset(ServiceConfig, 0, sizeof(ServiceConfig));
          pcbBytesNeeded = 0;
          if ( !QueryServiceConfigW(hService, ServiceConfig, 0x200u, &pcbBytesNeeded) )
          {
            HrGetLastFailure();
            ServiceConfig[0].lpDisplayName = (LPWSTR)L"<unknown>";
          }
          WPP_SF_SLSLLLLLd(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            ServiceStatus.dwServiceType,
            v18,
            ServiceStatus.dwControlsAccepted,
            ServiceStatus.dwWin32ExitCode,
            ServiceStatus.dwServiceSpecificExitCode,
            ServiceStatus.dwCheckPoint,
            ServiceStatus.dwWaitHint,
            dwWin32ExitCode);
        }
        return dwWin32ExitCode;
      }
    }
    dwWin32ExitCode = -2147023436;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      _mm_lfence();
      String = (wchar_t *)CommonUtil::ServiceStateToString((CommonUtil *)v7, v13);
      memset(ServiceConfig, 0, sizeof(ServiceConfig));
      pcbBytesNeeded = 0;
      if ( QueryServiceConfigW(hService, ServiceConfig, 0x200u, &pcbBytesNeeded) )
      {
        lpDisplayName = ServiceConfig[0].lpDisplayName;
      }
      else
      {
        HrGetLastFailure();
        lpDisplayName = (wchar_t *)L"<unknown>";
        ServiceConfig[0].lpDisplayName = (LPWSTR)L"<unknown>";
      }
      WPP_SF_LSSd(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), lpDisplayName, String, 180);
    }
    return dwWin32ExitCode;
  }
  return result;
}

```

## disassembly

```asm
0x1400166d4  mov     [rsp-8+arg_18], rbx
0x1400166d9  push    rbp
0x1400166da  push    rsi
0x1400166db  push    rdi
0x1400166dc  push    r12
0x1400166de  push    r13
0x1400166e0  push    r14
0x1400166e2  push    r15
0x1400166e4  lea     rbp, [rsp-1A0h]
0x1400166ec  sub     rsp, 2A0h
0x1400166f3  mov     rax, cs:__security_cookie
0x1400166fa  xor     rax, rsp
0x1400166fd  mov     [rbp+1D0h+var_38], rax
0x140016704  xor     eax, eax
0x140016706  mov     esi, edx
0x140016708  mov     rdx, rcx; hService
0x14001670b  mov     [rbp+1D0h+pcbBytesNeeded], r9d
0x140016712  mov     r12, rcx
0x140016715  mov     qword ptr [rbp+1D0h+ServiceStatus.dwServiceSpecificExitCode], rax
0x14001671c  xorps   xmm0, xmm0
0x14001671f  mov     [rbp+1D0h+ServiceStatus.dwWaitHint], eax
0x140016725  lea     rcx, [rbp+1D0h+ServiceStatus]; lpServiceStatus
0x14001672c  mov     r15d, r8d
0x14001672f  movups  xmmword ptr [rbp+1D0h+ServiceStatus.dwServiceType], xmm0
0x140016736  call    ?HrQueryServiceStatus@CommonUtil@@YAJPEAU_SERVICE_STATUS@@PEAUSC_HANDLE__@@@Z; CommonUtil::HrQueryServiceStatus(_SERVICE_STATUS *,SC_HANDLE__ *)
0x14001673b  mov     ecx, eax
0x14001673d  shr     ecx, 1Fh; this
0x140016740  test    cl, cl
0x140016742  jnz     loc_1400169CB
0x140016748  cmp     [rbp+1D0h+ServiceStatus.dwCurrentState], r15d
0x14001674f  jz      loc_1400169CB
0x140016755  cmp     esi, 0FFFFFFFFh
0x140016758  jnz     short loc_140016760
0x14001675a  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14001675e  jmp     short loc_14001676F
0x140016760  call    ?UtilGetSystemTimeAsUlong64@CommonUtil@@YA_KXZ; CommonUtil::UtilGetSystemTimeAsUlong64(void)
0x140016765  imul    rdi, rsi, 2710h
0x14001676c  add     rdi, rax
0x14001676f  mov     r14d, [rbp+1D0h+arg_20]
0x140016776  lea     rcx, [rsp+2D0h+var_270]
0x14001677b  mov     eax, 0CCCCCCCDh
0x140016780  mov     r8d, 0FAh
0x140016786  mul     [rbp+1D0h+ServiceStatus.dwWaitHint]
0x14001678c  lea     rax, [rsp+2D0h+var_26C]
0x140016791  mov     [rsp+2D0h+var_270], r8d
0x140016796  shr     edx, 3
0x140016799  mov     r9d, 0BB8h
0x14001679f  cmp     edx, r8d
0x1400167a2  mov     [rsp+2D0h+var_268], r9d
0x1400167a7  mov     [rsp+2D0h+var_26C], edx
0x1400167ab  cmovnb  rcx, rax; this
0x1400167af  cmp     edx, r9d
0x1400167b2  lea     rax, [rsp+2D0h+var_268]
0x1400167b7  cmovbe  rax, rcx
0x1400167bb  mov     r13d, [rax]
0x1400167be  cmp     esi, 0FFFFFFFFh
0x1400167c1  jz      short loc_1400167CD
0x1400167c3  call    ?UtilGetSystemTimeAsUlong64@CommonUtil@@YA_KXZ; CommonUtil::UtilGetSystemTimeAsUlong64(void)
0x1400167c8  cmp     rax, rdi
0x1400167cb  ja      short loc_140016834
0x1400167cd  mov     ecx, r13d; dwMilliseconds
0x1400167d0  call    cs:__imp_Sleep
0x1400167d6  mov     rdx, r12; hService
0x1400167d9  lea     rcx, [rbp+1D0h+ServiceStatus]; lpServiceStatus
0x1400167e0  call    ?HrQueryServiceStatus@CommonUtil@@YAJPEAU_SERVICE_STATUS@@PEAUSC_HANDLE__@@@Z; CommonUtil::HrQueryServiceStatus(_SERVICE_STATUS *,SC_HANDLE__ *)
0x1400167e5  mov     ebx, eax
0x1400167e7  shr     eax, 1Fh
0x1400167ea  test    al, al
0x1400167ec  jnz     loc_1400169C9
0x1400167f2  mov     ecx, [rbp+1D0h+ServiceStatus.dwCurrentState]; this
0x1400167f8  cmp     ecx, r15d
0x1400167fb  jz      loc_1400169C9
0x140016801  test    r14d, r14d
0x140016804  jz      short loc_14001680B
0x140016806  cmp     ecx, r14d
0x140016809  jz      short loc_1400167BE
0x14001680b  cmp     ecx, [rbp+1D0h+pcbBytesNeeded]
0x140016811  jz      short loc_1400167BE
0x140016813  mov     eax, [rbp+1D0h+ServiceStatus.dwWin32ExitCode]
0x140016819  test    eax, eax
0x14001681b  jz      loc_1400168EA
0x140016821  movzx   ebx, ax
0x140016824  or      ebx, 80070000h
0x14001682a  test    eax, eax
0x14001682c  cmovle  ebx, eax
0x14001682f  jmp     loc_1400168EF
0x140016834  mov     ebx, 800705B4h
0x140016839  mov     rcx, cs:WPP_GLOBAL_Control
0x140016840  lea     rax, WPP_GLOBAL_Control
0x140016847  cmp     rcx, rax
0x14001684a  jz      loc_1400169C9
0x140016850  test    byte ptr [rcx+1Ch], 1
0x140016854  jz      loc_1400169C9
0x14001685a  lfence
0x14001685d  mov     ecx, r15d; this
0x140016860  call    ?ServiceStateToString@CommonUtil@@YAPEB_WK@Z; CommonUtil::ServiceStateToString(ulong)
0x140016865  mov     edi, 200h
0x14001686a  lea     rcx, [rsp+2D0h+ServiceConfig]; void *
0x14001686f  mov     r8d, edi; Size
0x140016872  xor     edx, edx; Val
0x140016874  mov     r14, rax
0x140016877  call    memset
0x14001687c  lea     r9, [rbp+1D0h+pcbBytesNeeded]; pcbBytesNeeded
0x140016883  mov     [rbp+1D0h+pcbBytesNeeded], 0
0x14001688d  mov     r8d, edi; cbBufSize
0x140016890  lea     rdx, [rsp+2D0h+ServiceConfig]; lpServiceConfig
0x140016895  mov     rcx, r12; hService
0x140016898  call    cs:__imp_QueryServiceConfigW
0x14001689e  test    eax, eax
0x1400168a0  jnz     short loc_1400168B4
0x1400168a2  call    HrGetLastFailure
0x1400168a7  lea     r9, aUnknown_1; "<unknown>"
0x1400168ae  mov     [rbp+1D0h+ServiceConfig.lpDisplayName], r9
0x1400168b2  jmp     short loc_1400168B8
0x1400168b4  mov     r9, [rbp+1D0h+ServiceConfig.lpDisplayName]
0x1400168b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400168bf  lea     r8, WPP_2f794a95c3a031461a11d46e8fbe4e7a_Traceguids
0x1400168c6  mov     dword ptr [rsp+2D0h+var_2A0], ebx; char
0x1400168ca  mov     edx, 14h
0x1400168cf  mov     [rsp+2D0h+String], r14; String
0x1400168d4  mov     [rsp+2D0h+var_2B0], r9; wchar_t *
0x1400168d9  mov     r9d, esi
0x1400168dc  mov     rcx, [rcx+10h]; LoggerHandle
0x1400168e0  call    WPP_SF_LSSd
0x1400168e5  jmp     loc_1400169C9
0x1400168ea  mov     ebx, 8007139Fh
0x1400168ef  mov     rdx, cs:WPP_GLOBAL_Control; unsigned int
0x1400168f6  lea     rax, WPP_GLOBAL_Control
0x1400168fd  cmp     rdx, rax
0x140016900  jz      loc_1400169C9
0x140016906  test    byte ptr [rdx+1Ch], 1
0x14001690a  jz      loc_1400169C9
0x140016910  call    ?ServiceStateToString@CommonUtil@@YAPEB_WK@Z; CommonUtil::ServiceStateToString(ulong)
0x140016915  mov     edi, 200h
0x14001691a  lea     rcx, [rsp+2D0h+ServiceConfig]; void *
0x14001691f  mov     r8d, edi; Size
0x140016922  xor     edx, edx; Val
0x140016924  mov     rsi, rax
0x140016927  call    memset
0x14001692c  lea     r9, [rbp+1D0h+pcbBytesNeeded]; pcbBytesNeeded
0x140016933  mov     [rbp+1D0h+pcbBytesNeeded], 0
0x14001693d  mov     r8d, edi; cbBufSize
0x140016940  lea     rdx, [rsp+2D0h+ServiceConfig]; lpServiceConfig
0x140016945  mov     rcx, r12; hService
0x140016948  call    cs:__imp_QueryServiceConfigW
0x14001694e  test    eax, eax
0x140016950  jnz     short loc_140016964
0x140016952  call    HrGetLastFailure
0x140016957  lea     r9, aUnknown_1; "<unknown>"
0x14001695e  mov     [rbp+1D0h+ServiceConfig.lpDisplayName], r9
0x140016962  jmp     short loc_140016968
0x140016964  mov     r9, [rbp+1D0h+ServiceConfig.lpDisplayName]
0x140016968  mov     ecx, [rbp+1D0h+ServiceStatus.dwWin32ExitCode]
0x14001696e  lea     r8, WPP_2f794a95c3a031461a11d46e8fbe4e7a_Traceguids
0x140016975  mov     eax, [rbp+1D0h+ServiceStatus.dwWaitHint]
0x14001697b  mov     edx, 15h
0x140016980  mov     dword ptr [rsp+2D0h+var_278], ebx; char
0x140016984  mov     dword ptr [rsp+2D0h+var_280], eax; char
0x140016988  mov     eax, [rbp+1D0h+ServiceStatus.dwCheckPoint]
0x14001698e  mov     dword ptr [rsp+2D0h+var_288], eax; char
0x140016992  mov     eax, [rbp+1D0h+ServiceStatus.dwServiceSpecificExitCode]
0x140016998  mov     dword ptr [rsp+2D0h+var_290], eax; char
0x14001699c  mov     dword ptr [rsp+2D0h+var_298], ecx; char
0x1400169a0  mov     ecx, [rbp+1D0h+ServiceStatus.dwControlsAccepted]
0x1400169a6  mov     dword ptr [rsp+2D0h+var_2A0], ecx; char
0x1400169aa  mov     ecx, [rbp+1D0h+ServiceStatus.dwServiceType]
0x1400169b0  mov     [rsp+2D0h+String], rsi; String
0x1400169b5  mov     dword ptr [rsp+2D0h+var_2B0], ecx; char
0x1400169b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400169c0  mov     rcx, [rcx+10h]; LoggerHandle
0x1400169c4  call    WPP_SF_SLSLLLLLd
0x1400169c9  mov     eax, ebx
0x1400169cb  mov     rcx, [rbp+1D0h+var_38]
0x1400169d2  xor     rcx, rsp; StackCookie
0x1400169d5  call    __security_check_cookie
0x1400169da  mov     rbx, [rsp+2D0h+arg_18]
0x1400169e2  add     rsp, 2A0h
0x1400169e9  pop     r15
0x1400169eb  pop     r14
0x1400169ed  pop     r13
0x1400169ef  pop     r12
0x1400169f1  pop     rdi
0x1400169f2  pop     rsi
0x1400169f3  pop     rbp
0x1400169f4  retn
```
