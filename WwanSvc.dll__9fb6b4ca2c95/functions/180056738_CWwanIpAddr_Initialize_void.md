# CWwanIpAddr::Initialize(void)

- ea: `0x180056738`
- end: `0x180056831`
- name: `?Initialize@CWwanIpAddr@@AEAAKXZ`
- size: `249`
- prototype: `unsigned int __fastcall(CWwanIpAddr *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180056d5c`

## callees

- `0x180012300`
- `0x180014f1c`
- `0x180056738`
- `0x1800568b8`
- `0x1800c5d28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800567f7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800567f7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180056807`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180056807`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800567c3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800567c3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800567a8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800567a8`

## string_xrefs

- `0x1800567d2`: `Failed to CreateThreadpoolWait %d`

## pseudocode

```c
__int64 __fastcall CWwanIpAddr::Initialize(CWwanIpAddr *this)
{
  unsigned int v2; // ebx
  __int64 i; // rbx
  struct _TP_WAIT *ThreadpoolWait; // rax

  WwanLog::Info("CWwanIpAddr::Initialize", 0, L" Initializing CWwanIpAddr");
  if ( *(_DWORD *)this )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( (unsigned int)CWwanIpAddr::IpAddr_Initialize(this) )
  {
    v2 = 5023;
    WwanLog::Error("CWwanIpAddr::Initialize", 0, L"Failed to initialize CWwanIpAddr");
    MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  else
  {
    for ( i = 0; (unsigned int)i < 2; i = (unsigned int)(i + 1) )
    {
      ThreadpoolWait = CreateThreadpoolWait(CWwanIpAddr::_WaitCallbackForEventsStatic, this, 0);
      *((_QWORD *)this + i + 13) = ThreadpoolWait;
      if ( !ThreadpoolWait )
      {
        WwanLog::Error(
          "CWwanIpAddr::Initialize",
          0,
          L"Failed to CreateThreadpoolWait %d",
          *((unsigned int *)this + i + 12));
        v2 = 5023;
        MicrosoftTelemetryAssertTriggeredNoArgs();
        return v2;
      }
      SetThreadpoolWait(ThreadpoolWait, *((HANDLE *)this + i + 9), 0);
    }
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    *(_DWORD *)this = 1;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    v2 = 0;
    WwanLog::Info("CWwanIpAddr::Initialize", 0, L" Successfully IpAddrController Initialize");
  }
  return v2;
}

```

## disassembly

```asm
0x180056738  mov     [rsp+arg_0], rbx
0x18005673d  push    rdi
0x18005673e  sub     rsp, 20h
0x180056742  mov     rdi, rcx
0x180056745  lea     r8, aInitializingCw; " Initializing CWwanIpAddr"
0x18005674c  lea     rcx, aCwwanipaddrIni; "CWwanIpAddr::Initialize"
0x180056753  xor     edx, edx; struct _GUID *
0x180056755  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18005675a  cmp     dword ptr [rdi], 0
0x18005675d  jz      short loc_180056764
0x18005675f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180056764  mov     rcx, rdi; this
0x180056767  call    ?IpAddr_Initialize@CWwanIpAddr@@AEAAJXZ; CWwanIpAddr::IpAddr_Initialize(void)
0x18005676c  test    eax, eax
0x18005676e  jz      short loc_180056794
0x180056770  lea     r8, aFailedToInitia_0; "Failed to initialize CWwanIpAddr"
0x180056777  xor     edx, edx; struct _GUID *
0x180056779  lea     rcx, aCwwanipaddrIni; "CWwanIpAddr::Initialize"
0x180056780  mov     ebx, 139Fh
0x180056785  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18005678a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18005678f  jmp     loc_180056824
0x180056794  xor     ebx, ebx
0x180056796  cmp     ebx, 2
0x180056799  jnb     short loc_1800567F3
0x18005679b  xor     r8d, r8d; pcbe
0x18005679e  lea     rcx, ?_WaitCallbackForEventsStatic@CWwanIpAddr@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x1800567a5  mov     rdx, rdi; pv
0x1800567a8  call    cs:__imp_CreateThreadpoolWait
0x1800567ae  mov     [rdi+rbx*8+68h], rax
0x1800567b3  test    rax, rax
0x1800567b6  jz      short loc_1800567CD
0x1800567b8  mov     rdx, [rdi+rbx*8+48h]; h
0x1800567bd  xor     r8d, r8d; pftTimeout
0x1800567c0  mov     rcx, rax; pwa
0x1800567c3  call    cs:__imp_SetThreadpoolWait
0x1800567c9  inc     ebx
0x1800567cb  jmp     short loc_180056796
0x1800567cd  mov     r9d, [rdi+rbx*4+30h]
0x1800567d2  lea     r8, aFailedToCreate_15; "Failed to CreateThreadpoolWait %d"
0x1800567d9  xor     edx, edx; struct _GUID *
0x1800567db  lea     rcx, aCwwanipaddrIni; "CWwanIpAddr::Initialize"
0x1800567e2  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800567e7  mov     ebx, 139Fh
0x1800567ec  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800567f1  jmp     short loc_180056824
0x1800567f3  lea     rcx, [rdi+8]; lpCriticalSection
0x1800567f7  call    cs:__imp_EnterCriticalSection
0x1800567fd  lea     rcx, [rdi+8]; lpCriticalSection
0x180056801  mov     dword ptr [rdi], 1
0x180056807  call    cs:__imp_LeaveCriticalSection
0x18005680d  lea     r8, aSuccessfullyIp; " Successfully IpAddrController Initiali"...
0x180056814  xor     edx, edx; struct _GUID *
0x180056816  lea     rcx, aCwwanipaddrIni; "CWwanIpAddr::Initialize"
0x18005681d  xor     ebx, ebx
0x18005681f  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x180056824  mov     eax, ebx
0x180056826  mov     rbx, [rsp+28h+arg_0]
0x18005682b  add     rsp, 20h
0x18005682f  pop     rdi
0x180056830  retn
```
