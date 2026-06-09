# BdeCfgCheckWinREVolumeAsCandidate(ushort const *,unsigned __int64,unsigned __int64,_BDECFG_CANDIDATE *)

- ea: `0x180002814`
- end: `0x180002bd0`
- name: `?BdeCfgCheckWinREVolumeAsCandidate@@YAJPEBG_K1PEAU_BDECFG_CANDIDATE@@@Z`
- size: `956`
- prototype: `__int64 __fastcall(WCHAR *, unsigned __int64, unsigned __int64, struct _BDECFG_CANDIDATE *)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, service_task`

## callers

- `0x180003240`
- `0x18000fb40`

## callees

- `0x180002814`
- `0x18000634c`
- `0x180006738`
- `0x180006eb8`
- `0x180007210`
- `0x180007470`
- `0x1800081bc`
- `0x1800082ec`
- `0x18000dbc0`
- `0x18000e300`
- `0x18001358e`
- `0x1800135c0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800028c8`
- `msvcrt!_wcsicmp` at `0x1800028c8`
- `KERNEL32!GetVolumeInformationByHandleW` at `0x180002a12`
- `KERNEL32!GetVolumeInformationByHandleW` at `0x180002a12`
- `KERNEL32!GetLastError` at `0x180002919`
- `KERNEL32!GetLastError` at `0x180002a1c`
- `KERNEL32!GetLastError` at `0x180002919`
- `KERNEL32!GetLastError` at `0x180002a1c`
- `KERNEL32!CreateFileW` at `0x18000290a`
- `KERNEL32!CreateFileW` at `0x18000290a`
- `KERNEL32!CloseHandle` at `0x180002a62`
- `KERNEL32!CloseHandle` at `0x180002a70`
- `KERNEL32!CloseHandle` at `0x180002a62`
- `KERNEL32!CloseHandle` at `0x180002a70`

## pseudocode

```c
__int64 __fastcall BdeCfgCheckWinREVolumeAsCandidate(
        WCHAR *a1,
        unsigned __int64 a2,
        unsigned __int64 a3,
        struct _BDECFG_CANDIDATE *a4)
{
  struct _BDECFG_CANDIDATE *v4; // rsi
  __int64 v9; // r15
  unsigned int v10; // ebx
  HANDLE FileW; // rax
  void *v12; // r14
  signed int LastError; // eax
  __int64 v14; // rdx
  int v15; // eax
  __int64 v16; // rdx
  DWORD v17; // ecx
  DWORD v18; // ecx
  signed int v19; // eax
  int IsVolumeLogical; // eax
  DWORD v21; // ecx
  __int64 v22; // rax
  char *v23; // rdx
  WCHAR *v24; // rcx
  char *v25; // rcx
  __int64 v26; // rcx
  _OWORD *v27; // rax
  __int128 v28; // xmm1
  __int128 v29; // xmm0
  __int128 v30; // xmm1
  __int128 v31; // xmm0
  __int128 v32; // xmm1
  __int128 v33; // xmm0
  __int128 v34; // xmm1
  __int128 v35; // xmm1
  __int128 v36; // xmm0
  __int64 v37; // rax
  DWORD FileSystemFlags; // [rsp+40h] [rbp-C0h] BYREF
  int v39[3]; // [rsp+44h] [rbp-BCh] BYREF
  _DWORD v40[2]; // [rsp+50h] [rbp-B0h] BYREF
  char v41; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 v42; // [rsp+260h] [rbp+160h] BYREF
  unsigned __int64 v43; // [rsp+268h] [rbp+168h] BYREF
  int v44; // [rsp+278h] [rbp+178h]
  unsigned __int16 v45[4]; // [rsp+27Ch] [rbp+17Ch] BYREF
  unsigned int v46[3]; // [rsp+284h] [rbp+184h] BYREF
  wchar_t String2[264]; // [rsp+290h] [rbp+190h] BYREF

  v4 = a4;
  v39[0] = 0;
  if ( !g_pService )
    return 3231711254LL;
  if ( a1 && a4 )
  {
    memset_0(v40, 0, 0x238u);
    memset_0(v4, 0, 0x238u);
    v9 = 260;
    if ( !(unsigned int)BdeCfgDetectWinREVolumeName(0x104u, String2) && !_wcsicmp(a1, String2) )
    {
      v40[1] = 1;
      v40[0] = 0;
      v44 = 0;
      FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x80u, 0);
      v12 = FileW;
      if ( FileW == (HANDLE)-1LL )
      {
        LastError = GetLastError();
        v10 = LastError;
        if ( LastError > 0 )
          v10 = (unsigned __int16)LastError | 0x80070000;
LABEL_11:
        v14 = v10;
LABEL_12:
        BdeCfgLogError(1, v14);
        return v10;
      }
      v15 = BdeCfgpCheckVolumePartitionForMerge(FileW, v46);
      v10 = v15;
      if ( v15 < 0 )
      {
        if ( v15 == -1063256060 )
        {
          v17 = 1084227649;
        }
        else
        {
          if ( v15 != -1063256056 )
          {
LABEL_16:
            v16 = (unsigned int)v15;
LABEL_32:
            BdeCfgLogError(1, v16);
            goto LABEL_36;
          }
          v17 = 1084227650;
        }
LABEL_35:
        BdeCfgpLogFailedWinRETarget(v17, a1);
        v10 = -1063256032;
        goto LABEL_36;
      }
      v15 = BdeCfgpCheckVolumeNtfsDataForMerge(v12, a2, a3, &v43, &v42);
      v10 = v15;
      if ( v15 < 0 )
      {
        switch ( v15 )
        {
          case -1063256059:
            v18 = 1084227640;
            break;
          case -1063256016:
            BdeCfgpLogFailedWinRETarget(0x40A0003Au, a1);
            v10 = -1063256015;
LABEL_36:
            CloseHandle(v12);
            return v10;
          case -1063256014:
            v18 = 1084227641;
            break;
          default:
            goto LABEL_16;
        }
        BdeCfgpLogFailedWinRETarget(v18, a1);
        goto LABEL_36;
      }
      FileSystemFlags = 0;
      if ( GetVolumeInformationByHandleW(v12, 0, 0, 0, 0, &FileSystemFlags, 0, 0) )
      {
        if ( (FileSystemFlags & 0x8000) != 0 )
        {
          v17 = 1084227644;
          goto LABEL_35;
        }
      }
      else
      {
        v19 = GetLastError();
        v10 = v19;
        if ( v19 > 0 )
          v10 = (unsigned __int16)v19 | 0x80070000;
        if ( (v10 & 0x80000000) != 0 )
        {
          v16 = v10;
          goto LABEL_32;
        }
      }
      CloseHandle(v12);
      IsVolumeLogical = BdeCfgpIsVolumeLogical(a1, v39);
      v10 = IsVolumeLogical;
      if ( IsVolumeLogical < 0 )
      {
        v14 = (unsigned int)IsVolumeLogical;
        goto LABEL_12;
      }
      if ( v39[0] )
      {
        v21 = 1084227646;
      }
      else
      {
        if ( (unsigned int)BdeCfgpIsVolumeEncrypted(a1) == 1 )
        {
          v22 = 2147483646;
          v23 = &v41;
          v24 = a1;
          do
          {
            if ( !v22 )
              break;
            if ( !*v24 )
              break;
            *(_WORD *)v23 = *v24++;
            v23 += 2;
            --v22;
            --v9;
          }
          while ( v9 );
          v25 = v23 - 2;
          v10 = v9 == 0 ? 0x8007007A : 0;
          if ( v9 )
            v25 = v23;
          *(_WORD *)v25 = 0;
          if ( v9 )
          {
            BdeCfgGetVolumeDriveLetter(a1, v45);
            BdeCfgLogCandidateDrive(v40);
            v26 = 4;
            v27 = v40;
            v10 = 0;
            do
            {
              v28 = v27[1];
              *(_OWORD *)v4 = *v27;
              v29 = v27[2];
              *((_OWORD *)v4 + 1) = v28;
              v30 = v27[3];
              *((_OWORD *)v4 + 2) = v29;
              v31 = v27[4];
              *((_OWORD *)v4 + 3) = v30;
              v32 = v27[5];
              *((_OWORD *)v4 + 4) = v31;
              v33 = v27[6];
              *((_OWORD *)v4 + 5) = v32;
              v34 = v27[7];
              v27 += 8;
              *((_OWORD *)v4 + 6) = v33;
              *((_OWORD *)v4 + 7) = v34;
              v4 = (struct _BDECFG_CANDIDATE *)((char *)v4 + 128);
              --v26;
            }
            while ( v26 );
            v35 = v27[1];
            *(_OWORD *)v4 = *v27;
            v36 = v27[2];
            v37 = *((_QWORD *)v27 + 6);
            *((_OWORD *)v4 + 1) = v35;
            *((_OWORD *)v4 + 2) = v36;
            *((_QWORD *)v4 + 6) = v37;
            return v10;
          }
          goto LABEL_11;
        }
        v21 = 1084227648;
      }
      BdeCfgpLogFailedWinRETarget(v21, a1);
    }
    return (unsigned int)-1063256032;
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x180002814  push    rbp
0x180002816  push    rbx
0x180002817  push    rsi
0x180002818  push    rdi
0x180002819  push    r12
0x18000281b  push    r13
0x18000281d  push    r14
0x18000281f  push    r15
0x180002821  lea     rbp, [rsp-3B8h]
0x180002829  sub     rsp, 4B8h
0x180002830  mov     rax, cs:__security_cookie
0x180002837  xor     rax, rsp
0x18000283a  mov     [rbp+3F0h+var_50], rax
0x180002841  xor     r14d, r14d
0x180002844  mov     rsi, r9
0x180002847  cmp     cs:?g_pService@@3PEAUIVdsService@@EA, r14; IVdsService * g_pService
0x18000284e  mov     r13, r8
0x180002851  mov     r12, rdx
0x180002854  mov     [rsp+4F0h+var_4AC], r14d
0x180002859  mov     rdi, rcx
0x18000285c  jnz     short loc_180002868
0x18000285e  mov     eax, 0C0A00016h
0x180002863  jmp     loc_180002BAD
0x180002868  test    rdi, rdi
0x18000286b  jz      loc_180002BA8
0x180002871  test    rsi, rsi
0x180002874  jz      loc_180002BA8
0x18000287a  mov     ebx, 238h
0x18000287f  lea     rcx, [rsp+4F0h+var_4A0]; void *
0x180002884  mov     r8d, ebx; Size
0x180002887  xor     edx, edx; Val
0x180002889  call    memset_0
0x18000288e  mov     r8d, ebx; Size
0x180002891  xor     edx, edx; Val
0x180002893  mov     rcx, rsi; void *
0x180002896  call    memset_0
0x18000289b  mov     r15d, 104h
0x1800028a1  lea     rdx, [rbp+3F0h+String2]; unsigned __int16 *
0x1800028a8  mov     ecx, r15d; unsigned __int64
0x1800028ab  call    ?BdeCfgDetectWinREVolumeName@@YAJ_KPEAG@Z; BdeCfgDetectWinREVolumeName(unsigned __int64,ushort *)
0x1800028b0  test    eax, eax
0x1800028b2  jz      short loc_1800028BE
0x1800028b4  mov     ebx, 0C0A00020h
0x1800028b9  jmp     loc_180002BA4
0x1800028be  lea     rdx, [rbp+3F0h+String2]; String2
0x1800028c5  mov     rcx, rdi; String1
0x1800028c8  call    cs:__imp__wcsicmp
0x1800028ce  test    eax, eax
0x1800028d0  jnz     short loc_1800028B4
0x1800028d2  mov     [rsp+4F0h+hTemplateFile], r14; hTemplateFile
0x1800028d7  lea     r8d, [rax+1]; dwShareMode
0x1800028db  mov     [rsp+4F0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800028e3  xor     r9d, r9d; lpSecurityAttributes
0x1800028e6  mov     edx, 80000000h; dwDesiredAccess
0x1800028eb  mov     [rsp+4F0h+dwCreationDisposition], 3; dwCreationDisposition
0x1800028f3  mov     rcx, rdi; lpFileName
0x1800028f6  mov     [rsp+4F0h+var_49C], 1
0x1800028fe  mov     [rsp+4F0h+var_4A0], r14d
0x180002903  mov     [rbp+3F0h+var_278], r14d
0x18000290a  call    cs:__imp_CreateFileW
0x180002910  mov     r14, rax
0x180002913  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180002917  jnz     short loc_18000293F
0x180002919  call    cs:__imp_GetLastError
0x18000291f  mov     ebx, eax
0x180002921  test    eax, eax
0x180002923  jle     short loc_18000292E
0x180002925  movzx   ebx, ax
0x180002928  or      ebx, 80070000h
0x18000292e  mov     edx, ebx
0x180002930  mov     ecx, 1
0x180002935  call    BdeCfgLogError
0x18000293a  jmp     loc_180002BA4
0x18000293f  lea     rdx, [rbp+3F0h+var_26C]; unsigned int *
0x180002946  mov     rcx, r14; hDevice
0x180002949  call    ?BdeCfgpCheckVolumePartitionForMerge@@YAJPEAXPEAK@Z; BdeCfgpCheckVolumePartitionForMerge(void *,ulong *)
0x18000294e  mov     ebx, eax
0x180002950  test    eax, eax
0x180002952  jns     short loc_18000297D
0x180002954  cmp     eax, 0C0A00004h
0x180002959  jz      short loc_180002973
0x18000295b  cmp     eax, 0C0A00008h
0x180002960  jz      short loc_180002969
0x180002962  mov     edx, eax
0x180002964  jmp     loc_180002A37
0x180002969  mov     ecx, 40A00042h
0x18000296e  jmp     loc_180002A52
0x180002973  mov     ecx, 40A00041h
0x180002978  jmp     loc_180002A52
0x18000297d  lea     rax, [rbp+3F0h+var_290]
0x180002984  mov     r8, r13; unsigned __int64
0x180002987  lea     r9, [rbp+3F0h+var_288]; unsigned __int64 *
0x18000298e  mov     qword ptr [rsp+4F0h+dwCreationDisposition], rax; unsigned __int64 *
0x180002993  mov     rdx, r12; unsigned __int64
0x180002996  mov     rcx, r14; void *
0x180002999  call    ?BdeCfgpCheckVolumeNtfsDataForMerge@@YAJPEAX_K1PEA_K2@Z; BdeCfgpCheckVolumeNtfsDataForMerge(void *,unsigned __int64,unsigned __int64,unsigned __int64 *,unsigned __int64 *)
0x18000299e  xor     r12d, r12d
0x1800029a1  mov     ebx, eax
0x1800029a3  test    eax, eax
0x1800029a5  jns     short loc_1800029E9
0x1800029a7  cmp     eax, 0C0A00005h
0x1800029ac  jz      short loc_1800029DA
0x1800029ae  cmp     eax, 0C0A00030h
0x1800029b3  jz      short loc_1800029C3
0x1800029b5  cmp     eax, 0C0A00032h
0x1800029ba  jnz     short loc_180002962
0x1800029bc  mov     ecx, 40A00039h
0x1800029c1  jmp     short loc_1800029DF
0x1800029c3  mov     rdx, rdi; unsigned __int16 *
0x1800029c6  mov     ecx, 40A0003Ah; dwMessageId
0x1800029cb  call    BdeCfgpLogFailedWinRETarget
0x1800029d0  mov     ebx, 0C0A00031h
0x1800029d5  jmp     loc_180002A5F
0x1800029da  mov     ecx, 40A00038h; dwMessageId
0x1800029df  mov     rdx, rdi; unsigned __int16 *
0x1800029e2  call    BdeCfgpLogFailedWinRETarget
0x1800029e7  jmp     short loc_180002A5F
0x1800029e9  mov     [rsp+4F0h+nFileSystemNameSize], r12d; nFileSystemNameSize
0x1800029ee  lea     rax, [rsp+4F0h+FileSystemFlags]
0x1800029f3  mov     [rsp+4F0h+hTemplateFile], r12; lpFileSystemNameBuffer
0x1800029f8  xor     r9d, r9d; lpVolumeSerialNumber
0x1800029fb  mov     qword ptr [rsp+4F0h+dwFlagsAndAttributes], rax; lpFileSystemFlags
0x180002a00  xor     r8d, r8d; nVolumeNameSize
0x180002a03  xor     edx, edx; lpVolumeNameBuffer
0x180002a05  mov     qword ptr [rsp+4F0h+dwCreationDisposition], r12; lpMaximumComponentLength
0x180002a0a  mov     rcx, r14; hFile
0x180002a0d  mov     [rsp+4F0h+FileSystemFlags], r12d
0x180002a12  call    cs:__imp_GetVolumeInformationByHandleW
0x180002a18  test    eax, eax
0x180002a1a  jnz     short loc_180002A43
0x180002a1c  call    cs:__imp_GetLastError
0x180002a22  mov     ebx, eax
0x180002a24  test    eax, eax
0x180002a26  jle     short loc_180002A31
0x180002a28  movzx   ebx, ax
0x180002a2b  or      ebx, 80070000h
0x180002a31  test    ebx, ebx
0x180002a33  jns     short loc_180002A6D
0x180002a35  mov     edx, ebx
0x180002a37  mov     ecx, 1
0x180002a3c  call    BdeCfgLogError
0x180002a41  jmp     short loc_180002A5F
0x180002a43  test    [rsp+4F0h+FileSystemFlags], 8000h
0x180002a4b  jz      short loc_180002A6D
0x180002a4d  mov     ecx, 40A0003Ch; dwMessageId
0x180002a52  mov     rdx, rdi; unsigned __int16 *
0x180002a55  call    BdeCfgpLogFailedWinRETarget
0x180002a5a  mov     ebx, 0C0A00020h
0x180002a5f  mov     rcx, r14; hObject
0x180002a62  call    cs:__imp_CloseHandle
0x180002a68  jmp     loc_180002BA4
0x180002a6d  mov     rcx, r14; hObject
0x180002a70  call    cs:__imp_CloseHandle
0x180002a76  lea     rdx, [rsp+4F0h+var_4AC]; int *
0x180002a7b  mov     rcx, rdi; unsigned __int16 *
0x180002a7e  call    ?BdeCfgpIsVolumeLogical@@YAJPEBGPEAH@Z; BdeCfgpIsVolumeLogical(ushort const *,int *)
0x180002a83  mov     ebx, eax
0x180002a85  test    eax, eax
0x180002a87  jns     short loc_180002A90
0x180002a89  mov     edx, eax
0x180002a8b  jmp     loc_180002930
0x180002a90  cmp     [rsp+4F0h+var_4AC], r12d
0x180002a95  jz      short loc_180002AA9
0x180002a97  mov     ecx, 40A0003Eh; dwMessageId
0x180002a9c  mov     rdx, rdi; unsigned __int16 *
0x180002a9f  call    BdeCfgpLogFailedWinRETarget
0x180002aa4  jmp     loc_1800028B4
0x180002aa9  mov     rcx, rdi; unsigned __int16 *
0x180002aac  call    ?BdeCfgpIsVolumeEncrypted@@YAJPEBG@Z; BdeCfgpIsVolumeEncrypted(ushort const *)
0x180002ab1  cmp     eax, 1
0x180002ab4  jz      short loc_180002ABD
0x180002ab6  mov     ecx, 40A00040h
0x180002abb  jmp     short loc_180002A9C
0x180002abd  mov     eax, 7FFFFFFEh
0x180002ac2  lea     rdx, [rsp+4F0h+var_498]
0x180002ac7  mov     rcx, rdi
0x180002aca  test    rax, rax
0x180002acd  jz      short loc_180002AEE
0x180002acf  movzx   r8d, word ptr [rcx]
0x180002ad3  test    r8w, r8w
0x180002ad7  jz      short loc_180002AEE
0x180002ad9  mov     [rdx], r8w
0x180002add  add     rcx, 2
0x180002ae1  add     rdx, 2
0x180002ae5  dec     rax
0x180002ae8  sub     r15, 1
0x180002aec  jnz     short loc_180002ACA
0x180002aee  mov     rax, r15
0x180002af1  lea     rcx, [rdx-2]
0x180002af5  neg     rax
0x180002af8  sbb     ebx, ebx
0x180002afa  not     ebx
0x180002afc  and     ebx, 8007007Ah
0x180002b02  test    r15, r15
0x180002b05  cmovnz  rcx, rdx
0x180002b09  mov     [rcx], r12w
0x180002b0d  jz      loc_18000292E
0x180002b13  lea     rdx, [rbp+3F0h+var_274]; unsigned __int16 *
0x180002b1a  mov     rcx, rdi; unsigned __int16 *
0x180002b1d  call    ?BdeCfgGetVolumeDriveLetter@@YAJPEBGPEAG@Z; BdeCfgGetVolumeDriveLetter(ushort const *,ushort *)
0x180002b22  lea     rcx, [rsp+4F0h+var_4A0]
0x180002b27  call    BdeCfgLogCandidateDrive
0x180002b2c  mov     ecx, 4
0x180002b31  lea     rax, [rsp+4F0h+var_4A0]
0x180002b36  mov     ebx, r12d
0x180002b39  lea     edx, [rcx+7Ch]
0x180002b3c  movups  xmm0, xmmword ptr [rax]
0x180002b3f  movups  xmm1, xmmword ptr [rax+10h]
0x180002b43  movups  xmmword ptr [rsi], xmm0
0x180002b46  movups  xmm0, xmmword ptr [rax+20h]
0x180002b4a  movups  xmmword ptr [rsi+10h], xmm1
0x180002b4e  movups  xmm1, xmmword ptr [rax+30h]
0x180002b52  movups  xmmword ptr [rsi+20h], xmm0
0x180002b56  movups  xmm0, xmmword ptr [rax+40h]
0x180002b5a  movups  xmmword ptr [rsi+30h], xmm1
0x180002b5e  movups  xmm1, xmmword ptr [rax+50h]
0x180002b62  movups  xmmword ptr [rsi+40h], xmm0
0x180002b66  movups  xmm0, xmmword ptr [rax+60h]
0x180002b6a  movups  xmmword ptr [rsi+50h], xmm1
0x180002b6e  movups  xmm1, xmmword ptr [rax+70h]
0x180002b72  add     rax, rdx
0x180002b75  movups  xmmword ptr [rsi+60h], xmm0
0x180002b79  movups  xmmword ptr [rsi+70h], xmm1
0x180002b7d  add     rsi, rdx
0x180002b80  sub     rcx, 1
0x180002b84  jnz     short loc_180002B3C
0x180002b86  movups  xmm0, xmmword ptr [rax]
0x180002b89  movups  xmm1, xmmword ptr [rax+10h]
0x180002b8d  movups  xmmword ptr [rsi], xmm0
0x180002b90  movups  xmm0, xmmword ptr [rax+20h]
0x180002b94  mov     rax, [rax+30h]
0x180002b98  movups  xmmword ptr [rsi+10h], xmm1
0x180002b9c  movups  xmmword ptr [rsi+20h], xmm0
0x180002ba0  mov     [rsi+30h], rax
0x180002ba4  mov     eax, ebx
0x180002ba6  jmp     short loc_180002BAD
0x180002ba8  mov     eax, 80004003h
0x180002bad  mov     rcx, [rbp+3F0h+var_50]
0x180002bb4  xor     rcx, rsp; StackCookie
0x180002bb7  call    __security_check_cookie
0x180002bbc  add     rsp, 4B8h
0x180002bc3  pop     r15
0x180002bc5  pop     r14
0x180002bc7  pop     r13
0x180002bc9  pop     r12
0x180002bcb  pop     rdi
0x180002bcc  pop     rsi
0x180002bcd  pop     rbx
0x180002bce  pop     rbp
0x180002bcf  retn
```
