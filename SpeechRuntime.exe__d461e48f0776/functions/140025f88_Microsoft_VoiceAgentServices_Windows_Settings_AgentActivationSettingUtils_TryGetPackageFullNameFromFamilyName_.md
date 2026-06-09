# Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingUtils::TryGetPackageFullNameFromFamilyName(HSTRING__ *,HSTRING__ * *)

- ea: `0x140025f88`
- end: `0x1400261e2`
- name: `?TryGetPackageFullNameFromFamilyName@AgentActivationSettingUtils@Settings@Windows@VoiceAgentServices@Microsoft@@CAJPEAUHSTRING__@@PEAPEAU6@@Z`
- size: `602`
- prototype: `__int64 __fastcall(HSTRING, HSTRING *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140025884`

## callees

- `0x140002d30`
- `0x14000aab8`
- `0x14000c32c`
- `0x14000e030`
- `0x140025f88`
- `0x140031010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140026000`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140026000`

## string_xrefs

- `0x140026013`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingutils.cpp`
- `0x140026072`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingutils.cpp`
- `0x140026100`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingutils.cpp`
- `0x140026155`: `onecoreuap\enduser\nui\onecore\agentactivationruntime\settings\agentactivationsettingutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Microsoft::VoiceAgentServices::Windows::Settings::AgentActivationSettingUtils::TryGetPackageFullNameFromFamilyName(
        HSTRING a1,
        HSTRING *a2)
{
  __int64 v4; // rbx
  int ActivationFactory; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, _QWORD, HSTRING, __int64); // rbx
  int v9; // eax
  __int64 v10; // rdx
  int v11; // eax
  __int64 v12; // rcx
  int v13; // eax
  __int64 v14; // rcx
  __int64 v15; // rcx
  int v17; // [rsp+20h] [rbp-60h]
  int v18[2]; // [rsp+30h] [rbp-50h] BYREF
  __int64 v19; // [rsp+38h] [rbp-48h] BYREF
  unsigned int v20; // [rsp+40h] [rbp-40h] BYREF
  __int64 v21; // [rsp+48h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-30h] BYREF
  __int64 v23; // [rsp+68h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  *a2 = 0;
  v21 = 0;
  v23 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.StateRepository.Package",
    0x29u,
    0x28u);
  v4 = v23;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v21);
  ActivationFactory = RoGetActivationFactory(v4, &GUID_0450ce77_af0d_40ac_93fd_1e5d48c89419, &v21);
  v6 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCF,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingutils.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v17);
    goto LABEL_22;
  }
  *(_QWORD *)v18 = 0;
  v7 = v21;
  v8 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING, __int64))(*(_QWORD *)v21 + 424LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v18);
  v9 = v8(v7, 0, a1, 1);
  v6 = v9;
  if ( v9 < 0 )
  {
    v10 = 210;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingutils.cpp",
      (const char *)(unsigned int)v9,
      (int)v18);
LABEL_6:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v18);
    goto LABEL_22;
  }
  v20 = 0;
  v9 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)v18 + 56LL))(*(_QWORD *)v18, &v20);
  v6 = v9;
  if ( v9 < 0 )
  {
    v10 = 213;
    goto LABEL_5;
  }
  if ( v20 > 1 )
  {
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v18);
    v6 = -2147467259;
    goto LABEL_22;
  }
  v19 = 0;
  v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))(**(_QWORD **)v18 + 48LL))(*(_QWORD *)v18, 0, &v19);
  v6 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDE,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingutils.cpp",
      (const char *)(unsigned int)v11,
      (int)v18);
    v12 = v19;
    if ( v19 )
    {
      v19 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
    goto LABEL_6;
  }
  v13 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v19 + 112LL))(v19, a2);
  v6 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDF,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\agentactivationruntime\\settings\\agentactivationsettingutils.cpp",
      (const char *)(unsigned int)v13,
      (int)v18);
    v14 = v19;
    if ( v19 )
    {
      v19 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    goto LABEL_6;
  }
  v15 = v19;
  if ( v19 )
  {
    v19 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v18);
  v6 = 0;
LABEL_22:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v21);
  return v6;
}

```

## disassembly

```asm
0x140025f88  mov     [rsp-18h+arg_10], rbx
0x140025f8d  mov     [rsp-18h+arg_18], rsi
0x140025f92  push    rbp
0x140025f93  push    rdi
0x140025f94  push    r14
0x140025f96  mov     rbp, rsp
0x140025f99  sub     rsp, 80h
0x140025fa0  mov     rax, cs:__security_cookie
0x140025fa7  xor     rax, rsp
0x140025faa  mov     [rbp+var_10], rax
0x140025fae  mov     rsi, rdx
0x140025fb1  mov     r14, rcx
0x140025fb4  mov     qword ptr [rdx], 0
0x140025fbb  mov     [rbp+var_38], 0
0x140025fc3  mov     [rbp+var_18], 0
0x140025fcb  mov     r9d, 28h ; '('; unsigned int
0x140025fd1  lea     r8d, [r9+1]; unsigned int
0x140025fd5  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_Package@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x140025fdc  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x140025fe0  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x140025fe5  mov     rbx, [rbp+var_18]
0x140025fe9  lea     rcx, [rbp+var_38]
0x140025fed  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x140025ff2  lea     r8, [rbp+var_38]
0x140025ff6  lea     rdx, _GUID_0450ce77_af0d_40ac_93fd_1e5d48c89419
0x140025ffd  mov     rcx, rbx
0x140026000  call    cs:__imp_RoGetActivationFactory
0x140026006  mov     ebx, eax
0x140026008  test    eax, eax
0x14002600a  jns     short loc_140026029
0x14002600c  mov     rcx, [rbp+18h]; this
0x140026010  mov     r9d, eax; char *
0x140026013  lea     r8, aOnecoreuapEndu_42; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002601a  mov     edx, 0CFh; void *
0x14002601f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140026024  jmp     loc_1400261B3
0x140026029  mov     qword ptr [rbp+var_50], 0
0x140026031  mov     rdi, [rbp+var_38]
0x140026035  mov     rax, [rdi]
0x140026038  mov     rbx, [rax+1A8h]
0x14002603f  lea     rcx, [rbp+var_50]
0x140026043  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x140026048  lea     rax, [rbp+var_50]
0x14002604c  mov     qword ptr [rsp+80h+var_60], rax; int
0x140026051  mov     r9d, 1
0x140026057  mov     r8, r14
0x14002605a  xor     edx, edx
0x14002605c  mov     rcx, rdi
0x14002605f  mov     rax, rbx
0x140026062  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026067  mov     ebx, eax
0x140026069  test    eax, eax
0x14002606b  jns     short loc_140026094
0x14002606d  mov     edx, 0D2h; void *
0x140026072  lea     r8, aOnecoreuapEndu_42; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140026079  mov     r9d, eax; char *
0x14002607c  mov     rcx, [rbp+18h]; this
0x140026080  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140026085  nop
0x140026086  lea     rcx, [rbp+var_50]
0x14002608a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x14002608f  jmp     loc_1400261B3
0x140026094  mov     [rbp+var_40], 0
0x14002609b  mov     rcx, qword ptr [rbp+var_50]
0x14002609f  mov     rax, [rcx]
0x1400260a2  lea     rdx, [rbp+var_40]
0x1400260a6  mov     rax, [rax+38h]
0x1400260aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400260af  mov     ebx, eax
0x1400260b1  test    eax, eax
0x1400260b3  jns     short loc_1400260BC
0x1400260b5  mov     edx, 0D5h
0x1400260ba  jmp     short loc_140026072
0x1400260bc  cmp     [rbp+var_40], 1
0x1400260c0  jbe     short loc_1400260D5
0x1400260c2  lea     rcx, [rbp+var_50]
0x1400260c6  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1400260cb  mov     ebx, 80004005h
0x1400260d0  jmp     loc_1400261B3
0x1400260d5  mov     [rbp+var_48], 0
0x1400260dd  mov     rcx, qword ptr [rbp+var_50]
0x1400260e1  mov     rax, [rcx]
0x1400260e4  lea     r8, [rbp+var_48]
0x1400260e8  xor     edx, edx
0x1400260ea  mov     rax, [rax+30h]
0x1400260ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400260f3  mov     ebx, eax
0x1400260f5  test    eax, eax
0x1400260f7  jns     short loc_140026135
0x1400260f9  mov     rcx, [rbp+18h]; this
0x1400260fd  mov     r9d, eax; char *
0x140026100  lea     r8, aOnecoreuapEndu_42; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x140026107  mov     edx, 0DEh; void *
0x14002610c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140026111  nop
0x140026112  mov     rcx, [rbp+var_48]
0x140026116  test    rcx, rcx
0x140026119  jz      short loc_140026130
0x14002611b  mov     [rbp+var_48], 0
0x140026123  mov     rax, [rcx]
0x140026126  mov     rax, [rax+10h]
0x14002612a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002612f  nop
0x140026130  jmp     loc_140026086
0x140026135  mov     rcx, [rbp+var_48]
0x140026139  mov     rax, [rcx]
0x14002613c  mov     rdx, rsi
0x14002613f  mov     rax, [rax+70h]
0x140026143  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026148  mov     ebx, eax
0x14002614a  test    eax, eax
0x14002614c  jns     short loc_14002618A
0x14002614e  mov     rcx, [rbp+18h]; this
0x140026152  mov     r9d, eax; char *
0x140026155  lea     r8, aOnecoreuapEndu_42; "onecoreuap\\enduser\\nui\\onecore\\agen"...
0x14002615c  mov     edx, 0DFh; void *
0x140026161  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140026166  nop
0x140026167  mov     rcx, [rbp+var_48]
0x14002616b  test    rcx, rcx
0x14002616e  jz      short loc_140026185
0x140026170  mov     [rbp+var_48], 0
0x140026178  mov     rax, [rcx]
0x14002617b  mov     rax, [rax+10h]
0x14002617f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026184  nop
0x140026185  jmp     loc_140026086
0x14002618a  mov     rcx, [rbp+var_48]
0x14002618e  test    rcx, rcx
0x140026191  jz      short loc_1400261A8
0x140026193  mov     [rbp+var_48], 0
0x14002619b  mov     rax, [rcx]
0x14002619e  mov     rax, [rax+10h]
0x1400261a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400261a7  nop
0x1400261a8  lea     rcx, [rbp+var_50]
0x1400261ac  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1400261b1  xor     ebx, ebx
0x1400261b3  lea     rcx, [rbp+var_38]
0x1400261b7  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1400261bc  mov     eax, ebx
0x1400261be  mov     rcx, [rbp+var_10]
0x1400261c2  xor     rcx, rsp; StackCookie
0x1400261c5  call    __security_check_cookie
0x1400261ca  lea     r11, [rsp+80h+var_s0]
0x1400261d2  mov     rbx, [r11+30h]
0x1400261d6  mov     rsi, [r11+38h]
0x1400261da  mov     rsp, r11
0x1400261dd  pop     r14
0x1400261df  pop     rdi
0x1400261e0  pop     rbp
0x1400261e1  retn
```
