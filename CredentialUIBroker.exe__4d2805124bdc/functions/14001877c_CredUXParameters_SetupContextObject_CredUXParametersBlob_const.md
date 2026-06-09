# CredUXParameters::_SetupContextObject(CredUXParametersBlob const *)

- ea: `0x14001877c`
- end: `0x14001887f`
- name: `?_SetupContextObject@CredUXParameters@@AEAAJPEBUCredUXParametersBlob@@@Z`
- size: `259`
- prototype: `__int64 __fastcall(CredUXParameters *__hidden this, const struct CredUXParametersBlob *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140013ae4`

## callees

- `0x140006f10`
- `0x1400136fc`
- `0x14001877c`
- `0x140018c68`

## string_xrefs

- `0x1400187f1`: `shellcommon\internal\shell\inc\creduxparameters.h`
- `0x140018823`: `shellcommon\internal\shell\inc\creduxparameters.h`
- `0x14001885c`: `shellcommon\internal\shell\inc\creduxparameters.h`

## pseudocode

```c
__int64 __fastcall CredUXParameters::_SetupContextObject(CredUXParameters *this, const struct CredUXParametersBlob *a2)
{
  __int64 v2; // rbx
  __int64 v4; // rbx
  bool v5; // al
  int v6; // eax
  unsigned int v7; // ebp
  int v9; // eax
  __int64 v10; // rcx
  unsigned int v11; // esi
  int LogoStream; // eax
  unsigned int v13; // ebx
  int v14; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v2 = *((_QWORD *)a2 + 2);
  if ( !v2 )
    return 0;
  v4 = *(_QWORD *)(v2 + 120);
  if ( !v4 )
    return 0;
  v5 = *(_QWORD *)v4 && *(_QWORD *)(v4 + 8) && *(_DWORD *)(v4 + 28) && *(_QWORD *)(v4 + 16);
  *((_BYTE *)this + 224) = v5;
  if ( !v5 )
    return 0;
  v6 = Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>((char *)this + 232);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x289,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\creduxparameters.h",
      (const char *)(unsigned int)v6,
      v14);
    return v7;
  }
  v9 = Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>((char *)this + 240);
  v11 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x28A,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\creduxparameters.h",
      (const char *)(unsigned int)v9,
      v14);
    return v11;
  }
  LogoStream = CredUXParameters::_ValidateAndCreateLogoStream(
                 v10,
                 v4,
                 (int *)this + 62,
                 (struct Windows::Storage::Streams::IRandomAccessStream **)this + 32);
  v13 = LogoStream;
  if ( LogoStream >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x28B,
    (unsigned int)"shellcommon\\internal\\shell\\inc\\creduxparameters.h",
    (const char *)(unsigned int)LogoStream,
    v14);
  return v13;
}

```

## disassembly

```asm
0x14001877c  push    rbx
0x14001877e  push    rbp
0x14001877f  push    rsi
0x140018780  push    rdi
0x140018781  sub     rsp, 28h
0x140018785  mov     rbx, [rdx+10h]
0x140018789  mov     rdi, rcx
0x14001878c  test    rbx, rbx
0x14001878f  jz      loc_140018874
0x140018795  mov     rbx, [rbx+78h]
0x140018799  test    rbx, rbx
0x14001879c  jz      loc_140018874
0x1400187a2  cmp     qword ptr [rbx], 0
0x1400187a6  jz      short loc_1400187C3
0x1400187a8  lea     rsi, [rbx+8]
0x1400187ac  cmp     qword ptr [rsi], 0
0x1400187b0  jz      short loc_1400187C3
0x1400187b2  cmp     dword ptr [rbx+1Ch], 0
0x1400187b6  jbe     short loc_1400187C3
0x1400187b8  cmp     qword ptr [rbx+10h], 0
0x1400187bd  jz      short loc_1400187C3
0x1400187bf  mov     al, 1
0x1400187c1  jmp     short loc_1400187C9
0x1400187c3  xor     eax, eax
0x1400187c5  lea     rsi, [rbx+8]
0x1400187c9  mov     [rcx+0E0h], al
0x1400187cf  test    al, al
0x1400187d1  jz      loc_140018874
0x1400187d7  add     rcx, 0E8h
0x1400187de  mov     rdx, rbx
0x1400187e1  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1400187e6  mov     ebp, eax
0x1400187e8  test    eax, eax
0x1400187ea  jns     short loc_140018809
0x1400187ec  mov     rcx, [rsp+48h]; this
0x1400187f1  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\cred"...
0x1400187f8  mov     r9d, eax; char *
0x1400187fb  mov     edx, 289h; void *
0x140018800  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140018805  mov     eax, ebp
0x140018807  jmp     short loc_140018876
0x140018809  lea     rcx, [rdi+0F0h]
0x140018810  mov     rdx, rsi
0x140018813  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x140018818  mov     esi, eax
0x14001881a  test    eax, eax
0x14001881c  jns     short loc_14001883B
0x14001881e  mov     rcx, [rsp+48h]; this
0x140018823  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\cred"...
0x14001882a  mov     r9d, eax; char *
0x14001882d  mov     edx, 28Ah; void *
0x140018832  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140018837  mov     eax, esi
0x140018839  jmp     short loc_140018876
0x14001883b  lea     r9, [rdi+100h]
0x140018842  mov     rdx, rbx
0x140018845  lea     r8, [rdi+0F8h]
0x14001884c  call    ?_ValidateAndCreateLogoStream@CredUXParameters@@AEAAJPEBUCREDUI_ADDITIONAL_INFO@@AEAW4CREDUI_IMAGE_MIME_TYPE@@AEAV?$ComPtr@UIRandomAccessStream@Streams@Storage@Windows@@@WRL@Microsoft@@@Z; CredUXParameters::_ValidateAndCreateLogoStream(CREDUI_ADDITIONAL_INFO const *,CREDUI_IMAGE_MIME_TYPE &,Microsoft::WRL::ComPtr<Windows::Storage::Streams::IRandomAccessStream> &)
0x140018851  mov     ebx, eax
0x140018853  test    eax, eax
0x140018855  jns     short loc_140018874
0x140018857  mov     rcx, [rsp+48h]; this
0x14001885c  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\cred"...
0x140018863  mov     r9d, eax; char *
0x140018866  mov     edx, 28Bh; void *
0x14001886b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140018870  mov     eax, ebx
0x140018872  jmp     short loc_140018876
0x140018874  xor     eax, eax
0x140018876  add     rsp, 28h
0x14001887a  pop     rdi
0x14001887b  pop     rsi
0x14001887c  pop     rbp
0x14001887d  pop     rbx
0x14001887e  retn
```
