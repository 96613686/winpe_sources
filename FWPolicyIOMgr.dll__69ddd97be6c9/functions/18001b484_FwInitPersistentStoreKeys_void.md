# FwInitPersistentStoreKeys(void)

- ea: `0x18001b484`
- end: `0x18001ba55`
- name: `?FwInitPersistentStoreKeys@@YAJXZ`
- size: `1489`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002d280`

## callees

- `0x180001cdc`
- `0x180003b94`
- `0x1800041d0`
- `0x1800042c4`
- `0x18000cff0`
- `0x180019e0c`
- `0x18001b484`
- `0x18001e9ac`
- `0x18001f650`
- `0x18001ffd4`
- `0x18003b010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18001b5c5`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18001b5c5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18001b5e0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18001b5e0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001b4af`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001b4af`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b4bf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b4bf`
- `fwbase!FwNtStatusToHResult` at `0x18001b558`
- `fwbase!FwNtStatusToHResult` at `0x18001b7a1`
- `fwbase!FwNtStatusToHResult` at `0x18001b558`
- `fwbase!FwNtStatusToHResult` at `0x18001b7a1`
- `fwbase!FwLicensingIsXbox` at `0x18001b51a`
- `fwbase!FwLicensingIsXbox` at `0x18001b51a`

## string_xrefs

- `0x18001b52d`: `SYSTEM\CurrentControlSet\Services\SharedAccess\Parameters\FirewallPolicy`
- `0x18001b5d6`: `SYSTEM\CurrentControlSet\Services\SharedAccess\Parameters\FirewallPolicy`
- `0x18001b4a8`: `ntdll.dll`
- `0x18001b539`: `SharedAccessFirewallPolicy`
- `0x18001b6a2`: `StringCchPrintf::FWStoresRegPath`
- `0x18001b6e5`: `StringCchPrintf::HyperVFWStoresRegPath`
- `0x18001b6fa`: `SYSTEM\CurrentControlSet\Services\MpsSvc\Parameters`
- `0x18001b77f`: `SYSTEM\CurrentControlSet\Services\MpsSvc\Parameters`
- `0x18001b811`: `ACService`
- `0x18001b4c8`: `SYSTEM\CurrentControlSet\Services\SharedAccess\Parameters\FirewallPolicy`
- `0x18001b5ae`: `SYSTEM\CurrentControlSet\Services\SharedAccess\Parameters\FirewallPolicy`
- `0x18001b631`: `SYSTEM\CurrentControlSet\Services\SharedAccess\Parameters\FirewallPolicy`
- `0x18001b677`: `SYSTEM\CurrentControlSet\Services\SharedAccess\Parameters\FirewallPolicy`
- `0x18001b8bc`: `SYSTEM\CurrentControlSet\Services\SharedAccess\Parameters\FirewallPolicy`
- `0x18001b916`: `SYSTEM\CurrentControlSet\Services\SharedAccess\Parameters\FirewallPolicy`

## pseudocode

```c
__int64 FwInitPersistentStoreKeys(void)
{
  HMODULE ModuleHandleW; // rax
  __int64 v1; // rcx
  FARPROC ProcAddress; // rbp
  __int64 v3; // r8
  __int64 v4; // r9
  unsigned int v5; // eax
  int v6; // eax
  LPCOLESTR v7; // rcx
  unsigned int v8; // esi
  __int64 v9; // r14
  unsigned __int64 v10; // rdi
  const unsigned __int16 *v11; // r8
  unsigned int v12; // ebx
  const unsigned __int16 *v13; // r8
  LPCOLESTR v14; // rcx
  int v15; // edx
  const char *v16; // rax
  unsigned int v17; // eax
  int v18; // eax
  unsigned int i; // edi
  __int64 v20; // rsi
  int v21; // eax
  __int64 v22; // rdx
  _OWORD v24[6]; // [rsp+50h] [rbp-248h] BYREF
  __int64 v25; // [rsp+B0h] [rbp-1E8h]
  _BYTE v26[408]; // [rsp+B8h] [rbp-1E0h] BYREF

  ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
  ProcAddress = GetProcAddress(ModuleHandleW, "RtlGetPersistedStateLocation");
  if ( !ProcAddress )
  {
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids);
    goto LABEL_44;
  }
  if ( !(unsigned int)FwLicensingIsXbox(v1, _ImageBase, v3, v4) )
  {
    v5 = ((__int64 (__fastcall *)(const wchar_t *, _QWORD, const wchar_t *, _QWORD, wchar_t *, int, _QWORD))ProcAddress)(
           L"SharedAccessFirewallPolicy",
           0,
           L"SYSTEM\\CurrentControlSet\\Services\\SharedAccess\\Parameters\\FirewallPolicy",
           0,
           g_FwPersistentStoreRootKey,
           512,
           0);
    v6 = FwNtStatusToHResult(v5);
    if ( v6 < 0 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control )
      {
LABEL_14:
        if ( !g_FwPersistentStoreRootKey[0] )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        if ( wcsnlen(g_FwPersistentStoreRootKey, 0x100u) != 73
          || (unsigned int)_o__wcsnicmp(
                             g_FwPersistentStoreRootKey,
                             L"SYSTEM\\CurrentControlSet\\Services\\SharedAccess\\Parameters\\FirewallPolicy",
                             73) )
        {
          v8 = 0;
          while ( 1 )
          {
            v9 = v8;
            v10 = (unsigned __int64)v8 << 9;
            v11 = (const unsigned __int16 *)(&FWStoresRepathFormats)[v9];
            if ( *v11 )
            {
              v12 = StringCchPrintfW(
                      (unsigned __int16 *)((char *)&FWStoresRegPath + v10),
                      0x100u,
                      v11,
                      g_FwPersistentStoreRootKey);
              if ( (v12 & 0x80000000) != 0 )
                break;
            }
            v13 = (const unsigned __int16 *)(&HyperVFWStoresRepathFormats)[v9];
            if ( v13 )
            {
              v12 = StringCchPrintfW(
                      (unsigned __int16 *)((char *)&HyperVFWStoresRegPath + v10),
                      0x100u,
                      v13,
                      g_FwPersistentStoreRootKey);
              if ( (v12 & 0x80000000) != 0 )
              {
                v14 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control )
                  return v12;
                if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
                {
                  v15 = 14;
                  v16 = "StringCchPrintf::HyperVFWStoresRegPath";
                  goto LABEL_28;
                }
                goto LABEL_60;
              }
            }
            if ( (int)++v8 >= 13 )
              goto LABEL_32;
          }
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control )
            return v12;
          if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            v15 = 13;
            v16 = "StringCchPrintf::FWStoresRegPath";
LABEL_28:
            WPP_SF_ds(
              *((_QWORD *)v14 + 2),
              v15,
              (unsigned int)WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids,
              v12,
              (__int64)v16);
LABEL_59:
            v14 = WPP_GLOBAL_Control;
          }
LABEL_60:
          if ( v14 != (LPCOLESTR)&WPP_GLOBAL_Control && (v14[14] & 8) != 0 )
            WPP_SF_d(*((_QWORD *)v14 + 2), 21, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids, v12);
          return v12;
        }
LABEL_32:
        v24[0] = *(_OWORD *)L"SYSTEM\\CurrentControlSet\\Services\\MpsSvc\\Parameters";
        v24[2] = *(_OWORD *)L"ntrolSet\\Services\\MpsSvc\\Parameters";
        v24[1] = *(_OWORD *)L"urrentControlSet\\Services\\MpsSvc\\Parameters";
        v24[4] = *(_OWORD *)L"s\\MpsSvc\\Parameters";
        v24[3] = *(_OWORD *)L"\\Services\\MpsSvc\\Parameters";
        v25 = *(_QWORD *)L"ers";
        v24[5] = *(_OWORD *)L"\\Parameters";
        memset_0(v26, 0, sizeof(v26));
        v17 = ((__int64 (__fastcall *)(const wchar_t *, _QWORD, const wchar_t *, _QWORD, _OWORD *, int, _QWORD))ProcAddress)(
                L"MpssvcParameters",
                0,
                L"SYSTEM\\CurrentControlSet\\Services\\MpsSvc\\Parameters",
                0,
                v24,
                512,
                0);
        v18 = FwNtStatusToHResult(v17);
        if ( v18 < 0 )
        {
          if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              17,
              WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids,
              (unsigned int)v18);
        }
        else
        {
          v12 = StringCchPrintfW(off_18004D690, 0x200u, L"%ls\\%ls", v24, L"AppCs");
          if ( (v12 & 0x80000000) != 0 )
          {
            v14 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control )
              return v12;
            if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
            {
              v15 = 15;
              v16 = "StringCchPrintf::AppCPolicyStore[0]";
              goto LABEL_28;
            }
            goto LABEL_60;
          }
          v12 = StringCchPrintfW(off_18004D798, 0x200u, L"%ls\\%ls", v24, L"ACService");
          if ( (v12 & 0x80000000) != 0 )
          {
            v14 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control )
              return v12;
            if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
            {
              v15 = 16;
              v16 = "StringCchPrintf::AppCPolicyStore[1]";
              goto LABEL_28;
            }
            goto LABEL_60;
          }
        }
        goto LABEL_44;
      }
      if ( (WPP_GLOBAL_Control[14] & 1) == 0 )
      {
LABEL_11:
        if ( v7 != (LPCOLESTR)&WPP_GLOBAL_Control && (v7[14] & 4) != 0 )
          WPP_SF_S(*((_QWORD *)v7 + 2), 12, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids, g_FwPersistentStoreRootKey);
        goto LABEL_14;
      }
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids,
        (unsigned int)v6);
    }
    v7 = WPP_GLOBAL_Control;
    goto LABEL_11;
  }
LABEL_44:
  for ( i = 0; (int)i < 2; ++i )
  {
    v20 = 260LL * i;
    v21 = StringCchPrintfExW(
            (STRSAFE_LPWSTR)&dword_18004CE64[v20],
            0x100u,
            0,
            0,
            0x800u,
            L"%s\\%s",
            g_FwPersistentStoreRootKey,
            &_ImageBase[256 * (unsigned __int64)i + 162488]);
    v12 = v21;
    if ( v21 < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control )
        return v12;
      if ( (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_60;
      v22 = 18;
      goto LABEL_58;
    }
    v21 = StringCchPrintfExW(
            (STRSAFE_LPWSTR)&dword_18004D064[v20],
            0x100u,
            0,
            0,
            0x800u,
            L"%s\\%s\\%s",
            g_FwPersistentStoreRootKey,
            L"Mdm",
            &_ImageBase[256 * (unsigned __int64)i + 162488]);
    v12 = v21;
    if ( v21 < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control )
        return v12;
      if ( (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_60;
      v22 = 19;
LABEL_58:
      WPP_SF_d(*((_QWORD *)v14 + 2), v22, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids, (unsigned int)v21);
      goto LABEL_59;
    }
    dword_18004D264[v20] = 1;
  }
  v21 = StringCchPrintfExW(
          &g_HyperVVMCreatorsRegPath,
          0x100u,
          0,
          0,
          0x800u,
          L"%s\\%s",
          g_FwPersistentStoreRootKey,
          L"HyperVVMCreators");
  v12 = v21;
  if ( v21 >= 0 )
    goto LABEL_59;
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control )
  {
    if ( (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_60;
    v22 = 20;
    goto LABEL_58;
  }
  return v12;
}

```

## disassembly

```asm
0x18001b484  push    rbx
0x18001b486  push    rbp
0x18001b487  push    rsi
0x18001b488  push    rdi
0x18001b489  push    r12
0x18001b48b  push    r14
0x18001b48d  push    r15
0x18001b48f  sub     rsp, 260h
0x18001b496  mov     rax, cs:__security_cookie
0x18001b49d  xor     rax, rsp
0x18001b4a0  mov     [rsp+298h+var_48], rax
0x18001b4a8  lea     rcx, ModuleName; "ntdll.dll"
0x18001b4af  call    cs:__imp_GetModuleHandleW
0x18001b4b5  mov     rcx, rax; hModule
0x18001b4b8  lea     rdx, ProcName; "RtlGetPersistedStateLocation"
0x18001b4bf  call    cs:__imp_GetProcAddress
0x18001b4c5  xor     r15d, r15d
0x18001b4c8  lea     rbx, ?g_FwPersistentStoreRootKey@@3PAGA; "SYSTEM\\CurrentControlSet\\Services\\Sh"...
0x18001b4cf  lea     rdx, __ImageBase
0x18001b4d6  mov     rbp, rax
0x18001b4d9  lea     r12, WPP_GLOBAL_Control
0x18001b4e0  lea     r14, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18001b4e7  test    rax, rax
0x18001b4ea  jnz     short loc_18001B51A
0x18001b4ec  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b4f3  cmp     rcx, r12
0x18001b4f6  jz      loc_18001B88C
0x18001b4fc  test    byte ptr [rcx+1Ch], 2
0x18001b500  jz      loc_18001B88C
0x18001b506  mov     rcx, [rcx+10h]
0x18001b50a  lea     edx, [rax+0Ah]
0x18001b50d  mov     r8, r14
0x18001b510  call    WPP_SF_
0x18001b515  jmp     loc_18001B885
0x18001b51a  call    cs:__imp_FwLicensingIsXbox
0x18001b520  test    eax, eax
0x18001b522  jnz     loc_18001B885
0x18001b528  mov     [rsp+298h+var_268], r15
0x18001b52d  lea     r8, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Sh"...
0x18001b534  mov     edi, 200h
0x18001b539  lea     rcx, aSharedaccessfi; "SharedAccessFirewallPolicy"
0x18001b540  mov     dword ptr [rsp+298h+var_270], edi
0x18001b544  xor     r9d, r9d
0x18001b547  xor     edx, edx
0x18001b549  mov     qword ptr [rsp+298h+var_278], rbx
0x18001b54e  mov     rax, rbp
0x18001b551  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b556  mov     ecx, eax
0x18001b558  call    cs:__imp_FwNtStatusToHResult
0x18001b55e  test    eax, eax
0x18001b560  jns     short loc_18001B588
0x18001b562  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b569  cmp     rcx, r12
0x18001b56c  jz      short loc_18001B5AE
0x18001b56e  test    byte ptr [rcx+1Ch], 1
0x18001b572  jz      short loc_18001B58F
0x18001b574  mov     rcx, [rcx+10h]
0x18001b578  mov     edx, 0Bh
0x18001b57d  mov     r9d, eax
0x18001b580  mov     r8, r14
0x18001b583  call    WPP_SF_d
0x18001b588  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b58f  cmp     rcx, r12
0x18001b592  jz      short loc_18001B5AE
0x18001b594  test    byte ptr [rcx+1Ch], 4
0x18001b598  jz      short loc_18001B5AE
0x18001b59a  mov     rcx, [rcx+10h]
0x18001b59e  mov     edx, 0Ch
0x18001b5a3  mov     r9, rbx
0x18001b5a6  mov     r8, r14
0x18001b5a9  call    WPP_SF_S
0x18001b5ae  cmp     word ptr cs:?g_FwPersistentStoreRootKey@@3PAGA, r15w; "SYSTEM\\CurrentControlSet\\Services\\Sh"...
0x18001b5b6  jnz     short loc_18001B5BD
0x18001b5b8  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001b5bd  mov     edx, 100h; MaxCount
0x18001b5c2  mov     rcx, rbx; Source
0x18001b5c5  call    cs:__imp_wcsnlen
0x18001b5cb  mov     r8d, 49h ; 'I'
0x18001b5d1  cmp     rax, r8
0x18001b5d4  jnz     short loc_18001B5EE
0x18001b5d6  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Sh"...
0x18001b5dd  mov     rcx, rbx
0x18001b5e0  call    cs:__imp__o__wcsnicmp
0x18001b5e6  test    eax, eax
0x18001b5e8  jz      loc_18001B6FA
0x18001b5ee  mov     esi, r15d
0x18001b5f1  lea     rax, __ImageBase
0x18001b5f8  mov     edi, esi
0x18001b5fa  lea     r14, ds:0[rdi*8]
0x18001b602  shl     rdi, 9
0x18001b606  mov     r8, [r14+rax+3C1C0h]; unsigned __int16 *
0x18001b60e  cmp     [r8], r15w
0x18001b612  jz      short loc_18001B63F
0x18001b614  lea     rcx, rva ?FWStoresRegPath@@3PAY0BAA@GA[rax]; ushort (near * FWStoresRegPath)[256] ...
0x18001b61b  mov     r9, rbx
0x18001b61e  add     rcx, rdi; unsigned __int16 *
0x18001b621  mov     edx, 100h; unsigned __int64
0x18001b626  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001b62b  mov     ebx, eax
0x18001b62d  test    eax, eax
0x18001b62f  js      short loc_18001B683
0x18001b631  lea     rbx, ?g_FwPersistentStoreRootKey@@3PAGA; "SYSTEM\\CurrentControlSet\\Services\\Sh"...
0x18001b638  lea     rax, __ImageBase
0x18001b63f  mov     r8, [r14+rax+3C150h]; unsigned __int16 *
0x18001b647  test    r8, r8
0x18001b64a  jz      short loc_18001B670
0x18001b64c  lea     rcx, rva ?HyperVFWStoresRegPath@@3PAY0BAA@GA[rax]; ushort (near * HyperVFWStoresRegPath)[256] ...
0x18001b653  mov     r9, rbx
0x18001b656  add     rcx, rdi; unsigned __int16 *
0x18001b659  mov     edx, 100h; unsigned __int64
0x18001b65e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001b663  mov     ebx, eax
0x18001b665  test    eax, eax
0x18001b667  js      short loc_18001B6C6
0x18001b669  lea     rax, __ImageBase
0x18001b670  inc     esi
0x18001b672  cmp     esi, 0Dh
0x18001b675  jge     short loc_18001B6EE
0x18001b677  lea     rbx, ?g_FwPersistentStoreRootKey@@3PAGA; "SYSTEM\\CurrentControlSet\\Services\\Sh"...
0x18001b67e  jmp     loc_18001B5F8
0x18001b683  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b68a  cmp     rcx, r12
0x18001b68d  jz      loc_18001BA31
0x18001b693  test    byte ptr [rcx+1Ch], 1
0x18001b697  jz      loc_18001BA0E
0x18001b69d  mov     edx, 0Dh
0x18001b6a2  lea     rax, aStringcchprint_0; "StringCchPrintf::FWStoresRegPath"
0x18001b6a9  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18001b6b0  mov     rcx, [rcx+10h]
0x18001b6b4  mov     r9d, ebx
0x18001b6b7  mov     qword ptr [rsp+298h+var_278], rax
0x18001b6bc  call    WPP_SF_ds
0x18001b6c1  jmp     loc_18001BA07
0x18001b6c6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b6cd  cmp     rcx, r12
0x18001b6d0  jz      loc_18001BA31
0x18001b6d6  test    byte ptr [rcx+1Ch], 1
0x18001b6da  jz      loc_18001BA0E
0x18001b6e0  mov     edx, 0Eh
0x18001b6e5  lea     rax, aStringcchprint_1; "StringCchPrintf::HyperVFWStoresRegPath"
0x18001b6ec  jmp     short loc_18001B6A9
0x18001b6ee  lea     r14, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18001b6f5  mov     edi, 200h
0x18001b6fa  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Services\\Mp"...
0x18001b701  lea     rcx, [rsp+298h+var_1E0]; void *
0x18001b709  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+10h; "urrentControlSet\\Services\\MpsSvc\\Par"...
0x18001b710  xor     edx, edx; Val
0x18001b712  movaps  [rsp+298h+var_248], xmm0
0x18001b717  mov     r8d, 198h; Size
0x18001b71d  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+20h; "ntrolSet\\Services\\MpsSvc\\Parameters"
0x18001b724  movaps  [rsp+298h+var_228], xmm0
0x18001b729  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+40h; "s\\MpsSvc\\Parameters"
0x18001b730  movaps  [rsp+298h+var_238], xmm1
0x18001b735  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+30h; "\\Services\\MpsSvc\\Parameters"
0x18001b73c  movaps  [rsp+298h+var_208], xmm0
0x18001b744  movsd   xmm0, qword ptr cs:aSystemCurrentc_2+60h; "ers"
0x18001b74c  movaps  [rsp+298h+var_218], xmm1
0x18001b754  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+50h; "\\Parameters"
0x18001b75b  movsd   [rsp+298h+var_1E8], xmm0
0x18001b764  movaps  [rsp+298h+var_1F8], xmm1
0x18001b76c  call    memset_0
0x18001b771  lea     rax, [rsp+298h+var_248]
0x18001b776  mov     [rsp+298h+var_268], r15
0x18001b77b  mov     dword ptr [rsp+298h+var_270], edi
0x18001b77f  lea     r8, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Services\\Mp"...
0x18001b786  mov     qword ptr [rsp+298h+var_278], rax
0x18001b78b  lea     rcx, aMpssvcparamete; "MpssvcParameters"
0x18001b792  mov     rax, rbp
0x18001b795  xor     r9d, r9d
0x18001b798  xor     edx, edx
0x18001b79a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b79f  mov     ecx, eax
0x18001b7a1  call    cs:__imp_FwNtStatusToHResult
0x18001b7a7  test    eax, eax
0x18001b7a9  js      loc_18001B85F
0x18001b7af  mov     rcx, cs:off_18004D690; unsigned __int16 *
0x18001b7b6  lea     rax, aAppcs; "AppCs"
0x18001b7bd  lea     r9, [rsp+298h+var_248]
0x18001b7c2  mov     qword ptr [rsp+298h+var_278], rax
0x18001b7c7  lea     r8, aLsLs; "%ls\\%ls"
0x18001b7ce  mov     rdx, rdi; unsigned __int64
0x18001b7d1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001b7d6  mov     ebx, eax
0x18001b7d8  test    eax, eax
0x18001b7da  jns     short loc_18001B80A
0x18001b7dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b7e3  cmp     rcx, r12
0x18001b7e6  jz      loc_18001BA31
0x18001b7ec  test    byte ptr [rcx+1Ch], 1
0x18001b7f0  jz      loc_18001BA0E
0x18001b7f6  mov     edx, 0Fh
0x18001b7fb  lea     rax, aStringcchprint_2; "StringCchPrintf::AppCPolicyStore[0]"
0x18001b802  mov     r8, r14
0x18001b805  jmp     loc_18001B6B0
0x18001b80a  mov     rcx, cs:off_18004D798; unsigned __int16 *
0x18001b811  lea     rax, aAcservice; "ACService"
0x18001b818  lea     r9, [rsp+298h+var_248]
0x18001b81d  mov     qword ptr [rsp+298h+var_278], rax
0x18001b822  lea     r8, aLsLs; "%ls\\%ls"
0x18001b829  mov     rdx, rdi; unsigned __int64
0x18001b82c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001b831  mov     ebx, eax
0x18001b833  test    eax, eax
0x18001b835  jns     short loc_18001B885
0x18001b837  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b83e  cmp     rcx, r12
0x18001b841  jz      loc_18001BA31
0x18001b847  test    byte ptr [rcx+1Ch], 1
0x18001b84b  jz      loc_18001BA0E
0x18001b851  mov     edx, 10h
0x18001b856  lea     rax, aStringcchprint; "StringCchPrintf::AppCPolicyStore[1]"
0x18001b85d  jmp     short loc_18001B802
0x18001b85f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b866  cmp     rcx, r12
0x18001b869  jz      short loc_18001B885
0x18001b86b  test    byte ptr [rcx+1Ch], 1
0x18001b86f  jz      short loc_18001B885
0x18001b871  mov     rcx, [rcx+10h]
0x18001b875  mov     edx, 11h
0x18001b87a  mov     r9d, eax
0x18001b87d  mov     r8, r14
0x18001b880  call    WPP_SF_d
0x18001b885  lea     rdx, __ImageBase
0x18001b88c  mov     edi, r15d
0x18001b88f  lea     r8, aSS; "%s\\%s"
0x18001b896  mov     ecx, edi
0x18001b898  xor     r9d, r9d; unsigned __int64 *
0x18001b89b  imul    rsi, rcx, 410h
0x18001b8a2  lea     rcx, rva dword_18004CE64[rdx]
0x18001b8a9  mov     eax, edi
0x18001b8ab  shl     rax, 9
0x18001b8af  add     rcx, rsi; pszDest
0x18001b8b2  lea     rbp, [rax+4F570h]
0x18001b8b9  add     rbp, rdx
0x18001b8bc  lea     rax, ?g_FwPersistentStoreRootKey@@3PAGA; "SYSTEM\\CurrentControlSet\\Services\\Sh"...
0x18001b8c3  mov     [rsp+298h+var_260], rbp
0x18001b8c8  mov     edx, 100h; unsigned __int64
0x18001b8cd  mov     [rsp+298h+var_268], rax
0x18001b8d2  mov     [rsp+298h+var_270], r8; unsigned __int16 *
0x18001b8d7  xor     r8d, r8d; unsigned __int16 **
0x18001b8da  mov     [rsp+298h+var_278], 800h; unsigned int
0x18001b8e2  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18001b8e7  mov     ebx, eax
0x18001b8e9  test    eax, eax
0x18001b8eb  js      loc_18001B9E1
0x18001b8f1  mov     [rsp+298h+var_258], rbp
0x18001b8f6  lea     rax, __ImageBase
0x18001b8fd  lea     rcx, rva dword_18004D064[rax]
0x18001b904  xor     r9d, r9d; unsigned __int64 *
0x18001b907  lea     rax, aMdm; "Mdm"
0x18001b90e  add     rcx, rsi; pszDest
0x18001b911  mov     [rsp+298h+var_260], rax
0x18001b916  lea     rbp, ?g_FwPersistentStoreRootKey@@3PAGA; "SYSTEM\\CurrentControlSet\\Services\\Sh"...
0x18001b91d  lea     rax, aSSS_0; "%s\\%s\\%s"
0x18001b924  mov     [rsp+298h+var_268], rbp
0x18001b929  mov     [rsp+298h+var_270], rax; unsigned __int16 *
0x18001b92e  xor     r8d, r8d; unsigned __int16 **
0x18001b931  mov     edx, 100h; unsigned __int64
0x18001b936  mov     [rsp+298h+var_278], 800h; unsigned int
0x18001b93e  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18001b943  mov     ebx, eax
0x18001b945  test    eax, eax
0x18001b947  js      short loc_18001B9C8
0x18001b949  inc     edi
0x18001b94b  lea     rdx, __ImageBase
0x18001b952  mov     dword ptr [rsi+rdx+4D264h], 1
0x18001b95d  lea     r8, aSS; "%s\\%s"
0x18001b964  cmp     edi, 2
0x18001b967  jl      loc_18001B896
0x18001b96d  lea     rax, aHypervvmcreato; "HyperVVMCreators"
0x18001b974  xor     r9d, r9d; unsigned __int64 *
0x18001b977  mov     [rsp+298h+var_260], rax
0x18001b97c  lea     rcx, ?g_HyperVVMCreatorsRegPath@@3PAGA; pszDest
0x18001b983  lea     rax, aSS; "%s\\%s"
0x18001b98a  mov     [rsp+298h+var_268], rbp
0x18001b98f  mov     [rsp+298h+var_270], rax; unsigned __int16 *
0x18001b994  xor     r8d, r8d; unsigned __int16 **
0x18001b997  mov     edx, 100h; unsigned __int64
0x18001b99c  mov     [rsp+298h+var_278], 800h; unsigned int
0x18001b9a4  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18001b9a9  mov     ebx, eax
0x18001b9ab  test    eax, eax
0x18001b9ad  jns     short loc_18001BA07
0x18001b9af  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b9b6  cmp     rcx, r12
0x18001b9b9  jz      short loc_18001BA31
0x18001b9bb  test    byte ptr [rcx+1Ch], 1
0x18001b9bf  jz      short loc_18001BA0E
0x18001b9c1  mov     edx, 14h
0x18001b9c6  jmp     short loc_18001B9F8
0x18001b9c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b9cf  cmp     rcx, r12
0x18001b9d2  jz      short loc_18001BA31
0x18001b9d4  test    byte ptr [rcx+1Ch], 1
0x18001b9d8  jz      short loc_18001BA0E
0x18001b9da  mov     edx, 13h
0x18001b9df  jmp     short loc_18001B9F8
0x18001b9e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b9e8  cmp     rcx, r12
0x18001b9eb  jz      short loc_18001BA31
  ... truncated ...
```
