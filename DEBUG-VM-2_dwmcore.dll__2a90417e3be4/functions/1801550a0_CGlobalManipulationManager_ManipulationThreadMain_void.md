# CGlobalManipulationManager::ManipulationThreadMain(void)

- ea: `0x1801550a0`
- end: `0x1801552e1`
- name: `?ManipulationThreadMain@CGlobalManipulationManager@@EEAAJXZ`
- size: `577`
- prototype: `__int64 __fastcall(CGlobalManipulationManager *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18002de54`
- `0x180110480`
- `0x1801550a0`
- `0x1801552f0`
- `0x18015536c`
- `0x180204100`
- `0x180228490`
- `0x1802297c0`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18015512e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18015514f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18015512e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18015514f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18015511a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18015513b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18015511a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18015513b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180155271`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180155271`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180155176`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180155176`
- `CoreMessaging!CoreUICreateEx` at `0x1801550fc`
- `CoreMessaging!CoreUICreateEx` at `0x1801550fc`
- `ext-ms-win-compositor-hosting-l1-2-0!RegisterManipulationThread` at `0x18015516c`
- `ext-ms-win-compositor-hosting-l1-2-0!RegisterManipulationThread` at `0x18015516c`

## pseudocode

```c
__int64 __fastcall CGlobalManipulationManager::ManipulationThreadMain(
        CGlobalManipulationManager *this,
        __int64 a2,
        __int64 a3)
{
  struct IMessageSession **v4; // rdi
  int v5; // eax
  __int64 v6; // r8
  signed int LastError; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  _BYTE v13[16]; // [rsp+30h] [rbp-28h] BYREF
  void *retaddr; // [rsp+58h] [rbp+0h]

  if ( (Microsoft_Windows_Dwm_CoreEnableBits & 0x4000) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Dwm_Core_Provider_Context,
      MANIPULATION_THREAD_STARTUP,
      a3,
      1,
      v13);
  v4 = (struct IMessageSession **)((char *)this + 24);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 24);
  v5 = CoreUICreateEx(1, (char *)this + 24);
  if ( v5 < 0 )
    ModuleFailFastForHRESULT(v5, retaddr);
  EnterCriticalSection(&stru_1803B9968);
  byte_1803B9964 = 0;
  LeaveCriticalSection(&stru_1803B9968);
  EnterCriticalSection(&stru_1803B9928);
  byte_1803B9924 = 0;
  LeaveCriticalSection(&stru_1803B9928);
  if ( (unsigned __int8)IsRegisterManipulationThreadPresent() )
  {
    if ( !(unsigned int)RegisterManipulationThread(CManipulationManager::ManipulationThreadCallback, this) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      if ( LastError >= 0 )
        LastError = -2003304445;
      ModuleFailFastForHRESULT(LastError, retaddr);
    }
    CGlobalManipulationManager::UpdateMMCSSTask(this);
    v8 = CManipulationManager::SetupMessageCallThreadInfo(
           this,
           *v4,
           (int (*)(void *, const void *, int))CManipulationManager::s_ManipulationThreadEndpointProc,
           (CGlobalManipulationManager *)((char *)this + 32));
    if ( v8 < 0 )
      ModuleFailFastForHRESULT(v8, retaddr);
    v9 = (*(__int64 (__fastcall **)(struct IMessageSession *, HANDLE, __int64 (__fastcall *)(), CGlobalManipulationManager *))(*(_QWORD *)*v4 + 272LL))(
           *v4,
           hEvent,
           CGlobalManipulationManager::ManipulationThreadMain_::_25_::_lambda_1_::_lambda_invoker_cdecl_,
           this);
    if ( v9 < 0 )
      ModuleFailFastForHRESULT(v9, retaddr);
    v10 = (*(__int64 (__fastcall **)(struct IMessageSession *, void * near *, __int64 (__fastcall *)(), CGlobalManipulationManager *))(*(_QWORD *)*v4 + 272LL))(
            *v4,
            CManipulationManager::s_rghWaitEvents,
            CGlobalManipulationManager::ManipulationThreadMain_::_30_::_lambda_2_::_lambda_invoker_cdecl_,
            this);
    if ( v10 < 0 )
      ModuleFailFastForHRESULT(v10, retaddr);
    v11 = (*(__int64 (__fastcall **)(struct IMessageSession *, HANDLE, __int64 (__fastcall *)(), CGlobalManipulationManager *))(*(_QWORD *)*v4 + 272LL))(
            *v4,
            qword_1803BB160,
            CGlobalManipulationManager::ManipulationThreadMain_::_35_::_lambda_3_::_lambda_invoker_cdecl_,
            this);
    if ( v11 < 0 )
      ModuleFailFastForHRESULT(v11, retaddr);
    SetEvent(CManipulationManager::s_hManipThreadInitializedWaitEvent);
    (*(void (__fastcall **)(struct IMessageSession *))(*(_QWORD *)*v4 + 232LL))(*v4);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 24);
  }
  CManipulationManager::s_dwManipulationThreadId = 0;
  if ( (Microsoft_Windows_Dwm_CoreEnableBits & 0x4000) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Dwm_Core_Provider_Context,
      MANIPULATION_THREAD_CLEANUP,
      v6,
      1,
      v13);
  return 0;
}

```

## disassembly

```asm
0x1801550a0  mov     [rsp+arg_8], rbx
0x1801550a5  push    rdi
0x1801550a6  sub     rsp, 50h
0x1801550aa  mov     rax, cs:__security_cookie
0x1801550b1  xor     rax, rsp
0x1801550b4  mov     [rsp+58h+var_18], rax
0x1801550b9  test    byte ptr cs:Microsoft_Windows_Dwm_CoreEnableBits+1, 40h
0x1801550c0  mov     rbx, rcx
0x1801550c3  jz      short loc_1801550E8
0x1801550c5  lea     rax, [rsp+58h+var_28]
0x1801550ca  mov     r9d, 1
0x1801550d0  lea     rdx, MANIPULATION_THREAD_STARTUP
0x1801550d7  mov     [rsp+58h+var_38], rax
0x1801550dc  lea     rcx, Microsoft_Windows_Dwm_Core_Provider_Context
0x1801550e3  call    McGenEventWrite_EventWriteTransfer
0x1801550e8  lea     rdi, [rbx+18h]
0x1801550ec  mov     rcx, rdi
0x1801550ef  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801550f4  mov     rdx, rdi
0x1801550f7  mov     ecx, 1
0x1801550fc  call    cs:__imp_CoreUICreateEx
0x180155102  test    eax, eax
0x180155104  jns     short loc_180155113
0x180155106  mov     rdx, [rsp+58h]; void *
0x18015510b  mov     ecx, eax; int
0x18015510d  call    ModuleFailFastForHRESULT
0x180155113  lea     rcx, stru_1803B9968; lpCriticalSection
0x18015511a  call    cs:__imp_EnterCriticalSection
0x180155120  lea     rcx, stru_1803B9968; lpCriticalSection
0x180155127  mov     cs:byte_1803B9964, 0
0x18015512e  call    cs:__imp_LeaveCriticalSection
0x180155134  lea     rcx, stru_1803B9928; lpCriticalSection
0x18015513b  call    cs:__imp_EnterCriticalSection
0x180155141  lea     rcx, stru_1803B9928; lpCriticalSection
0x180155148  mov     cs:byte_1803B9924, 0
0x18015514f  call    cs:__imp_LeaveCriticalSection
0x180155155  call    IsRegisterManipulationThreadPresent
0x18015515a  test    al, al
0x18015515c  jz      loc_180155291
0x180155162  mov     rdx, rbx
0x180155165  lea     rcx, ?ManipulationThreadCallback@CManipulationManager@@SAHPEAU_MIT_INPUT_INTEROP_MESSAGE@@PEAX@Z; CManipulationManager::ManipulationThreadCallback(_MIT_INPUT_INTEROP_MESSAGE *,void *)
0x18015516c  call    cs:__imp_RegisterManipulationThread
0x180155172  test    eax, eax
0x180155174  jnz     short loc_18015519F
0x180155176  call    cs:__imp_GetLastError
0x18015517c  test    eax, eax
0x18015517e  jle     short loc_180155188
0x180155180  movzx   eax, ax
0x180155183  or      eax, 80070000h
0x180155188  mov     rdx, [rsp+58h]; void *
0x18015518d  mov     ecx, 88980003h
0x180155192  test    eax, eax
0x180155194  cmovns  eax, ecx
0x180155197  mov     ecx, eax; int
0x180155199  call    ModuleFailFastForHRESULT
0x18015519f  mov     rcx, rbx; this
0x1801551a2  call    ?UpdateMMCSSTask@CGlobalManipulationManager@@UEAAJXZ; CGlobalManipulationManager::UpdateMMCSSTask(void)
0x1801551a7  mov     rdx, [rdi]; struct IMessageSession *
0x1801551aa  lea     r9, [rbx+20h]; struct CManipulationManager::MessageCallThreadInfo *
0x1801551ae  lea     r8, ?s_ManipulationThreadEndpointProc@CManipulationManager@@KAJPEAXPEBXH@Z; int (*)(void *, const void *, int)
0x1801551b5  mov     rcx, rbx; this
0x1801551b8  call    ?SetupMessageCallThreadInfo@CManipulationManager@@IEAAJPEAUIMessageSession@@P6AJPEAXPEBXH@ZPEAUMessageCallThreadInfo@1@@Z; CManipulationManager::SetupMessageCallThreadInfo(IMessageSession *,long (*)(void *,void const *,int),CManipulationManager::MessageCallThreadInfo *)
0x1801551bd  test    eax, eax
0x1801551bf  jns     short loc_1801551CE
0x1801551c1  mov     rdx, [rsp+58h]; void *
0x1801551c6  mov     ecx, eax; int
0x1801551c8  call    ModuleFailFastForHRESULT
0x1801551ce  mov     rcx, [rdi]
0x1801551d1  lea     r8, _CGlobalManipulationManager__ManipulationThreadMain____25____lambda_1____lambda_invoker_cdecl_
0x1801551d8  mov     rdx, cs:hEvent
0x1801551df  mov     r9, rbx
0x1801551e2  mov     rax, [rcx]
0x1801551e5  mov     rax, [rax+110h]
0x1801551ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801551f1  test    eax, eax
0x1801551f3  jns     short loc_180155202
0x1801551f5  mov     rdx, [rsp+58h]; void *
0x1801551fa  mov     ecx, eax; int
0x1801551fc  call    ModuleFailFastForHRESULT
0x180155202  mov     rcx, [rdi]
0x180155205  lea     r8, _CGlobalManipulationManager__ManipulationThreadMain____30____lambda_2____lambda_invoker_cdecl_
0x18015520c  mov     rdx, cs:?s_rghWaitEvents@CManipulationManager@@1PAPEAXA; void * near * CManipulationManager::s_rghWaitEvents
0x180155213  mov     r9, rbx
0x180155216  mov     rax, [rcx]
0x180155219  mov     rax, [rax+110h]
0x180155220  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180155225  test    eax, eax
0x180155227  jns     short loc_180155236
0x180155229  mov     rdx, [rsp+58h]; void *
0x18015522e  mov     ecx, eax; int
0x180155230  call    ModuleFailFastForHRESULT
0x180155236  mov     rcx, [rdi]
0x180155239  lea     r8, _CGlobalManipulationManager__ManipulationThreadMain____35____lambda_3____lambda_invoker_cdecl_
0x180155240  mov     rdx, cs:qword_1803BB160
0x180155247  mov     r9, rbx
0x18015524a  mov     rax, [rcx]
0x18015524d  mov     rax, [rax+110h]
0x180155254  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180155259  test    eax, eax
0x18015525b  jns     short loc_18015526A
0x18015525d  mov     rdx, [rsp+58h]; void *
0x180155262  mov     ecx, eax; int
0x180155264  call    ModuleFailFastForHRESULT
0x18015526a  mov     rcx, cs:?s_hManipThreadInitializedWaitEvent@CManipulationManager@@1PEAXEA; hEvent
0x180155271  call    cs:__imp_SetEvent
0x180155277  mov     rcx, [rdi]
0x18015527a  mov     rax, [rcx]
0x18015527d  mov     rax, [rax+0E8h]
0x180155284  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180155289  mov     rcx, rdi
0x18015528c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180155291  test    byte ptr cs:Microsoft_Windows_Dwm_CoreEnableBits+1, 40h
0x180155298  mov     cs:?s_dwManipulationThreadId@CManipulationManager@@1KA, 0; ulong CManipulationManager::s_dwManipulationThreadId
0x1801552a2  jz      short loc_1801552C7
0x1801552a4  lea     rax, [rsp+58h+var_28]
0x1801552a9  mov     r9d, 1
0x1801552af  lea     rdx, MANIPULATION_THREAD_CLEANUP
0x1801552b6  mov     [rsp+58h+var_38], rax
0x1801552bb  lea     rcx, Microsoft_Windows_Dwm_Core_Provider_Context
0x1801552c2  call    McGenEventWrite_EventWriteTransfer
0x1801552c7  xor     eax, eax
0x1801552c9  mov     rcx, [rsp+58h+var_18]
0x1801552ce  xor     rcx, rsp; StackCookie
0x1801552d1  call    __security_check_cookie
0x1801552d6  mov     rbx, [rsp+58h+arg_8]
0x1801552db  add     rsp, 50h
0x1801552df  pop     rdi
0x1801552e0  retn
```
