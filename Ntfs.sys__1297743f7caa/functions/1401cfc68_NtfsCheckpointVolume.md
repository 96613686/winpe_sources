# NtfsCheckpointVolume

- ea: `0x1401cfc68`
- end: `0x1401d1fa4`
- name: `NtfsCheckpointVolume`
- size: `9020`
- prototype: `__int64 __usercall@<rax>(PVOID Context1@<rcx>, char, int, __int64)`
- caller_count: `10`
- callee_count: `49`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14003c454`
- `0x1400cc78c`
- `0x1400deecc`
- `0x140138c70`
- `0x1401cf490`
- `0x1401cf8b0`
- `0x1401f6448`
- `0x14021ec20`
- `0x1402301c0`
- `0x14023035c`

## callees

- `0x1400054e8`
- `0x140007ea0`
- `0x14000c290`
- `0x140014e74`
- `0x14002066c`
- `0x140020de0`
- `0x140021220`
- `0x1400224cc`
- `0x1400226f0`
- `0x140022a00`
- `0x140022da8`
- `0x1400284b0`
- `0x14002f230`
- `0x140038f44`
- `0x14003c34c`
- `0x14004062c`
- `0x140040d48`
- `0x14004a834`
- `0x1400592c0`
- `0x140059440`
- `0x140059740`
- `0x14012e540`
- `0x14013af60`
- `0x14013f3c4`
- `0x1401406b0`
- `0x1401418c0`
- `0x1401aab70`
- `0x1401ae858`
- `0x1401b2880`
- `0x1401b40d0`
- `0x1401bfc88`
- `0x1401c1c0c`
- `0x1401cf218`
- `0x1401cfc68`
- `0x1401d2528`
- `0x1401d2d3c`
- `0x1401f38a0`
- `0x1401f38e0`
- `0x1401ffeac`
- `0x14020955c`
- `0x1402096fc`
- `0x14020f3a0`
- `0x140223128`
- `0x14022ae10`
- `0x14022be40`
- `0x1402308d8`
- `0x1402737ec`
- `0x140274a58`
- `0x14029bc38`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1401d0c93`
- `ntoskrnl!ObfDereferenceObject` at `0x1401d0ee6`
- `ntoskrnl!ObfDereferenceObject` at `0x1401d1545`
- `ntoskrnl!ObfDereferenceObject` at `0x1401d0c93`
- `ntoskrnl!ObfDereferenceObject` at `0x1401d0ee6`
- `ntoskrnl!ObfDereferenceObject` at `0x1401d1545`
- `ntoskrnl!IoSetActivityIdThread` at `0x1401cfe7f`
- `ntoskrnl!IoSetActivityIdThread` at `0x1401d1ab8`
- `ntoskrnl!IoSetActivityIdThread` at `0x1401cfe7f`
- `ntoskrnl!IoSetActivityIdThread` at `0x1401d1ab8`
- `ntoskrnl!IoClearActivityIdThread` at `0x1401d1a71`
- `ntoskrnl!IoClearActivityIdThread` at `0x1401d1ae0`
- `ntoskrnl!IoClearActivityIdThread` at `0x1402b02a4`
- `ntoskrnl!IoClearActivityIdThread` at `0x1401d1a71`
- `ntoskrnl!IoClearActivityIdThread` at `0x1401d1ae0`
- `ntoskrnl!IoClearActivityIdThread` at `0x1402b02a4`
- `ntoskrnl!KeSetPriorityThread` at `0x1401d1df6`
- `ntoskrnl!KeSetPriorityThread` at `0x1401d1f2f`
- `ntoskrnl!KeSetPriorityThread` at `0x1402b024d`
- `ntoskrnl!KeSetPriorityThread` at `0x1401d1df6`
- `ntoskrnl!KeSetPriorityThread` at `0x1401d1f2f`
- `ntoskrnl!KeSetPriorityThread` at `0x1402b024d`
- `ntoskrnl!CcGetDirtyPages` at `0x1401d05fb`
- `ntoskrnl!CcGetDirtyPages` at `0x1401d05fb`
- `ntoskrnl!IoGetActivityIdThread` at `0x1401cfe5c`
- `ntoskrnl!IoGetActivityIdThread` at `0x1401cfe5c`
- `ntoskrnl!KeClearEvent` at `0x1401d1334`
- `ntoskrnl!KeClearEvent` at `0x1401d1cc2`
- `ntoskrnl!KeClearEvent` at `0x1401d1334`
- `ntoskrnl!KeClearEvent` at `0x1401d1cc2`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401d1375`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402cc501`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401d1375`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402cc501`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1401d1cd1`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1401d1d08`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1402cc4d3`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1401d1cd1`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1401d1d08`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1402cc4d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d09d0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d0d97`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d0e0d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d0ea4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d140e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d1761`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d17b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d1c7b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d1e69`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b0102`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b011d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b0138`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d09d0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d0d97`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d0e0d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d0ea4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d140e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d1761`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d17b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d1c7b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d1e69`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b0102`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b011d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b0138`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401d03b4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401d14a7`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401d03b4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401d14a7`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1401d1b2f`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1402cc51a`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1401d1b2f`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1402cc51a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d00e6`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d00fc`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d055b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d0576`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d093e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d0954`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d0a11`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d0a27`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d0cb1`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d0ddd`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d0df3`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d130b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d170e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d1e87`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d1ee8`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402b015b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402b01c4`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d00e6`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d00fc`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d055b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d0576`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d093e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d0954`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d0a11`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d0a27`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d0cb1`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d0ddd`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d0df3`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d130b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d170e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d1e87`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401d1ee8`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402b015b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402b01c4`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d00af`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d014e`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d015d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d030c`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d04e9`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d04f8`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d0923`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d09f8`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d0a76`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d0a85`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d0b4e`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d0e31`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d0e44`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d0f64`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d134a`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d1e28`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d1e40`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d1e53`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d1ea5`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d1eff`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b00ba`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b00d4`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b00e7`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b0181`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b01de`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d00af`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d014e`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d015d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d030c`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d04e9`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d04f8`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d0923`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d09f8`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d0a76`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d0a85`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d0b4e`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d0e31`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d0e44`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d0f64`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d134a`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d1e28`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d1e40`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d1e53`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d1ea5`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401d1eff`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b00ba`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b00d4`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b00e7`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b0181`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b01de`
- `ntoskrnl!ExAcquireFastMutex` at `0x1401cfecd`
- `ntoskrnl!ExAcquireFastMutex` at `0x1401cfecd`
- `ntoskrnl!ExReleaseFastMutex` at `0x1401cff0a`
- `ntoskrnl!ExReleaseFastMutex` at `0x1401cff0a`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401d0483`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401d049c`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401d0f44`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401d0483`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401d049c`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401d0f44`
- `ntoskrnl!CcFlushCache` at `0x1401d0c60`
- `ntoskrnl!CcFlushCache` at `0x1401d0c60`

## pseudocode

```c
void __fastcall NtfsCheckpointVolume(_DWORD *Context1, __int64 a2, char a3, char a4, char a5, char a6, __int64 a7)
{
  __int64 LastLsn; // rbx
  char v10; // r12
  PVOID QuadPart; // rdi
  __int64 v12; // rcx
  _QWORD *v13; // rcx
  _QWORD *ActivityIdThread; // rax
  char *v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // r8
  int v18; // r9d
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // rcx
  struct _ERESOURCE *v22; // rcx
  int v23; // eax
  __int64 FirstRestartTable; // rsi
  PVOID v25; // r11
  char v26; // cl
  unsigned __int16 *v27; // r11
  __int64 v28; // r9
  _DWORD *v29; // r8
  __int64 v30; // rax
  union _LARGE_INTEGER v31; // r9
  union _LARGE_INTEGER v32; // rdx
  unsigned int v33; // esi
  unsigned __int16 *v34; // rdx
  char v35; // si
  char v36; // di
  unsigned __int16 *v37; // rdx
  int v38; // esi
  __int64 v39; // rcx
  char *v40; // rcx
  __int64 v41; // rdx
  __int64 v42; // r8
  unsigned int v43; // esi
  PVOID v44; // r12
  unsigned __int16 *v45; // r8
  __int64 v46; // r9
  unsigned __int16 *v47; // rsi
  unsigned __int16 *v48; // rdx
  unsigned __int16 *v49; // rdx
  __int64 j; // rax
  unsigned __int16 *v51; // rax
  __int64 v52; // rcx
  __int64 v53; // rcx
  unsigned __int16 *v54; // rdx
  __int64 v55; // r9
  unsigned __int16 *v56; // r9
  __int64 v57; // r8
  char *v58; // r8
  __int64 v59; // r9
  unsigned int v60; // eax
  __int64 v61; // r12
  __int64 v62; // r8
  char v63; // r9
  __int64 v64; // rcx
  unsigned int v65; // eax
  unsigned int v66; // edx
  _QWORD *v67; // r8
  bool v68; // si
  struct _ERESOURCE *v69; // r12
  __int64 v70; // rax
  __int64 v71; // r8
  __int64 v72; // r9
  __int64 v73; // r8
  __int64 v74; // rbx
  unsigned __int16 *v75; // rdx
  __int64 v76; // rcx
  union _LARGE_INTEGER v77; // rcx
  union _LARGE_INTEGER v78; // rdx
  ULONG v79; // esi
  __int64 v80; // r9
  __int64 v81; // rcx
  char v82; // di
  __int64 v83; // rcx
  int v84; // r8d
  _QWORD *v85; // rcx
  unsigned int v86; // esi
  __int64 v87; // r12
  __int64 v88; // rdx
  _QWORD *v89; // rax
  __int64 v90; // rax
  __int64 *v91; // rdx
  int v92; // r9d
  char v93; // si
  __int64 i; // rsi
  __int64 v95; // rcx
  unsigned int v96; // eax
  __int64 v97; // rbx
  __int64 v98; // rax
  char v99; // bl
  __int64 v100; // rcx
  __int64 v101; // rdi
  __int64 v102; // rbx
  __int64 v104; // rcx
  signed __int64 v105; // rax
  __int64 *v106; // rdx
  NTSTATUS v107; // esi
  char v108; // [rsp+E9h] [rbp-437h] BYREF
  char v109; // [rsp+EAh] [rbp-436h]
  char v110; // [rsp+EBh] [rbp-435h]
  char v111; // [rsp+ECh] [rbp-434h]
  char v112; // [rsp+EDh] [rbp-433h]
  char v113; // [rsp+EEh] [rbp-432h]
  unsigned int RestartTableIndex; // [rsp+F0h] [rbp-430h] BYREF
  _WORD v115[2]; // [rsp+F4h] [rbp-42Ch] BYREF
  char v116; // [rsp+F8h] [rbp-428h]
  int v117; // [rsp+FCh] [rbp-424h]
  int v118; // [rsp+100h] [rbp-420h] BYREF
  union _LARGE_INTEGER FileOffset; // [rsp+108h] [rbp-418h] BYREF
  int v120; // [rsp+110h] [rbp-410h]
  unsigned int v121; // [rsp+114h] [rbp-40Ch]
  char v122; // [rsp+118h] [rbp-408h]
  int v123; // [rsp+11Ch] [rbp-404h]
  KPRIORITY Priority; // [rsp+120h] [rbp-400h]
  int v125; // [rsp+124h] [rbp-3FCh] BYREF
  __int64 v126; // [rsp+128h] [rbp-3F8h] BYREF
  PVOID PoolWithTag; // [rsp+130h] [rbp-3F0h]
  _QWORD *v128; // [rsp+138h] [rbp-3E8h] BYREF
  __int64 v129; // [rsp+140h] [rbp-3E0h] BYREF
  __int64 v130; // [rsp+148h] [rbp-3D8h]
  unsigned int v131; // [rsp+150h] [rbp-3D0h]
  PVOID P; // [rsp+158h] [rbp-3C8h]
  __int64 v133; // [rsp+160h] [rbp-3C0h] BYREF
  __int64 v134; // [rsp+168h] [rbp-3B8h]
  __int64 v135; // [rsp+170h] [rbp-3B0h]
  union _LARGE_INTEGER v136; // [rsp+178h] [rbp-3A8h]
  __int64 v137; // [rsp+180h] [rbp-3A0h]
  __int64 v138; // [rsp+188h] [rbp-398h]
  __int64 v139; // [rsp+190h] [rbp-390h]
  __int64 v140; // [rsp+198h] [rbp-388h]
  unsigned int v141; // [rsp+1A0h] [rbp-380h]
  unsigned __int16 *k; // [rsp+1A8h] [rbp-378h]
  unsigned __int16 *v143; // [rsp+1B0h] [rbp-370h]
  __int64 v144; // [rsp+1B8h] [rbp-368h]
  _DWORD *v145; // [rsp+1C0h] [rbp-360h]
  struct _IO_STATUS_BLOCK IoStatus; // [rsp+1C8h] [rbp-358h] BYREF
  __int64 v147; // [rsp+1D8h] [rbp-348h]
  PVOID v148; // [rsp+1E0h] [rbp-340h]
  _QWORD *v149; // [rsp+1E8h] [rbp-338h]
  __int64 v150; // [rsp+1F0h] [rbp-330h]
  union _LARGE_INTEGER v151; // [rsp+1F8h] [rbp-328h]
  _QWORD v152[28]; // [rsp+208h] [rbp-318h] BYREF
  _BYTE Resource[224]; // [rsp+2E8h] [rbp-238h] BYREF
  __int128 v154; // [rsp+3C8h] [rbp-158h] BYREF
  __int64 v155; // [rsp+3D8h] [rbp-148h]
  __int128 Context2; // [rsp+3E0h] [rbp-140h] BYREF
  PVOID Object[2]; // [rsp+3F0h] [rbp-130h]
  __int128 v158; // [rsp+400h] [rbp-120h] BYREF
  __int64 v159; // [rsp+410h] [rbp-110h] BYREF
  _QWORD v160[14]; // [rsp+418h] [rbp-108h] BYREF
  _QWORD v161[10]; // [rsp+488h] [rbp-98h] BYREF

  LOBYTE(LastLsn) = a4;
  v145 = Context1;
  v138 = a2;
  memset(v160, 0, sizeof(v160));
  memset(Resource, 0, sizeof(Resource));
  memset(v152, 0, sizeof(v152));
  v129 = 0;
  v108 = 0;
  v109 = 0;
  v10 = 0;
  RestartTableIndex = 0;
  v115[0] = 0;
  v118 = 0;
  v154 = 0;
  v155 = 0;
  if ( (*(_DWORD *)(a2 + 4) & 0x2000000) != 0 )
    return;
  P = 0;
  FileOffset.QuadPart = 0;
  v139 = 0;
  PoolWithTag = 0;
  QuadPart = (PVOID)NtfsLarge0.QuadPart;
  Priority = 16;
  v135 = 0;
  v121 = 0;
  v137 = 0;
  v110 = 0;
  v111 = 0;
  v112 = 0;
  v113 = 0;
  v140 = 0;
  if ( !(_BYTE)LastLsn && (Context1[4] & 0x200LL) != 0 )
  {
    v144 = MEMORY[0xFFFFF78000000320];
    if ( (dword_140095BE8 & 1) == 0 || (unsigned int)dword_1400953B0 * v144 > 300000000 )
    {
      if ( (*(_DWORD *)(a2 + 24) & 0x1000) == 0 )
        NtfsLockUnlockSystemFilePages(Context1, a2, 0);
      if ( *(_BYTE *)(a2 + 8417) )
        NtfsFspCloseInternal(0, a2, 0, 0, 0);
    }
  }
  if ( a3 )
    goto LABEL_4;
  KeAcquireGuardedMutex((PKGUARDED_MUTEX)(a2 + 576));
  while ( 1 )
  {
    v104 = *(unsigned int *)(a2 + 572);
    v125 = v104;
    if ( (v104 & 0x12) == 0 )
      break;
    KeReleaseGuardedMutex((PKGUARDED_MUTEX)(a2 + 576));
    if ( !a4 )
      return;
    v107 = KeWaitForSingleObject((PVOID)(a2 + 632), Executive, 0, 0, 0);
    if ( v107 < 0 )
    {
      if ( NtfsStatusDebugFlags
        && (unsigned int)v107 < 0xFFFFFFED
        && v107 != -1073741802
        && v107 != -1073741807
        && (unsigned int)(v107 + 2147483643) > 1
        && v107 != -1073741608 )
      {
        NtfsStatusTraceAndDebugInternal(Context1, (unsigned int)v107, 1443622);
      }
      NtfsRaiseStatusInternal((_DWORD)Context1, v107, 0, 0, 1443622);
      __debugbreak();
    }
    KeAcquireGuardedMutex((PKGUARDED_MUTEX)(a2 + 576));
    if ( (v125 & 2) != 0 && (*(_DWORD *)(a2 + 572) & 4) != 0 )
      a7 = 0;
  }
  if ( (*(_DWORD *)(a2 + 4) & 0x1000) == 0 || (a6 & 0xC) == 0 && a4 && a7 != *(_QWORD *)(a2 + 824) && (v104 & 0x24) != 0 )
    goto LABEL_307;
  if ( (Context1[4] & 0x200LL) != 0 )
  {
    v105 = _InterlockedExchangeAdd64((volatile signed __int64 *)(a2 + 7392), 0);
    if ( !v105 )
    {
      if ( (Context1[4] & 0x100000) == 0
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x100000000LL) != 0 )
      {
        McTemplateU0p_EtwWriteTransfer(v104, logsup_c1913, a2);
      }
      goto LABEL_304;
    }
    if ( (Context1[4] & 0x400LL) == 0 || v105 > MEMORY[0xFFFFF78000000320] )
    {
LABEL_307:
      KeReleaseGuardedMutex((PKGUARDED_MUTEX)(a2 + 576));
      return;
    }
  }
LABEL_304:
  *(_DWORD *)(a2 + 572) |= 0x12u;
  *(_QWORD *)(a2 + 1424) = KeGetCurrentThread();
  KeClearEvent((PRKEVENT)(a2 + 632));
  KeReleaseGuardedMutex((PKGUARDED_MUTEX)(a2 + 576));
  LOBYTE(LastLsn) = a4;
  if ( a4 )
  {
    Priority = KeSetPriorityThread(KeGetCurrentThread(), 16);
    v10 = RestartTableIndex;
    if ( Priority != 16 )
      v112 = 1;
  }
  else
  {
    v10 = RestartTableIndex;
  }
LABEL_4:
  v120 = 0;
  if ( !(_BYTE)LastLsn && (Context1[4] & 0x200LL) != 0 && NtfsLWWaitLogThreshold )
  {
    NtfsQueryLogFileUsage(*(_QWORD *)(a2 + 232), v115);
    v113 = 1;
    v122 = 1;
    v10 = v115[0];
    if ( v115[0] >= (unsigned int)NtfsLWWaitLogThreshold )
    {
      NtfsFlushLsnStreamsOnLogTooFull(Context1, a2, v115[0]);
      if ( (*(_DWORD *)(a2 + 4) & 0x8000823) != 1 )
        goto LABEL_133;
    }
    LOBYTE(LastLsn) = a4;
  }
  memset(v160, 0, sizeof(v160));
  memset(Resource, 0, sizeof(Resource));
  if ( a3 )
    goto LABEL_191;
  while ( 1 )
  {
    v144 = MEMORY[0xFFFFF78000000320];
    if ( (!Context1 || (Context1[4] & 0x100000LL) == 0)
      && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x100000000LL) != 0 )
    {
      McTemplateU0p_EtwWriteTransfer(v12, logsup_c2018, a2);
    }
    if ( Context1 && (v13 = (_QWORD *)*((_QWORD *)Context1 + 15)) != 0 )
    {
      *((_QWORD *)&v154 + 1) = *v13;
      v155 = v13[1];
      *(_QWORD *)&v154 = (char *)&v154 + 8;
      v15 = (char *)&v154 + 8;
    }
    else
    {
      ActivityIdThread = (_QWORD *)IoGetActivityIdThread();
      if ( ActivityIdThread )
      {
        *((_QWORD *)&v154 + 1) = *ActivityIdThread;
        v155 = ActivityIdThread[1];
        *(_QWORD *)&v154 = (char *)&v154 + 8;
        v15 = (char *)&v154 + 8;
      }
      else
      {
        *(_QWORD *)&v154 = 0;
        v15 = 0;
      }
    }
    v140 = IoSetActivityIdThread(v15);
    if ( (Microsoft_Windows_NtfsEnableBits & 0x800000) != 0 || (Microsoft_Windows_NtfsEnableBits & 0x1000000) != 0 )
    {
      if ( !v113 )
      {
        NtfsQueryLogFileUsage(*(_QWORD *)(a2 + 232), v115);
        v10 = v115[0];
      }
      if ( a4 )
      {
        if ( (Microsoft_Windows_NtfsEnableBits & 0x1000000) == 0 )
          goto LABEL_16;
        v91 = NTFS_ETW_CLEAN_CHECKPOINT_START;
      }
      else
      {
        if ( (Microsoft_Windows_NtfsEnableBits & 0x800000) == 0 )
          goto LABEL_16;
        v91 = NTFS_ETW_PERIODIC_CHECKPOINT_START;
      }
      McTemplateK0phh_EtwWriteTransfer(v16, (_DWORD)v91, v154, v18, *((_WORD *)Context1 + 196), v10);
    }
LABEL_16:
    v19 = *(_QWORD *)(a2 + 40);
    if ( v19 )
    {
      LOBYTE(v17) = 1;
      NtfsAcquireResourceShared(v16, v19, v17);
      ExAcquireFastMutex((PFAST_MUTEX)(a2 + 1992));
      v20 = *(_QWORD *)(a2 + 1976);
      if ( v20 == a2 + 1976 )
        v137 = *(_QWORD *)(*(_QWORD *)(a2 + 40) + 32LL);
      else
        v137 = *(_QWORD *)(*(_QWORD *)(v20 - 24) + 288LL);
      v147 = v137;
      ExReleaseFastMutex((PFAST_MUTEX)(a2 + 1992));
      v21 = *(_QWORD *)(a2 + 40);
      if ( *(_WORD *)v21 == 1794 )
        v22 = (struct _ERESOURCE *)(*(_QWORD *)(v21 + 104) + 64LL);
      else
        v22 = *(struct _ERESOURCE **)(v21 + 8);
      ExReleaseResourceLite(v22);
    }
    ExAcquireResourceExclusiveLite((PERESOURCE)(a2 + 1064), 1u);
    ExAcquireResourceExclusiveLite((PERESOURCE)(a2 + 1168), 1u);
    if ( (a6 & 1) != 0 )
    {
      v128 = 0;
      RestartTableIndex = 0;
      Context2 = 0;
      *(_OWORD *)Object = 0;
      v158 = 0;
      v159 = 0;
      IoStatus.Pointer = &Context2;
      IoStatus.Information = 56;
      RestartTableIndex = NtfsAllocateRestartTableIndex(Context1, a2 + 1064);
      v128 = 0;
      LfsGetActiveLsnRange(*(_QWORD *)(a2 + 232), (char *)&v158 + 8, &v159);
      LfsWrite(
        *(_QWORD *)(a2 + 232),
        1,
        (unsigned int)&IoStatus,
        v92,
        (__int64)&RestartTableIndex,
        (__int64)v128,
        (__int64)v128,
        0,
        a6 & 3,
        0,
        (__int64)&v128);
      NtfsFreeRestartTableIndex(Context1, a2 + 1064, RestartTableIndex);
      NtfsCommitCurrentTransaction(Context1);
    }
    LastLsn = LfsQueryLastLsn(*(_QWORD *)(a2 + 232));
    v160[1] = LastLsn;
    v134 = LastLsn;
    v129 = LastLsn;
    ExReleaseResourceLite((PERESOURCE)(a2 + 1168));
    ExReleaseResourceLite((PERESOURCE)(a2 + 1064));
    if ( a4 )
    {
      v72 = (unsigned int)++*(_DWORD *)(a2 + 4864);
      if ( (!Context1 || (Context1[4] & 0x100000LL) == 0)
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x100000000LL) != 0 )
      {
        McTemplateU0pd_EtwWriteTransfer(0, logsup_c2230, a2, v72);
      }
      if ( a5 )
      {
        NtfsAcquireAllFiles(Context1, a2, 7, v72);
        v111 = 1;
      }
      else
      {
        v93 = 0;
        LOBYTE(v71) = 1;
        NtfsAcquireSharedVcb(Context1, a2, v71);
        v109 = 1;
        ExAcquireResourceExclusiveLite((PERESOURCE)(a2 + 1064), 1u);
        *(_BYTE *)(a2 + 1281) = 1;
        if ( *(_WORD *)(*(_QWORD *)(a2 + 1272) + 4LL) )
        {
          KeClearEvent((PRKEVENT)(a2 + 1400));
          v93 = 1;
        }
        ExReleaseResourceLite((PERESOURCE)(a2 + 1064));
        if ( v93 )
          KeWaitForSingleObject((PVOID)(a2 + 1400), Executive, 0, 0, 0);
      }
      if ( !(unsigned __int8)NtfsIsVcbAvailableForThisRequest(Context1, a2) )
        goto LABEL_133;
      ExAcquireResourceExclusiveLite((PERESOURCE)(a2 + 832), 1u);
      v108 = 1;
      LfsResetUndoTotal(*(_QWORD *)(a2 + 232), 1, 4294959104LL);
      if ( a5 )
      {
        NtfsFlushVolume((int)Context1);
        for ( i = NtfsGetFirstRestartTable(a2 + 832); i; i = NtfsGetNextRestartTable(a2 + 832, i) )
          NtfsFreeAttributeEntry(Context1, a2, i);
      }
      else
      {
        LOBYTE(v84) = 1;
        NtfsFlushLsnStreams((_DWORD)Context1, a2, v84, 0, (__int64)&v108);
      }
      *(_DWORD *)(a2 + 572) |= 4u;
      while ( 1 )
      {
        v85 = *(_QWORD **)(a2 + 4928);
        if ( v85 == (_QWORD *)(a2 + 4928) )
          break;
        v88 = *v85;
        if ( *(_QWORD **)(*v85 + 8LL) != v85 || (v89 = (_QWORD *)v85[1], (_QWORD *)*v89 != v85) )
          __fastfail(3u);
        *v89 = v88;
        *(_QWORD *)(v88 + 8) = v89;
        ExFreePoolWithTag(v85, 0);
      }
      v86 = 1;
      if ( *(_DWORD *)(a2 + 4892) > 1u )
        v86 = *(_DWORD *)(a2 + 4892);
      InitializeNewTable(40, 8, v86 >= 2, v152);
      v130 = v152[26];
      v139 = v152[26];
      if ( v86 < 2 )
        InitializeNewTable(40, 5, 0, v152);
      else
        InitializeNewTable(48, 5, 1, v152);
      v87 = v152[26];
      PoolWithTag = (PVOID)v152[26];
      ExFreePoolWithTag(*(PVOID *)(a2 + 1040), 0);
      *(_QWORD *)(a2 + 1040) = v130;
      v139 = 0;
      if ( v86 != *(_DWORD *)(a2 + 4892) )
        NtfsUpdateOatVersion(a2, v86);
      NtfsCommitCurrentTransaction(Context1);
      ExAcquireResourceExclusiveLite((PERESOURCE)(a2 + 1064), 1u);
      ExAcquireResourceExclusiveLite((PERESOURCE)(a2 + 1168), 1u);
      ExFreePoolWithTag(*(PVOID *)(a2 + 1272), 0);
      *(_QWORD *)(a2 + 1272) = v87;
      PoolWithTag = 0;
      ExReleaseResourceLite((PERESOURCE)(a2 + 1168));
      ExReleaseResourceLite((PERESOURCE)(a2 + 1064));
      v160[1] = LfsQueryLastLsn(*(_QWORD *)(a2 + 232));
LABEL_48:
      if ( QuadPart )
      {
        if ( (__int64)QuadPart < LastLsn )
          LastLsn = (__int64)QuadPart;
        v134 = LastLsn;
      }
      v160[0] = *(unsigned int *)(a2 + 4892);
      v160[9] = *(_QWORD *)(a2 + 1320);
      v160[10] = *(unsigned int *)(a2 + 356);
      v160[11] = *(_QWORD *)(a2 + 1944);
      v160[12] = *(_QWORD *)(a2 + 1952);
      v135 = *(_QWORD *)(a2 + 40);
      if ( v135 )
      {
        v98 = v137;
        *(_QWORD *)(a2 + 1936) = v137;
        v160[8] = v98;
      }
      *(_QWORD *)(a2 + 824) = LastLsn;
      *(_QWORD *)(a2 + 1056) = LastLsn;
      v160[13] = LastLsn;
      LfsWriteRestartArea(*(_QWORD *)(a2 + 232), 112, v160, v121, a2 + 824);
      if ( (Context1[4] & 0x200LL) != 0 )
        _InterlockedExchange64((volatile __int64 *)(a2 + 7392), qword_140095A90);
      v35 = a4;
      if ( a4 )
      {
        *(_DWORD *)(a2 + 4856) = *(_DWORD *)(a2 + 4852);
        *(_DWORD *)(a2 + 4860) = 0;
        *(_QWORD *)(a2 + 1336) = 0;
        *(_QWORD *)(a2 + 1056) = *(_QWORD *)(a2 + 824);
        LfsResetUndoTotal(*(_QWORD *)(a2 + 232), 2, 8304);
        *(_DWORD *)(a2 + 5360) = 32;
      }
      *(_QWORD *)(a2 + 1304) = LfsQueryLastLsn(*(_QWORD *)(a2 + 232));
      v10 = 0;
      v36 = v108;
      goto LABEL_257;
    }
    Context2 = 0;
    *(_OWORD *)Object = 0;
    v158 = 0;
    v136.QuadPart = 0;
    v117 = 0;
    ExAcquireResourceSharedLite((PERESOURCE)(a2 + 1064), 1u);
    ExAcquireResourceSharedLite((PERESOURCE)(a2 + 1168), 1u);
    for ( j = NtfsGetFirstRestartTable(a2 + 1064); j; j = NtfsGetNextRestartTable(a2 + 1064, j) )
    {
      v95 = *(_QWORD *)(j + 8);
      if ( v95 )
      {
        if ( v95 < LastLsn )
          LastLsn = *(_QWORD *)(j + 8);
        v134 = LastLsn;
      }
    }
    if ( *(_DWORD *)(a2 + 1296) )
    {
      if ( *(_QWORD *)(a2 + 1288) < LastLsn )
        LastLsn = *(_QWORD *)(a2 + 1288);
      v134 = LastLsn;
    }
    v129 = LastLsn;
    v51 = *(unsigned __int16 **)(a2 + 1272);
    if ( v51[2] )
    {
      PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), *v51 * (unsigned int)v51[1] + 24, 0x4C46744Eu);
      memmove(
        PoolWithTag,
        *(const void **)(a2 + 1272),
        **(unsigned __int16 **)(a2 + 1272) * (unsigned int)*(unsigned __int16 *)(*(_QWORD *)(a2 + 1272) + 2LL) + 24);
      HIDWORD(v160[7]) = **(unsigned __int16 **)(a2 + 1272) * *(unsigned __int16 *)(*(_QWORD *)(a2 + 1272) + 2LL) + 24;
    }
    ExReleaseResourceLite((PERESOURCE)(a2 + 1168));
    ExReleaseResourceLite((PERESOURCE)(a2 + 1064));
    v10 = 0;
    NtfsInitializeRestartTable(
      (*(_DWORD *)(a2 + 4892) != 0 ? 40 : 44) + 8 * (*(_DWORD *)(a2 + 404) - 1),
      *(_DWORD *)(a2 + 5360),
      *(_DWORD *)(a2 + 4892) >= 2u,
      0,
      (PERESOURCE)Resource);
    ExAcquireResourceExclusiveLite((PERESOURCE)Resource, 1u);
    v110 = 1;
    ExAcquireResourceExclusiveLite((PERESOURCE)(a2 + 832), 1u);
    v108 = 1;
    if ( *(_DWORD *)(a2 + 4892) < 2u )
      v120 = NtfsCalculateNamedBytes(v52, a2);
    Object[0] = 0;
    *(_QWORD *)&v158 = 0;
    Context2 = (unsigned __int64)Resource;
    Object[1] = (PVOID)0x7FFFFFFFFFFFFFFFLL;
    *((_QWORD *)&v158 + 1) = &v118;
    CcGetDirtyPages(*(PVOID *)(a2 + 232), DirtyPageRoutine, Context1, &Context2);
    QuadPart = Object[1];
    v148 = Object[1];
    if ( !(_BYTE)v158 )
      break;
    ++*(_DWORD *)(a2 + 4876);
    if ( (!Context1 || (Context1[4] & 0x100000LL) == 0)
      && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x100000000LL) != 0 )
    {
      McTemplateU0pd_EtwWriteTransfer(v53, logsup_c2672, a2, *(unsigned int *)(a2 + 4876));
    }
    if ( Object[0] )
    {
      ObfDereferenceObject(Object[0]);
      Object[0] = 0;
    }
    Context1[98] = 1;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(Context1, 3221225864LL, 1444482);
    NtfsRaiseStatusInternal((_DWORD)Context1, -1073741432, 0, 0, 1444482);
LABEL_191:
    if ( (_BYTE)LastLsn )
    {
      v121 = 1;
      v123 = 1;
      if ( (a6 & 4) != 0 )
      {
        v12 = 3;
        v123 = 3;
        if ( (a6 & 8) != 0 )
          v12 = 11;
        v121 = v12;
        v123 = v12;
        if ( (dword_1400956B8 & 0x1000) != 0 )
        {
          v12 = (unsigned int)v12 | 4;
          v121 = v12;
          v123 = v12;
        }
      }
    }
  }
  ++*(_DWORD *)(a2 + 4868);
  if ( (!Context1 || (Context1[4] & 0x100000LL) == 0)
    && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x100000000LL) != 0 )
  {
    McTemplateU0pd_EtwWriteTransfer(v53, logsup_c2696, a2, *(unsigned int *)(a2 + 4868));
  }
  v45 = *(unsigned __int16 **)&Resource[208];
  *(_DWORD *)(a2 + 5360) = (*(_WORD *)(*(_QWORD *)&Resource[208] + 4LL) & 0xFFE0) + 32;
  if ( QuadPart == *(PVOID *)(a2 + 1328) )
  {
    ExReleaseResourceLite((PERESOURCE)(a2 + 832));
    v73 = 0;
    v36 = 0;
    v108 = 0;
    if ( !Object[0] )
      goto LABEL_134;
    IoStatus = 0;
    FileOffset.QuadPart = 0;
    v74 = *((_QWORD *)Object[0] + 3);
    v75 = *(unsigned __int16 **)(Context2 + 208);
    if ( (v75[3] & 1) != 0 )
      v76 = (unsigned int)*v75 * (DWORD2(Context2) - 1) + 24LL;
    else
      v76 = DWORD2(Context2);
    v77.QuadPart = (LONGLONG)v75 + v76;
    v136 = v77;
    if ( *(_DWORD *)(a2 + 4892) )
      v78 = *(union _LARGE_INTEGER *)(v77.QuadPart + 16);
    else
      v78 = *(union _LARGE_INTEGER *)(v77.QuadPart + 20);
    FileOffset = v78;
    v79 = *(_DWORD *)(v77.QuadPart + 8);
    if ( v74 == *(_QWORD *)(a2 + 40) )
    {
      v77.QuadPart = v78.QuadPart + *(_QWORD *)(a2 + 1952);
      FileOffset = v77;
    }
    v80 = (unsigned int)++*(_DWORD *)(a2 + 4888);
    if ( (!Context1 || (Context1[4] & 0x100000LL) == 0)
      && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x100000000LL) != 0 )
    {
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))McTemplateU0pd_EtwWriteTransfer)(
        (union _LARGE_INTEGER)v77.QuadPart,
        logsup_c2781,
        a2,
        v80);
    }
    LOBYTE(v78.LowPart) = 1;
    v82 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))NtfsAcquireScbForLazyWrite)(
            v74,
            (union _LARGE_INTEGER)v78.QuadPart,
            v73,
            v80);
    if ( (!Context1 || (Context1[4] & 0x100000) == 0)
      && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x100000000LL) != 0 )
    {
      McTemplateU0pp_EtwWriteTransfer(
        v81,
        logsup_c2790,
        a2,
        *(_QWORD *)(*(_QWORD *)(v74 + 184) + 8LL) & 0xFFFFFFFFFFFFLL);
    }
    CcFlushCache((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(v74 + 288) + 16LL), &FileOffset, v79, &IoStatus);
    if ( (!Context1 || (Context1[4] & 0x100000LL) == 0)
      && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x100000000LL) != 0 )
    {
      McTemplateU0pp_EtwWriteTransfer(v83, logsup_c2799, a2, Object[0]);
    }
    if ( v82 )
      NtfsReleaseScbFromLazyWrite(v74);
    ObfDereferenceObject(Object[0]);
LABEL_133:
    v36 = v108;
    v10 = 0;
  }
  else
  {
    if ( Object[0] )
    {
      ObfDereferenceObject(Object[0]);
      v45 = *(unsigned __int16 **)&Resource[208];
    }
    if ( QuadPart != (PVOID)0x7FFFFFFFFFFFFFFFLL )
      *(_QWORD *)(a2 + 1328) = QuadPart;
    if ( QuadPart )
    {
      if ( (__int64)QuadPart < *(_QWORD *)(a2 + 1056) )
        QuadPart = *(PVOID *)(a2 + 1056);
      v148 = QuadPart;
    }
    k = 0;
    if ( v45[2] )
    {
      v47 = v45 + 12;
      v54 = v45 + 12;
      for ( k = v45 + 12; ; k = v47 )
      {
        v55 = *v45;
        if ( (int)v54 - (int)v45 >= (unsigned int)v55 * v45[1] + 24 )
          break;
        if ( *(_DWORD *)v54 == -1 )
          goto LABEL_92;
        v47 = (unsigned __int16 *)((char *)v47 + v55);
        v54 = v47;
      }
    }
    v47 = 0;
LABEL_92:
    v136.QuadPart = (LONGLONG)v47;
    v49 = v47;
    while ( v47 )
    {
      if ( *((_DWORD *)v49 + 2) )
      {
        v56 = *(unsigned __int16 **)(a2 + 1040);
        if ( (v56[3] & 1) != 0 )
          v57 = (unsigned int)*v56 * (*((_DWORD *)v49 + 1) - 1) + 24LL;
        else
          v57 = *((unsigned int *)v49 + 1);
        v58 = (char *)v56 + v57;
        v58[12] = 1;
        *((_DWORD *)v49 + 1) = *(_DWORD *)(*((_QWORD *)v58 + 4) + 16LL);
        v59 = *(_QWORD *)(*((_QWORD *)v58 + 4) + 24LL);
        v130 = v59;
        if ( v59 == *(_QWORD *)(a2 + 40) )
        {
          v90 = *(_QWORD *)(a2 + 1952);
          if ( *(_DWORD *)(a2 + 4892) )
            *((_QWORD *)v49 + 2) += v90;
          else
            *(_QWORD *)(v49 + 10) += v90;
        }
        v60 = (unsigned int)(*((_DWORD *)v49 + 2) + *(_DWORD *)(a2 + 480)) >> *(_DWORD *)(a2 + 488);
        RestartTableIndex = v60;
        *((_DWORD *)v49 + 3) = v60;
        if ( *(_DWORD *)(a2 + 4892) )
        {
          if ( *((_QWORD *)v49 + 3) < (__int64)QuadPart )
            *((_QWORD *)v49 + 3) = QuadPart;
          v61 = *((__int64 *)v49 + 2) >> *(_DWORD *)(a2 + 488);
          *((_QWORD *)v49 + 2) = v61;
          v62 = (__int64)(v49 + 16);
        }
        else
        {
          *((_DWORD *)v49 + 4) = 0;
          if ( *(_QWORD *)(v49 + 14) < (__int64)QuadPart )
            *(_QWORD *)(v49 + 14) = QuadPart;
          v61 = *(__int64 *)(v49 + 10) >> *(_DWORD *)(a2 + 488);
          *(_QWORD *)(v49 + 10) = v61;
          v62 = (__int64)(v49 + 18);
        }
        v128 = (_QWORD *)v62;
        v149 = (_QWORD *)v62;
        v141 = v60;
        v150 = v61;
        v126 = 0;
        v133 = 0;
        v131 = 0;
        while ( v60 )
        {
          v63 = NtfsLookupNtfsMcbEntryWithSyncFlag(v59 + 400, v61, &v133, &v126, 0, 0, 0, 0);
          if ( !v63 || (v64 = v133, v133 == -1) )
          {
            v64 = 0;
            v133 = 0;
            v126 = RestartTableIndex;
            v63 = 0;
          }
          v65 = RestartTableIndex;
          if ( v126 > RestartTableIndex )
            v126 = RestartTableIndex;
          v66 = 0;
          v67 = v128;
          while ( 1 )
          {
            v131 = v66;
            if ( v66 >= (unsigned int)v126 )
              break;
            *v67++ = v64;
            v128 = v67;
            v149 = v67;
            if ( v63 )
              v133 = ++v64;
            ++v66;
          }
          v61 += v126;
          v150 = v61;
          v60 = v65 - v126;
          RestartTableIndex = v60;
          v141 = v60;
          v59 = v130;
        }
      }
      else
      {
        v96 = (_DWORD)v47 - (_DWORD)v45;
        if ( (v45[3] & 1) != 0 )
          v96 = (v96 - 24) / *v45 + 1;
        NtfsFreeRestartTableIndex(Context1, Resource, v96);
      }
      v143 = v47;
      v45 = *(unsigned __int16 **)&Resource[208];
      v46 = (unsigned __int16)**(_WORD **)&Resource[208];
      v47 = (unsigned __int16 *)((char *)v47 + v46);
      v48 = v47;
      v143 = v47;
      while ( (int)v48 - *(_DWORD *)&Resource[208] < (unsigned int)v46
                                                   * *(unsigned __int16 *)(*(_QWORD *)&Resource[208] + 2LL)
                                                   + 24 )
      {
        if ( *(_DWORD *)v48 == -1 )
          goto LABEL_71;
        v47 = (unsigned __int16 *)((char *)v47 + v46);
        v48 = v47;
        v143 = v47;
      }
      v47 = 0;
LABEL_71:
      v49 = v47;
      v136.QuadPart = (LONGLONG)v47;
    }
    if ( (*(_DWORD *)(a2 + 572) & 0x20) != 0 && v160[1] == *(_QWORD *)(a2 + 1304) && !v45[2] )
    {
      v69 = (struct _ERESOURCE *)(a2 + 1064);
      ExAcquireResourceSharedLite((PERESOURCE)(a2 + 1064), 1u);
      v68 = *(_WORD *)(*(_QWORD *)(a2 + 1272) + 4LL) == 0;
      ExReleaseResourceLite((PERESOURCE)(a2 + 1064));
    }
    else
    {
      v68 = 0;
      v69 = (struct _ERESOURCE *)(a2 + 1064);
    }
    if ( !v68 )
    {
      *(_DWORD *)(a2 + 572) &= ~0x20u;
      v23 = v120;
      if ( v120 )
      {
        v120 += 4;
        v43 = v23 + 4;
        v44 = ExAllocatePoolWithTag((POOL_TYPE)528, (unsigned int)(v23 + 4), 0x4C46744Eu);
        P = v44;
        memset(v44, 0, v43);
        FileOffset.QuadPart = (LONGLONG)v44;
        v151.QuadPart = (LONGLONG)v44;
      }
      FirstRestartTable = NtfsGetFirstRestartTable(a2 + 832);
LABEL_24:
      while ( FirstRestartTable )
      {
        v26 = (char)v25;
        v116 = (char)v25;
        if ( *(_BYTE *)(FirstRestartTable + 12) == (_BYTE)v25
          && *(PVOID *)(*(_QWORD *)(FirstRestartTable + 32) + 24LL) == v25 )
        {
          NtfsFreeAttributeEntry(Context1, a2, FirstRestartTable);
          v26 = 1;
          v116 = 1;
          LOWORD(v25) = 0;
        }
        if ( *(_DWORD *)(a2 + 4892) < 2u && !v26 )
        {
          v30 = *(_QWORD *)(FirstRestartTable + 32);
          if ( *(_WORD *)(v30 + 32) != (_WORD)v25 )
          {
            v31 = FileOffset;
            *(_WORD *)FileOffset.QuadPart = *(_WORD *)(v30 + 16);
            *(_WORD *)(v31.QuadPart + 2) = *(_WORD *)(*(_QWORD *)(FirstRestartTable + 32) + 32LL);
            memmove(
              (void *)(v31.QuadPart + 4),
              *(const void **)(*(_QWORD *)(FirstRestartTable + 32) + 40LL),
              *(unsigned __int16 *)(*(_QWORD *)(FirstRestartTable + 32) + 32LL));
            v32 = FileOffset;
            *(_WORD *)(FileOffset.QuadPart
                     + 2 * ((unsigned __int64)*(unsigned __int16 *)(FileOffset.QuadPart + 2) >> 1)
                     + 4) = 0;
            FileOffset.QuadPart = *(unsigned __int16 *)(v32.QuadPart + 2) + v32.QuadPart + 6;
            v151 = FileOffset;
          }
        }
        v130 = FirstRestartTable;
        v27 = *(unsigned __int16 **)(a2 + 1040);
        v28 = *v27;
        FirstRestartTable += v28;
        v29 = (_DWORD *)FirstRestartTable;
        v130 = FirstRestartTable;
        while ( (int)v29 - *(_DWORD *)(a2 + 1040) < (unsigned int)v28 * v27[1] + 24 )
        {
          if ( *v29 == -1 )
          {
            v25 = 0;
            goto LABEL_24;
          }
          FirstRestartTable += v28;
          v29 = (_DWORD *)FirstRestartTable;
          v130 = FirstRestartTable;
        }
        v25 = 0;
        FirstRestartTable = 0;
      }
      if ( P != v25 )
        *(_DWORD *)FileOffset.QuadPart = 0;
      if ( *(_DWORD *)(a2 + 4892) < 2u )
      {
        v37 = *(unsigned __int16 **)(*(_QWORD *)(a2 + 4920) + 208LL);
        if ( v37[2] != (_WORD)v25 )
        {
          v160[2] = NtfsWriteLog(
                      (_DWORD)Context1,
                      *(_QWORD *)(a2 + 48),
                      0,
                      29,
                      (__int64)v37,
                      *v37 * (unsigned int)v37[1] + 24,
                      (_DWORD)v25,
                      (__int64)v25,
                      (_DWORD)v25,
                      (__int64)v25,
                      (_DWORD)v25,
                      (_DWORD)v25,
                      (_DWORD)v25);
          LODWORD(v160[6]) = **(unsigned __int16 **)(*(_QWORD *)(a2 + 4920) + 208LL)
                           * *(unsigned __int16 *)(*(_QWORD *)(*(_QWORD *)(a2 + 4920) + 208LL) + 2LL)
                           + 24;
          v117 = 1;
        }
        ExReleaseResourceLite((PERESOURCE)(a2 + 832));
        v108 = 0;
        v38 = v120;
        if ( v120 )
        {
          v160[3] = NtfsWriteLog((_DWORD)Context1, *(_QWORD *)(a2 + 48), 0, 30, (__int64)P, v120, 0, 0, 0, 0, 0, 0, 0);
          HIDWORD(v160[6]) = v38;
          v33 = 1;
          v117 = 1;
        }
        else
        {
          v33 = v117;
        }
      }
      else
      {
        ExReleaseResourceLite((PERESOURCE)(a2 + 832));
        v108 = 0;
        v33 = 0;
      }
      if ( *(_WORD *)(*(_QWORD *)&Resource[208] + 4LL) )
      {
        v160[4] = NtfsWriteLog(
                    (_DWORD)Context1,
                    *(_QWORD *)(a2 + 48),
                    0,
                    31,
                    *(__int64 *)&Resource[208],
                    (unsigned __int16)**(_WORD **)&Resource[208]
                  * (unsigned int)*(unsigned __int16 *)(*(_QWORD *)&Resource[208] + 2LL)
                  + 24,
                    0,
                    0,
                    0,
                    0,
                    0,
                    0,
                    0);
        LODWORD(v160[7]) = (unsigned __int16)**(_WORD **)&Resource[208]
                         * *(unsigned __int16 *)(*(_QWORD *)&Resource[208] + 2LL)
                         + 24;
        v33 = 1;
        v117 = 1;
      }
      ExAcquireResourceExclusiveLite((PERESOURCE)(a2 + 1064), 1u);
      ExAcquireResourceExclusiveLite((PERESOURCE)(a2 + 1168), 1u);
      *(_DWORD *)(a2 + 572) &= ~4u;
      if ( PoolWithTag )
      {
        v160[5] = NtfsWriteLog(
                    (_DWORD)Context1,
                    *(_QWORD *)(a2 + 48),
                    0,
                    32,
                    (__int64)PoolWithTag,
                    HIDWORD(v160[7]),
                    0,
                    0,
                    0,
                    0,
                    0,
                    0,
                    0);
        v33 = 1;
        v117 = 1;
      }
      v34 = *(unsigned __int16 **)(a2 + 1272);
      if ( v34[2] <= v33 )
      {
        v39 = (unsigned int)Context1[7];
        if ( (_DWORD)v39 )
        {
          if ( (v34[3] & 1) != 0 )
            v39 = (unsigned int)*v34 * ((_DWORD)v39 - 1) + 24LL;
          v40 = (char *)v34 + v39;
          v41 = (unsigned int)(*((_DWORD *)v40 + 8) + 2);
          v42 = (unsigned int)(*((_DWORD *)v40 + 9) + 8304);
        }
        else
        {
          v41 = 2;
          v42 = 8304;
        }
        LfsResetUndoTotal(*(_QWORD *)(a2 + 232), v41, v42);
        if ( !*(_WORD *)(*(_QWORD *)&Resource[208] + 4LL) )
          *(_DWORD *)(a2 + 572) |= 0x20u;
      }
      ExReleaseResourceLite((PERESOURCE)(a2 + 1168));
      ExReleaseResourceLite((PERESOURCE)(a2 + 1064));
      goto LABEL_48;
    }
    if ( v160[1] == v129 )
    {
      memset(v161, 0, sizeof(v161));
      v125 = 80;
      LfsQueryLogFileInformation(*(_QWORD *)(a2 + 232), v161, &v125);
      v97 = v161[5];
      if ( v161[6] < v161[5] && (*(_DWORD *)(a2 + 4) & 0x20) == 0 && (int)NtfsFlushDiskCache(*(_QWORD *)(a2 + 216)) >= 0 )
      {
        LfsSetDurableLsn(*(_QWORD *)(a2 + 232), v97);
        ++v129;
      }
    }
    v70 = *(_QWORD *)(a2 + 1040);
    if ( !*(_WORD *)(v70 + 4) && *(_WORD *)(v70 + 2) > 0x10u )
    {
      InitializeNewTable(40, 8, *(_DWORD *)(a2 + 4892) >= 2u, v152);
      ExFreePoolWithTag(*(PVOID *)(a2 + 1040), 0);
      *(_QWORD *)(a2 + 1040) = v152[26];
      if ( *(_QWORD *)(a2 + 4920) != a2 + 832 )
      {
        InitializeNewTable(44, 8, 0, v152);
        ExFreePoolWithTag(*(PVOID *)(*(_QWORD *)(a2 + 4920) + 208LL), 0);
        *(_QWORD *)(*(_QWORD *)(a2 + 4920) + 208LL) = v152[26];
      }
    }
    ExReleaseResourceLite((PERESOURCE)(a2 + 832));
    v36 = 0;
    v108 = 0;
    ExAcquireResourceExclusiveLite(v69, 1u);
    ExAcquireResourceExclusiveLite((PERESOURCE)(a2 + 1168), 1u);
    v10 = 1;
    if ( !*(_WORD *)(*(_QWORD *)(a2 + 1272) + 4LL) )
    {
      LfsResetUndoTotal(*(_QWORD *)(a2 + 232), 2, 8304);
      if ( *(_WORD *)(*(_QWORD *)(a2 + 1272) + 2LL) > 0xAu )
      {
        InitializeNewTable(*(_DWORD *)(a2 + 4892) < 2u ? 40 : 48, 5, *(_DWORD *)(a2 + 4892) >= 2u, v152);
        ExFreePoolWithTag(*(PVOID *)(a2 + 1272), 0);
        *(_QWORD *)(a2 + 1272) = v152[26];
      }
    }
  }
LABEL_134:
  v35 = a4;
LABEL_257:
  if ( v110 )
    NtfsFreeRestartTable((PERESOURCE)Resource);
  if ( v36 )
    ExReleaseResourceLite((PERESOURCE)(a2 + 832));
  if ( v10 )
  {
    ExReleaseResourceLite((PERESOURCE)(a2 + 1168));
    ExReleaseResourceLite((PERESOURCE)(a2 + 1064));
  }
  if ( P )
    ExFreePoolWithTag(P, 0);
  if ( PoolWithTag )
    ExFreePoolWithTag(PoolWithTag, 0);
  if ( Context1[7] )
  {
    ExAcquireResourceExclusiveLite((PERESOURCE)(a2 + 1064), 1u);
    NtfsFreeRestartTableIndex(Context1, a2 + 1064, (unsigned int)Context1[7]);
    ExReleaseResourceLite((PERESOURCE)(a2 + 1064));
    Context1[7] = 0;
  }
  if ( v111 )
    NtfsReleaseAllFiles(Context1, a2, 6);
  v99 = v109;
  v100 = 0;
  if ( v109 )
  {
    if ( v35 )
    {
      ExAcquireResourceExclusiveLite((PERESOURCE)(a2 + 1064), 1u);
      *(_BYTE *)(a2 + 1281) = 0;
      ExReleaseResourceLite((PERESOURCE)(a2 + 1064));
    }
    NtfsReleaseVcb(Context1, a2);
    v100 = 0;
    v99 = 0;
    v109 = 0;
  }
  v101 = v135;
  if ( !a3 && (!v135 || v35) )
  {
    NtfsReleaseCheckpointSynchronization(0, a2, 19);
    v100 = 0;
  }
  if ( v112 )
    KeSetPriorityThread(KeGetCurrentThread(), Priority);
  if ( v35 )
  {
    if ( (Microsoft_Windows_NtfsEnableBits & 0x1000000) == 0 )
      goto LABEL_277;
    v106 = NTFS_ETW_CLEAN_CHECKPOINT_COMPLETE;
LABEL_342:
    McTemplateK0pq_EtwWriteTransfer(v100, v106, v154);
    goto LABEL_277;
  }
  if ( (Microsoft_Windows_NtfsEnableBits & 0x800000) != 0 )
  {
    v106 = NTFS_ETW_PERIODIC_CHECKPOINT_COMPLETE;
    goto LABEL_342;
  }
LABEL_277:
  IoClearActivityIdThread(v140);
  if ( a3 )
    goto LABEL_282;
  if ( !v99 )
  {
    v99 = NtfsAcquireSharedVcb(Context1, a2, 0);
    v109 = v99;
  }
  if ( v99 && (*(_DWORD *)(a2 + 4) & 0x21) == 1 )
  {
LABEL_282:
    v102 = IoSetActivityIdThread(v154);
    NtfsFreeRecentlyDeallocated(Context1, a2, &v129, 0);
    IoClearActivityIdThread(v102);
    v99 = v109;
  }
  if ( v99 )
  {
    NtfsReleaseVcb(Context1, a2);
    v109 = 0;
  }
  if ( !v35 && v101 && !a3 )
    NtfsTrimUsnJournal((int)Context1);
}

```

## disassembly

```asm
0x1401cfc68  mov     [rsp+arg_18], r9b
0x1401cfc6d  mov     [rsp+arg_10], r8b
0x1401cfc72  push    rbx
0x1401cfc73  push    rsi
0x1401cfc74  push    rdi
0x1401cfc75  push    r12
0x1401cfc77  push    r13
0x1401cfc79  push    r14
0x1401cfc7b  push    r15
0x1401cfc7d  sub     rsp, 470h
0x1401cfc84  mov     rax, cs:__security_cookie
0x1401cfc8b  xor     rax, rsp
0x1401cfc8e  mov     [rsp+4A8h+var_48], rax
0x1401cfc96  mov     bl, r9b
0x1401cfc99  mov     r14, rdx
0x1401cfc9c  mov     r13, rcx
0x1401cfc9f  mov     [rsp+4A8h+var_360], rcx
0x1401cfca7  mov     [rsp+4A8h+var_398], rdx
0x1401cfcaf  xor     edx, edx; Val
0x1401cfcb1  lea     r8d, [rdx+70h]; Size
0x1401cfcb5  lea     rcx, [rsp+4A8h+var_108]; void *
0x1401cfcbd  call    memset
0x1401cfcc2  mov     edi, 0E0h
0x1401cfcc7  mov     r8d, edi; Size
0x1401cfcca  xor     edx, edx; Val
0x1401cfccc  lea     rcx, [rsp+4A8h+Resource]; void *
0x1401cfcd4  call    memset
0x1401cfcd9  mov     r8d, edi; Size
0x1401cfcdc  xor     edx, edx; Val
0x1401cfcde  lea     rcx, [rsp+4A8h+var_318]; void *
0x1401cfce6  call    memset
0x1401cfceb  xor     esi, esi
0x1401cfced  mov     [rsp+4A8h+var_3E0], rsi
0x1401cfcf5  mov     [rsp+4A8h+var_437], sil
0x1401cfcfa  mov     [rsp+4A8h+var_436], sil
0x1401cfcff  mov     r12d, esi
0x1401cfd02  mov     [rsp+4A8h+var_430], esi
0x1401cfd06  mov     [rsp+4A8h+var_42C], si
0x1401cfd0b  mov     [rsp+4A8h+var_420], esi
0x1401cfd12  xorps   xmm0, xmm0
0x1401cfd15  xor     eax, eax
0x1401cfd17  movups  [rsp+4A8h+var_158], xmm0
0x1401cfd1f  mov     [rsp+4A8h+var_148], rax
0x1401cfd27  test    dword ptr [r14+4], 2000000h
0x1401cfd2f  jnz     loc_1401D1B01
0x1401cfd35  mov     [rsp+4A8h+P], rsi
0x1401cfd3d  mov     qword ptr [rsp+4A8h+FileOffset], rsi
0x1401cfd45  mov     [rsp+4A8h+var_390], rax
0x1401cfd4d  mov     [rsp+4A8h+var_3F0], rsi
0x1401cfd55  mov     rdi, qword ptr cs:NtfsLarge0
0x1401cfd5c  mov     [rsp+4A8h+Priority], 10h
0x1401cfd67  mov     [rsp+4A8h+var_3B0], rsi
0x1401cfd6f  mov     [rsp+4A8h+var_40C], esi
0x1401cfd76  mov     [rsp+4A8h+var_3A0], rsi
0x1401cfd7e  mov     [rsp+4A8h+var_435], sil
0x1401cfd83  mov     [rsp+4A8h+var_438], sil
0x1401cfd88  mov     [rsp+4A8h+var_434], sil
0x1401cfd8d  mov     [rsp+4A8h+var_433], sil
0x1401cfd92  mov     [rsp+4A8h+var_432], sil
0x1401cfd97  mov     [rsp+4A8h+var_388], rsi
0x1401cfd9f  lea     r15d, [rsi+1]
0x1401cfda3  test    bl, bl
0x1401cfda5  jz      loc_1401D1BDA
0x1401cfdab  cmp     [rsp+4A8h+arg_10], sil
0x1401cfdb3  jz      loc_1401D1B25
0x1401cfdb9  mov     esi, 100000h
0x1401cfdbe  mov     [rsp+4A8h+var_410], 0
0x1401cfdc9  test    bl, bl
0x1401cfdcb  jnz     short loc_1401CFDE6
0x1401cfdcd  mov     eax, [r13+10h]
0x1401cfdd1  bt      rax, 9
0x1401cfdd6  jnb     short loc_1401CFDE6
0x1401cfdd8  mov     eax, cs:NtfsLWWaitLogThreshold
0x1401cfdde  test    eax, eax
0x1401cfde0  jnz     loc_1401D0FFC
0x1401cfde6  xor     edx, edx; Val
0x1401cfde8  lea     r8d, [rdx+70h]; Size
0x1401cfdec  lea     rcx, [rsp+4A8h+var_108]; void *
0x1401cfdf4  call    memset
0x1401cfdf9  xor     edx, edx; Val
0x1401cfdfb  mov     r8d, 0E0h; Size
0x1401cfe01  lea     rcx, [rsp+4A8h+Resource]; void *
0x1401cfe09  call    memset
0x1401cfe0e  xor     eax, eax
0x1401cfe10  cmp     [rsp+4A8h+arg_10], al
0x1401cfe17  jnz     loc_1401D10EB
0x1401cfe1d  mov     rax, 0FFFFF78000000320h
0x1401cfe27  mov     rax, [rax]
0x1401cfe2a  mov     [rsp+4A8h+var_368], rax
0x1401cfe32  xor     ebx, ebx
0x1401cfe34  test    r13, r13
0x1401cfe37  jz      loc_1401D0FDB
0x1401cfe3d  mov     eax, [r13+10h]
0x1401cfe41  test    rsi, rax
0x1401cfe44  jz      loc_1401D0FDB
0x1401cfe4a  test    r13, r13
0x1401cfe4d  jz      short loc_1401CFE5C
0x1401cfe4f  mov     rcx, [r13+78h]
0x1401cfe53  test    rcx, rcx
0x1401cfe56  jnz     loc_1401D0FA7
0x1401cfe5c  call    cs:__imp_IoGetActivityIdThread
0x1401cfe63  nop     dword ptr [rax+rax+00h]
0x1401cfe68  mov     rcx, rax
0x1401cfe6b  test    rax, rax
0x1401cfe6e  jnz     loc_1401D105A
0x1401cfe74  mov     qword ptr [rsp+4A8h+var_158], rbx
0x1401cfe7c  mov     rcx, rbx
0x1401cfe7f  call    cs:__imp_IoSetActivityIdThread
0x1401cfe86  nop     dword ptr [rax+rax+00h]
0x1401cfe8b  mov     [rsp+4A8h+var_388], rax
0x1401cfe93  mov     al, byte ptr cs:Microsoft_Windows_NtfsEnableBits+2
0x1401cfe99  test    al, al
0x1401cfe9b  js      loc_1401D115D
0x1401cfea1  test    byte ptr cs:Microsoft_Windows_NtfsEnableBits+3, r15b
0x1401cfea8  jnz     loc_1401D115D
0x1401cfeae  mov     rdx, [r14+28h]
0x1401cfeb2  test    rdx, rdx
0x1401cfeb5  jz      loc_1401D0A04
0x1401cfebb  mov     r8b, r15b
0x1401cfebe  call    NtfsAcquireResourceShared
0x1401cfec3  lea     rbx, [r14+7C8h]
0x1401cfeca  mov     rcx, rbx; FastMutex
0x1401cfecd  call    cs:__imp_ExAcquireFastMutex
0x1401cfed4  nop     dword ptr [rax+rax+00h]
0x1401cfed9  lea     rax, [r14+7B8h]
0x1401cfee0  mov     rcx, [rax]
0x1401cfee3  cmp     rcx, rax
0x1401cfee6  jz      loc_1401D108E
0x1401cfeec  mov     rax, [rcx-18h]
0x1401cfef0  mov     rax, [rax+120h]
0x1401cfef7  mov     [rsp+4A8h+var_3A0], rax
0x1401cfeff  mov     [rsp+4A8h+var_348], rax
0x1401cff07  mov     rcx, rbx; FastMutex
0x1401cff0a  call    cs:__imp_ExReleaseFastMutex
0x1401cff11  nop     dword ptr [rax+rax+00h]
0x1401cff16  mov     rcx, [r14+28h]
0x1401cff1a  mov     eax, 702h
0x1401cff1f  cmp     ax, [rcx]
0x1401cff22  jz      loc_1401D09F0
0x1401cff28  mov     rcx, [rcx+8]
0x1401cff2c  jmp     loc_1401D09F8
0x1401cff31  and     dword ptr [r14+23Ch], 0FFFFFFDFh
0x1401cff39  mov     eax, [rsp+4A8h+var_410]
0x1401cff40  test    eax, eax
0x1401cff42  jnz     loc_1401D039B
0x1401cff48  lea     r12, [r14+340h]
0x1401cff4f  mov     rcx, r12
0x1401cff52  call    NtfsGetFirstRestartTable
0x1401cff57  mov     rsi, rax
0x1401cff5a  test    rsi, rsi
0x1401cff5d  jz      loc_1401D0090
0x1401cff63  mov     cl, r11b
0x1401cff66  mov     [rsp+4A8h+var_428], cl
0x1401cff6d  cmp     [rsi+0Ch], r11b
0x1401cff71  jz      short loc_1401CFFDE
0x1401cff73  cmp     dword ptr [r14+131Ch], 2
0x1401cff7b  jb      loc_1401D0010
0x1401cff81  mov     [rsp+4A8h+var_3D8], rsi
0x1401cff89  mov     r11, [r14+410h]
0x1401cff90  movzx   r9d, word ptr [r11]
0x1401cff94  add     rsi, r9
0x1401cff97  mov     r8, rsi
0x1401cff9a  mov     [rsp+4A8h+var_3D8], rsi
0x1401cffa2  mov     r10, rsi
0x1401cffa5  mov     edx, r8d
0x1401cffa8  sub     edx, [r14+410h]
0x1401cffaf  movzx   ecx, word ptr [r11+2]
0x1401cffb4  imul    ecx, r9d
0x1401cffb8  add     ecx, 18h
0x1401cffbb  cmp     edx, ecx
0x1401cffbd  jnb     short loc_1401D0008
0x1401cffbf  cmp     dword ptr [r8], 0FFFFFFFFh
0x1401cffc3  jz      short loc_1401CFFD6
0x1401cffc5  lea     rsi, [rsi+r9]
0x1401cffc9  mov     r8, rsi
0x1401cffcc  mov     [rsp+4A8h+var_3D8], rsi
0x1401cffd4  jmp     short loc_1401CFFA2
0x1401cffd6  xor     r11d, r11d
0x1401cffd9  jmp     loc_1401CFF5A
0x1401cffde  mov     rax, [rsi+20h]
0x1401cffe2  cmp     [rax+18h], r11
0x1401cffe6  jnz     short loc_1401CFF73
0x1401cffe8  mov     r8, rsi
0x1401cffeb  mov     rdx, r14
0x1401cffee  mov     rcx, r13
0x1401cfff1  call    NtfsFreeAttributeEntry
0x1401cfff6  mov     cl, r15b
0x1401cfff9  mov     [rsp+4A8h+var_428], cl
0x1401d0000  xor     r11d, r11d
0x1401d0003  jmp     loc_1401CFF73
0x1401d0008  xor     r11d, r11d
0x1401d000b  mov     esi, r11d
0x1401d000e  jmp     short loc_1401CFFD9
0x1401d0010  test    cl, cl
0x1401d0012  jnz     loc_1401CFF81
0x1401d0018  mov     rax, [rsi+20h]
0x1401d001c  cmp     [rax+20h], r11w
0x1401d0021  jz      loc_1401CFF81
0x1401d0027  movzx   eax, word ptr [rax+10h]
0x1401d002b  mov     r9, qword ptr [rsp+4A8h+FileOffset]
0x1401d0033  mov     [r9], ax
0x1401d0037  mov     rax, [rsi+20h]
0x1401d003b  movzx   ecx, word ptr [rax+20h]
0x1401d003f  mov     [r9+2], cx
0x1401d0044  mov     rdx, [rsi+20h]
0x1401d0048  movzx   r8d, word ptr [rdx+20h]; Size
0x1401d004d  lea     rcx, [r9+4]; void *
0x1401d0051  mov     rdx, [rdx+28h]; Src
0x1401d0055  call    memmove
0x1401d005a  mov     rdx, qword ptr [rsp+4A8h+FileOffset]
0x1401d0062  movzx   ecx, word ptr [rdx+2]
0x1401d0066  shr     rcx, 1
0x1401d0069  xor     eax, eax
0x1401d006b  mov     [rdx+rcx*2+4], ax
0x1401d0070  movzx   eax, word ptr [rdx+2]
0x1401d0074  add     rdx, 6
0x1401d0078  add     rdx, rax
0x1401d007b  mov     qword ptr [rsp+4A8h+FileOffset], rdx
0x1401d0083  mov     [rsp+4A8h+var_328], rdx
0x1401d008b  jmp     loc_1401CFF81
0x1401d0090  cmp     [rsp+4A8h+P], r11
0x1401d0098  jnz     loc_1401D17D7
0x1401d009e  cmp     dword ptr [r14+131Ch], 2
0x1401d00a6  jb      loc_1401D0270
0x1401d00ac  mov     rcx, r12; Resource
0x1401d00af  call    cs:__imp_ExReleaseResourceLite
0x1401d00b6  nop     dword ptr [rax+rax+00h]
0x1401d00bb  xor     r12d, r12d
0x1401d00be  mov     [rsp+4A8h+var_437], r12b
0x1401d00c3  mov     esi, r12d
0x1401d00c6  mov     rdx, [rsp+4A8h+var_168]
0x1401d00ce  cmp     [rdx+4], r12w
0x1401d00d3  jnz     loc_1401D1852
0x1401d00d9  mov     dl, r15b; Wait
0x1401d00dc  lea     r12, [r14+428h]
0x1401d00e3  mov     rcx, r12; Resource
0x1401d00e6  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1401d00ed  nop     dword ptr [rax+rax+00h]
0x1401d00f2  mov     dl, r15b; Wait
0x1401d00f5  lea     rcx, [r14+490h]; Resource
0x1401d00fc  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1401d0103  nop     dword ptr [rax+rax+00h]
0x1401d0108  mov     [rsp+4A8h+var_438], r15b
0x1401d010d  mov     eax, [r14+23Ch]
0x1401d0114  and     eax, 0FFFFFFFBh
0x1401d0117  mov     [r14+23Ch], eax
0x1401d011e  mov     rcx, [rsp+4A8h+var_3F0]
0x1401d0126  xor     r8d, r8d
0x1401d0129  test    rcx, rcx
0x1401d012c  jnz     loc_1401D18D4
0x1401d0132  mov     rdx, [r14+4F8h]
0x1401d0139  movzx   eax, word ptr [rdx+4]
0x1401d013d  cmp     eax, esi
0x1401d013f  jbe     loc_1401D033B
0x1401d0145  xor     esi, esi
0x1401d0147  lea     rcx, [r14+490h]; Resource
0x1401d014e  call    cs:__imp_ExReleaseResourceLite
0x1401d0155  nop     dword ptr [rax+rax+00h]
0x1401d015a  mov     rcx, r12; Resource
0x1401d015d  call    cs:__imp_ExReleaseResourceLite
0x1401d0164  nop     dword ptr [rax+rax+00h]
0x1401d0169  mov     [rsp+4A8h+var_438], sil
0x1401d016e  test    rdi, rdi
0x1401d0171  jnz     loc_1401D1952
0x1401d0177  mov     eax, [r14+131Ch]
0x1401d017e  mov     [rsp+4A8h+var_108], eax
0x1401d0185  mov     [rsp+4A8h+var_104], esi
0x1401d018c  mov     rax, [r14+528h]
0x1401d0193  mov     [rsp+4A8h+var_C0], rax
0x1401d019b  mov     eax, [r14+164h]
0x1401d01a2  mov     [rsp+4A8h+var_B8], eax
0x1401d01a9  mov     [rsp+4A8h+var_B4], esi
0x1401d01b0  mov     rax, [r14+798h]
0x1401d01b7  mov     [rsp+4A8h+var_B0], rax
0x1401d01bf  mov     rax, [r14+7A0h]
0x1401d01c6  mov     [rsp+4A8h+var_A8], rax
0x1401d01ce  mov     rax, [r14+28h]
0x1401d01d2  mov     [rsp+4A8h+var_3B0], rax
0x1401d01da  test    rax, rax
0x1401d01dd  jnz     loc_1401D1966
0x1401d01e3  lea     rdi, [r14+338h]
0x1401d01ea  mov     [rdi], rbx
0x1401d01ed  mov     [r14+420h], rbx
0x1401d01f4  mov     [rsp+4A8h+var_A0], rbx
0x1401d01fc  mov     [rsp+4A8h+Timeout], rdi
0x1401d0201  mov     r9d, [rsp+4A8h+var_40C]
0x1401d0209  lea     r8, [rsp+4A8h+var_108]
0x1401d0211  mov     edx, 70h ; 'p'
0x1401d0216  mov     rcx, [r14+0E8h]
0x1401d021d  call    LfsWriteRestartArea
0x1401d0222  mov     eax, [r13+10h]
0x1401d0226  bt      rax, 9
0x1401d022b  jnb     short loc_1401D023B
0x1401d022d  mov     rax, cs:qword_140095A90
0x1401d0234  xchg    rax, [r14+1CE0h]
0x1401d023b  mov     sil, [rsp+4A8h+arg_18]
0x1401d0243  xor     ebx, ebx
0x1401d0245  test    sil, sil
0x1401d0248  jnz     loc_1401D1982
0x1401d024e  mov     rcx, [r14+0E8h]
  ... truncated ...
```
