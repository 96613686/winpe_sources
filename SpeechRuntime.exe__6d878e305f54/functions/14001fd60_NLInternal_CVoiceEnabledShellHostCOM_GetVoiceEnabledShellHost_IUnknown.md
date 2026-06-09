# NLInternal::CVoiceEnabledShellHostCOM::GetVoiceEnabledShellHost(IUnknown * *)

- ea: `0x14001fd60`
- end: `0x14001fe4a`
- name: `?GetVoiceEnabledShellHost@CVoiceEnabledShellHostCOM@NLInternal@@UEAAJPEAPEAUIUnknown@@@Z`
- size: `234`
- prototype: `__int64 __fastcall(NLInternal::CVoiceEnabledShellHostCOM *__hidden this, struct IUnknown **)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x14000c32c`
- `0x140011ea8`
- `0x14001fadc`
- `0x14001fd60`
- `0x140031010`

## string_xrefs

- `0x14001fda7`: `onecoreuap\enduser\nui\onecore\speechruntime\voiceenabledshellhost\voiceenabledshellhostcom.cpp(18)`
- `0x14001fe0a`: `onecoreuap\enduser\nui\onecore\speechruntime\voiceenabledshellhost\voiceenabledshellhostcom.cpp(19)`
- `0x14001fdb3`: `NLInternal::CVoiceEnabledShellHostCOM::GetVoiceEnabledShellHost`

## pseudocode

```c
__int64 __fastcall NLInternal::CVoiceEnabledShellHostCOM::GetVoiceEnabledShellHost(
        NLInternal::CVoiceEnabledShellHostCOM *this,
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
  v3 = Microsoft::WRL::Details::MakeAndInitialize<NLInternal::CVoiceEnabledShellHost,NLInternal::CVoiceEnabledShellHost,>(&v11);
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
        L"NLInternal::CVoiceEnabledShellHostCOM::GetVoiceEnabledShellHost",
        L"onecoreuap\\enduser\\nui\\onecore\\speechruntime\\voiceenabledshellhost\\voiceenabledshellhostcom.cpp(19)",
        v7);
    }
  }
  else
  {
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      &NLInternal::s_tracingPrefix,
      L"NLInternal::CVoiceEnabledShellHostCOM::GetVoiceEnabledShellHost",
      L"onecoreuap\\enduser\\nui\\onecore\\speechruntime\\voiceenabledshellhost\\voiceenabledshellhostcom.cpp(18)",
      v3);
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v11);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v10);
  return v4;
}

```

## disassembly

```asm
0x14001fd60  mov     rax, rsp
0x14001fd63  mov     [rax+8], rbx
0x14001fd67  mov     [rax+20h], rsi
0x14001fd6b  push    rdi
0x14001fd6c  sub     rsp, 30h
0x14001fd70  mov     rsi, rdx
0x14001fd73  mov     qword ptr [rdx], 0
0x14001fd7a  mov     qword ptr [rax+10h], 0
0x14001fd82  mov     qword ptr [rax+18h], 0
0x14001fd8a  lea     rcx, [rax+18h]
0x14001fd8e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x14001fd93  lea     rcx, [rsp+38h+arg_10]
0x14001fd98  call    ??$MakeAndInitialize@VCVoiceEnabledShellHost@NLInternal@@V12@$$V@Details@WRL@Microsoft@@YAJPEAPEAVCVoiceEnabledShellHost@NLInternal@@@Z; Microsoft::WRL::Details::MakeAndInitialize<NLInternal::CVoiceEnabledShellHost,NLInternal::CVoiceEnabledShellHost,>(NLInternal::CVoiceEnabledShellHost * *)
0x14001fd9d  mov     ebx, eax
0x14001fd9f  test    eax, eax
0x14001fda1  jns     short loc_14001FDD4
0x14001fda3  mov     [rsp+38h+var_10], eax
0x14001fda7  lea     rax, aOnecoreuapEndu_82; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x14001fdae  mov     [rsp+38h+var_18], rax
0x14001fdb3  lea     r9, aNlinternalCvoi_11; "NLInternal::CVoiceEnabledShellHostCOM::"...
0x14001fdba  lea     r8, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x14001fdc1  lea     rdx, aSfunctionSFile; "%Sfunction=%S, fileline=%S, hr=0x%08x\n"
0x14001fdc8  mov     ecx, 2; int
0x14001fdcd  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14001fdd2  jmp     short loc_14001FE24
0x14001fdd4  mov     rbx, [rsp+38h+arg_10]
0x14001fdd9  mov     rax, [rbx]
0x14001fddc  mov     rdi, [rax]
0x14001fddf  lea     rcx, [rsp+38h+arg_8]
0x14001fde4  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x14001fde9  lea     r8, [rsp+38h+arg_8]
0x14001fdee  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x14001fdf5  mov     rcx, rbx
0x14001fdf8  mov     rax, rdi
0x14001fdfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001fe00  mov     ebx, eax
0x14001fe02  test    eax, eax
0x14001fe04  jns     short loc_14001FE13
0x14001fe06  mov     [rsp+38h+var_10], eax
0x14001fe0a  lea     rax, aOnecoreuapEndu_81; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x14001fe11  jmp     short loc_14001FDAE
0x14001fe13  mov     rax, [rsp+38h+arg_8]
0x14001fe18  mov     [rsp+38h+arg_8], 0
0x14001fe21  mov     [rsi], rax
0x14001fe24  lea     rcx, [rsp+38h+arg_10]
0x14001fe29  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x14001fe2e  lea     rcx, [rsp+38h+arg_8]
0x14001fe33  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x14001fe38  mov     eax, ebx
0x14001fe3a  mov     rbx, [rsp+38h+arg_0]
0x14001fe3f  mov     rsi, [rsp+38h+arg_18]
0x14001fe44  add     rsp, 30h
0x14001fe48  pop     rdi
0x14001fe49  retn
```
