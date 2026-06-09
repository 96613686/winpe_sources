# SvchostMain

- ea: `0x180012de0`
- end: `0x18001305c`
- name: `SvchostMain`
- size: `636`
- prototype: `void()`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18000a644`
- `0x18000a778`
- `0x1800110f0`
- `0x180011284`
- `0x1800127bc`
- `0x180012974`
- `0x180012c9c`
- `0x180012de0`
- `0x1800130b8`
- `0x180013138`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012e68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012f22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012e68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012f22`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180012e56`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180012e56`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180012f10`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180012f10`

## pseudocode

```c
void SvchostMain()
{
  _QWORD *v0; // rcx
  int v1; // edi
  signed int updated; // ebx
  _QWORD *v3; // rcx
  __int64 v4; // rdx
  signed int LastError; // eax
  int v6; // edx
  _QWORD *v7; // rcx

  v0 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_3f50365df99735211a88e8fb382b12e7_Traceguids);
    v0 = WPP_GLOBAL_Control;
  }
  v1 = 0;
  if ( g_cThreads && v0 != &WPP_GLOBAL_Control && (*((_BYTE *)v0 + 28) & 2) != 0 )
    WPP_SF_d(v0[2], 32, &WPP_3f50365df99735211a88e8fb382b12e7_Traceguids);
  g_ThreadsCompletedEvent = CreateEventW(0, 1, 1, 0);
  if ( !g_ThreadsCompletedEvent )
  {
    GetLastError();
    goto LABEL_41;
  }
  IncThreadCount("SvchostMain", 0xD9u);
  if ( !g_SvchostGlobals )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_3f50365df99735211a88e8fb382b12e7_Traceguids);
    updated = 0;
    goto LABEL_40;
  }
  updated = SMInitialize();
  if ( updated < 0 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_40;
    v4 = 34;
    goto LABEL_39;
  }
  g_hService = RegisterServiceCtrlHandlerExW(L"NcdAutoSetup", SvchostControlHandler, 0);
  if ( g_hService )
  {
    updated = InitializeService();
    if ( updated >= 0 )
    {
      v1 = 1;
      updated = UpdateServiceStatus(4u, v6);
      if ( updated >= 0 )
      {
        updated = SMStart();
        if ( updated >= 0 )
          goto LABEL_40;
        v3 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_40;
        v4 = 38;
      }
      else
      {
        v3 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_40;
        v4 = 37;
      }
    }
    else
    {
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_40;
      v4 = 36;
    }
LABEL_39:
    WPP_SF_d(v3[2], v4, &WPP_3f50365df99735211a88e8fb382b12e7_Traceguids);
    goto LABEL_40;
  }
  LastError = GetLastError();
  updated = LastError;
  if ( LastError > 0 )
    updated = (unsigned __int16)LastError | 0x80070000;
  if ( updated >= 0 )
    updated = -2147467259;
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v4 = 35;
    goto LABEL_39;
  }
LABEL_40:
  DecThreadCount("SvchostMain", 0x107u);
  if ( updated >= 0 )
  {
LABEL_46:
    v7 = WPP_GLOBAL_Control;
    goto LABEL_47;
  }
LABEL_41:
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_3f50365df99735211a88e8fb382b12e7_Traceguids);
    v7 = WPP_GLOBAL_Control;
  }
  if ( v1 )
  {
    StopService();
    goto LABEL_46;
  }
LABEL_47:
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x20) != 0 )
    WPP_SF_(v7[2], 40, &WPP_3f50365df99735211a88e8fb382b12e7_Traceguids);
}

```

## disassembly

```asm
0x180012de0  push    rbx
0x180012de2  push    rsi
0x180012de3  push    rdi
0x180012de4  push    r14
0x180012de6  sub     rsp, 28h
0x180012dea  mov     rcx, cs:WPP_GLOBAL_Control
0x180012df1  lea     rsi, WPP_GLOBAL_Control
0x180012df8  lea     r14, WPP_3f50365df99735211a88e8fb382b12e7_Traceguids
0x180012dff  cmp     rcx, rsi
0x180012e02  jz      short loc_180012E22
0x180012e04  test    byte ptr [rcx+1Ch], 20h
0x180012e08  jz      short loc_180012E22
0x180012e0a  mov     rcx, [rcx+10h]
0x180012e0e  mov     edx, 1Fh
0x180012e13  mov     r8, r14
0x180012e16  call    WPP_SF_
0x180012e1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180012e22  mov     r9d, cs:?g_cThreads@@3KA; ulong g_cThreads
0x180012e29  xor     edi, edi
0x180012e2b  test    r9d, r9d
0x180012e2e  jz      short loc_180012E4A
0x180012e30  cmp     rcx, rsi
0x180012e33  jz      short loc_180012E4A
0x180012e35  test    byte ptr [rcx+1Ch], 2
0x180012e39  jz      short loc_180012E4A
0x180012e3b  mov     rcx, [rcx+10h]
0x180012e3f  lea     edx, [rdi+20h]
0x180012e42  mov     r8, r14
0x180012e45  call    WPP_SF_d
0x180012e4a  xor     r9d, r9d; lpName
0x180012e4d  xor     ecx, ecx; lpEventAttributes
0x180012e4f  lea     edx, [r9+1]; bManualReset
0x180012e53  mov     r8d, edx; bInitialState
0x180012e56  call    cs:__imp_CreateEventW
0x180012e5c  mov     cs:?g_ThreadsCompletedEvent@@3PEAXEA, rax; void * g_ThreadsCompletedEvent
0x180012e63  test    rax, rax
0x180012e66  jnz     short loc_180012E8C
0x180012e68  call    cs:__imp_GetLastError
0x180012e6e  mov     ebx, eax
0x180012e70  test    eax, eax
0x180012e72  jle     short loc_180012E7D
0x180012e74  movzx   ebx, ax
0x180012e77  or      ebx, 80070000h
0x180012e7d  test    ebx, ebx
0x180012e7f  mov     eax, 80004005h
0x180012e84  cmovns  ebx, eax
0x180012e87  jmp     loc_180012FF9
0x180012e8c  mov     edx, 0D9h; unsigned int
0x180012e91  lea     rcx, aSvchostmain_0; "SvchostMain"
0x180012e98  call    ?IncThreadCount@@YAXPEBDK@Z; IncThreadCount(char const *,ulong)
0x180012e9d  cmp     cs:?g_SvchostGlobals@@3PEAU_SVCHOST_GLOBAL_DATA@@EA, rdi; _SVCHOST_GLOBAL_DATA * g_SvchostGlobals
0x180012ea4  jnz     short loc_180012ED0
0x180012ea6  mov     rcx, cs:WPP_GLOBAL_Control
0x180012ead  cmp     rcx, rsi
0x180012eb0  jz      short loc_180012EC9
0x180012eb2  test    byte ptr [rcx+1Ch], 2
0x180012eb6  jz      short loc_180012EC9
0x180012eb8  mov     rcx, [rcx+10h]
0x180012ebc  mov     edx, 21h ; '!'
0x180012ec1  mov     r8, r14
0x180012ec4  call    WPP_SF_
0x180012ec9  xor     ebx, ebx
0x180012ecb  jmp     loc_180012FE4
0x180012ed0  call    ?SMInitialize@@YAJXZ; SMInitialize(void)
0x180012ed5  mov     ebx, eax
0x180012ed7  test    eax, eax
0x180012ed9  jns     short loc_180012EFF
0x180012edb  mov     rcx, cs:WPP_GLOBAL_Control
0x180012ee2  cmp     rcx, rsi
0x180012ee5  jz      loc_180012FE4
0x180012eeb  test    byte ptr [rcx+1Ch], 2
0x180012eef  jz      loc_180012FE4
0x180012ef5  mov     edx, 22h ; '"'
0x180012efa  jmp     loc_180012FD5
0x180012eff  xor     r8d, r8d; lpContext
0x180012f02  lea     rdx, ?SvchostControlHandler@@YAKKKPEAX0@Z; lpHandlerProc
0x180012f09  lea     rcx, ServiceName; "NcdAutoSetup"
0x180012f10  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180012f16  mov     cs:?g_hService@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rax; SERVICE_STATUS_HANDLE__ * g_hService
0x180012f1d  test    rax, rax
0x180012f20  jnz     short loc_180012F65
0x180012f22  call    cs:__imp_GetLastError
0x180012f28  mov     ebx, eax
0x180012f2a  test    eax, eax
0x180012f2c  jle     short loc_180012F37
0x180012f2e  movzx   ebx, ax
0x180012f31  or      ebx, 80070000h
0x180012f37  test    ebx, ebx
0x180012f39  mov     eax, 80004005h
0x180012f3e  cmovns  ebx, eax
0x180012f41  mov     rcx, cs:WPP_GLOBAL_Control
0x180012f48  cmp     rcx, rsi
0x180012f4b  jz      loc_180012FE4
0x180012f51  test    byte ptr [rcx+1Ch], 2
0x180012f55  jz      loc_180012FE4
0x180012f5b  mov     edx, 23h ; '#'
0x180012f60  mov     r9d, ebx
0x180012f63  jmp     short loc_180012FD8
0x180012f65  call    ?InitializeService@@YAJXZ; InitializeService(void)
0x180012f6a  mov     ebx, eax
0x180012f6c  test    eax, eax
0x180012f6e  jns     short loc_180012F89
0x180012f70  mov     rcx, cs:WPP_GLOBAL_Control
0x180012f77  cmp     rcx, rsi
0x180012f7a  jz      short loc_180012FE4
0x180012f7c  test    byte ptr [rcx+1Ch], 2
0x180012f80  jz      short loc_180012FE4
0x180012f82  mov     edx, 24h ; '$'
0x180012f87  jmp     short loc_180012FD5
0x180012f89  mov     edi, 1
0x180012f8e  lea     ecx, [rdi+3]; unsigned int
0x180012f91  call    ?UpdateServiceStatus@@YAJKJ@Z; UpdateServiceStatus(ulong,long)
0x180012f96  mov     ebx, eax
0x180012f98  test    eax, eax
0x180012f9a  jns     short loc_180012FB3
0x180012f9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180012fa3  cmp     rcx, rsi
0x180012fa6  jz      short loc_180012FE4
0x180012fa8  test    byte ptr [rcx+1Ch], 2
0x180012fac  jz      short loc_180012FE4
0x180012fae  lea     edx, [rdi+24h]
0x180012fb1  jmp     short loc_180012FD5
0x180012fb3  call    ?SMStart@@YAJXZ; SMStart(void)
0x180012fb8  mov     ebx, eax
0x180012fba  test    eax, eax
0x180012fbc  jns     short loc_180012FE4
0x180012fbe  mov     rcx, cs:WPP_GLOBAL_Control
0x180012fc5  cmp     rcx, rsi
0x180012fc8  jz      short loc_180012FE4
0x180012fca  test    byte ptr [rcx+1Ch], 2
0x180012fce  jz      short loc_180012FE4
0x180012fd0  mov     edx, 26h ; '&'
0x180012fd5  mov     r9d, eax
0x180012fd8  mov     rcx, [rcx+10h]
0x180012fdc  mov     r8, r14
0x180012fdf  call    WPP_SF_d
0x180012fe4  mov     edx, 107h; unsigned int
0x180012fe9  lea     rcx, aSvchostmain_0; "SvchostMain"
0x180012ff0  call    ?DecThreadCount@@YAXPEBDK@Z; DecThreadCount(char const *,ulong)
0x180012ff5  test    ebx, ebx
0x180012ff7  jns     short loc_18001302F
0x180012ff9  mov     rcx, cs:WPP_GLOBAL_Control
0x180013000  cmp     rcx, rsi
0x180013003  jz      short loc_180013026
0x180013005  test    byte ptr [rcx+1Ch], 2
0x180013009  jz      short loc_180013026
0x18001300b  mov     rcx, [rcx+10h]
0x18001300f  mov     edx, 27h ; '''
0x180013014  mov     r9d, ebx
0x180013017  mov     r8, r14
0x18001301a  call    WPP_SF_d
0x18001301f  mov     rcx, cs:WPP_GLOBAL_Control
0x180013026  test    edi, edi
0x180013028  jz      short loc_180013036
0x18001302a  call    ?StopService@@YAJXZ; StopService(void)
0x18001302f  mov     rcx, cs:WPP_GLOBAL_Control
0x180013036  cmp     rcx, rsi
0x180013039  jz      short loc_180013052
0x18001303b  test    byte ptr [rcx+1Ch], 20h
0x18001303f  jz      short loc_180013052
0x180013041  mov     rcx, [rcx+10h]
0x180013045  mov     edx, 28h ; '('
0x18001304a  mov     r8, r14
0x18001304d  call    WPP_SF_
0x180013052  add     rsp, 28h
0x180013056  pop     r14
0x180013058  pop     rdi
0x180013059  pop     rsi
0x18001305a  pop     rbx
0x18001305b  retn
```
