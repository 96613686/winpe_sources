# MsixPackage::Provisioning::Library::MsixProvisioningContext::GetProvisionWriter(IAppxProvisionWriter * *)

- ea: `0x18003e4ec`
- end: `0x18003e88c`
- name: `?GetProvisionWriter@MsixProvisioningContext@Library@Provisioning@MsixPackage@@AEAAJPEAPEAUIAppxProvisionWriter@@@Z`
- size: `928`
- prototype: `__int64 __fastcall(MsixPackage::Provisioning::Library::MsixProvisioningContext *__hidden this, struct IAppxProvisionWriter **)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x18003b8b0`
- `0x18003f3ac`

## callees

- `0x18001bdfc`
- `0x180039e9c`
- `0x18003ae3c`
- `0x18003e098`
- `0x18003e128`
- `0x18003e4ec`
- `0x18003e894`
- `0x180066df0`
- `0x18006a010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18003e5ea`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003e704`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003e7d5`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003e818`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003e5ea`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003e704`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003e7d5`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003e818`

## string_xrefs

- `0x18003e55d`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningcontext.cpp`
- `0x18003e5cb`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningcontext.cpp`
- `0x18003e6e5`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningcontext.cpp`
- `0x18003e7b6`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningcontext.cpp`
- `0x18003e5bc`: `Failed to create temp directory.`
- `0x18003e6d6`: `Failed to create writer for file %ws.`
- `0x18003e7a7`: `Failed to create writer for file %ws.`
- `0x18003e64e`: `AppxProvisioning.xml`

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
    std::wstring::assign((void **)this + 86, v27, 0, 0xFFFFFFFFFFFFFFFFuLL);
    std::wstring::append((_QWORD *)this + 86, (char *)L"\\", pszSrc[0] != 0);
    std::wstring::append((_QWORD *)this + 86, (char *)L"AppxProvisioning.xml", 0x14u);
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
0x18003e4ec  mov     r11, rsp
0x18003e4ef  mov     [r11+18h], rbx
0x18003e4f3  mov     [r11+20h], rsi
0x18003e4f7  push    rdi
0x18003e4f8  push    r12
0x18003e4fa  push    r13
0x18003e4fc  push    r14
0x18003e4fe  push    r15
0x18003e500  sub     rsp, 70h
0x18003e504  mov     rax, cs:__security_cookie
0x18003e50b  xor     rax, rsp
0x18003e50e  mov     [rsp+98h+var_38], rax
0x18003e513  mov     r12, rdx
0x18003e516  mov     rbx, rcx
0x18003e519  xor     r13d, r13d
0x18003e51c  mov     [rdx], r13
0x18003e51f  lea     r14, [rcx+2D8h]
0x18003e526  cmp     [r14], r13
0x18003e529  jnz     loc_18003E849
0x18003e52f  mov     [r11-60h], r13
0x18003e533  mov     [r11-68h], r13
0x18003e537  lea     rdx, [r11-68h]; struct IAppxProvisionFactory **
0x18003e53b  call    ?GetProvisionFactory@MsixProvisioningContext@Library@Provisioning@MsixPackage@@AEAAJPEAPEAUIAppxProvisionFactory@@@Z; MsixPackage::Provisioning::Library::MsixProvisioningContext::GetProvisionFactory(IAppxProvisionFactory * *)
0x18003e540  mov     edi, eax
0x18003e542  test    eax, eax
0x18003e544  jns     short loc_18003E58D
0x18003e546  mov     rcx, [rsp+98h]; this
0x18003e54e  lea     rax, aFailedToObtain_8; "Failed to obtain provisioning factory."
0x18003e555  mov     qword ptr [rsp+98h+var_78], rax; int
0x18003e55a  mov     r9d, edi; char *
0x18003e55d  lea     r8, aOnecoreAdminAp_5; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003e564  mov     edx, 1FCh; void *
0x18003e569  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003e56e  nop
0x18003e56f  mov     rcx, [rsp+98h+var_68]
0x18003e574  test    rcx, rcx
0x18003e577  jz      short loc_18003E586
0x18003e579  mov     rax, [rcx]
0x18003e57c  mov     rax, [rax+10h]
0x18003e580  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e585  nop
0x18003e586  mov     eax, edi
0x18003e588  jmp     loc_18003E864
0x18003e58d  mov     [rsp+98h+var_40], 7
0x18003e596  mov     [rsp+98h+var_48], r13
0x18003e59b  mov     word ptr [rsp+98h+var_58], r13w
0x18003e5a1  lea     rdx, [rsp+98h+var_58]
0x18003e5a6  mov     rcx, rbx
0x18003e5a9  call    ?GetTemporaryPath@MsixProvisioningContext@Library@Provisioning@MsixPackage@@QEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MsixPackage::Provisioning::Library::MsixProvisioningContext::GetTemporaryPath(std::wstring &)
0x18003e5ae  mov     edi, eax
0x18003e5b0  test    eax, eax
0x18003e5b2  jns     short loc_18003E60F
0x18003e5b4  mov     rcx, [rsp+98h]; this
0x18003e5bc  lea     rax, aFailedToCreate_13; "Failed to create temp directory."
0x18003e5c3  mov     qword ptr [rsp+98h+var_78], rax; int
0x18003e5c8  mov     r9d, edi; char *
0x18003e5cb  lea     r8, aOnecoreAdminAp_5; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003e5d2  mov     edx, 200h; void *
0x18003e5d7  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003e5dc  nop
0x18003e5dd  cmp     [rsp+98h+var_40], 8
0x18003e5e3  jb      short loc_18003E5F1
0x18003e5e5  mov     rcx, [rsp+98h+var_58]
0x18003e5ea  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003e5f0  nop
0x18003e5f1  mov     rcx, [rsp+98h+var_68]
0x18003e5f6  test    rcx, rcx
0x18003e5f9  jz      short loc_18003E608
0x18003e5fb  mov     rax, [rcx]
0x18003e5fe  mov     rax, [rax+10h]
0x18003e602  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e607  nop
0x18003e608  mov     eax, edi
0x18003e60a  jmp     loc_18003E864
0x18003e60f  lea     rsi, [rbx+2B0h]
0x18003e616  or      r9, 0FFFFFFFFFFFFFFFFh
0x18003e61a  xor     r8d, r8d
0x18003e61d  lea     rdx, [rsp+98h+var_58]
0x18003e622  mov     rcx, rsi; void *
0x18003e625  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18003e62a  mov     r8, r13
0x18003e62d  cmp     word ptr cs:pszSrc, r13w; "\\"
0x18003e635  setnz   r8b
0x18003e639  lea     rdx, pszSrc; "\\"
0x18003e640  mov     rcx, rsi; Src
0x18003e643  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18003e648  mov     r8d, 14h
0x18003e64e  lea     rdx, aAppxprovisioni; "AppxProvisioning.xml"
0x18003e655  mov     rcx, rsi; Src
0x18003e658  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18003e65d  nop
0x18003e65e  mov     [rsp+98h+var_60], r13
0x18003e663  lea     rdx, [rsp+98h+var_60]; struct IAppxProvisionReader **
0x18003e668  mov     rcx, rbx; this
0x18003e66b  call    ?GetProvisionReader@MsixProvisioningContext@Library@Provisioning@MsixPackage@@AEAAJPEAPEAUIAppxProvisionReader@@@Z; MsixPackage::Provisioning::Library::MsixProvisioningContext::GetProvisionReader(IAppxProvisionReader * *)
0x18003e670  mov     rbx, [rsp+98h+var_68]
0x18003e675  test    eax, eax
0x18003e677  mov     rax, [rbx]
0x18003e67a  jns     loc_18003E748
0x18003e680  mov     rdi, [rax+20h]
0x18003e684  mov     rcx, [r14]
0x18003e687  mov     [r14], r13
0x18003e68a  test    rcx, rcx
0x18003e68d  jz      short loc_18003E69C
0x18003e68f  mov     rax, [rcx]
0x18003e692  mov     rax, [rax+10h]
0x18003e696  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e69b  nop
0x18003e69c  cmp     qword ptr [rsi+18h], 8
0x18003e6a1  jb      short loc_18003E6A8
0x18003e6a3  mov     rdx, [rsi]
0x18003e6a6  jmp     short loc_18003E6AB
0x18003e6a8  mov     rdx, rsi
0x18003e6ab  mov     r8, r14
0x18003e6ae  mov     rcx, rbx
0x18003e6b1  mov     rax, rdi
0x18003e6b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e6b9  mov     edi, eax
0x18003e6bb  test    eax, eax
0x18003e6bd  jns     short loc_18003E73E
0x18003e6bf  cmp     qword ptr [rsi+18h], 8
0x18003e6c4  jb      short loc_18003E6C9
0x18003e6c6  mov     rsi, [rsi]
0x18003e6c9  mov     rcx, [rsp+98h]; this
0x18003e6d1  mov     [rsp+98h+var_70], rsi; char *
0x18003e6d6  lea     rax, aFailedToCreate_31; "Failed to create writer for file %ws."
0x18003e6dd  mov     qword ptr [rsp+98h+var_78], rax; int
0x18003e6e2  mov     r9d, edi; char *
0x18003e6e5  lea     r8, aOnecoreAdminAp_5; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003e6ec  mov     edx, 20Eh; void *
0x18003e6f1  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003e6f6  nop
0x18003e6f7  cmp     [rsp+98h+var_40], 8
0x18003e6fd  jb      short loc_18003E70B
0x18003e6ff  mov     rcx, [rsp+98h+var_58]
0x18003e704  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003e70a  nop
0x18003e70b  test    rbx, rbx
0x18003e70e  jz      short loc_18003E720
0x18003e710  mov     rax, [rbx]
0x18003e713  mov     rcx, rbx
0x18003e716  mov     rax, [rax+10h]
0x18003e71a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e71f  nop
0x18003e720  mov     rcx, [rsp+98h+var_60]
0x18003e725  test    rcx, rcx
0x18003e728  jz      short loc_18003E737
0x18003e72a  mov     rax, [rcx]
0x18003e72d  mov     rax, [rax+10h]
0x18003e731  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e736  nop
0x18003e737  mov     eax, edi
0x18003e739  jmp     loc_18003E864
0x18003e73e  mov     rdi, [rsp+98h+var_60]
0x18003e743  jmp     loc_18003E80B
0x18003e748  mov     r15, [rax+28h]
0x18003e74c  mov     rcx, [r14]
0x18003e74f  mov     [r14], r13
0x18003e752  test    rcx, rcx
0x18003e755  jz      short loc_18003E764
0x18003e757  mov     rax, [rcx]
0x18003e75a  mov     rax, [rax+10h]
0x18003e75e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e763  nop
0x18003e764  cmp     qword ptr [rsi+18h], 8
0x18003e769  jb      short loc_18003E770
0x18003e76b  mov     r8, [rsi]
0x18003e76e  jmp     short loc_18003E773
0x18003e770  mov     r8, rsi
0x18003e773  mov     r9, r14
0x18003e776  mov     rdi, [rsp+98h+var_60]
0x18003e77b  mov     rdx, rdi
0x18003e77e  mov     rcx, rbx
0x18003e781  mov     rax, r15
0x18003e784  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e789  mov     r15d, eax
0x18003e78c  test    eax, eax
0x18003e78e  jns     short loc_18003E80B
0x18003e790  cmp     qword ptr [rsi+18h], 8
0x18003e795  jb      short loc_18003E79A
0x18003e797  mov     rsi, [rsi]
0x18003e79a  mov     rcx, [rsp+98h]; this
0x18003e7a2  mov     [rsp+98h+var_70], rsi; char *
0x18003e7a7  lea     rax, aFailedToCreate_31; "Failed to create writer for file %ws."
0x18003e7ae  mov     qword ptr [rsp+98h+var_78], rax; int
0x18003e7b3  mov     r9d, r15d; char *
0x18003e7b6  lea     r8, aOnecoreAdminAp_5; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003e7bd  mov     edx, 219h; void *
0x18003e7c2  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003e7c7  nop
0x18003e7c8  cmp     [rsp+98h+var_40], 8
0x18003e7ce  jb      short loc_18003E7DC
0x18003e7d0  mov     rcx, [rsp+98h+var_58]
0x18003e7d5  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003e7db  nop
0x18003e7dc  test    rbx, rbx
0x18003e7df  jz      short loc_18003E7F1
0x18003e7e1  mov     rax, [rbx]
0x18003e7e4  mov     rcx, rbx
0x18003e7e7  mov     rax, [rax+10h]
0x18003e7eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e7f0  nop
0x18003e7f1  test    rdi, rdi
0x18003e7f4  jz      short loc_18003E806
0x18003e7f6  mov     rax, [rdi]
0x18003e7f9  mov     rcx, rdi
0x18003e7fc  mov     rax, [rax+10h]
0x18003e800  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e805  nop
0x18003e806  mov     eax, r15d
0x18003e809  jmp     short loc_18003E864
0x18003e80b  cmp     [rsp+98h+var_40], 8
0x18003e811  jb      short loc_18003E81F
0x18003e813  mov     rcx, [rsp+98h+var_58]
0x18003e818  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003e81e  nop
0x18003e81f  test    rbx, rbx
0x18003e822  jz      short loc_18003E834
0x18003e824  mov     rax, [rbx]
0x18003e827  mov     rcx, rbx
0x18003e82a  mov     rax, [rax+10h]
0x18003e82e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e833  nop
0x18003e834  test    rdi, rdi
0x18003e837  jz      short loc_18003E849
0x18003e839  mov     rax, [rdi]
0x18003e83c  mov     rcx, rdi
0x18003e83f  mov     rax, [rax+10h]
0x18003e843  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e848  nop
0x18003e849  mov     rcx, [r14]
0x18003e84c  mov     [r12], rcx
0x18003e850  mov     rax, [rcx]
0x18003e853  mov     rax, [rax+8]
0x18003e857  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e85c  xor     eax, eax
0x18003e85e  jmp     short loc_18003E864
0x18003e860  mov     eax, dword ptr [rsp+98h+var_68]
0x18003e864  mov     rcx, [rsp+98h+var_38]
0x18003e869  xor     rcx, rsp; StackCookie
0x18003e86c  call    __security_check_cookie
0x18003e871  lea     r11, [rsp+98h+var_28]
0x18003e876  mov     rbx, [r11+40h]
0x18003e87a  mov     rsi, [r11+48h]
0x18003e87e  mov     rsp, r11
0x18003e881  pop     r15
0x18003e883  pop     r14
0x18003e885  pop     r13
0x18003e887  pop     r12
0x18003e889  pop     rdi
0x18003e88a  retn
```
