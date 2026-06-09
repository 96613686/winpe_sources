# ServiceMain

- ea: `0x180006040`
- end: `0x18000613a`
- name: `ServiceMain`
- size: `250`
- prototype: `void()`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callees

- `0x180005ac0`
- `0x180005bc4`
- `0x180005ec0`
- `0x180005f28`
- `0x180006040`
- `0x180006140`

## import_xrefs

- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerW` at `0x18000608d`
- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerW` at `0x18000608d`

## pseudocode

```c
void ServiceMain()
{
  _UNKNOWN **v0; // rcx
  bool v1; // zf

  WppEnable();
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_27ea2efe8112346a6f92681e48c92895_Traceguids);
  }
  g_SvcStatusHandle = RegisterServiceCtrlHandlerW(L"ApxSvc", SvcCtrlHandler);
  if ( g_SvcStatusHandle )
  {
    g_SvcStatus.dwServiceType = 16;
    g_SvcStatus.dwServiceSpecificExitCode = 0;
    ReportSvcStatus(2u, 0, 0xBB8u);
    SvcInit();
    v0 = (_UNKNOWN **)WPP_GLOBAL_Control;
    v1 = WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control;
  }
  else
  {
    v0 = (_UNKNOWN **)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_16;
    if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_27ea2efe8112346a6f92681e48c92895_Traceguids);
      v0 = (_UNKNOWN **)WPP_GLOBAL_Control;
    }
    v1 = v0 == &WPP_GLOBAL_Control;
  }
  if ( !v1 && (*((_BYTE *)v0 + 28) & 1) != 0 && *((_BYTE *)v0 + 25) >= 5u )
    WPP_SF_(v0[2], 21, &WPP_27ea2efe8112346a6f92681e48c92895_Traceguids);
LABEL_16:
  WppCleanup();
}

```

## disassembly

```asm
0x180006040  push    rdi
0x180006042  sub     rsp, 20h
0x180006046  call    ?WppEnable@@YAXXZ; WppEnable(void)
0x18000604b  mov     rcx, cs:WPP_GLOBAL_Control
0x180006052  lea     rdi, WPP_GLOBAL_Control
0x180006059  cmp     rcx, rdi
0x18000605c  jz      short loc_18000607F
0x18000605e  test    byte ptr [rcx+1Ch], 1
0x180006062  jz      short loc_18000607F
0x180006064  cmp     byte ptr [rcx+19h], 5
0x180006068  jb      short loc_18000607F
0x18000606a  mov     rcx, [rcx+10h]
0x18000606e  lea     r8, WPP_27ea2efe8112346a6f92681e48c92895_Traceguids
0x180006075  mov     edx, 14h
0x18000607a  call    WPP_SF_
0x18000607f  lea     rdx, ?SvcCtrlHandler@@YAXK@Z; lpHandlerProc
0x180006086  lea     rcx, ServiceName; "ApxSvc"
0x18000608d  call    cs:__imp_RegisterServiceCtrlHandlerW
0x180006093  mov     cs:?g_SvcStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rax; SERVICE_STATUS_HANDLE__ * g_SvcStatusHandle
0x18000609a  test    rax, rax
0x18000609d  jnz     short loc_1800060DA
0x18000609f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800060a6  cmp     rcx, rdi
0x1800060a9  jz      loc_180006130
0x1800060af  test    byte ptr [rcx+1Ch], 80h
0x1800060b3  jz      short loc_1800060D5
0x1800060b5  cmp     byte ptr [rcx+19h], 4
0x1800060b9  jb      short loc_1800060D5
0x1800060bb  mov     rcx, [rcx+10h]
0x1800060bf  lea     edx, [rax+16h]
0x1800060c2  lea     r8, WPP_27ea2efe8112346a6f92681e48c92895_Traceguids
0x1800060c9  call    WPP_SF_
0x1800060ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800060d5  cmp     rcx, rdi
0x1800060d8  jmp     short loc_18000610D
0x1800060da  xor     edx, edx; unsigned int
0x1800060dc  mov     cs:?g_SvcStatus@@3U_SERVICE_STATUS@@A.dwServiceType, 10h; _SERVICE_STATUS g_SvcStatus ...
0x1800060e6  mov     r8d, 0BB8h; unsigned int
0x1800060ec  mov     cs:?g_SvcStatus@@3U_SERVICE_STATUS@@A.dwServiceSpecificExitCode, 0; _SERVICE_STATUS g_SvcStatus ...
0x1800060f6  lea     ecx, [rdx+2]; unsigned int
0x1800060f9  call    ?ReportSvcStatus@@YAXKKK@Z; ReportSvcStatus(ulong,ulong,ulong)
0x1800060fe  call    ?SvcInit@@YAXXZ; SvcInit(void)
0x180006103  mov     rcx, cs:WPP_GLOBAL_Control
0x18000610a  cmp     rcx, rdi
0x18000610d  jz      short loc_180006130
0x18000610f  test    byte ptr [rcx+1Ch], 1
0x180006113  jz      short loc_180006130
0x180006115  cmp     byte ptr [rcx+19h], 5
0x180006119  jb      short loc_180006130
0x18000611b  mov     rcx, [rcx+10h]
0x18000611f  lea     r8, WPP_27ea2efe8112346a6f92681e48c92895_Traceguids
0x180006126  mov     edx, 15h
0x18000612b  call    WPP_SF_
0x180006130  add     rsp, 20h
0x180006134  pop     rdi
0x180006135  jmp     ?WppCleanup@@YAXXZ; WppCleanup(void)
```
