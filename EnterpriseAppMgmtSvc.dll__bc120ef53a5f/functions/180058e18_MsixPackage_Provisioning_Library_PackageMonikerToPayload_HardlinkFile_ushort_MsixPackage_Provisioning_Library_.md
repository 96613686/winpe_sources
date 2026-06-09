# MsixPackage::Provisioning::Library::PackageMonikerToPayload::HardlinkFile(ushort *,MsixPackage::Provisioning::Library::HardlinkTarget *,ushort const *)

- ea: `0x180058e18`
- end: `0x180059112`
- name: `?HardlinkFile@PackageMonikerToPayload@Library@Provisioning@MsixPackage@@AEAAJPEAGPEAVHardlinkTarget@234@PEBG@Z`
- size: `762`
- prototype: `int(MsixPackage::Provisioning::Library::PackageMonikerToPayload *__hidden this, unsigned __int16 *, struct MsixPackage::Provisioning::Library::HardlinkTarget *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, reparse_path, installer_update, broker_com_uri`

## callers

- `0x180059274`

## callees

- `0x18001d160`
- `0x18003d4b0`
- `0x18003d4ec`
- `0x18003e50c`
- `0x180043174`
- `0x180058e18`
- `0x18006c910`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180058f30`
- `msvcrt!??3@YAXPEAX@Z` at `0x180059070`
- `msvcrt!??3@YAXPEAX@Z` at `0x180059099`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800590b6`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800590df`
- `msvcrt!??3@YAXPEAX@Z` at `0x180058f30`
- `msvcrt!??3@YAXPEAX@Z` at `0x180059070`
- `msvcrt!??3@YAXPEAX@Z` at `0x180059099`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800590b6`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800590df`
- `api-ms-win-core-file-l2-1-0!CreateHardLinkW` at `0x180059001`
- `api-ms-win-core-file-l2-1-0!CreateHardLinkW` at `0x180059001`

## string_xrefs

- `0x180059049`: `CreateHardlink from %ws to %ws failed`
- `0x180058f02`: `Failed to create directory tree for '%ws'.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall MsixPackage::Provisioning::Library::PackageMonikerToPayload::HardlinkFile(
        MsixPackage::Provisioning::Library::PackageMonikerToPayload *this,
        unsigned __int16 *a2,
        struct MsixPackage::Provisioning::Library::HardlinkTarget *a3,
        unsigned __int16 *a4)
{
  __int64 v7; // rbx
  __int64 v8; // r8
  __int64 v9; // r8
  WCHAR *v10; // rcx
  int DirectoryTree; // edi
  LPCWSTR *v12; // rdx
  _WORD *v14; // rdx
  __int64 v15; // r8
  _WORD *v16; // rdx
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
  if ( *a4 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a4[v8] );
  }
  std::wstring::assign(lpFileName, a4);
  std::wstring::append(lpFileName, (void *)L"\\");
  if ( *a2 )
  {
    v9 = -1;
    do
      ++v9;
    while ( a2[v9] );
  }
  std::wstring::append(lpFileName, a2);
  v10 = (WCHAR *)lpFileName;
  if ( v23 >= 8 )
    v10 = (WCHAR *)lpFileName[0];
  DirectoryTree = MsixPackage::Provisioning::Library::ProvisioningCommonUtils::CreateDirectoryTree(v10);
  if ( DirectoryTree >= 0 )
  {
    v26 = 7;
    v25 = 0;
    LOWORD(lpExistingFileName[0]) = 0;
    std::wstring::assign(lpExistingFileName, (void *)L"\\\\?\\");
    v14 = *(_WORD **)(*((_QWORD *)this + 6) + 560LL);
    if ( *v14 )
    {
      v15 = -1;
      do
        ++v15;
      while ( v14[v15] );
    }
    std::wstring::append(lpExistingFileName, v14);
    std::wstring::append(lpExistingFileName, (void *)L"\\");
    v16 = *(_WORD **)a3;
    if ( **(_WORD **)a3 )
    {
      do
        ++v7;
      while ( v16[v7] );
    }
    std::wstring::append(lpExistingFileName, v16);
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
0x180058e18  push    rbx
0x180058e1a  push    rsi
0x180058e1b  push    rdi
0x180058e1c  push    r13
0x180058e1e  push    r14
0x180058e20  push    r15
0x180058e22  sub     rsp, 88h
0x180058e29  mov     rax, cs:__security_cookie
0x180058e30  xor     rax, rsp
0x180058e33  mov     [rsp+0B8h+var_40], rax
0x180058e38  mov     r14, r8
0x180058e3b  mov     rdi, rdx
0x180058e3e  mov     rsi, rcx
0x180058e41  mov     r13d, 7
0x180058e47  mov     [rsp+0B8h+var_68], r13
0x180058e4c  xor     r15d, r15d
0x180058e4f  mov     [rsp+0B8h+var_70], r15
0x180058e54  mov     word ptr [rsp+0B8h+lpFileName], r15w
0x180058e5a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180058e5e  cmp     [r9], r15w
0x180058e62  jnz     short loc_180058E69
0x180058e64  mov     r8d, r15d
0x180058e67  jmp     short loc_180058E76
0x180058e69  mov     r8, rbx
0x180058e6c  inc     r8
0x180058e6f  cmp     [r9+r8*2], r15w
0x180058e74  jnz     short loc_180058E6C
0x180058e76  mov     rdx, r9; Src
0x180058e79  lea     rcx, [rsp+0B8h+lpFileName]; void *
0x180058e7e  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180058e83  mov     r8, r15
0x180058e86  cmp     word ptr cs:pszSrc, r15w; "\\"
0x180058e8e  setnz   r8b
0x180058e92  lea     rdx, pszSrc; "\\"
0x180058e99  lea     rcx, [rsp+0B8h+lpFileName]; Src
0x180058e9e  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180058ea3  cmp     [rdi], r15w
0x180058ea7  jnz     short loc_180058EAE
0x180058ea9  mov     r8, r15
0x180058eac  jmp     short loc_180058EBB
0x180058eae  mov     r8, rbx
0x180058eb1  inc     r8
0x180058eb4  cmp     [rdi+r8*2], r15w
0x180058eb9  jnz     short loc_180058EB1
0x180058ebb  mov     rdx, rdi; void *
0x180058ebe  lea     rcx, [rsp+0B8h+lpFileName]; Src
0x180058ec3  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180058ec8  lea     rcx, [rsp+0B8h+lpFileName]
0x180058ecd  cmp     [rsp+0B8h+var_68], 8
0x180058ed3  cmovnb  rcx, [rsp+0B8h+lpFileName]; lpPathName
0x180058ed9  call    ?CreateDirectoryTree@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::CreateDirectoryTree(ushort const *)
0x180058ede  mov     edi, eax
0x180058ee0  test    eax, eax
0x180058ee2  jns     short loc_180058F43
0x180058ee4  lea     rdx, [rsp+0B8h+lpFileName]
0x180058ee9  cmp     [rsp+0B8h+var_68], 8
0x180058eef  cmovnb  rdx, [rsp+0B8h+lpFileName]
0x180058ef5  mov     rcx, [rsp+0B8h]; this
0x180058efd  mov     [rsp+0B8h+var_90], rdx; char *
0x180058f02  lea     rax, aFailedToCreate_32; "Failed to create directory tree for '%w"...
0x180058f09  mov     [rsp+0B8h+var_98], rax; int
0x180058f0e  mov     r9d, edi; char *
0x180058f11  lea     r8, aOnecoreAdminAp_9; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180058f18  mov     edx, 191h; void *
0x180058f1d  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180058f22  nop
0x180058f23  cmp     [rsp+0B8h+var_68], 8
0x180058f29  jb      short loc_180058F3C
0x180058f2b  mov     rcx, [rsp+0B8h+lpFileName]
0x180058f30  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180058f37  nop     dword ptr [rax+rax+00h]
0x180058f3c  mov     eax, edi
0x180058f3e  jmp     loc_1800590F3
0x180058f43  mov     [rsp+0B8h+var_48], r13
0x180058f48  mov     [rsp+0B8h+var_50], r15
0x180058f4d  mov     word ptr [rsp+0B8h+lpExistingFileName], r15w
0x180058f53  mov     r8d, 4
0x180058f59  lea     rdx, asc_18007A250; "\\\\?\\"
0x180058f60  lea     rcx, [rsp+0B8h+lpExistingFileName]; void *
0x180058f65  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180058f6a  mov     rax, [rsi+30h]
0x180058f6e  mov     rdx, [rax+230h]; void *
0x180058f75  cmp     [rdx], r15w
0x180058f79  jnz     short loc_180058F80
0x180058f7b  mov     r8, r15
0x180058f7e  jmp     short loc_180058F8D
0x180058f80  mov     r8, rbx
0x180058f83  inc     r8
0x180058f86  cmp     [rdx+r8*2], r15w
0x180058f8b  jnz     short loc_180058F83
0x180058f8d  lea     rcx, [rsp+0B8h+lpExistingFileName]; Src
0x180058f92  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180058f97  mov     r8, r15
0x180058f9a  cmp     word ptr cs:pszSrc, r15w; "\\"
0x180058fa2  setnz   r8b
0x180058fa6  lea     rdx, pszSrc; "\\"
0x180058fad  lea     rcx, [rsp+0B8h+lpExistingFileName]; Src
0x180058fb2  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180058fb7  mov     rdx, [r14]; void *
0x180058fba  cmp     [rdx], r15w
0x180058fbe  jnz     short loc_180058FC5
0x180058fc0  mov     rbx, r15
0x180058fc3  jmp     short loc_180058FCF
0x180058fc5  inc     rbx
0x180058fc8  cmp     [rdx+rbx*2], r15w
0x180058fcd  jnz     short loc_180058FC5
0x180058fcf  mov     r8, rbx
0x180058fd2  lea     rcx, [rsp+0B8h+lpExistingFileName]; Src
0x180058fd7  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180058fdc  lea     rdx, [rsp+0B8h+lpExistingFileName]
0x180058fe1  cmp     [rsp+0B8h+var_48], 8
0x180058fe7  cmovnb  rdx, [rsp+0B8h+lpExistingFileName]; lpExistingFileName
0x180058fed  lea     rcx, [rsp+0B8h+lpFileName]
0x180058ff2  cmp     [rsp+0B8h+var_68], 8
0x180058ff8  cmovnb  rcx, [rsp+0B8h+lpFileName]; lpFileName
0x180058ffe  xor     r8d, r8d; lpSecurityAttributes
0x180059001  call    cs:__imp_CreateHardLinkW
0x180059008  nop     dword ptr [rax+rax+00h]
0x18005900d  test    eax, eax
0x18005900f  jnz     loc_1800590A9
0x180059015  lea     rdx, [rsp+0B8h+lpFileName]
0x18005901a  cmp     [rsp+0B8h+var_68], 8
0x180059020  cmovnb  rdx, [rsp+0B8h+lpFileName]
0x180059026  lea     rax, [rsp+0B8h+lpExistingFileName]
0x18005902b  cmp     [rsp+0B8h+var_48], 8
0x180059031  cmovnb  rax, [rsp+0B8h+lpExistingFileName]
0x180059037  mov     rcx, [rsp+0B8h]; this
0x18005903f  mov     [rsp+0B8h+var_90], rdx
0x180059044  mov     [rsp+0B8h+var_98], rax; char *
0x180059049  lea     r9, aCreatehardlink; "CreateHardlink from %ws to %ws failed"
0x180059050  lea     r8, aOnecoreAdminAp_9; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180059057  mov     edx, 19Bh; void *
0x18005905c  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x180059061  mov     ebx, eax
0x180059063  cmp     [rsp+0B8h+var_48], 8
0x180059069  jb      short loc_18005907C
0x18005906b  mov     rcx, [rsp+0B8h+lpExistingFileName]
0x180059070  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180059077  nop     dword ptr [rax+rax+00h]
0x18005907c  mov     [rsp+0B8h+var_48], r13
0x180059081  mov     [rsp+0B8h+var_50], r15
0x180059086  mov     word ptr [rsp+0B8h+lpExistingFileName], r15w
0x18005908c  cmp     [rsp+0B8h+var_68], 8
0x180059092  jb      short loc_1800590A5
0x180059094  mov     rcx, [rsp+0B8h+lpFileName]
0x180059099  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800590a0  nop     dword ptr [rax+rax+00h]
0x1800590a5  mov     eax, ebx
0x1800590a7  jmp     short loc_1800590F3
0x1800590a9  cmp     [rsp+0B8h+var_48], 8
0x1800590af  jb      short loc_1800590C2
0x1800590b1  mov     rcx, [rsp+0B8h+lpExistingFileName]
0x1800590b6  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800590bd  nop     dword ptr [rax+rax+00h]
0x1800590c2  mov     [rsp+0B8h+var_48], r13
0x1800590c7  mov     [rsp+0B8h+var_50], r15
0x1800590cc  mov     word ptr [rsp+0B8h+lpExistingFileName], r15w
0x1800590d2  cmp     [rsp+0B8h+var_68], 8
0x1800590d8  jb      short loc_1800590EB
0x1800590da  mov     rcx, [rsp+0B8h+lpFileName]
0x1800590df  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800590e6  nop     dword ptr [rax+rax+00h]
0x1800590eb  xor     eax, eax
0x1800590ed  jmp     short loc_1800590F3
0x1800590ef  mov     eax, [rsp+0B8h+var_88]
0x1800590f3  mov     rcx, [rsp+0B8h+var_40]
0x1800590f8  xor     rcx, rsp; StackCookie
0x1800590fb  call    __security_check_cookie
0x180059100  add     rsp, 88h
0x180059107  pop     r15
0x180059109  pop     r14
0x18005910b  pop     r13
0x18005910d  pop     rdi
0x18005910e  pop     rsi
0x18005910f  pop     rbx
0x180059110  retn
```
