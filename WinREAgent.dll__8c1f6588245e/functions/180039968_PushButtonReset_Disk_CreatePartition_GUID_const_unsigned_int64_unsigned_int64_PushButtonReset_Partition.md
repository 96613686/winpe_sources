# PushButtonReset::Disk::CreatePartition(_GUID const &,unsigned __int64,unsigned __int64,PushButtonReset::Partition * *)

- ea: `0x180039968`
- end: `0x18003a66f`
- name: `?CreatePartition@Disk@PushButtonReset@@QEAAJAEBU_GUID@@_K1PEAPEAVPartition@2@@Z`
- size: `3335`
- prototype: `__int64 __fastcall(PushButtonReset::Disk *__hidden this, const struct _GUID *, unsigned __int64, unsigned __int64, struct PushButtonReset::Partition **)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003b348`

## callees

- `0x180005cc0`
- `0x18000d6f0`
- `0x180023620`
- `0x180037344`
- `0x180038944`
- `0x180039968`
- `0x180045294`
- `0x180049638`
- `0x180049a60`
- `0x180049b20`
- `0x18006c652`
- `0x18006c690`
- `0x18006f010`

## import_xrefs

- `ole32!CoCreateGuid` at `0x180039ae2`
- `ole32!CoCreateGuid` at `0x180039ae2`

## string_xrefs

- `0x180039a16`: `PushButtonReset::Disk::CreatePartition`
- `0x180039a60`: `PushButtonReset::Disk::CreatePartition`
- `0x180039b09`: `PushButtonReset::Disk::CreatePartition`
- `0x180039b96`: `PushButtonReset::Disk::CreatePartition`
- `0x180039c74`: `PushButtonReset::Disk::CreatePartition`
- `0x180039d04`: `PushButtonReset::Disk::CreatePartition`
- `0x180039d9a`: `PushButtonReset::Disk::CreatePartition`
- `0x180039e35`: `PushButtonReset::Disk::CreatePartition`
- `0x180039f35`: `PushButtonReset::Disk::CreatePartition`
- `0x18003a048`: `PushButtonReset::Disk::CreatePartition`
- `0x18003a1a6`: `PushButtonReset::Disk::CreatePartition`
- `0x18003a378`: `PushButtonReset::Disk::CreatePartition`
- `0x18003a445`: `PushButtonReset::Disk::CreatePartition`
- `0x18003a569`: `PushButtonReset::Disk::CreatePartition`
- `0x180039c59`: `Failed to create partition`
- `0x180039b7b`: `Failed to cast disk to IVdsCreatePartitionEx`
- `0x180039ce9`: `Failed to wait for partition creation to complete`
- `0x18003a42a`: `Failed to allocate created`
- `0x18003a54e`: `Failed to look up newly-created partition`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall PushButtonReset::Disk::CreatePartition(
        PushButtonReset::Disk *this,
        const struct _GUID *a2,
        unsigned __int64 a3,
        __int64 a4,
        struct PushButtonReset::Partition **a5)
{
  __int64 v9; // rax
  int v10; // edi
  unsigned __int64 v12; // rcx
  __int64 v13; // rax
  HRESULT v14; // ebx
  __int64 (__fastcall ***v15)(_QWORD, GUID *, __int64); // rdi
  __int64 (__fastcall *v16)(_QWORD, GUID *, __int64); // rbx
  __int64 v17; // rax
  __int64 v18; // r14
  unsigned __int64 v19; // rsi
  unsigned __int64 v20; // r15
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, unsigned __int64, unsigned __int64, _QWORD, int *, __int64); // rbx
  __int64 v23; // rax
  int v24; // esi
  __int64 v25; // rax
  struct PushButtonReset::Partition **v26; // r14
  struct IVdsService **v27; // rax
  __int64 v28; // rax
  __int64 v29; // r15
  __int64 (__fastcall ***v30)(_QWORD, GUID *, __int64); // rdi
  __int64 (__fastcall *v31)(_QWORD, GUID *, __int64); // rbx
  __int64 v32; // rax
  __int64 v33; // rdi
  __int64 (__fastcall *v34)(__int64, __int64, struct PushButtonReset::Partition ***); // rbx
  __int64 v35; // rax
  int v36; // eax
  __int64 v37; // rdi
  __int64 (__fastcall *v38)(__int64, __int64, unsigned __int64 *); // rbx
  __int64 v39; // rax
  int i; // edi
  __int64 v41; // rax
  void **v42; // rbx
  __int64 v43; // rax
  PushButtonReset::Partition *v44; // rax
  struct PushButtonReset::Partition *v45; // rax
  _QWORD v46[2]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v47[2]; // [rsp+50h] [rbp-B0h] BYREF
  void **v48; // [rsp+60h] [rbp-A0h] BYREF
  struct PushButtonReset::Partition *v49; // [rsp+68h] [rbp-98h]
  _QWORD v50[2]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v51[2]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v52[2]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 v53; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v54[2]; // [rsp+A8h] [rbp-58h] BYREF
  struct PushButtonReset::Partition **v55; // [rsp+B8h] [rbp-48h] BYREF
  _OWORD v56[2]; // [rsp+C0h] [rbp-40h] BYREF
  _VDS_DISK_EXTENT v57; // [rsp+E0h] [rbp-20h] BYREF
  int v58; // [rsp+1C0h] [rbp+C0h] BYREF
  __int128 v59; // [rsp+1C8h] [rbp+C8h]
  GUID pguid; // [rsp+1D8h] [rbp+D8h] BYREF
  unsigned __int64 v61; // [rsp+1E8h] [rbp+E8h]
  struct _GUID v62; // [rsp+240h] [rbp+140h] BYREF
  unsigned int v63; // [rsp+270h] [rbp+170h]
  int v64; // [rsp+284h] [rbp+184h]

  v53 = a3;
  v55 = a5;
  v62.Data1 = 0;
  memset_0(&v62.Data2, 0, 0x7Cu);
  v9 = (*(__int64 (__fastcall **)(PushButtonReset::Disk *))(*(_QWORD *)this + 24LL))(this);
  v10 = (*(__int64 (__fastcall **)(__int64, struct _GUID *))(*(_QWORD *)v9 + 24LL))(v9, &v62);
  if ( v10 < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)v10,
      "PushButtonReset::Disk::CreatePartition",
      "base\\reset\\util\\src\\diskpart.cpp",
      1636,
      L"Failed to get disk properties");
    return (unsigned int)v10;
  }
  if ( v64 != 2 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147942401LL,
      "PushButtonReset::Disk::CreatePartition",
      "base\\reset\\util\\src\\diskpart.cpp",
      1642,
      L"This overload can only be called on GPT disks (actual type was [%u])",
      v64);
    return 2147942401LL;
  }
  memset_0(&v58, 0, 0x78u);
  v58 = 2;
  v12 = 0x8000000000000000uLL;
  v59 = (__int128)*a2;
  v13 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&PARTITION_MSFT_RECOVERY_GUID.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&PARTITION_MSFT_RECOVERY_GUID.Data1 )
    v13 = *(_QWORD *)a2->Data4 - *(_QWORD *)PARTITION_MSFT_RECOVERY_GUID.Data4;
  if ( !v13 )
    v12 = 0x8000000000000001uLL;
  v61 = v12;
  v14 = CoCreateGuid(&pguid);
  if ( v14 >= 0 )
  {
    v46[1] = 0;
    v46[0] = &RAII::CAutoRelease<IVdsCreatePartitionEx *>::`vftable';
    v15 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64))(*(__int64 (__fastcall **)(PushButtonReset::Disk *))(*(_QWORD *)this + 24LL))(this);
    v16 = **v15;
    v17 = RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)v46);
    v14 = v16(v15, &IID_IVdsCreatePartitionEx, v17);
    if ( v14 >= 0 )
    {
      v18 = v63;
      v19 = a3 % v63;
      v20 = v19 + a4 - v63 - (v19 + a4 - v63) % v63;
      v47[1] = 0;
      v47[0] = &RAII::CAutoRelease<IVdsAsync *>::`vftable';
      v21 = (*(__int64 (__fastcall **)(_QWORD *))(v46[0] + 24LL))(v46);
      v22 = *(__int64 (__fastcall **)(__int64, unsigned __int64, unsigned __int64, _QWORD, int *, __int64))(*(_QWORD *)v21 + 24LL);
      v23 = (*(__int64 (__fastcall **)(_QWORD *))(v47[0] + 8LL))(v47);
      v14 = v22(v21, v18 + v53 - v19, v20, 0, &v58, v23);
      v24 = 0;
      if ( v14 >= 0 )
      {
        memset(v56, 0, sizeof(v56));
        v25 = (*(__int64 (__fastcall **)(_QWORD *))(v47[0] + 32LL))(v47);
        v14 = PbrVdsWait(v25, v56);
        if ( v14 >= 0 )
        {
          v26 = v55;
          if ( v55 )
          {
            v50[1] = 0;
            v50[0] = &RAII::CAutoRelease<IVdsService *>::`vftable';
            v27 = (struct IVdsService **)RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)v50);
            v14 = PbrVdsServiceCache::Get(v27);
            if ( v14 < 0 )
            {
              PushButtonReset::Logging::TraceErr(
                2,
                (unsigned int)v14,
                "PushButtonReset::Disk::CreatePartition",
                "base\\reset\\util\\src\\diskpart.cpp",
                1678,
                L"Failed to initialize VDS");
              v50[0] = &RAII::CAutoRelease<IVdsService *>::`vftable';
              RAII::CAutoRelease<IXMLDOMParseError *>::Release(v50);
              v47[0] = &RAII::CAutoRelease<IVdsAsync *>::`vftable';
              RAII::CAutoRelease<IXMLDOMParseError *>::Release(v47);
              v46[0] = &RAII::CAutoRelease<IVdsCreatePartitionEx *>::`vftable';
              RAII::CAutoRelease<IXMLDOMParseError *>::Release(v46);
              return (unsigned int)v14;
            }
            v28 = (*(__int64 (__fastcall **)(_QWORD *))(v50[0] + 24LL))(v50);
            v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v28 + 104LL))(v28);
            if ( v14 < 0 )
            {
              PushButtonReset::Logging::TraceErr(
                2,
                (unsigned int)v14,
                "PushButtonReset::Disk::CreatePartition",
                "base\\reset\\util\\src\\diskpart.cpp",
                1681,
                L"Failed to refresh VDS state");
              v50[0] = &RAII::CAutoRelease<IVdsService *>::`vftable';
              RAII::CAutoRelease<IXMLDOMParseError *>::Release(v50);
              v47[0] = &RAII::CAutoRelease<IVdsAsync *>::`vftable';
              RAII::CAutoRelease<IXMLDOMParseError *>::Release(v47);
              v46[0] = &RAII::CAutoRelease<IVdsCreatePartitionEx *>::`vftable';
              RAII::CAutoRelease<IXMLDOMParseError *>::Release(v46);
              return (unsigned int)v14;
            }
            v29 = *((_QWORD *)&v56[0] + 1);
            v49 = 0;
            v48 = &RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable';
            v51[1] = 0;
            v51[0] = &RAII::CAutoRelease<IVdsAdvancedDisk *>::`vftable';
            v30 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64))(*(__int64 (__fastcall **)(PushButtonReset::Disk *))(*(_QWORD *)this + 24LL))(this);
            v31 = **v30;
            v32 = (*(__int64 (__fastcall **)(_QWORD *))(v51[0] + 8LL))(v51);
            v14 = v31(v30, &IID_IVdsAdvancedDisk, v32);
            if ( v14 == -2147212277 )
            {
              v14 = 0;
              v51[0] = &RAII::CAutoRelease<IVdsAdvancedDisk *>::`vftable';
              RAII::CAutoRelease<IXMLDOMParseError *>::Release(v51);
            }
            else
            {
              if ( v14 < 0 )
              {
                PushButtonReset::Logging::TraceErr(
                  2,
                  (unsigned int)v14,
                  "PushButtonReset::Disk::CreatePartition",
                  "base\\reset\\util\\src\\diskpart.cpp",
                  1698,
                  L"Failed to cast disk to IVdsAdvancedDisk");
                v51[0] = &RAII::CAutoRelease<IVdsAdvancedDisk *>::`vftable';
                RAII::CAutoRelease<IXMLDOMParseError *>::Release(v51);
                v48 = &RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable';
                RAII::CAutoPbrHeapFree<unsigned short *>::Release(&v48);
                v50[0] = &RAII::CAutoRelease<IVdsService *>::`vftable';
                RAII::CAutoRelease<IXMLDOMParseError *>::Release(v50);
                v47[0] = &RAII::CAutoRelease<IVdsAsync *>::`vftable';
                RAII::CAutoRelease<IXMLDOMParseError *>::Release(v47);
                v46[0] = &RAII::CAutoRelease<IVdsCreatePartitionEx *>::`vftable';
                RAII::CAutoRelease<IXMLDOMParseError *>::Release(v46);
                return (unsigned int)v14;
              }
              v52[1] = 0;
              v52[0] = &RAII::CAutoComFree<_VDS_PARTITION_PROP *>::`vftable';
              LODWORD(v55) = 0;
              v33 = (*(__int64 (__fastcall **)(_QWORD *))(v51[0] + 24LL))(v51);
              v34 = *(__int64 (__fastcall **)(__int64, __int64, struct PushButtonReset::Partition ***))(*(_QWORD *)v33 + 32LL);
              v35 = (*(__int64 (__fastcall **)(_QWORD *))(v52[0] + 8LL))(v52);
              v36 = v34(v33, v35, &v55);
              v14 = v36;
              if ( v36 == -2147212265 || v36 == -2147212277 )
              {
                v14 = 0;
                v52[0] = &RAII::CAutoComFree<_VDS_PARTITION_PROP *>::`vftable';
                RAII::CAutoComFree<_VDS_DISK_EXTENT *>::Release(v52);
                v51[0] = &RAII::CAutoRelease<IVdsAdvancedDisk *>::`vftable';
                RAII::CAutoRelease<IXMLDOMParseError *>::Release(v51);
              }
              else
              {
                if ( v36 < 0 )
                {
                  PushButtonReset::Logging::TraceErr(
                    2,
                    (unsigned int)v36,
                    "PushButtonReset::Disk::CreatePartition",
                    "base\\reset\\util\\src\\diskpart.cpp",
                    1698,
                    L"Failed to query disk partitions");
                  v52[0] = &RAII::CAutoComFree<_VDS_PARTITION_PROP *>::`vftable';
                  RAII::CAutoComFree<_VDS_DISK_EXTENT *>::Release(v52);
                  v51[0] = &RAII::CAutoRelease<IVdsAdvancedDisk *>::`vftable';
                  RAII::CAutoRelease<IXMLDOMParseError *>::Release(v51);
                  v48 = &RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable';
                  RAII::CAutoPbrHeapFree<unsigned short *>::Release(&v48);
                  v50[0] = &RAII::CAutoRelease<IVdsService *>::`vftable';
                  RAII::CAutoRelease<IXMLDOMParseError *>::Release(v50);
                  v47[0] = &RAII::CAutoRelease<IVdsAsync *>::`vftable';
                  RAII::CAutoRelease<IXMLDOMParseError *>::Release(v47);
                  v46[0] = &RAII::CAutoRelease<IVdsCreatePartitionEx *>::`vftable';
                  RAII::CAutoRelease<IXMLDOMParseError *>::Release(v46);
                  return (unsigned int)v14;
                }
                v54[1] = 0;
                v54[0] = &RAII::CAutoComFree<_VDS_DISK_EXTENT *>::`vftable';
                LODWORD(v53) = 0;
                v37 = (*(__int64 (__fastcall **)(PushButtonReset::Disk *))(*(_QWORD *)this + 24LL))(this);
                v38 = *(__int64 (__fastcall **)(__int64, __int64, unsigned __int64 *))(*(_QWORD *)v37 + 48LL);
                v39 = (*(__int64 (__fastcall **)(_QWORD *))(v54[0] + 8LL))(v54);
                v14 = v38(v37, v39, &v53);
                if ( v14 == -2147212277 )
                {
                  v14 = 0;
                }
                else
                {
                  if ( v14 < 0 )
                  {
                    PushButtonReset::Logging::TraceErr(
                      2,
                      (unsigned int)v14,
                      "PushButtonReset::Disk::CreatePartition",
                      "base\\reset\\util\\src\\diskpart.cpp",
                      1698,
                      L"Failed to query disk extents");
                    v54[0] = &RAII::CAutoComFree<_VDS_DISK_EXTENT *>::`vftable';
                    RAII::CAutoComFree<_VDS_DISK_EXTENT *>::Release(v54);
                    v52[0] = &RAII::CAutoComFree<_VDS_PARTITION_PROP *>::`vftable';
                    RAII::CAutoComFree<_VDS_DISK_EXTENT *>::Release(v52);
                    v51[0] = &RAII::CAutoRelease<IVdsAdvancedDisk *>::`vftable';
                    RAII::CAutoRelease<IXMLDOMParseError *>::Release(v51);
                    v48 = &RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable';
                    RAII::CAutoPbrHeapFree<unsigned short *>::Release(&v48);
                    v50[0] = &RAII::CAutoRelease<IVdsService *>::`vftable';
                    RAII::CAutoRelease<IXMLDOMParseError *>::Release(v50);
                    v47[0] = &RAII::CAutoRelease<IVdsAsync *>::`vftable';
                    RAII::CAutoRelease<IXMLDOMParseError *>::Release(v47);
                    v46[0] = &RAII::CAutoRelease<IVdsCreatePartitionEx *>::`vftable';
                    RAII::CAutoRelease<IXMLDOMParseError *>::Release(v46);
                    return (unsigned int)v14;
                  }
                  for ( i = 0; i < (int)v53; ++i )
                  {
                    v57 = *(_VDS_DISK_EXTENT *)((*(__int64 (__fastcall **)(_QWORD *))(v54[0] + 32LL))(v54) + 80LL * i);
                    if ( (int)v55 <= 0 )
                    {
LABEL_40:
                      v24 = 0;
                    }
                    else
                    {
                      while ( 1 )
                      {
                        v41 = (*(__int64 (__fastcall **)(_QWORD *))(v52[0] + 32LL))(v52);
                        if ( v57.ullOffset == *(_QWORD *)(v41 + 144LL * v24 + 16) && v57.ullOffset == v29 )
                          break;
                        if ( ++v24 >= (int)v55 )
                          goto LABEL_40;
                      }
                      v42 = v48;
                      v43 = PbrNew<PushButtonReset::Partition,>();
                      ((void (__fastcall *)(void ***, __int64))v42[6])(&v48, v43);
                      v24 = 0;
                      if ( ((unsigned __int8 (__fastcall *)(void ***))v48[9])(&v48) )
                      {
                        PushButtonReset::Logging::TraceErr(
                          2,
                          2147942414LL,
                          "PushButtonReset::Disk::CreatePartition",
                          "base\\reset\\util\\src\\diskpart.cpp",
                          1698,
                          L"Failed to allocate created");
                        v54[0] = &RAII::CAutoComFree<_VDS_DISK_EXTENT *>::`vftable';
                        RAII::CAutoComFree<_VDS_DISK_EXTENT *>::Release(v54);
                        v52[0] = &RAII::CAutoComFree<_VDS_PARTITION_PROP *>::`vftable';
                        RAII::CAutoComFree<_VDS_DISK_EXTENT *>::Release(v52);
                        v51[0] = &RAII::CAutoRelease<IVdsAdvancedDisk *>::`vftable';
                        RAII::CAutoRelease<IXMLDOMParseError *>::Release(v51);
                        v48 = &RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable';
                        RAII::CAutoPbrHeapFree<unsigned short *>::Release(&v48);
                        v50[0] = &RAII::CAutoRelease<IVdsService *>::`vftable';
                        RAII::CAutoRelease<IXMLDOMParseError *>::Release(v50);
                        v47[0] = &RAII::CAutoRelease<IVdsAsync *>::`vftable';
                        RAII::CAutoRelease<IXMLDOMParseError *>::Release(v47);
                        v46[0] = &RAII::CAutoRelease<IVdsCreatePartitionEx *>::`vftable';
                        RAII::CAutoRelease<IXMLDOMParseError *>::Release(v46);
                        return 2147942414LL;
                      }
                      v44 = (PushButtonReset::Partition *)((__int64 (__fastcall *)(void ***))v48[3])(&v48);
                      v14 = PushButtonReset::Partition::Initialize(v44, &v62, *((_DWORD *)this + 4), &v57);
                      if ( v14 < 0 )
                      {
                        PushButtonReset::Logging::TraceErr(
                          2,
                          (unsigned int)v14,
                          "PushButtonReset::Disk::CreatePartition",
                          "base\\reset\\util\\src\\diskpart.cpp",
                          1698,
                          L"Failed to initialize partition object");
                        v54[0] = &RAII::CAutoComFree<_VDS_DISK_EXTENT *>::`vftable';
                        RAII::CAutoComFree<_VDS_DISK_EXTENT *>::Release(v54);
                        v52[0] = &RAII::CAutoComFree<_VDS_PARTITION_PROP *>::`vftable';
                        RAII::CAutoComFree<_VDS_DISK_EXTENT *>::Release(v52);
                        v51[0] = &RAII::CAutoRelease<IVdsAdvancedDisk *>::`vftable';
                        RAII::CAutoRelease<IXMLDOMParseError *>::Release(v51);
                        v48 = &RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable';
                        RAII::CAutoPbrHeapFree<unsigned short *>::Release(&v48);
                        v50[0] = &RAII::CAutoRelease<IVdsService *>::`vftable';
                        RAII::CAutoRelease<IXMLDOMParseError *>::Release(v50);
                        v47[0] = &RAII::CAutoRelease<IVdsAsync *>::`vftable';
                        RAII::CAutoRelease<IXMLDOMParseError *>::Release(v47);
                        v46[0] = &RAII::CAutoRelease<IVdsCreatePartitionEx *>::`vftable';
                        RAII::CAutoRelease<IXMLDOMParseError *>::Release(v46);
                        return (unsigned int)v14;
                      }
                    }
                  }
                }
                v54[0] = &RAII::CAutoComFree<_VDS_DISK_EXTENT *>::`vftable';
                RAII::CAutoComFree<_VDS_DISK_EXTENT *>::Release(v54);
                v52[0] = &RAII::CAutoComFree<_VDS_PARTITION_PROP *>::`vftable';
                RAII::CAutoComFree<_VDS_DISK_EXTENT *>::Release(v52);
                v51[0] = &RAII::CAutoRelease<IVdsAdvancedDisk *>::`vftable';
                RAII::CAutoRelease<IXMLDOMParseError *>::Release(v51);
              }
            }
            v53 = 0;
            if ( ((unsigned __int8 (__fastcall *)(void ***, unsigned __int64 *))v48[7])(&v48, &v53) )
            {
              PushButtonReset::Logging::TraceErr(
                2,
                2147943568LL,
                "PushButtonReset::Disk::CreatePartition",
                "base\\reset\\util\\src\\diskpart.cpp",
                1703,
                L"Failed to look up newly-created partition");
              v48 = &RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable';
              RAII::CAutoPbrHeapFree<unsigned short *>::Release(&v48);
              v50[0] = &RAII::CAutoRelease<IVdsService *>::`vftable';
              RAII::CAutoRelease<IXMLDOMParseError *>::Release(v50);
              v47[0] = &RAII::CAutoRelease<IVdsAsync *>::`vftable';
              RAII::CAutoRelease<IXMLDOMParseError *>::Release(v47);
              v46[0] = &RAII::CAutoRelease<IVdsCreatePartitionEx *>::`vftable';
              RAII::CAutoRelease<IXMLDOMParseError *>::Release(v46);
              return 2147943568LL;
            }
            v45 = v49;
            v49 = 0;
            *v26 = v45;
            v48 = &RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable';
            RAII::CAutoPbrHeapFree<unsigned short *>::Release(&v48);
            v50[0] = &RAII::CAutoRelease<IVdsService *>::`vftable';
            RAII::CAutoRelease<IXMLDOMParseError *>::Release(v50);
          }
          v47[0] = &RAII::CAutoRelease<IVdsAsync *>::`vftable';
          RAII::CAutoRelease<IXMLDOMParseError *>::Release(v47);
          v46[0] = &RAII::CAutoRelease<IVdsCreatePartitionEx *>::`vftable';
          RAII::CAutoRelease<IXMLDOMParseError *>::Release(v46);
          return (unsigned int)v14;
        }
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)v14,
          "PushButtonReset::Disk::CreatePartition",
          "base\\reset\\util\\src\\diskpart.cpp",
          1672,
          L"Failed to wait for partition creation to complete");
        v47[0] = &RAII::CAutoRelease<IVdsAsync *>::`vftable';
        RAII::CAutoRelease<IXMLDOMParseError *>::Release(v47);
        v46[0] = &RAII::CAutoRelease<IVdsCreatePartitionEx *>::`vftable';
        RAII::CAutoRelease<IXMLDOMParseError *>::Release(v46);
      }
      else
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)v14,
          "PushButtonReset::Disk::CreatePartition",
          "base\\reset\\util\\src\\diskpart.cpp",
          1668,
          L"Failed to create partition");
        v47[0] = &RAII::CAutoRelease<IVdsAsync *>::`vftable';
        RAII::CAutoRelease<IXMLDOMParseError *>::Release(v47);
        v46[0] = &RAII::CAutoRelease<IVdsCreatePartitionEx *>::`vftable';
        RAII::CAutoRelease<IXMLDOMParseError *>::Release(v46);
      }
    }
    else
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)v14,
        "PushButtonReset::Disk::CreatePartition",
        "base\\reset\\util\\src\\diskpart.cpp",
        1662,
        L"Failed to cast disk to IVdsCreatePartitionEx");
      v46[0] = &RAII::CAutoRelease<IVdsCreatePartitionEx *>::`vftable';
      RAII::CAutoRelease<IXMLDOMParseError *>::Release(v46);
    }
  }
  else
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)v14,
      "PushButtonReset::Disk::CreatePartition",
      "base\\reset\\util\\src\\diskpart.cpp",
      1658,
      L"Failed to generate partition ID");
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180039968  push    rbp
0x18003996a  push    rbx
0x18003996b  push    rsi
0x18003996c  push    rdi
0x18003996d  push    r12
0x18003996f  push    r13
0x180039971  push    r14
0x180039973  push    r15
0x180039975  lea     rbp, [rsp-1D8h]
0x18003997d  sub     rsp, 2D8h
0x180039984  mov     rax, cs:__security_cookie
0x18003998b  xor     rax, rsp
0x18003998e  mov     [rbp+210h+var_50], rax
0x180039995  mov     r15, r9
0x180039998  mov     rsi, r8
0x18003999b  mov     [rbp+210h+var_270], r8
0x18003999f  mov     rbx, rdx
0x1800399a2  mov     r13, rcx
0x1800399a5  mov     rax, [rbp+210h+arg_20]
0x1800399ac  mov     [rbp+210h+var_258], rax
0x1800399b0  mov     [rbp+210h+var_D0.Data1], 0
0x1800399ba  xor     edx, edx; Val
0x1800399bc  lea     r8d, [rdx+7Ch]; Size
0x1800399c0  lea     rcx, [rbp+210h+var_D0.Data2]; void *
0x1800399c7  call    memset_0
0x1800399cc  mov     rax, [r13+0]
0x1800399d0  mov     rcx, r13
0x1800399d3  mov     rax, [rax+18h]
0x1800399d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800399dc  mov     r8, rax
0x1800399df  mov     rcx, [rax]
0x1800399e2  mov     rax, [rcx+18h]
0x1800399e6  lea     rdx, [rbp+210h+var_D0]
0x1800399ed  mov     rcx, r8
0x1800399f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800399f5  mov     edi, eax
0x1800399f7  test    eax, eax
0x1800399f9  jns     short loc_180039A30
0x1800399fb  lea     rax, aFailedToGetDis; "Failed to get disk properties"
0x180039a02  mov     [rsp+310h+var_2E8], rax
0x180039a07  mov     dword ptr [rsp+310h+var_2F0], 664h
0x180039a0f  lea     r9, aBaseResetUtilS_2; "base\\reset\\util\\src\\diskpart.cpp"
0x180039a16  lea     r8, aPushbuttonrese_58; "PushButtonReset::Disk::CreatePartition"
0x180039a1d  mov     edx, edi
0x180039a1f  mov     ecx, 2
0x180039a24  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180039a29  mov     eax, edi
0x180039a2b  jmp     loc_18003A64C
0x180039a30  mov     eax, [rbp+210h+var_8C]
0x180039a36  mov     r12d, 2
0x180039a3c  cmp     eax, r12d
0x180039a3f  jz      short loc_180039A7E
0x180039a41  mov     [rsp+310h+var_2E0], eax
0x180039a45  lea     rax, aThisOverloadCa; "This overload can only be called on GPT"...
0x180039a4c  mov     [rsp+310h+var_2E8], rax
0x180039a51  mov     dword ptr [rsp+310h+var_2F0], 66Ah
0x180039a59  lea     r9, aBaseResetUtilS_2; "base\\reset\\util\\src\\diskpart.cpp"
0x180039a60  lea     r8, aPushbuttonrese_58; "PushButtonReset::Disk::CreatePartition"
0x180039a67  mov     edx, 80070001h
0x180039a6c  mov     ecx, r12d
0x180039a6f  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180039a74  mov     eax, 80070001h
0x180039a79  jmp     loc_18003A64C
0x180039a7e  xor     edx, edx; Val
0x180039a80  lea     r8d, [rdx+78h]; Size
0x180039a84  lea     rcx, [rbp+210h+var_150]; void *
0x180039a8b  call    memset_0
0x180039a90  mov     [rbp+210h+var_150], r12d
0x180039a97  mov     rcx, 8000000000000000h
0x180039aa1  movups  xmm0, xmmword ptr [rbx]
0x180039aa4  movdqu  [rbp+210h+var_148], xmm0
0x180039aac  mov     rax, [rbx]
0x180039aaf  sub     rax, qword ptr cs:PARTITION_MSFT_RECOVERY_GUID.Data1
0x180039ab6  jnz     short loc_180039AC3
0x180039ab8  mov     rax, [rbx+8]
0x180039abc  sub     rax, qword ptr cs:PARTITION_MSFT_RECOVERY_GUID.Data4
0x180039ac3  mov     rdx, 8000000000000001h
0x180039acd  test    rax, rax
0x180039ad0  cmovz   rcx, rdx
0x180039ad4  mov     [rbp+210h+var_128], rcx
0x180039adb  lea     rcx, [rbp+210h+pguid]; pguid
0x180039ae2  call    cs:__imp_CoCreateGuid
0x180039ae8  mov     ebx, eax
0x180039aea  test    eax, eax
0x180039aec  jns     short loc_180039B1F
0x180039aee  lea     rax, aFailedToGenera; "Failed to generate partition ID"
0x180039af5  mov     [rsp+310h+var_2E8], rax
0x180039afa  mov     dword ptr [rsp+310h+var_2F0], 67Ah
0x180039b02  lea     r9, aBaseResetUtilS_2; "base\\reset\\util\\src\\diskpart.cpp"
0x180039b09  lea     r8, aPushbuttonrese_58; "PushButtonReset::Disk::CreatePartition"
0x180039b10  mov     edx, ebx
0x180039b12  mov     ecx, r12d
0x180039b15  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180039b1a  jmp     loc_18003A64A
0x180039b1f  mov     [rsp+310h+var_2C8], 0
0x180039b28  lea     r14, ??_7?$CAutoRelease@PEAUIVdsCreatePartitionEx@@@RAII@@6B@; const RAII::CAutoRelease<IVdsCreatePartitionEx *>::`vftable'
0x180039b2f  mov     [rsp+310h+var_2D0], r14
0x180039b34  mov     rax, [r13+0]
0x180039b38  mov     rcx, r13
0x180039b3b  mov     rax, [rax+18h]
0x180039b3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039b44  mov     rdi, rax
0x180039b47  mov     rcx, [rax]
0x180039b4a  mov     rbx, [rcx]
0x180039b4d  mov     rcx, [rsp+310h+var_2D0]
0x180039b52  mov     rax, [rcx+8]
0x180039b56  lea     rcx, [rsp+310h+var_2D0]
0x180039b5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039b60  mov     r8, rax
0x180039b63  lea     rdx, IID_IVdsCreatePartitionEx
0x180039b6a  mov     rcx, rdi
0x180039b6d  mov     rax, rbx
0x180039b70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039b75  mov     ebx, eax
0x180039b77  test    eax, eax
0x180039b79  jns     short loc_180039BBD
0x180039b7b  lea     rax, aFailedToCastDi_2; "Failed to cast disk to IVdsCreatePartit"...
0x180039b82  mov     [rsp+310h+var_2E8], rax
0x180039b87  mov     dword ptr [rsp+310h+var_2F0], 67Eh
0x180039b8f  lea     r9, aBaseResetUtilS_2; "base\\reset\\util\\src\\diskpart.cpp"
0x180039b96  lea     r8, aPushbuttonrese_58; "PushButtonReset::Disk::CreatePartition"
0x180039b9d  mov     edx, ebx
0x180039b9f  mov     ecx, r12d
0x180039ba2  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180039ba7  nop
0x180039ba8  mov     [rsp+310h+var_2D0], r14
0x180039bad  lea     rcx, [rsp+310h+var_2D0]
0x180039bb2  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x180039bb7  nop
0x180039bb8  jmp     loc_18003A64A
0x180039bbd  mov     r14d, [rbp+210h+var_A0]
0x180039bc4  xor     edx, edx
0x180039bc6  mov     rax, rsi
0x180039bc9  div     r14
0x180039bcc  mov     rsi, rdx
0x180039bcf  sub     r15, r14
0x180039bd2  add     r15, rdx
0x180039bd5  xor     edx, edx
0x180039bd7  mov     rax, r15
0x180039bda  div     r14
0x180039bdd  sub     r15, rdx
0x180039be0  mov     [rsp+310h+var_2B8], 0
0x180039be9  lea     rax, ??_7?$CAutoRelease@PEAUIVdsAsync@@@RAII@@6B@; const RAII::CAutoRelease<IVdsAsync *>::`vftable'
0x180039bf0  mov     [rsp+310h+var_2C0], rax
0x180039bf5  mov     rax, [rsp+310h+var_2D0]
0x180039bfa  lea     rcx, [rsp+310h+var_2D0]
0x180039bff  mov     rax, [rax+18h]
0x180039c03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039c08  mov     rdi, rax
0x180039c0b  mov     rcx, [rax]
0x180039c0e  mov     rbx, [rcx+18h]
0x180039c12  mov     rcx, [rsp+310h+var_2C0]
0x180039c17  mov     rax, [rcx+8]
0x180039c1b  lea     rcx, [rsp+310h+var_2C0]
0x180039c20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039c25  mov     rdx, [rbp+210h+var_270]
0x180039c29  sub     rdx, rsi
0x180039c2c  add     rdx, r14
0x180039c2f  mov     [rsp+310h+var_2E8], rax
0x180039c34  lea     rax, [rbp+210h+var_150]
0x180039c3b  mov     [rsp+310h+var_2F0], rax
0x180039c40  xor     r9d, r9d
0x180039c43  mov     r8, r15
0x180039c46  mov     rcx, rdi
0x180039c49  mov     rax, rbx
0x180039c4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039c51  mov     ebx, eax
0x180039c53  xor     esi, esi
0x180039c55  test    eax, eax
0x180039c57  jns     short loc_180039CB9
0x180039c59  lea     rax, aFailedToCreate_13; "Failed to create partition"
0x180039c60  mov     [rsp+310h+var_2E8], rax
0x180039c65  mov     dword ptr [rsp+310h+var_2F0], 684h
0x180039c6d  lea     r9, aBaseResetUtilS_2; "base\\reset\\util\\src\\diskpart.cpp"
0x180039c74  lea     r8, aPushbuttonrese_58; "PushButtonReset::Disk::CreatePartition"
0x180039c7b  mov     edx, ebx
0x180039c7d  mov     ecx, r12d
0x180039c80  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180039c85  nop
0x180039c86  lea     rax, ??_7?$CAutoRelease@PEAUIVdsAsync@@@RAII@@6B@; const RAII::CAutoRelease<IVdsAsync *>::`vftable'
0x180039c8d  mov     [rsp+310h+var_2C0], rax
0x180039c92  lea     rcx, [rsp+310h+var_2C0]
0x180039c97  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x180039c9c  nop
0x180039c9d  lea     rax, ??_7?$CAutoRelease@PEAUIVdsCreatePartitionEx@@@RAII@@6B@; const RAII::CAutoRelease<IVdsCreatePartitionEx *>::`vftable'
0x180039ca4  mov     [rsp+310h+var_2D0], rax
0x180039ca9  lea     rcx, [rsp+310h+var_2D0]
0x180039cae  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x180039cb3  nop
0x180039cb4  jmp     loc_18003A64A
0x180039cb9  xorps   xmm0, xmm0
0x180039cbc  movups  [rbp+210h+var_250], xmm0
0x180039cc0  movups  [rbp+210h+var_240], xmm0
0x180039cc4  mov     rax, [rsp+310h+var_2C0]
0x180039cc9  lea     rcx, [rsp+310h+var_2C0]
0x180039cce  mov     rax, [rax+20h]
0x180039cd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039cd7  mov     rcx, rax
0x180039cda  lea     rdx, [rbp+210h+var_250]
0x180039cde  call    PbrVdsWait
0x180039ce3  mov     ebx, eax
0x180039ce5  test    eax, eax
0x180039ce7  jns     short loc_180039D49
0x180039ce9  lea     rax, aFailedToWaitFo; "Failed to wait for partition creation t"...
0x180039cf0  mov     [rsp+310h+var_2E8], rax
0x180039cf5  mov     dword ptr [rsp+310h+var_2F0], 688h
0x180039cfd  lea     r9, aBaseResetUtilS_2; "base\\reset\\util\\src\\diskpart.cpp"
0x180039d04  lea     r8, aPushbuttonrese_58; "PushButtonReset::Disk::CreatePartition"
0x180039d0b  mov     edx, ebx
0x180039d0d  mov     ecx, r12d
0x180039d10  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180039d15  nop
0x180039d16  lea     rax, ??_7?$CAutoRelease@PEAUIVdsAsync@@@RAII@@6B@; const RAII::CAutoRelease<IVdsAsync *>::`vftable'
0x180039d1d  mov     [rsp+310h+var_2C0], rax
0x180039d22  lea     rcx, [rsp+310h+var_2C0]
0x180039d27  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x180039d2c  nop
0x180039d2d  lea     rax, ??_7?$CAutoRelease@PEAUIVdsCreatePartitionEx@@@RAII@@6B@; const RAII::CAutoRelease<IVdsCreatePartitionEx *>::`vftable'
0x180039d34  mov     [rsp+310h+var_2D0], rax
0x180039d39  lea     rcx, [rsp+310h+var_2D0]
0x180039d3e  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x180039d43  nop
0x180039d44  jmp     loc_18003A64A
0x180039d49  mov     r14, [rbp+210h+var_258]
0x180039d4d  test    r14, r14
0x180039d50  jz      loc_18003A61C
0x180039d56  mov     [rsp+310h+var_298], rsi
0x180039d5b  lea     rdi, ??_7?$CAutoRelease@PEAUIVdsService@@@RAII@@6B@; const RAII::CAutoRelease<IVdsService *>::`vftable'
0x180039d62  mov     [rsp+310h+var_2A0], rdi
0x180039d67  lea     rcx, [rsp+310h+var_2A0]
0x180039d6c  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x180039d71  mov     rcx, rax; struct IVdsService **
0x180039d74  call    ?Get@PbrVdsServiceCache@@SAJPEAPEAUIVdsService@@@Z; PbrVdsServiceCache::Get(IVdsService * *)
0x180039d79  mov     ebx, eax
0x180039d7b  test    eax, eax
0x180039d7d  jns     short loc_180039DEF
0x180039d7f  lea     rax, aFailedToInitia_13; "Failed to initialize VDS"
0x180039d86  mov     [rsp+310h+var_2E8], rax
0x180039d8b  mov     dword ptr [rsp+310h+var_2F0], 68Eh
0x180039d93  lea     r9, aBaseResetUtilS_2; "base\\reset\\util\\src\\diskpart.cpp"
0x180039d9a  lea     r8, aPushbuttonrese_58; "PushButtonReset::Disk::CreatePartition"
0x180039da1  mov     edx, ebx
0x180039da3  mov     ecx, r12d
0x180039da6  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180039dab  nop
0x180039dac  mov     [rsp+310h+var_2A0], rdi
0x180039db1  lea     rcx, [rsp+310h+var_2A0]
0x180039db6  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x180039dbb  nop
0x180039dbc  lea     rax, ??_7?$CAutoRelease@PEAUIVdsAsync@@@RAII@@6B@; const RAII::CAutoRelease<IVdsAsync *>::`vftable'
0x180039dc3  mov     [rsp+310h+var_2C0], rax
0x180039dc8  lea     rcx, [rsp+310h+var_2C0]
0x180039dcd  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x180039dd2  nop
0x180039dd3  lea     rax, ??_7?$CAutoRelease@PEAUIVdsCreatePartitionEx@@@RAII@@6B@; const RAII::CAutoRelease<IVdsCreatePartitionEx *>::`vftable'
0x180039dda  mov     [rsp+310h+var_2D0], rax
0x180039ddf  lea     rcx, [rsp+310h+var_2D0]
0x180039de4  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x180039de9  nop
0x180039dea  jmp     loc_18003A64A
0x180039def  mov     rax, [rsp+310h+var_2A0]
0x180039df4  lea     rcx, [rsp+310h+var_2A0]
0x180039df9  mov     rax, [rax+18h]
0x180039dfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039e02  mov     rdx, rax
0x180039e05  mov     rcx, [rax]
0x180039e08  mov     rax, [rcx+68h]
0x180039e0c  mov     rcx, rdx
0x180039e0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039e14  mov     ebx, eax
0x180039e16  test    eax, eax
0x180039e18  jns     short loc_180039E8A
0x180039e1a  lea     rax, aFailedToRefres; "Failed to refresh VDS state"
0x180039e21  mov     [rsp+310h+var_2E8], rax
0x180039e26  mov     dword ptr [rsp+310h+var_2F0], 691h
0x180039e2e  lea     r9, aBaseResetUtilS_2; "base\\reset\\util\\src\\diskpart.cpp"
0x180039e35  lea     r8, aPushbuttonrese_58; "PushButtonReset::Disk::CreatePartition"
0x180039e3c  mov     edx, ebx
0x180039e3e  mov     ecx, r12d
0x180039e41  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180039e46  nop
0x180039e47  mov     [rsp+310h+var_2A0], rdi
0x180039e4c  lea     rcx, [rsp+310h+var_2A0]
0x180039e51  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x180039e56  nop
0x180039e57  lea     rax, ??_7?$CAutoRelease@PEAUIVdsAsync@@@RAII@@6B@; const RAII::CAutoRelease<IVdsAsync *>::`vftable'
0x180039e5e  mov     [rsp+310h+var_2C0], rax
0x180039e63  lea     rcx, [rsp+310h+var_2C0]
0x180039e68  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x180039e6d  nop
0x180039e6e  lea     rax, ??_7?$CAutoRelease@PEAUIVdsCreatePartitionEx@@@RAII@@6B@; const RAII::CAutoRelease<IVdsCreatePartitionEx *>::`vftable'
0x180039e75  mov     [rsp+310h+var_2D0], rax
0x180039e7a  lea     rcx, [rsp+310h+var_2D0]
0x180039e7f  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x180039e84  nop
0x180039e85  jmp     loc_18003A64A
0x180039e8a  mov     r15, qword ptr [rbp+210h+var_250+8]
0x180039e8e  mov     [rsp+310h+var_2A8], rsi
0x180039e93  lea     rax, ??_7?$CAutoPbrDelete@PEAVPartition@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable'
0x180039e9a  mov     [rsp+310h+var_2B0], rax
  ... truncated ...
```
