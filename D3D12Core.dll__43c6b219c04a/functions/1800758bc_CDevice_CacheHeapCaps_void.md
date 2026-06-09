# CDevice::CacheHeapCaps(void)

- ea: `0x1800758bc`
- end: `0x180076115`
- name: `?CacheHeapCaps@CDevice@@QEAAXXZ`
- size: `2137`
- prototype: `void __fastcall(CDevice *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18006f4a0`

## callees

- `0x180004a38`
- `0x180007f20`
- `0x18000b010`
- `0x180057ce8`
- `0x180067c30`
- `0x1800758bc`
- `0x18007e018`
- `0x18007efa0`
- `0x1800bb480`
- `0x180262020`

## import_xrefs

- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-0!__imp_D3DKMTQueryAdapterInfo` at `0x1800759f1`

## string_xrefs

- `0x180075b7e`: `Driver set pfnCalcPrivateOpenedHeapAndResourceSizes to NULL.\n`
- `0x180075bbb`: `Driver set pfnOpenHeapAndResource to NULL.\n`
- `0x180075a82`: `Driver set D3D12DDICAPS_MEMORY_ARCHITECTURE::IOCoherent FALSE on an x86 or amd64 system.PCIe support IOCoherence, and the hardware must use it. UMA systems must set TRUE, to avoid the runtimeflushing the CPU cache manually.\n`
- `0x180075aa9`: `Driver set D3D12DDICAPS_MEMORY_ARCHITECTURE::CacheCoherent TRUE along with D3D12DDICAPS_MEMORY_ARCHITECTURE::UMA FALSE. CacheCoherent is only a property of UMA systems, which don'tbenefit from the usage of write-combine.\n`
- `0x180075cc2`: `Driver set pfnCreateHeapAndResource to NULL.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CDevice::CacheHeapCaps(CDevice *this)
{
  __int64 v2; // r15
  __int64 v3; // r13
  int TextureLayoutCaps; // eax
  CJournal *v5; // rcx
  __int64 v6; // r9
  int v7; // eax
  int v8; // eax
  bool v9; // al
  unsigned int v10; // eax
  int v11; // eax
  CJournal *v12; // rcx
  __int64 v13; // r9
  unsigned int v14; // edi
  VersionedDeviceData *v15; // r14
  char *v16; // r12
  __int64 v17; // rsi
  int MemoryArchitectureCaps; // eax
  __int64 v19; // r9
  CJournal *v20; // rcx
  __int64 v21; // r9
  CJournal *v22; // rcx
  __int64 v23; // r9
  CJournal *v24; // rcx
  __int64 v25; // r9
  CJournal *v26; // rcx
  __int64 v27; // r9
  CJournal *v28; // rcx
  __int64 v29; // r9
  CJournal *v30; // rcx
  __int64 v31; // r9
  CJournal *v32; // rcx
  __int64 v33; // r9
  CJournal *v34; // rcx
  __int64 v35; // r9
  CJournal *v36; // rcx
  __int64 v37; // r9
  CJournal *v38; // rcx
  __int64 v39; // r9
  unsigned int i; // r12d
  char *v41; // r14
  int v42; // eax
  unsigned __int16 v43; // r15
  unsigned int j; // esi
  unsigned __int16 v45; // ax
  CJournal *v46; // rcx
  CJournal *v47; // rcx
  unsigned int v48; // ecx
  int v49; // eax
  int v50; // eax
  int v51; // [rsp+20h] [rbp-79h] BYREF
  __int64 v52; // [rsp+28h] [rbp-71h] BYREF
  __int64 *v53; // [rsp+30h] [rbp-69h]
  __int128 *v54; // [rsp+38h] [rbp-61h]
  __int64 v55; // [rsp+40h] [rbp-59h]
  __int64 v56; // [rsp+48h] [rbp-51h] BYREF
  unsigned int v57; // [rsp+50h] [rbp-49h] BYREF
  int v58; // [rsp+54h] [rbp-45h] BYREF
  __int64 v59; // [rsp+60h] [rbp-39h]
  __int64 v60; // [rsp+68h] [rbp-31h]
  __int128 v61; // [rsp+70h] [rbp-29h] BYREF
  int v62; // [rsp+80h] [rbp-19h]
  __int128 v63; // [rsp+88h] [rbp-11h] BYREF
  __int64 v64; // [rsp+98h] [rbp-1h]

  v2 = *(_QWORD *)(*((_QWORD *)this + 95) + 40LL);
  v59 = v2;
  v3 = (__int64)(*((_QWORD *)this + 704) - *((_QWORD *)this + 703)) >> 2;
  *((_BYTE *)this + 1484) = v3;
  if ( *((int *)this + 76) >= 37120 )
  {
    v61 = 0;
    v62 = 0;
    TextureLayoutCaps = CDevice::VersionedGetTextureLayoutCaps(this, (struct D3D12DDI_TEXTURE_LAYOUT_CAPS_0026 *)&v61);
    ThrowFailure(TextureLayoutCaps);
    v7 = v61;
    if ( (unsigned int)v61 > 0xFFFFFEFF )
    {
      CJournal::ReportDriverError(
        v5,
        -2005270496,
        "Driver set D3D12DDICAPS_TEXTURE_LAYOUT::DeviceDependentLayoutCount too large.\n",
        v6);
      ThrowFailure(-2005270496);
      v7 = v61;
    }
    *((_DWORD *)this + 689) = v7;
    v8 = DWORD1(v61);
    if ( DWORD1(v61) > 0xFFFFFEFF )
    {
      CJournal::ReportDriverError(
        v5,
        -2005270496,
        "Driver set D3D12DDICAPS_TEXTURE_LAYOUT::DeviceDependentSwizzleCount too large.\n",
        v6);
      ThrowFailure(-2005270496);
      v8 = DWORD1(v61);
    }
    *((_DWORD *)this + 690) = v8;
    *((_BYTE *)this + 1486) = DWORD2(v61) != 0;
    v9 = HIDWORD(v61) != 0;
    *((_BYTE *)this + 1487) = HIDWORD(v61) != 0;
    if ( v9 && *((int *)this + 390) >= 3000 )
    {
      v51 = 0;
      LODWORD(v63) = *(_DWORD *)(v2 + 448);
      DWORD1(v63) = 76;
      *((_QWORD *)&v63 + 1) = &v51;
      v64 = 4;
      v10 = CallAndLogImpl<long (*)(D3DDDI_DESTROYPAGINGQUEUE *),D3DDDI_DESTROYPAGINGQUEUE *>(
              D3DKMTQueryAdapterInfo,
              "QueryAdapterInfo (KMTQAITYPE_CROSSADAPTERRESOURCE_SUPPORT)",
              CLayeredObject<CCommandAllocator>::AddRef,
              &v63);
      v11 = NDXGI::CUMDAdapter::NTStatusToHResult(v10, 1);
      ThrowFailure(v11);
      if ( v51 < 2 )
      {
        CJournal::ReportDriverError(
          v12,
          -2005270496,
          "Driver set D3D12DDICAPS_TEXTURE_LAYOUT::SupportsRowMajorTexture but not DXGK_VIDMMCAPS::CrossAdapterResourceTexture.\n",
          v13);
        ThrowFailure(-2005270496);
      }
    }
    *((_BYTE *)this + 784) = v62 != 0;
  }
  v14 = 0;
  v51 = 0;
  if ( (_DWORD)v3 )
  {
    v15 = (CDevice *)((char *)this + 288);
    v16 = (char *)this + 48;
    do
    {
      v17 = 5LL * v14;
      v60 = v17;
      v61 = 0;
      v62 = 0;
      MemoryArchitectureCaps = CDevice::VersionedGetMemoryArchitectureCaps(
                                 this,
                                 v14,
                                 (struct D3D12DDI_MEMORY_ARCHITECTURE_CAPS_0041 *)&v61);
      ThrowFailure(MemoryArchitectureCaps);
      if ( !DWORD1(v61) )
      {
        CJournal::ReportDriverError(
          0,
          -2005270496,
          "Driver set D3D12DDICAPS_MEMORY_ARCHITECTURE::IOCoherent FALSE on an x86 or amd64 system.PCIe support IOCoheren"
          "ce, and the hardware must use it. UMA systems must set TRUE, to avoid the runtimeflushing the CPU cache manually.\n",
          v19);
        ThrowFailure(-2005270496);
      }
      LODWORD(v61) = (_DWORD)v61
                  || DWORD2(v61)
                  && (CJournal::ReportDriverError(
                        0,
                        -2005270496,
                        "Driver set D3D12DDICAPS_MEMORY_ARCHITECTURE::CacheCoherent TRUE along with D3D12DDICAPS_MEMORY_A"
                        "RCHITECTURE::UMA FALSE. CacheCoherent is only a property of UMA systems, which don'tbenefit from"
                        " the usage of write-combine.\n",
                        v19),
                      ThrowFailure(-2005270496),
                      (_DWORD)v61);
      DWORD2(v61) = DWORD2(v61) != 0;
      if ( !(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 662) + 512LL))(
              *((_QWORD *)this + 662),
              *((_QWORD *)this + 661)) )
      {
        CJournal::ReportDriverError(v20, -2005270496, "Driver set pfnCalcPrivateHeapAndResourceSizes to NULL.\n", v21);
        ThrowFailure(-2005270496);
      }
      if ( !(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 662) + 528LL))(
              *((_QWORD *)this + 662),
              *((_QWORD *)this + 661)) )
      {
        CJournal::ReportDriverError(v22, -2005270496, "Driver set pfnDestroyHeapAndResource to NULL.\n", v23);
        ThrowFailure(-2005270496);
      }
      if ( !(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 662) + 568LL))(
              *((_QWORD *)this + 662),
              *((_QWORD *)this + 661)) )
      {
        CJournal::ReportDriverError(
          v24,
          -2005270496,
          "Driver set pfnCalcPrivateOpenedHeapAndResourceSizes to NULL.\n",
          v25);
        ThrowFailure(-2005270496);
      }
      if ( !(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 662) + 576LL))(
              *((_QWORD *)this + 662),
              *((_QWORD *)this + 661)) )
      {
        CJournal::ReportDriverError(v26, -2005270496, "Driver set pfnOpenHeapAndResource to NULL.\n", v27);
        ThrowFailure(-2005270496);
      }
      v56 = 1;
      v63 = 0;
      LODWORD(v64) = 0;
      v52 = 1003;
      v53 = &v56;
      v54 = &v63;
      v55 = 20;
      if ( (*(int (__fastcall **)(_QWORD, __int64 *))(v2 + 520))(*(_QWORD *)(v2 + 552), &v52) < 0 )
      {
        CJournal::ReportDriverError(
          v28,
          -2005270496,
          "Driver failed D3D12DDICAPS_TEXTURE_LAYOUT or D3D12DDICAPS_TEXTURE_LAYOUT_SETS Caps.\n",
          v29);
        ThrowFailure(-2005270496);
      }
      if ( !(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 662) + 496LL))(
              *((_QWORD *)this + 662),
              *((_QWORD *)this + 661))
        || !(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 662) + 504LL))(
              *((_QWORD *)this + 662),
              *((_QWORD *)this + 661)) )
      {
        CJournal::ReportDriverError(v30, -2005270496, "Driver must set pfnMapHeap and pfnUnmapHeap to non-NULL.\n", v31);
        ThrowFailure(-2005270496);
      }
      if ( !(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 662) + 520LL))(
              *((_QWORD *)this + 662),
              *((_QWORD *)this + 661)) )
      {
        CJournal::ReportDriverError(v32, -2005270496, "Driver set pfnCreateHeapAndResource to NULL.\n", v33);
        ThrowFailure(-2005270496);
      }
      if ( !(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 662) + 640LL))(
              *((_QWORD *)this + 662),
              *((_QWORD *)this + 661)) )
      {
        CJournal::ReportDriverError(v34, -2005270496, "Driver set pfnCheckResourceAllocationInfo to NULL.\n", v35);
        ThrowFailure(-2005270496);
      }
      if ( !(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 662) + 648LL))(
              *((_QWORD *)this + 662),
              *((_QWORD *)this + 661)) )
      {
        CJournal::ReportDriverError(v36, -2005270496, "Driver set pfnCheckSubresourceInfo to NULL.\n", v37);
        ThrowFailure(-2005270496);
      }
      if ( !(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 662) + 656LL))(
              *((_QWORD *)this + 662),
              *((_QWORD *)this + 661)) )
      {
        CJournal::ReportDriverError(
          v38,
          -2005270496,
          "Driver set pfnCheckExistingResourceAllocationInfo to NULL.\n",
          v39);
        ThrowFailure(-2005270496);
      }
      if ( *((int *)this + 76) >= 37120 )
      {
        for ( i = 0; i < 3; ++i )
        {
          v41 = (char *)this + 16 * i + 4 * i + 2764;
          HIDWORD(v56) = i;
          if ( i
            && (v52 = 1003,
                v53 = &v56,
                v54 = &v63,
                v55 = 20,
                (*(int (__fastcall **)(_QWORD, __int64 *))(v2 + 520))(*(_QWORD *)(v2 + 552), &v52) < 0) )
          {
            *(_OWORD *)v41 = *(_OWORD *)((char *)this + 2764);
            v42 = *((_DWORD *)this + 695);
          }
          else
          {
            if ( !(_WORD)v63 )
            {
              CJournal::ReportDriverError(
                v38,
                -2005270496,
                "Driver set D3D12DDI_ROW_MAJOR_LAYOUT_SUB_CAPS::SubCaps[ 0 ]::MaxElementSize to 0.\n",
                v39);
              ThrowFailure(-2005270496);
            }
            v43 = 0;
            for ( j = 0; j < 2; ++j )
            {
              v45 = *((_WORD *)&v63 + 4 * j);
              *(_WORD *)&v41[8 * j] = v45;
              if ( v43 >= v45 )
                break;
              v43 = v45;
              v46 = (CJournal *)*((unsigned __int16 *)&v63 + 4 * j + 1);
              if ( (((_DWORD)v46 - 1) & (unsigned int)v46) != 0
                || !(_WORD)v46
                || (unsigned __int16)v46 > (unsigned __int16)word_18032B4D2 )
              {
                CJournal::ReportDriverError(
                  v46,
                  -2005270496,
                  "Driver set D3D12DDI_ROW_MAJOR_LAYOUT_SUB_CAPS::SubCaps::BaseOffsetAlignment either too large, 0, or to"
                  " a non-pow2 value.\n",
                  v39);
                ThrowFailure(-2005270496);
              }
              *(_WORD *)&v41[8 * j + 2] = *((_WORD *)&v63 + 4 * j + 1);
              v47 = (CJournal *)*((unsigned __int16 *)&v63 + 4 * j + 2);
              if ( (((_DWORD)v47 - 1) & (unsigned int)v47) != 0
                || !(_WORD)v47
                || (unsigned __int16)v47 > (unsigned __int16)word_18032B4D4 )
              {
                CJournal::ReportDriverError(
                  v47,
                  -2005270496,
                  "Driver set D3D12DDI_ROW_MAJOR_LAYOUT_SUB_CAPS::SubCaps::PitchAlignment either too large, 0, or to a non-pow2 value.\n",
                  v39);
                ThrowFailure(-2005270496);
              }
              *(_WORD *)&v41[8 * j + 4] = *((_WORD *)&v63 + 4 * j + 2);
              v38 = (CJournal *)*((unsigned __int16 *)&v63 + 4 * j + 3);
              if ( (((_DWORD)v38 - 1) & (unsigned int)v38) != 0
                || !(_WORD)v38
                || (unsigned __int16)v38 > (unsigned __int16)word_18032B4D6 )
              {
                CJournal::ReportDriverError(
                  v38,
                  -2005270496,
                  "Driver set D3D12DDI_ROW_MAJOR_LAYOUT_SUB_CAPS::SubCaps::DepthPitchAlignment either too large, 0, or to"
                  " a non-pow2 value.\n",
                  v39);
                ThrowFailure(-2005270496);
              }
              *(_WORD *)&v41[8 * j + 6] = *((_WORD *)&v63 + 4 * j + 3);
            }
            v42 = v64;
            if ( (v64 & 2) != 0 && (v64 & 1) == 0 )
            {
              CJournal::ReportDriverError(
                v38,
                -2005270496,
                "Driver set D3D12DDI_ROW_MAJOR_LAYOUT_CAPS::Flags incorrect. D3D12DDI_ROW_MAJOR_LAYOUT_FLAG_DEPTH_PITCH_4"
                "_8_16_HEIGHT_MULTIPLE must be set along with D3D12DDI_ROW_MAJOR_LAYOUT_FLAG_FLEXIBLE_DEPTH_PITCH.\n",
                v39);
              ThrowFailure(-2005270496);
              v42 = v64;
            }
            v2 = v59;
          }
          *((_DWORD *)v41 + 4) = v42;
        }
        v14 = v51;
        v17 = v60;
        v15 = (CDevice *)((char *)this + 288);
        v16 = (char *)this + 48;
      }
      *((_DWORD *)this + v17 + 198) = v61 != 0;
      *((_DWORD *)this + v17 + 199) = DWORD2(v61) != 0;
      *((_DWORD *)this + v17 + 200) = DWORD1(v61) != 0;
      v57 = v14;
      v58 = 0;
      if ( *((_BYTE *)this + 296) >= 0xAu )
      {
        v52 = 1059;
        v53 = (__int64 *)&v57;
        v54 = (__int128 *)&v58;
        v55 = 4;
        if ( (*(int (__fastcall **)(_QWORD, __int64 *))(v2 + 520))(*(_QWORD *)(v2 + 552), &v52) < 0 )
        {
          CJournal::ReportDriverError(
            v38,
            -2005270496,
            "Driver failed D3D12DDICAPS_TYPE_0022_CPU_PAGE_TABLE_FALSE_POSITIVES Caps.\n",
            v39);
          ThrowFailure(-2005270496);
        }
      }
      if ( (v58 & 0xFFFFFF88) != 0 )
      {
        CJournal::ReportDriverError(
          v38,
          -2005270496,
          "Driver responded with invalid bits to D3D12DDICAPS_TYPE_0022_CPU_PAGE_TABLE_FALSE_POSITIVES Caps.\n",
          v39);
        ThrowFailure(-2005270496);
      }
      v48 = *((_DWORD *)this + 719);
      if ( v48 < 0xD )
      {
        v49 = 7;
        if ( v48 >= 8 )
          v49 = 55;
      }
      else
      {
        v49 = 119;
      }
      *((_DWORD *)this + v17 + 201) = (v49 & v58) == 0;
      if ( HIDWORD(v61) == 1 )
        *((_DWORD *)this + v17 + 202) = 10;
      *((_DWORD *)this + 358) = VersionedDeviceData::TiledResourcesTier(v15);
      *((_DWORD *)this + 359) = *((_DWORD *)this + 95);
      v50 = *((_DWORD *)this + 92);
      if ( v50 > 3 )
        v50 = 3;
      *((_DWORD *)this + 360) = v50;
      *((_QWORD *)this + 182) = this;
      *((_QWORD *)this + 183) = v16;
      *((_QWORD *)this + 184) = (char *)this + 216;
      if ( *((_QWORD *)this + 625) )
        *((_DWORD *)this + 370) |= 1u;
      v51 = ++v14;
    }
    while ( v14 < (unsigned int)v3 );
  }
  *((_DWORD *)this + 394) = *((_BYTE *)this + 296) >= 0x11u;
}

```

## disassembly

```asm
0x1800758bc  push    rbp
0x1800758be  push    rbx
0x1800758bf  push    rsi
0x1800758c0  push    rdi
0x1800758c1  push    r12
0x1800758c3  push    r13
0x1800758c5  push    r14
0x1800758c7  push    r15
0x1800758c9  lea     rbp, [rsp-1Fh]
0x1800758ce  sub     rsp, 0B8h
0x1800758d5  mov     rax, cs:__security_cookie
0x1800758dc  xor     rax, rsp
0x1800758df  mov     [rbp+57h+var_50], rax
0x1800758e3  mov     rbx, rcx
0x1800758e6  mov     rax, [rcx+2F8h]
0x1800758ed  mov     r15, [rax+28h]
0x1800758f1  mov     [rbp+57h+var_90], r15
0x1800758f5  mov     r13, [rcx+1600h]
0x1800758fc  sub     r13, [rcx+15F8h]
0x180075903  sar     r13, 2
0x180075907  mov     [rcx+5CCh], r13b
0x18007590e  mov     edi, 887A0020h
0x180075913  xor     esi, esi
0x180075915  cmp     dword ptr [rcx+130h], 9100h
0x18007591f  jl      loc_180075A37
0x180075925  xorps   xmm0, xmm0
0x180075928  xor     eax, eax
0x18007592a  movups  [rbp+57h+var_80], xmm0
0x18007592e  mov     [rbp+57h+var_70], eax
0x180075931  lea     rdx, [rbp+57h+var_80]; struct D3D12DDI_TEXTURE_LAYOUT_CAPS_0026 *
0x180075935  call    ?VersionedGetTextureLayoutCaps@CDevice@@QEAAJPEAUD3D12DDI_TEXTURE_LAYOUT_CAPS_0026@@@Z; CDevice::VersionedGetTextureLayoutCaps(D3D12DDI_TEXTURE_LAYOUT_CAPS_0026 *)
0x18007593a  mov     ecx, eax; int
0x18007593c  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180075941  mov     eax, dword ptr [rbp+57h+var_80]
0x180075944  mov     r14d, 0FFFFFEFFh
0x18007594a  cmp     eax, r14d
0x18007594d  jbe     short loc_180075967
0x18007594f  lea     r8, aDriverSetD3d12_1; "Driver set D3D12DDICAPS_TEXTURE_LAYOUT:"...
0x180075956  mov     edx, edi; int
0x180075958  call    ?ReportDriverError@CJournal@@QEAAXJPEBD@Z; CJournal::ReportDriverError(long,char const *)
0x18007595d  mov     ecx, edi; int
0x18007595f  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180075964  mov     eax, dword ptr [rbp+57h+var_80]
0x180075967  mov     [rbx+0AC4h], eax
0x18007596d  mov     eax, dword ptr [rbp+57h+var_80+4]
0x180075970  cmp     eax, r14d
0x180075973  jbe     short loc_18007598D
0x180075975  lea     r8, aDriverSetD3d12_4; "Driver set D3D12DDICAPS_TEXTURE_LAYOUT:"...
0x18007597c  mov     edx, edi; int
0x18007597e  call    ?ReportDriverError@CJournal@@QEAAXJPEBD@Z; CJournal::ReportDriverError(long,char const *)
0x180075983  mov     ecx, edi; int
0x180075985  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18007598a  mov     eax, dword ptr [rbp+57h+var_80+4]
0x18007598d  mov     [rbx+0AC8h], eax
0x180075993  cmp     dword ptr [rbp+57h+var_80+8], esi
0x180075996  setnz   al
0x180075999  mov     [rbx+5CEh], al
0x18007599f  cmp     dword ptr [rbp+57h+var_80+0Ch], esi
0x1800759a2  setnz   al
0x1800759a5  mov     [rbx+5CFh], al
0x1800759ab  test    al, al
0x1800759ad  jz      short loc_180075A2B
0x1800759af  cmp     dword ptr [rbx+618h], 0BB8h
0x1800759b9  jl      short loc_180075A2B
0x1800759bb  mov     [rbp+57h+var_D0], esi
0x1800759be  mov     eax, [r15+1C0h]
0x1800759c5  mov     dword ptr [rbp+57h+var_68], eax
0x1800759c8  mov     dword ptr [rbp+57h+var_68+4], 4Ch ; 'L'
0x1800759cf  lea     rax, [rbp+57h+var_D0]
0x1800759d3  mov     qword ptr [rbp+57h+var_68+8], rax
0x1800759d7  mov     [rbp+57h+var_58], 4
0x1800759df  lea     r9, [rbp+57h+var_68]
0x1800759e3  lea     r8, ?AddRef@?$CLayeredObject@VCCommandAllocator@@@@UEAAKXZ; CLayeredObject<CCommandAllocator>::AddRef(void)
0x1800759ea  lea     rdx, aQueryadapterin_8; "QueryAdapterInfo (KMTQAITYPE_CROSSADAPT"...
0x1800759f1  mov     rcx, cs:__imp_D3DKMTQueryAdapterInfo
0x1800759f8  call    ??$CallAndLogImpl@P6AJPEAUD3DDDI_DESTROYPAGINGQUEUE@@@ZPEAU1@@@YAJP6AJPEAUD3DDDI_DESTROYPAGINGQUEUE@@@ZPEBDP6A?AW4RecordStatusFilterResult@@J@Z0@Z; CallAndLogImpl<long (*)(D3DDDI_DESTROYPAGINGQUEUE *),D3DDDI_DESTROYPAGINGQUEUE *>(long (*)(D3DDDI_DESTROYPAGINGQUEUE *),char const *,RecordStatusFilterResult (*)(long),D3DDDI_DESTROYPAGINGQUEUE *)
0x1800759fd  mov     edx, 1
0x180075a02  mov     ecx, eax
0x180075a04  call    ?NTStatusToHResult@CUMDAdapter@NDXGI@@SAJJW4EErrorTranslationBehavior@2@@Z; NDXGI::CUMDAdapter::NTStatusToHResult(long,NDXGI::EErrorTranslationBehavior)
0x180075a09  mov     ecx, eax; int
0x180075a0b  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180075a10  cmp     [rbp+57h+var_D0], 2
0x180075a14  jge     short loc_180075A2B
0x180075a16  lea     r8, aDriverSetD3d12_2; "Driver set D3D12DDICAPS_TEXTURE_LAYOUT:"...
0x180075a1d  mov     edx, edi; int
0x180075a1f  call    ?ReportDriverError@CJournal@@QEAAXJPEBD@Z; CJournal::ReportDriverError(long,char const *)
0x180075a24  mov     ecx, edi; int
0x180075a26  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180075a2b  cmp     [rbp+57h+var_70], esi
0x180075a2e  setnz   al
0x180075a31  mov     [rbx+310h], al
0x180075a37  mov     edi, esi
0x180075a39  mov     [rbp+57h+var_D0], esi
0x180075a3c  test    r13d, r13d
0x180075a3f  jz      loc_1800760E3
0x180075a45  lea     r14, [rbx+120h]
0x180075a4c  lea     r12, [rbx+30h]
0x180075a50  mov     eax, edi
0x180075a52  lea     rsi, [rax+rax*4]
0x180075a56  mov     [rbp+57h+var_88], rsi
0x180075a5a  xorps   xmm0, xmm0
0x180075a5d  xor     eax, eax
0x180075a5f  movups  [rbp+57h+var_80], xmm0
0x180075a63  mov     [rbp+57h+var_70], eax
0x180075a66  lea     r8, [rbp+57h+var_80]; struct D3D12DDI_MEMORY_ARCHITECTURE_CAPS_0041 *
0x180075a6a  mov     edx, edi; unsigned int
0x180075a6c  mov     rcx, rbx; this
0x180075a6f  call    ?VersionedGetMemoryArchitectureCaps@CDevice@@QEAAJIPEAUD3D12DDI_MEMORY_ARCHITECTURE_CAPS_0041@@@Z; CDevice::VersionedGetMemoryArchitectureCaps(uint,D3D12DDI_MEMORY_ARCHITECTURE_CAPS_0041 *)
0x180075a74  mov     ecx, eax; int
0x180075a76  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180075a7b  xor     ecx, ecx; this
0x180075a7d  cmp     dword ptr [rbp+57h+var_80+4], ecx
0x180075a80  jnz     short loc_180075A9F
0x180075a82  lea     r8, aDriverSetD3d12_7; "Driver set D3D12DDICAPS_MEMORY_ARCHITEC"...
0x180075a89  mov     edx, 887A0020h; int
0x180075a8e  call    ?ReportDriverError@CJournal@@QEAAXJPEBD@Z; CJournal::ReportDriverError(long,char const *)
0x180075a93  mov     ecx, 887A0020h; int
0x180075a98  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180075a9d  xor     ecx, ecx; this
0x180075a9f  cmp     dword ptr [rbp+57h+var_80], ecx
0x180075aa2  jnz     short loc_180075AD0
0x180075aa4  cmp     dword ptr [rbp+57h+var_80+8], ecx
0x180075aa7  jz      short loc_180075ACB
0x180075aa9  lea     r8, aDriverSetD3d12_5; "Driver set D3D12DDICAPS_MEMORY_ARCHITEC"...
0x180075ab0  mov     edx, 887A0020h; int
0x180075ab5  call    ?ReportDriverError@CJournal@@QEAAXJPEBD@Z; CJournal::ReportDriverError(long,char const *)
0x180075aba  mov     ecx, 887A0020h; int
0x180075abf  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180075ac4  xor     ecx, ecx
0x180075ac6  cmp     dword ptr [rbp+57h+var_80], ecx
0x180075ac9  jnz     short loc_180075AD0
0x180075acb  mov     dword ptr [rbp+57h+var_80], ecx
0x180075ace  jmp     short loc_180075AD7
0x180075ad0  mov     dword ptr [rbp+57h+var_80], 1
0x180075ad7  mov     eax, ecx
0x180075ad9  cmp     dword ptr [rbp+57h+var_80+8], ecx
0x180075adc  setnz   al
0x180075adf  mov     dword ptr [rbp+57h+var_80+8], eax
0x180075ae2  mov     rcx, [rbx+14B0h]
0x180075ae9  mov     rax, [rcx]
0x180075aec  mov     rdx, [rbx+14A8h]
0x180075af3  mov     rax, [rax+200h]
0x180075afa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075aff  test    rax, rax
0x180075b02  jnz     short loc_180075B1F
0x180075b04  lea     r8, aDriverSetPfnca_0; "Driver set pfnCalcPrivateHeapAndResourc"...
0x180075b0b  mov     edx, 887A0020h; int
0x180075b10  call    ?ReportDriverError@CJournal@@QEAAXJPEBD@Z; CJournal::ReportDriverError(long,char const *)
0x180075b15  mov     ecx, 887A0020h; int
0x180075b1a  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180075b1f  mov     rcx, [rbx+14B0h]
0x180075b26  mov     rax, [rcx]
0x180075b29  mov     rdx, [rbx+14A8h]
0x180075b30  mov     rax, [rax+210h]
0x180075b37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075b3c  test    rax, rax
0x180075b3f  jnz     short loc_180075B5C
0x180075b41  lea     r8, aDriverSetPfnde; "Driver set pfnDestroyHeapAndResource to"...
0x180075b48  mov     edx, 887A0020h; int
0x180075b4d  call    ?ReportDriverError@CJournal@@QEAAXJPEBD@Z; CJournal::ReportDriverError(long,char const *)
0x180075b52  mov     ecx, 887A0020h; int
0x180075b57  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180075b5c  mov     rcx, [rbx+14B0h]
0x180075b63  mov     rax, [rcx]
0x180075b66  mov     rdx, [rbx+14A8h]
0x180075b6d  mov     rax, [rax+238h]
0x180075b74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075b79  test    rax, rax
0x180075b7c  jnz     short loc_180075B99
0x180075b7e  lea     r8, aDriverSetPfnca; "Driver set pfnCalcPrivateOpenedHeapAndR"...
0x180075b85  mov     edx, 887A0020h; int
0x180075b8a  call    ?ReportDriverError@CJournal@@QEAAXJPEBD@Z; CJournal::ReportDriverError(long,char const *)
0x180075b8f  mov     ecx, 887A0020h; int
0x180075b94  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180075b99  mov     rcx, [rbx+14B0h]
0x180075ba0  mov     rax, [rcx]
0x180075ba3  mov     rdx, [rbx+14A8h]
0x180075baa  mov     rax, [rax+240h]
0x180075bb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075bb6  test    rax, rax
0x180075bb9  jnz     short loc_180075BD6
0x180075bbb  lea     r8, aDriverSetPfnop; "Driver set pfnOpenHeapAndResource to NU"...
0x180075bc2  mov     edx, 887A0020h; int
0x180075bc7  call    ?ReportDriverError@CJournal@@QEAAXJPEBD@Z; CJournal::ReportDriverError(long,char const *)
0x180075bcc  mov     ecx, 887A0020h; int
0x180075bd1  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180075bd6  mov     [rbp+57h+var_A8], 1
0x180075bde  xorps   xmm0, xmm0
0x180075be1  xor     eax, eax
0x180075be3  movups  [rbp+57h+var_68], xmm0
0x180075be7  mov     dword ptr [rbp+57h+var_58], eax
0x180075bea  mov     [rbp+57h+var_C8], 3EBh
0x180075bf2  lea     rax, [rbp+57h+var_A8]
0x180075bf6  mov     [rbp+57h+var_C0], rax
0x180075bfa  lea     rax, [rbp+57h+var_68]
0x180075bfe  mov     [rbp+57h+var_B8], rax
0x180075c02  mov     [rbp+57h+var_B0], 14h
0x180075c0a  lea     rdx, [rbp+57h+var_C8]
0x180075c0e  mov     rcx, [r15+228h]
0x180075c15  mov     rax, [r15+208h]
0x180075c1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075c21  nop
0x180075c22  test    eax, eax
0x180075c24  jns     short loc_180075C41
0x180075c26  lea     r8, aDriverFailedD3_3; "Driver failed D3D12DDICAPS_TEXTURE_LAYO"...
0x180075c2d  mov     edx, 887A0020h; int
0x180075c32  call    ?ReportDriverError@CJournal@@QEAAXJPEBD@Z; CJournal::ReportDriverError(long,char const *)
0x180075c37  mov     ecx, 887A0020h; int
0x180075c3c  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180075c41  mov     rcx, [rbx+14B0h]
0x180075c48  mov     rax, [rcx]
0x180075c4b  mov     rdx, [rbx+14A8h]
0x180075c52  mov     rax, [rax+1F0h]
0x180075c59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075c5e  test    rax, rax
0x180075c61  jz      short loc_180075C85
0x180075c63  mov     rcx, [rbx+14B0h]
0x180075c6a  mov     rax, [rcx]
0x180075c6d  mov     rdx, [rbx+14A8h]
0x180075c74  mov     rax, [rax+1F8h]
0x180075c7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075c80  test    rax, rax
0x180075c83  jnz     short loc_180075CA0
0x180075c85  lea     r8, aDriverMustSetP; "Driver must set pfnMapHeap and pfnUnmap"...
0x180075c8c  mov     edx, 887A0020h; int
0x180075c91  call    ?ReportDriverError@CJournal@@QEAAXJPEBD@Z; CJournal::ReportDriverError(long,char const *)
0x180075c96  mov     ecx, 887A0020h; int
0x180075c9b  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180075ca0  mov     rcx, [rbx+14B0h]
0x180075ca7  mov     rax, [rcx]
0x180075caa  mov     rdx, [rbx+14A8h]
0x180075cb1  mov     rax, [rax+208h]
0x180075cb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075cbd  test    rax, rax
0x180075cc0  jnz     short loc_180075CDD
0x180075cc2  lea     r8, aDriverSetPfncr; "Driver set pfnCreateHeapAndResource to "...
0x180075cc9  mov     edx, 887A0020h; int
0x180075cce  call    ?ReportDriverError@CJournal@@QEAAXJPEBD@Z; CJournal::ReportDriverError(long,char const *)
0x180075cd3  mov     ecx, 887A0020h; int
0x180075cd8  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180075cdd  mov     rcx, [rbx+14B0h]
0x180075ce4  mov     rax, [rcx]
0x180075ce7  mov     rdx, [rbx+14A8h]
0x180075cee  mov     rax, [rax+280h]
0x180075cf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075cfa  test    rax, rax
0x180075cfd  jnz     short loc_180075D1A
0x180075cff  lea     r8, aDriverSetPfnch; "Driver set pfnCheckResourceAllocationIn"...
0x180075d06  mov     edx, 887A0020h; int
0x180075d0b  call    ?ReportDriverError@CJournal@@QEAAXJPEBD@Z; CJournal::ReportDriverError(long,char const *)
0x180075d10  mov     ecx, 887A0020h; int
0x180075d15  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180075d1a  mov     rcx, [rbx+14B0h]
0x180075d21  mov     rax, [rcx]
0x180075d24  mov     rdx, [rbx+14A8h]
0x180075d2b  mov     rax, [rax+288h]
0x180075d32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075d37  test    rax, rax
0x180075d3a  jnz     short loc_180075D57
0x180075d3c  lea     r8, aDriverSetPfnch_0; "Driver set pfnCheckSubresourceInfo to N"...
0x180075d43  mov     edx, 887A0020h; int
0x180075d48  call    ?ReportDriverError@CJournal@@QEAAXJPEBD@Z; CJournal::ReportDriverError(long,char const *)
0x180075d4d  mov     ecx, 887A0020h; int
0x180075d52  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180075d57  mov     rcx, [rbx+14B0h]
0x180075d5e  mov     rax, [rcx]
0x180075d61  mov     rdx, [rbx+14A8h]
0x180075d68  mov     rax, [rax+290h]
0x180075d6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075d74  xor     edx, edx
0x180075d76  test    rax, rax
0x180075d79  jnz     short loc_180075D98
0x180075d7b  lea     r8, aDriverSetPfnch_1; "Driver set pfnCheckExistingResourceAllo"...
0x180075d82  mov     edx, 887A0020h; int
0x180075d87  call    ?ReportDriverError@CJournal@@QEAAXJPEBD@Z; CJournal::ReportDriverError(long,char const *)
0x180075d8c  mov     ecx, 887A0020h; int
0x180075d91  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180075d96  xor     edx, edx
0x180075d98  cmp     dword ptr [rbx+130h], 9100h
0x180075da2  jl      loc_180075F7D
0x180075da8  mov     r12d, edx
0x180075dab  mov     eax, r12d
0x180075dae  lea     r14, ds:2B3h[rax*4]
0x180075db6  add     r14, rax
0x180075db9  lea     r14, [rbx+r14*4]
0x180075dbd  mov     dword ptr [rbp+57h+var_A8+4], r12d
0x180075dc1  test    r12d, r12d
0x180075dc4  jz      short loc_180075E1A
0x180075dc6  mov     [rbp+57h+var_C8], 3EBh
0x180075dce  lea     rax, [rbp+57h+var_A8]
0x180075dd2  mov     [rbp+57h+var_C0], rax
0x180075dd6  lea     rax, [rbp+57h+var_68]
0x180075dda  mov     [rbp+57h+var_B8], rax
0x180075dde  mov     [rbp+57h+var_B0], 14h
0x180075de6  lea     rdx, [rbp+57h+var_C8]
0x180075dea  mov     rcx, [r15+228h]
0x180075df1  mov     rax, [r15+208h]
0x180075df8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075dfd  nop
0x180075dfe  xor     edx, edx
  ... truncated ...
```
