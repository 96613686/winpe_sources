# CWSManGroupPolicyManager::RegisterForPolicyNotification(IRequestContext *,int)

- ea: `0x1800caa90`
- end: `0x1800caf14`
- name: `?RegisterForPolicyNotification@CWSManGroupPolicyManager@@AEAAHPEAVIRequestContext@@H@Z`
- size: `1156`
- prototype: `__int64 __fastcall(PVOID Context, struct IRequestContext *, int)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1800e4110`

## callees

- `0x180005d10`
- `0x180010030`
- `0x180019950`
- `0x18004a900`
- `0x180071400`
- `0x18007d980`
- `0x1800caa90`
- `0x1800caf1c`
- `0x1800cb04c`
- `0x1800f9230`
- `0x18010e054`
- `0x180112380`
- `0x1801123a8`
- `0x18011a6d4`
- `0x18011d870`
- `0x18011dc70`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800cab66`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800cab66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cac0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cacad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cad89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cadda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800caed4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cac0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cacad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cad89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cadda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800caed4`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800caeca`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800caeca`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800cad5f`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800cad5f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800cabfa`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800cabfa`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x1800caca3`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x1800caca3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800cab8e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800cab8e`

## string_xrefs

- `0x1800cab0b`: `onecore\admin\wmi\wmx\binaries\service\wsmanmemory.cpp`
- `0x1800cac4c`: `CreateEvent`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CWSManGroupPolicyManager::RegisterForPolicyNotification(
        HMODULE **Context,
        struct IRequestContext *a2,
        int a3)
{
  CHeap *v6; // rcx
  CHeap *v7; // rcx
  CWSManGroupPolicyCache *v8; // r12
  void *Handle; // rax
  CWSManGroupPolicyCache *v11; // rax
  HMODULE *EventW; // rax
  HMODULE *v13; // rbx
  DWORD LastError; // eax
  DWORD v15; // ebx
  DWORD v16; // eax
  DWORD v17; // ebx
  HMODULE *v18; // rsi
  FARPROC ProcAddress; // rdi
  DWORD v20; // eax
  DWORD v21; // eax
  unsigned int v22; // ebx
  const unsigned __int16 *v23; // rdx
  HMODULE *v24; // rcx
  void *v25; // rbx
  void *phNewWaitObject; // [rsp+30h] [rbp-18h] BYREF
  _QWORD v27[2]; // [rsp+38h] [rbp-10h] BYREF
  CWSManGroupPolicyCache *v28; // [rsp+A8h] [rbp+60h] BYREF

  v6 = (CHeap *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_f70e972d993d3b5c7751a89ee7db7ab3_Traceguids, Context);
  if ( !CHeap::GetHandle(v6) )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\wsmanmemory.cpp", 170, L"170", 0x54Fu, 0);
LABEL_6:
    v8 = 0;
    goto LABEL_7;
  }
  Handle = CHeap::GetHandle(v7);
  v11 = (CWSManGroupPolicyCache *)HeapAlloc(Handle, 0, 0xB0u);
  if ( !v11 )
    goto LABEL_6;
  v8 = CWSManGroupPolicyCache::CWSManGroupPolicyCache(v11);
LABEL_7:
  v28 = v8;
  if ( !v8 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_f70e972d993d3b5c7751a89ee7db7ab3_Traceguids);
    if ( a2 )
      (*(void (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a2 + 24LL))(a2);
    SetLastError(0xEu);
    AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&v28);
    return 0;
  }
  if ( !CWSManGroupPolicyCache::Initialize(v8, a2, (struct CWSManGroupPolicyManager *)Context) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_f70e972d993d3b5c7751a89ee7db7ab3_Traceguids);
    AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&v28);
    return 0;
  }
  EventW = (HMODULE *)CreateEventW(0, 0, 0, 0);
  v13 = EventW;
  v27[0] = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    v15 = LastError;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_f70e972d993d3b5c7751a89ee7db7ab3_Traceguids, LastError);
    if ( a2 )
      (*(void (__fastcall **)(struct IRequestContext *, __int64, const wchar_t *, _QWORD))(*(_QWORD *)a2 + 88LL))(
        a2,
        1077134180,
        L"CreateEvent",
        v15);
    AutoCleanup<AutoHandle,void *>::ReleasePtr(v27);
    AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&v28);
    return 0;
  }
  phNewWaitObject = 0;
  if ( !RegisterWaitForSingleObject(
          &phNewWaitObject,
          EventW,
          CWSManGroupPolicyManager::_PolicyChangedCallback,
          Context,
          0xFFFFFFFF,
          0x10u) )
  {
    v16 = GetLastError();
    v17 = v16;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_f70e972d993d3b5c7751a89ee7db7ab3_Traceguids, v16);
    if ( a2 )
      (*(void (__fastcall **)(struct IRequestContext *, __int64, const wchar_t *, _QWORD))(*(_QWORD *)a2 + 88LL))(
        a2,
        1077134180,
        L"RegisterWaitForSingleObject",
        v17);
LABEL_35:
    AutoCleanup<AutoWaitHandle,void *>::ReleasePtr(&phNewWaitObject);
    AutoCleanup<AutoHandle,void *>::ReleasePtr(v27);
    AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&v28);
    return 0;
  }
  v18 = (HMODULE *)phNewWaitObject;
  phNewWaitObject = 0;
  AutoCleanup<AutoWaitHandle,void *>::ReleasePtr(Context + 5);
  Context[5] = v18;
  v27[0] = 0;
  AutoCleanup<AutoHandle,void *>::ReleasePtr(Context + 4);
  Context[4] = v13;
  ProcAddress = GetProcAddress(*Context[2], "RegisterGPNotification");
  if ( !ProcAddress )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
    {
      v20 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_f70e972d993d3b5c7751a89ee7db7ab3_Traceguids, v20);
    }
    goto LABEL_42;
  }
  if ( (unsigned __int8)IsRegisterGPNotificationInternalWorkerPresent()
    && !((unsigned int (__fastcall *)(HMODULE *, __int64))ProcAddress)(v13, 1) )
  {
LABEL_42:
    v21 = GetLastError();
    v22 = v21;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
      WPP_SF_dq(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_f70e972d993d3b5c7751a89ee7db7ab3_Traceguids, v21, Context);
    if ( WSMan::EventHandler::IsEventEnabled(&LOG_WSMAN_OP_POLICY_CHANGE_NOTIFICATION_FAILURE) )
    {
      v23 = L"Client";
      if ( !a3 )
        v23 = L"Server";
      WSMan::LogEvent<unsigned short const *,long>(
        (struct _EVENT_DESCRIPTOR *)&LOG_WSMAN_OP_POLICY_CHANGE_NOTIFICATION_FAILURE,
        v23,
        v22);
    }
    if ( a2 )
      (*(void (__fastcall **)(struct IRequestContext *, __int64, __int64, _QWORD))(*(_QWORD *)a2 + 64LL))(
        a2,
        2150859217LL,
        1077134584,
        v22);
    goto LABEL_35;
  }
  v24 = Context[25];
  if ( v24 )
    (*((void (__fastcall **)(HMODULE *, _QWORD, _QWORD))*v24 + 1))(v24, 0, 0);
  v28 = 0;
  Context[25] = (HMODULE *)v8;
  v25 = phNewWaitObject;
  phNewWaitObject = 0;
  if ( v25 && !UnregisterWaitEx(v25, (HANDLE)0xFFFFFFFFFFFFFFFFLL) && GetLastError() != 997 )
    PrintUnregisterWaitTrace(v25);
  AutoCleanup<AutoHandle,void *>::ReleasePtr(v27);
  AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(&v28);
  return 1;
}

```

## disassembly

```asm
0x1800caa90  push    rbp
0x1800caa92  push    rbx
0x1800caa93  push    rsi
0x1800caa94  push    rdi
0x1800caa95  push    r12
0x1800caa97  push    r13
0x1800caa99  push    r14
0x1800caa9b  push    r15
0x1800caa9d  mov     rbp, rsp
0x1800caaa0  sub     rsp, 48h
0x1800caaa4  mov     r13d, r8d
0x1800caaa7  mov     r14, rdx
0x1800caaaa  mov     r15, rcx
0x1800caaad  lea     rsi, WPP_GLOBAL_Control
0x1800caab4  lea     rbx, WPP_f70e972d993d3b5c7751a89ee7db7ab3_Traceguids
0x1800caabb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800caac2  cmp     rcx, rsi
0x1800caac5  jz      short loc_1800CAAE4
0x1800caac7  test    dword ptr [rcx+1Ch], 200000h
0x1800caace  jz      short loc_1800CAAE4
0x1800caad0  mov     edx, 1Ch
0x1800caad5  mov     r9, r15
0x1800caad8  mov     r8, rbx
0x1800caadb  mov     rcx, [rcx+10h]
0x1800caadf  call    WPP_SF_q
0x1800caae4  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x1800caae9  xor     edi, edi
0x1800caaeb  test    rax, rax
0x1800caaee  jnz     loc_1800CAB7E
0x1800caaf4  mov     qword ptr [rsp+48h+dwMilliseconds], rdi; struct IRequestContext *
0x1800caaf9  mov     r9d, 54Fh; unsigned int
0x1800caaff  lea     r8, a170; "170"
0x1800cab06  mov     edx, 0AAh; unsigned int
0x1800cab0b  lea     rcx, aOnecoreAdminWm_20; "onecore\\admin\\wmi\\wmx\\binaries\\ser"...
0x1800cab12  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x1800cab17  mov     r12, rdi
0x1800cab1a  mov     [rbp+arg_18], r12
0x1800cab1e  test    r12, r12
0x1800cab21  jnz     loc_1800CABAD
0x1800cab27  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cab2e  cmp     rcx, rsi
0x1800cab31  jz      short loc_1800CAB4D
0x1800cab33  test    dword ptr [rcx+1Ch], 400000h
0x1800cab3a  jz      short loc_1800CAB4D
0x1800cab3c  lea     edx, [r12+1Dh]
0x1800cab41  mov     r8, rbx
0x1800cab44  mov     rcx, [rcx+10h]
0x1800cab48  call    WPP_SF_
0x1800cab4d  test    r14, r14
0x1800cab50  jz      short loc_1800CAB61
0x1800cab52  mov     rax, [r14]
0x1800cab55  mov     rcx, r14
0x1800cab58  mov     rax, [rax+18h]
0x1800cab5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cab61  mov     ecx, 0Eh; dwErrCode
0x1800cab66  call    cs:__imp_SetLastError
0x1800cab6c  nop
0x1800cab6d  lea     rcx, [rbp+arg_18]
0x1800cab71  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VWSManHttpListener@@@@PEAVWSManHttpListener@@@@AEAAXXZ; AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(void)
0x1800cab76  nop
0x1800cab77  xor     eax, eax
0x1800cab79  jmp     loc_1800CAF03
0x1800cab7e  call    ?GetHandle@CHeap@@IEBAPEAXXZ; CHeap::GetHandle(void)
0x1800cab83  xor     edx, edx; dwFlags
0x1800cab85  mov     r8d, 0B0h; dwBytes
0x1800cab8b  mov     rcx, rax; hHeap
0x1800cab8e  call    cs:__imp_HeapAlloc
0x1800cab94  test    rax, rax
0x1800cab97  jz      loc_1800CAB17
0x1800cab9d  mov     rcx, rax; this
0x1800caba0  call    ??0CWSManGroupPolicyCache@@QEAA@XZ; CWSManGroupPolicyCache::CWSManGroupPolicyCache(void)
0x1800caba5  mov     r12, rax
0x1800caba8  jmp     loc_1800CAB1A
0x1800cabad  mov     r8, r15; struct CWSManGroupPolicyManager *
0x1800cabb0  mov     rdx, r14; struct IRequestContext *
0x1800cabb3  mov     rcx, r12; this
0x1800cabb6  call    ?Initialize@CWSManGroupPolicyCache@@QEAAHPEAVIRequestContext@@PEAVCWSManGroupPolicyManager@@@Z; CWSManGroupPolicyCache::Initialize(IRequestContext *,CWSManGroupPolicyManager *)
0x1800cabbb  test    eax, eax
0x1800cabbd  jnz     short loc_1800CABF0
0x1800cabbf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cabc6  cmp     rcx, rsi
0x1800cabc9  jz      short loc_1800CABE4
0x1800cabcb  test    dword ptr [rcx+1Ch], 400000h
0x1800cabd2  jz      short loc_1800CABE4
0x1800cabd4  lea     edx, [rax+1Eh]
0x1800cabd7  mov     r8, rbx
0x1800cabda  mov     rcx, [rcx+10h]
0x1800cabde  call    WPP_SF_
0x1800cabe3  nop
0x1800cabe4  lea     rcx, [rbp+arg_18]
0x1800cabe8  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VWSManHttpListener@@@@PEAVWSManHttpListener@@@@AEAAXXZ; AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(void)
0x1800cabed  nop
0x1800cabee  jmp     short loc_1800CAB77
0x1800cabf0  xor     r9d, r9d; lpName
0x1800cabf3  xor     r8d, r8d; bInitialState
0x1800cabf6  xor     edx, edx; bManualReset
0x1800cabf8  xor     ecx, ecx; lpEventAttributes
0x1800cabfa  call    cs:__imp_CreateEventW
0x1800cac00  mov     rbx, rax
0x1800cac03  mov     [rbp+var_10], rax
0x1800cac07  test    rax, rax
0x1800cac0a  jnz     short loc_1800CAC7E
0x1800cac0c  call    cs:__imp_GetLastError
0x1800cac12  mov     ebx, eax
0x1800cac14  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cac1b  cmp     rcx, rsi
0x1800cac1e  jz      short loc_1800CAC41
0x1800cac20  test    dword ptr [rcx+1Ch], 400000h
0x1800cac27  jz      short loc_1800CAC41
0x1800cac29  mov     edx, 1Fh
0x1800cac2e  mov     r9d, eax
0x1800cac31  lea     r8, WPP_f70e972d993d3b5c7751a89ee7db7ab3_Traceguids
0x1800cac38  mov     rcx, [rcx+10h]
0x1800cac3c  call    WPP_SF_d
0x1800cac41  test    r14, r14
0x1800cac44  jz      short loc_1800CAC65
0x1800cac46  mov     rax, [r14]
0x1800cac49  mov     r9d, ebx
0x1800cac4c  lea     r8, aCreateevent; "CreateEvent"
0x1800cac53  mov     edx, 4033C364h
0x1800cac58  mov     rcx, r14
0x1800cac5b  mov     rax, [rax+58h]
0x1800cac5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cac64  nop
0x1800cac65  lea     rcx, [rbp+var_10]
0x1800cac69  call    ?ReleasePtr@?$AutoCleanup@VAutoHandle@@PEAX@@AEAAXXZ; AutoCleanup<AutoHandle,void *>::ReleasePtr(void)
0x1800cac6e  nop
0x1800cac6f  lea     rcx, [rbp+arg_18]
0x1800cac73  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VWSManHttpListener@@@@PEAVWSManHttpListener@@@@AEAAXXZ; AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(void)
0x1800cac78  nop
0x1800cac79  jmp     loc_1800CAB77
0x1800cac7e  mov     [rbp+phNewWaitObject], rdi
0x1800cac82  mov     [rsp+48h+dwFlags], 10h; dwFlags
0x1800cac8a  mov     [rsp+48h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x1800cac92  mov     r9, r15; Context
0x1800cac95  lea     r8, ?_PolicyChangedCallback@CWSManGroupPolicyManager@@CAXPEAXE@Z; Callback
0x1800cac9c  mov     rdx, rbx; hObject
0x1800cac9f  lea     rcx, [rbp+phNewWaitObject]; phNewWaitObject
0x1800caca3  call    cs:__imp_RegisterWaitForSingleObject
0x1800caca9  test    eax, eax
0x1800cacab  jnz     short loc_1800CAD29
0x1800cacad  call    cs:__imp_GetLastError
0x1800cacb3  mov     ebx, eax
0x1800cacb5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cacbc  cmp     rcx, rsi
0x1800cacbf  jz      short loc_1800CACE2
0x1800cacc1  test    dword ptr [rcx+1Ch], 200000h
0x1800cacc8  jz      short loc_1800CACE2
0x1800cacca  mov     edx, 20h ; ' '
0x1800caccf  mov     r9d, eax
0x1800cacd2  lea     r8, WPP_f70e972d993d3b5c7751a89ee7db7ab3_Traceguids
0x1800cacd9  mov     rcx, [rcx+10h]
0x1800cacdd  call    WPP_SF_d
0x1800cace2  test    r14, r14
0x1800cace5  jz      short loc_1800CAD06
0x1800cace7  mov     rax, [r14]
0x1800cacea  mov     r9d, ebx
0x1800caced  lea     r8, aRegisterwaitfo; "RegisterWaitForSingleObject"
0x1800cacf4  mov     edx, 4033C364h
0x1800cacf9  mov     rcx, r14
0x1800cacfc  mov     rax, [rax+58h]
0x1800cad00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cad05  nop
0x1800cad06  lea     rcx, [rbp+phNewWaitObject]
0x1800cad0a  call    ?ReleasePtr@?$AutoCleanup@VAutoWaitHandle@@PEAX@@AEAAXXZ; AutoCleanup<AutoWaitHandle,void *>::ReleasePtr(void)
0x1800cad0f  nop
0x1800cad10  lea     rcx, [rbp+var_10]
0x1800cad14  call    ?ReleasePtr@?$AutoCleanup@VAutoHandle@@PEAX@@AEAAXXZ; AutoCleanup<AutoHandle,void *>::ReleasePtr(void)
0x1800cad19  nop
0x1800cad1a  lea     rcx, [rbp+arg_18]
0x1800cad1e  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VWSManHttpListener@@@@PEAVWSManHttpListener@@@@AEAAXXZ; AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(void)
0x1800cad23  nop
0x1800cad24  jmp     loc_1800CAB77
0x1800cad29  mov     rsi, [rbp+phNewWaitObject]
0x1800cad2d  mov     [rbp+phNewWaitObject], rdi
0x1800cad31  lea     rcx, [r15+28h]
0x1800cad35  call    ?ReleasePtr@?$AutoCleanup@VAutoWaitHandle@@PEAX@@AEAAXXZ; AutoCleanup<AutoWaitHandle,void *>::ReleasePtr(void)
0x1800cad3a  mov     [r15+28h], rsi
0x1800cad3e  xor     esi, esi
0x1800cad40  mov     [rbp+var_10], rsi
0x1800cad44  lea     rcx, [r15+20h]
0x1800cad48  call    ?ReleasePtr@?$AutoCleanup@VAutoHandle@@PEAX@@AEAAXXZ; AutoCleanup<AutoHandle,void *>::ReleasePtr(void)
0x1800cad4d  mov     [r15+20h], rbx
0x1800cad51  mov     rcx, [r15+10h]
0x1800cad55  lea     rdx, aRegistergpnoti; "RegisterGPNotification"
0x1800cad5c  mov     rcx, [rcx]; hModule
0x1800cad5f  call    cs:__imp_GetProcAddress
0x1800cad65  mov     rdi, rax
0x1800cad68  test    rax, rax
0x1800cad6b  jnz     short loc_1800CADAE
0x1800cad6d  mov     rax, cs:WPP_GLOBAL_Control
0x1800cad74  lea     rdi, WPP_GLOBAL_Control
0x1800cad7b  cmp     rax, rdi
0x1800cad7e  jz      short loc_1800CADDA
0x1800cad80  test    dword ptr [rax+1Ch], 200h
0x1800cad87  jz      short loc_1800CADDA
0x1800cad89  call    cs:__imp_GetLastError
0x1800cad8f  lea     edx, [rsi+0Eh]
0x1800cad92  mov     r9d, eax
0x1800cad95  lea     r8, WPP_f70e972d993d3b5c7751a89ee7db7ab3_Traceguids
0x1800cad9c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cada3  mov     rcx, [rcx+10h]
0x1800cada7  call    WPP_SF_d
0x1800cadac  jmp     short loc_1800CADDA
0x1800cadae  call    IsRegisterGPNotificationInternalWorkerPresent
0x1800cadb3  test    al, al
0x1800cadb5  jz      loc_1800CAE8E
0x1800cadbb  mov     edx, 1
0x1800cadc0  mov     rcx, rbx
0x1800cadc3  mov     rax, rdi
0x1800cadc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cadcb  test    eax, eax
0x1800cadcd  jnz     loc_1800CAE8E
0x1800cadd3  lea     rdi, WPP_GLOBAL_Control
0x1800cadda  call    cs:__imp_GetLastError
0x1800cade0  mov     ebx, eax
0x1800cade2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cade9  cmp     rcx, rdi
0x1800cadec  jz      short loc_1800CAE14
0x1800cadee  test    dword ptr [rcx+1Ch], 200000h
0x1800cadf5  jz      short loc_1800CAE14
0x1800cadf7  mov     edx, 21h ; '!'
0x1800cadfc  mov     qword ptr [rsp+48h+dwMilliseconds], r15
0x1800cae01  mov     r9d, eax
0x1800cae04  lea     r8, WPP_f70e972d993d3b5c7751a89ee7db7ab3_Traceguids
0x1800cae0b  mov     rcx, [rcx+10h]
0x1800cae0f  call    WPP_SF_dq
0x1800cae14  lea     rcx, LOG_WSMAN_OP_POLICY_CHANGE_NOTIFICATION_FAILURE; struct _EVENT_DESCRIPTOR *
0x1800cae1b  call    ?IsEventEnabled@EventHandler@WSMan@@SA_NAEBU_EVENT_DESCRIPTOR@@@Z; WSMan::EventHandler::IsEventEnabled(_EVENT_DESCRIPTOR const &)
0x1800cae20  test    al, al
0x1800cae22  jz      short loc_1800CAE48
0x1800cae24  lea     rax, aServer_0; "Server"
0x1800cae2b  lea     rdx, aClient_0; "Client"
0x1800cae32  test    r13d, r13d
0x1800cae35  cmovz   rdx, rax
0x1800cae39  mov     r8d, ebx
0x1800cae3c  lea     rcx, LOG_WSMAN_OP_POLICY_CHANGE_NOTIFICATION_FAILURE
0x1800cae43  call    ??$LogEvent@PEBGJ@WSMan@@YAXAEBU_EVENT_DESCRIPTOR@@PEBGJ@Z; WSMan::LogEvent<ushort const *,long>(_EVENT_DESCRIPTOR const &,ushort const *,long)
0x1800cae48  test    r14, r14
0x1800cae4b  jz      short loc_1800CAE6B
0x1800cae4d  mov     rax, [r14]
0x1800cae50  mov     r9d, ebx
0x1800cae53  mov     edx, 803381D1h
0x1800cae58  mov     r8d, 4033C4F8h
0x1800cae5e  mov     rcx, r14
0x1800cae61  mov     rax, [rax+40h]
0x1800cae65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cae6a  nop
0x1800cae6b  lea     rcx, [rbp+phNewWaitObject]
0x1800cae6f  call    ?ReleasePtr@?$AutoCleanup@VAutoWaitHandle@@PEAX@@AEAAXXZ; AutoCleanup<AutoWaitHandle,void *>::ReleasePtr(void)
0x1800cae74  nop
0x1800cae75  lea     rcx, [rbp+var_10]
0x1800cae79  call    ?ReleasePtr@?$AutoCleanup@VAutoHandle@@PEAX@@AEAAXXZ; AutoCleanup<AutoHandle,void *>::ReleasePtr(void)
0x1800cae7e  nop
0x1800cae7f  lea     rcx, [rbp+arg_18]
0x1800cae83  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VWSManHttpListener@@@@PEAVWSManHttpListener@@@@AEAAXXZ; AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(void)
0x1800cae88  nop
0x1800cae89  jmp     loc_1800CAB77
0x1800cae8e  mov     rcx, [r15+0C8h]
0x1800cae95  test    rcx, rcx
0x1800cae98  jz      short loc_1800CAEAB
0x1800cae9a  mov     rax, [rcx]
0x1800cae9d  xor     r8d, r8d
0x1800caea0  xor     edx, edx
0x1800caea2  mov     rax, [rax+8]
0x1800caea6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800caeab  mov     [rbp+arg_18], rsi
0x1800caeaf  mov     [r15+0C8h], r12
0x1800caeb6  mov     rbx, [rbp+phNewWaitObject]
0x1800caeba  mov     [rbp+phNewWaitObject], rsi
0x1800caebe  test    rbx, rbx
0x1800caec1  jz      short loc_1800CAEEA
0x1800caec3  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x1800caec7  mov     rcx, rbx; WaitHandle
0x1800caeca  call    cs:__imp_UnregisterWaitEx
0x1800caed0  test    eax, eax
0x1800caed2  jnz     short loc_1800CAEEA
0x1800caed4  call    cs:__imp_GetLastError
0x1800caeda  cmp     eax, 3E5h
0x1800caedf  jz      short loc_1800CAEEA
0x1800caee1  mov     rcx, rbx; void *
0x1800caee4  call    ?PrintUnregisterWaitTrace@@YAXPEAX@Z; PrintUnregisterWaitTrace(void *)
0x1800caee9  nop
0x1800caeea  lea     rcx, [rbp+var_10]
0x1800caeee  call    ?ReleasePtr@?$AutoCleanup@VAutoHandle@@PEAX@@AEAAXXZ; AutoCleanup<AutoHandle,void *>::ReleasePtr(void)
0x1800caef3  nop
0x1800caef4  lea     rcx, [rbp+arg_18]
0x1800caef8  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VWSManHttpListener@@@@PEAVWSManHttpListener@@@@AEAAXXZ; AutoCleanup<AutoRelease<WSManHttpListener>,WSManHttpListener *>::ReleasePtr(void)
0x1800caefd  nop
0x1800caefe  mov     eax, 1
0x1800caf03  add     rsp, 48h
0x1800caf07  pop     r15
0x1800caf09  pop     r14
0x1800caf0b  pop     r13
0x1800caf0d  pop     r12
0x1800caf0f  pop     rdi
0x1800caf10  pop     rsi
0x1800caf11  pop     rbx
0x1800caf12  pop     rbp
0x1800caf13  retn
  ... truncated ...
```
