# SetV2Status(ulong)

- ea: `0x14000ecf0`
- end: `0x14000edce`
- name: `?SetV2Status@@YAXK@Z`
- size: `222`
- prototype: `void __fastcall(int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x14000e590`

## callees

- `0x14000a390`
- `0x14000ecf0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14000ed36`
- `ADVAPI32!RegOpenKeyExW` at `0x14000ed36`
- `ADVAPI32!RegCloseKey` at `0x14000edb1`
- `ADVAPI32!RegCloseKey` at `0x14000edb1`
- `ADVAPI32!RegQueryValueExW` at `0x14000ed6c`
- `ADVAPI32!RegQueryValueExW` at `0x14000ed6c`
- `ADVAPI32!RegSetValueExW` at `0x14000eda7`
- `ADVAPI32!RegSetValueExW` at `0x14000eda7`

## string_xrefs

- `0x14000ed2f`: `SYSTEM\CurrentControlSet\Services\UCPD`

## pseudocode

```c
void __fastcall SetV2Status(int a1)
{
  LSTATUS v1; // eax
  bool v2; // zf
  HKEY hKey; // [rsp+30h] [rbp-20h] BYREF
  BYTE v4[8]; // [rsp+38h] [rbp-18h] BYREF
  BYTE Data[4]; // [rsp+40h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-Ch] BYREF

  *(_DWORD *)v4 = a1;
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services\\UCPD", 0, 0x2001Fu, &hKey) )
  {
    *(_DWORD *)Data = 0;
    cbData = 4;
    v1 = RegQueryValueExW(hKey, L"FeatureV2", 0, 0, Data, &cbData);
    if ( v1 )
    {
      if ( v1 != 2 )
      {
LABEL_8:
        RegCloseKey(hKey);
        return;
      }
      v2 = *(_DWORD *)v4 == 0;
    }
    else
    {
      v2 = *(_DWORD *)Data == *(_DWORD *)v4;
    }
    if ( !v2 )
      RegSetValueExW(hKey, L"FeatureV2", 0, 4u, v4, 4u);
    goto LABEL_8;
  }
}

```

## disassembly

```asm
0x14000ecf0  mov     [rsp-8+arg_8], rbx
0x14000ecf5  push    rbp
0x14000ecf6  mov     rbp, rsp
0x14000ecf9  sub     rsp, 50h
0x14000ecfd  mov     rax, cs:__security_cookie
0x14000ed04  xor     rax, rsp
0x14000ed07  mov     [rbp+var_8], rax
0x14000ed0b  mov     dword ptr [rbp+var_18], ecx
0x14000ed0e  lea     rax, [rbp+hKey]
0x14000ed12  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000ed19  mov     [rsp+50h+phkResult], rax; phkResult
0x14000ed1e  mov     r9d, 2001Fh; samDesired
0x14000ed24  mov     [rbp+hKey], 0
0x14000ed2c  xor     r8d, r8d; ulOptions
0x14000ed2f  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\UC"...
0x14000ed36  call    cs:__imp_RegOpenKeyExW
0x14000ed3c  test    eax, eax
0x14000ed3e  jnz     short loc_14000EDB7
0x14000ed40  mov     rcx, [rbp+hKey]; hKey
0x14000ed44  lea     ebx, [rax+4]
0x14000ed47  mov     dword ptr [rbp+Data], eax
0x14000ed4a  lea     rdx, aFeaturev2; "FeatureV2"
0x14000ed51  lea     rax, [rbp+cbData]
0x14000ed55  mov     [rbp+cbData], ebx
0x14000ed58  mov     [rsp+50h+lpcbData], rax; lpcbData
0x14000ed5d  xor     r9d, r9d; lpType
0x14000ed60  lea     rax, [rbp+Data]
0x14000ed64  xor     r8d, r8d; lpReserved
0x14000ed67  mov     [rsp+50h+phkResult], rax; lpData
0x14000ed6c  call    cs:__imp_RegQueryValueExW
0x14000ed72  test    eax, eax
0x14000ed74  jnz     short loc_14000ED7E
0x14000ed76  mov     eax, dword ptr [rbp+var_18]
0x14000ed79  cmp     dword ptr [rbp+Data], eax
0x14000ed7c  jmp     short loc_14000ED87
0x14000ed7e  cmp     eax, 2
0x14000ed81  jnz     short loc_14000EDAD
0x14000ed83  cmp     dword ptr [rbp+var_18], 0
0x14000ed87  jz      short loc_14000EDAD
0x14000ed89  mov     rcx, [rbp+hKey]; hKey
0x14000ed8d  lea     rax, [rbp+var_18]
0x14000ed91  mov     dword ptr [rsp+50h+lpcbData], ebx; cbData
0x14000ed95  lea     rdx, aFeaturev2; "FeatureV2"
0x14000ed9c  mov     r9d, ebx; dwType
0x14000ed9f  mov     [rsp+50h+phkResult], rax; lpData
0x14000eda4  xor     r8d, r8d; Reserved
0x14000eda7  call    cs:__imp_RegSetValueExW
0x14000edad  mov     rcx, [rbp+hKey]; hKey
0x14000edb1  call    cs:__imp_RegCloseKey
0x14000edb7  mov     rcx, [rbp+var_8]
0x14000edbb  xor     rcx, rsp; StackCookie
0x14000edbe  call    __security_check_cookie
0x14000edc3  mov     rbx, [rsp+50h+arg_8]
0x14000edc8  add     rsp, 50h
0x14000edcc  pop     rbp
0x14000edcd  retn
```
