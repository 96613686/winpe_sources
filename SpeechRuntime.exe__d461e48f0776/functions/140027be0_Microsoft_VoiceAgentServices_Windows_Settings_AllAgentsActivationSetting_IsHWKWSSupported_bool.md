# Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting::IsHWKWSSupported(bool &)

- ea: `0x140027be0`
- end: `0x140027ecb`
- name: `?IsHWKWSSupported@AllAgentsActivationSetting@Settings@Windows@VoiceAgentServices@Microsoft@@UEAAJAEA_N@Z`
- size: `747`
- prototype: `__int64 __fastcall(Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting *__hidden this, bool *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140002d30`
- `0x140007c0c`
- `0x14000e030`
- `0x140020ff0`
- `0x140021658`
- `0x140027be0`
- `0x140031010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140027e69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140027e7d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140027e69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140027e7d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140027cb9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140027cb9`
- `MMDevAPI!__imp_mmdDevGetInterfaceIdFromMMDevice` at `0x140027d12`
- `MMDevAPI!__imp_mmdDevGetInterfaceIdFromMMDevice` at `0x140027d12`
- `MMDevAPI!__imp_mmdDevGetRelatedInterfaceId` at `0x140027d3f`
- `MMDevAPI!__imp_mmdDevGetRelatedInterfaceId` at `0x140027d3f`

## string_xrefs

- `0x140027c31`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\allagentsactivationsetting.cpp`
- `0x140027da5`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\allagentsactivationsetting.cpp`
- `0x140027e27`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\allagentsactivationsetting.cpp`
- `0x140027c20`: `Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting::IsHWKWSSupported`
- `0x140027d92`: `Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting::IsHWKWSSupported`
- `0x140027e14`: `Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting::IsHWKWSSupported`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting::IsHWKWSSupported(
        Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting *this,
        bool *a2)
{
  __int64 v4; // rdi
  void (__fastcall *v5)(__int64, _OWORD *, _BYTE *, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting *); // rbx
  HRESULT InterfaceIdFromMMDevice; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  int v9; // r8d
  bool v10; // si
  __int64 v11; // r15
  void (__fastcall *v12)(__int64, _QWORD, __int64, __int64, int, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting *, bool); // r14
  __int64 v13; // rdi
  __int64 v14; // rbx
  __int64 v15; // rax
  __int64 v16; // r14
  void (__fastcall *v17)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting *, _QWORD); // rsi
  int v18; // r8d
  __int64 v19; // rdi
  __int64 v20; // rbx
  __int64 v21; // rax
  int ppv; // [rsp+20h] [rbp-E0h]
  LPVOID pv; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID v25; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID v26; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v27[2]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE *v28; // [rsp+78h] [rbp-88h]
  _BYTE v29[32]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v30[32]; // [rsp+A0h] [rbp-60h] BYREF
  _OWORD v31[2]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v32[32]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]

  v4 = *((_QWORD *)this + 47);
  v5 = *(void (__fastcall **)(__int64, _OWORD *, _BYTE *, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting *))(*(_QWORD *)v4 + 40LL);
  std::string::string(
    v32,
    "Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting::IsHWKWSSupported");
  std::string::string(
    v31,
    "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\allagentsactivationsetting.cpp");
  v5(v4, v31, v32, 70, this);
  std::string::~string(v31);
  std::string::~string(v32);
  v27[0] = 0;
  v26 = 0;
  v25 = 0;
  pv = 0;
  InterfaceIdFromMMDevice = CoCreateInstance(
                              &GUID_bcde0395_e52f_467c_8e3d_c4579291692e,
                              0,
                              0x17u,
                              &GUID_a95664d2_9614_4f35_a746_de8db63617e6,
                              &v26);
  v7 = InterfaceIdFromMMDevice;
  if ( InterfaceIdFromMMDevice >= 0 )
  {
    InterfaceIdFromMMDevice = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD, _QWORD *))(*(_QWORD *)v26 + 32LL))(
                                v26,
                                1,
                                0,
                                v27);
    v7 = InterfaceIdFromMMDevice;
    if ( InterfaceIdFromMMDevice >= 0 )
    {
      InterfaceIdFromMMDevice = mmdDevGetInterfaceIdFromMMDevice(v27[0], &pv);
      v7 = InterfaceIdFromMMDevice;
      if ( InterfaceIdFromMMDevice >= 0 )
      {
        v31[0] = DEVINTERFACE_AUDIO_KEYWORDDETECTOR;
        InterfaceIdFromMMDevice = mmdDevGetRelatedInterfaceId(pv, v31, &v25);
        v7 = InterfaceIdFromMMDevice;
        if ( InterfaceIdFromMMDevice >= 0 )
        {
          v10 = v25 != 0;
          *a2 = v25 != 0;
          v11 = *((_QWORD *)this + 47);
          v12 = *(void (__fastcall **)(__int64, _QWORD, __int64, __int64, int, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting *, bool))(*(_QWORD *)v11 + 16LL);
          v27[1] = v32;
          v13 = std::string::string(v32, "HWKWSSupported = %d", v9);
          v28 = v29;
          v14 = std::string::string(
                  v29,
                  "Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting::IsHWKWSSupported");
          v15 = std::string::string(
                  v30,
                  "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\allagentsactivationsetting.cpp");
          v12(v11, 0, v15, v14, 80, v13, this, v10);
          v16 = *((_QWORD *)this + 47);
          v17 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting *, _QWORD))(*(_QWORD *)v16 + 72LL);
          *(_QWORD *)&v31[0] = v30;
          v19 = std::string::string(v30, "hr = 0x%x", v18);
          v28 = v29;
          v20 = std::string::string(
                  v29,
                  "Microsoft::VoiceAgentServices::Windows::Settings::AllAgentsActivationSetting::IsHWKWSSupported");
          v21 = std::string::string(
                  v32,
                  "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\allagentsactivationsetting.cpp");
          v17(v16, v21, v20, 81, v19, this, 0);
          v7 = 0;
          goto LABEL_11;
        }
        v8 = 78;
      }
      else
      {
        v8 = 77;
      }
    }
    else
    {
      v8 = 76;
    }
  }
  else
  {
    v8 = 75;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\allagentsactivationsetting.cpp",
    (const char *)(unsigned int)InterfaceIdFromMMDevice,
    ppv);
LABEL_11:
  CoTaskMemFree(pv);
  pv = 0;
  CoTaskMemFree(v25);
  v25 = 0;
  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v26);
  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(v27);
  return v7;
}

```

## disassembly

```asm
0x140027be0  mov     [rsp-8+arg_10], rbx
0x140027be5  mov     [rsp-8+arg_18], rsi
0x140027bea  push    rbp
0x140027beb  push    rdi
0x140027bec  push    r13
0x140027bee  push    r14
0x140027bf0  push    r15
0x140027bf2  lea     rbp, [rsp-10h]
0x140027bf7  sub     rsp, 110h
0x140027bfe  mov     rax, cs:__security_cookie
0x140027c05  xor     rax, rsp
0x140027c08  mov     [rbp+30h+var_30], rax
0x140027c0c  mov     r14, rdx
0x140027c0f  mov     r13, rcx
0x140027c12  mov     rdi, [rcx+178h]
0x140027c19  mov     rax, [rdi]
0x140027c1c  mov     rbx, [rax+28h]
0x140027c20  lea     rdx, aMicrosoftVoice_40; "Microsoft::VoiceAgentServices::Windows:"...
0x140027c27  lea     rcx, [rbp+30h+var_50]
0x140027c2b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140027c30  nop
0x140027c31  lea     rsi, aOnecoreuapEndu_75; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140027c38  mov     rdx, rsi
0x140027c3b  lea     rcx, [rbp+30h+var_70]
0x140027c3f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140027c44  nop
0x140027c45  mov     [rsp+130h+ppv], r13
0x140027c4a  mov     r9d, 46h ; 'F'
0x140027c50  lea     r8, [rbp+30h+var_50]
0x140027c54  lea     rdx, [rbp+30h+var_70]
0x140027c58  mov     rcx, rdi
0x140027c5b  mov     rax, rbx
0x140027c5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027c63  nop
0x140027c64  lea     rcx, [rbp+30h+var_70]
0x140027c68  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140027c6d  nop
0x140027c6e  lea     rcx, [rbp+30h+var_50]
0x140027c72  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140027c77  mov     [rsp+130h+var_C8], 0
0x140027c80  mov     [rsp+130h+var_D0], 0
0x140027c89  mov     [rsp+130h+var_D8], 0
0x140027c92  mov     [rsp+130h+pv], 0
0x140027c9b  lea     rax, [rsp+130h+var_D0]
0x140027ca0  mov     [rsp+130h+ppv], rax; int
0x140027ca5  lea     r9, _GUID_a95664d2_9614_4f35_a746_de8db63617e6; riid
0x140027cac  xor     edx, edx; pUnkOuter
0x140027cae  lea     r8d, [rdx+17h]; dwClsContext
0x140027cb2  lea     rcx, _GUID_bcde0395_e52f_467c_8e3d_c4579291692e; rclsid
0x140027cb9  call    cs:__imp_CoCreateInstance
0x140027cbf  mov     ebx, eax
0x140027cc1  test    eax, eax
0x140027cc3  jns     short loc_140027CCC
0x140027cc5  mov     edx, 4Bh ; 'K'
0x140027cca  jmp     short loc_140027CF4
0x140027ccc  mov     rcx, [rsp+130h+var_D0]
0x140027cd1  mov     rax, [rcx]
0x140027cd4  lea     r9, [rsp+130h+var_C8]
0x140027cd9  xor     r8d, r8d
0x140027cdc  lea     edx, [r8+1]
0x140027ce0  mov     rax, [rax+20h]
0x140027ce4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027ce9  mov     ebx, eax
0x140027ceb  test    eax, eax
0x140027ced  jns     short loc_140027D08
0x140027cef  mov     edx, 4Ch ; 'L'; void *
0x140027cf4  mov     r8, rsi; unsigned int
0x140027cf7  mov     r9d, eax; char *
0x140027cfa  mov     rcx, [rbp+38h]; this
0x140027cfe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140027d03  jmp     loc_140027E64
0x140027d08  lea     rdx, [rsp+130h+pv]
0x140027d0d  mov     rcx, [rsp+130h+var_C8]
0x140027d12  call    cs:__imp_mmdDevGetInterfaceIdFromMMDevice
0x140027d18  mov     ebx, eax
0x140027d1a  test    eax, eax
0x140027d1c  jns     short loc_140027D25
0x140027d1e  mov     edx, 4Dh ; 'M'
0x140027d23  jmp     short loc_140027CF4
0x140027d25  movups  xmm0, cs:DEVINTERFACE_AUDIO_KEYWORDDETECTOR
0x140027d2c  movdqu  [rbp+30h+var_70], xmm0
0x140027d31  lea     r8, [rsp+130h+var_D8]
0x140027d36  lea     rdx, [rbp+30h+var_70]
0x140027d3a  mov     rcx, [rsp+130h+pv]
0x140027d3f  call    cs:__imp_mmdDevGetRelatedInterfaceId
0x140027d45  mov     ebx, eax
0x140027d47  test    eax, eax
0x140027d49  jns     short loc_140027D52
0x140027d4b  mov     edx, 4Eh ; 'N'
0x140027d50  jmp     short loc_140027CF4
0x140027d52  cmp     [rsp+130h+var_D8], 0
0x140027d58  setnz   sil
0x140027d5c  mov     [r14], sil
0x140027d5f  mov     r15, [r13+178h]
0x140027d66  mov     rax, [r15]
0x140027d69  mov     r14, [rax+10h]
0x140027d6d  lea     rax, [rbp+30h+var_50]
0x140027d71  mov     [rsp+130h+var_C0], rax
0x140027d76  lea     rdx, aHwkwssupported; "HWKWSSupported = %d"
0x140027d7d  lea     rcx, [rbp+30h+var_50]
0x140027d81  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140027d86  mov     rdi, rax
0x140027d89  lea     rax, [rbp+30h+var_B0]
0x140027d8d  mov     [rsp+130h+var_B8], rax
0x140027d92  lea     rdx, aMicrosoftVoice_40; "Microsoft::VoiceAgentServices::Windows:"...
0x140027d99  lea     rcx, [rbp+30h+var_B0]
0x140027d9d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140027da2  mov     rbx, rax
0x140027da5  lea     rdx, aOnecoreuapEndu_75; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140027dac  lea     rcx, [rbp+30h+var_90]
0x140027db0  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140027db5  movzx   edx, sil
0x140027db9  mov     [rsp+130h+var_F8], edx
0x140027dbd  mov     [rsp+130h+var_100], r13
0x140027dc2  mov     [rsp+130h+var_108], rdi
0x140027dc7  mov     dword ptr [rsp+130h+ppv], 50h ; 'P'
0x140027dcf  mov     r9, rbx
0x140027dd2  mov     r8, rax
0x140027dd5  xor     edx, edx
0x140027dd7  mov     rcx, r15
0x140027dda  mov     rax, r14
0x140027ddd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027de2  mov     r14, [r13+178h]
0x140027de9  mov     rax, [r14]
0x140027dec  mov     rsi, [rax+48h]
0x140027df0  lea     rax, [rbp+30h+var_90]
0x140027df4  mov     qword ptr [rbp+30h+var_70], rax
0x140027df8  lea     rdx, aHr0xX; "hr = 0x%x"
0x140027dff  lea     rcx, [rbp+30h+var_90]
0x140027e03  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140027e08  mov     rdi, rax
0x140027e0b  lea     rax, [rbp+30h+var_B0]
0x140027e0f  mov     [rsp+130h+var_B8], rax
0x140027e14  lea     rdx, aMicrosoftVoice_40; "Microsoft::VoiceAgentServices::Windows:"...
0x140027e1b  lea     rcx, [rbp+30h+var_B0]
0x140027e1f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140027e24  mov     rbx, rax
0x140027e27  lea     rdx, aOnecoreuapEndu_75; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140027e2e  lea     rcx, [rbp+30h+var_50]
0x140027e32  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140027e37  nop
0x140027e38  mov     [rsp+130h+var_100], 0
0x140027e41  mov     [rsp+130h+var_108], r13
0x140027e46  mov     [rsp+130h+ppv], rdi
0x140027e4b  mov     r9d, 51h ; 'Q'
0x140027e51  mov     r8, rbx
0x140027e54  mov     rdx, rax
0x140027e57  mov     rcx, r14
0x140027e5a  mov     rax, rsi
0x140027e5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140027e62  xor     ebx, ebx
0x140027e64  mov     rcx, [rsp+130h+pv]; pv
0x140027e69  call    cs:__imp_CoTaskMemFree
0x140027e6f  mov     [rsp+130h+pv], 0
0x140027e78  mov     rcx, [rsp+130h+var_D8]; pv
0x140027e7d  call    cs:__imp_CoTaskMemFree
0x140027e83  mov     [rsp+130h+var_D8], 0
0x140027e8c  lea     rcx, [rsp+130h+var_D0]
0x140027e91  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x140027e96  nop
0x140027e97  lea     rcx, [rsp+130h+var_C8]
0x140027e9c  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x140027ea1  mov     eax, ebx
0x140027ea3  mov     rcx, [rbp+30h+var_30]
0x140027ea7  xor     rcx, rsp; StackCookie
0x140027eaa  call    __security_check_cookie
0x140027eaf  lea     r11, [rsp+130h+var_20]
0x140027eb7  mov     rbx, [r11+40h]
0x140027ebb  mov     rsi, [r11+48h]
0x140027ebf  mov     rsp, r11
0x140027ec2  pop     r15
0x140027ec4  pop     r14
0x140027ec6  pop     r13
0x140027ec8  pop     rdi
0x140027ec9  pop     rbp
0x140027eca  retn
```
