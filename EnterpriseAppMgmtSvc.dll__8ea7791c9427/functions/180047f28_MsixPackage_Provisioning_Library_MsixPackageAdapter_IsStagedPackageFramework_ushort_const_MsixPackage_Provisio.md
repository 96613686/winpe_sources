# MsixPackage::Provisioning::Library::MsixPackageAdapter::IsStagedPackageFramework(ushort const *,MsixPackage::Provisioning::Library::MsixProvisioningContext *,int &)

- ea: `0x180047f28`
- end: `0x180048383`
- name: `?IsStagedPackageFramework@MsixPackageAdapter@Library@Provisioning@MsixPackage@@SAJPEBGPEAVMsixProvisioningContext@234@AEAH@Z`
- size: `1115`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct MsixPackage::Provisioning::Library::MsixProvisioningContext *, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180042444`

## callees

- `0x18001bf0c`
- `0x180039e9c`
- `0x18003ae3c`
- `0x18003b0b0`
- `0x180047f28`
- `0x180066df0`
- `0x18006a010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18004806f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004819d`
- `msvcrt!??3@YAXPEAX@Z` at `0x180048358`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004806f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004819d`
- `msvcrt!??3@YAXPEAX@Z` at `0x180048358`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateStreamOnFileW` at `0x18004800a`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateStreamOnFileW` at `0x18004800a`

## string_xrefs

- `0x18004802d`: `Failed to open '%ws'.`
- `0x18004803c`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x1800480a9`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004813f`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x1800481e3`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180048288`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004809a`: `Failed to create appx factory.`
- `0x180048130`: `Failed to create appx manifest reader for %ws.`
- `0x180047fe1`: `\AppxManifest.xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall MsixPackage::Provisioning::Library::MsixPackageAdapter::IsStagedPackageFramework(
        char *a1,
        struct MsixPackage::Provisioning::Library::MsixProvisioningContext *a2,
        int *a3)
{
  char *v6; // rdx
  unsigned __int64 v7; // rbx
  unsigned __int64 v8; // r8
  unsigned __int8 *Data4; // rcx
  _QWORD *v10; // rdx
  int v11; // ebx
  unsigned __int8 *v12; // rdx
  __int64 v14; // rbx
  __int64 v15; // rax
  int v16; // edi
  unsigned __int8 *v17; // rdx
  __int64 v18; // rax
  char *v19; // [rsp+28h] [rbp-58h]
  IStream *ppstm; // [rsp+30h] [rbp-50h] BYREF
  __int64 *v21; // [rsp+38h] [rbp-48h] BYREF
  __int64 v22; // [rsp+40h] [rbp-40h] BYREF
  struct _GUID v23; // [rsp+48h] [rbp-38h] BYREF
  __int64 v24; // [rsp+60h] [rbp-20h]
  unsigned __int64 v25; // [rsp+68h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  *a3 = 0;
  v25 = 7;
  v24 = 0;
  *(_WORD *)v23.Data4 = 0;
  v6 = (char *)*((_QWORD *)a2 + 70);
  v7 = -1;
  if ( *(_WORD *)v6 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)&v6[2 * v8] );
  }
  else
  {
    v8 = 0;
  }
  std::wstring::assign(v23.Data4, v6, v8);
  std::wstring::append(v23.Data4, (char *)L"\\", pszSrc[0] != 0);
  if ( *(_WORD *)a1 )
  {
    do
      ++v7;
    while ( *(_WORD *)&a1[2 * v7] );
  }
  else
  {
    v7 = 0;
  }
  std::wstring::append(v23.Data4, a1, v7);
  std::wstring::append(v23.Data4, (char *)L"\\AppxManifest.xml", 0x11u);
  ppstm = 0;
  Data4 = v23.Data4;
  if ( v25 >= 8 )
    Data4 = *(unsigned __int8 **)v23.Data4;
  v11 = SHCreateStreamOnFileW((LPCWSTR)Data4, 0, &ppstm);
  if ( v11 < 0 )
  {
    v12 = v23.Data4;
    if ( v25 >= 8 )
      v12 = *(unsigned __int8 **)v23.Data4;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x6C3,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
      (const char *)(unsigned int)v11,
      (int)"Failed to open '%ws'.",
      (const char *)v12);
    if ( ppstm )
      (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
LABEL_15:
    if ( v25 >= 8 )
      operator delete(*(void **)v23.Data4);
    return (unsigned int)v11;
  }
  *(_QWORD *)&v23.Data1 = 0;
  v11 = MsixPackage::Provisioning::Library::MsixAppxPackaging::CreateFactory<IAppxFactory>(
          (struct MsixPackage::Provisioning::Library::MsixProvisioningContext *)((char *)a2 + 216),
          v10,
          &v23);
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x6C8,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
      (const char *)(unsigned int)v11,
      (int)"Failed to create appx factory.",
      v19);
    if ( *(_QWORD *)&v23.Data1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v23.Data1 + 16LL))(*(_QWORD *)&v23.Data1);
    if ( ppstm )
      (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
    goto LABEL_15;
  }
  v21 = 0;
  v14 = *(_QWORD *)&v23.Data1;
  v15 = **(_QWORD **)&v23.Data1;
  v21 = 0;
  v16 = (*(__int64 (__fastcall **)(_QWORD, IStream *, __int64 **))(v15 + 40))(*(_QWORD *)&v23.Data1, ppstm, &v21);
  if ( v16 < 0 )
  {
    v17 = v23.Data4;
    if ( v25 >= 8 )
      v17 = *(unsigned __int8 **)v23.Data4;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x6CE,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
      (const char *)(unsigned int)v16,
      (int)"Failed to create appx manifest reader for %ws.",
      (const char *)v17);
    if ( v21 )
      (*(void (__fastcall **)(__int64 *))(*v21 + 16))(v21);
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    if ( ppstm )
      (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
LABEL_33:
    if ( v25 >= 8 )
      operator delete(*(void **)v23.Data4);
    return (unsigned int)v16;
  }
  v22 = 0;
  v18 = *v21;
  v22 = 0;
  v16 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v18 + 32))(v21, &v22);
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x6D1,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
      (const char *)(unsigned int)v16,
      (int)"Failed to get properties.",
      v19);
    if ( v22 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    if ( v21 )
      (*(void (__fastcall **)(__int64 *))(*v21 + 16))(v21);
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    if ( ppstm )
      (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
    goto LABEL_33;
  }
  v16 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *))(*(_QWORD *)v22 + 24LL))(v22, L"Framework", a3);
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x6D3,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
      (const char *)(unsigned int)v16,
      (int)"Failed to get framework bool value from properties.",
      v19);
    if ( v22 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    if ( v21 )
      (*(void (__fastcall **)(__int64 *))(*v21 + 16))(v21);
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    if ( ppstm )
      (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
    goto LABEL_33;
  }
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  if ( v21 )
    (*(void (__fastcall **)(__int64 *))(*v21 + 16))(v21);
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  if ( ppstm )
    (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
  if ( v25 >= 8 )
    operator delete(*(void **)v23.Data4);
  return 0;
}

```

## disassembly

```asm
0x180047f28  mov     [rsp-28h+arg_18], rbx
0x180047f2d  push    rbp
0x180047f2e  push    rsi
0x180047f2f  push    rdi
0x180047f30  push    r14
0x180047f32  push    r15
0x180047f34  mov     rbp, rsp
0x180047f37  sub     rsp, 80h
0x180047f3e  mov     rax, cs:__security_cookie
0x180047f45  xor     rax, rsp
0x180047f48  mov     [rbp+var_10], rax
0x180047f4c  mov     r14, r8
0x180047f4f  mov     rsi, rdx
0x180047f52  mov     rdi, rcx
0x180047f55  xor     r15d, r15d
0x180047f58  mov     [r8], r15d
0x180047f5b  mov     [rbp+var_18], 7
0x180047f63  mov     [rbp+var_20], r15
0x180047f67  mov     word ptr [rbp+pszFile], r15w
0x180047f6c  mov     rdx, [rdx+230h]; Src
0x180047f73  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180047f77  cmp     [rdx], r15w
0x180047f7b  jnz     short loc_180047F82
0x180047f7d  mov     r8d, r15d
0x180047f80  jmp     short loc_180047F8F
0x180047f82  mov     r8, rbx
0x180047f85  inc     r8
0x180047f88  cmp     [rdx+r8*2], r15w
0x180047f8d  jnz     short loc_180047F85
0x180047f8f  lea     rcx, [rbp+pszFile]; void *
0x180047f93  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180047f98  mov     r8, r15
0x180047f9b  cmp     word ptr cs:pszSrc, r15w; "\\"
0x180047fa3  setnz   r8b
0x180047fa7  lea     rdx, pszSrc; "\\"
0x180047fae  lea     rcx, [rbp+pszFile]; Src
0x180047fb2  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180047fb7  cmp     [rdi], r15w
0x180047fbb  jnz     short loc_180047FC2
0x180047fbd  mov     rbx, r15
0x180047fc0  jmp     short loc_180047FCC
0x180047fc2  inc     rbx
0x180047fc5  cmp     [rdi+rbx*2], r15w
0x180047fca  jnz     short loc_180047FC2
0x180047fcc  mov     r8, rbx
0x180047fcf  mov     rdx, rdi; void *
0x180047fd2  lea     rcx, [rbp+pszFile]; Src
0x180047fd6  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180047fdb  mov     r8d, 11h
0x180047fe1  lea     rdx, aAppxmanifestXm; "\\AppxManifest.xml"
0x180047fe8  lea     rcx, [rbp+pszFile]; Src
0x180047fec  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180047ff1  nop
0x180047ff2  mov     [rbp+ppstm], r15
0x180047ff6  lea     rcx, [rbp+pszFile]
0x180047ffa  cmp     [rbp+var_18], 8
0x180047fff  cmovnb  rcx, [rbp+pszFile]; pszFile
0x180048004  lea     r8, [rbp+ppstm]; ppstm
0x180048008  xor     edx, edx; grfMode
0x18004800a  call    cs:__imp_SHCreateStreamOnFileW
0x180048010  mov     ebx, eax
0x180048012  test    eax, eax
0x180048014  jns     short loc_18004807C
0x180048016  lea     rdx, [rbp+pszFile]
0x18004801a  cmp     [rbp+var_18], 8
0x18004801f  cmovnb  rdx, [rbp+pszFile]
0x180048024  mov     rcx, [rbp+28h]; this
0x180048028  mov     [rsp+80h+var_58], rdx; char *
0x18004802d  lea     rax, aFailedToOpenWs; "Failed to open '%ws'."
0x180048034  mov     qword ptr [rsp+80h+var_60], rax; int
0x180048039  mov     r9d, ebx; char *
0x18004803c  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180048043  mov     edx, 6C3h; void *
0x180048048  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004804d  nop
0x18004804e  mov     rcx, [rbp+ppstm]
0x180048052  test    rcx, rcx
0x180048055  jz      short loc_180048064
0x180048057  mov     rax, [rcx]
0x18004805a  mov     rax, [rax+10h]
0x18004805e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048063  nop
0x180048064  cmp     [rbp+var_18], 8
0x180048069  jb      short loc_180048075
0x18004806b  mov     rcx, [rbp+pszFile]
0x18004806f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180048075  mov     eax, ebx
0x180048077  jmp     loc_180048360
0x18004807c  lea     rcx, [rsi+0D8h]; this
0x180048083  mov     [rbp+var_38], r15
0x180048087  lea     r8, [rbp+var_38]
0x18004808b  call    ??$CreateFactory@UIAppxFactory@@@MsixAppxPackaging@Library@Provisioning@MsixPackage@@IEAAJAEBU_GUID@@PEAPEAUIAppxFactory@@@Z; MsixPackage::Provisioning::Library::MsixAppxPackaging::CreateFactory<IAppxFactory>(_GUID const &,IAppxFactory * *)
0x180048090  mov     ebx, eax
0x180048092  test    eax, eax
0x180048094  jns     short loc_1800480EC
0x180048096  mov     rcx, [rbp+28h]; this
0x18004809a  lea     rax, aFailedToCreate_28; "Failed to create appx factory."
0x1800480a1  mov     qword ptr [rsp+80h+var_60], rax; int
0x1800480a6  mov     r9d, ebx; char *
0x1800480a9  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800480b0  mov     edx, 6C8h; void *
0x1800480b5  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800480ba  nop
0x1800480bb  mov     rcx, [rbp+var_38]
0x1800480bf  test    rcx, rcx
0x1800480c2  jz      short loc_1800480D1
0x1800480c4  mov     rax, [rcx]
0x1800480c7  mov     rax, [rax+10h]
0x1800480cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800480d0  nop
0x1800480d1  mov     rcx, [rbp+ppstm]
0x1800480d5  test    rcx, rcx
0x1800480d8  jz      short loc_1800480E7
0x1800480da  mov     rax, [rcx]
0x1800480dd  mov     rax, [rax+10h]
0x1800480e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800480e6  nop
0x1800480e7  jmp     loc_180048064
0x1800480ec  mov     [rbp+var_48], r15
0x1800480f0  mov     rbx, [rbp+var_38]
0x1800480f4  mov     rax, [rbx]
0x1800480f7  mov     [rbp+var_48], r15
0x1800480fb  lea     r8, [rbp+var_48]
0x1800480ff  mov     rdx, [rbp+ppstm]
0x180048103  mov     rcx, rbx
0x180048106  mov     rax, [rax+28h]
0x18004810a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004810f  mov     edi, eax
0x180048111  test    eax, eax
0x180048113  jns     loc_1800481AA
0x180048119  lea     rdx, [rbp+pszFile]
0x18004811d  cmp     [rbp+var_18], 8
0x180048122  cmovnb  rdx, [rbp+pszFile]
0x180048127  mov     rcx, [rbp+28h]; this
0x18004812b  mov     [rsp+80h+var_58], rdx; char *
0x180048130  lea     rax, aFailedToCreate_14; "Failed to create appx manifest reader f"...
0x180048137  mov     qword ptr [rsp+80h+var_60], rax; int
0x18004813c  mov     r9d, edi; char *
0x18004813f  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180048146  mov     edx, 6CEh; void *
0x18004814b  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180048150  nop
0x180048151  mov     rcx, [rbp+var_48]
0x180048155  test    rcx, rcx
0x180048158  jz      short loc_180048167
0x18004815a  mov     rax, [rcx]
0x18004815d  mov     rax, [rax+10h]
0x180048161  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048166  nop
0x180048167  test    rbx, rbx
0x18004816a  jz      short loc_18004817C
0x18004816c  mov     rax, [rbx]
0x18004816f  mov     rcx, rbx
0x180048172  mov     rax, [rax+10h]
0x180048176  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004817b  nop
0x18004817c  mov     rcx, [rbp+ppstm]
0x180048180  test    rcx, rcx
0x180048183  jz      short loc_180048192
0x180048185  mov     rax, [rcx]
0x180048188  mov     rax, [rax+10h]
0x18004818c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048191  nop
0x180048192  cmp     [rbp+var_18], 8
0x180048197  jb      short loc_1800481A3
0x180048199  mov     rcx, [rbp+pszFile]
0x18004819d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800481a3  mov     eax, edi
0x1800481a5  jmp     loc_180048360
0x1800481aa  mov     [rbp+var_40], r15
0x1800481ae  mov     rcx, [rbp+var_48]
0x1800481b2  mov     rax, [rcx]
0x1800481b5  mov     [rbp+var_40], r15
0x1800481b9  lea     rdx, [rbp+var_40]
0x1800481bd  mov     rax, [rax+20h]
0x1800481c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800481c6  mov     edi, eax
0x1800481c8  test    eax, eax
0x1800481ca  jns     loc_180048251
0x1800481d0  mov     rcx, [rbp+28h]; this
0x1800481d4  lea     rax, aFailedToGetPro; "Failed to get properties."
0x1800481db  mov     qword ptr [rsp+80h+var_60], rax; int
0x1800481e0  mov     r9d, edi; char *
0x1800481e3  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800481ea  mov     edx, 6D1h; void *
0x1800481ef  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800481f4  nop
0x1800481f5  mov     rcx, [rbp+var_40]
0x1800481f9  test    rcx, rcx
0x1800481fc  jz      short loc_18004820B
0x1800481fe  mov     rax, [rcx]
0x180048201  mov     rax, [rax+10h]
0x180048205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004820a  nop
0x18004820b  mov     rcx, [rbp+var_48]
0x18004820f  test    rcx, rcx
0x180048212  jz      short loc_180048221
0x180048214  mov     rax, [rcx]
0x180048217  mov     rax, [rax+10h]
0x18004821b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048220  nop
0x180048221  test    rbx, rbx
0x180048224  jz      short loc_180048236
0x180048226  mov     rax, [rbx]
0x180048229  mov     rcx, rbx
0x18004822c  mov     rax, [rax+10h]
0x180048230  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048235  nop
0x180048236  mov     rcx, [rbp+ppstm]
0x18004823a  test    rcx, rcx
0x18004823d  jz      short loc_18004824C
0x18004823f  mov     rax, [rcx]
0x180048242  mov     rax, [rax+10h]
0x180048246  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004824b  nop
0x18004824c  jmp     loc_180048192
0x180048251  mov     rcx, [rbp+var_40]
0x180048255  mov     rax, [rcx]
0x180048258  mov     r8, r14
0x18004825b  lea     rdx, aFramework; "Framework"
0x180048262  mov     rax, [rax+18h]
0x180048266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004826b  mov     edi, eax
0x18004826d  test    eax, eax
0x18004826f  jns     loc_1800482F6
0x180048275  mov     rcx, [rbp+28h]; this
0x180048279  lea     rax, aFailedToGetFra; "Failed to get framework bool value from"...
0x180048280  mov     qword ptr [rsp+80h+var_60], rax; int
0x180048285  mov     r9d, edi; char *
0x180048288  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004828f  mov     edx, 6D3h; void *
0x180048294  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180048299  nop
0x18004829a  mov     rcx, [rbp+var_40]
0x18004829e  test    rcx, rcx
0x1800482a1  jz      short loc_1800482B0
0x1800482a3  mov     rax, [rcx]
0x1800482a6  mov     rax, [rax+10h]
0x1800482aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800482af  nop
0x1800482b0  mov     rcx, [rbp+var_48]
0x1800482b4  test    rcx, rcx
0x1800482b7  jz      short loc_1800482C6
0x1800482b9  mov     rax, [rcx]
0x1800482bc  mov     rax, [rax+10h]
0x1800482c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800482c5  nop
0x1800482c6  test    rbx, rbx
0x1800482c9  jz      short loc_1800482DB
0x1800482cb  mov     rax, [rbx]
0x1800482ce  mov     rcx, rbx
0x1800482d1  mov     rax, [rax+10h]
0x1800482d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800482da  nop
0x1800482db  mov     rcx, [rbp+ppstm]
0x1800482df  test    rcx, rcx
0x1800482e2  jz      short loc_1800482F1
0x1800482e4  mov     rax, [rcx]
0x1800482e7  mov     rax, [rax+10h]
0x1800482eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800482f0  nop
0x1800482f1  jmp     loc_180048192
0x1800482f6  mov     rcx, [rbp+var_40]
0x1800482fa  test    rcx, rcx
0x1800482fd  jz      short loc_18004830C
0x1800482ff  mov     rax, [rcx]
0x180048302  mov     rax, [rax+10h]
0x180048306  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004830b  nop
0x18004830c  mov     rcx, [rbp+var_48]
0x180048310  test    rcx, rcx
0x180048313  jz      short loc_180048322
0x180048315  mov     rax, [rcx]
0x180048318  mov     rax, [rax+10h]
0x18004831c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048321  nop
0x180048322  test    rbx, rbx
0x180048325  jz      short loc_180048337
0x180048327  mov     rax, [rbx]
0x18004832a  mov     rcx, rbx
0x18004832d  mov     rax, [rax+10h]
0x180048331  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048336  nop
0x180048337  mov     rcx, [rbp+ppstm]
0x18004833b  test    rcx, rcx
0x18004833e  jz      short loc_18004834D
0x180048340  mov     rax, [rcx]
0x180048343  mov     rax, [rax+10h]
0x180048347  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004834c  nop
0x18004834d  cmp     [rbp+var_18], 8
0x180048352  jb      short loc_18004835E
0x180048354  mov     rcx, [rbp+pszFile]
0x180048358  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18004835e  xor     eax, eax
0x180048360  mov     rcx, [rbp+var_10]
0x180048364  xor     rcx, rsp; StackCookie
0x180048367  call    __security_check_cookie
0x18004836c  mov     rbx, [rsp+80h+arg_18]
0x180048374  add     rsp, 80h
  ... truncated ...
```
