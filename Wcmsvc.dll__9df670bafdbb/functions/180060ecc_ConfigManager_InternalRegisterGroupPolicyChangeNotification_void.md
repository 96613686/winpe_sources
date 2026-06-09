# ConfigManager::InternalRegisterGroupPolicyChangeNotification(void)

- ea: `0x180060ecc`
- end: `0x18006101c`
- name: `?InternalRegisterGroupPolicyChangeNotification@ConfigManager@@AEAAXXZ`
- size: `336`
- prototype: `void __fastcall(ConfigManager *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180060784`

## callees

- `0x180019434`
- `0x1800355b4`
- `0x18003a08c`
- `0x180060ecc`
- `0x1800612c8`
- `0x1800627e8`
- `0x18007103c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180060f19`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180060f19`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180060fd6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180060fd6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180060f94`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180060f94`
- `api-ms-win-security-grouppolicy-l1-1-0!UnregisterGPNotificationInternal` at `0x180060fc8`
- `api-ms-win-security-grouppolicy-l1-1-0!UnregisterGPNotificationInternal` at `0x180060fc8`
- `api-ms-win-security-grouppolicy-l1-1-0!RegisterGPNotificationInternal` at `0x180060f59`
- `api-ms-win-security-grouppolicy-l1-1-0!RegisterGPNotificationInternal` at `0x180060f59`

## string_xrefs

- `0x180060ef9`: `onecoreuap\net\wcm\service\base\configmanager\configmanager.cpp`
- `0x180060f3e`: `onecoreuap\net\wcm\service\base\configmanager\configmanager.cpp`
- `0x180060f68`: `onecoreuap\net\wcm\service\base\configmanager\configmanager.cpp`
- `0x180060fb4`: `onecoreuap\net\wcm\service\base\configmanager\configmanager.cpp`

## pseudocode

```c
void __fastcall ConfigManager::InternalRegisterGroupPolicyChangeNotification(ConfigManager *this)
{
  HANDLE *v2; // rdi
  HANDLE EventW; // rax
  const char *v4; // r9
  const char *v5; // r9
  PTP_WAIT ThreadpoolWait; // rax
  const char *v7; // r9
  struct _TP_WAIT *v8; // rcx
  unsigned int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = (HANDLE *)((char *)this + 32);
  if ( *((_QWORD *)this + 4) )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( *v2 )
    {
      wil::details::in1diag3::Log_Win32(
        retaddr,
        (void *)0x65F,
        (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\configmanager\\configmanager.cpp",
        (const char *)0x139F,
        v9);
      return;
    }
  }
  EventW = CreateEventW(0, 0, 0, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    v2,
    EventW);
  if ( (((unsigned __int64)*v2 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    wil::details::in1diag3::_Log_GetLastError(
      retaddr,
      (void *)0x666,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\configmanager\\configmanager.cpp",
      v4);
    return;
  }
  if ( !(unsigned int)RegisterGPNotificationInternal(*v2, 1) )
  {
    wil::details::in1diag3::_Log_GetLastError(
      retaddr,
      (void *)0x66F,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\configmanager\\configmanager.cpp",
      v5);
LABEL_8:
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      v2,
      0);
    return;
  }
  ThreadpoolWait = CreateThreadpoolWait(ConfigManager::GroupPolicyChangeCallback, 0, 0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(
    (char *)this + 40,
    ThreadpoolWait);
  v8 = (struct _TP_WAIT *)*((_QWORD *)this + 5);
  if ( !v8 )
  {
    wil::details::in1diag3::_Log_GetLastError(
      retaddr,
      (void *)0x679,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\configmanager\\configmanager.cpp",
      v7);
    UnregisterGPNotificationInternal(*v2);
    goto LABEL_8;
  }
  SetThreadpoolWait(v8, *v2, 0);
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 64, WPP_d1926522bc273c8e7056db3405527a30_Traceguids);
  }
}

```

## disassembly

```asm
0x180060ecc  mov     [rsp+arg_8], rbx
0x180060ed1  push    rdi; unsigned int
0x180060ed2  sub     rsp, 20h
0x180060ed6  mov     rbx, rcx
0x180060ed9  lea     rdi, [rcx+20h]
0x180060edd  cmp     qword ptr [rdi], 0
0x180060ee1  jz      short loc_180060F0F
0x180060ee3  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180060ee8  cmp     qword ptr [rdi], 0
0x180060eec  jz      short loc_180060F0F
0x180060eee  mov     rcx, [rsp+28h]; this
0x180060ef3  mov     r9d, 139Fh; char *
0x180060ef9  lea     r8, aOnecoreuapNetW_30; "onecoreuap\\net\\wcm\\service\\base\\co"...
0x180060f00  mov     edx, 65Fh; void *
0x180060f05  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x180060f0a  jmp     loc_180061011
0x180060f0f  xor     r9d, r9d; lpName
0x180060f12  xor     r8d, r8d; bInitialState
0x180060f15  xor     edx, edx; bManualReset
0x180060f17  xor     ecx, ecx; lpEventAttributes
0x180060f19  call    cs:__imp_CreateEventW
0x180060f1f  mov     rdx, rax
0x180060f22  mov     rcx, rdi
0x180060f25  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180060f2a  mov     rcx, [rdi]
0x180060f2d  lea     rax, [rcx+1]
0x180060f31  test    rax, 0FFFFFFFFFFFFFFFEh
0x180060f37  jnz     short loc_180060F54
0x180060f39  mov     rcx, [rsp+28h]; this
0x180060f3e  lea     r8, aOnecoreuapNetW_30; "onecoreuap\\net\\wcm\\service\\base\\co"...
0x180060f45  mov     edx, 666h; void *
0x180060f4a  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180060f4f  jmp     loc_180061011
0x180060f54  mov     edx, 1
0x180060f59  call    cs:__imp_RegisterGPNotificationInternal
0x180060f5f  test    eax, eax
0x180060f61  jnz     short loc_180060F88
0x180060f63  mov     rcx, [rsp+28h]; this
0x180060f68  lea     r8, aOnecoreuapNetW_30; "onecoreuap\\net\\wcm\\service\\base\\co"...
0x180060f6f  mov     edx, 66Fh; void *
0x180060f74  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180060f79  xor     edx, edx
0x180060f7b  mov     rcx, rdi
0x180060f7e  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180060f83  jmp     loc_180061011
0x180060f88  xor     r8d, r8d; pcbe
0x180060f8b  xor     edx, edx; pv
0x180060f8d  lea     rcx, ?GroupPolicyChangeCallback@ConfigManager@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x180060f94  call    cs:__imp_CreateThreadpoolWait
0x180060f9a  mov     rdx, rax
0x180060f9d  lea     rcx, [rbx+28h]
0x180060fa1  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WAIT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(_TP_WAIT *)
0x180060fa6  mov     rcx, [rbx+28h]; pwa
0x180060faa  test    rcx, rcx
0x180060fad  jnz     short loc_180060FD0
0x180060faf  mov     rcx, [rsp+28h]; this
0x180060fb4  lea     r8, aOnecoreuapNetW_30; "onecoreuap\\net\\wcm\\service\\base\\co"...
0x180060fbb  mov     edx, 679h; void *
0x180060fc0  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180060fc5  mov     rcx, [rdi]
0x180060fc8  call    cs:__imp_UnregisterGPNotificationInternal
0x180060fce  jmp     short loc_180060F79
0x180060fd0  xor     r8d, r8d; pftTimeout
0x180060fd3  mov     rdx, [rdi]; h
0x180060fd6  call    cs:__imp_SetThreadpoolWait
0x180060fdc  lea     rax, WPP_GLOBAL_Control
0x180060fe3  mov     rcx, cs:WPP_GLOBAL_Control
0x180060fea  cmp     rcx, rax
0x180060fed  jz      short loc_180061011
0x180060fef  cmp     byte ptr [rcx+19h], 4
0x180060ff3  jb      short loc_180061011
0x180060ff5  test    byte ptr [rcx+1Ch], 1
0x180060ff9  jz      short loc_180061011
0x180060ffb  mov     edx, 40h ; '@'
0x180061000  lea     r8, WPP_d1926522bc273c8e7056db3405527a30_Traceguids
0x180061007  mov     rcx, [rcx+10h]
0x18006100b  call    WPP_SF_
0x180061010  nop
0x180061011  mov     rbx, [rsp+28h+arg_8]
0x180061016  add     rsp, 20h
0x18006101a  pop     rdi
0x18006101b  retn
```
