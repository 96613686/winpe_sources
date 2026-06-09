# wWinMain

- ea: `0x140004b94`
- end: `0x140004dfb`
- name: `wWinMain`
- size: `615`
- prototype: `int __stdcall(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140001b90`

## callees

- `0x140002323`
- `0x140002b4c`
- `0x140004a40`
- `0x140004a68`
- `0x140004b94`
- `0x14003fbb0`

## import_xrefs

- `ntdll!VerSetConditionMask` at `0x140004cce`
- `ntdll!VerSetConditionMask` at `0x140004cce`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x140004c50`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x140004c50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004d9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004d9a`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140004cf1`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140004cf1`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140004dce`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140004dce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004dc2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004dc2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140004db5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140004db5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140004d7e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140004d7e`
- `api-ms-win-service-core-l1-1-0!StartServiceCtrlDispatcherW` at `0x140004d90`
- `api-ms-win-service-core-l1-1-0!StartServiceCtrlDispatcherW` at `0x140004d90`
- `api-ms-win-core-kernel32-legacy-l1-1-1!VerifyVersionInfoW` at `0x140004cde`
- `api-ms-win-core-kernel32-legacy-l1-1-1!VerifyVersionInfoW` at `0x140004cde`

## pseudocode

```c
int __stdcall wWinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)
{
  int v4; // ebx
  ULONG64 *v5; // rdi
  const GUID **v6; // rsi
  const GUID *v7; // r8
  ULONGLONG v8; // rax
  HRESULT v9; // eax
  _BYTE v11[8]; // [rsp+40h] [rbp-C0h] BYREF
  struct _TRACE_GUID_REGISTRATION TraceGuidReg; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v13; // [rsp+58h] [rbp-A8h]
  __int64 v14; // [rsp+60h] [rbp-A0h]
  _OSVERSIONINFOEXW VersionInformation; // [rsp+70h] [rbp-90h] BYREF

  g_hInstance = hInstance;
  v4 = 1;
  qword_14004CA10 = 0;
  qword_14004CA18 = 1;
  v5 = (ULONG64 *)&WPP_MAIN_CB;
  WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_CtlGuidTieringEngine;
  WPP_GLOBAL_Control = &WPP_MAIN_CB;
  v6 = (const GUID **)&WPP_REGISTRATION_GUIDS;
  WPP_MAIN_CB = 0;
  do
  {
    v7 = *v6;
    TraceGuidReg.Guid = v7;
    ++v6;
    TraceGuidReg.RegHandle = 0;
    v5[4] = (ULONG64)v7;
    RegisterTraceGuidsW(WppControlCallback, v5, v7, 1u, &TraceGuidReg, 0, 0, v5 + 1);
    v5 = (ULONG64 *)*v5;
  }
  while ( v5 );
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x1Fu, (const GUID *)WPP_ef66010c4da23316be47f4e1f0858c5c_Traceguids);
  }
  VersionInformation.dwOSVersionInfoSize = 284;
  *(_OWORD *)&VersionInformation.dwMajorVersion = 0;
  memset_0(VersionInformation.szCSDVersion, 0, sizeof(VersionInformation.szCSDVersion));
  *(_DWORD *)&VersionInformation.wSuiteMask = 0x10000;
  *(_DWORD *)&VersionInformation.wServicePackMajor = 0;
  v8 = VerSetConditionMask(0, 0x80u, 1u);
  g_IsClientSku = VerifyVersionInfoW(&VersionInformation, 0x80u, v8);
  v9 = CoInitializeEx(0, 0);
  if ( v9 >= 0 )
  {
    if ( ATL::CAtlBaseModule::m_bInitFailed )
    {
      v4 = -1;
    }
    else
    {
      v13 = 0;
      TraceGuidReg.Guid = (LPCGUID)&Buffer;
      v14 = 0;
      TraceGuidReg.RegHandle = CMyAtlServiceModuleT<CTieringEngineService,102>::_ServiceMain;
      hObject = CreateEventW(0, 1, 0, 0);
      if ( !StartServiceCtrlDispatcherW((const SERVICE_TABLE_ENTRYW *)&TraceGuidReg) )
        LODWORD(xmmword_14004CCCC) = GetLastError();
      if ( hObject )
      {
        WaitForSingleObject(hObject, 0xFFFFFFFF);
        CloseHandle(hObject);
      }
      v4 = xmmword_14004CCCC;
    }
    CoUninitialize();
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      0x20u,
      (const GUID *)WPP_ef66010c4da23316be47f4e1f0858c5c_Traceguids,
      v9);
  }
  wWinMain_::_2_::CWppTrace::_CWppTrace(v11);
  return v4;
}

```

## disassembly

```asm
0x140004b94  push    rbp
0x140004b96  push    rbx
0x140004b97  push    rsi
0x140004b98  push    rdi
0x140004b99  lea     rbp, [rsp-0A8h]
0x140004ba1  sub     rsp, 1A8h
0x140004ba8  mov     rax, cs:__security_cookie
0x140004baf  xor     rax, rsp
0x140004bb2  mov     [rbp+0C0h+var_30], rax
0x140004bb9  mov     cs:?g_hInstance@@3PEAUHINSTANCE__@@EA, rcx; HINSTANCE__ * g_hInstance
0x140004bc0  mov     ebx, 1
0x140004bc5  mov     cs:qword_14004CA10, 0
0x140004bd0  lea     rax, WPP_ThisDir_CTLGUID_CtlGuidTieringEngine
0x140004bd7  mov     cs:qword_14004CA18, rbx
0x140004bde  lea     rdi, WPP_MAIN_CB
0x140004be5  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x140004bec  mov     cs:WPP_GLOBAL_Control, rdi
0x140004bf3  lea     rsi, WPP_REGISTRATION_GUIDS
0x140004bfa  mov     cs:WPP_MAIN_CB, 0
0x140004c05  mov     r8, [rsi]; ControlGuid
0x140004c08  lea     rax, [rdi+8]
0x140004c0c  mov     [rsp+1C0h+RegistrationHandle], rax; RegistrationHandle
0x140004c11  lea     rcx, WppControlCallback; RequestAddress
0x140004c18  mov     [rsp+1C0h+MofResourceName], 0; MofResourceName
0x140004c21  lea     rax, [rsp+1C0h+var_178]
0x140004c26  mov     [rsp+1C0h+var_178.Guid], r8
0x140004c2b  lea     rsi, [rsi+8]
0x140004c2f  mov     [rsp+1C0h+var_178.RegHandle], 0
0x140004c38  mov     r9d, ebx; GuidCount
0x140004c3b  mov     [rsp+1C0h+MofImagePath], 0; MofImagePath
0x140004c44  mov     rdx, rdi; RequestContext
0x140004c47  mov     [rsp+1C0h+TraceGuidReg], rax; TraceGuidReg
0x140004c4c  mov     [rdi+20h], r8
0x140004c50  call    cs:__imp_RegisterTraceGuidsW
0x140004c56  mov     rdi, [rdi]
0x140004c59  test    rdi, rdi
0x140004c5c  jnz     short loc_140004C05
0x140004c5e  mov     rcx, cs:WPP_GLOBAL_Control
0x140004c65  lea     rsi, WPP_GLOBAL_Control
0x140004c6c  cmp     rcx, rsi
0x140004c6f  jz      short loc_140004C8F
0x140004c71  test    [rcx+1Ch], bl
0x140004c74  jz      short loc_140004C8F
0x140004c76  cmp     byte ptr [rcx+19h], 4
0x140004c7a  jb      short loc_140004C8F
0x140004c7c  mov     rcx, [rcx+10h]
0x140004c80  lea     edx, [rdi+1Fh]
0x140004c83  lea     r8, WPP_ef66010c4da23316be47f4e1f0858c5c_Traceguids
0x140004c8a  call    WPP_SF_
0x140004c8f  xorps   xmm0, xmm0
0x140004c92  mov     [rsp+1C0h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x140004c9a  xor     edx, edx; Val
0x140004c9c  lea     rcx, [rbp+0C0h+VersionInformation.szCSDVersion]; void *
0x140004ca0  mov     r8d, 100h; Size
0x140004ca6  movups  xmmword ptr [rsp+1C0h+VersionInformation.dwMajorVersion], xmm0
0x140004cab  call    memset_0
0x140004cb0  xor     eax, eax
0x140004cb2  mov     dword ptr [rbp+0C0h+VersionInformation.wSuiteMask], 10000h
0x140004cbc  mov     edi, 80h
0x140004cc1  mov     dword ptr [rbp+0C0h+VersionInformation.wServicePackMajor], eax
0x140004cc7  mov     edx, edi; TypeMask
0x140004cc9  mov     r8b, bl; Condition
0x140004ccc  xor     ecx, ecx; ConditionMask
0x140004cce  call    cs:__imp_VerSetConditionMask
0x140004cd4  mov     edx, edi; dwTypeMask
0x140004cd6  lea     rcx, [rsp+1C0h+VersionInformation]; lpVersionInformation
0x140004cdb  mov     r8, rax; dwlConditionMask
0x140004cde  call    cs:__imp_VerifyVersionInfoW
0x140004ce4  test    eax, eax
0x140004ce6  setnz   cs:?g_IsClientSku@@3_NA; bool g_IsClientSku
0x140004ced  xor     edx, edx; dwCoInit
0x140004cef  xor     ecx, ecx; pvReserved
0x140004cf1  call    cs:__imp_CoInitializeEx
0x140004cf7  test    eax, eax
0x140004cf9  jns     short loc_140004D39
0x140004cfb  mov     rcx, cs:WPP_GLOBAL_Control
0x140004d02  cmp     rcx, rsi
0x140004d05  jz      loc_140004DD4
0x140004d0b  test    [rcx+1Ch], bl
0x140004d0e  jz      loc_140004DD4
0x140004d14  cmp     byte ptr [rcx+19h], 2
0x140004d18  jb      loc_140004DD4
0x140004d1e  mov     rcx, [rcx+10h]
0x140004d22  lea     edx, [rdi-60h]
0x140004d25  mov     r9d, eax
0x140004d28  lea     r8, WPP_ef66010c4da23316be47f4e1f0858c5c_Traceguids
0x140004d2f  call    WPP_SF_d
0x140004d34  jmp     loc_140004DD4
0x140004d39  cmp     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 0; bool ATL::CAtlBaseModule::m_bInitFailed
0x140004d40  jz      short loc_140004D4A
0x140004d42  or      ebx, 0FFFFFFFFh
0x140004d45  jmp     loc_140004DCE
0x140004d4a  lea     rax, Buffer
0x140004d51  mov     [rsp+1C0h+var_168], 0
0x140004d5a  mov     [rsp+1C0h+var_178.Guid], rax
0x140004d5f  xor     r9d, r9d; lpName
0x140004d62  lea     rax, ?_ServiceMain@?$CMyAtlServiceModuleT@VCTieringEngineService@@$0GG@@@KAXKPEAPEAG@Z; CMyAtlServiceModuleT<CTieringEngineService,102>::_ServiceMain(ulong,ushort * *)
0x140004d69  mov     [rsp+1C0h+var_160], 0
0x140004d72  xor     r8d, r8d; bInitialState
0x140004d75  mov     [rsp+1C0h+var_178.RegHandle], rax
0x140004d7a  mov     edx, ebx; bManualReset
0x140004d7c  xor     ecx, ecx; lpEventAttributes
0x140004d7e  call    cs:__imp_CreateEventW
0x140004d84  lea     rcx, [rsp+1C0h+var_178]; lpServiceStartTable
0x140004d89  mov     cs:hObject, rax
0x140004d90  call    cs:__imp_StartServiceCtrlDispatcherW
0x140004d96  test    eax, eax
0x140004d98  jnz     short loc_140004DA6
0x140004d9a  call    cs:__imp_GetLastError
0x140004da0  mov     dword ptr cs:xmmword_14004CCCC, eax
0x140004da6  mov     rcx, cs:hObject; hHandle
0x140004dad  test    rcx, rcx
0x140004db0  jz      short loc_140004DC8
0x140004db2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140004db5  call    cs:__imp_WaitForSingleObject
0x140004dbb  mov     rcx, cs:hObject; hObject
0x140004dc2  call    cs:__imp_CloseHandle
0x140004dc8  mov     ebx, dword ptr cs:xmmword_14004CCCC
0x140004dce  call    cs:__imp_CoUninitialize
0x140004dd4  lea     rcx, [rsp+1C0h+var_180]
0x140004dd9  call    _wWinMain____2___CWppTrace___CWppTrace
0x140004dde  mov     eax, ebx
0x140004de0  mov     rcx, [rbp+0C0h+var_30]
0x140004de7  xor     rcx, rsp; StackCookie
0x140004dea  call    __security_check_cookie
0x140004def  add     rsp, 1A8h
0x140004df6  pop     rdi
0x140004df7  pop     rsi
0x140004df8  pop     rbx
0x140004df9  pop     rbp
0x140004dfa  retn
```
