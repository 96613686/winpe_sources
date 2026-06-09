# MsixPackage::Provisioning::Library::PackageMonikerToPayload::GetBundleManifestReader(IAppxBundleManifestReader * *)

- ea: `0x1800544e0`
- end: `0x1800548a1`
- name: `?GetBundleManifestReader@PackageMonikerToPayload@Library@Provisioning@MsixPackage@@QEAAJPEAPEAUIAppxBundleManifestReader@@@Z`
- size: `961`
- prototype: `__int64 __fastcall(MsixPackage::Provisioning::Library::PackageMonikerToPayload *__hidden this, struct IAppxBundleManifestReader **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x18004f76c`

## callees

- `0x18001bf0c`
- `0x18003167c`
- `0x180039e9c`
- `0x18003ae3c`
- `0x1800544e0`
- `0x180066df0`
- `0x18006a010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18005466e`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800546fc`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800547d4`
- `msvcrt!??3@YAXPEAX@Z` at `0x180054827`
- `msvcrt!??3@YAXPEAX@Z` at `0x18005466e`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800546fc`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800547d4`
- `msvcrt!??3@YAXPEAX@Z` at `0x180054827`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateStreamOnFileW` at `0x180054612`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateStreamOnFileW` at `0x180054612`

## string_xrefs

- `0x180054640`: `Failed to open '%ws'.`
- `0x1800546ce`: `Failed to create appx bundle factory.`
- `0x1800547a6`: `Failed to create appx bundle manifest reader for %ws.`
- `0x1800545cc`: `\AppxMetadata\AppxBundleManifest.xml`
- `0x18005454d`: `Failed to get bundle manifest reader.`

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
  char *v10; // rdx
  unsigned __int64 v11; // r8
  unsigned __int8 *Data4; // rcx
  _QWORD *v13; // rdx
  HRESULT v14; // esi
  unsigned __int8 *v15; // rdx
  MsixPackage::Provisioning::Library::MsixAppxPackaging *v16; // rcx
  int v17; // ebx
  __int64 v18; // rbx
  __int64 (__fastcall *v19)(__int64, IStream *, struct IAppxBundleManifestReader **); // rsi
  struct IAppxBundleManifestReader *v20; // rcx
  int v21; // esi
  unsigned __int8 *v22; // rdx
  struct IAppxBundleManifestReader *v23; // rcx
  char *v24; // [rsp+28h] [rbp-70h]
  IStream *ppstm; // [rsp+30h] [rbp-68h] BYREF
  struct _GUID v26; // [rsp+38h] [rbp-60h] BYREF
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
            v24);
          return (unsigned int)v7;
        }
        goto LABEL_46;
      }
      ppstm = 0;
      *(_QWORD *)&v26.Data1 = 0;
      v10 = (char *)this + 88;
      if ( *((_QWORD *)this + 14) >= 8u )
        v10 = *(char **)v10;
      v28 = 7;
      v27 = 0;
      *(_WORD *)v26.Data4 = 0;
      if ( *(_WORD *)v10 )
      {
        v11 = -1;
        do
          ++v11;
        while ( *(_WORD *)&v10[2 * v11] );
      }
      else
      {
        v11 = 0;
      }
      std::wstring::assign(v26.Data4, v10, v11);
      std::wstring::append(v26.Data4, (char *)L"\\AppxMetadata\\AppxBundleManifest.xml", 0x24u);
      ppstm = 0;
      Data4 = v26.Data4;
      if ( v28 >= 8 )
        Data4 = *(unsigned __int8 **)v26.Data4;
      v14 = SHCreateStreamOnFileW((LPCWSTR)Data4, 0, &ppstm);
      if ( v14 < 0 )
      {
        v15 = v26.Data4;
        if ( v28 >= 8 )
          v15 = *(unsigned __int8 **)v26.Data4;
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0xE2,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagemonikertopayload.cpp",
          (const char *)(unsigned int)v14,
          (int)"Failed to open '%ws'.",
          (const char *)v15);
        if ( v28 >= 8 )
          operator delete(*(void **)v26.Data4);
        v28 = 7;
        v27 = 0;
        *(_WORD *)v26.Data4 = 0;
        if ( ppstm )
          (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
        return (unsigned int)v14;
      }
      v16 = (MsixPackage::Provisioning::Library::MsixAppxPackaging *)(*((_QWORD *)this + 6) + 216LL);
      *(_QWORD *)&v26.Data1 = 0;
      v17 = MsixPackage::Provisioning::Library::MsixAppxPackaging::CreateFactory<IAppxBundleFactory>(v16, v13, &v26);
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0xE4,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagemonikertopayload.cpp",
          (const char *)(unsigned int)v17,
          (int)"Failed to create appx bundle factory.",
          v24);
        if ( v28 >= 8 )
          operator delete(*(void **)v26.Data4);
        v28 = 7;
        v27 = 0;
        *(_WORD *)v26.Data4 = 0;
        if ( *(_QWORD *)&v26.Data1 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v26.Data1 + 16LL))(*(_QWORD *)&v26.Data1);
        if ( ppstm )
          (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
        return (unsigned int)v17;
      }
      v18 = *(_QWORD *)&v26.Data1;
      v19 = *(__int64 (__fastcall **)(__int64, IStream *, struct IAppxBundleManifestReader **))(**(_QWORD **)&v26.Data1
                                                                                              + 40LL);
      v20 = *v4;
      *v4 = 0;
      if ( v20 )
        ((void (__fastcall *)(struct IAppxBundleManifestReader *, struct IAppxBundleManifestReaderVtbl *))v20->lpVtbl->Release)(
          v20,
          v20->lpVtbl);
      v21 = v19(v18, ppstm, v4);
      if ( v21 < 0 )
      {
        v22 = v26.Data4;
        if ( v28 >= 8 )
          v22 = *(unsigned __int8 **)v26.Data4;
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0xEB,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagemonikertopayload.cpp",
          (const char *)(unsigned int)v21,
          (int)"Failed to create appx bundle manifest reader for %ws.",
          (const char *)v22);
        if ( v28 >= 8 )
          operator delete(*(void **)v26.Data4);
        v28 = 7;
        v27 = 0;
        *(_WORD *)v26.Data4 = 0;
        if ( v18 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
        if ( ppstm )
          (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
        return (unsigned int)v21;
      }
      if ( v28 >= 8 )
        operator delete(*(void **)v26.Data4);
      v28 = 7;
      v27 = 0;
      *(_WORD *)v26.Data4 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      if ( ppstm )
        (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
    }
LABEL_46:
    v23 = *v4;
    *a2 = *v4;
    ((void (__fastcall *)(struct IAppxBundleManifestReader *))v23->lpVtbl->AddRef)(v23);
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
0x1800544e0  mov     [rsp+arg_10], rbx
0x1800544e5  push    rsi
0x1800544e6  push    rdi
0x1800544e7  push    r12
0x1800544e9  push    r14
0x1800544eb  push    r15
0x1800544ed  sub     rsp, 70h
0x1800544f1  mov     rax, cs:__security_cookie
0x1800544f8  xor     rax, rsp
0x1800544fb  mov     [rsp+98h+var_38], rax
0x180054500  mov     r14, rdx
0x180054503  mov     rbx, rcx
0x180054506  xor     r15d, r15d
0x180054509  mov     [rdx], r15
0x18005450c  lea     rdi, [rcx+98h]
0x180054513  cmp     [rdi], r15
0x180054516  jnz     loc_180054864
0x18005451c  cmp     dword ptr [rcx+78h], 1
0x180054520  jnz     short loc_180054574
0x180054522  mov     rcx, [rcx+80h]
0x180054529  mov     rax, [rcx]
0x18005452c  mov     [rdi], r15
0x18005452f  mov     rdx, rdi
0x180054532  mov     rax, [rax+28h]
0x180054536  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005453b  mov     ebx, eax
0x18005453d  test    eax, eax
0x18005453f  jns     loc_180054864
0x180054545  mov     rcx, [rsp+98h]; this
0x18005454d  lea     rax, aFailedToGetBun_0; "Failed to get bundle manifest reader."
0x180054554  mov     qword ptr [rsp+98h+var_78], rax; int
0x180054559  mov     r9d, ebx; char *
0x18005455c  lea     r8, aOnecoreAdminAp_9; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180054563  mov     edx, 0CFh; void *
0x180054568  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18005456d  mov     eax, ebx
0x18005456f  jmp     loc_18005487E
0x180054574  mov     [rsp+98h+ppstm], r15
0x180054579  mov     [rsp+98h+var_60], r15
0x18005457e  lea     rdx, [rcx+58h]
0x180054582  cmp     qword ptr [rdx+18h], 8
0x180054587  jb      short loc_18005458C
0x180054589  mov     rdx, [rdx]; Src
0x18005458c  mov     r12d, 7
0x180054592  mov     [rsp+98h+var_40], r12
0x180054597  mov     [rsp+98h+var_48], r15
0x18005459c  mov     word ptr [rsp+98h+pszFile], r15w
0x1800545a2  cmp     [rdx], r15w
0x1800545a6  jnz     short loc_1800545AD
0x1800545a8  mov     r8, r15
0x1800545ab  jmp     short loc_1800545BB
0x1800545ad  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800545b1  inc     r8
0x1800545b4  cmp     [rdx+r8*2], r15w
0x1800545b9  jnz     short loc_1800545B1
0x1800545bb  lea     rcx, [rsp+98h+pszFile]; void *
0x1800545c0  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800545c5  nop
0x1800545c6  mov     r8d, 24h ; '$'
0x1800545cc  lea     rdx, aAppxmetadataAp; "\\AppxMetadata\\AppxBundleManifest.xml"
0x1800545d3  lea     rcx, [rsp+98h+pszFile]; Src
0x1800545d8  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x1800545dd  nop
0x1800545de  mov     rcx, [rsp+98h+ppstm]
0x1800545e3  mov     [rsp+98h+ppstm], r15
0x1800545e8  test    rcx, rcx
0x1800545eb  jz      short loc_1800545FA
0x1800545ed  mov     rax, [rcx]
0x1800545f0  mov     rax, [rax+10h]
0x1800545f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800545f9  nop
0x1800545fa  lea     rcx, [rsp+98h+pszFile]
0x1800545ff  cmp     [rsp+98h+var_40], 8
0x180054605  cmovnb  rcx, [rsp+98h+pszFile]; pszFile
0x18005460b  lea     r8, [rsp+98h+ppstm]; ppstm
0x180054610  xor     edx, edx; grfMode
0x180054612  call    cs:__imp_SHCreateStreamOnFileW
0x180054618  mov     esi, eax
0x18005461a  test    eax, eax
0x18005461c  jns     loc_1800546A2
0x180054622  lea     rdx, [rsp+98h+pszFile]
0x180054627  cmp     [rsp+98h+var_40], 8
0x18005462d  cmovnb  rdx, [rsp+98h+pszFile]
0x180054633  mov     rcx, [rsp+98h]; this
0x18005463b  mov     [rsp+98h+var_70], rdx; char *
0x180054640  lea     rax, aFailedToOpenWs; "Failed to open '%ws'."
0x180054647  mov     qword ptr [rsp+98h+var_78], rax; int
0x18005464c  mov     r9d, esi; char *
0x18005464f  lea     r8, aOnecoreAdminAp_9; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180054656  mov     edx, 0E2h; void *
0x18005465b  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180054660  nop
0x180054661  cmp     [rsp+98h+var_40], 8
0x180054667  jb      short loc_180054674
0x180054669  mov     rcx, [rsp+98h+pszFile]
0x18005466e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180054674  mov     [rsp+98h+var_40], r12
0x180054679  mov     [rsp+98h+var_48], r15
0x18005467e  mov     word ptr [rsp+98h+pszFile], r15w
0x180054684  mov     rcx, [rsp+98h+ppstm]
0x180054689  test    rcx, rcx
0x18005468c  jz      short loc_18005469B
0x18005468e  mov     rax, [rcx]
0x180054691  mov     rax, [rax+10h]
0x180054695  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005469a  nop
0x18005469b  mov     eax, esi
0x18005469d  jmp     loc_18005487E
0x1800546a2  mov     rcx, [rbx+30h]
0x1800546a6  add     rcx, 0D8h
0x1800546ad  mov     [rsp+98h+var_60], r15
0x1800546b2  lea     r8, [rsp+98h+var_60]
0x1800546b7  call    ??$CreateFactory@UIAppxBundleFactory@@@MsixAppxPackaging@Library@Provisioning@MsixPackage@@IEAAJAEBU_GUID@@PEAPEAUIAppxBundleFactory@@@Z; MsixPackage::Provisioning::Library::MsixAppxPackaging::CreateFactory<IAppxBundleFactory>(_GUID const &,IAppxBundleFactory * *)
0x1800546bc  mov     ebx, eax
0x1800546be  test    eax, eax
0x1800546c0  jns     loc_180054747
0x1800546c6  mov     rcx, [rsp+98h]; this
0x1800546ce  lea     rax, aFailedToCreate_10; "Failed to create appx bundle factory."
0x1800546d5  mov     qword ptr [rsp+98h+var_78], rax; int
0x1800546da  mov     r9d, ebx; char *
0x1800546dd  lea     r8, aOnecoreAdminAp_9; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800546e4  mov     edx, 0E4h; void *
0x1800546e9  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800546ee  nop
0x1800546ef  cmp     [rsp+98h+var_40], 8
0x1800546f5  jb      short loc_180054702
0x1800546f7  mov     rcx, [rsp+98h+pszFile]
0x1800546fc  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180054702  mov     [rsp+98h+var_40], r12
0x180054707  mov     [rsp+98h+var_48], r15
0x18005470c  mov     word ptr [rsp+98h+pszFile], r15w
0x180054712  mov     rcx, [rsp+98h+var_60]
0x180054717  test    rcx, rcx
0x18005471a  jz      short loc_180054729
0x18005471c  mov     rax, [rcx]
0x18005471f  mov     rax, [rax+10h]
0x180054723  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054728  nop
0x180054729  mov     rcx, [rsp+98h+ppstm]
0x18005472e  test    rcx, rcx
0x180054731  jz      short loc_180054740
0x180054733  mov     rax, [rcx]
0x180054736  mov     rax, [rax+10h]
0x18005473a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005473f  nop
0x180054740  mov     eax, ebx
0x180054742  jmp     loc_18005487E
0x180054747  mov     rbx, [rsp+98h+var_60]
0x18005474c  mov     rax, [rbx]
0x18005474f  mov     rsi, [rax+28h]
0x180054753  mov     rcx, [rdi]
0x180054756  mov     [rdi], r15
0x180054759  test    rcx, rcx
0x18005475c  jz      short loc_18005476B
0x18005475e  mov     rdx, [rcx]
0x180054761  mov     rax, [rdx+10h]
0x180054765  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005476a  nop
0x18005476b  mov     r8, rdi
0x18005476e  mov     rdx, [rsp+98h+ppstm]
0x180054773  mov     rcx, rbx
0x180054776  mov     rax, rsi
0x180054779  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005477e  mov     esi, eax
0x180054780  test    eax, eax
0x180054782  jns     loc_18005481A
0x180054788  lea     rdx, [rsp+98h+pszFile]
0x18005478d  cmp     [rsp+98h+var_40], 8
0x180054793  cmovnb  rdx, [rsp+98h+pszFile]
0x180054799  mov     rcx, [rsp+98h]; this
0x1800547a1  mov     [rsp+98h+var_70], rdx; char *
0x1800547a6  lea     rax, aFailedToCreate_8; "Failed to create appx bundle manifest r"...
0x1800547ad  mov     qword ptr [rsp+98h+var_78], rax; int
0x1800547b2  mov     r9d, esi; char *
0x1800547b5  lea     r8, aOnecoreAdminAp_9; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800547bc  mov     edx, 0EBh; void *
0x1800547c1  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800547c6  nop
0x1800547c7  cmp     [rsp+98h+var_40], 8
0x1800547cd  jb      short loc_1800547DA
0x1800547cf  mov     rcx, [rsp+98h+pszFile]
0x1800547d4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800547da  mov     [rsp+98h+var_40], r12
0x1800547df  mov     [rsp+98h+var_48], r15
0x1800547e4  mov     word ptr [rsp+98h+pszFile], r15w
0x1800547ea  test    rbx, rbx
0x1800547ed  jz      short loc_1800547FF
0x1800547ef  mov     rax, [rbx]
0x1800547f2  mov     rcx, rbx
0x1800547f5  mov     rax, [rax+10h]
0x1800547f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800547fe  nop
0x1800547ff  mov     rcx, [rsp+98h+ppstm]
0x180054804  test    rcx, rcx
0x180054807  jz      short loc_180054816
0x180054809  mov     rax, [rcx]
0x18005480c  mov     rax, [rax+10h]
0x180054810  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054815  nop
0x180054816  mov     eax, esi
0x180054818  jmp     short loc_18005487E
0x18005481a  cmp     [rsp+98h+var_40], 8
0x180054820  jb      short loc_18005482D
0x180054822  mov     rcx, [rsp+98h+pszFile]
0x180054827  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18005482d  mov     [rsp+98h+var_40], r12
0x180054832  mov     [rsp+98h+var_48], r15
0x180054837  mov     word ptr [rsp+98h+pszFile], r15w
0x18005483d  mov     rax, [rbx]
0x180054840  mov     rcx, rbx
0x180054843  mov     rax, [rax+10h]
0x180054847  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005484c  nop
0x18005484d  mov     rcx, [rsp+98h+ppstm]
0x180054852  test    rcx, rcx
0x180054855  jz      short loc_180054864
0x180054857  mov     rax, [rcx]
0x18005485a  mov     rax, [rax+10h]
0x18005485e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054863  nop
0x180054864  mov     rcx, [rdi]
0x180054867  mov     [r14], rcx
0x18005486a  mov     rax, [rcx]
0x18005486d  mov     rax, [rax+8]
0x180054871  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054876  xor     eax, eax
0x180054878  jmp     short loc_18005487E
0x18005487a  mov     eax, dword ptr [rsp+98h+ppstm]
0x18005487e  mov     rcx, [rsp+98h+var_38]
0x180054883  xor     rcx, rsp; StackCookie
0x180054886  call    __security_check_cookie
0x18005488b  mov     rbx, [rsp+98h+arg_10]
0x180054893  add     rsp, 70h
0x180054897  pop     r15
0x180054899  pop     r14
0x18005489b  pop     r12
0x18005489d  pop     rdi
0x18005489e  pop     rsi
0x18005489f  retn
```
