# MsixPackage::Provisioning::Library::MsixProvisioningContext::GetProvisionWriter(IAppxProvisionWriter * *)

- ea: `0x180041e7c`
- end: `0x18004223c`
- name: `?GetProvisionWriter@MsixProvisioningContext@Library@Provisioning@MsixPackage@@AEAAJPEAPEAUIAppxProvisionWriter@@@Z`
- size: `960`
- prototype: `__int64 __fastcall(MsixPackage::Provisioning::Library::MsixProvisioningContext *__hidden this, struct IAppxProvisionWriter **)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x18003efd0`
- `0x180042e20`

## callees

- `0x18001d050`
- `0x18003d4ec`
- `0x18003e50c`
- `0x180041a08`
- `0x180041aa0`
- `0x180041e7c`
- `0x180042244`
- `0x18006c910`
- `0x180070010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180041f7a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004209e`
- `msvcrt!??3@YAXPEAX@Z` at `0x180042179`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800421c2`
- `msvcrt!??3@YAXPEAX@Z` at `0x180041f7a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004209e`
- `msvcrt!??3@YAXPEAX@Z` at `0x180042179`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800421c2`

## string_xrefs

- `0x180041eed`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningcontext.cpp`
- `0x180041f5b`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningcontext.cpp`
- `0x18004207f`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningcontext.cpp`
- `0x18004215a`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningcontext.cpp`
- `0x180042070`: `Failed to create writer for file %ws.`
- `0x18004214b`: `Failed to create writer for file %ws.`
- `0x180041f4c`: `Failed to create temp directory.`
- `0x180041fe4`: `AppxProvisioning.xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall MsixPackage::Provisioning::Library::MsixProvisioningContext::GetProvisionWriter(
        MsixPackage::Provisioning::Library::MsixProvisioningContext *this,
        struct IAppxProvisionWriter **a2)
{
  struct IAppxProvisionWriter **v4; // r14
  int ProvisionFactory; // edi
  const char *v6; // r9
  __int64 result; // rax
  int TemporaryPath; // edi
  char *v9; // rsi
  int ProvisionReader; // eax
  struct IAppxProvisionFactory *v11; // rbx
  bool v12; // sf
  __int64 v13; // rax
  __int64 (__fastcall *v14)(struct IAppxProvisionFactory *, char *, struct IAppxProvisionWriter **); // rdi
  struct IAppxProvisionWriter *v15; // rcx
  char *v16; // rdx
  int v17; // edi
  struct IAppxProvisionReader *v18; // rdi
  __int64 (__fastcall *v19)(struct IAppxProvisionFactory *, struct IAppxProvisionReader *, char *, struct IAppxProvisionWriter **); // r15
  struct IAppxProvisionWriter *v20; // rcx
  char *v21; // r8
  int v22; // r15d
  struct IAppxProvisionWriter *v23; // rcx
  char *v24; // [rsp+28h] [rbp-70h]
  struct IAppxProvisionFactory *v25; // [rsp+30h] [rbp-68h] BYREF
  struct IAppxProvisionReader *v26; // [rsp+38h] [rbp-60h] BYREF
  void *v27[3]; // [rsp+40h] [rbp-58h] BYREF
  unsigned __int64 v28; // [rsp+58h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  try
  {
    *a2 = 0;
    v4 = (struct IAppxProvisionWriter **)((char *)this + 728);
    if ( *((_QWORD *)this + 91) )
    {
LABEL_51:
      v23 = *v4;
      *a2 = *v4;
      (*(void (__fastcall **)(struct IAppxProvisionWriter *))(*(_QWORD *)v23 + 8LL))(v23);
      return 0;
    }
    v26 = 0;
    v25 = 0;
    ProvisionFactory = MsixPackage::Provisioning::Library::MsixProvisioningContext::GetProvisionFactory(this, &v25);
    if ( ProvisionFactory < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x1FC,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningcontext.cpp",
        (const char *)(unsigned int)ProvisionFactory,
        (int)"Failed to obtain provisioning factory.",
        v24);
      if ( v25 )
        (*(void (__fastcall **)(struct IAppxProvisionFactory *))(*(_QWORD *)v25 + 16LL))(v25);
      return (unsigned int)ProvisionFactory;
    }
    v28 = 7;
    v27[2] = 0;
    LOWORD(v27[0]) = 0;
    TemporaryPath = MsixPackage::Provisioning::Library::MsixProvisioningContext::GetTemporaryPath(this, v27);
    if ( TemporaryPath < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x200,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningcontext.cpp",
        (const char *)(unsigned int)TemporaryPath,
        (int)"Failed to create temp directory.",
        v24);
      if ( v28 >= 8 )
        operator delete(v27[0]);
      if ( v25 )
        (*(void (__fastcall **)(struct IAppxProvisionFactory *))(*(_QWORD *)v25 + 16LL))(v25);
      return (unsigned int)TemporaryPath;
    }
    v9 = (char *)this + 688;
    std::wstring::assign((char *)this + 688);
    std::wstring::append((char *)this + 688, (void *)L"\\");
    std::wstring::append((char *)this + 688, L"AppxProvisioning.xml");
    v26 = 0;
    ProvisionReader = MsixPackage::Provisioning::Library::MsixProvisioningContext::GetProvisionReader(this, &v26);
    v11 = v25;
    v12 = ProvisionReader < 0;
    v13 = *(_QWORD *)v25;
    if ( v12 )
    {
      v14 = *(__int64 (__fastcall **)(struct IAppxProvisionFactory *, char *, struct IAppxProvisionWriter **))(v13 + 32);
      v15 = *v4;
      *v4 = 0;
      if ( v15 )
        (*(void (__fastcall **)(struct IAppxProvisionWriter *))(*(_QWORD *)v15 + 16LL))(v15);
      if ( *((_QWORD *)v9 + 3) < 8u )
        v16 = v9;
      else
        v16 = *(char **)v9;
      v17 = v14(v11, v16, v4);
      if ( v17 < 0 )
      {
        if ( *((_QWORD *)v9 + 3) >= 8u )
          v9 = *(char **)v9;
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x20E,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningcontext.cpp",
          (const char *)(unsigned int)v17,
          (int)"Failed to create writer for file %ws.",
          v9);
        if ( v28 >= 8 )
          operator delete(v27[0]);
        if ( v11 )
          (*(void (__fastcall **)(struct IAppxProvisionFactory *))(*(_QWORD *)v11 + 16LL))(v11);
        if ( v26 )
          (*(void (__fastcall **)(struct IAppxProvisionReader *))(*(_QWORD *)v26 + 16LL))(v26);
        return (unsigned int)v17;
      }
      v18 = v26;
      goto LABEL_45;
    }
    v19 = *(__int64 (__fastcall **)(struct IAppxProvisionFactory *, struct IAppxProvisionReader *, char *, struct IAppxProvisionWriter **))(v13 + 40);
    v20 = *v4;
    *v4 = 0;
    if ( v20 )
      (*(void (__fastcall **)(struct IAppxProvisionWriter *))(*(_QWORD *)v20 + 16LL))(v20);
    if ( *((_QWORD *)v9 + 3) < 8u )
      v21 = v9;
    else
      v21 = *(char **)v9;
    v18 = v26;
    v22 = v19(v11, v26, v21, v4);
    if ( v22 >= 0 )
    {
LABEL_45:
      if ( v28 >= 8 )
        operator delete(v27[0]);
      if ( v11 )
        (*(void (__fastcall **)(struct IAppxProvisionFactory *))(*(_QWORD *)v11 + 16LL))(v11);
      if ( v18 )
        (*(void (__fastcall **)(struct IAppxProvisionReader *))(*(_QWORD *)v18 + 16LL))(v18);
      goto LABEL_51;
    }
    if ( *((_QWORD *)v9 + 3) >= 8u )
      v9 = *(char **)v9;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x219,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningcontext.cpp",
      (const char *)(unsigned int)v22,
      (int)"Failed to create writer for file %ws.",
      v9);
    if ( v28 >= 8 )
      operator delete(v27[0]);
    if ( v11 )
      (*(void (__fastcall **)(struct IAppxProvisionFactory *))(*(_QWORD *)v11 + 16LL))(v11);
    if ( v18 )
      (*(void (__fastcall **)(struct IAppxProvisionReader *))(*(_QWORD *)v18 + 16LL))(v18);
    result = (unsigned int)v22;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x222,
                           (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningcontext.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x180041e7c  mov     r11, rsp
0x180041e7f  mov     [r11+18h], rbx
0x180041e83  mov     [r11+20h], rsi
0x180041e87  push    rdi
0x180041e88  push    r12
0x180041e8a  push    r13
0x180041e8c  push    r14
0x180041e8e  push    r15
0x180041e90  sub     rsp, 70h
0x180041e94  mov     rax, cs:__security_cookie
0x180041e9b  xor     rax, rsp
0x180041e9e  mov     [rsp+98h+var_38], rax
0x180041ea3  mov     r12, rdx
0x180041ea6  mov     rbx, rcx
0x180041ea9  xor     r13d, r13d
0x180041eac  mov     [rdx], r13
0x180041eaf  lea     r14, [rcx+2D8h]
0x180041eb6  cmp     [r14], r13
0x180041eb9  jnz     loc_1800421F9
0x180041ebf  mov     [r11-60h], r13
0x180041ec3  mov     [r11-68h], r13
0x180041ec7  lea     rdx, [r11-68h]; struct IAppxProvisionFactory **
0x180041ecb  call    ?GetProvisionFactory@MsixProvisioningContext@Library@Provisioning@MsixPackage@@AEAAJPEAPEAUIAppxProvisionFactory@@@Z; MsixPackage::Provisioning::Library::MsixProvisioningContext::GetProvisionFactory(IAppxProvisionFactory * *)
0x180041ed0  mov     edi, eax
0x180041ed2  test    eax, eax
0x180041ed4  jns     short loc_180041F1D
0x180041ed6  mov     rcx, [rsp+98h]; this
0x180041ede  lea     rax, aFailedToObtain_8; "Failed to obtain provisioning factory."
0x180041ee5  mov     qword ptr [rsp+98h+var_78], rax; int
0x180041eea  mov     r9d, edi; char *
0x180041eed  lea     r8, aOnecoreAdminAp_5; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180041ef4  mov     edx, 1FCh; void *
0x180041ef9  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180041efe  nop
0x180041eff  mov     rcx, [rsp+98h+var_68]
0x180041f04  test    rcx, rcx
0x180041f07  jz      short loc_180041F16
0x180041f09  mov     rax, [rcx]
0x180041f0c  mov     rax, [rax+10h]
0x180041f10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041f15  nop
0x180041f16  mov     eax, edi
0x180041f18  jmp     loc_180042214
0x180041f1d  mov     [rsp+98h+var_40], 7
0x180041f26  mov     [rsp+98h+var_48], r13
0x180041f2b  mov     word ptr [rsp+98h+var_58], r13w
0x180041f31  lea     rdx, [rsp+98h+var_58]
0x180041f36  mov     rcx, rbx
0x180041f39  call    ?GetTemporaryPath@MsixProvisioningContext@Library@Provisioning@MsixPackage@@QEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MsixPackage::Provisioning::Library::MsixProvisioningContext::GetTemporaryPath(std::wstring &)
0x180041f3e  mov     edi, eax
0x180041f40  test    eax, eax
0x180041f42  jns     short loc_180041FA5
0x180041f44  mov     rcx, [rsp+98h]; this
0x180041f4c  lea     rax, aFailedToCreate_13; "Failed to create temp directory."
0x180041f53  mov     qword ptr [rsp+98h+var_78], rax; int
0x180041f58  mov     r9d, edi; char *
0x180041f5b  lea     r8, aOnecoreAdminAp_5; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180041f62  mov     edx, 200h; void *
0x180041f67  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180041f6c  nop
0x180041f6d  cmp     [rsp+98h+var_40], 8
0x180041f73  jb      short loc_180041F87
0x180041f75  mov     rcx, [rsp+98h+var_58]
0x180041f7a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180041f81  nop     dword ptr [rax+rax+00h]
0x180041f86  nop
0x180041f87  mov     rcx, [rsp+98h+var_68]
0x180041f8c  test    rcx, rcx
0x180041f8f  jz      short loc_180041F9E
0x180041f91  mov     rax, [rcx]
0x180041f94  mov     rax, [rax+10h]
0x180041f98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041f9d  nop
0x180041f9e  mov     eax, edi
0x180041fa0  jmp     loc_180042214
0x180041fa5  lea     rsi, [rbx+2B0h]
0x180041fac  or      r9, 0FFFFFFFFFFFFFFFFh
0x180041fb0  xor     r8d, r8d
0x180041fb3  lea     rdx, [rsp+98h+var_58]
0x180041fb8  mov     rcx, rsi; void *
0x180041fbb  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180041fc0  mov     r8, r13
0x180041fc3  cmp     word ptr cs:pszSrc, r13w; "\\"
0x180041fcb  setnz   r8b
0x180041fcf  lea     rdx, pszSrc; "\\"
0x180041fd6  mov     rcx, rsi; Src
0x180041fd9  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180041fde  mov     r8d, 14h
0x180041fe4  lea     rdx, aAppxprovisioni; "AppxProvisioning.xml"
0x180041feb  mov     rcx, rsi; Src
0x180041fee  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180041ff3  nop
0x180041ff4  mov     [rsp+98h+var_60], r13
0x180041ff9  lea     rdx, [rsp+98h+var_60]; struct IAppxProvisionReader **
0x180041ffe  mov     rcx, rbx; this
0x180042001  call    ?GetProvisionReader@MsixProvisioningContext@Library@Provisioning@MsixPackage@@AEAAJPEAPEAUIAppxProvisionReader@@@Z; MsixPackage::Provisioning::Library::MsixProvisioningContext::GetProvisionReader(IAppxProvisionReader * *)
0x180042006  mov     rbx, [rsp+98h+var_68]
0x18004200b  test    eax, eax
0x18004200d  mov     rax, [rbx]
0x180042010  jns     loc_1800420E8
0x180042016  mov     rdi, [rax+20h]
0x18004201a  mov     rcx, [r14]
0x18004201d  mov     [r14], r13
0x180042020  test    rcx, rcx
0x180042023  jz      short loc_180042032
0x180042025  mov     rax, [rcx]
0x180042028  mov     rax, [rax+10h]
0x18004202c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042031  nop
0x180042032  cmp     qword ptr [rsi+18h], 8
0x180042037  jb      short loc_18004203E
0x180042039  mov     rdx, [rsi]
0x18004203c  jmp     short loc_180042041
0x18004203e  mov     rdx, rsi
0x180042041  mov     r8, r14
0x180042044  mov     rcx, rbx
0x180042047  mov     rax, rdi
0x18004204a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004204f  mov     edi, eax
0x180042051  test    eax, eax
0x180042053  jns     loc_1800420DE
0x180042059  cmp     qword ptr [rsi+18h], 8
0x18004205e  jb      short loc_180042063
0x180042060  mov     rsi, [rsi]
0x180042063  mov     rcx, [rsp+98h]; this
0x18004206b  mov     [rsp+98h+var_70], rsi; char *
0x180042070  lea     rax, aFailedToCreate_31; "Failed to create writer for file %ws."
0x180042077  mov     qword ptr [rsp+98h+var_78], rax; int
0x18004207c  mov     r9d, edi; char *
0x18004207f  lea     r8, aOnecoreAdminAp_5; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180042086  mov     edx, 20Eh; void *
0x18004208b  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180042090  nop
0x180042091  cmp     [rsp+98h+var_40], 8
0x180042097  jb      short loc_1800420AB
0x180042099  mov     rcx, [rsp+98h+var_58]
0x18004209e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800420a5  nop     dword ptr [rax+rax+00h]
0x1800420aa  nop
0x1800420ab  test    rbx, rbx
0x1800420ae  jz      short loc_1800420C0
0x1800420b0  mov     rax, [rbx]
0x1800420b3  mov     rcx, rbx
0x1800420b6  mov     rax, [rax+10h]
0x1800420ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800420bf  nop
0x1800420c0  mov     rcx, [rsp+98h+var_60]
0x1800420c5  test    rcx, rcx
0x1800420c8  jz      short loc_1800420D7
0x1800420ca  mov     rax, [rcx]
0x1800420cd  mov     rax, [rax+10h]
0x1800420d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800420d6  nop
0x1800420d7  mov     eax, edi
0x1800420d9  jmp     loc_180042214
0x1800420de  mov     rdi, [rsp+98h+var_60]
0x1800420e3  jmp     loc_1800421B5
0x1800420e8  mov     r15, [rax+28h]
0x1800420ec  mov     rcx, [r14]
0x1800420ef  mov     [r14], r13
0x1800420f2  test    rcx, rcx
0x1800420f5  jz      short loc_180042104
0x1800420f7  mov     rax, [rcx]
0x1800420fa  mov     rax, [rax+10h]
0x1800420fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042103  nop
0x180042104  cmp     qword ptr [rsi+18h], 8
0x180042109  jb      short loc_180042110
0x18004210b  mov     r8, [rsi]
0x18004210e  jmp     short loc_180042113
0x180042110  mov     r8, rsi
0x180042113  mov     r9, r14
0x180042116  mov     rdi, [rsp+98h+var_60]
0x18004211b  mov     rdx, rdi
0x18004211e  mov     rcx, rbx
0x180042121  mov     rax, r15
0x180042124  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042129  mov     r15d, eax
0x18004212c  test    eax, eax
0x18004212e  jns     loc_1800421B5
0x180042134  cmp     qword ptr [rsi+18h], 8
0x180042139  jb      short loc_18004213E
0x18004213b  mov     rsi, [rsi]
0x18004213e  mov     rcx, [rsp+98h]; this
0x180042146  mov     [rsp+98h+var_70], rsi; char *
0x18004214b  lea     rax, aFailedToCreate_31; "Failed to create writer for file %ws."
0x180042152  mov     qword ptr [rsp+98h+var_78], rax; int
0x180042157  mov     r9d, r15d; char *
0x18004215a  lea     r8, aOnecoreAdminAp_5; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180042161  mov     edx, 219h; void *
0x180042166  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004216b  nop
0x18004216c  cmp     [rsp+98h+var_40], 8
0x180042172  jb      short loc_180042186
0x180042174  mov     rcx, [rsp+98h+var_58]
0x180042179  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180042180  nop     dword ptr [rax+rax+00h]
0x180042185  nop
0x180042186  test    rbx, rbx
0x180042189  jz      short loc_18004219B
0x18004218b  mov     rax, [rbx]
0x18004218e  mov     rcx, rbx
0x180042191  mov     rax, [rax+10h]
0x180042195  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004219a  nop
0x18004219b  test    rdi, rdi
0x18004219e  jz      short loc_1800421B0
0x1800421a0  mov     rax, [rdi]
0x1800421a3  mov     rcx, rdi
0x1800421a6  mov     rax, [rax+10h]
0x1800421aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800421af  nop
0x1800421b0  mov     eax, r15d
0x1800421b3  jmp     short loc_180042214
0x1800421b5  cmp     [rsp+98h+var_40], 8
0x1800421bb  jb      short loc_1800421CF
0x1800421bd  mov     rcx, [rsp+98h+var_58]
0x1800421c2  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800421c9  nop     dword ptr [rax+rax+00h]
0x1800421ce  nop
0x1800421cf  test    rbx, rbx
0x1800421d2  jz      short loc_1800421E4
0x1800421d4  mov     rax, [rbx]
0x1800421d7  mov     rcx, rbx
0x1800421da  mov     rax, [rax+10h]
0x1800421de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800421e3  nop
0x1800421e4  test    rdi, rdi
0x1800421e7  jz      short loc_1800421F9
0x1800421e9  mov     rax, [rdi]
0x1800421ec  mov     rcx, rdi
0x1800421ef  mov     rax, [rax+10h]
0x1800421f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800421f8  nop
0x1800421f9  mov     rcx, [r14]
0x1800421fc  mov     [r12], rcx
0x180042200  mov     rax, [rcx]
0x180042203  mov     rax, [rax+8]
0x180042207  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004220c  xor     eax, eax
0x18004220e  jmp     short loc_180042214
0x180042210  mov     eax, dword ptr [rsp+98h+var_68]
0x180042214  mov     rcx, [rsp+98h+var_38]
0x180042219  xor     rcx, rsp; StackCookie
0x18004221c  call    __security_check_cookie
0x180042221  lea     r11, [rsp+98h+var_28]
0x180042226  mov     rbx, [r11+40h]
0x18004222a  mov     rsi, [r11+48h]
0x18004222e  mov     rsp, r11
0x180042231  pop     r15
0x180042233  pop     r14
0x180042235  pop     r13
0x180042237  pop     r12
0x180042239  pop     rdi
0x18004223a  retn
```
