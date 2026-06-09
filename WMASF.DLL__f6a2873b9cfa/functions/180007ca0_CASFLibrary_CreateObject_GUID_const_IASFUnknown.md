# CASFLibrary::CreateObject(_GUID const &,IASFUnknown * *)

- ea: `0x180007ca0`
- end: `0x1800089a7`
- name: `?CreateObject@CASFLibrary@@UEAAJAEBU_GUID@@PEAPEAUIASFUnknown@@@Z`
- size: `3335`
- prototype: `__int64 __fastcall(CASFLibrary *__hidden this, const struct _GUID *, struct IASFUnknown **)`
- caller_count: `0`
- callee_count: `48`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001174`
- `0x1800015d0`
- `0x1800021dc`
- `0x18000220c`
- `0x1800041c8`
- `0x1800061f0`
- `0x180007ca0`
- `0x180009bf4`
- `0x18000a230`
- `0x18000bd30`
- `0x18000c100`
- `0x18000cc38`
- `0x18000cd3c`
- `0x18000d530`
- `0x18000d61c`
- `0x18000d90c`
- `0x18000e188`
- `0x18000e3a0`
- `0x18000eed4`
- `0x18000efbc`
- `0x1800101e4`
- `0x180010400`
- `0x180010450`
- `0x1800104a0`
- `0x180013a40`
- `0x180013d90`
- `0x1800144b0`
- `0x180014ba4`
- `0x180014e00`
- `0x180016154`
- `0x180016804`
- `0x180016d58`
- `0x1800173f4`
- `0x180017b04`
- `0x180017d60`
- `0x1800181a0`
- `0x180018604`
- `0x180018b14`
- `0x180019c20`
- `0x18001a19c`
- `0x18001aac8`
- `0x18001b074`
- `0x18001b93c`
- `0x18001c6cc`
- `0x18001cb34`
- `0x18001d9fc`
- `0x180024a7c`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFLibrary::CreateObject(CASFLibrary *this, const struct _GUID *a2, struct IASFUnknown **a3)
{
  __int64 result; // rax
  int v7; // ebx
  __int64 v8; // rcx
  __int64 v9; // rax
  CASFBandwidthSharingObjectv1 *v10; // rax
  CASFIndexBlock *v11; // rax
  CASFIndexBlock *v12; // rsi
  struct IASFUnknown *v13; // rcx
  __int64 v14; // rax
  CASFPrioritizationObject *v15; // rax
  __int64 v16; // rax
  CASFClockObjectv1 *v17; // rax
  __int64 v18; // rax
  CASFCodecListObjectv1 *v19; // rax
  __int64 v20; // rax
  CASFColorTableObject *v21; // rax
  __int64 v22; // rax
  CASFContentBrandingObjectv1 *v23; // rax
  __int64 v24; // rax
  CASFContentDescriptionObjectv1 *v25; // rax
  __int64 v26; // rax
  CASFExtendedContentDescriptionObjectv1 *v27; // rax
  __int64 v28; // rax
  CASFContentEncryptionObjectv1 *v29; // rax
  __int64 v30; // rax
  CASFContentEncryptionObjectv2 *v31; // rax
  __int64 v32; // rax
  CASFContentEncryptionObjectExv1 *v33; // rax
  __int64 v34; // rax
  CASFContentEncryptionObjectExv2 *v35; // rax
  __int64 v36; // rax
  CASFDataObjectv2 *v37; // rax
  __int64 v38; // rax
  CASFDataObjectv1 *v39; // rax
  __int64 v40; // rax
  CASFDataUnitExtensionObject *v41; // rax
  __int64 v42; // rax
  CASFErrorCorrectionObjectv1 *v43; // rax
  __int64 v44; // rax
  CASFExtendedStreamPropertiesObjectv1 *v45; // rax
  __int64 v46; // rax
  CASFFilePropertiesObject *v47; // rax
  __int64 v48; // rax
  CASFFilePropertiesObjectv1 *v49; // rax
  __int64 v50; // rax
  CASFGenericObject *v51; // rax
  __int64 v52; // rax
  CASFHeaderObjectv2 *v53; // rax
  __int64 v54; // rax
  CASFHeaderObjectv1 *v55; // rax
  __int64 v56; // rax
  CASFIndexBlock *v57; // rax
  __int64 v58; // rax
  CASFIndexBlock *v59; // rax
  CASFIndexBlock *v60; // rsi
  __int64 v61; // rcx
  void **v62; // r9
  __int64 v63; // rax
  CASFIndexObjectv2 *v64; // rax
  __int64 v65; // rax
  CASFIndexObjectv2 *v66; // rax
  GUID v67; // xmm0
  __int64 v68; // rax
  CASFIndexObjectv2 *v69; // rax
  __int64 v70; // rax
  CASFIndexParametersObjectV2 *v71; // rax
  __int64 v72; // rax
  CASFMediaObjectIndexParametersObject *v73; // rax
  __int64 v74; // rax
  CASFSMPTEIndexParametersObject *v75; // rax
  __int64 v76; // rax
  CASFLanguageListObject *v77; // rax
  __int64 v78; // rax
  CASFMarkerObjectv2 *v79; // rax
  __int64 v80; // rax
  CASFMarkerObjectv1 *v81; // rax
  __int64 v82; // rax
  CASFMetaDataObject *v83; // rax
  __int64 v84; // rax
  CASFMetaDataObjectv1 *v85; // rax
  __int64 v86; // rax
  CASFMetaDataObjectBase *v87; // rax
  __int64 v88; // rax
  CASFMutualExclusionObjectv1 *v89; // rax
  __int64 v90; // rax
  __int64 v91; // rax
  CASFMutualExclusionObjectv2 *v92; // rax
  __int64 v93; // rax
  CASFGroupMutualExclusionObjectv1 *v94; // rax
  __int64 v95; // rax
  CASFScriptCommandObjectv2 *v96; // rax
  __int64 v97; // rax
  CASFScriptCommandObjectv1 *v98; // rax
  __int64 v99; // rax
  CASFStreamPropertiesObjectv2 *v100; // rax
  __int64 v101; // rax
  CASFStreamPropertiesObjectv1 *v102; // rax
  __int64 v103; // rax
  CASFStreamPropertiesObjectExv1 *v104; // rax
  __int64 v105; // rax
  CASFDigitalSignatureObjectv1 *v106; // rax
  char v107[8]; // [rsp+30h] [rbp-20h] BYREF
  struct IWMSCriticalSection *v108; // [rsp+38h] [rbp-18h] BYREF
  __int64 v109; // [rsp+40h] [rbp-10h] BYREF

  v108 = 0;
  result = (*(__int64 (__fastcall **)(char *, struct IWMSCriticalSection **))(*((_QWORD *)this + 1) + 24LL))(
             (char *)this + 8,
             &v108);
  if ( (int)result >= 0 )
  {
    CAutoCritSec::CAutoCritSec((CAutoCritSec *)v107, v108);
    if ( v108 )
    {
      (*(void (__fastcall **)(struct IWMSCriticalSection *))(*(_QWORD *)v108 + 16LL))(v108);
      v108 = 0;
    }
    if ( !a3 )
    {
      v7 = -2147024809;
LABEL_249:
      CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v107);
      return (unsigned int)v7;
    }
    v8 = *((_QWORD *)this + 38);
    if ( v8 )
    {
      v7 = (*(__int64 (__fastcall **)(__int64, const struct _GUID *, CASFLibrary *, struct IASFUnknown **))(*(_QWORD *)v8 + 24LL))(
             v8,
             a2,
             this,
             a3);
      goto LABEL_249;
    }
    v9 = *(_QWORD *)&CLSID_ASFBandwidthSharingObject.Data1 - *(_QWORD *)&a2->Data1;
    if ( *(_QWORD *)&CLSID_ASFBandwidthSharingObject.Data1 == *(_QWORD *)&a2->Data1 )
      v9 = *(_QWORD *)CLSID_ASFBandwidthSharingObject.Data4 - *(_QWORD *)a2->Data4;
    if ( !v9 )
    {
      v10 = (CASFBandwidthSharingObjectv1 *)operator new(0xD0u);
      if ( !v10 )
        goto LABEL_248;
      v11 = CASFBandwidthSharingObjectv1::CASFBandwidthSharingObjectv1(v10);
LABEL_13:
      v12 = v11;
      if ( v11 )
      {
        v7 = (**(__int64 (__fastcall ***)(CASFIndexBlock *, GUID *, struct IASFUnknown **))v11)(
               v11,
               &IID_IASFUnknown,
               a3);
        (*(void (__fastcall **)(CASFIndexBlock *))(*(_QWORD *)v12 + 16LL))(v12);
        goto LABEL_15;
      }
LABEL_248:
      v7 = -2147024882;
      goto LABEL_249;
    }
    v14 = *(_QWORD *)&CLSID_ASFPrioritizationObject.Data1 - *(_QWORD *)&a2->Data1;
    if ( *(_QWORD *)&CLSID_ASFPrioritizationObject.Data1 == *(_QWORD *)&a2->Data1 )
      v14 = *(_QWORD *)CLSID_ASFPrioritizationObject.Data4 - *(_QWORD *)a2->Data4;
    if ( !v14 )
    {
      v15 = (CASFPrioritizationObject *)operator new(0xE0u);
      if ( !v15 )
        goto LABEL_248;
      v11 = CASFPrioritizationObject::CASFPrioritizationObject(v15);
      goto LABEL_13;
    }
    v16 = *(_QWORD *)&CLSID_ASFClockObjectv1.Data1 - *(_QWORD *)&a2->Data1;
    if ( *(_QWORD *)&CLSID_ASFClockObjectv1.Data1 == *(_QWORD *)&a2->Data1 )
      v16 = *(_QWORD *)CLSID_ASFClockObjectv1.Data4 - *(_QWORD *)a2->Data4;
    if ( !v16 )
    {
      v17 = (CASFClockObjectv1 *)operator new(0x78u);
      if ( !v17 )
        goto LABEL_248;
      v11 = CASFClockObjectv1::CASFClockObjectv1(v17);
      goto LABEL_13;
    }
    v18 = *(_QWORD *)&CLSID_ASFCodecListObjectv1.Data1 - *(_QWORD *)&a2->Data1;
    if ( *(_QWORD *)&CLSID_ASFCodecListObjectv1.Data1 == *(_QWORD *)&a2->Data1 )
      v18 = *(_QWORD *)CLSID_ASFCodecListObjectv1.Data4 - *(_QWORD *)a2->Data4;
    if ( !v18 )
    {
      v19 = (CASFCodecListObjectv1 *)operator new(0x3E8u);
      if ( !v19 )
        goto LABEL_248;
      v11 = CASFCodecListObjectv1::CASFCodecListObjectv1(v19);
      goto LABEL_13;
    }
    v20 = *(_QWORD *)&CLSID_ASFColorTableObject.Data1 - *(_QWORD *)&a2->Data1;
    if ( *(_QWORD *)&CLSID_ASFColorTableObject.Data1 == *(_QWORD *)&a2->Data1 )
      v20 = *(_QWORD *)CLSID_ASFColorTableObject.Data4 - *(_QWORD *)a2->Data4;
    if ( !v20 )
    {
      v21 = (CASFColorTableObject *)operator new(0xE0u);
      if ( !v21 )
        goto LABEL_248;
      v11 = CASFColorTableObject::CASFColorTableObject(v21);
      goto LABEL_13;
    }
    v22 = *(_QWORD *)&CLSID_ASFContentBrandingObjectv1.Data1 - *(_QWORD *)&a2->Data1;
    if ( *(_QWORD *)&CLSID_ASFContentBrandingObjectv1.Data1 == *(_QWORD *)&a2->Data1 )
      v22 = *(_QWORD *)CLSID_ASFContentBrandingObjectv1.Data4 - *(_QWORD *)a2->Data4;
    if ( !v22 )
    {
      v23 = (CASFContentBrandingObjectv1 *)operator new(0x78u);
      if ( !v23 )
        goto LABEL_248;
      v11 = CASFContentBrandingObjectv1::CASFContentBrandingObjectv1(v23);
      goto LABEL_13;
    }
    v24 = *(_QWORD *)&CLSID_ASFContentDescriptionObjectv1.Data1 - *(_QWORD *)&a2->Data1;
    if ( *(_QWORD *)&CLSID_ASFContentDescriptionObjectv1.Data1 == *(_QWORD *)&a2->Data1 )
      v24 = *(_QWORD *)CLSID_ASFContentDescriptionObjectv1.Data4 - *(_QWORD *)a2->Data4;
    if ( !v24 )
    {
      v25 = (CASFContentDescriptionObjectv1 *)operator new(0x288u);
      if ( !v25 )
        goto LABEL_248;
      v11 = CASFContentDescriptionObjectv1::CASFContentDescriptionObjectv1(v25);
      goto LABEL_13;
    }
    v26 = *(_QWORD *)&CLSID_ASFExtendedContentDescriptionObjectv1.Data1 - *(_QWORD *)&a2->Data1;
    if ( *(_QWORD *)&CLSID_ASFExtendedContentDescriptionObjectv1.Data1 == *(_QWORD *)&a2->Data1 )
      v26 = *(_QWORD *)CLSID_ASFExtendedContentDescriptionObjectv1.Data4 - *(_QWORD *)a2->Data4;
    if ( !v26 )
    {
      v27 = (CASFExtendedContentDescriptionObjectv1 *)operator new(0x330u);
      if ( !v27 )
        goto LABEL_248;
      v11 = CASFExtendedContentDescriptionObjectv1::CASFExtendedContentDescriptionObjectv1(v27);
      goto LABEL_13;
    }
    v28 = *(_QWORD *)&CLSID_ASFContentEncryptionObjectv1.Data1 - *(_QWORD *)&a2->Data1;
    if ( *(_QWORD *)&CLSID_ASFContentEncryptionObjectv1.Data1 == *(_QWORD *)&a2->Data1 )
      v28 = *(_QWORD *)CLSID_ASFContentEncryptionObjectv1.Data4 - *(_QWORD *)a2->Data4;
    if ( !v28 )
    {
      v29 = (CASFContentEncryptionObjectv1 *)operator new(0x90u);
      if ( !v29 )
        goto LABEL_248;
      v11 = CASFContentEncryptionObjectv1::CASFContentEncryptionObjectv1(v29);
      goto LABEL_13;
    }
    v30 = *(_QWORD *)&CLSID_ASFContentEncryptionObject.Data1 - *(_QWORD *)&a2->Data1;
    if ( *(_QWORD *)&CLSID_ASFContentEncryptionObject.Data1 == *(_QWORD *)&a2->Data1 )
      v30 = *(_QWORD *)CLSID_ASFContentEncryptionObject.Data4 - *(_QWORD *)a2->Data4;
    if ( !v30 )
    {
      v31 = (CASFContentEncryptionObjectv2 *)operator new(0x68u);
      if ( !v31 )
        goto LABEL_248;
      v11 = CASFContentEncryptionObjectv2::CASFContentEncryptionObjectv2(v31);
      goto LABEL_13;
    }
    v32 = *(_QWORD *)&CLSID_ASFContentEncryptionObjectExv1.Data1 - *(_QWORD *)&a2->Data1;
    if ( *(_QWORD *)&CLSID_ASFContentEncryptionObjectExv1.Data1 == *(_QWORD *)&a2->Data1 )
      v32 = *(_QWORD *)CLSID_ASFContentEncryptionObjectExv1.Data4 - *(_QWORD *)a2->Data4;
    if ( !v32 )
    {
      v33 = (CASFContentEncryptionObjectExv1 *)operator new(0x68u);
      if ( !v33 )
        goto LABEL_248;
      v11 = CASFContentEncryptionObjectExv1::CASFContentEncryptionObjectExv1(v33);
      goto LABEL_13;
    }
    v34 = *(_QWORD *)&CLSID_ASFContentEncryptionObjectExv2.Data1 - *(_QWORD *)&a2->Data1;
    if ( *(_QWORD *)&CLSID_ASFContentEncryptionObjectExv2.Data1 == *(_QWORD *)&a2->Data1 )
      v34 = *(_QWORD *)CLSID_ASFContentEncryptionObjectExv2.Data4 - *(_QWORD *)a2->Data4;
    if ( !v34 )
    {
      v35 = (CASFContentEncryptionObjectExv2 *)operator new(0x68u);
      if ( !v35 )
        goto LABEL_248;
      v11 = CASFContentEncryptionObjectExv2::CASFContentEncryptionObjectExv2(v35);
      goto LABEL_13;
    }
    v36 = *(_QWORD *)&CLSID_ASFDataObject.Data1 - *(_QWORD *)&a2->Data1;
    if ( *(_QWORD *)&CLSID_ASFDataObject.Data1 == *(_QWORD *)&a2->Data1 )
      v36 = *(_QWORD *)CLSID_ASFDataObject.Data4 - *(_QWORD *)a2->Data4;
    if ( !v36 )
    {
      v37 = (CASFDataObjectv2 *)operator new(0x138u);
      if ( !v37 )
        goto LABEL_248;
      v11 = CASFDataObjectv2::CASFDataObjectv2(v37);
      goto LABEL_13;
    }
    v38 = *(_QWORD *)&CLSID_ASFDataObjectv1.Data1 - *(_QWORD *)&a2->Data1;
    if ( *(_QWORD *)&CLSID_ASFDataObjectv1.Data1 == *(_QWORD *)&a2->Data1 )
      v38 = *(_QWORD *)CLSID_ASFDataObjectv1.Data4 - *(_QWORD *)a2->Data4;
    if ( !v38 )
    {
      v39 = (CASFDataObjectv1 *)operator new(0x160u);
      if ( !v39 )
        goto LABEL_248;
      v11 = CASFDataObjectv1::CASFDataObjectv1(v39);
      goto LABEL_13;
    }
    v40 = *(_QWORD *)&CLSID_ASFDataUnitExtensionObject.Data1 - *(_QWORD *)&a2->Data1;
    if ( *(_QWORD *)&CLSID_ASFDataUnitExtensionObject.Data1 == *(_QWORD *)&a2->Data1 )
      v40 = *(_QWORD *)CLSID_ASFDataUnitExtensionObject.Data4 - *(_QWORD *)a2->Data4;
    if ( !v40 )
    {
      v41 = (CASFDataUnitExtensionObject *)operator new(0x78u);
      if ( !v41 )
        goto LABEL_248;
      v11 = CASFDataUnitExtensionObject::CASFDataUnitExtensionObject(v41);
      goto LABEL_13;
    }
    v42 = *(_QWORD *)&CLSID_ASFErrorCorrectionObjectv1.Data1 - *(_QWORD *)&a2->Data1;
    if ( *(_QWORD *)&CLSID_ASFErrorCorrectionObjectv1.Data1 == *(_QWORD *)&a2->Data1 )
      v42 = *(_QWORD *)CLSID_ASFErrorCorrectionObjectv1.Data4 - *(_QWORD *)a2->Data4;
    if ( !v42 )
    {
      v43 = (CASFErrorCorrectionObjectv1 *)operator new(0x70u);
      if ( !v43 )
        goto LABEL_248;
      v11 = CASFErrorCorrectionObjectv1::CASFErrorCorrectionObjectv1(v43);
      goto LABEL_13;
    }
    v44 = *(_QWORD *)&CLSID_ASFExtendedStreamPropertiesObjectv1.Data1 - *(_QWORD *)&a2->Data1;
    if ( *(_QWORD *)&CLSID_ASFExtendedStreamPropertiesObjectv1.Data1 == *(_QWORD *)&a2->Data1 )
      v44 = *(_QWORD *)CLSID_ASFExtendedStreamPropertiesObjectv1.Data4 - *(_QWORD *)a2->Data4;
    if ( !v44 )
    {
      v45 = (CASFExtendedStreamPropertiesObjectv1 *)operator new(0x138u);
      if ( !v45 )
        goto LABEL_248;
      v11 = CASFExtendedStreamPropertiesObjectv1::CASFExtendedStreamPropertiesObjectv1(v45);
      goto LABEL_13;
    }
    v46 = *(_QWORD *)&CLSID_ASFFilePropertiesObject.Data1 - *(_QWORD *)&a2->Data1;
    if ( *(_QWORD *)&CLSID_ASFFilePropertiesObject.Data1 == *(_QWORD *)&a2->Data1 )
      v46 = *(_QWORD *)CLSID_ASFFilePropertiesObject.Data4 - *(_QWORD *)a2->Data4;
    if ( !v46 )
    {
      v47 = (CASFFilePropertiesObject *)operator new(0xB8u);
      if ( !v47 )
        goto LABEL_248;
      v11 = CASFFilePropertiesObject::CASFFilePropertiesObject(v47);
      goto LABEL_13;
    }
    v48 = *(_QWORD *)&CLSID_ASFPropertiesObjectv1.Data1 - *(_QWORD *)&a2->Data1;
    if ( *(_QWORD *)&CLSID_ASFPropertiesObjectv1.Data1 == *(_QWORD *)&a2->Data1 )
      v48 = *(_QWORD *)CLSID_ASFPropertiesObjectv1.Data4 - *(_QWORD *)a2->Data4;
    if ( !v48 )
    {
      v49 = (CASFFilePropertiesObjectv1 *)operator new(0xD8u);
      if ( !v49 )
        goto LABEL_248;
      v11 = CASFFilePropertiesObjectv1::CASFFilePropertiesObjectv1(v49);
      goto LABEL_13;
    }
    v50 = *(_QWORD *)&CLSID_ASFGenericObject.Data1 - *(_QWORD *)&a2->Data1;
    if ( *(_QWORD *)&CLSID_ASFGenericObject.Data1 == *(_QWORD *)&a2->Data1 )
      v50 = *(_QWORD *)CLSID_ASFGenericObject.Data4 - *(_QWORD *)a2->Data4;
    if ( !v50 )
    {
      v51 = (CASFGenericObject *)operator new(0x60u);
      if ( !v51 )
        goto LABEL_248;
      v11 = CASFGenericObject::CASFGenericObject(v51);
      goto LABEL_13;
    }
    v52 = *(_QWORD *)&CLSID_ASFHeaderObject.Data1 - *(_QWORD *)&a2->Data1;
    if ( *(_QWORD *)&CLSID_ASFHeaderObject.Data1 == *(_QWORD *)&a2->Data1 )
      v52 = *(_QWORD *)CLSID_ASFHeaderObject.Data4 - *(_QWORD *)a2->Data4;
    if ( !v52 )
    {
      v53 = (CASFHeaderObjectv2 *)operator new(0x160u);
      if ( !v53 )
        goto LABEL_248;
      v11 = CASFHeaderObjectv2::CASFHeaderObjectv2(v53);
      goto LABEL_13;
    }
    v54 = *(_QWORD *)&CLSID_ASFHeaderObjectv1.Data1 - *(_QWORD *)&a2->Data1;
    if ( *(_QWORD *)&CLSID_ASFHeaderObjectv1.Data1 == *(_QWORD *)&a2->Data1 )
      v54 = *(_QWORD *)CLSID_ASFHeaderObjectv1.Data4 - *(_QWORD *)a2->Data4;
    if ( !v54 )
    {
      v55 = (CASFHeaderObjectv1 *)operator new(0x170u);
      if ( !v55 )
        goto LABEL_248;
      v11 = CASFHeaderObjectv1::CASFHeaderObjectv1(v55);
      goto LABEL_13;
    }
    v56 = *(_QWORD *)&CLSID_ASFIndexBlock.Data1 - *(_QWORD *)&a2->Data1;
    if ( *(_QWORD *)&CLSID_ASFIndexBlock.Data1 == *(_QWORD *)&a2->Data1 )
      v56 = *(_QWORD *)CLSID_ASFIndexBlock.Data4 - *(_QWORD *)a2->Data4;
    if ( !v56 )
    {
      v57 = (CASFIndexBlock *)operator new(0x90u);
      if ( !v57 )
        goto LABEL_248;
      v11 = CASFIndexBlock::CASFIndexBlock(v57);
      goto LABEL_13;
    }
    v58 = *(_QWORD *)&CLSID_ASFSMPTEIndexBlock.Data1 - *(_QWORD *)&a2->Data1;
    if ( *(_QWORD *)&CLSID_ASFSMPTEIndexBlock.Data1 == *(_QWORD *)&a2->Data1 )
      v58 = *(_QWORD *)CLSID_ASFSMPTEIndexBlock.Data4 - *(_QWORD *)a2->Data4;
    if ( !v58 )
    {
      v59 = (CASFIndexBlock *)operator new(0x90u);
      v60 = v59;
      if ( !v59 )
        goto LABEL_248;
      CASFIndexBlock::CASFIndexBlock(v59);
      *(_QWORD *)(v61 + 8) = &CASFIndexBlock::`vftable'{for `IASFIndexBlockPriv'};
      v62 = &CASFSMPTEIndexBlock::`vftable'{for `IASFSMPTEIndexBlock'};
      *(_QWORD *)v61 = &CASFSMPTEIndexBlock::`vftable'{for `IASFSMPTEIndexBlock'};
      *(_QWORD *)(v61 + 16) = &CASFSMPTEIndexBlock::`vftable'{for `CPoolReleaseItem'};
LABEL_137:
      v7 = ((__int64 (__fastcall *)(__int64, GUID *, struct IASFUnknown **))*v62)(v61, &IID_IASFUnknown, a3);
      (*(void (__fastcall **)(CASFIndexBlock *))(*(_QWORD *)v60 + 16LL))(v60);
LABEL_15:
      if ( v7 >= 0 )
      {
        v13 = *a3;
        v109 = 0;
        if ( (**(int (__fastcall ***)(struct IASFUnknown *, GUID *, __int64 *))v13)(v13, &IID_IASFUnknownPriv, &v109) < 0 )
          goto LABEL_247;
        v7 = (*(__int64 (__fastcall **)(__int64, CASFLibrary *))(*(_QWORD *)v109 + 24LL))(v109, this);
        if ( v109 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v109 + 16LL))(v109);
          v109 = 0;
        }
        if ( v7 >= 0 )
        {
LABEL_247:
          CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v107);
          return 0;
        }
        if ( *a3 )
        {
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 16LL))(*a3);
          *a3 = 0;
        }
      }
      goto LABEL_249;
    }
    v63 = *(_QWORD *)&CLSID_ASFIndexObject.Data1 - *(_QWORD *)&a2->Data1;
    if ( *(_QWORD *)&CLSID_ASFIndexObject.Data1 == *(_QWORD *)&a2->Data1 )
      v63 = *(_QWORD *)CLSID_ASFIndexObject.Data4 - *(_QWORD *)a2->Data4;
    if ( !v63 )
    {
      v64 = (CASFIndexObjectv2 *)operator new(0x1C8u);
      if ( !v64 )
        goto LABEL_248;
      v11 = CASFIndexObjectv2::CASFIndexObjectv2(v64);
      goto LABEL_13;
    }
    v65 = *(_QWORD *)&CLSID_ASFMediaObjectIndexObject.Data1 - *(_QWORD *)&a2->Data1;
    if ( *(_QWORD *)&CLSID_ASFMediaObjectIndexObject.Data1 == *(_QWORD *)&a2->Data1 )
      v65 = *(_QWORD *)CLSID_ASFMediaObjectIndexObject.Data4 - *(_QWORD *)a2->Data4;
    if ( !v65 )
    {
      v66 = (CASFIndexObjectv2 *)operator new(0x1C8u);
      v60 = v66;
      if ( !v66 )
        goto LABEL_248;
      CASFIndexObjectv2::CASFIndexObjectv2(v66);
      *(_QWORD *)(v61 + 8) = &CASFSMPTEIndexObject::`vftable'{for `IASFUnknownPriv'};
      v62 = &CASFIndexObjectv2::`vftable'{for `IASFIndexObject'};
      *(_QWORD *)v61 = &CASFIndexObjectv2::`vftable'{for `IASFIndexObject'};
      *(_QWORD *)(v61 + 16) = &CASFSMPTEIndexObject::`vftable'{for `CPoolReleaseItem'};
      v67 = CLSID_ASFMediaObjectIndexObject;
      goto LABEL_148;
    }
    v68 = *(_QWORD *)&CLSID_ASFSMPTEIndexObject.Data1 - *(_QWORD *)&a2->Data1;
    if ( *(_QWORD *)&CLSID_ASFSMPTEIndexObject.Data1 == *(_QWORD *)&a2->Data1 )
      v68 = *(_QWORD *)CLSID_ASFSMPTEIndexObject.Data4 - *(_QWORD *)a2->Data4;
    if ( !v68 )
    {
      v69 = (CASFIndexObjectv2 *)operator new(0x1C8u);
      v60 = v69;
      if ( !v69 )
        goto LABEL_248;
      CASFIndexObjectv2::CASFIndexObjectv2(v69);
      *(_QWORD *)(v61 + 8) = &CASFSMPTEIndexObject::`vftable'{for `IASFUnknownPriv'};
      v62 = &CASFSMPTEIndexObject::`vftable'{for `IASFIndexObject'};
      *(_QWORD *)v61 = &CASFSMPTEIndexObject::`vftable'{for `IASFIndexObject'};
      *(_QWORD *)(v61 + 16) = &CASFSMPTEIndexObject::`vftable'{for `CPoolReleaseItem'};
      v67 = CLSID_ASFSMPTEIndexObject;
      goto LABEL_148;
    }
    v70 = *(_QWORD *)&CLSID_ASFIndexParametersObject.Data1 - *(_QWORD *)&a2->Data1;
    if ( *(_QWORD *)&CLSID_ASFIndexParametersObject.Data1 == *(_QWORD *)&a2->Data1 )
      v70 = *(_QWORD *)CLSID_ASFIndexParametersObject.Data4 - *(_QWORD *)a2->Data4;
    if ( !v70 )
    {
      v71 = (CASFIndexParametersObjectV2 *)operator new(0xE8u);
      if ( !v71 )
        goto LABEL_248;
      v11 = CASFIndexParametersObjectV2::CASFIndexParametersObjectV2(v71);
      goto LABEL_13;
    }
    v72 = *(_QWORD *)&CLSID_ASFMediaObjectIndexParametersObject.Data1 - *(_QWORD *)&a2->Data1;
    if ( *(_QWORD *)&CLSID_ASFMediaObjectIndexParametersObject.Data1 == *(_QWORD *)&a2->Data1 )
      v72 = *(_QWORD *)CLSID_ASFMediaObjectIndexParametersObject.Data4 - *(_QWORD *)a2->Data4;
    if ( !v72 )
    {
      v73 = (CASFMediaObjectIndexParametersObject *)operator new(0xE8u);
      if ( !v73 )
        goto LABEL_248;
      v11 = CASFMediaObjectIndexParametersObject::CASFMediaObjectIndexParametersObject(v73);
      goto LABEL_13;
    }
    v74 = *(_QWORD *)&CLSID_ASFSMPTEIndexParametersObject.Data1 - *(_QWORD *)&a2->Data1;
    if ( *(_QWORD *)&CLSID_ASFSMPTEIndexParametersObject.Data1 == *(_QWORD *)&a2->Data1 )
      v74 = *(_QWORD *)CLSID_ASFSMPTEIndexParametersObject.Data4 - *(_QWORD *)a2->Data4;
    if ( !v74 )
    {
      v75 = (CASFSMPTEIndexParametersObject *)operator new(0xE8u);
      if ( !v75 )
        goto LABEL_248;
      v11 = CASFSMPTEIndexParametersObject::CASFSMPTEIndexParametersObject(v75);
      goto LABEL_13;
    }
    v76 = *(_QWORD *)&CLSID_ASFLanguageListObject.Data1 - *(_QWORD *)&a2->Data1;
    if ( *(_QWORD *)&CLSID_ASFLanguageListObject.Data1 == *(_QWORD *)&a2->Data1 )
      v76 = *(_QWORD *)CLSID_ASFLanguageListObject.Data4 - *(_QWORD *)a2->Data4;
    if ( !v76 )
    {
      v77 = (CASFLanguageListObject *)operator new(0x140u);
      if ( !v77 )
        goto LABEL_248;
      v11 = CASFLanguageListObject::CASFLanguageListObject(v77);
      goto LABEL_13;
    }
    v78 = *(_QWORD *)&CLSID_ASFMarkerObject.Data1 - *(_QWORD *)&a2->Data1;
    if ( *(_QWORD *)&CLSID_ASFMarkerObject.Data1 == *(_QWORD *)&a2->Data1 )
      v78 = *(_QWORD *)CLSID_ASFMarkerObject.Data4 - *(_QWORD *)a2->Data4;
    if ( !v78 )
    {
      v79 = (CASFMarkerObjectv2 *)operator new(0x1C0u);
      if ( !v79 )
        goto LABEL_248;
      v11 = CASFMarkerObjectv2::CASFMarkerObjectv2(v79);
      goto LABEL_13;
    }
    v80 = *(_QWORD *)&CLSID_ASFMarkerObjectv1.Data1 - *(_QWORD *)&a2->Data1;
    if ( *(_QWORD *)&CLSID_ASFMarkerObjectv1.Data1 == *(_QWORD *)&a2->Data1 )
      v80 = *(_QWORD *)CLSID_ASFMarkerObjectv1.Data4 - *(_QWORD *)a2->Data4;
    if ( !v80 )
    {
      v81 = (CASFMarkerObjectv1 *)operator new(0x1D0u);
      if ( !v81 )
        goto LABEL_248;
      v11 = CASFMarkerObjectv1::CASFMarkerObjectv1(v81);
      goto LABEL_13;
    }
    v82 = *(_QWORD *)&CLSID_ASFMetaDataObject.Data1 - *(_QWORD *)&a2->Data1;
    if ( *(_QWORD *)&CLSID_ASFMetaDataObject.Data1 == *(_QWORD *)&a2->Data1 )
      v82 = *(_QWORD *)CLSID_ASFMetaDataObject.Data4 - *(_QWORD *)a2->Data4;
    if ( !v82 )
    {
      v83 = (CASFMetaDataObject *)operator new(0x330u);
      if ( !v83 )
        goto LABEL_248;
      v11 = CASFMetaDataObject::CASFMetaDataObject(v83);
      goto LABEL_13;
    }
    v84 = *(_QWORD *)&CLSID_ASFMetaDataObjectv1.Data1 - *(_QWORD *)&a2->Data1;
    if ( *(_QWORD *)&CLSID_ASFMetaDataObjectv1.Data1 == *(_QWORD *)&a2->Data1 )
      v84 = *(_QWORD *)CLSID_ASFMetaDataObjectv1.Data4 - *(_QWORD *)a2->Data4;
    if ( !v84 )
    {
      v85 = (CASFMetaDataObjectv1 *)operator new(0x330u);
      if ( !v85 )
        goto LABEL_248;
      v11 = CASFMetaDataObjectv1::CASFMetaDataObjectv1(v85);
      goto LABEL_13;
    }
    v86 = *(_QWORD *)&CLSID_ASFMetaDataLibraryObjectv1.Data1 - *(_QWORD *)&a2->Data1;
    if ( *(_QWORD *)&CLSID_ASFMetaDataLibraryObjectv1.Data1 == *(_QWORD *)&a2->Data1 )
      v86 = *(_QWORD *)CLSID_ASFMetaDataLibraryObjectv1.Data4 - *(_QWORD *)a2->Data4;
    if ( !v86 )
    {
      v87 = (CASFMetaDataObjectBase *)operator new(0x330u);
      v60 = v87;
      if ( !v87 )
        goto LABEL_248;
      CASFMetaDataObjectBase::CASFMetaDataObjectBase(v87);
      *(_DWORD *)(v61 + 808) = 1;
      *(_QWORD *)(v61 + 8) = &CASFMetaDataObject::`vftable'{for `IASFUnknownPriv'};
      v62 = &CASFMetaDataLibraryObjectv1::`vftable'{for `IASFMetaDataObject'};
      *(_QWORD *)v61 = &CASFMetaDataLibraryObjectv1::`vftable'{for `IASFMetaDataObject'};
      *(_QWORD *)(v61 + 16) = &CASFMetaDataLibraryObjectv1::`vftable'{for `CPoolReleaseItem'};
      v67 = CLSID_ASFMetaDataLibraryObjectv1;
LABEL_148:
      *((GUID *)v60 + 3) = v67;
      goto LABEL_137;
    }
    v88 = *(_QWORD *)&CLSID_ASFMutualExclusionObjectv1.Data1 - *(_QWORD *)&a2->Data1;
    if ( *(_QWORD *)&CLSID_ASFMutualExclusionObjectv1.Data1 == *(_QWORD *)&a2->Data1 )
      v88 = *(_QWORD *)CLSID_ASFMutualExclusionObjectv1.Data4 - *(_QWORD *)a2->Data4;
    if ( !v88 )
      goto LABEL_202;
    v90 = *(_QWORD *)&CLSID_ASFMutualExclusionObjectExv1.Data1 - *(_QWORD *)&a2->Data1;
    if ( *(_QWORD *)&CLSID_ASFMutualExclusionObjectExv1.Data1 == *(_QWORD *)&a2->Data1 )
      v90 = *(_QWORD *)CLSID_ASFMutualExclusionObjectExv1.Data4 - *(_QWORD *)a2->Data4;
    if ( !v90 )
    {
LABEL_202:
      v89 = (CASFMutualExclusionObjectv1 *)operator new(0x2D0u);
      if ( !v89 )
        goto LABEL_248;
      v11 = CASFMutualExclusionObjectv1::CASFMutualExclusionObjectv1(v89);
      goto LABEL_13;
    }
    v91 = *(_QWORD *)&CLSID_ASFMutualExclusionObject.Data1 - *(_QWORD *)&a2->Data1;
    if ( *(_QWORD *)&CLSID_ASFMutualExclusionObject.Data1 == *(_QWORD *)&a2->Data1 )
      v91 = *(_QWORD *)CLSID_ASFMutualExclusionObject.Data4 - *(_QWORD *)a2->Data4;
    if ( !v91 )
    {
      v92 = (CASFMutualExclusionObjectv2 *)operator new(0x2D0u);
      if ( !v92 )
        goto LABEL_248;
      v11 = CASFMutualExclusionObjectv2::CASFMutualExclusionObjectv2(v92);
      goto LABEL_13;
    }
    v93 = *(_QWORD *)&CLSID_ASFGroupMutualExclusionObjectv1.Data1 - *(_QWORD *)&a2->Data1;
    if ( *(_QWORD *)&CLSID_ASFGroupMutualExclusionObjectv1.Data1 == *(_QWORD *)&a2->Data1 )
      v93 = *(_QWORD *)CLSID_ASFGroupMutualExclusionObjectv1.Data4 - *(_QWORD *)a2->Data4;
    if ( !v93 )
    {
      v94 = (CASFGroupMutualExclusionObjectv1 *)operator new(0x2D0u);
      if ( !v94 )
        goto LABEL_248;
      v11 = CASFGroupMutualExclusionObjectv1::CASFGroupMutualExclusionObjectv1(v94);
      goto LABEL_13;
    }
    v95 = *(_QWORD *)&CLSID_ASFScriptCommandObject.Data1 - *(_QWORD *)&a2->Data1;
    if ( *(_QWORD *)&CLSID_ASFScriptCommandObject.Data1 == *(_QWORD *)&a2->Data1 )
      v95 = *(_QWORD *)CLSID_ASFScriptCommandObject.Data4 - *(_QWORD *)a2->Data4;
    if ( !v95 )
    {
      v96 = (CASFScriptCommandObjectv2 *)operator new(0x368u);
      if ( !v96 )
        goto LABEL_248;
      v11 = CASFScriptCommandObjectv2::CASFScriptCommandObjectv2(v96);
      goto LABEL_13;
    }
    v97 = *(_QWORD *)&CLSID_ASFScriptCommandObjectv1.Data1 - *(_QWORD *)&a2->Data1;
    if ( *(_QWORD *)&CLSID_ASFScriptCommandObjectv1.Data1 == *(_QWORD *)&a2->Data1 )
      v97 = *(_QWORD *)CLSID_ASFScriptCommandObjectv1.Data4 - *(_QWORD *)a2->Data4;
    if ( !v97 )
    {
      v98 = (CASFScriptCommandObjectv1 *)operator new(0x368u);
      if ( !v98 )
        goto LABEL_248;
      v11 = CASFScriptCommandObjectv1::CASFScriptCommandObjectv1(v98);
      goto LABEL_13;
    }
    v99 = *(_QWORD *)&CLSID_ASFStreamPropertiesObject.Data1 - *(_QWORD *)&a2->Data1;
    if ( *(_QWORD *)&CLSID_ASFStreamPropertiesObject.Data1 == *(_QWORD *)&a2->Data1 )
      v99 = *(_QWORD *)CLSID_ASFStreamPropertiesObject.Data4 - *(_QWORD *)a2->Data4;
    if ( !v99 )
    {
      v100 = (CASFStreamPropertiesObjectv2 *)operator new(0x2B0u);
      if ( !v100 )
        goto LABEL_248;
      v11 = CASFStreamPropertiesObjectv2::CASFStreamPropertiesObjectv2(v100);
      goto LABEL_13;
    }
    v101 = *(_QWORD *)&CLSID_ASFStreamPropertiesObjectv1.Data1 - *(_QWORD *)&a2->Data1;
    if ( *(_QWORD *)&CLSID_ASFStreamPropertiesObjectv1.Data1 == *(_QWORD *)&a2->Data1 )
      v101 = *(_QWORD *)CLSID_ASFStreamPropertiesObjectv1.Data4 - *(_QWORD *)a2->Data4;
    if ( !v101 )
    {
      v102 = (CASFStreamPropertiesObjectv1 *)operator new(0x2E8u);
      if ( !v102 )
        goto LABEL_248;
      v11 = CASFStreamPropertiesObjectv1::CASFStreamPropertiesObjectv1(v102);
      goto LABEL_13;
    }
    v103 = *(_QWORD *)&CLSID_ASFStreamPropertiesObjectExv1.Data1 - *(_QWORD *)&a2->Data1;
    if ( *(_QWORD *)&CLSID_ASFStreamPropertiesObjectExv1.Data1 == *(_QWORD *)&a2->Data1 )
      v103 = *(_QWORD *)CLSID_ASFStreamPropertiesObjectExv1.Data4 - *(_QWORD *)a2->Data4;
    if ( !v103 )
    {
      v104 = (CASFStreamPropertiesObjectExv1 *)operator new(0x260u);
      if ( !v104 )
        goto LABEL_248;
      v11 = CASFStreamPropertiesObjectExv1::CASFStreamPropertiesObjectExv1(v104);
      goto LABEL_13;
    }
    v105 = *(_QWORD *)&CLSID_ASFDigitalSignatureObject.Data1 - *(_QWORD *)&a2->Data1;
    if ( *(_QWORD *)&CLSID_ASFDigitalSignatureObject.Data1 == *(_QWORD *)&a2->Data1 )
      v105 = *(_QWORD *)CLSID_ASFDigitalSignatureObject.Data4 - *(_QWORD *)a2->Data4;
    if ( !v105 )
    {
      v106 = (CASFDigitalSignatureObjectv1 *)operator new(0x68u);
      if ( !v106 )
        goto LABEL_248;
      v11 = CASFDigitalSignatureObjectv1::CASFDigitalSignatureObjectv1(v106);
      goto LABEL_13;
    }
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v107);
    return 3222079472LL;
  }
  return result;
}

```

## disassembly

```asm
0x180007ca0  push    rbp
0x180007ca2  push    rbx
0x180007ca3  push    rsi
0x180007ca4  push    rdi
0x180007ca5  push    r14
0x180007ca7  mov     rbp, rsp
0x180007caa  sub     rsp, 50h
0x180007cae  mov     rax, cs:__security_cookie
0x180007cb5  xor     rax, rsp
0x180007cb8  mov     [rbp+var_8], rax
0x180007cbc  mov     r14, rcx
0x180007cbf  mov     [rbp+var_18], 0
0x180007cc7  add     rcx, 8
0x180007ccb  mov     rbx, rdx
0x180007cce  lea     rdx, [rbp+var_18]
0x180007cd2  mov     rdi, r8
0x180007cd5  mov     rax, [rcx]
0x180007cd8  mov     rax, [rax+18h]
0x180007cdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ce1  test    eax, eax
0x180007ce3  js      loc_180008990
0x180007ce9  mov     rdx, [rbp+var_18]; struct IWMSCriticalSection *
0x180007ced  lea     rcx, [rbp+var_20]; this
0x180007cf1  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x180007cf6  mov     rcx, [rbp+var_18]
0x180007cfa  test    rcx, rcx
0x180007cfd  jz      short loc_180007D13
0x180007cff  mov     rax, [rcx]
0x180007d02  mov     rax, [rax+10h]
0x180007d06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d0b  mov     [rbp+var_18], 0
0x180007d13  test    rdi, rdi
0x180007d16  jnz     short loc_180007D22
0x180007d18  mov     ebx, 80070057h
0x180007d1d  jmp     loc_180008975
0x180007d22  mov     rcx, [r14+130h]
0x180007d29  test    rcx, rcx
0x180007d2c  jz      short loc_180007D4A
0x180007d2e  mov     rax, [rcx]
0x180007d31  mov     r9, rdi
0x180007d34  mov     r8, r14
0x180007d37  mov     rdx, rbx
0x180007d3a  mov     rax, [rax+18h]
0x180007d3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d43  mov     ebx, eax
0x180007d45  jmp     loc_180008975
0x180007d4a  mov     rax, qword ptr cs:CLSID_ASFBandwidthSharingObject.Data1
0x180007d51  sub     rax, [rbx]
0x180007d54  jnz     short loc_180007D61
0x180007d56  mov     rax, qword ptr cs:CLSID_ASFBandwidthSharingObject.Data4
0x180007d5d  sub     rax, [rbx+8]
0x180007d61  test    rax, rax
0x180007d64  jnz     loc_180007E49
0x180007d6a  mov     ecx, 0D0h; Size
0x180007d6f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007d74  test    rax, rax
0x180007d77  jz      loc_180008970
0x180007d7d  mov     rcx, rax; this
0x180007d80  call    ??0CASFBandwidthSharingObjectv1@@QEAA@XZ; CASFBandwidthSharingObjectv1::CASFBandwidthSharingObjectv1(void)
0x180007d85  mov     rsi, rax
0x180007d88  test    rax, rax
0x180007d8b  jz      loc_180008970
0x180007d91  mov     rcx, [rax]
0x180007d94  lea     rdx, IID_IASFUnknown
0x180007d9b  mov     r8, rdi
0x180007d9e  mov     rax, [rcx]
0x180007da1  mov     rcx, rsi
0x180007da4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007da9  mov     rcx, [rsi]
0x180007dac  mov     ebx, eax
0x180007dae  mov     rax, [rcx+10h]
0x180007db2  mov     rcx, rsi
0x180007db5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007dba  test    ebx, ebx
0x180007dbc  js      loc_180008975
0x180007dc2  mov     rcx, [rdi]
0x180007dc5  lea     r8, [rbp+var_10]
0x180007dc9  mov     [rbp+var_10], 0
0x180007dd1  lea     rdx, IID_IASFUnknownPriv
0x180007dd8  mov     rax, [rcx]
0x180007ddb  mov     rax, [rax]
0x180007dde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007de3  test    eax, eax
0x180007de5  js      loc_180008963
0x180007deb  mov     rcx, [rbp+var_10]
0x180007def  mov     rdx, r14
0x180007df2  mov     rax, [rcx]
0x180007df5  mov     rax, [rax+18h]
0x180007df9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007dfe  mov     rcx, [rbp+var_10]
0x180007e02  mov     ebx, eax
0x180007e04  test    rcx, rcx
0x180007e07  jz      short loc_180007E1D
0x180007e09  mov     rax, [rcx]
0x180007e0c  mov     rax, [rax+10h]
0x180007e10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e15  mov     [rbp+var_10], 0
0x180007e1d  test    ebx, ebx
0x180007e1f  jns     loc_180008963
0x180007e25  mov     rcx, [rdi]
0x180007e28  test    rcx, rcx
0x180007e2b  jz      loc_180008975
0x180007e31  mov     rax, [rcx]
0x180007e34  mov     rax, [rax+10h]
0x180007e38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e3d  mov     qword ptr [rdi], 0
0x180007e44  jmp     loc_180008975
0x180007e49  mov     rax, qword ptr cs:CLSID_ASFPrioritizationObject.Data1
0x180007e50  sub     rax, [rbx]
0x180007e53  jnz     short loc_180007E60
0x180007e55  mov     rax, qword ptr cs:CLSID_ASFPrioritizationObject.Data4
0x180007e5c  sub     rax, [rbx+8]
0x180007e60  test    rax, rax
0x180007e63  jnz     short loc_180007E85
0x180007e65  mov     ecx, 0E0h; Size
0x180007e6a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007e6f  test    rax, rax
0x180007e72  jz      loc_180008970
0x180007e78  mov     rcx, rax; this
0x180007e7b  call    ??0CASFPrioritizationObject@@QEAA@XZ; CASFPrioritizationObject::CASFPrioritizationObject(void)
0x180007e80  jmp     loc_180007D85
0x180007e85  mov     rax, qword ptr cs:CLSID_ASFClockObjectv1.Data1
0x180007e8c  sub     rax, [rbx]
0x180007e8f  jnz     short loc_180007E9C
0x180007e91  mov     rax, qword ptr cs:CLSID_ASFClockObjectv1.Data4
0x180007e98  sub     rax, [rbx+8]
0x180007e9c  test    rax, rax
0x180007e9f  jnz     short loc_180007EBF
0x180007ea1  lea     ecx, [rax+78h]; Size
0x180007ea4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007ea9  test    rax, rax
0x180007eac  jz      loc_180008970
0x180007eb2  mov     rcx, rax; this
0x180007eb5  call    ??0CASFClockObjectv1@@QEAA@XZ; CASFClockObjectv1::CASFClockObjectv1(void)
0x180007eba  jmp     loc_180007D85
0x180007ebf  mov     rax, qword ptr cs:CLSID_ASFCodecListObjectv1.Data1
0x180007ec6  sub     rax, [rbx]
0x180007ec9  jnz     short loc_180007ED6
0x180007ecb  mov     rax, qword ptr cs:CLSID_ASFCodecListObjectv1.Data4
0x180007ed2  sub     rax, [rbx+8]
0x180007ed6  test    rax, rax
0x180007ed9  jnz     short loc_180007EFB
0x180007edb  mov     ecx, 3E8h; Size
0x180007ee0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007ee5  test    rax, rax
0x180007ee8  jz      loc_180008970
0x180007eee  mov     rcx, rax; this
0x180007ef1  call    ??0CASFCodecListObjectv1@@QEAA@XZ; CASFCodecListObjectv1::CASFCodecListObjectv1(void)
0x180007ef6  jmp     loc_180007D85
0x180007efb  mov     rax, qword ptr cs:CLSID_ASFColorTableObject.Data1
0x180007f02  sub     rax, [rbx]
0x180007f05  jnz     short loc_180007F12
0x180007f07  mov     rax, qword ptr cs:CLSID_ASFColorTableObject.Data4
0x180007f0e  sub     rax, [rbx+8]
0x180007f12  test    rax, rax
0x180007f15  jnz     short loc_180007F37
0x180007f17  mov     ecx, 0E0h; Size
0x180007f1c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007f21  test    rax, rax
0x180007f24  jz      loc_180008970
0x180007f2a  mov     rcx, rax; this
0x180007f2d  call    ??0CASFColorTableObject@@QEAA@XZ; CASFColorTableObject::CASFColorTableObject(void)
0x180007f32  jmp     loc_180007D85
0x180007f37  mov     rax, qword ptr cs:CLSID_ASFContentBrandingObjectv1.Data1
0x180007f3e  sub     rax, [rbx]
0x180007f41  jnz     short loc_180007F4E
0x180007f43  mov     rax, qword ptr cs:CLSID_ASFContentBrandingObjectv1.Data4
0x180007f4a  sub     rax, [rbx+8]
0x180007f4e  test    rax, rax
0x180007f51  jnz     short loc_180007F71
0x180007f53  lea     ecx, [rax+78h]; Size
0x180007f56  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007f5b  test    rax, rax
0x180007f5e  jz      loc_180008970
0x180007f64  mov     rcx, rax; this
0x180007f67  call    ??0CASFContentBrandingObjectv1@@QEAA@XZ; CASFContentBrandingObjectv1::CASFContentBrandingObjectv1(void)
0x180007f6c  jmp     loc_180007D85
0x180007f71  mov     rax, qword ptr cs:CLSID_ASFContentDescriptionObjectv1.Data1
0x180007f78  sub     rax, [rbx]
0x180007f7b  jnz     short loc_180007F88
0x180007f7d  mov     rax, qword ptr cs:CLSID_ASFContentDescriptionObjectv1.Data4
0x180007f84  sub     rax, [rbx+8]
0x180007f88  test    rax, rax
0x180007f8b  jnz     short loc_180007FAD
0x180007f8d  mov     ecx, 288h; Size
0x180007f92  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007f97  test    rax, rax
0x180007f9a  jz      loc_180008970
0x180007fa0  mov     rcx, rax; this
0x180007fa3  call    ??0CASFContentDescriptionObjectv1@@QEAA@XZ; CASFContentDescriptionObjectv1::CASFContentDescriptionObjectv1(void)
0x180007fa8  jmp     loc_180007D85
0x180007fad  mov     rax, qword ptr cs:CLSID_ASFExtendedContentDescriptionObjectv1.Data1
0x180007fb4  sub     rax, [rbx]
0x180007fb7  jnz     short loc_180007FC4
0x180007fb9  mov     rax, qword ptr cs:CLSID_ASFExtendedContentDescriptionObjectv1.Data4
0x180007fc0  sub     rax, [rbx+8]
0x180007fc4  test    rax, rax
0x180007fc7  jnz     short loc_180007FE9
0x180007fc9  mov     ecx, 330h; Size
0x180007fce  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007fd3  test    rax, rax
0x180007fd6  jz      loc_180008970
0x180007fdc  mov     rcx, rax; this
0x180007fdf  call    ??0CASFExtendedContentDescriptionObjectv1@@QEAA@XZ; CASFExtendedContentDescriptionObjectv1::CASFExtendedContentDescriptionObjectv1(void)
0x180007fe4  jmp     loc_180007D85
0x180007fe9  mov     rax, qword ptr cs:CLSID_ASFContentEncryptionObjectv1.Data1
0x180007ff0  sub     rax, [rbx]
0x180007ff3  jnz     short loc_180008000
0x180007ff5  mov     rax, qword ptr cs:CLSID_ASFContentEncryptionObjectv1.Data4
0x180007ffc  sub     rax, [rbx+8]
0x180008000  test    rax, rax
0x180008003  jnz     short loc_180008025
0x180008005  mov     ecx, 90h; Size
0x18000800a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000800f  test    rax, rax
0x180008012  jz      loc_180008970
0x180008018  mov     rcx, rax; this
0x18000801b  call    ??0CASFContentEncryptionObjectv1@@QEAA@XZ; CASFContentEncryptionObjectv1::CASFContentEncryptionObjectv1(void)
0x180008020  jmp     loc_180007D85
0x180008025  mov     rax, qword ptr cs:CLSID_ASFContentEncryptionObject.Data1
0x18000802c  sub     rax, [rbx]
0x18000802f  jnz     short loc_18000803C
0x180008031  mov     rax, qword ptr cs:CLSID_ASFContentEncryptionObject.Data4
0x180008038  sub     rax, [rbx+8]
0x18000803c  test    rax, rax
0x18000803f  jnz     short loc_18000805F
0x180008041  lea     ecx, [rax+68h]; Size
0x180008044  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008049  test    rax, rax
0x18000804c  jz      loc_180008970
0x180008052  mov     rcx, rax; this
0x180008055  call    ??0CASFContentEncryptionObjectv2@@QEAA@XZ; CASFContentEncryptionObjectv2::CASFContentEncryptionObjectv2(void)
0x18000805a  jmp     loc_180007D85
0x18000805f  mov     rax, qword ptr cs:CLSID_ASFContentEncryptionObjectExv1.Data1
0x180008066  sub     rax, [rbx]
0x180008069  jnz     short loc_180008076
0x18000806b  mov     rax, qword ptr cs:CLSID_ASFContentEncryptionObjectExv1.Data4
0x180008072  sub     rax, [rbx+8]
0x180008076  test    rax, rax
0x180008079  jnz     short loc_180008099
0x18000807b  lea     ecx, [rax+68h]; Size
0x18000807e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008083  test    rax, rax
0x180008086  jz      loc_180008970
0x18000808c  mov     rcx, rax; this
0x18000808f  call    ??0CASFContentEncryptionObjectExv1@@QEAA@XZ; CASFContentEncryptionObjectExv1::CASFContentEncryptionObjectExv1(void)
0x180008094  jmp     loc_180007D85
0x180008099  mov     rax, qword ptr cs:CLSID_ASFContentEncryptionObjectExv2.Data1
0x1800080a0  sub     rax, [rbx]
0x1800080a3  jnz     short loc_1800080B0
0x1800080a5  mov     rax, qword ptr cs:CLSID_ASFContentEncryptionObjectExv2.Data4
0x1800080ac  sub     rax, [rbx+8]
0x1800080b0  test    rax, rax
0x1800080b3  jnz     short loc_1800080D3
0x1800080b5  lea     ecx, [rax+68h]; Size
0x1800080b8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800080bd  test    rax, rax
0x1800080c0  jz      loc_180008970
0x1800080c6  mov     rcx, rax; this
0x1800080c9  call    ??0CASFContentEncryptionObjectExv2@@QEAA@XZ; CASFContentEncryptionObjectExv2::CASFContentEncryptionObjectExv2(void)
0x1800080ce  jmp     loc_180007D85
0x1800080d3  mov     rax, qword ptr cs:CLSID_ASFDataObject.Data1
0x1800080da  sub     rax, [rbx]
0x1800080dd  jnz     short loc_1800080EA
0x1800080df  mov     rax, qword ptr cs:CLSID_ASFDataObject.Data4
0x1800080e6  sub     rax, [rbx+8]
0x1800080ea  test    rax, rax
0x1800080ed  jnz     short loc_18000810F
0x1800080ef  mov     ecx, 138h; Size
0x1800080f4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800080f9  test    rax, rax
0x1800080fc  jz      loc_180008970
0x180008102  mov     rcx, rax; this
0x180008105  call    ??0CASFDataObjectv2@@QEAA@XZ; CASFDataObjectv2::CASFDataObjectv2(void)
0x18000810a  jmp     loc_180007D85
0x18000810f  mov     rax, qword ptr cs:CLSID_ASFDataObjectv1.Data1
0x180008116  sub     rax, [rbx]
0x180008119  jnz     short loc_180008126
0x18000811b  mov     rax, qword ptr cs:CLSID_ASFDataObjectv1.Data4
0x180008122  sub     rax, [rbx+8]
0x180008126  test    rax, rax
0x180008129  jnz     short loc_18000814B
0x18000812b  mov     ecx, 160h; Size
0x180008130  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008135  test    rax, rax
0x180008138  jz      loc_180008970
0x18000813e  mov     rcx, rax; this
0x180008141  call    ??0CASFDataObjectv1@@QEAA@XZ; CASFDataObjectv1::CASFDataObjectv1(void)
0x180008146  jmp     loc_180007D85
0x18000814b  mov     rax, qword ptr cs:CLSID_ASFDataUnitExtensionObject.Data1
0x180008152  sub     rax, [rbx]
0x180008155  jnz     short loc_180008162
0x180008157  mov     rax, qword ptr cs:CLSID_ASFDataUnitExtensionObject.Data4
0x18000815e  sub     rax, [rbx+8]
0x180008162  test    rax, rax
0x180008165  jnz     short loc_180008185
0x180008167  lea     ecx, [rax+78h]; Size
0x18000816a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000816f  test    rax, rax
0x180008172  jz      loc_180008970
  ... truncated ...
```
