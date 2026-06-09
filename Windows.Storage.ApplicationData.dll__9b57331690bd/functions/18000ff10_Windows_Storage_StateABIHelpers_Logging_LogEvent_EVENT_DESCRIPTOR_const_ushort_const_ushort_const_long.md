# Windows::Storage::StateABIHelpers::Logging::LogEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,long)

- ea: `0x18000ff10`
- end: `0x180010045`
- name: `?LogEvent@Logging@StateABIHelpers@Storage@Windows@@CAJPEBU_EVENT_DESCRIPTOR@@PEBG1J@Z`
- size: `309`
- prototype: `int __fastcall(const _EVENT_DESCRIPTOR *eventDescriptor, const wchar_t *packageName, const wchar_t *folderName, int errorCode)`
- caller_count: `5`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180029ad8`
- `0x180029bfc`
- `0x180040d44`
- `0x180040e54`
- `0x180040f68`

## callees

- `0x18000ff10`
- `0x1800104c0`
- `0x18001a08c`
- `0x180021fc4`
- `0x180041620`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x18000ff71`
- `ntdll!EtwEventEnabled` at `0x18000ff71`
- `ntdll!RtlReleaseSRWLockShared` at `0x180010026`
- `ntdll!RtlReleaseSRWLockShared` at `0x180010026`
- `ntdll!EtwEventWrite` at `0x180010017`
- `ntdll!EtwEventWrite` at `0x180010017`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18000ffa2`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18000ffc1`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18000ffa2`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18000ffc1`

## pseudocode

```c
int __fastcall Windows::Storage::StateABIHelpers::Logging::LogEvent(
        const _EVENT_DESCRIPTOR *eventDescriptor,
        const wchar_t *packageName,
        const wchar_t *folderName,
        int errorCode)
{
  int result; // eax
  ULONG v8; // ebx
  NTSTATUS v9; // eax
  NTSTATUS v10; // eax
  unsigned __int64 packageNameLength; // [rsp+20h] [rbp-50h] BYREF
  unsigned __int64 folderNameLength; // [rsp+28h] [rbp-48h] BYREF
  _EVENT_DATA_DESCRIPTOR eventData[3]; // [rsp+30h] [rbp-40h] BYREF
  int v14; // [rsp+B8h] [rbp+48h] BYREF

  v14 = errorCode;
  if ( !packageName )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !folderName )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !v14 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  result = Windows::Storage::StateABIHelpers::Logging::AcquireLockAndInitLogging();
  v8 = result;
  if ( !result )
  {
    if ( (unsigned __int8)EtwEventEnabled(
                            Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle,
                            eventDescriptor) )
    {
      packageNameLength = 0;
      folderNameLength = 0;
      v9 = RtlStringCchLengthW(packageName, 0x7FFFFFFFu, &packageNameLength);
      v8 = RtlNtStatusToDosErrorNoTeb(v9);
      if ( !v8 )
      {
        v10 = RtlStringCchLengthW(folderName, 0x7FFFFFFFu, &folderNameLength);
        v8 = RtlNtStatusToDosErrorNoTeb(v10);
        if ( !v8 )
        {
          eventData[0].Ptr = (unsigned __int64)packageName;
          eventData[0].Reserved = 0;
          eventData[1].Ptr = (unsigned __int64)folderName;
          eventData[0].Size = 2 * packageNameLength + 2;
          eventData[1].Reserved = 0;
          *(_QWORD *)&eventData[2].Size = 4;
          eventData[1].Size = 2 * folderNameLength + 2;
          eventData[2].Ptr = (unsigned __int64)&v14;
          v8 = EtwEventWrite(
                 Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle,
                 eventDescriptor,
                 3,
                 eventData);
        }
      }
    }
    RtlReleaseSRWLockShared(&Windows::Storage::StateABIHelpers::Logging::lock);
    return v8;
  }
  return result;
}

```

## disassembly

```asm
0x18000ff10  mov     [rsp-28h+arg_18], errorCode
0x18000ff15  push    rbp
0x18000ff16  push    rbx
0x18000ff17  push    rsi
0x18000ff18  push    rdi
0x18000ff19  push    r14
0x18000ff1b  mov     rbp, rsp
0x18000ff1e  sub     rsp, 70h
0x18000ff22  mov     rax, cs:__security_cookie
0x18000ff29  xor     rax, rsp
0x18000ff2c  mov     [rbp+var_10], rax
0x18000ff30  mov     rdi, folderName
0x18000ff33  mov     rsi, packageName
0x18000ff36  mov     r14, eventDescriptor
0x18000ff39  test    packageName, packageName
0x18000ff3c  jnz     short loc_18000FF43
0x18000ff3e  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "packageName != NULL")
0x18000ff43  test    rdi, rdi
0x18000ff46  jnz     short loc_18000FF4D
0x18000ff48  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "folderName != NULL")
0x18000ff4d  cmp     [rbp+arg_18], 0
0x18000ff51  jnz     short loc_18000FF58
0x18000ff53  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "errorCode != ERROR_SUCCESS")
0x18000ff58  call    ?AcquireLockAndInitLogging@Logging@StateABIHelpers@Storage@Windows@@CAJXZ; Windows::Storage::StateABIHelpers::Logging::AcquireLockAndInitLogging(void)
0x18000ff5d  mov     ebx, eax
0x18000ff5f  test    eax, eax
0x18000ff61  jnz     loc_18001002E
0x18000ff67  mov     eventDescriptor, cs:?eventRegisteredHandle@Logging@StateABIHelpers@Storage@Windows@@0_KA; unsigned __int64 Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle
0x18000ff6e  mov     packageName, r14
0x18000ff71  call    cs:__imp_EtwEventEnabled
0x18000ff77  test    al, al
0x18000ff79  jz      loc_18001001F
0x18000ff7f  lea     folderName, [rbp+packageNameLength]; pcchLength
0x18000ff83  mov     [rbp+packageNameLength], 0
0x18000ff8b  mov     edx, 7FFFFFFFh; cchMax
0x18000ff90  mov     [rbp+folderNameLength], 0
0x18000ff98  mov     eventDescriptor, rsi; psz
0x18000ff9b  call    ?RtlStringCchLengthW@@YAJPEBG_KPEA_K@Z; RtlStringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000ffa0  mov     ecx, eax; Status
0x18000ffa2  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18000ffa8  mov     ebx, eax
0x18000ffaa  test    eax, eax
0x18000ffac  jnz     short loc_18001001F
0x18000ffae  lea     folderName, [rbp+folderNameLength]; pcchLength
0x18000ffb2  mov     edx, 7FFFFFFFh; cchMax
0x18000ffb7  mov     eventDescriptor, rdi; psz
0x18000ffba  call    ?RtlStringCchLengthW@@YAJPEBG_KPEA_K@Z; RtlStringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000ffbf  mov     ecx, eax; Status
0x18000ffc1  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18000ffc7  mov     ebx, eax
0x18000ffc9  test    eax, eax
0x18000ffcb  jnz     short loc_18001001F
0x18000ffcd  mov     eax, dword ptr [rbp+packageNameLength]
0x18000ffd0  lea     r9, [rbp+eventData]
0x18000ffd4  mov     eventDescriptor, cs:?eventRegisteredHandle@Logging@StateABIHelpers@Storage@Windows@@0_KA; unsigned __int64 Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle
0x18000ffdb  lea     r8d, [rbx+3]
0x18000ffdf  mov     packageName, r14
0x18000ffe2  mov     [rbp+eventData.Ptr], rsi
0x18000ffe6  mov     dword ptr [rbp+eventData.___u2], ebx
0x18000ffe9  lea     eax, ds:2[rax*2]
0x18000fff0  mov     [rbp+eventData.Ptr+10h], rdi
0x18000fff4  mov     [rbp+eventData.Size], eax
0x18000fff7  mov     eax, dword ptr [rbp+folderNameLength]
0x18000fffa  mov     dword ptr [rbp+eventData.___u2+10h], ebx
0x18000fffd  mov     qword ptr [rbp+eventData.Size+20h], 4
0x180010005  lea     eax, ds:2[rax*2]
0x18001000c  mov     [rbp+eventData.Size+10h], eax
0x18001000f  lea     rax, [rbp+arg_18]
0x180010013  mov     [rbp+eventData.Ptr+20h], rax
0x180010017  call    cs:__imp_EtwEventWrite
0x18001001d  mov     ebx, eax
0x18001001f  lea     eventDescriptor, ?lock@Logging@StateABIHelpers@Storage@Windows@@0U_RTL_SRWLOCK@@A; _RTL_SRWLOCK Windows::Storage::StateABIHelpers::Logging::lock
0x180010026  call    cs:__imp_RtlReleaseSRWLockShared
0x18001002c  mov     eax, ebx
0x18001002e  mov     eventDescriptor, [rbp+var_10]
0x180010032  xor     eventDescriptor, rsp; StackCookie
0x180010035  call    __security_check_cookie
0x18001003a  add     rsp, 70h
0x18001003e  pop     r14
0x180010040  pop     rdi
0x180010041  pop     rsi
0x180010042  pop     rbx
0x180010043  pop     rbp
0x180010044  retn
```
