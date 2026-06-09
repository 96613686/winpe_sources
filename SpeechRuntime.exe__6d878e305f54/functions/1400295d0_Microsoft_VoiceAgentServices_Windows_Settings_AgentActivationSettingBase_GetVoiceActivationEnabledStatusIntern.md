# Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationEnabledStatusInternal(bool &,Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationStatusDisabledReason &)

- ea: `0x1400295d0`
- end: `0x1400298f5`
- name: `?GetVoiceActivationEnabledStatusInternal@AgentActivationSettingBase@Settings@Windows@VoiceAgentServices@Microsoft@@MEAAJAEA_NAEAW4AgentActivationStatusDisabledReason@2345@@Z`
- size: `805`
- prototype: `__int64 __fastcall(Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *__hidden this, bool *, enum Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationStatusDisabledReason *)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140002d30`
- `0x14000e030`
- `0x14001296c`
- `0x140012d68`
- `0x140020ff0`
- `0x140021658`
- `0x140021c8c`
- `0x140025630`
- `0x140025768`
- `0x140025884`
- `0x140026fdc`
- `0x1400295d0`
- `0x140031010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400296d8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400296d8`

## string_xrefs

- `0x140029622`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x140029745`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x140029895`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x140029611`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationEnabledStatusInternal`
- `0x140029882`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationEnabledStatusInternal`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationEnabledStatusInternal(
        Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *this,
        bool *a2,
        enum Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationStatusDisabledReason *a3)
{
  __int64 v6; // rdi
  void (__fastcall *v7)(__int64, _BYTE *, _BYTE *, __int64); // rbx
  char v8; // di
  const WCHAR *v9; // rax
  _QWORD *v10; // rcx
  int IsMicrophoneAllowed; // ebx
  __int64 v12; // rdx
  __int64 v14; // rcx
  char v15; // al
  __int64 v16; // r14
  void (__fastcall *v17)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, _QWORD); // rsi
  int v18; // r8d
  __int64 v19; // rdi
  __int64 v20; // rbx
  __int64 v21; // rax
  int pdwType; // [rsp+20h] [rbp-89h]
  bool v23; // [rsp+40h] [rbp-69h] BYREF
  _BYTE v24[7]; // [rsp+41h] [rbp-68h] BYREF
  DWORD pcbData[2]; // [rsp+48h] [rbp-61h] BYREF
  _BYTE *pvData; // [rsp+50h] [rbp-59h] BYREF
  _BYTE v27[32]; // [rsp+60h] [rbp-49h] BYREF
  _BYTE v28[32]; // [rsp+80h] [rbp-29h] BYREF
  _BYTE v29[32]; // [rsp+A0h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v6 = *((_QWORD *)this + 47);
  v7 = *(void (__fastcall **)(__int64, _BYTE *, _BYTE *, __int64))(*(_QWORD *)v6 + 40LL);
  std::string::string(
    v28,
    "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationEnabledStatusInternal");
  std::string::string(
    v29,
    "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  pdwType = (int)this;
  v7(v6, v29, v28, 261);
  std::string::~string(v29);
  std::string::~string(v28);
  v8 = 1;
  if ( !*((_QWORD *)this + 6) || *((_WORD *)this + 80) != 0xFFFF )
    goto LABEL_11;
  Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingUtils::GetRegistryConfigurationPath(
    v28,
    (char *)this + 32);
  LODWORD(pvData) = 0xFFFF;
  pcbData[0] = 4;
  v9 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v28);
  RegGetValueW(HKEY_CURRENT_USER, v9, L"LANGID", 0x18u, 0, &pvData, pcbData);
  if ( (_DWORD)pvData == 0xFFFF )
  {
    *a2 = 0;
    *(_DWORD *)a3 = 5;
    v8 = 0;
  }
  else
  {
    *((_WORD *)this + 80) = (_WORD)pvData;
  }
  std::wstring::~wstring(v28);
  if ( v8 )
  {
LABEL_11:
    if ( !(unsigned __int8)std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>::operator bool((char *)this + 16) )
      goto LABEL_13;
    v23 = 1;
    pcbData[0] = 0;
    IsMicrophoneAllowed = (*(__int64 (__fastcall **)(_QWORD, bool *, DWORD *))(*(_QWORD *)*v10 + 16LL))(
                            *v10,
                            &v23,
                            pcbData);
    if ( IsMicrophoneAllowed < 0 )
    {
      v12 = 290;
LABEL_10:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp",
        (const char *)(unsigned int)IsMicrophoneAllowed,
        pdwType);
      return (unsigned int)IsMicrophoneAllowed;
    }
    if ( v23 )
    {
LABEL_13:
      v23 = 0;
      IsMicrophoneAllowed = Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingUtils::IsMicrophoneAllowed(
                              (__int64)this + 32,
                              &v23);
      if ( IsMicrophoneAllowed < 0 )
      {
        v12 = 302;
        goto LABEL_10;
      }
      if ( v23 )
      {
        v23 = 0;
        v24[0] = 0;
        IsMicrophoneAllowed = Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingUtils::IsGroupPolicyAllowed(
                                v14,
                                0,
                                &v23,
                                v24);
        if ( IsMicrophoneAllowed < 0 )
        {
          v12 = 315;
          goto LABEL_10;
        }
        if ( !v23 || v24[0] )
        {
          *a2 = v23;
          *(_DWORD *)a3 = 2;
        }
        else
        {
          v24[0] = 0;
          IsMicrophoneAllowed = (*(__int64 (__fastcall **)(Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, _BYTE *))(*(_QWORD *)this + 104LL))(
                                  this,
                                  v24);
          if ( IsMicrophoneAllowed < 0 )
          {
            v12 = 328;
            goto LABEL_10;
          }
          if ( IsMicrophoneAllowed == 1 )
            v15 = (*(__int64 (__fastcall **)(Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *))(*(_QWORD *)this + 144LL))(this);
          else
            v15 = v24[0];
          *a2 = v15;
          *(_DWORD *)a3 = 0;
        }
      }
      else
      {
        *a2 = 0;
        *(_DWORD *)a3 = 3;
      }
    }
    else
    {
      *a2 = 0;
      *(_DWORD *)a3 = 1;
    }
  }
  *(_QWORD *)pcbData = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 32);
  Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsTelemetry::VoiceActivationEnabledStatus<unsigned short const *,bool &,enum Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationStatusDisabledReason &>(
    pcbData,
    a2,
    a3);
  v16 = *((_QWORD *)this + 47);
  v17 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, _QWORD))(*(_QWORD *)v16 + 72LL);
  *(_QWORD *)pcbData = v28;
  v19 = std::string::string(v28, "hr = 0x%x", v18);
  pvData = v29;
  v20 = std::string::string(
          v29,
          "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::GetVoiceActivationEnabledStatusInternal");
  v21 = std::string::string(
          v27,
          "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v17(v16, v21, v20, 334, v19, this, 0);
  return 0;
}

```

## disassembly

```asm
0x1400295d0  mov     [rsp-8+arg_18], rbx
0x1400295d5  push    rbp
0x1400295d6  push    rsi
0x1400295d7  push    rdi
0x1400295d8  push    r12
0x1400295da  push    r13
0x1400295dc  push    r14
0x1400295de  push    r15
0x1400295e0  lea     rbp, [rsp-27h]
0x1400295e5  sub     rsp, 0D0h
0x1400295ec  mov     rax, cs:__security_cookie
0x1400295f3  xor     rax, rsp
0x1400295f6  mov     [rbp+57h+var_40], rax
0x1400295fa  mov     r14, r8
0x1400295fd  mov     rsi, rdx
0x140029600  mov     r15, rcx
0x140029603  mov     rdi, [rcx+178h]
0x14002960a  mov     rax, [rdi]
0x14002960d  mov     rbx, [rax+28h]
0x140029611  lea     rdx, aMicrosoftVoice_21; "Microsoft::VoiceAgentServices::Windows:"...
0x140029618  lea     rcx, [rbp+57h+var_80]
0x14002961c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140029621  nop
0x140029622  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140029629  lea     rcx, [rbp+57h+var_60]
0x14002962d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140029632  nop
0x140029633  mov     [rsp+100h+pdwType], r15
0x140029638  mov     r9d, 105h
0x14002963e  lea     r8, [rbp+57h+var_80]
0x140029642  lea     rdx, [rbp+57h+var_60]
0x140029646  mov     rcx, rdi
0x140029649  mov     rax, rbx
0x14002964c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029651  nop
0x140029652  lea     rcx, [rbp+57h+var_60]
0x140029656  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002965b  nop
0x14002965c  lea     rcx, [rbp+57h+var_80]
0x140029660  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140029665  mov     dil, 1
0x140029668  lea     r12, [r15+20h]
0x14002966c  xor     r13d, r13d
0x14002966f  cmp     [r12+10h], r13
0x140029674  jz      loc_14002970E
0x14002967a  mov     ebx, 0FFFFh
0x14002967f  cmp     [r15+0A0h], bx
0x140029687  jnz     loc_14002970E
0x14002968d  mov     rdx, r12
0x140029690  lea     rcx, [rbp+57h+var_80]
0x140029694  call    ?GetRegistryConfigurationPath@AgentActivationSettingUtils@Settings@Windows@VoiceAgentServices@Microsoft@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV67@@Z; Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingUtils::GetRegistryConfigurationPath(std::wstring const &)
0x140029699  mov     dword ptr [rbp+57h+var_B0], ebx
0x14002969c  mov     [rbp+57h+var_B8], 4
0x1400296a3  lea     rcx, [rbp+57h+var_80]
0x1400296a7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1400296ac  mov     rdx, rax; lpSubKey
0x1400296af  lea     rax, [rbp+57h+var_B8]
0x1400296b3  mov     [rsp+100h+pcbData], rax; pcbData
0x1400296b8  lea     rax, [rbp+57h+var_B0]
0x1400296bc  mov     [rsp+100h+pvData], rax; pvData
0x1400296c1  mov     [rsp+100h+pdwType], r13; int
0x1400296c6  lea     r9d, [r13+18h]; dwFlags
0x1400296ca  lea     r8, aLangid; "LANGID"
0x1400296d1  mov     rcx, 0FFFFFFFF80000001h; hkey
0x1400296d8  call    cs:__imp_RegGetValueW
0x1400296de  mov     eax, dword ptr [rbp+57h+var_B0]
0x1400296e1  cmp     eax, ebx
0x1400296e3  jz      short loc_1400296EF
0x1400296e5  mov     [r15+0A0h], ax
0x1400296ed  jmp     short loc_1400296FC
0x1400296ef  mov     [rsi], r13b
0x1400296f2  mov     dword ptr [r14], 5
0x1400296f9  mov     dil, r13b
0x1400296fc  lea     rcx, [rbp+57h+var_80]
0x140029700  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140029705  test    dil, dil
0x140029708  jz      loc_140029836
0x14002970e  lea     rcx, [r15+10h]
0x140029712  call    ??B?$shared_ptr@VAgentActivationSettingManager@Settings@Windows@VoiceAgentServices@Microsoft@@@std@@QEBA_NXZ; std::shared_ptr<Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingManager>::operator bool(void)
0x140029717  test    al, al
0x140029719  jz      short loc_140029774
0x14002971b  mov     [rbp+57h+var_C0], 1
0x14002971f  mov     [rbp+57h+var_B8], r13d
0x140029723  mov     rcx, [rcx]
0x140029726  mov     rax, [rcx]
0x140029729  lea     r8, [rbp+57h+var_B8]
0x14002972d  lea     rdx, [rbp+57h+var_C0]
0x140029731  mov     rax, [rax+10h]
0x140029735  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002973a  mov     ebx, eax
0x14002973c  test    eax, eax
0x14002973e  jns     short loc_14002975F
0x140029740  mov     edx, 122h; void *
0x140029745  lea     r8, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002974c  mov     r9d, ebx; char *
0x14002974f  mov     rcx, [rbp+5Fh]; this
0x140029753  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140029758  mov     eax, ebx
0x14002975a  jmp     loc_1400298CE
0x14002975f  cmp     [rbp+57h+var_C0], r13b
0x140029763  jnz     short loc_140029774
0x140029765  mov     [rsi], r13b
0x140029768  mov     dword ptr [r14], 1
0x14002976f  jmp     loc_140029836
0x140029774  test    dil, dil
0x140029777  jz      loc_140029836
0x14002977d  mov     [rbp+57h+var_C0], r13b
0x140029781  lea     rdx, [rbp+57h+var_C0]
0x140029785  mov     rcx, r12
0x140029788  call    ?IsMicrophoneAllowed@AgentActivationSettingUtils@Settings@Windows@VoiceAgentServices@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEA_N@Z; Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingUtils::IsMicrophoneAllowed(std::wstring const &,bool &)
0x14002978d  mov     ebx, eax
0x14002978f  test    eax, eax
0x140029791  jns     short loc_14002979A
0x140029793  mov     edx, 12Eh
0x140029798  jmp     short loc_140029745
0x14002979a  cmp     [rbp+57h+var_C0], r13b
0x14002979e  jnz     short loc_1400297AF
0x1400297a0  mov     [rsi], r13b
0x1400297a3  mov     dword ptr [r14], 3
0x1400297aa  jmp     loc_140029836
0x1400297af  mov     [rbp+57h+var_C0], r13b
0x1400297b3  mov     [rbp+57h+var_BF], r13b
0x1400297b7  lea     r9, [rbp+57h+var_BF]
0x1400297bb  lea     r8, [rbp+57h+var_C0]
0x1400297bf  xor     edx, edx
0x1400297c1  call    ?IsGroupPolicyAllowed@AgentActivationSettingUtils@Settings@Windows@VoiceAgentServices@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4AgentActivationSettingName@2345@AEA_N2@Z; Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingUtils::IsGroupPolicyAllowed(std::wstring const &,Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingName,bool &,bool &)
0x1400297c6  mov     ebx, eax
0x1400297c8  test    eax, eax
0x1400297ca  jns     short loc_1400297D6
0x1400297cc  mov     edx, 13Bh
0x1400297d1  jmp     loc_140029745
0x1400297d6  mov     al, [rbp+57h+var_C0]
0x1400297d9  test    al, al
0x1400297db  jz      short loc_14002982D
0x1400297dd  cmp     [rbp+57h+var_BF], r13b
0x1400297e1  jnz     short loc_14002982D
0x1400297e3  mov     [rbp+57h+var_BF], r13b
0x1400297e7  mov     rax, [r15]
0x1400297ea  lea     rdx, [rbp+57h+var_BF]
0x1400297ee  mov     rcx, r15
0x1400297f1  mov     rax, [rax+68h]
0x1400297f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400297fa  mov     ebx, eax
0x1400297fc  test    eax, eax
0x1400297fe  jns     short loc_14002980A
0x140029800  mov     edx, 148h
0x140029805  jmp     loc_140029745
0x14002980a  cmp     ebx, 1
0x14002980d  jnz     short loc_140029823
0x14002980f  mov     rax, [r15]
0x140029812  mov     rcx, r15
0x140029815  mov     rax, [rax+90h]
0x14002981c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029821  jmp     short loc_140029826
0x140029823  mov     al, [rbp+57h+var_BF]
0x140029826  mov     [rsi], al
0x140029828  mov     [r14], r13d
0x14002982b  jmp     short loc_140029836
0x14002982d  mov     [rsi], al
0x14002982f  mov     dword ptr [r14], 2
0x140029836  mov     rcx, r12
0x140029839  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14002983e  mov     qword ptr [rbp+57h+var_B8], rax
0x140029842  mov     r8, r14
0x140029845  mov     rdx, rsi
0x140029848  lea     rcx, [rbp+57h+var_B8]
0x14002984c  call    ??$VoiceActivationEnabledStatus@PEBGAEA_NAEAW4AgentActivationStatusDisabledReason@Settings@Windows@VoiceAgentServices@Microsoft@@@AgentActivationSettingsTelemetry@Settings@Windows@VoiceAgentServices@Microsoft@@SAX$$QEAPEBGAEA_NAEAW4AgentActivationStatusDisabledReason@1234@@Z; Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsTelemetry::VoiceActivationEnabledStatus<ushort const *,bool &,Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationStatusDisabledReason &>(ushort const * &&,bool &,Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationStatusDisabledReason &)
0x140029851  mov     r14, [r15+178h]
0x140029858  mov     rax, [r14]
0x14002985b  mov     rsi, [rax+48h]
0x14002985f  lea     rax, [rbp+57h+var_80]
0x140029863  mov     qword ptr [rbp+57h+var_B8], rax
0x140029867  lea     rdx, aHr0xX; "hr = 0x%x"
0x14002986e  lea     rcx, [rbp+57h+var_80]
0x140029872  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140029877  mov     rdi, rax
0x14002987a  lea     rax, [rbp+57h+var_60]
0x14002987e  mov     [rbp+57h+var_B0], rax
0x140029882  lea     rdx, aMicrosoftVoice_21; "Microsoft::VoiceAgentServices::Windows:"...
0x140029889  lea     rcx, [rbp+57h+var_60]
0x14002988d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140029892  mov     rbx, rax
0x140029895  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002989c  lea     rcx, [rbp+57h+var_A0]
0x1400298a0  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400298a5  nop
0x1400298a6  mov     [rsp+100h+pcbData], r13
0x1400298ab  mov     [rsp+100h+pvData], r15
0x1400298b0  mov     [rsp+100h+pdwType], rdi
0x1400298b5  mov     r9d, 14Eh
0x1400298bb  mov     r8, rbx
0x1400298be  mov     rdx, rax
0x1400298c1  mov     rcx, r14
0x1400298c4  mov     rax, rsi
0x1400298c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400298cc  xor     eax, eax
0x1400298ce  mov     rcx, [rbp+57h+var_40]
0x1400298d2  xor     rcx, rsp; StackCookie
0x1400298d5  call    __security_check_cookie
0x1400298da  mov     rbx, [rsp+100h+arg_18]
0x1400298e2  add     rsp, 0D0h
0x1400298e9  pop     r15
0x1400298eb  pop     r14
0x1400298ed  pop     r13
0x1400298ef  pop     r12
0x1400298f1  pop     rdi
0x1400298f2  pop     rsi
0x1400298f3  pop     rbp
0x1400298f4  retn
```
