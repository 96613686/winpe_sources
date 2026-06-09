# CCloudFileSystemApplier::UpdatePlaceholderInPlace(IFspFile *,IFspInPlaceFile *,ushort const *,ushort const *,ulong,ulong,int,IFileConcurrencyBlob * *)

- ea: `0x180095750`
- end: `0x180096167`
- name: `?UpdatePlaceholderInPlace@CCloudFileSystemApplier@@AEAAJPEAUIFspFile@@PEAUIFspInPlaceFile@@PEBG2KKHPEAPEAUIFileConcurrencyBlob@@@Z`
- size: `2583`
- prototype: `__int64 __fastcall(CCloudFileSystemApplier *__hidden this, struct IFspFile *, struct IFspInPlaceFile *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int, int, struct IFileConcurrencyBlob **)`
- caller_count: `4`
- callee_count: `24`
- tags: `file_ops, reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180093800`
- `0x180094880`
- `0x180094de0`
- `0x1800950b4`

## callees

- `0x180002ab0`
- `0x180007e10`
- `0x180008080`
- `0x180009188`
- `0x18000a6ec`
- `0x180011314`
- `0x18001133c`
- `0x18002db48`
- `0x180058d88`
- `0x18008c54c`
- `0x18008d358`
- `0x180095750`
- `0x1800963d0`
- `0x18009859c`
- `0x180098eec`
- `0x180099484`
- `0x1800995ec`
- `0x18009976c`
- `0x180099ad0`
- `0x18009a0e0`
- `0x18009a5c0`
- `0x1800bb594`
- `0x1800bb748`
- `0x18013e010`

## import_xrefs

- `ntdll!NtFsControlFile` at `0x180095c56`
- `ntdll!NtFsControlFile` at `0x180095c56`
- `ntdll!NtClose` at `0x180095e3b`
- `ntdll!NtClose` at `0x18009609a`
- `ntdll!NtClose` at `0x1800960ae`
- `ntdll!NtClose` at `0x180095e3b`
- `ntdll!NtClose` at `0x18009609a`
- `ntdll!NtClose` at `0x1800960ae`
- `cldapi!CfExecute` at `0x180095ea5`
- `cldapi!CfExecute` at `0x180095ea5`
- `cldapi!CfConvertToPlaceholder` at `0x180095ddb`
- `cldapi!CfConvertToPlaceholder` at `0x180095ddb`
- `cldapi!CfUpdatePlaceholder` at `0x180096004`
- `cldapi!CfUpdatePlaceholder` at `0x180096004`
- `cldapi!CfGetPlaceholderStateFromAttributeTag` at `0x180095db7`
- `cldapi!CfGetPlaceholderStateFromAttributeTag` at `0x180095db7`

## string_xrefs

- `0x1800957fd`: `CCloudFileSystemApplier::UpdatePlaceholderInPlace`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CCloudFileSystemApplier::UpdatePlaceholderInPlace(
        const unsigned __int16 **this,
        __int64 (__fastcall ***a2)(struct IFspFile *, GUID *, __int64 *),
        __int64 (__fastcall ***a3)(struct IFspFile *, GUID *, __int64 *),
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned int a6,
        unsigned int a7,
        int a8,
        struct IFileConcurrencyBlob **a9)
{
  _DWORD *v13; // rax
  char v14; // cl
  __int16 v15; // ax
  bool v16; // sf
  bool v17; // sf
  const WCHAR *v18; // rbx
  const WCHAR *v19; // rax
  int v20; // ecx
  int v21; // r12d
  unsigned int v22; // r8d
  __int16 v23; // ax
  unsigned int v24; // esi
  int v25; // r15d
  const unsigned __int16 *v26; // rcx
  const unsigned __int16 *v27; // rcx
  struct IUnknown *v28; // rax
  union _LARGE_INTEGER *v29; // rax
  int v30; // ebx
  unsigned int v31; // eax
  struct IUnknown *v32; // rcx
  int v33; // ebx
  const unsigned __int16 *v34; // r8
  union _LARGE_INTEGER *v35; // rax
  bool v36; // sf
  unsigned int v37; // ebx
  int IoStatusBlock; // [rsp+20h] [rbp-E0h]
  int NormalizedNtPath; // [rsp+50h] [rbp-B0h] BYREF
  int v41; // [rsp+54h] [rbp-ACh]
  char v42; // [rsp+58h] [rbp-A8h]
  const char *v43; // [rsp+60h] [rbp-A0h]
  __int64 v44; // [rsp+68h] [rbp-98h]
  HANDLE FileHandle; // [rsp+70h] [rbp-90h] BYREF
  PCWSTR v46; // [rsp+78h] [rbp-88h] BYREF
  int v47; // [rsp+80h] [rbp-80h]
  struct IUnknown *v48; // [rsp+88h] [rbp-78h] BYREF
  int v49; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v50; // [rsp+94h] [rbp-6Ch] BYREF
  unsigned int v51; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v52; // [rsp+9Ch] [rbp-64h] BYREF
  PCWSTR SourceString; // [rsp+A0h] [rbp-60h] BYREF
  HANDLE Handle; // [rsp+A8h] [rbp-58h] BYREF
  struct _FILE_ID_128 InputBuffer; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v56; // [rsp+C0h] [rbp-40h]
  struct IUnknown *v57; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v58; // [rsp+D8h] [rbp-28h] BYREF
  struct _IO_STATUS_BLOCK v59; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v60; // [rsp+F0h] [rbp-10h]
  __int128 v61; // [rsp+100h] [rbp+0h] BYREF
  __int128 v62; // [rsp+110h] [rbp+10h]
  __int128 v63; // [rsp+120h] [rbp+20h]
  __int128 v64; // [rsp+130h] [rbp+30h] BYREF
  __int128 v65; // [rsp+140h] [rbp+40h]
  __int128 v66; // [rsp+150h] [rbp+50h]
  struct _FILE_ID_128 v67; // [rsp+160h] [rbp+60h] BYREF
  __int128 v68; // [rsp+170h] [rbp+70h] BYREF
  __int128 v69; // [rsp+180h] [rbp+80h] BYREF
  __int128 v70; // [rsp+190h] [rbp+90h]

  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 27, &WPP_e4cf962a26e73539d62b7553e52927b0_Traceguids);
    v13 = WPP_GLOBAL_Control;
  }
  if ( (v13[17] & 0x100) == 0 || (v14 = 1, *((_BYTE *)v13 + 65) < 6u) )
    v14 = 0;
  NormalizedNtPath = 0;
  v41 = 1024;
  v42 = v14;
  v43 = "CCloudFileSystemApplier::UpdatePlaceholderInPlace";
  v44 = 0;
  v68 = 0;
  v69 = 0;
  v70 = 0;
  v67 = 0;
  SourceString = 0;
  v46 = 0;
  v58 = 0;
  v50 = 0;
  v52 = 0;
  v51 = 0;
  v49 = 0;
  FileHandle = 0;
  Handle = 0;
  v57 = 0;
  v48 = 0;
  if ( a9 )
    *a9 = 0;
  v15 = 1042;
  if ( !a2 )
  {
    NormalizedNtPath = -2147024809;
    goto LABEL_12;
  }
  NormalizedNtPath = 0;
  LOWORD(v41) = 1042;
  if ( a5 )
  {
    NormalizedNtPath = CPathUtilities::GetNormalizedNtPath(a5, (unsigned __int16 **)&v46);
    v16 = NormalizedNtPath < 0;
    v15 = 1047;
  }
  else
  {
    NormalizedNtPath = CPathUtilities::GetAbsoluteFileName(this[3], a2, (unsigned __int16 **)&v46);
    v16 = NormalizedNtPath < 0;
    v15 = 1051;
  }
  if ( v16 )
    goto LABEL_12;
  LOWORD(v41) = v15;
  if ( a4 )
  {
    NormalizedNtPath = CPathUtilities::GetNormalizedNtPath(a4, (unsigned __int16 **)&SourceString);
    v17 = NormalizedNtPath < 0;
    v15 = 1057;
  }
  else
  {
    if ( !a3 )
    {
      v18 = v46;
      goto LABEL_24;
    }
    NormalizedNtPath = CPathUtilities::GetAbsoluteFileName(this[3], a3, (unsigned __int16 **)&SourceString);
    v17 = NormalizedNtPath < 0;
    v15 = 1065;
  }
  if ( v17 )
    goto LABEL_12;
  LOWORD(v41) = v15;
  v18 = SourceString;
LABEL_24:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
  {
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      28,
      (unsigned int)&WPP_e4cf962a26e73539d62b7553e52927b0_Traceguids,
      (_DWORD)v18,
      (__int64)v46);
  }
  v19 = v18;
  do
  {
    v20 = *(const WCHAR *)((char *)v19 + (char *)v46 - (char *)v18);
    v21 = *v19 - v20;
    if ( v21 )
      break;
    ++v19;
  }
  while ( v20 );
  NormalizedNtPath = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(struct IFspFile *, GUID *, __int64 *), int *))(*a2)[5])(
                       a2,
                       &v49);
  v23 = 1079;
  if ( NormalizedNtPath < 0 )
    goto LABEL_32;
  LOWORD(v41) = 1079;
  v24 = a6;
  NormalizedNtPath = CFspCloudFileSystemOperations::CreateFileW(
                       v18,
                       (a6 & 0x800) != 0 ? 1114499 : 1114496,
                       v22,
                       (v49 & 0x10) != 0 ? 3 : 0,
                       0x2Au,
                       1u,
                       8u,
                       &FileHandle);
  v23 = 1127;
  if ( NormalizedNtPath < 0 )
    goto LABEL_32;
  LOWORD(v41) = 1127;
  if ( a3 )
  {
    NormalizedNtPath = CCloudFileSystemApplier::ValidateFileUnchangedAndNotUnderDownload(
                         (CCloudFileSystemApplier *)this,
                         FileHandle,
                         v18,
                         (struct IFspInPlaceFile *)a3);
    v23 = 1133;
    if ( NormalizedNtPath < 0 )
      goto LABEL_32;
    LOWORD(v41) = 1133;
  }
  NormalizedNtPath = CFspCloudFileSystemOperations::GetFileId(FileHandle, &v67);
  v23 = 1137;
  if ( NormalizedNtPath < 0 )
    goto LABEL_32;
  v47 = 0;
  v25 = 0;
  LOWORD(v41) = 1137;
  v26 = this[8];
  InputBuffer = v67;
  if ( !(*(unsigned __int8 (__fastcall **)(const unsigned __int16 *, struct _FILE_ID_128 *))(*(_QWORD *)v26 + 32LL))(
          v26,
          &InputBuffer) )
    goto LABEL_50;
  v27 = this[8];
  InputBuffer = v67;
  NormalizedNtPath = (*(__int64 (__fastcall **)(const unsigned __int16 *, struct _FILE_ID_128 *, struct IUnknown **))(*(_QWORD *)v27 + 40LL))(
                       v27,
                       &InputBuffer,
                       &v57);
  v23 = 1145;
  if ( NormalizedNtPath < 0 )
    goto LABEL_32;
  LOWORD(v41) = 1145;
  v28 = v48;
  if ( v48 != v57 )
  {
    ATL::AtlComQIPtrAssign(&v48, v57, &GUID_998a9007_a6fa_4e93_8c33_23760adab4b1);
    v28 = v48;
  }
  if ( v28 )
  {
    v59 = 0;
    v60 = 0;
    NormalizedNtPath = CFspCloudFileSystemOperations::GetPlaceholderInfo(FileHandle, (struct PlaceholderInfo *)&v59);
    v23 = 1153;
    if ( NormalizedNtPath < 0 )
      goto LABEL_32;
    LOWORD(v41) = 1153;
    if ( LODWORD(v59.Information) == 1 )
      v25 = 1;
    if ( v21 )
    {
      v29 = (union _LARGE_INTEGER *)((__int64 (__fastcall *)(struct IUnknown *, struct _FILE_ID_128 *))v48->lpVtbl[1].QueryInterface)(
                                      v48,
                                      &InputBuffer);
      v59 = (struct _IO_STATUS_BLOCK)v67;
      NormalizedNtPath = CCloudFileSystemApplier::AbortActiveHydration(
                           (CCloudFileSystemApplier *)this,
                           v18,
                           (struct _FILE_ID_128 *)&v59,
                           *v29,
                           IoStatusBlock,
                           v25 ^ 1u);
      v23 = 1163;
      if ( NormalizedNtPath < 0 )
        goto LABEL_32;
      LOWORD(v41) = 1163;
      v30 = v47;
    }
    else
    {
      v30 = 1;
      v47 = 1;
    }
  }
  else
  {
LABEL_50:
    v30 = 0;
  }
  if ( a6 )
    goto LABEL_54;
  NormalizedNtPath = CFspCloudFileSystemOperations::GetAttributes(FileHandle, &v50);
  v23 = 1181;
  if ( NormalizedNtPath < 0 )
  {
LABEL_32:
    HIWORD(v41) = v23;
    goto LABEL_95;
  }
  LOWORD(v41) = 1181;
  v24 = v50 & 0x186820;
LABEL_54:
  if ( v21 )
  {
    InputBuffer = 0;
    v56 = 0;
    v59 = 0;
    *(_DWORD *)InputBuffer.Identifier = 8;
    v31 = NtFsControlFile(FileHandle, 0, 0, 0, &v59, 0x900FCu, &InputBuffer, 0x18u, 0, 0);
    NormalizedNtPath = HRESULTFromNTSTATUS(v31);
    v15 = 1201;
    if ( NormalizedNtPath < 0 )
      goto LABEL_12;
    LOWORD(v41) = 1201;
    NormalizedNtPath = CFspCloudFileSystemOperations::Rename(FileHandle, v46);
    v15 = 1204;
    if ( NormalizedNtPath < 0 )
      goto LABEL_12;
    LOWORD(v41) = 1204;
  }
  NormalizedNtPath = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(struct IFspFile *, GUID *, __int64 *), __int128 *))(*a2)[7])(
                       a2,
                       &v68);
  v15 = 1208;
  if ( NormalizedNtPath < 0 )
    goto LABEL_12;
  LOWORD(v41) = 1208;
  NormalizedNtPath = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(struct IFspFile *, GUID *, __int64 *), __int128 *))(*a2)[6])(
                       a2,
                       &v69);
  v15 = 1209;
  if ( NormalizedNtPath < 0 )
    goto LABEL_12;
  LOWORD(v41) = 1209;
  NormalizedNtPath = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(struct IFspFile *, GUID *, __int64 *), char *))(*a2)[11])(
                       a2,
                       (char *)&v69 + 8);
  v15 = 1210;
  if ( NormalizedNtPath < 0 )
    goto LABEL_12;
  LOWORD(v41) = 1210;
  *((_QWORD *)&v68 + 1) = -1;
  LODWORD(v70) = v49 | v24 | 0x80;
  NormalizedNtPath = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(struct IFspFile *, GUID *, __int64 *), __int64 *))(*a2)[8])(
                       a2,
                       &v58);
  v15 = 1223;
  if ( NormalizedNtPath < 0
    || (LOWORD(v41) = 1223,
        *((_QWORD *)&v70 + 1) = v58,
        NormalizedNtPath = CFspCloudFileSystemOperations::GetAttributeInformation(FileHandle, &v51, &v52),
        v15 = 1227,
        NormalizedNtPath < 0) )
  {
LABEL_12:
    HIWORD(v41) = v15;
    goto LABEL_95;
  }
  LOWORD(v41) = 1227;
  if ( !(unsigned int)CfGetPlaceholderStateFromAttributeTag(v52, v51) )
  {
    IoStatusBlock = 0;
    NormalizedNtPath = CfConvertToPlaceholder(FileHandle, &v67, 16, 0);
    v15 = 1233;
    if ( NormalizedNtPath < 0 )
      goto LABEL_12;
    LOWORD(v41) = 1233;
  }
  if ( v30 && (v32 = v48) != 0 )
  {
    v64 = 0;
    v65 = 0;
    v66 = 0;
    v61 = 0;
    v62 = 0;
    v63 = 0;
    if ( FileHandle )
    {
      NtClose(FileHandle);
      FileHandle = 0;
      v32 = v48;
    }
    *(_QWORD *)&v64 = 0x300000030LL;
    *((_QWORD *)&v64 + 1) = this[6];
    *(_QWORD *)&v65 = *(_QWORD *)((__int64 (__fastcall *)(struct IUnknown *, struct _FILE_ID_128 *))v32->lpVtbl[1].QueryInterface)(
                                   v32,
                                   &InputBuffer);
    LODWORD(v61) = 40;
    DWORD2(v61) = 1;
    *(_QWORD *)&v62 = &v68;
    *((_QWORD *)&v62 + 1) = &v67;
    LODWORD(v63) = 16;
    v33 = CfExecute(&v64, &v61);
    if ( v33 < 0 )
    {
      v34 = this[8];
      v59 = (struct _IO_STATUS_BLOCK)v67;
      if ( (*(unsigned __int8 (__fastcall **)(const unsigned __int16 *, struct _IO_STATUS_BLOCK *))(*(_QWORD *)v34 + 32LL))(
             v34,
             &v59) )
      {
        v35 = (union _LARGE_INTEGER *)((__int64 (__fastcall *)(struct IUnknown *, struct _FILE_ID_128 *))v48->lpVtbl[1].QueryInterface)(
                                        v48,
                                        &InputBuffer);
        v59 = (struct _IO_STATUS_BLOCK)v67;
        NormalizedNtPath = CCloudFileSystemApplier::AbortActiveHydration(
                             (CCloudFileSystemApplier *)this,
                             v46,
                             (struct _FILE_ID_128 *)&v59,
                             *v35,
                             IoStatusBlock,
                             1);
        v15 = 1267;
        if ( NormalizedNtPath < 0 )
          goto LABEL_12;
        LOWORD(v41) = 1267;
      }
    }
    if ( v33 == -2147024498 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 29, &WPP_e4cf962a26e73539d62b7553e52927b0_Traceguids);
      }
      NormalizedNtPath = -2134375651;
      v15 = 1274;
      goto LABEL_12;
    }
    if ( v33 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          30,
          &WPP_e4cf962a26e73539d62b7553e52927b0_Traceguids,
          (unsigned int)v33);
      }
      NormalizedNtPath = v33;
      v15 = 1279;
      goto LABEL_12;
    }
    v30 = v47;
  }
  else
  {
    NormalizedNtPath = CfUpdatePlaceholder(FileHandle, &v68, &v67, 16, 0, 0, a8 != 0 ? 2 : 0, 0, 0);
    v15 = 1288;
    if ( NormalizedNtPath < 0 )
      goto LABEL_12;
    LOWORD(v41) = 1288;
  }
  if ( a9 )
  {
    if ( v30 )
    {
      NormalizedNtPath = CFspCloudFileSystemOperations::OpenFileAttribute(v46, &Handle);
      v15 = 1298;
      if ( NormalizedNtPath < 0 )
        goto LABEL_12;
      LOWORD(v41) = 1298;
      NormalizedNtPath = CCloudFileSystemApplier::CloseActionHandleAndGetConcurrencyBlob(
                           (CCloudFileSystemApplier *)this,
                           &Handle,
                           v46,
                           0,
                           a9);
      v36 = NormalizedNtPath < 0;
      v15 = 1300;
    }
    else
    {
      NormalizedNtPath = CCloudFileSystemApplier::CloseActionHandleAndGetConcurrencyBlob(
                           (CCloudFileSystemApplier *)this,
                           &FileHandle,
                           v46,
                           0,
                           a9);
      v15 = 1304;
      if ( NormalizedNtPath < 0 )
        goto LABEL_12;
      LOWORD(v41) = 1304;
      if ( !v25 )
        goto LABEL_95;
      NormalizedNtPath = CCloudFileSystemAsyncHydrationManager::HydratePlaceholderAsync(v46);
      v36 = NormalizedNtPath < 0;
      v15 = 1309;
    }
    if ( v36 )
      goto LABEL_12;
    LOWORD(v41) = v15;
  }
LABEL_95:
  if ( Handle )
  {
    NtClose(Handle);
    Handle = 0;
  }
  if ( FileHandle )
  {
    NtClose(FileHandle);
    FileHandle = 0;
  }
  v37 = NormalizedNtPath;
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v48);
  CEcsMemPtr<unsigned short,0>::~CEcsMemPtr<unsigned short,0>(&v46);
  CEcsMemPtr<unsigned short,0>::~CEcsMemPtr<unsigned short,0>(&SourceString);
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&NormalizedNtPath);
  return v37;
}

```

## disassembly

```asm
0x180095750  push    rbp
0x180095752  push    rbx
0x180095753  push    rsi
0x180095754  push    rdi
0x180095755  push    r12
0x180095757  push    r13
0x180095759  push    r14
0x18009575b  push    r15
0x18009575d  lea     rbp, [rsp-0B8h]
0x180095765  sub     rsp, 1B8h
0x18009576c  mov     rax, cs:__security_cookie
0x180095773  xor     rax, rsp
0x180095776  mov     [rbp+0F0h+var_50], rax
0x18009577d  mov     rsi, r9
0x180095780  mov     r15, r8
0x180095783  mov     rdi, rdx
0x180095786  mov     r14, rcx
0x180095789  mov     rbx, [rbp+0F0h+arg_20]
0x180095790  mov     r13, [rbp+0F0h+arg_40]
0x180095797  lea     rcx, WPP_GLOBAL_Control
0x18009579e  mov     rax, cs:WPP_GLOBAL_Control
0x1800957a5  cmp     rax, rcx
0x1800957a8  jz      short loc_1800957D5
0x1800957aa  test    dword ptr [rax+44h], 100h
0x1800957b1  jz      short loc_1800957D5
0x1800957b3  cmp     byte ptr [rax+41h], 6
0x1800957b7  jb      short loc_1800957D5
0x1800957b9  mov     edx, 1Bh
0x1800957be  lea     r8, WPP_e4cf962a26e73539d62b7553e52927b0_Traceguids
0x1800957c5  mov     rcx, [rax+38h]
0x1800957c9  call    WPP_SF_
0x1800957ce  mov     rax, cs:WPP_GLOBAL_Control
0x1800957d5  xor     r12d, r12d
0x1800957d8  test    dword ptr [rax+44h], 100h
0x1800957df  jz      short loc_1800957E9
0x1800957e1  cmp     byte ptr [rax+41h], 6
0x1800957e5  mov     cl, 1
0x1800957e7  jnb     short loc_1800957EC
0x1800957e9  mov     cl, r12b
0x1800957ec  mov     [rsp+1F0h+var_1A0], r12d
0x1800957f1  mov     [rsp+1F0h+var_19C], 400h
0x1800957f9  mov     [rsp+1F0h+var_198], cl
0x1800957fd  lea     rax, aCcloudfilesyst_65; "CCloudFileSystemApplier::UpdatePlacehol"...
0x180095804  mov     [rsp+1F0h+var_190], rax
0x180095809  mov     [rsp+1F0h+var_188], r12
0x18009580e  xorps   xmm0, xmm0
0x180095811  movups  [rbp+0F0h+var_80], xmm0
0x180095815  movups  [rbp+0F0h+var_70], xmm0
0x18009581c  movups  [rbp+0F0h+var_60], xmm0
0x180095823  movups  xmmword ptr [rbp+0F0h+var_90.Identifier], xmm0
0x180095827  mov     [rbp+0F0h+SourceString], r12
0x18009582b  mov     [rsp+1F0h+var_178], r12
0x180095830  mov     [rbp+0F0h+var_118], r12
0x180095834  mov     [rbp+0F0h+var_15C], r12d
0x180095838  mov     [rbp+0F0h+var_154], r12d
0x18009583c  mov     [rbp+0F0h+var_158], r12d
0x180095840  mov     [rbp+0F0h+var_160], r12d
0x180095844  mov     [rsp+1F0h+FileHandle], r12
0x180095849  mov     [rbp+0F0h+Handle], r12
0x18009584d  mov     [rbp+0F0h+var_120], r12
0x180095851  mov     [rbp+0F0h+var_168], r12
0x180095855  test    r13, r13
0x180095858  jz      short loc_18009585E
0x18009585a  mov     [r13+0], r12
0x18009585e  mov     eax, [rsp+1F0h+var_1A0]
0x180095862  mov     [rsp+1F0h+var_1A0], eax
0x180095866  mov     eax, 412h
0x18009586b  test    rdi, rdi
0x18009586e  jnz     short loc_180095882
0x180095870  mov     [rsp+1F0h+var_1A0], 80070057h
0x180095878  mov     word ptr [rsp+1F0h+var_19C+2], ax
0x18009587d  jmp     loc_180096091
0x180095882  mov     [rsp+1F0h+var_1A0], r12d
0x180095887  mov     word ptr [rsp+1F0h+var_19C], ax
0x18009588c  test    rbx, rbx
0x18009588f  jz      short loc_1800958E1
0x180095891  lea     rdx, [rsp+1F0h+var_178]; unsigned __int16 **
0x180095896  mov     rcx, rbx; unsigned __int16 *
0x180095899  call    ?GetNormalizedNtPath@CPathUtilities@@SAJPEBGPEAPEAG@Z; CPathUtilities::GetNormalizedNtPath(ushort const *,ushort * *)
0x18009589e  mov     [rsp+1F0h+var_1A0], eax
0x1800958a2  mov     [rsp+1F0h+var_1A0], eax
0x1800958a6  test    eax, eax
0x1800958a8  mov     eax, 417h
0x1800958ad  js      short loc_180095878
0x1800958af  mov     word ptr [rsp+1F0h+var_19C], ax
0x1800958b4  test    rsi, rsi
0x1800958b7  jz      short loc_180095903
0x1800958b9  lea     rdx, [rbp+0F0h+SourceString]; unsigned __int16 **
0x1800958bd  mov     rcx, rsi; unsigned __int16 *
0x1800958c0  call    ?GetNormalizedNtPath@CPathUtilities@@SAJPEBGPEAPEAG@Z; CPathUtilities::GetNormalizedNtPath(ushort const *,ushort * *)
0x1800958c5  mov     [rsp+1F0h+var_1A0], eax
0x1800958c9  mov     [rsp+1F0h+var_1A0], eax
0x1800958cd  test    eax, eax
0x1800958cf  mov     eax, 421h
0x1800958d4  js      short loc_180095878
0x1800958d6  mov     word ptr [rsp+1F0h+var_19C], ax
0x1800958db  mov     rbx, [rbp+0F0h+SourceString]
0x1800958df  jmp     short loc_18009592E
0x1800958e1  lea     r8, [rsp+1F0h+var_178]; unsigned __int16 **
0x1800958e6  mov     rdx, rdi; struct IFspFile *
0x1800958e9  mov     rcx, [r14+18h]; unsigned __int16 *
0x1800958ed  call    ?GetAbsoluteFileName@CPathUtilities@@SAJPEBGPEAUIFspFile@@PEAPEAG@Z; CPathUtilities::GetAbsoluteFileName(ushort const *,IFspFile *,ushort * *)
0x1800958f2  mov     [rsp+1F0h+var_1A0], eax
0x1800958f6  mov     [rsp+1F0h+var_1A0], eax
0x1800958fa  test    eax, eax
0x1800958fc  mov     eax, 41Bh
0x180095901  jmp     short loc_1800958AD
0x180095903  test    r15, r15
0x180095906  jz      short loc_180095929
0x180095908  lea     r8, [rbp+0F0h+SourceString]; unsigned __int16 **
0x18009590c  mov     rdx, r15; struct IFspFile *
0x18009590f  mov     rcx, [r14+18h]; unsigned __int16 *
0x180095913  call    ?GetAbsoluteFileName@CPathUtilities@@SAJPEBGPEAUIFspFile@@PEAPEAG@Z; CPathUtilities::GetAbsoluteFileName(ushort const *,IFspFile *,ushort * *)
0x180095918  mov     [rsp+1F0h+var_1A0], eax
0x18009591c  mov     [rsp+1F0h+var_1A0], eax
0x180095920  test    eax, eax
0x180095922  mov     eax, 429h
0x180095927  jmp     short loc_1800958D4
0x180095929  mov     rbx, [rsp+1F0h+var_178]
0x18009592e  mov     rcx, cs:WPP_GLOBAL_Control
0x180095935  lea     rax, WPP_GLOBAL_Control
0x18009593c  cmp     rcx, rax
0x18009593f  jz      short loc_180095972
0x180095941  test    dword ptr [rcx+44h], 100h
0x180095948  jz      short loc_180095972
0x18009594a  cmp     byte ptr [rcx+41h], 4
0x18009594e  jb      short loc_180095972
0x180095950  mov     edx, 1Ch
0x180095955  mov     rax, [rsp+1F0h+var_178]
0x18009595a  mov     [rsp+1F0h+IoStatusBlock], rax
0x18009595f  mov     r9, rbx
0x180095962  lea     r8, WPP_e4cf962a26e73539d62b7553e52927b0_Traceguids
0x180095969  mov     rcx, [rcx+38h]
0x18009596d  call    WPP_SF_SS
0x180095972  mov     rax, rbx
0x180095975  mov     rdx, [rsp+1F0h+var_178]
0x18009597a  sub     rdx, rbx
0x18009597d  movzx   r12d, word ptr [rax]
0x180095981  movzx   ecx, word ptr [rax+rdx]
0x180095985  sub     r12d, ecx
0x180095988  jnz     short loc_180095992
0x18009598a  add     rax, 2
0x18009598e  test    ecx, ecx
0x180095990  jnz     short loc_18009597D
0x180095992  mov     rax, [rdi]
0x180095995  lea     rdx, [rbp+0F0h+var_160]
0x180095999  mov     rcx, rdi
0x18009599c  mov     rax, [rax+28h]
0x1800959a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800959a5  mov     [rsp+1F0h+var_1A0], eax
0x1800959a9  mov     [rsp+1F0h+var_1A0], eax
0x1800959ad  test    eax, eax
0x1800959af  mov     eax, 437h
0x1800959b4  jns     short loc_1800959C3
0x1800959b6  mov     word ptr [rsp+1F0h+var_19C+2], ax
0x1800959bb  xor     r12d, r12d
0x1800959be  jmp     loc_180096091
0x1800959c3  mov     word ptr [rsp+1F0h+var_19C], ax
0x1800959c8  mov     eax, [rbp+0F0h+var_160]
0x1800959cb  and     al, 10h
0x1800959cd  neg     al
0x1800959cf  sbb     r9d, r9d
0x1800959d2  and     r9d, 3; unsigned int
0x1800959d6  mov     esi, [rbp+0F0h+arg_28]
0x1800959dc  mov     eax, esi
0x1800959de  and     eax, 800h
0x1800959e3  neg     eax
0x1800959e5  sbb     edx, edx
0x1800959e7  and     edx, 3
0x1800959ea  add     edx, 110180h; DesiredAccess
0x1800959f0  lea     rax, [rsp+1F0h+FileHandle]
0x1800959f5  mov     qword ptr [rsp+1F0h+InputBufferLength], rax; void **
0x1800959fa  mov     dword ptr [rsp+1F0h+InputBuffer], 8; unsigned int
0x180095a02  mov     [rsp+1F0h+FsControlCode], 1; ULONG
0x180095a0a  mov     dword ptr [rsp+1F0h+IoStatusBlock], 2Ah ; '*'; int
0x180095a12  mov     rcx, rbx; SourceString
0x180095a15  call    ?CreateFileW@CFspCloudFileSystemOperations@@SAJPEBGKKKKKKPEAPEAX@Z; CFspCloudFileSystemOperations::CreateFileW(ushort const *,ulong,ulong,ulong,ulong,ulong,ulong,void * *)
0x180095a1a  mov     [rsp+1F0h+var_1A0], eax
0x180095a1e  mov     [rsp+1F0h+var_1A0], eax
0x180095a22  test    eax, eax
0x180095a24  mov     eax, 467h
0x180095a29  js      short loc_1800959B6
0x180095a2b  mov     word ptr [rsp+1F0h+var_19C], ax
0x180095a30  test    r15, r15
0x180095a33  jz      short loc_180095A62
0x180095a35  mov     r9, r15; struct IFspInPlaceFile *
0x180095a38  mov     r8, rbx; unsigned __int16 *
0x180095a3b  mov     rdx, [rsp+1F0h+FileHandle]; void *
0x180095a40  mov     rcx, r14; this
0x180095a43  call    ?ValidateFileUnchangedAndNotUnderDownload@CCloudFileSystemApplier@@AEAAJPEAXPEBGPEAUIFspInPlaceFile@@@Z; CCloudFileSystemApplier::ValidateFileUnchangedAndNotUnderDownload(void *,ushort const *,IFspInPlaceFile *)
0x180095a48  mov     [rsp+1F0h+var_1A0], eax
0x180095a4c  mov     [rsp+1F0h+var_1A0], eax
0x180095a50  test    eax, eax
0x180095a52  mov     eax, 46Dh
0x180095a57  js      loc_1800959B6
0x180095a5d  mov     word ptr [rsp+1F0h+var_19C], ax
0x180095a62  lea     rdx, [rbp+0F0h+var_90]; struct _FILE_ID_128 *
0x180095a66  mov     rcx, [rsp+1F0h+FileHandle]; FileHandle
0x180095a6b  call    ?GetFileId@CFspCloudFileSystemOperations@@SAJPEAXPEAU_FILE_ID_128@@@Z; CFspCloudFileSystemOperations::GetFileId(void *,_FILE_ID_128 *)
0x180095a70  mov     [rsp+1F0h+var_1A0], eax
0x180095a74  mov     [rsp+1F0h+var_1A0], eax
0x180095a78  test    eax, eax
0x180095a7a  mov     eax, 471h
0x180095a7f  js      loc_1800959B6
0x180095a85  mov     [rbp+0F0h+var_170], 0
0x180095a8c  xor     r15d, r15d
0x180095a8f  mov     word ptr [rsp+1F0h+var_19C], ax
0x180095a94  mov     rcx, [r14+40h]
0x180095a98  movaps  xmm0, xmmword ptr [rbp+0F0h+var_90.Identifier]
0x180095a9c  movdqa  [rbp+0F0h+var_140], xmm0
0x180095aa1  mov     rax, [rcx]
0x180095aa4  lea     rdx, [rbp+0F0h+var_140]
0x180095aa8  mov     rax, [rax+20h]
0x180095aac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095ab1  test    al, al
0x180095ab3  jz      loc_180095BC1
0x180095ab9  mov     rcx, [r14+40h]
0x180095abd  movaps  xmm0, xmmword ptr [rbp+0F0h+var_90.Identifier]
0x180095ac1  movdqa  [rbp+0F0h+var_140], xmm0
0x180095ac6  mov     rax, [rcx]
0x180095ac9  lea     r8, [rbp+0F0h+var_120]
0x180095acd  lea     rdx, [rbp+0F0h+var_140]
0x180095ad1  mov     rax, [rax+28h]
0x180095ad5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095ada  mov     [rsp+1F0h+var_1A0], eax
0x180095ade  mov     [rsp+1F0h+var_1A0], eax
0x180095ae2  test    eax, eax
0x180095ae4  mov     eax, 479h
0x180095ae9  js      loc_1800959B6
0x180095aef  mov     word ptr [rsp+1F0h+var_19C], ax
0x180095af4  mov     rdx, [rbp+0F0h+var_120]; struct IUnknown *
0x180095af8  mov     rax, [rbp+0F0h+var_168]
0x180095afc  cmp     rax, rdx
0x180095aff  jz      short loc_180095B15
0x180095b01  lea     r8, _GUID_998a9007_a6fa_4e93_8c33_23760adab4b1; struct _GUID *
0x180095b08  lea     rcx, [rbp+0F0h+var_168]; struct IUnknown **
0x180095b0c  call    ?AtlComQIPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@AEBU_GUID@@@Z; ATL::AtlComQIPtrAssign(IUnknown * *,IUnknown *,_GUID const &)
0x180095b11  mov     rax, [rbp+0F0h+var_168]
0x180095b15  test    rax, rax
0x180095b18  jz      loc_180095BC1
0x180095b1e  xorps   xmm0, xmm0
0x180095b21  movups  xmmword ptr [rbp+0F0h+var_110], xmm0
0x180095b25  movups  [rbp+0F0h+var_100], xmm0
0x180095b29  lea     rdx, [rbp+0F0h+var_110]; struct PlaceholderInfo *
0x180095b2d  mov     rcx, [rsp+1F0h+FileHandle]; FileHandle
0x180095b32  call    ?GetPlaceholderInfo@CFspCloudFileSystemOperations@@SAJPEAXAEAUPlaceholderInfo@@@Z; CFspCloudFileSystemOperations::GetPlaceholderInfo(void *,PlaceholderInfo &)
0x180095b37  mov     [rsp+1F0h+var_1A0], eax
0x180095b3b  mov     [rsp+1F0h+var_1A0], eax
0x180095b3f  test    eax, eax
0x180095b41  mov     eax, 481h
0x180095b46  js      loc_1800959B6
0x180095b4c  mov     word ptr [rsp+1F0h+var_19C], ax
0x180095b51  mov     eax, 1
0x180095b56  cmp     dword ptr [rbp+0F0h+var_110.Information], eax
0x180095b59  cmovz   r15d, eax
0x180095b5d  test    r12d, r12d
0x180095b60  jz      short loc_180095BBA
0x180095b62  mov     rcx, [rbp+0F0h+var_168]
0x180095b66  mov     rax, [rcx]
0x180095b69  lea     rdx, [rbp+0F0h+var_140]
0x180095b6d  mov     rax, [rax+18h]
0x180095b71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095b76  movaps  xmm0, xmmword ptr [rbp+0F0h+var_90.Identifier]
0x180095b7a  movdqa  xmmword ptr [rbp+0F0h+var_110], xmm0
0x180095b7f  mov     ecx, r15d
0x180095b82  xor     ecx, 1
0x180095b85  mov     [rsp+1F0h+FsControlCode], ecx; int
0x180095b89  mov     r9, [rax]; union _LARGE_INTEGER
0x180095b8c  lea     r8, [rbp+0F0h+var_110]; struct _FILE_ID_128
0x180095b90  mov     rdx, rbx; unsigned __int16 *
0x180095b93  mov     rcx, r14; this
0x180095b96  call    ?AbortActiveHydration@CCloudFileSystemApplier@@AEAAJPEBGU_FILE_ID_128@@T_LARGE_INTEGER@@JH@Z; CCloudFileSystemApplier::AbortActiveHydration(ushort const *,_FILE_ID_128,_LARGE_INTEGER,long,int)
0x180095b9b  mov     [rsp+1F0h+var_1A0], eax
0x180095b9f  mov     [rsp+1F0h+var_1A0], eax
0x180095ba3  test    eax, eax
0x180095ba5  mov     eax, 48Bh
0x180095baa  js      loc_1800959B6
0x180095bb0  mov     word ptr [rsp+1F0h+var_19C], ax
0x180095bb5  mov     ebx, [rbp+0F0h+var_170]
0x180095bb8  jmp     short loc_180095BC4
0x180095bba  mov     ebx, eax
0x180095bbc  mov     [rbp+0F0h+var_170], eax
0x180095bbf  jmp     short loc_180095BC4
0x180095bc1  mov     ebx, r15d
0x180095bc4  test    esi, esi
0x180095bc6  jnz     short loc_180095BF9
0x180095bc8  lea     rdx, [rbp+0F0h+var_15C]; unsigned int *
0x180095bcc  mov     rcx, [rsp+1F0h+FileHandle]; FileHandle
0x180095bd1  call    ?GetAttributes@CFspCloudFileSystemOperations@@SAJPEAXPEAK@Z; CFspCloudFileSystemOperations::GetAttributes(void *,ulong *)
0x180095bd6  mov     [rsp+1F0h+var_1A0], eax
0x180095bda  mov     [rsp+1F0h+var_1A0], eax
0x180095bde  test    eax, eax
0x180095be0  mov     eax, 49Dh
0x180095be5  js      loc_1800959B6
0x180095beb  mov     word ptr [rsp+1F0h+var_19C], ax
0x180095bf0  mov     esi, [rbp+0F0h+var_15C]
0x180095bf3  and     esi, 186820h
0x180095bf9  test    r12d, r12d
0x180095bfc  jz      loc_180095CA8
0x180095c02  xorps   xmm0, xmm0
  ... truncated ...
```
