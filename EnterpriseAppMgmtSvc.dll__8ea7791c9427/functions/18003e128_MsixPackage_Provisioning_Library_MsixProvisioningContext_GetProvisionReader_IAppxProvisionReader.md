# MsixPackage::Provisioning::Library::MsixProvisioningContext::GetProvisionReader(IAppxProvisionReader * *)

- ea: `0x18003e128`
- end: `0x18003e4e6`
- name: `?GetProvisionReader@MsixProvisioningContext@Library@Provisioning@MsixPackage@@AEAAJPEAPEAUIAppxProvisionReader@@@Z`
- size: `958`
- prototype: `__int64 __fastcall(MsixPackage::Provisioning::Library::MsixProvisioningContext *__hidden this, struct IAppxProvisionReader **)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x18003e4ec`

## callees

- `0x18001bf0c`
- `0x180039e9c`
- `0x18003ae3c`
- `0x18003bf94`
- `0x18003e098`
- `0x18003e128`
- `0x18005ee08`
- `0x180066df0`
- `0x18006a010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18003e376`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003e442`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003e47e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003e376`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003e442`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003e47e`

## string_xrefs

- `0x18003e17f`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningcontext.cpp`
- `0x18003e1d6`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningcontext.cpp`
- `0x18003e423`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningcontext.cpp`
- `0x18003e414`: `Failed to read %ws from the image.`
- `0x18003e307`: `System32`
- `0x18003e26f`: `AppxProvisioning.xml`
- `0x18003e33e`: `AppxProvisioning.xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall MsixPackage::Provisioning::Library::MsixProvisioningContext::GetProvisionReader(
        char **this,
        struct IAppxProvisionReader **a2)
{
  int v4; // edi
  struct IAppxProvisionReader **v6; // rsi
  int ProvisionFactory; // edi
  char *v8; // rdx
  unsigned __int64 v9; // rdi
  unsigned __int64 v10; // r8
  void **v11; // rcx
  void **v12; // rcx
  char *v13; // rdx
  void **v14; // rcx
  struct IAppxProvisionFactory *v15; // rbx
  __int64 (__fastcall *v16)(struct IAppxProvisionFactory *, void **, struct IAppxProvisionReader **); // rdi
  struct IAppxProvisionReader *v17; // rcx
  void **v18; // rdx
  int v19; // edi
  const char *v20; // rdx
  struct IAppxProvisionReader *v21; // rcx
  char *v22; // [rsp+28h] [rbp-60h]
  struct IAppxProvisionFactory *v23; // [rsp+30h] [rbp-58h] BYREF
  void *Src[2]; // [rsp+38h] [rbp-50h] BYREF
  __int64 v25; // [rsp+48h] [rbp-40h]
  unsigned __int64 v26; // [rsp+50h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  *a2 = 0;
  if ( this[91] )
  {
    v4 = MsixPackage::Provisioning::Library::MsixProvisioningContext::FinalizeChanges((MsixPackage::Provisioning::Library::MsixProvisioningContext *)this);
    if ( v4 < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x229,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningcontext.cpp",
        (const char *)(unsigned int)v4,
        (int)"Failed to flush pending changes.",
        v22);
      return (unsigned int)v4;
    }
  }
  v6 = (struct IAppxProvisionReader **)(this + 90);
  if ( this[90] )
    goto LABEL_46;
  v23 = 0;
  ProvisionFactory = MsixPackage::Provisioning::Library::MsixProvisioningContext::GetProvisionFactory(
                       (MsixPackage::Provisioning::Library::MsixProvisioningContext *)this,
                       &v23);
  if ( ProvisionFactory < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x230,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningcontext.cpp",
      (const char *)(unsigned int)ProvisionFactory,
      (int)"Failed to obtain provisioning factory.",
      v22);
    if ( v23 )
      (*(void (__fastcall **)(struct IAppxProvisionFactory *))(*(_QWORD *)v23 + 16LL))(v23);
    return (unsigned int)ProvisionFactory;
  }
  v26 = 7;
  v25 = 0;
  LOWORD(Src[0]) = 0;
  v8 = this[72];
  v9 = -1;
  if ( *(_WORD *)v8 )
  {
    v10 = -1;
    do
      ++v10;
    while ( *(_WORD *)&v8[2 * v10] );
  }
  else
  {
    v10 = 0;
  }
  std::wstring::assign(Src, v8, v10);
  std::wstring::append(Src, (char *)L"\\", pszSrc[0] != 0);
  std::wstring::append(Src, (char *)L"AppxProvisioning.xml", 0x14u);
  v11 = Src;
  if ( v26 >= 8 )
    v11 = (void **)Src[0];
  if ( !(unsigned int)FileExists(v11) )
  {
    v12 = Src;
    if ( v26 >= 8 )
      v12 = (void **)Src[0];
    v25 = 0;
    *(_WORD *)v12 = 0;
    v13 = this[71];
    if ( *(_WORD *)v13 )
    {
      do
        ++v9;
      while ( *(_WORD *)&v13[2 * v9] );
    }
    else
    {
      v9 = 0;
    }
    std::wstring::assign(Src, v13, v9);
    std::wstring::append(Src, (char *)L"\\", pszSrc[0] != 0);
    std::wstring::append(Src, (char *)L"System32", 8u);
    std::wstring::append(Src, (char *)L"\\", pszSrc[0] != 0);
    std::wstring::append(Src, (char *)L"AppxProvisioning.xml", 0x14u);
  }
  v14 = Src;
  if ( v26 >= 8 )
    v14 = (void **)Src[0];
  if ( !(unsigned int)FileExists(v14) )
  {
    if ( v26 >= 8 )
      operator delete(Src[0]);
    v26 = 7;
    v25 = 0;
    LOWORD(Src[0]) = 0;
    if ( v23 )
      (*(void (__fastcall **)(struct IAppxProvisionFactory *))(*(_QWORD *)v23 + 16LL))(v23);
    return 2;
  }
  v15 = v23;
  v16 = *(__int64 (__fastcall **)(struct IAppxProvisionFactory *, void **, struct IAppxProvisionReader **))(*(_QWORD *)v23 + 24LL);
  v17 = *v6;
  *v6 = 0;
  if ( v17 )
    (*(void (__fastcall **)(struct IAppxProvisionReader *))(*(_QWORD *)v17 + 16LL))(v17);
  v18 = Src;
  if ( v26 >= 8 )
    v18 = (void **)Src[0];
  v19 = v16(v15, v18, v6);
  if ( v19 >= 0 )
  {
    if ( v26 >= 8 )
      operator delete(Src[0]);
    v26 = 7;
    v25 = 0;
    LOWORD(Src[0]) = 0;
    if ( v15 )
      (*(void (__fastcall **)(struct IAppxProvisionFactory *))(*(_QWORD *)v15 + 16LL))(v15);
LABEL_46:
    v21 = *v6;
    *a2 = *v6;
    (*(void (__fastcall **)(struct IAppxProvisionReader *))(*(_QWORD *)v21 + 8LL))(v21);
    return 0;
  }
  v20 = (const char *)Src;
  if ( v26 >= 8 )
    v20 = (const char *)Src[0];
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    (void *)0x252,
    (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningcontext.cpp",
    (const char *)(unsigned int)v19,
    (int)"Failed to read %ws from the image.",
    v20);
  if ( v26 >= 8 )
    operator delete(Src[0]);
  v26 = 7;
  v25 = 0;
  LOWORD(Src[0]) = 0;
  if ( v15 )
    (*(void (__fastcall **)(struct IAppxProvisionFactory *))(*(_QWORD *)v15 + 16LL))(v15);
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x18003e128  mov     [rsp+arg_10], rbx
0x18003e12d  push    rsi
0x18003e12e  push    rdi
0x18003e12f  push    r13
0x18003e131  push    r14
0x18003e133  push    r15
0x18003e135  sub     rsp, 60h
0x18003e139  mov     rax, cs:__security_cookie
0x18003e140  xor     rax, rsp
0x18003e143  mov     [rsp+88h+var_30], rax
0x18003e148  mov     r14, rdx
0x18003e14b  mov     rbx, rcx
0x18003e14e  xor     r15d, r15d
0x18003e151  mov     [rdx], r15
0x18003e154  cmp     [rcx+2D8h], r15
0x18003e15b  jz      short loc_18003E197
0x18003e15d  call    ?FinalizeChanges@MsixProvisioningContext@Library@Provisioning@MsixPackage@@QEAAJXZ; MsixPackage::Provisioning::Library::MsixProvisioningContext::FinalizeChanges(void)
0x18003e162  mov     edi, eax
0x18003e164  test    eax, eax
0x18003e166  jns     short loc_18003E197
0x18003e168  mov     rcx, [rsp+88h]; this
0x18003e170  lea     rax, aFailedToFlushP; "Failed to flush pending changes."
0x18003e177  mov     qword ptr [rsp+88h+var_68], rax; int
0x18003e17c  mov     r9d, edi; char *
0x18003e17f  lea     r8, aOnecoreAdminAp_5; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003e186  mov     edx, 229h; void *
0x18003e18b  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003e190  mov     eax, edi
0x18003e192  jmp     loc_18003E4C3
0x18003e197  lea     rsi, [rbx+2D0h]
0x18003e19e  cmp     [rsi], r15
0x18003e1a1  jnz     loc_18003E4A9
0x18003e1a7  mov     [rsp+88h+var_58], r15
0x18003e1ac  lea     rdx, [rsp+88h+var_58]; struct IAppxProvisionFactory **
0x18003e1b1  mov     rcx, rbx; this
0x18003e1b4  call    ?GetProvisionFactory@MsixProvisioningContext@Library@Provisioning@MsixPackage@@AEAAJPEAPEAUIAppxProvisionFactory@@@Z; MsixPackage::Provisioning::Library::MsixProvisioningContext::GetProvisionFactory(IAppxProvisionFactory * *)
0x18003e1b9  mov     edi, eax
0x18003e1bb  test    eax, eax
0x18003e1bd  jns     short loc_18003E206
0x18003e1bf  mov     rcx, [rsp+88h]; this
0x18003e1c7  lea     rax, aFailedToObtain_8; "Failed to obtain provisioning factory."
0x18003e1ce  mov     qword ptr [rsp+88h+var_68], rax; int
0x18003e1d3  mov     r9d, edi; char *
0x18003e1d6  lea     r8, aOnecoreAdminAp_5; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003e1dd  mov     edx, 230h; void *
0x18003e1e2  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003e1e7  nop
0x18003e1e8  mov     rcx, [rsp+88h+var_58]
0x18003e1ed  test    rcx, rcx
0x18003e1f0  jz      short loc_18003E1FF
0x18003e1f2  mov     rax, [rcx]
0x18003e1f5  mov     rax, [rax+10h]
0x18003e1f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e1fe  nop
0x18003e1ff  mov     eax, edi
0x18003e201  jmp     loc_18003E4C3
0x18003e206  mov     r13d, 7
0x18003e20c  mov     [rsp+88h+var_38], r13
0x18003e211  mov     [rsp+88h+var_40], r15
0x18003e216  mov     word ptr [rsp+88h+Src], r15w
0x18003e21c  mov     rdx, [rbx+240h]; Src
0x18003e223  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18003e227  cmp     [rdx], r15w
0x18003e22b  jnz     short loc_18003E232
0x18003e22d  mov     r8, r15
0x18003e230  jmp     short loc_18003E23F
0x18003e232  mov     r8, rdi
0x18003e235  inc     r8
0x18003e238  cmp     [rdx+r8*2], r15w
0x18003e23d  jnz     short loc_18003E235
0x18003e23f  lea     rcx, [rsp+88h+Src]; void *
0x18003e244  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18003e249  mov     r8, r15
0x18003e24c  cmp     word ptr cs:pszSrc, r15w; "\\"
0x18003e254  setnz   r8b
0x18003e258  lea     rdx, pszSrc; "\\"
0x18003e25f  lea     rcx, [rsp+88h+Src]; Src
0x18003e264  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18003e269  mov     r8d, 14h
0x18003e26f  lea     rdx, aAppxprovisioni; "AppxProvisioning.xml"
0x18003e276  lea     rcx, [rsp+88h+Src]; Src
0x18003e27b  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18003e280  lea     rcx, [rsp+88h+Src]
0x18003e285  cmp     [rsp+88h+var_38], 8
0x18003e28b  cmovnb  rcx, [rsp+88h+Src]
0x18003e291  call    FileExists
0x18003e296  test    eax, eax
0x18003e298  jnz     loc_18003E34F
0x18003e29e  lea     rcx, [rsp+88h+Src]
0x18003e2a3  cmp     [rsp+88h+var_38], 8
0x18003e2a9  cmovnb  rcx, [rsp+88h+Src]
0x18003e2af  mov     [rsp+88h+var_40], r15
0x18003e2b4  mov     [rcx], r15w
0x18003e2b8  mov     rdx, [rbx+238h]; Src
0x18003e2bf  cmp     [rdx], r15w
0x18003e2c3  jnz     short loc_18003E2CA
0x18003e2c5  mov     rdi, r15
0x18003e2c8  jmp     short loc_18003E2D4
0x18003e2ca  inc     rdi
0x18003e2cd  cmp     [rdx+rdi*2], r15w
0x18003e2d2  jnz     short loc_18003E2CA
0x18003e2d4  mov     r8, rdi
0x18003e2d7  lea     rcx, [rsp+88h+Src]; void *
0x18003e2dc  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18003e2e1  mov     r8, r15
0x18003e2e4  cmp     word ptr cs:pszSrc, r15w; "\\"
0x18003e2ec  setnz   r8b
0x18003e2f0  lea     rdx, pszSrc; "\\"
0x18003e2f7  lea     rcx, [rsp+88h+Src]; Src
0x18003e2fc  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18003e301  mov     r8d, 8
0x18003e307  lea     rdx, aSystem32; "System32"
0x18003e30e  lea     rcx, [rsp+88h+Src]; Src
0x18003e313  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18003e318  mov     r8, r15
0x18003e31b  cmp     word ptr cs:pszSrc, r15w; "\\"
0x18003e323  setnz   r8b
0x18003e327  lea     rdx, pszSrc; "\\"
0x18003e32e  lea     rcx, [rsp+88h+Src]; Src
0x18003e333  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18003e338  mov     r8d, 14h
0x18003e33e  lea     rdx, aAppxprovisioni; "AppxProvisioning.xml"
0x18003e345  lea     rcx, [rsp+88h+Src]; Src
0x18003e34a  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18003e34f  lea     rcx, [rsp+88h+Src]
0x18003e354  cmp     [rsp+88h+var_38], 8
0x18003e35a  cmovnb  rcx, [rsp+88h+Src]
0x18003e360  call    FileExists
0x18003e365  test    eax, eax
0x18003e367  jnz     short loc_18003E3AD
0x18003e369  cmp     [rsp+88h+var_38], 8
0x18003e36f  jb      short loc_18003E37C
0x18003e371  mov     rcx, [rsp+88h+Src]
0x18003e376  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003e37c  mov     [rsp+88h+var_38], r13
0x18003e381  mov     [rsp+88h+var_40], r15
0x18003e386  mov     word ptr [rsp+88h+Src], r15w
0x18003e38c  mov     rcx, [rsp+88h+var_58]
0x18003e391  test    rcx, rcx
0x18003e394  jz      short loc_18003E3A3
0x18003e396  mov     rax, [rcx]
0x18003e399  mov     rax, [rax+10h]
0x18003e39d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e3a2  nop
0x18003e3a3  mov     eax, 2
0x18003e3a8  jmp     loc_18003E4C3
0x18003e3ad  mov     rbx, [rsp+88h+var_58]
0x18003e3b2  mov     rax, [rbx]
0x18003e3b5  mov     rdi, [rax+18h]
0x18003e3b9  mov     rcx, [rsi]
0x18003e3bc  mov     [rsi], r15
0x18003e3bf  test    rcx, rcx
0x18003e3c2  jz      short loc_18003E3D1
0x18003e3c4  mov     rax, [rcx]
0x18003e3c7  mov     rax, [rax+10h]
0x18003e3cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e3d0  nop
0x18003e3d1  lea     rdx, [rsp+88h+Src]
0x18003e3d6  cmp     [rsp+88h+var_38], 8
0x18003e3dc  cmovnb  rdx, [rsp+88h+Src]
0x18003e3e2  mov     r8, rsi
0x18003e3e5  mov     rcx, rbx
0x18003e3e8  mov     rax, rdi
0x18003e3eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e3f0  mov     edi, eax
0x18003e3f2  test    eax, eax
0x18003e3f4  jns     short loc_18003E471
0x18003e3f6  lea     rdx, [rsp+88h+Src]
0x18003e3fb  cmp     [rsp+88h+var_38], 8
0x18003e401  cmovnb  rdx, [rsp+88h+Src]
0x18003e407  mov     rcx, [rsp+88h]; this
0x18003e40f  mov     [rsp+88h+var_60], rdx; char *
0x18003e414  lea     rax, aFailedToReadWs; "Failed to read %ws from the image."
0x18003e41b  mov     qword ptr [rsp+88h+var_68], rax; int
0x18003e420  mov     r9d, edi; char *
0x18003e423  lea     r8, aOnecoreAdminAp_5; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003e42a  mov     edx, 252h; void *
0x18003e42f  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003e434  nop
0x18003e435  cmp     [rsp+88h+var_38], 8
0x18003e43b  jb      short loc_18003E448
0x18003e43d  mov     rcx, [rsp+88h+Src]
0x18003e442  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003e448  mov     [rsp+88h+var_38], r13
0x18003e44d  mov     [rsp+88h+var_40], r15
0x18003e452  mov     word ptr [rsp+88h+Src], r15w
0x18003e458  test    rbx, rbx
0x18003e45b  jz      short loc_18003E46D
0x18003e45d  mov     rax, [rbx]
0x18003e460  mov     rcx, rbx
0x18003e463  mov     rax, [rax+10h]
0x18003e467  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e46c  nop
0x18003e46d  mov     eax, edi
0x18003e46f  jmp     short loc_18003E4C3
0x18003e471  cmp     [rsp+88h+var_38], 8
0x18003e477  jb      short loc_18003E484
0x18003e479  mov     rcx, [rsp+88h+Src]
0x18003e47e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003e484  mov     [rsp+88h+var_38], r13
0x18003e489  mov     [rsp+88h+var_40], r15
0x18003e48e  mov     word ptr [rsp+88h+Src], r15w
0x18003e494  test    rbx, rbx
0x18003e497  jz      short loc_18003E4A9
0x18003e499  mov     rax, [rbx]
0x18003e49c  mov     rcx, rbx
0x18003e49f  mov     rax, [rax+10h]
0x18003e4a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e4a8  nop
0x18003e4a9  mov     rcx, [rsi]
0x18003e4ac  mov     [r14], rcx
0x18003e4af  mov     rax, [rcx]
0x18003e4b2  mov     rax, [rax+8]
0x18003e4b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e4bb  xor     eax, eax
0x18003e4bd  jmp     short loc_18003E4C3
0x18003e4bf  mov     eax, dword ptr [rsp+88h+var_58]
0x18003e4c3  mov     rcx, [rsp+88h+var_30]
0x18003e4c8  xor     rcx, rsp; StackCookie
0x18003e4cb  call    __security_check_cookie
0x18003e4d0  mov     rbx, [rsp+88h+arg_10]
0x18003e4d8  add     rsp, 60h
0x18003e4dc  pop     r15
0x18003e4de  pop     r14
0x18003e4e0  pop     r13
0x18003e4e2  pop     rdi
0x18003e4e3  pop     rsi
0x18003e4e4  retn
```
