# CloudCacheInitializer::IsServiceAccount(ushort const *,bool *)

- ea: `0x18003c4f4`
- end: `0x18003c5b0`
- name: `?IsServiceAccount@CloudCacheInitializer@@CAJPEBGPEA_N@Z`
- size: `188`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool *)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003c340`
- `0x1801a76a0`
- `0x1801a7c60`

## callees

- `0x18003bf2c`
- `0x18003c4f4`
- `0x180178038`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003c586`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003c586`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18003c566`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18003c566`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18003c52a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18003c52a`

## string_xrefs

- `0x18003c598`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheinitializer.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CloudCacheInitializer::IsServiceAccount(const unsigned __int16 *a1, bool *a2)
{
  bool v3; // di
  const char *v4; // r9
  PSID v5; // r14
  __int64 *i; // rbx
  const char *v8; // r9
  __int64 v9; // rdx
  PSID *p_pSid; // [rsp+20h] [rbp-48h] BYREF
  PSID v11; // [rsp+28h] [rbp-40h] BYREF
  char v12; // [rsp+30h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  PSID pSid; // [rsp+78h] [rbp+10h] BYREF

  *a2 = 0;
  pSid = 0;
  p_pSid = &pSid;
  v11 = 0;
  v3 = 1;
  v12 = 1;
  if ( !ConvertStringSidToSidW(a1, &v11) )
  {
    try
    {
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x5C0,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheinitializer.cpp",
        v4);
    }
    catch ( ... )
    {
      *(_DWORD *)(v9 + 120) = wil::details::in1diag3::Return_CaughtException(
                                retaddr,
                                (void *)0x5C4,
                                (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheinitializer.cpp",
                                v8);
      return (unsigned int)pSid;
    }
  }
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&p_pSid);
  v5 = pSid;
  for ( i = qword_18022B6A0;
        i != winrt::impl::guid_v<winrt::Windows::Foundation::AsyncOperationCompletedHandler<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::ApplicationModel::AppExtensions::AppExtension>>>;
        ++i )
  {
    if ( !*((_BYTE *)i + 4) && IsWellKnownSid(v5, *(WELL_KNOWN_SID_TYPE *)i) )
      goto LABEL_8;
  }
  v3 = 0;
LABEL_8:
  *a2 = v3;
  if ( pSid )
    LocalFree(pSid);
  return 0;
}

```

## disassembly

```asm
0x18003c4f4  mov     r11, rsp
0x18003c4f7  push    rbx
0x18003c4f8  push    rsi
0x18003c4f9  push    rdi
0x18003c4fa  push    r14
0x18003c4fc  sub     rsp, 48h
0x18003c500  mov     rsi, rdx
0x18003c503  mov     byte ptr [rdx], 0
0x18003c506  mov     qword ptr [r11+10h], 0
0x18003c50e  lea     rax, [r11+10h]
0x18003c512  mov     [r11-48h], rax
0x18003c516  mov     qword ptr [r11-40h], 0
0x18003c51e  mov     dil, 1
0x18003c521  mov     [rsp+68h+var_38], dil
0x18003c526  lea     rdx, [r11-40h]; Sid
0x18003c52a  call    cs:__imp_ConvertStringSidToSidW
0x18003c530  mov     rcx, [rsp+68h]; this
0x18003c535  test    eax, eax
0x18003c537  jz      short loc_18003C598
0x18003c539  lea     rcx, [rsp+68h+var_48]
0x18003c53e  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x18003c543  mov     r14, [rsp+68h+pSid]
0x18003c548  lea     rbx, qword_18022B6A0
0x18003c54f  lea     rax, ??$guid_v@U?$AsyncOperationCompletedHandler@U?$IVectorView@UAppExtension@AppExtensions@ApplicationModel@Windows@winrt@@@Collections@Foundation@Windows@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::AsyncOperationCompletedHandler<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::ApplicationModel::AppExtensions::AppExtension>>>
0x18003c556  cmp     rbx, rax
0x18003c559  jz      short loc_18003C576
0x18003c55b  cmp     byte ptr [rbx+4], 0
0x18003c55f  jnz     short loc_18003C570
0x18003c561  mov     edx, [rbx]; WellKnownSidType
0x18003c563  mov     rcx, r14; pSid
0x18003c566  call    cs:__imp_IsWellKnownSid
0x18003c56c  test    eax, eax
0x18003c56e  jnz     short loc_18003C579
0x18003c570  add     rbx, 8
0x18003c574  jmp     short loc_18003C54F
0x18003c576  xor     dil, dil
0x18003c579  mov     [rsi], dil
0x18003c57c  mov     rcx, [rsp+68h+pSid]; hMem
0x18003c581  test    rcx, rcx
0x18003c584  jz      short loc_18003C58C
0x18003c586  call    cs:__imp_LocalFree
0x18003c58c  xor     eax, eax
0x18003c58e  add     rsp, 48h
0x18003c592  pop     r14
0x18003c594  pop     rdi
0x18003c595  pop     rsi
0x18003c596  pop     rbx
0x18003c597  retn
0x18003c598  lea     r8, aOnecoreuapShel_17; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x18003c59f  mov     edx, 5C0h; void *
0x18003c5a4  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18003c5aa  mov     eax, dword ptr [rsp+68h+pSid]
0x18003c5ae  jmp     short loc_18003C58E
```
