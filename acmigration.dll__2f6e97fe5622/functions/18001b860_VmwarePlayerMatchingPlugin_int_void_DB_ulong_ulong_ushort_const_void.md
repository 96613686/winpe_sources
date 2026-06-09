# VmwarePlayerMatchingPlugin(int *,void *,_DB *,ulong,ulong,ushort const *,void *)

- ea: `0x18001b860`
- end: `0x18001ba7b`
- name: `?VmwarePlayerMatchingPlugin@@YAHPEAHPEAXPEAU_DB@@KKPEBG1@Z`
- size: `539`
- prototype: `__int64 __fastcall(int *, void *, struct _DB *, unsigned int, unsigned int, const unsigned __int16 *, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x180001cf0`
- `0x18001b860`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x18001b9b4`
- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x18001b9b4`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18001b9d3`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18001b9d3`
- `ADVAPI32!RegQueryValueExW` at `0x18001b932`
- `ADVAPI32!RegQueryValueExW` at `0x18001b986`
- `ADVAPI32!RegQueryValueExW` at `0x18001b932`
- `ADVAPI32!RegQueryValueExW` at `0x18001b986`
- `ADVAPI32!RegCloseKey` at `0x18001ba41`
- `ADVAPI32!RegCloseKey` at `0x18001ba41`
- `ADVAPI32!RegSetValueExW` at `0x18001ba2c`
- `ADVAPI32!RegSetValueExW` at `0x18001ba2c`
- `ADVAPI32!RegOpenKeyExW` at `0x18001b8f4`
- `ADVAPI32!RegOpenKeyExW` at `0x18001b8f4`

## string_xrefs

- `0x18001b889`: `SYSTEM\ControlSet\Services\VMware NAT Service`
- `0x18001b89c`: `SYSTEM\ControlSet001\Services\VMware NAT Service`
- `0x18001b8b0`: `SYSTEM\ControlSet\Services\VMnetDHCP`
- `0x18001b8c1`: `SYSTEM\ControlSet001\Services\VMnetDHCP`
- `0x18001b97a`: `ImagePath`
- `0x18001ba14`: `ImagePath`
- `0x18001b9c7`: `\SYSTEM32\`

## pseudocode

```c
__int64 __fastcall VmwarePlayerMatchingPlugin(int *a1, void *a2, struct _DB *a3)
{
  __int64 v3; // rsi
  HKEY v4; // rcx
  DWORD i; // edi
  __int64 v6; // rbx
  wint_t v7; // ax
  wchar_t *v8; // rax
  __int64 v9; // rax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  LPCWSTR lpSubKey[4]; // [rsp+40h] [rbp-C0h]
  wchar_t Data[264]; // [rsp+60h] [rbp-A0h] BYREF

  lpSubKey[0] = L"SYSTEM\\ControlSet\\Services\\VMware NAT Service";
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  lpSubKey[1] = L"SYSTEM\\ControlSet001\\Services\\VMware NAT Service";
  v3 = 0;
  Type = 0;
  lpSubKey[2] = L"SYSTEM\\ControlSet\\Services\\VMnetDHCP";
  lpSubKey[3] = L"SYSTEM\\ControlSet001\\Services\\VMnetDHCP";
  cbData = 0;
  *a1 = 0;
  do
  {
    if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey[v3], 0, 0x2001Bu, &hKey) )
      goto LABEL_14;
    cbData = 520;
    if ( RegQueryValueExW(hKey, L"WOW64", 0, &Type, (LPBYTE)Data, &cbData) || Type != 4 )
      goto LABEL_14;
    v4 = hKey;
    if ( *(_DWORD *)Data == 1 )
    {
      cbData = 518;
      if ( !RegQueryValueExW(hKey, L"ImagePath", 0, &Type, (LPBYTE)Data, &cbData) && Type - 1 <= 1 )
      {
        for ( i = 0; i < cbData; Data[v6] = v7 )
        {
          v6 = i;
          v7 = towupper(Data[i++]);
        }
        v8 = wcsstr(Data, L"\\SYSTEM32\\");
        if ( v8 )
        {
          *(_OWORD *)v8 = *(_OWORD *)L"\\SYSWOW64\\";
          *((_DWORD *)v8 + 4) = *(_DWORD *)L"4\\";
          v9 = -1;
          do
            ++v9;
          while ( Data[v9] );
          RegSetValueExW(hKey, L"ImagePath", 0, Type, (const BYTE *)Data, 2 * v9 + 2);
        }
      }
LABEL_14:
      v4 = hKey;
      if ( (unsigned __int64)hKey - 1 > 0xFFFFFFFFFFFFFFFDuLL )
        goto LABEL_16;
    }
    RegCloseKey(v4);
    hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
LABEL_16:
    ++v3;
  }
  while ( v3 != 4 );
  return 1;
}

```

## disassembly

```asm
0x18001b860  push    rbp
0x18001b862  push    rbx
0x18001b863  push    rsi
0x18001b864  push    rdi
0x18001b865  push    r12
0x18001b867  push    r14
0x18001b869  lea     rbp, [rsp-188h]
0x18001b871  sub     rsp, 288h
0x18001b878  mov     rax, cs:__security_cookie
0x18001b87f  xor     rax, rsp
0x18001b882  mov     [rbp+1B0h+var_40], rax
0x18001b889  lea     rax, aSystemControls_0; "SYSTEM\\ControlSet\\Services\\VMware NA"...
0x18001b890  or      r12, 0FFFFFFFFFFFFFFFFh
0x18001b894  xor     r14d, r14d
0x18001b897  mov     [rsp+2B0h+lpSubKey], rax
0x18001b89c  lea     rax, aSystemControls_2; "SYSTEM\\ControlSet001\\Services\\VMware"...
0x18001b8a3  mov     [rsp+2B0h+hKey], r12
0x18001b8a8  mov     [rsp+2B0h+var_268], rax
0x18001b8ad  mov     esi, r14d
0x18001b8b0  lea     rax, aSystemControls; "SYSTEM\\ControlSet\\Services\\VMnetDHCP"
0x18001b8b7  mov     [rsp+2B0h+Type], r14d
0x18001b8bc  mov     [rsp+2B0h+var_260], rax
0x18001b8c1  lea     rax, aSystemControls_1; "SYSTEM\\ControlSet001\\Services\\VMnetD"...
0x18001b8c8  mov     [rsp+2B0h+var_258], rax
0x18001b8cd  mov     [rsp+2B0h+cbData], r14d
0x18001b8d2  mov     [rcx], r14d
0x18001b8d5  mov     rdx, [rsp+rsi*8+2B0h+lpSubKey]; lpSubKey
0x18001b8da  lea     rax, [rsp+2B0h+hKey]
0x18001b8df  mov     r9d, 2001Bh; samDesired
0x18001b8e5  mov     [rsp+2B0h+phkResult], rax; phkResult
0x18001b8ea  xor     r8d, r8d; ulOptions
0x18001b8ed  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001b8f4  call    cs:__imp_RegOpenKeyExW
0x18001b8fa  test    eax, eax
0x18001b8fc  jnz     loc_18001BA32
0x18001b902  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18001b907  lea     rax, [rsp+2B0h+cbData]
0x18001b90c  mov     [rsp+2B0h+lpcbData], rax; lpcbData
0x18001b911  lea     r9, [rsp+2B0h+Type]; lpType
0x18001b916  lea     rax, [rsp+2B0h+Data]
0x18001b91b  mov     [rsp+2B0h+cbData], 208h
0x18001b923  xor     r8d, r8d; lpReserved
0x18001b926  mov     [rsp+2B0h+phkResult], rax; lpData
0x18001b92b  lea     rdx, aWow64; "WOW64"
0x18001b932  call    cs:__imp_RegQueryValueExW
0x18001b938  test    eax, eax
0x18001b93a  jnz     loc_18001BA32
0x18001b940  cmp     [rsp+2B0h+Type], 4
0x18001b945  jnz     loc_18001BA32
0x18001b94b  cmp     dword ptr [rsp+2B0h+Data], 1
0x18001b950  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18001b955  jnz     loc_18001BA41
0x18001b95b  lea     rax, [rsp+2B0h+cbData]
0x18001b960  mov     [rsp+2B0h+cbData], 206h
0x18001b968  mov     [rsp+2B0h+lpcbData], rax; lpcbData
0x18001b96d  lea     r9, [rsp+2B0h+Type]; lpType
0x18001b972  lea     rax, [rsp+2B0h+Data]
0x18001b977  xor     r8d, r8d; lpReserved
0x18001b97a  lea     rdx, aImagepath; "ImagePath"
0x18001b981  mov     [rsp+2B0h+phkResult], rax; lpData
0x18001b986  call    cs:__imp_RegQueryValueExW
0x18001b98c  test    eax, eax
0x18001b98e  jnz     loc_18001BA32
0x18001b994  mov     eax, [rsp+2B0h+Type]
0x18001b998  dec     eax
0x18001b99a  cmp     eax, 1
0x18001b99d  ja      loc_18001BA32
0x18001b9a3  mov     edi, r14d
0x18001b9a6  cmp     [rsp+2B0h+cbData], r14d
0x18001b9ab  jbe     short loc_18001B9C7
0x18001b9ad  mov     ebx, edi
0x18001b9af  movzx   ecx, [rsp+rbx*2+2B0h+Data]; C
0x18001b9b4  call    cs:__imp_towupper
0x18001b9ba  inc     edi
0x18001b9bc  mov     [rsp+rbx*2+2B0h+Data], ax
0x18001b9c1  cmp     edi, [rsp+2B0h+cbData]
0x18001b9c5  jb      short loc_18001B9AD
0x18001b9c7  lea     rdx, aSystem32; "\\SYSTEM32\\"
0x18001b9ce  lea     rcx, [rsp+2B0h+Data]; Str
0x18001b9d3  call    cs:__imp_wcsstr
0x18001b9d9  test    rax, rax
0x18001b9dc  jz      short loc_18001BA32
0x18001b9de  movups  xmm0, xmmword ptr cs:aSyswow64_0; "\\SYSWOW64\\"
0x18001b9e5  movups  xmmword ptr [rax], xmm0
0x18001b9e8  mov     ecx, dword ptr cs:aSyswow64_0+10h; "4\\"
0x18001b9ee  mov     [rax+10h], ecx
0x18001b9f1  lea     rcx, [rsp+2B0h+Data]
0x18001b9f6  mov     rax, r12
0x18001b9f9  inc     rax
0x18001b9fc  cmp     [rcx+rax*2], r14w
0x18001ba01  jnz     short loc_18001B9F9
0x18001ba03  mov     r9d, [rsp+2B0h+Type]; dwType
0x18001ba08  lea     eax, ds:2[rax*2]
0x18001ba0f  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18001ba14  lea     rdx, aImagepath; "ImagePath"
0x18001ba1b  mov     dword ptr [rsp+2B0h+lpcbData], eax; cbData
0x18001ba1f  xor     r8d, r8d; Reserved
0x18001ba22  lea     rax, [rsp+2B0h+Data]
0x18001ba27  mov     [rsp+2B0h+phkResult], rax; lpData
0x18001ba2c  call    cs:__imp_RegSetValueExW
0x18001ba32  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18001ba37  lea     rdx, [rcx-1]
0x18001ba3b  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18001ba3f  ja      short loc_18001BA4C
0x18001ba41  call    cs:__imp_RegCloseKey
0x18001ba47  mov     [rsp+2B0h+hKey], r12
0x18001ba4c  inc     rsi
0x18001ba4f  cmp     rsi, 4
0x18001ba53  jnz     loc_18001B8D5
0x18001ba59  lea     eax, [rsi-3]
0x18001ba5c  mov     rcx, [rbp+1B0h+var_40]
0x18001ba63  xor     rcx, rsp; StackCookie
0x18001ba66  call    __security_check_cookie
0x18001ba6b  add     rsp, 288h
0x18001ba72  pop     r14
0x18001ba74  pop     r12
0x18001ba76  pop     rdi
0x18001ba77  pop     rsi
0x18001ba78  pop     rbx
0x18001ba79  pop     rbp
0x18001ba7a  retn
```
