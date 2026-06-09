# CSyncRootManager::GetStorageProviderInfoFromPath(ushort const *,IStorageProviderInfo * *,ushort * *,STORAGE_PROVIDER_PATH_COMPARE_FLAGS *)

- ea: `0x180008a40`
- end: `0x18000906a`
- name: `?GetStorageProviderInfoFromPath@CSyncRootManager@@UEAAJPEBGPEAPEAUIStorageProviderInfo@@PEAPEAGPEAW4STORAGE_PROVIDER_PATH_COMPARE_FLAGS@@@Z`
- size: `1578`
- prototype: `int(CSyncRootManager *__hidden this, const unsigned __int16 *, struct IStorageProviderInfo **, unsigned __int16 **, enum STORAGE_PROVIDER_PATH_COMPARE_FLAGS *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180008a40`
- `0x180009070`
- `0x180009374`
- `0x1800095fc`
- `0x18000964c`
- `0x180009f70`
- `0x18000a030`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x180008e1a`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x180008e4e`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x180008ead`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x180008ee0`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x180008e1a`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x180008e4e`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x180008ead`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x180008ee0`
- `Windows.Storage!__imp_PathComparePaths` at `0x180008c1a`
- `Windows.Storage!__imp_PathComparePaths` at `0x180008c9e`
- `Windows.Storage!__imp_PathComparePaths` at `0x180008c1a`
- `Windows.Storage!__imp_PathComparePaths` at `0x180008c9e`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x180008ac9`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x180008ac9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008dd8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008dd8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008afc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008afc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180008b54`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180008b54`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008b1d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008b1d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008f2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008f2d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSyncRootManager::GetStorageProviderInfoFromPath(
        CSyncRootManager *this,
        wil *a2,
        struct IStorageProviderInfo **a3,
        unsigned __int16 **a4,
        enum STORAGE_PROVIDER_PATH_COMPARE_FLAGS *a5)
{
  unsigned __int16 **v5; // r15
  unsigned __int64 v9; // r12
  enum STORAGE_PROVIDER_PATH_COMPARE_FLAGS *v10; // rdi
  __int64 result; // rax
  __int64 v12; // rsi
  unsigned int v13; // ebx
  int StorageProviderInfo; // ebx
  char v15; // bp
  RTL_SRWLOCK *v16; // rax
  unsigned __int64 v17; // rcx
  __int64 v18; // r13
  int v19; // r15d
  unsigned __int16 *v20; // rbx
  const unsigned __int16 *v21; // rsi
  unsigned __int64 v22; // rax
  unsigned __int64 v23; // rax
  char v24; // bp
  wil *v25; // rcx
  unsigned __int16 *v26; // rbx
  unsigned __int64 v27; // rax
  const unsigned __int16 *v28; // rsi
  unsigned __int64 v29; // rax
  char v30; // al
  char v31; // r15
  __int64 v32; // rax
  unsigned __int16 *v33; // rdi
  unsigned __int64 v34; // rax
  unsigned __int64 v35; // rbx
  unsigned __int64 v36; // rsi
  const unsigned __int16 *v37; // rdx
  const unsigned __int16 *v38; // rdx
  const unsigned __int16 *v39; // rdx
  const unsigned __int16 *v40; // rdx
  unsigned __int16 *v41; // rax
  unsigned __int16 *v42; // r8
  unsigned __int16 *v43; // rdx
  unsigned __int16 v44; // ax
  unsigned __int16 *v45; // rcx
  int v46; // [rsp+20h] [rbp-88h]
  unsigned __int64 v47; // [rsp+28h] [rbp-80h]
  __int64 v48; // [rsp+30h] [rbp-78h]
  RTL_SRWLOCK *v49; // [rsp+38h] [rbp-70h]
  __int64 v50; // [rsp+40h] [rbp-68h]
  PSRWLOCK SRWLock; // [rsp+48h] [rbp-60h] BYREF
  _OWORD v52[5]; // [rsp+50h] [rbp-58h] BYREF
  int v53; // [rsp+B0h] [rbp+8h]

  v5 = a4;
  v9 = 0;
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  v10 = a5;
  if ( a5 )
    *(_DWORD *)a5 = 0;
  result = CSyncRootManager::_EnsureSyncRootManagerCache((CSyncRootManager *)((char *)this - 32));
  if ( (int)result >= 0 )
  {
    v12 = *((_QWORD *)this + 8);
    v48 = v12;
    if ( a3 )
      *a3 = 0;
    if ( v5 )
      *v5 = 0;
    if ( a5 )
      *(_DWORD *)a5 = 0;
    v13 = *(_DWORD *)(v12 + 16);
    if ( __PAIR64__(*(_DWORD *)(v12 + 20), v13) == ((unsigned int)SHGlobalCounterGetValue(GLOBALCOUNTER_FOLDERDEFINITION_CACHE|GLOBALCOUNTER_OVERLAYMANAGER)
                                                  | 0xFFFFFFFF00000000uLL) )
    {
      v46 = 0;
      v16 = (RTL_SRWLOCK *)(v12 + 24);
      v49 = (RTL_SRWLOCK *)(v12 + 24);
    }
    else
    {
      memset(v52, 0, 32);
      v49 = (RTL_SRWLOCK *)(v12 + 24);
      SRWLock = (PSRWLOCK)(v12 + 24);
      AcquireSRWLockExclusive((PSRWLOCK)(v12 + 24));
      StorageProviderInfo = CSyncRootManagerCache::_EnsureCachedValues(v12, &SRWLock, 0xFFFFFFFFLL);
      ReleaseSRWLockExclusive(SRWLock);
      CSimplePointerArray<CStorageProviderRootsCache,CTContainer_PolicyNewMem,CSimpleArrayStandardCompareHelper<CStorageProviderRootsCache *>>::~CSimplePointerArray<CStorageProviderRootsCache,CTContainer_PolicyNewMem,CSimpleArrayStandardCompareHelper<CStorageProviderRootsCache *>>(v52);
      v15 = 0;
      v46 = 0;
      if ( StorageProviderInfo < 0 )
        goto LABEL_67;
      v16 = (RTL_SRWLOCK *)(v12 + 24);
    }
    AcquireSRWLockShared(v16);
    v17 = 0;
LABEL_19:
    v47 = v17;
    if ( v17 < *(_QWORD *)(v12 + 40) )
    {
      v50 = 8 * v17;
      v18 = *(_QWORD *)(8 * v17 + *(_QWORD *)(v12 + 32));
      if ( v5 )
        *v5 = 0;
      if ( v10 )
        *(_DWORD *)v10 = 0;
      v19 = 1;
      v53 = 1;
      while ( 1 )
      {
        if ( v9 >= *(_QWORD *)(v18 + 568) )
        {
LABEL_44:
          if ( v10 )
            v46 |= *(_DWORD *)v10;
          v17 = v47 + 1;
          v12 = v48;
          v5 = a4;
          v9 = 0;
          goto LABEL_19;
        }
        v20 = *(unsigned __int16 **)(*(_QWORD *)(*(_QWORD *)(v18 + 560) + 8 * v9) + 24LL);
        v21 = (const unsigned __int16 *)a2;
        v22 = -1;
        do
          ++v22;
        while ( *((_WORD *)a2 + v22) );
        if ( v22 >= 6
          && (unsigned int)_o_iswalpha(*((unsigned __int16 *)a2 + 4))
          && *((_WORD *)a2 + 5) == 58
          && wil::is_extended_length_path(a2, v37) )
        {
          v21 = (const unsigned __int16 *)((char *)a2 + 8);
        }
        v23 = -1;
        do
          ++v23;
        while ( v20[v23] );
        if ( v23 >= 6
          && (unsigned int)_o_iswalpha(v20[4])
          && v20[5] == 58
          && wil::is_extended_length_path((wil *)v20, v38) )
        {
          v20 += 4;
        }
        v24 = PathComparePaths(v20, v21);
        if ( (v24 & 0xE) != 0 )
        {
          v31 = 1;
        }
        else
        {
          v25 = *(wil **)(*(_QWORD *)(*(_QWORD *)(v18 + 560) + 8 * v9) + 48LL);
          if ( !v25 || !*(_WORD *)v25 )
            goto LABEL_34;
          v31 = 0;
          v24 = PathComparePathsStripLongPathPrefix(v25, a2);
          if ( (v24 & 0xE) == 0 )
          {
            v19 = v53;
LABEL_34:
            v10 = a5;
            if ( a5 )
            {
              v26 = *(unsigned __int16 **)(*(_QWORD *)(*(_QWORD *)(v18 + 560) + 8 * v9) + 24LL);
              v27 = -1;
              do
                ++v27;
              while ( v26[v27] );
              if ( v27 >= 6
                && (unsigned int)_o_iswalpha(v26[4])
                && v26[5] == 58
                && wil::is_extended_length_path((wil *)v26, v39) )
              {
                v26 += 4;
              }
              v28 = (const unsigned __int16 *)a2;
              v29 = -1;
              do
                ++v29;
              while ( *((_WORD *)a2 + v29) );
              if ( v29 >= 6
                && (unsigned int)_o_iswalpha(*((unsigned __int16 *)a2 + 4))
                && *((_WORD *)a2 + 5) == 58
                && wil::is_extended_length_path(a2, v40) )
              {
                v28 = (const unsigned __int16 *)((char *)a2 + 8);
              }
              v30 = PathComparePaths(v28, v26);
              v10 = a5;
              if ( (v30 & 0xE) != 0 && (v30 & 4) != 0 && (*(_DWORD *)(v18 + 544) & 0x202) == 0x202 )
                *(_DWORD *)a5 |= 4u;
            }
            goto LABEL_42;
          }
        }
        if ( a4 )
        {
          v32 = *(_QWORD *)(*(_QWORD *)(v18 + 560) + 8 * v9);
          *a4 = 0;
          v33 = *(unsigned __int16 **)v32;
          if ( *(_QWORD *)v32 )
          {
            v34 = *(_QWORD *)(v32 + 8);
            if ( v34 == -1 )
            {
              do
                ++v34;
              while ( v33[v34] );
            }
            v35 = -1;
            do
              ++v35;
            while ( v33[v35] );
            if ( v34 == -1 )
            {
              v34 = v35;
            }
            else if ( v34 < v35 )
            {
              v35 = v34;
            }
            v36 = v34 + 1;
            if ( v34 + 1 < v34 || !is_mul_ok(v36, 2u) )
            {
              v53 = -2147024362;
              goto LABEL_58;
            }
            v41 = (unsigned __int16 *)CoTaskMemAlloc(2 * v36);
            v42 = v41;
            if ( v41 )
            {
              *v41 = 0;
              if ( v36 )
              {
                if ( v36 <= 0x7FFFFFFF )
                {
                  v53 = 0;
                  if ( v35 > 0x7FFFFFFE )
                  {
                    *v41 = 0;
                  }
                  else
                  {
                    v43 = v41;
                    do
                    {
                      if ( !v35 )
                        break;
                      v44 = *v33;
                      if ( !*v33 )
                        break;
                      ++v33;
                      *v43++ = v44;
                      --v35;
                      --v36;
                    }
                    while ( v36 );
                    v45 = v43 - 1;
                    if ( v36 )
                      v45 = v43;
                    *v45 = 0;
                  }
                  goto LABEL_108;
                }
                *v41 = 0;
              }
              v53 = 0;
LABEL_108:
              *a4 = v42;
              goto LABEL_58;
            }
            v53 = -2147024882;
          }
          else
          {
            v53 = -2147023728;
          }
        }
LABEL_58:
        v10 = a5;
        if ( a5 )
        {
          if ( !v31 )
            *(_DWORD *)a5 |= 1u;
          if ( (v24 & 2) != 0 )
          {
            *(_DWORD *)a5 |= 2u;
            if ( (*(_DWORD *)(v18 + 544) & 0x200) == 0 )
              *(_DWORD *)a5 |= 4u;
          }
        }
        v19 = v53;
        if ( v53 >= 0 )
        {
          v19 = 0;
LABEL_43:
          if ( !v19 )
          {
            if ( a3 )
              StorageProviderInfo = CStorageProviderRootsCache::GetStorageProviderInfo(
                                      *(CStorageProviderRootsCache **)(v50 + *(_QWORD *)(v48 + 32)),
                                      a3);
            else
              StorageProviderInfo = 0;
            goto LABEL_66;
          }
          goto LABEL_44;
        }
LABEL_42:
        ++v9;
        if ( v19 != 1 )
          goto LABEL_43;
      }
    }
    StorageProviderInfo = -2147023728;
LABEL_66:
    ReleaseSRWLockShared(v49);
    v15 = v46;
LABEL_67:
    if ( StorageProviderInfo == -2147023728 && v10 && (v15 & 4) != 0 )
      *(_DWORD *)v10 |= 4u;
    return (unsigned int)StorageProviderInfo;
  }
  return result;
}

```

## disassembly

```asm
0x180008a40  mov     [rsp+arg_8], rbx
0x180008a45  mov     [rsp+arg_18], r9
0x180008a4a  mov     [rsp+arg_10], r8
0x180008a4f  push    rbp
0x180008a50  push    rsi
0x180008a51  push    rdi
0x180008a52  push    r12
0x180008a54  push    r13
0x180008a56  push    r14
0x180008a58  push    r15
0x180008a5a  sub     rsp, 70h
0x180008a5e  mov     r15, r9
0x180008a61  mov     rbp, r8
0x180008a64  mov     r14, rdx
0x180008a67  mov     rbx, rcx
0x180008a6a  xor     r12d, r12d
0x180008a6d  test    r8, r8
0x180008a70  jz      short loc_180008A75
0x180008a72  mov     [r8], r12
0x180008a75  test    r15, r15
0x180008a78  jz      short loc_180008A7D
0x180008a7a  mov     [r9], r12
0x180008a7d  mov     rdi, [rsp+0A8h+arg_20]
0x180008a85  test    rdi, rdi
0x180008a88  jz      short loc_180008A8D
0x180008a8a  mov     [rdi], r12d
0x180008a8d  add     rcx, 0FFFFFFFFFFFFFFE0h; this
0x180008a91  call    ?_EnsureSyncRootManagerCache@CSyncRootManager@@AEAAJXZ; CSyncRootManager::_EnsureSyncRootManagerCache(void)
0x180008a96  test    eax, eax
0x180008a98  js      loc_180008DFB
0x180008a9e  mov     rsi, [rbx+40h]
0x180008aa2  mov     [rsp+0A8h+var_78], rsi
0x180008aa7  test    rbp, rbp
0x180008aaa  jz      short loc_180008AB0
0x180008aac  mov     [rbp+0], r12
0x180008ab0  test    r15, r15
0x180008ab3  jnz     loc_180008FB4
0x180008ab9  test    rdi, rdi
0x180008abc  jz      short loc_180008AC1
0x180008abe  mov     [rdi], r12d
0x180008ac1  mov     ebx, [rsi+10h]
0x180008ac4  mov     ecx, 39h ; '9'; id
0x180008ac9  call    cs:__imp_SHGlobalCounterGetValue
0x180008acf  cmp     ebx, eax
0x180008ad1  jnz     short loc_180008AD9
0x180008ad3  cmp     dword ptr [rsi+14h], 0FFFFFFFFh
0x180008ad7  jz      short loc_180008B43
0x180008ad9  xorps   xmm0, xmm0
0x180008adc  movdqu  [rsp+0A8h+var_58], xmm0
0x180008ae2  xorps   xmm1, xmm1
0x180008ae5  movdqu  [rsp+0A8h+var_48], xmm1
0x180008aeb  lea     rax, [rsi+18h]
0x180008aef  mov     [rsp+0A8h+var_70], rax
0x180008af4  mov     [rsp+0A8h+SRWLock], rax
0x180008af9  mov     rcx, rax; SRWLock
0x180008afc  call    cs:__imp_AcquireSRWLockExclusive
0x180008b02  nop
0x180008b03  mov     r8d, 0FFFFFFFFh
0x180008b09  lea     rdx, [rsp+0A8h+SRWLock]
0x180008b0e  mov     rcx, rsi
0x180008b11  call    ?_EnsureCachedValues@CSyncRootManagerCache@@AEAAJAEAVLockCacheAndFreeStale@@W4SPGSP_FLAGS@@@Z; CSyncRootManagerCache::_EnsureCachedValues(LockCacheAndFreeStale &,SPGSP_FLAGS)
0x180008b16  mov     ebx, eax
0x180008b18  mov     rcx, [rsp+0A8h+SRWLock]; SRWLock
0x180008b1d  call    cs:__imp_ReleaseSRWLockExclusive
0x180008b23  lea     rcx, [rsp+0A8h+var_58]
0x180008b28  call    ??1?$CSimplePointerArray@VCStorageProviderRootsCache@@VCTContainer_PolicyNewMem@@V?$CSimpleArrayStandardCompareHelper@PEAVCStorageProviderRootsCache@@@@@@QEAA@XZ; CSimplePointerArray<CStorageProviderRootsCache,CTContainer_PolicyNewMem,CSimpleArrayStandardCompareHelper<CStorageProviderRootsCache *>>::~CSimplePointerArray<CStorageProviderRootsCache,CTContainer_PolicyNewMem,CSimpleArrayStandardCompareHelper<CStorageProviderRootsCache *>>(void)
0x180008b2d  mov     ebp, r12d
0x180008b30  mov     [rsp+0A8h+var_88], r12d
0x180008b35  test    ebx, ebx
0x180008b37  js      loc_180008DE2
0x180008b3d  lea     rax, [rsi+18h]
0x180008b41  jmp     short loc_180008B51
0x180008b43  mov     [rsp+0A8h+var_88], r12d
0x180008b48  lea     rax, [rsi+18h]
0x180008b4c  mov     [rsp+0A8h+var_70], rax
0x180008b51  mov     rcx, rax; SRWLock
0x180008b54  call    cs:__imp_AcquireSRWLockShared
0x180008b5a  mov     [rsp+0A8h+var_84], 80070490h
0x180008b62  mov     rcx, r12
0x180008b65  mov     [rsp+0A8h+var_80], rcx
0x180008b6a  cmp     rcx, [rsi+28h]
0x180008b6e  jnb     loc_18000902F
0x180008b74  lea     rcx, ds:0[rcx*8]
0x180008b7c  mov     [rsp+0A8h+var_68], rcx
0x180008b81  mov     rax, [rsi+20h]
0x180008b85  mov     r13, [rcx+rax]
0x180008b89  test    r15, r15
0x180008b8c  jz      short loc_180008B91
0x180008b8e  mov     [r15], r12
0x180008b91  test    rdi, rdi
0x180008b94  jz      short loc_180008B99
0x180008b96  mov     [rdi], r12d
0x180008b99  mov     r15d, 1
0x180008b9f  mov     dword ptr [rsp+0A8h+arg_0], r15d
0x180008ba7  nop     word ptr [rax+rax+00000000h]
0x180008bb0  cmp     r12, [r13+238h]
0x180008bb7  jnb     loc_180008CCA
0x180008bbd  mov     rax, [r13+230h]
0x180008bc4  mov     rcx, [rax+r12*8]
0x180008bc8  mov     rbx, [rcx+18h]
0x180008bcc  mov     rsi, r14
0x180008bcf  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180008bd6  nop     word ptr [rax+rax+00000000h]
0x180008be0  inc     rax
0x180008be3  cmp     word ptr [r14+rax*2], 0
0x180008be9  jnz     short loc_180008BE0
0x180008beb  cmp     rax, 6
0x180008bef  jnb     loc_180008E13
0x180008bf5  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180008bfc  nop     dword ptr [rax+00h]
0x180008c00  inc     rax
0x180008c03  cmp     word ptr [rbx+rax*2], 0
0x180008c08  jnz     short loc_180008C00
0x180008c0a  cmp     rax, 6
0x180008c0e  jnb     loc_180008E47
0x180008c14  mov     rdx, rsi
0x180008c17  mov     rcx, rbx
0x180008c1a  call    cs:__imp_PathComparePaths
0x180008c20  mov     ebp, eax
0x180008c22  test    al, 0Eh
0x180008c24  jnz     loc_180008CF6
0x180008c2a  mov     rax, [r13+230h]
0x180008c31  mov     rcx, [rax+r12*8]
0x180008c35  mov     rcx, [rcx+30h]; this
0x180008c39  test    rcx, rcx
0x180008c3c  jnz     loc_180008E7A
0x180008c42  mov     rdi, [rsp+0A8h+arg_20]
0x180008c4a  test    rdi, rdi
0x180008c4d  jz      short loc_180008CB4
0x180008c4f  mov     rax, [r13+230h]
0x180008c56  mov     rcx, [rax+r12*8]
0x180008c5a  mov     rbx, [rcx+18h]
0x180008c5e  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180008c65  inc     rax
0x180008c68  cmp     word ptr [rbx+rax*2], 0
0x180008c6d  jnz     short loc_180008C65
0x180008c6f  cmp     rax, 6
0x180008c73  jnb     loc_180008EA6
0x180008c79  mov     rsi, r14
0x180008c7c  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180008c83  inc     rax
0x180008c86  cmp     word ptr [r14+rax*2], 0
0x180008c8c  jnz     short loc_180008C83
0x180008c8e  cmp     rax, 6
0x180008c92  jnb     loc_180008ED9
0x180008c98  mov     rdx, rbx
0x180008c9b  mov     rcx, rsi
0x180008c9e  call    cs:__imp_PathComparePaths
0x180008ca4  mov     rdi, [rsp+0A8h+arg_20]
0x180008cac  test    al, 0Eh
0x180008cae  jnz     loc_180008FF1
0x180008cb4  inc     r12
0x180008cb7  cmp     r15d, 1
0x180008cbb  jz      loc_180008BB0
0x180008cc1  test    r15d, r15d
0x180008cc4  jz      loc_180008DA9
0x180008cca  test    rdi, rdi
0x180008ccd  jz      short loc_180008CD9
0x180008ccf  mov     eax, [rsp+0A8h+var_88]
0x180008cd3  or      eax, [rdi]
0x180008cd5  mov     [rsp+0A8h+var_88], eax
0x180008cd9  mov     rcx, [rsp+0A8h+var_80]
0x180008cde  inc     rcx
0x180008ce1  mov     rsi, [rsp+0A8h+var_78]
0x180008ce6  mov     r15, [rsp+0A8h+arg_18]
0x180008cee  xor     r12d, r12d
0x180008cf1  jmp     loc_180008B65
0x180008cf6  mov     r15b, 1
0x180008cf9  mov     rcx, [rsp+0A8h+arg_18]
0x180008d01  test    rcx, rcx
0x180008d04  jz      short loc_180008D70
0x180008d06  mov     rax, [r13+230h]
0x180008d0d  mov     rax, [rax+r12*8]
0x180008d11  mov     qword ptr [rcx], 0
0x180008d18  mov     rdi, [rax]
0x180008d1b  test    rdi, rdi
0x180008d1e  jz      loc_180009038
0x180008d24  mov     rax, [rax+8]
0x180008d28  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180008d2c  jnz     short loc_180008D3A
0x180008d2e  xchg    ax, ax
0x180008d30  inc     rax
0x180008d33  cmp     word ptr [rdi+rax*2], 0
0x180008d38  jnz     short loc_180008D30
0x180008d3a  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180008d41  inc     rbx
0x180008d44  cmp     word ptr [rdi+rbx*2], 0
0x180008d49  jnz     short loc_180008D41
0x180008d4b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180008d4f  jnz     loc_180008FE0
0x180008d55  mov     rax, rbx
0x180008d58  lea     rsi, [rax+1]
0x180008d5c  cmp     rsi, rax
0x180008d5f  jnb     loc_180008F0D
0x180008d65  mov     dword ptr [rsp+0A8h+arg_0], 80070216h
0x180008d70  mov     rdi, [rsp+0A8h+arg_20]
0x180008d78  test    rdi, rdi
0x180008d7b  jz      short loc_180008D90
0x180008d7d  test    r15b, r15b
0x180008d80  jz      loc_180008FBC
0x180008d86  test    bpl, 2
0x180008d8a  jnz     loc_180008FC4
0x180008d90  mov     r15d, dword ptr [rsp+0A8h+arg_0]
0x180008d98  test    r15d, r15d
0x180008d9b  js      loc_180008CB4
0x180008da1  xor     r15d, r15d
0x180008da4  jmp     loc_180008CC1
0x180008da9  mov     rdx, [rsp+0A8h+arg_10]; struct IStorageProviderInfo **
0x180008db1  test    rdx, rdx
0x180008db4  jz      loc_180009018
0x180008dba  mov     rcx, [rsp+0A8h+var_78]
0x180008dbf  mov     rcx, [rcx+20h]
0x180008dc3  mov     rax, [rsp+0A8h+var_68]
0x180008dc8  mov     rcx, [rax+rcx]; this
0x180008dcc  call    ?GetStorageProviderInfo@CStorageProviderRootsCache@@QEAAJPEAPEAUIStorageProviderInfo@@@Z; CStorageProviderRootsCache::GetStorageProviderInfo(IStorageProviderInfo * *)
0x180008dd1  mov     ebx, eax
0x180008dd3  mov     rcx, [rsp+0A8h+var_70]; SRWLock
0x180008dd8  call    cs:__imp_ReleaseSRWLockShared
0x180008dde  mov     ebp, [rsp+0A8h+var_88]
0x180008de2  cmp     ebx, 80070490h
0x180008de8  jnz     short loc_180008DF9
0x180008dea  test    rdi, rdi
0x180008ded  jz      short loc_180008DF9
0x180008def  test    bpl, 4
0x180008df3  jnz     loc_180009048
0x180008df9  mov     eax, ebx
0x180008dfb  mov     rbx, [rsp+0A8h+arg_8]
0x180008e03  add     rsp, 70h
0x180008e07  pop     r15
0x180008e09  pop     r14
0x180008e0b  pop     r13
0x180008e0d  pop     r12
0x180008e0f  pop     rdi
0x180008e10  pop     rsi
0x180008e11  pop     rbp
0x180008e12  retn
0x180008e13  lea     rdi, [r14+8]
0x180008e17  movzx   ecx, word ptr [rdi]
0x180008e1a  call    cs:__imp__o_iswalpha
0x180008e20  test    eax, eax
0x180008e22  jz      loc_180008BF5
0x180008e28  cmp     word ptr [r14+0Ah], 3Ah ; ':'
0x180008e2e  jnz     loc_180008BF5
0x180008e34  mov     rcx, r14; this
0x180008e37  call    ?is_extended_length_path@wil@@YA_NPEBG@Z; wil::is_extended_length_path(ushort const *)
0x180008e3c  test    al, al
0x180008e3e  cmovnz  rsi, rdi
0x180008e42  jmp     loc_180008BF5
0x180008e47  lea     rdi, [rbx+8]
0x180008e4b  movzx   ecx, word ptr [rdi]
0x180008e4e  call    cs:__imp__o_iswalpha
0x180008e54  test    eax, eax
0x180008e56  jz      loc_180008C14
0x180008e5c  cmp     word ptr [rbx+0Ah], 3Ah ; ':'
0x180008e61  jnz     loc_180008C14
0x180008e67  mov     rcx, rbx; this
0x180008e6a  call    ?is_extended_length_path@wil@@YA_NPEBG@Z; wil::is_extended_length_path(ushort const *)
0x180008e6f  test    al, al
0x180008e71  cmovnz  rbx, rdi
0x180008e75  jmp     loc_180008C14
0x180008e7a  cmp     word ptr [rcx], 0
0x180008e7e  jz      loc_180008C42
0x180008e84  xor     r15b, r15b
0x180008e87  mov     rdx, r14; wil *
0x180008e8a  call    ?PathComparePathsStripLongPathPrefix@@YAKPEBG0@Z; PathComparePathsStripLongPathPrefix(ushort const *,ushort const *)
0x180008e8f  mov     ebp, eax
0x180008e91  test    al, 0Eh
0x180008e93  jnz     loc_180008CF9
0x180008e99  mov     r15d, dword ptr [rsp+0A8h+arg_0]
0x180008ea1  jmp     loc_180008C42
0x180008ea6  lea     rdi, [rbx+8]
0x180008eaa  movzx   ecx, word ptr [rdi]
0x180008ead  call    cs:__imp__o_iswalpha
0x180008eb3  test    eax, eax
0x180008eb5  jz      loc_180008C79
0x180008ebb  cmp     word ptr [rbx+0Ah], 3Ah ; ':'
0x180008ec0  jnz     loc_180008C79
0x180008ec6  mov     rcx, rbx; this
0x180008ec9  call    ?is_extended_length_path@wil@@YA_NPEBG@Z; wil::is_extended_length_path(ushort const *)
0x180008ece  test    al, al
0x180008ed0  cmovnz  rbx, rdi
0x180008ed4  jmp     loc_180008C79
0x180008ed9  lea     rdi, [r14+8]
0x180008edd  movzx   ecx, word ptr [rdi]
0x180008ee0  call    cs:__imp__o_iswalpha
0x180008ee6  test    eax, eax
0x180008ee8  jz      loc_180008C98
0x180008eee  cmp     word ptr [r14+0Ah], 3Ah ; ':'
0x180008ef4  jnz     loc_180008C98
0x180008efa  mov     rcx, r14; this
0x180008efd  call    ?is_extended_length_path@wil@@YA_NPEBG@Z; wil::is_extended_length_path(ushort const *)
0x180008f02  test    al, al
0x180008f04  cmovnz  rsi, rdi
0x180008f08  jmp     loc_180008C98
0x180008f0d  mov     [rsp+0A8h+arg_0], 0
0x180008f19  mov     eax, 2
0x180008f1e  mul     rsi
0x180008f21  test    rdx, rdx
0x180008f24  jnz     loc_180008D65
0x180008f2a  mov     rcx, rax; cb
  ... truncated ...
```
