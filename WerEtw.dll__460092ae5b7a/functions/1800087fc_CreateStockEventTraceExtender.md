# CreateStockEventTraceExtender

- ea: `0x1800087fc`
- end: `0x180008a81`
- name: `CreateStockEventTraceExtender`
- size: `645`
- prototype: `__int64 __fastcall(_DWORD *, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180005740`
- `0x180008a88`

## callees

- `0x180004808`
- `0x1800049c8`
- `0x1800087fc`
- `0x18000b6c8`
- `0x180011c74`
- `0x18001713c`
- `0x180019140`
- `0x18001c4ac`
- `0x1800209b4`
- `0x180021d44`
- `0x180022848`
- `0x180023434`

## pseudocode

```c
__int64 __fastcall CreateStockEventTraceExtender(_DWORD *a1, __int64 a2, __int64 a3, __int64 a4)
{
  switch ( *a1 )
  {
    case 0x1D6CD37C:
      if ( a1[1] == *(_DWORD *)&GUID_1d6cd37c_977e_40d6_b05b_f06423d16f5d.Data2
        && a1[2] == *(_DWORD *)GUID_1d6cd37c_977e_40d6_b05b_f06423d16f5d.Data4
        && a1[3] == *(_DWORD *)&GUID_1d6cd37c_977e_40d6_b05b_f06423d16f5d.Data4[4] )
      {
        return ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>>::CreateInstance(
                 a1,
                 a2,
                 a4);
      }
      break;
    case 0x8105C558:
      if ( a1[1] == *(_DWORD *)&GUID_8105c558_9a6b_4ea1_b0f4_ac6ae1fa0eea.Data2
        && a1[2] == *(_DWORD *)GUID_8105c558_9a6b_4ea1_b0f4_ac6ae1fa0eea.Data4
        && a1[3] == *(_DWORD *)&GUID_8105c558_9a6b_4ea1_b0f4_ac6ae1fa0eea.Data4[4] )
      {
        return ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>>::CreateInstance(
                 a1,
                 a2,
                 a4);
      }
      break;
    case 0xB620D9A6:
      if ( a1[1] == *(_DWORD *)&GUID_b620d9a6_a01e_4afb_aa0a_d8b9400360b2.Data2
        && a1[2] == *(_DWORD *)GUID_b620d9a6_a01e_4afb_aa0a_d8b9400360b2.Data4
        && a1[3] == *(_DWORD *)&GUID_b620d9a6_a01e_4afb_aa0a_d8b9400360b2.Data4[4] )
      {
        return ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>>::CreateInstance(
                 a1,
                 a2,
                 a4);
      }
      break;
    case 0xB33AC241:
      if ( a1[1] == *(_DWORD *)&GUID_b33ac241_a192_42b7_ac0c_d828ab6ccb25.Data2
        && a1[2] == *(_DWORD *)GUID_b33ac241_a192_42b7_ac0c_d828ab6ccb25.Data4
        && a1[3] == *(_DWORD *)&GUID_b33ac241_a192_42b7_ac0c_d828ab6ccb25.Data4[4] )
      {
        return ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>>::CreateInstance(
                 a1,
                 a2,
                 a4);
      }
      break;
    case 0xAA981571:
      if ( a1[1] == *(_DWORD *)&GUID_aa981571_9628_42e8_a132_74c040a6fff2.Data2
        && a1[2] == *(_DWORD *)GUID_aa981571_9628_42e8_a132_74c040a6fff2.Data4
        && a1[3] == *(_DWORD *)&GUID_aa981571_9628_42e8_a132_74c040a6fff2.Data4[4] )
      {
        return ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>>::CreateInstance(
                 a1,
                 a2,
                 a4);
      }
      break;
    case 0xCF8B21C:
      if ( a1[1] == *(_DWORD *)&GUID_0cf8b21c_b9e5_49ce_96ec_66b5ffcf3a2e.Data2
        && a1[2] == *(_DWORD *)GUID_0cf8b21c_b9e5_49ce_96ec_66b5ffcf3a2e.Data4
        && a1[3] == *(_DWORD *)&GUID_0cf8b21c_b9e5_49ce_96ec_66b5ffcf3a2e.Data4[4] )
      {
        return ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>>::CreateInstance(
                 a1,
                 a2,
                 a4);
      }
      break;
    case 0x40C4F4F6:
      if ( a1[1] == *(_DWORD *)&GUID_40c4f4f6_c9ce_4ffc_b848_4300311f1ac7.Data2
        && a1[2] == *(_DWORD *)GUID_40c4f4f6_c9ce_4ffc_b848_4300311f1ac7.Data4
        && a1[3] == *(_DWORD *)&GUID_40c4f4f6_c9ce_4ffc_b848_4300311f1ac7.Data4[4] )
      {
        return ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>>::CreateInstance(
                 a1,
                 a2,
                 a4);
      }
      break;
    case 0xAD4F7AB3:
      if ( a1[1] == *(_DWORD *)&GUID_ad4f7ab3_bcda_4e6c_97c3_e999be858295.Data2
        && a1[2] == *(_DWORD *)GUID_ad4f7ab3_bcda_4e6c_97c3_e999be858295.Data4
        && a1[3] == *(_DWORD *)&GUID_ad4f7ab3_bcda_4e6c_97c3_e999be858295.Data4[4] )
      {
        return ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>>::CreateInstance(
                 a1,
                 a2,
                 a4);
      }
      break;
    case 0x164122F2:
      if ( a1[1] == *(_DWORD *)&GUID_164122f2_1705_40f8_9bb0_5692e8aa677a.Data2
        && a1[2] == *(_DWORD *)GUID_164122f2_1705_40f8_9bb0_5692e8aa677a.Data4
        && a1[3] == *(_DWORD *)&GUID_164122f2_1705_40f8_9bb0_5692e8aa677a.Data4[4] )
      {
        return ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>>::CreateInstance(
                 a1,
                 a2,
                 a4);
      }
      break;
    case 0x88B342B3:
      if ( a1[1] == *(_DWORD *)&GUID_88b342b3_e1b7_4ef3_95c2_664ce0d294d8.Data2
        && a1[2] == *(_DWORD *)GUID_88b342b3_e1b7_4ef3_95c2_664ce0d294d8.Data4
        && a1[3] == *(_DWORD *)&GUID_88b342b3_e1b7_4ef3_95c2_664ce0d294d8.Data4[4] )
      {
        return ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>>::CreateInstance(
                 a1,
                 a2,
                 a4);
      }
      break;
    default:
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
      break;
  }
  return 2147746065LL;
}

```

## disassembly

```asm
0x1800087fc  cmp     dword ptr [rcx], 1D6CD37Ch
0x180008802  jnz     short loc_180008839
0x180008804  mov     eax, dword ptr cs:_GUID_1d6cd37c_977e_40d6_b05b_f06423d16f5d.Data2
0x18000880a  cmp     [rcx+4], eax
0x18000880d  jnz     loc_180008A7B
0x180008813  mov     eax, dword ptr cs:_GUID_1d6cd37c_977e_40d6_b05b_f06423d16f5d.Data4
0x180008819  cmp     [rcx+8], eax
0x18000881c  jnz     loc_180008A7B
0x180008822  mov     eax, dword ptr cs:_GUID_1d6cd37c_977e_40d6_b05b_f06423d16f5d.Data4+4
0x180008828  cmp     [rcx+0Ch], eax
0x18000882b  jnz     loc_180008A7B
0x180008831  mov     r8, r9
0x180008834  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCTraceHeadersEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x180008839  cmp     dword ptr [rcx], 8105C558h
0x18000883f  jnz     short loc_180008876
0x180008841  mov     eax, dword ptr cs:_GUID_8105c558_9a6b_4ea1_b0f4_ac6ae1fa0eea.Data2
0x180008847  cmp     [rcx+4], eax
0x18000884a  jnz     loc_180008A7B
0x180008850  mov     eax, dword ptr cs:_GUID_8105c558_9a6b_4ea1_b0f4_ac6ae1fa0eea.Data4
0x180008856  cmp     [rcx+8], eax
0x180008859  jnz     loc_180008A7B
0x18000885f  mov     eax, dword ptr cs:_GUID_8105c558_9a6b_4ea1_b0f4_ac6ae1fa0eea.Data4+4
0x180008865  cmp     [rcx+0Ch], eax
0x180008868  jnz     loc_180008A7B
0x18000886e  mov     r8, r9
0x180008871  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCCoreRepeaterEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x180008876  cmp     dword ptr [rcx], 0B620D9A6h
0x18000887c  jnz     short loc_1800088B3
0x18000887e  mov     eax, dword ptr cs:_GUID_b620d9a6_a01e_4afb_aa0a_d8b9400360b2.Data2
0x180008884  cmp     [rcx+4], eax
0x180008887  jnz     loc_180008A7B
0x18000888d  mov     eax, dword ptr cs:_GUID_b620d9a6_a01e_4afb_aa0a_d8b9400360b2.Data4
0x180008893  cmp     [rcx+8], eax
0x180008896  jnz     loc_180008A7B
0x18000889c  mov     eax, dword ptr cs:_GUID_b620d9a6_a01e_4afb_aa0a_d8b9400360b2.Data4+4
0x1800088a2  cmp     [rcx+0Ch], eax
0x1800088a5  jnz     loc_180008A7B
0x1800088ab  mov     r8, r9
0x1800088ae  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCBuildInfoEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x1800088b3  cmp     dword ptr [rcx], 0B33AC241h
0x1800088b9  jnz     short loc_1800088F0
0x1800088bb  mov     eax, dword ptr cs:_GUID_b33ac241_a192_42b7_ac0c_d828ab6ccb25.Data2
0x1800088c1  cmp     [rcx+4], eax
0x1800088c4  jnz     loc_180008A7B
0x1800088ca  mov     eax, dword ptr cs:_GUID_b33ac241_a192_42b7_ac0c_d828ab6ccb25.Data4
0x1800088d0  cmp     [rcx+8], eax
0x1800088d3  jnz     loc_180008A7B
0x1800088d9  mov     eax, dword ptr cs:_GUID_b33ac241_a192_42b7_ac0c_d828ab6ccb25.Data4+4
0x1800088df  cmp     [rcx+0Ch], eax
0x1800088e2  jnz     loc_180008A7B
0x1800088e8  mov     r8, r9
0x1800088eb  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCImageIdEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x1800088f0  cmp     dword ptr [rcx], 0AA981571h
0x1800088f6  jnz     short loc_18000892D
0x1800088f8  mov     eax, dword ptr cs:_GUID_aa981571_9628_42e8_a132_74c040a6fff2.Data2
0x1800088fe  cmp     [rcx+4], eax
0x180008901  jnz     loc_180008A7B
0x180008907  mov     eax, dword ptr cs:_GUID_aa981571_9628_42e8_a132_74c040a6fff2.Data4
0x18000890d  cmp     [rcx+8], eax
0x180008910  jnz     loc_180008A7B
0x180008916  mov     eax, dword ptr cs:_GUID_aa981571_9628_42e8_a132_74c040a6fff2.Data4+4
0x18000891c  cmp     [rcx+0Ch], eax
0x18000891f  jnz     loc_180008A7B
0x180008925  mov     r8, r9
0x180008928  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCNGenEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x18000892d  cmp     dword ptr [rcx], 0CF8B21Ch
0x180008933  jnz     short loc_18000896A
0x180008935  mov     eax, dword ptr cs:_GUID_0cf8b21c_b9e5_49ce_96ec_66b5ffcf3a2e.Data2
0x18000893b  cmp     [rcx+4], eax
0x18000893e  jnz     loc_180008A7B
0x180008944  mov     eax, dword ptr cs:_GUID_0cf8b21c_b9e5_49ce_96ec_66b5ffcf3a2e.Data4
0x18000894a  cmp     [rcx+8], eax
0x18000894d  jnz     loc_180008A7B
0x180008953  mov     eax, dword ptr cs:_GUID_0cf8b21c_b9e5_49ce_96ec_66b5ffcf3a2e.Data4+4
0x180008959  cmp     [rcx+0Ch], eax
0x18000895c  jnz     loc_180008A7B
0x180008962  mov     r8, r9
0x180008965  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCVolumeMappingEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x18000896a  cmp     dword ptr [rcx], 40C4F4F6h
0x180008970  jnz     short loc_1800089A7
0x180008972  mov     eax, dword ptr cs:_GUID_40c4f4f6_c9ce_4ffc_b848_4300311f1ac7.Data2
0x180008978  cmp     [rcx+4], eax
0x18000897b  jnz     loc_180008A7B
0x180008981  mov     eax, dword ptr cs:_GUID_40c4f4f6_c9ce_4ffc_b848_4300311f1ac7.Data4
0x180008987  cmp     [rcx+8], eax
0x18000898a  jnz     loc_180008A7B
0x180008990  mov     eax, dword ptr cs:_GUID_40c4f4f6_c9ce_4ffc_b848_4300311f1ac7.Data4+4
0x180008996  cmp     [rcx+0Ch], eax
0x180008999  jnz     loc_180008A7B
0x18000899f  mov     r8, r9
0x1800089a2  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x1800089a7  cmp     dword ptr [rcx], 0AD4F7AB3h
0x1800089ad  jnz     short loc_1800089E4
0x1800089af  mov     eax, dword ptr cs:_GUID_ad4f7ab3_bcda_4e6c_97c3_e999be858295.Data2
0x1800089b5  cmp     [rcx+4], eax
0x1800089b8  jnz     loc_180008A7B
0x1800089be  mov     eax, dword ptr cs:_GUID_ad4f7ab3_bcda_4e6c_97c3_e999be858295.Data4
0x1800089c4  cmp     [rcx+8], eax
0x1800089c7  jnz     loc_180008A7B
0x1800089cd  mov     eax, dword ptr cs:_GUID_ad4f7ab3_bcda_4e6c_97c3_e999be858295.Data4+4
0x1800089d3  cmp     [rcx+0Ch], eax
0x1800089d6  jnz     loc_180008A7B
0x1800089dc  mov     r8, r9
0x1800089df  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x1800089e4  cmp     dword ptr [rcx], 164122F2h
0x1800089ea  jnz     short loc_180008A19
0x1800089ec  mov     eax, dword ptr cs:_GUID_164122f2_1705_40f8_9bb0_5692e8aa677a.Data2
0x1800089f2  cmp     [rcx+4], eax
0x1800089f5  jnz     loc_180008A7B
0x1800089fb  mov     eax, dword ptr cs:_GUID_164122f2_1705_40f8_9bb0_5692e8aa677a.Data4
0x180008a01  cmp     [rcx+8], eax
0x180008a04  jnz     short loc_180008A7B
0x180008a06  mov     eax, dword ptr cs:_GUID_164122f2_1705_40f8_9bb0_5692e8aa677a.Data4+4
0x180008a0c  cmp     [rcx+0Ch], eax
0x180008a0f  jnz     short loc_180008A7B
0x180008a11  mov     r8, r9
0x180008a14  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCWinSATEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x180008a19  cmp     dword ptr [rcx], 88B342B3h
0x180008a1f  jnz     short loc_180008A4A
0x180008a21  mov     eax, dword ptr cs:_GUID_88b342b3_e1b7_4ef3_95c2_664ce0d294d8.Data2
0x180008a27  cmp     [rcx+4], eax
0x180008a2a  jnz     short loc_180008A7B
0x180008a2c  mov     eax, dword ptr cs:_GUID_88b342b3_e1b7_4ef3_95c2_664ce0d294d8.Data4
0x180008a32  cmp     [rcx+8], eax
0x180008a35  jnz     short loc_180008A7B
0x180008a37  mov     eax, dword ptr cs:_GUID_88b342b3_e1b7_4ef3_95c2_664ce0d294d8.Data4+4
0x180008a3d  cmp     [rcx+0Ch], eax
0x180008a40  jnz     short loc_180008A7B
0x180008a42  mov     r8, r9
0x180008a45  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCNetworkInterfaceEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x180008a4a  cmp     dword ptr [rcx], 109FA25Dh
0x180008a50  jnz     short loc_180008A7B
0x180008a52  mov     eax, dword ptr cs:_GUID_109fa25d_d55e_4acd_b170_340b8194720e.Data2
0x180008a58  cmp     [rcx+4], eax
0x180008a5b  jnz     short loc_180008A7B
0x180008a5d  mov     eax, dword ptr cs:_GUID_109fa25d_d55e_4acd_b170_340b8194720e.Data4
0x180008a63  cmp     [rcx+8], eax
0x180008a66  jnz     short loc_180008A7B
0x180008a68  mov     eax, dword ptr cs:_GUID_109fa25d_d55e_4acd_b170_340b8194720e.Data4+4
0x180008a6e  cmp     [rcx+0Ch], eax
0x180008a71  jnz     short loc_180008A7B
0x180008a73  mov     r8, r9
0x180008a76  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCElfImageEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x180008a7b  mov     eax, 80040111h
0x180008a80  retn
```
