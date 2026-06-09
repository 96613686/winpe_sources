# Csl::ExpandSystemVolume(void)

- ea: `0x18002463c`
- end: `0x180024af5`
- name: `?ExpandSystemVolume@Csl@@YAJXZ`
- size: `1209`
- prototype: `__int64 __fastcall(Csl *this, struct Path *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x1800178e0`

## callees

- `0x180002140`
- `0x180002534`
- `0x1800045e4`
- `0x180007b2c`
- `0x1800095f8`
- `0x180009e10`
- `0x18000a768`
- `0x18000af30`
- `0x18000b0c0`
- `0x18000cd00`
- `0x180024218`
- `0x18002463c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024965`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024a9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024965`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024a9e`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800249fe`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800249fe`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800248db`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800248db`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180024936`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180024a7c`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180024936`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180024a7c`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18002481d`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18002481d`

## pseudocode

```c
__int64 __fastcall Csl::ExpandSystemVolume(Csl *this, struct Path *a2)
{
  int SystemDrivePath; // eax
  unsigned int LastError; // ebx
  __int64 v4; // rdx
  __int64 v6; // rdx
  const char *v7; // r9
  __int64 v8; // rdx
  __int64 v9; // rdx
  HANDLE FileW; // rbx
  unsigned __int64 *v11; // r8
  const char *v12; // r9
  __int64 v13; // rdx
  int v14; // eax
  unsigned int v15; // esi
  int v16; // eax
  NTSTATUS v17; // eax
  signed __int64 v18; // rax
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  int dwCreationDispositionb; // [rsp+20h] [rbp-E0h]
  int dwCreationDispositionc; // [rsp+20h] [rbp-E0h]
  LPWSTR lpszVolumeName; // [rsp+40h] [rbp-C0h] BYREF
  _WORD *v24; // [rsp+48h] [rbp-B8h]
  _WORD v25[8]; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpszVolumeMountPoint[2]; // [rsp+60h] [rbp-A0h] BYREF
  _WORD v27[8]; // [rsp+70h] [rbp-90h] BYREF
  DWORD BytesReturned; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 InBuffer; // [rsp+88h] [rbp-78h] BYREF
  void *v30; // [rsp+90h] [rbp-70h] BYREF
  char *v31; // [rsp+98h] [rbp-68h]
  _WORD v32[8]; // [rsp+A0h] [rbp-60h] BYREF
  void *v33[2]; // [rsp+B0h] [rbp-50h] BYREF
  _WORD v34[8]; // [rsp+C0h] [rbp-40h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+D0h] [rbp-30h] BYREF
  __int128 FsInformation; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v37; // [rsp+F0h] [rbp-10h]
  _OWORD OutBuffer[2]; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  lpszVolumeMountPoint[0] = v27;
  v27[0] = 0;
  lpszVolumeMountPoint[1] = v27;
  v30 = v32;
  v31 = (char *)v32;
  v32[0] = 0;
  SystemDrivePath = Csl::GetSystemDrivePath((Csl *)&v30, a2);
  LastError = SystemDrivePath;
  if ( SystemDrivePath < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x561,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslfilesystem.cpp",
      (const char *)(unsigned int)SystemDrivePath,
      dwCreationDisposition);
LABEL_9:
    if ( v30 != v32 )
      operator delete(v30, (const struct std::nothrow_t *)&std::nothrow);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3AE,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslstorage.cpp",
      (const char *)LastError,
      dwCreationDispositiona);
LABEL_12:
    if ( lpszVolumeMountPoint[0] != v27 )
      operator delete((void *)lpszVolumeMountPoint[0], (const struct std::nothrow_t *)&std::nothrow);
    return LastError;
  }
  v33[0] = v34;
  v33[1] = v34;
  v34[0] = 0;
  if ( !utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
          (__int64)v33,
          v30,
          (v31 - (_BYTE *)v30) >> 1) )
  {
    v4 = 1380;
    goto LABEL_7;
  }
  if ( !utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
          (__int64)v33,
          L"\\",
          1u) )
  {
    v4 = 1383;
LABEL_7:
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslfilesystem.cpp",
      (const char *)0x8007000ELL,
      dwCreationDisposition);
    if ( v33[0] != v34 )
      operator delete(v33[0], (const struct std::nothrow_t *)&std::nothrow);
    goto LABEL_9;
  }
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::operator=(
    (__int64)lpszVolumeMountPoint,
    (__int64)v33);
  if ( v33[0] != v34 )
    operator delete(v33[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v30 != v32 )
    operator delete(v30, (const struct std::nothrow_t *)&std::nothrow);
  v25[0] = 0;
  lpszVolumeName = v25;
  v24 = v25;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::resize(
                           &lpszVolumeName,
                           50) )
  {
    v6 = 946;
LABEL_30:
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslstorage.cpp",
      (const char *)0x8007000ELL,
      dwCreationDisposition);
LABEL_24:
    if ( lpszVolumeName != v25 )
      operator delete(lpszVolumeName, (const struct std::nothrow_t *)&std::nothrow);
    goto LABEL_12;
  }
  if ( !GetVolumeNameForVolumeMountPointW(lpszVolumeMountPoint[0], lpszVolumeName, 0x32u) )
  {
    v8 = 950;
LABEL_23:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v8,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslstorage.cpp",
                  v7);
    goto LABEL_24;
  }
  v9 = -1;
  do
    ++v9;
  while ( lpszVolumeName[v9] );
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::resize(
                           &lpszVolumeName,
                           v9) )
  {
    v6 = 953;
    goto LABEL_30;
  }
  *--v24 = 0;
  FileW = CreateFileW(lpszVolumeName, 0xC0000000, 3u, 0, 3u, 0x2000000u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    v8 = 966;
    goto LABEL_23;
  }
  BytesReturned = 0;
  memset(OutBuffer, 0, sizeof(OutBuffer));
  if ( !DeviceIoControl(FileW, 0x560000u, 0, 0, OutBuffer, 0x20u, &BytesReturned, 0) )
  {
    v13 = 983;
LABEL_35:
    v14 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)v13,
            (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslstorage.cpp",
            v12);
LABEL_36:
    v15 = v14;
LABEL_37:
    if ( FileW )
      CloseHandle(FileW);
    if ( lpszVolumeName != v25 )
      operator delete(lpszVolumeName, (const struct std::nothrow_t *)&std::nothrow);
    if ( lpszVolumeMountPoint[0] != v27 )
      operator delete((void *)lpszVolumeMountPoint[0], (const struct std::nothrow_t *)&std::nothrow);
    return v15;
  }
  InBuffer = 0;
  v16 = Csl::ExpandDiskPartition((Csl *)DWORD2(OutBuffer[0]), &InBuffer, v11);
  v15 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3DD,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslstorage.cpp",
      (const char *)(unsigned int)v16,
      dwCreationDispositionb);
    goto LABEL_37;
  }
  FsInformation = 0;
  v37 = 0;
  IoStatusBlock = 0;
  v17 = NtQueryVolumeInformationFile(FileW, &IoStatusBlock, &FsInformation, 0x20u, FileFsFullSizeInformation);
  if ( v17 < 0 )
  {
    v14 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x3E7,
            (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslstorage.cpp",
            (const char *)(unsigned int)v17,
            dwCreationDispositionc);
    goto LABEL_36;
  }
  v18 = InBuffer / (unsigned int)(HIDWORD(v37) * DWORD2(v37));
  if ( v18 >= (__int64)FsInformation + 1 )
  {
    InBuffer = v18 * DWORD2(v37);
    if ( !DeviceIoControl(FileW, 0x900F0u, &InBuffer, 8u, 0, 0, &BytesReturned, 0) )
    {
      v13 = 1021;
      goto LABEL_35;
    }
  }
  if ( FileW )
    CloseHandle(FileW);
  if ( lpszVolumeName != v25 )
    operator delete(lpszVolumeName, (const struct std::nothrow_t *)&std::nothrow);
  if ( lpszVolumeMountPoint[0] != v27 )
    operator delete((void *)lpszVolumeMountPoint[0], (const struct std::nothrow_t *)&std::nothrow);
  return 0;
}

```

## disassembly

```asm
0x18002463c  push    rbp
0x18002463e  push    rbx
0x18002463f  push    rsi
0x180024640  push    rdi
0x180024641  push    r14
0x180024643  lea     rbp, [rsp-30h]
0x180024648  sub     rsp, 130h
0x18002464f  mov     rax, cs:__security_cookie
0x180024656  xor     rax, rsp
0x180024659  mov     [rbp+50h+var_30], rax
0x18002465d  lea     rax, [rsp+150h+var_E0]
0x180024662  xor     r14d, r14d
0x180024665  mov     [rsp+150h+lpszVolumeMountPoint], rax
0x18002466a  lea     rcx, [rbp+50h+var_C0]; this
0x18002466e  lea     rax, [rsp+150h+var_E0]
0x180024673  mov     [rsp+150h+var_E0], r14w
0x180024679  mov     [rsp+150h+var_E8], rax
0x18002467e  lea     rax, [rbp+50h+var_B0]
0x180024682  mov     [rbp+50h+var_C0], rax
0x180024686  lea     rax, [rbp+50h+var_B0]
0x18002468a  mov     [rbp+50h+var_B8], rax
0x18002468e  mov     [rbp+50h+var_B0], r14w
0x180024693  call    ?GetSystemDrivePath@Csl@@YAJAEAVPath@1@@Z; Csl::GetSystemDrivePath(Csl::Path &)
0x180024698  mov     ebx, eax
0x18002469a  test    eax, eax
0x18002469c  jns     short loc_1800246C2
0x18002469e  mov     rcx, [rbp+58h]; this
0x1800246a2  lea     r8, aOnecoreBaseGen_1; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x1800246a9  mov     r9d, eax; char *
0x1800246ac  mov     edx, 561h; void *
0x1800246b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800246b6  lea     rdi, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800246bd  jmp     loc_180024750
0x1800246c2  mov     r8, [rbp+50h+var_B8]
0x1800246c6  lea     rax, [rbp+50h+var_90]
0x1800246ca  mov     rdx, [rbp+50h+var_C0]
0x1800246ce  lea     rcx, [rbp+50h+var_A0]
0x1800246d2  mov     [rbp+50h+var_A0], rax
0x1800246d6  sub     r8, rdx
0x1800246d9  lea     rax, [rbp+50h+var_90]
0x1800246dd  sar     r8, 1
0x1800246e0  mov     [rbp+50h+var_98], rax
0x1800246e4  mov     [rbp+50h+var_90], r14w
0x1800246e9  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x1800246ee  test    al, al
0x1800246f0  jnz     short loc_1800246F9
0x1800246f2  mov     edx, 564h
0x1800246f7  jmp     short loc_18002471C
0x1800246f9  mov     r8d, 1
0x1800246ff  lea     rdx, asc_18003F43C; "\\"
0x180024706  lea     rcx, [rbp+50h+var_A0]
0x18002470a  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18002470f  test    al, al
0x180024711  jnz     loc_18002479B
0x180024717  mov     edx, 567h; void *
0x18002471c  mov     rcx, [rbp+58h]; this
0x180024720  lea     r8, aOnecoreBaseGen_1; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180024727  mov     ebx, 8007000Eh
0x18002472c  mov     r9d, ebx; char *
0x18002472f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024734  mov     rcx, [rbp+50h+var_A0]; void *
0x180024738  lea     rax, [rbp+50h+var_90]
0x18002473c  lea     rdi, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180024743  cmp     rcx, rax
0x180024746  jz      short loc_180024750
0x180024748  mov     rdx, rdi; struct std::nothrow_t *
0x18002474b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180024750  mov     rcx, [rbp+50h+var_C0]; void *
0x180024754  lea     rax, [rbp+50h+var_B0]
0x180024758  cmp     rcx, rax
0x18002475b  jz      short loc_180024765
0x18002475d  mov     rdx, rdi; struct std::nothrow_t *
0x180024760  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180024765  mov     rcx, [rbp+58h]; this
0x180024769  lea     r8, aOnecoreBaseGen_12; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180024770  mov     r9d, ebx; char *
0x180024773  mov     edx, 3AEh; void *
0x180024778  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002477d  mov     rcx, [rsp+150h+lpszVolumeMountPoint]; void *
0x180024782  lea     rax, [rsp+150h+var_E0]
0x180024787  cmp     rcx, rax
0x18002478a  jz      short loc_180024794
0x18002478c  mov     rdx, rdi; struct std::nothrow_t *
0x18002478f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180024794  mov     eax, ebx
0x180024796  jmp     loc_180024ADA
0x18002479b  lea     rdx, [rbp+50h+var_A0]
0x18002479f  lea     rcx, [rsp+150h+lpszVolumeMountPoint]
0x1800247a4  call    ??4?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::operator=(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&)
0x1800247a9  mov     rcx, [rbp+50h+var_A0]; void *
0x1800247ad  lea     rax, [rbp+50h+var_90]
0x1800247b1  lea     rdi, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800247b8  cmp     rcx, rax
0x1800247bb  jz      short loc_1800247C5
0x1800247bd  mov     rdx, rdi; struct std::nothrow_t *
0x1800247c0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800247c5  mov     rcx, [rbp+50h+var_C0]; void *
0x1800247c9  lea     rax, [rbp+50h+var_B0]
0x1800247cd  cmp     rcx, rax
0x1800247d0  jz      short loc_1800247DA
0x1800247d2  mov     rdx, rdi; struct std::nothrow_t *
0x1800247d5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800247da  lea     rax, [rsp+150h+var_100]
0x1800247df  mov     [rsp+150h+var_100], r14w
0x1800247e5  mov     [rsp+150h+lpszVolumeName], rax
0x1800247ea  lea     rcx, [rsp+150h+lpszVolumeName]
0x1800247ef  lea     rax, [rsp+150h+var_100]
0x1800247f4  mov     ebx, 32h ; '2'
0x1800247f9  mov     edx, ebx
0x1800247fb  mov     [rsp+150h+var_108], rax
0x180024800  call    ?resize@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_N_KG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::resize(unsigned __int64,ushort)
0x180024805  test    al, al
0x180024807  jnz     short loc_180024810
0x180024809  mov     edx, 3B2h
0x18002480e  jmp     short loc_18002488A
0x180024810  mov     rdx, [rsp+150h+lpszVolumeName]; lpszVolumeName
0x180024815  mov     r8d, ebx; cchBufferLength
0x180024818  mov     rcx, [rsp+150h+lpszVolumeMountPoint]; lpszVolumeMountPoint
0x18002481d  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180024824  nop     dword ptr [rax+rax+00h]
0x180024829  test    eax, eax
0x18002482b  jnz     short loc_180024864
0x18002482d  mov     edx, 3B6h; void *
0x180024832  mov     rcx, [rbp+58h]; this
0x180024836  lea     r8, aOnecoreBaseGen_12; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18002483d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180024842  mov     ebx, eax
0x180024844  mov     rcx, [rsp+150h+lpszVolumeName]; void *
0x180024849  lea     rax, [rsp+150h+var_100]
0x18002484e  cmp     rcx, rax
0x180024851  jz      loc_18002477D
0x180024857  mov     rdx, rdi; struct std::nothrow_t *
0x18002485a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002485f  jmp     loc_18002477D
0x180024864  mov     rax, [rsp+150h+lpszVolumeName]
0x180024869  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18002486d  inc     rdx
0x180024870  cmp     [rax+rdx*2], r14w
0x180024875  jnz     short loc_18002486D
0x180024877  lea     rcx, [rsp+150h+lpszVolumeName]
0x18002487c  call    ?resize@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_N_KG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::resize(unsigned __int64,ushort)
0x180024881  test    al, al
0x180024883  jnz     short loc_1800248A4
0x180024885  mov     edx, 3B9h; void *
0x18002488a  mov     rcx, [rbp+58h]; this
0x18002488e  lea     r8, aOnecoreBaseGen_12; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180024895  mov     ebx, 8007000Eh
0x18002489a  mov     r9d, ebx; char *
0x18002489d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800248a2  jmp     short loc_180024844
0x1800248a4  mov     rcx, [rsp+150h+var_108]
0x1800248a9  mov     r8d, 3; dwShareMode
0x1800248af  sub     rcx, 2
0x1800248b3  mov     [rsp+150h+hTemplateFile], r14; hTemplateFile
0x1800248b8  mov     [rsp+150h+var_108], rcx
0x1800248bd  xor     r9d, r9d; lpSecurityAttributes
0x1800248c0  mov     [rsp+150h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x1800248c8  mov     edx, 0C0000000h; dwDesiredAccess
0x1800248cd  mov     [rsp+150h+dwCreationDisposition], r8d; dwCreationDisposition
0x1800248d2  mov     [rcx], r14w
0x1800248d6  mov     rcx, [rsp+150h+lpszVolumeName]; lpFileName
0x1800248db  call    cs:__imp_CreateFileW
0x1800248e2  nop     dword ptr [rax+rax+00h]
0x1800248e7  mov     rbx, rax
0x1800248ea  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800248ee  jnz     short loc_1800248FA
0x1800248f0  mov     edx, 3C6h
0x1800248f5  jmp     loc_180024832
0x1800248fa  mov     [rsp+150h+lpOverlapped], r14; lpOverlapped
0x1800248ff  lea     rax, [rbp+50h+BytesReturned]
0x180024903  mov     [rsp+150h+hTemplateFile], rax; lpBytesReturned
0x180024908  xorps   xmm0, xmm0
0x18002490b  lea     rax, [rbp+50h+OutBuffer]
0x18002490f  mov     [rsp+150h+dwFlagsAndAttributes], 20h ; ' '; nOutBufferSize
0x180024917  xor     r9d, r9d; nInBufferSize
0x18002491a  mov     qword ptr [rsp+150h+dwCreationDisposition], rax; int
0x18002491f  xor     r8d, r8d; lpInBuffer
0x180024922  mov     [rbp+50h+BytesReturned], r14d
0x180024926  mov     edx, 560000h; dwIoControlCode
0x18002492b  mov     rcx, rbx; hDevice
0x18002492e  movups  [rbp+50h+OutBuffer], xmm0
0x180024932  movups  [rbp+50h+var_40], xmm0
0x180024936  call    cs:__imp_DeviceIoControl
0x18002493d  nop     dword ptr [rax+rax+00h]
0x180024942  test    eax, eax
0x180024944  jnz     short loc_1800249A6
0x180024946  mov     edx, 3D7h; void *
0x18002494b  mov     rcx, [rbp+58h]; this
0x18002494f  lea     r8, aOnecoreBaseGen_12; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180024956  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002495b  mov     esi, eax
0x18002495d  test    rbx, rbx
0x180024960  jz      short loc_180024971
0x180024962  mov     rcx, rbx; hObject
0x180024965  call    cs:__imp_CloseHandle
0x18002496c  nop     dword ptr [rax+rax+00h]
0x180024971  mov     rcx, [rsp+150h+lpszVolumeName]; void *
0x180024976  lea     rax, [rsp+150h+var_100]
0x18002497b  cmp     rcx, rax
0x18002497e  jz      short loc_180024988
0x180024980  mov     rdx, rdi; struct std::nothrow_t *
0x180024983  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180024988  mov     rcx, [rsp+150h+lpszVolumeMountPoint]; void *
0x18002498d  lea     rax, [rsp+150h+var_E0]
0x180024992  cmp     rcx, rax
0x180024995  jz      short loc_18002499F
0x180024997  mov     rdx, rdi; struct std::nothrow_t *
0x18002499a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002499f  mov     eax, esi
0x1800249a1  jmp     loc_180024ADA
0x1800249a6  mov     ecx, dword ptr [rbp+50h+OutBuffer+8]; this
0x1800249a9  lea     rdx, [rbp+50h+InBuffer]; unsigned int
0x1800249ad  mov     [rbp+50h+InBuffer], r14
0x1800249b1  call    ?ExpandDiskPartition@Csl@@YAJKAEA_K@Z; Csl::ExpandDiskPartition(ulong,unsigned __int64 &)
0x1800249b6  mov     esi, eax
0x1800249b8  test    eax, eax
0x1800249ba  jns     short loc_1800249D6
0x1800249bc  mov     rcx, [rbp+58h]; this
0x1800249c0  lea     r8, aOnecoreBaseGen_12; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x1800249c7  mov     r9d, eax; char *
0x1800249ca  mov     edx, 3DDh; void *
0x1800249cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800249d4  jmp     short loc_18002495D
0x1800249d6  xorps   xmm0, xmm0
0x1800249d9  mov     [rsp+150h+dwCreationDisposition], 7; int
0x1800249e1  mov     r9d, 20h ; ' '; Length
0x1800249e7  lea     r8, [rbp+50h+FsInformation]; FsInformation
0x1800249eb  lea     rdx, [rbp+50h+IoStatusBlock]; IoStatusBlock
0x1800249ef  mov     rcx, rbx; FileHandle
0x1800249f2  movups  [rbp+50h+FsInformation], xmm0
0x1800249f6  movups  [rbp+50h+var_60], xmm0
0x1800249fa  movups  xmmword ptr [rbp+50h+IoStatusBlock], xmm0
0x1800249fe  call    cs:__imp_NtQueryVolumeInformationFile
0x180024a05  nop     dword ptr [rax+rax+00h]
0x180024a0a  test    eax, eax
0x180024a0c  jns     short loc_180024A2B
0x180024a0e  mov     rcx, [rbp+58h]; this
0x180024a12  lea     r8, aOnecoreBaseGen_12; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180024a19  mov     r9d, eax; char *
0x180024a1c  mov     edx, 3E7h; void *
0x180024a21  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180024a26  jmp     loc_18002495B
0x180024a2b  mov     ecx, dword ptr [rbp+50h+var_60+8]
0x180024a2e  xor     edx, edx
0x180024a30  imul    ecx, dword ptr [rbp+50h+var_60+0Ch]
0x180024a34  mov     rax, [rbp+50h+InBuffer]
0x180024a38  div     rcx
0x180024a3b  mov     rcx, qword ptr [rbp+50h+FsInformation]
0x180024a3f  inc     rcx
0x180024a42  cmp     rax, rcx
0x180024a45  jl      short loc_180024A96
0x180024a47  mov     ecx, dword ptr [rbp+50h+var_60+8]
0x180024a4a  lea     r8, [rbp+50h+InBuffer]; lpInBuffer
0x180024a4e  imul    rcx, rax
0x180024a52  mov     [rsp+150h+lpOverlapped], r14; lpOverlapped
0x180024a57  lea     rax, [rbp+50h+BytesReturned]
0x180024a5b  mov     [rsp+150h+hTemplateFile], rax; lpBytesReturned
0x180024a60  mov     r9d, 8; nInBufferSize
0x180024a66  mov     [rbp+50h+InBuffer], rcx
0x180024a6a  mov     edx, 900F0h; dwIoControlCode
0x180024a6f  mov     rcx, rbx; hDevice
0x180024a72  mov     [rsp+150h+dwFlagsAndAttributes], r14d; nOutBufferSize
0x180024a77  mov     qword ptr [rsp+150h+dwCreationDisposition], r14; lpOutBuffer
0x180024a7c  call    cs:__imp_DeviceIoControl
0x180024a83  nop     dword ptr [rax+rax+00h]
0x180024a88  test    eax, eax
0x180024a8a  jnz     short loc_180024A96
0x180024a8c  mov     edx, 3FDh
0x180024a91  jmp     loc_18002494B
0x180024a96  test    rbx, rbx
0x180024a99  jz      short loc_180024AAA
0x180024a9b  mov     rcx, rbx; hObject
0x180024a9e  call    cs:__imp_CloseHandle
0x180024aa5  nop     dword ptr [rax+rax+00h]
0x180024aaa  mov     rcx, [rsp+150h+lpszVolumeName]; void *
0x180024aaf  lea     rax, [rsp+150h+var_100]
0x180024ab4  cmp     rcx, rax
0x180024ab7  jz      short loc_180024AC1
0x180024ab9  mov     rdx, rdi; struct std::nothrow_t *
0x180024abc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180024ac1  mov     rcx, [rsp+150h+lpszVolumeMountPoint]; void *
0x180024ac6  lea     rax, [rsp+150h+var_E0]
0x180024acb  cmp     rcx, rax
0x180024ace  jz      short loc_180024AD8
0x180024ad0  mov     rdx, rdi; struct std::nothrow_t *
0x180024ad3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180024ad8  xor     eax, eax
0x180024ada  mov     rcx, [rbp+50h+var_30]
0x180024ade  xor     rcx, rsp; StackCookie
0x180024ae1  call    __security_check_cookie
0x180024ae6  add     rsp, 130h
0x180024aed  pop     r14
0x180024aef  pop     rdi
0x180024af0  pop     rsi
0x180024af1  pop     rbx
0x180024af2  pop     rbp
0x180024af3  retn
```
