# TcpipPlugin::SetLegacyKeys

- ea: `0x180018570`
- end: `0x180018a31`
- name: `TcpipPlugin::SetLegacyKeys`
- size: `1217`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18002ee80`

## callees

- `0x180005c94`
- `0x18000a430`
- `0x180015f50`
- `0x180017320`
- `0x180018570`
- `0x180027b38`
- `0x180040898`
- `0x180040930`
- `0x1800409c8`
- `0x180044324`
- `0x1800457b4`
- `0x18004a2d0`
- `0x18005097c`
- `0x1800582f0`
- `0x180065035`
- `0x18007c0e8`
- `0x18007c588`
- `0x18007c624`
- `0x18007c6b4`
- `0x1800810d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800186ed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018792`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018869`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018949`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018a01`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800186ed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018792`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018869`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018949`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018a01`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800186a5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800187d8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800188af`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001898f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800186a5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800187d8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800188af`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001898f`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
LSTATUS __fastcall TcpipPlugin::SetLegacyKeys(void **a1, __int64 a2, __int64 a3)
{
  bool Boolean; // r12
  LSTATUS result; // eax
  HKEY CurrentControlSetRegistryHandle; // rbx
  int v9; // eax
  signed int v10; // ebx
  HKEY v11; // r15
  HKEY v12; // r14
  int v13; // eax
  signed int v14; // eax
  HKEY v15; // r14
  int v16; // eax
  HKEY v17; // rbx
  int v18; // eax
  __int64 v19; // rcx
  __int64 v20; // [rsp+58h] [rbp-B0h] BYREF
  void **v21; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v22; // [rsp+68h] [rbp-A0h] BYREF
  int v23; // [rsp+70h] [rbp-98h]
  __int128 v24; // [rsp+74h] [rbp-94h]
  __int64 v25; // [rsp+88h] [rbp-80h]
  _BYTE pExceptionObject[208]; // [rsp+90h] [rbp-78h] BYREF
  GUID v27; // [rsp+160h] [rbp+58h] BYREF
  _BYTE v28[24]; // [rsp+178h] [rbp+70h] BYREF
  HKEY hKey; // [rsp+190h] [rbp+88h] BYREF
  WCHAR SubKey[264]; // [rsp+198h] [rbp+90h] BYREF

  v25 = -2;
  v21 = a1;
  v22 = 0;
  v23 = 9;
  v24 = 0;
  NetSetup2::ActiveObject::GetProperty(&v21, &v27, (__int128 *)&NETSETUPPKEY_Transaction_IsMigration, 0);
  Boolean = NetSetup2::Property::GetBoolean((NetSetup2::Property *)&v27);
  std::vector<_NETSETUPPROPKEY>::_Tidy(v28);
  std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(&v22);
  result = TcpipPlugin::GetTcpipVer(a3);
  if ( result )
  {
    if ( result == 1 && !Boolean )
    {
      v21 = a1;
      v22 = 0;
      v23 = 9;
      v24 = 0;
      CurrentControlSetRegistryHandle = NetSetup2::TransactionObject::get_CurrentControlSetRegistryHandle((NetSetup2::TransactionObject *)&v21);
      std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(&v22);
      TcpipPlugin::Getv6InterfacePathForAdapter(a2 + 20, SubKey);
      hKey = 0;
      v9 = RegCreateKeyExW(CurrentControlSetRegistryHandle, SubKey, 0, 0, 0, 2u, 0, &hKey, 0);
      if ( v9 )
      {
        if ( v9 > 0 )
          v9 = (unsigned __int16)v9 | 0x80070000;
        HResultException::HResultException((HResultException *)pExceptionObject, v9);
        throw (HResultException *)pExceptionObject;
      }
      v10 = TcpipPlugin::SetInterfaceDHCPConfigurationV1(a2, hKey);
      result = RegCloseKey(hKey);
      if ( v10 )
      {
        if ( v10 > 0 )
          v10 = (unsigned __int16)v10 | 0x80070000;
        HResultException::HResultException((HResultException *)pExceptionObject, v10);
        throw (HResultException *)pExceptionObject;
      }
    }
  }
  else
  {
    v21 = a1;
    v22 = 0;
    v23 = 9;
    v24 = 0;
    v11 = NetSetup2::TransactionObject::get_CurrentControlSetRegistryHandle((NetSetup2::TransactionObject *)&v21);
    std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(&v22);
    hKey = 0;
    if ( !Boolean )
    {
      TcpipPlugin::Getv4InterfacePathForAdapter(a2 + 20, SubKey);
      v12 = hKey;
      if ( hKey )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v20);
        RegCloseKey(v12);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v20);
      }
      hKey = 0;
      v13 = RegCreateKeyExW(v11, SubKey, 0, 0, 0, 2u, 0, &hKey, 0);
      if ( v13 )
      {
        if ( v13 > 0 )
          v13 = (unsigned __int16)v13 | 0x80070000;
        HResultException::HResultException((HResultException *)pExceptionObject, v13);
        throw (HResultException *)pExceptionObject;
      }
      v14 = TcpipPlugin::SetDefaultInterfaceParameters(a2, hKey);
      if ( v14 )
      {
        if ( v14 > 0 )
          v14 = (unsigned __int16)v14 | 0x80070000;
        HResultException::HResultException((HResultException *)pExceptionObject, v14);
        throw (HResultException *)pExceptionObject;
      }
    }
    TcpipPlugin::GetAdapterPathForAdapter(a2 + 20, SubKey);
    v15 = hKey;
    if ( hKey )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v20);
      RegCloseKey(v15);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v20);
    }
    hKey = 0;
    v16 = RegCreateKeyExW(v11, SubKey, 0, 0, 0, 2u, 0, &hKey, 0);
    if ( v16 )
    {
      if ( v16 > 0 )
        v16 = (unsigned __int16)v16 | 0x80070000;
      HResultException::HResultException((HResultException *)pExceptionObject, v16);
      throw (HResultException *)pExceptionObject;
    }
    result = TcpipPlugin::SetDefaultAdapterParameters(a2, hKey);
    if ( result )
    {
      if ( result > 0 )
        result = (unsigned __int16)result | 0x80070000;
      HResultException::HResultException((HResultException *)pExceptionObject, result);
      throw (HResultException *)pExceptionObject;
    }
    if ( !Boolean )
    {
      TcpipPlugin::GetNetBTInterfacePathForAdapter(a2 + 20, SubKey);
      v17 = hKey;
      if ( hKey )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v20);
        RegCloseKey(v17);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v20);
      }
      hKey = 0;
      v18 = RegCreateKeyExW(v11, SubKey, 0, 0, 0, 2u, 0, &hKey, 0);
      if ( v18 )
      {
        if ( v18 > 0 )
          v18 = (unsigned __int16)v18 | 0x80070000;
        HResultException::HResultException((HResultException *)pExceptionObject, v18);
        throw (HResultException *)pExceptionObject;
      }
      result = TcpipPlugin::SetDefaultNetBTParameters(v19, hKey);
      if ( result )
      {
        if ( result > 0 )
          result = (unsigned __int16)result | 0x80070000;
        HResultException::HResultException((HResultException *)pExceptionObject, result);
        throw (HResultException *)pExceptionObject;
      }
    }
    if ( hKey )
      return RegCloseKey(hKey);
  }
  return result;
}

```

## disassembly

```asm
0x180018570  mov     rax, rsp
0x180018573  push    rbp
0x180018574  push    rsi
0x180018575  push    rdi
0x180018576  push    r12
0x180018578  push    r13
0x18001857a  push    r14
0x18001857c  push    r15
0x18001857e  lea     rbp, [rax-2E8h]
0x180018585  sub     rsp, 3B0h
0x18001858c  mov     [rbp+2E0h+var_360], 0FFFFFFFFFFFFFFFEh
0x180018594  mov     [rax+8], rbx
0x180018598  mov     rax, cs:__security_cookie
0x18001859f  xor     rax, rsp
0x1800185a2  mov     [rbp+2E0h+var_40], rax
0x1800185a9  mov     rbx, r8
0x1800185ac  mov     rdi, rdx
0x1800185af  mov     rsi, rcx
0x1800185b2  xor     r13d, r13d
0x1800185b5  xorps   xmm0, xmm0
0x1800185b8  mov     [rsp+3E0h+var_388], rcx
0x1800185bd  mov     qword ptr [rsp+3E0h+var_380], r13
0x1800185c2  lea     r14d, [r13+9]
0x1800185c6  mov     dword ptr [rsp+3E0h+var_37C+4], r14d
0x1800185cb  movdqu  xmmword ptr [rsp+3E0h+var_37C+8], xmm0
0x1800185d1  xor     r9d, r9d
0x1800185d4  lea     r8, NETSETUPPKEY_Transaction_IsMigration; unsigned int
0x1800185db  lea     rdx, [rbp+2E0h+var_288]; struct _NETSETUPPROPKEY *
0x1800185df  lea     rcx, [rsp+3E0h+var_388]; this
0x1800185e4  call    ?GetProperty@ActiveObject@NetSetup2@@QEBA?AVProperty@2@AEBU_NETSETUPPROPKEY@@K@Z; NetSetup2::ActiveObject::GetProperty(_NETSETUPPROPKEY const &,ulong)
0x1800185e9  nop
0x1800185ea  lea     rcx, [rbp+2E0h+var_288]; this
0x1800185ee  call    ?GetBoolean@Property@NetSetup2@@QEBA_NXZ; NetSetup2::Property::GetBoolean(void)
0x1800185f3  mov     r12b, al
0x1800185f6  lea     rcx, [rbp+2E0h+var_270]
0x1800185fa  call    ?_Tidy@?$vector@U_NETSETUPPROPKEY@@V?$allocator@U_NETSETUPPROPKEY@@@std@@@std@@IEAAXXZ; std::vector<_NETSETUPPROPKEY>::_Tidy(void)
0x1800185ff  nop
0x180018600  lea     rcx, [rsp+3E0h+var_380]
0x180018605  call    ?_Delete@?$unique_ptr@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@U?$default_delete@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@@2@@std@@AEAAXXZ; std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(void)
0x18001860a  mov     rcx, rbx
0x18001860d  call    TcpipPlugin__GetTcpipVer
0x180018612  test    eax, eax
0x180018614  jz      loc_180018722
0x18001861a  cmp     eax, 1
0x18001861d  jnz     loc_180018A07
0x180018623  test    r12b, r12b
0x180018626  jnz     loc_180018A07
0x18001862c  xorps   xmm0, xmm0
0x18001862f  mov     [rsp+3E0h+var_388], rsi
0x180018634  mov     qword ptr [rsp+3E0h+var_380], r13
0x180018639  mov     dword ptr [rsp+3E0h+var_37C+4], r14d
0x18001863e  movdqu  xmmword ptr [rsp+3E0h+var_37C+8], xmm0
0x180018644  lea     rcx, [rsp+3E0h+var_388]; this
0x180018649  call    ?get_CurrentControlSetRegistryHandle@TransactionObject@NetSetup2@@QEBAPEAUHKEY__@@XZ; NetSetup2::TransactionObject::get_CurrentControlSetRegistryHandle(void)
0x18001864e  mov     rbx, rax
0x180018651  lea     rcx, [rsp+3E0h+var_380]
0x180018656  call    ?_Delete@?$unique_ptr@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@U?$default_delete@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@@2@@std@@AEAAXXZ; std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(void)
0x18001865b  lea     rcx, [rdi+14h]
0x18001865f  lea     rdx, [rbp+2E0h+SubKey]
0x180018666  call    TcpipPlugin__Getv6InterfacePathForAdapter
0x18001866b  mov     [rbp+2E0h+hKey], r13
0x180018672  mov     [rsp+40h], r13; lpdwDisposition
0x180018677  lea     rax, [rbp+2E0h+hKey]
0x18001867e  mov     [rsp+3E0h+phkResult], rax; phkResult
0x180018683  mov     [rsp+3E0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x180018688  mov     [rsp+3E0h+samDesired], 2; samDesired
0x180018690  mov     [rsp+3E0h+dwOptions], r13d; dwOptions
0x180018695  xor     r9d, r9d; lpClass
0x180018698  xor     r8d, r8d; Reserved
0x18001869b  lea     rdx, [rbp+2E0h+SubKey]; lpSubKey
0x1800186a2  mov     rcx, rbx; hKey
0x1800186a5  call    cs:__imp_RegCreateKeyExW
0x1800186ab  test    eax, eax
0x1800186ad  jz      short loc_1800186D5
0x1800186af  jle     short loc_1800186B9
0x1800186b1  movzx   eax, ax
0x1800186b4  or      eax, 80070000h
0x1800186b9  mov     edx, eax; int
0x1800186bb  lea     rcx, [rbp+2E0h+pExceptionObject]; this
0x1800186bf  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x1800186c4  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x1800186cb  lea     rcx, [rbp+2E0h+pExceptionObject]; pExceptionObject
0x1800186cf  call    _CxxThrowException_0
0x1800186d5  mov     rdx, [rbp+2E0h+hKey]
0x1800186dc  mov     rcx, rdi
0x1800186df  call    TcpipPlugin__SetInterfaceDHCPConfigurationV1
0x1800186e4  mov     ebx, eax
0x1800186e6  mov     rcx, [rbp+2E0h+hKey]; hKey
0x1800186ed  call    cs:__imp_RegCloseKey
0x1800186f3  test    ebx, ebx
0x1800186f5  jz      loc_180018A07
0x1800186fb  jle     short loc_180018706
0x1800186fd  movzx   ebx, bx
0x180018700  or      ebx, 80070000h
0x180018706  mov     edx, ebx; int
0x180018708  lea     rcx, [rbp+2E0h+pExceptionObject]; this
0x18001870c  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x180018711  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x180018718  lea     rcx, [rbp+2E0h+pExceptionObject]; pExceptionObject
0x18001871c  call    _CxxThrowException_0
0x180018722  xorps   xmm0, xmm0
0x180018725  mov     [rsp+3E0h+var_388], rsi
0x18001872a  mov     qword ptr [rsp+3E0h+var_380], r13
0x18001872f  mov     dword ptr [rsp+3E0h+var_37C+4], r14d
0x180018734  movdqu  xmmword ptr [rsp+3E0h+var_37C+8], xmm0
0x18001873a  lea     rcx, [rsp+3E0h+var_388]; this
0x18001873f  call    ?get_CurrentControlSetRegistryHandle@TransactionObject@NetSetup2@@QEBAPEAUHKEY__@@XZ; NetSetup2::TransactionObject::get_CurrentControlSetRegistryHandle(void)
0x180018744  mov     r15, rax
0x180018747  lea     rcx, [rsp+3E0h+var_380]
0x18001874c  call    ?_Delete@?$unique_ptr@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@U?$default_delete@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@@2@@std@@AEAAXXZ; std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(void)
0x180018751  mov     [rbp+2E0h+hKey], r13
0x180018758  lea     rbx, [rdi+14h]
0x18001875c  mov     esi, 2
0x180018761  test    r12b, r12b
0x180018764  jnz     loc_180018841
0x18001876a  lea     rdx, [rbp+2E0h+SubKey]
0x180018771  mov     rcx, rbx
0x180018774  call    TcpipPlugin__Getv4InterfacePathForAdapter
0x180018779  mov     r14, [rbp+2E0h+hKey]
0x180018780  test    r14, r14
0x180018783  jz      short loc_1800187A2
0x180018785  lea     rcx, [rsp+3E0h+var_390]; this
0x18001878a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001878f  mov     rcx, r14; hKey
0x180018792  call    cs:__imp_RegCloseKey
0x180018798  lea     rcx, [rsp+3E0h+var_390]; this
0x18001879d  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800187a2  mov     [rbp+2E0h+hKey], r13
0x1800187a9  mov     [rsp+40h], r13; lpdwDisposition
0x1800187ae  lea     rax, [rbp+2E0h+hKey]
0x1800187b5  mov     [rsp+3E0h+phkResult], rax; phkResult
0x1800187ba  mov     [rsp+3E0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x1800187bf  mov     [rsp+3E0h+samDesired], esi; samDesired
0x1800187c3  mov     [rsp+3E0h+dwOptions], r13d; dwOptions
0x1800187c8  xor     r9d, r9d; lpClass
0x1800187cb  xor     r8d, r8d; Reserved
0x1800187ce  lea     rdx, [rbp+2E0h+SubKey]; lpSubKey
0x1800187d5  mov     rcx, r15; hKey
0x1800187d8  call    cs:__imp_RegCreateKeyExW
0x1800187de  test    eax, eax
0x1800187e0  jz      short loc_180018808
0x1800187e2  jle     short loc_1800187EC
0x1800187e4  movzx   eax, ax
0x1800187e7  or      eax, 80070000h
0x1800187ec  mov     edx, eax; int
0x1800187ee  lea     rcx, [rbp+2E0h+pExceptionObject]; this
0x1800187f2  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x1800187f7  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x1800187fe  lea     rcx, [rbp+2E0h+pExceptionObject]; pExceptionObject
0x180018802  call    _CxxThrowException_0
0x180018808  mov     rdx, [rbp+2E0h+hKey]
0x18001880f  mov     rcx, rdi
0x180018812  call    TcpipPlugin__SetDefaultInterfaceParameters
0x180018817  test    eax, eax
0x180018819  jz      short loc_180018841
0x18001881b  jle     short loc_180018825
0x18001881d  movzx   eax, ax
0x180018820  or      eax, 80070000h
0x180018825  mov     edx, eax; int
0x180018827  lea     rcx, [rbp+2E0h+pExceptionObject]; this
0x18001882b  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x180018830  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x180018837  lea     rcx, [rbp+2E0h+pExceptionObject]; pExceptionObject
0x18001883b  call    _CxxThrowException_0
0x180018841  lea     rdx, [rbp+2E0h+SubKey]
0x180018848  mov     rcx, rbx
0x18001884b  call    TcpipPlugin__GetAdapterPathForAdapter
0x180018850  mov     r14, [rbp+2E0h+hKey]
0x180018857  test    r14, r14
0x18001885a  jz      short loc_180018879
0x18001885c  lea     rcx, [rsp+3E0h+var_390]; this
0x180018861  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180018866  mov     rcx, r14; hKey
0x180018869  call    cs:__imp_RegCloseKey
0x18001886f  lea     rcx, [rsp+3E0h+var_390]; this
0x180018874  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180018879  mov     [rbp+2E0h+hKey], r13
0x180018880  mov     [rsp+40h], r13; lpdwDisposition
0x180018885  lea     rax, [rbp+2E0h+hKey]
0x18001888c  mov     [rsp+3E0h+phkResult], rax; phkResult
0x180018891  mov     [rsp+3E0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x180018896  mov     [rsp+3E0h+samDesired], esi; samDesired
0x18001889a  mov     [rsp+3E0h+dwOptions], r13d; dwOptions
0x18001889f  xor     r9d, r9d; lpClass
0x1800188a2  xor     r8d, r8d; Reserved
0x1800188a5  lea     rdx, [rbp+2E0h+SubKey]; lpSubKey
0x1800188ac  mov     rcx, r15; hKey
0x1800188af  call    cs:__imp_RegCreateKeyExW
0x1800188b5  test    eax, eax
0x1800188b7  jz      short loc_1800188DF
0x1800188b9  jle     short loc_1800188C3
0x1800188bb  movzx   eax, ax
0x1800188be  or      eax, 80070000h
0x1800188c3  mov     edx, eax; int
0x1800188c5  lea     rcx, [rbp+2E0h+pExceptionObject]; this
0x1800188c9  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x1800188ce  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x1800188d5  lea     rcx, [rbp+2E0h+pExceptionObject]; pExceptionObject
0x1800188d9  call    _CxxThrowException_0
0x1800188df  mov     rdx, [rbp+2E0h+hKey]
0x1800188e6  mov     rcx, rdi
0x1800188e9  call    TcpipPlugin__SetDefaultAdapterParameters
0x1800188ee  test    eax, eax
0x1800188f0  jz      short loc_180018918
0x1800188f2  jle     short loc_1800188FC
0x1800188f4  movzx   eax, ax
0x1800188f7  or      eax, 80070000h
0x1800188fc  mov     edx, eax; int
0x1800188fe  lea     rcx, [rbp+2E0h+pExceptionObject]; this
0x180018902  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x180018907  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x18001890e  lea     rcx, [rbp+2E0h+pExceptionObject]; pExceptionObject
0x180018912  call    _CxxThrowException_0
0x180018918  test    r12b, r12b
0x18001891b  jnz     loc_1800189F5
0x180018921  lea     rdx, [rbp+2E0h+SubKey]
0x180018928  mov     rcx, rbx
0x18001892b  call    TcpipPlugin__GetNetBTInterfacePathForAdapter
0x180018930  mov     rbx, [rbp+2E0h+hKey]
0x180018937  test    rbx, rbx
0x18001893a  jz      short loc_180018959
0x18001893c  lea     rcx, [rsp+3E0h+var_390]; this
0x180018941  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180018946  mov     rcx, rbx; hKey
0x180018949  call    cs:__imp_RegCloseKey
0x18001894f  lea     rcx, [rsp+3E0h+var_390]; this
0x180018954  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180018959  mov     [rbp+2E0h+hKey], r13
0x180018960  mov     [rsp+40h], r13; lpdwDisposition
0x180018965  lea     rax, [rbp+2E0h+hKey]
0x18001896c  mov     [rsp+3E0h+phkResult], rax; phkResult
0x180018971  mov     [rsp+3E0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x180018976  mov     [rsp+3E0h+samDesired], esi; samDesired
0x18001897a  mov     [rsp+3E0h+dwOptions], r13d; dwOptions
0x18001897f  xor     r9d, r9d; lpClass
0x180018982  xor     r8d, r8d; Reserved
0x180018985  lea     rdx, [rbp+2E0h+SubKey]; lpSubKey
0x18001898c  mov     rcx, r15; hKey
0x18001898f  call    cs:__imp_RegCreateKeyExW
0x180018995  test    eax, eax
0x180018997  jz      short loc_1800189BF
0x180018999  jle     short loc_1800189A3
0x18001899b  movzx   eax, ax
0x18001899e  or      eax, 80070000h
0x1800189a3  mov     edx, eax; int
0x1800189a5  lea     rcx, [rbp+2E0h+pExceptionObject]; this
0x1800189a9  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x1800189ae  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x1800189b5  lea     rcx, [rbp+2E0h+pExceptionObject]; pExceptionObject
0x1800189b9  call    _CxxThrowException_0
0x1800189bf  mov     rdx, [rbp+2E0h+hKey]
0x1800189c6  call    TcpipPlugin__SetDefaultNetBTParameters
0x1800189cb  test    eax, eax
0x1800189cd  jz      short loc_1800189F5
0x1800189cf  jle     short loc_1800189D9
0x1800189d1  movzx   eax, ax
0x1800189d4  or      eax, 80070000h
0x1800189d9  mov     edx, eax; int
0x1800189db  lea     rcx, [rbp+2E0h+pExceptionObject]; this
0x1800189df  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x1800189e4  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x1800189eb  lea     rcx, [rbp+2E0h+pExceptionObject]; pExceptionObject
0x1800189ef  call    _CxxThrowException_0
0x1800189f5  mov     rcx, [rbp+2E0h+hKey]; hKey
0x1800189fc  test    rcx, rcx
0x1800189ff  jz      short loc_180018A07
0x180018a01  call    cs:__imp_RegCloseKey
0x180018a07  mov     rcx, [rbp+2E0h+var_40]
0x180018a0e  xor     rcx, rsp; StackCookie
0x180018a11  call    __security_check_cookie
0x180018a16  mov     rbx, [rsp+3E0h+arg_0]
0x180018a1e  add     rsp, 3B0h
0x180018a25  pop     r15
0x180018a27  pop     r14
0x180018a29  pop     r13
0x180018a2b  pop     r12
0x180018a2d  pop     rdi
0x180018a2e  pop     rsi
0x180018a2f  pop     rbp
0x180018a30  retn
```
