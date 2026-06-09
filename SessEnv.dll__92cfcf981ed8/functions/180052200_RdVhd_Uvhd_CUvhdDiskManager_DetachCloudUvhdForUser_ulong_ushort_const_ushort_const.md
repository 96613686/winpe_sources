# RdVhd::Uvhd::CUvhdDiskManager::DetachCloudUvhdForUser(ulong,ushort const *,ushort const *)

- ea: `0x180052200`
- end: `0x1800526ac`
- name: `?DetachCloudUvhdForUser@CUvhdDiskManager@Uvhd@RdVhd@@UEBAJKPEBG0@Z`
- size: `1196`
- prototype: `__int64 __fastcall(RdVhd::Uvhd::CUvhdDiskManager *__hidden this, unsigned int, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting`

## callees

- `0x180004db0`
- `0x1800141e8`
- `0x180019b38`
- `0x18001a280`
- `0x18001a8d0`
- `0x18001ad5c`
- `0x180031b5c`
- `0x1800488e4`
- `0x180048ab0`
- `0x180048b28`
- `0x180052200`
- `0x180054eb0`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800524af`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180052599`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800524af`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180052599`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180052668`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180052668`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800524bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800525a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800524bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800525a7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180052477`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180052477`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800522a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800522ee`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18005265f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800522a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800522ee`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18005265f`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180052485`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180052485`

## string_xrefs

- `0x1800522d1`: `szUserSID`
- `0x18005236a`: `IProfileHelper::GetProfileDiskName failed for user SID [%s].`
- `0x1800523e1`: `DetachCloudUvhdForUser() was not given a disk number and there is no disk name in user profile. Cannot detach. SID [%s].`
- `0x1800524a8`: `UnmountXDriveByName`
- `0x1800524d5`: `[%s] Failed to find unmount function call.`
- `0x1800525bf`: `[%s] Failed to find unmount function call.`
- `0x18005253e`: `[%s] Failed to unmount uservhd (xdrive) user.`
- `0x18005260c`: `[%s] Failed to unmount uservhd (xdrive) user.`
- `0x180052592`: `UnmountXDriveByDiskNumber`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RdVhd::Uvhd::CUvhdDiskManager::DetachCloudUvhdForUser(
        RdVhd::Uvhd::CUvhdDiskManager *this,
        unsigned int a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  __int64 v7; // rbx
  int v8; // ebx
  int v9; // r9d
  int v10; // eax
  RdVhd::Uvhd::CUvhdDiskManager *v11; // rcx
  int v12; // edx
  HMODULE LibraryW; // rsi
  FARPROC ProcAddress; // r14
  signed int LastError; // eax
  int v16; // r9d
  RdVhd::Uvhd::CUvhdDiskManager *v17; // rcx
  int v18; // edx
  __int64 v19; // rax
  int v20; // eax
  FARPROC v21; // r14
  signed int v22; // eax
  int v23; // eax
  DWORD pcbData[2]; // [rsp+40h] [rbp-C0h] BYREF
  const int *v26; // [rsp+48h] [rbp-B8h] BYREF
  int v27; // [rsp+50h] [rbp-B0h]
  __int64 v28; // [rsp+54h] [rbp-ACh]
  int v29; // [rsp+5Ch] [rbp-A4h]
  __int64 v30; // [rsp+60h] [rbp-A0h]
  int v31; // [rsp+68h] [rbp-98h]
  void **v32; // [rsp+70h] [rbp-90h] BYREF
  int v33; // [rsp+78h] [rbp-88h]
  __int64 v34; // [rsp+7Ch] [rbp-84h]
  int v35; // [rsp+84h] [rbp-7Ch]
  __int64 v36; // [rsp+88h] [rbp-78h]
  int v37; // [rsp+90h] [rbp-70h]
  WCHAR LibFileName[264]; // [rsp+A0h] [rbp-60h] BYREF

  v34 = 128;
  v36 = 0;
  v32 = &CPathString::`vftable';
  v35 = 0;
  v26 = &CBaseStringT<unsigned short>::`vftable';
  v37 = 0x8000000;
  v33 = 0;
  *(_QWORD *)pcbData = 0;
  v28 = 128;
  v30 = 0;
  v29 = 0;
  v31 = 0x8000000;
  v27 = 0;
  GetTickCount();
  if ( !a3 )
  {
    if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 223, WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids, L"szUserSID");
    }
    LODWORD(v7) = -2147024809;
    goto LABEL_7;
  }
  v8 = 0;
  if ( a2 != -1 )
  {
LABEL_26:
    memset_0(LibFileName, 0, 0x208u);
    pcbData[0] = 520;
    LibraryW = 0;
    if ( !RegGetValueW(
            HKEY_LOCAL_MACHINE,
            L"SYSTEM\\CurrentControlSet\\Control\\Terminal Server\\CloudSettings",
            L"RdvCloud",
            2u,
            0,
            LibFileName,
            pcbData) )
      LibraryW = LoadLibraryW(LibFileName);
    if ( !LibraryW )
    {
      LODWORD(v7) = -2147418113;
      goto LABEL_7;
    }
    if ( v8 )
    {
      ProcAddress = GetProcAddress(LibraryW, "UnmountXDriveByName");
      if ( ProcAddress )
        goto LABEL_39;
      LastError = GetLastError();
      LODWORD(v7) = LastError;
      if ( LastError > 0 )
        LODWORD(v7) = (unsigned __int16)LastError | 0x80070000;
      _TraceNrmRdvVmEx(L"UVHD", (unsigned int)v7, L"[%s] Failed to find unmount function call.");
      if ( (int)v7 >= 0 )
      {
LABEL_39:
        v19 = CBaseStringT<unsigned short>::PContents(&v26);
        LODWORD(v7) = ((__int64 (__fastcall *)(__int64, const unsigned __int16 *))ProcAddress)(v19, a4);
        _TraceNrmRdvVmEx(L"UVHD", (unsigned int)v7, L"[%s] Failed to unmount uservhd (xdrive) user.");
        if ( v20 >= 0 )
          goto LABEL_58;
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_58;
        }
        v18 = 228;
      }
      else
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_58;
        }
        v18 = 227;
      }
    }
    else
    {
      v21 = GetProcAddress(LibraryW, "UnmountXDriveByDiskNumber");
      if ( v21 )
        goto LABEL_52;
      v22 = GetLastError();
      LODWORD(v7) = v22;
      if ( v22 > 0 )
        LODWORD(v7) = (unsigned __int16)v22 | 0x80070000;
      _TraceNrmRdvVmEx(L"UVHD", (unsigned int)v7, L"[%s] Failed to find unmount function call.");
      if ( (int)v7 >= 0 )
      {
LABEL_52:
        LODWORD(v7) = ((__int64 (__fastcall *)(_QWORD))v21)(a2);
        _TraceNrmRdvVmEx(L"UVHD", (unsigned int)v7, L"[%s] Failed to unmount uservhd (xdrive) user.");
        if ( v23 >= 0 )
          goto LABEL_58;
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_58;
        }
        v18 = 230;
      }
      else
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_58;
        }
        v18 = 229;
      }
    }
    WPP_SF_Sd(*((_QWORD *)v17 + 2), v18, (unsigned int)WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids, v16, v7);
LABEL_58:
    GetTickCount();
    FreeLibrary(LibraryW);
    goto LABEL_59;
  }
  LODWORD(v7) = RdVhd::Uvhd::CProfileHelper::CreateInstance((struct RdVhd::Uvhd::IDirectoryHelper ***)pcbData);
  if ( (int)v7 < 0 )
  {
    if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        224,
        WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids,
        (unsigned int)v7);
    }
    goto LABEL_7;
  }
  v7 = (*(unsigned int (__fastcall **)(_QWORD, const unsigned __int16 *, const int **))(**(_QWORD **)pcbData + 80LL))(
         *(_QWORD *)pcbData,
         a3,
         &v26);
  _TraceNrmRdvVmEx(L"UVHD", v7, L"IProfileHelper::GetProfileDiskName failed for user SID [%s].");
  if ( v10 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    v12 = 225;
    goto LABEL_19;
  }
  if ( !(unsigned int)CBaseStringT<unsigned short>::IsEmpty(&v26) )
  {
    v8 = 1;
    goto LABEL_26;
  }
  LODWORD(v7) = -2147467259;
  _TraceNrmRdvVmEx(
    L"UVHD",
    2147500037LL,
    L"DetachCloudUvhdForUser() was not given a disk number and there is no disk name in user profile. Cannot detach. SID [%s].");
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    goto LABEL_7;
  }
  v12 = 226;
LABEL_19:
  WPP_SF_Sd(*((_QWORD *)v11 + 2), v12, (unsigned int)WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids, v9, v7);
LABEL_7:
  GetTickCount();
LABEL_59:
  CPathString::~CPathString((CPathString *)&v26);
  operator delete(0);
  CPathString::~CPathString((CPathString *)&v32);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180052200  push    rbp
0x180052202  push    rbx
0x180052203  push    rsi
0x180052204  push    rdi
0x180052205  push    r12
0x180052207  push    r14
0x180052209  push    r15
0x18005220b  lea     rbp, [rsp-1C0h]
0x180052213  sub     rsp, 2C0h
0x18005221a  mov     rax, cs:__security_cookie
0x180052221  xor     rax, rsp
0x180052224  mov     [rbp+1F0h+var_40], rax
0x18005222b  mov     ecx, 8000000h
0x180052230  mov     [rsp+2F0h+var_274], 80h
0x180052239  lea     rax, ??_7CPathString@@6B@; const CPathString::`vftable'
0x180052240  mov     [rbp+1F0h+var_268], 0
0x180052248  mov     [rsp+2F0h+var_280], rax
0x18005224d  mov     r12, r9
0x180052250  lea     rax, ??_7?$CBaseStringT@G@@6B@; const CBaseStringT<ushort>::`vftable'
0x180052257  mov     [rbp+1F0h+var_26C], 0
0x18005225e  mov     [rsp+2F0h+var_2A8], rax
0x180052263  mov     rdi, r8
0x180052266  mov     r15d, edx
0x180052269  mov     [rbp+1F0h+var_260], ecx
0x18005226c  mov     [rsp+2F0h+var_278], 0
0x180052274  mov     qword ptr [rsp+2F0h+var_2B0], 0
0x18005227d  mov     [rsp+2F0h+var_29C], 80h
0x180052286  mov     [rsp+2F0h+var_290], 0
0x18005228f  mov     [rsp+2F0h+var_294], 0
0x180052297  mov     [rsp+2F0h+var_288], ecx
0x18005229b  mov     [rsp+2F0h+var_2A0], 0
0x1800522a3  call    cs:__imp_GetTickCount
0x1800522a9  test    rdi, rdi
0x1800522ac  jnz     short loc_1800522F9
0x1800522ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800522b5  lea     rax, WPP_GLOBAL_Control
0x1800522bc  cmp     rcx, rax
0x1800522bf  jz      short loc_1800522E9
0x1800522c1  test    byte ptr [rcx+1Ch], 4
0x1800522c5  jz      short loc_1800522E9
0x1800522c7  cmp     byte ptr [rcx+19h], 2
0x1800522cb  jb      short loc_1800522E9
0x1800522cd  mov     rcx, [rcx+10h]
0x1800522d1  lea     r9, aSzusersid_0; "szUserSID"
0x1800522d8  mov     edx, 0DFh
0x1800522dd  lea     r8, WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids
0x1800522e4  call    WPP_SF_S
0x1800522e9  mov     ebx, 80070057h
0x1800522ee  call    cs:__imp_GetTickCount
0x1800522f4  jmp     loc_18005266E
0x1800522f9  xor     ebx, ebx
0x1800522fb  cmp     r15d, 0FFFFFFFFh
0x1800522ff  jnz     loc_18005242D
0x180052305  lea     rcx, [rsp+2F0h+var_2B0]; struct RdVhd::Uvhd::IProfileHelper **
0x18005230a  call    ?CreateInstance@CProfileHelper@Uvhd@RdVhd@@SAJPEAPEAVIProfileHelper@23@@Z; RdVhd::Uvhd::CProfileHelper::CreateInstance(RdVhd::Uvhd::IProfileHelper * *)
0x18005230f  mov     ebx, eax
0x180052311  test    eax, eax
0x180052313  jns     short loc_18005234E
0x180052315  mov     rcx, cs:WPP_GLOBAL_Control
0x18005231c  lea     rax, WPP_GLOBAL_Control
0x180052323  cmp     rcx, rax
0x180052326  jz      short loc_1800522EE
0x180052328  test    byte ptr [rcx+1Ch], 4
0x18005232c  jz      short loc_1800522EE
0x18005232e  cmp     byte ptr [rcx+19h], 2
0x180052332  jb      short loc_1800522EE
0x180052334  mov     rcx, [rcx+10h]
0x180052338  lea     r8, WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids
0x18005233f  mov     edx, 0E0h
0x180052344  mov     r9d, ebx
0x180052347  call    WPP_SF_d
0x18005234c  jmp     short loc_1800522EE
0x18005234e  mov     rcx, qword ptr [rsp+2F0h+var_2B0]
0x180052353  lea     r8, [rsp+2F0h+var_2A8]
0x180052358  mov     rdx, rdi
0x18005235b  mov     rax, [rcx]
0x18005235e  mov     rax, [rax+50h]
0x180052362  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052367  mov     r9, rdi
0x18005236a  lea     r8, aIprofilehelper_0; "IProfileHelper::GetProfileDiskName fail"...
0x180052371  mov     edx, eax; int
0x180052373  lea     rcx, aUvhd; "UVHD"
0x18005237a  mov     ebx, eax
0x18005237c  call    ?_TraceNrmRdvVmEx@@YAXPEBGJ0ZZ; _TraceNrmRdvVmEx(ushort const *,long,ushort const *,...)
0x180052381  test    eax, eax
0x180052383  jns     short loc_1800523CE
0x180052385  mov     rcx, cs:WPP_GLOBAL_Control
0x18005238c  lea     rax, WPP_GLOBAL_Control
0x180052393  cmp     rcx, rax
0x180052396  jz      loc_1800522EE
0x18005239c  test    byte ptr [rcx+1Ch], 4
0x1800523a0  jz      loc_1800522EE
0x1800523a6  cmp     byte ptr [rcx+19h], 2
0x1800523aa  jb      loc_1800522EE
0x1800523b0  mov     edx, 0E1h
0x1800523b5  mov     rcx, [rcx+10h]
0x1800523b9  lea     r8, WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids
0x1800523c0  mov     dword ptr [rsp+2F0h+pdwType], ebx
0x1800523c4  call    WPP_SF_Sd
0x1800523c9  jmp     loc_1800522EE
0x1800523ce  lea     rcx, [rsp+2F0h+var_2A8]
0x1800523d3  call    ?IsEmpty@?$CBaseStringT@G@@QEBAHXZ; CBaseStringT<ushort>::IsEmpty(void)
0x1800523d8  test    eax, eax
0x1800523da  jz      short loc_180052428
0x1800523dc  mov     ebx, 80004005h
0x1800523e1  lea     r8, aDetachclouduvh; "DetachCloudUvhdForUser() was not given "...
0x1800523e8  mov     edx, ebx; int
0x1800523ea  lea     rcx, aUvhd; "UVHD"
0x1800523f1  call    ?_TraceNrmRdvVmEx@@YAXPEBGJ0ZZ; _TraceNrmRdvVmEx(ushort const *,long,ushort const *,...)
0x1800523f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800523fd  lea     rax, WPP_GLOBAL_Control
0x180052404  cmp     rcx, rax
0x180052407  jz      loc_1800522EE
0x18005240d  test    byte ptr [rcx+1Ch], 4
0x180052411  jz      loc_1800522EE
0x180052417  cmp     byte ptr [rcx+19h], 2
0x18005241b  jb      loc_1800522EE
0x180052421  mov     edx, 0E2h
0x180052426  jmp     short loc_1800523B5
0x180052428  mov     ebx, 1
0x18005242d  mov     esi, 208h
0x180052432  lea     rcx, [rbp+1F0h+LibFileName]; void *
0x180052436  mov     r8d, esi; Size
0x180052439  xor     edx, edx; Val
0x18005243b  call    memset_0
0x180052440  mov     [rsp+2F0h+var_2B0], esi
0x180052444  lea     rax, [rsp+2F0h+var_2B0]
0x180052449  mov     [rsp+2F0h+pcbData], rax; pcbData
0x18005244e  lea     r8, aRdvcloud; "RdvCloud"
0x180052455  xor     esi, esi
0x180052457  lea     rax, [rbp+1F0h+LibFileName]
0x18005245b  mov     [rsp+2F0h+pvData], rax; pvData
0x180052460  lea     rdx, aSystemCurrentc_12; "SYSTEM\\CurrentControlSet\\Control\\Ter"...
0x180052467  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18005246e  mov     [rsp+2F0h+pdwType], rsi; pdwType
0x180052473  lea     r9d, [rsi+2]; dwFlags
0x180052477  call    cs:__imp_RegGetValueW
0x18005247d  test    eax, eax
0x18005247f  jnz     short loc_18005248E
0x180052481  lea     rcx, [rbp+1F0h+LibFileName]; lpLibFileName
0x180052485  call    cs:__imp_LoadLibraryW
0x18005248b  mov     rsi, rax
0x18005248e  test    rsi, rsi
0x180052491  jnz     short loc_18005249D
0x180052493  mov     ebx, 8000FFFFh
0x180052498  jmp     loc_1800522EE
0x18005249d  mov     rcx, rsi; hModule
0x1800524a0  test    ebx, ebx
0x1800524a2  jz      loc_180052592
0x1800524a8  lea     rdx, aUnmountxdriveb_0; "UnmountXDriveByName"
0x1800524af  call    cs:__imp_GetProcAddress
0x1800524b5  mov     r14, rax
0x1800524b8  test    rax, rax
0x1800524bb  jnz     short loc_180052523
0x1800524bd  call    cs:__imp_GetLastError
0x1800524c3  mov     ebx, eax
0x1800524c5  test    eax, eax
0x1800524c7  jle     short loc_1800524D2
0x1800524c9  movzx   ebx, ax
0x1800524cc  or      ebx, 80070000h
0x1800524d2  mov     r9, rdi
0x1800524d5  lea     r8, aSFailedToFindU; "[%s] Failed to find unmount function ca"...
0x1800524dc  mov     edx, ebx; int
0x1800524de  lea     rcx, aUvhd; "UVHD"
0x1800524e5  call    ?_TraceNrmRdvVmEx@@YAXPEBGJ0ZZ; _TraceNrmRdvVmEx(ushort const *,long,ushort const *,...)
0x1800524ea  test    ebx, ebx
0x1800524ec  jns     short loc_180052523
0x1800524ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800524f5  lea     rax, WPP_GLOBAL_Control
0x1800524fc  cmp     rcx, rax
0x1800524ff  jz      loc_18005265F
0x180052505  test    byte ptr [rcx+1Ch], 4
0x180052509  jz      loc_18005265F
0x18005250f  cmp     byte ptr [rcx+19h], 2
0x180052513  jb      loc_18005265F
0x180052519  mov     edx, 0E3h
0x18005251e  jmp     loc_18005264B
0x180052523  lea     rcx, [rsp+2F0h+var_2A8]
0x180052528  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x18005252d  mov     rcx, rax
0x180052530  mov     rdx, r12
0x180052533  mov     rax, r14
0x180052536  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005253b  mov     r9, rdi
0x18005253e  lea     r8, aSFailedToUnmou; "[%s] Failed to unmount uservhd (xdrive)"...
0x180052545  mov     edx, eax; int
0x180052547  lea     rcx, aUvhd; "UVHD"
0x18005254e  mov     ebx, eax
0x180052550  call    ?_TraceNrmRdvVmEx@@YAXPEBGJ0ZZ; _TraceNrmRdvVmEx(ushort const *,long,ushort const *,...)
0x180052555  test    eax, eax
0x180052557  jns     loc_18005265F
0x18005255d  mov     rcx, cs:WPP_GLOBAL_Control
0x180052564  lea     rax, WPP_GLOBAL_Control
0x18005256b  cmp     rcx, rax
0x18005256e  jz      loc_18005265F
0x180052574  test    byte ptr [rcx+1Ch], 4
0x180052578  jz      loc_18005265F
0x18005257e  cmp     byte ptr [rcx+19h], 2
0x180052582  jb      loc_18005265F
0x180052588  mov     edx, 0E4h
0x18005258d  jmp     loc_18005264B
0x180052592  lea     rdx, aUnmountxdriveb; "UnmountXDriveByDiskNumber"
0x180052599  call    cs:__imp_GetProcAddress
0x18005259f  mov     r14, rax
0x1800525a2  test    rax, rax
0x1800525a5  jnz     short loc_1800525FE
0x1800525a7  call    cs:__imp_GetLastError
0x1800525ad  mov     ebx, eax
0x1800525af  test    eax, eax
0x1800525b1  jle     short loc_1800525BC
0x1800525b3  movzx   ebx, ax
0x1800525b6  or      ebx, 80070000h
0x1800525bc  mov     r9, rdi
0x1800525bf  lea     r8, aSFailedToFindU; "[%s] Failed to find unmount function ca"...
0x1800525c6  mov     edx, ebx; int
0x1800525c8  lea     rcx, aUvhd; "UVHD"
0x1800525cf  call    ?_TraceNrmRdvVmEx@@YAXPEBGJ0ZZ; _TraceNrmRdvVmEx(ushort const *,long,ushort const *,...)
0x1800525d4  test    ebx, ebx
0x1800525d6  jns     short loc_1800525FE
0x1800525d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800525df  lea     rax, WPP_GLOBAL_Control
0x1800525e6  cmp     rcx, rax
0x1800525e9  jz      short loc_18005265F
0x1800525eb  test    byte ptr [rcx+1Ch], 4
0x1800525ef  jz      short loc_18005265F
0x1800525f1  cmp     byte ptr [rcx+19h], 2
0x1800525f5  jb      short loc_18005265F
0x1800525f7  mov     edx, 0E5h
0x1800525fc  jmp     short loc_18005264B
0x1800525fe  mov     ecx, r15d
0x180052601  mov     rax, r14
0x180052604  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052609  mov     r9, rdi
0x18005260c  lea     r8, aSFailedToUnmou; "[%s] Failed to unmount uservhd (xdrive)"...
0x180052613  mov     edx, eax; int
0x180052615  lea     rcx, aUvhd; "UVHD"
0x18005261c  mov     ebx, eax
0x18005261e  call    ?_TraceNrmRdvVmEx@@YAXPEBGJ0ZZ; _TraceNrmRdvVmEx(ushort const *,long,ushort const *,...)
0x180052623  test    eax, eax
0x180052625  jns     short loc_18005265F
0x180052627  mov     rcx, cs:WPP_GLOBAL_Control
0x18005262e  lea     rax, WPP_GLOBAL_Control
0x180052635  cmp     rcx, rax
0x180052638  jz      short loc_18005265F
0x18005263a  test    byte ptr [rcx+1Ch], 4
0x18005263e  jz      short loc_18005265F
0x180052640  cmp     byte ptr [rcx+19h], 2
0x180052644  jb      short loc_18005265F
0x180052646  mov     edx, 0E6h
0x18005264b  mov     rcx, [rcx+10h]
0x18005264f  lea     r8, WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids
0x180052656  mov     dword ptr [rsp+2F0h+pdwType], ebx
0x18005265a  call    WPP_SF_Sd
0x18005265f  call    cs:__imp_GetTickCount
0x180052665  mov     rcx, rsi; hLibModule
0x180052668  call    cs:__imp_FreeLibrary
0x18005266e  lea     rcx, [rsp+2F0h+var_2A8]; this
0x180052673  call    ??1CPathString@@QEAA@XZ; CPathString::~CPathString(void)
0x180052678  xor     ecx, ecx; Block
0x18005267a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005267f  lea     rcx, [rsp+2F0h+var_280]; this
0x180052684  call    ??1CPathString@@QEAA@XZ; CPathString::~CPathString(void)
0x180052689  mov     eax, ebx
0x18005268b  mov     rcx, [rbp+1F0h+var_40]
0x180052692  xor     rcx, rsp; StackCookie
0x180052695  call    __security_check_cookie
0x18005269a  add     rsp, 2C0h
0x1800526a1  pop     r15
0x1800526a3  pop     r14
0x1800526a5  pop     r12
0x1800526a7  pop     rdi
0x1800526a8  pop     rsi
0x1800526a9  pop     rbx
0x1800526aa  pop     rbp
0x1800526ab  retn
```
