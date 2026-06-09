# CreateStockEventTraceExtender

- ea: `0x18000447c`
- end: `0x18000469d`
- name: `CreateStockEventTraceExtender`
- size: `545`
- prototype: `__int64 __fastcall(_DWORD *, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180002af0`
- `0x180004b5c`

## callees

- `0x18000447c`
- `0x1800058d0`
- `0x1800059bc`
- `0x180008a18`
- `0x18000dc84`
- `0x180015b98`
- `0x180017074`
- `0x180019690`
- `0x18001dab4`
- `0x18001ea44`
- `0x18001ede4`
- `0x1800231a8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CreateStockEventTraceExtender(_DWORD *a1, __int64 a2, __int64 a3, __int64 a4)
{
  if ( *a1 == 493671292
    && a1[1] == *(_DWORD *)&GUID_1d6cd37c_977e_40d6_b05b_f06423d16f5d.Data2
    && a1[2] == *(_DWORD *)GUID_1d6cd37c_977e_40d6_b05b_f06423d16f5d.Data4
    && a1[3] == *(_DWORD *)&GUID_1d6cd37c_977e_40d6_b05b_f06423d16f5d.Data4[4] )
  {
    return ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>>::CreateInstance(
             a1,
             a2,
             a4);
  }
  if ( *a1 == -2130328232
    && a1[1] == *(_DWORD *)&GUID_8105c558_9a6b_4ea1_b0f4_ac6ae1fa0eea.Data2
    && a1[2] == *(_DWORD *)GUID_8105c558_9a6b_4ea1_b0f4_ac6ae1fa0eea.Data4
    && a1[3] == *(_DWORD *)&GUID_8105c558_9a6b_4ea1_b0f4_ac6ae1fa0eea.Data4[4] )
  {
    return ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>>::CreateInstance(
             a1,
             a2,
             a4);
  }
  if ( *a1 == -1239361114
    && a1[1] == *(_DWORD *)&GUID_b620d9a6_a01e_4afb_aa0a_d8b9400360b2.Data2
    && a1[2] == *(_DWORD *)GUID_b620d9a6_a01e_4afb_aa0a_d8b9400360b2.Data4
    && a1[3] == *(_DWORD *)&GUID_b620d9a6_a01e_4afb_aa0a_d8b9400360b2.Data4[4] )
  {
    return ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>>::CreateInstance(
             a1,
             a2,
             a4);
  }
  if ( *a1 == -1287994815
    && a1[1] == *(_DWORD *)&GUID_b33ac241_a192_42b7_ac0c_d828ab6ccb25.Data2
    && a1[2] == *(_DWORD *)GUID_b33ac241_a192_42b7_ac0c_d828ab6ccb25.Data4
    && a1[3] == *(_DWORD *)&GUID_b33ac241_a192_42b7_ac0c_d828ab6ccb25.Data4[4] )
  {
    return ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>>::CreateInstance(
             a1,
             a2,
             a4);
  }
  if ( *a1 == -1432873615
    && a1[1] == *(_DWORD *)&GUID_aa981571_9628_42e8_a132_74c040a6fff2.Data2
    && a1[2] == *(_DWORD *)GUID_aa981571_9628_42e8_a132_74c040a6fff2.Data4
    && a1[3] == *(_DWORD *)&GUID_aa981571_9628_42e8_a132_74c040a6fff2.Data4[4] )
  {
    return ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>>::CreateInstance(
             a1,
             a2,
             a4);
  }
  if ( *a1 == 217625116
    && a1[1] == *(_DWORD *)&GUID_0cf8b21c_b9e5_49ce_96ec_66b5ffcf3a2e.Data2
    && a1[2] == *(_DWORD *)GUID_0cf8b21c_b9e5_49ce_96ec_66b5ffcf3a2e.Data4
    && a1[3] == *(_DWORD *)&GUID_0cf8b21c_b9e5_49ce_96ec_66b5ffcf3a2e.Data4[4] )
  {
    return ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>>::CreateInstance(
             a1,
             a2,
             a4);
  }
  if ( *a1 == 1086649590
    && a1[1] == *(_DWORD *)&GUID_40c4f4f6_c9ce_4ffc_b848_4300311f1ac7.Data2
    && a1[2] == *(_DWORD *)GUID_40c4f4f6_c9ce_4ffc_b848_4300311f1ac7.Data4
    && a1[3] == *(_DWORD *)&GUID_40c4f4f6_c9ce_4ffc_b848_4300311f1ac7.Data4[4] )
  {
    return ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>>::CreateInstance(
             a1,
             a2,
             a4);
  }
  if ( *a1 == -1387300173
    && a1[1] == *(_DWORD *)&GUID_ad4f7ab3_bcda_4e6c_97c3_e999be858295.Data2
    && a1[2] == *(_DWORD *)GUID_ad4f7ab3_bcda_4e6c_97c3_e999be858295.Data4
    && a1[3] == *(_DWORD *)&GUID_ad4f7ab3_bcda_4e6c_97c3_e999be858295.Data4[4] )
  {
    return ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>>::CreateInstance(
             a1,
             a2,
             a4);
  }
  if ( *a1 == 373367538
    && a1[1] == *(_DWORD *)&GUID_164122f2_1705_40f8_9bb0_5692e8aa677a.Data2
    && a1[2] == *(_DWORD *)GUID_164122f2_1705_40f8_9bb0_5692e8aa677a.Data4
    && a1[3] == *(_DWORD *)&GUID_164122f2_1705_40f8_9bb0_5692e8aa677a.Data4[4] )
  {
    return ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>>::CreateInstance(
             a1,
             a2,
             a4);
  }
  if ( *a1 == -2001517901
    && a1[1] == *(_DWORD *)&GUID_88b342b3_e1b7_4ef3_95c2_664ce0d294d8.Data2
    && a1[2] == *(_DWORD *)GUID_88b342b3_e1b7_4ef3_95c2_664ce0d294d8.Data4
    && a1[3] == *(_DWORD *)&GUID_88b342b3_e1b7_4ef3_95c2_664ce0d294d8.Data4[4] )
  {
    return ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>>::CreateInstance(
             a1,
             a2,
             a4);
  }
  if ( *a1 == 278897245
    && a1[1] == *(_DWORD *)&GUID_109fa25d_d55e_4acd_b170_340b8194720e.Data2
    && a1[2] == *(_DWORD *)GUID_109fa25d_d55e_4acd_b170_340b8194720e.Data4
    && a1[3] == *(_DWORD *)&GUID_109fa25d_d55e_4acd_b170_340b8194720e.Data4[4] )
  {
    return ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>>::CreateInstance(
             a1,
             a2,
             a4);
  }
  return 2147746065LL;
}

```

## disassembly

```asm
0x18000447c  cmp     dword ptr [rcx], 1D6CD37Ch
0x180004482  jnz     short loc_1800044AD
0x180004484  mov     eax, dword ptr cs:_GUID_1d6cd37c_977e_40d6_b05b_f06423d16f5d.Data2
0x18000448a  cmp     [rcx+4], eax
0x18000448d  jnz     short loc_1800044AD
0x18000448f  mov     eax, dword ptr cs:_GUID_1d6cd37c_977e_40d6_b05b_f06423d16f5d.Data4
0x180004495  cmp     [rcx+8], eax
0x180004498  jnz     short loc_1800044AD
0x18000449a  mov     eax, dword ptr cs:_GUID_1d6cd37c_977e_40d6_b05b_f06423d16f5d.Data4+4
0x1800044a0  cmp     [rcx+0Ch], eax
0x1800044a3  jnz     short loc_1800044AD
0x1800044a5  mov     r8, r9
0x1800044a8  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCTraceHeadersEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x1800044ad  cmp     dword ptr [rcx], 8105C558h
0x1800044b3  jnz     short loc_1800044DE
0x1800044b5  mov     eax, dword ptr cs:_GUID_8105c558_9a6b_4ea1_b0f4_ac6ae1fa0eea.Data2
0x1800044bb  cmp     [rcx+4], eax
0x1800044be  jnz     short loc_1800044DE
0x1800044c0  mov     eax, dword ptr cs:_GUID_8105c558_9a6b_4ea1_b0f4_ac6ae1fa0eea.Data4
0x1800044c6  cmp     [rcx+8], eax
0x1800044c9  jnz     short loc_1800044DE
0x1800044cb  mov     eax, dword ptr cs:_GUID_8105c558_9a6b_4ea1_b0f4_ac6ae1fa0eea.Data4+4
0x1800044d1  cmp     [rcx+0Ch], eax
0x1800044d4  jnz     short loc_1800044DE
0x1800044d6  mov     r8, r9
0x1800044d9  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCCoreRepeaterEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x1800044de  cmp     dword ptr [rcx], 0B620D9A6h
0x1800044e4  jnz     short loc_18000450F
0x1800044e6  mov     eax, dword ptr cs:_GUID_b620d9a6_a01e_4afb_aa0a_d8b9400360b2.Data2
0x1800044ec  cmp     [rcx+4], eax
0x1800044ef  jnz     short loc_18000450F
0x1800044f1  mov     eax, dword ptr cs:_GUID_b620d9a6_a01e_4afb_aa0a_d8b9400360b2.Data4
0x1800044f7  cmp     [rcx+8], eax
0x1800044fa  jnz     short loc_18000450F
0x1800044fc  mov     eax, dword ptr cs:_GUID_b620d9a6_a01e_4afb_aa0a_d8b9400360b2.Data4+4
0x180004502  cmp     [rcx+0Ch], eax
0x180004505  jnz     short loc_18000450F
0x180004507  mov     r8, r9
0x18000450a  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCBuildInfoEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x18000450f  cmp     dword ptr [rcx], 0B33AC241h
0x180004515  jnz     short loc_180004540
0x180004517  mov     eax, dword ptr cs:_GUID_b33ac241_a192_42b7_ac0c_d828ab6ccb25.Data2
0x18000451d  cmp     [rcx+4], eax
0x180004520  jnz     short loc_180004540
0x180004522  mov     eax, dword ptr cs:_GUID_b33ac241_a192_42b7_ac0c_d828ab6ccb25.Data4
0x180004528  cmp     [rcx+8], eax
0x18000452b  jnz     short loc_180004540
0x18000452d  mov     eax, dword ptr cs:_GUID_b33ac241_a192_42b7_ac0c_d828ab6ccb25.Data4+4
0x180004533  cmp     [rcx+0Ch], eax
0x180004536  jnz     short loc_180004540
0x180004538  mov     r8, r9
0x18000453b  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCImageIdEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x180004540  cmp     dword ptr [rcx], 0AA981571h
0x180004546  jnz     short loc_180004571
0x180004548  mov     eax, dword ptr cs:_GUID_aa981571_9628_42e8_a132_74c040a6fff2.Data2
0x18000454e  cmp     [rcx+4], eax
0x180004551  jnz     short loc_180004571
0x180004553  mov     eax, dword ptr cs:_GUID_aa981571_9628_42e8_a132_74c040a6fff2.Data4
0x180004559  cmp     [rcx+8], eax
0x18000455c  jnz     short loc_180004571
0x18000455e  mov     eax, dword ptr cs:_GUID_aa981571_9628_42e8_a132_74c040a6fff2.Data4+4
0x180004564  cmp     [rcx+0Ch], eax
0x180004567  jnz     short loc_180004571
0x180004569  mov     r8, r9
0x18000456c  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCNGenEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x180004571  cmp     dword ptr [rcx], 0CF8B21Ch
0x180004577  jnz     short loc_1800045A2
0x180004579  mov     eax, dword ptr cs:_GUID_0cf8b21c_b9e5_49ce_96ec_66b5ffcf3a2e.Data2
0x18000457f  cmp     [rcx+4], eax
0x180004582  jnz     short loc_1800045A2
0x180004584  mov     eax, dword ptr cs:_GUID_0cf8b21c_b9e5_49ce_96ec_66b5ffcf3a2e.Data4
0x18000458a  cmp     [rcx+8], eax
0x18000458d  jnz     short loc_1800045A2
0x18000458f  mov     eax, dword ptr cs:_GUID_0cf8b21c_b9e5_49ce_96ec_66b5ffcf3a2e.Data4+4
0x180004595  cmp     [rcx+0Ch], eax
0x180004598  jnz     short loc_1800045A2
0x18000459a  mov     r8, r9
0x18000459d  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCVolumeMappingEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x1800045a2  cmp     dword ptr [rcx], 40C4F4F6h
0x1800045a8  jnz     short loc_1800045D3
0x1800045aa  mov     eax, dword ptr cs:_GUID_40c4f4f6_c9ce_4ffc_b848_4300311f1ac7.Data2
0x1800045b0  cmp     [rcx+4], eax
0x1800045b3  jnz     short loc_1800045D3
0x1800045b5  mov     eax, dword ptr cs:_GUID_40c4f4f6_c9ce_4ffc_b848_4300311f1ac7.Data4
0x1800045bb  cmp     [rcx+8], eax
0x1800045be  jnz     short loc_1800045D3
0x1800045c0  mov     eax, dword ptr cs:_GUID_40c4f4f6_c9ce_4ffc_b848_4300311f1ac7.Data4+4
0x1800045c6  cmp     [rcx+0Ch], eax
0x1800045c9  jnz     short loc_1800045D3
0x1800045cb  mov     r8, r9
0x1800045ce  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x1800045d3  cmp     dword ptr [rcx], 0AD4F7AB3h
0x1800045d9  jnz     short loc_180004604
0x1800045db  mov     eax, dword ptr cs:_GUID_ad4f7ab3_bcda_4e6c_97c3_e999be858295.Data2
0x1800045e1  cmp     [rcx+4], eax
0x1800045e4  jnz     short loc_180004604
0x1800045e6  mov     eax, dword ptr cs:_GUID_ad4f7ab3_bcda_4e6c_97c3_e999be858295.Data4
0x1800045ec  cmp     [rcx+8], eax
0x1800045ef  jnz     short loc_180004604
0x1800045f1  mov     eax, dword ptr cs:_GUID_ad4f7ab3_bcda_4e6c_97c3_e999be858295.Data4+4
0x1800045f7  cmp     [rcx+0Ch], eax
0x1800045fa  jnz     short loc_180004604
0x1800045fc  mov     r8, r9
0x1800045ff  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x180004604  cmp     dword ptr [rcx], 164122F2h
0x18000460a  jnz     short loc_180004635
0x18000460c  mov     eax, dword ptr cs:_GUID_164122f2_1705_40f8_9bb0_5692e8aa677a.Data2
0x180004612  cmp     [rcx+4], eax
0x180004615  jnz     short loc_180004635
0x180004617  mov     eax, dword ptr cs:_GUID_164122f2_1705_40f8_9bb0_5692e8aa677a.Data4
0x18000461d  cmp     [rcx+8], eax
0x180004620  jnz     short loc_180004635
0x180004622  mov     eax, dword ptr cs:_GUID_164122f2_1705_40f8_9bb0_5692e8aa677a.Data4+4
0x180004628  cmp     [rcx+0Ch], eax
0x18000462b  jnz     short loc_180004635
0x18000462d  mov     r8, r9
0x180004630  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCWinSATEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x180004635  cmp     dword ptr [rcx], 88B342B3h
0x18000463b  jnz     short loc_180004666
0x18000463d  mov     eax, dword ptr cs:_GUID_88b342b3_e1b7_4ef3_95c2_664ce0d294d8.Data2
0x180004643  cmp     [rcx+4], eax
0x180004646  jnz     short loc_180004666
0x180004648  mov     eax, dword ptr cs:_GUID_88b342b3_e1b7_4ef3_95c2_664ce0d294d8.Data4
0x18000464e  cmp     [rcx+8], eax
0x180004651  jnz     short loc_180004666
0x180004653  mov     eax, dword ptr cs:_GUID_88b342b3_e1b7_4ef3_95c2_664ce0d294d8.Data4+4
0x180004659  cmp     [rcx+0Ch], eax
0x18000465c  jnz     short loc_180004666
0x18000465e  mov     r8, r9
0x180004661  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCNetworkInterfaceEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x180004666  cmp     dword ptr [rcx], 109FA25Dh
0x18000466c  jnz     short loc_180004697
0x18000466e  mov     eax, dword ptr cs:_GUID_109fa25d_d55e_4acd_b170_340b8194720e.Data2
0x180004674  cmp     [rcx+4], eax
0x180004677  jnz     short loc_180004697
0x180004679  mov     eax, dword ptr cs:_GUID_109fa25d_d55e_4acd_b170_340b8194720e.Data4
0x18000467f  cmp     [rcx+8], eax
0x180004682  jnz     short loc_180004697
0x180004684  mov     eax, dword ptr cs:_GUID_109fa25d_d55e_4acd_b170_340b8194720e.Data4+4
0x18000468a  cmp     [rcx+0Ch], eax
0x18000468d  jnz     short loc_180004697
0x18000468f  mov     r8, r9
0x180004692  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCElfImageEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x180004697  mov     eax, 80040111h
0x18000469c  retn
```
