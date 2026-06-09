# Windows::Storage::StateABIHelpers::Logging::LogEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,long,long)

- ea: `0x1800100d8`
- end: `0x18001021b`
- name: `?LogEvent@Logging@StateABIHelpers@Storage@Windows@@CAJPEBU_EVENT_DESCRIPTOR@@PEBG1JJ@Z`
- size: `323`
- prototype: `int __fastcall(const _EVENT_DESCRIPTOR *eventDescriptor, const wchar_t *operation, const wchar_t *packageName, int errorCode, int repairTriggerErrorCode)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001004c`
- `0x180040a30`

## callees

- `0x1800100d8`
- `0x1800104c0`
- `0x18001a08c`
- `0x180021fc4`
- `0x180041620`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x18001013c`
- `ntdll!EtwEventEnabled` at `0x18001013c`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800101f9`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800101f9`
- `ntdll!EtwEventWrite` at `0x1800101ea`
- `ntdll!EtwEventWrite` at `0x1800101ea`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18001016d`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18001018c`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18001016d`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18001018c`

## pseudocode

```c
int __fastcall Windows::Storage::StateABIHelpers::Logging::LogEvent(
        const _EVENT_DESCRIPTOR *eventDescriptor,
        const wchar_t *operation,
        const wchar_t *packageName,
        int errorCode,
        int repairTriggerErrorCode)
{
  int result; // eax
  ULONG v9; // ebx
  NTSTATUS v10; // eax
  NTSTATUS v11; // eax
  unsigned __int64 operationLength; // [rsp+20h] [rbp-60h] BYREF
  unsigned __int64 packageNameLength; // [rsp+28h] [rbp-58h] BYREF
  _EVENT_DATA_DESCRIPTOR eventData[4]; // [rsp+30h] [rbp-50h] BYREF
  int v15; // [rsp+C8h] [rbp+48h] BYREF

  v15 = errorCode;
  if ( !operation )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !packageName )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !v15 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  result = Windows::Storage::StateABIHelpers::Logging::AcquireLockAndInitLogging();
  v9 = result;
  if ( !result )
  {
    if ( (unsigned __int8)EtwEventEnabled(
                            Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle,
                            eventDescriptor) )
    {
      packageNameLength = 0;
      operationLength = 0;
      v10 = RtlStringCchLengthW(packageName, 0x7FFFFFFFu, &packageNameLength);
      v9 = RtlNtStatusToDosErrorNoTeb(v10);
      if ( !v9 )
      {
        v11 = RtlStringCchLengthW(operation, 0x7FFFFFFFu, &operationLength);
        v9 = RtlNtStatusToDosErrorNoTeb(v11);
        if ( !v9 )
        {
          eventData[0].Ptr = (unsigned __int64)operation;
          eventData[0].Reserved = 0;
          eventData[1].Ptr = (unsigned __int64)packageName;
          eventData[0].Size = 2 * operationLength + 2;
          eventData[1].Reserved = 0;
          *(_QWORD *)&eventData[2].Size = 4;
          *(_QWORD *)&eventData[3].Size = 4;
          eventData[1].Size = 2 * packageNameLength + 2;
          eventData[2].Ptr = (unsigned __int64)&v15;
          eventData[3].Ptr = (unsigned __int64)&repairTriggerErrorCode;
          v9 = EtwEventWrite(
                 Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle,
                 eventDescriptor,
                 4,
                 eventData);
        }
      }
    }
    RtlReleaseSRWLockShared(&Windows::Storage::StateABIHelpers::Logging::lock);
    return v9;
  }
  return result;
}

```

## disassembly

```asm
0x1800100d8  mov     [rsp-28h+arg_18], errorCode
0x1800100dd  push    rbp
0x1800100de  push    rbx
0x1800100df  push    rsi
0x1800100e0  push    rdi
0x1800100e1  push    r14
0x1800100e3  mov     rbp, rsp
0x1800100e6  sub     rsp, 80h
0x1800100ed  mov     rax, cs:__security_cookie
0x1800100f4  xor     rax, rsp
0x1800100f7  mov     [rbp+var_10], rax
0x1800100fb  mov     rdi, packageName
0x1800100fe  mov     rsi, operation
0x180010101  mov     r14, eventDescriptor
0x180010104  test    operation, operation
0x180010107  jnz     short loc_18001010E
0x180010109  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "operation != NULL")
0x18001010e  test    rdi, rdi
0x180010111  jnz     short loc_180010118
0x180010113  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "packageName != NULL")
0x180010118  cmp     [rbp+arg_18], 0
0x18001011c  jnz     short loc_180010123
0x18001011e  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "errorCode != ERROR_SUCCESS")
0x180010123  call    ?AcquireLockAndInitLogging@Logging@StateABIHelpers@Storage@Windows@@CAJXZ; Windows::Storage::StateABIHelpers::Logging::AcquireLockAndInitLogging(void)
0x180010128  mov     ebx, eax
0x18001012a  test    eax, eax
0x18001012c  jnz     loc_180010201
0x180010132  mov     eventDescriptor, cs:?eventRegisteredHandle@Logging@StateABIHelpers@Storage@Windows@@0_KA; unsigned __int64 Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle
0x180010139  mov     operation, r14
0x18001013c  call    cs:__imp_EtwEventEnabled
0x180010142  test    al, al
0x180010144  jz      loc_1800101F2
0x18001014a  lea     packageName, [rbp+packageNameLength]; pcchLength
0x18001014e  mov     [rbp+packageNameLength], 0
0x180010156  mov     edx, 7FFFFFFFh; cchMax
0x18001015b  mov     [rbp+operationLength], 0
0x180010163  mov     eventDescriptor, rdi; psz
0x180010166  call    ?RtlStringCchLengthW@@YAJPEBG_KPEA_K@Z; RtlStringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001016b  mov     ecx, eax; Status
0x18001016d  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180010173  mov     ebx, eax
0x180010175  test    eax, eax
0x180010177  jnz     short loc_1800101F2
0x180010179  lea     packageName, [rbp+operationLength]; pcchLength
0x18001017d  mov     edx, 7FFFFFFFh; cchMax
0x180010182  mov     eventDescriptor, rsi; psz
0x180010185  call    ?RtlStringCchLengthW@@YAJPEBG_KPEA_K@Z; RtlStringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001018a  mov     ecx, eax; Status
0x18001018c  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180010192  mov     ebx, eax
0x180010194  test    eax, eax
0x180010196  jnz     short loc_1800101F2
0x180010198  mov     eax, dword ptr [rbp+operationLength]
0x18001019b  lea     r8d, [rbx+4]
0x18001019f  mov     eventDescriptor, cs:?eventRegisteredHandle@Logging@StateABIHelpers@Storage@Windows@@0_KA; unsigned __int64 Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle
0x1800101a6  lea     r9, [rbp+eventData]
0x1800101aa  mov     operation, r14
0x1800101ad  mov     [rbp+eventData.Ptr], rsi
0x1800101b1  mov     dword ptr [rbp+eventData.___u2], ebx
0x1800101b4  lea     eax, ds:2[rax*2]
0x1800101bb  mov     [rbp+eventData.Ptr+10h], rdi
0x1800101bf  mov     [rbp+eventData.Size], eax
0x1800101c2  mov     eax, dword ptr [rbp+packageNameLength]
0x1800101c5  mov     dword ptr [rbp+eventData.___u2+10h], ebx
0x1800101c8  mov     qword ptr [rbp+eventData.Size+20h], packageName
0x1800101cc  mov     qword ptr [rbp+eventData.Size+30h], packageName
0x1800101d0  lea     eax, ds:2[rax*2]
0x1800101d7  mov     [rbp+eventData.Size+10h], eax
0x1800101da  lea     rax, [rbp+arg_18]
0x1800101de  mov     [rbp+eventData.Ptr+20h], rax
0x1800101e2  lea     rax, [rbp+arg_20]
0x1800101e6  mov     [rbp+eventData.Ptr+30h], rax
0x1800101ea  call    cs:__imp_EtwEventWrite
0x1800101f0  mov     ebx, eax
0x1800101f2  lea     eventDescriptor, ?lock@Logging@StateABIHelpers@Storage@Windows@@0U_RTL_SRWLOCK@@A; _RTL_SRWLOCK Windows::Storage::StateABIHelpers::Logging::lock
0x1800101f9  call    cs:__imp_RtlReleaseSRWLockShared
0x1800101ff  mov     eax, ebx
0x180010201  mov     eventDescriptor, [rbp+var_10]
0x180010205  xor     eventDescriptor, rsp; StackCookie
0x180010208  call    __security_check_cookie
0x18001020d  add     rsp, 80h
0x180010214  pop     r14
0x180010216  pop     rdi
0x180010217  pop     rsi
0x180010218  pop     rbx
0x180010219  pop     rbp
0x18001021a  retn
```
