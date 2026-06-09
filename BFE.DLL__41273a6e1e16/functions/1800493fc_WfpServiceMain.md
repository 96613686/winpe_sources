# WfpServiceMain

- ea: `0x1800493fc`
- end: `0x180049554`
- name: `WfpServiceMain`
- size: `344`
- prototype: `__int64 __fastcall(LPVOID lpContext)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180049360`

## callees

- `0x180012d8c`
- `0x1800370e8`
- `0x18004668c`
- `0x1800493fc`
- `0x1800617c0`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180049532`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180049532`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180049467`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180049467`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004943d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004947b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004943d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004947b`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180049424`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180049424`

## string_xrefs

- `0x180049449`: `RegisterServiceCtrlHandlerExW`
- `0x180049487`: `CreateEventW`

## pseudocode

```c
int __fastcall WfpServiceMain(HANDLE *lpContext)
{
  _DWORD *v1; // rsi
  int v4; // ebp
  const WCHAR *v5; // rcx
  SERVICE_STATUS_HANDLE v6; // rax
  HANDLE *v7; // rbx
  DWORD LastError; // eax
  __int64 v9; // rcx
  const char *v10; // rdx
  __int64 v11; // rax
  HANDLE EventW; // rax
  __int64 v13; // rax
  int v14; // ecx
  __int64 v15; // rax
  __int64 v16; // rax
  HANDLE v17; // r8
  HANDLE v18; // rdx
  int v19; // eax

  v1 = (_DWORD *)lpContext + 11;
  *((_DWORD *)lpContext + 15) = 1;
  v4 = 0;
  v5 = (const WCHAR *)*lpContext;
  *v1 = 0;
  v6 = RegisterServiceCtrlHandlerExW(v5, WfpServiceHandlerEx, lpContext);
  lpContext[3] = v6;
  v7 = lpContext + 8;
  if ( !v6 )
  {
    LastError = GetLastError();
    v10 = "RegisterServiceCtrlHandlerExW";
    goto LABEL_3;
  }
  EventW = CreateEventW(0, 0, 0, 0);
  *v7 = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    v10 = "CreateEventW";
    goto LABEL_3;
  }
  v13 = WfpServiceChangeState(lpContext, 2);
  v14 = v13;
  if ( !v13 )
  {
    v15 = WfpComponentsStart(lpContext + 1, v1);
    v14 = v15;
    if ( !v15 )
    {
      v16 = gWfpSvcHostGlobalData;
      v17 = *v7;
      v18 = *lpContext;
      *((_DWORD *)lpContext + 22) = 1;
      LastError = (*(__int64 (__fastcall **)(char *, HANDLE, HANDLE, __int64 (__fastcall *)(_QWORD, _QWORD), HANDLE *, _DWORD))(v16 + 192))(
                    (char *)lpContext + 72,
                    v18,
                    v17,
                    WfpServiceExit,
                    lpContext,
                    0);
      if ( !LastError )
      {
        v4 = 1;
        v11 = WfpServiceChangeState(lpContext, 4);
LABEL_11:
        v14 = v11;
        if ( !v11 )
          return v11;
        goto LABEL_12;
      }
      v10 = "RegisterStopCallback";
LABEL_3:
      v11 = WfpReportSysErrorAsWinError(v9, v10, LastError);
      goto LABEL_11;
    }
  }
LABEL_12:
  v19 = (unsigned __int16)v14;
  if ( (v14 & 0x1FFF0000) != 0x70000 )
    v19 = v14;
  *v1 = v19;
  if ( v4 )
    LODWORD(v11) = SetEvent(*v7);
  else
    LODWORD(v11) = WfpServiceExit(lpContext, 0);
  return v11;
}

```

## disassembly

```asm
0x1800493fc  push    rbx
0x1800493fe  push    rbp
0x1800493ff  push    rsi
0x180049400  push    rdi
0x180049401  sub     rsp, 48h
0x180049405  lea     rsi, [rcx+2Ch]
0x180049409  mov     dword ptr [rcx+3Ch], 1
0x180049410  mov     rdi, rcx
0x180049413  lea     rdx, WfpServiceHandlerEx; lpHandlerProc
0x18004941a  mov     r8, rcx; lpContext
0x18004941d  xor     ebp, ebp
0x18004941f  mov     rcx, [rcx]; lpServiceName
0x180049422  mov     [rsi], ebp
0x180049424  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18004942b  nop     dword ptr [rax+rax+00h]
0x180049430  mov     [rdi+18h], rax
0x180049434  lea     rbx, [rdi+40h]
0x180049438  test    rax, rax
0x18004943b  jnz     short loc_18004945D
0x18004943d  call    cs:__imp_GetLastError
0x180049444  nop     dword ptr [rax+rax+00h]
0x180049449  lea     rdx, aRegisterservic_0; "RegisterServiceCtrlHandlerExW"
0x180049450  mov     r8d, eax
0x180049453  call    WfpReportSysErrorAsWinError
0x180049458  jmp     loc_18004950D
0x18004945d  xor     r9d, r9d; lpName
0x180049460  xor     r8d, r8d; bInitialState
0x180049463  xor     edx, edx; bManualReset
0x180049465  xor     ecx, ecx; lpEventAttributes
0x180049467  call    cs:__imp_CreateEventW
0x18004946e  nop     dword ptr [rax+rax+00h]
0x180049473  mov     [rbx], rax
0x180049476  test    rax, rax
0x180049479  jnz     short loc_180049490
0x18004947b  call    cs:__imp_GetLastError
0x180049482  nop     dword ptr [rax+rax+00h]
0x180049487  lea     rdx, aCreateeventw; "CreateEventW"
0x18004948e  jmp     short loc_180049450
0x180049490  mov     edx, 2
0x180049495  mov     rcx, rdi
0x180049498  call    WfpServiceChangeState
0x18004949d  mov     rcx, rax
0x1800494a0  test    rax, rax
0x1800494a3  jnz     short loc_180049515
0x1800494a5  lea     rcx, [rdi+8]
0x1800494a9  mov     rdx, rsi
0x1800494ac  call    WfpComponentsStart
0x1800494b1  mov     rcx, rax
0x1800494b4  test    rax, rax
0x1800494b7  jnz     short loc_180049515
0x1800494b9  mov     rax, cs:gWfpSvcHostGlobalData
0x1800494c0  lea     rcx, [rdi+48h]
0x1800494c4  mov     r8, [rbx]
0x1800494c7  lea     r9, WfpServiceExit
0x1800494ce  mov     rdx, [rdi]
0x1800494d1  mov     dword ptr [rdi+58h], 1
0x1800494d8  mov     rax, [rax+0C0h]
0x1800494df  mov     [rsp+68h+var_40], ebp
0x1800494e3  mov     [rsp+68h+var_48], rdi
0x1800494e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800494ed  test    eax, eax
0x1800494ef  jz      short loc_1800494FD
0x1800494f1  lea     rdx, aRegisterstopca; "RegisterStopCallback"
0x1800494f8  jmp     loc_180049450
0x1800494fd  mov     ebp, 1
0x180049502  mov     rcx, rdi
0x180049505  lea     edx, [rbp+3]
0x180049508  call    WfpServiceChangeState
0x18004950d  mov     rcx, rax
0x180049510  test    rax, rax
0x180049513  jz      short loc_18004954A
0x180049515  mov     edx, ecx
0x180049517  movzx   eax, cx
0x18004951a  and     edx, 1FFF0000h
0x180049520  cmp     edx, 70000h
0x180049526  cmovnz  eax, ecx
0x180049529  mov     [rsi], eax
0x18004952b  test    ebp, ebp
0x18004952d  jz      short loc_180049540
0x18004952f  mov     rcx, [rbx]; hEvent
0x180049532  call    cs:__imp_SetEvent
0x180049539  nop     dword ptr [rax+rax+00h]
0x18004953e  jmp     short loc_18004954A
0x180049540  xor     edx, edx
0x180049542  mov     rcx, rdi
0x180049545  call    WfpServiceExit
0x18004954a  add     rsp, 48h
0x18004954e  pop     rdi
0x18004954f  pop     rsi
0x180049550  pop     rbp
0x180049551  pop     rbx
0x180049552  retn
```
