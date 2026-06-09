# MsixPackage::Provisioning::Library::PackageMonikerToPayload::GetBundleManifestReader(IAppxBundleManifestReader * *)

- ea: `0x180058a30`
- end: `0x180058e0f`
- name: `?GetBundleManifestReader@PackageMonikerToPayload@Library@Provisioning@MsixPackage@@QEAAJPEAPEAUIAppxBundleManifestReader@@@Z`
- size: `991`
- prototype: `__int64 __fastcall(MsixPackage::Provisioning::Library::PackageMonikerToPayload *__hidden this, struct IAppxBundleManifestReader **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180053b30`

## callees

- `0x18001d160`
- `0x1800344e4`
- `0x18003d4ec`
- `0x18003e50c`
- `0x180058a30`
- `0x18006c910`
- `0x180070010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180058bc4`
- `msvcrt!??3@YAXPEAX@Z` at `0x180058c58`
- `msvcrt!??3@YAXPEAX@Z` at `0x180058d36`
- `msvcrt!??3@YAXPEAX@Z` at `0x180058d8f`
- `msvcrt!??3@YAXPEAX@Z` at `0x180058bc4`
- `msvcrt!??3@YAXPEAX@Z` at `0x180058c58`
- `msvcrt!??3@YAXPEAX@Z` at `0x180058d36`
- `msvcrt!??3@YAXPEAX@Z` at `0x180058d8f`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateStreamOnFileW` at `0x180058b62`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateStreamOnFileW` at `0x180058b62`

## string_xrefs

- `0x180058b96`: `Failed to open '%ws'.`
- `0x180058d08`: `Failed to create appx bundle manifest reader for %ws.`
- `0x180058c2a`: `Failed to create appx bundle factory.`
- `0x180058b1c`: `\AppxMetadata\AppxBundleManifest.xml`
- `0x180058a9d`: `Failed to get bundle manifest reader.`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall MsixPackage::Provisioning::Library::PackageMonikerToPayload::GetBundleManifestReader(
        MsixPackage::Provisioning::Library::PackageMonikerToPayload *this,
        struct IAppxBundleManifestReader **a2)
{
  struct IAppxBundleManifestReader **v4; // rdi
  __int64 *v5; // rcx
  __int64 v6; // rax
  int v7; // ebx
  const char *v8; // r9
  __int64 result; // rax
  _QWORD *v10; // rdx
  __int64 v11; // r8
  const WCHAR *v12; // rcx
  HRESULT v13; // esi
  LPCWSTR *v14; // rdx
  MsixPackage::Provisioning::Library::MsixAppxPackaging *v15; // rcx
  int v16; // ebx
  __int64 v17; // rbx
  __int64 (__fastcall *v18)(__int64, IStream *, struct IAppxBundleManifestReader **); // rsi
  struct IAppxBundleManifestReader *v19; // rcx
  int v20; // esi
  LPCWSTR *v21; // rdx
  struct IAppxBundleManifestReader *v22; // rcx
  char *v23; // [rsp+28h] [rbp-70h]
  IStream *ppstm; // [rsp+30h] [rbp-68h] BYREF
  __int64 v25; // [rsp+38h] [rbp-60h]
  LPCWSTR pszFile[2]; // [rsp+40h] [rbp-58h] BYREF
  __int64 v27; // [rsp+50h] [rbp-48h]
  unsigned __int64 v28; // [rsp+58h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  try
  {
    *a2 = 0;
    v4 = (struct IAppxBundleManifestReader **)((char *)this + 152);
    if ( !*((_QWORD *)this + 19) )
    {
      if ( *((_DWORD *)this + 30) == 1 )
      {
        v5 = (__int64 *)*((_QWORD *)this + 16);
        v6 = *v5;
        *v4 = 0;
        v7 = (*(__int64 (__fastcall **)(__int64 *, struct IAppxBundleManifestReader **))(v6 + 40))(v5, v4);
        if ( v7 < 0 )
        {
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0xCF,
            (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagemonikertopayload.cpp",
            (const char *)(unsigned int)v7,
            (int)"Failed to get bundle manifest reader.",
            v23);
          return (unsigned int)v7;
        }
        goto LABEL_45;
      }
      ppstm = 0;
      v25 = 0;
      v10 = (_QWORD *)((char *)this + 88);
      if ( *((_QWORD *)this + 14) >= 8u )
        v10 = (_QWORD *)*v10;
      v28 = 7;
      v27 = 0;
      LOWORD(pszFile[0]) = 0;
      if ( *(_WORD *)v10 )
      {
        v11 = -1;
        do
          ++v11;
        while ( *((_WORD *)v10 + v11) );
      }
      std::wstring::assign(pszFile, v10);
      std::wstring::append(pszFile, L"\\AppxMetadata\\AppxBundleManifest.xml");
      ppstm = 0;
      v12 = (const WCHAR *)pszFile;
      if ( v28 >= 8 )
        v12 = pszFile[0];
      v13 = SHCreateStreamOnFileW(v12, 0, &ppstm);
      if ( v13 < 0 )
      {
        v14 = pszFile;
        if ( v28 >= 8 )
          v14 = (LPCWSTR *)pszFile[0];
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0xE2,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagemonikertopayload.cpp",
          (const char *)(unsigned int)v13,
          (int)"Failed to open '%ws'.",
          (const char *)v14);
        if ( v28 >= 8 )
          operator delete((void *)pszFile[0]);
        v28 = 7;
        v27 = 0;
        LOWORD(pszFile[0]) = 0;
        if ( ppstm )
          (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
        return (unsigned int)v13;
      }
      v15 = (MsixPackage::Provisioning::Library::MsixAppxPackaging *)(*((_QWORD *)this + 6) + 216LL);
      v25 = 0;
      v16 = MsixPackage::Provisioning::Library::MsixAppxPackaging::CreateFactory<IAppxBundleFactory>(v15);
      if ( v16 < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0xE4,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagemonikertopayload.cpp",
          (const char *)(unsigned int)v16,
          (int)"Failed to create appx bundle factory.",
          v23);
        if ( v28 >= 8 )
          operator delete((void *)pszFile[0]);
        v28 = 7;
        v27 = 0;
        LOWORD(pszFile[0]) = 0;
        if ( v25 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
        if ( ppstm )
          (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
        return (unsigned int)v16;
      }
      v17 = v25;
      v18 = *(__int64 (__fastcall **)(__int64, IStream *, struct IAppxBundleManifestReader **))(*(_QWORD *)v25 + 40LL);
      v19 = *v4;
      *v4 = 0;
      if ( v19 )
        ((void (__fastcall *)(struct IAppxBundleManifestReader *, struct IAppxBundleManifestReaderVtbl *))v19->lpVtbl->Release)(
          v19,
          v19->lpVtbl);
      v20 = v18(v17, ppstm, v4);
      if ( v20 < 0 )
      {
        v21 = pszFile;
        if ( v28 >= 8 )
          v21 = (LPCWSTR *)pszFile[0];
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0xEB,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagemonikertopayload.cpp",
          (const char *)(unsigned int)v20,
          (int)"Failed to create appx bundle manifest reader for %ws.",
          (const char *)v21);
        if ( v28 >= 8 )
          operator delete((void *)pszFile[0]);
        v28 = 7;
        v27 = 0;
        LOWORD(pszFile[0]) = 0;
        if ( v17 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
        if ( ppstm )
          (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
        return (unsigned int)v20;
      }
      if ( v28 >= 8 )
        operator delete((void *)pszFile[0]);
      v28 = 7;
      v27 = 0;
      LOWORD(pszFile[0]) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      if ( ppstm )
        (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
    }
LABEL_45:
    v22 = *v4;
    *a2 = *v4;
    ((void (__fastcall *)(struct IAppxBundleManifestReader *))v22->lpVtbl->AddRef)(v22);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xF4,
                           (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagemonikertopayload.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x180058a30  mov     [rsp+arg_10], rbx
0x180058a35  push    rsi
0x180058a36  push    rdi
0x180058a37  push    r12
0x180058a39  push    r14
0x180058a3b  push    r15
0x180058a3d  sub     rsp, 70h
0x180058a41  mov     rax, cs:__security_cookie
0x180058a48  xor     rax, rsp
0x180058a4b  mov     [rsp+98h+var_38], rax
0x180058a50  mov     r14, rdx
0x180058a53  mov     rbx, rcx
0x180058a56  xor     r15d, r15d
0x180058a59  mov     [rdx], r15
0x180058a5c  lea     rdi, [rcx+98h]
0x180058a63  cmp     [rdi], r15
0x180058a66  jnz     loc_180058DD2
0x180058a6c  cmp     dword ptr [rcx+78h], 1
0x180058a70  jnz     short loc_180058AC4
0x180058a72  mov     rcx, [rcx+80h]
0x180058a79  mov     rax, [rcx]
0x180058a7c  mov     [rdi], r15
0x180058a7f  mov     rdx, rdi
0x180058a82  mov     rax, [rax+28h]
0x180058a86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058a8b  mov     ebx, eax
0x180058a8d  test    eax, eax
0x180058a8f  jns     loc_180058DD2
0x180058a95  mov     rcx, [rsp+98h]; this
0x180058a9d  lea     rax, aFailedToGetBun_0; "Failed to get bundle manifest reader."
0x180058aa4  mov     qword ptr [rsp+98h+var_78], rax; int
0x180058aa9  mov     r9d, ebx; char *
0x180058aac  lea     r8, aOnecoreAdminAp_9; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180058ab3  mov     edx, 0CFh; void *
0x180058ab8  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180058abd  mov     eax, ebx
0x180058abf  jmp     loc_180058DEC
0x180058ac4  mov     [rsp+98h+ppstm], r15
0x180058ac9  mov     [rsp+98h+var_60], r15
0x180058ace  lea     rdx, [rcx+58h]
0x180058ad2  cmp     qword ptr [rdx+18h], 8
0x180058ad7  jb      short loc_180058ADC
0x180058ad9  mov     rdx, [rdx]; Src
0x180058adc  mov     r12d, 7
0x180058ae2  mov     [rsp+98h+var_40], r12
0x180058ae7  mov     [rsp+98h+var_48], r15
0x180058aec  mov     word ptr [rsp+98h+pszFile], r15w
0x180058af2  cmp     [rdx], r15w
0x180058af6  jnz     short loc_180058AFD
0x180058af8  mov     r8, r15
0x180058afb  jmp     short loc_180058B0B
0x180058afd  or      r8, 0FFFFFFFFFFFFFFFFh
0x180058b01  inc     r8
0x180058b04  cmp     [rdx+r8*2], r15w
0x180058b09  jnz     short loc_180058B01
0x180058b0b  lea     rcx, [rsp+98h+pszFile]; void *
0x180058b10  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180058b15  nop
0x180058b16  mov     r8d, 24h ; '$'
0x180058b1c  lea     rdx, aAppxmetadataAp; "\\AppxMetadata\\AppxBundleManifest.xml"
0x180058b23  lea     rcx, [rsp+98h+pszFile]; Src
0x180058b28  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180058b2d  nop
0x180058b2e  mov     rcx, [rsp+98h+ppstm]
0x180058b33  mov     [rsp+98h+ppstm], r15
0x180058b38  test    rcx, rcx
0x180058b3b  jz      short loc_180058B4A
0x180058b3d  mov     rax, [rcx]
0x180058b40  mov     rax, [rax+10h]
0x180058b44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058b49  nop
0x180058b4a  lea     rcx, [rsp+98h+pszFile]
0x180058b4f  cmp     [rsp+98h+var_40], 8
0x180058b55  cmovnb  rcx, [rsp+98h+pszFile]; pszFile
0x180058b5b  lea     r8, [rsp+98h+ppstm]; ppstm
0x180058b60  xor     edx, edx; grfMode
0x180058b62  call    cs:__imp_SHCreateStreamOnFileW
0x180058b69  nop     dword ptr [rax+rax+00h]
0x180058b6e  mov     esi, eax
0x180058b70  test    eax, eax
0x180058b72  jns     loc_180058BFE
0x180058b78  lea     rdx, [rsp+98h+pszFile]
0x180058b7d  cmp     [rsp+98h+var_40], 8
0x180058b83  cmovnb  rdx, [rsp+98h+pszFile]
0x180058b89  mov     rcx, [rsp+98h]; this
0x180058b91  mov     [rsp+98h+var_70], rdx; char *
0x180058b96  lea     rax, aFailedToOpenWs; "Failed to open '%ws'."
0x180058b9d  mov     qword ptr [rsp+98h+var_78], rax; int
0x180058ba2  mov     r9d, esi; char *
0x180058ba5  lea     r8, aOnecoreAdminAp_9; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180058bac  mov     edx, 0E2h; void *
0x180058bb1  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180058bb6  nop
0x180058bb7  cmp     [rsp+98h+var_40], 8
0x180058bbd  jb      short loc_180058BD0
0x180058bbf  mov     rcx, [rsp+98h+pszFile]
0x180058bc4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180058bcb  nop     dword ptr [rax+rax+00h]
0x180058bd0  mov     [rsp+98h+var_40], r12
0x180058bd5  mov     [rsp+98h+var_48], r15
0x180058bda  mov     word ptr [rsp+98h+pszFile], r15w
0x180058be0  mov     rcx, [rsp+98h+ppstm]
0x180058be5  test    rcx, rcx
0x180058be8  jz      short loc_180058BF7
0x180058bea  mov     rax, [rcx]
0x180058bed  mov     rax, [rax+10h]
0x180058bf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058bf6  nop
0x180058bf7  mov     eax, esi
0x180058bf9  jmp     loc_180058DEC
0x180058bfe  mov     rcx, [rbx+30h]
0x180058c02  add     rcx, 0D8h
0x180058c09  mov     [rsp+98h+var_60], r15
0x180058c0e  lea     r8, [rsp+98h+var_60]
0x180058c13  call    ??$CreateFactory@UIAppxBundleFactory@@@MsixAppxPackaging@Library@Provisioning@MsixPackage@@IEAAJAEBU_GUID@@PEAPEAUIAppxBundleFactory@@@Z; MsixPackage::Provisioning::Library::MsixAppxPackaging::CreateFactory<IAppxBundleFactory>(_GUID const &,IAppxBundleFactory * *)
0x180058c18  mov     ebx, eax
0x180058c1a  test    eax, eax
0x180058c1c  jns     loc_180058CA9
0x180058c22  mov     rcx, [rsp+98h]; this
0x180058c2a  lea     rax, aFailedToCreate_10; "Failed to create appx bundle factory."
0x180058c31  mov     qword ptr [rsp+98h+var_78], rax; int
0x180058c36  mov     r9d, ebx; char *
0x180058c39  lea     r8, aOnecoreAdminAp_9; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180058c40  mov     edx, 0E4h; void *
0x180058c45  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180058c4a  nop
0x180058c4b  cmp     [rsp+98h+var_40], 8
0x180058c51  jb      short loc_180058C64
0x180058c53  mov     rcx, [rsp+98h+pszFile]
0x180058c58  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180058c5f  nop     dword ptr [rax+rax+00h]
0x180058c64  mov     [rsp+98h+var_40], r12
0x180058c69  mov     [rsp+98h+var_48], r15
0x180058c6e  mov     word ptr [rsp+98h+pszFile], r15w
0x180058c74  mov     rcx, [rsp+98h+var_60]
0x180058c79  test    rcx, rcx
0x180058c7c  jz      short loc_180058C8B
0x180058c7e  mov     rax, [rcx]
0x180058c81  mov     rax, [rax+10h]
0x180058c85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058c8a  nop
0x180058c8b  mov     rcx, [rsp+98h+ppstm]
0x180058c90  test    rcx, rcx
0x180058c93  jz      short loc_180058CA2
0x180058c95  mov     rax, [rcx]
0x180058c98  mov     rax, [rax+10h]
0x180058c9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058ca1  nop
0x180058ca2  mov     eax, ebx
0x180058ca4  jmp     loc_180058DEC
0x180058ca9  mov     rbx, [rsp+98h+var_60]
0x180058cae  mov     rax, [rbx]
0x180058cb1  mov     rsi, [rax+28h]
0x180058cb5  mov     rcx, [rdi]
0x180058cb8  mov     [rdi], r15
0x180058cbb  test    rcx, rcx
0x180058cbe  jz      short loc_180058CCD
0x180058cc0  mov     rdx, [rcx]
0x180058cc3  mov     rax, [rdx+10h]
0x180058cc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058ccc  nop
0x180058ccd  mov     r8, rdi
0x180058cd0  mov     rdx, [rsp+98h+ppstm]
0x180058cd5  mov     rcx, rbx
0x180058cd8  mov     rax, rsi
0x180058cdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058ce0  mov     esi, eax
0x180058ce2  test    eax, eax
0x180058ce4  jns     loc_180058D82
0x180058cea  lea     rdx, [rsp+98h+pszFile]
0x180058cef  cmp     [rsp+98h+var_40], 8
0x180058cf5  cmovnb  rdx, [rsp+98h+pszFile]
0x180058cfb  mov     rcx, [rsp+98h]; this
0x180058d03  mov     [rsp+98h+var_70], rdx; char *
0x180058d08  lea     rax, aFailedToCreate_8; "Failed to create appx bundle manifest r"...
0x180058d0f  mov     qword ptr [rsp+98h+var_78], rax; int
0x180058d14  mov     r9d, esi; char *
0x180058d17  lea     r8, aOnecoreAdminAp_9; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180058d1e  mov     edx, 0EBh; void *
0x180058d23  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180058d28  nop
0x180058d29  cmp     [rsp+98h+var_40], 8
0x180058d2f  jb      short loc_180058D42
0x180058d31  mov     rcx, [rsp+98h+pszFile]
0x180058d36  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180058d3d  nop     dword ptr [rax+rax+00h]
0x180058d42  mov     [rsp+98h+var_40], r12
0x180058d47  mov     [rsp+98h+var_48], r15
0x180058d4c  mov     word ptr [rsp+98h+pszFile], r15w
0x180058d52  test    rbx, rbx
0x180058d55  jz      short loc_180058D67
0x180058d57  mov     rax, [rbx]
0x180058d5a  mov     rcx, rbx
0x180058d5d  mov     rax, [rax+10h]
0x180058d61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058d66  nop
0x180058d67  mov     rcx, [rsp+98h+ppstm]
0x180058d6c  test    rcx, rcx
0x180058d6f  jz      short loc_180058D7E
0x180058d71  mov     rax, [rcx]
0x180058d74  mov     rax, [rax+10h]
0x180058d78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058d7d  nop
0x180058d7e  mov     eax, esi
0x180058d80  jmp     short loc_180058DEC
0x180058d82  cmp     [rsp+98h+var_40], 8
0x180058d88  jb      short loc_180058D9B
0x180058d8a  mov     rcx, [rsp+98h+pszFile]
0x180058d8f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180058d96  nop     dword ptr [rax+rax+00h]
0x180058d9b  mov     [rsp+98h+var_40], r12
0x180058da0  mov     [rsp+98h+var_48], r15
0x180058da5  mov     word ptr [rsp+98h+pszFile], r15w
0x180058dab  mov     rax, [rbx]
0x180058dae  mov     rcx, rbx
0x180058db1  mov     rax, [rax+10h]
0x180058db5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058dba  nop
0x180058dbb  mov     rcx, [rsp+98h+ppstm]
0x180058dc0  test    rcx, rcx
0x180058dc3  jz      short loc_180058DD2
0x180058dc5  mov     rax, [rcx]
0x180058dc8  mov     rax, [rax+10h]
0x180058dcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058dd1  nop
0x180058dd2  mov     rcx, [rdi]
0x180058dd5  mov     [r14], rcx
0x180058dd8  mov     rax, [rcx]
0x180058ddb  mov     rax, [rax+8]
0x180058ddf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058de4  xor     eax, eax
0x180058de6  jmp     short loc_180058DEC
0x180058de8  mov     eax, dword ptr [rsp+98h+ppstm]
0x180058dec  mov     rcx, [rsp+98h+var_38]
0x180058df1  xor     rcx, rsp; StackCookie
0x180058df4  call    __security_check_cookie
0x180058df9  mov     rbx, [rsp+98h+arg_10]
0x180058e01  add     rsp, 70h
0x180058e05  pop     r15
0x180058e07  pop     r14
0x180058e09  pop     r12
0x180058e0b  pop     rdi
0x180058e0c  pop     rsi
0x180058e0d  retn
```
