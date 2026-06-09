# MsixPackage::Provisioning::Library::MsixPackageAdapter::IsStagedPackageFramework(ushort const *,MsixPackage::Provisioning::Library::MsixProvisioningContext *,int &)

- ea: `0x18004bfa4`
- end: `0x18004c418`
- name: `?IsStagedPackageFramework@MsixPackageAdapter@Library@Provisioning@MsixPackage@@SAJPEBGPEAVMsixProvisioningContext@234@AEAH@Z`
- size: `1140`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct MsixPackage::Provisioning::Library::MsixProvisioningContext *, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x1800461ac`

## callees

- `0x18001d160`
- `0x18003d4ec`
- `0x18003e50c`
- `0x18003e780`
- `0x18004bfa4`
- `0x18006c910`
- `0x180070010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18004c0f1`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004c225`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004c3e6`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004c0f1`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004c225`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004c3e6`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateStreamOnFileW` at `0x18004c086`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateStreamOnFileW` at `0x18004c086`

## string_xrefs

- `0x18004c0af`: `Failed to open '%ws'.`
- `0x18004c0be`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004c131`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004c1c7`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004c271`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004c316`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004c122`: `Failed to create appx factory.`
- `0x18004c1b8`: `Failed to create appx manifest reader for %ws.`
- `0x18004c05d`: `\AppxManifest.xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall MsixPackage::Provisioning::Library::MsixPackageAdapter::IsStagedPackageFramework(
        unsigned __int16 *a1,
        struct MsixPackage::Provisioning::Library::MsixProvisioningContext *a2,
        int *a3)
{
  _WORD *v6; // rdx
  __int64 v7; // rbx
  __int64 v8; // r8
  const WCHAR *v9; // rcx
  HRESULT v10; // ebx
  LPCWSTR *v11; // rdx
  __int64 *v13; // rbx
  __int64 v14; // rax
  int v15; // edi
  LPCWSTR *v16; // rdx
  __int64 v17; // rax
  char *v18; // [rsp+28h] [rbp-58h]
  IStream *ppstm; // [rsp+30h] [rbp-50h] BYREF
  __int64 *v20; // [rsp+38h] [rbp-48h] BYREF
  __int64 v21; // [rsp+40h] [rbp-40h] BYREF
  __int64 *v22; // [rsp+48h] [rbp-38h]
  LPCWSTR pszFile[3]; // [rsp+50h] [rbp-30h] BYREF
  unsigned __int64 v24; // [rsp+68h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  *a3 = 0;
  v24 = 7;
  pszFile[2] = 0;
  LOWORD(pszFile[0]) = 0;
  v6 = (_WORD *)*((_QWORD *)a2 + 70);
  v7 = -1;
  if ( *v6 )
  {
    v8 = -1;
    do
      ++v8;
    while ( v6[v8] );
  }
  std::wstring::assign(pszFile, v6);
  std::wstring::append(pszFile, (void *)L"\\");
  if ( *a1 )
  {
    do
      ++v7;
    while ( a1[v7] );
  }
  std::wstring::append(pszFile, a1);
  std::wstring::append(pszFile, L"\\AppxManifest.xml");
  ppstm = 0;
  v9 = (const WCHAR *)pszFile;
  if ( v24 >= 8 )
    v9 = pszFile[0];
  v10 = SHCreateStreamOnFileW(v9, 0, &ppstm);
  if ( v10 < 0 )
  {
    v11 = pszFile;
    if ( v24 >= 8 )
      v11 = (LPCWSTR *)pszFile[0];
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x6C3,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
      (const char *)(unsigned int)v10,
      (int)"Failed to open '%ws'.",
      (const char *)v11);
    if ( ppstm )
      (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
LABEL_13:
    if ( v24 >= 8 )
      operator delete((void *)pszFile[0]);
    return (unsigned int)v10;
  }
  v22 = 0;
  v10 = MsixPackage::Provisioning::Library::MsixAppxPackaging::CreateFactory<IAppxFactory>((struct MsixPackage::Provisioning::Library::MsixProvisioningContext *)((char *)a2 + 216));
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x6C8,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
      (const char *)(unsigned int)v10,
      (int)"Failed to create appx factory.",
      v18);
    if ( v22 )
      (*(void (__fastcall **)(__int64 *))(*v22 + 16))(v22);
    if ( ppstm )
      (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
    goto LABEL_13;
  }
  v20 = 0;
  v13 = v22;
  v14 = *v22;
  v20 = 0;
  v15 = (*(__int64 (__fastcall **)(__int64 *, IStream *, __int64 **))(v14 + 40))(v22, ppstm, &v20);
  if ( v15 < 0 )
  {
    v16 = pszFile;
    if ( v24 >= 8 )
      v16 = (LPCWSTR *)pszFile[0];
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x6CE,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
      (const char *)(unsigned int)v15,
      (int)"Failed to create appx manifest reader for %ws.",
      (const char *)v16);
    if ( v20 )
      (*(void (__fastcall **)(__int64 *))(*v20 + 16))(v20);
    if ( v13 )
      (*(void (__fastcall **)(__int64 *))(*v13 + 16))(v13);
    if ( ppstm )
      (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
LABEL_31:
    if ( v24 >= 8 )
      operator delete((void *)pszFile[0]);
    return (unsigned int)v15;
  }
  v21 = 0;
  v17 = *v20;
  v21 = 0;
  v15 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v17 + 32))(v20, &v21);
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x6D1,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
      (const char *)(unsigned int)v15,
      (int)"Failed to get properties.",
      v18);
    if ( v21 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    if ( v20 )
      (*(void (__fastcall **)(__int64 *))(*v20 + 16))(v20);
    if ( v13 )
      (*(void (__fastcall **)(__int64 *))(*v13 + 16))(v13);
    if ( ppstm )
      (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
    goto LABEL_31;
  }
  v15 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *))(*(_QWORD *)v21 + 24LL))(v21, L"Framework", a3);
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x6D3,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
      (const char *)(unsigned int)v15,
      (int)"Failed to get framework bool value from properties.",
      v18);
    if ( v21 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    if ( v20 )
      (*(void (__fastcall **)(__int64 *))(*v20 + 16))(v20);
    if ( v13 )
      (*(void (__fastcall **)(__int64 *))(*v13 + 16))(v13);
    if ( ppstm )
      (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
    goto LABEL_31;
  }
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  if ( v20 )
    (*(void (__fastcall **)(__int64 *))(*v20 + 16))(v20);
  if ( v13 )
    (*(void (__fastcall **)(__int64 *))(*v13 + 16))(v13);
  if ( ppstm )
    (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
  if ( v24 >= 8 )
    operator delete((void *)pszFile[0]);
  return 0;
}

```

## disassembly

```asm
0x18004bfa4  mov     [rsp-28h+arg_18], rbx
0x18004bfa9  push    rbp
0x18004bfaa  push    rsi
0x18004bfab  push    rdi
0x18004bfac  push    r14
0x18004bfae  push    r15
0x18004bfb0  mov     rbp, rsp
0x18004bfb3  sub     rsp, 80h
0x18004bfba  mov     rax, cs:__security_cookie
0x18004bfc1  xor     rax, rsp
0x18004bfc4  mov     [rbp+var_10], rax
0x18004bfc8  mov     r14, r8
0x18004bfcb  mov     rsi, rdx
0x18004bfce  mov     rdi, rcx
0x18004bfd1  xor     r15d, r15d
0x18004bfd4  mov     [r8], r15d
0x18004bfd7  mov     [rbp+var_18], 7
0x18004bfdf  mov     [rbp+var_20], r15
0x18004bfe3  mov     word ptr [rbp+pszFile], r15w
0x18004bfe8  mov     rdx, [rdx+230h]; Src
0x18004bfef  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18004bff3  cmp     [rdx], r15w
0x18004bff7  jnz     short loc_18004BFFE
0x18004bff9  mov     r8d, r15d
0x18004bffc  jmp     short loc_18004C00B
0x18004bffe  mov     r8, rbx
0x18004c001  inc     r8
0x18004c004  cmp     [rdx+r8*2], r15w
0x18004c009  jnz     short loc_18004C001
0x18004c00b  lea     rcx, [rbp+pszFile]; void *
0x18004c00f  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18004c014  mov     r8, r15
0x18004c017  cmp     word ptr cs:pszSrc, r15w; "\\"
0x18004c01f  setnz   r8b
0x18004c023  lea     rdx, pszSrc; "\\"
0x18004c02a  lea     rcx, [rbp+pszFile]; Src
0x18004c02e  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18004c033  cmp     [rdi], r15w
0x18004c037  jnz     short loc_18004C03E
0x18004c039  mov     rbx, r15
0x18004c03c  jmp     short loc_18004C048
0x18004c03e  inc     rbx
0x18004c041  cmp     [rdi+rbx*2], r15w
0x18004c046  jnz     short loc_18004C03E
0x18004c048  mov     r8, rbx
0x18004c04b  mov     rdx, rdi; void *
0x18004c04e  lea     rcx, [rbp+pszFile]; Src
0x18004c052  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18004c057  mov     r8d, 11h
0x18004c05d  lea     rdx, aAppxmanifestXm; "\\AppxManifest.xml"
0x18004c064  lea     rcx, [rbp+pszFile]; Src
0x18004c068  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18004c06d  nop
0x18004c06e  mov     [rbp+ppstm], r15
0x18004c072  lea     rcx, [rbp+pszFile]
0x18004c076  cmp     [rbp+var_18], 8
0x18004c07b  cmovnb  rcx, [rbp+pszFile]; pszFile
0x18004c080  lea     r8, [rbp+ppstm]; ppstm
0x18004c084  xor     edx, edx; grfMode
0x18004c086  call    cs:__imp_SHCreateStreamOnFileW
0x18004c08d  nop     dword ptr [rax+rax+00h]
0x18004c092  mov     ebx, eax
0x18004c094  test    eax, eax
0x18004c096  jns     short loc_18004C104
0x18004c098  lea     rdx, [rbp+pszFile]
0x18004c09c  cmp     [rbp+var_18], 8
0x18004c0a1  cmovnb  rdx, [rbp+pszFile]
0x18004c0a6  mov     rcx, [rbp+28h]; this
0x18004c0aa  mov     [rsp+80h+var_58], rdx; char *
0x18004c0af  lea     rax, aFailedToOpenWs; "Failed to open '%ws'."
0x18004c0b6  mov     qword ptr [rsp+80h+var_60], rax; int
0x18004c0bb  mov     r9d, ebx; char *
0x18004c0be  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004c0c5  mov     edx, 6C3h; void *
0x18004c0ca  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004c0cf  nop
0x18004c0d0  mov     rcx, [rbp+ppstm]
0x18004c0d4  test    rcx, rcx
0x18004c0d7  jz      short loc_18004C0E6
0x18004c0d9  mov     rax, [rcx]
0x18004c0dc  mov     rax, [rax+10h]
0x18004c0e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c0e5  nop
0x18004c0e6  cmp     [rbp+var_18], 8
0x18004c0eb  jb      short loc_18004C0FD
0x18004c0ed  mov     rcx, [rbp+pszFile]
0x18004c0f1  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18004c0f8  nop     dword ptr [rax+rax+00h]
0x18004c0fd  mov     eax, ebx
0x18004c0ff  jmp     loc_18004C3F4
0x18004c104  lea     rcx, [rsi+0D8h]; this
0x18004c10b  mov     [rbp+var_38], r15
0x18004c10f  lea     r8, [rbp+var_38]
0x18004c113  call    ??$CreateFactory@UIAppxFactory@@@MsixAppxPackaging@Library@Provisioning@MsixPackage@@IEAAJAEBU_GUID@@PEAPEAUIAppxFactory@@@Z; MsixPackage::Provisioning::Library::MsixAppxPackaging::CreateFactory<IAppxFactory>(_GUID const &,IAppxFactory * *)
0x18004c118  mov     ebx, eax
0x18004c11a  test    eax, eax
0x18004c11c  jns     short loc_18004C174
0x18004c11e  mov     rcx, [rbp+28h]; this
0x18004c122  lea     rax, aFailedToCreate_28; "Failed to create appx factory."
0x18004c129  mov     qword ptr [rsp+80h+var_60], rax; int
0x18004c12e  mov     r9d, ebx; char *
0x18004c131  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004c138  mov     edx, 6C8h; void *
0x18004c13d  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004c142  nop
0x18004c143  mov     rcx, [rbp+var_38]
0x18004c147  test    rcx, rcx
0x18004c14a  jz      short loc_18004C159
0x18004c14c  mov     rax, [rcx]
0x18004c14f  mov     rax, [rax+10h]
0x18004c153  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c158  nop
0x18004c159  mov     rcx, [rbp+ppstm]
0x18004c15d  test    rcx, rcx
0x18004c160  jz      short loc_18004C16F
0x18004c162  mov     rax, [rcx]
0x18004c165  mov     rax, [rax+10h]
0x18004c169  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c16e  nop
0x18004c16f  jmp     loc_18004C0E6
0x18004c174  mov     [rbp+var_48], r15
0x18004c178  mov     rbx, [rbp+var_38]
0x18004c17c  mov     rax, [rbx]
0x18004c17f  mov     [rbp+var_48], r15
0x18004c183  lea     r8, [rbp+var_48]
0x18004c187  mov     rdx, [rbp+ppstm]
0x18004c18b  mov     rcx, rbx
0x18004c18e  mov     rax, [rax+28h]
0x18004c192  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c197  mov     edi, eax
0x18004c199  test    eax, eax
0x18004c19b  jns     loc_18004C238
0x18004c1a1  lea     rdx, [rbp+pszFile]
0x18004c1a5  cmp     [rbp+var_18], 8
0x18004c1aa  cmovnb  rdx, [rbp+pszFile]
0x18004c1af  mov     rcx, [rbp+28h]; this
0x18004c1b3  mov     [rsp+80h+var_58], rdx; char *
0x18004c1b8  lea     rax, aFailedToCreate_14; "Failed to create appx manifest reader f"...
0x18004c1bf  mov     qword ptr [rsp+80h+var_60], rax; int
0x18004c1c4  mov     r9d, edi; char *
0x18004c1c7  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004c1ce  mov     edx, 6CEh; void *
0x18004c1d3  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004c1d8  nop
0x18004c1d9  mov     rcx, [rbp+var_48]
0x18004c1dd  test    rcx, rcx
0x18004c1e0  jz      short loc_18004C1EF
0x18004c1e2  mov     rax, [rcx]
0x18004c1e5  mov     rax, [rax+10h]
0x18004c1e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c1ee  nop
0x18004c1ef  test    rbx, rbx
0x18004c1f2  jz      short loc_18004C204
0x18004c1f4  mov     rax, [rbx]
0x18004c1f7  mov     rcx, rbx
0x18004c1fa  mov     rax, [rax+10h]
0x18004c1fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c203  nop
0x18004c204  mov     rcx, [rbp+ppstm]
0x18004c208  test    rcx, rcx
0x18004c20b  jz      short loc_18004C21A
0x18004c20d  mov     rax, [rcx]
0x18004c210  mov     rax, [rax+10h]
0x18004c214  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c219  nop
0x18004c21a  cmp     [rbp+var_18], 8
0x18004c21f  jb      short loc_18004C231
0x18004c221  mov     rcx, [rbp+pszFile]
0x18004c225  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18004c22c  nop     dword ptr [rax+rax+00h]
0x18004c231  mov     eax, edi
0x18004c233  jmp     loc_18004C3F4
0x18004c238  mov     [rbp+var_40], r15
0x18004c23c  mov     rcx, [rbp+var_48]
0x18004c240  mov     rax, [rcx]
0x18004c243  mov     [rbp+var_40], r15
0x18004c247  lea     rdx, [rbp+var_40]
0x18004c24b  mov     rax, [rax+20h]
0x18004c24f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c254  mov     edi, eax
0x18004c256  test    eax, eax
0x18004c258  jns     loc_18004C2DF
0x18004c25e  mov     rcx, [rbp+28h]; this
0x18004c262  lea     rax, aFailedToGetPro; "Failed to get properties."
0x18004c269  mov     qword ptr [rsp+80h+var_60], rax; int
0x18004c26e  mov     r9d, edi; char *
0x18004c271  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004c278  mov     edx, 6D1h; void *
0x18004c27d  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004c282  nop
0x18004c283  mov     rcx, [rbp+var_40]
0x18004c287  test    rcx, rcx
0x18004c28a  jz      short loc_18004C299
0x18004c28c  mov     rax, [rcx]
0x18004c28f  mov     rax, [rax+10h]
0x18004c293  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c298  nop
0x18004c299  mov     rcx, [rbp+var_48]
0x18004c29d  test    rcx, rcx
0x18004c2a0  jz      short loc_18004C2AF
0x18004c2a2  mov     rax, [rcx]
0x18004c2a5  mov     rax, [rax+10h]
0x18004c2a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c2ae  nop
0x18004c2af  test    rbx, rbx
0x18004c2b2  jz      short loc_18004C2C4
0x18004c2b4  mov     rax, [rbx]
0x18004c2b7  mov     rcx, rbx
0x18004c2ba  mov     rax, [rax+10h]
0x18004c2be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c2c3  nop
0x18004c2c4  mov     rcx, [rbp+ppstm]
0x18004c2c8  test    rcx, rcx
0x18004c2cb  jz      short loc_18004C2DA
0x18004c2cd  mov     rax, [rcx]
0x18004c2d0  mov     rax, [rax+10h]
0x18004c2d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c2d9  nop
0x18004c2da  jmp     loc_18004C21A
0x18004c2df  mov     rcx, [rbp+var_40]
0x18004c2e3  mov     rax, [rcx]
0x18004c2e6  mov     r8, r14
0x18004c2e9  lea     rdx, aFramework; "Framework"
0x18004c2f0  mov     rax, [rax+18h]
0x18004c2f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c2f9  mov     edi, eax
0x18004c2fb  test    eax, eax
0x18004c2fd  jns     loc_18004C384
0x18004c303  mov     rcx, [rbp+28h]; this
0x18004c307  lea     rax, aFailedToGetFra; "Failed to get framework bool value from"...
0x18004c30e  mov     qword ptr [rsp+80h+var_60], rax; int
0x18004c313  mov     r9d, edi; char *
0x18004c316  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004c31d  mov     edx, 6D3h; void *
0x18004c322  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004c327  nop
0x18004c328  mov     rcx, [rbp+var_40]
0x18004c32c  test    rcx, rcx
0x18004c32f  jz      short loc_18004C33E
0x18004c331  mov     rax, [rcx]
0x18004c334  mov     rax, [rax+10h]
0x18004c338  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c33d  nop
0x18004c33e  mov     rcx, [rbp+var_48]
0x18004c342  test    rcx, rcx
0x18004c345  jz      short loc_18004C354
0x18004c347  mov     rax, [rcx]
0x18004c34a  mov     rax, [rax+10h]
0x18004c34e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c353  nop
0x18004c354  test    rbx, rbx
0x18004c357  jz      short loc_18004C369
0x18004c359  mov     rax, [rbx]
0x18004c35c  mov     rcx, rbx
0x18004c35f  mov     rax, [rax+10h]
0x18004c363  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c368  nop
0x18004c369  mov     rcx, [rbp+ppstm]
0x18004c36d  test    rcx, rcx
0x18004c370  jz      short loc_18004C37F
0x18004c372  mov     rax, [rcx]
0x18004c375  mov     rax, [rax+10h]
0x18004c379  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c37e  nop
0x18004c37f  jmp     loc_18004C21A
0x18004c384  mov     rcx, [rbp+var_40]
0x18004c388  test    rcx, rcx
0x18004c38b  jz      short loc_18004C39A
0x18004c38d  mov     rax, [rcx]
0x18004c390  mov     rax, [rax+10h]
0x18004c394  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c399  nop
0x18004c39a  mov     rcx, [rbp+var_48]
0x18004c39e  test    rcx, rcx
0x18004c3a1  jz      short loc_18004C3B0
0x18004c3a3  mov     rax, [rcx]
0x18004c3a6  mov     rax, [rax+10h]
0x18004c3aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c3af  nop
0x18004c3b0  test    rbx, rbx
0x18004c3b3  jz      short loc_18004C3C5
0x18004c3b5  mov     rax, [rbx]
0x18004c3b8  mov     rcx, rbx
0x18004c3bb  mov     rax, [rax+10h]
0x18004c3bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c3c4  nop
0x18004c3c5  mov     rcx, [rbp+ppstm]
0x18004c3c9  test    rcx, rcx
0x18004c3cc  jz      short loc_18004C3DB
0x18004c3ce  mov     rax, [rcx]
0x18004c3d1  mov     rax, [rax+10h]
0x18004c3d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c3da  nop
0x18004c3db  cmp     [rbp+var_18], 8
0x18004c3e0  jb      short loc_18004C3F2
0x18004c3e2  mov     rcx, [rbp+pszFile]
0x18004c3e6  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18004c3ed  nop     dword ptr [rax+rax+00h]
0x18004c3f2  xor     eax, eax
0x18004c3f4  mov     rcx, [rbp+var_10]
  ... truncated ...
```
