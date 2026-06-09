# FSIsOEMOptInForWindowsEffects(ushort const *)

- ea: `0x1800035f0`
- end: `0x18000373a`
- name: `?FSIsOEMOptInForWindowsEffects@@YA_NPEBG@Z`
- size: `330`
- prototype: `bool __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180002474`
- `0x18002eb64`

## callees

- `0x1800035f0`

## import_xrefs

- `api-ms-win-devices-config-l1-1-1!CM_Open_Device_Interface_KeyW` at `0x180003637`
- `api-ms-win-devices-config-l1-1-1!CM_Open_Device_Interface_KeyW` at `0x180003637`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1800036b0`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1800036b0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000366c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003700`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000366c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003700`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800036a1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800036a1`

## pseudocode

```c
bool __fastcall FSIsOEMOptInForWindowsEffects(const unsigned __int16 *a1)
{
  CONFIGRET v1; // eax
  LSTATUS v2; // eax
  signed int v3; // ebx
  signed int v5; // eax
  LSTATUS v6; // eax
  DWORD cbData; // [rsp+50h] [rbp+18h] BYREF
  DWORD Type; // [rsp+58h] [rbp+20h] BYREF
  int Data; // [rsp+60h] [rbp+28h] BYREF
  HKEY phkDeviceInterface; // [rsp+68h] [rbp+30h] BYREF

  Data = 0;
  if ( !a1 )
    return 0;
  cbData = 0;
  Type = 0;
  phkDeviceInterface = 0;
  v1 = CM_Open_Device_Interface_KeyW(a1, 0x20019u, 1u, &phkDeviceInterface, 0);
  if ( !v1 )
    goto LABEL_3;
  v5 = CM_MapCrToWin32Err(v1, 0xDu);
  v3 = v5;
  if ( v5 > 0 )
    v3 = (unsigned __int16)v5 | 0x80070000;
  if ( v3 >= 0 )
  {
LABEL_3:
    cbData = 0;
    v2 = RegQueryValueExW(phkDeviceInterface, L"FSMEnableMsEffects", 0, &Type, 0, &cbData);
    v3 = v2;
    if ( !v2 )
      goto LABEL_15;
    if ( v2 > 0 )
      v3 = (unsigned __int16)v2 | 0x80070000;
    if ( v3 >= 0 )
    {
LABEL_15:
      if ( cbData > 4 )
      {
        v3 = -1072860816;
      }
      else
      {
        cbData = 4;
        v6 = RegQueryValueExW(phkDeviceInterface, L"FSMEnableMsEffects", 0, &Type, (LPBYTE)&Data, &cbData);
        v3 = v6;
        if ( v6 > 0 )
          v3 = (unsigned __int16)v6 | 0x80070000;
      }
    }
  }
  if ( phkDeviceInterface )
    RegCloseKey(phkDeviceInterface);
  return v3 >= 0 && Data != 0;
}

```

## disassembly

```asm
0x1800035f0  push    rbp
0x1800035f2  push    rbx
0x1800035f3  mov     rbp, rsp
0x1800035f6  sub     rsp, 38h
0x1800035fa  mov     [rbp+Data], 0
0x180003601  test    rcx, rcx
0x180003604  jz      loc_180003698
0x18000360a  lea     r9, [rbp+phkDeviceInterface]; phkDeviceInterface
0x18000360e  mov     [rbp+cbData], 0
0x180003615  mov     edx, 20019h; samDesired
0x18000361a  mov     [rbp+Type], 0
0x180003621  mov     r8d, 1; Disposition
0x180003627  mov     [rbp+phkDeviceInterface], 0
0x18000362f  mov     [rsp+38h+ulFlags], 0; ulFlags
0x180003637  call    cs:__imp_CM_Open_Device_Interface_KeyW
0x18000363d  test    eax, eax
0x18000363f  jnz     short loc_1800036A9
0x180003641  mov     rcx, [rbp+phkDeviceInterface]; hKey
0x180003645  lea     rax, [rbp+cbData]
0x180003649  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18000364e  lea     r9, [rbp+Type]; lpType
0x180003652  xor     r8d, r8d; lpReserved
0x180003655  mov     qword ptr [rsp+38h+ulFlags], 0; lpData
0x18000365e  lea     rdx, aFsmenablemseff; "FSMEnableMsEffects"
0x180003665  mov     [rbp+cbData], 0
0x18000366c  call    cs:__imp_RegQueryValueExW
0x180003672  mov     ebx, eax
0x180003674  test    eax, eax
0x180003676  jz      short loc_1800036CF
0x180003678  jle     short loc_180003683
0x18000367a  movzx   ebx, ax
0x18000367d  or      ebx, 80070000h
0x180003683  test    ebx, ebx
0x180003685  jns     short loc_1800036CF
0x180003687  mov     rcx, [rbp+phkDeviceInterface]; hKey
0x18000368b  test    rcx, rcx
0x18000368e  jnz     short loc_1800036A1
0x180003690  test    ebx, ebx
0x180003692  jns     loc_18000372E
0x180003698  xor     al, al
0x18000369a  add     rsp, 38h
0x18000369e  pop     rbx
0x18000369f  pop     rbp
0x1800036a0  retn
0x1800036a1  call    cs:__imp_RegCloseKey
0x1800036a7  jmp     short loc_180003690
0x1800036a9  mov     edx, 0Dh; DefaultErr
0x1800036ae  mov     ecx, eax; CmReturnCode
0x1800036b0  call    cs:__imp_CM_MapCrToWin32Err
0x1800036b6  mov     ebx, eax
0x1800036b8  test    eax, eax
0x1800036ba  jle     short loc_1800036C5
0x1800036bc  movzx   ebx, ax
0x1800036bf  or      ebx, 80070000h
0x1800036c5  test    ebx, ebx
0x1800036c7  jns     loc_180003641
0x1800036cd  jmp     short loc_180003687
0x1800036cf  cmp     [rbp+cbData], 4
0x1800036d3  ja      short loc_180003724
0x1800036d5  mov     rcx, [rbp+phkDeviceInterface]; hKey
0x1800036d9  lea     rax, [rbp+cbData]
0x1800036dd  mov     [rsp+38h+lpcbData], rax; lpcbData
0x1800036e2  lea     r9, [rbp+Type]; lpType
0x1800036e6  lea     rax, [rbp+Data]
0x1800036ea  mov     [rbp+cbData], 4
0x1800036f1  xor     r8d, r8d; lpReserved
0x1800036f4  mov     qword ptr [rsp+38h+ulFlags], rax; lpData
0x1800036f9  lea     rdx, aFsmenablemseff; "FSMEnableMsEffects"
0x180003700  call    cs:__imp_RegQueryValueExW
0x180003706  mov     ebx, eax
0x180003708  test    eax, eax
0x18000370a  jz      loc_180003687
0x180003710  jle     loc_180003687
0x180003716  movzx   ebx, ax
0x180003719  or      ebx, 80070000h
0x18000371f  jmp     loc_180003687
0x180003724  mov     ebx, 0C00D7170h
0x180003729  jmp     loc_180003687
0x18000372e  cmp     [rbp+Data], 0
0x180003732  setnz   al
0x180003735  jmp     loc_18000369A
```
