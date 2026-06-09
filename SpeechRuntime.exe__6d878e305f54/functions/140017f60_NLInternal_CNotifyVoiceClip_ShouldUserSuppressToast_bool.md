# NLInternal::CNotifyVoiceClip::ShouldUserSuppressToast(bool *)

- ea: `0x140017f60`
- end: `0x1400180d2`
- name: `?ShouldUserSuppressToast@CNotifyVoiceClip@NLInternal@@CAJPEA_N@Z`
- size: `370`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140018460`

## callees

- `0x14000c32c`
- `0x14000e030`
- `0x1400152cc`
- `0x140017f60`
- `0x140031010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140017fa4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140017fa4`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall NLInternal::CNotifyVoiceClip::ShouldUserSuppressToast(bool *a1)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  LPVOID v4; // rdi
  __int64 (__fastcall *v5)(LPVOID, _QWORD, _QWORD); // rbx
  int v6; // eax
  HSTRING *v7; // r8
  struct Windows::System::IUser *v8; // rcx
  __int64 (__fastcall ***v9)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v10)(_QWORD, GUID *, struct Windows::System::IUser **); // rdi
  int AuthorityForUser; // eax
  __int64 v12; // rdx
  int ppv; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+20h]
  bool v16; // [rsp+60h] [rbp+28h] BYREF
  __int64 (__fastcall ***v17)(_QWORD, GUID *, struct Windows::System::IUser **); // [rsp+68h] [rbp+30h] BYREF
  struct Windows::System::IUser *v18; // [rsp+70h] [rbp+38h] BYREF
  LPVOID v19; // [rsp+78h] [rbp+40h] BYREF

  *a1 = 0;
  v16 = 0;
  v19 = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v19);
  v2 = CoCreateInstance(
         &GUID_ff99e1c1_7f9a_4c83_8a57_305992edd07b,
         0,
         5u,
         &GUID_ef2b1603_8f77_4e22_9200_bb8d2f3a58ed,
         &v19);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v17 = 0;
    v4 = v19;
    v5 = *(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD))(*(_QWORD *)v19 + 24LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v17);
    v6 = v5(v4, &v17, 0);
    v3 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x45,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechruntime\\toastnotifier\\sendtoastnotification.cpp",
        (const char *)(unsigned int)v6,
        ppv);
LABEL_5:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v17);
      goto LABEL_14;
    }
    v8 = 0;
    v18 = 0;
    v9 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v17;
    if ( v17 )
    {
      v10 = **v17;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v18);
      AuthorityForUser = v10(v9, &GUID_df9a26c6_e746_4bcd_b5d4_120103c4209b, &v18);
      v3 = AuthorityForUser;
      if ( AuthorityForUser < 0 )
      {
        v12 = 73;
LABEL_9:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v12,
          (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechruntime\\toastnotifier\\sendtoastnotification.cpp",
          (const char *)(unsigned int)AuthorityForUser,
          ppv);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v18);
        goto LABEL_5;
      }
      v8 = v18;
    }
    AuthorityForUser = Microsoft::Authentication::Validation::FindAuthorityForUser(v8, &v16, v7);
    v3 = AuthorityForUser;
    if ( AuthorityForUser >= 0 )
    {
      *a1 = !v16;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v18);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v17);
      v3 = 0;
      goto LABEL_14;
    }
    v12 = 75;
    goto LABEL_9;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x43,
    (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechruntime\\toastnotifier\\sendtoastnotification.cpp",
    (const char *)(unsigned int)v2,
    ppv);
LABEL_14:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v19);
  return v3;
}

```

## disassembly

```asm
0x140017f60  push    rbp
0x140017f62  push    rbx
0x140017f63  push    rsi
0x140017f64  push    rdi
0x140017f65  mov     rbp, rsp
0x140017f68  sub     rsp, 38h
0x140017f6c  mov     rsi, rcx
0x140017f6f  mov     byte ptr [rcx], 0
0x140017f72  mov     [rbp+arg_0], 0
0x140017f76  mov     [rbp+arg_18], 0
0x140017f7e  lea     rcx, [rbp+arg_18]
0x140017f82  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x140017f87  lea     rax, [rbp+arg_18]
0x140017f8b  mov     qword ptr [rsp+38h+ppv], rax; int
0x140017f90  lea     r9, _GUID_ef2b1603_8f77_4e22_9200_bb8d2f3a58ed; riid
0x140017f97  xor     edx, edx; pUnkOuter
0x140017f99  lea     r8d, [rdx+5]; dwClsContext
0x140017f9d  lea     rcx, _GUID_ff99e1c1_7f9a_4c83_8a57_305992edd07b; rclsid
0x140017fa4  call    cs:__imp_CoCreateInstance
0x140017faa  mov     ebx, eax
0x140017fac  test    eax, eax
0x140017fae  jns     short loc_140017FCD
0x140017fb0  mov     rcx, [rbp+20h]; this
0x140017fb4  mov     r9d, eax; char *
0x140017fb7  lea     r8, aOnecoreuapEndu_102; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x140017fbe  mov     edx, 43h ; 'C'; void *
0x140017fc3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140017fc8  jmp     loc_1400180BE
0x140017fcd  mov     [rbp+arg_8], 0
0x140017fd5  mov     rdi, [rbp+arg_18]
0x140017fd9  mov     rax, [rdi]
0x140017fdc  mov     rbx, [rax+18h]
0x140017fe0  lea     rcx, [rbp+arg_8]
0x140017fe4  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x140017fe9  xor     r8d, r8d
0x140017fec  lea     rdx, [rbp+arg_8]
0x140017ff0  mov     rcx, rdi
0x140017ff3  mov     rax, rbx
0x140017ff6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017ffb  mov     ebx, eax
0x140017ffd  test    eax, eax
0x140017fff  jns     short loc_140018028
0x140018001  mov     rcx, [rbp+20h]; this
0x140018005  mov     r9d, eax; char *
0x140018008  lea     r8, aOnecoreuapEndu_102; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x14001800f  mov     edx, 45h ; 'E'; void *
0x140018014  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140018019  nop
0x14001801a  lea     rcx, [rbp+arg_8]
0x14001801e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x140018023  jmp     loc_1400180BE
0x140018028  xor     ecx, ecx
0x14001802a  mov     [rbp+arg_10], rcx
0x14001802e  mov     rbx, [rbp+arg_8]
0x140018032  test    rbx, rbx
0x140018035  jz      short loc_14001808A
0x140018037  mov     rax, [rbx]
0x14001803a  mov     rdi, [rax]
0x14001803d  lea     rcx, [rbp+arg_10]
0x140018041  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x140018046  lea     r8, [rbp+arg_10]
0x14001804a  lea     rdx, _GUID_df9a26c6_e746_4bcd_b5d4_120103c4209b
0x140018051  mov     rcx, rbx
0x140018054  mov     rax, rdi
0x140018057  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001805c  mov     ebx, eax
0x14001805e  test    eax, eax
0x140018060  jns     short loc_140018086
0x140018062  mov     edx, 49h ; 'I'; void *
0x140018067  lea     r8, aOnecoreuapEndu_102; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x14001806e  mov     r9d, eax; char *
0x140018071  mov     rcx, [rbp+20h]; this
0x140018075  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001807a  nop
0x14001807b  lea     rcx, [rbp+arg_10]
0x14001807f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x140018084  jmp     short loc_14001801A
0x140018086  mov     rcx, [rbp+arg_10]; struct Windows::System::IUser *
0x14001808a  lea     rdx, [rbp+arg_0]; bool *
0x14001808e  call    ?FindAuthorityForUser@Validation@Authentication@Microsoft@@SAJPEAUIUser@System@Windows@@PEA_NPEAPEAUHSTRING__@@@Z; Microsoft::Authentication::Validation::FindAuthorityForUser(Windows::System::IUser *,bool *,HSTRING__ * *)
0x140018093  mov     ebx, eax
0x140018095  test    eax, eax
0x140018097  jns     short loc_1400180A0
0x140018099  mov     edx, 4Bh ; 'K'
0x14001809e  jmp     short loc_140018067
0x1400180a0  cmp     [rbp+arg_0], 0
0x1400180a4  setz    al
0x1400180a7  mov     [rsi], al
0x1400180a9  lea     rcx, [rbp+arg_10]
0x1400180ad  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1400180b2  nop
0x1400180b3  lea     rcx, [rbp+arg_8]
0x1400180b7  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1400180bc  xor     ebx, ebx
0x1400180be  lea     rcx, [rbp+arg_18]
0x1400180c2  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1400180c7  mov     eax, ebx
0x1400180c9  add     rsp, 38h
0x1400180cd  pop     rdi
0x1400180ce  pop     rsi
0x1400180cf  pop     rbx
0x1400180d0  pop     rbp
0x1400180d1  retn
```
