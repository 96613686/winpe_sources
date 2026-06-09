# MsixPackage::Provisioning::Library::PackageMonikerToPayload::HardlinkFile(ushort *,MsixPackage::Provisioning::Library::HardlinkTarget *,ushort const *)

- ea: `0x1800548a8`
- end: `0x180054b7e`
- name: `?HardlinkFile@PackageMonikerToPayload@Library@Provisioning@MsixPackage@@AEAAJPEAGPEAVHardlinkTarget@234@PEBG@Z`
- size: `726`
- prototype: `int(MsixPackage::Provisioning::Library::PackageMonikerToPayload *__hidden this, unsigned __int16 *, struct MsixPackage::Provisioning::Library::HardlinkTarget *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, reparse_path, installer_update, broker_com_uri`

## callers

- `0x180054cdc`

## callees

- `0x18001bf0c`
- `0x180039e60`
- `0x180039e9c`
- `0x18003ae3c`
- `0x18003f6d8`
- `0x1800548a8`
- `0x180066df0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800549c0`
- `msvcrt!??3@YAXPEAX@Z` at `0x180054af4`
- `msvcrt!??3@YAXPEAX@Z` at `0x180054b17`
- `msvcrt!??3@YAXPEAX@Z` at `0x180054b2e`
- `msvcrt!??3@YAXPEAX@Z` at `0x180054b51`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800549c0`
- `msvcrt!??3@YAXPEAX@Z` at `0x180054af4`
- `msvcrt!??3@YAXPEAX@Z` at `0x180054b17`
- `msvcrt!??3@YAXPEAX@Z` at `0x180054b2e`
- `msvcrt!??3@YAXPEAX@Z` at `0x180054b51`
- `api-ms-win-core-file-l2-1-0!CreateHardLinkW` at `0x180054a8b`
- `api-ms-win-core-file-l2-1-0!CreateHardLinkW` at `0x180054a8b`

## string_xrefs

- `0x180054992`: `Failed to create directory tree for '%ws'.`
- `0x180054acd`: `CreateHardlink from %ws to %ws failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall MsixPackage::Provisioning::Library::PackageMonikerToPayload::HardlinkFile(
        MsixPackage::Provisioning::Library::PackageMonikerToPayload *this,
        char *a2,
        char **a3,
        char *a4)
{
  unsigned __int64 v7; // rbx
  unsigned __int64 v8; // r8
  unsigned __int64 v9; // r8
  WCHAR *v10; // rcx
  int DirectoryTree; // edi
  LPCWSTR *v12; // rdx
  char *v14; // rdx
  unsigned __int64 v15; // r8
  char *v16; // rdx
  const WCHAR *v17; // rdx
  const WCHAR *v18; // rcx
  LPCWSTR *v19; // rdx
  LPCWSTR *v20; // rax
  unsigned int LastErrorMsg; // ebx
  LPCWSTR lpFileName[3]; // [rsp+38h] [rbp-80h] BYREF
  unsigned __int64 v23; // [rsp+50h] [rbp-68h]
  LPCWSTR lpExistingFileName[2]; // [rsp+58h] [rbp-60h] BYREF
  __int64 v25; // [rsp+68h] [rbp-50h]
  unsigned __int64 v26; // [rsp+70h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  v23 = 7;
  lpFileName[2] = 0;
  LOWORD(lpFileName[0]) = 0;
  v7 = -1;
  if ( *(_WORD *)a4 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)&a4[2 * v8] );
  }
  else
  {
    v8 = 0;
  }
  std::wstring::assign(lpFileName, a4, v8);
  std::wstring::append(lpFileName, (char *)L"\\", pszSrc[0] != 0);
  if ( *(_WORD *)a2 )
  {
    v9 = -1;
    do
      ++v9;
    while ( *(_WORD *)&a2[2 * v9] );
  }
  else
  {
    v9 = 0;
  }
  std::wstring::append(lpFileName, a2, v9);
  v10 = (WCHAR *)lpFileName;
  if ( v23 >= 8 )
    v10 = (WCHAR *)lpFileName[0];
  DirectoryTree = MsixPackage::Provisioning::Library::ProvisioningCommonUtils::CreateDirectoryTree(v10);
  if ( DirectoryTree >= 0 )
  {
    v26 = 7;
    v25 = 0;
    LOWORD(lpExistingFileName[0]) = 0;
    std::wstring::assign(lpExistingFileName, (char *)L"\\\\?\\", 4u);
    v14 = *(char **)(*((_QWORD *)this + 6) + 560LL);
    if ( *(_WORD *)v14 )
    {
      v15 = -1;
      do
        ++v15;
      while ( *(_WORD *)&v14[2 * v15] );
    }
    else
    {
      v15 = 0;
    }
    std::wstring::append(lpExistingFileName, v14, v15);
    std::wstring::append(lpExistingFileName, (char *)L"\\", pszSrc[0] != 0);
    v16 = *a3;
    if ( *(_WORD *)*a3 )
    {
      do
        ++v7;
      while ( *(_WORD *)&v16[2 * v7] );
    }
    else
    {
      v7 = 0;
    }
    std::wstring::append(lpExistingFileName, v16, v7);
    v17 = (const WCHAR *)lpExistingFileName;
    if ( v26 >= 8 )
      v17 = lpExistingFileName[0];
    v18 = (const WCHAR *)lpFileName;
    if ( v23 >= 8 )
      v18 = lpFileName[0];
    if ( CreateHardLinkW(v18, v17, 0) )
    {
      if ( v26 >= 8 )
        operator delete((void *)lpExistingFileName[0]);
      v26 = 7;
      v25 = 0;
      LOWORD(lpExistingFileName[0]) = 0;
      if ( v23 >= 8 )
        operator delete((void *)lpFileName[0]);
      return 0;
    }
    else
    {
      v19 = lpFileName;
      if ( v23 >= 8 )
        v19 = (LPCWSTR *)lpFileName[0];
      v20 = lpExistingFileName;
      if ( v26 >= 8 )
        v20 = (LPCWSTR *)lpExistingFileName[0];
      LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                       retaddr,
                       (void *)0x19B,
                       (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagemonikertopayload.cpp",
                       "CreateHardlink from %ws to %ws failed",
                       (const char *)v20,
                       v19);
      if ( v26 >= 8 )
        operator delete((void *)lpExistingFileName[0]);
      v26 = 7;
      v25 = 0;
      LOWORD(lpExistingFileName[0]) = 0;
      if ( v23 >= 8 )
        operator delete((void *)lpFileName[0]);
      return LastErrorMsg;
    }
  }
  else
  {
    v12 = lpFileName;
    if ( v23 >= 8 )
      v12 = (LPCWSTR *)lpFileName[0];
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x191,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagemonikertopayload.cpp",
      (const char *)(unsigned int)DirectoryTree,
      (int)"Failed to create directory tree for '%ws'.",
      (const char *)v12);
    if ( v23 >= 8 )
      operator delete((void *)lpFileName[0]);
    return (unsigned int)DirectoryTree;
  }
}

```

## disassembly

```asm
0x1800548a8  push    rbx
0x1800548aa  push    rsi
0x1800548ab  push    rdi
0x1800548ac  push    r13
0x1800548ae  push    r14
0x1800548b0  push    r15
0x1800548b2  sub     rsp, 88h
0x1800548b9  mov     rax, cs:__security_cookie
0x1800548c0  xor     rax, rsp
0x1800548c3  mov     [rsp+0B8h+var_40], rax
0x1800548c8  mov     r14, r8
0x1800548cb  mov     rdi, rdx
0x1800548ce  mov     rsi, rcx
0x1800548d1  mov     r13d, 7
0x1800548d7  mov     [rsp+0B8h+var_68], r13
0x1800548dc  xor     r15d, r15d
0x1800548df  mov     [rsp+0B8h+var_70], r15
0x1800548e4  mov     word ptr [rsp+0B8h+lpFileName], r15w
0x1800548ea  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800548ee  cmp     [r9], r15w
0x1800548f2  jnz     short loc_1800548F9
0x1800548f4  mov     r8d, r15d
0x1800548f7  jmp     short loc_180054906
0x1800548f9  mov     r8, rbx
0x1800548fc  inc     r8
0x1800548ff  cmp     [r9+r8*2], r15w
0x180054904  jnz     short loc_1800548FC
0x180054906  mov     rdx, r9; Src
0x180054909  lea     rcx, [rsp+0B8h+lpFileName]; void *
0x18005490e  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180054913  mov     r8, r15
0x180054916  cmp     word ptr cs:pszSrc, r15w; "\\"
0x18005491e  setnz   r8b
0x180054922  lea     rdx, pszSrc; "\\"
0x180054929  lea     rcx, [rsp+0B8h+lpFileName]; Src
0x18005492e  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180054933  cmp     [rdi], r15w
0x180054937  jnz     short loc_18005493E
0x180054939  mov     r8, r15
0x18005493c  jmp     short loc_18005494B
0x18005493e  mov     r8, rbx
0x180054941  inc     r8
0x180054944  cmp     [rdi+r8*2], r15w
0x180054949  jnz     short loc_180054941
0x18005494b  mov     rdx, rdi; void *
0x18005494e  lea     rcx, [rsp+0B8h+lpFileName]; Src
0x180054953  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180054958  lea     rcx, [rsp+0B8h+lpFileName]
0x18005495d  cmp     [rsp+0B8h+var_68], 8
0x180054963  cmovnb  rcx, [rsp+0B8h+lpFileName]; lpPathName
0x180054969  call    ?CreateDirectoryTree@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::CreateDirectoryTree(ushort const *)
0x18005496e  mov     edi, eax
0x180054970  test    eax, eax
0x180054972  jns     short loc_1800549CD
0x180054974  lea     rdx, [rsp+0B8h+lpFileName]
0x180054979  cmp     [rsp+0B8h+var_68], 8
0x18005497f  cmovnb  rdx, [rsp+0B8h+lpFileName]
0x180054985  mov     rcx, [rsp+0B8h]; this
0x18005498d  mov     [rsp+0B8h+var_90], rdx; char *
0x180054992  lea     rax, aFailedToCreate_32; "Failed to create directory tree for '%w"...
0x180054999  mov     [rsp+0B8h+var_98], rax; int
0x18005499e  mov     r9d, edi; char *
0x1800549a1  lea     r8, aOnecoreAdminAp_9; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800549a8  mov     edx, 191h; void *
0x1800549ad  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800549b2  nop
0x1800549b3  cmp     [rsp+0B8h+var_68], 8
0x1800549b9  jb      short loc_1800549C6
0x1800549bb  mov     rcx, [rsp+0B8h+lpFileName]
0x1800549c0  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800549c6  mov     eax, edi
0x1800549c8  jmp     loc_180054B5F
0x1800549cd  mov     [rsp+0B8h+var_48], r13
0x1800549d2  mov     [rsp+0B8h+var_50], r15
0x1800549d7  mov     word ptr [rsp+0B8h+lpExistingFileName], r15w
0x1800549dd  mov     r8d, 4
0x1800549e3  lea     rdx, asc_180074250; "\\\\?\\"
0x1800549ea  lea     rcx, [rsp+0B8h+lpExistingFileName]; void *
0x1800549ef  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800549f4  mov     rax, [rsi+30h]
0x1800549f8  mov     rdx, [rax+230h]; void *
0x1800549ff  cmp     [rdx], r15w
0x180054a03  jnz     short loc_180054A0A
0x180054a05  mov     r8, r15
0x180054a08  jmp     short loc_180054A17
0x180054a0a  mov     r8, rbx
0x180054a0d  inc     r8
0x180054a10  cmp     [rdx+r8*2], r15w
0x180054a15  jnz     short loc_180054A0D
0x180054a17  lea     rcx, [rsp+0B8h+lpExistingFileName]; Src
0x180054a1c  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180054a21  mov     r8, r15
0x180054a24  cmp     word ptr cs:pszSrc, r15w; "\\"
0x180054a2c  setnz   r8b
0x180054a30  lea     rdx, pszSrc; "\\"
0x180054a37  lea     rcx, [rsp+0B8h+lpExistingFileName]; Src
0x180054a3c  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180054a41  mov     rdx, [r14]; void *
0x180054a44  cmp     [rdx], r15w
0x180054a48  jnz     short loc_180054A4F
0x180054a4a  mov     rbx, r15
0x180054a4d  jmp     short loc_180054A59
0x180054a4f  inc     rbx
0x180054a52  cmp     [rdx+rbx*2], r15w
0x180054a57  jnz     short loc_180054A4F
0x180054a59  mov     r8, rbx
0x180054a5c  lea     rcx, [rsp+0B8h+lpExistingFileName]; Src
0x180054a61  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180054a66  lea     rdx, [rsp+0B8h+lpExistingFileName]
0x180054a6b  cmp     [rsp+0B8h+var_48], 8
0x180054a71  cmovnb  rdx, [rsp+0B8h+lpExistingFileName]; lpExistingFileName
0x180054a77  lea     rcx, [rsp+0B8h+lpFileName]
0x180054a7c  cmp     [rsp+0B8h+var_68], 8
0x180054a82  cmovnb  rcx, [rsp+0B8h+lpFileName]; lpFileName
0x180054a88  xor     r8d, r8d; lpSecurityAttributes
0x180054a8b  call    cs:__imp_CreateHardLinkW
0x180054a91  test    eax, eax
0x180054a93  jnz     loc_180054B21
0x180054a99  lea     rdx, [rsp+0B8h+lpFileName]
0x180054a9e  cmp     [rsp+0B8h+var_68], 8
0x180054aa4  cmovnb  rdx, [rsp+0B8h+lpFileName]
0x180054aaa  lea     rax, [rsp+0B8h+lpExistingFileName]
0x180054aaf  cmp     [rsp+0B8h+var_48], 8
0x180054ab5  cmovnb  rax, [rsp+0B8h+lpExistingFileName]
0x180054abb  mov     rcx, [rsp+0B8h]; this
0x180054ac3  mov     [rsp+0B8h+var_90], rdx
0x180054ac8  mov     [rsp+0B8h+var_98], rax; char *
0x180054acd  lea     r9, aCreatehardlink; "CreateHardlink from %ws to %ws failed"
0x180054ad4  lea     r8, aOnecoreAdminAp_9; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180054adb  mov     edx, 19Bh; void *
0x180054ae0  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x180054ae5  mov     ebx, eax
0x180054ae7  cmp     [rsp+0B8h+var_48], 8
0x180054aed  jb      short loc_180054AFA
0x180054aef  mov     rcx, [rsp+0B8h+lpExistingFileName]
0x180054af4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180054afa  mov     [rsp+0B8h+var_48], r13
0x180054aff  mov     [rsp+0B8h+var_50], r15
0x180054b04  mov     word ptr [rsp+0B8h+lpExistingFileName], r15w
0x180054b0a  cmp     [rsp+0B8h+var_68], 8
0x180054b10  jb      short loc_180054B1D
0x180054b12  mov     rcx, [rsp+0B8h+lpFileName]
0x180054b17  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180054b1d  mov     eax, ebx
0x180054b1f  jmp     short loc_180054B5F
0x180054b21  cmp     [rsp+0B8h+var_48], 8
0x180054b27  jb      short loc_180054B34
0x180054b29  mov     rcx, [rsp+0B8h+lpExistingFileName]
0x180054b2e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180054b34  mov     [rsp+0B8h+var_48], r13
0x180054b39  mov     [rsp+0B8h+var_50], r15
0x180054b3e  mov     word ptr [rsp+0B8h+lpExistingFileName], r15w
0x180054b44  cmp     [rsp+0B8h+var_68], 8
0x180054b4a  jb      short loc_180054B57
0x180054b4c  mov     rcx, [rsp+0B8h+lpFileName]
0x180054b51  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180054b57  xor     eax, eax
0x180054b59  jmp     short loc_180054B5F
0x180054b5b  mov     eax, [rsp+0B8h+var_88]
0x180054b5f  mov     rcx, [rsp+0B8h+var_40]
0x180054b64  xor     rcx, rsp; StackCookie
0x180054b67  call    __security_check_cookie
0x180054b6c  add     rsp, 88h
0x180054b73  pop     r15
0x180054b75  pop     r14
0x180054b77  pop     r13
0x180054b79  pop     rdi
0x180054b7a  pop     rsi
0x180054b7b  pop     rbx
0x180054b7c  retn
```
