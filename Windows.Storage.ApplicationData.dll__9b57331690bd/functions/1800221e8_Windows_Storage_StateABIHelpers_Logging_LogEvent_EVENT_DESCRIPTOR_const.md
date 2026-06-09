# Windows::Storage::StateABIHelpers::Logging::LogEvent(_EVENT_DESCRIPTOR const *)

- ea: `0x1800221e8`
- end: `0x180022287`
- name: `?LogEvent@Logging@StateABIHelpers@Storage@Windows@@CAJPEBU_EVENT_DESCRIPTOR@@@Z`
- size: `159`
- prototype: `int __fastcall(const _EVENT_DESCRIPTOR *eventDescriptor)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18004107c`
- `0x1800410c0`
- `0x180041104`

## callees

- `0x1800097b4`
- `0x1800221e8`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x18002224b`
- `ntdll!EtwEventEnabled` at `0x18002224b`
- `ntdll!RtlReleaseSRWLockShared` at `0x180022217`
- `ntdll!RtlReleaseSRWLockShared` at `0x180022274`
- `ntdll!RtlReleaseSRWLockShared` at `0x180022217`
- `ntdll!RtlReleaseSRWLockShared` at `0x180022274`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800221fe`
- `ntdll!RtlAcquireSRWLockShared` at `0x18002222f`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800221fe`
- `ntdll!RtlAcquireSRWLockShared` at `0x18002222f`
- `ntdll!EtwEventWrite` at `0x180022265`
- `ntdll!EtwEventWrite` at `0x180022265`

## pseudocode

```c
int __fastcall Windows::Storage::StateABIHelpers::Logging::LogEvent(const _EVENT_DESCRIPTOR *eventDescriptor)
{
  int v2; // ebx
  unsigned __int64 v3; // rcx
  int result; // eax

  v2 = 0;
  RtlAcquireSRWLockShared(&Windows::Storage::StateABIHelpers::Logging::lock);
  v3 = Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle;
  if ( Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle )
    goto LABEL_10;
  RtlReleaseSRWLockShared(&Windows::Storage::StateABIHelpers::Logging::lock);
  result = Windows::Storage::StateABIHelpers::Logging::Initialize();
  v2 = result;
  if ( result )
    return result;
  RtlAcquireSRWLockShared(&Windows::Storage::StateABIHelpers::Logging::lock);
  v3 = Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle;
  if ( Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle )
  {
LABEL_10:
    if ( (unsigned __int8)EtwEventEnabled(v3, eventDescriptor) )
      v2 = EtwEventWrite(Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle, eventDescriptor, 0, 0);
  }
  else
  {
    v2 = 1359;
  }
  RtlReleaseSRWLockShared(&Windows::Storage::StateABIHelpers::Logging::lock);
  return v2;
}

```

## disassembly

```asm
0x1800221e8  mov     [rsp+arg_0], rbx
0x1800221ed  push    rdi
0x1800221ee  sub     rsp, 20h
0x1800221f2  mov     rdi, eventDescriptor
0x1800221f5  xor     ebx, ebx
0x1800221f7  lea     eventDescriptor, ?lock@Logging@StateABIHelpers@Storage@Windows@@0U_RTL_SRWLOCK@@A; _RTL_SRWLOCK Windows::Storage::StateABIHelpers::Logging::lock
0x1800221fe  call    cs:__imp_RtlAcquireSRWLockShared
0x180022204  mov     eventDescriptor, cs:?eventRegisteredHandle@Logging@StateABIHelpers@Storage@Windows@@0_KA; unsigned __int64 Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle
0x18002220b  test    eventDescriptor, eventDescriptor
0x18002220e  jnz     short loc_180022248
0x180022210  lea     eventDescriptor, ?lock@Logging@StateABIHelpers@Storage@Windows@@0U_RTL_SRWLOCK@@A; _RTL_SRWLOCK Windows::Storage::StateABIHelpers::Logging::lock
0x180022217  call    cs:__imp_RtlReleaseSRWLockShared
0x18002221d  call    ?Initialize@Logging@StateABIHelpers@Storage@Windows@@CAJXZ; Windows::Storage::StateABIHelpers::Logging::Initialize(void)
0x180022222  mov     ebx, eax
0x180022224  test    eax, eax
0x180022226  jnz     short loc_18002227C
0x180022228  lea     eventDescriptor, ?lock@Logging@StateABIHelpers@Storage@Windows@@0U_RTL_SRWLOCK@@A; _RTL_SRWLOCK Windows::Storage::StateABIHelpers::Logging::lock
0x18002222f  call    cs:__imp_RtlAcquireSRWLockShared
0x180022235  mov     eventDescriptor, cs:?eventRegisteredHandle@Logging@StateABIHelpers@Storage@Windows@@0_KA; unsigned __int64 Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle
0x18002223c  test    eventDescriptor, eventDescriptor
0x18002223f  jnz     short loc_180022248
0x180022241  mov     ebx, 54Fh
0x180022246  jmp     short loc_18002226D
0x180022248  mov     rdx, rdi
0x18002224b  call    cs:__imp_EtwEventEnabled
0x180022251  test    al, al
0x180022253  jz      short loc_18002226D
0x180022255  mov     eventDescriptor, cs:?eventRegisteredHandle@Logging@StateABIHelpers@Storage@Windows@@0_KA; unsigned __int64 Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle
0x18002225c  xor     r9d, r9d
0x18002225f  xor     r8d, r8d
0x180022262  mov     rdx, rdi
0x180022265  call    cs:__imp_EtwEventWrite
0x18002226b  mov     ebx, eax
0x18002226d  lea     eventDescriptor, ?lock@Logging@StateABIHelpers@Storage@Windows@@0U_RTL_SRWLOCK@@A; _RTL_SRWLOCK Windows::Storage::StateABIHelpers::Logging::lock
0x180022274  call    cs:__imp_RtlReleaseSRWLockShared
0x18002227a  mov     eax, ebx
0x18002227c  mov     rbx, [rsp+28h+arg_0]
0x180022281  add     rsp, 20h
0x180022285  pop     rdi
0x180022286  retn
```
