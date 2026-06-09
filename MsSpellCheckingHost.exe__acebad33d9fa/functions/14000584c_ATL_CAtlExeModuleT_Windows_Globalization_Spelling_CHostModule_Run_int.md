# ATL::CAtlExeModuleT<Windows::Globalization::Spelling::CHostModule>::Run(int)

- ea: `0x14000584c`
- end: `0x1400059eb`
- name: `?Run@?$CAtlExeModuleT@VCHostModule@Spelling@Globalization@Windows@@@ATL@@QEAAJH@Z`
- size: `415`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140006b20`

## callees

- `0x140004458`
- `0x1400046e8`
- `0x14000584c`
- `0x1400059f4`
- `0x140005ba4`
- `0x140006ab8`

## import_xrefs

- `USER32!DispatchMessageW` at `0x1400059b4`
- `USER32!DispatchMessageW` at `0x1400059b4`
- `USER32!TranslateMessage` at `0x1400059a9`
- `USER32!TranslateMessage` at `0x1400059a9`
- `USER32!GetMessageW` at `0x1400059c7`
- `USER32!GetMessageW` at `0x1400059c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000586e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400058cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005922`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005967`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000586e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400058cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005922`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005967`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005947`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005947`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x1400058bb`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x1400058bb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140005915`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140005915`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14000595d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14000595d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x140005861`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x140005861`

## string_xrefs

- `0x140005906`: `SpellingHostRegistrationComplete`

## pseudocode

```c
__int64 ATL::CAtlExeModuleT<Windows::Globalization::Spelling::CHostModule>::Run()
{
  signed int LastError; // eax
  IUnknown *v1; // rcx
  int started; // ebx
  DWORD v3; // edx
  signed int v4; // eax
  bool v5; // zf
  signed int v6; // eax
  signed int v7; // eax
  int v8; // eax
  MSG Msg; // [rsp+20h] [rbp-38h] BYREF

  xmmword_14001C040 = CreateMutexW(0, 0, L"SpellingHostSingletonMutex");
  LastError = GetLastError();
  v1 = (IUnknown *)xmmword_14001C040;
  started = LastError;
  if ( xmmword_14001C040 )
  {
    if ( LastError == 183 )
    {
      CloseHandle(xmmword_14001C040);
      started = -2147024713;
      goto LABEL_25;
    }
  }
  else
  {
    if ( LastError > 0 )
      started = (unsigned __int16)LastError | 0x80070000;
    if ( started < 0 )
      goto LABEL_25;
  }
  started = Windows::Globalization::Spelling::CHostModule::SharePIDInMemory((Windows::Globalization::Spelling::CHostModule *)xmmword_14001C040);
  if ( started < 0 )
    goto LABEL_25;
  started = 0;
  hMutex = OpenMutexW(0x120000u, 0, L"SpellingHostActivationMutex");
  if ( !hMutex )
  {
    v4 = GetLastError();
    started = v4;
    if ( v4 > 0 )
      started = (unsigned __int16)v4 | 0x80070000;
  }
  v5 = started == 0;
  if ( started < 0 )
    goto LABEL_26;
  started = ATL::CAtlExeModuleT<Windows::Globalization::Spelling::CHostModule>::PreMessageLoop(v1, v3);
  if ( started < 0
    || (started = Windows::Globalization::Spelling::CHostModule::StartTimeoutMonitor((Windows::Globalization::Spelling::CHostModule *)v1),
        started < 0) )
  {
LABEL_25:
    v5 = started == 0;
    goto LABEL_26;
  }
  started = 0;
  *(&xmmword_14001C040 + 1) = CreateEventW(0, 1, 0, L"SpellingHostRegistrationComplete");
  v6 = GetLastError();
  v1 = (IUnknown *)*(&xmmword_14001C040 + 1);
  if ( *(&xmmword_14001C040 + 1)
    || (v6 > 0 ? (started = (unsigned __int16)v6 | 0x80070000) : (started = v6), v5 = started == 0, started >= 0) )
  {
    if ( !SetEvent(*(&xmmword_14001C040 + 1)) )
    {
      v7 = GetLastError();
      started = v7;
      if ( v7 > 0 )
        started = (unsigned __int16)v7 | 0x80070000;
    }
    v5 = started == 0;
    if ( started >= 0 )
    {
      v8 = McGenEventRegister_EventRegister();
      started = v8;
      if ( v8 > 0 )
        started = (unsigned __int16)v8 | 0x80070000;
      goto LABEL_25;
    }
  }
LABEL_26:
  if ( v5 )
  {
    memset(&Msg, 0, sizeof(Msg));
    while ( GetMessageW(&Msg, 0, 0, 0) > 0 )
    {
      TranslateMessage(&Msg);
      DispatchMessageW(&Msg);
    }
    return (unsigned int)Windows::Globalization::Spelling::CHostModule::PostMessageLoop((Windows::Globalization::Spelling::CHostModule *)v1);
  }
  if ( started >= 0 )
    return (unsigned int)Windows::Globalization::Spelling::CHostModule::PostMessageLoop((Windows::Globalization::Spelling::CHostModule *)v1);
  return (unsigned int)started;
}

```

## disassembly

```asm
0x14000584c  mov     [rsp+arg_0], rbx
0x140005851  push    rdi
0x140005852  sub     rsp, 50h
0x140005856  lea     r8, Name; "SpellingHostSingletonMutex"
0x14000585d  xor     edx, edx; bInitialOwner
0x14000585f  xor     ecx, ecx; lpMutexAttributes
0x140005861  call    cs:__imp_CreateMutexW
0x140005867  mov     qword ptr cs:xmmword_14001C040, rax
0x14000586e  call    cs:__imp_GetLastError
0x140005874  mov     rcx, qword ptr cs:xmmword_14001C040; this
0x14000587b  mov     edi, 80070000h
0x140005880  mov     ebx, eax
0x140005882  test    rcx, rcx
0x140005885  jnz     loc_14000593C
0x14000588b  test    eax, eax
0x14000588d  jle     short loc_140005894
0x14000588f  movzx   ebx, ax
0x140005892  or      ebx, edi
0x140005894  test    ebx, ebx
0x140005896  js      loc_14000598C
0x14000589c  call    ?SharePIDInMemory@CHostModule@Spelling@Globalization@Windows@@QEAAJXZ; Windows::Globalization::Spelling::CHostModule::SharePIDInMemory(void)
0x1400058a1  mov     ebx, eax
0x1400058a3  test    eax, eax
0x1400058a5  js      loc_14000598C
0x1400058ab  lea     r8, aSpellinghostac; "SpellingHostActivationMutex"
0x1400058b2  xor     edx, edx; bInheritHandle
0x1400058b4  mov     ecx, 120000h; dwDesiredAccess
0x1400058b9  xor     ebx, ebx
0x1400058bb  call    cs:__imp_OpenMutexW
0x1400058c1  mov     cs:hMutex, rax
0x1400058c8  test    rax, rax
0x1400058cb  jnz     short loc_1400058DE
0x1400058cd  call    cs:__imp_GetLastError
0x1400058d3  mov     ebx, eax
0x1400058d5  test    eax, eax
0x1400058d7  jle     short loc_1400058DE
0x1400058d9  movzx   ebx, ax
0x1400058dc  or      ebx, edi
0x1400058de  test    ebx, ebx
0x1400058e0  js      loc_14000598E
0x1400058e6  call    ?PreMessageLoop@?$CAtlExeModuleT@VCHostModule@Spelling@Globalization@Windows@@@ATL@@QEAAJH@Z; ATL::CAtlExeModuleT<Windows::Globalization::Spelling::CHostModule>::PreMessageLoop(int)
0x1400058eb  mov     ebx, eax
0x1400058ed  test    eax, eax
0x1400058ef  js      loc_14000598C
0x1400058f5  call    ?StartTimeoutMonitor@CHostModule@Spelling@Globalization@Windows@@QEAAJXZ; Windows::Globalization::Spelling::CHostModule::StartTimeoutMonitor(void)
0x1400058fa  mov     ebx, eax
0x1400058fc  test    eax, eax
0x1400058fe  js      loc_14000598C
0x140005904  xor     ebx, ebx
0x140005906  lea     r9, aSpellinghostre; "SpellingHostRegistrationComplete"
0x14000590d  xor     r8d, r8d; bInitialState
0x140005910  xor     ecx, ecx; lpEventAttributes
0x140005912  lea     edx, [rbx+1]; bManualReset
0x140005915  call    cs:__imp_CreateEventW
0x14000591b  mov     qword ptr cs:xmmword_14001C040+8, rax
0x140005922  call    cs:__imp_GetLastError
0x140005928  mov     rcx, qword ptr cs:xmmword_14001C040+8; hEvent
0x14000592f  test    rcx, rcx
0x140005932  jnz     short loc_14000595D
0x140005934  test    eax, eax
0x140005936  jg      short loc_140005954
0x140005938  mov     ebx, eax
0x14000593a  jmp     short loc_140005959
0x14000593c  cmp     eax, 0B7h
0x140005941  jnz     loc_14000589C
0x140005947  call    cs:__imp_CloseHandle
0x14000594d  mov     ebx, 800700B7h
0x140005952  jmp     short loc_14000598C
0x140005954  movzx   ebx, ax
0x140005957  or      ebx, edi
0x140005959  test    ebx, ebx
0x14000595b  js      short loc_14000598E
0x14000595d  call    cs:__imp_SetEvent
0x140005963  test    eax, eax
0x140005965  jnz     short loc_140005978
0x140005967  call    cs:__imp_GetLastError
0x14000596d  mov     ebx, eax
0x14000596f  test    eax, eax
0x140005971  jle     short loc_140005978
0x140005973  movzx   ebx, ax
0x140005976  or      ebx, edi
0x140005978  test    ebx, ebx
0x14000597a  js      short loc_14000598E
0x14000597c  call    McGenEventRegister_EventRegister
0x140005981  mov     ebx, eax
0x140005983  test    eax, eax
0x140005985  jle     short loc_14000598C
0x140005987  movzx   ebx, ax
0x14000598a  or      ebx, edi
0x14000598c  test    ebx, ebx
0x14000598e  jnz     short loc_1400059D3
0x140005990  xorps   xmm0, xmm0
0x140005993  movups  xmmword ptr [rsp+58h+Msg.hwnd], xmm0
0x140005998  movups  xmmword ptr [rsp+58h+Msg.wParam], xmm0
0x14000599d  movups  xmmword ptr [rsp+58h+Msg.time], xmm0
0x1400059a2  jmp     short loc_1400059BA
0x1400059a4  lea     rcx, [rsp+58h+Msg]; lpMsg
0x1400059a9  call    cs:__imp_TranslateMessage
0x1400059af  lea     rcx, [rsp+58h+Msg]; lpMsg
0x1400059b4  call    cs:__imp_DispatchMessageW
0x1400059ba  xor     r9d, r9d; wMsgFilterMax
0x1400059bd  lea     rcx, [rsp+58h+Msg]; lpMsg
0x1400059c2  xor     r8d, r8d; wMsgFilterMin
0x1400059c5  xor     edx, edx; hWnd
0x1400059c7  call    cs:__imp_GetMessageW
0x1400059cd  test    eax, eax
0x1400059cf  jg      short loc_1400059A4
0x1400059d1  jmp     short loc_1400059D7
0x1400059d3  test    ebx, ebx
0x1400059d5  js      short loc_1400059DE
0x1400059d7  call    ?PostMessageLoop@CHostModule@Spelling@Globalization@Windows@@QEAAJXZ; Windows::Globalization::Spelling::CHostModule::PostMessageLoop(void)
0x1400059dc  mov     ebx, eax
0x1400059de  mov     eax, ebx
0x1400059e0  mov     rbx, [rsp+58h+arg_0]
0x1400059e5  add     rsp, 50h
0x1400059e9  pop     rdi
0x1400059ea  retn
```
