# CStaticHandlerCollection::BindToHandler(ushort const *,_GUID const &,void * *)

- ea: `0x180006b00`
- end: `0x180006de9`
- name: `?BindToHandler@CStaticHandlerCollection@@UEAAJPEBGAEBU_GUID@@PEAPEAX@Z`
- size: `745`
- prototype: `int(CStaticHandlerCollection *__hidden this, const unsigned __int16 *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180003b40`
- `0x180006b00`
- `0x180012c9c`
- `0x180012e08`
- `0x180052950`
- `0x180053010`

## import_xrefs

- `SHELL32!__imp_GUIDFromStringW` at `0x180006db4`
- `SHELL32!__imp_GUIDFromStringW` at `0x180006db4`
- `SHLWAPI!SHRegGetValueW` at `0x180006c81`
- `SHLWAPI!SHRegGetValueW` at `0x180006c81`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006ce0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006dd3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006ce0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006dd3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006bf6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006bf6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006bbe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006bbe`

## pseudocode

```c
HRESULT __fastcall CStaticHandlerCollection::BindToHandler(
        CStaticHandlerCollection *this,
        const unsigned __int16 *a2,
        const struct _GUID *a3,
        void **a4)
{
  signed int v8; // ebx
  LSTATUS v9; // eax
  HKEY v10; // rcx
  bool v11; // bl
  HRESULT result; // eax
  HRESULT Instance; // ebx
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 pvData; // [rsp+58h] [rbp-A8h] BYREF
  IID rclsid; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR SubKey[264]; // [rsp+70h] [rbp-90h] BYREF

  hKey = 0;
  if ( (int)StringCchPrintfExW(
              SubKey,
              0x104u,
              (unsigned __int16 **)&rclsid,
              &pvData,
              0,
              L"%ws\\%ws\\%ws\\",
              L"Software\\Microsoft\\Windows\\CurrentVersion\\SyncMgr",
              L"Handlers",
              a2) < 0 )
    return -2147024809;
  hKey = 0;
  v8 = 0;
  v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey);
  if ( v9 )
  {
    v10 = 0;
    if ( v9 > 0 )
      v8 = (unsigned __int16)v9 | 0x80070000;
    else
      v8 = v9;
    hKey = 0;
  }
  else
  {
    v10 = hKey;
  }
  if ( v8 < 0 )
    return -2147024809;
  RegCloseKey(v10);
  v11 = 0;
  if ( (int)StringCchPrintfExW(
              SubKey,
              0x104u,
              (unsigned __int16 **)&hKey,
              (unsigned __int64 *)&rclsid.Data1,
              0,
              L"%ws\\%ws\\%ws\\",
              L"Software\\Microsoft\\Windows\\CurrentVersion\\SyncMgr",
              L"Handlers",
              a2) >= 0 )
  {
    LODWORD(pvData) = 0;
    LODWORD(hKey) = 4;
    if ( !SHRegGetValueW(HKEY_LOCAL_MACHINE, SubKey, L"Isolate", 16, 0, &pvData, (DWORD *)&hKey) )
      v11 = (_DWORD)pvData != 0;
  }
  if ( *((_BYTE *)this + 12) || !v11 )
  {
    rclsid = 0;
    if ( (unsigned int)GUIDFromStringW(a2, &rclsid) )
      return CoCreateInstance(&rclsid, 0, 0x15u, a3, a4);
    return -2147024809;
  }
  result = RequestingIsolationServerStartup();
  if ( result >= 0 )
  {
    hKey = 0;
    Instance = CoCreateInstance(
                 &CLSID_SyncMgrIsolationCollection,
                 0,
                 4u,
                 &GUID_1a0e696d_2797_425c_83da_11690e066f95,
                 (LPVOID *)&hKey);
    if ( Instance >= 0 )
    {
      Instance = (*(__int64 (__fastcall **)(HKEY, GUID *))(*(_QWORD *)hKey + 40LL))(hKey, &GUID_NULL);
      if ( Instance >= 0 )
      {
        pvData = 0;
        Instance = (**(__int64 (__fastcall ***)(HKEY, GUID *, unsigned __int64 *))hKey)(
                     hKey,
                     &GUID_a7f337a3_d20b_45cb_9ed7_87d094ca5045,
                     &pvData);
        if ( Instance >= 0 )
        {
          Instance = (*(__int64 (__fastcall **)(unsigned __int64, const unsigned __int16 *, const struct _GUID *, void **))(*(_QWORD *)pvData + 32LL))(
                       pvData,
                       a2,
                       a3,
                       a4);
          (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)pvData + 16LL))(pvData);
        }
      }
      (*(void (__fastcall **)(HKEY))(*(_QWORD *)hKey + 16LL))(hKey);
    }
    IsolationServerStartupCompleted();
    return Instance;
  }
  return result;
}

```

## disassembly

```asm
0x180006b00  push    rbp
0x180006b02  push    rsi
0x180006b03  push    rdi
0x180006b04  push    r12
0x180006b06  push    r13
0x180006b08  push    r14
0x180006b0a  push    r15
0x180006b0c  lea     rbp, [rsp-190h]
0x180006b14  sub     rsp, 290h
0x180006b1b  mov     rax, cs:__security_cookie
0x180006b22  xor     rax, rsp
0x180006b25  mov     [rbp+1C0h+var_40], rax
0x180006b2c  mov     [rsp+2C0h+var_280], rdx
0x180006b31  lea     rax, ?s_szToplevel_regkey@CSettingsBase@@1QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180006b38  mov     r14, r9
0x180006b3b  lea     r13, ?s_szHandlers_regkey@CSettingsBase@@1QBGB; "Handlers"
0x180006b42  mov     [rsp+2C0h+var_288], r13
0x180006b47  lea     r9, [rsp+2C0h+var_268]; unsigned __int64 *
0x180006b4c  mov     [rsp+2C0h+pcbData], rax
0x180006b51  mov     rsi, r8
0x180006b54  lea     rax, aWsWsWs_0; "%ws\\%ws\\%ws\\"
0x180006b5b  mov     rdi, rdx
0x180006b5e  mov     r15, rcx
0x180006b61  mov     [rsp+2C0h+pvData], rax; unsigned __int16 *
0x180006b66  xor     r12d, r12d
0x180006b69  lea     r8, [rsp+2C0h+rclsid]; unsigned __int16 **
0x180006b6e  mov     edx, 104h; unsigned __int64
0x180006b73  mov     [rsp+2C0h+phkResult], r12; unsigned int
0x180006b78  lea     rcx, [rsp+2C0h+SubKey]; pszDest
0x180006b7d  mov     [rsp+2C0h+hKey], r12
0x180006b82  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180006b87  test    eax, eax
0x180006b89  js      loc_180006DE2
0x180006b8f  lea     rax, [rsp+2C0h+hKey]
0x180006b94  mov     [rsp+2C0h+arg_0], rbx
0x180006b9c  mov     r9d, 20019h; samDesired
0x180006ba2  mov     [rsp+2C0h+phkResult], rax; phkResult
0x180006ba7  xor     r8d, r8d; ulOptions
0x180006baa  mov     [rsp+2C0h+hKey], r12
0x180006baf  lea     rdx, [rsp+2C0h+SubKey]; lpSubKey
0x180006bb4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180006bbb  mov     ebx, r12d
0x180006bbe  call    cs:__imp_RegOpenKeyExW
0x180006bc4  test    eax, eax
0x180006bc6  jz      short loc_180006BE9
0x180006bc8  jg      short loc_180006BD6
0x180006bca  mov     ecx, r12d
0x180006bcd  mov     ebx, eax
0x180006bcf  mov     [rsp+2C0h+hKey], rcx
0x180006bd4  jmp     short loc_180006BEE
0x180006bd6  movzx   ebx, ax
0x180006bd9  mov     rcx, r12
0x180006bdc  or      ebx, 80070000h
0x180006be2  mov     [rsp+2C0h+hKey], rcx
0x180006be7  jmp     short loc_180006BEE
0x180006be9  mov     rcx, [rsp+2C0h+hKey]; hKey
0x180006bee  test    ebx, ebx
0x180006bf0  js      loc_180006DDB
0x180006bf6  call    cs:__imp_RegCloseKey
0x180006bfc  mov     [rsp+2C0h+var_280], rdi
0x180006c01  lea     rax, ?s_szToplevel_regkey@CSettingsBase@@1QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180006c08  mov     [rsp+2C0h+var_288], r13
0x180006c0d  lea     r9, [rsp+2C0h+rclsid]; unsigned __int64 *
0x180006c12  mov     [rsp+2C0h+pcbData], rax
0x180006c17  lea     r8, [rsp+2C0h+hKey]; unsigned __int16 **
0x180006c1c  lea     rax, aWsWsWs_0; "%ws\\%ws\\%ws\\"
0x180006c23  mov     edx, 104h; unsigned __int64
0x180006c28  mov     [rsp+2C0h+pvData], rax; unsigned __int16 *
0x180006c2d  lea     rcx, [rsp+2C0h+SubKey]; pszDest
0x180006c32  mov     [rsp+2C0h+phkResult], r12; unsigned int
0x180006c37  xor     bl, bl
0x180006c39  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180006c3e  test    eax, eax
0x180006c40  js      short loc_180006C9B
0x180006c42  lea     rax, [rsp+2C0h+hKey]
0x180006c47  mov     dword ptr [rsp+2C0h+var_268], r12d
0x180006c4c  mov     [rsp+2C0h+pcbData], rax; pcbData
0x180006c51  lea     r8, ?s_szIsolate_value@CSettingsBase@@1QBGB; "Isolate"
0x180006c58  lea     rax, [rsp+2C0h+var_268]
0x180006c5d  mov     dword ptr [rsp+2C0h+hKey], 4
0x180006c65  mov     [rsp+2C0h+pvData], rax; pvData
0x180006c6a  lea     rdx, [rsp+2C0h+SubKey]; pszSubKey
0x180006c6f  mov     r9d, 10h; srrfFlags
0x180006c75  mov     [rsp+2C0h+phkResult], r12; pdwType
0x180006c7a  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180006c81  call    cs:__imp_SHRegGetValueW
0x180006c87  test    eax, eax
0x180006c89  jnz     short loc_180006C9B
0x180006c8b  cmp     dword ptr [rsp+2C0h+var_268], r12d
0x180006c90  mov     eax, 1
0x180006c95  movzx   ebx, bl
0x180006c98  cmovnz  ebx, eax
0x180006c9b  cmp     [r15+0Ch], r12b
0x180006c9f  jnz     loc_180006DA4
0x180006ca5  cmp     bl, 1
0x180006ca8  jnz     loc_180006DA4
0x180006cae  call    ?RequestingIsolationServerStartup@@YAJXZ; RequestingIsolationServerStartup(void)
0x180006cb3  test    eax, eax
0x180006cb5  js      loc_180006D7A
0x180006cbb  lea     rax, [rsp+2C0h+hKey]
0x180006cc0  mov     [rsp+2C0h+hKey], r12
0x180006cc5  lea     r9, _GUID_1a0e696d_2797_425c_83da_11690e066f95; riid
0x180006ccc  mov     [rsp+2C0h+phkResult], rax; ppv
0x180006cd1  xor     edx, edx; pUnkOuter
0x180006cd3  lea     rcx, CLSID_SyncMgrIsolationCollection; rclsid
0x180006cda  mov     r8d, 4; dwClsContext
0x180006ce0  call    cs:__imp_CoCreateInstance
0x180006ce6  mov     ebx, eax
0x180006ce8  test    eax, eax
0x180006cea  js      loc_180006D73
0x180006cf0  mov     rcx, [rsp+2C0h+hKey]
0x180006cf5  lea     rdx, GUID_NULL
0x180006cfc  mov     rax, [rcx]
0x180006cff  mov     rax, [rax+28h]
0x180006d03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d08  mov     ebx, eax
0x180006d0a  test    eax, eax
0x180006d0c  js      short loc_180006D62
0x180006d0e  mov     rcx, [rsp+2C0h+hKey]
0x180006d13  lea     r8, [rsp+2C0h+var_268]
0x180006d18  mov     [rsp+2C0h+var_268], r12
0x180006d1d  lea     rdx, _GUID_a7f337a3_d20b_45cb_9ed7_87d094ca5045
0x180006d24  mov     rax, [rcx]
0x180006d27  mov     rax, [rax]
0x180006d2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d2f  mov     ebx, eax
0x180006d31  test    eax, eax
0x180006d33  js      short loc_180006D62
0x180006d35  mov     rcx, [rsp+2C0h+var_268]
0x180006d3a  mov     r9, r14
0x180006d3d  mov     r8, rsi
0x180006d40  mov     rdx, rdi
0x180006d43  mov     rax, [rcx]
0x180006d46  mov     rax, [rax+20h]
0x180006d4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d4f  mov     rcx, [rsp+2C0h+var_268]
0x180006d54  mov     ebx, eax
0x180006d56  mov     rax, [rcx]
0x180006d59  mov     rax, [rax+10h]
0x180006d5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d62  mov     rcx, [rsp+2C0h+hKey]
0x180006d67  mov     rax, [rcx]
0x180006d6a  mov     rax, [rax+10h]
0x180006d6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d73  call    ?IsolationServerStartupCompleted@@YAXXZ; IsolationServerStartupCompleted(void)
0x180006d78  mov     eax, ebx
0x180006d7a  mov     rbx, [rsp+2C0h+arg_0]
0x180006d82  mov     rcx, [rbp+1C0h+var_40]
0x180006d89  xor     rcx, rsp; StackCookie
0x180006d8c  call    __security_check_cookie
0x180006d91  add     rsp, 290h
0x180006d98  pop     r15
0x180006d9a  pop     r14
0x180006d9c  pop     r13
0x180006d9e  pop     r12
0x180006da0  pop     rdi
0x180006da1  pop     rsi
0x180006da2  pop     rbp
0x180006da3  retn
0x180006da4  xorps   xmm0, xmm0
0x180006da7  lea     rdx, [rsp+2C0h+rclsid]
0x180006dac  mov     rcx, rdi
0x180006daf  movups  xmmword ptr [rsp+2C0h+rclsid.Data1], xmm0
0x180006db4  call    cs:__imp_GUIDFromStringW
0x180006dba  test    eax, eax
0x180006dbc  jz      short loc_180006DDB
0x180006dbe  mov     r9, rsi; riid
0x180006dc1  mov     [rsp+2C0h+phkResult], r14; ppv
0x180006dc6  xor     edx, edx; pUnkOuter
0x180006dc8  lea     rcx, [rsp+2C0h+rclsid]; rclsid
0x180006dcd  mov     r8d, 15h; dwClsContext
0x180006dd3  call    cs:__imp_CoCreateInstance
0x180006dd9  jmp     short loc_180006D7A
0x180006ddb  mov     eax, 80070057h
0x180006de0  jmp     short loc_180006D7A
0x180006de2  mov     eax, 80070057h
0x180006de7  jmp     short loc_180006D82
```
