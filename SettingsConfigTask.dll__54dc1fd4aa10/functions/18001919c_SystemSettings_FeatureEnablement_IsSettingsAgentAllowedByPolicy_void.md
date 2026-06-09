# SystemSettings::FeatureEnablement::IsSettingsAgentAllowedByPolicy(void)

- ea: `0x18001919c`
- end: `0x180019266`
- name: `?IsSettingsAgentAllowedByPolicy@FeatureEnablement@SystemSettings@@YA_NXZ`
- size: `202`
- prototype: `char __fastcall(SystemSettings::FeatureEnablement *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180012f68`

## callees

- `0x180002e88`
- `0x180002ef4`
- `0x1800129b8`
- `0x18001919c`
- `0x18001cd90`

## import_xrefs

- `ext-ms-win-devmgmt-policy-l1-1-1!PolicyManager_GetPolicy` at `0x180019222`
- `ext-ms-win-devmgmt-policy-l1-1-1!PolicyManager_GetPolicy` at `0x180019222`

## string_xrefs

- `0x180019214`: `DisableSettingsAgent`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall SystemSettings::FeatureEnablement::IsSettingsAgentAllowedByPolicy(
        SystemSettings::FeatureEnablement *this)
{
  bool v1; // bl
  __m128i si128; // [rsp+20h] [rbp-18h] BYREF
  __int64 v4; // [rsp+40h] [rbp+8h] BYREF

  if ( __TSS0__1__IsSettingsAgentAllowedByPolicy_FeatureEnablement_SystemSettings__YA_NXZ_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 4LL) )
  {
    Init_thread_header(&__TSS0__1__IsSettingsAgentAllowedByPolicy_FeatureEnablement_SystemSettings__YA_NXZ_4HA);
    if ( __TSS0__1__IsSettingsAgentAllowedByPolicy_FeatureEnablement_SystemSettings__YA_NXZ_4HA == -1 )
    {
      v1 = 1;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57359072>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57359072>::GetImpl'::`2'::impl) )
      {
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        v4 = 0;
        if ( (int)((__int64 (__fastcall *)(const wchar_t *, const wchar_t *, __m128i *, __int64 *))PolicyManager_GetPolicy)(
                    L"WindowsAI",
                    L"DisableSettingsAgent",
                    &si128,
                    &v4) >= 0
          && *(_DWORD *)(v4 + 8) == 1 )
        {
          v1 = *(_DWORD *)(v4 + 16) == 0;
        }
        wil::details::unique_storage<wil::details::resource_policy<PMPolicyRetrievedInfo *,long (*)(PMPolicyRetrievedInfo *),&long PolicyManager_FreeGetPolicyData(PMPolicyRetrievedInfo *),wistd::integral_constant<unsigned __int64,0>,PMPolicyRetrievedInfo *,PMPolicyRetrievedInfo *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<PMPolicyRetrievedInfo *,long (*)(PMPolicyRetrievedInfo *),&long PolicyManager_FreeGetPolicyData(PMPolicyRetrievedInfo *),wistd::integral_constant<unsigned __int64,0>,PMPolicyRetrievedInfo *,PMPolicyRetrievedInfo *,0,std::nullptr_t>>(&v4);
      }
      `SystemSettings::FeatureEnablement::IsSettingsAgentAllowedByPolicy'::`2'::s_isSettingsAgentAllowedByPolicy = v1;
      Init_thread_footer(&__TSS0__1__IsSettingsAgentAllowedByPolicy_FeatureEnablement_SystemSettings__YA_NXZ_4HA);
    }
  }
  return `SystemSettings::FeatureEnablement::IsSettingsAgentAllowedByPolicy'::`2'::s_isSettingsAgentAllowedByPolicy;
}

```

## disassembly

```asm
0x18001919c  push    rbx
0x18001919e  sub     rsp, 30h
0x1800191a2  mov     ecx, cs:_tls_index
0x1800191a8  mov     rax, gs:58h
0x1800191b1  mov     edx, 4
0x1800191b6  mov     rax, [rax+rcx*8]
0x1800191ba  mov     eax, [rdx+rax]
0x1800191bd  cmp     cs:?$TSS0@?1??IsSettingsAgentAllowedByPolicy@FeatureEnablement@SystemSettings@@YA_NXZ@4HA, eax
0x1800191c3  jle     loc_18001925A
0x1800191c9  lea     rcx, ?$TSS0@?1??IsSettingsAgentAllowedByPolicy@FeatureEnablement@SystemSettings@@YA_NXZ@4HA
0x1800191d0  call    _Init_thread_header
0x1800191d5  cmp     cs:?$TSS0@?1??IsSettingsAgentAllowedByPolicy@FeatureEnablement@SystemSettings@@YA_NXZ@4HA, 0FFFFFFFFh
0x1800191dc  jnz     short loc_18001925A
0x1800191de  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57359072@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57359072@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57359072> `wil::Feature<__WilFeatureTraits_Feature_57359072>::GetImpl(void)'::`2'::impl
0x1800191e5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_57359072@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57359072>::__private_IsEnabled(void)
0x1800191ea  mov     ebx, 1
0x1800191ef  test    al, al
0x1800191f1  jz      short loc_180019248
0x1800191f3  movdqa  xmm0, cs:__xmm@00000000000000000000000200000001
0x1800191fb  movdqu  [rsp+38h+var_18], xmm0
0x180019201  mov     [rsp+38h+arg_0], 0
0x18001920a  lea     r9, [rsp+38h+arg_0]
0x18001920f  lea     r8, [rsp+38h+var_18]
0x180019214  lea     rdx, aDisablesetting; "DisableSettingsAgent"
0x18001921b  lea     rcx, aWindowsai; "WindowsAI"
0x180019222  call    cs:__imp_PolicyManager_GetPolicy
0x180019228  test    eax, eax
0x18001922a  js      short loc_18001923E
0x18001922c  mov     rax, [rsp+38h+arg_0]
0x180019231  cmp     [rax+8], ebx
0x180019234  jnz     short loc_18001923E
0x180019236  cmp     dword ptr [rax+10h], 0
0x18001923a  jz      short loc_18001923E
0x18001923c  xor     bl, bl
0x18001923e  lea     rcx, [rsp+38h+arg_0]
0x180019243  call    ??1?$unique_storage@U?$resource_policy@PEAUPMPolicyRetrievedInfo@@P6AJPEAU1@@Z$1?PolicyManager_FreeGetPolicyData@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<PMPolicyRetrievedInfo *,long (*)(PMPolicyRetrievedInfo *),&PolicyManager_FreeGetPolicyData(PMPolicyRetrievedInfo *),wistd::integral_constant<unsigned __int64,0>,PMPolicyRetrievedInfo *,PMPolicyRetrievedInfo *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<PMPolicyRetrievedInfo *,long (*)(PMPolicyRetrievedInfo *),&PolicyManager_FreeGetPolicyData(PMPolicyRetrievedInfo *),wistd::integral_constant<unsigned __int64,0>,PMPolicyRetrievedInfo *,PMPolicyRetrievedInfo *,0,std::nullptr_t>>(void)
0x180019248  mov     cs:?s_isSettingsAgentAllowedByPolicy@?1??IsSettingsAgentAllowedByPolicy@FeatureEnablement@SystemSettings@@YA_NXZ@4_NA, bl; bool `SystemSettings::FeatureEnablement::IsSettingsAgentAllowedByPolicy(void)'::`2'::s_isSettingsAgentAllowedByPolicy
0x18001924e  lea     rcx, ?$TSS0@?1??IsSettingsAgentAllowedByPolicy@FeatureEnablement@SystemSettings@@YA_NXZ@4HA
0x180019255  call    _Init_thread_footer
0x18001925a  mov     al, cs:?s_isSettingsAgentAllowedByPolicy@?1??IsSettingsAgentAllowedByPolicy@FeatureEnablement@SystemSettings@@YA_NXZ@4_NA; bool `SystemSettings::FeatureEnablement::IsSettingsAgentAllowedByPolicy(void)'::`2'::s_isSettingsAgentAllowedByPolicy
0x180019260  add     rsp, 30h
0x180019264  pop     rbx
0x180019265  retn
```
