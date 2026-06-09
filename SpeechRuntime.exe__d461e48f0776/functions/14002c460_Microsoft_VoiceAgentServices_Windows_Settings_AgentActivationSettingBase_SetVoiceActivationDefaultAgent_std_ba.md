# Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::SetVoiceActivationDefaultAgent(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x14002c460`
- end: `0x14002c64c`
- name: `?SetVoiceActivationDefaultAgent@AgentActivationSettingBase@Settings@Windows@VoiceAgentServices@Microsoft@@UEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `492`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140002d30`
- `0x14000e030`
- `0x14001296c`
- `0x140012d68`
- `0x140020208`
- `0x140020ff0`
- `0x1400210dc`
- `0x140021658`
- `0x140027f90`
- `0x14002c320`
- `0x14002c460`
- `0x140031010`

## string_xrefs

- `0x14002c4ba`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x14002c577`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x14002c5d3`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x14002c4a9`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::SetVoiceActivationDefaultAgent`
- `0x14002c5c0`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::SetVoiceActivationDefaultAgent`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::SetVoiceActivationDefaultAgent(
        __int64 a1,
        __int64 a2)
{
  __int64 v4; // r12
  __int64 v5; // rdi
  void (__fastcall *v6)(__int64, _BYTE *, _BYTE *, __int64); // rbx
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rdx
  int v10; // r8d
  const unsigned __int16 *v11; // rax
  HKEY v12; // rcx
  const unsigned __int16 *v13; // r8
  const unsigned __int16 *v14; // r9
  __int64 v15; // r14
  void (__fastcall *v16)(__int64, __int64, __int64, __int64, __int64, __int64, _QWORD); // rsi
  __int64 v17; // rdi
  __int64 v18; // rbx
  __int64 v19; // rax
  _QWORD v21[3]; // [rsp+40h] [rbp-79h] BYREF
  _BYTE v22[32]; // [rsp+58h] [rbp-61h] BYREF
  __int64 v23; // [rsp+78h] [rbp-41h]
  _BYTE v24[32]; // [rsp+80h] [rbp-39h] BYREF
  _BYTE v25[32]; // [rsp+A0h] [rbp-19h] BYREF
  _BYTE v26[32]; // [rsp+C0h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v23 = a2;
  v4 = a1 - 8;
  v5 = *(_QWORD *)(a1 - 8 + 376);
  v6 = *(void (__fastcall **)(__int64, _BYTE *, _BYTE *, __int64))(*(_QWORD *)v5 + 40LL);
  std::string::string(
    v25,
    "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::SetVoiceActivationDefaultAgent");
  std::string::string(
    v24,
    "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v6(v5, v24, v25, 492);
  std::string::~string(v24);
  std::string::~string(v25);
  v21[0] = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
  Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsTelemetry::SetVoiceActivationDefaultAgent<unsigned short const *>(v21);
  std::wstring::wstring(v26);
  v7 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v4 + 48LL))(v4, v26);
  v8 = v7;
  if ( v7 >= 0 )
  {
    if ( !(unsigned __int8)std::operator!=<unsigned short>(a2, v26)
      || (std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2),
          v11 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 264),
          v7 = SpRegUtil::Set(v12, v11, v13, v14),
          v8 = v7,
          v7 >= 0) )
    {
      v15 = *(_QWORD *)(a1 + 368);
      v16 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, __int64, __int64, _QWORD))(*(_QWORD *)v15 + 72LL);
      v21[0] = v25;
      v17 = std::string::string(v25, "hr = 0x%x", v10);
      v21[1] = v24;
      v18 = std::string::string(
              v24,
              "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::SetVoiceActivationDefaultAgent");
      v19 = std::string::string(
              v22,
              "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
      v16(v15, v19, v18, 500, v17, v4, 0);
      v8 = 0;
      goto LABEL_8;
    }
    v9 = 498;
  }
  else
  {
    v9 = 495;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp",
    (const char *)(unsigned int)v7,
    v4);
LABEL_8:
  std::wstring::~wstring(v26);
  std::wstring::~wstring(a2);
  return v8;
}

```

## disassembly

```asm
0x14002c460  mov     [rsp-8+arg_10], rbx
0x14002c465  mov     [rsp-8+arg_18], rsi
0x14002c46a  push    rbp
0x14002c46b  push    rdi
0x14002c46c  push    r12
0x14002c46e  push    r14
0x14002c470  push    r15
0x14002c472  lea     rbp, [rsp-37h]
0x14002c477  sub     rsp, 0F0h
0x14002c47e  mov     rax, cs:__security_cookie
0x14002c485  xor     rax, rsp
0x14002c488  mov     [rbp+57h+var_30], rax
0x14002c48c  mov     r15, rdx
0x14002c48f  mov     r14, rcx
0x14002c492  mov     [rbp+57h+var_98], rdx
0x14002c496  lea     r12, [rcx-8]
0x14002c49a  mov     rdi, [r12+178h]
0x14002c4a2  mov     rax, [rdi]
0x14002c4a5  mov     rbx, [rax+28h]
0x14002c4a9  lea     rdx, aMicrosoftVoice_25; "Microsoft::VoiceAgentServices::Windows:"...
0x14002c4b0  lea     rcx, [rbp+57h+var_70]
0x14002c4b4  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002c4b9  nop
0x14002c4ba  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002c4c1  lea     rcx, [rbp+57h+var_90]
0x14002c4c5  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002c4ca  nop
0x14002c4cb  mov     qword ptr [rsp+110h+var_F0], r12; int
0x14002c4d0  mov     r9d, 1ECh
0x14002c4d6  lea     r8, [rbp+57h+var_70]
0x14002c4da  lea     rdx, [rbp+57h+var_90]
0x14002c4de  mov     rcx, rdi
0x14002c4e1  mov     rax, rbx
0x14002c4e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c4e9  nop
0x14002c4ea  lea     rcx, [rbp+57h+var_90]
0x14002c4ee  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002c4f3  nop
0x14002c4f4  lea     rcx, [rbp+57h+var_70]
0x14002c4f8  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002c4fd  mov     rcx, r15
0x14002c500  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14002c505  mov     [rbp+57h+var_D0], rax
0x14002c509  lea     rcx, [rbp+57h+var_D0]
0x14002c50d  call    ??$SetVoiceActivationDefaultAgent@PEBG@AgentActivationSettingsTelemetry@Settings@Windows@VoiceAgentServices@Microsoft@@SAX$$QEAPEBG@Z; Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsTelemetry::SetVoiceActivationDefaultAgent<ushort const *>(ushort const * &&)
0x14002c512  lea     rcx, [rbp+57h+var_50]
0x14002c516  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x14002c51b  nop
0x14002c51c  mov     rax, [r12]
0x14002c520  lea     rdx, [rbp+57h+var_50]
0x14002c524  mov     rcx, r12
0x14002c527  mov     rax, [rax+30h]
0x14002c52b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c530  mov     ebx, eax
0x14002c532  test    eax, eax
0x14002c534  jns     short loc_14002C53D
0x14002c536  mov     edx, 1EFh
0x14002c53b  jmp     short loc_14002C577
0x14002c53d  lea     rdx, [rbp+57h+var_50]
0x14002c541  mov     rcx, r15
0x14002c544  call    ??$?9GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator!=<ushort>(std::wstring const &,std::wstring const &)
0x14002c549  test    al, al
0x14002c54b  jz      short loc_14002C58F
0x14002c54d  mov     rcx, r15
0x14002c550  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14002c555  mov     r9, rax
0x14002c558  lea     rcx, [r14+108h]
0x14002c55f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14002c564  mov     rdx, rax; unsigned __int16 *
0x14002c567  call    ?Set@SpRegUtil@@SAJPEAUHKEY__@@PEBG11@Z; SpRegUtil::Set(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x14002c56c  mov     ebx, eax
0x14002c56e  test    eax, eax
0x14002c570  jns     short loc_14002C58F
0x14002c572  mov     edx, 1F2h; void *
0x14002c577  lea     r8, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002c57e  mov     r9d, eax; char *
0x14002c581  mov     rcx, [rbp+5Fh]; this
0x14002c585  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002c58a  jmp     loc_14002C610
0x14002c58f  mov     r14, [r14+170h]
0x14002c596  mov     rax, [r14]
0x14002c599  mov     rsi, [rax+48h]
0x14002c59d  lea     rax, [rbp+57h+var_70]
0x14002c5a1  mov     [rbp+57h+var_D0], rax
0x14002c5a5  lea     rdx, aHr0xX; "hr = 0x%x"
0x14002c5ac  lea     rcx, [rbp+57h+var_70]
0x14002c5b0  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002c5b5  mov     rdi, rax
0x14002c5b8  lea     rax, [rbp+57h+var_90]
0x14002c5bc  mov     [rbp+57h+var_C8], rax
0x14002c5c0  lea     rdx, aMicrosoftVoice_25; "Microsoft::VoiceAgentServices::Windows:"...
0x14002c5c7  lea     rcx, [rbp+57h+var_90]
0x14002c5cb  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002c5d0  mov     rbx, rax
0x14002c5d3  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002c5da  lea     rcx, [rbp+57h+var_B8]
0x14002c5de  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002c5e3  nop
0x14002c5e4  mov     [rsp+110h+var_E0], 0
0x14002c5ed  mov     [rsp+110h+var_E8], r12
0x14002c5f2  mov     qword ptr [rsp+110h+var_F0], rdi
0x14002c5f7  mov     r9d, 1F4h
0x14002c5fd  mov     r8, rbx
0x14002c600  mov     rdx, rax
0x14002c603  mov     rcx, r14
0x14002c606  mov     rax, rsi
0x14002c609  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c60e  xor     ebx, ebx
0x14002c610  lea     rcx, [rbp+57h+var_50]
0x14002c614  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002c619  nop
0x14002c61a  mov     rcx, r15
0x14002c61d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002c622  mov     eax, ebx
0x14002c624  mov     rcx, [rbp+57h+var_30]
0x14002c628  xor     rcx, rsp; StackCookie
0x14002c62b  call    __security_check_cookie
0x14002c630  lea     r11, [rsp+110h+var_20]
0x14002c638  mov     rbx, [r11+40h]
0x14002c63c  mov     rsi, [r11+48h]
0x14002c640  mov     rsp, r11
0x14002c643  pop     r15
0x14002c645  pop     r14
0x14002c647  pop     r12
0x14002c649  pop     rdi
0x14002c64a  pop     rbp
0x14002c64b  retn
```
