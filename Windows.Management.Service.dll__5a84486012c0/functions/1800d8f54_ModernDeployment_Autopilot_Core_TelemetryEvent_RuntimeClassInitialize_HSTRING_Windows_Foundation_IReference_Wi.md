# ModernDeployment::Autopilot::Core::TelemetryEvent::RuntimeClassInitialize(HSTRING__ *,Windows::Foundation::IReference<Windows::Foundation::DateTime> *)

- ea: `0x1800d8f54`
- end: `0x1800d9157`
- name: `?RuntimeClassInitialize@TelemetryEvent@Core@Autopilot@ModernDeployment@@QEAAJPEAUHSTRING__@@PEAU?$IReference@UDateTime@Foundation@Windows@@@Foundation@Windows@@@Z`
- size: `515`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18006afb0`

## callees

- `0x18000b820`
- `0x180067a54`
- `0x1800775c4`
- `0x1800aa0d4`
- `0x1800d8c80`
- `0x1800d8f54`
- `0x1801fa010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800d90d7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800d90d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800d90be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800d90be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d8fc2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d8fc2`

## string_xrefs

- `0x1800d8f9e`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\telemetryevent.cpp`
- `0x1800d8ff9`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\telemetryevent.cpp`
- `0x1800d9023`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\telemetryevent.cpp`
- `0x1800d9063`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\telemetryevent.cpp`
- `0x1800d90f9`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\telemetryevent.cpp`
- `0x1800d911f`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\telemetryevent.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall ModernDeployment::Autopilot::Core::TelemetryEvent::RuntimeClassInitialize(
        __int64 a1,
        HSTRING a2,
        __int64 a3)
{
  PCWSTR StringRawBuffer; // rax
  int v8; // eax
  unsigned int v9; // edi
  __int64 v10; // rcx
  int v11; // eax
  unsigned int v12; // ebx
  UINT32 length; // [rsp+20h] [rbp-58h] BYREF
  __int64 v14; // [rsp+28h] [rbp-50h] BYREF
  HSTRING v15; // [rsp+30h] [rbp-48h] BYREF
  HSTRING string; // [rsp+38h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v15 = a2;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::GetImpl'::`2'::impl) )
  {
    length = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(a2, &length);
    if ( length && *StringRawBuffer )
    {
      v8 = Microsoft::WRL::Wrappers::HString::Set((HSTRING *)(a1 + 32), &v15);
      v9 = v8;
      if ( v8 >= 0 )
      {
        if ( a3 )
        {
          v14 = 0;
          if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a3 + 48LL))(a3, &v14) >= 0 )
          {
            *(_QWORD *)(a1 + 40) = v14;
            if ( !*(_BYTE *)(a1 + 48) )
              *(_BYTE *)(a1 + 48) = 1;
            v10 = *(_QWORD *)(a1 + 56);
            *(_QWORD *)(a1 + 56) = 0;
            if ( v10 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
            if ( WindowsCreateStringReference(
                   L"Windows.Foundation.Collections.StringMap",
                   0x28u,
                   &hstringHeader,
                   &string) < 0 )
              RaiseException(0xC000000D, 1u, 0, 0);
            v11 = Windows::Foundation::ActivateInstance<Windows::Foundation::Collections::IMap<HSTRING__ *,HSTRING__ *>>(
                    string,
                    a1 + 56);
            v12 = v11;
            if ( v11 >= 0 )
            {
              return 0;
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1A,
                (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\telemetryevent.cpp",
                (const char *)(unsigned int)v11,
                length);
              return v12;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x17,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\telemetryevent.cpp",
              (const char *)0x80070057LL,
              length);
            return 2147942487LL;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x15,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\telemetryevent.cpp",
            (const char *)0x80070057LL,
            length);
          return 2147942487LL;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x13,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\telemetryevent.cpp",
          (const char *)(unsigned int)v8,
          length);
        return v9;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x12,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\telemetryevent.cpp",
        (const char *)0x80070057LL,
        length);
      return 2147942487LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\telemetryevent.cpp",
      (const char *)0x80004001LL,
      length);
    return 2147500033LL;
  }
}

```

## disassembly

```asm
0x1800d8f54  mov     [rsp+arg_18], rbx
0x1800d8f59  push    rsi
0x1800d8f5a  push    rdi
0x1800d8f5b  push    r14
0x1800d8f5d  sub     rsp, 60h
0x1800d8f61  mov     rax, cs:__security_cookie
0x1800d8f68  xor     rax, rsp
0x1800d8f6b  mov     [rsp+78h+var_20], rax
0x1800d8f70  mov     rsi, r8
0x1800d8f73  mov     rdi, rdx
0x1800d8f76  mov     rbx, rcx
0x1800d8f79  mov     [rsp+78h+var_48], rdx
0x1800d8f7e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry> `wil::Feature<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::GetImpl(void)'::`2'::impl
0x1800d8f85  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::__private_IsEnabled(void)
0x1800d8f8a  xor     r14d, r14d
0x1800d8f8d  test    al, al
0x1800d8f8f  jnz     short loc_1800D8FB5
0x1800d8f91  mov     rcx, [rsp+78h]; this
0x1800d8f96  mov     ebx, 80004001h
0x1800d8f9b  mov     r9d, ebx; char *
0x1800d8f9e  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800d8fa5  lea     edx, [r14+0Eh]; void *
0x1800d8fa9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d8fae  mov     eax, ebx
0x1800d8fb0  jmp     loc_1800D9138
0x1800d8fb5  mov     [rsp+78h+length], r14d; int
0x1800d8fba  lea     rdx, [rsp+78h+length]; length
0x1800d8fbf  mov     rcx, rdi; string
0x1800d8fc2  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d8fc8  cmp     [rsp+78h+length], r14d
0x1800d8fcd  jz      loc_1800D9112
0x1800d8fd3  cmp     [rax], r14w
0x1800d8fd7  jz      loc_1800D9112
0x1800d8fdd  lea     rcx, [rbx+20h]; newString
0x1800d8fe1  lea     rdx, [rsp+78h+var_48]; HSTRING *
0x1800d8fe6  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x1800d8feb  mov     edi, eax
0x1800d8fed  test    eax, eax
0x1800d8fef  jns     short loc_1800D9011
0x1800d8ff1  mov     rcx, [rsp+78h]; this
0x1800d8ff6  mov     r9d, eax; char *
0x1800d8ff9  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800d9000  mov     edx, 13h; void *
0x1800d9005  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d900a  mov     eax, edi
0x1800d900c  jmp     loc_1800D9138
0x1800d9011  test    rsi, rsi
0x1800d9014  jnz     short loc_1800D9039
0x1800d9016  mov     rcx, [rsp+78h]; this
0x1800d901b  mov     ebx, 80070057h
0x1800d9020  mov     r9d, ebx; char *
0x1800d9023  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800d902a  lea     edx, [rsi+15h]; void *
0x1800d902d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d9032  mov     eax, ebx
0x1800d9034  jmp     loc_1800D9138
0x1800d9039  mov     [rsp+78h+var_50], r14
0x1800d903e  mov     rax, [rsi]
0x1800d9041  lea     rdx, [rsp+78h+var_50]
0x1800d9046  mov     rcx, rsi
0x1800d9049  mov     rax, [rax+30h]
0x1800d904d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d9052  test    eax, eax
0x1800d9054  jns     short loc_1800D907B
0x1800d9056  mov     rcx, [rsp+78h]; this
0x1800d905b  mov     ebx, 80070057h
0x1800d9060  mov     r9d, ebx; char *
0x1800d9063  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800d906a  mov     edx, 17h; void *
0x1800d906f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d9074  mov     eax, ebx
0x1800d9076  jmp     loc_1800D9138
0x1800d907b  mov     rax, [rsp+78h+var_50]
0x1800d9080  mov     [rbx+28h], rax
0x1800d9084  cmp     [rbx+30h], r14b
0x1800d9088  jnz     short loc_1800D908E
0x1800d908a  mov     byte ptr [rbx+30h], 1
0x1800d908e  mov     rcx, [rbx+38h]
0x1800d9092  mov     [rbx+38h], r14
0x1800d9096  test    rcx, rcx
0x1800d9099  jz      short loc_1800D90A8
0x1800d909b  mov     rax, [rcx]
0x1800d909e  mov     rax, [rax+10h]
0x1800d90a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d90a7  nop
0x1800d90a8  lea     r9, [rsp+78h+string]; string
0x1800d90ad  lea     r8, [rsp+78h+hstringHeader]; hstringHeader
0x1800d90b2  mov     edx, 28h ; '('; length
0x1800d90b7  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_StringMap@@3QBGB; "Windows.Foundation.Collections.StringMa"...
0x1800d90be  call    cs:__imp_WindowsCreateStringReference
0x1800d90c4  test    eax, eax
0x1800d90c6  jns     short loc_1800D90DD
0x1800d90c8  xor     r9d, r9d; lpArguments
0x1800d90cb  xor     r8d, r8d; nNumberOfArguments
0x1800d90ce  lea     edx, [r9+1]; dwExceptionFlags
0x1800d90d2  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800d90d7  call    cs:__imp_RaiseException
0x1800d90dd  lea     rdx, [rbx+38h]
0x1800d90e1  mov     rcx, [rsp+78h+string]
0x1800d90e6  call    ??$ActivateInstance@U?$IMap@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAU?$IMap@PEAUHSTRING__@@PEAU1@@Collections@01@@Z; Windows::Foundation::ActivateInstance<Windows::Foundation::Collections::IMap<HSTRING__ *,HSTRING__ *>>(HSTRING__ *,Windows::Foundation::Collections::IMap<HSTRING__ *,HSTRING__ *> * *)
0x1800d90eb  mov     ebx, eax
0x1800d90ed  test    eax, eax
0x1800d90ef  jns     short loc_1800D910E
0x1800d90f1  mov     rcx, [rsp+78h]; this
0x1800d90f6  mov     r9d, eax; char *
0x1800d90f9  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800d9100  mov     edx, 1Ah; void *
0x1800d9105  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d910a  mov     eax, ebx
0x1800d910c  jmp     short loc_1800D9138
0x1800d910e  xor     eax, eax
0x1800d9110  jmp     short loc_1800D9138
0x1800d9112  mov     rcx, [rsp+78h]; this
0x1800d9117  mov     ebx, 80070057h
0x1800d911c  mov     r9d, ebx; char *
0x1800d911f  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800d9126  mov     edx, 12h; void *
0x1800d912b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d9130  mov     eax, ebx
0x1800d9132  jmp     short loc_1800D9138
0x1800d9134  mov     eax, [rsp+78h+length]
0x1800d9138  mov     rcx, [rsp+78h+var_20]
0x1800d913d  xor     rcx, rsp; StackCookie
0x1800d9140  call    __security_check_cookie
0x1800d9145  mov     rbx, [rsp+78h+arg_18]
0x1800d914d  add     rsp, 60h
0x1800d9151  pop     r14
0x1800d9153  pop     rdi
0x1800d9154  pop     rsi
0x1800d9155  retn
```
