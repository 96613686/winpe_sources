# Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::IsHWKWSSupported(bool &)

- ea: `0x14002b2f0`
- end: `0x14002b548`
- name: `?IsHWKWSSupported@AgentActivationSettingBase@Settings@Windows@VoiceAgentServices@Microsoft@@UEAAJAEA_N@Z`
- size: `600`
- prototype: `__int64 __fastcall(Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *__hidden this, bool *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140002d30`
- `0x1400128b8`
- `0x14001296c`
- `0x140012d68`
- `0x140020ff0`
- `0x140021658`
- `0x140023cd0`
- `0x140031010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14002b403`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14002b403`

## string_xrefs

- `0x14002b341`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x14002b458`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x14002b4d9`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x14002b330`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::IsHWKWSSupported`
- `0x14002b445`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::IsHWKWSSupported`
- `0x14002b4c6`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::IsHWKWSSupported`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::IsHWKWSSupported(
        Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *this,
        bool *a2)
{
  __int64 v4; // rdi
  void (__fastcall *v5)(__int64, _BYTE *, _BYTE *, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *); // rbx
  __int64 v6; // rax
  const WCHAR *v7; // rax
  bool v8; // si
  __int64 v9; // r15
  void (__fastcall *v10)(__int64, _QWORD, __int64, __int64, int, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, bool); // r14
  int v11; // r8d
  __int64 v12; // rdi
  __int64 v13; // rbx
  __int64 v14; // rax
  __int64 v15; // r14
  void (__fastcall *v16)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, _QWORD); // rsi
  int v17; // r8d
  __int64 v18; // rdi
  __int64 v19; // rbx
  __int64 v20; // rax
  _BYTE *pvData; // [rsp+50h] [rbp-69h] BYREF
  DWORD pcbData[2]; // [rsp+58h] [rbp-61h] BYREF
  _BYTE *v24; // [rsp+60h] [rbp-59h]
  _BYTE v25[32]; // [rsp+68h] [rbp-51h] BYREF
  _BYTE v26[32]; // [rsp+88h] [rbp-31h] BYREF
  _BYTE v27[32]; // [rsp+A8h] [rbp-11h] BYREF
  _BYTE v28[32]; // [rsp+C8h] [rbp+Fh] BYREF

  v4 = *((_QWORD *)this + 47);
  v5 = *(void (__fastcall **)(__int64, _BYTE *, _BYTE *, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *))(*(_QWORD *)v4 + 40LL);
  std::string::string(
    v27,
    "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::IsHWKWSSupported");
  std::string::string(
    v26,
    "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v5(v4, v26, v27, 559, this);
  std::string::~string(v26);
  std::string::~string(v27);
  std::wstring::wstring(v28, L"SOFTWARE\\Microsoft\\Speech_OneCore\\Settings\\VoiceActivation");
  std::wstring::append(v28, L"\\");
  v6 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 32);
  std::wstring::append(v28, v6);
  LODWORD(pvData) = 0;
  pcbData[0] = 4;
  v7 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v28);
  RegGetValueW(HKEY_CURRENT_USER, v7, L"HwKeywordState", 0x18u, 0, &pvData, pcbData);
  v8 = (_DWORD)pvData == 4;
  *a2 = (_DWORD)pvData == 4;
  v9 = *((_QWORD *)this + 47);
  v10 = *(void (__fastcall **)(__int64, _QWORD, __int64, __int64, int, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, bool))(*(_QWORD *)v9 + 16LL);
  *(_QWORD *)pcbData = v27;
  v12 = std::string::string(v27, "HWKWSSupported = %d", v11);
  pvData = v26;
  v13 = std::string::string(
          v26,
          "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::IsHWKWSSupported");
  v14 = std::string::string(
          v25,
          "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v10(v9, 0, v14, v13, 572, v12, this, v8);
  v15 = *((_QWORD *)this + 47);
  v16 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, _QWORD))(*(_QWORD *)v15 + 72LL);
  v24 = v25;
  v18 = std::string::string(v25, "hr = 0x%x", v17);
  *(_QWORD *)pcbData = v27;
  v19 = std::string::string(
          v27,
          "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::IsHWKWSSupported");
  v20 = std::string::string(
          v26,
          "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v16(v15, v20, v19, 573, v18, this, 0);
  std::wstring::~wstring(v28);
  return 0;
}

```

## disassembly

```asm
0x14002b2f0  mov     [rsp-8+arg_10], rbx
0x14002b2f5  mov     [rsp-8+arg_18], rsi
0x14002b2fa  push    rbp
0x14002b2fb  push    rdi
0x14002b2fc  push    r13
0x14002b2fe  push    r14
0x14002b300  push    r15
0x14002b302  lea     rbp, [rsp-37h]
0x14002b307  sub     rsp, 0F0h
0x14002b30e  mov     rax, cs:__security_cookie
0x14002b315  xor     rax, rsp
0x14002b318  mov     [rbp+57h+var_28], rax
0x14002b31c  mov     r14, rdx
0x14002b31f  mov     r13, rcx
0x14002b322  mov     rdi, [rcx+178h]
0x14002b329  mov     rax, [rdi]
0x14002b32c  mov     rbx, [rax+28h]
0x14002b330  lea     rdx, aMicrosoftVoice_30; "Microsoft::VoiceAgentServices::Windows:"...
0x14002b337  lea     rcx, [rbp+57h+var_68]
0x14002b33b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002b340  nop
0x14002b341  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002b348  lea     rcx, [rbp+57h+var_88]
0x14002b34c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002b351  nop
0x14002b352  mov     [rsp+110h+pdwType], r13
0x14002b357  mov     r9d, 22Fh
0x14002b35d  lea     r8, [rbp+57h+var_68]
0x14002b361  lea     rdx, [rbp+57h+var_88]
0x14002b365  mov     rcx, rdi
0x14002b368  mov     rax, rbx
0x14002b36b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002b370  nop
0x14002b371  lea     rcx, [rbp+57h+var_88]
0x14002b375  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002b37a  nop
0x14002b37b  lea     rcx, [rbp+57h+var_68]
0x14002b37f  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002b384  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Speech_OneCore\\Se"...
0x14002b38b  lea     rcx, [rbp+57h+var_48]
0x14002b38f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x14002b394  nop
0x14002b395  lea     rdx, asc_140034BF8; "\\"
0x14002b39c  lea     rcx, [rbp+57h+var_48]
0x14002b3a0  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x14002b3a5  lea     rcx, [r13+20h]
0x14002b3a9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14002b3ae  mov     rdx, rax
0x14002b3b1  lea     rcx, [rbp+57h+var_48]
0x14002b3b5  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x14002b3ba  mov     dword ptr [rbp+57h+var_C0], 0
0x14002b3c1  mov     [rbp+57h+var_B8], 4
0x14002b3c8  lea     rcx, [rbp+57h+var_48]
0x14002b3cc  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14002b3d1  mov     rdx, rax; lpSubKey
0x14002b3d4  lea     rax, [rbp+57h+var_B8]
0x14002b3d8  mov     [rsp+110h+pcbData], rax; pcbData
0x14002b3dd  lea     rax, [rbp+57h+var_C0]
0x14002b3e1  mov     [rsp+110h+pvData], rax; pvData
0x14002b3e6  mov     [rsp+110h+pdwType], 0; pdwType
0x14002b3ef  mov     r9d, 18h; dwFlags
0x14002b3f5  lea     r8, aHwkeywordstate; "HwKeywordState"
0x14002b3fc  mov     rcx, 0FFFFFFFF80000001h; hkey
0x14002b403  call    cs:__imp_RegGetValueW
0x14002b409  cmp     dword ptr [rbp+57h+var_C0], 4
0x14002b40d  setz    sil
0x14002b411  mov     [r14], sil
0x14002b414  mov     r15, [r13+178h]
0x14002b41b  mov     rax, [r15]
0x14002b41e  mov     r14, [rax+10h]
0x14002b422  lea     rax, [rbp+57h+var_68]
0x14002b426  mov     qword ptr [rbp+57h+var_B8], rax
0x14002b42a  lea     rdx, aHwkwssupported; "HWKWSSupported = %d"
0x14002b431  lea     rcx, [rbp+57h+var_68]
0x14002b435  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002b43a  mov     rdi, rax
0x14002b43d  lea     rax, [rbp+57h+var_88]
0x14002b441  mov     [rbp+57h+var_C0], rax
0x14002b445  lea     rdx, aMicrosoftVoice_30; "Microsoft::VoiceAgentServices::Windows:"...
0x14002b44c  lea     rcx, [rbp+57h+var_88]
0x14002b450  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002b455  mov     rbx, rax
0x14002b458  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002b45f  lea     rcx, [rbp+57h+var_A8]
0x14002b463  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002b468  movzx   edx, sil
0x14002b46c  mov     [rsp+110h+var_D8], edx
0x14002b470  mov     [rsp+110h+pcbData], r13
0x14002b475  mov     [rsp+110h+pvData], rdi
0x14002b47a  mov     dword ptr [rsp+110h+pdwType], 23Ch
0x14002b482  mov     r9, rbx
0x14002b485  mov     r8, rax
0x14002b488  xor     edx, edx
0x14002b48a  mov     rcx, r15
0x14002b48d  mov     rax, r14
0x14002b490  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002b495  mov     r14, [r13+178h]
0x14002b49c  mov     rax, [r14]
0x14002b49f  mov     rsi, [rax+48h]
0x14002b4a3  lea     rax, [rbp+57h+var_A8]
0x14002b4a7  mov     [rbp+57h+var_B0], rax
0x14002b4ab  lea     rdx, aHr0xX; "hr = 0x%x"
0x14002b4b2  lea     rcx, [rbp+57h+var_A8]
0x14002b4b6  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002b4bb  mov     rdi, rax
0x14002b4be  lea     rax, [rbp+57h+var_68]
0x14002b4c2  mov     qword ptr [rbp+57h+var_B8], rax
0x14002b4c6  lea     rdx, aMicrosoftVoice_30; "Microsoft::VoiceAgentServices::Windows:"...
0x14002b4cd  lea     rcx, [rbp+57h+var_68]
0x14002b4d1  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002b4d6  mov     rbx, rax
0x14002b4d9  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002b4e0  lea     rcx, [rbp+57h+var_88]
0x14002b4e4  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002b4e9  nop
0x14002b4ea  mov     [rsp+110h+pcbData], 0
0x14002b4f3  mov     [rsp+110h+pvData], r13
0x14002b4f8  mov     [rsp+110h+pdwType], rdi
0x14002b4fd  mov     r9d, 23Dh
0x14002b503  mov     r8, rbx
0x14002b506  mov     rdx, rax
0x14002b509  mov     rcx, r14
0x14002b50c  mov     rax, rsi
0x14002b50f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002b514  nop
0x14002b515  lea     rcx, [rbp+57h+var_48]
0x14002b519  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002b51e  xor     eax, eax
0x14002b520  mov     rcx, [rbp+57h+var_28]
0x14002b524  xor     rcx, rsp; StackCookie
0x14002b527  call    __security_check_cookie
0x14002b52c  lea     r11, [rsp+110h+var_20]
0x14002b534  mov     rbx, [r11+40h]
0x14002b538  mov     rsi, [r11+48h]
0x14002b53c  mov     rsp, r11
0x14002b53f  pop     r15
0x14002b541  pop     r14
0x14002b543  pop     r13
0x14002b545  pop     rdi
0x14002b546  pop     rbp
0x14002b547  retn
```
