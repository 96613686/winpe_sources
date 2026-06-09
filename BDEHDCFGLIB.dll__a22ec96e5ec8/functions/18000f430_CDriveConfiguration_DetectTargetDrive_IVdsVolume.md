# CDriveConfiguration::DetectTargetDrive(IVdsVolume *)

- ea: `0x18000f430`
- end: `0x18000f889`
- name: `?DetectTargetDrive@CDriveConfiguration@@AEAAJPEAUIVdsVolume@@@Z`
- size: `1113`
- prototype: `__int64 __fastcall(CDriveConfiguration *this, struct IVdsVolume *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x180010800`

## callees

- `0x1800021b0`
- `0x180002460`
- `0x180003240`
- `0x180003580`
- `0x180003bc0`
- `0x180004410`
- `0x1800046bc`
- `0x18000f430`
- `0x18001358e`
- `0x1800135c0`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall CDriveConfiguration::DetectTargetDrive(CDriveConfiguration *this, struct IVdsVolume *a2)
{
  int VolumeDisk; // ebx
  unsigned __int64 *v5; // r15
  _OWORD *v6; // rdi
  _OWORD *v7; // rax
  __int64 v8; // rdx
  unsigned __int16 v9; // cx
  __int16 v10; // r14
  unsigned __int64 v11; // rsi
  _OWORD *v12; // rcx
  _OWORD *v13; // rax
  __int64 v14; // rdx
  int CandidateVolumes; // eax
  _BYTE *v16; // rcx
  _DWORD *v17; // rax
  __int64 v18; // rdx
  __int64 v19; // r9
  struct IVdsDisk *v21; // [rsp+38h] [rbp-950h] BYREF
  struct IVdsVolume *v22; // [rsp+40h] [rbp-948h] BYREF
  unsigned __int64 v23; // [rsp+48h] [rbp-940h] BYREF
  unsigned __int64 v24; // [rsp+50h] [rbp-938h] BYREF
  _BYTE v25[576]; // [rsp+60h] [rbp-928h] BYREF
  _BYTE v26[8]; // [rsp+2A0h] [rbp-6E8h] BYREF
  _DWORD v27[426]; // [rsp+2A8h] [rbp-6E0h] BYREF

  v22 = 0;
  v21 = 0;
  v23 = 0;
  memset_0(v26, 0, 0x6B0u);
  memset_0(v25, 0, 0x238u);
  if ( !a2 )
  {
    VolumeDisk = -2147467261;
    goto LABEL_37;
  }
  v5 = (unsigned __int64 *)((char *)this + 1208);
  VolumeDisk = BdeCfgDetectAndCheckWinREVolume(
                 (CDriveConfiguration *)((char *)this + 1208),
                 (struct _BDECFG_CANDIDATE *)v25);
  if ( !VolumeDisk )
  {
    *((_DWORD *)this + 16) = 2;
    v6 = (_OWORD *)((char *)this + 592);
    v7 = v25;
    v8 = 4;
    do
    {
      *v6 = *v7;
      v6[1] = v7[1];
      v6[2] = v7[2];
      v6[3] = v7[3];
      v6[4] = v7[4];
      v6[5] = v7[5];
      v6[6] = v7[6];
      v6[7] = v7[7];
      v6 += 8;
      v7 += 8;
      --v8;
    }
    while ( v8 );
LABEL_6:
    *v6 = *v7;
    v6[1] = v7[1];
    v6[2] = v7[2];
    *((_QWORD *)v6 + 6) = *((_QWORD *)v7 + 6);
    goto LABEL_37;
  }
  v9 = *((_WORD *)this + 592);
  if ( v9 )
  {
    if ( !(unsigned int)BdeCfgGetVolumeWithDriveLetter(v9, &v22) )
    {
      VolumeDisk = -1063256029;
      goto LABEL_37;
    }
    v10 = *((_WORD *)this + 592);
  }
  else
  {
    v10 = 0;
  }
  v11 = *((_QWORD *)this + 149);
  if ( v11 <= *v5 )
    v11 = *v5;
  VolumeDisk = BdeCfgGetVolumeDisk(a2, &v21);
  if ( VolumeDisk >= 0 )
  {
    if ( !(unsigned int)BdeCfgCanCreateActivePartOnDisk(v21) )
    {
      VolumeDisk = BdeCfgFindLargestUnallocatedExtent(v21, v11, &v23, &v24);
      if ( !VolumeDisk )
      {
        *((_DWORD *)this + 16) = 3;
        *((_QWORD *)this + 74) = v23;
        *((_QWORD *)this + 75) = v11;
        *((_WORD *)this + 304) = v10;
        goto LABEL_37;
      }
      VolumeDisk = BdeCfgCheckVolumeAsCandidate(
                     a2,
                     v11,
                     (CDriveConfiguration *)((char *)this + 1208),
                     2,
                     (struct _BDECFG_CANDIDATE *)v25);
      if ( VolumeDisk >= 0 )
      {
        *((_DWORD *)this + 16) = 1;
        *((_QWORD *)this + 145) = v11;
        v12 = (_OWORD *)((char *)this + 592);
        v13 = v25;
        v14 = 4;
        do
        {
          *v12 = *v13;
          v12[1] = v13[1];
          v12[2] = v13[2];
          v12[3] = v13[3];
          v12[4] = v13[4];
          v12[5] = v13[5];
          v12[6] = v13[6];
          v12[7] = v13[7];
          v12 += 8;
          v13 += 8;
          --v14;
        }
        while ( v14 );
LABEL_30:
        *v12 = *v13;
        v12[1] = v13[1];
        v12[2] = v13[2];
        *((_QWORD *)v12 + 6) = *((_QWORD *)v13 + 6);
        *((_WORD *)this + 584) = v10;
        goto LABEL_37;
      }
    }
    CandidateVolumes = BdeCfgFindCandidateVolumes(
                         v21,
                         v11,
                         (CDriveConfiguration *)((char *)this + 1208),
                         (struct _BDECFG_CANDIDATES *)v26);
    VolumeDisk = CandidateVolumes;
    if ( CandidateVolumes < 0 )
      goto LABEL_37;
    if ( CandidateVolumes == 1 )
    {
      VolumeDisk = -1063256057;
      goto LABEL_37;
    }
    v16 = v25;
    v17 = v27;
    v18 = 4;
    v19 = 4;
    do
    {
      v16 += 128;
      v17 += 32;
      --v19;
    }
    while ( v19 );
    if ( v27[0] )
    {
      *((_DWORD *)this + 16) = 1;
      *((_QWORD *)this + 145) = v11;
      v12 = (_OWORD *)((char *)this + 592);
      v13 = v27;
      do
      {
        *v12 = *v13;
        v12[1] = v13[1];
        v12[2] = v13[2];
        v12[3] = v13[3];
        v12[4] = v13[4];
        v12[5] = v13[5];
        v12[6] = v13[6];
        v12[7] = v13[7];
        v12 += 8;
        v13 += 8;
        --v18;
      }
      while ( v18 );
      goto LABEL_30;
    }
    if ( !*((_QWORD *)this + 149) && !*((_WORD *)this + 592) )
    {
      *((_DWORD *)this + 16) = 2;
      v6 = (_OWORD *)((char *)this + 592);
      v7 = v27;
      do
      {
        *v6 = *v7;
        v6[1] = v7[1];
        v6[2] = v7[2];
        v6[3] = v7[3];
        v6[4] = v7[4];
        v6[5] = v7[5];
        v6[6] = v7[6];
        v6[7] = v7[7];
        v6 += 8;
        v7 += 8;
        --v18;
      }
      while ( v18 );
      goto LABEL_6;
    }
    VolumeDisk = -1063256021;
  }
LABEL_37:
  if ( v22 )
  {
    ((void (__fastcall *)(struct IVdsVolume *))v22->lpVtbl->Release)(v22);
    v22 = 0;
  }
  if ( v21 )
    ((void (__fastcall *)(struct IVdsDisk *))v21->lpVtbl->Release)(v21);
  return (unsigned int)VolumeDisk;
}

```

## disassembly

```asm
0x18000f430  mov     [rsp+arg_10], rbx
0x18000f435  mov     [rsp+arg_18], rsi
0x18000f43a  push    rdi
0x18000f43b  push    r12
0x18000f43d  push    r13
0x18000f43f  push    r14
0x18000f441  push    r15
0x18000f443  sub     rsp, 960h
0x18000f44a  mov     rax, cs:__security_cookie
0x18000f451  xor     rax, rsp
0x18000f454  mov     [rsp+988h+var_38], rax
0x18000f45c  mov     r12, rdx
0x18000f45f  mov     rdi, rcx
0x18000f462  xor     r13d, r13d
0x18000f465  mov     [rsp+988h+var_948], r13
0x18000f46a  mov     [rsp+988h+var_950], r13
0x18000f46f  mov     [rsp+988h+var_940], r13
0x18000f474  xor     edx, edx; Val
0x18000f476  mov     r8d, 6B0h; Size
0x18000f47c  lea     rcx, [rsp+988h+var_6E8]; void *
0x18000f484  call    memset_0
0x18000f489  xor     edx, edx; Val
0x18000f48b  mov     r8d, 238h; Size
0x18000f491  lea     rcx, [rsp+988h+var_928]; void *
0x18000f496  call    memset_0
0x18000f49b  nop
0x18000f49c  test    r12, r12
0x18000f49f  jnz     short loc_18000F4AB
0x18000f4a1  mov     ebx, 80004003h
0x18000f4a6  jmp     loc_18000F825
0x18000f4ab  lea     r15, [rdi+4B8h]
0x18000f4b2  lea     rdx, [rsp+988h+var_928]; struct _BDECFG_CANDIDATE *
0x18000f4b7  mov     rcx, r15; struct _BDECFG_SIZE_REQUIREMENTS *
0x18000f4ba  call    ?BdeCfgDetectAndCheckWinREVolume@@YAJQEAU_BDECFG_SIZE_REQUIREMENTS@@PEAU_BDECFG_CANDIDATE@@@Z; BdeCfgDetectAndCheckWinREVolume(_BDECFG_SIZE_REQUIREMENTS * const,_BDECFG_CANDIDATE *)
0x18000f4bf  mov     ebx, eax
0x18000f4c1  mov     [rsp+988h+var_958], eax
0x18000f4c5  test    eax, eax
0x18000f4c7  jnz     loc_18000F554
0x18000f4cd  mov     dword ptr [rdi+40h], 2
0x18000f4d4  add     rdi, 250h
0x18000f4db  lea     rax, [rsp+988h+var_928]
0x18000f4e0  lea     edx, [rbx+4]
0x18000f4e3  lea     r8d, [rdx+7Ch]
0x18000f4e7  movups  xmm0, xmmword ptr [rax]
0x18000f4ea  movups  xmmword ptr [rdi], xmm0
0x18000f4ed  movups  xmm1, xmmword ptr [rax+10h]
0x18000f4f1  movups  xmmword ptr [rdi+10h], xmm1
0x18000f4f5  movups  xmm0, xmmword ptr [rax+20h]
0x18000f4f9  movups  xmmword ptr [rdi+20h], xmm0
0x18000f4fd  movups  xmm1, xmmword ptr [rax+30h]
0x18000f501  movups  xmmword ptr [rdi+30h], xmm1
0x18000f505  movups  xmm0, xmmword ptr [rax+40h]
0x18000f509  movups  xmmword ptr [rdi+40h], xmm0
0x18000f50d  movups  xmm1, xmmword ptr [rax+50h]
0x18000f511  movups  xmmword ptr [rdi+50h], xmm1
0x18000f515  movups  xmm0, xmmword ptr [rax+60h]
0x18000f519  movups  xmmword ptr [rdi+60h], xmm0
0x18000f51d  movups  xmm1, xmmword ptr [rax+70h]
0x18000f521  movups  xmmword ptr [rdi+70h], xmm1
0x18000f525  add     rdi, r8
0x18000f528  add     rax, r8
0x18000f52b  sub     rdx, 1
0x18000f52f  jnz     short loc_18000F4E7
0x18000f531  movups  xmm0, xmmword ptr [rax]
0x18000f534  movups  xmmword ptr [rdi], xmm0
0x18000f537  movups  xmm1, xmmword ptr [rax+10h]
0x18000f53b  movups  xmmword ptr [rdi+10h], xmm1
0x18000f53f  movups  xmm0, xmmword ptr [rax+20h]
0x18000f543  movups  xmmword ptr [rdi+20h], xmm0
0x18000f547  mov     rax, [rax+30h]
0x18000f54b  mov     [rdi+30h], rax
0x18000f54f  jmp     loc_18000F829
0x18000f554  movzx   ecx, word ptr [rdi+4A0h]; unsigned __int16
0x18000f55b  test    cx, cx
0x18000f55e  jz      short loc_18000F586
0x18000f560  lea     rdx, [rsp+988h+var_948]; struct IVdsVolume **
0x18000f565  call    ?BdeCfgGetVolumeWithDriveLetter@@YAJGPEAPEAUIVdsVolume@@@Z; BdeCfgGetVolumeWithDriveLetter(ushort,IVdsVolume * *)
0x18000f56a  mov     [rsp+988h+var_958], eax
0x18000f56e  test    eax, eax
0x18000f570  jnz     short loc_18000F57C
0x18000f572  mov     ebx, 0C0A00023h
0x18000f577  jmp     loc_18000F825
0x18000f57c  movzx   r14d, word ptr [rdi+4A0h]
0x18000f584  jmp     short loc_18000F589
0x18000f586  mov     r14d, r13d
0x18000f589  mov     rsi, [rdi+4A8h]
0x18000f590  cmp     rsi, [r15]
0x18000f593  cmovbe  rsi, [r15]
0x18000f597  lea     rdx, [rsp+988h+var_950]; struct IVdsDisk **
0x18000f59c  mov     rcx, r12; struct IVdsVolume *
0x18000f59f  call    ?BdeCfgGetVolumeDisk@@YAJPEAUIVdsVolume@@PEAPEAUIVdsDisk@@@Z; BdeCfgGetVolumeDisk(IVdsVolume *,IVdsDisk * *)
0x18000f5a4  mov     ebx, eax
0x18000f5a6  mov     [rsp+988h+var_958], eax
0x18000f5aa  test    eax, eax
0x18000f5ac  js      loc_18000F829
0x18000f5b2  mov     rcx, [rsp+988h+var_950]; struct IVdsDisk *
0x18000f5b7  call    ?BdeCfgCanCreateActivePartOnDisk@@YAJPEAUIVdsDisk@@@Z; BdeCfgCanCreateActivePartOnDisk(IVdsDisk *)
0x18000f5bc  mov     [rsp+988h+var_958], eax
0x18000f5c0  test    eax, eax
0x18000f5c2  jnz     loc_18000F6AA
0x18000f5c8  lea     r9, [rsp+988h+var_938]; unsigned __int64 *
0x18000f5cd  lea     r8, [rsp+988h+var_940]; unsigned __int64 *
0x18000f5d2  mov     rdx, rsi; unsigned __int64
0x18000f5d5  mov     rcx, [rsp+988h+var_950]; struct IVdsDisk *
0x18000f5da  call    ?BdeCfgFindLargestUnallocatedExtent@@YAJPEAUIVdsDisk@@_KPEA_K2@Z; BdeCfgFindLargestUnallocatedExtent(IVdsDisk *,unsigned __int64,unsigned __int64 *,unsigned __int64 *)
0x18000f5df  mov     ebx, eax
0x18000f5e1  mov     [rsp+988h+var_958], eax
0x18000f5e5  test    eax, eax
0x18000f5e7  jnz     short loc_18000F610
0x18000f5e9  mov     dword ptr [rdi+40h], 3
0x18000f5f0  mov     rax, [rsp+988h+var_940]
0x18000f5f5  mov     [rdi+250h], rax
0x18000f5fc  mov     [rdi+258h], rsi
0x18000f603  mov     [rdi+260h], r14w
0x18000f60b  jmp     loc_18000F829
0x18000f610  lea     rax, [rsp+988h+var_928]
0x18000f615  mov     [rsp+988h+var_968], rax; struct _BDECFG_CANDIDATE *
0x18000f61a  mov     r9d, 2; unsigned int
0x18000f620  mov     r8, r15; struct _BDECFG_SIZE_REQUIREMENTS *
0x18000f623  mov     rdx, rsi; unsigned __int64
0x18000f626  mov     rcx, r12; struct IVdsVolume *
0x18000f629  call    ?BdeCfgCheckVolumeAsCandidate@@YAJPEAUIVdsVolume@@_KQEAU_BDECFG_SIZE_REQUIREMENTS@@KPEAU_BDECFG_CANDIDATE@@@Z; BdeCfgCheckVolumeAsCandidate(IVdsVolume *,unsigned __int64,_BDECFG_SIZE_REQUIREMENTS * const,ulong,_BDECFG_CANDIDATE *)
0x18000f62e  mov     ebx, eax
0x18000f630  mov     [rsp+988h+var_958], eax
0x18000f634  test    eax, eax
0x18000f636  js      short loc_18000F6AA
0x18000f638  mov     dword ptr [rdi+40h], 1
0x18000f63f  mov     [rdi+488h], rsi
0x18000f646  lea     rcx, [rdi+250h]
0x18000f64d  lea     rax, [rsp+988h+var_928]
0x18000f652  mov     edx, 4
0x18000f657  lea     r8d, [rdx+7Ch]
0x18000f65b  movups  xmm0, xmmword ptr [rax]
0x18000f65e  movups  xmmword ptr [rcx], xmm0
0x18000f661  movups  xmm1, xmmword ptr [rax+10h]
0x18000f665  movups  xmmword ptr [rcx+10h], xmm1
0x18000f669  movups  xmm0, xmmword ptr [rax+20h]
0x18000f66d  movups  xmmword ptr [rcx+20h], xmm0
0x18000f671  movups  xmm1, xmmword ptr [rax+30h]
0x18000f675  movups  xmmword ptr [rcx+30h], xmm1
0x18000f679  movups  xmm0, xmmword ptr [rax+40h]
0x18000f67d  movups  xmmword ptr [rcx+40h], xmm0
0x18000f681  movups  xmm1, xmmword ptr [rax+50h]
0x18000f685  movups  xmmword ptr [rcx+50h], xmm1
0x18000f689  movups  xmm0, xmmword ptr [rax+60h]
0x18000f68d  movups  xmmword ptr [rcx+60h], xmm0
0x18000f691  movups  xmm1, xmmword ptr [rax+70h]
0x18000f695  movups  xmmword ptr [rcx+70h], xmm1
0x18000f699  add     rcx, r8
0x18000f69c  add     rax, r8
0x18000f69f  sub     rdx, 1
0x18000f6a3  jnz     short loc_18000F65B
0x18000f6a5  jmp     loc_18000F77D
0x18000f6aa  lea     r9, [rsp+988h+var_6E8]; struct _BDECFG_CANDIDATES *
0x18000f6b2  mov     r8, r15; struct _BDECFG_SIZE_REQUIREMENTS *
0x18000f6b5  mov     rdx, rsi; unsigned __int64
0x18000f6b8  mov     rcx, [rsp+988h+var_950]; struct IVdsDisk *
0x18000f6bd  call    ?BdeCfgFindCandidateVolumes@@YAJPEAUIVdsDisk@@_KQEAU_BDECFG_SIZE_REQUIREMENTS@@PEAU_BDECFG_CANDIDATES@@@Z; BdeCfgFindCandidateVolumes(IVdsDisk *,unsigned __int64,_BDECFG_SIZE_REQUIREMENTS * const,_BDECFG_CANDIDATES *)
0x18000f6c2  mov     ebx, eax
0x18000f6c4  mov     [rsp+988h+var_958], eax
0x18000f6c8  test    eax, eax
0x18000f6ca  js      loc_18000F829
0x18000f6d0  cmp     eax, 1
0x18000f6d3  jnz     short loc_18000F6DF
0x18000f6d5  mov     ebx, 0C0A00007h
0x18000f6da  jmp     loc_18000F825
0x18000f6df  lea     rcx, [rsp+988h+var_928]
0x18000f6e4  lea     rax, [rsp+988h+var_6E0]
0x18000f6ec  mov     edx, 4
0x18000f6f1  mov     r9d, edx
0x18000f6f4  lea     r8d, [rdx+7Ch]
0x18000f6f8  add     rcx, r8
0x18000f6fb  add     rax, r8
0x18000f6fe  sub     r9, 1
0x18000f702  jnz     short loc_18000F6F8
0x18000f704  mov     rax, [rax+30h]
0x18000f708  cmp     [rsp+988h+var_6E0], r13d
0x18000f710  jz      loc_18000F7A8
0x18000f716  mov     dword ptr [rdi+40h], 1
0x18000f71d  mov     [rdi+488h], rsi
0x18000f724  lea     rcx, [rdi+250h]
0x18000f72b  lea     rax, [rsp+988h+var_6E0]
0x18000f733  movups  xmm0, xmmword ptr [rax]
0x18000f736  movups  xmmword ptr [rcx], xmm0
0x18000f739  movups  xmm1, xmmword ptr [rax+10h]
0x18000f73d  movups  xmmword ptr [rcx+10h], xmm1
0x18000f741  movups  xmm0, xmmword ptr [rax+20h]
0x18000f745  movups  xmmword ptr [rcx+20h], xmm0
0x18000f749  movups  xmm1, xmmword ptr [rax+30h]
0x18000f74d  movups  xmmword ptr [rcx+30h], xmm1
0x18000f751  movups  xmm0, xmmword ptr [rax+40h]
0x18000f755  movups  xmmword ptr [rcx+40h], xmm0
0x18000f759  movups  xmm1, xmmword ptr [rax+50h]
0x18000f75d  movups  xmmword ptr [rcx+50h], xmm1
0x18000f761  movups  xmm0, xmmword ptr [rax+60h]
0x18000f765  movups  xmmword ptr [rcx+60h], xmm0
0x18000f769  movups  xmm1, xmmword ptr [rax+70h]
0x18000f76d  movups  xmmword ptr [rcx+70h], xmm1
0x18000f771  add     rcx, r8
0x18000f774  add     rax, r8
0x18000f777  sub     rdx, 1
0x18000f77b  jnz     short loc_18000F733
0x18000f77d  movups  xmm0, xmmword ptr [rax]
0x18000f780  movups  xmmword ptr [rcx], xmm0
0x18000f783  movups  xmm1, xmmword ptr [rax+10h]
0x18000f787  movups  xmmword ptr [rcx+10h], xmm1
0x18000f78b  movups  xmm0, xmmword ptr [rax+20h]
0x18000f78f  movups  xmmword ptr [rcx+20h], xmm0
0x18000f793  mov     rax, [rax+30h]
0x18000f797  mov     [rcx+30h], rax
0x18000f79b  mov     [rdi+490h], r14w
0x18000f7a3  jmp     loc_18000F829
0x18000f7a8  cmp     [rdi+4A8h], r13
0x18000f7af  jnz     short loc_18000F820
0x18000f7b1  cmp     [rdi+4A0h], r13w
0x18000f7b9  jnz     short loc_18000F820
0x18000f7bb  mov     dword ptr [rdi+40h], 2
0x18000f7c2  add     rdi, 250h
0x18000f7c9  lea     rax, [rsp+988h+var_6E0]
0x18000f7d1  movups  xmm0, xmmword ptr [rax]
0x18000f7d4  movups  xmmword ptr [rdi], xmm0
0x18000f7d7  movups  xmm1, xmmword ptr [rax+10h]
0x18000f7db  movups  xmmword ptr [rdi+10h], xmm1
0x18000f7df  movups  xmm0, xmmword ptr [rax+20h]
0x18000f7e3  movups  xmmword ptr [rdi+20h], xmm0
0x18000f7e7  movups  xmm1, xmmword ptr [rax+30h]
0x18000f7eb  movups  xmmword ptr [rdi+30h], xmm1
0x18000f7ef  movups  xmm0, xmmword ptr [rax+40h]
0x18000f7f3  movups  xmmword ptr [rdi+40h], xmm0
0x18000f7f7  movups  xmm1, xmmword ptr [rax+50h]
0x18000f7fb  movups  xmmword ptr [rdi+50h], xmm1
0x18000f7ff  movups  xmm0, xmmword ptr [rax+60h]
0x18000f803  movups  xmmword ptr [rdi+60h], xmm0
0x18000f807  movups  xmm1, xmmword ptr [rax+70h]
0x18000f80b  movups  xmmword ptr [rdi+70h], xmm1
0x18000f80f  add     rdi, r8
0x18000f812  add     rax, r8
0x18000f815  sub     rdx, 1
0x18000f819  jnz     short loc_18000F7D1
0x18000f81b  jmp     loc_18000F531
0x18000f820  mov     ebx, 0C0A0002Bh
0x18000f825  mov     [rsp+988h+var_958], ebx
0x18000f829  mov     rcx, [rsp+988h+var_948]
0x18000f82e  test    rcx, rcx
0x18000f831  jz      short loc_18000F844
0x18000f833  mov     rax, [rcx]
0x18000f836  mov     rax, [rax+10h]
0x18000f83a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f83f  mov     [rsp+988h+var_948], r13
0x18000f844  mov     rcx, [rsp+988h+var_950]
0x18000f849  test    rcx, rcx
0x18000f84c  jz      short loc_18000F85A
0x18000f84e  mov     rax, [rcx]
0x18000f851  mov     rax, [rax+10h]
0x18000f855  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f85a  mov     eax, ebx
0x18000f85c  mov     rcx, [rsp+988h+var_38]
0x18000f864  xor     rcx, rsp; StackCookie
0x18000f867  call    __security_check_cookie
0x18000f86c  lea     r11, [rsp+988h+var_28]
0x18000f874  mov     rbx, [r11+40h]
0x18000f878  mov     rsi, [r11+48h]
0x18000f87c  mov     rsp, r11
0x18000f87f  pop     r15
0x18000f881  pop     r14
0x18000f883  pop     r13
0x18000f885  pop     r12
0x18000f887  pop     rdi
0x18000f888  retn
0x1800143a8  push    rbp
0x1800143aa  sub     rsp, 30h
0x1800143ae  mov     rbp, rdx
0x1800143b1  mov     rcx, [rbp+40h]
0x1800143b5  test    rcx, rcx
0x1800143b8  jz      short loc_1800143CE
0x1800143ba  mov     rax, [rcx]
0x1800143bd  mov     rax, [rax+10h]
0x1800143c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800143c6  mov     qword ptr [rbp+40h], 0
0x1800143ce  mov     rcx, [rbp+38h]
0x1800143d2  test    rcx, rcx
0x1800143d5  jz      short loc_1800143E4
0x1800143d7  mov     rax, [rcx]
0x1800143da  mov     rax, [rax+10h]
0x1800143de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800143e3  nop
0x1800143e4  add     rsp, 30h
0x1800143e8  pop     rbp
0x1800143e9  retn
```
