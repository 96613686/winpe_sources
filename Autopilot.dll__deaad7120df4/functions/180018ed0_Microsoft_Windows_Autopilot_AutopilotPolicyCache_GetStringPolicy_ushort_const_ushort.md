# Microsoft::Windows::Autopilot::AutopilotPolicyCache::GetStringPolicy(ushort const *,ushort * *)

- ea: `0x180018ed0`
- end: `0x1800190c5`
- name: `?GetStringPolicy@AutopilotPolicyCache@Autopilot@Windows@Microsoft@@SAJPEBGPEAPEAG@Z`
- size: `501`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012bf0`

## callees

- `0x1800045d0`
- `0x180010764`
- `0x1800185f8`
- `0x180018854`
- `0x180018b38`
- `0x180018ed0`
- `0x18001ecc4`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001901f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001901f`

## string_xrefs

- `0x180018f25`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicycache.cpp`
- `0x180018fe4`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicycache.cpp`
- `0x180019050`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicycache.cpp`

## pseudocode

```c
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
  char *StringRawBuffer; // rax
  const char *v15; // r9
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // [rsp+20h] [rbp-40h] BYREF
  const WCHAR *v19; // [rsp+28h] [rbp-38h] BYREF
  HSTRING string; // [rsp+30h] [rbp-30h] BYREF
  HSTRING_HEADER v21; // [rsp+38h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  v19 = a1;
  if ( Microsoft::Windows::Autopilot::AutoPilotPolicyManager::IsDisabled() )
    return 2147943569LL;
  v18 = 0;
  JsonFromRegistry = Microsoft::Windows::Autopilot::GetJsonFromRegistry(&v18, v3);
  v7 = JsonFromRegistry;
  if ( JsonFromRegistry < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x78,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotpolicycache.cpp",
      (const char *)(unsigned int)JsonFromRegistry,
      v18);
    v8 = v18;
    if ( v18 )
    {
      v18 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    return v7;
  }
  string = 0;
  v9 = v18;
  v10 = *(__int64 (__fastcall **)(__int64, PVOID, HSTRING *))(*(_QWORD *)v18 + 80LL);
  v11 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v21, &v19, v6);
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
    v12 = v18;
    if ( v18 )
    {
      v18 = 0;
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
        v18);
      v13 = v18;
      if ( v18 )
      {
        v18 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      }
      return v7;
    }
    StringRawBuffer = (char *)WindowsGetStringRawBuffer(string, 0);
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v19,
      StringRawBuffer,
      0xFFFFFFFFFFFFFFFFuLL,
      v15);
    if ( !v19 )
    {
      v7 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x80,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotpolicycache.cpp",
        (const char *)0x8007000ELL,
        v18);
      v16 = v18;
      if ( v18 )
      {
        v18 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      }
      return v7;
    }
    *a2 = (unsigned __int16 *)v19;
    v17 = v18;
    if ( v18 )
    {
      v18 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x180018ed0  mov     [rsp-18h+arg_10], rbx
0x180018ed5  push    rbp
0x180018ed6  push    rsi
0x180018ed7  push    rdi
0x180018ed8  mov     rbp, rsp
0x180018edb  sub     rsp, 60h
0x180018edf  mov     rax, cs:__security_cookie
0x180018ee6  xor     rax, rsp
0x180018ee9  mov     [rbp+var_8], rax
0x180018eed  mov     rsi, rdx
0x180018ef0  mov     [rbp+var_38], rcx
0x180018ef4  call    ?IsDisabled@AutoPilotPolicyManager@Autopilot@Windows@Microsoft@@SA_NXZ; Microsoft::Windows::Autopilot::AutoPilotPolicyManager::IsDisabled(void)
0x180018ef9  test    al, al
0x180018efb  jz      short loc_180018F07
0x180018efd  mov     eax, 80070491h
0x180018f02  jmp     loc_1800190A8
0x180018f07  mov     [rbp+var_40], 0
0x180018f0f  lea     rcx, [rbp+var_40]
0x180018f13  call    ?GetJsonFromRegistry@Autopilot@Windows@Microsoft@@YAJAEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@3@@Z; Microsoft::Windows::Autopilot::GetJsonFromRegistry(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)
0x180018f18  mov     ebx, eax
0x180018f1a  test    eax, eax
0x180018f1c  jns     short loc_180018F5C
0x180018f1e  mov     rcx, [rbp+18h]; this
0x180018f22  mov     r9d, eax; char *
0x180018f25  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x180018f2c  mov     edx, 78h ; 'x'; void *
0x180018f31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018f36  nop
0x180018f37  mov     rcx, [rbp+var_40]
0x180018f3b  test    rcx, rcx
0x180018f3e  jz      short loc_180018F55
0x180018f40  mov     [rbp+var_40], 0
0x180018f48  mov     rax, [rcx]
0x180018f4b  mov     rax, [rax+10h]
0x180018f4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f54  nop
0x180018f55  mov     eax, ebx
0x180018f57  jmp     loc_1800190A8
0x180018f5c  mov     [rbp+string], 0
0x180018f64  mov     rdi, [rbp+var_40]
0x180018f68  mov     rax, [rdi]
0x180018f6b  mov     rbx, [rax+50h]
0x180018f6f  lea     rdx, [rbp+var_38]
0x180018f73  lea     rcx, [rbp+var_28]
0x180018f77  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180018f7c  nop
0x180018f7d  lea     r8, [rbp+string]
0x180018f81  mov     rdx, [rax+18h]
0x180018f85  mov     rcx, rdi
0x180018f88  mov     rax, rbx
0x180018f8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f90  mov     ebx, eax
0x180018f92  mov     edi, 80070491h
0x180018f97  cmp     eax, 83750009h
0x180018f9c  jnz     short loc_180018FA2
0x180018f9e  mov     ebx, edi
0x180018fa0  jmp     short loc_180018FB0
0x180018fa2  mov     eax, 8007065Dh
0x180018fa7  cmp     ebx, 8000000Eh
0x180018fad  cmovz   ebx, eax
0x180018fb0  cmp     ebx, edi
0x180018fb2  jnz     short loc_180018FD9
0x180018fb4  mov     rcx, [rbp+var_40]
0x180018fb8  test    rcx, rcx
0x180018fbb  jz      short loc_180018FD2
0x180018fbd  mov     [rbp+var_40], 0
0x180018fc5  mov     rax, [rcx]
0x180018fc8  mov     rax, [rax+10h]
0x180018fcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018fd1  nop
0x180018fd2  mov     eax, edi
0x180018fd4  jmp     loc_1800190A8
0x180018fd9  test    ebx, ebx
0x180018fdb  jns     short loc_180019019
0x180018fdd  mov     rcx, [rbp+18h]; this
0x180018fe1  mov     r9d, ebx; char *
0x180018fe4  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x180018feb  mov     edx, 7Dh ; '}'; void *
0x180018ff0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018ff5  nop
0x180018ff6  mov     rcx, [rbp+var_40]
0x180018ffa  test    rcx, rcx
0x180018ffd  jz      short loc_180019014
0x180018fff  mov     [rbp+var_40], 0
0x180019007  mov     rdx, [rcx]
0x18001900a  mov     rax, [rdx+10h]
0x18001900e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019013  nop
0x180019014  jmp     loc_180018F55
0x180019019  xor     edx, edx; length
0x18001901b  mov     rcx, [rbp+string]; string
0x18001901f  call    cs:__imp_WindowsGetStringRawBuffer
0x180019026  nop     dword ptr [rax+rax+00h]
0x18001902b  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001902f  mov     rdx, rax
0x180019032  lea     rcx, [rbp+var_38]
0x180019036  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18001903b  mov     rax, [rbp+var_38]
0x18001903f  test    rax, rax
0x180019042  jnz     short loc_180019085
0x180019044  mov     rcx, [rbp+18h]; this
0x180019048  mov     ebx, 8007000Eh
0x18001904d  mov     r9d, ebx; char *
0x180019050  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x180019057  mov     edx, 80h; void *
0x18001905c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019061  nop
0x180019062  mov     rcx, [rbp+var_40]
0x180019066  test    rcx, rcx
0x180019069  jz      short loc_180019080
0x18001906b  mov     [rbp+var_40], 0
0x180019073  mov     rdx, [rcx]
0x180019076  mov     rax, [rdx+10h]
0x18001907a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001907f  nop
0x180019080  jmp     loc_180018F55
0x180019085  mov     [rsi], rax
0x180019088  mov     rcx, [rbp+var_40]
0x18001908c  test    rcx, rcx
0x18001908f  jz      short loc_1800190A6
0x180019091  mov     [rbp+var_40], 0
0x180019099  mov     rax, [rcx]
0x18001909c  mov     rax, [rax+10h]
0x1800190a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800190a5  nop
0x1800190a6  xor     eax, eax
0x1800190a8  mov     rcx, [rbp+var_8]
0x1800190ac  xor     rcx, rsp; StackCookie
0x1800190af  call    __security_check_cookie
0x1800190b4  mov     rbx, [rsp+60h+arg_10]
0x1800190bc  add     rsp, 60h
0x1800190c0  pop     rdi
0x1800190c1  pop     rsi
0x1800190c2  pop     rbp
0x1800190c3  retn
```
