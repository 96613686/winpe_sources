# SystemSettings::FeatureEnablement::IsSettingsAgentFeatureAllowedByEnterpriseControl(void)

- ea: `0x1800192e0`
- end: `0x180019340`
- name: `?IsSettingsAgentFeatureAllowedByEnterpriseControl@FeatureEnablement@SystemSettings@@YA_NXZ`
- size: `96`
- prototype: `char __fastcall(SystemSettings::FeatureEnablement *this)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x180012f68`
- `0x180018d58`

## callees

- `0x180002e88`
- `0x180002ef4`
- `0x180018ff4`
- `0x1800192e0`

## pseudocode

```c
char __fastcall SystemSettings::FeatureEnablement::IsSettingsAgentFeatureAllowedByEnterpriseControl(
        SystemSettings::FeatureEnablement *this)
{
  unsigned int v2; // ecx

  if ( __TSS0__1__IsSettingsAgentFeatureAllowedByEnterpriseControl_FeatureEnablement_SystemSettings__YA_NXZ_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 4LL) )
  {
    Init_thread_header(&__TSS0__1__IsSettingsAgentFeatureAllowedByEnterpriseControl_FeatureEnablement_SystemSettings__YA_NXZ_4HA);
    if ( __TSS0__1__IsSettingsAgentFeatureAllowedByEnterpriseControl_FeatureEnablement_SystemSettings__YA_NXZ_4HA == -1 )
    {
      `SystemSettings::FeatureEnablement::IsSettingsAgentFeatureAllowedByEnterpriseControl'::`2'::s_isSettingsAgentFeatureAllowedByEnterpriseControl = EnterpriseFeatureControl::IsFeatureEnabled(v2);
      Init_thread_footer(&__TSS0__1__IsSettingsAgentFeatureAllowedByEnterpriseControl_FeatureEnablement_SystemSettings__YA_NXZ_4HA);
    }
  }
  return `SystemSettings::FeatureEnablement::IsSettingsAgentFeatureAllowedByEnterpriseControl'::`2'::s_isSettingsAgentFeatureAllowedByEnterpriseControl;
}

```

## disassembly

```asm
0x1800192e0  sub     rsp, 28h
0x1800192e4  mov     ecx, cs:_tls_index
0x1800192ea  mov     rax, gs:58h
0x1800192f3  mov     edx, 4
0x1800192f8  mov     rax, [rax+rcx*8]
0x1800192fc  mov     eax, [rdx+rax]
0x1800192ff  cmp     cs:?$TSS0@?1??IsSettingsAgentFeatureAllowedByEnterpriseControl@FeatureEnablement@SystemSettings@@YA_NXZ@4HA, eax
0x180019305  jg      short loc_180019312
0x180019307  mov     al, cs:?s_isSettingsAgentFeatureAllowedByEnterpriseControl@?1??IsSettingsAgentFeatureAllowedByEnterpriseControl@FeatureEnablement@SystemSettings@@YA_NXZ@4_NA; bool `SystemSettings::FeatureEnablement::IsSettingsAgentFeatureAllowedByEnterpriseControl(void)'::`2'::s_isSettingsAgentFeatureAllowedByEnterpriseControl
0x18001930d  add     rsp, 28h
0x180019311  retn
0x180019312  lea     rcx, ?$TSS0@?1??IsSettingsAgentFeatureAllowedByEnterpriseControl@FeatureEnablement@SystemSettings@@YA_NXZ@4HA
0x180019319  call    _Init_thread_header
0x18001931e  cmp     cs:?$TSS0@?1??IsSettingsAgentFeatureAllowedByEnterpriseControl@FeatureEnablement@SystemSettings@@YA_NXZ@4HA, 0FFFFFFFFh
0x180019325  jnz     short loc_180019307
0x180019327  call    ?IsFeatureEnabled@EnterpriseFeatureControl@@SA_NK@Z; EnterpriseFeatureControl::IsFeatureEnabled(ulong)
0x18001932c  mov     cs:?s_isSettingsAgentFeatureAllowedByEnterpriseControl@?1??IsSettingsAgentFeatureAllowedByEnterpriseControl@FeatureEnablement@SystemSettings@@YA_NXZ@4_NA, al; bool `SystemSettings::FeatureEnablement::IsSettingsAgentFeatureAllowedByEnterpriseControl(void)'::`2'::s_isSettingsAgentFeatureAllowedByEnterpriseControl
0x180019332  lea     rcx, ?$TSS0@?1??IsSettingsAgentFeatureAllowedByEnterpriseControl@FeatureEnablement@SystemSettings@@YA_NXZ@4HA
0x180019339  call    _Init_thread_footer
0x18001933e  jmp     short loc_180019307
```
