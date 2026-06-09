# CredUXParameters::_SetupfooterLink(CredUXParametersBlob const *)

- ea: `0x140018ac0`
- end: `0x140018b97`
- name: `?_SetupfooterLink@CredUXParameters@@AEAAJPEBUCredUXParametersBlob@@@Z`
- size: `215`
- prototype: `__int64 __fastcall(CredUXParameters *__hidden this, const struct CredUXParametersBlob *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140013ae4`

## callees

- `0x140006f10`
- `0x1400136fc`
- `0x140018ac0`
- `0x140018c68`

## string_xrefs

- `0x140018b22`: `shellcommon\internal\shell\inc\creduxparameters.h`
- `0x140018b73`: `shellcommon\internal\shell\inc\creduxparameters.h`

## pseudocode

```c
__int64 __fastcall CredUXParameters::_SetupfooterLink(CredUXParameters *this, const struct CredUXParametersBlob *a2)
{
  __int64 v2; // rbx
  __int64 v4; // rbx
  __int64 v5; // rdx
  int v6; // esi
  __int64 v7; // rdx
  __int64 v9; // rcx
  int LogoStream; // eax
  unsigned int v11; // ebx
  int v12; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v2 = *((_QWORD *)a2 + 2);
  if ( !v2 )
    return 0;
  v4 = *(_QWORD *)(v2 + 128);
  if ( !v4 )
    return 0;
  v5 = *(_QWORD *)(v4 + 8);
  *((_BYTE *)this + 264) = v5 != 0;
  if ( !v5 )
    return 0;
  v6 = Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>((char *)this + 272);
  if ( v6 < 0 )
  {
    v7 = 683;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\creduxparameters.h",
      (const char *)(unsigned int)v6,
      v12);
    return (unsigned int)v6;
  }
  v6 = Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>((char *)this + 280);
  if ( v6 < 0 )
  {
    v7 = 684;
    goto LABEL_6;
  }
  LogoStream = CredUXParameters::_ValidateAndCreateLogoStream(
                 v9,
                 v4,
                 (int *)this + 63,
                 (struct Windows::Storage::Streams::IRandomAccessStream **)this + 36);
  v11 = LogoStream;
  if ( LogoStream >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2AD,
    (unsigned int)"shellcommon\\internal\\shell\\inc\\creduxparameters.h",
    (const char *)(unsigned int)LogoStream,
    v12);
  return v11;
}

```

## disassembly

```asm
0x140018ac0  push    rbx
0x140018ac2  push    rsi
0x140018ac3  push    rdi
0x140018ac4  push    r14
0x140018ac6  sub     rsp, 28h
0x140018aca  mov     rbx, [rdx+10h]
0x140018ace  mov     rdi, rcx
0x140018ad1  test    rbx, rbx
0x140018ad4  jz      loc_140018B8B
0x140018ada  mov     rbx, [rbx+80h]
0x140018ae1  test    rbx, rbx
0x140018ae4  jz      loc_140018B8B
0x140018aea  mov     rdx, [rbx+8]
0x140018aee  test    rdx, rdx
0x140018af1  setnz   al
0x140018af4  mov     [rcx+108h], al
0x140018afa  test    rdx, rdx
0x140018afd  jz      loc_140018B8B
0x140018b03  add     rcx, 110h
0x140018b0a  mov     rdx, rbx
0x140018b0d  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x140018b12  mov     esi, eax
0x140018b14  test    eax, eax
0x140018b16  jns     short loc_140018B35
0x140018b18  mov     edx, 2ABh; void *
0x140018b1d  mov     rcx, [rsp+48h]; this
0x140018b22  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\cred"...
0x140018b29  mov     r9d, esi; char *
0x140018b2c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140018b31  mov     eax, esi
0x140018b33  jmp     short loc_140018B8D
0x140018b35  lea     rcx, [rdi+118h]
0x140018b3c  lea     rdx, [rbx+8]
0x140018b40  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x140018b45  mov     esi, eax
0x140018b47  test    eax, eax
0x140018b49  jns     short loc_140018B52
0x140018b4b  mov     edx, 2ACh
0x140018b50  jmp     short loc_140018B1D
0x140018b52  lea     r9, [rdi+120h]
0x140018b59  mov     rdx, rbx
0x140018b5c  lea     r8, [rdi+0FCh]
0x140018b63  call    ?_ValidateAndCreateLogoStream@CredUXParameters@@AEAAJPEBUCREDUI_ADDITIONAL_INFO@@AEAW4CREDUI_IMAGE_MIME_TYPE@@AEAV?$ComPtr@UIRandomAccessStream@Streams@Storage@Windows@@@WRL@Microsoft@@@Z; CredUXParameters::_ValidateAndCreateLogoStream(CREDUI_ADDITIONAL_INFO const *,CREDUI_IMAGE_MIME_TYPE &,Microsoft::WRL::ComPtr<Windows::Storage::Streams::IRandomAccessStream> &)
0x140018b68  mov     ebx, eax
0x140018b6a  test    eax, eax
0x140018b6c  jns     short loc_140018B8B
0x140018b6e  mov     rcx, [rsp+48h]; this
0x140018b73  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\cred"...
0x140018b7a  mov     r9d, eax; char *
0x140018b7d  mov     edx, 2ADh; void *
0x140018b82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140018b87  mov     eax, ebx
0x140018b89  jmp     short loc_140018B8D
0x140018b8b  xor     eax, eax
0x140018b8d  add     rsp, 28h
0x140018b91  pop     r14
0x140018b93  pop     rdi
0x140018b94  pop     rsi
0x140018b95  pop     rbx
0x140018b96  retn
```
