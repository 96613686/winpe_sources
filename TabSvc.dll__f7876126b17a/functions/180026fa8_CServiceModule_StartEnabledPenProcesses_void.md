# CServiceModule::StartEnabledPenProcesses(void)

- ea: `0x180026fa8`
- end: `0x180027184`
- name: `?StartEnabledPenProcesses@CServiceModule@@QEAAXXZ`
- size: `476`
- prototype: `void __fastcall(PVOID Context)`
- caller_count: `3`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x18000ed70`
- `0x18000fa00`
- `0x180025bbc`

## callees

- `0x1800010f8`
- `0x180001ec0`
- `0x18001506c`
- `0x180015630`
- `0x18001a174`
- `0x180026fa8`
- `0x18002b3a8`
- `0x18002b404`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800270c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027111`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800270c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027111`
- `WTSAPI32!WTSEnumerateSessionsW` at `0x18002705b`
- `WTSAPI32!WTSEnumerateSessionsW` at `0x18002705b`
- `WTSAPI32!WTSFreeMemory` at `0x1800270ac`
- `WTSAPI32!WTSFreeMemory` at `0x1800270ac`

## string_xrefs

- `0x180026fed`: `PENSERVICE_CServiceModule::StartEnabledPenProcesses`
- `0x1800270d3`: `PENSERVICE_CServiceModule::StartEnabledPenProcesses`
- `0x180027147`: `PENSERVICE_CServiceModule::StartEnabledPenProcesses`

## pseudocode

```c
void __fastcall CServiceModule::StartEnabledPenProcesses(int *Context)
{
  struct _GUID *v2; // rcx
  unsigned __int64 v3; // r8
  __int64 v4; // rcx
  const struct _GUID *v5; // rcx
  __int64 i; // rbx
  char LastError; // al
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  struct _GUID *v11; // rax
  unsigned __int64 v12; // r8
  DWORD pCount; // [rsp+68h] [rbp+10h] BYREF
  DWORD v14; // [rsp+70h] [rbp+18h] BYREF
  PWTS_SESSION_INFOW ppSessionInfo; // [rsp+78h] [rbp+20h] BYREF

  v2 = WPP_GLOBAL_Control;
  v3 = *(_QWORD *)WPP_GLOBAL_Control[3].Data4;
  if ( v3 )
  {
    PrivateTraceEvent(WPP_GLOBAL_Control, 0x61Au, v3, 1u);
    v2 = WPP_GLOBAL_Control;
  }
  if ( v2 != (struct _GUID *)&WPP_GLOBAL_Control && (v2[1].Data4[4] & 0x10) != 0 )
    WPP_SF_s(
      *(_QWORD *)&v2[1].Data1,
      40,
      WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      "PENSERVICE_CServiceModule::StartEnabledPenProcesses");
  if ( (unsigned int)dword_1800411A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800411A8, 0x4000000) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v4,
      (int)&word_180039F86);
  pCount = 0;
  ppSessionInfo = 0;
  if ( WTSEnumerateSessionsW(0, 0, 1u, &ppSessionInfo, &pCount) )
  {
    for ( i = 0; ppSessionInfo && (unsigned int)i < pCount; i = (unsigned int)(i + 1) )
      CServiceModule::_StartPenProcessesWorker(
        Context,
        ppSessionInfo[i].SessionId,
        ppSessionInfo[i].State,
        1,
        1,
        Context[17]);
    WTSFreeMemory(ppSessionInfo);
  }
  else
  {
    if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 4) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_sd(
        *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
        41,
        (unsigned int)WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
        (unsigned int)"PENSERVICE_CServiceModule::StartEnabledPenProcesses",
        LastError);
    }
    if ( (unsigned int)dword_1800411A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800411A8, 0x4000000) )
    {
      v14 = GetLastError();
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v8,
        (int)&dword_18003A514,
        v9,
        v10,
        (__int64)&v14);
    }
  }
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
  {
    WPP_SF_s(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      42,
      WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      "PENSERVICE_CServiceModule::StartEnabledPenProcesses");
    v11 = WPP_GLOBAL_Control;
  }
  v12 = *(_QWORD *)v11[3].Data4;
  if ( v12 )
    PrivateTraceEvent(v5, 0x61Au, v12, 2u);
}

```

## disassembly

```asm
0x180026fa8  push    rbx
0x180026faa  push    rbp
0x180026fab  push    rdi
0x180026fac  sub     rsp, 40h
0x180026fb0  mov     rdi, rcx
0x180026fb3  mov     rcx, cs:WPP_GLOBAL_Control; struct _GUID *
0x180026fba  mov     r8, [rcx+38h]; unsigned __int64
0x180026fbe  test    r8, r8
0x180026fc1  jz      short loc_180026FD7
0x180026fc3  mov     r9b, 1; unsigned __int8
0x180026fc6  mov     edx, 61Ah; unsigned int
0x180026fcb  call    ?PrivateTraceEvent@@YAXPEBU_GUID@@K_KE@Z; PrivateTraceEvent(_GUID const *,ulong,unsigned __int64,uchar)
0x180026fd0  mov     rcx, cs:WPP_GLOBAL_Control
0x180026fd7  lea     rbp, WPP_GLOBAL_Control
0x180026fde  cmp     rcx, rbp
0x180026fe1  jz      short loc_180027005
0x180026fe3  test    byte ptr [rcx+1Ch], 10h
0x180026fe7  jz      short loc_180027005
0x180026fe9  mov     rcx, [rcx+10h]
0x180026fed  lea     r9, aPenserviceCser_14; "PENSERVICE_CServiceModule::StartEnabled"...
0x180026ff4  mov     edx, 28h ; '('
0x180026ff9  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x180027000  call    WPP_SF_s
0x180027005  mov     eax, cs:dword_1800411A8
0x18002700b  mov     ebx, 4000000h
0x180027010  cmp     eax, 5
0x180027013  jbe     short loc_180027033
0x180027015  mov     edx, ebx
0x180027017  lea     rcx, dword_1800411A8
0x18002701e  call    _tlgKeywordOn
0x180027023  test    al, al
0x180027025  jz      short loc_180027033
0x180027027  lea     rdx, word_180039F86
0x18002702e  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180027033  xor     edx, edx; Reserved
0x180027035  mov     [rsp+58h+arg_8], 0
0x18002703d  lea     rax, [rsp+58h+arg_8]
0x180027042  mov     [rsp+58h+ppSessionInfo], 0
0x18002704b  lea     r9, [rsp+58h+ppSessionInfo]; ppSessionInfo
0x180027050  mov     [rsp+58h+pCount], rax; pCount
0x180027055  xor     ecx, ecx; hServer
0x180027057  lea     r8d, [rdx+1]; Version
0x18002705b  call    cs:__imp_WTSEnumerateSessionsW
0x180027061  test    eax, eax
0x180027063  jz      short loc_1800270B4
0x180027065  xor     ebx, ebx
0x180027067  jmp     short loc_1800270A2
0x180027069  cmp     ebx, [rsp+58h+arg_8]
0x18002706d  jnb     short loc_1800270AC
0x18002706f  mov     eax, [rdi+44h]
0x180027072  lea     rdx, [rbx+rbx*2]
0x180027076  mov     r8d, [rcx+rdx*8+10h]; enum _WTS_CONNECTSTATE_CLASS
0x18002707b  mov     r9d, 1; int
0x180027081  mov     edx, [rcx+rdx*8]; unsigned int
0x180027084  mov     rcx, rdi; Context
0x180027087  mov     [rsp+58h+var_28], 1; int
0x18002708f  mov     [rsp+58h+var_30], eax; int
0x180027093  mov     dword ptr [rsp+58h+pCount], 1; int
0x18002709b  call    ?_StartPenProcessesWorker@CServiceModule@@AEAAXKW4_WTS_CONNECTSTATE_CLASS@@HHHH@Z; CServiceModule::_StartPenProcessesWorker(ulong,_WTS_CONNECTSTATE_CLASS,int,int,int,int)
0x1800270a0  inc     ebx
0x1800270a2  mov     rcx, [rsp+58h+ppSessionInfo]; pMemory
0x1800270a7  test    rcx, rcx
0x1800270aa  jnz     short loc_180027069
0x1800270ac  call    cs:__imp_WTSFreeMemory
0x1800270b2  jmp     short loc_180027131
0x1800270b4  mov     rax, cs:WPP_GLOBAL_Control
0x1800270bb  cmp     rax, rbp
0x1800270be  jz      short loc_1800270F3
0x1800270c0  test    byte ptr [rax+1Ch], 4
0x1800270c4  jz      short loc_1800270F3
0x1800270c6  call    cs:__imp_GetLastError
0x1800270cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800270d3  lea     r9, aPenserviceCser_14; "PENSERVICE_CServiceModule::StartEnabled"...
0x1800270da  mov     edx, 29h ; ')'
0x1800270df  mov     dword ptr [rsp+58h+pCount], eax
0x1800270e3  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x1800270ea  mov     rcx, [rcx+10h]
0x1800270ee  call    WPP_SF_sd
0x1800270f3  mov     eax, cs:dword_1800411A8
0x1800270f9  cmp     eax, 5
0x1800270fc  jbe     short loc_180027131
0x1800270fe  mov     rdx, rbx
0x180027101  lea     rcx, dword_1800411A8
0x180027108  call    _tlgKeywordOn
0x18002710d  test    al, al
0x18002710f  jz      short loc_180027131
0x180027111  call    cs:__imp_GetLastError
0x180027117  mov     [rsp+58h+arg_10], eax
0x18002711b  lea     rdx, dword_18003A514
0x180027122  lea     rax, [rsp+58h+arg_10]
0x180027127  mov     [rsp+58h+pCount], rax
0x18002712c  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180027131  mov     rax, cs:WPP_GLOBAL_Control
0x180027138  cmp     rax, rbp
0x18002713b  jz      short loc_180027166
0x18002713d  test    byte ptr [rax+1Ch], 10h
0x180027141  jz      short loc_180027166
0x180027143  mov     rcx, [rax+10h]
0x180027147  lea     r9, aPenserviceCser_14; "PENSERVICE_CServiceModule::StartEnabled"...
0x18002714e  mov     edx, 2Ah ; '*'
0x180027153  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x18002715a  call    WPP_SF_s
0x18002715f  mov     rax, cs:WPP_GLOBAL_Control
0x180027166  mov     r8, [rax+38h]; unsigned __int64
0x18002716a  test    r8, r8
0x18002716d  jz      short loc_18002717C
0x18002716f  mov     r9b, 2; unsigned __int8
0x180027172  mov     edx, 61Ah; unsigned int
0x180027177  call    ?PrivateTraceEvent@@YAXPEBU_GUID@@K_KE@Z; PrivateTraceEvent(_GUID const *,ulong,unsigned __int64,uchar)
0x18002717c  add     rsp, 40h
0x180027180  pop     rdi
0x180027181  pop     rbp
0x180027182  pop     rbx
0x180027183  retn
```
