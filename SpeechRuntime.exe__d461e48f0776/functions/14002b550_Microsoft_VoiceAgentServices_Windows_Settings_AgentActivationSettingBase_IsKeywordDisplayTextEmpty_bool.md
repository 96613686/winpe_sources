# Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::IsKeywordDisplayTextEmpty(bool &)

- ea: `0x14002b550`
- end: `0x14002b6e8`
- name: `?IsKeywordDisplayTextEmpty@AgentActivationSettingBase@Settings@Windows@VoiceAgentServices@Microsoft@@UEAAJAEA_N@Z`
- size: `408`
- prototype: `__int64 __fastcall(Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *__hidden this, bool *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140002d30`
- `0x14001296c`
- `0x140012d68`
- `0x140020ff0`
- `0x140021658`
- `0x140021b80`
- `0x140022480`
- `0x14002b550`
- `0x140031010`

## string_xrefs

- `0x14002b59b`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x14002b688`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x14002b58a`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::IsKeywordDisplayTextEmpty`
- `0x14002b675`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::IsKeywordDisplayTextEmpty`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::IsKeywordDisplayTextEmpty(
        Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *this,
        bool *a2)
{
  __int64 v4; // rdi
  void (__fastcall *v5)(__int64, _BYTE *, int *, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *); // rbx
  int v6; // r8d
  int v7; // eax
  unsigned __int16 *v8; // rdx
  __int64 String; // rax
  __int64 v10; // r14
  void (__fastcall *v11)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, _QWORD); // rsi
  __int64 v12; // rdi
  __int64 v13; // rbx
  __int64 v14; // rax
  _BYTE v16[32]; // [rsp+58h] [rbp-31h] BYREF
  int v17[8]; // [rsp+78h] [rbp-11h] BYREF
  _BYTE v18[32]; // [rsp+98h] [rbp+Fh] BYREF

  v4 = *((_QWORD *)this + 47);
  v5 = *(void (__fastcall **)(__int64, _BYTE *, int *, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *))(*(_QWORD *)v4 + 40LL);
  std::string::string(
    v17,
    "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::IsKeywordDisplayTextEmpty");
  std::string::string(
    v18,
    "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v5(v4, v18, v17, 595, this);
  std::string::~string(v18);
  std::string::~string(v17);
  if ( !*((_QWORD *)this + 18) )
  {
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 64);
    v7 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 272);
    String = SpRegUtil::GetString((int)v17, -2147483647, v7, (int)L"DisplayName", v8);
    std::wstring::operator=((char *)this + 128, String);
    std::wstring::~wstring(v17);
    *a2 = *((_QWORD *)this + 18) == 0;
  }
  v10 = *((_QWORD *)this + 47);
  v11 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, _QWORD))(*(_QWORD *)v10 + 72LL);
  v12 = std::string::string(v17, "hr = 0x%x", v6);
  v13 = std::string::string(
          v18,
          "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::IsKeywordDisplayTextEmpty");
  v14 = std::string::string(
          v16,
          "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v11(v10, v14, v13, 601, v12, this, 0);
  return 0;
}

```

## disassembly

```asm
0x14002b550  mov     [rsp-8+arg_10], rbx
0x14002b555  push    rbp
0x14002b556  push    rsi
0x14002b557  push    rdi
0x14002b558  push    r14
0x14002b55a  push    r15
0x14002b55c  lea     rbp, [rsp-37h]
0x14002b561  sub     rsp, 0C0h
0x14002b568  mov     rax, cs:__security_cookie
0x14002b56f  xor     rax, rsp
0x14002b572  mov     [rbp+57h+var_28], rax
0x14002b576  mov     rsi, rdx
0x14002b579  mov     r15, rcx
0x14002b57c  mov     rdi, [rcx+178h]
0x14002b583  mov     rax, [rdi]
0x14002b586  mov     rbx, [rax+28h]
0x14002b58a  lea     rdx, aMicrosoftVoice_1; "Microsoft::VoiceAgentServices::Windows:"...
0x14002b591  lea     rcx, [rbp+57h+var_68]
0x14002b595  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002b59a  nop
0x14002b59b  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002b5a2  lea     rcx, [rbp+57h+var_48]
0x14002b5a6  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002b5ab  nop
0x14002b5ac  mov     [rsp+0E0h+var_C0], r15
0x14002b5b1  mov     r9d, 253h
0x14002b5b7  lea     r8, [rbp+57h+var_68]
0x14002b5bb  lea     rdx, [rbp+57h+var_48]
0x14002b5bf  mov     rcx, rdi
0x14002b5c2  mov     rax, rbx
0x14002b5c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002b5ca  nop
0x14002b5cb  lea     rcx, [rbp+57h+var_48]
0x14002b5cf  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002b5d4  nop
0x14002b5d5  lea     rcx, [rbp+57h+var_68]
0x14002b5d9  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002b5de  cmp     qword ptr [r15+90h], 0
0x14002b5e6  jnz     short loc_14002B644
0x14002b5e8  lea     rcx, [r15+40h]
0x14002b5ec  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14002b5f1  mov     rdx, rax
0x14002b5f4  lea     rcx, [r15+110h]
0x14002b5fb  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14002b600  mov     [rsp+0E0h+var_C0], rdx; unsigned __int16 *
0x14002b605  lea     r9, aDisplayname; "DisplayName"
0x14002b60c  mov     r8, rax; int
0x14002b60f  mov     rdx, 0FFFFFFFF80000001h; int
0x14002b616  lea     rcx, [rbp+57h+var_68]; int
0x14002b61a  call    ?GetString@SpRegUtil@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHKEY__@@PEBG11@Z; SpRegUtil::GetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x14002b61f  lea     rcx, [r15+80h]
0x14002b626  mov     rdx, rax
0x14002b629  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x14002b62e  lea     rcx, [rbp+57h+var_68]
0x14002b632  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002b637  cmp     qword ptr [r15+90h], 0
0x14002b63f  setz    al
0x14002b642  mov     [rsi], al
0x14002b644  mov     r14, [r15+178h]
0x14002b64b  mov     rax, [r14]
0x14002b64e  mov     rsi, [rax+48h]
0x14002b652  lea     rax, [rbp+57h+var_68]
0x14002b656  mov     [rbp+57h+var_A0], rax
0x14002b65a  lea     rdx, aHr0xX; "hr = 0x%x"
0x14002b661  lea     rcx, [rbp+57h+var_68]
0x14002b665  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002b66a  mov     rdi, rax
0x14002b66d  lea     rax, [rbp+57h+var_48]
0x14002b671  mov     [rbp+57h+var_98], rax
0x14002b675  lea     rdx, aMicrosoftVoice_1; "Microsoft::VoiceAgentServices::Windows:"...
0x14002b67c  lea     rcx, [rbp+57h+var_48]
0x14002b680  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002b685  mov     rbx, rax
0x14002b688  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002b68f  lea     rcx, [rbp+57h+var_88]
0x14002b693  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002b698  nop
0x14002b699  mov     [rsp+0E0h+var_B0], 0
0x14002b6a2  mov     [rsp+0E0h+var_B8], r15
0x14002b6a7  mov     [rsp+0E0h+var_C0], rdi
0x14002b6ac  mov     r9d, 259h
0x14002b6b2  mov     r8, rbx
0x14002b6b5  mov     rdx, rax
0x14002b6b8  mov     rcx, r14
0x14002b6bb  mov     rax, rsi
0x14002b6be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002b6c3  xor     eax, eax
0x14002b6c5  mov     rcx, [rbp+57h+var_28]
0x14002b6c9  xor     rcx, rsp; StackCookie
0x14002b6cc  call    __security_check_cookie
0x14002b6d1  mov     rbx, [rsp+0E0h+arg_10]
0x14002b6d9  add     rsp, 0C0h
0x14002b6e0  pop     r15
0x14002b6e2  pop     r14
0x14002b6e4  pop     rdi
0x14002b6e5  pop     rsi
0x14002b6e6  pop     rbp
0x14002b6e7  retn
```
