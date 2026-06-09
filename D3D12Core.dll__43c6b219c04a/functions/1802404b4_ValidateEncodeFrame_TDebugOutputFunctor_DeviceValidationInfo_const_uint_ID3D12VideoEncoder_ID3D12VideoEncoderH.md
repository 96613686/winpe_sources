# ValidateEncodeFrame(TDebugOutputFunctor &,DeviceValidationInfo const &,uint,ID3D12VideoEncoder *,ID3D12VideoEncoderHeap1 *,D3D12_VIDEO_ENCODER_ENCODEFRAME_INPUT_ARGUMENTS1 const *,D3D12_VIDEO_ENCODER_ENCODEFRAME_OUTPUT_ARGUMENTS1 const *)

- ea: `0x1802404b4`
- end: `0x1802448ab`
- name: `?ValidateEncodeFrame@@YAJAEAUTDebugOutputFunctor@@AEBUDeviceValidationInfo@@IPEAUID3D12VideoEncoder@@PEAUID3D12VideoEncoderHeap1@@PEBUD3D12_VIDEO_ENCODER_ENCODEFRAME_INPUT_ARGUMENTS1@@PEBUD3D12_VIDEO_ENCODER_ENCODEFRAME_OUTPUT_ARGUMENTS1@@@Z`
- size: `17399`
- prototype: `__int64 __usercall@<rax>(struct TDebugOutputFunctor *@<rcx>, const struct DeviceValidationInfo *@<rdx>, unsigned int@<r8d>, struct ID3D12VideoEncoder *@<r9>, struct ID3D12VideoEncoderHeap1 *, const struct D3D12_VIDEO_ENCODER_ENCODEFRAME_INPUT_ARGUMENTS1 *, const struct D3D12_VIDEO_ENCODER_ENCODEFRAME_OUTPUT_ARGUMENTS1 *)`
- caller_count: `1`
- callee_count: `32`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18023d364`

## callees

- `0x180006b40`
- `0x18000b010`
- `0x18000bb58`
- `0x180025550`
- `0x18002ef50`
- `0x18004bccc`
- `0x18004ed34`
- `0x18005a444`
- `0x18005f00c`
- `0x18005fd58`
- `0x1800abc10`
- `0x1800abe94`
- `0x1800ba8a0`
- `0x1800bb480`
- `0x1800bc010`
- `0x1800bc094`
- `0x180125b04`
- `0x180125cb4`
- `0x180132850`
- `0x18023968c`
- `0x18023c518`
- `0x1802404b4`
- `0x1802448b4`
- `0x180244aec`
- `0x180244f38`
- `0x18024532c`
- `0x180245468`
- `0x180245c4c`
- `0x180246e70`
- `0x18025cda8`
- `0x18025ce10`
- `0x180262020`

## string_xrefs

- `0x180240661`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - pOutputArguments->Bitstream.SubregionOutputBuffers.ppSubregionBitstreams cannot be null.`
- `0x18024063d`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - pOutputArguments->Bitstream.SubregionOutputBuffers.pSubregionBitstreamsBaseOffsets cannot be null.`
- `0x1802406a9`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - pOutputArguments->Bitstream.SubregionOutputBuffers.ppSubregionOffsets cannot be null.`
- `0x180240685`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - pOutputArguments->Bitstream.SubregionOutputBuffers.ppSubregionSizes cannot be null.`
- `0x1802405b9`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - pInputArguments->pInputFrame cannot be null.`
- `0x180240595`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - pOutputArguments cannot be null.`
- `0x180240601`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - pOutputArguments->Bitstream.FrameOutputBuffer.pBuffer cannot be null.`
- `0x1802405da`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - pOutputArguments->EncoderOutputMetadata.pBuffer cannot be null.`
- `0x180240535`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - pEncoder cannot be null.`
- `0x180240575`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - pInputArguments cannot be null.`
- `0x180240555`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - pHeap cannot be null.`
- `0x180240796`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - pOutputArguments->Bitstream.SubregionOutputBuffers.ppSubregionFences[%d] cannot be null.`
- `0x18024076f`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - pOutputArguments->Bitstream.SubregionOutputBuffers.ppSubregionOffsets[%d] cannot be null.`
- `0x180240805`: `ID3D12VideoEncodeCommandList::EncodeFrame Failure on call to CheckFeatureSupport(D3D12_FEATURE_VIDEO_ARCHITECTURE,...).`
- `0x180244860`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - Invalid D3D12_VIDEO_ENCODER_COMPRESSED_BITSTREAM_NOTIFICATION_MODE set.`
- `0x1802406ee`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - pOutputArguments->Bitstream.SubregionOutputBuffers.pSubregionFenceValues cannot be null.`
- `0x1802406cd`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - pOutputArguments->Bitstream.SubregionOutputBuffers.ppSubregionFences cannot be null.`
- `0x180240748`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - pOutputArguments->Bitstream.SubregionOutputBuffers.ppSubregionSizes[%d] cannot be null.`
- `0x180240721`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - pOutputArguments->Bitstream.SubregionOutputBuffers.ppSubregionBitstreams[%d] cannot be null.`
- `0x180240920`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct  Target resolution must be within the associated heap allowed resolution list.`
- `0x18024093e`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - Invalid pInputArguments->PictureControlDesc.Flags.`
- `0x1802408ff`: `ID3D12VideoEncodeCommandList::EncodeFrame validation failure - Error produced while validating encoder heap resolution list - HRESULT: %x.`
- `0x18024085a`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - Invalid pInputArguments->SequenceControlDesc.IntraRefreshConfig.Mode.`
- `0x180240840`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - Invalid pInputArguments->SequenceControlDesc.Flags.`
- `0x18024089e`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - Invalid pInputArguments->SequenceControlDesc.CodecGopSequence.`
- `0x180240a0e`: `The resource in D3D12_VIDEO_ENCODER_COMPRESSED_BITSTREAM must have heap type D3D12_HEAP_TYPE_DEFAULT, D3D12_HEAP_TYPE_UPLOAD, D3D12_HEAP_TYPE_GPU_UPLOAD, or D3D12_HEAP_TYPE_CUSTOM. For D3D12_HEAP_TYPE_CUSTOM, CPUPageProperty must not be equal to D3D12_CPU_PAGE_PROPERTY_WRITE_BACK.See D3D12_FEATURE_VIDEO_ARCHITECTURE.`
- `0x180240a99`: `The resource in D3D12_VIDEO_ENCODER_ENCODEFRAME_OUTPUT_ARGUMENTS.EncoderOutputMetadata.pBuffer must have heap type D3D12_HEAP_TYPE_DEFAULT, D3D12_HEAP_TYPE_UPLOAD, D3D12_HEAP_TYPE_GPU_UPLOAD, or D3D12_HEAP_TYPE_CUSTOM. For D3D12_HEAP_TYPE_CUSTOM, CPUPageProperty must not be equal to D3D12_CPU_PAGE_PROPERTY_WRITE_BACK.See D3D12_FEATURE_VIDEO_ARCHITECTURE.`
- `0x1802409f4`: `The resource in D3D12_VIDEO_ENCODER_COMPRESSED_BITSTREAM must not be a reserved resource.`
- `0x1802409d7`: `The resource in D3D12_VIDEO_ENCODER_COMPRESSED_BITSTREAM must be a buffer.`
- `0x180240e37`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - pOutputArguments->ReconstructedPicture.pReconstructedPicture cannot be null.if D3D12_VIDEO_ENCODER_PICTURE_CONTROL_FLAG_USED_AS_REFERENCE_PICTURE is set`
- `0x180240e06`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - pInputArguments->pInputFrame must NOT have the D3D12_RESOURCE_FLAG_VIDEO_ENCODE_REFERENCE_ONLY set.`
- `0x180240b2f`: `D3D12_VIDEO_ENCODER_ENCODEFRAME_INPUT_ARGUMENTS::pInputFrame must have heap type D3D12_HEAP_TYPE_DEFAULT, D3D12_HEAP_TYPE_UPLOAD, D3D12_HEAP_TYPE_GPU_UPLOAD, or D3D12_HEAP_TYPE_CUSTOM. For D3D12_HEAP_TYPE_CUSTOM, CPUPageProperty must not be equal to D3D12_CPU_PAGE_PROPERTY_WRITE_BACK.See D3D12_FEATURE_VIDEO_ARCHITECTURE.`
- `0x180242595`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - H264 Picture control structure - IDR or I Frames must not contain references information.`
- `0x1802424f8`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - H264 Picture control structure - adaptive_ref_pic_marking_mode_flag is set but RefPicMarkingOperationsCommandsCount or pRefPicMarkingOperationsCommands are not set correctly.`
- `0x180242608`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - H264 Picture control structure - Number of L0 elements (%d) for P frame exceeded respect to MaxL0ReferencesForB (%d) or Number of L1 elements (%d) for P frame exceeded respect to MaxL1ReferencesForB (%d).`
- `0x1802425c4`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - H264 Picture control structure - Number of L0 elements (%d) for P frame exceeded respect to MaxL0ReferencesForP (%d).`
- `0x180242462`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - H264 Picture control structure - P or B frames are not supported as D3D12_VIDEO_ENCODER_CODEC_PICTURE_CONTROL_SUPPORT_H264.capMaxDPBCapacity is reporting zero.`
- `0x180241380`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - CheckFeatureSupport(D3D12_FEATURE_VIDEO_ENCODER_CODEC_PICTURE_CONTROL_SUPPORT,...) for the given input returned failure or not supported.`
- `0x1802424c1`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - H264 Picture control structure - B frame not supported as D3D12_VIDEO_ENCODER_CODEC_PICTURE_CONTROL_SUPPORT_H264.MaxL0ReferencesForB or D3D12_VIDEO_ENCODER_CODEC_PICTURE_CONTROL_SUPPORT_H264.MaxL1ReferencesForB are reporting zero.`
- `0x180242490`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - H264 Picture control structure - P frame not supported as D3D12_VIDEO_ENCODER_CODEC_PICTURE_CONTROL_SUPPORT_H264.MaxL0ReferencesForP is reporting zero.`
- `0x180240f17`: `The NodeMask of the ID3D12VideoEncoder is not supported by the NodeMask of this command list.`
- `0x180240ead`: `The NodeMask of the ID3D12VideoEncoderHeap is not supported by the NodeMask of this command list.`
- `0x18024205e`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - HEVC Picture control structure - Number of unique elements in L0 + L1 lists (%d) has to be exactly the same as the number of DPB entries marked as IsRefUsedByCurrentPic (%d) for current frame.`
- `0x180242019`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - HEVC Picture control structure - num_ref_idx_l0_active (%d) for P frame exceeded respect to MaxL0ReferencesForB (%d) or num_ref_idx_l1_active (%d) for P frame exceeded respect to MaxL1ReferencesForB (%d).`
- `0x180242132`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - Number of reference pictures addressable by L0 and L1 lists according to caps (MaxLXReferencesForX) exceeds the MaxDPBCapacity value reported. Max L0 size for P: %d Max L0 size for B: %d Max L1 size: %d Max number of adressable unique frames in DPB between L0 and L1 lists: %d Reported maximum DPB size %d`
- `0x180242765`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - Number of reference pictures addressable by L0 and L1 lists according to caps (MaxLXReferencesForX) exceeds the MaxDPBCapacity value reported. Max L0 size for P: %d Max L0 size for B: %d Max L1 size: %d Max number of adressable unique frames in DPB between L0 and L1 lists: %d Reported maximum DPB size %d`
- `0x1802420d9`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - HEVC Picture control structure - Indices in L0 or L1 lists are out of bounds, exceeding the ReferenceFramesReconPictureDescriptorsCount size.`
- `0x180241f77`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - HEVC Picture control structure - IDR or I Frames must not contain num_ref_idx_l0_active_minus1 (%d)/num_ref_idx_l1_active_minus1  (%d)> 0.`
- `0x180241f41`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - HEVC Picture control structure - IDR or I Frames must not contain L0/L1 references information.`
- `0x180241fcc`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - HEVC Picture control structure - num_ref_idx_l0_active (%d) for P frame exceeded respect to MaxL0ReferencesForP (%d).`
- `0x180241f93`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - HEVC Picture control structure - IDR or I Frames must not use frame references from the DPB (Check the IsRefUsedByCurrentPic flag setting in DPB descriptor).`
- `0x180241e31`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - HEVC Picture control structure - B frame not supported as D3D12_VIDEO_ENCODER_CODEC_PICTURE_CONTROL_SUPPORT_HEVC.MaxL0ReferencesForB or D3D12_VIDEO_ENCODER_CODEC_PICTURE_CONTROL_SUPPORT_H264.MaxL1ReferencesForB are reporting zero.`
- `0x180241e05`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - HEVC Picture control structure - P frame not supported as D3D12_VIDEO_ENCODER_CODEC_PICTURE_CONTROL_SUPPORT_HEVC.MaxL0ReferencesForP is reporting zero.`
- `0x180241eea`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - HEVC Picture control structure - Number of LTR in L0/L1 lists (%d) exceeds maximum supported number of LTRs (%d) for current frame`
- `0x180241ec4`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - HEVC Picture control structure - Long term references detected in picture control used for this frame but not enabled in associated encoder, please see D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_FLAG_ENABLE_LONG_TERM_REFERENCES.`
- `0x18024270e`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - H264 Picture control structure - Number of LTR in L0/L1 lists (%d) exceeds maximum supported number of LTRs (%d) for current frame`
- `0x1802426ea`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - H264 Picture control structure - Indices in L0 or L1 lists are out of bounds, exceeding the ReferenceFramesReconPictureDescriptorsCount size.`
- `0x180241dd5`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - HEVC Picture control structure - P or B frames are not supported as D3D12_VIDEO_ENCODER_CODEC_PICTURE_CONTROL_SUPPORT_HEVC.capMaxDPBCapacity is reporting zero.`
- `0x180242792`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - Number of distinct reference pictures indexed from L0 and L1 lists into ReferenceFramesReconPictureDescriptorsCount exceeds the MaxDPBCapacity value reported Current DPB size: %d Reported maximum DPB size %d`
- `0x1802423b3`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - ReferenceFrames.NumTexture2Ds does not match with ReferenceFramesReconPictureDescriptorsCount.`
- `0x180242384`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - Number of distinct reference pictures indexed from pList0ReferenceFrames and List1ReferenceFramesCount lists into ReferenceFramesReconPictureDescriptorsCount exceeds the MaxDPBCapacity value reported Current DPB size: %d Reported maximum DPB size %d`
- `0x1802414d4`: `D3D12VideoEncodeCommandList::EncodeFrame arguments not supported - Call to CheckFeatureCaps (D3D12_FEATURE_VIDEO_ENCODER_CODEC_CONFIGURATION_SUPPORT, ...) returned failure or not supported.`
- `0x180242180`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - HEVC Picture control structure - num_ref_idx_l1_active_minus1 + 1 (%d) cannot be higher than List1ReferenceFramesCount(%d).`
- `0x18024215a`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - HEVC Picture control structure - num_ref_idx_l0_active_minus1 + 1 (%d) cannot be higher than List0ReferenceFramesCount(%d).`
- `0x1802421e3`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - HEVC Picture control structure - List1RefPicModificationsCount (%d) must be equal to num_ref_idx_l1_active_minus1 + 1 (%d).`
- `0x1802421ab`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - HEVC Picture control structure - List0RefPicModificationsCount (%d) must be equal to num_ref_idx_l0_active_minus1 + 1 (%d).`
- `0x1802417d4`: `D3D12_VIDEO_ENCODER_AV1_PICTURE_CONTROL_FLAGS - D3D12_VIDEO_ENCODER_AV1_PICTURE_CONTROL_FLAG_ALLOW_INTRA_BLOCK_COPY is required in RequiredFeatureFlags but not set.`
- `0x1802415e3`: `D3D12_VIDEO_ENCODER_AV1_PICTURE_CONTROL_FLAGS arguments are not supported - D3D12_VIDEO_ENCODER_AV1_PICTURE_CONTROL_FLAG_ALLOW_INTRA_BLOCK_COPY not supported.`
- `0x180241c18`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - Number of distinct ReferenceFramesReconPictureDescriptors[i].ReconstructedPictureResourceIndex into ppTextures exceeds maximum MaxUniqueReferencesPerFrame reported Current DPB size: %d Reported maximum DPB size %d`
- `0x180241c7e`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - AV1 Picture control structure - RefreshFrameFlags must be 0xFF for D3D12_VIDEO_ENCODER_AV1_FRAME_TYPE_KEY_FRAME.`
- `0x180241c4d`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - AV1 Picture control structure - WarpedMotionInfo not supported. See values supported values for D3D12_VIDEO_ENCODER_AV1_REFERENCE_WARPED_MOTION_TRANSFORMATION_FLAGS.`
- `0x180241a7d`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - Reference descriptor %d - TemporalLayerIndexPlus1 %d must be in the range [0..D3D12_VIDEO_ENCODER_AV1_CODEC_CONFIGURATION_SUPPORT.MaxTemporalLayers (%d)].`
- `0x1802419cf`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - AV1 Picture control structure - SpatialLayerIndexPlus1 %d must be in the range [0..D3D12_VIDEO_ENCODER_AV1_CODEC_CONFIGURATION_SUPPORT.MaxSpatialLayers (%d)].`
- `0x180241ac1`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - Reference descriptor %d - SpatialLayerIndexPlus1 %d must be in the range [0..D3D12_VIDEO_ENCODER_AV1_CODEC_CONFIGURATION_SUPPORT.MaxSpatialLayers (%d)].`
- `0x180241944`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - AV1 Picture control structure - Requested FrameType (%d) is not reported as supported in D3D12_VIDEO_ENCODER_CODEC_PICTURE_CONTROL_SUPPORT_AV1.SupportedFrameTypes (%x)`
- `0x18024191b`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - AV1 Picture control structure - Only key frames are supported as D3D12_VIDEO_ENCODER_CODEC_PICTURE_CONTROL_SUPPORT_AV1 is reporting zero supported references.`
- `0x1802419a0`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - AV1 Picture control structure - TemporalLayerIndexPlus1 %d must be in the range [0..D3D12_VIDEO_ENCODER_AV1_CODEC_CONFIGURATION_SUPPORT.MaxTemporalLayers (%d)].`
- `0x18024196a`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - AV1 Picture control structure - ReferenceIndices[%d] index is out of bounds of [0..7] to index into ReferenceFramesReconPictureDescriptors.`
- `0x1802418ec`: `D3D12_VIDEO_ENCODER_AV1_PICTURE_CONTROL_FLAGS - D3D12_VIDEO_ENCODER_AV1_PICTURE_CONTROL_FLAG_DISABLE_CDF_UPDATE is not supported by driver with D3D12_VIDEO_ENCODER_AV1_FEATURE_FLAG_DISABLE_CDF_UPDATE_UNSUPPORTED.`
- `0x1802427e9`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - ReferenceFramesReconPictureDescriptors has (%d) entries but the selected codec supports at most (%d) entries.`
- `0x180241c9c`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - AV1 Picture control structure - Key Frames must not use any references. Must set all ReconstructedPictureResourceIndex DPB entries to D3D12_VIDEO_ENCODER_AV1_INVALID_DPB_RESOURCE_INDEX.`
- `0x18024282a`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - DPB descriptors for the current picture have temporal layers indices higher than the current picture temporal layer index.`
- `0x18024280c`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - DPB descriptors have indices set in ReconstructedPictureResourceIndex out of bounds respect to ReferenceFramesReconPictureDescriptorsCount (%d).`
- `0x180242d50`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - CheckFeatureSupport(D3D12_FEATURE_VIDEO_ENCODER_SUPPORT2,...) returned the following flags ValidationFlags: 0x%x SupportFlags: 0x%x`
- `0x180242bbd`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - CheckFeatureSupport(D3D12_FEATURE_VIDEO_ENCODER_SUPPORT2,...) for the given input returned failure.`
- `0x180242f9f`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - D3D12_VIDEO_ENCODER_OPTIONAL_METADATA_ENABLE_FLAG_RC_BIT_ALLOCATION_MAP was requested but D3D12_VIDEO_ENCODER_SUPPORT_FLAG_PER_BLOCK_RC_BIT_ALLOCATION_MAP_METADATA_AVAILABLE is not supported.`
- `0x180242f71`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - D3D12_VIDEO_ENCODER_OPTIONAL_METADATA_ENABLE_FLAG_SATD_MAP was requested but D3D12_VIDEO_ENCODER_SUPPORT_FLAG_PER_BLOCK_SATD_MAP_METADATA_AVAILABLE is not supported.`
- `0x180242ffb`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - D3D12_VIDEO_ENCODER_OPTIONAL_METADATA_ENABLE_FLAG_SUBREGIONS_PSNR was requested but D3D12_VIDEO_ENCODER_SUPPORT_FLAG_SUBREGIONS_PSNR_METADATA_AVAILABLE is not supported.`
- `0x180242fcd`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - D3D12_VIDEO_ENCODER_OPTIONAL_METADATA_ENABLE_FLAG_FRAME_PSNR was requested but D3D12_VIDEO_ENCODER_SUPPORT_FLAG_FRAME_PSNR_METADATA_AVAILABLE is not supported.`
- `0x180242ee3`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - Invalid D3D12_VIDEO_ENCODER_SUBREGION_COMPRESSED_BITSTREAM_BUFFER_MODE.`
- `0x180242eda`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - D3D12_VIDEO_ENCODER_SUBREGION_COMPRESSED_BITSTREAM_BUFFER_MODE_SINGLE_BUFFER was requested but D3D12_VIDEO_ENCODER_HEAP_FLAG_ALLOW_SUBREGION_NOTIFICATION_SINGLE_BUFFER is not set in the encoder heap.`
- `0x180242f43`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - D3D12_VIDEO_ENCODER_OPTIONAL_METADATA_ENABLE_FLAG_QP_MAP was requested but D3D12_VIDEO_ENCODER_SUPPORT_FLAG_PER_BLOCK_QP_MAP_METADATA_AVAILABLE is not supported.`
- `0x180242f10`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - D3D12_VIDEO_ENCODER_HEAP_FLAG_ENABLE_SUBREGION_NOTIFICATION_SEQUENTIAL_SIGNALING is set in the encoder heap but D3D12_VIDEO_ENCODER_SUPPORT_FLAG_SUBREGION_NOTIFICATION_SEQUENTIAL_SIGNALING_AVAILABLE is not supported.`
- `0x180242e87`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - D3D12_VIDEO_ENCODER_SUBREGION_COMPRESSED_BITSTREAM_BUFFER_MODE_ARRAY_OF_BUFFERS was requested but D3D12_VIDEO_ENCODER_SUPPORT_FLAG_SUBREGION_NOTIFICATION_ARRAY_OF_BUFFERS_AVAILABLE is not supported.`
- `0x180242e1c`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - pInputArguments->PictureControlDesc.ReferenceFrames.ppTexture2Ds MUST ALL have the D3D12_RESOURCE_FLAG_VIDEO_ENCODE_REFERENCE_ONLY set when D3D12_VIDEO_ENCODER_SUPPORT_FLAG_READABLE_RECONSTRUCTED_PICTURE_LAYOUT_AVAILABLE is not supported.`
- `0x180242ec0`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - D3D12_VIDEO_ENCODER_SUBREGION_COMPRESSED_BITSTREAM_BUFFER_MODE_SINGLE_BUFFER was requested but D3D12_VIDEO_ENCODER_SUPPORT_FLAG_SUBREGION_NOTIFICATION_SINGLE_BUFFER_AVAILABLE is not supported.`
- `0x180242ea1`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - D3D12_VIDEO_ENCODER_SUBREGION_COMPRESSED_BITSTREAM_BUFFER_MODE_ARRAY_OF_BUFFERS was requested but D3D12_VIDEO_ENCODER_HEAP_FLAG_ALLOW_SUBREGION_NOTIFICATION_ARRAY_OF_BUFFERS is not set in the encoder heap.`
- `0x180242dc8`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - pOutputArguments->ReconstructedPicture.pReconstructedPicture MUST have the D3D12_RESOURCE_FLAG_VIDEO_ENCODE_REFERENCE_ONLY set when D3D12_VIDEO_ENCODER_SUPPORT_FLAG_READABLE_RECONSTRUCTED_PICTURE_LAYOUT_AVAILABLE is not supported.`
- `0x1802433a7`: `D3D12_VIDEO_ENCODER_FRAME_ANALYSIS::pDownscaledFrame must have heap type D3D12_HEAP_TYPE_DEFAULT, D3D12_HEAP_TYPE_UPLOAD, D3D12_HEAP_TYPE_GPU_UPLOAD, or D3D12_HEAP_TYPE_CUSTOM. For D3D12_HEAP_TYPE_CUSTOM, CPUPageProperty must not be equal to D3D12_CPU_PAGE_PROPERTY_WRITE_BACK.See D3D12_FEATURE_VIDEO_ARCHITECTURE.`
- `0x1802432a6`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - D3D12_FEATURE_DATA_VIDEO_ENCODER_RESOLUTION_SUPPORT_LIMITS1.FrameAnalysis.SupportFlags (0x%x) does not support the current frame type`
- `0x180243152`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - Rate control QualityVsSpeed (%d) is higher than reported MaxQualityVsSpeed (%d).`
- `0x18024330d`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - FrameAnalysisReconstructedPicture.pReconstructedPicture cannot be NULL when D3D12_VIDEO_ENCODER_PICTURE_CONTROL_FLAG_USED_AS_REFERENCE_PICTURE set and D3D12_VIDEO_ENCODER_RATE_CONTROL_FRAME_ANALYSIS_SUPPORT_FLAG_EXTERNAL_DPB_DOWNSCALING not supported`
- `0x1802432d5`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - D3D12_VIDEO_ENCODER_HEAP_FLAG_ALLOW_RATE_CONTROL_FRAME_ANALYSIS not set in the encoder heap passed to EncodeFrame`
- `0x18024304b`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - Resolution reconfiguration was requested but it's not supported.`
- `0x180243023`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - Rate control reconfiguration was requested but it's not supported.`
- `0x1802430b9`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - Rate control optional mode %s is requested but it's not reported in the SupportFlags: %s.`
- `0x180243073`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - Subregion layout reconfiguration was requested but it's not supported.`
- `0x180243855`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - pInputArguments->PictureControlDesc.FrameAnalysis.DownscaledReferences.ppTexture2Ds MUST ALL have the D3D12_RESOURCE_FLAG_VIDEO_ENCODE_REFERENCE_ONLY set when D3D12_VIDEO_ENCODER_SUPPORT_FLAG_READABLE_RECONSTRUCTED_PICTURE_LAYOUT_AVAILABLE is not supported.`
- `0x1802437fe`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - pOutputArguments->FrameAnalysisReconstructedPicture.pReconstructedPicture MUST have the D3D12_RESOURCE_FLAG_VIDEO_ENCODE_REFERENCE_ONLY set when D3D12_VIDEO_ENCODER_SUPPORT_FLAG_READABLE_RECONSTRUCTED_PICTURE_LAYOUT_AVAILABLE is not supported.`
- `0x18024360b`: `The D3D12_VIDEO_ENCODER_FRAME_ANALYSIS::DownscaledReferences reference frame at index %d must have heap type D3D12_HEAP_TYPE_DEFAULT, D3D12_HEAP_TYPE_UPLOAD, D3D12_HEAP_TYPE_GPU_UPLOAD, or D3D12_HEAP_TYPE_CUSTOM. For D3D12_HEAP_TYPE_CUSTOM, CPUPageProperty must not be equal to D3D12_CPU_PAGE_PROPERTY_WRITE_BACK.See D3D12_FEATURE_VIDEO_ARCHITECTURE.`
- `0x180244021`: `The resource in SubregionOutputBuffers.ppSubregionOffsets[%d] must have heap type D3D12_HEAP_TYPE_DEFAULT, D3D12_HEAP_TYPE_UPLOAD, D3D12_HEAP_TYPE_GPU_UPLOAD, or D3D12_HEAP_TYPE_CUSTOM. For D3D12_HEAP_TYPE_CUSTOM, CPUPageProperty must not be equal to D3D12_CPU_PAGE_PROPERTY_WRITE_BACK.See D3D12_FEATURE_VIDEO_ARCHITECTURE.`
- `0x180243d91`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - ColWidths[%d] number specified (%d) for frame subregions mode . D3D12_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_MODE_CONFIGURABLE_GRID_PARTITION out of minimum %d or maximum %d supported bounds`
- `0x180243e97`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - RowCount number specified (%d) for frame subregions mode %d. out of minimum %d or maximum %d supported bounds`
- `0x1802439cf`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - SubregionOutputBuffers.ExpectedSubregionCount (%d). is less than the expected number of slices for this frame %d. Please increase ExpectedSubregionCount.`
- `0x180243e53`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - ColWidths[%d] = %d RowHeights[%d] = %d for frame subregions mode . D3D12_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_MODE_CONFIGURABLE_GRID_PARTITION out of %d or maximum %d supported bounds for tile area`
- `0x180243ada`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - Subregions number specified (%d) for frame subregions mode %d. exceeds the maximum supported number of subregions %d`
- `0x180243a70`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - Subregion tile partition is only available for AV1 codec.`
- `0x180243ce1`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - ColCount number specified (%d) for frame subregions mode %d. out of minimum %d or maximum %d supported bounds`
- `0x180243eb0`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - CheckFeatureSupport(D3D12_FEATURE_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_CONFIG,...) for the given input returned failure.`
- `0x180243fed`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - Subregions number inferred (%d) for frame subregions mode . D3D12_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_MODE_SQUARE_UNITS_PER_SUBREGION_ROW_UNALIGNED exceeds the maximum supported number of subregions %d`
- `0x1802438c7`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - The associated encoder heap has D3D12_VIDEO_ENCODER_HEAP_FLAG_ALLOW_RATE_CONTROL_FRAME_ANALYSIS and Pow2DownscaleFactor > 0,  and this EncodeFrame command does NOT enable D3D12_VIDEO_ENCODER_RATE_CONTROL_FLAG_ENABLE_FRAME_ANALYSIS. However the driver does NOT support D3D12_VIDEO_ENCODER_RATE_CONTROL_FRAME_ANALYSIS_SUPPORT_FLAG_DYNAMIC_1ST_PASS_SKIP to disable two pass dynamically in given frames. When this flag is not suppor`
- `0x180243f52`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - Subregions number specified (%d) for frame subregions mode . D3D12_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_MODE_UNIFORM_PARTITIONING_SUBREGIONS_PER_FRAME exceeds the maximum supported number of subregions %d`
- `0x180243fad`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - Subregions number inferred (%d) for frame subregions mode . D3D12_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_MODE_UNIFORM_PARTITIONING_ROWS_PER_SUBREGION exceeds the maximum supported number of subregions %d`
- `0x1802441b1`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - Intra refresh index specified (%d). exceeds the intra refresh frames duration specified %d. IR index range is [0..IntraRefreshDuration)`
- `0x18024418d`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - Intra refresh duration specified (%d). exceeds the maximum supported number of intra refresh frames duration %d`
- `0x180244141`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - SubregionOutputBuffers.ppSubregionFences[%d] must be either monitored fences with GPU access or native fences.`
- `0x180244133`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - SubregionOutputBuffers.ppSubregionFences[%d] cannot have D3D12_FENCE_FLAG_SHARED set when driver uses monitored fences.`
- `0x1802440a8`: `The resource in SubregionOutputBuffers.ppSubregionSizes[%d] must have heap type D3D12_HEAP_TYPE_DEFAULT, D3D12_HEAP_TYPE_UPLOAD, D3D12_HEAP_TYPE_GPU_UPLOAD, or D3D12_HEAP_TYPE_CUSTOM. For D3D12_HEAP_TYPE_CUSTOM, CPUPageProperty must not be equal to D3D12_CPU_PAGE_PROPERTY_WRITE_BACK.See D3D12_FEATURE_VIDEO_ARCHITECTURE.`
- `0x18024461b`: `The D3D12_VIDEO_ENCODER_SUBREGION_COMPRESSED_BITSTREAM::pSubregionBitstreamsBaseOffsets[%d] = %d is not aligned with D3D12_FEATURE_DATA_VIDEO_ENCODER_RESOURCE_REQUIREMENTS.CompressedBitstreamBufferAccessAlignment (%d) Current buffer offset: %d Required alignment reported: %d`
- `0x1802445d5`: `The D3D12_VIDEO_ENCODER_SUBREGION_COMPRESSED_BITSTREAM::pSubregionBitstreamsBaseOffsets[%d] = %d exceeds the size of the buffer specified D3D12_VIDEO_ENCODER_SUBREGION_COMPRESSED_BITSTREAM::ppSubregionBitstreams[%d].`
- `0x180244661`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - D3D12_VIDEO_ENCODER_PICTURE_CONTROL_FLAG_ENABLE_DIRTY_REGIONS_INPUT was requested but D3D12_VIDEO_ENCODER_HEAP_FLAG_ALLOW_DIRTY_REGIONS is not set in the encoder heap.`
- `0x1802444d9`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments warning - Buffer offset alignment for EncoderOutputMetadata.pBuffer specified in OutputArguments.EncoderOutputMetadata.Offset is different than advised in encoder caps. Current buffer offset: %d Required alignment reported: %d`
- `0x1802444a4`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments warning - Output buffer size for EncoderOutputMetadata.pBuffer is less than advised in encoder caps. Current buffer size: %d Maximum size reported %d`
- `0x180244558`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments warning - Buffer offset access alignment for Bitstream.pBuffer specified in Bitstream.FrameStartOffset is different than advised in encoder caps. Current buffer offset: %d Required alignment reported: %d`
- `0x18024451c`: `The D3D12_VIDEO_ENCODER_COMPRESSED_BITSTREAM::FrameStartOffset exceeds the size of the buffer specified D3D12_VIDEO_ENCODER_COMPRESSED_BITSTREAM::pBuffer.`
- `0x180244330`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - The QP Map passed in passed in D3D12_VIDEO_ENCODER_PICTURE_CONTROL_CODEC_DATA_<Codec>.pRateControlQPMap must have a size of ceil(FramePixelWidth/QPMapRegionPixelsSize) * ceil(FramePixelHeight/QPMapRegionPixelsSize)) where the QPMapRegionPixelsSize is reported in the support queries or the current resolution being used.`
- `0x180244574`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not valid - Rate control modes that use a CPU buffer QP map, require a non-null QP Map passed in D3D12_VIDEO_ENCODER_PICTURE_CONTROL_CODEC_DATA_<Codec>.pRateControlQPMap`
- `0x1802447dc`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - CheckFeatureSupport(D3D12_FEATURE_VIDEO_ENCODER_RESOURCE_REQUIREMENTS1,...) for the given input returned failure or not supported.`
- `0x180240cd1`: `The reference frame at index %d must have heap type D3D12_HEAP_TYPE_DEFAULT, D3D12_HEAP_TYPE_UPLOAD, D3D12_HEAP_TYPE_GPU_UPLOAD, or D3D12_HEAP_TYPE_CUSTOM. For D3D12_HEAP_TYPE_CUSTOM, CPUPageProperty must not be equal to D3D12_CPU_PAGE_PROPERTY_WRITE_BACK.See D3D12_FEATURE_VIDEO_ARCHITECTURE.`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall ValidateEncodeFrame(
        struct TDebugOutputFunctor *a1,
        const struct DeviceValidationInfo *a2,
        unsigned int a3,
        struct ID3D12VideoEncoder *a4,
        struct ID3D12VideoEncoderHeap1 *a5,
        const struct D3D12_VIDEO_ENCODER_ENCODEFRAME_INPUT_ARGUMENTS1 *a6,
        const struct D3D12_VIDEO_ENCODER_ENCODEFRAME_OUTPUT_ARGUMENTS1 *a7)
{
  struct DeviceValidationInfo *v7; // r11
  const struct D3D12_VIDEO_ENCODER_ENCODEFRAME_INPUT_ARGUMENTS1 *v9; // rsi
  struct ID3D12VideoEncoderHeap *v10; // rbx
  unsigned int v12; // r15d
  __int64 v13; // r10
  __int64 v14; // r9
  __int64 v15; // r8
  __int64 v16; // rdx
  unsigned int i; // eax
  char v18; // di
  enum D3D12_MESSAGE_ID v19; // r8d
  int v20; // eax
  char v21; // bl
  char v22; // di
  int v23; // eax
  int v24; // ebx
  char v25; // bl
  char *v26; // r13
  __int64 v27; // rdi
  CResource *v28; // rsi
  const struct D3D12_VIDEO_ENCODER_ENCODEFRAME_OUTPUT_ARGUMENTS1 *v29; // r13
  CResource *v30; // rdi
  char v31; // r15
  __int64 v32; // rdi
  __int64 v33; // rdx
  unsigned __int16 v34; // ax
  unsigned int v35; // r8d
  enum DXGI_FORMAT v36; // eax
  bool v37; // dl
  bool v38; // dl
  const char *Name; // rax
  const char *v40; // r8
  unsigned __int64 v41; // r9
  unsigned int v42; // r13d
  __int64 j; // rdi
  __int64 v44; // rcx
  __int64 v45; // rsi
  __int64 v46; // rax
  unsigned int v47; // r15d
  __int64 v48; // rdx
  unsigned __int16 v49; // ax
  bool v50; // dl
  const char *v51; // rax
  const char *v52; // r8
  int v53; // eax
  unsigned __int64 v54; // rdx
  struct CResource *v55; // rax
  unsigned int v56; // edi
  struct CResource *v57; // rax
  struct ID3D12VideoEncoderHeap1 *v58; // rdi
  int v59; // eax
  int v60; // eax
  struct CResource *v61; // r13
  int v62; // ebx
  __int64 *v63; // rax
  struct ID3D12VideoEncoder *v64; // rsi
  unsigned int v65; // eax
  unsigned int v66; // esi
  unsigned int v67; // edi
  signed __int64 v68; // rbx
  int v69; // eax
  int v70; // eax
  _DWORD *v71; // rdi
  int v72; // eax
  _DWORD *v73; // rax
  unsigned int v74; // eax
  int v75; // eax
  unsigned int v76; // r9d
  __int64 v77; // rbx
  unsigned int v78; // ecx
  unsigned int v79; // r9d
  unsigned int v80; // ecx
  unsigned int v81; // r9d
  char v82; // r8
  unsigned int v83; // ecx
  unsigned int v84; // edi
  __int64 v85; // r13
  _DWORD *v86; // r9
  __int64 v87; // rbx
  unsigned int v88; // eax
  unsigned int v89; // edx
  int v90; // ecx
  unsigned int v91; // ecx
  unsigned int v92; // ecx
  unsigned int v93; // eax
  unsigned int v94; // ebx
  char *v95; // rdx
  int v96; // eax
  __int64 v97; // rax
  const struct D3D12_VIDEO_ENCODER_ENCODEFRAME_INPUT_ARGUMENTS1 *v98; // r13
  unsigned int v99; // eax
  __int64 v100; // rbx
  int v101; // ecx
  unsigned int v102; // edx
  int v103; // r8d
  int v104; // r13d
  unsigned int v105; // edx
  int v106; // edx
  __int64 v107; // rdi
  unsigned int v108; // ebx
  int v109; // r13d
  unsigned int v110; // r8d
  __int64 v111; // rdx
  struct CResource *v112; // rdi
  unsigned int v113; // ebx
  unsigned int v114; // eax
  unsigned int v115; // r9d
  unsigned int v116; // ebx
  unsigned int v117; // eax
  char v118; // dl
  __int64 n; // rcx
  __int64 ii; // rcx
  unsigned int v121; // eax
  unsigned int v122; // r13d
  int v123; // r9d
  char v124; // bl
  int v125; // r9d
  unsigned int v126; // r11d
  char v127; // di
  unsigned int v128; // edx
  struct CResource *jj; // r10
  unsigned int *v130; // rax
  unsigned int kk; // edx
  unsigned int *v132; // rax
  unsigned int v133; // eax
  unsigned int v134; // r8d
  __int64 v135; // rbx
  int v136; // eax
  int v137; // edx
  unsigned int v138; // edi
  unsigned int v139; // r13d
  unsigned int v140; // eax
  __int64 v141; // rdx
  char v142; // r11
  char v143; // r8
  unsigned int v144; // ebx
  struct CResource *v145; // rcx
  __int64 k; // rdx
  __int64 v147; // rcx
  unsigned int *v148; // rcx
  __int64 m; // rdx
  __int64 v150; // rcx
  unsigned int v151; // eax
  unsigned int v152; // ebx
  unsigned int v153; // eax
  unsigned int v154; // eax
  unsigned int v155; // ebx
  int v156; // eax
  struct ID3D12VideoEncoderHeap1 *v157; // rbx
  int v158; // eax
  int v159; // eax
  __int64 *v160; // rax
  int v161; // edi
  int v162; // ebx
  __int64 v163; // rcx
  CResource *v164; // rax
  __int64 v165; // r13
  const struct D3D12_VIDEO_ENCODER_ENCODEFRAME_INPUT_ARGUMENTS1 *mm; // rax
  __int64 v167; // rcx
  CResource *v168; // rax
  char v169; // r13
  const char *v170; // r8
  const struct D3D12_VIDEO_ENCODER_ENCODEFRAME_INPUT_ARGUMENTS1 *v171; // r13
  __int64 *v172; // r13
  const struct D3D12_VIDEO_ENCODER_ENCODEFRAME_INPUT_ARGUMENTS1 *v173; // rdx
  int v174; // ecx
  int v175; // ecx
  int v176; // ecx
  int v177; // ecx
  unsigned int v178; // r9d
  __int64 v179; // rcx
  int v180; // eax
  int v181; // eax
  int v182; // ecx
  bool v183; // zf
  bool v184; // zf
  int v185; // ecx
  int v186; // ecx
  const struct D3D12_VIDEO_ENCODER_ENCODEFRAME_INPUT_ARGUMENTS1 *v187; // rax
  __int64 v188; // rcx
  __int64 v189; // r13
  __int64 v190; // rdx
  unsigned __int16 v191; // ax
  __int64 v192; // r8
  struct ID3D12VideoEncoder *v193; // r13
  int v194; // eax
  enum DXGI_FORMAT v195; // eax
  bool v196; // dl
  bool v197; // dl
  const char *v198; // rax
  const char *v199; // r8
  unsigned __int64 v200; // r13
  unsigned int v201; // r13d
  const struct D3D12_VIDEO_ENCODER_ENCODEFRAME_INPUT_ARGUMENTS1 *v202; // rcx
  int v203; // r9d
  __int64 v204; // r12
  __int64 v205; // rcx
  struct CResource *v206; // rax
  __int64 v207; // rcx
  __int64 v208; // rdx
  unsigned __int16 v209; // ax
  unsigned int v210; // r8d
  bool v211; // dl
  const char *v212; // rax
  const char *v213; // r8
  unsigned int v214; // edx
  __int64 v215; // rcx
  CResource *v216; // rax
  __int64 v217; // r12
  const struct D3D12_VIDEO_ENCODER_ENCODEFRAME_INPUT_ARGUMENTS1 *nn; // rax
  __int64 v219; // rcx
  CResource *v220; // rax
  struct ID3D12VideoEncoderHeap1 *v221; // r12
  unsigned __int64 v222; // rcx
  unsigned __int64 v223; // r13
  int v224; // ecx
  int v225; // ecx
  int v226; // ecx
  int v227; // ecx
  int v228; // ecx
  int v229; // ecx
  int v230; // ecx
  const struct D3D12_VIDEO_ENCODER_ENCODEFRAME_OUTPUT_ARGUMENTS1 *v231; // r12
  unsigned __int64 v232; // r9
  __int64 i1; // rbx
  CResource *v234; // r12
  const struct D3D12_VIDEO_ENCODER_ENCODEFRAME_INPUT_ARGUMENTS1 *v235; // r12
  int v236; // eax
  int v237; // eax
  _OWORD *v238; // rax
  char *v239; // rcx
  __int64 v240; // rdx
  unsigned __int64 v241; // r9
  int v242; // ecx
  unsigned __int64 *v243; // rax
  unsigned __int64 v244; // r9
  int v245; // ecx
  unsigned __int64 v246; // rbx
  __int64 v247; // rcx
  unsigned __int64 v248; // rax
  unsigned __int64 v249; // rcx
  unsigned __int64 i3; // r12
  unsigned __int64 *v251; // rcx
  unsigned __int64 v252; // rax
  int v253; // eax
  int v254; // edx
  unsigned int v255; // eax
  __int64 v256; // r9
  const char *v257; // r8
  CResource *v258; // r12
  int (__fastcall ***v259)(_QWORD, GUID *, struct CResource **); // rcx
  struct CResource *v260; // rcx
  int v261; // eax
  const char *v262; // r8
  const struct D3D12_VIDEO_ENCODER_ENCODEFRAME_INPUT_ARGUMENTS1 *v263; // r13
  unsigned int v264; // ebx
  unsigned int v265; // r9d
  unsigned int v266; // eax
  unsigned int v267; // r8d
  int v268; // eax
  int v269; // eax
  __int64 v270; // rax
  __int64 v271; // rcx
  int v272; // r12d
  __int64 v273; // rax
  __int64 v274; // rax
  __int64 v275; // rbx
  unsigned __int64 v276; // rbx
  int v277; // r13d
  unsigned int v278; // eax
  struct ID3D12VideoEncoderHeap1 *v279; // r12
  const struct D3D12_VIDEO_ENCODER_ENCODEFRAME_OUTPUT_ARGUMENTS1 *v280; // rsi
  CResource *v281; // rax
  unsigned __int64 v282; // r9
  CResource *v283; // rax
  unsigned __int64 v284; // r9
  unsigned int i2; // ebx
  CResource *v286; // rax
  unsigned __int64 v287; // r9
  unsigned __int64 v288; // r8
  struct ID3D12VideoEncoder *v289; // rsi
  unsigned int v290; // eax
  unsigned int v291; // r8d
  unsigned int v292; // edi
  struct DeviceValidationInfo *v293; // r12
  unsigned int v294; // eax
  unsigned int v295; // r8d
  struct D3D12_FEATURE_DATA_VIDEO_ARCHITECTURE *v296; // [rsp+20h] [rbp-948h]
  unsigned int v297; // [rsp+20h] [rbp-948h]
  int v298; // [rsp+30h] [rbp-938h]
  bool v299[4]; // [rsp+38h] [rbp-930h]
  char v300; // [rsp+50h] [rbp-918h]
  char v301; // [rsp+51h] [rbp-917h]
  char v302[6]; // [rsp+52h] [rbp-916h] BYREF
  const struct D3D12_VIDEO_ENCODER_ENCODEFRAME_INPUT_ARGUMENTS1 *v303; // [rsp+58h] [rbp-910h]
  bool v304; // [rsp+60h] [rbp-908h]
  bool v305; // [rsp+61h] [rbp-907h]
  unsigned int v306; // [rsp+64h] [rbp-904h]
  unsigned int v307; // [rsp+68h] [rbp-900h]
  unsigned int v308; // [rsp+6Ch] [rbp-8FCh]
  unsigned int v309[2]; // [rsp+70h] [rbp-8F8h]
  unsigned int v310; // [rsp+78h] [rbp-8F0h]
  D3D12_FEATURE_DATA_VIDEO_ARCHITECTURE v311; // [rsp+7Ch] [rbp-8ECh] BYREF
  struct ID3D12VideoEncoder *v312; // [rsp+80h] [rbp-8E8h]
  struct ID3D12VideoEncoderHeap1 *v313; // [rsp+88h] [rbp-8E0h]
  unsigned int v314; // [rsp+90h] [rbp-8D8h]
  struct CResource *v315[2]; // [rsp+98h] [rbp-8D0h] BYREF
  unsigned int v316; // [rsp+A8h] [rbp-8C0h]
  unsigned int v317; // [rsp+ACh] [rbp-8BCh]
  _DWORD *v318; // [rsp+B0h] [rbp-8B8h]
  unsigned int v319; // [rsp+B8h] [rbp-8B0h] BYREF
  unsigned int *v320[2]; // [rsp+C0h] [rbp-8A8h] BYREF
  enum DXGI_FORMAT v321; // [rsp+D0h] [rbp-898h] BYREF
  const struct D3D12_VIDEO_ENCODER_ENCODEFRAME_OUTPUT_ARGUMENTS1 *v322; // [rsp+D8h] [rbp-890h]
  struct DeviceValidationInfo *v323; // [rsp+E0h] [rbp-888h]
  unsigned int *v324; // [rsp+E8h] [rbp-880h]
  __int128 v325; // [rsp+F0h] [rbp-878h]
  __int128 v326; // [rsp+100h] [rbp-868h]
  unsigned int *v327; // [rsp+110h] [rbp-858h]
  int v328; // [rsp+118h] [rbp-850h] BYREF
  __int128 v329; // [rsp+120h] [rbp-848h]
  __int128 v330; // [rsp+130h] [rbp-838h] BYREF
  __int64 v331; // [rsp+140h] [rbp-828h]
  void *Src[2]; // [rsp+148h] [rbp-820h] BYREF
  char *v333; // [rsp+158h] [rbp-810h]
  __int128 v334; // [rsp+160h] [rbp-808h] BYREF
  __int64 v335; // [rsp+170h] [rbp-7F8h]
  int v336; // [rsp+178h] [rbp-7F0h] BYREF
  int v337; // [rsp+17Ch] [rbp-7ECh] BYREF
  int v338; // [rsp+180h] [rbp-7E8h] BYREF
  int v339; // [rsp+184h] [rbp-7E4h] BYREF
  int v340; // [rsp+188h] [rbp-7E0h] BYREF
  int v341; // [rsp+18Ch] [rbp-7DCh] BYREF
  int v342; // [rsp+190h] [rbp-7D8h] BYREF
  __int64 v343; // [rsp+198h] [rbp-7D0h] BYREF
  __int64 v344; // [rsp+1A0h] [rbp-7C8h] BYREF
  __int64 v345; // [rsp+1A8h] [rbp-7C0h] BYREF
  __int64 v346; // [rsp+1B0h] [rbp-7B8h] BYREF
  __int64 v347; // [rsp+1B8h] [rbp-7B0h] BYREF
  _DWORD v348[2]; // [rsp+1C0h] [rbp-7A8h] BYREF
  __int128 v349; // [rsp+1C8h] [rbp-7A0h]
  __int64 v350; // [rsp+1D8h] [rbp-790h]
  int v351; // [rsp+1E0h] [rbp-788h]
  int v352; // [rsp+1E4h] [rbp-784h]
  struct CResource *v353; // [rsp+1E8h] [rbp-780h]
  _DWORD v354[4]; // [rsp+1F0h] [rbp-778h] BYREF
  __int64 v355; // [rsp+200h] [rbp-768h]
  __int128 v356; // [rsp+208h] [rbp-760h]
  int v357; // [rsp+218h] [rbp-750h]
  __int64 v358; // [rsp+21Ch] [rbp-74Ch]
  int v359; // [rsp+224h] [rbp-744h]
  int v360; // [rsp+228h] [rbp-740h]
  int v361; // [rsp+22Ch] [rbp-73Ch]
  __int64 v362; // [rsp+230h] [rbp-738h]
  int v363; // [rsp+238h] [rbp-730h]
  int v364; // [rsp+23Ch] [rbp-72Ch]
  __int128 v365; // [rsp+240h] [rbp-728h]
  _DWORD v366[4]; // [rsp+250h] [rbp-718h] BYREF
  __int64 v367; // [rsp+260h] [rbp-708h]
  int v368; // [rsp+268h] [rbp-700h]
  __int64 v369; // [rsp+26Ch] [rbp-6FCh]
  int v370; // [rsp+274h] [rbp-6F4h]
  unsigned int v371; // [rsp+278h] [rbp-6F0h]
  unsigned int v372; // [rsp+27Ch] [rbp-6ECh]
  unsigned int v373; // [rsp+280h] [rbp-6E8h]
  int v374; // [rsp+284h] [rbp-6E4h]
  int v375; // [rsp+288h] [rbp-6E0h]
  int v376; // [rsp+28Ch] [rbp-6DCh]
  __int64 v377; // [rsp+290h] [rbp-6D8h]
  _DWORD v378[4]; // [rsp+2D0h] [rbp-698h] BYREF
  __int128 v379; // [rsp+2E0h] [rbp-688h]
  __int128 v380; // [rsp+2F0h] [rbp-678h]
  __int128 v381; // [rsp+300h] [rbp-668h]
  __int128 v382; // [rsp+310h] [rbp-658h]
  int v383; // [rsp+320h] [rbp-648h]
  int v384; // [rsp+324h] [rbp-644h]
  unsigned int v385; // [rsp+328h] [rbp-640h]
  __int64 v386; // [rsp+330h] [rbp-638h]
  int v387; // [rsp+338h] [rbp-630h]
  int v388; // [rsp+33Ch] [rbp-62Ch]
  int v389; // [rsp+340h] [rbp-628h]
  int v390; // [rsp+348h] [rbp-620h]
  int *v391; // [rsp+350h] [rbp-618h]
  int v392; // [rsp+358h] [rbp-610h]
  __int64 *v393; // [rsp+360h] [rbp-608h]
  __int64 v394; // [rsp+368h] [rbp-600h]
  __int128 v395; // [rsp+370h] [rbp-5F8h]
  unsigned int v396; // [rsp+380h] [rbp-5E8h]
  int v397; // [rsp+384h] [rbp-5E4h]
  int v398; // [rsp+388h] [rbp-5E0h]
  int v399; // [rsp+38Ch] [rbp-5DCh]
  int v401; // [rsp+394h] [rbp-5D4h]
  int v402; // [rsp+398h] [rbp-5D0h]
  int v404; // [rsp+3A0h] [rbp-5C8h]
  BOOL v405; // [rsp+3A4h] [rbp-5C4h]
  int v406; // [rsp+3A8h] [rbp-5C0h]
  int v407; // [rsp+3ACh] [rbp-5BCh]
  struct D3D12_RESOURCE_DESC v408; // [rsp+3B0h] [rbp-5B8h] BYREF
  __int64 v409; // [rsp+3E8h] [rbp-580h]
  int *v410; // [rsp+3F0h] [rbp-578h]
  int v411; // [rsp+3F8h] [rbp-570h]
  __int64 v412; // [rsp+410h] [rbp-558h] BYREF
  int v413; // [rsp+418h] [rbp-550h]
  __int128 v414; // [rsp+420h] [rbp-548h] BYREF
  __int128 v415; // [rsp+430h] [rbp-538h] BYREF
  int v416; // [rsp+440h] [rbp-528h]
  __int128 v417; // [rsp+448h] [rbp-520h] BYREF
  int v418; // [rsp+458h] [rbp-510h]
  __int128 v419; // [rsp+460h] [rbp-508h] BYREF
  __int64 v420; // [rsp+470h] [rbp-4F8h]
  int v421; // [rsp+480h] [rbp-4E8h] BYREF
  char v422; // [rsp+488h] [rbp-4E0h] BYREF
  unsigned int v423; // [rsp+8A4h] [rbp-C4h]
  unsigned int v424; // [rsp+8A8h] [rbp-C0h]
  unsigned int v425; // [rsp+8ACh] [rbp-BCh]
  unsigned int v426; // [rsp+8B0h] [rbp-B8h]
  unsigned int v427; // [rsp+8B4h] [rbp-B4h]
  unsigned int v428; // [rsp+8B8h] [rbp-B0h]
  unsigned int v429; // [rsp+8BCh] [rbp-ACh]
  unsigned int v430; // [rsp+8C0h] [rbp-A8h]
  struct D3D12_RESOURCE_DESC v431; // [rsp+8D0h] [rbp-98h] BYREF
  __int64 v432; // [rsp+908h] [rbp-60h]

  v312 = a4;
  v314 = a3;
  v7 = a2;
  v323 = a2;
  v322 = a7;
  v9 = a6;
  v303 = a6;
  v10 = a5;
  v313 = a5;
  if ( !a4 )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1305,
      "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - pEncoder cannot be null.");
    return 2147942487LL;
  }
  if ( !a5 )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1305,
      "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - pHeap cannot be null.");
    return 2147942487LL;
  }
  if ( !a6 )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1305,
      "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - pInputArguments cannot be null.");
    return 2147942487LL;
  }
  if ( !a7 )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1305,
      "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - pOutputArguments cannot be null.");
    return 2147942487LL;
  }
  if ( !*((_QWORD *)a6 + 28) )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1305,
      "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - pInputArguments->pInputFrame cannot be null.");
    return 2147942487LL;
  }
  if ( !*((_QWORD *)a7 + 10) )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1305,
      "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - pOutputArguments->EncoderOutputMetadata.pBuf"
      "fer cannot be null.");
    return 2147942487LL;
  }
  if ( *(_DWORD *)a7 )
  {
    v12 = 1;
    if ( *(_DWORD *)a7 != 1 )
    {
      TDebugOutputFunctor::operator()(
        a1,
        1305,
        "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - Invalid D3D12_VIDEO_ENCODER_COMPRESSED_BIT"
        "STREAM_NOTIFICATION_MODE set.");
      return 2147942487LL;
    }
    if ( !*((_QWORD *)a7 + 2) )
    {
      TDebugOutputFunctor::operator()(
        a1,
        1305,
        "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - pOutputArguments->Bitstream.SubregionOutpu"
        "tBuffers.pSubregionBitstreamsBaseOffsets cannot be null.");
      return 2147942487LL;
    }
    v13 = *((_QWORD *)a7 + 3);
    if ( !v13 )
    {
      TDebugOutputFunctor::operator()(
        a1,
        1305,
        "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - pOutputArguments->Bitstream.SubregionOutpu"
        "tBuffers.ppSubregionBitstreams cannot be null.");
      return 2147942487LL;
    }
    v14 = *((_QWORD *)a7 + 4);
    if ( !v14 )
    {
      TDebugOutputFunctor::operator()(
        a1,
        1305,
        "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - pOutputArguments->Bitstream.SubregionOutpu"
        "tBuffers.ppSubregionSizes cannot be null.");
      return 2147942487LL;
    }
    v15 = *((_QWORD *)a7 + 5);
    if ( !v15 )
    {
      TDebugOutputFunctor::operator()(
        a1,
        1305,
        "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - pOutputArguments->Bitstream.SubregionOutpu"
        "tBuffers.ppSubregionOffsets cannot be null.");
      return 2147942487LL;
    }
    v16 = *((_QWORD *)a7 + 6);
    if ( !v16 )
    {
      TDebugOutputFunctor::operator()(
        a1,
        1305,
        "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - pOutputArguments->Bitstream.SubregionOutpu"
        "tBuffers.ppSubregionFences cannot be null.");
      return 2147942487LL;
    }
    if ( !*((_QWORD *)a7 + 7) )
    {
      TDebugOutputFunctor::operator()(
        a1,
        1305,
        "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - pOutputArguments->Bitstream.SubregionOutpu"
        "tBuffers.pSubregionFenceValues cannot be null.");
      return 2147942487LL;
    }
    for ( i = 0; i < *((_DWORD *)a7 + 3); ++i )
    {
      if ( !*(_QWORD *)(v13 + 8LL * i) )
      {
        TDebugOutputFunctor::operator()(
          a1,
          1305,
          "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - pOutputArguments->Bitstream.SubregionOut"
          "putBuffers.ppSubregionBitstreams[%d] cannot be null.",
          i);
        return 2147942487LL;
      }
      if ( !*(_QWORD *)(v14 + 8LL * i) )
      {
        TDebugOutputFunctor::operator()(
          a1,
          1305,
          "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - pOutputArguments->Bitstream.SubregionOut"
          "putBuffers.ppSubregionSizes[%d] cannot be null.",
          i);
        return 2147942487LL;
      }
      if ( !*(_QWORD *)(v15 + 8LL * i) )
      {
        TDebugOutputFunctor::operator()(
          a1,
          1305,
          "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - pOutputArguments->Bitstream.SubregionOut"
          "putBuffers.ppSubregionOffsets[%d] cannot be null.",
          i);
        return 2147942487LL;
      }
      if ( !*(_QWORD *)(v16 + 8LL * i) )
      {
        TDebugOutputFunctor::operator()(
          a1,
          1305,
          "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - pOutputArguments->Bitstream.SubregionOut"
          "putBuffers.ppSubregionFences[%d] cannot be null.",
          i);
        return 2147942487LL;
      }
    }
    v9 = v303;
    v10 = v313;
    v7 = v323;
  }
  else
  {
    if ( !*((_QWORD *)a7 + 1) )
    {
      TDebugOutputFunctor::operator()(
        a1,
        1305,
        "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - pOutputArguments->Bitstream.FrameOutputBuf"
        "fer.pBuffer cannot be null.");
      return 2147942487LL;
    }
    v12 = 1;
  }
  v18 = 1;
  v311.IOCoherent = 0;
  if ( (*(int (__fastcall **)(_QWORD, __int64, D3D12_FEATURE_DATA_VIDEO_ARCHITECTURE *))(**((_QWORD **)v7 + 85) + 24LL))(
         *((_QWORD *)v7 + 85),
         17,
         &v311) < 0 )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1305,
      "ID3D12VideoEncodeCommandList::EncodeFrame Failure on call to CheckFeatureSupport(D3D12_FEATURE_VIDEO_ARCHITECTURE,...).");
    v18 = 0;
  }
  v20 = ValidateEncoderAndEncoderHeapCombination(v312, v10, v19, a1);
  v21 = 0;
  if ( v20 >= 0 )
    v21 = v18;
  if ( (*(_DWORD *)v9 & 0xFFFFFFE0) != 0 )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1305,
      "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - Invalid pInputArguments->SequenceControlDesc.Flags.");
    v21 = 0;
  }
  if ( *((int *)v9 + 1) >= 2 )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1305,
      "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - Invalid pInputArguments->SequenceControlDesc"
      ".IntraRefreshConfig.Mode.");
    v21 = 0;
  }
  v321 = (*(unsigned int (__fastcall **)(struct ID3D12VideoEncoder *))(*(_QWORD *)v312 + 80LL))(v312);
  if ( (int)ValidateVideoEncodeCodecGOPStructure(
              (const struct D3D12_VIDEO_ENCODER_ENCODEFRAME_INPUT_ARGUMENTS1 *)((char *)v9 + 80),
              (const enum D3D12_VIDEO_ENCODER_CODEC *)&v321) < 0 )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1305,
      "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - Invalid pInputArguments->SequenceControlDesc"
      ".CodecGopSequence.");
    v21 = 0;
  }
  v22 = 0;
  if ( (int)ValidateVideoEncodeRateControl(
              (const struct D3D12_VIDEO_ENCODER_ENCODEFRAME_INPUT_ARGUMENTS1 *)((char *)v9 + 16),
              a1) >= 0 )
    v22 = v21;
  v319 = 0;
  v302[0] = 0;
  v23 = ValidateResolutionPresentInEncoderHeap(*((_QWORD *)v9 + 6), v313, v302, &v319);
  v24 = v23;
  if ( v23 >= 0 )
  {
    if ( !v302[0] )
    {
      TDebugOutputFunctor::operator()(
        a1,
        1305,
        "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct  Target resolution must be within the associ"
        "ated heap allowed resolution list.");
      v22 = 0;
    }
  }
  else
  {
    TDebugOutputFunctor::operator()(
      a1,
      0,
      "ID3D12VideoEncodeCommandList::EncodeFrame validation failure - Error produced while validating encoder heap resolu"
      "tion list - HRESULT: %x.",
      v23);
    ThrowFailure(v24);
  }
  if ( (*((_DWORD *)v9 + 25) & 0xFFFFFFF0) != 0 )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1305,
      "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - Invalid pInputArguments->PictureControlDesc.Flags.");
    v22 = 0;
  }
  v321 = (*(unsigned int (__fastcall **)(struct ID3D12VideoEncoder *))(*(_QWORD *)v312 + 80LL))(v312);
  v25 = 0;
  if ( (int)ValidateEncodeFrameCodecInput(
              v9,
              (const struct D3D12_VIDEO_ENCODER_ENCODEFRAME_INPUT_ARGUMENTS1 *)((char *)v9 + 96),
              (const enum D3D12_VIDEO_ENCODER_CODEC *)&v321,
              a1) >= 0 )
    v25 = v22;
  if ( *(_DWORD *)a7 )
  {
    v12 = *((_DWORD *)a7 + 3);
    v26 = (char *)*((_QWORD *)a7 + 3);
  }
  else
  {
    v26 = (char *)a7 + 8;
  }
  if ( v12 )
  {
    v27 = 0;
    while ( 1 )
    {
      v28 = (CResource *)QIFrom<CResource>(*(_QWORD *)&v26[8 * v27]);
      CResource::GetDesc(v28, &v408);
      if ( v408.Dimension != D3D12_RESOURCE_DIMENSION_BUFFER )
      {
        TDebugOutputFunctor::operator()(
          a1,
          1305,
          "The resource in D3D12_VIDEO_ENCODER_COMPRESSED_BITSTREAM must be a buffer.");
        v25 = 0;
      }
      if ( *((_BYTE *)v28 + 392) == 3 )
        break;
      if ( !IsVideoHeapTypeSupported(&v311, v28) )
      {
        TDebugOutputFunctor::operator()(
          a1,
          1305,
          "The resource in D3D12_VIDEO_ENCODER_COMPRESSED_BITSTREAM must have heap type D3D12_HEAP_TYPE_DEFAULT, D3D12_HE"
          "AP_TYPE_UPLOAD, D3D12_HEAP_TYPE_GPU_UPLOAD, or D3D12_HEAP_TYPE_CUSTOM. For D3D12_HEAP_TYPE_CUSTOM, CPUPageProp"
          "erty must not be equal to D3D12_CPU_PAGE_PROPERTY_WRITE_BACK.See D3D12_FEATURE_VIDEO_ARCHITECTURE.");
        goto LABEL_73;
      }
LABEL_74:
      v27 = (unsigned int)(v27 + 1);
      if ( (unsigned int)v27 >= v12 )
      {
        v9 = v303;
        goto LABEL_76;
      }
    }
    TDebugOutputFunctor::operator()(
      a1,
      1305,
      "The resource in D3D12_VIDEO_ENCODER_COMPRESSED_BITSTREAM must not be a reserved resource.");
LABEL_73:
    v25 = 0;
    goto LABEL_74;
  }
LABEL_76:
  v29 = v322;
  v30 = (CResource *)QIFrom<CResource>(*((_QWORD *)v322 + 10));
  CResource::GetDesc(v30, &v408);
  v31 = 1;
  if ( v408.Dimension != D3D12_RESOURCE_DIMENSION_BUFFER )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1305,
      "The resource in D3D12_VIDEO_ENCODER_ENCODEFRAME_OUTPUT_ARGUMENTS.EncoderOutputMetadata.pBuffer must be a buffer.");
    v25 = 0;
  }
  if ( *((_BYTE *)v30 + 392) == 3 )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1305,
      "The resource in D3D12_VIDEO_ENCODER_ENCODEFRAME_OUTPUT_ARGUMENTS.EncoderOutputMetadata.pBuffer must not be a reserved resource.");
  }
  else
  {
    if ( IsVideoHeapTypeSupported(&v311, v30) )
      goto LABEL_83;
    TDebugOutputFunctor::operator()(
      a1,
      1305,
      "The resource in D3D12_VIDEO_ENCODER_ENCODEFRAME_OUTPUT_ARGUMENTS.EncoderOutputMetadata.pBuffer must have heap type"
      " D3D12_HEAP_TYPE_DEFAULT, D3D12_HEAP_TYPE_UPLOAD, D3D12_HEAP_TYPE_GPU_UPLOAD, or D3D12_HEAP_TYPE_CUSTOM. For D3D12"
      "_HEAP_TYPE_CUSTOM, CPUPageProperty must not be equal to D3D12_CPU_PAGE_PROPERTY_WRITE_BACK.See D3D12_FEATURE_VIDEO_ARCHITECTURE.");
  }
  v25 = 0;
LABEL_83:
  if ( *((_QWORD *)v29 + 11) >= v408.Width )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1305,
      "The D3D12_VIDEO_ENCODER_ENCODEFRAME_OUTPUT_ARGUMENTS::EncoderOutputMetadata.Offset exceeds the size of the buffer "
      "specified D3D12_VIDEO_ENCODER_ENCODEFRAME_OUTPUT_ARGUMENTS.EncoderOutputMetadata.pBuffer.");
    v25 = 0;
  }
  v32 = QIFrom<CResource>(*((_QWORD *)v9 + 28));
  CResource::GetDesc((CResource *)v32, &v431);
  if ( v431.Dimension != D3D12_RESOURCE_DIMENSION_TEXTURE2D )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1305,
      "D3D12_VIDEO_ENCODER_ENCODEFRAME_INPUT_ARGUMENTS::pInputFrame must have a resource dimension of D3D12_RESOURCE_DIME"
      "NSION_TEXTURE2D.");
    v25 = 0;
  }
  if ( *(_BYTE *)(v32 + 392) == 3 )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1305,
      "D3D12_VIDEO_ENCODER_ENCODEFRAME_INPUT_ARGUMENTS::pInputFrame must not be a reserved resource.");
  }
  else
  {
    if ( IsVideoHeapTypeSupported(&v311, (struct CResource *)v32) )
      goto LABEL_92;
    TDebugOutputFunctor::operator()(
      a1,
      1305,
      "D3D12_VIDEO_ENCODER_ENCODEFRAME_INPUT_ARGUMENTS::pInputFrame must have heap type D3D12_HEAP_TYPE_DEFAULT, D3D12_HE"
      "AP_TYPE_UPLOAD, D3D12_HEAP_TYPE_GPU_UPLOAD, or D3D12_HEAP_TYPE_CUSTOM. For D3D12_HEAP_TYPE_CUSTOM, CPUPageProperty"
      " must not be equal to D3D12_CPU_PAGE_PROPERTY_WRITE_BACK.See D3D12_FEATURE_VIDEO_ARCHITECTURE.");
  }
  v25 = 0;
LABEL_92:
  if ( *((_DWORD *)v9 + 58) >= (*(_DWORD *)(v32 + 244) & 0xFFFFFFu) )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1305,
      "The D3D12_VIDEO_ENCODER_ENCODEFRAME_INPUT_ARGUMENTS::InputFrameSubresource exceeds the number of subresources for "
      "D3D12_VIDEO_ENCODER_ENCODEFRAME_INPUT_ARGUMENTS::pInputFrame.");
LABEL_98:
    v25 = 0;
    goto LABEL_99;
  }
  if ( *(_BYTE *)(v32 + 247) != 1 )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1305,
      "The subresource for reference frame at index %d has MipLevels != 1 which is not supported with EncodeFrame.");
    goto LABEL_98;
  }
  v34 = ResourceValidationInfo::ArraySize((ResourceValidationInfo *)(v32 + 224));
  v33 = v35 % v34;
  if ( v35 / v34 )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1305,
      "D3D12_VIDEO_ENCODER_ENCODEFRAME_INPUT_ARGUMENTS::InputFrameSubresource must specify PlaneSlice 0 of a planar resou"
      "rce for the chosen ArraySlice.");
    goto LABEL_98;
  }
LABEL_99:
  v36 = (*(unsigned int (__fastcall **)(struct ID3D12VideoEncoder *, __int64))(*(_QWORD *)v312 + 104LL))(v312, v33);
  v321 = v36;
  if ( v431.Format != v36 )
  {
    D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v36, v37);
    Name = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v431.Format, v38);
    TDebugOutputFunctor::operator()(
      a1,
      1305,
      "The input frame has a format of %s that does not match the encoder which has a format of %s.",
      Name,
      v40);
    v25 = 0;
  }
  v41 = *((unsigned int *)v9 + 12);
  if ( v41 > v431.Width || *((_DWORD *)v9 + 13) > v431.Height )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1305,
      "The input frame is smaller than the requested PictureTargetResolution.  PictureTargetResolution.Width: %d, Picture"
      "TargetResolution.Height: %d, Resource Width: %I64u, Resource Height: %d",
      v41,
      *((_DWORD *)v9 + 13),
      v431.Width,
      v431.Height);
    v25 = 0;
  }
  v42 = *((_DWORD *)v9 + 30);
  for ( j = 0; (unsigned int)j < v42; j = (unsigned int)(j + 1) )
  {
    v44 = *(_QWORD *)(*((_QWORD *)v9 + 16) + 8 * j);
    if ( !v44 )
      goto LABEL_130;
    v45 = QIFrom<CResource>(v44);
    v46 = *((_QWORD *)v303 + 17);
    if ( v46 )
      v47 = *(_DWORD *)(v46 + 4 * j);
    else
      v47 = 0;
    CResource::GetDesc((CResource *)v45, &v408);
    if ( v408.Dimension != D3D12_RESOURCE_DIMENSION_TEXTURE2D )
    {
      TDebugOutputFunctor::operator()(
        a1,
        1305,
        "The reference frame at index %d must have a resource dimension of D3D12_RESOURCE_DIMENSION_TEXTURE2D.",
        j);
      v25 = 0;
    }
    if ( *(_BYTE *)(v45 + 392) == 3 )
    {
      TDebugOutputFunctor::operator()(
        a1,
        1305,
        "The reference frame at index %d must not be a reserved resource.",
        (unsigned int)j);
    }
    else
    {
      if ( IsVideoHeapTypeSupported(&v311, (struct CResource *)v45) )
        goto LABEL_117;
      TDebugOutputFunctor::operator()(
        a1,
        1305,
        "The reference frame at index %d must have heap type D3D12_HEAP_TYPE_DEFAULT, D3D12_HEAP_TYPE_UPLOAD, D3D12_HEAP_"
        "TYPE_GPU_UPLOAD, or D3D12_HEAP_TYPE_CUSTOM. For D3D12_HEAP_TYPE_CUSTOM, CPUPageProperty must not be equal to D3D"
        "12_CPU_PAGE_PROPERTY_WRITE_BACK.See D3D12_FEATURE_VIDEO_ARCHITECTURE.",
        (unsigned int)j);
    }
    v25 = 0;
LABEL_117:
    if ( v47 >= (*(_DWORD *)(v45 + 244) & 0xFFFFFFu) )
    {
      TDebugOutputFunctor::operator()(
        a1,
        1305,
        "The subresource for reference frame at index %d exceeds the number of subresources for the associated resource.",
        (unsigned int)j);
LABEL_123:
      v25 = 0;
      goto LABEL_124;
    }
    if ( *(_BYTE *)(v45 + 247) != 1 )
    {
      TDebugOutputFunctor::operator()(
        a1,
        1305,
        "The subresource for reference frame at index %d has MipLevels != 1 which is not supported with EncodeFrame.",
        (unsigned int)j);
      goto LABEL_123;
    }
    v49 = ResourceValidationInfo::ArraySize((ResourceValidationInfo *)(v45 + 224));
    v48 = v47 % v49;
    if ( v47 / v49 )
    {
      TDebugOutputFunctor::operator()(
        a1,
        1305,
        "The subresource for reference frame at index %d must specify PlaneSlice 0 of a planar resource for the chosen ArraySlice.",
        (unsigned int)j);
      goto LABEL_123;
    }
LABEL_124:
    if ( v408.Format != v321 )
    {
      D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v321, v48);
      v51 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v408.Format, v50);
      TDebugOutputFunctor::operator()(
        a1,
        1305,
        "The reference frame at index %d has a format of %s that does not match the encoder which has a format of %s.",
        j,
        v51,
        v52);
      v25 = 0;
    }
    v53 = (*(__int64 (__fastcall **)(struct ID3D12VideoEncoder *, __int64))(*(_QWORD *)v312 + 80LL))(v312, v48);
    v9 = v303;
    if ( v53 != 2 )
    {
      v54 = *((unsigned int *)v303 + 12);
      if ( v54 > v408.Width || *((_DWORD *)v303 + 13) > v408.Height )
      {
        TDebugOutputFunctor::operator()(
          a1,
          1305,
          "The reference frame at index %d is smaller than the current PictureTargetResolution.  PictureTargetResolution."
          "Width: %d, PictureTargetResolution.Height: %d, Resource Width: %I64u, Resource Height: %d",
          j,
          v54,
          *((_DWORD *)v303 + 13),
          v408.Width,
          v408.Height);
        v25 = 0;
      }
    }
LABEL_130:
    v31 = 1;
  }
  if ( SLOBYTE(v431.Flags) < 0 )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1305,
      "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - pInputArguments->pInputFrame must NOT have t"
      "he D3D12_RESOURCE_FLAG_VIDEO_ENCODE_REFERENCE_ONLY set.");
    v25 = 0;
  }
  if ( (*((_BYTE *)v9 + 100) & 1) != 0 && !*((_QWORD *)v322 + 8) )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1305,
      "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - pOutputArguments->ReconstructedPicture.pReco"
      "nstructedPicture cannot be null.if D3D12_VIDEO_ENCODER_PICTURE_CONTROL_FLAG_USED_AS_REFERENCE_PICTURE is set");
    v25 = 0;
  }
  v315[0] = 0;
  if ( (**(int (__fastcall ***)(struct ID3D12VideoEncoderHeap1 *, GUID *, struct CResource **))v313)(
         v313,
         &GUID_ffffffff_335a_4bc5_9de9_43d8fb7777ae,
         v315) < 0 )
  {
    v55 = 0;
  }
  else
  {
    (*(void (__fastcall **)(struct CResource *))(*(_QWORD *)v315[0] + 16LL))(v315[0]);
    v55 = v315[0];
  }
  v56 = v314;
  if ( (v314 & *((_DWORD *)v55 + 50)) == 0 )
  {
    v25 = 0;
    TDebugOutputFunctor::operator()(
      a1,
      1305,
      "The NodeMask of the ID3D12VideoEncoderHeap is not supported by the NodeMask of this command list.");
  }
  v315[0] = 0;
  if ( (**(int (__fastcall ***)(struct ID3D12VideoEncoder *, GUID *, struct CResource **))v312)(
         v312,
         &GUID_ffffffff_335a_4bc5_9de9_43d8fb7777ae,
         v315) < 0 )
  {
    v57 = 0;
  }
  else
  {
    (*(void (__fastcall **)(struct CResource *))(*(_QWORD *)v315[0] + 16LL))(v315[0]);
    v57 = v315[0];
  }
  if ( (v56 & *((_DWORD *)v57 + 50)) == 0 )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1305,
      "The NodeMask of the ID3D12VideoEncoder is not supported by the NodeMask of this command list.");
    return 2147942487LL;
  }
  if ( !v25 )
    return 2147942487LL;
  v417 = 0;
  v418 = 0;
  v415 = 0;
  v416 = 0;
  v414 = 0;
  *(_OWORD *)v315 = 0;
  v325 = 0;
  v342 = 0;
  v341 = 0;
  v340 = 0;
  v329 = 0;
  v336 = 0;
  v345 = 0;
  v343 = 0;
  v326 = 0;
  v412 = 0;
  v413 = 0;
  v419 = 0;
  v420 = 0;
  v344 = 0;
  v58 = v313;
  v59 = (*(__int64 (__fastcall **)(struct ID3D12VideoEncoderHeap1 *))(*(_QWORD *)v313 + 80LL))(v313);
  if ( v59 )
  {
    v60 = v59 - 1;
    if ( v60 )
    {
      if ( v60 == 1 )
      {
        LODWORD(v414) = *(_DWORD *)(*((_QWORD *)v9 + 14) + 8LL);
        v61 = (struct CResource *)&v414;
        *(_QWORD *)v309 = &v414;
        v62 = 16;
        *((_QWORD *)&v325 + 1) = &v340;
        LODWORD(v325) = 4;
        *(_OWORD *)v320 = v325;
        (*(void (__fastcall **)(struct ID3D12VideoEncoderHeap1 *, unsigned int **))(*(_QWORD *)v58 + 88LL))(v58, v320);
        *((_QWORD *)&v329 + 1) = &v343;
        LODWORD(v329) = 8;
        *(_OWORD *)v320 = v329;
        (*(void (__fastcall **)(struct ID3D12VideoEncoderHeap1 *, unsigned int **))(*(_QWORD *)v58 + 96LL))(v58, v320);
        v63 = &v344;
        LODWORD(v326) = 8;
        goto LABEL_154;
      }
      v61 = v315[1];
      *(struct CResource **)v309 = v315[1];
      v62 = (int)v315[0];
      v64 = v312;
    }
    else
    {
      v61 = (struct CResource *)&v415;
      *(_QWORD *)v309 = &v415;
      v62 = 20;
      *((_QWORD *)&v325 + 1) = &v341;
      LODWORD(v325) = 4;
      *(_OWORD *)v320 = v325;
      (*(void (__fastcall **)(struct ID3D12VideoEncoderHeap1 *, unsigned int **))(*(_QWORD *)v58 + 88LL))(v58, v320);
      *((_QWORD *)&v329 + 1) = &v345;
      LODWORD(v329) = 8;
      *(_OWORD *)v320 = v329;
      (*(void (__fastcall **)(struct ID3D12VideoEncoderHeap1 *, unsigned int **))(*(_QWORD *)v58 + 96LL))(v58, v320);
      v63 = (__int64 *)&v419;
      LODWORD(v326) = 24;
LABEL_154:
      *((_QWORD *)&v326 + 1) = v63;
      *(_OWORD *)v320 = v326;
      v64 = v312;
      (*(void (__fastcall **)(struct ID3D12VideoEncoder *, unsigned int **))(*(_QWORD *)v312 + 96LL))(v312, v320);
    }
  }
  else
  {
    v61 = (struct CResource *)&v417;
    *(_QWORD *)v309 = &v417;
    v62 = 20;
    *((_QWORD *)&v325 + 1) = &v342;
    LODWORD(v325) = 4;
    *(_OWORD *)v320 = v325;
    (*(void (__fastcall **)(struct ID3D12VideoEncoderHeap1 *, unsigned int **))(*(_QWORD *)v58 + 88LL))(v58, v320);
    *((_QWORD *)&v329 + 1) = &v336;
    LODWORD(v329) = 4;
    *(_OWORD *)v320 = v329;
    (*(void (__fastcall **)(struct ID3D12VideoEncoderHeap1 *, unsigned int **))(*(_QWORD *)v58 + 96LL))(v58, v320);
    *((_QWORD *)&v326 + 1) = &v412;
    LODWORD(v326) = 12;
    *(_OWORD *)v320 = v326;
    v64 = v312;
    (*(void (__fastcall **)(struct ID3D12VideoEncoder *, unsigned int **))(*(_QWORD *)v312 + 96LL))(v312, v320);
  }
  v65 = (*(__int64 (__fastcall **)(struct ID3D12VideoEncoder *))(*(_QWORD *)v64 + 64LL))(v64);
  if ( !v65 )
    v65 = 1;
  v310 = 0;
  _BitScanForward(&v65, v65);
  v348[0] = v65;
  v348[1] = (*(__int64 (__fastcall **)(struct ID3D12VideoEncoderHeap1 *))(*(_QWORD *)v58 + 80LL))(v58);
  v349 = v325;
  v66 = DWORD1(v325);
  v67 = 0;
  v350 = 0;
  v351 = v62;
  v352 = HIDWORD(v315[0]);
  v353 = v61;
  if ( (*(int (__fastcall **)(_QWORD, __int64, _DWORD *, __int64))(**((_QWORD **)v323 + 85) + 24LL))(
         *((_QWORD *)v323 + 85),
         44,
         v348,
         48) < 0
    || !(_DWORD)v350 )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1310,
      "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - CheckFeatureSupport(D3D12_FEATURE_VIDEO_EN"
      "CODER_CODEC_PICTURE_CONTROL_SUPPORT,...) for the given input returned failure or not supported.");
    v31 = 0;
  }
  v307 = 0;
  v300 = 1;
  v301 = 1;
  LODWORD(v68) = 0;
  v320[0] = 0;
  v305 = 0;
  v304 = 0;
  v69 = (*(__int64 (__fastcall **)(struct ID3D12VideoEncoderHeap1 *))(*(_QWORD *)v313 + 80LL))(v313);
  if ( !v69 )
  {
    v134 = *((_DWORD *)v61 + 4);
    v314 = v134;
    v305 = *(_DWORD *)(*((_QWORD *)v303 + 11) + 4LL) > 1u;
    v135 = *((_QWORD *)v303 + 14);
    v136 = *(_DWORD *)(v135 + 4);
    v304 = v136 == 2;
    v137 = *(_DWORD *)v61;
    LODWORD(v318) = *(_DWORD *)v61;
    v317 = *((_DWORD *)v61 + 1);
    v316 = *((_DWORD *)v61 + 2);
    v310 = *((_DWORD *)v61 + 3);
    v138 = *(_DWORD *)(v135 + 28);
    v315[0] = *(struct CResource **)(v135 + 32);
    v139 = *(_DWORD *)(v135 + 40);
    v327 = *(unsigned int **)(v135 + 48);
    v324 = *(unsigned int **)(v135 + 64);
    if ( (unsigned int)(v136 - 1) <= 1 && !v134 )
    {
      v31 = 0;
      TDebugOutputFunctor::operator()(
        a1,
        1306,
        "ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - H264 Picture control structure - P or B fram"
        "es are not supported as D3D12_VIDEO_ENCODER_CODEC_PICTURE_CONTROL_SUPPORT_H264.capMaxDPBCapacity is reporting zero.");
      v137 = (int)v318;
    }
    if ( *(_DWORD *)(v135 + 4) == 1 && !v137 )
    {
      v31 = 0;
      TDebugOutputFunctor::operator()(
        a1,
        1306,
        "ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - H264 Picture control structure - P frame not"
        " supported as D3D12_VIDEO_ENCODER_CODEC_PICTURE_CONTROL_SUPPORT_H264.MaxL0ReferencesForP is reporting zero.");
    }
    if ( *(_DWORD *)(v135 + 4) == 2 && (!v317 || !v316) )
    {
      v31 = 0;
      TDebugOutputFunctor::operator()(
        a1,
        1306,
        "ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - H264 Picture control structure - B frame not"
        " supported as D3D12_VIDEO_ENCODER_CODEC_PICTURE_CONTROL_SUPPORT_H264.MaxL0ReferencesForB or D3D12_VIDEO_ENCODER_"
        "CODEC_PICTURE_CONTROL_SUPPORT_H264.MaxL1ReferencesForB are reporting zero.");
    }
    v140 = *(_DWORD *)(v135 + 56);
    v307 = v140;
    if ( *(_DWORD *)(v135 + 4) != 3 && *(_BYTE *)(v135 + 72) && (!*(_DWORD *)(v135 + 76) || !*(_QWORD *)(v135 + 80)) )
    {
      v31 = 0;
      TDebugOutputFunctor::operator()(
        a1,
        1306,
        "ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - H264 Picture control structure - adaptive_re"
        "f_pic_marking_mode_flag is set but RefPicMarkingOperationsCommandsCount or pRefPicMarkingOperationsCommands are "
        "not set correctly.");
      v140 = v307;
    }
    if ( v324 && v140 )
    {
      v141 = 0;
      v142 = 1;
      do
      {
        v142 |= v324[6 * v141] < *((_DWORD *)v303 + 30);
        v300 = v142;
        v301 |= v324[6 * v141 + 5] <= *(_DWORD *)(v135 + 24);
        v141 = (unsigned int)(v141 + 1);
        v140 = v307;
      }
      while ( (unsigned int)v141 < v307 );
    }
    if ( (!*(_DWORD *)(v135 + 4) || *(_DWORD *)(v135 + 4) == 3) && (v315[0] || v138 || v327 || v139 || v324 || v140) )
    {
      v31 = 0;
      TDebugOutputFunctor::operator()(
        a1,
        1306,
        "ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - H264 Picture control structure - IDR or I Fr"
        "ames must not contain references information.");
    }
    if ( *(_DWORD *)(v135 + 4) == 1 && v138 > (unsigned int)v318 )
    {
      v31 = 0;
      TDebugOutputFunctor::operator()(
        a1,
        1306,
        "ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - H264 Picture control structure - Number of L"
        "0 elements (%d) for P frame exceeded respect to MaxL0ReferencesForP (%d).",
        v138,
        (_DWORD)v318);
    }
    if ( *(_DWORD *)(v135 + 4) == 2 && (v138 > v317 || v139 > v316) )
    {
      v31 = 0;
      TDebugOutputFunctor::operator()(
        a1,
        1306,
        "ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - H264 Picture control structure - Number of L"
        "0 elements (%d) for P frame exceeded respect to MaxL0ReferencesForB (%d) or Number of L1 elements (%d) for P fra"
        "me exceeded respect to MaxL1ReferencesForB (%d).",
        v138,
        v317,
        v139,
        v316);
    }
    LODWORD(v320[0]) = CalculateNumberOfDistinctL0L1EncodeReferences((unsigned int *)v315[0], v138, v327, v139);
    v143 = 1;
    v144 = 0;
    v145 = v315[0];
    if ( v315[0] )
    {
      for ( k = 0; (unsigned int)k < v138; v145 = v315[0] )
      {
        v147 = *((unsigned int *)v145 + k);
        v143 |= (unsigned int)v147 < v307;
        if ( v143 )
          v144 += v324[6 * v147 + 1] != 0;
        k = (unsigned int)(k + 1);
      }
    }
    v67 = 17;
    v148 = v327;
    if ( v327 )
    {
      for ( m = 0; (unsigned int)m < v139; v148 = v327 )
      {
        v150 = v148[m];
        v143 |= (unsigned int)v150 < v307;
        if ( v143 )
          v144 += v324[6 * v150 + 1] != 0;
        m = (unsigned int)(m + 1);
      }
    }
    if ( !v143 )
    {
      v31 = 0;
      TDebugOutputFunctor::operator()(
        a1,
        1306,
        "ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - H264 Picture control structure - Indices in "
        "L0 or L1 lists are out of bounds, exceeding the ReferenceFramesReconPictureDescriptorsCount size.",
        v324);
    }
    if ( v144 > v310 )
    {
      v31 = 0;
      TDebugOutputFunctor::operator()(
        a1,
        1306,
        "ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - H264 Picture control structure - Number of L"
        "TR in L0/L1 lists (%d) exceeds maximum supported number of LTRs (%d) for current frame",
        v144,
        v310);
    }
    v151 = (unsigned int)v318;
    if ( (unsigned int)v318 < v317 )
      v151 = v317;
    if ( v151 < v316 )
      v151 = v316;
    v152 = v314;
    if ( v151 > v314 )
    {
      v31 = 0;
      TDebugOutputFunctor::operator()(
        a1,
        1306,
        "ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - Number of reference pictures addressable by "
        "L0 and L1 lists according to caps (MaxLXReferencesForX) exceeds the MaxDPBCapacity value reported. Max L0 size f"
        "or P: %d Max L0 size for B: %d Max L1 size: %d Max number of adressable unique frames in DPB between L0 and L1 l"
        "ists: %d Reported maximum DPB size %d",
        (_DWORD)v318,
        v317,
        v316,
        v151,
        v314);
    }
    if ( LODWORD(v320[0]) <= v152 )
    {
      LODWORD(v68) = v320[0];
    }
    else
    {
      v31 = 0;
      v297 = v152;
      LODWORD(v68) = v320[0];
      TDebugOutputFunctor::operator()(
        a1,
        1306,
        "ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - Number of distinct reference pictures indexe"
        "d from L0 and L1 lists into ReferenceFramesReconPictureDescriptorsCount exceeds the MaxDPBCapacity value reporte"
        "d Current DPB size: %d Reported maximum DPB size %d",
        LODWORD(v320[0]),
        v297);
    }
    v98 = v303;
    if ( v307 != *((_DWORD *)v303 + 30) )
      goto LABEL_373;
    goto LABEL_433;
  }
  v70 = v69 - 1;
  if ( !v70 )
  {
    v100 = *((_QWORD *)v303 + 14);
    v315[0] = (struct CResource *)v100;
    v101 = *(_DWORD *)(v100 + 4);
    v304 = v101 == 2;
    v102 = *((_DWORD *)v61 + 4);
    v316 = v102;
    v305 = *(_DWORD *)(*((_QWORD *)v303 + 11) + 4LL) > 1u;
    v103 = *(_DWORD *)v61;
    LODWORD(v327) = *(_DWORD *)v61;
    v317 = *((_DWORD *)v61 + 1);
    v104 = *((_DWORD *)v61 + 2);
    LODWORD(v318) = v104;
    v310 = *(_DWORD *)(*(_QWORD *)v309 + 12LL);
    if ( (unsigned int)(v101 - 1) <= 1 )
    {
      v105 = 16;
      if ( (unsigned int)(*(_DWORD *)(v100 + 132) + 1) < 0x10 )
        v105 = *(_DWORD *)(v100 + 132) + 1;
      v308 = v105;
      if ( v101 == 2 )
      {
        v106 = 16;
        if ( (unsigned int)(*(_DWORD *)(v100 + 136) + 1) < 0x10 )
          v106 = *(_DWORD *)(v100 + 136) + 1;
        v309[0] = v106;
        v102 = v316;
LABEL_292:
        v314 = *(_DWORD *)(v100 + 20);
        v324 = *(unsigned int **)(v100 + 24);
        v306 = *(_DWORD *)(v100 + 32);
        v320[0] = *(unsigned int **)(v100 + 40);
        v307 = *(_DWORD *)(v100 + 48);
        v107 = *(_QWORD *)(v100 + 56);
        if ( (unsigned int)(v101 - 1) <= 1 && !v102 )
        {
          v31 = 0;
          TDebugOutputFunctor::operator()(
            a1,
            1306,
            "ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - HEVC Picture control structure - P or B "
            "frames are not supported as D3D12_VIDEO_ENCODER_CODEC_PICTURE_CONTROL_SUPPORT_HEVC.capMaxDPBCapacity is reporting zero.");
          v103 = (int)v327;
        }
        if ( *(_DWORD *)(v100 + 4) == 1 && !v103 )
        {
          v31 = 0;
          TDebugOutputFunctor::operator()(
            a1,
            1306,
            "ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - HEVC Picture control structure - P frame"
            " not supported as D3D12_VIDEO_ENCODER_CODEC_PICTURE_CONTROL_SUPPORT_HEVC.MaxL0ReferencesForP is reporting zero.");
        }
        if ( *(_DWORD *)(v100 + 4) == 2 && (!v317 || !v104) )
        {
          v31 = 0;
          TDebugOutputFunctor::operator()(
            a1,
            1306,
            "ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - HEVC Picture control structure - B frame"
            " not supported as D3D12_VIDEO_ENCODER_CODEC_PICTURE_CONTROL_SUPPORT_HEVC.MaxL0ReferencesForB or D3D12_VIDEO_"
            "ENCODER_CODEC_PICTURE_CONTROL_SUPPORT_H264.MaxL1ReferencesForB are reporting zero.");
        }
        v108 = 0;
        v109 = 0;
        if ( v107 && v307 )
        {
          v110 = 0;
          v111 = 0;
          do
          {
            if ( *(_DWORD *)(v107 + 20 * v111 + 4) == 1 )
            {
              v108 += *(_DWORD *)(v107 + 20 * v111 + 8) != 0;
              ++v109;
            }
            v300 |= *(_DWORD *)(v107 + 20 * v111) < *((_DWORD *)v303 + 30);
            v301 |= *(_DWORD *)(v107 + 20 * v111 + 16) <= *((_DWORD *)v315[0] + 4);
            ++v110;
            ++v111;
          }
          while ( v110 < v307 );
        }
        if ( v108 && (**((_BYTE **)&v326 + 1) & 8) == 0 )
        {
          v31 = 0;
          TDebugOutputFunctor::operator()(
            a1,
            1306,
            "ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - HEVC Picture control structure - Long te"
            "rm references detected in picture control used for this frame but not enabled in associated encoder, please "
            "see D3D12_VIDEO_ENCODER_CODEC_CONFIGURATION_HEVC_FLAG_ENABLE_LONG_TERM_REFERENCES.");
        }
        if ( v108 > v310 )
        {
          v31 = 0;
          TDebugOutputFunctor::operator()(
            a1,
            1306,
            "ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - HEVC Picture control structure - Number "
            "of LTR in L0/L1 lists (%d) exceeds maximum supported number of LTRs (%d) for current frame",
            v108,
            v310);
        }
        v112 = v315[0];
        if ( *((_DWORD *)v315[0] + 1) && *((_DWORD *)v315[0] + 1) != 3 )
        {
          v113 = v306;
        }
        else
        {
          v113 = v306;
          if ( v324 || v314 || v320[0] || v306 )
          {
            v31 = 0;
            TDebugOutputFunctor::operator()(
              a1,
              1306,
              "ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - HEVC Picture control structure - IDR o"
              "r I Frames must not contain L0/L1 references information.");
          }
          if ( *(_QWORD *)((char *)v112 + 132) )
          {
            v31 = 0;
            TDebugOutputFunctor::operator()(
              a1,
              1306,
              "ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - HEVC Picture control structure - IDR o"
              "r I Frames must not contain num_ref_idx_l0_active_minus1 (%d)/num_ref_idx_l1_active_minus1  (%d)> 0.",
              *((_DWORD *)v112 + 33),
              *((_DWORD *)v112 + 34));
          }
          if ( v109 )
          {
            v31 = 0;
            TDebugOutputFunctor::operator()(
              a1,
              1306,
              "ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - HEVC Picture control structure - IDR o"
              "r I Frames must not use frame references from the DPB (Check the IsRefUsedByCurrentPic flag setting in DPB descriptor).");
          }
        }
        v114 = v308;
        if ( *((_DWORD *)v112 + 1) == 1 && v308 > (unsigned int)v327 )
        {
          v31 = 0;
          TDebugOutputFunctor::operator()(
            a1,
            1306,
            "ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - HEVC Picture control structure - num_ref"
            "_idx_l0_active (%d) for P frame exceeded respect to MaxL0ReferencesForP (%d).",
            v308,
            (_DWORD)v327);
          v114 = v308;
        }
        if ( *((_DWORD *)v112 + 1) == 2 && (v114 > v317 || v309[0] > (unsigned int)v318) )
        {
          v31 = 0;
          TDebugOutputFunctor::operator()(
            a1,
            1306,
            "ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - HEVC Picture control structure - num_ref"
            "_idx_l0_active (%d) for P frame exceeded respect to MaxL0ReferencesForB (%d) or num_ref_idx_l1_active (%d) f"
            "or P frame exceeded respect to MaxL1ReferencesForB (%d).",
            v114,
            v317,
            v309[0],
            (_DWORD)v318);
        }
        v115 = v113;
        v116 = v314;
        v117 = CalculateNumberOfDistinctL0L1EncodeReferences(v324, v314, v320[0], v115);
        if ( v109 != v117 )
        {
          v31 = 0;
          TDebugOutputFunctor::operator()(
            a1,
            1306,
            "ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - HEVC Picture control structure - Number "
            "of unique elements in L0 + L1 lists (%d) has to be exactly the same as the number of DPB entries marked as I"
            "sRefUsedByCurrentPic (%d) for current frame.",
            v117,
            v109);
        }
        v118 = 1;
        if ( v324 )
        {
          for ( n = 0; (unsigned int)n < v116; n = (unsigned int)(n + 1) )
            v118 |= v324[n] < v307;
        }
        if ( v320[0] )
        {
          for ( ii = 0; (unsigned int)ii < v306; ii = (unsigned int)(ii + 1) )
            v118 |= v320[0][ii] < v307;
        }
        if ( !v118 )
        {
          v31 = 0;
          TDebugOutputFunctor::operator()(
            a1,
            1306,
            "ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - HEVC Picture control structure - Indices"
            " in L0 or L1 lists are out of bounds, exceeding the ReferenceFramesReconPictureDescriptorsCount size.");
        }
        v121 = (unsigned int)v327;
        if ( (unsigned int)v327 < v317 )
          v121 = v317;
        if ( v121 < (unsigned int)v318 )
          v121 = (unsigned int)v318;
        if ( v121 > v316 )
        {
          v31 = 0;
          TDebugOutputFunctor::operator()(
            a1,
            1306,
            "ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - Number of reference pictures addressable"
            " by L0 and L1 lists according to caps (MaxLXReferencesForX) exceeds the MaxDPBCapacity value reported. Max L"
            "0 size for P: %d Max L0 size for B: %d Max L1 size: %d Max number of adressable unique frames in DPB between"
            " L0 and L1 lists: %d Reported maximum DPB size %d",
            (_DWORD)v327,
            v317,
            (_DWORD)v318,
            v121,
            v316);
        }
        v122 = v308;
        if ( v308 > *((_DWORD *)v112 + 5) )
        {
          v31 = 0;
          TDebugOutputFunctor::operator()(
            a1,
            1306,
            "ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - HEVC Picture control structure - num_ref"
            "_idx_l0_active_minus1 + 1 (%d) cannot be higher than List0ReferenceFramesCount(%d).",
            v308,
            *((_DWORD *)v112 + 5));
        }
        if ( v309[0] > *((_DWORD *)v112 + 8) )
        {
          v31 = 0;
          TDebugOutputFunctor::operator()(
            a1,
            1306,
            "ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - HEVC Picture control structure - num_ref"
            "_idx_l1_active_minus1 + 1 (%d) cannot be higher than List1ReferenceFramesCount(%d).",
            v309[0],
            *((_DWORD *)v112 + 8));
        }
        v123 = *((_DWORD *)v112 + 16);
        if ( v123 )
        {
          v124 = 1;
          if ( v123 != v122 )
          {
            v31 = 0;
            TDebugOutputFunctor::operator()(
              a1,
              1306,
              "ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - HEVC Picture control structure - List0"
              "RefPicModificationsCount (%d) must be equal to num_ref_idx_l0_active_minus1 + 1 (%d).",
              v123,
              v122);
          }
        }
        else
        {
          v124 = 0;
        }
        v125 = *((_DWORD *)v112 + 20);
        v126 = v309[0];
        if ( v125 )
        {
          v127 = 1;
          if ( v125 != v309[0] )
          {
            v31 = 0;
            TDebugOutputFunctor::operator()(
              a1,
              1306,
              "ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - HEVC Picture control structure - List1"
              "RefPicModificationsCount (%d) must be equal to num_ref_idx_l1_active_minus1 + 1 (%d).",
              v125,
              v309[0]);
            v126 = v309[0];
          }
        }
        else
        {
          v127 = 0;
        }
        memset(&v431, 0, sizeof(v431));
        v432 = 0;
        v128 = 0;
        for ( jj = v315[0]; v128 < v122; ++v128 )
        {
          if ( v124 )
            v130 = &v324[*(unsigned int *)(*((_QWORD *)jj + 9) + 4LL * v128)];
          else
            v130 = &v324[v128];
          *((_DWORD *)&v431.Dimension + v128) = *v130;
        }
        memset(&v408, 0, sizeof(v408));
        v409 = 0;
        for ( kk = 0; kk < v126; ++kk )
        {
          if ( v127 )
            v132 = &v320[0][*(unsigned int *)(*((_QWORD *)jj + 11) + 4LL * kk)];
          else
            v132 = &v320[0][kk];
          *((_DWORD *)&v408.Dimension + kk) = *v132;
        }
        v133 = CalculateNumberOfDistinctL0L1EncodeReferences((unsigned int *)&v431, v122, (unsigned int *)&v408, v126);
        LODWORD(v68) = v133;
        if ( v133 > v316 )
        {
          v31 = 0;
          TDebugOutputFunctor::operator()(
            a1,
            1306,
            "ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - Number of distinct reference pictures in"
            "dexed from pList0ReferenceFrames and List1ReferenceFramesCount lists into ReferenceFramesReconPictureDescrip"
            "torsCount exceeds the MaxDPBCapacity value reported Current DPB size: %d Reported maximum DPB size %d",
            v133,
            v316);
        }
        v67 = 16;
        v98 = v303;
        if ( v307 != *((_DWORD *)v303 + 30) )
        {
LABEL_373:
          v31 = 0;
          TDebugOutputFunctor::operator()(
            a1,
            1306,
            "ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - ReferenceFrames.NumTexture2Ds does not m"
            "atch with ReferenceFramesReconPictureDescriptorsCount.");
        }
LABEL_433:
        v99 = v307;
        if ( v307 <= v67 )
          goto LABEL_434;
        goto LABEL_435;
      }
      v102 = v316;
    }
    else
    {
      v308 = 0;
    }
    v309[0] = 0;
    goto LABEL_292;
  }
  if ( v70 == 1 )
  {
    v71 = (_DWORD *)*((_QWORD *)v303 + 14);
    v318 = v71;
    memset(&v431, 0, 48);
    v72 = (*(__int64 (__fastcall **)(struct ID3D12VideoEncoder *))(*(_QWORD *)v312 + 64LL))(v312);
    if ( !v72 )
      v72 = 1;
    v310 = 0;
    _BitScanForward((unsigned int *)&v72, v72);
    v431.Dimension = v72;
    *((_DWORD *)&v431.Dimension + 1) = 2;
    v431.Alignment = __PAIR64__(v66, v325);
    v431.Width = *((_QWORD *)&v325 + 1);
    memset_0(&v408, 0, 0x54u);
    *(_QWORD *)&v431.SampleDesc.Quality = &v408;
    v431.Format = DXGI_FORMAT_BC5_SNORM;
    if ( (*(int (__fastcall **)(_QWORD, __int64, struct D3D12_RESOURCE_DESC *, __int64))(**((_QWORD **)v323 + 85) + 24LL))(
           *((_QWORD *)v323 + 85),
           42,
           &v431,
           48) < 0
      || !v431.Height )
    {
      TDebugOutputFunctor::operator()(
        a1,
        1306,
        "D3D12VideoEncodeCommandList::EncodeFrame arguments not supported - Call to CheckFeatureCaps (D3D12_FEATURE_VIDEO"
        "_ENCODER_CODEC_CONFIGURATION_SUPPORT, ...) returned failure or not supported.");
      v31 = 0;
    }
    v73 = *(_DWORD **)&v431.SampleDesc.Quality;
    if ( (*v71 & 0x200) != 0 && (**(_DWORD **)&v431.SampleDesc.Quality & 0x10000) == 0 )
    {
      TDebugOutputFunctor::operator()(
        a1,
        1306,
        "D3D12_VIDEO_ENCODER_AV1_PICTURE_CONTROL_FLAGS arguments are not supported - D3D12_VIDEO_ENCODER_AV1_PICTURE_CONT"
        "ROL_FLAG_ENABLE_FRAME_SEGMENTATION_AUTO not supported.");
      v31 = 0;
      v73 = *(_DWORD **)&v431.SampleDesc.Quality;
    }
    if ( (*v71 & 0x400) != 0 && (*v73 & 0x20000) == 0 )
    {
      TDebugOutputFunctor::operator()(
        a1,
        1306,
        "D3D12_VIDEO_ENCODER_AV1_PICTURE_CONTROL_FLAGS arguments are not supported - D3D12_VIDEO_ENCODER_AV1_PICTURE_CONT"
        "ROL_FLAG_ENABLE_FRAME_SEGMENTATION_CUSTOM not supported.");
      v31 = 0;
      v73 = *(_DWORD **)&v431.SampleDesc.Quality;
    }
    if ( (*(_BYTE *)v71 & 0x10) != 0 && (*v73 & 0x4000) == 0 )
    {
      TDebugOutputFunctor::operator()(
        a1,
        1306,
        "D3D12_VIDEO_ENCODER_AV1_PICTURE_CONTROL_FLAGS arguments are not supported - D3D12_VIDEO_ENCODER_AV1_PICTURE_CONT"
        "ROL_FLAG_FRAME_REFERENCE_MOTION_VECTORS not supported.");
      v31 = 0;
      v73 = *(_DWORD **)&v431.SampleDesc.Quality;
    }
    if ( (*v71 & 0x800) != 0 && (*(_BYTE *)v73 & 0x20) == 0 )
    {
      TDebugOutputFunctor::operator()(
        a1,
        1306,
        "D3D12_VIDEO_ENCODER_AV1_PICTURE_CONTROL_FLAGS arguments are not supported - D3D12_VIDEO_ENCODER_AV1_PICTURE_CONT"
        "ROL_FLAG_ENABLE_WARPED_MOTION not supported.");
      v31 = 0;
      v73 = *(_DWORD **)&v431.SampleDesc.Quality;
    }
    if ( (*(_BYTE *)v71 & 4) != 0 && (*v73 & 0x800) == 0 )
    {
      TDebugOutputFunctor::operator()(
        a1,
        1306,
        "D3D12_VIDEO_ENCODER_AV1_PICTURE_CONTROL_FLAGS arguments are not supported - D3D12_VIDEO_ENCODER_AV1_PICTURE_CONT"
        "ROL_FLAG_ENABLE_PALETTE_ENCODING not supported.");
      v31 = 0;
      v73 = *(_DWORD **)&v431.SampleDesc.Quality;
    }
    if ( (*(_BYTE *)v71 & 0x40) != 0 && (*v73 & 0x2000) == 0 )
    {
      TDebugOutputFunctor::operator()(
        a1,
        1306,
        "D3D12_VIDEO_ENCODER_AV1_PICTURE_CONTROL_FLAGS arguments are not supported - D3D12_VIDEO_ENCODER_AV1_PICTURE_CONT"
        "ROL_FLAG_ALLOW_INTRA_BLOCK_COPY not supported.");
      v31 = 0;
      v73 = *(_DWORD **)&v431.SampleDesc.Quality;
    }
    if ( *(char *)v71 < 0 && (*v73 & 0x200) == 0 )
    {
      TDebugOutputFunctor::operator()(
        a1,
        1306,
        "D3D12_VIDEO_ENCODER_AV1_PICTURE_CONTROL_FLAGS arguments are not supported - D3D12_VIDEO_ENCODER_AV1_PICTURE_CONT"
        "ROL_FLAG_USE_SUPER_RESOLUTION not supported.");
      v31 = 0;
      v73 = *(_DWORD **)&v431.SampleDesc.Quality;
    }
    if ( (*v71 & 0x1000) != 0 && (*v73 & 0x200000) == 0 )
    {
      TDebugOutputFunctor::operator()(
        a1,
        1306,
        "D3D12_VIDEO_ENCODER_AV1_PICTURE_CONTROL_FLAGS arguments are not supported - D3D12_VIDEO_ENCODER_AV1_PICTURE_CONT"
        "ROL_FLAG_REDUCED_TX_SET not supported.");
      v31 = 0;
      v73 = *(_DWORD **)&v431.SampleDesc.Quality;
    }
    if ( (*v71 & 0x2000) != 0 && (*v73 & 0x400000) == 0 )
    {
      TDebugOutputFunctor::operator()(
        a1,
        1306,
        "D3D12_VIDEO_ENCODER_AV1_PICTURE_CONTROL_FLAGS arguments are not supported - D3D12_VIDEO_ENCODER_AV1_PICTURE_CONT"
        "ROL_FLAG_MOTION_MODE_SWITCHABLE not supported.");
      v31 = 0;
      v73 = *(_DWORD **)&v431.SampleDesc.Quality;
    }
    if ( (*(_BYTE *)v71 & 8) != 0 && (*v73 & 0x1000000) == 0 )
    {
      TDebugOutputFunctor::operator()(
        a1,
        1306,
        "D3D12_VIDEO_ENCODER_AV1_PICTURE_CONTROL_FLAGS arguments are not supported - D3D12_VIDEO_ENCODER_AV1_FEATURE_FLAG"
        "_SKIP_MODE_PRESENT not supported.");
      v31 = 0;
      v73 = *(_DWORD **)&v431.SampleDesc.Quality;
    }
    if ( (*v71 & 0x4000) != 0 && (*v73 & 0x800000) == 0 )
    {
      TDebugOutputFunctor::operator()(
        a1,
        1306,
        "D3D12_VIDEO_ENCODER_AV1_PICTURE_CONTROL_FLAGS arguments are not supported - D3D12_VIDEO_ENCODER_AV1_PICTURE_CONT"
        "ROL_FLAG_ALLOW_HIGH_PRECISION_MV not supported.");
      v31 = 0;
      v73 = *(_DWORD **)&v431.SampleDesc.Quality;
    }
    if ( (*v71 & 0x200) == 0 && (v73[1] & 0x10000) != 0 )
    {
      TDebugOutputFunctor::operator()(
        a1,
        1306,
        "D3D12_VIDEO_ENCODER_AV1_PICTURE_CONTROL_FLAGS - D3D12_VIDEO_ENCODER_AV1_PICTURE_CONTROL_FLAG_ENABLE_FRAME_SEGMEN"
        "TATION_AUTO is required in RequiredFeatureFlags but not set.");
      v31 = 0;
      v73 = *(_DWORD **)&v431.SampleDesc.Quality;
    }
    if ( (*v71 & 0x400) == 0 && (v73[1] & 0x20000) != 0 )
    {
      TDebugOutputFunctor::operator()(
        a1,
        1306,
        "D3D12_VIDEO_ENCODER_AV1_PICTURE_CONTROL_FLAGS - D3D12_VIDEO_ENCODER_AV1_PICTURE_CONTROL_FLAG_ENABLE_FRAME_SEGMEN"
        "TATION_CUSTOM is required in RequiredFeatureFlags but not set.");
      v31 = 0;
      v73 = *(_DWORD **)&v431.SampleDesc.Quality;
    }
    if ( (*(_BYTE *)v71 & 0x10) == 0 && (v73[1] & 0x4000) != 0 )
    {
      TDebugOutputFunctor::operator()(
        a1,
        1306,
        "D3D12_VIDEO_ENCODER_AV1_PICTURE_CONTROL_FLAGS - D3D12_VIDEO_ENCODER_AV1_PICTURE_CONTROL_FLAG_FRAME_REFERENCE_MOT"
        "ION_VECTORS is required in RequiredFeatureFlags but not set.");
      v31 = 0;
      v73 = *(_DWORD **)&v431.SampleDesc.Quality;
    }
    if ( (*v71 & 0x800) == 0 && (v73[1] & 0x20) != 0 )
    {
      TDebugOutputFunctor::operator()(
        a1,
        1306,
        "D3D12_VIDEO_ENCODER_AV1_PICTURE_CONTROL_FLAGS - D3D12_VIDEO_ENCODER_AV1_PICTURE_CONTROL_FLAG_ENABLE_WARPED_MOTIO"
        "N is required in RequiredFeatureFlags but not set.");
      v31 = 0;
      v73 = *(_DWORD **)&v431.SampleDesc.Quality;
    }
    if ( (*(_BYTE *)v71 & 4) == 0 && (v73[1] & 0x800) != 0 )
    {
      TDebugOutputFunctor::operator()(
        a1,
        1306,
        "D3D12_VIDEO_ENCODER_AV1_PICTURE_CONTROL_FLAGS - D3D12_VIDEO_ENCODER_AV1_PICTURE_CONTROL_FLAG_ENABLE_PALETTE_ENCO"
        "DING is required in RequiredFeatureFlags but not set.");
      v31 = 0;
      v73 = *(_DWORD **)&v431.SampleDesc.Quality;
    }
    if ( (*(_BYTE *)v71 & 0x40) == 0 && (v73[1] & 0x2000) != 0 )
    {
      TDebugOutputFunctor::operator()(
        a1,
        1306,
        "D3D12_VIDEO_ENCODER_AV1_PICTURE_CONTROL_FLAGS - D3D12_VIDEO_ENCODER_AV1_PICTURE_CONTROL_FLAG_ALLOW_INTRA_BLOCK_C"
        "OPY is required in RequiredFeatureFlags but not set.");
      v31 = 0;
      v73 = *(_DWORD **)&v431.SampleDesc.Quality;
    }
    if ( *(char *)v71 >= 0 && (v73[1] & 0x200) != 0 )
    {
      TDebugOutputFunctor::operator()(
        a1,
        1306,
        "D3D12_VIDEO_ENCODER_AV1_PICTURE_CONTROL_FLAGS - D3D12_VIDEO_ENCODER_AV1_PICTURE_CONTROL_FLAG_USE_SUPER_RESOLUTIO"
        "N is required in RequiredFeatureFlags but not set.");
      v31 = 0;
      v73 = *(_DWORD **)&v431.SampleDesc.Quality;
    }
    if ( (*v71 & 0x1000) == 0 && (v73[1] & 0x200000) != 0 )
    {
      TDebugOutputFunctor::operator()(
        a1,
        1306,
        "D3D12_VIDEO_ENCODER_AV1_PICTURE_CONTROL_FLAGS - D3D12_VIDEO_ENCODER_AV1_PICTURE_CONTROL_FLAG_REDUCED_TX_SET is r"
        "equired in RequiredFeatureFlags but not set.");
      v31 = 0;
      v73 = *(_DWORD **)&v431.SampleDesc.Quality;
    }
    if ( (*v71 & 0x2000) == 0 && (v73[1] & 0x400000) != 0 )
    {
      TDebugOutputFunctor::operator()(
        a1,
        1306,
        "D3D12_VIDEO_ENCODER_AV1_PICTURE_CONTROL_FLAGS - D3D12_VIDEO_ENCODER_AV1_PICTURE_CONTROL_FLAG_MOTION_MODE_SWITCHA"
        "BLE is required in RequiredFeatureFlags but not set.");
      v31 = 0;
      v73 = *(_DWORD **)&v431.SampleDesc.Quality;
    }
    if ( (*(_BYTE *)v71 & 8) == 0 && (v73[1] & 0x1000000) != 0 )
    {
      TDebugOutputFunctor::operator()(
        a1,
        1306,
        "D3D12_VIDEO_ENCODER_AV1_PICTURE_CONTROL_FLAGS - D3D12_VIDEO_ENCODER_AV1_PICTURE_CONTROL_FLAG_ENABLE_SKIP_MODE is"
        " required in RequiredFeatureFlags but not set.");
      v31 = 0;
      v73 = *(_DWORD **)&v431.SampleDesc.Quality;
    }
    if ( (*v71 & 0x4000) == 0 && (v73[1] & 0x800000) != 0 )
    {
      TDebugOutputFunctor::operator()(
        a1,
        1306,
        "D3D12_VIDEO_ENCODER_AV1_PICTURE_CONTROL_FLAGS - D3D12_VIDEO_ENCODER_AV1_PICTURE_CONTROL_FLAG_ALLOW_HIGH_PRECISIO"
        "N_MV is required in RequiredFeatureFlags but not set.");
      v31 = 0;
      v73 = *(_DWORD **)&v431.SampleDesc.Quality;
    }
    if ( (*(_BYTE *)v71 & 2) != 0 && ((v73[1] & 0x4000000) != 0 || (*v73 & 0x4000000) != 0) )
    {
      TDebugOutputFunctor::operator()(
        a1,
        1306,
        "D3D12_VIDEO_ENCODER_AV1_PICTURE_CONTROL_FLAGS - D3D12_VIDEO_ENCODER_AV1_PICTURE_CONTROL_FLAG_DISABLE_CDF_UPDATE "
        "is not supported by driver with D3D12_VIDEO_ENCODER_AV1_FEATURE_FLAG_DISABLE_CDF_UPDATE_UNSUPPORTED.");
      v31 = 0;
    }
    v74 = *((_DWORD *)v61 + 1);
    v314 = v74;
    if ( v71[1] && !v74 )
    {
      v31 = 0;
      TDebugOutputFunctor::operator()(
        a1,
        1306,
        "ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - AV1 Picture control structure - Only key fra"
        "mes are supported as D3D12_VIDEO_ENCODER_CODEC_PICTURE_CONTROL_SUPPORT_AV1 is reporting zero supported references.");
    }
    v75 = *((_DWORD *)v61 + 2);
    v76 = v71[1];
    if ( !_bittest(&v75, v76) )
    {
      v31 = 0;
      TDebugOutputFunctor::operator()(
        a1,
        1306,
        "ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - AV1 Picture control structure - Requested Fr"
        "ameType (%d) is not reported as supported in D3D12_VIDEO_ENCODER_CODEC_PICTURE_CONTROL_SUPPORT_AV1.SupportedFrameTypes (%x)",
        v76,
        *((_DWORD *)v61 + 2));
    }
    v77 = 0;
    do
    {
      if ( v71[v77 + 144] >= 8u )
      {
        v31 = 0;
        TDebugOutputFunctor::operator()(
          a1,
          1306,
          "ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - AV1 Picture control structure - ReferenceI"
          "ndices[%d] index is out of bounds of [0..7] to index into ReferenceFramesReconPictureDescriptors.",
          v77);
      }
      v77 = (unsigned int)(v77 + 1);
    }
    while ( (unsigned int)v77 < 7 );
    v78 = *(_DWORD *)(*(_QWORD *)&v431.SampleDesc.Quality + 76LL);
    v79 = v71[14];
    if ( v79 > v78 )
    {
      v31 = 0;
      TDebugOutputFunctor::operator()(
        a1,
        1306,
        "ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - AV1 Picture control structure - TemporalLaye"
        "rIndexPlus1 %d must be in the range [0..D3D12_VIDEO_ENCODER_AV1_CODEC_CONFIGURATION_SUPPORT.MaxTemporalLayers (%d)].",
        v79,
        v78);
    }
    v80 = *(_DWORD *)(*(_QWORD *)&v431.SampleDesc.Quality + 80LL);
    v81 = v71[15];
    if ( v81 > v80 )
    {
      v31 = 0;
      TDebugOutputFunctor::operator()(
        a1,
        1306,
        "ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - AV1 Picture control structure - SpatialLayer"
        "IndexPlus1 %d must be in the range [0..D3D12_VIDEO_ENCODER_AV1_CODEC_CONFIGURATION_SUPPORT.MaxSpatialLayers (%d)].",
        v81,
        v80);
    }
    v82 = 1;
    v302[0] = 1;
    v83 = 0;
    v308 = 0;
    v84 = 0;
    v85 = 0;
    v86 = v318;
    do
    {
      v87 = v85 << 6;
      v88 = v86[16 * v85 + 16];
      if ( v88 != 255 )
      {
        v308 = v83 + 1;
        v300 |= v88 < *((_DWORD *)v303 + 30);
        v89 = *(_DWORD *)((char *)v86 + v87 + 68);
        v301 |= v89 <= v86[14];
        v90 = *(_DWORD *)(*(_QWORD *)v309 + 12LL);
        if ( v90 )
          v302[0] = _bittest(&v90, *(_DWORD *)((char *)v86 + v87 + 80)) & v82;
        v91 = *(_DWORD *)(*(_QWORD *)&v431.SampleDesc.Quality + 76LL);
        if ( v89 > v91 )
        {
          v31 = 0;
          TDebugOutputFunctor::operator()(
            a1,
            1306,
            "ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - Reference descriptor %d - TemporalLayerI"
            "ndexPlus1 %d must be in the range [0..D3D12_VIDEO_ENCODER_AV1_CODEC_CONFIGURATION_SUPPORT.MaxTemporalLayers (%d)].",
            v84,
            v89,
            v91);
          v86 = v318;
        }
        v92 = *(_DWORD *)(*(_QWORD *)&v431.SampleDesc.Quality + 80LL);
        v93 = *(_DWORD *)((char *)v86 + v87 + 72);
        if ( v93 > v92 )
        {
          v31 = 0;
          TDebugOutputFunctor::operator()(
            a1,
            1306,
            "ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - Reference descriptor %d - SpatialLayerIn"
            "dexPlus1 %d must be in the range [0..D3D12_VIDEO_ENCODER_AV1_CODEC_CONFIGURATION_SUPPORT.MaxSpatialLayers (%d)].",
            v84,
            v93,
            v92);
          v86 = v318;
        }
        v83 = v308;
      }
      ++v84;
      ++v85;
      v82 = v302[0];
    }
    while ( v84 < 8 );
    *(_OWORD *)Src = 0;
    v333 = 0;
    v94 = 0;
    v95 = (char *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
    while ( v94 < 7 )
    {
      v96 = v86[16 * (unsigned __int64)(unsigned int)v86[v94 + 144] + 16];
      if ( v96 != 255 )
      {
        if ( v95 == v333 )
        {
          std::vector<unsigned int>::_Emplace_reallocate<unsigned int>(Src);
          v95 = (char *)Src[1];
          v86 = v318;
        }
        else
        {
          *(_DWORD *)v95 = v96;
          v95 = (char *)Src[1] + 4;
          Src[1] = (char *)Src[1] + 4;
        }
      }
      ++v94;
    }
    if ( (v95 - (char *)Src[0]) >> 2 )
    {
      std::_Sort_unchecked<unsigned int *,std::less<void>>(Src[0]);
      v97 = _std_unique_4(Src[0], Src[1]);
      std::vector<unsigned int>::erase(Src, v315, v97, Src[1]);
      v68 = ((char *)Src[1] - (char *)Src[0]) >> 2;
      if ( (unsigned int)v68 > v314 )
      {
        v31 = 0;
        TDebugOutputFunctor::operator()(
          a1,
          1306,
          "ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - Number of distinct ReferenceFramesReconPic"
          "tureDescriptors[i].ReconstructedPictureResourceIndex into ppTextures exceeds maximum MaxUniqueReferencesPerFra"
          "me reported Current DPB size: %d Reported maximum DPB size %d",
          v68,
          v314);
      }
    }
    else
    {
      LODWORD(v68) = v320[0];
    }
    v307 = 8;
    v67 = 9;
    if ( !v302[0] )
    {
      v31 = 0;
      TDebugOutputFunctor::operator()(
        a1,
        1306,
        "ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - AV1 Picture control structure - WarpedMotion"
        "Info not supported. See values supported values for D3D12_VIDEO_ENCODER_AV1_REFERENCE_WARPED_MOTION_TRANSFORMATION_FLAGS.");
    }
    if ( !v318[1] )
    {
      if ( v318[152] != 255 )
      {
        v31 = 0;
        TDebugOutputFunctor::operator()(
          a1,
          1306,
          "ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - AV1 Picture control structure - RefreshFra"
          "meFlags must be 0xFF for D3D12_VIDEO_ENCODER_AV1_FRAME_TYPE_KEY_FRAME.");
      }
      if ( v308 )
      {
        v31 = 0;
        TDebugOutputFunctor::operator()(
          a1,
          1306,
          "ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - AV1 Picture control structure - Key Frames"
          " must not use any references. Must set all ReconstructedPictureResourceIndex DPB entries to D3D12_VIDEO_ENCODE"
          "R_AV1_INVALID_DPB_RESOURCE_INDEX.");
      }
    }
    std::vector<enum DXGI_FORMAT>::_Tidy(Src);
    v98 = v303;
    v99 = v307;
  }
  else
  {
    v98 = v303;
    v99 = 0;
  }
LABEL_434:
  if ( *((_DWORD *)v98 + 30) > v67 )
  {
LABEL_435:
    v31 = 0;
    TDebugOutputFunctor::operator()(
      a1,
      1306,
      "ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - ReferenceFramesReconPictureDescriptors has (%d"
      ") entries but the selected codec supports at most (%d) entries.",
      v99,
      v67);
  }
  if ( !v300 )
  {
    v31 = 0;
    TDebugOutputFunctor::operator()(
      a1,
      1306,
      "ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - DPB descriptors have indices set in Reconstruc"
      "tedPictureResourceIndex out of bounds respect to ReferenceFramesReconPictureDescriptorsCount (%d).",
      v307);
  }
  if ( !v301 )
  {
    v31 = 0;
    TDebugOutputFunctor::operator()(
      a1,
      1306,
      "ID3D12VideoEncodeCommandList::EncodeFrame arguments not supported - DPB descriptors for the current picture have t"
      "emporal layers indices higher than the current picture temporal layer index.");
  }
  memset_0(v378, 0, 0xE0u);
  v153 = (*(__int64 (__fastcall **)(struct ID3D12VideoEncoder *))(*(_QWORD *)v312 + 64LL))(v312);
  if ( !v153 )
    v153 = 1;
  v310 = 0;
  _BitScanForward(&v153, v153);
  v378[0] = v153;
  v378[1] = (*(__int64 (__fastcall **)(struct ID3D12VideoEncoder *))(*(_QWORD *)v312 + 80LL))(v312);
  v378[2] = (*(__int64 (__fastcall **)(struct ID3D12VideoEncoder *))(*(_QWORD *)v312 + 104LL))(v312);
  v381 = *((_OWORD *)v98 + 1);
  v382 = *((_OWORD *)v98 + 2);
  v380 = *((_OWORD *)v98 + 5);
  v383 = *((_DWORD *)v98 + 1);
  v384 = *((_DWORD *)v98 + 14);
  v387 = v68;
  v154 = (*(__int64 (__fastcall **)(struct ID3D12VideoEncoderHeap1 *))(*(_QWORD *)v313 + 104LL))(v313);
  v155 = v154;
  v334 = 0;
  v335 = 0;
  if ( v154 )
    std::vector<D3D12_VIDEO_ENCODER_PICTURE_RESOLUTION_RATIO_DESC>::_Resize_reallocate<std::_Value_init_tag>(
      &v334,
      v154);
  v156 = (*(__int64 (__fastcall **)(struct ID3D12VideoEncoderHeap1 *, _QWORD, _QWORD))(*(_QWORD *)v313 + 112LL))(
           v313,
           v155,
           v334);
  ThrowFailure(v156);
  v385 = v155;
  v386 = v334;
  v395 = *((_OWORD *)v98 + 4);
  if ( !*((_DWORD *)v98 + 4) || (*((_BYTE *)v98 + 20) & 1) != 0 )
  {
    v397 = 1;
    v398 = (*((unsigned __int8 *)v98 + 100) >> 1) & 1;
  }
  if ( (*((_BYTE *)v98 + 100) & 4) != 0 )
  {
    v399 = 1;
    if ( *((_DWORD *)v98 + 40) )
      v401 = 0;
    else
      v401 = *(_DWORD *)(*((_QWORD *)v98 + 21) + 4LL);
  }
  if ( (*((_BYTE *)v98 + 100) & 8) != 0 )
  {
    v402 = 1;
    if ( *((_DWORD *)v98 + 36) )
      v404 = 0;
    else
      v404 = *(_DWORD *)(*((_QWORD *)v98 + 19) + 16LL);
    v405 = v304;
  }
  v157 = v313;
  if ( (*((_BYTE *)v98 + 20) & 2) != 0 )
  {
    v406 = 1;
    v407 = (*(__int64 (__fastcall **)(struct ID3D12VideoEncoderHeap1 *))(*(_QWORD *)v313 + 120LL))(v313);
  }
  v338 = 0;
  v328 = 0;
  v337 = 0;
  v347 = 0;
  v339 = 0;
  v346 = 0;
  v158 = (*(__int64 (__fastcall **)(struct ID3D12VideoEncoderHeap1 *))(*(_QWORD *)v157 + 80LL))(v157);
  if ( !v158 )
  {
    v391 = &v338;
    v160 = (__int64 *)&v328;
    v392 = 4;
LABEL_465:
    v390 = 4;
    v393 = v160;
    goto LABEL_466;
  }
  v159 = v158 - 1;
  if ( !v159 )
  {
    v391 = &v337;
    v160 = &v347;
LABEL_462:
    v392 = 8;
    goto LABEL_465;
  }
  if ( v159 == 1 )
  {
    v391 = &v339;
    v160 = &v346;
    goto LABEL_462;
  }
LABEL_466:
  v379 = v326;
  v161 = DWORD1(v326);
  v330 = 0;
  v331 = 0;
  if ( v385 )
    std::vector<D3D12_FEATURE_DATA_VIDEO_ENCODER_RESOLUTION_SUPPORT_LIMITS1>::_Resize_reallocate<std::_Value_init_tag>(&v330);
  v394 = v330;
  if ( (*(int (__fastcall **)(_QWORD, __int64, _DWORD *, __int64))(**((_QWORD **)v323 + 85) + 24LL))(
         *((_QWORD *)v323 + 85),
         55,
         v378,
         224) < 0 )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1306,
      "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - CheckFeatureSupport(D3D12_FEATURE_VIDEO_EN"
      "CODER_SUPPORT2,...) for the given input returned failure.");
    if ( (_QWORD)v330 )
    {
      std::_Deallocate<16>(v330, 8 * ((v331 - (__int64)v330) >> 3));
      v330 = 0;
      v331 = 0;
    }
    if ( (_QWORD)v334 )
      std::_Deallocate<16>(v334, (v335 - v334) & 0xFFFFFFFFFFFFFFF8uLL);
    return 2147942487LL;
  }
  v354[0] = (*(__int64 (__fastcall **)(struct ID3D12VideoEncoder *))(*(_QWORD *)v312 + 80LL))(v312);
  v354[1] = 0;
  v354[2] = v325;
  v354[3] = v66;
  v355 = *((_QWORD *)&v325 + 1);
  v356 = v329;
  v162 = DWORD1(v329);
  v357 = (*(__int64 (__fastcall **)(struct ID3D12VideoEncoder *))(*(_QWORD *)v312 + 104LL))(v312);
  v358 = *((_QWORD *)v98 + 6);
  v359 = 0;
  v360 = v326;
  v361 = v161;
  v362 = *((_QWORD *)&v326 + 1);
  v363 = *((_DWORD *)v98 + 14);
  v364 = 0;
  v365 = *((_OWORD *)v98 + 4);
  if ( (v389 & 1) == 0 )
  {
    TDebugOutputFunctor::operator()(
      a1,
      1306,
      "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - CheckFeatureSupport(D3D12_FEATURE_VIDEO_EN"
      "CODER_SUPPORT2,...) returned the following flags ValidationFlags: 0x%x SupportFlags: 0x%x",
      v388,
      v389);
    v31 = 0;
    ValidateVideoEncoderSupportSimultaneousHazards(
      (const struct D3D12_FEATURE_DATA_VIDEO_ENCODER_SUPPORT2 *)v378,
      (const struct D3D12_VIDEO_ENCODER_INPUT_MAP_SESSION_INFO *)v354,
      v323,
      a1);
  }
  if ( (v389 & 0x8000) == 0 )
  {
    v163 = *((_QWORD *)v322 + 8);
    if ( v163 )
    {
      v164 = (CResource *)QIFrom<CResource>(v163);
      CResource::GetDesc(v164, &v408);
      if ( SLOBYTE(v408.Flags) >= 0 )
      {
        TDebugOutputFunctor::operator()(
          a1,
          1306,
          "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - pOutputArguments->ReconstructedPicture"
          ".pReconstructedPicture MUST have the D3D12_RESOURCE_FLAG_VIDEO_ENCODE_REFERENCE_ONLY set when D3D12_VIDEO_ENCO"
          "DER_SUPPORT_FLAG_READABLE_RECONSTRUCTED_PICTURE_LAYOUT_AVAILABLE is not supported.");
        v31 = 0;
      }
    }
    v165 = 0;
    for ( mm = v303; (unsigned int)v165 < *((_DWORD *)v303 + 30); mm = v303 )
    {
      v167 = *(_QWORD *)(*((_QWORD *)mm + 16) + 8 * v165);
      if ( v167 )
      {
        v168 = (CResource *)QIFrom<CResource>(v167);
        CResource::GetDesc(v168, &v408);
        if ( SLOBYTE(v408.Flags) >= 0 )
        {
          TDebugOutputFunctor::operator()(
            a1,
            1306,
            "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - pInputArguments->PictureControlDesc."
            "ReferenceFrames.ppTexture2Ds MUST ALL have the D3D12_RESOURCE_FLAG_VIDEO_ENCODE_REFERENCE_ONLY set when D3D1"
            "2_VIDEO_ENCODER_SUPPORT_FLAG_READABLE_RECONSTRUCTED_PICTURE_LAYOUT_AVAILABLE is not supported.");
          v31 = 0;
        }
      }
      v165 = (unsigned int)(v165 + 1);
    }
  }
  if ( *(_DWORD *)v322 == 1 )
  {
    v169 = (*(__int64 (__fastcall **)(struct ID3D12VideoEncoderHeap1 *))(*(_QWORD *)v313 + 72LL))(v313);
    if ( *((_DWORD *)v322 + 2) )
    {
      if ( *((_DWORD *)v322 + 2) == 1 )
      {
        if ( (v389 & 0x100000) == 0 )
        {
          v31 = 0;
          TDebugOutputFunctor::operator()(
            a1,
            1306,
            "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - D3D12_VIDEO_ENCODER_SUBREGION_COMPRE"
            "SSED_BITSTREAM_BUFFER_MODE_SINGLE_BUFFER was requested but D3D12_VIDEO_ENCODER_SUPPORT_FLAG_SUBREGION_NOTIFI"
            "CATION_SINGLE_BUFFER_AVAILABLE is not supported.");
        }
        if ( (v169 & 2) != 0 )
          goto LABEL_498;
        v170 = "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - D3D12_VIDEO_ENCODER_SUBREGION_COM"
               "PRESSED_BITSTREAM_BUFFER_MODE_SINGLE_BUFFER was requested but D3D12_VIDEO_ENCODER_HEAP_FLAG_ALLOW_SUBREGI"
               "ON_NOTIFICATION_SINGLE_BUFFER is not set in the encoder heap.";
      }
      else
      {
        v170 = "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - Invalid D3D12_VIDEO_ENCODER_SUBRE"
               "GION_COMPRESSED_BITSTREAM_BUFFER_MODE.";
      }
LABEL_497:
      v31 = 0;
      TDebugOutputFunctor::operator()(a1, 1306, v170);
      goto LABEL_498;
    }
    if ( (v389 & 0x80000) == 0 )
    {
      v31 = 0;
      TDebugOutputFunctor::operator()(
        a1,
        1306,
        "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - D3D12_VIDEO_ENCODER_SUBREGION_COMPRESSED"
        "_BITSTREAM_BUFFER_MODE_ARRAY_OF_BUFFERS was requested but D3D12_VIDEO_ENCODER_SUPPORT_FLAG_SUBREGION_NOTIFICATIO"
        "N_ARRAY_OF_BUFFERS_AVAILABLE is not supported.");
    }
    if ( (v169 & 1) == 0 )
    {
      v170 = "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - D3D12_VIDEO_ENCODER_SUBREGION_COMPR"
             "ESSED_BITSTREAM_BUFFER_MODE_ARRAY_OF_BUFFERS was requested but D3D12_VIDEO_ENCODER_HEAP_FLAG_ALLOW_SUBREGIO"
             "N_NOTIFICATION_ARRAY_OF_BUFFERS is not set in the encoder heap.";
      goto LABEL_497;
    }
LABEL_498:
    if ( (v169 & 0x10) != 0 && (v389 & 0x2000000) == 0 )
    {
      v31 = 0;
      TDebugOutputFunctor::operator()(
        a1,
        1306,
        "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - D3D12_VIDEO_ENCODER_HEAP_FLAG_ENABLE_SUB"
        "REGION_NOTIFICATION_SEQUENTIAL_SIGNALING is set in the encoder heap but D3D12_VIDEO_ENCODER_SUPPORT_FLAG_SUBREGI"
        "ON_NOTIFICATION_SEQUENTIAL_SIGNALING_AVAILABLE is not supported.");
    }
  }
  v171 = v303;
  if ( (v389 & 0x10000) == 0 && (*((_BYTE *)v303 + 240) & 1) != 0 )
  {
    v31 = 0;
    TDebugOutputFunctor::operator()(
      a1,
      1306,
      "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - D3D12_VIDEO_ENCODER_OPTIONAL_METADATA_ENAB"
      "LE_FLAG_QP_MAP was requested but D3D12_VIDEO_ENCODER_SUPPORT_FLAG_PER_BLOCK_QP_MAP_METADATA_AVAILABLE is not supported.");
  }
  if ( (v389 & 0x20000) == 0 && (*((_BYTE *)v171 + 240) & 2) != 0 )
  {
    v31 = 0;
    TDebugOutputFunctor::operator()(
      a1,
      1306,
      "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - D3D12_VIDEO_ENCODER_OPTIONAL_METADATA_ENAB"
      "LE_FLAG_SATD_MAP was requested but D3D12_VIDEO_ENCODER_SUPPORT_FLAG_PER_BLOCK_SATD_MAP_METADATA_AVAILABLE is not supported.");
  }
  if ( (v389 & 0x40000) == 0 && (*((_BYTE *)v171 + 240) & 4) != 0 )
  {
    v31 = 0;
    TDebugOutputFunctor::operator()(
      a1,
      1306,
      "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - D3D12_VIDEO_ENCODER_OPTIONAL_METADATA_ENAB"
      "LE_FLAG_RC_BIT_ALLOCATION_MAP was requested but D3D12_VIDEO_ENCODER_SUPPORT_FLAG_PER_BLOCK_RC_BIT_ALLOCATION_MAP_M"
      "ETADATA_AVAILABLE is not supported.");
  }
  if ( (v389 & 0x200000) == 0 && (*((_BYTE *)v171 + 240) & 8) != 0 )
  {
    v31 = 0;
    TDebugOutputFunctor::operator()(
      a1,
      1306,
      "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - D3D12_VIDEO_ENCODER_OPTIONAL_METADATA_ENAB"
      "LE_FLAG_FRAME_PSNR was requested but D3D12_VIDEO_ENCODER_SUPPORT_FLAG_FRAME_PSNR_METADATA_AVAILABLE is not supported.");
  }
  if ( (v389 & 0x400000) == 0 && (*((_BYTE *)v171 + 240) & 0x10) != 0 )
  {
    v31 = 0;
    TDebugOutputFunctor::operator()(
      a1,
      1306,
      "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - D3D12_VIDEO_ENCODER_OPTIONAL_METADATA_ENAB"
      "LE_FLAG_SUBREGIONS_PSNR was requested but D3D12_VIDEO_ENCODER_SUPPORT_FLAG_SUBREGIONS_PSNR_METADATA_AVAILABLE is not supported.");
  }
  if ( (v389 & 2) == 0 && (*(_BYTE *)v171 & 2) != 0 )
  {
    v31 = 0;
    TDebugOutputFunctor::operator()(
      a1,
      1306,
      "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - Rate control reconfiguration was requested"
      " but it's not supported.");
  }
  if ( (v389 & 4) == 0 && (*(_BYTE *)v171 & 1) != 0 )
  {
    v31 = 0;
    TDebugOutputFunctor::operator()(
      a1,
      1306,
      "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - Resolution reconfiguration was requested b"
      "ut it's not supported.");
  }
  if ( (v389 & 0x80u) == 0 && (*(_BYTE *)v171 & 4) != 0 )
  {
    v31 = 0;
    TDebugOutputFunctor::operator()(
      a1,
      1306,
      "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - Subregion layout reconfiguration was reque"
      "sted but it's not supported.");
  }
  v172 = &`ValidateEncodeFrame'::`3'::rgRateControlModeFlagChecks;
  do
  {
    v173 = v303;
    if ( ((_DWORD)v172[2] & v389) == 0 && (*((_DWORD *)v303 + 5) & *(_DWORD *)v172) != 0 )
    {
      v31 = 0;
      TDebugOutputFunctor::operator()(
        a1,
        1306,
        "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - Rate control optional mode %s is request"
        "ed but it's not reported in the SupportFlags: %s.",
        (const char *)v172[1],
        (const char *)v172[3]);
      v173 = v303;
    }
    v172 += 4;
  }
  while ( v172 != (__int64 *)&load_config_used );
  if ( (v389 & 0x2000) != 0 && *((char *)v173 + 20) < 0 )
  {
    v174 = *((_DWORD *)v173 + 4);
    if ( !v174 )
    {
      v178 = **((_DWORD **)v173 + 4);
      goto LABEL_542;
    }
    v175 = v174 - 1;
    if ( !v175 )
    {
      v178 = *(_DWORD *)(*((_QWORD *)v173 + 4) + 12LL);
      goto LABEL_542;
    }
    v176 = v175 - 1;
    if ( !v176 )
    {
      v178 = *(_DWORD *)(*((_QWORD *)v173 + 4) + 48LL);
      goto LABEL_542;
    }
    v177 = v176 - 1;
    if ( !v177 )
    {
      v178 = *(_DWORD *)(*((_QWORD *)v173 + 4) + 56LL);
      goto LABEL_542;
    }
    if ( v177 == 1 )
    {
      v178 = *(_DWORD *)(*((_QWORD *)v173 + 4) + 64LL);
LABEL_542:
      if ( v178 > v396 )
      {
        v31 = 0;
        TDebugOutputFunctor::operator()(
          a1,
          1306,
          "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - Rate control QualityVsSpeed (%d) is hi"
          "gher than reported MaxQualityVsSpeed (%d).",
          v178,
          v396);
      }
    }
  }
  v179 = 56LL * v319;
  v308 = *(_DWORD *)(v179 + v394);
  LODWORD(v318) = *(_DWORD *)(v179 + v394 + 4);
  v314 = *(_DWORD *)(v179 + v394 + 8);
  v317 = *(_DWORD *)(v179 + v394 + 12);
  v309[0] = *(_DWORD *)(v179 + v394 + 52);
  LOBYTE(v172) = 0;
  v306 = (unsigned int)v172;
  v180 = (*(__int64 (__fastcall **)(struct ID3D12VideoEncoderHeap1 *))(*(_QWORD *)v313 + 80LL))(v313);
  if ( v180 )
  {
    v181 = v180 - 1;
    if ( v181 )
    {
      if ( v181 == 1 )
      {
        v182 = *(_DWORD *)(*((_QWORD *)v303 + 14) + 4LL);
        if ( v182 == 2 )
          goto LABEL_548;
        if ( v182 != 1 && v182 != 3 )
        {
          v184 = v182 == 0;
          goto LABEL_555;
        }
LABEL_552:
        v183 = (v309[0] & 4) == 0;
LABEL_549:
        if ( !v183 )
        {
          LOBYTE(v172) = 1;
          goto LABEL_567;
        }
      }
      goto LABEL_568;
    }
    v185 = *(_DWORD *)(*((_QWORD *)v303 + 14) + 4LL);
    if ( v185 )
    {
      if ( v185 == 1 )
      {
LABEL_559:
        v183 = (v309[0] & 2) == 0;
        goto LABEL_549;
      }
      if ( v185 == 2 )
        goto LABEL_552;
      v184 = v185 == 3;
LABEL_555:
      if ( !v184 )
        goto LABEL_568;
    }
LABEL_548:
    v183 = (v309[0] & 1) == 0;
    goto LABEL_549;
  }
  v186 = *(_DWORD *)(*((_QWORD *)v303 + 14) + 4LL);
  switch ( v186 )
  {
    case 0:
      goto LABEL_548;
    case 1:
      goto LABEL_559;
    case 2:
      goto LABEL_552;
    case 3:
      LODWORD(v172) = (v309[0] & 1) != 0;
LABEL_567:
      v306 = (unsigned int)v172;
      break;
  }
LABEL_568:
  if ( (*((_BYTE *)v303 + 20) & 2) != 0
    && (*(unsigned int (__fastcall **)(struct ID3D12VideoEncoderHeap1 *))(*(_QWORD *)v313 + 120LL))(v313) )
  {
    if ( !(_BYTE)v172 )
    {
      v31 = 0;
      TDebugOutputFunctor::operator()(
        a1,
        1306,
        "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - D3D12_FEATURE_DATA_VIDEO_ENCODER_RESOLUT"
        "ION_SUPPORT_LIMITS1.FrameAnalysis.SupportFlags (0x%x) does not support the current frame type",
        v309[0]);
    }
    if ( ((*(__int64 (__fastcall **)(struct ID3D12VideoEncoderHeap1 *))(*(_QWORD *)v313 + 72LL))(v313) & 8) == 0 )
    {
      v31 = 0;
      TDebugOutputFunctor::operator()(
        a1,
        1306,
        "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - D3D12_VIDEO_ENCODER_HEAP_FLAG_ALLOW_RATE"
        "_CONTROL_FRAME_ANALYSIS not set in the encoder heap passed to EncodeFrame");
    }
    v187 = v303;
    if ( (v309[0] & 8) == 0 && (*((_BYTE *)v303 + 100) & 1) != 0 && !*((_QWORD *)v322 + 12) )
    {
      v31 = 0;
      TDebugOutputFunctor::operator()(
        a1,
        1306,
        "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - FrameAnalysisReconstructedPicture.pRecon"
        "structedPicture cannot be NULL when D3D12_VIDEO_ENCODER_PICTURE_CONTROL_FLAG_USED_AS_REFERENCE_PICTURE set and D"
        "3D12_VIDEO_ENCODER_RATE_CONTROL_FRAME_ANALYSIS_SUPPORT_FLAG_EXTERNAL_DPB_DOWNSCALING not supported");
      v187 = v303;
    }
    v188 = *((_QWORD *)v187 + 23);
    if ( !v188 )
    {
      TDebugOutputFunctor::operator()(a1, 1305, "D3D12_VIDEO_ENCODER_FRAME_ANALYSIS::pDownscaledFrame cannot be null.");
      v31 = 0;
      goto LABEL_600;
    }
    v189 = QIFrom<CResource>(v188);
    CResource::GetDesc((CResource *)v189, &v408);
    if ( v408.Dimension != D3D12_RESOURCE_DIMENSION_TEXTURE2D )
    {
      TDebugOutputFunctor::operator()(
        a1,
        1305,
        "D3D12_VIDEO_ENCODER_FRAME_ANALYSIS::pDownscaledFrame must have a resource dimension of D3D12_RESOURCE_DIMENSION_TEXTURE2D.");
      v31 = 0;
    }
    if ( *(_BYTE *)(v189 + 392) == 3 )
    {
      TDebugOutputFunctor::operator()(
        a1,
        1305,
        "D3D12_VIDEO_ENCODER_FRAME_ANALYSIS::pDownscaledFrame must not be a reserved resource.");
      goto LABEL_586;
    }
    if ( !IsVideoHeapTypeSupported(&v311, (struct CResource *)v189) )
    {
      TDebugOutputFunctor::operator()(
        a1,
        1305,
        "D3D12_VIDEO_ENCODER_FRAME_ANALYSIS::pDownscaledFrame must have heap type D3D12_HEAP_TYPE_DEFAULT, D3D12_HEAP_TYP"
        "E_UPLOAD, D3D12_HEAP_TYPE_GPU_UPLOAD, or D3D12_HEAP_TYPE_CUSTOM. For D3D12_HEAP_TYPE_CUSTOM, CPUPageProperty mus"
        "t not be equal to D3D12_CPU_PAGE_PROPERTY_WRITE_BACK.See D3D12_FEATURE_VIDEO_ARCHITECTURE.");
LABEL_586:
      v31 = 0;
    }
    if ( *((_QWORD *)v303 + 24) >= (unsigned __int64)(*(_DWORD *)(v189 + 244) & 0xFFFFFF) )
    {
      TDebugOutputFunctor::operator()(
        a1,
        1305,
        "The D3D12_VIDEO_ENCODER_FRAME_ANALYSIS::Subresource exceeds the number of subresources for D3D12_VIDEO_ENCODER_F"
        "RAME_ANALYSIS::pDownscaledFrame.");
      goto LABEL_593;
    }
    if ( *(_BYTE *)(v189 + 247) != 1 )
    {
      TDebugOutputFunctor::operator()(
        a1,
        1305,
        "The subresource for reference frame at index %d has MipLevels != 1 which is not supported with EncodeFrame.");
      goto LABEL_593;
    }
    v191 = ResourceValidationInfo::ArraySize((ResourceValidationInfo *)(v189 + 224));
    v190 = *(_DWORD *)(v192 + 232) % (unsigned int)v191;
    if ( *(_DWORD *)(v192 + 232) / (unsigned int)v191 )
    {
      TDebugOutputFunctor::operator()(
        a1,
        1305,
        "D3D12_VIDEO_ENCODER_FRAME_ANALYSIS::Subresource must specify PlaneSlice 0 of a planar resource for the chosen ArraySlice.");
LABEL_593:
      v31 = 0;
    }
    v193 = v312;
    v194 = (*(__int64 (__fastcall **)(struct ID3D12VideoEncoder *, __int64))(*(_QWORD *)v312 + 104LL))(v312, v190);
    if ( v408.Format != v194 )
    {
      v195 = (*(unsigned int (__fastcall **)(struct ID3D12VideoEncoder *))(*(_QWORD *)v193 + 104LL))(v193);
      D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v195, v196);
      v198 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v408.Format, v197);
      TDebugOutputFunctor::operator()(
        a1,
        1305,
        "D3D12_VIDEO_ENCODER_FRAME_ANALYSIS::pDownscaledFrame has a format of %s that does not match the encoder which ha"
        "s a format of %s.",
        v198,
        v199);
      v31 = 0;
    }
    v200 = *((unsigned int *)v303 + 12);
    v315[0] = (struct CResource *)(v200 >> (*(__int64 (__fastcall **)(struct ID3D12VideoEncoderHeap1 *))(*(_QWORD *)v313 + 120LL))(v313));
    LODWORD(v200) = *((_DWORD *)v303 + 13);
    v201 = (unsigned int)v200 >> (*(__int64 (__fastcall **)(struct ID3D12VideoEncoderHeap1 *))(*(_QWORD *)v313 + 120LL))(v313);
    if ( v315[0] > (struct CResource *)v408.Width || v201 > v408.Height )
    {
      TDebugOutputFunctor::operator()(
        a1,
        1305,
        "D3D12_VIDEO_ENCODER_FRAME_ANALYSIS::pDownscaledFrame is smaller than the expected downscaled resolution PictureT"
        "argetResolution/(2^Pow2DownscaleFactor).  Expected downscaled width: %d, Expected downscaled height: %d, Resourc"
        "e Width: %I64u, Resource Height: %d",
        LODWORD(v315[0]),
        v201,
        v408.Width,
        v408.Height);
      v31 = 0;
    }
    LOBYTE(v172) = v306;
LABEL_600:
    v202 = v303;
    v203 = *((_DWORD *)v303 + 30);
    if ( v203 != *((_DWORD *)v303 + 50) )
    {
      TDebugOutputFunctor::operator()(
        a1,
        1305,
        "D3D12_VIDEO_ENCODER_FRAME_ANALYSIS::DownscaledReferences.NumTexture2Ds (%d) must match PictureControlDesc.Refere"
        "nceFrames.NumTexture2Ds (%d). The DPB reference frames must be mirrored between the 1st and 2nd pass",
        v203,
        *((_DWORD *)v303 + 50));
      v31 = 0;
LABEL_630:
      if ( (v389 & 0x8000) == 0 )
      {
        v215 = *((_QWORD *)v322 + 12);
        if ( v215 )
        {
          v216 = (CResource *)QIFrom<CResource>(v215);
          CResource::GetDesc(v216, &v408);
          if ( SLOBYTE(v408.Flags) >= 0 )
          {
            TDebugOutputFunctor::operator()(
              a1,
              1306,
              "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - pOutputArguments->FrameAnalysisRec"
              "onstructedPicture.pReconstructedPicture MUST have the D3D12_RESOURCE_FLAG_VIDEO_ENCODE_REFERENCE_ONLY set "
              "when D3D12_VIDEO_ENCODER_SUPPORT_FLAG_READABLE_RECONSTRUCTED_PICTURE_LAYOUT_AVAILABLE is not supported.");
            v31 = 0;
          }
        }
        v217 = 0;
        for ( nn = v303; (unsigned int)v217 < *((_DWORD *)v303 + 50); nn = v303 )
        {
          v219 = *(_QWORD *)(*((_QWORD *)nn + 26) + 8 * v217);
          if ( v219 )
          {
            v220 = (CResource *)QIFrom<CResource>(v219);
            CResource::GetDesc(v220, &v408);
            if ( SLOBYTE(v408.Flags) >= 0 )
            {
              TDebugOutputFunctor::operator()(
                a1,
                1306,
                "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - pInputArguments->PictureControlD"
                "esc.FrameAnalysis.DownscaledReferences.ppTexture2Ds MUST ALL have the D3D12_RESOURCE_FLAG_VIDEO_ENCODE_R"
                "EFERENCE_ONLY set when D3D12_VIDEO_ENCODER_SUPPORT_FLAG_READABLE_RECONSTRUCTED_PICTURE_LAYOUT_AVAILABLE "
                "is not supported.");
              v31 = 0;
            }
          }
          v217 = (unsigned int)(v217 + 1);
        }
      }
      goto LABEL_639;
    }
    v204 = 0;
    while ( 2 )
    {
      if ( (unsigned int)v204 >= *((_DWORD *)v202 + 50) )
      {
        LOBYTE(v172) = v306;
        goto LABEL_630;
      }
      v205 = *(_QWORD *)(*((_QWORD *)v202 + 26) + 8 * v204);
      if ( v205 )
      {
        v206 = (struct CResource *)QIFrom<CResource>(v205);
        v315[0] = v206;
        v207 = *((_QWORD *)v303 + 27);
        if ( v207 )
          v319 = *(_DWORD *)(v207 + 4 * v204);
        else
          v319 = 0;
        CResource::GetDesc(v206, &v408);
        if ( v408.Dimension != D3D12_RESOURCE_DIMENSION_TEXTURE2D )
        {
          TDebugOutputFunctor::operator()(
            a1,
            1305,
            "The D3D12_VIDEO_ENCODER_FRAME_ANALYSIS::DownscaledReferences reference frame at index %d must have a resourc"
            "e dimension of D3D12_RESOURCE_DIMENSION_TEXTURE2D.",
            v204);
          v31 = 0;
        }
        if ( *((_BYTE *)v315[0] + 392) == 3 )
        {
          TDebugOutputFunctor::operator()(
            a1,
            1305,
            "The reference frame at index %d must not be a reserved resource.",
            (unsigned int)v204);
          goto LABEL_614;
        }
        if ( !IsVideoHeapTypeSupported(&v311, v315[0]) )
        {
          TDebugOutputFunctor::operator()(
            a1,
            1305,
            "The D3D12_VIDEO_ENCODER_FRAME_ANALYSIS::DownscaledReferences reference frame at index %d must have heap type"
            " D3D12_HEAP_TYPE_DEFAULT, D3D12_HEAP_TYPE_UPLOAD, D3D12_HEAP_TYPE_GPU_UPLOAD, or D3D12_HEAP_TYPE_CUSTOM. For"
            " D3D12_HEAP_TYPE_CUSTOM, CPUPageProperty must not be equal to D3D12_CPU_PAGE_PROPERTY_WRITE_BACK.See D3D12_F"
            "EATURE_VIDEO_ARCHITECTURE.",
            (unsigned int)v204);
LABEL_614:
          v31 = 0;
        }
        if ( v319 >= (*((_DWORD *)v315[0] + 61) & 0xFFFFFFu) )
        {
          TDebugOutputFunctor::operator()(
            a1,
            1305,
            "The subresource for D3D12_VIDEO_ENCODER_FRAME_ANALYSIS::DownscaledReferences reference frame at index %d exc"
            "eeds the number of subresources for the associated resource.",
            (unsigned int)v204);
          goto LABEL_621;
        }
        if ( *((_BYTE *)v315[0] + 247) != 1 )
        {
          TDebugOutputFunctor::operator()(
            a1,
            1305,
            "The subresource for D3D12_VIDEO_ENCODER_FRAME_ANALYSIS::DownscaledReferences reference frame at index %d has"
            " MipLevels != 1 which is not supported with EncodeFrame.",
            (unsigned int)v204);
          goto LABEL_621;
        }
        v209 = ResourceValidationInfo::ArraySize((struct CResource *)((char *)v315[0] + 224));
        v208 = v210 % v209;
        if ( v210 / v209 )
        {
          TDebugOutputFunctor::operator()(
            a1,
            1305,
            "The subresource for D3D12_VIDEO_ENCODER_FRAME_ANALYSIS::DownscaledReferences reference frame at index %d mus"
            "t specify PlaneSlice 0 of a planar resource for the chosen ArraySlice.",
            (unsigned int)v204);
LABEL_621:
          v31 = 0;
        }
        if ( v408.Format != v321 )
        {
          D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v321, v208);
          v212 = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetName(v408.Format, v211);
          TDebugOutputFunctor::operator()(
            a1,
            1305,
            "The D3D12_VIDEO_ENCODER_FRAME_ANALYSIS::DownscaledReferences reference frame at index %d has a format of %s "
            "that does not match the encoder which has a format of %s.",
            v204,
            v212,
            v213);
          v31 = 0;
        }
        v315[0] = (struct CResource *)*((unsigned int *)v303 + 12);
        LODWORD(v320[0]) = (*(__int64 (__fastcall **)(struct ID3D12VideoEncoderHeap1 *, __int64))(*(_QWORD *)v313 + 120LL))(
                             v313,
                             v208);
        v319 = *((_DWORD *)v303 + 13);
        v310 = (*(__int64 (__fastcall **)(struct ID3D12VideoEncoderHeap1 *))(*(_QWORD *)v313 + 120LL))(v313);
        if ( (*(unsigned int (__fastcall **)(struct ID3D12VideoEncoder *))(*(_QWORD *)v312 + 80LL))(v312) != 2 )
        {
          v214 = v319 >> v310;
          if ( (unsigned __int64)LODWORD(v315[0]) >> SLOBYTE(v320[0]) > v408.Width || v214 > v408.Height )
          {
            TDebugOutputFunctor::operator()(
              a1,
              1305,
              "The D3D12_VIDEO_ENCODER_FRAME_ANALYSIS::DownscaledReferences reference frame at index %d is smaller than t"
              "he current PictureTargetResolution divided by 2^Pow2DownscaleFactor.  DownscaledPictureTargetResolution.Wi"
              "dth: %d, DownscaledPictureTargetResolution.Height: %d, Resource Width: %I64u, Resource Height: %d",
              v204,
              (unsigned __int64)LODWORD(v315[0]) >> SLOBYTE(v320[0]),
              v214,
              v408.Width,
              v408.Height);
            v31 = 0;
          }
        }
      }
      v204 = (unsigned int)(v204 + 1);
      v202 = v303;
      continue;
    }
  }
LABEL_639:
  v221 = v313;
  if ( (*(unsigned int (__fastcall **)(struct ID3D12VideoEncoderHeap1 *))(*(_QWORD *)v313 + 120LL))(v313)
    && ((*(__int64 (__fastcall **)(struct ID3D12VideoEncoderHeap1 *))(*(_QWORD *)v221 + 72LL))(v221) & 8) != 0
    && (*((_BYTE *)v303 + 20) & 2) == 0
    && (_BYTE)v172
    && (v309[0] & 0x10) == 0 )
  {
    v31 = 0;
    TDebugOutputFunctor::operator()(
      a1,
      1306,
      "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - The associated encoder heap has D3D12_VIDE"
      "O_ENCODER_HEAP_FLAG_ALLOW_RATE_CONTROL_FRAME_ANALYSIS and Pow2DownscaleFactor > 0,  and this EncodeFrame command d"
      "oes NOT enable D3D12_VIDEO_ENCODER_RATE_CONTROL_FLAG_ENABLE_FRAME_ANALYSIS. However the driver does NOT support D3"
      "D12_VIDEO_ENCODER_RATE_CONTROL_FRAME_ANALYSIS_SUPPORT_FLAG_DYNAMIC_1ST_PASS_SKIP to disable two pass dynamically i"
      "n given frames. When this flag is not supported and the heap allows it, two pass must always be enabled for all frames");
  }
  v315[0] = (struct CResource *)(unsigned int)(int)o_ceil_0();
  v222 = (unsigned __int64)v315[0] * (unsigned int)(int)o_ceil_0();
  ThrowFailure(v222 > 0xFFFFFFFF ? 0x80070216 : 0);
  v223 = 0;
  v224 = *((_DWORD *)v303 + 14);
  if ( !v224 )
  {
    v223 = 1;
    goto LABEL_653;
  }
  v225 = v224 - 1;
  if ( !v225 )
    goto LABEL_712;
  v226 = v225 - 1;
  if ( !v226 )
  {
    v256 = (unsigned int)(int)o_ceil_0();
    v223 = (unsigned int)v256;
    v255 = v308;
    if ( (unsigned int)v256 <= v308 )
      goto LABEL_653;
    v257 = "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - Subregions number inferred (%d) for f"
           "rame subregions mode . D3D12_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_MODE_SQUARE_UNITS_PER_SUBREGION_ROW_UNALIGN"
           "ED exceeds the maximum supported number of subregions %d";
    goto LABEL_707;
  }
  v227 = v226 - 1;
  if ( !v227 )
  {
    v256 = (unsigned int)(int)o_ceil_0();
    v223 = (unsigned int)v256;
    v255 = v308;
    if ( (unsigned int)v256 <= v308 )
      goto LABEL_653;
    v257 = "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - Subregions number inferred (%d) for f"
           "rame subregions mode . D3D12_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_MODE_UNIFORM_PARTITIONING_ROWS_PER_SUBREGIO"
           "N exceeds the maximum supported number of subregions %d";
    goto LABEL_707;
  }
  v228 = v227 - 1;
  if ( !v228 )
  {
    v223 = **((unsigned int **)v303 + 9);
    v255 = v308;
    if ( (unsigned int)v223 <= v308 )
      goto LABEL_653;
    v256 = (unsigned int)v223;
    v257 = "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - Subregions number specified (%d) for "
           "frame subregions mode . D3D12_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_MODE_UNIFORM_PARTITIONING_SUBREGIONS_PER_F"
           "RAME exceeds the maximum supported number of subregions %d";
LABEL_707:
    v31 = 0;
    LODWORD(v296) = v255;
    TDebugOutputFunctor::operator()(a1, 1306, v257, v256, v296);
    goto LABEL_653;
  }
  v229 = v228 - 1;
  if ( v229 )
  {
    v230 = v229 - 1;
    if ( v230 )
    {
      if ( v230 != 1 )
      {
LABEL_653:
        v231 = v322;
        if ( *(_DWORD *)v322 == 1 )
        {
          v232 = *((unsigned int *)v322 + 3);
          if ( v232 < v223 )
          {
            v31 = 0;
            TDebugOutputFunctor::operator()(
              a1,
              1306,
              "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - SubregionOutputBuffers.ExpectedSub"
              "regionCount (%d). is less than the expected number of slices for this frame %d. Please increase ExpectedSubregionCount.",
              v232,
              v223);
          }
          for ( i1 = 0; (unsigned int)i1 < *((_DWORD *)v231 + 3); i1 = (unsigned int)(i1 + 1) )
          {
            v234 = (CResource *)QIFrom<CResource>(*(_QWORD *)(*((_QWORD *)v231 + 5) + 8 * i1));
            CResource::GetDesc(v234, &v408);
            if ( v408.Dimension != D3D12_RESOURCE_DIMENSION_BUFFER )
            {
              TDebugOutputFunctor::operator()(
                a1,
                1305,
                "The resource in SubregionOutputBuffers.ppSubregionOffsets[%d] must be a buffer.",
                i1);
              v31 = 0;
            }
            if ( *((_BYTE *)v234 + 392) == 3 )
            {
              TDebugOutputFunctor::operator()(
                a1,
                1305,
                "The resource in SubregionOutputBuffers.ppSubregionOffsets[%d] must not be a reserved resource.",
                (unsigned int)i1);
            }
            else
            {
              if ( IsVideoHeapTypeSupported(&v311, v234) )
                goto LABEL_717;
              TDebugOutputFunctor::operator()(
                a1,
                1305,
                "The resource in SubregionOutputBuffers.ppSubregionOffsets[%d] must have heap type D3D12_HEAP_TYPE_DEFAUL"
                "T, D3D12_HEAP_TYPE_UPLOAD, D3D12_HEAP_TYPE_GPU_UPLOAD, or D3D12_HEAP_TYPE_CUSTOM. For D3D12_HEAP_TYPE_CU"
                "STOM, CPUPageProperty must not be equal to D3D12_CPU_PAGE_PROPERTY_WRITE_BACK.See D3D12_FEATURE_VIDEO_ARCHITECTURE.",
                (unsigned int)i1);
            }
            v31 = 0;
LABEL_717:
            v258 = (CResource *)QIFrom<CResource>(*(_QWORD *)(*((_QWORD *)v322 + 4) + 8 * i1));
            CResource::GetDesc(v258, &v431);
            if ( v431.Dimension != D3D12_RESOURCE_DIMENSION_BUFFER )
            {
              TDebugOutputFunctor::operator()(
                a1,
                1305,
                "The resource in SubregionOutputBuffers.ppSubregionSizes[%d] must be a buffer.",
                i1);
              v31 = 0;
            }
            if ( *((_BYTE *)v258 + 392) == 3 )
            {
              TDebugOutputFunctor::operator()(
                a1,
                1305,
                "The resource in SubregionOutputBuffers.ppSubregionSizes[%d] must not be a reserved resource.",
                (unsigned int)i1);
LABEL_723:
              v31 = 0;
              goto LABEL_724;
            }
            if ( !IsVideoHeapTypeSupported(&v311, v258) )
            {
              TDebugOutputFunctor::operator()(
                a1,
                1305,
                "The resource in SubregionOutputBuffers.ppSubregionSizes[%d] must have heap type D3D12_HEAP_TYPE_DEFAULT,"
                " D3D12_HEAP_TYPE_UPLOAD, D3D12_HEAP_TYPE_GPU_UPLOAD, or D3D12_HEAP_TYPE_CUSTOM. For D3D12_HEAP_TYPE_CUST"
                "OM, CPUPageProperty must not be equal to D3D12_CPU_PAGE_PROPERTY_WRITE_BACK.See D3D12_FEATURE_VIDEO_ARCHITECTURE.",
                (unsigned int)i1);
              goto LABEL_723;
            }
LABEL_724:
            v231 = v322;
            v259 = *(int (__fastcall ****)(_QWORD, GUID *, struct CResource **))(*((_QWORD *)v322 + 6) + 8 * i1);
            if ( v259 && (v315[0] = 0, (**v259)(v259, &GUID_ffffffff_335a_4bc5_9de9_43d8fb7777ae, v315) >= 0) )
            {
              (*(void (__fastcall **)(struct CResource *))(*(_QWORD *)v315[0] + 16LL))(v315[0]);
              v260 = v315[0];
            }
            else
            {
              v260 = 0;
            }
            v261 = *((_DWORD *)v260 + 56);
            if ( v261 )
            {
              if ( v261 != 1 )
              {
                v262 = "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - SubregionOutputBuffers.pp"
                       "SubregionFences[%d] must be either monitored fences with GPU access or native fences.";
                goto LABEL_733;
              }
            }
            else if ( (CFence::GetCreationFlags(v260) & 1) != 0 )
            {
              v262 = "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - SubregionOutputBuffers.ppSu"
                     "bregionFences[%d] cannot have D3D12_FENCE_FLAG_SHARED set when driver uses monitored fences.";
LABEL_733:
              v31 = 0;
              TDebugOutputFunctor::operator()(a1, 1306, v262, (unsigned int)i1);
            }
          }
        }
        v263 = v303;
        if ( (*(_BYTE *)v303 & 8) != 0 )
        {
          v264 = *((_DWORD *)v303 + 2);
          if ( v264 > (unsigned int)v318 )
          {
            v31 = 0;
            TDebugOutputFunctor::operator()(
              a1,
              1306,
              "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - Intra refresh duration specified ("
              "%d). exceeds the maximum supported number of intra refresh frames duration %d",
              v264,
              (_DWORD)v318);
          }
          v265 = *((_DWORD *)v263 + 24);
          if ( v265 >= v264 )
          {
            v31 = 0;
            TDebugOutputFunctor::operator()(
              a1,
              1306,
              "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - Intra refresh index specified (%d)"
              ". exceeds the intra refresh frames duration specified %d. IR index range is [0..IntraRefreshDuration)",
              v265,
              v264);
          }
        }
        if ( *((_DWORD *)v263 + 4) && (*((_BYTE *)v263 + 20) & 1) == 0 )
          goto LABEL_762;
        if ( (*((_BYTE *)v263 + 100) & 2) != 0 )
        {
          v266 = (*(__int64 (__fastcall **)(struct ID3D12VideoEncoder *))(*(_QWORD *)v312 + 64LL))(v312);
          if ( !v266 )
            v266 = 1;
          v310 = 0;
          _BitScanForward(&v267, v266);
          if ( !(unsigned int)ValidateEncodeFrameQuantizationMatrix(
                                (const struct D3D12_VIDEO_ENCODER_ENCODEFRAME_INPUT_ARGUMENTS1 *)((char *)v263 + 176),
                                v323,
                                v267,
                                (const struct D3D12_VIDEO_ENCODER_INPUT_MAP_SESSION_INFO *)v354,
                                &v311,
                                a1) )
            v31 = 0;
          goto LABEL_762;
        }
        v268 = (*(__int64 (__fastcall **)(struct ID3D12VideoEncoderHeap1 *))(*(_QWORD *)v313 + 80LL))(v313);
        if ( v268 )
        {
          v269 = v268 - 1;
          if ( v269 )
          {
            if ( v269 == 1 )
            {
              v270 = *((_QWORD *)v263 + 14);
              if ( v270 )
              {
                v271 = *(_QWORD *)(v270 + 1160);
                v272 = *(_DWORD *)(v270 + 1152);
                goto LABEL_756;
              }
            }
LABEL_775:
            v31 = 0;
            TDebugOutputFunctor::operator()(
              a1,
              1305,
              "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not valid - Rate control modes that use a CPU buff"
              "er QP map, require a non-null QP Map passed in D3D12_VIDEO_ENCODER_PICTURE_CONTROL_CODEC_DATA_<Codec>.pRateControlQPMap");
LABEL_762:
            memset_0(v366, 0, 0x70u);
            v278 = (*(__int64 (__fastcall **)(struct ID3D12VideoEncoder *))(*(_QWORD *)v312 + 64LL))(v312);
            if ( !v278 )
              v278 = 1;
            v310 = 0;
            _BitScanForward(&v278, v278);
            v366[0] = v278;
            v279 = v313;
            v366[1] = (*(__int64 (__fastcall **)(struct ID3D12VideoEncoderHeap1 *))(*(_QWORD *)v313 + 80LL))(v313);
            v366[2] = v325;
            v366[3] = v66;
            v367 = *((_QWORD *)&v325 + 1);
            v368 = (*(__int64 (__fastcall **)(struct ID3D12VideoEncoder *))(*(_QWORD *)v312 + 104LL))(v312);
            v369 = *((_QWORD *)v263 + 6);
            v374 = *((_DWORD *)v263 + 60);
            v375 = v326;
            v376 = v161;
            v377 = *((_QWORD *)&v326 + 1);
            if ( (*(int (__fastcall **)(_QWORD, __int64, _DWORD *, __int64))(**((_QWORD **)v323 + 85) + 24LL))(
                   *((_QWORD *)v323 + 85),
                   48,
                   v366,
                   112) >= 0
              && v370 )
            {
              v280 = v322;
              v281 = (CResource *)QIFrom<CResource>(*((_QWORD *)v322 + 10));
              CResource::GetDesc(v281, &v408);
              if ( v408.Width < v373 )
                TDebugOutputFunctor::operator()(
                  a1,
                  1306,
                  "ID3D12VideoEncodeCommandList::EncodeFrame arguments warning - Output buffer size for EncoderOutputMeta"
                  "data.pBuffer is less than advised in encoder caps. Current buffer size: %d Maximum size reported %d",
                  LODWORD(v408.Width),
                  v373);
              v282 = *((_QWORD *)v280 + 11);
              if ( v282 % v372 )
              {
                v31 = 0;
                TDebugOutputFunctor::operator()(
                  a1,
                  1306,
                  "ID3D12VideoEncodeCommandList::EncodeFrame arguments warning - Buffer offset alignment for EncoderOutpu"
                  "tMetadata.pBuffer specified in OutputArguments.EncoderOutputMetadata.Offset is different than advised "
                  "in encoder caps. Current buffer offset: %d Required alignment reported: %d",
                  v282,
                  v372);
              }
              if ( *(_DWORD *)v280 )
              {
                for ( i2 = 0; i2 < *((_DWORD *)v280 + 3); ++i2 )
                {
                  v286 = (CResource *)QIFrom<CResource>(*(_QWORD *)(*((_QWORD *)v280 + 3) + 8LL * i2));
                  CResource::GetDesc(v286, &v408);
                  v287 = *(_QWORD *)(*((_QWORD *)v280 + 2) + 8LL * i2);
                  if ( v287 >= v408.Width )
                  {
                    TDebugOutputFunctor::operator()(
                      a1,
                      1305,
                      "The D3D12_VIDEO_ENCODER_SUBREGION_COMPRESSED_BITSTREAM::pSubregionBitstreamsBaseOffsets[%d] = %d e"
                      "xceeds the size of the buffer specified D3D12_VIDEO_ENCODER_SUBREGION_COMPRESSED_BITSTREAM::ppSubr"
                      "egionBitstreams[%d].",
                      v287,
                      i2,
                      LODWORD(v408.Width));
                    v31 = 0;
                  }
                  v288 = *(_QWORD *)(*((_QWORD *)v280 + 2) + 8LL * i2);
                  if ( v288 % v371 )
                  {
                    v31 = 0;
                    TDebugOutputFunctor::operator()(
                      a1,
                      1306,
                      "The D3D12_VIDEO_ENCODER_SUBREGION_COMPRESSED_BITSTREAM::pSubregionBitstreamsBaseOffsets[%d] = %d i"
                      "s not aligned with D3D12_FEATURE_DATA_VIDEO_ENCODER_RESOURCE_REQUIREMENTS.CompressedBitstreamBuffe"
                      "rAccessAlignment (%d) Current buffer offset: %d Required alignment reported: %d",
                      i2,
                      v288,
                      v371,
                      v298,
                      *(_DWORD *)v299);
                  }
                }
              }
              else
              {
                v283 = (CResource *)QIFrom<CResource>(*((_QWORD *)v280 + 1));
                CResource::GetDesc(v283, &v408);
                if ( *((_QWORD *)v280 + 2) >= v408.Width )
                {
                  TDebugOutputFunctor::operator()(
                    a1,
                    1305,
                    "The D3D12_VIDEO_ENCODER_COMPRESSED_BITSTREAM::FrameStartOffset exceeds the size of the buffer specif"
                    "ied D3D12_VIDEO_ENCODER_COMPRESSED_BITSTREAM::pBuffer.");
                  v31 = 0;
                }
                v284 = *((_QWORD *)v280 + 2);
                if ( v284 % v371 )
                {
                  v31 = 0;
                  TDebugOutputFunctor::operator()(
                    a1,
                    1306,
                    "ID3D12VideoEncodeCommandList::EncodeFrame arguments warning - Buffer offset access alignment for Bit"
                    "stream.pBuffer specified in Bitstream.FrameStartOffset is different than advised in encoder caps. Cu"
                    "rrent buffer offset: %d Required alignment reported: %d",
                    v284,
                    v371);
                }
              }
              if ( (*((_BYTE *)v263 + 100) & 4) != 0 )
              {
                if ( ((*(__int64 (__fastcall **)(struct ID3D12VideoEncoderHeap1 *))(*(_QWORD *)v279 + 72LL))(v279) & 4) == 0 )
                {
                  v31 = 0;
                  TDebugOutputFunctor::operator()(
                    a1,
                    1306,
                    "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - D3D12_VIDEO_ENCODER_PICTURE_"
                    "CONTROL_FLAG_ENABLE_DIRTY_REGIONS_INPUT was requested but D3D12_VIDEO_ENCODER_HEAP_FLAG_ALLOW_DIRTY_"
                    "REGIONS is not set in the encoder heap.");
                }
                v289 = v312;
                v290 = (*(__int64 (__fastcall **)(struct ID3D12VideoEncoder *))(*(_QWORD *)v312 + 64LL))(v312);
                if ( !v290 )
                  v290 = 1;
                _BitScanForward(&v291, v290);
                v292 = v307;
                v293 = v323;
                v31 = (unsigned int)ValidateEncodeFrameDirtyRegions(
                                      (const struct D3D12_VIDEO_ENCODER_ENCODEFRAME_INPUT_ARGUMENTS1 *)((char *)v263 + 160),
                                      v323,
                                      v291,
                                      (const struct D3D12_VIDEO_ENCODER_INPUT_MAP_SESSION_INFO *)v354,
                                      &v311,
                                      a1,
                                      (const struct D3D12_VIDEO_ENCODER_ENCODEFRAME_INPUT_ARGUMENTS1 *)((char *)v263 + 48),
                                      v307) != 0
                    ? v31
                    : 0;
              }
              else
              {
                v292 = v307;
                v289 = v312;
                v293 = v323;
              }
              if ( (*((_BYTE *)v263 + 100) & 8) != 0 )
              {
                v294 = (*(__int64 (__fastcall **)(struct ID3D12VideoEncoder *))(*(_QWORD *)v289 + 64LL))(v289);
                if ( !v294 )
                  v294 = 1;
                v310 = 0;
                _BitScanForward(&v295, v294);
                v31 = (unsigned int)ValidateEncodeFrameMotionVectors(
                                      (const struct D3D12_VIDEO_ENCODER_ENCODEFRAME_INPUT_ARGUMENTS1 *)((char *)v263 + 144),
                                      v293,
                                      v295,
                                      (const struct D3D12_VIDEO_ENCODER_INPUT_MAP_SESSION_INFO *)v354,
                                      &v311,
                                      a1,
                                      (const struct D3D12_VIDEO_ENCODER_ENCODEFRAME_INPUT_ARGUMENTS1 *)((char *)v263 + 48),
                                      v305,
                                      v292) != 0
                    ? v31
                    : 0;
              }
              if ( (_QWORD)v330 )
              {
                std::_Deallocate<16>(v330, 8 * ((v331 - (__int64)v330) >> 3));
                v330 = 0;
                v331 = 0;
              }
              if ( (_QWORD)v334 )
                std::_Deallocate<16>(v334, (v335 - v334) & 0xFFFFFFFFFFFFFFF8uLL);
              return v31 == 0 ? 0x80070057 : 0;
            }
            else
            {
              TDebugOutputFunctor::operator()(
                a1,
                1306,
                "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - CheckFeatureSupport(D3D12_FEATUR"
                "E_VIDEO_ENCODER_RESOURCE_REQUIREMENTS1,...) for the given input returned failure or not supported.");
              if ( (_QWORD)v330 )
              {
                std::_Deallocate<16>(v330, 8 * ((v331 - (__int64)v330) >> 3));
                v330 = 0;
                v331 = 0;
              }
              if ( (_QWORD)v334 )
                std::_Deallocate<16>(v334, (v335 - v334) & 0xFFFFFFFFFFFFFFF8uLL);
              return 2147942487LL;
            }
          }
          v273 = *((_QWORD *)v263 + 14);
          if ( !v273 )
            goto LABEL_775;
          v271 = *(_QWORD *)(v273 + 104);
          v272 = *(_DWORD *)(v273 + 96);
        }
        else
        {
          v274 = *((_QWORD *)v263 + 14);
          if ( !v274 )
            goto LABEL_775;
          v271 = *(_QWORD *)(v274 + 128);
          v272 = *(_DWORD *)(v274 + 120);
        }
LABEL_756:
        if ( v271 )
        {
          v275 = (unsigned int)(int)o_ceil_0();
          v276 = (unsigned int)(int)o_ceil_0() * v275;
          v277 = v276;
          if ( v276 > 0xFFFFFFFF )
            v277 = -1;
          ThrowFailure(v276 > 0xFFFFFFFF ? 0x80070216 : 0);
          if ( v272 != v277 )
          {
            v31 = 0;
            TDebugOutputFunctor::operator()(
              a1,
              1306,
              "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - The QP Map passed in passed in D3D"
              "12_VIDEO_ENCODER_PICTURE_CONTROL_CODEC_DATA_<Codec>.pRateControlQPMap must have a size of ceil(FramePixelW"
              "idth/QPMapRegionPixelsSize) * ceil(FramePixelHeight/QPMapRegionPixelsSize)) where the QPMapRegionPixelsSiz"
              "e is reported in the support queries or the current resolution being used.");
          }
          v263 = v303;
          goto LABEL_762;
        }
        goto LABEL_775;
      }
LABEL_712:
      v223 = v308;
      goto LABEL_653;
    }
  }
  if ( (*(unsigned int (__fastcall **)(struct ID3D12VideoEncoderHeap1 *))(*(_QWORD *)v313 + 80LL))(v313) != 2 )
  {
    v31 = 0;
    TDebugOutputFunctor::operator()(
      a1,
      1306,
      "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - Subregion tile partition is only available for AV1 codec.");
    goto LABEL_653;
  }
  v315[0] = 0;
  v235 = v303;
  v236 = ULongLongMult(**((_QWORD **)v303 + 9), *(_QWORD *)(*((_QWORD *)v303 + 9) + 8LL), (unsigned __int64 *)v315);
  ThrowFailure(v236);
  v223 = (unsigned __int64)v315[0];
  if ( v315[0] > (struct CResource *)v308 )
  {
    v31 = 0;
    TDebugOutputFunctor::operator()(
      a1,
      1306,
      "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - Subregions number specified (%d) for frame"
      " subregions mode %d. exceeds the maximum supported number of subregions %d",
      LODWORD(v315[0]),
      *((_DWORD *)v235 + 14),
      v308);
  }
  memset_0(&v421, 0, 0x448u);
  memset_0(&v408, 0, 0x50u);
  v237 = (*(__int64 (__fastcall **)(struct ID3D12VideoEncoder *))(*(_QWORD *)v312 + 64LL))(v312);
  if ( !v237 )
    v237 = 1;
  v310 = 0;
  _BitScanForward((unsigned int *)&v237, v237);
  v408.Dimension = v237;
  *((_DWORD *)&v408.Dimension + 1) = (*(__int64 (__fastcall **)(struct ID3D12VideoEncoderHeap1 *))(*(_QWORD *)v313 + 80LL))(v313);
  v408.Alignment = __PAIR64__(v66, v325);
  v408.Width = *((_QWORD *)&v325 + 1);
  v408.Height = v329;
  *(_DWORD *)&v408.DepthOrArraySize = v162;
  *(_QWORD *)&v408.Format = *((_QWORD *)&v329 + 1);
  v408.SampleDesc.Quality = *((_DWORD *)v235 + 14);
  *(_QWORD *)&v408.Layout = *((_QWORD *)v235 + 6);
  LODWORD(v409) = 1096;
  v410 = &v421;
  v421 = **((_BYTE **)&v326 + 1) & 1;
  v238 = (_OWORD *)*((_QWORD *)v235 + 9);
  v239 = &v422;
  v240 = 8;
  do
  {
    *(_OWORD *)v239 = *v238;
    *((_OWORD *)v239 + 1) = v238[1];
    *((_OWORD *)v239 + 2) = v238[2];
    *((_OWORD *)v239 + 3) = v238[3];
    *((_OWORD *)v239 + 4) = v238[4];
    *((_OWORD *)v239 + 5) = v238[5];
    *((_OWORD *)v239 + 6) = v238[6];
    *((_OWORD *)v239 + 7) = v238[7];
    v239 += 128;
    v238 += 8;
    --v240;
  }
  while ( v240 );
  *(_OWORD *)v239 = *v238;
  *((_QWORD *)v239 + 2) = *((_QWORD *)v238 + 2);
  if ( (*(int (__fastcall **)(_QWORD, __int64, struct D3D12_RESOURCE_DESC *))(**((_QWORD **)v323 + 85) + 24LL))(
         *((_QWORD *)v323 + 85),
         46,
         &v408) >= 0
    && v411 )
  {
    v241 = *(_QWORD *)(*((_QWORD *)v235 + 9) + 8LL);
    if ( v241 < v425 )
    {
      v242 = v426;
    }
    else
    {
      v242 = v426;
      if ( v241 <= v426 )
        goto LABEL_676;
    }
    v31 = 0;
    TDebugOutputFunctor::operator()(
      a1,
      1306,
      "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - ColCount number specified (%d) for frame s"
      "ubregions mode %d. out of minimum %d or maximum %d supported bounds",
      v241,
      *((_DWORD *)v235 + 14),
      v425,
      v242);
LABEL_676:
    v243 = (unsigned __int64 *)*((_QWORD *)v235 + 9);
    v244 = *v243;
    if ( *v243 < v423 )
    {
      v245 = v424;
    }
    else
    {
      v245 = v424;
      if ( v244 <= v424 )
      {
        if ( !v31 || *((_DWORD *)v235 + 14) != 6 )
          goto LABEL_653;
        v246 = 0;
LABEL_681:
        v247 = *((_QWORD *)v235 + 9);
        v248 = 64;
        if ( *(_QWORD *)(v247 + 8) < 0x40u )
          v248 = *(_QWORD *)(v247 + 8);
        if ( v246 >= v248 )
          goto LABEL_653;
        v249 = *(_QWORD *)(v247 + 8 * v246 + 528);
        if ( v249 < v427 || v249 > v428 )
        {
          v31 = 0;
          TDebugOutputFunctor::operator()(
            a1,
            1306,
            "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - ColWidths[%d] number specified (%d) "
            "for frame subregions mode . D3D12_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_MODE_CONFIGURABLE_GRID_PARTITION out "
            "of minimum %d or maximum %d supported bounds",
            v246,
            v249,
            v427,
            v428);
        }
        for ( i3 = 0; ; ++i3 )
        {
          v251 = (unsigned __int64 *)*((_QWORD *)v303 + 9);
          v252 = 64;
          if ( *v251 < 0x40 )
            v252 = *v251;
          if ( i3 >= v252 )
          {
            ++v246;
            v235 = v303;
            goto LABEL_681;
          }
          v315[0] = 0;
          v253 = ULongLongMult(v251[v246 + 66], v251[i3 + 2], (unsigned __int64 *)v315);
          ThrowFailure(v253);
          if ( v315[0] < (struct CResource *)v429 )
          {
            v254 = v430;
          }
          else
          {
            v254 = v430;
            if ( v315[0] <= (struct CResource *)v430 )
              continue;
          }
          v31 = 0;
          TDebugOutputFunctor::operator()(
            a1,
            1306,
            "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - ColWidths[%d] = %d RowHeights[%d] = "
            "%d for frame subregions mode . D3D12_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_MODE_CONFIGURABLE_GRID_PARTITION o"
            "ut of %d or maximum %d supported bounds for tile area",
            v246,
            *(_QWORD *)(*((_QWORD *)v303 + 9) + 8 * v246 + 528),
            i3,
            *(_QWORD *)(*((_QWORD *)v303 + 9) + 8 * i3 + 16),
            v429,
            v254);
        }
      }
    }
    v31 = 0;
    TDebugOutputFunctor::operator()(
      a1,
      1306,
      "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - RowCount number specified (%d) for frame s"
      "ubregions mode %d. out of minimum %d or maximum %d supported bounds",
      v244,
      *((_DWORD *)v235 + 14),
      v423,
      v245);
    goto LABEL_653;
  }
  TDebugOutputFunctor::operator()(
    a1,
    1306,
    "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not supported - CheckFeatureSupport(D3D12_FEATURE_VIDEO_ENCO"
    "DER_FRAME_SUBREGION_LAYOUT_CONFIG,...) for the given input returned failure.");
  if ( (_QWORD)v330 )
  {
    std::_Deallocate<16>(v330, 8 * ((v331 - (__int64)v330) >> 3));
    v330 = 0;
    v331 = 0;
  }
  if ( (_QWORD)v334 )
    std::_Deallocate<16>(v334, (v335 - v334) & 0xFFFFFFFFFFFFFFF8uLL);
  return 2147942487LL;
}

```

## disassembly

```asm
0x1802404b4  mov     rax, rsp
0x1802404b7  push    rbx
0x1802404b8  push    rsi
0x1802404b9  push    rdi
0x1802404ba  push    r12
0x1802404bc  push    r13
0x1802404be  push    r14
0x1802404c0  push    r15
0x1802404c2  sub     rsp, 930h
0x1802404c9  movaps  xmmword ptr [rax-48h], xmm6
0x1802404cd  mov     rax, cs:__security_cookie
0x1802404d4  xor     rax, rsp
0x1802404d7  mov     [rsp+968h+var_58], rax
0x1802404df  mov     rax, r9
0x1802404e2  mov     [rsp+968h+var_8E8], rax
0x1802404ea  mov     [rsp+968h+var_8D8], r8d
0x1802404f2  mov     r11, rdx
0x1802404f5  mov     [rsp+968h+var_888], rdx
0x1802404fd  mov     r14, rcx
0x180240500  mov     r13, [rsp+968h+arg_30]
0x180240508  mov     [rsp+968h+var_890], r13
0x180240510  mov     rsi, [rsp+968h+arg_28]
0x180240518  mov     [rsp+968h+var_910], rsi
0x18024051d  mov     rbx, [rsp+968h+arg_20]
0x180240525  mov     [rsp+968h+var_8E0], rbx
0x18024052d  xor     r12d, r12d
0x180240530  test    rax, rax
0x180240533  jnz     short loc_180240550
0x180240535  lea     r8, aId3d12videoenc_108; "ID3D12VideoEncodeCommandList::EncodeFra"...
0x18024053c  mov     edx, 519h
0x180240541  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180240546  mov     eax, 80070057h
0x18024054b  jmp     loc_18024487F
0x180240550  test    rbx, rbx
0x180240553  jnz     short loc_180240570
0x180240555  lea     r8, aId3d12videoenc_28; "ID3D12VideoEncodeCommandList::EncodeFra"...
0x18024055c  mov     edx, 519h
0x180240561  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180240566  mov     eax, 80070057h
0x18024056b  jmp     loc_18024487F
0x180240570  test    rsi, rsi
0x180240573  jnz     short loc_180240590
0x180240575  lea     r8, aId3d12videoenc_137; "ID3D12VideoEncodeCommandList::EncodeFra"...
0x18024057c  mov     edx, 519h
0x180240581  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180240586  mov     eax, 80070057h
0x18024058b  jmp     loc_18024487F
0x180240590  test    r13, r13
0x180240593  jnz     short loc_1802405B0
0x180240595  lea     r8, aId3d12videoenc_129; "ID3D12VideoEncodeCommandList::EncodeFra"...
0x18024059c  mov     edx, 519h
0x1802405a1  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1802405a6  mov     eax, 80070057h
0x1802405ab  jmp     loc_18024487F
0x1802405b0  cmp     [rsi+0E0h], r12
0x1802405b7  jnz     short loc_1802405D4
0x1802405b9  lea     r8, aId3d12videoenc_145; "ID3D12VideoEncodeCommandList::EncodeFra"...
0x1802405c0  mov     edx, 519h
0x1802405c5  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1802405ca  mov     eax, 80070057h
0x1802405cf  jmp     loc_18024487F
0x1802405d4  cmp     [r13+50h], r12
0x1802405d8  jnz     short loc_1802405F5
0x1802405da  lea     r8, aId3d12videoenc_13; "ID3D12VideoEncodeCommandList::EncodeFra"...
0x1802405e1  mov     edx, 519h
0x1802405e6  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1802405eb  mov     eax, 80070057h
0x1802405f0  jmp     loc_18024487F
0x1802405f5  cmp     [r13+0], r12d
0x1802405f9  jnz     short loc_180240627
0x1802405fb  cmp     [r13+8], r12
0x1802405ff  jnz     short loc_18024061C
0x180240601  lea     r8, aId3d12videoenc_7; "ID3D12VideoEncodeCommandList::EncodeFra"...
0x180240608  mov     edx, 519h
0x18024060d  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180240612  mov     eax, 80070057h
0x180240617  jmp     loc_18024487F
0x18024061c  mov     r15d, 1
0x180240622  jmp     loc_1802407D1
0x180240627  mov     r15d, 1
0x18024062d  cmp     [r13+0], r15d
0x180240631  jnz     loc_180244860
0x180240637  cmp     [r13+10h], r12
0x18024063b  jnz     short loc_180240658
0x18024063d  lea     r8, aId3d12videoenc_47; "ID3D12VideoEncodeCommandList::EncodeFra"...
0x180240644  mov     edx, 519h
0x180240649  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18024064e  mov     eax, 80070057h
0x180240653  jmp     loc_18024487F
0x180240658  mov     r10, [r13+18h]
0x18024065c  test    r10, r10
0x18024065f  jnz     short loc_18024067C
0x180240661  lea     r8, aId3d12videoenc_146; "ID3D12VideoEncodeCommandList::EncodeFra"...
0x180240668  mov     edx, 519h
0x18024066d  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180240672  mov     eax, 80070057h
0x180240677  jmp     loc_18024487F
0x18024067c  mov     r9, [r13+20h]
0x180240680  test    r9, r9
0x180240683  jnz     short loc_1802406A0
0x180240685  lea     r8, aId3d12videoenc_30; "ID3D12VideoEncodeCommandList::EncodeFra"...
0x18024068c  mov     edx, 519h
0x180240691  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180240696  mov     eax, 80070057h
0x18024069b  jmp     loc_18024487F
0x1802406a0  mov     r8, [r13+28h]
0x1802406a4  test    r8, r8
0x1802406a7  jnz     short loc_1802406C4
0x1802406a9  lea     r8, aId3d12videoenc_112; "ID3D12VideoEncodeCommandList::EncodeFra"...
0x1802406b0  mov     edx, 519h
0x1802406b5  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1802406ba  mov     eax, 80070057h
0x1802406bf  jmp     loc_18024487F
0x1802406c4  mov     rdx, [r13+30h]
0x1802406c8  test    rdx, rdx
0x1802406cb  jnz     short loc_1802406E8
0x1802406cd  lea     r8, aId3d12videoenc_111; "ID3D12VideoEncodeCommandList::EncodeFra"...
0x1802406d4  mov     edx, 519h
0x1802406d9  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1802406de  mov     eax, 80070057h
0x1802406e3  jmp     loc_18024487F
0x1802406e8  cmp     [r13+38h], r12
0x1802406ec  jnz     short loc_180240709
0x1802406ee  lea     r8, aId3d12videoenc_139; "ID3D12VideoEncodeCommandList::EncodeFra"...
0x1802406f5  mov     edx, 519h
0x1802406fa  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1802406ff  mov     eax, 80070057h
0x180240704  jmp     loc_18024487F
0x180240709  mov     eax, r12d
0x18024070c  cmp     eax, [r13+0Ch]
0x180240710  jnb     loc_1802407BC
0x180240716  mov     ecx, eax
0x180240718  cmp     [r10+rcx*8], r12
0x18024071c  jnz     short loc_18024073F
0x18024071e  mov     r9d, eax
0x180240721  lea     r8, aId3d12videoenc_127; "ID3D12VideoEncodeCommandList::EncodeFra"...
0x180240728  mov     edx, 519h
0x18024072d  mov     rcx, r14
0x180240730  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180240735  mov     eax, 80070057h
0x18024073a  jmp     loc_18024487F
0x18024073f  cmp     [r9+rcx*8], r12
0x180240743  jnz     short loc_180240766
0x180240745  mov     r9d, eax
0x180240748  lea     r8, aId3d12videoenc_72; "ID3D12VideoEncodeCommandList::EncodeFra"...
0x18024074f  mov     edx, 519h
0x180240754  mov     rcx, r14
0x180240757  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18024075c  mov     eax, 80070057h
0x180240761  jmp     loc_18024487F
0x180240766  cmp     [r8+rcx*8], r12
0x18024076a  jnz     short loc_18024078D
0x18024076c  mov     r9d, eax
0x18024076f  lea     r8, aId3d12videoenc_134; "ID3D12VideoEncodeCommandList::EncodeFra"...
0x180240776  mov     edx, 519h
0x18024077b  mov     rcx, r14
0x18024077e  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180240783  mov     eax, 80070057h
0x180240788  jmp     loc_18024487F
0x18024078d  cmp     [rdx+rcx*8], r12
0x180240791  jnz     short loc_1802407B4
0x180240793  mov     r9d, eax
0x180240796  lea     r8, aId3d12videoenc_143; "ID3D12VideoEncodeCommandList::EncodeFra"...
0x18024079d  mov     edx, 519h
0x1802407a2  mov     rcx, r14
0x1802407a5  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1802407aa  mov     eax, 80070057h
0x1802407af  jmp     loc_18024487F
0x1802407b4  add     eax, r15d
0x1802407b7  jmp     loc_18024070C
0x1802407bc  mov     rsi, [rsp+968h+var_910]
0x1802407c1  mov     rbx, [rsp+968h+var_8E0]
0x1802407c9  mov     r11, [rsp+968h+var_888]
0x1802407d1  mov     dil, r15b
0x1802407d4  mov     [rsp+968h+var_8EC.IOCoherent], r12d
0x1802407d9  mov     rcx, [r11+2A8h]
0x1802407e0  mov     rax, [rcx]
0x1802407e3  mov     r9d, 4
0x1802407e9  lea     r8, [rsp+968h+var_8EC]
0x1802407ee  lea     edx, [r9+0Dh]
0x1802407f2  mov     rax, [rax+18h]
0x1802407f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802407fb  mov     r12d, 519h
0x180240801  test    eax, eax
0x180240803  jns     short loc_18024081A
0x180240805  lea     r8, aId3d12videoenc_9; "ID3D12VideoEncodeCommandList::EncodeFra"...
0x18024080c  mov     edx, r12d
0x18024080f  mov     rcx, r14
0x180240812  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180240817  xor     dil, dil
0x18024081a  mov     r9, r14; struct TDebugOutputFunctor *
0x18024081d  mov     rdx, rbx; struct ID3D12VideoEncoderHeap *
0x180240820  mov     rcx, [rsp+968h+var_8E8]; struct ID3D12VideoEncoder *
0x180240828  call    ?ValidateEncoderAndEncoderHeapCombination@@YAJPEAUID3D12VideoEncoder@@PEAUID3D12VideoEncoderHeap@@W4D3D12_MESSAGE_ID@@AEAUTDebugOutputFunctor@@@Z; ValidateEncoderAndEncoderHeapCombination(ID3D12VideoEncoder *,ID3D12VideoEncoderHeap *,D3D12_MESSAGE_ID,TDebugOutputFunctor &)
0x18024082d  xor     ebx, ebx
0x18024082f  movzx   ecx, dil
0x180240833  test    eax, eax
0x180240835  cmovns  ebx, ecx
0x180240838  test    dword ptr [rsi], 0FFFFFFE0h
0x18024083e  jz      short loc_180240854
0x180240840  lea     r8, aId3d12videoenc_62; "ID3D12VideoEncodeCommandList::EncodeFra"...
0x180240847  mov     edx, r12d
0x18024084a  mov     rcx, r14
0x18024084d  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180240852  xor     bl, bl
0x180240854  cmp     dword ptr [rsi+4], 2
0x180240858  jl      short loc_18024086E
0x18024085a  lea     r8, aId3d12videoenc_68; "ID3D12VideoEncodeCommandList::EncodeFra"...
0x180240861  mov     edx, r12d
0x180240864  mov     rcx, r14
0x180240867  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18024086c  xor     bl, bl
0x18024086e  mov     rcx, [rsp+968h+var_8E8]
0x180240876  mov     rax, [rcx]
0x180240879  mov     rax, [rax+50h]
0x18024087d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180240882  mov     [rsp+968h+var_898], eax
0x180240889  lea     rcx, [rsi+50h]; struct D3D12_VIDEO_ENCODER_SEQUENCE_GOP_STRUCTURE *
0x18024088d  lea     rdx, [rsp+968h+var_898]; enum D3D12_VIDEO_ENCODER_CODEC *
0x180240895  call    ?ValidateVideoEncodeCodecGOPStructure@@YAJAEBUD3D12_VIDEO_ENCODER_SEQUENCE_GOP_STRUCTURE@@AEBW4D3D12_VIDEO_ENCODER_CODEC@@@Z; ValidateVideoEncodeCodecGOPStructure(D3D12_VIDEO_ENCODER_SEQUENCE_GOP_STRUCTURE const &,D3D12_VIDEO_ENCODER_CODEC const &)
0x18024089a  test    eax, eax
0x18024089c  jns     short loc_1802408B2
0x18024089e  lea     r8, aId3d12videoenc_56; "ID3D12VideoEncodeCommandList::EncodeFra"...
0x1802408a5  mov     edx, r12d
0x1802408a8  mov     rcx, r14
0x1802408ab  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1802408b0  xor     bl, bl
0x1802408b2  lea     rcx, [rsi+10h]; struct D3D12_VIDEO_ENCODER_RATE_CONTROL *
0x1802408b6  mov     rdx, r14; struct TDebugOutputFunctor *
0x1802408b9  call    ?ValidateVideoEncodeRateControl@@YAJAEBUD3D12_VIDEO_ENCODER_RATE_CONTROL@@AEAUTDebugOutputFunctor@@@Z; ValidateVideoEncodeRateControl(D3D12_VIDEO_ENCODER_RATE_CONTROL const &,TDebugOutputFunctor &)
0x1802408be  xor     edi, edi
0x1802408c0  movzx   ecx, bl
0x1802408c3  test    eax, eax
0x1802408c5  cmovns  edi, ecx
0x1802408c8  mov     [rsp+968h+var_8B0], 0
0x1802408d3  mov     [rsp+968h+var_916], 0
0x1802408d8  lea     r9, [rsp+968h+var_8B0]
0x1802408e0  lea     r8, [rsp+968h+var_916]
0x1802408e5  mov     rdx, [rsp+968h+var_8E0]
0x1802408ed  mov     rcx, [rsi+30h]
0x1802408f1  call    ?ValidateResolutionPresentInEncoderHeap@@YAJUD3D12_VIDEO_ENCODER_PICTURE_RESOLUTION_DESC@@PEAUID3D12VideoEncoderHeap@@AEA_NAEAI@Z; ValidateResolutionPresentInEncoderHeap(D3D12_VIDEO_ENCODER_PICTURE_RESOLUTION_DESC,ID3D12VideoEncoderHeap *,bool &,uint &)
0x1802408f6  mov     ebx, eax
0x1802408f8  test    eax, eax
0x1802408fa  jns     short loc_180240919
0x1802408fc  mov     r9d, eax
0x1802408ff  lea     r8, aId3d12videoenc_42; "ID3D12VideoEncodeCommandList::EncodeFra"...
0x180240906  xor     edx, edx
0x180240908  mov     rcx, r14
0x18024090b  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180240910  mov     ecx, ebx; int
0x180240912  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180240917  jmp     short loc_180240935
0x180240919  cmp     [rsp+968h+var_916], 0
0x18024091e  jnz     short loc_180240935
0x180240920  lea     r8, aId3d12videoenc_32; "ID3D12VideoEncodeCommandList::EncodeFra"...
0x180240927  mov     edx, r12d
0x18024092a  mov     rcx, r14
0x18024092d  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180240932  xor     dil, dil
0x180240935  test    dword ptr [rsi+64h], 0FFFFFFF0h
0x18024093c  jz      short loc_180240953
0x18024093e  lea     r8, aId3d12videoenc_130; "ID3D12VideoEncodeCommandList::EncodeFra"...
0x180240945  mov     edx, r12d
0x180240948  mov     rcx, r14
0x18024094b  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180240950  xor     dil, dil
0x180240953  mov     rcx, [rsp+968h+var_8E8]
0x18024095b  mov     rax, [rcx]
0x18024095e  mov     rax, [rax+50h]
0x180240962  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180240967  mov     [rsp+968h+var_898], eax
0x18024096e  mov     r9, r14; struct TDebugOutputFunctor *
0x180240971  lea     r8, [rsp+968h+var_898]; enum D3D12_VIDEO_ENCODER_CODEC *
0x180240979  lea     rdx, [rsi+60h]; struct D3D12_VIDEO_ENCODER_PICTURE_CONTROL_DESC1 *
0x18024097d  mov     rcx, rsi; struct D3D12_VIDEO_ENCODER_SEQUENCE_CONTROL_DESC *
0x180240980  call    ?ValidateEncodeFrameCodecInput@@YAJAEBUD3D12_VIDEO_ENCODER_SEQUENCE_CONTROL_DESC@@AEBUD3D12_VIDEO_ENCODER_PICTURE_CONTROL_DESC1@@AEBW4D3D12_VIDEO_ENCODER_CODEC@@AEAUTDebugOutputFunctor@@@Z; ValidateEncodeFrameCodecInput(D3D12_VIDEO_ENCODER_SEQUENCE_CONTROL_DESC const &,D3D12_VIDEO_ENCODER_PICTURE_CONTROL_DESC1 const &,D3D12_VIDEO_ENCODER_CODEC const &,TDebugOutputFunctor &)
0x180240985  xor     ebx, ebx
0x180240987  movzx   ecx, dil
0x18024098b  test    eax, eax
0x18024098d  cmovns  ebx, ecx
0x180240990  cmp     dword ptr [r13+0], 0
0x180240995  jnz     short loc_18024099D
0x180240997  add     r13, 8
0x18024099b  jmp     short loc_1802409A5
0x18024099d  mov     r15d, [r13+0Ch]
0x1802409a1  mov     r13, [r13+18h]
0x1802409a5  test    r15d, r15d
0x1802409a8  jz      loc_180240A2E
0x1802409ae  xor     edi, edi
0x1802409b0  mov     rcx, [r13+rdi*8+0]
0x1802409b5  call    ??$QIFrom@VCResource@@@@YAPEAVCResource@@PEAUIUnknown@@AEBU_GUID@@W4ERefType@@@Z; QIFrom<CResource>(IUnknown *,_GUID const &,ERefType)
0x1802409ba  mov     rsi, rax
0x1802409bd  lea     rdx, [rsp+968h+var_5B8]; retstr
0x1802409c5  mov     rcx, rax; this
0x1802409c8  call    ?GetDesc@CResource@@UEAA?AUD3D12_RESOURCE_DESC@@XZ; CResource::GetDesc(void)
0x1802409cd  cmp     [rsp+968h+var_5B8.Dimension], 1
0x1802409d5  jz      short loc_1802409EB
0x1802409d7  lea     r8, aTheResourceInD_11; "The resource in D3D12_VIDEO_ENCODER_COM"...
0x1802409de  mov     edx, r12d
0x1802409e1  mov     rcx, r14
  ... truncated ...
```
