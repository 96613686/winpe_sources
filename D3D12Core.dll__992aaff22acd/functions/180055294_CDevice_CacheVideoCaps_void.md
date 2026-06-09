# CDevice::CacheVideoCaps(void)

- ea: `0x180055294`
- end: `0x180055e2a`
- name: `?CacheVideoCaps@CDevice@@AEAAXXZ`
- size: `2966`
- prototype: `void __fastcall(CDevice *__hidden this)`
- caller_count: `1`
- callee_count: `27`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180054318`

## callees

- `0x180007df0`
- `0x18000b010`
- `0x18000bb58`
- `0x180028070`
- `0x180052aa4`
- `0x180053630`
- `0x180055294`
- `0x180060b00`
- `0x1800672e8`
- `0x18006740c`
- `0x18006748c`
- `0x1800679dc`
- `0x180067a38`
- `0x18007197c`
- `0x180072320`
- `0x1800755b4`
- `0x18007efa0`
- `0x18007f054`
- `0x18009fee0`
- `0x1800a0770`
- `0x1800ae1f4`
- `0x1800af19c`
- `0x1800bb480`
- `0x1800f1af0`
- `0x18010292c`
- `0x18011dc70`
- `0x180262020`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x1800552c5`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x1800552c5`

## string_xrefs

- `0x18005546c`: `One of the COMMAND_INFO returned from D3D12DDICAPS_TYPE_VIDEO_0063_EXTENSION_COMMANDS reported GUID_NULL.\n`
- `0x18005548d`: `One of the COMMAND_INFO returned from D3D12DDICAPS_TYPE_VIDEO_0063_EXTENSION_COMMANDS reported more than one D3D12DDI_COMMAND_QUEUE_FLAG.\n`
- `0x1800553bc`: `Failed GetCaps for D3D12DDICAPS_TYPE_VIDEO_0063_EXTENSION_COMMAND_COUNT.\n`
- `0x180055429`: `Failed GetCaps for D3D12DDICAPS_TYPE_VIDEO_0063_EXTENSION_COMMANDS.\n`
- `0x1800556fb`: `Failed CheckEngineAccess for Video Encode. FeatureAreaSupport.VideoEncodeSupport unchanged. \n`
- `0x180055696`: `VidEnc: ENGINE_ACCESS_DENIED - FeatureAreaSupport.VideoEncodeSupport disabled\n`
- `0x1800554ad`: `One of the COMMAND_INFO returned from D3D12DDICAPS_TYPE_VIDEO_0063_EXTENSION_COMMANDS reported a non-Video D3D12DDI_COMMAND_QUEUE_FLAG.\n`
- `0x1800556d7`: `One of the COMMAND_INFO returned from D3D12DDICAPS_TYPE_VIDEO_0063_EXTENSION_COMMANDS reported CommandQueueFlags that do not match the registered CommandQueueFlags.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CDevice::CacheVideoCaps(CDevice *this)
{
  __int64 v2; // rsi
  __int64 *v3; // r14
  __int64 v4; // r8
  unsigned __int64 v5; // rcx
  CDevice::VideoNodeCaps *v6; // rbx
  unsigned int v7; // eax
  __int64 v8; // rsi
  __int64 v9; // r14
  unsigned int v10; // r12d
  CJournal *v11; // rcx
  __int64 v12; // r8
  __int128 *v13; // rbx
  __int128 *v14; // r15
  CJournal *v15; // rcx
  unsigned int v16; // r8d
  CJournal *v17; // rcx
  __int64 v18; // r9
  int v19; // r8d
  int v20; // edx
  int v21; // ecx
  int v22; // edx
  int v23; // ecx
  int v24; // eax
  CJournal *v25; // rcx
  __int64 v26; // rax
  __int64 (__fastcall *v27)(__int64 *); // rax
  __int64 v28; // rbx
  unsigned int v29; // eax
  int v30; // eax
  __int64 v31; // rcx
  __int64 v32; // r9
  __int64 v33; // rcx
  int v34; // eax
  CJournal *v35; // rcx
  __int64 v36; // r8
  const char *v37; // r8
  CJournal *v38; // rcx
  const char *v39; // r8
  CJournal *v40; // rcx
  __int64 v41; // r8
  const char *v42; // r8
  int v43; // eax
  __int64 v44; // r8
  CJournal *v45; // rcx
  _QWORD *v46; // rbx
  unsigned int v47; // edx
  unsigned int v48; // r15d
  __int64 v49; // r10
  int IsDecodeProfileRegistered; // r13d
  CJournal *v51; // rcx
  __int128 v52; // xmm1
  __int64 v53; // rdx
  CJournal *v54; // rcx
  __int128 *v55; // r15
  __int128 *v56; // r13
  __int64 *v57; // rsi
  CJournal *v58; // rcx
  const char *v59; // r8
  __int64 v60; // r8
  CJournal *v61; // rcx
  __int64 v62; // r8
  unsigned __int64 v63; // rcx
  __int64 v64; // rbx
  char v65; // r12
  unsigned __int64 v66; // r13
  __int64 v67; // rdx
  __int64 v68; // rax
  unsigned int v69; // r9d
  const struct CRegisteredBitstreamEncryptionSchemes::RegisteredBitstreamEncryptionSchemeInfo near **v70; // rcx
  _OWORD *v71; // rbx
  __int64 v72; // r8
  unsigned __int64 v73; // rcx
  __int64 v74; // rbx
  _OWORD *v75; // rbx
  unsigned int v76; // [rsp+30h] [rbp-D0h]
  unsigned int v77; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v78; // [rsp+3Ch] [rbp-C4h]
  unsigned int v79; // [rsp+40h] [rbp-C0h]
  int v80; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v81; // [rsp+4Ch] [rbp-B4h]
  unsigned int v82; // [rsp+50h] [rbp-B0h] BYREF
  int v83; // [rsp+54h] [rbp-ACh]
  unsigned int v84; // [rsp+58h] [rbp-A8h] BYREF
  int v85; // [rsp+5Ch] [rbp-A4h]
  __int128 *v86; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v87; // [rsp+68h] [rbp-98h] BYREF
  int v88; // [rsp+6Ch] [rbp-94h]
  __int128 v89; // [rsp+70h] [rbp-90h] BYREF
  __int64 v90; // [rsp+80h] [rbp-80h]
  __int64 v91; // [rsp+88h] [rbp-78h]
  _DWORD v92[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v93; // [rsp+98h] [rbp-68h]
  _DWORD v94[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v95; // [rsp+A8h] [rbp-58h]
  char v96[16]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v97; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v98; // [rsp+D0h] [rbp-30h]
  int v99; // [rsp+D8h] [rbp-28h]
  int v100; // [rsp+DCh] [rbp-24h]
  __int64 v101; // [rsp+E0h] [rbp-20h] BYREF
  int v102; // [rsp+E8h] [rbp-18h]
  unsigned int v103; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v104; // [rsp+F4h] [rbp-Ch]
  int v105; // [rsp+FCh] [rbp-4h]
  _BYTE v106[20]; // [rsp+100h] [rbp+0h] BYREF
  int v107; // [rsp+114h] [rbp+14h]
  __int128 v108; // [rsp+118h] [rbp+18h] BYREF
  __int64 v109; // [rsp+128h] [rbp+28h]
  unsigned int v110; // [rsp+130h] [rbp+30h] BYREF
  __int128 v111; // [rsp+134h] [rbp+34h]
  unsigned int v112; // [rsp+144h] [rbp+44h]

  GetNativeSystemInfo((LPSYSTEM_INFO)this + 153);
  v2 = (__int64)(*((_QWORD *)this + 701) - *((_QWORD *)this + 700)) >> 2;
  v91 = v2;
  v3 = (__int64 *)((char *)this + 7320);
  v4 = *((_QWORD *)this + 915);
  v5 = 0xEEEEEEEEEEEEEEEFuLL * ((*((_QWORD *)this + 916) - v4) >> 3);
  if ( (unsigned int)v2 >= v5 )
  {
    if ( (unsigned int)v2 > v5 )
    {
      if ( (unsigned int)v2 <= 0xEEEEEEEEEEEEEEEFuLL * ((*((_QWORD *)this + 917) - v4) >> 3) )
        *((_QWORD *)this + 916) = std::_Uninitialized_value_construct_n<std::allocator<CDevice::VideoNodeCaps>>(*((CDevice::VideoNodeCaps **)this + 916));
      else
        std::vector<CDevice::VideoNodeCaps>::_Resize_reallocate<std::_Value_init_tag>((char *)this + 7320);
    }
  }
  else
  {
    v6 = (CDevice::VideoNodeCaps *)(v4 + 120LL * (unsigned int)v2);
    std::_Destroy_range<std::allocator<CDevice::VideoNodeCaps>>(v6);
    *((_QWORD *)this + 916) = v6;
  }
  v7 = 0;
  v79 = 0;
  if ( (_DWORD)v2 )
  {
    while ( 1 )
    {
      v8 = 120LL * v7;
      v9 = *v3;
      v10 = *(_DWORD *)(*((_QWORD *)this + 700) + 4LL * v7);
      v76 = v10;
      if ( *((_DWORD *)this + 719) >= 0xFu )
      {
        v80 = *(_DWORD *)(*((_QWORD *)this + 700) + 4LL * v7);
        v81 = 0;
        if ( (int)CDevice::GetCaps(this, 22, v4, &v80, 8) < 0 )
        {
          CJournal::ReportDriverError(
            v11,
            -2005270496,
            "Failed GetCaps for D3D12DDICAPS_TYPE_VIDEO_0063_EXTENSION_COMMAND_COUNT.\n");
          ThrowFailure(-2005270496);
        }
        v89 = 0;
        v90 = 0;
        if ( v81 )
        {
          std::vector<D3D12_VIDEO_EXTENSION_COMMAND_INFO>::_Resize_reallocate<std::_Value_init_tag>(&v89, v81);
          v92[0] = v10;
          v92[1] = v81;
          v93 = v89;
          if ( (int)CDevice::GetCaps(this, 23, v12, v92, 16) < 0 )
          {
            CJournal::ReportDriverError(
              v11,
              -2005270496,
              "Failed GetCaps for D3D12DDICAPS_TYPE_VIDEO_0063_EXTENSION_COMMANDS.\n");
            ThrowFailure(-2005270496);
          }
        }
        v14 = (__int128 *)*((_QWORD *)&v89 + 1);
        v13 = (__int128 *)v89;
        if ( (_QWORD)v89 != *((_QWORD *)&v89 + 1) )
        {
          do
          {
            if ( *(_QWORD *)v13 == *(_QWORD *)&GUID_NULL.Data1 && *((_QWORD *)v13 + 1) == *(_QWORD *)GUID_NULL.Data4 )
            {
              CJournal::ReportDriverError(
                v11,
                -2005270496,
                "One of the COMMAND_INFO returned from D3D12DDICAPS_TYPE_VIDEO_0063_EXTENSION_COMMANDS reported GUID_NULL.\n");
              ThrowFailure(-2005270496);
            }
            v15 = (CJournal *)*((unsigned int *)v13 + 6);
            if ( (((_DWORD)v15 - 1) & (unsigned int)v15) != 0 )
            {
              CJournal::ReportDriverError(
                v15,
                -2005270496,
                "One of the COMMAND_INFO returned from D3D12DDICAPS_TYPE_VIDEO_0063_EXTENSION_COMMANDS reported more than"
                " one D3D12DDI_COMMAND_QUEUE_FLAG.\n");
              ThrowFailure(-2005270496);
            }
            if ( (*((_DWORD *)v13 + 6) & 0xFFFFFF8F) != 0 )
            {
              CJournal::ReportDriverError(
                v15,
                -2005270496,
                "One of the COMMAND_INFO returned from D3D12DDICAPS_TYPE_VIDEO_0063_EXTENSION_COMMANDS reported a non-Vid"
                "eo D3D12DDI_COMMAND_QUEUE_FLAG.\n");
              ThrowFailure(-2005270496);
            }
            v16 = *((_DWORD *)this + 719);
            v17 = (CJournal *)&CRegisteredExtensionCommands::s_Commands;
            while ( **(_QWORD **)v17 != *(_QWORD *)v13
                 || *(_QWORD *)(*(_QWORD *)v17 + 8LL) != *((_QWORD *)v13 + 1)
                 || v16 < *((_DWORD *)v17 + 2)
                 || v16 > *((_DWORD *)v17 + 3) )
            {
              v17 = (CJournal *)((char *)v17 + 24);
              if ( v17 == (CJournal *)&g_3dClosedOrRemovedCommandListDDIs_0074 )
                goto LABEL_28;
            }
            v34 = *((_DWORD *)v17 + 4);
            if ( v34 != 112 )
            {
              if ( v34 != *((_DWORD *)v13 + 6) )
              {
                CJournal::ReportDriverError(
                  v17,
                  -2005270496,
                  "One of the COMMAND_INFO returned from D3D12DDICAPS_TYPE_VIDEO_0063_EXTENSION_COMMANDS reported Command"
                  "QueueFlags that do not match the registered CommandQueueFlags.\n");
                ThrowFailure(-2005270496);
              }
              goto LABEL_29;
            }
LABEL_28:
            if ( !CDevice::DeveloperModeEnabled(this) )
              goto LABEL_40;
LABEL_29:
            v18 = *((_QWORD *)v13 + 2);
            v19 = *((_DWORD *)v13 + 6);
            v20 = ((v19 & 1) != 0 ? 3 : 0) | 4;
            if ( (v19 & 2) == 0 )
              v20 = (*((_DWORD *)v13 + 6) & 1) != 0 ? 3 : 0;
            v21 = v20 | 8;
            if ( (v19 & 4) == 0 )
              v21 = v20;
            v22 = v21 | 0x10;
            if ( (v19 & 0x10) == 0 )
              v22 = v21;
            v23 = v22 | 0x20;
            if ( (v19 & 0x20) == 0 )
              v23 = v22;
            v24 = v23 | 0x40;
            if ( (v19 & 0x40) == 0 )
              v24 = v23;
            v97 = *v13;
            v98 = v18;
            v99 = v24;
            v100 = 0;
            std::_Hash<std::_Umap_traits<SGuid,CDevice::DriverVideoExtensionCommand,std::_Uhash_compare<SGuid,std::hash<SGuid>,std::equal_to<SGuid>>,std::allocator<std::pair<SGuid const,CDevice::DriverVideoExtensionCommand>>,0>>::emplace<std::pair<_GUID,CDevice::DriverVideoExtensionCommand>>(
              v8 + v9 + 56,
              v96,
              &v97);
LABEL_40:
            v13 += 2;
          }
          while ( v13 != v14 );
          v13 = (__int128 *)v89;
        }
        if ( v13 )
          std::_Deallocate<16>(v13, (v90 - (_QWORD)v13) & 0xFFFFFFFFFFFFFFE0uLL);
      }
      if ( *((_DWORD *)this + 719) < 0xDu )
      {
        *(_DWORD *)(v8 + v9) = 1;
        *(_QWORD *)(v8 + v9 + 4) = 1;
      }
      else
      {
        v103 = v10;
        v104 = 0;
        v105 = 0;
        if ( (int)CDevice::GetCaps(this, 19, v4, &v103, 16) < 0 )
        {
          CJournal::ReportDriverError(
            v25,
            -2005270496,
            "Failed GetCaps for D3D12DDICAPS_TYPE_VIDEO_0053_FEATURE_AREA_SUPPORT.\n");
          ThrowFailure(-2005270496);
        }
        *(_QWORD *)(v8 + v9) = v104;
        *(_DWORD *)(v8 + v9 + 8) = v105;
        v26 = *((_QWORD *)this + 87);
        if ( v26 )
        {
          v27 = *(__int64 (__fastcall **)(__int64 *))(v26 + 8);
          if ( v27 )
          {
            v101 = 0;
            v102 = 0;
            v28 = *((_QWORD *)this + 95);
            LODWORD(v101) = *(_DWORD *)(*(_QWORD *)(v28 + 40) + 448LL);
            HIDWORD(v101) = 3;
            v29 = v27(&v101);
            v30 = NDXGI::CDevice::NTStatusToHResult(v28, v29, 1);
            if ( v30 < 0 )
            {
              CJournal::RecordJournal(
                v31,
                v30,
                (__int64)"Failed CheckEngineAccess for Video Encode. FeatureAreaSupport.VideoEncodeSupport unchanged. \n",
                v32,
                0);
            }
            else if ( v102 == 2 )
            {
              *(_DWORD *)(v8 + v9 + 8) = 0;
              CJournal::RecordJournal(
                v31,
                0,
                (__int64)"VidEnc: ENGINE_ACCESS_DENIED - FeatureAreaSupport.VideoEncodeSupport disabled\n",
                v32,
                0);
              if ( (Microsoft_Windows_Direct3D12EnableBits & 4) != 0 )
                McTemplateU0p_EtwEventWriteTransfer(
                  v33,
                  EventD3D12VideoEncodeEngineAccessDenied,
                  *((_QWORD *)this + 96));
            }
          }
        }
      }
      if ( *((_DWORD *)this + 719) >= 0x10u )
        break;
LABEL_70:
      v77 = v10;
      v78 = 0;
      if ( (int)CDevice::GetCaps(this, 10, v4, &v77, 8) < 0 )
      {
        v42 = "Failed GetCaps for D3D12DDICAPS_TYPE_VIDEO_0032_DECODE_PROFILE_COUNT.\n";
LABEL_76:
        CJournal::ReportDriverError(v40, -2005270496, v42);
        ThrowFailure(-2005270496);
        goto LABEL_96;
      }
      v40 = (CJournal *)v78;
      if ( !v78 )
      {
        v43 = *((_DWORD *)this + 76);
        if ( v43 != 4096 && v43 != 256 )
        {
          v42 = "PFND3D12DDI_VIDEO_GET_DECODE_PROFILE_COUNT_0020 returned no supported profiles.\n";
          goto LABEL_76;
        }
      }
      v97 = 0;
      v98 = 0;
      if ( v78 )
        std::vector<_GUID>::_Resize_reallocate<std::_Value_init_tag>(&v97, v78);
      v94[0] = v10;
      v94[1] = (__int64)(*((_QWORD *)&v97 + 1) - v97) >> 4;
      v95 = v97;
      if ( (int)CDevice::GetCaps(this, 1, v41, v94, 16) < 0 )
      {
        CJournal::ReportDriverError(
          v45,
          -2005270496,
          "Failed GetCaps for D3D12DDICAPS_TYPE_VIDEO_0020_DECODE_PROFILES.\n");
        ThrowFailure(-2005270496);
      }
      v46 = (_QWORD *)(v8 + v9);
      if ( *(_QWORD *)(v8 + v9 + 16) != *(_QWORD *)(v8 + v9 + 24) )
      {
        std::_Destroy_range<std::allocator<CDevice::VideoNodeCaps::DecodeProfileInfo>>(v46[2]);
        v46[3] = v46[2];
      }
      v47 = v78;
      v86 = (__int128 *)v78;
      if ( v78 > 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*(_QWORD *)(v8 + v9 + 32) - v46[2]) >> 4) )
      {
        std::vector<CDevice::VideoNodeCaps::DecodeProfileInfo>::_Reallocate<0>(v46 + 2, &v86);
        v47 = v78;
      }
      v48 = 0;
      if ( v47 )
      {
        while ( 1 )
        {
          IsDecodeProfileRegistered = CRegisteredDecodeProfiles::IsDecodeProfileRegistered(
                                        v97 + 16LL * v48,
                                        *((unsigned int *)this + 719));
          if ( IsDecodeProfileRegistered )
            goto LABEL_90;
          if ( CDevice::DeveloperModeEnabled(this) )
            break;
          CJournal::ReportDriverError(
            v51,
            -2005270496,
            "D3D12DDICAPS_TYPE_VIDEO_0020_DECODE_PROFILES reported an unsupported profile GUID.\n");
          ThrowFailure(-2005270496);
LABEL_94:
          if ( ++v48 >= v78 )
            goto LABEL_95;
        }
        v49 = v97;
LABEL_90:
        v52 = *(_OWORD *)(v49 + 16LL * v48);
        *(_OWORD *)v106 = v52;
        *(_DWORD *)&v106[16] = IsDecodeProfileRegistered;
        v107 = 0;
        v108 = 0;
        v109 = 0;
        v53 = v46[3];
        if ( v53 == v46[4] )
        {
          std::vector<CDevice::VideoNodeCaps::DecodeProfileInfo>::_Emplace_reallocate<CDevice::VideoNodeCaps::DecodeProfileInfo>(
            v46 + 2,
            v53,
            v106);
        }
        else
        {
          *(_OWORD *)v53 = v52;
          *(_DWORD *)(v53 + 16) = IsDecodeProfileRegistered;
          v109 = 0;
          v108 = 0u;
          *(_QWORD *)(v53 + 24) = 0;
          *(_QWORD *)(v53 + 32) = 0;
          *(_QWORD *)(v53 + 40) = 0;
          v46[3] += 48LL;
        }
        std::vector<CDevice::VideoNodeCaps::BitstreamEncryptionSchemeInfo>::_Tidy(&v108);
        goto LABEL_94;
      }
LABEL_95:
      std::vector<D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_INFO_0063>::_Tidy(&v97);
LABEL_96:
      v87 = v10;
      v88 = 0;
      if ( (int)CDevice::GetCaps(this, 6, v44, &v87, 8) < 0 )
      {
        CJournal::ReportDriverError(
          v54,
          -2005270496,
          "Failure when retrieving D3D12DDICAPS_TYPE_VIDEO_0020_PROCESS_MAX_INPUT_STREAMS.\n");
        ThrowFailure(-2005270496);
      }
      else
      {
        *(_DWORD *)(v8 + v9 + 40) = v88;
      }
      v55 = *(__int128 **)(v8 + v9 + 16);
      v56 = *(__int128 **)(v8 + v9 + 24);
      v86 = v56;
      if ( v55 != v56 )
      {
        v57 = (__int64 *)v55 + 3;
        do
        {
          if ( *((_DWORD *)this + 722) )
          {
            v110 = v10;
            v111 = *v55;
            v112 = 0;
            if ( (int)CDevice::GetCaps(this, 12, v4, &v110, 24) >= 0 )
            {
              if ( v112 )
              {
                v97 = 0;
                v98 = 0;
                std::vector<_GUID>::_Resize_reallocate<std::_Value_init_tag>(&v97, v112);
                *(_DWORD *)v106 = v10;
                *(_OWORD *)&v106[4] = *v55;
                v107 = (__int64)(*((_QWORD *)&v97 + 1) - v97) >> 4;
                *(_QWORD *)&v108 = v97;
                if ( (int)CDevice::GetCaps(this, 4, v60, v106, 32) >= 0 )
                {
                  v62 = *v57;
                  v63 = 0xCCCCCCCCCCCCCCCDuLL * ((v57[1] - *v57) >> 4);
                  if ( v112 >= v63 )
                  {
                    if ( v112 > v63 )
                    {
                      if ( v112 <= 0xCCCCCCCCCCCCCCCDuLL * ((v57[2] - v62) >> 4) )
                        v57[1] = std::_Uninitialized_value_construct_n<std::allocator<CDevice::VideoNodeCaps::BitstreamEncryptionSchemeInfo>>((void *)v57[1]);
                      else
                        std::vector<CDevice::VideoNodeCaps::BitstreamEncryptionSchemeInfo>::_Resize_reallocate<std::_Value_init_tag>(
                          v57,
                          v112);
                    }
                  }
                  else
                  {
                    v64 = v62 + 80LL * v112;
                    std::_Destroy_range<std::allocator<CDevice::VideoNodeCaps::BitstreamEncryptionSchemeInfo>>(
                      v64,
                      v57[1]);
                    v57[1] = v64;
                  }
                  v65 = 0;
                  v66 = 0;
                  v67 = v97;
                  if ( !((__int64)(*((_QWORD *)&v97 + 1) - v97) >> 4) )
                    goto LABEL_129;
                  do
                  {
                    v68 = *(_QWORD *)(v67 + 16 * v66) - D3D12DDI_VIDEO_DECODE_BITSTREAM_ENCRYPTION_NONE;
                    if ( !v68 )
                      v68 = *(_QWORD *)(v67 + 16 * v66 + 8)
                          - *((_QWORD *)&D3D12DDI_VIDEO_DECODE_BITSTREAM_ENCRYPTION_NONE + 1);
                    if ( !v68 )
                      v65 = 1;
                    v69 = *((_DWORD *)this + 719);
                    v70 = (const struct CRegisteredBitstreamEncryptionSchemes::RegisteredBitstreamEncryptionSchemeInfo near **)&CRegisteredBitstreamEncryptionSchemes::s_Schemes;
                    while ( *(_QWORD *)*v70 != *(_QWORD *)(v67 + 16 * v66)
                         || *((_QWORD *)*v70 + 1) != *(_QWORD *)(v67 + 16 * v66 + 8)
                         || v69 < *((_DWORD *)v70 + 2)
                         || v69 > *((_DWORD *)v70 + 3) )
                    {
                      v70 += 2;
                      if ( v70 == (const struct CRegisteredBitstreamEncryptionSchemes::RegisteredBitstreamEncryptionSchemeInfo near **)&`Dred::CDredSettingsController::_GetEntries'::`2'::_entries )
                      {
                        CJournal::ReportDriverError(
                          (CJournal *)v70,
                          -2005270496,
                          "PFND3D12DDI_VIDEO_GET_BITSTREAM_ENCRYPTION_SCHEME_COUNT_0020 reported an unrecognized bitstream encryption.\n");
                        ThrowFailure(-2005270496);
                        v67 = v97;
                        break;
                      }
                    }
                    v71 = (_OWORD *)(*v57 + 80 * v66);
                    *v71 = *(_OWORD *)(v67 + 16 * v66);
                    CDevice::CacheVideoDecodeFormatCaps(this, v76, v55, v71, 0, v71 + 1);
                    CDevice::CacheVideoDecodeFormatCaps(this, v76, v55, v71, 1, v71 + 3);
                    ++v66;
                    v67 = v97;
                  }
                  while ( v66 < (__int64)(*((_QWORD *)&v97 + 1) - v97) >> 4 );
                  if ( !v65 )
                  {
LABEL_129:
                    CJournal::ReportDriverError(
                      (CJournal *)v63,
                      -2005270496,
                      "PFND3D12DDI_VIDEO_GET_BITSTREAM_ENCRYPTION_SCHEME_COUNT_0020 must report support for at least D3D1"
                      "2_VIDEO_DECODE_BITSTREAM_ENCRYPTION_NONE.\n");
                    ThrowFailure(-2005270496);
                  }
                  v56 = v86;
                  v10 = v76;
                }
                else
                {
                  CJournal::ReportDriverError(
                    v61,
                    -2005270496,
                    "Failed GetCaps for D3D12DDICAPS_TYPE_VIDEO_0020_DECODE_BITSTREAM_ENCRYPTION_SCHEMES.\n");
                  ThrowFailure(-2005270496);
                }
                std::vector<D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_INFO_0063>::_Tidy(&v97);
                goto LABEL_139;
              }
              v59 = "PFND3D12DDI_VIDEO_GET_BITSTREAM_ENCRYPTION_SCHEME_COUNT_0020 reported zero bitstream encryption sche"
                    "mes.  It must support at least D3D12_VIDEO_DECODE_BITSTREAM_ENCRYPTION_NONE.\n";
            }
            else
            {
              v59 = "Failed GetCaps for D3D12DDICAPS_TYPE_VIDEO_0032_DECODE_BITSTREAM_ENCRYPTION_SCHEME_COUNT.\n";
            }
            CJournal::ReportDriverError(v58, -2005270496, v59);
            ThrowFailure(-2005270496);
          }
          else
          {
            v72 = *v57;
            v73 = 0xCCCCCCCCCCCCCCCDuLL * ((v57[1] - *v57) >> 4);
            if ( v73 <= 1 )
            {
              if ( !v73 )
              {
                if ( 0xCCCCCCCCCCCCCCCDuLL * ((v57[2] - v72) >> 4) )
                  v57[1] = std::_Uninitialized_value_construct_n<std::allocator<CDevice::VideoNodeCaps::BitstreamEncryptionSchemeInfo>>((void *)v57[1]);
                else
                  std::vector<CDevice::VideoNodeCaps::BitstreamEncryptionSchemeInfo>::_Resize_reallocate<std::_Value_init_tag>(
                    v57,
                    1);
              }
            }
            else
            {
              v74 = v72 + 80;
              std::_Destroy_range<std::allocator<CDevice::VideoNodeCaps::BitstreamEncryptionSchemeInfo>>(
                v72 + 80,
                v57[1]);
              v57[1] = v74;
            }
            v75 = (_OWORD *)*((_QWORD *)v55 + 3);
            *v75 = D3D12DDI_VIDEO_DECODE_BITSTREAM_ENCRYPTION_NONE;
            CDevice::CacheVideoDecodeFormatCaps(this, v10, v55, v75, 0, v75 + 1);
            CDevice::CacheVideoDecodeFormatCaps(this, v10, v55, v75, 1, v75 + 3);
          }
LABEL_139:
          v55 += 3;
          v57 += 6;
        }
        while ( v55 != v56 );
      }
      v7 = v79 + 1;
      v79 = v7;
      v3 = (__int64 *)((char *)this + 7320);
      if ( v7 >= (unsigned int)v91 )
        return;
    }
    v82 = v10;
    v83 = 0;
    if ( (int)CDevice::GetCaps(this, 29, v4, &v82, 8) >= 0 )
    {
      if ( (v83 & 0xFFFFFFFE) == 0 )
        goto LABEL_64;
      v37 = "GetCaps for D3D12DDICAPS_TYPE_VIDEO_0072_PROCESS_PROTECTED_RESOURCES returned invalid support flags.\n";
    }
    else
    {
      v37 = "Failed GetCaps for D3D12DDICAPS_TYPE_VIDEO_0072_PROCESS_PROTECTED_RESOURCES.\n";
    }
    CJournal::ReportDriverError(v35, -2005270496, v37);
    ThrowFailure(-2005270496);
LABEL_64:
    *(_DWORD *)(v8 + v9 + 44) = v83 & 1;
    v84 = v10;
    v85 = 0;
    if ( (int)CDevice::GetCaps(this, 30, v36, &v84, 8) >= 0 )
    {
      if ( (v85 & 0xFFFFFFFE) == 0 )
      {
LABEL_69:
        *(_DWORD *)(v8 + v9 + 48) = v85 & 1;
        goto LABEL_70;
      }
      v39 = "GetCaps for D3D12DDICAPS_TYPE_VIDEO_0072_MOTION_ESTIMATOR_PROTECTED_RESOURCES returned invalid support flags.\n";
    }
    else
    {
      v39 = "Failed GetCaps for D3D12DDICAPS_TYPE_VIDEO_0072_MOTION_ESTIMATOR_PROTECTED_RESOURCES.\n";
    }
    CJournal::ReportDriverError(v38, -2005270496, v39);
    ThrowFailure(-2005270496);
    goto LABEL_69;
  }
}

```

## disassembly

```asm
0x180055294  push    rbp
0x180055296  push    rbx
0x180055297  push    rsi
0x180055298  push    rdi
0x180055299  push    r12
0x18005529b  push    r13
0x18005529d  push    r14
0x18005529f  push    r15
0x1800552a1  lea     rbp, [rsp-58h]
0x1800552a6  sub     rsp, 158h
0x1800552ad  mov     rax, cs:__security_cookie
0x1800552b4  xor     rax, rsp
0x1800552b7  mov     [rbp+90h+var_48], rax
0x1800552bb  mov     rdi, rcx
0x1800552be  add     rcx, 1CB0h; lpSystemInfo
0x1800552c5  call    cs:__imp_GetNativeSystemInfo
0x1800552cb  mov     rsi, [rdi+15E8h]
0x1800552d2  sub     rsi, [rdi+15E0h]
0x1800552d9  sar     rsi, 2
0x1800552dd  mov     [rbp+90h+var_108], rsi
0x1800552e1  lea     r14, [rdi+1C98h]
0x1800552e8  mov     r8, [r14]
0x1800552eb  mov     rcx, [r14+8]
0x1800552ef  sub     rcx, r8
0x1800552f2  sar     rcx, 3
0x1800552f6  mov     r9, 0EEEEEEEEEEEEEEEFh
0x180055300  imul    rcx, r9
0x180055304  mov     edx, esi
0x180055306  cmp     rdx, rcx
0x180055309  jnb     short loc_180055324
0x18005530b  imul    rbx, rdx, 78h ; 'x'
0x18005530f  add     rbx, r8
0x180055312  mov     rdx, [r14+8]
0x180055316  mov     rcx, rbx; this
0x180055319  call    ??$_Destroy_range@V?$allocator@UVideoNodeCaps@CDevice@@@std@@@std@@YAXPEAUVideoNodeCaps@CDevice@@QEAU12@AEAV?$allocator@UVideoNodeCaps@CDevice@@@0@@Z; std::_Destroy_range<std::allocator<CDevice::VideoNodeCaps>>(CDevice::VideoNodeCaps *,CDevice::VideoNodeCaps * const,std::allocator<CDevice::VideoNodeCaps> &)
0x18005531e  mov     [r14+8], rbx
0x180055322  jmp     short loc_180055357
0x180055324  jbe     short loc_180055357
0x180055326  mov     rax, [r14+10h]
0x18005532a  sub     rax, r8
0x18005532d  sar     rax, 3
0x180055331  imul    rax, r9
0x180055335  cmp     rdx, rax
0x180055338  jbe     short loc_180055344
0x18005533a  mov     rcx, r14
0x18005533d  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@UVideoNodeCaps@CDevice@@V?$allocator@UVideoNodeCaps@CDevice@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<CDevice::VideoNodeCaps>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180055342  jmp     short loc_180055357
0x180055344  sub     rdx, rcx
0x180055347  mov     r8, r14
0x18005534a  mov     rcx, [r14+8]; this
0x18005534e  call    ??$_Uninitialized_value_construct_n@V?$allocator@UVideoNodeCaps@CDevice@@@std@@@std@@YAPEAUVideoNodeCaps@CDevice@@PEAU12@_KAEAV?$allocator@UVideoNodeCaps@CDevice@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<CDevice::VideoNodeCaps>>(CDevice::VideoNodeCaps *,unsigned __int64,std::allocator<CDevice::VideoNodeCaps> &)
0x180055353  mov     [r14+8], rax
0x180055357  xor     eax, eax
0x180055359  mov     dword ptr [rsp+190h+var_154+4], eax
0x18005535d  test    esi, esi
0x18005535f  jz      loc_180055E0A
0x180055365  mov     r13d, 887A0020h
0x18005536b  lea     r15d, [rax+1]
0x18005536f  mov     ecx, eax
0x180055371  imul    rsi, rcx, 78h ; 'x'
0x180055375  mov     r14, [r14]
0x180055378  mov     rax, [rdi+15E0h]
0x18005537f  mov     r12d, [rax+rcx*4]
0x180055383  mov     [rsp+190h+var_160], r12d
0x180055388  cmp     dword ptr [rdi+0B3Ch], 0Fh
0x18005538f  jb      loc_1800555BB
0x180055395  mov     [rsp+190h+var_148], r12d
0x18005539a  xor     eax, eax
0x18005539c  mov     [rsp+190h+var_144], eax
0x1800553a0  mov     [rsp+190h+var_170], 8
0x1800553a8  lea     r9, [rsp+190h+var_148]
0x1800553ad  lea     edx, [rax+16h]
0x1800553b0  mov     rcx, rdi
0x1800553b3  call    ?GetCaps@CDevice@@QEAAJW4D3D12DDICAPS_TYPE_VIDEO_0020@@PEAX1I@Z; CDevice::GetCaps(D3D12DDICAPS_TYPE_VIDEO_0020,void *,void *,uint)
0x1800553b8  test    eax, eax
0x1800553ba  jns     short loc_1800553D3
0x1800553bc  lea     r8, aFailedGetcapsF_5; "Failed GetCaps for D3D12DDICAPS_TYPE_VI"...
0x1800553c3  mov     edx, r13d; int
0x1800553c6  call    ?ReportDriverError@CJournal@@QEAAXJPEBD@Z; CJournal::ReportDriverError(long,char const *)
0x1800553cb  mov     ecx, r13d; int
0x1800553ce  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800553d3  xorps   xmm0, xmm0
0x1800553d6  movdqu  [rsp+190h+var_120], xmm0
0x1800553dc  mov     [rbp+90h+var_110], 0
0x1800553e4  mov     eax, [rsp+190h+var_144]
0x1800553e8  test    eax, eax
0x1800553ea  jz      short loc_180055440
0x1800553ec  mov     edx, eax
0x1800553ee  lea     rcx, [rsp+190h+var_120]
0x1800553f3  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@UD3D12_VIDEO_EXTENSION_COMMAND_INFO@@V?$allocator@UD3D12_VIDEO_EXTENSION_COMMAND_INFO@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<D3D12_VIDEO_EXTENSION_COMMAND_INFO>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800553f8  mov     eax, [rsp+190h+var_144]
0x1800553fc  mov     [rbp+90h+var_100], r12d
0x180055400  mov     [rbp+90h+var_FC], eax
0x180055403  mov     rax, qword ptr [rsp+190h+var_120]
0x180055408  mov     [rbp+90h+var_F8], rax
0x18005540c  mov     [rsp+190h+var_170], 10h
0x180055414  lea     r9, [rbp+90h+var_100]
0x180055418  mov     edx, 17h
0x18005541d  mov     rcx, rdi
0x180055420  call    ?GetCaps@CDevice@@QEAAJW4D3D12DDICAPS_TYPE_VIDEO_0020@@PEAX1I@Z; CDevice::GetCaps(D3D12DDICAPS_TYPE_VIDEO_0020,void *,void *,uint)
0x180055425  test    eax, eax
0x180055427  jns     short loc_180055440
0x180055429  lea     r8, aFailedGetcapsF_12; "Failed GetCaps for D3D12DDICAPS_TYPE_VI"...
0x180055430  mov     edx, r13d; int
0x180055433  call    ?ReportDriverError@CJournal@@QEAAXJPEBD@Z; CJournal::ReportDriverError(long,char const *)
0x180055438  mov     ecx, r13d; int
0x18005543b  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180055440  mov     rbx, qword ptr [rsp+190h+var_120]
0x180055445  mov     r15, qword ptr [rsp+190h+var_120+8]
0x18005544a  cmp     rbx, r15
0x18005544d  jz      loc_18005559D
0x180055453  mov     rax, [rbx]
0x180055456  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x18005545d  jnz     short loc_180055483
0x18005545f  mov     rax, [rbx+8]
0x180055463  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x18005546a  jnz     short loc_180055483
0x18005546c  lea     r8, aOneOfTheComman_1; "One of the COMMAND_INFO returned from D"...
0x180055473  mov     edx, r13d; int
0x180055476  call    ?ReportDriverError@CJournal@@QEAAXJPEBD@Z; CJournal::ReportDriverError(long,char const *)
0x18005547b  mov     ecx, r13d; int
0x18005547e  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180055483  mov     ecx, [rbx+18h]; this
0x180055486  lea     eax, [rcx-1]
0x180055489  test    ecx, eax
0x18005548b  jz      short loc_1800554A4
0x18005548d  lea     r8, aOneOfTheComman_0; "One of the COMMAND_INFO returned from D"...
0x180055494  mov     edx, r13d; int
0x180055497  call    ?ReportDriverError@CJournal@@QEAAXJPEBD@Z; CJournal::ReportDriverError(long,char const *)
0x18005549c  mov     ecx, r13d; int
0x18005549f  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800554a4  test    dword ptr [rbx+18h], 0FFFFFF8Fh
0x1800554ab  jz      short loc_1800554C4
0x1800554ad  lea     r8, aOneOfTheComman_2; "One of the COMMAND_INFO returned from D"...
0x1800554b4  mov     edx, r13d; int
0x1800554b7  call    ?ReportDriverError@CJournal@@QEAAXJPEBD@Z; CJournal::ReportDriverError(long,char const *)
0x1800554bc  mov     ecx, r13d; int
0x1800554bf  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800554c4  mov     r8d, [rdi+0B3Ch]
0x1800554cb  lea     rcx, ?s_Commands@CRegisteredExtensionCommands@@0QBU?$pair@UCommand@CRegisteredExtensionCommands@@W4D3D12DDI_COMMAND_QUEUE_FLAGS@@@std@@B; this
0x1800554d2  mov     rdx, [rcx]
0x1800554d5  mov     rax, [rdx]
0x1800554d8  cmp     rax, [rbx]
0x1800554db  jnz     short loc_1800554F7
0x1800554dd  mov     rax, [rdx+8]
0x1800554e1  cmp     rax, [rbx+8]
0x1800554e5  jnz     short loc_1800554F7
0x1800554e7  cmp     r8d, [rcx+8]
0x1800554eb  jb      short loc_1800554F7
0x1800554ed  cmp     r8d, [rcx+0Ch]
0x1800554f1  jbe     loc_1800556C2
0x1800554f7  add     rcx, 18h
0x1800554fb  lea     rax, ?g_3dClosedOrRemovedCommandListDDIs_0074@@3UD3D12DDI_COMMAND_LIST_FUNCS_3D_0074@@B; D3D12DDI_COMMAND_LIST_FUNCS_3D_0074 const g_3dClosedOrRemovedCommandListDDIs_0074
0x180055502  cmp     rcx, rax
0x180055505  jnz     short loc_1800554D2
0x180055507  mov     rcx, rdi; this
0x18005550a  call    ?DeveloperModeEnabled@CDevice@@QEAA_NXZ; CDevice::DeveloperModeEnabled(void)
0x18005550f  test    al, al
0x180055511  jz      short loc_18005558B
0x180055513  mov     r9, [rbx+10h]
0x180055517  mov     r8d, [rbx+18h]
0x18005551b  mov     eax, r8d
0x18005551e  and     al, 1
0x180055520  neg     al
0x180055522  sbb     ecx, ecx
0x180055524  and     ecx, 3
0x180055527  mov     edx, ecx
0x180055529  or      edx, 4
0x18005552c  test    r8b, 2
0x180055530  cmovz   edx, ecx
0x180055533  mov     ecx, edx
0x180055535  or      ecx, 8
0x180055538  test    r8b, 4
0x18005553c  cmovz   ecx, edx
0x18005553f  mov     edx, ecx
0x180055541  or      edx, 10h
0x180055544  test    r8b, 10h
0x180055548  cmovz   edx, ecx
0x18005554b  mov     ecx, edx
0x18005554d  or      ecx, 20h
0x180055550  test    r8b, 20h
0x180055554  cmovz   ecx, edx
0x180055557  mov     eax, ecx
0x180055559  or      eax, 40h
0x18005555c  test    r8b, 40h
0x180055560  cmovz   eax, ecx
0x180055563  xor     ecx, ecx
0x180055565  movups  xmm0, xmmword ptr [rbx]
0x180055568  movdqu  [rbp+90h+var_D0], xmm0
0x18005556d  mov     [rbp+90h+var_C0], r9
0x180055571  mov     [rbp+90h+var_B8], eax
0x180055574  mov     [rbp+90h+var_B4], ecx
0x180055577  lea     rcx, [r14+38h]
0x18005557b  add     rcx, rsi
0x18005557e  lea     r8, [rbp+90h+var_D0]
0x180055582  lea     rdx, [rbp+90h+var_E0]
0x180055586  call    ??$emplace@U?$pair@U_GUID@@UDriverVideoExtensionCommand@CDevice@@@std@@@?$_Hash@V?$_Umap_traits@USGuid@@UDriverVideoExtensionCommand@CDevice@@V?$_Uhash_compare@USGuid@@V?$hash@USGuid@@@std@@U?$equal_to@USGuid@@@3@@std@@V?$allocator@U?$pair@$$CBUSGuid@@UDriverVideoExtensionCommand@CDevice@@@std@@@5@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUSGuid@@UDriverVideoExtensionCommand@CDevice@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@U_GUID@@UDriverVideoExtensionCommand@CDevice@@@1@@Z; std::_Hash<std::_Umap_traits<SGuid,CDevice::DriverVideoExtensionCommand,std::_Uhash_compare<SGuid,std::hash<SGuid>,std::equal_to<SGuid>>,std::allocator<std::pair<SGuid const,CDevice::DriverVideoExtensionCommand>>,0>>::emplace<std::pair<_GUID,CDevice::DriverVideoExtensionCommand>>(std::pair<_GUID,CDevice::DriverVideoExtensionCommand> &&)
0x18005558b  add     rbx, 20h ; ' '
0x18005558f  cmp     rbx, r15
0x180055592  jnz     loc_180055453
0x180055598  mov     rbx, qword ptr [rsp+190h+var_120]
0x18005559d  test    rbx, rbx
0x1800555a0  jz      short loc_1800555B5
0x1800555a2  mov     rdx, [rbp+90h+var_110]
0x1800555a6  sub     rdx, rbx
0x1800555a9  and     rdx, 0FFFFFFFFFFFFFFE0h
0x1800555ad  mov     rcx, rbx
0x1800555b0  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800555b5  mov     r15d, 1
0x1800555bb  cmp     dword ptr [rdi+0B3Ch], 0Dh
0x1800555c2  jb      loc_18005570B
0x1800555c8  mov     [rbp+90h+var_A0], r12d
0x1800555cc  xor     eax, eax
0x1800555ce  mov     [rbp+90h+var_9C], rax
0x1800555d2  mov     [rbp+90h+var_94], eax
0x1800555d5  mov     [rsp+190h+var_170], 10h
0x1800555dd  lea     r9, [rbp+90h+var_A0]
0x1800555e1  lea     edx, [rax+13h]
0x1800555e4  mov     rcx, rdi
0x1800555e7  call    ?GetCaps@CDevice@@QEAAJW4D3D12DDICAPS_TYPE_VIDEO_0020@@PEAX1I@Z; CDevice::GetCaps(D3D12DDICAPS_TYPE_VIDEO_0020,void *,void *,uint)
0x1800555ec  test    eax, eax
0x1800555ee  jns     short loc_180055607
0x1800555f0  lea     r8, aFailedGetcapsF_17; "Failed GetCaps for D3D12DDICAPS_TYPE_VI"...
0x1800555f7  mov     edx, r13d; int
0x1800555fa  call    ?ReportDriverError@CJournal@@QEAAXJPEBD@Z; CJournal::ReportDriverError(long,char const *)
0x1800555ff  mov     ecx, r13d; int
0x180055602  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180055607  mov     eax, dword ptr [rbp+90h+var_9C]
0x18005560a  mov     [rsi+r14], eax
0x18005560e  mov     eax, dword ptr [rbp+90h+var_9C+4]
0x180055611  mov     [rsi+r14+4], eax
0x180055616  mov     eax, [rbp+90h+var_94]
0x180055619  mov     [rsi+r14+8], eax
0x18005561e  mov     rax, [rdi+2B8h]
0x180055625  test    rax, rax
0x180055628  jz      loc_180055718
0x18005562e  mov     rax, [rax+8]
0x180055632  test    rax, rax
0x180055635  jz      loc_180055718
0x18005563b  xor     ecx, ecx
0x18005563d  mov     [rbp+90h+var_B0], rcx
0x180055641  mov     [rbp+90h+var_A8], ecx
0x180055644  mov     rbx, [rdi+2F8h]
0x18005564b  mov     rdx, [rbx+28h]
0x18005564f  mov     r8d, [rdx+1C0h]
0x180055656  mov     dword ptr [rbp+90h+var_B0], r8d
0x18005565a  mov     dword ptr [rbp+90h+var_B0+4], 3
0x180055661  lea     rcx, [rbp+90h+var_B0]
0x180055665  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005566a  mov     r8d, r15d
0x18005566d  mov     edx, eax
0x18005566f  mov     rcx, rbx
0x180055672  call    ?NTStatusToHResult@CDevice@NDXGI@@QEAAJJW4EErrorTranslationBehavior@2@@Z; NDXGI::CDevice::NTStatusToHResult(long,NDXGI::EErrorTranslationBehavior)
0x180055677  test    eax, eax
0x180055679  js      short loc_1800556F3
0x18005567b  cmp     [rbp+90h+var_A8], 2
0x18005567f  jnz     loc_180055718
0x180055685  mov     dword ptr [rsi+r14+8], 0
0x18005568e  mov     [rsp+190h+var_170], 0
0x180055696  lea     r8, aVidencEngineAc; "VidEnc: ENGINE_ACCESS_DENIED - FeatureA"...
0x18005569d  xor     edx, edx
0x18005569f  call    ?RecordJournal@CJournal@@QEAAXIPEBD_NW4RecordJournalOptions@@@Z; CJournal::RecordJournal(uint,char const *,bool,RecordJournalOptions)
0x1800556a4  test    cs:Microsoft_Windows_Direct3D12EnableBits, 4
0x1800556ab  jz      short loc_180055718
0x1800556ad  mov     r8, [rdi+300h]
0x1800556b4  lea     rdx, EventD3D12VideoEncodeEngineAccessDenied
0x1800556bb  call    McTemplateU0p_EtwEventWriteTransfer
0x1800556c0  jmp     short loc_180055718
0x1800556c2  mov     eax, [rcx+10h]
0x1800556c5  cmp     eax, 70h ; 'p'
0x1800556c8  jz      loc_180055507
0x1800556ce  cmp     eax, [rbx+18h]
0x1800556d1  jz      loc_180055513
0x1800556d7  lea     r8, aOneOfTheComman; "One of the COMMAND_INFO returned from D"...
0x1800556de  mov     edx, r13d; int
0x1800556e1  call    ?ReportDriverError@CJournal@@QEAAXJPEBD@Z; CJournal::ReportDriverError(long,char const *)
0x1800556e6  mov     ecx, r13d; int
0x1800556e9  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x1800556ee  jmp     loc_180055513
0x1800556f3  mov     [rsp+190h+var_170], 0
0x1800556fb  lea     r8, aFailedCheckeng; "Failed CheckEngineAccess for Video Enco"...
0x180055702  mov     edx, eax
0x180055704  call    ?RecordJournal@CJournal@@QEAAXIPEBD_NW4RecordJournalOptions@@@Z; CJournal::RecordJournal(uint,char const *,bool,RecordJournalOptions)
0x180055709  jmp     short loc_180055718
0x18005570b  mov     [rsi+r14], r15d
0x18005570f  mov     qword ptr [rsi+r14+4], 1
0x180055718  cmp     dword ptr [rdi+0B3Ch], 10h
0x18005571f  jb      loc_1800557DF
0x180055725  mov     [rsp+190h+var_140], r12d
0x18005572a  xor     eax, eax
0x18005572c  mov     [rsp+190h+var_13C], eax
0x180055730  mov     [rsp+190h+var_170], 8
0x180055738  lea     r9, [rsp+190h+var_140]
0x18005573d  lea     edx, [rax+1Dh]
0x180055740  mov     rcx, rdi
0x180055743  call    ?GetCaps@CDevice@@QEAAJW4D3D12DDICAPS_TYPE_VIDEO_0020@@PEAX1I@Z; CDevice::GetCaps(D3D12DDICAPS_TYPE_VIDEO_0020,void *,void *,uint)
0x180055748  test    eax, eax
0x18005574a  jns     short loc_180055755
0x18005574c  lea     r8, aFailedGetcapsF_36; "Failed GetCaps for D3D12DDICAPS_TYPE_VI"...
0x180055753  jmp     short loc_180055766
  ... truncated ...
```
