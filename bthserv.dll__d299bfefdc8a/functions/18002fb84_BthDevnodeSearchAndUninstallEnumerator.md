# BthDevnodeSearchAndUninstallEnumerator

- ea: `0x18002fb84`
- end: `0x18002fde4`
- name: `BthDevnodeSearchAndUninstallEnumerator`
- size: `608`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180025bd0`

## callees

- `0x180001790`
- `0x1800024ac`
- `0x18002fb84`
- `0x18002fdec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fbd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fc29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fcab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fd7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fbd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fc29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fcab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fd7b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002fd5a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002fd5a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002fd10`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002fd10`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002fd28`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002fd28`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x18002fc9c`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x18002fc9c`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18002fbc6`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18002fbc6`
- `DEVOBJ!DevObjGetClassDevs` at `0x18002fc16`
- `DEVOBJ!DevObjGetClassDevs` at `0x18002fc16`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18002fdb4`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18002fdb4`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x18002fc6f`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x18002fc6f`

## pseudocode

```c
__int64 __fastcall BthDevnodeSearchAndUninstallEnumerator(__int64 a1, const WCHAR *a2)
{
  __int64 DeviceInfoList; // rsi
  signed int LastError; // eax
  int v5; // ebx
  signed int v6; // eax
  unsigned int v7; // r15d
  HKEY v8; // r14
  signed int v9; // eax
  LSTATUS v10; // eax
  unsigned int v11; // edi
  signed int v12; // eax
  DWORD Type; // [rsp+30h] [rbp-99h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-95h] BYREF
  _OWORD v16[3]; // [rsp+38h] [rbp-91h] BYREF
  WCHAR Data[64]; // [rsp+70h] [rbp-59h] BYREF

  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  if ( DeviceInfoList != -1 )
    goto LABEL_40;
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
  if ( v5 >= 0 )
  {
LABEL_40:
    if ( (unsigned int)DevObjGetClassDevs(DeviceInfoList, 0, L"bthenum", 4, 0, 0) )
    {
      v5 = 0;
    }
    else
    {
      v6 = GetLastError();
      v5 = v6;
      if ( v6 > 0 )
        v5 = (unsigned __int16)v6 | 0x80070000;
      if ( v5 >= 0 )
        v5 = -2147467259;
    }
    v7 = 0;
    while ( v5 >= 0 )
    {
      memset(v16, 0, sizeof(v16));
      LODWORD(v16[0]) = 48;
      if ( (unsigned int)DevObjEnumDeviceInfo(DeviceInfoList, v7, v16) )
      {
        v8 = (HKEY)DevObjOpenDevRegKey(DeviceInfoList, v16, 1);
        if ( v8 == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
        {
          v9 = GetLastError();
          v5 = v9;
          if ( v9 > 0 )
            v5 = (unsigned __int16)v9 | 0x80070000;
        }
        else
        {
          v5 = 0;
        }
        if ( v5 >= 0 )
        {
          Type = 0;
          memset_0(Data, 0, 0x7Cu);
          cbData = 124;
          v10 = RegQueryValueExW(v8, L"Bluetooth_UniqueID", 0, &Type, (LPBYTE)Data, &cbData);
          v11 = v10;
          if ( v10 > 0 )
            v11 = (unsigned __int16)v10 | 0x80070000;
          RegCloseKey(v8);
          v5 = 0;
          if ( v11 != -536870389 )
            v5 = v11;
          if ( v5 >= 0 && Type == 1 && CompareStringOrdinal(a2, -1, Data, -1, 1) == 2 )
            v5 = BthDevnodeUninstallDevice(DeviceInfoList, (__int64)v16);
        }
      }
      else
      {
        v12 = GetLastError();
        v5 = v12;
        if ( v12 > 0 )
          v5 = (unsigned __int16)v12 | 0x80070000;
        if ( v5 >= 0 )
          v5 = -2147467259;
      }
      ++v7;
    }
    if ( v5 == -2147024637 )
      v5 = 0;
    if ( DeviceInfoList != -1 )
      DevObjDestroyDeviceInfoList(DeviceInfoList);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18002fb84  mov     [rsp-8+arg_0], rbx
0x18002fb89  mov     [rsp-8+arg_10], rsi
0x18002fb8e  push    rbp
0x18002fb8f  push    rdi
0x18002fb90  push    r12
0x18002fb92  push    r14
0x18002fb94  push    r15
0x18002fb96  lea     rbp, [rsp-37h]
0x18002fb9b  sub     rsp, 100h
0x18002fba2  mov     rax, cs:__security_cookie
0x18002fba9  xor     rax, rsp
0x18002fbac  mov     [rbp+57h+var_30], rax
0x18002fbb0  mov     r12, rdx
0x18002fbb3  mov     [rsp+120h+lpData], 0
0x18002fbbc  xor     edx, edx
0x18002fbbe  xor     r9d, r9d
0x18002fbc1  xor     r8d, r8d
0x18002fbc4  xor     ecx, ecx
0x18002fbc6  call    cs:__imp_DevObjCreateDeviceInfoList
0x18002fbcc  mov     rsi, rax
0x18002fbcf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002fbd3  jnz     short loc_18002FBF2
0x18002fbd5  call    cs:__imp_GetLastError
0x18002fbdb  mov     ebx, eax
0x18002fbdd  test    eax, eax
0x18002fbdf  jle     short loc_18002FBEA
0x18002fbe1  movzx   ebx, ax
0x18002fbe4  or      ebx, 80070000h
0x18002fbea  test    ebx, ebx
0x18002fbec  js      loc_18002FDBA
0x18002fbf2  mov     [rsp+120h+lpcbData], 0
0x18002fbfb  lea     r8, aBthenum; "bthenum"
0x18002fc02  mov     r9d, 4
0x18002fc08  mov     [rsp+120h+lpData], 0
0x18002fc11  xor     edx, edx
0x18002fc13  mov     rcx, rsi
0x18002fc16  call    cs:__imp_DevObjGetClassDevs
0x18002fc1c  mov     edi, 80004005h
0x18002fc21  test    eax, eax
0x18002fc23  jz      short loc_18002FC29
0x18002fc25  xor     ebx, ebx
0x18002fc27  jmp     short loc_18002FC43
0x18002fc29  call    cs:__imp_GetLastError
0x18002fc2f  mov     ebx, eax
0x18002fc31  test    eax, eax
0x18002fc33  jle     short loc_18002FC3E
0x18002fc35  movzx   ebx, ax
0x18002fc38  or      ebx, 80070000h
0x18002fc3e  test    ebx, ebx
0x18002fc40  cmovns  ebx, edi
0x18002fc43  xor     r15d, r15d
0x18002fc46  jmp     loc_18002FD98
0x18002fc4b  xorps   xmm0, xmm0
0x18002fc4e  lea     r8, [rsp+120h+var_E8]
0x18002fc53  movups  [rsp+120h+var_E8], xmm0
0x18002fc58  mov     edx, r15d
0x18002fc5b  mov     dword ptr [rsp+120h+var_E8], 30h ; '0'
0x18002fc63  mov     rcx, rsi
0x18002fc66  movups  [rsp+120h+var_D8], xmm0
0x18002fc6b  movups  [rbp+57h+var_C8], xmm0
0x18002fc6f  call    cs:__imp_DevObjEnumDeviceInfo
0x18002fc75  test    eax, eax
0x18002fc77  jz      loc_18002FD7B
0x18002fc7d  xor     r9d, r9d
0x18002fc80  mov     dword ptr [rsp+120h+lpcbData], 20019h
0x18002fc88  lea     rdx, [rsp+120h+var_E8]
0x18002fc8d  mov     dword ptr [rsp+120h+lpData], 1
0x18002fc95  mov     rcx, rsi
0x18002fc98  lea     r8d, [r9+1]
0x18002fc9c  call    cs:__imp_DevObjOpenDevRegKey
0x18002fca2  mov     r14, rax
0x18002fca5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002fca9  jnz     short loc_18002FCC2
0x18002fcab  call    cs:__imp_GetLastError
0x18002fcb1  mov     ebx, eax
0x18002fcb3  test    eax, eax
0x18002fcb5  jle     short loc_18002FCC4
0x18002fcb7  movzx   ebx, ax
0x18002fcba  or      ebx, 80070000h
0x18002fcc0  jmp     short loc_18002FCC4
0x18002fcc2  xor     ebx, ebx
0x18002fcc4  test    ebx, ebx
0x18002fcc6  js      loc_18002FD95
0x18002fccc  mov     ebx, 7Ch ; '|'
0x18002fcd1  mov     [rsp+120h+Type], 0
0x18002fcd9  mov     r8d, ebx; Size
0x18002fcdc  lea     rcx, [rbp+57h+Data]; void *
0x18002fce0  xor     edx, edx; Val
0x18002fce2  call    memset_0
0x18002fce7  lea     rax, [rsp+120h+cbData]
0x18002fcec  mov     [rsp+120h+cbData], ebx
0x18002fcf0  mov     [rsp+120h+lpcbData], rax; lpcbData
0x18002fcf5  lea     r9, [rsp+120h+Type]; lpType
0x18002fcfa  lea     rax, [rbp+57h+Data]
0x18002fcfe  xor     r8d, r8d; lpReserved
0x18002fd01  lea     rdx, aBluetoothUniqu; "Bluetooth_UniqueID"
0x18002fd08  mov     [rsp+120h+lpData], rax; lpData
0x18002fd0d  mov     rcx, r14; hKey
0x18002fd10  call    cs:__imp_RegQueryValueExW
0x18002fd16  mov     edi, eax
0x18002fd18  test    eax, eax
0x18002fd1a  jle     short loc_18002FD25
0x18002fd1c  movzx   edi, ax
0x18002fd1f  or      edi, 80070000h
0x18002fd25  mov     rcx, r14; hKey
0x18002fd28  call    cs:__imp_RegCloseKey
0x18002fd2e  xor     ebx, ebx
0x18002fd30  cmp     edi, 0E000020Bh
0x18002fd36  cmovnz  ebx, edi
0x18002fd39  test    ebx, ebx
0x18002fd3b  js      short loc_18002FD74
0x18002fd3d  cmp     [rsp+120h+Type], 1
0x18002fd42  jnz     short loc_18002FD74
0x18002fd44  or      r9d, 0FFFFFFFFh; cchCount2
0x18002fd48  mov     dword ptr [rsp+120h+lpData], 1; bIgnoreCase
0x18002fd50  or      edx, r9d; cchCount1
0x18002fd53  lea     r8, [rbp+57h+Data]; lpString2
0x18002fd57  mov     rcx, r12; lpString1
0x18002fd5a  call    cs:__imp_CompareStringOrdinal
0x18002fd60  cmp     eax, 2
0x18002fd63  jnz     short loc_18002FD74
0x18002fd65  lea     rdx, [rsp+120h+var_E8]
0x18002fd6a  mov     rcx, rsi
0x18002fd6d  call    BthDevnodeUninstallDevice
0x18002fd72  mov     ebx, eax
0x18002fd74  mov     edi, 80004005h
0x18002fd79  jmp     short loc_18002FD95
0x18002fd7b  call    cs:__imp_GetLastError
0x18002fd81  mov     ebx, eax
0x18002fd83  test    eax, eax
0x18002fd85  jle     short loc_18002FD90
0x18002fd87  movzx   ebx, ax
0x18002fd8a  or      ebx, 80070000h
0x18002fd90  test    ebx, ebx
0x18002fd92  cmovns  ebx, edi
0x18002fd95  inc     r15d
0x18002fd98  test    ebx, ebx
0x18002fd9a  jns     loc_18002FC4B
0x18002fda0  xor     ecx, ecx
0x18002fda2  cmp     ebx, 80070103h
0x18002fda8  cmovz   ebx, ecx
0x18002fdab  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18002fdaf  jz      short loc_18002FDBA
0x18002fdb1  mov     rcx, rsi
0x18002fdb4  call    cs:__imp_DevObjDestroyDeviceInfoList
0x18002fdba  mov     eax, ebx
0x18002fdbc  mov     rcx, [rbp+57h+var_30]
0x18002fdc0  xor     rcx, rsp; StackCookie
0x18002fdc3  call    __security_check_cookie
0x18002fdc8  lea     r11, [rsp+120h+var_20]
0x18002fdd0  mov     rbx, [r11+30h]
0x18002fdd4  mov     rsi, [r11+40h]
0x18002fdd8  mov     rsp, r11
0x18002fddb  pop     r15
0x18002fddd  pop     r14
0x18002fddf  pop     r12
0x18002fde1  pop     rdi
0x18002fde2  pop     rbp
0x18002fde3  retn
```
