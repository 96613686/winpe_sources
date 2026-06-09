# Microsoft::Windows::Autopilot::DirectDdsDownloadManagerBase::GetRegistryDownloadKey(ushort const *,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1800260b8`
- end: `0x1800261a0`
- name: `?GetRegistryDownloadKey@DirectDdsDownloadManagerBase@Autopilot@Windows@Microsoft@@SAJPEBG0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `232`
- prototype: `__int64 __fastcall(__int64, _WORD *, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800199e4`
- `0x18001b220`

## callees

- `0x1800098e7`
- `0x180013580`
- `0x1800192a4`
- `0x1800216e8`
- `0x1800260b8`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x1800260df`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800260df`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::DirectDdsDownloadManagerBase::GetRegistryDownloadKey(
        __int64 a1,
        _WORD *a2,
        __int64 a3)
{
  char v6; // al
  const wchar_t *v7; // rdx
  int StringValueFromRegistry; // eax
  __int64 v9; // rcx
  __int64 v10; // r8
  unsigned __int64 v11; // rdx
  char *v12; // rdi
  __int64 v13; // rbx
  const char *v14; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( `ZTPIsStateSeparationEnabled'::`2'::s_HasRun )
  {
    v6 = `ZTPIsStateSeparationEnabled'::`2'::s_Redirection;
  }
  else
  {
    v6 = (unsigned __int8)RtlIsStateSeparationEnabled(a1, a2) != 0;
    `ZTPIsStateSeparationEnabled'::`2'::s_Redirection = v6;
    `ZTPIsStateSeparationEnabled'::`2'::s_HasRun = 1;
  }
  v7 = L"OSData\\Software\\Microsoft\\Provisioning\\AutopilotSettings";
  if ( !v6 )
    v7 = (const wchar_t *)&stru_180039380;
  StringValueFromRegistry = Microsoft::Windows::Autopilot::AutoPilotStateUtils::ReadStringValueFromRegistry(
                              &stru_180039380,
                              v7,
                              a1,
                              a3);
  if ( StringValueFromRegistry < 0 )
  {
    if ( StringValueFromRegistry != -2147023727
      && (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 1) != 0 )
    {
      McTemplateU0dz_EventWriteTransfer(
        v9,
        AutopilotDownloadInvalidRegistryOverride,
        (unsigned int)StringValueFromRegistry,
        a1);
    }
    v11 = -1;
    do
      ++v11;
    while ( a2[v11] );
    if ( v11 > *(_QWORD *)(a3 + 24) )
    {
      try
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
          (char **)a3,
          v11,
          v10,
          a2);
      }
      catch ( ... )
      {
        return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                               retaddr,
                               (void *)0x95,
                               (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\directddsdownl"
                                             "oadmanagerbase.cpp",
                               v14);
      }
    }
    else
    {
      if ( *(_QWORD *)(a3 + 24) <= 7u )
        v12 = (char *)a3;
      else
        v12 = *(char **)a3;
      *(_QWORD *)(a3 + 16) = v11;
      v13 = 2 * v11;
      memmove_0(v12, a2, 2 * v11);
      *(_WORD *)&v12[v13] = 0;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800260b8  push    rbx
0x1800260ba  push    rsi
0x1800260bb  push    rdi
0x1800260bc  push    r14
0x1800260be  sub     rsp, 28h
0x1800260c2  mov     rbx, r8
0x1800260c5  mov     rsi, rdx
0x1800260c8  mov     rdi, rcx
0x1800260cb  xor     r14d, r14d
0x1800260ce  cmp     cs:?s_HasRun@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, r14b; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x1800260d5  jz      short loc_1800260DF
0x1800260d7  mov     al, cs:?s_Redirection@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x1800260dd  jmp     short loc_1800260FD
0x1800260df  call    cs:__imp_RtlIsStateSeparationEnabled
0x1800260e6  nop     dword ptr [rax+rax+00h]
0x1800260eb  test    al, al
0x1800260ed  setnz   al
0x1800260f0  mov     cs:?s_Redirection@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, al; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x1800260f6  mov     cs:?s_HasRun@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, 1; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x1800260fd  lea     rcx, stru_180039380
0x180026104  lea     rdx, aOsdataSoftware_2; "OSData\\Software\\Microsoft\\Provisioni"...
0x18002610b  test    al, al
0x18002610d  cmovz   rdx, rcx
0x180026111  mov     r9, rbx
0x180026114  mov     r8, rdi
0x180026117  call    ?ReadStringValueFromRegistry@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SAJPEAUHKEY__@@PEBG1AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::AutoPilotStateUtils::ReadStringValueFromRegistry(HKEY__ *,ushort const *,ushort const *,std::wstring &)
0x18002611c  test    eax, eax
0x18002611e  jns     short loc_18002618D
0x180026120  cmp     eax, 80070491h
0x180026125  jz      short loc_180026142
0x180026127  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 1
0x18002612e  jz      short loc_180026142
0x180026130  mov     r9, rdi
0x180026133  mov     r8d, eax
0x180026136  lea     rdx, AutopilotDownloadInvalidRegistryOverride
0x18002613d  call    McTemplateU0dz_EventWriteTransfer
0x180026142  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180026146  inc     rdx
0x180026149  cmp     [rsi+rdx*2], r14w
0x18002614e  jnz     short loc_180026146
0x180026150  cmp     rdx, [rbx+18h]
0x180026154  ja      short loc_180026182
0x180026156  cmp     qword ptr [rbx+18h], 7
0x18002615b  jbe     short loc_180026162
0x18002615d  mov     rdi, [rbx]
0x180026160  jmp     short loc_180026165
0x180026162  mov     rdi, rbx
0x180026165  mov     [rbx+10h], rdx
0x180026169  lea     rbx, [rdx+rdx]
0x18002616d  mov     r8, rbx; Size
0x180026170  mov     rdx, rsi; Src
0x180026173  mov     rcx, rdi; void *
0x180026176  call    memmove_0
0x18002617b  mov     [rbx+rdi], r14w
0x180026180  jmp     short loc_18002618D
0x180026182  mov     r9, rsi
0x180026185  mov     rcx, rbx
0x180026188  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18002618d  xor     eax, eax
0x18002618f  jmp     short loc_180026195
0x180026191  mov     eax, [rsp+48h+arg_0]
0x180026195  add     rsp, 28h
0x180026199  pop     r14
0x18002619b  pop     rdi
0x18002619c  pop     rsi
0x18002619d  pop     rbx
0x18002619e  retn
```
