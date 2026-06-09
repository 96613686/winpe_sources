# CDeploymentSessionWrapper::Download(ushort const *,ushort const *,ushort const *,IDeploymentSessionHelper *,int,ushort * *)

- ea: `0x1802970bc`
- end: `0x180297859`
- name: `?Download@CDeploymentSessionWrapper@@QEAAJPEBG00PEAVIDeploymentSessionHelper@@HPEAPEAG@Z`
- size: `1949`
- prototype: `__int64 __fastcall(CDeploymentSessionWrapper *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct IDeploymentSessionHelper *, int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `18`
- tags: `reparse_path, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180297860`

## callees

- `0x180012fe4`
- `0x18003f44c`
- `0x18003f950`
- `0x1800d986c`
- `0x1800eb920`
- `0x1800ec920`
- `0x1801f15e4`
- `0x1801f17f8`
- `0x180296168`
- `0x180297084`
- `0x1802970bc`
- `0x180298470`
- `0x1802989d8`
- `0x180299100`
- `0x18029a260`
- `0x18029a67c`
- `0x18029acd0`
- `0x1802d5010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1802974f1`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1802974f1`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18029749f`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18029749f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18029722a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802974c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180297505`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18029722a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802974c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180297505`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180297316`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180297316`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1802972c5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1802972c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180297328`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180297328`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18029721a`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18029721a`

## string_xrefs

- `0x180297651`: `ActionList.xml`
- `0x18029736c`: `UpdateAgent.dll`
- `0x1802974e2`: `CreateOfflineDeploymentSession`
- `0x18029730f`: `AlternateServiceStackDLLPath`
- `0x1802972b7`: `SOFTWARE\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test`
- `0x18029757b`: `DeploymentSessionWrapper: Sandbox path [%s]`
- `0x180297489`: `DeploymentSessionWrapper: Loading Update Agent from [%s]`
- `0x180297458`: `DeploymentSessionWrapper: UpdateAgent.dll signature is not trusted.`
- `0x18029767d`: `DeploymentSessionWrapper: ActionList path: [%s]`

## pseudocode

```c
__int64 __fastcall CDeploymentSessionWrapper::Download(
        CDeploymentSessionWrapper *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        struct IDeploymentSessionHelper *a5,
        int a6,
        unsigned __int16 **a7)
{
  __int64 v11; // r9
  __int64 v12; // rdx
  unsigned int v13; // ebx
  __int64 v14; // rcx
  int v15; // eax
  const WCHAR *v16; // rsi
  DWORD LastError; // eax
  LSTATUS v18; // ebx
  const WCHAR *v19; // rbx
  int FinalPath; // eax
  const unsigned __int16 *v21; // r14
  HMODULE Library; // rbx
  DWORD v23; // eax
  FARPROC ProcAddress; // rbx
  DWORD v25; // eax
  __int64 v26; // rcx
  struct IDeploymentSessionHelper *v27; // r12
  unsigned __int16 *v28; // r13
  int v29; // r14d
  int v30; // eax
  int v32; // [rsp+50h] [rbp-B0h] BYREF
  int v33; // [rsp+54h] [rbp-ACh] BYREF
  unsigned __int16 *v34; // [rsp+58h] [rbp-A8h] BYREF
  HMODULE v35; // [rsp+60h] [rbp-A0h] BYREF
  LPCWSTR lpPathName; // [rsp+68h] [rbp-98h] BYREF
  struct IDeploymentSessionHelper *v37; // [rsp+70h] [rbp-90h]
  unsigned __int16 *v38; // [rsp+78h] [rbp-88h]
  unsigned __int16 **v39; // [rsp+80h] [rbp-80h]
  HKEY hKey[2]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v41; // [rsp+A0h] [rbp-60h]
  __int128 v42; // [rsp+B0h] [rbp-50h]
  __int128 v43; // [rsp+C0h] [rbp-40h]
  __int64 v44; // [rsp+D0h] [rbp-30h]
  DWORD Type; // [rsp+D8h] [rbp-28h] BYREF
  LPCWSTR lpLibFileName; // [rsp+E0h] [rbp-20h] BYREF
  unsigned int v47; // [rsp+E8h] [rbp-18h] BYREF
  DWORD cbData[2]; // [rsp+F0h] [rbp-10h] BYREF
  struct IDeploymentDownloadRequest *v49; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v50; // [rsp+100h] [rbp+0h] BYREF
  __int64 v51; // [rsp+108h] [rbp+8h]
  BYTE Data[1024]; // [rsp+110h] [rbp+10h] BYREF

  v37 = a5;
  lpPathName = 0;
  v39 = a7;
  lpLibFileName = 0;
  v35 = 0;
  v51 = 0;
  v44 = 0;
  v49 = 0;
  v50 = 0;
  v47 = 0;
  Type = 0;
  v32 = 0;
  v33 = 0;
  v38 = 0;
  v34 = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  if ( !a2 )
  {
    v11 = 106;
LABEL_3:
    v12 = 2147942487LL;
    v13 = -2147024809;
    goto LABEL_4;
  }
  if ( !a3 )
  {
    v11 = 107;
    goto LABEL_3;
  }
  if ( !a5 )
  {
    v11 = 108;
    goto LABEL_3;
  }
  if ( !a7 )
  {
    v11 = 109;
    goto LABEL_3;
  }
  v15 = CMiscHelpersT<CEmptyType>::DirectoryExists(a3, &Type);
  v13 = v15;
  if ( v15 < 0 )
  {
    v11 = 113;
LABEL_14:
    v12 = (unsigned int)v15;
    goto LABEL_4;
  }
  if ( Type )
  {
    v15 = CMiscHelpersT<CEmptyType>::CombinePath(a3, L"metadata", 0, &lpPathName);
    v13 = v15;
    if ( v15 < 0 )
    {
      v11 = 118;
      goto LABEL_14;
    }
    v16 = lpPathName;
    v15 = CMiscHelpersT<CEmptyType>::DirectoryExists(lpPathName, &Type);
    v13 = v15;
    if ( v15 < 0 )
    {
      v11 = 119;
      goto LABEL_14;
    }
    if ( !Type && !CreateDirectoryW(v16, 0) )
    {
      LastError = GetLastError();
      v15 = SErrorConverter::C_LR2HR(LastError);
      v13 = v15;
      v11 = 122;
      goto LABEL_14;
    }
    v15 = (**(__int64 (__fastcall ***)(struct IDeploymentSessionHelper *, const WCHAR *))a5)(a5, v16);
    v13 = v15;
    if ( v15 < 0 )
    {
      v11 = 127;
      goto LABEL_14;
    }
    v15 = (*(__int64 (__fastcall **)(struct IDeploymentSessionHelper *, const WCHAR *))(*(_QWORD *)a5 + 8LL))(a5, v16);
    v13 = v15;
    if ( v15 < 0 )
    {
      v11 = 129;
      goto LABEL_14;
    }
    SH<unsigned short *,SH_SSTRING>::Reset(&lpLibFileName);
    if ( !a4 )
    {
      hKey[0] = 0;
      if ( !RegOpenKeyExW(
              HKEY_LOCAL_MACHINE,
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test",
              0,
              0x20019u,
              hKey) )
      {
        Type = 0;
        memset_0(Data, 0, sizeof(Data));
        cbData[0] = 1024;
        v18 = RegQueryValueExW(hKey[0], L"AlternateServiceStackDLLPath", 0, &Type, Data, cbData);
        RegCloseKey(hKey[0]);
        if ( !v18 && Type == 1 )
        {
          v15 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::Create(Data);
          v13 = v15;
          if ( v15 < 0 )
          {
            v11 = 151;
            goto LABEL_14;
          }
        }
      }
    }
    v19 = lpLibFileName;
    if ( !lpLibFileName )
    {
      v15 = CMiscHelpersT<CEmptyType>::CombinePath(v16, L"UpdateAgent.dll", 0, &lpLibFileName);
      v13 = v15;
      if ( v15 < 0 )
      {
        v11 = 160;
        goto LABEL_14;
      }
      v19 = lpLibFileName;
    }
    lpLibFileName = 0;
    *(_QWORD *)cbData = 0;
    SH<unsigned short *,SH_SSTRING>::Reset(cbData);
    *(_QWORD *)cbData = v19;
    FinalPath = CMiscHelpersT<CEmptyType>::GetFinalPath(v19);
    v13 = FinalPath;
    if ( FinalPath < 0 )
    {
      CFCLogLiteT<CEmptyType>::LogError(
        *(_QWORD *)this,
        (unsigned int)FinalPath,
        L"CDeploymentSessionWrapper::Download",
        167);
      SH<unsigned short *,SH_SSTRING>::Reset(cbData);
      goto LABEL_96;
    }
    SH<unsigned short *,SH_SSTRING>::Reset(cbData);
    v21 = lpLibFileName;
    v15 = CMiscHelpersT<CEmptyType>::FileExists(lpLibFileName, &v32);
    v13 = v15;
    if ( v15 < 0 )
    {
      v11 = 169;
      goto LABEL_14;
    }
    if ( v32 )
    {
      if ( a4 )
        goto LABEL_106;
      v15 = VerifyFileSignature(v21, &v33);
      v13 = v15;
      if ( v15 < 0 )
      {
        v11 = 176;
        goto LABEL_14;
      }
      if ( v33 )
      {
LABEL_106:
        if ( *(_QWORD *)this )
          CFCLogLiteT<CEmptyType>::LogFormat(
            *(_QWORD *)this,
            2,
            L"DeploymentSessionWrapper: Loading Update Agent from [%s]",
            v21);
        Library = LoadLibraryExW(v21, 0, 0);
        SH<HINSTANCE__ *,SH_HMODULE>::Reset(&v35);
        if ( Library )
        {
          v35 = Library;
          ProcAddress = GetProcAddress(Library, "CreateOfflineDeploymentSession");
          if ( ProcAddress )
          {
            v26 = *(_QWORD *)this;
            v44 = 0;
            v41 = (unsigned __int64)a2;
            v42 = 0;
            v43 = 0;
            if ( v26 )
              CFCLogLiteT<CEmptyType>::LogFormat(
                v26,
                2,
                L"DeploymentSessionWrapper: Creating Deployment Session object");
            if ( *(_QWORD *)this )
              CFCLogLiteT<CEmptyType>::LogFormat(
                *(_QWORD *)this,
                2,
                L"DeploymentSessionWrapper: Session Version [%d]",
                1);
            if ( *(_QWORD *)this )
              CFCLogLiteT<CEmptyType>::LogFormat(*(_QWORD *)this, 2, L"DeploymentSessionWrapper: Sandbox path [%s]", a3);
            if ( *(_QWORD *)this )
              CFCLogLiteT<CEmptyType>::LogFormat(
                *(_QWORD *)this,
                2,
                L"DeploymentSessionWrapper: Offline windir [%s]",
                a4);
            if ( *(_QWORD *)this )
              CFCLogLiteT<CEmptyType>::LogFormat(*(_QWORD *)this, 2, L"DeploymentSessionWrapper: Info2version [%d]", 2);
            if ( *(_QWORD *)this )
              CFCLogLiteT<CEmptyType>::LogFormat(
                *(_QWORD *)this,
                2,
                L"DeploymentSessionWrapper: Session data [%s]",
                (_QWORD)v41);
            *(GUID *)hKey = GUID_NULL;
            v15 = ((__int64 (__fastcall *)(__int64, const unsigned __int16 *, const unsigned __int16 *))ProcAddress)(
                    1,
                    a3,
                    a4);
            v13 = v15;
            if ( v15 >= 0 )
            {
              v27 = v37;
              v28 = v38;
              while ( 2 )
              {
                v29 = 1;
                do
                {
                  while ( 1 )
                  {
                    if ( !v29 )
                      goto LABEL_95;
                    SH<unsigned short *,SH_SSTRING>::Reset(&v34);
                    v30 = CMiscHelpersT<CEmptyType>::CombinePath(a3, L"ActionList.xml", 0, &v34);
                    v14 = *(_QWORD *)this;
                    v13 = v30;
                    if ( v30 < 0 )
                    {
                      v11 = 219;
                      goto LABEL_103;
                    }
                    v28 = v34;
                    v29 = 0;
                    if ( v14 )
                      CFCLogLiteT<CEmptyType>::LogFormat(
                        v14,
                        2,
                        L"DeploymentSessionWrapper: ActionList path: [%s]",
                        v34);
                    if ( *(_QWORD *)this )
                      CFCLogLiteT<CEmptyType>::LogFormat(
                        *(_QWORD *)this,
                        2,
                        L"DeploymentSessionWrapper: Calling GenerateDownloadRequest on Deployment Session object");
                    Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v49);
                    v15 = (*(__int64 (__fastcall **)(__int64, struct IDeploymentDownloadRequest **))(*(_QWORD *)v51 + 32LL))(
                            v51,
                            &v49);
                    v13 = v15;
                    if ( v15 != -1047526399 )
                      break;
                    if ( *(_QWORD *)this )
                      CFCLogLiteT<CEmptyType>::LogFormat(
                        *(_QWORD *)this,
                        2,
                        L"DeploymentSessionWrapper: No packages to be downloaded");
                    v13 = 0;
                  }
                  if ( v15 < 0 )
                  {
                    v11 = 233;
                    goto LABEL_14;
                  }
                  Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v50);
                  v15 = (*(__int64 (__fastcall **)(struct IDeploymentDownloadRequest *, __int64 *))(*(_QWORD *)v49 + 40LL))(
                          v49,
                          &v50);
                  v13 = v15;
                  if ( v15 < 0 )
                  {
                    v11 = 235;
                    goto LABEL_14;
                  }
                  v30 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v50 + 24LL))(v50, &v47);
                  v14 = *(_QWORD *)this;
                  v13 = v30;
                  if ( v30 < 0 )
                  {
                    v11 = 236;
LABEL_103:
                    v12 = (unsigned int)v30;
                    goto LABEL_5;
                  }
                  if ( v14 )
                    CFCLogLiteT<CEmptyType>::LogFormat(
                      v14,
                      2,
                      L"DeploymentSessionWrapper: Download Request File Count = [%lu]",
                      v47);
                }
                while ( !v47 );
                if ( a6 )
                {
                  if ( *(_QWORD *)this )
                    CFCLogLiteT<CEmptyType>::LogFormat(
                      *(_QWORD *)this,
                      2,
                      L"DeploymentSessionWrapper: Skipping the request for payload files");
LABEL_95:
                  v34 = 0;
                  *v39 = v28;
                  goto LABEL_96;
                }
                v15 = CDeploymentSessionWrapper::RequestPayloadFiles(this, v49, v27, a3);
                v13 = v15;
                if ( v15 >= 0 )
                  continue;
                break;
              }
              v11 = 248;
            }
            else
            {
              v11 = 209;
            }
          }
          else
          {
            v25 = GetLastError();
            v15 = SErrorConverter::C_LR2HR(v25);
            v13 = v15;
            v11 = 189;
          }
        }
        else
        {
          v35 = 0;
          v23 = GetLastError();
          v15 = SErrorConverter::C_LR2HR(v23);
          v13 = v15;
          v11 = 186;
        }
        goto LABEL_14;
      }
      if ( *(_QWORD *)this )
        CFCLogLiteT<CEmptyType>::LogFormat(
          *(_QWORD *)this,
          2,
          L"DeploymentSessionWrapper: UpdateAgent.dll signature is not trusted.");
      v13 = -2147024210;
      v11 = 180;
    }
    else
    {
      v13 = -2147024894;
      v11 = 170;
    }
  }
  else
  {
    v13 = -2147024893;
    v11 = 114;
  }
  v12 = v13;
LABEL_4:
  v14 = *(_QWORD *)this;
LABEL_5:
  CFCLogLiteT<CEmptyType>::LogError(v14, v12, L"CDeploymentSessionWrapper::Download", v11);
LABEL_96:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v13);
  SH<unsigned short *,SH_SSTRING>::Reset(&v34);
  Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v50);
  Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v49);
  if ( v51 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
    v51 = 0;
  }
  SH<HINSTANCE__ *,SH_HMODULE>::Reset(&v35);
  SH<unsigned short *,SH_SSTRING>::Reset(&lpLibFileName);
  SH<unsigned short *,SH_SSTRING>::Reset(&lpPathName);
  return v13;
}

```

## disassembly

```asm
0x1802970bc  push    rbp
0x1802970be  push    rbx
0x1802970bf  push    rsi
0x1802970c0  push    rdi
0x1802970c1  push    r12
0x1802970c3  push    r13
0x1802970c5  push    r14
0x1802970c7  push    r15
0x1802970c9  lea     rbp, [rsp-428h]
0x1802970d1  sub     rsp, 528h
0x1802970d8  mov     rax, cs:__security_cookie
0x1802970df  xor     rax, rsp
0x1802970e2  mov     [rbp+460h+var_50], rax
0x1802970e9  mov     r14, [rbp+460h+arg_20]
0x1802970f0  xorps   xmm0, xmm0
0x1802970f3  mov     r13, rdx
0x1802970f6  mov     [rsp+560h+var_4F0], r14
0x1802970fb  xor     edx, edx
0x1802970fd  xor     eax, eax
0x1802970ff  mov     [rsp+560h+lpPathName], rdx
0x180297104  mov     rdi, rcx
0x180297107  mov     rcx, [rbp+460h+arg_30]
0x18029710e  mov     r12, r9
0x180297111  mov     [rbp+460h+var_4E0], rcx
0x180297115  mov     r15, r8
0x180297118  mov     [rbp+460h+lpLibFileName], rdx
0x18029711c  mov     [rsp+560h+var_500], rdx
0x180297121  mov     [rbp+460h+var_458], rdx
0x180297125  mov     [rbp+460h+var_490], rax
0x180297129  mov     [rbp+460h+var_468], rdx
0x18029712d  mov     [rbp+460h+var_460], rdx
0x180297131  mov     [rbp+460h+var_478], edx
0x180297134  mov     [rbp+460h+Type], edx
0x180297137  mov     [rsp+560h+var_510], edx
0x18029713b  mov     [rsp+560h+var_50C], edx
0x18029713f  mov     [rsp+560h+var_4E8], rdx
0x180297144  mov     [rsp+560h+var_508], rdx
0x180297149  movups  [rbp+460h+var_4C0], xmm0
0x18029714d  movups  [rbp+460h+var_4B0], xmm0
0x180297151  movups  [rbp+460h+var_4A0], xmm0
0x180297155  test    r13, r13
0x180297158  jnz     short loc_180297179
0x18029715a  lea     r9d, [rdx+6Ah]
0x18029715e  mov     edx, 80070057h
0x180297163  mov     ebx, edx
0x180297165  mov     rcx, [rdi]
0x180297168  lea     r8, aCdeploymentses; "CDeploymentSessionWrapper::Download"
0x18029716f  call    ?LogError@?$CFCLogLiteT@VCEmptyType@@@@SAJPEAVIFCDiagnosticsLite@@JPEBGK@Z; CFCLogLiteT<CEmptyType>::LogError(IFCDiagnosticsLite *,long,ushort const *,ulong)
0x180297174  jmp     loc_1802977AB
0x180297179  test    r15, r15
0x18029717c  jnz     short loc_180297184
0x18029717e  lea     r9d, [r15+6Bh]
0x180297182  jmp     short loc_18029715E
0x180297184  test    r14, r14
0x180297187  jnz     short loc_18029718F
0x180297189  lea     r9d, [r14+6Ch]
0x18029718d  jmp     short loc_18029715E
0x18029718f  test    rcx, rcx
0x180297192  jnz     short loc_18029719A
0x180297194  lea     r9d, [rcx+6Dh]
0x180297198  jmp     short loc_18029715E
0x18029719a  lea     rdx, [rbp+460h+Type]
0x18029719e  mov     rcx, r15
0x1802971a1  call    ?DirectoryExists@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAH@Z; CMiscHelpersT<CEmptyType>::DirectoryExists(ushort const *,int *)
0x1802971a6  mov     ebx, eax
0x1802971a8  test    eax, eax
0x1802971aa  jns     short loc_1802971B6
0x1802971ac  mov     r9d, 71h ; 'q'
0x1802971b2  mov     edx, eax
0x1802971b4  jmp     short loc_180297165
0x1802971b6  cmp     [rbp+460h+Type], 0
0x1802971ba  jnz     short loc_1802971CB
0x1802971bc  mov     ebx, 80070003h
0x1802971c1  mov     r9d, 72h ; 'r'
0x1802971c7  mov     edx, ebx
0x1802971c9  jmp     short loc_180297165
0x1802971cb  lea     r9, [rsp+560h+lpPathName]
0x1802971d0  xor     r8d, r8d
0x1802971d3  lea     rdx, aMetadata_2; "metadata"
0x1802971da  mov     rcx, r15
0x1802971dd  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x1802971e2  mov     ebx, eax
0x1802971e4  test    eax, eax
0x1802971e6  jns     short loc_1802971F0
0x1802971e8  mov     r9d, 76h ; 'v'
0x1802971ee  jmp     short loc_1802971B2
0x1802971f0  mov     rsi, [rsp+560h+lpPathName]
0x1802971f5  lea     rdx, [rbp+460h+Type]
0x1802971f9  mov     rcx, rsi
0x1802971fc  call    ?DirectoryExists@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAH@Z; CMiscHelpersT<CEmptyType>::DirectoryExists(ushort const *,int *)
0x180297201  mov     ebx, eax
0x180297203  test    eax, eax
0x180297205  jns     short loc_18029720F
0x180297207  mov     r9d, 77h ; 'w'
0x18029720d  jmp     short loc_1802971B2
0x18029720f  cmp     [rbp+460h+Type], 0
0x180297213  jnz     short loc_18029724A
0x180297215  xor     edx, edx; lpSecurityAttributes
0x180297217  mov     rcx, rsi; lpPathName
0x18029721a  call    cs:__imp_CreateDirectoryW
0x180297221  nop     dword ptr [rax+rax+00h]
0x180297226  test    eax, eax
0x180297228  jnz     short loc_18029724A
0x18029722a  call    cs:__imp_GetLastError
0x180297231  nop     dword ptr [rax+rax+00h]
0x180297236  mov     ecx, eax; unsigned int
0x180297238  call    ?C_LR2HR@SErrorConverter@@SAJK@Z; SErrorConverter::C_LR2HR(ulong)
0x18029723d  mov     ebx, eax
0x18029723f  mov     r9d, 7Ah ; 'z'
0x180297245  jmp     loc_1802971B2
0x18029724a  mov     rax, [r14]
0x18029724d  mov     rdx, rsi
0x180297250  mov     rcx, r14
0x180297253  mov     rax, [rax]
0x180297256  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029725b  mov     ebx, eax
0x18029725d  test    eax, eax
0x18029725f  jns     short loc_18029726C
0x180297261  mov     r9d, 7Fh
0x180297267  jmp     loc_1802971B2
0x18029726c  mov     rax, [r14]
0x18029726f  mov     rdx, rsi
0x180297272  mov     rcx, r14
0x180297275  mov     rax, [rax+8]
0x180297279  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029727e  mov     ebx, eax
0x180297280  test    eax, eax
0x180297282  jns     short loc_18029728F
0x180297284  mov     r9d, 81h
0x18029728a  jmp     loc_1802971B2
0x18029728f  lea     rcx, [rbp+460h+lpLibFileName]
0x180297293  call    ?Reset@?$SH@PEAGVSH_SSTRING@@@@QEAAXXZ; SH<ushort *,SH_SSTRING>::Reset(void)
0x180297298  test    r12, r12
0x18029729b  jnz     loc_18029735C
0x1802972a1  lea     rax, [rbp+460h+hKey]
0x1802972a5  mov     [rbp+460h+hKey], r12
0x1802972a9  mov     r9d, 20019h; samDesired
0x1802972af  mov     [rsp+560h+phkResult], rax; phkResult
0x1802972b4  xor     r8d, r8d; ulOptions
0x1802972b7  lea     rdx, aSoftwareMicros_12; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1802972be  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1802972c5  call    cs:__imp_RegOpenKeyExW
0x1802972cc  nop     dword ptr [rax+rax+00h]
0x1802972d1  test    eax, eax
0x1802972d3  jnz     loc_18029735C
0x1802972d9  mov     ebx, 400h
0x1802972de  mov     [rbp+460h+Type], eax
0x1802972e1  mov     r8d, ebx; Size
0x1802972e4  lea     rcx, [rbp+460h+Data]; void *
0x1802972e8  xor     edx, edx; Val
0x1802972ea  call    memset_0
0x1802972ef  mov     rcx, [rbp+460h+hKey]; hKey
0x1802972f3  lea     rax, [rbp+460h+cbData]
0x1802972f7  mov     [rsp+560h+lpcbData], rax; lpcbData
0x1802972fc  lea     r9, [rbp+460h+Type]; lpType
0x180297300  lea     rax, [rbp+460h+Data]
0x180297304  mov     [rbp+460h+cbData], ebx
0x180297307  xor     r8d, r8d; lpReserved
0x18029730a  mov     [rsp+560h+phkResult], rax; lpData
0x18029730f  lea     rdx, aAlternateservi; "AlternateServiceStackDLLPath"
0x180297316  call    cs:__imp_RegQueryValueExW
0x18029731d  nop     dword ptr [rax+rax+00h]
0x180297322  mov     rcx, [rbp+460h+hKey]; hKey
0x180297326  mov     ebx, eax
0x180297328  call    cs:__imp_RegCloseKey
0x18029732f  nop     dword ptr [rax+rax+00h]
0x180297334  test    ebx, ebx
0x180297336  jnz     short loc_18029735C
0x180297338  cmp     [rbp+460h+Type], 1
0x18029733c  jnz     short loc_18029735C
0x18029733e  lea     rdx, [rbp+460h+lpLibFileName]
0x180297342  lea     rcx, [rbp+460h+Data]; Src
0x180297346  call    ?Create@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@SAJPEBGPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::Create(ushort const *,ushort * *)
0x18029734b  mov     ebx, eax
0x18029734d  test    eax, eax
0x18029734f  jns     short loc_18029735C
0x180297351  mov     r9d, 97h
0x180297357  jmp     loc_1802971B2
0x18029735c  mov     rbx, [rbp+460h+lpLibFileName]
0x180297360  test    rbx, rbx
0x180297363  jnz     short loc_180297390
0x180297365  lea     r9, [rbp+460h+lpLibFileName]
0x180297369  xor     r8d, r8d
0x18029736c  lea     rdx, aUpdateagentDll_1; "UpdateAgent.dll"
0x180297373  mov     rcx, rsi
0x180297376  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x18029737b  mov     ebx, eax
0x18029737d  test    eax, eax
0x18029737f  jns     short loc_18029738C
0x180297381  mov     r9d, 0A0h
0x180297387  jmp     loc_1802971B2
0x18029738c  mov     rbx, [rbp+460h+lpLibFileName]
0x180297390  lea     rcx, [rbp+460h+cbData]
0x180297394  mov     [rbp+460h+lpLibFileName], 0
0x18029739c  mov     qword ptr [rbp+460h+cbData], 0
0x1802973a4  call    ?Reset@?$SH@PEAGVSH_SSTRING@@@@QEAAXXZ; SH<ushort *,SH_SSTRING>::Reset(void)
0x1802973a9  lea     r8, [rbp+460h+lpLibFileName]
0x1802973ad  mov     qword ptr [rbp+460h+cbData], rbx
0x1802973b1  mov     rcx, rbx; lpFileName
0x1802973b4  call    ?GetFinalPath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGKPEAPEAG@Z; CMiscHelpersT<CEmptyType>::GetFinalPath(ushort const *,ulong,ushort * *)
0x1802973b9  mov     ebx, eax
0x1802973bb  test    eax, eax
0x1802973bd  jns     short loc_1802973E4
0x1802973bf  mov     rcx, [rdi]
0x1802973c2  lea     r8, aCdeploymentses; "CDeploymentSessionWrapper::Download"
0x1802973c9  mov     r9d, 0A7h
0x1802973cf  mov     edx, eax
0x1802973d1  call    ?LogError@?$CFCLogLiteT@VCEmptyType@@@@SAJPEAVIFCDiagnosticsLite@@JPEBGK@Z; CFCLogLiteT<CEmptyType>::LogError(IFCDiagnosticsLite *,long,ushort const *,ulong)
0x1802973d6  lea     rcx, [rbp+460h+cbData]
0x1802973da  call    ?Reset@?$SH@PEAGVSH_SSTRING@@@@QEAAXXZ; SH<ushort *,SH_SSTRING>::Reset(void)
0x1802973df  jmp     loc_1802977AB
0x1802973e4  lea     rcx, [rbp+460h+cbData]
0x1802973e8  call    ?Reset@?$SH@PEAGVSH_SSTRING@@@@QEAAXXZ; SH<ushort *,SH_SSTRING>::Reset(void)
0x1802973ed  mov     r14, [rbp+460h+lpLibFileName]
0x1802973f1  lea     rdx, [rsp+560h+var_510]
0x1802973f6  mov     rcx, r14
0x1802973f9  call    ?FileExists@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAH@Z; CMiscHelpersT<CEmptyType>::FileExists(ushort const *,int *)
0x1802973fe  mov     ebx, eax
0x180297400  test    eax, eax
0x180297402  jns     short loc_18029740F
0x180297404  mov     r9d, 0A9h
0x18029740a  jmp     loc_1802971B2
0x18029740f  cmp     [rsp+560h+var_510], 0
0x180297414  jnz     short loc_180297426
0x180297416  mov     ebx, 80070002h
0x18029741b  mov     r9d, 0AAh
0x180297421  jmp     loc_1802971C7
0x180297426  test    r12, r12
0x180297429  jnz     short loc_180297479
0x18029742b  lea     rdx, [rsp+560h+var_50C]; int *
0x180297430  mov     rcx, r14; unsigned __int16 *
0x180297433  call    ?VerifyFileSignature@@YAJPEBGPEAH@Z; VerifyFileSignature(ushort const *,int *)
0x180297438  mov     ebx, eax
0x18029743a  test    eax, eax
0x18029743c  jns     short loc_180297449
0x18029743e  mov     r9d, 0B0h
0x180297444  jmp     loc_1802971B2
0x180297449  cmp     [rsp+560h+var_50C], 0
0x18029744e  jnz     short loc_180297479
0x180297450  mov     rcx, [rdi]
0x180297453  test    rcx, rcx
0x180297456  jz      short loc_180297469
0x180297458  lea     r8, aDeploymentsess_18; "DeploymentSessionWrapper: UpdateAgent.d"...
0x18029745f  mov     edx, 2
0x180297464  call    ?LogFormat@?$CFCLogLiteT@VCEmptyType@@@@SAJPEAVIFCDiagnosticsLite@@W4FC_LOGLEVEL@@PEBGZZ; CFCLogLiteT<CEmptyType>::LogFormat(IFCDiagnosticsLite *,FC_LOGLEVEL,ushort const *,...)
0x180297469  mov     ebx, 800702AEh
0x18029746e  mov     r9d, 0B4h
0x180297474  jmp     loc_1802971C7
0x180297479  mov     rcx, [rdi]
0x18029747c  mov     esi, 2
0x180297481  test    rcx, rcx
0x180297484  jz      short loc_180297497
0x180297486  mov     r9, r14
0x180297489  lea     r8, aDeploymentsess_17; "DeploymentSessionWrapper: Loading Updat"...
0x180297490  mov     edx, esi
0x180297492  call    ?LogFormat@?$CFCLogLiteT@VCEmptyType@@@@SAJPEAVIFCDiagnosticsLite@@W4FC_LOGLEVEL@@PEBGZZ; CFCLogLiteT<CEmptyType>::LogFormat(IFCDiagnosticsLite *,FC_LOGLEVEL,ushort const *,...)
0x180297497  xor     r8d, r8d; dwFlags
0x18029749a  xor     edx, edx; hFile
0x18029749c  mov     rcx, r14; lpLibFileName
0x18029749f  call    cs:__imp_LoadLibraryExW
0x1802974a6  nop     dword ptr [rax+rax+00h]
0x1802974ab  lea     rcx, [rsp+560h+var_500]
0x1802974b0  mov     rbx, rax
0x1802974b3  call    ?Reset@?$SH@PEAUHINSTANCE__@@VSH_HMODULE@@@@QEAAXXZ; SH<HINSTANCE__ *,SH_HMODULE>::Reset(void)
0x1802974b8  test    rbx, rbx
0x1802974bb  jnz     short loc_1802974E2
0x1802974bd  mov     [rsp+560h+var_500], rbx
0x1802974c2  call    cs:__imp_GetLastError
0x1802974c9  nop     dword ptr [rax+rax+00h]
0x1802974ce  mov     ecx, eax; unsigned int
0x1802974d0  call    ?C_LR2HR@SErrorConverter@@SAJK@Z; SErrorConverter::C_LR2HR(ulong)
0x1802974d5  mov     ebx, eax
0x1802974d7  mov     r9d, 0BAh
0x1802974dd  jmp     loc_1802971B2
0x1802974e2  lea     rdx, aCreateofflined; "CreateOfflineDeploymentSession"
0x1802974e9  mov     [rsp+560h+var_500], rbx
0x1802974ee  mov     rcx, rbx; hModule
0x1802974f1  call    cs:__imp_GetProcAddress
0x1802974f8  nop     dword ptr [rax+rax+00h]
0x1802974fd  mov     rbx, rax
0x180297500  test    rax, rax
0x180297503  jnz     short loc_180297525
0x180297505  call    cs:__imp_GetLastError
0x18029750c  nop     dword ptr [rax+rax+00h]
0x180297511  mov     ecx, eax; unsigned int
0x180297513  call    ?C_LR2HR@SErrorConverter@@SAJK@Z; SErrorConverter::C_LR2HR(ulong)
0x180297518  mov     ebx, eax
0x18029751a  mov     r9d, 0BDh
0x180297520  jmp     loc_1802971B2
0x180297525  mov     rcx, [rdi]
0x180297528  xorps   xmm0, xmm0
0x18029752b  xor     eax, eax
0x18029752d  mov     [rbp+460h+var_490], rax
0x180297531  movups  [rbp+460h+var_4C0], xmm0
0x180297535  mov     qword ptr [rbp+460h+var_4C0], r13
0x180297539  movups  [rbp+460h+var_4B0], xmm0
0x18029753d  movups  [rbp+460h+var_4A0], xmm0
0x180297541  test    rcx, rcx
0x180297544  jz      short loc_180297554
0x180297546  lea     r8, aDeploymentsess_7; "DeploymentSessionWrapper: Creating Depl"...
  ... truncated ...
```
