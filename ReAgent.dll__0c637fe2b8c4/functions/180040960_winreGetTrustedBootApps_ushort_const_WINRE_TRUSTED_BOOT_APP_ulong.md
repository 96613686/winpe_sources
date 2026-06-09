# winreGetTrustedBootApps(ushort const *,_WINRE_TRUSTED_BOOT_APP * *,ulong *)

- ea: `0x180040960`
- end: `0x180040c20`
- name: `?winreGetTrustedBootApps@@YAKPEBGPEAPEAU_WINRE_TRUSTED_BOOT_APP@@PEAK@Z`
- size: `704`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, struct _WINRE_TRUSTED_BOOT_APP **, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800234f0`

## callees

- `0x1800059fc`
- `0x180040960`
- `0x180040c28`
- `0x18004111c`
- `0x18004d2fc`
- `0x18004d584`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180040adc`
- `KERNEL32!GetLastError` at `0x180040adc`
- `KERNEL32!HeapFree` at `0x180040b82`
- `KERNEL32!HeapFree` at `0x180040b82`
- `KERNEL32!HeapAlloc` at `0x180040ace`
- `KERNEL32!HeapAlloc` at `0x180040ace`
- `KERNEL32!GetProcessHeap` at `0x180040ac0`
- `KERNEL32!GetProcessHeap` at `0x180040b74`
- `KERNEL32!GetProcessHeap` at `0x180040ac0`
- `KERNEL32!GetProcessHeap` at `0x180040b74`
- `ADVAPI32!RegEnumValueW` at `0x180040aa0`
- `ADVAPI32!RegEnumValueW` at `0x180040b4d`
- `ADVAPI32!RegEnumValueW` at `0x180040aa0`
- `ADVAPI32!RegEnumValueW` at `0x180040b4d`
- `ADVAPI32!RegCreateKeyExW` at `0x180040a4d`
- `ADVAPI32!RegCreateKeyExW` at `0x180040a4d`
- `ADVAPI32!RegCloseKey` at `0x180040bb4`
- `ADVAPI32!RegCloseKey` at `0x180040bb4`

## string_xrefs

- `0x1800409be`: `winreGetTrustedBootApps: Failed to enable backup privilege`
- `0x1800409ec`: `winreGetTrustedBootApps: Failed to enable restore privilege`
- `0x180040a5c`: `winreGetTrustedBootApps: Failed to open trusted app list key: 0x%x`
- `0x180040b60`: `winreGetTrustedBootApps: Failed to read app [%u]: 0x%x`

## pseudocode

```c
__int64 __fastcall winreGetTrustedBootApps(unsigned __int16 *a1, WCHAR **a2, unsigned int *a3)
{
  DWORD v3; // esi
  __int64 LastError; // rbx
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // edi
  DWORD i; // edx
  unsigned int v12; // eax
  HANDLE ProcessHeap; // rax
  WCHAR *v14; // r14
  unsigned int v15; // eax
  HANDLE v16; // rax
  int v18; // [rsp+50h] [rbp-B0h] BYREF
  int v19; // [rsp+54h] [rbp-ACh] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cchValueName; // [rsp+68h] [rbp-98h] BYREF
  DWORD v23; // [rsp+6Ch] [rbp-94h] BYREF
  WCHAR ValueName[304]; // [rsp+70h] [rbp-90h] BYREF

  v3 = 0;
  v18 = 0;
  v19 = 0;
  hKey = 0;
  phkResult = 0;
  if ( !(unsigned int)Utils::EnablePrivilege(0x11u, &v18) )
  {
    UnattendLogW(1, L"winreGetTrustedBootApps: Failed to enable backup privilege");
LABEL_3:
    LODWORD(LastError) = 1314;
    goto LABEL_24;
  }
  if ( !(unsigned int)Utils::EnablePrivilege(0x12u, &v19) )
  {
    UnattendLogW(1, L"winreGetTrustedBootApps: Failed to enable restore privilege");
    goto LABEL_3;
  }
  v8 = winreLoadSoftwareHive(a1, &hKey);
  LODWORD(LastError) = v8;
  if ( v8 )
  {
    UnattendLogW(1, L"winreGetTrustedBootApps: Failed to load SOFTWARE hive: 0x%x", v8);
  }
  else
  {
    v9 = RegCreateKeyExW(hKey, L"Microsoft\\RecoveryEnvironment\\TrustedApps", 0, 0, 4u, 0xF003Fu, 0, &phkResult, 0);
    LODWORD(LastError) = v9;
    if ( v9 )
    {
      UnattendLogW(1, L"winreGetTrustedBootApps: Failed to open trusted app list key: 0x%x", v9);
    }
    else
    {
      v10 = 0;
      for ( i = 0; ; i = v10 )
      {
        cchValueName = 302;
        v12 = RegEnumValueW(phkResult, i, ValueName, &cchValueName, 0, 0, 0, 0);
        LODWORD(LastError) = v12;
        if ( v12 )
          break;
        ++v10;
      }
      if ( v12 == 259 )
      {
        ProcessHeap = GetProcessHeap();
        v14 = (WCHAR *)HeapAlloc(ProcessHeap, 0, 636LL * v10);
        if ( v14 )
        {
          LODWORD(LastError) = 0;
          while ( v3 < v10 )
          {
            v23 = 302;
            cchValueName = 32;
            v15 = RegEnumValueW(phkResult, v3, &v14[318 * v3], &v23, 0, 0, (LPBYTE)&v14[318 * v3 + 302], &cchValueName);
            LODWORD(LastError) = v15;
            if ( v15 )
            {
              UnattendLogW(1, L"winreGetTrustedBootApps: Failed to read app [%u]: 0x%x", v3, v15);
              v16 = GetProcessHeap();
              HeapFree(v16, 0, v14);
              goto LABEL_24;
            }
            ++v3;
          }
          *a2 = v14;
          *a3 = v10;
        }
        else
        {
          LastError = GetLastError();
          UnattendLogW(1, L"winreGetTrustedBootApps: Failed to allocate output array: 0x%x", LastError);
        }
      }
      else
      {
        UnattendLogW(1, L"winreGetTrustedBootApps: Failed to count trusted apps: 0x%x", v12);
      }
    }
  }
LABEL_24:
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
  Utils::DisablePrivilege(0x11u, &v18);
  Utils::DisablePrivilege(0x12u, &v19);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180040960  mov     [rsp-8+arg_18], rbx
0x180040965  push    rbp
0x180040966  push    rsi
0x180040967  push    rdi
0x180040968  push    r12
0x18004096a  push    r13
0x18004096c  push    r14
0x18004096e  push    r15
0x180040970  lea     rbp, [rsp-1E0h]
0x180040978  sub     rsp, 2E0h
0x18004097f  mov     rax, cs:__security_cookie
0x180040986  xor     rax, rsp
0x180040989  mov     [rbp+210h+var_40], rax
0x180040990  xor     esi, esi
0x180040992  mov     r12, rdx
0x180040995  mov     r15, rcx
0x180040998  mov     [rsp+310h+var_2C0], esi
0x18004099c  lea     rdx, [rsp+310h+var_2C0]; int *
0x1800409a1  mov     [rsp+310h+var_2BC], esi
0x1800409a5  mov     r13, r8
0x1800409a8  mov     [rsp+310h+hKey], rsi
0x1800409ad  lea     ecx, [rsi+11h]; unsigned int
0x1800409b0  mov     [rsp+310h+var_2B8], rsi
0x1800409b5  call    ?EnablePrivilege@Utils@@SAHKPEAH@Z; Utils::EnablePrivilege(ulong,int *)
0x1800409ba  test    eax, eax
0x1800409bc  jnz     short loc_1800409D9
0x1800409be  lea     rdx, aWinregettruste_1; "winreGetTrustedBootApps: Failed to enab"...
0x1800409c5  mov     ecx, 1
0x1800409ca  call    UnattendLogW
0x1800409cf  mov     ebx, 522h
0x1800409d4  jmp     loc_180040BAA
0x1800409d9  lea     rdx, [rsp+310h+var_2BC]; int *
0x1800409de  mov     ecx, 12h; unsigned int
0x1800409e3  call    ?EnablePrivilege@Utils@@SAHKPEAH@Z; Utils::EnablePrivilege(ulong,int *)
0x1800409e8  test    eax, eax
0x1800409ea  jnz     short loc_1800409F5
0x1800409ec  lea     rdx, aWinregettruste_0; "winreGetTrustedBootApps: Failed to enab"...
0x1800409f3  jmp     short loc_1800409C5
0x1800409f5  lea     rdx, [rsp+310h+hKey]; phkResult
0x1800409fa  mov     rcx, r15; unsigned __int16 *
0x1800409fd  call    winreLoadSoftwareHive
0x180040a02  mov     ebx, eax
0x180040a04  test    eax, eax
0x180040a06  jz      short loc_180040A17
0x180040a08  mov     r8d, eax
0x180040a0b  lea     rdx, aWinregettruste_2; "winreGetTrustedBootApps: Failed to load"...
0x180040a12  jmp     loc_180040BA0
0x180040a17  mov     rcx, [rsp+310h+hKey]; hKey
0x180040a1c  lea     rax, [rsp+310h+var_2B8]
0x180040a21  mov     [rsp+310h+lpdwDisposition], rsi; lpdwDisposition
0x180040a26  lea     rdx, aMicrosoftRecov; "Microsoft\\RecoveryEnvironment\\Trusted"...
0x180040a2d  mov     [rsp+310h+phkResult], rax; phkResult
0x180040a32  xor     r9d, r9d; lpClass
0x180040a35  mov     [rsp+310h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180040a3a  xor     r8d, r8d; Reserved
0x180040a3d  mov     [rsp+310h+samDesired], 0F003Fh; samDesired
0x180040a45  mov     [rsp+310h+dwOptions], 4; dwOptions
0x180040a4d  call    cs:__imp_RegCreateKeyExW
0x180040a53  mov     ebx, eax
0x180040a55  test    eax, eax
0x180040a57  jz      short loc_180040A68
0x180040a59  mov     r8d, eax
0x180040a5c  lea     rdx, aWinregettruste_6; "winreGetTrustedBootApps: Failed to open"...
0x180040a63  jmp     loc_180040BA0
0x180040a68  mov     edi, esi
0x180040a6a  mov     r14d, 12Eh
0x180040a70  xor     edx, edx
0x180040a72  jmp     short loc_180040A78
0x180040a74  inc     edi
0x180040a76  mov     edx, edi; dwIndex
0x180040a78  mov     rcx, [rsp+310h+var_2B8]; hKey
0x180040a7d  lea     r9, [rsp+310h+cchValueName]; lpcchValueName
0x180040a82  mov     [rsp+310h+phkResult], rsi; lpcbData
0x180040a87  lea     r8, [rsp+310h+ValueName]; lpValueName
0x180040a8c  mov     [rsp+310h+lpSecurityAttributes], rsi; lpData
0x180040a91  mov     qword ptr [rsp+310h+samDesired], rsi; lpType
0x180040a96  mov     qword ptr [rsp+310h+dwOptions], rsi; lpReserved
0x180040a9b  mov     [rsp+310h+cchValueName], r14d
0x180040aa0  call    cs:__imp_RegEnumValueW
0x180040aa6  mov     ebx, eax
0x180040aa8  test    eax, eax
0x180040aaa  jz      short loc_180040A74
0x180040aac  cmp     eax, 103h
0x180040ab1  jnz     loc_180040B96
0x180040ab7  mov     eax, edi
0x180040ab9  imul    rbx, rax, 27Ch
0x180040ac0  call    cs:__imp_GetProcessHeap
0x180040ac6  mov     r8, rbx; dwBytes
0x180040ac9  xor     edx, edx; dwFlags
0x180040acb  mov     rcx, rax; hHeap
0x180040ace  call    cs:__imp_HeapAlloc
0x180040ad4  mov     r14, rax
0x180040ad7  test    rax, rax
0x180040ada  jnz     short loc_180040AF3
0x180040adc  call    cs:__imp_GetLastError
0x180040ae2  mov     ebx, eax
0x180040ae4  lea     rdx, aWinregettruste_3; "winreGetTrustedBootApps: Failed to allo"...
0x180040aeb  mov     r8d, eax
0x180040aee  jmp     loc_180040BA0
0x180040af3  mov     ebx, esi
0x180040af5  cmp     esi, edi
0x180040af7  jnb     loc_180040B8A
0x180040afd  mov     eax, esi
0x180040aff  lea     rcx, [rsp+310h+cchValueName]
0x180040b04  mov     [rsp+310h+phkResult], rcx; lpcbData
0x180040b09  lea     r9, [rsp+310h+var_2A4]; lpcchValueName
0x180040b0e  mov     rcx, [rsp+310h+var_2B8]; hKey
0x180040b13  mov     edx, esi; dwIndex
0x180040b15  imul    r8, rax, 27Ch
0x180040b1c  mov     [rsp+310h+var_2A4], 12Eh
0x180040b24  add     r8, r14; lpValueName
0x180040b27  mov     [rsp+310h+cchValueName], 20h ; ' '
0x180040b2f  lea     rax, [r8+25Ch]
0x180040b36  mov     [rsp+310h+lpSecurityAttributes], rax; lpData
0x180040b3b  mov     qword ptr [rsp+310h+samDesired], 0; lpType
0x180040b44  mov     qword ptr [rsp+310h+dwOptions], 0; lpReserved
0x180040b4d  call    cs:__imp_RegEnumValueW
0x180040b53  mov     ebx, eax
0x180040b55  test    eax, eax
0x180040b57  jnz     short loc_180040B5D
0x180040b59  inc     esi
0x180040b5b  jmp     short loc_180040AF5
0x180040b5d  mov     r9d, eax
0x180040b60  lea     rdx, aWinregettruste_4; "winreGetTrustedBootApps: Failed to read"...
0x180040b67  mov     r8d, esi
0x180040b6a  mov     ecx, 1
0x180040b6f  call    UnattendLogW
0x180040b74  call    cs:__imp_GetProcessHeap
0x180040b7a  mov     r8, r14; lpMem
0x180040b7d  xor     edx, edx; dwFlags
0x180040b7f  mov     rcx, rax; hHeap
0x180040b82  call    cs:__imp_HeapFree
0x180040b88  jmp     short loc_180040B92
0x180040b8a  mov     [r12], r14
0x180040b8e  mov     [r13+0], edi
0x180040b92  xor     esi, esi
0x180040b94  jmp     short loc_180040BAA
0x180040b96  mov     r8d, ebx
0x180040b99  lea     rdx, aWinregettruste_5; "winreGetTrustedBootApps: Failed to coun"...
0x180040ba0  mov     ecx, 1
0x180040ba5  call    UnattendLogW
0x180040baa  mov     rcx, [rsp+310h+var_2B8]; hKey
0x180040baf  test    rcx, rcx
0x180040bb2  jz      short loc_180040BBF
0x180040bb4  call    cs:__imp_RegCloseKey
0x180040bba  mov     [rsp+310h+var_2B8], rsi
0x180040bbf  mov     rdx, [rsp+310h+hKey]
0x180040bc4  test    rdx, rdx
0x180040bc7  jz      short loc_180040BD6
0x180040bc9  mov     rcx, r15
0x180040bcc  call    winreUnloadSoftwareHive
0x180040bd1  mov     [rsp+310h+hKey], rsi
0x180040bd6  lea     rdx, [rsp+310h+var_2C0]; int *
0x180040bdb  mov     ecx, 11h; unsigned int
0x180040be0  call    ?DisablePrivilege@Utils@@SAHKPEAH@Z; Utils::DisablePrivilege(ulong,int *)
0x180040be5  lea     rdx, [rsp+310h+var_2BC]; int *
0x180040bea  mov     ecx, 12h; unsigned int
0x180040bef  call    ?DisablePrivilege@Utils@@SAHKPEAH@Z; Utils::DisablePrivilege(ulong,int *)
0x180040bf4  mov     eax, ebx
0x180040bf6  mov     rcx, [rbp+210h+var_40]
0x180040bfd  xor     rcx, rsp; StackCookie
0x180040c00  call    __security_check_cookie
0x180040c05  mov     rbx, [rsp+310h+arg_18]
0x180040c0d  add     rsp, 2E0h
0x180040c14  pop     r15
0x180040c16  pop     r14
0x180040c18  pop     r13
0x180040c1a  pop     r12
0x180040c1c  pop     rdi
0x180040c1d  pop     rsi
0x180040c1e  pop     rbp
0x180040c1f  retn
```
