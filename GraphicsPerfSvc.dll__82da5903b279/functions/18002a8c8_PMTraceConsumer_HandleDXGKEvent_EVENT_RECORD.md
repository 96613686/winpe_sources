# PMTraceConsumer::HandleDXGKEvent(_EVENT_RECORD *)

- ea: `0x18002a8c8`
- end: `0x18002bc26`
- name: `?HandleDXGKEvent@PMTraceConsumer@@QEAAXPEAU_EVENT_RECORD@@@Z`
- size: `4958`
- prototype: `void __fastcall(PMTraceConsumer *__hidden this, struct _EVENT_RECORD *)`
- caller_count: `1`
- callee_count: `32`
- tags: `broker_com_uri`

## callers

- `0x180019ee0`

## callees

- `0x180003ab0`
- `0x180004b35`
- `0x18000d67c`
- `0x18000e3e4`
- `0x18001139c`
- `0x180014a64`
- `0x1800273f8`
- `0x180027450`
- `0x1800282d4`
- `0x180028308`
- `0x180028524`
- `0x180028630`
- `0x180029018`
- `0x18002905c`
- `0x180029130`
- `0x180029588`
- `0x18002a8c8`
- `0x18002bc2c`
- `0x18002bd00`
- `0x18002bd70`
- `0x18002bf8c`
- `0x18002c060`
- `0x18002c13c`
- `0x18002c34c`
- `0x18002c448`
- `0x18002c53c`
- `0x18002c5d4`
- `0x18002c6a4`
- `0x18002cd94`
- `0x18002e1cc`
- `0x18002e218`
- `0x18002e664`

## string_xrefs

- `0x18002a958`: `Token`
- `0x18002ad23`: `Token`
- `0x18002a985`: `TokenData`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall PMTraceConsumer::HandleDXGKEvent(PMTraceConsumer *this, struct _EVENT_RECORD *a2)
{
  struct _EVENT_RECORD *v2; // r15
  unsigned int Id; // ecx
  unsigned int v5; // ecx
  unsigned int v6; // ecx
  unsigned int v7; // ecx
  unsigned int v8; // ecx
  unsigned int v9; // ecx
  int v10; // esi
  unsigned int v11; // ebx
  unsigned int v12; // ebx
  unsigned int v13; // ebx
  unsigned int v14; // ebx
  bool v15; // r9
  int v16; // r8d
  unsigned __int64 v17; // rax
  unsigned int v18; // ecx
  unsigned int v19; // ecx
  unsigned int v20; // ecx
  unsigned int v21; // ecx
  unsigned int v22; // ecx
  unsigned int v23; // edi
  __int64 v24; // rax
  std::_Ref_count_base *v25; // rbx
  std::_Ref_count_base *v26; // rdi
  _QWORD *v27; // rax
  unsigned int j; // ebx
  __int64 *v29; // rdx
  __int64 v30; // rax
  _QWORD *v31; // rax
  unsigned __int64 v32; // rbx
  unsigned int v33; // ecx
  unsigned int v34; // ecx
  unsigned int v35; // ecx
  unsigned int v36; // ecx
  unsigned int v37; // ecx
  unsigned int v38; // eax
  unsigned int v39; // esi
  unsigned int v40; // r13d
  const wchar_t *v41; // r12
  unsigned int v42; // ebx
  unsigned int i; // edi
  __int64 Event; // rax
  unsigned int v45; // ecx
  bool v46; // bl
  __int64 v47; // rax
  std::_Ref_count_base *v48; // rcx
  UCHAR Version; // bl
  unsigned int v50; // esi
  unsigned int v51; // rdi^4
  unsigned int v52; // ecx
  unsigned int v53; // ecx
  unsigned int v54; // ecx
  unsigned int v55; // ecx
  std::_Ref_count_base *v56; // rbx
  std::_Ref_count_base *v57; // r8
  std::_Ref_count_base *v58; // rbx
  std::_Ref_count_base *v59; // r8
  _QWORD *v60; // rdx
  __int64 v61; // rax
  _QWORD *v62; // rax
  std::_Ref_count_base *v63; // r12
  unsigned int v64; // r13d
  void *v65; // rbx
  __int64 *BltQueuePresent; // rax
  std::_Ref_count_base **v67; // r9
  __int64 v68; // r10
  __int64 v69; // r10
  std::_Ref_count_base **v70; // rdx
  std::_Ref_count_base *v71; // rcx
  std::_Ref_count_base *v72; // rcx
  std::_Ref_count_base *v73; // rcx
  std::_Ref_count_base *v74; // rcx
  std::_Ref_count_base *v75; // rcx
  std::_Ref_count_base *v76; // rdi
  unsigned int v77; // ebx
  std::_Ref_count_base *v78; // rcx
  std::_Ref_count_base *v79; // rbx
  std::_Ref_count_base *v80; // rbx
  char *v81; // r15
  unsigned __int64 v82; // rax
  _QWORD *v83; // rax
  unsigned int v84; // [rsp+20h] [rbp-E0h]
  bool v85; // [rsp+30h] [rbp-D0h]
  unsigned int v86[2]; // [rsp+40h] [rbp-C0h] BYREF
  std::_Ref_count_base *v87[2]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v88[2]; // [rsp+58h] [rbp-A8h] BYREF
  std::_Ref_count_base *v89; // [rsp+60h] [rbp-A0h] BYREF
  std::_Ref_count_base *v90; // [rsp+68h] [rbp-98h]
  __int64 v91; // [rsp+70h] [rbp-90h]
  unsigned int v92; // [rsp+78h] [rbp-88h] BYREF
  __int64 v93; // [rsp+80h] [rbp-80h]
  std::_Ref_count_base *v94; // [rsp+88h] [rbp-78h]
  const wchar_t *v95; // [rsp+90h] [rbp-70h] BYREF
  void *Src[2]; // [rsp+98h] [rbp-68h]
  size_t Size; // [rsp+A8h] [rbp-58h]
  const wchar_t *v98; // [rsp+B0h] [rbp-50h]
  void *v99[2]; // [rsp+B8h] [rbp-48h]
  size_t v100; // [rsp+C8h] [rbp-38h]
  const wchar_t *v101; // [rsp+D0h] [rbp-30h]
  void *v102[2]; // [rsp+D8h] [rbp-28h]
  size_t v103; // [rsp+E8h] [rbp-18h]
  const wchar_t *v104; // [rsp+F0h] [rbp-10h]
  void *v105[2]; // [rsp+F8h] [rbp-8h]
  size_t v106; // [rsp+108h] [rbp+8h]

  v2 = a2;
  Id = a2->EventHeader.EventDescriptor.Id;
  if ( Id > 0xFC )
  {
    if ( (unsigned __int16)Id <= 0x1F5u )
    {
      if ( (_WORD)Id == 501 )
      {
        PMTraceConsumer::HandleDxgkBltCancel(this, &a2->EventHeader);
        return;
      }
      v33 = Id - 259;
      if ( !v33 )
      {
        Version = a2->EventHeader.EventDescriptor.Version;
        v95 = L"FlipSubmitSequence";
        *(_OWORD *)Src = 0;
        Size = 0;
        v98 = L"FlipEntryStatusAfterFlip";
        *(_OWORD *)v99 = 0;
        v100 = 0;
        EventMetadata::GetEventData(this, a2, (struct EventDataDesc *)&v95, 2 - (Version < 2u), v84);
        v50 = 0;
        v87[0] = 0;
        memcpy_0(v87, Src[1], (unsigned int)Size);
        v51 = HIDWORD(v87[0]);
        if ( Version >= 2u )
        {
          LODWORD(v87[0]) = 0;
          memcpy_0(v87, v99[1], (unsigned int)v100);
          v50 = (unsigned int)v87[0];
        }
        PMTraceConsumer::HandleDxgkMMIOFlipMPO(this, &v2->EventHeader, v51, v50, Version >= 2u);
        return;
      }
      v34 = v33 - 7;
      if ( v34 )
      {
        v35 = v34 - 7;
        if ( !v35 || (v36 = v35 - 109) == 0 )
        {
          v95 = L"PlaneCount";
          *(_OWORD *)Src = 0;
          Size = 0;
          v98 = L"FlipEntryCount";
          *(_OWORD *)v99 = 0;
          v100 = 0;
          v101 = L"VidPnSourceId";
          *(_OWORD *)v102 = 0;
          v103 = 0;
          v104 = L"pDxgAdapter";
          *(_OWORD *)v105 = 0;
          v106 = 0;
          EventMetadata::GetEventData(this, a2, (struct EventDataDesc *)&v95, 4u, v84);
          v39 = 0;
          v88[0] = 0;
          memcpy_0(v88, Src[1], (unsigned int)Size);
          v86[0] = 0;
          memcpy_0(v86, v99[1], (unsigned int)v100);
          LODWORD(v87[0]) = 0;
          memcpy_0(v87, v102[1], (unsigned int)v103);
          v40 = (unsigned int)v87[0];
          v87[0] = 0;
          memcpy_0(v87, v105[1], (unsigned int)v106);
          if ( v2->EventHeader.EventDescriptor.Id != 273
            || (v41 = L"PresentIdOrPhysicalAddress", !v2->EventHeader.EventDescriptor.Version) )
          {
            v41 = L"ScannedPhysicalAddress";
          }
          v42 = 0;
          for ( i = 0; i < v88[0]; ++i )
          {
            Event = EventMetadata::GetEventData<unsigned __int64>(this, v2, v41, i);
            v45 = v42 + 1;
            if ( !Event )
              v45 = v42;
            v42 = v45;
          }
          v46 = v42 > 1;
          if ( v86[0] )
          {
            do
            {
              v47 = EventMetadata::GetEventData<unsigned __int64>(this, v2, L"FlipSubmitSequence", v39);
              PMTraceConsumer::HandleDxgkSyncDPCMPO(
                this,
                &v2->EventHeader,
                HIDWORD(v47),
                v46,
                v40,
                (unsigned __int64)v87[0]);
              ++v39;
            }
            while ( v39 < v86[0] );
          }
          return;
        }
        v37 = v36 - 87;
        if ( !v37 )
        {
          v95 = L"PacketType";
          *(_OWORD *)Src = 0;
          Size = 0;
          v98 = L"SubmitSequence";
          *(_OWORD *)v99 = 0;
          v100 = 0;
          v101 = L"hContext";
          *(_OWORD *)v102 = 0;
          v103 = 0;
          EventMetadata::GetEventData(this, a2, (struct EventDataDesc *)&v95, 3u, v84);
          v86[0] = 0;
          memcpy_0(v86, Src[1], (unsigned int)Size);
          LODWORD(v87[0]) = 0;
          memcpy_0(v87, v99[1], (unsigned int)v100);
          *(_QWORD *)v88 = 0;
          memcpy_0(v88, v102[1], (unsigned int)v103);
          PMTraceConsumer::HandleDxgkQueueSubmit(
            this,
            &v2->EventHeader,
            v86[0],
            (unsigned int)v87[0],
            *(unsigned __int64 *)v88,
            1,
            v85);
          return;
        }
        if ( v37 != 1 )
          return;
LABEL_70:
        v38 = EventMetadata::GetEventData<unsigned int>(this, a2, L"SubmitSequence");
        PMTraceConsumer::HandleDxgkQueueComplete(this, &v2->EventHeader, v38);
        return;
      }
      v95 = L"SubmitSequence";
      *(_OWORD *)Src = 0;
      Size = 0;
      EventMetadata::GetEventData(this, a2, (struct EventDataDesc *)&v95, 1u, v84);
      LODWORD(v87[0]) = 0;
      memcpy_0(v87, Src[1], (unsigned int)Size);
      std::_Tree<std::_Tmap_traits<unsigned long,PresentTraceConsumerCore::ProcessInfo,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,PresentTraceConsumerCore::ProcessInfo>>,0>>::find(
        (char *)this + 448,
        &v89,
        v87);
      if ( v89 == *((std::_Ref_count_base **)this + 56) )
        return;
      std::shared_ptr<PresentEvent>::shared_ptr<PresentEvent>(&v89, (_QWORD *)v89 + 5);
      *((_DWORD *)v89 + 39) = 3;
      v48 = v90;
LABEL_84:
      if ( v48 )
        std::_Ref_count_base::_Decref(v48);
      return;
    }
    v52 = Id - 1066;
    if ( !v52 )
    {
      v95 = L"AdapterLuid";
      *(_OWORD *)Src = 0;
      Size = 0;
      v98 = L"VidPnTargetId";
      *(_OWORD *)v99 = 0;
      v100 = 0;
      v101 = L"PresentCount";
      *(_OWORD *)v102 = 0;
      v103 = 0;
      EventMetadata::GetEventData(this, a2, (struct EventDataDesc *)&v95, 3u, v84);
      v89 = 0;
      memcpy_0(&v89, Src[1], (unsigned int)Size);
      v79 = v89;
      v86[0] = 0;
      memcpy_0(v86, v99[1], (unsigned int)v100);
      LODWORD(v87[0]) = 0;
      memcpy_0(v87, v102[1], (unsigned int)v103);
      LODWORD(v95) = v87[0];
      Src[0] = (void *)v86[0];
      Src[1] = v79;
      v87[0] = (std::_Ref_count_base *)v86[0];
      v87[1] = v79;
      std::_Tree<std::_Tmap_traits<std::tuple<unsigned __int64,unsigned __int64,unsigned int>,std::shared_ptr<PresentEvent>,std::less<std::tuple<unsigned __int64,unsigned __int64,unsigned int>>,std::allocator<std::pair<std::tuple<unsigned __int64,unsigned __int64,unsigned int> const,std::shared_ptr<PresentEvent>>>,0>>::find(
        (char *)this + 656,
        &v89,
        &v95);
      v80 = v89;
      if ( v89 == *((std::_Ref_count_base **)this + 82) )
        return;
      v81 = (char *)v89 + 56;
      if ( *(_DWORD *)(*((_QWORD *)v89 + 7) + 156LL) != 9 )
        return;
      std::_Tree<std::_Tmap_traits<std::tuple<unsigned __int64,unsigned __int64>,unsigned __int64,std::less<std::tuple<unsigned __int64,unsigned __int64>>,std::allocator<std::pair<std::tuple<unsigned __int64,unsigned __int64> const,unsigned __int64>>,0>>::find(
        (char *)this + 672,
        &v89,
        v87);
      if ( v89 == *((std::_Ref_count_base **)this + 84) || (v82 = *(_QWORD *)(*(_QWORD *)v81 + 208LL)) == 0 )
      {
        v83 = std::shared_ptr<PresentEvent>::shared_ptr<PresentEvent>(&v89, (_QWORD *)v80 + 7);
        PMTraceConsumer::RemoveLostPresent(this, v83);
        return;
      }
      if ( v82 <= *((_QWORD *)v89 + 6) )
        v82 = *((_QWORD *)v89 + 6);
      *(_QWORD *)(*(_QWORD *)v81 + 40LL) = v82;
      v61 = *((_QWORD *)v80 + 7);
      v60 = (_QWORD *)((char *)v80 + 56);
      goto LABEL_99;
    }
    v53 = v52 - 2;
    if ( !v53 )
    {
      v95 = L"AdapterLuid";
      *(_OWORD *)Src = 0;
      Size = 0;
      v98 = L"VidPnTargetId";
      *(_OWORD *)v99 = 0;
      v100 = 0;
      v101 = L"FrameNumber";
      *(_OWORD *)v102 = 0;
      v103 = 0;
      v104 = L"FrameDisplayTime";
      *(_OWORD *)v105 = 0;
      v106 = 0;
      EventMetadata::GetEventData(this, a2, (struct EventDataDesc *)&v95, 4u, v84);
      v89 = 0;
      memcpy_0(&v89, Src[1], (unsigned int)Size);
      v76 = v89;
      v86[0] = 0;
      memcpy_0(v86, v99[1], (unsigned int)v100);
      LODWORD(v87[0]) = 0;
      memcpy_0(v87, v102[1], (unsigned int)v103);
      v77 = (unsigned int)v87[0];
      v89 = 0;
      memcpy_0(&v89, v105[1], (unsigned int)v106);
      v92 = v77;
      v93 = v86[0];
      v94 = v76;
      LODWORD(v95) = v77;
      Src[0] = (void *)v86[0];
      Src[1] = v76;
      PMTraceConsumer::FindOrCreateBltQueuePresent(this);
      v78 = v87[0];
      if ( v87[0] )
      {
        *((_DWORD *)v87[0] + 39) = 9;
        *((_QWORD *)v78 + 26) = v89;
        std::_Tree<std::_Tmap_traits<std::tuple<unsigned __int64,unsigned __int64,unsigned int>,std::shared_ptr<PresentEvent>,std::less<std::tuple<unsigned __int64,unsigned __int64,unsigned int>>,std::allocator<std::pair<std::tuple<unsigned __int64,unsigned __int64,unsigned int> const,std::shared_ptr<PresentEvent>>>,0>>::emplace<std::tuple<unsigned __int64,unsigned __int64,unsigned int> &,std::shared_ptr<PresentEvent> &>(
          (char *)this + 656,
          &v89,
          &v92,
          v87);
      }
      goto LABEL_105;
    }
    v54 = v53 - 3;
    if ( v54 )
    {
      v55 = v54 - 53;
      if ( v55 )
      {
        if ( v55 == 1 )
        {
          v95 = L"AdapterLuid";
          *(_OWORD *)Src = 0;
          Size = 0;
          v98 = L"VidPnTargetId";
          *(_OWORD *)v99 = 0;
          v100 = 0;
          v101 = L"FrameNumber";
          *(_OWORD *)v102 = 0;
          v103 = 0;
          EventMetadata::GetEventData(this, a2, (struct EventDataDesc *)&v95, 3u, v84);
          v87[0] = 0;
          memcpy_0(v87, Src[1], (unsigned int)Size);
          v56 = v87[0];
          v86[0] = 0;
          memcpy_0(v86, v99[1], (unsigned int)v100);
          LODWORD(v87[0]) = 0;
          memcpy_0(v87, v102[1], (unsigned int)v103);
          v92 = (unsigned int)v87[0];
          v93 = v86[0];
          v94 = v56;
          std::_Tree<std::_Tmap_traits<std::tuple<unsigned __int64,unsigned __int64,unsigned int>,std::shared_ptr<PresentEvent>,std::less<std::tuple<unsigned __int64,unsigned __int64,unsigned int>>,std::allocator<std::pair<std::tuple<unsigned __int64,unsigned __int64,unsigned int> const,std::shared_ptr<PresentEvent>>>,0>>::find(
            (char *)this + 656,
            &v89,
            &v92);
          v57 = v89;
          if ( v89 != *((std::_Ref_count_base **)this + 82) )
          {
            *(_DWORD *)(*((_QWORD *)v89 + 7) + 156LL) = 10;
            *(_QWORD *)(*((_QWORD *)v57 + 7) + 32LL) = v2->EventHeader.TimeStamp.QuadPart;
          }
        }
        return;
      }
      v95 = L"AdapterLuid";
      *(_OWORD *)Src = 0;
      Size = 0;
      v98 = L"VidPnTargetId";
      *(_OWORD *)v99 = 0;
      v100 = 0;
      v101 = L"FrameNumber";
      *(_OWORD *)v102 = 0;
      v103 = 0;
      EventMetadata::GetEventData(this, a2, (struct EventDataDesc *)&v95, 3u, v84);
      v87[0] = 0;
      memcpy_0(v87, Src[1], (unsigned int)Size);
      v58 = v87[0];
      v86[0] = 0;
      memcpy_0(v86, v99[1], (unsigned int)v100);
      LODWORD(v87[0]) = 0;
      memcpy_0(v87, v102[1], (unsigned int)v103);
      v92 = (unsigned int)v87[0];
      v93 = v86[0];
      v94 = v58;
      std::_Tree<std::_Tmap_traits<std::tuple<unsigned __int64,unsigned __int64,unsigned int>,std::shared_ptr<PresentEvent>,std::less<std::tuple<unsigned __int64,unsigned __int64,unsigned int>>,std::allocator<std::pair<std::tuple<unsigned __int64,unsigned __int64,unsigned int> const,std::shared_ptr<PresentEvent>>>,0>>::find(
        (char *)this + 656,
        &v89,
        &v92);
      v59 = v89;
      if ( v89 == *((std::_Ref_count_base **)this + 82) )
        return;
      v60 = (_QWORD *)((char *)v89 + 56);
      *(_DWORD *)(*((_QWORD *)v89 + 7) + 156LL) = 10;
      *(_QWORD *)(*((_QWORD *)v59 + 7) + 40LL) = v2->EventHeader.TimeStamp.QuadPart;
      v61 = *((_QWORD *)v59 + 7);
LABEL_99:
      *(_DWORD *)(v61 + 160) = 1;
      v62 = std::shared_ptr<PresentEvent>::shared_ptr<PresentEvent>(&v89, v60);
      PMTraceConsumer::CompletePresent((__int64)this, v62);
      return;
    }
    v95 = L"AdapterLuid";
    *(_OWORD *)Src = 0;
    Size = 0;
    v98 = L"VidPnTargetId";
    *(_OWORD *)v99 = 0;
    v100 = 0;
    v101 = L"FrameNumber";
    *(_OWORD *)v102 = 0;
    v103 = 0;
    v104 = L"AddReason";
    *(_OWORD *)v105 = 0;
    v106 = 0;
    EventMetadata::GetEventData(this, a2, (struct EventDataDesc *)&v95, 4u, v84);
    v89 = 0;
    memcpy_0(&v89, Src[1], (unsigned int)Size);
    v88[0] = 0;
    memcpy_0(v88, v99[1], (unsigned int)v100);
    v86[0] = 0;
    memcpy_0(v86, v102[1], (unsigned int)v103);
    LODWORD(v87[0]) = 0;
    memcpy_0(v87, v105[1], (unsigned int)v106);
    if ( LODWORD(v87[0]) )
      return;
    v63 = v89;
    v64 = v86[0];
    v92 = v86[0];
    v65 = (void *)v88[0];
    v93 = v88[0];
    v94 = v89;
    *(_OWORD *)v87 = 0;
    std::_Tree<std::_Tmap_traits<std::tuple<unsigned __int64,unsigned __int64,unsigned int>,std::shared_ptr<PresentEvent>,std::less<std::tuple<unsigned __int64,unsigned __int64,unsigned int>>,std::allocator<std::pair<std::tuple<unsigned __int64,unsigned __int64,unsigned int> const,std::shared_ptr<PresentEvent>>>,0>>::find(
      (char *)this + 656,
      &v89,
      &v92);
    if ( v89 == *((std::_Ref_count_base **)this + 82) )
    {
      LODWORD(v95) = v64;
      Src[0] = v65;
      Src[1] = v63;
      BltQueuePresent = (__int64 *)PMTraceConsumer::FindOrCreateBltQueuePresent(this);
      std::shared_ptr<PresentEvent>::operator=(v87, BltQueuePresent);
      if ( v90 )
        std::_Ref_count_base::_Decref(v90);
      if ( !v87[0] )
        goto LABEL_105;
      std::_Tree<std::_Tmap_traits<std::tuple<unsigned __int64,unsigned __int64,unsigned int>,std::shared_ptr<PresentEvent>,std::less<std::tuple<unsigned __int64,unsigned __int64,unsigned int>>,std::allocator<std::pair<std::tuple<unsigned __int64,unsigned __int64,unsigned int> const,std::shared_ptr<PresentEvent>>>,0>>::emplace<std::tuple<unsigned __int64,unsigned __int64,unsigned int> &,std::shared_ptr<PresentEvent> &>(
        (char *)this + 656,
        &v89,
        &v92,
        v87);
    }
    else
    {
      std::shared_ptr<PresentEvent>::operator=(v87, (char *)v89 + 56);
    }
    if ( v2->EventHeader.ThreadId == *((_DWORD *)this + 154) )
    {
      v67 = (std::_Ref_count_base **)((char *)this + 528);
      v90 = 0;
      v68 = *((_QWORD *)this + 69);
      v91 = v68;
      if ( this == (PMTraceConsumer *)-528LL )
        v89 = 0;
      else
        v89 = *v67;
      while ( v68 != *((_QWORD *)this + 70) + *((_QWORD *)this + 69) )
      {
        *(_BYTE *)(*(_QWORD *)std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<std::shared_ptr<PresentEvent>>>>::operator->(&v89)
                 + 256LL) = 0;
        v68 = v69 + 1;
        v91 = v68;
      }
      v70 = (std::_Ref_count_base **)((char *)v87[0] + 216);
      if ( (std::_Ref_count_base **)v87[0] + 27 != v67 )
      {
        v71 = *v70;
        *v70 = *v67;
        *v67 = v71;
        if ( *v70 )
          *(_QWORD *)*v70 = v70;
        if ( *v67 )
          *(_QWORD *)*v67 = v67;
        v72 = v70[1];
        v70[1] = v67[1];
        v67[1] = v72;
        v73 = v70[2];
        v70[2] = v67[2];
        v67[2] = v73;
        v74 = v70[3];
        v70[3] = v67[3];
        v67[3] = v74;
        v75 = v70[4];
        v70[4] = v67[4];
        v67[4] = v75;
      }
      *((_DWORD *)this + 154) = 0;
    }
LABEL_105:
    v48 = v87[1];
    goto LABEL_84;
  }
  if ( Id == 252 )
  {
    v15 = 1;
    v16 = -1;
    goto LABEL_18;
  }
  if ( Id <= 0xAC )
  {
    if ( Id == 172 )
    {
      v17 = EventMetadata::GetEventData<unsigned __int64>(this, a2, L"Token", 0);
      PMTraceConsumer::HandleDxgkPresentHistoryInfo(this, &v2->EventHeader, v17);
      return;
    }
    v5 = Id - 17;
    if ( !v5 )
    {
      v95 = L"FlipFenceId";
      *(_OWORD *)Src = 0;
      Size = 0;
      v98 = L"VidPnSourceId";
      *(_OWORD *)v99 = 0;
      v100 = 0;
      v101 = L"pDxgAdapter";
      *(_OWORD *)v102 = 0;
      v103 = 0;
      EventMetadata::GetEventData(this, a2, (struct EventDataDesc *)&v95, 3u, v84);
      v87[0] = 0;
      memcpy_0(v87, Src[1], (unsigned int)Size);
      v86[0] = 0;
      memcpy_0(v86, v99[1], (unsigned int)v100);
      *(_QWORD *)v88 = 0;
      memcpy_0(v88, v102[1], (unsigned int)v103);
      PMTraceConsumer::HandleDxgkSyncDPC(this, &v2->EventHeader, HIDWORD(v87[0]), v86[0], *(unsigned __int64 *)v88);
      return;
    }
    v6 = v5 - 93;
    if ( !v6 )
    {
      v95 = L"pDxgAdapter";
      *(_OWORD *)Src = 0;
      Size = 0;
      v98 = L"AdapterLuid";
      *(_OWORD *)v99 = 0;
      v100 = 0;
      EventMetadata::GetEventData(this, a2, (struct EventDataDesc *)&v95, 2u, v84);
      v87[0] = 0;
      memcpy_0(v87, Src[1], (unsigned int)Size);
      *(std::_Ref_count_base **)v86 = v87[0];
      v87[0] = 0;
      memcpy_0(v87, v99[1], (unsigned int)v100);
      v89 = v87[0];
      std::_Tree<std::_Tmap_traits<unsigned __int64,unsigned __int64,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,unsigned __int64>>,0>>::emplace<unsigned __int64 &,unsigned __int64 &>(
        (char *)this + 720,
        v87,
        v86,
        &v89);
      return;
    }
    v7 = v6 - 6;
    if ( !v7 )
    {
      v95 = L"FlipSubmitSequence";
      *(_OWORD *)Src = 0;
      Size = 0;
      v98 = L"Flags";
      *(_OWORD *)v99 = 0;
      v100 = 0;
      EventMetadata::GetEventData(this, a2, (struct EventDataDesc *)&v95, 2u, v84);
      v88[0] = 0;
      memcpy_0(v88, Src[1], (unsigned int)Size);
      v86[0] = 0;
      memcpy_0(v86, v99[1], (unsigned int)v100);
      PMTraceConsumer::HandleDxgkMMIOFlip(this, &v2->EventHeader, v88[0], v86[0]);
      return;
    }
    v8 = v7 - 50;
    if ( !v8 )
    {
      v95 = L"hwnd";
      *(_OWORD *)Src = 0;
      Size = 0;
      v98 = L"bRedirectedPresent";
      *(_OWORD *)v99 = 0;
      v100 = 0;
      EventMetadata::GetEventData(this, a2, (struct EventDataDesc *)&v95, 2u, v84);
      v87[0] = 0;
      memcpy_0(v87, Src[1], (unsigned int)Size);
      v86[0] = 0;
      memcpy_0(v86, v99[1], (unsigned int)v100);
      PMTraceConsumer::HandleDxgkBlt(this, &v2->EventHeader, (unsigned __int64)v87[0], v86[0] != 0);
      return;
    }
    v9 = v8 - 2;
    if ( v9 )
    {
      if ( v9 != 3 )
        return;
      goto LABEL_11;
    }
    v95 = L"FlipInterval";
    *(_OWORD *)Src = 0;
    Size = 0;
    v98 = L"MMIOFlip";
    *(_OWORD *)v99 = 0;
    v100 = 0;
    EventMetadata::GetEventData(this, a2, (struct EventDataDesc *)&v95, 2u, v84);
    v88[0] = 0;
    memcpy_0(v88, Src[1], (unsigned int)Size);
    v86[0] = 0;
    memcpy_0(v86, v99[1], (unsigned int)v100);
    v15 = v86[0] != 0;
    v16 = v88[0];
    a2 = v2;
LABEL_18:
    PMTraceConsumer::HandleDxgkFlip(this, &a2->EventHeader, v16, v15);
    return;
  }
  v18 = Id - 178;
  if ( !v18 )
  {
    v95 = L"PacketType";
    *(_OWORD *)Src = 0;
    Size = 0;
    v98 = L"SubmitSequence";
    *(_OWORD *)v99 = 0;
    v100 = 0;
    v101 = L"hContext";
    *(_OWORD *)v102 = 0;
    v103 = 0;
    v104 = L"bPresent";
    *(_OWORD *)v105 = 0;
    v106 = 0;
    EventMetadata::GetEventData(this, a2, (struct EventDataDesc *)&v95, 4u, v84);
    LODWORD(v87[0]) = 0;
    memcpy_0(v87, Src[1], (unsigned int)Size);
    v88[0] = 0;
    memcpy_0(v88, v99[1], (unsigned int)v100);
    *(_QWORD *)v86 = 0;
    memcpy_0(v86, v102[1], (unsigned int)v103);
    v32 = *(_QWORD *)v86;
    v86[0] = 0;
    memcpy_0(v86, v105[1], (unsigned int)v106);
    PMTraceConsumer::HandleDxgkQueueSubmit(this, &v2->EventHeader, (unsigned int)v87[0], v88[0], v32, v86[0] != 0, v85);
    return;
  }
  v19 = v18 - 2;
  if ( !v19 )
    goto LABEL_70;
  v20 = v19 - 4;
  if ( !v20 )
  {
    LODWORD(v87[0]) = a2->EventHeader.ThreadId;
    std::_Tree<std::_Tmap_traits<unsigned long,PresentTraceConsumerCore::ProcessInfo,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,PresentTraceConsumerCore::ProcessInfo>>,0>>::find(
      (char *)this + 416,
      &v89,
      v87);
    v25 = v89;
    if ( v89 == *((std::_Ref_count_base **)this + 52) )
    {
LABEL_52:
      if ( !*((_BYTE *)this + 67) )
      {
        *((_BYTE *)this + 67) = 1;
        for ( j = 0; j < *((_DWORD *)this + 96); ++j )
        {
          v29 = (__int64 *)(*((_QWORD *)this + 49) + 16LL * j);
          v30 = *v29;
          if ( *v29 && !*(_BYTE *)(v30 + 170) && !*(_BYTE *)(v30 + 171) )
          {
            v31 = std::shared_ptr<PresentEvent>::shared_ptr<PresentEvent>(v87, v29);
            PMTraceConsumer::RemoveLostPresent(this, v31);
          }
        }
      }
      return;
    }
    std::shared_ptr<PresentEvent>::shared_ptr<PresentEvent>(v87, (_QWORD *)v89 + 5);
    v26 = v87[0];
    *((_BYTE *)v87[0] + 166) = 1;
    if ( !*((_QWORD *)v26 + 14) )
      *((_QWORD *)v26 + 14) = EventMetadata::GetEventData<unsigned __int64>(this, v2, L"hWindow", 0);
    if ( *((_DWORD *)v26 + 3) == v2->EventHeader.ThreadId )
    {
      if ( *((_DWORD *)v26 + 38) != 2 )
        goto LABEL_47;
    }
    else if ( !*((_QWORD *)v26 + 3) )
    {
      *((_QWORD *)v26 + 3) = v2->EventHeader.TimeStamp.QuadPart - *(_QWORD *)v26;
    }
    std::_Tree<std::_Tmap_traits<unsigned int,std::shared_ptr<PresentEvent>,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,std::shared_ptr<PresentEvent>>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned int const,std::shared_ptr<PresentEvent>>>>>,0>(
      (char *)this + 416,
      &v89,
      v25);
LABEL_47:
    if ( *((_DWORD *)v26 + 39) == 2 && *((_QWORD *)v26 + 5) )
    {
      v27 = std::shared_ptr<PresentEvent>::shared_ptr<PresentEvent>(&v89, v87);
      PMTraceConsumer::CompletePresent((__int64)this, v27);
    }
    if ( v87[1] )
      std::_Ref_count_base::_Decref(v87[1]);
    goto LABEL_52;
  }
  v21 = v20 - 31;
  if ( !v21 )
  {
LABEL_11:
    v95 = L"Token";
    *(_OWORD *)Src = 0;
    Size = 0;
    v98 = L"Model";
    *(_OWORD *)v99 = 0;
    v100 = 0;
    v101 = L"TokenData";
    *(_OWORD *)v102 = 0;
    v103 = 0;
    EventMetadata::GetEventData(this, a2, (struct EventDataDesc *)&v95, 3u, v84);
    v10 = 0;
    *(_QWORD *)v88 = 0;
    memcpy_0(v88, Src[1], (unsigned int)Size);
    v86[0] = 0;
    memcpy_0(v86, v99[1], (unsigned int)v100);
    v11 = v86[0];
    v87[0] = 0;
    memcpy_0(v87, v102[1], (unsigned int)v103);
    if ( v11 != 1 )
    {
      v12 = v11 - 2;
      if ( v12 )
      {
        v13 = v12 - 1;
        if ( v13 )
        {
          v14 = v13 - 1;
          if ( v14 )
          {
            if ( v14 == 3 )
              v10 = 7;
          }
          else
          {
            v10 = 6;
          }
        }
        else
        {
          v10 = 5;
        }
      }
      else
      {
        v10 = 4;
      }
      PMTraceConsumer::HandleDxgkPresentHistory(this, v2, *(_QWORD *)v88, v87[0], v10);
    }
    return;
  }
  v22 = v21 - 15;
  if ( v22 )
  {
    if ( v22 == 15 )
    {
      v95 = L"SubmitSequence";
      *(_OWORD *)Src = 0;
      Size = 0;
      EventMetadata::GetEventData(this, a2, (struct EventDataDesc *)&v95, 1u, v84);
      v86[0] = 0;
      memcpy_0(v86, Src[1], (unsigned int)Size);
      v23 = v86[0];
      LODWORD(v87[0]) = v2->EventHeader.ThreadId;
      std::_Tree<std::_Tmap_traits<unsigned long,PresentTraceConsumerCore::ProcessInfo,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,PresentTraceConsumerCore::ProcessInfo>>,0>>::find(
        (char *)this + 416,
        &v89,
        v87);
      if ( v89 != *((std::_Ref_count_base **)this + 52) )
      {
        v24 = *((_QWORD *)v89 + 5);
        if ( *(_DWORD *)(v24 + 156) == 9 )
        {
          *(_DWORD *)(v24 + 136) = v23;
          std::_Tree<std::_Tmap_traits<unsigned int,std::shared_ptr<PresentEvent>,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,std::shared_ptr<PresentEvent>>>,0>>::emplace<unsigned int &,std::shared_ptr<PresentEvent> &>(
            (char *)this + 448,
            &v89,
            v86);
        }
      }
    }
  }
  else
  {
    LODWORD(v87[0]) = a2->EventHeader.ThreadId;
    std::_Tree<std::_Tmap_traits<unsigned long,PresentTraceConsumerCore::ProcessInfo,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,PresentTraceConsumerCore::ProcessInfo>>,0>>::find(
      (char *)this + 416,
      &v89,
      v87);
    if ( v89 != *((std::_Ref_count_base **)this + 52) )
      *(_QWORD *)(*((_QWORD *)v89 + 5) + 176LL) = v2->EventHeader.TimeStamp.QuadPart;
  }
}

```

## disassembly

```asm
0x18002a8c8  mov     [rsp-8+arg_10], rbx
0x18002a8cd  push    rbp
0x18002a8ce  push    rsi
0x18002a8cf  push    rdi
0x18002a8d0  push    r12
0x18002a8d2  push    r13
0x18002a8d4  push    r14
0x18002a8d6  push    r15
0x18002a8d8  lea     rbp, [rsp-20h]
0x18002a8dd  sub     rsp, 120h
0x18002a8e4  mov     rax, cs:__security_cookie
0x18002a8eb  xor     rax, rsp
0x18002a8ee  mov     [rbp+50h+var_40], rax
0x18002a8f2  mov     r15, rdx
0x18002a8f5  mov     r14, rcx
0x18002a8f8  movzx   ecx, word ptr [rdx+28h]
0x18002a8fc  mov     eax, 0FCh
0x18002a901  cmp     ecx, eax
0x18002a903  ja      loc_18002B0DD
0x18002a909  jz      loc_18002B0D1
0x18002a90f  mov     eax, 0ACh
0x18002a914  cmp     ecx, eax
0x18002a916  ja      loc_18002AD45
0x18002a91c  jz      loc_18002AD20
0x18002a922  sub     ecx, 11h
0x18002a925  jz      loc_18002AC60
0x18002a92b  sub     ecx, 5Dh ; ']'
0x18002a92e  jz      loc_18002ABBF
0x18002a934  sub     ecx, 6
0x18002a937  jz      loc_18002AB3A
0x18002a93d  sub     ecx, 32h ; '2'
0x18002a940  jz      loc_18002AAB1
0x18002a946  sub     ecx, 2
0x18002a949  jz      loc_18002AA29
0x18002a94f  cmp     ecx, 3
0x18002a952  jnz     loc_18002BBFF
0x18002a958  lea     rax, aToken; "Token"
0x18002a95f  mov     [rbp+50h+var_C0], rax
0x18002a963  xorps   xmm0, xmm0
0x18002a966  xor     eax, eax
0x18002a968  movups  xmmword ptr [rbp+50h+Src], xmm0
0x18002a96c  mov     [rbp+50h+Size], rax
0x18002a970  lea     rax, aModel; "Model"
0x18002a977  mov     [rbp+50h+var_A0], rax
0x18002a97b  xor     eax, eax
0x18002a97d  movups  xmmword ptr [rbp+50h+var_98], xmm0
0x18002a981  mov     [rbp+50h+var_88], rax
0x18002a985  lea     rax, aTokendata; "TokenData"
0x18002a98c  mov     [rbp+50h+var_80], rax
0x18002a990  xor     eax, eax
0x18002a992  movups  xmmword ptr [rbp+50h+var_78], xmm0
0x18002a996  mov     [rbp+50h+var_68], rax
0x18002a99a  lea     r9d, [rax+3]; unsigned int
0x18002a99e  lea     r8, [rbp+50h+var_C0]; struct EventDataDesc *
0x18002a9a2  mov     rcx, r14; this
0x18002a9a5  call    ?GetEventData@EventMetadata@@QEAAXPEAU_EVENT_RECORD@@PEAUEventDataDesc@@II@Z; EventMetadata::GetEventData(_EVENT_RECORD *,EventDataDesc *,uint,uint)
0x18002a9aa  xor     esi, esi
0x18002a9ac  mov     qword ptr [rsp+150h+var_F8], rsi
0x18002a9b1  mov     r8d, dword ptr [rbp+50h+Size]; Size
0x18002a9b5  mov     rdx, [rbp+50h+Src+8]; Src
0x18002a9b9  lea     rcx, [rsp+150h+var_F8]; void *
0x18002a9be  call    memcpy_0
0x18002a9c3  mov     [rsp+150h+var_110], esi
0x18002a9c7  mov     r8d, dword ptr [rbp+50h+var_88]; Size
0x18002a9cb  mov     rdx, [rbp+50h+var_98+8]; Src
0x18002a9cf  lea     rcx, [rsp+150h+var_110]; void *
0x18002a9d4  call    memcpy_0
0x18002a9d9  mov     ebx, [rsp+150h+var_110]
0x18002a9dd  mov     [rsp+150h+var_108], rsi
0x18002a9e2  mov     r8d, dword ptr [rbp+50h+var_68]; Size
0x18002a9e6  mov     rdx, [rbp+50h+var_78+8]; Src
0x18002a9ea  lea     rcx, [rsp+150h+var_108]; void *
0x18002a9ef  call    memcpy_0
0x18002a9f4  cmp     ebx, 1
0x18002a9f7  jz      loc_18002BBFF
0x18002a9fd  sub     ebx, 2
0x18002aa00  jz      loc_18002AE7A
0x18002aa06  sub     ebx, 1
0x18002aa09  jz      loc_18002AE73
0x18002aa0f  sub     ebx, 1
0x18002aa12  jz      loc_18002AE6C
0x18002aa18  cmp     ebx, 3
0x18002aa1b  jnz     loc_18002AE7F
0x18002aa21  lea     esi, [rbx+4]
0x18002aa24  jmp     loc_18002AE7F
0x18002aa29  lea     rax, aFlipinterval; "FlipInterval"
0x18002aa30  mov     [rbp+50h+var_C0], rax
0x18002aa34  xorps   xmm0, xmm0
0x18002aa37  xor     eax, eax
0x18002aa39  movups  xmmword ptr [rbp+50h+Src], xmm0
0x18002aa3d  mov     [rbp+50h+Size], rax
0x18002aa41  lea     rax, aMmioflip; "MMIOFlip"
0x18002aa48  mov     [rbp+50h+var_A0], rax
0x18002aa4c  xor     eax, eax
0x18002aa4e  movups  xmmword ptr [rbp+50h+var_98], xmm0
0x18002aa52  mov     [rbp+50h+var_88], rax
0x18002aa56  lea     r9d, [rax+2]; unsigned int
0x18002aa5a  lea     r8, [rbp+50h+var_C0]; struct EventDataDesc *
0x18002aa5e  mov     rcx, r14; this
0x18002aa61  call    ?GetEventData@EventMetadata@@QEAAXPEAU_EVENT_RECORD@@PEAUEventDataDesc@@II@Z; EventMetadata::GetEventData(_EVENT_RECORD *,EventDataDesc *,uint,uint)
0x18002aa66  xor     esi, esi
0x18002aa68  mov     [rsp+150h+var_F8], esi
0x18002aa6c  mov     r8d, dword ptr [rbp+50h+Size]; Size
0x18002aa70  mov     rdx, [rbp+50h+Src+8]; Src
0x18002aa74  lea     rcx, [rsp+150h+var_F8]; void *
0x18002aa79  call    memcpy_0
0x18002aa7e  mov     [rsp+150h+var_110], esi
0x18002aa82  mov     r8d, dword ptr [rbp+50h+var_88]; Size
0x18002aa86  mov     rdx, [rbp+50h+var_98+8]; Src
0x18002aa8a  lea     rcx, [rsp+150h+var_110]; void *
0x18002aa8f  call    memcpy_0
0x18002aa94  cmp     [rsp+150h+var_110], esi
0x18002aa98  setnz   r9b; bool
0x18002aa9c  mov     r8d, [rsp+150h+var_F8]; int
0x18002aaa1  mov     rdx, r15; struct _EVENT_HEADER *
0x18002aaa4  mov     rcx, r14; this
0x18002aaa7  call    ?HandleDxgkFlip@PMTraceConsumer@@QEAAXAEBU_EVENT_HEADER@@H_N@Z; PMTraceConsumer::HandleDxgkFlip(_EVENT_HEADER const &,int,bool)
0x18002aaac  jmp     loc_18002BBFF
0x18002aab1  lea     rax, aHwnd; "hwnd"
0x18002aab8  mov     [rbp+50h+var_C0], rax
0x18002aabc  xorps   xmm0, xmm0
0x18002aabf  xor     eax, eax
0x18002aac1  movups  xmmword ptr [rbp+50h+Src], xmm0
0x18002aac5  mov     [rbp+50h+Size], rax
0x18002aac9  lea     rax, aBredirectedpre; "bRedirectedPresent"
0x18002aad0  mov     [rbp+50h+var_A0], rax
0x18002aad4  xor     eax, eax
0x18002aad6  movups  xmmword ptr [rbp+50h+var_98], xmm0
0x18002aada  mov     [rbp+50h+var_88], rax
0x18002aade  lea     r9d, [rax+2]; unsigned int
0x18002aae2  lea     r8, [rbp+50h+var_C0]; struct EventDataDesc *
0x18002aae6  mov     rcx, r14; this
0x18002aae9  call    ?GetEventData@EventMetadata@@QEAAXPEAU_EVENT_RECORD@@PEAUEventDataDesc@@II@Z; EventMetadata::GetEventData(_EVENT_RECORD *,EventDataDesc *,uint,uint)
0x18002aaee  xor     esi, esi
0x18002aaf0  mov     [rsp+150h+var_108], rsi
0x18002aaf5  mov     r8d, dword ptr [rbp+50h+Size]; Size
0x18002aaf9  mov     rdx, [rbp+50h+Src+8]; Src
0x18002aafd  lea     rcx, [rsp+150h+var_108]; void *
0x18002ab02  call    memcpy_0
0x18002ab07  mov     [rsp+150h+var_110], esi
0x18002ab0b  mov     r8d, dword ptr [rbp+50h+var_88]; Size
0x18002ab0f  mov     rdx, [rbp+50h+var_98+8]; Src
0x18002ab13  lea     rcx, [rsp+150h+var_110]; void *
0x18002ab18  call    memcpy_0
0x18002ab1d  cmp     [rsp+150h+var_110], esi
0x18002ab21  setnz   r9b; bool
0x18002ab25  mov     r8, [rsp+150h+var_108]; unsigned __int64
0x18002ab2a  mov     rdx, r15; struct _EVENT_HEADER *
0x18002ab2d  mov     rcx, r14; this
0x18002ab30  call    ?HandleDxgkBlt@PMTraceConsumer@@QEAAXAEBU_EVENT_HEADER@@_K_N@Z; PMTraceConsumer::HandleDxgkBlt(_EVENT_HEADER const &,unsigned __int64,bool)
0x18002ab35  jmp     loc_18002BBFF
0x18002ab3a  lea     rdi, aFlipsubmitsequ; "FlipSubmitSequence"
0x18002ab41  mov     [rbp+50h+var_C0], rdi
0x18002ab45  xorps   xmm0, xmm0
0x18002ab48  xor     eax, eax
0x18002ab4a  movups  xmmword ptr [rbp+50h+Src], xmm0
0x18002ab4e  mov     [rbp+50h+Size], rax
0x18002ab52  lea     rax, aFlags; "Flags"
0x18002ab59  mov     [rbp+50h+var_A0], rax
0x18002ab5d  xor     eax, eax
0x18002ab5f  movups  xmmword ptr [rbp+50h+var_98], xmm0
0x18002ab63  mov     [rbp+50h+var_88], rax
0x18002ab67  lea     r9d, [rax+2]; unsigned int
0x18002ab6b  lea     r8, [rbp+50h+var_C0]; struct EventDataDesc *
0x18002ab6f  mov     rcx, r14; this
0x18002ab72  call    ?GetEventData@EventMetadata@@QEAAXPEAU_EVENT_RECORD@@PEAUEventDataDesc@@II@Z; EventMetadata::GetEventData(_EVENT_RECORD *,EventDataDesc *,uint,uint)
0x18002ab77  xor     esi, esi
0x18002ab79  mov     [rsp+150h+var_F8], esi
0x18002ab7d  mov     r8d, dword ptr [rbp+50h+Size]; Size
0x18002ab81  mov     rdx, [rbp+50h+Src+8]; Src
0x18002ab85  lea     rcx, [rsp+150h+var_F8]; void *
0x18002ab8a  call    memcpy_0
0x18002ab8f  mov     [rsp+150h+var_110], esi
0x18002ab93  mov     r8d, dword ptr [rbp+50h+var_88]; Size
0x18002ab97  mov     rdx, [rbp+50h+var_98+8]; Src
0x18002ab9b  lea     rcx, [rsp+150h+var_110]; void *
0x18002aba0  call    memcpy_0
0x18002aba5  mov     r9d, [rsp+150h+var_110]; unsigned int
0x18002abaa  mov     r8d, [rsp+150h+var_F8]; unsigned int
0x18002abaf  mov     rdx, r15; struct _EVENT_HEADER *
0x18002abb2  mov     rcx, r14; this
0x18002abb5  call    ?HandleDxgkMMIOFlip@PMTraceConsumer@@QEAAXAEBU_EVENT_HEADER@@II@Z; PMTraceConsumer::HandleDxgkMMIOFlip(_EVENT_HEADER const &,uint,uint)
0x18002abba  jmp     loc_18002BBFF
0x18002abbf  lea     rax, aPdxgadapter; "pDxgAdapter"
0x18002abc6  mov     [rbp+50h+var_C0], rax
0x18002abca  xorps   xmm0, xmm0
0x18002abcd  xor     eax, eax
0x18002abcf  movups  xmmword ptr [rbp+50h+Src], xmm0
0x18002abd3  mov     [rbp+50h+Size], rax
0x18002abd7  lea     rax, aAdapterluid; "AdapterLuid"
0x18002abde  mov     [rbp+50h+var_A0], rax
0x18002abe2  xor     eax, eax
0x18002abe4  movups  xmmword ptr [rbp+50h+var_98], xmm0
0x18002abe8  mov     [rbp+50h+var_88], rax
0x18002abec  lea     r9d, [rax+2]; unsigned int
0x18002abf0  lea     r8, [rbp+50h+var_C0]; struct EventDataDesc *
0x18002abf4  mov     rcx, r14; this
0x18002abf7  call    ?GetEventData@EventMetadata@@QEAAXPEAU_EVENT_RECORD@@PEAUEventDataDesc@@II@Z; EventMetadata::GetEventData(_EVENT_RECORD *,EventDataDesc *,uint,uint)
0x18002abfc  xor     esi, esi
0x18002abfe  mov     [rsp+150h+var_108], rsi
0x18002ac03  mov     r8d, dword ptr [rbp+50h+Size]; Size
0x18002ac07  mov     rdx, [rbp+50h+Src+8]; Src
0x18002ac0b  lea     rcx, [rsp+150h+var_108]; void *
0x18002ac10  call    memcpy_0
0x18002ac15  mov     rax, [rsp+150h+var_108]
0x18002ac1a  mov     qword ptr [rsp+150h+var_110], rax
0x18002ac1f  mov     [rsp+150h+var_108], rsi
0x18002ac24  mov     r8d, dword ptr [rbp+50h+var_88]; Size
0x18002ac28  mov     rdx, [rbp+50h+var_98+8]; Src
0x18002ac2c  lea     rcx, [rsp+150h+var_108]; void *
0x18002ac31  call    memcpy_0
0x18002ac36  mov     rax, [rsp+150h+var_108]
0x18002ac3b  mov     [rsp+150h+var_F0], rax
0x18002ac40  lea     rcx, [r14+2D0h]
0x18002ac47  lea     r9, [rsp+150h+var_F0]
0x18002ac4c  lea     r8, [rsp+150h+var_110]
0x18002ac51  lea     rdx, [rsp+150h+var_108]
0x18002ac56  call    ??$emplace@AEA_KAEA_K@?$_Tree@V?$_Tmap_traits@_K_KU?$less@_K@std@@V?$allocator@U?$pair@$$CB_K_K@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_K_K@std@@@std@@@std@@@std@@_N@1@AEA_K0@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,unsigned __int64,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,unsigned __int64>>,0>>::emplace<unsigned __int64 &,unsigned __int64 &>(unsigned __int64 &,unsigned __int64 &)
0x18002ac5b  jmp     loc_18002BBFF
0x18002ac60  lea     rax, aFlipfenceid; "FlipFenceId"
0x18002ac67  mov     [rbp+50h+var_C0], rax
0x18002ac6b  xorps   xmm0, xmm0
0x18002ac6e  xor     eax, eax
0x18002ac70  movups  xmmword ptr [rbp+50h+Src], xmm0
0x18002ac74  mov     [rbp+50h+Size], rax
0x18002ac78  lea     rax, aVidpnsourceid_0; "VidPnSourceId"
0x18002ac7f  mov     [rbp+50h+var_A0], rax
0x18002ac83  xor     eax, eax
0x18002ac85  movups  xmmword ptr [rbp+50h+var_98], xmm0
0x18002ac89  mov     [rbp+50h+var_88], rax
0x18002ac8d  lea     rax, aPdxgadapter; "pDxgAdapter"
0x18002ac94  mov     [rbp+50h+var_80], rax
0x18002ac98  xor     eax, eax
0x18002ac9a  movups  xmmword ptr [rbp+50h+var_78], xmm0
0x18002ac9e  mov     [rbp+50h+var_68], rax
0x18002aca2  lea     r9d, [rax+3]; unsigned int
0x18002aca6  lea     r8, [rbp+50h+var_C0]; struct EventDataDesc *
0x18002acaa  mov     rcx, r14; this
0x18002acad  call    ?GetEventData@EventMetadata@@QEAAXPEAU_EVENT_RECORD@@PEAUEventDataDesc@@II@Z; EventMetadata::GetEventData(_EVENT_RECORD *,EventDataDesc *,uint,uint)
0x18002acb2  xor     esi, esi
0x18002acb4  mov     [rsp+150h+var_108], rsi
0x18002acb9  mov     r8d, dword ptr [rbp+50h+Size]; Size
0x18002acbd  mov     rdx, [rbp+50h+Src+8]; Src
0x18002acc1  lea     rcx, [rsp+150h+var_108]; void *
0x18002acc6  call    memcpy_0
0x18002accb  mov     [rsp+150h+var_110], esi
0x18002accf  mov     r8d, dword ptr [rbp+50h+var_88]; Size
0x18002acd3  mov     rdx, [rbp+50h+var_98+8]; Src
0x18002acd7  lea     rcx, [rsp+150h+var_110]; void *
0x18002acdc  call    memcpy_0
0x18002ace1  mov     qword ptr [rsp+150h+var_F8], rsi
0x18002ace6  mov     r8d, dword ptr [rbp+50h+var_68]; Size
0x18002acea  mov     rdx, [rbp+50h+var_78+8]; Src
0x18002acee  lea     rcx, [rsp+150h+var_F8]; void *
0x18002acf3  call    memcpy_0
0x18002acf8  mov     r8, [rsp+150h+var_108]
0x18002acfd  shr     r8, 20h; unsigned int
0x18002ad01  mov     rax, qword ptr [rsp+150h+var_F8]
0x18002ad06  mov     qword ptr [rsp+150h+var_130], rax; unsigned __int64
0x18002ad0b  mov     r9d, [rsp+150h+var_110]; unsigned int
0x18002ad10  mov     rdx, r15; struct _EVENT_HEADER *
0x18002ad13  mov     rcx, r14; this
0x18002ad16  call    ?HandleDxgkSyncDPC@PMTraceConsumer@@QEAAXAEBU_EVENT_HEADER@@II_K@Z; PMTraceConsumer::HandleDxgkSyncDPC(_EVENT_HEADER const &,uint,uint,unsigned __int64)
0x18002ad1b  jmp     loc_18002BBFF
0x18002ad20  xor     r9d, r9d
0x18002ad23  lea     r8, aToken; "Token"
0x18002ad2a  mov     rcx, r14
0x18002ad2d  call    ??$GetEventData@_K@EventMetadata@@QEAA_KPEAU_EVENT_RECORD@@PEBGI@Z; EventMetadata::GetEventData<unsigned __int64>(_EVENT_RECORD *,ushort const *,uint)
0x18002ad32  mov     r8, rax; unsigned __int64
0x18002ad35  mov     rdx, r15; struct _EVENT_HEADER *
0x18002ad38  mov     rcx, r14; this
0x18002ad3b  call    ?HandleDxgkPresentHistoryInfo@PMTraceConsumer@@QEAAXAEBU_EVENT_HEADER@@_K@Z; PMTraceConsumer::HandleDxgkPresentHistoryInfo(_EVENT_HEADER const &,unsigned __int64)
0x18002ad40  jmp     loc_18002BBFF
0x18002ad45  sub     ecx, 0B2h
0x18002ad4b  jz      loc_18002AFE0
0x18002ad51  sub     ecx, 2
0x18002ad54  jz      loc_18002B126
0x18002ad5a  sub     ecx, 4
0x18002ad5d  jz      loc_18002AE9D
0x18002ad63  sub     ecx, 1Fh
0x18002ad66  jz      loc_18002A958
0x18002ad6c  sub     ecx, 0Fh
0x18002ad6f  jz      loc_18002AE2A
0x18002ad75  cmp     ecx, 0Fh
0x18002ad78  jnz     loc_18002BBFF
0x18002ad7e  lea     rax, aSubmitsequence; "SubmitSequence"
0x18002ad85  mov     [rbp+50h+var_C0], rax
0x18002ad89  xorps   xmm0, xmm0
0x18002ad8c  xor     eax, eax
0x18002ad8e  movups  xmmword ptr [rbp+50h+Src], xmm0
0x18002ad92  mov     [rbp+50h+Size], rax
0x18002ad96  lea     r9d, [rcx-0Eh]; unsigned int
0x18002ad9a  lea     r8, [rbp+50h+var_C0]; struct EventDataDesc *
0x18002ad9e  mov     rcx, r14; this
0x18002ada1  call    ?GetEventData@EventMetadata@@QEAAXPEAU_EVENT_RECORD@@PEAUEventDataDesc@@II@Z; EventMetadata::GetEventData(_EVENT_RECORD *,EventDataDesc *,uint,uint)
0x18002ada6  xor     esi, esi
0x18002ada8  mov     [rsp+150h+var_110], esi
0x18002adac  mov     r8d, dword ptr [rbp+50h+Size]; Size
0x18002adb0  mov     rdx, [rbp+50h+Src+8]; Src
0x18002adb4  lea     rcx, [rsp+150h+var_110]; void *
  ... truncated ...
```
