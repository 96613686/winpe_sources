# Windows::Storage::StateABIHelpers::Logging::LogStateUpdateRequired(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,long)

- ea: `0x180010224`
- end: `0x18001034e`
- name: `?LogStateUpdateRequired@Logging@StateABIHelpers@Storage@Windows@@SAJPEBU_EVENT_DESCRIPTOR@@PEBG1J@Z`
- size: `298`
- prototype: `int __fastcall(const _EVENT_DESCRIPTOR *eventDescriptor, const wchar_t *packageFullName, const wchar_t *userSID, HRESULT hResult)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002491c`

## callees

- `0x180010224`
- `0x1800104c0`
- `0x18001a08c`
- `0x180021fc4`
- `0x180041620`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x18001027a`
- `ntdll!EtwEventEnabled` at `0x18001027a`
- `ntdll!RtlReleaseSRWLockShared` at `0x18001032f`
- `ntdll!RtlReleaseSRWLockShared` at `0x18001032f`
- `ntdll!EtwEventWrite` at `0x180010320`
- `ntdll!EtwEventWrite` at `0x180010320`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800102ab`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800102ca`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800102ab`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800102ca`

## pseudocode

```c
__int64 __fastcall Windows::Storage::StateABIHelpers::Logging::LogStateUpdateRequired(
        const _EVENT_DESCRIPTOR *eventDescriptor,
        const wchar_t *packageFullName,
        const wchar_t *userSID,
        HRESULT hResult)
{
  ULONG inited; // ebx
  NTSTATUS v8; // eax
  NTSTATUS v9; // eax
  unsigned __int64 packageNameLength; // [rsp+20h] [rbp-50h] BYREF
  unsigned __int64 userSIDLength; // [rsp+28h] [rbp-48h] BYREF
  _EVENT_DATA_DESCRIPTOR eventData[3]; // [rsp+30h] [rbp-40h] BYREF
  HRESULT v14; // [rsp+B8h] [rbp+48h] BYREF

  v14 = hResult;
  if ( !packageFullName )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !userSID )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  inited = Windows::Storage::StateABIHelpers::Logging::AcquireLockAndInitLogging();
  if ( !inited )
  {
    if ( (unsigned __int8)EtwEventEnabled(
                            Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle,
                            eventDescriptor) )
    {
      packageNameLength = 0;
      userSIDLength = 0;
      v8 = RtlStringCchLengthW(packageFullName, 0x7FFFFFFFu, &packageNameLength);
      inited = RtlNtStatusToDosErrorNoTeb(v8);
      if ( !inited )
      {
        v9 = RtlStringCchLengthW(userSID, 0x7FFFFFFFu, &userSIDLength);
        inited = RtlNtStatusToDosErrorNoTeb(v9);
        if ( !inited )
        {
          eventData[0].Ptr = (unsigned __int64)packageFullName;
          eventData[0].Reserved = 0;
          eventData[1].Ptr = (unsigned __int64)userSID;
          eventData[0].Size = 2 * packageNameLength + 2;
          eventData[1].Reserved = 0;
          *(_QWORD *)&eventData[2].Size = 4;
          eventData[1].Size = 2 * userSIDLength + 2;
          eventData[2].Ptr = (unsigned __int64)&v14;
          inited = EtwEventWrite(
                     Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle,
                     eventDescriptor,
                     3,
                     eventData);
        }
      }
    }
    RtlReleaseSRWLockShared(&Windows::Storage::StateABIHelpers::Logging::lock);
  }
  return inited;
}

```

## disassembly

```asm
0x180010224  mov     [rsp-28h+arg_18], hResult
0x180010229  push    rbp
0x18001022a  push    rbx
0x18001022b  push    rsi
0x18001022c  push    rdi
0x18001022d  push    r14
0x18001022f  mov     rbp, rsp
0x180010232  sub     rsp, 70h
0x180010236  mov     rax, cs:__security_cookie
0x18001023d  xor     rax, rsp
0x180010240  mov     [rbp+var_10], rax
0x180010244  mov     rdi, userSID
0x180010247  mov     rsi, packageFullName
0x18001024a  mov     r14, eventDescriptor
0x18001024d  test    packageFullName, packageFullName
0x180010250  jnz     short loc_180010257
0x180010252  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "packageFullName != NULL")
0x180010257  test    rdi, rdi
0x18001025a  jnz     short loc_180010261
0x18001025c  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "userSID != NULL")
0x180010261  call    ?AcquireLockAndInitLogging@Logging@StateABIHelpers@Storage@Windows@@CAJXZ; Windows::Storage::StateABIHelpers::Logging::AcquireLockAndInitLogging(void)
0x180010266  mov     ebx, eax
0x180010268  test    eax, eax
0x18001026a  jnz     loc_180010335
0x180010270  mov     eventDescriptor, cs:?eventRegisteredHandle@Logging@StateABIHelpers@Storage@Windows@@0_KA; unsigned __int64 Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle
0x180010277  mov     packageFullName, r14
0x18001027a  call    cs:__imp_EtwEventEnabled
0x180010280  test    al, al
0x180010282  jz      loc_180010328
0x180010288  lea     userSID, [rbp+packageNameLength]; pcchLength
0x18001028c  mov     [rbp+packageNameLength], 0
0x180010294  mov     edx, 7FFFFFFFh; cchMax
0x180010299  mov     [rbp+userSIDLength], 0
0x1800102a1  mov     eventDescriptor, rsi; psz
0x1800102a4  call    ?RtlStringCchLengthW@@YAJPEBG_KPEA_K@Z; RtlStringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800102a9  mov     ecx, eax; Status
0x1800102ab  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1800102b1  mov     ebx, eax
0x1800102b3  test    eax, eax
0x1800102b5  jnz     short loc_180010328
0x1800102b7  lea     userSID, [rbp+userSIDLength]; pcchLength
0x1800102bb  mov     edx, 7FFFFFFFh; cchMax
0x1800102c0  mov     eventDescriptor, rdi; psz
0x1800102c3  call    ?RtlStringCchLengthW@@YAJPEBG_KPEA_K@Z; RtlStringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800102c8  mov     ecx, eax; Status
0x1800102ca  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1800102d0  mov     ebx, eax
0x1800102d2  test    eax, eax
0x1800102d4  jnz     short loc_180010328
0x1800102d6  mov     eax, dword ptr [rbp+packageNameLength]
0x1800102d9  lea     r9, [rbp+eventData]
0x1800102dd  mov     eventDescriptor, cs:?eventRegisteredHandle@Logging@StateABIHelpers@Storage@Windows@@0_KA; unsigned __int64 Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle
0x1800102e4  lea     r8d, [rbx+3]
0x1800102e8  mov     packageFullName, r14
0x1800102eb  mov     [rbp+eventData.Ptr], rsi
0x1800102ef  mov     dword ptr [rbp+eventData.___u2], ebx
0x1800102f2  lea     eax, ds:2[rax*2]
0x1800102f9  mov     [rbp+eventData.Ptr+10h], rdi
0x1800102fd  mov     [rbp+eventData.Size], eax
0x180010300  mov     eax, dword ptr [rbp+userSIDLength]
0x180010303  mov     dword ptr [rbp+eventData.___u2+10h], ebx
0x180010306  mov     qword ptr [rbp+eventData.Size+20h], 4
0x18001030e  lea     eax, ds:2[rax*2]
0x180010315  mov     [rbp+eventData.Size+10h], eax
0x180010318  lea     rax, [rbp+arg_18]
0x18001031c  mov     [rbp+eventData.Ptr+20h], rax
0x180010320  call    cs:__imp_EtwEventWrite
0x180010326  mov     ebx, eax
0x180010328  lea     eventDescriptor, ?lock@Logging@StateABIHelpers@Storage@Windows@@0U_RTL_SRWLOCK@@A; _RTL_SRWLOCK Windows::Storage::StateABIHelpers::Logging::lock
0x18001032f  call    cs:__imp_RtlReleaseSRWLockShared
0x180010335  mov     eax, ebx
0x180010337  mov     eventDescriptor, [rbp+var_10]
0x18001033b  xor     eventDescriptor, rsp; StackCookie
0x18001033e  call    __security_check_cookie
0x180010343  add     rsp, 70h
0x180010347  pop     r14
0x180010349  pop     rdi
0x18001034a  pop     rsi
0x18001034b  pop     rbx
0x18001034c  pop     rbp
0x18001034d  retn
```
