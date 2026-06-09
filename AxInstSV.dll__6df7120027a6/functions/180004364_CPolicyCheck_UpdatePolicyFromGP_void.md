# CPolicyCheck::UpdatePolicyFromGP(void)

- ea: `0x180004364`
- end: `0x1800046bc`
- name: `?UpdatePolicyFromGP@CPolicyCheck@@QEAAJXZ`
- size: `856`
- prototype: `__int64 __fastcall(HKEY *this)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000bbfc`
- `0x18000c224`

## callees

- `0x18000383c`
- `0x18000401c`
- `0x180004318`
- `0x180004364`
- `0x1800046c4`
- `0x180004fe8`
- `0x180014310`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800044f5`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800044f5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004693`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800046a2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004693`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800046a2`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800045fe`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800045fe`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000465b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000465b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000453b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000453b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800043ea`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000447e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800043ea`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000447e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180004458`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180004458`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000456f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000456f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004676`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004684`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004676`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004684`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004401`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004401`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800045ac`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800045ac`
- `ntdll!RtlReleaseResource` at `0x180004665`
- `ntdll!RtlReleaseResource` at `0x180004665`

## string_xrefs

- `0x18000444e`: `ApprovedActiveXInstallSites`
- `0x180004474`: `Software\policies\Microsoft\Windows\AxInstaller\ApprovedActiveXInstallSites`

## pseudocode

```c
__int64 __fastcall CPolicyCheck::UpdatePolicyFromGP(HKEY *this)
{
  unsigned __int16 *v2; // rsi
  HKEY *v3; // rbx
  LSTATUS v4; // eax
  signed int v5; // ebx
  signed int LastError; // eax
  LSTATUS v7; // eax
  wchar_t *v8; // rdi
  int v9; // edx
  DWORD i; // r15d
  BYTE phkResult; // [rsp+20h] [rbp-59h]
  DWORD Type; // [rsp+60h] [rbp-19h] BYREF
  HKEY v14; // [rsp+68h] [rbp-11h] BYREF
  DWORD dwDisposition; // [rsp+70h] [rbp-9h] BYREF
  DWORD cchValueName; // [rsp+74h] [rbp-5h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-1h] BYREF
  unsigned __int16 *v18; // [rsp+80h] [rbp+7h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+88h] [rbp+Fh] BYREF
  DWORD cSubKeys; // [rsp+8Ch] [rbp+13h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+90h] [rbp+17h] BYREF
  BYTE Data[56]; // [rsp+98h] [rbp+1Fh] BYREF
  DWORD cbMaxValueNameLen; // [rsp+E0h] [rbp+67h] BYREF
  DWORD cbData; // [rsp+E8h] [rbp+6Fh] BYREF
  DWORD cValues; // [rsp+F0h] [rbp+77h] BYREF
  DWORD cbMaxValueLen; // [rsp+F8h] [rbp+7Fh] BYREF

  hKey = 0;
  v14 = 0;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  cValues = 0;
  cbMaxValueNameLen = 0;
  cbMaxValueLen = 0;
  ftLastWriteTime = 0;
  *(_QWORD *)Data = 0;
  v2 = 0;
  v18 = 0;
  cbData = 0;
  cchValueName = 0;
  Type = 0;
  dwDisposition = 0;
  v3 = this + 20;
  if ( !this[20] )
  {
    v4 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\Internet Settings",
           0,
           0x2001Fu,
           this + 20);
    if ( v4 )
    {
      if ( v4 == 2 )
      {
LABEL_4:
        v5 = 0;
        goto LABEL_26;
      }
      goto LABEL_5;
    }
  }
  CPolicyCheck::UpdateTrustedZonePolicyFromGP((CPolicyCheck *)this);
  if ( RegCreateKeyExW(*v3, L"ApprovedActiveXInstallSites", 0, 0, 0, 0x2001Fu, 0, &v14, &dwDisposition) )
    goto LABEL_5;
  v7 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\policies\\Microsoft\\Windows\\AxInstaller\\ApprovedActiveXInstallSites",
         0,
         0x20019u,
         &hKey);
  if ( v7 )
  {
    if ( v7 == 2 )
    {
      CPolicyCheck::DeletedMarkedEntries((CPolicyCheck *)this, v14, 1, 1);
      goto LABEL_4;
    }
    goto LABEL_5;
  }
  if ( RegQueryInfoKeyW(
         hKey,
         0,
         0,
         0,
         &cSubKeys,
         &cbMaxSubKeyLen,
         0,
         &cValues,
         &cbMaxValueNameLen,
         &cbMaxValueLen,
         0,
         &ftLastWriteTime) )
  {
    goto LABEL_5;
  }
  if ( dwDisposition == 2 )
  {
    Type = 3;
    cbData = 8;
    if ( !RegQueryValueExW(v14, L"AxInstGPRefreshTime", 0, &Type, Data, &cbData)
      && !memcmp_0(Data, &ftLastWriteTime, 8u) )
    {
      goto LABEL_4;
    }
  }
  v8 = 0;
  if ( !cValues )
  {
LABEL_18:
    v18 = (unsigned __int16 *)(this + 2);
    RtlAcquireResourceExclusive((PRTL_RESOURCE)(this + 2), 1u);
    CPolicyCheck::UpdateMarkToBeDeletedFlag((CPolicyCheck *)this, v9);
    for ( i = 0; i < cValues; ++i )
    {
      cchValueName = cbMaxValueNameLen;
      cbData = cbMaxValueLen;
      *v2 = 0;
      if ( !RegEnumValueW(hKey, i, v2, &cchValueName, 0, &Type, (LPBYTE)v8, &cbData) )
        CPolicyCheck::UpdateLocalRegPolicyEntry((CPolicyCheck *)this, v14, v2, v8, phkResult);
    }
    CPolicyCheck::DeletedMarkedEntries((CPolicyCheck *)this, v14, 1, 0);
    RegSetValueExW(v14, L"AxInstGPRefreshTime", 0, 3u, (const BYTE *)&ftLastWriteTime, 8u);
    RtlReleaseResource((PRTL_RESOURCE)(this + 2));
    v5 = 0;
    if ( !v8 )
      goto LABEL_24;
    goto LABEL_23;
  }
  v8 = (wchar_t *)LocalAlloc(0x40u, cbMaxValueLen);
  if ( !v8 )
  {
LABEL_5:
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_26;
  }
  v5 = Utils::AllocateCchStringBuffer(cbMaxValueNameLen, &v18, &cbMaxValueNameLen);
  v2 = v18;
  if ( v5 >= 0 )
    goto LABEL_18;
LABEL_23:
  LocalFree(v8);
LABEL_24:
  if ( v2 )
    LocalFree(v2);
LABEL_26:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v14 )
    RegCloseKey(v14);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180004364  push    rbp
0x180004366  push    rbx
0x180004367  push    rsi
0x180004368  push    rdi
0x180004369  push    r12
0x18000436b  push    r14
0x18000436d  push    r15
0x18000436f  lea     rbp, [rsp-27h]
0x180004374  sub     rsp, 0A0h
0x18000437b  mov     r14, rcx
0x18000437e  xor     r12d, r12d
0x180004381  mov     [rbp+57h+hKey], r12
0x180004385  mov     [rbp+57h+var_68], r12
0x180004389  mov     [rbp+57h+cSubKeys], r12d
0x18000438d  mov     [rbp+57h+cbMaxSubKeyLen], r12d
0x180004391  mov     [rbp+57h+cValues], r12d
0x180004395  mov     [rbp+57h+cbMaxValueNameLen], r12d
0x180004399  mov     [rbp+57h+cbMaxValueLen], r12d
0x18000439d  mov     qword ptr [rbp+57h+ftLastWriteTime.dwLowDateTime], r12
0x1800043a1  mov     qword ptr [rbp+57h+Data], r12
0x1800043a5  mov     esi, r12d
0x1800043a8  mov     [rbp+57h+var_50], r12
0x1800043ac  mov     [rbp+57h+cbData], r12d
0x1800043b0  mov     [rbp+57h+cchValueName], r12d
0x1800043b4  mov     [rbp+57h+Type], r12d
0x1800043b8  mov     [rbp+57h+dwDisposition], r12d
0x1800043bc  lea     rbx, [rcx+0A0h]
0x1800043c3  mov     rdi, 0FFFFFFFF80000002h
0x1800043ca  mov     r15d, 2001Fh
0x1800043d0  cmp     [rbx], r12
0x1800043d3  jnz     short loc_18000441F
0x1800043d5  mov     [rsp+0D0h+phkResult], rbx; phkResult
0x1800043da  mov     r9d, r15d; samDesired
0x1800043dd  xor     r8d, r8d; ulOptions
0x1800043e0  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800043e7  mov     rcx, rdi; hKey
0x1800043ea  call    cs:__imp_RegOpenKeyExW
0x1800043f0  test    eax, eax
0x1800043f2  jz      short loc_18000441F
0x1800043f4  cmp     eax, 2
0x1800043f7  jnz     short loc_180004401
0x1800043f9  mov     ebx, r12d
0x1800043fc  jmp     loc_18000468A
0x180004401  call    cs:__imp_GetLastError
0x180004407  mov     ebx, eax
0x180004409  test    eax, eax
0x18000440b  jle     loc_18000468A
0x180004411  movzx   ebx, ax
0x180004414  or      ebx, 80070000h
0x18000441a  jmp     loc_18000468A
0x18000441f  mov     rcx, r14; this
0x180004422  call    ?UpdateTrustedZonePolicyFromGP@CPolicyCheck@@QEAAXXZ; CPolicyCheck::UpdateTrustedZonePolicyFromGP(void)
0x180004427  lea     rax, [rbp+57h+dwDisposition]
0x18000442b  mov     [rsp+0D0h+lpdwDisposition], rax; lpdwDisposition
0x180004430  lea     rax, [rbp+57h+var_68]
0x180004434  mov     [rsp+0D0h+var_98], rax; phkResult
0x180004439  mov     [rsp+0D0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x18000443e  mov     [rsp+0D0h+samDesired], r15d; samDesired
0x180004443  mov     dword ptr [rsp+0D0h+phkResult], r12d; dwOptions
0x180004448  xor     r9d, r9d; lpClass
0x18000444b  xor     r8d, r8d; Reserved
0x18000444e  lea     rdx, aApprovedactive; "ApprovedActiveXInstallSites"
0x180004455  mov     rcx, [rbx]; hKey
0x180004458  call    cs:__imp_RegCreateKeyExW
0x18000445e  test    eax, eax
0x180004460  jnz     short loc_180004401
0x180004462  lea     rax, [rbp+57h+hKey]
0x180004466  mov     [rsp+0D0h+phkResult], rax; phkResult
0x18000446b  mov     r9d, 20019h; samDesired
0x180004471  xor     r8d, r8d; ulOptions
0x180004474  lea     rdx, aSoftwarePolici_0; "Software\\policies\\Microsoft\\Windows"...
0x18000447b  mov     rcx, rdi; hKey
0x18000447e  call    cs:__imp_RegOpenKeyExW
0x180004484  test    eax, eax
0x180004486  jz      short loc_1800044A9
0x180004488  cmp     eax, 2
0x18000448b  jnz     loc_180004401
0x180004491  lea     r9d, [rax-1]; int
0x180004495  mov     r8d, r9d; int
0x180004498  mov     rdx, [rbp+57h+var_68]; HKEY
0x18000449c  mov     rcx, r14; this
0x18000449f  call    ?DeletedMarkedEntries@CPolicyCheck@@QEAAJPEAUHKEY__@@HH@Z; CPolicyCheck::DeletedMarkedEntries(HKEY__ *,int,int)
0x1800044a4  jmp     loc_1800043F9
0x1800044a9  lea     rax, [rbp+57h+ftLastWriteTime]
0x1800044ad  mov     [rsp+0D0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1800044b2  mov     [rsp+0D0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x1800044b7  lea     rax, [rbp+57h+cbMaxValueLen]
0x1800044bb  mov     [rsp+0D0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x1800044c0  lea     rax, [rbp+57h+cbMaxValueNameLen]
0x1800044c4  mov     [rsp+0D0h+lpdwDisposition], rax; lpcbMaxValueNameLen
0x1800044c9  lea     rax, [rbp+57h+cValues]
0x1800044cd  mov     [rsp+0D0h+var_98], rax; lpcValues
0x1800044d2  mov     [rsp+0D0h+lpSecurityAttributes], r12; lpcbMaxClassLen
0x1800044d7  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x1800044db  mov     qword ptr [rsp+0D0h+samDesired], rax; lpcbMaxSubKeyLen
0x1800044e0  lea     rax, [rbp+57h+cSubKeys]
0x1800044e4  mov     [rsp+0D0h+phkResult], rax; lpcSubKeys
0x1800044e9  xor     r9d, r9d; lpReserved
0x1800044ec  xor     r8d, r8d; lpcchClass
0x1800044ef  xor     edx, edx; lpClass
0x1800044f1  mov     rcx, [rbp+57h+hKey]; hKey
0x1800044f5  call    cs:__imp_RegQueryInfoKeyW
0x1800044fb  test    eax, eax
0x1800044fd  jnz     loc_180004401
0x180004503  cmp     [rbp+57h+dwDisposition], 2
0x180004507  jnz     short loc_18000455E
0x180004509  mov     [rbp+57h+Type], 3
0x180004510  mov     [rbp+57h+cbData], 8
0x180004517  lea     rax, [rbp+57h+cbData]
0x18000451b  mov     qword ptr [rsp+0D0h+samDesired], rax; lpcbData
0x180004520  lea     rax, [rbp+57h+Data]
0x180004524  mov     [rsp+0D0h+phkResult], rax; lpData
0x180004529  lea     r9, [rbp+57h+Type]; lpType
0x18000452d  xor     r8d, r8d; lpReserved
0x180004530  lea     rdx, aAxinstgprefres; "AxInstGPRefreshTime"
0x180004537  mov     rcx, [rbp+57h+var_68]; hKey
0x18000453b  call    cs:__imp_RegQueryValueExW
0x180004541  test    eax, eax
0x180004543  jnz     short loc_18000455E
0x180004545  lea     r8d, [rax+8]; Size
0x180004549  lea     rdx, [rbp+57h+ftLastWriteTime]; Buf2
0x18000454d  lea     rcx, [rbp+57h+Data]; Buf1
0x180004551  call    memcmp_0
0x180004556  test    eax, eax
0x180004558  jz      loc_1800043F9
0x18000455e  mov     rdi, r12
0x180004561  cmp     [rbp+57h+cValues], r12d
0x180004565  jbe     short loc_18000459F
0x180004567  mov     edx, [rbp+57h+cbMaxValueLen]; uBytes
0x18000456a  mov     ecx, 40h ; '@'; uFlags
0x18000456f  call    cs:__imp_LocalAlloc
0x180004575  mov     rdi, rax
0x180004578  test    rax, rax
0x18000457b  jz      loc_180004401
0x180004581  lea     r8, [rbp+57h+cbMaxValueNameLen]; unsigned int *
0x180004585  lea     rdx, [rbp+57h+var_50]; unsigned __int16 **
0x180004589  mov     ecx, [rbp+57h+cbMaxValueNameLen]; unsigned int
0x18000458c  call    ?AllocateCchStringBuffer@Utils@@SAJKPEAPEAGPEAK@Z; Utils::AllocateCchStringBuffer(ulong,ushort * *,ulong *)
0x180004591  mov     ebx, eax
0x180004593  mov     rsi, [rbp+57h+var_50]
0x180004597  test    eax, eax
0x180004599  js      loc_180004673
0x18000459f  lea     rbx, [r14+10h]
0x1800045a3  mov     [rbp+57h+var_50], rbx
0x1800045a7  mov     dl, 1; Wait
0x1800045a9  mov     rcx, rbx; Resource
0x1800045ac  call    cs:__imp_RtlAcquireResourceExclusive
0x1800045b2  nop
0x1800045b3  mov     rcx, r14; this
0x1800045b6  call    ?UpdateMarkToBeDeletedFlag@CPolicyCheck@@QEAAJH@Z; CPolicyCheck::UpdateMarkToBeDeletedFlag(int)
0x1800045bb  mov     r15d, r12d
0x1800045be  cmp     [rbp+57h+cValues], r12d
0x1800045c2  jbe     short loc_180004623
0x1800045c4  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x1800045c7  mov     [rbp+57h+cchValueName], eax
0x1800045ca  mov     eax, [rbp+57h+cbMaxValueLen]
0x1800045cd  mov     [rbp+57h+cbData], eax
0x1800045d0  mov     [rsi], r12w
0x1800045d4  lea     rax, [rbp+57h+cbData]
0x1800045d8  mov     [rsp+0D0h+var_98], rax; lpcbData
0x1800045dd  mov     [rsp+0D0h+lpSecurityAttributes], rdi; lpData
0x1800045e2  lea     rax, [rbp+57h+Type]
0x1800045e6  mov     qword ptr [rsp+0D0h+samDesired], rax; lpType
0x1800045eb  mov     [rsp+0D0h+phkResult], r12; Data
0x1800045f0  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x1800045f4  mov     r8, rsi; lpValueName
0x1800045f7  mov     edx, r15d; dwIndex
0x1800045fa  mov     rcx, [rbp+57h+hKey]; hKey
0x1800045fe  call    cs:__imp_RegEnumValueW
0x180004604  test    eax, eax
0x180004606  jnz     short loc_18000461A
0x180004608  mov     r9, rdi; Buffer
0x18000460b  mov     r8, rsi; unsigned __int16 *
0x18000460e  mov     rdx, [rbp+57h+var_68]; hKey
0x180004612  mov     rcx, r14; this
0x180004615  call    ?UpdateLocalRegPolicyEntry@CPolicyCheck@@QEAAJPEAUHKEY__@@PEBG1H@Z; CPolicyCheck::UpdateLocalRegPolicyEntry(HKEY__ *,ushort const *,ushort const *,int)
0x18000461a  inc     r15d
0x18000461d  cmp     r15d, [rbp+57h+cValues]
0x180004621  jb      short loc_1800045C4
0x180004623  xor     r9d, r9d; int
0x180004626  lea     r8d, [r9+1]; int
0x18000462a  mov     rdx, [rbp+57h+var_68]; HKEY
0x18000462e  mov     rcx, r14; this
0x180004631  call    ?DeletedMarkedEntries@CPolicyCheck@@QEAAJPEAUHKEY__@@HH@Z; CPolicyCheck::DeletedMarkedEntries(HKEY__ *,int,int)
0x180004636  mov     [rsp+0D0h+samDesired], 8; cbData
0x18000463e  lea     rax, [rbp+57h+ftLastWriteTime]
0x180004642  mov     [rsp+0D0h+phkResult], rax; lpData
0x180004647  mov     r9d, 3; dwType
0x18000464d  xor     r8d, r8d; Reserved
0x180004650  lea     rdx, aAxinstgprefres; "AxInstGPRefreshTime"
0x180004657  mov     rcx, [rbp+57h+var_68]; hKey
0x18000465b  call    cs:__imp_RegSetValueExW
0x180004661  nop
0x180004662  mov     rcx, rbx; Resource
0x180004665  call    cs:__imp_RtlReleaseResource
0x18000466b  mov     ebx, r12d
0x18000466e  test    rdi, rdi
0x180004671  jz      short loc_18000467C
0x180004673  mov     rcx, rdi; hMem
0x180004676  call    cs:__imp_LocalFree
0x18000467c  test    rsi, rsi
0x18000467f  jz      short loc_18000468A
0x180004681  mov     rcx, rsi; hMem
0x180004684  call    cs:__imp_LocalFree
0x18000468a  mov     rcx, [rbp+57h+hKey]; hKey
0x18000468e  test    rcx, rcx
0x180004691  jz      short loc_180004699
0x180004693  call    cs:__imp_RegCloseKey
0x180004699  mov     rcx, [rbp+57h+var_68]; hKey
0x18000469d  test    rcx, rcx
0x1800046a0  jz      short loc_1800046A8
0x1800046a2  call    cs:__imp_RegCloseKey
0x1800046a8  mov     eax, ebx
0x1800046aa  add     rsp, 0A0h
0x1800046b1  pop     r15
0x1800046b3  pop     r14
0x1800046b5  pop     r12
0x1800046b7  pop     rdi
0x1800046b8  pop     rsi
0x1800046b9  pop     rbx
0x1800046ba  pop     rbp
0x1800046bb  retn
```
