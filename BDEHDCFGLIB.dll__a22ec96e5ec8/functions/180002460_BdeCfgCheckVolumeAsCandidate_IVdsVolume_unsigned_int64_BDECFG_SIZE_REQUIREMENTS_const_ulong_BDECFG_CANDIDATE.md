# BdeCfgCheckVolumeAsCandidate(IVdsVolume *,unsigned __int64,_BDECFG_SIZE_REQUIREMENTS * const,ulong,_BDECFG_CANDIDATE *)

- ea: `0x180002460`
- end: `0x18000280d`
- name: `?BdeCfgCheckVolumeAsCandidate@@YAJPEAUIVdsVolume@@_KQEAU_BDECFG_SIZE_REQUIREMENTS@@KPEAU_BDECFG_CANDIDATE@@@Z`
- size: `941`
- prototype: `__int64 __fastcall(struct IVdsVolume *, unsigned __int64, struct _BDECFG_SIZE_REQUIREMENTS *const, char, struct _BDECFG_CANDIDATE *)`
- caller_count: `4`
- callee_count: `14`
- tags: `service_task`

## callers

- `0x180003240`
- `0x180003580`
- `0x18000f430`
- `0x18000fb40`

## callees

- `0x180002460`
- `0x180003f68`
- `0x1800042a0`
- `0x180005284`
- `0x18000634c`
- `0x180006738`
- `0x180006860`
- `0x180007210`
- `0x180007470`
- `0x18000dbc0`
- `0x18000e300`
- `0x18001358e`
- `0x1800135c0`
- `0x180015010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180002645`
- `msvcrt!_wcsicmp` at `0x180002645`
- `ole32!CoTaskMemFree` at `0x1800027db`
- `ole32!CoTaskMemFree` at `0x1800027db`

## pseudocode

```c
__int64 __fastcall BdeCfgCheckVolumeAsCandidate(
        struct IVdsVolume *a1,
        unsigned __int64 a2,
        struct _BDECFG_SIZE_REQUIREMENTS *const a3,
        char a4,
        struct _BDECFG_CANDIDATE *a5)
{
  struct _BDECFG_CANDIDATE *v5; // rdi
  signed int NtfsVolumeSize; // ebx
  char v12; // al
  int v13; // r14d
  int v14; // eax
  int v15; // r15d
  wchar_t *v16; // rcx
  wchar_t *v17; // r8
  __int64 v18; // rax
  __int64 v19; // rdx
  wchar_t *v20; // rcx
  unsigned __int64 v21; // rdx
  DWORD v22; // ecx
  int IsVolumeEncrypted; // eax
  __int64 v24; // rcx
  int *v25; // rax
  __int128 v26; // xmm1
  __int128 v27; // xmm0
  __int128 v28; // xmm1
  __int128 v29; // xmm0
  __int128 v30; // xmm1
  __int128 v31; // xmm0
  __int128 v32; // xmm1
  __int128 v33; // xmm1
  __int128 v34; // xmm0
  __int64 v35; // rax
  int v36[4]; // [rsp+30h] [rbp-D0h] BYREF
  _VDS_PARTITION_PROP v37; // [rsp+40h] [rbp-C0h] BYREF
  _OWORD v38[4]; // [rsp+D0h] [rbp-30h] BYREF
  int v39; // [rsp+110h] [rbp+10h] BYREF
  wchar_t String2[260]; // [rsp+118h] [rbp+18h] BYREF
  unsigned __int64 v41; // [rsp+320h] [rbp+220h] BYREF
  unsigned __int64 v42; // [rsp+328h] [rbp+228h] BYREF
  unsigned __int64 v43; // [rsp+330h] [rbp+230h] BYREF
  int v44; // [rsp+338h] [rbp+238h]
  unsigned __int16 v45; // [rsp+33Ch] [rbp+23Ch] BYREF
  unsigned int v46[4]; // [rsp+340h] [rbp+240h] BYREF
  wchar_t String1[264]; // [rsp+350h] [rbp+250h] BYREF

  v5 = a5;
  memset(v38, 0, 56);
  memset_0(&v37, 0, sizeof(v37));
  memset_0(&v39, 0, 0x238u);
  memset_0(String1, 0, 0x208u);
  v36[0] = 0;
  if ( !g_pService )
    return 3231711254LL;
  if ( !a3 )
  {
    NtfsVolumeSize = -2147467261;
    goto LABEL_46;
  }
  memset(v38, 0, 56);
  memset_0(a5, 0, 0x238u);
  v12 = a4;
  v13 = a4 & 1;
  v14 = v12 & 2;
  if ( !v14 && !v13 )
  {
    NtfsVolumeSize = -1063256037;
    goto LABEL_46;
  }
  v15 = 0;
  if ( v14 )
  {
    NtfsVolumeSize = BdeCfgpCheckVolumeFileSystemAndSpace(a1, a2, a3, 1, &v43);
    if ( NtfsVolumeSize < 0 )
    {
      if ( !v13 )
        goto LABEL_46;
    }
    else
    {
      v15 = 1;
    }
  }
  NtfsVolumeSize = ((__int64 (__fastcall *)(struct IVdsVolume *, _OWORD *))a1->lpVtbl->GetProperties)(a1, v38);
  if ( NtfsVolumeSize < 0 )
    goto LABEL_46;
  v16 = *(wchar_t **)&v38[3];
  v17 = String2;
  v18 = 2147483646;
  v19 = 260;
  do
  {
    if ( !v18 )
      break;
    if ( !*v16 )
      break;
    *v17++ = *v16++;
    --v18;
    --v19;
  }
  while ( v19 );
  v20 = v17 - 1;
  NtfsVolumeSize = v19 == 0 ? 0x8007007A : 0;
  if ( v19 )
    v20 = v17;
  *v20 = 0;
  if ( !v19 )
    goto LABEL_46;
  v44 = DWORD2(v38[2]);
  if ( v13 && !v15 )
  {
    v21 = (unsigned int)BdeCfgDetectWinREVolumeName(0x104u, String1) || _wcsicmp(String1, String2)
        ? *((_QWORD *)a3 + 4)
        : *((_QWORD *)a3 + 5);
    NtfsVolumeSize = BdeCfgpCheckVolumeFileSystemAndSpace(a1, v21, a3, 0, 0);
    if ( NtfsVolumeSize < 0 )
      goto LABEL_46;
  }
  v39 = v15;
  NtfsVolumeSize = BdeCfgGetNtfsVolumeSize(a1, &v41, &v42, 0);
  if ( NtfsVolumeSize < 0 )
    goto LABEL_46;
  BdeCfgGetVolumeDriveLetter(String2, &v45);
  NtfsVolumeSize = BdeCfgGetBasicVolumePartitionProperties(a1, v46, &v37);
  if ( NtfsVolumeSize < 0 )
    goto LABEL_46;
  v46[1] = v37.ulPartitionNumber;
  NtfsVolumeSize = BdeCfgpIsVolumeLogical(String2, v36);
  if ( NtfsVolumeSize < 0 )
    goto LABEL_46;
  if ( v36[0] )
  {
    v22 = 1084227646;
LABEL_32:
    BdeCfgpLogFailedTarget(v22, a1);
LABEL_33:
    NtfsVolumeSize = -1063256032;
    goto LABEL_46;
  }
  if ( !v15 )
  {
    if ( (BYTE8(v38[2]) & 1) != 0 )
    {
      v22 = 1084227647;
      goto LABEL_32;
    }
    IsVolumeEncrypted = BdeCfgpIsVolumeEncrypted(String2);
    if ( IsVolumeEncrypted < 0 )
    {
      BdeCfgLogError(1, (unsigned int)IsVolumeEncrypted);
      goto LABEL_33;
    }
    if ( IsVolumeEncrypted != 1 )
    {
      v22 = 1084227648;
      goto LABEL_32;
    }
    if ( v37.Mbr.partitionType != 7 )
    {
      v22 = 1084227649;
      goto LABEL_32;
    }
  }
  BdeCfgLogCandidateDrive(&v39);
  v24 = 4;
  v25 = &v39;
  NtfsVolumeSize = 0;
  do
  {
    v26 = *((_OWORD *)v25 + 1);
    *(_OWORD *)v5 = *(_OWORD *)v25;
    v27 = *((_OWORD *)v25 + 2);
    *((_OWORD *)v5 + 1) = v26;
    v28 = *((_OWORD *)v25 + 3);
    *((_OWORD *)v5 + 2) = v27;
    v29 = *((_OWORD *)v25 + 4);
    *((_OWORD *)v5 + 3) = v28;
    v30 = *((_OWORD *)v25 + 5);
    *((_OWORD *)v5 + 4) = v29;
    v31 = *((_OWORD *)v25 + 6);
    *((_OWORD *)v5 + 5) = v30;
    v32 = *((_OWORD *)v25 + 7);
    v25 += 32;
    *((_OWORD *)v5 + 6) = v31;
    *((_OWORD *)v5 + 7) = v32;
    v5 = (struct _BDECFG_CANDIDATE *)((char *)v5 + 128);
    --v24;
  }
  while ( v24 );
  v33 = *((_OWORD *)v25 + 1);
  *(_OWORD *)v5 = *(_OWORD *)v25;
  v34 = *((_OWORD *)v25 + 2);
  v35 = *((_QWORD *)v25 + 6);
  *((_OWORD *)v5 + 1) = v33;
  *((_OWORD *)v5 + 2) = v34;
  *((_QWORD *)v5 + 6) = v35;
LABEL_46:
  if ( *(_QWORD *)&v38[3] )
    CoTaskMemFree(*(LPVOID *)&v38[3]);
  return (unsigned int)NtfsVolumeSize;
}

```

## disassembly

```asm
0x180002460  mov     [rsp-8+arg_18], rbx
0x180002465  push    rbp
0x180002466  push    rsi
0x180002467  push    rdi
0x180002468  push    r12
0x18000246a  push    r13
0x18000246c  push    r14
0x18000246e  push    r15
0x180002470  lea     rbp, [rsp-470h]
0x180002478  sub     rsp, 570h
0x18000247f  mov     rax, cs:__security_cookie
0x180002486  xor     rax, rsp
0x180002489  mov     [rbp+4A0h+var_40], rax
0x180002490  mov     rdi, [rbp+4A0h+arg_20]
0x180002497  xorps   xmm0, xmm0
0x18000249a  mov     r13, r8
0x18000249d  mov     rbx, rdx
0x1800024a0  mov     rsi, rcx
0x1800024a3  xor     eax, eax
0x1800024a5  xor     r12d, r12d
0x1800024a8  mov     [rbp+4A0h+var_49C], eax
0x1800024ab  xor     edx, edx; Val
0x1800024ad  mov     dword ptr [rbp+4A0h+var_4D0], r12d
0x1800024b1  mov     r8d, 90h; Size
0x1800024b7  lea     rcx, [rsp+5A0h+var_560]; void *
0x1800024bc  movups  [rbp+4A0h+var_4D0+4], xmm0
0x1800024c0  mov     r14d, r9d
0x1800024c3  movups  [rbp+4A0h+var_4BC], xmm0
0x1800024c7  movups  xmmword ptr [rbp+4A0h+pv], xmm0
0x1800024cb  call    memset_0
0x1800024d0  mov     r15d, 238h
0x1800024d6  lea     rcx, [rbp+4A0h+var_490]; void *
0x1800024da  mov     r8d, r15d; Size
0x1800024dd  xor     edx, edx; Val
0x1800024df  call    memset_0
0x1800024e4  xor     edx, edx; Val
0x1800024e6  lea     r8d, [r15-30h]; Size
0x1800024ea  lea     rcx, [rbp+4A0h+String1]; void *
0x1800024f1  call    memset_0
0x1800024f6  cmp     cs:?g_pService@@3PEAUIVdsService@@EA, r12; IVdsService * g_pService
0x1800024fd  mov     [rsp+5A0h+var_570], r12d
0x180002502  jnz     short loc_18000250E
0x180002504  mov     eax, 0C0A00016h
0x180002509  jmp     loc_1800027E3
0x18000250e  test    r13, r13
0x180002511  jnz     short loc_18000251D
0x180002513  mov     ebx, 80004003h
0x180002518  jmp     loc_1800027D2
0x18000251d  xorps   xmm0, xmm0
0x180002520  xor     eax, eax
0x180002522  mov     r8, r15; Size
0x180002525  mov     [rbp+4A0h+pv+0Ch], rax
0x180002529  xor     edx, edx; Val
0x18000252b  mov     rcx, rdi; void *
0x18000252e  movups  [rbp+4A0h+var_4D0], xmm0
0x180002532  movups  xmmword ptr [rbp-20h], xmm0
0x180002536  movups  [rbp+4A0h+var_4BC+0Ch], xmm0
0x18000253a  call    memset_0
0x18000253f  mov     eax, r14d
0x180002542  and     r14d, 1
0x180002546  and     eax, 2
0x180002549  jnz     short loc_18000255A
0x18000254b  test    r14d, r14d
0x18000254e  jnz     short loc_18000255A
0x180002550  mov     ebx, 0C0A0001Bh
0x180002555  jmp     loc_1800027D2
0x18000255a  mov     r15d, r12d
0x18000255d  test    eax, eax
0x18000255f  jz      short loc_180002598
0x180002561  lea     rax, [rbp+4A0h+var_270]
0x180002568  mov     r9d, 1; int
0x18000256e  mov     r8, r13; struct _BDECFG_SIZE_REQUIREMENTS *
0x180002571  mov     [rsp+5A0h+var_580], rax; unsigned __int64 *
0x180002576  mov     rdx, rbx; unsigned __int64
0x180002579  mov     rcx, rsi; struct IVdsVolume *
0x18000257c  call    ?BdeCfgpCheckVolumeFileSystemAndSpace@@YAJPEAUIVdsVolume@@_KQEAU_BDECFG_SIZE_REQUIREMENTS@@HPEA_K@Z; BdeCfgpCheckVolumeFileSystemAndSpace(IVdsVolume *,unsigned __int64,_BDECFG_SIZE_REQUIREMENTS * const,int,unsigned __int64 *)
0x180002581  mov     ebx, eax
0x180002583  test    eax, eax
0x180002585  js      short loc_18000258F
0x180002587  mov     r15d, 1
0x18000258d  jmp     short loc_180002598
0x18000258f  test    r14d, r14d
0x180002592  jz      loc_1800027D2
0x180002598  mov     rax, [rsi]
0x18000259b  lea     rdx, [rbp+4A0h+var_4D0]
0x18000259f  mov     rcx, rsi
0x1800025a2  mov     rax, [rax+18h]
0x1800025a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025ab  mov     ebx, eax
0x1800025ad  test    eax, eax
0x1800025af  js      loc_1800027D2
0x1800025b5  mov     rcx, [rbp+4A0h+pv+0Ch]
0x1800025b9  lea     r8, [rbp+4A0h+String2]
0x1800025bd  mov     r10d, 104h
0x1800025c3  mov     eax, 7FFFFFFEh
0x1800025c8  mov     edx, r10d
0x1800025cb  test    rax, rax
0x1800025ce  jz      short loc_1800025EF
0x1800025d0  movzx   r9d, word ptr [rcx]
0x1800025d4  test    r9w, r9w
0x1800025d8  jz      short loc_1800025EF
0x1800025da  mov     [r8], r9w
0x1800025de  add     rcx, 2
0x1800025e2  add     r8, 2
0x1800025e6  dec     rax
0x1800025e9  sub     rdx, 1
0x1800025ed  jnz     short loc_1800025CB
0x1800025ef  mov     rax, rdx
0x1800025f2  lea     rcx, [r8-2]
0x1800025f6  neg     rax
0x1800025f9  sbb     ebx, ebx
0x1800025fb  not     ebx
0x1800025fd  and     ebx, 8007007Ah
0x180002603  test    rdx, rdx
0x180002606  cmovnz  rcx, r8
0x18000260a  mov     [rcx], r12w
0x18000260e  jz      loc_1800027D2
0x180002614  mov     eax, dword ptr [rbp+4A0h+pv+4]
0x180002617  mov     [rbp+4A0h+var_268], eax
0x18000261d  test    r14d, r14d
0x180002620  jz      short loc_180002676
0x180002622  test    r15d, r15d
0x180002625  jnz     short loc_180002676
0x180002627  lea     rdx, [rbp+4A0h+String1]; unsigned __int16 *
0x18000262e  mov     rcx, r10; unsigned __int64
0x180002631  call    ?BdeCfgDetectWinREVolumeName@@YAJ_KPEAG@Z; BdeCfgDetectWinREVolumeName(unsigned __int64,ushort *)
0x180002636  test    eax, eax
0x180002638  jnz     short loc_180002655
0x18000263a  lea     rdx, [rbp+4A0h+String2]; String2
0x18000263e  lea     rcx, [rbp+4A0h+String1]; String1
0x180002645  call    cs:__imp__wcsicmp
0x18000264b  test    eax, eax
0x18000264d  jnz     short loc_180002655
0x18000264f  mov     rdx, [r13+28h]
0x180002653  jmp     short loc_180002659
0x180002655  mov     rdx, [r13+20h]; unsigned __int64
0x180002659  xor     r9d, r9d; int
0x18000265c  mov     [rsp+5A0h+var_580], r12; unsigned __int64 *
0x180002661  mov     r8, r13; struct _BDECFG_SIZE_REQUIREMENTS *
0x180002664  mov     rcx, rsi; struct IVdsVolume *
0x180002667  call    ?BdeCfgpCheckVolumeFileSystemAndSpace@@YAJPEAUIVdsVolume@@_KQEAU_BDECFG_SIZE_REQUIREMENTS@@HPEA_K@Z; BdeCfgpCheckVolumeFileSystemAndSpace(IVdsVolume *,unsigned __int64,_BDECFG_SIZE_REQUIREMENTS * const,int,unsigned __int64 *)
0x18000266c  mov     ebx, eax
0x18000266e  test    eax, eax
0x180002670  js      loc_1800027D2
0x180002676  xor     r9d, r9d; struct _VDS_FILE_SYSTEM_PROP *
0x180002679  mov     [rbp+4A0h+var_490], r15d
0x18000267d  lea     r8, [rbp+4A0h+var_278]; unsigned __int64 *
0x180002684  mov     rcx, rsi; struct IVdsVolume *
0x180002687  lea     rdx, [rbp+4A0h+var_280]; unsigned __int64 *
0x18000268e  call    ?BdeCfgGetNtfsVolumeSize@@YAJPEAUIVdsVolume@@PEA_K1PEAU_VDS_FILE_SYSTEM_PROP@@@Z; BdeCfgGetNtfsVolumeSize(IVdsVolume *,unsigned __int64 *,unsigned __int64 *,_VDS_FILE_SYSTEM_PROP *)
0x180002693  mov     ebx, eax
0x180002695  test    eax, eax
0x180002697  js      loc_1800027D2
0x18000269d  lea     rdx, [rbp+4A0h+var_264]; unsigned __int16 *
0x1800026a4  lea     rcx, [rbp+4A0h+String2]; unsigned __int16 *
0x1800026a8  call    ?BdeCfgGetVolumeDriveLetter@@YAJPEBGPEAG@Z; BdeCfgGetVolumeDriveLetter(ushort const *,ushort *)
0x1800026ad  lea     r8, [rsp+5A0h+var_560]; struct _VDS_PARTITION_PROP *
0x1800026b2  mov     rcx, rsi; struct IVdsVolume *
0x1800026b5  lea     rdx, [rbp+4A0h+var_260]; unsigned int *
0x1800026bc  call    ?BdeCfgGetBasicVolumePartitionProperties@@YAJPEAUIVdsVolume@@PEAKPEAU_VDS_PARTITION_PROP@@@Z; BdeCfgGetBasicVolumePartitionProperties(IVdsVolume *,ulong *,_VDS_PARTITION_PROP *)
0x1800026c1  mov     ebx, eax
0x1800026c3  test    eax, eax
0x1800026c5  js      loc_1800027D2
0x1800026cb  mov     eax, [rsp+5A0h+var_560.ulPartitionNumber]
0x1800026cf  lea     rdx, [rsp+5A0h+var_570]; int *
0x1800026d4  lea     rcx, [rbp+4A0h+String2]; unsigned __int16 *
0x1800026d8  mov     [rbp+4A0h+var_25C], eax
0x1800026de  call    ?BdeCfgpIsVolumeLogical@@YAJPEBGPEAH@Z; BdeCfgpIsVolumeLogical(ushort const *,int *)
0x1800026e3  mov     ebx, eax
0x1800026e5  test    eax, eax
0x1800026e7  js      loc_1800027D2
0x1800026ed  cmp     [rsp+5A0h+var_570], r12d
0x1800026f2  jz      short loc_18000270B
0x1800026f4  mov     ecx, 40A0003Eh; dwMessageId
0x1800026f9  mov     rdx, rsi; struct IVdsVolume *
0x1800026fc  call    ?BdeCfgpLogFailedTarget@@YAJJPEAUIVdsVolume@@@Z; BdeCfgpLogFailedTarget(long,IVdsVolume *)
0x180002701  mov     ebx, 0C0A00020h
0x180002706  jmp     loc_1800027D2
0x18000270b  test    r15d, r15d
0x18000270e  jnz     short loc_180002752
0x180002710  test    byte ptr [rbp+4A0h+pv+4], 1
0x180002714  jz      short loc_18000271D
0x180002716  mov     ecx, 40A0003Fh
0x18000271b  jmp     short loc_1800026F9
0x18000271d  lea     rcx, [rbp+4A0h+String2]; unsigned __int16 *
0x180002721  call    ?BdeCfgpIsVolumeEncrypted@@YAJPEBG@Z; BdeCfgpIsVolumeEncrypted(ushort const *)
0x180002726  test    eax, eax
0x180002728  jns     short loc_180002738
0x18000272a  mov     edx, eax
0x18000272c  mov     ecx, 1
0x180002731  call    BdeCfgLogError
0x180002736  jmp     short loc_180002701
0x180002738  cmp     eax, 1
0x18000273b  jz      short loc_180002744
0x18000273d  mov     ecx, 40A00040h
0x180002742  jmp     short loc_1800026F9
0x180002744  cmp     byte ptr [rsp+5A0h+var_560.20h], 7
0x180002749  jz      short loc_180002752
0x18000274b  mov     ecx, 40A00041h
0x180002750  jmp     short loc_1800026F9
0x180002752  lea     rcx, [rbp+4A0h+var_490]
0x180002756  call    BdeCfgLogCandidateDrive
0x18000275b  mov     ecx, 4
0x180002760  lea     rax, [rbp+4A0h+var_490]
0x180002764  mov     ebx, r12d
0x180002767  lea     edx, [rcx+7Ch]
0x18000276a  movups  xmm0, xmmword ptr [rax]
0x18000276d  movups  xmm1, xmmword ptr [rax+10h]
0x180002771  movups  xmmword ptr [rdi], xmm0
0x180002774  movups  xmm0, xmmword ptr [rax+20h]
0x180002778  movups  xmmword ptr [rdi+10h], xmm1
0x18000277c  movups  xmm1, xmmword ptr [rax+30h]
0x180002780  movups  xmmword ptr [rdi+20h], xmm0
0x180002784  movups  xmm0, xmmword ptr [rax+40h]
0x180002788  movups  xmmword ptr [rdi+30h], xmm1
0x18000278c  movups  xmm1, xmmword ptr [rax+50h]
0x180002790  movups  xmmword ptr [rdi+40h], xmm0
0x180002794  movups  xmm0, xmmword ptr [rax+60h]
0x180002798  movups  xmmword ptr [rdi+50h], xmm1
0x18000279c  movups  xmm1, xmmword ptr [rax+70h]
0x1800027a0  add     rax, rdx
0x1800027a3  movups  xmmword ptr [rdi+60h], xmm0
0x1800027a7  movups  xmmword ptr [rdi+70h], xmm1
0x1800027ab  add     rdi, rdx
0x1800027ae  sub     rcx, 1
0x1800027b2  jnz     short loc_18000276A
0x1800027b4  movups  xmm0, xmmword ptr [rax]
0x1800027b7  movups  xmm1, xmmword ptr [rax+10h]
0x1800027bb  movups  xmmword ptr [rdi], xmm0
0x1800027be  movups  xmm0, xmmword ptr [rax+20h]
0x1800027c2  mov     rax, [rax+30h]
0x1800027c6  movups  xmmword ptr [rdi+10h], xmm1
0x1800027ca  movups  xmmword ptr [rdi+20h], xmm0
0x1800027ce  mov     [rdi+30h], rax
0x1800027d2  mov     rcx, [rbp+4A0h+pv+0Ch]; pv
0x1800027d6  test    rcx, rcx
0x1800027d9  jz      short loc_1800027E1
0x1800027db  call    cs:__imp_CoTaskMemFree
0x1800027e1  mov     eax, ebx
0x1800027e3  mov     rcx, [rbp+4A0h+var_40]
0x1800027ea  xor     rcx, rsp; StackCookie
0x1800027ed  call    __security_check_cookie
0x1800027f2  mov     rbx, [rsp+5A0h+arg_18]
0x1800027fa  add     rsp, 570h
0x180002801  pop     r15
0x180002803  pop     r14
0x180002805  pop     r13
0x180002807  pop     r12
0x180002809  pop     rdi
0x18000280a  pop     rsi
0x18000280b  pop     rbp
0x18000280c  retn
```
