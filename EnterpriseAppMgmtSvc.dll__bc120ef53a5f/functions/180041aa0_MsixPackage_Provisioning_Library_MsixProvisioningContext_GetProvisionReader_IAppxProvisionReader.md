# MsixPackage::Provisioning::Library::MsixProvisioningContext::GetProvisionReader(IAppxProvisionReader * *)

- ea: `0x180041aa0`
- end: `0x180041e74`
- name: `?GetProvisionReader@MsixProvisioningContext@Library@Provisioning@MsixPackage@@AEAAJPEAPEAUIAppxProvisionReader@@@Z`
- size: `980`
- prototype: `__int64 __fastcall(MsixPackage::Provisioning::Library::MsixProvisioningContext *__hidden this, struct IAppxProvisionReader **)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180041e7c`

## callees

- `0x18001d160`
- `0x18003d4ec`
- `0x18003e50c`
- `0x18003f6f8`
- `0x180041a08`
- `0x180041aa0`
- `0x180063d1c`
- `0x18006c910`
- `0x180070010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180041cee`
- `msvcrt!??3@YAXPEAX@Z` at `0x180041dc4`
- `msvcrt!??3@YAXPEAX@Z` at `0x180041e06`
- `msvcrt!??3@YAXPEAX@Z` at `0x180041cee`
- `msvcrt!??3@YAXPEAX@Z` at `0x180041dc4`
- `msvcrt!??3@YAXPEAX@Z` at `0x180041e06`

## string_xrefs

- `0x180041af7`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningcontext.cpp`
- `0x180041b4e`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningcontext.cpp`
- `0x180041da5`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningcontext.cpp`
- `0x180041d96`: `Failed to read %ws from the image.`
- `0x180041c7f`: `System32`
- `0x180041be7`: `AppxProvisioning.xml`
- `0x180041cb6`: `AppxProvisioning.xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall MsixPackage::Provisioning::Library::MsixProvisioningContext::GetProvisionReader(
        MsixPackage::Provisioning::Library::MsixProvisioningContext *this,
        struct IAppxProvisionReader **a2)
{
  int v4; // edi
  struct IAppxProvisionReader **v6; // rsi
  int ProvisionFactory; // edi
  _WORD *v8; // rdx
  __int64 v9; // rdi
  __int64 v10; // r8
  void **v11; // rcx
  void **v12; // rcx
  _WORD *v13; // rdx
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
  if ( *((_QWORD *)this + 91) )
  {
    v4 = MsixPackage::Provisioning::Library::MsixProvisioningContext::FinalizeChanges(this);
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
  v6 = (struct IAppxProvisionReader **)((char *)this + 720);
  if ( *((_QWORD *)this + 90) )
    goto LABEL_44;
  v23 = 0;
  ProvisionFactory = MsixPackage::Provisioning::Library::MsixProvisioningContext::GetProvisionFactory(this, &v23);
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
  v8 = (_WORD *)*((_QWORD *)this + 72);
  v9 = -1;
  if ( *v8 )
  {
    v10 = -1;
    do
      ++v10;
    while ( v8[v10] );
  }
  std::wstring::assign(Src, v8);
  std::wstring::append(Src, (void *)L"\\");
  std::wstring::append(Src, L"AppxProvisioning.xml");
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
    v13 = (_WORD *)*((_QWORD *)this + 71);
    if ( *v13 )
    {
      do
        ++v9;
      while ( v13[v9] );
    }
    std::wstring::assign(Src, v13);
    std::wstring::append(Src, (void *)L"\\");
    std::wstring::append(Src, L"System32");
    std::wstring::append(Src, (void *)L"\\");
    std::wstring::append(Src, L"AppxProvisioning.xml");
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
LABEL_44:
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
0x180041aa0  mov     [rsp+arg_10], rbx
0x180041aa5  push    rsi
0x180041aa6  push    rdi
0x180041aa7  push    r13
0x180041aa9  push    r14
0x180041aab  push    r15
0x180041aad  sub     rsp, 60h
0x180041ab1  mov     rax, cs:__security_cookie
0x180041ab8  xor     rax, rsp
0x180041abb  mov     [rsp+88h+var_30], rax
0x180041ac0  mov     r14, rdx
0x180041ac3  mov     rbx, rcx
0x180041ac6  xor     r15d, r15d
0x180041ac9  mov     [rdx], r15
0x180041acc  cmp     [rcx+2D8h], r15
0x180041ad3  jz      short loc_180041B0F
0x180041ad5  call    ?FinalizeChanges@MsixProvisioningContext@Library@Provisioning@MsixPackage@@QEAAJXZ; MsixPackage::Provisioning::Library::MsixProvisioningContext::FinalizeChanges(void)
0x180041ada  mov     edi, eax
0x180041adc  test    eax, eax
0x180041ade  jns     short loc_180041B0F
0x180041ae0  mov     rcx, [rsp+88h]; this
0x180041ae8  lea     rax, aFailedToFlushP; "Failed to flush pending changes."
0x180041aef  mov     qword ptr [rsp+88h+var_68], rax; int
0x180041af4  mov     r9d, edi; char *
0x180041af7  lea     r8, aOnecoreAdminAp_5; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180041afe  mov     edx, 229h; void *
0x180041b03  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180041b08  mov     eax, edi
0x180041b0a  jmp     loc_180041E51
0x180041b0f  lea     rsi, [rbx+2D0h]
0x180041b16  cmp     [rsi], r15
0x180041b19  jnz     loc_180041E37
0x180041b1f  mov     [rsp+88h+var_58], r15
0x180041b24  lea     rdx, [rsp+88h+var_58]; struct IAppxProvisionFactory **
0x180041b29  mov     rcx, rbx; this
0x180041b2c  call    ?GetProvisionFactory@MsixProvisioningContext@Library@Provisioning@MsixPackage@@AEAAJPEAPEAUIAppxProvisionFactory@@@Z; MsixPackage::Provisioning::Library::MsixProvisioningContext::GetProvisionFactory(IAppxProvisionFactory * *)
0x180041b31  mov     edi, eax
0x180041b33  test    eax, eax
0x180041b35  jns     short loc_180041B7E
0x180041b37  mov     rcx, [rsp+88h]; this
0x180041b3f  lea     rax, aFailedToObtain_8; "Failed to obtain provisioning factory."
0x180041b46  mov     qword ptr [rsp+88h+var_68], rax; int
0x180041b4b  mov     r9d, edi; char *
0x180041b4e  lea     r8, aOnecoreAdminAp_5; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180041b55  mov     edx, 230h; void *
0x180041b5a  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180041b5f  nop
0x180041b60  mov     rcx, [rsp+88h+var_58]
0x180041b65  test    rcx, rcx
0x180041b68  jz      short loc_180041B77
0x180041b6a  mov     rax, [rcx]
0x180041b6d  mov     rax, [rax+10h]
0x180041b71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041b76  nop
0x180041b77  mov     eax, edi
0x180041b79  jmp     loc_180041E51
0x180041b7e  mov     r13d, 7
0x180041b84  mov     [rsp+88h+var_38], r13
0x180041b89  mov     [rsp+88h+var_40], r15
0x180041b8e  mov     word ptr [rsp+88h+Src], r15w
0x180041b94  mov     rdx, [rbx+240h]; Src
0x180041b9b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180041b9f  cmp     [rdx], r15w
0x180041ba3  jnz     short loc_180041BAA
0x180041ba5  mov     r8, r15
0x180041ba8  jmp     short loc_180041BB7
0x180041baa  mov     r8, rdi
0x180041bad  inc     r8
0x180041bb0  cmp     [rdx+r8*2], r15w
0x180041bb5  jnz     short loc_180041BAD
0x180041bb7  lea     rcx, [rsp+88h+Src]; void *
0x180041bbc  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180041bc1  mov     r8, r15
0x180041bc4  cmp     word ptr cs:pszSrc, r15w; "\\"
0x180041bcc  setnz   r8b
0x180041bd0  lea     rdx, pszSrc; "\\"
0x180041bd7  lea     rcx, [rsp+88h+Src]; Src
0x180041bdc  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180041be1  mov     r8d, 14h
0x180041be7  lea     rdx, aAppxprovisioni; "AppxProvisioning.xml"
0x180041bee  lea     rcx, [rsp+88h+Src]; Src
0x180041bf3  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180041bf8  lea     rcx, [rsp+88h+Src]
0x180041bfd  cmp     [rsp+88h+var_38], 8
0x180041c03  cmovnb  rcx, [rsp+88h+Src]
0x180041c09  call    FileExists
0x180041c0e  test    eax, eax
0x180041c10  jnz     loc_180041CC7
0x180041c16  lea     rcx, [rsp+88h+Src]
0x180041c1b  cmp     [rsp+88h+var_38], 8
0x180041c21  cmovnb  rcx, [rsp+88h+Src]
0x180041c27  mov     [rsp+88h+var_40], r15
0x180041c2c  mov     [rcx], r15w
0x180041c30  mov     rdx, [rbx+238h]; Src
0x180041c37  cmp     [rdx], r15w
0x180041c3b  jnz     short loc_180041C42
0x180041c3d  mov     rdi, r15
0x180041c40  jmp     short loc_180041C4C
0x180041c42  inc     rdi
0x180041c45  cmp     [rdx+rdi*2], r15w
0x180041c4a  jnz     short loc_180041C42
0x180041c4c  mov     r8, rdi
0x180041c4f  lea     rcx, [rsp+88h+Src]; void *
0x180041c54  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180041c59  mov     r8, r15
0x180041c5c  cmp     word ptr cs:pszSrc, r15w; "\\"
0x180041c64  setnz   r8b
0x180041c68  lea     rdx, pszSrc; "\\"
0x180041c6f  lea     rcx, [rsp+88h+Src]; Src
0x180041c74  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180041c79  mov     r8d, 8
0x180041c7f  lea     rdx, aSystem32; "System32"
0x180041c86  lea     rcx, [rsp+88h+Src]; Src
0x180041c8b  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180041c90  mov     r8, r15
0x180041c93  cmp     word ptr cs:pszSrc, r15w; "\\"
0x180041c9b  setnz   r8b
0x180041c9f  lea     rdx, pszSrc; "\\"
0x180041ca6  lea     rcx, [rsp+88h+Src]; Src
0x180041cab  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180041cb0  mov     r8d, 14h
0x180041cb6  lea     rdx, aAppxprovisioni; "AppxProvisioning.xml"
0x180041cbd  lea     rcx, [rsp+88h+Src]; Src
0x180041cc2  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180041cc7  lea     rcx, [rsp+88h+Src]
0x180041ccc  cmp     [rsp+88h+var_38], 8
0x180041cd2  cmovnb  rcx, [rsp+88h+Src]
0x180041cd8  call    FileExists
0x180041cdd  test    eax, eax
0x180041cdf  jnz     short loc_180041D2B
0x180041ce1  cmp     [rsp+88h+var_38], 8
0x180041ce7  jb      short loc_180041CFA
0x180041ce9  mov     rcx, [rsp+88h+Src]
0x180041cee  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180041cf5  nop     dword ptr [rax+rax+00h]
0x180041cfa  mov     [rsp+88h+var_38], r13
0x180041cff  mov     [rsp+88h+var_40], r15
0x180041d04  mov     word ptr [rsp+88h+Src], r15w
0x180041d0a  mov     rcx, [rsp+88h+var_58]
0x180041d0f  test    rcx, rcx
0x180041d12  jz      short loc_180041D21
0x180041d14  mov     rax, [rcx]
0x180041d17  mov     rax, [rax+10h]
0x180041d1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041d20  nop
0x180041d21  mov     eax, 2
0x180041d26  jmp     loc_180041E51
0x180041d2b  mov     rbx, [rsp+88h+var_58]
0x180041d30  mov     rax, [rbx]
0x180041d33  mov     rdi, [rax+18h]
0x180041d37  mov     rcx, [rsi]
0x180041d3a  mov     [rsi], r15
0x180041d3d  test    rcx, rcx
0x180041d40  jz      short loc_180041D4F
0x180041d42  mov     rax, [rcx]
0x180041d45  mov     rax, [rax+10h]
0x180041d49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041d4e  nop
0x180041d4f  lea     rdx, [rsp+88h+Src]
0x180041d54  cmp     [rsp+88h+var_38], 8
0x180041d5a  cmovnb  rdx, [rsp+88h+Src]
0x180041d60  mov     r8, rsi
0x180041d63  mov     rcx, rbx
0x180041d66  mov     rax, rdi
0x180041d69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041d6e  mov     edi, eax
0x180041d70  test    eax, eax
0x180041d72  jns     loc_180041DF9
0x180041d78  lea     rdx, [rsp+88h+Src]
0x180041d7d  cmp     [rsp+88h+var_38], 8
0x180041d83  cmovnb  rdx, [rsp+88h+Src]
0x180041d89  mov     rcx, [rsp+88h]; this
0x180041d91  mov     [rsp+88h+var_60], rdx; char *
0x180041d96  lea     rax, aFailedToReadWs; "Failed to read %ws from the image."
0x180041d9d  mov     qword ptr [rsp+88h+var_68], rax; int
0x180041da2  mov     r9d, edi; char *
0x180041da5  lea     r8, aOnecoreAdminAp_5; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180041dac  mov     edx, 252h; void *
0x180041db1  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180041db6  nop
0x180041db7  cmp     [rsp+88h+var_38], 8
0x180041dbd  jb      short loc_180041DD0
0x180041dbf  mov     rcx, [rsp+88h+Src]
0x180041dc4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180041dcb  nop     dword ptr [rax+rax+00h]
0x180041dd0  mov     [rsp+88h+var_38], r13
0x180041dd5  mov     [rsp+88h+var_40], r15
0x180041dda  mov     word ptr [rsp+88h+Src], r15w
0x180041de0  test    rbx, rbx
0x180041de3  jz      short loc_180041DF5
0x180041de5  mov     rax, [rbx]
0x180041de8  mov     rcx, rbx
0x180041deb  mov     rax, [rax+10h]
0x180041def  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041df4  nop
0x180041df5  mov     eax, edi
0x180041df7  jmp     short loc_180041E51
0x180041df9  cmp     [rsp+88h+var_38], 8
0x180041dff  jb      short loc_180041E12
0x180041e01  mov     rcx, [rsp+88h+Src]
0x180041e06  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180041e0d  nop     dword ptr [rax+rax+00h]
0x180041e12  mov     [rsp+88h+var_38], r13
0x180041e17  mov     [rsp+88h+var_40], r15
0x180041e1c  mov     word ptr [rsp+88h+Src], r15w
0x180041e22  test    rbx, rbx
0x180041e25  jz      short loc_180041E37
0x180041e27  mov     rax, [rbx]
0x180041e2a  mov     rcx, rbx
0x180041e2d  mov     rax, [rax+10h]
0x180041e31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041e36  nop
0x180041e37  mov     rcx, [rsi]
0x180041e3a  mov     [r14], rcx
0x180041e3d  mov     rax, [rcx]
0x180041e40  mov     rax, [rax+8]
0x180041e44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041e49  xor     eax, eax
0x180041e4b  jmp     short loc_180041E51
0x180041e4d  mov     eax, dword ptr [rsp+88h+var_58]
0x180041e51  mov     rcx, [rsp+88h+var_30]
0x180041e56  xor     rcx, rsp; StackCookie
0x180041e59  call    __security_check_cookie
0x180041e5e  mov     rbx, [rsp+88h+arg_10]
0x180041e66  add     rsp, 60h
0x180041e6a  pop     r15
0x180041e6c  pop     r14
0x180041e6e  pop     r13
0x180041e70  pop     rdi
0x180041e71  pop     rsi
0x180041e72  retn
```
