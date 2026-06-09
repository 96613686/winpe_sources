# CCuChangeConsumptionHandler::GetFileInfoFromParentEnumeration(_FILE_ID_128,_FILE_ID_128,void *,CCuEventLogger *,ISyncFileSystemInterface *,IFileInfoFromDisk * *)

- ea: `0x1801194f0`
- end: `0x180119a7a`
- name: `?GetFileInfoFromParentEnumeration@CCuChangeConsumptionHandler@@CAJU_FILE_ID_128@@0PEAXPEAVCCuEventLogger@@PEAUISyncFileSystemInterface@@PEAPEAUIFileInfoFromDisk@@@Z`
- size: `1418`
- prototype: `__int64 __usercall@<rax>(struct _FILE_ID_128 *@<rcx>, struct _FILE_ID_128 *__struct_ptr@<rdx>, void *@<r8>, struct CCuEventLogger *@<r9>, struct ISyncFileSystemInterface *, struct IFileInfoFromDisk **)`
- caller_count: `1`
- callee_count: `20`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1801163e0`

## callees

- `0x180002ab0`
- `0x180007e10`
- `0x180008080`
- `0x180009188`
- `0x180011314`
- `0x18001137c`
- `0x180058d88`
- `0x18008b670`
- `0x1800bbe18`
- `0x18011621c`
- `0x18011634c`
- `0x1801194f0`
- `0x18011e7c0`
- `0x18011ede8`
- `0x18012122c`
- `0x1801220c4`
- `0x180123300`
- `0x1801237a0`
- `0x180123f60`
- `0x18013e010`

## import_xrefs

- `ntdll!NtQueryDirectoryFile` at `0x180119847`
- `ntdll!NtQueryDirectoryFile` at `0x180119847`
- `ntdll!NtClose` at `0x180119a1d`
- `ntdll!NtClose` at `0x180119a1d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CCuChangeConsumptionHandler::GetFileInfoFromParentEnumeration(
        struct _FILE_ID_128 *a1,
        struct _FILE_ID_128 *a2,
        void *a3,
        struct CCuEventLogger *a4,
        struct ISyncFileSystemInterface *a5,
        struct IFileInfoFromDisk **a6)
{
  _BYTE *v9; // rax
  char v10; // cl
  __int16 v11; // ax
  int FileMetadataByNativeFileID; // eax
  unsigned int v13; // r8d
  __int64 v14; // rax
  bool v15; // sf
  unsigned int v16; // eax
  int v17; // eax
  int v18; // ebx
  unsigned __int16 *v19; // rdi
  BOOLEAN RestartScan; // cl
  char v21; // r14
  unsigned __int16 *v22; // rdi
  PVOID v23; // rbx
  unsigned int v24; // eax
  int v25; // eax
  int v26; // esi
  _DWORD *v27; // rsi
  _DWORD *v28; // rdx
  __int64 v29; // rax
  __int16 v30; // ax
  unsigned int v31; // ebx
  unsigned int IoStatusBlock; // [rsp+20h] [rbp-E0h]
  unsigned int FileInformation; // [rsp+28h] [rbp-D8h]
  int Name; // [rsp+60h] [rbp-A0h] BYREF
  int v36; // [rsp+64h] [rbp-9Ch]
  char v37; // [rsp+68h] [rbp-98h]
  const char *v38; // [rsp+70h] [rbp-90h]
  __int64 v39; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v40; // [rsp+80h] [rbp-80h] BYREF
  int v41; // [rsp+88h] [rbp-78h] BYREF
  struct IFileSyncItemMetadata *v42; // [rsp+90h] [rbp-70h] BYREF
  HANDLE FileHandle; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v44; // [rsp+A0h] [rbp-60h] BYREF
  PVOID v45; // [rsp+A8h] [rbp-58h] BYREF
  struct _FILE_ID_128 v46; // [rsp+B0h] [rbp-50h] BYREF
  struct _FILE_ID_128 *v47; // [rsp+C0h] [rbp-40h]
  struct ISyncFileSystemInterface *v48; // [rsp+C8h] [rbp-38h]
  struct _IO_STATUS_BLOCK v49; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v50[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v51; // [rsp+F0h] [rbp-10h]

  v47 = a2;
  v48 = a5;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x80) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 15, &WPP_a5ec28a0d89e3ece50ad9a323350d00e_Traceguids);
    v9 = WPP_GLOBAL_Control;
  }
  if ( (v9[68] & 0x80) == 0 || (v10 = 1, v9[65] < 6u) )
    v10 = 0;
  Name = 0;
  v36 = 261;
  v37 = v10;
  v38 = "CCuChangeConsumptionHandler::GetFileInfoFromParentEnumeration";
  v39 = 0;
  FileHandle = 0;
  v49 = 0;
  v42 = 0;
  v40 = 0;
  v41 = 0;
  v45 = 0;
  v11 = 279;
  if ( !a3 || (LOWORD(v36) = 279, v11 = 280, !a4) || (LOWORD(v36) = 280, v11 = 281, !a6) )
  {
    Name = -2147024809;
    goto LABEL_63;
  }
  Name = 0;
  LOWORD(v36) = 281;
  FileMetadataByNativeFileID = CCuDBOperations::FindFileMetadataByNativeFileID(
                                 *(struct IFileSyncReplicaMetadata **)a3,
                                 a1,
                                 &v42);
  if ( FileMetadataByNativeFileID == -2147216764 )
  {
    Name = -2134375930;
    v11 = 291;
    goto LABEL_63;
  }
  Name = FileMetadataByNativeFileID;
  v15 = FileMetadataByNativeFileID < 0;
  v11 = 295;
  if ( v15 )
    goto LABEL_63;
  LOWORD(v36) = 295;
  Name = (*(__int64 (__fastcall **)(struct IFileSyncItemMetadata *, int *))(*(_QWORD *)v42 + 40LL))(v42, &v41);
  v11 = 299;
  if ( Name < 0 )
    goto LABEL_63;
  LOWORD(v36) = 299;
  if ( !v41 )
  {
    *(_QWORD *)v46.Identifier = 0;
    v44 = 0;
    Name = (*(__int64 (__fastcall **)(struct IFileSyncItemMetadata *, struct _FILE_ID_128 *))(*(_QWORD *)v42 + 168LL))(
             v42,
             &v46);
    v11 = 304;
    if ( Name < 0 )
      goto LABEL_63;
    LOWORD(v36) = 304;
    Name = (*(__int64 (__fastcall **)(struct IFileSyncItemMetadata *, unsigned __int16 **))(*(_QWORD *)v42 + 56LL))(
             v42,
             &v44);
    v11 = 305;
    if ( Name < 0 )
      goto LABEL_63;
    LOWORD(v36) = 305;
    v14 = -1;
    do
      ++v14;
    while ( *(_WORD *)(*(_QWORD *)v46.Identifier + 2 * v14) );
    if ( v14 )
    {
      Name = CPathUtilitiesBase<92>::CombinePathParts(&v40, 2, *(_QWORD *)v46.Identifier, v44);
      v15 = Name < 0;
      v11 = 308;
    }
    else
    {
      Name = CSyncCoreStringUtils::StringCopyAlloc(v44, &v40);
      v15 = Name < 0;
      v11 = 312;
    }
    if ( v15 )
      goto LABEL_63;
    LOWORD(v36) = v11;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x80) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 16, &WPP_a5ec28a0d89e3ece50ad9a323350d00e_Traceguids, v40);
  }
  v46 = *a1;
  v16 = CCuFileSystemOperations::OpenFile(&FileHandle, *((void **)a3 + 8), v13, &v46, IoStatusBlock, FileInformation);
  v17 = HRESULTFromNTSTATUS(v16);
  v18 = v17;
  if ( v17 < 0 )
  {
    v19 = (unsigned __int16 *)&Format;
    if ( v40 )
      v19 = v40;
    CCuEventLogger::LogEvent(a4, v17, 0, 0, (__int64)v19, 0);
    Name = v18;
    v11 = 328;
    goto LABEL_63;
  }
  LOWORD(v36) = 328;
  Name = CEcsMemPtr<_FILE_ID_EXTD_DIR_INFORMATION,0>::AllocBytes(&v45);
  v11 = 330;
  if ( Name < 0 )
  {
LABEL_63:
    HIWORD(v36) = v11;
    goto LABEL_64;
  }
  RestartScan = 1;
  v21 = 0;
  LOWORD(v36) = 330;
  v22 = (unsigned __int16 *)&Format;
  v23 = v45;
LABEL_35:
  if ( v21 )
  {
    Name = 0;
    LOWORD(v36) = 402;
    goto LABEL_64;
  }
  v49.Status = -1073741823;
  v49.Information = 0;
  v24 = NtQueryDirectoryFile(
          FileHandle,
          0,
          0,
          0,
          &v49,
          v23,
          0x10000u,
          FileMaximumInformation|FileBasicInformation,
          0,
          0,
          RestartScan);
  if ( v24 == -2147483642 )
  {
    Name = -2134375931;
    v11 = 402;
    goto LABEL_63;
  }
  v25 = HRESULTFromNTSTATUS(v24);
  v26 = v25;
  if ( v25 < 0 )
  {
    if ( v40 )
      v22 = v40;
    CCuEventLogger::LogEvent(a4, v25, 1, 0, (__int64)v22, 0);
    Name = v26;
    v11 = 358;
    goto LABEL_63;
  }
  Name = v25;
  LOWORD(v36) = 358;
  v27 = v23;
  while ( 1 )
  {
    do
    {
      if ( !v27 || v21 )
      {
        RestartScan = 0;
        goto LABEL_35;
      }
      v28 = v27;
      if ( *v27 )
        v27 = (_DWORD *)((char *)v27 + (unsigned int)*v27);
      else
        v27 = 0;
      v29 = *((_QWORD *)v28 + 9) - *(_QWORD *)v47->Identifier;
      if ( !v29 )
        v29 = *((_QWORD *)v28 + 10) - *(_QWORD *)&v47->Identifier[8];
    }
    while ( v29 );
    v50[0] = &CCuFileEnumItem::`vftable';
    v50[1] = 0;
    v51 = 0;
    *(_QWORD *)v46.Identifier = 0;
    Name = CCuFileEnumItem::PopulateItemInfo(
             (CCuFileEnumItem *)v50,
             (const struct _FILE_ID_EXTD_DIR_INFORMATION *)v28,
             &Format,
             a1,
             L"\\");
    v30 = 388;
    if ( Name < 0 )
      break;
    LOWORD(v36) = 388;
    Name = CCuFileEnumItem::GetName((CCuFileEnumItem *)v50, (const unsigned __int16 **)&v46);
    v30 = 389;
    if ( Name < 0 )
      break;
    LOWORD(v36) = 389;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 68) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
    {
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        17,
        &WPP_a5ec28a0d89e3ece50ad9a323350d00e_Traceguids,
        *(_QWORD *)v46.Identifier);
    }
    Name = CCuFileEnumItem::GetFileInfoFromDisk((CCuFileEnumItem *)v50, v48, a6);
    v30 = 394;
    if ( Name < 0 )
      break;
    LOWORD(v36) = 394;
    v21 = 1;
    CCuFileEnumItem::~CCuFileEnumItem((CCuFileEnumItem *)v50);
  }
  HIWORD(v36) = v30;
  CCuFileEnumItem::~CCuFileEnumItem((CCuFileEnumItem *)v50);
LABEL_64:
  if ( FileHandle )
  {
    NtClose(FileHandle);
    FileHandle = 0;
  }
  v31 = Name;
  CEcsMemPtr<_FILE_ID_EXTD_DIR_INFORMATION,0>::~CEcsMemPtr<_FILE_ID_EXTD_DIR_INFORMATION,0>(&v45);
  CEcsMemPtr<unsigned short,0>::~CEcsMemPtr<unsigned short,0>(&v40);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v42);
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&Name);
  return v31;
}

```

## disassembly

```asm
0x1801194f0  mov     [rsp-8+arg_8], rbx
0x1801194f5  push    rbp
0x1801194f6  push    rsi
0x1801194f7  push    rdi
0x1801194f8  push    r12
0x1801194fa  push    r13
0x1801194fc  push    r14
0x1801194fe  push    r15
0x180119500  lea     rbp, [rsp-60h]
0x180119505  sub     rsp, 160h
0x18011950c  mov     rax, cs:__security_cookie
0x180119513  xor     rax, rsp
0x180119516  mov     [rbp+90h+var_40], rax
0x18011951a  mov     r15, r9
0x18011951d  mov     rbx, r8
0x180119520  mov     [rbp+90h+var_D0], rdx
0x180119524  mov     r12, rcx
0x180119527  mov     rax, [rbp+90h+arg_20]
0x18011952e  mov     [rbp+90h+var_C8], rax
0x180119532  mov     r13, [rbp+90h+arg_28]
0x180119539  lea     r14, WPP_GLOBAL_Control
0x180119540  mov     dil, 80h
0x180119543  mov     rax, cs:WPP_GLOBAL_Control
0x18011954a  cmp     rax, r14
0x18011954d  jz      short loc_180119577
0x18011954f  test    [rax+44h], dil
0x180119553  jz      short loc_180119577
0x180119555  cmp     byte ptr [rax+41h], 6
0x180119559  jb      short loc_180119577
0x18011955b  mov     edx, 0Fh
0x180119560  lea     r8, WPP_a5ec28a0d89e3ece50ad9a323350d00e_Traceguids
0x180119567  mov     rcx, [rax+38h]
0x18011956b  call    WPP_SF_
0x180119570  mov     rax, cs:WPP_GLOBAL_Control
0x180119577  xor     esi, esi
0x180119579  test    [rax+44h], dil
0x18011957d  jz      short loc_180119587
0x18011957f  cmp     byte ptr [rax+41h], 6
0x180119583  mov     cl, 1
0x180119585  jnb     short loc_18011958A
0x180119587  mov     cl, sil
0x18011958a  mov     [rsp+190h+var_130], esi
0x18011958e  mov     [rsp+190h+var_12C], 105h
0x180119596  mov     [rsp+190h+var_128], cl
0x18011959a  lea     rax, aCcuchangeconsu_4; "CCuChangeConsumptionHandler::GetFileInf"...
0x1801195a1  mov     [rsp+190h+var_120], rax
0x1801195a6  mov     [rsp+190h+var_118], rsi
0x1801195ab  mov     [rbp+90h+FileHandle], rsi
0x1801195af  xorps   xmm0, xmm0
0x1801195b2  movups  xmmword ptr [rbp+90h+var_C0], xmm0
0x1801195b6  mov     [rbp+90h+var_100], rsi
0x1801195ba  mov     [rbp+90h+var_110], rsi
0x1801195be  mov     [rbp+90h+var_108], esi
0x1801195c1  mov     [rbp+90h+var_E8], rsi
0x1801195c5  mov     eax, 117h
0x1801195ca  test    rbx, rbx
0x1801195cd  jz      loc_180119A07
0x1801195d3  mov     word ptr [rsp+190h+var_12C], ax
0x1801195d8  mov     eax, 118h
0x1801195dd  test    r15, r15
0x1801195e0  jz      loc_180119A07
0x1801195e6  mov     word ptr [rsp+190h+var_12C], ax
0x1801195eb  mov     eax, 119h
0x1801195f0  test    r13, r13
0x1801195f3  jz      loc_180119A07
0x1801195f9  mov     [rsp+190h+var_130], esi
0x1801195fd  mov     word ptr [rsp+190h+var_12C], ax
0x180119602  lea     r8, [rbp+90h+var_100]; struct IFileSyncItemMetadata **
0x180119606  mov     rdx, r12; struct _FILE_ID_128 *
0x180119609  mov     rcx, [rbx]; struct IFileSyncReplicaMetadata *
0x18011960c  call    ?FindFileMetadataByNativeFileID@CCuDBOperations@@SAJPEAUIFileSyncReplicaMetadata@@PEAU_FILE_ID_128@@PEAPEAUIFileSyncItemMetadata@@@Z; CCuDBOperations::FindFileMetadataByNativeFileID(IFileSyncReplicaMetadata *,_FILE_ID_128 *,IFileSyncItemMetadata * *)
0x180119611  cmp     eax, 80041284h
0x180119616  jnz     short loc_18011962A
0x180119618  mov     [rsp+190h+var_130], 80C80206h
0x180119620  mov     eax, 123h
0x180119625  jmp     loc_180119A0F
0x18011962a  mov     [rsp+190h+var_130], eax
0x18011962e  test    eax, eax
0x180119630  mov     eax, 127h
0x180119635  js      loc_180119A0F
0x18011963b  mov     word ptr [rsp+190h+var_12C], ax
0x180119640  mov     rcx, [rbp+90h+var_100]
0x180119644  mov     rax, [rcx]
0x180119647  lea     rdx, [rbp+90h+var_108]
0x18011964b  mov     rax, [rax+28h]
0x18011964f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180119654  mov     [rsp+190h+var_130], eax
0x180119658  test    eax, eax
0x18011965a  mov     eax, 12Bh
0x18011965f  js      loc_180119A0F
0x180119665  mov     word ptr [rsp+190h+var_12C], ax
0x18011966a  cmp     [rbp+90h+var_108], esi
0x18011966d  jnz     loc_18011972B
0x180119673  mov     qword ptr [rbp+90h+var_E0.Identifier], rsi
0x180119677  mov     [rbp+90h+var_F0], rsi
0x18011967b  mov     rcx, [rbp+90h+var_100]
0x18011967f  mov     rax, [rcx]
0x180119682  lea     rdx, [rbp+90h+var_E0]
0x180119686  mov     rax, [rax+0A8h]
0x18011968d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180119692  mov     [rsp+190h+var_130], eax
0x180119696  test    eax, eax
0x180119698  mov     eax, 130h
0x18011969d  js      loc_180119A0F
0x1801196a3  mov     word ptr [rsp+190h+var_12C], ax
0x1801196a8  mov     rcx, [rbp+90h+var_100]
0x1801196ac  mov     rax, [rcx]
0x1801196af  lea     rdx, [rbp+90h+var_F0]
0x1801196b3  mov     rax, [rax+38h]
0x1801196b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801196bc  mov     [rsp+190h+var_130], eax
0x1801196c0  test    eax, eax
0x1801196c2  mov     eax, 131h
0x1801196c7  js      loc_180119A0F
0x1801196cd  mov     word ptr [rsp+190h+var_12C], ax
0x1801196d2  mov     r8, qword ptr [rbp+90h+var_E0.Identifier]
0x1801196d6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801196da  inc     rax
0x1801196dd  cmp     [r8+rax*2], si
0x1801196e2  jnz     short loc_1801196DA
0x1801196e4  test    rax, rax
0x1801196e7  jz      short loc_180119708
0x1801196e9  mov     r9, [rbp+90h+var_F0]
0x1801196ed  mov     edx, 2
0x1801196f2  lea     rcx, [rbp+90h+var_110]
0x1801196f6  call    ?CombinePathParts@?$CPathUtilitiesBase@$0FM@@@SAJPEAPEAGKZZ; CPathUtilitiesBase<92>::CombinePathParts(ushort * *,ulong,...)
0x1801196fb  mov     [rsp+190h+var_130], eax
0x1801196ff  test    eax, eax
0x180119701  mov     eax, 134h
0x180119706  jmp     short loc_180119720
0x180119708  lea     rdx, [rbp+90h+var_110]; unsigned __int16 **
0x18011970c  mov     rcx, [rbp+90h+var_F0]; unsigned __int16 *
0x180119710  call    ?StringCopyAlloc@CSyncCoreStringUtils@@SAJPEBGPEAPEAG@Z; CSyncCoreStringUtils::StringCopyAlloc(ushort const *,ushort * *)
0x180119715  mov     [rsp+190h+var_130], eax
0x180119719  test    eax, eax
0x18011971b  mov     eax, 138h
0x180119720  js      loc_180119A0F
0x180119726  mov     word ptr [rsp+190h+var_12C], ax
0x18011972b  mov     rcx, cs:WPP_GLOBAL_Control
0x180119732  cmp     rcx, r14
0x180119735  jz      short loc_18011975C
0x180119737  test    [rcx+44h], dil
0x18011973b  jz      short loc_18011975C
0x18011973d  cmp     byte ptr [rcx+41h], 4
0x180119741  jb      short loc_18011975C
0x180119743  mov     edx, 10h
0x180119748  mov     r9, [rbp+90h+var_110]
0x18011974c  lea     r8, WPP_a5ec28a0d89e3ece50ad9a323350d00e_Traceguids
0x180119753  mov     rcx, [rcx+38h]
0x180119757  call    WPP_SF_S
0x18011975c  movaps  xmm0, xmmword ptr [r12]
0x180119761  movdqa  xmmword ptr [rbp+90h+var_E0.Identifier], xmm0
0x180119766  lea     r9, [rbp+90h+var_E0]; struct _FILE_ID_128
0x18011976a  mov     rdx, [rbx+40h]; void *
0x18011976e  lea     rcx, [rbp+90h+FileHandle]; void **
0x180119772  call    ?OpenFile@CCuFileSystemOperations@@SAJPEAPEAXPEAXKU_FILE_ID_128@@KK@Z; CCuFileSystemOperations::OpenFile(void * *,void *,ulong,_FILE_ID_128,ulong,ulong)
0x180119777  mov     ecx, eax
0x180119779  call    HRESULTFromNTSTATUS
0x18011977e  mov     ebx, eax
0x180119780  test    eax, eax
0x180119782  jns     short loc_1801197BE
0x180119784  lea     rdi, Format
0x18011978b  mov     rdx, [rbp+90h+var_110]
0x18011978f  test    rdx, rdx
0x180119792  cmovnz  rdi, rdx
0x180119796  mov     [rsp+190h+FileInformation], rsi
0x18011979b  mov     [rsp+190h+IoStatusBlock], rdi
0x1801197a0  xor     r9d, r9d
0x1801197a3  xor     r8d, r8d
0x1801197a6  mov     edx, eax
0x1801197a8  mov     rcx, r15
0x1801197ab  call    ?LogEvent@CCuEventLogger@@QEAAJJW4CCU_EVENT_ACTION@1@KPEBGPEAU_SYNC_GID@@@Z; CCuEventLogger::LogEvent(long,CCuEventLogger::CCU_EVENT_ACTION,ulong,ushort const *,_SYNC_GID *)
0x1801197b0  mov     [rsp+190h+var_130], ebx
0x1801197b4  mov     eax, 148h
0x1801197b9  jmp     loc_180119A0F
0x1801197be  mov     [rsp+190h+var_130], ebx
0x1801197c2  mov     eax, 148h
0x1801197c7  mov     word ptr [rsp+190h+var_12C], ax
0x1801197cc  lea     rcx, [rbp+90h+var_E8]; void **
0x1801197d0  call    ?AllocBytes@?$CEcsMemPtr@U_FILE_ID_EXTD_DIR_INFORMATION@@$0A@@@QEAAJ_K@Z; CEcsMemPtr<_FILE_ID_EXTD_DIR_INFORMATION,0>::AllocBytes(unsigned __int64)
0x1801197d5  mov     [rsp+190h+var_130], eax
0x1801197d9  test    eax, eax
0x1801197db  mov     eax, 14Ah
0x1801197e0  js      loc_180119A0F
0x1801197e6  mov     cl, 1
0x1801197e8  mov     r14b, sil
0x1801197eb  mov     word ptr [rsp+190h+var_12C], ax
0x1801197f0  lea     rdi, Format
0x1801197f7  mov     rbx, [rbp+90h+var_E8]
0x1801197fb  test    r14b, r14b
0x1801197fe  jnz     loc_1801199F7
0x180119804  mov     dword ptr [rbp+90h+var_C0], 0C0000001h
0x18011980b  mov     [rbp+90h+var_C0.Information], rsi
0x18011980f  mov     [rsp+190h+RestartScan], cl; RestartScan
0x180119813  mov     [rsp+190h+FileName], rsi; FileName
0x180119818  mov     [rsp+190h+ReturnSingleEntry], sil; ReturnSingleEntry
0x18011981d  mov     [rsp+190h+FileInformationClass], 3Ch ; '<'; FileInformationClass
0x180119825  mov     [rsp+190h+Length], 10000h; Length
0x18011982d  mov     [rsp+190h+FileInformation], rbx; FileInformation
0x180119832  lea     rax, [rbp+90h+var_C0]
0x180119836  mov     [rsp+190h+IoStatusBlock], rax; IoStatusBlock
0x18011983b  xor     r9d, r9d; ApcContext
0x18011983e  xor     r8d, r8d; ApcRoutine
0x180119841  xor     edx, edx; Event
0x180119843  mov     rcx, [rbp+90h+FileHandle]; FileHandle
0x180119847  call    cs:__imp_NtQueryDirectoryFile
0x18011984d  cmp     eax, 80000006h
0x180119852  jz      loc_1801199E8
0x180119858  mov     ecx, eax
0x18011985a  call    HRESULTFromNTSTATUS
0x18011985f  mov     esi, eax
0x180119861  test    eax, eax
0x180119863  js      loc_1801199B1
0x180119869  mov     [rsp+190h+var_130], eax
0x18011986d  mov     eax, 166h
0x180119872  mov     word ptr [rsp+190h+var_12C], ax
0x180119877  mov     rsi, rbx
0x18011987a  mov     rcx, [rbp+90h+var_D0]
0x18011987e  test    rsi, rsi
0x180119881  jz      loc_180119995
0x180119887  test    r14b, r14b
0x18011988a  jnz     loc_180119995
0x180119890  mov     rdx, rsi; struct _FILE_ID_EXTD_DIR_INFORMATION *
0x180119893  cmp     dword ptr [rsi], 0
0x180119896  jnz     short loc_18011989C
0x180119898  xor     esi, esi
0x18011989a  jmp     short loc_1801198A1
0x18011989c  mov     eax, [rsi]
0x18011989e  add     rsi, rax
0x1801198a1  mov     rax, [rdx+48h]
0x1801198a5  sub     rax, [rcx]
0x1801198a8  jnz     short loc_1801198B2
0x1801198aa  mov     rax, [rdx+50h]
0x1801198ae  sub     rax, [rcx+8]
0x1801198b2  test    rax, rax
0x1801198b5  jnz     short loc_18011987E
0x1801198b7  lea     rax, ??_7CCuFileEnumItem@@6B@; const CCuFileEnumItem::`vftable'
0x1801198be  mov     [rbp+90h+var_B0], rax
0x1801198c2  mov     [rbp+90h+var_A8], 0
0x1801198ca  xorps   xmm0, xmm0
0x1801198cd  movdqa  [rbp+90h+var_A0], xmm0
0x1801198d2  mov     qword ptr [rbp+90h+var_E0.Identifier], 0
0x1801198da  lea     rax, asc_18014CE40; "\\"
0x1801198e1  mov     [rsp+190h+IoStatusBlock], rax; unsigned __int16 *
0x1801198e6  mov     r9, r12; struct _FILE_ID_128 *
0x1801198e9  mov     r8, rdi; unsigned __int16 *
0x1801198ec  lea     rcx, [rbp+90h+var_B0]; this
0x1801198f0  call    ?PopulateItemInfo@CCuFileEnumItem@@QEAAJPEBU_FILE_ID_EXTD_DIR_INFORMATION@@PEBGAEBU_FILE_ID_128@@1@Z; CCuFileEnumItem::PopulateItemInfo(_FILE_ID_EXTD_DIR_INFORMATION const *,ushort const *,_FILE_ID_128 const &,ushort const *)
0x1801198f5  mov     [rsp+190h+var_130], eax
0x1801198f9  lea     rcx, [rbp+90h+var_B0]; this
0x1801198fd  test    eax, eax
0x1801198ff  mov     eax, 184h
0x180119904  js      loc_1801199A3
0x18011990a  mov     word ptr [rsp+190h+var_12C], ax
0x18011990f  lea     rdx, [rbp+90h+var_E0]; unsigned __int16 **
0x180119913  call    ?GetName@CCuFileEnumItem@@UEBAJPEAPEBG@Z; CCuFileEnumItem::GetName(ushort const * *)
0x180119918  mov     [rsp+190h+var_130], eax
0x18011991c  test    eax, eax
0x18011991e  mov     eax, 185h
0x180119923  js      short loc_18011999F
0x180119925  mov     word ptr [rsp+190h+var_12C], ax
0x18011992a  mov     rcx, cs:WPP_GLOBAL_Control
0x180119931  lea     rax, WPP_GLOBAL_Control
0x180119938  cmp     rcx, rax
0x18011993b  jz      short loc_180119962
0x18011993d  test    byte ptr [rcx+44h], 80h
0x180119941  jz      short loc_180119962
0x180119943  cmp     byte ptr [rcx+41h], 4
0x180119947  jb      short loc_180119962
0x180119949  mov     edx, 11h
0x18011994e  mov     r9, qword ptr [rbp+90h+var_E0.Identifier]
0x180119952  lea     r8, WPP_a5ec28a0d89e3ece50ad9a323350d00e_Traceguids
0x180119959  mov     rcx, [rcx+38h]
0x18011995d  call    WPP_SF_S
0x180119962  mov     r8, r13; struct IFileInfoFromDisk **
0x180119965  mov     rdx, [rbp+90h+var_C8]; struct ISyncFileSystemInterface *
0x180119969  lea     rcx, [rbp+90h+var_B0]; this
0x18011996d  call    ?GetFileInfoFromDisk@CCuFileEnumItem@@UEBAJPEAUISyncFileSystemInterface@@PEAPEAUIFileInfoFromDisk@@@Z; CCuFileEnumItem::GetFileInfoFromDisk(ISyncFileSystemInterface *,IFileInfoFromDisk * *)
0x180119972  mov     [rsp+190h+var_130], eax
0x180119976  lea     rcx, [rbp+90h+var_B0]; this
0x18011997a  test    eax, eax
0x18011997c  mov     eax, 18Ah
0x180119981  js      short loc_1801199A3
0x180119983  mov     word ptr [rsp+190h+var_12C], ax
0x180119988  mov     r14b, 1
0x18011998b  call    ??1CCuFileEnumItem@@UEAA@XZ; CCuFileEnumItem::~CCuFileEnumItem(void)
0x180119990  jmp     loc_18011987A
0x180119995  xor     esi, esi
0x180119997  mov     cl, sil
0x18011999a  jmp     loc_1801197FB
0x18011999f  lea     rcx, [rbp+90h+var_B0]; this
0x1801199a3  mov     word ptr [rsp+190h+var_12C+2], ax
0x1801199a8  call    ??1CCuFileEnumItem@@UEAA@XZ; CCuFileEnumItem::~CCuFileEnumItem(void)
0x1801199ad  xor     esi, esi
0x1801199af  jmp     short loc_180119A14
0x1801199b1  mov     rax, [rbp+90h+var_110]
0x1801199b5  test    rax, rax
0x1801199b8  cmovnz  rdi, rax
0x1801199bc  mov     [rsp+190h+FileInformation], 0
0x1801199c5  mov     [rsp+190h+IoStatusBlock], rdi
  ... truncated ...
```
