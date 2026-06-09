# CBroadcastConfigManager::Initialize(void)

- ea: `0x180063f98`
- end: `0x180064088`
- name: `?Initialize@CBroadcastConfigManager@@QEAAJXZ`
- size: `240`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180015c78`

## callees

- `0x180051420`
- `0x180063f98`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180063fdd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180063fdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063fec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064037`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063fec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064037`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18006402d`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18006402d`

## string_xrefs

- `0x180063ffe`: `Failed to create m_hNotifyEvent`
- `0x180064058`: `CBroadcastConfigManager::Initialize`
- `0x180064049`: `Failed to create m_hNotifyEventWait`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CBroadcastConfigManager::Initialize(char *Context)
{
  char *v2; // rdi
  HANDLE EventW; // rax
  signed int v4; // eax
  signed int LastError; // eax

  v2 = Context + 40;
  (**((void (__fastcall ***)(char *))Context + 5))(Context + 40);
  if ( !*((_DWORD *)Context + 2) )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)Context + 2) = EventW;
    if ( EventW )
    {
      if ( !RegisterWaitForSingleObject(
              (PHANDLE)Context + 3,
              EventW,
              CBroadcastConfigManager::NotifyBroadcastConfigChangeCallbackStatic,
              Context,
              0xFFFFFFFF,
              0) )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        LogSmsRouterError(
          "CBroadcastConfigManager::Initialize",
          0x2Eu,
          LastError,
          "Failed to create m_hNotifyEventWait");
      }
    }
    else
    {
      v4 = GetLastError();
      if ( v4 > 0 )
        v4 = (unsigned __int16)v4 | 0x80070000;
      LogSmsRouterError("CBroadcastConfigManager::Initialize", 0x27u, v4, "Failed to create m_hNotifyEvent");
    }
    *((_DWORD *)Context + 2) = 1;
  }
  (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 8LL))(v2);
  return 0;
}

```

## disassembly

```asm
0x180063f98  mov     [rsp+arg_0], rbx
0x180063f9d  push    rdi
0x180063f9e  sub     rsp, 40h
0x180063fa2  mov     rbx, rcx
0x180063fa5  lea     rax, ??_7?$lock_guard@Vrecursive_mutex@Common@Sms@Windows@@@Common@Sms@Windows@@6B@; const Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable'
0x180063fac  mov     [rsp+48h+var_18], rax
0x180063fb1  lea     rdi, [rcx+28h]
0x180063fb5  mov     [rsp+48h+var_10], rdi
0x180063fba  mov     rax, [rdi]
0x180063fbd  mov     rcx, rdi
0x180063fc0  mov     rax, [rax]
0x180063fc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063fc8  nop
0x180063fc9  cmp     dword ptr [rbx+8], 0
0x180063fcd  jnz     loc_18006406B
0x180063fd3  xor     r9d, r9d; lpName
0x180063fd6  xor     r8d, r8d; bInitialState
0x180063fd9  xor     edx, edx; bManualReset
0x180063fdb  xor     ecx, ecx; lpEventAttributes
0x180063fdd  call    cs:__imp_CreateEventW
0x180063fe3  mov     [rbx+10h], rax
0x180063fe7  test    rax, rax
0x180063fea  jnz     short loc_18006400C
0x180063fec  call    cs:__imp_GetLastError
0x180063ff2  test    eax, eax
0x180063ff4  jle     short loc_180063FFE
0x180063ff6  movzx   eax, ax
0x180063ff9  or      eax, 80070000h
0x180063ffe  lea     r9, aFailedToCreate_6; "Failed to create m_hNotifyEvent"
0x180064005  mov     edx, 27h ; '''
0x18006400a  jmp     short loc_180064055
0x18006400c  lea     rcx, [rbx+18h]; phNewWaitObject
0x180064010  mov     [rsp+48h+dwFlags], 0; dwFlags
0x180064018  mov     [rsp+48h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x180064020  mov     r9, rbx; Context
0x180064023  lea     r8, ?NotifyBroadcastConfigChangeCallbackStatic@CBroadcastConfigManager@@SAXPEAXE@Z; Callback
0x18006402a  mov     rdx, rax; hObject
0x18006402d  call    cs:__imp_RegisterWaitForSingleObject
0x180064033  test    eax, eax
0x180064035  jnz     short loc_180064064
0x180064037  call    cs:__imp_GetLastError
0x18006403d  test    eax, eax
0x18006403f  jle     short loc_180064049
0x180064041  movzx   eax, ax
0x180064044  or      eax, 80070000h
0x180064049  lea     r9, aFailedToCreate_10; "Failed to create m_hNotifyEventWait"
0x180064050  mov     edx, 2Eh ; '.'; unsigned int
0x180064055  mov     r8d, eax; int
0x180064058  lea     rcx, aCbroadcastconf_0; "CBroadcastConfigManager::Initialize"
0x18006405f  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x180064064  mov     dword ptr [rbx+8], 1
0x18006406b  mov     rax, [rdi]
0x18006406e  mov     rcx, rdi
0x180064071  mov     rax, [rax+8]
0x180064075  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006407a  nop
0x18006407b  xor     eax, eax
0x18006407d  mov     rbx, [rsp+48h+arg_0]
0x180064082  add     rsp, 40h
0x180064086  pop     rdi
0x180064087  retn
```
