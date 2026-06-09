# NDXGI::CDevice::AllocateCB_0022(D3D10DDI_HRTDEVICE,D3D12DDICB_ALLOCATE_0022 *)

- ea: `0x18005c5d0`
- end: `0x18005ce4d`
- name: `?AllocateCB_0022@CDevice@NDXGI@@SAJUD3D10DDI_HRTDEVICE@@PEAUD3D12DDICB_ALLOCATE_0022@@@Z`
- size: `2173`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18005c400`

## callees

- `0x18000345c`
- `0x180006994`
- `0x1800074c4`
- `0x180007df0`
- `0x18000b010`
- `0x18000b920`
- `0x18000bfd8`
- `0x18000c290`
- `0x1800447c8`
- `0x18004b9a0`
- `0x18004eb40`
- `0x18005c5d0`
- `0x18006e0a4`
- `0x180074d90`
- `0x18007f054`
- `0x1800b9818`
- `0x1800bc07c`
- `0x1800bc094`

## import_xrefs

- `msvcp_win!_Thrd_id` at `0x18005ca01`
- `msvcp_win!_Thrd_id` at `0x18005ca01`
- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-0!__imp_D3DKMTCreateAllocation2` at `0x18005cc33`
- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-0!__imp_D3DKMTGetAllocationPriority` at `0x18005cda6`

## string_xrefs

- `0x18005cc2c`: `CreateAllocation2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall NDXGI::CDevice::AllocateCB_0022(__int64 a1, __int64 *a2)
{
  __int64 v4; // r9
  __int64 i; // r12
  unsigned int v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // rbx
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rcx
  char v12; // bl
  __int64 v13; // rbx
  __int64 j; // r12
  __int64 v15; // rdx
  __int64 v16; // rbx
  SIZE_T v17; // rbx
  char *v18; // rax
  char *v19; // rdx
  __int64 v20; // r8
  char *v21; // rsi
  _DWORD *v22; // rbx
  __int64 v23; // r9
  __int64 v24; // rax
  int v25; // ecx
  __int64 v26; // rsi
  __int64 v27; // rcx
  __int64 v28; // rax
  __int64 v29; // rcx
  __int64 v30; // rax
  __int64 v31; // rcx
  _OWORD *v32; // r13
  __int64 *v33; // r12
  _OWORD *v34; // rcx
  __int64 v35; // rax
  unsigned int v36; // ecx
  unsigned int v37; // ecx
  __int64 v38; // r8
  unsigned int v39; // r12d
  __int64 v40; // rdx
  __int64 v41; // r8
  __int64 v42; // r9
  int v43; // r13d
  __int64 v44; // rdx
  __int64 v45; // r8
  _DWORD *v46; // rax
  __int64 v47; // r8
  unsigned int k; // r9d
  unsigned int v49; // eax
  __int64 v50; // rcx
  __int64 v51; // r9
  __int64 result; // rax
  int v53; // [rsp+30h] [rbp-E8h] BYREF
  __int64 v54; // [rsp+34h] [rbp-E4h]
  __int64 v55; // [rsp+40h] [rbp-D8h]
  int v56; // [rsp+48h] [rbp-D0h]
  __int64 v57; // [rsp+50h] [rbp-C8h]
  int v58; // [rsp+58h] [rbp-C0h]
  unsigned int v59; // [rsp+5Ch] [rbp-BCh]
  char *v60; // [rsp+60h] [rbp-B8h]
  int v61; // [rsp+68h] [rbp-B0h]
  _BYTE v62[24]; // [rsp+80h] [rbp-98h] BYREF
  char *v63; // [rsp+98h] [rbp-80h]
  _Smtx_t *v64; // [rsp+A0h] [rbp-78h] BYREF
  char v65; // [rsp+A8h] [rbp-70h]
  std::bad_alloc *v66; // [rsp+B0h] [rbp-68h] BYREF
  _com_error *v67; // [rsp+B8h] [rbp-60h] BYREF
  _BYTE v68[88]; // [rsp+C0h] [rbp-58h] BYREF
  __int64 v69; // [rsp+120h] [rbp+8h] BYREF
  __int64 v70; // [rsp+130h] [rbp+18h] BYREF
  char *v71; // [rsp+138h] [rbp+20h] BYREF

  try
  {
    if ( (unsigned __int8)((__int64 (*)(void))wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShareBackingStoreWithKMD>::__private_IsEnabled)() )
    {
      if ( *((_DWORD *)a2 + 7) )
        LOBYTE(v69) = (*(_BYTE *)(a2[4] + 32) & 8) != 0;
      else
        LOBYTE(v69) = 0;
      for ( i = 0; ; i = (unsigned int)(i + 1) )
      {
        v6 = *((_DWORD *)a2 + 7);
        if ( (unsigned int)i >= v6 )
          goto LABEL_37;
        v7 = (unsigned int)i;
        v8 = 96 * i;
        v9 = *(unsigned int *)(96 * i + a2[4] + 32);
        if ( *(_BYTE *)(*(_QWORD *)(a1 + 24) + 296LL) < 0x42u )
        {
          if ( (v9 & 0xFFFFFFF8) == 0 )
            goto LABEL_19;
          CJournal::RecordJournal(v9, -2147024809, (__int64)"Reserved flags given to AllocateCb", v4, 0);
          ThrowFailure(-2147024809);
        }
        else
        {
          if ( (v9 & 0xFFFFFFF0) != 0 )
          {
            CJournal::RecordJournal(v9, -2147024809, (__int64)"Reserved flags given to AllocateCb", v4, 0);
            ThrowFailure(-2147024809);
          }
          v10 = a2[4];
          v11 = *(_DWORD *)(v8 + v10 + 32) & 8;
          v12 = (*(_DWORD *)(v8 + v10 + 32) & 8) != 0;
          if ( a2[2] && (_DWORD)v11 )
          {
            CJournal::RecordJournal(
              v11,
              -2147024809,
              (__int64)"AllocateCB - hResource was non-null when D3D12DDI_ALLOCATION_INFO_FLAGS_0022_SHARED flag was set.",
              v4,
              0);
            ThrowFailure(-2147024809);
          }
          if ( (_BYTE)v69 != v12 )
          {
            CJournal::RecordJournal(
              v11,
              -2147024809,
              (__int64)"AllocateCB - all allocationInfos must have the same value set for D3D12DDI_ALLOCATION_INFO_FLAGS_0022_SHARED.",
              v4,
              0);
            ThrowFailure(-2147024809);
          }
        }
        v7 = (unsigned int)i;
LABEL_19:
        if ( *(_BYTE *)(*(_QWORD *)(a1 + 24) + 296LL) >= 0xAu )
        {
          v13 = 0;
          while ( (unsigned int)v13 < 5 )
          {
            if ( *(_QWORD *)(a2[4] + 8 * (v13 + 12 * v7) + 56) )
            {
              CJournal::RecordJournal(
                3 * v7,
                -2147024809,
                (__int64)"Reserved fields in D3D12DDI_ALLOCATION_INFO_0022 were not zero.",
                v4,
                0);
              ThrowFailure(-2147024809);
            }
            v13 = (unsigned int)(v13 + 1);
            v7 = (unsigned int)i;
          }
        }
      }
    }
    LOBYTE(v69) = 0;
    for ( j = 0; ; j = (unsigned int)(j + 1) )
    {
      v6 = *((_DWORD *)a2 + 7);
      if ( (unsigned int)j >= v6 )
        break;
      v15 = (unsigned int)j;
      if ( (*(_DWORD *)(96 * j + a2[4] + 32) & 0xFFFFFFF8) != 0 )
      {
        CJournal::RecordJournal(96 * j, -2147024809, (__int64)"Reserved flags given to AllocateCb", v4, 0);
        ThrowFailure(-2147024809);
        v15 = (unsigned int)j;
      }
      if ( *(_BYTE *)(*(_QWORD *)(a1 + 24) + 296LL) >= 0xAu )
      {
        v16 = 0;
        while ( (unsigned int)v16 < 5 )
        {
          if ( *(_QWORD *)(a2[4] + 8 * (v16 + 12 * v15) + 56) )
          {
            CJournal::RecordJournal(
              3 * v15,
              -2147024809,
              (__int64)"Reserved fields in D3D12DDI_ALLOCATION_INFO_0022 were not zero.",
              v4,
              0);
            ThrowFailure(-2147024809);
          }
          v16 = (unsigned int)(v16 + 1);
          v15 = (unsigned int)j;
        }
      }
    }
LABEL_37:
    memset_0(&v53, 0, 0x48u);
    v53 = *(_DWORD *)(a1 + 56);
    v54 = 0;
    v55 = 0;
    v56 = 0;
    v57 = *a2;
    v58 = *((_DWORD *)a2 + 2);
    v59 = v6;
    v71 = 0;
    v17 = saturated_mul(v6, 0x60u);
    v18 = (char *)operator new(v17);
    v21 = v18;
    if ( v18 )
      memset_0(v18, 0, v17);
    else
      v21 = 0;
    v71 = v21;
    v60 = v21;
    v22 = 0;
    if ( a2[2] )
      v22 = (_DWORD *)a2[2];
    v23 = 0;
    if ( v59 )
    {
      while ( 1 )
      {
        v20 = 96LL * (unsigned int)v23;
        *(_QWORD *)&v21[v20 + 8] = *(_QWORD *)(v20 + a2[4] + 8);
        *(_QWORD *)&v60[v20 + 16] = *(_QWORD *)(a2[4] + v20 + 16);
        *(_DWORD *)&v60[v20 + 24] = *(_DWORD *)(a2[4] + v20 + 24);
        *(_QWORD *)&v60[v20 + 28] = *(unsigned int *)(v20 + a2[4] + 28);
        if ( (*(_BYTE *)(a2[4] + v20 + 32) & 1) != 0 )
        {
          *(_DWORD *)&v60[v20 + 32] |= 1u;
          if ( v22 )
          {
            if ( (v22[2] & 1) != 0 && *(_DWORD *)(v20 + a2[4] + 28) == -1 )
              *(_DWORD *)&v60[v20 + 28] = v22[3];
          }
        }
        v24 = a2[4];
        if ( (*(_BYTE *)(v24 + v20 + 32) & 2) != 0 )
        {
          *(_DWORD *)&v60[v20 + 32] |= 2u;
          v24 = a2[4];
        }
        if ( !v22 || (*(_BYTE *)(v24 + v20 + 32) & 4) != 0 )
        {
          v19 = v60;
          *(_DWORD *)&v60[v20 + 32] = *(_DWORD *)&v60[v20 + 32] & 0xFFFFFFFB
                                    | (*(_BYTE *)(*(_QWORD *)(a1 + 24) + 296LL) >= 0xAu ? 4 : 0);
          v25 = *(_DWORD *)(v20 + a2[4] + 48);
        }
        else
        {
          *(_DWORD *)&v60[v20 + 32] |= 4u;
          v25 = v22[4];
        }
        *(_DWORD *)&v60[v20 + 48] = v25;
        v23 = (unsigned int)(v23 + 1);
        if ( (unsigned int)v23 >= v59 )
          break;
        v21 = v60;
      }
    }
    v26 = 0;
    if ( v22 )
    {
      std::shared_lock<std::shared_mutex>::shared_lock<std::shared_mutex>(&v64, a1 + 1440);
      LODWORD(v70) = _Thrd_id();
      v28 = std::_Uhash_compare<std::thread::id,std::hash<std::thread::id>,std::equal_to<std::thread::id>>::operator()<std::thread::id>(
              v27,
              &v70);
      v29 = *(_QWORD *)(std::_Hash<std::_Umap_traits<std::thread::id,SD3D12SharedResourceCreationArgs *,std::_Uhash_compare<std::thread::id,std::hash<std::thread::id>,std::equal_to<std::thread::id>>,std::allocator<std::pair<std::thread::id const,SD3D12SharedResourceCreationArgs *>>,0>>::_Find_last<std::thread::id>(
                          a1 + 1448,
                          v62,
                          &v70,
                          v28)
                      + 8);
      if ( !v29 )
        v29 = *(_QWORD *)(a1 + 1456);
      if ( v29 != *(_QWORD *)(a1 + 1456) )
        v26 = *(_QWORD *)(v29 + 24);
      if ( v65 )
        Smtx_unlock_shared(v64);
      if ( v26 )
      {
        v30 = *(_QWORD *)(v26 + 312);
        v31 = *(_QWORD *)(v26 + 304);
        if ( v31 == v30 )
        {
          v55 = v26 + 24;
          v56 = 280;
        }
        else
        {
          v32 = (_OWORD *)(v26 + 24);
          *(_DWORD *)(v26 + 200) = v30 - v31 + 104;
          v70 = *(_QWORD *)(v26 + 312) - *(_QWORD *)(v26 + 304) + 280LL;
          v33 = (__int64 *)(v26 + 328);
          std::vector<unsigned char>::_Resize<std::_Value_init_tag>(v26 + 328, v70);
          v34 = *(_OWORD **)(v26 + 328);
          v35 = 2;
          do
          {
            *v34 = *v32;
            v34[1] = v32[1];
            v34[2] = v32[2];
            v34[3] = v32[3];
            v34[4] = v32[4];
            v34[5] = v32[5];
            v34[6] = v32[6];
            v34[7] = v32[7];
            v34 += 8;
            v32 += 8;
            --v35;
          }
          while ( v35 );
          *v34 = *v32;
          *((_QWORD *)v34 + 2) = *((_QWORD *)v32 + 2);
          memcpy_0((void *)(*v33 + 280), *(const void **)(v26 + 304), *(_QWORD *)(v26 + 312) - *(_QWORD *)(v26 + 304));
          v55 = *v33;
          v56 = v70;
        }
        v36 = v61 & 0xFFFFFFE9 | 6;
        v61 = v36;
        if ( *(_DWORD *)(v26 + 64) )
        {
          v36 |= 0x40u;
          v61 = v36;
        }
        if ( *(_DWORD *)(v26 + 68) )
        {
          v36 |= 0x400u;
          v61 = v36;
        }
        if ( *(_DWORD *)(v26 + 72) )
        {
          v36 |= 0x800u;
          v61 = v36;
        }
      }
      else
      {
        v36 = v61;
      }
      v37 = v36 & 0xFFFB7FFF | ((v22[2] & 2) << 14) | ((~*((_BYTE *)v22 + 8) & 4) << 16);
      v61 = v37;
      if ( v22[1] )
      {
        LODWORD(v54) = v22[1];
        v61 = v37 ^ (v37 ^ (v37 >> 1)) & 1;
      }
      else
      {
        v61 = v37 | 1;
      }
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShareBackingStoreWithKMD>::__private_IsEnabled(
                            `wil::Feature<__WilFeatureTraits_Feature_ShareBackingStoreWithKMD>::GetImpl'::`2'::impl,
                            v19,
                            v20,
                            v23)
      && (_BYTE)v69 )
    {
      v61 |= 0x43u;
    }
    v39 = CallAndLogImpl<long (*)(_D3DKMT_CREATEALLOCATION *),_D3DKMT_CREATEALLOCATION *>(
            D3DKMTCreateAllocation2,
            "CreateAllocation2",
            v38,
            &v53);
    v43 = NDXGI::CDevice::NTStatusToHResult(a1, v39, 0);
    if ( v43 < 0 )
    {
      if ( v39 == -1073741816
        && v22
        && v22[1]
        && (unsigned int)CLayeredObject<CCommandAllocator>::AddRef(3221225480LL) == 1 )
      {
        CJournal::RecordJournal(
          v50,
          -1073741816,
          (__int64)"Allocation append failed. Resource handle likely stale.",
          v51,
          0);
      }
    }
    else
    {
      v70 = 0;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShareBackingStoreWithKMD>::__private_IsEnabled(
                              `wil::Feature<__WilFeatureTraits_Feature_ShareBackingStoreWithKMD>::GetImpl'::`2'::impl,
                              v40,
                              v41,
                              v42)
        && (_BYTE)v69 )
      {
        try
        {
          v46 = operator new(0x18u);
          v22 = v46;
          if ( v46 )
          {
            *v46 = 1;
            v46[1] = 0;
            *((_BYTE *)v46 + 8) &= 0xFCu;
            *((_BYTE *)v46 + 8) |= 4u;
            v46[3] = -1;
            *((_QWORD *)v46 + 2) = 2013265920;
          }
          else
          {
            v22 = 0;
          }
        }
        catch ( std::bad_alloc *v66 )
        {
          *(_OWORD *)v62 = 0;
          *(_QWORD *)&v62[16] = 0x100000000LL;
          *(_DWORD *)v62 = v53;
          *(_DWORD *)&v62[4] = v54;
          CallAndLogImpl<long (*)(_D3DKMT_CREATEALLOCATION *),_D3DKMT_CREATEALLOCATION *>(
            D3DKMTDestroyAllocation2,
            "DestroyAllocation2",
            v47,
            v62);
          std::logic_error::logic_error((std::logic_error *)v68, v66);
          throw (std::bad_alloc *)v68;
        }
        v70 = (__int64)v22;
        v69 = 0;
        NDXGI::CSafeKMResourcePtr::~CSafeKMResourcePtr((NDXGI::CSafeKMResourcePtr *)&v69);
        if ( *((_DWORD *)a2 + 7) )
        {
          v22[3] = *(_DWORD *)(a2[4] + 28);
          *((_BYTE *)v22 + 8) = v22[2] & 0xFE | *(_BYTE *)(a2[4] + 32) & 1;
        }
        a2[2] = (__int64)v22;
      }
      for ( k = 0; k < v59; ++k )
      {
        v45 = 96LL * k;
        *(_DWORD *)(v45 + a2[4]) = *(_DWORD *)&v60[v45];
        v44 = a2[4];
        *(_QWORD *)(v45 + v44 + 40) = *(_QWORD *)&v60[v45 + 40];
      }
      if ( v22 )
      {
        v22[5] = *(_DWORD *)a2[4];
        if ( (v61 & 1) != 0 )
        {
          v22[1] = v54;
          _InterlockedAdd(v22, 1u);
          if ( *(_BYTE *)(*(_QWORD *)(a1 + 24) + 296LL) < 0xAu )
          {
            *(_OWORD *)&v62[8] = 0;
            *(_DWORD *)v62 = *(_DWORD *)(a1 + 56);
            *(_DWORD *)&v62[4] = v22[1];
            v63 = (char *)(v22 + 4);
            v49 = CallAndLogImpl<long (*)(_D3DKMT_GETALLOCATIONPRIORITY const *),_D3DKMT_GETALLOCATIONPRIORITY *>(
                    D3DKMTGetAllocationPriority,
                    v44,
                    v45,
                    v62);
            NDXGI::CDevice::NTStatusToHResult(a1, v49, 0);
          }
          if ( v26 && !*(_DWORD *)(v26 + 64) )
            *(_QWORD *)v26 = HIDWORD(v54);
        }
      }
      NDXGI::CSafeKMResourcePtr::~CSafeKMResourcePtr((NDXGI::CSafeKMResourcePtr *)&v70);
    }
    Microsoft::WRL::Details::MakeAllocator<CD3DShaderCacheInstallerFactory>::~MakeAllocator<CD3DShaderCacheInstallerFactory>(&v71);
    result = (unsigned int)v43;
  }
  catch ( _com_error *v67 )
  {
    LODWORD(v69) = *((_DWORD *)v67 + 2);
    return (unsigned int)v69;
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  return result;
}

```

## disassembly

```asm
0x18005c5d0  push    rbx
0x18005c5d2  push    rsi
0x18005c5d3  push    rdi
0x18005c5d4  push    r12
0x18005c5d6  push    r13
0x18005c5d8  push    r14
0x18005c5da  push    r15
0x18005c5dc  sub     rsp, 0E0h
0x18005c5e3  mov     rdi, rdx
0x18005c5e6  mov     r14, rcx
0x18005c5e9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShareBackingStoreWithKMD@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShareBackingStoreWithKMD@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShareBackingStoreWithKMD> `wil::Feature<__WilFeatureTraits_Feature_ShareBackingStoreWithKMD>::GetImpl(void)'::`2'::impl
0x18005c5f0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShareBackingStoreWithKMD@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShareBackingStoreWithKMD>::__private_IsEnabled(void)
0x18005c5f5  test    al, al
0x18005c5f7  jz      loc_18005C765
0x18005c5fd  cmp     dword ptr [rdi+1Ch], 0
0x18005c601  jbe     short loc_18005C615
0x18005c603  mov     rax, [rdi+20h]
0x18005c607  test    byte ptr [rax+20h], 8
0x18005c60b  setnbe  byte ptr [rsp+118h+arg_0]
0x18005c613  jmp     short loc_18005C61D
0x18005c615  mov     byte ptr [rsp+118h+arg_0], 0
0x18005c61d  xor     r12d, r12d
0x18005c620  mov     esi, 80070057h
0x18005c625  mov     r13d, 80070057h
0x18005c62b  lea     r15d, [r12+1]
0x18005c630  mov     ebx, [rdi+1Ch]
0x18005c633  cmp     r12d, ebx
0x18005c636  jnb     loc_18005C81C
0x18005c63c  mov     edx, r12d
0x18005c63f  lea     rbx, [r12+r12*2]
0x18005c643  shl     rbx, 5
0x18005c647  mov     rax, [rdi+20h]
0x18005c64b  mov     ecx, [rbx+rax+20h]
0x18005c64f  mov     rax, [r14+18h]
0x18005c653  cmp     byte ptr [rax+128h], 42h ; 'B'
0x18005c65a  jb      loc_18005C6E6
0x18005c660  test    ecx, 0FFFFFFF0h
0x18005c666  jz      short loc_18005C686
0x18005c668  mov     [rsp+118h+var_F8], 0
0x18005c670  lea     r8, aReservedFlagsG_2; "Reserved flags given to AllocateCb"
0x18005c677  mov     edx, r13d
0x18005c67a  call    ?RecordJournal@CJournal@@QEAAXIPEBD_NW4RecordJournalOptions@@@Z; CJournal::RecordJournal(uint,char const *,bool,RecordJournalOptions)
0x18005c67f  mov     ecx, esi; int
0x18005c681  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18005c686  mov     rax, [rdi+20h]
0x18005c68a  mov     ecx, [rbx+rax+20h]
0x18005c68e  and     ecx, 8
0x18005c691  setnbe  bl
0x18005c694  cmp     qword ptr [rdi+10h], 0
0x18005c699  jz      short loc_18005C6BD
0x18005c69b  test    ecx, ecx
0x18005c69d  jz      short loc_18005C6BD
0x18005c69f  mov     [rsp+118h+var_F8], 0
0x18005c6a7  lea     r8, aAllocatecbHres; "AllocateCB - hResource was non-null whe"...
0x18005c6ae  mov     edx, r13d
0x18005c6b1  call    ?RecordJournal@CJournal@@QEAAXIPEBD_NW4RecordJournalOptions@@@Z; CJournal::RecordJournal(uint,char const *,bool,RecordJournalOptions)
0x18005c6b6  mov     ecx, esi; int
0x18005c6b8  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18005c6bd  cmp     byte ptr [rsp+118h+arg_0], bl
0x18005c6c4  jz      short loc_18005C70C
0x18005c6c6  mov     [rsp+118h+var_F8], 0
0x18005c6ce  lea     r8, aAllocatecbAllA; "AllocateCB - all allocationInfos must h"...
0x18005c6d5  mov     edx, r13d
0x18005c6d8  call    ?RecordJournal@CJournal@@QEAAXIPEBD_NW4RecordJournalOptions@@@Z; CJournal::RecordJournal(uint,char const *,bool,RecordJournalOptions)
0x18005c6dd  mov     ecx, esi; int
0x18005c6df  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18005c6e4  jmp     short loc_18005C70C
0x18005c6e6  test    ecx, 0FFFFFFF8h
0x18005c6ec  jz      short loc_18005C70F
0x18005c6ee  mov     [rsp+118h+var_F8], 0
0x18005c6f6  lea     r8, aReservedFlagsG_2; "Reserved flags given to AllocateCb"
0x18005c6fd  mov     edx, r13d
0x18005c700  call    ?RecordJournal@CJournal@@QEAAXIPEBD_NW4RecordJournalOptions@@@Z; CJournal::RecordJournal(uint,char const *,bool,RecordJournalOptions)
0x18005c705  mov     ecx, esi; int
0x18005c707  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18005c70c  mov     edx, r12d
0x18005c70f  mov     rax, [r14+18h]
0x18005c713  cmp     byte ptr [rax+128h], 0Ah
0x18005c71a  jb      short loc_18005C75D
0x18005c71c  xor     ebx, ebx
0x18005c71e  cmp     ebx, 5
0x18005c721  jnb     short loc_18005C75D
0x18005c723  lea     rcx, [rdx+rdx*2]
0x18005c727  lea     rdx, [rbx+rcx*4]
0x18005c72b  mov     rax, [rdi+20h]
0x18005c72f  cmp     qword ptr [rax+rdx*8+38h], 0
0x18005c735  jz      short loc_18005C755
0x18005c737  mov     [rsp+118h+var_F8], 0
0x18005c73f  lea     r8, aReservedFields; "Reserved fields in D3D12DDI_ALLOCATION_"...
0x18005c746  mov     edx, r13d
0x18005c749  call    ?RecordJournal@CJournal@@QEAAXIPEBD_NW4RecordJournalOptions@@@Z; CJournal::RecordJournal(uint,char const *,bool,RecordJournalOptions)
0x18005c74e  mov     ecx, esi; int
0x18005c750  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18005c755  add     ebx, r15d
0x18005c758  mov     edx, r12d
0x18005c75b  jmp     short loc_18005C71E
0x18005c75d  add     r12d, r15d
0x18005c760  jmp     loc_18005C630
0x18005c765  mov     byte ptr [rsp+118h+arg_0], 0
0x18005c76d  xor     r12d, r12d
0x18005c770  mov     esi, 80070057h
0x18005c775  mov     r13d, 80070057h
0x18005c77b  lea     r15d, [r12+1]
0x18005c780  mov     ebx, [rdi+1Ch]
0x18005c783  cmp     r12d, ebx
0x18005c786  jnb     loc_18005C81C
0x18005c78c  mov     edx, r12d
0x18005c78f  lea     rcx, [r12+r12*2]
0x18005c793  shl     rcx, 5
0x18005c797  mov     rax, [rdi+20h]
0x18005c79b  test    dword ptr [rcx+rax+20h], 0FFFFFFF8h
0x18005c7a3  jz      short loc_18005C7C6
0x18005c7a5  mov     [rsp+118h+var_F8], 0
0x18005c7ad  lea     r8, aReservedFlagsG_2; "Reserved flags given to AllocateCb"
0x18005c7b4  mov     edx, r13d
0x18005c7b7  call    ?RecordJournal@CJournal@@QEAAXIPEBD_NW4RecordJournalOptions@@@Z; CJournal::RecordJournal(uint,char const *,bool,RecordJournalOptions)
0x18005c7bc  mov     ecx, esi; int
0x18005c7be  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18005c7c3  mov     edx, r12d
0x18005c7c6  mov     rax, [r14+18h]
0x18005c7ca  cmp     byte ptr [rax+128h], 0Ah
0x18005c7d1  jb      short loc_18005C814
0x18005c7d3  xor     ebx, ebx
0x18005c7d5  cmp     ebx, 5
0x18005c7d8  jnb     short loc_18005C814
0x18005c7da  lea     rcx, [rdx+rdx*2]
0x18005c7de  lea     rdx, [rbx+rcx*4]
0x18005c7e2  mov     rax, [rdi+20h]
0x18005c7e6  cmp     qword ptr [rax+rdx*8+38h], 0
0x18005c7ec  jz      short loc_18005C80C
0x18005c7ee  mov     [rsp+118h+var_F8], 0
0x18005c7f6  lea     r8, aReservedFields; "Reserved fields in D3D12DDI_ALLOCATION_"...
0x18005c7fd  mov     edx, r13d
0x18005c800  call    ?RecordJournal@CJournal@@QEAAXIPEBD_NW4RecordJournalOptions@@@Z; CJournal::RecordJournal(uint,char const *,bool,RecordJournalOptions)
0x18005c805  mov     ecx, esi; int
0x18005c807  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18005c80c  add     ebx, r15d
0x18005c80f  mov     edx, r12d
0x18005c812  jmp     short loc_18005C7D5
0x18005c814  add     r12d, r15d
0x18005c817  jmp     loc_18005C780
0x18005c81c  xor     edx, edx; Val
0x18005c81e  lea     r8d, [rdx+48h]; Size
0x18005c822  lea     rcx, [rsp+118h+var_E8]; void *
0x18005c827  call    memset_0
0x18005c82c  mov     eax, [r14+38h]
0x18005c830  mov     [rsp+118h+var_E8], eax
0x18005c834  xor     r12d, r12d
0x18005c837  mov     [rsp+118h+var_E4], r12
0x18005c83c  mov     [rsp+118h+var_D8], r12
0x18005c841  mov     [rsp+118h+var_D0], r12d
0x18005c846  mov     rax, [rdi]
0x18005c849  mov     [rsp+118h+var_C8], rax
0x18005c84e  mov     eax, [rdi+8]
0x18005c851  mov     [rsp+118h+var_C0], eax
0x18005c855  mov     [rsp+118h+var_BC], ebx
0x18005c859  mov     [rsp+118h+arg_18], r12
0x18005c861  mov     ecx, ebx
0x18005c863  lea     eax, [r12+60h]
0x18005c868  mul     rcx
0x18005c86b  mov     rbx, rax
0x18005c86e  lea     rax, [r12-1]
0x18005c873  cmovb   rbx, rax
0x18005c877  mov     rcx, rbx; dwBytes
0x18005c87a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005c87f  mov     rsi, rax
0x18005c882  test    rax, rax
0x18005c885  jz      short loc_18005C896
0x18005c887  mov     r8, rbx; Size
0x18005c88a  xor     edx, edx; Val
0x18005c88c  mov     rcx, rax; void *
0x18005c88f  call    memset_0
0x18005c894  jmp     short loc_18005C899
0x18005c896  mov     rsi, r12
0x18005c899  mov     [rsp+118h+arg_18], rsi
0x18005c8a1  mov     [rsp+118h+var_B8], rsi
0x18005c8a6  mov     rbx, r12
0x18005c8a9  cmp     [rdi+10h], r12
0x18005c8ad  cmovnz  rbx, [rdi+10h]
0x18005c8b2  mov     r9d, r12d
0x18005c8b5  cmp     [rsp+118h+var_BC], r12d
0x18005c8ba  jbe     loc_18005C9DA
0x18005c8c0  mov     eax, r9d
0x18005c8c3  lea     r8, [rax+rax*2]
0x18005c8c7  shl     r8, 5
0x18005c8cb  mov     rax, [rdi+20h]
0x18005c8cf  mov     rcx, [r8+rax+8]
0x18005c8d4  mov     [r8+rsi+8], rcx
0x18005c8d9  mov     rax, [rdi+20h]
0x18005c8dd  mov     rcx, [rax+r8+10h]
0x18005c8e2  mov     rax, [rsp+118h+var_B8]
0x18005c8e7  mov     [r8+rax+10h], rcx
0x18005c8ec  mov     rax, [rdi+20h]
0x18005c8f0  mov     ecx, [rax+r8+18h]
0x18005c8f5  mov     rax, [rsp+118h+var_B8]
0x18005c8fa  mov     [r8+rax+18h], ecx
0x18005c8ff  mov     rax, [rdi+20h]
0x18005c903  mov     ecx, [r8+rax+1Ch]
0x18005c908  mov     rax, [rsp+118h+var_B8]
0x18005c90d  mov     [r8+rax+1Ch], ecx
0x18005c912  mov     rax, [rsp+118h+var_B8]
0x18005c917  mov     [r8+rax+20h], r12d
0x18005c91c  mov     rax, [rdi+20h]
0x18005c920  test    [rax+r8+20h], r15b
0x18005c925  jz      short loc_18005C955
0x18005c927  mov     rax, [rsp+118h+var_B8]
0x18005c92c  or      [r8+rax+20h], r15d
0x18005c931  test    rbx, rbx
0x18005c934  jz      short loc_18005C955
0x18005c936  test    [rbx+8], r15b
0x18005c93a  jz      short loc_18005C955
0x18005c93c  mov     rax, [rdi+20h]
0x18005c940  cmp     dword ptr [r8+rax+1Ch], 0FFFFFFFFh
0x18005c946  jnz     short loc_18005C955
0x18005c948  mov     ecx, [rbx+0Ch]
0x18005c94b  mov     rax, [rsp+118h+var_B8]
0x18005c950  mov     [r8+rax+1Ch], ecx
0x18005c955  mov     rax, [rdi+20h]
0x18005c959  test    byte ptr [rax+r8+20h], 2
0x18005c95f  jz      short loc_18005C970
0x18005c961  mov     rax, [rsp+118h+var_B8]
0x18005c966  or      dword ptr [r8+rax+20h], 2
0x18005c96c  mov     rax, [rdi+20h]
0x18005c970  test    rbx, rbx
0x18005c973  jz      short loc_18005C98D
0x18005c975  test    byte ptr [rax+r8+20h], 4
0x18005c97b  jnz     short loc_18005C98D
0x18005c97d  mov     rax, [rsp+118h+var_B8]
0x18005c982  or      dword ptr [r8+rax+20h], 4
0x18005c988  mov     ecx, [rbx+10h]
0x18005c98b  jmp     short loc_18005C9BC
0x18005c98d  mov     rdx, [rsp+118h+var_B8]
0x18005c992  mov     rax, [r14+18h]
0x18005c996  cmp     byte ptr [rax+128h], 0Ah
0x18005c99d  sbb     ecx, ecx
0x18005c99f  not     ecx
0x18005c9a1  and     ecx, 4
0x18005c9a4  mov     eax, [r8+rdx+20h]
0x18005c9a9  and     eax, 0FFFFFFFBh
0x18005c9ac  or      ecx, eax
0x18005c9ae  mov     [r8+rdx+20h], ecx
0x18005c9b3  mov     rax, [rdi+20h]
0x18005c9b7  mov     ecx, [r8+rax+30h]
0x18005c9bc  mov     rax, [rsp+118h+var_B8]
0x18005c9c1  mov     [r8+rax+30h], ecx
0x18005c9c6  add     r9d, r15d
0x18005c9c9  cmp     r9d, [rsp+118h+var_BC]
0x18005c9ce  jnb     short loc_18005C9DA
0x18005c9d0  mov     rsi, [rsp+118h+var_B8]
0x18005c9d5  jmp     loc_18005C8C0
0x18005c9da  mov     rsi, r12
0x18005c9dd  test    rbx, rbx
0x18005c9e0  jz      loc_18005CC08
0x18005c9e6  lea     rdx, [r14+5A0h]
0x18005c9ed  lea     rcx, [rsp+118h+var_78]
0x18005c9f5  call    ??0?$shared_lock@Vshared_mutex@std@@@std@@QEAA@AEAVshared_mutex@1@@Z; std::shared_lock<std::shared_mutex>::shared_lock<std::shared_mutex>(std::shared_mutex &)
0x18005c9fa  lea     r13, [r14+5A8h]
0x18005ca01  call    cs:__imp__Thrd_id
0x18005ca07  mov     dword ptr [rsp+118h+arg_10], eax
0x18005ca0e  lea     rdx, [rsp+118h+arg_10]
0x18005ca16  call    ??$?RVid@thread@std@@@?$_Uhash_compare@Vid@thread@std@@U?$hash@Vid@thread@std@@@3@U?$equal_to@Vid@thread@std@@@3@@std@@QEBA_KAEBVid@thread@1@@Z; std::_Uhash_compare<std::thread::id,std::hash<std::thread::id>,std::equal_to<std::thread::id>>::operator()<std::thread::id>(std::thread::id const &)
0x18005ca1b  mov     r9, rax
0x18005ca1e  lea     r8, [rsp+118h+arg_10]
0x18005ca26  lea     rdx, [rsp+118h+var_98]
0x18005ca2e  mov     rcx, r13
0x18005ca31  call    ??$_Find_last@Vid@thread@std@@@?$_Hash@V?$_Umap_traits@Vid@thread@std@@PEAUSD3D12SharedResourceCreationArgs@@V?$_Uhash_compare@Vid@thread@std@@U?$hash@Vid@thread@std@@@3@U?$equal_to@Vid@thread@std@@@3@@3@V?$allocator@U?$pair@$$CBVid@thread@std@@PEAUSD3D12SharedResourceCreationArgs@@@std@@@3@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBVid@thread@std@@PEAUSD3D12SharedResourceCreationArgs@@@std@@PEAX@std@@@1@AEBVid@thread@1@_K@Z; std::_Hash<std::_Umap_traits<std::thread::id,SD3D12SharedResourceCreationArgs *,std::_Uhash_compare<std::thread::id,std::hash<std::thread::id>,std::equal_to<std::thread::id>>,std::allocator<std::pair<std::thread::id const,SD3D12SharedResourceCreationArgs *>>,0>>::_Find_last<std::thread::id>(std::thread::id const &,unsigned __int64)
0x18005ca36  mov     rcx, [rax+8]
0x18005ca3a  test    rcx, rcx
0x18005ca3d  jnz     short loc_18005CA43
0x18005ca3f  mov     rcx, [r13+8]
0x18005ca43  cmp     rcx, [r14+5B0h]
0x18005ca4a  jz      short loc_18005CA50
0x18005ca4c  mov     rsi, [rcx+18h]
0x18005ca50  cmp     [rsp+118h+var_70], r12b
0x18005ca58  jz      short loc_18005CA67
0x18005ca5a  mov     rcx, [rsp+118h+var_78]; _Smtx_t *
0x18005ca62  call    _Smtx_unlock_shared
0x18005ca67  test    rsi, rsi
0x18005ca6a  jz      loc_18005CBB8
0x18005ca70  mov     rax, [rsi+138h]
0x18005ca77  mov     rcx, [rsi+130h]
0x18005ca7e  cmp     rcx, rax
0x18005ca81  jnz     short loc_18005CA99
0x18005ca83  lea     rax, [rsi+18h]
0x18005ca87  mov     [rsp+118h+var_D8], rax
0x18005ca8c  mov     [rsp+118h+var_D0], 118h
0x18005ca94  jmp     loc_18005CB7F
0x18005ca99  lea     r13, [rsi+18h]
0x18005ca9d  sub     eax, ecx
0x18005ca9f  add     eax, 68h ; 'h'
0x18005caa2  mov     [r13+0B0h], eax
0x18005caa9  mov     rax, [rsi+138h]
0x18005cab0  sub     rax, [rsi+130h]
0x18005cab7  add     rax, 118h
0x18005cabd  mov     [rsp+118h+arg_10], rax
0x18005cac5  lea     r12, [rsi+148h]
0x18005cacc  mov     rdx, rax
0x18005cacf  mov     rcx, r12
0x18005cad2  call    ??$_Resize@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18005cad7  mov     rcx, [r12]
  ... truncated ...
```
