# NLInternal::CVoiceActivationControllerCOM::GetVoiceActivationController(IUnknown * *)

- ea: `0x140019890`
- end: `0x14001997a`
- name: `?GetVoiceActivationController@CVoiceActivationControllerCOM@NLInternal@@UEAAJPEAPEAUIUnknown@@@Z`
- size: `234`
- prototype: `__int64 __fastcall(NLInternal::CVoiceActivationControllerCOM *__hidden this, struct IUnknown **)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x14000c32c`
- `0x140011ea8`
- `0x1400197c0`
- `0x140019890`
- `0x140031010`

## string_xrefs

- `0x1400198d7`: `onecoreuap\enduser\nui\onecore\speechruntime\voiceactivation\voiceactivationcontrollercom.cpp(36)`
- `0x1400198e3`: `NLInternal::CVoiceActivationControllerCOM::GetVoiceActivationController`
- `0x14001993a`: `onecoreuap\enduser\nui\onecore\speechruntime\voiceactivation\voiceactivationcontrollercom.cpp(37)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NLInternal::CVoiceActivationControllerCOM::GetVoiceActivationController(
        NLInternal::CVoiceActivationControllerCOM *this,
        struct IUnknown **a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  __int64 (__fastcall ***v5)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v6)(_QWORD, GUID *, struct IUnknown **); // rdi
  int v7; // eax
  struct IUnknown *v8; // rax
  struct IUnknown *v10; // [rsp+48h] [rbp+10h] BYREF
  __int64 (__fastcall ***v11)(_QWORD, GUID *, struct IUnknown **); // [rsp+50h] [rbp+18h] BYREF

  *a2 = 0;
  v10 = 0;
  v11 = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v11);
  v3 = Microsoft::WRL::Details::MakeAndInitialize<NLInternal::CVoiceActivationController,NLInternal::CVoiceActivationController,>(&v11);
  v4 = v3;
  if ( v3 >= 0 )
  {
    v5 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v11;
    v6 = **v11;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v10);
    v7 = v6(v5, &GUID_00000000_0000_0000_c000_000000000046, &v10);
    v4 = v7;
    if ( v7 >= 0 )
    {
      v8 = v10;
      v10 = 0;
      *a2 = v8;
    }
    else
    {
      DoTraceMessage(
        2,
        "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
        &NLInternal::s_tracingPrefix,
        L"NLInternal::CVoiceActivationControllerCOM::GetVoiceActivationController",
        L"onecoreuap\\enduser\\nui\\onecore\\speechruntime\\voiceactivation\\voiceactivationcontrollercom.cpp(37)",
        v7);
    }
  }
  else
  {
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      &NLInternal::s_tracingPrefix,
      L"NLInternal::CVoiceActivationControllerCOM::GetVoiceActivationController",
      L"onecoreuap\\enduser\\nui\\onecore\\speechruntime\\voiceactivation\\voiceactivationcontrollercom.cpp(36)",
      v3);
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v11);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v10);
  return v4;
}

```

## disassembly

```asm
0x140019890  mov     rax, rsp
0x140019893  mov     [rax+8], rbx
0x140019897  mov     [rax+20h], rsi
0x14001989b  push    rdi
0x14001989c  sub     rsp, 30h
0x1400198a0  mov     rsi, rdx
0x1400198a3  mov     qword ptr [rdx], 0
0x1400198aa  mov     qword ptr [rax+10h], 0
0x1400198b2  mov     qword ptr [rax+18h], 0
0x1400198ba  lea     rcx, [rax+18h]
0x1400198be  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1400198c3  lea     rcx, [rsp+38h+arg_10]
0x1400198c8  call    ??$MakeAndInitialize@VCVoiceActivationController@NLInternal@@V12@$$V@Details@WRL@Microsoft@@YAJPEAPEAVCVoiceActivationController@NLInternal@@@Z; Microsoft::WRL::Details::MakeAndInitialize<NLInternal::CVoiceActivationController,NLInternal::CVoiceActivationController,>(NLInternal::CVoiceActivationController * *)
0x1400198cd  mov     ebx, eax
0x1400198cf  test    eax, eax
0x1400198d1  jns     short loc_140019904
0x1400198d3  mov     [rsp+38h+var_10], eax
0x1400198d7  lea     rax, aOnecoreuapEndu_71; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x1400198de  mov     [rsp+38h+var_18], rax
0x1400198e3  lea     r9, aNlinternalCvoi; "NLInternal::CVoiceActivationControllerC"...
0x1400198ea  lea     r8, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x1400198f1  lea     rdx, aSfunctionSFile; "%Sfunction=%S, fileline=%S, hr=0x%08x\n"
0x1400198f8  mov     ecx, 2; int
0x1400198fd  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x140019902  jmp     short loc_140019954
0x140019904  mov     rbx, [rsp+38h+arg_10]
0x140019909  mov     rax, [rbx]
0x14001990c  mov     rdi, [rax]
0x14001990f  lea     rcx, [rsp+38h+arg_8]
0x140019914  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x140019919  lea     r8, [rsp+38h+arg_8]
0x14001991e  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x140019925  mov     rcx, rbx
0x140019928  mov     rax, rdi
0x14001992b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019930  mov     ebx, eax
0x140019932  test    eax, eax
0x140019934  jns     short loc_140019943
0x140019936  mov     [rsp+38h+var_10], eax
0x14001993a  lea     rax, aOnecoreuapEndu_6; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x140019941  jmp     short loc_1400198DE
0x140019943  mov     rax, [rsp+38h+arg_8]
0x140019948  mov     [rsp+38h+arg_8], 0
0x140019951  mov     [rsi], rax
0x140019954  lea     rcx, [rsp+38h+arg_10]
0x140019959  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x14001995e  lea     rcx, [rsp+38h+arg_8]
0x140019963  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x140019968  mov     eax, ebx
0x14001996a  mov     rbx, [rsp+38h+arg_0]
0x14001996f  mov     rsi, [rsp+38h+arg_18]
0x140019974  add     rsp, 30h
0x140019978  pop     rdi
0x140019979  retn
```
