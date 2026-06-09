# DdcDrivesHelper::GetBitLockerInfoForVolume(ushort const *,VolInfo *)

- ea: `0x180021afc`
- end: `0x180021f04`
- name: `?GetBitLockerInfoForVolume@DdcDrivesHelper@@CAJPEBGPEAUVolInfo@@@Z`
- size: `1032`
- prototype: `__int64 __fastcall(LPCWSTR lpszVolumeMountPoint, struct VolInfo *)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180021f0c`

## callees

- `0x1800024c0`
- `0x180002fc0`
- `0x180003288`
- `0x1800050b8`
- `0x180020c20`
- `0x180020c44`
- `0x180021afc`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180021bd0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180021be3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180021bf8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180021c0b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180021c1e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180021bd0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180021be3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180021bf8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180021c0b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180021c1e`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180021b97`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180021b97`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180021c64`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180021c64`

## string_xrefs

- `0x180021c99`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcdriveshelper.cpp`
- `0x180021b90`: `fveapi.dll`
- `0x180021bc6`: `FveOpenVolumeW`
- `0x180021c82`: `CBR(GetVolumeNameForVolumeMountPointW(pathName, volumeName, sizeof(*__countof_helper(volumeName))))`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall DdcDrivesHelper::GetBitLockerInfoForVolume(LPCWSTR lpszVolumeMountPoint, struct VolInfo *a2)
{
  HMODULE LibraryW; // rax
  HMODULE v5; // rbx
  FARPROC ProcAddress; // r13
  FARPROC v8; // rdi
  FARPROC v9; // r15
  FARPROC v10; // rax
  unsigned int (__fastcall *v11)(_QWORD, _QWORD, _QWORD, _QWORD); // r14
  int v12; // edx
  int v13; // ebx
  const char *v14; // rcx
  int v15; // r8d
  _DWORD *v16; // rax
  _DWORD *v17; // rdi
  GUID v18; // xmm0
  char v19; // [rsp+20h] [rbp-E0h]
  const char *v20; // [rsp+28h] [rbp-D8h]
  __int64 v21; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
  void *v23; // [rsp+40h] [rbp-C0h] BYREF
  HMODULE v24; // [rsp+48h] [rbp-B8h] BYREF
  void (*v25)(void); // [rsp+50h] [rbp-B0h]
  _DWORD v26[3]; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v27; // [rsp+64h] [rbp-9Ch]
  _BYTE v28[28]; // [rsp+74h] [rbp-8Ch] BYREF
  int v29; // [rsp+90h] [rbp-70h] BYREF
  __int64 v30; // [rsp+94h] [rbp-6Ch]
  _DWORD v31[11]; // [rsp+9Ch] [rbp-64h] BYREF
  __int64 v32; // [rsp+C8h] [rbp-38h]
  WCHAR szVolumeName[264]; // [rsp+120h] [rbp+20h] BYREF

  v29 = 144;
  v30 = 10;
  memset_0(v31, 0, 0x84u);
  v21 = -1;
  v26[0] = 56;
  v26[1] = 1;
  v26[2] = 0x80000;
  v27 = 0;
  memset(v28, 0, sizeof(v28));
  v22 = 0;
  v23 = 0;
  LibraryW = LoadLibraryW(L"fveapi.dll");
  v5 = LibraryW;
  v24 = LibraryW;
  if ( !LibraryW )
  {
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v24);
    std::unique_ptr<_FVE_AUTH_INFORMATION>::~unique_ptr<_FVE_AUTH_INFORMATION>(&v23);
    return 0;
  }
  ProcAddress = GetProcAddress(LibraryW, "FveOpenVolumeW");
  v25 = (void (*)(void))GetProcAddress(v5, "FveCloseVolume");
  v8 = GetProcAddress(v5, "FveIsVolumeEncryptable");
  v9 = GetProcAddress(v5, "FveGetStatusW");
  v10 = GetProcAddress(v5, "FveGetAuthMethodInformation");
  v11 = (unsigned int (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))v10;
  if ( !ProcAddress || !v25 || !v8 || !v9 || !v10 )
  {
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v24);
    std::unique_ptr<_FVE_AUTH_INFORMATION>::~unique_ptr<_FVE_AUTH_INFORMATION>(&v23);
    return 2147500037LL;
  }
  if ( GetVolumeNameForVolumeMountPointW(lpszVolumeMountPoint, szVolumeName, 0x105u) )
  {
    v13 = ((__int64 (__fastcall *)(WCHAR *, _QWORD, __int64 *))ProcAddress)(szVolumeName, 0, &v21);
    if ( v13 < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
        goto LABEL_41;
      v20 = "CHR(hr)";
      v19 = 68;
      goto LABEL_16;
    }
    *((_DWORD *)a2 + 141) = ((int (__fastcall *)(__int64))v8)(v21) >= 0;
    *((_DWORD *)a2 + 140) = 0;
    v13 = ((__int64 (__fastcall *)(WCHAR *, int *))v9)(szVolumeName, &v29);
    if ( v13 < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
        goto LABEL_41;
      v20 = "CHR(hr)";
      v19 = 75;
      goto LABEL_16;
    }
    if ( (v31[0] & 1) != 0 )
    {
      if ( (v31[0] & 0x400) != 0 )
      {
        if ( (v31[0] & 4) == 0 )
        {
          if ( (v31[0] & 0x400) != 0 )
            *((_DWORD *)a2 + 140) = 3;
LABEL_28:
          if ( (v32 & 0x100) != 0 )
          {
            if ( v11(v21, v26, 56, &v22) != -2147024774 )
            {
              v13 = -2147467259;
              if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
                goto LABEL_41;
              v14 = "CBR(hr == HRESULT_FROM_WIN32(122L))";
              v20 = "CBR(hr == HRESULT_FROM_WIN32(122L))";
              v19 = 107;
              goto LABEL_11;
            }
            v16 = operator new[](v22, (const struct std::nothrow_t *)&std::nothrow);
            v17 = v16;
            v23 = v16;
            if ( !v16 )
            {
              v13 = -2147024882;
              if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
                goto LABEL_41;
              v20 = "CBR(authInfo != nullptr)";
              v19 = 110;
              goto LABEL_16;
            }
            *v16 = 56;
            v16[1] = 1;
            v16[2] = 0x80000;
            v13 = v11(v21, v16, v22, &v22);
            if ( v13 < 0 )
            {
              if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
                goto LABEL_41;
              v20 = "CHR(hr)";
              v19 = 117;
LABEL_16:
              v15 = v13;
              goto LABEL_12;
            }
            v18 = *(GUID *)(v17 + 10);
          }
          else
          {
            v18 = GUID_NULL;
          }
          *(GUID *)((char *)a2 + 568) = v18;
          goto LABEL_41;
        }
      }
      else if ( (v31[0] & 4) == 0 )
      {
        *((_DWORD *)a2 + 140) = 2;
        goto LABEL_28;
      }
    }
    *((_DWORD *)a2 + 140) = 1;
    goto LABEL_28;
  }
  v13 = -2147467259;
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
  {
    v14 = "CBR(GetVolumeNameForVolumeMountPointW(pathName, volumeName, sizeof(*__countof_helper(volumeName))))";
    v20 = "CBR(GetVolumeNameForVolumeMountPointW(pathName, volumeName, sizeof(*__countof_helper(volumeName))))";
    v19 = 65;
LABEL_11:
    v15 = -2147467259;
LABEL_12:
    McTemplateU0dsqs_EventWriteTransfer(
      (_DWORD)v14,
      v12,
      v15,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdriveshelper.cpp",
      v19,
      v20);
  }
LABEL_41:
  if ( v21 != -1 )
    v25();
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v24);
  std::unique_ptr<_FVE_AUTH_INFORMATION>::~unique_ptr<_FVE_AUTH_INFORMATION>(&v23);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180021afc  mov     [rsp-8+arg_10], rbx
0x180021b01  push    rbp
0x180021b02  push    rsi
0x180021b03  push    rdi
0x180021b04  push    r12
0x180021b06  push    r13
0x180021b08  push    r14
0x180021b0a  push    r15
0x180021b0c  lea     rbp, [rsp-240h]
0x180021b14  sub     rsp, 340h
0x180021b1b  mov     rax, cs:__security_cookie
0x180021b22  xor     rax, rsp
0x180021b25  mov     [rbp+270h+var_40], rax
0x180021b2c  mov     rsi, rdx
0x180021b2f  mov     r12, rcx
0x180021b32  mov     [rbp+270h+var_2E0], 90h
0x180021b39  mov     [rbp+270h+var_2DC], 0Ah
0x180021b41  xor     edx, edx; Val
0x180021b43  mov     r8d, 84h; Size
0x180021b49  lea     rcx, [rbp+270h+var_2D4]; void *
0x180021b4d  call    memset_0
0x180021b52  mov     [rsp+370h+var_340], 0FFFFFFFFFFFFFFFFh
0x180021b5b  mov     [rsp+370h+var_318], 38h ; '8'
0x180021b63  mov     [rsp+370h+var_314], 1
0x180021b6b  mov     [rsp+370h+var_310], 80000h
0x180021b73  xorps   xmm0, xmm0
0x180021b76  xor     eax, eax
0x180021b78  movups  [rsp+370h+var_30C], xmm0
0x180021b7d  movups  xmmword ptr [rsp+370h+var_2FC], xmm0
0x180021b82  movups  xmmword ptr [rbp+270h+var_2FC+0Ch], xmm0
0x180021b86  mov     [rsp+370h+var_338], rax
0x180021b8b  mov     [rsp+370h+var_330], rax
0x180021b90  lea     rcx, aFveapiDll; "fveapi.dll"
0x180021b97  call    cs:__imp_LoadLibraryW
0x180021b9d  mov     rbx, rax
0x180021ba0  mov     [rsp+370h+var_328], rax
0x180021ba5  test    rax, rax
0x180021ba8  jnz     short loc_180021BC6
0x180021baa  lea     rcx, [rsp+370h+var_328]
0x180021baf  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180021bb4  nop
0x180021bb5  lea     rcx, [rsp+370h+var_330]
0x180021bba  call    ??1?$unique_ptr@U_FVE_AUTH_INFORMATION@@U?$default_delete@U_FVE_AUTH_INFORMATION@@@std@@@std@@QEAA@XZ; std::unique_ptr<_FVE_AUTH_INFORMATION>::~unique_ptr<_FVE_AUTH_INFORMATION>(void)
0x180021bbf  xor     eax, eax
0x180021bc1  jmp     loc_180021EDA
0x180021bc6  lea     rdx, aFveopenvolumew; "FveOpenVolumeW"
0x180021bcd  mov     rcx, rbx; hModule
0x180021bd0  call    cs:__imp_GetProcAddress
0x180021bd6  mov     r13, rax
0x180021bd9  lea     rdx, aFveclosevolume; "FveCloseVolume"
0x180021be0  mov     rcx, rbx; hModule
0x180021be3  call    cs:__imp_GetProcAddress
0x180021be9  mov     [rsp+370h+var_320], rax
0x180021bee  lea     rdx, aFveisvolumeenc; "FveIsVolumeEncryptable"
0x180021bf5  mov     rcx, rbx; hModule
0x180021bf8  call    cs:__imp_GetProcAddress
0x180021bfe  mov     rdi, rax
0x180021c01  lea     rdx, aFvegetstatusw; "FveGetStatusW"
0x180021c08  mov     rcx, rbx; hModule
0x180021c0b  call    cs:__imp_GetProcAddress
0x180021c11  mov     r15, rax
0x180021c14  lea     rdx, aFvegetauthmeth; "FveGetAuthMethodInformation"
0x180021c1b  mov     rcx, rbx; hModule
0x180021c1e  call    cs:__imp_GetProcAddress
0x180021c24  mov     r14, rax
0x180021c27  test    r13, r13
0x180021c2a  jz      loc_180021EC0
0x180021c30  cmp     [rsp+370h+var_320], 0
0x180021c36  jz      loc_180021EC0
0x180021c3c  test    rdi, rdi
0x180021c3f  jz      loc_180021EC0
0x180021c45  test    r15, r15
0x180021c48  jz      loc_180021EC0
0x180021c4e  test    rax, rax
0x180021c51  jz      loc_180021EC0
0x180021c57  mov     r8d, 105h; cchBufferLength
0x180021c5d  lea     rdx, [rbp+270h+szVolumeName]; lpszVolumeName
0x180021c61  mov     rcx, r12; lpszVolumeMountPoint
0x180021c64  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180021c6a  test    eax, eax
0x180021c6c  jnz     short loc_180021CAA
0x180021c6e  mov     eax, 80004005h
0x180021c73  mov     ebx, eax
0x180021c75  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180021c7c  jz      loc_180021E91
0x180021c82  lea     rcx, aCbrGetvolumena; "CBR(GetVolumeNameForVolumeMountPointW(p"...
0x180021c89  mov     [rsp+370h+var_348], rcx
0x180021c8e  mov     dword ptr [rsp+370h+var_350], 141h
0x180021c96  mov     r8d, eax
0x180021c99  lea     r9, aOnecoreuapShel_5; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180021ca0  call    McTemplateU0dsqs_EventWriteTransfer
0x180021ca5  jmp     loc_180021E91
0x180021caa  lea     r8, [rsp+370h+var_340]
0x180021caf  xor     edx, edx
0x180021cb1  lea     rcx, [rbp+270h+szVolumeName]
0x180021cb5  mov     rax, r13
0x180021cb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021cbd  mov     ebx, eax
0x180021cbf  test    eax, eax
0x180021cc1  jns     short loc_180021CE9
0x180021cc3  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180021cca  jz      loc_180021E91
0x180021cd0  lea     rax, aChrHr; "CHR(hr)"
0x180021cd7  mov     [rsp+370h+var_348], rax
0x180021cdc  mov     dword ptr [rsp+370h+var_350], 144h
0x180021ce4  mov     r8d, ebx
0x180021ce7  jmp     short loc_180021C99
0x180021ce9  mov     rcx, [rsp+370h+var_340]
0x180021cee  mov     rax, rdi
0x180021cf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021cf6  not     eax
0x180021cf8  shr     eax, 1Fh
0x180021cfb  mov     [rsi+234h], eax
0x180021d01  mov     dword ptr [rsi+230h], 0
0x180021d0b  lea     rdx, [rbp+270h+var_2E0]
0x180021d0f  lea     rcx, [rbp+270h+szVolumeName]
0x180021d13  mov     rax, r15
0x180021d16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d1b  mov     ebx, eax
0x180021d1d  test    eax, eax
0x180021d1f  jns     short loc_180021D44
0x180021d21  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180021d28  jz      loc_180021E91
0x180021d2e  lea     rax, aChrHr; "CHR(hr)"
0x180021d35  mov     [rsp+370h+var_348], rax
0x180021d3a  mov     dword ptr [rsp+370h+var_350], 14Bh
0x180021d42  jmp     short loc_180021CE4
0x180021d44  mov     eax, [rbp+270h+var_2D4]
0x180021d47  mov     r15d, 1
0x180021d4d  test    r15b, al
0x180021d50  jz      short loc_180021D80
0x180021d52  mov     ecx, eax
0x180021d54  and     ecx, 400h
0x180021d5a  jnz     short loc_180021D6C
0x180021d5c  test    al, 4
0x180021d5e  jnz     short loc_180021D80
0x180021d60  mov     dword ptr [rsi+230h], 2
0x180021d6a  jmp     short loc_180021D87
0x180021d6c  test    al, 4
0x180021d6e  jnz     short loc_180021D80
0x180021d70  test    ecx, ecx
0x180021d72  jz      short loc_180021D87
0x180021d74  mov     dword ptr [rsi+230h], 3
0x180021d7e  jmp     short loc_180021D87
0x180021d80  mov     [rsi+230h], r15d
0x180021d87  test    [rbp+270h+var_2A8], 100h
0x180021d8f  jz      loc_180021E82
0x180021d95  lea     r9, [rsp+370h+var_338]
0x180021d9a  mov     ebx, 38h ; '8'
0x180021d9f  mov     r8d, ebx
0x180021da2  lea     rdx, [rsp+370h+var_318]
0x180021da7  mov     rcx, [rsp+370h+var_340]
0x180021dac  mov     rax, r14
0x180021daf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021db4  cmp     eax, 8007007Ah
0x180021db9  jz      short loc_180021DE8
0x180021dbb  mov     eax, 80004005h
0x180021dc0  mov     ebx, eax
0x180021dc2  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r15b
0x180021dc9  jz      loc_180021E91
0x180021dcf  lea     rcx, aCbrHrHresultFr; "CBR(hr == HRESULT_FROM_WIN32(122L))"
0x180021dd6  mov     [rsp+370h+var_348], rcx
0x180021ddb  mov     dword ptr [rsp+370h+var_350], 16Bh
0x180021de3  jmp     loc_180021C96
0x180021de8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180021def  mov     rcx, [rsp+370h+var_338]; unsigned __int64
0x180021df4  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180021df9  mov     rdi, rax
0x180021dfc  mov     [rsp+370h+var_330], rax
0x180021e01  test    rax, rax
0x180021e04  jnz     short loc_180021E2D
0x180021e06  mov     ebx, 8007000Eh
0x180021e0b  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r15b
0x180021e12  jz      short loc_180021E91
0x180021e14  lea     rax, aCbrAuthinfoNul; "CBR(authInfo != nullptr)"
0x180021e1b  mov     [rsp+370h+var_348], rax
0x180021e20  mov     dword ptr [rsp+370h+var_350], 16Eh
0x180021e28  jmp     loc_180021CE4
0x180021e2d  mov     [rax], ebx
0x180021e2f  mov     [rax+4], r15d
0x180021e33  mov     dword ptr [rax+8], 80000h
0x180021e3a  lea     r9, [rsp+370h+var_338]
0x180021e3f  mov     r8, [rsp+370h+var_338]
0x180021e44  mov     rdx, rdi
0x180021e47  mov     rcx, [rsp+370h+var_340]
0x180021e4c  mov     rax, r14
0x180021e4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021e54  mov     ebx, eax
0x180021e56  test    eax, eax
0x180021e58  jns     short loc_180021E7C
0x180021e5a  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r15b
0x180021e61  jz      short loc_180021E91
0x180021e63  lea     rax, aChrHr; "CHR(hr)"
0x180021e6a  mov     [rsp+370h+var_348], rax
0x180021e6f  mov     dword ptr [rsp+370h+var_350], 175h
0x180021e77  jmp     loc_180021CE4
0x180021e7c  movups  xmm0, xmmword ptr [rdi+28h]
0x180021e80  jmp     short loc_180021E89
0x180021e82  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180021e89  movdqu  xmmword ptr [rsi+238h], xmm0
0x180021e91  mov     rcx, [rsp+370h+var_340]
0x180021e96  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180021e9a  jz      short loc_180021EA7
0x180021e9c  mov     rax, [rsp+370h+var_320]
0x180021ea1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ea6  nop
0x180021ea7  lea     rcx, [rsp+370h+var_328]
0x180021eac  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180021eb1  nop
0x180021eb2  lea     rcx, [rsp+370h+var_330]
0x180021eb7  call    ??1?$unique_ptr@U_FVE_AUTH_INFORMATION@@U?$default_delete@U_FVE_AUTH_INFORMATION@@@std@@@std@@QEAA@XZ; std::unique_ptr<_FVE_AUTH_INFORMATION>::~unique_ptr<_FVE_AUTH_INFORMATION>(void)
0x180021ebc  mov     eax, ebx
0x180021ebe  jmp     short loc_180021EDA
0x180021ec0  lea     rcx, [rsp+370h+var_328]
0x180021ec5  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180021eca  nop
0x180021ecb  lea     rcx, [rsp+370h+var_330]
0x180021ed0  call    ??1?$unique_ptr@U_FVE_AUTH_INFORMATION@@U?$default_delete@U_FVE_AUTH_INFORMATION@@@std@@@std@@QEAA@XZ; std::unique_ptr<_FVE_AUTH_INFORMATION>::~unique_ptr<_FVE_AUTH_INFORMATION>(void)
0x180021ed5  mov     eax, 80004005h
0x180021eda  mov     rcx, [rbp+270h+var_40]
0x180021ee1  xor     rcx, rsp; StackCookie
0x180021ee4  call    __security_check_cookie
0x180021ee9  mov     rbx, [rsp+370h+arg_10]
0x180021ef1  add     rsp, 340h
0x180021ef8  pop     r15
0x180021efa  pop     r14
0x180021efc  pop     r13
0x180021efe  pop     r12
0x180021f00  pop     rdi
0x180021f01  pop     rsi
0x180021f02  pop     rbp
0x180021f03  retn
```
