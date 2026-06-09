# FSGetDeviceInterfaceRegistryEntry2(ushort const *,ushort const *,uchar *,ulong,ulong *,ulong *)

- ea: `0x1800285cc`
- end: `0x180028739`
- name: `?FSGetDeviceInterfaceRegistryEntry2@@YAJPEBG0PEAEKPEAK2@Z`
- size: `365`
- prototype: `__int64 __usercall@<rax>(LPCWSTR pszDeviceInterface@<rcx>, LPCWSTR lpValueName@<rdx>, LPBYTE lpData@<r8>, unsigned int@<r9d>, unsigned int *, unsigned int *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180028b4c`
- `0x18002a0ec`
- `0x180077014`

## callees

- `0x180026ecc`
- `0x1800285cc`
- `0x18002b510`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800286ac`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800286fb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800286ac`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800286fb`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180028668`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180028668`
- `api-ms-win-devices-config-l1-1-1!CM_Open_Device_Interface_KeyW` at `0x180028657`
- `api-ms-win-devices-config-l1-1-1!CM_Open_Device_Interface_KeyW` at `0x180028657`

## pseudocode

```c
__int64 __fastcall FSGetDeviceInterfaceRegistryEntry2(
        LPCWSTR pszDeviceInterface,
        LPCWSTR lpValueName,
        LPBYTE lpData,
        __int64 a4,
        unsigned int *a5,
        unsigned int *phkDeviceInterface)
{
  signed int v9; // ebx
  unsigned int *v10; // rdi
  CONFIGRET v11; // eax
  signed int v12; // eax
  LSTATUS v13; // eax
  DWORD v14; // eax
  LSTATUS v15; // eax
  DWORD Type; // [rsp+50h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+38h] BYREF

  cbData = 0;
  phkDeviceInterface = 0;
  Type = 0;
  if ( pszDeviceInterface && lpValueName )
  {
    v10 = a5;
    if ( a5 )
    {
      *a5 = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &phkDeviceInterface,
        0);
      v11 = CM_Open_Device_Interface_KeyW(pszDeviceInterface, 0x20019u, 1u, (PHKEY)&phkDeviceInterface, 0);
      if ( !v11 )
        goto LABEL_10;
      v12 = CM_MapCrToWin32Err(v11, 0xDu);
      v9 = v12;
      if ( v12 > 0 )
        v9 = (unsigned __int16)v12 | 0x80070000;
      if ( v9 >= 0 )
      {
LABEL_10:
        cbData = 0;
        v13 = RegQueryValueExW((HKEY)phkDeviceInterface, lpValueName, 0, &Type, 0, &cbData);
        v9 = v13;
        if ( !v13 )
          goto LABEL_14;
        if ( v13 > 0 )
          v9 = (unsigned __int16)v13 | 0x80070000;
        if ( v9 >= 0 )
        {
LABEL_14:
          v14 = cbData;
          *v10 = cbData;
          if ( v14 <= 4 )
          {
            cbData = 4;
            v15 = RegQueryValueExW((HKEY)phkDeviceInterface, lpValueName, 0, &Type, lpData, &cbData);
            v9 = v15;
            if ( !v15 )
              goto LABEL_20;
            if ( v15 > 0 )
              v9 = (unsigned __int16)v15 | 0x80070000;
            if ( v9 >= 0 )
LABEL_20:
              *v10 = cbData;
          }
          else
          {
            v9 = -1072860816;
          }
        }
      }
    }
    else
    {
      v9 = -2147467261;
    }
  }
  else
  {
    v9 = -2147024809;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkDeviceInterface);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800285cc  mov     [rsp-18h+arg_8], rbx
0x1800285d1  mov     [rsp-18h+arg_10], rsi
0x1800285d6  mov     [rsp-18h+cbData], r9d
0x1800285db  push    rbp
0x1800285dc  push    rdi
0x1800285dd  push    r14
0x1800285df  mov     rbp, rsp
0x1800285e2  sub     rsp, 30h
0x1800285e6  mov     [rbp+cbData], 0
0x1800285ed  mov     r14, r8
0x1800285f0  mov     [rbp+phkDeviceInterface], 0
0x1800285f8  mov     rsi, rdx
0x1800285fb  mov     [rbp+Type], 0
0x180028602  mov     rbx, rcx
0x180028605  test    rcx, rcx
0x180028608  jnz     short loc_180028614
0x18002860a  mov     ebx, 80070057h
0x18002860f  jmp     loc_18002871B
0x180028614  test    rsi, rsi
0x180028617  jz      short loc_18002860A
0x180028619  mov     rdi, [rbp+arg_20]
0x18002861d  test    rdi, rdi
0x180028620  jnz     short loc_18002862C
0x180028622  mov     ebx, 80004003h
0x180028627  jmp     loc_18002871B
0x18002862c  xor     edx, edx
0x18002862e  mov     dword ptr [rdi], 0
0x180028634  lea     rcx, [rbp+phkDeviceInterface]
0x180028638  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002863d  lea     r9, [rbp+phkDeviceInterface]; phkDeviceInterface
0x180028641  mov     [rsp+30h+ulFlags], 0; ulFlags
0x180028649  mov     edx, 20019h; samDesired
0x18002864e  mov     r8d, 1; Disposition
0x180028654  mov     rcx, rbx; pszDeviceInterface
0x180028657  call    cs:__imp_CM_Open_Device_Interface_KeyW
0x18002865d  test    eax, eax
0x18002865f  jz      short loc_180028685
0x180028661  mov     edx, 0Dh; DefaultErr
0x180028666  mov     ecx, eax; CmReturnCode
0x180028668  call    cs:__imp_CM_MapCrToWin32Err
0x18002866e  mov     ebx, eax
0x180028670  test    eax, eax
0x180028672  jle     short loc_18002867D
0x180028674  movzx   ebx, ax
0x180028677  or      ebx, 80070000h
0x18002867d  test    ebx, ebx
0x18002867f  js      loc_18002871B
0x180028685  mov     rcx, [rbp+phkDeviceInterface]; hKey
0x180028689  lea     rax, [rbp+cbData]
0x18002868d  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180028692  lea     r9, [rbp+Type]; lpType
0x180028696  xor     r8d, r8d; lpReserved
0x180028699  mov     qword ptr [rsp+30h+ulFlags], 0; lpData
0x1800286a2  mov     rdx, rsi; lpValueName
0x1800286a5  mov     [rbp+cbData], 0
0x1800286ac  call    cs:__imp_RegQueryValueExW
0x1800286b2  mov     ebx, eax
0x1800286b4  test    eax, eax
0x1800286b6  jz      short loc_1800286C7
0x1800286b8  jle     short loc_1800286C3
0x1800286ba  movzx   ebx, ax
0x1800286bd  or      ebx, 80070000h
0x1800286c3  test    ebx, ebx
0x1800286c5  js      short loc_18002871B
0x1800286c7  mov     eax, [rbp+cbData]
0x1800286ca  mov     [rdi], eax
0x1800286cc  cmp     eax, 4
0x1800286cf  jbe     short loc_1800286D8
0x1800286d1  mov     ebx, 0C00D7170h
0x1800286d6  jmp     short loc_18002871B
0x1800286d8  mov     rcx, [rbp+phkDeviceInterface]; hKey
0x1800286dc  lea     rax, [rbp+cbData]
0x1800286e0  mov     [rsp+30h+lpcbData], rax; lpcbData
0x1800286e5  lea     r9, [rbp+Type]; lpType
0x1800286e9  xor     r8d, r8d; lpReserved
0x1800286ec  mov     qword ptr [rsp+30h+ulFlags], r14; lpData
0x1800286f1  mov     rdx, rsi; lpValueName
0x1800286f4  mov     [rbp+cbData], 4
0x1800286fb  call    cs:__imp_RegQueryValueExW
0x180028701  mov     ebx, eax
0x180028703  test    eax, eax
0x180028705  jz      short loc_180028716
0x180028707  jle     short loc_180028712
0x180028709  movzx   ebx, ax
0x18002870c  or      ebx, 80070000h
0x180028712  test    ebx, ebx
0x180028714  js      short loc_18002871B
0x180028716  mov     ecx, [rbp+cbData]
0x180028719  mov     [rdi], ecx
0x18002871b  lea     rcx, [rbp+phkDeviceInterface]
0x18002871f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180028724  mov     rsi, [rsp+30h+arg_10]
0x180028729  mov     eax, ebx
0x18002872b  mov     rbx, [rsp+30h+arg_8]
0x180028730  add     rsp, 30h
0x180028734  pop     r14
0x180028736  pop     rdi
0x180028737  pop     rbp
0x180028738  retn
```
