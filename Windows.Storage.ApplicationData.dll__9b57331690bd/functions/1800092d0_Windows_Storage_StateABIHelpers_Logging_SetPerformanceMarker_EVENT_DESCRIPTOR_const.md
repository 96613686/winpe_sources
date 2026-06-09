# Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(_EVENT_DESCRIPTOR const *)

- ea: `0x1800092d0`
- end: `0x1800093bc`
- name: `?SetPerformanceMarker@Logging@StateABIHelpers@Storage@Windows@@SAJPEBU_EVENT_DESCRIPTOR@@@Z`
- size: `236`
- prototype: `int __fastcall(const _EVENT_DESCRIPTOR *eventDescriptor)`
- caller_count: `35`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180005c70`
- `0x180005de0`
- `0x180006280`
- `0x180007a00`
- `0x180007b10`
- `0x180007dc0`
- `0x180007f98`
- `0x1800082b0`
- `0x180008410`
- `0x1800089c0`
- `0x1800090b0`
- `0x180009690`
- `0x180009808`
- `0x180009900`
- `0x18000ac10`
- `0x18000ae30`
- `0x18000bc30`
- `0x180013590`
- `0x180014ab0`
- `0x180016890`
- `0x180019714`
- `0x18001aaf8`
- `0x18001ada0`
- `0x18001b390`
- `0x18001d950`
- `0x18001da60`
- `0x18001ded0`
- `0x18001f770`
- `0x18001fea0`
- `0x180024138`
- `0x180035060`
- `0x180037e10`
- `0x180038098`
- `0x180038f30`
- `0x18003f264`

## callees

- `0x1800092d0`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x1800092fb`
- `ntdll!EtwEventEnabled` at `0x1800092fb`
- `ntdll!EtwEventRegister` at `0x18000936f`
- `ntdll!EtwEventRegister` at `0x18000936f`
- `ntdll!RtlReleaseSRWLockShared` at `0x180009324`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000933e`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800093ac`
- `ntdll!RtlReleaseSRWLockShared` at `0x180009324`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000933e`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800093ac`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800092e4`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000938f`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800092e4`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000938f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000937e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000937e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000934d`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000934d`
- `ntdll!EtwEventWrite` at `0x180009315`
- `ntdll!EtwEventWrite` at `0x180009315`

## pseudocode

```c
__int64 __fastcall Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(
        const _EVENT_DESCRIPTOR *eventDescriptor)
{
  unsigned __int64 v2; // rcx
  unsigned int v3; // ebx

  RtlAcquireSRWLockShared(&Windows::Storage::StateABIHelpers::Logging::lock);
  v2 = Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle;
  if ( Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle )
  {
LABEL_2:
    v3 = 0;
    if ( (unsigned __int8)EtwEventEnabled(v2, eventDescriptor) )
      v3 = EtwEventWrite(Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle, eventDescriptor, 0, 0);
    RtlReleaseSRWLockShared(&Windows::Storage::StateABIHelpers::Logging::lock);
    return v3;
  }
  RtlReleaseSRWLockShared(&Windows::Storage::StateABIHelpers::Logging::lock);
  v3 = 0;
  RtlAcquireSRWLockExclusive(&Windows::Storage::StateABIHelpers::Logging::lock);
  if ( !Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle )
    v3 = EtwEventRegister(
           &StateManagerProviderId,
           0,
           0,
           &Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle);
  RtlReleaseSRWLockExclusive(&Windows::Storage::StateABIHelpers::Logging::lock);
  if ( !v3 )
  {
    RtlAcquireSRWLockShared(&Windows::Storage::StateABIHelpers::Logging::lock);
    v2 = Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle;
    if ( !Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle )
    {
      RtlReleaseSRWLockShared(&Windows::Storage::StateABIHelpers::Logging::lock);
      return 1359;
    }
    goto LABEL_2;
  }
  return v3;
}

```

## disassembly

```asm
0x1800092d0  mov     [rsp+arg_0], rbx
0x1800092d5  push    rdi
0x1800092d6  sub     rsp, 20h
0x1800092da  mov     rdi, eventDescriptor
0x1800092dd  lea     eventDescriptor, ?lock@Logging@StateABIHelpers@Storage@Windows@@0U_RTL_SRWLOCK@@A; _RTL_SRWLOCK Windows::Storage::StateABIHelpers::Logging::lock
0x1800092e4  call    cs:__imp_RtlAcquireSRWLockShared
0x1800092ea  mov     eventDescriptor, cs:?eventRegisteredHandle@Logging@StateABIHelpers@Storage@Windows@@0_KA; unsigned __int64 Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle
0x1800092f1  test    eventDescriptor, eventDescriptor
0x1800092f4  jz      short loc_180009337
0x1800092f6  mov     rdx, rdi
0x1800092f9  xor     ebx, ebx
0x1800092fb  call    cs:__imp_EtwEventEnabled
0x180009301  test    al, al
0x180009303  jz      short loc_18000931D
0x180009305  mov     eventDescriptor, cs:?eventRegisteredHandle@Logging@StateABIHelpers@Storage@Windows@@0_KA; unsigned __int64 Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle
0x18000930c  xor     r9d, r9d
0x18000930f  xor     r8d, r8d
0x180009312  mov     rdx, rdi
0x180009315  call    cs:__imp_EtwEventWrite
0x18000931b  mov     ebx, eax
0x18000931d  lea     eventDescriptor, ?lock@Logging@StateABIHelpers@Storage@Windows@@0U_RTL_SRWLOCK@@A; _RTL_SRWLOCK Windows::Storage::StateABIHelpers::Logging::lock
0x180009324  call    cs:__imp_RtlReleaseSRWLockShared
0x18000932a  mov     eax, ebx
0x18000932c  mov     rbx, [rsp+28h+arg_0]
0x180009331  add     rsp, 20h
0x180009335  pop     rdi
0x180009336  retn
0x180009337  lea     eventDescriptor, ?lock@Logging@StateABIHelpers@Storage@Windows@@0U_RTL_SRWLOCK@@A; _RTL_SRWLOCK Windows::Storage::StateABIHelpers::Logging::lock
0x18000933e  call    cs:__imp_RtlReleaseSRWLockShared
0x180009344  lea     eventDescriptor, ?lock@Logging@StateABIHelpers@Storage@Windows@@0U_RTL_SRWLOCK@@A; _RTL_SRWLOCK Windows::Storage::StateABIHelpers::Logging::lock
0x18000934b  xor     ebx, ebx
0x18000934d  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180009353  cmp     cs:?eventRegisteredHandle@Logging@StateABIHelpers@Storage@Windows@@0_KA, rbx; unsigned __int64 Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle
0x18000935a  jnz     short loc_180009377
0x18000935c  lea     r9, ?eventRegisteredHandle@Logging@StateABIHelpers@Storage@Windows@@0_KA; unsigned __int64 Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle
0x180009363  xor     r8d, r8d
0x180009366  xor     edx, edx
0x180009368  lea     eventDescriptor, StateManagerProviderId
0x18000936f  call    cs:__imp_EtwEventRegister
0x180009375  mov     ebx, eax
0x180009377  lea     eventDescriptor, ?lock@Logging@StateABIHelpers@Storage@Windows@@0U_RTL_SRWLOCK@@A; _RTL_SRWLOCK Windows::Storage::StateABIHelpers::Logging::lock
0x18000937e  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180009384  test    ebx, ebx
0x180009386  jnz     short loc_18000932A
0x180009388  lea     eventDescriptor, ?lock@Logging@StateABIHelpers@Storage@Windows@@0U_RTL_SRWLOCK@@A; _RTL_SRWLOCK Windows::Storage::StateABIHelpers::Logging::lock
0x18000938f  call    cs:__imp_RtlAcquireSRWLockShared
0x180009395  mov     eventDescriptor, cs:?eventRegisteredHandle@Logging@StateABIHelpers@Storage@Windows@@0_KA; unsigned __int64 Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle
0x18000939c  test    eventDescriptor, eventDescriptor
0x18000939f  jnz     loc_1800092F6
0x1800093a5  lea     eventDescriptor, ?lock@Logging@StateABIHelpers@Storage@Windows@@0U_RTL_SRWLOCK@@A; _RTL_SRWLOCK Windows::Storage::StateABIHelpers::Logging::lock
0x1800093ac  call    cs:__imp_RtlReleaseSRWLockShared
0x1800093b2  mov     ebx, 54Fh
0x1800093b7  jmp     loc_18000932A
```
