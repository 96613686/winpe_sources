# ServiceControl::OnRegister(void)

- ea: `0x140003c40`
- end: `0x140003f32`
- name: `?OnRegister@ServiceControl@@CAXXZ`
- size: `754`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14000395c`

## callees

- `0x1400023e4`
- `0x140003c40`
- `0x140003f34`
- `0x1400041b4`
- `0x140004278`
- `0x140004334`
- `0x1400137e0`

## import_xrefs

- `ole32!StringFromGUID2` at `0x140003c7f`
- `ole32!StringFromGUID2` at `0x140003c7f`
- `ADVAPI32!RegSetValueExW` at `0x140003d48`
- `ADVAPI32!RegSetValueExW` at `0x140003d96`
- `ADVAPI32!RegSetValueExW` at `0x140003e2b`
- `ADVAPI32!RegSetValueExW` at `0x140003e60`
- `ADVAPI32!RegSetValueExW` at `0x140003e91`
- `ADVAPI32!RegSetValueExW` at `0x140003ec3`
- `ADVAPI32!RegSetValueExW` at `0x140003d48`
- `ADVAPI32!RegSetValueExW` at `0x140003d96`
- `ADVAPI32!RegSetValueExW` at `0x140003e2b`
- `ADVAPI32!RegSetValueExW` at `0x140003e60`
- `ADVAPI32!RegSetValueExW` at `0x140003e91`
- `ADVAPI32!RegSetValueExW` at `0x140003ec3`
- `ADVAPI32!RegCloseKey` at `0x140003ee8`
- `ADVAPI32!RegCloseKey` at `0x140003f01`
- `ADVAPI32!RegCloseKey` at `0x140003ee8`
- `ADVAPI32!RegCloseKey` at `0x140003f01`

## string_xrefs

- `0x140003e21`: `LocalService`
- `0x140003e56`: `AccessPermission`
- `0x140003ecd`: `SUCCESS: The service was installed successfully\n`
- `0x140003c94`: `CLSID\`
- `0x140003d24`: `Visual Studio Standard Collector Service`
- `0x140003e04`: `VsStandardCollectorService170`

## pseudocode

```c
void ServiceControl::OnRegister(void)
{
  __int64 v0; // rdx
  unsigned __int16 *v1; // rcx
  unsigned __int16 v2; // ax
  unsigned __int16 *v3; // rax
  HKEY v4; // rdx
  unsigned __int16 *v5; // r9
  __int64 v6; // rax
  HKEY v7; // rdx
  unsigned __int16 *v8; // r9
  int v9; // eax
  HKEY v10; // rbx
  unsigned int lpData; // [rsp+20h] [rbp-E0h]
  unsigned int lpDataa; // [rsp+20h] [rbp-E0h]
  DWORD cbData; // [rsp+28h] [rbp-D8h]
  DWORD cbDataa; // [rsp+28h] [rbp-D8h]
  struct _SECURITY_ATTRIBUTES *v15; // [rsp+30h] [rbp-D0h]
  struct _SECURITY_ATTRIBUTES *v16; // [rsp+30h] [rbp-D0h]
  unsigned int *v17; // [rsp+38h] [rbp-C8h]
  unsigned int *v18; // [rsp+38h] [rbp-C8h]
  HKEY hKey[3]; // [rsp+40h] [rbp-C0h] BYREF
  HKEY v20[3]; // [rsp+58h] [rbp-A8h] BYREF
  BYTE Data[16]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v22[1024]; // [rsp+80h] [rbp-80h] BYREF
  OLECHAR sz[40]; // [rsp+880h] [rbp+780h] BYREF

  if ( !StringFromGUID2(&CLSID_StandardCollectorService, sz, 39) )
    goto LABEL_29;
  v0 = 1024;
  v1 = v22;
  do
  {
    if ( v0 == -2147482622 )
      break;
    v2 = *(unsigned __int16 *)((char *)v1 + (char *)L"CLSID\\" - (char *)v22);
    if ( !v2 )
      break;
    *v1++ = v2;
    --v0;
  }
  while ( v0 );
  v3 = v1 - 1;
  if ( v0 )
    v3 = v1;
  *v3 = 0;
  if ( v0 && (int)StringCchCatW(v22, 0x400u, sz) >= 0 )
  {
    memset(hKey, 0, sizeof(hKey));
    if ( ATL::CRegKey::Create((ATL::CRegKey *)hKey, v4, v22, v5, lpData, cbData, v15, v17) )
      goto LABEL_26;
    if ( RegSetValueExW(
           hKey[0],
           &word_140019B74,
           0,
           1u,
           (const BYTE *)L"Visual Studio Standard Collector Service",
           0x52u) )
    {
      goto LABEL_26;
    }
    v6 = -1;
    do
      ++v6;
    while ( sz[v6] );
    if ( RegSetValueExW(hKey[0], L"AppID", 0, 1u, (const BYTE *)sz, 2 * v6 + 2)
      || (int)StringCchCopyW(v22, 0x400u, L"AppID\\") < 0
      || (int)StringCchCatW(v22, 0x400u, sz) < 0 )
    {
LABEL_26:
      ServiceControl::OnUnregister();
    }
    else
    {
      memset(v20, 0, sizeof(v20));
      v9 = ATL::CRegKey::Create((ATL::CRegKey *)v20, v7, v22, v8, lpDataa, cbDataa, v16, v18);
      v10 = v20[0];
      if ( v9
        || RegSetValueExW(v20[0], L"LocalService", 0, 1u, (const BYTE *)L"VsStandardCollectorService170", 0x3Cu)
        || RegSetValueExW(v10, L"AccessPermission", 0, 3u, &byte_140023100, 0x90u)
        || RegSetValueExW(v10, L"LaunchPermission", 0, 3u, &byte_140023190, 0x90u)
        || (*(_DWORD *)Data = 2, RegSetValueExW(v10, L"AuthenticationLevel", 0, 4u, Data, 4u)) )
      {
        ServiceControl::OnUnregister();
      }
      else
      {
        wprintf(L"SUCCESS: The service was installed successfully\n");
      }
      if ( v10 )
        RegCloseKey(v10);
    }
    if ( hKey[0] )
      RegCloseKey(hKey[0]);
  }
  else
  {
LABEL_29:
    ServiceControl::OnUnregister();
  }
}

```

## disassembly

```asm
0x140003c40  mov     [rsp-8+arg_0], rbx
0x140003c45  mov     [rsp-8+arg_8], rsi
0x140003c4a  push    rbp
0x140003c4b  lea     rbp, [rsp-7E0h]
0x140003c53  sub     rsp, 8E0h
0x140003c5a  mov     rax, cs:__security_cookie
0x140003c61  xor     rax, rsp
0x140003c64  mov     [rbp+7E0h+var_10], rax
0x140003c6b  mov     r8d, 27h ; '''; cchMax
0x140003c71  lea     rdx, [rbp+7E0h+sz]; lpsz
0x140003c78  lea     rcx, CLSID_StandardCollectorService; rguid
0x140003c7f  call    cs:__imp_StringFromGUID2
0x140003c85  xor     esi, esi
0x140003c87  test    eax, eax
0x140003c89  jz      loc_140003F09
0x140003c8f  mov     ebx, 400h
0x140003c94  lea     r8, aClsid; "CLSID\\"
0x140003c9b  lea     rax, [rbp+7E0h+var_860]
0x140003c9f  mov     edx, ebx
0x140003ca1  sub     r8, rax
0x140003ca4  lea     rcx, [rbp+7E0h+var_860]
0x140003ca8  lea     rax, [rdx+7FFFFBFEh]
0x140003caf  test    rax, rax
0x140003cb2  jz      short loc_140003CCB
0x140003cb4  movzx   eax, word ptr [rcx+r8]
0x140003cb9  test    ax, ax
0x140003cbc  jz      short loc_140003CCB
0x140003cbe  mov     [rcx], ax
0x140003cc1  add     rcx, 2
0x140003cc5  sub     rdx, 1
0x140003cc9  jnz     short loc_140003CA8
0x140003ccb  test    rdx, rdx
0x140003cce  lea     rax, [rcx-2]
0x140003cd2  cmovnz  rax, rcx
0x140003cd6  mov     [rax], si
0x140003cd9  jz      loc_140003F09
0x140003cdf  lea     r8, [rbp+7E0h+sz]; unsigned __int16 *
0x140003ce6  mov     rdx, rbx; unsigned __int64
0x140003ce9  lea     rcx, [rbp+7E0h+var_860]; unsigned __int16 *
0x140003ced  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140003cf2  test    eax, eax
0x140003cf4  js      loc_140003F09
0x140003cfa  lea     r8, [rbp+7E0h+var_860]; unsigned __int16 *
0x140003cfe  mov     [rsp+8E0h+var_898], rsi
0x140003d03  lea     rcx, [rsp+8E0h+hKey]; this
0x140003d08  mov     [rsp+8E0h+hKey], rsi
0x140003d0d  mov     [rsp+8E0h+var_890], rsi
0x140003d12  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x140003d17  test    eax, eax
0x140003d19  jnz     loc_140003EF0
0x140003d1f  mov     rcx, [rsp+8E0h+hKey]; hKey
0x140003d24  lea     rax, Data; "Visual Studio Standard Collector Servic"...
0x140003d2b  mov     [rsp+8E0h+cbData], 52h ; 'R'; cbData
0x140003d33  lea     rdx, word_140019B74; lpValueName
0x140003d3a  mov     r9d, 1; dwType
0x140003d40  mov     [rsp+8E0h+lpData], rax; lpData
0x140003d45  xor     r8d, r8d; Reserved
0x140003d48  call    cs:__imp_RegSetValueExW
0x140003d4e  test    eax, eax
0x140003d50  jnz     loc_140003EF0
0x140003d56  lea     rcx, [rbp+7E0h+sz]
0x140003d5d  or      rax, 0FFFFFFFFFFFFFFFFh
0x140003d61  inc     rax
0x140003d64  cmp     [rcx+rax*2], si
0x140003d68  jnz     short loc_140003D61
0x140003d6a  mov     rcx, [rsp+8E0h+hKey]; hKey
0x140003d6f  lea     eax, ds:2[rax*2]
0x140003d76  mov     [rsp+8E0h+cbData], eax; unsigned int
0x140003d7a  lea     rdx, aAppid_0; "AppID"
0x140003d81  lea     rax, [rbp+7E0h+sz]
0x140003d88  mov     r9d, 1; dwType
0x140003d8e  xor     r8d, r8d; Reserved
0x140003d91  mov     [rsp+8E0h+lpData], rax; unsigned int
0x140003d96  call    cs:__imp_RegSetValueExW
0x140003d9c  test    eax, eax
0x140003d9e  jnz     loc_140003EF0
0x140003da4  lea     r8, aAppid; "AppID\\"
0x140003dab  mov     rdx, rbx; unsigned __int64
0x140003dae  lea     rcx, [rbp+7E0h+var_860]; unsigned __int16 *
0x140003db2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140003db7  test    eax, eax
0x140003db9  js      loc_140003EF0
0x140003dbf  lea     r8, [rbp+7E0h+sz]; unsigned __int16 *
0x140003dc6  mov     rdx, rbx; unsigned __int64
0x140003dc9  lea     rcx, [rbp+7E0h+var_860]; unsigned __int16 *
0x140003dcd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140003dd2  test    eax, eax
0x140003dd4  js      loc_140003EF0
0x140003dda  lea     r8, [rbp+7E0h+var_860]; unsigned __int16 *
0x140003dde  mov     [rsp+8E0h+var_880], rsi
0x140003de3  lea     rcx, [rsp+8E0h+var_888]; this
0x140003de8  mov     [rsp+8E0h+var_888], rsi
0x140003ded  mov     [rsp+8E0h+var_878], rsi
0x140003df2  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x140003df7  mov     rbx, [rsp+8E0h+var_888]
0x140003dfc  test    eax, eax
0x140003dfe  jnz     loc_140003EDB
0x140003e04  lea     rax, ?WZ_SERVICENAME@@3QBGB; "VsStandardCollectorService170"
0x140003e0b  mov     [rsp+8E0h+cbData], 3Ch ; '<'; cbData
0x140003e13  mov     r9d, 1; dwType
0x140003e19  mov     [rsp+8E0h+lpData], rax; lpData
0x140003e1e  xor     r8d, r8d; Reserved
0x140003e21  lea     rdx, aLocalservice; "LocalService"
0x140003e28  mov     rcx, rbx; hKey
0x140003e2b  call    cs:__imp_RegSetValueExW
0x140003e31  test    eax, eax
0x140003e33  jnz     loc_140003EDB
0x140003e39  lea     rax, byte_140023100
0x140003e40  mov     [rsp+8E0h+cbData], 90h; cbData
0x140003e48  mov     r9d, 3; dwType
0x140003e4e  mov     [rsp+8E0h+lpData], rax; lpData
0x140003e53  xor     r8d, r8d; Reserved
0x140003e56  lea     rdx, aAccesspermissi; "AccessPermission"
0x140003e5d  mov     rcx, rbx; hKey
0x140003e60  call    cs:__imp_RegSetValueExW
0x140003e66  test    eax, eax
0x140003e68  jnz     short loc_140003EDB
0x140003e6a  lea     rax, byte_140023190
0x140003e71  mov     [rsp+8E0h+cbData], 90h; cbData
0x140003e79  mov     r9d, 3; dwType
0x140003e7f  mov     [rsp+8E0h+lpData], rax; lpData
0x140003e84  xor     r8d, r8d; Reserved
0x140003e87  lea     rdx, aLaunchpermissi; "LaunchPermission"
0x140003e8e  mov     rcx, rbx; hKey
0x140003e91  call    cs:__imp_RegSetValueExW
0x140003e97  test    eax, eax
0x140003e99  jnz     short loc_140003EDB
0x140003e9b  lea     r9d, [rax+4]; dwType
0x140003e9f  mov     dword ptr [rsp+8E0h+Data], 2
0x140003ea7  lea     rax, [rsp+8E0h+Data]
0x140003eac  mov     [rsp+8E0h+cbData], r9d; cbData
0x140003eb1  xor     r8d, r8d; Reserved
0x140003eb4  mov     [rsp+8E0h+lpData], rax; lpData
0x140003eb9  lea     rdx, aAuthentication; "AuthenticationLevel"
0x140003ec0  mov     rcx, rbx; hKey
0x140003ec3  call    cs:__imp_RegSetValueExW
0x140003ec9  test    eax, eax
0x140003ecb  jnz     short loc_140003EDB
0x140003ecd  lea     rcx, aSuccessTheServ_1; "SUCCESS: The service was installed succ"...
0x140003ed4  call    wprintf
0x140003ed9  jmp     short loc_140003EE0
0x140003edb  call    ?OnUnregister@ServiceControl@@CAXXZ; ServiceControl::OnUnregister(void)
0x140003ee0  test    rbx, rbx
0x140003ee3  jz      short loc_140003EF5
0x140003ee5  mov     rcx, rbx; hKey
0x140003ee8  call    cs:__imp_RegCloseKey
0x140003eee  jmp     short loc_140003EF5
0x140003ef0  call    ?OnUnregister@ServiceControl@@CAXXZ; ServiceControl::OnUnregister(void)
0x140003ef5  cmp     [rsp+8E0h+hKey], rsi
0x140003efa  jz      short loc_140003F0E
0x140003efc  mov     rcx, [rsp+8E0h+hKey]; hKey
0x140003f01  call    cs:__imp_RegCloseKey
0x140003f07  jmp     short loc_140003F0E
0x140003f09  call    ?OnUnregister@ServiceControl@@CAXXZ; ServiceControl::OnUnregister(void)
0x140003f0e  mov     rcx, [rbp+7E0h+var_10]
0x140003f15  xor     rcx, rsp; StackCookie
0x140003f18  call    __security_check_cookie
0x140003f1d  lea     r11, [rsp+8E0h+var_s0]
0x140003f25  mov     rbx, [r11+10h]
0x140003f29  mov     rsi, [r11+18h]
0x140003f2d  mov     rsp, r11
0x140003f30  pop     rbp
0x140003f31  retn
```
