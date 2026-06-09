# InternalCleanupVirtualCameraEntries_Registry(void)

- ea: `0x18000cb74`
- end: `0x18000cf39`
- name: `?InternalCleanupVirtualCameraEntries_Registry@@YAJXZ`
- size: `965`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180056590`

## callees

- `0x180005fa0`
- `0x18000ae14`
- `0x18000c348`
- `0x18000cb74`
- `0x18000ec30`
- `0x18002d02c`
- `0x180044f30`
- `0x180045900`
- `0x180051a1c`

## import_xrefs

- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x18000cd9b`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x18000cd9b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18000cf07`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18000cf07`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000ccd2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000cd49`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000ccd2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000cd49`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000cc2e`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000cc2e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cc5d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cc5d`

## pseudocode

```c
__int64 InternalCleanupVirtualCameraEntries_Registry(void)
{
  int v0; // eax
  unsigned int v1; // edi
  DWORD i; // r14d
  LSTATUS v3; // eax
  LSTATUS ValueW; // esi
  __int64 v6; // rdx
  BYTE PropertyBuffer[4]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  int pvData; // [rsp+50h] [rbp-B0h] BYREF
  DWORD pdwType; // [rsp+54h] [rbp-ACh] BYREF
  DWORD cchName; // [rsp+58h] [rbp-A8h] BYREF
  ULONG PropertyBufferSize; // [rsp+5Ch] [rbp-A4h] BYREF
  DEVPROPTYPE PropertyType[4]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR pszDeviceInterface[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Name[264]; // [rsp+280h] [rbp+180h] BYREF

  if ( (unsigned __int8)byte_18008D62D >= 8u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 231, &WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids);
  hKey = 0;
  v0 = OpenSensorGroupRegistryKey(0, 131353, 0, &hKey);
  v1 = v0;
  if ( v0 < 0 )
  {
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 232, &WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids, 0, v0);
LABEL_28:
    if ( byte_18008D62D )
    {
      v6 = 238;
LABEL_31:
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), v6, &WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids, v1);
    }
  }
  else
  {
    for ( i = 0; ; ++i )
    {
      memset_0(Name, 0, 0x208u);
      cchName = 260;
      v3 = RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0);
      if ( v3 == 259 )
        break;
      if ( v3 )
      {
        if ( v3 <= 0 )
          v1 = v3;
        else
          v1 = (unsigned __int16)v3 | 0x80070000;
        if ( g_wppLevels )
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 233, &WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids, 0, v1);
        goto LABEL_28;
      }
      pdwType = 0;
      pvData = 0;
      pcbData = 4;
      if ( RegGetValueW(hKey, Name, lpValue, 0x10018u, &pdwType, &pvData, &pcbData) || !pvData )
      {
        if ( (unsigned __int8)byte_18008D62D >= 8u )
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 27), 237, &WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids, Name);
      }
      else
      {
        memset_0(pszDeviceInterface, 0, 0x208u);
        pcbData = 520;
        ValueW = RegGetValueW(hKey, Name, off_18008B8E8, 0x10002u, &pdwType, pszDeviceInterface, &pcbData);
        if ( (unsigned __int8)byte_18008D62D >= 8u )
          WPP_SF_dS(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            234,
            (unsigned int)&WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids,
            ValueW,
            (__int64)pszDeviceInterface);
        if ( ValueW
          || (PropertyType[0] = 0,
              PropertyBuffer[0] = 0,
              PropertyBufferSize = 1,
              CM_Get_Device_Interface_PropertyW(
                pszDeviceInterface,
                &DEVPKEY_DeviceInterface_Enabled,
                PropertyType,
                PropertyBuffer,
                &PropertyBufferSize,
                0))
          || PropertyBuffer[0] != 0xFF )
        {
          if ( (unsigned __int8)byte_18008D62D >= 8u )
            WPP_SF_dS(
              *((_QWORD *)WPP_GLOBAL_Control + 27),
              235,
              (unsigned int)&WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids,
              ValueW,
              (__int64)pszDeviceInterface);
          RegDeleteTreeW(hKey, Name);
        }
        else if ( (unsigned __int8)byte_18008D62D >= 8u )
        {
          WPP_SF_dS(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            236,
            (unsigned int)&WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids,
            0,
            (__int64)pszDeviceInterface);
        }
      }
    }
    if ( (v1 & 0x80000000) != 0 )
      goto LABEL_28;
    if ( (unsigned __int8)byte_18008D62D >= 8u )
    {
      v6 = 239;
      goto LABEL_31;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v1;
}

```

## disassembly

```asm
0x18000cb74  push    rbp
0x18000cb76  push    rsi
0x18000cb77  push    rdi
0x18000cb78  push    r12
0x18000cb7a  push    r14
0x18000cb7c  lea     rbp, [rsp-3A0h]
0x18000cb84  sub     rsp, 4A0h
0x18000cb8b  mov     rax, cs:__security_cookie
0x18000cb92  xor     rax, rsp
0x18000cb95  mov     [rbp+3C0h+var_30], rax
0x18000cb9c  cmp     cs:byte_18008D62D, 8
0x18000cba3  lea     r12, WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids
0x18000cbaa  jnb     loc_18000CE45
0x18000cbb0  lea     r9, [rsp+4C0h+hKey]; HKEY *
0x18000cbb5  mov     [rsp+4C0h+hKey], 0
0x18000cbbe  xor     r8d, r8d; bool *
0x18000cbc1  mov     edx, 20119h; unsigned int
0x18000cbc6  xor     ecx, ecx; unsigned __int16 *
0x18000cbc8  call    ?OpenSensorGroupRegistryKey@@YAJPEBGKPEA_NPEAPEAUHKEY__@@@Z; OpenSensorGroupRegistryKey(ushort const *,ulong,bool *,HKEY__ * *)
0x18000cbcd  mov     edi, eax
0x18000cbcf  test    eax, eax
0x18000cbd1  js      loc_18000CE65
0x18000cbd7  xor     r14d, r14d
0x18000cbda  xor     edx, edx; Val
0x18000cbdc  lea     rcx, [rbp+3C0h+Name]; void *
0x18000cbe3  mov     r8d, 208h; Size
0x18000cbe9  call    memset_0
0x18000cbee  mov     rcx, [rsp+4C0h+hKey]; hKey
0x18000cbf3  lea     r9, [rsp+4C0h+cchName]; lpcchName
0x18000cbf8  mov     [rsp+4C0h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18000cc01  lea     r8, [rbp+3C0h+Name]; lpName
0x18000cc08  mov     [rsp+4C0h+lpcchClass], 0; lpcchClass
0x18000cc11  mov     edx, r14d; dwIndex
0x18000cc14  mov     [rsp+4C0h+lpClass], 0; lpClass
0x18000cc1d  mov     [rsp+4C0h+lpReserved], 0; lpReserved
0x18000cc26  mov     [rsp+4C0h+cchName], 104h
0x18000cc2e  call    cs:__imp_RegEnumKeyExW
0x18000cc34  cmp     eax, 103h
0x18000cc39  jnz     short loc_18000CC83
0x18000cc3b  test    edi, edi
0x18000cc3d  js      loc_18000CE0A
0x18000cc43  cmp     cs:byte_18008D62D, 8
0x18000cc4a  jnb     loc_18000CE1E
0x18000cc50  cmp     [rsp+4C0h+hKey], 0
0x18000cc56  jz      short loc_18000CC63
0x18000cc58  mov     rcx, [rsp+4C0h+hKey]; hKey
0x18000cc5d  call    cs:__imp_RegCloseKey
0x18000cc63  mov     eax, edi
0x18000cc65  mov     rcx, [rbp+3C0h+var_30]
0x18000cc6c  xor     rcx, rsp; StackCookie
0x18000cc6f  call    __security_check_cookie
0x18000cc74  add     rsp, 4A0h
0x18000cc7b  pop     r14
0x18000cc7d  pop     r12
0x18000cc7f  pop     rdi
0x18000cc80  pop     rsi
0x18000cc81  pop     rbp
0x18000cc82  retn
0x18000cc83  test    eax, eax
0x18000cc85  jnz     loc_18000CDEE
0x18000cc8b  mov     r8, cs:lpValue; lpValue
0x18000cc92  lea     rdx, [rbp+3C0h+Name]; lpSubKey
0x18000cc99  mov     rcx, [rsp+4C0h+hKey]; hkey
0x18000cc9e  mov     r9d, 10018h; dwFlags
0x18000cca4  mov     [rsp+4C0h+pdwType], eax
0x18000cca8  mov     [rsp+4C0h+pvData], eax
0x18000ccac  lea     rax, [rsp+4C0h+pcbData]
0x18000ccb1  mov     [rsp+4C0h+lpcchClass], rax; pcbData
0x18000ccb6  lea     rax, [rsp+4C0h+pvData]
0x18000ccbb  mov     [rsp+4C0h+lpClass], rax; pvData
0x18000ccc0  lea     rax, [rsp+4C0h+pdwType]
0x18000ccc5  mov     [rsp+4C0h+lpReserved], rax; pdwType
0x18000ccca  mov     [rsp+4C0h+pcbData], 4
0x18000ccd2  call    cs:__imp_RegGetValueW
0x18000ccd8  test    eax, eax
0x18000ccda  jz      short loc_18000CCF1
0x18000ccdc  cmp     cs:byte_18008D62D, 8
0x18000cce3  jnb     loc_18000CF12
0x18000cce9  inc     r14d
0x18000ccec  jmp     loc_18000CBDA
0x18000ccf1  cmp     [rsp+4C0h+pvData], 0
0x18000ccf6  jz      short loc_18000CCDC
0x18000ccf8  xor     edx, edx; Val
0x18000ccfa  lea     rcx, [rsp+4C0h+pszDeviceInterface]; void *
0x18000ccff  mov     r8d, 208h; Size
0x18000cd05  call    memset_0
0x18000cd0a  mov     r8, cs:off_18008B8E8; lpValue
0x18000cd11  lea     rax, [rsp+4C0h+pcbData]
0x18000cd16  mov     rcx, [rsp+4C0h+hKey]; hkey
0x18000cd1b  lea     rdx, [rbp+3C0h+Name]; lpSubKey
0x18000cd22  mov     [rsp+4C0h+lpcchClass], rax; pcbData
0x18000cd27  mov     r9d, 10002h; dwFlags
0x18000cd2d  lea     rax, [rsp+4C0h+pszDeviceInterface]
0x18000cd32  mov     [rsp+4C0h+pcbData], 208h
0x18000cd3a  mov     [rsp+4C0h+lpClass], rax; pvData
0x18000cd3f  lea     rax, [rsp+4C0h+pdwType]
0x18000cd44  mov     [rsp+4C0h+lpReserved], rax; pdwType
0x18000cd49  call    cs:__imp_RegGetValueW
0x18000cd4f  mov     esi, eax
0x18000cd51  cmp     cs:byte_18008D62D, 8
0x18000cd58  jnb     loc_18000CE9D
0x18000cd5e  test    esi, esi
0x18000cd60  jnz     loc_18000CECA
0x18000cd66  lea     rax, [rsp+4C0h+PropertyBufferSize]
0x18000cd6b  mov     dword ptr [rsp+4C0h+lpClass], esi; ulFlags
0x18000cd6f  lea     r9, [rsp+4C0h+PropertyBuffer]; PropertyBuffer
0x18000cd74  mov     [rsp+4C0h+lpReserved], rax; PropertyBufferSize
0x18000cd79  lea     r8, [rsp+4C0h+PropertyType]; PropertyType
0x18000cd7e  mov     [rsp+4C0h+PropertyType], esi
0x18000cd82  lea     rdx, DEVPKEY_DeviceInterface_Enabled; PropertyKey
0x18000cd89  mov     [rsp+4C0h+PropertyBuffer], sil
0x18000cd8e  lea     rcx, [rsp+4C0h+pszDeviceInterface]; pszDeviceInterface
0x18000cd93  mov     [rsp+4C0h+PropertyBufferSize], 1
0x18000cd9b  call    cs:__imp_CM_Get_Device_Interface_PropertyW
0x18000cda1  test    eax, eax
0x18000cda3  jnz     loc_18000CECA
0x18000cda9  cmp     [rsp+4C0h+PropertyBuffer], 0FFh
0x18000cdae  jnz     loc_18000CECA
0x18000cdb4  cmp     cs:byte_18008D62D, 8
0x18000cdbb  jb      loc_18000CCE9
0x18000cdc1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cdc8  lea     rax, [rsp+4C0h+pszDeviceInterface]
0x18000cdcd  mov     edx, 0ECh
0x18000cdd2  mov     [rsp+4C0h+lpReserved], rax
0x18000cdd7  xor     r9d, r9d
0x18000cdda  mov     r8, r12
0x18000cddd  mov     rcx, [rcx+0D8h]
0x18000cde4  call    WPP_SF_dS
0x18000cde9  jmp     loc_18000CCE9
0x18000cdee  jle     short loc_18000CE41
0x18000cdf0  movzx   edi, ax
0x18000cdf3  or      edi, 80070000h
0x18000cdf9  test    edi, edi
0x18000cdfb  jns     loc_18000CCE9
0x18000ce01  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000ce08  jnb     short loc_18000CE79
0x18000ce0a  cmp     cs:byte_18008D62D, 1
0x18000ce11  jb      loc_18000CC50
0x18000ce17  mov     edx, 0EEh
0x18000ce1c  jmp     short loc_18000CE23
0x18000ce1e  mov     edx, 0EFh
0x18000ce23  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ce2a  mov     r9d, edi
0x18000ce2d  mov     r8, r12
0x18000ce30  mov     rcx, [rcx+0D8h]
0x18000ce37  call    WPP_SF_d
0x18000ce3c  jmp     loc_18000CC50
0x18000ce41  mov     edi, eax
0x18000ce43  jmp     short loc_18000CDF9
0x18000ce45  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ce4c  mov     edx, 0E7h
0x18000ce51  mov     r8, r12
0x18000ce54  mov     rcx, [rcx+0D8h]
0x18000ce5b  call    WPP_SF_
0x18000ce60  jmp     loc_18000CBB0
0x18000ce65  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000ce6c  jb      short loc_18000CE0A
0x18000ce6e  mov     edx, 0E8h
0x18000ce73  mov     dword ptr [rsp+4C0h+lpReserved], eax
0x18000ce77  jmp     short loc_18000CE82
0x18000ce79  mov     edx, 0E9h
0x18000ce7e  mov     dword ptr [rsp+4C0h+lpReserved], edi
0x18000ce82  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ce89  xor     r9d, r9d
0x18000ce8c  mov     r8, r12
0x18000ce8f  mov     rcx, [rcx+10h]
0x18000ce93  call    WPP_SF_qD
0x18000ce98  jmp     loc_18000CE0A
0x18000ce9d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cea4  lea     rax, [rsp+4C0h+pszDeviceInterface]
0x18000cea9  mov     edx, 0EAh
0x18000ceae  mov     [rsp+4C0h+lpReserved], rax
0x18000ceb3  mov     r9d, esi
0x18000ceb6  mov     r8, r12
0x18000ceb9  mov     rcx, [rcx+0D8h]
0x18000cec0  call    WPP_SF_dS
0x18000cec5  jmp     loc_18000CD5E
0x18000ceca  cmp     cs:byte_18008D62D, 8
0x18000ced1  jb      short loc_18000CEFB
0x18000ced3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ceda  lea     rax, [rsp+4C0h+pszDeviceInterface]
0x18000cedf  mov     edx, 0EBh
0x18000cee4  mov     [rsp+4C0h+lpReserved], rax
0x18000cee9  mov     r9d, esi
0x18000ceec  mov     r8, r12
0x18000ceef  mov     rcx, [rcx+0D8h]
0x18000cef6  call    WPP_SF_dS
0x18000cefb  mov     rcx, [rsp+4C0h+hKey]; hKey
0x18000cf00  lea     rdx, [rbp+3C0h+Name]; lpSubKey
0x18000cf07  call    cs:__imp_RegDeleteTreeW
0x18000cf0d  jmp     loc_18000CCE9
0x18000cf12  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cf19  lea     r9, [rbp+3C0h+Name]
0x18000cf20  mov     edx, 0EDh
0x18000cf25  mov     r8, r12
0x18000cf28  mov     rcx, [rcx+0D8h]
0x18000cf2f  call    WPP_SF_S
0x18000cf34  jmp     loc_18000CCE9
```
