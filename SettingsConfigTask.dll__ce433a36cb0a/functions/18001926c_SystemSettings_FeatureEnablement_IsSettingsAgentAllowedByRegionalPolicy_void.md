# SystemSettings::FeatureEnablement::IsSettingsAgentAllowedByRegionalPolicy(void)

- ea: `0x18001926c`
- end: `0x1800192d8`
- name: `?IsSettingsAgentAllowedByRegionalPolicy@FeatureEnablement@SystemSettings@@YA_NXZ`
- size: `108`
- prototype: `char __fastcall(SystemSettings::FeatureEnablement *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180013230`

## callees

- `0x180002e88`
- `0x180002ef4`
- `0x18001317c`
- `0x18001926c`
- `0x18001cf34`

## pseudocode

```c
char __fastcall SystemSettings::FeatureEnablement::IsSettingsAgentAllowedByRegionalPolicy(
        SystemSettings::FeatureEnablement *this)
{
  if ( __TSS0__1__IsSettingsAgentAllowedByRegionalPolicy_FeatureEnablement_SystemSettings__YA_NXZ_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 4LL) )
  {
    Init_thread_header(&__TSS0__1__IsSettingsAgentAllowedByRegionalPolicy_FeatureEnablement_SystemSettings__YA_NXZ_4HA);
    if ( __TSS0__1__IsSettingsAgentAllowedByRegionalPolicy_FeatureEnablement_SystemSettings__YA_NXZ_4HA == -1 )
    {
      `SystemSettings::FeatureEnablement::IsSettingsAgentAllowedByRegionalPolicy'::`2'::s_isSettingsAgentAllowedByRegionalPolicy = _lambda_9b1ed20268516391b0c52a30464c4be2_::operator()();
      Init_thread_footer(&__TSS0__1__IsSettingsAgentAllowedByRegionalPolicy_FeatureEnablement_SystemSettings__YA_NXZ_4HA);
    }
  }
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommandMultilingualSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CommandMultilingualSupport>::GetImpl'::`2'::impl);
  return `SystemSettings::FeatureEnablement::IsSettingsAgentAllowedByRegionalPolicy'::`2'::s_isSettingsAgentAllowedByRegionalPolicy;
}

```

## disassembly

```asm
0x18001926c  sub     rsp, 28h
0x180019270  mov     ecx, cs:_tls_index
0x180019276  mov     rax, gs:58h
0x18001927f  mov     edx, 4
0x180019284  mov     rax, [rax+rcx*8]
0x180019288  mov     eax, [rdx+rax]
0x18001928b  cmp     cs:?$TSS0@?1??IsSettingsAgentAllowedByRegionalPolicy@FeatureEnablement@SystemSettings@@YA_NXZ@4HA, eax
0x180019291  jg      short loc_1800192AA
0x180019293  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CommandMultilingualSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CommandMultilingualSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommandMultilingualSupport> `wil::Feature<__WilFeatureTraits_Feature_CommandMultilingualSupport>::GetImpl(void)'::`2'::impl
0x18001929a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CommandMultilingualSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommandMultilingualSupport>::__private_IsEnabled(void)
0x18001929f  mov     al, cs:?s_isSettingsAgentAllowedByRegionalPolicy@?1??IsSettingsAgentAllowedByRegionalPolicy@FeatureEnablement@SystemSettings@@YA_NXZ@4_NA; bool `SystemSettings::FeatureEnablement::IsSettingsAgentAllowedByRegionalPolicy(void)'::`2'::s_isSettingsAgentAllowedByRegionalPolicy
0x1800192a5  add     rsp, 28h
0x1800192a9  retn
0x1800192aa  lea     rcx, ?$TSS0@?1??IsSettingsAgentAllowedByRegionalPolicy@FeatureEnablement@SystemSettings@@YA_NXZ@4HA
0x1800192b1  call    _Init_thread_header
0x1800192b6  cmp     cs:?$TSS0@?1??IsSettingsAgentAllowedByRegionalPolicy@FeatureEnablement@SystemSettings@@YA_NXZ@4HA, 0FFFFFFFFh
0x1800192bd  jnz     short loc_180019293
0x1800192bf  call    ??R_lambda_9b1ed20268516391b0c52a30464c4be2_@@QEBA@XZ; _lambda_9b1ed20268516391b0c52a30464c4be2_::operator()(void)
0x1800192c4  mov     cs:?s_isSettingsAgentAllowedByRegionalPolicy@?1??IsSettingsAgentAllowedByRegionalPolicy@FeatureEnablement@SystemSettings@@YA_NXZ@4_NA, al; bool `SystemSettings::FeatureEnablement::IsSettingsAgentAllowedByRegionalPolicy(void)'::`2'::s_isSettingsAgentAllowedByRegionalPolicy
0x1800192ca  lea     rcx, ?$TSS0@?1??IsSettingsAgentAllowedByRegionalPolicy@FeatureEnablement@SystemSettings@@YA_NXZ@4HA
0x1800192d1  call    _Init_thread_footer
0x1800192d6  jmp     short loc_180019293
```
