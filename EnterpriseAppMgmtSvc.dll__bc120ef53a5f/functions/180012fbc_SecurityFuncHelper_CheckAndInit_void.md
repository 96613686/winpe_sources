# SecurityFuncHelper::CheckAndInit(void)

- ea: `0x180012fbc`
- end: `0x1800133bf`
- name: `?CheckAndInit@SecurityFuncHelper@@AEAAJXZ`
- size: `1027`
- prototype: `__int64 __fastcall(SecurityFuncHelper *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800036b8`

## callees

- `0x180012fbc`
- `0x1800133c8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180012fde`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180013129`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800131d7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800132ce`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180012fde`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180013129`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800131d7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800132ce`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001302c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013056`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013080`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800130aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800130d4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800130fe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013173`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013194`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800131b5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013225`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001324f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013279`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800132a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001331c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013342`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013368`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001302c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013056`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013080`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800130aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800130d4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800130fe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013173`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013194`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800131b5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013225`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001324f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013279`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800132a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001331c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013342`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013368`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180013001`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001314c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800131fa`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800132f1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180013001`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001314c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800131fa`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800132f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013380`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013380`

## string_xrefs

- `0x180012fd1`: `ChamberProf.Dll`
- `0x18001304f`: `UpdateChamberProfile`
- `0x180013022`: `CreateChamberProfile`
- `0x1800130a3`: `DeleteChamberProfileAfterMove`
- `0x180013079`: `DeleteChamberProfile`
- `0x1800130f7`: `GetChamberFolderPath`
- `0x1800130cd`: `ApplyCodeFolderACL`
- `0x18001311c`: `DeploymentExt.dll`
- `0x1800131a7`: `SetCapabilitiesSIDs`
- `0x1800131ca`: `WPTrust.dll`
- `0x1800132c1`: `PreAuthz.dll`
- `0x180013312`: `AddTrustedPreInstalledExecutable`

## pseudocode

```c
__int64 __fastcall SecurityFuncHelper::CheckAndInit(SecurityFuncHelper *this)
{
  HMODULE Library; // rbx
  HMODULE v2; // rbx
  HMODULE v3; // rbx
  HMODULE v4; // rbx
  signed int LastError; // eax
  signed int v6; // ebx

  if ( byte_180096AF0 )
    return 0;
  Library = LoadLibraryExW(L"ChamberProf.Dll", 0, 0x800u);
  if ( Library == s_SecurityFuncHelper )
  {
    Library = s_SecurityFuncHelper;
  }
  else
  {
    if ( s_SecurityFuncHelper )
      FreeLibrary(s_SecurityFuncHelper);
    s_SecurityFuncHelper = Library;
  }
  if ( !Library
    || (qword_180096AF8 = (__int64)GetProcAddress(Library, "CreateChamberProfile")) != 0
    && (qword_180096B00 = (__int64)GetProcAddress(s_SecurityFuncHelper, "UpdateChamberProfile")) != 0
    && (qword_180096B08 = (__int64)GetProcAddress(s_SecurityFuncHelper, "DeleteChamberProfile")) != 0
    && (qword_180096B10 = (__int64)GetProcAddress(s_SecurityFuncHelper, "DeleteChamberProfileAfterMove")) != 0
    && (qword_180096B18 = (__int64)GetProcAddress(s_SecurityFuncHelper, "ApplyCodeFolderACL")) != 0
    && (qword_180096B68 = (__int64)GetProcAddress(s_SecurityFuncHelper, "GetChamberFolderPath")) != 0 )
  {
    v2 = LoadLibraryExW(L"DeploymentExt.dll", 0, 0x800u);
    if ( v2 == hModule )
    {
      v2 = hModule;
    }
    else
    {
      if ( hModule )
        FreeLibrary(hModule);
      hModule = v2;
    }
    if ( v2 )
    {
      qword_180096B58 = (__int64)GetProcAddress(v2, "ProvisionRuntime_ProvisionMarketplaceApplication");
      qword_180096B60 = (__int64)GetProcAddress(hModule, "ProvisionRuntime_DeprovisionMarketplaceApplication");
      qword_180096B70 = (__int64)GetProcAddress(hModule, "SetCapabilitiesSIDs");
    }
    v3 = LoadLibraryExW(L"WPTrust.dll", 0, 0x800u);
    if ( v3 == hLibModule )
    {
      v3 = hLibModule;
    }
    else
    {
      if ( hLibModule )
        FreeLibrary(hLibModule);
      hLibModule = v3;
    }
    if ( !v3
      || (qword_180096B20 = (__int64)GetProcAddress(v3, "SV_AuthenticateAppXSignatureFile")) != 0
      && (qword_180096B28 = (__int64)GetProcAddress(hLibModule, "SV_DeallocateSignedFileInfoMember")) != 0
      && (qword_180096B38 = (__int64)GetProcAddress(hLibModule, "SV_AuthenticateEmbeddedSignedFile")) != 0
      && (qword_180096B30 = (__int64)GetProcAddress(hLibModule, "SV_AuthenticateXAPFile")) != 0 )
    {
      v4 = LoadLibraryExW(L"PreAuthz.dll", 0, 0x800u);
      if ( v4 == qword_180096AE8 )
      {
        v4 = qword_180096AE8;
      }
      else
      {
        if ( qword_180096AE8 )
          FreeLibrary(qword_180096AE8);
        qword_180096AE8 = v4;
      }
      if ( !v4
        || (qword_180096B48 = (__int64)GetProcAddress(v4, "AddTrustedPreInstalledExecutable")) != 0
        && (qword_180096B40 = (__int64)GetProcAddress(qword_180096AE8, "AddTrustedExecutable")) != 0
        && (qword_180096B50 = (__int64)GetProcAddress(qword_180096AE8, "AddTrustedExecutableFromCatalog")) != 0 )
      {
        byte_180096AF0 = 1;
        return 0;
      }
    }
  }
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
  if ( v6 < 0 )
    SecurityFuncHelper::Uninitialize((SecurityFuncHelper *)&s_SecurityFuncHelper);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180012fbc  push    rbx
0x180012fbe  sub     rsp, 20h
0x180012fc2  cmp     cs:byte_180096AF0, 0
0x180012fc9  jnz     loc_1800133B4
0x180012fcf  xor     edx, edx; hFile
0x180012fd1  lea     rcx, LibFileName; "ChamberProf.Dll"
0x180012fd8  mov     r8d, 800h; dwFlags
0x180012fde  call    cs:__imp_LoadLibraryExW
0x180012fe5  nop     dword ptr [rax+rax+00h]
0x180012fea  mov     rbx, rax
0x180012fed  mov     rax, cs:?s_SecurityFuncHelper@@3VSecurityFuncHelper@@A; SecurityFuncHelper s_SecurityFuncHelper
0x180012ff4  cmp     rbx, rax
0x180012ff7  jz      short loc_180013016
0x180012ff9  test    rax, rax
0x180012ffc  jz      short loc_18001300D
0x180012ffe  mov     rcx, rax; hLibModule
0x180013001  call    cs:__imp_FreeLibrary
0x180013008  nop     dword ptr [rax+rax+00h]
0x18001300d  mov     cs:?s_SecurityFuncHelper@@3VSecurityFuncHelper@@A, rbx; SecurityFuncHelper s_SecurityFuncHelper
0x180013014  jmp     short loc_180013019
0x180013016  mov     rbx, rax
0x180013019  test    rbx, rbx
0x18001301c  jz      loc_18001311A
0x180013022  lea     rdx, aCreatechamberp; "CreateChamberProfile"
0x180013029  mov     rcx, rbx; hModule
0x18001302c  call    cs:__imp_GetProcAddress
0x180013033  nop     dword ptr [rax+rax+00h]
0x180013038  mov     cs:qword_180096AF8, rax
0x18001303f  test    rax, rax
0x180013042  jz      loc_180013380
0x180013048  mov     rcx, cs:?s_SecurityFuncHelper@@3VSecurityFuncHelper@@A; hModule
0x18001304f  lea     rdx, aUpdatechamberp; "UpdateChamberProfile"
0x180013056  call    cs:__imp_GetProcAddress
0x18001305d  nop     dword ptr [rax+rax+00h]
0x180013062  mov     cs:qword_180096B00, rax
0x180013069  test    rax, rax
0x18001306c  jz      loc_180013380
0x180013072  mov     rcx, cs:?s_SecurityFuncHelper@@3VSecurityFuncHelper@@A; hModule
0x180013079  lea     rdx, aDeletechamberp; "DeleteChamberProfile"
0x180013080  call    cs:__imp_GetProcAddress
0x180013087  nop     dword ptr [rax+rax+00h]
0x18001308c  mov     cs:qword_180096B08, rax
0x180013093  test    rax, rax
0x180013096  jz      loc_180013380
0x18001309c  mov     rcx, cs:?s_SecurityFuncHelper@@3VSecurityFuncHelper@@A; hModule
0x1800130a3  lea     rdx, aDeletechamberp_0; "DeleteChamberProfileAfterMove"
0x1800130aa  call    cs:__imp_GetProcAddress
0x1800130b1  nop     dword ptr [rax+rax+00h]
0x1800130b6  mov     cs:qword_180096B10, rax
0x1800130bd  test    rax, rax
0x1800130c0  jz      loc_180013380
0x1800130c6  mov     rcx, cs:?s_SecurityFuncHelper@@3VSecurityFuncHelper@@A; hModule
0x1800130cd  lea     rdx, aApplycodefolde; "ApplyCodeFolderACL"
0x1800130d4  call    cs:__imp_GetProcAddress
0x1800130db  nop     dword ptr [rax+rax+00h]
0x1800130e0  mov     cs:qword_180096B18, rax
0x1800130e7  test    rax, rax
0x1800130ea  jz      loc_180013380
0x1800130f0  mov     rcx, cs:?s_SecurityFuncHelper@@3VSecurityFuncHelper@@A; hModule
0x1800130f7  lea     rdx, aGetchamberfold; "GetChamberFolderPath"
0x1800130fe  call    cs:__imp_GetProcAddress
0x180013105  nop     dword ptr [rax+rax+00h]
0x18001310a  mov     cs:qword_180096B68, rax
0x180013111  test    rax, rax
0x180013114  jz      loc_180013380
0x18001311a  xor     edx, edx; hFile
0x18001311c  lea     rcx, aDeploymentextD; "DeploymentExt.dll"
0x180013123  mov     r8d, 800h; dwFlags
0x180013129  call    cs:__imp_LoadLibraryExW
0x180013130  nop     dword ptr [rax+rax+00h]
0x180013135  mov     rbx, rax
0x180013138  mov     rax, cs:hModule
0x18001313f  cmp     rbx, rax
0x180013142  jz      short loc_180013161
0x180013144  test    rax, rax
0x180013147  jz      short loc_180013158
0x180013149  mov     rcx, rax; hLibModule
0x18001314c  call    cs:__imp_FreeLibrary
0x180013153  nop     dword ptr [rax+rax+00h]
0x180013158  mov     cs:hModule, rbx
0x18001315f  jmp     short loc_180013164
0x180013161  mov     rbx, rax
0x180013164  test    rbx, rbx
0x180013167  jz      short loc_1800131C8
0x180013169  lea     rdx, aProvisionrunti; "ProvisionRuntime_ProvisionMarketplaceAp"...
0x180013170  mov     rcx, rbx; hModule
0x180013173  call    cs:__imp_GetProcAddress
0x18001317a  nop     dword ptr [rax+rax+00h]
0x18001317f  mov     rcx, cs:hModule; hModule
0x180013186  lea     rdx, aProvisionrunti_0; "ProvisionRuntime_DeprovisionMarketplace"...
0x18001318d  mov     cs:qword_180096B58, rax
0x180013194  call    cs:__imp_GetProcAddress
0x18001319b  nop     dword ptr [rax+rax+00h]
0x1800131a0  mov     rcx, cs:hModule; hModule
0x1800131a7  lea     rdx, aSetcapabilitie; "SetCapabilitiesSIDs"
0x1800131ae  mov     cs:qword_180096B60, rax
0x1800131b5  call    cs:__imp_GetProcAddress
0x1800131bc  nop     dword ptr [rax+rax+00h]
0x1800131c1  mov     cs:qword_180096B70, rax
0x1800131c8  xor     edx, edx; hFile
0x1800131ca  lea     rcx, aWptrustDll; "WPTrust.dll"
0x1800131d1  mov     r8d, 800h; dwFlags
0x1800131d7  call    cs:__imp_LoadLibraryExW
0x1800131de  nop     dword ptr [rax+rax+00h]
0x1800131e3  mov     rbx, rax
0x1800131e6  mov     rax, cs:hLibModule
0x1800131ed  cmp     rbx, rax
0x1800131f0  jz      short loc_18001320F
0x1800131f2  test    rax, rax
0x1800131f5  jz      short loc_180013206
0x1800131f7  mov     rcx, rax; hLibModule
0x1800131fa  call    cs:__imp_FreeLibrary
0x180013201  nop     dword ptr [rax+rax+00h]
0x180013206  mov     cs:hLibModule, rbx
0x18001320d  jmp     short loc_180013212
0x18001320f  mov     rbx, rax
0x180013212  test    rbx, rbx
0x180013215  jz      loc_1800132BF
0x18001321b  lea     rdx, aSvAuthenticate_1; "SV_AuthenticateAppXSignatureFile"
0x180013222  mov     rcx, rbx; hModule
0x180013225  call    cs:__imp_GetProcAddress
0x18001322c  nop     dword ptr [rax+rax+00h]
0x180013231  mov     cs:qword_180096B20, rax
0x180013238  test    rax, rax
0x18001323b  jz      loc_180013380
0x180013241  mov     rcx, cs:hLibModule; hModule
0x180013248  lea     rdx, aSvDeallocatesi; "SV_DeallocateSignedFileInfoMember"
0x18001324f  call    cs:__imp_GetProcAddress
0x180013256  nop     dword ptr [rax+rax+00h]
0x18001325b  mov     cs:qword_180096B28, rax
0x180013262  test    rax, rax
0x180013265  jz      loc_180013380
0x18001326b  mov     rcx, cs:hLibModule; hModule
0x180013272  lea     rdx, aSvAuthenticate; "SV_AuthenticateEmbeddedSignedFile"
0x180013279  call    cs:__imp_GetProcAddress
0x180013280  nop     dword ptr [rax+rax+00h]
0x180013285  mov     cs:qword_180096B38, rax
0x18001328c  test    rax, rax
0x18001328f  jz      loc_180013380
0x180013295  mov     rcx, cs:hLibModule; hModule
0x18001329c  lea     rdx, aSvAuthenticate_0; "SV_AuthenticateXAPFile"
0x1800132a3  call    cs:__imp_GetProcAddress
0x1800132aa  nop     dword ptr [rax+rax+00h]
0x1800132af  mov     cs:qword_180096B30, rax
0x1800132b6  test    rax, rax
0x1800132b9  jz      loc_180013380
0x1800132bf  xor     edx, edx; hFile
0x1800132c1  lea     rcx, aPreauthzDll; "PreAuthz.dll"
0x1800132c8  mov     r8d, 800h; dwFlags
0x1800132ce  call    cs:__imp_LoadLibraryExW
0x1800132d5  nop     dword ptr [rax+rax+00h]
0x1800132da  mov     rbx, rax
0x1800132dd  mov     rax, cs:qword_180096AE8
0x1800132e4  cmp     rbx, rax
0x1800132e7  jz      short loc_180013306
0x1800132e9  test    rax, rax
0x1800132ec  jz      short loc_1800132FD
0x1800132ee  mov     rcx, rax; hLibModule
0x1800132f1  call    cs:__imp_FreeLibrary
0x1800132f8  nop     dword ptr [rax+rax+00h]
0x1800132fd  mov     cs:qword_180096AE8, rbx
0x180013304  jmp     short loc_180013309
0x180013306  mov     rbx, rax
0x180013309  test    rbx, rbx
0x18001330c  jz      loc_1800133AD
0x180013312  lea     rdx, aAddtrustedprei; "AddTrustedPreInstalledExecutable"
0x180013319  mov     rcx, rbx; hModule
0x18001331c  call    cs:__imp_GetProcAddress
0x180013323  nop     dword ptr [rax+rax+00h]
0x180013328  mov     cs:qword_180096B48, rax
0x18001332f  test    rax, rax
0x180013332  jz      short loc_180013380
0x180013334  mov     rcx, cs:qword_180096AE8; hModule
0x18001333b  lea     rdx, aAddtrustedexec_0; "AddTrustedExecutable"
0x180013342  call    cs:__imp_GetProcAddress
0x180013349  nop     dword ptr [rax+rax+00h]
0x18001334e  mov     cs:qword_180096B40, rax
0x180013355  test    rax, rax
0x180013358  jz      short loc_180013380
0x18001335a  mov     rcx, cs:qword_180096AE8; hModule
0x180013361  lea     rdx, aAddtrustedexec; "AddTrustedExecutableFromCatalog"
0x180013368  call    cs:__imp_GetProcAddress
0x18001336f  nop     dword ptr [rax+rax+00h]
0x180013374  mov     cs:qword_180096B50, rax
0x18001337b  test    rax, rax
0x18001337e  jnz     short loc_1800133AD
0x180013380  call    cs:__imp_GetLastError
0x180013387  nop     dword ptr [rax+rax+00h]
0x18001338c  mov     ebx, eax
0x18001338e  test    eax, eax
0x180013390  jle     short loc_18001339B
0x180013392  movzx   ebx, ax
0x180013395  or      ebx, 80070000h
0x18001339b  test    ebx, ebx
0x18001339d  jns     short loc_1800133B6
0x18001339f  lea     rcx, ?s_SecurityFuncHelper@@3VSecurityFuncHelper@@A; this
0x1800133a6  call    ?Uninitialize@SecurityFuncHelper@@AEAAXXZ; SecurityFuncHelper::Uninitialize(void)
0x1800133ab  jmp     short loc_1800133B6
0x1800133ad  mov     cs:byte_180096AF0, 1
0x1800133b4  xor     ebx, ebx
0x1800133b6  mov     eax, ebx
0x1800133b8  add     rsp, 20h
0x1800133bc  pop     rbx
0x1800133bd  retn
```
