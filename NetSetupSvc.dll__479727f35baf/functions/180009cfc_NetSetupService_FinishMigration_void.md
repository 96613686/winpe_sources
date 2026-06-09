# NetSetupService::FinishMigration(void)

- ea: `0x180009cfc`
- end: `0x18000a160`
- name: `?FinishMigration@NetSetupService@@AEAAXXZ`
- size: `1124`
- prototype: `void __fastcall(NetSetupService *__hidden this)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000a6d4`

## callees

- `0x1800027c0`
- `0x1800032e4`
- `0x1800078d0`
- `0x1800078f8`
- `0x180008854`
- `0x180008e00`
- `0x180008e3c`
- `0x180009cfc`
- `0x18000d384`
- `0x18000d8ec`
- `0x18000d954`
- `0x18000d9b4`
- `0x18000df60`
- `0x18000fd7c`
- `0x180026958`
- `0x180026a10`
- `0x180027560`
- `0x1800275e4`
- `0x180027d2c`
- `0x1800283fc`
- `0x1800285cc`
- `0x1800286d8`
- `0x180031010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180009e4c`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180009e4c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180009f01`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180009f01`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009f20`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009f20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f53`
- `RPCRT4!UuidCreate` at `0x180009fd5`
- `RPCRT4!UuidCreate` at `0x180009fd5`

## string_xrefs

- `0x180009d9a`: `MigrationComplete`
- `0x180009ddb`: `MigrationComplete`
- `0x18000a053`: `MigrationComplete`
- `0x180009df7`: `System\CurrentControlSet\Control\NetworkSetup2\Plugins\Migration`

## pseudocode

```c
void __fastcall NetSetupService::FinishMigration(NetSetupService *this)
{
  bool v2; // bl
  char ValueBoolean; // bl
  unsigned int ValueDword; // eax
  __int64 v5; // rsi
  __int64 v6; // r8
  const wchar_t *v7; // rax
  wchar_t v8; // dx
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rax
  __int64 v12; // r10
  __int64 v13; // rax
  __int64 v14; // r10
  const WCHAR *v15; // rax
  HMODULE Library; // rax
  FARPROC ProcAddress; // r14
  signed int LastError; // eax
  int v19; // eax
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  std::_Ref_count_base *v22; // rbx
  _BYTE pExceptionObject[208]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v24[8]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v25[8]; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v26[8]; // [rsp+120h] [rbp+20h] BYREF
  HMODULE v27; // [rsp+128h] [rbp+28h] BYREF
  _QWORD v28[3]; // [rsp+130h] [rbp+30h] BYREF
  _QWORD *v29; // [rsp+148h] [rbp+48h] BYREF
  std::_Ref_count_base *v30; // [rsp+150h] [rbp+50h]
  _BYTE v31[40]; // [rsp+158h] [rbp+58h] BYREF
  _OWORD v32[4]; // [rsp+180h] [rbp+80h] BYREF
  UUID Uuid; // [rsp+1C0h] [rbp+C0h] BYREF

  RegistryKey::RegistryKey((RegistryKey *)v25, HKEY_LOCAL_MACHINE);
  v2 = *(_QWORD *)RegistryKey::TryOpenSubKey(v25, v26, L"SYSTEM\\Setup\\Upgrade\\NetworkDriverBackup", 1, 0) == 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v26);
  if ( !v2 )
  {
    RegistryKey::CreateSubKey(v25, v24, L"System\\CurrentControlSet\\Control\\NetworkSetup2\\State", 3, 0);
    ValueBoolean = RegistryKey::GetValueBoolean(v24, L"MigrationComplete");
    ValueDword = RegistryKey::GetValueDword(v24, L"MigrationFailureCount", 0, 1);
    LODWORD(v5) = ValueDword;
    if ( ValueBoolean || ValueDword >= 5 )
      goto LABEL_39;
    RegistryKey::SetValue(v24, L"MigrationComplete", 1, 0);
    RegistryKey::CreateSubKey(v25, v26, L"System\\CurrentControlSet\\Control\\NetworkSetup2\\Plugins\\Migration", 1, 0);
    if ( !RegistryKey::ValueExists((RegistryKey *)v26, L"Module") )
    {
LABEL_38:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v26);
LABEL_39:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v24);
      goto LABEL_40;
    }
    RegistryKey::GetValueString(v26, v31, L"Module", 0);
    v7 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v31, 92, v6);
    if ( wcschr(v7, v8) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v11 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v31, v9, v10);
        WPP_SF_S(*(_QWORD *)(v12 + 16), 23, WPP_284c2e15fd5e36fcf548f5e5b86dc764_Traceguids, v11);
      }
      HResultException::HResultException((HResultException *)pExceptionObject, -2147024891);
      throw (HResultException *)pExceptionObject;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v13 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v31, v9, v10);
      WPP_SF_S(*(_QWORD *)(v14 + 16), 24, WPP_284c2e15fd5e36fcf548f5e5b86dc764_Traceguids, v13);
    }
    v15 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v31, v9, v10);
    Library = LoadLibraryExW(v15, 0, 0x800u);
    if ( !Library )
      Win32Exception::ThrowLastError();
    v27 = Library;
    ProcAddress = GetProcAddress(Library, "NetworkBindingEngineFinishMigration");
    if ( !ProcAddress )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_284c2e15fd5e36fcf548f5e5b86dc764_Traceguids);
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      HResultException::HResultException((HResultException *)pExceptionObject, LastError);
      throw (HResultException *)pExceptionObject;
    }
    v32[0] = *((_OWORD *)this + 19);
    v32[1] = *((_OWORD *)this + 20);
    v32[2] = *((_OWORD *)this + 21);
    v32[3] = *((_OWORD *)this + 22);
    Uuid = (UUID)*((_OWORD *)this + 23);
    UuidCreate(&Uuid);
    v28[0] = 9;
    v28[2] = 0;
    v28[1] = v32;
    NetSetupSvcTransactionCoordinator::CreateNewTransaction(
      (NetSetupService *)((char *)g_NetSetupService + 32),
      &v29,
      &Uuid,
      (__int64)v28);
    v19 = ((__int64 (__fastcall *)(_QWORD))ProcAddress)(*v29);
    if ( v19 < 0 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        26,
        WPP_284c2e15fd5e36fcf548f5e5b86dc764_Traceguids,
        (unsigned int)v19);
    if ( (unsigned __int8)RegistryKey::GetValueBoolean(v24, L"MigrationComplete") )
    {
      RegistryKey::SetValue(v24, L"MigrationFailureCount", 0, 0);
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
        goto LABEL_34;
      v21 = 28;
    }
    else
    {
      v5 = (unsigned int)RegistryKey::GetValueDword(v24, L"MigrationFailureCount", 0, 1) + 1;
      RegistryKey::SetValue(v24, L"MigrationFailureCount", v5, 0);
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_34;
      v21 = 27;
    }
    WPP_SF_d(v20[2], v21, WPP_284c2e15fd5e36fcf548f5e5b86dc764_Traceguids, (unsigned int)v5);
LABEL_34:
    v22 = v30;
    if ( v30 && _InterlockedExchangeAdd((volatile signed __int32 *)v30 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(std::_Ref_count_base *))v22)(v22);
      std::_Ref_count_base::_Decwref(v22);
    }
    std::unique_ptr<void,SafeHandleCleanupIsFreeLibrary>::~unique_ptr<void,SafeHandleCleanupIsFreeLibrary>(&v27);
    std::wstring::_Tidy_deallocate(v31);
    goto LABEL_38;
  }
LABEL_40:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v25);
}

```

## disassembly

```asm
0x180009cfc  push    rbp
0x180009cfe  push    rbx
0x180009cff  push    rsi
0x180009d00  push    r13
0x180009d02  push    r14
0x180009d04  push    r15
0x180009d06  lea     rbp, [rsp-0E8h]
0x180009d0e  sub     rsp, 1E8h
0x180009d15  mov     rax, cs:__security_cookie
0x180009d1c  xor     rax, rsp
0x180009d1f  mov     [rbp+110h+var_40], rax
0x180009d26  mov     r15, rcx
0x180009d29  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x180009d30  lea     rcx, [rbp+110h+var_F8]; this
0x180009d34  call    ??0RegistryKey@@QEAA@PEAUHKEY__@@@Z; RegistryKey::RegistryKey(HKEY__ *)
0x180009d39  nop
0x180009d3a  mov     [rsp+210h+var_1F0], 0
0x180009d43  mov     r13d, 1
0x180009d49  mov     r9d, r13d
0x180009d4c  lea     r8, aSystemSetupUpg; "SYSTEM\\Setup\\Upgrade\\NetworkDriverBa"...
0x180009d53  lea     rdx, [rbp+110h+var_F0]
0x180009d57  lea     rcx, [rbp+110h+var_F8]
0x180009d5b  call    ?TryOpenSubKey@RegistryKey@@QEBA?AV1@PEB_WKPEAX@Z; RegistryKey::TryOpenSubKey(wchar_t const *,ulong,void *)
0x180009d60  cmp     qword ptr [rax], 0
0x180009d64  setz    bl
0x180009d67  lea     rcx, [rbp+110h+var_F0]
0x180009d6b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180009d70  test    bl, bl
0x180009d72  jnz     loc_18000A137
0x180009d78  mov     [rsp+210h+var_1F0], 0
0x180009d81  lea     r9d, [r13+2]
0x180009d85  lea     r8, aSystemCurrentc_2; "System\\CurrentControlSet\\Control\\Net"...
0x180009d8c  lea     rdx, [rbp+110h+var_100]
0x180009d90  lea     rcx, [rbp+110h+var_F8]
0x180009d94  call    ?CreateSubKey@RegistryKey@@QEBA?AV1@PEB_WKPEAXPEAKK@Z; RegistryKey::CreateSubKey(wchar_t const *,ulong,void *,ulong *,ulong)
0x180009d99  nop
0x180009d9a  lea     rdx, aMigrationcompl; "MigrationComplete"
0x180009da1  lea     rcx, [rbp+110h+var_100]
0x180009da5  call    ?GetValueBoolean@RegistryKey@@QEBA_NPEB_WW4MissingValueDisposition@1@@Z; RegistryKey::GetValueBoolean(wchar_t const *,RegistryKey::MissingValueDisposition)
0x180009daa  mov     bl, al
0x180009dac  mov     r9d, r13d
0x180009daf  xor     r8d, r8d
0x180009db2  lea     rdx, aMigrationfailu; "MigrationFailureCount"
0x180009db9  lea     rcx, [rbp+110h+var_100]
0x180009dbd  call    ?GetValueDword@RegistryKey@@QEBAKPEB_WW4EncodingOptions@1@W4MissingValueDisposition@1@@Z; RegistryKey::GetValueDword(wchar_t const *,RegistryKey::EncodingOptions,RegistryKey::MissingValueDisposition)
0x180009dc2  mov     esi, eax
0x180009dc4  test    bl, bl
0x180009dc6  jnz     loc_18000A12D
0x180009dcc  cmp     eax, 5
0x180009dcf  jnb     loc_18000A12D
0x180009dd5  xor     r9d, r9d
0x180009dd8  mov     r8d, r13d
0x180009ddb  lea     rdx, aMigrationcompl; "MigrationComplete"
0x180009de2  lea     rcx, [rbp+110h+var_100]
0x180009de6  call    ?SetValue@RegistryKey@@QEBAXPEB_WKW4EncodingOptions@1@@Z; RegistryKey::SetValue(wchar_t const *,ulong,RegistryKey::EncodingOptions)
0x180009deb  mov     [rsp+210h+var_1F0], 0
0x180009df4  mov     r9d, r13d
0x180009df7  lea     r8, aSystemCurrentc_3; "System\\CurrentControlSet\\Control\\Net"...
0x180009dfe  lea     rdx, [rbp+110h+var_F0]
0x180009e02  lea     rcx, [rbp+110h+var_F8]
0x180009e06  call    ?CreateSubKey@RegistryKey@@QEBA?AV1@PEB_WKPEAXPEAKK@Z; RegistryKey::CreateSubKey(wchar_t const *,ulong,void *,ulong *,ulong)
0x180009e0b  nop
0x180009e0c  lea     rdx, aModule; "Module"
0x180009e13  lea     rcx, [rbp+110h+var_F0]; this
0x180009e17  call    ?ValueExists@RegistryKey@@QEBA_NPEB_W@Z; RegistryKey::ValueExists(wchar_t const *)
0x180009e1c  test    al, al
0x180009e1e  jz      loc_18000A123
0x180009e24  xor     r9d, r9d
0x180009e27  lea     r8, aModule; "Module"
0x180009e2e  lea     rdx, [rbp+110h+var_B8]
0x180009e32  lea     rcx, [rbp+110h+var_F0]
0x180009e36  call    ?GetValueString@RegistryKey@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WW4MissingValueDisposition@1@@Z; RegistryKey::GetValueString(wchar_t const *,RegistryKey::MissingValueDisposition)
0x180009e3b  nop
0x180009e3c  lea     edx, [r13+5Bh]
0x180009e40  lea     rcx, [rbp+110h+var_B8]
0x180009e44  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180009e49  mov     rcx, rax; Str
0x180009e4c  call    cs:__imp_wcschr
0x180009e52  test    rax, rax
0x180009e55  jz      short loc_180009EB2
0x180009e57  lea     rbx, WPP_GLOBAL_Control
0x180009e5e  mov     r10, cs:WPP_GLOBAL_Control
0x180009e65  cmp     r10, rbx
0x180009e68  jz      short loc_180009E91
0x180009e6a  cmp     byte ptr [r10+19h], 2
0x180009e6f  jb      short loc_180009E91
0x180009e71  lea     rcx, [rbp+110h+var_B8]
0x180009e75  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180009e7a  mov     r9, rax
0x180009e7d  lea     edx, [r13+16h]
0x180009e81  lea     r8, WPP_284c2e15fd5e36fcf548f5e5b86dc764_Traceguids
0x180009e88  mov     rcx, [r10+10h]
0x180009e8c  call    WPP_SF_S
0x180009e91  mov     edx, 80070005h; int
0x180009e96  lea     rcx, [rsp+210h+pExceptionObject]; this
0x180009e9b  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x180009ea0  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x180009ea7  lea     rcx, [rsp+210h+pExceptionObject]; pExceptionObject
0x180009eac  call    _CxxThrowException_0
0x180009eb2  lea     rbx, WPP_GLOBAL_Control
0x180009eb9  mov     r10, cs:WPP_GLOBAL_Control
0x180009ec0  cmp     r10, rbx
0x180009ec3  jz      short loc_180009EED
0x180009ec5  cmp     byte ptr [r10+19h], 4
0x180009eca  jb      short loc_180009EED
0x180009ecc  lea     rcx, [rbp+110h+var_B8]
0x180009ed0  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180009ed5  mov     r9, rax
0x180009ed8  mov     edx, 18h
0x180009edd  lea     r8, WPP_284c2e15fd5e36fcf548f5e5b86dc764_Traceguids
0x180009ee4  mov     rcx, [r10+10h]
0x180009ee8  call    WPP_SF_S
0x180009eed  lea     rcx, [rbp+110h+var_B8]
0x180009ef1  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180009ef6  mov     rcx, rax; lpLibFileName
0x180009ef9  xor     edx, edx; hFile
0x180009efb  mov     r8d, 800h; dwFlags
0x180009f01  call    cs:__imp_LoadLibraryExW
0x180009f07  test    rax, rax
0x180009f0a  jnz     short loc_180009F12
0x180009f0c  call    ?ThrowLastError@Win32Exception@@SAXXZ; Win32Exception::ThrowLastError(void)
0x180009f12  mov     [rbp+110h+var_E8], rax
0x180009f16  lea     rdx, aNetworkbinding; "NetworkBindingEngineFinishMigration"
0x180009f1d  mov     rcx, rax; hModule
0x180009f20  call    cs:__imp_GetProcAddress
0x180009f26  mov     r14, rax
0x180009f29  test    rax, rax
0x180009f2c  jnz     short loc_180009F83
0x180009f2e  mov     rcx, cs:WPP_GLOBAL_Control
0x180009f35  cmp     rcx, rbx
0x180009f38  jz      short loc_180009F53
0x180009f3a  cmp     byte ptr [rcx+19h], 2
0x180009f3e  jb      short loc_180009F53
0x180009f40  lea     edx, [rax+19h]
0x180009f43  lea     r8, WPP_284c2e15fd5e36fcf548f5e5b86dc764_Traceguids
0x180009f4a  mov     rcx, [rcx+10h]
0x180009f4e  call    WPP_SF_
0x180009f53  call    cs:__imp_GetLastError
0x180009f59  test    eax, eax
0x180009f5b  jle     short loc_180009F65
0x180009f5d  movzx   eax, ax
0x180009f60  or      eax, 80070000h
0x180009f65  mov     edx, eax; int
0x180009f67  lea     rcx, [rsp+210h+pExceptionObject]; this
0x180009f6c  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x180009f71  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x180009f78  lea     rcx, [rsp+210h+pExceptionObject]; pExceptionObject
0x180009f7d  call    _CxxThrowException_0
0x180009f83  movups  xmm0, xmmword ptr [r15+130h]
0x180009f8b  movaps  [rbp+110h+var_90], xmm0
0x180009f92  movups  xmm1, xmmword ptr [r15+140h]
0x180009f9a  movaps  [rbp+110h+var_80], xmm1
0x180009fa1  movups  xmm0, xmmword ptr [r15+150h]
0x180009fa9  movaps  [rbp+110h+var_70], xmm0
0x180009fb0  movups  xmm1, xmmword ptr [r15+160h]
0x180009fb8  movaps  [rbp+110h+var_60], xmm1
0x180009fbf  movups  xmm0, xmmword ptr [r15+170h]
0x180009fc7  movaps  xmmword ptr [rbp+110h+Uuid.Data1], xmm0
0x180009fce  lea     rcx, [rbp+110h+Uuid]; Uuid
0x180009fd5  call    cs:__imp_UuidCreate
0x180009fdb  mov     [rbp+110h+var_E0], 9
0x180009fe3  mov     [rbp+110h+var_D0], 0
0x180009feb  lea     rax, [rbp+110h+var_90]
0x180009ff2  mov     [rbp+110h+var_D8], rax
0x180009ff6  mov     rcx, cs:?g_NetSetupService@@3PEAVNetSetupService@@EA; NetSetupService * g_NetSetupService
0x180009ffd  add     rcx, 20h ; ' '; struct StackLock *
0x18000a001  lea     r9, [rbp+110h+var_E0]
0x18000a005  lea     r8, [rbp+110h+Uuid]
0x18000a00c  lea     rdx, [rbp+110h+var_C8]
0x18000a010  call    ?CreateNewTransaction@NetSetupSvcTransactionCoordinator@@QEAA?AV?$shared_ptr@UNetSetupSvcTxHolder@@@std@@AEBU_GUID@@PEAU_NETSETUP_ENVIRONMENT@@@Z; NetSetupSvcTransactionCoordinator::CreateNewTransaction(_GUID const &,_NETSETUP_ENVIRONMENT *)
0x18000a015  nop
0x18000a016  mov     rcx, [rbp+110h+var_C8]
0x18000a01a  mov     rcx, [rcx]
0x18000a01d  mov     rax, r14
0x18000a020  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a025  test    eax, eax
0x18000a027  jns     short loc_18000A053
0x18000a029  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a030  cmp     rcx, rbx
0x18000a033  jz      short loc_18000A053
0x18000a035  cmp     byte ptr [rcx+19h], 3
0x18000a039  jb      short loc_18000A053
0x18000a03b  mov     edx, 1Ah
0x18000a040  mov     r9d, eax
0x18000a043  lea     r8, WPP_284c2e15fd5e36fcf548f5e5b86dc764_Traceguids
0x18000a04a  mov     rcx, [rcx+10h]
0x18000a04e  call    WPP_SF_d
0x18000a053  lea     rdx, aMigrationcompl; "MigrationComplete"
0x18000a05a  lea     rcx, [rbp+110h+var_100]
0x18000a05e  call    ?GetValueBoolean@RegistryKey@@QEBA_NPEB_WW4MissingValueDisposition@1@@Z; RegistryKey::GetValueBoolean(wchar_t const *,RegistryKey::MissingValueDisposition)
0x18000a063  xor     r8d, r8d
0x18000a066  lea     rdx, aMigrationfailu; "MigrationFailureCount"
0x18000a06d  lea     rcx, [rbp+110h+var_100]
0x18000a071  test    al, al
0x18000a073  jnz     short loc_18000A0AF
0x18000a075  mov     r9d, r13d
0x18000a078  call    ?GetValueDword@RegistryKey@@QEBAKPEB_WW4EncodingOptions@1@W4MissingValueDisposition@1@@Z; RegistryKey::GetValueDword(wchar_t const *,RegistryKey::EncodingOptions,RegistryKey::MissingValueDisposition)
0x18000a07d  lea     esi, [rax+1]
0x18000a080  xor     r9d, r9d
0x18000a083  mov     r8d, esi
0x18000a086  lea     rdx, aMigrationfailu; "MigrationFailureCount"
0x18000a08d  lea     rcx, [rbp+110h+var_100]
0x18000a091  call    ?SetValue@RegistryKey@@QEBAXPEB_WKW4EncodingOptions@1@@Z; RegistryKey::SetValue(wchar_t const *,ulong,RegistryKey::EncodingOptions)
0x18000a096  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a09d  cmp     rcx, rbx
0x18000a0a0  jz      short loc_18000A0E2
0x18000a0a2  cmp     byte ptr [rcx+19h], 2
0x18000a0a6  jb      short loc_18000A0E2
0x18000a0a8  mov     edx, 1Bh
0x18000a0ad  jmp     short loc_18000A0CE
0x18000a0af  xor     r9d, r9d
0x18000a0b2  call    ?SetValue@RegistryKey@@QEBAXPEB_WKW4EncodingOptions@1@@Z; RegistryKey::SetValue(wchar_t const *,ulong,RegistryKey::EncodingOptions)
0x18000a0b7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a0be  cmp     rcx, rbx
0x18000a0c1  jz      short loc_18000A0E2
0x18000a0c3  cmp     byte ptr [rcx+19h], 4
0x18000a0c7  jb      short loc_18000A0E2
0x18000a0c9  mov     edx, 1Ch
0x18000a0ce  mov     r9d, esi
0x18000a0d1  lea     r8, WPP_284c2e15fd5e36fcf548f5e5b86dc764_Traceguids
0x18000a0d8  mov     rcx, [rcx+10h]
0x18000a0dc  call    WPP_SF_d
0x18000a0e1  nop
0x18000a0e2  mov     rbx, [rbp+110h+var_C0]
0x18000a0e6  test    rbx, rbx
0x18000a0e9  jz      short loc_18000A10F
0x18000a0eb  or      eax, 0FFFFFFFFh
0x18000a0ee  lock xadd [rbx+8], eax
0x18000a0f3  cmp     eax, 1
0x18000a0f6  jnz     short loc_18000A10F
0x18000a0f8  mov     rax, [rbx]
0x18000a0fb  mov     rcx, rbx
0x18000a0fe  mov     rax, [rax]
0x18000a101  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a106  mov     rcx, rbx; this
0x18000a109  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18000a10e  nop
0x18000a10f  lea     rcx, [rbp+110h+var_E8]
0x18000a113  call    ??1?$unique_ptr@XUSafeHandleCleanupIsFreeLibrary@@@std@@QEAA@XZ; std::unique_ptr<void,SafeHandleCleanupIsFreeLibrary>::~unique_ptr<void,SafeHandleCleanupIsFreeLibrary>(void)
0x18000a118  nop
0x18000a119  lea     rcx, [rbp+110h+var_B8]
0x18000a11d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000a122  nop
0x18000a123  lea     rcx, [rbp+110h+var_F0]
0x18000a127  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000a12c  nop
0x18000a12d  lea     rcx, [rbp+110h+var_100]
0x18000a131  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000a136  nop
0x18000a137  lea     rcx, [rbp+110h+var_F8]
0x18000a13b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000a140  mov     rcx, [rbp+110h+var_40]
0x18000a147  xor     rcx, rsp; StackCookie
0x18000a14a  call    __security_check_cookie
0x18000a14f  add     rsp, 1E8h
0x18000a156  pop     r15
0x18000a158  pop     r14
0x18000a15a  pop     r13
0x18000a15c  pop     rsi
0x18000a15d  pop     rbx
0x18000a15e  pop     rbp
0x18000a15f  retn
```
