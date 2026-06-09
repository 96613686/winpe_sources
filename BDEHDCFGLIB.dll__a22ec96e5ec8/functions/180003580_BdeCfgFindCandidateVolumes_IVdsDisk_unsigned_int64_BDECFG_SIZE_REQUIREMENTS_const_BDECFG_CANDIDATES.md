# BdeCfgFindCandidateVolumes(IVdsDisk *,unsigned __int64,_BDECFG_SIZE_REQUIREMENTS * const,_BDECFG_CANDIDATES *)

- ea: `0x180003580`
- end: `0x180003a03`
- name: `?BdeCfgFindCandidateVolumes@@YAJPEAUIVdsDisk@@_KQEAU_BDECFG_SIZE_REQUIREMENTS@@PEAU_BDECFG_CANDIDATES@@@Z`
- size: `1155`
- prototype: `__int64 __fastcall(struct IVdsDisk *, unsigned __int64, struct _BDECFG_SIZE_REQUIREMENTS *const, struct _BDECFG_CANDIDATES *)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task`

## callers

- `0x18000f430`

## callees

- `0x1800021b0`
- `0x180002460`
- `0x180003240`
- `0x180003580`
- `0x180004170`
- `0x180004620`
- `0x180006234`
- `0x18000960c`
- `0x18000e300`
- `0x18001358e`
- `0x1800135c0`
- `0x180015010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800039d8`
- `ole32!CoTaskMemFree` at `0x1800039d8`

## pseudocode

```c
__int64 __fastcall BdeCfgFindCandidateVolumes(
        struct IVdsDisk *a1,
        unsigned __int64 a2,
        struct _BDECFG_SIZE_REQUIREMENTS *const a3,
        struct _BDECFG_CANDIDATES *a4)
{
  int ExtendedPartitionExtent; // ebx
  unsigned int v10; // esi
  __int64 v11; // rcx
  char *v12; // r8
  __int64 v13; // rdx
  _WORD *v14; // rax
  _WORD *v15; // rcx
  __int64 v16; // rdx
  _OWORD *v17; // rcx
  _OWORD *v18; // rax
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int128 v26; // xmm1
  __int128 v27; // xmm0
  __int64 v28; // rax
  int ActivePartOnDisk; // eax
  unsigned __int64 v30; // r15
  int v31; // edi
  unsigned __int64 v32; // r12
  __int64 v33; // r8
  __int64 v34; // r9
  int VolumeFromId; // eax
  unsigned __int16 *v36; // rax
  int v37; // ecx
  int v38; // edx
  int v39; // ebx
  __int64 v40; // rcx
  _OWORD *v41; // rax
  _OWORD *v42; // rdx
  __int128 v43; // xmm1
  __int128 v44; // xmm0
  __int128 v45; // xmm1
  __int128 v46; // xmm0
  __int128 v47; // xmm1
  __int128 v48; // xmm0
  __int128 v49; // xmm1
  __int128 v50; // xmm1
  __int128 v51; // xmm0
  __int64 v52; // rax
  int v53; // [rsp+30h] [rbp-D0h] BYREF
  struct IVdsVolume *v54; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v55; // [rsp+40h] [rbp-C0h]
  LPVOID pv; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 v57; // [rsp+50h] [rbp-B0h] BYREF
  struct _GUID v58; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v59; // [rsp+70h] [rbp-90h]
  _BYTE v60[8]; // [rsp+80h] [rbp-80h] BYREF
  char v61; // [rsp+88h] [rbp-78h] BYREF
  _WORD v62[264]; // [rsp+2C0h] [rbp+1C0h] BYREF
  unsigned __int16 v63[264]; // [rsp+4D0h] [rbp+3D0h] BYREF

  v59 = a2;
  v54 = 0;
  *(_QWORD *)&v58.Data1 = 0;
  v57 = 0;
  memset_0(v60, 0, 0x238u);
  pv = 0;
  v53 = 0;
  memset_0(v62, 0, 0x208u);
  memset_0(v63, 0, 0x208u);
  if ( !g_pService )
    return 3231711254LL;
  if ( a3 )
  {
    v10 = 0;
    memset_0(a4, 0, 0x6B0u);
    if ( !(unsigned int)BdeCfgDetectAndCheckWinREVolume(a3, (struct _BDECFG_CANDIDATE *)v60) )
    {
      v11 = 2147483646;
      v12 = &v61;
      v13 = 260;
      v14 = v62;
      do
      {
        if ( !v11 )
          break;
        if ( !*(_WORD *)v12 )
          break;
        *v14 = *(_WORD *)v12;
        v12 += 2;
        ++v14;
        --v11;
        --v13;
      }
      while ( v13 );
      v15 = v14 - 1;
      if ( v13 )
        v15 = v14;
      *v15 = 0;
      if ( v13 )
      {
        v16 = 4;
        v17 = (_OWORD *)((char *)a4 + 8);
        v18 = v60;
        do
        {
          v19 = v18[1];
          *v17 = *v18;
          v20 = v18[2];
          v17[1] = v19;
          v21 = v18[3];
          v17[2] = v20;
          v22 = v18[4];
          v17[3] = v21;
          v23 = v18[5];
          v17[4] = v22;
          v24 = v18[6];
          v17[5] = v23;
          v25 = v18[7];
          v18 += 8;
          v17[6] = v24;
          v17[7] = v25;
          v17 += 8;
          --v16;
        }
        while ( v16 );
        v10 = 1;
        v26 = v18[1];
        *v17 = *v18;
        v27 = v18[2];
        v28 = *((_QWORD *)v18 + 6);
        v17[1] = v26;
        v17[2] = v27;
        *((_QWORD *)v17 + 6) = v28;
      }
      else
      {
        v62[0] = 0;
      }
    }
    v55 = 3;
    memset_0(v60, 0, 0x238u);
    ActivePartOnDisk = BdeCfgCanCreateActivePartOnDisk(a1);
    ExtendedPartitionExtent = ActivePartOnDisk;
    if ( ActivePartOnDisk < 0 )
    {
      if ( ActivePartOnDisk != -1063256017 )
      {
LABEL_49:
        if ( v54 )
        {
          ((void (__fastcall *)(struct IVdsVolume *))v54->lpVtbl->Release)(v54);
          v54 = 0;
        }
        if ( pv )
          CoTaskMemFree(pv);
        return (unsigned int)ExtendedPartitionExtent;
      }
      v55 = 1;
    }
    ExtendedPartitionExtent = BdeCfgpGetExtendedPartitionExtent(a1, (unsigned __int64 *)&v58.Data1, &v57);
    if ( ExtendedPartitionExtent >= 0 )
    {
      ExtendedPartitionExtent = ((__int64 (__fastcall *)(struct IVdsDisk *, LPVOID *, int *))a1->lpVtbl->QueryExtents)(
                                  a1,
                                  &pv,
                                  &v53);
      if ( ExtendedPartitionExtent >= 0 )
      {
        v30 = a2;
        if ( *(_QWORD *)a3 - *((_QWORD *)a3 + 3) < a2 )
          v30 = *(_QWORD *)a3 - *((_QWORD *)a3 + 3);
        v31 = 0;
        if ( v53 > 0 )
        {
          v32 = *(_QWORD *)&v58.Data1;
          v33 = *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4;
          v34 = *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1;
          do
          {
            if ( *((_DWORD *)pv + 20 * v31 + 4) == 2
              && *((_QWORD *)pv + 10 * v31 + 4) >= v30
              && (*((_QWORD *)pv + 10 * v31 + 5) != v34 || *((_QWORD *)pv + 10 * v31 + 6) != v33)
              && (*((_QWORD *)pv + 10 * v31 + 3) < v32 || *((_QWORD *)pv + 10 * v31 + 3) >= v32 + v57) )
            {
              v58 = *(struct _GUID *)((char *)pv + 80 * v31 + 40);
              VolumeFromId = BdeCfgGetVolumeFromId(&v58, &v54);
              if ( VolumeFromId < 0
                || (VolumeFromId = BdeCfgGetDeviceNameFromVolume(v54, 0x104u, v63), VolumeFromId < 0) )
              {
                BdeCfgLogError(1, (unsigned int)VolumeFromId);
              }
              else
              {
                v36 = v63;
                do
                {
                  v37 = *(v36 - 264);
                  v38 = *v36 - v37;
                  if ( v38 )
                    break;
                  ++v36;
                }
                while ( v37 );
                if ( v38 )
                {
                  v39 = BdeCfgCheckVolumeAsCandidate(v54, v59, a3, v55, (struct _BDECFG_CANDIDATE *)v60);
                  if ( v54 )
                  {
                    ((void (__fastcall *)(struct IVdsVolume *))v54->lpVtbl->Release)(v54);
                    v54 = 0;
                  }
                  if ( v39 >= 0 )
                  {
                    v40 = 4;
                    v41 = v60;
                    v42 = (_OWORD *)((char *)a4 + 568 * v10 + 8);
                    do
                    {
                      v43 = v41[1];
                      *v42 = *v41;
                      v44 = v41[2];
                      v42[1] = v43;
                      v45 = v41[3];
                      v42[2] = v44;
                      v46 = v41[4];
                      v42[3] = v45;
                      v47 = v41[5];
                      v42[4] = v46;
                      v48 = v41[6];
                      v42[5] = v47;
                      v49 = v41[7];
                      v41 += 8;
                      v42[6] = v48;
                      v42[7] = v49;
                      v42 += 8;
                      --v40;
                    }
                    while ( v40 );
                    ++v10;
                    v50 = v41[1];
                    *v42 = *v41;
                    v51 = v41[2];
                    v52 = *((_QWORD *)v41 + 6);
                    v42[1] = v50;
                    v42[2] = v51;
                    *((_QWORD *)v42 + 6) = v52;
                    if ( v10 >= 3 )
                      break;
                    memset_0(v60, 0, 0x238u);
                  }
                }
              }
              v33 = *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4;
              v34 = *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1;
            }
            ++v31;
          }
          while ( v31 < v53 );
        }
        *(_DWORD *)a4 = v10;
        BdeCfgpSortCandidates(a4);
        ExtendedPartitionExtent = v10 == 0;
      }
    }
    goto LABEL_49;
  }
  return (unsigned int)-2147467261;
}

```

## disassembly

```asm
0x180003580  push    rbp
0x180003582  push    rbx
0x180003583  push    rsi
0x180003584  push    rdi
0x180003585  push    r12
0x180003587  push    r13
0x180003589  push    r14
0x18000358b  push    r15
0x18000358d  lea     rbp, [rsp-5F8h]
0x180003595  sub     rsp, 6F8h
0x18000359c  mov     rax, cs:__security_cookie
0x1800035a3  xor     rax, rsp
0x1800035a6  mov     [rbp+630h+var_50], rax
0x1800035ad  xor     r15d, r15d
0x1800035b0  mov     [rsp+730h+var_6C0], rdx
0x1800035b5  mov     r13, r8
0x1800035b8  mov     [rsp+730h+var_6F8], r15
0x1800035bd  mov     r12, rdx
0x1800035c0  mov     qword ptr [rsp+730h+var_6D0.Data1], r15
0x1800035c5  mov     rdi, rcx
0x1800035c8  mov     [rsp+730h+var_6E0], r15
0x1800035cd  xor     edx, edx; Val
0x1800035cf  lea     rcx, [rbp+630h+var_6B0]; void *
0x1800035d3  mov     r8d, 238h; Size
0x1800035d9  mov     r14, r9
0x1800035dc  call    memset_0
0x1800035e1  mov     ebx, 208h
0x1800035e6  mov     [rsp+730h+pv], r15
0x1800035eb  mov     r8d, ebx; Size
0x1800035ee  mov     [rsp+730h+var_700], r15d
0x1800035f3  xor     edx, edx; Val
0x1800035f5  lea     rcx, [rbp+630h+var_470]; void *
0x1800035fc  call    memset_0
0x180003601  mov     r8d, ebx; Size
0x180003604  lea     rcx, [rbp+630h+var_260]; void *
0x18000360b  xor     edx, edx; Val
0x18000360d  call    memset_0
0x180003612  cmp     cs:?g_pService@@3PEAUIVdsService@@EA, r15; IVdsService * g_pService
0x180003619  jnz     short loc_180003625
0x18000361b  mov     eax, 0C0A00016h
0x180003620  jmp     loc_1800039E0
0x180003625  test    r13, r13
0x180003628  jnz     short loc_180003634
0x18000362a  mov     ebx, 80004003h
0x18000362f  jmp     loc_1800039DE
0x180003634  xor     edx, edx; Val
0x180003636  mov     r8d, 6B0h; Size
0x18000363c  mov     rcx, r14; void *
0x18000363f  mov     esi, r15d
0x180003642  call    memset_0
0x180003647  lea     rdx, [rbp+630h+var_6B0]; struct _BDECFG_CANDIDATE *
0x18000364b  mov     rcx, r13; struct _BDECFG_SIZE_REQUIREMENTS *
0x18000364e  call    ?BdeCfgDetectAndCheckWinREVolume@@YAJQEAU_BDECFG_SIZE_REQUIREMENTS@@PEAU_BDECFG_CANDIDATE@@@Z; BdeCfgDetectAndCheckWinREVolume(_BDECFG_SIZE_REQUIREMENTS * const,_BDECFG_CANDIDATE *)
0x180003653  test    eax, eax
0x180003655  jnz     loc_18000372B
0x18000365b  mov     ecx, 7FFFFFFEh
0x180003660  lea     r8, [rbp+630h+var_6A8]
0x180003664  mov     edx, 104h
0x180003669  lea     rax, [rbp+630h+var_470]
0x180003670  test    rcx, rcx
0x180003673  jz      short loc_180003694
0x180003675  movzx   r9d, word ptr [r8]
0x180003679  test    r9w, r9w
0x18000367d  jz      short loc_180003694
0x18000367f  mov     [rax], r9w
0x180003683  add     r8, 2
0x180003687  add     rax, 2
0x18000368b  dec     rcx
0x18000368e  sub     rdx, 1
0x180003692  jnz     short loc_180003670
0x180003694  test    rdx, rdx
0x180003697  lea     rcx, [rax-2]
0x18000369b  cmovnz  rcx, rax
0x18000369f  mov     [rcx], r15w
0x1800036a3  jz      short loc_180003723
0x1800036a5  mov     edx, 4
0x1800036aa  lea     rcx, [r14+8]
0x1800036ae  lea     rax, [rbp+630h+var_6B0]
0x1800036b2  lea     r9d, [rdx+7Ch]
0x1800036b6  movups  xmm0, xmmword ptr [rax]
0x1800036b9  movups  xmm1, xmmword ptr [rax+10h]
0x1800036bd  movups  xmmword ptr [rcx], xmm0
0x1800036c0  movups  xmm0, xmmword ptr [rax+20h]
0x1800036c4  movups  xmmword ptr [rcx+10h], xmm1
0x1800036c8  movups  xmm1, xmmword ptr [rax+30h]
0x1800036cc  movups  xmmword ptr [rcx+20h], xmm0
0x1800036d0  movups  xmm0, xmmword ptr [rax+40h]
0x1800036d4  movups  xmmword ptr [rcx+30h], xmm1
0x1800036d8  movups  xmm1, xmmword ptr [rax+50h]
0x1800036dc  movups  xmmword ptr [rcx+40h], xmm0
0x1800036e0  movups  xmm0, xmmword ptr [rax+60h]
0x1800036e4  movups  xmmword ptr [rcx+50h], xmm1
0x1800036e8  movups  xmm1, xmmword ptr [rax+70h]
0x1800036ec  add     rax, r9
0x1800036ef  movups  xmmword ptr [rcx+60h], xmm0
0x1800036f3  movups  xmmword ptr [rcx+70h], xmm1
0x1800036f7  add     rcx, r9
0x1800036fa  sub     rdx, 1
0x1800036fe  jnz     short loc_1800036B6
0x180003700  movups  xmm0, xmmword ptr [rax]
0x180003703  lea     esi, [rdx+1]
0x180003706  movups  xmm1, xmmword ptr [rax+10h]
0x18000370a  movups  xmmword ptr [rcx], xmm0
0x18000370d  movups  xmm0, xmmword ptr [rax+20h]
0x180003711  mov     rax, [rax+30h]
0x180003715  movups  xmmword ptr [rcx+10h], xmm1
0x180003719  movups  xmmword ptr [rcx+20h], xmm0
0x18000371d  mov     [rcx+30h], rax
0x180003721  jmp     short loc_18000372B
0x180003723  mov     [rbp+630h+var_470], r15w
0x18000372b  xor     edx, edx; Val
0x18000372d  mov     [rsp+730h+var_6F0], 3
0x180003735  mov     r8d, 238h; Size
0x18000373b  lea     rcx, [rbp+630h+var_6B0]; void *
0x18000373f  call    memset_0
0x180003744  mov     rcx, rdi; struct IVdsDisk *
0x180003747  call    ?BdeCfgCanCreateActivePartOnDisk@@YAJPEAUIVdsDisk@@@Z; BdeCfgCanCreateActivePartOnDisk(IVdsDisk *)
0x18000374c  mov     ebx, eax
0x18000374e  test    eax, eax
0x180003750  jns     short loc_180003765
0x180003752  cmp     eax, 0C0A0002Fh
0x180003757  jnz     loc_1800039B3
0x18000375d  mov     [rsp+730h+var_6F0], 1
0x180003765  lea     r8, [rsp+730h+var_6E0]; unsigned __int64 *
0x18000376a  mov     rcx, rdi; struct IVdsDisk *
0x18000376d  lea     rdx, [rsp+730h+var_6D0]; unsigned __int64 *
0x180003772  call    ?BdeCfgpGetExtendedPartitionExtent@@YAJPEAUIVdsDisk@@PEA_K1@Z; BdeCfgpGetExtendedPartitionExtent(IVdsDisk *,unsigned __int64 *,unsigned __int64 *)
0x180003777  mov     ebx, eax
0x180003779  test    eax, eax
0x18000377b  js      loc_1800039B3
0x180003781  mov     rax, [rdi]
0x180003784  lea     r8, [rsp+730h+var_700]
0x180003789  lea     rdx, [rsp+730h+pv]
0x18000378e  mov     rcx, rdi
0x180003791  mov     rax, [rax+30h]
0x180003795  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000379a  mov     ebx, eax
0x18000379c  test    eax, eax
0x18000379e  js      loc_1800039B3
0x1800037a4  mov     rax, [r13+0]
0x1800037a8  mov     r15, r12
0x1800037ab  sub     rax, [r13+18h]
0x1800037af  cmp     rax, r12
0x1800037b2  cmovb   r15, rax
0x1800037b6  xor     edi, edi
0x1800037b8  cmp     [rsp+730h+var_700], edi
0x1800037bc  jle     loc_18000399C
0x1800037c2  mov     r12, qword ptr [rsp+730h+var_6D0.Data1]
0x1800037c7  mov     r8, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data4
0x1800037ce  mov     r9, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800037d5  mov     rdx, [rsp+730h+pv]
0x1800037da  movsxd  rax, edi
0x1800037dd  lea     rcx, [rax+rax*4]
0x1800037e1  add     rcx, rcx
0x1800037e4  cmp     dword ptr [rdx+rcx*8+10h], 2
0x1800037e9  jnz     loc_180003990
0x1800037ef  cmp     [rdx+rcx*8+20h], r15
0x1800037f4  jb      loc_180003990
0x1800037fa  cmp     [rdx+rcx*8+28h], r9
0x1800037ff  jnz     short loc_18000380C
0x180003801  cmp     [rdx+rcx*8+30h], r8
0x180003806  jz      loc_180003990
0x18000380c  cmp     [rdx+rcx*8+18h], r12
0x180003811  jb      short loc_180003826
0x180003813  mov     rax, [rsp+730h+var_6E0]
0x180003818  add     rax, r12
0x18000381b  cmp     [rdx+rcx*8+18h], rax
0x180003820  jb      loc_180003990
0x180003826  movups  xmm0, xmmword ptr [rdx+rcx*8+28h]
0x18000382b  lea     rdx, [rsp+730h+var_6F8]; struct IVdsVolume **
0x180003830  lea     rcx, [rsp+730h+var_6D0]; struct _GUID
0x180003835  movdqu  xmmword ptr [rsp+730h+var_6D0.Data1], xmm0
0x18000383b  call    ?BdeCfgGetVolumeFromId@@YAJU_GUID@@PEAPEAUIVdsVolume@@@Z; BdeCfgGetVolumeFromId(_GUID,IVdsVolume * *)
0x180003840  test    eax, eax
0x180003842  jns     short loc_180003855
0x180003844  mov     edx, eax
0x180003846  mov     ecx, 1
0x18000384b  call    BdeCfgLogError
0x180003850  jmp     loc_180003982
0x180003855  mov     rcx, [rsp+730h+var_6F8]; struct IVdsVolume *
0x18000385a  lea     r8, [rbp+630h+var_260]; unsigned __int16 *
0x180003861  mov     edx, 104h; unsigned __int64
0x180003866  call    ?BdeCfgGetDeviceNameFromVolume@@YAJPEAUIVdsVolume@@_KPEAG@Z; BdeCfgGetDeviceNameFromVolume(IVdsVolume *,unsigned __int64,ushort *)
0x18000386b  test    eax, eax
0x18000386d  js      short loc_180003844
0x18000386f  lea     rax, [rbp+630h+var_260]
0x180003876  lea     r8, [rbp+630h+var_470]
0x18000387d  sub     r8, rax
0x180003880  movzx   edx, word ptr [rax]
0x180003883  movzx   ecx, word ptr [rax+r8]
0x180003888  sub     edx, ecx
0x18000388a  jnz     short loc_180003894
0x18000388c  add     rax, 2
0x180003890  test    ecx, ecx
0x180003892  jnz     short loc_180003880
0x180003894  test    edx, edx
0x180003896  jz      loc_180003982
0x18000389c  mov     r9d, [rsp+730h+var_6F0]; unsigned int
0x1800038a1  lea     rax, [rbp+630h+var_6B0]
0x1800038a5  mov     rdx, [rsp+730h+var_6C0]; unsigned __int64
0x1800038aa  mov     r8, r13; struct _BDECFG_SIZE_REQUIREMENTS *
0x1800038ad  mov     rcx, [rsp+730h+var_6F8]; struct IVdsVolume *
0x1800038b2  mov     [rsp+730h+var_710], rax; struct _BDECFG_CANDIDATE *
0x1800038b7  call    ?BdeCfgCheckVolumeAsCandidate@@YAJPEAUIVdsVolume@@_KQEAU_BDECFG_SIZE_REQUIREMENTS@@KPEAU_BDECFG_CANDIDATE@@@Z; BdeCfgCheckVolumeAsCandidate(IVdsVolume *,unsigned __int64,_BDECFG_SIZE_REQUIREMENTS * const,ulong,_BDECFG_CANDIDATE *)
0x1800038bc  mov     rcx, [rsp+730h+var_6F8]
0x1800038c1  mov     ebx, eax
0x1800038c3  test    rcx, rcx
0x1800038c6  jz      short loc_1800038DD
0x1800038c8  mov     rdx, [rcx]
0x1800038cb  mov     rax, [rdx+10h]
0x1800038cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038d4  mov     [rsp+730h+var_6F8], 0
0x1800038dd  test    ebx, ebx
0x1800038df  js      loc_180003982
0x1800038e5  mov     eax, esi
0x1800038e7  mov     ecx, 4
0x1800038ec  imul    rdx, rax, 238h
0x1800038f3  lea     rax, [rbp+630h+var_6B0]
0x1800038f7  add     rdx, 8
0x1800038fb  lea     r8d, [rcx+7Ch]
0x1800038ff  add     rdx, r14
0x180003902  movups  xmm0, xmmword ptr [rax]
0x180003905  movups  xmm1, xmmword ptr [rax+10h]
0x180003909  movups  xmmword ptr [rdx], xmm0
0x18000390c  movups  xmm0, xmmword ptr [rax+20h]
0x180003910  movups  xmmword ptr [rdx+10h], xmm1
0x180003914  movups  xmm1, xmmword ptr [rax+30h]
0x180003918  movups  xmmword ptr [rdx+20h], xmm0
0x18000391c  movups  xmm0, xmmword ptr [rax+40h]
0x180003920  movups  xmmword ptr [rdx+30h], xmm1
0x180003924  movups  xmm1, xmmword ptr [rax+50h]
0x180003928  movups  xmmword ptr [rdx+40h], xmm0
0x18000392c  movups  xmm0, xmmword ptr [rax+60h]
0x180003930  movups  xmmword ptr [rdx+50h], xmm1
0x180003934  movups  xmm1, xmmword ptr [rax+70h]
0x180003938  add     rax, r8
0x18000393b  movups  xmmword ptr [rdx+60h], xmm0
0x18000393f  movups  xmmword ptr [rdx+70h], xmm1
0x180003943  add     rdx, r8
0x180003946  sub     rcx, 1
0x18000394a  jnz     short loc_180003902
0x18000394c  movups  xmm0, xmmword ptr [rax]
0x18000394f  inc     esi
0x180003951  movups  xmm1, xmmword ptr [rax+10h]
0x180003955  movups  xmmword ptr [rdx], xmm0
0x180003958  movups  xmm0, xmmword ptr [rax+20h]
0x18000395c  mov     rax, [rax+30h]
0x180003960  movups  xmmword ptr [rdx+10h], xmm1
0x180003964  movups  xmmword ptr [rdx+20h], xmm0
0x180003968  mov     [rdx+30h], rax
0x18000396c  cmp     esi, 3
0x18000396f  jnb     short loc_18000399C
0x180003971  xor     edx, edx; Val
0x180003973  lea     rcx, [rbp+630h+var_6B0]; void *
0x180003977  mov     r8d, 238h; Size
0x18000397d  call    memset_0
0x180003982  mov     r8, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data4
0x180003989  mov     r9, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180003990  inc     edi
0x180003992  cmp     edi, [rsp+730h+var_700]
0x180003996  jl      loc_1800037D5
0x18000399c  mov     rcx, r14; struct _BDECFG_CANDIDATES *
0x18000399f  mov     [r14], esi
0x1800039a2  call    ?BdeCfgpSortCandidates@@YAXPEAU_BDECFG_CANDIDATES@@@Z; BdeCfgpSortCandidates(_BDECFG_CANDIDATES *)
0x1800039a7  xor     r15d, r15d
0x1800039aa  cmp     esi, 1
0x1800039ad  mov     ebx, r15d
0x1800039b0  setb    bl
0x1800039b3  mov     rcx, [rsp+730h+var_6F8]
0x1800039b8  test    rcx, rcx
0x1800039bb  jz      short loc_1800039CE
0x1800039bd  mov     rax, [rcx]
0x1800039c0  mov     rax, [rax+10h]
0x1800039c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039c9  mov     [rsp+730h+var_6F8], r15
0x1800039ce  mov     rcx, [rsp+730h+pv]; pv
0x1800039d3  test    rcx, rcx
0x1800039d6  jz      short loc_1800039DE
0x1800039d8  call    cs:__imp_CoTaskMemFree
0x1800039de  mov     eax, ebx
0x1800039e0  mov     rcx, [rbp+630h+var_50]
0x1800039e7  xor     rcx, rsp; StackCookie
0x1800039ea  call    __security_check_cookie
0x1800039ef  add     rsp, 6F8h
0x1800039f6  pop     r15
0x1800039f8  pop     r14
0x1800039fa  pop     r13
0x1800039fc  pop     r12
0x1800039fe  pop     rdi
0x1800039ff  pop     rsi
0x180003a00  pop     rbx
0x180003a01  pop     rbp
0x180003a02  retn
```
