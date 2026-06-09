# CDevice::CreateTestResourceAndHeap_Worker<D3D12_RESOURCE_STATES>(D3D12_HEAP_DESC const *,D3D12TEST_HEAP_FLAGS,ID3D12Heap *,ID3D12Resource *,unsigned __int64,void *,D3D12_RESOURCE_DESC2 const *,D3D11_RESOURCE_FLAGS const *,D3D12TEST_RESOURCE_FLAGS,D3D12_RESOURCE_STATES,D3D12_CLEAR_VALUE const *,ID3D12ProtectedResourceSession *,ID3D12LifetimeTracker *,ID3D12SwapChainAssistant *,uint,DXGI_FORMAT const *,_GUID const &,void * *,_GUID const &,void * *)

- ea: `0x18002ccf8`
- end: `0x18002e248`
- name: `??$CreateTestResourceAndHeap_Worker@W4D3D12_RESOURCE_STATES@@@CDevice@@QEAAJPEBUD3D12_HEAP_DESC@@W4D3D12TEST_HEAP_FLAGS@@PEAUID3D12Heap@@PEAUID3D12Resource@@_KPEAXPEBUD3D12_RESOURCE_DESC2@@PEBUD3D11_RESOURCE_FLAGS@@W4D3D12TEST_RESOURCE_FLAGS@@W4D3D12_RESOURCE_STATES@@PEBUD3D12_CLEAR_VALUE@@PEAUID3D12ProtectedResourceSession@@PEAUID3D12LifetimeTracker@@PEAUID3D12SwapChainAssistant@@IPEBW4DXGI_FORMAT@@AEBU_GUID@@PEAPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `5456`
- prototype: `__int64 __usercall@<rax>(CDevice *this@<rcx>, int, __int64, __int64, struct CD3DX12_RESOURCE_DESC2 *, __int64, int, int, __int64, __int64, __int64, __int64, int, int, __int64, __int64, __int64, __int64)`
- caller_count: `5`
- callee_count: `35`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002b8dc`
- `0x18002c304`
- `0x18002c4e0`
- `0x18002c700`
- `0x18002cbc0`

## callees

- `0x180003c84`
- `0x180004a38`
- `0x180006b40`
- `0x180007df0`
- `0x18000b010`
- `0x180017d60`
- `0x180027ff4`
- `0x180028038`
- `0x18002ccf8`
- `0x18002e250`
- `0x18002e3e0`
- `0x180046000`
- `0x1800483f8`
- `0x180048568`
- `0x18004858c`
- `0x1800485d4`
- `0x180049c70`
- `0x18004c700`
- `0x180052c34`
- `0x180054104`
- `0x180058a6c`
- `0x180058c0c`
- `0x18006a1e0`
- `0x18006cf64`
- `0x180078b10`
- `0x18007b300`
- `0x18007de6c`
- `0x180092db4`
- `0x18009332c`
- `0x1800bb480`
- `0x1800bc094`
- `0x1800ccc94`
- `0x1800ead00`
- `0x1800f0438`
- `0x180262020`

## import_xrefs

- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-0!__imp_D3DKMTCreateSynchronizationObject2` at `0x18002dde5`
- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-0!__imp_D3DKMTCreateKeyedMutex2` at `0x18002dd90`

## string_xrefs

- `0x18002ddde`: `CreateKeyedMutexFence`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CDevice::CreateTestResourceAndHeap_Worker<enum D3D12_RESOURCE_STATES>(
        CDevice *this,
        CHeap *a2,
        __int16 a3,
        _BYTE *a4,
        int a5,
        __int64 a6,
        __int64 a7,
        struct CD3DX12_RESOURCE_DESC2 *a8,
        int *a9,
        char a10,
        int a11,
        __int64 a12,
        void *a13,
        __int64 a14,
        __int64 a15,
        int a16,
        int a17,
        __int64 a18,
        _QWORD *a19,
        __int64 a20,
        _QWORD *a21)
{
  char v23; // si
  struct CD3DX12_RESOURCE_DESC2 *v24; // r14
  CHeap *v25; // r8
  bool v26; // di
  enum D3D12_TIGHT_ALIGNMENT_TIER v27; // eax
  const struct CD3DX12_RESOURCE_DESC2 *v28; // rax
  __int64 v29; // rcx
  __int64 v30; // rax
  __int16 v31; // cx
  __int16 v32; // ax
  CHeap *v33; // r8
  __int64 v34; // r9
  int v35; // eax
  __int64 *v36; // rcx
  int v37; // eax
  int v38; // eax
  char IsEnabled; // al
  int v40; // eax
  unsigned int v41; // ecx
  int v42; // eax
  int v43; // r8d
  struct D3D12_HEAP_PROPERTIES *CustomHeapProperties; // rax
  unsigned int v45; // eax
  int v46; // edi
  UINT64 Alignment; // r8
  __int64 v48; // rax
  bool v49; // di
  __int64 v50; // rdx
  int v51; // esi
  unsigned int v52; // edi
  struct D3D12_RESOURCE_ALLOCATION_INFO *v53; // rax
  UINT64 v54; // r10
  UINT64 SizeInBytes; // rdx
  __int64 v56; // r8
  __int128 *v57; // r12
  char v58; // cl
  unsigned int v59; // eax
  __int64 v60; // rcx
  int v61; // edx
  int v62; // eax
  char v63; // cl
  __int128 v64; // xmm2
  char v65; // bl
  __int64 v66; // r8
  UINT64 *v67; // rcx
  UINT64 v68; // rax
  UINT64 v69; // rax
  bool v70; // zf
  char v71; // r9
  int v72; // r8d
  int v73; // eax
  int *v74; // r12
  __int64 v75; // rdx
  int v76; // ebx
  int v77; // r11d
  int v78; // r10d
  int v79; // r9d
  int v80; // edx
  int v81; // r8d
  int v82; // eax
  int v83; // esi
  int v84; // ebx
  int v85; // r10d
  int v86; // edi
  int v87; // r11d
  int v88; // r8d
  int v89; // r9d
  int v90; // edx
  int v91; // r11d
  int v92; // r10d
  int v93; // r9d
  int v94; // edx
  int v95; // r8d
  int v96; // r9d
  int v97; // edx
  int v98; // ecx
  int v99; // eax
  int v100; // ebx
  __int64 v101; // rdx
  __int64 v102; // r8
  unsigned int v103; // eax
  int v104; // eax
  int v105; // ebx
  unsigned int v106; // eax
  int v107; // eax
  int v108; // ebx
  __int64 v109; // rbx
  int v110; // esi
  int v111; // r8d
  _QWORD *v112; // rbx
  int v113; // ecx
  unsigned int v114; // eax
  __int64 v115; // rcx
  __int64 v116; // rcx
  int v117; // eax
  int v118; // eax
  int v119; // eax
  __int64 result; // rax
  __int64 v121; // [rsp+20h] [rbp-778h]
  __int64 v122; // [rsp+30h] [rbp-768h]
  int v123; // [rsp+40h] [rbp-758h]
  char v124; // [rsp+60h] [rbp-738h]
  CHeap *v125; // [rsp+68h] [rbp-730h] BYREF
  int v126; // [rsp+70h] [rbp-728h] BYREF
  int v127; // [rsp+74h] [rbp-724h]
  int v128; // [rsp+78h] [rbp-720h]
  unsigned int v129; // [rsp+7Ch] [rbp-71Ch]
  void *v130; // [rsp+80h] [rbp-718h]
  int v131; // [rsp+88h] [rbp-710h]
  int v132; // [rsp+8Ch] [rbp-70Ch]
  int v133; // [rsp+90h] [rbp-708h]
  void *v134; // [rsp+98h] [rbp-700h] BYREF
  __int64 v135; // [rsp+A0h] [rbp-6F8h]
  int *v136; // [rsp+A8h] [rbp-6F0h]
  _QWORD *v137; // [rsp+B0h] [rbp-6E8h]
  _QWORD *v138; // [rsp+B8h] [rbp-6E0h]
  __int64 v139; // [rsp+C0h] [rbp-6D8h]
  _QWORD *v140; // [rsp+C8h] [rbp-6D0h]
  _QWORD *v141; // [rsp+D0h] [rbp-6C8h]
  _BYTE *v142; // [rsp+D8h] [rbp-6C0h]
  __int64 v143; // [rsp+E0h] [rbp-6B8h]
  __int64 v144; // [rsp+E8h] [rbp-6B0h]
  __int64 v145; // [rsp+F0h] [rbp-6A8h]
  __int64 v146; // [rsp+F8h] [rbp-6A0h]
  __int128 v147; // [rsp+100h] [rbp-698h] BYREF
  _com_error *v148; // [rsp+110h] [rbp-688h] BYREF
  __int128 v149; // [rsp+120h] [rbp-678h] BYREF
  __int128 v150; // [rsp+130h] [rbp-668h]
  __int128 v151; // [rsp+140h] [rbp-658h]
  __int128 v152; // [rsp+150h] [rbp-648h]
  int v153; // [rsp+160h] [rbp-638h]
  int v154; // [rsp+164h] [rbp-634h]
  int v155; // [rsp+170h] [rbp-628h]
  int v156; // [rsp+178h] [rbp-620h]
  _BYTE v157[24]; // [rsp+180h] [rbp-618h] BYREF
  int v158; // [rsp+198h] [rbp-600h]
  int v159; // [rsp+19Ch] [rbp-5FCh]
  int v160; // [rsp+1A0h] [rbp-5F8h]
  __int128 *v161; // [rsp+1A8h] [rbp-5F0h]
  _BYTE *v162; // [rsp+1B8h] [rbp-5E0h]
  _BYTE v163[48]; // [rsp+1F0h] [rbp-5A8h] BYREF
  UINT64 v164; // [rsp+220h] [rbp-578h]
  __int128 *v165; // [rsp+228h] [rbp-570h]
  _DWORD *v166; // [rsp+238h] [rbp-560h]
  int v167; // [rsp+240h] [rbp-558h]
  int v168; // [rsp+270h] [rbp-528h]
  char v169; // [rsp+274h] [rbp-524h]
  __int16 v170; // [rsp+275h] [rbp-523h]
  void *v171; // [rsp+278h] [rbp-520h]
  int v172; // [rsp+2B4h] [rbp-4E4h]
  char v173[48]; // [rsp+300h] [rbp-498h] BYREF
  _DWORD v174[2]; // [rsp+330h] [rbp-468h] BYREF
  __int64 v175; // [rsp+338h] [rbp-460h]
  __int128 v176; // [rsp+340h] [rbp-458h] BYREF
  _BYTE v177[48]; // [rsp+350h] [rbp-448h]
  __int128 v178; // [rsp+390h] [rbp-408h] BYREF
  __int64 v179; // [rsp+3A0h] [rbp-3F8h]
  __int64 v180; // [rsp+3A8h] [rbp-3F0h]
  int v181; // [rsp+3B0h] [rbp-3E8h]
  __int64 v182; // [rsp+3B4h] [rbp-3E4h]
  int v183; // [rsp+3BCh] [rbp-3DCh]
  int v184; // [rsp+3C0h] [rbp-3D8h]
  BOOL v185; // [rsp+3C4h] [rbp-3D4h]
  int v186; // [rsp+3C8h] [rbp-3D0h]
  int v187; // [rsp+3CCh] [rbp-3CCh]
  BOOL v188; // [rsp+3D0h] [rbp-3C8h]
  BOOL v189; // [rsp+3D4h] [rbp-3C4h]
  BOOL v190; // [rsp+3D8h] [rbp-3C0h]
  unsigned int v191; // [rsp+3DCh] [rbp-3BCh]
  int v192; // [rsp+3E0h] [rbp-3B8h]
  int v193; // [rsp+3E4h] [rbp-3B4h]
  int v194; // [rsp+3E8h] [rbp-3B0h]
  int v195; // [rsp+3ECh] [rbp-3ACh]
  int v196; // [rsp+3F0h] [rbp-3A8h]
  int v197; // [rsp+3F4h] [rbp-3A4h]
  int v198; // [rsp+3F8h] [rbp-3A0h]
  int v199; // [rsp+3FCh] [rbp-39Ch]
  int v200; // [rsp+400h] [rbp-398h]
  int v201; // [rsp+404h] [rbp-394h]
  int v202; // [rsp+408h] [rbp-390h]
  int v203; // [rsp+40Ch] [rbp-38Ch]
  int v204; // [rsp+410h] [rbp-388h]
  __int64 v205; // [rsp+414h] [rbp-384h]
  __int64 v206; // [rsp+420h] [rbp-378h]
  enum D3D12_HEAP_TYPE v207; // [rsp+428h] [rbp-370h]
  __int64 v208; // [rsp+42Ch] [rbp-36Ch]
  unsigned int v209; // [rsp+434h] [rbp-364h]
  int v210; // [rsp+438h] [rbp-360h]
  int v211; // [rsp+43Ch] [rbp-35Ch]
  __int64 v212; // [rsp+440h] [rbp-358h]
  int v213; // [rsp+448h] [rbp-350h]
  int v214; // [rsp+44Ch] [rbp-34Ch]
  int v215; // [rsp+450h] [rbp-348h]
  int v216; // [rsp+458h] [rbp-340h]
  int v217; // [rsp+45Ch] [rbp-33Ch]
  int v218; // [rsp+460h] [rbp-338h]
  __int128 v219; // [rsp+468h] [rbp-330h]
  __int128 v220; // [rsp+478h] [rbp-320h]
  __int128 v221; // [rsp+488h] [rbp-310h]
  __int128 v222; // [rsp+498h] [rbp-300h]
  __int128 v223; // [rsp+4A8h] [rbp-2F0h]
  int v224; // [rsp+4B8h] [rbp-2E0h]
  __int128 v225; // [rsp+4C0h] [rbp-2D8h]
  __int128 v226; // [rsp+4D0h] [rbp-2C8h]
  __int128 v227; // [rsp+4E0h] [rbp-2B8h]
  __int128 v228; // [rsp+4F0h] [rbp-2A8h]
  __int64 v229; // [rsp+500h] [rbp-298h]
  __int128 v230; // [rsp+510h] [rbp-288h] BYREF
  __int128 v231; // [rsp+520h] [rbp-278h]
  __int128 v232; // [rsp+530h] [rbp-268h]
  __int128 v233; // [rsp+540h] [rbp-258h]
  __int128 v234; // [rsp+550h] [rbp-248h]
  _DWORD v235[20]; // [rsp+560h] [rbp-238h] BYREF
  char v236[272]; // [rsp+5B0h] [rbp-1E8h] BYREF
  char v237[48]; // [rsp+6C0h] [rbp-D8h] BYREF
  __int64 v238; // [rsp+6F0h] [rbp-A8h] BYREF
  enum D3D12_HEAP_TYPE v239; // [rsp+6F8h] [rbp-A0h]
  __int64 v240; // [rsp+6FCh] [rbp-9Ch]
  unsigned int v241; // [rsp+704h] [rbp-94h]
  int v242; // [rsp+708h] [rbp-90h]
  __int64 v243; // [rsp+710h] [rbp-88h]
  int v244; // [rsp+718h] [rbp-80h]
  __int64 v245; // [rsp+720h] [rbp-78h]
  D3D12_HEAP_TYPE Type; // [rsp+728h] [rbp-70h]
  int CPUPageProperty; // [rsp+72Ch] [rbp-6Ch]
  int MemoryPoolPreference; // [rsp+730h] [rbp-68h]
  unsigned int v249; // [rsp+734h] [rbp-64h]
  int v250; // [rsp+738h] [rbp-60h]
  int v251; // [rsp+748h] [rbp-50h]
  _QWORD v252[9]; // [rsp+750h] [rbp-48h] BYREF

  v142 = a4;
  v125 = a2;
  v23 = a10;
  v135 = a6;
  v24 = a8;
  v136 = a9;
  v131 = a11;
  v143 = a12;
  v130 = a13;
  v144 = a14;
  v145 = a15;
  v139 = a18;
  v138 = a19;
  v140 = a19;
  v146 = a20;
  v137 = a21;
  v141 = a21;
  if ( a19 )
    *a19 = 0;
  if ( a21 )
    *a21 = 0;
  memset_0(&v230, 0, 0x50u);
  v25 = v125;
  if ( a8 && v125 )
  {
    v26 = 1;
    v124 = 1;
    goto LABEL_9;
  }
  v26 = 0;
  v124 = 0;
  if ( a8 )
  {
LABEL_9:
    v27 = CDevice::TightAlignmentTier(this);
    v28 = D3DX12ConditionallyExpandAPIDesc(
            (struct CD3DX12_RESOURCE_DESC2 *)&v230,
            a8,
            v27 >= D3D12_TIGHT_ALIGNMENT_TIER_1,
            v26);
    v24 = v28;
    v25 = v125;
    if ( !v125 )
      goto LABEL_193;
    goto LABEL_15;
  }
  v124 = 0;
  if ( !v125 )
    goto LABEL_193;
  v29 = *(_QWORD *)v125;
  v30 = *((_QWORD *)v125 + 4);
  if ( !v30 )
    v30 = 0x10000;
  LODWORD(v176) = 1;
  *((_QWORD *)&v176 + 1) = v30;
  *(_QWORD *)v177 = v29;
  *(_DWORD *)&v177[8] = 1;
  *(_QWORD *)&v177[12] = 65537;
  *(_QWORD *)&v177[20] = 1;
  *(_OWORD *)&v177[28] = 1u;
  *(_DWORD *)&v177[44] = 0;
  v230 = v176;
  v231 = *(_OWORD *)v177;
  v232 = *(_OWORD *)&v177[16];
  v233 = *(_OWORD *)&v177[32];
  v234 = 0;
  v24 = (struct CD3DX12_RESOURCE_DESC2 *)&v230;
  v23 = a10 | 2;
  v124 = 0;
LABEL_15:
  if ( (*((_BYTE *)v25 + 40) & 1) != 0 && (a3 & 6) == 0 )
    a3 |= 2u;
LABEL_193:
  try
  {
    if ( a7 )
      goto LABEL_23;
    if ( !v25 )
      goto LABEL_69;
    if ( (*((_BYTE *)v25 + 40) & 8) != 0 )
    {
LABEL_23:
      v31 = a3 | 0x280;
      a3 |= 0x282u;
      if ( (v31 & 6) != 0 )
        a3 = v31;
      if ( !v25 )
      {
LABEL_69:
        v46 = a3 & 4;
        v127 = v46;
        v133 = a3 & 8;
        v132 = a3 & 0x10;
        v126 = a3 & 0x200;
        v129 = (v132 != 0 ? 0x10 : 0)
             | (v126 != 0 ? 0x200 : 0)
             | (v46 != 0 ? 4 : 0)
             | (v133 != 0 ? 8 : 0)
             | a3 & 0x582
             | ((unsigned __int16)(a3 & 0x4000) >> 2);
        v128 = v137 == 0 ? 0x10000000 : 0;
        CLayeredResourceCreationArgs::CLayeredResourceCreationArgs((CLayeredResourceCreationArgs *)v163);
        if ( !v24 )
        {
          v51 = 33;
          goto LABEL_87;
        }
        v123 = v23 & 2;
        HIDWORD(v122) = HIDWORD(v24);
        HIDWORD(v121) = HIDWORD(v135);
        v48 = CLayeredResourceCreationArgs::CLayeredResourceCreationArgs(v236, this, v142);
        CLayeredResourceCreationArgs::operator=(v163, v48);
        std::vector<enum DXGI_FORMAT>::_Tidy(v237);
        if ( v125 )
        {
          v49 = 0;
          v50 = *((unsigned int *)v125 + 6);
        }
        else
        {
          if ( v142 )
          {
            v50 = *(unsigned int *)((*(__int64 (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v142 + 64LL))(v142, v157)
                                  + 24);
            v51 = 33;
            v49 = (v142[224] & 6) != 0 || (v142[220] & 0x21) != 0;
            goto LABEL_79;
          }
          v50 = (unsigned int)(1LL << ((__int64)(unsigned int)(*((_DWORD *)this + 1402) - *((_DWORD *)this + 1400)) >> 2))
              - 1;
          v49 = 1;
        }
        v51 = 33;
LABEL_79:
        v149 = 0;
        v150 = 0;
        v151 = 0;
        LOBYTE(v123) = v124;
        LODWORD(v122) = 0;
        LODWORD(v121) = CDevice::TranslateNodeMask(this, v50, 0);
        v52 = CDevice::VersionedCheckResourceAllocationInfo(this, &v149, v24, v129, v121, v49, v122, 0, v123);
        v168 = DWORD2(v151);
        v172 = DWORD1(v151);
        v169 = BYTE12(v151);
        v170 = *(_WORD *)((char *)&v151 + 13);
        if ( (unsigned __int64)v149 >= 0xFFFFFFFFFFC00000uLL )
          ThrowFailure(-2147024882);
        v53 = DDIRAIToAPIRAI(
                (struct D3D12_RESOURCE_ALLOCATION_INFO *)v157,
                (const struct D3D12DDI_RESOURCE_ALLOCATION_INFO_0022 *)&v149,
                v52);
        SizeInBytes = v53->SizeInBytes;
        Alignment = v53->Alignment;
        if ( (*((_DWORD *)v24 + 12) & 0x400) != 0 )
        {
          v230 = *(_OWORD *)v24;
          v231 = *((_OWORD *)v24 + 1);
          v232 = *((_OWORD *)v24 + 2);
          v233 = *((_OWORD *)v24 + 3);
          v234 = *((_OWORD *)v24 + 4);
          *((_QWORD *)&v230 + 1) = Alignment;
          v24 = (struct CD3DX12_RESOURCE_DESC2 *)&v230;
          v165 = &v230;
        }
        if ( v142 || v125 )
        {
          v164 = SizeInBytes;
          if ( v125 )
          {
            v67 = (UINT64 *)&v238;
            do
            {
              v68 = *v67;
              if ( !*v67 )
                v68 = SizeInBytes;
              *v67 = v68;
              v69 = v67[4];
              if ( !v69 )
                v69 = Alignment;
              v67[4] = v69;
              v67 += 6;
            }
            while ( v67 != v252 );
          }
        }
        else
        {
          v164 = v54;
        }
        v46 = v127;
LABEL_87:
        *(_QWORD *)&v149 = &std::_Func_impl_no_alloc<_lambda_d025a5101352581dddc785c0b96b6911_,void,unsigned int>::`vftable';
        *((_QWORD *)&v152 + 1) = &v149;
        SafeKMTHandle::SafeKMTHandle(&v176, &v149, Alignment);
        *(_QWORD *)v157 = &std::_Func_impl_no_alloc<_lambda_767f222b9673f51dc202691d3fe8ac08_,void,unsigned int>::`vftable';
        v162 = v157;
        SafeKMTHandle::SafeKMTHandle(v235, v157, v56);
        v178 = 0;
        v179 = 0;
        v204 = 72;
        v205 = 6;
        v216 = 104;
        v217 = 6;
        v218 = 1;
        LODWORD(v180) = 104;
        v225 = 0;
        v226 = 0;
        v227 = 0;
        v228 = 0;
        v229 = 0;
        v57 = 0;
        v134 = 0;
        if ( !v125 || (v251 & 1) == 0 )
        {
LABEL_163:
          v171 = v130;
          v109 = v144 + 192;
          if ( !v144 )
            v109 = 0;
          if ( v125 )
          {
            if ( (*((_BYTE *)v125 + 40) & 0x20) != 0 )
            {
              CPUPageProperty = 2;
              MemoryPoolPreference = 1;
            }
            v244 &= 0xFFFFE7FF;
            v110 = CDevice::TranslateNodeMask(this, *((unsigned int *)v125 + 5), 1);
            v111 = CDevice::TranslateNodeMask(this, *((unsigned int *)v125 + 6), 0);
            *(_QWORD *)&v149 = v109;
            *((_QWORD *)&v149 + 1) = &GUID_NULL;
            v150 = 0u;
            v151 = 0u;
            v112 = v137;
            LOBYTE(v152) = v137 == 0;
            *(_DWORD *)((char *)&v152 + 1) = 0;
            *(_WORD *)((char *)&v152 + 5) = 0;
            BYTE7(v152) = 0;
            *((_QWORD *)&v152 + 1) = v145;
            v113 = -1;
            v154 = 0;
            if ( a7 )
            {
              v153 = *(_DWORD *)(a7 + 4);
            }
            else
            {
              if ( (v251 & 8) != 0 )
                v113 = 0;
              v153 = v113;
            }
            v114 = *((_DWORD *)v125 + 5);
            if ( !v114 )
              v114 = 1;
            _BitScanForward((unsigned int *)&v115, v114);
            v116 = *(unsigned int *)(*((_QWORD *)this + 700) + 4 * v115);
            CLayeredHeapCreationArgs::CLayeredHeapCreationArgs(
              v157,
              (char *)this + 792,
              &v238,
              v129 | v128,
              *((_DWORD *)this + 359),
              (char *)this + 16 * v116 + 4 * v116 + 792,
              v163,
              &v149,
              v110,
              v111);
            v206 = v238;
            v207 = v239;
            v208 = v240;
            v209 = v241;
            v210 = v242;
            v211 = HIDWORD(v150);
            v212 = v243;
            v213 = v244;
            v214 = HIDWORD(v151);
            v215 = v160;
            v161 = v57;
            v125 = 0;
            v117 = (*(__int64 (__fastcall **)(_QWORD, __int64, _BYTE *, __int64, _QWORD, GUID *, CHeap **))(**((_QWORD **)this + 86) + 72LL))(
                     *((_QWORD *)this + 86),
                     8,
                     v157,
                     72,
                     0,
                     &GUID_ffffffff_335a_4bc5_9de9_43d8fb7777ae,
                     &v125);
            ThrowFailure(v117);
            if ( v138 )
              v118 = (***(__int64 (__fastcall ****)(_QWORD, __int64))(*((_QWORD *)v125 + 32) + 144LL))(
                       *(_QWORD *)(*((_QWORD *)v125 + 32) + 144LL),
                       v139);
            else
              v118 = (***((__int64 (__fastcall ****)(_QWORD, __int64, _QWORD *))v125 + 18))(
                       *((_QWORD *)v125 + 18),
                       v146,
                       v112);
            ThrowFailure(v118);
            if ( v185 )
              CHeap::SetKeyedMutexHandles((_DWORD)v125, (unsigned int)&v176, (unsigned int)v235, v186, v187);
            CHeap::CompleteDependencyGraph(v125);
            ATL::CComPtrBase<CApplicationIdentity>::~CComPtrBase<CApplicationIdentity>(&v125);
          }
          else
          {
            v119 = (*(__int64 (__fastcall **)(_QWORD, __int64, _BYTE *, __int64, __int64, __int64, _QWORD *))(**((_QWORD **)this + 86) + 72LL))(
                     *((_QWORD *)this + 86),
                     5,
                     v163,
                     144,
                     v109,
                     v139,
                     v138);
            ThrowFailure(v119);
          }
          ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(&v134);
          SD3D12SharedResourceCreationArgs::~SD3D12SharedResourceCreationArgs((SD3D12SharedResourceCreationArgs *)&v178);
          SafeKMTHandle::~SafeKMTHandle((SafeKMTHandle *)v235);
          SafeKMTHandle::~SafeKMTHandle((SafeKMTHandle *)&v176);
          std::vector<enum DXGI_FORMAT>::_Tidy(v173);
          return 0;
        }
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12Displayable>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_D3D12Displayable>::GetImpl'::`2'::impl);
        v188 = v46 == 0;
        v190 = v132 != 0;
        v185 = v133 != 0;
        v189 = v126 != 0;
        if ( a3 < 0 )
          v189 = 0;
        v70 = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12Displayable>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_D3D12Displayable>::GetImpl'::`2'::impl) == 0;
        v58 = v251;
        if ( v70 )
          v58 = v244;
        v191 = v191 & 0xFFFFFFFE | ((unsigned __int8)(v58 & 8) >> 3);
        v184 = 0;
        v180 = 104;
        v182 = 0;
        v181 = 0;
        v59 = *((_DWORD *)v125 + 5);
        if ( !v59 )
          v59 = 1;
        v126 = 0;
        _BitScanForward((unsigned int *)&v60, v59);
        v61 = *((_DWORD *)v24 + 12);
        if ( (v61 & 0xAC0) != 0
          || CPUPageProperty != 1
          || (v62 = 2 - (*((_DWORD *)this + 5 * *(unsigned int *)(*((_QWORD *)this + 700) + 4 * v60) + 198) != 0),
              v63 = 1,
              MemoryPoolPreference != v62) )
        {
          v63 = 0;
        }
        LODWORD(v149) = *(_DWORD *)v24;
        *((_QWORD *)&v149 + 1) = *((_QWORD *)v24 + 1);
        v150 = *((_OWORD *)v24 + 1);
        v151 = *((_OWORD *)v24 + 2);
        LODWORD(v152) = v61;
        *(_QWORD *)((char *)&v152 + 4) = *(_QWORD *)((char *)v24 + 52);
        HIDWORD(v152) = *((_DWORD *)v24 + 15);
        v64 = *((_OWORD *)v24 + 4);
        v219 = v149;
        v220 = v150;
        v221 = v151;
        v222 = v152;
        v223 = v64;
        v224 = v167;
        if ( !v63 )
          goto LABEL_161;
        if ( *(_DWORD *)v24 != 3 || *((_WORD *)v24 + 15) != 1 || (v65 = 1, *((_DWORD *)v24 + 9) != 1) )
          v65 = 0;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12Displayable>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_D3D12Displayable>::GetImpl'::`2'::impl) )
        {
          if ( v65 && (*((_BYTE *)v24 + 48) & 0xE) == 0 && (*((_BYTE *)v24 + 48) & 0x11) != 0 )
            goto LABEL_120;
        }
        else if ( v65 && (*((_DWORD *)v24 + 12) & 0xF) == 1 )
        {
LABEL_120:
          LOBYTE(v66) = *((_BYTE *)this + 712);
          if ( (unsigned __int8)IsCrossApiShareableFormat(
                                  *((unsigned int *)v24 + 8),
                                  *((unsigned int *)this + 363),
                                  v66) )
          {
            v181 = *((_DWORD *)v24 + 4);
            LODWORD(v182) = *((_DWORD *)v24 + 6);
            HIDWORD(v182) = *((_DWORD *)v24 + 8);
            v183 = *((unsigned __int16 *)v24 + 14);
          }
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12Displayable>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_D3D12Displayable>::GetImpl'::`2'::impl) )
          v70 = *((_BYTE *)this + 1491) == 0;
        else
          v70 = *((_BYTE *)this + 1489) == 0;
        if ( !v70 && (v191 & 1) != 0 && v65 )
        {
          v71 = 1;
          v51 = 0;
        }
        else
        {
          v71 = 0;
        }
        v174[0] = (v71 != 0 ? 0x600 : 0) | (32 * (*((_DWORD *)v24 + 12) & 4)) | (32 * (*((_DWORD *)v24 + 12) & 1)) | 8;
        v72 = (v185 ? 256 : 2) | (v188 ? 0x800 : 0) | (v130 != 0 ? 0x80000 : 0);
        if ( v71 )
        {
          if ( (*((_BYTE *)v24 + 48) & 0x20) == 0 )
            v72 |= 0x200000u;
          v73 = 0x100000;
        }
        else
        {
          v73 = 0;
        }
        v174[1] = v73 | v72;
        v175 = 0;
        v74 = v136;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12Displayable>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_D3D12Displayable>::GetImpl'::`2'::impl) )
        {
          if ( v136 )
          {
            if ( !*((_BYTE *)this + 1491) || (v191 & 1) == 0 )
            {
              v147 = *(_OWORD *)v136;
              DWORD1(v147) &= ~0x100000u;
              v74 = (int *)&v147;
            }
LABEL_148:
            HIDWORD(v180) = 4;
            if ( *(_DWORD *)v24 != 1 )
            {
              if ( *(_DWORD *)v24 == 2 )
              {
                v192 = 2;
                v91 = v74[1];
                v92 = v74[2];
                v93 = *v74;
                v94 = *((unsigned __int16 *)v24 + 14);
                v95 = *((_DWORD *)v24 + 8);
                v82 = *((_DWORD *)v24 + 4);
                v194 = *((unsigned __int16 *)v24 + 15);
                v195 = v94;
                v196 = v95;
                v197 = 0;
                v198 = v93;
                v199 = v92;
                v200 = v91;
              }
              else
              {
                if ( *(_DWORD *)v24 != 3 )
                {
                  v192 = 4;
                  v76 = v74[1];
                  v77 = v74[2];
                  v78 = *v74;
                  v79 = *((unsigned __int16 *)v24 + 15);
                  v80 = *((unsigned __int16 *)v24 + 14);
                  v81 = *((_DWORD *)v24 + 8);
                  v82 = *((_DWORD *)v24 + 4);
                  v194 = *((_DWORD *)v24 + 6);
                  v195 = v80;
                  v196 = v79;
                  v198 = 0;
                  v199 = v78;
                  v200 = v77;
                  v201 = v76;
LABEL_155:
                  v197 = v81;
                  goto LABEL_156;
                }
                v192 = 3;
                v83 = v74[1];
                v84 = *((_DWORD *)v24 + 10);
                v85 = *((_DWORD *)v24 + 9);
                v86 = v74[2];
                v87 = *v74;
                v88 = *((unsigned __int16 *)v24 + 15);
                v89 = *((unsigned __int16 *)v24 + 14);
                v90 = *((_DWORD *)v24 + 8);
                v82 = *((_DWORD *)v24 + 4);
                v194 = *((_DWORD *)v24 + 6);
                v195 = v88;
                v196 = v89;
                v197 = v90;
                v198 = v85;
                v199 = v84;
                v200 = 0;
                v201 = v87;
                v202 = v86;
                v203 = v83;
              }
LABEL_156:
              v193 = v82;
              if ( !v130
                && (v74[1] & 0x80000) != 0
                && CDevice::EnsureContentProtectionSupported(this)
                && (**((_BYTE **)this + 929) & 1) != 0 )
              {
                *(_QWORD *)v157 = 0;
                *(_OWORD *)&v157[8] = D3D12_PROTECTED_RESOURCES_SESSION_HARDWARE_PROTECTED;
                v99 = CDevice::CreateProtectedResourceSessionImpl(
                        this,
                        (const struct D3D12_PROTECTED_RESOURCE_SESSION_DESC1 *)v157,
                        &GUID_ffffffff_335a_4bc5_9de9_43d8fb7777ae,
                        &v134);
                ThrowFailure(v99);
                v130 = v134;
              }
              goto LABEL_161;
            }
            v192 = 1;
            v96 = v74[3];
            v81 = v74[1];
            v97 = v74[2];
            v98 = *v74;
            v82 = *((_DWORD *)v24 + 4);
            v194 = 0;
            v195 = v98;
            v196 = v97;
            v198 = v96;
            goto LABEL_155;
          }
        }
        else if ( v136 )
        {
          goto LABEL_148;
        }
        if ( v65 )
        {
          v75 = *((unsigned int *)this + 363);
          if ( (int)v75 >= 7
            && (unsigned __int8)CD3D11FormatHelper::IsCrossD3DAPIShareableFormat(*((unsigned int *)v24 + 8), v75)
            && !*((_DWORD *)v24 + 11)
            && (*((_DWORD *)v24 + 12) & v51) == v51
            && (*((_BYTE *)v24 + 48) & 0x1A) == 0 )
          {
            v74 = v174;
            v166 = v174;
            goto LABEL_148;
          }
        }
LABEL_161:
        v57 = &v178;
        if ( v185 )
        {
          v126 = 0;
          *(_QWORD *)v157 = 0;
          *(_QWORD *)&v157[8] = 0;
          v100 = v188;
          v159 = v100;
          *(_QWORD *)&v157[16] = &v126;
          v158 = 4;
          memset_0(&v149, 0, 0x60u);
          LODWORD(v149) = *(_DWORD *)(*((_QWORD *)this + 95) + 56LL);
          DWORD2(v149) = 3;
          HIDWORD(v149) = (2 * v100) | 1;
          v103 = CallAndLogImpl<long (*)(_D3DKMT_CREATEKEYEDMUTEX2 *),_D3DKMT_CREATEKEYEDMUTEX2 *>(
                   D3DKMTCreateKeyedMutex2,
                   v101,
                   v102,
                   v157);
          v104 = NDXGI::CDevice::NTStatusToHResult(*((_QWORD *)this + 95), v103, 1);
          ThrowFailure(v104);
          v105 = *(_DWORD *)&v157[12];
          SafeKMTHandle::Release((SafeKMTHandle *)&v176);
          LODWORD(v176) = v105;
          v106 = CallAndLogImpl<long (*)(D3DDDI_DESTROYPAGINGQUEUE *),D3DDDI_DESTROYPAGINGQUEUE *>(
                   D3DKMTCreateSynchronizationObject2,
                   "CreateKeyedMutexFence",
                   CLayeredObject<CCommandAllocator>::AddRef,
                   &v149);
          v107 = NDXGI::CDevice::NTStatusToHResult(*((_QWORD *)this + 95), v106, 1);
          ThrowFailure(v107);
          v108 = v156;
          SafeKMTHandle::Release((SafeKMTHandle *)v235);
          v235[0] = v108;
          v186 = *(_DWORD *)&v157[8];
          v187 = v155;
        }
        goto LABEL_163;
      }
    }
    v32 = a3 | 0x10;
    if ( (*((_BYTE *)v25 + 40) & 0x20) == 0 )
      v32 = a3;
    a3 = v32;
    v70 = (std::fill<D3D12_HEAP_DESC *,D3D12_HEAP_DESC>(&v238, v252) & 6) == 0;
    v35 = v251;
    if ( !v70 )
    {
      v35 = v251 | 1;
      v251 |= 1u;
    }
    if ( (a3 & 0x2000) != 0 )
      v251 = v35 | 0x200;
    if ( (a3 & 0x80u) != 0 )
      v244 |= 8u;
    v36 = &v238;
    do
    {
      v37 = 1;
      if ( *((_DWORD *)v36 + 6) != (_DWORD)v34 )
        v37 = *((_DWORD *)v36 + 6);
      *((_DWORD *)v36 + 6) = v37;
      v38 = 1;
      if ( *((_DWORD *)v36 + 5) != (_DWORD)v34 )
        v38 = *((_DWORD *)v36 + 5);
      *((_DWORD *)v36 + 5) = v38;
      v36 += 6;
    }
    while ( v36 != v252 );
    if ( (a3 & 0x200) == 0 )
    {
      v41 = v251;
LABEL_55:
      if ( (a3 & 0x100) != 0 && (*((_BYTE *)v33 + 40) & 0xC4) == 0 )
      {
        v43 = v34;
        if ( *(_DWORD *)v24 == 1 )
        {
          v43 = 192;
        }
        else if ( *(_DWORD *)v24 == 2 || (unsigned int)(*(_DWORD *)v24 - 3) <= 1 )
        {
          v43 = (*((_DWORD *)v24 + 12) & 3) != 0 ? 132 : 68;
        }
        v251 = v43 | v41;
        v244 |= v43;
      }
      if ( Type != D3D12_HEAP_TYPE_CUSTOM )
      {
        CustomHeapProperties = CDevice::GetCustomHeapProperties(this, (struct D3D12_HEAP_PROPERTIES *)v157, v241, v239);
        Type = CustomHeapProperties->Type;
        CPUPageProperty = CustomHeapProperties->CPUPageProperty;
        MemoryPoolPreference = CustomHeapProperties->MemoryPoolPreference;
        v45 = v241;
        v34 = 0;
        if ( !v241 )
          v45 = 1;
        v249 = v45;
        v250 = v242;
      }
      if ( (v23 & 2) != 0 )
        v245 = v34;
      goto LABEL_69;
    }
    v244 |= 8u;
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12Displayable>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_D3D12Displayable>::GetImpl'::`2'::impl);
    v34 = 0;
    if ( IsEnabled )
    {
      *(_DWORD *)v157 = *((_DWORD *)v24 + 8);
      *(_QWORD *)&v157[4] = 0;
      v40 = CDevice::CheckFeatureSupport(this, D3D12_FEATURE_FORMAT_SUPPORT, v157, 0xCu);
      v34 = 0;
      if ( (*((_BYTE *)this + 5316) || (a3 & 0x10) != 0)
        && *((_BYTE *)this + 1489)
        && v40 >= 0
        && ((*(_DWORD *)&v157[4] & 0x80000) != 0 || (*(_DWORD *)&v157[8] & 0x10000) != 0) )
      {
LABEL_46:
        v41 = v251 | 8;
LABEL_48:
        v251 = v41;
        v33 = v125;
        goto LABEL_55;
      }
    }
    else if ( *((_BYTE *)this + 5316) || (a3 & 0x10) != 0 )
    {
      if ( !*((_BYTE *)this + 1489) )
        goto LABEL_46;
      v42 = CD3D11FormatHelper::DisplayScanOutSupport(
              *((unsigned int *)v24 + 8),
              *((unsigned int *)this + 362),
              *((unsigned int *)this + 363),
              0);
      v34 = 0;
      if ( v42 == 1 )
        goto LABEL_46;
    }
    v41 = v251 & 0xFFFFFFF7;
    a3 &= ~0x200u;
    goto LABEL_48;
  }
  catch ( _com_error *v148 )
  {
    if ( v140 )
      *v140 = 0;
    if ( v141 )
      *v141 = 0;
    return *((unsigned int *)v148 + 2);
  }
  catch ( std::bad_alloc )
  {
    if ( v140 )
      *v140 = 0;
    if ( v141 )
      *v141 = 0;
    return 2147942414LL;
  }
  return result;
}

```

## disassembly

```asm
0x18002ccf8  push    rbx
0x18002ccfa  push    rsi
0x18002ccfb  push    rdi
0x18002ccfc  push    r12
0x18002ccfe  push    r13
0x18002cd00  push    r14
0x18002cd02  push    r15
0x18002cd04  sub     rsp, 760h
0x18002cd0b  mov     rax, cs:__security_cookie
0x18002cd12  xor     rax, rsp
0x18002cd15  mov     [rsp+798h+var_48], rax
0x18002cd1d  mov     [rsp+798h+var_6C0], r9
0x18002cd25  mov     ebx, r8d
0x18002cd28  mov     [rsp+798h+var_730], rdx
0x18002cd2d  mov     r13, rcx
0x18002cd30  mov     esi, dword ptr [rsp+798h+arg_48]
0x18002cd37  mov     rax, [rsp+798h+arg_28]
0x18002cd3f  mov     [rsp+798h+var_6F8], rax
0x18002cd47  mov     r14, [rsp+798h+arg_38]
0x18002cd4f  mov     r12, [rsp+798h+arg_40]
0x18002cd57  mov     [rsp+798h+var_6F0], r12
0x18002cd5f  mov     eax, [rsp+798h+arg_50]
0x18002cd66  mov     [rsp+798h+var_710], eax
0x18002cd6d  mov     rax, [rsp+798h+arg_58]
0x18002cd75  mov     [rsp+798h+var_6B8], rax
0x18002cd7d  mov     rax, [rsp+798h+arg_60]
0x18002cd85  mov     [rsp+798h+var_718], rax
0x18002cd8d  mov     rax, [rsp+798h+arg_68]
0x18002cd95  mov     [rsp+798h+var_6B0], rax
0x18002cd9d  mov     rax, [rsp+798h+arg_70]
0x18002cda5  mov     [rsp+798h+var_6A8], rax
0x18002cdad  mov     rax, [rsp+798h+arg_88]
0x18002cdb5  mov     [rsp+798h+var_6D8], rax
0x18002cdbd  mov     rax, [rsp+798h+arg_90]
0x18002cdc5  mov     [rsp+798h+var_6E0], rax
0x18002cdcd  mov     [rsp+798h+var_6D0], rax
0x18002cdd5  mov     rcx, [rsp+798h+arg_98]
0x18002cddd  mov     [rsp+798h+var_6A0], rcx
0x18002cde5  mov     rcx, [rsp+798h+arg_A0]
0x18002cded  mov     [rsp+798h+var_6E8], rcx
0x18002cdf5  mov     [rsp+798h+var_6C8], rcx
0x18002cdfd  test    rax, rax
0x18002ce00  jz      short loc_18002CE09
0x18002ce02  mov     qword ptr [rax], 0
0x18002ce09  test    rcx, rcx
0x18002ce0c  jz      short loc_18002CE15
0x18002ce0e  mov     qword ptr [rcx], 0
0x18002ce15  xor     edx, edx; Val
0x18002ce17  lea     r8d, [rdx+50h]; Size
0x18002ce1b  lea     rcx, [rsp+798h+var_288]; void *
0x18002ce23  call    memset_0
0x18002ce28  xor     r9d, r9d
0x18002ce2b  mov     r8, [rsp+798h+var_730]
0x18002ce30  test    r14, r14
0x18002ce33  jz      short loc_18002CE48
0x18002ce35  test    r8, r8
0x18002ce38  jz      short loc_18002CE48
0x18002ce3a  lea     r15d, [r9+1]
0x18002ce3e  mov     dil, r15b
0x18002ce41  mov     [rsp+798h+var_738], r15b
0x18002ce46  jmp     short loc_18002CE5B
0x18002ce48  mov     dil, r9b
0x18002ce4b  mov     [rsp+798h+var_738], r9b
0x18002ce50  mov     r15d, 1
0x18002ce56  test    r14, r14
0x18002ce59  jz      short loc_18002CE9B
0x18002ce5b  mov     rcx, r13; this
0x18002ce5e  call    ?TightAlignmentTier@CDevice@@QEBA?AW4D3D12_TIGHT_ALIGNMENT_TIER@@XZ; CDevice::TightAlignmentTier(void)
0x18002ce63  cmp     eax, r15d
0x18002ce66  setnl   r8b; bool
0x18002ce6a  mov     r9b, dil; bool
0x18002ce6d  mov     rdx, r14; struct CD3DX12_RESOURCE_DESC2 *
0x18002ce70  lea     rcx, [rsp+798h+var_288]; struct CD3DX12_RESOURCE_DESC2 *
0x18002ce78  call    ?D3DX12ConditionallyExpandAPIDesc@@YAPEBUCD3DX12_RESOURCE_DESC2@@AEAU1@PEBU1@_N2@Z; D3DX12ConditionallyExpandAPIDesc(CD3DX12_RESOURCE_DESC2 &,CD3DX12_RESOURCE_DESC2 const *,bool,bool)
0x18002ce7d  mov     r14, rax
0x18002ce80  mov     r8, [rsp+798h+var_730]
0x18002ce85  xor     r9d, r9d
0x18002ce88  mov     edi, 10000h
0x18002ce8d  test    r8, r8
0x18002ce90  jnz     loc_18002CF63
0x18002ce96  jmp     loc_18002CF71
0x18002ce9b  mov     [rsp+798h+var_738], r9b
0x18002cea0  mov     edi, 10000h
0x18002cea5  test    r8, r8
0x18002cea8  jz      loc_18002CF71
0x18002ceae  xorps   xmm2, xmm2
0x18002ceb1  mov     rcx, [r8]
0x18002ceb4  mov     rax, [r8+20h]
0x18002ceb8  test    rax, rax
0x18002cebb  cmovz   rax, rdi
0x18002cebf  mov     dword ptr [rsp+798h+var_458], r15d
0x18002cec7  mov     qword ptr [rsp+798h+var_458+8], rax
0x18002cecf  mov     qword ptr [rsp+798h+var_448], rcx
0x18002ced7  mov     dword ptr [rsp+798h+var_448+8], r15d
0x18002cedf  mov     qword ptr [rsp+798h+var_448+0Ch], 10001h
0x18002ceeb  mov     [rsp+798h+var_434], r15
0x18002cef3  mov     qword ptr [rsp+798h+var_42C], r15
0x18002cefb  mov     qword ptr [rsp+798h+var_42C+8], r9
0x18002cf03  mov     [rsp+798h+var_41C], r9d
0x18002cf0b  movaps  xmm0, [rsp+798h+var_458]
0x18002cf13  movaps  [rsp+798h+var_288], xmm0
0x18002cf1b  movaps  xmm1, [rsp+798h+var_448]
0x18002cf23  movaps  [rsp+798h+var_278], xmm1
0x18002cf2b  movaps  xmm0, xmmword ptr [rsp+360h]
0x18002cf33  movaps  [rsp+798h+var_268], xmm0
0x18002cf3b  movaps  xmm1, [rsp+798h+var_42C+4]
0x18002cf43  movaps  [rsp+798h+var_258], xmm1
0x18002cf4b  movaps  [rsp+798h+var_248], xmm2
0x18002cf53  lea     r14, [rsp+798h+var_288]
0x18002cf5b  or      esi, 2
0x18002cf5e  mov     [rsp+798h+var_738], r9b
0x18002cf63  test    [r8+28h], r15b
0x18002cf67  jz      short loc_18002CF71
0x18002cf69  test    bl, 6
0x18002cf6c  jnz     short loc_18002CF71
0x18002cf6e  or      ebx, 2
0x18002cf71  cmp     [rsp+798h+arg_30], r9
0x18002cf79  jnz     short loc_18002CF8B
0x18002cf7b  test    r8, r8
0x18002cf7e  jz      loc_18002D1F3
0x18002cf84  test    byte ptr [r8+28h], 8
0x18002cf89  jz      short loc_18002CFA5
0x18002cf8b  or      ebx, 280h
0x18002cf91  mov     ecx, ebx
0x18002cf93  or      ebx, 2
0x18002cf96  test    cl, 6
0x18002cf99  cmovnz  ebx, ecx
0x18002cf9c  test    r8, r8
0x18002cf9f  jz      loc_18002D1F3
0x18002cfa5  mov     eax, ebx
0x18002cfa7  or      eax, 10h
0x18002cfaa  test    byte ptr [r8+28h], 20h
0x18002cfaf  cmovz   eax, ebx
0x18002cfb2  mov     ebx, eax
0x18002cfb4  lea     rdx, [rsp+798h+var_48]
0x18002cfbc  lea     rcx, [rsp+798h+var_A8]
0x18002cfc4  call    ??$fill@PEAUD3D12_HEAP_DESC@@U1@@std@@YAXQEAUD3D12_HEAP_DESC@@0AEBU1@@Z; std::fill<D3D12_HEAP_DESC *,D3D12_HEAP_DESC>(D3D12_HEAP_DESC * const,D3D12_HEAP_DESC * const,D3D12_HEAP_DESC const &)
0x18002cfc9  test    al, 6
0x18002cfcb  mov     eax, [rsp+798h+var_50]
0x18002cfd2  jz      short loc_18002CFDE
0x18002cfd4  or      eax, r15d
0x18002cfd7  mov     [rsp+798h+var_50], eax
0x18002cfde  bt      ebx, 0Dh
0x18002cfe2  jnb     short loc_18002CFEF
0x18002cfe4  bts     eax, 9
0x18002cfe8  mov     [rsp+798h+var_50], eax
0x18002cfef  test    bl, bl
0x18002cff1  jns     short loc_18002CFFB
0x18002cff3  or      [rsp+798h+var_80], 8
0x18002cffb  lea     rcx, [rsp+798h+var_A8]
0x18002d003  mov     eax, r15d
0x18002d006  cmp     [rcx+18h], r9d
0x18002d00a  cmovnz  eax, [rcx+18h]
0x18002d00e  mov     [rcx+18h], eax
0x18002d011  mov     eax, r15d
0x18002d014  cmp     [rcx+14h], r9d
0x18002d018  cmovnz  eax, [rcx+14h]
0x18002d01c  mov     [rcx+14h], eax
0x18002d01f  add     rcx, 30h ; '0'
0x18002d023  lea     rax, [rsp+798h+var_48]
0x18002d02b  cmp     rcx, rax
0x18002d02e  jnz     short loc_18002D003
0x18002d030  bt      ebx, 9
0x18002d034  jnb     loc_18002D11E
0x18002d03a  or      [rsp+798h+var_80], 8
0x18002d042  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_D3D12Displayable@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_D3D12Displayable@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12Displayable> `wil::Feature<__WilFeatureTraits_Feature_D3D12Displayable>::GetImpl(void)'::`2'::impl
0x18002d049  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_D3D12Displayable@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12Displayable>::__private_IsEnabled(void)
0x18002d04e  xor     r9d, r9d
0x18002d051  test    al, al
0x18002d053  jz      loc_18002D0E6
0x18002d059  mov     eax, [r14+20h]
0x18002d05d  mov     dword ptr [rsp+798h+var_618], eax
0x18002d064  mov     qword ptr [rsp+798h+var_618+4], r9
0x18002d06c  mov     r9d, 0Ch; unsigned int
0x18002d072  lea     r8, [rsp+798h+var_618]; void *
0x18002d07a  lea     edx, [r9-9]; enum D3D12_FEATURE
0x18002d07e  mov     rcx, r13; this
0x18002d081  call    ?CheckFeatureSupport@CDevice@@UEAAJW4D3D12_FEATURE@@PEAXI@Z; CDevice::CheckFeatureSupport(D3D12_FEATURE,void *,uint)
0x18002d086  xor     r9d, r9d
0x18002d089  cmp     [r13+14C4h], r9b
0x18002d090  jnz     short loc_18002D097
0x18002d092  test    bl, 10h
0x18002d095  jz      short loc_18002D0CA
0x18002d097  cmp     [r13+5D1h], r9b
0x18002d09e  jz      short loc_18002D0CA
0x18002d0a0  shr     eax, 1Fh
0x18002d0a3  xor     al, r15b
0x18002d0a6  jz      short loc_18002D0CA
0x18002d0a8  test    dword ptr [rsp+798h+var_618+4], 80000h
0x18002d0b3  jnz     short loc_18002D0BE
0x18002d0b5  test    dword ptr [rsp+798h+var_618+8], edi
0x18002d0bc  jz      short loc_18002D0CA
0x18002d0be  mov     ecx, [rsp+798h+var_50]
0x18002d0c5  or      ecx, 8
0x18002d0c8  jmp     short loc_18002D0D8
0x18002d0ca  mov     ecx, [rsp+798h+var_50]
0x18002d0d1  and     ecx, 0FFFFFFF7h
0x18002d0d4  btr     ebx, 9
0x18002d0d8  mov     [rsp+798h+var_50], ecx
0x18002d0df  mov     r8, [rsp+798h+var_730]
0x18002d0e4  jmp     short loc_18002D125
0x18002d0e6  cmp     [r13+14C4h], r9b
0x18002d0ed  jnz     short loc_18002D0F4
0x18002d0ef  test    bl, 10h
0x18002d0f2  jz      short loc_18002D0CA
0x18002d0f4  cmp     [r13+5D1h], r9b
0x18002d0fb  jz      short loc_18002D0BE
0x18002d0fd  mov     r8d, [r13+5ACh]
0x18002d104  mov     edx, [r13+5A8h]
0x18002d10b  mov     ecx, [r14+20h]
0x18002d10f  call    ?DisplayScanOutSupport@CD3D11FormatHelper@@SA?AW4D3D11_REQUIREMENTS@@W4DXGI_FORMAT@@W4D3D_FEATURE_LEVEL@@W4eExtendedFormatFeatures@1@@Z; CD3D11FormatHelper::DisplayScanOutSupport(DXGI_FORMAT,D3D_FEATURE_LEVEL,CD3D11FormatHelper::eExtendedFormatFeatures)
0x18002d114  xor     r9d, r9d
0x18002d117  cmp     eax, r15d
0x18002d11a  jnz     short loc_18002D0CA
0x18002d11c  jmp     short loc_18002D0BE
0x18002d11e  mov     ecx, [rsp+798h+var_50]
0x18002d125  bt      ebx, 8
0x18002d129  jnb     short loc_18002D179
0x18002d12b  test    byte ptr [r8+28h], 0C4h
0x18002d130  jnz     short loc_18002D179
0x18002d132  mov     r8d, r9d
0x18002d135  mov     edx, [r14]
0x18002d138  sub     edx, 1
0x18002d13b  jz      short loc_18002D161
0x18002d13d  sub     edx, 1
0x18002d140  jz      short loc_18002D14C
0x18002d142  sub     edx, 1
0x18002d145  jz      short loc_18002D14C
0x18002d147  cmp     edx, 1
0x18002d14a  jnz     short loc_18002D167
0x18002d14c  mov     eax, [r14+30h]
0x18002d150  and     al, 3
0x18002d152  neg     al
0x18002d154  sbb     r8d, r8d
0x18002d157  and     r8d, 40h
0x18002d15b  add     r8d, 44h ; 'D'
0x18002d15f  jmp     short loc_18002D167
0x18002d161  mov     r8d, 0C0h
0x18002d167  or      ecx, r8d
0x18002d16a  mov     [rsp+798h+var_50], ecx
0x18002d171  or      [rsp+798h+var_80], r8d
0x18002d179  cmp     [rsp+798h+var_70], 4
0x18002d181  jz      short loc_18002D1E5
0x18002d183  mov     r9d, [rsp+798h+var_A0]; enum D3D12_HEAP_TYPE
0x18002d18b  mov     r8d, [rsp+798h+var_94]; unsigned int
0x18002d193  lea     rdx, [rsp+798h+var_618]; retstr
0x18002d19b  mov     rcx, r13; this
0x18002d19e  call    ?GetCustomHeapProperties@CDevice@@UEAA?AUD3D12_HEAP_PROPERTIES@@IW4D3D12_HEAP_TYPE@@@Z; CDevice::GetCustomHeapProperties(uint,D3D12_HEAP_TYPE)
0x18002d1a3  mov     ecx, [rax]
0x18002d1a5  mov     [rsp+798h+var_70], ecx
0x18002d1ac  mov     ecx, [rax+4]
0x18002d1af  mov     [rsp+798h+var_6C], ecx
0x18002d1b6  mov     eax, [rax+8]
0x18002d1b9  mov     [rsp+798h+var_68], eax
0x18002d1c0  mov     eax, [rsp+798h+var_94]
0x18002d1c7  xor     r9d, r9d
0x18002d1ca  test    eax, eax
0x18002d1cc  cmovz   eax, r15d
0x18002d1d0  mov     [rsp+798h+var_64], eax
0x18002d1d7  mov     eax, [rsp+798h+var_90]
0x18002d1de  mov     [rsp+798h+var_60], eax
0x18002d1e5  test    sil, 2
0x18002d1e9  jz      short loc_18002D1F3
0x18002d1eb  mov     [rsp+798h+var_78], r9
0x18002d1f3  mov     edi, ebx
0x18002d1f5  and     edi, 4
0x18002d1f8  mov     [rsp+798h+var_724], edi
0x18002d1fc  mov     ecx, ebx
0x18002d1fe  and     ecx, 8
0x18002d201  mov     [rsp+798h+var_708], ecx
0x18002d208  mov     edx, ebx
0x18002d20a  and     edx, 10h
0x18002d20d  mov     [rsp+798h+var_70C], edx
0x18002d214  mov     r8d, ebx
0x18002d217  and     r8d, 200h
0x18002d21e  mov     [rsp+798h+var_728], r8d
0x18002d223  mov     r9d, ebx
0x18002d226  and     r9d, 4000h
0x18002d22d  shr     r9d, 2
0x18002d231  mov     eax, ebx
0x18002d233  and     eax, 582h
0x18002d238  or      r9d, eax
0x18002d23b  mov     eax, ecx
0x18002d23d  neg     eax
0x18002d23f  sbb     ecx, ecx
0x18002d241  and     ecx, 8
0x18002d244  or      r9d, ecx
0x18002d247  mov     eax, edi
0x18002d249  neg     eax
0x18002d24b  sbb     ecx, ecx
0x18002d24d  and     ecx, 4
0x18002d250  or      r9d, ecx
0x18002d253  mov     eax, r8d
0x18002d256  neg     eax
0x18002d258  sbb     ecx, ecx
0x18002d25a  and     ecx, 200h
0x18002d260  or      r9d, ecx
0x18002d263  mov     eax, edx
0x18002d265  neg     eax
0x18002d267  sbb     ecx, ecx
  ... truncated ...
```
