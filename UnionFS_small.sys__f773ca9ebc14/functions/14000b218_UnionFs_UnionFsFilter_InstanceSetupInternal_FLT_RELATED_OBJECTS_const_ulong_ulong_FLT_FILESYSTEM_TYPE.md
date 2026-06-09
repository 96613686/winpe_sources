# UnionFs::UnionFsFilter::InstanceSetupInternal(_FLT_RELATED_OBJECTS const *,ulong,ulong,_FLT_FILESYSTEM_TYPE)

- ea: `0x14000b218`
- end: `0x14000bd8a`
- name: `?InstanceSetupInternal@UnionFsFilter@UnionFs@@CAJPEBU_FLT_RELATED_OBJECTS@@KKW4_FLT_FILESYSTEM_TYPE@@@Z`
- size: `2930`
- prototype: `__int64 __fastcall(const struct _FLT_RELATED_OBJECTS *, unsigned int, unsigned int, enum _FLT_FILESYSTEM_TYPE)`
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, installer_update`

## callers

- `0x14000b0f0`

## callees

- `0x140001008`
- `0x14000110c`
- `0x140001220`
- `0x140001344`
- `0x14000147c`
- `0x1400055d0`
- `0x140006168`
- `0x140008b3c`
- `0x14000b218`
- `0x14000fe6c`
- `0x140026880`
- `0x1400276c4`
- `0x140056a50`
- `0x140056ac4`
- `0x140056afc`
- `0x140079c48`
- `0x14007b7d0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14000b30b`
- `ntoskrnl!ObfDereferenceObject` at `0x14000b354`
- `ntoskrnl!ObfDereferenceObject` at `0x14000b383`
- `ntoskrnl!ObfDereferenceObject` at `0x14000b30b`
- `ntoskrnl!ObfDereferenceObject` at `0x14000b354`
- `ntoskrnl!ObfDereferenceObject` at `0x14000b383`
- `ntoskrnl!IoMountBootLayer` at `0x14000b536`
- `ntoskrnl!IoMountBootLayer` at `0x14000b536`
- `FLTMGR!FltIsVolumeSnapshot` at `0x14000b799`
- `FLTMGR!FltIsVolumeSnapshot` at `0x14000b799`
- `FLTMGR!FltSetInstanceContext` at `0x14000ba6b`
- `FLTMGR!FltSetInstanceContext` at `0x14000ba6b`
- `FLTMGR!FltGetDiskDeviceObject` at `0x14000b2e4`
- `FLTMGR!FltGetDiskDeviceObject` at `0x14000b2e4`
- `FLTMGR!FltAttachVolume` at `0x14000b57b`
- `FLTMGR!FltAttachVolume` at `0x14000b57b`
- `FLTMGR!FltGetVolumeFromName` at `0x14000b552`
- `FLTMGR!FltGetVolumeFromName` at `0x14000b552`
- `FLTMGR!FltReferenceContext` at `0x14000b5b2`
- `FLTMGR!FltReferenceContext` at `0x14000bb7c`
- `FLTMGR!FltReferenceContext` at `0x14000b5b2`
- `FLTMGR!FltReferenceContext` at `0x14000bb7c`
- `FLTMGR!FltReleaseContext` at `0x14000b406`
- `FLTMGR!FltReleaseContext` at `0x14000b5dc`
- `FLTMGR!FltReleaseContext` at `0x14000b5f0`
- `FLTMGR!FltReleaseContext` at `0x14000ba2f`
- `FLTMGR!FltReleaseContext` at `0x14000ba96`
- `FLTMGR!FltReleaseContext` at `0x14000baf8`
- `FLTMGR!FltReleaseContext` at `0x14000bb31`
- `FLTMGR!FltReleaseContext` at `0x14000bb62`
- `FLTMGR!FltReleaseContext` at `0x14000bba1`
- `FLTMGR!FltReleaseContext` at `0x14000bca0`
- `FLTMGR!FltReleaseContext` at `0x14000b406`
- `FLTMGR!FltReleaseContext` at `0x14000b5dc`
- `FLTMGR!FltReleaseContext` at `0x14000b5f0`
- `FLTMGR!FltReleaseContext` at `0x14000ba2f`
- `FLTMGR!FltReleaseContext` at `0x14000ba96`
- `FLTMGR!FltReleaseContext` at `0x14000baf8`
- `FLTMGR!FltReleaseContext` at `0x14000bb31`
- `FLTMGR!FltReleaseContext` at `0x14000bb62`
- `FLTMGR!FltReleaseContext` at `0x14000bba1`
- `FLTMGR!FltReleaseContext` at `0x14000bca0`
- `FLTMGR!FltObjectDereference` at `0x14000b605`
- `FLTMGR!FltObjectDereference` at `0x14000b61a`
- `FLTMGR!FltObjectDereference` at `0x14000b730`
- `FLTMGR!FltObjectDereference` at `0x14000b76f`
- `FLTMGR!FltObjectDereference` at `0x14000b605`
- `FLTMGR!FltObjectDereference` at `0x14000b61a`
- `FLTMGR!FltObjectDereference` at `0x14000b730`
- `FLTMGR!FltObjectDereference` at `0x14000b76f`

## string_xrefs

- `0x14000b96a`: `Attempting to attach`
- `0x14000bbcb`: `PUSH: CreateBootUnion`

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
            (unsigned int)qword_140095C50,
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
          (unsigned int)&dword_140095B54,
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
            (unsigned int)word_1400956D2,
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
          (unsigned int)&byte_1400950CF,
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
          (unsigned int)&byte_1400954AF,
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
      (unsigned int)&byte_14009592F,
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
0x14000b218  mov     [rsp-8+arg_8], rbx
0x14000b21d  push    rbp
0x14000b21e  push    rsi
0x14000b21f  push    rdi
0x14000b220  push    r12
0x14000b222  push    r13
0x14000b224  push    r14
0x14000b226  push    r15
0x14000b228  lea     rbp, [rsp-300h]
0x14000b230  sub     rsp, 400h
0x14000b237  mov     rax, cs:__security_cookie
0x14000b23e  xor     rax, rsp
0x14000b241  mov     [rbp+330h+var_40], rax
0x14000b248  mov     [rsp+430h+var_3B8], r8d
0x14000b24d  mov     r12d, r9d
0x14000b250  mov     [rbp+330h+var_390], edx
0x14000b253  mov     r14d, r8d
0x14000b256  mov     esi, edx
0x14000b258  mov     r13, rcx
0x14000b25b  cmp     r9d, 1Eh
0x14000b25f  ja      loc_14000BCBF
0x14000b265  mov     eax, 50000004h
0x14000b26a  bt      eax, r9d
0x14000b26e  jnb     loc_14000BCBF
0x14000b274  mov     rdx, 500010459h; unsigned __int64
0x14000b27e  lea     rcx, [rbp+330h+var_330]; this
0x14000b282  call    ??0StackEventTracer@UnionFs@@QEAA@_K@Z; UnionFs::StackEventTracer::StackEventTracer(unsigned __int64)
0x14000b287  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14000b28e  xor     r15d, r15d
0x14000b291  mov     dl, r15b
0x14000b294  mov     dil, r15b
0x14000b297  mov     [rsp+430h+var_3D0], dl
0x14000b29b  mov     cl, [rax+88h]
0x14000b2a1  nop
0x14000b2a2  test    cl, cl
0x14000b2a4  jnz     loc_14000B392
0x14000b2aa  test    sil, 1
0x14000b2ae  jz      loc_14000B392
0x14000b2b4  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14000b2bb  cmp     [rax+0C8h], r15b
0x14000b2c2  jz      loc_14000B392
0x14000b2c8  mov     rcx, [r13+10h]; Volume
0x14000b2cc  lea     rax, [rbp+330h+Object]
0x14000b2d0  lea     rdx, [rbp+330h+DiskDeviceObject]; DiskDeviceObject
0x14000b2d4  mov     [rbp+330h+var_370], rax
0x14000b2d8  mov     [rbp+330h+Object], r15
0x14000b2dc  mov     [rbp+330h+DiskDeviceObject], r15
0x14000b2e0  mov     [rbp+330h+var_360], 1
0x14000b2e4  call    cs:__imp_FltGetDiskDeviceObject
0x14000b2eb  nop     dword ptr [rax+rax+00h]
0x14000b2f0  mov     edi, eax
0x14000b2f2  cmp     [rbp+330h+var_360], r15b
0x14000b2f6  jz      short loc_14000B317
0x14000b2f8  mov     r8, [rbp+330h+var_370]
0x14000b2fc  mov     rdx, [rbp+330h+DiskDeviceObject]
0x14000b300  mov     rcx, [r8]; Object
0x14000b303  mov     [r8], rdx
0x14000b306  test    rcx, rcx
0x14000b309  jz      short loc_14000B317
0x14000b30b  call    cs:__imp_ObfDereferenceObject
0x14000b312  nop     dword ptr [rax+rax+00h]
0x14000b317  test    edi, edi
0x14000b319  jns     short loc_14000B365
0x14000b31b  lea     rax, aApiFltgetdiskd; "API: FltGetDiskDeviceObject"
0x14000b322  mov     r8, 8700010465h; struct UnionFs::StackEventTracer *
0x14000b32c  lea     r9, aUnionfsUnionfs_64; "UnionFs::UnionFsFilter::InstanceSetupIn"...
0x14000b333  mov     [rsp+430h+var_410], rax; char *
0x14000b338  lea     rdx, [rbp+330h+var_330]; int
0x14000b33c  mov     ecx, edi; this
0x14000b33e  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14000b343  mov     rcx, [rbp+330h+Object]; Object
0x14000b347  mov     [rbp+330h+Object], r15
0x14000b34b  test    rcx, rcx
0x14000b34e  jz      loc_14000BCAF
0x14000b354  call    cs:__imp_ObfDereferenceObject
0x14000b35b  nop     dword ptr [rax+rax+00h]
0x14000b360  jmp     loc_14000BCAF
0x14000b365  mov     rcx, [rbp+330h+Object]; Object
0x14000b369  mov     edi, [rcx+30h]
0x14000b36c  shr     edi, 8
0x14000b36f  and     dil, 1
0x14000b373  mov     [rbp+330h+Object], r15
0x14000b377  mov     dl, dil
0x14000b37a  mov     [rsp+430h+var_3D0], dl
0x14000b37e  test    rcx, rcx
0x14000b381  jz      short loc_14000B392
0x14000b383  call    cs:__imp_ObfDereferenceObject
0x14000b38a  nop     dword ptr [rax+rax+00h]
0x14000b38f  mov     dl, dil
0x14000b392  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14000b399  mov     cl, [rax+88h]
0x14000b39f  nop
0x14000b3a0  test    cl, cl
0x14000b3a2  jnz     loc_14000B64F
0x14000b3a8  test    dl, dl
0x14000b3aa  jz      loc_14000B64F
0x14000b3b0  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14000b3b7  lea     rsi, [rax+90h]
0x14000b3be  mov     rax, [rax+0D0h]
0x14000b3c5  mov     rbx, [rsi+8]
0x14000b3c9  mov     rcx, [rsi]
0x14000b3cc  mov     r15, rbx
0x14000b3cf  sub     r15, rcx
0x14000b3d2  mov     r14d, [rax+18h]
0x14000b3d6  inc     r14d
0x14000b3d9  sar     r15, 3
0x14000b3dd  cmp     r14, r15
0x14000b3e0  ja      short loc_14000B41C
0x14000b3e2  lea     r14, [rcx+r14*8]
0x14000b3e6  sub     rbx, r14
0x14000b3e9  mov     [rsi+8], r14
0x14000b3ed  sar     rbx, 3
0x14000b3f1  xor     r15d, r15d
0x14000b3f4  jmp     short loc_14000B412
0x14000b3f6  dec     rbx
0x14000b3f9  mov     rcx, [r14+rbx*8]; Context
0x14000b3fd  mov     [r14+rbx*8], r15
0x14000b401  test    rcx, rcx
0x14000b404  jz      short loc_14000B412
0x14000b406  call    cs:__imp_FltReleaseContext
0x14000b40d  nop     dword ptr [rax+rax+00h]
0x14000b412  test    rbx, rbx
0x14000b415  jnz     short loc_14000B3F6
0x14000b417  jmp     loc_14000B4CA
0x14000b41c  mov     rdx, [rsi+10h]
0x14000b420  mov     rax, rdx
0x14000b423  sub     rax, rcx
0x14000b426  sar     rax, 3
0x14000b42a  cmp     r14, rax
0x14000b42d  jbe     short loc_14000B46F
0x14000b42f  sub     rdx, rcx
0x14000b432  mov     rax, 0FFFFFFFFFFFFFFFh
0x14000b43c  sar     rdx, 3
0x14000b440  shr     rdx, 2
0x14000b444  imul    rdx, 7
0x14000b448  add     rdx, 8
0x14000b44c  cmp     rdx, r14
0x14000b44f  cmovb   rdx, r14
0x14000b453  cmp     rdx, rax
0x14000b456  cmova   rdx, rax
0x14000b45a  cmp     r14, rdx
0x14000b45d  ja      short loc_14000B48A
0x14000b45f  mov     rcx, rsi
0x14000b462  call    ?_SetCapacity@?$vector@V?$unique_ptr@VUfsInstanceCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@V?$allocator@V?$unique_ptr@VUfsInstanceCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@@utl@@@utl@@AEAA_N_K@Z; utl::vector<wistd::unique_ptr<UnionFs::UfsInstanceCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>>,utl::allocator<wistd::unique_ptr<UnionFs::UfsInstanceCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>>>>::_SetCapacity(unsigned __int64)
0x14000b467  test    al, al
0x14000b469  jz      short loc_14000B48A
0x14000b46b  mov     rbx, [rsi+8]
0x14000b46f  xor     eax, eax
0x14000b471  mov     rcx, r14
0x14000b474  sub     rcx, r15
0x14000b477  jz      short loc_14000B4BC
0x14000b479  xor     r15d, r15d
0x14000b47c  mov     [rbx+rax*8], r15
0x14000b480  inc     rax
0x14000b483  cmp     rax, rcx
0x14000b486  jnz     short loc_14000B47C
0x14000b488  jmp     short loc_14000B4BF
0x14000b48a  lea     rax, aOriginAllocati_1; "ORIGIN: Allocating boot layer contexts"
0x14000b491  mov     edi, 0C000009Ah
0x14000b496  mov     ecx, edi; this
0x14000b498  mov     [rsp+430h+var_410], rax; char *
0x14000b49d  lea     r9, aUnionfsUnionfs_64; "UnionFs::UnionFsFilter::InstanceSetupIn"...
0x14000b4a4  mov     r8, 5E50001047Bh; struct UnionFs::StackEventTracer *
0x14000b4ae  lea     rdx, [rbp+330h+var_330]; int
0x14000b4b2  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14000b4b7  jmp     loc_14000BCAF
0x14000b4bc  xor     r15d, r15d
0x14000b4bf  mov     rax, [rsi]
0x14000b4c2  lea     rcx, [rax+r14*8]
0x14000b4c6  mov     [rsi+8], rcx
0x14000b4ca  mov     rdx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14000b4d1  xor     eax, eax
0x14000b4d3  mov     [rbp+330h+var_338], rax
0x14000b4d7  xorps   xmm0, xmm0
0x14000b4da  movups  [rbp+330h+var_348], xmm0
0x14000b4de  mov     r14d, r15d
0x14000b4e1  mov     rax, [rdx+0D0h]
0x14000b4e8  mov     rcx, [rax+8]
0x14000b4ec  mov     rax, [r13+8]
0x14000b4f0  mov     qword ptr [rbp+330h+var_348+8], rax
0x14000b4f4  mov     rax, [r13+18h]
0x14000b4f8  mov     [rbp+330h+var_338], rax
0x14000b4fc  mov     qword ptr [rbp+330h+var_348], rcx
0x14000b500  mov     rax, [rdx+0D0h]
0x14000b507  cmp     [rax+18h], r15d
0x14000b50b  jbe     loc_14000B647
0x14000b511  xorps   xmm0, xmm0
0x14000b514  mov     eax, r14d
0x14000b517  movups  xmmword ptr [rbp+330h+VolumeName.Length], xmm0
0x14000b51b  mov     rdx, [rdx+0D0h]
0x14000b522  lea     r8, [rbp+330h+VolumeName]
0x14000b526  lea     r9, [rax+rax*2]
0x14000b52a  mov     rcx, [rdx+10h]
0x14000b52e  lea     rdx, [rbp+330h+var_348]
0x14000b532  mov     rcx, [rcx+r9*8]
0x14000b536  call    cs:__imp_IoMountBootLayer
0x14000b53d  nop     dword ptr [rax+rax+00h]
0x14000b542  mov     rcx, [r13+8]; Filter
0x14000b546  lea     r8, [rbp+330h+RetVolume]; RetVolume
0x14000b54a  lea     rdx, [rbp+330h+VolumeName]; VolumeName
0x14000b54e  mov     [rbp+330h+RetVolume], r15
0x14000b552  call    cs:__imp_FltGetVolumeFromName
0x14000b559  nop     dword ptr [rax+rax+00h]
0x14000b55e  mov     esi, eax
0x14000b560  test    eax, eax
0x14000b562  js      loc_14000B73E
0x14000b568  mov     rdx, [rbp+330h+RetVolume]; Volume
0x14000b56c  lea     r9, [rbp+330h+RetInstance]; RetInstance
0x14000b570  mov     rcx, [r13+8]; Filter
0x14000b574  xor     r8d, r8d; InstanceName
0x14000b577  mov     [rbp+330h+RetInstance], r15
0x14000b57b  call    cs:__imp_FltAttachVolume
0x14000b582  nop     dword ptr [rax+rax+00h]
0x14000b587  mov     esi, eax
0x14000b589  test    eax, eax
0x14000b58b  js      loc_14000B6FF
0x14000b591  mov     rcx, [rbp+330h+RetInstance]; Instance
0x14000b595  lea     r9, [rbp+330h+var_330]
0x14000b599  lea     r8, [rsp+430h+Context]
0x14000b59e  mov     [rsp+430h+Context], r15
0x14000b5a3  xor     edx, edx
0x14000b5a5  call    ?FltGet@UfsInstanceCtx@UnionFs@@SAJAEBU_FLT_INSTANCE@@_NAEAV?$unique_ptr@VUfsInstanceCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::UfsInstanceCtx::FltGet(_FLT_INSTANCE const &,bool,wistd::unique_ptr<UnionFs::UfsInstanceCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &,UnionFs::StackEventTracer &)
0x14000b5aa  mov     rbx, [rsp+430h+Context]
0x14000b5af  mov     rcx, rbx; Context
0x14000b5b2  call    cs:__imp_FltReferenceContext
0x14000b5b9  nop     dword ptr [rax+rax+00h]
0x14000b5be  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14000b5c5  inc     r14d
0x14000b5c8  mov     rdx, [rax+90h]
0x14000b5cf  mov     rcx, [rdx+r14*8]; Context
0x14000b5d3  mov     [rdx+r14*8], rbx
0x14000b5d7  test    rcx, rcx
0x14000b5da  jz      short loc_14000B5E8
0x14000b5dc  call    cs:__imp_FltReleaseContext
0x14000b5e3  nop     dword ptr [rax+rax+00h]
0x14000b5e8  test    rbx, rbx
0x14000b5eb  jz      short loc_14000B5FC
0x14000b5ed  mov     rcx, rbx; Context
0x14000b5f0  call    cs:__imp_FltReleaseContext
0x14000b5f7  nop     dword ptr [rax+rax+00h]
0x14000b5fc  mov     rcx, [rbp+330h+RetInstance]; FltObject
0x14000b600  test    rcx, rcx
0x14000b603  jz      short loc_14000B611
0x14000b605  call    cs:__imp_FltObjectDereference
0x14000b60c  nop     dword ptr [rax+rax+00h]
0x14000b611  mov     rcx, [rbp+330h+RetVolume]; FltObject
0x14000b615  test    rcx, rcx
0x14000b618  jz      short loc_14000B626
0x14000b61a  call    cs:__imp_FltObjectDereference
0x14000b621  nop     dword ptr [rax+rax+00h]
0x14000b626  lea     rcx, [rbp+330h+VolumeName]; UnicodeString
0x14000b62a  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14000b62f  mov     rdx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14000b636  mov     rax, [rdx+0D0h]
0x14000b63d  cmp     r14d, [rax+18h]
0x14000b641  jb      loc_14000B511
0x14000b647  mov     r14d, [rsp+430h+var_3B8]
0x14000b64c  mov     esi, [rbp+330h+var_390]
0x14000b64f  test    dil, dil
0x14000b652  jnz     loc_14000B78B
0x14000b658  test    sil, 2
0x14000b65c  jnz     loc_14000B78B
0x14000b662  mov     eax, cs:dword_14009E178
0x14000b668  cmp     eax, 5
0x14000b66b  jbe     loc_14000B939
0x14000b671  mov     rcx, cs:qword_14009E190
0x14000b678  mov     edi, 80h
0x14000b67d  mov     rax, cs:qword_14009E188
0x14000b684  test    dil, al
0x14000b687  jz      loc_14000B939
0x14000b68d  mov     rax, rcx
0x14000b690  and     rax, rdi
0x14000b693  cmp     rax, rcx
0x14000b696  jnz     loc_14000B939
0x14000b69c  lea     rax, aNoAutoAttachAn; "No auto-attach and manual attach not re"...
0x14000b6a3  mov     [rsp+430h+var_3B8], 4EBh
0x14000b6ab  mov     [rbp+330h+var_3B0], rax
0x14000b6af  lea     r15, aOnecoreBaseFsU_4; "onecore\\base\\fs\\unionfs\\sys\\unionf"...
0x14000b6b6  lea     rax, [rsp+430h+var_3B8]
0x14000b6bb  mov     [rsp+430h+Context], r15
0x14000b6c0  mov     [rsp+430h+var_3F8], rax
0x14000b6c5  lea     rbx, aUnionfsUnionfs_64; "UnionFs::UnionFsFilter::InstanceSetupIn"...
0x14000b6cc  lea     rax, [rsp+430h+Context]
0x14000b6d1  mov     [rsp+430h+NewContext], rbx
0x14000b6d6  mov     [rsp+430h+var_400], rax
0x14000b6db  lea     rdx, qword_140095C50
0x14000b6e2  lea     rax, [rsp+430h+NewContext]
0x14000b6e7  mov     [rsp+430h+var_408], rax
0x14000b6ec  lea     rax, [rbp+330h+var_3B0]
0x14000b6f0  mov     [rsp+430h+var_410], rax
0x14000b6f5  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x14000b6fa  jmp     loc_14000B939
0x14000b6ff  lea     rax, aApiFltattachvo; "API: FltAttachVolume"
0x14000b706  mov     r8, 0B500010497h; struct UnionFs::StackEventTracer *
0x14000b710  lea     r9, aUnionfsUnionfs_64; "UnionFs::UnionFsFilter::InstanceSetupIn"...
0x14000b717  mov     [rsp+430h+var_410], rax; char *
0x14000b71c  lea     rdx, [rbp+330h+var_330]; int
0x14000b720  mov     ecx, esi; this
0x14000b722  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14000b727  mov     rcx, [rbp+330h+RetInstance]; FltObject
  ... truncated ...
```
