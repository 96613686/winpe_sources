# TsSessionNewPrimaryConsoleAudioSession(TSSession *)

- ea: `0x18002890c`
- end: `0x180028a3d`
- name: `?TsSessionNewPrimaryConsoleAudioSession@@YAXPEAVTSSession@@@Z`
- size: `305`
- prototype: `void __fastcall(struct TSSession *)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180002d68`
- `0x1800425ac`
- `0x180042918`

## callees

- `0x180002e80`
- `0x18001d0b0`
- `0x180020a60`
- `0x180027f10`
- `0x18002890c`
- `0x18003a5fc`
- `0x1800420ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028923`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028923`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028a36`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x18002892b`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x18002892b`

## pseudocode

```c
void __fastcall TsSessionNewPrimaryConsoleAudioSession(struct TSSession *a1)
{
  int v2; // ebx
  __int64 v3; // r14
  __int64 *i; // rbx
  unsigned int *v5; // rax
  unsigned int v6; // ebx
  const struct _tlgProvider_t *v7; // rax
  __int64 v8; // r8
  __int64 v9; // r9
  int v10; // eax
  int v11; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  int v13; // [rsp+50h] [rbp+8h] BYREF
  int v14; // [rsp+58h] [rbp+10h] BYREF

  EnterCriticalSection(&stru_180064458);
  v2 = *(_DWORD *)a1;
  if ( v2 != (unsigned int)RtlGetCurrentServiceSessionId() )
  {
    v3 = qword_180064488;
    for ( i = *(__int64 **)qword_180064488;
          i != (__int64 *)v3 && !(unsigned int)TSSession::IsPrimaryConsoleAudioSession((TSSession *)i[3]);
          i = (__int64 *)*i )
    {
      ;
    }
    v5 = i == (__int64 *)qword_180064488 ? 0LL : (unsigned int *)i[3];
    if ( v5 != (unsigned int *)a1 )
    {
      v6 = -2;
      if ( v5 )
      {
        v6 = *v5;
        v5[278] = 0;
        if ( g_MaxSessions <= 1 )
          v5[9] = 1;
      }
      *((_DWORD *)a1 + 278) = 1;
      *((_DWORD *)a1 + 9) = 0;
      if ( g_MaxSessions <= 1 )
      {
        v7 = AudioSrvPolicyManagerTelemetryProvider::Provider();
        if ( *(_DWORD *)v7 > 4u && (unsigned __int8)tlgKeywordOn(v7, 0x20000, v7) )
        {
          v13 = *(_DWORD *)a1;
          v14 = v6;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v8,
            (unsigned __int8 *)&dword_1800584F4,
            v8,
            v9,
            (__int64)&v14,
            (__int64)&v13);
        }
        v10 = QueueSessionMuteUnmute(v6, *(_DWORD *)a1);
        if ( v10 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x374,
            (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\ts.cpp",
            (const char *)(unsigned int)v10,
            v11);
      }
    }
  }
  LeaveCriticalSection(&stru_180064458);
}

```

## disassembly

```asm
0x18002890c  mov     [rsp+arg_10], rbx
0x180028911  push    rsi
0x180028912  push    rdi
0x180028913  push    r14
0x180028915  sub     rsp, 30h
0x180028919  mov     rdi, rcx
0x18002891c  lea     rcx, stru_180064458; lpCriticalSection
0x180028923  call    cs:__imp_EnterCriticalSection
0x180028929  mov     ebx, [rdi]
0x18002892b  call    cs:__imp_RtlGetCurrentServiceSessionId
0x180028931  cmp     ebx, eax
0x180028933  jz      loc_180028A22
0x180028939  mov     r14, cs:qword_180064488
0x180028940  mov     rbx, [r14]
0x180028943  cmp     rbx, r14
0x180028946  jz      short loc_18002895A
0x180028948  mov     rcx, [rbx+18h]; this
0x18002894c  call    ?IsPrimaryConsoleAudioSession@TSSession@@QEAAHXZ; TSSession::IsPrimaryConsoleAudioSession(void)
0x180028951  test    eax, eax
0x180028953  jnz     short loc_18002895A
0x180028955  mov     rbx, [rbx]
0x180028958  jmp     short loc_180028943
0x18002895a  cmp     rbx, cs:qword_180064488
0x180028961  jz      short loc_180028969
0x180028963  mov     rax, [rbx+18h]
0x180028967  jmp     short loc_18002896B
0x180028969  xor     eax, eax
0x18002896b  cmp     rax, rdi
0x18002896e  jz      loc_180028A22
0x180028974  mov     ebx, 0FFFFFFFEh
0x180028979  mov     ecx, 1
0x18002897e  test    rax, rax
0x180028981  jz      short loc_18002899A
0x180028983  mov     ebx, [rax]
0x180028985  mov     dword ptr [rax+458h], 0
0x18002898f  cmp     cs:?g_MaxSessions@@3KA, ecx; ulong g_MaxSessions
0x180028995  ja      short loc_18002899A
0x180028997  mov     [rax+24h], ecx
0x18002899a  mov     [rdi+458h], ecx
0x1800289a0  mov     dword ptr [rdi+24h], 0
0x1800289a7  cmp     cs:?g_MaxSessions@@3KA, ecx; ulong g_MaxSessions
0x1800289ad  ja      short loc_180028A22
0x1800289af  call    ?Provider@AudioSrvPolicyManagerTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioSrvPolicyManagerTelemetryProvider::Provider(void)
0x1800289b4  mov     r8, rax
0x1800289b7  mov     ecx, [rax]
0x1800289b9  cmp     ecx, 4
0x1800289bc  jbe     short loc_1800289FC
0x1800289be  mov     edx, 20000h
0x1800289c3  mov     rcx, rax
0x1800289c6  call    _tlgKeywordOn
0x1800289cb  test    al, al
0x1800289cd  jz      short loc_1800289FC
0x1800289cf  mov     edx, [rdi]
0x1800289d1  lea     rax, [rsp+48h+arg_0]
0x1800289d6  mov     [rsp+48h+var_20], rax
0x1800289db  mov     rcx, r8
0x1800289de  lea     rax, [rsp+48h+arg_8]
0x1800289e3  mov     [rsp+48h+arg_0], edx
0x1800289e7  lea     rdx, dword_1800584F4
0x1800289ee  mov     qword ptr [rsp+48h+var_28], rax; int
0x1800289f3  mov     [rsp+48h+arg_8], ebx
0x1800289f7  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800289fc  mov     edx, [rdi]; unsigned int
0x1800289fe  mov     ecx, ebx; unsigned int
0x180028a00  call    ?QueueSessionMuteUnmute@@YAJKK@Z; QueueSessionMuteUnmute(ulong,ulong)
0x180028a05  test    eax, eax
0x180028a07  jns     short loc_180028A22
0x180028a09  mov     rcx, [rsp+48h]; this
0x180028a0e  lea     r8, aClientcoreMult_10; "clientcore\\multimedia\\audiocore\\serv"...
0x180028a15  mov     r9d, eax; char *
0x180028a18  mov     edx, 374h; void *
0x180028a1d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180028a22  lea     rcx, stru_180064458
0x180028a29  mov     rbx, [rsp+48h+arg_10]
0x180028a2e  add     rsp, 30h
0x180028a32  pop     r14
0x180028a34  pop     rdi
0x180028a35  pop     rsi
0x180028a36  jmp     cs:__imp_LeaveCriticalSection
```
