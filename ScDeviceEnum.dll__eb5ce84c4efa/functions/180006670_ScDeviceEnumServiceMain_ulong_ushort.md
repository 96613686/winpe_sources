# ScDeviceEnumServiceMain(ulong,ushort * *)

- ea: `0x180006670`
- end: `0x180006abc`
- name: `?ScDeviceEnumServiceMain@@YAXKPEAPEAG@Z`
- size: `1100`
- prototype: `void __fastcall(__int64, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180005e84`
- `0x180005f7c`
- `0x180006034`
- `0x180006670`
- `0x180006d40`
- `0x1800070b8`
- `0x180007120`
- `0x180007178`
- `0x1800071d4`
- `0x180007ec0`
- `0x180008c14`
- `0x180009fbc`
- `0x18000b7cc`
- `0x18001e020`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000677c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000677c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180006a23`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180006a23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000678e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800067ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006875`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800069e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006a10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000678e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800067ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006875`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800069e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006a10`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000686b`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800069be`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000686b`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800069be`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800067dd`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800067dd`

## string_xrefs

- `0x18000669b`: `ScDeviceEnumServiceMain`

## pseudocode

```c
void __fastcall ScDeviceEnumServiceMain(__int64 a1, unsigned __int16 **a2)
{
  int v2; // eax
  __int64 v3; // rcx
  char v4; // bl
  __int64 v5; // rcx
  _QWORD *v6; // rcx
  int v7; // edx
  SERVICE_STATUS_HANDLE v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 (__fastcall *v12)(SERVICE_STATUS_HANDLE *, const WCHAR *, HANDLE, void (__fastcall *)(void *, unsigned __int8), _QWORD, int); // rax
  __int64 v13; // rcx
  DWORD v14; // ebx
  int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // r8
  char LastError; // al
  DWORD v19; // [rsp+40h] [rbp-39h] BYREF
  int v20; // [rsp+44h] [rbp-35h] BYREF
  DWORD *v21; // [rsp+48h] [rbp-31h] BYREF
  __int16 v22; // [rsp+50h] [rbp-29h]
  _QWORD *v23; // [rsp+58h] [rbp-21h] BYREF
  _QWORD v24[2]; // [rsp+60h] [rbp-19h] BYREF
  _BYTE v25[16]; // [rsp+70h] [rbp-9h] BYREF
  char v26[24]; // [rsp+80h] [rbp+7h] BYREF

  v20 = 0;
  strcpy(v26, "ScDeviceEnumServiceMain");
  v24[0] = v26;
  v24[1] = &v20;
  lambda_7100c4b05337816adaa9a0810e332b08_::operator()(v24, a2);
  v20 = 1;
  v23 = v24;
  v19 = 0;
  v21 = &v19;
  v22 = 258;
  v2 = McGenEventRegister_EventRegister();
  v4 = v2;
  if ( v2 < 0 )
  {
    WppTraceIndent(v3, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        (unsigned int)&WPP_cc5e31c4c3a13497f43cc016dcb7f87d_Traceguids,
        (_DWORD)WPP_pszIndent,
        v4);
    }
  }
  *(_OWORD *)&ServiceStatus.dwServiceType = 0;
  *(_OWORD *)&ServiceStatus.dwServiceSpecificExitCode = 0;
  *(_OWORD *)&hServiceStatus = 0;
  hObject = 0;
  _InterlockedExchange64(&qword_18002BD40, 0);
  hObject = CreateEventW(0, 1, 0, 0);
  if ( hObject )
  {
    v8 = RegisterServiceCtrlHandlerExW(L"ScDeviceEnum", ScDeviceEnumCtrlHandler, 0);
    hServiceStatus = v8;
    if ( v8 )
    {
      ServiceStatus.dwServiceType = 32;
      *(_QWORD *)&ServiceStatus.dwCurrentState = 2;
      *(_QWORD *)&ServiceStatus.dwWin32ExitCode = 0;
      ServiceStatus.dwWaitHint = 10000;
      ServiceStatus.dwCheckPoint = 0;
      if ( SetServiceStatus(v8, &ServiceStatus) )
      {
        if ( qword_18002BD38 )
        {
          v12 = *(__int64 (__fastcall **)(SERVICE_STATUS_HANDLE *, const WCHAR *, HANDLE, void (__fastcall *)(void *, unsigned __int8), _QWORD, int))(qword_18002BD38 + 192);
          if ( v12 )
          {
            v14 = v12(&hServiceStatus + 1, L"ScDeviceEnum", hObject, ScDeviceEnumStopCallback, 0, 24);
            if ( v14 )
            {
              WppTraceIndent(v13, 2);
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  16,
                  (unsigned int)&WPP_cc5e31c4c3a13497f43cc016dcb7f87d_Traceguids,
                  (_DWORD)WPP_pszIndent,
                  v14);
              }
              v19 = v14;
              goto LABEL_48;
            }
            HIBYTE(v22) = 0;
            v15 = CTaskCounter::Initialize();
            if ( v15 >= 0 )
            {
              v15 = CBusNode::Initialize();
              if ( v15 >= 0 )
              {
                v15 = CRpcManager::Start();
                if ( v15 >= 0 )
                {
                  v15 = CSessionManager::Initialize();
                  if ( v15 >= 0 )
                  {
                    ServiceStatus.dwControlsAccepted = 1153;
                    ServiceStatus.dwCurrentState = 4;
                    if ( SetServiceStatus(hServiceStatus, &ServiceStatus) )
                    {
                      if ( (Microsoft_Windows_SmartCard_DeviceEnumEnableBits & 2) != 0 )
                        McGenEventWrite_EventWriteTransfer(v16, SCDEVICEENUM_SERVICE_START, v17, 1, v25);
                      goto LABEL_48;
                    }
                    WppTraceIndent(v16, 2);
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      LastError = GetLastError();
                      WPP_SF_sd(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        17,
                        (unsigned int)&WPP_cc5e31c4c3a13497f43cc016dcb7f87d_Traceguids,
                        (_DWORD)WPP_pszIndent,
                        LastError);
                    }
                    v15 = GetLastError();
                  }
                }
              }
            }
            ServiceStatus.dwWin32ExitCode = v15;
            SetEvent(hObject);
            goto LABEL_48;
          }
        }
        WppTraceIndent(v10, 2);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            15,
            &WPP_cc5e31c4c3a13497f43cc016dcb7f87d_Traceguids,
            WPP_pszIndent);
        }
        v19 = -2147418113;
      }
      else
      {
        v19 = GetLastError();
        WppTraceIndent(v11, 2);
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v7 = 14;
          goto LABEL_21;
        }
      }
    }
    else
    {
      v19 = GetLastError();
      WppTraceIndent(v9, 2);
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v7 = 13;
        goto LABEL_21;
      }
    }
  }
  else
  {
    v19 = GetLastError();
    WppTraceIndent(v5, 2);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = 12;
LABEL_21:
      WPP_SF_sd(v6[2], v7, (unsigned int)&WPP_cc5e31c4c3a13497f43cc016dcb7f87d_Traceguids, (_DWORD)WPP_pszIndent, v19);
    }
  }
LABEL_48:
  wil::details::ScopeExitFnGuard__lambda_d495ed0969d7a4df03df3ad00c2006cb___::operator()(&v21);
  WppTraceUnwinder__lambda_7100c4b05337816adaa9a0810e332b08____::_WppTraceUnwinder__lambda_7100c4b05337816adaa9a0810e332b08____(&v23);
}

```

## disassembly

```asm
0x180006670  push    rbp
0x180006672  push    rbx
0x180006673  push    rdi
0x180006674  push    r12
0x180006676  push    r14
0x180006678  push    r15
0x18000667a  lea     rbp, [rsp-2Fh]
0x18000667f  sub     rsp, 0A8h
0x180006686  mov     rax, cs:__security_cookie
0x18000668d  xor     rax, rsp
0x180006690  mov     [rbp+57h+var_38], rax
0x180006694  mov     [rbp+57h+var_8C], 0
0x18000669b  movups  xmm0, xmmword ptr cs:aScdeviceenumse_0; "ScDeviceEnumServiceMain"
0x1800066a2  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x1800066a6  movsd   xmm1, qword ptr cs:aScdeviceenumse_0+10h; "iceMain"
0x1800066ae  movsd   qword ptr [rbp+57h+var_50+10h], xmm1
0x1800066b3  lea     rax, [rbp+57h+var_50]
0x1800066b7  mov     [rbp+57h+var_70], rax
0x1800066bb  lea     rax, [rbp+57h+var_8C]
0x1800066bf  mov     [rbp+57h+var_68], rax
0x1800066c3  lea     rcx, [rbp+57h+var_70]
0x1800066c7  call    _lambda_7100c4b05337816adaa9a0810e332b08___operator__
0x1800066cc  mov     r14d, 1
0x1800066d2  mov     [rbp+57h+var_8C], r14d
0x1800066d6  lea     rax, [rbp+57h+var_70]
0x1800066da  mov     [rbp+57h+var_78], rax
0x1800066de  mov     [rbp+57h+var_90], 0
0x1800066e5  lea     rax, [rbp+57h+var_90]
0x1800066e9  mov     [rbp+57h+var_88], rax
0x1800066ed  lea     edi, [r14+1]
0x1800066f1  mov     [rbp+57h+var_80], 102h
0x1800066f7  call    McGenEventRegister_EventRegister
0x1800066fc  mov     ebx, eax
0x1800066fe  lea     r12, WPP_cc5e31c4c3a13497f43cc016dcb7f87d_Traceguids
0x180006705  lea     r15, WPP_GLOBAL_Control
0x18000670c  test    eax, eax
0x18000670e  jns     short loc_180006749
0x180006710  mov     edx, edi
0x180006712  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180006717  mov     rcx, cs:WPP_GLOBAL_Control
0x18000671e  cmp     rcx, r15
0x180006721  jz      short loc_180006749
0x180006723  test    [rcx+1Ch], r14b
0x180006727  jz      short loc_180006749
0x180006729  cmp     byte ptr [rcx+19h], 3
0x18000672d  jb      short loc_180006749
0x18000672f  lea     edx, [rdi+9]
0x180006732  mov     dword ptr [rsp+0D0h+var_B0], ebx
0x180006736  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18000673d  mov     r8, r12
0x180006740  mov     rcx, [rcx+10h]
0x180006744  call    WPP_SF_sd
0x180006749  xorps   xmm0, xmm0
0x18000674c  xor     eax, eax
0x18000674e  movups  xmmword ptr cs:ServiceStatus.dwServiceType, xmm0
0x180006755  movups  xmmword ptr cs:ServiceStatus.dwServiceSpecificExitCode, xmm0
0x18000675c  movups  cs:hServiceStatus, xmm0
0x180006763  mov     cs:hObject, rax
0x18000676a  xchg    rax, cs:qword_18002BD40
0x180006771  xor     r9d, r9d; lpName
0x180006774  xor     r8d, r8d; bInitialState
0x180006777  mov     edx, r14d; bManualReset
0x18000677a  xor     ecx, ecx; lpEventAttributes
0x18000677c  call    cs:__imp_CreateEventW
0x180006782  mov     cs:hObject, rax
0x180006789  test    rax, rax
0x18000678c  jnz     short loc_1800067CC
0x18000678e  call    cs:__imp_GetLastError
0x180006794  mov     [rbp+57h+var_90], eax
0x180006797  mov     edx, edi
0x180006799  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000679e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800067a5  cmp     rcx, r15
0x1800067a8  jz      loc_180006A8C
0x1800067ae  test    [rcx+1Ch], r14b
0x1800067b2  jz      loc_180006A8C
0x1800067b8  cmp     [rcx+19h], dil
0x1800067bc  jb      loc_180006A8C
0x1800067c2  mov     edx, 0Ch
0x1800067c7  jmp     loc_1800068AE
0x1800067cc  xor     r8d, r8d; lpContext
0x1800067cf  lea     rdx, ?ScDeviceEnumCtrlHandler@@YAKKKPEAX0@Z; lpHandlerProc
0x1800067d6  lea     rcx, ServiceName; "ScDeviceEnum"
0x1800067dd  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x1800067e3  mov     qword ptr cs:hServiceStatus, rax
0x1800067ea  test    rax, rax
0x1800067ed  jnz     short loc_18000682D
0x1800067ef  call    cs:__imp_GetLastError
0x1800067f5  mov     [rbp+57h+var_90], eax
0x1800067f8  mov     edx, edi
0x1800067fa  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800067ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180006806  cmp     rcx, r15
0x180006809  jz      loc_180006A8C
0x18000680f  test    [rcx+1Ch], r14b
0x180006813  jz      loc_180006A8C
0x180006819  cmp     [rcx+19h], dil
0x18000681d  jb      loc_180006A8C
0x180006823  mov     edx, 0Dh
0x180006828  jmp     loc_1800068AE
0x18000682d  mov     cs:ServiceStatus.dwServiceType, 20h ; ' '
0x180006837  mov     qword ptr cs:ServiceStatus.dwCurrentState, 2
0x180006842  mov     qword ptr cs:ServiceStatus.dwWin32ExitCode, 0
0x18000684d  mov     cs:ServiceStatus.dwWaitHint, 2710h
0x180006857  mov     cs:ServiceStatus.dwCheckPoint, 0
0x180006861  lea     rdx, ServiceStatus; lpServiceStatus
0x180006868  mov     rcx, rax; hServiceStatus
0x18000686b  call    cs:__imp_SetServiceStatus
0x180006871  test    eax, eax
0x180006873  jnz     short loc_1800068CD
0x180006875  call    cs:__imp_GetLastError
0x18000687b  mov     [rbp+57h+var_90], eax
0x18000687e  mov     edx, edi
0x180006880  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180006885  mov     rcx, cs:WPP_GLOBAL_Control
0x18000688c  cmp     rcx, r15
0x18000688f  jz      loc_180006A8C
0x180006895  test    [rcx+1Ch], r14b
0x180006899  jz      loc_180006A8C
0x18000689f  cmp     [rcx+19h], dil
0x1800068a3  jb      loc_180006A8C
0x1800068a9  mov     edx, 0Eh
0x1800068ae  mov     eax, [rbp+57h+var_90]
0x1800068b1  mov     dword ptr [rsp+0D0h+var_B0], eax
0x1800068b5  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800068bc  mov     r8, r12
0x1800068bf  mov     rcx, [rcx+10h]
0x1800068c3  call    WPP_SF_sd
0x1800068c8  jmp     loc_180006A8C
0x1800068cd  mov     rax, cs:qword_18002BD38
0x1800068d4  test    rax, rax
0x1800068d7  jz      loc_180006A4E
0x1800068dd  mov     rax, [rax+0C0h]
0x1800068e4  test    rax, rax
0x1800068e7  jz      loc_180006A4E
0x1800068ed  mov     [rsp+0D0h+var_A8], 18h
0x1800068f5  mov     [rsp+0D0h+var_B0], 0
0x1800068fe  lea     r9, ?ScDeviceEnumStopCallback@@YAXPEAXE@Z; ScDeviceEnumStopCallback(void *,uchar)
0x180006905  mov     r8, cs:hObject
0x18000690c  lea     rdx, ServiceName; "ScDeviceEnum"
0x180006913  lea     rcx, hServiceStatus+8
0x18000691a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000691f  mov     ebx, eax
0x180006921  test    eax, eax
0x180006923  jz      short loc_180006968
0x180006925  mov     edx, edi
0x180006927  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000692c  mov     rcx, cs:WPP_GLOBAL_Control
0x180006933  cmp     rcx, r15
0x180006936  jz      short loc_180006960
0x180006938  test    [rcx+1Ch], r14b
0x18000693c  jz      short loc_180006960
0x18000693e  cmp     [rcx+19h], dil
0x180006942  jb      short loc_180006960
0x180006944  mov     edx, 10h
0x180006949  mov     dword ptr [rsp+0D0h+var_B0], ebx
0x18000694d  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180006954  mov     r8, r12
0x180006957  mov     rcx, [rcx+10h]
0x18000695b  call    WPP_SF_sd
0x180006960  mov     [rbp+57h+var_90], ebx
0x180006963  jmp     loc_180006A8C
0x180006968  mov     byte ptr [rbp+57h+var_80+1], 0
0x18000696c  call    ?Initialize@CTaskCounter@@SAJXZ; CTaskCounter::Initialize(void)
0x180006971  test    eax, eax
0x180006973  js      loc_180006A16
0x180006979  call    ?Initialize@CBusNode@@SAJXZ; CBusNode::Initialize(void)
0x18000697e  test    eax, eax
0x180006980  js      loc_180006A16
0x180006986  call    ?Start@CRpcManager@@SAJXZ; CRpcManager::Start(void)
0x18000698b  test    eax, eax
0x18000698d  js      loc_180006A16
0x180006993  call    ?Initialize@CSessionManager@@SAJXZ; CSessionManager::Initialize(void)
0x180006998  test    eax, eax
0x18000699a  js      short loc_180006A16
0x18000699c  mov     cs:ServiceStatus.dwControlsAccepted, 481h
0x1800069a6  mov     cs:ServiceStatus.dwCurrentState, 4
0x1800069b0  lea     rdx, ServiceStatus; lpServiceStatus
0x1800069b7  mov     rcx, qword ptr cs:hServiceStatus; hServiceStatus
0x1800069be  call    cs:__imp_SetServiceStatus
0x1800069c4  test    eax, eax
0x1800069c6  jnz     short loc_180006A2B
0x1800069c8  mov     edx, edi
0x1800069ca  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800069cf  mov     rax, cs:WPP_GLOBAL_Control
0x1800069d6  cmp     rax, r15
0x1800069d9  jz      short loc_180006A10
0x1800069db  test    [rax+1Ch], r14b
0x1800069df  jz      short loc_180006A10
0x1800069e1  cmp     [rax+19h], dil
0x1800069e5  jb      short loc_180006A10
0x1800069e7  call    cs:__imp_GetLastError
0x1800069ed  mov     edx, 11h
0x1800069f2  mov     dword ptr [rsp+0D0h+var_B0], eax
0x1800069f6  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800069fd  mov     r8, r12
0x180006a00  mov     rcx, cs:WPP_GLOBAL_Control
0x180006a07  mov     rcx, [rcx+10h]
0x180006a0b  call    WPP_SF_sd
0x180006a10  call    cs:__imp_GetLastError
0x180006a16  mov     cs:ServiceStatus.dwWin32ExitCode, eax
0x180006a1c  mov     rcx, cs:hObject; hEvent
0x180006a23  call    cs:__imp_SetEvent
0x180006a29  jmp     short loc_180006A8C
0x180006a2b  test    cs:Microsoft_Windows_SmartCard_DeviceEnumEnableBits, dil
0x180006a32  jz      short loc_180006A8C
0x180006a34  lea     rax, [rbp+57h+var_60]
0x180006a38  mov     [rsp+0D0h+var_B0], rax
0x180006a3d  mov     r9d, r14d
0x180006a40  lea     rdx, SCDEVICEENUM_SERVICE_START
0x180006a47  call    McGenEventWrite_EventWriteTransfer
0x180006a4c  jmp     short loc_180006A8C
0x180006a4e  mov     edx, edi
0x180006a50  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180006a55  mov     rcx, cs:WPP_GLOBAL_Control
0x180006a5c  cmp     rcx, r15
0x180006a5f  jz      short loc_180006A85
0x180006a61  test    [rcx+1Ch], r14b
0x180006a65  jz      short loc_180006A85
0x180006a67  cmp     [rcx+19h], dil
0x180006a6b  jb      short loc_180006A85
0x180006a6d  mov     edx, 0Fh
0x180006a72  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180006a79  mov     r8, r12
0x180006a7c  mov     rcx, [rcx+10h]
0x180006a80  call    WPP_SF_s
0x180006a85  mov     [rbp+57h+var_90], 8000FFFFh
0x180006a8c  lea     rcx, [rbp+57h+var_88]
0x180006a90  call    wil__details__ScopeExitFnGuard__lambda_d495ed0969d7a4df03df3ad00c2006cb_____operator__
0x180006a95  nop
0x180006a96  lea     rcx, [rbp+57h+var_78]
0x180006a9a  call    WppTraceUnwinder__lambda_7100c4b05337816adaa9a0810e332b08_______WppTraceUnwinder__lambda_7100c4b05337816adaa9a0810e332b08____
0x180006a9f  mov     rcx, [rbp+57h+var_38]
0x180006aa3  xor     rcx, rsp; StackCookie
0x180006aa6  call    __security_check_cookie
0x180006aab  add     rsp, 0A8h
0x180006ab2  pop     r15
0x180006ab4  pop     r14
0x180006ab6  pop     r12
0x180006ab8  pop     rdi
0x180006ab9  pop     rbx
0x180006aba  pop     rbp
0x180006abb  retn
```
