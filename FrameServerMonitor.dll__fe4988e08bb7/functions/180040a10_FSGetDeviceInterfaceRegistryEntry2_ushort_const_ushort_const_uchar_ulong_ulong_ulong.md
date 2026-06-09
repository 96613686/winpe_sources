# FSGetDeviceInterfaceRegistryEntry2(ushort const *,ushort const *,uchar *,ulong,ulong *,ulong *)

- ea: `0x180040a10`
- end: `0x180040b6d`
- name: `?FSGetDeviceInterfaceRegistryEntry2@@YAJPEBG0PEAEKPEAK2@Z`
- size: `349`
- prototype: `__int64 __fastcall(LPCWSTR pszDeviceInterface, LPCWSTR lpValueName, LPBYTE lpData, DWORD, unsigned int *, unsigned int *Type)`
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180011860`
- `0x180012ec4`
- `0x180040ef8`
- `0x180041e90`
- `0x180042058`

## callees

- `0x18000e6bc`
- `0x180017b98`
- `0x180040a10`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180040ae9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180040b35`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180040ae9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180040b35`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180040aa5`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180040aa5`
- `api-ms-win-devices-config-l1-1-1!CM_Open_Device_Interface_KeyW` at `0x180040a94`
- `api-ms-win-devices-config-l1-1-1!CM_Open_Device_Interface_KeyW` at `0x180040a94`

## pseudocode

```c
__int64 __fastcall FSGetDeviceInterfaceRegistryEntry2(
        LPCWSTR pszDeviceInterface,
        LPCWSTR lpValueName,
        LPBYTE lpData,
        DWORD a4,
        unsigned int *a5,
        unsigned int *Type)
{
  signed int v10; // ebx
  unsigned int *v11; // rdi
  CONFIGRET v12; // eax
  signed int v13; // eax
  LSTATUS v14; // eax
  DWORD v15; // eax
  LSTATUS v16; // eax
  HKEY phkDeviceInterface[3]; // [rsp+30h] [rbp-18h] BYREF
  DWORD cbData; // [rsp+80h] [rbp+38h] BYREF

  cbData = 0;
  phkDeviceInterface[0] = 0;
  LODWORD(Type) = 0;
  if ( pszDeviceInterface && lpValueName )
  {
    v11 = a5;
    if ( a5 )
    {
      *a5 = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        phkDeviceInterface,
        0);
      v12 = CM_Open_Device_Interface_KeyW(pszDeviceInterface, 0x20019u, 1u, phkDeviceInterface, 0);
      if ( !v12 )
        goto LABEL_10;
      v13 = CM_MapCrToWin32Err(v12, 0xDu);
      v10 = v13;
      if ( v13 > 0 )
        v10 = (unsigned __int16)v13 | 0x80070000;
      if ( v10 >= 0 )
      {
LABEL_10:
        cbData = 0;
        v14 = RegQueryValueExW(phkDeviceInterface[0], lpValueName, 0, (LPDWORD)&Type, 0, &cbData);
        v10 = v14;
        if ( !v14 )
          goto LABEL_14;
        if ( v14 > 0 )
          v10 = (unsigned __int16)v14 | 0x80070000;
        if ( v10 >= 0 )
        {
LABEL_14:
          v15 = cbData;
          *v11 = cbData;
          if ( v15 <= a4 )
          {
            cbData = a4;
            v16 = RegQueryValueExW(phkDeviceInterface[0], lpValueName, 0, (LPDWORD)&Type, lpData, &cbData);
            v10 = v16;
            if ( !v16 )
              goto LABEL_20;
            if ( v16 > 0 )
              v10 = (unsigned __int16)v16 | 0x80070000;
            if ( v10 >= 0 )
LABEL_20:
              *v11 = cbData;
          }
          else
          {
            v10 = -1072860816;
          }
        }
      }
    }
    else
    {
      v10 = -2147467261;
    }
  }
  else
  {
    v10 = -2147024809;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(phkDeviceInterface);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180040a10  push    rbp
0x180040a12  push    rbx
0x180040a13  push    rsi
0x180040a14  push    rdi
0x180040a15  push    r14
0x180040a17  push    r15
0x180040a19  mov     rbp, rsp
0x180040a1c  sub     rsp, 48h
0x180040a20  mov     [rbp+cbData], 0
0x180040a27  mov     r14d, r9d
0x180040a2a  mov     [rbp+phkDeviceInterface], 0
0x180040a32  mov     r15, r8
0x180040a35  mov     [rbp+Type], 0
0x180040a3c  mov     rsi, rdx
0x180040a3f  mov     rbx, rcx
0x180040a42  test    rcx, rcx
0x180040a45  jnz     short loc_180040A51
0x180040a47  mov     ebx, 80070057h
0x180040a4c  jmp     loc_180040B55
0x180040a51  test    rsi, rsi
0x180040a54  jz      short loc_180040A47
0x180040a56  mov     rdi, [rbp+arg_20]
0x180040a5a  test    rdi, rdi
0x180040a5d  jnz     short loc_180040A69
0x180040a5f  mov     ebx, 80004003h
0x180040a64  jmp     loc_180040B55
0x180040a69  xor     edx, edx
0x180040a6b  mov     dword ptr [rdi], 0
0x180040a71  lea     rcx, [rbp+phkDeviceInterface]
0x180040a75  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180040a7a  lea     r9, [rbp+phkDeviceInterface]; phkDeviceInterface
0x180040a7e  mov     [rsp+48h+ulFlags], 0; ulFlags
0x180040a86  mov     edx, 20019h; samDesired
0x180040a8b  mov     r8d, 1; Disposition
0x180040a91  mov     rcx, rbx; pszDeviceInterface
0x180040a94  call    cs:__imp_CM_Open_Device_Interface_KeyW
0x180040a9a  test    eax, eax
0x180040a9c  jz      short loc_180040AC2
0x180040a9e  mov     edx, 0Dh; DefaultErr
0x180040aa3  mov     ecx, eax; CmReturnCode
0x180040aa5  call    cs:__imp_CM_MapCrToWin32Err
0x180040aab  mov     ebx, eax
0x180040aad  test    eax, eax
0x180040aaf  jle     short loc_180040ABA
0x180040ab1  movzx   ebx, ax
0x180040ab4  or      ebx, 80070000h
0x180040aba  test    ebx, ebx
0x180040abc  js      loc_180040B55
0x180040ac2  mov     rcx, [rbp+phkDeviceInterface]; hKey
0x180040ac6  lea     rax, [rbp+cbData]
0x180040aca  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180040acf  lea     r9, [rbp+Type]; lpType
0x180040ad3  xor     r8d, r8d; lpReserved
0x180040ad6  mov     qword ptr [rsp+48h+ulFlags], 0; lpData
0x180040adf  mov     rdx, rsi; lpValueName
0x180040ae2  mov     [rbp+cbData], 0
0x180040ae9  call    cs:__imp_RegQueryValueExW
0x180040aef  mov     ebx, eax
0x180040af1  test    eax, eax
0x180040af3  jz      short loc_180040B04
0x180040af5  jle     short loc_180040B00
0x180040af7  movzx   ebx, ax
0x180040afa  or      ebx, 80070000h
0x180040b00  test    ebx, ebx
0x180040b02  js      short loc_180040B55
0x180040b04  mov     eax, [rbp+cbData]
0x180040b07  mov     [rdi], eax
0x180040b09  cmp     eax, r14d
0x180040b0c  jbe     short loc_180040B15
0x180040b0e  mov     ebx, 0C00D7170h
0x180040b13  jmp     short loc_180040B55
0x180040b15  mov     rcx, [rbp+phkDeviceInterface]; hKey
0x180040b19  lea     rax, [rbp+cbData]
0x180040b1d  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180040b22  lea     r9, [rbp+Type]; lpType
0x180040b26  xor     r8d, r8d; lpReserved
0x180040b29  mov     qword ptr [rsp+48h+ulFlags], r15; lpData
0x180040b2e  mov     rdx, rsi; lpValueName
0x180040b31  mov     [rbp+cbData], r14d
0x180040b35  call    cs:__imp_RegQueryValueExW
0x180040b3b  mov     ebx, eax
0x180040b3d  test    eax, eax
0x180040b3f  jz      short loc_180040B50
0x180040b41  jle     short loc_180040B4C
0x180040b43  movzx   ebx, ax
0x180040b46  or      ebx, 80070000h
0x180040b4c  test    ebx, ebx
0x180040b4e  js      short loc_180040B55
0x180040b50  mov     ecx, [rbp+cbData]
0x180040b53  mov     [rdi], ecx
0x180040b55  lea     rcx, [rbp+phkDeviceInterface]
0x180040b59  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180040b5e  mov     eax, ebx
0x180040b60  add     rsp, 48h
0x180040b64  pop     r15
0x180040b66  pop     r14
0x180040b68  pop     rdi
0x180040b69  pop     rsi
0x180040b6a  pop     rbx
0x180040b6b  pop     rbp
0x180040b6c  retn
```
