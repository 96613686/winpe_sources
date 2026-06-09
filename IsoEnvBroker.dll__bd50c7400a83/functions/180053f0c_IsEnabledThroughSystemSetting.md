# IsEnabledThroughSystemSetting

- ea: `0x180053f0c`
- end: `0x18005406c`
- name: `IsEnabledThroughSystemSetting`
- size: `352`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180053cf0`

## callees

- `0x180002520`
- `0x180011e18`
- `0x180028aa0`
- `0x1800532e8`
- `0x180053da0`
- `0x180053f0c`
- `0x1800542c8`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180053f9d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180053f9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180053f5f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180053f5f`

## string_xrefs

- `0x180053f58`: `Windows.Internal.CapabilityAccess.CapabilityAccess`
- `0x180053fa7`: `GetActivationFactory for CapabilityAccess failed`
- `0x180053fef`: `mcpAccess`
- `0x180053fdb`: `cuaAccess`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
bool IsEnabledThroughSystemSetting()
{
  __int64 v0; // rdx
  __int64 v1; // rcx
  HRESULT v2; // eax
  int v3; // edx
  unsigned int v4; // r8d
  __int64 v5; // rcx
  bool v7; // bl
  __int64 v8; // rcx
  __int64 v9; // [rsp+20h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+28h] [rbp-28h] BYREF
  HSTRING string; // [rsp+40h] [rbp-10h] BYREF

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59930952>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID59930952>::GetImpl'::`2'::impl) )
  {
    v9 = 0;
    string = 0;
    v2 = WindowsCreateStringReference(
           L"Windows.Internal.CapabilityAccess.CapabilityAccess",
           0x32u,
           &hstringHeader,
           &string);
    if ( v2 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v2, v3, v4);
      JUMPOUT(0x18005406BLL);
    }
    if ( (int)RoGetActivationFactory(string, &GUID_518f3880_4e5c_4524_ab03_cd01336b2178, &v9) < 0 )
    {
      Log(2u, L"GetActivationFactory for CapabilityAccess failed");
      v5 = v9;
      if ( v9 )
      {
        v9 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
      }
      return 0;
    }
    v7 = (unsigned __int8)IsCAMPolicyEnabled(&v9, L"cuaAccess")
      && (unsigned __int8)IsCAMPolicyEnabled(&v9, L"mcpAccess");
    v8 = v9;
    if ( v9 )
    {
      v9 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    return v7;
  }
  else
  {
    LODWORD(v9) = 0;
    if ( wil::reg::get_value_nothrow<unsigned long,0>(v1, v0, L"Enabled", &v9) < 0 )
      return 0;
    return (_DWORD)v9 != 0;
  }
}

```

## disassembly

```asm
0x180053f0c  mov     [rsp-8+arg_0], rbx
0x180053f11  push    rbp
0x180053f12  mov     rbp, rsp
0x180053f15  sub     rsp, 50h
0x180053f19  mov     rax, cs:__security_cookie
0x180053f20  xor     rax, rsp
0x180053f23  mov     [rbp+var_8], rax
0x180053f27  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID59930952@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID59930952@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59930952> `wil::Feature<__WilFeatureTraits_Feature_ID59930952>::GetImpl(void)'::`2'::impl
0x180053f2e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID59930952@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59930952>::__private_IsEnabled(void)
0x180053f33  test    al, al
0x180053f35  jz      loc_18005402B
0x180053f3b  mov     [rbp+var_30], 0
0x180053f43  mov     [rbp+string], 0
0x180053f4b  lea     r9, [rbp+string]; string
0x180053f4f  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180053f53  mov     edx, 32h ; '2'; length
0x180053f58  lea     rcx, ?RuntimeClass_Windows_Internal_CapabilityAccess_CapabilityAccess@@3QB_WB; "Windows.Internal.CapabilityAccess.Capab"...
0x180053f5f  call    cs:__imp_WindowsCreateStringReference
0x180053f65  test    eax, eax
0x180053f67  js      loc_180054064
0x180053f6d  mov     rbx, [rbp+string]
0x180053f71  mov     rcx, [rbp+var_30]
0x180053f75  test    rcx, rcx
0x180053f78  jz      short loc_180053F8F
0x180053f7a  mov     [rbp+var_30], 0
0x180053f82  mov     rax, [rcx]
0x180053f85  mov     rax, [rax+10h]
0x180053f89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053f8e  nop
0x180053f8f  lea     r8, [rbp+var_30]
0x180053f93  lea     rdx, _GUID_518f3880_4e5c_4524_ab03_cd01336b2178
0x180053f9a  mov     rcx, rbx
0x180053f9d  call    cs:__imp_RoGetActivationFactory
0x180053fa3  test    eax, eax
0x180053fa5  jns     short loc_180053FDB
0x180053fa7  lea     rdx, aGetactivationf; "GetActivationFactory for CapabilityAcce"...
0x180053fae  mov     ecx, 2; unsigned __int8
0x180053fb3  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180053fb8  nop
0x180053fb9  mov     rcx, [rbp+var_30]
0x180053fbd  test    rcx, rcx
0x180053fc0  jz      short loc_180053FD7
0x180053fc2  mov     [rbp+var_30], 0
0x180053fca  mov     rax, [rcx]
0x180053fcd  mov     rax, [rax+10h]
0x180053fd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053fd6  nop
0x180053fd7  xor     al, al
0x180053fd9  jmp     short loc_18005404D
0x180053fdb  lea     rdx, aCuaaccess; "cuaAccess"
0x180053fe2  lea     rcx, [rbp+var_30]
0x180053fe6  call    IsCAMPolicyEnabled
0x180053feb  test    al, al
0x180053fed  jz      short loc_180054007
0x180053fef  lea     rdx, aMcpaccess; "mcpAccess"
0x180053ff6  lea     rcx, [rbp+var_30]
0x180053ffa  call    IsCAMPolicyEnabled
0x180053fff  test    al, al
0x180054001  jz      short loc_180054007
0x180054003  mov     bl, 1
0x180054005  jmp     short loc_180054009
0x180054007  xor     bl, bl
0x180054009  mov     rcx, [rbp+var_30]
0x18005400d  test    rcx, rcx
0x180054010  jz      short loc_180054027
0x180054012  mov     [rbp+var_30], 0
0x18005401a  mov     rdx, [rcx]
0x18005401d  mov     rax, [rdx+10h]
0x180054021  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054026  nop
0x180054027  mov     al, bl
0x180054029  jmp     short loc_18005404D
0x18005402b  mov     dword ptr [rbp+var_30], 0
0x180054032  lea     r9, [rbp+var_30]
0x180054036  lea     r8, aEnabled; "Enabled"
0x18005403d  call    ??$get_value_nothrow@K$0A@@reg@wil@@YAJPEAUHKEY__@@PEB_W1PEAK@Z; wil::reg::get_value_nothrow<ulong,0>(HKEY__ *,wchar_t const *,wchar_t const *,ulong *)
0x180054042  test    eax, eax
0x180054044  js      short loc_180053FD7
0x180054046  cmp     dword ptr [rbp+var_30], 0
0x18005404a  setnz   al
0x18005404d  mov     rcx, [rbp+var_8]
0x180054051  xor     rcx, rsp; StackCookie
0x180054054  call    __security_check_cookie
0x180054059  mov     rbx, [rsp+50h+arg_0]
0x18005405e  add     rsp, 50h
0x180054062  pop     rbp
0x180054063  retn
0x180054064  mov     ecx, eax; this
0x180054066  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
