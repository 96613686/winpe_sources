# BthDevnodeSearchAndUninstallEnumerator

- ea: `0x140001950`
- end: `0x140001baf`
- name: `BthDevnodeSearchAndUninstallEnumerator`
- size: `607`
- prototype: `__int64 __fastcall(__int64, const WCHAR *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140001da0`

## callees

- `0x140001950`
- `0x140001bb8`
- `0x140001fea`
- `0x140002010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140001af3`
- `ADVAPI32!RegCloseKey` at `0x140001af3`
- `ADVAPI32!RegQueryValueExW` at `0x140001adb`
- `ADVAPI32!RegQueryValueExW` at `0x140001adb`
- `KERNEL32!GetLastError` at `0x1400019a4`
- `KERNEL32!GetLastError` at `0x1400019f4`
- `KERNEL32!GetLastError` at `0x140001a76`
- `KERNEL32!GetLastError` at `0x140001b46`
- `KERNEL32!GetLastError` at `0x1400019a4`
- `KERNEL32!GetLastError` at `0x1400019f4`
- `KERNEL32!GetLastError` at `0x140001a76`
- `KERNEL32!GetLastError` at `0x140001b46`
- `KERNEL32!CompareStringOrdinal` at `0x140001b25`
- `KERNEL32!CompareStringOrdinal` at `0x140001b25`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x140001a3a`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x140001a3a`
- `DEVOBJ!DevObjGetClassDevs` at `0x1400019e1`
- `DEVOBJ!DevObjGetClassDevs` at `0x1400019e1`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x140001995`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x140001995`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x140001a67`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x140001a67`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x140001b7f`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x140001b7f`

## pseudocode

```c
__int64 __fastcall BthDevnodeSearchAndUninstallEnumerator(__int64 a1, const WCHAR *a2)
{
  __int64 DeviceInfoList; // rsi
  signed int LastError; // eax
  signed int v6; // ebx
  signed int v7; // eax
  unsigned int v8; // r15d
  HKEY v9; // r14
  signed int v10; // eax
  LSTATUS v11; // eax
  unsigned int v12; // edi
  signed int v13; // eax
  DWORD Type; // [rsp+30h] [rbp-99h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-95h] BYREF
  _OWORD v17[3]; // [rsp+38h] [rbp-91h] BYREF
  WCHAR Data[64]; // [rsp+70h] [rbp-59h] BYREF

  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  if ( DeviceInfoList != -1 )
    goto LABEL_40;
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
  if ( v6 >= 0 )
  {
LABEL_40:
    if ( (unsigned int)DevObjGetClassDevs(DeviceInfoList, 0, a1, 4, 0, 0) )
    {
      v6 = 0;
    }
    else
    {
      v7 = GetLastError();
      v6 = v7;
      if ( v7 > 0 )
        v6 = (unsigned __int16)v7 | 0x80070000;
      if ( v6 >= 0 )
        v6 = -2147467259;
    }
    v8 = 0;
    while ( v6 >= 0 )
    {
      memset(v17, 0, sizeof(v17));
      LODWORD(v17[0]) = 48;
      if ( (unsigned int)DevObjEnumDeviceInfo(DeviceInfoList, v8, v17) )
      {
        v9 = (HKEY)DevObjOpenDevRegKey(DeviceInfoList, v17, 1);
        if ( v9 == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
        {
          v10 = GetLastError();
          v6 = v10;
          if ( v10 > 0 )
            v6 = (unsigned __int16)v10 | 0x80070000;
        }
        else
        {
          v6 = 0;
        }
        if ( v6 >= 0 )
        {
          Type = 0;
          memset_0(Data, 0, 0x7Cu);
          cbData = 124;
          v11 = RegQueryValueExW(v9, L"Bluetooth_UniqueID", 0, &Type, (LPBYTE)Data, &cbData);
          v12 = v11;
          if ( v11 > 0 )
            v12 = (unsigned __int16)v11 | 0x80070000;
          RegCloseKey(v9);
          v6 = 0;
          if ( v12 != -536870389 )
            v6 = v12;
          if ( v6 >= 0 && Type == 1 && CompareStringOrdinal(a2, -1, Data, -1, 1) == 2 )
            v6 = BthDevnodeUninstallDevice(DeviceInfoList, v17);
        }
      }
      else
      {
        v13 = GetLastError();
        v6 = v13;
        if ( v13 > 0 )
          v6 = (unsigned __int16)v13 | 0x80070000;
        if ( v6 >= 0 )
          v6 = -2147467259;
      }
      ++v8;
    }
    if ( v6 == -2147024637 )
      v6 = 0;
    if ( DeviceInfoList != -1 )
      DevObjDestroyDeviceInfoList(DeviceInfoList);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140001950  mov     [rsp-8+arg_10], rbx
0x140001955  mov     [rsp-8+arg_18], rsi
0x14000195a  push    rbp
0x14000195b  push    rdi
0x14000195c  push    r12
0x14000195e  push    r14
0x140001960  push    r15
0x140001962  lea     rbp, [rsp-37h]
0x140001967  sub     rsp, 100h
0x14000196e  mov     rax, cs:__security_cookie
0x140001975  xor     rax, rsp
0x140001978  mov     [rbp+57h+var_30], rax
0x14000197c  mov     r12, rdx
0x14000197f  mov     [rsp+120h+lpData], 0
0x140001988  mov     rdi, rcx
0x14000198b  xor     edx, edx
0x14000198d  xor     ecx, ecx
0x14000198f  xor     r9d, r9d
0x140001992  xor     r8d, r8d
0x140001995  call    cs:__imp_DevObjCreateDeviceInfoList
0x14000199b  mov     rsi, rax
0x14000199e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400019a2  jnz     short loc_1400019C1
0x1400019a4  call    cs:__imp_GetLastError
0x1400019aa  mov     ebx, eax
0x1400019ac  test    eax, eax
0x1400019ae  jle     short loc_1400019B9
0x1400019b0  movzx   ebx, ax
0x1400019b3  or      ebx, 80070000h
0x1400019b9  test    ebx, ebx
0x1400019bb  js      loc_140001B85
0x1400019c1  mov     [rsp+120h+lpcbData], 0
0x1400019ca  mov     r9d, 4
0x1400019d0  mov     r8, rdi
0x1400019d3  mov     [rsp+120h+lpData], 0
0x1400019dc  xor     edx, edx
0x1400019de  mov     rcx, rsi
0x1400019e1  call    cs:__imp_DevObjGetClassDevs
0x1400019e7  mov     edi, 80004005h
0x1400019ec  test    eax, eax
0x1400019ee  jz      short loc_1400019F4
0x1400019f0  xor     ebx, ebx
0x1400019f2  jmp     short loc_140001A0E
0x1400019f4  call    cs:__imp_GetLastError
0x1400019fa  mov     ebx, eax
0x1400019fc  test    eax, eax
0x1400019fe  jle     short loc_140001A09
0x140001a00  movzx   ebx, ax
0x140001a03  or      ebx, 80070000h
0x140001a09  test    ebx, ebx
0x140001a0b  cmovns  ebx, edi
0x140001a0e  xor     r15d, r15d
0x140001a11  jmp     loc_140001B63
0x140001a16  xorps   xmm0, xmm0
0x140001a19  lea     r8, [rsp+120h+var_E8]
0x140001a1e  movups  [rsp+120h+var_E8], xmm0
0x140001a23  mov     edx, r15d
0x140001a26  mov     dword ptr [rsp+120h+var_E8], 30h ; '0'
0x140001a2e  mov     rcx, rsi
0x140001a31  movups  [rsp+120h+var_D8], xmm0
0x140001a36  movups  [rbp+57h+var_C8], xmm0
0x140001a3a  call    cs:__imp_DevObjEnumDeviceInfo
0x140001a40  test    eax, eax
0x140001a42  jz      loc_140001B46
0x140001a48  xor     r9d, r9d
0x140001a4b  mov     dword ptr [rsp+120h+lpcbData], 20019h
0x140001a53  lea     rdx, [rsp+120h+var_E8]
0x140001a58  mov     dword ptr [rsp+120h+lpData], 1
0x140001a60  mov     rcx, rsi
0x140001a63  lea     r8d, [r9+1]
0x140001a67  call    cs:__imp_DevObjOpenDevRegKey
0x140001a6d  mov     r14, rax
0x140001a70  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140001a74  jnz     short loc_140001A8D
0x140001a76  call    cs:__imp_GetLastError
0x140001a7c  mov     ebx, eax
0x140001a7e  test    eax, eax
0x140001a80  jle     short loc_140001A8F
0x140001a82  movzx   ebx, ax
0x140001a85  or      ebx, 80070000h
0x140001a8b  jmp     short loc_140001A8F
0x140001a8d  xor     ebx, ebx
0x140001a8f  test    ebx, ebx
0x140001a91  js      loc_140001B60
0x140001a97  mov     ebx, 7Ch ; '|'
0x140001a9c  mov     [rsp+120h+Type], 0
0x140001aa4  mov     r8d, ebx; Size
0x140001aa7  lea     rcx, [rbp+57h+Data]; void *
0x140001aab  xor     edx, edx; Val
0x140001aad  call    memset_0
0x140001ab2  lea     rax, [rsp+120h+cbData]
0x140001ab7  mov     [rsp+120h+cbData], ebx
0x140001abb  mov     [rsp+120h+lpcbData], rax; lpcbData
0x140001ac0  lea     r9, [rsp+120h+Type]; lpType
0x140001ac5  lea     rax, [rbp+57h+Data]
0x140001ac9  xor     r8d, r8d; lpReserved
0x140001acc  lea     rdx, ValueName; "Bluetooth_UniqueID"
0x140001ad3  mov     [rsp+120h+lpData], rax; lpData
0x140001ad8  mov     rcx, r14; hKey
0x140001adb  call    cs:__imp_RegQueryValueExW
0x140001ae1  mov     edi, eax
0x140001ae3  test    eax, eax
0x140001ae5  jle     short loc_140001AF0
0x140001ae7  movzx   edi, ax
0x140001aea  or      edi, 80070000h
0x140001af0  mov     rcx, r14; hKey
0x140001af3  call    cs:__imp_RegCloseKey
0x140001af9  xor     ebx, ebx
0x140001afb  cmp     edi, 0E000020Bh
0x140001b01  cmovnz  ebx, edi
0x140001b04  test    ebx, ebx
0x140001b06  js      short loc_140001B3F
0x140001b08  cmp     [rsp+120h+Type], 1
0x140001b0d  jnz     short loc_140001B3F
0x140001b0f  or      r9d, 0FFFFFFFFh; cchCount2
0x140001b13  mov     dword ptr [rsp+120h+lpData], 1; bIgnoreCase
0x140001b1b  or      edx, r9d; cchCount1
0x140001b1e  lea     r8, [rbp+57h+Data]; lpString2
0x140001b22  mov     rcx, r12; lpString1
0x140001b25  call    cs:__imp_CompareStringOrdinal
0x140001b2b  cmp     eax, 2
0x140001b2e  jnz     short loc_140001B3F
0x140001b30  lea     rdx, [rsp+120h+var_E8]
0x140001b35  mov     rcx, rsi
0x140001b38  call    BthDevnodeUninstallDevice
0x140001b3d  mov     ebx, eax
0x140001b3f  mov     edi, 80004005h
0x140001b44  jmp     short loc_140001B60
0x140001b46  call    cs:__imp_GetLastError
0x140001b4c  mov     ebx, eax
0x140001b4e  test    eax, eax
0x140001b50  jle     short loc_140001B5B
0x140001b52  movzx   ebx, ax
0x140001b55  or      ebx, 80070000h
0x140001b5b  test    ebx, ebx
0x140001b5d  cmovns  ebx, edi
0x140001b60  inc     r15d
0x140001b63  test    ebx, ebx
0x140001b65  jns     loc_140001A16
0x140001b6b  xor     ecx, ecx
0x140001b6d  cmp     ebx, 80070103h
0x140001b73  cmovz   ebx, ecx
0x140001b76  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x140001b7a  jz      short loc_140001B85
0x140001b7c  mov     rcx, rsi
0x140001b7f  call    cs:__imp_DevObjDestroyDeviceInfoList
0x140001b85  mov     eax, ebx
0x140001b87  mov     rcx, [rbp+57h+var_30]
0x140001b8b  xor     rcx, rsp; StackCookie
0x140001b8e  call    __security_check_cookie
0x140001b93  lea     r11, [rsp+120h+var_20]
0x140001b9b  mov     rbx, [r11+40h]
0x140001b9f  mov     rsi, [r11+48h]
0x140001ba3  mov     rsp, r11
0x140001ba6  pop     r15
0x140001ba8  pop     r14
0x140001baa  pop     r12
0x140001bac  pop     rdi
0x140001bad  pop     rbp
0x140001bae  retn
```
