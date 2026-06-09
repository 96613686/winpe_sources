# PushButtonReset::Disk::CreatePartition(ulong,unsigned __int64,unsigned __int64,bool,PushButtonReset::Partition * *)

- ea: `0x18003a678`
- end: `0x18003b340`
- name: `?CreatePartition@Disk@PushButtonReset@@QEAAJK_K0_NPEAPEAVPartition@2@@Z`
- size: `3272`
- prototype: `__int64 __fastcall(PushButtonReset::Disk *__hidden this, unsigned int, unsigned __int64, unsigned __int64, bool, struct PushButtonReset::Partition **)`
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
- `0x18003a678`
- `0x180045294`
- `0x180049638`
- `0x180049a60`
- `0x180049b20`
- `0x18006c652`
- `0x18006c690`
- `0x18006f010`

## string_xrefs

- `0x18003a71f`: `PushButtonReset::Disk::CreatePartition`
- `0x18003a75f`: `PushButtonReset::Disk::CreatePartition`
- `0x18003a7a6`: `PushButtonReset::Disk::CreatePartition`
- `0x18003a863`: `PushButtonReset::Disk::CreatePartition`
- `0x18003a941`: `PushButtonReset::Disk::CreatePartition`
- `0x18003a9d2`: `PushButtonReset::Disk::CreatePartition`
- `0x18003aa6a`: `PushButtonReset::Disk::CreatePartition`
- `0x18003ab07`: `PushButtonReset::Disk::CreatePartition`
- `0x18003ac0a`: `PushButtonReset::Disk::CreatePartition`
- `0x18003ad19`: `PushButtonReset::Disk::CreatePartition`
- `0x18003ae35`: `PushButtonReset::Disk::CreatePartition`
- `0x18003b050`: `PushButtonReset::Disk::CreatePartition`
- `0x18003b11f`: `PushButtonReset::Disk::CreatePartition`
- `0x18003b246`: `PushButtonReset::Disk::CreatePartition`
- `0x18003a926`: `Failed to create partition`
- `0x18003a848`: `Failed to cast disk to IVdsCreatePartitionEx`
- `0x18003a9b7`: `Failed to wait for partition creation to complete`
- `0x18003b104`: `Failed to allocate created`
- `0x18003b22b`: `Failed to look up newly-created partition`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall PushButtonReset::Disk::CreatePartition(
        PushButtonReset::Disk *this,
        unsigned int a2,
        unsigned __int64 a3,
        __int64 a4,
        bool a5,
        struct PushButtonReset::Partition **a6)
{
  __int64 v10; // rax
  int v11; // ebx
  __int64 (__fastcall ***v13)(_QWORD, GUID *, __int64); // rdi
  __int64 (__fastcall *v14)(_QWORD, GUID *, __int64); // rbx
  __int64 v15; // rax
  __int64 v16; // r14
  unsigned __int64 v17; // rsi
  unsigned __int64 v18; // r15
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, unsigned __int64, unsigned __int64, _QWORD, int *, __int64); // rbx
  __int64 v21; // rax
  __int64 v22; // rax
  struct PushButtonReset::Partition **v23; // r14
  struct IVdsService **v24; // rax
  __int64 v25; // rax
  __int64 v26; // r15
  __int64 (__fastcall ***v27)(_QWORD, GUID *, __int64); // rdi
  __int64 (__fastcall *v28)(_QWORD, GUID *, __int64); // rbx
  __int64 v29; // rax
  __int64 v30; // rdi
  __int64 (__fastcall *v31)(__int64, __int64, int *); // rbx
  __int64 v32; // rax
  int v33; // eax
  __int64 v34; // rdi
  __int64 (__fastcall *v35)(__int64, __int64, struct PushButtonReset::Partition ***); // rbx
  __int64 v36; // rax
  int i; // edi
  int v38; // esi
  __int64 v39; // rax
  void **v40; // rbx
  __int64 v41; // rax
  PushButtonReset::Partition *v42; // rax
  struct PushButtonReset::Partition *v43; // rax
  _QWORD v44[2]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v45[2]; // [rsp+50h] [rbp-B0h] BYREF
  void **v46; // [rsp+60h] [rbp-A0h] BYREF
  struct PushButtonReset::Partition *v47; // [rsp+68h] [rbp-98h]
  _QWORD v48[2]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v49[2]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v50[2]; // [rsp+90h] [rbp-70h] BYREF
  int v51; // [rsp+A0h] [rbp-60h] BYREF
  struct PushButtonReset::Partition **v52; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v53[2]; // [rsp+B0h] [rbp-50h] BYREF
  _OWORD v54[2]; // [rsp+C0h] [rbp-40h] BYREF
  struct _VDS_DISK_EXTENT v55; // [rsp+E0h] [rbp-20h] BYREF
  int v56; // [rsp+1C0h] [rbp+C0h] BYREF
  char v57; // [rsp+1C8h] [rbp+C8h]
  char v58; // [rsp+1C9h] [rbp+C9h]
  struct _GUID v59; // [rsp+240h] [rbp+140h] BYREF
  unsigned int v60; // [rsp+270h] [rbp+170h]
  int v61; // [rsp+284h] [rbp+184h]

  v52 = a6;
  v59.Data1 = 0;
  memset_0(&v59.Data2, 0, 0x7Cu);
  v10 = (*(__int64 (__fastcall **)(PushButtonReset::Disk *))(*(_QWORD *)this + 24LL))(this);
  v11 = (*(__int64 (__fastcall **)(__int64, struct _GUID *))(*(_QWORD *)v10 + 24LL))(v10, &v59);
  if ( v11 >= 0 )
  {
    if ( v61 != 1 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        2147942401LL,
        "PushButtonReset::Disk::CreatePartition",
        "base\\reset\\util\\src\\diskpart.cpp",
        1559,
        L"This overload can only be called on MBR disks (actual type was [%u])",
        v61);
      return 2147942401LL;
    }
    if ( a2 > 0xFF )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        2147942487LL,
        "PushButtonReset::Disk::CreatePartition",
        "base\\reset\\util\\src\\diskpart.cpp",
        1565,
        L"Invalid MBR type ID (must be in [0-255], was [%u])",
        a2);
      return 2147942487LL;
    }
    memset_0(&v56, 0, 0x78u);
    v56 = 1;
    v58 = 0;
    v57 = a2;
    v44[1] = 0;
    v44[0] = &RAII::CAutoRelease<IVdsCreatePartitionEx *>::`vftable';
    v13 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64))(*(__int64 (__fastcall **)(PushButtonReset::Disk *))(*(_QWORD *)this + 24LL))(this);
    v14 = **v13;
    v15 = RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)v44);
    v11 = v14(v13, &IID_IVdsCreatePartitionEx, v15);
    if ( v11 >= 0 )
    {
      v16 = v60;
      v17 = a3 % v60;
      v18 = v17 + a4 - v60 - (v17 + a4 - v60) % v60;
      v45[1] = 0;
      v45[0] = &RAII::CAutoRelease<IVdsAsync *>::`vftable';
      v19 = (*(__int64 (__fastcall **)(_QWORD *))(v44[0] + 24LL))(v44);
      v20 = *(__int64 (__fastcall **)(__int64, unsigned __int64, unsigned __int64, _QWORD, int *, __int64))(*(_QWORD *)v19 + 24LL);
      v21 = (*(__int64 (__fastcall **)(_QWORD *))(v45[0] + 8LL))(v45);
      v11 = v20(v19, v16 + a3 - v17, v18, 0, &v56, v21);
      if ( v11 >= 0 )
      {
        memset(v54, 0, sizeof(v54));
        v22 = (*(__int64 (__fastcall **)(_QWORD *))(v45[0] + 32LL))(v45);
        v11 = PbrVdsWait(v22, v54);
        if ( v11 >= 0 )
        {
          v23 = v52;
          if ( v52 )
          {
            v48[1] = 0;
            v48[0] = &RAII::CAutoRelease<IVdsService *>::`vftable';
            v24 = (struct IVdsService **)RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)v48);
            v11 = PbrVdsServiceCache::Get(v24);
            if ( v11 < 0 )
            {
              PushButtonReset::Logging::TraceErr(
                2,
                (unsigned int)v11,
                "PushButtonReset::Disk::CreatePartition",
                "base\\reset\\util\\src\\diskpart.cpp",
                1593,
                L"Failed to initialize VDS");
              v48[0] = &RAII::CAutoRelease<IVdsService *>::`vftable';
              RAII::CAutoRelease<IXMLDOMParseError *>::Release(v48);
              v45[0] = &RAII::CAutoRelease<IVdsAsync *>::`vftable';
              RAII::CAutoRelease<IXMLDOMParseError *>::Release(v45);
              v44[0] = &RAII::CAutoRelease<IVdsCreatePartitionEx *>::`vftable';
              RAII::CAutoRelease<IXMLDOMParseError *>::Release(v44);
              return (unsigned int)v11;
            }
            v25 = (*(__int64 (__fastcall **)(_QWORD *))(v48[0] + 24LL))(v48);
            v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v25 + 104LL))(v25);
            if ( v11 < 0 )
            {
              PushButtonReset::Logging::TraceErr(
                2,
                (unsigned int)v11,
                "PushButtonReset::Disk::CreatePartition",
                "base\\reset\\util\\src\\diskpart.cpp",
                1596,
                L"Failed to refresh VDS state");
              v48[0] = &RAII::CAutoRelease<IVdsService *>::`vftable';
              RAII::CAutoRelease<IXMLDOMParseError *>::Release(v48);
              v45[0] = &RAII::CAutoRelease<IVdsAsync *>::`vftable';
              RAII::CAutoRelease<IXMLDOMParseError *>::Release(v45);
              v44[0] = &RAII::CAutoRelease<IVdsCreatePartitionEx *>::`vftable';
              RAII::CAutoRelease<IXMLDOMParseError *>::Release(v44);
              return (unsigned int)v11;
            }
            v26 = *((_QWORD *)&v54[0] + 1);
            v47 = 0;
            v46 = &RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable';
            v49[1] = 0;
            v49[0] = &RAII::CAutoRelease<IVdsAdvancedDisk *>::`vftable';
            v27 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64))(*(__int64 (__fastcall **)(PushButtonReset::Disk *))(*(_QWORD *)this + 24LL))(this);
            v28 = **v27;
            v29 = (*(__int64 (__fastcall **)(_QWORD *))(v49[0] + 8LL))(v49);
            v11 = v28(v27, &IID_IVdsAdvancedDisk, v29);
            if ( v11 == -2147212277 )
            {
              v11 = 0;
              v49[0] = &RAII::CAutoRelease<IVdsAdvancedDisk *>::`vftable';
              RAII::CAutoRelease<IXMLDOMParseError *>::Release(v49);
            }
            else
            {
              if ( v11 < 0 )
              {
                PushButtonReset::Logging::TraceErr(
                  2,
                  (unsigned int)v11,
                  "PushButtonReset::Disk::CreatePartition",
                  "base\\reset\\util\\src\\diskpart.cpp",
                  1613,
                  L"Failed to cast disk to IVdsAdvancedDisk");
                v49[0] = &RAII::CAutoRelease<IVdsAdvancedDisk *>::`vftable';
                RAII::CAutoRelease<IXMLDOMParseError *>::Release(v49);
                v46 = &RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable';
                RAII::CAutoPbrHeapFree<unsigned short *>::Release(&v46);
                v48[0] = &RAII::CAutoRelease<IVdsService *>::`vftable';
                RAII::CAutoRelease<IXMLDOMParseError *>::Release(v48);
                v45[0] = &RAII::CAutoRelease<IVdsAsync *>::`vftable';
                RAII::CAutoRelease<IXMLDOMParseError *>::Release(v45);
                v44[0] = &RAII::CAutoRelease<IVdsCreatePartitionEx *>::`vftable';
                RAII::CAutoRelease<IXMLDOMParseError *>::Release(v44);
                return (unsigned int)v11;
              }
              v50[1] = 0;
              v50[0] = &RAII::CAutoComFree<_VDS_PARTITION_PROP *>::`vftable';
              v51 = 0;
              v30 = (*(__int64 (__fastcall **)(_QWORD *))(v49[0] + 24LL))(v49);
              v31 = *(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v30 + 32LL);
              v32 = (*(__int64 (__fastcall **)(_QWORD *))(v50[0] + 8LL))(v50);
              v33 = v31(v30, v32, &v51);
              v11 = v33;
              if ( v33 == -2147212265 || v33 == -2147212277 )
              {
                v11 = 0;
                v50[0] = &RAII::CAutoComFree<_VDS_PARTITION_PROP *>::`vftable';
                RAII::CAutoComFree<_VDS_DISK_EXTENT *>::Release(v50);
                v49[0] = &RAII::CAutoRelease<IVdsAdvancedDisk *>::`vftable';
                RAII::CAutoRelease<IXMLDOMParseError *>::Release(v49);
              }
              else
              {
                if ( v33 < 0 )
                {
                  PushButtonReset::Logging::TraceErr(
                    2,
                    (unsigned int)v33,
                    "PushButtonReset::Disk::CreatePartition",
                    "base\\reset\\util\\src\\diskpart.cpp",
                    1613,
                    L"Failed to query disk partitions");
                  v50[0] = &RAII::CAutoComFree<_VDS_PARTITION_PROP *>::`vftable';
                  RAII::CAutoComFree<_VDS_DISK_EXTENT *>::Release(v50);
                  v49[0] = &RAII::CAutoRelease<IVdsAdvancedDisk *>::`vftable';
                  RAII::CAutoRelease<IXMLDOMParseError *>::Release(v49);
                  v46 = &RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable';
                  RAII::CAutoPbrHeapFree<unsigned short *>::Release(&v46);
                  v48[0] = &RAII::CAutoRelease<IVdsService *>::`vftable';
                  RAII::CAutoRelease<IXMLDOMParseError *>::Release(v48);
                  v45[0] = &RAII::CAutoRelease<IVdsAsync *>::`vftable';
                  RAII::CAutoRelease<IXMLDOMParseError *>::Release(v45);
                  v44[0] = &RAII::CAutoRelease<IVdsCreatePartitionEx *>::`vftable';
                  RAII::CAutoRelease<IXMLDOMParseError *>::Release(v44);
                  return (unsigned int)v11;
                }
                v53[1] = 0;
                v53[0] = &RAII::CAutoComFree<_VDS_DISK_EXTENT *>::`vftable';
                LODWORD(v52) = 0;
                v34 = (*(__int64 (__fastcall **)(PushButtonReset::Disk *))(*(_QWORD *)this + 24LL))(this);
                v35 = *(__int64 (__fastcall **)(__int64, __int64, struct PushButtonReset::Partition ***))(*(_QWORD *)v34 + 48LL);
                v36 = (*(__int64 (__fastcall **)(_QWORD *))(v53[0] + 8LL))(v53);
                v11 = v35(v34, v36, &v52);
                if ( v11 == -2147212277 )
                {
                  v11 = 0;
                }
                else
                {
                  if ( v11 < 0 )
                  {
                    PushButtonReset::Logging::TraceErr(
                      2,
                      (unsigned int)v11,
                      "PushButtonReset::Disk::CreatePartition",
                      "base\\reset\\util\\src\\diskpart.cpp",
                      1613,
                      L"Failed to query disk extents");
                    v53[0] = &RAII::CAutoComFree<_VDS_DISK_EXTENT *>::`vftable';
                    RAII::CAutoComFree<_VDS_DISK_EXTENT *>::Release(v53);
                    v50[0] = &RAII::CAutoComFree<_VDS_PARTITION_PROP *>::`vftable';
                    RAII::CAutoComFree<_VDS_DISK_EXTENT *>::Release(v50);
                    v49[0] = &RAII::CAutoRelease<IVdsAdvancedDisk *>::`vftable';
                    RAII::CAutoRelease<IXMLDOMParseError *>::Release(v49);
                    v46 = &RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable';
                    RAII::CAutoPbrHeapFree<unsigned short *>::Release(&v46);
                    v48[0] = &RAII::CAutoRelease<IVdsService *>::`vftable';
                    RAII::CAutoRelease<IXMLDOMParseError *>::Release(v48);
                    v45[0] = &RAII::CAutoRelease<IVdsAsync *>::`vftable';
                    RAII::CAutoRelease<IXMLDOMParseError *>::Release(v45);
                    v44[0] = &RAII::CAutoRelease<IVdsCreatePartitionEx *>::`vftable';
                    RAII::CAutoRelease<IXMLDOMParseError *>::Release(v44);
                    return (unsigned int)v11;
                  }
                  for ( i = 0; i < (int)v52; ++i )
                  {
                    v55 = *(struct _VDS_DISK_EXTENT *)((*(__int64 (__fastcall **)(_QWORD *))(v53[0] + 32LL))(v53)
                                                     + 80LL * i);
                    v38 = 0;
                    if ( v51 > 0 )
                    {
                      while ( 1 )
                      {
                        v39 = (*(__int64 (__fastcall **)(_QWORD *))(v50[0] + 32LL))(v50);
                        if ( v55.ullOffset == *(_QWORD *)(v39 + 144LL * v38 + 16) && v55.ullOffset == v26 )
                          break;
                        if ( ++v38 >= v51 )
                          goto LABEL_38;
                      }
                      v40 = v46;
                      v41 = PbrNew<PushButtonReset::Partition,>();
                      ((void (__fastcall *)(void ***, __int64))v40[6])(&v46, v41);
                      if ( ((unsigned __int8 (__fastcall *)(void ***))v46[9])(&v46) )
                      {
                        PushButtonReset::Logging::TraceErr(
                          2,
                          2147942414LL,
                          "PushButtonReset::Disk::CreatePartition",
                          "base\\reset\\util\\src\\diskpart.cpp",
                          1613,
                          L"Failed to allocate created");
                        v53[0] = &RAII::CAutoComFree<_VDS_DISK_EXTENT *>::`vftable';
                        RAII::CAutoComFree<_VDS_DISK_EXTENT *>::Release(v53);
                        v50[0] = &RAII::CAutoComFree<_VDS_PARTITION_PROP *>::`vftable';
                        RAII::CAutoComFree<_VDS_DISK_EXTENT *>::Release(v50);
                        v49[0] = &RAII::CAutoRelease<IVdsAdvancedDisk *>::`vftable';
                        RAII::CAutoRelease<IXMLDOMParseError *>::Release(v49);
                        v46 = &RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable';
                        RAII::CAutoPbrHeapFree<unsigned short *>::Release(&v46);
                        v48[0] = &RAII::CAutoRelease<IVdsService *>::`vftable';
                        RAII::CAutoRelease<IXMLDOMParseError *>::Release(v48);
                        v45[0] = &RAII::CAutoRelease<IVdsAsync *>::`vftable';
                        RAII::CAutoRelease<IXMLDOMParseError *>::Release(v45);
                        v44[0] = &RAII::CAutoRelease<IVdsCreatePartitionEx *>::`vftable';
                        RAII::CAutoRelease<IXMLDOMParseError *>::Release(v44);
                        return 2147942414LL;
                      }
                      v42 = (PushButtonReset::Partition *)((__int64 (__fastcall *)(void ***))v46[3])(&v46);
                      v11 = PushButtonReset::Partition::Initialize(v42, &v59, *((_DWORD *)this + 4), &v55);
                      if ( v11 < 0 )
                      {
                        PushButtonReset::Logging::TraceErr(
                          2,
                          (unsigned int)v11,
                          "PushButtonReset::Disk::CreatePartition",
                          "base\\reset\\util\\src\\diskpart.cpp",
                          1613,
                          L"Failed to initialize partition object");
                        v53[0] = &RAII::CAutoComFree<_VDS_DISK_EXTENT *>::`vftable';
                        RAII::CAutoComFree<_VDS_DISK_EXTENT *>::Release(v53);
                        v50[0] = &RAII::CAutoComFree<_VDS_PARTITION_PROP *>::`vftable';
                        RAII::CAutoComFree<_VDS_DISK_EXTENT *>::Release(v50);
                        v49[0] = &RAII::CAutoRelease<IVdsAdvancedDisk *>::`vftable';
                        RAII::CAutoRelease<IXMLDOMParseError *>::Release(v49);
                        v46 = &RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable';
                        RAII::CAutoPbrHeapFree<unsigned short *>::Release(&v46);
                        v48[0] = &RAII::CAutoRelease<IVdsService *>::`vftable';
                        RAII::CAutoRelease<IXMLDOMParseError *>::Release(v48);
                        v45[0] = &RAII::CAutoRelease<IVdsAsync *>::`vftable';
                        RAII::CAutoRelease<IXMLDOMParseError *>::Release(v45);
                        v44[0] = &RAII::CAutoRelease<IVdsCreatePartitionEx *>::`vftable';
                        RAII::CAutoRelease<IXMLDOMParseError *>::Release(v44);
                        return (unsigned int)v11;
                      }
                    }
LABEL_38:
                    ;
                  }
                }
                v53[0] = &RAII::CAutoComFree<_VDS_DISK_EXTENT *>::`vftable';
                RAII::CAutoComFree<_VDS_DISK_EXTENT *>::Release(v53);
                v50[0] = &RAII::CAutoComFree<_VDS_PARTITION_PROP *>::`vftable';
                RAII::CAutoComFree<_VDS_DISK_EXTENT *>::Release(v50);
                v49[0] = &RAII::CAutoRelease<IVdsAdvancedDisk *>::`vftable';
                RAII::CAutoRelease<IXMLDOMParseError *>::Release(v49);
              }
            }
            v52 = 0;
            if ( ((unsigned __int8 (__fastcall *)(void ***, struct PushButtonReset::Partition ***))v46[7])(&v46, &v52) )
            {
              PushButtonReset::Logging::TraceErr(
                2,
                2147943568LL,
                "PushButtonReset::Disk::CreatePartition",
                "base\\reset\\util\\src\\diskpart.cpp",
                1618,
                L"Failed to look up newly-created partition");
              v46 = &RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable';
              RAII::CAutoPbrHeapFree<unsigned short *>::Release(&v46);
              v48[0] = &RAII::CAutoRelease<IVdsService *>::`vftable';
              RAII::CAutoRelease<IXMLDOMParseError *>::Release(v48);
              v45[0] = &RAII::CAutoRelease<IVdsAsync *>::`vftable';
              RAII::CAutoRelease<IXMLDOMParseError *>::Release(v45);
              v44[0] = &RAII::CAutoRelease<IVdsCreatePartitionEx *>::`vftable';
              RAII::CAutoRelease<IXMLDOMParseError *>::Release(v44);
              return 2147943568LL;
            }
            v43 = v47;
            v47 = 0;
            *v23 = v43;
            v46 = &RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable';
            RAII::CAutoPbrHeapFree<unsigned short *>::Release(&v46);
            v48[0] = &RAII::CAutoRelease<IVdsService *>::`vftable';
            RAII::CAutoRelease<IXMLDOMParseError *>::Release(v48);
          }
          v45[0] = &RAII::CAutoRelease<IVdsAsync *>::`vftable';
          RAII::CAutoRelease<IXMLDOMParseError *>::Release(v45);
          v44[0] = &RAII::CAutoRelease<IVdsCreatePartitionEx *>::`vftable';
          RAII::CAutoRelease<IXMLDOMParseError *>::Release(v44);
          return (unsigned int)v11;
        }
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)v11,
          "PushButtonReset::Disk::CreatePartition",
          "base\\reset\\util\\src\\diskpart.cpp",
          1587,
          L"Failed to wait for partition creation to complete");
        v45[0] = &RAII::CAutoRelease<IVdsAsync *>::`vftable';
        RAII::CAutoRelease<IXMLDOMParseError *>::Release(v45);
        v44[0] = &RAII::CAutoRelease<IVdsCreatePartitionEx *>::`vftable';
        RAII::CAutoRelease<IXMLDOMParseError *>::Release(v44);
      }
      else
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)v11,
          "PushButtonReset::Disk::CreatePartition",
          "base\\reset\\util\\src\\diskpart.cpp",
          1583,
          L"Failed to create partition");
        v45[0] = &RAII::CAutoRelease<IVdsAsync *>::`vftable';
        RAII::CAutoRelease<IXMLDOMParseError *>::Release(v45);
        v44[0] = &RAII::CAutoRelease<IVdsCreatePartitionEx *>::`vftable';
        RAII::CAutoRelease<IXMLDOMParseError *>::Release(v44);
      }
    }
    else
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)v11,
        "PushButtonReset::Disk::CreatePartition",
        "base\\reset\\util\\src\\diskpart.cpp",
        1577,
        L"Failed to cast disk to IVdsCreatePartitionEx");
      v44[0] = &RAII::CAutoRelease<IVdsCreatePartitionEx *>::`vftable';
      RAII::CAutoRelease<IXMLDOMParseError *>::Release(v44);
    }
  }
  else
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)v11,
      "PushButtonReset::Disk::CreatePartition",
      "base\\reset\\util\\src\\diskpart.cpp",
      1553,
      L"Failed to get disk properties");
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18003a678  push    rbp
0x18003a67a  push    rbx
0x18003a67b  push    rsi
0x18003a67c  push    rdi
0x18003a67d  push    r12
0x18003a67f  push    r13
0x18003a681  push    r14
0x18003a683  push    r15
0x18003a685  lea     rbp, [rsp-1D8h]
0x18003a68d  sub     rsp, 2D8h
0x18003a694  mov     rax, cs:__security_cookie
0x18003a69b  xor     rax, rsp
0x18003a69e  mov     [rbp+210h+var_50], rax
0x18003a6a5  mov     r15, r9
0x18003a6a8  mov     r13, r8
0x18003a6ab  mov     edi, edx
0x18003a6ad  mov     r12, rcx
0x18003a6b0  mov     rax, [rbp+210h+arg_28]
0x18003a6b7  mov     [rbp+210h+var_268], rax
0x18003a6bb  xor     esi, esi
0x18003a6bd  mov     [rbp+210h+var_D0.Data1], esi
0x18003a6c3  xor     edx, edx; Val
0x18003a6c5  lea     r8d, [rsi+7Ch]; Size
0x18003a6c9  lea     rcx, [rbp+210h+var_D0.Data2]; void *
0x18003a6d0  call    memset_0
0x18003a6d5  mov     rax, [r12]
0x18003a6d9  mov     rcx, r12
0x18003a6dc  mov     rax, [rax+18h]
0x18003a6e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a6e5  mov     r8, rax
0x18003a6e8  mov     rcx, [rax]
0x18003a6eb  mov     rax, [rcx+18h]
0x18003a6ef  lea     rdx, [rbp+210h+var_D0]
0x18003a6f6  mov     rcx, r8
0x18003a6f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a6fe  mov     ebx, eax
0x18003a700  test    eax, eax
0x18003a702  jns     short loc_18003A735
0x18003a704  lea     rax, aFailedToGetDis; "Failed to get disk properties"
0x18003a70b  mov     [rsp+310h+var_2E8], rax
0x18003a710  mov     dword ptr [rsp+310h+var_2F0], 611h
0x18003a718  lea     r9, aBaseResetUtilS_2; "base\\reset\\util\\src\\diskpart.cpp"
0x18003a71f  lea     r8, aPushbuttonrese_58; "PushButtonReset::Disk::CreatePartition"
0x18003a726  mov     edx, ebx
0x18003a728  lea     ecx, [rsi+2]
0x18003a72b  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18003a730  jmp     loc_18003B31B
0x18003a735  mov     eax, [rbp+210h+var_8C]
0x18003a73b  cmp     eax, 1
0x18003a73e  jz      short loc_18003A77F
0x18003a740  mov     [rsp+310h+var_2E0], eax
0x18003a744  lea     rax, aThisOverloadCa_0; "This overload can only be called on MBR"...
0x18003a74b  mov     [rsp+310h+var_2E8], rax
0x18003a750  mov     dword ptr [rsp+310h+var_2F0], 617h
0x18003a758  lea     r9, aBaseResetUtilS_2; "base\\reset\\util\\src\\diskpart.cpp"
0x18003a75f  lea     r8, aPushbuttonrese_58; "PushButtonReset::Disk::CreatePartition"
0x18003a766  mov     edx, 80070001h
0x18003a76b  mov     ecx, 2
0x18003a770  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18003a775  mov     eax, 80070001h
0x18003a77a  jmp     loc_18003B31D
0x18003a77f  cmp     edi, 0FFh
0x18003a785  jbe     short loc_18003A7C6
0x18003a787  mov     [rsp+310h+var_2E0], edi
0x18003a78b  lea     rax, aInvalidMbrType; "Invalid MBR type ID (must be in [0-255]"...
0x18003a792  mov     [rsp+310h+var_2E8], rax
0x18003a797  mov     dword ptr [rsp+310h+var_2F0], 61Dh
0x18003a79f  lea     r9, aBaseResetUtilS_2; "base\\reset\\util\\src\\diskpart.cpp"
0x18003a7a6  lea     r8, aPushbuttonrese_58; "PushButtonReset::Disk::CreatePartition"
0x18003a7ad  mov     edx, 80070057h
0x18003a7b2  mov     ecx, 2
0x18003a7b7  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18003a7bc  mov     eax, 80070057h
0x18003a7c1  jmp     loc_18003B31D
0x18003a7c6  xor     edx, edx; Val
0x18003a7c8  lea     r8d, [rdx+78h]; Size
0x18003a7cc  lea     rcx, [rbp+210h+var_150]; void *
0x18003a7d3  call    memset_0
0x18003a7d8  mov     [rbp+210h+var_150], 1
0x18003a7e2  mov     [rbp+210h+var_147], sil
0x18003a7e9  mov     [rbp+210h+var_148], dil
0x18003a7f0  mov     [rsp+310h+var_2C8], rsi
0x18003a7f5  lea     r14, ??_7?$CAutoRelease@PEAUIVdsCreatePartitionEx@@@RAII@@6B@; const RAII::CAutoRelease<IVdsCreatePartitionEx *>::`vftable'
0x18003a7fc  mov     [rsp+310h+var_2D0], r14
0x18003a801  mov     rax, [r12]
0x18003a805  mov     rcx, r12
0x18003a808  mov     rax, [rax+18h]
0x18003a80c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a811  mov     rdi, rax
0x18003a814  mov     rcx, [rax]
0x18003a817  mov     rbx, [rcx]
0x18003a81a  mov     rcx, [rsp+310h+var_2D0]
0x18003a81f  mov     rax, [rcx+8]
0x18003a823  lea     rcx, [rsp+310h+var_2D0]
0x18003a828  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a82d  mov     r8, rax
0x18003a830  lea     rdx, IID_IVdsCreatePartitionEx
0x18003a837  mov     rcx, rdi
0x18003a83a  mov     rax, rbx
0x18003a83d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a842  mov     ebx, eax
0x18003a844  test    eax, eax
0x18003a846  jns     short loc_18003A88C
0x18003a848  lea     rax, aFailedToCastDi_2; "Failed to cast disk to IVdsCreatePartit"...
0x18003a84f  mov     [rsp+310h+var_2E8], rax
0x18003a854  mov     dword ptr [rsp+310h+var_2F0], 629h
0x18003a85c  lea     r9, aBaseResetUtilS_2; "base\\reset\\util\\src\\diskpart.cpp"
0x18003a863  lea     r8, aPushbuttonrese_58; "PushButtonReset::Disk::CreatePartition"
0x18003a86a  mov     edx, ebx
0x18003a86c  mov     ecx, 2
0x18003a871  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18003a876  nop
0x18003a877  mov     [rsp+310h+var_2D0], r14
0x18003a87c  lea     rcx, [rsp+310h+var_2D0]
0x18003a881  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x18003a886  nop
0x18003a887  jmp     loc_18003B31B
0x18003a88c  mov     r14d, [rbp+210h+var_A0]
0x18003a893  xor     edx, edx
0x18003a895  mov     rax, r13
0x18003a898  div     r14
0x18003a89b  mov     rsi, rdx
0x18003a89e  sub     r15, r14
0x18003a8a1  add     r15, rdx
0x18003a8a4  xor     edx, edx
0x18003a8a6  mov     rax, r15
0x18003a8a9  div     r14
0x18003a8ac  sub     r15, rdx
0x18003a8af  mov     [rsp+310h+var_2B8], 0
0x18003a8b8  lea     rax, ??_7?$CAutoRelease@PEAUIVdsAsync@@@RAII@@6B@; const RAII::CAutoRelease<IVdsAsync *>::`vftable'
0x18003a8bf  mov     [rsp+310h+var_2C0], rax
0x18003a8c4  mov     rax, [rsp+310h+var_2D0]
0x18003a8c9  lea     rcx, [rsp+310h+var_2D0]
0x18003a8ce  mov     rax, [rax+18h]
0x18003a8d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a8d7  mov     rdi, rax
0x18003a8da  mov     rcx, [rax]
0x18003a8dd  mov     rbx, [rcx+18h]
0x18003a8e1  mov     rcx, [rsp+310h+var_2C0]
0x18003a8e6  mov     rax, [rcx+8]
0x18003a8ea  lea     rcx, [rsp+310h+var_2C0]
0x18003a8ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a8f4  sub     r13, rsi
0x18003a8f7  lea     rdx, [r14+r13]
0x18003a8fb  mov     [rsp+310h+var_2E8], rax
0x18003a900  lea     rax, [rbp+210h+var_150]
0x18003a907  mov     [rsp+310h+var_2F0], rax
0x18003a90c  xor     r9d, r9d
0x18003a90f  mov     r8, r15
0x18003a912  mov     rcx, rdi
0x18003a915  mov     rax, rbx
0x18003a918  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a91d  mov     ebx, eax
0x18003a91f  xor     r13d, r13d
0x18003a922  test    eax, eax
0x18003a924  jns     short loc_18003A987
0x18003a926  lea     rax, aFailedToCreate_13; "Failed to create partition"
0x18003a92d  mov     [rsp+310h+var_2E8], rax
0x18003a932  mov     dword ptr [rsp+310h+var_2F0], 62Fh
0x18003a93a  lea     r9, aBaseResetUtilS_2; "base\\reset\\util\\src\\diskpart.cpp"
0x18003a941  lea     r8, aPushbuttonrese_58; "PushButtonReset::Disk::CreatePartition"
0x18003a948  mov     edx, ebx
0x18003a94a  lea     ecx, [r13+2]
0x18003a94e  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18003a953  nop
0x18003a954  lea     rax, ??_7?$CAutoRelease@PEAUIVdsAsync@@@RAII@@6B@; const RAII::CAutoRelease<IVdsAsync *>::`vftable'
0x18003a95b  mov     [rsp+310h+var_2C0], rax
0x18003a960  lea     rcx, [rsp+310h+var_2C0]
0x18003a965  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x18003a96a  nop
0x18003a96b  lea     rax, ??_7?$CAutoRelease@PEAUIVdsCreatePartitionEx@@@RAII@@6B@; const RAII::CAutoRelease<IVdsCreatePartitionEx *>::`vftable'
0x18003a972  mov     [rsp+310h+var_2D0], rax
0x18003a977  lea     rcx, [rsp+310h+var_2D0]
0x18003a97c  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x18003a981  nop
0x18003a982  jmp     loc_18003B31B
0x18003a987  xorps   xmm0, xmm0
0x18003a98a  movups  [rbp+210h+var_250], xmm0
0x18003a98e  movups  [rbp+210h+var_240], xmm0
0x18003a992  mov     rax, [rsp+310h+var_2C0]
0x18003a997  lea     rcx, [rsp+310h+var_2C0]
0x18003a99c  mov     rax, [rax+20h]
0x18003a9a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a9a5  mov     rcx, rax
0x18003a9a8  lea     rdx, [rbp+210h+var_250]
0x18003a9ac  call    PbrVdsWait
0x18003a9b1  mov     ebx, eax
0x18003a9b3  test    eax, eax
0x18003a9b5  jns     short loc_18003AA19
0x18003a9b7  lea     rax, aFailedToWaitFo; "Failed to wait for partition creation t"...
0x18003a9be  mov     [rsp+310h+var_2E8], rax
0x18003a9c3  mov     dword ptr [rsp+310h+var_2F0], 633h
0x18003a9cb  lea     r9, aBaseResetUtilS_2; "base\\reset\\util\\src\\diskpart.cpp"
0x18003a9d2  lea     r8, aPushbuttonrese_58; "PushButtonReset::Disk::CreatePartition"
0x18003a9d9  mov     edx, ebx
0x18003a9db  mov     ecx, 2
0x18003a9e0  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18003a9e5  nop
0x18003a9e6  lea     rax, ??_7?$CAutoRelease@PEAUIVdsAsync@@@RAII@@6B@; const RAII::CAutoRelease<IVdsAsync *>::`vftable'
0x18003a9ed  mov     [rsp+310h+var_2C0], rax
0x18003a9f2  lea     rcx, [rsp+310h+var_2C0]
0x18003a9f7  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x18003a9fc  nop
0x18003a9fd  lea     rax, ??_7?$CAutoRelease@PEAUIVdsCreatePartitionEx@@@RAII@@6B@; const RAII::CAutoRelease<IVdsCreatePartitionEx *>::`vftable'
0x18003aa04  mov     [rsp+310h+var_2D0], rax
0x18003aa09  lea     rcx, [rsp+310h+var_2D0]
0x18003aa0e  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x18003aa13  nop
0x18003aa14  jmp     loc_18003B31B
0x18003aa19  mov     r14, [rbp+210h+var_268]
0x18003aa1d  test    r14, r14
0x18003aa20  jz      loc_18003B2ED
0x18003aa26  mov     [rsp+310h+var_298], r13
0x18003aa2b  lea     rsi, ??_7?$CAutoRelease@PEAUIVdsService@@@RAII@@6B@; const RAII::CAutoRelease<IVdsService *>::`vftable'
0x18003aa32  mov     [rsp+310h+var_2A0], rsi
0x18003aa37  lea     rcx, [rsp+310h+var_2A0]
0x18003aa3c  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x18003aa41  mov     rcx, rax; struct IVdsService **
0x18003aa44  call    ?Get@PbrVdsServiceCache@@SAJPEAPEAUIVdsService@@@Z; PbrVdsServiceCache::Get(IVdsService * *)
0x18003aa49  mov     ebx, eax
0x18003aa4b  test    eax, eax
0x18003aa4d  jns     short loc_18003AAC1
0x18003aa4f  lea     rax, aFailedToInitia_13; "Failed to initialize VDS"
0x18003aa56  mov     [rsp+310h+var_2E8], rax
0x18003aa5b  mov     dword ptr [rsp+310h+var_2F0], 639h
0x18003aa63  lea     r9, aBaseResetUtilS_2; "base\\reset\\util\\src\\diskpart.cpp"
0x18003aa6a  lea     r8, aPushbuttonrese_58; "PushButtonReset::Disk::CreatePartition"
0x18003aa71  mov     edx, ebx
0x18003aa73  mov     ecx, 2
0x18003aa78  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18003aa7d  nop
0x18003aa7e  mov     [rsp+310h+var_2A0], rsi
0x18003aa83  lea     rcx, [rsp+310h+var_2A0]
0x18003aa88  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x18003aa8d  nop
0x18003aa8e  lea     rax, ??_7?$CAutoRelease@PEAUIVdsAsync@@@RAII@@6B@; const RAII::CAutoRelease<IVdsAsync *>::`vftable'
0x18003aa95  mov     [rsp+310h+var_2C0], rax
0x18003aa9a  lea     rcx, [rsp+310h+var_2C0]
0x18003aa9f  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x18003aaa4  nop
0x18003aaa5  lea     rax, ??_7?$CAutoRelease@PEAUIVdsCreatePartitionEx@@@RAII@@6B@; const RAII::CAutoRelease<IVdsCreatePartitionEx *>::`vftable'
0x18003aaac  mov     [rsp+310h+var_2D0], rax
0x18003aab1  lea     rcx, [rsp+310h+var_2D0]
0x18003aab6  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x18003aabb  nop
0x18003aabc  jmp     loc_18003B31B
0x18003aac1  mov     rax, [rsp+310h+var_2A0]
0x18003aac6  lea     rcx, [rsp+310h+var_2A0]
0x18003aacb  mov     rax, [rax+18h]
0x18003aacf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aad4  mov     rdx, rax
0x18003aad7  mov     rcx, [rax]
0x18003aada  mov     rax, [rcx+68h]
0x18003aade  mov     rcx, rdx
0x18003aae1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aae6  mov     ebx, eax
0x18003aae8  test    eax, eax
0x18003aaea  jns     short loc_18003AB5E
0x18003aaec  lea     rax, aFailedToRefres; "Failed to refresh VDS state"
0x18003aaf3  mov     [rsp+310h+var_2E8], rax
0x18003aaf8  mov     dword ptr [rsp+310h+var_2F0], 63Ch
0x18003ab00  lea     r9, aBaseResetUtilS_2; "base\\reset\\util\\src\\diskpart.cpp"
0x18003ab07  lea     r8, aPushbuttonrese_58; "PushButtonReset::Disk::CreatePartition"
0x18003ab0e  mov     edx, ebx
0x18003ab10  mov     ecx, 2
0x18003ab15  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18003ab1a  nop
0x18003ab1b  mov     [rsp+310h+var_2A0], rsi
0x18003ab20  lea     rcx, [rsp+310h+var_2A0]
0x18003ab25  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x18003ab2a  nop
0x18003ab2b  lea     rax, ??_7?$CAutoRelease@PEAUIVdsAsync@@@RAII@@6B@; const RAII::CAutoRelease<IVdsAsync *>::`vftable'
0x18003ab32  mov     [rsp+310h+var_2C0], rax
0x18003ab37  lea     rcx, [rsp+310h+var_2C0]
0x18003ab3c  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x18003ab41  nop
0x18003ab42  lea     rax, ??_7?$CAutoRelease@PEAUIVdsCreatePartitionEx@@@RAII@@6B@; const RAII::CAutoRelease<IVdsCreatePartitionEx *>::`vftable'
0x18003ab49  mov     [rsp+310h+var_2D0], rax
0x18003ab4e  lea     rcx, [rsp+310h+var_2D0]
0x18003ab53  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x18003ab58  nop
0x18003ab59  jmp     loc_18003B31B
0x18003ab5e  mov     r15, qword ptr [rbp+210h+var_250+8]
0x18003ab62  mov     [rsp+310h+var_2A8], r13
0x18003ab67  lea     rax, ??_7?$CAutoPbrDelete@PEAVPartition@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable'
0x18003ab6e  mov     [rsp+310h+var_2B0], rax
0x18003ab73  mov     [rbp+210h+var_288], r13
0x18003ab77  lea     rax, ??_7?$CAutoRelease@PEAUIVdsAdvancedDisk@@@RAII@@6B@; const RAII::CAutoRelease<IVdsAdvancedDisk *>::`vftable'
0x18003ab7e  mov     [rbp+210h+var_290], rax
0x18003ab82  mov     rax, [r12]
0x18003ab86  mov     rcx, r12
0x18003ab89  mov     rax, [rax+18h]
0x18003ab8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ab92  mov     rdi, rax
0x18003ab95  mov     rcx, [rax]
0x18003ab98  mov     rbx, [rcx]
0x18003ab9b  mov     rcx, [rbp+210h+var_290]
0x18003ab9f  mov     rax, [rcx+8]
0x18003aba3  lea     rcx, [rbp+210h+var_290]
0x18003aba7  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
