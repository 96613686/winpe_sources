# CredUXParameters::RuntimeClassInitialize(CredUXParametersBlob *,Windows::Internal::UI::Credentials::Controller::ICredUXExtension *,Windows::Internal::UI::Credentials::Controller::IConsentUXContext *,Windows::Internal::UI::Credentials::Controller::ICredUXSecurePrompt *)

- ea: `0x140013ae4`
- end: `0x140013e43`
- name: `?RuntimeClassInitialize@CredUXParameters@@QEAAJPEAUCredUXParametersBlob@@PEAUICredUXExtension@Controller@Credentials@UI@Internal@Windows@@PEAUIConsentUXContext@45678@PEAUICredUXSecurePrompt@45678@@Z`
- size: `863`
- prototype: `__int64 __fastcall(CredUXParameters *this, struct CredUXParametersBlob *, struct Windows::Internal::UI::Credentials::Controller::ICredUXExtension *, struct Windows::Internal::UI::Credentials::Controller::IConsentUXContext *, struct Windows::Internal::UI::Credentials::Controller::ICredUXSecurePrompt *)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140005d0c`

## callees

- `0x140005f10`
- `0x140006f10`
- `0x14000e8fc`
- `0x14000e920`
- `0x14000eaac`
- `0x1400136fc`
- `0x140013ae4`
- `0x140018498`
- `0x1400186c0`
- `0x14001877c`
- `0x140018888`
- `0x14001894c`
- `0x140018a00`
- `0x140018ac0`
- `0x14001f010`

## string_xrefs

- `0x140013c39`: `shellcommon\internal\shell\inc\creduxparameters.h`
- `0x140013db4`: `shellcommon\internal\shell\inc\creduxparameters.h`

## pseudocode

```c
__int64 __fastcall CredUXParameters::RuntimeClassInitialize(
        CredUXParameters *this,
        struct CredUXParametersBlob *a2,
        struct Windows::Internal::UI::Credentials::Controller::ICredUXExtension *a3,
        struct Windows::Internal::UI::Credentials::Controller::IConsentUXContext *a4,
        struct Windows::Internal::UI::Credentials::Controller::ICredUXSecurePrompt *a5)
{
  __int64 v9; // rcx
  __int64 v10; // rcx
  struct Windows::Internal::UI::Credentials::Controller::ICredUXSecurePrompt *v11; // rbx
  __int64 v12; // rcx
  char v13; // r14
  __int64 v14; // rbp
  _OWORD *v15; // rax
  _OWORD *v16; // rax
  int v17; // ebx
  __int64 v18; // rdx
  __int64 v20; // rax
  int v21; // eax
  __int64 v22; // rdx
  int v23; // ecx
  int v24; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  struct Windows::Internal::UI::Credentials::Controller::IConsentUXContext *v26; // [rsp+60h] [rbp+8h] BYREF

  if ( *((struct Windows::Internal::UI::Credentials::Controller::ICredUXExtension **)this + 24) != a3 )
  {
    if ( a3 )
      (*(void (__fastcall **)(struct Windows::Internal::UI::Credentials::Controller::ICredUXExtension *))(*(_QWORD *)a3 + 8LL))(a3);
    v9 = *((_QWORD *)this + 24);
    *((_QWORD *)this + 24) = a3;
    if ( v9 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  if ( *((struct Windows::Internal::UI::Credentials::Controller::IConsentUXContext **)this + 25) != a4 )
  {
    v26 = a4;
    Microsoft::WRL::ComPtr<Windows::Internal::UI::Credentials::Controller::ICredUXSecurePrompt>::InternalAddRef(&v26);
    v10 = *((_QWORD *)this + 25);
    *((_QWORD *)this + 25) = a4;
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
  v11 = a5;
  if ( *((struct Windows::Internal::UI::Credentials::Controller::ICredUXSecurePrompt **)this + 26) != a5 )
  {
    Microsoft::WRL::ComPtr<Windows::Internal::UI::Credentials::Controller::ICredUXSecurePrompt>::InternalAddRef(&a5);
    v12 = *((_QWORD *)this + 26);
    *((_QWORD *)this + 26) = v11;
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  }
  v13 = 1;
  *((_DWORD *)this + 16) = *((_DWORD *)a2 + 16);
  *((_DWORD *)this + 17) = *((_DWORD *)a2 + 15) & 0xF7FFFFFF;
  *((_DWORD *)this + 18) = *(_DWORD *)a2;
  *((_BYTE *)this + 120) = *((_DWORD *)a2 + 13) != 0;
  *((_BYTE *)this + 121) = *((_DWORD *)a2 + 14) != 0;
  v14 = *((_QWORD *)a2 + 2);
  if ( v14 )
  {
    v15 = *(_OWORD **)(v14 + 72);
    if ( v15 )
      *(_OWORD *)((char *)this + 152) = *v15;
    v16 = *(_OWORD **)(v14 + 112);
    if ( v16 )
      *(_OWORD *)((char *)this + 168) = *v16;
    if ( *(_QWORD *)(v14 + 40) )
    {
      v17 = Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>((char *)this + 104);
      if ( v17 < 0 )
      {
        v18 = 99;
LABEL_20:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v18,
          (unsigned int)"shellcommon\\internal\\shell\\inc\\creduxparameters.h",
          (const char *)(unsigned int)v17,
          v24);
        return (unsigned int)v17;
      }
    }
    if ( *(_QWORD *)(v14 + 48) )
    {
      v17 = Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>((char *)this + 80);
      if ( v17 < 0 )
      {
        v18 = 104;
        goto LABEL_20;
      }
    }
    if ( *(_QWORD *)(v14 + 104) )
    {
      v17 = Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>((char *)this + 112);
      if ( v17 < 0 )
      {
        v18 = 109;
        goto LABEL_20;
      }
    }
    if ( *(_QWORD *)(v14 + 8) )
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 216);
      v17 = Microsoft::WRL::Details::MakeAndInitialize<WindowContainer,IInspectable,HWND__ * &>(
              (char *)this + 216,
              v14 + 8);
      if ( v17 < 0 )
      {
        v18 = 114;
        goto LABEL_20;
      }
    }
    *((_BYTE *)this + 122) = (*(_DWORD *)(v14 + 32) & 0x1000) != 0;
    *((_BYTE *)this + 127) = (*(_DWORD *)(v14 + 32) & 0x2000) != 0;
    *((_BYTE *)this + 123) = (*(_DWORD *)(v14 + 32) & 0x20000) != 0;
    *((_BYTE *)this + 124) = (*(_DWORD *)(v14 + 32) & 0x40000) != 0;
    *((_BYTE *)this + 128) = (*(_DWORD *)(v14 + 32) & 0x80000) != 0;
  }
  v17 = CredUXParameters::_SetupErrorText(this, a2);
  if ( v17 < 0 )
  {
    v18 = 125;
    goto LABEL_20;
  }
  v17 = CredUXParameters::_SetupCaptionText(this, a2);
  if ( v17 < 0 )
  {
    v18 = 126;
    goto LABEL_20;
  }
  v17 = CredUXParameters::_SetupMessageText(this, a2);
  if ( v17 < 0 )
  {
    v18 = 127;
    goto LABEL_20;
  }
  v17 = CredUXParameters::_SetupInputBuffer(this, a2);
  if ( v17 < 0 )
  {
    v18 = 128;
    goto LABEL_20;
  }
  v17 = CredUXParameters::_SetupAuthContext(this, a2);
  if ( v17 < 0 )
  {
    v18 = 129;
    goto LABEL_20;
  }
  v20 = *((_QWORD *)a2 + 2);
  if ( v20 )
  {
    if ( !IsWideStringEmpty(*(const unsigned __int16 *const *)(v20 + 104)) )
    {
      v21 = Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>((char *)this + 112);
      v17 = v21;
      if ( v21 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x279,
          (unsigned int)"shellcommon\\internal\\shell\\inc\\creduxparameters.h",
          (const char *)(unsigned int)v21,
          v24);
        v18 = 130;
        goto LABEL_20;
      }
    }
  }
  v17 = CredUXParameters::_SetupContextObject(this, a2);
  if ( v17 < 0 )
  {
    v18 = 131;
    goto LABEL_20;
  }
  v17 = CredUXParameters::_SetupfooterLink(this, a2);
  if ( v17 < 0 )
  {
    v18 = 132;
    goto LABEL_20;
  }
  v22 = *((_QWORD *)a2 + 2);
  if ( v22 )
  {
    v23 = *(_DWORD *)(v22 + 32);
    *((_BYTE *)this + 126) = (v23 & 0x10000) != 0;
    if ( (v23 & 0x10000) == 0 || (*(_DWORD *)(v22 + 32) & 0x8000) == 0 )
      v13 = 0;
    *((_BYTE *)this + 125) = v13;
  }
  return 0;
}

```

## disassembly

```asm
0x140013ae4  push    rbx
0x140013ae6  push    rbp
0x140013ae7  push    rsi
0x140013ae8  push    rdi
0x140013ae9  push    r14
0x140013aeb  push    r15
0x140013aed  sub     rsp, 28h
0x140013af1  mov     rbp, r9
0x140013af4  mov     rbx, r8
0x140013af7  mov     rsi, rdx
0x140013afa  mov     rdi, rcx
0x140013afd  cmp     [rcx+0C0h], r8
0x140013b04  jz      short loc_140013B39
0x140013b06  test    rbx, rbx
0x140013b09  jz      short loc_140013B1A
0x140013b0b  mov     rax, [r8]
0x140013b0e  mov     rcx, rbx
0x140013b11  mov     rax, [rax+8]
0x140013b15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013b1a  mov     rcx, [rdi+0C0h]
0x140013b21  mov     [rdi+0C0h], rbx
0x140013b28  test    rcx, rcx
0x140013b2b  jz      short loc_140013B39
0x140013b2d  mov     rax, [rcx]
0x140013b30  mov     rax, [rax+10h]
0x140013b34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013b39  cmp     [rdi+0C8h], rbp
0x140013b40  jz      short loc_140013B70
0x140013b42  lea     rcx, [rsp+58h+arg_0]
0x140013b47  mov     [rsp+58h+arg_0], rbp
0x140013b4c  call    ?InternalAddRef@?$ComPtr@UICredUXSecurePrompt@Controller@Credentials@UI@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Credentials::Controller::ICredUXSecurePrompt>::InternalAddRef(void)
0x140013b51  mov     rcx, [rdi+0C8h]
0x140013b58  mov     [rdi+0C8h], rbp
0x140013b5f  test    rcx, rcx
0x140013b62  jz      short loc_140013B70
0x140013b64  mov     rax, [rcx]
0x140013b67  mov     rax, [rax+10h]
0x140013b6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013b70  mov     rbx, [rsp+58h+arg_20]
0x140013b78  cmp     [rdi+0D0h], rbx
0x140013b7f  jz      short loc_140013BB5
0x140013b81  lea     rcx, [rsp+58h+arg_20]
0x140013b89  mov     [rsp+58h+arg_20], rbx
0x140013b91  call    ?InternalAddRef@?$ComPtr@UICredUXSecurePrompt@Controller@Credentials@UI@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Credentials::Controller::ICredUXSecurePrompt>::InternalAddRef(void)
0x140013b96  mov     rcx, [rdi+0D0h]
0x140013b9d  mov     [rdi+0D0h], rbx
0x140013ba4  test    rcx, rcx
0x140013ba7  jz      short loc_140013BB5
0x140013ba9  mov     rax, [rcx]
0x140013bac  mov     rax, [rax+10h]
0x140013bb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013bb5  mov     eax, [rsi+40h]
0x140013bb8  mov     r14b, 1
0x140013bbb  mov     [rdi+40h], eax
0x140013bbe  mov     eax, [rsi+3Ch]
0x140013bc1  btr     eax, 1Bh
0x140013bc5  mov     [rdi+44h], eax
0x140013bc8  mov     eax, [rsi]
0x140013bca  mov     [rdi+48h], eax
0x140013bcd  cmp     dword ptr [rsi+34h], 0
0x140013bd1  setnz   al
0x140013bd4  mov     [rdi+78h], al
0x140013bd7  cmp     dword ptr [rsi+38h], 0
0x140013bdb  setnz   al
0x140013bde  mov     [rdi+79h], al
0x140013be1  mov     rbp, [rsi+10h]
0x140013be5  test    rbp, rbp
0x140013be8  jz      loc_140013D00
0x140013bee  mov     rax, [rbp+48h]
0x140013bf2  test    rax, rax
0x140013bf5  jz      short loc_140013C02
0x140013bf7  movups  xmm0, xmmword ptr [rax]
0x140013bfa  movdqu  xmmword ptr [rdi+98h], xmm0
0x140013c02  mov     rax, [rbp+70h]
0x140013c06  test    rax, rax
0x140013c09  jz      short loc_140013C16
0x140013c0b  movups  xmm0, xmmword ptr [rax]
0x140013c0e  movdqu  xmmword ptr [rdi+0A8h], xmm0
0x140013c16  lea     rdx, [rbp+28h]
0x140013c1a  cmp     qword ptr [rdx], 0
0x140013c1e  jz      short loc_140013C4F
0x140013c20  lea     rcx, [rdi+68h]
0x140013c24  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x140013c29  mov     ebx, eax
0x140013c2b  test    eax, eax
0x140013c2d  jns     short loc_140013C4F
0x140013c2f  mov     edx, 63h ; 'c'; void *
0x140013c34  mov     rcx, [rsp+58h]; this
0x140013c39  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\cred"...
0x140013c40  mov     r9d, ebx; char *
0x140013c43  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140013c48  mov     eax, ebx
0x140013c4a  jmp     loc_140013E36
0x140013c4f  lea     rdx, [rbp+30h]
0x140013c53  cmp     qword ptr [rdx], 0
0x140013c57  jz      short loc_140013C6F
0x140013c59  lea     rcx, [rdi+50h]
0x140013c5d  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x140013c62  mov     ebx, eax
0x140013c64  test    eax, eax
0x140013c66  jns     short loc_140013C6F
0x140013c68  mov     edx, 68h ; 'h'
0x140013c6d  jmp     short loc_140013C34
0x140013c6f  lea     rdx, [rbp+68h]
0x140013c73  cmp     qword ptr [rdx], 0
0x140013c77  jz      short loc_140013C8F
0x140013c79  lea     rcx, [rdi+70h]
0x140013c7d  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x140013c82  mov     ebx, eax
0x140013c84  test    eax, eax
0x140013c86  jns     short loc_140013C8F
0x140013c88  mov     edx, 6Dh ; 'm'
0x140013c8d  jmp     short loc_140013C34
0x140013c8f  cmp     qword ptr [rbp+8], 0
0x140013c94  jz      short loc_140013CC1
0x140013c96  lea     rbx, [rdi+0D8h]
0x140013c9d  mov     rcx, rbx
0x140013ca0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140013ca5  lea     rdx, [rbp+8]
0x140013ca9  mov     rcx, rbx
0x140013cac  call    ??$MakeAndInitialize@VWindowContainer@@UIInspectable@@AEAPEAUHWND__@@@Details@WRL@Microsoft@@YAJPEAPEAUIInspectable@@AEAPEAUHWND__@@@Z; Microsoft::WRL::Details::MakeAndInitialize<WindowContainer,IInspectable,HWND__ * &>(IInspectable * *,HWND__ * &)
0x140013cb1  mov     ebx, eax
0x140013cb3  test    eax, eax
0x140013cb5  jns     short loc_140013CC1
0x140013cb7  mov     edx, 72h ; 'r'
0x140013cbc  jmp     loc_140013C34
0x140013cc1  mov     eax, [rbp+20h]
0x140013cc4  shr     eax, 0Ch
0x140013cc7  and     al, r14b
0x140013cca  mov     [rdi+7Ah], al
0x140013ccd  mov     eax, [rbp+20h]
0x140013cd0  shr     eax, 0Dh
0x140013cd3  and     al, r14b
0x140013cd6  mov     [rdi+7Fh], al
0x140013cd9  mov     eax, [rbp+20h]
0x140013cdc  shr     eax, 11h
0x140013cdf  and     al, r14b
0x140013ce2  mov     [rdi+7Bh], al
0x140013ce5  mov     eax, [rbp+20h]
0x140013ce8  shr     eax, 12h
0x140013ceb  and     al, r14b
0x140013cee  mov     [rdi+7Ch], al
0x140013cf1  mov     eax, [rbp+20h]
0x140013cf4  shr     eax, 13h
0x140013cf7  and     al, r14b
0x140013cfa  mov     [rdi+80h], al
0x140013d00  mov     rdx, rsi; struct CredUXParametersBlob *
0x140013d03  mov     rcx, rdi; this
0x140013d06  call    ?_SetupErrorText@CredUXParameters@@AEAAJPEBUCredUXParametersBlob@@@Z; CredUXParameters::_SetupErrorText(CredUXParametersBlob const *)
0x140013d0b  mov     ebx, eax
0x140013d0d  test    eax, eax
0x140013d0f  jns     short loc_140013D1B
0x140013d11  mov     edx, 7Dh ; '}'
0x140013d16  jmp     loc_140013C34
0x140013d1b  mov     rdx, rsi; struct CredUXParametersBlob *
0x140013d1e  mov     rcx, rdi; this
0x140013d21  call    ?_SetupCaptionText@CredUXParameters@@AEAAJPEBUCredUXParametersBlob@@@Z; CredUXParameters::_SetupCaptionText(CredUXParametersBlob const *)
0x140013d26  mov     ebx, eax
0x140013d28  test    eax, eax
0x140013d2a  jns     short loc_140013D36
0x140013d2c  mov     edx, 7Eh ; '~'
0x140013d31  jmp     loc_140013C34
0x140013d36  mov     rdx, rsi; struct CredUXParametersBlob *
0x140013d39  mov     rcx, rdi; this
0x140013d3c  call    ?_SetupMessageText@CredUXParameters@@AEAAJPEBUCredUXParametersBlob@@@Z; CredUXParameters::_SetupMessageText(CredUXParametersBlob const *)
0x140013d41  mov     ebx, eax
0x140013d43  test    eax, eax
0x140013d45  jns     short loc_140013D51
0x140013d47  mov     edx, 7Fh
0x140013d4c  jmp     loc_140013C34
0x140013d51  mov     rdx, rsi; struct CredUXParametersBlob *
0x140013d54  mov     rcx, rdi; this
0x140013d57  call    ?_SetupInputBuffer@CredUXParameters@@AEAAJPEBUCredUXParametersBlob@@@Z; CredUXParameters::_SetupInputBuffer(CredUXParametersBlob const *)
0x140013d5c  mov     ebx, eax
0x140013d5e  test    eax, eax
0x140013d60  jns     short loc_140013D6C
0x140013d62  mov     edx, 80h
0x140013d67  jmp     loc_140013C34
0x140013d6c  mov     rdx, rsi; struct CredUXParametersBlob *
0x140013d6f  mov     rcx, rdi; this
0x140013d72  call    ?_SetupAuthContext@CredUXParameters@@AEAAJPEBUCredUXParametersBlob@@@Z; CredUXParameters::_SetupAuthContext(CredUXParametersBlob const *)
0x140013d77  mov     ebx, eax
0x140013d79  test    eax, eax
0x140013d7b  jns     short loc_140013D87
0x140013d7d  mov     edx, 81h
0x140013d82  jmp     loc_140013C34
0x140013d87  mov     rax, [rsi+10h]
0x140013d8b  test    rax, rax
0x140013d8e  jz      short loc_140013DD2
0x140013d90  lea     rdx, [rax+68h]
0x140013d94  mov     rcx, [rdx]; unsigned __int16 *
0x140013d97  call    ?IsWideStringEmpty@@YA_NQEBG@Z; IsWideStringEmpty(ushort const * const)
0x140013d9c  test    al, al
0x140013d9e  jnz     short loc_140013DD2
0x140013da0  lea     rcx, [rdi+70h]
0x140013da4  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x140013da9  mov     ebx, eax
0x140013dab  test    eax, eax
0x140013dad  jns     short loc_140013DD2
0x140013daf  mov     rcx, [rsp+58h]; this
0x140013db4  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\cred"...
0x140013dbb  mov     r9d, eax; char *
0x140013dbe  mov     edx, 279h; void *
0x140013dc3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140013dc8  mov     edx, 82h
0x140013dcd  jmp     loc_140013C34
0x140013dd2  mov     rdx, rsi; struct CredUXParametersBlob *
0x140013dd5  mov     rcx, rdi; this
0x140013dd8  call    ?_SetupContextObject@CredUXParameters@@AEAAJPEBUCredUXParametersBlob@@@Z; CredUXParameters::_SetupContextObject(CredUXParametersBlob const *)
0x140013ddd  mov     ebx, eax
0x140013ddf  test    eax, eax
0x140013de1  jns     short loc_140013DED
0x140013de3  mov     edx, 83h
0x140013de8  jmp     loc_140013C34
0x140013ded  mov     rdx, rsi; struct CredUXParametersBlob *
0x140013df0  mov     rcx, rdi; this
0x140013df3  call    ?_SetupfooterLink@CredUXParameters@@AEAAJPEBUCredUXParametersBlob@@@Z; CredUXParameters::_SetupfooterLink(CredUXParametersBlob const *)
0x140013df8  mov     ebx, eax
0x140013dfa  test    eax, eax
0x140013dfc  jns     short loc_140013E08
0x140013dfe  mov     edx, 84h
0x140013e03  jmp     loc_140013C34
0x140013e08  mov     rdx, [rsi+10h]
0x140013e0c  test    rdx, rdx
0x140013e0f  jz      short loc_140013E34
0x140013e11  mov     ecx, [rdx+20h]
0x140013e14  bt      ecx, 10h
0x140013e18  setb    al
0x140013e1b  mov     [rdi+7Eh], al
0x140013e1e  bt      ecx, 10h
0x140013e22  jnb     short loc_140013E2D
0x140013e24  test    dword ptr [rdx+20h], 8000h
0x140013e2b  jnz     short loc_140013E30
0x140013e2d  xor     r14d, r14d
0x140013e30  mov     [rdi+7Dh], r14b
0x140013e34  xor     eax, eax
0x140013e36  add     rsp, 28h
0x140013e3a  pop     r15
0x140013e3c  pop     r14
0x140013e3e  pop     rdi
0x140013e3f  pop     rsi
0x140013e40  pop     rbp
0x140013e41  pop     rbx
0x140013e42  retn
```
