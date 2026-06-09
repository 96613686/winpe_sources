# RmServiceNotificationHandler(ulong,ulong,void *,void *)

- ea: `0x180002f20`
- end: `0x180003179`
- name: `?RmServiceNotificationHandler@@YAKKKPEAX0@Z`
- size: `601`
- prototype: `DWORD __stdcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callees

- `0x180002ec0`
- `0x180002f20`
- `0x180003180`
- `0x180003ce0`
- `0x180003d50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180002f91`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180003072`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180002f91`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180003072`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180002fcb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180002fcb`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180003110`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180003110`

## pseudocode

```c
__int64 __fastcall RmServiceNotificationHandler(
        DWORD dwControl,
        DWORD dwEventType,
        LPVOID lpEventData,
        LPVOID lpContext)
{
  __int64 v5; // rcx
  unsigned int v7; // ebx
  DWORD v8; // edi
  __int64 v9; // rdx
  const wchar_t *v10; // r9

  v5 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
  {
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 17, WPP_d42538173eb033b5db6066a79c0c461a_Traceguids, dwControl);
    v5 = WPP_GLOBAL_Control;
  }
  if ( dwControl == 4 )
  {
    if ( (_UNKNOWN *)v5 == &WPP_GLOBAL_Control || (*(_BYTE *)(v5 + 28) & 4) == 0 )
      return 0;
    v9 = 22;
LABEL_17:
    WPP_SF_(*(_QWORD *)(v5 + 16), v9, WPP_d42538173eb033b5db6066a79c0c461a_Traceguids);
    return 0;
  }
  v7 = dwControl - 1;
  if ( v7 )
  {
    if ( v7 == 31 )
    {
      if ( WaitForSingleObject(g_ServiceStopEvent, 0) )
      {
        v5 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) == 0 )
          return 0;
        v9 = 21;
        goto LABEL_17;
      }
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 20, WPP_d42538173eb033b5db6066a79c0c461a_Traceguids);
      return 1115;
    }
    else
    {
      if ( (_UNKNOWN *)v5 != &WPP_GLOBAL_Control && (*(_BYTE *)(v5 + 28) & 4) != 0 )
        WPP_SF_(*(_QWORD *)(v5 + 16), 23, WPP_d42538173eb033b5db6066a79c0c461a_Traceguids);
      return 120;
    }
  }
  else
  {
LABEL_8:
    RmReportServiceStatus(3u);
    while ( 1 )
    {
      v8 = WaitForSingleObject(g_ServiceStopEvent, 0);
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      {
        v10 = L"true";
        if ( !v8 )
          v10 = L"false";
        WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 23, WPP_ca79b6ae5c6e3755e5d5afc497605ed9_Traceguids, v10);
      }
      if ( !v8 || v7 >= 0x32 )
        break;
      Sleep(0x64u);
      ++v7;
      if ( v7 == 10 * (v7 / 0xA) )
        goto LABEL_8;
    }
    if ( v7 != 50 )
    {
      SetEvent(g_ServiceStopEvent);
      v5 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) == 0 )
        return 0;
      v9 = 19;
      goto LABEL_17;
    }
    RmReportServiceStatus(4u);
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 18, WPP_d42538173eb033b5db6066a79c0c461a_Traceguids);
    return 170;
  }
}

```

## disassembly

```asm
0x180002f20  mov     [rsp+arg_10], rbx
0x180002f25  push    rsi
0x180002f26  sub     rsp, 20h
0x180002f2a  mov     ebx, ecx
0x180002f2c  mov     rcx, cs:WPP_GLOBAL_Control
0x180002f33  lea     rsi, WPP_GLOBAL_Control
0x180002f3a  cmp     rcx, rsi
0x180002f3d  jz      short loc_180002F49
0x180002f3f  test    byte ptr [rcx+1Ch], 4
0x180002f43  jnz     loc_180002FF2
0x180002f49  cmp     ebx, 4
0x180002f4c  jnz     short loc_180002F64
0x180002f4e  cmp     rcx, rsi
0x180002f51  jnz     loc_180003016
0x180002f57  xor     eax, eax
0x180002f59  mov     rbx, [rsp+28h+arg_10]
0x180002f5e  add     rsp, 20h
0x180002f62  pop     rsi
0x180002f63  retn
0x180002f64  sub     ebx, 1
0x180002f67  jnz     loc_18000303A
0x180002f6d  mov     [rsp+28h+arg_0], rbp
0x180002f72  mov     ecx, 3; unsigned int
0x180002f77  mov     [rsp+28h+arg_8], rdi
0x180002f7c  call    ?RmReportServiceStatus@@YAXKK@Z; RmReportServiceStatus(ulong,ulong)
0x180002f81  lea     rbp, aFalse_0; "false"
0x180002f88  mov     rcx, cs:?g_ServiceStopEvent@@3PEAXEA; hHandle
0x180002f8f  xor     edx, edx; dwMilliseconds
0x180002f91  call    cs:__imp_WaitForSingleObject
0x180002f97  mov     edi, eax
0x180002f99  mov     rcx, cs:WPP_GLOBAL_Control
0x180002fa0  cmp     rcx, rsi
0x180002fa3  jnz     loc_1800030D1
0x180002fa9  test    edi, edi
0x180002fab  jnz     loc_180003102
0x180002fb1  mov     rdi, [rsp+28h+arg_8]
0x180002fb6  mov     rbp, [rsp+28h+arg_0]
0x180002fbb  cmp     ebx, 32h ; '2'
0x180002fbe  jz      loc_18000313E
0x180002fc4  mov     rcx, cs:?g_ServiceStopEvent@@3PEAXEA; hEvent
0x180002fcb  call    cs:__imp_SetEvent
0x180002fd1  mov     rcx, cs:WPP_GLOBAL_Control
0x180002fd8  cmp     rcx, rsi
0x180002fdb  jz      loc_180002F57
0x180002fe1  test    byte ptr [rcx+1Ch], 4
0x180002fe5  jz      loc_180002F57
0x180002feb  mov     edx, 13h
0x180002ff0  jmp     short loc_180003025
0x180002ff2  mov     rcx, [rcx+10h]
0x180002ff6  lea     r8, WPP_d42538173eb033b5db6066a79c0c461a_Traceguids
0x180002ffd  mov     edx, 11h
0x180003002  mov     r9d, ebx
0x180003005  call    WPP_SF_d
0x18000300a  mov     rcx, cs:WPP_GLOBAL_Control
0x180003011  jmp     loc_180002F49
0x180003016  test    byte ptr [rcx+1Ch], 4
0x18000301a  jz      loc_180002F57
0x180003020  mov     edx, 16h
0x180003025  mov     rcx, [rcx+10h]
0x180003029  lea     r8, WPP_d42538173eb033b5db6066a79c0c461a_Traceguids
0x180003030  call    WPP_SF_
0x180003035  jmp     loc_180002F57
0x18000303a  cmp     ebx, 1Fh
0x18000303d  jz      short loc_180003069
0x18000303f  cmp     rcx, rsi
0x180003042  jz      short loc_18000305F
0x180003044  test    byte ptr [rcx+1Ch], 4
0x180003048  jz      short loc_18000305F
0x18000304a  mov     rcx, [rcx+10h]
0x18000304e  lea     r8, WPP_d42538173eb033b5db6066a79c0c461a_Traceguids
0x180003055  mov     edx, 17h
0x18000305a  call    WPP_SF_
0x18000305f  mov     eax, 78h ; 'x'
0x180003064  jmp     loc_180002F59
0x180003069  mov     rcx, cs:?g_ServiceStopEvent@@3PEAXEA; hHandle
0x180003070  xor     edx, edx; dwMilliseconds
0x180003072  call    cs:__imp_WaitForSingleObject
0x180003078  test    eax, eax
0x18000307a  jnz     short loc_1800030AD
0x18000307c  mov     rcx, cs:WPP_GLOBAL_Control
0x180003083  cmp     rcx, rsi
0x180003086  jz      short loc_1800030A3
0x180003088  test    byte ptr [rcx+1Ch], 4
0x18000308c  jz      short loc_1800030A3
0x18000308e  mov     rcx, [rcx+10h]
0x180003092  lea     r8, WPP_d42538173eb033b5db6066a79c0c461a_Traceguids
0x180003099  mov     edx, 14h
0x18000309e  call    WPP_SF_
0x1800030a3  mov     eax, 45Bh
0x1800030a8  jmp     loc_180002F59
0x1800030ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800030b4  cmp     rcx, rsi
0x1800030b7  jz      loc_180002F57
0x1800030bd  test    byte ptr [rcx+1Ch], 4
0x1800030c1  jz      loc_180002F57
0x1800030c7  mov     edx, 15h
0x1800030cc  jmp     loc_180003025
0x1800030d1  test    byte ptr [rcx+1Ch], 4
0x1800030d5  jz      loc_180002FA9
0x1800030db  mov     rcx, [rcx+10h]
0x1800030df  lea     r9, aTrue; "true"
0x1800030e6  test    edi, edi
0x1800030e8  lea     r8, WPP_ca79b6ae5c6e3755e5d5afc497605ed9_Traceguids
0x1800030ef  mov     edx, 17h
0x1800030f4  cmovz   r9, rbp
0x1800030f8  call    WPP_SF_S
0x1800030fd  jmp     loc_180002FA9
0x180003102  cmp     ebx, 32h ; '2'
0x180003105  jnb     loc_180002FB1
0x18000310b  mov     ecx, 64h ; 'd'; dwMilliseconds
0x180003110  call    cs:__imp_Sleep
0x180003116  inc     ebx
0x180003118  mov     eax, 0CCCCCCCDh
0x18000311d  mul     ebx
0x18000311f  shr     edx, 3; unsigned int
0x180003122  lea     ecx, [rdx+rdx*4]
0x180003125  add     ecx, ecx
0x180003127  cmp     ebx, ecx
0x180003129  jnz     loc_180002F88
0x18000312f  mov     ecx, 3; unsigned int
0x180003134  call    ?RmReportServiceStatus@@YAXKK@Z; RmReportServiceStatus(ulong,ulong)
0x180003139  jmp     loc_180002F88
0x18000313e  mov     ecx, 4; unsigned int
0x180003143  call    ?RmReportServiceStatus@@YAXKK@Z; RmReportServiceStatus(ulong,ulong)
0x180003148  mov     rcx, cs:WPP_GLOBAL_Control
0x18000314f  cmp     rcx, rsi
0x180003152  jz      short loc_18000316F
0x180003154  test    byte ptr [rcx+1Ch], 4
0x180003158  jz      short loc_18000316F
0x18000315a  mov     rcx, [rcx+10h]
0x18000315e  lea     r8, WPP_d42538173eb033b5db6066a79c0c461a_Traceguids
0x180003165  mov     edx, 12h
0x18000316a  call    WPP_SF_
0x18000316f  mov     eax, 0AAh
0x180003174  jmp     loc_180002F59
```
