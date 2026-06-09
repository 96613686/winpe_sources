# OSIntegration::DEH::Internal::CustomInstallExtensionHelper::AclCustomInstallFolder(void)

- ea: `0x18008a774`
- end: `0x18008a9c3`
- name: `?AclCustomInstallFolder@CustomInstallExtensionHelper@Internal@DEH@OSIntegration@@IEAAXXZ`
- size: `591`
- prototype: `void __fastcall(OSIntegration::DEH::Internal::CustomInstallExtensionHelper *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800eedc0`

## callees

- `0x18003d9b0`
- `0x180064a88`
- `0x1800687ac`
- `0x18008a774`
- `0x18008a9cc`
- `0x18008aa14`
- `0x18008ab30`
- `0x18008abf4`
- `0x1800af1bc`
- `0x180173890`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008a98f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008a98f`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x18008a975`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x18008a975`
- `ADVAPI32!RevertToSelf` at `0x18008a9ad`
- `ADVAPI32!RevertToSelf` at `0x18008a9ad`

## string_xrefs

- `0x18008a7ba`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\dehlib\custominstallextensionhelper.cpp`
- `0x18008a7fd`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\dehlib\custominstallextensionhelper.cpp`
- `0x18008a823`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\dehlib\custominstallextensionhelper.cpp`
- `0x18008a866`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\dehlib\custominstallextensionhelper.cpp`
- `0x18008a88c`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\dehlib\custominstallextensionhelper.cpp`
- `0x18008a8e1`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\dehlib\custominstallextensionhelper.cpp`
- `0x18008a90b`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\dehlib\custominstallextensionhelper.cpp`
- `0x18008a931`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\dehlib\custominstallextensionhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall OSIntegration::DEH::Internal::CustomInstallExtensionHelper::AclCustomInstallFolder(
        OSIntegration::DEH::Internal::CustomInstallExtensionHelper *this)
{
  int v2; // eax
  int v3; // eax
  int v4; // eax
  int v5; // eax
  int v6; // eax
  int appended; // eax
  int v8; // eax
  const unsigned __int16 *v9; // rdx
  int v10; // eax
  const struct std::nothrow_t *v11; // rdx
  int v12; // [rsp+20h] [rbp-39h] BYREF
  HANDLE hToken; // [rsp+28h] [rbp-31h]
  DirectoryACLs *v14[2]; // [rsp+30h] [rbp-29h] BYREF
  int v15; // [rsp+40h] [rbp-19h]
  _QWORD v16[3]; // [rsp+48h] [rbp-11h] BYREF
  void *v17[2]; // [rsp+60h] [rbp+7h] BYREF
  char v18; // [rsp+70h] [rbp+17h]
  char v19; // [rsp+78h] [rbp+1Fh]
  __int64 v20; // [rsp+80h] [rbp+27h]
  void *TokenHandle[2]; // [rsp+88h] [rbp+2Fh] BYREF
  char v22; // [rsp+98h] [rbp+3Fh]
  char v23; // [rsp+A0h] [rbp+47h]
  __int64 v24; // [rsp+A8h] [rbp+4Fh]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  if ( !*(_BYTE *)(*((_QWORD *)this + 2) + 413LL) )
  {
    LOBYTE(v12) = 0;
    hToken = 0;
    v2 = Common::ImpersonateSelf::Impersonate((Common::ImpersonateSelf *)&v12);
    if ( v2 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xBE,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\dehlib\\custominstallextensionhelper.cpp",
        (const char *)(unsigned int)v2,
        v12);
    *(_OWORD *)TokenHandle = 0;
    v22 = 0;
    v23 = 0;
    v24 = 0;
    v3 = Common::Deployment::Privilege::Initialize(TokenHandle, 8);
    if ( v3 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xC1,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\dehlib\\custominstallextensionhelper.cpp",
        (const char *)(unsigned int)v3,
        v12);
    v4 = Common::Deployment::Privilege::Enable((Common::Deployment::Privilege *)TokenHandle);
    if ( v4 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xC2,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\dehlib\\custominstallextensionhelper.cpp",
        (const char *)(unsigned int)v4,
        v12);
    *(_OWORD *)v17 = 0;
    v18 = 0;
    v19 = 0;
    v20 = 0;
    v5 = Common::Deployment::Privilege::Initialize(v17, 18);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xC5,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\dehlib\\custominstallextensionhelper.cpp",
        (const char *)(unsigned int)v5,
        v12);
    v6 = Common::Deployment::Privilege::Enable((Common::Deployment::Privilege *)v17);
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xC6,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\dehlib\\custominstallextensionhelper.cpp",
        (const char *)(unsigned int)v6,
        v12);
    *(_OWORD *)v14 = 0;
    v15 = 0;
    v16[1] = v14;
    v16[0] = &Common::StringBufferBuilder::`vftable';
    v16[2] = v14;
    appended = Common::StringBuilder::AppendString(
                 (Common::StringBuilder *)v16,
                 *(const unsigned __int16 **)(*((_QWORD *)this + 2) + 96LL));
    if ( appended < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xCA,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\dehlib\\custominstallextensionhelper.cpp",
        (const char *)(unsigned int)appended,
        v12);
    v8 = Common::StringBuilder::AppendString((Common::StringBuilder *)v16, *((const unsigned __int16 **)this + 4));
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xCB,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\dehlib\\custominstallextensionhelper.cpp",
        (const char *)(unsigned int)v8,
        v12);
    v10 = DirectoryACLs::ConvertConditionalAcesToUnconditionalAces(v14[1], v9);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xCE,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\dehlib\\custominstallextensionhelper.cpp",
        (const char *)(unsigned int)v10,
        v12);
    if ( v14[1] )
      operator delete(v14[1], v11);
    Common::Deployment::Privilege::~Privilege((Common::Deployment::Privilege *)v17);
    Common::Deployment::Privilege::~Privilege((Common::Deployment::Privilege *)TokenHandle);
    if ( (_BYTE)v12 )
    {
      if ( hToken )
      {
        if ( !ImpersonateLoggedOnUser(hToken) )
        {
          Common::HandleInternalFailure();
          __debugbreak();
        }
        CloseHandle(hToken);
      }
      else if ( !RevertToSelf() )
      {
        Common::HandleInternalFailure();
        JUMPOUT(0x18008A9C2LL);
      }
    }
  }
}

```

## disassembly

```asm
0x18008a774  mov     [rsp-8+arg_0], rbx
0x18008a779  push    rbp
0x18008a77a  lea     rbp, [rsp-57h]
0x18008a77f  sub     rsp, 0B0h
0x18008a786  mov     rbx, rcx
0x18008a789  mov     rax, [rcx+10h]
0x18008a78d  cmp     byte ptr [rax+19Dh], 0
0x18008a794  jnz     loc_18008A99B
0x18008a79a  mov     byte ptr [rbp+57h+var_90], 0
0x18008a79e  mov     [rbp+57h+hToken], 0
0x18008a7a6  lea     rcx, [rbp+57h+var_90]; this
0x18008a7aa  call    ?Impersonate@ImpersonateSelf@Common@@QEAAJXZ; Common::ImpersonateSelf::Impersonate(void)
0x18008a7af  mov     rcx, [rbp+5Fh]; this
0x18008a7b3  test    eax, eax
0x18008a7b5  jns     short loc_18008A7CC
0x18008a7b7  mov     r9d, eax; char *
0x18008a7ba  lea     r8, aOnecoreAdminAp_71; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18008a7c1  mov     edx, 0BEh; void *
0x18008a7c6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008a7cc  xorps   xmm0, xmm0
0x18008a7cf  movdqu  xmmword ptr [rbp+57h+TokenHandle], xmm0
0x18008a7d4  mov     [rbp+57h+var_18], 0
0x18008a7d8  mov     [rbp+57h+var_10], 0
0x18008a7dc  mov     [rbp+57h+var_8], 0
0x18008a7e4  mov     edx, 8; int
0x18008a7e9  lea     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18008a7ed  call    ?Initialize@Privilege@Deployment@Common@@QEAAJJ@Z; Common::Deployment::Privilege::Initialize(long)
0x18008a7f2  mov     rcx, [rbp+5Fh]; this
0x18008a7f6  test    eax, eax
0x18008a7f8  jns     short loc_18008A80F
0x18008a7fa  mov     r9d, eax; char *
0x18008a7fd  lea     r8, aOnecoreAdminAp_71; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18008a804  mov     edx, 0C1h; void *
0x18008a809  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008a80f  lea     rcx, [rbp+57h+TokenHandle]; this
0x18008a813  call    ?Enable@Privilege@Deployment@Common@@QEAAJXZ; Common::Deployment::Privilege::Enable(void)
0x18008a818  mov     rcx, [rbp+5Fh]; this
0x18008a81c  test    eax, eax
0x18008a81e  jns     short loc_18008A835
0x18008a820  mov     r9d, eax; char *
0x18008a823  lea     r8, aOnecoreAdminAp_71; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18008a82a  mov     edx, 0C2h; void *
0x18008a82f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008a835  xorps   xmm0, xmm0
0x18008a838  movdqu  xmmword ptr [rbp+57h+var_50], xmm0
0x18008a83d  mov     [rbp+57h+var_40], 0
0x18008a841  mov     [rbp+57h+var_38], 0
0x18008a845  mov     [rbp+57h+var_30], 0
0x18008a84d  mov     edx, 12h; int
0x18008a852  lea     rcx, [rbp+57h+var_50]; TokenHandle
0x18008a856  call    ?Initialize@Privilege@Deployment@Common@@QEAAJJ@Z; Common::Deployment::Privilege::Initialize(long)
0x18008a85b  mov     rcx, [rbp+5Fh]; this
0x18008a85f  test    eax, eax
0x18008a861  jns     short loc_18008A878
0x18008a863  mov     r9d, eax; char *
0x18008a866  lea     r8, aOnecoreAdminAp_71; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18008a86d  mov     edx, 0C5h; void *
0x18008a872  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008a878  lea     rcx, [rbp+57h+var_50]; this
0x18008a87c  call    ?Enable@Privilege@Deployment@Common@@QEAAJXZ; Common::Deployment::Privilege::Enable(void)
0x18008a881  mov     rcx, [rbp+5Fh]; this
0x18008a885  test    eax, eax
0x18008a887  jns     short loc_18008A89E
0x18008a889  mov     r9d, eax; char *
0x18008a88c  lea     r8, aOnecoreAdminAp_71; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18008a893  mov     edx, 0C6h; void *
0x18008a898  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008a89e  xor     eax, eax
0x18008a8a0  xorps   xmm0, xmm0
0x18008a8a3  movups  xmmword ptr [rbp+57h+var_80], xmm0
0x18008a8a7  mov     [rbp+57h+var_70], eax
0x18008a8aa  lea     rax, [rbp+57h+var_80]
0x18008a8ae  mov     [rbp+57h+var_60], rax
0x18008a8b2  lea     rax, ??_7StringBufferBuilder@Common@@6B@; const Common::StringBufferBuilder::`vftable'
0x18008a8b9  mov     [rbp+57h+var_68], rax
0x18008a8bd  lea     rax, [rbp+57h+var_80]
0x18008a8c1  mov     [rbp+57h+var_58], rax
0x18008a8c5  mov     rdx, [rbx+10h]
0x18008a8c9  mov     rdx, [rdx+60h]; unsigned __int16 *
0x18008a8cd  lea     rcx, [rbp+57h+var_68]; this
0x18008a8d1  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x18008a8d6  mov     rcx, [rbp+5Fh]; this
0x18008a8da  test    eax, eax
0x18008a8dc  jns     short loc_18008A8F3
0x18008a8de  mov     r9d, eax; char *
0x18008a8e1  lea     r8, aOnecoreAdminAp_71; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18008a8e8  mov     edx, 0CAh; void *
0x18008a8ed  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008a8f3  mov     rdx, [rbx+20h]; unsigned __int16 *
0x18008a8f7  lea     rcx, [rbp+57h+var_68]; this
0x18008a8fb  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x18008a900  mov     rcx, [rbp+5Fh]; this
0x18008a904  test    eax, eax
0x18008a906  jns     short loc_18008A91D
0x18008a908  mov     r9d, eax; char *
0x18008a90b  lea     r8, aOnecoreAdminAp_71; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18008a912  mov     edx, 0CBh; void *
0x18008a917  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008a91d  mov     rcx, [rbp+57h+var_80+8]; this
0x18008a921  call    ?ConvertConditionalAcesToUnconditionalAces@DirectoryACLs@@YAJPEBG@Z; DirectoryACLs::ConvertConditionalAcesToUnconditionalAces(ushort const *)
0x18008a926  mov     rcx, [rbp+5Fh]; this
0x18008a92a  test    eax, eax
0x18008a92c  jns     short loc_18008A943
0x18008a92e  mov     r9d, eax; char *
0x18008a931  lea     r8, aOnecoreAdminAp_71; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18008a938  mov     edx, 0CEh; void *
0x18008a93d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008a943  mov     rcx, [rbp+57h+var_80+8]; void *
0x18008a947  test    rcx, rcx
0x18008a94a  jz      short loc_18008A952
0x18008a94c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18008a951  nop
0x18008a952  lea     rcx, [rbp+57h+var_50]; this
0x18008a956  call    ??1Privilege@Deployment@Common@@QEAA@XZ; Common::Deployment::Privilege::~Privilege(void)
0x18008a95b  nop
0x18008a95c  lea     rcx, [rbp+57h+TokenHandle]; this
0x18008a960  call    ??1Privilege@Deployment@Common@@QEAA@XZ; Common::Deployment::Privilege::~Privilege(void)
0x18008a965  nop
0x18008a966  cmp     byte ptr [rbp+57h+var_90], 0
0x18008a96a  jz      short loc_18008A99B
0x18008a96c  mov     rcx, [rbp+57h+hToken]; hToken
0x18008a970  test    rcx, rcx
0x18008a973  jz      short loc_18008A9AD
0x18008a975  call    cs:__imp_ImpersonateLoggedOnUser
0x18008a97c  nop     dword ptr [rax+rax+00h]
0x18008a981  test    eax, eax
0x18008a983  jnz     short loc_18008A98B
0x18008a985  call    ?HandleInternalFailure@Common@@YAXW4FATAL_FAILURE_REASON_TYPE@1@_KK@Z; Common::HandleInternalFailure(Common::FATAL_FAILURE_REASON_TYPE,unsigned __int64,ulong)
0x18008a98a  int     3; Trap to Debugger
0x18008a98b  mov     rcx, [rbp+57h+hToken]; hObject
0x18008a98f  call    cs:__imp_CloseHandle
0x18008a996  nop     dword ptr [rax+rax+00h]
0x18008a99b  mov     rbx, [rsp+0B0h+arg_0]
0x18008a9a3  add     rsp, 0B0h
0x18008a9aa  pop     rbp
0x18008a9ab  retn
0x18008a9ad  call    cs:__imp_RevertToSelf
0x18008a9b4  nop     dword ptr [rax+rax+00h]
0x18008a9b9  test    eax, eax
0x18008a9bb  jnz     short loc_18008A99B
0x18008a9bd  call    ?HandleInternalFailure@Common@@YAXW4FATAL_FAILURE_REASON_TYPE@1@_KK@Z; Common::HandleInternalFailure(Common::FATAL_FAILURE_REASON_TYPE,unsigned __int64,ulong)
```
