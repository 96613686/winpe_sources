# WsAddCertMappingToRegistry

- ea: `0x18002373c`
- end: `0x180024012`
- name: `WsAddCertMappingToRegistry`
- size: `2262`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180020d14`
- `0x180021ff0`
- `0x180024fe8`

## callees

- `0x180008950`
- `0x1800089d0`
- `0x18001c6dc`
- `0x18001e420`
- `0x180022b7c`
- `0x180022c10`
- `0x18002373c`
- `0x180032e9c`

## import_xrefs

- `ntdll!RtlDestroyEnvironment` at `0x180023fe1`
- `ntdll!RtlDestroyEnvironment` at `0x180023fe1`
- `ntdll!RtlIntegerToUnicodeString` at `0x180023cb2`
- `ntdll!RtlIntegerToUnicodeString` at `0x180023d73`
- `ntdll!RtlIntegerToUnicodeString` at `0x180023cb2`
- `ntdll!RtlIntegerToUnicodeString` at `0x180023d73`
- `ntdll!RtlCreateEnvironment` at `0x1800237e0`
- `ntdll!RtlCreateEnvironment` at `0x1800237e0`
- `ntdll!RtlNtStatusToDosError` at `0x180023fe9`
- `ntdll!RtlNtStatusToDosError` at `0x180023fe9`
- `ntdll!RtlSetEnvironmentVariable` at `0x180023861`
- `ntdll!RtlSetEnvironmentVariable` at `0x18002392a`
- `ntdll!RtlSetEnvironmentVariable` at `0x18002399b`
- `ntdll!RtlSetEnvironmentVariable` at `0x180023a0c`
- `ntdll!RtlSetEnvironmentVariable` at `0x180023a7d`
- `ntdll!RtlSetEnvironmentVariable` at `0x180023aee`
- `ntdll!RtlSetEnvironmentVariable` at `0x180023b5f`
- `ntdll!RtlSetEnvironmentVariable` at `0x180023bd0`
- `ntdll!RtlSetEnvironmentVariable` at `0x180023c41`
- `ntdll!RtlSetEnvironmentVariable` at `0x180023d02`
- `ntdll!RtlSetEnvironmentVariable` at `0x180023dc3`
- `ntdll!RtlSetEnvironmentVariable` at `0x180023861`
- `ntdll!RtlSetEnvironmentVariable` at `0x18002392a`
- `ntdll!RtlSetEnvironmentVariable` at `0x18002399b`
- `ntdll!RtlSetEnvironmentVariable` at `0x180023a0c`
- `ntdll!RtlSetEnvironmentVariable` at `0x180023a7d`
- `ntdll!RtlSetEnvironmentVariable` at `0x180023aee`
- `ntdll!RtlSetEnvironmentVariable` at `0x180023b5f`
- `ntdll!RtlSetEnvironmentVariable` at `0x180023bd0`
- `ntdll!RtlSetEnvironmentVariable` at `0x180023c41`
- `ntdll!RtlSetEnvironmentVariable` at `0x180023d02`
- `ntdll!RtlSetEnvironmentVariable` at `0x180023dc3`
- `ntdll!RtlInitUnicodeString` at `0x18002383e`
- `ntdll!RtlInitUnicodeString` at `0x18002384c`
- `ntdll!RtlInitUnicodeString` at `0x180023906`
- `ntdll!RtlInitUnicodeString` at `0x180023915`
- `ntdll!RtlInitUnicodeString` at `0x180023977`
- `ntdll!RtlInitUnicodeString` at `0x180023986`
- `ntdll!RtlInitUnicodeString` at `0x1800239e8`
- `ntdll!RtlInitUnicodeString` at `0x1800239f7`
- `ntdll!RtlInitUnicodeString` at `0x180023a59`
- `ntdll!RtlInitUnicodeString` at `0x180023a68`
- `ntdll!RtlInitUnicodeString` at `0x180023aca`
- `ntdll!RtlInitUnicodeString` at `0x180023ad9`
- `ntdll!RtlInitUnicodeString` at `0x180023b3b`
- `ntdll!RtlInitUnicodeString` at `0x180023b4a`
- `ntdll!RtlInitUnicodeString` at `0x180023bac`
- `ntdll!RtlInitUnicodeString` at `0x180023bbb`
- `ntdll!RtlInitUnicodeString` at `0x180023c1d`
- `ntdll!RtlInitUnicodeString` at `0x180023c2c`
- `ntdll!RtlInitUnicodeString` at `0x180023c8e`
- `ntdll!RtlInitUnicodeString` at `0x180023d4f`
- `ntdll!RtlInitUnicodeString` at `0x18002383e`
- `ntdll!RtlInitUnicodeString` at `0x18002384c`
- `ntdll!RtlInitUnicodeString` at `0x180023906`
- `ntdll!RtlInitUnicodeString` at `0x180023915`
- `ntdll!RtlInitUnicodeString` at `0x180023977`
- `ntdll!RtlInitUnicodeString` at `0x180023986`
- `ntdll!RtlInitUnicodeString` at `0x1800239e8`
- `ntdll!RtlInitUnicodeString` at `0x1800239f7`
- `ntdll!RtlInitUnicodeString` at `0x180023a59`
- `ntdll!RtlInitUnicodeString` at `0x180023a68`
- `ntdll!RtlInitUnicodeString` at `0x180023aca`
- `ntdll!RtlInitUnicodeString` at `0x180023ad9`
- `ntdll!RtlInitUnicodeString` at `0x180023b3b`
- `ntdll!RtlInitUnicodeString` at `0x180023b4a`
- `ntdll!RtlInitUnicodeString` at `0x180023bac`
- `ntdll!RtlInitUnicodeString` at `0x180023bbb`
- `ntdll!RtlInitUnicodeString` at `0x180023c1d`
- `ntdll!RtlInitUnicodeString` at `0x180023c2c`
- `ntdll!RtlInitUnicodeString` at `0x180023c8e`
- `ntdll!RtlInitUnicodeString` at `0x180023d4f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180023ea0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180023ea0`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x180023f27`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x180023f27`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180023f84`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180023f84`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023fd1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023fd1`

## string_xrefs

- `0x180023c11`: `StoreName`
- `0x180023e2d`: `WsAddCertMappingToRegistry`
- `0x180023eef`: `WsAddCertMappingToRegistry`

## pseudocode

```c
ULONG __fastcall WsAddCertMappingToRegistry(__int64 a1, const WCHAR *a2, unsigned int a3)
{
  NTSTATUS v6; // edi
  NTSTATUS v7; // eax
  int v8; // r8d
  _QWORD *v9; // rcx
  int v10; // edx
  ULONG v11; // ecx
  ULONG v12; // ecx
  PWSTR v13; // rbx
  int v14; // ebx
  unsigned int v15; // eax
  __int64 v16; // rcx
  unsigned int v17; // eax
  unsigned int v18; // edi
  unsigned int v19; // eax
  LSTATUS v20; // eax
  int v21; // r8d
  unsigned int v22; // edi
  PWSTR Environment; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING Value; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-98h] BYREF
  DWORD dwDisposition; // [rsp+78h] [rbp-88h] BYREF
  HKEY hKey; // [rsp+80h] [rbp-80h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+88h] [rbp-78h] BYREF
  char v30; // [rsp+A0h] [rbp-60h] BYREF
  char v31; // [rsp+F0h] [rbp-10h] BYREF

  hKey = 0;
  Environment = 0;
  dwDisposition = 0;
  DestinationString = 0;
  Value = 0;
  memset(&SecurityAttributes, 0, 20);
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids, 0);
    }
    v6 = -1073741811;
    goto LABEL_111;
  }
  v7 = RtlCreateEnvironment(0, &Environment);
  v6 = v7;
  if ( v7 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_111;
    }
    v10 = 23;
    goto LABEL_12;
  }
  RtlInitUnicodeString(&DestinationString, L"ServerName");
  RtlInitUnicodeString(&Value, a2);
  v7 = RtlSetEnvironmentVariable(&Environment, &DestinationString, &Value);
  v6 = v7;
  if ( v7 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_111;
    }
    v10 = 24;
    goto LABEL_12;
  }
  if ( a3 )
  {
    v6 = -1073741637;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids, a3);
    }
    goto LABEL_111;
  }
  if ( *(_QWORD *)(a1 + 8) )
  {
    RtlInitUnicodeString(&DestinationString, L"Subject");
    RtlInitUnicodeString(&Value, *(PCWSTR *)(a1 + 8));
    v7 = RtlSetEnvironmentVariable(&Environment, &DestinationString, &Value);
    v6 = v7;
    if ( v7 < 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        goto LABEL_111;
      }
      v10 = 26;
      goto LABEL_12;
    }
  }
  RtlInitUnicodeString(&DestinationString, L"Issuer");
  RtlInitUnicodeString(&Value, *(PCWSTR *)(a1 + 16));
  v7 = RtlSetEnvironmentVariable(&Environment, &DestinationString, &Value);
  v6 = v7;
  if ( v7 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_111;
    }
    v10 = 27;
    goto LABEL_12;
  }
  RtlInitUnicodeString(&DestinationString, L"ThumbPrint");
  RtlInitUnicodeString(&Value, *(PCWSTR *)(a1 + 24));
  v7 = RtlSetEnvironmentVariable(&Environment, &DestinationString, &Value);
  v6 = v7;
  if ( v7 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_111;
    }
    v10 = 28;
    goto LABEL_12;
  }
  RtlInitUnicodeString(&DestinationString, L"FriendlyName");
  RtlInitUnicodeString(&Value, *(PCWSTR *)(a1 + 32));
  v7 = RtlSetEnvironmentVariable(&Environment, &DestinationString, &Value);
  v6 = v7;
  if ( v7 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_111;
    }
    v10 = 29;
    goto LABEL_12;
  }
  RtlInitUnicodeString(&DestinationString, L"NotBefore");
  RtlInitUnicodeString(&Value, *(PCWSTR *)(a1 + 40));
  v7 = RtlSetEnvironmentVariable(&Environment, &DestinationString, &Value);
  v6 = v7;
  if ( v7 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_111;
    }
    v10 = 30;
    goto LABEL_12;
  }
  RtlInitUnicodeString(&DestinationString, L"NotAfter");
  RtlInitUnicodeString(&Value, *(PCWSTR *)(a1 + 48));
  v7 = RtlSetEnvironmentVariable(&Environment, &DestinationString, &Value);
  v6 = v7;
  if ( v7 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_111;
    }
    v10 = 31;
    goto LABEL_12;
  }
  RtlInitUnicodeString(&DestinationString, L"StoreLocation");
  RtlInitUnicodeString(&Value, *(PCWSTR *)(a1 + 56));
  v7 = RtlSetEnvironmentVariable(&Environment, &DestinationString, &Value);
  v6 = v7;
  if ( v7 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_111;
    }
    v10 = 32;
    goto LABEL_12;
  }
  RtlInitUnicodeString(&DestinationString, L"StoreName");
  RtlInitUnicodeString(&Value, *(PCWSTR *)(a1 + 64));
  v7 = RtlSetEnvironmentVariable(&Environment, &DestinationString, &Value);
  v6 = v7;
  if ( v7 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_111;
    }
    v10 = 33;
    goto LABEL_12;
  }
  RtlInitUnicodeString(&DestinationString, L"Type");
  v11 = *(_DWORD *)(a1 + 80);
  Value.Buffer = (PWSTR)&v30;
  *(_DWORD *)&Value.Length = 4325442;
  v7 = RtlIntegerToUnicodeString(v11, 0xAu, &Value);
  v6 = v7;
  if ( v7 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_111;
    }
    v10 = 34;
    goto LABEL_12;
  }
  v7 = RtlSetEnvironmentVariable(&Environment, &DestinationString, &Value);
  v6 = v7;
  if ( v7 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_111;
    }
    v10 = 35;
    goto LABEL_12;
  }
  RtlInitUnicodeString(&DestinationString, L"Flags");
  v12 = *(_DWORD *)(a1 + 84);
  Value.Buffer = (PWSTR)&v31;
  *(_DWORD *)&Value.Length = 4325442;
  v7 = RtlIntegerToUnicodeString(v12, 0xAu, &Value);
  v6 = v7;
  if ( v7 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_111;
    }
    v10 = 36;
    goto LABEL_12;
  }
  v7 = RtlSetEnvironmentVariable(&Environment, &DestinationString, &Value);
  v6 = v7;
  if ( v7 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_111;
    }
    v10 = 37;
LABEL_12:
    WPP_SF_LS(v9[2], v10, v8, v7, (__int64)a2);
    goto LABEL_111;
  }
  v13 = Environment;
  if ( *Environment )
  {
    while ( *v13 || *++v13 )
      ++v13;
  }
  v14 = (_DWORD)v13 - (_DWORD)Environment;
  v15 = WsImpersonateClient2("WsAddCertMappingToRegistry", 1126);
  if ( v15 )
  {
    v16 = v15;
    goto LABEL_91;
  }
  SecurityAttributes.lpSecurityDescriptor = pSecurityDescriptor;
  SecurityAttributes.nLength = 24;
  SecurityAttributes.bInheritHandle = 0;
  v17 = RegCreateKeyExW(
          HKEY_LOCAL_MACHINE,
          &word_18004E9AC,
          0,
          0,
          0,
          0xE0002u,
          &SecurityAttributes,
          &hKey,
          &dwDisposition);
  v18 = v17;
  if ( !v17 )
  {
    if ( dwDisposition == 2 )
    {
      v19 = RegSetKeySecurity(hKey, 7u, pSecurityDescriptor);
      if ( v19 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids, v19);
        }
      }
    }
    WsRevertToSelf2(0, 0);
    v20 = RegSetValueExW(hKey, a2, 0, 7u, (const BYTE *)Environment, v14 + 2);
    v22 = v20;
    if ( !v20 )
    {
      v6 = 0;
      goto LABEL_111;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_LS(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, v21, v20, (__int64)a2);
    }
    v16 = v22;
LABEL_91:
    v6 = NetpApiStatusToNtStatus(v16);
    goto LABEL_111;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids, v17);
  }
  v6 = NetpApiStatusToNtStatus(v18);
  WsRevertToSelf2("WsAddCertMappingToRegistry", 1214);
LABEL_111:
  if ( hKey )
    RegCloseKey(hKey);
  if ( Environment )
    RtlDestroyEnvironment(Environment);
  return RtlNtStatusToDosError(v6);
}

```

## disassembly

```asm
0x18002373c  mov     [rsp-8+arg_18], rbx
0x180023741  push    rbp
0x180023742  push    rsi
0x180023743  push    rdi
0x180023744  push    r14
0x180023746  push    r15
0x180023748  lea     rbp, [rsp-50h]
0x18002374d  sub     rsp, 150h
0x180023754  mov     rax, cs:__security_cookie
0x18002375b  xor     rax, rsp
0x18002375e  mov     [rbp+70h+var_30], rax
0x180023762  xor     r15d, r15d
0x180023765  xor     eax, eax
0x180023767  mov     [rbp+70h+hKey], r15
0x18002376b  xorps   xmm0, xmm0
0x18002376e  mov     [rsp+170h+Environment], r15
0x180023773  xorps   xmm1, xmm1
0x180023776  mov     [rsp+170h+dwDisposition], r15d
0x18002377b  mov     r14d, r8d
0x18002377e  mov     [rbp+70h+SecurityAttributes.bInheritHandle], eax
0x180023781  mov     rsi, rdx
0x180023784  mov     rbx, rcx
0x180023787  movups  xmmword ptr [rsp+170h+DestinationString.Length], xmm0
0x18002378c  movups  xmmword ptr [rsp+170h+Value.Length], xmm1
0x180023791  movups  xmmword ptr [rbp+70h+SecurityAttributes.nLength], xmm0
0x180023795  test    rdx, rdx
0x180023798  jnz     short loc_1800237D9
0x18002379a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800237a1  lea     rbx, WPP_GLOBAL_Control
0x1800237a8  cmp     rcx, rbx
0x1800237ab  jz      short loc_1800237CF
0x1800237ad  test    byte ptr [rcx+1Ch], 2
0x1800237b1  jz      short loc_1800237CF
0x1800237b3  cmp     byte ptr [rcx+19h], 1
0x1800237b7  jb      short loc_1800237CF
0x1800237b9  mov     rcx, [rcx+10h]
0x1800237bd  lea     edx, [rsi+16h]
0x1800237c0  xor     r9d, r9d
0x1800237c3  lea     r8, WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids
0x1800237ca  call    WPP_SF_S
0x1800237cf  mov     edi, 0C000000Dh
0x1800237d4  jmp     loc_180023FC8
0x1800237d9  lea     rdx, [rsp+170h+Environment]; Environment
0x1800237de  xor     ecx, ecx; Inherit
0x1800237e0  call    cs:__imp_RtlCreateEnvironment
0x1800237e6  mov     edi, eax
0x1800237e8  test    eax, eax
0x1800237ea  jns     short loc_180023832
0x1800237ec  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800237f3  lea     rbx, WPP_GLOBAL_Control
0x1800237fa  cmp     rcx, rbx
0x1800237fd  jz      loc_180023FC8
0x180023803  test    byte ptr [rcx+1Ch], 2
0x180023807  jz      loc_180023FC8
0x18002380d  cmp     byte ptr [rcx+19h], 1
0x180023811  jb      loc_180023FC8
0x180023817  mov     edx, 17h
0x18002381c  mov     rcx, [rcx+10h]
0x180023820  mov     r9d, eax
0x180023823  mov     qword ptr [rsp+170h+dwOptions], rsi
0x180023828  call    WPP_SF_LS
0x18002382d  jmp     loc_180023FC8
0x180023832  lea     rdx, aServername; "ServerName"
0x180023839  lea     rcx, [rsp+170h+DestinationString]; DestinationString
0x18002383e  call    cs:__imp_RtlInitUnicodeString
0x180023844  mov     rdx, rsi; SourceString
0x180023847  lea     rcx, [rsp+170h+Value]; DestinationString
0x18002384c  call    cs:__imp_RtlInitUnicodeString
0x180023852  lea     r8, [rsp+170h+Value]; Value
0x180023857  lea     rdx, [rsp+170h+DestinationString]; Name
0x18002385c  lea     rcx, [rsp+170h+Environment]; Environment
0x180023861  call    cs:__imp_RtlSetEnvironmentVariable
0x180023867  mov     edi, eax
0x180023869  test    eax, eax
0x18002386b  jns     short loc_1800238A2
0x18002386d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180023874  lea     rbx, WPP_GLOBAL_Control
0x18002387b  cmp     rcx, rbx
0x18002387e  jz      loc_180023FC8
0x180023884  test    byte ptr [rcx+1Ch], 2
0x180023888  jz      loc_180023FC8
0x18002388e  cmp     byte ptr [rcx+19h], 1
0x180023892  jb      loc_180023FC8
0x180023898  mov     edx, 18h
0x18002389d  jmp     loc_18002381C
0x1800238a2  test    r14d, r14d
0x1800238a5  jz      short loc_1800238F4
0x1800238a7  mov     edi, 0C00000BBh
0x1800238ac  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800238b3  lea     rbx, WPP_GLOBAL_Control
0x1800238ba  cmp     rcx, rbx
0x1800238bd  jz      loc_180023FC8
0x1800238c3  test    byte ptr [rcx+1Ch], 2
0x1800238c7  jz      loc_180023FC8
0x1800238cd  cmp     byte ptr [rcx+19h], 1
0x1800238d1  jb      loc_180023FC8
0x1800238d7  mov     rcx, [rcx+10h]
0x1800238db  lea     r8, WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids
0x1800238e2  mov     edx, 19h
0x1800238e7  mov     r9d, r14d
0x1800238ea  call    WPP_SF_d
0x1800238ef  jmp     loc_180023FC8
0x1800238f4  cmp     [rbx+8], r15
0x1800238f8  jz      short loc_18002396B
0x1800238fa  lea     rdx, aSubject; "Subject"
0x180023901  lea     rcx, [rsp+170h+DestinationString]; DestinationString
0x180023906  call    cs:__imp_RtlInitUnicodeString
0x18002390c  mov     rdx, [rbx+8]; SourceString
0x180023910  lea     rcx, [rsp+170h+Value]; DestinationString
0x180023915  call    cs:__imp_RtlInitUnicodeString
0x18002391b  lea     r8, [rsp+170h+Value]; Value
0x180023920  lea     rdx, [rsp+170h+DestinationString]; Name
0x180023925  lea     rcx, [rsp+170h+Environment]; Environment
0x18002392a  call    cs:__imp_RtlSetEnvironmentVariable
0x180023930  mov     edi, eax
0x180023932  test    eax, eax
0x180023934  jns     short loc_18002396B
0x180023936  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18002393d  lea     rbx, WPP_GLOBAL_Control
0x180023944  cmp     rcx, rbx
0x180023947  jz      loc_180023FC8
0x18002394d  test    byte ptr [rcx+1Ch], 2
0x180023951  jz      loc_180023FC8
0x180023957  cmp     byte ptr [rcx+19h], 1
0x18002395b  jb      loc_180023FC8
0x180023961  mov     edx, 1Ah
0x180023966  jmp     loc_18002381C
0x18002396b  lea     rdx, aIssuer; "Issuer"
0x180023972  lea     rcx, [rsp+170h+DestinationString]; DestinationString
0x180023977  call    cs:__imp_RtlInitUnicodeString
0x18002397d  mov     rdx, [rbx+10h]; SourceString
0x180023981  lea     rcx, [rsp+170h+Value]; DestinationString
0x180023986  call    cs:__imp_RtlInitUnicodeString
0x18002398c  lea     r8, [rsp+170h+Value]; Value
0x180023991  lea     rdx, [rsp+170h+DestinationString]; Name
0x180023996  lea     rcx, [rsp+170h+Environment]; Environment
0x18002399b  call    cs:__imp_RtlSetEnvironmentVariable
0x1800239a1  mov     edi, eax
0x1800239a3  test    eax, eax
0x1800239a5  jns     short loc_1800239DC
0x1800239a7  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800239ae  lea     rbx, WPP_GLOBAL_Control
0x1800239b5  cmp     rcx, rbx
0x1800239b8  jz      loc_180023FC8
0x1800239be  test    byte ptr [rcx+1Ch], 2
0x1800239c2  jz      loc_180023FC8
0x1800239c8  cmp     byte ptr [rcx+19h], 1
0x1800239cc  jb      loc_180023FC8
0x1800239d2  mov     edx, 1Bh
0x1800239d7  jmp     loc_18002381C
0x1800239dc  lea     rdx, aThumbprint; "ThumbPrint"
0x1800239e3  lea     rcx, [rsp+170h+DestinationString]; DestinationString
0x1800239e8  call    cs:__imp_RtlInitUnicodeString
0x1800239ee  mov     rdx, [rbx+18h]; SourceString
0x1800239f2  lea     rcx, [rsp+170h+Value]; DestinationString
0x1800239f7  call    cs:__imp_RtlInitUnicodeString
0x1800239fd  lea     r8, [rsp+170h+Value]; Value
0x180023a02  lea     rdx, [rsp+170h+DestinationString]; Name
0x180023a07  lea     rcx, [rsp+170h+Environment]; Environment
0x180023a0c  call    cs:__imp_RtlSetEnvironmentVariable
0x180023a12  mov     edi, eax
0x180023a14  test    eax, eax
0x180023a16  jns     short loc_180023A4D
0x180023a18  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180023a1f  lea     rbx, WPP_GLOBAL_Control
0x180023a26  cmp     rcx, rbx
0x180023a29  jz      loc_180023FC8
0x180023a2f  test    byte ptr [rcx+1Ch], 2
0x180023a33  jz      loc_180023FC8
0x180023a39  cmp     byte ptr [rcx+19h], 1
0x180023a3d  jb      loc_180023FC8
0x180023a43  mov     edx, 1Ch
0x180023a48  jmp     loc_18002381C
0x180023a4d  lea     rdx, aFriendlyname; "FriendlyName"
0x180023a54  lea     rcx, [rsp+170h+DestinationString]; DestinationString
0x180023a59  call    cs:__imp_RtlInitUnicodeString
0x180023a5f  mov     rdx, [rbx+20h]; SourceString
0x180023a63  lea     rcx, [rsp+170h+Value]; DestinationString
0x180023a68  call    cs:__imp_RtlInitUnicodeString
0x180023a6e  lea     r8, [rsp+170h+Value]; Value
0x180023a73  lea     rdx, [rsp+170h+DestinationString]; Name
0x180023a78  lea     rcx, [rsp+170h+Environment]; Environment
0x180023a7d  call    cs:__imp_RtlSetEnvironmentVariable
0x180023a83  mov     edi, eax
0x180023a85  test    eax, eax
0x180023a87  jns     short loc_180023ABE
0x180023a89  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180023a90  lea     rbx, WPP_GLOBAL_Control
0x180023a97  cmp     rcx, rbx
0x180023a9a  jz      loc_180023FC8
0x180023aa0  test    byte ptr [rcx+1Ch], 2
0x180023aa4  jz      loc_180023FC8
0x180023aaa  cmp     byte ptr [rcx+19h], 1
0x180023aae  jb      loc_180023FC8
0x180023ab4  mov     edx, 1Dh
0x180023ab9  jmp     loc_18002381C
0x180023abe  lea     rdx, aNotbefore; "NotBefore"
0x180023ac5  lea     rcx, [rsp+170h+DestinationString]; DestinationString
0x180023aca  call    cs:__imp_RtlInitUnicodeString
0x180023ad0  mov     rdx, [rbx+28h]; SourceString
0x180023ad4  lea     rcx, [rsp+170h+Value]; DestinationString
0x180023ad9  call    cs:__imp_RtlInitUnicodeString
0x180023adf  lea     r8, [rsp+170h+Value]; Value
0x180023ae4  lea     rdx, [rsp+170h+DestinationString]; Name
0x180023ae9  lea     rcx, [rsp+170h+Environment]; Environment
0x180023aee  call    cs:__imp_RtlSetEnvironmentVariable
0x180023af4  mov     edi, eax
0x180023af6  test    eax, eax
0x180023af8  jns     short loc_180023B2F
0x180023afa  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180023b01  lea     rbx, WPP_GLOBAL_Control
0x180023b08  cmp     rcx, rbx
0x180023b0b  jz      loc_180023FC8
0x180023b11  test    byte ptr [rcx+1Ch], 2
0x180023b15  jz      loc_180023FC8
0x180023b1b  cmp     byte ptr [rcx+19h], 1
0x180023b1f  jb      loc_180023FC8
0x180023b25  mov     edx, 1Eh
0x180023b2a  jmp     loc_18002381C
0x180023b2f  lea     rdx, aNotafter; "NotAfter"
0x180023b36  lea     rcx, [rsp+170h+DestinationString]; DestinationString
0x180023b3b  call    cs:__imp_RtlInitUnicodeString
0x180023b41  mov     rdx, [rbx+30h]; SourceString
0x180023b45  lea     rcx, [rsp+170h+Value]; DestinationString
0x180023b4a  call    cs:__imp_RtlInitUnicodeString
0x180023b50  lea     r8, [rsp+170h+Value]; Value
0x180023b55  lea     rdx, [rsp+170h+DestinationString]; Name
0x180023b5a  lea     rcx, [rsp+170h+Environment]; Environment
0x180023b5f  call    cs:__imp_RtlSetEnvironmentVariable
0x180023b65  mov     edi, eax
0x180023b67  test    eax, eax
0x180023b69  jns     short loc_180023BA0
0x180023b6b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180023b72  lea     rbx, WPP_GLOBAL_Control
0x180023b79  cmp     rcx, rbx
0x180023b7c  jz      loc_180023FC8
0x180023b82  test    byte ptr [rcx+1Ch], 2
0x180023b86  jz      loc_180023FC8
0x180023b8c  cmp     byte ptr [rcx+19h], 1
0x180023b90  jb      loc_180023FC8
0x180023b96  mov     edx, 1Fh
0x180023b9b  jmp     loc_18002381C
0x180023ba0  lea     rdx, aStorelocation; "StoreLocation"
0x180023ba7  lea     rcx, [rsp+170h+DestinationString]; DestinationString
0x180023bac  call    cs:__imp_RtlInitUnicodeString
0x180023bb2  mov     rdx, [rbx+38h]; SourceString
0x180023bb6  lea     rcx, [rsp+170h+Value]; DestinationString
0x180023bbb  call    cs:__imp_RtlInitUnicodeString
0x180023bc1  lea     r8, [rsp+170h+Value]; Value
0x180023bc6  lea     rdx, [rsp+170h+DestinationString]; Name
0x180023bcb  lea     rcx, [rsp+170h+Environment]; Environment
0x180023bd0  call    cs:__imp_RtlSetEnvironmentVariable
0x180023bd6  mov     edi, eax
0x180023bd8  test    eax, eax
0x180023bda  jns     short loc_180023C11
0x180023bdc  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180023be3  lea     rbx, WPP_GLOBAL_Control
0x180023bea  cmp     rcx, rbx
0x180023bed  jz      loc_180023FC8
0x180023bf3  test    byte ptr [rcx+1Ch], 2
0x180023bf7  jz      loc_180023FC8
0x180023bfd  cmp     byte ptr [rcx+19h], 1
0x180023c01  jb      loc_180023FC8
0x180023c07  mov     edx, 20h ; ' '
0x180023c0c  jmp     loc_18002381C
0x180023c11  lea     rdx, aStorename; "StoreName"
0x180023c18  lea     rcx, [rsp+170h+DestinationString]; DestinationString
0x180023c1d  call    cs:__imp_RtlInitUnicodeString
0x180023c23  mov     rdx, [rbx+40h]; SourceString
0x180023c27  lea     rcx, [rsp+170h+Value]; DestinationString
0x180023c2c  call    cs:__imp_RtlInitUnicodeString
0x180023c32  lea     r8, [rsp+170h+Value]; Value
0x180023c37  lea     rdx, [rsp+170h+DestinationString]; Name
0x180023c3c  lea     rcx, [rsp+170h+Environment]; Environment
0x180023c41  call    cs:__imp_RtlSetEnvironmentVariable
0x180023c47  mov     edi, eax
0x180023c49  test    eax, eax
0x180023c4b  jns     short loc_180023C82
0x180023c4d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180023c54  lea     rbx, WPP_GLOBAL_Control
0x180023c5b  cmp     rcx, rbx
0x180023c5e  jz      loc_180023FC8
0x180023c64  test    byte ptr [rcx+1Ch], 2
0x180023c68  jz      loc_180023FC8
0x180023c6e  cmp     byte ptr [rcx+19h], 1
0x180023c72  jb      loc_180023FC8
0x180023c78  mov     edx, 21h ; '!'
0x180023c7d  jmp     loc_18002381C
0x180023c82  lea     rdx, aType; "Type"
0x180023c89  lea     rcx, [rsp+170h+DestinationString]; DestinationString
0x180023c8e  call    cs:__imp_RtlInitUnicodeString
0x180023c94  mov     ecx, [rbx+50h]; Value
0x180023c97  lea     rax, [rbp+70h+var_D0]
0x180023c9b  lea     r8, [rsp+170h+Value]; String
0x180023ca0  mov     [rsp+170h+Value.Buffer], rax
0x180023ca5  mov     edx, 0Ah; Base
0x180023caa  mov     dword ptr [rsp+170h+Value.Length], 420042h
0x180023cb2  call    cs:__imp_RtlIntegerToUnicodeString
0x180023cb8  mov     edi, eax
0x180023cba  test    eax, eax
  ... truncated ...
```
