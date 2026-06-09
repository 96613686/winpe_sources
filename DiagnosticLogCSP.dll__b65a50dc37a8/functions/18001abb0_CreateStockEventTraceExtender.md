# CreateStockEventTraceExtender

- ea: `0x18001abb0`
- end: `0x18001ae35`
- name: `CreateStockEventTraceExtender`
- size: `645`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1800173ac`
- `0x18001ae3c`

## callees

- `0x18001641c`
- `0x1800165dc`
- `0x18001abb0`
- `0x18001d5ec`
- `0x180023844`
- `0x18002913c`
- `0x18002b1c4`
- `0x18002cf08`
- `0x18002f374`
- `0x1800306f4`
- `0x18003126c`
- `0x180031fa4`

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
0x18001abb0  cmp     dword ptr [rcx], 1D6CD37Ch
0x18001abb6  jnz     short loc_18001ABED
0x18001abb8  mov     eax, dword ptr cs:_GUID_1d6cd37c_977e_40d6_b05b_f06423d16f5d.Data2
0x18001abbe  cmp     [rcx+4], eax
0x18001abc1  jnz     loc_18001AE2F
0x18001abc7  mov     eax, dword ptr cs:_GUID_1d6cd37c_977e_40d6_b05b_f06423d16f5d.Data4
0x18001abcd  cmp     [rcx+8], eax
0x18001abd0  jnz     loc_18001AE2F
0x18001abd6  mov     eax, dword ptr cs:_GUID_1d6cd37c_977e_40d6_b05b_f06423d16f5d.Data4+4
0x18001abdc  cmp     [rcx+0Ch], eax
0x18001abdf  jnz     loc_18001AE2F
0x18001abe5  mov     r8, r9
0x18001abe8  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCTraceHeadersEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x18001abed  cmp     dword ptr [rcx], 8105C558h
0x18001abf3  jnz     short loc_18001AC2A
0x18001abf5  mov     eax, dword ptr cs:_GUID_8105c558_9a6b_4ea1_b0f4_ac6ae1fa0eea.Data2
0x18001abfb  cmp     [rcx+4], eax
0x18001abfe  jnz     loc_18001AE2F
0x18001ac04  mov     eax, dword ptr cs:_GUID_8105c558_9a6b_4ea1_b0f4_ac6ae1fa0eea.Data4
0x18001ac0a  cmp     [rcx+8], eax
0x18001ac0d  jnz     loc_18001AE2F
0x18001ac13  mov     eax, dword ptr cs:_GUID_8105c558_9a6b_4ea1_b0f4_ac6ae1fa0eea.Data4+4
0x18001ac19  cmp     [rcx+0Ch], eax
0x18001ac1c  jnz     loc_18001AE2F
0x18001ac22  mov     r8, r9
0x18001ac25  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCCoreRepeaterEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x18001ac2a  cmp     dword ptr [rcx], 0B620D9A6h
0x18001ac30  jnz     short loc_18001AC67
0x18001ac32  mov     eax, dword ptr cs:_GUID_b620d9a6_a01e_4afb_aa0a_d8b9400360b2.Data2
0x18001ac38  cmp     [rcx+4], eax
0x18001ac3b  jnz     loc_18001AE2F
0x18001ac41  mov     eax, dword ptr cs:_GUID_b620d9a6_a01e_4afb_aa0a_d8b9400360b2.Data4
0x18001ac47  cmp     [rcx+8], eax
0x18001ac4a  jnz     loc_18001AE2F
0x18001ac50  mov     eax, dword ptr cs:_GUID_b620d9a6_a01e_4afb_aa0a_d8b9400360b2.Data4+4
0x18001ac56  cmp     [rcx+0Ch], eax
0x18001ac59  jnz     loc_18001AE2F
0x18001ac5f  mov     r8, r9
0x18001ac62  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCBuildInfoEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x18001ac67  cmp     dword ptr [rcx], 0B33AC241h
0x18001ac6d  jnz     short loc_18001ACA4
0x18001ac6f  mov     eax, dword ptr cs:_GUID_b33ac241_a192_42b7_ac0c_d828ab6ccb25.Data2
0x18001ac75  cmp     [rcx+4], eax
0x18001ac78  jnz     loc_18001AE2F
0x18001ac7e  mov     eax, dword ptr cs:_GUID_b33ac241_a192_42b7_ac0c_d828ab6ccb25.Data4
0x18001ac84  cmp     [rcx+8], eax
0x18001ac87  jnz     loc_18001AE2F
0x18001ac8d  mov     eax, dword ptr cs:_GUID_b33ac241_a192_42b7_ac0c_d828ab6ccb25.Data4+4
0x18001ac93  cmp     [rcx+0Ch], eax
0x18001ac96  jnz     loc_18001AE2F
0x18001ac9c  mov     r8, r9
0x18001ac9f  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCImageIdEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x18001aca4  cmp     dword ptr [rcx], 0AA981571h
0x18001acaa  jnz     short loc_18001ACE1
0x18001acac  mov     eax, dword ptr cs:_GUID_aa981571_9628_42e8_a132_74c040a6fff2.Data2
0x18001acb2  cmp     [rcx+4], eax
0x18001acb5  jnz     loc_18001AE2F
0x18001acbb  mov     eax, dword ptr cs:_GUID_aa981571_9628_42e8_a132_74c040a6fff2.Data4
0x18001acc1  cmp     [rcx+8], eax
0x18001acc4  jnz     loc_18001AE2F
0x18001acca  mov     eax, dword ptr cs:_GUID_aa981571_9628_42e8_a132_74c040a6fff2.Data4+4
0x18001acd0  cmp     [rcx+0Ch], eax
0x18001acd3  jnz     loc_18001AE2F
0x18001acd9  mov     r8, r9
0x18001acdc  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCNGenEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x18001ace1  cmp     dword ptr [rcx], 0CF8B21Ch
0x18001ace7  jnz     short loc_18001AD1E
0x18001ace9  mov     eax, dword ptr cs:_GUID_0cf8b21c_b9e5_49ce_96ec_66b5ffcf3a2e.Data2
0x18001acef  cmp     [rcx+4], eax
0x18001acf2  jnz     loc_18001AE2F
0x18001acf8  mov     eax, dword ptr cs:_GUID_0cf8b21c_b9e5_49ce_96ec_66b5ffcf3a2e.Data4
0x18001acfe  cmp     [rcx+8], eax
0x18001ad01  jnz     loc_18001AE2F
0x18001ad07  mov     eax, dword ptr cs:_GUID_0cf8b21c_b9e5_49ce_96ec_66b5ffcf3a2e.Data4+4
0x18001ad0d  cmp     [rcx+0Ch], eax
0x18001ad10  jnz     loc_18001AE2F
0x18001ad16  mov     r8, r9
0x18001ad19  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCVolumeMappingEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x18001ad1e  cmp     dword ptr [rcx], 40C4F4F6h
0x18001ad24  jnz     short loc_18001AD5B
0x18001ad26  mov     eax, dword ptr cs:_GUID_40c4f4f6_c9ce_4ffc_b848_4300311f1ac7.Data2
0x18001ad2c  cmp     [rcx+4], eax
0x18001ad2f  jnz     loc_18001AE2F
0x18001ad35  mov     eax, dword ptr cs:_GUID_40c4f4f6_c9ce_4ffc_b848_4300311f1ac7.Data4
0x18001ad3b  cmp     [rcx+8], eax
0x18001ad3e  jnz     loc_18001AE2F
0x18001ad44  mov     eax, dword ptr cs:_GUID_40c4f4f6_c9ce_4ffc_b848_4300311f1ac7.Data4+4
0x18001ad4a  cmp     [rcx+0Ch], eax
0x18001ad4d  jnz     loc_18001AE2F
0x18001ad53  mov     r8, r9
0x18001ad56  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x18001ad5b  cmp     dword ptr [rcx], 0AD4F7AB3h
0x18001ad61  jnz     short loc_18001AD98
0x18001ad63  mov     eax, dword ptr cs:_GUID_ad4f7ab3_bcda_4e6c_97c3_e999be858295.Data2
0x18001ad69  cmp     [rcx+4], eax
0x18001ad6c  jnz     loc_18001AE2F
0x18001ad72  mov     eax, dword ptr cs:_GUID_ad4f7ab3_bcda_4e6c_97c3_e999be858295.Data4
0x18001ad78  cmp     [rcx+8], eax
0x18001ad7b  jnz     loc_18001AE2F
0x18001ad81  mov     eax, dword ptr cs:_GUID_ad4f7ab3_bcda_4e6c_97c3_e999be858295.Data4+4
0x18001ad87  cmp     [rcx+0Ch], eax
0x18001ad8a  jnz     loc_18001AE2F
0x18001ad90  mov     r8, r9
0x18001ad93  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x18001ad98  cmp     dword ptr [rcx], 164122F2h
0x18001ad9e  jnz     short loc_18001ADCD
0x18001ada0  mov     eax, dword ptr cs:_GUID_164122f2_1705_40f8_9bb0_5692e8aa677a.Data2
0x18001ada6  cmp     [rcx+4], eax
0x18001ada9  jnz     loc_18001AE2F
0x18001adaf  mov     eax, dword ptr cs:_GUID_164122f2_1705_40f8_9bb0_5692e8aa677a.Data4
0x18001adb5  cmp     [rcx+8], eax
0x18001adb8  jnz     short loc_18001AE2F
0x18001adba  mov     eax, dword ptr cs:_GUID_164122f2_1705_40f8_9bb0_5692e8aa677a.Data4+4
0x18001adc0  cmp     [rcx+0Ch], eax
0x18001adc3  jnz     short loc_18001AE2F
0x18001adc5  mov     r8, r9
0x18001adc8  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCWinSATEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x18001adcd  cmp     dword ptr [rcx], 88B342B3h
0x18001add3  jnz     short loc_18001ADFE
0x18001add5  mov     eax, dword ptr cs:_GUID_88b342b3_e1b7_4ef3_95c2_664ce0d294d8.Data2
0x18001addb  cmp     [rcx+4], eax
0x18001adde  jnz     short loc_18001AE2F
0x18001ade0  mov     eax, dword ptr cs:_GUID_88b342b3_e1b7_4ef3_95c2_664ce0d294d8.Data4
0x18001ade6  cmp     [rcx+8], eax
0x18001ade9  jnz     short loc_18001AE2F
0x18001adeb  mov     eax, dword ptr cs:_GUID_88b342b3_e1b7_4ef3_95c2_664ce0d294d8.Data4+4
0x18001adf1  cmp     [rcx+0Ch], eax
0x18001adf4  jnz     short loc_18001AE2F
0x18001adf6  mov     r8, r9
0x18001adf9  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCNetworkInterfaceEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x18001adfe  cmp     dword ptr [rcx], 109FA25Dh
0x18001ae04  jnz     short loc_18001AE2F
0x18001ae06  mov     eax, dword ptr cs:_GUID_109fa25d_d55e_4acd_b170_340b8194720e.Data2
0x18001ae0c  cmp     [rcx+4], eax
0x18001ae0f  jnz     short loc_18001AE2F
0x18001ae11  mov     eax, dword ptr cs:_GUID_109fa25d_d55e_4acd_b170_340b8194720e.Data4
0x18001ae17  cmp     [rcx+8], eax
0x18001ae1a  jnz     short loc_18001AE2F
0x18001ae1c  mov     eax, dword ptr cs:_GUID_109fa25d_d55e_4acd_b170_340b8194720e.Data4+4
0x18001ae22  cmp     [rcx+0Ch], eax
0x18001ae25  jnz     short loc_18001AE2F
0x18001ae27  mov     r8, r9
0x18001ae2a  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCElfImageEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x18001ae2f  mov     eax, 80040111h
0x18001ae34  retn
```
