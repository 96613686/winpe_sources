# InitializeService(void)

- ea: `0x1800127bc`
- end: `0x18001296b`
- name: `?InitializeService@@YAJXZ`
- size: `431`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update`

## callers

- `0x180012de0`

## callees

- `0x18000a644`
- `0x18000a778`
- `0x1800127bc`
- `0x180012c9c`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012840`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012840`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001282e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001282e`

## pseudocode

```c
__int64 InitializeService(void)
{
  int v0; // edx
  signed int LastError; // eax
  bool v2; // sf
  unsigned int updated; // ebx
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  int v7; // edi

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_3f50365df99735211a88e8fb382b12e7_Traceguids);
  *(_QWORD *)&g_ServiceStatus.dwCheckPoint = 0;
  g_ServiceStatus.dwServiceType = 32;
  g_hServiceWaitObject = 0;
  *(_OWORD *)&g_ServiceStatus.dwCurrentState = 0;
  g_hServiceStopEvent = CreateEventW(0, 1, 0, 0);
  if ( g_hServiceStopEvent )
  {
    updated = UpdateServiceStatus(2u, v0);
    if ( (updated & 0x80000000) == 0 )
    {
      v7 = (*((__int64 (__fastcall **)(HANDLE *, const WCHAR *, HANDLE, void (__fastcall *)(void *, unsigned __int8), _QWORD, int))g_SvchostGlobals
            + 24))(
             &g_hServiceWaitObject,
             L"NcdAutoSetup",
             g_hServiceStopEvent,
             SvchostStopCallback,
             0,
             24);
      if ( v7 )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_3f50365df99735211a88e8fb382b12e7_Traceguids);
          v4 = WPP_GLOBAL_Control;
        }
        if ( v7 > 0 )
          updated = (unsigned __int16)v7 | 0x80070000;
        else
          updated = v7;
        goto LABEL_14;
      }
      goto LABEL_13;
    }
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return updated;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_14;
    v5 = 23;
LABEL_12:
    WPP_SF_d(v4[2], v5, &WPP_3f50365df99735211a88e8fb382b12e7_Traceguids);
LABEL_13:
    v4 = WPP_GLOBAL_Control;
    goto LABEL_14;
  }
  LastError = GetLastError();
  v2 = LastError < 0;
  if ( LastError > 0 )
  {
    LastError = (unsigned __int16)LastError | 0x80070000;
    v2 = LastError < 0;
  }
  if ( !v2 )
    LastError = -2147467259;
  updated = LastError;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
    {
LABEL_14:
      if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x20) != 0 )
        WPP_SF_(v4[2], 25, &WPP_3f50365df99735211a88e8fb382b12e7_Traceguids);
      return updated;
    }
    v5 = 22;
    goto LABEL_12;
  }
  return updated;
}

```

## disassembly

```asm
0x1800127bc  push    rbx
0x1800127be  push    rbp
0x1800127bf  push    rdi
0x1800127c0  push    r14
0x1800127c2  sub     rsp, 48h
0x1800127c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800127cd  lea     rbp, WPP_GLOBAL_Control
0x1800127d4  lea     r14, WPP_3f50365df99735211a88e8fb382b12e7_Traceguids
0x1800127db  cmp     rcx, rbp
0x1800127de  jz      short loc_1800127F7
0x1800127e0  test    byte ptr [rcx+1Ch], 20h
0x1800127e4  jz      short loc_1800127F7
0x1800127e6  mov     rcx, [rcx+10h]
0x1800127ea  mov     edx, 15h
0x1800127ef  mov     r8, r14
0x1800127f2  call    WPP_SF_
0x1800127f7  xor     r9d, r9d; lpName
0x1800127fa  mov     qword ptr cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, 0; _SERVICE_STATUS g_ServiceStatus ...
0x180012805  xorps   xmm0, xmm0
0x180012808  mov     cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwServiceType, 20h ; ' '; _SERVICE_STATUS g_ServiceStatus ...
0x180012812  xor     r8d, r8d; bInitialState
0x180012815  mov     cs:?g_hServiceWaitObject@@3PEAXEA, 0; void * g_hServiceWaitObject
0x180012820  xor     ecx, ecx; lpEventAttributes
0x180012822  lea     edx, [r9+1]; bManualReset
0x180012826  movdqu  xmmword ptr cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, xmm0; _SERVICE_STATUS g_ServiceStatus ...
0x18001282e  call    cs:__imp_CreateEventW
0x180012834  mov     cs:?g_hServiceStopEvent@@3PEAXEA, rax; void * g_hServiceStopEvent
0x18001283b  test    rax, rax
0x18001283e  jnz     short loc_1800128B2
0x180012840  call    cs:__imp_GetLastError
0x180012846  test    eax, eax
0x180012848  jle     short loc_180012854
0x18001284a  movzx   eax, ax
0x18001284d  or      eax, 80070000h
0x180012852  test    eax, eax
0x180012854  js      short loc_18001285B
0x180012856  mov     eax, 80004005h
0x18001285b  mov     ebx, eax
0x18001285d  mov     rcx, cs:WPP_GLOBAL_Control
0x180012864  cmp     rcx, rbp
0x180012867  jz      short loc_1800128A6
0x180012869  test    byte ptr [rcx+1Ch], 2
0x18001286d  jz      short loc_18001288A
0x18001286f  mov     edx, 16h
0x180012874  mov     rcx, [rcx+10h]
0x180012878  mov     r9d, eax
0x18001287b  mov     r8, r14
0x18001287e  call    WPP_SF_d
0x180012883  mov     rcx, cs:WPP_GLOBAL_Control
0x18001288a  cmp     rcx, rbp
0x18001288d  jz      short loc_1800128A6
0x18001288f  test    byte ptr [rcx+1Ch], 20h
0x180012893  jz      short loc_1800128A6
0x180012895  mov     rcx, [rcx+10h]
0x180012899  mov     edx, 19h
0x18001289e  mov     r8, r14
0x1800128a1  call    WPP_SF_
0x1800128a6  mov     eax, ebx
0x1800128a8  add     rsp, 48h
0x1800128ac  pop     r14
0x1800128ae  pop     rdi
0x1800128af  pop     rbp
0x1800128b0  pop     rbx
0x1800128b1  retn
0x1800128b2  mov     ecx, 2; unsigned int
0x1800128b7  call    ?UpdateServiceStatus@@YAJKJ@Z; UpdateServiceStatus(ulong,long)
0x1800128bc  mov     ebx, eax
0x1800128be  test    eax, eax
0x1800128c0  jns     short loc_1800128DB
0x1800128c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800128c9  cmp     rcx, rbp
0x1800128cc  jz      short loc_1800128A6
0x1800128ce  test    byte ptr [rcx+1Ch], 2
0x1800128d2  jz      short loc_18001288A
0x1800128d4  mov     edx, 17h
0x1800128d9  jmp     short loc_180012874
0x1800128db  mov     rax, cs:?g_SvchostGlobals@@3PEAU_SVCHOST_GLOBAL_DATA@@EA; _SVCHOST_GLOBAL_DATA * g_SvchostGlobals
0x1800128e2  lea     r9, ?SvchostStopCallback@@YAXPEAXE@Z; SvchostStopCallback(void *,uchar)
0x1800128e9  mov     r8, cs:?g_hServiceStopEvent@@3PEAXEA; void * g_hServiceStopEvent
0x1800128f0  lea     rdx, ServiceName; "NcdAutoSetup"
0x1800128f7  mov     [rsp+68h+var_40], 18h
0x1800128ff  lea     rcx, ?g_hServiceWaitObject@@3PEAXEA; void * g_hServiceWaitObject
0x180012906  mov     [rsp+68h+var_48], 0
0x18001290f  mov     rax, [rax+0C0h]
0x180012916  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001291b  mov     edi, eax
0x18001291d  test    eax, eax
0x18001291f  jz      loc_180012883
0x180012925  mov     rcx, cs:WPP_GLOBAL_Control
0x18001292c  cmp     rcx, rbp
0x18001292f  jz      short loc_180012952
0x180012931  test    byte ptr [rcx+1Ch], 2
0x180012935  jz      short loc_180012952
0x180012937  mov     rcx, [rcx+10h]
0x18001293b  mov     edx, 18h
0x180012940  mov     r9d, eax
0x180012943  mov     r8, r14
0x180012946  call    WPP_SF_d
0x18001294b  mov     rcx, cs:WPP_GLOBAL_Control
0x180012952  test    edi, edi
0x180012954  jg      short loc_18001295D
0x180012956  mov     ebx, edi
0x180012958  jmp     loc_18001288A
0x18001295d  movzx   ebx, di
0x180012960  or      ebx, 80070000h
0x180012966  jmp     loc_18001288A
```
