# WwanTimerWrapper::DeleteTimer(void)

- ea: `0x180085a50`
- end: `0x180085af2`
- name: `?DeleteTimer@WwanTimerWrapper@@QEAAXXZ`
- size: `162`
- prototype: `void __fastcall(WwanTimerWrapper *__hidden this)`
- caller_count: `8`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001e3d0`
- `0x18001f0d8`
- `0x180065dfc`
- `0x180067f8c`
- `0x18008bb44`
- `0x180091714`
- `0x1800920e4`
- `0x18009a17c`

## callees

- `0x180014f1c`
- `0x180085a50`
- `0x1800c5d28`

## import_xrefs

- `MobileNetworking!StopTimer` at `0x180085a8f`
- `MobileNetworking!StopTimer` at `0x180085a8f`
- `MobileNetworking!DeleteReadWriteLock` at `0x180085ac9`
- `MobileNetworking!DeleteReadWriteLock` at `0x180085ac9`
- `MobileNetworking!AcquireWriteLock` at `0x180085a82`
- `MobileNetworking!AcquireWriteLock` at `0x180085a82`
- `MobileNetworking!ReleaseWriteLock` at `0x180085aa5`
- `MobileNetworking!ReleaseWriteLock` at `0x180085aa5`
- `MobileNetworking!DeleteTimer` at `0x180085ac0`
- `MobileNetworking!DeleteTimer` at `0x180085ac0`

## string_xrefs

- `0x180085aab`: ` Timer Stop Completed`
- `0x180085acf`: ` Timer Deinitialization Completed`
- `0x180085a6e`: `WwanTimerWrapper::DeleteTimer`

## pseudocode

```c
void __fastcall WwanTimerWrapper::DeleteTimer(WwanTimerWrapper *this)
{
  if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 28, 0, 1) )
  {
    AcquireWriteLock(*((_QWORD *)this + 13), this, "WwanTimerWrapper::DeleteTimer", 472);
    StopTimer(*((_QWORD *)this + 13), "WwanTimerWrapper::DeleteTimer");
    ReleaseWriteLock(*((_QWORD *)this + 13), this, "WwanTimerWrapper::DeleteTimer", 474);
    WwanLog::Info("WwanTimerWrapper::DeleteTimer", 0, L" Timer Stop Completed");
    DeleteTimer(*((_QWORD *)this + 13));
    DeleteReadWriteLock(this);
    WwanLog::Info("WwanTimerWrapper::DeleteTimer", 0, L" Timer Deinitialization Completed");
  }
  else
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
  }
}

```

## disassembly

```asm
0x180085a50  mov     [rsp+arg_0], rbx
0x180085a55  push    rdi
0x180085a56  sub     rsp, 20h
0x180085a5a  xor     edx, edx
0x180085a5c  mov     rbx, rcx
0x180085a5f  lea     eax, [rdx+1]
0x180085a62  lock cmpxchg [rcx+70h], edx
0x180085a67  test    eax, eax
0x180085a69  jz      short loc_180085AE2
0x180085a6b  mov     rdx, rcx
0x180085a6e  lea     rdi, aWwantimerwrapp_0; "WwanTimerWrapper::DeleteTimer"
0x180085a75  mov     rcx, [rcx+68h]
0x180085a79  mov     r8, rdi
0x180085a7c  mov     r9d, 1D8h
0x180085a82  call    cs:__imp_AcquireWriteLock
0x180085a88  mov     rcx, [rbx+68h]
0x180085a8c  mov     rdx, rdi
0x180085a8f  call    cs:__imp_StopTimer
0x180085a95  mov     rcx, [rbx+68h]
0x180085a99  mov     r9d, 1DAh
0x180085a9f  mov     r8, rdi
0x180085aa2  mov     rdx, rbx
0x180085aa5  call    cs:__imp_ReleaseWriteLock
0x180085aab  lea     r8, aTimerStopCompl_0; " Timer Stop Completed"
0x180085ab2  xor     edx, edx; struct _GUID *
0x180085ab4  mov     rcx, rdi; char *
0x180085ab7  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x180085abc  mov     rcx, [rbx+68h]
0x180085ac0  call    cs:__imp_DeleteTimer
0x180085ac6  mov     rcx, rbx
0x180085ac9  call    cs:__imp_DeleteReadWriteLock
0x180085acf  lea     r8, aTimerDeinitial; " Timer Deinitialization Completed"
0x180085ad6  xor     edx, edx; struct _GUID *
0x180085ad8  mov     rcx, rdi; char *
0x180085adb  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x180085ae0  jmp     short loc_180085AE7
0x180085ae2  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180085ae7  mov     rbx, [rsp+28h+arg_0]
0x180085aec  add     rsp, 20h
0x180085af0  pop     rdi
0x180085af1  retn
```
