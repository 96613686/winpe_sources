# CComDllModule::Init(ATL::_ATL_OBJMAP_ENTRY *,HINSTANCE__ *,_GUID const *)

- ea: `0x1800569a0`
- end: `0x180056c38`
- name: `?Init@CComDllModule@@QEAAJPEAU_ATL_OBJMAP_ENTRY@ATL@@PEAUHINSTANCE__@@PEBU_GUID@@@Z`
- size: `664`
- prototype: `__int64 __fastcall(CComDllModule *__hidden this, struct ATL::_ATL_OBJMAP_ENTRY *, HINSTANCE, const struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18002a46c`

## callees

- `0x180010350`
- `0x180044ab0`
- `0x18004d794`
- `0x1800569a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x180056ae9`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x180056ae9`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180056b60`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180056b7d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180056b60`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180056b7d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180056b34`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180056b4b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180056bca`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180056b34`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180056b4b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180056bca`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180056a31`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180056a48`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180056a5f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180056aa0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180056ab7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180056ace`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180056a31`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180056a48`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180056a5f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180056aa0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180056ab7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180056ace`
- `api-ms-win-core-errorhandling-l1-1-1!AddVectoredExceptionHandler` at `0x180056c12`
- `api-ms-win-core-errorhandling-l1-1-1!AddVectoredExceptionHandler` at `0x180056c12`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CComDllModule::Init(
        CComDllModule *this,
        struct ATL::_ATL_OBJMAP_ENTRY *a2,
        HINSTANCE a3,
        const struct _GUID *a4)
{
  int v4; // edi
  HANDLE EventW; // rax
  HANDLE WaitableTimer; // rax
  char *v7; // rax
  CRealTimePenService *v8; // rbx
  const struct _GUID *pExceptionObject; // [rsp+48h] [rbp+20h] BYREF

  pExceptionObject = a4;
  qword_18016D1E8 = (__int64)&ATL::GUID_ATLVer30;
  ATL::_pModule = (struct ATL::CComModule *)&_Module;
  _Module = 248;
  dword_18016D1D0 = 769;
  v4 = ATL::AtlModuleInit(this, a2, a3);
  if ( v4 < 0 )
    return (unsigned int)v4;
  ATL::CComModule::m_libid = LIBID_MSINKAUTLib;
  dword_18016D210 = 1;
  _InterlockedExchange(&g_lClassicWEnabled, 0);
  dword_18016D268 = 0;
  hObject = 0;
  qword_18016D228 = CreateEventW(0, 0, 0, 0);
  qword_18016D230 = CreateEventW(0, 0, 0, 0);
  EventW = CreateEventW(0, 0, 0, 0);
  qword_18016D238 = EventW;
  if ( qword_18016D228 )
  {
    if ( qword_18016D230 )
    {
      if ( EventW )
      {
        hThread = 0;
        hEvent = CreateEventW(0, 0, 0, 0);
        qword_18016D250 = CreateEventW(0, 0, 0, 0);
        qword_18016D258 = CreateEventW(0, 0, 0, 0);
        WaitableTimer = CreateWaitableTimerExW(0, 0, 1u, 0x1F0003u);
        hTimer = WaitableTimer;
        if ( hEvent )
        {
          if ( qword_18016D250 )
          {
            if ( qword_18016D258 )
            {
              if ( WaitableTimer )
              {
                if ( InitializeCriticalSectionAndSpinCount(&g_csTabletManager, 0x8001FA0u) )
                {
                  if ( InitializeCriticalSectionAndSpinCount(&g_csModule, 0x8001FA0u) )
                  {
                    pHandles = CreateMutexW(0, 0, 0);
                    if ( pHandles )
                    {
                      hMutex = CreateMutexW(0, 0, 0);
                      if ( hMutex )
                      {
                        qword_18016D280 = 0;
                        rc2 = 0;
                        v7 = (char *)WinMalloc(0x40u);
                        v8 = (CRealTimePenService *)v7;
                        if ( v7 )
                        {
                          *(_QWORD *)v7 = 0;
                          *((_QWORD *)v7 + 1) = 0;
                          *((_QWORD *)v7 + 2) = 0;
                          if ( !InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)(v7 + 24), 0x8001FA0u) )
                          {
                            LODWORD(pExceptionObject) = -2147024882;
                            throw (long *)&pExceptionObject;
                          }
                        }
                        else
                        {
                          v8 = 0;
                        }
                        qword_18016D218 = v8;
                        v4 = 0;
                        if ( !v8 )
                          v4 = -2147024882;
                        g_watsonExceptionHandler = AddVectoredExceptionHandler(0, WatsonExceptionHandler);
                        return (unsigned int)v4;
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
  return 2147500037LL;
}

```

## disassembly

```asm
0x1800569a0  mov     rax, rsp
0x1800569a3  mov     [rax+8], rbx
0x1800569a7  mov     [rax+18h], rsi
0x1800569ab  mov     [rax+20h], r9
0x1800569af  mov     [rax+10h], rdx
0x1800569b3  push    rdi
0x1800569b4  sub     rsp, 20h
0x1800569b8  lea     rax, ?GUID_ATLVer30@ATL@@3U_GUID@@A; _GUID ATL::GUID_ATLVer30
0x1800569bf  mov     cs:qword_18016D1E8, rax
0x1800569c6  lea     rax, ?_Module@@3VCComDllModule@@A; CComDllModule _Module
0x1800569cd  mov     cs:?_pModule@ATL@@3PEAVCComModule@1@EA, rax; ATL::CComModule * ATL::_pModule
0x1800569d4  mov     cs:?_Module@@3VCComDllModule@@A, 0F8h; CComDllModule _Module
0x1800569de  mov     cs:dword_18016D1D0, 301h
0x1800569e8  call    ?AtlModuleInit@ATL@@YAJPEAU_ATL_MODULE@1@PEAU_ATL_OBJMAP_ENTRY@1@PEAUHINSTANCE__@@@Z; ATL::AtlModuleInit(ATL::_ATL_MODULE *,ATL::_ATL_OBJMAP_ENTRY *,HINSTANCE__ *)
0x1800569ed  mov     edi, eax
0x1800569ef  xor     esi, esi
0x1800569f1  test    eax, eax
0x1800569f3  js      loc_180056C1F
0x1800569f9  movups  xmm0, xmmword ptr cs:LIBID_MSINKAUTLib.Data1
0x180056a00  movdqu  xmmword ptr cs:?m_libid@CComModule@ATL@@2U_GUID@@A.Data1, xmm0; _GUID ATL::CComModule::m_libid ...
0x180056a08  mov     cs:dword_18016D210, 1
0x180056a12  mov     eax, esi
0x180056a14  xchg    eax, cs:?g_lClassicWEnabled@@3JC; long volatile g_lClassicWEnabled
0x180056a1a  mov     cs:dword_18016D268, esi
0x180056a20  mov     cs:hObject, rsi
0x180056a27  xor     r9d, r9d; lpName
0x180056a2a  xor     r8d, r8d; bInitialState
0x180056a2d  xor     edx, edx; bManualReset
0x180056a2f  xor     ecx, ecx; lpEventAttributes
0x180056a31  call    cs:__imp_CreateEventW
0x180056a37  mov     cs:qword_18016D228, rax
0x180056a3e  xor     r9d, r9d; lpName
0x180056a41  xor     r8d, r8d; bInitialState
0x180056a44  xor     edx, edx; bManualReset
0x180056a46  xor     ecx, ecx; lpEventAttributes
0x180056a48  call    cs:__imp_CreateEventW
0x180056a4e  mov     cs:qword_18016D230, rax
0x180056a55  xor     r9d, r9d; lpName
0x180056a58  xor     r8d, r8d; bInitialState
0x180056a5b  xor     edx, edx; bManualReset
0x180056a5d  xor     ecx, ecx; lpEventAttributes
0x180056a5f  call    cs:__imp_CreateEventW
0x180056a65  mov     cs:qword_18016D238, rax
0x180056a6c  cmp     cs:qword_18016D228, rsi
0x180056a73  jz      loc_180056C23
0x180056a79  cmp     cs:qword_18016D230, rsi
0x180056a80  jz      loc_180056C23
0x180056a86  test    rax, rax
0x180056a89  jz      loc_180056C23
0x180056a8f  mov     cs:hThread, rsi
0x180056a96  xor     r9d, r9d; lpName
0x180056a99  xor     r8d, r8d; bInitialState
0x180056a9c  xor     edx, edx; bManualReset
0x180056a9e  xor     ecx, ecx; lpEventAttributes
0x180056aa0  call    cs:__imp_CreateEventW
0x180056aa6  mov     cs:hEvent, rax
0x180056aad  xor     r9d, r9d; lpName
0x180056ab0  xor     r8d, r8d; bInitialState
0x180056ab3  xor     edx, edx; bManualReset
0x180056ab5  xor     ecx, ecx; lpEventAttributes
0x180056ab7  call    cs:__imp_CreateEventW
0x180056abd  mov     cs:qword_18016D250, rax
0x180056ac4  xor     r9d, r9d; lpName
0x180056ac7  xor     r8d, r8d; bInitialState
0x180056aca  xor     edx, edx; bManualReset
0x180056acc  xor     ecx, ecx; lpEventAttributes
0x180056ace  call    cs:__imp_CreateEventW
0x180056ad4  mov     cs:qword_18016D258, rax
0x180056adb  xor     edx, edx; lpTimerName
0x180056add  xor     ecx, ecx; lpTimerAttributes
0x180056adf  mov     r9d, 1F0003h; dwDesiredAccess
0x180056ae5  lea     r8d, [rsi+1]; dwFlags
0x180056ae9  call    cs:__imp_CreateWaitableTimerExW
0x180056aef  mov     cs:hTimer, rax
0x180056af6  cmp     cs:hEvent, rsi
0x180056afd  jz      loc_180056C23
0x180056b03  cmp     cs:qword_18016D250, rsi
0x180056b0a  jz      loc_180056C23
0x180056b10  cmp     cs:qword_18016D258, rsi
0x180056b17  jz      loc_180056C23
0x180056b1d  test    rax, rax
0x180056b20  jz      loc_180056C23
0x180056b26  mov     edi, 8001FA0h
0x180056b2b  mov     edx, edi; dwSpinCount
0x180056b2d  lea     rcx, ?g_csTabletManager@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180056b34  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180056b3a  test    eax, eax
0x180056b3c  jz      loc_180056C23
0x180056b42  mov     edx, edi; dwSpinCount
0x180056b44  lea     rcx, ?g_csModule@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180056b4b  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180056b51  test    eax, eax
0x180056b53  jz      loc_180056C23
0x180056b59  xor     r8d, r8d; lpName
0x180056b5c  xor     edx, edx; bInitialOwner
0x180056b5e  xor     ecx, ecx; lpMutexAttributes
0x180056b60  call    cs:__imp_CreateMutexW
0x180056b66  mov     cs:pHandles, rax
0x180056b6d  test    rax, rax
0x180056b70  jz      loc_180056C23
0x180056b76  xor     r8d, r8d; lpName
0x180056b79  xor     edx, edx; bInitialOwner
0x180056b7b  xor     ecx, ecx; lpMutexAttributes
0x180056b7d  call    cs:__imp_CreateMutexW
0x180056b83  mov     cs:hMutex, rax
0x180056b8a  test    rax, rax
0x180056b8d  jz      loc_180056C23
0x180056b93  mov     cs:qword_18016D280, rsi
0x180056b9a  xorps   xmm0, xmm0
0x180056b9d  movups  xmmword ptr cs:rc2.left, xmm0
0x180056ba4  lea     ecx, [rsi+40h]; unsigned __int64
0x180056ba7  call    ?WinMalloc@@YAPEAX_K@Z; WinMalloc(unsigned __int64)
0x180056bac  mov     rbx, rax
0x180056baf  mov     [rsp+28h+arg_8], rax
0x180056bb4  test    rax, rax
0x180056bb7  jz      short loc_180056BF2
0x180056bb9  mov     [rax], rsi
0x180056bbc  mov     [rax+8], rsi
0x180056bc0  mov     [rax+10h], rsi
0x180056bc4  lea     rcx, [rax+18h]; lpCriticalSection
0x180056bc8  mov     edx, edi; dwSpinCount
0x180056bca  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180056bd0  cmp     eax, 1
0x180056bd3  jz      short loc_180056BF0
0x180056bd5  mov     eax, 8007000Eh
0x180056bda  mov     dword ptr [rsp+28h+pExceptionObject], eax
0x180056bde  lea     rdx, _TI1J; pThrowInfo
0x180056be5  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180056bea  call    _CxxThrowException_0
0x180056bf0  jmp     short loc_180056BF5
0x180056bf2  mov     rbx, rsi
0x180056bf5  mov     cs:qword_18016D218, rbx
0x180056bfc  mov     edi, esi
0x180056bfe  mov     eax, 8007000Eh
0x180056c03  test    rbx, rbx
0x180056c06  cmovz   edi, eax
0x180056c09  lea     rdx, ?WatsonExceptionHandler@@YAJPEAU_EXCEPTION_POINTERS@@@Z; Handler
0x180056c10  xor     ecx, ecx; First
0x180056c12  call    cs:__imp_AddVectoredExceptionHandler
0x180056c18  mov     cs:?g_watsonExceptionHandler@@3PEAXEA, rax; void * g_watsonExceptionHandler
0x180056c1f  mov     eax, edi
0x180056c21  jmp     short loc_180056C28
0x180056c23  mov     eax, 80004005h
0x180056c28  mov     rbx, [rsp+28h+arg_0]
0x180056c2d  mov     rsi, [rsp+28h+arg_10]
0x180056c32  add     rsp, 20h
0x180056c36  pop     rdi
0x180056c37  retn
```
