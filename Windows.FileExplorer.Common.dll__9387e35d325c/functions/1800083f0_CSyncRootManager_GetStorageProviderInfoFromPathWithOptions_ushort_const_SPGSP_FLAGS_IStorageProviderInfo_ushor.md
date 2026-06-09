# CSyncRootManager::GetStorageProviderInfoFromPathWithOptions(ushort const *,SPGSP_FLAGS,IStorageProviderInfo * *,ushort * *,STORAGE_PROVIDER_PATH_COMPARE_FLAGS *)

- ea: `0x1800083f0`
- end: `0x180008a30`
- name: `?GetStorageProviderInfoFromPathWithOptions@CSyncRootManager@@UEAAJPEBGW4SPGSP_FLAGS@@PEAPEAUIStorageProviderInfo@@PEAPEAGPEAW4STORAGE_PROVIDER_PATH_COMPARE_FLAGS@@@Z`
- size: `1600`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800083f0`
- `0x180009070`
- `0x180009374`
- `0x1800095fc`
- `0x18000964c`
- `0x18000a030`
- `0x18000a6e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x1800087dd`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x18000881b`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x180008880`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x1800088ba`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x1800087dd`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x18000881b`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x180008880`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x1800088ba`
- `Windows.Storage!__imp_PathComparePaths` at `0x1800085bf`
- `Windows.Storage!__imp_PathComparePaths` at `0x18000864c`
- `Windows.Storage!__imp_PathComparePaths` at `0x1800085bf`
- `Windows.Storage!__imp_PathComparePaths` at `0x18000864c`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x180008481`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x180008481`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008797`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008797`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800084b7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800084b7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180008516`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180008516`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800084d9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800084d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800088f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800088f8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSyncRootManager::GetStorageProviderInfoFromPathWithOptions(
        __int64 a1,
        wil *a2,
        unsigned int a3,
        struct IStorageProviderInfo **a4,
        _QWORD *a5,
        _DWORD *a6)
{
  _QWORD *v9; // r14
  _DWORD *v10; // rsi
  int StorageProviderInfo; // r13d
  __int64 v12; // rbp
  int v13; // ebx
  char v14; // bl
  RTL_SRWLOCK *v15; // rax
  unsigned __int64 v16; // rcx
  __int64 v17; // rax
  int v18; // r15d
  unsigned __int64 v19; // r12
  unsigned __int16 *v20; // rdi
  wil *v21; // rbp
  unsigned __int64 v22; // rax
  unsigned __int64 v23; // rax
  int v24; // eax
  char v25; // bp
  __int64 v26; // rbx
  CStorageProviderRootsCache *v27; // rcx
  const unsigned __int16 *v28; // rdx
  unsigned __int16 *v29; // rbp
  unsigned __int16 *v30; // rbx
  unsigned __int64 v31; // rax
  unsigned __int16 *v32; // rdi
  unsigned __int64 v33; // rax
  char v34; // al
  _WORD *v35; // rcx
  char v36; // r12
  __int64 v37; // rax
  __int16 *v38; // r14
  unsigned __int64 v39; // rax
  unsigned __int64 v40; // rbx
  unsigned __int64 v41; // rdi
  wil *v43; // rbx
  const unsigned __int16 *v44; // rdx
  const unsigned __int16 *v45; // rdx
  const unsigned __int16 *v46; // rdx
  const unsigned __int16 *v47; // rdx
  _WORD *v48; // rax
  _WORD *v49; // rdx
  __int16 v50; // cx
  __int64 v51; // [rsp+20h] [rbp-88h]
  __int64 v52; // [rsp+28h] [rbp-80h]
  unsigned __int64 v53; // [rsp+30h] [rbp-78h]
  __int64 v54; // [rsp+38h] [rbp-70h]
  RTL_SRWLOCK *v55; // [rsp+40h] [rbp-68h]
  PSRWLOCK SRWLock; // [rsp+48h] [rbp-60h] BYREF
  _OWORD v57[5]; // [rsp+50h] [rbp-58h] BYREF
  __int64 v58; // [rsp+B0h] [rbp+8h] BYREF
  wil *v59; // [rsp+B8h] [rbp+10h]
  struct IStorageProviderInfo **v60; // [rsp+C8h] [rbp+20h]

  v60 = a4;
  v59 = a2;
  if ( a4 )
    *a4 = 0;
  v9 = a5;
  if ( a5 )
    *a5 = 0;
  v10 = a6;
  if ( a6 )
    *a6 = 0;
  StorageProviderInfo = CSyncRootManager::_EnsureSyncRootManagerCache((CSyncRootManager *)(a1 - 56));
  if ( StorageProviderInfo >= 0 )
  {
    v12 = *(_QWORD *)(a1 + 40);
    v54 = v12;
    if ( a4 )
      *a4 = 0;
    if ( v9 )
      *v9 = 0;
    if ( v10 )
      *v10 = 0;
    v13 = *(_DWORD *)(v12 + 16);
    if ( v13 == SHGlobalCounterGetValue(GLOBALCOUNTER_FOLDERDEFINITION_CACHE|GLOBALCOUNTER_OVERLAYMANAGER)
      && (a3 & *(_DWORD *)(v12 + 20)) == a3 )
    {
      LODWORD(a6) = 0;
      v15 = (RTL_SRWLOCK *)(v12 + 24);
      v55 = (RTL_SRWLOCK *)(v12 + 24);
    }
    else
    {
      memset(v57, 0, 32);
      v55 = (RTL_SRWLOCK *)(v12 + 24);
      SRWLock = (PSRWLOCK)(v12 + 24);
      AcquireSRWLockExclusive((PSRWLOCK)(v12 + 24));
      StorageProviderInfo = CSyncRootManagerCache::_EnsureCachedValues(v12, &SRWLock, *(_DWORD *)(v12 + 20) | a3);
      ReleaseSRWLockExclusive(SRWLock);
      CSimplePointerArray<CStorageProviderRootsCache,CTContainer_PolicyNewMem,CSimpleArrayStandardCompareHelper<CStorageProviderRootsCache *>>::~CSimplePointerArray<CStorageProviderRootsCache,CTContainer_PolicyNewMem,CSimpleArrayStandardCompareHelper<CStorageProviderRootsCache *>>(v57);
      v14 = 0;
      LODWORD(a6) = 0;
      if ( StorageProviderInfo < 0 )
        goto LABEL_76;
      v15 = (RTL_SRWLOCK *)(v12 + 24);
    }
    AcquireSRWLockShared(v15);
    StorageProviderInfo = -2147023728;
    v16 = 0;
LABEL_20:
    v53 = v16;
    if ( v16 < *(_QWORD *)(v12 + 40) )
    {
      v17 = *(_QWORD *)(*(_QWORD *)(v12 + 32) + 8 * v16);
      v51 = v17;
      if ( v9 )
        *v9 = 0;
      if ( v10 )
        *v10 = 0;
      v18 = 1;
      v19 = 0;
      v52 = 0;
      while ( 1 )
      {
        if ( v19 >= *(_QWORD *)(v17 + 568) )
        {
LABEL_56:
          if ( v10 )
            LODWORD(a6) = *v10 | (unsigned int)a6;
          v16 = v53 + 1;
          v12 = v54;
          goto LABEL_20;
        }
        v20 = *(unsigned __int16 **)(*(_QWORD *)(*(_QWORD *)(v17 + 560) + 8 * v19) + 24LL);
        v21 = v59;
        v22 = -1;
        do
          ++v22;
        while ( *((_WORD *)v59 + v22) );
        if ( v22 >= 6 )
        {
          v43 = (wil *)((char *)v59 + 8);
          if ( (unsigned int)_o_iswalpha(*((unsigned __int16 *)v59 + 4)) )
          {
            if ( *((_WORD *)v59 + 5) == 58 && wil::is_extended_length_path(v59, v44) )
              v21 = v43;
          }
        }
        v23 = -1;
        do
          ++v23;
        while ( v20[v23] );
        if ( v23 >= 6
          && (unsigned int)_o_iswalpha(v20[4])
          && v20[5] == 58
          && wil::is_extended_length_path((wil *)v20, v45) )
        {
          v20 += 4;
        }
        v24 = PathComparePaths(v20, v21);
        v25 = v24;
        LODWORD(v58) = v24;
        v26 = v51;
        if ( (v24 & 0xE) != 0 )
        {
          v36 = 1;
        }
        else
        {
          v27 = *(CStorageProviderRootsCache **)(*(_QWORD *)(v51 + 560) + 8 * v19);
          v28 = (const unsigned __int16 *)*((_QWORD *)v27 + 6);
          v29 = (unsigned __int16 *)v59;
          if ( !v28 || !*v28 )
            goto LABEL_35;
          v36 = 0;
          if ( !CStorageProviderRootsCache::_PathIsEqualOrSubFolder(
                  v27,
                  v28,
                  (const unsigned __int16 *)v59,
                  (unsigned int *)&v58) )
          {
            v19 = v52;
LABEL_35:
            if ( v10 )
            {
              v30 = *(unsigned __int16 **)(*(_QWORD *)(*(_QWORD *)(v51 + 560) + 8 * v19) + 24LL);
              v31 = -1;
              do
                ++v31;
              while ( v30[v31] );
              if ( v31 >= 6
                && (unsigned int)_o_iswalpha(v30[4])
                && v30[5] == 58
                && wil::is_extended_length_path((wil *)v30, v46) )
              {
                v30 += 4;
              }
              v32 = v29;
              v33 = -1;
              do
                ++v33;
              while ( v29[v33] );
              if ( v33 >= 6 )
              {
                if ( (unsigned int)_o_iswalpha(v29[4]) && v29[5] == 58 && wil::is_extended_length_path((wil *)v29, v47) )
                  v32 = v29 + 4;
                v9 = a5;
              }
              v34 = PathComparePaths(v32, v30);
              if ( (v34 & 0xE) != 0 && (v34 & 4) != 0 && (*(_DWORD *)(v51 + 544) & 0x202) == 0x202 )
                *v10 |= 4u;
            }
            goto LABEL_43;
          }
          v25 = v58;
        }
        if ( v9 )
          break;
LABEL_49:
        if ( v10 )
        {
          if ( !v36 )
            *v10 |= 1u;
          if ( (v25 & 2) != 0 )
          {
            *v10 |= 2u;
            if ( (*(_DWORD *)(v26 + 544) & 0x200) == 0 )
              *v10 |= 4u;
          }
        }
        if ( v18 >= 0 )
        {
          v18 = 0;
LABEL_55:
          if ( !v18 )
          {
            if ( v60 )
              StorageProviderInfo = CStorageProviderRootsCache::GetStorageProviderInfo(
                                      *(CStorageProviderRootsCache **)(*(_QWORD *)(v54 + 32) + 8 * v53),
                                      v60);
            else
              StorageProviderInfo = 0;
            goto LABEL_75;
          }
          goto LABEL_56;
        }
        v19 = v52;
LABEL_43:
        v52 = ++v19;
        if ( v18 != 1 )
          goto LABEL_55;
        v17 = v51;
      }
      v37 = *(_QWORD *)(*(_QWORD *)(v51 + 560) + 8 * v52);
      *v9 = 0;
      v38 = *(__int16 **)v37;
      if ( !*(_QWORD *)v37 )
      {
        v18 = -2147023728;
        goto LABEL_72;
      }
      v39 = *(_QWORD *)(v37 + 8);
      if ( v39 == -1 )
      {
        v39 = -1;
        do
          ++v39;
        while ( v38[v39] );
      }
      v40 = -1;
      do
        ++v40;
      while ( v38[v40] );
      if ( v39 == -1 )
      {
        v39 = v40;
      }
      else if ( v39 < v40 )
      {
        v40 = v39;
      }
      v41 = v39 + 1;
      if ( v39 + 1 < v39 || (v58 = 0, !is_mul_ok(v41, 2u)) )
      {
        v18 = -2147024362;
        goto LABEL_71;
      }
      v48 = CoTaskMemAlloc(2 * v41);
      v49 = v48;
      if ( !v48 )
      {
        v18 = -2147024882;
LABEL_71:
        v26 = v51;
LABEL_72:
        v9 = a5;
        goto LABEL_49;
      }
      *v48 = 0;
      if ( v41 )
      {
        if ( v41 <= 0x7FFFFFFF )
        {
          v18 = 0;
          if ( v40 > 0x7FFFFFFE )
          {
            *v48 = 0;
          }
          else
          {
            do
            {
              if ( !v40 )
                break;
              v50 = *v38;
              if ( !*v38 )
                break;
              ++v38;
              *v48++ = v50;
              --v40;
              --v41;
            }
            while ( v41 );
            v35 = v48 - 1;
            if ( v41 )
              v35 = v48;
            *v35 = 0;
          }
          goto LABEL_48;
        }
        *v48 = 0;
      }
      v18 = 0;
LABEL_48:
      v9 = a5;
      *a5 = v49;
      v26 = v51;
      goto LABEL_49;
    }
LABEL_75:
    ReleaseSRWLockShared(v55);
    v14 = (char)a6;
LABEL_76:
    if ( StorageProviderInfo == -2147023728 && v10 && (v14 & 4) != 0 )
      *v10 |= 4u;
  }
  return (unsigned int)StorageProviderInfo;
}

```

## disassembly

```asm
0x1800083f0  mov     [rsp+arg_10], rbx
0x1800083f5  mov     [rsp+arg_18], r9
0x1800083fa  mov     [rsp+arg_8], rdx
0x1800083ff  push    rbp
0x180008400  push    rsi
0x180008401  push    rdi
0x180008402  push    r12
0x180008404  push    r13
0x180008406  push    r14
0x180008408  push    r15
0x18000840a  sub     rsp, 70h
0x18000840e  mov     r15, r9
0x180008411  mov     edi, r8d
0x180008414  mov     rbx, rcx
0x180008417  xor     r12d, r12d
0x18000841a  test    r9, r9
0x18000841d  jz      short loc_180008422
0x18000841f  mov     [r9], r12
0x180008422  mov     r14, [rsp+0A8h+arg_20]
0x18000842a  test    r14, r14
0x18000842d  jnz     loc_180008A07
0x180008433  mov     rsi, [rsp+0A8h+arg_28]
0x18000843b  test    rsi, rsi
0x18000843e  jz      short loc_180008443
0x180008440  mov     [rsi], r12d
0x180008443  add     rcx, 0FFFFFFFFFFFFFFC8h; this
0x180008447  call    ?_EnsureSyncRootManagerCache@CSyncRootManager@@AEAAJXZ; CSyncRootManager::_EnsureSyncRootManagerCache(void)
0x18000844c  mov     r13d, eax
0x18000844f  test    eax, eax
0x180008451  js      loc_1800087BB
0x180008457  mov     rbp, [rbx+28h]
0x18000845b  mov     [rsp+0A8h+var_70], rbp
0x180008460  test    r15, r15
0x180008463  jz      short loc_180008468
0x180008465  mov     [r15], r12
0x180008468  test    r14, r14
0x18000846b  jnz     loc_180008966
0x180008471  test    rsi, rsi
0x180008474  jz      short loc_180008479
0x180008476  mov     [rsi], r12d
0x180008479  mov     ebx, [rbp+10h]
0x18000847c  mov     ecx, 39h ; '9'; id
0x180008481  call    cs:__imp_SHGlobalCounterGetValue
0x180008487  cmp     ebx, eax
0x180008489  jnz     short loc_180008494
0x18000848b  mov     eax, [rbp+14h]
0x18000848e  and     eax, edi
0x180008490  cmp     eax, edi
0x180008492  jz      short loc_180008502
0x180008494  xorps   xmm0, xmm0
0x180008497  movdqu  [rsp+0A8h+var_58], xmm0
0x18000849d  xorps   xmm1, xmm1
0x1800084a0  movdqu  [rsp+0A8h+var_48], xmm1
0x1800084a6  lea     rax, [rbp+18h]
0x1800084aa  mov     [rsp+0A8h+var_68], rax
0x1800084af  mov     [rsp+0A8h+SRWLock], rax
0x1800084b4  mov     rcx, rax; SRWLock
0x1800084b7  call    cs:__imp_AcquireSRWLockExclusive
0x1800084bd  nop
0x1800084be  or      edi, [rbp+14h]
0x1800084c1  mov     r8d, edi
0x1800084c4  lea     rdx, [rsp+0A8h+SRWLock]
0x1800084c9  mov     rcx, rbp
0x1800084cc  call    ?_EnsureCachedValues@CSyncRootManagerCache@@AEAAJAEAVLockCacheAndFreeStale@@W4SPGSP_FLAGS@@@Z; CSyncRootManagerCache::_EnsureCachedValues(LockCacheAndFreeStale &,SPGSP_FLAGS)
0x1800084d1  mov     r13d, eax
0x1800084d4  mov     rcx, [rsp+0A8h+SRWLock]; SRWLock
0x1800084d9  call    cs:__imp_ReleaseSRWLockExclusive
0x1800084df  lea     rcx, [rsp+0A8h+var_58]
0x1800084e4  call    ??1?$CSimplePointerArray@VCStorageProviderRootsCache@@VCTContainer_PolicyNewMem@@V?$CSimpleArrayStandardCompareHelper@PEAVCStorageProviderRootsCache@@@@@@QEAA@XZ; CSimplePointerArray<CStorageProviderRootsCache,CTContainer_PolicyNewMem,CSimpleArrayStandardCompareHelper<CStorageProviderRootsCache *>>::~CSimplePointerArray<CStorageProviderRootsCache,CTContainer_PolicyNewMem,CSimpleArrayStandardCompareHelper<CStorageProviderRootsCache *>>(void)
0x1800084e9  mov     ebx, r12d
0x1800084ec  mov     dword ptr [rsp+0A8h+arg_28], ebx
0x1800084f3  test    r13d, r13d
0x1800084f6  js      loc_1800087A4
0x1800084fc  lea     rax, [rbp+18h]
0x180008500  jmp     short loc_180008513
0x180008502  mov     dword ptr [rsp+0A8h+arg_28], r12d
0x18000850a  lea     rax, [rbp+18h]
0x18000850e  mov     [rsp+0A8h+var_68], rax
0x180008513  mov     rcx, rax; SRWLock
0x180008516  call    cs:__imp_AcquireSRWLockShared
0x18000851c  mov     r13d, 80070490h
0x180008522  xor     r8d, r8d
0x180008525  mov     ecx, r8d
0x180008528  mov     [rsp+0A8h+var_78], rcx
0x18000852d  cmp     rcx, [rbp+28h]
0x180008531  jnb     loc_180008792
0x180008537  mov     rax, [rbp+20h]
0x18000853b  mov     rax, [rax+rcx*8]
0x18000853f  mov     [rsp+0A8h+var_88], rax
0x180008544  test    r14, r14
0x180008547  jz      short loc_18000854C
0x180008549  mov     [r14], r8
0x18000854c  test    rsi, rsi
0x18000854f  jz      short loc_180008554
0x180008551  mov     [rsi], r8d
0x180008554  mov     r15d, 1
0x18000855a  mov     r12, r8
0x18000855d  mov     [rsp+0A8h+var_80], r8
0x180008562  cmp     r12, [rax+238h]
0x180008569  jnb     loc_1800086C1
0x18000856f  mov     rax, [rax+230h]
0x180008576  mov     rcx, [rax+r12*8]
0x18000857a  mov     rdi, [rcx+18h]
0x18000857e  mov     rcx, [rsp+0A8h+arg_8]
0x180008586  mov     rbp, rcx
0x180008589  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000858d  inc     rax
0x180008590  cmp     [rcx+rax*2], r8w
0x180008595  jnz     short loc_18000858D
0x180008597  cmp     rax, 6
0x18000859b  jnb     loc_1800087D6
0x1800085a1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800085a5  inc     rax
0x1800085a8  cmp     [rdi+rax*2], r8w
0x1800085ad  jnz     short loc_1800085A5
0x1800085af  cmp     rax, 6
0x1800085b3  jnb     loc_180008814
0x1800085b9  mov     rdx, rbp
0x1800085bc  mov     rcx, rdi
0x1800085bf  call    cs:__imp_PathComparePaths
0x1800085c5  mov     ebp, eax
0x1800085c7  mov     dword ptr [rsp+0A8h+arg_0], eax
0x1800085ce  mov     rbx, [rsp+0A8h+var_88]
0x1800085d3  xor     r8d, r8d
0x1800085d6  test    al, 0Eh
0x1800085d8  jnz     loc_1800086E8
0x1800085de  mov     rax, [rbx+230h]
0x1800085e5  mov     rcx, [rax+r12*8]; this
0x1800085e9  mov     rdx, [rcx+30h]; unsigned __int16 *
0x1800085ed  mov     rbp, [rsp+0A8h+arg_8]
0x1800085f5  test    rdx, rdx
0x1800085f8  jnz     loc_180008847
0x1800085fe  test    rsi, rsi
0x180008601  jz      short loc_18000865D
0x180008603  mov     rax, [rbx+230h]
0x18000860a  mov     rcx, [rax+r12*8]
0x18000860e  mov     rbx, [rcx+18h]
0x180008612  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008616  inc     rax
0x180008619  cmp     [rbx+rax*2], r8w
0x18000861e  jnz     short loc_180008616
0x180008620  cmp     rax, 6
0x180008624  jnb     loc_180008879
0x18000862a  mov     rdi, rbp
0x18000862d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008631  inc     rax
0x180008634  cmp     [rbp+rax*2+0], r8w
0x18000863a  jnz     short loc_180008631
0x18000863c  cmp     rax, 6
0x180008640  jnb     loc_1800088B2
0x180008646  mov     rdx, rbx
0x180008649  mov     rcx, rdi
0x18000864c  call    cs:__imp_PathComparePaths
0x180008652  test    al, 0Eh
0x180008654  jnz     loc_18000899D
0x18000865a  xor     r8d, r8d
0x18000865d  inc     r12
0x180008660  mov     [rsp+0A8h+var_80], r12
0x180008665  cmp     r15d, 1
0x180008669  jnz     short loc_1800086B8
0x18000866b  mov     rax, [rsp+0A8h+var_88]
0x180008670  jmp     loc_180008562
0x180008675  lea     rcx, [rax-2]
0x180008679  test    rdi, rdi
0x18000867c  cmovnz  rcx, rax
0x180008680  mov     [rcx], r8w
0x180008684  mov     r14, [rsp+0A8h+arg_20]
0x18000868c  mov     [r14], rdx
0x18000868f  mov     rbx, [rsp+0A8h+var_88]
0x180008694  test    rsi, rsi
0x180008697  jz      short loc_1800086AC
0x180008699  test    r12b, r12b
0x18000869c  jz      loc_18000896E
0x1800086a2  test    bpl, 2
0x1800086a6  jnz     loc_180008976
0x1800086ac  test    r15d, r15d
0x1800086af  js      loc_1800089C7
0x1800086b5  mov     r15d, r8d
0x1800086b8  test    r15d, r15d
0x1800086bb  jz      loc_180008767
0x1800086c1  test    rsi, rsi
0x1800086c4  jz      short loc_1800086D6
0x1800086c6  mov     ebx, dword ptr [rsp+0A8h+arg_28]
0x1800086cd  or      ebx, [rsi]
0x1800086cf  mov     dword ptr [rsp+0A8h+arg_28], ebx
0x1800086d6  mov     rcx, [rsp+0A8h+var_78]
0x1800086db  inc     rcx
0x1800086de  mov     rbp, [rsp+0A8h+var_70]
0x1800086e3  jmp     loc_180008528
0x1800086e8  mov     r12b, 1
0x1800086eb  test    r14, r14
0x1800086ee  jz      short loc_180008694
0x1800086f0  mov     rax, [rbx+230h]
0x1800086f7  mov     rcx, [rsp+0A8h+var_80]
0x1800086fc  mov     rax, [rax+rcx*8]
0x180008700  mov     [r14], r8
0x180008703  mov     r14, [rax]
0x180008706  test    r14, r14
0x180008709  jz      loc_1800089F7
0x18000870f  mov     rax, [rax+8]
0x180008713  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180008717  cmp     rax, rcx
0x18000871a  jnz     short loc_180008729
0x18000871c  mov     rax, rcx
0x18000871f  inc     rax
0x180008722  cmp     [r14+rax*2], r8w
0x180008727  jnz     short loc_18000871F
0x180008729  mov     rbx, rcx
0x18000872c  inc     rbx
0x18000872f  cmp     [r14+rbx*2], r8w
0x180008734  jnz     short loc_18000872C
0x180008736  cmp     rax, rcx
0x180008739  jnz     loc_180008991
0x18000873f  mov     rax, rbx
0x180008742  lea     rdi, [rax+1]
0x180008746  cmp     rdi, rax
0x180008749  jnb     loc_1800088DC
0x18000874f  mov     r15d, 80070216h
0x180008755  mov     rbx, [rsp+0A8h+var_88]
0x18000875a  mov     r14, [rsp+0A8h+arg_20]
0x180008762  jmp     loc_180008694
0x180008767  mov     rdx, [rsp+0A8h+arg_18]; struct IStorageProviderInfo **
0x18000876f  test    rdx, rdx
0x180008772  jz      loc_1800089D1
0x180008778  mov     rcx, [rsp+0A8h+var_70]
0x18000877d  mov     rcx, [rcx+20h]
0x180008781  mov     rax, [rsp+0A8h+var_78]
0x180008786  mov     rcx, [rcx+rax*8]; this
0x18000878a  call    ?GetStorageProviderInfo@CStorageProviderRootsCache@@QEAAJPEAPEAUIStorageProviderInfo@@@Z; CStorageProviderRootsCache::GetStorageProviderInfo(IStorageProviderInfo * *)
0x18000878f  mov     r13d, eax
0x180008792  mov     rcx, [rsp+0A8h+var_68]; SRWLock
0x180008797  call    cs:__imp_ReleaseSRWLockShared
0x18000879d  mov     ebx, dword ptr [rsp+0A8h+arg_28]
0x1800087a4  cmp     r13d, 80070490h
0x1800087ab  jnz     short loc_1800087BB
0x1800087ad  test    rsi, rsi
0x1800087b0  jz      short loc_1800087BB
0x1800087b2  test    bl, 4
0x1800087b5  jnz     loc_1800089FF
0x1800087bb  mov     eax, r13d
0x1800087be  mov     rbx, [rsp+0A8h+arg_10]
0x1800087c6  add     rsp, 70h
0x1800087ca  pop     r15
0x1800087cc  pop     r14
0x1800087ce  pop     r13
0x1800087d0  pop     r12
0x1800087d2  pop     rdi
0x1800087d3  pop     rsi
0x1800087d4  pop     rbp
0x1800087d5  retn
0x1800087d6  lea     rbx, [rcx+8]
0x1800087da  movzx   ecx, word ptr [rbx]
0x1800087dd  call    cs:__imp__o_iswalpha
0x1800087e3  xor     r8d, r8d
0x1800087e6  test    eax, eax
0x1800087e8  jz      loc_1800085A1
0x1800087ee  mov     rcx, [rsp+0A8h+arg_8]; this
0x1800087f6  cmp     word ptr [rcx+0Ah], 3Ah ; ':'
0x1800087fb  jnz     loc_1800085A1
0x180008801  call    ?is_extended_length_path@wil@@YA_NPEBG@Z; wil::is_extended_length_path(ushort const *)
0x180008806  xor     r8d, r8d
0x180008809  test    al, al
0x18000880b  cmovnz  rbp, rbx
0x18000880f  jmp     loc_1800085A1
0x180008814  lea     rbx, [rdi+8]
0x180008818  movzx   ecx, word ptr [rbx]
0x18000881b  call    cs:__imp__o_iswalpha
0x180008821  test    eax, eax
0x180008823  jz      loc_1800085B9
0x180008829  cmp     word ptr [rdi+0Ah], 3Ah ; ':'
0x18000882e  jnz     loc_1800085B9
0x180008834  mov     rcx, rdi; this
0x180008837  call    ?is_extended_length_path@wil@@YA_NPEBG@Z; wil::is_extended_length_path(ushort const *)
0x18000883c  test    al, al
0x18000883e  cmovnz  rdi, rbx
0x180008842  jmp     loc_1800085B9
0x180008847  cmp     [rdx], r8w
0x18000884b  jz      loc_1800085FE
0x180008851  mov     r12b, r8b
0x180008854  lea     r9, [rsp+0A8h+arg_0]; unsigned int *
0x18000885c  mov     r8, rbp; unsigned __int16 *
0x18000885f  call    ?_PathIsEqualOrSubFolder@CStorageProviderRootsCache@@AEAA_NPEBG0PEAK@Z; CStorageProviderRootsCache::_PathIsEqualOrSubFolder(ushort const *,ushort const *,ulong *)
0x180008864  xor     r8d, r8d
0x180008867  test    al, al
0x180008869  jnz     loc_180008A0F
0x18000886f  mov     r12, [rsp+0A8h+var_80]
0x180008874  jmp     loc_1800085FE
0x180008879  lea     rdi, [rbx+8]
0x18000887d  movzx   ecx, word ptr [rdi]
0x180008880  call    cs:__imp__o_iswalpha
0x180008886  xor     r8d, r8d
0x180008889  test    eax, eax
0x18000888b  jz      loc_18000862A
0x180008891  cmp     word ptr [rbx+0Ah], 3Ah ; ':'
0x180008896  jnz     loc_18000862A
0x18000889c  mov     rcx, rbx; this
0x18000889f  call    ?is_extended_length_path@wil@@YA_NPEBG@Z; wil::is_extended_length_path(ushort const *)
0x1800088a4  xor     r8d, r8d
0x1800088a7  test    al, al
0x1800088a9  cmovnz  rbx, rdi
  ... truncated ...
```
