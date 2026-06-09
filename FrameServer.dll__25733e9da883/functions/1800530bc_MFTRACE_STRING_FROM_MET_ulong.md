# MFTRACE_STRING_FROM_MET(ulong)

- ea: `0x1800530bc`
- end: `0x180053800`
- name: `?MFTRACE_STRING_FROM_MET@@YAPEBDK@Z`
- size: `1860`
- prototype: `const char *__fastcall(unsigned int)`
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18003d190`
- `0x18009cd78`
- `0x1800c017c`
- `0x1800c0d50`

## callees

- `0x1800530bc`

## string_xrefs

- `0x180053361`: `MEUpdatedStream`
- `0x180053465`: `MEStreamSinkFormatChanged`
- `0x18005345d`: `MEStreamSinkStopped`
- `0x1800533f0`: `MEStreamSinkStarted`
- `0x18005344d`: `MEStreamSinkRateChanged`
- `0x180053455`: `MEStreamSinkPaused`
- `0x180053445`: `MEStreamSinkRequestSample`
- `0x18005343d`: `MEStreamSinkMarker`
- `0x18005342d`: `MEStreamSinkScrubSampleComplete`
- `0x180053435`: `MEStreamSinkPrerolled`
- `0x180053492`: `MEAudioSessionDeviceRemoved`
- `0x1800534ba`: `MEStreamSinkDeviceChanged`
- `0x1800531b7`: `MESessionScrubSampleComplete`
- `0x180053708`: `MEPMPRemoveStream`
- `0x180053700`: `MEPMPTopologyCreated`
- `0x180053710`: `MEPMPDropToken`
- `0x18005353a`: `MEWMDRMLicenseBackupCompleted`
- `0x18005352a`: `MEWMDRMLicenseRestoreCompleted`
- `0x1800535cc`: `MEWMDRMLicenseAcquisitionCompleted`
- `0x180053250`: `MELicenseAcquisitionCompleted`
- `0x1800535c4`: `MEWMDRMIndividualizationCompleted`
- `0x180053240`: `MEIndividualizationCompleted`
- `0x180053230`: `MEEnablerCompleted`
- `0x1800535b4`: `MEWMDRMProximityCompleted`
- `0x180053282`: `MESessionStreamSinkFormatChanged`
- `0x1800535d4`: `METransformDrainComplete`
- `0x180053644`: `MEVideoCaptureDeviceRemoved`
- `0x180053634`: `MEStreamSinkFormatInvalidated`

## pseudocode

```c
const char *__fastcall MFTRACE_STRING_FROM_MET(unsigned int a1)
{
  unsigned int v1; // ecx
  unsigned int v2; // ecx
  unsigned int v3; // ecx
  unsigned int v4; // ecx
  unsigned int v5; // ecx
  unsigned int v6; // ecx
  const char *result; // rax
  unsigned int v8; // ecx
  unsigned int v9; // ecx
  unsigned int v10; // ecx
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  unsigned int v13; // ecx
  unsigned int v14; // ecx
  unsigned int v15; // ecx
  unsigned int v16; // ecx
  unsigned int v17; // ecx
  unsigned int v18; // ecx
  unsigned int v19; // ecx
  unsigned int v20; // ecx
  unsigned int v21; // ecx
  unsigned int v22; // ecx
  unsigned int v23; // ecx
  unsigned int v24; // ecx
  unsigned int v25; // ecx
  unsigned int v26; // ecx
  unsigned int v27; // ecx
  unsigned int v28; // ecx
  unsigned int v29; // ecx
  unsigned int v30; // ecx
  unsigned int v31; // ecx
  unsigned int v32; // ecx
  unsigned int v33; // ecx
  unsigned int v34; // ecx
  unsigned int v35; // ecx
  unsigned int v36; // ecx
  unsigned int v37; // ecx
  unsigned int v38; // ecx
  unsigned int v39; // ecx
  unsigned int v40; // ecx
  unsigned int v41; // ecx
  unsigned int v42; // ecx
  unsigned int v43; // ecx
  unsigned int v44; // ecx
  unsigned int v45; // ecx
  unsigned int v46; // ecx
  unsigned int v47; // ecx
  unsigned int v48; // ecx
  unsigned int v49; // ecx
  unsigned int v50; // ecx
  unsigned int v51; // ecx
  unsigned int v52; // ecx
  unsigned int v53; // ecx
  unsigned int v54; // ecx
  unsigned int v55; // ecx
  unsigned int v56; // ecx
  unsigned int v57; // ecx
  unsigned int v58; // ecx
  unsigned int v59; // ecx
  unsigned int v60; // ecx
  unsigned int v61; // ecx
  unsigned int v62; // ecx
  unsigned int v63; // ecx
  unsigned int v64; // ecx
  unsigned int v65; // ecx
  unsigned int v66; // ecx
  unsigned int v67; // ecx
  unsigned int v68; // ecx
  unsigned int v69; // ecx
  unsigned int v70; // ecx
  unsigned int v71; // ecx
  unsigned int v72; // ecx
  unsigned int v73; // ecx
  unsigned int v74; // ecx
  unsigned int v75; // ecx
  unsigned int v76; // ecx
  unsigned int v77; // ecx

  if ( a1 <= 0x13C )
  {
    if ( a1 == 316 )
      return "MEAudioSessionServerShutdown";
    if ( a1 > 0xCB )
    {
      if ( a1 > 0x12D )
      {
        if ( a1 > 0x135 )
        {
          v47 = a1 - 310;
          if ( !v47 )
            return "MEStreamSinkDeviceChanged";
          v48 = v47 - 1;
          if ( !v48 )
            return "MEQualityNotify";
          v49 = v48 - 1;
          if ( !v49 )
            return "MESinkInvalidated";
          v50 = v49 - 1;
          if ( !v50 )
            return "MEAudioSessionNameChanged";
          v51 = v50 - 1;
          if ( !v51 )
            return "MEAudioSessionVolumeChanged";
          if ( v51 == 1 )
            return "MEAudioSessionDeviceRemoved";
        }
        else
        {
          if ( a1 == 309 )
            return "MEStreamSinkFormatChanged";
          v41 = a1 - 302;
          if ( !v41 )
            return "MEStreamSinkStopped";
          v42 = v41 - 1;
          if ( !v42 )
            return "MEStreamSinkPaused";
          v43 = v42 - 1;
          if ( !v43 )
            return "MEStreamSinkRateChanged";
          v44 = v43 - 1;
          if ( !v44 )
            return "MEStreamSinkRequestSample";
          v45 = v44 - 1;
          if ( !v45 )
            return "MEStreamSinkMarker";
          v46 = v45 - 1;
          if ( !v46 )
            return "MEStreamSinkPrerolled";
          if ( v46 == 1 )
            return "MEStreamSinkScrubSampleComplete";
        }
      }
      else
      {
        if ( a1 == 301 )
          return "MEStreamSinkStarted";
        if ( a1 > 0xD5 )
        {
          v34 = a1 - 214;
          if ( !v34 )
            return "MEStreamTick";
          v35 = v34 - 1;
          if ( !v35 )
            return "MEStreamThinMode";
          v36 = v35 - 1;
          if ( !v36 )
            return "MEStreamFormatChanged";
          v37 = v36 - 1;
          if ( !v37 )
            return "MESourceRateChanged";
          v38 = v37 - 1;
          if ( !v38 )
            return "MEEndOfPresentationSegment";
          v39 = v38 - 1;
          if ( !v39 )
            return "MESourceCharacteristicsChanged";
          v40 = v39 - 1;
          if ( !v40 )
            return "MESourceRateChangeRequested";
          if ( v40 == 1 )
            return "MESourceMetadataChanged";
        }
        else
        {
          if ( a1 == 213 )
            return "MEMediaSample";
          v26 = a1 - 204;
          if ( !v26 )
            return "MEStreamSeeked";
          v27 = v26 - 1;
          if ( !v27 )
            return "MENewStream";
          v28 = v27 - 1;
          if ( !v28 )
            return "MEUpdatedStream";
          v29 = v28 - 1;
          if ( !v29 )
            return "MESourceStopped";
          v30 = v29 - 1;
          if ( !v30 )
            return "MEStreamStopped";
          v31 = v30 - 1;
          if ( !v31 )
            return "MESourcePaused";
          v32 = v31 - 1;
          if ( !v32 )
            return "MEStreamPaused";
          v33 = v32 - 1;
          if ( !v33 )
            return "MEEndOfPresentation";
          if ( v33 == 1 )
            return "MEEndOfStream";
        }
      }
    }
    else
    {
      if ( a1 == 203 )
        return "MESourceSeeked";
      if ( a1 > 0x72 )
      {
        if ( a1 > 0xC9 )
          return "MEStreamStarted";
        if ( a1 == 201 )
          return "MESourceStarted";
        if ( a1 > 0x7A )
        {
          v21 = a1 - 123;
          if ( !v21 )
            return "MEBufferingStopped";
          v22 = v21 - 1;
          if ( !v22 )
            return "MEConnectStart";
          v23 = v22 - 1;
          if ( !v23 )
            return "MEConnectEnd";
          v24 = v23 - 1;
          if ( !v24 )
            return "MEReconnectStart";
          v25 = v24 - 1;
          if ( !v25 )
            return "MEReconnectEnd";
          if ( v25 == 2 )
            return "MESessionStreamSinkFormatChanged";
        }
        else
        {
          if ( a1 == 122 )
            return "MEBufferingStarted";
          v15 = a1 - 115;
          if ( !v15 )
            return "MELicenseAcquisitionCompleted";
          v16 = v15 - 1;
          if ( !v16 )
            return "MEIndividualizationStart";
          v17 = v16 - 1;
          if ( !v17 )
            return "MEIndividualizationCompleted";
          v18 = v17 - 1;
          if ( !v18 )
            return "MEEnablerProgress";
          v19 = v18 - 1;
          if ( !v19 )
            return "MEEnablerCompleted";
          v20 = v19 - 1;
          if ( !v20 )
            return "MEPolicyError";
          if ( v20 == 1 )
            return "MEPolicyReport";
        }
      }
      else
      {
        if ( a1 == 114 )
          return "MELicenseAcquisitionStart";
        if ( a1 > 0x69 )
        {
          v8 = a1 - 106;
          if ( !v8 )
            return "MESessionClosed";
          v9 = v8 - 1;
          if ( !v9 )
            return "MESessionEnded";
          v10 = v9 - 1;
          if ( !v10 )
            return "MESessionRateChanged";
          v11 = v10 - 1;
          if ( !v11 )
            return "MESessionScrubSampleComplete";
          v12 = v11 - 1;
          if ( !v12 )
            return "MESessionCapabilitiesChanged";
          v13 = v12 - 1;
          if ( !v13 )
            return "MESessionTopologyStatus";
          v14 = v13 - 1;
          if ( !v14 )
            return "MESessionNotifyPresentationTime";
          if ( v14 == 1 )
            return "MENewPresentation";
        }
        else
        {
          if ( a1 == 105 )
            return "MESessionStopped";
          if ( !a1 )
            return "MEUnknown";
          v1 = a1 - 1;
          if ( !v1 )
            return "MEError";
          v2 = v1 - 1;
          if ( !v2 )
            return "MEExtendedType";
          v3 = v2 - 1;
          if ( !v3 )
            return "MENonFatalError";
          v4 = v3 - 98;
          if ( !v4 )
            return "MESessionTopologySet";
          v5 = v4 - 1;
          if ( !v5 )
            return "MESessionTopologiesCleared";
          v6 = v5 - 1;
          if ( !v6 )
            return "MESessionStarted";
          if ( v6 == 1 )
            return "MESessionPaused";
        }
      }
    }
    return "unknown event";
  }
  if ( a1 <= 0x2527 )
  {
    if ( a1 == 9511 )
      return "MEBitPumpScrubbed";
    if ( a1 > 0x25B )
    {
      if ( a1 > 0x251F )
      {
        v72 = a1 - 9504;
        if ( !v72 )
          return "MEMediaProcessorTopologyChanged";
        v73 = v72 - 1;
        if ( !v73 )
          return "MEBitPumpStarted";
        v74 = v73 - 1;
        if ( !v74 )
          return "MEBitPumpSeeked";
        v75 = v74 - 1;
        if ( !v75 )
          return "MEBitPumpPaused";
        v76 = v75 - 1;
        if ( !v76 )
          return "MEBitPumpPrerolled";
        v77 = v76 - 1;
        if ( !v77 )
          return "MEBitPumpStopped";
        if ( v77 == 1 )
          return "MEBitPumpEndOfStream";
      }
      else
      {
        if ( a1 == 9503 )
          return "MEMediaProcessorDropRequest";
        v65 = a1 - 604;
        if ( !v65 )
          return "METransformMarker";
        v66 = v65 - 1;
        if ( !v66 )
          return "METransformInputStreamStateChanged";
        v67 = v66 - 195;
        if ( !v67 )
          return "MEVideoCaptureDeviceRemoved";
        v68 = v67 - 1;
        if ( !v68 )
          return "MEVideoCaptureDevicePreempted";
        v69 = v68 - 1;
        if ( !v69 )
          return "MEStreamSinkFormatInvalidated";
        v70 = v69 - 1;
        if ( !v70 )
          return "MEEncodingParameters";
        v71 = v70 - 8698;
        if ( !v71 )
          return "MEMediaProcessorTopologySet";
        if ( v71 == 1 )
          return "MEMediaProcessorMarkout";
      }
    }
    else
    {
      if ( a1 == 603 )
        return "METransformDrainComplete";
      if ( a1 > 0x1F7 )
      {
        v59 = a1 - 506;
        if ( !v59 )
          return "MEWMDRMLicenseAcquisitionCompleted";
        v60 = v59 - 2;
        if ( !v60 )
          return "MEWMDRMIndividualizationCompleted";
        v61 = v60 - 5;
        if ( !v61 )
          return "MEWMDRMIndividualizationProgress";
        v62 = v61 - 1;
        if ( !v62 )
          return "MEWMDRMProximityCompleted";
        v63 = v62 - 1;
        if ( !v63 )
          return "MEWMDRMLicenseStoreCleaned";
        v64 = v63 - 86;
        if ( !v64 )
          return "METransformNeedInput";
        if ( v64 == 1 )
          return "METransformHaveOutput";
      }
      else
      {
        if ( a1 == 503 )
          return "MEWMDRMLicenseRestoreProgress";
        v52 = a1 - 317;
        if ( !v52 )
          return "MEAudioSessionGroupingParamChanged";
        v53 = v52 - 1;
        if ( !v53 )
          return "MEAudioSessionIconChanged";
        v54 = v53 - 83;
        if ( !v54 )
          return "MEPolicyChanged";
        v55 = v54 - 1;
        if ( !v55 )
          return "MEContentProtectionMessage";
        v56 = v55 - 1;
        if ( !v56 )
          return "MEPolicySet";
        v57 = v56 - 97;
        if ( !v57 )
          return "MEWMDRMLicenseBackupCompleted";
        v58 = v57 - 1;
        if ( !v58 )
          return "MEWMDRMLicenseBackupProgress";
        if ( v58 == 1 )
          return "MEWMDRMLicenseRestoreCompleted";
      }
    }
    return "unknown event";
  }
  switch ( a1 )
  {
    case 0x2528u:
      result = "MEBitPumpShutdown";
      break;
    case 0x252Au:
      result = "MEBitPumpEndOfSegment";
      break;
    case 0x252Bu:
      result = "MEPMPTopologyCreated";
      break;
    case 0x252Cu:
      result = "MEPMPRemoveStream";
      break;
    case 0x252Du:
      result = "MEPMPDropToken";
      break;
    case 0x252Eu:
      result = "MENetSessionUnknown";
      break;
    case 0x252Fu:
      result = "MENetSessionAuthenticate";
      break;
    case 0x2530u:
      result = "MENetSessionAuthorize";
      break;
    case 0x2531u:
      result = "MENetSessionUrlTransform";
      break;
    case 0x2532u:
      result = "MENetSessionProfiles";
      break;
    case 0x2533u:
      result = "MENetSessionCardeaLicenseRequest";
      break;
    case 0x2534u:
      result = "MENetSessionDownload";
      break;
    case 0x2535u:
      result = "MENetSessionDescribe";
      break;
    case 0x2536u:
      result = "MENetSessionSelectStreams";
      break;
    case 0x2537u:
      result = "MENetSessionPlay";
      break;
    case 0x2538u:
      result = "MENetSessionPause";
      break;
    case 0x2539u:
      result = "MENetSessionStop";
      break;
    case 0x253Bu:
      result = "MENetSessionClose";
      break;
    case 0x253Cu:
      result = "MENetSessionLog";
      break;
    case 0x253Du:
      result = "MENetSessionEos";
      break;
    case 0x253Eu:
      result = "MENetSessionAnnounce";
      break;
    case 0x253Fu:
      result = "MENetSessionChangeProfile";
      break;
    case 0x2540u:
      result = "MENetSessionSetHDCPContext";
      break;
    case 0x2541u:
      result = "MENetSessionChangeSurfaceProtection";
      break;
    case 0x2549u:
      result = "MENetSessionIDRRequest";
      break;
    case 0x254Bu:
      result = "MENetMonitorConnectorTypeChanged";
      break;
    case 0x254Cu:
      result = "MENetSessionAudioMuted";
      break;
    case 0x254Du:
      result = "MEHDCPAuthorizationStatus";
      break;
    case 0x254Eu:
      result = "MEHDCPEncryptionPaused";
      break;
    case 0x254Fu:
      result = "MEHDCPEncryptionResumed";
      break;
    case 0x2550u:
      result = "MEHDCPReauthenticating";
      break;
    case 0x2551u:
      result = "MEHDCPType1StreamBlocked";
      break;
    case 0x2552u:
      result = "MEHDCPDownstreamTopologyChanged";
      break;
    default:
      return "unknown event";
  }
  return result;
}

```

## disassembly

```asm
0x1800530bc  mov     eax, 13Ch
0x1800530c1  cmp     ecx, eax
0x1800530c3  ja      loc_1800534CA
0x1800530c9  jz      loc_1800534C2
0x1800530cf  mov     eax, 0CBh
0x1800530d4  cmp     ecx, eax
0x1800530d6  ja      loc_1800532DB
0x1800530dc  jz      loc_1800532D3
0x1800530e2  cmp     ecx, 72h ; 'r'
0x1800530e5  ja      loc_1800531DF
0x1800530eb  jz      loc_1800531D7
0x1800530f1  cmp     ecx, 69h ; 'i'
0x1800530f4  ja      short loc_18005316B
0x1800530f6  jz      short loc_180053163
0x1800530f8  test    ecx, ecx
0x1800530fa  jz      short loc_18005315B
0x1800530fc  sub     ecx, 1
0x1800530ff  jz      short loc_180053153
0x180053101  sub     ecx, 1
0x180053104  jz      short loc_18005314B
0x180053106  sub     ecx, 1
0x180053109  jz      short loc_180053143
0x18005310b  sub     ecx, 62h ; 'b'
0x18005310e  jz      short loc_18005313B
0x180053110  sub     ecx, 1
0x180053113  jz      short loc_180053133
0x180053115  sub     ecx, 1
0x180053118  jz      short loc_18005312B
0x18005311a  cmp     ecx, 1
0x18005311d  jnz     def_1800536EE; jumptable 00000001800536EE default case, cases 9513,9530,9538-9544,9546
0x180053123  lea     rax, aMesessionpause; "MESessionPaused"
0x18005312a  retn
0x18005312b  lea     rax, aMesessionstart; "MESessionStarted"
0x180053132  retn
0x180053133  lea     rax, aMesessiontopol; "MESessionTopologiesCleared"
0x18005313a  retn
0x18005313b  lea     rax, aMesessiontopol_0; "MESessionTopologySet"
0x180053142  retn
0x180053143  lea     rax, aMenonfatalerro; "MENonFatalError"
0x18005314a  retn
0x18005314b  lea     rax, aMeextendedtype; "MEExtendedType"
0x180053152  retn
0x180053153  lea     rax, aMeerror; "MEError"
0x18005315a  retn
0x18005315b  lea     rax, aMeunknown; "MEUnknown"
0x180053162  retn
0x180053163  lea     rax, aMesessionstopp; "MESessionStopped"
0x18005316a  retn
0x18005316b  sub     ecx, 6Ah ; 'j'
0x18005316e  jz      short loc_1800531CF
0x180053170  sub     ecx, 1
0x180053173  jz      short loc_1800531C7
0x180053175  sub     ecx, 1
0x180053178  jz      short loc_1800531BF
0x18005317a  sub     ecx, 1
0x18005317d  jz      short loc_1800531B7
0x18005317f  sub     ecx, 1
0x180053182  jz      short loc_1800531AF
0x180053184  sub     ecx, 1
0x180053187  jz      short loc_1800531A7
0x180053189  sub     ecx, 1
0x18005318c  jz      short loc_18005319F
0x18005318e  cmp     ecx, 1
0x180053191  jnz     def_1800536EE; jumptable 00000001800536EE default case, cases 9513,9530,9538-9544,9546
0x180053197  lea     rax, aMenewpresentat; "MENewPresentation"
0x18005319e  retn
0x18005319f  lea     rax, aMesessionnotif; "MESessionNotifyPresentationTime"
0x1800531a6  retn
0x1800531a7  lea     rax, aMesessiontopol_1; "MESessionTopologyStatus"
0x1800531ae  retn
0x1800531af  lea     rax, aMesessioncapab; "MESessionCapabilitiesChanged"
0x1800531b6  retn
0x1800531b7  lea     rax, aMesessionscrub; "MESessionScrubSampleComplete"
0x1800531be  retn
0x1800531bf  lea     rax, aMesessionratec; "MESessionRateChanged"
0x1800531c6  retn
0x1800531c7  lea     rax, aMesessionended; "MESessionEnded"
0x1800531ce  retn
0x1800531cf  lea     rax, aMesessionclose; "MESessionClosed"
0x1800531d6  retn
0x1800531d7  lea     rax, aMelicenseacqui_0; "MELicenseAcquisitionStart"
0x1800531de  retn
0x1800531df  mov     eax, 0C9h
0x1800531e4  cmp     ecx, eax
0x1800531e6  ja      loc_1800532BA
0x1800531ec  jz      loc_1800532B2
0x1800531f2  cmp     ecx, 7Ah ; 'z'
0x1800531f5  ja      short loc_180053260
0x1800531f7  jz      short loc_180053258
0x1800531f9  sub     ecx, 73h ; 's'
0x1800531fc  jz      short loc_180053250
0x1800531fe  sub     ecx, 1
0x180053201  jz      short loc_180053248
0x180053203  sub     ecx, 1
0x180053206  jz      short loc_180053240
0x180053208  sub     ecx, 1
0x18005320b  jz      short loc_180053238
0x18005320d  sub     ecx, 1
0x180053210  jz      short loc_180053230
0x180053212  sub     ecx, 1
0x180053215  jz      short loc_180053228
0x180053217  cmp     ecx, 1
0x18005321a  jnz     def_1800536EE; jumptable 00000001800536EE default case, cases 9513,9530,9538-9544,9546
0x180053220  lea     rax, aMepolicyreport; "MEPolicyReport"
0x180053227  retn
0x180053228  lea     rax, aMepolicyerror; "MEPolicyError"
0x18005322f  retn
0x180053230  lea     rax, aMeenablercompl; "MEEnablerCompleted"
0x180053237  retn
0x180053238  lea     rax, aMeenablerprogr; "MEEnablerProgress"
0x18005323f  retn
0x180053240  lea     rax, aMeindividualiz; "MEIndividualizationCompleted"
0x180053247  retn
0x180053248  lea     rax, aMeindividualiz_0; "MEIndividualizationStart"
0x18005324f  retn
0x180053250  lea     rax, aMelicenseacqui; "MELicenseAcquisitionCompleted"
0x180053257  retn
0x180053258  lea     rax, aMebufferingsta; "MEBufferingStarted"
0x18005325f  retn
0x180053260  sub     ecx, 7Bh ; '{'
0x180053263  jz      short loc_1800532AA
0x180053265  sub     ecx, 1
0x180053268  jz      short loc_1800532A2
0x18005326a  sub     ecx, 1
0x18005326d  jz      short loc_18005329A
0x18005326f  sub     ecx, 1
0x180053272  jz      short loc_180053292
0x180053274  sub     ecx, 1
0x180053277  jz      short loc_18005328A
0x180053279  cmp     ecx, 2
0x18005327c  jnz     def_1800536EE; jumptable 00000001800536EE default case, cases 9513,9530,9538-9544,9546
0x180053282  lea     rax, aMesessionstrea; "MESessionStreamSinkFormatChanged"
0x180053289  retn
0x18005328a  lea     rax, aMereconnectend; "MEReconnectEnd"
0x180053291  retn
0x180053292  lea     rax, aMereconnectsta; "MEReconnectStart"
0x180053299  retn
0x18005329a  lea     rax, aMeconnectend; "MEConnectEnd"
0x1800532a1  retn
0x1800532a2  lea     rax, aMeconnectstart; "MEConnectStart"
0x1800532a9  retn
0x1800532aa  lea     rax, aMebufferingsto; "MEBufferingStopped"
0x1800532b1  retn
0x1800532b2  lea     rax, aMesourcestarte; "MESourceStarted"
0x1800532b9  retn
0x1800532ba  cmp     ecx, 0CAh
0x1800532c0  lea     rdx, aMestreamstarte; "MEStreamStarted"
0x1800532c7  lea     rax, aUnknownEvent; "unknown event"
0x1800532ce  cmovz   rax, rdx
0x1800532d2  retn
0x1800532d3  lea     rax, aMesourceseeked; "MESourceSeeked"
0x1800532da  retn
0x1800532db  mov     eax, 12Dh
0x1800532e0  cmp     ecx, eax
0x1800532e2  ja      loc_1800533F8
0x1800532e8  jz      loc_1800533F0
0x1800532ee  mov     eax, 0D5h
0x1800532f3  cmp     ecx, eax
0x1800532f5  ja      loc_180053381
0x1800532fb  jz      short loc_180053379
0x1800532fd  sub     ecx, 0CCh
0x180053303  jz      short loc_180053371
0x180053305  sub     ecx, 1
0x180053308  jz      short loc_180053369
0x18005330a  sub     ecx, 1
0x18005330d  jz      short loc_180053361
0x18005330f  sub     ecx, 1
0x180053312  jz      short loc_180053359
0x180053314  sub     ecx, 1
0x180053317  jz      short loc_180053351
0x180053319  sub     ecx, 1
0x18005331c  jz      short loc_180053349
0x18005331e  sub     ecx, 1
0x180053321  jz      short loc_180053341
0x180053323  sub     ecx, 1
0x180053326  jz      short loc_180053339
0x180053328  cmp     ecx, 1
0x18005332b  jnz     def_1800536EE; jumptable 00000001800536EE default case, cases 9513,9530,9538-9544,9546
0x180053331  lea     rax, aMeendofstream; "MEEndOfStream"
0x180053338  retn
0x180053339  lea     rax, aMeendofpresent_0; "MEEndOfPresentation"
0x180053340  retn
0x180053341  lea     rax, aMestreampaused; "MEStreamPaused"
0x180053348  retn
0x180053349  lea     rax, aMesourcepaused; "MESourcePaused"
0x180053350  retn
0x180053351  lea     rax, aMestreamstoppe; "MEStreamStopped"
0x180053358  retn
0x180053359  lea     rax, aMesourcestoppe; "MESourceStopped"
0x180053360  retn
0x180053361  lea     rax, aMeupdatedstrea; "MEUpdatedStream"
0x180053368  retn
0x180053369  lea     rax, aMenewstream; "MENewStream"
0x180053370  retn
0x180053371  lea     rax, aMestreamseeked; "MEStreamSeeked"
0x180053378  retn
0x180053379  lea     rax, aMemediasample; "MEMediaSample"
0x180053380  retn
0x180053381  sub     ecx, 0D6h
0x180053387  jz      short loc_1800533E8
0x180053389  sub     ecx, 1
0x18005338c  jz      short loc_1800533E0
0x18005338e  sub     ecx, 1
0x180053391  jz      short loc_1800533D8
0x180053393  sub     ecx, 1
0x180053396  jz      short loc_1800533D0
0x180053398  sub     ecx, 1
0x18005339b  jz      short loc_1800533C8
0x18005339d  sub     ecx, 1
0x1800533a0  jz      short loc_1800533C0
0x1800533a2  sub     ecx, 1
0x1800533a5  jz      short loc_1800533B8
0x1800533a7  cmp     ecx, 1
0x1800533aa  jnz     def_1800536EE; jumptable 00000001800536EE default case, cases 9513,9530,9538-9544,9546
0x1800533b0  lea     rax, aMesourcemetada; "MESourceMetadataChanged"
0x1800533b7  retn
0x1800533b8  lea     rax, aMesourceratech_0; "MESourceRateChangeRequested"
0x1800533bf  retn
0x1800533c0  lea     rax, aMesourcecharac; "MESourceCharacteristicsChanged"
0x1800533c7  retn
0x1800533c8  lea     rax, aMeendofpresent; "MEEndOfPresentationSegment"
0x1800533cf  retn
0x1800533d0  lea     rax, aMesourceratech; "MESourceRateChanged"
0x1800533d7  retn
0x1800533d8  lea     rax, aMestreamformat; "MEStreamFormatChanged"
0x1800533df  retn
0x1800533e0  lea     rax, aMestreamthinmo; "MEStreamThinMode"
0x1800533e7  retn
0x1800533e8  lea     rax, aMestreamtick; "MEStreamTick"
0x1800533ef  retn
0x1800533f0  lea     rax, aMestreamsinkst_0; "MEStreamSinkStarted"
0x1800533f7  retn
0x1800533f8  mov     eax, 135h
0x1800533fd  cmp     ecx, eax
0x1800533ff  ja      short loc_18005346D
0x180053401  jz      short loc_180053465
0x180053403  sub     ecx, 12Eh
0x180053409  jz      short loc_18005345D
0x18005340b  sub     ecx, 1
0x18005340e  jz      short loc_180053455
0x180053410  sub     ecx, 1
0x180053413  jz      short loc_18005344D
0x180053415  sub     ecx, 1
0x180053418  jz      short loc_180053445
0x18005341a  sub     ecx, 1
0x18005341d  jz      short loc_18005343D
0x18005341f  sub     ecx, 1
0x180053422  jz      short loc_180053435
0x180053424  cmp     ecx, 1
0x180053427  jnz     def_1800536EE; jumptable 00000001800536EE default case, cases 9513,9530,9538-9544,9546
0x18005342d  lea     rax, aMestreamsinksc; "MEStreamSinkScrubSampleComplete"
0x180053434  retn
0x180053435  lea     rax, aMestreamsinkpr; "MEStreamSinkPrerolled"
0x18005343c  retn
0x18005343d  lea     rax, aMestreamsinkma; "MEStreamSinkMarker"
0x180053444  retn
0x180053445  lea     rax, aMestreamsinkre; "MEStreamSinkRequestSample"
0x18005344c  retn
0x18005344d  lea     rax, aMestreamsinkra; "MEStreamSinkRateChanged"
0x180053454  retn
0x180053455  lea     rax, aMestreamsinkpa; "MEStreamSinkPaused"
0x18005345c  retn
0x18005345d  lea     rax, aMestreamsinkst; "MEStreamSinkStopped"
0x180053464  retn
0x180053465  lea     rax, aMestreamsinkfo_0; "MEStreamSinkFormatChanged"
0x18005346c  retn
0x18005346d  sub     ecx, 136h
0x180053473  jz      short loc_1800534BA
0x180053475  sub     ecx, 1
0x180053478  jz      short loc_1800534B2
0x18005347a  sub     ecx, 1
0x18005347d  jz      short loc_1800534AA
0x18005347f  sub     ecx, 1
0x180053482  jz      short loc_1800534A2
0x180053484  sub     ecx, 1
0x180053487  jz      short loc_18005349A
0x180053489  cmp     ecx, 1
0x18005348c  jnz     def_1800536EE; jumptable 00000001800536EE default case, cases 9513,9530,9538-9544,9546
0x180053492  lea     rax, aMeaudiosession_1; "MEAudioSessionDeviceRemoved"
0x180053499  retn
0x18005349a  lea     rax, aMeaudiosession; "MEAudioSessionVolumeChanged"
0x1800534a1  retn
0x1800534a2  lea     rax, aMeaudiosession_4; "MEAudioSessionNameChanged"
0x1800534a9  retn
0x1800534aa  lea     rax, aMesinkinvalida; "MESinkInvalidated"
0x1800534b1  retn
0x1800534b2  lea     rax, aMequalitynotif; "MEQualityNotify"
0x1800534b9  retn
0x1800534ba  lea     rax, aMestreamsinkde; "MEStreamSinkDeviceChanged"
0x1800534c1  retn
0x1800534c2  lea     rax, aMeaudiosession_3; "MEAudioSessionServerShutdown"
0x1800534c9  retn
0x1800534ca  mov     eax, 2527h
0x1800534cf  cmp     ecx, eax
0x1800534d1  ja      loc_1800536CE
0x1800534d7  jz      loc_1800536C6
0x1800534dd  mov     eax, 25Bh
0x1800534e2  cmp     ecx, eax
0x1800534e4  ja      loc_1800535DC
0x1800534ea  jz      loc_1800535D4
  ... truncated ...
```
