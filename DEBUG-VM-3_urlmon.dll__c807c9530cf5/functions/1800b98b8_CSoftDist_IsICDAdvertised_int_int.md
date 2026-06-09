# CSoftDist::IsICDAdvertised(int *,int *)

- ea: `0x1800b98b8`
- end: `0x1800b9d8a`
- name: `?IsICDAdvertised@CSoftDist@@AEAAJPEAH0@Z`
- size: `1234`
- prototype: `__int64 __fastcall(CSoftDist *__hidden this, int *, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800baed0`

## callees

- `0x1800150e0`
- `0x180030880`
- `0x1800763a8`
- `0x18009d130`
- `0x1800b9678`
- `0x1800b989c`
- `0x1800b98b8`
- `0x18011baa0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800b9974`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800b99bf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800b9a05`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800b9a6b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800b9974`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800b99bf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800b9a05`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800b9a6b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800b9a37`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800b9aa0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800b9ae9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800b9b17`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800b9b5b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800b9bac`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800b9bef`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800b9c26`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800b9c69`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800b9ca2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800b9a37`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800b9aa0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800b9ae9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800b9b17`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800b9b5b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800b9bac`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800b9bef`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800b9c26`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800b9c69`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800b9ca2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b9d19`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b9d2e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b9d43`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b9d58`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b9d19`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b9d2e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b9d43`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b9d58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b9b65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b9b65`

## string_xrefs

- `0x1800b9a2b`: `Precache`

## pseudocode

```c
__int64 __fastcall CSoftDist::IsICDAdvertised(CSoftDist *this, int *a2, int *a3)
{
  CHAR *v6; // rsi
  int v7; // ebx
  int IsAuthorizedCDF; // eax
  HKEY v9; // rcx
  char v10; // r9
  BYTE *v11; // rax
  signed int LastError; // eax
  BYTE *v13; // rax
  BYTE *v14; // rax
  char v15; // r9
  unsigned int v16; // edx
  unsigned int v17; // r8d
  DWORD lpcbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY v21; // [rsp+38h] [rbp-C8h] BYREF
  BYTE Data[4]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-BCh] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v25; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v26; // [rsp+54h] [rbp-ACh] BYREF
  HKEY v27; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  LPCSTR lpSubKey; // [rsp+68h] [rbp-98h]
  BYTE v30[272]; // [rsp+70h] [rbp-90h] BYREF

  lpcbData = 260;
  *(_DWORD *)Data = 0;
  hKey = 0;
  phkResult = 0;
  v21 = 0;
  v6 = 0;
  v27 = 0;
  cbData = 4;
  Type = 0;
  v25 = 0;
  v26 = 0;
  lpSubKey = 0;
  if ( a2 && a3 )
  {
    *a2 = 0;
    *a3 = 1;
    *(_DWORD *)Data = RegOpenKeyExA(
                        HKEY_LOCAL_MACHINE,
                        "Software\\Microsoft\\Code Store Database\\Distribution Units",
                        0,
                        0xF003Fu,
                        &hKey);
    if ( *(_DWORD *)Data )
    {
      v7 = 1;
      goto LABEL_39;
    }
    v7 = Unicode2Ansi(*((LPCWCH *)this + 2));
    if ( v7 >= 0 )
    {
      v6 = (CHAR *)lpSubKey;
      if ( !RegOpenKeyExA(hKey, lpSubKey, 0, 0xF003Fu, &phkResult) )
      {
        IsAuthorizedCDF = CSoftDist::IsAuthorizedCDF(this, phkResult, 1);
        v9 = phkResult;
        *a3 = IsAuthorizedCDF;
        if ( !RegOpenKeyExA(v9, "AvailableVersion", 0, 0xF003Fu, &v21) )
        {
          if ( !RegQueryValueExA(v21, "Precache", 0, &Type, Data, &cbData) )
            *a2 = *(_DWORD *)Data >= 0;
          if ( !RegOpenKeyExA(phkResult, "AdvertisedVersion", 0, 0xF003Fu, &v27) )
          {
            lpcbData = 260;
            if ( !RegQueryValueExA(v27, 0, 0, &Type, v30, &lpcbData) )
              GetVersionFromString((LPCSTR)v30, (unsigned int *)this + 8, (unsigned int *)this + 9, v10);
            cbData = 4;
            RegQueryValueExA(v27, "AdState", 0, 0, (LPBYTE)this + 40, &cbData);
          }
          if ( !*((_QWORD *)this + 7) && !RegQueryValueExA(phkResult, 0, 0, &Type, 0, &lpcbData) )
          {
            v11 = (BYTE *)operator new(lpcbData);
            *((_QWORD *)this + 7) = v11;
            if ( !v11 )
            {
LABEL_18:
              v7 = -2147024882;
              goto LABEL_37;
            }
            if ( RegQueryValueExA(phkResult, 0, 0, &Type, v11, &lpcbData) )
              goto LABEL_20;
          }
          if ( !*((_QWORD *)this + 9) && !RegQueryValueExA(v21, "Abstract", 0, &Type, 0, &lpcbData) )
          {
            v13 = (BYTE *)operator new(lpcbData);
            *((_QWORD *)this + 9) = v13;
            if ( !v13 )
              goto LABEL_18;
            if ( RegQueryValueExA(v21, "Abstract", 0, &Type, v13, &lpcbData) )
              goto LABEL_20;
          }
          if ( !*((_QWORD *)this + 10) && !RegQueryValueExA(v21, "HREF", 0, &Type, 0, &lpcbData) )
          {
            v14 = (BYTE *)operator new(lpcbData);
            *((_QWORD *)this + 10) = v14;
            if ( !v14 )
              goto LABEL_18;
            if ( RegQueryValueExA(v21, "HREF", 0, &Type, v14, &lpcbData) )
            {
LABEL_20:
              LastError = GetLastError();
              v7 = LastError;
              if ( LastError > 0 )
                v7 = (unsigned __int16)LastError | 0x80070000;
              goto LABEL_37;
            }
          }
          lpcbData = 260;
          if ( !RegQueryValueExA(v21, 0, 0, &Type, v30, &lpcbData)
            && (int)GetVersionFromString((LPCSTR)v30, &v25, &v26, v15) >= 0 )
          {
            v16 = v25;
            v17 = v26;
            if ( !*((_QWORD *)this + 3) )
            {
              *((_DWORD *)this + 6) = v25;
              *((_DWORD *)this + 7) = v17;
            }
            v7 = CSoftDist::IsCDFNewerVersion(this, v16, v17) != 0;
            goto LABEL_37;
          }
        }
      }
      v7 = 1;
      goto LABEL_37;
    }
    v6 = (CHAR *)lpSubKey;
  }
  else
  {
    v7 = -2147024809;
  }
LABEL_37:
  if ( v6 )
    operator delete(v6);
LABEL_39:
  if ( v21 )
  {
    RegCloseKey(v21);
    v21 = 0;
  }
  if ( v27 )
  {
    RegCloseKey(v27);
    v27 = 0;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800b98b8  mov     [rsp-8+arg_18], rbx
0x1800b98bd  push    rbp
0x1800b98be  push    rsi
0x1800b98bf  push    rdi
0x1800b98c0  push    r12
0x1800b98c2  push    r13
0x1800b98c4  push    r14
0x1800b98c6  push    r15
0x1800b98c8  lea     rbp, [rsp-90h]
0x1800b98d0  sub     rsp, 190h
0x1800b98d7  mov     rax, cs:__security_cookie
0x1800b98de  xor     rax, rsp
0x1800b98e1  mov     [rbp+0C0h+var_40], rax
0x1800b98e8  xor     r12d, r12d
0x1800b98eb  mov     [rsp+1C0h+var_190], 104h
0x1800b98f3  mov     dword ptr [rsp+1C0h+Data], r12d
0x1800b98f8  mov     r15, r8
0x1800b98fb  mov     [rsp+1C0h+hKey], r12
0x1800b9900  mov     r14, rdx
0x1800b9903  mov     [rsp+1C0h+var_178], r12
0x1800b9908  mov     rdi, rcx
0x1800b990b  mov     [rsp+1C0h+var_188], r12
0x1800b9910  mov     esi, r12d
0x1800b9913  mov     [rsp+1C0h+var_168], r12
0x1800b9918  mov     [rsp+1C0h+cbData], 4
0x1800b9920  mov     [rsp+1C0h+Type], r12d
0x1800b9925  mov     [rsp+1C0h+var_170], r12d
0x1800b992a  mov     [rsp+1C0h+var_16C], r12d
0x1800b992f  mov     [rsp+1C0h+lpSubKey], r12
0x1800b9934  test    rdx, rdx
0x1800b9937  jz      loc_1800B9CFD
0x1800b993d  test    r8, r8
0x1800b9940  jz      loc_1800B9CFD
0x1800b9946  mov     [rdx], r12d
0x1800b9949  lea     rax, [rsp+1C0h+hKey]
0x1800b994e  lea     r13d, [r12+1]
0x1800b9953  mov     [rsp+1C0h+phkResult], rax; phkResult
0x1800b9958  mov     [r8], r13d
0x1800b995b  lea     rdx, aSoftwareMicros_53; "Software\\Microsoft\\Code Store Databas"...
0x1800b9962  mov     esi, 0F003Fh
0x1800b9967  xor     r8d, r8d; ulOptions
0x1800b996a  mov     r9d, esi; samDesired
0x1800b996d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800b9974  call    cs:__imp_RegOpenKeyExA
0x1800b997a  mov     dword ptr [rsp+1C0h+Data], eax
0x1800b997e  test    eax, eax
0x1800b9980  jz      short loc_1800B998A
0x1800b9982  mov     ebx, r13d
0x1800b9985  jmp     loc_1800B9D0F
0x1800b998a  mov     rcx, [rdi+10h]; lpWideCharStr
0x1800b998e  lea     rdx, [rsp+1C0h+lpSubKey]
0x1800b9993  call    Unicode2Ansi
0x1800b9998  mov     ebx, eax
0x1800b999a  test    eax, eax
0x1800b999c  js      loc_1800B9CF6
0x1800b99a2  mov     rcx, [rsp+1C0h+hKey]; hKey
0x1800b99a7  lea     rax, [rsp+1C0h+var_178]
0x1800b99ac  mov     r9d, esi; samDesired
0x1800b99af  mov     [rsp+1C0h+phkResult], rax; phkResult
0x1800b99b4  mov     rsi, [rsp+1C0h+lpSubKey]
0x1800b99b9  xor     r8d, r8d; ulOptions
0x1800b99bc  mov     rdx, rsi; lpSubKey
0x1800b99bf  call    cs:__imp_RegOpenKeyExA
0x1800b99c5  test    eax, eax
0x1800b99c7  jz      short loc_1800B99D1
0x1800b99c9  mov     ebx, r13d
0x1800b99cc  jmp     loc_1800B9D02
0x1800b99d1  mov     rdx, [rsp+1C0h+var_178]; HKEY
0x1800b99d6  mov     r8d, r13d; int
0x1800b99d9  mov     rcx, rdi; this
0x1800b99dc  call    ?IsAuthorizedCDF@CSoftDist@@AEAAHPEAUHKEY__@@H@Z; CSoftDist::IsAuthorizedCDF(HKEY__ *,int)
0x1800b99e1  mov     rcx, [rsp+1C0h+var_178]; hKey
0x1800b99e6  lea     rdx, aAvailableversi; "AvailableVersion"
0x1800b99ed  mov     [r15], eax
0x1800b99f0  mov     ebx, 0F003Fh
0x1800b99f5  lea     rax, [rsp+1C0h+var_188]
0x1800b99fa  mov     r9d, ebx; samDesired
0x1800b99fd  xor     r8d, r8d; ulOptions
0x1800b9a00  mov     [rsp+1C0h+phkResult], rax; phkResult
0x1800b9a05  call    cs:__imp_RegOpenKeyExA
0x1800b9a0b  test    eax, eax
0x1800b9a0d  jnz     short loc_1800B99C9
0x1800b9a0f  mov     rcx, [rsp+1C0h+var_188]; hKey
0x1800b9a14  lea     rax, [rsp+1C0h+cbData]
0x1800b9a19  mov     [rsp+1C0h+lpcbData], rax; lpcbData
0x1800b9a1e  lea     r9, [rsp+1C0h+Type]; lpType
0x1800b9a23  lea     rax, [rsp+1C0h+Data]
0x1800b9a28  xor     r8d, r8d; lpReserved
0x1800b9a2b  lea     rdx, aPrecache_0; "Precache"
0x1800b9a32  mov     [rsp+1C0h+phkResult], rax; lpData
0x1800b9a37  call    cs:__imp_RegQueryValueExA
0x1800b9a3d  test    eax, eax
0x1800b9a3f  jnz     short loc_1800B9A4F
0x1800b9a41  cmp     dword ptr [rsp+1C0h+Data], r12d
0x1800b9a46  mov     eax, r12d
0x1800b9a49  setnl   al
0x1800b9a4c  mov     [r14], eax
0x1800b9a4f  mov     rcx, [rsp+1C0h+var_178]; hKey
0x1800b9a54  lea     rax, [rsp+1C0h+var_168]
0x1800b9a59  mov     r9d, ebx; samDesired
0x1800b9a5c  mov     [rsp+1C0h+phkResult], rax; phkResult
0x1800b9a61  xor     r8d, r8d; ulOptions
0x1800b9a64  lea     rdx, aAdvertisedvers; "AdvertisedVersion"
0x1800b9a6b  call    cs:__imp_RegOpenKeyExA
0x1800b9a71  test    eax, eax
0x1800b9a73  jnz     short loc_1800B9AEF
0x1800b9a75  mov     rcx, [rsp+1C0h+var_168]; hKey
0x1800b9a7a  lea     rax, [rsp+1C0h+var_190]
0x1800b9a7f  mov     [rsp+1C0h+lpcbData], rax; lpcbData
0x1800b9a84  lea     r9, [rsp+1C0h+Type]; lpType
0x1800b9a89  lea     rax, [rsp+1C0h+var_150]
0x1800b9a8e  mov     [rsp+1C0h+var_190], 104h
0x1800b9a96  xor     r8d, r8d; lpReserved
0x1800b9a99  mov     [rsp+1C0h+phkResult], rax; lpData
0x1800b9a9e  xor     edx, edx; lpValueName
0x1800b9aa0  call    cs:__imp_RegQueryValueExA
0x1800b9aa6  test    eax, eax
0x1800b9aa8  jnz     short loc_1800B9ABC
0x1800b9aaa  lea     r8, [rdi+24h]; unsigned int *
0x1800b9aae  lea     rdx, [rdi+20h]; unsigned int *
0x1800b9ab2  lea     rcx, [rsp+1C0h+var_150]; lpString1
0x1800b9ab7  call    ?GetVersionFromString@@YAJPEBDPEAK1D@Z; GetVersionFromString(char const *,ulong *,ulong *,char)
0x1800b9abc  lea     rcx, [rsp+1C0h+cbData]
0x1800b9ac1  mov     [rsp+1C0h+cbData], 4
0x1800b9ac9  mov     [rsp+1C0h+lpcbData], rcx; lpcbData
0x1800b9ace  lea     rax, [rdi+28h]
0x1800b9ad2  mov     rcx, [rsp+1C0h+var_168]; hKey
0x1800b9ad7  lea     rdx, aAdstate; "AdState"
0x1800b9ade  xor     r9d, r9d; lpType
0x1800b9ae1  mov     [rsp+1C0h+phkResult], rax; lpData
0x1800b9ae6  xor     r8d, r8d; lpReserved
0x1800b9ae9  call    cs:__imp_RegQueryValueExA
0x1800b9aef  cmp     [rdi+38h], r12
0x1800b9af3  jnz     loc_1800B9B83
0x1800b9af9  mov     rcx, [rsp+1C0h+var_178]; hKey
0x1800b9afe  lea     rax, [rsp+1C0h+var_190]
0x1800b9b03  mov     [rsp+1C0h+lpcbData], rax; lpcbData
0x1800b9b08  lea     r9, [rsp+1C0h+Type]; lpType
0x1800b9b0d  xor     r8d, r8d; lpReserved
0x1800b9b10  mov     [rsp+1C0h+phkResult], r12; lpData
0x1800b9b15  xor     edx, edx; lpValueName
0x1800b9b17  call    cs:__imp_RegQueryValueExA
0x1800b9b1d  test    eax, eax
0x1800b9b1f  jnz     short loc_1800B9B83
0x1800b9b21  mov     ecx, [rsp+1C0h+var_190]; Size
0x1800b9b25  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b9b2a  mov     [rdi+38h], rax
0x1800b9b2e  test    rax, rax
0x1800b9b31  jnz     short loc_1800B9B3D
0x1800b9b33  mov     ebx, 8007000Eh
0x1800b9b38  jmp     loc_1800B9D02
0x1800b9b3d  lea     rcx, [rsp+1C0h+var_190]
0x1800b9b42  xor     r8d, r8d; lpReserved
0x1800b9b45  mov     [rsp+1C0h+lpcbData], rcx; lpcbData
0x1800b9b4a  lea     r9, [rsp+1C0h+Type]; lpType
0x1800b9b4f  mov     rcx, [rsp+1C0h+var_178]; hKey
0x1800b9b54  xor     edx, edx; lpValueName
0x1800b9b56  mov     [rsp+1C0h+phkResult], rax; lpData
0x1800b9b5b  call    cs:__imp_RegQueryValueExA
0x1800b9b61  test    eax, eax
0x1800b9b63  jz      short loc_1800B9B83
0x1800b9b65  call    cs:__imp_GetLastError
0x1800b9b6b  mov     ebx, eax
0x1800b9b6d  test    eax, eax
0x1800b9b6f  jle     loc_1800B9D02
0x1800b9b75  movzx   ebx, ax
0x1800b9b78  or      ebx, 80070000h
0x1800b9b7e  jmp     loc_1800B9D02
0x1800b9b83  cmp     [rdi+48h], r12
0x1800b9b87  jnz     short loc_1800B9BFD
0x1800b9b89  mov     rcx, [rsp+1C0h+var_188]; hKey
0x1800b9b8e  lea     rax, [rsp+1C0h+var_190]
0x1800b9b93  mov     [rsp+1C0h+lpcbData], rax; lpcbData
0x1800b9b98  lea     r9, [rsp+1C0h+Type]; lpType
0x1800b9b9d  xor     r8d, r8d; lpReserved
0x1800b9ba0  mov     [rsp+1C0h+phkResult], r12; lpData
0x1800b9ba5  lea     rdx, aAbstract_0; "Abstract"
0x1800b9bac  call    cs:__imp_RegQueryValueExA
0x1800b9bb2  test    eax, eax
0x1800b9bb4  jnz     short loc_1800B9BFD
0x1800b9bb6  mov     ecx, [rsp+1C0h+var_190]; Size
0x1800b9bba  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b9bbf  mov     [rdi+48h], rax
0x1800b9bc3  test    rax, rax
0x1800b9bc6  jz      loc_1800B9B33
0x1800b9bcc  lea     rcx, [rsp+1C0h+var_190]
0x1800b9bd1  xor     r8d, r8d; lpReserved
0x1800b9bd4  mov     [rsp+1C0h+lpcbData], rcx; lpcbData
0x1800b9bd9  lea     r9, [rsp+1C0h+Type]; lpType
0x1800b9bde  mov     rcx, [rsp+1C0h+var_188]; hKey
0x1800b9be3  lea     rdx, aAbstract_0; "Abstract"
0x1800b9bea  mov     [rsp+1C0h+phkResult], rax; lpData
0x1800b9bef  call    cs:__imp_RegQueryValueExA
0x1800b9bf5  test    eax, eax
0x1800b9bf7  jnz     loc_1800B9B65
0x1800b9bfd  cmp     [rdi+50h], r12
0x1800b9c01  jnz     short loc_1800B9C77
0x1800b9c03  mov     rcx, [rsp+1C0h+var_188]; hKey
0x1800b9c08  lea     rax, [rsp+1C0h+var_190]
0x1800b9c0d  mov     [rsp+1C0h+lpcbData], rax; lpcbData
0x1800b9c12  lea     r9, [rsp+1C0h+Type]; lpType
0x1800b9c17  xor     r8d, r8d; lpReserved
0x1800b9c1a  mov     [rsp+1C0h+phkResult], r12; lpData
0x1800b9c1f  lea     rdx, aHref; "HREF"
0x1800b9c26  call    cs:__imp_RegQueryValueExA
0x1800b9c2c  test    eax, eax
0x1800b9c2e  jnz     short loc_1800B9C77
0x1800b9c30  mov     ecx, [rsp+1C0h+var_190]; Size
0x1800b9c34  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b9c39  mov     [rdi+50h], rax
0x1800b9c3d  test    rax, rax
0x1800b9c40  jz      loc_1800B9B33
0x1800b9c46  lea     rcx, [rsp+1C0h+var_190]
0x1800b9c4b  xor     r8d, r8d; lpReserved
0x1800b9c4e  mov     [rsp+1C0h+lpcbData], rcx; lpcbData
0x1800b9c53  lea     r9, [rsp+1C0h+Type]; lpType
0x1800b9c58  mov     rcx, [rsp+1C0h+var_188]; hKey
0x1800b9c5d  lea     rdx, aHref; "HREF"
0x1800b9c64  mov     [rsp+1C0h+phkResult], rax; lpData
0x1800b9c69  call    cs:__imp_RegQueryValueExA
0x1800b9c6f  test    eax, eax
0x1800b9c71  jnz     loc_1800B9B65
0x1800b9c77  mov     rcx, [rsp+1C0h+var_188]; hKey
0x1800b9c7c  lea     rax, [rsp+1C0h+var_190]
0x1800b9c81  mov     [rsp+1C0h+lpcbData], rax; lpcbData
0x1800b9c86  lea     r9, [rsp+1C0h+Type]; lpType
0x1800b9c8b  lea     rax, [rsp+1C0h+var_150]
0x1800b9c90  mov     [rsp+1C0h+var_190], 104h
0x1800b9c98  xor     r8d, r8d; lpReserved
0x1800b9c9b  mov     [rsp+1C0h+phkResult], rax; lpData
0x1800b9ca0  xor     edx, edx; lpValueName
0x1800b9ca2  call    cs:__imp_RegQueryValueExA
0x1800b9ca8  test    eax, eax
0x1800b9caa  jnz     loc_1800B99C9
0x1800b9cb0  lea     r8, [rsp+1C0h+var_16C]; unsigned int *
0x1800b9cb5  lea     rdx, [rsp+1C0h+var_170]; unsigned int *
0x1800b9cba  lea     rcx, [rsp+1C0h+var_150]; lpString1
0x1800b9cbf  call    ?GetVersionFromString@@YAJPEBDPEAK1D@Z; GetVersionFromString(char const *,ulong *,ulong *,char)
0x1800b9cc4  test    eax, eax
0x1800b9cc6  js      loc_1800B99C9
0x1800b9ccc  mov     eax, [rdi+1Ch]
0x1800b9ccf  or      eax, [rdi+18h]
0x1800b9cd2  mov     edx, [rsp+1C0h+var_170]; unsigned int
0x1800b9cd6  mov     r8d, [rsp+1C0h+var_16C]; unsigned int
0x1800b9cdb  jnz     short loc_1800B9CE4
0x1800b9cdd  mov     [rdi+18h], edx
0x1800b9ce0  mov     [rdi+1Ch], r8d
0x1800b9ce4  mov     rcx, rdi; this
0x1800b9ce7  call    ?IsCDFNewerVersion@CSoftDist@@AEAAHKK@Z; CSoftDist::IsCDFNewerVersion(ulong,ulong)
0x1800b9cec  test    eax, eax
0x1800b9cee  mov     ebx, r12d
0x1800b9cf1  setnz   bl
0x1800b9cf4  jmp     short loc_1800B9D02
0x1800b9cf6  mov     rsi, [rsp+1C0h+lpSubKey]
0x1800b9cfb  jmp     short loc_1800B9D02
0x1800b9cfd  mov     ebx, 80070057h
0x1800b9d02  test    rsi, rsi
0x1800b9d05  jz      short loc_1800B9D0F
0x1800b9d07  mov     rcx, rsi; void *
0x1800b9d0a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800b9d0f  mov     rcx, [rsp+1C0h+var_188]; hKey
0x1800b9d14  test    rcx, rcx
0x1800b9d17  jz      short loc_1800B9D24
0x1800b9d19  call    cs:__imp_RegCloseKey
0x1800b9d1f  mov     [rsp+1C0h+var_188], r12
0x1800b9d24  mov     rcx, [rsp+1C0h+var_168]; hKey
0x1800b9d29  test    rcx, rcx
0x1800b9d2c  jz      short loc_1800B9D39
0x1800b9d2e  call    cs:__imp_RegCloseKey
0x1800b9d34  mov     [rsp+1C0h+var_168], r12
0x1800b9d39  mov     rcx, [rsp+1C0h+hKey]; hKey
0x1800b9d3e  test    rcx, rcx
0x1800b9d41  jz      short loc_1800B9D4E
0x1800b9d43  call    cs:__imp_RegCloseKey
0x1800b9d49  mov     [rsp+1C0h+hKey], r12
0x1800b9d4e  mov     rcx, [rsp+1C0h+var_178]; hKey
0x1800b9d53  test    rcx, rcx
0x1800b9d56  jz      short loc_1800B9D5E
0x1800b9d58  call    cs:__imp_RegCloseKey
0x1800b9d5e  mov     eax, ebx
0x1800b9d60  mov     rcx, [rbp+0C0h+var_40]
0x1800b9d67  xor     rcx, rsp; StackCookie
0x1800b9d6a  call    __security_check_cookie
0x1800b9d6f  mov     rbx, [rsp+1C0h+arg_18]
0x1800b9d77  add     rsp, 190h
0x1800b9d7e  pop     r15
0x1800b9d80  pop     r14
0x1800b9d82  pop     r13
0x1800b9d84  pop     r12
0x1800b9d86  pop     rdi
0x1800b9d87  pop     rsi
0x1800b9d88  pop     rbp
0x1800b9d89  retn
```
