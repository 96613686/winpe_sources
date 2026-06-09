# winreAddTrustedBootApp(ushort const *,ushort const *,uchar *)

- ea: `0x1800407ac`
- end: `0x180040958`
- name: `?winreAddTrustedBootApp@@YAKPEBG0PEAE@Z`
- size: `428`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, LPCWSTR lpValueName, BYTE *lpData)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800207b0`

## callees

- `0x1800059fc`
- `0x1800407ac`
- `0x180040c28`
- `0x18004111c`
- `0x18004d2fc`
- `0x18004d584`
- `0x18005cf30`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x1800408d0`
- `ADVAPI32!RegSetValueExW` at `0x1800408d0`
- `ADVAPI32!RegCreateKeyExW` at `0x18004089e`
- `ADVAPI32!RegCreateKeyExW` at `0x18004089e`
- `ADVAPI32!RegCloseKey` at `0x1800408fc`
- `ADVAPI32!RegCloseKey` at `0x1800408fc`

## string_xrefs

- `0x180040801`: `winreAddTrustedBootApp: Failed to enable backup privilege`
- `0x18004082e`: `winreAddTrustedBootApp: Failed to enable restore privilege`
- `0x180040849`: `winreAddTrustedBootApp: Failed to load SOFTWARE hive: 0x%x`
- `0x1800408aa`: `winreAddTrustedBootApp: Failed to open trusted app list key: 0x%x`
- `0x1800408df`: `winreAddTrustedBootApp: Failed to write hash for app [%s]: 0x%x`

## pseudocode

```c
__int64 __fastcall winreAddTrustedBootApp(unsigned __int16 *a1, LPCWSTR lpValueName, BYTE *lpData)
{
  unsigned int v6; // ebx
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  int v11; // [rsp+50h] [rbp-20h] BYREF
  int v12; // [rsp+54h] [rbp-1Ch] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-10h] BYREF

  v11 = 0;
  v12 = 0;
  hKey = 0;
  phkResult = 0;
  if ( !(unsigned int)Utils::EnablePrivilege(0x11u, &v11) )
  {
    UnattendLogW(1, L"winreAddTrustedBootApp: Failed to enable backup privilege");
LABEL_3:
    v6 = 1314;
    goto LABEL_13;
  }
  if ( !(unsigned int)Utils::EnablePrivilege(0x12u, &v12) )
  {
    UnattendLogW(1, L"winreAddTrustedBootApp: Failed to enable restore privilege");
    goto LABEL_3;
  }
  v7 = winreLoadSoftwareHive(a1, &hKey);
  v6 = v7;
  if ( v7 )
  {
    UnattendLogW(1, L"winreAddTrustedBootApp: Failed to load SOFTWARE hive: 0x%x", v7);
  }
  else
  {
    v8 = RegCreateKeyExW(hKey, L"Microsoft\\RecoveryEnvironment\\TrustedApps", 0, 0, 4u, 0xF003Fu, 0, &phkResult, 0);
    v6 = v8;
    if ( v8 )
    {
      UnattendLogW(1, L"winreAddTrustedBootApp: Failed to open trusted app list key: 0x%x", v8);
    }
    else
    {
      v9 = RegSetValueExW(phkResult, lpValueName, 0, 3u, lpData, 0x20u);
      v6 = v9;
      if ( v9 )
        UnattendLogW(1, L"winreAddTrustedBootApp: Failed to write hash for app [%s]: 0x%x", lpValueName, v9);
    }
  }
LABEL_13:
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( hKey )
  {
    winreUnloadSoftwareHive(a1);
    hKey = 0;
  }
  Utils::DisablePrivilege(0x11u, &v11);
  Utils::DisablePrivilege(0x12u, &v12);
  return v6;
}

```

## disassembly

```asm
0x1800407ac  push    rbp
0x1800407ae  push    rbx
0x1800407af  push    rsi
0x1800407b0  push    rdi
0x1800407b1  push    r14
0x1800407b3  mov     rbp, rsp
0x1800407b6  sub     rsp, 70h
0x1800407ba  mov     rax, cs:__security_cookie
0x1800407c1  xor     rax, rsp
0x1800407c4  mov     [rbp+var_8], rax
0x1800407c8  mov     rdi, rdx
0x1800407cb  mov     [rbp+var_20], 0
0x1800407d2  mov     rsi, rcx
0x1800407d5  mov     [rbp+var_1C], 0
0x1800407dc  lea     rdx, [rbp+var_20]; int *
0x1800407e0  mov     [rbp+hKey], 0
0x1800407e8  mov     ecx, 11h; unsigned int
0x1800407ed  mov     [rbp+var_18], 0
0x1800407f5  mov     r14, r8
0x1800407f8  call    ?EnablePrivilege@Utils@@SAHKPEAH@Z; Utils::EnablePrivilege(ulong,int *)
0x1800407fd  test    eax, eax
0x1800407ff  jnz     short loc_18004081C
0x180040801  lea     rdx, aWinreaddtruste_1; "winreAddTrustedBootApp: Failed to enabl"...
0x180040808  mov     ecx, 1
0x18004080d  call    UnattendLogW
0x180040812  mov     ebx, 522h
0x180040817  jmp     loc_1800408F3
0x18004081c  lea     rdx, [rbp+var_1C]; int *
0x180040820  mov     ecx, 12h; unsigned int
0x180040825  call    ?EnablePrivilege@Utils@@SAHKPEAH@Z; Utils::EnablePrivilege(ulong,int *)
0x18004082a  test    eax, eax
0x18004082c  jnz     short loc_180040837
0x18004082e  lea     rdx, aWinreaddtruste_0; "winreAddTrustedBootApp: Failed to enabl"...
0x180040835  jmp     short loc_180040808
0x180040837  lea     rdx, [rbp+hKey]; phkResult
0x18004083b  mov     rcx, rsi; unsigned __int16 *
0x18004083e  call    winreLoadSoftwareHive
0x180040843  mov     ebx, eax
0x180040845  test    eax, eax
0x180040847  jz      short loc_180040862
0x180040849  lea     rdx, aWinreaddtruste_2; "winreAddTrustedBootApp: Failed to load "...
0x180040850  mov     r8d, eax
0x180040853  mov     ecx, 1
0x180040858  call    UnattendLogW
0x18004085d  jmp     loc_1800408F3
0x180040862  mov     rcx, [rbp+hKey]; hKey
0x180040866  lea     rax, [rbp+var_18]
0x18004086a  mov     [rsp+70h+lpdwDisposition], 0; lpdwDisposition
0x180040873  lea     rdx, aMicrosoftRecov; "Microsoft\\RecoveryEnvironment\\Trusted"...
0x18004087a  mov     [rsp+70h+phkResult], rax; phkResult
0x18004087f  xor     r9d, r9d; lpClass
0x180040882  mov     [rsp+70h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18004088b  xor     r8d, r8d; Reserved
0x18004088e  mov     [rsp+70h+samDesired], 0F003Fh; samDesired
0x180040896  mov     [rsp+70h+dwOptions], 4; dwOptions
0x18004089e  call    cs:__imp_RegCreateKeyExW
0x1800408a4  mov     ebx, eax
0x1800408a6  test    eax, eax
0x1800408a8  jz      short loc_1800408B3
0x1800408aa  lea     rdx, aWinreaddtruste_3; "winreAddTrustedBootApp: Failed to open "...
0x1800408b1  jmp     short loc_180040850
0x1800408b3  mov     rcx, [rbp+var_18]; hKey
0x1800408b7  mov     r9d, 3; dwType
0x1800408bd  mov     [rsp+70h+samDesired], 20h ; ' '; cbData
0x1800408c5  xor     r8d, r8d; Reserved
0x1800408c8  mov     rdx, rdi; lpValueName
0x1800408cb  mov     qword ptr [rsp+70h+dwOptions], r14; lpData
0x1800408d0  call    cs:__imp_RegSetValueExW
0x1800408d6  mov     ebx, eax
0x1800408d8  test    eax, eax
0x1800408da  jz      short loc_1800408F3
0x1800408dc  mov     r9d, eax
0x1800408df  lea     rdx, aWinreaddtruste_4; "winreAddTrustedBootApp: Failed to write"...
0x1800408e6  mov     r8, rdi
0x1800408e9  mov     ecx, 1
0x1800408ee  call    UnattendLogW
0x1800408f3  mov     rcx, [rbp+var_18]; hKey
0x1800408f7  test    rcx, rcx
0x1800408fa  jz      short loc_18004090A
0x1800408fc  call    cs:__imp_RegCloseKey
0x180040902  mov     [rbp+var_18], 0
0x18004090a  mov     rdx, [rbp+hKey]
0x18004090e  test    rdx, rdx
0x180040911  jz      short loc_180040923
0x180040913  mov     rcx, rsi
0x180040916  call    winreUnloadSoftwareHive
0x18004091b  mov     [rbp+hKey], 0
0x180040923  lea     rdx, [rbp+var_20]; int *
0x180040927  mov     ecx, 11h; unsigned int
0x18004092c  call    ?DisablePrivilege@Utils@@SAHKPEAH@Z; Utils::DisablePrivilege(ulong,int *)
0x180040931  lea     rdx, [rbp+var_1C]; int *
0x180040935  mov     ecx, 12h; unsigned int
0x18004093a  call    ?DisablePrivilege@Utils@@SAHKPEAH@Z; Utils::DisablePrivilege(ulong,int *)
0x18004093f  mov     eax, ebx
0x180040941  mov     rcx, [rbp+var_8]
0x180040945  xor     rcx, rsp; StackCookie
0x180040948  call    __security_check_cookie
0x18004094d  add     rsp, 70h
0x180040951  pop     r14
0x180040953  pop     rdi
0x180040954  pop     rsi
0x180040955  pop     rbx
0x180040956  pop     rbp
0x180040957  retn
```
