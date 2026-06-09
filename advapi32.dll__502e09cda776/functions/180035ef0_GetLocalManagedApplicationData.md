# GetLocalManagedApplicationData

- ea: `0x180035ef0`
- end: `0x180036170`
- name: `GetLocalManagedApplicationData`
- size: `640`
- prototype: `void __stdcall(LPWSTR ProductCode, LPWSTR *DisplayName, LPWSTR *SupportUrl)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180027f00`
- `0x180035ef0`
- `0x180048b00`
- `0x1800720b0`

## import_xrefs

- `KERNELBASE!lstrcmpiW` at `0x1800360bb`
- `KERNELBASE!lstrcmpiW` at `0x1800360bb`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180035f68`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180035f68`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180036010`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800360a7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180036010`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800360a7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180035fb7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180036060`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180035fb7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180036060`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035fce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800360d0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003610b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003611c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003615d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035fce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800360d0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003610b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003611c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003615d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __stdcall GetLocalManagedApplicationData(LPWSTR ProductCode, LPWSTR *DisplayName, LPWSTR *SupportUrl)
{
  int v6; // ebx
  int v7; // edi
  HKEY v8; // rcx
  LSTATUS v9; // esi
  DWORD i; // edi
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  HKEY v13; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  BYTE Data[16]; // [rsp+50h] [rbp-B0h] BYREF
  BYTE v16[2]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Name[48]; // [rsp+B0h] [rbp-50h] BYREF

  *DisplayName = 0;
  *SupportUrl = 0;
  phkResult = 0;
  hKey = 0;
  v6 = 0;
  v13 = 0;
  cbData = 0;
  while ( v6 < 2 )
  {
    if ( v6 )
    {
      v8 = HKEY_LOCAL_MACHINE;
      v7 = 0;
      phkResult = HKEY_LOCAL_MACHINE;
    }
    else
    {
      v7 = 1;
      if ( RegOpenCurrentUser(0x20019u, &phkResult) )
        return;
      v8 = phkResult;
    }
    hKey = 0;
    v9 = RegOpenKeyExW(v8, L"Software\\Microsoft\\Windows\\CurrentVersion\\Group Policy\\Appmgmt", 0, 0x20019u, &hKey);
    if ( v7 )
      RegCloseKey(phkResult);
    if ( v9 || (*(_DWORD *)Data = 0, cbData = 4, RegQueryValueExW(hKey, ProductCode, 0, 0, Data, &cbData)) )
    {
      if ( hKey )
        RegCloseKey(hKey);
    }
    else
    {
      for ( i = 0; !RegEnumKeyW(hKey, i, Name, 0x2Cu) && !RegOpenKeyExW(hKey, Name, 0, 0x20019u, &v13); ++i )
      {
        *(_WORD *)v16 = 0;
        cbData = 80;
        RegQueryValueExW(v13, L"Product ID", 0, 0, v16, &cbData);
        if ( !lstrcmpiW(ProductCode, (LPCWSTR)v16) )
        {
          ReadStringValue(v13, L"Deployment Name", DisplayName);
          ReadStringValue(v13, L"SupportUrl", SupportUrl);
          RegCloseKey(v13);
          break;
        }
        RegCloseKey(v13);
      }
      RegCloseKey(hKey);
      if ( *DisplayName || *SupportUrl )
        return;
    }
    ++v6;
  }
}

```

## disassembly

```asm
0x180035ef0  push    rbp
0x180035ef2  push    rbx
0x180035ef3  push    rsi
0x180035ef4  push    rdi
0x180035ef5  push    r12
0x180035ef7  push    r14
0x180035ef9  push    r15
0x180035efb  lea     rbp, [rsp-20h]
0x180035f00  sub     rsp, 120h
0x180035f07  mov     rax, cs:__security_cookie
0x180035f0e  xor     rax, rsp
0x180035f11  mov     [rbp+50h+var_40], rax
0x180035f15  mov     qword ptr [rdx], 0
0x180035f1c  mov     r14, r8
0x180035f1f  mov     qword ptr [r8], 0
0x180035f26  mov     r15, rdx
0x180035f29  mov     r12, rcx
0x180035f2c  mov     [rsp+150h+phkResult], 0
0x180035f35  mov     [rsp+150h+hKey], 0
0x180035f3e  xor     ebx, ebx
0x180035f40  mov     [rsp+150h+var_110], 0
0x180035f49  mov     [rsp+150h+cbData], 0
0x180035f51  cmp     ebx, 2
0x180035f54  jge     loc_180036134
0x180035f5a  test    ebx, ebx
0x180035f5c  jnz     short loc_180035F86
0x180035f5e  lea     rdx, [rsp+150h+phkResult]; phkResult
0x180035f63  mov     ecx, 20019h; samDesired
0x180035f68  call    cs:__imp_RegOpenCurrentUser
0x180035f6f  nop     dword ptr [rax+rax+00h]
0x180035f74  lea     edi, [rbx+1]
0x180035f77  test    eax, eax
0x180035f79  jnz     loc_180036134
0x180035f7f  mov     rcx, [rsp+150h+phkResult]
0x180035f84  jmp     short loc_180035F94
0x180035f86  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180035f8d  xor     edi, edi
0x180035f8f  mov     [rsp+150h+phkResult], rcx
0x180035f94  lea     rax, [rsp+150h+hKey]
0x180035f99  mov     [rsp+150h+hKey], 0
0x180035fa2  mov     r9d, 20019h; samDesired
0x180035fa8  mov     [rsp+150h+var_130], rax; phkResult
0x180035fad  xor     r8d, r8d; ulOptions
0x180035fb0  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180035fb7  call    cs:__imp_RegOpenKeyExW
0x180035fbe  nop     dword ptr [rax+rax+00h]
0x180035fc3  mov     esi, eax
0x180035fc5  test    edi, edi
0x180035fc7  jz      short loc_180035FDA
0x180035fc9  mov     rcx, [rsp+150h+phkResult]; hKey
0x180035fce  call    cs:__imp_RegCloseKey
0x180035fd5  nop     dword ptr [rax+rax+00h]
0x180035fda  test    esi, esi
0x180035fdc  jnz     loc_180036153
0x180035fe2  mov     rcx, [rsp+150h+hKey]; hKey
0x180035fe7  lea     rax, [rsp+150h+cbData]
0x180035fec  mov     [rsp+150h+lpcbData], rax; lpcbData
0x180035ff1  xor     r9d, r9d; lpType
0x180035ff4  lea     rax, [rsp+150h+Data]
0x180035ff9  mov     dword ptr [rsp+150h+Data], esi
0x180035ffd  xor     r8d, r8d; lpReserved
0x180036000  mov     [rsp+150h+var_130], rax; lpData
0x180036005  mov     rdx, r12; lpValueName
0x180036008  mov     [rsp+150h+cbData], 4
0x180036010  call    cs:__imp_RegQueryValueExW
0x180036017  nop     dword ptr [rax+rax+00h]
0x18003601c  test    eax, eax
0x18003601e  jnz     loc_180036153
0x180036024  xor     edi, edi
0x180036026  mov     rcx, [rsp+150h+hKey]; hKey
0x18003602b  lea     r8, [rbp+50h+Name]; lpName
0x18003602f  mov     r9d, 2Ch ; ','; cchName
0x180036035  mov     edx, edi; dwIndex
0x180036037  call    RegEnumKeyW
0x18003603c  test    eax, eax
0x18003603e  jnz     loc_180036117
0x180036044  mov     rcx, [rsp+150h+hKey]; hKey
0x180036049  lea     rax, [rsp+150h+var_110]
0x18003604e  mov     r9d, 20019h; samDesired
0x180036054  mov     [rsp+150h+var_130], rax; phkResult
0x180036059  xor     r8d, r8d; ulOptions
0x18003605c  lea     rdx, [rbp+50h+Name]; lpSubKey
0x180036060  call    cs:__imp_RegOpenKeyExW
0x180036067  nop     dword ptr [rax+rax+00h]
0x18003606c  test    eax, eax
0x18003606e  jnz     loc_180036117
0x180036074  mov     rcx, [rsp+150h+var_110]; hKey
0x180036079  lea     rdx, aProductId; "Product ID"
0x180036080  mov     word ptr [rsp+150h+var_F0], ax
0x180036085  xor     r9d, r9d; lpType
0x180036088  lea     rax, [rsp+150h+cbData]
0x18003608d  mov     [rsp+150h+cbData], 50h ; 'P'
0x180036095  mov     [rsp+150h+lpcbData], rax; lpcbData
0x18003609a  xor     r8d, r8d; lpReserved
0x18003609d  lea     rax, [rsp+150h+var_F0]
0x1800360a2  mov     [rsp+150h+var_130], rax; lpData
0x1800360a7  call    cs:__imp_RegQueryValueExW
0x1800360ae  nop     dword ptr [rax+rax+00h]
0x1800360b3  lea     rdx, [rsp+150h+var_F0]; lpString2
0x1800360b8  mov     rcx, r12; lpString1
0x1800360bb  call    cs:__imp_lstrcmpiW
0x1800360c2  nop     dword ptr [rax+rax+00h]
0x1800360c7  mov     rcx, [rsp+150h+var_110]; hKey
0x1800360cc  test    eax, eax
0x1800360ce  jz      short loc_1800360E3
0x1800360d0  call    cs:__imp_RegCloseKey
0x1800360d7  nop     dword ptr [rax+rax+00h]
0x1800360dc  inc     edi
0x1800360de  jmp     loc_180036026
0x1800360e3  mov     r8, r15; unsigned __int16 **
0x1800360e6  lea     rdx, aDeploymentName; "Deployment Name"
0x1800360ed  call    ?ReadStringValue@@YAKPEAUHKEY__@@PEBGPEAPEAG@Z; ReadStringValue(HKEY__ *,ushort const *,ushort * *)
0x1800360f2  mov     rcx, [rsp+150h+var_110]; hKey
0x1800360f7  lea     rdx, aSupporturl; "SupportUrl"
0x1800360fe  mov     r8, r14; unsigned __int16 **
0x180036101  call    ?ReadStringValue@@YAKPEAUHKEY__@@PEBGPEAPEAG@Z; ReadStringValue(HKEY__ *,ushort const *,ushort * *)
0x180036106  mov     rcx, [rsp+150h+var_110]; hKey
0x18003610b  call    cs:__imp_RegCloseKey
0x180036112  nop     dword ptr [rax+rax+00h]
0x180036117  mov     rcx, [rsp+150h+hKey]; hKey
0x18003611c  call    cs:__imp_RegCloseKey
0x180036123  nop     dword ptr [rax+rax+00h]
0x180036128  cmp     qword ptr [r15], 0
0x18003612c  jnz     short loc_180036134
0x18003612e  cmp     qword ptr [r14], 0
0x180036132  jz      short loc_180036169
0x180036134  mov     rcx, [rbp+50h+var_40]
0x180036138  xor     rcx, rsp; StackCookie
0x18003613b  call    __security_check_cookie
0x180036140  add     rsp, 120h
0x180036147  pop     r15
0x180036149  pop     r14
0x18003614b  pop     r12
0x18003614d  pop     rdi
0x18003614e  pop     rsi
0x18003614f  pop     rbx
0x180036150  pop     rbp
0x180036151  retn
0x180036153  mov     rcx, [rsp+150h+hKey]; hKey
0x180036158  test    rcx, rcx
0x18003615b  jz      short loc_180036169
0x18003615d  call    cs:__imp_RegCloseKey
0x180036164  nop     dword ptr [rax+rax+00h]
0x180036169  inc     ebx
0x18003616b  jmp     loc_180035F51
```
