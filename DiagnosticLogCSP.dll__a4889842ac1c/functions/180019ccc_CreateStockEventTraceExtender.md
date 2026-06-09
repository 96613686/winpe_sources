# CreateStockEventTraceExtender

- ea: `0x180019ccc`
- end: `0x180019f51`
- name: `CreateStockEventTraceExtender`
- size: `645`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1800167e0`
- `0x180019f58`

## callees

- `0x180015898`
- `0x180015a58`
- `0x180019ccc`
- `0x18001c6d8`
- `0x1800228a4`
- `0x180027f40`
- `0x180029f44`
- `0x18002bbf4`
- `0x18002df44`
- `0x18002f2e4`
- `0x18002fdf8`
- `0x180030a94`

## pseudocode

```c
__int64 __fastcall CreateStockEventTraceExtender(_DWORD *a1, __int64 a2, __int64 a3, _QWORD *a4)
{
  switch ( *a1 )
  {
    case 0x1D6CD37C:
      if ( a1[1] == *(_DWORD *)&GUID_1d6cd37c_977e_40d6_b05b_f06423d16f5d.Data2
        && a1[2] == *(_DWORD *)GUID_1d6cd37c_977e_40d6_b05b_f06423d16f5d.Data4
        && a1[3] == *(_DWORD *)&GUID_1d6cd37c_977e_40d6_b05b_f06423d16f5d.Data4[4] )
      {
        return ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>>::CreateInstance(
                 (__int64)a1,
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
                 (__int64)a1,
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
                 (__int64)a1,
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
                 (__int64)a1,
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
                 (__int64)a1,
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
                 (__int64)a1,
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
                 (__int64)a1,
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
                 (__int64)a1,
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
                 (__int64)a1,
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
                 (__int64)a1,
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
                 (__int64)a1,
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
0x180019ccc  cmp     dword ptr [rcx], 1D6CD37Ch
0x180019cd2  jnz     short loc_180019D09
0x180019cd4  mov     eax, dword ptr cs:_GUID_1d6cd37c_977e_40d6_b05b_f06423d16f5d.Data2
0x180019cda  cmp     [rcx+4], eax
0x180019cdd  jnz     loc_180019F4B
0x180019ce3  mov     eax, dword ptr cs:_GUID_1d6cd37c_977e_40d6_b05b_f06423d16f5d.Data4
0x180019ce9  cmp     [rcx+8], eax
0x180019cec  jnz     loc_180019F4B
0x180019cf2  mov     eax, dword ptr cs:_GUID_1d6cd37c_977e_40d6_b05b_f06423d16f5d.Data4+4
0x180019cf8  cmp     [rcx+0Ch], eax
0x180019cfb  jnz     loc_180019F4B
0x180019d01  mov     r8, r9
0x180019d04  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCTraceHeadersEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x180019d09  cmp     dword ptr [rcx], 8105C558h
0x180019d0f  jnz     short loc_180019D46
0x180019d11  mov     eax, dword ptr cs:_GUID_8105c558_9a6b_4ea1_b0f4_ac6ae1fa0eea.Data2
0x180019d17  cmp     [rcx+4], eax
0x180019d1a  jnz     loc_180019F4B
0x180019d20  mov     eax, dword ptr cs:_GUID_8105c558_9a6b_4ea1_b0f4_ac6ae1fa0eea.Data4
0x180019d26  cmp     [rcx+8], eax
0x180019d29  jnz     loc_180019F4B
0x180019d2f  mov     eax, dword ptr cs:_GUID_8105c558_9a6b_4ea1_b0f4_ac6ae1fa0eea.Data4+4
0x180019d35  cmp     [rcx+0Ch], eax
0x180019d38  jnz     loc_180019F4B
0x180019d3e  mov     r8, r9
0x180019d41  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCCoreRepeaterEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x180019d46  cmp     dword ptr [rcx], 0B620D9A6h
0x180019d4c  jnz     short loc_180019D83
0x180019d4e  mov     eax, dword ptr cs:_GUID_b620d9a6_a01e_4afb_aa0a_d8b9400360b2.Data2
0x180019d54  cmp     [rcx+4], eax
0x180019d57  jnz     loc_180019F4B
0x180019d5d  mov     eax, dword ptr cs:_GUID_b620d9a6_a01e_4afb_aa0a_d8b9400360b2.Data4
0x180019d63  cmp     [rcx+8], eax
0x180019d66  jnz     loc_180019F4B
0x180019d6c  mov     eax, dword ptr cs:_GUID_b620d9a6_a01e_4afb_aa0a_d8b9400360b2.Data4+4
0x180019d72  cmp     [rcx+0Ch], eax
0x180019d75  jnz     loc_180019F4B
0x180019d7b  mov     r8, r9
0x180019d7e  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCBuildInfoEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x180019d83  cmp     dword ptr [rcx], 0B33AC241h
0x180019d89  jnz     short loc_180019DC0
0x180019d8b  mov     eax, dword ptr cs:_GUID_b33ac241_a192_42b7_ac0c_d828ab6ccb25.Data2
0x180019d91  cmp     [rcx+4], eax
0x180019d94  jnz     loc_180019F4B
0x180019d9a  mov     eax, dword ptr cs:_GUID_b33ac241_a192_42b7_ac0c_d828ab6ccb25.Data4
0x180019da0  cmp     [rcx+8], eax
0x180019da3  jnz     loc_180019F4B
0x180019da9  mov     eax, dword ptr cs:_GUID_b33ac241_a192_42b7_ac0c_d828ab6ccb25.Data4+4
0x180019daf  cmp     [rcx+0Ch], eax
0x180019db2  jnz     loc_180019F4B
0x180019db8  mov     r8, r9
0x180019dbb  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCImageIdEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x180019dc0  cmp     dword ptr [rcx], 0AA981571h
0x180019dc6  jnz     short loc_180019DFD
0x180019dc8  mov     eax, dword ptr cs:_GUID_aa981571_9628_42e8_a132_74c040a6fff2.Data2
0x180019dce  cmp     [rcx+4], eax
0x180019dd1  jnz     loc_180019F4B
0x180019dd7  mov     eax, dword ptr cs:_GUID_aa981571_9628_42e8_a132_74c040a6fff2.Data4
0x180019ddd  cmp     [rcx+8], eax
0x180019de0  jnz     loc_180019F4B
0x180019de6  mov     eax, dword ptr cs:_GUID_aa981571_9628_42e8_a132_74c040a6fff2.Data4+4
0x180019dec  cmp     [rcx+0Ch], eax
0x180019def  jnz     loc_180019F4B
0x180019df5  mov     r8, r9
0x180019df8  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCNGenEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x180019dfd  cmp     dword ptr [rcx], 0CF8B21Ch
0x180019e03  jnz     short loc_180019E3A
0x180019e05  mov     eax, dword ptr cs:_GUID_0cf8b21c_b9e5_49ce_96ec_66b5ffcf3a2e.Data2
0x180019e0b  cmp     [rcx+4], eax
0x180019e0e  jnz     loc_180019F4B
0x180019e14  mov     eax, dword ptr cs:_GUID_0cf8b21c_b9e5_49ce_96ec_66b5ffcf3a2e.Data4
0x180019e1a  cmp     [rcx+8], eax
0x180019e1d  jnz     loc_180019F4B
0x180019e23  mov     eax, dword ptr cs:_GUID_0cf8b21c_b9e5_49ce_96ec_66b5ffcf3a2e.Data4+4
0x180019e29  cmp     [rcx+0Ch], eax
0x180019e2c  jnz     loc_180019F4B
0x180019e32  mov     r8, r9
0x180019e35  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCVolumeMappingEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x180019e3a  cmp     dword ptr [rcx], 40C4F4F6h
0x180019e40  jnz     short loc_180019E77
0x180019e42  mov     eax, dword ptr cs:_GUID_40c4f4f6_c9ce_4ffc_b848_4300311f1ac7.Data2
0x180019e48  cmp     [rcx+4], eax
0x180019e4b  jnz     loc_180019F4B
0x180019e51  mov     eax, dword ptr cs:_GUID_40c4f4f6_c9ce_4ffc_b848_4300311f1ac7.Data4
0x180019e57  cmp     [rcx+8], eax
0x180019e5a  jnz     loc_180019F4B
0x180019e60  mov     eax, dword ptr cs:_GUID_40c4f4f6_c9ce_4ffc_b848_4300311f1ac7.Data4+4
0x180019e66  cmp     [rcx+0Ch], eax
0x180019e69  jnz     loc_180019F4B
0x180019e6f  mov     r8, r9
0x180019e72  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x180019e77  cmp     dword ptr [rcx], 0AD4F7AB3h
0x180019e7d  jnz     short loc_180019EB4
0x180019e7f  mov     eax, dword ptr cs:_GUID_ad4f7ab3_bcda_4e6c_97c3_e999be858295.Data2
0x180019e85  cmp     [rcx+4], eax
0x180019e88  jnz     loc_180019F4B
0x180019e8e  mov     eax, dword ptr cs:_GUID_ad4f7ab3_bcda_4e6c_97c3_e999be858295.Data4
0x180019e94  cmp     [rcx+8], eax
0x180019e97  jnz     loc_180019F4B
0x180019e9d  mov     eax, dword ptr cs:_GUID_ad4f7ab3_bcda_4e6c_97c3_e999be858295.Data4+4
0x180019ea3  cmp     [rcx+0Ch], eax
0x180019ea6  jnz     loc_180019F4B
0x180019eac  mov     r8, r9
0x180019eaf  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x180019eb4  cmp     dword ptr [rcx], 164122F2h
0x180019eba  jnz     short loc_180019EE9
0x180019ebc  mov     eax, dword ptr cs:_GUID_164122f2_1705_40f8_9bb0_5692e8aa677a.Data2
0x180019ec2  cmp     [rcx+4], eax
0x180019ec5  jnz     loc_180019F4B
0x180019ecb  mov     eax, dword ptr cs:_GUID_164122f2_1705_40f8_9bb0_5692e8aa677a.Data4
0x180019ed1  cmp     [rcx+8], eax
0x180019ed4  jnz     short loc_180019F4B
0x180019ed6  mov     eax, dword ptr cs:_GUID_164122f2_1705_40f8_9bb0_5692e8aa677a.Data4+4
0x180019edc  cmp     [rcx+0Ch], eax
0x180019edf  jnz     short loc_180019F4B
0x180019ee1  mov     r8, r9
0x180019ee4  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCWinSATEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x180019ee9  cmp     dword ptr [rcx], 88B342B3h
0x180019eef  jnz     short loc_180019F1A
0x180019ef1  mov     eax, dword ptr cs:_GUID_88b342b3_e1b7_4ef3_95c2_664ce0d294d8.Data2
0x180019ef7  cmp     [rcx+4], eax
0x180019efa  jnz     short loc_180019F4B
0x180019efc  mov     eax, dword ptr cs:_GUID_88b342b3_e1b7_4ef3_95c2_664ce0d294d8.Data4
0x180019f02  cmp     [rcx+8], eax
0x180019f05  jnz     short loc_180019F4B
0x180019f07  mov     eax, dword ptr cs:_GUID_88b342b3_e1b7_4ef3_95c2_664ce0d294d8.Data4+4
0x180019f0d  cmp     [rcx+0Ch], eax
0x180019f10  jnz     short loc_180019F4B
0x180019f12  mov     r8, r9
0x180019f15  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCNetworkInterfaceEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x180019f1a  cmp     dword ptr [rcx], 109FA25Dh
0x180019f20  jnz     short loc_180019F4B
0x180019f22  mov     eax, dword ptr cs:_GUID_109fa25d_d55e_4acd_b170_340b8194720e.Data2
0x180019f28  cmp     [rcx+4], eax
0x180019f2b  jnz     short loc_180019F4B
0x180019f2d  mov     eax, dword ptr cs:_GUID_109fa25d_d55e_4acd_b170_340b8194720e.Data4
0x180019f33  cmp     [rcx+8], eax
0x180019f36  jnz     short loc_180019F4B
0x180019f38  mov     eax, dword ptr cs:_GUID_109fa25d_d55e_4acd_b170_340b8194720e.Data4+4
0x180019f3e  cmp     [rcx+0Ch], eax
0x180019f41  jnz     short loc_180019F4B
0x180019f43  mov     r8, r9
0x180019f46  jmp     ?CreateInstance@?$CComCreator@V?$CComObject@VCElfImageEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)
0x180019f4b  mov     eax, 80040111h
0x180019f50  retn
```
