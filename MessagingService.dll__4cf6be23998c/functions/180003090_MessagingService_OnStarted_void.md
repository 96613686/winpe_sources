# MessagingService::OnStarted(void)

- ea: `0x180003090`
- end: `0x180003487`
- name: `?OnStarted@MessagingService@@UEAAJXZ`
- size: `1015`
- prototype: `__int64 __fastcall(MessagingService *__hidden this)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000108c`
- `0x180001730`
- `0x18000307c`
- `0x180003090`
- `0x180003678`
- `0x1800042c8`
- `0x1800044dc`
- `0x180004ad8`
- `0x180004c48`
- `0x18000aa27`
- `0x18000aa50`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000318c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000318c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800031ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800031ff`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800032f4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800033d5`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000345e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800032f4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800033d5`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000345e`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800030f8`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800030f8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800031d1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800031d1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800031eb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800031eb`

## string_xrefs

- `0x18000312d`: `onecoreuap\net\messaging\desktoptransport\service\messagingservice.cpp`
- `0x1800032cc`: `onecoreuap\net\messaging\desktoptransport\service\messagingservice.cpp`
- `0x180003369`: `onecoreuap\net\messaging\desktoptransport\service\messagingservice.cpp`
- `0x1800033e8`: `onecoreuap\net\messaging\desktoptransport\service\messagingservice.cpp`
- `0x180003436`: `onecoreuap\net\messaging\desktoptransport\service\messagingservice.cpp`
- `0x180003108`: `onecoreuap\internal\base\inc\CComInit.h`
- `0x1800032b4`: `onecoreuap\net\messaging\desktoptransport\service\transportmanager.cpp`

## pseudocode

```c
__int64 __fastcall MessagingService::OnStarted(MessagingService *this)
{
  int v2; // esi
  HRESULT v3; // eax
  __int64 v4; // rdx
  signed int v5; // ebx
  unsigned int ServiceIdleTimeoutInterval; // r12d
  struct IAsyncWorkQueue *v7; // rdi
  PTP_WORK *v8; // rax
  __int64 v9; // rdx
  PTP_WORK *v10; // r14
  PTP_WORK ThreadpoolWork; // rbx
  struct _TP_WORK *v12; // rax
  signed int LastError; // eax
  int v14; // ebp
  TransportManager *v15; // rbx
  __int64 v16; // rdx
  __int64 v17; // rdx
  TransportManager **v19; // r14
  TransportManager *v20; // rcx
  int v21; // eax
  __int64 v22; // rdx
  TransportManager *v23; // [rsp+38h] [rbp-90h] BYREF
  PTP_WORK *v24; // [rsp+40h] [rbp-88h]
  TransportManager *v25; // [rsp+48h] [rbp-80h]
  struct _EVENT_DATA_DESCRIPTOR v26; // [rsp+50h] [rbp-78h] BYREF

  if ( (unsigned int)dword_180013018 > 4 )
    tlgWriteTransfer_EventWriteTransfer((int)&dword_180013018, (int)&qword_180010148, 0, 0, 2u, &v26);
  v2 = 0;
  v3 = CoInitializeEx(0, 0);
  v5 = v3;
  if ( v3 >= 0 )
  {
    v2 = 1;
    v5 = 0;
  }
  else
  {
    Log_HREvent((unsigned int)v3, v4, "onecoreuap\\internal\\base\\inc\\CComInit.h", 37);
  }
  if ( v5 < 0 )
  {
    Log_HREvent((unsigned int)v5, v4, "onecoreuap\\net\\messaging\\desktoptransport\\service\\messagingservice.cpp", 49);
LABEL_59:
    if ( v2 )
      CoUninitialize();
    return (unsigned int)v5;
  }
  ServiceIdleTimeoutInterval = MessagingService::_GetServiceIdleTimeoutInterval();
  v7 = 0;
  v24 = 0;
  v8 = (PTP_WORK *)operator new(0x70u);
  v10 = v8;
  if ( !v8 )
  {
    v5 = -2147024882;
LABEL_57:
    Log_HREvent((unsigned int)v5, v9, "onecoreuap\\net\\messaging\\desktoptransport\\service\\messagingservice.cpp", 54);
    if ( v7 )
      (*(void (__fastcall **)(struct IAsyncWorkQueue *))(*(_QWORD *)v7 + 16LL))(v7);
    goto LABEL_59;
  }
  memset_0((char *)v8 + 12, 0, 0x64u);
  *v10 = (PTP_WORK)&AsyncWorkQueue::`vftable';
  *((_DWORD *)v10 + 2) = 0;
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v10 + 2), 0, 0);
  v10[7] = (PTP_WORK)(v10 + 7);
  v10[8] = (PTP_WORK)(v10 + 7);
  v10[9] = 0;
  v10[10] = 0;
  *((_DWORD *)v10 + 22) = 0;
  *((_DWORD *)v10 + 23) = 0;
  v10[12] = 0;
  *((_DWORD *)v10 + 26) = 0;
  (*((void (__fastcall **)(PTP_WORK *))*v10 + 1))(v10);
  ThreadpoolWork = CreateThreadpoolWork(AsyncWorkQueue::WorkCallBack, v10, 0);
  v12 = v10[12];
  if ( ThreadpoolWork == v12 )
  {
    ThreadpoolWork = v10[12];
  }
  else
  {
    if ( v12 )
      CloseThreadpoolWork(v10[12]);
    v10[12] = ThreadpoolWork;
  }
  if ( ThreadpoolWork )
  {
    v7 = (struct IAsyncWorkQueue *)v10;
    v24 = v10;
    v5 = 0;
  }
  else
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    (*((void (__fastcall **)(PTP_WORK *))*v10 + 2))(v10);
  }
  if ( v5 < 0 )
    goto LABEL_57;
  v25 = 0;
  v23 = 0;
  v14 = ATL::CComObject<TransportManager>::CreateInstance(&v23);
  if ( v14 < 0 )
  {
LABEL_26:
    Log_HREvent_0((unsigned int)v14, 1, "onecoreuap\\net\\messaging\\desktoptransport\\service\\transportmanager.cpp");
    Log_HREvent(
      (unsigned int)v14,
      v17,
      "onecoreuap\\net\\messaging\\desktoptransport\\service\\messagingservice.cpp",
      57);
    if ( v7 )
      (*(void (__fastcall **)(struct IAsyncWorkQueue *))(*(_QWORD *)v7 + 16LL))(v7);
LABEL_28:
    if ( v2 )
      CoUninitialize();
    return (unsigned int)v14;
  }
  v15 = v23;
  if ( v23 )
    (*(void (__fastcall **)(TransportManager *))(*(_QWORD *)v23 + 8LL))(v23);
  v14 = TransportManager::_Initialize(
          v15,
          v7,
          (struct ITransportManagerCallback *)(((unsigned __int64)this + 184) & -(__int64)(this != 0)),
          ServiceIdleTimeoutInterval);
  if ( v14 < 0 )
  {
    if ( v15 )
      (*(void (__fastcall **)(TransportManager *))(*(_QWORD *)v15 + 16LL))(v15);
    goto LABEL_26;
  }
  if ( v15 )
    (*(void (__fastcall **)(TransportManager *))(*(_QWORD *)v15 + 8LL))(v15);
  v25 = v15;
  if ( v15 )
    (*(void (__fastcall **)(TransportManager *))(*(_QWORD *)v15 + 16LL))(v15);
  v19 = (TransportManager **)((char *)this + 192);
  if ( this == (MessagingService *)-192LL )
  {
    v14 = -2147467261;
    Log_HREvent(2147500035LL, v16, "onecoreuap\\net\\messaging\\desktoptransport\\service\\messagingservice.cpp", 59);
    if ( v15 )
      (*(void (__fastcall **)(TransportManager *))(*(_QWORD *)v15 + 16LL))(v15);
    if ( v7 )
      (*(void (__fastcall **)(struct IAsyncWorkQueue *))(*(_QWORD *)v7 + 16LL))(v7);
    goto LABEL_28;
  }
  *v19 = v15;
  v20 = v15;
  if ( v15 )
  {
    (*(void (__fastcall **)(TransportManager *))(*(_QWORD *)v15 + 8LL))(v15);
    v20 = *v19;
  }
  v21 = TransportManager::Start(v20);
  v14 = v21;
  if ( v21 < 0 )
  {
    Log_HREvent(
      (unsigned int)v21,
      v22,
      "onecoreuap\\net\\messaging\\desktoptransport\\service\\messagingservice.cpp",
      61);
    if ( v15 )
      (*(void (__fastcall **)(TransportManager *))(*(_QWORD *)v15 + 16LL))(v15);
    if ( v7 )
      (*(void (__fastcall **)(struct IAsyncWorkQueue *))(*(_QWORD *)v7 + 16LL))(v7);
    goto LABEL_28;
  }
  if ( v15 )
    (*(void (__fastcall **)(TransportManager *))(*(_QWORD *)v15 + 16LL))(v15);
  if ( v7 )
    (*(void (__fastcall **)(struct IAsyncWorkQueue *))(*(_QWORD *)v7 + 16LL))(v7);
  if ( v2 )
    CoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x180003090  push    rbx
0x180003092  push    rbp
0x180003093  push    rsi
0x180003094  push    rdi
0x180003095  push    r12
0x180003097  push    r13
0x180003099  push    r14
0x18000309b  push    r15
0x18000309d  sub     rsp, 88h
0x1800030a4  mov     rax, cs:__security_cookie
0x1800030ab  xor     rax, rsp
0x1800030ae  mov     [rsp+0C8h+var_58], rax
0x1800030b3  mov     r13, rcx
0x1800030b6  mov     eax, cs:dword_180013018
0x1800030bc  cmp     eax, 4
0x1800030bf  jbe     short loc_1800030EC
0x1800030c1  lea     rax, [rsp+0C8h+var_78]
0x1800030c6  mov     [rsp+0C8h+var_A0], rax; PEVENT_DATA_DESCRIPTOR
0x1800030cb  mov     [rsp+0C8h+var_A8], 2; ULONG
0x1800030d3  xor     r9d, r9d; int
0x1800030d6  xor     r8d, r8d; int
0x1800030d9  lea     rdx, qword_180010148; int
0x1800030e0  lea     rcx, dword_180013018; int
0x1800030e7  call    _tlgWriteTransfer_EventWriteTransfer
0x1800030ec  xor     ebp, ebp
0x1800030ee  mov     esi, ebp
0x1800030f0  mov     [rsp+0C8h+var_98], ebp
0x1800030f4  xor     edx, edx; dwCoInit
0x1800030f6  xor     ecx, ecx; pvReserved
0x1800030f8  call    cs:__imp_CoInitializeEx
0x1800030fe  mov     ebx, eax
0x180003100  test    eax, eax
0x180003102  jns     short loc_180003118
0x180003104  lea     r9d, [rbp+25h]
0x180003108  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\base\\inc\\CComIn"...
0x18000310f  mov     ecx, eax
0x180003111  call    Log_HREvent
0x180003116  jmp     short loc_180003123
0x180003118  mov     esi, 1
0x18000311d  mov     [rsp+0C8h+var_98], esi
0x180003121  mov     ebx, ebp
0x180003123  test    ebx, ebx
0x180003125  jns     short loc_180003140
0x180003127  mov     r9d, 31h ; '1'
0x18000312d  lea     r8, aOnecoreuapNetM_7; "onecoreuap\\net\\messaging\\desktoptran"...
0x180003134  mov     ecx, ebx
0x180003136  call    Log_HREvent
0x18000313b  jmp     loc_18000345A
0x180003140  call    ?_GetServiceIdleTimeoutInterval@MessagingService@@CAKXZ; MessagingService::_GetServiceIdleTimeoutInterval(void)
0x180003145  mov     r12d, eax
0x180003148  mov     rdi, rbp
0x18000314b  mov     [rsp+0C8h+var_88], rbp
0x180003150  mov     ecx, 70h ; 'p'; Size
0x180003155  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000315a  mov     r14, rax
0x18000315d  test    rax, rax
0x180003160  jz      loc_18000342B
0x180003166  lea     rcx, [rax+0Ch]; void *
0x18000316a  xor     edx, edx; Val
0x18000316c  lea     r8d, [rdx+64h]; Size
0x180003170  call    memset_0
0x180003175  lea     rax, ??_7AsyncWorkQueue@@6B@; const AsyncWorkQueue::`vftable'
0x18000317c  mov     [r14], rax
0x18000317f  mov     [r14+8], ebp
0x180003183  lea     rcx, [r14+10h]; lpCriticalSection
0x180003187  xor     r8d, r8d; Flags
0x18000318a  xor     edx, edx; dwSpinCount
0x18000318c  call    cs:__imp_InitializeCriticalSectionEx
0x180003192  lea     rax, [r14+38h]
0x180003196  mov     [rax], rax
0x180003199  mov     [rax+8], rax
0x18000319d  mov     [rax+10h], rbp
0x1800031a1  mov     [r14+50h], rbp
0x1800031a5  mov     [r14+58h], ebp
0x1800031a9  mov     [r14+5Ch], ebp
0x1800031ad  mov     [r14+60h], rbp
0x1800031b1  mov     [r14+68h], ebp
0x1800031b5  mov     rax, [r14]
0x1800031b8  mov     rcx, r14
0x1800031bb  mov     rax, [rax+8]
0x1800031bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031c4  xor     r8d, r8d; pcbe
0x1800031c7  mov     rdx, r14; pv
0x1800031ca  lea     rcx, ?WorkCallBack@AsyncWorkQueue@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800031d1  call    cs:__imp_CreateThreadpoolWork
0x1800031d7  mov     rbx, rax
0x1800031da  mov     rax, [r14+60h]
0x1800031de  cmp     rbx, rax
0x1800031e1  jz      short loc_1800031F7
0x1800031e3  test    rax, rax
0x1800031e6  jz      short loc_1800031F1
0x1800031e8  mov     rcx, rax; pwk
0x1800031eb  call    cs:__imp_CloseThreadpoolWork
0x1800031f1  mov     [r14+60h], rbx
0x1800031f5  jmp     short loc_1800031FA
0x1800031f7  mov     rbx, rax
0x1800031fa  test    rbx, rbx
0x1800031fd  jnz     short loc_180003225
0x1800031ff  call    cs:__imp_GetLastError
0x180003205  mov     ebx, eax
0x180003207  test    eax, eax
0x180003209  jle     short loc_180003214
0x18000320b  movzx   ebx, ax
0x18000320e  or      ebx, 80070000h
0x180003214  mov     rax, [r14]
0x180003217  mov     rcx, r14
0x18000321a  mov     rax, [rax+10h]
0x18000321e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003223  jmp     short loc_18000322F
0x180003225  mov     rdi, r14
0x180003228  mov     [rsp+0C8h+var_88], r14
0x18000322d  mov     ebx, ebp
0x18000322f  test    ebx, ebx
0x180003231  js      loc_180003430
0x180003237  mov     rax, r13
0x18000323a  lea     rcx, [r13+0B8h]
0x180003241  neg     rax
0x180003244  sbb     r15, r15
0x180003247  and     r15, rcx
0x18000324a  mov     [rsp+0C8h+var_80], rbp
0x18000324f  mov     [rsp+0C8h+var_90], rbp
0x180003254  lea     rcx, [rsp+0C8h+var_90]
0x180003259  call    ?CreateInstance@?$CComObject@VTransportManager@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<TransportManager>::CreateInstance(ATL::CComObject<TransportManager> * *)
0x18000325e  mov     ebp, eax
0x180003260  test    eax, eax
0x180003262  js      short loc_1800032AE
0x180003264  mov     rbx, [rsp+0C8h+var_90]
0x180003269  mov     [rsp+0C8h+var_90], rbx
0x18000326e  test    rbx, rbx
0x180003271  jz      short loc_180003283
0x180003273  mov     rax, [rbx]
0x180003276  mov     rcx, rbx
0x180003279  mov     rax, [rax+8]
0x18000327d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003282  nop
0x180003283  mov     r9d, r12d; unsigned int
0x180003286  mov     r8, r15; struct ITransportManagerCallback *
0x180003289  mov     rdx, rdi; struct IAsyncWorkQueue *
0x18000328c  mov     rcx, rbx; this
0x18000328f  call    ?_Initialize@TransportManager@@AEAAJPEAUIAsyncWorkQueue@@PEAUITransportManagerCallback@@K@Z; TransportManager::_Initialize(IAsyncWorkQueue *,ITransportManagerCallback *,ulong)
0x180003294  mov     ebp, eax
0x180003296  test    eax, eax
0x180003298  jns     short loc_180003301
0x18000329a  test    rbx, rbx
0x18000329d  jz      short loc_1800032AE
0x18000329f  mov     rax, [rbx]
0x1800032a2  mov     rcx, rbx
0x1800032a5  mov     rax, [rax+10h]
0x1800032a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032ae  mov     r9d, 0Ch
0x1800032b4  lea     r8, aOnecoreuapNetM_6; "onecoreuap\\net\\messaging\\desktoptran"...
0x1800032bb  lea     edx, [r9-0Bh]
0x1800032bf  mov     ecx, ebp
0x1800032c1  call    Log_HREvent_0
0x1800032c6  mov     r9d, 39h ; '9'
0x1800032cc  lea     r8, aOnecoreuapNetM_7; "onecoreuap\\net\\messaging\\desktoptran"...
0x1800032d3  mov     ecx, ebp
0x1800032d5  call    Log_HREvent
0x1800032da  nop
0x1800032db  test    rdi, rdi
0x1800032de  jz      short loc_1800032F0
0x1800032e0  mov     rax, [rdi]
0x1800032e3  mov     rcx, rdi
0x1800032e6  mov     rax, [rax+10h]
0x1800032ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032ef  nop
0x1800032f0  test    esi, esi
0x1800032f2  jz      short loc_1800032FA
0x1800032f4  call    cs:__imp_CoUninitialize
0x1800032fa  mov     eax, ebp
0x1800032fc  jmp     loc_180003466
0x180003301  test    rbx, rbx
0x180003304  jz      short loc_180003315
0x180003306  mov     rax, [rbx]
0x180003309  mov     rcx, rbx
0x18000330c  mov     rax, [rax+8]
0x180003310  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003315  mov     [rsp+0C8h+var_80], rbx
0x18000331a  test    rbx, rbx
0x18000331d  jz      short loc_18000332E
0x18000331f  mov     rax, [rbx]
0x180003322  mov     rcx, rbx
0x180003325  mov     rax, [rax+10h]
0x180003329  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000332e  lea     r14, [r13+0C0h]
0x180003335  test    r14, r14
0x180003338  jz      loc_1800033E2
0x18000333e  mov     [r14], rbx
0x180003341  mov     rcx, rbx
0x180003344  test    rbx, rbx
0x180003347  jz      short loc_180003358
0x180003349  mov     rax, [rbx]
0x18000334c  mov     rax, [rax+8]
0x180003350  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003355  mov     rcx, [r14]; this
0x180003358  call    ?Start@TransportManager@@QEAAJXZ; TransportManager::Start(void)
0x18000335d  mov     ebp, eax
0x18000335f  test    eax, eax
0x180003361  jns     short loc_1800033A7
0x180003363  mov     r9d, 3Dh ; '='
0x180003369  lea     r8, aOnecoreuapNetM_7; "onecoreuap\\net\\messaging\\desktoptran"...
0x180003370  mov     ecx, eax
0x180003372  call    Log_HREvent
0x180003377  nop
0x180003378  test    rbx, rbx
0x18000337b  jz      short loc_18000338D
0x18000337d  mov     rcx, [rbx]
0x180003380  mov     rax, [rcx+10h]
0x180003384  mov     rcx, rbx
0x180003387  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000338c  nop
0x18000338d  test    rdi, rdi
0x180003390  jz      short loc_1800033A2
0x180003392  mov     rax, [rdi]
0x180003395  mov     rcx, rdi
0x180003398  mov     rax, [rax+10h]
0x18000339c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033a1  nop
0x1800033a2  jmp     loc_1800032F0
0x1800033a7  test    rbx, rbx
0x1800033aa  jz      short loc_1800033BC
0x1800033ac  mov     rax, [rbx]
0x1800033af  mov     rcx, rbx
0x1800033b2  mov     rax, [rax+10h]
0x1800033b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033bb  nop
0x1800033bc  test    rdi, rdi
0x1800033bf  jz      short loc_1800033D1
0x1800033c1  mov     rax, [rdi]
0x1800033c4  mov     rcx, rdi
0x1800033c7  mov     rax, [rax+10h]
0x1800033cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033d0  nop
0x1800033d1  test    esi, esi
0x1800033d3  jz      short loc_1800033DB
0x1800033d5  call    cs:__imp_CoUninitialize
0x1800033db  xor     eax, eax
0x1800033dd  jmp     loc_180003466
0x1800033e2  mov     r9d, 3Bh ; ';'
0x1800033e8  lea     r8, aOnecoreuapNetM_7; "onecoreuap\\net\\messaging\\desktoptran"...
0x1800033ef  mov     ebp, 80004003h
0x1800033f4  mov     ecx, ebp
0x1800033f6  call    Log_HREvent
0x1800033fb  nop
0x1800033fc  test    rbx, rbx
0x1800033ff  jz      short loc_180003411
0x180003401  mov     rax, [rbx]
0x180003404  mov     rcx, rbx
0x180003407  mov     rax, [rax+10h]
0x18000340b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003410  nop
0x180003411  test    rdi, rdi
0x180003414  jz      short loc_180003426
0x180003416  mov     rax, [rdi]
0x180003419  mov     rcx, rdi
0x18000341c  mov     rax, [rax+10h]
0x180003420  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003425  nop
0x180003426  jmp     loc_1800032F0
0x18000342b  mov     ebx, 8007000Eh
0x180003430  mov     r9d, 36h ; '6'
0x180003436  lea     r8, aOnecoreuapNetM_7; "onecoreuap\\net\\messaging\\desktoptran"...
0x18000343d  mov     ecx, ebx
0x18000343f  call    Log_HREvent
0x180003444  nop
0x180003445  test    rdi, rdi
0x180003448  jz      short loc_18000345A
0x18000344a  mov     rax, [rdi]
0x18000344d  mov     rcx, rdi
0x180003450  mov     rax, [rax+10h]
0x180003454  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003459  nop
0x18000345a  test    esi, esi
0x18000345c  jz      short loc_180003464
0x18000345e  call    cs:__imp_CoUninitialize
0x180003464  mov     eax, ebx
0x180003466  mov     rcx, [rsp+0C8h+var_58]
0x18000346b  xor     rcx, rsp; StackCookie
0x18000346e  call    __security_check_cookie
0x180003473  add     rsp, 88h
0x18000347a  pop     r15
0x18000347c  pop     r14
0x18000347e  pop     r13
0x180003480  pop     r12
0x180003482  pop     rdi
0x180003483  pop     rsi
0x180003484  pop     rbp
0x180003485  pop     rbx
0x180003486  retn
```
