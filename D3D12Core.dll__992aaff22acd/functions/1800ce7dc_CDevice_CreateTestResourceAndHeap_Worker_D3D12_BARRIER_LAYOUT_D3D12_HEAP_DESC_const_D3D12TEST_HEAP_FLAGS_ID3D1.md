# CDevice::CreateTestResourceAndHeap_Worker<D3D12_BARRIER_LAYOUT>(D3D12_HEAP_DESC const *,D3D12TEST_HEAP_FLAGS,ID3D12Heap *,ID3D12Resource *,unsigned __int64,void *,D3D12_RESOURCE_DESC2 const *,D3D11_RESOURCE_FLAGS const *,D3D12TEST_RESOURCE_FLAGS,D3D12_BARRIER_LAYOUT,D3D12_CLEAR_VALUE const *,ID3D12ProtectedResourceSession *,ID3D12LifetimeTracker *,ID3D12SwapChainAssistant *,uint,DXGI_FORMAT const *,_GUID const &,void * *,_GUID const &,void * *)

- ea: `0x1800ce7dc`
- end: `0x1800cfd0c`
- name: `??$CreateTestResourceAndHeap_Worker@W4D3D12_BARRIER_LAYOUT@@@CDevice@@QEAAJPEBUD3D12_HEAP_DESC@@W4D3D12TEST_HEAP_FLAGS@@PEAUID3D12Heap@@PEAUID3D12Resource@@_KPEAXPEBUD3D12_RESOURCE_DESC2@@PEBUD3D11_RESOURCE_FLAGS@@W4D3D12TEST_RESOURCE_FLAGS@@W4D3D12_BARRIER_LAYOUT@@PEBUD3D12_CLEAR_VALUE@@PEAUID3D12ProtectedResourceSession@@PEAUID3D12LifetimeTracker@@PEAUID3D12SwapChainAssistant@@IPEBW4DXGI_FORMAT@@AEBU_GUID@@PEAPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `5424`
- prototype: `__int64 __usercall@<rax>(CDevice *this@<rcx>, int, __int64, int, struct CD3DX12_RESOURCE_DESC2 *, int, int, int, __int64, __int64, int, int, int, __int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `38`
- tags: `broker_com_uri`

## callers

- `0x1800cd9fc`
- `0x1800cdce8`
- `0x1800cdeb4`

## callees

- `0x180003c84`
- `0x180004a38`
- `0x180006b40`
- `0x180007df0`
- `0x18000b010`
- `0x18000bee0`
- `0x180017d60`
- `0x180027ff4`
- `0x180028038`
- `0x18002a3f0`
- `0x18002e250`
- `0x18002e3e0`
- `0x180046000`
- `0x1800483f8`
- `0x180048568`
- `0x18004858c`
- `0x1800485d4`
- `0x180049c70`
- `0x18004c700`
- `0x18004db78`
- `0x180052c34`
- `0x180054104`
- `0x180058a6c`
- `0x180058c0c`
- `0x18006a1e0`
- `0x18006cf64`
- `0x180078b10`
- `0x18007de6c`
- `0x180092db4`
- `0x18009332c`
- `0x1800bb480`
- `0x1800bc094`
- `0x1800ccc94`
- `0x1800ce7dc`
- `0x1800ead00`
- `0x1800f0438`
- `0x18013fd9c`
- `0x180262020`

## import_xrefs

- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-0!__imp_D3DKMTCreateSynchronizationObject2` at `0x1800cf8c1`
- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-0!__imp_D3DKMTCreateKeyedMutex2` at `0x1800cf86c`

## string_xrefs

- `0x1800cf8ba`: `CreateKeyedMutexFence`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CDevice::CreateTestResourceAndHeap_Worker<enum D3D12_BARRIER_LAYOUT>(
        CDevice *this,
        __int64 *a2,
        __int16 a3,
        UINT64 a4,
        int a5,
        __int64 a6,
        int a7,
        struct CD3DX12_RESOURCE_DESC2 *a8,
        int a9,
        int a10,
        int a11,
        __int64 a12,
        void *a13,
        int a14,
        int a15,
        unsigned int a16,
        __int64 a17,
        __int64 a18,
        _QWORD *a19,
        __int64 a20)
{
  const struct CD3DX12_RESOURCE_DESC2 *v23; // rsi
  char v24; // r12
  bool v25; // di
  enum D3D12_TIGHT_ALIGNMENT_TIER v26; // eax
  __int64 v27; // rcx
  __int64 v28; // rax
  int v29; // ecx
  __int16 v30; // ax
  __int64 v31; // r9
  int v32; // eax
  __int64 *v33; // rcx
  int v34; // eax
  int v35; // eax
  char IsEnabled; // al
  int v37; // eax
  unsigned int v38; // ecx
  int v39; // eax
  int v40; // r8d
  struct D3D12_HEAP_PROPERTIES *CustomHeapProperties; // rax
  unsigned int v42; // eax
  UINT64 Alignment; // r8
  UINT64 SizeInBytes; // r12
  __int64 v45; // rax
  bool v46; // di
  __int64 v47; // rdx
  int v48; // r13d
  unsigned int v49; // edi
  struct D3D12_RESOURCE_ALLOCATION_INFO *v50; // rax
  UINT64 v51; // r10
  UINT64 v52; // rdx
  __int64 *v53; // rdi
  UINT64 *v54; // rcx
  UINT64 v55; // rax
  UINT64 v56; // rax
  __int64 v57; // r8
  __int128 *v58; // r12
  char v59; // cl
  unsigned int v60; // eax
  __int64 v61; // rcx
  int v62; // edx
  __int128 v63; // xmm2
  __int64 v64; // rdi
  __int64 v65; // rbx
  _DWORD *v66; // r9
  __int64 v67; // r8
  __int64 v68; // rcx
  unsigned int v69; // edx
  bool v70; // bl
  __int64 v71; // r8
  bool v72; // zf
  char v73; // r9
  int v74; // r8d
  int v75; // eax
  __int64 v76; // rdx
  int v77; // r9d
  int v78; // edx
  int v79; // r8d
  int v80; // eax
  int v81; // ebx
  int v82; // r10d
  int v83; // r8d
  int v84; // r9d
  int v85; // edx
  int v86; // edx
  int v87; // r8d
  int v88; // eax
  int v89; // ebx
  __int64 v90; // rdx
  __int64 v91; // r8
  unsigned int v92; // eax
  int v93; // eax
  int Alignment_high; // ebx
  unsigned int v95; // eax
  int v96; // eax
  int v97; // ebx
  __int64 *v98; // rsi
  int v99; // ebx
  int v100; // r8d
  int v101; // ecx
  unsigned int v102; // eax
  __int64 v103; // rcx
  __int64 v104; // rcx
  __int64 v105; // r9
  int v106; // eax
  int v107; // eax
  int v108; // eax
  __int64 result; // rax
  __int64 v110; // [rsp+20h] [rbp-738h]
  __int64 v111; // [rsp+30h] [rbp-728h]
  int v112; // [rsp+40h] [rbp-718h]
  char v113[4]; // [rsp+60h] [rbp-6F8h] BYREF
  int v114; // [rsp+64h] [rbp-6F4h] BYREF
  unsigned int v115; // [rsp+68h] [rbp-6F0h]
  unsigned int v116; // [rsp+6Ch] [rbp-6ECh]
  __int64 v117; // [rsp+70h] [rbp-6E8h]
  void *v118; // [rsp+78h] [rbp-6E0h]
  __int64 *v119; // [rsp+80h] [rbp-6D8h]
  int v120; // [rsp+88h] [rbp-6D0h]
  int v121; // [rsp+8Ch] [rbp-6CCh]
  int v122; // [rsp+90h] [rbp-6C8h]
  void *v123; // [rsp+98h] [rbp-6C0h] BYREF
  _QWORD *v124; // [rsp+A0h] [rbp-6B8h]
  __int64 v125; // [rsp+A8h] [rbp-6B0h]
  _QWORD *v126; // [rsp+B0h] [rbp-6A8h]
  __int64 v127; // [rsp+B8h] [rbp-6A0h]
  __int64 v128; // [rsp+C0h] [rbp-698h]
  __int64 v129; // [rsp+C8h] [rbp-690h]
  _com_error *v130; // [rsp+D0h] [rbp-688h] BYREF
  __int128 v131; // [rsp+E0h] [rbp-678h] BYREF
  __int128 v132; // [rsp+F0h] [rbp-668h]
  __int128 v133; // [rsp+100h] [rbp-658h]
  __int128 v134; // [rsp+110h] [rbp-648h]
  int v135; // [rsp+120h] [rbp-638h]
  int v136; // [rsp+124h] [rbp-634h]
  int v137; // [rsp+130h] [rbp-628h]
  int v138; // [rsp+138h] [rbp-620h]
  struct D3D12_RESOURCE_ALLOCATION_INFO v139; // [rsp+140h] [rbp-618h] BYREF
  int *v140; // [rsp+150h] [rbp-608h]
  int v141; // [rsp+158h] [rbp-600h]
  int v142; // [rsp+15Ch] [rbp-5FCh]
  int v143; // [rsp+160h] [rbp-5F8h]
  __int128 *v144; // [rsp+168h] [rbp-5F0h]
  struct D3D12_RESOURCE_ALLOCATION_INFO *v145; // [rsp+178h] [rbp-5E0h]
  _BYTE v146[48]; // [rsp+1B0h] [rbp-5A8h] BYREF
  UINT64 v147; // [rsp+1E0h] [rbp-578h]
  __int128 *v148; // [rsp+1E8h] [rbp-570h]
  struct D3D12_RESOURCE_ALLOCATION_INFO *v149; // [rsp+1F8h] [rbp-560h]
  int v150; // [rsp+200h] [rbp-558h]
  __int64 v151; // [rsp+208h] [rbp-550h]
  int v152; // [rsp+230h] [rbp-528h]
  char v153; // [rsp+234h] [rbp-524h]
  __int16 v154; // [rsp+235h] [rbp-523h]
  void *v155; // [rsp+238h] [rbp-520h]
  int v156; // [rsp+274h] [rbp-4E4h]
  _QWORD v157[6]; // [rsp+2C0h] [rbp-498h] BYREF
  _BYTE v158[24]; // [rsp+2F0h] [rbp-468h] BYREF
  __int128 v159; // [rsp+308h] [rbp-450h] BYREF
  __int64 v160; // [rsp+318h] [rbp-440h]
  __int64 v161; // [rsp+320h] [rbp-438h]
  int v162; // [rsp+328h] [rbp-430h]
  __int64 v163; // [rsp+32Ch] [rbp-42Ch]
  int v164; // [rsp+334h] [rbp-424h]
  int v165; // [rsp+338h] [rbp-420h]
  BOOL v166; // [rsp+33Ch] [rbp-41Ch]
  int v167; // [rsp+340h] [rbp-418h]
  int v168; // [rsp+344h] [rbp-414h]
  BOOL v169; // [rsp+348h] [rbp-410h]
  BOOL v170; // [rsp+34Ch] [rbp-40Ch]
  BOOL v171; // [rsp+350h] [rbp-408h]
  unsigned int v172; // [rsp+354h] [rbp-404h]
  int v173; // [rsp+358h] [rbp-400h]
  int v174; // [rsp+35Ch] [rbp-3FCh]
  int v175; // [rsp+360h] [rbp-3F8h]
  int v176; // [rsp+364h] [rbp-3F4h]
  int v177; // [rsp+368h] [rbp-3F0h]
  int SizeInBytes_high; // [rsp+36Ch] [rbp-3ECh]
  int v179; // [rsp+370h] [rbp-3E8h]
  int v180; // [rsp+374h] [rbp-3E4h]
  int v181; // [rsp+378h] [rbp-3E0h]
  int v182; // [rsp+37Ch] [rbp-3DCh]
  int v183; // [rsp+380h] [rbp-3D8h]
  int v184; // [rsp+384h] [rbp-3D4h]
  int v185; // [rsp+388h] [rbp-3D0h]
  __int64 v186; // [rsp+38Ch] [rbp-3CCh]
  __int64 v187; // [rsp+398h] [rbp-3C0h]
  enum D3D12_HEAP_TYPE v188; // [rsp+3A0h] [rbp-3B8h]
  __int64 v189; // [rsp+3A4h] [rbp-3B4h]
  unsigned int v190; // [rsp+3ACh] [rbp-3ACh]
  int v191; // [rsp+3B0h] [rbp-3A8h]
  int v192; // [rsp+3B4h] [rbp-3A4h]
  __int64 v193; // [rsp+3B8h] [rbp-3A0h]
  int v194; // [rsp+3C0h] [rbp-398h]
  int v195; // [rsp+3C4h] [rbp-394h]
  int v196; // [rsp+3C8h] [rbp-390h]
  int v197; // [rsp+3D0h] [rbp-388h]
  int v198; // [rsp+3D4h] [rbp-384h]
  int v199; // [rsp+3D8h] [rbp-380h]
  __int128 v200; // [rsp+3E0h] [rbp-378h]
  __int128 v201; // [rsp+3F0h] [rbp-368h]
  __int128 v202; // [rsp+400h] [rbp-358h]
  __int128 v203; // [rsp+410h] [rbp-348h]
  __int128 v204; // [rsp+420h] [rbp-338h]
  int v205; // [rsp+430h] [rbp-328h]
  _OWORD v206[4]; // [rsp+438h] [rbp-320h] BYREF
  __int64 v207; // [rsp+478h] [rbp-2E0h]
  __int128 v208; // [rsp+480h] [rbp-2D8h] BYREF
  _BYTE v209[48]; // [rsp+490h] [rbp-2C8h]
  __int128 v210; // [rsp+4D0h] [rbp-288h] BYREF
  __int128 v211; // [rsp+4E0h] [rbp-278h]
  __int128 v212; // [rsp+4F0h] [rbp-268h]
  __int128 v213; // [rsp+500h] [rbp-258h]
  __int128 v214; // [rsp+510h] [rbp-248h]
  _DWORD v215[20]; // [rsp+520h] [rbp-238h] BYREF
  char v216[272]; // [rsp+570h] [rbp-1E8h] BYREF
  char v217[48]; // [rsp+680h] [rbp-D8h] BYREF
  __int64 v218; // [rsp+6B0h] [rbp-A8h] BYREF
  enum D3D12_HEAP_TYPE v219; // [rsp+6B8h] [rbp-A0h]
  __int64 v220; // [rsp+6BCh] [rbp-9Ch]
  unsigned int v221; // [rsp+6C4h] [rbp-94h]
  int v222; // [rsp+6C8h] [rbp-90h]
  __int64 v223; // [rsp+6D0h] [rbp-88h]
  int v224; // [rsp+6D8h] [rbp-80h]
  __int64 v225; // [rsp+6E0h] [rbp-78h]
  D3D12_HEAP_TYPE Type; // [rsp+6E8h] [rbp-70h]
  __int64 v227; // [rsp+6ECh] [rbp-6Ch]
  unsigned int v228; // [rsp+6F4h] [rbp-64h]
  int v229; // [rsp+6F8h] [rbp-60h]
  int v230; // [rsp+708h] [rbp-50h]
  _QWORD v231[9]; // [rsp+710h] [rbp-48h] BYREF

  v139.SizeInBytes = a4;
  v119 = a2;
  v128 = a6;
  v23 = a8;
  v120 = a11;
  v127 = a12;
  v118 = a13;
  v115 = a16;
  v117 = a17;
  v125 = a18;
  v124 = a19;
  v126 = a19;
  v129 = a20;
  v24 = 0;
  if ( a19 )
    *a19 = 0;
  memset_0(&v210, 0, 0x50u);
  try
  {
    if ( a8 && a2 )
    {
      v25 = 1;
      v113[0] = 1;
    }
    else
    {
      v25 = 0;
      v113[0] = 0;
      if ( !a8 )
      {
        v113[0] = 0;
        if ( !a2 )
          goto LABEL_63;
        v27 = *a2;
        v28 = a2[4];
        if ( !v28 )
          v28 = 0x10000;
        LODWORD(v208) = 1;
        *((_QWORD *)&v208 + 1) = v28;
        *(_QWORD *)v209 = v27;
        *(_DWORD *)&v209[8] = 1;
        *(_QWORD *)&v209[12] = 65537;
        *(_QWORD *)&v209[20] = 1;
        *(_OWORD *)&v209[28] = 1u;
        *(_DWORD *)&v209[44] = 0;
        v210 = v208;
        v211 = *(_OWORD *)v209;
        v212 = *(_OWORD *)&v209[16];
        v213 = *(_OWORD *)&v209[32];
        v214 = 0;
        v23 = (const struct CD3DX12_RESOURCE_DESC2 *)&v210;
        v24 = 2;
LABEL_14:
        v29 = *((_DWORD *)a2 + 10);
        if ( (v29 & 1) != 0 && (a3 & 6) == 0 )
          a3 |= 2u;
        if ( (v29 & 8) != 0 )
        {
          a3 |= 0x280u;
          if ( (a3 & 6) == 0 )
            a3 |= 2u;
        }
        v30 = a3 | 0x10;
        if ( (a2[5] & 0x20) == 0 )
          v30 = a3;
        a3 = v30;
        v72 = (std::fill<D3D12_HEAP_DESC *,D3D12_HEAP_DESC>(&v218, v231) & 6) == 0;
        v32 = v230;
        if ( !v72 )
        {
          v32 = v230 | 1;
          v230 |= 1u;
        }
        if ( (a3 & 0x2000) != 0 )
          v230 = v32 | 0x200;
        if ( (a3 & 0x80u) != 0 )
          v224 |= 8u;
        v33 = &v218;
        do
        {
          v34 = 1;
          if ( *((_DWORD *)v33 + 6) != (_DWORD)v31 )
            v34 = *((_DWORD *)v33 + 6);
          *((_DWORD *)v33 + 6) = v34;
          v35 = 1;
          if ( *((_DWORD *)v33 + 5) != (_DWORD)v31 )
            v35 = *((_DWORD *)v33 + 5);
          *((_DWORD *)v33 + 5) = v35;
          v33 += 6;
        }
        while ( v33 != v231 );
        if ( (a3 & 0x200) != 0 )
        {
          v224 |= 8u;
          IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12Displayable>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_D3D12Displayable>::GetImpl'::`2'::impl);
          v31 = 0;
          if ( IsEnabled )
          {
            *(_DWORD *)v158 = *((_DWORD *)v23 + 8);
            *(_QWORD *)&v158[4] = 0;
            v37 = CDevice::CheckFeatureSupport(this, D3D12_FEATURE_FORMAT_SUPPORT, v158, 0xCu);
            v31 = 0;
            if ( (*((_BYTE *)this + 5316) || (a3 & 0x10) != 0)
              && *((_BYTE *)this + 1489)
              && v37 >= 0
              && ((*(_DWORD *)&v158[4] & 0x80000) != 0 || (*(_DWORD *)&v158[8] & 0x10000) != 0) )
            {
LABEL_42:
              v38 = v230 | 8;
              v230 |= 8u;
              goto LABEL_49;
            }
          }
          else if ( *((_BYTE *)this + 5316) || (a3 & 0x10) != 0 )
          {
            if ( !*((_BYTE *)this + 1489) )
              goto LABEL_42;
            v39 = CD3D11FormatHelper::DisplayScanOutSupport(
                    *((unsigned int *)v23 + 8),
                    *((unsigned int *)this + 362),
                    *((unsigned int *)this + 363),
                    0);
            v31 = 0;
            if ( v39 == 1 )
              goto LABEL_42;
          }
          v38 = v230 & 0xFFFFFFF7;
          v230 &= ~8u;
          a3 &= ~0x200u;
        }
        else
        {
          v38 = v230;
        }
LABEL_49:
        if ( (a3 & 0x100) != 0 && (a2[5] & 0xC4) == 0 )
        {
          v40 = v31;
          if ( *(_DWORD *)v23 == 1 )
          {
            v40 = 192;
          }
          else if ( *(_DWORD *)v23 == 2 || (unsigned int)(*(_DWORD *)v23 - 3) <= 1 )
          {
            v40 = (*((_DWORD *)v23 + 12) & 3) != 0 ? 132 : 68;
          }
          v230 = v40 | v38;
          v224 |= v40;
        }
        if ( Type != D3D12_HEAP_TYPE_CUSTOM )
        {
          CustomHeapProperties = CDevice::GetCustomHeapProperties(
                                   this,
                                   (struct D3D12_HEAP_PROPERTIES *)v158,
                                   v221,
                                   v219);
          Type = CustomHeapProperties->Type;
          v227 = *(_QWORD *)&CustomHeapProperties->CPUPageProperty;
          v42 = v221;
          v31 = 0;
          if ( !v221 )
            v42 = 1;
          v228 = v42;
          v229 = v222;
        }
        if ( (v24 & 2) != 0 )
          v225 = v31;
LABEL_63:
        v121 = a3 & 4;
        *(_DWORD *)v158 = a3 & 8;
        v122 = a3 & 0x10;
        v114 = a3 & 0x200;
        v116 = (v122 != 0 ? 0x10 : 0)
             | (v114 != 0 ? 0x200 : 0)
             | (v121 != 0 ? 4 : 0)
             | (*(_DWORD *)v158 != 0 ? 8 : 0)
             | a3 & 0x582
             | ((unsigned __int16)(a3 & 0x4000) >> 2);
        CLayeredResourceCreationArgs::CLayeredResourceCreationArgs((CLayeredResourceCreationArgs *)v146);
        if ( !v23 )
        {
          v48 = 33;
          v53 = v119;
          goto LABEL_91;
        }
        v112 = v24 & 2;
        HIDWORD(v111) = HIDWORD(v23);
        HIDWORD(v110) = HIDWORD(v128);
        SizeInBytes = v139.SizeInBytes;
        v45 = CLayeredResourceCreationArgs::CLayeredResourceCreationArgs(v216, this, v139.SizeInBytes);
        CLayeredResourceCreationArgs::operator=(v146, v45);
        std::vector<enum DXGI_FORMAT>::_Tidy(v217);
        if ( a2 )
        {
          v46 = 0;
          v47 = *((unsigned int *)a2 + 6);
        }
        else
        {
          if ( v139.SizeInBytes )
          {
            v47 = *(unsigned int *)((*(__int64 (__fastcall **)(UINT64, struct D3D12_RESOURCE_ALLOCATION_INFO *))(*(_QWORD *)v139.SizeInBytes + 64LL))(
                                      v139.SizeInBytes,
                                      &v139)
                                  + 24);
            v48 = 33;
            v46 = (*(_BYTE *)(SizeInBytes + 224) & 6) != 0 || (*(_BYTE *)(SizeInBytes + 220) & 0x21) != 0;
            goto LABEL_73;
          }
          v47 = (unsigned int)(1LL << ((__int64)(unsigned int)(*((_DWORD *)this + 1402) - *((_DWORD *)this + 1400)) >> 2))
              - 1;
          v46 = 1;
        }
        v48 = 33;
LABEL_73:
        v131 = 0;
        v132 = 0;
        v133 = 0;
        LOBYTE(v112) = v113[0];
        LODWORD(v111) = v115;
        LODWORD(v110) = CDevice::TranslateNodeMask(this, v47, 0);
        v49 = CDevice::VersionedCheckResourceAllocationInfo(this, &v131, v23, v116, v110, v46, v111, v117, v112);
        v152 = DWORD2(v133);
        v156 = DWORD1(v133);
        v153 = BYTE12(v133);
        v154 = *(_WORD *)((char *)&v133 + 13);
        if ( v117 )
        {
          std::vector<enum DXGI_FORMAT>::_Assign_counted_range<enum DXGI_FORMAT const *>(v157, v117, v115);
          *(_DWORD *)(v151 + 84) = v115;
          *(_QWORD *)(v151 + 88) = v157[0];
        }
        if ( (unsigned __int64)v131 >= 0xFFFFFFFFFFC00000uLL )
          ThrowFailure(-2147024882);
        v50 = DDIRAIToAPIRAI(&v139, (const struct D3D12DDI_RESOURCE_ALLOCATION_INFO_0022 *)&v131, v49);
        v52 = v50->SizeInBytes;
        Alignment = v50->Alignment;
        if ( (*((_DWORD *)v23 + 12) & 0x400) != 0 )
        {
          v210 = *(_OWORD *)v23;
          v211 = *((_OWORD *)v23 + 1);
          v212 = *((_OWORD *)v23 + 2);
          v213 = *((_OWORD *)v23 + 3);
          v214 = *((_OWORD *)v23 + 4);
          *((_QWORD *)&v210 + 1) = Alignment;
          v23 = (const struct CD3DX12_RESOURCE_DESC2 *)&v210;
          v148 = &v210;
        }
        v53 = v119;
        if ( SizeInBytes || v119 )
        {
          v147 = v52;
          if ( v119 )
          {
            v54 = (UINT64 *)&v218;
            do
            {
              v55 = *v54;
              if ( !*v54 )
                v55 = v52;
              *v54 = v55;
              v56 = v54[4];
              if ( !v56 )
                v56 = Alignment;
              v54[4] = v56;
              v54 += 6;
            }
            while ( v54 != v231 );
          }
        }
        else
        {
          v147 = v51;
        }
LABEL_91:
        *(_QWORD *)&v131 = &std::_Func_impl_no_alloc<_lambda_cb7126380e5e8dc36c48574558f94384_,void,unsigned int>::`vftable';
        *((_QWORD *)&v134 + 1) = &v131;
        SafeKMTHandle::SafeKMTHandle(&v208, &v131, Alignment);
        v139.SizeInBytes = (UINT64)&std::_Func_impl_no_alloc<_lambda_e338db3e2b0e7134473a6028ee089ba6_,void,unsigned int>::`vftable';
        v145 = &v139;
        SafeKMTHandle::SafeKMTHandle(v215, &v139, v57);
        v159 = 0;
        v160 = 0;
        v185 = 72;
        v186 = 6;
        v197 = 104;
        v198 = 6;
        v199 = 1;
        LODWORD(v161) = 104;
        memset(v206, 0, sizeof(v206));
        v207 = 0;
        v58 = 0;
        v123 = 0;
        if ( !v53 || (v230 & 1) == 0 )
        {
LABEL_156:
          v155 = v118;
          v98 = v119;
          if ( v119 )
          {
            if ( (v119[5] & 0x20) != 0 )
              v227 = 0x100000002LL;
            v224 &= 0xFFFFE7FF;
            v99 = CDevice::TranslateNodeMask(this, *((unsigned int *)v119 + 5), 1);
            v100 = CDevice::TranslateNodeMask(this, *((unsigned int *)v98 + 6), 0);
            *(_QWORD *)&v131 = 0;
            *((_QWORD *)&v131 + 1) = &GUID_NULL;
            v132 = 0u;
            v133 = 0u;
            v134 = 1u;
            v101 = -1;
            v136 = 0;
            if ( (v230 & 8) != 0 )
              v101 = 0;
            v135 = v101;
            v102 = *((_DWORD *)v98 + 5);
            if ( !v102 )
              v102 = 1;
            v114 = 0;
            _BitScanForward((unsigned int *)&v103, v102);
            v104 = *(unsigned int *)(*((_QWORD *)this + 700) + 4 * v103);
            v105 = v116;
            LODWORD(v105) = v116 | 0x10000000;
            CLayeredHeapCreationArgs::CLayeredHeapCreationArgs(
              &v139,
              (char *)this + 792,
              &v218,
              v105,
              *((_DWORD *)this + 359),
              (char *)this + 16 * v104 + 4 * v104 + 792,
              v146,
              &v131,
              v99,
              v100);
            v187 = v218;
            v188 = v219;
            v189 = v220;
            v190 = v221;
            v191 = v222;
            v192 = HIDWORD(v132);
            v193 = v223;
            v194 = v224;
            v195 = HIDWORD(v133);
            v196 = v143;
            v144 = v58;
            *(_QWORD *)v158 = 0;
            v106 = (*(__int64 (__fastcall **)(_QWORD, __int64, struct D3D12_RESOURCE_ALLOCATION_INFO *))(**((_QWORD **)this + 86) + 72LL))(
                     *((_QWORD *)this + 86),
                     8,
                     &v139);
            ThrowFailure(v106);
            if ( v124 )
              v107 = (***(__int64 (__fastcall ****)(_QWORD, __int64))(*(_QWORD *)(*(_QWORD *)v158 + 256LL) + 144LL))(
                       *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v158 + 256LL) + 144LL),
                       v125);
            else
              v107 = (***(__int64 (__fastcall ****)(_QWORD, __int64, _QWORD))(*(_QWORD *)v158 + 144LL))(
                       *(_QWORD *)(*(_QWORD *)v158 + 144LL),
                       v129,
                       0);
            ThrowFailure(v107);
            if ( v166 )
              CHeap::SetKeyedMutexHandles(*(_DWORD *)v158, (unsigned int)&v208, (unsigned int)v215, v167, v168);
            CHeap::CompleteDependencyGraph(*(CHeap **)v158);
            ATL::CComPtrBase<CApplicationIdentity>::~CComPtrBase<CApplicationIdentity>(v158);
          }
          else
          {
            v108 = (*(__int64 (__fastcall **)(_QWORD, __int64, _BYTE *, __int64, _QWORD, __int64, _QWORD *))(**((_QWORD **)this + 86) + 72LL))(
                     *((_QWORD *)this + 86),
                     5,
                     v146,
                     144,
                     0,
                     v125,
                     v124);
            ThrowFailure(v108);
          }
          ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(&v123);
          SD3D12SharedResourceCreationArgs::~SD3D12SharedResourceCreationArgs((SD3D12SharedResourceCreationArgs *)&v159);
          SafeKMTHandle::~SafeKMTHandle((SafeKMTHandle *)v215);
          SafeKMTHandle::~SafeKMTHandle((SafeKMTHandle *)&v208);
          std::vector<enum DXGI_FORMAT>::_Tidy(v157);
          return 0;
        }
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12Displayable>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_D3D12Displayable>::GetImpl'::`2'::impl);
        v169 = v121 == 0;
        v171 = v122 != 0;
        v166 = *(_DWORD *)v158 != 0;
        v170 = v114 != 0;
        if ( a3 < 0 )
          v170 = 0;
        v72 = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12Displayable>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_D3D12Displayable>::GetImpl'::`2'::impl) == 0;
        v59 = v230;
        if ( v72 )
          v59 = v224;
        v172 = v172 & 0xFFFFFFFE | ((unsigned __int8)(v59 & 8) >> 3);
        v165 = 0;
        v161 = 104;
        v163 = 0;
        v162 = 0;
        v60 = *((_DWORD *)v53 + 5);
        if ( !v60 )
          v60 = 1;
        v114 = 0;
        _BitScanForward((unsigned int *)&v61, v60);
        v62 = *((_DWORD *)v23 + 12);
        if ( (v62 & 0xAC0) == 0
          && v227 == __PAIR64__(
                       2
                     - (unsigned int)(*((_DWORD *)this + 5 * *(unsigned int *)(*((_QWORD *)this + 700) + 4 * v61) + 198) != 0),
                       1) )
        {
          LOBYTE(v58) = 1;
        }
        LODWORD(v131) = *(_DWORD *)v23;
        *((_QWORD *)&v131 + 1) = *((_QWORD *)v23 + 1);
        v132 = *((_OWORD *)v23 + 1);
        v133 = *((_OWORD *)v23 + 2);
        LODWORD(v134) = v62;
        *(_QWORD *)((char *)&v134 + 4) = *(_QWORD *)((char *)v23 + 52);
        HIDWORD(v134) = *((_DWORD *)v23 + 15);
        v63 = *((_OWORD *)v23 + 4);
        v200 = v131;
        v201 = v132;
        v202 = v133;
        v203 = v134;
        v204 = v63;
        v205 = v150;
        if ( v115 && v117 )
        {
          v64 = (unsigned int)Align<unsigned int>(32);
          v65 = *((_QWORD *)&v206[0] + 1) - *(_QWORD *)&v206[0];
          v113[0] = 0;
          std::vector<unsigned char>::_Resize<unsigned char>(
            v206,
            *((_QWORD *)&v206[0] + 1) - *(_QWORD *)&v206[0] + v64,
            v113);
          v66 = (_DWORD *)(v65 + *(_QWORD *)&v206[0]);
          *v66 = 1;
          v66[1] = v64;
          v67 = 0;
          v68 = v117;
          do
          {
            if ( *(_DWORD *)(v68 + 4 * v67) < 0xC0u )
            {
              v69 = *(_DWORD *)(v68 + 4 * v67);
              *(_QWORD *)&v66[2 * ((unsigned __int64)v69 >> 6) + 2] |= 1LL << (v69 & 0x3F);
              v68 = v117;
            }
            v67 = (unsigned int)(v67 + 1);
          }
          while ( (unsigned int)v67 < v115 );
        }
        if ( !(_BYTE)v58 )
        {
LABEL_154:
          v58 = &v159;
          if ( v166 )
          {
            v114 = 0;
            v139.SizeInBytes = 0;
            v139.Alignment = 0;
            v89 = v169;
            v142 = v89;
            v140 = &v114;
            v141 = 4;
            memset_0(&v131, 0, 0x60u);
            LODWORD(v131) = *(_DWORD *)(*((_QWORD *)this + 95) + 56LL);
            DWORD2(v131) = 3;
            HIDWORD(v131) = (2 * v89) | 1;
            v92 = CallAndLogImpl<long (*)(_D3DKMT_CREATEKEYEDMUTEX2 *),_D3DKMT_CREATEKEYEDMUTEX2 *>(
                    D3DKMTCreateKeyedMutex2,
                    v90,
                    v91,
                    &v139);
            v93 = NDXGI::CDevice::NTStatusToHResult(*((_QWORD *)this + 95), v92, 1);
            ThrowFailure(v93);
            Alignment_high = HIDWORD(v139.Alignment);
            SafeKMTHandle::Release((SafeKMTHandle *)&v208);
            LODWORD(v208) = Alignment_high;
            v95 = CallAndLogImpl<long (*)(D3DDDI_DESTROYPAGINGQUEUE *),D3DDDI_DESTROYPAGINGQUEUE *>(
                    D3DKMTCreateSynchronizationObject2,
                    "CreateKeyedMutexFence",
                    CLayeredObject<CCommandAllocator>::AddRef,
                    &v131);
            v96 = NDXGI::CDevice::NTStatusToHResult(*((_QWORD *)this + 95), v95, 1);
            ThrowFailure(v96);
            v97 = v138;
            SafeKMTHandle::Release((SafeKMTHandle *)v215);
            v215[0] = v97;
            v167 = v139.Alignment;
            v168 = v137;
          }
          goto LABEL_156;
        }
        v70 = *(_DWORD *)v23 == 3 && *((_WORD *)v23 + 15) == 1 && *((_DWORD *)v23 + 9) == 1;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12Displayable>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_D3D12Displayable>::GetImpl'::`2'::impl) )
        {
          if ( v70 && (*((_BYTE *)v23 + 48) & 0xE) == 0 && (*((_BYTE *)v23 + 48) & 0x11) != 0 )
            goto LABEL_121;
        }
        else if ( v70 && (*((_DWORD *)v23 + 12) & 0xF) == 1 )
        {
LABEL_121:
          LOBYTE(v71) = *((_BYTE *)this + 712);
          if ( (unsigned __int8)IsCrossApiShareableFormat(
                                  *((unsigned int *)v23 + 8),
                                  *((unsigned int *)this + 363),
                                  v71) )
          {
            v162 = *((_DWORD *)v23 + 4);
            LODWORD(v163) = *((_DWORD *)v23 + 6);
            HIDWORD(v163) = *((_DWORD *)v23 + 8);
            v164 = *((unsigned __int16 *)v23 + 14);
          }
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12Displayable>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_D3D12Displayable>::GetImpl'::`2'::impl) )
          v72 = *((_BYTE *)this + 1491) == 0;
        else
          v72 = *((_BYTE *)this + 1489) == 0;
        if ( !v72 && (v172 & 1) != 0 && v70 )
        {
          v73 = 1;
          v48 = 0;
        }
        else
        {
          v73 = 0;
        }
        LODWORD(v139.SizeInBytes) = (v73 != 0 ? 0x600 : 0)
                                  | (32 * (*((_DWORD *)v23 + 12) & 4))
                                  | (32 * (*((_DWORD *)v23 + 12) & 1))
                                  | 8;
        v74 = (v166 ? 256 : 2) | (v169 ? 0x800 : 0) | (v118 != 0 ? 0x80000 : 0);
        if ( v73 )
        {
          if ( (*((_BYTE *)v23 + 48) & 0x20) == 0 )
            v74 |= 0x200000u;
          v75 = 0x100000;
        }
        else
        {
          v75 = 0;
        }
        HIDWORD(v139.SizeInBytes) = v75 | v74;
        v139.Alignment = 0;
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12Displayable>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_D3D12Displayable>::GetImpl'::`2'::impl);
        if ( v70 )
        {
          v76 = *((unsigned int *)this + 363);
          if ( (int)v76 >= 7
            && (unsigned __int8)CD3D11FormatHelper::IsCrossD3DAPIShareableFormat(*((unsigned int *)v23 + 8), v76)
            && !*((_DWORD *)v23 + 11)
            && (*((_DWORD *)v23 + 12) & v48) == v48
            && (*((_BYTE *)v23 + 48) & 0x1A) == 0 )
          {
            v149 = &v139;
            HIDWORD(v161) = 4;
            switch ( *(_DWORD *)v23 )
            {
              case 1:
                v173 = 1;
                v80 = *((_DWORD *)v23 + 4);
                v175 = 0;
                v176 = v139.SizeInBytes;
                v177 = v139.Alignment;
                SizeInBytes_high = HIDWORD(v139.SizeInBytes);
                v179 = HIDWORD(v139.Alignment);
                break;
              case 2:
                v173 = 2;
                v86 = *((unsigned __int16 *)v23 + 14);
                v87 = *((_DWORD *)v23 + 8);
                v80 = *((_DWORD *)v23 + 4);
                v175 = *((unsigned __int16 *)v23 + 15);
                v176 = v86;
                v177 = v87;
                SizeInBytes_high = 0;
                v179 = v139.SizeInBytes;
                v180 = v139.Alignment;
                v181 = HIDWORD(v139.SizeInBytes);
                break;
              case 3:
                v173 = 3;
                v81 = *((_DWORD *)v23 + 10);
                v82 = *((_DWORD *)v23 + 9);
                v83 = *((unsigned __int16 *)v23 + 15);
                v84 = *((unsigned __int16 *)v23 + 14);
                v85 = *((_DWORD *)v23 + 8);
                v80 = *((_DWORD *)v23 + 4);
                v175 = *((_DWORD *)v23 + 6);
                v176 = v83;
                v177 = v84;
                SizeInBytes_high = v85;
                v179 = v82;
                v180 = v81;
                v181 = 0;
                v182 = v139.SizeInBytes;
                v183 = v139.Alignment;
                v184 = HIDWORD(v139.SizeInBytes);
                break;
              default:
                v173 = 4;
                v77 = *((unsigned __int16 *)v23 + 15);
                v78 = *((unsigned __int16 *)v23 + 14);
                v79 = *((_DWORD *)v23 + 8);
                v80 = *((_DWORD *)v23 + 4);
                v175 = *((_DWORD *)v23 + 6);
                v176 = v78;
                v177 = v77;
                SizeInBytes_high = v79;
                v179 = 0;
                v180 = v139.SizeInBytes;
                v181 = v139.Alignment;
                v182 = HIDWORD(v139.SizeInBytes);
                break;
            }
            v174 = v80;
            if ( !v118
              && (v139.SizeInBytes & 0x8000000000000LL) != 0
              && CDevice::EnsureContentProtectionSupported(this)
              && (**((_BYTE **)this + 929) & 1) != 0 )
            {
              *(_QWORD *)v158 = 0;
              *(_OWORD *)&v158[8] = D3D12_PROTECTED_RESOURCES_SESSION_HARDWARE_PROTECTED;
              v88 = CDevice::CreateProtectedResourceSessionImpl(
                      this,
                      (const struct D3D12_PROTECTED_RESOURCE_SESSION_DESC1 *)v158,
                      &GUID_ffffffff_335a_4bc5_9de9_43d8fb7777ae,
                      &v123);
              ThrowFailure(v88);
              v118 = v123;
            }
          }
        }
        goto LABEL_154;
      }
    }
    v26 = CDevice::TightAlignmentTier(this);
    v23 = D3DX12ConditionallyExpandAPIDesc(
            (struct CD3DX12_RESOURCE_DESC2 *)&v210,
            a8,
            v26 >= D3D12_TIGHT_ALIGNMENT_TIER_1,
            v25);
    v24 = 0;
    if ( !a2 )
      goto LABEL_63;
    goto LABEL_14;
  }
  catch ( _com_error *v130 )
  {
    if ( v126 )
      *v126 = 0;
    return *((unsigned int *)v130 + 2);
  }
  catch ( std::bad_alloc )
  {
    if ( v126 )
      *v126 = 0;
    return 2147942414LL;
  }
  return result;
}

```

## disassembly

```asm
0x1800ce7dc  push    rbx
0x1800ce7de  push    rsi
0x1800ce7df  push    rdi
0x1800ce7e0  push    r12
0x1800ce7e2  push    r13
0x1800ce7e4  push    r14
0x1800ce7e6  push    r15
0x1800ce7e8  sub     rsp, 720h
0x1800ce7ef  mov     rax, cs:__security_cookie
0x1800ce7f6  xor     rax, rsp
0x1800ce7f9  mov     [rsp+758h+var_48], rax
0x1800ce801  mov     [rsp+758h+var_618.SizeInBytes], r9
0x1800ce809  mov     ebx, r8d
0x1800ce80c  mov     r13, rdx
0x1800ce80f  mov     [rsp+758h+var_6D8], rdx
0x1800ce817  mov     r15, rcx
0x1800ce81a  mov     rax, [rsp+758h+arg_28]
0x1800ce822  mov     [rsp+758h+var_698], rax
0x1800ce82a  mov     rsi, [rsp+758h+arg_38]
0x1800ce832  mov     eax, [rsp+758h+arg_50]
0x1800ce839  mov     [rsp+758h+var_6D0], eax
0x1800ce840  mov     rax, [rsp+758h+arg_58]
0x1800ce848  mov     [rsp+758h+var_6A0], rax
0x1800ce850  mov     rax, [rsp+758h+arg_60]
0x1800ce858  mov     [rsp+758h+var_6E0], rax
0x1800ce85d  mov     eax, [rsp+758h+arg_78]
0x1800ce864  mov     [rsp+758h+var_6F0], eax
0x1800ce868  mov     rax, [rsp+758h+arg_80]
0x1800ce870  mov     [rsp+758h+var_6E8], rax
0x1800ce875  mov     rax, [rsp+758h+arg_88]
0x1800ce87d  mov     [rsp+758h+var_6B0], rax
0x1800ce885  mov     rax, [rsp+758h+arg_90]
0x1800ce88d  mov     [rsp+758h+var_6B8], rax
0x1800ce895  mov     [rsp+758h+var_6A8], rax
0x1800ce89d  mov     rcx, [rsp+758h+arg_98]
0x1800ce8a5  mov     [rsp+758h+var_690], rcx
0x1800ce8ad  xor     r12d, r12d
0x1800ce8b0  test    rax, rax
0x1800ce8b3  jz      short loc_1800CE8B8
0x1800ce8b5  mov     [rax], r12
0x1800ce8b8  xor     edx, edx; Val
0x1800ce8ba  lea     r8d, [rdx+50h]; Size
0x1800ce8be  lea     rcx, [rsp+758h+var_288]; void *
0x1800ce8c6  call    memset_0
0x1800ce8cb  xor     r9d, r9d
0x1800ce8ce  test    rsi, rsi
0x1800ce8d1  jz      short loc_1800CE8E6
0x1800ce8d3  test    r13, r13
0x1800ce8d6  jz      short loc_1800CE8E6
0x1800ce8d8  lea     r14d, [r9+1]
0x1800ce8dc  mov     dil, r14b
0x1800ce8df  mov     [rsp+758h+var_6F8], r14b
0x1800ce8e4  jmp     short loc_1800CE8F9
0x1800ce8e6  mov     dil, r9b
0x1800ce8e9  mov     [rsp+758h+var_6F8], r9b
0x1800ce8ee  mov     r14d, 1
0x1800ce8f4  test    rsi, rsi
0x1800ce8f7  jz      short loc_1800CE937
0x1800ce8f9  mov     rcx, r15; this
0x1800ce8fc  call    ?TightAlignmentTier@CDevice@@QEBA?AW4D3D12_TIGHT_ALIGNMENT_TIER@@XZ; CDevice::TightAlignmentTier(void)
0x1800ce901  cmp     eax, r14d
0x1800ce904  setnl   r8b; bool
0x1800ce908  mov     r9b, dil; bool
0x1800ce90b  mov     rdx, rsi; struct CD3DX12_RESOURCE_DESC2 *
0x1800ce90e  lea     rcx, [rsp+758h+var_288]; struct CD3DX12_RESOURCE_DESC2 *
0x1800ce916  call    ?D3DX12ConditionallyExpandAPIDesc@@YAPEBUCD3DX12_RESOURCE_DESC2@@AEAU1@PEBU1@_N2@Z; D3DX12ConditionallyExpandAPIDesc(CD3DX12_RESOURCE_DESC2 &,CD3DX12_RESOURCE_DESC2 const *,bool,bool)
0x1800ce91b  mov     rsi, rax
0x1800ce91e  xor     r9d, r9d
0x1800ce921  mov     r12d, r9d
0x1800ce924  test    r13, r13
0x1800ce927  jz      loc_1800CEC6B
0x1800ce92d  mov     edi, 10000h
0x1800ce932  jmp     loc_1800CE9FE
0x1800ce937  mov     [rsp+758h+var_6F8], r9b
0x1800ce93c  test    r13, r13
0x1800ce93f  jz      loc_1800CEC6B
0x1800ce945  xorps   xmm2, xmm2
0x1800ce948  mov     rcx, [r13+0]
0x1800ce94c  mov     rax, [r13+20h]
0x1800ce950  mov     edi, 10000h
0x1800ce955  test    rax, rax
0x1800ce958  cmovz   rax, rdi
0x1800ce95c  mov     dword ptr [rsp+758h+var_2D8], r14d
0x1800ce964  mov     qword ptr [rsp+758h+var_2D8+8], rax
0x1800ce96c  mov     qword ptr [rsp+758h+var_2C8], rcx
0x1800ce974  mov     dword ptr [rsp+758h+var_2C8+8], r14d
0x1800ce97c  mov     qword ptr [rsp+758h+var_2C8+0Ch], 10001h
0x1800ce988  mov     [rsp+758h+var_2B4], r14
0x1800ce990  mov     qword ptr [rsp+758h+var_2AC], r14
0x1800ce998  mov     qword ptr [rsp+758h+var_2AC+8], r9
0x1800ce9a0  mov     [rsp+758h+var_29C], r9d
0x1800ce9a8  movaps  xmm0, [rsp+758h+var_2D8]
0x1800ce9b0  movaps  [rsp+758h+var_288], xmm0
0x1800ce9b8  movaps  xmm1, [rsp+758h+var_2C8]
0x1800ce9c0  movaps  [rsp+758h+var_278], xmm1
0x1800ce9c8  movaps  xmm0, xmmword ptr [rsp+4A0h]
0x1800ce9d0  movaps  [rsp+758h+var_268], xmm0
0x1800ce9d8  movaps  xmm1, [rsp+758h+var_2AC+4]
0x1800ce9e0  movaps  [rsp+758h+var_258], xmm1
0x1800ce9e8  movaps  [rsp+758h+var_248], xmm2
0x1800ce9f0  lea     rsi, [rsp+758h+var_288]
0x1800ce9f8  mov     r12d, 2
0x1800ce9fe  mov     ecx, [r13+28h]
0x1800cea02  test    r14b, cl
0x1800cea05  jz      short loc_1800CEA0F
0x1800cea07  test    bl, 6
0x1800cea0a  jnz     short loc_1800CEA0F
0x1800cea0c  or      ebx, 2
0x1800cea0f  test    cl, 8
0x1800cea12  jz      short loc_1800CEA22
0x1800cea14  or      ebx, 280h
0x1800cea1a  test    bl, 6
0x1800cea1d  jnz     short loc_1800CEA22
0x1800cea1f  or      ebx, 2
0x1800cea22  mov     eax, ebx
0x1800cea24  or      eax, 10h
0x1800cea27  test    byte ptr [r13+28h], 20h
0x1800cea2c  cmovz   eax, ebx
0x1800cea2f  mov     ebx, eax
0x1800cea31  mov     r8, r13
0x1800cea34  lea     rdx, [rsp+758h+var_48]
0x1800cea3c  lea     rcx, [rsp+758h+var_A8]
0x1800cea44  call    ??$fill@PEAUD3D12_HEAP_DESC@@U1@@std@@YAXQEAUD3D12_HEAP_DESC@@0AEBU1@@Z; std::fill<D3D12_HEAP_DESC *,D3D12_HEAP_DESC>(D3D12_HEAP_DESC * const,D3D12_HEAP_DESC * const,D3D12_HEAP_DESC const &)
0x1800cea49  test    al, 6
0x1800cea4b  mov     eax, [rsp+758h+var_50]
0x1800cea52  jz      short loc_1800CEA5E
0x1800cea54  or      eax, r14d
0x1800cea57  mov     [rsp+758h+var_50], eax
0x1800cea5e  bt      ebx, 0Dh
0x1800cea62  jnb     short loc_1800CEA6F
0x1800cea64  bts     eax, 9
0x1800cea68  mov     [rsp+758h+var_50], eax
0x1800cea6f  test    bl, bl
0x1800cea71  jns     short loc_1800CEA7B
0x1800cea73  or      [rsp+758h+var_80], 8
0x1800cea7b  lea     rcx, [rsp+758h+var_A8]
0x1800cea83  mov     eax, r14d
0x1800cea86  cmp     [rcx+18h], r9d
0x1800cea8a  cmovnz  eax, [rcx+18h]
0x1800cea8e  mov     [rcx+18h], eax
0x1800cea91  mov     eax, r14d
0x1800cea94  cmp     [rcx+14h], r9d
0x1800cea98  cmovnz  eax, [rcx+14h]
0x1800cea9c  mov     [rcx+14h], eax
0x1800cea9f  add     rcx, 30h ; '0'
0x1800ceaa3  lea     rax, [rsp+758h+var_48]
0x1800ceaab  cmp     rcx, rax
0x1800ceaae  jnz     short loc_1800CEA83
0x1800ceab0  bt      ebx, 9
0x1800ceab4  jnb     loc_1800CEB98
0x1800ceaba  or      [rsp+758h+var_80], 8
0x1800ceac2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_D3D12Displayable@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_D3D12Displayable@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12Displayable> `wil::Feature<__WilFeatureTraits_Feature_D3D12Displayable>::GetImpl(void)'::`2'::impl
0x1800ceac9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_D3D12Displayable@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12Displayable>::__private_IsEnabled(void)
0x1800ceace  xor     r9d, r9d
0x1800cead1  test    al, al
0x1800cead3  jz      short loc_1800CEB4C
0x1800cead5  mov     eax, [rsi+20h]
0x1800cead8  mov     dword ptr [rsp+758h+var_468], eax
0x1800ceadf  mov     qword ptr [rsp+758h+var_468+4], r9
0x1800ceae7  mov     r9d, 0Ch; unsigned int
0x1800ceaed  lea     r8, [rsp+758h+var_468]; void *
0x1800ceaf5  lea     edx, [r9-9]; enum D3D12_FEATURE
0x1800ceaf9  mov     rcx, r15; this
0x1800ceafc  call    ?CheckFeatureSupport@CDevice@@UEAAJW4D3D12_FEATURE@@PEAXI@Z; CDevice::CheckFeatureSupport(D3D12_FEATURE,void *,uint)
0x1800ceb01  xor     r9d, r9d
0x1800ceb04  cmp     [r15+14C4h], r9b
0x1800ceb0b  jnz     short loc_1800CEB12
0x1800ceb0d  test    bl, 10h
0x1800ceb10  jz      short loc_1800CEB81
0x1800ceb12  cmp     [r15+5D1h], r9b
0x1800ceb19  jz      short loc_1800CEB81
0x1800ceb1b  shr     eax, 1Fh
0x1800ceb1e  xor     al, r14b
0x1800ceb21  jz      short loc_1800CEB81
0x1800ceb23  test    dword ptr [rsp+758h+var_468+4], 80000h
0x1800ceb2e  jnz     short loc_1800CEB39
0x1800ceb30  test    dword ptr [rsp+758h+var_468+8], edi
0x1800ceb37  jz      short loc_1800CEB81
0x1800ceb39  mov     ecx, [rsp+758h+var_50]
0x1800ceb40  or      ecx, 8
0x1800ceb43  mov     [rsp+758h+var_50], ecx
0x1800ceb4a  jmp     short loc_1800CEB9F
0x1800ceb4c  cmp     [r15+14C4h], r9b
0x1800ceb53  jnz     short loc_1800CEB5A
0x1800ceb55  test    bl, 10h
0x1800ceb58  jz      short loc_1800CEB81
0x1800ceb5a  cmp     [r15+5D1h], r9b
0x1800ceb61  jz      short loc_1800CEB39
0x1800ceb63  mov     r8d, [r15+5ACh]
0x1800ceb6a  mov     edx, [r15+5A8h]
0x1800ceb71  mov     ecx, [rsi+20h]
0x1800ceb74  call    ?DisplayScanOutSupport@CD3D11FormatHelper@@SA?AW4D3D11_REQUIREMENTS@@W4DXGI_FORMAT@@W4D3D_FEATURE_LEVEL@@W4eExtendedFormatFeatures@1@@Z; CD3D11FormatHelper::DisplayScanOutSupport(DXGI_FORMAT,D3D_FEATURE_LEVEL,CD3D11FormatHelper::eExtendedFormatFeatures)
0x1800ceb79  xor     r9d, r9d
0x1800ceb7c  cmp     eax, r14d
0x1800ceb7f  jz      short loc_1800CEB39
0x1800ceb81  mov     ecx, [rsp+758h+var_50]
0x1800ceb88  and     ecx, 0FFFFFFF7h
0x1800ceb8b  mov     [rsp+758h+var_50], ecx
0x1800ceb92  btr     ebx, 9
0x1800ceb96  jmp     short loc_1800CEB9F
0x1800ceb98  mov     ecx, [rsp+758h+var_50]
0x1800ceb9f  bt      ebx, 8
0x1800ceba3  jnb     short loc_1800CEBF1
0x1800ceba5  test    byte ptr [r13+28h], 0C4h
0x1800cebaa  jnz     short loc_1800CEBF1
0x1800cebac  mov     r8d, r9d
0x1800cebaf  mov     edx, [rsi]
0x1800cebb1  sub     edx, 1
0x1800cebb4  jz      short loc_1800CEBD9
0x1800cebb6  sub     edx, 1
0x1800cebb9  jz      short loc_1800CEBC5
0x1800cebbb  sub     edx, 1
0x1800cebbe  jz      short loc_1800CEBC5
0x1800cebc0  cmp     edx, 1
0x1800cebc3  jnz     short loc_1800CEBDF
0x1800cebc5  mov     eax, [rsi+30h]
0x1800cebc8  and     al, 3
0x1800cebca  neg     al
0x1800cebcc  sbb     r8d, r8d
0x1800cebcf  and     r8d, 40h
0x1800cebd3  add     r8d, 44h ; 'D'
0x1800cebd7  jmp     short loc_1800CEBDF
0x1800cebd9  mov     r8d, 0C0h
0x1800cebdf  or      ecx, r8d
0x1800cebe2  mov     [rsp+758h+var_50], ecx
0x1800cebe9  or      [rsp+758h+var_80], r8d
0x1800cebf1  cmp     [rsp+758h+var_70], 4
0x1800cebf9  jz      short loc_1800CEC5D
0x1800cebfb  mov     r9d, [rsp+758h+var_A0]; enum D3D12_HEAP_TYPE
0x1800cec03  mov     r8d, [rsp+758h+var_94]; unsigned int
0x1800cec0b  lea     rdx, [rsp+758h+var_468]; retstr
0x1800cec13  mov     rcx, r15; this
0x1800cec16  call    ?GetCustomHeapProperties@CDevice@@UEAA?AUD3D12_HEAP_PROPERTIES@@IW4D3D12_HEAP_TYPE@@@Z; CDevice::GetCustomHeapProperties(uint,D3D12_HEAP_TYPE)
0x1800cec1b  mov     ecx, [rax]
0x1800cec1d  mov     [rsp+758h+var_70], ecx
0x1800cec24  mov     ecx, [rax+4]
0x1800cec27  mov     dword ptr [rsp+758h+var_6C], ecx
0x1800cec2e  mov     eax, [rax+8]
0x1800cec31  mov     dword ptr [rsp+758h+var_6C+4], eax
0x1800cec38  mov     eax, [rsp+758h+var_94]
0x1800cec3f  xor     r9d, r9d
0x1800cec42  test    eax, eax
0x1800cec44  cmovz   eax, r14d
0x1800cec48  mov     [rsp+758h+var_64], eax
0x1800cec4f  mov     eax, [rsp+758h+var_90]
0x1800cec56  mov     [rsp+758h+var_60], eax
0x1800cec5d  test    r12b, 2
0x1800cec61  jz      short loc_1800CEC6B
0x1800cec63  mov     [rsp+758h+var_78], r9
0x1800cec6b  mov     edx, ebx
0x1800cec6d  and     edx, 4
0x1800cec70  mov     [rsp+758h+var_6CC], edx
0x1800cec77  mov     ecx, ebx
0x1800cec79  and     ecx, 8
0x1800cec7c  mov     dword ptr [rsp+758h+var_468], ecx
0x1800cec83  mov     r8d, ebx
0x1800cec86  and     r8d, 10h
0x1800cec8a  mov     [rsp+758h+var_6C8], r8d
0x1800cec92  mov     r9d, ebx
0x1800cec95  and     r9d, 200h
0x1800cec9c  mov     [rsp+758h+var_6F4], r9d
0x1800ceca1  mov     r10d, ebx
0x1800ceca4  and     r10d, 4000h
0x1800cecab  shr     r10d, 2
0x1800cecaf  mov     eax, ebx
0x1800cecb1  and     eax, 582h
0x1800cecb6  or      r10d, eax
0x1800cecb9  mov     eax, ecx
0x1800cecbb  neg     eax
0x1800cecbd  sbb     ecx, ecx
0x1800cecbf  and     ecx, 8
0x1800cecc2  or      r10d, ecx
0x1800cecc5  mov     eax, edx
0x1800cecc7  neg     eax
0x1800cecc9  sbb     ecx, ecx
0x1800ceccb  and     ecx, 4
0x1800cecce  or      r10d, ecx
0x1800cecd1  mov     eax, r9d
0x1800cecd4  neg     eax
0x1800cecd6  sbb     ecx, ecx
0x1800cecd8  and     ecx, 200h
0x1800cecde  or      r10d, ecx
0x1800cece1  mov     eax, r8d
0x1800cece4  neg     eax
0x1800cece6  sbb     ecx, ecx
0x1800cece8  and     ecx, 10h
0x1800ceceb  or      r10d, ecx
0x1800cecee  mov     [rsp+758h+var_6EC], r10d
0x1800cecf3  lea     rcx, [rsp+758h+var_5A8]; this
0x1800cecfb  call    ??0CLayeredResourceCreationArgs@@QEAA@XZ; CLayeredResourceCreationArgs::CLayeredResourceCreationArgs(void)
0x1800ced00  nop
0x1800ced01  test    rsi, rsi
0x1800ced04  jz      loc_1800CEFD1
0x1800ced0a  and     r12d, 2
0x1800ced0e  mov     rax, [rsp+758h+var_6A0]
0x1800ced16  mov     [rsp+758h+var_708], rax
0x1800ced1b  mov     eax, [rsp+758h+var_6D0]
0x1800ced22  mov     [rsp+758h+var_710], eax
0x1800ced26  mov     [rsp+758h+var_718], r12d
0x1800ced2b  mov     [rsp+758h+var_728], rsi
  ... truncated ...
```
