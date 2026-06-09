# I_RedirectionContextInitialize(_REDIRECTION_CONTEXT * *)

- ea: `0x1800176a0`
- end: `0x180017a2f`
- name: `?I_RedirectionContextInitialize@@YAKPEAPEAU_REDIRECTION_CONTEXT@@@Z`
- size: `911`
- prototype: `unsigned int __fastcall(struct _REDIRECTION_CONTEXT **)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, installer_update`

## callers

- `0x180006c80`

## callees

- `0x180007bc0`
- `0x180008d20`
- `0x180013d34`
- `0x180014150`
- `0x1800150c0`
- `0x180015e24`
- `0x1800176a0`
- `0x180017c48`
- `0x18001991c`
- `0x18001c7a8`
- `0x1800239b8`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitializeConditionVariable` at `0x1800177a5`
- `api-ms-win-core-synch-l1-2-0!InitializeConditionVariable` at `0x1800177a5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800177b6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001785b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180017880`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800178a0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800178df`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800177b6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001785b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180017880`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800178a0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800178df`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800178c1`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800178c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017709`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017709`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001771f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001771f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800177c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800177c5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180017987`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800179a8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800179c9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800179ed`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180017a11`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180017987`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800179a8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800179c9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800179ed`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180017a11`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18001794c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18001794c`
- `ntdll!RtlInitializeCriticalSection` at `0x180017738`
- `ntdll!RtlInitializeCriticalSection` at `0x180017738`

## string_xrefs

- `0x1800178b3`: `Global\TermSrvReadyEvent`

## pseudocode

```c
__int64 __fastcall I_RedirectionContextInitialize(struct _RTL_CRITICAL_SECTION **a1)
{
  __int64 v2; // rcx
  HANDLE ProcessHeap; // rax
  DWORD SessionID; // ebx
  struct _RTL_CRITICAL_SECTION *v5; // rax
  struct _RTL_CRITICAL_SECTION *v6; // rdi
  __int64 v7; // rcx
  int v8; // r9d
  HANDLE EventW; // rax
  __int64 v10; // rcx
  int v11; // r9d
  HANDLE v13; // rax
  HANDLE v14; // rax
  HANDLE v15; // rax
  HANDLE v16; // rax
  HANDLE v17; // rax
  struct _TP_CLEANUP_GROUP *ThreadpoolCleanupGroup; // rax
  PTP_WAIT v19; // rax
  PTP_WAIT v20; // rax
  PTP_WAIT v21; // rax
  PTP_WAIT v22; // rax
  PTP_WAIT v23; // rax
  _TP_CALLBACK_ENVIRON_V3 pcbe; // [rsp+30h] [rbp-29h] BYREF

  memset_0(&pcbe, 0, sizeof(pcbe));
  WppTraceIndent(v2, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_ff6f9e331ef63b4fe1fc76f2b0998229_Traceguids);
  }
  *a1 = 0;
  ProcessHeap = GetProcessHeap();
  SessionID = 8;
  v5 = (struct _RTL_CRITICAL_SECTION *)HeapAlloc(ProcessHeap, 8u, 0x1E8u);
  v6 = v5;
  if ( v5 )
  {
    if ( RtlInitializeCriticalSection(v5) )
      goto LABEL_14;
    HIDWORD(v6[1].DebugInfo) = 1;
    SessionID = I_RedirectionContextGetSessionID((unsigned int *)&v6[1].SpinCount);
    if ( SessionID )
      goto LABEL_14;
    WppTraceIndent(v7, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        (unsigned int)&WPP_ff6f9e331ef63b4fe1fc76f2b0998229_Traceguids,
        v8,
        v6[1].SpinCount);
    }
    LODWORD(v6[1].LockSemaphore) = 0;
    InitializeConditionVariable((PCONDITION_VARIABLE)&v6[1].LockCount);
    EventW = CreateEventW(0, 1, 0, 0);
    v6[1].OwningThread = EventW;
    if ( EventW )
    {
      if ( g_bDisconnectedLocalSessionsAreAllowed )
      {
        BYTE1(v6[1].DebugInfo) = 1;
        UpdateRedirectionStateForContext(v6);
      }
      UpdateConnectionStateForContext(v6);
      v13 = CreateEventW(0, 1, 0, 0);
      *(_QWORD *)&v6[3].LockCount = v13;
      if ( v13 )
      {
        LOBYTE(v6[1].DebugInfo) = 0;
        v14 = CreateEventW(0, 1, 0, 0);
        v6[3].OwningThread = v14;
        if ( v14 )
        {
          v15 = CreateEventW(0, 0, 0, 0);
          v6[2].LockSemaphore = v15;
          if ( v15 )
          {
            v16 = OpenEventW(0x100000u, 0, L"Global\\TermSrvReadyEvent");
            *(_QWORD *)&v6[2].LockCount = v16;
            if ( v16 )
            {
              v17 = CreateEventW(0, 1, 1, 0);
              *(_QWORD *)&v6[4].LockCount = v17;
              if ( v17 )
              {
                if ( !RedirectionContextThreadpoolIsSafeForUse((struct _REDIRECTION_CONTEXT *)v6) )
                {
                  SessionID = -2146435054;
                  goto LABEL_14;
                }
                pcbe.Version = 3;
                memset(&pcbe.Pool, 0, 52);
                pcbe.CallbackPriority = TP_CALLBACK_PRIORITY_NORMAL;
                pcbe.Size = 72;
                ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
                v6[4].SpinCount = (ULONG_PTR)ThreadpoolCleanupGroup;
                if ( ThreadpoolCleanupGroup )
                {
                  pcbe.CleanupGroup = ThreadpoolCleanupGroup;
                  pcbe.RaceDll = g_hInst;
                  pcbe.CleanupGroupCancelCallback = 0;
                  v19 = CreateThreadpoolWait(TermSrvReadyCallback, v6, &pcbe);
                  v6[2].OwningThread = v19;
                  if ( v19 )
                  {
                    v20 = CreateThreadpoolWait(SessionChangeCallback, v6, &pcbe);
                    v6[2].SpinCount = (ULONG_PTR)v20;
                    if ( v20 )
                    {
                      v21 = CreateThreadpoolWait(SmartCardSubsystemStoppedCallback, v6, &pcbe);
                      v6[3].SpinCount = (ULONG_PTR)v21;
                      if ( v21 )
                      {
                        v22 = CreateThreadpoolWait(SmartCardSubsystemStartedCallback, v6, &pcbe);
                        v6[4].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)v22;
                        if ( v22 )
                        {
                          v23 = CreateThreadpoolWait(RedirectionIOCTLCallback, v6, &pcbe);
                          v6[4].OwningThread = v23;
                          if ( v23 )
                          {
                            *a1 = v6;
                            goto LABEL_15;
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    SessionID = GetLastError();
LABEL_14:
    I_RedirectionContextCleanup(v6);
  }
LABEL_15:
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::GetImpl'::`2'::impl);
  WppTraceIndent(v10, 1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      19,
      (unsigned int)&WPP_ff6f9e331ef63b4fe1fc76f2b0998229_Traceguids,
      v11,
      SessionID);
  }
  return SessionID;
}

```

## disassembly

```asm
0x1800176a0  push    rbp
0x1800176a2  push    rbx
0x1800176a3  push    rsi
0x1800176a4  push    rdi
0x1800176a5  push    r12
0x1800176a7  push    r14
0x1800176a9  lea     rbp, [rsp-2Fh]
0x1800176ae  sub     rsp, 88h
0x1800176b5  xor     edx, edx; Val
0x1800176b7  mov     r14, rcx
0x1800176ba  lea     rcx, [rbp+57h+pcbe]; void *
0x1800176be  lea     r8d, [rdx+48h]; Size
0x1800176c2  call    memset_0
0x1800176c7  xor     edx, edx
0x1800176c9  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800176ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800176d5  lea     rax, WPP_GLOBAL_Control
0x1800176dc  cmp     rcx, rax
0x1800176df  jz      short loc_180017702
0x1800176e1  test    byte ptr [rcx+1Ch], 2
0x1800176e5  jz      short loc_180017702
0x1800176e7  cmp     byte ptr [rcx+19h], 5
0x1800176eb  jb      short loc_180017702
0x1800176ed  mov     rcx, [rcx+10h]
0x1800176f1  lea     r8, WPP_ff6f9e331ef63b4fe1fc76f2b0998229_Traceguids
0x1800176f8  mov     edx, 11h
0x1800176fd  call    WPP_SF_s
0x180017702  mov     qword ptr [r14], 0
0x180017709  call    cs:__imp_GetProcessHeap
0x18001770f  mov     ebx, 8
0x180017714  mov     r8d, 1E8h; dwBytes
0x18001771a  mov     rcx, rax; hHeap
0x18001771d  mov     edx, ebx; dwFlags
0x18001771f  call    cs:__imp_HeapAlloc
0x180017725  lea     r12d, [rbx-7]
0x180017729  mov     rdi, rax
0x18001772c  test    rax, rax
0x18001772f  jz      loc_1800177D5
0x180017735  mov     rcx, rax; CriticalSection
0x180017738  call    cs:__imp_RtlInitializeCriticalSection
0x18001773e  test    eax, eax
0x180017740  jnz     loc_1800177CD
0x180017746  lea     rcx, [rdi+48h]; TokenInformation
0x18001774a  mov     [rdi+2Ch], r12d
0x18001774e  call    ?I_RedirectionContextGetSessionID@@YAKPEAK@Z; I_RedirectionContextGetSessionID(ulong *)
0x180017753  mov     ebx, eax
0x180017755  test    eax, eax
0x180017757  jnz     short loc_1800177CD
0x180017759  lea     edx, [rax+2]
0x18001775c  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180017761  mov     rcx, cs:WPP_GLOBAL_Control
0x180017768  lea     rax, WPP_GLOBAL_Control
0x18001776f  cmp     rcx, rax
0x180017772  jz      short loc_18001779A
0x180017774  test    [rcx+1Ch], r12b
0x180017778  jz      short loc_18001779A
0x18001777a  cmp     byte ptr [rcx+19h], 4
0x18001777e  jb      short loc_18001779A
0x180017780  mov     eax, [rdi+48h]
0x180017783  lea     edx, [rbx+12h]
0x180017786  mov     rcx, [rcx+10h]
0x18001778a  lea     r8, WPP_ff6f9e331ef63b4fe1fc76f2b0998229_Traceguids
0x180017791  mov     [rsp+0B0h+var_90], eax
0x180017795  call    WPP_SF_sd
0x18001779a  lea     rcx, [rdi+30h]; ConditionVariable
0x18001779e  mov     dword ptr [rdi+40h], 0
0x1800177a5  call    cs:__imp_InitializeConditionVariable
0x1800177ab  xor     r9d, r9d; lpName
0x1800177ae  xor     r8d, r8d; bInitialState
0x1800177b1  mov     edx, r12d; bManualReset
0x1800177b4  xor     ecx, ecx; lpEventAttributes
0x1800177b6  call    cs:__imp_CreateEventW
0x1800177bc  mov     [rdi+38h], rax
0x1800177c0  test    rax, rax
0x1800177c3  jnz     short loc_180017833
0x1800177c5  call    cs:__imp_GetLastError
0x1800177cb  mov     ebx, eax
0x1800177cd  mov     rcx, rdi; lpCriticalSection
0x1800177d0  call    ?I_RedirectionContextCleanup@@YAXPEAU_REDIRECTION_CONTEXT@@@Z; I_RedirectionContextCleanup(_REDIRECTION_CONTEXT *)
0x1800177d5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock> `wil::Feature<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::GetImpl(void)'::`2'::impl
0x1800177dc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::__private_IsEnabled(void)
0x1800177e1  mov     edx, r12d
0x1800177e4  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800177e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800177f0  lea     rax, WPP_GLOBAL_Control
0x1800177f7  cmp     rcx, rax
0x1800177fa  jz      short loc_180017821
0x1800177fc  test    byte ptr [rcx+1Ch], 2
0x180017800  jz      short loc_180017821
0x180017802  cmp     byte ptr [rcx+19h], 5
0x180017806  jb      short loc_180017821
0x180017808  mov     rcx, [rcx+10h]
0x18001780c  lea     r8, WPP_ff6f9e331ef63b4fe1fc76f2b0998229_Traceguids
0x180017813  mov     edx, 13h
0x180017818  mov     [rsp+0B0h+var_90], ebx
0x18001781c  call    WPP_SF_sd
0x180017821  mov     eax, ebx
0x180017823  add     rsp, 88h
0x18001782a  pop     r14
0x18001782c  pop     r12
0x18001782e  pop     rdi
0x18001782f  pop     rsi
0x180017830  pop     rbx
0x180017831  pop     rbp
0x180017832  retn
0x180017833  cmp     cs:?g_bDisconnectedLocalSessionsAreAllowed@@3_NA, 0; bool g_bDisconnectedLocalSessionsAreAllowed
0x18001783a  jz      short loc_180017848
0x18001783c  mov     rcx, rdi; lpCriticalSection
0x18001783f  mov     [rdi+29h], r12b
0x180017843  call    ?UpdateRedirectionStateForContext@@YAXPEAU_REDIRECTION_CONTEXT@@@Z; UpdateRedirectionStateForContext(_REDIRECTION_CONTEXT *)
0x180017848  mov     rcx, rdi; lpCriticalSection
0x18001784b  call    ?UpdateConnectionStateForContext@@YAXPEAU_REDIRECTION_CONTEXT@@@Z; UpdateConnectionStateForContext(_REDIRECTION_CONTEXT *)
0x180017850  xor     r9d, r9d; lpName
0x180017853  xor     r8d, r8d; bInitialState
0x180017856  mov     edx, r12d; bManualReset
0x180017859  xor     ecx, ecx; lpEventAttributes
0x18001785b  call    cs:__imp_CreateEventW
0x180017861  mov     [rdi+80h], rax
0x180017868  test    rax, rax
0x18001786b  jz      loc_1800177C5
0x180017871  xor     r9d, r9d; lpName
0x180017874  mov     byte ptr [rdi+28h], 0
0x180017878  xor     r8d, r8d; bInitialState
0x18001787b  mov     edx, r12d; bManualReset
0x18001787e  xor     ecx, ecx; lpEventAttributes
0x180017880  call    cs:__imp_CreateEventW
0x180017886  mov     [rdi+88h], rax
0x18001788d  test    rax, rax
0x180017890  jz      loc_1800177C5
0x180017896  xor     r9d, r9d; lpName
0x180017899  xor     r8d, r8d; bInitialState
0x18001789c  xor     edx, edx; bManualReset
0x18001789e  xor     ecx, ecx; lpEventAttributes
0x1800178a0  call    cs:__imp_CreateEventW
0x1800178a6  mov     [rdi+68h], rax
0x1800178aa  test    rax, rax
0x1800178ad  jz      loc_1800177C5
0x1800178b3  lea     r8, Name; "Global\\TermSrvReadyEvent"
0x1800178ba  xor     edx, edx; bInheritHandle
0x1800178bc  mov     ecx, 100000h; dwDesiredAccess
0x1800178c1  call    cs:__imp_OpenEventW
0x1800178c7  mov     [rdi+58h], rax
0x1800178cb  test    rax, rax
0x1800178ce  jz      loc_1800177C5
0x1800178d4  xor     r9d, r9d; lpName
0x1800178d7  mov     r8d, r12d; bInitialState
0x1800178da  mov     edx, r12d; bManualReset
0x1800178dd  xor     ecx, ecx; lpEventAttributes
0x1800178df  call    cs:__imp_CreateEventW
0x1800178e5  mov     [rdi+0A8h], rax
0x1800178ec  test    rax, rax
0x1800178ef  jz      loc_1800177C5
0x1800178f5  mov     rcx, rdi; struct _REDIRECTION_CONTEXT *
0x1800178f8  call    ?RedirectionContextThreadpoolIsSafeForUse@@YA_NPEAU_REDIRECTION_CONTEXT@@@Z; RedirectionContextThreadpoolIsSafeForUse(_REDIRECTION_CONTEXT *)
0x1800178fd  test    al, al
0x1800178ff  jnz     short loc_18001790B
0x180017901  mov     ebx, 80100012h
0x180017906  jmp     loc_1800177CD
0x18001790b  xorps   xmm0, xmm0
0x18001790e  mov     [rbp+57h+pcbe.Version], 3
0x180017915  movdqa  xmmword ptr [rbp+57h+pcbe.RaceDll], xmm0
0x18001791a  mov     [rbp+57h+pcbe.Pool], 0
0x180017922  mov     [rbp+57h+pcbe.CleanupGroup], 0
0x18001792a  mov     [rbp+57h+pcbe.CleanupGroupCancelCallback], 0
0x180017932  mov     [rbp+57h+pcbe.FinalizationCallback], 0
0x18001793a  mov     dword ptr [rbp+57h+pcbe.u], 0
0x180017941  mov     [rbp+57h+pcbe.CallbackPriority], r12d
0x180017945  mov     [rbp+57h+pcbe.Size], 48h ; 'H'
0x18001794c  call    cs:__imp_CreateThreadpoolCleanupGroup
0x180017952  mov     [rdi+0C0h], rax
0x180017959  test    rax, rax
0x18001795c  jz      loc_1800177C5
0x180017962  mov     [rbp+57h+pcbe.CleanupGroup], rax
0x180017966  lea     r8, [rbp+57h+pcbe]; pcbe
0x18001796a  mov     rax, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInst
0x180017971  lea     rcx, ?TermSrvReadyCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x180017978  mov     rdx, rdi; pv
0x18001797b  mov     [rbp+57h+pcbe.RaceDll], rax
0x18001797f  mov     [rbp+57h+pcbe.CleanupGroupCancelCallback], 0
0x180017987  call    cs:__imp_CreateThreadpoolWait
0x18001798d  mov     [rdi+60h], rax
0x180017991  test    rax, rax
0x180017994  jz      loc_1800177C5
0x18001799a  lea     r8, [rbp+57h+pcbe]; pcbe
0x18001799e  mov     rdx, rdi; pv
0x1800179a1  lea     rcx, ?SessionChangeCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x1800179a8  call    cs:__imp_CreateThreadpoolWait
0x1800179ae  mov     [rdi+70h], rax
0x1800179b2  test    rax, rax
0x1800179b5  jz      loc_1800177C5
0x1800179bb  lea     r8, [rbp+57h+pcbe]; pcbe
0x1800179bf  mov     rdx, rdi; pv
0x1800179c2  lea     rcx, ?SmartCardSubsystemStoppedCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x1800179c9  call    cs:__imp_CreateThreadpoolWait
0x1800179cf  mov     [rdi+98h], rax
0x1800179d6  test    rax, rax
0x1800179d9  jz      loc_1800177C5
0x1800179df  lea     r8, [rbp+57h+pcbe]; pcbe
0x1800179e3  mov     rdx, rdi; pv
0x1800179e6  lea     rcx, ?SmartCardSubsystemStartedCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x1800179ed  call    cs:__imp_CreateThreadpoolWait
0x1800179f3  mov     [rdi+0A0h], rax
0x1800179fa  test    rax, rax
0x1800179fd  jz      loc_1800177C5
0x180017a03  lea     r8, [rbp+57h+pcbe]; pcbe
0x180017a07  mov     rdx, rdi; pv
0x180017a0a  lea     rcx, ?RedirectionIOCTLCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x180017a11  call    cs:__imp_CreateThreadpoolWait
0x180017a17  mov     [rdi+0B0h], rax
0x180017a1e  test    rax, rax
0x180017a21  jz      loc_1800177C5
0x180017a27  mov     [r14], rdi
0x180017a2a  jmp     loc_1800177D5
```
