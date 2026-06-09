# RegionPolicyProvider::RuntimeClassInitialize(Windows::Data::Json::IJsonObject *)

- ea: `0x18006b368`
- end: `0x18006b507`
- name: `?RuntimeClassInitialize@RegionPolicyProvider@@QEAAJPEAUIJsonObject@Json@Data@Windows@@@Z`
- size: `415`
- prototype: `__int64 __fastcall(RegionPolicyProvider *__hidden this, struct Windows::Data::Json::IJsonObject *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180047470`

## callees

- `0x180004b80`
- `0x18000cc8c`
- `0x1800168c8`
- `0x180041c44`
- `0x18006b368`
- `0x18006b510`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006b3f1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006b495`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006b3f1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006b495`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006b408`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006b4ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006b408`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006b4ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b456`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b456`

## string_xrefs

- `0x18006b430`: `onecore\base\flighting\flightsettings\broker\libs\ctac\regionpolicyprovider.cpp`
- `0x18006b4d2`: `onecore\base\flighting\flightsettings\broker\libs\ctac\regionpolicyprovider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
int __fastcall RegionPolicyProvider::RuntimeClassInitialize(HSTRING *this, struct Windows::Data::Json::IJsonObject *a2)
{
  __int64 (__fastcall *v4)(struct Windows::Data::Json::IJsonObject *, HSTRING, HSTRING *); // r15
  unsigned __int64 v5; // rbx
  unsigned __int64 v6; // rcx
  int v7; // eax
  int v8; // edi
  __int64 (__fastcall *v9)(struct Windows::Data::Json::IJsonObject *, HSTRING, HSTRING *); // r15
  UINT32 length; // [rsp+20h] [rbp-58h] BYREF
  HSTRING string; // [rsp+28h] [rbp-50h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_47988461>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_47988461>::GetImpl'::`2'::impl) )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x28,
             (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\regionpolicyprovider.cpp",
             (const char *)0x32,
             length);
  v4 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, HSTRING, HSTRING *))(*(_QWORD *)a2 + 96LL);
  length = 0;
  v5 = -1;
  v6 = -1;
  do
    ++v6;
  while ( RegionPolicyProvider::s_pszJsonTagForce[v6] );
  if ( (int)ULongLongToUInt(v6, &length) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCreateStringReference(RegionPolicyProvider::s_pszJsonTagForce, length, &hstringHeader, &string);
  v7 = v4(a2, string, this + 3);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v9 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, HSTRING, HSTRING *))(*(_QWORD *)a2 + 80LL);
    WindowsDeleteString(this[2]);
    this[2] = 0;
    length = 0;
    do
      ++v5;
    while ( RegionPolicyProvider::s_pszJsonTagPolicyGUID[v5] );
    if ( (int)ULongLongToUInt(v5, &length) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    WindowsCreateStringReference(RegionPolicyProvider::s_pszJsonTagPolicyGUID, length, &hstringHeader, &string);
    return v9(a2, string, this + 2);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\regionpolicyprovider.cpp",
      (const char *)(unsigned int)v7,
      length);
    return v8;
  }
}

```

## disassembly

```asm
0x18006b368  mov     [rsp+arg_10], rbx
0x18006b36d  push    rsi
0x18006b36e  push    rdi
0x18006b36f  push    r12
0x18006b371  push    r14
0x18006b373  push    r15
0x18006b375  sub     rsp, 50h
0x18006b379  mov     rax, cs:__security_cookie
0x18006b380  xor     rax, rsp
0x18006b383  mov     [rsp+78h+var_30], rax
0x18006b388  mov     rsi, rdx
0x18006b38b  mov     r14, rcx
0x18006b38e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_47988461@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_47988461@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_47988461> `wil::Feature<__WilFeatureTraits_Feature_47988461>::GetImpl(void)'::`2'::impl
0x18006b395  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_47988461@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_47988461>::__private_IsEnabled(void)
0x18006b39a  xor     r12d, r12d
0x18006b39d  test    al, al
0x18006b39f  jnz     short loc_18006B3B0
0x18006b3a1  lea     r9d, [r12+32h]
0x18006b3a6  lea     edx, [r12+28h]
0x18006b3ab  jmp     loc_18006B4D2
0x18006b3b0  mov     rax, [rsi]
0x18006b3b3  mov     r15, [rax+60h]
0x18006b3b7  mov     rdi, cs:?s_pszJsonTagForce@RegionPolicyProvider@@0QEBGEB; ushort const * const RegionPolicyProvider::s_pszJsonTagForce
0x18006b3be  mov     [rsp+78h+length], r12d; int
0x18006b3c3  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18006b3c7  mov     rcx, rbx
0x18006b3ca  inc     rcx; unsigned __int64
0x18006b3cd  cmp     [rdi+rcx*2], r12w
0x18006b3d2  jnz     short loc_18006B3CA
0x18006b3d4  lea     rdx, [rsp+78h+length]; unsigned int *
0x18006b3d9  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18006b3de  test    eax, eax
0x18006b3e0  jns     short loc_18006B3F7
0x18006b3e2  xor     r9d, r9d; lpArguments
0x18006b3e5  xor     r8d, r8d; nNumberOfArguments
0x18006b3e8  lea     edx, [r9+1]; dwExceptionFlags
0x18006b3ec  mov     ecx, 0C000000Dh; dwExceptionCode
0x18006b3f1  call    cs:__imp_RaiseException
0x18006b3f7  lea     r9, [rsp+78h+string]; string
0x18006b3fc  lea     r8, [rsp+78h+hstringHeader]; hstringHeader
0x18006b401  mov     edx, [rsp+78h+length]; length
0x18006b405  mov     rcx, rdi; sourceString
0x18006b408  call    cs:__imp_WindowsCreateStringReference
0x18006b40e  lea     r8, [r14+18h]
0x18006b412  mov     rdx, [rsp+78h+string]
0x18006b417  mov     rcx, rsi
0x18006b41a  mov     rax, r15
0x18006b41d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b422  mov     edi, eax
0x18006b424  test    eax, eax
0x18006b426  jns     short loc_18006B448
0x18006b428  mov     rcx, [rsp+78h]; this
0x18006b42d  mov     r9d, eax; char *
0x18006b430  lea     r8, aOnecoreBaseFli_46; "onecore\\base\\flighting\\flightsetting"...
0x18006b437  mov     edx, 2Fh ; '/'; void *
0x18006b43c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006b441  mov     eax, edi
0x18006b443  jmp     loc_18006B4E4
0x18006b448  mov     rax, [rsi]
0x18006b44b  mov     r15, [rax+50h]
0x18006b44f  lea     rdi, [r14+10h]
0x18006b453  mov     rcx, [rdi]; string
0x18006b456  call    cs:__imp_WindowsDeleteString
0x18006b45c  mov     [rdi], r12
0x18006b45f  mov     r14, cs:?s_pszJsonTagPolicyGUID@RegionPolicyProvider@@0QEBGEB; ushort const * const RegionPolicyProvider::s_pszJsonTagPolicyGUID
0x18006b466  mov     [rsp+78h+length], r12d
0x18006b46b  inc     rbx
0x18006b46e  cmp     [r14+rbx*2], r12w
0x18006b473  jnz     short loc_18006B46B
0x18006b475  lea     rdx, [rsp+78h+length]; unsigned int *
0x18006b47a  mov     rcx, rbx; unsigned __int64
0x18006b47d  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18006b482  test    eax, eax
0x18006b484  jns     short loc_18006B49B
0x18006b486  xor     r9d, r9d; lpArguments
0x18006b489  xor     r8d, r8d; nNumberOfArguments
0x18006b48c  lea     edx, [r9+1]; dwExceptionFlags
0x18006b490  mov     ecx, 0C000000Dh; dwExceptionCode
0x18006b495  call    cs:__imp_RaiseException
0x18006b49b  lea     r9, [rsp+78h+string]; string
0x18006b4a0  lea     r8, [rsp+78h+hstringHeader]; hstringHeader
0x18006b4a5  mov     edx, [rsp+78h+length]; length
0x18006b4a9  mov     rcx, r14; sourceString
0x18006b4ac  call    cs:__imp_WindowsCreateStringReference
0x18006b4b2  mov     r8, rdi
0x18006b4b5  mov     rdx, [rsp+78h+string]
0x18006b4ba  mov     rcx, rsi
0x18006b4bd  mov     rax, r15
0x18006b4c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b4c5  jmp     short loc_18006B4E4
0x18006b4c7  mov     r9d, 65Bh; char *
0x18006b4cd  mov     edx, 33h ; '3'; void *
0x18006b4d2  lea     r8, aOnecoreBaseFli_46; "onecore\\base\\flighting\\flightsetting"...
0x18006b4d9  mov     rcx, [rsp+78h]; this
0x18006b4de  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18006b4e3  nop
0x18006b4e4  mov     rcx, [rsp+78h+var_30]
0x18006b4e9  xor     rcx, rsp; StackCookie
0x18006b4ec  call    __security_check_cookie
0x18006b4f1  mov     rbx, [rsp+78h+arg_10]
0x18006b4f9  add     rsp, 50h
0x18006b4fd  pop     r15
0x18006b4ff  pop     r14
0x18006b501  pop     r12
0x18006b503  pop     rdi
0x18006b504  pop     rsi
0x18006b505  retn
```
