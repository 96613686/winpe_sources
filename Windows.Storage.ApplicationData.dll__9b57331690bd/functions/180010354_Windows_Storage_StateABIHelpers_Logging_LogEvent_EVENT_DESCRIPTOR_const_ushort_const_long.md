# Windows::Storage::StateABIHelpers::Logging::LogEvent(_EVENT_DESCRIPTOR const *,ushort const *,long)

- ea: `0x180010354`
- end: `0x1800104b5`
- name: `?LogEvent@Logging@StateABIHelpers@Storage@Windows@@CAJPEBU_EVENT_DESCRIPTOR@@PEBGJ@Z`
- size: `353`
- prototype: `int __fastcall(const _EVENT_DESCRIPTOR *eventDescriptor, const wchar_t *logString, int errorCode)`
- caller_count: `5`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180019500`
- `0x1800235c4`
- `0x180040abc`
- `0x180040c10`
- `0x180040ccc`

## callees

- `0x180010354`
- `0x1800104c0`
- `0x180021fc4`
- `0x180041620`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x1800103ae`
- `ntdll!EtwEventEnabled` at `0x1800103ae`
- `ntdll!RtlReleaseSRWLockShared` at `0x180010462`
- `ntdll!RtlReleaseSRWLockShared` at `0x180010462`
- `ntdll!EtwEventWrite` at `0x180010453`
- `ntdll!EtwEventWrite` at `0x180010453`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180010409`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180010409`

## pseudocode

```c
int __fastcall Windows::Storage::StateABIHelpers::Logging::LogEvent(
        const _EVENT_DESCRIPTOR *eventDescriptor,
        const wchar_t *logString,
        int errorCode)
{
  int result; // eax
  ULONG v6; // ebx
  const wchar_t *v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rsi
  NTSTATUS v10; // edx
  _EVENT_DATA_DESCRIPTOR eventData[2]; // [rsp+20h] [rbp-48h] BYREF
  int v12; // [rsp+80h] [rbp+18h] BYREF

  v12 = errorCode;
  if ( !logString )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    errorCode = v12;
  }
  if ( !errorCode )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  result = Windows::Storage::StateABIHelpers::Logging::AcquireLockAndInitLogging();
  v6 = result;
  if ( !result )
  {
    if ( !(unsigned __int8)EtwEventEnabled(
                             Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle,
                             eventDescriptor) )
    {
LABEL_14:
      RtlReleaseSRWLockShared(&Windows::Storage::StateABIHelpers::Logging::lock);
      return v6;
    }
    if ( logString )
    {
      v7 = logString;
      v8 = 0x7FFFFFFF;
      do
      {
        if ( !*v7 )
          break;
        ++v7;
        --v8;
      }
      while ( v8 );
      v9 = (0x7FFFFFFF - v8) & -(__int64)(v8 != 0);
      v10 = v8 == 0 ? 0xC000000D : 0;
      if ( v8 )
        goto LABEL_12;
    }
    else
    {
      v10 = -1073741811;
    }
    LODWORD(v9) = 0;
LABEL_12:
    v6 = RtlNtStatusToDosErrorNoTeb(v10);
    if ( !v6 )
    {
      eventData[0].Size = 2 * v9 + 2;
      eventData[0].Ptr = (unsigned __int64)logString;
      eventData[1].Ptr = (unsigned __int64)&v12;
      eventData[0].Reserved = 0;
      *(_QWORD *)&eventData[1].Size = 4;
      v6 = EtwEventWrite(
             Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle,
             eventDescriptor,
             2,
             eventData);
    }
    goto LABEL_14;
  }
  return result;
}

```

## disassembly

```asm
0x180010354  mov     [rsp+arg_8], rbx
0x180010359  mov     [rsp+arg_18], rbp
0x18001035e  mov     [rsp+arg_10], errorCode
0x180010363  push    rsi
0x180010364  push    rdi
0x180010365  push    r14
0x180010367  sub     rsp, 50h
0x18001036b  mov     rax, cs:__security_cookie
0x180010372  xor     rax, rsp
0x180010375  mov     [rsp+68h+var_28], rax
0x18001037a  xor     r14d, r14d
0x18001037d  mov     rdi, logString
0x180010380  mov     rbp, eventDescriptor
0x180010383  test    logString, logString
0x180010386  jz      loc_18001048C
0x18001038c  test    errorCode, errorCode
0x18001038f  jz      loc_18001049E
0x180010395  call    ?AcquireLockAndInitLogging@Logging@StateABIHelpers@Storage@Windows@@CAJXZ; Windows::Storage::StateABIHelpers::Logging::AcquireLockAndInitLogging(void)
0x18001039a  mov     ebx, eax
0x18001039c  test    eax, eax
0x18001039e  jnz     loc_18001046A
0x1800103a4  mov     eventDescriptor, cs:?eventRegisteredHandle@Logging@StateABIHelpers@Storage@Windows@@0_KA; unsigned __int64 Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle
0x1800103ab  mov     logString, rbp
0x1800103ae  call    cs:__imp_EtwEventEnabled
0x1800103b4  test    al, al
0x1800103b6  jz      loc_18001045B
0x1800103bc  test    rdi, rdi
0x1800103bf  jz      loc_1800104A8
0x1800103c5  mov     edx, 7FFFFFFFh
0x1800103ca  mov     rax, rdi
0x1800103cd  mov     ecx, edx
0x1800103cf  cmp     [rax], r14w
0x1800103d3  jz      short loc_1800103DF
0x1800103d5  add     rax, 2
0x1800103d9  sub     eventDescriptor, 1
0x1800103dd  jnz     short loc_1800103CF
0x1800103df  sub     logString, eventDescriptor
0x1800103e2  mov     rax, eventDescriptor
0x1800103e5  neg     rax
0x1800103e8  mov     rax, eventDescriptor
0x1800103eb  sbb     rsi, rsi
0x1800103ee  and     rsi, logString
0x1800103f1  neg     rax
0x1800103f4  sbb     edx, edx
0x1800103f6  not     edx
0x1800103f8  and     edx, 0C000000Dh
0x1800103fe  test    eventDescriptor, eventDescriptor
0x180010401  jz      loc_1800104AD
0x180010407  mov     ecx, edx; Status
0x180010409  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18001040f  mov     ebx, eax
0x180010411  test    eax, eax
0x180010413  jnz     short loc_18001045B
0x180010415  mov     eventDescriptor, cs:?eventRegisteredHandle@Logging@StateABIHelpers@Storage@Windows@@0_KA; unsigned __int64 Windows::Storage::StateABIHelpers::Logging::eventRegisteredHandle
0x18001041c  lea     eax, ds:2[rsi*2]
0x180010423  mov     [rsp+68h+eventData.Size], eax
0x180010427  lea     r9, [rsp+68h+eventData]
0x18001042c  lea     rax, [rsp+68h+arg_10]
0x180010434  mov     [rsp+68h+eventData.Ptr], rdi
0x180010439  lea     errorCode, [rbx+2]
0x18001043d  mov     [rsp+68h+eventData.Ptr+10h], rax
0x180010442  mov     logString, rbp
0x180010445  mov     dword ptr [rsp+68h+eventData.___u2], r14d
0x18001044a  mov     qword ptr [rsp+68h+eventData.Size+10h], 4
0x180010453  call    cs:__imp_EtwEventWrite
0x180010459  mov     ebx, eax
0x18001045b  lea     eventDescriptor, ?lock@Logging@StateABIHelpers@Storage@Windows@@0U_RTL_SRWLOCK@@A; _RTL_SRWLOCK Windows::Storage::StateABIHelpers::Logging::lock
0x180010462  call    cs:__imp_RtlReleaseSRWLockShared
0x180010468  mov     eax, ebx
0x18001046a  mov     eventDescriptor, [rsp+68h+var_28]
0x18001046f  xor     eventDescriptor, rsp; StackCookie
0x180010472  call    __security_check_cookie
0x180010477  lea     r11, [rsp+68h+var_18]
0x18001047c  mov     rbx, [r11+28h]
0x180010480  mov     rbp, [r11+38h]
0x180010484  mov     rsp, r11
0x180010487  pop     r14
0x180010489  pop     rdi
0x18001048a  pop     rsi
0x18001048b  retn
0x18001048c  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "logString != NULL")
0x180010491  mov     errorCode, [rsp+68h+arg_10]
0x180010499  jmp     loc_18001038C
0x18001049e  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "errorCode != ERROR_SUCCESS")
0x1800104a3  jmp     loc_180010395
0x1800104a8  mov     edx, 0C000000Dh
0x1800104ad  mov     rsi, r14
0x1800104b0  jmp     loc_180010407
```
