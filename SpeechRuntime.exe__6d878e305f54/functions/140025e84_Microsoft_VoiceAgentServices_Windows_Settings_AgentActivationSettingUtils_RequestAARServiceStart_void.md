# Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingUtils::RequestAARServiceStart(void)

- ea: `0x140025e84`
- end: `0x140025f82`
- name: `?RequestAARServiceStart@AgentActivationSettingUtils@Settings@Windows@VoiceAgentServices@Microsoft@@SAJXZ`
- size: `254`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14002c660`

## callees

- `0x140002d30`
- `0x14000aab8`
- `0x14000c32c`
- `0x14000e030`
- `0x140012724`
- `0x140025e84`
- `0x140031010`

## string_xrefs

- `0x140025ee8`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingutils.cpp`
- `0x140025f33`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingutils.cpp`
- `0x140025ebe`: `Windows.ApplicationModel.ConversationalAgent.Internal.ConversationalAgentSessionInternal`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingUtils::RequestAARServiceStart(void)
{
  int v0; // eax
  unsigned int v1; // ebx
  __int64 v2; // rdi
  __int64 (__fastcall *v3)(__int64, __int64 *); // rbx
  int v4; // eax
  __int64 v6; // [rsp+20h] [rbp-40h] BYREF
  __int64 v7; // [rsp+28h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-30h] BYREF
  __int64 v9; // [rsp+48h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  v7 = 0;
  v9 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.ApplicationModel.ConversationalAgent.Internal.ConversationalAgentSessionInternal",
    0x59u,
    0x58u);
  v0 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<IActivationFactory>>(v9, &v7);
  v1 = v0;
  if ( v0 >= 0 )
  {
    v6 = 0;
    v2 = v7;
    v3 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v7 + 48LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v6);
    v4 = v3(v2, &v6);
    v1 = v4;
    if ( v4 >= 0 )
    {
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v6);
      v1 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBB,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingutils.cpp",
        (const char *)(unsigned int)v4,
        v6);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v6);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB8,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingutils.cpp",
      (const char *)(unsigned int)v0,
      v6);
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v7);
  return v1;
}

```

## disassembly

```asm
0x140025e84  mov     [rsp-8+arg_0], rbx
0x140025e89  mov     [rsp-8+arg_8], rdi
0x140025e8e  push    rbp
0x140025e8f  mov     rbp, rsp
0x140025e92  sub     rsp, 60h
0x140025e96  mov     rax, cs:__security_cookie
0x140025e9d  xor     rax, rsp
0x140025ea0  mov     [rbp+var_10], rax
0x140025ea4  mov     [rbp+var_38], 0
0x140025eac  mov     [rbp+var_18], 0
0x140025eb4  mov     r9d, 58h ; 'X'; unsigned int
0x140025eba  lea     r8d, [r9+1]; unsigned int
0x140025ebe  lea     rdx, ?RuntimeClass_Windows_ApplicationModel_ConversationalAgent_Internal_ConversationalAgentSessionInternal@@3QBGB; "Windows.ApplicationModel.Conversational"...
0x140025ec5  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x140025ec9  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x140025ece  lea     rdx, [rbp+var_38]
0x140025ed2  mov     rcx, [rbp+var_18]
0x140025ed6  call    ??$GetActivationFactory@V?$ComPtr@UIActivationFactory@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIActivationFactory@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<IActivationFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IActivationFactory>>)
0x140025edb  mov     ebx, eax
0x140025edd  test    eax, eax
0x140025edf  jns     short loc_140025EFB
0x140025ee1  mov     rcx, [rbp+8]; this
0x140025ee5  mov     r9d, eax; char *
0x140025ee8  lea     r8, aOnecoreuapEndu_42; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140025eef  mov     edx, 0B8h; void *
0x140025ef4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140025ef9  jmp     short loc_140025F5B
0x140025efb  mov     [rbp+var_40], 0
0x140025f03  mov     rdi, [rbp+var_38]
0x140025f07  mov     rax, [rdi]
0x140025f0a  mov     rbx, [rax+30h]
0x140025f0e  lea     rcx, [rbp+var_40]
0x140025f12  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x140025f17  lea     rdx, [rbp+var_40]
0x140025f1b  mov     rcx, rdi
0x140025f1e  mov     rax, rbx
0x140025f21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025f26  mov     ebx, eax
0x140025f28  test    eax, eax
0x140025f2a  jns     short loc_140025F50
0x140025f2c  mov     rcx, [rbp+8]; this
0x140025f30  mov     r9d, eax; char *
0x140025f33  lea     r8, aOnecoreuapEndu_42; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140025f3a  mov     edx, 0BBh; void *
0x140025f3f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140025f44  nop
0x140025f45  lea     rcx, [rbp+var_40]
0x140025f49  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x140025f4e  jmp     short loc_140025F5B
0x140025f50  lea     rcx, [rbp+var_40]
0x140025f54  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x140025f59  xor     ebx, ebx
0x140025f5b  lea     rcx, [rbp+var_38]
0x140025f5f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x140025f64  mov     eax, ebx
0x140025f66  mov     rcx, [rbp+var_10]
0x140025f6a  xor     rcx, rsp; StackCookie
0x140025f6d  call    __security_check_cookie
0x140025f72  mov     rbx, [rsp+60h+arg_0]
0x140025f77  mov     rdi, [rsp+60h+arg_8]
0x140025f7c  add     rsp, 60h
0x140025f80  pop     rbp
0x140025f81  retn
```
