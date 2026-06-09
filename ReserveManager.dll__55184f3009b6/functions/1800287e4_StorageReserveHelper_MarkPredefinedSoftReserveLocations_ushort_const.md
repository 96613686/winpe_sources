# StorageReserveHelper::MarkPredefinedSoftReserveLocations(ushort const *)

- ea: `0x1800287e4`
- end: `0x18002898f`
- name: `?MarkPredefinedSoftReserveLocations@StorageReserveHelper@@YAJPEBG@Z`
- size: `427`
- prototype: `__int64 __fastcall(StorageReserveHelper *this, const unsigned __int16 *, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180019634`

## callees

- `0x180003870`
- `0x18000a0f4`
- `0x180025b48`
- `0x180025cdc`
- `0x180026eb8`
- `0x180028644`
- `0x1800287e4`
- `0x180028998`
- `0x18002a1fc`
- `0x18002a648`
- `0x18002b4e4`
- `0x18002d33c`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800288d7`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800288d7`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180028928`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180028928`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1800288c6`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1800288c6`

## pseudocode

```c
__int64 __fastcall StorageReserveHelper::MarkPredefinedSoftReserveLocations(
        StorageReserveHelper *this,
        const unsigned __int16 *a2,
        __int64 a3)
{
  StorageReserveHelper::Internal *v4; // rcx
  unsigned int v5; // ebx
  __int64 v6; // rdx
  __int64 v7; // r9
  int Dependencies; // eax
  int v9; // edi
  unsigned int i; // ebx
  const unsigned __int16 *v11; // rdx
  enum _STORAGE_RESERVE_ID v12; // r8d
  int v13; // esi
  const unsigned __int16 *v14; // rdi
  _DWORD *v15; // rcx
  StorageReserveTelemetry::Internal::SRProvider *v16; // rcx
  int v18; // [rsp+20h] [rbp-E0h]
  LPCWSTR pszPath[4]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v20[42]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+E8h]

  wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v20,
    "MarkPredefinedSoftReserveLocations",
    a3);
  v20[0] = &StorageReserveTelemetry::Internal::SRProvider::MarkPredefinedSoftReserveLocations::`vftable';
  StorageReserveTelemetry::Internal::SRProvider::MarkPredefinedSoftReserveLocations::StartActivity((StorageReserveTelemetry::Internal::SRProvider::MarkPredefinedSoftReserveLocations *)v20);
  if ( !this )
  {
    v5 = -2147024809;
    v6 = 1065;
    v7 = 2147942487LL;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\storagereserve\\storagereservehelper.cpp",
      (const char *)v7,
      v18);
    goto LABEL_19;
  }
  Dependencies = StorageReserveHelper::Internal::LoadDependencies(v4);
  v5 = Dependencies;
  if ( Dependencies < 0 )
  {
    v7 = (unsigned int)Dependencies;
    v6 = 1066;
    goto LABEL_5;
  }
  v9 = 0;
  for ( i = 0; i < 9; ++i )
  {
    pszPath[0] = 0;
    pszPath[1] = (LPCWSTR)-1LL;
    pszPath[2] = (LPCWSTR)-1LL;
    if ( (int)((__int64 (__fastcall *)(StorageReserveHelper *, const unsigned __int16 *const near *const, __int64, LPCWSTR *))StorageReserveHelper::Internal::pfnPathAllocCombine)(
                this,
                (&StorageReserveHelper::Internal::SoftReservePaths)[i],
                1,
                pszPath) >= 0
      && (PathFileExistsW(pszPath[0]) || CreateDirectoryW(pszPath[0], 0)) )
    {
      v13 = StorageReserveHelper::SetReserveAreaOnFileTree((StorageReserveHelper *)pszPath[0], v11, v12);
      if ( v13 >= 0 )
      {
        v14 = pszPath[0];
        v15 = (_DWORD *)*((_QWORD *)StorageReserveTelemetry::Internal::SRProvider::Instance() + 1);
        if ( v15 && *v15 )
        {
          StorageReserveTelemetry::Internal::SRProvider::Instance();
          StorageReserveTelemetry::Internal::SRProvider::MarkSoftReserveLocations_(v16, v13, v14);
        }
        v9 = 1;
      }
    }
    if ( pszPath[0] )
      LocalFree((HLOCAL)pszPath[0]);
  }
  v5 = v9 == 0 ? 0x80004005 : 0;
  StorageReserveTelemetry::Internal::SRProvider::MarkPredefinedSoftReserveLocations::Stop(
    (StorageReserveTelemetry::Internal::SRProvider::MarkPredefinedSoftReserveLocations *)v20,
    (const unsigned __int16 *)this,
    v5);
LABEL_19:
  v20[0] = &StorageReserveTelemetry::Internal::SRProvider::MarkPredefinedSoftReserveLocations::`vftable';
  wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v20);
  wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v20);
  return v5;
}

```

## disassembly

```asm
0x1800287e4  push    rbp
0x1800287e6  push    rbx
0x1800287e7  push    rsi
0x1800287e8  push    rdi
0x1800287e9  push    r12
0x1800287eb  push    r14
0x1800287ed  lea     rbp, [rsp-0B8h]
0x1800287f5  sub     rsp, 1B8h
0x1800287fc  mov     rax, cs:__security_cookie
0x180028803  xor     rax, rsp
0x180028806  mov     [rbp+0E0h+var_40], rax
0x18002880d  mov     r14, rcx
0x180028810  lea     rdx, aMarkpredefined; "MarkPredefinedSoftReserveLocations"
0x180028817  lea     rcx, [rsp+1E0h+var_190]
0x18002881c  call    ??0?$ActivityBase@VStorageReserveProvider@Internal@StorageReserveTelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180028821  lea     r12, ??_7MarkPredefinedSoftReserveLocations@SRProvider@Internal@StorageReserveTelemetry@@6B@; const StorageReserveTelemetry::Internal::SRProvider::MarkPredefinedSoftReserveLocations::`vftable'
0x180028828  lea     rcx, [rsp+1E0h+var_190]; this
0x18002882d  mov     [rsp+1E0h+var_190], r12
0x180028832  call    ?StartActivity@MarkPredefinedSoftReserveLocations@SRProvider@Internal@StorageReserveTelemetry@@QEAAXXZ; StorageReserveTelemetry::Internal::SRProvider::MarkPredefinedSoftReserveLocations::StartActivity(void)
0x180028837  test    r14, r14
0x18002883a  jnz     short loc_18002884B
0x18002883c  mov     ebx, 80070057h
0x180028841  mov     edx, 429h
0x180028846  mov     r9d, ebx
0x180028849  jmp     short loc_18002885E
0x18002884b  call    ?LoadDependencies@Internal@StorageReserveHelper@@YAJXZ; StorageReserveHelper::Internal::LoadDependencies(void)
0x180028850  mov     ebx, eax
0x180028852  test    eax, eax
0x180028854  jns     short loc_180028876
0x180028856  mov     r9d, eax; char *
0x180028859  mov     edx, 42Ah; void *
0x18002885e  mov     rcx, [rbp+0E8h]; this
0x180028865  lea     r8, aOnecoreDrivers_1; "onecore\\drivers\\storage\\storsvc\\sto"...
0x18002886c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028871  jmp     loc_180028955
0x180028876  xor     edi, edi
0x180028878  xor     ebx, ebx
0x18002887a  lea     rax, ?SoftReservePaths@Internal@StorageReserveHelper@@3QBQEBGB; ushort const * const near * const StorageReserveHelper::Internal::SoftReservePaths
0x180028881  movsxd  rdx, ebx
0x180028884  lea     r9, [rsp+1E0h+pszPath]
0x180028889  mov     [rsp+1E0h+pszPath], 0
0x180028892  mov     r8d, 1
0x180028898  mov     [rsp+1E0h+var_1A8], 0FFFFFFFFFFFFFFFFh
0x1800288a1  mov     rcx, r14
0x1800288a4  mov     [rsp+1E0h+var_1A0], 0FFFFFFFFFFFFFFFFh
0x1800288ad  mov     rdx, [rax+rdx*8]
0x1800288b1  mov     rax, cs:?pfnPathAllocCombine@Internal@StorageReserveHelper@@3P6AJPEBG0KPEAPEAG@ZEA; long (*StorageReserveHelper::Internal::pfnPathAllocCombine)(ushort const *,ushort const *,ulong,ushort * *)
0x1800288b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800288bd  test    eax, eax
0x1800288bf  js      short loc_18002891E
0x1800288c1  mov     rcx, [rsp+1E0h+pszPath]; pszPath
0x1800288c6  call    cs:__imp_PathFileExistsW
0x1800288cc  test    eax, eax
0x1800288ce  jnz     short loc_1800288E1
0x1800288d0  mov     rcx, [rsp+1E0h+pszPath]; lpPathName
0x1800288d5  xor     edx, edx; lpSecurityAttributes
0x1800288d7  call    cs:__imp_CreateDirectoryW
0x1800288dd  test    eax, eax
0x1800288df  jz      short loc_18002891E
0x1800288e1  mov     rcx, [rsp+1E0h+pszPath]; this
0x1800288e6  call    ?SetReserveAreaOnFileTree@StorageReserveHelper@@YAJPEBGW4_STORAGE_RESERVE_ID@@@Z; StorageReserveHelper::SetReserveAreaOnFileTree(ushort const *,_STORAGE_RESERVE_ID)
0x1800288eb  mov     esi, eax
0x1800288ed  test    eax, eax
0x1800288ef  js      short loc_18002891E
0x1800288f1  mov     rdi, [rsp+1E0h+pszPath]
0x1800288f6  call    ?Instance@SRProvider@Internal@StorageReserveTelemetry@@KAPEAV123@XZ; StorageReserveTelemetry::Internal::SRProvider::Instance(void)
0x1800288fb  mov     rcx, [rax+8]
0x1800288ff  test    rcx, rcx
0x180028902  jz      short loc_180028919
0x180028904  mov     ecx, [rcx]
0x180028906  test    ecx, ecx
0x180028908  jz      short loc_180028919
0x18002890a  call    ?Instance@SRProvider@Internal@StorageReserveTelemetry@@KAPEAV123@XZ; StorageReserveTelemetry::Internal::SRProvider::Instance(void)
0x18002890f  mov     r8, rdi; unsigned __int16 *
0x180028912  mov     edx, esi; int
0x180028914  call    ?MarkSoftReserveLocations_@SRProvider@Internal@StorageReserveTelemetry@@QEAAXJPEBG@Z; StorageReserveTelemetry::Internal::SRProvider::MarkSoftReserveLocations_(long,ushort const *)
0x180028919  mov     edi, 1
0x18002891e  mov     rcx, [rsp+1E0h+pszPath]; hMem
0x180028923  test    rcx, rcx
0x180028926  jz      short loc_18002892E
0x180028928  call    cs:__imp_LocalFree
0x18002892e  inc     ebx
0x180028930  cmp     ebx, 9
0x180028933  jb      loc_18002887A
0x180028939  neg     edi
0x18002893b  lea     rcx, [rsp+1E0h+var_190]; this
0x180028940  mov     rdx, r14; unsigned __int16 *
0x180028943  sbb     ebx, ebx
0x180028945  not     ebx
0x180028947  and     ebx, 80004005h
0x18002894d  mov     r8d, ebx; int
0x180028950  call    ?Stop@MarkPredefinedSoftReserveLocations@SRProvider@Internal@StorageReserveTelemetry@@QEAAXPEBGJ@Z; StorageReserveTelemetry::Internal::SRProvider::MarkPredefinedSoftReserveLocations::Stop(ushort const *,long)
0x180028955  lea     rcx, [rsp+1E0h+var_190]
0x18002895a  mov     [rsp+1E0h+var_190], r12
0x18002895f  call    ?Destroy@?$ActivityBase@VStorageReserveProvider@Internal@StorageReserveTelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180028964  lea     rcx, [rsp+1E0h+var_190]
0x180028969  call    ??1?$ActivityBase@VStorageReserveProvider@Internal@StorageReserveTelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18002896e  mov     eax, ebx
0x180028970  mov     rcx, [rbp+0E0h+var_40]
0x180028977  xor     rcx, rsp; StackCookie
0x18002897a  call    __security_check_cookie
0x18002897f  add     rsp, 1B8h
0x180028986  pop     r14
0x180028988  pop     r12
0x18002898a  pop     rdi
0x18002898b  pop     rsi
0x18002898c  pop     rbx
0x18002898d  pop     rbp
0x18002898e  retn
```
