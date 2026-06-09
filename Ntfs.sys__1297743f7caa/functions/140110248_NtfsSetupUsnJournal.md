# NtfsSetupUsnJournal

- ea: `0x140110248`
- end: `0x1401123dd`
- name: `NtfsSetupUsnJournal`
- size: `8597`
- prototype: ``
- caller_count: `2`
- callee_count: `44`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14026fdd0`
- `0x140286f50`

## callees

- `0x140007ea0`
- `0x140009830`
- `0x14000c290`
- `0x14000ea70`
- `0x14001e810`
- `0x14001ebf0`
- `0x1400211b0`
- `0x140021e60`
- `0x140037854`
- `0x140040e80`
- `0x1400410a8`
- `0x1400592c0`
- `0x140059440`
- `0x140059740`
- `0x1400f5ce0`
- `0x140110248`
- `0x140125100`
- `0x140125fc0`
- `0x140126220`
- `0x140126a10`
- `0x140128da0`
- `0x1401305a0`
- `0x14013c320`
- `0x1401403d0`
- `0x140142c60`
- `0x140143730`
- `0x140145ddc`
- `0x140151da4`
- `0x1401560d0`
- `0x140158130`
- `0x1401597b8`
- `0x14015a5c0`
- `0x14015ec88`
- `0x140160c30`
- `0x140161230`
- `0x140162110`
- `0x1401623c0`
- `0x140163fc8`
- `0x1401751cc`
- `0x14019a768`
- `0x1401bb800`
- `0x1401c1c0c`
- `0x1401e06b0`
- `0x1402446b8`

## import_xrefs

- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x14011156d`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x14011156d`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140111844`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140111898`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140111844`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140111898`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x140111967`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x140111e4f`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x140111fc0`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x1402c64bd`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x140111967`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x140111e4f`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x140111fc0`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x1402c64bd`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140111877`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1401118a6`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140111a84`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140111faa`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1402c64a8`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140111877`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1401118a6`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140111a84`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140111faa`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1402c64a8`
- `ntoskrnl!CcMapData` at `0x140111774`
- `ntoskrnl!CcMapData` at `0x140111774`
- `ntoskrnl!ExSetTimer` at `0x140111f48`
- `ntoskrnl!ExSetTimer` at `0x140111f48`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140110c05`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140110e5f`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1401112cf`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140111f06`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14011216f`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1402c6513`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1402c6724`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140110c05`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140110e5f`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1401112cf`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140111f06`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14011216f`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1402c6513`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1402c6724`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140110bf2`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140110e4c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402c6500`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140110bf2`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140110e4c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1402c6500`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140110b6d`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140110b6d`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140110b5a`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14011117e`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140111ed3`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140112014`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1402c6575`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140110b5a`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14011117e`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140111ed3`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140112014`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1402c6575`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140111411`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140111411`
- `ntoskrnl!CcUnpinData` at `0x14011084c`
- `ntoskrnl!CcUnpinData` at `0x1401114d3`
- `ntoskrnl!CcUnpinData` at `0x140111930`
- `ntoskrnl!CcUnpinData` at `0x140111aa7`
- `ntoskrnl!CcUnpinData` at `0x140111e07`
- `ntoskrnl!CcUnpinData` at `0x140112195`
- `ntoskrnl!CcUnpinData` at `0x1401121c0`
- `ntoskrnl!CcUnpinData` at `0x1401121de`
- `ntoskrnl!CcUnpinData` at `0x1402c6749`
- `ntoskrnl!CcUnpinData` at `0x1402c6775`
- `ntoskrnl!CcUnpinData` at `0x1402c6795`
- `ntoskrnl!CcUnpinData` at `0x14011084c`
- `ntoskrnl!CcUnpinData` at `0x1401114d3`
- `ntoskrnl!CcUnpinData` at `0x140111930`
- `ntoskrnl!CcUnpinData` at `0x140111aa7`
- `ntoskrnl!CcUnpinData` at `0x140111e07`
- `ntoskrnl!CcUnpinData` at `0x140112195`
- `ntoskrnl!CcUnpinData` at `0x1401121c0`
- `ntoskrnl!CcUnpinData` at `0x1401121de`
- `ntoskrnl!CcUnpinData` at `0x1402c6749`
- `ntoskrnl!CcUnpinData` at `0x1402c6775`
- `ntoskrnl!CcUnpinData` at `0x1402c6795`
- `ntoskrnl!ExReleaseResourceLite` at `0x140110c2d`
- `ntoskrnl!ExReleaseResourceLite` at `0x140110e87`
- `ntoskrnl!ExReleaseResourceLite` at `0x14011149e`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c653b`
- `ntoskrnl!ExReleaseResourceLite` at `0x140110c2d`
- `ntoskrnl!ExReleaseResourceLite` at `0x140110e87`
- `ntoskrnl!ExReleaseResourceLite` at `0x14011149e`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402c653b`

## pseudocode

```c
void __fastcall NtfsSetupUsnJournal(__int64 a1, __int64 a2, __int64 a3, int a4, int a5, __int64 *a6)
{
  int v6; // ebx
  __int64 v9; // r14
  __int64 v10; // rdi
  unsigned __int64 v11; // rbx
  __int64 v12; // rcx
  int v13; // r9d
  __int64 v14; // rcx
  int v15; // eax
  __m128i v16; // xmm1
  __int64 v17; // r9
  unsigned __int64 v18; // r8
  __int64 v19; // rax
  __int64 *v20; // rdx
  char v21; // cl
  __int64 v22; // r9
  unsigned __int64 v23; // r9
  char v24; // cl
  unsigned int v25; // edx
  unsigned __int64 v26; // r9
  unsigned __int64 v27; // r8
  unsigned __int64 v28; // rcx
  unsigned __int64 v29; // rcx
  const UNICODE_STRING *v30; // rbx
  signed __int64 v31; // rbx
  signed __int64 v32; // rax
  LONGLONG v33; // rbx
  __int64 v34; // rcx
  struct _ERESOURCE *v35; // rcx
  unsigned int v36; // eax
  int v37; // edx
  char v38; // cl
  __int64 v39; // rax
  __int64 *v40; // r11
  PCUNICODE_STRING v41; // r9
  __int64 v42; // rdx
  LONGLONG v43; // r8
  __int64 v44; // rax
  __int64 v45; // rcx
  __int64 v46; // rdx
  signed __int64 v47; // rcx
  __int64 v48; // rbx
  signed __int64 v49; // rdx
  signed __int64 v50; // rax
  signed __int64 v51; // rdx
  signed __int64 v52; // rax
  __int64 v53; // r8
  signed __int64 v54; // rcx
  signed __int64 v55; // rdx
  signed __int64 v56; // rax
  signed __int64 v57; // rdx
  signed __int64 v58; // rax
  __int64 v59; // rcx
  struct _ERESOURCE *v60; // rcx
  __int64 v61; // rcx
  unsigned int v62; // r8d
  __int64 v63; // rdx
  char v64; // al
  __int128 *v65; // rcx
  union _LARGE_INTEGER v66; // rdi
  __int128 *v67; // rax
  __m128i v68; // xmm1
  signed __int64 v69; // xmm1_8
  signed __int64 v70; // rax
  __int64 v71; // r9
  __int64 v72; // rax
  __int64 v73; // rdx
  union _LARGE_INTEGER v74; // rax
  __int64 v75; // rdx
  __int64 v76; // r8
  union _LARGE_INTEGER v77; // r9
  LONGLONG v78; // rax
  __int64 v79; // rdx
  __int64 v80; // rdx
  signed __int64 v81; // rcx
  signed __int64 v82; // rdx
  signed __int64 v83; // rax
  signed __int64 v84; // rdx
  signed __int64 v85; // rax
  __int64 v86; // rdx
  signed __int64 v87; // rcx
  signed __int64 v88; // rdx
  signed __int64 v89; // rax
  signed __int64 v90; // rdx
  signed __int64 v91; // rax
  __int16 v92; // ax
  int v93; // ebx
  __int64 v94; // rbx
  __int64 v95; // rax
  unsigned __int64 v96; // rcx
  unsigned __int64 v97; // rax
  int v98; // r8d
  __int64 v99; // rbx
  _QWORD *v100; // rbx
  __int64 v101; // rcx
  __int64 v102; // rcx
  __int64 v103; // rdx
  unsigned __int64 v104; // rcx
  __int64 v105; // r8
  __int64 v106; // r8
  unsigned int *v107; // r10
  unsigned int v108; // r9d
  unsigned int v109; // ecx
  __int64 v110; // r11
  _DWORD *inserted; // rax
  __int64 v112; // rax
  bool v113; // cc
  _QWORD *v114; // r8
  _QWORD *v115; // rax
  __int64 v116; // rcx
  unsigned int v117; // ebx
  int v118; // ebx
  PVOID v119; // rcx
  unsigned __int64 v120; // rbx
  __int64 v121; // rbx
  int v122; // r9d
  PVOID v123; // rcx
  PCUNICODE_STRING v124; // rax
  int v125; // edx
  PVOID v126; // rax
  __int128 *v127; // rax
  __int64 v128; // rax
  __int64 v129; // rdx
  __int64 v130; // r8
  __int64 v131; // rax
  __int64 v132; // rcx
  __int64 v133; // rdx
  signed __int64 v134; // rcx
  __int64 v135; // r8
  signed __int64 v136; // rdx
  signed __int64 v137; // rax
  signed __int64 v138; // rdx
  signed __int64 v139; // rax
  __int64 v140; // r8
  signed __int64 v141; // rcx
  __int64 v142; // r8
  signed __int64 v143; // rdx
  signed __int64 v144; // rax
  signed __int64 v145; // rdx
  signed __int64 v146; // rax
  PVOID v147; // rcx
  int v148; // edx
  __int64 v149; // r9
  int v150; // ecx
  __int64 v151; // rdx
  int TableContext; // [rsp+78h] [rbp-378h]
  PVOID TableContexta; // [rsp+78h] [rbp-378h]
  int v154; // [rsp+88h] [rbp-368h]
  int v155; // [rsp+88h] [rbp-368h]
  size_t v156; // [rsp+90h] [rbp-360h]
  int v157; // [rsp+98h] [rbp-358h]
  char v158; // [rsp+A8h] [rbp-348h] BYREF
  char v159; // [rsp+A9h] [rbp-347h]
  unsigned int Size; // [rsp+ACh] [rbp-344h] BYREF
  char Size_4; // [rsp+B0h] [rbp-340h]
  char Size_5; // [rsp+B1h] [rbp-33Fh]
  unsigned __int8 Size_6; // [rsp+B2h] [rbp-33Eh] BYREF
  char Size_7; // [rsp+B3h] [rbp-33Dh]
  int v165; // [rsp+B4h] [rbp-33Ch]
  char v166; // [rsp+B8h] [rbp-338h]
  PVOID Buffer; // [rsp+C0h] [rbp-330h] BYREF
  PVOID Bcb; // [rsp+C8h] [rbp-328h] BYREF
  char v169; // [rsp+D0h] [rbp-320h]
  PCUNICODE_STRING ConstantNameB; // [rsp+D8h] [rbp-318h] BYREF
  int v171[2]; // [rsp+E0h] [rbp-310h] BYREF
  int v172[2]; // [rsp+E8h] [rbp-308h]
  union _LARGE_INTEGER FileOffset; // [rsp+F0h] [rbp-300h] BYREF
  int v174; // [rsp+F8h] [rbp-2F8h]
  PVOID v175; // [rsp+100h] [rbp-2F0h] BYREF
  char *v176; // [rsp+108h] [rbp-2E8h]
  ULONG Length[2]; // [rsp+110h] [rbp-2E0h] BYREF
  __int64 v178; // [rsp+118h] [rbp-2D8h]
  __int64 v179; // [rsp+120h] [rbp-2D0h] BYREF
  __int128 *v180; // [rsp+128h] [rbp-2C8h]
  __int64 *v181; // [rsp+130h] [rbp-2C0h]
  union _LARGE_INTEGER v182; // [rsp+138h] [rbp-2B8h]
  void *Src; // [rsp+140h] [rbp-2B0h] BYREF
  _DWORD *v184; // [rsp+148h] [rbp-2A8h]
  __int64 v185; // [rsp+150h] [rbp-2A0h]
  int v186[2]; // [rsp+158h] [rbp-298h] BYREF
  __int16 *Scb; // [rsp+160h] [rbp-290h]
  __int64 v188; // [rsp+168h] [rbp-288h] BYREF
  __int64 v189; // [rsp+170h] [rbp-280h] BYREF
  __int64 *v190; // [rsp+178h] [rbp-278h]
  __int64 v191; // [rsp+180h] [rbp-270h]
  int v192; // [rsp+188h] [rbp-268h]
  __int128 v193; // [rsp+190h] [rbp-260h]
  PVOID v194[2]; // [rsp+1A0h] [rbp-250h] BYREF
  PVOID v195; // [rsp+1B0h] [rbp-240h] BYREF
  __int64 v196; // [rsp+1B8h] [rbp-238h]
  __int64 v197; // [rsp+1C0h] [rbp-230h]
  _DWORD *v198; // [rsp+1C8h] [rbp-228h]
  __int128 *v199; // [rsp+1D0h] [rbp-220h]
  __int64 *v200; // [rsp+1D8h] [rbp-218h]
  __int64 v201; // [rsp+1E0h] [rbp-210h]
  __int128 v202; // [rsp+1E8h] [rbp-208h] BYREF
  __int128 v203; // [rsp+1F8h] [rbp-1F8h]
  __int64 v204[12]; // [rsp+208h] [rbp-1E8h] BYREF
  __int64 v205; // [rsp+268h] [rbp-188h]
  __int64 v206; // [rsp+270h] [rbp-180h]
  __int64 v207; // [rsp+278h] [rbp-178h]
  __int64 v208; // [rsp+280h] [rbp-170h]
  _DWORD *v209; // [rsp+288h] [rbp-168h]
  __int64 v210; // [rsp+298h] [rbp-158h]
  _QWORD *v211; // [rsp+2A0h] [rbp-150h]
  _QWORD v212[12]; // [rsp+2A8h] [rbp-148h] BYREF
  __int128 v213; // [rsp+308h] [rbp-E8h] BYREF
  __m128i v214; // [rsp+318h] [rbp-D8h]
  _QWORD v215[2]; // [rsp+328h] [rbp-C8h] BYREF
  struct _RTL_AVL_TABLE Table; // [rsp+338h] [rbp-B8h] BYREF

  v6 = a3;
  *(_QWORD *)v172 = a3;
  v190 = a6;
  v178 = a1;
  v191 = a2;
  v197 = a3;
  v201 = (__int64)a6;
  memset(&Table, 0, sizeof(Table));
  *(_QWORD *)v186 = 0;
  Buffer = 0;
  memset(v204, 0, 0x58u);
  memset(v212, 0, 0x58u);
  v193 = 0;
  *(_OWORD *)v194 = 0;
  *(_QWORD *)v171 = 0;
  v189 = 0;
  Src = 0;
  v213 = 0;
  v214 = 0;
  v202 = 0;
  v203 = 0;
  v188 = 0;
  Bcb = 0;
  v175 = 0;
  v158 = 0;
  Size_6 = 0;
  Size = 0;
  *(_QWORD *)Length = 0;
  v184 = (_DWORD *)(a2 + 4);
  v165 = *(_DWORD *)(a2 + 4) & 0x2000000;
  v192 = v165;
  if ( (unsigned int)NtOfsCreateAttributeEx(
                       a1,
                       v6,
                       (unsigned int)&JournalStreamName,
                       128,
                       (unsigned int)(v165 != 0) + 1,
                       1,
                       (__int64)v186) == -1073741772
    || (v9 = *(_QWORD *)v186) == 0 )
  {
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 3221226168LL, 2820940);
    NtfsRaiseStatusInternal(a1, -1073741128, 0, 0, 2820940);
    JUMPOUT(0x1401123DDLL);
  }
  v185 = a2;
  v215[0] = a2 + 4;
  Size_4 = 0;
  v166 = 0;
  Size_7 = 1;
  v10 = 0;
  v196 = 0;
  v11 = 0;
  v198 = v184;
  v209 = v184;
  v159 = 0;
  *(_DWORD *)(*(_QWORD *)v186 + 512LL) |= 1u;
  memset(v212, 0, 0x58u);
  memset(v204, 0, 0x58u);
  v194[1] = 0;
  v12 = *v190;
  v213 = *(_OWORD *)v190;
  v214 = *(__m128i *)(a2 + 1912);
  if ( !a4 || (Size_5 = 1, (v12 & 0xFFFFFFFFFDFFFFFFuLL) != 0) )
    Size_5 = 0;
  FileOffset = *(union _LARGE_INTEGER *)(v9 + 576);
  v182 = FileOffset;
  v199 = (__int128 *)(a2 + 1896);
  v202 = *(_OWORD *)(a2 + 1896);
  v203 = *(_OWORD *)(a2 + 1912);
  v180 = &v202;
  if ( (*(_DWORD *)(v9 + 200) & 0x20) == 0 )
    NtfsUpdateScbFromAttribute(a1, v9, 0);
  if ( (*(_DWORD *)(v9 + 200) & 8) != 0 && !v165 )
  {
    LOBYTE(v154) = 0;
    if ( !(unsigned __int8)NtfsLookupInFileRecord(
                             a1,
                             *(_QWORD *)(v9 + 184),
                             *(_QWORD *)(v9 + 184) + 8LL,
                             *(unsigned int *)(v9 + 256),
                             v9 + 264,
                             0,
                             v154,
                             0,
                             0,
                             v204)
      && (*(_DWORD *)(v9 + 512) & 4) == 0 )
    {
      v11 = 0xA9002B0B96LL;
      NtfsAttachCorruption_BadOrOrphanFRS(a1, 2, 2821014, v13, *(_QWORD *)(v9 + 184) + 8LL, *(_QWORD *)(v9 + 184), 0);
      NtfsAttachRepairInfoPriv(a1, 512, 0, 0xA9002B0B96LL);
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 3221225730LL, 2821014);
      NtfsRaiseStatusInternal(a1, -1073741566, *(_QWORD *)(v9 + 184) + 8, *(_QWORD *)(v9 + 184), 2821014);
    }
    NtfsConvertToNonresident(a1, *(__int64 *)v172, v204[0], 1u, v204);
    NtfsCleanupAttributeContext(v14, v204);
    memset(v204, 0, 0x58u);
  }
  v15 = 1;
  if ( (*v184 & 0x400000) == 0 )
    v15 = a5;
  LODWORD(v176) = v15;
  v181 = (__int64 *)(*(_QWORD *)v172 + 8LL);
  v207 = *(_QWORD *)v172 + 8LL;
  LOBYTE(v154) = 0;
  v169 = NtfsLookupInFileRecord(a1, *(_QWORD *)v172, *(_QWORD *)v172 + 8LL, 128, _Max, 0, v154, 0, 0, v204);
  if ( !v169 || (_DWORD)v176 )
  {
    NtfsAdvanceUsnJournal(a2, &v213, *(_QWORD *)(v9 + 32), &v158);
    goto LABEL_37;
  }
  if ( *(_BYTE *)(v204[0] + 8) )
  {
    Size = *(_DWORD *)(v204[0] + 48);
    v158 = 1;
  }
  else
  {
    Size = *(_DWORD *)(v204[0] + 16);
  }
  NtfsMapAttributeValue(a1, *(_QWORD *)v172, &Src, &Size, &Bcb, v204);
  if ( Size == 16 )
  {
    v214 = (__m128i)MEMORY[0xFFFFF78000000014];
    v158 = 1;
    if ( !a4 )
      memmove(&v213, Src, Size);
  }
  else if ( Size == 32 )
  {
    if ( a4 )
    {
      v158 = 1;
      v214 = *((__m128i *)Src + 1);
    }
    else
    {
      v213 = *(_OWORD *)Src;
      v16 = *((__m128i *)Src + 1);
      v214.m128i_i64[0] = *((_QWORD *)Src + 2);
      v214.m128i_i64[1] = _mm_srli_si128(v16, 8).m128i_u64[0];
    }
  }
  else
  {
    NtfsAdvanceUsnJournal(a2, &v213, *(_QWORD *)(v9 + 32), &v158);
  }
  if ( v204[2] )
  {
    if ( !Bcb )
      goto LABEL_37;
    CcUnpinData(Bcb);
  }
  else
  {
    v204[2] = (__int64)Bcb;
  }
  Bcb = 0;
LABEL_37:
  if ( !v158 )
  {
    v17 = *(_QWORD *)(v9 + 24);
    if ( v17 )
    {
      if ( v214.m128i_i64[1] != v17 )
      {
        v179 = 0;
        if ( !(unsigned __int8)NtfsLookupRealAllocationInternal(a1, (__int64)&v179, (__int64)&v189, 0, 0) || v179 == -1 )
          NtfsAdvanceUsnJournal(a2, &v213, *(_QWORD *)(v9 + 24), &v158);
      }
    }
  }
  v18 = v213;
  if ( (unsigned __int64)v213 < (unsigned __int64)v202 || Size_5 )
  {
    v18 = v202;
    *(_QWORD *)&v213 = v202;
    v19 = *((_QWORD *)&v213 + 1);
    if ( !*((_QWORD *)&v213 + 1) )
      v19 = *((_QWORD *)&v202 + 1);
    *((_QWORD *)&v213 + 1) = v19;
  }
  v20 = (__int64 *)(a2 + 296);
  if ( a4 )
  {
    if ( (dword_1400956B8 & 0x2000000) != 0
      || (v21 = *(_BYTE *)(a2 + 488), v22 = *v20, (unsigned __int64)(*v20 << v21) <= 0x40000000) )
    {
      v11 = 0x100000;
      v18 = 0;
      *(_QWORD *)&v213 = 0;
      goto LABEL_57;
    }
  }
  else
  {
    v21 = *(_BYTE *)(a2 + 488);
    v22 = *v20;
  }
  if ( Size_5 )
  {
    v23 = v22 << v21;
    if ( v23 > 0x400000000LL )
      v11 = 0x2000000;
    else
      v11 = (-(__int64)(v23 < 0x200000000LL) & 0xFFFFFFFFFFE00000uLL) + 0x400000;
  }
LABEL_57:
  if ( v11 > v18 )
  {
    v18 = v11;
    *(_QWORD *)&v213 = v11;
    *((_QWORD *)&v213 + 1) = v11 >> 2;
  }
  v176 = (char *)(a2 + 488);
  v24 = *(_BYTE *)(a2 + 488);
  if ( v18 > (unsigned __int64)(*v20 << v24) >> 1 )
    v18 = (unsigned __int64)(*v20 << v24) >> 1;
  *(_QWORD *)&v213 = v18;
  if ( v18 > 0x100000000LL )
    v18 = 0x100000000LL;
  *(_QWORD *)&v213 = v18;
  if ( v18 < 0x100000 )
    v18 = 0x100000;
  *(_QWORD *)&v213 = v18;
  v25 = *(_DWORD *)(a2 + 356);
  if ( v18 < 4 * v25 )
    v18 = 4 * v25;
  *(_QWORD *)&v213 = v18 & 0x1FFFC0000LL;
  v179 = a2 + 480;
  v26 = *(int *)(a2 + 484) & ((v18 & 0xFFFFFFFFFFFC0000uLL) + *(unsigned int *)(a2 + 480));
  *(_QWORD *)&v213 = v26;
  v27 = *((_QWORD *)&v213 + 1);
  if ( *((_QWORD *)&v213 + 1) < *((_QWORD *)&v202 + 1) )
    v27 = *((_QWORD *)&v202 + 1);
  *((_QWORD *)&v213 + 1) = v27;
  v28 = v25;
  if ( v25 < 0x40000 )
    v28 = 0x40000;
  if ( v27 >= v28 )
  {
    v28 = v27;
    if ( v27 > v26 >> 2 )
      v28 = v26 >> 2;
  }
  *((_QWORD *)&v213 + 1) = v28;
  if ( v25 < 0x40000 )
    v25 = 0x40000;
  v29 = -v25 & (unsigned int)v28;
  *((_QWORD *)&v213 + 1) = v29;
  if ( __PAIR128__(v29, v26) != v202 )
    v158 = 1;
  if ( v165 )
  {
    v30 = 0;
  }
  else
  {
    v31 = v26 + 2 * v29;
    v32 = *(_QWORD *)(v9 + 472);
    if ( v31 < v32 )
    {
      v30 = (const UNICODE_STRING *)v29;
      ConstantNameB = (PCUNICODE_STRING)v29;
      goto LABEL_84;
    }
    v30 = (const UNICODE_STRING *)(v31 - v32);
  }
  ConstantNameB = v30;
LABEL_84:
  LOBYTE(v27) = 1;
  NtfsAcquireResourceExclusive(v29, *(_QWORD *)(a2 + 72), v27);
  KeAcquireGuardedMutex((PKGUARDED_MUTEX)(a2 + 720));
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a2 + 6376));
  v159 = 1;
  if ( (__int64)v30 > FileOffset.QuadPart )
  {
    v33 = (LONGLONG)v30 - FileOffset.QuadPart;
    if ( (unsigned __int8)NtfsIsNoSpaceForReserve(a1) )
    {
      if ( a4 )
      {
        ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a2 + 6376));
        KeReleaseGuardedMutex((PKGUARDED_MUTEX)(a2 + 720));
        v34 = *(_QWORD *)(a2 + 72);
        if ( *(_WORD *)v34 == 1794 )
          v35 = (struct _ERESOURCE *)(*(_QWORD *)(v34 + 104) + 64LL);
        else
          v35 = *(struct _ERESOURCE **)(v34 + 8);
        ExReleaseResourceLite(v35);
        v159 = 0;
        NtfsAllocateDiskFullContext(a1, v33, 0x281002B0D3CLL);
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(a1, 3221225599LL, 2821437);
        NtfsRaiseStatusInternal(a1, -1073741697, 0, 0, 2821437);
      }
      Size = 0x2000;
      v36 = *(_DWORD *)(a2 + 356);
      v37 = 0x2000;
      if ( v36 > 0x2000 )
      {
        Size = *(_DWORD *)(a2 + 356);
        v37 = v36;
      }
      v214.m128i_i64[1] = -v37 & (*(_QWORD *)(v9 + 32) + v37 - 1);
      v214.m128i_i64[0] = MEMORY[0xFFFFF78000000014];
      v158 = 1;
      v166 = 1;
    }
  }
  v38 = *v176;
  v39 = *(unsigned int *)v179;
  v40 = (__int64 *)(a2 + 328);
  v200 = (__int64 *)(a2 + 328);
  v41 = ConstantNameB;
  v42 = ((__int64)ConstantNameB + v39) >> v38;
  v43 = (v39 + FileOffset.QuadPart) >> v38;
  v44 = v42 - v43;
  v45 = *(_QWORD *)(a2 + 328);
  if ( v42 - v43 <= 0 )
  {
    v53 = v42 - v43 + v45;
    *v40 = v53;
    if ( v53 < *(_QWORD *)(a2 + 8312) )
      *(_QWORD *)(a2 + 8312) = v53;
    v54 = *(_QWORD *)(a2 + 304) - (v53 >> 8) - *(_QWORD *)(a2 + 6368) - v53;
    if ( v54 <= 0 )
      v54 = 0;
    v48 = v185;
    do
    {
      v55 = *(_QWORD *)(v48 + 8344);
      v56 = v55;
      if ( v54 < v55 )
        v56 = _InterlockedCompareExchange64((volatile signed __int64 *)(v48 + 8344), v54, v55);
    }
    while ( v56 != v55 );
    do
    {
      v57 = *(_QWORD *)(v48 + 8352);
      v58 = v57;
      if ( v54 > v57 )
        v58 = _InterlockedCompareExchange64((volatile signed __int64 *)(v48 + 8352), v54, v57);
    }
    while ( v58 != v57 );
  }
  else
  {
    v46 = v44 + v45;
    *v40 = v44 + v45;
    if ( v44 + v45 > *(_QWORD *)(a2 + 8320) )
      *(_QWORD *)(a2 + 8320) = v46;
    v47 = *(_QWORD *)(a2 + 304) - (v46 >> 8) - *(_QWORD *)(a2 + 6368) - v46;
    if ( v47 <= 0 )
      v47 = 0;
    v48 = v185;
    do
    {
      v49 = *(_QWORD *)(v48 + 8344);
      v50 = v49;
      if ( v47 < v49 )
        v50 = _InterlockedCompareExchange64((volatile signed __int64 *)(v48 + 8344), v47, v49);
    }
    while ( v50 != v49 );
    do
    {
      v51 = *(_QWORD *)(v48 + 8352);
      v52 = v51;
      if ( v47 > v51 )
        v52 = _InterlockedCompareExchange64((volatile signed __int64 *)(v48 + 8352), v47, v51);
    }
    while ( v52 != v51 );
  }
  *(_QWORD *)(v9 + 576) = v41;
  *(_DWORD *)(v9 + 512) |= 0x2000u;
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a2 + 6376));
  KeReleaseGuardedMutex((PKGUARDED_MUTEX)(a2 + 720));
  v59 = *(_QWORD *)(a2 + 72);
  if ( *(_WORD *)v59 == 1794 )
    v60 = (struct _ERESOURCE *)(*(_QWORD *)(v59 + 104) + 64LL);
  else
    v60 = *(struct _ERESOURCE **)(v59 + 8);
  ExReleaseResourceLite(v60);
  v159 = 0;
  if ( v158 && !v165 )
  {
    if ( v169 )
    {
      if ( *(_BYTE *)(v204[0] + 8) )
      {
        Scb = NtfsCreateScb(a1, *(__int64 *)v172, 128, (const UNICODE_STRING *)_Max, 0, 0, 0);
        ConstantNameB = (PCUNICODE_STRING)(Scb + 132);
        do
        {
          NtfsDeleteAttributeRecord(a1, *(_QWORD *)v172, 7, v204);
          v62 = *((_DWORD *)Scb + 64);
          v63 = *((_QWORD *)Scb + 23);
          if ( v204[5] )
          {
            LODWORD(v156) = 0;
            v64 = NtfsLookupExternalAttribute(a1, v63, v62, ConstantNameB, 0, 0, 0, v156, (__int64)v204);
          }
          else
          {
            LOBYTE(v155) = 0;
            v64 = NtfsLookupInFileRecord(a1, v63, 0, v62, ConstantNameB, 0, v155, 0, 0, v204);
          }
        }
        while ( v64 );
      }
      else
      {
        NtfsDeleteAttributeRecord(a1, *(_QWORD *)v172, 7, v204);
      }
    }
    NtfsCleanupAttributeContext(v61, v204);
    memset(v204, 0, 0x58u);
    LOBYTE(v157) = 1;
    LOWORD(v155) = 0;
    NtfsCreateAttributeWithValue(a1, *(_QWORD *)(v9 + 184), 128, _Max, &v213, 32, v155, 0, v157, v204);
  }
  if ( v166 )
  {
    NtfsCheckpointCurrentTransaction(a1);
    v66 = FileOffset;
    goto LABEL_274;
  }
  v67 = v199;
  *v199 = v213;
  v68 = v214;
  v67[1] = (__int128)v214;
  v69 = _mm_srli_si128(v68, 8).m128i_u64[0];
  v70 = v69;
  if ( v69 >= *(_QWORD *)(v9 + 32) && !v165 )
  {
    v71 = *(_QWORD *)(v9 + 24);
    if ( v69 > v71 )
    {
      NtfsAddSparseAllocation(a1, v69 - v71);
      v70 = v214.m128i_i64[1];
    }
    *(_QWORD *)(v9 + 464) = v70;
    *(_QWORD *)(v9 + 32) = v214.m128i_i64[1];
    *(_QWORD *)(v9 + 40) = v214.m128i_i64[1];
    LOBYTE(v71) = 1;
    NtfsWriteFileSizes(a1, v9, 0, v71, 1, 0);
    NtfsDeleteAllocation(a1, (v214.m128i_i64[1] >> *v176) - 1, 1, 0);
    v61 = *((_QWORD *)&v213 + 1);
    v72 = v213 + 2LL * *((_QWORD *)&v213 + 1);
    v73 = *(_QWORD *)(v9 + 472);
    if ( v72 < v73 )
    {
      v74 = *(union _LARGE_INTEGER *)((char *)&v213 + 8);
      FileOffset = *(union _LARGE_INTEGER *)((char *)&v213 + 8);
    }
    else
    {
      v74.QuadPart = v72 - v73;
      FileOffset = v74;
    }
    if ( *(_QWORD *)(v9 + 576) != v74.QuadPart )
    {
      KeAcquireGuardedMutex((PKGUARDED_MUTEX)(*(_QWORD *)(v9 + 192) + 720LL));
      v75 = *(unsigned int *)v179;
      v76 = (v75 + *(_QWORD *)(v9 + 576)) >> *v176;
      v77 = FileOffset;
      v78 = (v75 + FileOffset.QuadPart) >> *v176;
      v79 = *v200;
      if ( v78 - v76 <= 0 )
      {
        v86 = v78 - v76 + v79;
        *v200 = v86;
        if ( v86 < *(_QWORD *)(a2 + 8312) )
          *(_QWORD *)(a2 + 8312) = v86;
        v87 = *(_QWORD *)(a2 + 304) - (v86 >> 8) - *(_QWORD *)(a2 + 6368) - v86;
        if ( v87 <= 0 )
          v87 = 0;
        do
        {
          v88 = *(_QWORD *)(v48 + 8344);
          v89 = v88;
          if ( v87 < v88 )
            v89 = _InterlockedCompareExchange64((volatile signed __int64 *)(v48 + 8344), v87, v88);
        }
        while ( v89 != v88 );
        do
        {
          v90 = *(_QWORD *)(v48 + 8352);
          v91 = v90;
          if ( v87 > v90 )
            v91 = _InterlockedCompareExchange64((volatile signed __int64 *)(v48 + 8352), v87, v90);
        }
        while ( v91 != v90 );
      }
      else
      {
        v80 = v78 - v76 + v79;
        *v200 = v80;
        if ( v80 > *(_QWORD *)(a2 + 8320) )
          *(_QWORD *)(a2 + 8320) = v80;
        v81 = *(_QWORD *)(a2 + 304) - (v80 >> 8) - *(_QWORD *)(a2 + 6368) - v80;
        if ( v81 <= 0 )
          v81 = 0;
        do
        {
          v82 = *(_QWORD *)(v48 + 8344);
          v83 = v82;
          if ( v81 < v82 )
            v83 = _InterlockedCompareExchange64((volatile signed __int64 *)(v48 + 8344), v81, v82);
        }
        while ( v83 != v82 );
        do
        {
          v84 = *(_QWORD *)(v48 + 8352);
          v85 = v84;
          if ( v81 > v84 )
            v85 = _InterlockedCompareExchange64((volatile signed __int64 *)(v48 + 8352), v81, v84);
        }
        while ( v85 != v84 );
      }
      *(union _LARGE_INTEGER *)(v9 + 576) = v77;
      KeReleaseGuardedMutex((PKGUARDED_MUTEX)(*(_QWORD *)(v9 + 192) + 720LL));
    }
  }
  v92 = *(_WORD *)(v9 + 460);
  if ( v92 >= 0 && !v165 )
  {
    NtfsChangeAttributeCompression(a1, v92 | 0x8000);
    NtfsUpdateDuplicateInfo(a1, *(_QWORD *)(v9 + 184));
    v180 = 0;
    v182 = *(union _LARGE_INTEGER *)(v9 + 576);
  }
  v93 = v165;
  if ( !v165 )
  {
    LOBYTE(v155) = 0;
    v94 = *(_QWORD *)v172;
    if ( !(unsigned __int8)NtfsLookupInFileRecord(a1, *(_QWORD *)v172, v181, 128, &_Info, 0, v155, 0, 0, v212) )
      goto LABEL_191;
    NtfsMapAttributeValue(a1, v94, &v188, &Size, &v175, v212);
    if ( Size < 0x20
      || (v61 = 18762, *(_WORD *)v188 != 18762)
      || !*(_WORD *)(v188 + 2)
      || (*(_DWORD *)(v188 + 4) & 1) == 0 )
    {
LABEL_186:
      if ( !v212[2] )
      {
        v212[2] = v175;
LABEL_190:
        v175 = 0;
        goto LABEL_191;
      }
      v61 = (__int64)v175;
      if ( v175 )
      {
        CcUnpinData(v175);
        goto LABEL_190;
      }
LABEL_191:
      v93 = v165;
      goto LABEL_192;
    }
    ExAcquireResourceExclusiveLite((PERESOURCE)(a2 + 8032), 1u);
    v95 = v188;
    v96 = *(_QWORD *)(v188 + 16);
    *(_QWORD *)(a2 + 8016) = v96;
    *(_QWORD *)(a2 + 8024) = *(_QWORD *)(v95 + 8);
    v97 = 0x4000;
    if ( v96 >= 0x4000 )
    {
      if ( v96 > 0x100000000LL )
      {
        *(_QWORD *)(a2 + 8016) = 0x100000000LL;
LABEL_183:
        if ( *(__int64 *)(a2 + 8024) < 0x100000 )
          *(_QWORD *)(a2 + 8024) = 0x100000;
        *(_DWORD *)(a2 + 8008) |= 1u;
        ExReleaseResourceLite((PERESOURCE)(a2 + 8032));
        goto LABEL_186;
      }
      v205 = 0x4000;
      while ( v97 < v96 )
      {
        v97 *= 4LL;
        v205 = v97;
      }
    }
    *(_QWORD *)(a2 + 8016) = v97;
    goto LABEL_183;
  }
LABEL_192:
  NtfsCleanupAttributeContext(v61, v212);
  Scb = (__int16 *)(a2 + 40);
  if ( *(_QWORD *)(a2 + 40) )
  {
    v66 = *(union _LARGE_INTEGER *)(v9 + 576);
    v182 = v66;
    v180 = 0;
    goto LABEL_274;
  }
  v210 = a2 + 40;
  *(_DWORD *)(*(_QWORD *)(v9 + 184) + 4LL) |= 0x8000u;
  if ( !v93 )
  {
    RtlInitializeGenericTableAvl(&Table, NtfsUsnTableCompare, NtfsUsnTableAllocate, TxfFreeTableSpace, 0);
    Size_4 = 1;
  }
  NtfsPreloadAllocationInternal(a1, 0x7FFFFFFFFFFFFFFFLL, 0);
  if ( *(_QWORD *)(v9 + 24) )
  {
    v99 = 0;
    v206 = 0;
    while ( !(unsigned __int8)NtfsLookupRealAllocationInternal(a1, (__int64)Length, (__int64)&v189, 0, 0) )
    {
      v99 += v189;
      if ( v99 == 0x7FFFFFFFFFFFFFFFLL )
      {
        *(_QWORD *)(a2 + 1928) = *(_QWORD *)(v9 + 32);
        break;
      }
      *(_QWORD *)(a2 + 1928) += v189 << *v176;
      v102 = *(_QWORD *)(v9 + 32);
      if ( *(_QWORD *)(a2 + 1928) >= v102 )
      {
        *(_QWORD *)(a2 + 1928) = v102;
        break;
      }
      v206 = v99;
    }
  }
  v100 = (_QWORD *)(a2 + 1928);
  v211 = (_QWORD *)(a2 + 1928);
  v101 = v214.m128i_i64[1];
  if ( *(_QWORD *)(a2 + 1928) >= v214.m128i_i64[1] )
    v101 = *(_QWORD *)(a2 + 1928);
  else
    *v100 = v214.m128i_i64[1];
  v103 = *(_QWORD *)(a2 + 1936);
  *(_QWORD *)v171 = v103;
  if ( v103 < v101 )
  {
    v103 = v101;
    *(_QWORD *)v171 = v101;
  }
  if ( !*(_QWORD *)(*(_QWORD *)(v9 + 288) + 16LL) )
  {
    v104 = v101 & 0xFFFFFFFFFFC00000uLL;
    *(_QWORD *)(a2 + 1952) = v104;
    if ( v104 )
      *(_QWORD *)(a2 + 1952) = v104 - 0x400000;
    LOBYTE(v98) = 1;
    NtfsCreateInternalAttributeStream(a1, v9, v98, 0, 0, 0);
    v103 = *(_QWORD *)v171;
  }
LABEL_213:
  v105 = *(_QWORD *)(v9 + 32);
  if ( v103 < v105 && !v165 )
  {
    FileOffset.QuadPart = 0;
    *(_QWORD *)Length = v105 - v103;
    if ( v105 - v103 > 0x40000 - ((unsigned int)v103 & 0x3FFFF) )
      *(_QWORD *)Length = 0x40000 - ((unsigned int)v103 & 0x3FFFF);
    FileOffset.QuadPart = v103 - *(_QWORD *)(a2 + 1952);
    NtfsPerformPrefetch(*(PFILE_OBJECT *)(v9 + 280));
    CcMapData(*(PFILE_OBJECT *)(v9 + 280), &FileOffset, Length[0], 1u, &v194[1], &Buffer);
    *(union _LARGE_INTEGER *)&v193 = FileOffset;
    v106 = *(_QWORD *)Length;
    DWORD2(v193) = Length[0];
    v107 = (unsigned int *)Buffer;
    v194[0] = Buffer;
    v103 = *(_QWORD *)v171;
    while ( 1 )
    {
      if ( !v106 )
      {
        if ( v194[1] )
        {
          CcUnpinData(v194[1]);
          v194[1] = 0;
          v103 = *(_QWORD *)v171;
        }
        goto LABEL_213;
      }
      v108 = 4096 - (v103 & 0xFFF);
      v109 = v108;
      Size = v108;
      if ( v108 >= 0x3E && (v110 = *v107, (_DWORD)v110) )
      {
        v109 = *v107;
        Size = *v107;
        if ( (v110 & 7) == 0 && v110 <= v106 && (unsigned int)v110 <= v108 && v103 == *((_QWORD *)v107 + 3) )
        {
          if ( (unsigned __int16)(*((_WORD *)v107 + 2) - 1) <= 1u )
          {
            if ( (v107[10] & 0x80000000) != 0 )
            {
              RtlDeleteElementGenericTableAvl(&Table, v107);
            }
            else
            {
              inserted = RtlInsertElementGenericTableAvl(&Table, v107, *v107, &Size_6);
              if ( !Size_6 )
              {
                if ( *inserted == *(_DWORD *)Buffer )
                {
                  memmove(inserted, Buffer, *(unsigned int *)Buffer);
                }
                else
                {
                  RtlDeleteElementGenericTableAvl(&Table, Buffer);
                  RtlInsertElementGenericTableAvl(&Table, Buffer, *(_DWORD *)Buffer, &Size_6);
                }
              }
            }
            v107 = (unsigned int *)Buffer;
            v10 = *((_QWORD *)Buffer + 4);
            v196 = v10;
            v103 = *(_QWORD *)v171;
            v109 = Size;
            v106 = *(_QWORD *)Length;
          }
          goto LABEL_239;
        }
        v109 = 4096 - (v103 & 0xFFF);
        v112 = v108;
      }
      else
      {
        v112 = v108;
        v113 = v108 <= v106;
        if ( v108 > v106 )
          goto LABEL_237;
        if ( v108 )
          goto LABEL_239;
      }
      v113 = v112 <= v106;
LABEL_237:
      Size = v109;
      if ( !v113 )
      {
        v109 = v106;
        Size = v106;
      }
LABEL_239:
      v103 += v109;
      *(_QWORD *)v171 = v103;
      v106 -= v109;
      *(_QWORD *)Length = v106;
      v107 = (unsigned int *)((char *)v107 + v109);
      Buffer = v107;
    }
  }
  Size = 0;
  if ( Size_4 )
    v114 = RtlEnumerateGenericTableAvl(&Table, 1u);
  else
    v114 = 0;
  Buffer = v114;
  v115 = v114;
  while ( v115 )
  {
    ConstantNameB = 0;
    v195 = 0;
    v174 = -1073741823;
    if ( !a4 && *v100 + (_QWORD)v213 + *((_QWORD *)&v213 + 1) < *(_QWORD *)(v9 + 32) )
    {
      NtfsTrimUsnJournal(a1);
      v114 = Buffer;
    }
    v116 = *(_QWORD *)(v9 + 32);
    *(_QWORD *)v171 = v116;
    v117 = 4096 - (v116 & 0xFFF);
    if ( v117 < *(_DWORD *)v114 )
    {
      NtOfsPutData(a1, v9, -1, v117, 0);
      v116 = v117 + *(_QWORD *)v171;
      *(_QWORD *)v171 = v116;
      v114 = Buffer;
    }
    v114[3] = v116;
    *((_QWORD *)Buffer + 4) = v10;
    *((_DWORD *)Buffer + 10) |= 0x80000000;
    NtOfsPutData(a1, v9, -1, *(_DWORD *)Buffer, Buffer);
    v118 = *((_DWORD *)Buffer + 10);
    ConstantNameB = (PCUNICODE_STRING)*((_QWORD *)Buffer + 1);
    RtlDeleteElementGenericTableAvl(&Table, Buffer);
    ++Size;
    if ( (v118 & 0x200) == 0 )
    {
      v119 = Bcb;
      if ( Bcb )
      {
        CcUnpinData(Bcb);
        Bcb = 0;
      }
      LOBYTE(v119) = *(_BYTE *)(a2 + 492);
      v120 = ((unsigned __int64)ConstantNameB & 0xFFFFFFFFFFFFLL) << (char)v119;
      NtfsCleanupAttributeContext(v119, v204);
      memset(v204, 0, 0x58u);
      if ( (signed __int64)(v120 + *(unsigned int *)(a2 + 360)) <= *(_QWORD *)(*(_QWORD *)(a2 + 48) + 24LL) )
      {
        v121 = *v181;
        v208 = *v181;
        NtfsReadMftRecord(a1, a2, (int)&ConstantNameB, 0, TableContext, 0, &Bcb, &v195);
        v123 = v195;
        if ( *(_DWORD *)v195 == FileSignature
          && (*((_BYTE *)v195 + 22) & 1) != 0
          && *((_WORD *)v195 + 8) == HIWORD(ConstantNameB) )
        {
          v204[0] = (__int64)v195 + *((unsigned __int16 *)v195 + 10);
          if ( *(_DWORD *)v204[0] != 16 )
          {
            v121 = *(_QWORD *)v172;
            v10 = 0x140002B1037LL;
            NtfsAttachCorruption_BadOrOrphanFRS(a1, 2, 2822199, v122, (__int64)v181, *(__int64 *)v172, 0);
            NtfsAttachRepairInfoPriv(a1, 256, 0, 0x140002B1037LL);
            if ( NtfsStatusDebugFlags )
              NtfsStatusTraceAndDebugInternal(a1, 3221225730LL, 2822199);
            NtfsRaiseStatusInternal(a1, -1073741566, v207, v121, 2822199);
          }
          v204[2] = (__int64)Bcb;
          v204[1] = (__int64)v123;
          v204[5] = 0;
          v204[6] = 0;
          Bcb = 0;
          v124 = ConstantNameB;
          *v181 = (__int64)ConstantNameB;
          v125 = v172[0];
          *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v172 + 104LL) + 240LL) = v124;
          LODWORD(TableContexta) = 8;
          NtfsChangeAttributeValue(a1, v125, 64, (int)v171, (SIZE_T)TableContexta, 0, 0, 0, 0, v204);
          *v181 = v121;
          *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v172 + 104LL) + 240LL) = v121;
        }
      }
      if ( Bcb )
      {
        CcUnpinData(Bcb);
        Bcb = 0;
      }
    }
    if ( Size > 0xC8 )
    {
      NtfsCheckpointCurrentTransaction(a1);
      v182 = *(union _LARGE_INTEGER *)(v9 + 576);
      v180 = 0;
      Size = 0;
    }
    v115 = RtlEnumerateGenericTableAvl(&Table, 1u);
    v114 = v115;
    Buffer = v115;
    v100 = v211;
  }
  if ( (*v184 & 0x400000) != 0 && !v165 )
    NtfsSetVolumeInformationFlags(a1, a2, 16, 0, 1, 0);
  v180 = 0;
  v66 = *(union _LARGE_INTEGER *)(v9 + 576);
  v182 = v66;
  *(_QWORD *)Scb = v9;
  Size_7 = 0;
  KeAcquireGuardedMutex((PKGUARDED_MUTEX)(a2 + 664));
  SetFlagInterlocked(v215[0], 0x80000);
  ClearFlagInterlocked(v198, 0x400000);
  KeReleaseGuardedMutex((PKGUARDED_MUTEX)(a2 + 664));
  v215[0] = 0;
  v215[1] = -1;
  ExSetTimer(qword_140095660, -600000000LL * (unsigned int)dword_140095AAC, 0, v215);
LABEL_274:
  if ( a4 && *(_QWORD *)(a2 + 40) && (unsigned __int8)NtfsTelemetryGuard(2048) )
    NtfsTelemetryUsnCreate(a1, a2, &v202, v190);
  if ( Size_4 )
  {
    while ( 1 )
    {
      v126 = RtlEnumerateGenericTableAvl(&Table, 1u);
      Buffer = v126;
      if ( !v126 )
        break;
      RtlDeleteElementGenericTableAvl(&Table, v126);
    }
  }
  v127 = v180;
  if ( v180 )
  {
    v65 = v199;
    *v199 = *v180;
    v65[1] = v127[1];
  }
  if ( *(_QWORD *)(v9 + 576) != v66.QuadPart )
  {
    KeAcquireGuardedMutex((PKGUARDED_MUTEX)(*(_QWORD *)(v9 + 192) + 720LL));
    v128 = *(unsigned int *)v179;
    v129 = (v128 + v66.QuadPart) >> *v176;
    v130 = (v128 + *(_QWORD *)(v9 + 576)) >> *v176;
    v131 = v129 - v130;
    v132 = *v200;
    if ( v129 - v130 <= 0 )
    {
      v140 = v129 - v130 + v132;
      *v200 = v140;
      if ( v140 < *(_QWORD *)(a2 + 8312) )
        *(_QWORD *)(a2 + 8312) = v140;
      v141 = *(_QWORD *)(a2 + 304) - *(_QWORD *)(a2 + 6368) - (v140 >> 8) - v140;
      if ( v141 <= 0 )
        v141 = 0;
      v142 = v185;
      do
      {
        v143 = *(_QWORD *)(v142 + 8344);
        v144 = v143;
        if ( v141 < v143 )
          v144 = _InterlockedCompareExchange64((volatile signed __int64 *)(v142 + 8344), v141, v143);
      }
      while ( v144 != v143 );
      do
      {
        v145 = *(_QWORD *)(v142 + 8352);
        v146 = v145;
        if ( v141 > v145 )
          v146 = _InterlockedCompareExchange64((volatile signed __int64 *)(v142 + 8352), v141, v145);
      }
      while ( v146 != v145 );
    }
    else
    {
      v133 = v132 + v131;
      *v200 = v132 + v131;
      if ( v132 + v131 > *(_QWORD *)(a2 + 8320) )
        *(_QWORD *)(a2 + 8320) = v133;
      v134 = *(_QWORD *)(a2 + 304) - *(_QWORD *)(a2 + 6368) - (v133 >> 8) - v133;
      if ( v134 <= 0 )
        v134 = 0;
      v135 = v185;
      do
      {
        v136 = *(_QWORD *)(v135 + 8344);
        v137 = v136;
        if ( v134 < v136 )
          v137 = _InterlockedCompareExchange64((volatile signed __int64 *)(v135 + 8344), v134, v136);
      }
      while ( v137 != v136 );
      do
      {
        v138 = *(_QWORD *)(v135 + 8352);
        v139 = v138;
        if ( v134 > v138 )
          v139 = _InterlockedCompareExchange64((volatile signed __int64 *)(v135 + 8352), v134, v138);
      }
      while ( v139 != v138 );
    }
    *(union _LARGE_INTEGER *)(v9 + 576) = v66;
    KeReleaseGuardedMutex((PKGUARDED_MUTEX)(*(_QWORD *)(v9 + 192) + 720LL));
  }
  NtfsCleanupAttributeContext(v65, v212);
  v147 = v175;
  if ( v175 )
  {
    CcUnpinData(v175);
    v175 = 0;
  }
  NtfsCleanupAttributeContext(v147, v204);
  if ( Bcb )
  {
    CcUnpinData(Bcb);
    Bcb = 0;
  }
  if ( v194[1] )
  {
    CcUnpinData(v194[1]);
    v194[1] = 0;
  }
  if ( Size_7 )
    NtfsDecrementCloseCounts(a1, v9, 0, 1, 0);
  if ( !*(_QWORD *)(a2 + 40) )
  {
    *(_QWORD *)(v9 + 464) = 0;
    *(_QWORD *)(v9 + 24) = 0;
    if ( (*(_DWORD *)(v9 + 200) & 0x20000) == 0 || *(__int64 *)(v9 + 32) >= 0 || *(__int64 *)(v9 + 40) >= 0 )
      goto LABEL_330;
    v148 = *(_DWORD *)(v9 + 200);
    if ( (v148 & 0x20000) != 0 )
    {
      v149 = *(_QWORD *)(v9 + 464);
      if ( v149 < 0 )
      {
LABEL_328:
        *(_QWORD *)(v9 + 464) = 0;
        goto LABEL_329;
      }
      if ( *(__int64 *)(v9 + 40) > 0 )
      {
        if ( *(_QWORD *)(*(_QWORD *)(v9 + 288) + 16LL) )
        {
          if ( v149 > 0 )
            *(_QWORD *)(v9 + 464) = 0;
          goto LABEL_329;
        }
        goto LABEL_328;
      }
    }
LABEL_329:
    *(_QWORD *)(v9 + 40) = 0;
LABEL_330:
    *(_QWORD *)(v9 + 32) = 0;
    v150 = *(_DWORD *)(v9 + 200);
    if ( (v150 & 0x20000) != 0 )
    {
      v151 = *(_QWORD *)(v9 + 464);
      if ( v151 < 0 || *(__int64 *)(v9 + 40) > 0 && (!*(_QWORD *)(*(_QWORD *)(v9 + 288) + 16LL) || v151 > 0) )
        *(_QWORD *)(v9 + 464) = 0;
    }
    *(_QWORD *)(v9 + 40) = 0;
    *(_DWORD *)(v9 + 256) = 0;
    *(_DWORD *)(v9 + 512) |= 0x40u;
    *(_DWORD *)(*(_QWORD *)(v9 + 184) + 4LL) &= ~0x100u;
    NtfsTeardownStructures(a1, v9, 0);
  }
}

```

## disassembly

```asm
0x140110248  mov     [rsp+arg_18], r9d
0x14011024d  push    rbx
0x14011024e  push    rsi
0x14011024f  push    rdi
0x140110250  push    r12
0x140110252  push    r13
0x140110254  push    r14
0x140110256  push    r15
0x140110258  sub     rsp, 360h
0x14011025f  mov     rax, cs:__security_cookie
0x140110266  xor     rax, rsp
0x140110269  mov     [rsp+398h+var_48], rax
0x140110271  mov     rbx, r8
0x140110274  mov     qword ptr [rsp+398h+var_308], rbx
0x14011027c  mov     r15, rdx
0x14011027f  mov     r13, rcx
0x140110282  mov     rax, [rsp+398h+arg_28]
0x14011028a  mov     [rsp+398h+var_278], rax
0x140110292  mov     [rsp+398h+var_2D8], rcx
0x14011029a  mov     [rsp+398h+var_270], rdx
0x1401102a2  mov     [rsp+398h+var_230], rbx
0x1401102aa  mov     [rsp+398h+var_210], rax
0x1401102b2  xor     edx, edx; Val
0x1401102b4  lea     r8d, [rdx+68h]; Size
0x1401102b8  lea     rcx, [rsp+398h+Table]; void *
0x1401102c0  call    memset
0x1401102c5  xor     esi, esi
0x1401102c7  mov     qword ptr [rsp+398h+var_298], rsi
0x1401102cf  mov     [rsp+398h+var_330], rsi
0x1401102d4  lea     edi, [rsi+58h]
0x1401102d7  mov     r8d, edi; Size
0x1401102da  xor     edx, edx; Val
0x1401102dc  lea     rcx, [rsp+398h+var_1E8]; void *
0x1401102e4  call    memset
0x1401102e9  mov     r8d, edi; Size
0x1401102ec  xor     edx, edx; Val
0x1401102ee  lea     rcx, [rsp+398h+var_148]; void *
0x1401102f6  call    memset
0x1401102fb  xorps   xmm0, xmm0
0x1401102fe  movups  [rsp+398h+var_260], xmm0
0x140110306  movups  xmmword ptr [rsp+398h+var_250], xmm0
0x14011030e  mov     qword ptr [rsp+398h+var_310], rsi
0x140110316  mov     [rsp+398h+var_280], rsi
0x14011031e  mov     [rsp+398h+Src], rsi
0x140110326  movups  [rsp+398h+var_E8], xmm0
0x14011032e  movups  [rsp+398h+var_D8], xmm0
0x140110336  xorps   xmm1, xmm1
0x140110339  movups  [rsp+398h+var_208], xmm1
0x140110341  movups  [rsp+398h+var_1F8], xmm1
0x140110349  mov     [rsp+398h+var_288], rsi
0x140110351  mov     [rsp+398h+Bcb], rsi
0x140110356  mov     [rsp+398h+var_2F0], rsi
0x14011035e  mov     [rsp+398h+var_348], sil
0x140110363  mov     byte ptr [rsp+398h+Size+6], sil
0x140110368  mov     dword ptr [rsp+398h+Size], esi
0x14011036c  mov     qword ptr [rsp+398h+Length], rsi
0x140110374  lea     rdi, [r15+4]
0x140110378  mov     [rsp+398h+var_2A8], rdi
0x140110380  mov     eax, [rdi]
0x140110382  and     eax, 2000000h
0x140110387  mov     [rsp+398h+var_33C], eax
0x14011038b  mov     [rsp+398h+var_268], eax
0x140110392  neg     eax
0x140110394  sbb     ecx, ecx
0x140110396  neg     ecx
0x140110398  lea     r12d, [rsi+1]
0x14011039c  add     ecx, r12d
0x14011039f  lea     rax, [rsp+398h+var_298]
0x1401103a7  mov     [rsp+398h+var_368], rax
0x1401103ac  mov     dword ptr [rsp+398h+Buffer], r12d
0x1401103b1  mov     dword ptr [rsp+398h+TableContext], ecx
0x1401103b5  lea     r9d, [r12+7Fh]
0x1401103ba  lea     r8, JournalStreamName
0x1401103c1  mov     rdx, rbx
0x1401103c4  mov     rcx, r13
0x1401103c7  call    NtOfsCreateAttributeEx
0x1401103cc  cmp     eax, 0C0000034h
0x1401103d1  jz      loc_1401123A3
0x1401103d7  mov     r14, qword ptr [rsp+398h+var_298]
0x1401103df  test    r14, r14
0x1401103e2  jz      loc_1401123A3
0x1401103e8  mov     [rsp+398h+var_2A0], r15
0x1401103f0  mov     qword ptr [rsp+398h+var_C8], rdi
0x1401103f8  mov     byte ptr [rsp+398h+Size+4], sil
0x1401103fd  mov     [rsp+398h+var_338], sil
0x140110402  mov     byte ptr [rsp+398h+Size+7], r12b
0x140110407  mov     edi, esi
0x140110409  mov     [rsp+398h+var_238], rsi
0x140110411  mov     ebx, esi
0x140110413  mov     rax, [rsp+398h+var_2A8]
0x14011041b  mov     [rsp+398h+var_228], rax
0x140110423  mov     [rsp+398h+var_168], rax
0x14011042b  mov     [rsp+398h+var_347], sil
0x140110430  or      [r14+200h], r12d
0x140110437  xor     edx, edx; Val
0x140110439  lea     r8d, [rsi+58h]; Size
0x14011043d  lea     rcx, [rsp+398h+var_148]; void *
0x140110445  call    memset
0x14011044a  xor     edx, edx; Val
0x14011044c  lea     r8d, [rsi+58h]; Size
0x140110450  lea     rcx, [rsp+398h+var_1E8]; void *
0x140110458  call    memset
0x14011045d  mov     [rsp+398h+var_250+8], rsi
0x140110465  mov     rax, [rsp+398h+var_278]
0x14011046d  mov     rcx, [rax]
0x140110470  mov     qword ptr [rsp+398h+var_E8], rcx
0x140110478  mov     rax, [rax+8]
0x14011047c  mov     qword ptr [rsp+398h+var_E8+8], rax
0x140110484  mov     rax, [r15+778h]
0x14011048b  mov     qword ptr [rsp+398h+var_D8], rax
0x140110493  mov     rax, [r15+780h]
0x14011049a  mov     qword ptr [rsp+398h+var_D8+8], rax
0x1401104a2  cmp     [rsp+398h+arg_18], esi
0x1401104a9  jz      short loc_1401104B9
0x1401104ab  test    rcx, 0FFFFFFFFFDFFFFFFh
0x1401104b2  mov     byte ptr [rsp+398h+Size+5], r12b
0x1401104b7  jz      short loc_1401104BE
0x1401104b9  mov     byte ptr [rsp+398h+Size+5], sil
0x1401104be  mov     rax, [r14+240h]
0x1401104c5  mov     qword ptr [rsp+398h+FileOffset], rax
0x1401104cd  mov     [rsp+398h+var_2B8], rax
0x1401104d5  lea     rax, [r15+768h]
0x1401104dc  mov     [rsp+398h+var_220], rax
0x1401104e4  movups  xmm0, xmmword ptr [rax]
0x1401104e7  movups  [rsp+398h+var_208], xmm0
0x1401104ef  movups  xmm1, xmmword ptr [rax+10h]
0x1401104f3  movups  [rsp+398h+var_1F8], xmm1
0x1401104fb  lea     rax, [rsp+398h+var_208]
0x140110503  mov     [rsp+398h+var_2C8], rax
0x14011050b  mov     eax, [r14+0C8h]
0x140110512  test    al, 20h
0x140110514  jnz     short loc_140110524
0x140110516  xor     r8d, r8d
0x140110519  mov     rdx, r14
0x14011051c  mov     rcx, r13
0x14011051f  call    NtfsUpdateScbFromAttribute
0x140110524  mov     eax, [r14+0C8h]
0x14011052b  test    al, 8
0x14011052d  jz      loc_140110667
0x140110533  cmp     [rsp+398h+var_33C], esi
0x140110537  jnz     loc_140110667
0x14011053d  mov     rdx, [r14+0B8h]
0x140110544  lea     rax, [r14+108h]
0x14011054b  lea     r8, [rdx+8]
0x14011054f  lea     rcx, [rsp+398h+var_1E8]
0x140110557  mov     [rsp+398h+var_350], rcx
0x14011055c  mov     dword ptr [rsp+398h+var_358], esi
0x140110560  mov     [rsp+398h+var_360], rsi
0x140110565  mov     byte ptr [rsp+398h+var_368], sil
0x14011056a  mov     [rsp+398h+Buffer], rsi
0x14011056f  mov     [rsp+398h+TableContext], rax
0x140110574  mov     r9d, [r14+100h]
0x14011057b  mov     rcx, r13
0x14011057e  call    NtfsLookupInFileRecord
0x140110583  test    al, al
0x140110585  jnz     loc_14011061F
0x14011058b  mov     eax, [r14+200h]
0x140110592  test    al, 4
0x140110594  jnz     loc_14011061F
0x14011059a  mov     rax, [r14+0B8h]
0x1401105a1  lea     rcx, [rax+8]
0x1401105a5  mov     edx, 2
0x1401105aa  mov     byte ptr [rsp+398h+var_368], sil
0x1401105af  mov     [rsp+398h+Buffer], rax
0x1401105b4  mov     [rsp+398h+TableContext], rcx
0x1401105b9  mov     rbx, 0A9002B0B96h
0x1401105c3  mov     r8, rbx
0x1401105c6  mov     rcx, r13
0x1401105c9  call    NtfsAttachCorruption_BadOrOrphanFRS
0x1401105ce  mov     r9, rbx
0x1401105d1  xor     r8d, r8d
0x1401105d4  mov     edx, 200h
0x1401105d9  mov     rcx, r13
0x1401105dc  call    NtfsAttachRepairInfoPriv
0x1401105e1  mov     al, cs:NtfsStatusDebugFlags
0x1401105e7  test    al, al
0x1401105e9  jz      short loc_1401105FE
0x1401105eb  mov     edx, 0C0000102h
0x1401105f0  mov     r8d, 2B0B96h
0x1401105f6  mov     rcx, r13
0x1401105f9  call    NtfsStatusTraceAndDebugInternal
0x1401105fe  mov     r9, [r14+0B8h]
0x140110605  lea     r8, [r9+8]
0x140110609  mov     [rsp+398h+TableContext], 2B0B96h
0x140110612  mov     edx, 0C0000102h
0x140110617  mov     rcx, r13
0x14011061a  call    NtfsRaiseStatusInternal
0x14011061f  lea     rax, [rsp+398h+var_1E8]
0x140110627  mov     [rsp+398h+TableContext], rax; void *
0x14011062c  mov     r9b, r12b
0x14011062f  mov     r8, [rsp+398h+var_1E8]
0x140110637  mov     rdx, qword ptr [rsp+398h+var_308]; int
0x14011063f  mov     rcx, r13; int
0x140110642  call    NtfsConvertToNonresident
0x140110647  lea     rdx, [rsp+398h+var_1E8]
0x14011064f  call    NtfsCleanupAttributeContext
0x140110654  xor     edx, edx; Val
0x140110656  lea     r8d, [rdx+58h]; Size
0x14011065a  lea     rcx, [rsp+398h+var_1E8]; void *
0x140110662  call    memset
0x140110667  mov     rax, [rsp+398h+var_2A8]
0x14011066f  test    dword ptr [rax], 400000h
0x140110675  mov     eax, r12d
0x140110678  cmovz   eax, [rsp+398h+arg_20]
0x140110680  mov     dword ptr [rsp+398h+var_2E8], eax
0x140110687  mov     rax, qword ptr [rsp+398h+var_308]
0x14011068f  lea     rcx, [rax+8]
0x140110693  mov     [rsp+398h+var_2C0], rcx
0x14011069b  mov     [rsp+398h+var_178], rcx
0x1401106a3  lea     rdx, [rsp+398h+var_1E8]
0x1401106ab  mov     [rsp+398h+var_350], rdx
0x1401106b0  mov     dword ptr [rsp+398h+var_358], esi
0x1401106b4  mov     [rsp+398h+var_360], rsi
0x1401106b9  mov     byte ptr [rsp+398h+var_368], sil
0x1401106be  mov     [rsp+398h+Buffer], rsi
0x1401106c3  lea     rdx, $Max; "\b\n"
0x1401106ca  mov     [rsp+398h+TableContext], rdx
0x1401106cf  mov     r9d, 80h
0x1401106d5  mov     r8, rcx
0x1401106d8  mov     rdx, rax
0x1401106db  mov     rcx, r13
0x1401106de  call    NtfsLookupInFileRecord
0x1401106e3  mov     [rsp+398h+var_320], al
0x1401106e7  test    al, al
0x1401106e9  jz      loc_14011085A
0x1401106ef  cmp     dword ptr [rsp+398h+var_2E8], esi
0x1401106f6  jnz     loc_14011085A
0x1401106fc  mov     rax, [rsp+398h+var_1E8]
0x140110704  cmp     [rax+8], sil
0x140110708  jnz     short loc_140110713
0x14011070a  mov     ecx, [rax+10h]
0x14011070d  mov     dword ptr [rsp+398h+Size], ecx
0x140110711  jmp     short loc_14011071F
0x140110713  mov     eax, [rax+30h]
0x140110716  mov     dword ptr [rsp+398h+Size], eax
0x14011071a  mov     [rsp+398h+var_348], r12b
0x14011071f  lea     rax, [rsp+398h+var_1E8]
0x140110727  mov     [rsp+398h+Buffer], rax
0x14011072c  lea     rax, [rsp+398h+Bcb]
0x140110731  mov     [rsp+398h+TableContext], rax
0x140110736  lea     r9, [rsp+398h+Size]
0x14011073b  lea     r8, [rsp+398h+Src]
0x140110743  mov     rdx, qword ptr [rsp+398h+var_308]
0x14011074b  mov     rcx, r13
0x14011074e  call    NtfsMapAttributeValue
0x140110753  cmp     dword ptr [rsp+398h+Size], 10h
0x140110758  jnz     short loc_1401107A5
0x14011075a  mov     qword ptr [rsp+398h+var_D8+8], rsi
0x140110762  mov     rcx, 0FFFFF78000000014h
0x14011076c  mov     rax, [rcx]
0x14011076f  mov     qword ptr [rsp+398h+var_D8], rax
0x140110777  mov     [rsp+398h+var_348], r12b
0x14011077c  cmp     [rsp+398h+arg_18], esi
0x140110783  jnz     loc_140110824
0x140110789  mov     r8d, dword ptr [rsp+398h+Size]; Size
0x14011078e  mov     rdx, [rsp+398h+Src]; Src
0x140110796  lea     rcx, [rsp+398h+var_E8]; void *
0x14011079e  call    memmove
0x1401107a3  jmp     short loc_140110824
0x1401107a5  cmp     dword ptr [rsp+398h+Size], 20h ; ' '
0x1401107aa  jnz     short loc_14011080B
0x1401107ac  cmp     [rsp+398h+arg_18], esi
0x1401107b3  jz      short loc_1401107DC
0x1401107b5  mov     [rsp+398h+var_348], r12b
0x1401107ba  mov     rcx, [rsp+398h+Src]
0x1401107c2  mov     rax, [rcx+18h]
0x1401107c6  mov     qword ptr [rsp+398h+var_D8+8], rax
0x1401107ce  mov     rax, [rcx+10h]
0x1401107d2  mov     qword ptr [rsp+398h+var_D8], rax
0x1401107da  jmp     short loc_140110824
0x1401107dc  mov     rax, [rsp+398h+Src]
0x1401107e4  movups  xmm0, xmmword ptr [rax]
0x1401107e7  movups  [rsp+398h+var_E8], xmm0
0x1401107ef  movups  xmm1, xmmword ptr [rax+10h]
0x1401107f3  movups  [rsp+398h+var_D8], xmm1
0x1401107fb  psrldq  xmm1, 8
0x140110800  movq    qword ptr [rsp+398h+var_D8+8], xmm1
0x140110809  jmp     short loc_140110824
0x14011080b  lea     r9, [rsp+398h+var_348]
0x140110810  mov     r8, [r14+20h]
0x140110814  lea     rdx, [rsp+398h+var_E8]
0x14011081c  mov     rcx, r15
0x14011081f  call    NtfsAdvanceUsnJournal
0x140110824  cmp     [rsp+398h+var_1D8], rsi
0x14011082c  jnz     short loc_140110842
0x14011082e  mov     rax, [rsp+398h+Bcb]
0x140110833  mov     [rsp+398h+var_1D8], rax
0x14011083b  mov     [rsp+398h+Bcb], rsi
0x140110840  jmp     short loc_140110873
0x140110842  mov     rcx, [rsp+398h+Bcb]; Bcb
0x140110847  test    rcx, rcx
0x14011084a  jz      short loc_140110873
0x14011084c  call    cs:__imp_CcUnpinData
0x140110853  nop     dword ptr [rax+rax+00h]
0x140110858  jmp     short loc_14011083B
0x14011085a  lea     r9, [rsp+398h+var_348]
0x14011085f  mov     r8, [r14+20h]
0x140110863  lea     rdx, [rsp+398h+var_E8]
0x14011086b  mov     rcx, r15
0x14011086e  call    NtfsAdvanceUsnJournal
  ... truncated ...
```
