# NLInternal::CNotifyVoiceClip::CheckStatusOnBackgroundThread(void)

- ea: `0x140014734`
- end: `0x14001482d`
- name: `?CheckStatusOnBackgroundThread@CNotifyVoiceClip@NLInternal@@CAJXZ`
- size: `249`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140017a40`

## callees

- `0x140014734`
- `0x140016110`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400147c5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400147c5`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x14001474b`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x14001474b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014767`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001479b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400147fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140014767`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001479b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400147fb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140014819`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140014819`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1400147b7`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1400147b7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x14001478d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x14001478d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1400147d3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1400147d3`

## pseudocode

```c
__int64 NLInternal::CNotifyVoiceClip::CheckStatusOnBackgroundThread(void)
{
  HANDLE Event; // rax
  signed int v1; // eax
  signed int v2; // ebx
  struct _TP_WORK *ThreadpoolWork; // rsi
  signed int LastError; // eax
  int v5; // eax
  void **v7; // [rsp+20h] [rbp-18h] BYREF
  HANDLE hHandle; // [rsp+28h] [rbp-10h]

  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  hHandle = Event;
  v7 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
  if ( Event )
  {
    v2 = 0;
    ThreadpoolWork = CreateThreadpoolWork(NLInternal::CNotifyVoiceClip::ThreadpoolWrapper, Event, 0);
    if ( ThreadpoolWork )
      goto LABEL_8;
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    if ( v2 >= 0 )
    {
LABEL_8:
      SubmitThreadpoolWork(ThreadpoolWork);
      WaitForSingleObject(hHandle, 0xFFFFFFFF);
      if ( ThreadpoolWork )
        CloseThreadpoolWork(ThreadpoolWork);
    }
  }
  else
  {
    v1 = GetLastError();
    v2 = v1;
    if ( v1 > 0 )
      v2 = (unsigned __int16)v1 | 0x80070000;
  }
  v7 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
  if ( hHandle
    && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::InternalClose(&v7) )
  {
    v5 = GetLastError();
    if ( v5 > 0 )
      v5 = (unsigned __int16)v5 | 0x80070000;
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140014734  mov     [rsp+arg_0], rbx
0x140014739  push    rsi
0x14001473a  sub     rsp, 30h
0x14001473e  mov     r9d, 1F0003h; dwDesiredAccess
0x140014744  xor     r8d, r8d; dwFlags
0x140014747  xor     edx, edx; lpName
0x140014749  xor     ecx, ecx; lpEventAttributes
0x14001474b  call    cs:__imp_CreateEventExW
0x140014751  mov     [rsp+38h+hHandle], rax
0x140014756  lea     rcx, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x14001475d  mov     [rsp+38h+var_18], rcx
0x140014762  test    rax, rax
0x140014765  jnz     short loc_14001477E
0x140014767  call    cs:__imp_GetLastError
0x14001476d  mov     ebx, eax
0x14001476f  test    eax, eax
0x140014771  jle     short loc_1400147D9
0x140014773  movzx   ebx, ax
0x140014776  or      ebx, 80070000h
0x14001477c  jmp     short loc_1400147D9
0x14001477e  xor     r8d, r8d; pcbe
0x140014781  lea     rcx, ?ThreadpoolWrapper@CNotifyVoiceClip@NLInternal@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x140014788  mov     rdx, rax; pv
0x14001478b  xor     ebx, ebx
0x14001478d  call    cs:__imp_CreateThreadpoolWork
0x140014793  mov     rsi, rax
0x140014796  test    rax, rax
0x140014799  jnz     short loc_1400147B4
0x14001479b  call    cs:__imp_GetLastError
0x1400147a1  mov     ebx, eax
0x1400147a3  test    eax, eax
0x1400147a5  jle     short loc_1400147B0
0x1400147a7  movzx   ebx, ax
0x1400147aa  or      ebx, 80070000h
0x1400147b0  test    ebx, ebx
0x1400147b2  js      short loc_1400147D9
0x1400147b4  mov     rcx, rsi; pwk
0x1400147b7  call    cs:__imp_SubmitThreadpoolWork
0x1400147bd  mov     rcx, [rsp+38h+hHandle]; hHandle
0x1400147c2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1400147c5  call    cs:__imp_WaitForSingleObject
0x1400147cb  test    rsi, rsi
0x1400147ce  jz      short loc_1400147D9
0x1400147d0  mov     rcx, rsi; pwk
0x1400147d3  call    cs:__imp_CloseThreadpoolWork
0x1400147d9  cmp     [rsp+38h+hHandle], 0
0x1400147df  lea     rax, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x1400147e6  mov     [rsp+38h+var_18], rax
0x1400147eb  jz      short loc_140014820
0x1400147ed  lea     rcx, [rsp+38h+var_18]
0x1400147f2  call    ?InternalClose@?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::InternalClose(void)
0x1400147f7  test    al, al
0x1400147f9  jnz     short loc_140014820
0x1400147fb  call    cs:__imp_GetLastError
0x140014801  test    eax, eax
0x140014803  jle     short loc_14001480D
0x140014805  movzx   eax, ax
0x140014808  or      eax, 80070000h
0x14001480d  xor     r9d, r9d; lpArguments
0x140014810  xor     r8d, r8d; nNumberOfArguments
0x140014813  mov     ecx, eax; dwExceptionCode
0x140014815  lea     edx, [r9+1]; dwExceptionFlags
0x140014819  call    cs:__imp_RaiseException
0x14001481f  int     3; Trap to Debugger
0x140014820  mov     eax, ebx
0x140014822  mov     rbx, [rsp+38h+arg_0]
0x140014827  add     rsp, 30h
0x14001482b  pop     rsi
0x14001482c  retn
```
