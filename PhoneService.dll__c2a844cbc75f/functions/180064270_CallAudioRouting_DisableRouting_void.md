# CallAudioRouting::_DisableRouting(void)

- ea: `0x180064270`
- end: `0x18006433d`
- name: `?_DisableRouting@CallAudioRouting@@AEAAXXZ`
- size: `205`
- prototype: `void __fastcall(CallAudioRouting *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x18005f9b4`
- `0x18005f9c0`
- `0x18006278c`
- `0x180064270`
- `0x18007f9ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800642b1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800642f0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800642b1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800642f0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800642c3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006432c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800642c3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006432c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006427d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006429e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006427d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006429e`

## string_xrefs

- `0x180064292`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x1800642db`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x180064305`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`

## pseudocode

```c
void __fastcall CallAudioRouting::_DisableRouting(CallAudioRouting *this)
{
  __int64 v2; // rcx
  struct _RTL_CRITICAL_SECTION *v3; // rcx
  int v4; // eax
  __int64 v5; // rcx

  if ( *((_DWORD *)this + 26) == GetCurrentThreadId() )
  {
    Log_AssertionEvent_9(v2, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 708);
    if ( *((_DWORD *)this + 26) == GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 88);
  if ( *((_DWORD *)this + 35) )
  {
    LeaveCriticalSection(v3);
    v4 = CallAudioRouting::_CallAudioRoutingManagerToDisableRouting(this);
    if ( v4 < 0 )
    {
      Log_HREvent_17(
        (unsigned int)v4,
        0,
        "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp",
        720);
      return;
    }
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
    if ( !*((_DWORD *)this + 35) )
    {
      Log_AssertionEvent_9(v5, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\callaudiorouting.cpp", 728);
      if ( !*((_DWORD *)this + 35) )
        MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    *((_DWORD *)this + 35) = 0;
    v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 88);
  }
  LeaveCriticalSection(v3);
}

```

## disassembly

```asm
0x180064270  mov     [rsp+arg_0], rbx
0x180064275  push    rdi
0x180064276  sub     rsp, 30h
0x18006427a  mov     rbx, rcx
0x18006427d  call    cs:__imp_GetCurrentThreadId
0x180064283  lea     rdi, [rbx+58h]
0x180064287  cmp     [rdi+10h], eax
0x18006428a  jnz     short loc_1800642AE
0x18006428c  mov     r8d, 2C4h
0x180064292  lea     rdx, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180064299  call    Log_AssertionEvent_9
0x18006429e  call    cs:__imp_GetCurrentThreadId
0x1800642a4  cmp     [rbx+68h], eax
0x1800642a7  jnz     short loc_1800642AE
0x1800642a9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800642ae  mov     rcx, rdi; lpCriticalSection
0x1800642b1  call    cs:__imp_EnterCriticalSection
0x1800642b7  cmp     dword ptr [rbx+8Ch], 0
0x1800642be  mov     rcx, rdi; lpCriticalSection
0x1800642c1  jz      short loc_18006432C
0x1800642c3  call    cs:__imp_LeaveCriticalSection
0x1800642c9  mov     rcx, rbx; this
0x1800642cc  call    ?_CallAudioRoutingManagerToDisableRouting@CallAudioRouting@@AEAAJXZ; CallAudioRouting::_CallAudioRoutingManagerToDisableRouting(void)
0x1800642d1  test    eax, eax
0x1800642d3  jns     short loc_1800642ED
0x1800642d5  mov     r9d, 2D0h
0x1800642db  lea     r8, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x1800642e2  xor     edx, edx
0x1800642e4  mov     ecx, eax
0x1800642e6  call    Log_HREvent_17
0x1800642eb  jmp     short loc_180064332
0x1800642ed  mov     rcx, rdi; lpCriticalSection
0x1800642f0  call    cs:__imp_EnterCriticalSection
0x1800642f6  cmp     dword ptr [rbx+8Ch], 0
0x1800642fd  jnz     short loc_18006431F
0x1800642ff  mov     r8d, 2D8h
0x180064305  lea     rdx, aOnecoreuapNetP_6; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18006430c  call    Log_AssertionEvent_9
0x180064311  cmp     dword ptr [rbx+8Ch], 0
0x180064318  jnz     short loc_18006431F
0x18006431a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18006431f  mov     dword ptr [rbx+8Ch], 0
0x180064329  mov     rcx, rdi; lpCriticalSection
0x18006432c  call    cs:__imp_LeaveCriticalSection
0x180064332  mov     rbx, [rsp+38h+arg_0]
0x180064337  add     rsp, 30h
0x18006433b  pop     rdi
0x18006433c  retn
```
