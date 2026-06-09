# IsDistUnitLocallyInstalledInDistNode(HKEY__ *,char const *,ulong,ulong,CLocalComponentInfo *,char *,int *,ulong,int *)

- ea: `0x180076b88`
- end: `0x180076eea`
- name: `?IsDistUnitLocallyInstalledInDistNode@@YAJPEAUHKEY__@@PEBDKKPEAVCLocalComponentInfo@@PEADPEAHK4@Z`
- size: `866`
- prototype: `int(HKEY, const char *, unsigned int, unsigned int, struct CLocalComponentInfo *, char *, int *, unsigned int, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800761f0`

## callees

- `0x180030880`
- `0x180076078`
- `0x18007679c`
- `0x180076b88`
- `0x180090b64`
- `0x18009e830`
- `0x1800c78ac`
- `0x18011baa0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180076c09`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180076c75`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180076cae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180076dfa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180076c09`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180076c75`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180076cae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180076dfa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180076e88`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180076e98`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180076ea8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180076eb8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180076e88`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180076e98`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180076ea8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180076eb8`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueA` at `0x180076ce7`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueA` at `0x180076e43`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueA` at `0x180076ce7`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueA` at `0x180076e43`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesA` at `0x180076e5c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesA` at `0x180076e5c`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180076d40`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180076d40`

## pseudocode

```c
__int64 __fastcall IsDistUnitLocallyInstalledInDistNode(
        HKEY a1,
        const char *a2,
        unsigned int a3,
        unsigned int a4,
        struct CLocalComponentInfo *a5,
        char *a6,
        int *a7,
        unsigned int a8,
        int *a9)
{
  LSTATUS v11; // eax
  signed int v12; // ebx
  DWORD v13; // r14d
  OLECHAR *v14; // rdi
  DWORD v15; // edi
  DWORD cchValueName; // [rsp+50h] [rbp-B0h] BYREF
  DWORD v18; // [rsp+54h] [rbp-ACh] BYREF
  LPCOLESTR lpsz; // [rsp+58h] [rbp-A8h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  HKEY v22; // [rsp+70h] [rbp-90h] BYREF
  HKEY v23; // [rsp+78h] [rbp-88h] BYREF
  GUID pclsid; // [rsp+80h] [rbp-80h] BYREF
  CHAR v25[320]; // [rsp+90h] [rbp-70h] BYREF
  CHAR ValueName[272]; // [rsp+1D0h] [rbp+D0h] BYREF

  v22 = 0;
  *a9 = 0;
  hKey = 0;
  phkResult = 0;
  v23 = 0;
  cchValueName = 260;
  v11 = RegOpenKeyExA(a1, a2, 0, 0x20019u, &hKey);
  v12 = v11;
  if ( v11 )
  {
    if ( v11 > 0 )
      v12 = (unsigned __int16)v11 | 0x80070000;
    goto LABEL_35;
  }
  v12 = CheckInstalledVersionHint(hKey, a5, a3, a4);
  if ( v12 == 1 )
  {
    *a9 = 1;
LABEL_6:
    if ( a3 != -1 || a4 != -1 )
      goto LABEL_8;
    goto LABEL_9;
  }
  if ( v12 )
  {
    if ( v12 < 0 )
    {
LABEL_8:
      v12 = 1;
      goto LABEL_35;
    }
    goto LABEL_6;
  }
LABEL_9:
  if ( !RegOpenKeyExA(hKey, "Contains", 0, 0x20019u, &phkResult) )
  {
    if ( a7 )
      *a7 = 1;
    if ( !RegOpenKeyExA(phkResult, "Distribution Units", 0, 0x20019u, &v22) )
    {
      v13 = 0;
      while ( !RegEnumValueA(v22, v13, ValueName, &cchValueName, 0, 0, 0, 0) )
      {
        CLocalComponentInfo::CLocalComponentInfo((CLocalComponentInfo *)v25);
        lpsz = 0;
        pclsid = 0;
        if ( (int)Ansi2Unicode(ValueName) < 0 )
        {
          if ( lpsz )
            operator delete((void *)lpsz);
          CLocalComponentInfo::~CLocalComponentInfo((CLocalComponentInfo *)v25);
          break;
        }
        v14 = (OLECHAR *)lpsz;
        pclsid = GUID_NULL;
        if ( lpsz )
          CLSIDFromString(lpsz, &pclsid);
        if ( (unsigned int)IsControlLocallyInstalled(0, &pclsid, v14, 0, 0, (struct CLocalComponentInfo *)v25, 0, 0, a9) )
        {
          if ( v14 )
            operator delete(v14);
          *((_QWORD *)a5 + 35) = 0;
          v12 = 1;
          CLocalComponentInfo::~CLocalComponentInfo((CLocalComponentInfo *)v25);
          goto LABEL_35;
        }
        ++v13;
        if ( v14 )
          operator delete(v14);
        cchValueName = 260;
        CLocalComponentInfo::~CLocalComponentInfo((CLocalComponentInfo *)v25);
      }
    }
    if ( !RegOpenKeyExA(phkResult, "Files", 0, 0x20019u, &v23) )
    {
      LODWORD(lpsz) = 1;
      v18 = 260;
      v15 = 0;
      while ( !RegEnumValueA(v23, v15, ValueName, &v18, 0, (LPDWORD)&lpsz, 0, 0) )
      {
        v18 = 260;
        ++v15;
        if ( GetFileAttributesA(ValueName) == -1 )
        {
          *((_QWORD *)a5 + 35) = 0;
          v12 = 1;
          break;
        }
      }
    }
  }
LABEL_35:
  if ( v22 )
    RegCloseKey(v22);
  if ( v23 )
    RegCloseKey(v23);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180076b88  mov     [rsp-8+arg_10], rbx
0x180076b8d  push    rbp
0x180076b8e  push    rsi
0x180076b8f  push    rdi
0x180076b90  push    r12
0x180076b92  push    r13
0x180076b94  push    r14
0x180076b96  push    r15
0x180076b98  lea     rbp, [rsp-1F0h]
0x180076ba0  sub     rsp, 2F0h
0x180076ba7  mov     rax, cs:__security_cookie
0x180076bae  xor     rax, rsp
0x180076bb1  mov     [rbp+220h+var_40], rax
0x180076bb8  mov     r12, [rbp+220h+arg_40]
0x180076bbf  lea     rax, [rsp+320h+hKey]
0x180076bc4  mov     rsi, [rbp+220h+arg_20]
0x180076bcb  xor     r13d, r13d
0x180076bce  mov     rdi, [rbp+220h+arg_30]
0x180076bd5  mov     r15d, r9d
0x180076bd8  mov     r14d, r8d
0x180076bdb  mov     [rsp+320h+var_2B0], r13
0x180076be0  mov     r9d, 20019h; samDesired
0x180076be6  mov     [r12], r13d
0x180076bea  xor     r8d, r8d; ulOptions
0x180076bed  mov     [rsp+320h+hKey], r13
0x180076bf2  mov     [rsp+320h+var_2C0], r13
0x180076bf7  mov     [rsp+320h+var_2A8], r13
0x180076bfc  mov     [rsp+320h+cchValueName], 104h
0x180076c04  mov     [rsp+320h+phkResult], rax; phkResult
0x180076c09  call    cs:__imp_RegOpenKeyExA
0x180076c0f  mov     ebx, eax
0x180076c11  test    eax, eax
0x180076c13  jnz     loc_180076E73
0x180076c19  mov     rcx, [rsp+320h+hKey]; hKey
0x180076c1e  mov     r9d, r15d; unsigned int
0x180076c21  mov     r8d, r14d; unsigned int
0x180076c24  mov     rdx, rsi; struct CLocalComponentInfo *
0x180076c27  call    ?CheckInstalledVersionHint@@YAJPEAUHKEY__@@PEAVCLocalComponentInfo@@KK@Z; CheckInstalledVersionHint(HKEY__ *,CLocalComponentInfo *,ulong,ulong)
0x180076c2c  mov     ebx, eax
0x180076c2e  or      ecx, 0FFFFFFFFh
0x180076c31  lea     eax, [r13+1]
0x180076c35  cmp     ebx, eax
0x180076c37  jnz     short loc_180076C3F
0x180076c39  mov     [r12], eax
0x180076c3d  jmp     short loc_180076C45
0x180076c3f  test    ebx, ebx
0x180076c41  jz      short loc_180076C56
0x180076c43  js      short loc_180076C4F
0x180076c45  cmp     r14d, ecx
0x180076c48  jnz     short loc_180076C4F
0x180076c4a  cmp     r15d, ecx
0x180076c4d  jz      short loc_180076C56
0x180076c4f  mov     ebx, eax
0x180076c51  jmp     loc_180076E7E
0x180076c56  mov     rcx, [rsp+320h+hKey]; hKey
0x180076c5b  lea     rax, [rsp+320h+var_2C0]
0x180076c60  mov     r9d, 20019h; samDesired
0x180076c66  mov     [rsp+320h+phkResult], rax; phkResult
0x180076c6b  xor     r8d, r8d; ulOptions
0x180076c6e  lea     rdx, aContains; "Contains"
0x180076c75  call    cs:__imp_RegOpenKeyExA
0x180076c7b  test    eax, eax
0x180076c7d  jnz     loc_180076E7E
0x180076c83  lea     r15d, [rax+1]
0x180076c87  test    rdi, rdi
0x180076c8a  jz      short loc_180076C8F
0x180076c8c  mov     [rdi], r15d
0x180076c8f  mov     rcx, [rsp+320h+var_2C0]; hKey
0x180076c94  lea     rax, [rsp+320h+var_2B0]
0x180076c99  mov     r9d, 20019h; samDesired
0x180076c9f  mov     [rsp+320h+phkResult], rax; phkResult
0x180076ca4  xor     r8d, r8d; ulOptions
0x180076ca7  lea     rdx, aDistributionUn; "Distribution Units"
0x180076cae  call    cs:__imp_RegOpenKeyExA
0x180076cb4  test    eax, eax
0x180076cb6  jnz     loc_180076DDB
0x180076cbc  mov     r14d, r13d
0x180076cbf  mov     rcx, [rsp+320h+var_2B0]; hKey
0x180076cc4  lea     r9, [rsp+320h+cchValueName]; lpcchValueName
0x180076cc9  mov     [rsp+320h+lpcbData], r13; lpcbData
0x180076cce  lea     r8, [rbp+220h+ValueName]; lpValueName
0x180076cd5  mov     [rsp+320h+lpData], r13; lpData
0x180076cda  mov     edx, r14d; dwIndex
0x180076cdd  mov     [rsp+320h+lpType], r13; lpType
0x180076ce2  mov     [rsp+320h+phkResult], r13; lpReserved
0x180076ce7  call    cs:__imp_RegEnumValueA
0x180076ced  test    eax, eax
0x180076cef  jnz     loc_180076DDB
0x180076cf5  lea     rcx, [rbp+220h+var_290]; this
0x180076cf9  call    ??0CLocalComponentInfo@@QEAA@XZ; CLocalComponentInfo::CLocalComponentInfo(void)
0x180076cfe  xorps   xmm0, xmm0
0x180076d01  mov     [rsp+320h+lpsz], r13
0x180076d06  lea     rdx, [rsp+320h+lpsz]
0x180076d0b  lea     rcx, [rbp+220h+ValueName]; lpMultiByteStr
0x180076d12  movups  xmmword ptr [rbp+220h+pclsid.Data1], xmm0
0x180076d16  call    Ansi2Unicode
0x180076d1b  test    eax, eax
0x180076d1d  js      loc_180076DC3
0x180076d23  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180076d2a  mov     rdi, [rsp+320h+lpsz]
0x180076d2f  movdqu  xmmword ptr [rbp+220h+pclsid.Data1], xmm0
0x180076d34  test    rdi, rdi
0x180076d37  jz      short loc_180076D46
0x180076d39  lea     rdx, [rbp+220h+pclsid]; pclsid
0x180076d3d  mov     rcx, rdi; lpsz
0x180076d40  call    cs:__imp_CLSIDFromString
0x180076d46  mov     [rsp+320h+var_2E0], r12; int *
0x180076d4b  lea     rax, [rbp+220h+var_290]
0x180076d4f  mov     dword ptr [rsp+320h+lpcbData], r13d; int
0x180076d54  lea     rdx, [rbp+220h+pclsid]; struct _GUID *
0x180076d58  mov     [rsp+320h+lpData], r13; char *
0x180076d5d  xor     r9d, r9d; unsigned int
0x180076d60  mov     [rsp+320h+lpType], rax; struct CLocalComponentInfo *
0x180076d65  mov     r8, rdi; unsigned __int16 *
0x180076d68  xor     ecx, ecx; char *
0x180076d6a  mov     dword ptr [rsp+320h+phkResult], r13d; unsigned int
0x180076d6f  call    ?IsControlLocallyInstalled@@YAJPEADQEAU_GUID@@PEBGKKPEAVCLocalComponentInfo@@0HPEAH@Z; IsControlLocallyInstalled(char *,_GUID * const,ushort const *,ulong,ulong,CLocalComponentInfo *,char *,int,int *)
0x180076d74  test    eax, eax
0x180076d76  jnz     short loc_180076D9E
0x180076d78  add     r14d, r15d
0x180076d7b  test    rdi, rdi
0x180076d7e  jz      short loc_180076D88
0x180076d80  mov     rcx, rdi; void *
0x180076d83  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180076d88  lea     rcx, [rbp+220h+var_290]; this
0x180076d8c  mov     [rsp+320h+cchValueName], 104h
0x180076d94  call    ??1CLocalComponentInfo@@QEAA@XZ; CLocalComponentInfo::~CLocalComponentInfo(void)
0x180076d99  jmp     loc_180076CBF
0x180076d9e  test    rdi, rdi
0x180076da1  jz      short loc_180076DAB
0x180076da3  mov     rcx, rdi; void *
0x180076da6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180076dab  lea     rcx, [rbp+220h+var_290]; this
0x180076daf  mov     [rsi+118h], r13
0x180076db6  mov     ebx, r15d
0x180076db9  call    ??1CLocalComponentInfo@@QEAA@XZ; CLocalComponentInfo::~CLocalComponentInfo(void)
0x180076dbe  jmp     loc_180076E7E
0x180076dc3  mov     rcx, [rsp+320h+lpsz]; void *
0x180076dc8  test    rcx, rcx
0x180076dcb  jz      short loc_180076DD2
0x180076dcd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180076dd2  lea     rcx, [rbp+220h+var_290]; this
0x180076dd6  call    ??1CLocalComponentInfo@@QEAA@XZ; CLocalComponentInfo::~CLocalComponentInfo(void)
0x180076ddb  mov     rcx, [rsp+320h+var_2C0]; hKey
0x180076de0  lea     rax, [rsp+320h+var_2A8]
0x180076de5  mov     r9d, 20019h; samDesired
0x180076deb  mov     [rsp+320h+phkResult], rax; phkResult
0x180076df0  xor     r8d, r8d; ulOptions
0x180076df3  lea     rdx, aFiles; "Files"
0x180076dfa  call    cs:__imp_RegOpenKeyExA
0x180076e00  test    eax, eax
0x180076e02  jnz     short loc_180076E7E
0x180076e04  mov     r14d, 104h
0x180076e0a  mov     dword ptr [rsp+320h+lpsz], r15d
0x180076e0f  mov     [rsp+320h+var_2CC], r14d
0x180076e14  mov     edi, r13d
0x180076e17  mov     rcx, [rsp+320h+var_2A8]; hKey
0x180076e1c  lea     rax, [rsp+320h+lpsz]
0x180076e21  mov     [rsp+320h+lpcbData], r13; lpcbData
0x180076e26  lea     r9, [rsp+320h+var_2CC]; lpcchValueName
0x180076e2b  mov     [rsp+320h+lpData], r13; lpData
0x180076e30  lea     r8, [rbp+220h+ValueName]; lpValueName
0x180076e37  mov     [rsp+320h+lpType], rax; lpType
0x180076e3c  mov     edx, edi; dwIndex
0x180076e3e  mov     [rsp+320h+phkResult], r13; lpReserved
0x180076e43  call    cs:__imp_RegEnumValueA
0x180076e49  test    eax, eax
0x180076e4b  jnz     short loc_180076E7E
0x180076e4d  lea     rcx, [rbp+220h+ValueName]; lpFileName
0x180076e54  mov     [rsp+320h+var_2CC], r14d
0x180076e59  add     edi, r15d
0x180076e5c  call    cs:__imp_GetFileAttributesA
0x180076e62  cmp     eax, 0FFFFFFFFh
0x180076e65  jnz     short loc_180076E17
0x180076e67  mov     [rsi+118h], r13
0x180076e6e  mov     ebx, r15d
0x180076e71  jmp     short loc_180076E7E
0x180076e73  jle     short loc_180076E7E
0x180076e75  movzx   ebx, ax
0x180076e78  or      ebx, 80070000h
0x180076e7e  mov     rcx, [rsp+320h+var_2B0]; hKey
0x180076e83  test    rcx, rcx
0x180076e86  jz      short loc_180076E8E
0x180076e88  call    cs:__imp_RegCloseKey
0x180076e8e  mov     rcx, [rsp+320h+var_2A8]; hKey
0x180076e93  test    rcx, rcx
0x180076e96  jz      short loc_180076E9E
0x180076e98  call    cs:__imp_RegCloseKey
0x180076e9e  mov     rcx, [rsp+320h+var_2C0]; hKey
0x180076ea3  test    rcx, rcx
0x180076ea6  jz      short loc_180076EAE
0x180076ea8  call    cs:__imp_RegCloseKey
0x180076eae  mov     rcx, [rsp+320h+hKey]; hKey
0x180076eb3  test    rcx, rcx
0x180076eb6  jz      short loc_180076EBE
0x180076eb8  call    cs:__imp_RegCloseKey
0x180076ebe  mov     eax, ebx
0x180076ec0  mov     rcx, [rbp+220h+var_40]
0x180076ec7  xor     rcx, rsp; StackCookie
0x180076eca  call    __security_check_cookie
0x180076ecf  mov     rbx, [rsp+320h+arg_10]
0x180076ed7  add     rsp, 2F0h
0x180076ede  pop     r15
0x180076ee0  pop     r14
0x180076ee2  pop     r13
0x180076ee4  pop     r12
0x180076ee6  pop     rdi
0x180076ee7  pop     rsi
0x180076ee8  pop     rbp
0x180076ee9  retn
```
