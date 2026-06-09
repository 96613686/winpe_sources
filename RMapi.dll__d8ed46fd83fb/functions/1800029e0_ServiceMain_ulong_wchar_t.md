# ServiceMain(ulong,wchar_t * *)

- ea: `0x1800029e0`
- end: `0x180002bfe`
- name: `?ServiceMain@@YAXKPEAPEA_W@Z`
- size: `542`
- prototype: `void __fastcall(__int64, wchar_t **)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callees

- `0x1800029e0`
- `0x180002ec0`
- `0x180003180`
- `0x180003d50`
- `0x180003d78`
- `0x18000afa0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002be8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002be8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180002ba9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180002ba9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002a9e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180002a9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002a43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002ab0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002a43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002ab0`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180002a31`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180002a31`

## pseudocode

```c
void __fastcall ServiceMain(__int64 a1, wchar_t **a2)
{
  unsigned int v2; // edx
  signed int LastError; // eax
  __int64 v4; // rcx
  signed int v5; // eax
  unsigned int v6; // edx
  unsigned int v7; // ebx
  __int64 v8; // r9
  int v9; // eax
  RadioModule *v10; // rcx
  unsigned int v11; // edx

  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 10, WPP_d42538173eb033b5db6066a79c0c461a_Traceguids);
  hServiceStatus = RegisterServiceCtrlHandlerExW(L"RMsvc", RmServiceNotificationHandler, 0);
  if ( !hServiceStatus )
  {
    LastError = GetLastError();
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        11,
        WPP_d42538173eb033b5db6066a79c0c461a_Traceguids,
        (unsigned int)LastError);
    }
    return;
  }
  RmReportServiceStatus(2u, v2);
  g_ServiceStopEvent = CreateEventW(0, 1, 0, 0);
  if ( !g_ServiceStopEvent )
  {
    v5 = GetLastError();
    v7 = v5;
    v4 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      if ( v5 > 0 )
        v8 = (unsigned __int16)v5 | 0x80070000;
      else
        v8 = (unsigned int)v5;
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 12, WPP_d42538173eb033b5db6066a79c0c461a_Traceguids, v8);
      v4 = WPP_GLOBAL_Control;
    }
    if ( v7 )
      goto LABEL_25;
  }
  v9 = RadioModule::Initialize((RadioModule *)v4);
  v7 = v9;
  if ( v9 >= 0 )
  {
    v4 = WPP_GLOBAL_Control;
  }
  else
  {
    v4 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        13,
        WPP_d42538173eb033b5db6066a79c0c461a_Traceguids,
        (unsigned int)v9);
      v4 = WPP_GLOBAL_Control;
    }
    if ( (v7 & 0x1FFF0000) == 0x70000 )
      v7 = (unsigned __int16)v7;
    if ( v7 )
    {
LABEL_25:
      if ( (_UNKNOWN *)v4 != &WPP_GLOBAL_Control && (*(_BYTE *)(v4 + 28) & 4) != 0 )
        WPP_SF_d(*(_QWORD *)(v4 + 16), 14, WPP_d42538173eb033b5db6066a79c0c461a_Traceguids, v7);
      RmReportServiceStatus(1u, v6);
      return;
    }
  }
  if ( (_UNKNOWN *)v4 != &WPP_GLOBAL_Control && (*(_BYTE *)(v4 + 28) & 4) != 0 )
    WPP_SF_(*(_QWORD *)(v4 + 16), 15, WPP_d42538173eb033b5db6066a79c0c461a_Traceguids);
  RmReportServiceStatus(4u, v6);
  WaitForSingleObject(g_ServiceStopEvent, 0xFFFFFFFF);
  RadioModule::Uninitialize(v10);
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 16, WPP_d42538173eb033b5db6066a79c0c461a_Traceguids);
  RmReportServiceStatus(1u, v11);
  CloseHandle(g_ServiceStopEvent);
}

```

## disassembly

```asm
0x1800029e0  mov     [rsp+arg_0], rbx
0x1800029e5  mov     [rsp+arg_8], rbp
0x1800029ea  push    rsi
0x1800029eb  sub     rsp, 20h
0x1800029ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800029f6  lea     rsi, WPP_GLOBAL_Control
0x1800029fd  lea     rbp, WPP_d42538173eb033b5db6066a79c0c461a_Traceguids
0x180002a04  cmp     rcx, rsi
0x180002a07  jz      short loc_180002A20
0x180002a09  test    byte ptr [rcx+1Ch], 4
0x180002a0d  jz      short loc_180002A20
0x180002a0f  mov     rcx, [rcx+10h]
0x180002a13  mov     edx, 0Ah
0x180002a18  mov     r8, rbp
0x180002a1b  call    WPP_SF_
0x180002a20  xor     r8d, r8d; lpContext
0x180002a23  lea     rdx, ?RmServiceNotificationHandler@@YAKKKPEAX0@Z; lpHandlerProc
0x180002a2a  lea     rcx, ServiceName; "RMsvc"
0x180002a31  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180002a37  mov     cs:hServiceStatus, rax
0x180002a3e  test    rax, rax
0x180002a41  jnz     short loc_180002A88
0x180002a43  call    cs:__imp_GetLastError
0x180002a49  mov     rcx, cs:WPP_GLOBAL_Control
0x180002a50  cmp     rcx, rsi
0x180002a53  jz      loc_180002BEE
0x180002a59  test    byte ptr [rcx+1Ch], 1
0x180002a5d  jz      loc_180002BEE
0x180002a63  test    eax, eax
0x180002a65  jle     short loc_180002A6F
0x180002a67  movzx   eax, ax
0x180002a6a  or      eax, 80070000h
0x180002a6f  mov     rcx, [rcx+10h]
0x180002a73  mov     edx, 0Bh
0x180002a78  mov     r9d, eax
0x180002a7b  mov     r8, rbp
0x180002a7e  call    WPP_SF_d
0x180002a83  jmp     loc_180002BEE
0x180002a88  mov     ecx, 2; unsigned int
0x180002a8d  call    ?RmReportServiceStatus@@YAXKK@Z; RmReportServiceStatus(ulong,ulong)
0x180002a92  xor     r9d, r9d; lpName
0x180002a95  xor     r8d, r8d; bInitialState
0x180002a98  xor     ecx, ecx; lpEventAttributes
0x180002a9a  lea     edx, [r9+1]; bManualReset
0x180002a9e  call    cs:__imp_CreateEventW
0x180002aa4  mov     cs:?g_ServiceStopEvent@@3PEAXEA, rax; void * g_ServiceStopEvent
0x180002aab  test    rax, rax
0x180002aae  jnz     short loc_180002AFA
0x180002ab0  call    cs:__imp_GetLastError
0x180002ab6  mov     ebx, eax
0x180002ab8  mov     rcx, cs:WPP_GLOBAL_Control
0x180002abf  cmp     rcx, rsi
0x180002ac2  jz      short loc_180002AF6
0x180002ac4  test    byte ptr [rcx+1Ch], 1
0x180002ac8  jz      short loc_180002AF6
0x180002aca  test    eax, eax
0x180002acc  jg      short loc_180002AD3
0x180002ace  mov     r9d, eax
0x180002ad1  jmp     short loc_180002ADE
0x180002ad3  movzx   r9d, bx
0x180002ad7  or      r9d, 80070000h
0x180002ade  mov     rcx, [rcx+10h]
0x180002ae2  mov     edx, 0Ch
0x180002ae7  mov     r8, rbp
0x180002aea  call    WPP_SF_d
0x180002aef  mov     rcx, cs:WPP_GLOBAL_Control; this
0x180002af6  test    ebx, ebx
0x180002af8  jnz     short loc_180002B47
0x180002afa  call    ?Initialize@RadioModule@@QEAAJXZ; RadioModule::Initialize(void)
0x180002aff  mov     ebx, eax
0x180002b01  test    eax, eax
0x180002b03  jns     short loc_180002B72
0x180002b05  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b0c  cmp     rcx, rsi
0x180002b0f  jz      short loc_180002B32
0x180002b11  test    byte ptr [rcx+1Ch], 1
0x180002b15  jz      short loc_180002B32
0x180002b17  mov     rcx, [rcx+10h]
0x180002b1b  mov     edx, 0Dh
0x180002b20  mov     r9d, eax
0x180002b23  mov     r8, rbp
0x180002b26  call    WPP_SF_d
0x180002b2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b32  mov     eax, ebx
0x180002b34  and     eax, 1FFF0000h
0x180002b39  cmp     eax, 70000h
0x180002b3e  jnz     short loc_180002B43
0x180002b40  movzx   ebx, bx
0x180002b43  test    ebx, ebx
0x180002b45  jz      short loc_180002B79
0x180002b47  cmp     rcx, rsi
0x180002b4a  jz      short loc_180002B66
0x180002b4c  test    byte ptr [rcx+1Ch], 4
0x180002b50  jz      short loc_180002B66
0x180002b52  mov     rcx, [rcx+10h]
0x180002b56  mov     edx, 0Eh
0x180002b5b  mov     r9d, ebx
0x180002b5e  mov     r8, rbp
0x180002b61  call    WPP_SF_d
0x180002b66  mov     ecx, 1; unsigned int
0x180002b6b  call    ?RmReportServiceStatus@@YAXKK@Z; RmReportServiceStatus(ulong,ulong)
0x180002b70  jmp     short loc_180002BEE
0x180002b72  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b79  cmp     rcx, rsi
0x180002b7c  jz      short loc_180002B95
0x180002b7e  test    byte ptr [rcx+1Ch], 4
0x180002b82  jz      short loc_180002B95
0x180002b84  mov     rcx, [rcx+10h]
0x180002b88  mov     edx, 0Fh
0x180002b8d  mov     r8, rbp
0x180002b90  call    WPP_SF_
0x180002b95  mov     ecx, 4; unsigned int
0x180002b9a  call    ?RmReportServiceStatus@@YAXKK@Z; RmReportServiceStatus(ulong,ulong)
0x180002b9f  mov     rcx, cs:?g_ServiceStopEvent@@3PEAXEA; hHandle
0x180002ba6  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180002ba9  call    cs:__imp_WaitForSingleObject
0x180002baf  call    ?Uninitialize@RadioModule@@QEAAXXZ; RadioModule::Uninitialize(void)
0x180002bb4  mov     rcx, cs:WPP_GLOBAL_Control
0x180002bbb  cmp     rcx, rsi
0x180002bbe  jz      short loc_180002BD7
0x180002bc0  test    byte ptr [rcx+1Ch], 4
0x180002bc4  jz      short loc_180002BD7
0x180002bc6  mov     rcx, [rcx+10h]
0x180002bca  mov     edx, 10h
0x180002bcf  mov     r8, rbp
0x180002bd2  call    WPP_SF_
0x180002bd7  mov     ecx, 1; unsigned int
0x180002bdc  call    ?RmReportServiceStatus@@YAXKK@Z; RmReportServiceStatus(ulong,ulong)
0x180002be1  mov     rcx, cs:?g_ServiceStopEvent@@3PEAXEA; hObject
0x180002be8  call    cs:__imp_CloseHandle
0x180002bee  mov     rbx, [rsp+28h+arg_0]
0x180002bf3  mov     rbp, [rsp+28h+arg_8]
0x180002bf8  add     rsp, 20h
0x180002bfc  pop     rsi
0x180002bfd  retn
```
