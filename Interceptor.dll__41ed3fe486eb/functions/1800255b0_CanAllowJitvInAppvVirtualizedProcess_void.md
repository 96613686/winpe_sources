# CanAllowJitvInAppvVirtualizedProcess(void)

- ea: `0x1800255b0`
- end: `0x1800256e0`
- name: `?CanAllowJitvInAppvVirtualizedProcess@@YA_NXZ`
- size: `304`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800256e0`

## callees

- `0x1800255b0`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x180025645`
- `KERNEL32!OutputDebugStringW` at `0x180025652`
- `KERNEL32!OutputDebugStringW` at `0x180025661`
- `KERNEL32!OutputDebugStringW` at `0x18002566e`
- `KERNEL32!OutputDebugStringW` at `0x180025684`
- `KERNEL32!OutputDebugStringW` at `0x180025691`
- `KERNEL32!OutputDebugStringW` at `0x18002569e`
- `KERNEL32!OutputDebugStringW` at `0x1800256b8`
- `KERNEL32!OutputDebugStringW` at `0x1800256c5`
- `KERNEL32!OutputDebugStringW` at `0x1800256d2`
- `KERNEL32!OutputDebugStringW` at `0x180025645`
- `KERNEL32!OutputDebugStringW` at `0x180025652`
- `KERNEL32!OutputDebugStringW` at `0x180025661`
- `KERNEL32!OutputDebugStringW` at `0x18002566e`
- `KERNEL32!OutputDebugStringW` at `0x180025684`
- `KERNEL32!OutputDebugStringW` at `0x180025691`
- `KERNEL32!OutputDebugStringW` at `0x18002569e`
- `KERNEL32!OutputDebugStringW` at `0x1800256b8`
- `KERNEL32!OutputDebugStringW` at `0x1800256c5`
- `KERNEL32!OutputDebugStringW` at `0x1800256d2`
- `ADVAPI32!RegCloseKey` at `0x1800256a9`
- `ADVAPI32!RegCloseKey` at `0x1800256a9`
- `ADVAPI32!RegOpenKeyExW` at `0x1800255e2`
- `ADVAPI32!RegOpenKeyExW` at `0x1800255e2`
- `ADVAPI32!RegQueryValueExW` at `0x180025620`
- `ADVAPI32!RegQueryValueExW` at `0x180025620`

## string_xrefs

- `0x180025635`: `Registry override `
- `0x18002567d`: `Registry override `
- `0x1800256b1`: `Registry override key `

## pseudocode

```c
bool CanAllowJitvInAppvVirtualizedProcess(void)
{
  bool v0; // bl
  const WCHAR *v1; // rcx
  DWORD cbData; // [rsp+40h] [rbp+8h] BYREF
  DWORD Type; // [rsp+48h] [rbp+10h] BYREF
  int Data; // [rsp+50h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+20h] BYREF

  hKey = 0;
  v0 = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\ClickToRun\\OverRide", 0, 0x101u, &hKey) )
  {
    OutputDebugStringW(L"Registry override key ");
    OutputDebugStringW(L"Software\\Microsoft\\ClickToRun\\OverRide");
    OutputDebugStringW(L" does not exist\n");
  }
  else
  {
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"AllowJitvInAppvVirtualizedProcess", 0, &Type, (LPBYTE)&Data, &cbData) || Type != 4 )
    {
      OutputDebugStringW(L"Registry override ");
      OutputDebugStringW(L"AllowJitvInAppvVirtualizedProcess");
      v1 = L" not found\n";
    }
    else
    {
      v0 = Data != 0;
      if ( Data )
      {
        OutputDebugStringW(L"Registry override ");
        OutputDebugStringW(L"AllowJitvInAppvVirtualizedProcess");
        v1 = L" is enabled.  C2R JitV will run in AppV-virtualized processes.\n";
      }
      else
      {
        OutputDebugStringW(L"Registry override ");
        OutputDebugStringW(L"AllowJitvInAppvVirtualizedProcess");
        v1 = L" is disabled.  C2R JitV will NOT run in AppV-virtualized processes.\n";
      }
    }
    OutputDebugStringW(v1);
    RegCloseKey(hKey);
  }
  return v0;
}

```

## disassembly

```asm
0x1800255b0  push    rbx
0x1800255b2  sub     rsp, 30h
0x1800255b6  lea     rax, [rsp+38h+hKey]
0x1800255bb  mov     [rsp+38h+hKey], 0
0x1800255c4  mov     r9d, 101h; samDesired
0x1800255ca  mov     [rsp+38h+phkResult], rax; phkResult
0x1800255cf  xor     r8d, r8d; ulOptions
0x1800255d2  lea     rdx, ?C2R_OVERRIDE_PATH@@3QB_WB; "Software\\Microsoft\\ClickToRun\\OverRi"...
0x1800255d9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800255e0  xor     bl, bl
0x1800255e2  call    cs:__imp_RegOpenKeyExW
0x1800255e8  test    eax, eax
0x1800255ea  jnz     loc_1800256B1
0x1800255f0  mov     rcx, [rsp+38h+hKey]; hKey
0x1800255f5  lea     rax, [rsp+38h+cbData]
0x1800255fa  mov     [rsp+38h+lpcbData], rax; lpcbData
0x1800255ff  lea     r9, [rsp+38h+Type]; lpType
0x180025604  lea     rax, [rsp+38h+Data]
0x180025609  mov     [rsp+38h+cbData], 4
0x180025611  xor     r8d, r8d; lpReserved
0x180025614  mov     [rsp+38h+phkResult], rax; lpData
0x180025619  lea     rdx, ?C2R_OVERRIDE_ALLOW_JITV_APPV@@3QB_WB; "AllowJitvInAppvVirtualizedProcess"
0x180025620  call    cs:__imp_RegQueryValueExW
0x180025626  test    eax, eax
0x180025628  jnz     short loc_18002567D
0x18002562a  cmp     [rsp+38h+Type], 4
0x18002562f  jnz     short loc_18002567D
0x180025631  mov     eax, [rsp+38h+Data]
0x180025635  lea     rcx, OutputString; "Registry override "
0x18002563c  test    eax, eax
0x18002563e  setnz   bl
0x180025641  test    eax, eax
0x180025643  jz      short loc_180025661
0x180025645  call    cs:__imp_OutputDebugStringW
0x18002564b  lea     rcx, ?C2R_OVERRIDE_ALLOW_JITV_APPV@@3QB_WB; "AllowJitvInAppvVirtualizedProcess"
0x180025652  call    cs:__imp_OutputDebugStringW
0x180025658  lea     rcx, aIsEnabledC2rJi; " is enabled.  C2R JitV will run in AppV"...
0x18002565f  jmp     short loc_18002569E
0x180025661  call    cs:__imp_OutputDebugStringW
0x180025667  lea     rcx, ?C2R_OVERRIDE_ALLOW_JITV_APPV@@3QB_WB; "AllowJitvInAppvVirtualizedProcess"
0x18002566e  call    cs:__imp_OutputDebugStringW
0x180025674  lea     rcx, aIsDisabledC2rJ; " is disabled.  C2R JitV will NOT run in"...
0x18002567b  jmp     short loc_18002569E
0x18002567d  lea     rcx, OutputString; "Registry override "
0x180025684  call    cs:__imp_OutputDebugStringW
0x18002568a  lea     rcx, ?C2R_OVERRIDE_ALLOW_JITV_APPV@@3QB_WB; "AllowJitvInAppvVirtualizedProcess"
0x180025691  call    cs:__imp_OutputDebugStringW
0x180025697  lea     rcx, aNotFound; " not found\n"
0x18002569e  call    cs:__imp_OutputDebugStringW
0x1800256a4  mov     rcx, [rsp+38h+hKey]; hKey
0x1800256a9  call    cs:__imp_RegCloseKey
0x1800256af  jmp     short loc_1800256D8
0x1800256b1  lea     rcx, aRegistryOverri_0; "Registry override key "
0x1800256b8  call    cs:__imp_OutputDebugStringW
0x1800256be  lea     rcx, ?C2R_OVERRIDE_PATH@@3QB_WB; "Software\\Microsoft\\ClickToRun\\OverRi"...
0x1800256c5  call    cs:__imp_OutputDebugStringW
0x1800256cb  lea     rcx, aDoesNotExist; " does not exist\n"
0x1800256d2  call    cs:__imp_OutputDebugStringW
0x1800256d8  mov     al, bl
0x1800256da  add     rsp, 30h
0x1800256de  pop     rbx
0x1800256df  retn
```
