# Process(int)

- ea: `0x14002d070`
- end: `0x14002d442`
- name: `?Process@@YAJH@Z`
- size: `978`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x14002e680`

## callees

- `0x140007358`
- `0x1400084f8`
- `0x14000a530`
- `0x14000b010`
- `0x140017090`
- `0x14001ec18`
- `0x140020150`
- `0x140022b5c`
- `0x1400234b8`
- `0x1400242f8`
- `0x140024408`
- `0x1400251dc`
- `0x140025aa0`
- `0x1400262d0`
- `0x140026adc`
- `0x140027388`
- `0x140027a10`
- `0x140028068`
- `0x140028468`
- `0x14002861c`
- `0x140029a60`
- `0x14002be6c`
- `0x14002d070`
- `0x140048010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14002d337`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14002d39f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14002d337`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14002d39f`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x14002d37f`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x14002d37f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002d3a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002d3a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14002d346`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14002d35a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14002d346`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14002d35a`
- `wbemcomn!GetMemLogObject` at `0x14002d3e0`
- `wbemcomn!GetMemLogObject` at `0x14002d3e0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14002d3eb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14002d3eb`
- `ext-ms-win-ntuser-message-l1-1-0!TranslateMessage` at `0x14002d304`
- `ext-ms-win-ntuser-message-l1-1-0!TranslateMessage` at `0x14002d304`
- `ext-ms-win-ntuser-message-l1-1-0!GetMessageW` at `0x14002d320`
- `ext-ms-win-ntuser-message-l1-1-0!GetMessageW` at `0x14002d320`
- `ext-ms-win-ntuser-message-l1-1-0!DispatchMessageW` at `0x14002d30e`
- `ext-ms-win-ntuser-message-l1-1-0!DispatchMessageW` at `0x14002d30e`
- `OLEAUT32!__imp_SysAllocString` at `0x14002d0ff`
- `OLEAUT32!__imp_SysAllocString` at `0x14002d0ff`
- `OLEAUT32!__imp_SysFreeString` at `0x14002d231`
- `OLEAUT32!__imp_SysFreeString` at `0x14002d231`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14002d3d6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14002d3d6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14002d0e6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14002d0e6`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Process(int a1)
{
  bool v2; // cl
  signed int inited; // ebx
  OLECHAR *v4; // rbx
  struct IWbemContext *v5; // rdx
  struct IWbemPath *v6; // r8
  unsigned __int64 v7; // rdx
  struct IWbemContext *v8; // rdx
  struct IWbemPath *v9; // r8
  unsigned __int64 v10; // rdx
  struct IWbemServices *v11; // rax
  __int64 v12; // r8
  struct IWbemServices *v13; // rdi
  struct IWbemServicesVtbl *v14; // rbx
  int v15; // ebx
  HANDLE CurrentProcess; // rdi
  void *v17; // rbx
  HANDLE v18; // rax
  CMemoryLog *MemLogObject; // rax
  MSG Msg; // [rsp+50h] [rbp-49h] BYREF
  __int128 v22; // [rsp+80h] [rbp-19h]
  _BYTE v23[4]; // [rsp+90h] [rbp-9h] BYREF
  int v24; // [rsp+94h] [rbp-5h]
  __int64 v25; // [rsp+98h] [rbp-1h]
  __int128 v26; // [rsp+A0h] [rbp+7h]
  __int128 v27; // [rsp+B0h] [rbp+17h]
  __int128 v28; // [rsp+C0h] [rbp+27h]
  __int64 v29; // [rsp+D0h] [rbp+37h]
  struct IWbemServices *v30; // [rsp+108h] [rbp+6Fh] BYREF
  HANDLE TargetHandle; // [rsp+110h] [rbp+77h] BYREF

  inited = InitComServer();
  if ( inited < 0 )
    goto LABEL_33;
  ProviderSubSystem_Globals::Initialize_SharedCounters(v2);
  if ( (int)ProviderSubSystem_Globals::Initialize_Events() >= 0
    && (int)ProviderSubSystem_Common_Globals::CreateSystemAces() >= 0 )
  {
    TargetHandle = 0;
    if ( CoCreateInstance(&CLSID_WbemLocator, 0, 5u, &IID_IUnknown, &TargetHandle) >= 0 )
    {
      v30 = 0;
      v4 = SysAllocString(L"Root");
      if ( v4 )
      {
        if ( (*(int (__fastcall **)(HANDLE, OLECHAR *, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, struct IWbemServices **))(*(_QWORD *)TargetHandle + 24LL))(
               TargetHandle,
               v4,
               0,
               0,
               0,
               0,
               0,
               0,
               &v30) >= 0 )
        {
          HIDWORD(Msg.hwnd) = 0;
          *(_QWORD *)&Msg.message = 0;
          LODWORD(Msg.wParam) = 120000;
          Msg.lParam = 0;
          Msg.time = 120000;
          *(_QWORD *)&Msg.pt.y = 0;
          v22 = 0;
          if ( (int)CServerObject_GlobalRegistration::SetContext((CServerObject_GlobalRegistration *)&Msg, v5, v6, v30) >= 0
            && (int)CServerObject_GlobalRegistration::QueryRepository((CServerObject_GlobalRegistration *)&Msg, v7) >= 0 )
          {
            ProviderSubSystem_Globals::s_InternalCacheTimeout = Msg.wParam;
            ProviderSubSystem_Globals::s_ObjectCacheTimeout = Msg.wParam;
            ProviderSubSystem_Globals::s_EventCacheTimeout = Msg.time;
            v24 = 0;
            v25 = 0;
            v26 = 0;
            v27 = 0;
            v28 = 0;
            v29 = 0;
            if ( (int)CServerObject_HostQuotaRegistration::SetContext(
                        (CServerObject_HostQuotaRegistration *)v23,
                        v8,
                        v9,
                        v30) >= 0
              && (int)CServerObject_HostQuotaRegistration::QueryRepository(
                        (CServerObject_HostQuotaRegistration *)v23,
                        v10) >= 0 )
            {
              ProviderSubSystem_Globals::s_Quota_HandleCount = v27;
              ProviderSubSystem_Globals::s_Quota_NumberOfThreads = DWORD2(v26);
              *(_QWORD *)&ProviderSubSystem_Globals::s_Quota_PrivatePageCount = v25;
            }
            CServerObject_HostQuotaRegistration::~CServerObject_HostQuotaRegistration((CServerObject_HostQuotaRegistration *)v23);
          }
          ((void (__fastcall *)(struct IWbemServices *))v30->lpVtbl->Release)(v30);
          CServerObject_GlobalRegistration::~CServerObject_GlobalRegistration((CServerObject_GlobalRegistration *)&Msg);
        }
        SysFreeString(v4);
      }
      (*(void (__fastcall **)(HANDLE))(*(_QWORD *)TargetHandle + 16LL))(TargetHandle);
    }
    v11 = (struct IWbemServices *)operator new(0xF8u);
    v13 = v11;
    v30 = v11;
    if ( v11 )
    {
      v14 = (struct IWbemServicesVtbl *)ProviderSubSystem_Globals::s_Allocator;
      WmiThread<unsigned long>::WmiThread<unsigned long>(v11, ProviderSubSystem_Globals::s_Allocator, v12, 120000);
      v13->lpVtbl = (struct IWbemServicesVtbl *)&FactoryLifeTimeThread::`vftable';
      v13[30].lpVtbl = v14;
    }
    else
    {
      v13 = 0;
    }
    g_Thread = (struct FactoryLifeTimeThread *)v13;
    if ( v13 )
    {
      ((void (__fastcall *)(struct IWbemServices *))v13->lpVtbl->AddRef)(v13);
      LODWORD(v30) = -1;
      if ( !(*(unsigned int (__fastcall **)(struct FactoryLifeTimeThread *, struct IWbemServices **))(*(_QWORD *)g_Thread + 64LL))(
              g_Thread,
              &v30) )
      {
        if ( (int)Enqueue_ObjectDestruction() >= 0 )
        {
          v15 = InitFactories(a1);
          if ( (unsigned __int8)IsCreateWindowExWPresent() )
          {
            if ( v15 >= 0 )
            {
              memset(&Msg, 0, sizeof(Msg));
              while ( GetMessageW(&Msg, 0, 0, 0) )
              {
                TranslateMessage(&Msg);
                DispatchMessageW(&Msg);
              }
            }
          }
          else
          {
            WaitForSingleObject(g_ShutdownEvent, 0xFFFFFFFF);
          }
          Dequeue_ObjectDestruction();
        }
        TargetHandle = 0;
        CurrentProcess = GetCurrentProcess();
        v17 = (void *)*((_QWORD *)g_Thread + 15);
        v18 = GetCurrentProcess();
        DuplicateHandle(v18, v17, CurrentProcess, &TargetHandle, 0, 0, 2u);
        (*(void (__fastcall **)(struct FactoryLifeTimeThread *))(*(_QWORD *)g_Thread + 16LL))(g_Thread);
        WaitForSingleObject(TargetHandle, 0xFFFFFFFF);
        CloseHandle(TargetHandle);
        g_Thread = 0;
        Dequeue_ObjectDestruction();
      }
    }
    exitIfManaged();
    ProviderSubSystem_Common_Globals::DeleteSystemAces();
    ProviderSubSystem_Globals::UnInitialize_Events();
  }
  inited = ProviderSubSystem_Globals::UnInitialize_SharedCounters();
  RevokeFactories();
  CoUninitialize();
  if ( inited < 0 )
  {
LABEL_33:
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, inited);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      25,
      WPP_06f3c53ba90d3c5290ee926c0e3353ee_Traceguids,
      (unsigned int)inited);
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x14002d070  mov     [rsp-8+arg_0], rbx
0x14002d075  mov     [rsp-8+arg_18], rsi
0x14002d07a  push    rbp
0x14002d07b  push    rdi
0x14002d07c  push    r14
0x14002d07e  lea     rbp, [rsp-47h]
0x14002d083  sub     rsp, 0E0h
0x14002d08a  mov     esi, ecx
0x14002d08c  mov     edx, 3; unsigned int
0x14002d091  lea     ecx, [rdx-1]; unsigned int
0x14002d094  call    ?InitComServer@@YAJKK@Z; InitComServer(ulong,ulong)
0x14002d099  mov     ebx, eax
0x14002d09b  xor     r14d, r14d
0x14002d09e  test    eax, eax
0x14002d0a0  js      loc_14002D3E0
0x14002d0a6  call    ?Initialize_SharedCounters@ProviderSubSystem_Globals@@SAJ_N@Z; ProviderSubSystem_Globals::Initialize_SharedCounters(bool)
0x14002d0ab  call    ?Initialize_Events@ProviderSubSystem_Globals@@SAJXZ; ProviderSubSystem_Globals::Initialize_Events(void)
0x14002d0b0  test    eax, eax
0x14002d0b2  js      loc_14002D3CA
0x14002d0b8  call    ?CreateSystemAces@ProviderSubSystem_Common_Globals@@SAJXZ; ProviderSubSystem_Common_Globals::CreateSystemAces(void)
0x14002d0bd  test    eax, eax
0x14002d0bf  js      loc_14002D3CA
0x14002d0c5  mov     [rbp+57h+TargetHandle], r14
0x14002d0c9  lea     rax, [rbp+57h+TargetHandle]
0x14002d0cd  mov     [rsp+0F0h+ppv], rax; ppv
0x14002d0d2  lea     r9, IID_IUnknown; riid
0x14002d0d9  xor     edx, edx; pUnkOuter
0x14002d0db  lea     r8d, [r14+5]; dwClsContext
0x14002d0df  lea     rcx, CLSID_WbemLocator; rclsid
0x14002d0e6  call    cs:__imp_CoCreateInstance
0x14002d0ec  test    eax, eax
0x14002d0ee  js      loc_14002D247
0x14002d0f4  mov     [rbp+57h+arg_8], r14
0x14002d0f8  lea     rcx, aRoot; "Root"
0x14002d0ff  call    cs:__imp_SysAllocString
0x14002d105  mov     rbx, rax
0x14002d108  test    rax, rax
0x14002d10b  jz      loc_14002D237
0x14002d111  mov     rcx, [rbp+57h+TargetHandle]
0x14002d115  mov     rdx, [rcx]
0x14002d118  mov     rax, [rdx+18h]
0x14002d11c  lea     rdx, [rbp+57h+arg_8]
0x14002d120  mov     [rsp+0F0h+var_B0], rdx
0x14002d125  mov     [rsp+0F0h+var_B8], r14
0x14002d12a  mov     qword ptr [rsp+0F0h+dwOptions], r14
0x14002d12f  mov     [rsp+0F0h+bInheritHandle], r14d
0x14002d134  mov     [rsp+0F0h+ppv], r14
0x14002d139  xor     r9d, r9d
0x14002d13c  xor     r8d, r8d
0x14002d13f  mov     rdx, rbx
0x14002d142  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002d147  test    eax, eax
0x14002d149  js      loc_14002D22E
0x14002d14f  mov     dword ptr [rbp+57h+Msg.hwnd+4], r14d
0x14002d153  mov     qword ptr [rbp+57h+Msg.message], r14
0x14002d157  mov     dword ptr [rbp+57h+Msg.wParam], 1D4C0h
0x14002d15e  mov     [rbp+57h+Msg.lParam], r14
0x14002d162  mov     [rbp+57h+Msg.time], 1D4C0h
0x14002d169  mov     qword ptr [rbp+57h+Msg.pt.y], r14
0x14002d16d  xorps   xmm0, xmm0
0x14002d170  movdqa  [rbp+57h+var_70], xmm0
0x14002d175  mov     r9, [rbp+57h+arg_8]; struct IWbemServices *
0x14002d179  lea     rcx, [rbp+57h+Msg]; this
0x14002d17d  call    ?SetContext@CServerObject_GlobalRegistration@@QEAAJPEAUIWbemContext@@PEAUIWbemPath@@PEAUIWbemServices@@@Z; CServerObject_GlobalRegistration::SetContext(IWbemContext *,IWbemPath *,IWbemServices *)
0x14002d182  test    eax, eax
0x14002d184  js      loc_14002D214
0x14002d18a  lea     rcx, [rbp+57h+Msg]; this
0x14002d18e  call    ?QueryRepository@CServerObject_GlobalRegistration@@QEAAJ_K@Z; CServerObject_GlobalRegistration::QueryRepository(unsigned __int64)
0x14002d193  test    eax, eax
0x14002d195  js      short loc_14002D214
0x14002d197  mov     eax, dword ptr [rbp+57h+Msg.wParam]
0x14002d19a  mov     cs:?s_InternalCacheTimeout@ProviderSubSystem_Globals@@2KA, eax; ulong ProviderSubSystem_Globals::s_InternalCacheTimeout
0x14002d1a0  mov     cs:?s_ObjectCacheTimeout@ProviderSubSystem_Globals@@2KA, eax; ulong ProviderSubSystem_Globals::s_ObjectCacheTimeout
0x14002d1a6  mov     eax, [rbp+57h+Msg.time]
0x14002d1a9  mov     cs:?s_EventCacheTimeout@ProviderSubSystem_Globals@@2KA, eax; ulong ProviderSubSystem_Globals::s_EventCacheTimeout
0x14002d1af  mov     [rbp+57h+var_5C], r14d
0x14002d1b3  mov     [rbp+57h+var_58], r14
0x14002d1b7  xorps   xmm0, xmm0
0x14002d1ba  movdqa  [rbp+57h+var_50], xmm0
0x14002d1bf  xorps   xmm1, xmm1
0x14002d1c2  movdqa  [rbp+57h+var_40], xmm1
0x14002d1c7  movdqa  [rbp+57h+var_30], xmm0
0x14002d1cc  mov     [rbp+57h+var_20], r14
0x14002d1d0  mov     r9, [rbp+57h+arg_8]; struct IWbemServices *
0x14002d1d4  lea     rcx, [rbp+57h+var_60]; this
0x14002d1d8  call    ?SetContext@CServerObject_HostQuotaRegistration@@QEAAJPEAUIWbemContext@@PEAUIWbemPath@@PEAUIWbemServices@@@Z; CServerObject_HostQuotaRegistration::SetContext(IWbemContext *,IWbemPath *,IWbemServices *)
0x14002d1dd  test    eax, eax
0x14002d1df  js      short loc_14002D20B
0x14002d1e1  lea     rcx, [rbp+57h+var_60]; this
0x14002d1e5  call    ?QueryRepository@CServerObject_HostQuotaRegistration@@QEAAJ_K@Z; CServerObject_HostQuotaRegistration::QueryRepository(unsigned __int64)
0x14002d1ea  test    eax, eax
0x14002d1ec  js      short loc_14002D20B
0x14002d1ee  mov     eax, dword ptr [rbp+57h+var_40]
0x14002d1f1  mov     cs:?s_Quota_HandleCount@ProviderSubSystem_Globals@@2KA, eax; ulong ProviderSubSystem_Globals::s_Quota_HandleCount
0x14002d1f7  mov     eax, dword ptr [rbp+57h+var_50+8]
0x14002d1fa  mov     cs:?s_Quota_NumberOfThreads@ProviderSubSystem_Globals@@2KA, eax; ulong ProviderSubSystem_Globals::s_Quota_NumberOfThreads
0x14002d200  mov     rax, [rbp+57h+var_58]
0x14002d204  mov     cs:?s_Quota_PrivatePageCount@ProviderSubSystem_Globals@@2_KA, rax; unsigned __int64 ProviderSubSystem_Globals::s_Quota_PrivatePageCount
0x14002d20b  lea     rcx, [rbp+57h+var_60]; this
0x14002d20f  call    ??1CServerObject_HostQuotaRegistration@@QEAA@XZ; CServerObject_HostQuotaRegistration::~CServerObject_HostQuotaRegistration(void)
0x14002d214  mov     rcx, [rbp+57h+arg_8]
0x14002d218  mov     rax, [rcx]
0x14002d21b  mov     rax, [rax+10h]
0x14002d21f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002d224  nop
0x14002d225  lea     rcx, [rbp+57h+Msg]; this
0x14002d229  call    ??1CServerObject_GlobalRegistration@@QEAA@XZ; CServerObject_GlobalRegistration::~CServerObject_GlobalRegistration(void)
0x14002d22e  mov     rcx, rbx; bstrString
0x14002d231  call    cs:__imp_SysFreeString
0x14002d237  mov     rcx, [rbp+57h+TargetHandle]
0x14002d23b  mov     rax, [rcx]
0x14002d23e  mov     rax, [rax+10h]
0x14002d242  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002d247  mov     ecx, 0F8h; dwBytes
0x14002d24c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002d251  mov     rdi, rax
0x14002d254  mov     [rbp+57h+arg_8], rax
0x14002d258  test    rax, rax
0x14002d25b  jz      short loc_14002D288
0x14002d25d  mov     rbx, cs:?s_Allocator@ProviderSubSystem_Globals@@2PEAVWmiAllocator@@EA; WmiAllocator * ProviderSubSystem_Globals::s_Allocator
0x14002d264  mov     r9d, 1D4C0h
0x14002d26a  mov     rdx, rbx
0x14002d26d  mov     rcx, rax
0x14002d270  call    ??0?$WmiThread@K@@QEAA@AEAVWmiAllocator@@PEBGKK@Z; WmiThread<ulong>::WmiThread<ulong>(WmiAllocator &,ushort const *,ulong,ulong)
0x14002d275  lea     rax, ??_7FactoryLifeTimeThread@@6B@; const FactoryLifeTimeThread::`vftable'
0x14002d27c  mov     [rdi], rax
0x14002d27f  mov     [rdi+0F0h], rbx
0x14002d286  jmp     short loc_14002D28B
0x14002d288  mov     rdi, r14
0x14002d28b  mov     cs:?g_Thread@@3PEAVFactoryLifeTimeThread@@EA, rdi; FactoryLifeTimeThread * g_Thread
0x14002d292  test    rdi, rdi
0x14002d295  jz      loc_14002D3BB
0x14002d29b  mov     rax, [rdi]
0x14002d29e  mov     rcx, rdi
0x14002d2a1  mov     rax, [rax+8]
0x14002d2a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002d2aa  mov     dword ptr [rbp+57h+arg_8], 0FFFFFFFFh
0x14002d2b1  mov     rcx, cs:?g_Thread@@3PEAVFactoryLifeTimeThread@@EA; FactoryLifeTimeThread * g_Thread
0x14002d2b8  mov     rax, [rcx]
0x14002d2bb  lea     rdx, [rbp+57h+arg_8]
0x14002d2bf  mov     rax, [rax+40h]
0x14002d2c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002d2c8  test    eax, eax
0x14002d2ca  jnz     loc_14002D3BB
0x14002d2d0  call    ?Enqueue_ObjectDestruction@@YAJPEAV?$WmiThread@K@@@Z; Enqueue_ObjectDestruction(WmiThread<ulong> *)
0x14002d2d5  test    eax, eax
0x14002d2d7  js      short loc_14002D342
0x14002d2d9  mov     ecx, esi; int
0x14002d2db  call    ?InitFactories@@YAJH@Z; InitFactories(int)
0x14002d2e0  mov     ebx, eax
0x14002d2e2  call    IsCreateWindowExWPresent
0x14002d2e7  test    al, al
0x14002d2e9  jz      short loc_14002D32D
0x14002d2eb  test    ebx, ebx
0x14002d2ed  js      short loc_14002D33D
0x14002d2ef  xorps   xmm0, xmm0
0x14002d2f2  movups  xmmword ptr [rbp+57h+Msg.hwnd], xmm0
0x14002d2f6  movups  xmmword ptr [rbp+57h+Msg.wParam], xmm0
0x14002d2fa  movups  xmmword ptr [rbp+57h+Msg.time], xmm0
0x14002d2fe  jmp     short loc_14002D314
0x14002d300  lea     rcx, [rbp+57h+Msg]; lpMsg
0x14002d304  call    cs:__imp_TranslateMessage
0x14002d30a  lea     rcx, [rbp+57h+Msg]; lpMsg
0x14002d30e  call    cs:__imp_DispatchMessageW
0x14002d314  xor     r9d, r9d; wMsgFilterMax
0x14002d317  xor     r8d, r8d; wMsgFilterMin
0x14002d31a  xor     edx, edx; hWnd
0x14002d31c  lea     rcx, [rbp+57h+Msg]; lpMsg
0x14002d320  call    cs:__imp_GetMessageW
0x14002d326  cmp     eax, 1
0x14002d329  jz      short loc_14002D300
0x14002d32b  jmp     short loc_14002D33D
0x14002d32d  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14002d330  mov     rcx, cs:?g_ShutdownEvent@@3PEAXEA; hHandle
0x14002d337  call    cs:__imp_WaitForSingleObject
0x14002d33d  call    ?Dequeue_ObjectDestruction@@YAJPEAV?$WmiThread@K@@@Z; Dequeue_ObjectDestruction(WmiThread<ulong> *)
0x14002d342  mov     [rbp+57h+TargetHandle], r14
0x14002d346  call    cs:__imp_GetCurrentProcess
0x14002d34c  mov     rdi, rax
0x14002d34f  mov     rcx, cs:?g_Thread@@3PEAVFactoryLifeTimeThread@@EA; FactoryLifeTimeThread * g_Thread
0x14002d356  mov     rbx, [rcx+78h]
0x14002d35a  call    cs:__imp_GetCurrentProcess
0x14002d360  mov     [rsp+0F0h+dwOptions], 2; dwOptions
0x14002d368  mov     [rsp+0F0h+bInheritHandle], r14d; bInheritHandle
0x14002d36d  mov     dword ptr [rsp+0F0h+ppv], r14d; dwDesiredAccess
0x14002d372  lea     r9, [rbp+57h+TargetHandle]; lpTargetHandle
0x14002d376  mov     r8, rdi; hTargetProcessHandle
0x14002d379  mov     rdx, rbx; hSourceHandle
0x14002d37c  mov     rcx, rax; hSourceProcessHandle
0x14002d37f  call    cs:__imp_DuplicateHandle
0x14002d385  mov     rcx, cs:?g_Thread@@3PEAVFactoryLifeTimeThread@@EA; FactoryLifeTimeThread * g_Thread
0x14002d38c  mov     rax, [rcx]
0x14002d38f  mov     rax, [rax+10h]
0x14002d393  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002d398  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14002d39b  mov     rcx, [rbp+57h+TargetHandle]; hHandle
0x14002d39f  call    cs:__imp_WaitForSingleObject
0x14002d3a5  mov     rcx, [rbp+57h+TargetHandle]; hObject
0x14002d3a9  call    cs:__imp_CloseHandle
0x14002d3af  mov     cs:?g_Thread@@3PEAVFactoryLifeTimeThread@@EA, r14; FactoryLifeTimeThread * g_Thread
0x14002d3b6  call    ?Dequeue_ObjectDestruction@@YAJPEAV?$WmiThread@K@@@Z; Dequeue_ObjectDestruction(WmiThread<ulong> *)
0x14002d3bb  call    ?exitIfManaged@@YAXXZ; exitIfManaged(void)
0x14002d3c0  call    ?DeleteSystemAces@ProviderSubSystem_Common_Globals@@SAJXZ; ProviderSubSystem_Common_Globals::DeleteSystemAces(void)
0x14002d3c5  call    ?UnInitialize_Events@ProviderSubSystem_Globals@@SAJXZ; ProviderSubSystem_Globals::UnInitialize_Events(void)
0x14002d3ca  call    ?UnInitialize_SharedCounters@ProviderSubSystem_Globals@@SAJXZ; ProviderSubSystem_Globals::UnInitialize_SharedCounters(void)
0x14002d3cf  mov     ebx, eax
0x14002d3d1  call    ?RevokeFactories@@YAJXZ; RevokeFactories(void)
0x14002d3d6  call    cs:__imp_CoUninitialize
0x14002d3dc  test    ebx, ebx
0x14002d3de  jns     short loc_14002D3F1
0x14002d3e0  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x14002d3e6  mov     edx, ebx
0x14002d3e8  mov     rcx, rax
0x14002d3eb  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x14002d3f1  lea     rax, WPP_GLOBAL_Control
0x14002d3f8  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d3ff  cmp     rcx, rax
0x14002d402  jz      short loc_14002D428
0x14002d404  test    byte ptr [rcx+1Ch], 4
0x14002d408  jz      short loc_14002D428
0x14002d40a  cmp     byte ptr [rcx+19h], 2
0x14002d40e  jb      short loc_14002D428
0x14002d410  mov     edx, 19h
0x14002d415  mov     r9d, ebx
0x14002d418  lea     r8, WPP_06f3c53ba90d3c5290ee926c0e3353ee_Traceguids
0x14002d41f  mov     rcx, [rcx+10h]
0x14002d423  call    WPP_SF_d
0x14002d428  mov     eax, ebx
0x14002d42a  lea     r11, [rsp+0F0h+var_10]
0x14002d432  mov     rbx, [r11+20h]
0x14002d436  mov     rsi, [r11+38h]
0x14002d43a  mov     rsp, r11
0x14002d43d  pop     r14
0x14002d43f  pop     rdi
0x14002d440  pop     rbp
0x14002d441  retn
```
