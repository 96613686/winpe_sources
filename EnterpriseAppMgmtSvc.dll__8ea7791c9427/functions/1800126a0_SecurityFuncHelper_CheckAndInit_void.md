# SecurityFuncHelper::CheckAndInit(void)

- ea: `0x1800126a0`
- end: `0x180012a0c`
- name: `?CheckAndInit@SecurityFuncHelper@@AEAAJXZ`
- size: `876`
- prototype: `__int64 __fastcall(SecurityFuncHelper *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180003608`

## callees

- `0x1800126a0`
- `0x180012a14`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800126c2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800127dd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001286d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180012940`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800126c2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800127dd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001286d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180012940`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012704`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012728`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001274c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012770`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012794`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800127b8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001281b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012836`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012851`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800128af`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800128d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800128f7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001291b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012982`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800129a2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800129c2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012704`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012728`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001274c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012770`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012794`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800127b8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001281b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012836`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012851`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800128af`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800128d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800128f7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001291b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012982`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800129a2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800129c2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800126df`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800127fa`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001288a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001295d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800126df`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800127fa`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001288a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001295d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800129d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800129d4`

## string_xrefs

- `0x1800126b5`: `ChamberProf.Dll`
- `0x180012721`: `UpdateChamberProfile`
- `0x1800126fa`: `CreateChamberProfile`
- `0x180012769`: `DeleteChamberProfileAfterMove`
- `0x180012745`: `DeleteChamberProfile`
- `0x1800127b1`: `GetChamberFolderPath`
- `0x18001278d`: `ApplyCodeFolderACL`
- `0x1800127d0`: `DeploymentExt.dll`
- `0x180012843`: `SetCapabilitiesSIDs`
- `0x180012860`: `WPTrust.dll`
- `0x180012933`: `PreAuthz.dll`
- `0x180012978`: `AddTrustedPreInstalledExecutable`

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

  if ( byte_180090AF0 )
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
    || (qword_180090AF8 = (__int64)GetProcAddress(Library, "CreateChamberProfile")) != 0
    && (qword_180090B00 = (__int64)GetProcAddress(s_SecurityFuncHelper, "UpdateChamberProfile")) != 0
    && (qword_180090B08 = (__int64)GetProcAddress(s_SecurityFuncHelper, "DeleteChamberProfile")) != 0
    && (qword_180090B10 = (__int64)GetProcAddress(s_SecurityFuncHelper, "DeleteChamberProfileAfterMove")) != 0
    && (qword_180090B18 = (__int64)GetProcAddress(s_SecurityFuncHelper, "ApplyCodeFolderACL")) != 0
    && (qword_180090B68 = (__int64)GetProcAddress(s_SecurityFuncHelper, "GetChamberFolderPath")) != 0 )
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
      qword_180090B58 = (__int64)GetProcAddress(v2, "ProvisionRuntime_ProvisionMarketplaceApplication");
      qword_180090B60 = (__int64)GetProcAddress(hModule, "ProvisionRuntime_DeprovisionMarketplaceApplication");
      qword_180090B70 = (__int64)GetProcAddress(hModule, "SetCapabilitiesSIDs");
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
      || (qword_180090B20 = (__int64)GetProcAddress(v3, "SV_AuthenticateAppXSignatureFile")) != 0
      && (qword_180090B28 = (__int64)GetProcAddress(hLibModule, "SV_DeallocateSignedFileInfoMember")) != 0
      && (qword_180090B38 = (__int64)GetProcAddress(hLibModule, "SV_AuthenticateEmbeddedSignedFile")) != 0
      && (qword_180090B30 = (__int64)GetProcAddress(hLibModule, "SV_AuthenticateXAPFile")) != 0 )
    {
      v4 = LoadLibraryExW(L"PreAuthz.dll", 0, 0x800u);
      if ( v4 == qword_180090AE8 )
      {
        v4 = qword_180090AE8;
      }
      else
      {
        if ( qword_180090AE8 )
          FreeLibrary(qword_180090AE8);
        qword_180090AE8 = v4;
      }
      if ( !v4
        || (qword_180090B48 = (__int64)GetProcAddress(v4, "AddTrustedPreInstalledExecutable")) != 0
        && (qword_180090B40 = (__int64)GetProcAddress(qword_180090AE8, "AddTrustedExecutable")) != 0
        && (qword_180090B50 = (__int64)GetProcAddress(qword_180090AE8, "AddTrustedExecutableFromCatalog")) != 0 )
      {
        byte_180090AF0 = 1;
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
0x1800126a0  push    rbx
0x1800126a2  sub     rsp, 20h
0x1800126a6  cmp     cs:byte_180090AF0, 0
0x1800126ad  jnz     loc_180012A02
0x1800126b3  xor     edx, edx; hFile
0x1800126b5  lea     rcx, LibFileName; "ChamberProf.Dll"
0x1800126bc  mov     r8d, 800h; dwFlags
0x1800126c2  call    cs:__imp_LoadLibraryExW
0x1800126c8  mov     rbx, rax
0x1800126cb  mov     rax, cs:?s_SecurityFuncHelper@@3VSecurityFuncHelper@@A; SecurityFuncHelper s_SecurityFuncHelper
0x1800126d2  cmp     rbx, rax
0x1800126d5  jz      short loc_1800126EE
0x1800126d7  test    rax, rax
0x1800126da  jz      short loc_1800126E5
0x1800126dc  mov     rcx, rax; hLibModule
0x1800126df  call    cs:__imp_FreeLibrary
0x1800126e5  mov     cs:?s_SecurityFuncHelper@@3VSecurityFuncHelper@@A, rbx; SecurityFuncHelper s_SecurityFuncHelper
0x1800126ec  jmp     short loc_1800126F1
0x1800126ee  mov     rbx, rax
0x1800126f1  test    rbx, rbx
0x1800126f4  jz      loc_1800127CE
0x1800126fa  lea     rdx, aCreatechamberp; "CreateChamberProfile"
0x180012701  mov     rcx, rbx; hModule
0x180012704  call    cs:__imp_GetProcAddress
0x18001270a  mov     cs:qword_180090AF8, rax
0x180012711  test    rax, rax
0x180012714  jz      loc_1800129D4
0x18001271a  mov     rcx, cs:?s_SecurityFuncHelper@@3VSecurityFuncHelper@@A; hModule
0x180012721  lea     rdx, aUpdatechamberp; "UpdateChamberProfile"
0x180012728  call    cs:__imp_GetProcAddress
0x18001272e  mov     cs:qword_180090B00, rax
0x180012735  test    rax, rax
0x180012738  jz      loc_1800129D4
0x18001273e  mov     rcx, cs:?s_SecurityFuncHelper@@3VSecurityFuncHelper@@A; hModule
0x180012745  lea     rdx, aDeletechamberp; "DeleteChamberProfile"
0x18001274c  call    cs:__imp_GetProcAddress
0x180012752  mov     cs:qword_180090B08, rax
0x180012759  test    rax, rax
0x18001275c  jz      loc_1800129D4
0x180012762  mov     rcx, cs:?s_SecurityFuncHelper@@3VSecurityFuncHelper@@A; hModule
0x180012769  lea     rdx, aDeletechamberp_0; "DeleteChamberProfileAfterMove"
0x180012770  call    cs:__imp_GetProcAddress
0x180012776  mov     cs:qword_180090B10, rax
0x18001277d  test    rax, rax
0x180012780  jz      loc_1800129D4
0x180012786  mov     rcx, cs:?s_SecurityFuncHelper@@3VSecurityFuncHelper@@A; hModule
0x18001278d  lea     rdx, aApplycodefolde; "ApplyCodeFolderACL"
0x180012794  call    cs:__imp_GetProcAddress
0x18001279a  mov     cs:qword_180090B18, rax
0x1800127a1  test    rax, rax
0x1800127a4  jz      loc_1800129D4
0x1800127aa  mov     rcx, cs:?s_SecurityFuncHelper@@3VSecurityFuncHelper@@A; hModule
0x1800127b1  lea     rdx, aGetchamberfold; "GetChamberFolderPath"
0x1800127b8  call    cs:__imp_GetProcAddress
0x1800127be  mov     cs:qword_180090B68, rax
0x1800127c5  test    rax, rax
0x1800127c8  jz      loc_1800129D4
0x1800127ce  xor     edx, edx; hFile
0x1800127d0  lea     rcx, aDeploymentextD; "DeploymentExt.dll"
0x1800127d7  mov     r8d, 800h; dwFlags
0x1800127dd  call    cs:__imp_LoadLibraryExW
0x1800127e3  mov     rbx, rax
0x1800127e6  mov     rax, cs:hModule
0x1800127ed  cmp     rbx, rax
0x1800127f0  jz      short loc_180012809
0x1800127f2  test    rax, rax
0x1800127f5  jz      short loc_180012800
0x1800127f7  mov     rcx, rax; hLibModule
0x1800127fa  call    cs:__imp_FreeLibrary
0x180012800  mov     cs:hModule, rbx
0x180012807  jmp     short loc_18001280C
0x180012809  mov     rbx, rax
0x18001280c  test    rbx, rbx
0x18001280f  jz      short loc_18001285E
0x180012811  lea     rdx, aProvisionrunti; "ProvisionRuntime_ProvisionMarketplaceAp"...
0x180012818  mov     rcx, rbx; hModule
0x18001281b  call    cs:__imp_GetProcAddress
0x180012821  mov     rcx, cs:hModule; hModule
0x180012828  lea     rdx, aProvisionrunti_0; "ProvisionRuntime_DeprovisionMarketplace"...
0x18001282f  mov     cs:qword_180090B58, rax
0x180012836  call    cs:__imp_GetProcAddress
0x18001283c  mov     rcx, cs:hModule; hModule
0x180012843  lea     rdx, aSetcapabilitie; "SetCapabilitiesSIDs"
0x18001284a  mov     cs:qword_180090B60, rax
0x180012851  call    cs:__imp_GetProcAddress
0x180012857  mov     cs:qword_180090B70, rax
0x18001285e  xor     edx, edx; hFile
0x180012860  lea     rcx, aWptrustDll; "WPTrust.dll"
0x180012867  mov     r8d, 800h; dwFlags
0x18001286d  call    cs:__imp_LoadLibraryExW
0x180012873  mov     rbx, rax
0x180012876  mov     rax, cs:hLibModule
0x18001287d  cmp     rbx, rax
0x180012880  jz      short loc_180012899
0x180012882  test    rax, rax
0x180012885  jz      short loc_180012890
0x180012887  mov     rcx, rax; hLibModule
0x18001288a  call    cs:__imp_FreeLibrary
0x180012890  mov     cs:hLibModule, rbx
0x180012897  jmp     short loc_18001289C
0x180012899  mov     rbx, rax
0x18001289c  test    rbx, rbx
0x18001289f  jz      loc_180012931
0x1800128a5  lea     rdx, aSvAuthenticate_1; "SV_AuthenticateAppXSignatureFile"
0x1800128ac  mov     rcx, rbx; hModule
0x1800128af  call    cs:__imp_GetProcAddress
0x1800128b5  mov     cs:qword_180090B20, rax
0x1800128bc  test    rax, rax
0x1800128bf  jz      loc_1800129D4
0x1800128c5  mov     rcx, cs:hLibModule; hModule
0x1800128cc  lea     rdx, aSvDeallocatesi; "SV_DeallocateSignedFileInfoMember"
0x1800128d3  call    cs:__imp_GetProcAddress
0x1800128d9  mov     cs:qword_180090B28, rax
0x1800128e0  test    rax, rax
0x1800128e3  jz      loc_1800129D4
0x1800128e9  mov     rcx, cs:hLibModule; hModule
0x1800128f0  lea     rdx, aSvAuthenticate; "SV_AuthenticateEmbeddedSignedFile"
0x1800128f7  call    cs:__imp_GetProcAddress
0x1800128fd  mov     cs:qword_180090B38, rax
0x180012904  test    rax, rax
0x180012907  jz      loc_1800129D4
0x18001290d  mov     rcx, cs:hLibModule; hModule
0x180012914  lea     rdx, aSvAuthenticate_0; "SV_AuthenticateXAPFile"
0x18001291b  call    cs:__imp_GetProcAddress
0x180012921  mov     cs:qword_180090B30, rax
0x180012928  test    rax, rax
0x18001292b  jz      loc_1800129D4
0x180012931  xor     edx, edx; hFile
0x180012933  lea     rcx, aPreauthzDll; "PreAuthz.dll"
0x18001293a  mov     r8d, 800h; dwFlags
0x180012940  call    cs:__imp_LoadLibraryExW
0x180012946  mov     rbx, rax
0x180012949  mov     rax, cs:qword_180090AE8
0x180012950  cmp     rbx, rax
0x180012953  jz      short loc_18001296C
0x180012955  test    rax, rax
0x180012958  jz      short loc_180012963
0x18001295a  mov     rcx, rax; hLibModule
0x18001295d  call    cs:__imp_FreeLibrary
0x180012963  mov     cs:qword_180090AE8, rbx
0x18001296a  jmp     short loc_18001296F
0x18001296c  mov     rbx, rax
0x18001296f  test    rbx, rbx
0x180012972  jz      loc_1800129FB
0x180012978  lea     rdx, aAddtrustedprei; "AddTrustedPreInstalledExecutable"
0x18001297f  mov     rcx, rbx; hModule
0x180012982  call    cs:__imp_GetProcAddress
0x180012988  mov     cs:qword_180090B48, rax
0x18001298f  test    rax, rax
0x180012992  jz      short loc_1800129D4
0x180012994  mov     rcx, cs:qword_180090AE8; hModule
0x18001299b  lea     rdx, aAddtrustedexec_0; "AddTrustedExecutable"
0x1800129a2  call    cs:__imp_GetProcAddress
0x1800129a8  mov     cs:qword_180090B40, rax
0x1800129af  test    rax, rax
0x1800129b2  jz      short loc_1800129D4
0x1800129b4  mov     rcx, cs:qword_180090AE8; hModule
0x1800129bb  lea     rdx, aAddtrustedexec; "AddTrustedExecutableFromCatalog"
0x1800129c2  call    cs:__imp_GetProcAddress
0x1800129c8  mov     cs:qword_180090B50, rax
0x1800129cf  test    rax, rax
0x1800129d2  jnz     short loc_1800129FB
0x1800129d4  call    cs:__imp_GetLastError
0x1800129da  mov     ebx, eax
0x1800129dc  test    eax, eax
0x1800129de  jle     short loc_1800129E9
0x1800129e0  movzx   ebx, ax
0x1800129e3  or      ebx, 80070000h
0x1800129e9  test    ebx, ebx
0x1800129eb  jns     short loc_180012A04
0x1800129ed  lea     rcx, ?s_SecurityFuncHelper@@3VSecurityFuncHelper@@A; this
0x1800129f4  call    ?Uninitialize@SecurityFuncHelper@@AEAAXXZ; SecurityFuncHelper::Uninitialize(void)
0x1800129f9  jmp     short loc_180012A04
0x1800129fb  mov     cs:byte_180090AF0, 1
0x180012a02  xor     ebx, ebx
0x180012a04  mov     eax, ebx
0x180012a06  add     rsp, 20h
0x180012a0a  pop     rbx
0x180012a0b  retn
```
