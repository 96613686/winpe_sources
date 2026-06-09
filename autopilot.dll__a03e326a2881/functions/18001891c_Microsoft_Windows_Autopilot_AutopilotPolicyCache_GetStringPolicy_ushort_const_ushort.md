# Microsoft::Windows::Autopilot::AutopilotPolicyCache::GetStringPolicy(ushort const *,ushort * *)

- ea: `0x18001891c`
- end: `0x180018b0a`
- name: `?GetStringPolicy@AutopilotPolicyCache@Autopilot@Windows@Microsoft@@SAJPEBGPEAPEAG@Z`
- size: `494`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800129b0`

## callees

- `0x1800045b0`
- `0x1800105f4`
- `0x1800180a8`
- `0x1800182f4`
- `0x1800185c0`
- `0x18001891c`
- `0x18001e470`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180018a6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180018a6b`

## string_xrefs

- `0x180018971`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicycache.cpp`
- `0x180018a30`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicycache.cpp`
- `0x180018a96`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicycache.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::Windows::Autopilot::AutopilotPolicyCache::GetStringPolicy(
        const unsigned __int16 *a1,
        unsigned __int16 **a2)
{
  __int64 v3; // rdx
  int JsonFromRegistry; // eax
  unsigned int v6; // r8d
  unsigned int v7; // ebx
  __int64 v8; // rcx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, PVOID, HSTRING *); // rbx
  HSTRING_HEADER *v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rcx
  PCWSTR StringRawBuffer; // rax
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // [rsp+20h] [rbp-40h] BYREF
  const WCHAR *v18; // [rsp+28h] [rbp-38h] BYREF
  HSTRING string; // [rsp+30h] [rbp-30h] BYREF
  HSTRING_HEADER v20; // [rsp+38h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  v18 = a1;
  if ( Microsoft::Windows::Autopilot::AutoPilotPolicyManager::IsDisabled() )
    return 2147943569LL;
  v17 = 0;
  JsonFromRegistry = Microsoft::Windows::Autopilot::GetJsonFromRegistry(&v17, v3);
  v7 = JsonFromRegistry;
  if ( JsonFromRegistry < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x78,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotpolicycache.cpp",
      (const char *)(unsigned int)JsonFromRegistry,
      v17);
    v8 = v17;
    if ( v17 )
    {
      v17 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    return v7;
  }
  string = 0;
  v9 = v17;
  v10 = *(__int64 (__fastcall **)(__int64, PVOID, HSTRING *))(*(_QWORD *)v17 + 80LL);
  v11 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v20, &v18, v6);
  v7 = v10(v9, v11[1].Reserved.Reserved1, &string);
  if ( v7 == -2089484279 )
  {
    v7 = -2147023727;
  }
  else if ( v7 == -2147483634 )
  {
    v7 = -2147023267;
  }
  if ( v7 == -2147023727 )
  {
    v12 = v17;
    if ( v17 )
    {
      v17 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
    return 2147943569LL;
  }
  else
  {
    if ( (v7 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7D,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotpolicycache.cpp",
        (const char *)v7,
        v17);
      v13 = v17;
      if ( v17 )
      {
        v17 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      }
      return v7;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v18,
      StringRawBuffer,
      -1);
    if ( !v18 )
    {
      v7 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x80,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotpolicycache.cpp",
        (const char *)0x8007000ELL,
        v17);
      v15 = v17;
      if ( v17 )
      {
        v17 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      }
      return v7;
    }
    *a2 = (unsigned __int16 *)v18;
    v16 = v17;
    if ( v17 )
    {
      v17 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x18001891c  mov     [rsp-18h+arg_10], rbx
0x180018921  push    rbp
0x180018922  push    rsi
0x180018923  push    rdi
0x180018924  mov     rbp, rsp
0x180018927  sub     rsp, 60h
0x18001892b  mov     rax, cs:__security_cookie
0x180018932  xor     rax, rsp
0x180018935  mov     [rbp+var_8], rax
0x180018939  mov     rsi, rdx
0x18001893c  mov     [rbp+var_38], rcx
0x180018940  call    ?IsDisabled@AutoPilotPolicyManager@Autopilot@Windows@Microsoft@@SA_NXZ; Microsoft::Windows::Autopilot::AutoPilotPolicyManager::IsDisabled(void)
0x180018945  test    al, al
0x180018947  jz      short loc_180018953
0x180018949  mov     eax, 80070491h
0x18001894e  jmp     loc_180018AEE
0x180018953  mov     [rbp+var_40], 0
0x18001895b  lea     rcx, [rbp+var_40]
0x18001895f  call    ?GetJsonFromRegistry@Autopilot@Windows@Microsoft@@YAJAEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@3@@Z; Microsoft::Windows::Autopilot::GetJsonFromRegistry(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)
0x180018964  mov     ebx, eax
0x180018966  test    eax, eax
0x180018968  jns     short loc_1800189A8
0x18001896a  mov     rcx, [rbp+18h]; this
0x18001896e  mov     r9d, eax; char *
0x180018971  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x180018978  mov     edx, 78h ; 'x'; void *
0x18001897d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018982  nop
0x180018983  mov     rcx, [rbp+var_40]
0x180018987  test    rcx, rcx
0x18001898a  jz      short loc_1800189A1
0x18001898c  mov     [rbp+var_40], 0
0x180018994  mov     rax, [rcx]
0x180018997  mov     rax, [rax+10h]
0x18001899b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800189a0  nop
0x1800189a1  mov     eax, ebx
0x1800189a3  jmp     loc_180018AEE
0x1800189a8  mov     [rbp+string], 0
0x1800189b0  mov     rdi, [rbp+var_40]
0x1800189b4  mov     rax, [rdi]
0x1800189b7  mov     rbx, [rax+50h]
0x1800189bb  lea     rdx, [rbp+var_38]
0x1800189bf  lea     rcx, [rbp+var_28]
0x1800189c3  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800189c8  nop
0x1800189c9  lea     r8, [rbp+string]
0x1800189cd  mov     rdx, [rax+18h]
0x1800189d1  mov     rcx, rdi
0x1800189d4  mov     rax, rbx
0x1800189d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800189dc  mov     ebx, eax
0x1800189de  mov     edi, 80070491h
0x1800189e3  cmp     eax, 83750009h
0x1800189e8  jnz     short loc_1800189EE
0x1800189ea  mov     ebx, edi
0x1800189ec  jmp     short loc_1800189FC
0x1800189ee  mov     eax, 8007065Dh
0x1800189f3  cmp     ebx, 8000000Eh
0x1800189f9  cmovz   ebx, eax
0x1800189fc  cmp     ebx, edi
0x1800189fe  jnz     short loc_180018A25
0x180018a00  mov     rcx, [rbp+var_40]
0x180018a04  test    rcx, rcx
0x180018a07  jz      short loc_180018A1E
0x180018a09  mov     [rbp+var_40], 0
0x180018a11  mov     rax, [rcx]
0x180018a14  mov     rax, [rax+10h]
0x180018a18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a1d  nop
0x180018a1e  mov     eax, edi
0x180018a20  jmp     loc_180018AEE
0x180018a25  test    ebx, ebx
0x180018a27  jns     short loc_180018A65
0x180018a29  mov     rcx, [rbp+18h]; this
0x180018a2d  mov     r9d, ebx; char *
0x180018a30  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x180018a37  mov     edx, 7Dh ; '}'; void *
0x180018a3c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018a41  nop
0x180018a42  mov     rcx, [rbp+var_40]
0x180018a46  test    rcx, rcx
0x180018a49  jz      short loc_180018A60
0x180018a4b  mov     [rbp+var_40], 0
0x180018a53  mov     rdx, [rcx]
0x180018a56  mov     rax, [rdx+10h]
0x180018a5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a5f  nop
0x180018a60  jmp     loc_1800189A1
0x180018a65  xor     edx, edx; length
0x180018a67  mov     rcx, [rbp+string]; string
0x180018a6b  call    cs:__imp_WindowsGetStringRawBuffer
0x180018a71  or      r8, 0FFFFFFFFFFFFFFFFh
0x180018a75  mov     rdx, rax
0x180018a78  lea     rcx, [rbp+var_38]
0x180018a7c  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180018a81  mov     rax, [rbp+var_38]
0x180018a85  test    rax, rax
0x180018a88  jnz     short loc_180018ACB
0x180018a8a  mov     rcx, [rbp+18h]; this
0x180018a8e  mov     ebx, 8007000Eh
0x180018a93  mov     r9d, ebx; char *
0x180018a96  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x180018a9d  mov     edx, 80h; void *
0x180018aa2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018aa7  nop
0x180018aa8  mov     rcx, [rbp+var_40]
0x180018aac  test    rcx, rcx
0x180018aaf  jz      short loc_180018AC6
0x180018ab1  mov     [rbp+var_40], 0
0x180018ab9  mov     rdx, [rcx]
0x180018abc  mov     rax, [rdx+10h]
0x180018ac0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018ac5  nop
0x180018ac6  jmp     loc_1800189A1
0x180018acb  mov     [rsi], rax
0x180018ace  mov     rcx, [rbp+var_40]
0x180018ad2  test    rcx, rcx
0x180018ad5  jz      short loc_180018AEC
0x180018ad7  mov     [rbp+var_40], 0
0x180018adf  mov     rax, [rcx]
0x180018ae2  mov     rax, [rax+10h]
0x180018ae6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018aeb  nop
0x180018aec  xor     eax, eax
0x180018aee  mov     rcx, [rbp+var_8]
0x180018af2  xor     rcx, rsp; StackCookie
0x180018af5  call    __security_check_cookie
0x180018afa  mov     rbx, [rsp+60h+arg_10]
0x180018b02  add     rsp, 60h
0x180018b06  pop     rdi
0x180018b07  pop     rsi
0x180018b08  pop     rbp
0x180018b09  retn
```
