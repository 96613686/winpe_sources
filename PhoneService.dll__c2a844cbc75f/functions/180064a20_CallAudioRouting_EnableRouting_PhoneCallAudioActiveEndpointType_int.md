# CallAudioRouting::_EnableRouting(PhoneCallAudioActiveEndpointType,int)

- ea: `0x180064a20`
- end: `0x180064b0e`
- name: `?_EnableRouting@CallAudioRouting@@AEAAXW4PhoneCallAudioActiveEndpointType@@H@Z`
- size: `238`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x18005f9b4`
- `0x18005f9c0`
- `0x180062c5c`
- `0x180064a20`
- `0x1800698c0`
- `0x18007f9ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180064a67`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180064ac1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180064a67`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180064ac1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180064a76`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180064afd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180064a76`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180064afd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180064a33`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180064a54`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180064a33`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180064a54`

## string_xrefs

- `0x180064a48`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x180064aac`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x180064ad6`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`

## pseudocode

```c
void __fastcall CallAudioRouting::_EnableRouting(__int64 a1, unsigned int a2, int a3)
{
  __int64 v6; // rcx
  int v7; // ebx
  int v8; // eax
  __int64 v9; // rcx

  if ( *(_DWORD *)(a1 + 104) == GetCurrentThreadId() )
  {
    Log_AssertionEvent_9(v6, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 650);
    if ( *(_DWORD *)(a1 + 104) == GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 88));
  v7 = *(_DWORD *)(a1 + 140);
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 88));
  if ( v7 )
  {
    if ( a2 )
    {
      if ( a2 != 7 )
        CallAudioRouting::_SetAudioEndpoint(a1, a2);
    }
  }
  else
  {
    v8 = CallAudioRouting::_CallAudioRoutingManagerToEnableRouting(a1, a2, a3);
    if ( v8 >= 0 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 88));
      if ( *(_DWORD *)(a1 + 140) )
      {
        Log_AssertionEvent_9(v9, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 683);
        if ( *(_DWORD *)(a1 + 140) )
          MicrosoftTelemetryAssertTriggeredNoArgs();
      }
      *(_DWORD *)(a1 + 140) = 1;
      LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 88));
    }
    else
    {
      Log_HREvent_17(
        (unsigned int)v8,
        0,
        "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp",
        675);
    }
  }
}

```

## disassembly

```asm
0x180064a20  push    rbx
0x180064a22  push    rbp
0x180064a23  push    rsi
0x180064a24  push    rdi
0x180064a25  push    r14
0x180064a27  sub     rsp, 30h
0x180064a2b  mov     r14d, r8d
0x180064a2e  mov     esi, edx
0x180064a30  mov     rdi, rcx
0x180064a33  call    cs:__imp_GetCurrentThreadId
0x180064a39  lea     rbp, [rdi+58h]
0x180064a3d  cmp     [rbp+10h], eax
0x180064a40  jnz     short loc_180064A64
0x180064a42  mov     r8d, 28Ah
0x180064a48  lea     rdx, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180064a4f  call    Log_AssertionEvent_9
0x180064a54  call    cs:__imp_GetCurrentThreadId
0x180064a5a  cmp     [rdi+68h], eax
0x180064a5d  jnz     short loc_180064A64
0x180064a5f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180064a64  mov     rcx, rbp; lpCriticalSection
0x180064a67  call    cs:__imp_EnterCriticalSection
0x180064a6d  mov     ebx, [rdi+8Ch]
0x180064a73  mov     rcx, rbp; lpCriticalSection
0x180064a76  call    cs:__imp_LeaveCriticalSection
0x180064a7c  test    ebx, ebx
0x180064a7e  jz      short loc_180064A95
0x180064a80  test    esi, esi
0x180064a82  jz      short loc_180064B03
0x180064a84  cmp     esi, 7
0x180064a87  jz      short loc_180064B03
0x180064a89  mov     edx, esi
0x180064a8b  mov     rcx, rdi
0x180064a8e  call    ?_SetAudioEndpoint@CallAudioRouting@@AEAAXW4PhoneCallAudioActiveEndpointType@@@Z; CallAudioRouting::_SetAudioEndpoint(PhoneCallAudioActiveEndpointType)
0x180064a93  jmp     short loc_180064B03
0x180064a95  mov     r8d, r14d
0x180064a98  mov     edx, esi
0x180064a9a  mov     rcx, rdi
0x180064a9d  call    ?_CallAudioRoutingManagerToEnableRouting@CallAudioRouting@@AEAAJW4PhoneCallAudioActiveEndpointType@@H@Z; CallAudioRouting::_CallAudioRoutingManagerToEnableRouting(PhoneCallAudioActiveEndpointType,int)
0x180064aa2  test    eax, eax
0x180064aa4  jns     short loc_180064ABE
0x180064aa6  mov     r9d, 2A3h
0x180064aac  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180064ab3  xor     edx, edx
0x180064ab5  mov     ecx, eax
0x180064ab7  call    Log_HREvent_17
0x180064abc  jmp     short loc_180064B03
0x180064abe  mov     rcx, rbp; lpCriticalSection
0x180064ac1  call    cs:__imp_EnterCriticalSection
0x180064ac7  cmp     dword ptr [rdi+8Ch], 0
0x180064ace  jz      short loc_180064AF0
0x180064ad0  mov     r8d, 2ABh
0x180064ad6  lea     rdx, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180064add  call    Log_AssertionEvent_9
0x180064ae2  cmp     dword ptr [rdi+8Ch], 0
0x180064ae9  jz      short loc_180064AF0
0x180064aeb  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180064af0  mov     rcx, rbp; lpCriticalSection
0x180064af3  mov     dword ptr [rdi+8Ch], 1
0x180064afd  call    cs:__imp_LeaveCriticalSection
0x180064b03  add     rsp, 30h
0x180064b07  pop     r14
0x180064b09  pop     rdi
0x180064b0a  pop     rsi
0x180064b0b  pop     rbp
0x180064b0c  pop     rbx
0x180064b0d  retn
```
