# NgcStatusStorage::Load(HKEY__ *,ushort const *)

- ea: `0x180020df8`
- end: `0x18002117b`
- name: `?Load@NgcStatusStorage@@QEAAJPEAUHKEY__@@PEBG@Z`
- size: `899`
- prototype: `__int64 __fastcall(NgcStatusStorage *__hidden this, HKEY hKey, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180020d28`

## callees

- `0x18001a100`
- `0x18001ea7c`
- `0x180020df8`
- `0x1800215e4`
- `0x18002161c`
- `0x18004a348`
- `0x18004a8ec`
- `0x18004aa08`
- `0x18004d79c`
- `0x18004d820`
- `0x18005cee0`
- `0x1800ab8a8`
- `0x1800ac598`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180020e9d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180020e9d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002112d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002112d`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180021027`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180021027`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180020f39`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180020f39`
- `RPCRT4!UuidFromStringW` at `0x180021045`
- `RPCRT4!UuidFromStringW` at `0x180021045`

## string_xrefs

- `0x180020ebb`: `%s: The registry key "%s\%s" does not exist. Noting to read.`
- `0x180020ee5`: `RegOpenKeyExW`
- `0x180020e44`: `hUserRegistry`
- `0x180020e63`: `hUserRegistry`
- `0x180021118`: `%s: There is no valid key registry.`
- `0x180020f5a`: `%s: Cannot query values of registry key "%s\%s". Win32 error code: 0x%08x.`
- `0x180020ef1`: `%s: Cannot open registry key "%s\%s". Win32 error code: 0x%08x.`
- `0x1800210ba`: `%s: Failed to read registry key "%s\%s\%s". Error code: 0x%08x.`
- `0x18002105c`: `%s: The registry key "%s" is not a valid NGC key ID. Error code: 0x%08x.`
- `0x1800210dd`: `%s: Cannot enumerate keys under registry key "%s\%s". Win32 error code: 0x%08x.`

## pseudocode

```c
__int64 __fastcall NgcStatusStorage::Load(NgcStatusStorage *this, HKEY hKey, const unsigned __int16 *a3)
{
  WCHAR *v4; // r14
  signed int v6; // edi
  LSTATUS v7; // eax
  int v8; // ebx
  const unsigned __int16 *v9; // rcx
  LSTATUS v10; // eax
  const unsigned __int16 *v11; // r8
  DWORD v12; // eax
  size_t v13; // rbx
  _BYTE *v14; // rax
  __int64 v15; // rcx
  DWORD i; // r15d
  LSTATUS v17; // eax
  const unsigned __int16 *v18; // r8
  unsigned int v19; // eax
  struct STRUCT_NGC_REG_KEY *v20; // r9
  unsigned int v21; // eax
  PHKEY phkResult; // [rsp+20h] [rbp-69h]
  const unsigned __int16 *phkResulta; // [rsp+20h] [rbp-69h]
  const unsigned __int16 *phkResultb; // [rsp+20h] [rbp-69h]
  LPDWORD lpcbMaxSubKeyLen; // [rsp+28h] [rbp-61h]
  DWORD cbMaxSubKeyLen; // [rsp+60h] [rbp-29h] BYREF
  DWORD cSubKeys; // [rsp+64h] [rbp-25h] BYREF
  HKEY hKeya; // [rsp+68h] [rbp-21h] BYREF
  DWORD cchName[4]; // [rsp+70h] [rbp-19h] BYREF
  struct _GUID v31; // [rsp+80h] [rbp-9h] BYREF
  UUID Uuid; // [rsp+90h] [rbp+7h] BYREF

  hKeya = 0;
  v4 = 0;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  NgcStatusStorage::Cleanup(this);
  if ( !hKey )
  {
    v6 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"NgcStatusStorage::Load", L"hUserRegistry");
    Logger::WriteNullOrEmptyParameterFailureEvent(L"NgcStatusStorage::Load", L"hUserRegistry");
    goto LABEL_34;
  }
  v6 = 0;
  v7 = RegOpenKeyExW(
         hKey,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC",
         0,
         0x20019u,
         &hKeya);
  v8 = v7;
  if ( v7 == 2 )
  {
    Logger::TraceVerbose(
      L"%s: The registry key \"%s\\%s\" does not exist. Noting to read.",
      L"NgcStatusStorage::Load",
      L"HKEY_CURRENT_USER",
      L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC");
    goto LABEL_34;
  }
  if ( v7 )
  {
    Logger::WriteRegistryFailureEventEx(
      v7,
      L"RegOpenKeyExW",
      L"%s\\%s",
      L"HKEY_CURRENT_USER",
      L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC");
    v9 = L"%s: Cannot open registry key \"%s\\%s\". Win32 error code: 0x%08x.";
    goto LABEL_29;
  }
  v10 = RegQueryInfoKeyW(hKeya, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  v8 = v10;
  if ( v10 )
  {
    Logger::WriteRegistryFailureEvent(v10, L"RegQueryInfoKeyW", v11, L"HKEY_CURRENT_USER", phkResulta);
    v9 = L"%s: Cannot query values of registry key \"%s\\%s\". Win32 error code: 0x%08x.";
LABEL_29:
    LODWORD(phkResult) = v8;
    Logger::TraceError(
      v9,
      L"NgcStatusStorage::Load",
      L"HKEY_CURRENT_USER",
      L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC",
      phkResult);
LABEL_30:
    if ( v8 > 0 )
      v6 = (unsigned __int16)v8 | 0x80070000;
    else
      v6 = v8;
    goto LABEL_34;
  }
  v12 = cSubKeys;
  if ( cSubKeys && cbMaxSubKeyLen )
  {
    if ( cSubKeys > 0x400 )
      v12 = 1024;
    v13 = (unsigned __int64)v12 << 6;
    v14 = MIDL_user_allocate(v13);
    *(_QWORD *)this = v14;
    if ( !v14 )
      goto LABEL_14;
    for ( ; v13; --v13 )
      *v14++ = 0;
    v15 = cbMaxSubKeyLen + 1;
    *((_QWORD *)this + 1) = 0;
    v4 = (WCHAR *)MIDL_user_allocate(2 * v15);
    if ( v4 )
    {
      for ( i = 0; i < cSubKeys && *((_QWORD *)this + 1) < 0x400u; ++i )
      {
        cchName[0] = cbMaxSubKeyLen + 1;
        v17 = RegEnumKeyExW(hKeya, i, v4, cchName, 0, 0, 0, 0);
        v8 = v17;
        if ( v17 )
        {
          Logger::WriteRegistryFailureEvent(v17, L"RegEnumKeyExW", v18, L"HKEY_CURRENT_USER", phkResultb);
          v9 = L"%s: Cannot enumerate keys under registry key \"%s\\%s\". Win32 error code: 0x%08x.";
          goto LABEL_29;
        }
        Uuid = 0;
        v19 = UuidFromStringW(v4, &Uuid);
        if ( v19 )
        {
          Logger::TraceInformation(
            L"%s: The registry key \"%s\" is not a valid NGC key ID. Error code: 0x%08x.",
            L"NgcStatusStorage::Load",
            v4,
            v19);
        }
        else
        {
          v20 = (struct STRUCT_NGC_REG_KEY *)(*(_QWORD *)this + (*((_QWORD *)this + 1) << 6));
          v31 = Uuid;
          v21 = NgcStatusStorage::ReadKey(hKeya, v4, &v31, v20);
          v8 = v21;
          if ( v21 )
          {
            LODWORD(lpcbMaxSubKeyLen) = v21;
            Logger::TraceError(
              L"%s: Failed to read registry key \"%s\\%s\\%s\". Error code: 0x%08x.",
              L"NgcStatusStorage::Load",
              L"HKEY_CURRENT_USER",
              L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkplaceJoin\\AADNGC",
              v4,
              lpcbMaxSubKeyLen);
            goto LABEL_30;
          }
          ++*((_QWORD *)this + 1);
        }
      }
    }
    else
    {
LABEL_14:
      v6 = -2147024882;
      Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"NgcStatusStorage::Load");
    }
  }
  else
  {
    Logger::TraceVerbose(L"%s: There is no valid key registry.", L"NgcStatusStorage::Load");
  }
LABEL_34:
  if ( hKeya )
  {
    RegCloseKey(hKeya);
    hKeya = 0;
  }
  SafeFree(v4);
  SafeFree(0);
  if ( v6 < 0 )
    NgcStatusStorage::Cleanup(this);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180020df8  mov     [rsp-8+arg_10], rbx
0x180020dfd  push    rbp
0x180020dfe  push    rsi
0x180020dff  push    rdi
0x180020e00  push    r12
0x180020e02  push    r13
0x180020e04  push    r14
0x180020e06  push    r15
0x180020e08  lea     rbp, [rsp-27h]
0x180020e0d  sub     rsp, 0B0h
0x180020e14  mov     rax, cs:__security_cookie
0x180020e1b  xor     rax, rsp
0x180020e1e  mov     [rbp+57h+var_40], rax
0x180020e22  xor     r12d, r12d
0x180020e25  mov     rbx, rdx
0x180020e28  mov     [rbp+57h+hKey], r12
0x180020e2c  mov     r14d, r12d
0x180020e2f  mov     [rbp+57h+cSubKeys], r12d
0x180020e33  mov     rsi, rcx
0x180020e36  mov     [rbp+57h+cbMaxSubKeyLen], r12d
0x180020e3a  call    ?Cleanup@NgcStatusStorage@@QEAAXXZ; NgcStatusStorage::Cleanup(void)
0x180020e3f  test    rbx, rbx
0x180020e42  jnz     short loc_180020E7B
0x180020e44  lea     r8, aHuserregistry; "hUserRegistry"
0x180020e4b  mov     edi, 80070057h
0x180020e50  lea     rdx, aNgcstatusstora; "NgcStatusStorage::Load"
0x180020e57  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x180020e5e  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180020e63  lea     rdx, aHuserregistry; "hUserRegistry"
0x180020e6a  lea     rcx, aNgcstatusstora; "NgcStatusStorage::Load"
0x180020e71  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x180020e76  jmp     loc_180021124
0x180020e7b  lea     rax, [rbp+57h+hKey]
0x180020e7f  mov     r9d, 20019h; samDesired
0x180020e85  lea     r13, aSoftwareMicros_12; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180020e8c  mov     [rsp+0E0h+phkResult], rax; phkResult
0x180020e91  mov     rdx, r13; lpSubKey
0x180020e94  xor     r8d, r8d; ulOptions
0x180020e97  mov     rcx, rbx; hKey
0x180020e9a  mov     edi, r12d
0x180020e9d  call    cs:__imp_RegOpenKeyExW
0x180020ea3  mov     ebx, eax
0x180020ea5  cmp     eax, 2
0x180020ea8  jnz     short loc_180020ECC
0x180020eaa  mov     r9, r13
0x180020ead  lea     r8, aHkeyCurrentUse; "HKEY_CURRENT_USER"
0x180020eb4  lea     rdx, aNgcstatusstora; "NgcStatusStorage::Load"
0x180020ebb  lea     rcx, aSTheRegistryKe_5; "%s: The registry key \"%s\\%s\" does no"...
0x180020ec2  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180020ec7  jmp     loc_180021124
0x180020ecc  test    ebx, ebx
0x180020ece  jz      short loc_180020EFD
0x180020ed0  lea     r9, aHkeyCurrentUse; "HKEY_CURRENT_USER"
0x180020ed7  mov     [rsp+0E0h+phkResult], r13
0x180020edc  lea     r8, aSS_0; "%s\\%s"
0x180020ee3  mov     ecx, ebx; unsigned int
0x180020ee5  lea     rdx, aRegopenkeyexw; "RegOpenKeyExW"
0x180020eec  call    ?WriteRegistryFailureEventEx@Logger@@SAJKPEBG0ZZ; Logger::WriteRegistryFailureEventEx(ulong,ushort const *,ushort const *,...)
0x180020ef1  lea     rcx, aSCannotOpenReg_1; "%s: Cannot open registry key \"%s\\%s\""...
0x180020ef8  jmp     loc_1800210E4
0x180020efd  mov     rcx, [rbp+57h+hKey]; hKey
0x180020f01  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x180020f05  mov     [rsp+0E0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180020f0a  xor     r9d, r9d; lpReserved
0x180020f0d  mov     [rsp+0E0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x180020f12  xor     r8d, r8d; lpcchClass
0x180020f15  mov     [rsp+0E0h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x180020f1a  xor     edx, edx; lpClass
0x180020f1c  mov     [rsp+0E0h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x180020f21  mov     [rsp+0E0h+lpcValues], r12; lpcValues
0x180020f26  mov     [rsp+0E0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x180020f2b  mov     [rsp+0E0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180020f30  lea     rax, [rbp+57h+cSubKeys]
0x180020f34  mov     [rsp+0E0h+phkResult], rax; unsigned __int16 *
0x180020f39  call    cs:__imp_RegQueryInfoKeyW
0x180020f3f  mov     ebx, eax
0x180020f41  test    eax, eax
0x180020f43  jz      short loc_180020F66
0x180020f45  lea     r9, aHkeyCurrentUse; "HKEY_CURRENT_USER"
0x180020f4c  mov     ecx, eax; unsigned int
0x180020f4e  lea     rdx, aRegqueryinfoke; "RegQueryInfoKeyW"
0x180020f55  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG000@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *,ushort const *,ushort const *)
0x180020f5a  lea     rcx, aSCannotQueryVa; "%s: Cannot query values of registry key"...
0x180020f61  jmp     loc_1800210E4
0x180020f66  mov     eax, [rbp+57h+cSubKeys]
0x180020f69  test    eax, eax
0x180020f6b  jz      loc_180021111
0x180020f71  cmp     [rbp+57h+cbMaxSubKeyLen], r12d
0x180020f75  jz      loc_180021111
0x180020f7b  mov     ecx, 400h
0x180020f80  cmp     eax, ecx
0x180020f82  cmova   eax, ecx
0x180020f85  mov     ebx, eax
0x180020f87  shl     rbx, 6
0x180020f8b  mov     rcx, rbx; size
0x180020f8e  call    MIDL_user_allocate
0x180020f93  mov     [rsi], rax
0x180020f96  test    rax, rax
0x180020f99  jnz     short loc_180020FB8
0x180020f9b  lea     rdx, aNgcstatusstora; "NgcStatusStorage::Load"
0x180020fa2  mov     edi, 8007000Eh
0x180020fa7  lea     rcx, aSOutOfMemoryAl; "%s: Out of memory. Allocation failed."
0x180020fae  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x180020fb3  jmp     loc_180021124
0x180020fb8  test    rbx, rbx
0x180020fbb  jz      short loc_180020FC9
0x180020fbd  mov     [rax], r12b
0x180020fc0  inc     rax
0x180020fc3  sub     rbx, 1
0x180020fc7  jnz     short loc_180020FBD
0x180020fc9  mov     ecx, [rbp+57h+cbMaxSubKeyLen]
0x180020fcc  inc     ecx
0x180020fce  mov     [rsi+8], r12
0x180020fd2  add     rcx, rcx; size
0x180020fd5  call    MIDL_user_allocate
0x180020fda  mov     r14, rax
0x180020fdd  test    rax, rax
0x180020fe0  jz      short loc_180020F9B
0x180020fe2  mov     r15d, r12d
0x180020fe5  cmp     r15d, [rbp+57h+cSubKeys]
0x180020fe9  jnb     loc_180021124
0x180020fef  cmp     qword ptr [rsi+8], 400h
0x180020ff7  jnb     loc_180021124
0x180020ffd  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x180021000  lea     r9, [rbp+57h+cchName]; lpcchName
0x180021004  mov     rcx, [rbp+57h+hKey]; hKey
0x180021008  inc     eax
0x18002100a  mov     [rsp+0E0h+lpcValues], r12; lpftLastWriteTime
0x18002100f  mov     r8, r14; lpName
0x180021012  mov     [rsp+0E0h+lpcbMaxClassLen], r12; lpcchClass
0x180021017  mov     edx, r15d; dwIndex
0x18002101a  mov     [rsp+0E0h+lpcbMaxSubKeyLen], r12; lpClass
0x18002101f  mov     [rbp+57h+cchName], eax
0x180021022  mov     [rsp+0E0h+phkResult], r12; unsigned __int16 *
0x180021027  call    cs:__imp_RegEnumKeyExW
0x18002102d  mov     ebx, eax
0x18002102f  test    eax, eax
0x180021031  jnz     loc_1800210C8
0x180021037  xorps   xmm0, xmm0
0x18002103a  lea     rdx, [rbp+57h+Uuid]; Uuid
0x18002103e  mov     rcx, r14; StringUuid
0x180021041  movups  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x180021045  call    cs:__imp_UuidFromStringW
0x18002104b  test    eax, eax
0x18002104d  jz      short loc_18002106A
0x18002104f  mov     r9d, eax
0x180021052  lea     rdx, aNgcstatusstora; "NgcStatusStorage::Load"
0x180021059  mov     r8, r14
0x18002105c  lea     rcx, aSTheRegistryKe_0; "%s: The registry key \"%s\" is not a va"...
0x180021063  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x180021068  jmp     short loc_180021098
0x18002106a  mov     r9, [rsi+8]
0x18002106e  lea     r8, [rbp+57h+var_60]; struct _GUID
0x180021072  movaps  xmm0, xmmword ptr [rbp+57h+Uuid.Data1]
0x180021076  mov     rdx, r14; unsigned __int16 *
0x180021079  mov     rcx, [rbp+57h+hKey]; HKEY
0x18002107d  shl     r9, 6
0x180021081  add     r9, [rsi]; struct STRUCT_NGC_REG_KEY *
0x180021084  movdqa  xmmword ptr [rbp+57h+var_60.Data1], xmm0
0x180021089  call    ?ReadKey@NgcStatusStorage@@CAKPEAUHKEY__@@PEBGU_GUID@@PEAUSTRUCT_NGC_REG_KEY@@@Z; NgcStatusStorage::ReadKey(HKEY__ *,ushort const *,_GUID,STRUCT_NGC_REG_KEY *)
0x18002108e  mov     ebx, eax
0x180021090  test    eax, eax
0x180021092  jnz     short loc_1800210A0
0x180021094  inc     qword ptr [rsi+8]
0x180021098  inc     r15d
0x18002109b  jmp     loc_180020FE5
0x1800210a0  mov     dword ptr [rsp+0E0h+lpcbMaxSubKeyLen], eax
0x1800210a4  lea     r8, aHkeyCurrentUse; "HKEY_CURRENT_USER"
0x1800210ab  mov     r9, r13
0x1800210ae  mov     [rsp+0E0h+phkResult], r14
0x1800210b3  lea     rdx, aNgcstatusstora; "NgcStatusStorage::Load"
0x1800210ba  lea     rcx, aSFailedToReadR; "%s: Failed to read registry key \"%s\\%"...
0x1800210c1  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800210c6  jmp     short loc_1800210FE
0x1800210c8  lea     r9, aHkeyCurrentUse; "HKEY_CURRENT_USER"
0x1800210cf  mov     ecx, ebx; unsigned int
0x1800210d1  lea     rdx, aRegenumkeyexw; "RegEnumKeyExW"
0x1800210d8  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG000@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *,ushort const *,ushort const *)
0x1800210dd  lea     rcx, aSCannotEnumera; "%s: Cannot enumerate keys under registr"...
0x1800210e4  mov     r9, r13
0x1800210e7  mov     dword ptr [rsp+0E0h+phkResult], ebx
0x1800210eb  lea     r8, aHkeyCurrentUse; "HKEY_CURRENT_USER"
0x1800210f2  lea     rdx, aNgcstatusstora; "NgcStatusStorage::Load"
0x1800210f9  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800210fe  test    ebx, ebx
0x180021100  jg      short loc_180021106
0x180021102  mov     edi, ebx
0x180021104  jmp     short loc_180021124
0x180021106  movzx   edi, bx
0x180021109  or      edi, 80070000h
0x18002110f  jmp     short loc_180021124
0x180021111  lea     rdx, aNgcstatusstora; "NgcStatusStorage::Load"
0x180021118  lea     rcx, aSThereIsNoVali; "%s: There is no valid key registry."
0x18002111f  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180021124  mov     rcx, [rbp+57h+hKey]; hKey
0x180021128  test    rcx, rcx
0x18002112b  jz      short loc_180021137
0x18002112d  call    cs:__imp_RegCloseKey
0x180021133  mov     [rbp+57h+hKey], r12
0x180021137  mov     rcx, r14; void *
0x18002113a  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18002113f  xor     ecx, ecx; void *
0x180021141  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x180021146  test    edi, edi
0x180021148  jns     short loc_180021152
0x18002114a  mov     rcx, rsi; this
0x18002114d  call    ?Cleanup@NgcStatusStorage@@QEAAXXZ; NgcStatusStorage::Cleanup(void)
0x180021152  mov     eax, edi
0x180021154  mov     rcx, [rbp+57h+var_40]
0x180021158  xor     rcx, rsp; StackCookie
0x18002115b  call    __security_check_cookie
0x180021160  mov     rbx, [rsp+0E0h+arg_10]
0x180021168  add     rsp, 0B0h
0x18002116f  pop     r15
0x180021171  pop     r14
0x180021173  pop     r13
0x180021175  pop     r12
0x180021177  pop     rdi
0x180021178  pop     rsi
0x180021179  pop     rbp
0x18002117a  retn
```
