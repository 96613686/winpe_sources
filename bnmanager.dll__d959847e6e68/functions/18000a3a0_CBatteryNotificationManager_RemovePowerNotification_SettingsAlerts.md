# CBatteryNotificationManager::RemovePowerNotification(_SettingsAlerts)

- ea: `0x18000a3a0`
- end: `0x18000a4ef`
- name: `?RemovePowerNotification@CBatteryNotificationManager@@UEAAJW4_SettingsAlerts@@@Z`
- size: `335`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000a3a0`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000a452`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000a452`

## string_xrefs

- `0x18000a41b`: `EnergySaverHeuristic`
- `0x18000a48b`: `Windows.SystemToast.BackgroundAccess`

## pseudocode

```c
__int64 __fastcall CBatteryNotificationManager::RemovePowerNotification(__int64 a1, int a2)
{
  const wchar_t *v2; // rbx
  int v3; // edx
  int v4; // edx
  int v5; // edx
  int v6; // edx
  int v7; // edx
  int v8; // edx
  HRESULT v9; // edi
  __int64 v11; // [rsp+60h] [rbp+18h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp+20h] BYREF

  v2 = 0;
  v11 = 0;
  ppv = 0;
  if ( a2 <= 5 )
  {
    if ( a2 != 5 )
    {
      if ( a2 )
      {
        v3 = a2 - 1;
        if ( v3 )
        {
          v4 = v3 - 1;
          if ( v4 )
          {
            if ( (unsigned int)(v4 - 1) <= 1 )
              v2 = L"BatteryLevelLowCritical";
          }
          else
          {
            v2 = L"GenericToast";
          }
        }
        else
        {
          v2 = L"SleepTimeout";
        }
      }
      else
      {
        v2 = L"DisplayBrightness";
      }
      goto LABEL_20;
    }
LABEL_19:
    v2 = L"BatterySlowCharging";
    goto LABEL_20;
  }
  v5 = a2 - 6;
  if ( !v5 )
    goto LABEL_19;
  v6 = v5 - 1;
  if ( v6 && (v7 = v6 - 1) != 0 )
  {
    v8 = v7 - 1;
    if ( v8 )
    {
      if ( v8 == 11 )
        v2 = L"CleanEnergyCharging";
    }
    else
    {
      v2 = L"EnergySaverHeuristic";
    }
  }
  else
  {
    v2 = L"BatterySaver";
  }
LABEL_20:
  v9 = CoCreateInstance(
         &GUID_0c9281f9_6da1_4006_8729_de6e6b61581c,
         0,
         4u,
         &GUID_df8e9480_ca73_448e_b8f0_da000f581428,
         &ppv);
  if ( v9 >= 0 )
  {
    v9 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 24LL))(ppv, &v11);
    if ( v9 >= 0 )
      (*(void (__fastcall **)(__int64, const wchar_t *, const wchar_t *, _QWORD, const wchar_t *, const wchar_t *))(*(_QWORD *)v11 + 80LL))(
        v11,
        L"NonImmersivePackage",
        L"Windows.SystemToast.BackgroundAccess",
        0,
        v2,
        L"PowerToast");
  }
  if ( v11 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    v11 = 0;
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000a3a0  mov     [rsp+arg_0], rbx
0x18000a3a5  push    rdi
0x18000a3a6  sub     rsp, 40h
0x18000a3aa  xor     ebx, ebx
0x18000a3ac  mov     [rsp+48h+arg_10], rbx
0x18000a3b1  mov     [rsp+48h+arg_18], rbx
0x18000a3b6  cmp     edx, 5
0x18000a3b9  jg      short loc_18000A3F9
0x18000a3bb  jz      short loc_18000A42D
0x18000a3bd  test    edx, edx
0x18000a3bf  jz      short loc_18000A3F0
0x18000a3c1  sub     edx, 1
0x18000a3c4  jz      short loc_18000A3E7
0x18000a3c6  sub     edx, 1
0x18000a3c9  jz      short loc_18000A3DE
0x18000a3cb  sub     edx, 1
0x18000a3ce  jz      short loc_18000A3D5
0x18000a3d0  cmp     edx, 1
0x18000a3d3  jnz     short loc_18000A434
0x18000a3d5  lea     rbx, aBatterylevello; "BatteryLevelLowCritical"
0x18000a3dc  jmp     short loc_18000A434
0x18000a3de  lea     rbx, aGenerictoast; "GenericToast"
0x18000a3e5  jmp     short loc_18000A434
0x18000a3e7  lea     rbx, aSleeptimeout; "SleepTimeout"
0x18000a3ee  jmp     short loc_18000A434
0x18000a3f0  lea     rbx, aDisplaybrightn; "DisplayBrightness"
0x18000a3f7  jmp     short loc_18000A434
0x18000a3f9  sub     edx, 6
0x18000a3fc  jz      short loc_18000A42D
0x18000a3fe  sub     edx, 1
0x18000a401  jz      short loc_18000A424
0x18000a403  sub     edx, 1
0x18000a406  jz      short loc_18000A424
0x18000a408  sub     edx, 1
0x18000a40b  jz      short loc_18000A41B
0x18000a40d  cmp     edx, 0Bh
0x18000a410  jnz     short loc_18000A434
0x18000a412  lea     rbx, aCleanenergycha; "CleanEnergyCharging"
0x18000a419  jmp     short loc_18000A434
0x18000a41b  lea     rbx, aEnergysaverheu; "EnergySaverHeuristic"
0x18000a422  jmp     short loc_18000A434
0x18000a424  lea     rbx, aBatterysaver; "BatterySaver"
0x18000a42b  jmp     short loc_18000A434
0x18000a42d  lea     rbx, aBatteryslowcha; "BatterySlowCharging"
0x18000a434  xor     edx, edx; pUnkOuter
0x18000a436  lea     rax, [rsp+48h+arg_18]
0x18000a43b  lea     r9, _GUID_df8e9480_ca73_448e_b8f0_da000f581428; riid
0x18000a442  mov     [rsp+48h+ppv], rax; ppv
0x18000a447  lea     rcx, _GUID_0c9281f9_6da1_4006_8729_de6e6b61581c; rclsid
0x18000a44e  lea     r8d, [rdx+4]; dwClsContext
0x18000a452  call    cs:__imp_CoCreateInstance
0x18000a458  mov     edi, eax
0x18000a45a  test    eax, eax
0x18000a45c  js      short loc_18000A4AD
0x18000a45e  mov     rcx, [rsp+48h+arg_18]
0x18000a463  lea     rdx, [rsp+48h+arg_10]
0x18000a468  mov     rax, [rcx]
0x18000a46b  mov     rax, [rax+18h]
0x18000a46f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a474  mov     edi, eax
0x18000a476  test    eax, eax
0x18000a478  js      short loc_18000A4AD
0x18000a47a  mov     rcx, [rsp+48h+arg_10]
0x18000a47f  lea     rdx, aPowertoast; "PowerToast"
0x18000a486  mov     [rsp+48h+var_20], rdx
0x18000a48b  lea     r8, aWindowsSystemt; "Windows.SystemToast.BackgroundAccess"
0x18000a492  xor     r9d, r9d
0x18000a495  mov     [rsp+48h+ppv], rbx
0x18000a49a  lea     rdx, aNonimmersivepa; "NonImmersivePackage"
0x18000a4a1  mov     rax, [rcx]
0x18000a4a4  mov     rax, [rax+50h]
0x18000a4a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4ad  mov     rcx, [rsp+48h+arg_10]
0x18000a4b2  test    rcx, rcx
0x18000a4b5  jz      short loc_18000A4CC
0x18000a4b7  mov     rax, [rcx]
0x18000a4ba  mov     rax, [rax+10h]
0x18000a4be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4c3  mov     [rsp+48h+arg_10], 0
0x18000a4cc  mov     rcx, [rsp+48h+arg_18]
0x18000a4d1  test    rcx, rcx
0x18000a4d4  jz      short loc_18000A4E2
0x18000a4d6  mov     rax, [rcx]
0x18000a4d9  mov     rax, [rax+10h]
0x18000a4dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4e2  mov     rbx, [rsp+48h+arg_0]
0x18000a4e7  mov     eax, edi
0x18000a4e9  add     rsp, 40h
0x18000a4ed  pop     rdi
0x18000a4ee  retn
```
