# NLInternal::CSharedRecoActivationCustomMarshallerCOM::GetSharedRecoCustomMarshaller(IUnknown * *)

- ea: `0x14001ec30`
- end: `0x14001ed1a`
- name: `?GetSharedRecoCustomMarshaller@CSharedRecoActivationCustomMarshallerCOM@NLInternal@@UEAAJPEAPEAUIUnknown@@@Z`
- size: `234`
- prototype: `__int64 __fastcall(NLInternal::CSharedRecoActivationCustomMarshallerCOM *__hidden this, struct IUnknown **)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x14000c32c`
- `0x140011ea8`
- `0x14001ead8`
- `0x14001ec30`
- `0x140031010`

## string_xrefs

- `0x14001ec83`: `NLInternal::CSharedRecoActivationCustomMarshallerCOM::GetSharedRecoCustomMarshaller`
- `0x14001ec77`: `onecoreuap\enduser\nui\onecore\speechruntime\sharedrecosvr\sharedrecocustommarshallercom.cpp(28)`
- `0x14001ecda`: `onecoreuap\enduser\nui\onecore\speechruntime\sharedrecosvr\sharedrecocustommarshallercom.cpp(29)`

## pseudocode

```c
__int64 __fastcall NLInternal::CSharedRecoActivationCustomMarshallerCOM::GetSharedRecoCustomMarshaller(
        NLInternal::CSharedRecoActivationCustomMarshallerCOM *this,
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
  v3 = Microsoft::WRL::Details::MakeAndInitialize<NLInternal::CSharedRecoCustomMarshaller,NLInternal::CSharedRecoCustomMarshaller,>(&v11);
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
        L"NLInternal::CSharedRecoActivationCustomMarshallerCOM::GetSharedRecoCustomMarshaller",
        L"onecoreuap\\enduser\\nui\\onecore\\speechruntime\\sharedrecosvr\\sharedrecocustommarshallercom.cpp(29)",
        v7);
    }
  }
  else
  {
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      &NLInternal::s_tracingPrefix,
      L"NLInternal::CSharedRecoActivationCustomMarshallerCOM::GetSharedRecoCustomMarshaller",
      L"onecoreuap\\enduser\\nui\\onecore\\speechruntime\\sharedrecosvr\\sharedrecocustommarshallercom.cpp(28)",
      v3);
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v11);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v10);
  return v4;
}

```

## disassembly

```asm
0x14001ec30  mov     rax, rsp
0x14001ec33  mov     [rax+8], rbx
0x14001ec37  mov     [rax+20h], rsi
0x14001ec3b  push    rdi
0x14001ec3c  sub     rsp, 30h
0x14001ec40  mov     rsi, rdx
0x14001ec43  mov     qword ptr [rdx], 0
0x14001ec4a  mov     qword ptr [rax+10h], 0
0x14001ec52  mov     qword ptr [rax+18h], 0
0x14001ec5a  lea     rcx, [rax+18h]
0x14001ec5e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x14001ec63  lea     rcx, [rsp+38h+arg_10]
0x14001ec68  call    ??$MakeAndInitialize@VCSharedRecoCustomMarshaller@NLInternal@@V12@$$V@Details@WRL@Microsoft@@YAJPEAPEAVCSharedRecoCustomMarshaller@NLInternal@@@Z; Microsoft::WRL::Details::MakeAndInitialize<NLInternal::CSharedRecoCustomMarshaller,NLInternal::CSharedRecoCustomMarshaller,>(NLInternal::CSharedRecoCustomMarshaller * *)
0x14001ec6d  mov     ebx, eax
0x14001ec6f  test    eax, eax
0x14001ec71  jns     short loc_14001ECA4
0x14001ec73  mov     [rsp+38h+var_10], eax
0x14001ec77  lea     rax, aOnecoreuapEndu_38; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x14001ec7e  mov     [rsp+38h+var_18], rax
0x14001ec83  lea     r9, aNlinternalCsha_5; "NLInternal::CSharedRecoActivationCustom"...
0x14001ec8a  lea     r8, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x14001ec91  lea     rdx, aSfunctionSFile; "%Sfunction=%S, fileline=%S, hr=0x%08x\n"
0x14001ec98  mov     ecx, 2; int
0x14001ec9d  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14001eca2  jmp     short loc_14001ECF4
0x14001eca4  mov     rbx, [rsp+38h+arg_10]
0x14001eca9  mov     rax, [rbx]
0x14001ecac  mov     rdi, [rax]
0x14001ecaf  lea     rcx, [rsp+38h+arg_8]
0x14001ecb4  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x14001ecb9  lea     r8, [rsp+38h+arg_8]
0x14001ecbe  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x14001ecc5  mov     rcx, rbx
0x14001ecc8  mov     rax, rdi
0x14001eccb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ecd0  mov     ebx, eax
0x14001ecd2  test    eax, eax
0x14001ecd4  jns     short loc_14001ECE3
0x14001ecd6  mov     [rsp+38h+var_10], eax
0x14001ecda  lea     rax, aOnecoreuapEndu_94; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x14001ece1  jmp     short loc_14001EC7E
0x14001ece3  mov     rax, [rsp+38h+arg_8]
0x14001ece8  mov     [rsp+38h+arg_8], 0
0x14001ecf1  mov     [rsi], rax
0x14001ecf4  lea     rcx, [rsp+38h+arg_10]
0x14001ecf9  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x14001ecfe  lea     rcx, [rsp+38h+arg_8]
0x14001ed03  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x14001ed08  mov     eax, ebx
0x14001ed0a  mov     rbx, [rsp+38h+arg_0]
0x14001ed0f  mov     rsi, [rsp+38h+arg_18]
0x14001ed14  add     rsp, 30h
0x14001ed18  pop     rdi
0x14001ed19  retn
```
