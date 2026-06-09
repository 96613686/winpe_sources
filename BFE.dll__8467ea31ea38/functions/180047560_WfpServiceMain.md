# WfpServiceMain

- ea: `0x180047560`
- end: `0x180047699`
- name: `WfpServiceMain`
- size: `313`
- prototype: `__int64 __fastcall(LPVOID lpContext)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800474d0`

## callees

- `0x18001236c`
- `0x180038630`
- `0x18004472c`
- `0x180047560`
- `0x18005f500`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004767e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004767e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800475bf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800475bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004759b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800475cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004759b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800475cd`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180047588`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180047588`

## string_xrefs

- `0x1800475a1`: `RegisterServiceCtrlHandlerExW`
- `0x1800475d3`: `CreateEventW`

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
0x180047560  push    rbx
0x180047562  push    rbp
0x180047563  push    rsi
0x180047564  push    rdi
0x180047565  sub     rsp, 48h
0x180047569  lea     rsi, [rcx+2Ch]
0x18004756d  mov     dword ptr [rcx+3Ch], 1
0x180047574  mov     rdi, rcx
0x180047577  lea     rdx, WfpServiceHandlerEx; lpHandlerProc
0x18004757e  mov     r8, rcx; lpContext
0x180047581  xor     ebp, ebp
0x180047583  mov     rcx, [rcx]; lpServiceName
0x180047586  mov     [rsi], ebp
0x180047588  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18004758e  mov     [rdi+18h], rax
0x180047592  lea     rbx, [rdi+40h]
0x180047596  test    rax, rax
0x180047599  jnz     short loc_1800475B5
0x18004759b  call    cs:__imp_GetLastError
0x1800475a1  lea     rdx, aRegisterservic_0; "RegisterServiceCtrlHandlerExW"
0x1800475a8  mov     r8d, eax
0x1800475ab  call    WfpReportSysErrorAsWinError
0x1800475b0  jmp     loc_180047659
0x1800475b5  xor     r9d, r9d; lpName
0x1800475b8  xor     r8d, r8d; bInitialState
0x1800475bb  xor     edx, edx; bManualReset
0x1800475bd  xor     ecx, ecx; lpEventAttributes
0x1800475bf  call    cs:__imp_CreateEventW
0x1800475c5  mov     [rbx], rax
0x1800475c8  test    rax, rax
0x1800475cb  jnz     short loc_1800475DC
0x1800475cd  call    cs:__imp_GetLastError
0x1800475d3  lea     rdx, aCreateeventw; "CreateEventW"
0x1800475da  jmp     short loc_1800475A8
0x1800475dc  mov     edx, 2
0x1800475e1  mov     rcx, rdi
0x1800475e4  call    WfpServiceChangeState
0x1800475e9  mov     rcx, rax
0x1800475ec  test    rax, rax
0x1800475ef  jnz     short loc_180047661
0x1800475f1  lea     rcx, [rdi+8]
0x1800475f5  mov     rdx, rsi
0x1800475f8  call    WfpComponentsStart
0x1800475fd  mov     rcx, rax
0x180047600  test    rax, rax
0x180047603  jnz     short loc_180047661
0x180047605  mov     rax, cs:gWfpSvcHostGlobalData
0x18004760c  lea     rcx, [rdi+48h]
0x180047610  mov     r8, [rbx]
0x180047613  lea     r9, WfpServiceExit
0x18004761a  mov     rdx, [rdi]
0x18004761d  mov     dword ptr [rdi+58h], 1
0x180047624  mov     rax, [rax+0C0h]
0x18004762b  mov     [rsp+68h+var_40], ebp
0x18004762f  mov     [rsp+68h+var_48], rdi
0x180047634  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047639  test    eax, eax
0x18004763b  jz      short loc_180047649
0x18004763d  lea     rdx, aRegisterstopca; "RegisterStopCallback"
0x180047644  jmp     loc_1800475A8
0x180047649  mov     ebp, 1
0x18004764e  mov     rcx, rdi
0x180047651  lea     edx, [rbp+3]
0x180047654  call    WfpServiceChangeState
0x180047659  mov     rcx, rax
0x18004765c  test    rax, rax
0x18004765f  jz      short loc_180047690
0x180047661  mov     edx, ecx
0x180047663  movzx   eax, cx
0x180047666  and     edx, 1FFF0000h
0x18004766c  cmp     edx, 70000h
0x180047672  cmovnz  eax, ecx
0x180047675  mov     [rsi], eax
0x180047677  test    ebp, ebp
0x180047679  jz      short loc_180047686
0x18004767b  mov     rcx, [rbx]; hEvent
0x18004767e  call    cs:__imp_SetEvent
0x180047684  jmp     short loc_180047690
0x180047686  xor     edx, edx
0x180047688  mov     rcx, rdi
0x18004768b  call    WfpServiceExit
0x180047690  add     rsp, 48h
0x180047694  pop     rdi
0x180047695  pop     rsi
0x180047696  pop     rbp
0x180047697  pop     rbx
0x180047698  retn
```
