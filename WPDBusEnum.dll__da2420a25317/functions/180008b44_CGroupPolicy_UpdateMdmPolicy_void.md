# CGroupPolicy::UpdateMdmPolicy(void)

- ea: `0x180008b44`
- end: `0x180008e0f`
- name: `?UpdateMdmPolicy@CGroupPolicy@@IEAAXXZ`
- size: `715`
- prototype: `void __fastcall(CGroupPolicy *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800069d0`

## callees

- `0x180002fa0`
- `0x180008b44`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008dfe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008dfe`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008d52`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008d79`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008da2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008dd2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008d52`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008d79`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008da2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008dd2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180008cec`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180008cfd`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180008d0e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180008d1f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180008cec`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180008cfd`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180008d0e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180008d1f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180008cc2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180008cc2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008bbd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008c13`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008c5a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008bbd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008c13`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008c5a`

## string_xrefs

- `0x180008bed`: `MDMRegSet`
- `0x180008cf6`: `MDMRegSet`
- `0x180008d5c`: `MDMRegSet`
- `0x180008ccf`: `Failed to create the GPO root key with (%d)\n`
- `0x180008ddc`: `Failed to set GP registry entry for MDM.\n`

## pseudocode

```c
void __fastcall CGroupPolicy::UpdateMdmPolicy(CGroupPolicy *this)
{
  int v2; // eax
  LSTATUS v3; // eax
  unsigned int v4; // eax
  LSTATUS v5; // ebx
  int v6; // edi
  LSTATUS v7; // eax
  int v8; // [rsp+50h] [rbp-10h] BYREF
  int v9; // [rsp+54h] [rbp-Ch] BYREF
  HKEY hKey; // [rsp+58h] [rbp-8h] BYREF
  int Data; // [rsp+98h] [rbp+38h] BYREF
  DWORD pcbData; // [rsp+A0h] [rbp+40h] BYREF
  unsigned int pvData; // [rsp+A8h] [rbp+48h] BYREF

  pvData = -1;
  Data = 0;
  v8 = 0;
  v9 = 0;
  hKey = 0;
  pcbData = 4;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\PolicyManager\\current\\Device\\System",
          L"AllowStorageCard",
          0x18u,
          0,
          &pvData,
          &pcbData)
    && pvData <= 1
    && pvData != *((_DWORD *)this + 12) )
  {
    pcbData = 4;
    if ( RegGetValueW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Policies\\Microsoft\\Windows\\RemovableStorageDevices",
           L"MDMRegSet",
           0x18u,
           0,
           &v9,
           &pcbData) )
    {
      v9 = 0;
    }
    pcbData = 4;
    if ( RegGetValueW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Policies\\Microsoft\\Windows\\RemovableStorageDevices",
           L"Deny_All",
           0x18u,
           0,
           &v8,
           &pcbData) )
    {
      v2 = 0;
      v8 = 0;
    }
    else
    {
      v2 = v8;
    }
    if ( (v9 == 1 || !pvData) && pvData == v2 )
    {
      v3 = RegCreateKeyExW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Policies\\Microsoft\\Windows\\RemovableStorageDevices",
             0,
             0,
             0,
             0x20006u,
             0,
             &hKey,
             0);
      if ( v3 )
      {
        GPDebugPrintX(2, "Failed to create the GPO root key with (%d)\n", v3);
        return;
      }
      RegDeleteValueW(hKey, L"Deny_All");
      RegDeleteValueW(hKey, L"MDMRegSet");
      RegDeleteValueW(hKey, L"RebootTimeinSeconds");
      RegDeleteValueW(hKey, L"RebootTimeinSeconds_state");
      v4 = pvData;
      if ( !pvData )
      {
        Data = 1;
        v5 = RegSetValueExW(hKey, L"Deny_All", 0, 4u, (const BYTE *)&Data, 4u);
        v6 = v5 | RegSetValueExW(hKey, L"MDMRegSet", 0, 4u, (const BYTE *)&Data, 4u);
        v7 = RegSetValueExW(hKey, L"RebootTimeinSeconds_state", 0, 4u, (const BYTE *)&Data, 4u);
        Data = 300;
        if ( v6 | v7 | RegSetValueExW(hKey, L"RebootTimeinSeconds", 0, 4u, (const BYTE *)&Data, 4u) )
        {
          GPDebugPrintX(2, "Failed to set GP registry entry for MDM.\n");
          goto LABEL_19;
        }
        v4 = pvData;
      }
      *((_DWORD *)this + 12) = v4;
LABEL_19:
      if ( hKey )
        RegCloseKey(hKey);
    }
  }
}

```

## disassembly

```asm
0x180008b44  push    rbp
0x180008b46  push    rbx
0x180008b47  push    rsi
0x180008b48  push    rdi
0x180008b49  push    r15
0x180008b4b  mov     rbp, rsp
0x180008b4e  sub     rsp, 60h
0x180008b52  mov     r15d, 4
0x180008b58  mov     [rbp+arg_18], 0FFFFFFFFh
0x180008b5f  lea     rax, [rbp+arg_10]
0x180008b63  mov     [rbp+Data], 0
0x180008b6a  mov     [rsp+60h+pcbData], rax; pcbData
0x180008b6f  lea     r8, aAllowstorageca; "AllowStorageCard"
0x180008b76  lea     rax, [rbp+arg_18]
0x180008b7a  mov     [rbp+var_10], 0
0x180008b81  mov     rsi, rcx
0x180008b84  mov     [rsp+60h+pvData], rax; pvData
0x180008b89  lea     edi, [r15+14h]
0x180008b8d  mov     [rbp+var_C], 0
0x180008b94  mov     rbx, 0FFFFFFFF80000002h
0x180008b9b  mov     [rbp+hKey], 0
0x180008ba3  mov     r9d, edi; dwFlags
0x180008ba6  mov     [rbp+arg_10], r15d
0x180008baa  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\PolicyManager\\cur"...
0x180008bb1  mov     [rsp+60h+pdwType], 0; pdwType
0x180008bba  mov     rcx, rbx; hkey
0x180008bbd  call    cs:__imp_RegGetValueW
0x180008bc3  test    eax, eax
0x180008bc5  jnz     loc_180008E04
0x180008bcb  mov     eax, [rbp+arg_18]
0x180008bce  cmp     eax, 1
0x180008bd1  ja      loc_180008E04
0x180008bd7  cmp     eax, [rsi+30h]
0x180008bda  jz      loc_180008E04
0x180008be0  lea     rax, [rbp+arg_10]
0x180008be4  mov     [rbp+arg_10], r15d
0x180008be8  mov     [rsp+60h+pcbData], rax; pcbData
0x180008bed  lea     r8, aMdmregset; "MDMRegSet"
0x180008bf4  lea     rax, [rbp+var_C]
0x180008bf8  mov     r9d, edi; dwFlags
0x180008bfb  mov     [rsp+60h+pvData], rax; pvData
0x180008c00  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x180008c07  mov     rcx, rbx; hkey
0x180008c0a  mov     [rsp+60h+pdwType], 0; pdwType
0x180008c13  call    cs:__imp_RegGetValueW
0x180008c19  test    eax, eax
0x180008c1b  jz      short loc_180008C24
0x180008c1d  mov     [rbp+var_C], 0
0x180008c24  lea     rax, [rbp+arg_10]
0x180008c28  mov     [rbp+arg_10], r15d
0x180008c2c  mov     [rsp+60h+pcbData], rax; pcbData
0x180008c31  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x180008c38  mov     r9d, edi; dwFlags
0x180008c3b  lea     rax, [rbp+var_10]
0x180008c3f  mov     [rsp+60h+pvData], rax; pvData
0x180008c44  lea     rdi, aDenyAll; "Deny_All"
0x180008c4b  mov     r8, rdi; lpValue
0x180008c4e  mov     [rsp+60h+pdwType], 0; pdwType
0x180008c57  mov     rcx, rbx; hkey
0x180008c5a  call    cs:__imp_RegGetValueW
0x180008c60  test    eax, eax
0x180008c62  jz      short loc_180008C6B
0x180008c64  xor     eax, eax
0x180008c66  mov     [rbp+var_10], eax
0x180008c69  jmp     short loc_180008C6E
0x180008c6b  mov     eax, [rbp+var_10]
0x180008c6e  cmp     [rbp+var_C], 1
0x180008c72  mov     edx, [rbp+arg_18]
0x180008c75  jz      short loc_180008C7F
0x180008c77  test    edx, edx
0x180008c79  jnz     loc_180008E04
0x180008c7f  cmp     edx, eax
0x180008c81  jnz     loc_180008E04
0x180008c87  mov     [rsp+60h+lpdwDisposition], 0; lpdwDisposition
0x180008c90  lea     rax, [rbp+hKey]
0x180008c94  mov     [rsp+60h+phkResult], rax; phkResult
0x180008c99  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x180008ca0  mov     [rsp+60h+pcbData], 0; lpSecurityAttributes
0x180008ca9  xor     r9d, r9d; lpClass
0x180008cac  mov     dword ptr [rsp+60h+pvData], 20006h; samDesired
0x180008cb4  xor     r8d, r8d; Reserved
0x180008cb7  mov     rcx, rbx; hKey
0x180008cba  mov     dword ptr [rsp+60h+pdwType], 0; dwOptions
0x180008cc2  call    cs:__imp_RegCreateKeyExW
0x180008cc8  test    eax, eax
0x180008cca  jz      short loc_180008CE5
0x180008ccc  mov     r8d, eax
0x180008ccf  lea     rdx, aFailedToCreate_0; "Failed to create the GPO root key with "...
0x180008cd6  mov     ecx, 2; unsigned int
0x180008cdb  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x180008ce0  jmp     loc_180008E04
0x180008ce5  mov     rcx, [rbp+hKey]; hKey
0x180008ce9  mov     rdx, rdi; lpValueName
0x180008cec  call    cs:__imp_RegDeleteValueW
0x180008cf2  mov     rcx, [rbp+hKey]; hKey
0x180008cf6  lea     rdx, aMdmregset; "MDMRegSet"
0x180008cfd  call    cs:__imp_RegDeleteValueW
0x180008d03  mov     rcx, [rbp+hKey]; hKey
0x180008d07  lea     rdx, aReboottimeinse_0; "RebootTimeinSeconds"
0x180008d0e  call    cs:__imp_RegDeleteValueW
0x180008d14  mov     rcx, [rbp+hKey]; hKey
0x180008d18  lea     rdx, aReboottimeinse; "RebootTimeinSeconds_state"
0x180008d1f  call    cs:__imp_RegDeleteValueW
0x180008d25  mov     eax, [rbp+arg_18]
0x180008d28  test    eax, eax
0x180008d2a  jnz     loc_180008DF2
0x180008d30  mov     rcx, [rbp+hKey]; hKey
0x180008d34  lea     rax, [rbp+Data]
0x180008d38  mov     dword ptr [rsp+60h+pvData], r15d; cbData
0x180008d3d  mov     r9d, r15d; dwType
0x180008d40  xor     r8d, r8d; Reserved
0x180008d43  mov     [rsp+60h+pdwType], rax; lpData
0x180008d48  mov     rdx, rdi; lpValueName
0x180008d4b  mov     [rbp+Data], 1
0x180008d52  call    cs:__imp_RegSetValueExW
0x180008d58  mov     rcx, [rbp+hKey]; hKey
0x180008d5c  lea     rdx, aMdmregset; "MDMRegSet"
0x180008d63  mov     ebx, eax
0x180008d65  mov     dword ptr [rsp+60h+pvData], r15d; cbData
0x180008d6a  lea     rax, [rbp+Data]
0x180008d6e  mov     r9d, r15d; dwType
0x180008d71  xor     r8d, r8d; Reserved
0x180008d74  mov     [rsp+60h+pdwType], rax; lpData
0x180008d79  call    cs:__imp_RegSetValueExW
0x180008d7f  mov     rcx, [rbp+hKey]; hKey
0x180008d83  lea     rdx, aReboottimeinse; "RebootTimeinSeconds_state"
0x180008d8a  mov     edi, eax
0x180008d8c  mov     dword ptr [rsp+60h+pvData], r15d; cbData
0x180008d91  lea     rax, [rbp+Data]
0x180008d95  mov     r9d, r15d; dwType
0x180008d98  xor     r8d, r8d; Reserved
0x180008d9b  mov     [rsp+60h+pdwType], rax; lpData
0x180008da0  or      edi, ebx
0x180008da2  call    cs:__imp_RegSetValueExW
0x180008da8  mov     rcx, [rbp+hKey]; hKey
0x180008dac  lea     rdx, aReboottimeinse_0; "RebootTimeinSeconds"
0x180008db3  mov     ebx, eax
0x180008db5  mov     dword ptr [rsp+60h+pvData], r15d; cbData
0x180008dba  lea     rax, [rbp+Data]
0x180008dbe  mov     [rbp+Data], 12Ch
0x180008dc5  mov     r9d, r15d; dwType
0x180008dc8  mov     [rsp+60h+pdwType], rax; lpData
0x180008dcd  xor     r8d, r8d; Reserved
0x180008dd0  or      ebx, edi
0x180008dd2  call    cs:__imp_RegSetValueExW
0x180008dd8  or      eax, ebx
0x180008dda  jz      short loc_180008DEF
0x180008ddc  lea     rdx, aFailedToSetGpR; "Failed to set GP registry entry for MDM"...
0x180008de3  mov     ecx, 2; unsigned int
0x180008de8  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x180008ded  jmp     short loc_180008DF5
0x180008def  mov     eax, [rbp+arg_18]
0x180008df2  mov     [rsi+30h], eax
0x180008df5  mov     rcx, [rbp+hKey]; hKey
0x180008df9  test    rcx, rcx
0x180008dfc  jz      short loc_180008E04
0x180008dfe  call    cs:__imp_RegCloseKey
0x180008e04  add     rsp, 60h
0x180008e08  pop     r15
0x180008e0a  pop     rdi
0x180008e0b  pop     rsi
0x180008e0c  pop     rbx
0x180008e0d  pop     rbp
0x180008e0e  retn
```
