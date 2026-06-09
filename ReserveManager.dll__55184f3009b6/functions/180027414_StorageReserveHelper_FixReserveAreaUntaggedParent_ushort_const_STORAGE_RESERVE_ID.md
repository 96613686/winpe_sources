# StorageReserveHelper::FixReserveAreaUntaggedParent(ushort const *,_STORAGE_RESERVE_ID)

- ea: `0x180027414`
- end: `0x180027c23`
- name: `?FixReserveAreaUntaggedParent@StorageReserveHelper@@YAJPEBGW4_STORAGE_RESERVE_ID@@@Z`
- size: `2063`
- prototype: `__int64 __fastcall(StorageReserveHelper *this, const unsigned __int16 *, __int64)`
- caller_count: `2`
- callee_count: `28`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180013600`
- `0x180021a28`

## callees

- `0x180003870`
- `0x180003894`
- `0x180003c84`
- `0x180004164`
- `0x1800042f4`
- `0x1800044e0`
- `0x18000a0cc`
- `0x18000a0f4`
- `0x18000fef0`
- `0x1800256a0`
- `0x180025b48`
- `0x180025c1c`
- `0x180025cdc`
- `0x180025ed4`
- `0x180025fc0`
- `0x18002603c`
- `0x180026288`
- `0x180026eb8`
- `0x18002702c`
- `0x180027414`
- `0x180028644`
- `0x18002a440`
- `0x18002afa8`
- `0x18002c9c4`
- `0x18002d33c`
- `0x18002d494`
- `0x18002de04`
- `0x180031bf8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18002790d`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18002790d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027a81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027a81`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027af5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027bcf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027af5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027bcf`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180027737`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180027737`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18002780b`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18002780b`

## pseudocode

```c
__int64 __fastcall StorageReserveHelper::FixReserveAreaUntaggedParent(
        StorageReserveHelper *this,
        const unsigned __int16 *a2,
        __int64 a3)
{
  _BYTE *v4; // rbx
  __int64 v5; // rdi
  const unsigned __int16 *v6; // rdx
  int v7; // eax
  StorageReserveHelper::Internal *v8; // rcx
  int LastError; // ebx
  signed int Dependencies; // r14d
  _WORD *v11; // rax
  _WORD *v12; // r13
  unsigned __int64 v13; // rcx
  unsigned __int64 v14; // r8
  StorageReserveHelper *v15; // r9
  __int64 v16; // rax
  _WORD *v17; // rdx
  __int16 v18; // r10
  unsigned __int64 i; // rsi
  _BYTE *v20; // rdi
  _WORD *v21; // rbx
  _BYTE *v22; // rsi
  __int64 v23; // rdi
  _BYTE *j; // rbx
  _DWORD *v25; // r15
  const char *v26; // r9
  HANDLE FileW; // r12
  void *v28; // rbx
  unsigned int *v29; // rdi
  DWORD v30; // esi
  unsigned int v31; // r13d
  int v32; // eax
  enum _STORAGE_RESERVE_ID *v33; // r9
  char *v34; // rsi
  void **v35; // r13
  __int64 v36; // rcx
  bool v37; // zf
  char *v38; // rcx
  __int64 v39; // rdi
  __int64 v40; // rdi
  void *v41; // r14
  wchar_t *v42; // rax
  __int64 v43; // rax
  int v44; // edi
  __int64 v45; // r8
  __int64 v46; // r8
  signed int v47; // eax
  unsigned __int16 v48; // r8
  struct StorageReserveTelemetry::Internal::SRProvider *v49; // rax
  unsigned __int16 *v50; // rdi
  __int64 v51; // rcx
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  char v55[4]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v56; // [rsp+54h] [rbp-ACh]
  unsigned int v57[2]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v58; // [rsp+60h] [rbp-A0h]
  int v59; // [rsp+64h] [rbp-9Ch]
  DWORD k; // [rsp+68h] [rbp-98h]
  __int64 v61; // [rsp+70h] [rbp-90h]
  unsigned __int16 *v62; // [rsp+78h] [rbp-88h]
  int v63; // [rsp+80h] [rbp-80h] BYREF
  unsigned int *v64; // [rsp+88h] [rbp-78h]
  unsigned __int64 v65; // [rsp+90h] [rbp-70h]
  unsigned __int64 v66; // [rsp+98h] [rbp-68h]
  _DWORD *v67; // [rsp+A0h] [rbp-60h] BYREF
  void *Block; // [rsp+A8h] [rbp-58h]
  __int64 v69; // [rsp+B0h] [rbp-50h]
  __int128 v70; // [rsp+B8h] [rbp-48h]
  DWORD BytesReturned; // [rsp+D0h] [rbp-30h] BYREF
  int v72; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v73; // [rsp+DCh] [rbp-24h]
  __int64 v74; // [rsp+E8h] [rbp-18h]
  unsigned __int64 v75; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v76; // [rsp+F8h] [rbp-8h] BYREF
  void *v77; // [rsp+108h] [rbp+8h]
  char v78[8]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE *v79; // [rsp+118h] [rbp+18h]
  __int64 v80; // [rsp+120h] [rbp+20h]
  unsigned __int64 v81; // [rsp+128h] [rbp+28h]
  __int64 v82; // [rsp+130h] [rbp+30h]
  __int64 v83; // [rsp+138h] [rbp+38h]
  _BYTE v84[240]; // [rsp+140h] [rbp+40h] BYREF
  _QWORD v85[42]; // [rsp+230h] [rbp+130h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3D8h] [rbp+2D8h]

  v69 = -2;
  v62 = (unsigned __int16 *)this;
  wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v85,
    "FixReserveAreaUntaggedParent",
    a3);
  v85[0] = &StorageReserveTelemetry::Internal::SRProvider::FixReserveAreaUntaggedParent::`vftable';
  StorageReserveTelemetry::Internal::SRProvider::FixReserveAreaUntaggedParent::StartActivity(
    (StorageReserveTelemetry::Internal::SRProvider::FixReserveAreaUntaggedParent *)v85,
    (const unsigned __int16 *)this,
    2u);
  BytesReturned = 0;
  v79 = v84;
  v80 = 0;
  v81 = 7;
  v82 = 0;
  v83 = 35;
  v4 = v84;
  v5 = 7;
  do
  {
    BUCL::HashTable::CTable<BUCL::Rtl::CSwappableValueTableTraits<StorageReserveHelper::Internal::CCaseInsensitiveNullTerminatedLUnicodeStringTableTraits,unsigned long>>::CBucketChain::CBucketChain(v4);
    v4 += 32;
    --v5;
  }
  while ( v5 );
  v76 = 0;
  v77 = 0;
  v72 = 0;
  v74 = 0;
  v73 = 0;
  v7 = StorageReserveHelper::Internal::AdjustTokenPrivilege::Enable(
         (StorageReserveHelper::Internal::AdjustTokenPrivilege *)&v72,
         v6);
  LastError = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x31E,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\storagereserve\\storagereservehelper.cpp",
      (const char *)(unsigned int)v7,
      dwCreationDisposition);
    StorageReserveHelper::Internal::AdjustTokenPrivilege::~AdjustTokenPrivilege((StorageReserveHelper::Internal::AdjustTokenPrivilege *)&v72);
    BUCL::HashTable::CTable<BUCL::Rtl::CSwappableValueTableTraits<StorageReserveHelper::Internal::CCaseInsensitiveNullTerminatedLUnicodeStringTableTraits,unsigned long>>::~CTable<BUCL::Rtl::CSwappableValueTableTraits<StorageReserveHelper::Internal::CCaseInsensitiveNullTerminatedLUnicodeStringTableTraits,unsigned long>>(v78);
    goto LABEL_94;
  }
  Dependencies = StorageReserveHelper::Internal::LoadDependencies(v8);
  if ( Dependencies < 0 )
  {
    StorageReserveHelper::Internal::AdjustTokenPrivilege::~AdjustTokenPrivilege((StorageReserveHelper::Internal::AdjustTokenPrivilege *)&v72);
    BUCL::HashTable::CTable<BUCL::Rtl::CSwappableValueTableTraits<StorageReserveHelper::Internal::CCaseInsensitiveNullTerminatedLUnicodeStringTableTraits,unsigned long>>::~CTable<BUCL::Rtl::CSwappableValueTableTraits<StorageReserveHelper::Internal::CCaseInsensitiveNullTerminatedLUnicodeStringTableTraits,unsigned long>>(v78);
LABEL_93:
    LastError = Dependencies;
    goto LABEL_94;
  }
  if ( !this )
  {
    LastError = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x328,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\storagereserve\\storagereservehelper.cpp",
      (const char *)0x80070057LL,
      dwCreationDisposition);
    StorageReserveHelper::Internal::AdjustTokenPrivilege::~AdjustTokenPrivilege((StorageReserveHelper::Internal::AdjustTokenPrivilege *)&v72);
    BUCL::HashTable::CTable<BUCL::Rtl::CSwappableValueTableTraits<StorageReserveHelper::Internal::CCaseInsensitiveNullTerminatedLUnicodeStringTableTraits,unsigned long>>::~CTable<BUCL::Rtl::CSwappableValueTableTraits<StorageReserveHelper::Internal::CCaseInsensitiveNullTerminatedLUnicodeStringTableTraits,unsigned long>>(v78);
    goto LABEL_94;
  }
  v11 = operator new(0x10000u);
  v12 = v11;
  Block = v11;
  v13 = -1;
  do
    ++v13;
  while ( *((_WORD *)this + v13) );
  if ( v13 > 0x7FFFFFFE )
  {
    LastError = -2147024809;
    *v11 = 0;
    goto LABEL_20;
  }
  v14 = v13;
  v15 = this;
  v16 = 0x8000;
  v17 = v12;
  LastError = 0;
  while ( v14 )
  {
    v18 = *(_WORD *)v15;
    if ( *(_WORD *)v15 )
    {
      v15 = (StorageReserveHelper *)((char *)v15 + 2);
      *v17++ = v18;
      --v14;
      if ( --v16 )
        continue;
    }
    if ( !v16 )
    {
      --v17;
      LastError = -2147024774;
    }
    break;
  }
  *v17 = 0;
  if ( LastError < 0 )
  {
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x32E,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\storagereserve\\storagereservehelper.cpp",
      (const char *)(unsigned int)LastError,
      dwCreationDisposition);
    StorageReserveHelper::Internal::AdjustTokenPrivilege::~AdjustTokenPrivilege((StorageReserveHelper::Internal::AdjustTokenPrivilege *)&v72);
    BUCL::HashTable::CTable<BUCL::Rtl::CSwappableValueTableTraits<StorageReserveHelper::Internal::CCaseInsensitiveNullTerminatedLUnicodeStringTableTraits,unsigned long>>::~CTable<BUCL::Rtl::CSwappableValueTableTraits<StorageReserveHelper::Internal::CCaseInsensitiveNullTerminatedLUnicodeStringTableTraits,unsigned long>>(v78);
    operator delete(v12);
    goto LABEL_94;
  }
  if ( v12[v13 - 1] == 92 )
    v12[v13 - 1] = 0;
  for ( i = 0; i < v81; ++i )
  {
    v20 = &v79[32 * i];
    v17 = *(_WORD **)v20;
    if ( *(_QWORD *)v20 && v17 != (_WORD *)v20 )
    {
      do
      {
        v21 = *(_WORD **)v17;
        BUCL::HashTable::CTable<BUCL::Rtl::CSwappableValueTableTraits<StorageReserveHelper::Internal::CCaseInsensitiveNullTerminatedLUnicodeStringTableTraits,unsigned long>>::DeallocateBucket(
          v78,
          v17,
          v14,
          v15);
        v17 = v21;
      }
      while ( v21 != (_WORD *)v20 );
    }
    *(_QWORD *)v20 = v20;
    *((_QWORD *)v20 + 1) = v20;
    *((_QWORD *)v20 + 2) = v20;
    *((_QWORD *)v20 + 3) = 0;
  }
  if ( v79 != v84 )
  {
    if ( v79 )
    {
      v22 = v79 - 8;
      v23 = *((_QWORD *)v79 - 1);
      for ( j = &v79[32 * v23]; v23; --v23 )
      {
        j -= 32;
        BUCL::HashTable::CTable<BUCL::Rtl::CSwappableValueTableTraits<StorageReserveHelper::Internal::CCaseInsensitiveNullTerminatedLUnicodeStringTableTraits,unsigned long>>::CBucketChain::~CBucketChain(
          j,
          v17,
          v14,
          v15);
      }
      operator delete(v22);
    }
    v79 = v84;
    v81 = 7;
  }
  v82 = 0;
  v25 = operator new[](0x14u);
  v25[1] = 103;
  v25[2] = 3;
  *v25 = 1;
  v25[4] = 2;
  FileW = CreateFileW(v12, 0x100u, 3u, 0, 3u, 0x2000080u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x34F,
                  (unsigned int)"onecore\\drivers\\storage\\storsvc\\storagereserve\\storagereservehelper.cpp",
                  v26);
    StorageReserveHelper::Internal::AdjustTokenPrivilege::~AdjustTokenPrivilege((StorageReserveHelper::Internal::AdjustTokenPrivilege *)&v72);
    BUCL::HashTable::CTable<BUCL::Rtl::CSwappableValueTableTraits<StorageReserveHelper::Internal::CCaseInsensitiveNullTerminatedLUnicodeStringTableTraits,unsigned long>>::~CTable<BUCL::Rtl::CSwappableValueTableTraits<StorageReserveHelper::Internal::CCaseInsensitiveNullTerminatedLUnicodeStringTableTraits,unsigned long>>(v78);
    operator delete(v12);
    operator delete(v25);
    goto LABEL_94;
  }
  v28 = 0;
  v29 = 0;
  v64 = 0;
  v30 = 0x2000000;
  v31 = 0;
  v56 = 0;
  v58 = 0;
  v57[1] = 0;
  v65 = 0;
  v66 = 0;
LABEL_37:
  v32 = 1;
  for ( k = v30; ; v30 = k )
  {
    if ( v32 )
    {
      if ( v28 )
        operator delete(v28);
      v28 = operator new[](v30);
      v29 = (unsigned int *)v28;
      v64 = (unsigned int *)v28;
    }
    if ( !DeviceIoControl(FileW, 0x90277u, v25, 0x14u, v29, v30, &BytesReturned, 0) )
    {
      v47 = GetLastError();
      if ( v47 != 122 )
      {
        if ( v47 != 38 )
        {
          if ( v47 > 0 )
            Dependencies = (unsigned __int16)v47 | 0x80070000;
          else
            Dependencies = v47;
        }
        if ( v82
          && (v49 = StorageReserveTelemetry::Internal::SRProvider::Instance(), *((_QWORD *)v49 + 1))
          && **((_DWORD **)v49 + 1) )
        {
          StorageReserveTelemetry::Internal::SRProvider::Instance();
          v50 = v62;
          StorageReserveTelemetry::Internal::SRProvider::TopPaths_(v51, v78, v62, 2);
        }
        else
        {
          v50 = v62;
        }
        StorageReserveTelemetry::Internal::SRProvider::FixReserveAreaUntaggedParent::Stop(
          (StorageReserveTelemetry::Internal::SRProvider::FixReserveAreaUntaggedParent *)v85,
          v50,
          v48,
          v31,
          v58,
          v57[1],
          v66,
          v65,
          Dependencies);
        StorageReserveHelper::Internal::AdjustTokenPrivilege::~AdjustTokenPrivilege((StorageReserveHelper::Internal::AdjustTokenPrivilege *)&v72);
        BUCL::HashTable::CTable<BUCL::Rtl::CSwappableValueTableTraits<StorageReserveHelper::Internal::CCaseInsensitiveNullTerminatedLUnicodeStringTableTraits,unsigned long>>::~CTable<BUCL::Rtl::CSwappableValueTableTraits<StorageReserveHelper::Internal::CCaseInsensitiveNullTerminatedLUnicodeStringTableTraits,unsigned long>>(v78);
        operator delete(Block);
        if ( v28 )
          operator delete(v28);
        operator delete(v25);
        if ( FileW )
          CloseHandle(FileW);
        goto LABEL_93;
      }
      v30 = BytesReturned;
      goto LABEL_37;
    }
    v34 = (char *)v29 + v29[1];
    v59 = 0;
    if ( *v29 )
      break;
LABEL_72:
    v32 = 0;
    v25[1] &= ~1u;
  }
  while ( 1 )
  {
    if ( !*((_DWORD *)v34 + 6) || (v34[12] & 0x10) != 0 )
      goto LABEL_71;
    v35 = (void **)&v34[*((unsigned int *)v34 + 6)];
    v36 = *((unsigned int *)v34 + 7);
    v37 = &v34[v36] == 0;
    v38 = &v34[v36];
    v61 = 0;
    if ( !v37 )
    {
      v39 = 0;
      do
      {
        if ( (v38[8] & 4) == 0 )
          v39 += *((_QWORD *)v38 + 3);
        if ( !*((_DWORD *)v38 + 1) )
          break;
        v38 += *((unsigned int *)v38 + 1);
      }
      while ( v38 );
      v61 = v39;
      v29 = v64;
    }
    while ( 1 )
    {
      if ( *((_DWORD *)v35 + 1) != 2 )
      {
        ++v57[1];
        v57[0] = 0;
        if ( (int)StorageReserveHelper::Internal::QueryAreaID(
                    (StorageReserveHelper::Internal *)FileW,
                    v35[1],
                    (unsigned __int64)v57,
                    v33) >= 0
          && v57[0] != 2 )
        {
          break;
        }
      }
      if ( !*(_DWORD *)v35 )
      {
        v31 = v56;
        goto LABEL_71;
      }
      v35 = (void **)((char *)v35 + *(unsigned int *)v35);
    }
    v40 = *((unsigned int *)v35 + 4);
    v41 = operator new(saturated_mul((unsigned __int64)(v40 + 2) >> 1, 2u));
    memset_0(v41, 0, v40 + 2);
    memcpy_0(v41, v35 + 3, *((unsigned int *)v35 + 4));
    v42 = wcsrchr((const wchar_t *)v41, 0x5Cu);
    if ( v42 )
      *v42 = 0;
    v43 = -1;
    do
      ++v43;
    while ( *((_WORD *)v41 + v43) );
    *(_QWORD *)&v70 = 2 * v43;
    *((_QWORD *)&v70 + 1) = 2 * v43 + 2;
    v76 = v70;
    v77 = v41;
    v57[0] = 1;
    v75 = 0;
    v67 = 0;
    v55[0] = 0;
    v44 = RtlHashEncodedLBlob(&v76, RtlDecodeUtf16LE, RtlDowncaseUCSCharacter, &v75);
    if ( v44 < 0 )
      break;
    BUCL::HashTable::CTable<BUCL::Rtl::CSwappableValueTableTraits<StorageReserveHelper::Internal::CCaseInsensitiveNullTerminatedLUnicodeStringTableTraits,unsigned long>>::CBucketChain::FindOrInsertIfNotPresent<_LUNICODE_STRING,int>(
      (_DWORD)v79 + 32 * (v75 % v81),
      (unsigned int)&v63,
      (unsigned int)v78,
      (unsigned int)&v76,
      (__int64)v57,
      v75,
      (__int64)&v67,
      (__int64)v55);
    v44 = v63;
    if ( v63 < 0 )
      break;
    if ( v55[0] )
      ++*v67;
    operator delete(v41);
    if ( (unsigned int)StorageReserveHelper::Internal::SetAreaID(
                         (StorageReserveHelper::Internal *)FileW,
                         *((void **)v34 + 2),
                         v45,
                         0) == -2147024784 )
    {
      ++v58;
      v65 += v61;
      StorageReserveHelper::Internal::SetAreaID(
        (StorageReserveHelper::Internal *)FileW,
        *((void **)v34 + 2),
        v46,
        (void **)2);
      v31 = v56;
    }
    else
    {
      v31 = ++v56;
      v66 += v61;
    }
    Dependencies = 0;
    v29 = v64;
LABEL_71:
    v34 += *((unsigned int *)v34 + 1);
    if ( ++v59 >= *v29 )
      goto LABEL_72;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x3B7,
    (unsigned int)"onecore\\drivers\\storage\\storsvc\\storagereserve\\storagereservehelper.cpp",
    (const char *)(unsigned int)v44,
    dwCreationDispositiona);
  operator delete(v41);
  StorageReserveHelper::Internal::AdjustTokenPrivilege::~AdjustTokenPrivilege((StorageReserveHelper::Internal::AdjustTokenPrivilege *)&v72);
  BUCL::HashTable::CTable<BUCL::Rtl::CSwappableValueTableTraits<StorageReserveHelper::Internal::CCaseInsensitiveNullTerminatedLUnicodeStringTableTraits,unsigned long>>::~CTable<BUCL::Rtl::CSwappableValueTableTraits<StorageReserveHelper::Internal::CCaseInsensitiveNullTerminatedLUnicodeStringTableTraits,unsigned long>>(v78);
  operator delete(Block);
  if ( v28 )
    operator delete(v28);
  operator delete(v25);
  if ( FileW )
    CloseHandle(FileW);
  LastError = v44;
LABEL_94:
  v85[0] = &StorageReserveTelemetry::Internal::SRProvider::FixReserveAreaUntaggedParent::`vftable';
  wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v85);
  wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v85);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180027414  push    rbp
0x180027416  push    rbx
0x180027417  push    rsi
0x180027418  push    rdi
0x180027419  push    r12
0x18002741b  push    r13
0x18002741d  push    r14
0x18002741f  push    r15
0x180027421  lea     rbp, [rsp-298h]
0x180027429  sub     rsp, 398h
0x180027430  mov     [rbp+2D0h+var_320], 0FFFFFFFFFFFFFFFEh
0x180027438  mov     rax, cs:__security_cookie
0x18002743f  xor     rax, rsp
0x180027442  mov     [rbp+2D0h+var_50], rax
0x180027449  mov     rsi, rcx
0x18002744c  mov     [rsp+3D0h+var_358], rcx
0x180027451  lea     rdx, aFixreservearea; "FixReserveAreaUntaggedParent"
0x180027458  lea     rcx, [rbp+2D0h+var_1A0]
0x18002745f  call    ??0?$ActivityBase@VStorageReserveProvider@Internal@StorageReserveTelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180027464  lea     rax, ??_7FixReserveAreaUntaggedParent@SRProvider@Internal@StorageReserveTelemetry@@6B@; const StorageReserveTelemetry::Internal::SRProvider::FixReserveAreaUntaggedParent::`vftable'
0x18002746b  mov     [rbp+2D0h+var_1A0], rax
0x180027472  mov     r8d, 2; unsigned __int16
0x180027478  mov     rdx, rsi; unsigned __int16 *
0x18002747b  lea     rcx, [rbp+2D0h+var_1A0]; this
0x180027482  call    ?StartActivity@FixReserveAreaUntaggedParent@SRProvider@Internal@StorageReserveTelemetry@@QEAAXPEBGG@Z; StorageReserveTelemetry::Internal::SRProvider::FixReserveAreaUntaggedParent::StartActivity(ushort const *,ushort)
0x180027487  xor     r12d, r12d
0x18002748a  mov     [rbp+2D0h+BytesReturned], r12d
0x18002748e  lea     rax, [rbp+2D0h+var_290]
0x180027492  mov     [rbp+2D0h+var_2B8], rax
0x180027496  mov     [rbp+2D0h+var_2B0], r12
0x18002749a  lea     r15d, [r12+7]
0x18002749f  mov     [rbp+2D0h+var_2A8], r15
0x1800274a3  mov     [rbp+2D0h+var_2A0], r12
0x1800274a7  mov     [rbp+2D0h+var_298], 23h ; '#'
0x1800274af  lea     rbx, [rbp+2D0h+var_290]
0x1800274b3  mov     edi, r15d
0x1800274b6  mov     rcx, rbx
0x1800274b9  call    ??0CBucketChain@?$CTable@V?$CSwappableValueTableTraits@VCCaseInsensitiveNullTerminatedLUnicodeStringTableTraits@Internal@StorageReserveHelper@@K@Rtl@BUCL@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<BUCL::Rtl::CSwappableValueTableTraits<StorageReserveHelper::Internal::CCaseInsensitiveNullTerminatedLUnicodeStringTableTraits,ulong>>::CBucketChain::CBucketChain(void)
0x1800274be  add     rbx, 20h ; ' '
0x1800274c2  sub     rdi, 1
0x1800274c6  jnz     short loc_1800274B6
0x1800274c8  xorps   xmm0, xmm0
0x1800274cb  xor     eax, eax
0x1800274cd  movups  [rbp+2D0h+var_2D8], xmm0
0x1800274d1  mov     [rbp+2D0h+var_2C8], rax
0x1800274d5  mov     [rbp+2D0h+var_2F8], r12d
0x1800274d9  mov     [rbp+2D0h+var_2E8], r12
0x1800274dd  mov     [rbp+2D0h+var_2F4], rax
0x1800274e1  lea     rcx, [rbp+2D0h+var_2F8]; this
0x1800274e5  call    ?Enable@AdjustTokenPrivilege@Internal@StorageReserveHelper@@QEAAJPEBG@Z; StorageReserveHelper::Internal::AdjustTokenPrivilege::Enable(ushort const *)
0x1800274ea  mov     ebx, eax
0x1800274ec  test    eax, eax
0x1800274ee  jns     short loc_180027523
0x1800274f0  mov     rcx, [rbp+2D8h]; this
0x1800274f7  mov     r9d, eax; char *
0x1800274fa  lea     r8, aOnecoreDrivers_1; "onecore\\drivers\\storage\\storsvc\\sto"...
0x180027501  mov     edx, 31Eh; void *
0x180027506  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002750b  lea     rcx, [rbp+2D0h+var_2F8]; this
0x18002750f  call    ??1AdjustTokenPrivilege@Internal@StorageReserveHelper@@QEAA@XZ; StorageReserveHelper::Internal::AdjustTokenPrivilege::~AdjustTokenPrivilege(void)
0x180027514  lea     rcx, [rbp+2D0h+var_2C0]
0x180027518  call    ??1?$CTable@V?$CSwappableValueTableTraits@VCCaseInsensitiveNullTerminatedLUnicodeStringTableTraits@Internal@StorageReserveHelper@@K@Rtl@BUCL@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<BUCL::Rtl::CSwappableValueTableTraits<StorageReserveHelper::Internal::CCaseInsensitiveNullTerminatedLUnicodeStringTableTraits,ulong>>::~CTable<BUCL::Rtl::CSwappableValueTableTraits<StorageReserveHelper::Internal::CCaseInsensitiveNullTerminatedLUnicodeStringTableTraits,ulong>>(void)
0x18002751d  nop
0x18002751e  jmp     loc_180027BD8
0x180027523  call    ?LoadDependencies@Internal@StorageReserveHelper@@YAJXZ; StorageReserveHelper::Internal::LoadDependencies(void)
0x180027528  mov     r14d, eax
0x18002752b  test    eax, eax
0x18002752d  jns     short loc_180027547
0x18002752f  lea     rcx, [rbp+2D0h+var_2F8]; this
0x180027533  call    ??1AdjustTokenPrivilege@Internal@StorageReserveHelper@@QEAA@XZ; StorageReserveHelper::Internal::AdjustTokenPrivilege::~AdjustTokenPrivilege(void)
0x180027538  lea     rcx, [rbp+2D0h+var_2C0]
0x18002753c  call    ??1?$CTable@V?$CSwappableValueTableTraits@VCCaseInsensitiveNullTerminatedLUnicodeStringTableTraits@Internal@StorageReserveHelper@@K@Rtl@BUCL@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<BUCL::Rtl::CSwappableValueTableTraits<StorageReserveHelper::Internal::CCaseInsensitiveNullTerminatedLUnicodeStringTableTraits,ulong>>::~CTable<BUCL::Rtl::CSwappableValueTableTraits<StorageReserveHelper::Internal::CCaseInsensitiveNullTerminatedLUnicodeStringTableTraits,ulong>>(void)
0x180027541  nop
0x180027542  jmp     loc_180027BD5
0x180027547  test    rsi, rsi
0x18002754a  jnz     short loc_180027584
0x18002754c  mov     rcx, [rbp+2D8h]; this
0x180027553  mov     ebx, 80070057h
0x180027558  mov     r9d, ebx; char *
0x18002755b  lea     r8, aOnecoreDrivers_1; "onecore\\drivers\\storage\\storsvc\\sto"...
0x180027562  mov     edx, 328h; void *
0x180027567  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002756c  lea     rcx, [rbp+2D0h+var_2F8]; this
0x180027570  call    ??1AdjustTokenPrivilege@Internal@StorageReserveHelper@@QEAA@XZ; StorageReserveHelper::Internal::AdjustTokenPrivilege::~AdjustTokenPrivilege(void)
0x180027575  lea     rcx, [rbp+2D0h+var_2C0]
0x180027579  call    ??1?$CTable@V?$CSwappableValueTableTraits@VCCaseInsensitiveNullTerminatedLUnicodeStringTableTraits@Internal@StorageReserveHelper@@K@Rtl@BUCL@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<BUCL::Rtl::CSwappableValueTableTraits<StorageReserveHelper::Internal::CCaseInsensitiveNullTerminatedLUnicodeStringTableTraits,ulong>>::~CTable<BUCL::Rtl::CSwappableValueTableTraits<StorageReserveHelper::Internal::CCaseInsensitiveNullTerminatedLUnicodeStringTableTraits,ulong>>(void)
0x18002757e  nop
0x18002757f  jmp     loc_180027BD8
0x180027584  mov     ecx, 10000h; Size
0x180027589  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002758e  mov     r13, rax
0x180027591  mov     [rbp+2D0h+Block], rax
0x180027595  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180027599  inc     rcx
0x18002759c  cmp     [rsi+rcx*2], r12w
0x1800275a1  jnz     short loc_180027599
0x1800275a3  cmp     rcx, 7FFFFFFEh
0x1800275aa  jbe     short loc_1800275B7
0x1800275ac  mov     ebx, 80070057h
0x1800275b1  mov     [rax], r12w
0x1800275b5  jmp     short loc_180027602
0x1800275b7  mov     r8, rcx
0x1800275ba  mov     r9, rsi
0x1800275bd  mov     eax, 8000h
0x1800275c2  mov     rdx, r13
0x1800275c5  mov     ebx, r12d
0x1800275c8  test    r8, r8
0x1800275cb  jz      short loc_1800275FA
0x1800275cd  movzx   r10d, word ptr [r9]
0x1800275d1  test    r10w, r10w
0x1800275d5  jz      short loc_1800275EC
0x1800275d7  add     r9, 2
0x1800275db  mov     [rdx], r10w
0x1800275df  add     rdx, 2
0x1800275e3  dec     r8
0x1800275e6  sub     rax, 1
0x1800275ea  jnz     short loc_1800275C8
0x1800275ec  test    rax, rax
0x1800275ef  jnz     short loc_1800275FA
0x1800275f1  sub     rdx, 2
0x1800275f5  mov     ebx, 8007007Ah
0x1800275fa  mov     [rdx], r12w
0x1800275fe  test    ebx, ebx
0x180027600  jns     short loc_18002763D
0x180027602  mov     rcx, [rbp+2D8h]; this
0x180027609  mov     r9d, ebx; char *
0x18002760c  lea     r8, aOnecoreDrivers_1; "onecore\\drivers\\storage\\storsvc\\sto"...
0x180027613  mov     edx, 32Eh; void *
0x180027618  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002761d  lea     rcx, [rbp+2D0h+var_2F8]; this
0x180027621  call    ??1AdjustTokenPrivilege@Internal@StorageReserveHelper@@QEAA@XZ; StorageReserveHelper::Internal::AdjustTokenPrivilege::~AdjustTokenPrivilege(void)
0x180027626  lea     rcx, [rbp+2D0h+var_2C0]
0x18002762a  call    ??1?$CTable@V?$CSwappableValueTableTraits@VCCaseInsensitiveNullTerminatedLUnicodeStringTableTraits@Internal@StorageReserveHelper@@K@Rtl@BUCL@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<BUCL::Rtl::CSwappableValueTableTraits<StorageReserveHelper::Internal::CCaseInsensitiveNullTerminatedLUnicodeStringTableTraits,ulong>>::~CTable<BUCL::Rtl::CSwappableValueTableTraits<StorageReserveHelper::Internal::CCaseInsensitiveNullTerminatedLUnicodeStringTableTraits,ulong>>(void)
0x18002762f  mov     rcx, r13; Block
0x180027632  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180027637  nop
0x180027638  jmp     loc_180027BD8
0x18002763d  mov     eax, 5Ch ; '\'
0x180027642  cmp     [r13+rcx*2-2], ax
0x180027648  jnz     short loc_180027650
0x18002764a  mov     [r13+rcx*2-2], r12w
0x180027650  mov     rsi, r12
0x180027653  cmp     [rbp+2D0h+var_2A8], r12
0x180027657  jbe     short loc_18002769D
0x180027659  mov     rdi, rsi
0x18002765c  shl     rdi, 5
0x180027660  add     rdi, [rbp+2D0h+var_2B8]
0x180027664  mov     rdx, [rdi]
0x180027667  test    rdx, rdx
0x18002766a  jz      short loc_180027685
0x18002766c  cmp     rdx, rdi
0x18002766f  jz      short loc_180027685
0x180027671  mov     rbx, [rdx]
0x180027674  lea     rcx, [rbp+2D0h+var_2C0]
0x180027678  call    ?DeallocateBucket@?$CTable@V?$CSwappableValueTableTraits@VCCaseInsensitiveNullTerminatedLUnicodeStringTableTraits@Internal@StorageReserveHelper@@K@Rtl@BUCL@@@HashTable@BUCL@@AEBAXPEAVCBucket@123@@Z; BUCL::HashTable::CTable<BUCL::Rtl::CSwappableValueTableTraits<StorageReserveHelper::Internal::CCaseInsensitiveNullTerminatedLUnicodeStringTableTraits,ulong>>::DeallocateBucket(BUCL::HashTable::CTable<BUCL::Rtl::CSwappableValueTableTraits<StorageReserveHelper::Internal::CCaseInsensitiveNullTerminatedLUnicodeStringTableTraits,ulong>>::CBucket *)
0x18002767d  mov     rdx, rbx
0x180027680  cmp     rbx, rdi
0x180027683  jnz     short loc_180027671
0x180027685  mov     [rdi], rdi
0x180027688  mov     [rdi+8], rdi
0x18002768c  mov     [rdi+10h], rdi
0x180027690  mov     [rdi+18h], r12
0x180027694  inc     rsi
0x180027697  cmp     rsi, [rbp+2D0h+var_2A8]
0x18002769b  jb      short loc_180027659
0x18002769d  lea     rcx, [rbp+2D0h+var_290]
0x1800276a1  mov     rax, [rbp+2D0h+var_2B8]
0x1800276a5  cmp     rax, rcx
0x1800276a8  jz      short loc_1800276EB
0x1800276aa  test    rax, rax
0x1800276ad  jz      short loc_1800276DF
0x1800276af  lea     rsi, [rax-8]
0x1800276b3  mov     rdi, [rsi]
0x1800276b6  mov     rbx, rdi
0x1800276b9  shl     rbx, 5
0x1800276bd  add     rbx, rax
0x1800276c0  test    rdi, rdi
0x1800276c3  jz      short loc_1800276D7
0x1800276c5  sub     rbx, 20h ; ' '
0x1800276c9  mov     rcx, rbx
0x1800276cc  call    ??1CBucketChain@?$CTable@V?$CSwappableValueTableTraits@VCCaseInsensitiveNullTerminatedLUnicodeStringTableTraits@Internal@StorageReserveHelper@@K@Rtl@BUCL@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<BUCL::Rtl::CSwappableValueTableTraits<StorageReserveHelper::Internal::CCaseInsensitiveNullTerminatedLUnicodeStringTableTraits,ulong>>::CBucketChain::~CBucketChain(void)
0x1800276d1  sub     rdi, 1
0x1800276d5  jnz     short loc_1800276C5
0x1800276d7  mov     rcx, rsi; Block
0x1800276da  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800276df  lea     rax, [rbp+2D0h+var_290]
0x1800276e3  mov     [rbp+2D0h+var_2B8], rax
0x1800276e7  mov     [rbp+2D0h+var_2A8], r15
0x1800276eb  mov     [rbp+2D0h+var_2A0], r12
0x1800276ef  mov     ecx, 14h; unsigned __int64
0x1800276f4  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800276f9  mov     r15, rax
0x1800276fc  mov     dword ptr [rax+4], 67h ; 'g'
0x180027703  mov     r8d, 3; dwShareMode
0x180027709  mov     [rax+8], r8d
0x18002770d  mov     dword ptr [rax], 1
0x180027713  mov     dword ptr [rax+10h], 2
0x18002771a  mov     [rsp+3D0h+hTemplateFile], r12; hTemplateFile
0x18002771f  mov     [rsp+3D0h+dwFlagsAndAttributes], 2000080h; dwFlagsAndAttributes
0x180027727  mov     [rsp+3D0h+dwCreationDisposition], r8d; dwCreationDisposition
0x18002772c  xor     r9d, r9d; lpSecurityAttributes
0x18002772f  mov     edx, 100h; dwDesiredAccess
0x180027734  mov     rcx, r13; lpFileName
0x180027737  call    cs:__imp_CreateFileW
0x18002773d  mov     r12, rax
0x180027740  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180027744  jnz     short loc_180027789
0x180027746  mov     rcx, [rbp+2D8h]; this
0x18002774d  lea     r8, aOnecoreDrivers_1; "onecore\\drivers\\storage\\storsvc\\sto"...
0x180027754  mov     edx, 34Fh; void *
0x180027759  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002775e  mov     ebx, eax
0x180027760  lea     rcx, [rbp+2D0h+var_2F8]; this
0x180027764  call    ??1AdjustTokenPrivilege@Internal@StorageReserveHelper@@QEAA@XZ; StorageReserveHelper::Internal::AdjustTokenPrivilege::~AdjustTokenPrivilege(void)
0x180027769  lea     rcx, [rbp+2D0h+var_2C0]
0x18002776d  call    ??1?$CTable@V?$CSwappableValueTableTraits@VCCaseInsensitiveNullTerminatedLUnicodeStringTableTraits@Internal@StorageReserveHelper@@K@Rtl@BUCL@@@HashTable@BUCL@@QEAA@XZ; BUCL::HashTable::CTable<BUCL::Rtl::CSwappableValueTableTraits<StorageReserveHelper::Internal::CCaseInsensitiveNullTerminatedLUnicodeStringTableTraits,ulong>>::~CTable<BUCL::Rtl::CSwappableValueTableTraits<StorageReserveHelper::Internal::CCaseInsensitiveNullTerminatedLUnicodeStringTableTraits,ulong>>(void)
0x180027772  mov     rcx, r13; Block
0x180027775  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002777a  nop
0x18002777b  mov     rcx, r15; void *
0x18002777e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180027783  nop
0x180027784  jmp     loc_180027BD8
0x180027789  xor     r8d, r8d
0x18002778c  mov     ebx, r8d
0x18002778f  mov     edi, r8d
0x180027792  mov     [rbp+2D0h+var_348], r8
0x180027796  mov     esi, 2000000h
0x18002779b  mov     r13d, r8d
0x18002779e  mov     [rsp+3D0h+var_37C], r8d
0x1800277a3  mov     [rsp+3D0h+var_370], r8d
0x1800277a8  mov     [rsp+3D0h+var_378+4], r8d
0x1800277ad  mov     [rbp+2D0h+var_340], r8
0x1800277b1  mov     [rbp+2D0h+var_338], r8
0x1800277b5  mov     eax, 1
0x1800277ba  mov     [rsp+3D0h+var_368], esi
0x1800277be  test    eax, eax
0x1800277c0  jz      short loc_1800277E3
0x1800277c2  test    rbx, rbx
0x1800277c5  jz      short loc_1800277CF
0x1800277c7  mov     rcx, rbx; void *
0x1800277ca  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800277cf  mov     ecx, esi; unsigned __int64
0x1800277d1  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800277d6  mov     rbx, rax
0x1800277d9  mov     rdi, rax
0x1800277dc  mov     [rbp+2D0h+var_348], rax
0x1800277e0  xor     r8d, r8d
0x1800277e3  mov     [rsp+3D0h+lpOverlapped], r8; lpOverlapped
0x1800277e8  lea     rax, [rbp+2D0h+BytesReturned]
0x1800277ec  mov     [rsp+3D0h+hTemplateFile], rax; lpBytesReturned
0x1800277f1  mov     [rsp+3D0h+dwFlagsAndAttributes], esi; nOutBufferSize
0x1800277f5  mov     qword ptr [rsp+3D0h+dwCreationDisposition], rdi; int
0x1800277fa  mov     r9d, 14h; nInBufferSize
0x180027800  mov     r8, r15; lpInBuffer
0x180027803  mov     edx, 90277h; dwIoControlCode
0x180027808  mov     rcx, r12; hDevice
0x18002780b  call    cs:__imp_DeviceIoControl
0x180027811  xor     r8d, r8d
0x180027814  test    eax, eax
0x180027816  jz      loc_180027A81
0x18002781c  mov     esi, [rdi+4]
0x18002781f  add     rsi, rdi
0x180027822  mov     [rsp+3D0h+var_36C], r8d
0x180027827  cmp     [rdi], r8d
0x18002782a  jbe     loc_180027A70
0x180027830  cmp     [rsi+18h], r8d
0x180027834  jz      loc_180027A58
0x18002783a  test    byte ptr [rsi+0Ch], 10h
0x18002783e  jnz     loc_180027A58
0x180027844  mov     r13d, [rsi+18h]
0x180027848  add     r13, rsi
0x18002784b  mov     ecx, [rsi+1Ch]
0x18002784e  add     rcx, rsi
0x180027851  mov     [rsp+3D0h+var_360], r8
0x180027856  jz      short loc_18002787C
0x180027858  mov     rdi, r8
0x18002785b  test    byte ptr [rcx+8], 4
0x18002785f  jnz     short loc_180027865
0x180027861  add     rdi, [rcx+18h]
0x180027865  cmp     [rcx+4], r8d
0x180027869  jz      short loc_180027873
0x18002786b  mov     eax, [rcx+4]
0x18002786e  add     rcx, rax
0x180027871  jnz     short loc_18002785B
0x180027873  mov     [rsp+3D0h+var_360], rdi
0x180027878  mov     rdi, [rbp+2D0h+var_348]
0x18002787c  cmp     dword ptr [r13+4], 2
0x180027881  jz      short loc_1800278AB
0x180027883  inc     [rsp+3D0h+var_378+4]
0x180027887  mov     [rsp+3D0h+var_378], r8d
0x18002788c  lea     r8, [rsp+3D0h+var_378]; unsigned __int64
0x180027891  mov     rdx, [r13+8]; void *
0x180027895  mov     rcx, r12; this
0x180027898  call    ?QueryAreaID@Internal@StorageReserveHelper@@YAJPEAX_KPEAW4_STORAGE_RESERVE_ID@@@Z; StorageReserveHelper::Internal::QueryAreaID(void *,unsigned __int64,_STORAGE_RESERVE_ID *)
0x18002789d  xor     r8d, r8d
0x1800278a0  test    eax, eax
0x1800278a2  js      short loc_1800278AB
0x1800278a4  cmp     [rsp+3D0h+var_378], 2
0x1800278a9  jnz     short loc_1800278BE
  ... truncated ...
```
