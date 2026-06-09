# FilterReferencedTypeInfos

- ea: `0x180056cf8`
- end: `0x18005710b`
- name: `FilterReferencedTypeInfos`
- size: `1043`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18003fe6c`

## callees

- `0x1800228e0`
- `0x180048808`
- `0x18004d900`
- `0x180056cf8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180056dc9`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180056e7b`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180056f80`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180056dc9`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180056e7b`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180056f80`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x180056d8a`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x180056e3d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x180056f43`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x180056d8a`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x180056e3d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x180056f43`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180056fe2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180056fe2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005707b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180057088`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180057097`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800570ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800570c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800570d2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005707b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180057088`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180057097`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800570ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800570c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800570d2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180056df1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180056ef9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180056fa9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180056df1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180056ef9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180056fa9`

## pseudocode

```c
__int64 __fastcall FilterReferencedTypeInfos(HKEY hKey, __int64 a2, unsigned int a3)
{
  DWORD v3; // edi
  int RegGuidsFromTypeLib; // ebx
  DWORD v8; // r14d
  DWORD i; // esi
  WCHAR *v10; // rax
  int v11; // ecx
  int v12; // edx
  WCHAR *v13; // rax
  int v14; // ecx
  int v15; // edx
  unsigned int v16; // r11d
  unsigned int v17; // r10d
  __int64 j; // r8
  unsigned int k; // edx
  __int64 v20; // rcx
  __int64 v21; // rax
  DWORD cchName; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKeya; // [rsp+68h] [rbp-98h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-90h] BYREF
  DWORD cSubKeys; // [rsp+78h] [rbp-88h] BYREF
  DWORD lpcSubKeys; // [rsp+7Ch] [rbp-84h] BYREF
  DWORD v28; // [rsp+80h] [rbp-80h] BYREF
  DWORD pcbData; // [rsp+84h] [rbp-7Ch] BYREF
  unsigned int v30; // [rsp+88h] [rbp-78h] BYREF
  HKEY hkey; // [rsp+90h] [rbp-70h] BYREF
  __int64 v32; // [rsp+98h] [rbp-68h] BYREF
  WCHAR SubKey[12]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR Name[12]; // [rsp+B8h] [rbp-48h] BYREF
  WCHAR v35[16]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE pvData[528]; // [rsp+F0h] [rbp-10h] BYREF

  v3 = 0;
  RegGuidsFromTypeLib = 0;
  phkResult = 0;
  hKeya = 0;
  hkey = 0;
  v32 = 0;
  v30 = 0;
  cchName = 0;
  pcbData = 0;
  cSubKeys = 0;
  RegQueryInfoKeyA(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
  v8 = 0;
LABEL_2:
  if ( v8 < cSubKeys )
  {
    cchName = 10;
    if ( RegEnumKeyExW(hKey, v8, Name, &cchName, 0, 0, 0, 0) || RegOpenKeyExW(hKey, Name, 0, 0x2000000u, &phkResult) )
    {
      return (unsigned int)-2147319780;
    }
    else
    {
      lpcSubKeys = 0;
      RegQueryInfoKeyA(phkResult, 0, 0, 0, &lpcSubKeys, 0, 0, 0, 0, 0, 0, 0);
      for ( i = 0; ; ++i )
      {
        if ( i >= lpcSubKeys )
        {
          RegCloseKey(phkResult);
          ++v8;
          goto LABEL_2;
        }
        cchName = 11;
        if ( RegEnumKeyExW(phkResult, i, SubKey, &cchName, 0, 0, 0, 0) )
          goto LABEL_43;
        v10 = SubKey;
        do
        {
          v11 = *(WCHAR *)((char *)v10 + (char *)L"HELPDIR" - (char *)SubKey);
          v12 = *v10 - v11;
          if ( v12 )
            break;
          ++v10;
        }
        while ( v11 );
        if ( v12 )
        {
          v13 = SubKey;
          do
          {
            v14 = *(WCHAR *)((char *)v13 + (char *)L"FLAGS" - (char *)SubKey);
            v15 = *v13 - v14;
            if ( v15 )
              break;
            ++v13;
          }
          while ( v14 );
          if ( v15 )
            break;
        }
LABEL_37:
        ;
      }
      if ( RegOpenKeyExW(phkResult, SubKey, 0, 0x2000000u, &hKeya) )
      {
LABEL_43:
        RegGuidsFromTypeLib = -2147319780;
        goto LABEL_44;
      }
      v28 = 0;
      RegQueryInfoKeyA(hKeya, 0, 0, 0, &v28, 0, 0, 0, 0, 0, 0, 0);
      while ( 1 )
      {
        if ( v3 >= v28 )
        {
          RegCloseKey(hKeya);
          v3 = 0;
          goto LABEL_37;
        }
        cchName = 11;
        if ( RegEnumKeyExW(hKeya, v3, v35, &cchName, 0, 0, 0, 0) || RegOpenKeyExW(hKeya, v35, 0, 0x2000000u, &hkey) )
          break;
        pcbData = 520;
        if ( RegGetValueW(hkey, 0, 0, 6u, 0, pvData, &pcbData) )
        {
          RegGuidsFromTypeLib = -2147319780;
LABEL_40:
          RegCloseKey(hkey);
          goto LABEL_42;
        }
        RegGuidsFromTypeLib = GetRegGuidsFromTypeLib(pvData, &v32, &v30);
        if ( RegGuidsFromTypeLib < 0 )
          goto LABEL_40;
        v16 = v30;
        v17 = 0;
        for ( j = v32; v17 < v16; ++v17 )
        {
          for ( k = 0; k < a3; ++k )
          {
            v20 = 16LL * k;
            if ( *(_DWORD *)(j + 16LL * v17) == *(_DWORD *)(v20 + a2) )
            {
              v21 = *(_QWORD *)(j + 16LL * v17) - *(_QWORD *)(v20 + a2);
              if ( !v21 )
                v21 = *(_QWORD *)(j + 16LL * v17 + 8) - *(_QWORD *)(v20 + a2 + 8);
              if ( !v21 )
              {
                *(GUID *)(v20 + a2) = GUID_NULL;
                break;
              }
            }
          }
        }
        if ( j )
          MemFree(j);
        RegCloseKey(hkey);
        ++v3;
      }
      RegGuidsFromTypeLib = -2147319780;
LABEL_42:
      RegCloseKey(hKeya);
LABEL_44:
      RegCloseKey(phkResult);
    }
  }
  return (unsigned int)RegGuidsFromTypeLib;
}

```

## disassembly

```asm
0x180056cf8  mov     [rsp-8+arg_10], rbx
0x180056cfd  push    rbp
0x180056cfe  push    rsi
0x180056cff  push    rdi
0x180056d00  push    r12
0x180056d02  push    r13
0x180056d04  push    r14
0x180056d06  push    r15
0x180056d08  lea     rbp, [rsp-210h]
0x180056d10  sub     rsp, 310h
0x180056d17  mov     rax, cs:__security_cookie
0x180056d1e  xor     rax, rsp
0x180056d21  mov     [rbp+240h+var_40], rax
0x180056d28  xor     edi, edi
0x180056d2a  lea     rax, [rsp+340h+cSubKeys]
0x180056d2f  mov     [rsp+340h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x180056d34  mov     r13d, r8d
0x180056d37  mov     [rsp+340h+lpcbSecurityDescriptor], rdi; lpcbSecurityDescriptor
0x180056d3c  mov     r12, rdx
0x180056d3f  mov     [rsp+340h+lpcbMaxValueLen], rdi; lpcbMaxValueLen
0x180056d44  xor     r9d, r9d; lpReserved
0x180056d47  mov     [rsp+340h+lpcbMaxValueNameLen], rdi; lpcbMaxValueNameLen
0x180056d4c  xor     r8d, r8d; lpcchClass
0x180056d4f  mov     [rsp+340h+lpcValues], rdi; lpcValues
0x180056d54  xor     edx, edx; lpClass
0x180056d56  mov     [rsp+340h+lpcbMaxClassLen], rdi; lpcbMaxClassLen
0x180056d5b  mov     r15, rcx
0x180056d5e  mov     [rsp+340h+lpcbMaxSubKeyLen], rdi; lpcbMaxSubKeyLen
0x180056d63  mov     ebx, edi
0x180056d65  mov     [rsp+340h+lpcSubKeys], rax; lpcSubKeys
0x180056d6a  mov     [rsp+340h+phkResult], rdi
0x180056d6f  mov     [rsp+340h+hKey], rdi
0x180056d74  mov     [rbp+240h+hkey], rdi
0x180056d78  mov     [rbp+240h+var_2A8], rdi
0x180056d7c  mov     [rbp+240h+var_2B8], edi
0x180056d7f  mov     [rsp+340h+cchName], edi
0x180056d83  mov     [rbp+240h+pcbData], edi
0x180056d86  mov     [rsp+340h+cSubKeys], edi
0x180056d8a  call    cs:__imp_RegQueryInfoKeyA
0x180056d90  mov     r14d, edi
0x180056d93  cmp     r14d, [rsp+340h+cSubKeys]
0x180056d98  jnb     loc_1800570DF
0x180056d9e  mov     [rsp+340h+lpcValues], rdi; lpftLastWriteTime
0x180056da3  lea     r9, [rsp+340h+cchName]; lpcchName
0x180056da8  mov     [rsp+340h+lpcbMaxClassLen], rdi; lpcchClass
0x180056dad  lea     r8, [rbp+240h+Name]; lpName
0x180056db1  mov     [rsp+340h+lpcbMaxSubKeyLen], rdi; lpClass
0x180056db6  mov     edx, r14d; dwIndex
0x180056db9  mov     rcx, r15; hKey
0x180056dbc  mov     [rsp+340h+lpcSubKeys], rdi; lpReserved
0x180056dc1  mov     [rsp+340h+cchName], 0Ah
0x180056dc9  call    cs:__imp_RegEnumKeyExW
0x180056dcf  test    eax, eax
0x180056dd1  jnz     loc_1800570DA
0x180056dd7  lea     rax, [rsp+340h+phkResult]
0x180056ddc  mov     r9d, 2000000h; samDesired
0x180056de2  xor     r8d, r8d; ulOptions
0x180056de5  mov     [rsp+340h+lpcSubKeys], rax; phkResult
0x180056dea  lea     rdx, [rbp+240h+Name]; lpSubKey
0x180056dee  mov     rcx, r15; hKey
0x180056df1  call    cs:__imp_RegOpenKeyExW
0x180056df7  test    eax, eax
0x180056df9  jnz     loc_1800570DA
0x180056dff  mov     rcx, [rsp+340h+phkResult]; hKey
0x180056e04  lea     rax, [rsp+340h+var_2C4]
0x180056e09  mov     [rsp+340h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x180056e0e  xor     r9d, r9d; lpReserved
0x180056e11  mov     [rsp+340h+lpcbSecurityDescriptor], rdi; lpcbSecurityDescriptor
0x180056e16  xor     r8d, r8d; lpcchClass
0x180056e19  mov     [rsp+340h+lpcbMaxValueLen], rdi; lpcbMaxValueLen
0x180056e1e  xor     edx, edx; lpClass
0x180056e20  mov     [rsp+340h+lpcbMaxValueNameLen], rdi; lpcbMaxValueNameLen
0x180056e25  mov     [rsp+340h+lpcValues], rdi; lpcValues
0x180056e2a  mov     [rsp+340h+lpcbMaxClassLen], rdi; lpcbMaxClassLen
0x180056e2f  mov     [rsp+340h+lpcbMaxSubKeyLen], rdi; lpcbMaxSubKeyLen
0x180056e34  mov     [rsp+340h+lpcSubKeys], rax; lpcSubKeys
0x180056e39  mov     [rsp+340h+var_2C4], edi
0x180056e3d  call    cs:__imp_RegQueryInfoKeyA
0x180056e43  mov     esi, edi
0x180056e45  mov     rcx, [rsp+340h+phkResult]; hKey
0x180056e4a  cmp     esi, [rsp+340h+var_2C4]
0x180056e4e  jnb     loc_180057097
0x180056e54  mov     [rsp+340h+lpcValues], rdi; lpftLastWriteTime
0x180056e59  lea     r9, [rsp+340h+cchName]; lpcchName
0x180056e5e  mov     [rsp+340h+lpcbMaxClassLen], rdi; lpcchClass
0x180056e63  lea     r8, [rbp+240h+SubKey]; lpName
0x180056e67  mov     [rsp+340h+lpcbMaxSubKeyLen], rdi; lpClass
0x180056e6c  mov     edx, esi; dwIndex
0x180056e6e  mov     [rsp+340h+lpcSubKeys], rdi; lpReserved
0x180056e73  mov     [rsp+340h+cchName], 0Bh
0x180056e7b  call    cs:__imp_RegEnumKeyExW
0x180056e81  test    eax, eax
0x180056e83  jnz     loc_1800570C8
0x180056e89  lea     rax, [rbp+240h+SubKey]
0x180056e8d  lea     r8, ?HELPDIR@Constants@Catalog@Com@@3QBGB; "HELPDIR"
0x180056e94  sub     r8, rax
0x180056e97  movzx   edx, word ptr [rax]
0x180056e9a  movzx   ecx, word ptr [rax+r8]
0x180056e9f  sub     edx, ecx
0x180056ea1  jnz     short loc_180056EAB
0x180056ea3  add     rax, 2
0x180056ea7  test    ecx, ecx
0x180056ea9  jnz     short loc_180056E97
0x180056eab  test    edx, edx
0x180056ead  jz      loc_180057090
0x180056eb3  lea     rax, [rbp+240h+SubKey]
0x180056eb7  lea     r8, ?FLAGS@Constants@Catalog@Com@@3QBGB; "FLAGS"
0x180056ebe  sub     r8, rax
0x180056ec1  movzx   edx, word ptr [rax]
0x180056ec4  movzx   ecx, word ptr [rax+r8]
0x180056ec9  sub     edx, ecx
0x180056ecb  jnz     short loc_180056ED5
0x180056ecd  add     rax, 2
0x180056ed1  test    ecx, ecx
0x180056ed3  jnz     short loc_180056EC1
0x180056ed5  test    edx, edx
0x180056ed7  jz      loc_180057090
0x180056edd  mov     rcx, [rsp+340h+phkResult]; hKey
0x180056ee2  lea     rax, [rsp+340h+hKey]
0x180056ee7  mov     r9d, 2000000h; samDesired
0x180056eed  mov     [rsp+340h+lpcSubKeys], rax; phkResult
0x180056ef2  xor     r8d, r8d; ulOptions
0x180056ef5  lea     rdx, [rbp+240h+SubKey]; lpSubKey
0x180056ef9  call    cs:__imp_RegOpenKeyExW
0x180056eff  test    eax, eax
0x180056f01  jnz     loc_1800570C8
0x180056f07  mov     rcx, [rsp+340h+hKey]; hKey
0x180056f0c  lea     rax, [rbp+240h+var_2C0]
0x180056f10  mov     [rsp+340h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x180056f15  xor     r9d, r9d; lpReserved
0x180056f18  mov     [rsp+340h+lpcbSecurityDescriptor], rdi; lpcbSecurityDescriptor
0x180056f1d  xor     r8d, r8d; lpcchClass
0x180056f20  mov     [rsp+340h+lpcbMaxValueLen], rdi; lpcbMaxValueLen
0x180056f25  xor     edx, edx; lpClass
0x180056f27  mov     [rsp+340h+lpcbMaxValueNameLen], rdi; lpcbMaxValueNameLen
0x180056f2c  mov     [rsp+340h+lpcValues], rdi; lpcValues
0x180056f31  mov     [rsp+340h+lpcbMaxClassLen], rdi; lpcbMaxClassLen
0x180056f36  mov     [rsp+340h+lpcbMaxSubKeyLen], rdi; lpcbMaxSubKeyLen
0x180056f3b  mov     [rsp+340h+lpcSubKeys], rax; lpcSubKeys
0x180056f40  mov     [rbp+240h+var_2C0], edi
0x180056f43  call    cs:__imp_RegQueryInfoKeyA
0x180056f49  mov     rcx, [rsp+340h+hKey]; hKey
0x180056f4e  cmp     edi, [rbp+240h+var_2C0]
0x180056f51  jnb     loc_180057088
0x180056f57  xor     ebx, ebx
0x180056f59  mov     [rsp+340h+cchName], 0Bh
0x180056f61  mov     [rsp+340h+lpcValues], rbx; lpftLastWriteTime
0x180056f66  lea     r9, [rsp+340h+cchName]; lpcchName
0x180056f6b  mov     [rsp+340h+lpcbMaxClassLen], rbx; lpcchClass
0x180056f70  lea     r8, [rbp+240h+var_270]; lpName
0x180056f74  mov     [rsp+340h+lpcbMaxSubKeyLen], rbx; lpClass
0x180056f79  mov     edx, edi; dwIndex
0x180056f7b  mov     [rsp+340h+lpcSubKeys], rbx; lpReserved
0x180056f80  call    cs:__imp_RegEnumKeyExW
0x180056f86  test    eax, eax
0x180056f88  jnz     loc_1800570B6
0x180056f8e  mov     rcx, [rsp+340h+hKey]; hKey
0x180056f93  lea     rax, [rbp+240h+hkey]
0x180056f97  mov     r9d, 2000000h; samDesired
0x180056f9d  mov     [rsp+340h+lpcSubKeys], rax; phkResult
0x180056fa2  xor     r8d, r8d; ulOptions
0x180056fa5  lea     rdx, [rbp+240h+var_270]; lpSubKey
0x180056fa9  call    cs:__imp_RegOpenKeyExW
0x180056faf  test    eax, eax
0x180056fb1  jnz     loc_1800570B6
0x180056fb7  mov     rcx, [rbp+240h+hkey]; hkey
0x180056fbb  lea     rax, [rbp+240h+pcbData]
0x180056fbf  mov     [rsp+340h+lpcbMaxClassLen], rax; pcbData
0x180056fc4  lea     r9d, [rbx+6]; dwFlags
0x180056fc8  lea     rax, [rbp+240h+pvData]
0x180056fcc  mov     [rbp+240h+pcbData], 208h
0x180056fd3  mov     [rsp+340h+lpcbMaxSubKeyLen], rax; pvData
0x180056fd8  xor     r8d, r8d; lpValue
0x180056fdb  xor     edx, edx; lpSubKey
0x180056fdd  mov     [rsp+340h+lpcSubKeys], rbx; pdwType
0x180056fe2  call    cs:__imp_RegGetValueW
0x180056fe8  test    eax, eax
0x180056fea  jnz     loc_1800570A5
0x180056ff0  lea     r8, [rbp+240h+var_2B8]
0x180056ff4  lea     rdx, [rbp+240h+var_2A8]
0x180056ff8  lea     rcx, [rbp+240h+pvData]
0x180056ffc  call    GetRegGuidsFromTypeLib
0x180057001  mov     ebx, eax
0x180057003  test    eax, eax
0x180057005  js      loc_1800570AA
0x18005700b  mov     r11d, [rbp+240h+var_2B8]
0x18005700f  xor     r10d, r10d
0x180057012  mov     r8, [rbp+240h+var_2A8]
0x180057016  test    r11d, r11d
0x180057019  jz      short loc_18005706A
0x18005701b  xor     edx, edx
0x18005701d  mov     r9d, r10d
0x180057020  add     r9, r9
0x180057023  cmp     edx, r13d
0x180057026  jnb     short loc_180057062
0x180057028  mov     ecx, edx
0x18005702a  shl     rcx, 4
0x18005702e  mov     eax, [rcx+r12]
0x180057032  cmp     [r8+r9*8], eax
0x180057036  jnz     short loc_180057051
0x180057038  mov     rax, [r8+r9*8]
0x18005703c  sub     rax, [rcx+r12]
0x180057040  jnz     short loc_18005704C
0x180057042  mov     rax, [r8+r9*8+8]
0x180057047  sub     rax, [rcx+r12+8]
0x18005704c  test    rax, rax
0x18005704f  jz      short loc_180057055
0x180057051  inc     edx
0x180057053  jmp     short loc_180057023
0x180057055  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18005705c  movdqu  xmmword ptr [rcx+r12], xmm0
0x180057062  inc     r10d
0x180057065  cmp     r10d, r11d
0x180057068  jb      short loc_18005701B
0x18005706a  test    r8, r8
0x18005706d  jz      short loc_180057077
0x18005706f  mov     rcx, r8
0x180057072  call    MemFree
0x180057077  mov     rcx, [rbp+240h+hkey]; hKey
0x18005707b  call    cs:__imp_RegCloseKey
0x180057081  inc     edi
0x180057083  jmp     loc_180056F49
0x180057088  call    cs:__imp_RegCloseKey
0x18005708e  xor     edi, edi
0x180057090  inc     esi
0x180057092  jmp     loc_180056E45
0x180057097  call    cs:__imp_RegCloseKey
0x18005709d  inc     r14d
0x1800570a0  jmp     loc_180056D93
0x1800570a5  mov     ebx, 8002801Ch
0x1800570aa  mov     rcx, [rbp+240h+hkey]; hKey
0x1800570ae  call    cs:__imp_RegCloseKey
0x1800570b4  jmp     short loc_1800570BB
0x1800570b6  mov     ebx, 8002801Ch
0x1800570bb  mov     rcx, [rsp+340h+hKey]; hKey
0x1800570c0  call    cs:__imp_RegCloseKey
0x1800570c6  jmp     short loc_1800570CD
0x1800570c8  mov     ebx, 8002801Ch
0x1800570cd  mov     rcx, [rsp+340h+phkResult]; hKey
0x1800570d2  call    cs:__imp_RegCloseKey
0x1800570d8  jmp     short loc_1800570DF
0x1800570da  mov     ebx, 8002801Ch
0x1800570df  mov     eax, ebx
0x1800570e1  mov     rcx, [rbp+240h+var_40]
0x1800570e8  xor     rcx, rsp; StackCookie
0x1800570eb  call    __security_check_cookie
0x1800570f0  mov     rbx, [rsp+340h+arg_10]
0x1800570f8  add     rsp, 310h
0x1800570ff  pop     r15
0x180057101  pop     r14
0x180057103  pop     r13
0x180057105  pop     r12
0x180057107  pop     rdi
0x180057108  pop     rsi
0x180057109  pop     rbp
0x18005710a  retn
```
