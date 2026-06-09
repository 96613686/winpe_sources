# GetCurrentContextParameters(AppInfo *,ushort * *,IMrtResourceManager * *,ushort * *,ushort * *)

- ea: `0x1802f41b0`
- end: `0x1802f45aa`
- name: `?GetCurrentContextParameters@@YAJPEAVAppInfo@@PEAPEAGPEAPEAUIMrtResourceManager@@11@Z`
- size: `1018`
- prototype: `__int64 __fastcall(struct AppInfo *, unsigned __int16 **, struct IMrtResourceManager **, unsigned __int16 **, DWORD dwProcessId)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1802f3df0`
- `0x1802f46e4`

## callees

- `0x180009dd0`
- `0x18000e4b4`
- `0x18002fc18`
- `0x1800308d0`
- `0x180041f54`
- `0x180090bc8`
- `0x1800a0f20`
- `0x1800b2c68`
- `0x18012b5d8`
- `0x1802742e4`
- `0x1802f41b0`
- `0x1803855a4`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1802f426f`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1802f426f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1802f43fc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1802f4437`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1802f43fc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1802f4437`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x1802f4258`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x1802f4258`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackagePath` at `0x1802f4367`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackagePath` at `0x1802f43ae`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackagePath` at `0x1802f4367`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackagePath` at `0x1802f43ae`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageId` at `0x1802f42d8`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageId` at `0x1802f4337`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageId` at `0x1802f42d8`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageId` at `0x1802f4337`

## pseudocode

```c
__int64 __fastcall GetCurrentContextParameters(
        struct AppInfo *a1,
        unsigned __int16 **a2,
        struct IMrtResourceManager **a3,
        unsigned __int16 **a4,
        PWSTR *dwProcessId)
{
  PWSTR *v8; // r14
  PWSTR v9; // r15
  CDefaultUILangugageCache *v10; // rcx
  int CachedDefaultUILanguage; // edi
  HWND v12; // rcx
  HANDLE v13; // rsi
  unsigned __int16 **v14; // r8
  LONG PackageId; // eax
  void *v16; // rcx
  BYTE *v17; // rbx
  LONG v18; // eax
  LONG PackagePath; // eax
  int v20; // eax
  LONG v21; // eax
  HRESULT Instance; // eax
  unsigned __int16 *v23; // rsi
  struct IMrtResourceManager *v24; // rbx
  struct IPropertyStore *v25; // r8
  unsigned __int16 *v26; // rax
  BYTE *buffer; // [rsp+30h] [rbp-51h] BYREF
  HANDLE v29; // [rsp+38h] [rbp-49h] BYREF
  unsigned __int16 *v30; // [rsp+40h] [rbp-41h] BYREF
  __int64 v31; // [rsp+48h] [rbp-39h]
  __int64 v32; // [rsp+50h] [rbp-31h]
  unsigned __int16 *v33; // [rsp+58h] [rbp-29h] BYREF
  __int64 v34; // [rsp+60h] [rbp-21h]
  __int64 v35; // [rsp+68h] [rbp-19h]
  PWSTR path; // [rsp+70h] [rbp-11h] BYREF
  __int64 v37; // [rsp+78h] [rbp-9h]
  __int64 v38; // [rsp+80h] [rbp-1h]
  __int16 v39; // [rsp+88h] [rbp+7h] BYREF
  PWSTR v40; // [rsp+90h] [rbp+Fh]
  BYTE *pathLength; // [rsp+F0h] [rbp+6Fh] BYREF
  TileUtils *ppv; // [rsp+F8h] [rbp+77h] BYREF

  *a2 = 0;
  *a3 = 0;
  if ( a4 )
    *a4 = 0;
  v8 = dwProcessId;
  if ( dwProcessId )
    *dwProcessId = 0;
  v33 = 0;
  v34 = 0;
  v9 = 0;
  v35 = 0;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  path = 0;
  v37 = 0;
  v38 = 0;
  ppv = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v33);
  v34 = -1;
  v35 = -1;
  v29 = 0;
  CachedDefaultUILanguage = CDefaultUILangugageCache::GetCachedDefaultUILanguage(v10, &v33);
  if ( CachedDefaultUILanguage >= 0 )
  {
    v12 = (HWND)*((_QWORD *)a1 + 3);
    LODWORD(dwProcessId) = 0;
    GetWindowThreadProcessId(v12, (LPDWORD)&dwProcessId);
    v13 = OpenProcess(0x1000u, 0, (DWORD)dwProcessId);
    CAutoHandle<void *>::~CAutoHandle<void *>(&v29);
    v29 = v13;
    if ( v13 || (CachedDefaultUILanguage = ResultFromKnownLastError(), CachedDefaultUILanguage >= 0) )
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v30);
      v31 = -1;
      v32 = -1;
      CachedDefaultUILanguage = CallerIdentity::GetPackageFullNameFromProcess(v13, &v30, v14);
      if ( CachedDefaultUILanguage >= 0 )
      {
        LODWORD(dwProcessId) = 0;
        PackageId = GetPackageId(v13, (UINT32 *)&dwProcessId, 0);
        CachedDefaultUILanguage = PackageId;
        if ( PackageId > 0 )
          CachedDefaultUILanguage = (unsigned __int16)PackageId | 0x80070000;
        if ( CachedDefaultUILanguage == -2147024774 )
        {
          if ( !(_DWORD)dwProcessId )
            goto LABEL_39;
          buffer = 0;
          CachedDefaultUILanguage = CTCoAllocPolicy::Alloc(v16, 1u, (unsigned int)dwProcessId, (void **)&buffer);
          if ( CachedDefaultUILanguage >= 0 )
          {
            v17 = buffer;
            v18 = GetPackageId(v13, (UINT32 *)&dwProcessId, buffer);
            CachedDefaultUILanguage = v18;
            if ( v18 > 0 )
              CachedDefaultUILanguage = (unsigned __int16)v18 | 0x80070000;
            if ( CachedDefaultUILanguage >= 0 )
            {
              LODWORD(pathLength) = 0;
              PackagePath = GetPackagePath((const PACKAGE_ID *)v17, 0, (UINT32 *)&pathLength, 0);
              CachedDefaultUILanguage = PackagePath;
              if ( PackagePath > 0 )
                CachedDefaultUILanguage = (unsigned __int16)PackagePath | 0x80070000;
              if ( CachedDefaultUILanguage == -2147024774 )
              {
                if ( (_DWORD)pathLength )
                {
                  v20 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
                          &path,
                          (unsigned int)pathLength);
                  v9 = path;
                  CachedDefaultUILanguage = v20;
                  if ( v20 >= 0 )
                  {
                    v21 = GetPackagePath((const PACKAGE_ID *)v17, 0, (UINT32 *)&pathLength, path);
                    CachedDefaultUILanguage = v21;
                    if ( v21 > 0 )
                      CachedDefaultUILanguage = (unsigned __int16)v21 | 0x80070000;
                  }
                }
              }
            }
          }
          CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&buffer);
        }
        if ( CachedDefaultUILanguage >= 0 )
        {
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppv);
          CachedDefaultUILanguage = CoCreateInstance(
                                      &GUID_dbce7e40_7345_439d_b12c_114a11819a09,
                                      0,
                                      1u,
                                      &GUID_130a2f65_2be7_4309_9a58_a9052ff2b61c,
                                      (LPVOID *)&ppv);
          if ( CachedDefaultUILanguage >= 0 )
          {
            pathLength = 0;
            Instance = CoCreateInstance(
                         &CLSID_InMemoryPropertyStore,
                         0,
                         3u,
                         &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
                         (LPVOID *)&pathLength);
            v23 = v30;
            CachedDefaultUILanguage = Instance;
            if ( Instance >= 0 )
            {
              v24 = (struct IMrtResourceManager *)pathLength;
              buffer = pathLength;
              if ( pathLength )
                (*(void (__fastcall **)(BYTE *))(*(_QWORD *)pathLength + 8LL))(pathLength);
              v40 = v9;
              v39 = 31;
              CachedDefaultUILanguage = (*(__int64 (__fastcall **)(struct IMrtResourceManager *, __int128 *, __int16 *))(*(_QWORD *)v24 + 48LL))(
                                          v24,
                                          &PKEY_AppUserModel_PackageInstallPath,
                                          &v39);
              if ( CachedDefaultUILanguage >= 0 )
              {
                v40 = v23;
                v39 = 31;
                CachedDefaultUILanguage = (*(__int64 (__fastcall **)(struct IMrtResourceManager *, __int128 *, __int16 *))(*(_QWORD *)v24 + 48LL))(
                                            v24,
                                            &PKEY_AppUserModel_PackageFullName,
                                            &v39);
                if ( CachedDefaultUILanguage >= 0 )
                  CachedDefaultUILanguage = TileUtils::InitializeMRTResourceManager(ppv, v24, v25);
              }
              DirectUI::DuiPVLTrigger::~DuiPVLTrigger((DirectUI::DuiPVLTrigger *)&buffer);
            }
            Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&pathLength);
            if ( CachedDefaultUILanguage >= 0 )
            {
              v26 = v33;
              v33 = 0;
              v35 = 0;
              v34 = 0;
              *a2 = v26;
              *a3 = ppv;
              ppv = 0;
              if ( a4 )
              {
                v30 = 0;
                v32 = 0;
                v31 = 0;
                *a4 = v23;
              }
              if ( v8 )
              {
                path = 0;
                v38 = 0;
                v37 = 0;
                *v8 = v9;
              }
            }
          }
        }
      }
    }
  }
LABEL_39:
  CAutoHandle<void *>::~CAutoHandle<void *>(&v29);
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppv);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&path);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v30);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v33);
  return (unsigned int)CachedDefaultUILanguage;
}

```

## disassembly

```asm
0x1802f41b0  mov     [rsp-8+arg_0], rbx
0x1802f41b5  mov     [rsp-8+arg_8], rdx
0x1802f41ba  push    rbp
0x1802f41bb  push    rsi
0x1802f41bc  push    rdi
0x1802f41bd  push    r12
0x1802f41bf  push    r13
0x1802f41c1  push    r14
0x1802f41c3  push    r15
0x1802f41c5  lea     rbp, [rsp-1Fh]
0x1802f41ca  sub     rsp, 0A0h
0x1802f41d1  xor     esi, esi
0x1802f41d3  mov     r12, r9
0x1802f41d6  mov     [rdx], rsi
0x1802f41d9  mov     r13, r8
0x1802f41dc  mov     [r8], rsi
0x1802f41df  mov     rbx, rcx
0x1802f41e2  test    r9, r9
0x1802f41e5  jz      short loc_1802F41EA
0x1802f41e7  mov     [r9], rsi
0x1802f41ea  mov     r14, [rbp+4Fh+dwProcessId]
0x1802f41ee  test    r14, r14
0x1802f41f1  jz      short loc_1802F41F6
0x1802f41f3  mov     [r14], rsi
0x1802f41f6  lea     rcx, [rbp+4Fh+var_78]
0x1802f41fa  mov     [rbp+4Fh+var_78], rsi
0x1802f41fe  mov     [rbp+4Fh+var_70], rsi
0x1802f4202  mov     r15, rsi
0x1802f4205  mov     [rbp+4Fh+var_68], rsi
0x1802f4209  mov     [rbp+4Fh+var_90], rsi
0x1802f420d  mov     [rbp+4Fh+var_88], rsi
0x1802f4211  mov     [rbp+4Fh+var_80], rsi
0x1802f4215  mov     [rbp+4Fh+path], rsi
0x1802f4219  mov     [rbp+4Fh+var_58], rsi
0x1802f421d  mov     [rbp+4Fh+var_50], rsi
0x1802f4221  mov     [rbp+4Fh+arg_18], rsi
0x1802f4225  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1802f422a  or      rax, 0FFFFFFFFFFFFFFFFh
0x1802f422e  lea     rdx, [rbp+4Fh+var_78]; unsigned __int16 **
0x1802f4232  mov     [rbp+4Fh+var_70], rax
0x1802f4236  mov     [rbp+4Fh+var_68], rax
0x1802f423a  call    ?GetCachedDefaultUILanguage@CDefaultUILangugageCache@@QEAAJPEAPEAG@Z; CDefaultUILangugageCache::GetCachedDefaultUILanguage(ushort * *)
0x1802f423f  mov     [rbp+4Fh+var_98], rsi
0x1802f4243  mov     edi, eax
0x1802f4245  test    eax, eax
0x1802f4247  js      loc_1802F455F
0x1802f424d  mov     rcx, [rbx+18h]; hWnd
0x1802f4251  lea     rdx, [rbp+4Fh+dwProcessId]; lpdwProcessId
0x1802f4255  mov     dword ptr [rbp+4Fh+dwProcessId], esi
0x1802f4258  call    cs:__imp_GetWindowThreadProcessId
0x1802f425f  nop     dword ptr [rax+rax+00h]
0x1802f4264  mov     r8d, dword ptr [rbp+4Fh+dwProcessId]; dwProcessId
0x1802f4268  xor     edx, edx; bInheritHandle
0x1802f426a  mov     ecx, 1000h; dwDesiredAccess
0x1802f426f  call    cs:__imp_OpenProcess
0x1802f4276  nop     dword ptr [rax+rax+00h]
0x1802f427b  lea     rcx, [rbp+4Fh+var_98]
0x1802f427f  mov     rsi, rax
0x1802f4282  call    ??1?$CAutoHandle@PEAX@@QEAA@XZ; CAutoHandle<void *>::~CAutoHandle<void *>(void)
0x1802f4287  mov     [rbp+4Fh+var_98], rsi
0x1802f428b  test    rsi, rsi
0x1802f428e  jnz     short loc_1802F429F
0x1802f4290  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1802f4295  mov     edi, eax
0x1802f4297  test    eax, eax
0x1802f4299  js      loc_1802F455F
0x1802f429f  lea     rcx, [rbp+4Fh+var_90]
0x1802f42a3  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1802f42a8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1802f42ac  lea     rdx, [rbp+4Fh+var_90]; void *
0x1802f42b0  mov     rcx, rsi; hProcess
0x1802f42b3  mov     [rbp+4Fh+var_88], rax
0x1802f42b7  mov     [rbp+4Fh+var_80], rax
0x1802f42bb  call    ?GetPackageFullNameFromProcess@CallerIdentity@@YAJPEAXPEAPEAG@Z; CallerIdentity::GetPackageFullNameFromProcess(void *,ushort * *)
0x1802f42c0  mov     edi, eax
0x1802f42c2  test    eax, eax
0x1802f42c4  js      loc_1802F455F
0x1802f42ca  xor     r8d, r8d; buffer
0x1802f42cd  mov     dword ptr [rbp+4Fh+dwProcessId], r15d
0x1802f42d1  lea     rdx, [rbp+4Fh+dwProcessId]; bufferLength
0x1802f42d5  mov     rcx, rsi; hProcess
0x1802f42d8  call    cs:__imp_GetPackageId
0x1802f42df  nop     dword ptr [rax+rax+00h]
0x1802f42e4  mov     edi, eax
0x1802f42e6  test    eax, eax
0x1802f42e8  jle     short loc_1802F42F3
0x1802f42ea  movzx   edi, ax
0x1802f42ed  or      edi, 80070000h
0x1802f42f3  cmp     edi, 8007007Ah
0x1802f42f9  jnz     loc_1802F43CE
0x1802f42ff  mov     eax, dword ptr [rbp+4Fh+dwProcessId]
0x1802f4302  test    eax, eax
0x1802f4304  jz      loc_1802F455F
0x1802f430a  mov     r8d, eax; unsigned __int64
0x1802f430d  mov     [rbp+4Fh+buffer], r15
0x1802f4311  lea     r9, [rbp+4Fh+buffer]; void **
0x1802f4315  mov     edx, 1; unsigned int
0x1802f431a  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1802f431f  mov     edi, eax
0x1802f4321  test    eax, eax
0x1802f4323  js      loc_1802F43C5
0x1802f4329  mov     rbx, [rbp+4Fh+buffer]
0x1802f432d  lea     rdx, [rbp+4Fh+dwProcessId]; bufferLength
0x1802f4331  mov     r8, rbx; buffer
0x1802f4334  mov     rcx, rsi; hProcess
0x1802f4337  call    cs:__imp_GetPackageId
0x1802f433e  nop     dword ptr [rax+rax+00h]
0x1802f4343  mov     edi, eax
0x1802f4345  mov     esi, 80070000h
0x1802f434a  test    eax, eax
0x1802f434c  jle     short loc_1802F4353
0x1802f434e  movzx   edi, ax
0x1802f4351  or      edi, esi
0x1802f4353  test    edi, edi
0x1802f4355  js      short loc_1802F43C5
0x1802f4357  xor     r9d, r9d; path
0x1802f435a  mov     dword ptr [rbp+4Fh+pathLength], r15d
0x1802f435e  lea     r8, [rbp+4Fh+pathLength]; pathLength
0x1802f4362  xor     edx, edx; reserved
0x1802f4364  mov     rcx, rbx; packageId
0x1802f4367  call    cs:__imp_GetPackagePath
0x1802f436e  nop     dword ptr [rax+rax+00h]
0x1802f4373  mov     edi, eax
0x1802f4375  test    eax, eax
0x1802f4377  jle     short loc_1802F437E
0x1802f4379  movzx   edi, ax
0x1802f437c  or      edi, esi
0x1802f437e  cmp     edi, 8007007Ah
0x1802f4384  jnz     short loc_1802F43C5
0x1802f4386  mov     eax, dword ptr [rbp+4Fh+pathLength]
0x1802f4389  test    eax, eax
0x1802f438b  jz      short loc_1802F43C5
0x1802f438d  mov     edx, eax
0x1802f438f  lea     rcx, [rbp+4Fh+path]
0x1802f4393  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x1802f4398  mov     r15, [rbp+4Fh+path]
0x1802f439c  mov     edi, eax
0x1802f439e  test    eax, eax
0x1802f43a0  js      short loc_1802F43C5
0x1802f43a2  mov     r9, r15; path
0x1802f43a5  lea     r8, [rbp+4Fh+pathLength]; pathLength
0x1802f43a9  xor     edx, edx; reserved
0x1802f43ab  mov     rcx, rbx; packageId
0x1802f43ae  call    cs:__imp_GetPackagePath
0x1802f43b5  nop     dword ptr [rax+rax+00h]
0x1802f43ba  mov     edi, eax
0x1802f43bc  test    eax, eax
0x1802f43be  jle     short loc_1802F43C5
0x1802f43c0  movzx   edi, ax
0x1802f43c3  or      edi, esi
0x1802f43c5  lea     rcx, [rbp+4Fh+buffer]
0x1802f43c9  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x1802f43ce  test    edi, edi
0x1802f43d0  js      loc_1802F455F
0x1802f43d6  lea     rcx, [rbp+4Fh+arg_18]
0x1802f43da  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1802f43df  xor     edx, edx; pUnkOuter
0x1802f43e1  lea     rax, [rbp+4Fh+arg_18]
0x1802f43e5  lea     r9, _GUID_130a2f65_2be7_4309_9a58_a9052ff2b61c; riid
0x1802f43ec  mov     [rsp+0D0h+ppv], rax; ppv
0x1802f43f1  lea     rcx, _GUID_dbce7e40_7345_439d_b12c_114a11819a09; rclsid
0x1802f43f8  lea     r8d, [rdx+1]; dwClsContext
0x1802f43fc  call    cs:__imp_CoCreateInstance
0x1802f4403  nop     dword ptr [rax+rax+00h]
0x1802f4408  mov     edi, eax
0x1802f440a  test    eax, eax
0x1802f440c  js      loc_1802F455F
0x1802f4412  xor     edx, edx; pUnkOuter
0x1802f4414  mov     [rbp+4Fh+pathLength], 0
0x1802f441c  lea     rax, [rbp+4Fh+pathLength]
0x1802f4420  lea     r9, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x1802f4427  mov     [rsp+0D0h+ppv], rax; ppv
0x1802f442c  lea     rcx, CLSID_InMemoryPropertyStore; rclsid
0x1802f4433  lea     r8d, [rdx+3]; dwClsContext
0x1802f4437  call    cs:__imp_CoCreateInstance
0x1802f443e  nop     dword ptr [rax+rax+00h]
0x1802f4443  mov     rsi, [rbp+4Fh+var_90]
0x1802f4447  mov     edi, eax
0x1802f4449  test    eax, eax
0x1802f444b  js      loc_1802F44DE
0x1802f4451  mov     rbx, [rbp+4Fh+pathLength]
0x1802f4455  mov     [rbp+4Fh+buffer], rbx
0x1802f4459  test    rbx, rbx
0x1802f445c  jz      short loc_1802F446D
0x1802f445e  mov     rax, [rbx]
0x1802f4461  mov     rcx, rbx
0x1802f4464  mov     rax, [rax+8]
0x1802f4468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802f446d  mov     eax, 1Fh
0x1802f4472  mov     [rbp+4Fh+var_40], r15
0x1802f4476  mov     [rbp+4Fh+var_48], ax
0x1802f447a  lea     r8, [rbp+4Fh+var_48]
0x1802f447e  mov     rax, [rbx]
0x1802f4481  lea     rdx, PKEY_AppUserModel_PackageInstallPath
0x1802f4488  mov     rcx, rbx
0x1802f448b  mov     rax, [rax+30h]
0x1802f448f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802f4494  mov     edi, eax
0x1802f4496  test    eax, eax
0x1802f4498  js      short loc_1802F44D5
0x1802f449a  mov     eax, 1Fh
0x1802f449f  mov     [rbp+4Fh+var_40], rsi
0x1802f44a3  mov     [rbp+4Fh+var_48], ax
0x1802f44a7  lea     r8, [rbp+4Fh+var_48]
0x1802f44ab  mov     rax, [rbx]
0x1802f44ae  lea     rdx, PKEY_AppUserModel_PackageFullName
0x1802f44b5  mov     rcx, rbx
0x1802f44b8  mov     rax, [rax+30h]
0x1802f44bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802f44c1  mov     edi, eax
0x1802f44c3  test    eax, eax
0x1802f44c5  js      short loc_1802F44D5
0x1802f44c7  mov     rcx, [rbp+4Fh+arg_18]; this
0x1802f44cb  mov     rdx, rbx; struct IMrtResourceManager *
0x1802f44ce  call    ?InitializeMRTResourceManager@TileUtils@@YAJPEAUIMrtResourceManager@@PEAUIPropertyStore@@@Z; TileUtils::InitializeMRTResourceManager(IMrtResourceManager *,IPropertyStore *)
0x1802f44d3  mov     edi, eax
0x1802f44d5  lea     rcx, [rbp+4Fh+buffer]; this
0x1802f44d9  call    ??1DuiPVLTrigger@DirectUI@@QEAA@XZ; DirectUI::DuiPVLTrigger::~DuiPVLTrigger(void)
0x1802f44de  lea     rcx, [rbp+4Fh+pathLength]
0x1802f44e2  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1802f44e7  test    edi, edi
0x1802f44e9  js      short loc_1802F455F
0x1802f44eb  mov     rax, [rbp+4Fh+var_78]
0x1802f44ef  mov     rcx, [rbp+4Fh+arg_8]
0x1802f44f3  mov     [rbp+4Fh+var_78], 0
0x1802f44fb  mov     [rbp+4Fh+var_68], 0
0x1802f4503  mov     [rbp+4Fh+var_70], 0
0x1802f450b  mov     [rcx], rax
0x1802f450e  mov     rax, [rbp+4Fh+arg_18]
0x1802f4512  mov     [r13+0], rax
0x1802f4516  mov     [rbp+4Fh+arg_18], 0
0x1802f451e  test    r12, r12
0x1802f4521  jz      short loc_1802F453F
0x1802f4523  mov     [rbp+4Fh+var_90], 0
0x1802f452b  mov     [rbp+4Fh+var_80], 0
0x1802f4533  mov     [rbp+4Fh+var_88], 0
0x1802f453b  mov     [r12], rsi
0x1802f453f  test    r14, r14
0x1802f4542  jz      short loc_1802F455F
0x1802f4544  mov     [rbp+4Fh+path], 0
0x1802f454c  mov     [rbp+4Fh+var_50], 0
0x1802f4554  mov     [rbp+4Fh+var_58], 0
0x1802f455c  mov     [r14], r15
0x1802f455f  lea     rcx, [rbp+4Fh+var_98]
0x1802f4563  call    ??1?$CAutoHandle@PEAX@@QEAA@XZ; CAutoHandle<void *>::~CAutoHandle<void *>(void)
0x1802f4568  lea     rcx, [rbp+4Fh+arg_18]
0x1802f456c  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1802f4571  lea     rcx, [rbp+4Fh+path]
0x1802f4575  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1802f457a  lea     rcx, [rbp+4Fh+var_90]
0x1802f457e  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1802f4583  lea     rcx, [rbp+4Fh+var_78]
0x1802f4587  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1802f458c  mov     rbx, [rsp+0D0h+arg_0]
0x1802f4594  mov     eax, edi
0x1802f4596  add     rsp, 0A0h
0x1802f459d  pop     r15
0x1802f459f  pop     r14
0x1802f45a1  pop     r13
0x1802f45a3  pop     r12
0x1802f45a5  pop     rdi
0x1802f45a6  pop     rsi
0x1802f45a7  pop     rbp
0x1802f45a8  retn
```
