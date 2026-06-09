# Spctl_Pool_CreateVirtualDisk_P0(_SP_SPCTL_PARAMS *)

- ea: `0x18009d8f8`
- end: `0x18009e9a9`
- name: `?Spctl_Pool_CreateVirtualDisk_P0@@YAKPEAU_SP_SPCTL_PARAMS@@@Z`
- size: `4273`
- prototype: `unsigned int __fastcall(struct _SP_SPCTL_PARAMS *)`
- caller_count: `1`
- callee_count: `34`
- tags: `file_ops`

## callers

- `0x18009304c`

## callees

- `0x1800011b0`
- `0x1800015b8`
- `0x180006290`
- `0x1800062e0`
- `0x180006330`
- `0x180006cf4`
- `0x18000714d`
- `0x18000c704`
- `0x18000cdc8`
- `0x18000ce3c`
- `0x180019b50`
- `0x18002602c`
- `0x180029ea0`
- `0x180029ef0`
- `0x180029f60`
- `0x180029fd8`
- `0x18002c6b4`
- `0x180036804`
- `0x180045238`
- `0x180046998`
- `0x18004a390`
- `0x180067a58`
- `0x1800692e8`
- `0x18007ea44`
- `0x18007ed50`
- `0x18007fa28`
- `0x18009d8f8`
- `0x1800ac344`
- `0x1801b4e9c`
- `0x1801b9e74`
- `0x1801baba0`
- `0x1801bb148`
- `0x1801bc8dc`
- `0x1801bc944`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009de28`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009de51`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009de60`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009de73`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009de81`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009de90`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009de28`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009de51`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009de60`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009de73`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009de81`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009de90`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009dc64`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009dc64`

## string_xrefs

- `0x18009d932`: `Spctl_Pool_CreateVirtualDisk_P0`
- `0x18009dc99`: `Spctl_Pool_CreateVirtualDisk_P0`
- `0x18009dcd5`: `Spctl_Pool_CreateVirtualDisk_P0`
- `0x18009ddad`: `Spctl_Pool_CreateVirtualDisk_P0`
- `0x18009dea9`: `Spctl_Pool_CreateVirtualDisk_P0`
- `0x18009e752`: `Spctl_Pool_CreateVirtualDisk_P0`
- `0x18009e7ac`: `Spctl_Pool_CreateVirtualDisk_P0`
- `0x18009e82b`: `Spctl_Pool_CreateVirtualDisk_P0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Spctl_Pool_CreateVirtualDisk_P0(struct _SP_SPCTL_PARAMS *a1, __int64 a2, int a3, int a4)
{
  unsigned int v5; // edi
  struct _SP_SPACE_INFO *v6; // r15
  unsigned int v7; // eax
  unsigned int VirtualDiskErrors; // r13d
  HLOCAL v10; // rbx
  __int64 v11; // rsi
  unsigned int v12; // ecx
  __int64 v13; // rax
  __int64 v14; // rax
  unsigned int v15; // ecx
  __int64 v16; // rax
  unsigned int v17; // ecx
  __int64 v18; // rax
  unsigned int v19; // ecx
  unsigned __int64 v20; // rdx
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // r8
  __int64 v24; // r9
  unsigned int v25; // eax
  int v26; // r8d
  int v27; // r9d
  int v28; // ecx
  char *v29; // rdx
  __int64 v30; // r12
  unsigned int v31; // r12d
  __int64 v32; // rcx
  int v33; // r14d
  __int64 v34; // rbx
  _DWORD *v35; // rax
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // r9
  _DWORD *v39; // rcx
  unsigned int v40; // eax
  unsigned int v41; // eax
  int SpaceTemplate; // eax
  __int64 v43; // rdx
  __int64 v44; // rcx
  __int64 v45; // r8
  unsigned int v46; // r9d
  int v47; // ecx
  int v48; // r8d
  int v49; // r9d
  char v50; // bl
  char v51; // r11
  struct _SP_SPACE_INFO *v52; // r14
  int v53; // eax
  int v54; // ecx
  int v55; // r8d
  __int64 *v56; // rdx
  int v57; // r8d
  int v58; // r9d
  _QWORD *v59; // r12
  __int64 i; // rbx
  void *v61; // rcx
  int v62; // ecx
  int v63; // eax
  __int64 v64; // r15
  __int64 v65; // r12
  __int64 v66; // r10
  int v67; // eax
  unsigned int v68; // edx
  unsigned int v69; // edx
  int v70; // eax
  int v71; // eax
  unsigned int v72; // ecx
  unsigned __int64 v73; // rax
  unsigned __int64 v74; // rbx
  unsigned int v75; // edx
  unsigned int v76; // r8d
  unsigned int v77; // ecx
  __int64 v78; // rax
  int v79; // eax
  char *v80; // rbx
  int TierTemplate; // eax
  __int64 v82; // rdx
  __int64 v83; // rcx
  __int64 v84; // r8
  char v85; // r12
  char v86; // r14
  int v87; // eax
  int v88; // ecx
  int v89; // r8d
  int v90; // eax
  unsigned int v91; // edx
  unsigned int v92; // edx
  int v93; // ecx
  int v94; // ecx
  __int64 v95; // rax
  int v96; // ecx
  __int64 v97; // rax
  int v98; // ecx
  int v99; // ecx
  int v100; // ecx
  int v101; // r8d
  int v102; // r9d
  const unsigned __int16 *v103; // rbx
  int v104; // ecx
  int v105; // r8d
  int v106; // r9d
  __int16 *v107; // rdx
  enum _MI_Result Instance; // eax
  __int64 v109; // rax
  int v110; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v111; // [rsp+48h] [rbp-B8h]
  struct _SP_SPACE_INFO *v112; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v113; // [rsp+58h] [rbp-A8h] BYREF
  int v114; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned __int64 v115[2]; // [rsp+60h] [rbp-A0h] BYREF
  struct CSpCluster *v116; // [rsp+70h] [rbp-90h] BYREF
  HLOCAL v117; // [rsp+78h] [rbp-88h] BYREF
  HLOCAL v118; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 v119; // [rsp+88h] [rbp-78h] BYREF
  int v120; // [rsp+90h] [rbp-70h]
  void *Block; // [rsp+98h] [rbp-68h]
  HLOCAL v122; // [rsp+A0h] [rbp-60h] BYREF
  HLOCAL hMem; // [rsp+A8h] [rbp-58h]
  const char *v124; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v125; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v126; // [rsp+C8h] [rbp-38h]
  __int128 v127; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v128; // [rsp+F0h] [rbp-10h]
  __int16 v129; // [rsp+F8h] [rbp-8h]
  __int64 v130; // [rsp+100h] [rbp+0h]
  __int64 v131; // [rsp+108h] [rbp+8h]
  int v132; // [rsp+110h] [rbp+10h]
  _BYTE v133[64]; // [rsp+114h] [rbp+14h] BYREF
  int v134; // [rsp+154h] [rbp+54h]
  _BYTE v135[24]; // [rsp+160h] [rbp+60h] BYREF
  __int128 v136; // [rsp+178h] [rbp+78h]
  __int128 v137; // [rsp+188h] [rbp+88h]

  v124 = (const char *)a1;
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    v110 = 2172;
    v118 = "Spctl_Pool_CreateVirtualDisk_P0";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (_DWORD)a1,
      (unsigned int)byte_18031CA6B,
      a3,
      a4,
      (__int64)&v118,
      (__int64)&v110);
  }
  v5 = 0;
  v116 = 0;
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v116);
  v116 = 0;
  v127 = 0;
  v128 = 0;
  v129 = 0;
  v130 = 0;
  v131 = 0;
  v132 = 16;
  v134 = 0;
  memset_0(v133, 0, sizeof(v133));
  memset_0(v135, 0, 0x48u);
  v117 = 0;
  v118 = 0;
  v6 = 0;
  v112 = 0;
  v125 = 0;
  v126 = 0;
  v119 = 0;
  LOBYTE(v120) = 0;
  v122 = 0;
  v7 = *((_DWORD *)a1 + 142);
  if ( v7 < 0x18 )
  {
    CSpExtendedStatus::~CSpExtendedStatus((CSpExtendedStatus *)&v127);
    CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v116);
    return 87;
  }
  if ( *((_DWORD *)a1 + 146) >= 0x220u )
  {
    VirtualDiskErrors = 0;
    v10 = 0;
    hMem = 0;
    Block = 0;
    v11 = *((_QWORD *)a1 + 70);
    v111 = *((_QWORD *)a1 + 72);
    v12 = *(_DWORD *)(v11 + 12);
    if ( v7 < v12 )
      goto LABEL_10;
    if ( *(_DWORD *)(v11 + 16) != 2005 )
      goto LABEL_10;
    if ( *(_DWORD *)(v11 + 8) < 0x8Au )
      goto LABEL_10;
    if ( v12 < *(_DWORD *)(v11 + 8) )
      goto LABEL_10;
    v13 = *(unsigned int *)(v11 + 40);
    if ( (_DWORD)v13 )
    {
      if ( (unsigned int)v13 < *(_DWORD *)(v11 + 8)
        || (unsigned int)v13 > v12
        || (v13 & 1) != 0
        || (int)StringCbLengthW((const unsigned __int16 *)(v11 + v13), v12 - (unsigned int)v13, v115) < 0 )
      {
        goto LABEL_10;
      }
    }
    if ( (v14 = *(unsigned int *)(v11 + 32), (_DWORD)v14)
      && ((unsigned int)v14 < *(_DWORD *)(v11 + 8)
       || (v15 = *(_DWORD *)(v11 + 12), (unsigned int)v14 > v15)
       || (v14 & 1) != 0
       || (int)StringCbLengthW((const unsigned __int16 *)(v11 + v14), v15 - (unsigned int)v14, v115) < 0)
      || (v16 = *(unsigned int *)(v11 + 36), (_DWORD)v16)
      && ((unsigned int)v16 < *(_DWORD *)(v11 + 8)
       || (v17 = *(_DWORD *)(v11 + 12), (unsigned int)v16 > v17)
       || (v16 & 1) != 0
       || (int)StringCbLengthW((const unsigned __int16 *)(v11 + v16), v17 - (unsigned int)v16, v115) < 0)
      || (v18 = *(unsigned int *)(v11 + 28), (_DWORD)v18)
      && ((unsigned int)v18 < *(_DWORD *)(v11 + 8)
       || (unsigned int)v18 > *(_DWORD *)(v11 + 12)
       || (v18 & 3) != 0
       || (v19 = v18 + 4, (int)v18 + 4 < (unsigned int)v18)
       || v19 > *(_DWORD *)(v11 + 12)
       || (v20 = 16LL * *(unsigned int *)(v18 + v11), v20 > 0xFFFFFFFF)
       || (unsigned int)v20 + v19 < v19
       || (unsigned int)v20 + v19 > *(_DWORD *)(v11 + 12)) )
    {
LABEL_10:
      v5 = 87;
LABEL_66:
      v30 = v111;
LABEL_67:
      _FillMethodResponse(v30, *((unsigned int *)v124 + 146), VirtualDiskErrors, v122, *((_QWORD *)v124 + 74));
      v59 = Block;
      if ( Block )
      {
        for ( i = 0; (unsigned int)i < *(_DWORD *)(v11 + 44); i = (unsigned int)(i + 1) )
        {
          v61 = (void *)v59[i];
          if ( v61 )
          {
            LocalFree(v61);
            v59[i] = 0;
          }
        }
        operator delete(v59);
      }
      if ( hMem )
        LocalFree(hMem);
      if ( v122 )
        LocalFree(v122);
      if ( v117 )
        LocalFree(v117);
      if ( v6 )
        LocalFree(v6);
      v62 = (int)v118;
      if ( v118 )
        LocalFree(v118);
      if ( (unsigned int)dword_180397B68 > 5 )
      {
        v114 = 3077;
        v124 = "Spctl_Pool_CreateVirtualDisk_P0";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v62,
          (unsigned int)byte_180320BCD,
          v57,
          v58,
          (__int64)&v124,
          (__int64)&v114);
      }
      goto LABEL_85;
    }
    if ( !(unsigned int)SiGetPool((struct _GUID *)((char *)a1 + 4), 2u, (struct _SU_POOL_OBJECT **)&v117) )
    {
      v25 = GleToSmpReturnCode(v22, v21, v23, v24);
      VirtualDiskErrors = v25;
      v28 = dword_180397B68;
      if ( (unsigned int)dword_180397B68 <= 2 )
      {
LABEL_40:
        v30 = v111;
LABEL_41:
        if ( VirtualDiskErrors && VirtualDiskErrors != 46011 && v118 )
          SuDeleteSpace((struct _SU_SPACE_OBJECT *)v118);
        goto LABEL_67;
      }
      v110 = v25;
      v113 = 2380;
      v115[0] = (unsigned __int64)"Spctl_Pool_CreateVirtualDisk_P0";
      v29 = byte_18031AB6B;
LABEL_39:
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v28,
        (_DWORD)v29,
        v26,
        v27,
        (__int64)v115,
        (__int64)&v113,
        (__int64)&v110);
      goto LABEL_40;
    }
    v31 = 0;
    v113 = 0;
    if ( *(_DWORD *)(v11 + 40) )
    {
      v31 = SmpToSpResiliencyType(v11 + *(unsigned int *)(v11 + 40));
      v113 = v31;
    }
    if ( *(_DWORD *)(v11 + 28) )
    {
      if ( *(_DWORD *)(v11 + 8) >= 0xC0u && *(_BYTE *)(v11 + 188) )
        v32 = *(unsigned __int16 *)(v11 + 190);
      else
        v32 = 1;
      v33 = SmpToSpFaultDomainType(v32);
      v34 = *(unsigned int *)(v11 + 28);
      v35 = LocalAlloc(0x40u, 16 * *(_DWORD *)(v34 + v11) + 8);
      v39 = v35;
      hMem = v35;
      if ( !v35 )
      {
        v40 = GleToSmpReturnCode(0, v36, v37, v38);
        VirtualDiskErrors = v40;
        v28 = dword_180397B68;
        if ( (unsigned int)dword_180397B68 <= 2 )
          goto LABEL_40;
        v110 = v40;
        v113 = 2403;
        v115[0] = (unsigned __int64)"Spctl_Pool_CreateVirtualDisk_P0";
        v29 = byte_180319A61;
        goto LABEL_39;
      }
      *v35 = v33;
      v41 = *(_DWORD *)(v34 + v11);
      v39[1] = v41;
      memcpy_0(v39 + 2, (const void *)(v34 + v11 + 4), 16LL * v41);
      v10 = hMem;
    }
    SpaceTemplate = SuGetSpaceTemplate(v117, v21, v31, v10, &v112);
    v46 = 0;
    if ( !SpaceTemplate )
    {
      VirtualDiskErrors = GleToSmpReturnCode(v44, v43, v45, 0);
      if ( (unsigned int)dword_180397B68 > 2 )
      {
        v110 = VirtualDiskErrors;
        v113 = 2419;
        v115[0] = (unsigned __int64)"Spctl_Pool_CreateVirtualDisk_P0";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v47,
          (unsigned int)&word_18031831E,
          v48,
          v49,
          (__int64)v115,
          (__int64)&v113,
          (__int64)&v110);
      }
LABEL_59:
      v6 = v112;
      goto LABEL_40;
    }
    v50 = *(_BYTE *)(v11 + 82);
    v51 = *(_BYTE *)(v11 + 78);
    v52 = v112;
    if ( *(_DWORD *)(v11 + 32) )
    {
      v53 = StringCchCopyW(
              (unsigned __int16 *)v112 + 20,
              0x100u,
              (const unsigned __int16 *)(v11 + *(unsigned int *)(v11 + 32)));
      v46 = 0;
      if ( v53 < 0 )
      {
        VirtualDiskErrors = 5;
        if ( (unsigned int)dword_180397B68 <= 2 )
        {
LABEL_65:
          v6 = v112;
          goto LABEL_66;
        }
        v113 = 2436;
        v56 = (__int64 *)byte_180319593;
LABEL_64:
        v115[0] = (unsigned __int64)"Spctl_Pool_CreateVirtualDisk_P0";
        v110 = 5;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v54,
          (_DWORD)v56,
          v55,
          0,
          (__int64)v115,
          (__int64)&v113,
          (__int64)&v110);
        goto LABEL_65;
      }
    }
    if ( *(_DWORD *)(v11 + 36) )
    {
      v63 = StringCchCopyW(
              (unsigned __int16 *)v52 + 276,
              0x400u,
              (const unsigned __int16 *)(v11 + *(unsigned int *)(v11 + 36)));
      v46 = 0;
      if ( v63 < 0 )
      {
        VirtualDiskErrors = 5;
        if ( (unsigned int)dword_180397B68 <= 2 )
          goto LABEL_65;
        v113 = 2447;
        v56 = qword_180321038;
        goto LABEL_64;
      }
    }
    v64 = 0;
    LODWORD(v65) = 0;
    if ( *(_BYTE *)(v11 + 56) )
      *((_QWORD *)v52 + 333) = *(_QWORD *)(v11 + 64);
    v66 = -1;
    if ( *(_BYTE *)(v11 + 72) && *(_BYTE *)(v11 + 73) )
      *((_QWORD *)v52 + 333) = -1;
    if ( *(_BYTE *)(v11 + 52) )
      *((_DWORD *)v52 + 674) = SmpToSpProvisioningType(*(unsigned __int16 *)(v11 + 54));
    if ( *(_DWORD *)(v11 + 8) >= 0xB0u && *(_BYTE *)(v11 + 160) != (_BYTE)v46 )
      *((_QWORD *)v52 + 338) = *(_QWORD *)(v11 + 168);
    if ( *(_DWORD *)(v11 + 8) >= 0xBCu && *(_BYTE *)(v11 + 184) != (_BYTE)v46 )
      *((_DWORD *)v52 + 678) = SmpToSpMediaType(*(unsigned __int16 *)(v11 + 186));
    if ( *(_BYTE *)(v11 + 112) != (_BYTE)v46 )
    {
      v67 = SmpToSpFaultDomainType(*(unsigned __int16 *)(v11 + 114));
      *((_DWORD *)v52 + 681) = v67;
      if ( v113 == 3 )
        *((_DWORD *)v52 + 679) = v67;
    }
    if ( *(_DWORD *)(v11 + 8) >= 0xB8u && *(_BYTE *)(v11 + 180) != (_BYTE)v46 )
      *((_DWORD *)v52 + 679) = SmpToSpFaultDomainType(*(unsigned __int16 *)(v11 + 182));
    if ( v50 )
    {
      v68 = *(unsigned __int16 *)(v11 + 84);
      if ( !v51 )
      {
        SP_RESILIENCY_INFO::SetFaultTolerance((struct _SP_SPACE_INFO *)((char *)v52 + 2748), v68);
        goto LABEL_117;
      }
      *((_DWORD *)v52 + 688) = v68;
    }
    else if ( !v51 )
    {
      goto LABEL_117;
    }
    v69 = *(unsigned __int16 *)(v11 + 80);
    if ( v50 )
      *((_DWORD *)v52 + 689) = v69;
    else
      SP_RESILIENCY_INFO::SetNumberOfCopies((struct _SP_SPACE_INFO *)((char *)v52 + 2748), v69);
LABEL_117:
    if ( *(_DWORD *)(v11 + 8) >= 0xB4u && *(_BYTE *)(v11 + 176) != (_BYTE)v46 )
    {
      v70 = *(unsigned __int16 *)(v11 + 178);
      if ( (_WORD)v70 == 0xFFFF )
        v70 = -1;
      *((_DWORD *)v52 + 690) = v70;
    }
    if ( *(_BYTE *)(v11 + 86) != (_BYTE)v46 )
    {
      if ( *(_WORD *)(v11 + 88) == 0xFFFF )
        v71 = -1;
      else
        v71 = *(unsigned __int16 *)(v11 + 88);
      *((_DWORD *)v52 + 691) = v71;
    }
    if ( *(_BYTE *)(v11 + 90) != (_BYTE)v46 && *(_BYTE *)(v11 + 91) != (_BYTE)v46 )
      *((_DWORD *)v52 + 691) = -1;
    if ( *(_BYTE *)(v11 + 96) != (_BYTE)v46 )
      *((_DWORD *)v52 + 692) = *(_DWORD *)(v11 + 104);
    if ( *(_DWORD *)(v11 + 8) >= 0xCCu && *(_BYTE *)(v11 + 200) != (_BYTE)v46 )
      *((_DWORD *)v52 + 700) = *(unsigned __int16 *)(v11 + 202);
    if ( *(_BYTE *)(v11 + 120) != (_BYTE)v46 )
      *((_QWORD *)v52 + 347) = *(_QWORD *)(v11 + 128);
    if ( *(_BYTE *)(v11 + 136) != (_BYTE)v46 && *(_BYTE *)(v11 + 137) != (_BYTE)v46 )
      *((_QWORD *)v52 + 347) = v66;
    if ( *(_DWORD *)(v11 + 8) >= 0xE0u && *(_BYTE *)(v11 + 208) != (_BYTE)v46 )
      *((_QWORD *)v52 + 348) = *(_QWORD *)(v11 + 216);
    if ( *(_DWORD *)(v11 + 8) >= 0xA0u && *(_BYTE *)(v11 + 144) != (_BYTE)v46 )
      *((_QWORD *)v52 + 349) = *(_QWORD *)(v11 + 152);
    if ( *(_DWORD *)(v11 + 8) >= 0xE8u && *(_BYTE *)(v11 + 224) != (_BYTE)v46 && *(_DWORD *)(v11 + 228) != v46 )
      *((_WORD *)v52 + 1434) |= 0x20u;
    if ( *(_DWORD *)(v11 + 8) >= 0xC8u && *(_BYTE *)(v11 + 192) != (_BYTE)v46 && *(_DWORD *)(v11 + 196) != v46 )
      *((_QWORD *)v52 + 331) |= 1uLL;
    if ( *(_DWORD *)(v11 + 44) > v46 )
    {
      v65 = *(unsigned int *)(v11 + 48);
      if ( (unsigned int)v65 < *(_DWORD *)(v11 + 8)
        || (v72 = *(_DWORD *)(v11 + 12), (unsigned int)v65 > v72)
        || (v65 & 7) != 0
        || (v73 = 48LL * *(unsigned int *)(v11 + 44), v73 > 0xFFFFFFFF)
        || v72 - (unsigned int)v65 < (unsigned int)v73 )
      {
LABEL_160:
        v5 = 87;
        goto LABEL_65;
      }
      v64 = v11 + v65;
      v74 = 8LL * *(unsigned int *)(v11 + 44);
      if ( !is_mul_ok(*(unsigned int *)(v11 + 44), 8u) )
        v74 = v66;
      Block = operator new[](v74);
      memset_0(Block, 0, v74);
      v46 = 0;
    }
    v75 = v46;
    v110 = v46;
    v76 = *(_DWORD *)(v11 + 44);
    if ( v76 )
    {
      while ( 1 )
      {
        if ( (int)v65 + 48 < (unsigned int)v65 )
          goto LABEL_160;
        if ( (unsigned int)(v65 + 48) > *(_DWORD *)(v11 + 12) )
          goto LABEL_160;
        v77 = *(_DWORD *)(v64 + 12);
        v114 = v77 + v65;
        if ( v77 + (unsigned int)v65 < (unsigned int)v65
          || v77 + (unsigned int)v65 > *(_DWORD *)(v11 + 12)
          || *(_DWORD *)(v64 + 16) != 2006
          || *(_DWORD *)(v64 + 8) < 0x30u
          || v77 < *(_DWORD *)(v64 + 8) )
        {
          goto LABEL_160;
        }
        v78 = *(unsigned int *)(v64 + 44);
        if ( (_DWORD)v78 )
        {
          if ( (unsigned int)v78 < *(_DWORD *)(v64 + 8) )
            goto LABEL_160;
          if ( (unsigned int)v78 > v77 )
            goto LABEL_160;
          if ( (v78 & 1) != 0 )
            goto LABEL_160;
          v79 = StringCbLengthW((const unsigned __int16 *)(v64 + v78), v77 - (unsigned int)v78, v115);
          LOBYTE(v46) = 0;
          if ( v79 < 0 )
            goto LABEL_160;
          v75 = v110;
        }
        if ( *(_BYTE *)(v64 + 48) != (_BYTE)v46 )
          v113 = *(unsigned __int16 *)(v64 + 50);
        v80 = (char *)Block + 8 * v75;
        TierTemplate = SuGetTierTemplate(v117, v113, 0, v80);
        v46 = 0;
        if ( !TierTemplate )
        {
          VirtualDiskErrors = GleToSmpReturnCode(v83, v82, v84, 0);
          if ( (unsigned int)dword_180397B68 > 2 )
          {
            v114 = VirtualDiskErrors;
            v110 = 2735;
            v115[0] = (unsigned __int64)"Spctl_Pool_CreateVirtualDisk_P0";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v100,
              (unsigned int)byte_18031DE75,
              v101,
              v102,
              (__int64)v115,
              (__int64)&v110,
              (__int64)&v114);
          }
          goto LABEL_59;
        }
        if ( *(_DWORD *)(v64 + 8) < 0x50u || (v85 = 1, !*(_BYTE *)(v64 + 76)) )
          v85 = 0;
        if ( *(_DWORD *)(v64 + 8) < 0x64u || (v86 = 1, !*(_BYTE *)(v64 + 96)) )
          v86 = 0;
        if ( *(_DWORD *)(v11 + 32) )
        {
          if ( *(_DWORD *)(v64 + 44) )
          {
            v87 = StringCchPrintfW(
                    (unsigned __int16 *)(*(_QWORD *)v80 + 56LL),
                    0x100u,
                    L"%s-%s",
                    v11 + *(unsigned int *)(v11 + 32),
                    v64 + *(unsigned int *)(v64 + 44));
            v46 = 0;
            if ( v87 < 0 )
            {
              VirtualDiskErrors = 5;
              if ( (unsigned int)dword_180397B68 > 2 )
              {
                v114 = 5;
                v110 = 2763;
                v115[0] = (unsigned __int64)"Spctl_Pool_CreateVirtualDisk_P0";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                  v88,
                  (unsigned int)&byte_18031B38F,
                  v89,
                  0,
                  (__int64)v115,
                  (__int64)&v110,
                  (__int64)&v114);
              }
              goto LABEL_65;
            }
          }
        }
        if ( *(_DWORD *)(v64 + 8) >= 0x68u && *(_BYTE *)(v64 + 100) )
          *(_DWORD *)(*(_QWORD *)v80 + 2616LL) = *(unsigned __int16 *)(v64 + 102);
        if ( *(_BYTE *)(v64 + 24) )
          *(_QWORD *)(*(_QWORD *)v80 + 2624LL) = *(_QWORD *)(v64 + 32);
        if ( *(_DWORD *)(v64 + 8) >= 0x58u && *(_BYTE *)(v64 + 84) )
          *(_DWORD *)(*(_QWORD *)v80 + 2648LL) = SmpToSpProvisioningType(*(unsigned __int16 *)(v64 + 86));
        if ( *(_DWORD *)(v64 + 8) >= 0x78u && *(_BYTE *)(v64 + 104) != (_BYTE)v46 )
          *(_QWORD *)(*(_QWORD *)v80 + 2656LL) = *(_QWORD *)(v64 + 112);
        if ( *(_DWORD *)(v64 + 8) >= 0x5Cu && *(_BYTE *)(v64 + 88) != (_BYTE)v46 )
        {
          v90 = SmpToSpFaultDomainType(*(unsigned __int16 *)(v64 + 90));
          *(_DWORD *)(*(_QWORD *)v80 + 2676LL) = v90;
          if ( v113 == 3 )
            *(_DWORD *)(*(_QWORD *)v80 + 2668LL) = v90;
        }
        if ( *(_DWORD *)(v64 + 8) >= 0x60u && *(_BYTE *)(v64 + 92) != (_BYTE)v46 )
          *(_DWORD *)(*(_QWORD *)v80 + 2668LL) = SmpToSpFaultDomainType(*(unsigned __int16 *)(v64 + 94));
        if ( v85 )
        {
          v91 = *(unsigned __int16 *)(v64 + 78);
          if ( !v86 )
          {
            SP_RESILIENCY_INFO::SetFaultTolerance((SP_RESILIENCY_INFO *)(*(_QWORD *)v80 + 2692LL), v91);
            goto LABEL_216;
          }
          *(_DWORD *)(*(_QWORD *)v80 + 2696LL) = v91;
        }
        else if ( !v86 )
        {
          goto LABEL_216;
        }
        v92 = *(unsigned __int16 *)(v64 + 98);
        if ( v85 )
          *(_DWORD *)(*(_QWORD *)v80 + 2700LL) = v92;
        else
          SP_RESILIENCY_INFO::SetNumberOfCopies((SP_RESILIENCY_INFO *)(*(_QWORD *)v80 + 2692LL), v92);
LABEL_216:
        if ( *(_DWORD *)(v64 + 8) >= 0x54u && *(_BYTE *)(v64 + 80) != (_BYTE)v46 )
        {
          if ( *(_WORD *)(v64 + 82) == 0xFFFF )
            v93 = -1;
          else
            v93 = *(unsigned __int16 *)(v64 + 82);
          *(_DWORD *)(*(_QWORD *)v80 + 2704LL) = v93;
        }
        if ( *(_DWORD *)(v64 + 8) >= 0x4Cu && *(_BYTE *)(v64 + 72) != (_BYTE)v46 )
        {
          if ( *(_WORD *)(v64 + 74) == 0xFFFF )
            v94 = -1;
          else
            v94 = *(unsigned __int16 *)(v64 + 74);
          *(_DWORD *)(*(_QWORD *)v80 + 2708LL) = v94;
        }
        if ( *(_DWORD *)(v64 + 8) >= 0x48u && *(_BYTE *)(v64 + 56) != (_BYTE)v46 )
          *(_DWORD *)(*(_QWORD *)v80 + 2712LL) = *(_DWORD *)(v64 + 64);
        if ( *(_BYTE *)(v64 + 40) != (_BYTE)v46 )
          *(_DWORD *)(*(_QWORD *)v80 + 2664LL) = SmpToSpMediaType(*(unsigned __int16 *)(v64 + 42));
        if ( *((_DWORD *)v117 + 661) > 0xEu )
        {
          if ( *(_BYTE *)(v11 + 52) != (_BYTE)v46 )
            *(_DWORD *)(*(_QWORD *)v80 + 2648LL) = SmpToSpProvisioningType(*(unsigned __int16 *)(v11 + 54));
          if ( *(_DWORD *)(v11 + 8) >= 0xBCu && *(_BYTE *)(v11 + 184) != (_BYTE)v46 )
            *(_DWORD *)(*(_QWORD *)v80 + 2664LL) = SmpToSpMediaType(*(unsigned __int16 *)(v11 + 186));
          if ( *(_DWORD *)(v11 + 8) >= 0xB0u && *(_BYTE *)(v11 + 160) != (_BYTE)v46 )
            *(_QWORD *)(*(_QWORD *)v80 + 2656LL) = *(_QWORD *)(v11 + 168);
          if ( *(_DWORD *)(v11 + 8) >= 0xB8u && *(_BYTE *)(v11 + 180) != (_BYTE)v46 )
            *(_DWORD *)(*(_QWORD *)v80 + 2668LL) = SmpToSpFaultDomainType(*(unsigned __int16 *)(v11 + 182));
          if ( *(_BYTE *)(v11 + 112) != (_BYTE)v46 )
            *(_DWORD *)(*(_QWORD *)v80 + 2676LL) = SmpToSpFaultDomainType(*(unsigned __int16 *)(v11 + 114));
          if ( *(_DWORD *)(v11 + 40) != v46 )
          {
            *(_DWORD *)(*(_QWORD *)v80 + 2692LL) = SmpToSpResiliencyType(v11 + *(unsigned int *)(v11 + 40));
            LOBYTE(v46) = 0;
          }
          if ( *(_BYTE *)(v11 + 82) != (_BYTE)v46 )
          {
            if ( *(_BYTE *)(v11 + 78) == (_BYTE)v46 )
              SP_RESILIENCY_INFO::SetFaultTolerance(
                (SP_RESILIENCY_INFO *)(*(_QWORD *)v80 + 2692LL),
                *(unsigned __int16 *)(v11 + 84));
            else
              *(_DWORD *)(*(_QWORD *)v80 + 2696LL) = *(unsigned __int16 *)(v11 + 84);
          }
          if ( *(_BYTE *)(v11 + 78) != (_BYTE)v46 )
          {
            if ( *(_BYTE *)(v11 + 82) == (_BYTE)v46 )
              SP_RESILIENCY_INFO::SetNumberOfCopies(
                (SP_RESILIENCY_INFO *)(*(_QWORD *)v80 + 2692LL),
                *(unsigned __int16 *)(v11 + 80));
            else
              *(_DWORD *)(*(_QWORD *)v80 + 2700LL) = *(unsigned __int16 *)(v11 + 80);
          }
          if ( *(_DWORD *)(v11 + 8) >= 0xB4u && *(_BYTE *)(v11 + 176) != (_BYTE)v46 )
          {
            if ( *(_WORD *)(v11 + 178) == 0xFFFF )
              v98 = -1;
            else
              v98 = *(unsigned __int16 *)(v11 + 178);
            *(_DWORD *)(*(_QWORD *)v80 + 2704LL) = v98;
          }
          if ( *(_BYTE *)(v11 + 86) != (_BYTE)v46 )
          {
            if ( *(_WORD *)(v11 + 88) == 0xFFFF )
              v99 = -1;
            else
              v99 = *(unsigned __int16 *)(v11 + 88);
            *(_DWORD *)(*(_QWORD *)v80 + 2708LL) = v99;
          }
          if ( *(_BYTE *)(v11 + 90) != (_BYTE)v46 && *(_BYTE *)(v11 + 91) != (_BYTE)v46 )
            *(_DWORD *)(*(_QWORD *)v80 + 2708LL) = -1;
          v52 = v112;
          if ( *(_BYTE *)(v11 + 96) != (_BYTE)v46 )
            *(_DWORD *)(*(_QWORD *)v80 + 2712LL) = *(_DWORD *)(v11 + 104);
        }
        else
        {
          v95 = *(_QWORD *)v80;
          v96 = *(_DWORD *)(*(_QWORD *)v80 + 2664LL);
          v52 = v112;
          *(_OWORD *)(v95 + 2648) = *(_OWORD *)((char *)v112 + 2696);
          *(_OWORD *)(v95 + 2664) = *(_OWORD *)((char *)v52 + 2712);
          *(_DWORD *)(*(_QWORD *)v80 + 2664LL) = v96;
          v97 = *(_QWORD *)v80;
          *(_OWORD *)(v97 + 2692) = *(_OWORD *)((char *)v52 + 2748);
          *(_QWORD *)(v97 + 2708) = *(_QWORD *)((char *)v52 + 2764);
        }
        v75 = v110 + 1;
        v110 = v75;
        v76 = *(_DWORD *)(v11 + 44);
        if ( v75 >= v76 )
          break;
        v64 += *(unsigned int *)(v64 + 12);
        LODWORD(v65) = v114;
      }
    }
    v30 = v111;
    v103 = (const unsigned __int16 *)(v111 + 4);
    if ( !(unsigned int)SuexCreateSpace(
                          (struct _SU_POOL_OBJECT *)v117,
                          v52,
                          v76,
                          (struct _SP_TIER_INFO **const)Block,
                          (unsigned __int16 *const)(v111 + 4),
                          (struct _SU_SPACE_OBJECT **)&v118,
                          (struct _SUEX_EXTENDEDSTATUS_OBJECT **)&v122) )
    {
      VirtualDiskErrors = _TranslateCreateVirtualDiskErrors();
      if ( (unsigned int)dword_180397B68 <= 2 )
      {
LABEL_284:
        v6 = v112;
        goto LABEL_41;
      }
      v110 = 2998;
      v107 = (__int16 *)byte_18031BA8D;
LABEL_283:
      v115[0] = (unsigned __int64)"Spctl_Pool_CreateVirtualDisk_P0";
      v114 = VirtualDiskErrors;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v104,
        (_DWORD)v107,
        v105,
        v106,
        (__int64)v115,
        (__int64)&v110,
        (__int64)&v114);
      goto LABEL_284;
    }
    if ( *(_BYTE *)(v11 + 24) )
    {
      SuexParseIdLite(v103, (struct _SUEX_ID *)v135);
      v125 = v137;
      v126 = v136;
      VirtualDiskErrors = InitializeDiskForSpace(&v125, 0);
      if ( VirtualDiskErrors == 8 )
      {
        if ( (unsigned int)CSpExtendedStatus::Initialize((CSpExtendedStatus *)&v127, 0x8024u, 0) )
          CSpExtendedStatus::ToSuexExtendedStatus(
            (CSpExtendedStatus *)&v127,
            (struct _SUEX_EXTENDEDSTATUS_OBJECT **)&v122);
        goto LABEL_290;
      }
      if ( VirtualDiskErrors )
      {
LABEL_290:
        if ( (unsigned int)dword_180397B68 <= 2 )
          goto LABEL_284;
        v110 = 3024;
        v107 = word_18031BD4A;
        goto LABEL_283;
      }
      CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v116);
      Instance = CSpCluster::GetInstance(&v116);
      if ( Instance )
      {
        LODWORD(v119) = Instance | 0x85200000;
        VirtualDiskErrors = _status_t::ToSMRC(&v119);
        if ( (unsigned int)dword_180397B68 <= 2 )
          goto LABEL_284;
        v110 = 3032;
        v107 = &word_18032112E;
        goto LABEL_283;
      }
      v109 = CSpCluster::AddSpaceToCluster(v116, v115, &v125, v52, 0);
      v119 = *(_QWORD *)v109;
      v120 = *(_DWORD *)(v109 + 8);
      if ( _mm_cvtsi128_si32((__m128i)v119) < 0 )
      {
        VirtualDiskErrors = _status_t::ToSMRC(&v119);
        if ( (unsigned int)dword_180397B68 <= 2 )
          goto LABEL_284;
        v110 = 3042;
        v107 = (__int16 *)byte_18031D821;
        goto LABEL_283;
      }
    }
    v6 = v112;
    goto LABEL_67;
  }
  **((_DWORD **)a1 + 74) = 544;
  v5 = 87;
LABEL_85:
  CSpExtendedStatus::~CSpExtendedStatus((CSpExtendedStatus *)&v127);
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(&v116);
  return v5;
}

```

## disassembly

```asm
0x18009d8f8  push    rbp
0x18009d8fa  push    rbx
0x18009d8fb  push    rsi
0x18009d8fc  push    rdi
0x18009d8fd  push    r12
0x18009d8ff  push    r13
0x18009d901  push    r14
0x18009d903  push    r15
0x18009d905  lea     rbp, [rsp-0C8h]
0x18009d90d  sub     rsp, 1C8h
0x18009d914  mov     rax, cs:__security_cookie
0x18009d91b  xor     rax, rsp
0x18009d91e  mov     [rbp+100h+var_50], rax
0x18009d925  mov     r12, rcx
0x18009d928  mov     [rbp+100h+var_150], rcx
0x18009d92c  mov     eax, cs:dword_180397B68
0x18009d932  lea     r14, aSpctlPoolCreat_3; "Spctl_Pool_CreateVirtualDisk_P0"
0x18009d939  cmp     eax, 5
0x18009d93c  jbe     short loc_18009D969
0x18009d93e  mov     [rsp+200h+var_1C0], 87Ch
0x18009d946  mov     [rbp+100h+var_180], r14
0x18009d94a  lea     rax, [rsp+200h+var_1C0]
0x18009d94f  mov     [rsp+200h+var_1D8], rax
0x18009d954  lea     rax, [rbp+100h+var_180]
0x18009d958  mov     [rsp+200h+var_1E0], rax
0x18009d95d  lea     rdx, byte_18031CA6B
0x18009d964  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18009d969  xor     edi, edi
0x18009d96b  mov     [rsp+200h+var_190], rdi
0x18009d970  lea     rcx, [rsp+200h+var_190]
0x18009d975  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18009d97a  mov     [rsp+200h+var_190], rdi
0x18009d97f  xorps   xmm0, xmm0
0x18009d982  movups  [rbp+100h+var_120], xmm0
0x18009d986  mov     [rbp+100h+var_110], rdi
0x18009d98a  mov     [rbp+100h+var_108], di
0x18009d98e  mov     [rbp+100h+var_100], rdi
0x18009d992  mov     [rbp+100h+var_F8], rdi
0x18009d996  mov     [rbp+100h+var_F0], 10h
0x18009d99d  mov     [rbp+100h+var_AC], edi
0x18009d9a0  xor     edx, edx; Val
0x18009d9a2  lea     r8d, [rdi+40h]; Size
0x18009d9a6  lea     rcx, [rbp+100h+var_EC]; void *
0x18009d9aa  call    memset_0
0x18009d9af  nop
0x18009d9b0  xor     edx, edx; Val
0x18009d9b2  lea     r8d, [rdi+48h]; Size
0x18009d9b6  lea     rcx, [rbp+100h+var_A0]; void *
0x18009d9ba  call    memset_0
0x18009d9bf  mov     [rsp+200h+var_188], rdi
0x18009d9c4  mov     [rbp+100h+var_180], rdi
0x18009d9c8  mov     r15d, edi
0x18009d9cb  mov     [rsp+200h+var_1B0], rdi
0x18009d9d0  xorps   xmm0, xmm0
0x18009d9d3  movups  [rbp+100h+var_148], xmm0
0x18009d9d7  movups  [rbp+100h+var_138], xmm0
0x18009d9db  mov     [rbp+100h+var_178], rdi
0x18009d9df  mov     byte ptr [rbp+100h+var_170], dil
0x18009d9e3  mov     [rbp+100h+var_160], rdi
0x18009d9e7  mov     eax, [r12+238h]
0x18009d9ef  cmp     eax, 18h
0x18009d9f2  jnb     short loc_18009DA10
0x18009d9f4  lea     rcx, [rbp+100h+var_120]; this
0x18009d9f8  call    ??1CSpExtendedStatus@@QEAA@XZ; CSpExtendedStatus::~CSpExtendedStatus(void)
0x18009d9fd  nop
0x18009d9fe  lea     rcx, [rsp+200h+var_190]
0x18009da03  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x18009da08  lea     eax, [rdi+57h]
0x18009da0b  jmp     loc_18009DEEA
0x18009da10  mov     ecx, 220h
0x18009da15  cmp     [r12+248h], ecx
0x18009da1d  jnb     short loc_18009DA33
0x18009da1f  mov     rax, [r12+250h]
0x18009da27  mov     [rax], ecx
0x18009da29  mov     edi, 57h ; 'W'
0x18009da2e  jmp     loc_18009DED4
0x18009da33  mov     r13d, edi
0x18009da36  mov     rbx, rdi
0x18009da39  mov     [rbp+100h+hMem], rbx
0x18009da3d  mov     [rbp+100h+Block], rdi
0x18009da41  mov     rsi, [r12+230h]
0x18009da49  mov     rcx, [r12+240h]
0x18009da51  mov     [rsp+200h+var_1B8], rcx
0x18009da56  mov     ecx, [rsi+0Ch]
0x18009da59  cmp     eax, ecx
0x18009da5b  jb      short loc_18009DA6F
0x18009da5d  cmp     dword ptr [rsi+10h], 7D5h
0x18009da64  jnz     short loc_18009DA6F
0x18009da66  cmp     dword ptr [rsi+8], 8Ah
0x18009da6d  jnb     short loc_18009DA79
0x18009da6f  mov     edi, 57h ; 'W'
0x18009da74  jmp     loc_18009DDE5
0x18009da79  cmp     ecx, [rsi+8]
0x18009da7c  jb      short loc_18009DA6F
0x18009da7e  mov     eax, [rsi+28h]
0x18009da81  test    eax, eax
0x18009da83  jz      short loc_18009DAA8
0x18009da85  cmp     eax, [rsi+8]
0x18009da88  jb      short loc_18009DA6F
0x18009da8a  cmp     eax, ecx
0x18009da8c  ja      short loc_18009DA6F
0x18009da8e  test    al, 1
0x18009da90  jnz     short loc_18009DA6F
0x18009da92  sub     ecx, eax
0x18009da94  mov     edx, ecx; unsigned __int64
0x18009da96  lea     rcx, [rsi+rax]; unsigned __int16 *
0x18009da9a  lea     r8, [rsp+200h+var_1A0]; unsigned __int64 *
0x18009da9f  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18009daa4  test    eax, eax
0x18009daa6  js      short loc_18009DA6F
0x18009daa8  mov     eax, [rsi+20h]
0x18009daab  test    eax, eax
0x18009daad  jz      short loc_18009DAD5
0x18009daaf  cmp     eax, [rsi+8]
0x18009dab2  jb      short loc_18009DA6F
0x18009dab4  mov     ecx, [rsi+0Ch]
0x18009dab7  cmp     eax, ecx
0x18009dab9  ja      short loc_18009DA6F
0x18009dabb  test    al, 1
0x18009dabd  jnz     short loc_18009DA6F
0x18009dabf  sub     ecx, eax
0x18009dac1  mov     edx, ecx; unsigned __int64
0x18009dac3  lea     rcx, [rsi+rax]; unsigned __int16 *
0x18009dac7  lea     r8, [rsp+200h+var_1A0]; unsigned __int64 *
0x18009dacc  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18009dad1  test    eax, eax
0x18009dad3  js      short loc_18009DA6F
0x18009dad5  mov     eax, [rsi+24h]
0x18009dad8  test    eax, eax
0x18009dada  jz      short loc_18009DB06
0x18009dadc  cmp     eax, [rsi+8]
0x18009dadf  jb      short loc_18009DA6F
0x18009dae1  mov     ecx, [rsi+0Ch]
0x18009dae4  cmp     eax, ecx
0x18009dae6  ja      short loc_18009DA6F
0x18009dae8  test    al, 1
0x18009daea  jnz     short loc_18009DA6F
0x18009daec  sub     ecx, eax
0x18009daee  mov     edx, ecx; unsigned __int64
0x18009daf0  lea     rcx, [rsi+rax]; unsigned __int16 *
0x18009daf4  lea     r8, [rsp+200h+var_1A0]; unsigned __int64 *
0x18009daf9  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18009dafe  test    eax, eax
0x18009db00  js      loc_18009DA6F
0x18009db06  mov     eax, [rsi+1Ch]
0x18009db09  mov     r8d, 0FFFFFFFFh
0x18009db0f  test    eax, eax
0x18009db11  jz      short loc_18009DB65
0x18009db13  cmp     eax, [rsi+8]
0x18009db16  jb      loc_18009DA6F
0x18009db1c  cmp     eax, [rsi+0Ch]
0x18009db1f  ja      loc_18009DA6F
0x18009db25  test    al, 3
0x18009db27  jnz     loc_18009DA6F
0x18009db2d  lea     ecx, [rax+4]
0x18009db30  cmp     ecx, eax
0x18009db32  jb      loc_18009DA6F
0x18009db38  cmp     ecx, [rsi+0Ch]
0x18009db3b  ja      loc_18009DA6F
0x18009db41  mov     edx, [rax+rsi]
0x18009db44  shl     rdx, 4
0x18009db48  cmp     rdx, r8
0x18009db4b  ja      loc_18009DA6F
0x18009db51  lea     eax, [rdx+rcx]
0x18009db54  cmp     eax, ecx
0x18009db56  jb      loc_18009DA6F
0x18009db5c  cmp     eax, [rsi+0Ch]
0x18009db5f  ja      loc_18009DA6F
0x18009db65  lea     rcx, [r12+4]; struct _GUID *
0x18009db6a  lea     r8, [rsp+200h+var_188]; struct _SU_POOL_OBJECT **
0x18009db6f  mov     edx, 2; unsigned int
0x18009db74  call    ?SiGetPool@@YAHPEAU_GUID@@KPEAPEAU_SU_POOL_OBJECT@@@Z; SiGetPool(_GUID *,ulong,_SU_POOL_OBJECT * *)
0x18009db79  test    eax, eax
0x18009db7b  jnz     loc_18009DC01
0x18009db81  call    ?GleToSmpReturnCode@@YA?AW4SM_RETURN_CODE@@XZ; GleToSmpReturnCode(void)
0x18009db86  mov     r13d, eax
0x18009db89  mov     ecx, cs:dword_180397B68
0x18009db8f  cmp     ecx, 2
0x18009db92  jbe     short loc_18009DBCF
0x18009db94  mov     [rsp+200h+var_1C0], eax
0x18009db98  mov     [rsp+200h+var_1A8], 94Ch
0x18009dba0  mov     [rsp+200h+var_1A0], r14
0x18009dba5  lea     rdx, byte_18031AB6B
0x18009dbac  lea     rax, [rsp+200h+var_1C0]
0x18009dbb1  mov     [rsp+200h+var_1D0], rax
0x18009dbb6  lea     rax, [rsp+200h+var_1A8]
0x18009dbbb  mov     [rsp+200h+var_1D8], rax
0x18009dbc0  lea     rax, [rsp+200h+var_1A0]
0x18009dbc5  mov     [rsp+200h+var_1E0], rax
0x18009dbca  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18009dbcf  mov     r12, [rsp+200h+var_1B8]
0x18009dbd4  test    r13d, r13d
0x18009dbd7  jz      loc_18009DDEA
0x18009dbdd  cmp     r13d, 0B3BBh
0x18009dbe4  jz      loc_18009DDEA
0x18009dbea  mov     rcx, [rbp+100h+var_180]; struct _SU_SPACE_OBJECT *
0x18009dbee  test    rcx, rcx
0x18009dbf1  jz      loc_18009DDEA
0x18009dbf7  call    ?SuDeleteSpace@@YAHPEAU_SU_SPACE_OBJECT@@@Z; SuDeleteSpace(_SU_SPACE_OBJECT *)
0x18009dbfc  jmp     loc_18009DDEA
0x18009dc01  xor     r12d, r12d
0x18009dc04  mov     [rsp+200h+var_1A8], r12d
0x18009dc09  cmp     [rsi+28h], ebx
0x18009dc0c  jz      short loc_18009DC20
0x18009dc0e  mov     ecx, [rsi+28h]
0x18009dc11  add     rcx, rsi
0x18009dc14  call    ?SmpToSpResiliencyType@@YA?AW4_SP_RESILIENCY_TYPE@@PEBG@Z; SmpToSpResiliencyType(ushort const *)
0x18009dc19  mov     r12d, eax
0x18009dc1c  mov     [rsp+200h+var_1A8], eax
0x18009dc20  cmp     [rsi+1Ch], ebx
0x18009dc23  jz      loc_18009DCDC
0x18009dc29  cmp     dword ptr [rsi+8], 0C0h
0x18009dc30  jb      short loc_18009DC43
0x18009dc32  cmp     [rsi+0BCh], bl
0x18009dc38  jz      short loc_18009DC43
0x18009dc3a  movzx   ecx, word ptr [rsi+0BEh]
0x18009dc41  jmp     short loc_18009DC48
0x18009dc43  mov     ecx, 1
0x18009dc48  call    ?SmpToSpFaultDomainType@@YA?AW4_SC_FD_TYPE@@G@Z; SmpToSpFaultDomainType(ushort)
0x18009dc4d  mov     r14d, eax
0x18009dc50  mov     ebx, [rsi+1Ch]
0x18009dc53  mov     edx, [rbx+rsi]
0x18009dc56  shl     edx, 4
0x18009dc59  add     edx, 8
0x18009dc5c  movsxd  rdx, edx; uBytes
0x18009dc5f  mov     ecx, 40h ; '@'; uFlags
0x18009dc64  call    cs:__imp_LocalAlloc
0x18009dc6a  mov     rcx, rax
0x18009dc6d  mov     [rbp+100h+hMem], rax
0x18009dc71  test    rax, rax
0x18009dc74  jnz     short loc_18009DCB1
0x18009dc76  call    ?GleToSmpReturnCode@@YA?AW4SM_RETURN_CODE@@XZ; GleToSmpReturnCode(void)
0x18009dc7b  mov     r13d, eax
0x18009dc7e  mov     ecx, cs:dword_180397B68
0x18009dc84  cmp     ecx, 2
0x18009dc87  jbe     loc_18009DBCF
0x18009dc8d  mov     [rsp+200h+var_1C0], eax
0x18009dc91  mov     [rsp+200h+var_1A8], 963h
0x18009dc99  lea     rax, aSpctlPoolCreat_3; "Spctl_Pool_CreateVirtualDisk_P0"
0x18009dca0  mov     [rsp+200h+var_1A0], rax
0x18009dca5  lea     rdx, byte_180319A61
0x18009dcac  jmp     loc_18009DBAC
0x18009dcb1  mov     [rax], r14d
0x18009dcb4  mov     eax, [rbx+rsi]
0x18009dcb7  mov     [rcx+4], eax
0x18009dcba  mov     r8d, eax
0x18009dcbd  shl     r8, 4; Size
0x18009dcc1  lea     rdx, [rsi+4]
0x18009dcc5  add     rdx, rbx; Src
0x18009dcc8  add     rcx, 8; void *
0x18009dccc  call    memcpy_0
0x18009dcd1  mov     rbx, [rbp+100h+hMem]
0x18009dcd5  lea     r14, aSpctlPoolCreat_3; "Spctl_Pool_CreateVirtualDisk_P0"
0x18009dcdc  lea     rax, [rsp+200h+var_1B0]
0x18009dce1  mov     [rsp+200h+var_1E0], rax
0x18009dce6  mov     r9, rbx
0x18009dce9  mov     r8d, r12d
0x18009dcec  mov     rcx, [rsp+200h+var_188]
0x18009dcf1  call    ?SuGetSpaceTemplate@@YAHPEAU_SU_POOL_OBJECT@@W4_SC_SPACE_USAGE@@W4_SP_RESILIENCY_TYPE@@PEAU_SP_FD_IDS@@PEAPEAU_SP_SPACE_INFO@@@Z; SuGetSpaceTemplate(_SU_POOL_OBJECT *,_SC_SPACE_USAGE,_SP_RESILIENCY_TYPE,_SP_FD_IDS *,_SP_SPACE_INFO * *)
0x18009dcf6  xor     r9d, r9d
0x18009dcf9  test    eax, eax
0x18009dcfb  jnz     short loc_18009DD56
0x18009dcfd  call    ?GleToSmpReturnCode@@YA?AW4SM_RETURN_CODE@@XZ; GleToSmpReturnCode(void)
0x18009dd02  mov     r13d, eax
0x18009dd05  mov     eax, cs:dword_180397B68
0x18009dd0b  cmp     eax, 2
0x18009dd0e  jbe     short loc_18009DD4C
0x18009dd10  mov     [rsp+200h+var_1C0], r13d
0x18009dd15  mov     [rsp+200h+var_1A8], 973h
0x18009dd1d  mov     [rsp+200h+var_1A0], r14
0x18009dd22  lea     rax, [rsp+200h+var_1C0]
0x18009dd27  mov     [rsp+200h+var_1D0], rax
0x18009dd2c  lea     rax, [rsp+200h+var_1A8]
0x18009dd31  lea     rdx, word_18031831E
0x18009dd38  mov     [rsp+200h+var_1D8], rax
0x18009dd3d  lea     rax, [rsp+200h+var_1A0]
0x18009dd42  mov     [rsp+200h+var_1E0], rax
0x18009dd47  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18009dd4c  mov     r15, [rsp+200h+var_1B0]
0x18009dd51  jmp     loc_18009DBCF
0x18009dd56  mov     bl, [rsi+52h]
0x18009dd59  mov     r11b, [rsi+4Eh]
0x18009dd5d  mov     r14, [rsp+200h+var_1B0]
0x18009dd62  cmp     [rsi+20h], r9d
0x18009dd66  jz      loc_18009DF0D
0x18009dd6c  mov     r8d, [rsi+20h]
0x18009dd70  add     r8, rsi; unsigned __int16 *
0x18009dd73  lea     rcx, [r14+28h]; unsigned __int16 *
0x18009dd77  mov     edx, 100h; unsigned __int64
0x18009dd7c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18009dd81  xor     r9d, r9d
0x18009dd84  test    eax, eax
0x18009dd86  jns     loc_18009DF0D
0x18009dd8c  lea     ebx, [r9+5]
0x18009dd90  mov     r13d, ebx
0x18009dd93  mov     eax, cs:dword_180397B68
0x18009dd99  cmp     eax, 2
0x18009dd9c  jbe     short loc_18009DDE0
0x18009dd9e  mov     [rsp+200h+var_1A8], 984h
0x18009dda6  lea     rdx, byte_180319593
  ... truncated ...
```
