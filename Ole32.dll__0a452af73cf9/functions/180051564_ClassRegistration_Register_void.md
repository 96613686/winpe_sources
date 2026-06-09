# ClassRegistration::Register(void)

- ea: `0x180051564`
- end: `0x180051ab3`
- name: `?Register@ClassRegistration@@QEAAJXZ`
- size: `1359`
- prototype: `HRESULT __fastcall(ClassRegistration *this)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800688c4`

## callees

- `0x180051564`
- `0x180051abc`
- `0x180051b94`
- `0x180051d64`
- `0x180052390`
- `0x180072fb0`
- `0x180072fc8`
- `0x1800c4639`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180051984`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180051984`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180051603`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180051603`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180051a2a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800ccd8c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180051a2a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800ccd8c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180051a20`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180051a5e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180051a20`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180051a5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800519f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051a32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800519f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051a32`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180051895`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800518e7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005194e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180051a6f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180051a7d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ccdd1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ccde1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ccdf1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cce01`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180051895`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800518e7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005194e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180051a6f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180051a7d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ccdd1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ccde1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ccdf1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cce01`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005168f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005168f`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x180051960`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x180051960`

## pseudocode

```c
__int64 __fastcall ClassRegistration::Register(ClassRegistration *this)
{
  HKEY__ *v2; // rsi
  HINSTANCE__ *hModule; // rcx
  __int64 v5; // rax
  int v6; // eax
  __int64 v7; // rax
  HKEY__ *v8; // rbx
  unsigned int serverType; // ecx
  unsigned int v10; // ecx
  unsigned int v11; // ecx
  HRESULT v12; // eax
  const wchar_t *v13; // rdx
  HKEY__ *v14; // rbx
  HINSTANCE__ *LibraryA; // rax
  HMODULE v16; // rbx
  FARPROC ProcAddress; // rax
  int v18; // eax
  signed int LastError; // eax
  signed int v20; // eax
  _BYTE v21[32]; // [rsp+0h] [rbp-3C8h] BYREF
  ITypeLib *pITypeLib; // [rsp+30h] [rbp-398h] BYREF
  HKEY__ *hkProgID; // [rsp+38h] [rbp-390h] BYREF
  _BYTE *v24; // [rsp+40h] [rbp-388h]
  HKEY__ *hkGuid; // [rsp+48h] [rbp-380h] BYREF
  HKEY__ *hkCLSID; // [rsp+50h] [rbp-378h] BYREF
  HKEY__ *hkInproc; // [rsp+58h] [rbp-370h] BYREF
  _EXCEPTION_POINTERS *e; // [rsp+60h] [rbp-368h]
  int v29; // [rsp+68h] [rbp-360h]
  int v30; // [rsp+6Ch] [rbp-35Ch]
  int v31; // [rsp+70h] [rbp-358h]
  int v32; // [rsp+74h] [rbp-354h]
  HRESULT v33; // [rsp+78h] [rbp-350h]
  int v34; // [rsp+7Ch] [rbp-34Ch]
  int v35; // [rsp+80h] [rbp-348h]
  ULONG_PTR Arguments; // [rsp+88h] [rbp-340h] BYREF
  HINSTANCE__ *hOleAut; // [rsp+90h] [rbp-338h]
  ULONG_PTR v38; // [rsp+98h] [rbp-330h] BYREF
  AppRegistration a; // [rsp+A0h] [rbp-328h] BYREF
  wchar_t szClsid[40]; // [rsp+D0h] [rbp-2F8h] BYREF
  wchar_t szAppId[40]; // [rsp+120h] [rbp-2A8h] BYREF
  wchar_t szModuleName[264]; // [rsp+170h] [rbp-258h] BYREF

  v24 = v21;
  hkCLSID = 0;
  hkGuid = 0;
  hkProgID = 0;
  v2 = 0;
  hkInproc = 0;
  e = 0;
  hModule = this->hModule;
  if ( !hModule )
  {
    v29 = -2147024809;
    local_unwind_0(v21, &_LN46_0);
    return 2147942487LL;
  }
  if ( !GetModuleFileNameW(hModule, szModuleName, 0x104u) )
  {
    v30 = -2147418113;
    local_unwind_0(v24, &_LN47);
    return 2147549183LL;
  }
  v5 = *(_QWORD *)&this->clsid.Data1 - *(_QWORD *)&GUID_NULL.Data1;
  if ( *(_QWORD *)&this->clsid.Data1 == *(_QWORD *)&GUID_NULL.Data1 )
    v5 = *(_QWORD *)this->clsid.Data4 - *(_QWORD *)GUID_NULL.Data4;
  if ( !v5 )
  {
    v31 = -2147024809;
    local_unwind_0(v24, &_LN48);
    return 2147942487LL;
  }
  v6 = RegOpenKeyExW(HKEY_CLASSES_ROOT, Com::Catalog::Constants::CLSID, 0, 0xF003Fu, &hkCLSID);
  if ( v6 )
  {
    if ( v6 > 0 )
      v6 = (unsigned __int16)v6 | 0x80070000;
    LODWORD(pITypeLib) = v6;
    v32 = v6;
    local_unwind_0(v24, &_LN49);
    return (unsigned int)pITypeLib;
  }
  else
  {
    GetGuidString(&this->clsid, szClsid);
    SetKeyAndValue(hkCLSID, szClsid, this->className, &hkGuid, 1);
    v7 = *(_QWORD *)&this->appid.Data1 - *(_QWORD *)&GUID_NULL.Data1;
    if ( !v7 )
      v7 = *(_QWORD *)this->appid.Data4 - *(_QWORD *)GUID_NULL.Data4;
    if ( v7 )
    {
      GetGuidString(&this->appid, szAppId);
      v8 = hkGuid;
      SetValue(hkGuid, Com::Catalog::Constants::AppID, szAppId);
      memset(&a, 0, sizeof(a));
      a.appid = this->appid;
      v12 = AppRegistration::Register(&a);
      LODWORD(pITypeLib) = v12;
      if ( v12 )
      {
        v33 = v12;
        local_unwind_0(v24, &_LN50);
        return (unsigned int)pITypeLib;
      }
    }
    else
    {
      v8 = hkGuid;
    }
    serverType = this->serverType;
    if ( serverType )
    {
      v10 = serverType - 1;
      if ( v10 )
      {
        v11 = v10 - 1;
        if ( v11 )
        {
          if ( v11 != 2 )
          {
            v34 = -2147024809;
            local_unwind_0(v24, &_LN51);
            return 2147942487LL;
          }
          v13 = Com::Catalog::Constants::LocalServer32;
        }
        else
        {
          v13 = Com::Catalog::Constants::InprocHandler32;
        }
        SetKeyAndValue(v8, v13, szModuleName, 0, 0);
      }
      else
      {
        SetKeyAndValue(v8, Com::Catalog::Constants::InprocServer32, szModuleName, &hkInproc, 0);
        v2 = hkInproc;
        SetValue(hkInproc, Com::Catalog::Constants::ThreadingModel, this->threadingModel);
      }
    }
    SetKeyAndValue(v8, Com::Catalog::Constants::ProgID, this->progID, 0, 0);
    SetKeyAndValue(v8, Com::Catalog::Constants::VersionIndependentProgID, this->versionIndependentProgID, 0, 0);
    RegCloseKey(v8);
    hkGuid = 0;
    SetKeyAndValue((HKEY__ *)0xFFFFFFFF80000000LL, this->progID, this->className, &hkProgID, 0);
    SetKeyAndValue(hkProgID, Com::Catalog::Constants::CLSID, szClsid, 0, 0);
    RegCloseKey(hkProgID);
    hkProgID = 0;
    SetKeyAndValue((HKEY__ *)0xFFFFFFFF80000000LL, this->versionIndependentProgID, this->className, &hkProgID, 0);
    v14 = hkProgID;
    SetKeyAndValue(hkProgID, Com::Catalog::Constants::CLSID, szClsid, 0, 0);
    SetKeyAndValue(v14, Com::Catalog::Constants::CurVer, this->progID, 0, 0);
    RegCloseKey(v14);
    hkProgID = 0;
    LibraryA = LoadLibraryA("OLEAUT32");
    v16 = LibraryA;
    hOleAut = LibraryA;
    if ( LibraryA )
    {
      ProcAddress = GetProcAddress(LibraryA, "LoadTypeLibEx");
      if ( ProcAddress )
      {
        pITypeLib = 0;
        v18 = ((__int64 (__fastcall *)(wchar_t *, __int64, ITypeLib **))ProcAddress)(szModuleName, 1, &pITypeLib);
        if ( v18 < 0 )
        {
          if ( v18 != -2147312566 )
          {
            v35 = -2147220992;
            local_unwind_0(v24, &_LN56);
            return 2147746304LL;
          }
        }
        else
        {
          ((void (__fastcall *)(ITypeLib *))pITypeLib->lpVtbl->Release)(pITypeLib);
          pITypeLib = 0;
        }
      }
      else
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        Arguments = LastError;
        RaiseException(0, 1u, 1u, &Arguments);
      }
      FreeLibrary(v16);
    }
    else
    {
      v20 = GetLastError();
      if ( v20 > 0 )
        v20 = (unsigned __int16)v20 | 0x80070000;
      v38 = v20;
      RaiseException(0, 1u, 1u, &v38);
    }
    if ( hkCLSID )
      RegCloseKey(hkCLSID);
    if ( v2 )
      RegCloseKey(v2);
    return 0;
  }
}

```

## disassembly

```asm
0x180051564  push    rbx
0x180051566  push    rsi
0x180051567  push    rdi
0x180051568  push    r12
0x18005156a  push    r14
0x18005156c  push    r15
0x18005156e  sub     rsp, 398h
0x180051575  mov     rax, cs:__security_cookie
0x18005157c  xor     rax, rsp
0x18005157f  mov     [rsp+3C8h+var_48], rax
0x180051587  mov     [rsp+3C8h+var_388], rsp
0x18005158c  mov     rdi, this
0x18005158f  xor     r15d, r15d
0x180051592  mov     [rsp+3C8h+hkCLSID], r15
0x180051597  mov     [rsp+3C8h+hkGuid], r15
0x18005159c  mov     [rsp+3C8h+hkProgID], r15
0x1800515a1  mov     esi, r15d
0x1800515a4  mov     [rsp+3C8h+hkInproc], r15
0x1800515a9  mov     [rsp+3C8h+e], r15
0x1800515ae  mov     this, [this+18h]; hModule
0x1800515b2  test    this, this
0x1800515b5  jnz     short loc_1800515F5
0x1800515b7  mov     [rsp+3C8h+var_360], 80070057h
0x1800515bf  lea     rdx, $LN46_0
0x1800515c6  mov     this, rsp
0x1800515c9  call    _local_unwind_0
0x1800515ce  nop
0x1800515cf  mov     eax, 80070057h
0x1800515d4  mov     this, [rsp+3C8h+var_48]
0x1800515dc  xor     this, rsp; StackCookie
0x1800515df  call    __security_check_cookie
0x1800515e4  add     rsp, 398h
0x1800515eb  pop     r15
0x1800515ed  pop     r14
0x1800515ef  pop     r12
0x1800515f1  pop     rdi
0x1800515f2  pop     rsi
0x1800515f3  pop     rbx
0x1800515f4  retn
0x1800515f5  mov     r8d, 104h; nSize
0x1800515fb  lea     rdx, [rsp+3C8h+szModuleName]; lpFilename
0x180051603  call    cs:__imp_GetModuleFileNameW
0x180051609  test    eax, eax
0x18005160b  jnz     short loc_18005162E
0x18005160d  mov     [rsp+3C8h+var_35C], 8000FFFFh
0x180051615  lea     rdx, $LN47
0x18005161c  mov     this, [rsp+3C8h+var_388]
0x180051621  call    _local_unwind_0
0x180051626  nop
0x180051627  mov     eax, 8000FFFFh
0x18005162c  jmp     short $LN37
0x18005162e  mov     rax, [rdi]
0x180051631  sub     rax, qword ptr cs:GUID_NULL.Data1
0x180051638  jnz     short loc_180051645
0x18005163a  mov     rax, [rdi+8]
0x18005163e  sub     rax, qword ptr cs:GUID_NULL.Data4
0x180051645  test    rax, rax
0x180051648  jnz     short loc_18005166E
0x18005164a  mov     [rsp+3C8h+var_358], 80070057h
0x180051652  lea     rdx, $LN48
0x180051659  mov     this, [rsp+3C8h+var_388]
0x18005165e  call    _local_unwind_0
0x180051663  nop
0x180051664  mov     eax, 80070057h
0x180051669  jmp     $LN37
0x18005166e  lea     rax, [rsp+3C8h+hkCLSID]
0x180051673  mov     [rsp+3C8h+phkResult], rax; phkResult
0x180051678  mov     r9d, 0F003Fh; samDesired
0x18005167e  xor     r8d, r8d; ulOptions
0x180051681  lea     rdx, ?CLSID@Constants@Catalog@Com@@3QBGB; lpSubKey
0x180051688  mov     this, 0FFFFFFFF80000000h; hKey
0x18005168f  call    cs:__imp_RegOpenKeyExW
0x180051695  test    eax, eax
0x180051697  jz      short loc_1800516C6
0x180051699  jle     short loc_1800516A3
0x18005169b  movzx   eax, ax
0x18005169e  or      eax, 80070000h
0x1800516a3  mov     dword ptr [rsp+3C8h+pITypeLib], eax
0x1800516a7  mov     [rsp+3C8h+var_354], eax
0x1800516ab  lea     rdx, $LN49
0x1800516b2  mov     this, [rsp+3C8h+var_388]
0x1800516b7  call    _local_unwind_0
0x1800516bc  nop
0x1800516bd  mov     eax, dword ptr [rsp+3C8h+pITypeLib]
0x1800516c1  jmp     $LN37
0x1800516c6  lea     rdx, [rsp+3C8h+szClsid]; pstrGuid
0x1800516ce  mov     this, rdi; rGuid
0x1800516d1  call    GetGuidString
0x1800516d6  mov     r12d, 1
0x1800516dc  mov     dword ptr [rsp+3C8h+phkResult], r12d; fForceKeyCreation
0x1800516e1  lea     r9, [rsp+3C8h+hkGuid]; o_phkOut
0x1800516e6  mov     r8, [rdi+20h]; i_szVal
0x1800516ea  lea     rdx, [rsp+3C8h+szClsid]; i_szKey
0x1800516f2  mov     this, [rsp+3C8h+hkCLSID]; i_hKey
0x1800516f7  call    SetKeyAndValue
0x1800516fc  lea     r14, [rdi+40h]
0x180051700  mov     rax, [r14]
0x180051703  sub     rax, qword ptr cs:GUID_NULL.Data1
0x18005170a  jnz     short loc_180051717
0x18005170c  mov     rax, [r14+8]
0x180051710  sub     rax, qword ptr cs:GUID_NULL.Data4
0x180051717  test    rax, rax
0x18005171a  jnz     short loc_18005176B
0x18005171c  mov     rbx, [rsp+3C8h+hkGuid]
0x180051721  mov     ecx, [rdi+10h]
0x180051724  test    ecx, ecx
0x180051726  jz      loc_18005185C
0x18005172c  sub     ecx, r12d
0x18005172f  jz      loc_180051823
0x180051735  sub     ecx, r12d
0x180051738  jz      loc_18005181A
0x18005173e  cmp     ecx, 2
0x180051741  jz      loc_1800517F9
0x180051747  mov     [rsp+3C8h+var_34C], 80070057h
0x18005174f  lea     rdx, $LN51
0x180051756  mov     this, [rsp+3C8h+var_388]
0x18005175b  call    _local_unwind_0
0x180051760  nop
0x180051761  mov     eax, 80070057h
0x180051766  jmp     $LN37
0x18005176b  lea     rdx, [rsp+3C8h+szAppId]; pstrGuid
0x180051773  mov     this, r14; rGuid
0x180051776  call    GetGuidString
0x18005177b  lea     r8, [rsp+3C8h+szAppId]; i_szVal
0x180051783  lea     rdx, ?AppID@Constants@Catalog@Com@@3QBGB; i_szName
0x18005178a  mov     rbx, [rsp+3C8h+hkGuid]
0x18005178f  mov     this, rbx; i_hKey
0x180051792  call    SetValue
0x180051797  xorps   xmm0, xmm0
0x18005179a  xor     eax, eax
0x18005179c  movups  xmmword ptr [rsp+3C8h+a.appid.Data1], xmm0
0x1800517a4  movups  xmmword ptr [rsp+3C8h+a.appName], xmm0
0x1800517ac  mov     [rsp+3C8h+a.hModuleSurrogate], rax
0x1800517b4  movups  xmm0, xmmword ptr [r14]
0x1800517b8  movdqu  xmmword ptr [rsp+3C8h+a.appid.Data1], xmm0
0x1800517c1  lea     this, [rsp+3C8h+a]; this
0x1800517c9  call    ?Register@AppRegistration@@QEAAJXZ; AppRegistration::Register(void)
0x1800517ce  mov     dword ptr [rsp+3C8h+pITypeLib], eax
0x1800517d2  test    eax, eax
0x1800517d4  jz      loc_180051721
0x1800517da  mov     [rsp+3C8h+var_350], eax
0x1800517de  lea     rdx, $LN50
0x1800517e5  mov     this, [rsp+3C8h+var_388]
0x1800517ea  call    _local_unwind_0
0x1800517ef  nop
0x1800517f0  mov     eax, dword ptr [rsp+3C8h+pITypeLib]
0x1800517f4  jmp     $LN37
0x1800517f9  lea     rdx, ?LocalServer32@Constants@Catalog@Com@@3QBGB; i_szKey
0x180051800  lea     r8, [rsp+3C8h+szModuleName]; i_szVal
0x180051808  xor     r9d, r9d; o_phkOut
0x18005180b  mov     dword ptr [rsp+3C8h+phkResult], r15d; fForceKeyCreation
0x180051810  mov     this, rbx; i_hKey
0x180051813  call    SetKeyAndValue
0x180051818  jmp     short loc_18005185C
0x18005181a  lea     rdx, ?InprocHandler32@Constants@Catalog@Com@@3QBGB; ushort const near * const Com::Catalog::Constants::InprocHandler32
0x180051821  jmp     short loc_180051800
0x180051823  mov     dword ptr [rsp+3C8h+phkResult], r15d; fForceKeyCreation
0x180051828  lea     r9, [rsp+3C8h+hkInproc]; o_phkOut
0x18005182d  lea     r8, [rsp+3C8h+szModuleName]; i_szVal
0x180051835  lea     rdx, ?InprocServer32@Constants@Catalog@Com@@3QBGB; i_szKey
0x18005183c  mov     this, rbx; i_hKey
0x18005183f  call    SetKeyAndValue
0x180051844  mov     r8, [rdi+38h]; i_szVal
0x180051848  lea     rdx, ?ThreadingModel@Constants@Catalog@Com@@3QBGB; i_szName
0x18005184f  mov     rsi, [rsp+3C8h+hkInproc]
0x180051854  mov     this, rsi; i_hKey
0x180051857  call    SetValue
0x18005185c  mov     dword ptr [rsp+3C8h+phkResult], r15d; fForceKeyCreation
0x180051861  xor     r9d, r9d; o_phkOut
0x180051864  mov     r8, [rdi+28h]; i_szVal
0x180051868  lea     rdx, ?ProgID@Constants@Catalog@Com@@3QBGB; i_szKey
0x18005186f  mov     this, rbx; i_hKey
0x180051872  call    SetKeyAndValue
0x180051877  mov     dword ptr [rsp+3C8h+phkResult], r15d; fForceKeyCreation
0x18005187c  xor     r9d, r9d; o_phkOut
0x18005187f  mov     r8, [rdi+30h]; i_szVal
0x180051883  lea     rdx, ?VersionIndependentProgID@Constants@Catalog@Com@@3QBGB; i_szKey
0x18005188a  mov     this, rbx; i_hKey
0x18005188d  call    SetKeyAndValue
0x180051892  mov     this, rbx; hKey
0x180051895  call    cs:__imp_RegCloseKey
0x18005189b  mov     [rsp+3C8h+hkGuid], r15
0x1800518a0  mov     dword ptr [rsp+3C8h+phkResult], r15d; fForceKeyCreation
0x1800518a5  lea     r9, [rsp+3C8h+hkProgID]; o_phkOut
0x1800518aa  mov     r8, [rdi+20h]; i_szVal
0x1800518ae  mov     rdx, [rdi+28h]; i_szKey
0x1800518b2  mov     rbx, 0FFFFFFFF80000000h
0x1800518b9  mov     this, rbx; i_hKey
0x1800518bc  call    SetKeyAndValue
0x1800518c1  mov     dword ptr [rsp+3C8h+phkResult], r15d; fForceKeyCreation
0x1800518c6  xor     r9d, r9d; o_phkOut
0x1800518c9  lea     r8, [rsp+3C8h+szClsid]; i_szVal
0x1800518d1  lea     rdx, ?CLSID@Constants@Catalog@Com@@3QBGB; i_szKey
0x1800518d8  mov     this, [rsp+3C8h+hkProgID]; i_hKey
0x1800518dd  call    SetKeyAndValue
0x1800518e2  mov     this, [rsp+3C8h+hkProgID]; hKey
0x1800518e7  call    cs:__imp_RegCloseKey
0x1800518ed  mov     [rsp+3C8h+hkProgID], r15
0x1800518f2  mov     dword ptr [rsp+3C8h+phkResult], r15d; fForceKeyCreation
0x1800518f7  lea     r9, [rsp+3C8h+hkProgID]; o_phkOut
0x1800518fc  mov     r8, [rdi+20h]; i_szVal
0x180051900  mov     rdx, [rdi+30h]; i_szKey
0x180051904  mov     this, rbx; i_hKey
0x180051907  call    SetKeyAndValue
0x18005190c  mov     dword ptr [rsp+3C8h+phkResult], r15d; fForceKeyCreation
0x180051911  xor     r9d, r9d; o_phkOut
0x180051914  lea     r8, [rsp+3C8h+szClsid]; i_szVal
0x18005191c  lea     rdx, ?CLSID@Constants@Catalog@Com@@3QBGB; i_szKey
0x180051923  mov     rbx, [rsp+3C8h+hkProgID]
0x180051928  mov     this, rbx; i_hKey
0x18005192b  call    SetKeyAndValue
0x180051930  mov     dword ptr [rsp+3C8h+phkResult], r15d; fForceKeyCreation
0x180051935  xor     r9d, r9d; o_phkOut
0x180051938  mov     r8, [rdi+28h]; i_szVal
0x18005193c  lea     rdx, ?CurVer@Constants@Catalog@Com@@3QBGB; i_szKey
0x180051943  mov     this, rbx; i_hKey
0x180051946  call    SetKeyAndValue
0x18005194b  mov     this, rbx; hKey
0x18005194e  call    cs:__imp_RegCloseKey
0x180051954  mov     [rsp+3C8h+hkProgID], r15
0x180051959  lea     this, aOleaut32; "OLEAUT32"
0x180051960  call    cs:__imp_LoadLibraryA
0x180051966  mov     rbx, rax
0x180051969  mov     [rsp+3C8h+hOleAut], rax
0x180051971  test    rax, rax
0x180051974  jz      loc_180051A32
0x18005197a  lea     rdx, aLoadtypelibex; "LoadTypeLibEx"
0x180051981  mov     this, rax; hModule
0x180051984  call    cs:__imp_GetProcAddress
0x18005198a  test    rax, rax
0x18005198d  jz      short loc_1800519F4
0x18005198f  mov     [rsp+3C8h+pITypeLib], r15
0x180051994  lea     r8, [rsp+3C8h+pITypeLib]
0x180051999  mov     edx, r12d
0x18005199c  lea     this, [rsp+3C8h+szModuleName]
0x1800519a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800519a9  test    eax, eax
0x1800519ab  js      short loc_1800519C5
0x1800519ad  mov     this, [rsp+3C8h+pITypeLib]
0x1800519b2  mov     rax, [this]
0x1800519b5  mov     rax, [rax+10h]
0x1800519b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800519be  mov     [rsp+3C8h+pITypeLib], r15
0x1800519c3  jmp     short $LN55
0x1800519c5  cmp     eax, 80029C4Ah
0x1800519ca  jz      short $LN55
0x1800519cc  mov     [rsp+3C8h+var_348], 80040200h
0x1800519d7  lea     rdx, $LN56
0x1800519de  mov     this, [rsp+3C8h+var_388]
0x1800519e3  call    _local_unwind_0
0x1800519e8  nop
0x1800519e9  nop
0x1800519ea  mov     eax, 80040200h
0x1800519ef  jmp     $LN37
0x1800519f4  call    cs:__imp_GetLastError
0x1800519fa  test    eax, eax
0x1800519fc  jle     short loc_180051A06
0x1800519fe  movzx   eax, ax
0x180051a01  or      eax, 80070000h
0x180051a06  cdqe
0x180051a08  mov     [rsp+3C8h+Arguments], rax
0x180051a10  lea     r9, [rsp+3C8h+Arguments]; lpArguments
0x180051a18  mov     r8d, r12d; nNumberOfArguments
0x180051a1b  mov     edx, r12d; dwExceptionFlags
0x180051a1e  xor     ecx, ecx; dwExceptionCode
0x180051a20  call    cs:__imp_RaiseException
0x180051a26  nop
0x180051a27  mov     this, rbx; hLibModule
0x180051a2a  call    cs:__imp_FreeLibrary
0x180051a30  jmp     short $LN41
0x180051a32  call    cs:__imp_GetLastError
0x180051a38  test    eax, eax
0x180051a3a  jle     short loc_180051A44
0x180051a3c  movzx   eax, ax
0x180051a3f  or      eax, 80070000h
0x180051a44  cdqe
0x180051a46  mov     [rsp+3C8h+var_330], rax
0x180051a4e  lea     r9, [rsp+3C8h+var_330]; lpArguments
0x180051a56  mov     r8d, r12d; nNumberOfArguments
0x180051a59  mov     edx, r12d; dwExceptionFlags
0x180051a5c  xor     ecx, ecx; dwExceptionCode
0x180051a5e  call    cs:__imp_RaiseException
0x180051a64  nop
0x180051a65  mov     this, [rsp+3C8h+hkCLSID]; hKey
0x180051a6a  test    this, this
0x180051a6d  jz      short loc_180051A75
0x180051a6f  call    cs:__imp_RegCloseKey
0x180051a75  test    rsi, rsi
0x180051a78  jz      short loc_180051A83
0x180051a7a  mov     this, rsi; hKey
0x180051a7d  call    cs:__imp_RegCloseKey
0x180051a83  xor     eax, eax
0x180051a85  jmp     $LN37
0x180051a8a  mov     this, [rsp+3C8h+e]; e
0x180051a8f  call    HRESULTFrom
0x180051a94  mov     dword ptr [rsp+3C8h+pITypeLib], eax
0x180051a98  lea     rdx, $LN57
0x180051a9f  mov     this, [rsp+3C8h+var_388]
0x180051aa4  call    _local_unwind_0
0x180051aa9  nop
  ... truncated ...
```
