# CPolicyCheck::AddPolicyEntryFromRegistry(HKEY__ *,ushort const *)

- ea: `0x18000300c`
- end: `0x180003200`
- name: `?AddPolicyEntryFromRegistry@CPolicyCheck@@QEAAJPEAUHKEY__@@PEBG@Z`
- size: `500`
- prototype: `__int64 __fastcall(CPolicyCheck *__hidden this, HKEY hKey, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x180003afc`

## callees

- `0x180002e78`
- `0x18000300c`
- `0x1800038dc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800031e3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800031e3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800030a3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800030de`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003116`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000314e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800030a3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800030de`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003116`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000314e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003068`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003068`

## string_xrefs

- `0x18000309c`: `InstallTrustedOCX`
- `0x1800030d4`: `InstallSignedOCX`
- `0x18000310c`: `InstallUnSignedOCX`

## pseudocode

```c
__int64 __fastcall CPolicyCheck::AddPolicyEntryFromRegistry(CPolicyCheck *this, HKEY hKey, const unsigned __int16 *a3)
{
  int PolicyEntry; // ebx
  struct CPolicyEntry *v6; // r10
  int v7; // r9d
  int v8; // r8d
  DWORD Type; // [rsp+30h] [rbp-30h] BYREF
  BYTE v11[4]; // [rsp+34h] [rbp-2Ch] BYREF
  __int64 v12; // [rsp+38h] [rbp-28h] BYREF
  BYTE v13[4]; // [rsp+40h] [rbp-20h] BYREF
  HKEY hKeya; // [rsp+48h] [rbp-18h] BYREF
  struct CPolicyEntry *v15; // [rsp+50h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+98h] [rbp+38h] BYREF

  hKeya = 0;
  Type = 0;
  cbData = 0;
  v12 = 0;
  *(_DWORD *)v11 = 0;
  PolicyEntry = 0;
  *(_DWORD *)v13 = 0;
  v15 = 0;
  if ( !RegOpenKeyExW(hKey, a3, 0, 0x20019u, &hKeya) )
  {
    Type = 4;
    cbData = 4;
    if ( RegQueryValueExW(hKeya, L"InstallTrustedOCX", 0, &Type, (LPBYTE)&v12 + 4, &cbData) )
      HIDWORD(v12) = 1;
    Type = 4;
    cbData = 4;
    if ( RegQueryValueExW(hKeya, L"InstallSignedOCX", 0, &Type, (LPBYTE)&v12, &cbData) )
      LODWORD(v12) = 0;
    Type = 4;
    cbData = 4;
    if ( RegQueryValueExW(hKeya, L"InstallUnSignedOCX", 0, &Type, v11, &cbData) )
      *(_DWORD *)v11 = 0;
    Type = 4;
    cbData = 4;
    if ( RegQueryValueExW(hKeya, L"VerifyServerCert", 0, &Type, v13, &cbData) )
      *(_DWORD *)v13 = 0;
    if ( HIDWORD(v12) > 2 || (unsigned int)v12 > 2 || *(_DWORD *)v11 > 2u )
    {
      PolicyEntry = -2147024809;
    }
    else
    {
      PolicyEntry = CPolicyCheck::FindPolicyEntry(this, a3, &v15);
      if ( PolicyEntry >= 0 && (v6 = v15) != 0 )
      {
        *((_DWORD *)v15 + 11) = 0;
        v7 = *(_DWORD *)v13;
        v8 = *(_DWORD *)v11;
        *(_QWORD *)((char *)v6 + 28) = v12;
        *((_DWORD *)v6 + 10) = v8;
        *((_DWORD *)v6 + 9) = v7;
      }
      else
      {
        PolicyEntry = CPolicyCheck::AddPolicyEntry(
                        this,
                        a3,
                        SHIDWORD(v12),
                        v12,
                        *(unsigned int *)v11,
                        *(unsigned int *)v13);
      }
    }
  }
  if ( hKeya )
    RegCloseKey(hKeya);
  return (unsigned int)PolicyEntry;
}

```

## disassembly

```asm
0x18000300c  mov     [rsp-18h+arg_0], rbx
0x180003011  mov     [rsp-18h+arg_8], rsi
0x180003016  push    rbp
0x180003017  push    rdi
0x180003018  push    r14
0x18000301a  mov     rbp, rsp
0x18000301d  sub     rsp, 60h
0x180003021  xor     r14d, r14d
0x180003024  mov     rsi, rcx
0x180003027  mov     rdi, r8
0x18000302a  mov     [rbp+hKey], r14
0x18000302e  mov     rax, rdx
0x180003031  mov     [rbp+Type], r14d
0x180003035  lea     rcx, [rbp+hKey]
0x180003039  mov     [rbp+cbData], r14d
0x18000303d  mov     [rsp+60h+phkResult], rcx; phkResult
0x180003042  mov     r9d, 20019h; samDesired
0x180003048  mov     rcx, rax; hKey
0x18000304b  mov     dword ptr [rbp+var_28+4], r14d
0x18000304f  xor     r8d, r8d; ulOptions
0x180003052  mov     dword ptr [rbp+var_28], r14d
0x180003056  mov     rdx, rdi; lpSubKey
0x180003059  mov     dword ptr [rbp+var_2C], r14d
0x18000305d  mov     ebx, r14d
0x180003060  mov     dword ptr [rbp+var_20], r14d
0x180003064  mov     [rbp+var_10], r14
0x180003068  call    cs:__imp_RegOpenKeyExW
0x18000306e  test    eax, eax
0x180003070  jnz     loc_1800031DA
0x180003076  mov     rcx, [rbp+hKey]; hKey
0x18000307a  lea     ebx, [rax+4]
0x18000307d  lea     rax, [rbp+cbData]
0x180003081  mov     [rbp+Type], ebx
0x180003084  mov     [rsp+60h+lpcbData], rax; lpcbData
0x180003089  lea     r9, [rbp+Type]; lpType
0x18000308d  lea     rax, [rbp+var_28+4]
0x180003091  mov     [rbp+cbData], ebx
0x180003094  xor     r8d, r8d; lpReserved
0x180003097  mov     [rsp+60h+phkResult], rax; lpData
0x18000309c  lea     rdx, ValueName; "InstallTrustedOCX"
0x1800030a3  call    cs:__imp_RegQueryValueExW
0x1800030a9  test    eax, eax
0x1800030ab  jz      short loc_1800030B4
0x1800030ad  mov     dword ptr [rbp+var_28+4], 1
0x1800030b4  mov     rcx, [rbp+hKey]; hKey
0x1800030b8  lea     rax, [rbp+cbData]
0x1800030bc  mov     [rsp+60h+lpcbData], rax; lpcbData
0x1800030c1  lea     r9, [rbp+Type]; lpType
0x1800030c5  lea     rax, [rbp+var_28]
0x1800030c9  mov     [rbp+Type], ebx
0x1800030cc  xor     r8d, r8d; lpReserved
0x1800030cf  mov     [rsp+60h+phkResult], rax; lpData
0x1800030d4  lea     rdx, aInstallsignedo; "InstallSignedOCX"
0x1800030db  mov     [rbp+cbData], ebx
0x1800030de  call    cs:__imp_RegQueryValueExW
0x1800030e4  test    eax, eax
0x1800030e6  jz      short loc_1800030EC
0x1800030e8  mov     dword ptr [rbp+var_28], r14d
0x1800030ec  mov     rcx, [rbp+hKey]; hKey
0x1800030f0  lea     rax, [rbp+cbData]
0x1800030f4  mov     [rsp+60h+lpcbData], rax; lpcbData
0x1800030f9  lea     r9, [rbp+Type]; lpType
0x1800030fd  lea     rax, [rbp+var_2C]
0x180003101  mov     [rbp+Type], ebx
0x180003104  xor     r8d, r8d; lpReserved
0x180003107  mov     [rsp+60h+phkResult], rax; lpData
0x18000310c  lea     rdx, aInstallunsigne; "InstallUnSignedOCX"
0x180003113  mov     [rbp+cbData], ebx
0x180003116  call    cs:__imp_RegQueryValueExW
0x18000311c  test    eax, eax
0x18000311e  jz      short loc_180003124
0x180003120  mov     dword ptr [rbp+var_2C], r14d
0x180003124  mov     rcx, [rbp+hKey]; hKey
0x180003128  lea     rax, [rbp+cbData]
0x18000312c  mov     [rsp+60h+lpcbData], rax; lpcbData
0x180003131  lea     r9, [rbp+Type]; lpType
0x180003135  lea     rax, [rbp+var_20]
0x180003139  mov     [rbp+Type], ebx
0x18000313c  xor     r8d, r8d; lpReserved
0x18000313f  mov     [rsp+60h+phkResult], rax; lpData
0x180003144  lea     rdx, aVerifyserverce; "VerifyServerCert"
0x18000314b  mov     [rbp+cbData], ebx
0x18000314e  call    cs:__imp_RegQueryValueExW
0x180003154  test    eax, eax
0x180003156  jz      short loc_18000315C
0x180003158  mov     dword ptr [rbp+var_20], r14d
0x18000315c  cmp     dword ptr [rbp+var_28+4], 2
0x180003160  ja      short loc_1800031D5
0x180003162  cmp     dword ptr [rbp+var_28], 2
0x180003166  ja      short loc_1800031D5
0x180003168  cmp     dword ptr [rbp+var_2C], 2
0x18000316c  ja      short loc_1800031D5
0x18000316e  lea     r8, [rbp+var_10]; struct CPolicyEntry **
0x180003172  mov     rdx, rdi; unsigned __int16 *
0x180003175  mov     rcx, rsi; this
0x180003178  call    ?FindPolicyEntry@CPolicyCheck@@QEAAJPEBGPEAPEAVCPolicyEntry@@@Z; CPolicyCheck::FindPolicyEntry(ushort const *,CPolicyEntry * *)
0x18000317d  mov     ebx, eax
0x18000317f  test    eax, eax
0x180003181  js      short loc_1800031B0
0x180003183  mov     r10, [rbp+var_10]
0x180003187  test    r10, r10
0x18000318a  jz      short loc_1800031B0
0x18000318c  mov     [r10+2Ch], r14d
0x180003190  mov     r9d, dword ptr [rbp+var_20]
0x180003194  mov     r8d, dword ptr [rbp+var_2C]
0x180003198  mov     edx, dword ptr [rbp+var_28]
0x18000319b  mov     ecx, dword ptr [rbp+var_28+4]
0x18000319e  mov     [r10+20h], ecx
0x1800031a2  mov     [r10+1Ch], edx
0x1800031a6  mov     [r10+28h], r8d
0x1800031aa  mov     [r10+24h], r9d
0x1800031ae  jmp     short loc_1800031DA
0x1800031b0  mov     eax, dword ptr [rbp+var_20]
0x1800031b3  mov     rdx, rdi; unsigned __int16 *
0x1800031b6  mov     r9d, dword ptr [rbp+var_28]; unsigned int
0x1800031ba  mov     rcx, rsi; this
0x1800031bd  mov     r8d, dword ptr [rbp+var_28+4]; unsigned int
0x1800031c1  mov     dword ptr [rsp+60h+lpcbData], eax; unsigned int
0x1800031c5  mov     eax, dword ptr [rbp+var_2C]
0x1800031c8  mov     dword ptr [rsp+60h+phkResult], eax; unsigned int
0x1800031cc  call    ?AddPolicyEntry@CPolicyCheck@@QEAAJPEBGKKKK@Z; CPolicyCheck::AddPolicyEntry(ushort const *,ulong,ulong,ulong,ulong)
0x1800031d1  mov     ebx, eax
0x1800031d3  jmp     short loc_1800031DA
0x1800031d5  mov     ebx, 80070057h
0x1800031da  mov     rcx, [rbp+hKey]; hKey
0x1800031de  test    rcx, rcx
0x1800031e1  jz      short loc_1800031E9
0x1800031e3  call    cs:__imp_RegCloseKey
0x1800031e9  lea     r11, [rsp+60h+var_s0]
0x1800031ee  mov     eax, ebx
0x1800031f0  mov     rbx, [r11+20h]
0x1800031f4  mov     rsi, [r11+28h]
0x1800031f8  mov     rsp, r11
0x1800031fb  pop     r14
0x1800031fd  pop     rdi
0x1800031fe  pop     rbp
0x1800031ff  retn
```
