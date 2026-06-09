# IsEnabledThroughSystemSetting_0

- ea: `0x1800581c0`
- end: `0x180058320`
- name: `IsEnabledThroughSystemSetting_0`
- size: `352`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180058110`

## callees

- `0x180002520`
- `0x180011e18`
- `0x180028aa0`
- `0x1800532e8`
- `0x180053da0`
- `0x1800581c0`
- `0x180058328`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180058251`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180058251`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180058213`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180058213`

## string_xrefs

- `0x18005820c`: `Windows.Internal.CapabilityAccess.CapabilityAccess`
- `0x18005825b`: `GetActivationFactory for CapabilityAccess failed`
- `0x1800582a3`: `mcpAccess`
- `0x18005828f`: `cuaAccess`

## pseudocode

```c
bool IsEnabledThroughSystemSetting_0()
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

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59214605>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID59214605>::GetImpl'::`2'::impl) )
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
      JUMPOUT(0x18005831FLL);
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
0x1800581c0  mov     [rsp-8+arg_0], rbx
0x1800581c5  push    rbp
0x1800581c6  mov     rbp, rsp
0x1800581c9  sub     rsp, 50h
0x1800581cd  mov     rax, cs:__security_cookie
0x1800581d4  xor     rax, rsp
0x1800581d7  mov     [rbp+var_8], rax
0x1800581db  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID59214605@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID59214605@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59214605> `wil::Feature<__WilFeatureTraits_Feature_ID59214605>::GetImpl(void)'::`2'::impl
0x1800581e2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID59214605@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59214605>::__private_IsEnabled(void)
0x1800581e7  test    al, al
0x1800581e9  jz      loc_1800582DF
0x1800581ef  mov     [rbp+var_30], 0
0x1800581f7  mov     [rbp+string], 0
0x1800581ff  lea     r9, [rbp+string]; string
0x180058203  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180058207  mov     edx, 32h ; '2'; length
0x18005820c  lea     rcx, ?RuntimeClass_Windows_Internal_CapabilityAccess_CapabilityAccess@@3QB_WB; "Windows.Internal.CapabilityAccess.Capab"...
0x180058213  call    cs:__imp_WindowsCreateStringReference
0x180058219  test    eax, eax
0x18005821b  js      loc_180058318
0x180058221  mov     rbx, [rbp+string]
0x180058225  mov     rcx, [rbp+var_30]
0x180058229  test    rcx, rcx
0x18005822c  jz      short loc_180058243
0x18005822e  mov     [rbp+var_30], 0
0x180058236  mov     rax, [rcx]
0x180058239  mov     rax, [rax+10h]
0x18005823d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058242  nop
0x180058243  lea     r8, [rbp+var_30]
0x180058247  lea     rdx, _GUID_518f3880_4e5c_4524_ab03_cd01336b2178
0x18005824e  mov     rcx, rbx
0x180058251  call    cs:__imp_RoGetActivationFactory
0x180058257  test    eax, eax
0x180058259  jns     short loc_18005828F
0x18005825b  lea     rdx, aGetactivationf; "GetActivationFactory for CapabilityAcce"...
0x180058262  mov     ecx, 2; unsigned __int8
0x180058267  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x18005826c  nop
0x18005826d  mov     rcx, [rbp+var_30]
0x180058271  test    rcx, rcx
0x180058274  jz      short loc_18005828B
0x180058276  mov     [rbp+var_30], 0
0x18005827e  mov     rax, [rcx]
0x180058281  mov     rax, [rax+10h]
0x180058285  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005828a  nop
0x18005828b  xor     al, al
0x18005828d  jmp     short loc_180058301
0x18005828f  lea     rdx, aCuaaccess; "cuaAccess"
0x180058296  lea     rcx, [rbp+var_30]
0x18005829a  call    IsCAMPolicyEnabled
0x18005829f  test    al, al
0x1800582a1  jz      short loc_1800582BB
0x1800582a3  lea     rdx, aMcpaccess; "mcpAccess"
0x1800582aa  lea     rcx, [rbp+var_30]
0x1800582ae  call    IsCAMPolicyEnabled
0x1800582b3  test    al, al
0x1800582b5  jz      short loc_1800582BB
0x1800582b7  mov     bl, 1
0x1800582b9  jmp     short loc_1800582BD
0x1800582bb  xor     bl, bl
0x1800582bd  mov     rcx, [rbp+var_30]
0x1800582c1  test    rcx, rcx
0x1800582c4  jz      short loc_1800582DB
0x1800582c6  mov     [rbp+var_30], 0
0x1800582ce  mov     rdx, [rcx]
0x1800582d1  mov     rax, [rdx+10h]
0x1800582d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800582da  nop
0x1800582db  mov     al, bl
0x1800582dd  jmp     short loc_180058301
0x1800582df  mov     dword ptr [rbp+var_30], 0
0x1800582e6  lea     r9, [rbp+var_30]
0x1800582ea  lea     r8, aEnabled; "Enabled"
0x1800582f1  call    ??$get_value_nothrow@K$0A@@reg@wil@@YAJPEAUHKEY__@@PEB_W1PEAK@Z; wil::reg::get_value_nothrow<ulong,0>(HKEY__ *,wchar_t const *,wchar_t const *,ulong *)
0x1800582f6  test    eax, eax
0x1800582f8  js      short loc_18005828B
0x1800582fa  cmp     dword ptr [rbp+var_30], 0
0x1800582fe  setnz   al
0x180058301  mov     rcx, [rbp+var_8]
0x180058305  xor     rcx, rsp; StackCookie
0x180058308  call    __security_check_cookie
0x18005830d  mov     rbx, [rsp+50h+arg_0]
0x180058312  add     rsp, 50h
0x180058316  pop     rbp
0x180058317  retn
0x180058318  mov     ecx, eax; this
0x18005831a  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
