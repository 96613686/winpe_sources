# UnionFs::UnionFsFilter::InstanceSetupInternal(_FLT_RELATED_OBJECTS const *,ulong,ulong,_FLT_FILESYSTEM_TYPE)

- ea: `0x14000b1e8`
- end: `0x14000bd5a`
- name: `?InstanceSetupInternal@UnionFsFilter@UnionFs@@CAJPEBU_FLT_RELATED_OBJECTS@@KKW4_FLT_FILESYSTEM_TYPE@@@Z`
- size: `2930`
- prototype: `__int64 __fastcall(const struct _FLT_RELATED_OBJECTS *, unsigned int, unsigned int, enum _FLT_FILESYSTEM_TYPE)`
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, installer_update`

## callers

- `0x14000b0c0`

## callees

- `0x140001008`
- `0x14000110c`
- `0x140001220`
- `0x140001344`
- `0x14000147c`
- `0x1400055d0`
- `0x140006168`
- `0x140008b0c`
- `0x14000b1e8`
- `0x14000fe8c`
- `0x140026920`
- `0x140027764`
- `0x140056bd0`
- `0x140056c44`
- `0x140056c7c`
- `0x140079f68`
- `0x14007baf0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14000b2db`
- `ntoskrnl!ObfDereferenceObject` at `0x14000b324`
- `ntoskrnl!ObfDereferenceObject` at `0x14000b353`
- `ntoskrnl!ObfDereferenceObject` at `0x14000b2db`
- `ntoskrnl!ObfDereferenceObject` at `0x14000b324`
- `ntoskrnl!ObfDereferenceObject` at `0x14000b353`
- `ntoskrnl!IoMountBootLayer` at `0x14000b506`
- `ntoskrnl!IoMountBootLayer` at `0x14000b506`
- `FLTMGR!FltIsVolumeSnapshot` at `0x14000b769`
- `FLTMGR!FltIsVolumeSnapshot` at `0x14000b769`
- `FLTMGR!FltSetInstanceContext` at `0x14000ba3b`
- `FLTMGR!FltSetInstanceContext` at `0x14000ba3b`
- `FLTMGR!FltGetDiskDeviceObject` at `0x14000b2b4`
- `FLTMGR!FltGetDiskDeviceObject` at `0x14000b2b4`
- `FLTMGR!FltAttachVolume` at `0x14000b54b`
- `FLTMGR!FltAttachVolume` at `0x14000b54b`
- `FLTMGR!FltGetVolumeFromName` at `0x14000b522`
- `FLTMGR!FltGetVolumeFromName` at `0x14000b522`
- `FLTMGR!FltReferenceContext` at `0x14000b582`
- `FLTMGR!FltReferenceContext` at `0x14000bb4c`
- `FLTMGR!FltReferenceContext` at `0x14000b582`
- `FLTMGR!FltReferenceContext` at `0x14000bb4c`
- `FLTMGR!FltReleaseContext` at `0x14000b3d6`
- `FLTMGR!FltReleaseContext` at `0x14000b5ac`
- `FLTMGR!FltReleaseContext` at `0x14000b5c0`
- `FLTMGR!FltReleaseContext` at `0x14000b9ff`
- `FLTMGR!FltReleaseContext` at `0x14000ba66`
- `FLTMGR!FltReleaseContext` at `0x14000bac8`
- `FLTMGR!FltReleaseContext` at `0x14000bb01`
- `FLTMGR!FltReleaseContext` at `0x14000bb32`
- `FLTMGR!FltReleaseContext` at `0x14000bb71`
- `FLTMGR!FltReleaseContext` at `0x14000bc70`
- `FLTMGR!FltReleaseContext` at `0x14000b3d6`
- `FLTMGR!FltReleaseContext` at `0x14000b5ac`
- `FLTMGR!FltReleaseContext` at `0x14000b5c0`
- `FLTMGR!FltReleaseContext` at `0x14000b9ff`
- `FLTMGR!FltReleaseContext` at `0x14000ba66`
- `FLTMGR!FltReleaseContext` at `0x14000bac8`
- `FLTMGR!FltReleaseContext` at `0x14000bb01`
- `FLTMGR!FltReleaseContext` at `0x14000bb32`
- `FLTMGR!FltReleaseContext` at `0x14000bb71`
- `FLTMGR!FltReleaseContext` at `0x14000bc70`
- `FLTMGR!FltObjectDereference` at `0x14000b5d5`
- `FLTMGR!FltObjectDereference` at `0x14000b5ea`
- `FLTMGR!FltObjectDereference` at `0x14000b700`
- `FLTMGR!FltObjectDereference` at `0x14000b73f`
- `FLTMGR!FltObjectDereference` at `0x14000b5d5`
- `FLTMGR!FltObjectDereference` at `0x14000b5ea`
- `FLTMGR!FltObjectDereference` at `0x14000b700`
- `FLTMGR!FltObjectDereference` at `0x14000b73f`

## string_xrefs

- `0x14000b93a`: `Attempting to attach`
- `0x14000bb9b`: `PUSH: CreateBootUnion`

## pseudocode

```c
__int64 __fastcall UnionFs::UnionFsFilter::InstanceSetupInternal(
        const struct _FLT_RELATED_OBJECTS *a1,
        int a2,
        unsigned int a3,
        unsigned int a4)
{
  unsigned int v5; // r14d
  int v6; // esi
  int v8; // eax
  int v9; // r8d
  int v10; // r9d
  char v11; // dl
  char v12; // di
  struct _FLT_VOLUME *Volume; // rcx
  NTSTATUS v14; // edi
  PVOID v15; // rcx
  PVOID v16; // rcx
  PVOID v17; // rcx
  _QWORD *v18; // rsi
  __int64 v19; // rbx
  __int64 v20; // rcx
  unsigned __int64 v21; // r14
  unsigned __int64 v22; // r15
  __int64 v23; // r14
  __int64 v24; // rbx
  void *v25; // rcx
  unsigned __int64 v26; // rdx
  __int64 v27; // rax
  _QWORD *v28; // rdx
  __int64 v29; // r14
  __int64 v30; // rcx
  struct _FLT_FILTER *Filter; // rcx
  NTSTATUS VolumeFromName; // esi
  struct _FLT_FILTER *v33; // rcx
  struct _UNICODE_STRING *v34; // rdx
  void *v35; // rcx
  struct _UNICODE_STRING *v36; // rdx
  PFLT_VOLUME v37; // rcx
  NTSTATUS IsVolumeSnapshot; // edx
  int v39; // r8d
  int v40; // r9d
  struct _FLT_VOLUME *v41; // rdx
  struct _FLT_INSTANCE *v42; // rcx
  PFLT_CONTEXT v43; // rsi
  struct _FLT_INSTANCE *v44; // rcx
  int v45; // r8d
  int v46; // r9d
  NTSTATUS BootUnion; // r14d
  PVOID v48; // rcx
  PFLT_CONTEXT v49; // rcx
  const char *v50; // rax
  __int64 v51; // r8
  PFLT_CONTEXT v52; // rcx
  PFLT_CONTEXT v53; // rax
  void **v54; // rdx
  void *v55; // rcx
  char *v57; // [rsp+28h] [rbp-D8h]
  char v58; // [rsp+60h] [rbp-A0h]
  unsigned __int8 IsSnapshotVolume[7]; // [rsp+61h] [rbp-9Fh] BYREF
  PFLT_CONTEXT Context; // [rsp+68h] [rbp-98h] BYREF
  PFLT_CONTEXT NewContext; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v62; // [rsp+78h] [rbp-88h] BYREF
  const char *v63; // [rsp+80h] [rbp-80h] BYREF
  const char *v64; // [rsp+88h] [rbp-78h] BYREF
  char v65[8]; // [rsp+90h] [rbp-70h] BYREF
  const char *v66; // [rsp+98h] [rbp-68h] BYREF
  int v67; // [rsp+A0h] [rbp-60h]
  int v68; // [rsp+A4h] [rbp-5Ch] BYREF
  PVOID Object; // [rsp+A8h] [rbp-58h] BYREF
  PFLT_VOLUME RetVolume; // [rsp+B0h] [rbp-50h] BYREF
  PFLT_INSTANCE RetInstance; // [rsp+B8h] [rbp-48h] BYREF
  PVOID *p_Object; // [rsp+C0h] [rbp-40h]
  PDEVICE_OBJECT DiskDeviceObject; // [rsp+C8h] [rbp-38h] BYREF
  char v74; // [rsp+D0h] [rbp-30h]
  UNICODE_STRING VolumeName; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v76; // [rsp+E8h] [rbp-18h] BYREF
  PFLT_INSTANCE Instance; // [rsp+F8h] [rbp-8h]
  int v78[188]; // [rsp+100h] [rbp+0h] BYREF

  v62 = a3;
  v67 = a2;
  v5 = a3;
  v6 = a2;
  if ( a4 <= 0x1E )
  {
    v8 = 1342177284;
    if ( _bittest(&v8, a4) )
    {
      UnionFs::StackEventTracer::StackEventTracer((UnionFs::StackEventTracer *)v78, 0x500010459uLL);
      v11 = 0;
      v12 = 0;
      v58 = 0;
      if ( !*((_BYTE *)UnionFs::g_FilterState + 136) && (v6 & 1) != 0 && *((_BYTE *)UnionFs::g_FilterState + 200) )
      {
        Volume = a1->Volume;
        p_Object = &Object;
        Object = 0;
        DiskDeviceObject = 0;
        v74 = 1;
        v14 = FltGetDiskDeviceObject(Volume, &DiskDeviceObject);
        if ( v74 )
        {
          v9 = (int)p_Object;
          v15 = *p_Object;
          *p_Object = DiskDeviceObject;
          if ( v15 )
            ObfDereferenceObject(v15);
        }
        if ( v14 < 0 )
        {
          UnionFs::ProcessTraceStatusFromApi(
            (UnionFs *)(unsigned int)v14,
            (int)v78,
            (struct UnionFs::StackEventTracer *)0x8700010465LL,
            (unsigned __int64)"UnionFs::UnionFsFilter::InstanceSetupInternal",
            "API: FltGetDiskDeviceObject",
            v57);
          v16 = Object;
          Object = 0;
          if ( v16 )
            ObfDereferenceObject(v16);
          goto LABEL_106;
        }
        v17 = Object;
        v12 = BYTE1(*((_DWORD *)Object + 12)) & 1;
        Object = 0;
        v11 = v12;
        v58 = v12;
        if ( v17 )
        {
          ObfDereferenceObject(v17);
          v11 = v12;
        }
      }
      if ( !*((_BYTE *)UnionFs::g_FilterState + 136) && v11 )
      {
        v18 = (char *)UnionFs::g_FilterState + 144;
        v19 = *((_QWORD *)UnionFs::g_FilterState + 19);
        v20 = *((_QWORD *)UnionFs::g_FilterState + 18);
        v21 = (unsigned int)(*(_DWORD *)(*((_QWORD *)UnionFs::g_FilterState + 26) + 24LL) + 1);
        v22 = (v19 - v20) >> 3;
        if ( v21 > v22 )
        {
          if ( v21 > (*((_QWORD *)UnionFs::g_FilterState + 20) - v20) >> 3 )
          {
            v26 = 7 * ((unsigned __int64)((*((_QWORD *)UnionFs::g_FilterState + 20) - v20) >> 3) >> 2) + 8;
            if ( v26 < v21 )
              v26 = (unsigned int)(*(_DWORD *)(*((_QWORD *)UnionFs::g_FilterState + 26) + 24LL) + 1);
            if ( v26 > 0xFFFFFFFFFFFFFFFLL )
              v26 = 0xFFFFFFFFFFFFFFFLL;
            if ( v21 > v26
              || !(unsigned __int8)utl::vector<wistd::unique_ptr<UnionFs::UfsInstanceCtx,wil::function_deleter<void (*)(void *),&void FltReleaseContext(void *)>>,utl::allocator<wistd::unique_ptr<UnionFs::UfsInstanceCtx,wil::function_deleter<void (*)(void *),&void FltReleaseContext(void *)>>>>::_SetCapacity((char *)UnionFs::g_FilterState + 144) )
            {
              v14 = -1073741670;
              UnionFs::ProcessTraceStatusOrigin(
                (UnionFs *)0xC000009ALL,
                (int)v78,
                (struct UnionFs::StackEventTracer *)0x5E50001047BLL,
                (unsigned __int64)"UnionFs::UnionFsFilter::InstanceSetupInternal",
                "ORIGIN: Allocating boot layer contexts",
                v57);
LABEL_106:
              UnionFs::StackEventTracer::~StackEventTracer((UnionFs::StackEventTracer *)v78);
              return (unsigned int)v14;
            }
            v19 = v18[1];
          }
          v27 = 0;
          if ( v21 != v22 )
          {
            do
              *(_QWORD *)(v19 + 8 * v27++) = 0;
            while ( v27 != v21 - v22 );
          }
          v18[1] = *v18 + 8 * v21;
        }
        else
        {
          v23 = v20 + 8 * v21;
          *((_QWORD *)UnionFs::g_FilterState + 19) = v23;
          v24 = (v19 - v23) >> 3;
          while ( v24 )
          {
            --v24;
            v25 = *(void **)(v23 + 8 * v24);
            *(_QWORD *)(v23 + 8 * v24) = 0;
            if ( v25 )
              FltReleaseContext(v25);
          }
        }
        v28 = UnionFs::g_FilterState;
        Instance = 0;
        v76 = 0;
        LODWORD(v29) = 0;
        v30 = *(_QWORD *)(*((_QWORD *)UnionFs::g_FilterState + 26) + 8LL);
        *((_QWORD *)&v76 + 1) = a1->Filter;
        Instance = a1->Instance;
        *(_QWORD *)&v76 = v30;
        if ( *(_DWORD *)(*((_QWORD *)UnionFs::g_FilterState + 26) + 24LL) )
        {
          while ( 1 )
          {
            VolumeName = 0;
            IoMountBootLayer(*(_QWORD *)(*(_QWORD *)(v28[26] + 16LL) + 24LL * (unsigned int)v29), &v76, &VolumeName);
            Filter = a1->Filter;
            RetVolume = 0;
            VolumeFromName = FltGetVolumeFromName(Filter, &VolumeName, &RetVolume);
            if ( VolumeFromName < 0 )
            {
              UnionFs::ProcessTraceStatusFromApi(
                (UnionFs *)(unsigned int)VolumeFromName,
                (int)v78,
                (struct UnionFs::StackEventTracer *)0xB400010491LL,
                (unsigned __int64)"UnionFs::UnionFsFilter::InstanceSetupInternal",
                "API: FltGetVolumeFromName",
                v57);
              goto LABEL_55;
            }
            v33 = a1->Filter;
            RetInstance = 0;
            VolumeFromName = FltAttachVolume(v33, RetVolume, 0, &RetInstance);
            if ( VolumeFromName < 0 )
              break;
            Context = 0;
            UnionFs::UfsInstanceCtx::FltGet(RetInstance);
            FltReferenceContext(0);
            v29 = (unsigned int)(v29 + 1);
            v34 = (struct _UNICODE_STRING *)*((_QWORD *)UnionFs::g_FilterState + 18);
            v35 = (void *)*((_QWORD *)&v34->Length + v29);
            *((_QWORD *)&v34->Length + v29) = 0;
            if ( v35 )
              FltReleaseContext(v35);
            if ( RetInstance )
              FltObjectDereference(RetInstance);
            if ( RetVolume )
              FltObjectDereference(RetVolume);
            FsFltWil::Details::FreeUnicodeString(&VolumeName, v34);
            v28 = UnionFs::g_FilterState;
            if ( (unsigned int)v29 >= *(_DWORD *)(*((_QWORD *)UnionFs::g_FilterState + 26) + 24LL) )
              goto LABEL_45;
          }
          UnionFs::ProcessTraceStatusFromApi(
            (UnionFs *)(unsigned int)VolumeFromName,
            (int)v78,
            (struct UnionFs::StackEventTracer *)0xB500010497LL,
            (unsigned __int64)"UnionFs::UnionFsFilter::InstanceSetupInternal",
            "API: FltAttachVolume",
            v57);
          if ( RetInstance )
            FltObjectDereference(RetInstance);
LABEL_55:
          if ( RetVolume )
            FltObjectDereference(RetVolume);
          FsFltWil::Details::FreeUnicodeString(&VolumeName, v36);
          goto LABEL_58;
        }
LABEL_45:
        v5 = v62;
        v6 = v67;
      }
      if ( !v12 && (v6 & 2) == 0 )
      {
        if ( (unsigned int)dword_14009E178 > 5
          && (qword_14009E188 & 0x80u) != 0LL
          && (qword_14009E190 & 0x80) == qword_14009E190 )
        {
          v62 = 1259;
          v63 = "No auto-attach and manual attach not requested.";
          Context = "onecore\\base\\fs\\unionfs\\sys\\unionfsfilter.cpp";
          NewContext = (PFLT_CONTEXT)"UnionFs::UnionFsFilter::InstanceSetupInternal";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            qword_14009E190,
            (unsigned int)qword_140095CD0,
            v9,
            v10,
            (__int64)&v63,
            (__int64)&NewContext,
            (__int64)&Context,
            (__int64)&v62);
        }
LABEL_70:
        v14 = -1071906801;
        goto LABEL_106;
      }
      v37 = a1->Volume;
      IsSnapshotVolume[0] = 0;
      IsVolumeSnapshot = FltIsVolumeSnapshot(v37, IsSnapshotVolume);
      if ( (int)(IsVolumeSnapshot + 0x80000000) >= 0
        && IsVolumeSnapshot != -1071906791
        && (unsigned int)dword_14009E178 > 3
        && (qword_14009E188 & 0x80) != 0
        && (qword_14009E190 & 0x80) == qword_14009E190 )
      {
        LODWORD(NewContext) = IsVolumeSnapshot;
        v66 = "Unexpected FltIsVolumeSnapshot failure";
        v62 = a4;
        v68 = v5;
        LODWORD(v63) = v6;
        LODWORD(Context) = 1198;
        v64 = "onecore\\base\\fs\\unionfs\\sys\\unionfsfilter.cpp";
        *(_QWORD *)v65 = "UnionFs::UnionFsFilter::InstanceSetupInternal";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          qword_14009E190,
          (unsigned int)&dword_140095BD4,
          v39,
          v40,
          (__int64)&v66,
          (__int64)v65,
          (__int64)&v64,
          (__int64)&Context,
          (__int64)&NewContext,
          (__int64)&v63,
          (__int64)&v68,
          (__int64)&v62);
      }
      if ( IsSnapshotVolume[0] )
      {
        if ( (unsigned int)dword_14009E178 > 5
          && (qword_14009E188 & 0x80) != 0
          && (qword_14009E190 & 0x80) == qword_14009E190 )
        {
          LODWORD(Context) = a4;
          v64 = "Not attaching to snapshot volume";
          LODWORD(NewContext) = v5;
          LODWORD(v63) = v6;
          v68 = 1210;
          v66 = "onecore\\base\\fs\\unionfs\\sys\\unionfsfilter.cpp";
          *(_QWORD *)v65 = "UnionFs::UnionFsFilter::InstanceSetupInternal";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            qword_14009E190,
            (unsigned int)word_140095752,
            v39,
            v40,
            (__int64)&v64,
            (__int64)v65,
            (__int64)&v66,
            (__int64)&v68,
            (__int64)&v63,
            (__int64)&NewContext,
            (__int64)&Context);
        }
        goto LABEL_70;
      }
      if ( (unsigned int)dword_14009E178 > 4
        && (qword_14009E188 & 0x80) != 0
        && (qword_14009E190 & 0x80) == qword_14009E190 )
      {
        LODWORD(Context) = a4;
        v64 = "Attempting to attach";
        LODWORD(NewContext) = v6;
        LODWORD(v63) = 1219;
        v66 = "onecore\\base\\fs\\unionfs\\sys\\unionfsfilter.cpp";
        *(_QWORD *)v65 = "UnionFs::UnionFsFilter::InstanceSetupInternal";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          qword_14009E190,
          (unsigned int)&byte_14009514F,
          v39,
          v40,
          (__int64)&v64,
          (__int64)v65,
          (__int64)&v66,
          (__int64)&v63,
          (__int64)&NewContext,
          (__int64)&Context);
      }
      v41 = a1->Volume;
      v42 = a1->Instance;
      NewContext = 0;
      VolumeFromName = UnionFs::UfsInstanceCtx::FltAllocAndInit(v42, v41, (int)v78);
      if ( VolumeFromName < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)VolumeFromName,
          (int)v78,
          (struct UnionFs::StackEventTracer *)0x7000104CELL,
          (unsigned __int64)"UnionFs::UnionFsFilter::InstanceSetupInternal",
          "PUSH: Allocating instance context",
          v57);
        if ( NewContext )
          FltReleaseContext(NewContext);
LABEL_58:
        v14 = VolumeFromName;
        goto LABEL_106;
      }
      v43 = NewContext;
      v44 = a1->Instance;
      Context = 0;
      p_Object = &Context;
      DiskDeviceObject = 0;
      v74 = 1;
      BootUnion = FltSetInstanceContext(
                    v44,
                    FLT_SET_CONTEXT_KEEP_IF_EXISTS,
                    NewContext,
                    (PFLT_CONTEXT *)&DiskDeviceObject);
      if ( v74 )
      {
        v45 = (int)p_Object;
        v48 = *p_Object;
        *p_Object = DiskDeviceObject;
        if ( v48 )
          FltReleaseContext(v48);
      }
      if ( (int)(BootUnion + 0x80000000) >= 0 && BootUnion != -1071906814 )
      {
        UnionFs::ProcessTraceStatusFromApi(
          (UnionFs *)(unsigned int)BootUnion,
          (int)v78,
          (struct UnionFs::StackEventTracer *)0xB000A00EBLL,
          (unsigned __int64)"UnionFs::UfsInstanceCtx::FltSet",
          "API: Attaching instance context",
          v57);
        v49 = Context;
        Context = 0;
        if ( v49 )
          FltReleaseContext(v49);
        v50 = "PUSH: Setting instance context";
        v51 = 0x8000104D4LL;
        goto LABEL_86;
      }
      v52 = Context;
      if ( Context )
      {
        v53 = v43;
        v43 = Context;
        v52 = v53;
      }
      Context = 0;
      if ( v52 )
        FltReleaseContext(v52);
      if ( v58 )
      {
        FltReferenceContext(v43);
        v54 = (void **)*((_QWORD *)UnionFs::g_FilterState + 18);
        v55 = *v54;
        *v54 = v43;
        if ( v55 )
          FltReleaseContext(v55);
        BootUnion = UnionFs::UnionFsFilter::CreateBootUnion(v55, (char *)UnionFs::g_FilterState + 144, v78);
        if ( BootUnion < 0 )
        {
          v50 = "PUSH: CreateBootUnion";
          v51 = 0x88000104DDLL;
LABEL_86:
          UnionFs::ProcessTraceStatusPushLocation(
            (UnionFs *)(unsigned int)BootUnion,
            (int)v78,
            (struct UnionFs::StackEventTracer *)v51,
            (unsigned __int64)"UnionFs::UnionFsFilter::InstanceSetupInternal",
            v50,
            v57);
          if ( v43 )
            FltReleaseContext(v43);
          v14 = BootUnion;
          goto LABEL_106;
        }
        *((_BYTE *)UnionFs::g_FilterState + 136) = 1;
        _mm_mfence();
        *((_QWORD *)UnionFs::g_FilterState + 26) = 0;
      }
      if ( (unsigned int)dword_14009E178 > 4
        && (qword_14009E188 & 0x80) != 0
        && (qword_14009E190 & 0x80) == qword_14009E190 )
      {
        LODWORD(NewContext) = v67;
        v64 = "Will attach to volume.";
        LODWORD(Context) = a4;
        LODWORD(v63) = 1254;
        v66 = "onecore\\base\\fs\\unionfs\\sys\\unionfsfilter.cpp";
        *(_QWORD *)v65 = "UnionFs::UnionFsFilter::InstanceSetupInternal";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          qword_14009E190,
          (unsigned int)&byte_14009552F,
          v45,
          v46,
          (__int64)&v64,
          (__int64)v65,
          (__int64)&v66,
          (__int64)&v63,
          (__int64)&NewContext,
          (__int64)&Context);
      }
      if ( v43 )
        FltReleaseContext(v43);
      v14 = 0;
      goto LABEL_106;
    }
  }
  if ( (unsigned int)dword_14009E178 > 5
    && (qword_14009E188 & 0x80u) != 0LL
    && (qword_14009E190 & 0x80) == qword_14009E190 )
  {
    LODWORD(Context) = a4;
    v64 = "Not attaching to unsupported file system type";
    LODWORD(NewContext) = 1109;
    v66 = "onecore\\base\\fs\\unionfs\\sys\\unionfsfilter.cpp";
    *(_QWORD *)v65 = "UnionFs::UnionFsFilter::InstanceSetupInternal";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      qword_14009E190,
      (unsigned int)&byte_1400959AF,
      a3,
      a4,
      (__int64)&v64,
      (__int64)v65,
      (__int64)&v66,
      (__int64)&NewContext,
      (__int64)&Context);
  }
  return 3223060495LL;
}

```

## disassembly

```asm
0x14000b1e8  mov     [rsp-8+arg_8], rbx
0x14000b1ed  push    rbp
0x14000b1ee  push    rsi
0x14000b1ef  push    rdi
0x14000b1f0  push    r12
0x14000b1f2  push    r13
0x14000b1f4  push    r14
0x14000b1f6  push    r15
0x14000b1f8  lea     rbp, [rsp-300h]
0x14000b200  sub     rsp, 400h
0x14000b207  mov     rax, cs:__security_cookie
0x14000b20e  xor     rax, rsp
0x14000b211  mov     [rbp+330h+var_40], rax
0x14000b218  mov     [rsp+430h+var_3B8], r8d
0x14000b21d  mov     r12d, r9d
0x14000b220  mov     [rbp+330h+var_390], edx
0x14000b223  mov     r14d, r8d
0x14000b226  mov     esi, edx
0x14000b228  mov     r13, rcx
0x14000b22b  cmp     r9d, 1Eh
0x14000b22f  ja      loc_14000BC8F
0x14000b235  mov     eax, 50000004h
0x14000b23a  bt      eax, r9d
0x14000b23e  jnb     loc_14000BC8F
0x14000b244  mov     rdx, 500010459h; unsigned __int64
0x14000b24e  lea     rcx, [rbp+330h+var_330]; this
0x14000b252  call    ??0StackEventTracer@UnionFs@@QEAA@_K@Z; UnionFs::StackEventTracer::StackEventTracer(unsigned __int64)
0x14000b257  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14000b25e  xor     r15d, r15d
0x14000b261  mov     dl, r15b
0x14000b264  mov     dil, r15b
0x14000b267  mov     [rsp+430h+var_3D0], dl
0x14000b26b  mov     cl, [rax+88h]
0x14000b271  nop
0x14000b272  test    cl, cl
0x14000b274  jnz     loc_14000B362
0x14000b27a  test    sil, 1
0x14000b27e  jz      loc_14000B362
0x14000b284  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14000b28b  cmp     [rax+0C8h], r15b
0x14000b292  jz      loc_14000B362
0x14000b298  mov     rcx, [r13+10h]; Volume
0x14000b29c  lea     rax, [rbp+330h+Object]
0x14000b2a0  lea     rdx, [rbp+330h+DiskDeviceObject]; DiskDeviceObject
0x14000b2a4  mov     [rbp+330h+var_370], rax
0x14000b2a8  mov     [rbp+330h+Object], r15
0x14000b2ac  mov     [rbp+330h+DiskDeviceObject], r15
0x14000b2b0  mov     [rbp+330h+var_360], 1
0x14000b2b4  call    cs:__imp_FltGetDiskDeviceObject
0x14000b2bb  nop     dword ptr [rax+rax+00h]
0x14000b2c0  mov     edi, eax
0x14000b2c2  cmp     [rbp+330h+var_360], r15b
0x14000b2c6  jz      short loc_14000B2E7
0x14000b2c8  mov     r8, [rbp+330h+var_370]
0x14000b2cc  mov     rdx, [rbp+330h+DiskDeviceObject]
0x14000b2d0  mov     rcx, [r8]; Object
0x14000b2d3  mov     [r8], rdx
0x14000b2d6  test    rcx, rcx
0x14000b2d9  jz      short loc_14000B2E7
0x14000b2db  call    cs:__imp_ObfDereferenceObject
0x14000b2e2  nop     dword ptr [rax+rax+00h]
0x14000b2e7  test    edi, edi
0x14000b2e9  jns     short loc_14000B335
0x14000b2eb  lea     rax, aApiFltgetdiskd; "API: FltGetDiskDeviceObject"
0x14000b2f2  mov     r8, 8700010465h; struct UnionFs::StackEventTracer *
0x14000b2fc  lea     r9, aUnionfsUnionfs_64; "UnionFs::UnionFsFilter::InstanceSetupIn"...
0x14000b303  mov     [rsp+430h+var_410], rax; char *
0x14000b308  lea     rdx, [rbp+330h+var_330]; int
0x14000b30c  mov     ecx, edi; this
0x14000b30e  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14000b313  mov     rcx, [rbp+330h+Object]; Object
0x14000b317  mov     [rbp+330h+Object], r15
0x14000b31b  test    rcx, rcx
0x14000b31e  jz      loc_14000BC7F
0x14000b324  call    cs:__imp_ObfDereferenceObject
0x14000b32b  nop     dword ptr [rax+rax+00h]
0x14000b330  jmp     loc_14000BC7F
0x14000b335  mov     rcx, [rbp+330h+Object]; Object
0x14000b339  mov     edi, [rcx+30h]
0x14000b33c  shr     edi, 8
0x14000b33f  and     dil, 1
0x14000b343  mov     [rbp+330h+Object], r15
0x14000b347  mov     dl, dil
0x14000b34a  mov     [rsp+430h+var_3D0], dl
0x14000b34e  test    rcx, rcx
0x14000b351  jz      short loc_14000B362
0x14000b353  call    cs:__imp_ObfDereferenceObject
0x14000b35a  nop     dword ptr [rax+rax+00h]
0x14000b35f  mov     dl, dil
0x14000b362  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14000b369  mov     cl, [rax+88h]
0x14000b36f  nop
0x14000b370  test    cl, cl
0x14000b372  jnz     loc_14000B61F
0x14000b378  test    dl, dl
0x14000b37a  jz      loc_14000B61F
0x14000b380  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14000b387  lea     rsi, [rax+90h]
0x14000b38e  mov     rax, [rax+0D0h]
0x14000b395  mov     rbx, [rsi+8]
0x14000b399  mov     rcx, [rsi]
0x14000b39c  mov     r15, rbx
0x14000b39f  sub     r15, rcx
0x14000b3a2  mov     r14d, [rax+18h]
0x14000b3a6  inc     r14d
0x14000b3a9  sar     r15, 3
0x14000b3ad  cmp     r14, r15
0x14000b3b0  ja      short loc_14000B3EC
0x14000b3b2  lea     r14, [rcx+r14*8]
0x14000b3b6  sub     rbx, r14
0x14000b3b9  mov     [rsi+8], r14
0x14000b3bd  sar     rbx, 3
0x14000b3c1  xor     r15d, r15d
0x14000b3c4  jmp     short loc_14000B3E2
0x14000b3c6  dec     rbx
0x14000b3c9  mov     rcx, [r14+rbx*8]; Context
0x14000b3cd  mov     [r14+rbx*8], r15
0x14000b3d1  test    rcx, rcx
0x14000b3d4  jz      short loc_14000B3E2
0x14000b3d6  call    cs:__imp_FltReleaseContext
0x14000b3dd  nop     dword ptr [rax+rax+00h]
0x14000b3e2  test    rbx, rbx
0x14000b3e5  jnz     short loc_14000B3C6
0x14000b3e7  jmp     loc_14000B49A
0x14000b3ec  mov     rdx, [rsi+10h]
0x14000b3f0  mov     rax, rdx
0x14000b3f3  sub     rax, rcx
0x14000b3f6  sar     rax, 3
0x14000b3fa  cmp     r14, rax
0x14000b3fd  jbe     short loc_14000B43F
0x14000b3ff  sub     rdx, rcx
0x14000b402  mov     rax, 0FFFFFFFFFFFFFFFh
0x14000b40c  sar     rdx, 3
0x14000b410  shr     rdx, 2
0x14000b414  imul    rdx, 7
0x14000b418  add     rdx, 8
0x14000b41c  cmp     rdx, r14
0x14000b41f  cmovb   rdx, r14
0x14000b423  cmp     rdx, rax
0x14000b426  cmova   rdx, rax
0x14000b42a  cmp     r14, rdx
0x14000b42d  ja      short loc_14000B45A
0x14000b42f  mov     rcx, rsi
0x14000b432  call    ?_SetCapacity@?$vector@V?$unique_ptr@VUfsInstanceCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@V?$allocator@V?$unique_ptr@VUfsInstanceCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@@utl@@@utl@@AEAA_N_K@Z; utl::vector<wistd::unique_ptr<UnionFs::UfsInstanceCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>>,utl::allocator<wistd::unique_ptr<UnionFs::UfsInstanceCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>>>>::_SetCapacity(unsigned __int64)
0x14000b437  test    al, al
0x14000b439  jz      short loc_14000B45A
0x14000b43b  mov     rbx, [rsi+8]
0x14000b43f  xor     eax, eax
0x14000b441  mov     rcx, r14
0x14000b444  sub     rcx, r15
0x14000b447  jz      short loc_14000B48C
0x14000b449  xor     r15d, r15d
0x14000b44c  mov     [rbx+rax*8], r15
0x14000b450  inc     rax
0x14000b453  cmp     rax, rcx
0x14000b456  jnz     short loc_14000B44C
0x14000b458  jmp     short loc_14000B48F
0x14000b45a  lea     rax, aOriginAllocati_1; "ORIGIN: Allocating boot layer contexts"
0x14000b461  mov     edi, 0C000009Ah
0x14000b466  mov     ecx, edi; this
0x14000b468  mov     [rsp+430h+var_410], rax; char *
0x14000b46d  lea     r9, aUnionfsUnionfs_64; "UnionFs::UnionFsFilter::InstanceSetupIn"...
0x14000b474  mov     r8, 5E50001047Bh; struct UnionFs::StackEventTracer *
0x14000b47e  lea     rdx, [rbp+330h+var_330]; int
0x14000b482  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14000b487  jmp     loc_14000BC7F
0x14000b48c  xor     r15d, r15d
0x14000b48f  mov     rax, [rsi]
0x14000b492  lea     rcx, [rax+r14*8]
0x14000b496  mov     [rsi+8], rcx
0x14000b49a  mov     rdx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14000b4a1  xor     eax, eax
0x14000b4a3  mov     [rbp+330h+var_338], rax
0x14000b4a7  xorps   xmm0, xmm0
0x14000b4aa  movups  [rbp+330h+var_348], xmm0
0x14000b4ae  mov     r14d, r15d
0x14000b4b1  mov     rax, [rdx+0D0h]
0x14000b4b8  mov     rcx, [rax+8]
0x14000b4bc  mov     rax, [r13+8]
0x14000b4c0  mov     qword ptr [rbp+330h+var_348+8], rax
0x14000b4c4  mov     rax, [r13+18h]
0x14000b4c8  mov     [rbp+330h+var_338], rax
0x14000b4cc  mov     qword ptr [rbp+330h+var_348], rcx
0x14000b4d0  mov     rax, [rdx+0D0h]
0x14000b4d7  cmp     [rax+18h], r15d
0x14000b4db  jbe     loc_14000B617
0x14000b4e1  xorps   xmm0, xmm0
0x14000b4e4  mov     eax, r14d
0x14000b4e7  movups  xmmword ptr [rbp+330h+VolumeName.Length], xmm0
0x14000b4eb  mov     rdx, [rdx+0D0h]
0x14000b4f2  lea     r8, [rbp+330h+VolumeName]
0x14000b4f6  lea     r9, [rax+rax*2]
0x14000b4fa  mov     rcx, [rdx+10h]
0x14000b4fe  lea     rdx, [rbp+330h+var_348]
0x14000b502  mov     rcx, [rcx+r9*8]
0x14000b506  call    cs:__imp_IoMountBootLayer
0x14000b50d  nop     dword ptr [rax+rax+00h]
0x14000b512  mov     rcx, [r13+8]; Filter
0x14000b516  lea     r8, [rbp+330h+RetVolume]; RetVolume
0x14000b51a  lea     rdx, [rbp+330h+VolumeName]; VolumeName
0x14000b51e  mov     [rbp+330h+RetVolume], r15
0x14000b522  call    cs:__imp_FltGetVolumeFromName
0x14000b529  nop     dword ptr [rax+rax+00h]
0x14000b52e  mov     esi, eax
0x14000b530  test    eax, eax
0x14000b532  js      loc_14000B70E
0x14000b538  mov     rdx, [rbp+330h+RetVolume]; Volume
0x14000b53c  lea     r9, [rbp+330h+RetInstance]; RetInstance
0x14000b540  mov     rcx, [r13+8]; Filter
0x14000b544  xor     r8d, r8d; InstanceName
0x14000b547  mov     [rbp+330h+RetInstance], r15
0x14000b54b  call    cs:__imp_FltAttachVolume
0x14000b552  nop     dword ptr [rax+rax+00h]
0x14000b557  mov     esi, eax
0x14000b559  test    eax, eax
0x14000b55b  js      loc_14000B6CF
0x14000b561  mov     rcx, [rbp+330h+RetInstance]; Instance
0x14000b565  lea     r9, [rbp+330h+var_330]
0x14000b569  lea     r8, [rsp+430h+Context]
0x14000b56e  mov     [rsp+430h+Context], r15
0x14000b573  xor     edx, edx
0x14000b575  call    ?FltGet@UfsInstanceCtx@UnionFs@@SAJAEBU_FLT_INSTANCE@@_NAEAV?$unique_ptr@VUfsInstanceCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::UfsInstanceCtx::FltGet(_FLT_INSTANCE const &,bool,wistd::unique_ptr<UnionFs::UfsInstanceCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &,UnionFs::StackEventTracer &)
0x14000b57a  mov     rbx, [rsp+430h+Context]
0x14000b57f  mov     rcx, rbx; Context
0x14000b582  call    cs:__imp_FltReferenceContext
0x14000b589  nop     dword ptr [rax+rax+00h]
0x14000b58e  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14000b595  inc     r14d
0x14000b598  mov     rdx, [rax+90h]
0x14000b59f  mov     rcx, [rdx+r14*8]; Context
0x14000b5a3  mov     [rdx+r14*8], rbx
0x14000b5a7  test    rcx, rcx
0x14000b5aa  jz      short loc_14000B5B8
0x14000b5ac  call    cs:__imp_FltReleaseContext
0x14000b5b3  nop     dword ptr [rax+rax+00h]
0x14000b5b8  test    rbx, rbx
0x14000b5bb  jz      short loc_14000B5CC
0x14000b5bd  mov     rcx, rbx; Context
0x14000b5c0  call    cs:__imp_FltReleaseContext
0x14000b5c7  nop     dword ptr [rax+rax+00h]
0x14000b5cc  mov     rcx, [rbp+330h+RetInstance]; FltObject
0x14000b5d0  test    rcx, rcx
0x14000b5d3  jz      short loc_14000B5E1
0x14000b5d5  call    cs:__imp_FltObjectDereference
0x14000b5dc  nop     dword ptr [rax+rax+00h]
0x14000b5e1  mov     rcx, [rbp+330h+RetVolume]; FltObject
0x14000b5e5  test    rcx, rcx
0x14000b5e8  jz      short loc_14000B5F6
0x14000b5ea  call    cs:__imp_FltObjectDereference
0x14000b5f1  nop     dword ptr [rax+rax+00h]
0x14000b5f6  lea     rcx, [rbp+330h+VolumeName]; UnicodeString
0x14000b5fa  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14000b5ff  mov     rdx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14000b606  mov     rax, [rdx+0D0h]
0x14000b60d  cmp     r14d, [rax+18h]
0x14000b611  jb      loc_14000B4E1
0x14000b617  mov     r14d, [rsp+430h+var_3B8]
0x14000b61c  mov     esi, [rbp+330h+var_390]
0x14000b61f  test    dil, dil
0x14000b622  jnz     loc_14000B75B
0x14000b628  test    sil, 2
0x14000b62c  jnz     loc_14000B75B
0x14000b632  mov     eax, cs:dword_14009E178
0x14000b638  cmp     eax, 5
0x14000b63b  jbe     loc_14000B909
0x14000b641  mov     rcx, cs:qword_14009E190
0x14000b648  mov     edi, 80h
0x14000b64d  mov     rax, cs:qword_14009E188
0x14000b654  test    dil, al
0x14000b657  jz      loc_14000B909
0x14000b65d  mov     rax, rcx
0x14000b660  and     rax, rdi
0x14000b663  cmp     rax, rcx
0x14000b666  jnz     loc_14000B909
0x14000b66c  lea     rax, aNoAutoAttachAn; "No auto-attach and manual attach not re"...
0x14000b673  mov     [rsp+430h+var_3B8], 4EBh
0x14000b67b  mov     [rbp+330h+var_3B0], rax
0x14000b67f  lea     r15, aOnecoreBaseFsU_4; "onecore\\base\\fs\\unionfs\\sys\\unionf"...
0x14000b686  lea     rax, [rsp+430h+var_3B8]
0x14000b68b  mov     [rsp+430h+Context], r15
0x14000b690  mov     [rsp+430h+var_3F8], rax
0x14000b695  lea     rbx, aUnionfsUnionfs_64; "UnionFs::UnionFsFilter::InstanceSetupIn"...
0x14000b69c  lea     rax, [rsp+430h+Context]
0x14000b6a1  mov     [rsp+430h+NewContext], rbx
0x14000b6a6  mov     [rsp+430h+var_400], rax
0x14000b6ab  lea     rdx, qword_140095CD0
0x14000b6b2  lea     rax, [rsp+430h+NewContext]
0x14000b6b7  mov     [rsp+430h+var_408], rax
0x14000b6bc  lea     rax, [rbp+330h+var_3B0]
0x14000b6c0  mov     [rsp+430h+var_410], rax
0x14000b6c5  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x14000b6ca  jmp     loc_14000B909
0x14000b6cf  lea     rax, aApiFltattachvo; "API: FltAttachVolume"
0x14000b6d6  mov     r8, 0B500010497h; struct UnionFs::StackEventTracer *
0x14000b6e0  lea     r9, aUnionfsUnionfs_64; "UnionFs::UnionFsFilter::InstanceSetupIn"...
0x14000b6e7  mov     [rsp+430h+var_410], rax; char *
0x14000b6ec  lea     rdx, [rbp+330h+var_330]; int
0x14000b6f0  mov     ecx, esi; this
0x14000b6f2  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14000b6f7  mov     rcx, [rbp+330h+RetInstance]; FltObject
  ... truncated ...
```
