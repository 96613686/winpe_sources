# GetLocalManagedApplicationData

- ea: `0x180032490`
- end: `0x1800326cd`
- name: `GetLocalManagedApplicationData`
- size: `573`
- prototype: `void __stdcall(LPWSTR ProductCode, LPWSTR *DisplayName, LPWSTR *SupportUrl)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180025af0`
- `0x180032490`
- `0x18004357c`
- `0x180065090`

## import_xrefs

- `KERNELBASE!lstrcmpiW` at `0x180032637`
- `KERNELBASE!lstrcmpiW` at `0x180032637`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180032508`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180032508`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003259e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180032629`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003259e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180032629`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180032551`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800325e8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180032551`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800325e8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180032562`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180032646`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003267b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180032686`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800326c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180032562`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180032646`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003267b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180032686`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800326c0`

## pseudocode

```c
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
0x180032490  push    rbp
0x180032492  push    rbx
0x180032493  push    rsi
0x180032494  push    rdi
0x180032495  push    r12
0x180032497  push    r14
0x180032499  push    r15
0x18003249b  lea     rbp, [rsp-20h]
0x1800324a0  sub     rsp, 120h
0x1800324a7  mov     rax, cs:__security_cookie
0x1800324ae  xor     rax, rsp
0x1800324b1  mov     [rbp+50h+var_40], rax
0x1800324b5  mov     qword ptr [rdx], 0
0x1800324bc  mov     r14, r8
0x1800324bf  mov     qword ptr [r8], 0
0x1800324c6  mov     r15, rdx
0x1800324c9  mov     r12, rcx
0x1800324cc  mov     [rsp+150h+phkResult], 0
0x1800324d5  mov     [rsp+150h+hKey], 0
0x1800324de  xor     ebx, ebx
0x1800324e0  mov     [rsp+150h+var_110], 0
0x1800324e9  mov     [rsp+150h+cbData], 0
0x1800324f1  cmp     ebx, 2
0x1800324f4  jge     loc_180032698
0x1800324fa  test    ebx, ebx
0x1800324fc  jnz     short loc_180032520
0x1800324fe  lea     rdx, [rsp+150h+phkResult]; phkResult
0x180032503  mov     ecx, 20019h; samDesired
0x180032508  call    cs:__imp_RegOpenCurrentUser
0x18003250e  lea     edi, [rbx+1]
0x180032511  test    eax, eax
0x180032513  jnz     loc_180032698
0x180032519  mov     rcx, [rsp+150h+phkResult]
0x18003251e  jmp     short loc_18003252E
0x180032520  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180032527  xor     edi, edi
0x180032529  mov     [rsp+150h+phkResult], rcx
0x18003252e  lea     rax, [rsp+150h+hKey]
0x180032533  mov     [rsp+150h+hKey], 0
0x18003253c  mov     r9d, 20019h; samDesired
0x180032542  mov     [rsp+150h+var_130], rax; phkResult
0x180032547  xor     r8d, r8d; ulOptions
0x18003254a  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180032551  call    cs:__imp_RegOpenKeyExW
0x180032557  mov     esi, eax
0x180032559  test    edi, edi
0x18003255b  jz      short loc_180032568
0x18003255d  mov     rcx, [rsp+150h+phkResult]; hKey
0x180032562  call    cs:__imp_RegCloseKey
0x180032568  test    esi, esi
0x18003256a  jnz     loc_1800326B6
0x180032570  mov     rcx, [rsp+150h+hKey]; hKey
0x180032575  lea     rax, [rsp+150h+cbData]
0x18003257a  mov     [rsp+150h+lpcbData], rax; lpcbData
0x18003257f  xor     r9d, r9d; lpType
0x180032582  lea     rax, [rsp+150h+Data]
0x180032587  mov     dword ptr [rsp+150h+Data], esi
0x18003258b  xor     r8d, r8d; lpReserved
0x18003258e  mov     [rsp+150h+var_130], rax; lpData
0x180032593  mov     rdx, r12; lpValueName
0x180032596  mov     [rsp+150h+cbData], 4
0x18003259e  call    cs:__imp_RegQueryValueExW
0x1800325a4  test    eax, eax
0x1800325a6  jnz     loc_1800326B6
0x1800325ac  xor     edi, edi
0x1800325ae  mov     rcx, [rsp+150h+hKey]; hKey
0x1800325b3  lea     r8, [rbp+50h+Name]; lpName
0x1800325b7  mov     r9d, 2Ch ; ','; cchName
0x1800325bd  mov     edx, edi; dwIndex
0x1800325bf  call    RegEnumKeyW
0x1800325c4  test    eax, eax
0x1800325c6  jnz     loc_180032681
0x1800325cc  mov     rcx, [rsp+150h+hKey]; hKey
0x1800325d1  lea     rax, [rsp+150h+var_110]
0x1800325d6  mov     r9d, 20019h; samDesired
0x1800325dc  mov     [rsp+150h+var_130], rax; phkResult
0x1800325e1  xor     r8d, r8d; ulOptions
0x1800325e4  lea     rdx, [rbp+50h+Name]; lpSubKey
0x1800325e8  call    cs:__imp_RegOpenKeyExW
0x1800325ee  test    eax, eax
0x1800325f0  jnz     loc_180032681
0x1800325f6  mov     rcx, [rsp+150h+var_110]; hKey
0x1800325fb  lea     rdx, aProductId; "Product ID"
0x180032602  mov     word ptr [rsp+150h+var_F0], ax
0x180032607  xor     r9d, r9d; lpType
0x18003260a  lea     rax, [rsp+150h+cbData]
0x18003260f  mov     [rsp+150h+cbData], 50h ; 'P'
0x180032617  mov     [rsp+150h+lpcbData], rax; lpcbData
0x18003261c  xor     r8d, r8d; lpReserved
0x18003261f  lea     rax, [rsp+150h+var_F0]
0x180032624  mov     [rsp+150h+var_130], rax; lpData
0x180032629  call    cs:__imp_RegQueryValueExW
0x18003262f  lea     rdx, [rsp+150h+var_F0]; lpString2
0x180032634  mov     rcx, r12; lpString1
0x180032637  call    cs:__imp_lstrcmpiW
0x18003263d  mov     rcx, [rsp+150h+var_110]; hKey
0x180032642  test    eax, eax
0x180032644  jz      short loc_180032653
0x180032646  call    cs:__imp_RegCloseKey
0x18003264c  inc     edi
0x18003264e  jmp     loc_1800325AE
0x180032653  mov     r8, r15; unsigned __int16 **
0x180032656  lea     rdx, aDeploymentName; "Deployment Name"
0x18003265d  call    ?ReadStringValue@@YAKPEAUHKEY__@@PEBGPEAPEAG@Z; ReadStringValue(HKEY__ *,ushort const *,ushort * *)
0x180032662  mov     rcx, [rsp+150h+var_110]; hKey
0x180032667  lea     rdx, aSupporturl; "SupportUrl"
0x18003266e  mov     r8, r14; unsigned __int16 **
0x180032671  call    ?ReadStringValue@@YAKPEAUHKEY__@@PEBGPEAPEAG@Z; ReadStringValue(HKEY__ *,ushort const *,ushort * *)
0x180032676  mov     rcx, [rsp+150h+var_110]; hKey
0x18003267b  call    cs:__imp_RegCloseKey
0x180032681  mov     rcx, [rsp+150h+hKey]; hKey
0x180032686  call    cs:__imp_RegCloseKey
0x18003268c  cmp     qword ptr [r15], 0
0x180032690  jnz     short loc_180032698
0x180032692  cmp     qword ptr [r14], 0
0x180032696  jz      short loc_1800326C6
0x180032698  mov     rcx, [rbp+50h+var_40]
0x18003269c  xor     rcx, rsp; StackCookie
0x18003269f  call    __security_check_cookie
0x1800326a4  add     rsp, 120h
0x1800326ab  pop     r15
0x1800326ad  pop     r14
0x1800326af  pop     r12
0x1800326b1  pop     rdi
0x1800326b2  pop     rsi
0x1800326b3  pop     rbx
0x1800326b4  pop     rbp
0x1800326b5  retn
0x1800326b6  mov     rcx, [rsp+150h+hKey]; hKey
0x1800326bb  test    rcx, rcx
0x1800326be  jz      short loc_1800326C6
0x1800326c0  call    cs:__imp_RegCloseKey
0x1800326c6  inc     ebx
0x1800326c8  jmp     loc_1800324F1
```
