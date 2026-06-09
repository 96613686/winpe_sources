# ProxResManInitialize

- ea: `0x18007c82c`
- end: `0x18007ca88`
- name: `ProxResManInitialize`
- size: `604`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180031a80`

## callees

- `0x18000c944`
- `0x18000c964`
- `0x18007bb18`
- `0x18007c018`
- `0x18007c82c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007c9e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007ca4f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007ca6b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007c9e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007ca4f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007ca6b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007c84a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007c84a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007c8a5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007c8a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c8bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c916`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c98e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c8bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c916`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c98e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007c8d2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007c942`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007c9ac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007c8d2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007c942`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007c9ac`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18007c99b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18007c99b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18007c926`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18007c967`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18007c926`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18007c967`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18007c93a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18007c93a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18007c9a4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18007c9a4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18007c979`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18007c979`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18007c931`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18007c931`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18007c901`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18007c901`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007c8ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007c8ca`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ProxResManInitialize(_WORD *a1)
{
  unsigned int v2; // ebx
  unsigned __int16 v3; // di
  unsigned __int16 *v4; // rdx
  const char *v5; // r9
  HANDLE EventW; // r14
  HANDLE v7; // r15
  DWORD LastError; // ebx
  __int64 v9; // rdx
  struct _TP_WAIT *ThreadpoolWait; // r14
  struct _TP_WAIT *v11; // r15
  DWORD v12; // ebx
  struct _TP_WORK *ThreadpoolWork; // r14
  struct _TP_WORK *v14; // r15
  DWORD v15; // ebx
  __int64 result; // rax
  int v17; // [rsp+20h] [rbp-28h]
  int v18; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  char v20; // [rsp+50h] [rbp+8h] BYREF
  char v21; // [rsp+51h] [rbp+9h]
  struct _RTL_CRITICAL_SECTION *v22; // [rsp+58h] [rbp+10h]

  EnterCriticalSection(&g_resManInitializationLock);
  v22 = &g_resManInitializationLock;
  if ( !a1 )
  {
    v2 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x69,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\utils\\proxresman\\lib\\proxresman.cpp",
      (const char *)0x80070057LL,
      v18);
LABEL_17:
    LeaveCriticalSection(&g_resManInitializationLock);
    return v2;
  }
  v3 = 1;
  v21 = 1;
  v4 = (unsigned __int16 *)qword_180133298;
  if ( g_resManInitializationTokens == (void *)qword_180133298 )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    v7 = g_hResourceManagerNotification;
    if ( (char *)g_hResourceManagerNotification - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      LastError = GetLastError();
      CloseHandle(v7);
      SetLastError(LastError);
    }
    g_hResourceManagerNotification = EventW;
    if ( (((unsigned __int64)EventW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      v9 = 116;
LABEL_16:
      v2 = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v9,
             (unsigned int)"onecoreuap\\ds\\nfc\\product\\utils\\proxresman\\lib\\proxresman.cpp",
             v5);
      wil::details::lambda_call__ProxResManInitialize_::_2_::_lambda_1___::_lambda_call__ProxResManInitialize_::_2_::_lambda_1___(&v20);
      goto LABEL_17;
    }
    ThreadpoolWait = CreateThreadpoolWait(ResourceManagerNotificationCallback, 0, 0);
    v11 = g_threadpoolResourceManagerNotification;
    if ( g_threadpoolResourceManagerNotification )
    {
      v12 = GetLastError();
      SetThreadpoolWait(v11, 0, 0);
      WaitForThreadpoolWaitCallbacks(v11, 1);
      CloseThreadpoolWait(v11);
      SetLastError(v12);
    }
    g_threadpoolResourceManagerNotification = ThreadpoolWait;
    if ( !ThreadpoolWait )
    {
      v9 = 122;
      goto LABEL_16;
    }
    SetThreadpoolWait(ThreadpoolWait, g_hResourceManagerNotification, 0);
    ThreadpoolWork = CreateThreadpoolWork(ProxResManProcessPendingStartsCallback, 0, 0);
    v14 = g_threadpoolStartMonitor;
    if ( g_threadpoolStartMonitor )
    {
      v15 = GetLastError();
      WaitForThreadpoolWorkCallbacks(v14, 1);
      CloseThreadpoolWork(v14);
      SetLastError(v15);
    }
    g_threadpoolStartMonitor = ThreadpoolWork;
    if ( !ThreadpoolWork )
    {
      v9 = 127;
      goto LABEL_16;
    }
    v4 = (unsigned __int16 *)qword_180133298;
  }
  else
  {
    v21 = 0;
  }
  if ( uTokenIndex != 0xFFFF )
    v3 = uTokenIndex + 1;
  try
  {
    uTokenIndex = v3;
    if ( v4 == (unsigned __int16 *)qword_1801332A0 )
    {
      std::vector<unsigned short>::_Emplace_reallocate<unsigned short const &>();
    }
    else
    {
      *v4 = v3;
      qword_180133298 += 2;
    }
    *a1 = uTokenIndex;
    v21 = 0;
    wil::details::lambda_call__ProxResManInitialize_::_2_::_lambda_1___::_lambda_call__ProxResManInitialize_::_2_::_lambda_1___(&v20);
    LeaveCriticalSection(&g_resManInitializationLock);
    result = 0;
  }
  catch ( std::bad_alloc )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8F,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\utils\\proxresman\\lib\\proxresman.cpp",
      (const char *)0x8007000ELL,
      v17);
    wil::details::lambda_call__ProxResManInitialize_::_2_::_lambda_1___::_lambda_call__ProxResManInitialize_::_2_::_lambda_1___(&v20);
    LeaveCriticalSection(&g_resManInitializationLock);
    return 2147942414LL;
  }
  return result;
}

```

## disassembly

```asm
0x18007c82c  mov     [rsp+arg_10], rbx
0x18007c831  push    rsi
0x18007c832  push    rdi
0x18007c833  push    r12
0x18007c835  push    r14
0x18007c837  push    r15; int
0x18007c839  sub     rsp, 20h
0x18007c83d  mov     r12, rcx
0x18007c840  lea     rsi, ?g_resManInitializationLock@@3Vcritical_section@wil@@A; wil::critical_section g_resManInitializationLock
0x18007c847  mov     rcx, rsi; lpCriticalSection
0x18007c84a  call    cs:__imp_EnterCriticalSection
0x18007c850  mov     [rsp+48h+arg_8], rsi
0x18007c855  test    r12, r12
0x18007c858  jnz     short loc_18007C87D
0x18007c85a  mov     rcx, [rsp+48h]; this
0x18007c85f  mov     ebx, 80070057h
0x18007c864  mov     r9d, ebx; char *
0x18007c867  lea     r8, aOnecoreuapDsNf_2; "onecoreuap\\ds\\nfc\\product\\utils\\pr"...
0x18007c86e  lea     edx, [r12+69h]; void *
0x18007c873  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007c878  jmp     loc_18007C9E0
0x18007c87d  mov     edi, 1
0x18007c882  mov     [rsp+48h+arg_1], dil
0x18007c887  mov     rdx, cs:qword_180133298
0x18007c88e  cmp     cs:?g_resManInitializationTokens@@3V?$vector@GV?$allocator@G@std@@@std@@A, rdx; std::vector<ushort> g_resManInitializationTokens
0x18007c895  jnz     loc_18007C9F9
0x18007c89b  xor     r9d, r9d; lpName
0x18007c89e  xor     r8d, r8d; bInitialState
0x18007c8a1  xor     edx, edx; bManualReset
0x18007c8a3  xor     ecx, ecx; lpEventAttributes
0x18007c8a5  call    cs:__imp_CreateEventW
0x18007c8ab  mov     r14, rax
0x18007c8ae  mov     r15, cs:?g_hResourceManagerNotification@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> g_hResourceManagerNotification
0x18007c8b5  lea     rdx, [r15-1]
0x18007c8b9  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18007c8bd  ja      short loc_18007C8D8
0x18007c8bf  call    cs:__imp_GetLastError
0x18007c8c5  mov     ebx, eax
0x18007c8c7  mov     rcx, r15; hObject
0x18007c8ca  call    cs:__imp_CloseHandle
0x18007c8d0  mov     ecx, ebx; dwErrCode
0x18007c8d2  call    cs:__imp_SetLastError
0x18007c8d8  mov     cs:?g_hResourceManagerNotification@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@A, r14; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> g_hResourceManagerNotification
0x18007c8df  lea     rax, [r14+1]
0x18007c8e3  test    rax, 0FFFFFFFFFFFFFFFEh
0x18007c8e9  jnz     short loc_18007C8F5
0x18007c8eb  mov     edx, 74h ; 't'
0x18007c8f0  jmp     loc_18007C9C2
0x18007c8f5  xor     r8d, r8d; pcbe
0x18007c8f8  xor     edx, edx; pv
0x18007c8fa  lea     rcx, ResourceManagerNotificationCallback; pfnwa
0x18007c901  call    cs:__imp_CreateThreadpoolWait
0x18007c907  mov     r14, rax
0x18007c90a  mov     r15, cs:?g_threadpoolResourceManagerNotification@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>> g_threadpoolResourceManagerNotification
0x18007c911  test    r15, r15
0x18007c914  jz      short loc_18007C948
0x18007c916  call    cs:__imp_GetLastError
0x18007c91c  mov     ebx, eax
0x18007c91e  xor     r8d, r8d; pftTimeout
0x18007c921  xor     edx, edx; h
0x18007c923  mov     rcx, r15; pwa
0x18007c926  call    cs:__imp_SetThreadpoolWait
0x18007c92c  mov     edx, edi; fCancelPendingCallbacks
0x18007c92e  mov     rcx, r15; pwa
0x18007c931  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18007c937  mov     rcx, r15; pwa
0x18007c93a  call    cs:__imp_CloseThreadpoolWait
0x18007c940  mov     ecx, ebx; dwErrCode
0x18007c942  call    cs:__imp_SetLastError
0x18007c948  mov     cs:?g_threadpoolResourceManagerNotification@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A, r14; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>> g_threadpoolResourceManagerNotification
0x18007c94f  test    r14, r14
0x18007c952  jnz     short loc_18007C95A
0x18007c954  lea     edx, [r14+7Ah]
0x18007c958  jmp     short loc_18007C9C2
0x18007c95a  xor     r8d, r8d; pftTimeout
0x18007c95d  mov     rdx, cs:?g_hResourceManagerNotification@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@A; h
0x18007c964  mov     rcx, r14; pwa
0x18007c967  call    cs:__imp_SetThreadpoolWait
0x18007c96d  xor     r8d, r8d; pcbe
0x18007c970  xor     edx, edx; pv
0x18007c972  lea     rcx, ?ProxResManProcessPendingStartsCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18007c979  call    cs:__imp_CreateThreadpoolWork
0x18007c97f  mov     r14, rax
0x18007c982  mov     r15, cs:?g_threadpoolStartMonitor@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>> g_threadpoolStartMonitor
0x18007c989  test    r15, r15
0x18007c98c  jz      short loc_18007C9B2
0x18007c98e  call    cs:__imp_GetLastError
0x18007c994  mov     ebx, eax
0x18007c996  mov     edx, edi; fCancelPendingCallbacks
0x18007c998  mov     rcx, r15; pwk
0x18007c99b  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18007c9a1  mov     rcx, r15; pwk
0x18007c9a4  call    cs:__imp_CloseThreadpoolWork
0x18007c9aa  mov     ecx, ebx; dwErrCode
0x18007c9ac  call    cs:__imp_SetLastError
0x18007c9b2  mov     cs:?g_threadpoolStartMonitor@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A, r14; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>> g_threadpoolStartMonitor
0x18007c9b9  test    r14, r14
0x18007c9bc  jnz     short loc_18007C9F0
0x18007c9be  lea     edx, [r14+7Fh]; void *
0x18007c9c2  lea     r8, aOnecoreuapDsNf_2; "onecoreuap\\ds\\nfc\\product\\utils\\pr"...
0x18007c9c9  mov     rcx, [rsp+48h]; this
0x18007c9ce  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18007c9d3  mov     ebx, eax
0x18007c9d5  lea     rcx, [rsp+48h+arg_0]
0x18007c9da  call    wil__details__lambda_call__ProxResManInitialize____2____lambda_1______lambda_call__ProxResManInitialize____2____lambda_1___
0x18007c9df  nop
0x18007c9e0  mov     rcx, rsi; lpCriticalSection
0x18007c9e3  call    cs:__imp_LeaveCriticalSection
0x18007c9e9  mov     eax, ebx
0x18007c9eb  jmp     loc_18007CA76
0x18007c9f0  mov     rdx, cs:qword_180133298
0x18007c9f7  jmp     short loc_18007C9FE
0x18007c9f9  mov     [rsp+48h+arg_1], 0
0x18007c9fe  movzx   eax, cs:?uTokenIndex@@3GA; ushort uTokenIndex
0x18007ca05  add     ax, di
0x18007ca08  jz      short loc_18007CA0D
0x18007ca0a  movzx   edi, ax
0x18007ca0d  mov     cs:?uTokenIndex@@3GA, di; ushort uTokenIndex
0x18007ca14  cmp     rdx, cs:qword_1801332A0
0x18007ca1b  jz      short loc_18007CA2A
0x18007ca1d  mov     [rdx], di
0x18007ca20  add     cs:qword_180133298, 2
0x18007ca28  jmp     short loc_18007CA30
0x18007ca2a  call    ??$_Emplace_reallocate@AEBG@?$vector@GV?$allocator@G@std@@@std@@AEAAPEAGQEAGAEBG@Z; std::vector<ushort>::_Emplace_reallocate<ushort const &>(ushort * const,ushort const &)
0x18007ca2f  nop
0x18007ca30  movzx   eax, cs:?uTokenIndex@@3GA; ushort uTokenIndex
0x18007ca37  mov     [r12], ax
0x18007ca3c  mov     [rsp+48h+arg_1], 0
0x18007ca41  lea     rcx, [rsp+48h+arg_0]
0x18007ca46  call    wil__details__lambda_call__ProxResManInitialize____2____lambda_1______lambda_call__ProxResManInitialize____2____lambda_1___
0x18007ca4b  nop
0x18007ca4c  mov     rcx, rsi; lpCriticalSection
0x18007ca4f  call    cs:__imp_LeaveCriticalSection
0x18007ca55  xor     eax, eax
0x18007ca57  jmp     short loc_18007CA76
0x18007ca59  lea     rcx, [rsp+48h+arg_0]
0x18007ca5e  call    wil__details__lambda_call__ProxResManInitialize____2____lambda_1______lambda_call__ProxResManInitialize____2____lambda_1___
0x18007ca63  nop
0x18007ca64  lea     rcx, ?g_resManInitializationLock@@3Vcritical_section@wil@@A; lpCriticalSection
0x18007ca6b  call    cs:__imp_LeaveCriticalSection
0x18007ca71  mov     eax, 8007000Eh
0x18007ca76  mov     rbx, [rsp+48h+arg_10]
0x18007ca7b  add     rsp, 20h
0x18007ca7f  pop     r15
0x18007ca81  pop     r14
0x18007ca83  pop     r12
0x18007ca85  pop     rdi
0x18007ca86  pop     rsi
0x18007ca87  retn
```
