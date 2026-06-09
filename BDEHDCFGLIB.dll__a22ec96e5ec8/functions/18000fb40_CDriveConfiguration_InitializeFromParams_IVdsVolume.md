# CDriveConfiguration::InitializeFromParams(IVdsVolume *)

- ea: `0x18000fb40`
- end: `0x18001005f`
- name: `?InitializeFromParams@CDriveConfiguration@@AEAAJPEAUIVdsVolume@@@Z`
- size: `1311`
- prototype: `__int64 __fastcall(CDriveConfiguration *this, struct IVdsVolume *)`
- caller_count: `1`
- callee_count: `16`
- tags: `reparse_path, registry_config`

## callers

- `0x180010800`

## callees

- `0x1800021b0`
- `0x180002460`
- `0x180002814`
- `0x180003bc0`
- `0x180004410`
- `0x1800049d0`
- `0x180005ce8`
- `0x180006c30`
- `0x180007624`
- `0x180007824`
- `0x180008e4c`
- `0x18000e300`
- `0x18000fb40`
- `0x18001358e`
- `0x1800135c0`
- `0x180015010`

## import_xrefs

- `msvcrt!iswdigit` at `0x18000fd01`
- `msvcrt!iswdigit` at `0x18000fd01`
- `msvcrt!iswalpha` at `0x18000fc83`
- `msvcrt!iswalpha` at `0x18000fcaa`
- `msvcrt!iswalpha` at `0x18000fc83`
- `msvcrt!iswalpha` at `0x18000fcaa`

## pseudocode

```c
__int64 __fastcall CDriveConfiguration::InitializeFromParams(CDriveConfiguration *this, struct IVdsVolume *a2)
{
  int VolumeDisk; // ebx
  __int64 v5; // r15
  int ActivePartOnDisk; // eax
  unsigned __int64 v7; // rsi
  int LargestUnallocatedExtent; // eax
  __int16 v9; // ax
  int v10; // eax
  unsigned int v11; // ebx
  wint_t v12; // cx
  bool v13; // sf
  unsigned __int64 v14; // r8
  int IsVolumeOnDisk; // eax
  int v16; // eax
  int v17; // eax
  unsigned __int64 v18; // r14
  struct _BDECFG_SIZE_REQUIREMENTS *v19; // r8
  int v20; // eax
  _OWORD *v21; // rcx
  _OWORD *v22; // rax
  __int16 v23; // ax
  int v24; // eax
  _OWORD *v25; // rdi
  _OWORD *v26; // rax
  struct IVdsDisk *v28; // [rsp+38h] [rbp-4D0h] BYREF
  struct IVdsVolume *v29; // [rsp+40h] [rbp-4C8h] BYREF
  unsigned __int64 v30; // [rsp+48h] [rbp-4C0h] BYREF
  unsigned __int64 v31; // [rsp+50h] [rbp-4B8h] BYREF
  _BYTE v32[576]; // [rsp+60h] [rbp-4A8h] BYREF
  WCHAR SourceString[16]; // [rsp+2A0h] [rbp-268h] BYREF
  WCHAR FileName[264]; // [rsp+2C0h] [rbp-248h] BYREF

  memset_0(FileName, 0, 0x208u);
  v29 = 0;
  v28 = 0;
  v31 = 0;
  memset_0(v32, 0, 0x238u);
  LODWORD(v30) = 0;
  VolumeDisk = BdeCfgGetVolumeDisk(a2, &v28);
  if ( VolumeDisk < 0 )
    goto LABEL_52;
  v5 = 4;
  if ( *((_DWORD *)this + 295) == 4 )
  {
    ActivePartOnDisk = BdeCfgCanCreateActivePartOnDisk(v28);
    VolumeDisk = ActivePartOnDisk;
    if ( ActivePartOnDisk < 0 )
      goto LABEL_52;
    if ( ActivePartOnDisk == 1 )
      goto LABEL_5;
    v7 = *((_QWORD *)this + 149);
    if ( !v7 )
      v7 = *((_QWORD *)this + 151);
    LargestUnallocatedExtent = BdeCfgFindLargestUnallocatedExtent(v28, v7, &v31, &v30);
    VolumeDisk = LargestUnallocatedExtent;
    if ( LargestUnallocatedExtent >= 0 )
    {
      if ( LargestUnallocatedExtent )
      {
        VolumeDisk = -1063256020;
      }
      else
      {
        *((_DWORD *)this + 16) = 3;
        *((_QWORD *)this + 74) = v31;
        *((_QWORD *)this + 75) = v7;
        v9 = *((_WORD *)this + 592);
        if ( v9 )
          *((_WORD *)this + 304) = v9;
      }
    }
    goto LABEL_52;
  }
  v10 = iswalpha(*((_WORD *)this + 589));
  v11 = *((unsigned __int16 *)this + 589);
  v12 = *((_WORD *)this + 589);
  if ( v10 )
  {
    memset(SourceString, 0, 26);
    if ( iswalpha(v12) )
    {
      VolumeDisk = StringCchPrintfW(SourceString, 0xDu, L"\\GLOBAL??\\%c:", v11);
      if ( VolumeDisk >= 0 )
        VolumeDisk = BdeCfgpGetVolumeNameFromSymbolicLink(SourceString, 0x104u, FileName);
    }
    else
    {
      VolumeDisk = -2147024809;
    }
    v13 = VolumeDisk < 0;
  }
  else
  {
    if ( !iswdigit(v12) )
      goto LABEL_51;
    VolumeDisk = BdeCfgGetVolumeNameFromPartitionNumber(v28, *((unsigned __int16 *)this + 589) - 48, v14, FileName);
    v13 = VolumeDisk < 0;
  }
  if ( v13 )
    goto LABEL_52;
  IsVolumeOnDisk = BdeCfgIsVolumeOnDisk(FileName, v28);
  VolumeDisk = IsVolumeOnDisk;
  if ( IsVolumeOnDisk < 0 )
    goto LABEL_52;
  if ( IsVolumeOnDisk == 1 )
  {
    VolumeDisk = -1063256019;
    goto LABEL_52;
  }
  v16 = *((_DWORD *)this + 295);
  if ( v16 != 2 )
  {
    if ( v16 == 3 )
    {
      VolumeDisk = BdeCfgIsRecoveryPartitionType(FileName, (int *)&v30);
      if ( VolumeDisk < 0 )
        goto LABEL_52;
      if ( (_DWORD)v30 )
      {
        v24 = BdeCfgCheckWinREVolumeAsCandidate(
                FileName,
                *((_QWORD *)this + 151) - *((_QWORD *)this + 154),
                *((_QWORD *)this + 156),
                (struct _BDECFG_CANDIDATE *)v32);
      }
      else
      {
        VolumeDisk = BdeCfgpFindFirstVolume(BdeCfgpFilterVolumesByName, (unsigned __int64)FileName, &v29);
        if ( VolumeDisk == 1 )
          VolumeDisk = -1063256034;
        if ( VolumeDisk < 0 )
          goto LABEL_52;
        v24 = BdeCfgCheckVolumeAsCandidate(
                v29,
                0,
                (CDriveConfiguration *)((char *)this + 1208),
                1u,
                (struct _BDECFG_CANDIDATE *)v32);
      }
      VolumeDisk = v24;
      if ( v24 >= 0 )
      {
        *((_DWORD *)this + 16) = 2;
        v25 = (_OWORD *)((char *)this + 592);
        v26 = v32;
        do
        {
          *v25 = *v26;
          v25[1] = v26[1];
          v25[2] = v26[2];
          v25[3] = v26[3];
          v25[4] = v26[4];
          v25[5] = v26[5];
          v25[6] = v26[6];
          v25[7] = v26[7];
          v25 += 8;
          v26 += 8;
          --v5;
        }
        while ( v5 );
        *v25 = *v26;
        v25[1] = v26[1];
        v25[2] = v26[2];
        *((_QWORD *)v25 + 6) = *((_QWORD *)v26 + 6);
      }
      goto LABEL_52;
    }
LABEL_51:
    VolumeDisk = -1063256037;
    goto LABEL_52;
  }
  v17 = BdeCfgCanCreateActivePartOnDisk(v28);
  VolumeDisk = v17;
  if ( v17 >= 0 )
  {
    if ( v17 == 1 )
    {
LABEL_5:
      VolumeDisk = -1063256017;
      goto LABEL_52;
    }
    VolumeDisk = BdeCfgpFindFirstVolume(BdeCfgpFilterVolumesByName, (unsigned __int64)FileName, &v29);
    if ( VolumeDisk == 1 )
      VolumeDisk = -1063256034;
    if ( VolumeDisk >= 0 )
    {
      v18 = *((_QWORD *)this + 149);
      v19 = (CDriveConfiguration *)((char *)this + 1208);
      if ( !v18 )
        v18 = *(_QWORD *)v19;
      v20 = BdeCfgCheckVolumeAsCandidate(v29, v18, v19, 2u, (struct _BDECFG_CANDIDATE *)v32);
      VolumeDisk = v20;
      if ( v20 >= 0 )
      {
        *((_DWORD *)this + 16) = 1;
        *((_QWORD *)this + 145) = v18;
        v21 = (_OWORD *)((char *)this + 592);
        v22 = v32;
        do
        {
          *v21 = *v22;
          v21[1] = v22[1];
          v21[2] = v22[2];
          v21[3] = v22[3];
          v21[4] = v22[4];
          v21[5] = v22[5];
          v21[6] = v22[6];
          v21[7] = v22[7];
          v21 += 8;
          v22 += 8;
          --v5;
        }
        while ( v5 );
        *v21 = *v22;
        v21[1] = v22[1];
        v21[2] = v22[2];
        *((_QWORD *)v21 + 6) = *((_QWORD *)v22 + 6);
        v23 = *((_WORD *)this + 592);
        if ( v23 )
          *((_WORD *)this + 584) = v23;
      }
      else
      {
        BdeCfgLogError(1, (unsigned int)v20);
        VolumeDisk = -1063256033;
      }
    }
  }
LABEL_52:
  if ( v28 )
  {
    ((void (__fastcall *)(struct IVdsDisk *))v28->lpVtbl->Release)(v28);
    v28 = 0;
  }
  if ( v29 )
    ((void (__fastcall *)(struct IVdsVolume *))v29->lpVtbl->Release)(v29);
  return (unsigned int)VolumeDisk;
}

```

## disassembly

```asm
0x18000fb40  mov     [rsp+arg_10], rbx
0x18000fb45  push    rsi
0x18000fb46  push    rdi
0x18000fb47  push    r12
0x18000fb49  push    r14
0x18000fb4b  push    r15
0x18000fb4d  sub     rsp, 4E0h
0x18000fb54  mov     rax, cs:__security_cookie
0x18000fb5b  xor     rax, rsp
0x18000fb5e  mov     [rsp+508h+var_38], rax
0x18000fb66  mov     rbx, rdx
0x18000fb69  mov     rdi, rcx
0x18000fb6c  xor     edx, edx; Val
0x18000fb6e  mov     r8d, 208h; Size
0x18000fb74  lea     rcx, [rsp+508h+FileName]; void *
0x18000fb7c  call    memset_0
0x18000fb81  xor     r12d, r12d
0x18000fb84  mov     [rsp+508h+var_4C8], r12
0x18000fb89  mov     [rsp+508h+var_4D0], r12
0x18000fb8e  mov     [rsp+508h+var_4B8], r12
0x18000fb93  xor     edx, edx; Val
0x18000fb95  mov     r8d, 238h; Size
0x18000fb9b  lea     rcx, [rsp+508h+var_4A8]; void *
0x18000fba0  call    memset_0
0x18000fba5  mov     dword ptr [rsp+508h+var_4C0], r12d
0x18000fbaa  lea     rdx, [rsp+508h+var_4D0]; struct IVdsDisk **
0x18000fbaf  mov     rcx, rbx; struct IVdsVolume *
0x18000fbb2  call    ?BdeCfgGetVolumeDisk@@YAJPEAUIVdsVolume@@PEAPEAUIVdsDisk@@@Z; BdeCfgGetVolumeDisk(IVdsVolume *,IVdsDisk * *)
0x18000fbb7  mov     ebx, eax
0x18000fbb9  mov     [rsp+508h+var_4D8], eax
0x18000fbbd  test    eax, eax
0x18000fbbf  js      loc_180010004
0x18000fbc5  lea     r15d, [r12+4]
0x18000fbca  cmp     [rdi+49Ch], r15d
0x18000fbd1  jnz     loc_18000FC7C
0x18000fbd7  mov     rcx, [rsp+508h+var_4D0]; struct IVdsDisk *
0x18000fbdc  call    ?BdeCfgCanCreateActivePartOnDisk@@YAJPEAUIVdsDisk@@@Z; BdeCfgCanCreateActivePartOnDisk(IVdsDisk *)
0x18000fbe1  mov     ebx, eax
0x18000fbe3  mov     [rsp+508h+var_4D8], eax
0x18000fbe7  test    eax, eax
0x18000fbe9  js      loc_180010004
0x18000fbef  lea     esi, [r12+1]
0x18000fbf4  cmp     eax, esi
0x18000fbf6  jnz     short loc_18000FC02
0x18000fbf8  mov     ebx, 0C0A0002Fh
0x18000fbfd  jmp     loc_180010000
0x18000fc02  mov     rsi, [rdi+4A8h]
0x18000fc09  test    rsi, rsi
0x18000fc0c  jnz     short loc_18000FC15
0x18000fc0e  mov     rsi, [rdi+4B8h]
0x18000fc15  lea     r9, [rsp+508h+var_4C0]; unsigned __int64 *
0x18000fc1a  lea     r8, [rsp+508h+var_4B8]; unsigned __int64 *
0x18000fc1f  mov     rdx, rsi; unsigned __int64
0x18000fc22  mov     rcx, [rsp+508h+var_4D0]; struct IVdsDisk *
0x18000fc27  call    ?BdeCfgFindLargestUnallocatedExtent@@YAJPEAUIVdsDisk@@_KPEA_K2@Z; BdeCfgFindLargestUnallocatedExtent(IVdsDisk *,unsigned __int64,unsigned __int64 *,unsigned __int64 *)
0x18000fc2c  mov     ebx, eax
0x18000fc2e  mov     [rsp+508h+var_4D8], eax
0x18000fc32  test    eax, eax
0x18000fc34  js      loc_180010004
0x18000fc3a  jz      short loc_18000FC46
0x18000fc3c  mov     ebx, 0C0A0002Ch
0x18000fc41  jmp     loc_180010000
0x18000fc46  mov     dword ptr [rdi+40h], 3
0x18000fc4d  mov     rax, [rsp+508h+var_4B8]
0x18000fc52  mov     [rdi+250h], rax
0x18000fc59  mov     [rdi+258h], rsi
0x18000fc60  movzx   eax, word ptr [rdi+4A0h]
0x18000fc67  test    ax, ax
0x18000fc6a  jz      loc_180010004
0x18000fc70  mov     [rdi+260h], ax
0x18000fc77  jmp     loc_180010004
0x18000fc7c  movzx   ecx, word ptr [rdi+49Ah]; C
0x18000fc83  call    cs:__imp_iswalpha
0x18000fc89  movzx   ebx, word ptr [rdi+49Ah]
0x18000fc90  movzx   ecx, bx; C
0x18000fc93  test    eax, eax
0x18000fc95  jz      short loc_18000FD01
0x18000fc97  xorps   xmm0, xmm0
0x18000fc9a  movups  xmmword ptr [rsp+508h+SourceString], xmm0
0x18000fca2  movups  xmmword ptr [rsp+508h+SourceString+0Ah], xmm0
0x18000fcaa  call    cs:__imp_iswalpha
0x18000fcb0  test    eax, eax
0x18000fcb2  jnz     short loc_18000FCBB
0x18000fcb4  mov     ebx, 80070057h
0x18000fcb9  jmp     short loc_18000FCF9
0x18000fcbb  mov     r9d, ebx
0x18000fcbe  lea     r8, aGlobalC; "\\GLOBAL??\\%c:"
0x18000fcc5  mov     edx, 0Dh; unsigned __int64
0x18000fcca  lea     rcx, [rsp+508h+SourceString]; unsigned __int16 *
0x18000fcd2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000fcd7  mov     ebx, eax
0x18000fcd9  test    eax, eax
0x18000fcdb  js      short loc_18000FCF9
0x18000fcdd  lea     r8, [rsp+508h+FileName]; unsigned __int16 *
0x18000fce5  mov     edx, 104h; unsigned __int64
0x18000fcea  lea     rcx, [rsp+508h+SourceString]; SourceString
0x18000fcf2  call    ?BdeCfgpGetVolumeNameFromSymbolicLink@@YAJPEBG_KPEAG@Z; BdeCfgpGetVolumeNameFromSymbolicLink(ushort const *,unsigned __int64,ushort *)
0x18000fcf7  mov     ebx, eax
0x18000fcf9  mov     [rsp+508h+var_4D8], ebx
0x18000fcfd  test    ebx, ebx
0x18000fcff  jmp     short loc_18000FD33
0x18000fd01  call    cs:__imp_iswdigit
0x18000fd07  test    eax, eax
0x18000fd09  jz      loc_18000FFFB
0x18000fd0f  movzx   edx, word ptr [rdi+49Ah]
0x18000fd16  sub     edx, 30h ; '0'; unsigned int
0x18000fd19  lea     r9, [rsp+508h+FileName]; unsigned __int16 *
0x18000fd21  mov     rcx, [rsp+508h+var_4D0]; struct IVdsDisk *
0x18000fd26  call    ?BdeCfgGetVolumeNameFromPartitionNumber@@YAJPEAUIVdsDisk@@K_KPEAG@Z; BdeCfgGetVolumeNameFromPartitionNumber(IVdsDisk *,ulong,unsigned __int64,ushort *)
0x18000fd2b  mov     ebx, eax
0x18000fd2d  mov     [rsp+508h+var_4D8], eax
0x18000fd31  test    eax, eax
0x18000fd33  js      loc_180010004
0x18000fd39  mov     rdx, [rsp+508h+var_4D0]; struct IVdsDisk *
0x18000fd3e  lea     rcx, [rsp+508h+FileName]; unsigned __int16 *
0x18000fd46  call    ?BdeCfgIsVolumeOnDisk@@YAJPEBGPEAUIVdsDisk@@@Z; BdeCfgIsVolumeOnDisk(ushort const *,IVdsDisk *)
0x18000fd4b  mov     ebx, eax
0x18000fd4d  mov     [rsp+508h+var_4D8], eax
0x18000fd51  test    eax, eax
0x18000fd53  js      loc_180010004
0x18000fd59  mov     esi, 1
0x18000fd5e  cmp     eax, esi
0x18000fd60  jnz     short loc_18000FD6C
0x18000fd62  mov     ebx, 0C0A0002Dh
0x18000fd67  jmp     loc_180010000
0x18000fd6c  mov     eax, [rdi+49Ch]
0x18000fd72  cmp     eax, 2
0x18000fd75  jnz     loc_18000FEBE
0x18000fd7b  mov     rcx, [rsp+508h+var_4D0]; struct IVdsDisk *
0x18000fd80  call    ?BdeCfgCanCreateActivePartOnDisk@@YAJPEAUIVdsDisk@@@Z; BdeCfgCanCreateActivePartOnDisk(IVdsDisk *)
0x18000fd85  mov     ebx, eax
0x18000fd87  mov     [rsp+508h+var_4D8], eax
0x18000fd8b  test    eax, eax
0x18000fd8d  js      loc_180010004
0x18000fd93  cmp     eax, esi
0x18000fd95  jz      loc_18000FBF8
0x18000fd9b  lea     r8, [rsp+508h+var_4C8]; struct IVdsVolume **
0x18000fda0  lea     rdx, [rsp+508h+FileName]; unsigned __int64
0x18000fda8  lea     rcx, ?BdeCfgpFilterVolumesByName@@YAHPEAUIVdsVolume@@_K@Z; int (*)(struct IVdsVolume *, unsigned __int64)
0x18000fdaf  call    ?BdeCfgpFindFirstVolume@@YAJP6AHPEAUIVdsVolume@@_K@Z1PEAPEAU1@@Z; BdeCfgpFindFirstVolume(int (*)(IVdsVolume *,unsigned __int64),unsigned __int64,IVdsVolume * *)
0x18000fdb4  mov     ebx, eax
0x18000fdb6  mov     [rsp+508h+var_4D8], eax
0x18000fdba  mov     eax, 0C0A0001Eh
0x18000fdbf  cmp     ebx, esi
0x18000fdc1  cmovz   ebx, eax
0x18000fdc4  mov     [rsp+508h+var_4D8], ebx
0x18000fdc8  test    ebx, ebx
0x18000fdca  js      loc_180010004
0x18000fdd0  mov     r14, [rdi+4A8h]
0x18000fdd7  lea     r8, [rdi+4B8h]; struct _BDECFG_SIZE_REQUIREMENTS *
0x18000fdde  test    r14, r14
0x18000fde1  jnz     short loc_18000FDE6
0x18000fde3  mov     r14, [r8]
0x18000fde6  lea     rax, [rsp+508h+var_4A8]
0x18000fdeb  mov     [rsp+508h+var_4E8], rax; struct _BDECFG_CANDIDATE *
0x18000fdf0  mov     r9d, 2; unsigned int
0x18000fdf6  mov     rdx, r14; unsigned __int64
0x18000fdf9  mov     rcx, [rsp+508h+var_4C8]; struct IVdsVolume *
0x18000fdfe  call    ?BdeCfgCheckVolumeAsCandidate@@YAJPEAUIVdsVolume@@_KQEAU_BDECFG_SIZE_REQUIREMENTS@@KPEAU_BDECFG_CANDIDATE@@@Z; BdeCfgCheckVolumeAsCandidate(IVdsVolume *,unsigned __int64,_BDECFG_SIZE_REQUIREMENTS * const,ulong,_BDECFG_CANDIDATE *)
0x18000fe03  mov     ebx, eax
0x18000fe05  mov     [rsp+508h+var_4D8], eax
0x18000fe09  test    eax, eax
0x18000fe0b  jns     short loc_18000FE20
0x18000fe0d  mov     edx, eax
0x18000fe0f  mov     ecx, esi
0x18000fe11  call    BdeCfgLogError
0x18000fe16  mov     ebx, 0C0A0001Fh
0x18000fe1b  jmp     loc_180010000
0x18000fe20  mov     [rdi+40h], esi
0x18000fe23  mov     [rdi+488h], r14
0x18000fe2a  lea     rcx, [rdi+250h]
0x18000fe31  lea     rax, [rsp+508h+var_4A8]
0x18000fe36  mov     edx, 80h
0x18000fe3b  movups  xmm0, xmmword ptr [rax]
0x18000fe3e  movups  xmmword ptr [rcx], xmm0
0x18000fe41  movups  xmm1, xmmword ptr [rax+10h]
0x18000fe45  movups  xmmword ptr [rcx+10h], xmm1
0x18000fe49  movups  xmm0, xmmword ptr [rax+20h]
0x18000fe4d  movups  xmmword ptr [rcx+20h], xmm0
0x18000fe51  movups  xmm1, xmmword ptr [rax+30h]
0x18000fe55  movups  xmmword ptr [rcx+30h], xmm1
0x18000fe59  movups  xmm0, xmmword ptr [rax+40h]
0x18000fe5d  movups  xmmword ptr [rcx+40h], xmm0
0x18000fe61  movups  xmm1, xmmword ptr [rax+50h]
0x18000fe65  movups  xmmword ptr [rcx+50h], xmm1
0x18000fe69  movups  xmm0, xmmword ptr [rax+60h]
0x18000fe6d  movups  xmmword ptr [rcx+60h], xmm0
0x18000fe71  movups  xmm1, xmmword ptr [rax+70h]
0x18000fe75  movups  xmmword ptr [rcx+70h], xmm1
0x18000fe79  add     rcx, rdx
0x18000fe7c  add     rax, rdx
0x18000fe7f  sub     r15, rsi
0x18000fe82  jnz     short loc_18000FE3B
0x18000fe84  movups  xmm0, xmmword ptr [rax]
0x18000fe87  movups  xmmword ptr [rcx], xmm0
0x18000fe8a  movups  xmm1, xmmword ptr [rax+10h]
0x18000fe8e  movups  xmmword ptr [rcx+10h], xmm1
0x18000fe92  movups  xmm0, xmmword ptr [rax+20h]
0x18000fe96  movups  xmmword ptr [rcx+20h], xmm0
0x18000fe9a  mov     rax, [rax+30h]
0x18000fe9e  mov     [rcx+30h], rax
0x18000fea2  movzx   eax, word ptr [rdi+4A0h]
0x18000fea9  test    ax, ax
0x18000feac  jz      loc_180010004
0x18000feb2  mov     [rdi+490h], ax
0x18000feb9  jmp     loc_180010004
0x18000febe  cmp     eax, 3
0x18000fec1  jnz     loc_18000FFFB
0x18000fec7  lea     rdx, [rsp+508h+var_4C0]; int *
0x18000fecc  lea     rcx, [rsp+508h+FileName]; lpFileName
0x18000fed4  call    ?BdeCfgIsRecoveryPartitionType@@YAJPEBGPEAH@Z; BdeCfgIsRecoveryPartitionType(ushort const *,int *)
0x18000fed9  mov     ebx, eax
0x18000fedb  mov     [rsp+508h+var_4D8], eax
0x18000fedf  test    eax, eax
0x18000fee1  js      loc_180010004
0x18000fee7  cmp     dword ptr [rsp+508h+var_4C0], r12d
0x18000feec  jz      short loc_18000FF17
0x18000feee  mov     rdx, [rdi+4B8h]
0x18000fef5  sub     rdx, [rdi+4D0h]; unsigned __int64
0x18000fefc  lea     r9, [rsp+508h+var_4A8]; struct _BDECFG_CANDIDATE *
0x18000ff01  mov     r8, [rdi+4E0h]; unsigned __int64
0x18000ff08  lea     rcx, [rsp+508h+FileName]; unsigned __int16 *
0x18000ff10  call    ?BdeCfgCheckWinREVolumeAsCandidate@@YAJPEBG_K1PEAU_BDECFG_CANDIDATE@@@Z; BdeCfgCheckWinREVolumeAsCandidate(ushort const *,unsigned __int64,unsigned __int64,_BDECFG_CANDIDATE *)
0x18000ff15  jmp     short loc_18000FF6C
0x18000ff17  lea     r8, [rsp+508h+var_4C8]; struct IVdsVolume **
0x18000ff1c  lea     rdx, [rsp+508h+FileName]; unsigned __int64
0x18000ff24  lea     rcx, ?BdeCfgpFilterVolumesByName@@YAHPEAUIVdsVolume@@_K@Z; int (*)(struct IVdsVolume *, unsigned __int64)
0x18000ff2b  call    ?BdeCfgpFindFirstVolume@@YAJP6AHPEAUIVdsVolume@@_K@Z1PEAPEAU1@@Z; BdeCfgpFindFirstVolume(int (*)(IVdsVolume *,unsigned __int64),unsigned __int64,IVdsVolume * *)
0x18000ff30  mov     ebx, eax
0x18000ff32  mov     [rsp+508h+var_4D8], eax
0x18000ff36  mov     eax, 0C0A0001Eh
0x18000ff3b  cmp     ebx, esi
0x18000ff3d  cmovz   ebx, eax
0x18000ff40  mov     [rsp+508h+var_4D8], ebx
0x18000ff44  test    ebx, ebx
0x18000ff46  js      loc_180010004
0x18000ff4c  lea     r8, [rdi+4B8h]; struct _BDECFG_SIZE_REQUIREMENTS *
0x18000ff53  lea     rax, [rsp+508h+var_4A8]
0x18000ff58  mov     [rsp+508h+var_4E8], rax; struct _BDECFG_CANDIDATE *
0x18000ff5d  mov     r9d, esi; unsigned int
0x18000ff60  xor     edx, edx; unsigned __int64
0x18000ff62  mov     rcx, [rsp+508h+var_4C8]; struct IVdsVolume *
0x18000ff67  call    ?BdeCfgCheckVolumeAsCandidate@@YAJPEAUIVdsVolume@@_KQEAU_BDECFG_SIZE_REQUIREMENTS@@KPEAU_BDECFG_CANDIDATE@@@Z; BdeCfgCheckVolumeAsCandidate(IVdsVolume *,unsigned __int64,_BDECFG_SIZE_REQUIREMENTS * const,ulong,_BDECFG_CANDIDATE *)
0x18000ff6c  test    eax, eax
0x18000ff6e  mov     [rsp+508h+var_4D8], eax
0x18000ff72  mov     ebx, eax
0x18000ff74  js      loc_180010004
0x18000ff7a  mov     dword ptr [rdi+40h], 2
0x18000ff81  add     rdi, 250h
0x18000ff88  lea     rax, [rsp+508h+var_4A8]
0x18000ff8d  mov     edx, 80h
0x18000ff92  movups  xmm0, xmmword ptr [rax]
0x18000ff95  movups  xmmword ptr [rdi], xmm0
0x18000ff98  movups  xmm1, xmmword ptr [rax+10h]
0x18000ff9c  movups  xmmword ptr [rdi+10h], xmm1
0x18000ffa0  movups  xmm0, xmmword ptr [rax+20h]
0x18000ffa4  movups  xmmword ptr [rdi+20h], xmm0
0x18000ffa8  movups  xmm1, xmmword ptr [rax+30h]
0x18000ffac  movups  xmmword ptr [rdi+30h], xmm1
0x18000ffb0  movups  xmm0, xmmword ptr [rax+40h]
0x18000ffb4  movups  xmmword ptr [rdi+40h], xmm0
0x18000ffb8  movups  xmm1, xmmword ptr [rax+50h]
0x18000ffbc  movups  xmmword ptr [rdi+50h], xmm1
0x18000ffc0  movups  xmm0, xmmword ptr [rax+60h]
0x18000ffc4  movups  xmmword ptr [rdi+60h], xmm0
0x18000ffc8  movups  xmm1, xmmword ptr [rax+70h]
0x18000ffcc  movups  xmmword ptr [rdi+70h], xmm1
0x18000ffd0  add     rdi, rdx
0x18000ffd3  add     rax, rdx
0x18000ffd6  sub     r15, rsi
0x18000ffd9  jnz     short loc_18000FF92
0x18000ffdb  movups  xmm0, xmmword ptr [rax]
0x18000ffde  movups  xmmword ptr [rdi], xmm0
0x18000ffe1  movups  xmm1, xmmword ptr [rax+10h]
0x18000ffe5  movups  xmmword ptr [rdi+10h], xmm1
0x18000ffe9  movups  xmm0, xmmword ptr [rax+20h]
0x18000ffed  movups  xmmword ptr [rdi+20h], xmm0
0x18000fff1  mov     rax, [rax+30h]
0x18000fff5  mov     [rdi+30h], rax
0x18000fff9  jmp     short loc_180010004
0x18000fffb  mov     ebx, 0C0A0001Bh
0x180010000  mov     [rsp+508h+var_4D8], ebx
0x180010004  mov     rcx, [rsp+508h+var_4D0]
0x180010009  test    rcx, rcx
0x18001000c  jz      short loc_18001001F
0x18001000e  mov     rax, [rcx]
0x180010011  mov     rax, [rax+10h]
0x180010015  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001001a  mov     [rsp+508h+var_4D0], r12
0x18001001f  mov     rcx, [rsp+508h+var_4C8]
0x180010024  test    rcx, rcx
0x180010027  jz      short loc_180010035
0x180010029  mov     rax, [rcx]
0x18001002c  mov     rax, [rax+10h]
0x180010030  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010035  mov     eax, ebx
0x180010037  mov     rcx, [rsp+508h+var_38]
0x18001003f  xor     rcx, rsp; StackCookie
0x180010042  call    __security_check_cookie
0x180010047  mov     rbx, [rsp+508h+arg_10]
  ... truncated ...
```
