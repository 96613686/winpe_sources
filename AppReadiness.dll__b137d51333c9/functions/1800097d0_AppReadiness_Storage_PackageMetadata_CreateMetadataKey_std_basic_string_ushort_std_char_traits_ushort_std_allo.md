# AppReadiness::Storage::PackageMetadata::CreateMetadataKey(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ulong)

- ea: `0x1800097d0`
- end: `0x180009c24`
- name: `?CreateMetadataKey@PackageMetadata@Storage@AppReadiness@@AEAA?AV?$HandleT@URegistryHandleTraits@HandleTraits@Storage@AppReadiness@@@Wrappers@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z`
- size: `1108`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, const WCHAR *, REGSAM)`
- caller_count: `5`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007b70`
- `0x180008580`
- `0x180008800`
- `0x180008d7c`
- `0x18000a1a8`

## callees

- `0x1800097d0`
- `0x180009d60`
- `0x180009d80`
- `0x180009e10`
- `0x180027a4c`
- `0x18003e210`
- `0x18003ecb4`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000988a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800099ea`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180009aa9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000988a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800099ea`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180009aa9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000986b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800099cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009a8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000986b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800099cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009a8a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000994e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180009996`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000994e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180009996`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800098f1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009a00`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800098f1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009a00`

## string_xrefs

- `0x180009acd`: `onecoreuap\shell\appreadiness\src\core\packagemetadata.cpp`
- `0x180009b1f`: `onecoreuap\shell\appreadiness\src\core\packagemetadata.cpp`
- `0x180009b6c`: `onecoreuap\shell\appreadiness\src\core\packagemetadata.cpp`
- `0x180009bac`: `onecoreuap\shell\appreadiness\src\core\packagemetadata.cpp`
- `0x180009bec`: `onecoreuap\shell\appreadiness\src\core\packagemetadata.cpp`
- `0x180009ad9`: `AppReadiness::Storage::PackageMetadata::CreateMetadataKey`
- `0x180009b2b`: `AppReadiness::Storage::PackageMetadata::CreateMetadataKey`
- `0x180009b78`: `AppReadiness::Storage::PackageMetadata::CreateMetadataKey`
- `0x180009bb8`: `AppReadiness::Storage::PackageMetadata::CreateMetadataKey`
- `0x180009bf8`: `AppReadiness::Storage::PackageMetadata::CreateMetadataKey`
- `0x180009bff`: `RegCreateKeyEx(packageKey.Get(), c_MetadataStoreKeyName, 0, nullptr, REG_OPTION_VOLATILE, access, nullptr, key.GetAddressOf(), nullptr)`
- `0x180009bbf`: `RegCreateKeyEx(m_queueRootKey.Get(), packageFamilyName.c_str(), 0, nullptr, 0, KEY_CREATE_SUB_KEY, nullptr, packageKey.GetAddressOf(), nullptr)`

## pseudocode

```c
_QWORD *__fastcall AppReadiness::Storage::PackageMetadata::CreateMetadataKey(
        __int64 a1,
        _QWORD *a2,
        const WCHAR *a3,
        REGSAM a4)
{
  HKEY *phkResult; // r13
  _QWORD *v9; // rdi
  int LastError; // eax
  __int64 *v11; // r9
  int v12; // eax
  HKEY v13; // rcx
  LSTATUS v14; // eax
  unsigned int v15; // edx
  int v16; // eax
  bool v17; // sf
  int Key; // eax
  bool v19; // sf
  int v20; // eax
  int v21; // eax
  int v23; // eax
  bool v24; // sf
  bool v25; // sf
  void **v26; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  int v28; // [rsp+60h] [rbp-A0h]
  _BYTE pExceptionObject[40]; // [rsp+68h] [rbp-98h] BYREF
  _QWORD *v30; // [rsp+90h] [rbp-70h]
  WCHAR SubKey[264]; // [rsp+A0h] [rbp-60h] BYREF

  v30 = a2;
  *a2 = &Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::`vftable';
  phkResult = (HKEY *)(a2 + 1);
  a2[1] = 0;
  v28 = 1;
  if ( !*(_QWORD *)(a1 + 16) )
  {
    v9 = AppReadiness::Storage::PackageList::OpenUserQueueRoot(&v26, *(_QWORD *)a1, 0xF003Fu);
    if ( *(_QWORD *)(a1 + 16) )
    {
      if ( !(**(unsigned __int8 (__fastcall ***)(__int64))(a1 + 8))(a1 + 8) )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        RaiseException(LastError, 1u, 0, 0);
        __debugbreak();
      }
      *(_QWORD *)(a1 + 16) = 0;
    }
    *(_QWORD *)(a1 + 16) = v9[1];
    v9[1] = 0;
    v26 = &Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::`vftable';
    if ( hKey
      && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::InternalClose(&v26) )
    {
      v23 = GetLastError();
      if ( v23 > 0 )
        v23 = (unsigned __int16)v23 | 0x80070000;
      RaiseException(v23, 1u, 0, 0);
      __debugbreak();
    }
  }
  if ( *((_QWORD *)a3 + 3) <= 7u )
    v11 = (__int64 *)a3;
  else
    v11 = *(__int64 **)a3;
  v12 = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", v11, L"Metadata");
  if ( v12 < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)pExceptionObject,
      v12,
      "StringCchPrintf(subKeyName, _countof(subKeyName), L\"%s\\\\%s\", packageFamilyName.c_str(), c_MetadataStoreKeyName)",
      "AppReadiness::Storage::PackageMetadata::CreateMetadataKey",
      "onecoreuap\\shell\\appreadiness\\src\\core\\packagemetadata.cpp",
      47);
    throw (Windows::HResultException *)pExceptionObject;
  }
  v13 = *(HKEY *)(a1 + 16);
  if ( v13 )
  {
    if ( (a4 & 0x20006) != 0 )
    {
      v14 = RegOpenKeyExW(v13, SubKey, 0, a4, phkResult);
      v15 = v14;
      if ( v14 )
      {
        if ( (unsigned int)(v14 - 2) > 1 )
        {
          v24 = v14 < 0;
          if ( v14 > 0 )
          {
            v15 = (unsigned __int16)v14 | 0x80070000;
            v24 = 1;
          }
          if ( v24 )
          {
            Windows::HResultException::HResultException(
              (Windows::HResultException *)pExceptionObject,
              v15,
              "result",
              "AppReadiness::Storage::PackageMetadata::CreateMetadataKey",
              "onecoreuap\\shell\\appreadiness\\src\\core\\packagemetadata.cpp",
              62);
            throw (Windows::HResultException *)pExceptionObject;
          }
        }
        else
        {
          v26 = &Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::`vftable';
          hKey = 0;
          if ( *((_QWORD *)a3 + 3) > 7u )
            a3 = *(const WCHAR **)a3;
          v16 = RegCreateKeyExW(*(HKEY *)(a1 + 16), a3, 0, 0, 0, 4u, 0, &hKey, 0);
          v17 = v16 < 0;
          if ( v16 > 0 )
          {
            v16 = (unsigned __int16)v16 | 0x80070000;
            v17 = v16 < 0;
          }
          if ( v17 )
          {
            Windows::HResultException::HResultException(
              (Windows::HResultException *)pExceptionObject,
              v16,
              "RegCreateKeyEx(m_queueRootKey.Get(), packageFamilyName.c_str(), 0, nullptr, 0, KEY_CREATE_SUB_KEY, nullptr"
              ", packageKey.GetAddressOf(), nullptr)",
              "AppReadiness::Storage::PackageMetadata::CreateMetadataKey",
              "onecoreuap\\shell\\appreadiness\\src\\core\\packagemetadata.cpp",
              57);
            throw (Windows::HResultException *)pExceptionObject;
          }
          Key = RegCreateKeyExW(hKey, L"Metadata", 0, 0, 1u, a4, 0, phkResult, 0);
          v19 = Key < 0;
          if ( Key > 0 )
          {
            Key = (unsigned __int16)Key | 0x80070000;
            v19 = Key < 0;
          }
          if ( v19 )
          {
            Windows::HResultException::HResultException(
              (Windows::HResultException *)pExceptionObject,
              Key,
              "RegCreateKeyEx(packageKey.Get(), c_MetadataStoreKeyName, 0, nullptr, REG_OPTION_VOLATILE, access, nullptr,"
              " key.GetAddressOf(), nullptr)",
              "AppReadiness::Storage::PackageMetadata::CreateMetadataKey",
              "onecoreuap\\shell\\appreadiness\\src\\core\\packagemetadata.cpp",
              58);
            throw (Windows::HResultException *)pExceptionObject;
          }
          v26 = &Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::`vftable';
          if ( hKey
            && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::InternalClose(&v26) )
          {
            v20 = GetLastError();
            if ( v20 > 0 )
              v20 = (unsigned __int16)v20 | 0x80070000;
            RaiseException(v20, 1u, 0, 0);
            __debugbreak();
          }
        }
      }
    }
    else if ( (a4 & 0x20019) != 0 )
    {
      v21 = RegOpenKeyExW(v13, SubKey, 0, a4, phkResult);
      if ( (v21 & 0xFFFFFFFC) != 0 || v21 == 1 )
      {
        v25 = v21 < 0;
        if ( v21 > 0 )
        {
          v21 = (unsigned __int16)v21 | 0x80070000;
          v25 = v21 < 0;
        }
        if ( v25 )
        {
          Windows::HResultException::HResultException(
            (Windows::HResultException *)pExceptionObject,
            v21,
            "result",
            "AppReadiness::Storage::PackageMetadata::CreateMetadataKey",
            "onecoreuap\\shell\\appreadiness\\src\\core\\packagemetadata.cpp",
            72);
          throw (Windows::HResultException *)pExceptionObject;
        }
      }
    }
  }
  return a2;
}

```

## disassembly

```asm
0x1800097d0  push    rbp
0x1800097d2  push    rbx
0x1800097d3  push    rsi
0x1800097d4  push    rdi
0x1800097d5  push    r12
0x1800097d7  push    r13
0x1800097d9  push    r14
0x1800097db  push    r15
0x1800097dd  lea     rbp, [rsp-1C8h]
0x1800097e5  sub     rsp, 2C8h
0x1800097ec  mov     rax, cs:__security_cookie
0x1800097f3  xor     rax, rsp
0x1800097f6  mov     [rbp+200h+var_50], rax
0x1800097fd  mov     r12d, r9d
0x180009800  mov     r15, r8
0x180009803  mov     rsi, rdx
0x180009806  mov     r14, rcx
0x180009809  mov     [rbp+200h+var_270], rdx
0x18000980d  xor     ebx, ebx
0x18000980f  mov     [rsp+300h+var_2A0], ebx
0x180009813  lea     rdi, ??_7?$HandleT@URegistryHandleTraits@HandleTraits@Storage@AppReadiness@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::`vftable'
0x18000981a  mov     [rdx], rdi
0x18000981d  lea     r13, [rdx+8]
0x180009821  mov     [r13+0], rbx
0x180009825  mov     [rsp+300h+var_2A0], 1
0x18000982d  cmp     [rcx+10h], rbx
0x180009831  jnz     short loc_180009891
0x180009833  mov     r8d, 0F003Fh
0x180009839  mov     rdx, [rcx]
0x18000983c  lea     rcx, [rsp+300h+var_2B0]
0x180009841  call    ?OpenUserQueueRoot@PackageList@Storage@AppReadiness@@SA?AV?$HandleT@URegistryHandleTraits@HandleTraits@Storage@AppReadiness@@@Wrappers@WRL@Microsoft@@PEBVUser@3@K@Z; AppReadiness::Storage::PackageList::OpenUserQueueRoot(AppReadiness::User const *,ulong)
0x180009846  mov     rdi, rax
0x180009849  cmp     [r14+10h], rbx
0x18000984d  jz      loc_180009A53
0x180009853  mov     rax, [r14+8]
0x180009857  lea     rcx, [r14+8]
0x18000985b  mov     rax, [rax]
0x18000985e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009863  test    al, al
0x180009865  jnz     loc_180009B57
0x18000986b  call    cs:__imp_GetLastError
0x180009871  test    eax, eax
0x180009873  jle     short loc_18000987D
0x180009875  movzx   eax, ax
0x180009878  or      eax, 80070000h
0x18000987d  xor     r9d, r9d; lpArguments
0x180009880  xor     r8d, r8d; nNumberOfArguments
0x180009883  mov     edx, 1; dwExceptionFlags
0x180009888  mov     ecx, eax; dwExceptionCode
0x18000988a  call    cs:__imp_RaiseException
0x180009890  int     3; Trap to Debugger
0x180009891  cmp     qword ptr [r15+18h], 7
0x180009896  jbe     loc_180009A40
0x18000989c  mov     r9, [r15]
0x18000989f  lea     rax, aMetadata; "Metadata"
0x1800098a6  mov     [rsp+300h+phkResult], rax
0x1800098ab  lea     r8, aSS; "%s\\%s"
0x1800098b2  mov     edx, 104h; unsigned __int64
0x1800098b7  lea     rcx, [rbp+200h+SubKey]; unsigned __int16 *
0x1800098bb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800098c0  test    eax, eax
0x1800098c2  js      loc_180009B64
0x1800098c8  mov     rcx, [r14+10h]; hKey
0x1800098cc  test    rcx, rcx
0x1800098cf  jz      loc_180009A1A
0x1800098d5  test    r12d, 20006h
0x1800098dc  jz      loc_180009A48
0x1800098e2  mov     [rsp+300h+phkResult], r13; phkResult
0x1800098e7  mov     r9d, r12d; samDesired
0x1800098ea  xor     r8d, r8d; ulOptions
0x1800098ed  lea     rdx, [rbp+200h+SubKey]; lpSubKey
0x1800098f1  call    cs:__imp_RegOpenKeyExW
0x1800098f7  mov     edx, eax
0x1800098f9  test    eax, eax
0x1800098fb  jz      loc_180009A1A
0x180009901  add     eax, 0FFFFFFFEh
0x180009904  cmp     eax, 1
0x180009907  ja      loc_180009AB0
0x18000990d  mov     [rsp+300h+var_2B0], rdi
0x180009912  mov     [rsp+300h+hKey], rbx
0x180009917  cmp     qword ptr [r15+18h], 7
0x18000991c  jbe     short loc_180009921
0x18000991e  mov     r15, [r15]
0x180009921  mov     [rsp+300h+lpdwDisposition], rbx; lpdwDisposition
0x180009926  lea     rax, [rsp+300h+hKey]
0x18000992b  mov     [rsp+300h+var_2C8], rax; phkResult
0x180009930  mov     [rsp+300h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x180009935  mov     [rsp+300h+samDesired], 4; samDesired
0x18000993d  mov     dword ptr [rsp+300h+phkResult], ebx; dwOptions
0x180009941  xor     r9d, r9d; lpClass
0x180009944  xor     r8d, r8d; Reserved
0x180009947  mov     rdx, r15; lpSubKey
0x18000994a  mov     rcx, [r14+10h]; hKey
0x18000994e  call    cs:__imp_RegCreateKeyExW
0x180009954  test    eax, eax
0x180009956  jle     short loc_180009962
0x180009958  movzx   eax, ax
0x18000995b  or      eax, 80070000h
0x180009960  test    eax, eax
0x180009962  js      loc_180009BA4
0x180009968  mov     [rsp+300h+lpdwDisposition], rbx; lpdwDisposition
0x18000996d  mov     [rsp+300h+var_2C8], r13; phkResult
0x180009972  mov     [rsp+300h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x180009977  mov     [rsp+300h+samDesired], r12d; samDesired
0x18000997c  mov     dword ptr [rsp+300h+phkResult], 1; dwOptions
0x180009984  xor     r9d, r9d; lpClass
0x180009987  xor     r8d, r8d; Reserved
0x18000998a  lea     rdx, aMetadata; "Metadata"
0x180009991  mov     rcx, [rsp+300h+hKey]; hKey
0x180009996  call    cs:__imp_RegCreateKeyExW
0x18000999c  test    eax, eax
0x18000999e  jle     short loc_1800099AA
0x1800099a0  movzx   eax, ax
0x1800099a3  or      eax, 80070000h
0x1800099a8  test    eax, eax
0x1800099aa  js      loc_180009BE4
0x1800099b0  mov     [rsp+300h+var_2B0], rdi
0x1800099b5  cmp     [rsp+300h+hKey], 0
0x1800099bb  jz      short loc_180009A1A
0x1800099bd  lea     rcx, [rsp+300h+var_2B0]
0x1800099c2  call    ?InternalClose@?$HandleT@URegistryHandleTraits@HandleTraits@Storage@AppReadiness@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::InternalClose(void)
0x1800099c7  test    al, al
0x1800099c9  jnz     short loc_180009A1A
0x1800099cb  call    cs:__imp_GetLastError
0x1800099d1  test    eax, eax
0x1800099d3  jle     short loc_1800099DD
0x1800099d5  movzx   eax, ax
0x1800099d8  or      eax, 80070000h
0x1800099dd  xor     r9d, r9d; lpArguments
0x1800099e0  xor     r8d, r8d; nNumberOfArguments
0x1800099e3  mov     edx, 1; dwExceptionFlags
0x1800099e8  mov     ecx, eax; dwExceptionCode
0x1800099ea  call    cs:__imp_RaiseException
0x1800099f0  int     3; Trap to Debugger
0x1800099f1  mov     [rsp+300h+phkResult], r13; phkResult
0x1800099f6  mov     r9d, r12d; samDesired
0x1800099f9  xor     r8d, r8d; ulOptions
0x1800099fc  lea     rdx, [rbp+200h+SubKey]; lpSubKey
0x180009a00  call    cs:__imp_RegOpenKeyExW
0x180009a06  test    eax, 0FFFFFFFCh
0x180009a0b  jnz     loc_180009B03
0x180009a11  cmp     eax, 1
0x180009a14  jz      loc_180009B03
0x180009a1a  mov     rax, rsi
0x180009a1d  mov     rcx, [rbp+200h+var_50]
0x180009a24  xor     rcx, rsp; StackCookie
0x180009a27  call    __security_check_cookie
0x180009a2c  add     rsp, 2C8h
0x180009a33  pop     r15
0x180009a35  pop     r14
0x180009a37  pop     r13
0x180009a39  pop     r12
0x180009a3b  pop     rdi
0x180009a3c  pop     rsi
0x180009a3d  pop     rbx
0x180009a3e  pop     rbp
0x180009a3f  retn
0x180009a40  mov     r9, r15
0x180009a43  jmp     loc_18000989F
0x180009a48  test    r12d, 20019h
0x180009a4f  jnz     short loc_1800099F1
0x180009a51  jmp     short loc_180009A1A
0x180009a53  mov     rax, [rdi+8]
0x180009a57  mov     [r14+10h], rax
0x180009a5b  xor     ebx, ebx
0x180009a5d  mov     [rdi+8], rbx
0x180009a61  lea     rdi, ??_7?$HandleT@URegistryHandleTraits@HandleTraits@Storage@AppReadiness@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::`vftable'
0x180009a68  mov     [rsp+300h+var_2B0], rdi
0x180009a6d  cmp     [rsp+300h+hKey], rbx
0x180009a72  jz      loc_180009891
0x180009a78  lea     rcx, [rsp+300h+var_2B0]
0x180009a7d  call    ?InternalClose@?$HandleT@URegistryHandleTraits@HandleTraits@Storage@AppReadiness@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<AppReadiness::Storage::HandleTraits::RegistryHandleTraits>::InternalClose(void)
0x180009a82  test    al, al
0x180009a84  jnz     loc_180009891
0x180009a8a  call    cs:__imp_GetLastError
0x180009a90  test    eax, eax
0x180009a92  jle     short loc_180009A9C
0x180009a94  movzx   eax, ax
0x180009a97  or      eax, 80070000h
0x180009a9c  xor     r9d, r9d; lpArguments
0x180009a9f  xor     r8d, r8d; nNumberOfArguments
0x180009aa2  mov     edx, 1; dwExceptionFlags
0x180009aa7  mov     ecx, eax; dwExceptionCode
0x180009aa9  call    cs:__imp_RaiseException
0x180009aaf  int     3; Trap to Debugger
0x180009ab0  test    edx, edx
0x180009ab2  jle     short loc_180009ABF
0x180009ab4  movzx   edx, dx
0x180009ab7  or      edx, 80070000h; int
0x180009abd  test    edx, edx
0x180009abf  jns     loc_180009A1A
0x180009ac5  mov     [rsp+300h+samDesired], 3Eh ; '>'; int
0x180009acd  lea     rcx, aOnecoreuapShel_32; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180009ad4  mov     [rsp+300h+phkResult], rcx; char *
0x180009ad9  lea     r9, aAppreadinessSt_0; "AppReadiness::Storage::PackageMetadata:"...
0x180009ae0  lea     r8, aResult; "result"
0x180009ae7  lea     rcx, [rsp+300h+pExceptionObject]; this
0x180009aec  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180009af1  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180009af8  lea     rcx, [rsp+300h+pExceptionObject]; pExceptionObject
0x180009afd  call    _CxxThrowException_0
0x180009b03  test    eax, eax
0x180009b05  jle     short loc_180009B11
0x180009b07  movzx   eax, ax
0x180009b0a  or      eax, 80070000h
0x180009b0f  test    eax, eax
0x180009b11  jns     loc_180009A1A
0x180009b17  mov     [rsp+300h+samDesired], 48h ; 'H'; int
0x180009b1f  lea     rcx, aOnecoreuapShel_32; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180009b26  mov     [rsp+300h+phkResult], rcx; char *
0x180009b2b  lea     r9, aAppreadinessSt_0; "AppReadiness::Storage::PackageMetadata:"...
0x180009b32  lea     r8, aResult; "result"
0x180009b39  mov     edx, eax; int
0x180009b3b  lea     rcx, [rsp+300h+pExceptionObject]; this
0x180009b40  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180009b45  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180009b4c  lea     rcx, [rsp+300h+pExceptionObject]; pExceptionObject
0x180009b51  call    _CxxThrowException_0
0x180009b57  mov     qword ptr [r14+10h], 0
0x180009b5f  jmp     loc_180009A53
0x180009b64  mov     [rsp+300h+samDesired], 2Fh ; '/'; int
0x180009b6c  lea     rcx, aOnecoreuapShel_32; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180009b73  mov     [rsp+300h+phkResult], rcx; char *
0x180009b78  lea     r9, aAppreadinessSt_0; "AppReadiness::Storage::PackageMetadata:"...
0x180009b7f  lea     r8, aStringcchprint; "StringCchPrintf(subKeyName, _countof(su"...
0x180009b86  mov     edx, eax; int
0x180009b88  lea     rcx, [rsp+300h+pExceptionObject]; this
0x180009b8d  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180009b92  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180009b99  lea     rcx, [rsp+300h+pExceptionObject]; pExceptionObject
0x180009b9e  call    _CxxThrowException_0
0x180009ba4  mov     [rsp+300h+samDesired], 39h ; '9'; int
0x180009bac  lea     rcx, aOnecoreuapShel_32; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180009bb3  mov     [rsp+300h+phkResult], rcx; char *
0x180009bb8  lea     r9, aAppreadinessSt_0; "AppReadiness::Storage::PackageMetadata:"...
0x180009bbf  lea     r8, aRegcreatekeyex; "RegCreateKeyEx(m_queueRootKey.Get(), pa"...
0x180009bc6  mov     edx, eax; int
0x180009bc8  lea     rcx, [rsp+300h+pExceptionObject]; this
0x180009bcd  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180009bd2  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180009bd9  lea     rcx, [rsp+300h+pExceptionObject]; pExceptionObject
0x180009bde  call    _CxxThrowException_0
0x180009be4  mov     [rsp+300h+samDesired], 3Ah ; ':'; int
0x180009bec  lea     rcx, aOnecoreuapShel_32; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180009bf3  mov     [rsp+300h+phkResult], rcx; char *
0x180009bf8  lea     r9, aAppreadinessSt_0; "AppReadiness::Storage::PackageMetadata:"...
0x180009bff  lea     r8, aRegcreatekeyex_1; "RegCreateKeyEx(packageKey.Get(), c_Meta"...
0x180009c06  mov     edx, eax; int
0x180009c08  lea     rcx, [rsp+300h+pExceptionObject]; this
0x180009c0d  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180009c12  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180009c19  lea     rcx, [rsp+300h+pExceptionObject]; pExceptionObject
0x180009c1e  call    _CxxThrowException_0
```
