# Initialize(WiFiTaskServer)

- ea: `0x14000728c`
- end: `0x1400075ca`
- name: `?Initialize@@YAKW4WiFiTaskServer@@@Z`
- size: `830`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task`

## callers

- `0x14000c7b0`

## callees

- `0x1400016a0`
- `0x1400016d0`
- `0x140001714`
- `0x14000728c`
- `0x14000a4a0`
- `0x14000a628`
- `0x14000bef0`
- `0x14000bf20`
- `0x14000cf98`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x14000742c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x14000742c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140007492`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x140007492`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000736f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000736f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007381`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000743e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400074a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007381`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000743e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400074a4`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x140007329`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x140007329`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x140007359`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x140007359`

## pseudocode

```c
__int64 __fastcall Initialize(unsigned int a1)
{
  signed int v2; // eax
  unsigned int v3; // ebx
  DWORD LastError; // eax
  DWORD v5; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  struct _TP_CLEANUP_GROUP *ThreadpoolCleanupGroup; // rax
  __int64 v9; // rcx
  _DWORD *v10; // rbx
  int v11; // eax
  unsigned int v12; // edi
  GUID ProviderId; // [rsp+28h] [rbp-40h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11);
  }
  ProviderId = *(GUID *)&(*off_140019058)[-16];
  if ( RegHandle )
    __fastfail(5u);
  qword_140019078 = 0;
  qword_140019080 = 0;
  v2 = EventRegister(&ProviderId, tlgEnableCallback, &dword_140019050, &RegHandle);
  v3 = v2;
  if ( v2 )
  {
    if ( v2 > 0 )
      v3 = (unsigned __int16)v2 | 0x80070000;
  }
  else
  {
    EventSetInformation(RegHandle, 2, (char *)off_140019058, *(unsigned __int16 *)off_140019058);
  }
  g_ulWiFiTaskTraceLoggingRegistered = v3;
  g_hAllDoneEvent = CreateEventW(0, 1, 0, 0);
  if ( g_hAllDoneEvent )
  {
    g_ftpEnvironmentInitialized = 1;
    g_tpEnvironment.Version = 3;
    g_tpEnvironment.Pool = 0;
    g_tpEnvironment.CleanupGroup = 0;
    g_tpEnvironment.CleanupGroupCancelCallback = 0;
    *(_OWORD *)&g_tpEnvironment.RaceDll = 0;
    g_tpEnvironment.FinalizationCallback = 0;
    g_tpEnvironment.u.Flags = 0;
    g_tpEnvironment.CallbackPriority = TP_CALLBACK_PRIORITY_NORMAL;
    g_tpEnvironment.Size = 72;
    ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
    g_tpCleanupGroup = ThreadpoolCleanupGroup;
    if ( ThreadpoolCleanupGroup )
    {
      g_tpEnvironment.CleanupGroup = ThreadpoolCleanupGroup;
      g_tpEnvironment.CleanupGroupCancelCallback = 0;
      g_pDisconnectTimer = CreateThreadpoolTimer(DisconnectCallback, 0, 0);
      if ( g_pDisconnectTimer )
      {
        StartDisconnectTimer();
        v10 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
        if ( v10 )
        {
          *(_QWORD *)v10 = &WiFiTaskPipeClient::`vftable';
          v10[2] = 1;
          *(_QWORD *)&ProviderId.Data1 = operator new(0x618u);
          *((_QWORD *)v10 + 2) = AsyncPipe::AsyncPipe(*(AsyncPipe **)&ProviderId.Data1);
        }
        else
        {
          v10 = 0;
        }
        g_TaskPipe = (WiFiTaskPipeClient *)v10;
        if ( v10 )
        {
          v5 = 0;
          v11 = WiFiTaskPipeClient::Start(v9, a1);
          v12 = v11;
          if ( v11 < 0 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                16,
                &WPP_b0092361ee8d34528df1964c4db39788_Traceguids,
                (unsigned int)v11);
            }
            v5 = (unsigned __int16)v12;
            if ( (v12 & 0x1FFF0000) != 0x70000 )
              return v12;
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15);
          }
          return 8;
        }
      }
      else
      {
        LastError = GetLastError();
        v5 = LastError;
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v7 = 14;
          goto LABEL_16;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      v5 = LastError;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v7 = 13;
        goto LABEL_16;
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v5 = LastError;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v7 = 12;
LABEL_16:
      WPP_SF_d(v6[2], v7, &WPP_b0092361ee8d34528df1964c4db39788_Traceguids, LastError);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x14000728c  push    rbx
0x14000728e  push    rbp
0x14000728f  push    rdi
0x140007290  push    r15
0x140007292  sub     rsp, 48h
0x140007296  mov     rax, cs:__security_cookie
0x14000729d  xor     rax, rsp
0x1400072a0  mov     [rsp+68h+var_30], rax
0x1400072a5  mov     edi, ecx
0x1400072a7  lea     r15, WPP_GLOBAL_Control
0x1400072ae  mov     ebp, 1
0x1400072b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400072ba  cmp     rcx, r15
0x1400072bd  jz      short loc_1400072D7
0x1400072bf  cmp     byte ptr [rcx+19h], 4
0x1400072c3  jb      short loc_1400072D7
0x1400072c5  test    [rcx+1Ch], bpl
0x1400072c9  jz      short loc_1400072D7
0x1400072cb  lea     edx, [rbp+0Ah]
0x1400072ce  mov     rcx, [rcx+10h]
0x1400072d2  call    WPP_SF_
0x1400072d7  mov     rax, cs:off_140019058
0x1400072de  movups  xmm0, xmmword ptr [rax-10h]
0x1400072e2  movdqu  xmmword ptr [rsp+68h+ProviderId.Data1], xmm0
0x1400072e8  cmp     cs:RegHandle, 0
0x1400072f0  jz      short loc_1400072F9
0x1400072f2  mov     ecx, 5
0x1400072f7  int     29h; Win8: RtlFailFast(ecx)
0x1400072f9  mov     cs:qword_140019078, 0
0x140007304  mov     cs:qword_140019080, 0
0x14000730f  lea     r9, RegHandle; RegHandle
0x140007316  lea     r8, dword_140019050; CallbackContext
0x14000731d  lea     rdx, _tlgEnableCallback; EnableCallback
0x140007324  lea     rcx, [rsp+68h+ProviderId]; ProviderId
0x140007329  call    cs:__imp_EventRegister
0x14000732f  mov     ebx, eax
0x140007331  test    eax, eax
0x140007333  jz      short loc_140007342
0x140007335  jle     short loc_14000735F
0x140007337  movzx   ebx, ax
0x14000733a  or      ebx, 80070000h
0x140007340  jmp     short loc_14000735F
0x140007342  mov     r8, cs:off_140019058
0x140007349  movzx   r9d, word ptr [r8]
0x14000734d  mov     edx, 2
0x140007352  mov     rcx, cs:RegHandle
0x140007359  call    cs:__imp_EventSetInformation
0x14000735f  mov     cs:?g_ulWiFiTaskTraceLoggingRegistered@@3JA, ebx; long g_ulWiFiTaskTraceLoggingRegistered
0x140007365  xor     r9d, r9d; lpName
0x140007368  xor     r8d, r8d; bInitialState
0x14000736b  mov     edx, ebp; bManualReset
0x14000736d  xor     ecx, ecx; lpEventAttributes
0x14000736f  call    cs:__imp_CreateEventW
0x140007375  mov     cs:?g_hAllDoneEvent@@3PEAXEA, rax; void * g_hAllDoneEvent
0x14000737c  test    rax, rax
0x14000737f  jnz     short loc_1400073CA
0x140007381  call    cs:__imp_GetLastError
0x140007387  mov     ebx, eax
0x140007389  mov     rcx, cs:WPP_GLOBAL_Control
0x140007390  cmp     rcx, r15
0x140007393  jz      loc_1400075B1
0x140007399  cmp     byte ptr [rcx+19h], 2
0x14000739d  jb      loc_1400075B1
0x1400073a3  test    [rcx+1Ch], bpl
0x1400073a7  jz      loc_1400075B1
0x1400073ad  mov     edx, 0Ch
0x1400073b2  mov     r9d, eax
0x1400073b5  lea     r8, WPP_b0092361ee8d34528df1964c4db39788_Traceguids
0x1400073bc  mov     rcx, [rcx+10h]
0x1400073c0  call    WPP_SF_d
0x1400073c5  jmp     loc_1400075B1
0x1400073ca  mov     cs:?g_ftpEnvironmentInitialized@@3_NA, bpl; bool g_ftpEnvironmentInitialized
0x1400073d1  mov     cs:?g_tpEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.Version, 3; _TP_CALLBACK_ENVIRON_V3 g_tpEnvironment ...
0x1400073db  mov     cs:?g_tpEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.Pool, 0; _TP_CALLBACK_ENVIRON_V3 g_tpEnvironment ...
0x1400073e6  mov     cs:?g_tpEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroup, 0; _TP_CALLBACK_ENVIRON_V3 g_tpEnvironment ...
0x1400073f1  mov     cs:?g_tpEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroupCancelCallback, 0; _TP_CALLBACK_ENVIRON_V3 g_tpEnvironment ...
0x1400073fc  xorps   xmm0, xmm0
0x1400073ff  movdqa  xmmword ptr cs:?g_tpEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.RaceDll, xmm0; _TP_CALLBACK_ENVIRON_V3 g_tpEnvironment ...
0x140007407  mov     cs:?g_tpEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.FinalizationCallback, 0; _TP_CALLBACK_ENVIRON_V3 g_tpEnvironment ...
0x140007412  mov     dword ptr cs:?g_tpEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.u, 0; _TP_CALLBACK_ENVIRON_V3 g_tpEnvironment ...
0x14000741c  mov     cs:?g_tpEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.CallbackPriority, ebp; _TP_CALLBACK_ENVIRON_V3 g_tpEnvironment ...
0x140007422  mov     cs:?g_tpEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.Size, 48h ; 'H'; _TP_CALLBACK_ENVIRON_V3 g_tpEnvironment ...
0x14000742c  call    cs:__imp_CreateThreadpoolCleanupGroup
0x140007432  mov     cs:?g_tpCleanupGroup@@3PEAU_TP_CLEANUP_GROUP@@EA, rax; _TP_CLEANUP_GROUP * g_tpCleanupGroup
0x140007439  test    rax, rax
0x14000743c  jnz     short loc_140007474
0x14000743e  call    cs:__imp_GetLastError
0x140007444  mov     ebx, eax
0x140007446  mov     rcx, cs:WPP_GLOBAL_Control
0x14000744d  cmp     rcx, r15
0x140007450  jz      loc_1400075B1
0x140007456  cmp     byte ptr [rcx+19h], 2
0x14000745a  jb      loc_1400075B1
0x140007460  test    [rcx+1Ch], bpl
0x140007464  jz      loc_1400075B1
0x14000746a  mov     edx, 0Dh
0x14000746f  jmp     loc_1400073B2
0x140007474  mov     cs:?g_tpEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroup, rax; _TP_CALLBACK_ENVIRON_V3 g_tpEnvironment ...
0x14000747b  mov     cs:?g_tpEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroupCancelCallback, 0; _TP_CALLBACK_ENVIRON_V3 g_tpEnvironment ...
0x140007486  xor     r8d, r8d; pcbe
0x140007489  xor     edx, edx; pv
0x14000748b  lea     rcx, ?DisconnectCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140007492  call    cs:__imp_CreateThreadpoolTimer
0x140007498  mov     cs:?g_pDisconnectTimer@@3PEAU_TP_TIMER@@EA, rax; _TP_TIMER * g_pDisconnectTimer
0x14000749f  test    rax, rax
0x1400074a2  jnz     short loc_1400074DA
0x1400074a4  call    cs:__imp_GetLastError
0x1400074aa  mov     ebx, eax
0x1400074ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1400074b3  cmp     rcx, r15
0x1400074b6  jz      loc_1400075B1
0x1400074bc  cmp     byte ptr [rcx+19h], 2
0x1400074c0  jb      loc_1400075B1
0x1400074c6  test    [rcx+1Ch], bpl
0x1400074ca  jz      loc_1400075B1
0x1400074d0  mov     edx, 0Eh
0x1400074d5  jmp     loc_1400073B2
0x1400074da  call    ?StartDisconnectTimer@@YAXXZ; StartDisconnectTimer(void)
0x1400074df  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400074e6  mov     ecx, 18h; unsigned __int64
0x1400074eb  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400074f0  mov     rbx, rax
0x1400074f3  mov     [rsp+68h+var_48], rax
0x1400074f8  test    rax, rax
0x1400074fb  jz      short loc_140007528
0x1400074fd  lea     rax, ??_7WiFiTaskPipeClient@@6B@; const WiFiTaskPipeClient::`vftable'
0x140007504  mov     [rbx], rax
0x140007507  mov     [rbx+8], ebp
0x14000750a  mov     ecx, 618h; Size
0x14000750f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140007514  mov     qword ptr [rsp+68h+ProviderId.Data1], rax
0x140007519  mov     rcx, rax; this
0x14000751c  call    ??0AsyncPipe@@QEAA@XZ; AsyncPipe::AsyncPipe(void)
0x140007521  nop
0x140007522  mov     [rbx+10h], rax
0x140007526  jmp     short loc_14000752A
0x140007528  xor     ebx, ebx
0x14000752a  mov     cs:?g_TaskPipe@@3PEAVWiFiTaskPipeClient@@EA, rbx; WiFiTaskPipeClient * g_TaskPipe
0x140007531  test    rbx, rbx
0x140007534  jnz     short loc_140007561
0x140007536  mov     rcx, cs:WPP_GLOBAL_Control
0x14000753d  cmp     rcx, r15
0x140007540  jz      short loc_14000755A
0x140007542  cmp     byte ptr [rcx+19h], 2
0x140007546  jb      short loc_14000755A
0x140007548  test    [rcx+1Ch], bpl
0x14000754c  jz      short loc_14000755A
0x14000754e  lea     edx, [rbx+0Fh]
0x140007551  mov     rcx, [rcx+10h]
0x140007555  call    WPP_SF_
0x14000755a  mov     ebx, 8
0x14000755f  jmp     short loc_1400075B1
0x140007561  xor     ebx, ebx
0x140007563  mov     edx, edi
0x140007565  call    ?Start@WiFiTaskPipeClient@@QEAAJW4WiFiTaskServer@@@Z; WiFiTaskPipeClient::Start(WiFiTaskServer)
0x14000756a  mov     edi, eax
0x14000756c  test    eax, eax
0x14000756e  jns     short loc_1400075B1
0x140007570  mov     rcx, cs:WPP_GLOBAL_Control
0x140007577  cmp     rcx, r15
0x14000757a  jz      short loc_14000759E
0x14000757c  cmp     byte ptr [rcx+19h], 2
0x140007580  jb      short loc_14000759E
0x140007582  test    [rcx+1Ch], bpl
0x140007586  jz      short loc_14000759E
0x140007588  lea     edx, [rbx+10h]
0x14000758b  mov     r9d, eax
0x14000758e  lea     r8, WPP_b0092361ee8d34528df1964c4db39788_Traceguids
0x140007595  mov     rcx, [rcx+10h]
0x140007599  call    WPP_SF_d
0x14000759e  mov     eax, edi
0x1400075a0  and     eax, 1FFF0000h
0x1400075a5  cmp     eax, 70000h
0x1400075aa  movzx   ebx, di
0x1400075ad  jz      short loc_1400075B1
0x1400075af  mov     ebx, edi
0x1400075b1  mov     eax, ebx
0x1400075b3  mov     rcx, [rsp+68h+var_30]
0x1400075b8  xor     rcx, rsp; StackCookie
0x1400075bb  call    __security_check_cookie
0x1400075c0  add     rsp, 48h
0x1400075c4  pop     r15
0x1400075c6  pop     rdi
0x1400075c7  pop     rbp
0x1400075c8  pop     rbx
0x1400075c9  retn
```
