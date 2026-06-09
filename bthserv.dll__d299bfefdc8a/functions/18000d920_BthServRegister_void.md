# BthServRegister(void)

- ea: `0x18000d920`
- end: `0x18000d9da`
- name: `?BthServRegister@@YAXXZ`
- size: `186`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x1800100c0`

## callees

- `0x18000d920`
- `0x18001140c`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000d969`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000d969`

## pseudocode

```c
void BthServRegister(void)
{
  bool v0; // dl

  ServiceStatus.dwServiceType = 32;
  ServiceStatus.dwCurrentState = 2;
  *(_QWORD *)&ServiceStatus.dwControlsAccepted = 133;
  *(_QWORD *)&ServiceStatus.dwServiceSpecificExitCode = 0;
  ServiceStatus.dwWaitHint = 0;
  hServiceStatus = RegisterServiceCtrlHandlerExW(L"BthServ", ServiceHandlerEx, 0);
  v0 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  if ( v0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_si(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v0,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
}

```

## disassembly

```asm
0x18000d920  sub     rsp, 58h
0x18000d924  xor     r8d, r8d; lpContext
0x18000d927  mov     cs:ServiceStatus.dwServiceType, 20h ; ' '
0x18000d931  lea     rdx, ?ServiceHandlerEx@@YAKKKPEAX0@Z; lpHandlerProc
0x18000d938  mov     cs:ServiceStatus.dwCurrentState, 2
0x18000d942  lea     rcx, ServiceName; "BthServ"
0x18000d949  mov     qword ptr cs:ServiceStatus.dwControlsAccepted, 85h
0x18000d954  mov     qword ptr cs:ServiceStatus.dwServiceSpecificExitCode, 0
0x18000d95f  mov     cs:ServiceStatus.dwWaitHint, 0
0x18000d969  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18000d96f  mov     cs:hServiceStatus, rax
0x18000d976  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d97d  lea     rdx, WPP_GLOBAL_Control
0x18000d984  cmp     rcx, rdx
0x18000d987  jz      short loc_18000D993
0x18000d989  cmp     byte ptr [rcx+19h], 5
0x18000d98d  jb      short loc_18000D993
0x18000d98f  mov     dl, 1
0x18000d991  jmp     short loc_18000D995
0x18000d993  xor     dl, dl
0x18000d995  lea     r8, WPP_RECORDER_INITIALIZED
0x18000d99c  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x18000d9a3  setnz   r8b
0x18000d9a7  test    dl, dl
0x18000d9a9  jnz     short loc_18000D9B0
0x18000d9ab  test    r8b, r8b
0x18000d9ae  jz      short loc_18000D9D5
0x18000d9b0  mov     r9, [rcx+28h]
0x18000d9b4  mov     rcx, [rcx+10h]
0x18000d9b8  mov     [rsp+58h+var_10], rax
0x18000d9bd  lea     rax, WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids
0x18000d9c4  mov     [rsp+58h+var_20], rax
0x18000d9c9  mov     [rsp+58h+var_28], 26h ; '&'
0x18000d9d0  call    WPP_RECORDER_AND_TRACE_SF_si
0x18000d9d5  add     rsp, 58h
0x18000d9d9  retn
```
