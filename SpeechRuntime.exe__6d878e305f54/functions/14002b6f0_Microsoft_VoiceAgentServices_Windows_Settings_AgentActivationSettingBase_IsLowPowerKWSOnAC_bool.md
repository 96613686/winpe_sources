# Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::IsLowPowerKWSOnAC(bool &)

- ea: `0x14002b6f0`
- end: `0x14002baf3`
- name: `?IsLowPowerKWSOnAC@AgentActivationSettingBase@Settings@Windows@VoiceAgentServices@Microsoft@@UEAAJAEA_N@Z`
- size: `1027`
- prototype: `__int64 __fastcall(Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *__hidden this, bool *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140002d30`
- `0x140007c0c`
- `0x14000c32c`
- `0x14000e030`
- `0x140020ff0`
- `0x140021658`
- `0x140027ed4`
- `0x14002b6f0`
- `0x140031010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002ba91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002ba91`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14002b7ef`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14002b7ef`

## string_xrefs

- `0x14002b741`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x14002b9d1`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x14002ba4f`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingbase.cpp`
- `0x14002b730`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::IsLowPowerKWSOnAC`
- `0x14002b9be`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::IsLowPowerKWSOnAC`
- `0x14002ba3c`: `Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::IsLowPowerKWSOnAC`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::IsLowPowerKWSOnAC(
        Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *this,
        bool *a2)
{
  __int64 v4; // rdi
  void (__fastcall *v5)(__int64, _BYTE *, _BYTE *, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *); // rbx
  HRESULT v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, GUID *, __int64, _QWORD); // rbx
  __int64 (__fastcall ***v11)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v12)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v13; // r15
  void (__fastcall *v14)(__int64, _QWORD, __int64, __int64, LPVOID *, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, BOOL); // r14
  BOOL v15; // esi
  int v16; // r8d
  __int64 v17; // rdi
  __int64 v18; // rbx
  __int64 v19; // rax
  __int64 v20; // r14
  void (__fastcall *v21)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, _QWORD); // rsi
  int v22; // r8d
  __int64 v23; // rdi
  __int64 v24; // rbx
  __int64 v25; // rax
  LPVOID *ppv; // [rsp+20h] [rbp-E0h]
  LPVOID pv; // [rsp+58h] [rbp-A8h] BYREF
  __int64 (__fastcall ***v29)(_QWORD, GUID *, __int64 *); // [rsp+60h] [rbp-A0h] BYREF
  __int64 v30; // [rsp+68h] [rbp-98h] BYREF
  int v31; // [rsp+70h] [rbp-90h] BYREF
  int v32; // [rsp+74h] [rbp-8Ch] BYREF
  int v33; // [rsp+78h] [rbp-88h] BYREF
  _BYTE *v34; // [rsp+80h] [rbp-80h] BYREF
  LPVOID v35; // [rsp+88h] [rbp-78h] BYREF
  __int64 v36; // [rsp+90h] [rbp-70h] BYREF
  _BYTE *v37; // [rsp+98h] [rbp-68h]
  _BYTE *v38; // [rsp+A0h] [rbp-60h]
  _BYTE v39[32]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v40[32]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v41[32]; // [rsp+E8h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]

  v4 = *((_QWORD *)this + 47);
  v5 = *(void (__fastcall **)(__int64, _BYTE *, _BYTE *, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *))(*(_QWORD *)v4 + 40LL);
  std::string::string(
    v41,
    "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::IsLowPowerKWSOnAC");
  std::string::string(
    v40,
    "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
  v5(v4, v40, v41, 535, this);
  std::string::~string(v40);
  std::string::~string(v41);
  v36 = 0;
  v29 = 0;
  v30 = 0;
  v35 = 0;
  pv = 0;
  v33 = 0;
  v32 = 0;
  v31 = 0;
  v6 = CoCreateInstance(
         &GUID_bcde0395_e52f_467c_8e3d_c4579291692e,
         0,
         0x17u,
         &GUID_a95664d2_9614_4f35_a746_de8db63617e6,
         &v35);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD, __int64 *))(*(_QWORD *)v35 + 32LL))(v35, 1, 0, &v36);
    v7 = v6;
    if ( v6 >= 0 )
    {
      v9 = v36;
      v10 = *(__int64 (__fastcall **)(__int64, GUID *, __int64, _QWORD))(*(_QWORD *)v36 + 24LL);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v29);
      ppv = (LPVOID *)&v29;
      v6 = v10(v9, &GUID_7ed4ee07_8e67_4cd4_8c1a_2b7a5987ad42, 1, 0);
      v7 = v6;
      if ( v6 >= 0 )
      {
        v6 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), LPVOID *))(*v29)[8])(
               v29,
               &pv);
        v7 = v6;
        if ( v6 >= 0 )
        {
          v11 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v29;
          v12 = **v29;
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v30);
          v6 = v12(v11, &GUID_59ea7369_26c3_4eb9_a3bb_4f7d9b0b6ccb, &v30);
          v7 = v6;
          if ( v6 >= 0 )
          {
            ppv = (LPVOID *)&v31;
            v6 = (*(__int64 (__fastcall **)(__int64, LPVOID, int *, int *))(*(_QWORD *)v30 + 24LL))(v30, pv, &v33, &v32);
            v7 = v6;
            if ( v6 >= 0 )
            {
              LODWORD(v34) = (int)((double)0 * 10000000.0 / (double)*((int *)pv + 1) + 0.5) / 0x2710u;
              *a2 = (unsigned int)v34 >= 0x64;
              Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsTelemetry::IsLowPowerKWSOnAC<unsigned long &>(&v34);
              v13 = *((_QWORD *)this + 47);
              v14 = *(void (__fastcall **)(__int64, _QWORD, __int64, __int64, LPVOID *, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, BOOL))(*(_QWORD *)v13 + 16LL);
              v15 = *a2;
              v34 = v41;
              v17 = std::string::string(v41, "lowPowerKWSOnAC = %d", v16);
              v37 = v40;
              v18 = std::string::string(
                      v40,
                      "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::IsLowPowerKWSOnAC");
              v19 = std::string::string(
                      v39,
                      "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
              LODWORD(ppv) = 552;
              v14(v13, 0, v19, v18, ppv, v17, this, v15);
              v20 = *((_QWORD *)this + 47);
              v21 = *(void (__fastcall **)(__int64, __int64, __int64, __int64, __int64, Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase *, _QWORD))(*(_QWORD *)v20 + 72LL);
              v38 = v39;
              v23 = std::string::string(v39, "hr = 0x%x", v22);
              v37 = v41;
              v24 = std::string::string(
                      v41,
                      "Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingBase::IsLowPowerKWSOnAC");
              v25 = std::string::string(
                      v40,
                      "onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp");
              v21(v20, v25, v24, 553, v23, this, 0);
              v7 = 0;
              goto LABEL_15;
            }
            v8 = 547;
          }
          else
          {
            v8 = 546;
          }
        }
        else
        {
          v8 = 545;
        }
      }
      else
      {
        v8 = 544;
      }
    }
    else
    {
      v8 = 543;
    }
  }
  else
  {
    v8 = 542;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingbase.cpp",
    (const char *)(unsigned int)v6,
    (int)ppv);
LABEL_15:
  CoTaskMemFree(pv);
  pv = 0;
  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v35);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v30);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v29);
  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v36);
  return v7;
}

```

## disassembly

```asm
0x14002b6f0  mov     [rsp-8+arg_10], rbx
0x14002b6f5  mov     [rsp-8+arg_18], rsi
0x14002b6fa  push    rbp
0x14002b6fb  push    rdi
0x14002b6fc  push    r13
0x14002b6fe  push    r14
0x14002b700  push    r15
0x14002b702  lea     rbp, [rsp-10h]
0x14002b707  sub     rsp, 110h
0x14002b70e  mov     rax, cs:__security_cookie
0x14002b715  xor     rax, rsp
0x14002b718  mov     [rbp+30h+var_28], rax
0x14002b71c  mov     rsi, rdx
0x14002b71f  mov     r13, rcx
0x14002b722  mov     rdi, [rcx+178h]
0x14002b729  mov     rax, [rdi]
0x14002b72c  mov     rbx, [rax+28h]
0x14002b730  lea     rdx, aMicrosoftVoice_44; "Microsoft::VoiceAgentServices::Windows:"...
0x14002b737  lea     rcx, [rbp+30h+var_48]
0x14002b73b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002b740  nop
0x14002b741  lea     r14, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002b748  mov     rdx, r14
0x14002b74b  lea     rcx, [rbp+30h+var_68]
0x14002b74f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002b754  nop
0x14002b755  mov     [rsp+130h+ppv], r13
0x14002b75a  mov     r9d, 217h
0x14002b760  lea     r8, [rbp+30h+var_48]
0x14002b764  lea     rdx, [rbp+30h+var_68]
0x14002b768  mov     rcx, rdi
0x14002b76b  mov     rax, rbx
0x14002b76e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002b773  nop
0x14002b774  lea     rcx, [rbp+30h+var_68]
0x14002b778  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002b77d  nop
0x14002b77e  lea     rcx, [rbp+30h+var_48]
0x14002b782  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002b787  mov     [rbp+30h+var_A0], 0
0x14002b78f  mov     [rsp+130h+var_D0], 0
0x14002b798  mov     [rsp+130h+var_C8], 0
0x14002b7a1  mov     [rbp+30h+var_A8], 0
0x14002b7a9  mov     [rsp+130h+pv], 0
0x14002b7b2  mov     [rsp+130h+var_B8], 0
0x14002b7ba  mov     [rsp+130h+var_BC], 0
0x14002b7c2  mov     [rsp+130h+var_C0], 0
0x14002b7ca  mov     [rsp+130h+var_E0], 0
0x14002b7d2  lea     rax, [rbp+30h+var_A8]
0x14002b7d6  mov     [rsp+130h+ppv], rax; int
0x14002b7db  lea     r9, _GUID_a95664d2_9614_4f35_a746_de8db63617e6; riid
0x14002b7e2  xor     edx, edx; pUnkOuter
0x14002b7e4  lea     r8d, [rdx+17h]; dwClsContext
0x14002b7e8  lea     rcx, _GUID_bcde0395_e52f_467c_8e3d_c4579291692e; rclsid
0x14002b7ef  call    cs:__imp_CoCreateInstance
0x14002b7f5  mov     ebx, eax
0x14002b7f7  test    eax, eax
0x14002b7f9  jns     short loc_14002B802
0x14002b7fb  mov     edx, 21Eh
0x14002b800  jmp     short loc_14002B82B
0x14002b802  mov     rcx, [rbp+30h+var_A8]
0x14002b806  mov     rax, [rcx]
0x14002b809  lea     r9, [rbp+30h+var_A0]
0x14002b80d  xor     r8d, r8d
0x14002b810  lea     r15d, [r8+1]
0x14002b814  mov     edx, r15d
0x14002b817  mov     rax, [rax+20h]
0x14002b81b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002b820  mov     ebx, eax
0x14002b822  test    eax, eax
0x14002b824  jns     short loc_14002B83F
0x14002b826  mov     edx, 21Fh; void *
0x14002b82b  mov     r8, r14; unsigned int
0x14002b82e  mov     r9d, eax; char *
0x14002b831  mov     rcx, [rbp+38h]; this
0x14002b835  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002b83a  jmp     loc_14002BA8C
0x14002b83f  mov     rdi, [rbp+30h+var_A0]
0x14002b843  mov     rax, [rdi]
0x14002b846  mov     rbx, [rax+18h]
0x14002b84a  lea     rcx, [rsp+130h+var_D0]
0x14002b84f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x14002b854  lea     rax, [rsp+130h+var_D0]
0x14002b859  mov     [rsp+130h+ppv], rax
0x14002b85e  xor     r9d, r9d
0x14002b861  mov     r8d, r15d
0x14002b864  lea     rdx, _GUID_7ed4ee07_8e67_4cd4_8c1a_2b7a5987ad42
0x14002b86b  mov     rcx, rdi
0x14002b86e  mov     rax, rbx
0x14002b871  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002b876  mov     ebx, eax
0x14002b878  test    eax, eax
0x14002b87a  jns     short loc_14002B883
0x14002b87c  mov     edx, 220h
0x14002b881  jmp     short loc_14002B82B
0x14002b883  mov     rcx, [rsp+130h+var_D0]
0x14002b888  mov     rax, [rcx]
0x14002b88b  lea     rdx, [rsp+130h+pv]
0x14002b890  mov     rax, [rax+40h]
0x14002b894  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002b899  mov     ebx, eax
0x14002b89b  test    eax, eax
0x14002b89d  jns     short loc_14002B8A6
0x14002b89f  mov     edx, 221h
0x14002b8a4  jmp     short loc_14002B82B
0x14002b8a6  mov     rbx, [rsp+130h+var_D0]
0x14002b8ab  mov     rax, [rbx]
0x14002b8ae  mov     rdi, [rax]
0x14002b8b1  lea     rcx, [rsp+130h+var_C8]
0x14002b8b6  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x14002b8bb  lea     r8, [rsp+130h+var_C8]
0x14002b8c0  lea     rdx, _GUID_59ea7369_26c3_4eb9_a3bb_4f7d9b0b6ccb
0x14002b8c7  mov     rcx, rbx
0x14002b8ca  mov     rax, rdi
0x14002b8cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002b8d2  mov     ebx, eax
0x14002b8d4  test    eax, eax
0x14002b8d6  jns     short loc_14002B8E2
0x14002b8d8  mov     edx, 222h
0x14002b8dd  jmp     loc_14002B82B
0x14002b8e2  mov     rcx, [rsp+130h+var_C8]
0x14002b8e7  mov     rax, [rcx]
0x14002b8ea  lea     rdx, [rsp+130h+var_E0]
0x14002b8ef  mov     [rsp+130h+var_108], rdx
0x14002b8f4  lea     rdx, [rsp+130h+var_C0]
0x14002b8f9  mov     [rsp+130h+ppv], rdx
0x14002b8fe  lea     r9, [rsp+130h+var_BC]
0x14002b903  lea     r8, [rsp+130h+var_B8]
0x14002b908  mov     rdx, [rsp+130h+pv]
0x14002b90d  mov     rax, [rax+18h]
0x14002b911  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002b916  mov     ebx, eax
0x14002b918  test    eax, eax
0x14002b91a  jns     short loc_14002B926
0x14002b91c  mov     edx, 223h
0x14002b921  jmp     loc_14002B82B
0x14002b926  mov     eax, [rsp+130h+var_E0]
0x14002b92a  xorps   xmm1, xmm1
0x14002b92d  cvtsi2sd xmm1, rax
0x14002b932  mulsd   xmm1, cs:__real@416312d000000000
0x14002b93a  mov     rax, [rsp+130h+pv]
0x14002b93f  mov     ecx, [rax+4]
0x14002b942  xorps   xmm0, xmm0
0x14002b945  cvtsi2sd xmm0, rcx
0x14002b94a  divsd   xmm1, xmm0
0x14002b94e  addsd   xmm1, cs:__real@3fe0000000000000
0x14002b956  cvttsd2si rcx, xmm1
0x14002b95b  mov     rax, 346DC5D63886594Bh
0x14002b965  imul    rcx
0x14002b968  sar     rdx, 0Bh
0x14002b96c  mov     rax, rdx
0x14002b96f  shr     rax, 3Fh
0x14002b973  add     rdx, rax
0x14002b976  mov     dword ptr [rbp+30h+var_B0], edx
0x14002b979  cmp     edx, 64h ; 'd'
0x14002b97c  setnb   al
0x14002b97f  mov     [rsi], al
0x14002b981  lea     rcx, [rbp+30h+var_B0]
0x14002b985  call    ??$IsLowPowerKWSOnAC@AEAK@AgentActivationSettingsTelemetry@Settings@Windows@VoiceAgentServices@Microsoft@@SAXAEAK@Z; Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingsTelemetry::IsLowPowerKWSOnAC<ulong &>(ulong &)
0x14002b98a  mov     r15, [r13+178h]
0x14002b991  mov     rax, [r15]
0x14002b994  mov     r14, [rax+10h]
0x14002b998  movzx   esi, byte ptr [rsi]
0x14002b99b  lea     rax, [rbp+30h+var_48]
0x14002b99f  mov     [rbp+30h+var_B0], rax
0x14002b9a3  lea     rdx, aLowpowerkwsona; "lowPowerKWSOnAC = %d"
0x14002b9aa  lea     rcx, [rbp+30h+var_48]
0x14002b9ae  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002b9b3  mov     rdi, rax
0x14002b9b6  lea     rax, [rbp+30h+var_68]
0x14002b9ba  mov     [rbp+30h+var_98], rax
0x14002b9be  lea     rdx, aMicrosoftVoice_44; "Microsoft::VoiceAgentServices::Windows:"...
0x14002b9c5  lea     rcx, [rbp+30h+var_68]
0x14002b9c9  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002b9ce  mov     rbx, rax
0x14002b9d1  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002b9d8  lea     rcx, [rbp+30h+var_88]
0x14002b9dc  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002b9e1  nop
0x14002b9e2  mov     [rsp+130h+var_F8], esi
0x14002b9e6  mov     [rsp+130h+var_100], r13
0x14002b9eb  mov     [rsp+130h+var_108], rdi
0x14002b9f0  mov     dword ptr [rsp+130h+ppv], 228h
0x14002b9f8  mov     r9, rbx
0x14002b9fb  mov     r8, rax
0x14002b9fe  xor     edx, edx
0x14002ba00  mov     rcx, r15
0x14002ba03  mov     rax, r14
0x14002ba06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002ba0b  mov     r14, [r13+178h]
0x14002ba12  mov     rax, [r14]
0x14002ba15  mov     rsi, [rax+48h]
0x14002ba19  lea     rax, [rbp+30h+var_88]
0x14002ba1d  mov     [rbp+30h+var_90], rax
0x14002ba21  lea     rdx, aHr0xX; "hr = 0x%x"
0x14002ba28  lea     rcx, [rbp+30h+var_88]
0x14002ba2c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002ba31  mov     rdi, rax
0x14002ba34  lea     rax, [rbp+30h+var_48]
0x14002ba38  mov     [rbp+30h+var_98], rax
0x14002ba3c  lea     rdx, aMicrosoftVoice_44; "Microsoft::VoiceAgentServices::Windows:"...
0x14002ba43  lea     rcx, [rbp+30h+var_48]
0x14002ba47  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002ba4c  mov     rbx, rax
0x14002ba4f  lea     rdx, aOnecoreuapEndu_28; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002ba56  lea     rcx, [rbp+30h+var_68]
0x14002ba5a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002ba5f  nop
0x14002ba60  mov     [rsp+130h+var_100], 0
0x14002ba69  mov     [rsp+130h+var_108], r13
0x14002ba6e  mov     [rsp+130h+ppv], rdi
0x14002ba73  mov     r9d, 229h
0x14002ba79  mov     r8, rbx
0x14002ba7c  mov     rdx, rax
0x14002ba7f  mov     rcx, r14
0x14002ba82  mov     rax, rsi
0x14002ba85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002ba8a  xor     ebx, ebx
0x14002ba8c  mov     rcx, [rsp+130h+pv]; pv
0x14002ba91  call    cs:__imp_CoTaskMemFree
0x14002ba97  mov     [rsp+130h+pv], 0
0x14002baa0  lea     rcx, [rbp+30h+var_A8]
0x14002baa4  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x14002baa9  nop
0x14002baaa  lea     rcx, [rsp+130h+var_C8]
0x14002baaf  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x14002bab4  nop
0x14002bab5  lea     rcx, [rsp+130h+var_D0]
0x14002baba  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x14002babf  nop
0x14002bac0  lea     rcx, [rbp+30h+var_A0]
0x14002bac4  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x14002bac9  mov     eax, ebx
0x14002bacb  mov     rcx, [rbp+30h+var_28]
0x14002bacf  xor     rcx, rsp; StackCookie
0x14002bad2  call    __security_check_cookie
0x14002bad7  lea     r11, [rsp+130h+var_20]
0x14002badf  mov     rbx, [r11+40h]
0x14002bae3  mov     rsi, [r11+48h]
0x14002bae7  mov     rsp, r11
0x14002baea  pop     r15
0x14002baec  pop     r14
0x14002baee  pop     r13
0x14002baf0  pop     rdi
0x14002baf1  pop     rbp
0x14002baf2  retn
```
