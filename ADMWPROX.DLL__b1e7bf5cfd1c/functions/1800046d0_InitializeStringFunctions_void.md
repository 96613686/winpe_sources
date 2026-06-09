# InitializeStringFunctions(void)

- ea: `0x1800046d0`
- end: `0x180004785`
- name: `?InitializeStringFunctions@@YAKXZ`
- size: `181`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x180002400`

## callees

- `0x1800046d0`
- `0x180008410`

## import_xrefs

- `KERNEL32!GetCPInfo` at `0x1800046fd`
- `KERNEL32!GetCPInfo` at `0x1800046fd`
- `ADVAPI32!RegCloseKey` at `0x18000476b`
- `ADVAPI32!RegCloseKey` at `0x18000476b`
- `ADVAPI32!RegQueryValueExA` at `0x180004760`
- `ADVAPI32!RegQueryValueExA` at `0x180004760`
- `ADVAPI32!RegOpenKeyExA` at `0x180004724`
- `ADVAPI32!RegOpenKeyExA` at `0x180004724`

## string_xrefs

- `0x180004716`: `System\CurrentControlSet\Services\InetInfo\Parameters`

## pseudocode

```c
__int64 InitializeStringFunctions(void)
{
  DWORD cbData; // [rsp+30h] [rbp-38h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-34h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-30h] BYREF
  _cpinfo CPInfo; // [rsp+40h] [rbp-28h] BYREF

  hKey = 0;
  memset(&CPInfo, 0, sizeof(CPInfo));
  GetCPInfo(0, &CPInfo);
  if ( !RegOpenKeyExA(
          HKEY_LOCAL_MACHINE,
          "System\\CurrentControlSet\\Services\\InetInfo\\Parameters",
          0,
          0x20019u,
          &hKey) )
  {
    *(_DWORD *)Data = 0;
    cbData = 4;
    RegQueryValueExA(hKey, "FavorDBCS", 0, 0, Data, &cbData);
    RegCloseKey(hKey);
  }
  return 0;
}

```

## disassembly

```asm
0x1800046d0  sub     rsp, 68h
0x1800046d4  mov     rax, cs:__security_cookie
0x1800046db  xor     rax, rsp
0x1800046de  mov     [rsp+68h+var_10], rax
0x1800046e3  xor     eax, eax
0x1800046e5  lea     rdx, [rsp+68h+CPInfo]; lpCPInfo
0x1800046ea  xorps   xmm0, xmm0
0x1800046ed  mov     dword ptr [rsp+68h+CPInfo.LeadByte+0Ah], eax
0x1800046f1  xor     ecx, ecx; CodePage
0x1800046f3  mov     [rsp+68h+hKey], rax
0x1800046f8  movups  xmmword ptr [rsp+68h+CPInfo.MaxCharSize], xmm0
0x1800046fd  call    cs:__imp_GetCPInfo
0x180004703  lea     rax, [rsp+68h+hKey]
0x180004708  mov     r9d, 20019h; samDesired
0x18000470e  xor     r8d, r8d; ulOptions
0x180004711  mov     [rsp+68h+phkResult], rax; phkResult
0x180004716  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\In"...
0x18000471d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180004724  call    cs:__imp_RegOpenKeyExA
0x18000472a  test    eax, eax
0x18000472c  jnz     short loc_180004771
0x18000472e  mov     rcx, [rsp+68h+hKey]; hKey
0x180004733  lea     rdx, ValueName; "FavorDBCS"
0x18000473a  mov     dword ptr [rsp+68h+Data], eax
0x18000473e  xor     r9d, r9d; lpType
0x180004741  lea     rax, [rsp+68h+cbData]
0x180004746  mov     [rsp+68h+cbData], 4
0x18000474e  mov     [rsp+68h+lpcbData], rax; lpcbData
0x180004753  xor     r8d, r8d; lpReserved
0x180004756  lea     rax, [rsp+68h+Data]
0x18000475b  mov     [rsp+68h+phkResult], rax; lpData
0x180004760  call    cs:__imp_RegQueryValueExA
0x180004766  mov     rcx, [rsp+68h+hKey]; hKey
0x18000476b  call    cs:__imp_RegCloseKey
0x180004771  xor     eax, eax
0x180004773  mov     rcx, [rsp+68h+var_10]
0x180004778  xor     rcx, rsp; StackCookie
0x18000477b  call    __security_check_cookie
0x180004780  add     rsp, 68h
0x180004784  retn
```
