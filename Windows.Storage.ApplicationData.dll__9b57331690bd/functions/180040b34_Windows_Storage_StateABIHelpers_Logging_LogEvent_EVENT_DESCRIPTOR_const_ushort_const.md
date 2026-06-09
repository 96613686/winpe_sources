# Windows::Storage::StateABIHelpers::Logging::LogEvent(_EVENT_DESCRIPTOR const *,ushort const *)

- ea: `0x180040b34`
- end: `0x180040c08`
- name: `?LogEvent@Logging@StateABIHelpers@Storage@Windows@@CAJPEBU_EVENT_DESCRIPTOR@@PEBG@Z`
- size: `212`
- prototype: `int __fastcall(const _EVENT_DESCRIPTOR *logString, const wchar_t *eventDescriptor)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001fc18`

## callees

- `0x1800104c0`
- `0x18001a08c`
- `0x180021fc4`
- `0x180040b34`
- `0x180041620`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x180040b77`
- `ntdll!EtwEventEnabled` at `0x180040b77`
- `ntdll!RtlReleaseSRWLockShared` at `0x180040be8`
- `ntdll!RtlReleaseSRWLockShared` at `0x180040be8`
- `ntdll!EtwEventWrite` at `0x180040bd9`
- `ntdll!EtwEventWrite` at `0x180040bd9`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180040b9e`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180040b9e`

## pseudocode

```c
int __fastcall Windows::Storage::StateABIHelpers::Logging::LogEvent(
        const _EVENT_DESCRIPTOR *logString,
        const wchar_t *eventDescriptor)
{
  int result; // eax
  ULONG v4; // ebx
  NTSTATUS v5; // eax
  unsigned __int64 logStringLength; // [rsp+20h] [rbp-28h] BYREF
  _EVENT_DATA_DESCRIPTOR eventData[1]; // [rsp+28h] [rbp-20h] BYREF

  if ( !eventDescriptor )
    MicrosoftTelemetryAssertTriggeredNoArgs(logString);
  result = Windows::Storage::StateABIHelpers::Logging::AcquireLockAndInitLogging();
  v4 = result;
  if ( !result )
  {
    if ( (unsigned __int8)EtwEventEnabled(
                            Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle,
                            &APPLICATIONSTATE_FIXSTATELOCATIONS_SUCCEEDED_EVENT) )
    {
      logStringLength = 0;
      v5 = RtlStringCchLengthW(eventDescriptor, 0x7FFFFFFFu, &logStringLength);
      v4 = RtlNtStatusToDosErrorNoTeb(v5);
      if ( !v4 )
      {
        eventData[0].Ptr = (unsigned __int64)eventDescriptor;
        eventData[0].Reserved = 0;
        eventData[0].Size = 2 * logStringLength + 2;
        v4 = EtwEventWrite(
               Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle,
               &APPLICATIONSTATE_FIXSTATELOCATIONS_SUCCEEDED_EVENT,
               1,
               eventData);
      }
    }
    RtlReleaseSRWLockShared(&Windows::Storage::StateABIHelpers::Logging::lock);
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x180040b34  mov     [rsp+arg_0], rbx
0x180040b39  push    rdi
0x180040b3a  sub     rsp, 40h
0x180040b3e  mov     rax, cs:__security_cookie
0x180040b45  xor     rax, rsp
0x180040b48  mov     [rsp+48h+var_10], rax
0x180040b4d  mov     rdi, logString
0x180040b50  test    logString, logString
0x180040b53  jnz     short loc_180040B5A
0x180040b55  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "logString != NULL")
0x180040b5a  call    ?AcquireLockAndInitLogging@Logging@StateABIHelpers@Storage@Windows@@CAJXZ; Windows::Storage::StateABIHelpers::Logging::AcquireLockAndInitLogging(void)
0x180040b5f  mov     ebx, eax
0x180040b61  test    eax, eax
0x180040b63  jnz     loc_180040BF0
0x180040b69  mov     rcx, cs:?eventRegisteredHandle@Logging@StateABIHelpers@Storage@Windows@@0_KA; unsigned __int64 Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle
0x180040b70  lea     logString, APPLICATIONSTATE_FIXSTATELOCATIONS_SUCCEEDED_EVENT
0x180040b77  call    cs:__imp_EtwEventEnabled
0x180040b7d  test    al, al
0x180040b7f  jz      short loc_180040BE1
0x180040b81  lea     r8, [rsp+48h+logStringLength]; pcchLength
0x180040b86  mov     [rsp+48h+logStringLength], 0
0x180040b8f  mov     edx, 7FFFFFFFh; cchMax
0x180040b94  mov     rcx, rdi; psz
0x180040b97  call    ?RtlStringCchLengthW@@YAJPEBG_KPEA_K@Z; RtlStringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180040b9c  mov     ecx, eax; Status
0x180040b9e  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180040ba4  mov     ebx, eax
0x180040ba6  test    eax, eax
0x180040ba8  jnz     short loc_180040BE1
0x180040baa  mov     eax, dword ptr [rsp+48h+logStringLength]
0x180040bae  lea     r9, [rsp+48h+eventData]
0x180040bb3  mov     rcx, cs:?eventRegisteredHandle@Logging@StateABIHelpers@Storage@Windows@@0_KA; unsigned __int64 Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle
0x180040bba  lea     r8d, [rbx+1]
0x180040bbe  lea     logString, APPLICATIONSTATE_FIXSTATELOCATIONS_SUCCEEDED_EVENT
0x180040bc5  mov     [rsp+48h+eventData.Ptr], rdi
0x180040bca  mov     dword ptr [rsp+48h+eventData.___u2], ebx
0x180040bce  lea     eax, ds:2[rax*2]
0x180040bd5  mov     [rsp+48h+eventData.Size], eax
0x180040bd9  call    cs:__imp_EtwEventWrite
0x180040bdf  mov     ebx, eax
0x180040be1  lea     rcx, ?lock@Logging@StateABIHelpers@Storage@Windows@@0U_RTL_SRWLOCK@@A; _RTL_SRWLOCK Windows::Storage::StateABIHelpers::Logging::lock
0x180040be8  call    cs:__imp_RtlReleaseSRWLockShared
0x180040bee  mov     eax, ebx
0x180040bf0  mov     rcx, [rsp+48h+var_10]
0x180040bf5  xor     rcx, rsp; StackCookie
0x180040bf8  call    __security_check_cookie
0x180040bfd  mov     rbx, [rsp+48h+arg_0]
0x180040c02  add     rsp, 40h
0x180040c06  pop     rdi
0x180040c07  retn
```
