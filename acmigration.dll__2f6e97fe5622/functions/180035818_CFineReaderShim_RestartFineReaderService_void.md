# CFineReaderShim::RestartFineReaderService(void)

- ea: `0x180035818`
- end: `0x180035948`
- name: `?RestartFineReaderService@CFineReaderShim@@QEAAKXZ`
- size: `304`
- prototype: `unsigned int __fastcall(CFineReaderShim *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x1800353b0`

## callees

- `0x180001cf0`
- `0x180035818`
- `0x180035950`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800358f6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800358f6`
- `ADVAPI32!RegCloseKey` at `0x180035920`
- `ADVAPI32!RegCloseKey` at `0x180035920`
- `ADVAPI32!RegEnumKeyExW` at `0x1800358df`
- `ADVAPI32!RegEnumKeyExW` at `0x1800358df`
- `ADVAPI32!RegOpenKeyExW` at `0x1800358a1`
- `ADVAPI32!RegOpenKeyExW` at `0x1800358a1`

## string_xrefs

- `0x18003583e`: `ABBYY.Licensing.FineReader.`
- `0x18003585a`: `System\ControlSet001\Services`

## pseudocode

```c
__int64 __fastcall CFineReaderShim::RestartFineReaderService(CFineReaderShim *this)
{
  DWORD restarted; // ebx
  CFineReaderShim *v2; // rcx
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  _OWORD v6[3]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v7; // [rsp+80h] [rbp-80h]
  WCHAR Name[264]; // [rsp+90h] [rbp-70h] BYREF

  v6[0] = *(_OWORD *)L"ABBYY.Licensing.FineReader.";
  hKey = 0;
  cchName = 259;
  v6[1] = *(_OWORD *)L"censing.FineReader.";
  v6[2] = *(_OWORD *)L"FineReader.";
  v7 = *(_QWORD *)L"er.";
  restarted = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\ControlSet001\\Services", 0, 0x20019u, &hKey);
  if ( !restarted )
  {
    while ( 1 )
    {
      cchName = 259;
      Name[0] = 0;
      if ( RegEnumKeyExW(hKey, restarted, Name, &cchName, 0, 0, 0, 0) )
        break;
      if ( !(unsigned int)_o__wcsnicmp(v6, Name) )
      {
        restarted = CFineReaderShim::RestartService(v2, Name);
        goto LABEL_7;
      }
      ++restarted;
    }
    restarted = 2;
  }
LABEL_7:
  if ( hKey )
    RegCloseKey(hKey);
  return restarted;
}

```

## disassembly

```asm
0x180035818  mov     [rsp-8+arg_0], rbx
0x18003581d  push    rbp
0x18003581e  lea     rbp, [rsp-1B0h]
0x180035826  sub     rsp, 2B0h
0x18003582d  mov     rax, cs:__security_cookie
0x180035834  xor     rax, rsp
0x180035837  mov     [rbp+1B0h+var_10], rax
0x18003583e  movups  xmm0, xmmword ptr cs:aAbbyyLicensing; "ABBYY.Licensing.FineReader."
0x180035845  lea     rax, [rsp+2B0h+hKey]
0x18003584a  mov     r9d, 20019h; samDesired
0x180035850  movups  xmm1, xmmword ptr cs:aAbbyyLicensing+10h; "censing.FineReader."
0x180035857  xor     r8d, r8d; ulOptions
0x18003585a  lea     rdx, aSystemControls_3; "System\\ControlSet001\\Services"
0x180035861  movups  [rsp+2B0h+var_260], xmm0
0x180035866  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003586d  mov     [rsp+2B0h+hKey], 0
0x180035876  movups  xmm0, xmmword ptr cs:aAbbyyLicensing+20h; "FineReader."
0x18003587d  mov     [rsp+2B0h+cchName], 103h
0x180035885  movups  [rsp+2B0h+var_250], xmm1
0x18003588a  mov     [rsp+2B0h+phkResult], rax; phkResult
0x18003588f  movsd   xmm1, qword ptr cs:aAbbyyLicensing+30h; "er."
0x180035897  movups  [rsp+2B0h+var_240], xmm0
0x18003589c  movsd   [rbp+1B0h+var_230], xmm1
0x1800358a1  call    cs:__imp_RegOpenKeyExW
0x1800358a7  mov     ebx, eax
0x1800358a9  test    eax, eax
0x1800358ab  jnz     short loc_180035916
0x1800358ad  mov     rcx, [rsp+2B0h+hKey]; hKey
0x1800358b2  lea     r9, [rsp+2B0h+cchName]; lpcchName
0x1800358b7  xor     eax, eax
0x1800358b9  mov     [rsp+2B0h+cchName], 103h
0x1800358c1  mov     [rsp+2B0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1800358c6  lea     r8, [rbp+1B0h+Name]; lpName
0x1800358ca  mov     [rsp+2B0h+lpcchClass], rax; lpcchClass
0x1800358cf  mov     edx, ebx; dwIndex
0x1800358d1  mov     [rsp+2B0h+lpClass], rax; lpClass
0x1800358d6  mov     [rsp+2B0h+phkResult], rax; lpReserved
0x1800358db  mov     [rbp+1B0h+Name], ax
0x1800358df  call    cs:__imp_RegEnumKeyExW
0x1800358e5  test    eax, eax
0x1800358e7  jnz     short loc_180035911
0x1800358e9  lea     r8d, [rax+1Bh]
0x1800358ed  lea     rdx, [rbp+1B0h+Name]
0x1800358f1  lea     rcx, [rsp+2B0h+var_260]
0x1800358f6  call    cs:__imp__o__wcsnicmp
0x1800358fc  test    eax, eax
0x1800358fe  jz      short loc_180035904
0x180035900  inc     ebx
0x180035902  jmp     short loc_1800358AD
0x180035904  lea     rdx, [rbp+1B0h+Name]; unsigned __int16 *
0x180035908  call    ?RestartService@CFineReaderShim@@AEAAKPEBG@Z; CFineReaderShim::RestartService(ushort const *)
0x18003590d  mov     ebx, eax
0x18003590f  jmp     short loc_180035916
0x180035911  mov     ebx, 2
0x180035916  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18003591b  test    rcx, rcx
0x18003591e  jz      short loc_180035926
0x180035920  call    cs:__imp_RegCloseKey
0x180035926  mov     eax, ebx
0x180035928  mov     rcx, [rbp+1B0h+var_10]
0x18003592f  xor     rcx, rsp; StackCookie
0x180035932  call    __security_check_cookie
0x180035937  mov     rbx, [rsp+2B0h+arg_0]
0x18003593f  add     rsp, 2B0h
0x180035946  pop     rbp
0x180035947  retn
```
