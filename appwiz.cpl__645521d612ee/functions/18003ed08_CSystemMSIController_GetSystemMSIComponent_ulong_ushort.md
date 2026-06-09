# CSystemMSIController::_GetSystemMSIComponent(ulong,ushort * *)

- ea: `0x18003ed08`
- end: `0x18003ee41`
- name: `?_GetSystemMSIComponent@CSystemMSIController@@AEAAKKPEAPEAG@Z`
- size: `313`
- prototype: `unsigned int(CSystemMSIController *__hidden this, unsigned int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18003ea60`

## callees

- `0x18003ed08`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ed50`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ed50`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ee20`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ee20`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18003edb7`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18003edb7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ee0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ee0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003edd9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003edd9`
- `ADVAPI32!RegEnumKeyW` at `0x18003edf9`
- `ADVAPI32!RegEnumKeyW` at `0x18003edf9`

## string_xrefs

- `0x18003ed3f`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Setup\OC Setup\Components`

## pseudocode

```c
__int64 __fastcall CSystemMSIController::_GetSystemMSIComponent(CSystemMSIController *this, DWORD a2, LPVOID *a3)
{
  unsigned int v5; // ebx
  SIZE_T v6; // rcx
  unsigned __int16 *v7; // rax
  DWORD cbMaxSubKeyLen; // [rsp+70h] [rbp+8h] BYREF
  int v10; // [rsp+74h] [rbp+Ch]
  HKEY hKey; // [rsp+88h] [rbp+20h] BYREF

  v10 = HIDWORD(this);
  hKey = 0;
  cbMaxSubKeyLen = 0;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Setup\\OC Setup\\Components",
         0,
         0x20019u,
         &hKey) )
  {
    return 259;
  }
  else
  {
    v5 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
    if ( !v5 )
    {
      v5 = 8;
      ++cbMaxSubKeyLen;
      v6 = 2 * cbMaxSubKeyLen;
      if ( (unsigned int)v6 > cbMaxSubKeyLen )
      {
        v7 = (unsigned __int16 *)CoTaskMemAlloc(v6);
        *a3 = v7;
        if ( v7 )
        {
          v5 = RegEnumKeyW(hKey, a2, v7, cbMaxSubKeyLen);
          if ( v5 == 259 )
          {
            CoTaskMemFree(*a3);
            *a3 = 0;
          }
        }
      }
    }
    RegCloseKey(hKey);
  }
  return v5;
}

```

## disassembly

```asm
0x18003ed08  mov     rax, rsp
0x18003ed0b  mov     [rax+10h], rbx
0x18003ed0f  mov     [rax+18h], rsi
0x18003ed13  mov     [rax+8], rcx
0x18003ed17  push    rdi
0x18003ed18  sub     rsp, 60h
0x18003ed1c  mov     qword ptr [rax+20h], 0
0x18003ed24  mov     rdi, r8
0x18003ed27  mov     dword ptr [rax+8], 0
0x18003ed2e  lea     rax, [rax+20h]
0x18003ed32  mov     esi, edx
0x18003ed34  mov     [rsp+68h+phkResult], rax; phkResult
0x18003ed39  mov     r9d, 20019h; samDesired
0x18003ed3f  lea     rdx, aSoftwareMicros_0
0x18003ed46  xor     r8d, r8d; ulOptions
0x18003ed49  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003ed50  call    cs:__imp_RegOpenKeyExW
0x18003ed56  test    eax, eax
0x18003ed58  jnz     loc_18003EE28
0x18003ed5e  mov     rcx, [rsp+68h+hKey]; hKey
0x18003ed66  lea     rax, [rsp+68h+cbMaxSubKeyLen]
0x18003ed6b  mov     [rsp+68h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18003ed74  xor     r9d, r9d; lpReserved
0x18003ed77  mov     [rsp+68h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x18003ed80  xor     r8d, r8d; lpcchClass
0x18003ed83  mov     [rsp+68h+lpcbMaxValueLen], 0; lpcbMaxValueLen
0x18003ed8c  xor     edx, edx; lpClass
0x18003ed8e  mov     [rsp+68h+lpcbMaxValueNameLen], 0; lpcbMaxValueNameLen
0x18003ed97  mov     [rsp+68h+lpcValues], 0; lpcValues
0x18003eda0  mov     [rsp+68h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x18003eda9  mov     [rsp+68h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18003edae  mov     [rsp+68h+phkResult], 0; lpcSubKeys
0x18003edb7  call    cs:__imp_RegQueryInfoKeyW
0x18003edbd  mov     ebx, eax
0x18003edbf  test    eax, eax
0x18003edc1  jnz     short loc_18003EE18
0x18003edc3  mov     eax, [rsp+68h+cbMaxSubKeyLen]
0x18003edc7  mov     ebx, 8
0x18003edcc  inc     eax
0x18003edce  mov     [rsp+68h+cbMaxSubKeyLen], eax
0x18003edd2  lea     ecx, [rax+rax]; cb
0x18003edd5  cmp     ecx, eax
0x18003edd7  jbe     short loc_18003EE18
0x18003edd9  call    cs:__imp_CoTaskMemAlloc
0x18003eddf  mov     [rdi], rax
0x18003ede2  test    rax, rax
0x18003ede5  jz      short loc_18003EE18
0x18003ede7  mov     r9d, [rsp+68h+cbMaxSubKeyLen]; cchName
0x18003edec  mov     r8, rax; lpName
0x18003edef  mov     rcx, [rsp+68h+hKey]; hKey
0x18003edf7  mov     edx, esi; dwIndex
0x18003edf9  call    cs:__imp_RegEnumKeyW
0x18003edff  mov     ebx, eax
0x18003ee01  cmp     eax, 103h
0x18003ee06  jnz     short loc_18003EE18
0x18003ee08  mov     rcx, [rdi]; pv
0x18003ee0b  call    cs:__imp_CoTaskMemFree
0x18003ee11  mov     qword ptr [rdi], 0
0x18003ee18  mov     rcx, [rsp+68h+hKey]; hKey
0x18003ee20  call    cs:__imp_RegCloseKey
0x18003ee26  jmp     short loc_18003EE2D
0x18003ee28  mov     ebx, 103h
0x18003ee2d  lea     r11, [rsp+68h+var_8]
0x18003ee32  mov     eax, ebx
0x18003ee34  mov     rbx, [r11+18h]
0x18003ee38  mov     rsi, [r11+20h]
0x18003ee3c  mov     rsp, r11
0x18003ee3f  pop     rdi
0x18003ee40  retn
```
