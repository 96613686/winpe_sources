# ShouldSecurebootSkipAnyUpdate(ulong,ulong *,ushort const * *,ushort * *,ulong *)

- ea: `0x18003d8e0`
- end: `0x18003dce2`
- name: `?ShouldSecurebootSkipAnyUpdate@@YAJKPEAKPEAPEBGPEAPEAG0@Z`
- size: `1026`
- prototype: `__int64 __fastcall(int, unsigned int *, const unsigned __int16 **, unsigned __int16 **, unsigned int *)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001e5d0`
- `0x180034634`

## callees

- `0x1800394b0`
- `0x18003c0b8`
- `0x18003c688`
- `0x18003d3cc`
- `0x18003d444`
- `0x18003d87c`
- `0x18003d8e0`
- `0x18003dce8`
- `0x18003dea4`
- `0x18003e110`
- `0x18003e2cc`
- `0x18003e360`
- `0x18003e45c`
- `0x18003e4f4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003dc93`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003dcac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003dc93`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003dcac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003dc85`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003dc9e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003dc85`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003dc9e`
- `SHLWAPI!StrCmpIW` at `0x18003d9ef`
- `SHLWAPI!StrCmpIW` at `0x18003d9ef`

## string_xrefs

- `0x18003d9af`: `SkipUpdateOnIncompatibleUEFI_OlderSystems`
- `0x18003daf3`: `ToshibaBadSystemProduct`
- `0x18003dcb9`: `ShouldSecurebootSkipAnyUpdate`
- `0x18003d9dc`: `SystemManufacturerRegistryFailed`
- `0x18003da35`: `BaseBoardProductRegistryFailed`
- `0x18003d97c`: `ShouldSkipSecureBootUpdatesOnOlderSystemsFailed`
- `0x18003d9a3`: `Skipping update on older AMI devices`
- `0x18003da59`: `Skipping update on FUJITSU %ls devices`
- `0x18003d9ff`: `Skipping update on Apple Inc devices`
- `0x18003daa5`: `SystemProductName`
- `0x18003da83`: `Skipping update on %ls %ls devices`
- `0x18003dae0`: `Skipping update on %ls %ls devices`
- `0x18003db14`: `Skipping update on %ls %ls devices`
- `0x18003db48`: `ShouldSecureBootSkipUpdateOnHPFailed`
- `0x18003dabe`: `SystemProductNameRegistryFailed`
- `0x18003dbb8`: `ShouldSecurebootSkipUpdateOnARMFailed`
- `0x18003db7d`: `ShouldSecureBootSkipDBXUpdateOnHPFailed`
- `0x18003dbf2`: `ShouldSecurebootSkipUpdateOnSamsungFailed`
- `0x18003dc35`: `ShouldSecurebootSkipAnyUpdate returned: %x\nActionString: %ls\nSystemManufacturer: %ls\nBaseBoardProduct: %ls\n*pSkipUpdates: %d\nShouldSkipUpdateOnHP: %d\nShouldSkipUpdateOnARM: %d\nShouldSkipUpdateOnSamsung: %d\nShouldSkipDBXUpdateOnHP: %d\nShouldSkipDBXReasonHP: %ls\nShouldSkipReasonHP: %ls\nShouldSkipReasonARM: %ls\nuefiSecAppVersionRTVariable: %lx`

## pseudocode

```c
__int64 __fastcall ShouldSecurebootSkipAnyUpdate(
        int a1,
        unsigned int *a2,
        const unsigned __int16 **a3,
        unsigned __int16 **a4,
        unsigned int *a5)
{
  unsigned __int16 *v5; // r12
  unsigned __int16 *v6; // r15
  unsigned __int16 *v10; // rbx
  __int64 result; // rax
  int v12; // ebx
  const unsigned __int16 *v13; // rsi
  unsigned __int16 *v14; // r13
  int v15; // r9d
  const unsigned __int16 *v16; // rax
  int HWSystemInformationFromRegistry; // eax
  int v18; // eax
  int v19; // eax
  int v20; // edx
  unsigned __int16 *v21; // rax
  int v22; // eax
  int v23; // r8d
  unsigned __int16 *v24; // rax
  int v25; // eax
  HANDLE ProcessHeap; // rax
  HANDLE v27; // rax
  unsigned int v28; // [rsp+68h] [rbp-39h]
  int v29; // [rsp+70h] [rbp-31h] BYREF
  int v30; // [rsp+74h] [rbp-2Dh] BYREF
  unsigned __int16 *v31; // [rsp+78h] [rbp-29h] BYREF
  int v32; // [rsp+80h] [rbp-21h] BYREF
  int v33; // [rsp+84h] [rbp-1Dh] BYREF
  unsigned int v34; // [rsp+88h] [rbp-19h] BYREF
  PCWSTR psz1; // [rsp+90h] [rbp-11h] BYREF
  LPVOID lpMem; // [rsp+98h] [rbp-9h] BYREF
  unsigned __int16 *v37; // [rsp+A0h] [rbp-1h] BYREF
  unsigned __int16 *v38; // [rsp+A8h] [rbp+7h] BYREF
  unsigned __int16 *v39; // [rsp+B0h] [rbp+Fh] BYREF
  unsigned __int16 *v40; // [rsp+B8h] [rbp+17h] BYREF
  int v42; // [rsp+108h] [rbp+67h] BYREF

  v5 = 0;
  lpMem = 0;
  v37 = 0;
  v6 = 0;
  psz1 = 0;
  v33 = 0;
  v32 = 0;
  v31 = 0;
  v42 = 0;
  v39 = 0;
  v29 = 0;
  v38 = 0;
  v34 = 0;
  v40 = 0;
  v30 = 0;
  *a2 = 0;
  if ( (unsigned int)ShouldSkipDeviceCheck((const unsigned __int16 **)&v40) )
  {
    v10 = v40;
    SBServicingLogMessage((wchar_t *)L"Skipping firmware check due to %ls", v40);
    *a2 = 0;
    result = 0;
    *a3 = v10;
    return result;
  }
  v12 = ShouldSkipSecureBootUpdatesOnOlderSystems(&v33);
  if ( v12 < 0 )
  {
    v13 = L"ShouldSkipSecureBootUpdatesOnOlderSystemsFailed";
LABEL_5:
    v14 = v31;
    v15 = v30;
LABEL_43:
    v20 = v42;
    goto LABEL_44;
  }
  v13 = L"Passed";
  if ( v33 )
  {
    *a2 |= 0x1946u;
    SBServicingLogMessage((wchar_t *)L"Skipping update on older AMI devices");
    v16 = L"SkipUpdateOnIncompatibleUEFI_OlderSystems";
LABEL_8:
    *a3 = v16;
    goto LABEL_5;
  }
  HWSystemInformationFromRegistry = GetHWSystemInformationFromRegistry(
                                      L"HARDWARE\\DESCRIPTION\\System\\BIOS",
                                      L"SystemManufacturer",
                                      (unsigned __int16 **)&psz1);
  v6 = (unsigned __int16 *)psz1;
  v12 = HWSystemInformationFromRegistry;
  if ( HWSystemInformationFromRegistry < 0 )
  {
    v13 = L"SystemManufacturerRegistryFailed";
    goto LABEL_5;
  }
  if ( !StrCmpIW(psz1, L"Apple Inc.") )
  {
    *a2 |= 0x1946u;
    SBServicingLogMessage((wchar_t *)L"Skipping update on Apple Inc devices");
    v16 = L"AppleBadBaseBoardProduct";
    goto LABEL_8;
  }
  v18 = GetHWSystemInformationFromRegistry(
          L"HARDWARE\\DESCRIPTION\\System\\BIOS",
          L"BaseBoardProduct",
          (unsigned __int16 **)&lpMem);
  v5 = (unsigned __int16 *)lpMem;
  v12 = v18;
  if ( v18 < 0 )
  {
    v13 = L"BaseBoardProductRegistryFailed";
    goto LABEL_5;
  }
  if ( ShouldSkipUpdateOnFujitsu(v6, (const unsigned __int16 *)lpMem) )
  {
    *a2 |= 0x1946u;
    SBServicingLogMessage((wchar_t *)L"Skipping update on FUJITSU %ls devices", v5);
    v16 = L"FujitsuBadBaseBoardProduct";
    goto LABEL_8;
  }
  if ( ShouldSkipUpdateOnInsydeFirmware(v6, v5) )
  {
    *a2 |= 0x1946u;
    SBServicingLogMessage((wchar_t *)L"Skipping update on %ls %ls devices", v6, v5);
    v16 = L"InsydeBadBaseBoardProduct";
    goto LABEL_8;
  }
  v12 = GetHWSystemInformationFromRegistry(L"HARDWARE\\DESCRIPTION\\System\\BIOS", L"SystemProductName", &v37);
  if ( v12 < 0 )
  {
    v13 = L"SystemProductNameRegistryFailed";
    goto LABEL_5;
  }
  if ( ShouldSecureBootSkipUpdateOnToshiba(v6, v37) )
  {
    *a2 |= 0x1946u;
    SBServicingLogMessage((wchar_t *)L"Skipping update on %ls %ls devices", v6, v37);
    v16 = L"ToshibaBadSystemProduct";
    goto LABEL_8;
  }
  if ( ShouldSecureBootSkipUpdateOnAsus(v6, v5) )
  {
    *a2 |= 0x1946u;
    SBServicingLogMessage((wchar_t *)L"Skipping update on %ls %ls devices", v6, v5);
    v16 = L"AsusBadBaseBoardProduct";
    goto LABEL_8;
  }
  v12 = ShouldSecureBootSkipUpdateOnHP(&v32, (const unsigned __int16 **)&v31, a4);
  if ( v12 < 0 )
  {
    v13 = L"ShouldSecureBootSkipUpdateOnHPFailed";
    goto LABEL_5;
  }
  v14 = v31;
  if ( v32 )
  {
    *a2 |= 0x1944u;
    *a3 = v14;
  }
  v19 = ShouldSecurebootSkipDBXUpdateOnHP(&v42, (const unsigned __int16 **)&v39);
  v20 = v42;
  v12 = v19;
  if ( v19 < 0 )
  {
    v13 = L"ShouldSecureBootSkipDBXUpdateOnHPFailed";
LABEL_31:
    v15 = v30;
LABEL_44:
    v23 = v29;
    goto LABEL_45;
  }
  if ( v42 )
  {
    v21 = v39;
    *a2 |= 2u;
    *a3 = v21;
    goto LABEL_31;
  }
  v22 = ShouldSecurebootSkipUpdateOnARM(&v29, (const unsigned __int16 **)&v38, &v34);
  v23 = v29;
  v12 = v22;
  if ( v22 >= 0 )
  {
    if ( !v29 )
    {
      v25 = ShouldSecurebootSkipUpdateOnSamsung(v6, &v30);
      v15 = v30;
      v12 = v25;
      if ( v25 >= 0 )
      {
        if ( v30 )
        {
          *a2 |= 0x1944u;
          *a3 = L"SamsungBadSKU";
        }
      }
      else
      {
        v13 = L"ShouldSecurebootSkipUpdateOnSamsungFailed";
      }
      goto LABEL_43;
    }
    v24 = v38;
    *a2 |= 0x1940u;
    *a3 = v24;
  }
  else
  {
    v13 = L"ShouldSecurebootSkipUpdateOnARMFailed";
  }
  v20 = v42;
  v15 = v30;
LABEL_45:
  if ( (a1 & *a2) == 0 )
    *a3 = &sourceString;
  v28 = v34;
  *a5 = v34;
  SBServicingLogMessage(
    (wchar_t *)L"ShouldSecurebootSkipAnyUpdate returned: %x\n"
                "ActionString: %ls\n"
                "SystemManufacturer: %ls\n"
                "BaseBoardProduct: %ls\n"
                "*pSkipUpdates: %d\n"
                "ShouldSkipUpdateOnHP: %d\n"
                "ShouldSkipUpdateOnARM: %d\n"
                "ShouldSkipUpdateOnSamsung: %d\n"
                "ShouldSkipDBXUpdateOnHP: %d\n"
                "ShouldSkipDBXReasonHP: %ls\n"
                "ShouldSkipReasonHP: %ls\n"
                "ShouldSkipReasonARM: %ls\n"
                "uefiSecAppVersionRTVariable: %lx",
    (unsigned int)v12,
    v13,
    v6,
    v5,
    *a2,
    v32,
    v23,
    v15,
    v20,
    v39,
    v14,
    v38,
    v28);
  if ( v6 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v6);
  }
  if ( v5 )
  {
    v27 = GetProcessHeap();
    HeapFree(v27, 0, v5);
  }
  if ( v12 < 0 )
    SBServicingCoreTelemetryProvider::SBServicingCoreFunctionFailed(L"ShouldSecurebootSkipAnyUpdate", v13);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18003d8e0  mov     [rsp-8+arg_10], rbx
0x18003d8e5  mov     [rsp-8+arg_0], ecx
0x18003d8e9  push    rbp
0x18003d8ea  push    rsi
0x18003d8eb  push    rdi
0x18003d8ec  push    r12
0x18003d8ee  push    r13
0x18003d8f0  push    r14
0x18003d8f2  push    r15
0x18003d8f4  lea     rbp, [rsp-1Fh]
0x18003d8f9  sub     rsp, 0C0h
0x18003d900  xor     esi, esi
0x18003d902  lea     rcx, [rbp+4Fh+var_38]; unsigned __int16 **
0x18003d906  mov     r12d, esi
0x18003d909  mov     [rbp+4Fh+lpMem], rsi
0x18003d90d  mov     [rbp+4Fh+var_50], rsi
0x18003d911  mov     r15d, esi
0x18003d914  mov     [rbp+4Fh+psz1], rsi
0x18003d918  mov     r13, r9
0x18003d91b  mov     [rbp+4Fh+var_6C], esi
0x18003d91e  mov     r14, r8
0x18003d921  mov     [rbp+4Fh+var_70], esi
0x18003d924  mov     rdi, rdx
0x18003d927  mov     [rbp+4Fh+var_78], rsi
0x18003d92b  mov     [rbp+4Fh+arg_8], esi
0x18003d92e  mov     [rbp+4Fh+var_40], rsi
0x18003d932  mov     [rbp+4Fh+var_80], esi
0x18003d935  mov     [rbp+4Fh+var_48], rsi
0x18003d939  mov     [rbp+4Fh+var_68], esi
0x18003d93c  mov     [rbp+4Fh+var_38], rsi
0x18003d940  mov     [rbp+4Fh+var_7C], esi
0x18003d943  mov     [rdx], esi
0x18003d945  call    ?ShouldSkipDeviceCheck@@YAHPEAPEBG@Z; ShouldSkipDeviceCheck(ushort const * *)
0x18003d94a  test    eax, eax
0x18003d94c  jz      short loc_18003D96D
0x18003d94e  mov     rbx, [rbp+4Fh+var_38]
0x18003d952  lea     rcx, aSkippingFirmwa; "Skipping firmware check due to %ls"
0x18003d959  mov     rdx, rbx
0x18003d95c  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18003d961  mov     [rdi], esi
0x18003d963  xor     eax, eax
0x18003d965  mov     [r14], rbx
0x18003d968  jmp     loc_18003DCC7
0x18003d96d  lea     rcx, [rbp+4Fh+var_6C]; int *
0x18003d971  call    ?ShouldSkipSecureBootUpdatesOnOlderSystems@@YAJPEAH@Z; ShouldSkipSecureBootUpdatesOnOlderSystems(int *)
0x18003d976  mov     ebx, eax
0x18003d978  test    eax, eax
0x18003d97a  jns     short loc_18003D990
0x18003d97c  lea     rsi, aShouldskipsecu_0; "ShouldSkipSecureBootUpdatesOnOlderSyste"...
0x18003d983  mov     r13, [rbp+4Fh+var_78]
0x18003d987  mov     r9d, [rbp+4Fh+var_7C]
0x18003d98b  jmp     loc_18003DC10
0x18003d990  lea     rsi, aPassed; "Passed"
0x18003d997  cmp     [rbp+4Fh+var_6C], r12d
0x18003d99b  jz      short loc_18003D9BB
0x18003d99d  or      dword ptr [rdi], 1946h
0x18003d9a3  lea     rcx, aSkippingUpdate_2; "Skipping update on older AMI devices"
0x18003d9aa  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18003d9af  lea     rax, aSkipupdateonin_0; "SkipUpdateOnIncompatibleUEFI_OlderSyste"...
0x18003d9b6  mov     [r14], rax
0x18003d9b9  jmp     short loc_18003D983
0x18003d9bb  lea     r8, [rbp+4Fh+psz1]; unsigned __int16 **
0x18003d9bf  lea     rdx, aSystemmanufact_0; "SystemManufacturer"
0x18003d9c6  lea     rcx, aHardwareDescri; "HARDWARE\\DESCRIPTION\\System\\BIOS"
0x18003d9cd  call    ?GetHWSystemInformationFromRegistry@@YAJPEBG0PEAPEAG@Z; GetHWSystemInformationFromRegistry(ushort const *,ushort const *,ushort * *)
0x18003d9d2  mov     r15, [rbp+4Fh+psz1]
0x18003d9d6  mov     ebx, eax
0x18003d9d8  test    eax, eax
0x18003d9da  jns     short loc_18003D9E5
0x18003d9dc  lea     rsi, aSystemmanufact_1; "SystemManufacturerRegistryFailed"
0x18003d9e3  jmp     short loc_18003D983
0x18003d9e5  lea     rdx, aAppleInc; "Apple Inc."
0x18003d9ec  mov     rcx, r15; psz1
0x18003d9ef  call    cs:__imp_StrCmpIW
0x18003d9f5  test    eax, eax
0x18003d9f7  jnz     short loc_18003DA14
0x18003d9f9  or      dword ptr [rdi], 1946h
0x18003d9ff  lea     rcx, aSkippingUpdate_0; "Skipping update on Apple Inc devices"
0x18003da06  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18003da0b  lea     rax, aApplebadbasebo; "AppleBadBaseBoardProduct"
0x18003da12  jmp     short loc_18003D9B6
0x18003da14  lea     r8, [rbp+4Fh+lpMem]; unsigned __int16 **
0x18003da18  lea     rdx, aBaseboardprodu_0; "BaseBoardProduct"
0x18003da1f  lea     rcx, aHardwareDescri; "HARDWARE\\DESCRIPTION\\System\\BIOS"
0x18003da26  call    ?GetHWSystemInformationFromRegistry@@YAJPEBG0PEAPEAG@Z; GetHWSystemInformationFromRegistry(ushort const *,ushort const *,ushort * *)
0x18003da2b  mov     r12, [rbp+4Fh+lpMem]
0x18003da2f  mov     ebx, eax
0x18003da31  test    eax, eax
0x18003da33  jns     short loc_18003DA41
0x18003da35  lea     rsi, aBaseboardprodu; "BaseBoardProductRegistryFailed"
0x18003da3c  jmp     loc_18003D983
0x18003da41  mov     rdx, r12; unsigned __int16 *
0x18003da44  mov     rcx, r15; unsigned __int16 *
0x18003da47  call    ?ShouldSkipUpdateOnFujitsu@@YAHPEBG0@Z; ShouldSkipUpdateOnFujitsu(ushort const *,ushort const *)
0x18003da4c  mov     rdx, r12; unsigned __int16 *
0x18003da4f  test    eax, eax
0x18003da51  jz      short loc_18003DA71
0x18003da53  or      dword ptr [rdi], 1946h
0x18003da59  lea     rcx, aSkippingUpdate_1; "Skipping update on FUJITSU %ls devices"
0x18003da60  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18003da65  lea     rax, aFujitsubadbase; "FujitsuBadBaseBoardProduct"
0x18003da6c  jmp     loc_18003D9B6
0x18003da71  mov     rcx, r15; unsigned __int16 *
0x18003da74  call    ?ShouldSkipUpdateOnInsydeFirmware@@YAHPEBG0@Z; ShouldSkipUpdateOnInsydeFirmware(ushort const *,ushort const *)
0x18003da79  test    eax, eax
0x18003da7b  jz      short loc_18003DAA1
0x18003da7d  or      dword ptr [rdi], 1946h
0x18003da83  lea     rcx, aSkippingUpdate_6; "Skipping update on %ls %ls devices"
0x18003da8a  mov     r8, r12
0x18003da8d  mov     rdx, r15
0x18003da90  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18003da95  lea     rax, aInsydebadbaseb; "InsydeBadBaseBoardProduct"
0x18003da9c  jmp     loc_18003D9B6
0x18003daa1  lea     r8, [rbp+4Fh+var_50]; unsigned __int16 **
0x18003daa5  lea     rdx, aSystemproductn; "SystemProductName"
0x18003daac  lea     rcx, aHardwareDescri; "HARDWARE\\DESCRIPTION\\System\\BIOS"
0x18003dab3  call    ?GetHWSystemInformationFromRegistry@@YAJPEBG0PEAPEAG@Z; GetHWSystemInformationFromRegistry(ushort const *,ushort const *,ushort * *)
0x18003dab8  mov     ebx, eax
0x18003daba  test    eax, eax
0x18003dabc  jns     short loc_18003DACA
0x18003dabe  lea     rsi, aSystemproductn_0; "SystemProductNameRegistryFailed"
0x18003dac5  jmp     loc_18003D983
0x18003daca  mov     rdx, [rbp+4Fh+var_50]; unsigned __int16 *
0x18003dace  mov     rcx, r15; unsigned __int16 *
0x18003dad1  call    ?ShouldSecureBootSkipUpdateOnToshiba@@YAHPEBG0@Z; ShouldSecureBootSkipUpdateOnToshiba(ushort const *,ushort const *)
0x18003dad6  test    eax, eax
0x18003dad8  jz      short loc_18003DAFF
0x18003dada  or      dword ptr [rdi], 1946h
0x18003dae0  lea     rcx, aSkippingUpdate_6; "Skipping update on %ls %ls devices"
0x18003dae7  mov     r8, [rbp+4Fh+var_50]
0x18003daeb  mov     rdx, r15
0x18003daee  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18003daf3  lea     rax, aToshibabadsyst; "ToshibaBadSystemProduct"
0x18003dafa  jmp     loc_18003D9B6
0x18003daff  mov     rdx, r12; unsigned __int16 *
0x18003db02  mov     rcx, r15; unsigned __int16 *
0x18003db05  call    ?ShouldSecureBootSkipUpdateOnAsus@@YAHPEBG0@Z; ShouldSecureBootSkipUpdateOnAsus(ushort const *,ushort const *)
0x18003db0a  test    eax, eax
0x18003db0c  jz      short loc_18003DB32
0x18003db0e  or      dword ptr [rdi], 1946h
0x18003db14  lea     rcx, aSkippingUpdate_6; "Skipping update on %ls %ls devices"
0x18003db1b  mov     r8, r12
0x18003db1e  mov     rdx, r15
0x18003db21  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18003db26  lea     rax, aAsusbadbaseboa; "AsusBadBaseBoardProduct"
0x18003db2d  jmp     loc_18003D9B6
0x18003db32  mov     r8, r13; unsigned __int16 **
0x18003db35  lea     rdx, [rbp+4Fh+var_78]; unsigned __int16 **
0x18003db39  lea     rcx, [rbp+4Fh+var_70]; int *
0x18003db3d  call    ?ShouldSecureBootSkipUpdateOnHP@@YAJPEAHPEAPEBGPEAPEAG@Z; ShouldSecureBootSkipUpdateOnHP(int *,ushort const * *,ushort * *)
0x18003db42  mov     ebx, eax
0x18003db44  test    eax, eax
0x18003db46  jns     short loc_18003DB54
0x18003db48  lea     rsi, aShouldsecurebo_17; "ShouldSecureBootSkipUpdateOnHPFailed"
0x18003db4f  jmp     loc_18003D983
0x18003db54  cmp     [rbp+4Fh+var_70], 0
0x18003db58  mov     r13, [rbp+4Fh+var_78]
0x18003db5c  jz      short loc_18003DB67
0x18003db5e  or      dword ptr [rdi], 1944h
0x18003db64  mov     [r14], r13
0x18003db67  lea     rdx, [rbp+4Fh+var_40]; unsigned __int16 **
0x18003db6b  lea     rcx, [rbp+4Fh+arg_8]; int *
0x18003db6f  call    ?ShouldSecurebootSkipDBXUpdateOnHP@@YAJPEAHPEAPEBG@Z; ShouldSecurebootSkipDBXUpdateOnHP(int *,ushort const * *)
0x18003db74  mov     edx, [rbp+4Fh+arg_8]
0x18003db77  mov     ebx, eax
0x18003db79  test    eax, eax
0x18003db7b  jns     short loc_18003DB8D
0x18003db7d  lea     rsi, aShouldsecurebo_6; "ShouldSecureBootSkipDBXUpdateOnHPFailed"
0x18003db84  mov     r9d, [rbp+4Fh+var_7C]
0x18003db88  jmp     loc_18003DC13
0x18003db8d  test    edx, edx
0x18003db8f  jz      short loc_18003DB9D
0x18003db91  mov     rax, [rbp+4Fh+var_40]
0x18003db95  or      dword ptr [rdi], 2
0x18003db98  mov     [r14], rax
0x18003db9b  jmp     short loc_18003DB84
0x18003db9d  lea     r8, [rbp+4Fh+var_68]; unsigned int *
0x18003dba1  lea     rdx, [rbp+4Fh+var_48]; unsigned __int16 **
0x18003dba5  lea     rcx, [rbp+4Fh+var_80]; int *
0x18003dba9  call    ?ShouldSecurebootSkipUpdateOnARM@@YAJPEAHPEAPEBGPEAK@Z; ShouldSecurebootSkipUpdateOnARM(int *,ushort const * *,ulong *)
0x18003dbae  mov     r8d, [rbp+4Fh+var_80]
0x18003dbb2  mov     ebx, eax
0x18003dbb4  test    eax, eax
0x18003dbb6  jns     short loc_18003DBC8
0x18003dbb8  lea     rsi, aShouldsecurebo_13; "ShouldSecurebootSkipUpdateOnARMFailed"
0x18003dbbf  mov     edx, [rbp+4Fh+arg_8]
0x18003dbc2  mov     r9d, [rbp+4Fh+var_7C]
0x18003dbc6  jmp     short loc_18003DC17
0x18003dbc8  test    r8d, r8d
0x18003dbcb  jz      short loc_18003DBDC
0x18003dbcd  mov     rax, [rbp+4Fh+var_48]
0x18003dbd1  or      dword ptr [rdi], 1940h
0x18003dbd7  mov     [r14], rax
0x18003dbda  jmp     short loc_18003DBBF
0x18003dbdc  lea     rdx, [rbp+4Fh+var_7C]; int *
0x18003dbe0  mov     rcx, r15; unsigned __int16 *
0x18003dbe3  call    ?ShouldSecurebootSkipUpdateOnSamsung@@YAJPEBGPEAH@Z; ShouldSecurebootSkipUpdateOnSamsung(ushort const *,int *)
0x18003dbe8  mov     r9d, [rbp+4Fh+var_7C]
0x18003dbec  mov     ebx, eax
0x18003dbee  test    eax, eax
0x18003dbf0  jns     short loc_18003DBFB
0x18003dbf2  lea     rsi, aShouldsecurebo_8; "ShouldSecurebootSkipUpdateOnSamsungFail"...
0x18003dbf9  jmp     short loc_18003DC10
0x18003dbfb  test    r9d, r9d
0x18003dbfe  jz      short loc_18003DC10
0x18003dc00  or      dword ptr [rdi], 1944h
0x18003dc06  lea     rax, aSamsungbadsku; "SamsungBadSKU"
0x18003dc0d  mov     [r14], rax
0x18003dc10  mov     edx, [rbp+4Fh+arg_8]
0x18003dc13  mov     r8d, [rbp+4Fh+var_80]
0x18003dc17  mov     eax, [rbp+4Fh+arg_0]
0x18003dc1a  test    [rdi], eax
0x18003dc1c  jnz     short loc_18003DC28
0x18003dc1e  lea     rax, sourceString
0x18003dc25  mov     [r14], rax
0x18003dc28  mov     ecx, [rbp+4Fh+var_68]
0x18003dc2b  mov     rax, [rbp+4Fh+arg_20]
0x18003dc2f  mov     [rsp+0F0h+var_88], ecx
0x18003dc33  mov     [rax], ecx
0x18003dc35  lea     rcx, aShouldsecurebo; "ShouldSecurebootSkipAnyUpdate returned:"...
0x18003dc3c  mov     rax, [rbp+4Fh+var_48]
0x18003dc40  mov     [rsp+0F0h+var_90], rax
0x18003dc45  mov     rax, [rbp+4Fh+var_40]
0x18003dc49  mov     [rsp+0F0h+var_98], r13
0x18003dc4e  mov     [rsp+0F0h+var_A0], rax
0x18003dc53  mov     eax, [rbp+4Fh+var_70]
0x18003dc56  mov     [rsp+0F0h+var_A8], edx
0x18003dc5a  mov     edx, ebx
0x18003dc5c  mov     [rsp+0F0h+var_B0], r9d
0x18003dc61  mov     r9, r15
0x18003dc64  mov     [rsp+0F0h+var_B8], r8d
0x18003dc69  mov     r8, rsi
0x18003dc6c  mov     [rsp+0F0h+var_C0], eax
0x18003dc70  mov     eax, [rdi]
0x18003dc72  mov     [rsp+0F0h+var_C8], eax
0x18003dc76  mov     [rsp+0F0h+var_D0], r12
0x18003dc7b  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18003dc80  test    r15, r15
0x18003dc83  jz      short loc_18003DC99
0x18003dc85  call    cs:__imp_GetProcessHeap
0x18003dc8b  mov     r8, r15; lpMem
0x18003dc8e  xor     edx, edx; dwFlags
0x18003dc90  mov     rcx, rax; hHeap
0x18003dc93  call    cs:__imp_HeapFree
0x18003dc99  test    r12, r12
0x18003dc9c  jz      short loc_18003DCB2
0x18003dc9e  call    cs:__imp_GetProcessHeap
0x18003dca4  mov     r8, r12; lpMem
0x18003dca7  xor     edx, edx; dwFlags
0x18003dca9  mov     rcx, rax; hHeap
0x18003dcac  call    cs:__imp_HeapFree
0x18003dcb2  test    ebx, ebx
0x18003dcb4  jns     short loc_18003DCC5
0x18003dcb6  mov     rdx, rsi; unsigned __int16 *
0x18003dcb9  lea     rcx, aShouldsecurebo_12; "ShouldSecurebootSkipAnyUpdate"
0x18003dcc0  call    ?SBServicingCoreFunctionFailed@SBServicingCoreTelemetryProvider@@SAXPEBG0@Z; SBServicingCoreTelemetryProvider::SBServicingCoreFunctionFailed(ushort const *,ushort const *)
0x18003dcc5  mov     eax, ebx
0x18003dcc7  mov     rbx, [rsp+0F0h+arg_10]
0x18003dccf  add     rsp, 0C0h
0x18003dcd6  pop     r15
0x18003dcd8  pop     r14
0x18003dcda  pop     r13
0x18003dcdc  pop     r12
0x18003dcde  pop     rdi
0x18003dcdf  pop     rsi
0x18003dce0  pop     rbp
0x18003dce1  retn
```
