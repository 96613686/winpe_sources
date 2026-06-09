# av_packet_side_data_name

- ea: `0x18000f530`
- end: `0x18000f75e`
- name: `av_packet_side_data_name`
- size: `558`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000f530`

## string_xrefs

- `0x18000f5c9`: `Audio Service Type`
- `0x18000f61a`: `Metadata Update`
- `0x18000f696`: `DOVI configuration record`

## pseudocode

```c
const char *__fastcall av_packet_side_data_name(int a1)
{
  int v1; // ecx
  int v2; // ecx
  int v3; // ecx
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  int v25; // ecx
  int v26; // ecx
  int v27; // ecx
  int v28; // ecx
  int v29; // ecx
  int v30; // ecx
  int v31; // ecx

  if ( a1 <= 20 )
  {
    if ( a1 == 20 )
      return "Mastering display metadata";
    if ( a1 > 10 )
    {
      v8 = a1 - 11;
      if ( !v8 )
        return "Skip Samples";
      v9 = v8 - 1;
      if ( !v9 )
        return "JP Dual Mono";
      v10 = v9 - 1;
      if ( !v10 )
        return "Strings Metadata";
      v11 = v10 - 1;
      if ( !v11 )
        return "Subtitle Position";
      v12 = v11 - 1;
      if ( !v12 )
        return "Matroska BlockAdditional";
      v13 = v12 - 1;
      if ( !v13 )
        return "WebVTT ID";
      v14 = v13 - 1;
      if ( !v14 )
        return "WebVTT Settings";
      v15 = v14 - 1;
      if ( !v15 )
        return "Metadata Update";
      if ( v15 == 1 )
        return "MPEGTS Stream ID";
    }
    else
    {
      if ( a1 == 10 )
        return "CPB properties";
      if ( a1 > 5 )
      {
        v5 = a1 - 6;
        if ( !v5 )
          return "Stereo 3D";
        v6 = v5 - 1;
        if ( !v6 )
          return "Audio Service Type";
        v7 = v6 - 1;
        if ( !v7 )
          return "Quality stats";
        if ( v7 == 1 )
          return "Fallback track";
      }
      else
      {
        if ( a1 == 5 )
          return "Display Matrix";
        if ( !a1 )
          return "Palette";
        v1 = a1 - 1;
        if ( !v1 )
          return "New Extradata";
        v2 = v1 - 1;
        if ( !v2 )
          return "Param Change";
        v3 = v2 - 1;
        if ( !v3 )
          return "H263 MB Info";
        if ( v3 == 1 )
          return "Replay Gain";
      }
    }
    return 0;
  }
  if ( a1 <= 30 )
  {
    if ( a1 == 30 )
      return "SMPTE ST 12-1:2014 timecode";
    v16 = a1 - 21;
    if ( !v16 )
      return "Spherical Mapping";
    v17 = v16 - 1;
    if ( !v17 )
      return "Content light level metadata";
    v18 = v17 - 1;
    if ( !v18 )
      return "A53 Closed Captions";
    v19 = v18 - 1;
    if ( !v19 )
      return "Encryption initialization data";
    v20 = v19 - 1;
    if ( !v20 )
      return "Encryption info";
    v21 = v20 - 1;
    if ( !v21 )
      return "Active Format Description data";
    v22 = v21 - 1;
    if ( !v22 )
      return "Producer Reference Time";
    v23 = v22 - 1;
    if ( !v23 )
      return "ICC Profile";
    if ( v23 == 1 )
      return "DOVI configuration record";
    return 0;
  }
  v24 = a1 - 31;
  if ( !v24 )
    return "HDR10+ Dynamic Metadata (SMPTE 2094-40)";
  v25 = v24 - 1;
  if ( !v25 )
    return "IAMF Mix Gain Parameter Data";
  v26 = v25 - 1;
  if ( !v26 )
    return "IAMF Demixing Info Parameter Data";
  v27 = v26 - 1;
  if ( !v27 )
    return "IAMF Recon Gain Info Parameter Data";
  v28 = v27 - 1;
  if ( !v28 )
    return "Ambient viewing environment";
  v29 = v28 - 1;
  if ( !v29 )
    return "Frame Cropping";
  v30 = v29 - 1;
  if ( !v30 )
    return "LCEVC NAL data";
  v31 = v30 - 1;
  if ( !v31 )
    return "3D Reference Displays Info";
  if ( v31 != 1 )
    return 0;
  return "RTCP Sender Report";
}

```

## disassembly

```asm
0x18000f530  cmp     ecx, 14h
0x18000f533  jg      loc_18000F662
0x18000f539  jz      loc_18000F65A
0x18000f53f  cmp     ecx, 0Ah
0x18000f542  jg      loc_18000F5E1
0x18000f548  jz      loc_18000F5D9
0x18000f54e  cmp     ecx, 5
0x18000f551  jg      short loc_18000F5A1
0x18000f553  jz      short loc_18000F599
0x18000f555  test    ecx, ecx
0x18000f557  jz      short loc_18000F591
0x18000f559  sub     ecx, 1
0x18000f55c  jz      short loc_18000F589
0x18000f55e  sub     ecx, 1
0x18000f561  jz      short loc_18000F581
0x18000f563  sub     ecx, 1
0x18000f566  jz      short loc_18000F579
0x18000f568  cmp     ecx, 1
0x18000f56b  jnz     loc_18000F713
0x18000f571  lea     rax, aReplayGain; "Replay Gain"
0x18000f578  retn
0x18000f579  lea     rax, aH263MbInfo; "H263 MB Info"
0x18000f580  retn
0x18000f581  lea     rax, aParamChange; "Param Change"
0x18000f588  retn
0x18000f589  lea     rax, aNewExtradata; "New Extradata"
0x18000f590  retn
0x18000f591  lea     rax, aPalette; "Palette"
0x18000f598  retn
0x18000f599  lea     rax, aDisplayMatrix; "Display Matrix"
0x18000f5a0  retn
0x18000f5a1  sub     ecx, 6
0x18000f5a4  jz      short loc_18000F5D1
0x18000f5a6  sub     ecx, 1
0x18000f5a9  jz      short loc_18000F5C9
0x18000f5ab  sub     ecx, 1
0x18000f5ae  jz      short loc_18000F5C1
0x18000f5b0  cmp     ecx, 1
0x18000f5b3  jnz     loc_18000F713
0x18000f5b9  lea     rax, aFallbackTrack; "Fallback track"
0x18000f5c0  retn
0x18000f5c1  lea     rax, aQualityStats; "Quality stats"
0x18000f5c8  retn
0x18000f5c9  lea     rax, aAudioServiceTy; "Audio Service Type"
0x18000f5d0  retn
0x18000f5d1  lea     rax, aStereo3d; "Stereo 3D"
0x18000f5d8  retn
0x18000f5d9  lea     rax, aCpbProperties; "CPB properties"
0x18000f5e0  retn
0x18000f5e1  sub     ecx, 0Bh
0x18000f5e4  jz      short loc_18000F652
0x18000f5e6  sub     ecx, 1
0x18000f5e9  jz      short loc_18000F64A
0x18000f5eb  sub     ecx, 1
0x18000f5ee  jz      short loc_18000F642
0x18000f5f0  sub     ecx, 1
0x18000f5f3  jz      short loc_18000F63A
0x18000f5f5  sub     ecx, 1
0x18000f5f8  jz      short loc_18000F632
0x18000f5fa  sub     ecx, 1
0x18000f5fd  jz      short loc_18000F62A
0x18000f5ff  sub     ecx, 1
0x18000f602  jz      short loc_18000F622
0x18000f604  sub     ecx, 1
0x18000f607  jz      short loc_18000F61A
0x18000f609  cmp     ecx, 1
0x18000f60c  jnz     loc_18000F713
0x18000f612  lea     rax, aMpegtsStreamId; "MPEGTS Stream ID"
0x18000f619  retn
0x18000f61a  lea     rax, aMetadataUpdate; "Metadata Update"
0x18000f621  retn
0x18000f622  lea     rax, aWebvttSettings; "WebVTT Settings"
0x18000f629  retn
0x18000f62a  lea     rax, aWebvttId; "WebVTT ID"
0x18000f631  retn
0x18000f632  lea     rax, aMatroskaBlocka; "Matroska BlockAdditional"
0x18000f639  retn
0x18000f63a  lea     rax, aSubtitlePositi; "Subtitle Position"
0x18000f641  retn
0x18000f642  lea     rax, aStringsMetadat; "Strings Metadata"
0x18000f649  retn
0x18000f64a  lea     rax, aJpDualMono; "JP Dual Mono"
0x18000f651  retn
0x18000f652  lea     rax, aSkipSamples; "Skip Samples"
0x18000f659  retn
0x18000f65a  lea     rax, aMasteringDispl; "Mastering display metadata"
0x18000f661  retn
0x18000f662  cmp     ecx, 1Eh
0x18000f665  jg      short loc_18000F6E6
0x18000f667  jz      short loc_18000F6DE
0x18000f669  sub     ecx, 15h
0x18000f66c  jz      short loc_18000F6D6
0x18000f66e  sub     ecx, 1
0x18000f671  jz      short loc_18000F6CE
0x18000f673  sub     ecx, 1
0x18000f676  jz      short loc_18000F6C6
0x18000f678  sub     ecx, 1
0x18000f67b  jz      short loc_18000F6BE
0x18000f67d  sub     ecx, 1
0x18000f680  jz      short loc_18000F6B6
0x18000f682  sub     ecx, 1
0x18000f685  jz      short loc_18000F6AE
0x18000f687  sub     ecx, 1
0x18000f68a  jz      short loc_18000F6A6
0x18000f68c  sub     ecx, 1
0x18000f68f  jz      short loc_18000F69E
0x18000f691  cmp     ecx, 1
0x18000f694  jnz     short loc_18000F713
0x18000f696  lea     rax, aDoviConfigurat; "DOVI configuration record"
0x18000f69d  retn
0x18000f69e  lea     rax, aIccProfile; "ICC Profile"
0x18000f6a5  retn
0x18000f6a6  lea     rax, aProducerRefere; "Producer Reference Time"
0x18000f6ad  retn
0x18000f6ae  lea     rax, aActiveFormatDe; "Active Format Description data"
0x18000f6b5  retn
0x18000f6b6  lea     rax, aEncryptionInfo; "Encryption info"
0x18000f6bd  retn
0x18000f6be  lea     rax, aEncryptionInit; "Encryption initialization data"
0x18000f6c5  retn
0x18000f6c6  lea     rax, aA53ClosedCapti; "A53 Closed Captions"
0x18000f6cd  retn
0x18000f6ce  lea     rax, aContentLightLe; "Content light level metadata"
0x18000f6d5  retn
0x18000f6d6  lea     rax, aSphericalMappi; "Spherical Mapping"
0x18000f6dd  retn
0x18000f6de  lea     rax, aSmpteSt1212014; "SMPTE ST 12-1:2014 timecode"
0x18000f6e5  retn
0x18000f6e6  sub     ecx, 1Fh
0x18000f6e9  jz      short loc_18000F756
0x18000f6eb  sub     ecx, 1
0x18000f6ee  jz      short loc_18000F74E
0x18000f6f0  sub     ecx, 1
0x18000f6f3  jz      short loc_18000F746
0x18000f6f5  sub     ecx, 1
0x18000f6f8  jz      short loc_18000F73E
0x18000f6fa  sub     ecx, 1
0x18000f6fd  jz      short loc_18000F736
0x18000f6ff  sub     ecx, 1
0x18000f702  jz      short loc_18000F72E
0x18000f704  sub     ecx, 1
0x18000f707  jz      short loc_18000F726
0x18000f709  sub     ecx, 1
0x18000f70c  jz      short loc_18000F71E
0x18000f70e  cmp     ecx, 1
0x18000f711  jz      short loc_18000F716
0x18000f713  xor     eax, eax
0x18000f715  retn
0x18000f716  lea     rax, aRtcpSenderRepo; "RTCP Sender Report"
0x18000f71d  retn
0x18000f71e  lea     rax, a3dReferenceDis; "3D Reference Displays Info"
0x18000f725  retn
0x18000f726  lea     rax, aLcevcNalData; "LCEVC NAL data"
0x18000f72d  retn
0x18000f72e  lea     rax, aFrameCropping; "Frame Cropping"
0x18000f735  retn
0x18000f736  lea     rax, aAmbientViewing; "Ambient viewing environment"
0x18000f73d  retn
0x18000f73e  lea     rax, aIamfReconGainI; "IAMF Recon Gain Info Parameter Data"
0x18000f745  retn
0x18000f746  lea     rax, aIamfDemixingIn; "IAMF Demixing Info Parameter Data"
0x18000f74d  retn
0x18000f74e  lea     rax, aIamfMixGainPar; "IAMF Mix Gain Parameter Data"
0x18000f755  retn
0x18000f756  lea     rax, aHdr10DynamicMe; "HDR10+ Dynamic Metadata (SMPTE 2094-40)"
0x18000f75d  retn
```
