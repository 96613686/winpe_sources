# CDiskProtection::s_GetDelayedUninstall(int *)

- ea: `0x140011310`
- end: `0x14001152b`
- name: `?s_GetDelayedUninstall@CDiskProtection@@SAJPEAH@Z`
- size: `539`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x140007fd0`

## callees

- `0x140011310`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14001150f`
- `ADVAPI32!RegCloseKey` at `0x14001150f`
- `ADVAPI32!RegCreateKeyExW` at `0x140011382`
- `ADVAPI32!RegCreateKeyExW` at `0x140011382`
- `ADVAPI32!RegQueryValueExW` at `0x140011460`
- `ADVAPI32!RegQueryValueExW` at `0x140011460`
- `KERNEL32!IsDebuggerPresent` at `0x1400113d5`
- `KERNEL32!IsDebuggerPresent` at `0x1400114e0`
- `KERNEL32!IsDebuggerPresent` at `0x1400113d5`
- `KERNEL32!IsDebuggerPresent` at `0x1400114e0`

## string_xrefs

- `0x1400113a8`: `CDiskProtection::s_GetDelayedUninstall`
- `0x1400114af`: `CDiskProtection::s_GetDelayedUninstall`
- `0x140011454`: `DelayedUninstall`
- `0x140011335`: `System\CurrentControlSet\Services\WMS\Parameters\`

## pseudocode

```c
__int64 __fastcall CDiskProtection::s_GetDelayedUninstall(int *a1)
{
  LSTATUS v2; // eax
  unsigned int v3; // ebx
  const unsigned __int16 *v4; // r13
  __int64 v5; // r9
  __int64 v6; // r8
  LSTATUS v7; // eax
  __int64 v9; // [rsp+30h] [rbp-30h]
  __int64 v10; // [rsp+38h] [rbp-28h]
  HKEY hKey; // [rsp+50h] [rbp-10h] BYREF
  DWORD Type; // [rsp+98h] [rbp+38h] BYREF
  int Data; // [rsp+A0h] [rbp+40h] BYREF
  DWORD cbData; // [rsp+A8h] [rbp+48h] BYREF

  hKey = 0;
  Data = 0;
  Type = 0;
  cbData = 4;
  v2 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\WMS\\Parameters\\",
         0,
         0,
         0,
         1u,
         0,
         &hKey,
         0);
  v3 = v2;
  if ( v2 )
  {
    if ( v2 > 0 )
      v3 = (unsigned __int16)v2 | 0x80070000;
    v4 = L"err == 0L";
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
      0x6A9u,
      L"CDiskProtection::s_GetDelayedUninstall",
      L"CBRAEx",
      L"err == 0L",
      v3);
    if ( IsDebuggerPresent() )
    {
      v5 = 1705;
LABEL_6:
      LODWORD(v10) = v3;
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
        v5,
        L"CDiskProtection::s_GetDelayedUninstall",
        L"CBRAEx",
        v4,
        v10);
      goto LABEL_23;
    }
    v6 = 1705;
LABEL_8:
    LODWORD(v9) = v3;
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
      v6,
      L"CDiskProtection::s_GetDelayedUninstall",
      L"CBRAEx",
      v4,
      v9);
    goto LABEL_23;
  }
  v7 = RegQueryValueExW(hKey, L"DelayedUninstall", 0, &Type, (LPBYTE)&Data, &cbData);
  v3 = v7;
  if ( v7 == 2 )
  {
    v3 = 0;
  }
  else if ( v7 )
  {
    if ( v7 > 0 )
      v3 = (unsigned __int16)v7 | 0x80070000;
  }
  else if ( Type == 4 )
  {
    v3 = 0;
    if ( Data )
    {
      if ( Data != 1 )
      {
        v3 = -2147418113;
        v4 = L"0";
        LOGASSERTHR(
          L"termsrv\\wms\\src\\devices\\wmssvc\\diskprotection.cpp",
          0x6C0u,
          L"CDiskProtection::s_GetDelayedUninstall",
          L"CBRAEx",
          L"0",
          -2147418113);
        if ( IsDebuggerPresent() )
        {
          v5 = 1728;
          goto LABEL_6;
        }
        v6 = 1728;
        goto LABEL_8;
      }
      *a1 = 1;
    }
    else
    {
      *a1 = 0;
    }
  }
  else
  {
    v3 = -2147467259;
  }
LABEL_23:
  if ( hKey )
    RegCloseKey(hKey);
  return v3;
}

```

## disassembly

```asm
0x140011310  mov     r11, rsp
0x140011313  mov     [r11+8], rbx
0x140011317  push    rbp
0x140011318  push    rsi
0x140011319  push    rdi
0x14001131a  push    r13
0x14001131c  push    r14
0x14001131e  mov     rbp, rsp
0x140011321  sub     rsp, 60h
0x140011325  mov     qword ptr [r11-48h], 0
0x14001132d  lea     rax, [rbp+hKey]
0x140011331  mov     [r11-50h], rax
0x140011335  lea     rdx, ?s_szServiceParametersKey@CDiskProtection@@1QBGB; "System\\CurrentControlSet\\Services\\WM"...
0x14001133c  mov     qword ptr [r11-58h], 0
0x140011344  mov     rdi, rcx
0x140011347  mov     esi, 1
0x14001134c  mov     [rbp+hKey], 0
0x140011354  mov     [rsp+60h+samDesired], esi; samDesired
0x140011358  xor     r9d, r9d; lpClass
0x14001135b  xor     r8d, r8d; Reserved
0x14001135e  mov     [rsp+60h+dwOptions], 0; dwOptions
0x140011366  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14001136d  mov     [rbp+Data], 0
0x140011374  mov     [rbp+Type], 0
0x14001137b  mov     [rbp+cbData], 4
0x140011382  call    cs:__imp_RegCreateKeyExW
0x140011388  mov     ebx, eax
0x14001138a  test    eax, eax
0x14001138c  jz      loc_14001143C
0x140011392  jle     short loc_14001139D
0x140011394  movzx   ebx, ax
0x140011397  or      ebx, 80070000h
0x14001139d  lea     r14, aCbraex; "CBRAEx"
0x1400113a4  mov     [rsp+60h+samDesired], ebx; int
0x1400113a8  lea     rsi, aCdiskprotectio_149; "CDiskProtection::s_GetDelayedUninstall"
0x1400113af  mov     r9, r14; unsigned __int16 *
0x1400113b2  lea     rdi, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x1400113b9  mov     r8, rsi; unsigned __int16 *
0x1400113bc  lea     r13, aErr0l; "err == 0L"
0x1400113c3  mov     rcx, rdi; unsigned __int16 *
0x1400113c6  mov     edx, 6A9h; unsigned int
0x1400113cb  mov     qword ptr [rsp+60h+dwOptions], r13; unsigned __int16 *
0x1400113d0  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400113d5  call    cs:__imp_IsDebuggerPresent
0x1400113db  test    eax, eax
0x1400113dd  jz      short loc_140011411
0x1400113df  mov     r9d, 6A9h
0x1400113e5  mov     dword ptr [rsp+60h+var_28], ebx
0x1400113e9  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x1400113f0  mov     [rsp+60h+var_30], r13
0x1400113f5  mov     r8, rdi
0x1400113f8  mov     qword ptr [rsp+60h+samDesired], r14
0x1400113fd  mov     ecx, 2; unsigned __int8
0x140011402  mov     qword ptr [rsp+60h+dwOptions], rsi
0x140011407  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14001140c  jmp     loc_140011506
0x140011411  mov     r8d, 6A9h
0x140011417  mov     dword ptr [rsp+60h+var_30], ebx
0x14001141b  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140011422  mov     qword ptr [rsp+60h+samDesired], r13
0x140011427  mov     r9, rsi
0x14001142a  mov     rdx, rdi
0x14001142d  mov     qword ptr [rsp+60h+dwOptions], r14
0x140011432  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140011437  jmp     loc_140011506
0x14001143c  mov     rcx, [rbp+hKey]; hKey
0x140011440  lea     rax, [rbp+cbData]
0x140011444  mov     qword ptr [rsp+60h+samDesired], rax; lpcbData
0x140011449  lea     r9, [rbp+Type]; lpType
0x14001144d  lea     rax, [rbp+Data]
0x140011451  xor     r8d, r8d; lpReserved
0x140011454  lea     rdx, ?s_szDelayedUninstallRegValueName@CDiskProtection@@1QBGB; "DelayedUninstall"
0x14001145b  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x140011460  call    cs:__imp_RegQueryValueExW
0x140011466  mov     ebx, eax
0x140011468  cmp     eax, 2
0x14001146b  jnz     short loc_140011474
0x14001146d  xor     ebx, ebx
0x14001146f  jmp     loc_140011506
0x140011474  test    eax, eax
0x140011476  jz      short loc_140011489
0x140011478  jle     loc_140011506
0x14001147e  movzx   ebx, ax
0x140011481  or      ebx, 80070000h
0x140011487  jmp     short loc_140011506
0x140011489  cmp     [rbp+Type], 4
0x14001148d  jz      short loc_140011496
0x14001148f  mov     ebx, 80004005h
0x140011494  jmp     short loc_140011506
0x140011496  mov     eax, [rbp+Data]
0x140011499  xor     ebx, ebx
0x14001149b  test    eax, eax
0x14001149d  jz      short loc_140011504
0x14001149f  cmp     eax, esi
0x1400114a1  jz      short loc_140011500
0x1400114a3  mov     ebx, 8000FFFFh
0x1400114a8  lea     r14, aCbraex; "CBRAEx"
0x1400114af  lea     rsi, aCdiskprotectio_149; "CDiskProtection::s_GetDelayedUninstall"
0x1400114b6  mov     [rsp+60h+samDesired], ebx; int
0x1400114ba  lea     rdi, aTermsrvWmsSrcD_28; "termsrv\\wms\\src\\devices\\wmssvc\\dis"...
0x1400114c1  mov     r9, r14; unsigned __int16 *
0x1400114c4  lea     r13, a0; "0"
0x1400114cb  mov     r8, rsi; unsigned __int16 *
0x1400114ce  mov     rcx, rdi; unsigned __int16 *
0x1400114d1  mov     qword ptr [rsp+60h+dwOptions], r13; unsigned __int16 *
0x1400114d6  mov     edx, 6C0h; unsigned int
0x1400114db  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400114e0  call    cs:__imp_IsDebuggerPresent
0x1400114e6  test    eax, eax
0x1400114e8  jz      short loc_1400114F5
0x1400114ea  mov     r9d, 6C0h
0x1400114f0  jmp     loc_1400113E5
0x1400114f5  mov     r8d, 6C0h
0x1400114fb  jmp     loc_140011417
0x140011500  mov     [rdi], esi
0x140011502  jmp     short loc_140011506
0x140011504  mov     [rdi], ebx
0x140011506  mov     rcx, [rbp+hKey]; hKey
0x14001150a  test    rcx, rcx
0x14001150d  jz      short loc_140011515
0x14001150f  call    cs:__imp_RegCloseKey
0x140011515  mov     eax, ebx
0x140011517  mov     rbx, [rsp+60h+arg_0]
0x14001151f  add     rsp, 60h
0x140011523  pop     r14
0x140011525  pop     r13
0x140011527  pop     rdi
0x140011528  pop     rsi
0x140011529  pop     rbp
0x14001152a  retn
```
