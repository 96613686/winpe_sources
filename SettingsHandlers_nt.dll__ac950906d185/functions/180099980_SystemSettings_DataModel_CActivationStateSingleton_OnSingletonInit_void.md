# SystemSettings::DataModel::CActivationStateSingleton::OnSingletonInit(void)

- ea: `0x180099980`
- end: `0x180099d51`
- name: `?OnSingletonInit@CActivationStateSingleton@DataModel@SystemSettings@@MEAAJXZ`
- size: `977`
- prototype: `__int64 __fastcall(SystemSettings::DataModel::CActivationStateSingleton *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001a50`
- `0x18000d44c`
- `0x18001098c`
- `0x18001c9c8`
- `0x180021328`
- `0x1800939dc`
- `0x180099980`
- `0x180249e44`

## import_xrefs

- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x180099ade`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x180099b98`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x180099c52`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x180099ade`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x180099b98`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x180099c52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099a9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099aee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099b54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099ba8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099c0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099c62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099a9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099aee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099b54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099ba8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099c0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099c62`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180099a7c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180099b3c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180099bf6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180099a7c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180099b3c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180099bf6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180099998`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180099998`
- `ntdll!NtQueryWnfStateData` at `0x180099cd4`
- `ntdll!NtQueryWnfStateData` at `0x180099cd4`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180099d17`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180099d17`
- `SLC!SLRegisterWindowsEvent` at `0x180099b1c`
- `SLC!SLRegisterWindowsEvent` at `0x180099bd6`
- `SLC!SLRegisterWindowsEvent` at `0x180099c90`
- `SLC!SLRegisterWindowsEvent` at `0x180099b1c`
- `SLC!SLRegisterWindowsEvent` at `0x180099bd6`
- `SLC!SLRegisterWindowsEvent` at `0x180099c90`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::DataModel::CActivationStateSingleton::OnSingletonInit(
        SystemSettings::DataModel::CActivationStateSingleton *this)
{
  __int64 v2; // rdx
  char *v3; // rax
  char *v4; // rbx
  int v5; // ebx
  unsigned int v6; // edx
  int v7; // ecx
  HANDLE EventW; // rax
  signed int LastError; // eax
  signed int v10; // eax
  int v11; // eax
  HANDLE v12; // rax
  signed int v13; // eax
  signed int v14; // eax
  HANDLE v15; // rax
  signed int v16; // eax
  signed int v17; // eax
  int v18; // eax
  int v20; // [rsp+70h] [rbp+8h] BYREF
  unsigned int v21; // [rsp+78h] [rbp+10h] BYREF
  struct _RTL_CRITICAL_SECTION *v22; // [rsp+80h] [rbp+18h] BYREF
  char *v23; // [rsp+88h] [rbp+20h]

  EnterCriticalSection(&SystemSettings::DataModel::g_licensingDataLock);
  v22 = &SystemSettings::DataModel::g_licensingDataLock;
  *((_BYTE *)this + 2048) = 1;
  *((_BYTE *)this + 2049) = 1;
  v21 = 0;
  v20 = 0;
  McGenEventRegister_EventRegister(
    Microsoft_Windows_Security_SPP_UX_GenuineCenter,
    v2,
    Microsoft_Windows_Security_SPP_UX_GenuineCenter_Context,
    Microsoft_Windows_Security_SPP_UX_GenuineCenter_Context);
  TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_18038EAD0);
  TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_18038E1C0);
  v3 = (char *)operator new(0x650u, (const struct std::nothrow_t *)&std::nothrow);
  v4 = v3;
  v23 = v3;
  if ( v3 )
  {
    memset_0(v3, 0, 0x650u);
    memset_0(v4 + 8, 0, 0x648u);
  }
  else
  {
    v4 = 0;
  }
  *((_QWORD *)this + 29) = v4;
  if ( !v4 )
  {
    v5 = -2147024882;
    v6 = 7218;
    v7 = -2147024882;
LABEL_35:
    CProviderUtils::LogError(v7, v6);
    goto LABEL_38;
  }
  *((_BYTE *)this + 1960) = 0;
  v5 = SystemSettings::DataModel::CActivationStateSingleton::DetermineInitialState((SystemSettings::DataModel::CActivationStateSingleton *)((char *)this - 40));
  if ( v5 >= 0 )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)this + 233) = EventW;
    if ( EventW )
      goto LABEL_43;
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( v5 >= 0 )
    {
LABEL_43:
      if ( RegisterWaitForSingleObject(
             (PHANDLE)this + 234,
             *((HANDLE *)this + 233),
             SystemSettings::DataModel::CActivationStateSingleton::s_MonitorLastActivationErrorChangeCallBack,
             (char *)this - 40,
             0xFFFFFFFF,
             0) )
      {
        goto LABEL_15;
      }
      v10 = GetLastError();
      v5 = v10;
      if ( v10 > 0 )
        v5 = (unsigned __int16)v10 | 0x80070000;
      if ( v5 >= 0 )
      {
LABEL_15:
        v11 = SLRegisterWindowsEvent(L"msft:rm/event/licensingstatechanged", *((_QWORD *)this + 233));
        v5 = v11;
        if ( v11 < 0 )
          goto LABEL_34;
        v12 = CreateEventW(0, 0, 0, 0);
        *((_QWORD *)this + 235) = v12;
        if ( !v12 )
        {
          v13 = GetLastError();
          v5 = v13;
          if ( v13 > 0 )
            v5 = (unsigned __int16)v13 | 0x80070000;
          if ( v5 < 0 )
            goto LABEL_38;
        }
        if ( !RegisterWaitForSingleObject(
                (PHANDLE)this + 236,
                *((HANDLE *)this + 235),
                SystemSettings::DataModel::CActivationStateSingleton::s_MonitorLastActivationErrorChangeCallBack,
                (char *)this - 40,
                0xFFFFFFFF,
                0) )
        {
          v14 = GetLastError();
          v5 = v14;
          if ( v14 > 0 )
            v5 = (unsigned __int16)v14 | 0x80070000;
          if ( v5 < 0 )
            goto LABEL_38;
        }
        v11 = SLRegisterWindowsEvent(L"msft:rm/event/lastactivationresultchanged", *((_QWORD *)this + 235));
        v5 = v11;
        if ( v11 < 0 )
        {
LABEL_34:
          v6 = 7214;
          v7 = v11;
          goto LABEL_35;
        }
        v15 = CreateEventW(0, 0, 0, 0);
        *((_QWORD *)this + 237) = v15;
        if ( v15 )
          goto LABEL_32;
        v16 = GetLastError();
        v5 = v16;
        if ( v16 > 0 )
          v5 = (unsigned __int16)v16 | 0x80070000;
        if ( v5 >= 0 )
        {
LABEL_32:
          if ( RegisterWaitForSingleObject(
                 (PHANDLE)this + 238,
                 *((HANDLE *)this + 237),
                 SystemSettings::DataModel::CActivationStateSingleton::s_MonitorLastActivationErrorChangeCallBack,
                 (char *)this - 40,
                 0xFFFFFFFF,
                 0) )
          {
            goto LABEL_33;
          }
          v17 = GetLastError();
          v5 = v17;
          if ( v17 > 0 )
            v5 = (unsigned __int16)v17 | 0x80070000;
          if ( v5 >= 0 )
          {
LABEL_33:
            v11 = SLRegisterWindowsEvent(L"msft:rm/event/policychanged", *((_QWORD *)this + 237));
            v5 = v11;
            if ( v11 < 0 )
              goto LABEL_34;
            v20 = 0;
            v18 = NtQueryWnfStateData(&WNF_CI_SMODE_CHANGE, 0, 0, &v21, 0, &v20);
            v5 = v18 | 0x10000000;
            if ( v18 >= 0 )
              v5 = RtlSubscribeWnfStateChangeNotification(
                     (char *)this + 2064,
                     WNF_CI_SMODE_CHANGE,
                     v21,
                     SystemSettings::DataModel::CActivationStateSingleton::SModeChangeCallback,
                     0,
                     0,
                     0,
                     0)
                 | 0x10000000;
          }
        }
      }
    }
  }
LABEL_38:
  if ( *((_DWORD *)this + 456) )
    *((_WORD *)this + 1024) = 0;
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v22);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180099980  push    rbx
0x180099982  push    rbp
0x180099983  push    rsi
0x180099984  push    rdi
0x180099985  push    r14
0x180099987  sub     rsp, 40h
0x18009998b  mov     rdi, rcx
0x18009998e  lea     rbx, ?g_licensingDataLock@DataModel@SystemSettings@@3VCriticalSection@Wrappers@WRL@Microsoft@@A; Microsoft::WRL::Wrappers::CriticalSection SystemSettings::DataModel::g_licensingDataLock
0x180099995  mov     rcx, rbx; lpCriticalSection
0x180099998  call    cs:__imp_EnterCriticalSection
0x18009999f  nop     dword ptr [rax+rax+00h]
0x1800999a4  mov     [rsp+68h+arg_10], rbx
0x1800999ac  lea     rsi, [rdi-28h]
0x1800999b0  mov     byte ptr [rsi+828h], 1
0x1800999b7  mov     byte ptr [rdi+801h], 1
0x1800999be  xor     ebp, ebp
0x1800999c0  mov     [rsp+68h+arg_8], ebp
0x1800999c4  mov     [rsp+68h+arg_0], ebp
0x1800999c8  lea     r8, Microsoft_Windows_Security_SPP_UX_GenuineCenter_Context
0x1800999cf  mov     r9, r8
0x1800999d2  lea     rcx, Microsoft_Windows_Security_SPP_UX_GenuineCenter
0x1800999d9  call    McGenEventRegister_EventRegister
0x1800999de  lea     rcx, dword_18038EAD0; CallbackContext
0x1800999e5  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x1800999ea  lea     rcx, dword_18038E1C0; CallbackContext
0x1800999f1  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x1800999f6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800999fd  mov     r14d, 650h
0x180099a03  mov     ecx, r14d; unsigned __int64
0x180099a06  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180099a0b  mov     rbx, rax
0x180099a0e  mov     [rsp+68h+arg_18], rax
0x180099a16  test    rax, rax
0x180099a19  jz      short loc_180099A39
0x180099a1b  mov     r8d, r14d; Size
0x180099a1e  xor     edx, edx; Val
0x180099a20  mov     rcx, rax; void *
0x180099a23  call    memset_0
0x180099a28  lea     rcx, [rbx+8]; void *
0x180099a2c  xor     edx, edx; Val
0x180099a2e  lea     r8d, [r14-8]; Size
0x180099a32  call    memset_0
0x180099a37  jmp     short loc_180099A3C
0x180099a39  mov     rbx, rbp
0x180099a3c  mov     [rdi+0E8h], rbx
0x180099a43  test    rbx, rbx
0x180099a46  jnz     short loc_180099A59
0x180099a48  mov     ebx, 8007000Eh
0x180099a4d  mov     edx, 1C32h
0x180099a52  mov     ecx, ebx
0x180099a54  jmp     loc_180099CA9
0x180099a59  mov     [rdi+7A8h], bpl
0x180099a60  mov     rcx, rsi; this
0x180099a63  call    ?DetermineInitialState@CActivationStateSingleton@DataModel@SystemSettings@@QEAAJXZ; SystemSettings::DataModel::CActivationStateSingleton::DetermineInitialState(void)
0x180099a68  mov     ebx, eax
0x180099a6a  test    eax, eax
0x180099a6c  js      loc_180099D27
0x180099a72  xor     r9d, r9d; lpName
0x180099a75  xor     r8d, r8d; bInitialState
0x180099a78  xor     edx, edx; bManualReset
0x180099a7a  xor     ecx, ecx; lpEventAttributes
0x180099a7c  call    cs:__imp_CreateEventW
0x180099a83  nop     dword ptr [rax+rax+00h]
0x180099a88  mov     [rdi+748h], rax
0x180099a8f  mov     r14d, 80070000h
0x180099a95  test    rax, rax
0x180099a98  jnz     short loc_180099ABA
0x180099a9a  call    cs:__imp_GetLastError
0x180099aa1  nop     dword ptr [rax+rax+00h]
0x180099aa6  mov     ebx, eax
0x180099aa8  test    eax, eax
0x180099aaa  jle     short loc_180099AB2
0x180099aac  movzx   ebx, ax
0x180099aaf  or      ebx, r14d
0x180099ab2  test    ebx, ebx
0x180099ab4  js      loc_180099D27
0x180099aba  lea     rcx, [rdi+750h]; phNewWaitObject
0x180099ac1  mov     [rsp+68h+dwFlags], ebp; dwFlags
0x180099ac5  mov     [rsp+68h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x180099acd  mov     r9, rsi; Context
0x180099ad0  lea     r8, ?s_MonitorLastActivationErrorChangeCallBack@CActivationStateSingleton@DataModel@SystemSettings@@SAXPEAXE@Z; Callback
0x180099ad7  mov     rdx, [rdi+748h]; hObject
0x180099ade  call    cs:__imp_RegisterWaitForSingleObject
0x180099ae5  nop     dword ptr [rax+rax+00h]
0x180099aea  test    eax, eax
0x180099aec  jnz     short loc_180099B0E
0x180099aee  call    cs:__imp_GetLastError
0x180099af5  nop     dword ptr [rax+rax+00h]
0x180099afa  mov     ebx, eax
0x180099afc  test    eax, eax
0x180099afe  jle     short loc_180099B06
0x180099b00  movzx   ebx, ax
0x180099b03  or      ebx, r14d
0x180099b06  test    ebx, ebx
0x180099b08  js      loc_180099D27
0x180099b0e  mov     rdx, [rdi+748h]
0x180099b15  lea     rcx, aMsftRmEventLic; "msft:rm/event/licensingstatechanged"
0x180099b1c  call    cs:__imp_SLRegisterWindowsEvent
0x180099b23  nop     dword ptr [rax+rax+00h]
0x180099b28  mov     ebx, eax
0x180099b2a  test    eax, eax
0x180099b2c  js      loc_180099CA2
0x180099b32  xor     r9d, r9d; lpName
0x180099b35  xor     r8d, r8d; bInitialState
0x180099b38  xor     edx, edx; bManualReset
0x180099b3a  xor     ecx, ecx; lpEventAttributes
0x180099b3c  call    cs:__imp_CreateEventW
0x180099b43  nop     dword ptr [rax+rax+00h]
0x180099b48  mov     [rdi+758h], rax
0x180099b4f  test    rax, rax
0x180099b52  jnz     short loc_180099B74
0x180099b54  call    cs:__imp_GetLastError
0x180099b5b  nop     dword ptr [rax+rax+00h]
0x180099b60  mov     ebx, eax
0x180099b62  test    eax, eax
0x180099b64  jle     short loc_180099B6C
0x180099b66  movzx   ebx, ax
0x180099b69  or      ebx, r14d
0x180099b6c  test    ebx, ebx
0x180099b6e  js      loc_180099D27
0x180099b74  lea     rcx, [rdi+760h]; phNewWaitObject
0x180099b7b  mov     [rsp+68h+dwFlags], ebp; dwFlags
0x180099b7f  mov     [rsp+68h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x180099b87  mov     r9, rsi; Context
0x180099b8a  lea     r8, ?s_MonitorLastActivationErrorChangeCallBack@CActivationStateSingleton@DataModel@SystemSettings@@SAXPEAXE@Z; Callback
0x180099b91  mov     rdx, [rdi+758h]; hObject
0x180099b98  call    cs:__imp_RegisterWaitForSingleObject
0x180099b9f  nop     dword ptr [rax+rax+00h]
0x180099ba4  test    eax, eax
0x180099ba6  jnz     short loc_180099BC8
0x180099ba8  call    cs:__imp_GetLastError
0x180099baf  nop     dword ptr [rax+rax+00h]
0x180099bb4  mov     ebx, eax
0x180099bb6  test    eax, eax
0x180099bb8  jle     short loc_180099BC0
0x180099bba  movzx   ebx, ax
0x180099bbd  or      ebx, r14d
0x180099bc0  test    ebx, ebx
0x180099bc2  js      loc_180099D27
0x180099bc8  mov     rdx, [rdi+758h]
0x180099bcf  lea     rcx, aMsftRmEventLas; "msft:rm/event/lastactivationresultchang"...
0x180099bd6  call    cs:__imp_SLRegisterWindowsEvent
0x180099bdd  nop     dword ptr [rax+rax+00h]
0x180099be2  mov     ebx, eax
0x180099be4  test    eax, eax
0x180099be6  js      loc_180099CA2
0x180099bec  xor     r9d, r9d; lpName
0x180099bef  xor     r8d, r8d; bInitialState
0x180099bf2  xor     edx, edx; bManualReset
0x180099bf4  xor     ecx, ecx; lpEventAttributes
0x180099bf6  call    cs:__imp_CreateEventW
0x180099bfd  nop     dword ptr [rax+rax+00h]
0x180099c02  mov     [rdi+768h], rax
0x180099c09  test    rax, rax
0x180099c0c  jnz     short loc_180099C2E
0x180099c0e  call    cs:__imp_GetLastError
0x180099c15  nop     dword ptr [rax+rax+00h]
0x180099c1a  mov     ebx, eax
0x180099c1c  test    eax, eax
0x180099c1e  jle     short loc_180099C26
0x180099c20  movzx   ebx, ax
0x180099c23  or      ebx, r14d
0x180099c26  test    ebx, ebx
0x180099c28  js      loc_180099D27
0x180099c2e  lea     rcx, [rdi+770h]; phNewWaitObject
0x180099c35  mov     [rsp+68h+dwFlags], ebp; dwFlags
0x180099c39  mov     [rsp+68h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x180099c41  mov     r9, rsi; Context
0x180099c44  lea     r8, ?s_MonitorLastActivationErrorChangeCallBack@CActivationStateSingleton@DataModel@SystemSettings@@SAXPEAXE@Z; Callback
0x180099c4b  mov     rdx, [rdi+768h]; hObject
0x180099c52  call    cs:__imp_RegisterWaitForSingleObject
0x180099c59  nop     dword ptr [rax+rax+00h]
0x180099c5e  test    eax, eax
0x180099c60  jnz     short loc_180099C82
0x180099c62  call    cs:__imp_GetLastError
0x180099c69  nop     dword ptr [rax+rax+00h]
0x180099c6e  mov     ebx, eax
0x180099c70  test    eax, eax
0x180099c72  jle     short loc_180099C7A
0x180099c74  movzx   ebx, ax
0x180099c77  or      ebx, r14d
0x180099c7a  test    ebx, ebx
0x180099c7c  js      loc_180099D27
0x180099c82  mov     rdx, [rdi+768h]
0x180099c89  lea     rcx, aMsftRmEventPol; "msft:rm/event/policychanged"
0x180099c90  call    cs:__imp_SLRegisterWindowsEvent
0x180099c97  nop     dword ptr [rax+rax+00h]
0x180099c9c  mov     ebx, eax
0x180099c9e  test    eax, eax
0x180099ca0  jns     short loc_180099CB0
0x180099ca2  mov     edx, 1C2Eh; unsigned int
0x180099ca7  mov     ecx, eax; int
0x180099ca9  call    ?LogError@CProviderUtils@@SAXJI@Z; CProviderUtils::LogError(long,uint)
0x180099cae  jmp     short loc_180099D27
0x180099cb0  mov     [rsp+68h+arg_0], ebp
0x180099cb4  lea     rax, [rsp+68h+arg_0]
0x180099cb9  mov     qword ptr [rsp+68h+dwFlags], rax
0x180099cbe  mov     qword ptr [rsp+68h+dwMilliseconds], rbp
0x180099cc3  lea     r9, [rsp+68h+arg_8]
0x180099cc8  xor     r8d, r8d
0x180099ccb  xor     edx, edx
0x180099ccd  lea     rcx, WNF_CI_SMODE_CHANGE
0x180099cd4  call    cs:__imp_NtQueryWnfStateData
0x180099cdb  nop     dword ptr [rax+rax+00h]
0x180099ce0  mov     ebx, eax
0x180099ce2  mov     esi, 10000000h
0x180099ce7  or      ebx, esi
0x180099ce9  jl      short loc_180099D27
0x180099ceb  lea     rcx, [rdi+810h]
0x180099cf2  mov     [rsp+68h+var_30], ebp
0x180099cf6  mov     [rsp+68h+var_38], ebp
0x180099cfa  mov     qword ptr [rsp+68h+dwFlags], rbp
0x180099cff  mov     qword ptr [rsp+68h+dwMilliseconds], rbp
0x180099d04  lea     r9, ?SModeChangeCallback@CActivationStateSingleton@DataModel@SystemSettings@@SAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; SystemSettings::DataModel::CActivationStateSingleton::SModeChangeCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x180099d0b  mov     r8d, [rsp+68h+arg_8]
0x180099d10  mov     rdx, cs:WNF_CI_SMODE_CHANGE
0x180099d17  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x180099d1e  nop     dword ptr [rax+rax+00h]
0x180099d23  mov     ebx, eax
0x180099d25  or      ebx, esi
0x180099d27  cmp     [rdi+720h], ebp
0x180099d2d  jz      short loc_180099D36
0x180099d2f  mov     [rdi+800h], bp
0x180099d36  lea     rcx, [rsp+68h+arg_10]; this
0x180099d3e  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x180099d43  mov     eax, ebx
0x180099d45  add     rsp, 40h
0x180099d49  pop     r14
0x180099d4b  pop     rdi
0x180099d4c  pop     rsi
0x180099d4d  pop     rbp
0x180099d4e  pop     rbx
0x180099d4f  retn
```
