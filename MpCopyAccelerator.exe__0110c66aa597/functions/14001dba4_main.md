# main

- ea: `0x14001dba4`
- end: `0x14001e065`
- name: `main`
- size: `1217`
- prototype: `int __fastcall(int argc, const char **argv, const char **envp)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140005a6c`

## callees

- `0x140003088`
- `0x140003680`
- `0x140005c20`
- `0x14001d330`
- `0x14001d700`
- `0x14001d9e0`
- `0x14001da4c`
- `0x14001da70`
- `0x14001dba4`
- `0x14001e068`
- `0x140020800`
- `0x140024148`

## import_xrefs

- `MpClient!MpConfigUninitialize` at `0x14001dde7`
- `MpClient!MpConfigUninitialize` at `0x14001deb2`
- `MpClient!MpConfigUninitialize` at `0x14001dfe8`
- `MpClient!MpConfigUninitialize` at `0x14001dde7`
- `MpClient!MpConfigUninitialize` at `0x14001deb2`
- `MpClient!MpConfigUninitialize` at `0x14001dfe8`
- `MpClient!MpConfigUnregisterNotifications` at `0x14001dfa7`
- `MpClient!MpConfigUnregisterNotifications` at `0x14001dfa7`
- `MpClient!MpConfigInitialize` at `0x14001dd19`
- `MpClient!MpConfigInitialize` at `0x14001dd19`
- `KERNEL32!DebugBreak` at `0x14001ddaf`
- `KERNEL32!DebugBreak` at `0x14001ddaf`
- `KERNEL32!CloseHandle` at `0x14001df90`
- `KERNEL32!CloseHandle` at `0x14001df90`
- `KERNEL32!GetLastError` at `0x14001ddd2`
- `KERNEL32!GetLastError` at `0x14001ddd2`
- `KERNEL32!CreateEventW` at `0x14001ddc0`
- `KERNEL32!CreateEventW` at `0x14001ddc0`
- `KERNEL32!WaitForSingleObject` at `0x14001df0b`
- `KERNEL32!WaitForSingleObject` at `0x14001df0b`
- `KERNEL32!SetErrorMode` at `0x14001dbdb`
- `KERNEL32!SetErrorMode` at `0x14001dbdb`
- `ADVAPI32!RegisterTraceGuidsW` at `0x14001dc5a`
- `ADVAPI32!RegisterTraceGuidsW` at `0x14001dc5a`
- `ADVAPI32!UnregisterTraceGuids` at `0x14001dd02`
- `ADVAPI32!UnregisterTraceGuids` at `0x14001dd7e`
- `ADVAPI32!UnregisterTraceGuids` at `0x14001de15`
- `ADVAPI32!UnregisterTraceGuids` at `0x14001dee0`
- `ADVAPI32!UnregisterTraceGuids` at `0x14001e01b`
- `ADVAPI32!UnregisterTraceGuids` at `0x14001dd02`
- `ADVAPI32!UnregisterTraceGuids` at `0x14001dd7e`
- `ADVAPI32!UnregisterTraceGuids` at `0x14001de15`
- `ADVAPI32!UnregisterTraceGuids` at `0x14001dee0`
- `ADVAPI32!UnregisterTraceGuids` at `0x14001e01b`

## string_xrefs

- `0x14001ddda`: `Create shutdown event failed: error code = %ld\n`

## pseudocode

```c
int __fastcall main(int argc, const char **argv, const char **envp)
{
  ULONG64 *v3; // rdi
  const GUID **v4; // rsi
  const GUID *v5; // r8
  struct CommonUtil::MpUtilsType **v6; // rdx
  int v7; // eax
  _UNKNOWN **v8; // rdi
  TRACEHANDLE v9; // rcx
  int v10; // eax
  _UNKNOWN **v11; // rdi
  TRACEHANDLE v12; // rcx
  __int64 Guid; // rdi
  HANDLE EventW; // rax
  DWORD LastError; // eax
  _QWORD *v16; // rdi
  TRACEHANDLE v17; // rcx
  int v19; // eax
  _QWORD *v20; // rdi
  TRACEHANDLE v21; // rcx
  DWORD v22; // eax
  __int64 v23; // r15
  struct CopyAcceleratorFeatures *Instance; // r14
  _UNKNOWN **v25; // r14
  TRACEHANDLE v26; // rcx
  __int64 v27; // [rsp+0h] [rbp-B8h] BYREF
  unsigned int v28; // [rsp+40h] [rbp-78h]
  BOOL v29; // [rsp+44h] [rbp-74h]
  const std::exception *v30; // [rsp+48h] [rbp-70h] BYREF
  struct _TRACE_GUID_REGISTRATION TraceGuidReg; // [rsp+50h] [rbp-68h] BYREF
  struct CommonUtil::MpUtilsType *v32; // [rsp+60h] [rbp-58h] BYREF
  _OWORD v33[3]; // [rsp+68h] [rbp-50h] BYREF
  __int64 v34; // [rsp+98h] [rbp-20h]

  SetErrorMode(1u);
  qword_14003D918 = 0;
  WPP_MAIN_CB = 0;
  qword_14003D920 = 1;
  WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_MpCopyAccelerator;
  v3 = (ULONG64 *)&WPP_MAIN_CB;
  WPP_GLOBAL_Control = &WPP_MAIN_CB;
  v4 = (const GUID **)&WPP_REGISTRATION_GUIDS;
  do
  {
    v5 = *v4++;
    TraceGuidReg.Guid = v5;
    TraceGuidReg.RegHandle = 0;
    v3[4] = (ULONG64)v5;
    RegisterTraceGuidsW(WppControlCallback, v3, v5, 1u, &TraceGuidReg, 0, 0, v3 + 1);
    v3 = (ULONG64 *)*v3;
  }
  while ( v3 );
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_d8286ee67877374a5cef524a3b6f17fd_Traceguids);
  v32 = 0;
  v7 = CommonUtil::MpSmartUtilsInitializeForExe((CommonUtil *)&v32, v6);
  if ( v7 < 0 )
  {
    v8 = (_UNKNOWN **)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        WPP_d8286ee67877374a5cef524a3b6f17fd_Traceguids,
        (unsigned int)v7);
      v8 = (_UNKNOWN **)WPP_GLOBAL_Control;
    }
    if ( v32 )
    {
      CommonUtil::CMpUtilsUninitialize::Release(v32);
      v8 = (_UNKNOWN **)WPP_GLOBAL_Control;
    }
    if ( v8 == &WPP_GLOBAL_Control )
      return 1;
    while ( v8 )
    {
      v9 = (TRACEHANDLE)v8[1];
      if ( v9 )
      {
        UnregisterTraceGuids(v9);
        v8[1] = 0;
      }
      v8 = (_UNKNOWN **)*v8;
    }
LABEL_43:
    WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
    return 1;
  }
  v10 = MpConfigInitialize();
  if ( v10 < 0 )
  {
    v11 = (_UNKNOWN **)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        WPP_d8286ee67877374a5cef524a3b6f17fd_Traceguids,
        (unsigned int)v10);
      v11 = (_UNKNOWN **)WPP_GLOBAL_Control;
    }
    if ( v32 )
    {
      CommonUtil::CMpUtilsUninitialize::Release(v32);
      v11 = (_UNKNOWN **)WPP_GLOBAL_Control;
    }
    if ( v11 == &WPP_GLOBAL_Control )
      return 1;
    while ( v11 )
    {
      v12 = (TRACEHANDLE)v11[1];
      if ( v12 )
      {
        UnregisterTraceGuids(v12);
        v11[1] = 0;
      }
      v11 = (_UNKNOWN **)*v11;
    }
    goto LABEL_43;
  }
  Guid = 305419896;
  TraceGuidReg.Guid = (LPCGUID)305419896;
  if ( (unsigned int)MpLookupMiscConfigFlag(L"MpCa_Debug") )
    DebugBreak();
  EventW = CreateEventW(0, 1, 0, 0);
  g_hShutdownEvent = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    MpCmdLogPrintf(L"Create shutdown event failed: error code = %ld\n", LastError);
    MpConfigUninitialize();
    if ( v32 )
      CommonUtil::CMpUtilsUninitialize::Release(v32);
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return 1;
    while ( v16 )
    {
      v17 = v16[1];
      if ( v17 )
      {
        UnregisterTraceGuids(v17);
        v16[1] = 0;
      }
      v16 = (_QWORD *)*v16;
    }
    goto LABEL_43;
  }
  try
  {
    v29 = 1;
    v34 = 0;
    memset(v33, 0, sizeof(v33));
    CopyAcceleratorRpc::CopyAcceleratorRpc((CopyAcceleratorRpc *)((char *)v33 + 8));
    v19 = CAutoInitCopyAccelerator::Initialize((CAutoInitCopyAccelerator *)v33);
  }
  catch ( const std::exception *v30 )
  {
    CommonUtil::HrFromStdException(v30, (const struct std::exception *)&v27);
  }
  catch ( ... )
  {
    v28 = -2147467259;
    LODWORD(v23) = 2;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_d8286ee67877374a5cef524a3b6f17fd_Traceguids, v28);
    Guid = (__int64)TraceGuidReg.Guid;
    goto LABEL_64;
  }
  if ( v19 >= 0 )
  {
    v22 = WaitForSingleObject(g_hShutdownEvent, 0xFFFFFFFF);
    v23 = v22 != 0;
    v29 = v22 != 0;
    CAutoInitCopyAccelerator::~CAutoInitCopyAccelerator((CAutoInitCopyAccelerator *)v33);
LABEL_64:
    CloseHandle(g_hShutdownEvent);
    Instance = CopyAcceleratorFeatures::GetInstance();
    if ( *((_QWORD *)Instance + 1) )
    {
      MpConfigUnregisterNotifications();
      *((_QWORD *)Instance + 1) = 0;
    }
    v25 = (_UNKNOWN **)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        WPP_d8286ee67877374a5cef524a3b6f17fd_Traceguids,
        (unsigned int)v23);
      v25 = (_UNKNOWN **)WPP_GLOBAL_Control;
    }
    if ( Guid )
    {
      MpConfigUninitialize();
      v25 = (_UNKNOWN **)WPP_GLOBAL_Control;
    }
    if ( v32 )
    {
      CommonUtil::CMpUtilsUninitialize::Release(v32);
      v25 = (_UNKNOWN **)WPP_GLOBAL_Control;
    }
    if ( v25 != &WPP_GLOBAL_Control )
    {
      while ( v25 )
      {
        v26 = (TRACEHANDLE)v25[1];
        if ( v26 )
        {
          UnregisterTraceGuids(v26);
          v25[1] = 0;
        }
        v25 = (_UNKNOWN **)*v25;
      }
      WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
    }
    return v23;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      19,
      WPP_d8286ee67877374a5cef524a3b6f17fd_Traceguids,
      (unsigned int)v19);
  CAutoInitCopyAccelerator::~CAutoInitCopyAccelerator((CAutoInitCopyAccelerator *)v33);
  MpConfigUninitialize();
  if ( v32 )
    CommonUtil::CMpUtilsUninitialize::Release(v32);
  v20 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    while ( v20 )
    {
      v21 = v20[1];
      if ( v21 )
      {
        UnregisterTraceGuids(v21);
        v20[1] = 0;
      }
      v20 = (_QWORD *)*v20;
    }
    WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
  }
  return 1;
}

```

## disassembly

```asm
0x14001dba4  mov     rax, rsp
0x14001dba7  mov     [rax+8], rbx
0x14001dbab  mov     [rax+10h], rsi
0x14001dbaf  mov     [rax+18h], rdi
0x14001dbb3  mov     [rax+20h], r14
0x14001dbb7  push    r15
0x14001dbb9  sub     rsp, 0B0h
0x14001dbc0  mov     rax, cs:__security_cookie
0x14001dbc7  xor     rax, rsp
0x14001dbca  mov     [rsp+0B8h+var_10], rax
0x14001dbd2  mov     r14d, 1
0x14001dbd8  mov     ecx, r14d; uMode
0x14001dbdb  call    cs:__imp_SetErrorMode
0x14001dbe1  xor     ebx, ebx
0x14001dbe3  mov     cs:qword_14003D918, rbx
0x14001dbea  mov     cs:WPP_MAIN_CB, rbx
0x14001dbf1  mov     cs:qword_14003D920, r14
0x14001dbf8  lea     rax, WPP_ThisDir_CTLGUID_MpCopyAccelerator
0x14001dbff  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x14001dc06  lea     rdi, WPP_MAIN_CB
0x14001dc0d  mov     cs:WPP_GLOBAL_Control, rdi
0x14001dc14  lea     rsi, WPP_REGISTRATION_GUIDS
0x14001dc1b  mov     r8, [rsi]; ControlGuid
0x14001dc1e  lea     rsi, [rsi+8]
0x14001dc22  mov     [rsp+0B8h+var_68.Guid], r8
0x14001dc27  mov     [rsp+0B8h+var_68.RegHandle], rbx
0x14001dc2c  mov     [rdi+20h], r8
0x14001dc30  lea     rax, [rdi+8]
0x14001dc34  mov     [rsp+0B8h+RegistrationHandle], rax; RegistrationHandle
0x14001dc39  mov     [rsp+0B8h+MofResourceName], rbx; MofResourceName
0x14001dc3e  mov     [rsp+0B8h+MofImagePath], rbx; MofImagePath
0x14001dc43  lea     rax, [rsp+0B8h+var_68]
0x14001dc48  mov     [rsp+0B8h+TraceGuidReg], rax; TraceGuidReg
0x14001dc4d  mov     r9d, r14d; GuidCount
0x14001dc50  mov     rdx, rdi; RequestContext
0x14001dc53  lea     rcx, WppControlCallback; RequestAddress
0x14001dc5a  call    cs:__imp_RegisterTraceGuidsW
0x14001dc60  mov     rdi, [rdi]
0x14001dc63  test    rdi, rdi
0x14001dc66  jnz     short loc_14001DC1B
0x14001dc68  lea     rsi, WPP_GLOBAL_Control
0x14001dc6f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001dc76  cmp     rcx, rsi
0x14001dc79  jz      short loc_14001DC94
0x14001dc7b  test    byte ptr [rcx+1Ch], 4
0x14001dc7f  jz      short loc_14001DC94
0x14001dc81  lea     edx, [rdi+10h]
0x14001dc84  lea     r8, WPP_d8286ee67877374a5cef524a3b6f17fd_Traceguids
0x14001dc8b  mov     rcx, [rcx+10h]
0x14001dc8f  call    WPP_SF_
0x14001dc94  mov     [rsp+0B8h+var_58], rbx
0x14001dc99  lea     rcx, [rsp+0B8h+var_58]; this
0x14001dc9e  call    ?MpSmartUtilsInitializeForExe@CommonUtil@@YAJPEAPEAUMpUtilsType@1@@Z; CommonUtil::MpSmartUtilsInitializeForExe(CommonUtil::MpUtilsType * *)
0x14001dca3  test    eax, eax
0x14001dca5  jns     short loc_14001DD19
0x14001dca7  mov     rdi, cs:WPP_GLOBAL_Control
0x14001dcae  cmp     rdi, rsi
0x14001dcb1  jz      short loc_14001DCD8
0x14001dcb3  test    [rdi+1Ch], r14b
0x14001dcb7  jz      short loc_14001DCD8
0x14001dcb9  mov     edx, 11h
0x14001dcbe  mov     r9d, eax
0x14001dcc1  lea     r8, WPP_d8286ee67877374a5cef524a3b6f17fd_Traceguids
0x14001dcc8  mov     rcx, [rdi+10h]
0x14001dccc  call    WPP_SF_d
0x14001dcd1  mov     rdi, cs:WPP_GLOBAL_Control
0x14001dcd8  mov     rcx, [rsp+0B8h+var_58]; struct CommonUtil::MpUtilsType *
0x14001dcdd  test    rcx, rcx
0x14001dce0  jz      short loc_14001DCEE
0x14001dce2  call    ?Release@CMpUtilsUninitialize@CommonUtil@@SAXPEAUMpUtilsType@2@@Z; CommonUtil::CMpUtilsUninitialize::Release(CommonUtil::MpUtilsType *)
0x14001dce7  mov     rdi, cs:WPP_GLOBAL_Control
0x14001dcee  cmp     rdi, rsi
0x14001dcf1  jz      loc_14001DE2E
0x14001dcf7  jmp     short loc_14001DD0F
0x14001dcf9  mov     rcx, [rdi+8]; RegistrationHandle
0x14001dcfd  test    rcx, rcx
0x14001dd00  jz      short loc_14001DD0C
0x14001dd02  call    cs:__imp_UnregisterTraceGuids
0x14001dd08  mov     [rdi+8], rbx
0x14001dd0c  mov     rdi, [rdi]
0x14001dd0f  test    rdi, rdi
0x14001dd12  jnz     short loc_14001DCF9
0x14001dd14  jmp     loc_14001DE27
0x14001dd19  call    cs:__imp_MpConfigInitialize
0x14001dd1f  test    eax, eax
0x14001dd21  jns     short loc_14001DD95
0x14001dd23  mov     rdi, cs:WPP_GLOBAL_Control
0x14001dd2a  cmp     rdi, rsi
0x14001dd2d  jz      short loc_14001DD54
0x14001dd2f  test    [rdi+1Ch], r14b
0x14001dd33  jz      short loc_14001DD54
0x14001dd35  mov     edx, 12h
0x14001dd3a  mov     r9d, eax
0x14001dd3d  lea     r8, WPP_d8286ee67877374a5cef524a3b6f17fd_Traceguids
0x14001dd44  mov     rcx, [rdi+10h]
0x14001dd48  call    WPP_SF_d
0x14001dd4d  mov     rdi, cs:WPP_GLOBAL_Control
0x14001dd54  mov     rcx, [rsp+0B8h+var_58]; struct CommonUtil::MpUtilsType *
0x14001dd59  test    rcx, rcx
0x14001dd5c  jz      short loc_14001DD6A
0x14001dd5e  call    ?Release@CMpUtilsUninitialize@CommonUtil@@SAXPEAUMpUtilsType@2@@Z; CommonUtil::CMpUtilsUninitialize::Release(CommonUtil::MpUtilsType *)
0x14001dd63  mov     rdi, cs:WPP_GLOBAL_Control
0x14001dd6a  cmp     rdi, rsi
0x14001dd6d  jz      loc_14001DE2E
0x14001dd73  jmp     short loc_14001DD8B
0x14001dd75  mov     rcx, [rdi+8]; RegistrationHandle
0x14001dd79  test    rcx, rcx
0x14001dd7c  jz      short loc_14001DD88
0x14001dd7e  call    cs:__imp_UnregisterTraceGuids
0x14001dd84  mov     [rdi+8], rbx
0x14001dd88  mov     rdi, [rdi]
0x14001dd8b  test    rdi, rdi
0x14001dd8e  jnz     short loc_14001DD75
0x14001dd90  jmp     loc_14001DE27
0x14001dd95  mov     edi, 12345678h
0x14001dd9a  mov     [rsp+0B8h+var_68.Guid], rdi
0x14001dd9f  lea     rcx, aMpcaDebug; "MpCa_Debug"
0x14001dda6  call    MpLookupMiscConfigFlag
0x14001ddab  test    eax, eax
0x14001ddad  jz      short loc_14001DDB5
0x14001ddaf  call    cs:__imp_DebugBreak
0x14001ddb5  xor     r9d, r9d; lpName
0x14001ddb8  xor     r8d, r8d; bInitialState
0x14001ddbb  mov     edx, r14d; bManualReset
0x14001ddbe  xor     ecx, ecx; lpEventAttributes
0x14001ddc0  call    cs:__imp_CreateEventW
0x14001ddc6  mov     cs:?g_hShutdownEvent@@3PEAXEA, rax; void * g_hShutdownEvent
0x14001ddcd  test    rax, rax
0x14001ddd0  jnz     short loc_14001DE36
0x14001ddd2  call    cs:__imp_GetLastError
0x14001ddd8  mov     edx, eax
0x14001ddda  lea     rcx, aCreateShutdown; "Create shutdown event failed: error cod"...
0x14001dde1  call    ?MpCmdLogPrintf@@YAXPEB_WZZ; MpCmdLogPrintf(wchar_t const *,...)
0x14001dde6  nop
0x14001dde7  call    cs:__imp_MpConfigUninitialize
0x14001dded  nop
0x14001ddee  mov     rcx, [rsp+0B8h+var_58]; struct CommonUtil::MpUtilsType *
0x14001ddf3  test    rcx, rcx
0x14001ddf6  jz      short loc_14001DDFE
0x14001ddf8  call    ?Release@CMpUtilsUninitialize@CommonUtil@@SAXPEAUMpUtilsType@2@@Z; CommonUtil::CMpUtilsUninitialize::Release(CommonUtil::MpUtilsType *)
0x14001ddfd  nop
0x14001ddfe  mov     rdi, cs:WPP_GLOBAL_Control
0x14001de05  cmp     rdi, rsi
0x14001de08  jz      short loc_14001DE2E
0x14001de0a  jmp     short loc_14001DE22
0x14001de0c  mov     rcx, [rdi+8]; RegistrationHandle
0x14001de10  test    rcx, rcx
0x14001de13  jz      short loc_14001DE1F
0x14001de15  call    cs:__imp_UnregisterTraceGuids
0x14001de1b  mov     [rdi+8], rbx
0x14001de1f  mov     rdi, [rdi]
0x14001de22  test    rdi, rdi
0x14001de25  jnz     short loc_14001DE0C
0x14001de27  mov     cs:WPP_GLOBAL_Control, rsi
0x14001de2e  mov     eax, r14d
0x14001de31  jmp     loc_14001E037
0x14001de36  mov     [rsp+0B8h+var_74], r14d
0x14001de3b  xorps   xmm0, xmm0
0x14001de3e  xor     eax, eax
0x14001de40  movups  [rsp+0B8h+var_50], xmm0
0x14001de45  movups  [rsp+0B8h+var_40], xmm0
0x14001de4a  movups  [rsp+0B8h+var_30], xmm0
0x14001de52  mov     [rsp+0B8h+var_20], rax
0x14001de5a  mov     qword ptr [rsp+0B8h+var_50], rbx
0x14001de5f  lea     rcx, [rsp+0B8h+var_50+8]; this
0x14001de64  call    ??0CopyAcceleratorRpc@@QEAA@XZ; CopyAcceleratorRpc::CopyAcceleratorRpc(void)
0x14001de69  nop
0x14001de6a  lea     rcx, [rsp+0B8h+var_50]; this
0x14001de6f  call    ?Initialize@CAutoInitCopyAccelerator@@QEAAJXZ; CAutoInitCopyAccelerator::Initialize(void)
0x14001de74  test    eax, eax
0x14001de76  jns     loc_14001DF01
0x14001de7c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001de83  cmp     rcx, rsi
0x14001de86  jz      short loc_14001DEA7
0x14001de88  test    [rcx+1Ch], r14b
0x14001de8c  jz      short loc_14001DEA7
0x14001de8e  mov     edx, 13h
0x14001de93  mov     r9d, eax
0x14001de96  lea     r8, WPP_d8286ee67877374a5cef524a3b6f17fd_Traceguids
0x14001de9d  mov     rcx, [rcx+10h]
0x14001dea1  call    WPP_SF_d
0x14001dea6  nop
0x14001dea7  lea     rcx, [rsp+0B8h+var_50]; this
0x14001deac  call    ??1CAutoInitCopyAccelerator@@QEAA@XZ; CAutoInitCopyAccelerator::~CAutoInitCopyAccelerator(void)
0x14001deb1  nop
0x14001deb2  call    cs:__imp_MpConfigUninitialize
0x14001deb8  nop
0x14001deb9  mov     rcx, [rsp+0B8h+var_58]; struct CommonUtil::MpUtilsType *
0x14001debe  test    rcx, rcx
0x14001dec1  jz      short loc_14001DEC9
0x14001dec3  call    ?Release@CMpUtilsUninitialize@CommonUtil@@SAXPEAUMpUtilsType@2@@Z; CommonUtil::CMpUtilsUninitialize::Release(CommonUtil::MpUtilsType *)
0x14001dec8  nop
0x14001dec9  mov     rdi, cs:WPP_GLOBAL_Control
0x14001ded0  cmp     rdi, rsi
0x14001ded3  jz      short loc_14001DEF9
0x14001ded5  jmp     short loc_14001DEED
0x14001ded7  mov     rcx, [rdi+8]; RegistrationHandle
0x14001dedb  test    rcx, rcx
0x14001dede  jz      short loc_14001DEEA
0x14001dee0  call    cs:__imp_UnregisterTraceGuids
0x14001dee6  mov     [rdi+8], rbx
0x14001deea  mov     rdi, [rdi]
0x14001deed  test    rdi, rdi
0x14001def0  jnz     short loc_14001DED7
0x14001def2  mov     cs:WPP_GLOBAL_Control, rsi
0x14001def9  mov     eax, r14d
0x14001defc  jmp     loc_14001E037
0x14001df01  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14001df04  mov     rcx, cs:?g_hShutdownEvent@@3PEAXEA; hHandle
0x14001df0b  call    cs:__imp_WaitForSingleObject
0x14001df11  mov     r15d, ebx
0x14001df14  test    eax, eax
0x14001df16  setnz   r15b
0x14001df1a  mov     [rsp+0B8h+var_74], r15d
0x14001df1f  lea     rcx, [rsp+0B8h+var_50]; this
0x14001df24  call    ??1CAutoInitCopyAccelerator@@QEAA@XZ; CAutoInitCopyAccelerator::~CAutoInitCopyAccelerator(void)
0x14001df29  nop
0x14001df2a  jmp     short loc_14001DF89
0x14001df2c  mov     r9d, [rsp+0B8h+var_78]
0x14001df31  xor     ebx, ebx
0x14001df33  test    r9d, r9d
0x14001df36  js      short loc_14001DF4D
0x14001df38  lea     rsi, WPP_GLOBAL_Control
0x14001df3f  mov     r15d, [rsp+0B8h+var_74]
0x14001df44  jmp     short loc_14001DF84
0x14001df46  xor     ebx, ebx
0x14001df48  mov     r9d, [rsp+0B8h+var_78]
0x14001df4d  mov     r15d, 2
0x14001df53  lea     rsi, WPP_GLOBAL_Control
0x14001df5a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001df61  cmp     rcx, rsi
0x14001df64  jz      short loc_14001DF84
0x14001df66  lea     r14d, [r15-1]
0x14001df6a  test    [rcx+1Ch], r14b
0x14001df6e  jz      short loc_14001DF84
0x14001df70  lea     edx, [r15+12h]
0x14001df74  lea     r8, WPP_d8286ee67877374a5cef524a3b6f17fd_Traceguids
0x14001df7b  mov     rcx, [rcx+10h]
0x14001df7f  call    WPP_SF_d
0x14001df84  mov     rdi, [rsp+0B8h+var_68.Guid]
0x14001df89  mov     rcx, cs:?g_hShutdownEvent@@3PEAXEA; hObject
0x14001df90  call    cs:__imp_CloseHandle
0x14001df96  call    ?GetInstance@CopyAcceleratorFeatures@@SAAEAV1@XZ; CopyAcceleratorFeatures::GetInstance(void)
0x14001df9b  mov     r14, rax
0x14001df9e  mov     rcx, [rax+8]
0x14001dfa2  test    rcx, rcx
0x14001dfa5  jz      short loc_14001DFB1
0x14001dfa7  call    cs:__imp_MpConfigUnregisterNotifications
0x14001dfad  mov     [r14+8], rbx
0x14001dfb1  mov     r14, cs:WPP_GLOBAL_Control
0x14001dfb8  cmp     r14, rsi
0x14001dfbb  jz      short loc_14001DFE3
0x14001dfbd  test    byte ptr [r14+1Ch], 4
0x14001dfc2  jz      short loc_14001DFE3
0x14001dfc4  mov     edx, 15h
0x14001dfc9  mov     r9d, r15d
0x14001dfcc  lea     r8, WPP_d8286ee67877374a5cef524a3b6f17fd_Traceguids
0x14001dfd3  mov     rcx, [r14+10h]
0x14001dfd7  call    WPP_SF_d
0x14001dfdc  mov     r14, cs:WPP_GLOBAL_Control
0x14001dfe3  test    rdi, rdi
0x14001dfe6  jz      short loc_14001DFF5
0x14001dfe8  call    cs:__imp_MpConfigUninitialize
0x14001dfee  mov     r14, cs:WPP_GLOBAL_Control
0x14001dff5  mov     rcx, [rsp+0B8h+var_58]; struct CommonUtil::MpUtilsType *
0x14001dffa  test    rcx, rcx
0x14001dffd  jz      short loc_14001E00B
0x14001dfff  call    ?Release@CMpUtilsUninitialize@CommonUtil@@SAXPEAUMpUtilsType@2@@Z; CommonUtil::CMpUtilsUninitialize::Release(CommonUtil::MpUtilsType *)
0x14001e004  mov     r14, cs:WPP_GLOBAL_Control
0x14001e00b  cmp     r14, rsi
0x14001e00e  jz      short loc_14001E034
0x14001e010  jmp     short loc_14001E028
0x14001e012  mov     rcx, [r14+8]; RegistrationHandle
0x14001e016  test    rcx, rcx
0x14001e019  jz      short loc_14001E025
0x14001e01b  call    cs:__imp_UnregisterTraceGuids
0x14001e021  mov     [r14+8], rbx
0x14001e025  mov     r14, [r14]
0x14001e028  test    r14, r14
0x14001e02b  jnz     short loc_14001E012
0x14001e02d  mov     cs:WPP_GLOBAL_Control, rsi
0x14001e034  mov     eax, r15d
0x14001e037  mov     rcx, [rsp+0B8h+var_10]
0x14001e03f  xor     rcx, rsp; StackCookie
0x14001e042  call    __security_check_cookie
0x14001e047  lea     r11, [rsp+0B8h+var_8]
0x14001e04f  mov     rbx, [r11+10h]
0x14001e053  mov     rsi, [r11+18h]
0x14001e057  mov     rdi, [r11+20h]
0x14001e05b  mov     r14, [r11+28h]
0x14001e05f  mov     rsp, r11
0x14001e062  pop     r15
0x14001e064  retn
```
