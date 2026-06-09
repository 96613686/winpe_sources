# NgcStatusStorage::Load(HKEY__ *,ushort const *)

- ea: `0x180080c58`
- end: `0x180080fe5`
- name: `?Load@NgcStatusStorage@@QEAAJPEAUHKEY__@@PEBG@Z`
- size: `909`
- prototype: `__int64 __fastcall(NgcStatusStorage *__hidden this, HKEY hKey, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180080fec`

## callees

- `0x180007670`
- `0x18006b2c0`
- `0x180079de0`
- `0x18007d17c`
- `0x18007d1b8`
- `0x18007d1f4`
- `0x18007d22c`
- `0x18007d2a4`
- `0x18007d300`
- `0x18007d3e0`
- `0x180080b30`
- `0x180080c58`
- `0x180081084`

## import_xrefs

- `RPCRT4!UuidFromStringW` at `0x180080ea5`
- `RPCRT4!UuidFromStringW` at `0x180080ea5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180080cfd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180080cfd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180080f97`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180080f97`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180080e87`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180080e87`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180080d99`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180080d99`

## string_xrefs

- `0x180080d45`: `RegOpenKeyExW`
- `0x180080ca4`: `hUserRegistry`
- `0x180080cc3`: `hUserRegistry`
- `0x180080d1b`: `%s: The registry key "%s\%s" does not exist. Noting to read.`
- `0x180080dba`: `%s: Cannot query values of registry key "%s\%s". Win32 error code: 0x%08x.`
- `0x180080f82`: `%s: There is no valid key registry.`
- `0x180080d51`: `%s: Cannot open registry key "%s\%s". Win32 error code: 0x%08x.`
- `0x180080ebc`: `%s: The registry key "%s" is not a valid NGC key ID. Error code: 0x%08x.`
- `0x180080f24`: `%s: Failed to read registry key "%s\%s\%s". Error code: 0x%08x.`
- `0x180080f47`: `%s: Cannot enumerate keys under registry key "%s\%s". Win32 error code: 0x%08x.`

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
  DWORD v16; // r15d
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
      v16 = 0;
      if ( cSubKeys )
      {
        while ( *((_QWORD *)this + 1) < 0x400u )
        {
          cchName[0] = cbMaxSubKeyLen + 1;
          v17 = RegEnumKeyExW(hKeya, v16, v4, cchName, 0, 0, 0, 0);
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
          if ( ++v16 >= cSubKeys )
            break;
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
0x180080c58  mov     [rsp-8+arg_10], rbx
0x180080c5d  push    rbp
0x180080c5e  push    rsi
0x180080c5f  push    rdi
0x180080c60  push    r12
0x180080c62  push    r13
0x180080c64  push    r14
0x180080c66  push    r15
0x180080c68  lea     rbp, [rsp-27h]
0x180080c6d  sub     rsp, 0B0h
0x180080c74  mov     rax, cs:__security_cookie
0x180080c7b  xor     rax, rsp
0x180080c7e  mov     [rbp+57h+var_40], rax
0x180080c82  xor     r12d, r12d
0x180080c85  mov     rbx, rdx
0x180080c88  mov     [rbp+57h+hKey], r12
0x180080c8c  mov     r14d, r12d
0x180080c8f  mov     [rbp+57h+cSubKeys], r12d
0x180080c93  mov     rsi, rcx
0x180080c96  mov     [rbp+57h+cbMaxSubKeyLen], r12d
0x180080c9a  call    ?Cleanup@NgcStatusStorage@@QEAAXXZ; NgcStatusStorage::Cleanup(void)
0x180080c9f  test    rbx, rbx
0x180080ca2  jnz     short loc_180080CDB
0x180080ca4  lea     r8, aHuserregistry; "hUserRegistry"
0x180080cab  mov     edi, 80070057h
0x180080cb0  lea     rdx, aNgcstatusstora; "NgcStatusStorage::Load"
0x180080cb7  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x180080cbe  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180080cc3  lea     rdx, aHuserregistry; "hUserRegistry"
0x180080cca  lea     rcx, aNgcstatusstora; "NgcStatusStorage::Load"
0x180080cd1  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x180080cd6  jmp     loc_180080F8E
0x180080cdb  lea     rax, [rbp+57h+hKey]
0x180080cdf  mov     r9d, 20019h; samDesired
0x180080ce5  lea     r13, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180080cec  mov     [rsp+0E0h+phkResult], rax; phkResult
0x180080cf1  mov     rdx, r13; lpSubKey
0x180080cf4  xor     r8d, r8d; ulOptions
0x180080cf7  mov     rcx, rbx; hKey
0x180080cfa  mov     edi, r12d
0x180080cfd  call    cs:__imp_RegOpenKeyExW
0x180080d03  mov     ebx, eax
0x180080d05  cmp     eax, 2
0x180080d08  jnz     short loc_180080D2C
0x180080d0a  mov     r9, r13
0x180080d0d  lea     r8, aHkeyCurrentUse; "HKEY_CURRENT_USER"
0x180080d14  lea     rdx, aNgcstatusstora; "NgcStatusStorage::Load"
0x180080d1b  lea     rcx, aSTheRegistryKe_5; "%s: The registry key \"%s\\%s\" does no"...
0x180080d22  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180080d27  jmp     loc_180080F8E
0x180080d2c  test    ebx, ebx
0x180080d2e  jz      short loc_180080D5D
0x180080d30  lea     r9, aHkeyCurrentUse; "HKEY_CURRENT_USER"
0x180080d37  mov     [rsp+0E0h+phkResult], r13
0x180080d3c  lea     r8, aSS_0; "%s\\%s"
0x180080d43  mov     ecx, ebx; unsigned int
0x180080d45  lea     rdx, aRegopenkeyexw; "RegOpenKeyExW"
0x180080d4c  call    ?WriteRegistryFailureEventEx@Logger@@SAJKPEBG0ZZ; Logger::WriteRegistryFailureEventEx(ulong,ushort const *,ushort const *,...)
0x180080d51  lea     rcx, aSCannotOpenReg_1; "%s: Cannot open registry key \"%s\\%s\""...
0x180080d58  jmp     loc_180080F4E
0x180080d5d  mov     rcx, [rbp+57h+hKey]; hKey
0x180080d61  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x180080d65  mov     [rsp+0E0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180080d6a  xor     r9d, r9d; lpReserved
0x180080d6d  mov     [rsp+0E0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x180080d72  xor     r8d, r8d; lpcchClass
0x180080d75  mov     [rsp+0E0h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x180080d7a  xor     edx, edx; lpClass
0x180080d7c  mov     [rsp+0E0h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x180080d81  mov     [rsp+0E0h+lpcValues], r12; lpcValues
0x180080d86  mov     [rsp+0E0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x180080d8b  mov     [rsp+0E0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180080d90  lea     rax, [rbp+57h+cSubKeys]
0x180080d94  mov     [rsp+0E0h+phkResult], rax; unsigned __int16 *
0x180080d99  call    cs:__imp_RegQueryInfoKeyW
0x180080d9f  mov     ebx, eax
0x180080da1  test    eax, eax
0x180080da3  jz      short loc_180080DC6
0x180080da5  lea     r9, aHkeyCurrentUse; "HKEY_CURRENT_USER"
0x180080dac  mov     ecx, eax; unsigned int
0x180080dae  lea     rdx, aRegqueryinfoke; "RegQueryInfoKeyW"
0x180080db5  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG000@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *,ushort const *,ushort const *)
0x180080dba  lea     rcx, aSCannotQueryVa; "%s: Cannot query values of registry key"...
0x180080dc1  jmp     loc_180080F4E
0x180080dc6  mov     eax, [rbp+57h+cSubKeys]
0x180080dc9  test    eax, eax
0x180080dcb  jz      loc_180080F7B
0x180080dd1  cmp     [rbp+57h+cbMaxSubKeyLen], r12d
0x180080dd5  jz      loc_180080F7B
0x180080ddb  mov     ecx, 400h
0x180080de0  cmp     eax, ecx
0x180080de2  cmova   eax, ecx
0x180080de5  mov     ebx, eax
0x180080de7  shl     rbx, 6
0x180080deb  mov     rcx, rbx; size
0x180080dee  call    MIDL_user_allocate
0x180080df3  mov     [rsi], rax
0x180080df6  test    rax, rax
0x180080df9  jnz     short loc_180080E18
0x180080dfb  lea     rdx, aNgcstatusstora; "NgcStatusStorage::Load"
0x180080e02  mov     edi, 8007000Eh
0x180080e07  lea     rcx, aSOutOfMemoryAl; "%s: Out of memory. Allocation failed."
0x180080e0e  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x180080e13  jmp     loc_180080F8E
0x180080e18  test    rbx, rbx
0x180080e1b  jz      short loc_180080E29
0x180080e1d  mov     [rax], r12b
0x180080e20  inc     rax
0x180080e23  sub     rbx, 1
0x180080e27  jnz     short loc_180080E1D
0x180080e29  mov     ecx, [rbp+57h+cbMaxSubKeyLen]
0x180080e2c  inc     ecx
0x180080e2e  mov     [rsi+8], r12
0x180080e32  add     rcx, rcx; size
0x180080e35  call    MIDL_user_allocate
0x180080e3a  mov     r14, rax
0x180080e3d  test    rax, rax
0x180080e40  jz      short loc_180080DFB
0x180080e42  mov     r15d, r12d
0x180080e45  cmp     [rbp+57h+cSubKeys], r12d
0x180080e49  jbe     loc_180080F8E
0x180080e4f  cmp     qword ptr [rsi+8], 400h
0x180080e57  jnb     loc_180080F8E
0x180080e5d  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x180080e60  lea     r9, [rbp+57h+cchName]; lpcchName
0x180080e64  mov     rcx, [rbp+57h+hKey]; hKey
0x180080e68  inc     eax
0x180080e6a  mov     [rsp+0E0h+lpcValues], r12; lpftLastWriteTime
0x180080e6f  mov     r8, r14; lpName
0x180080e72  mov     [rsp+0E0h+lpcbMaxClassLen], r12; lpcchClass
0x180080e77  mov     edx, r15d; dwIndex
0x180080e7a  mov     [rsp+0E0h+lpcbMaxSubKeyLen], r12; lpClass
0x180080e7f  mov     [rbp+57h+cchName], eax
0x180080e82  mov     [rsp+0E0h+phkResult], r12; unsigned __int16 *
0x180080e87  call    cs:__imp_RegEnumKeyExW
0x180080e8d  mov     ebx, eax
0x180080e8f  test    eax, eax
0x180080e91  jnz     loc_180080F32
0x180080e97  xorps   xmm0, xmm0
0x180080e9a  lea     rdx, [rbp+57h+Uuid]; Uuid
0x180080e9e  mov     rcx, r14; StringUuid
0x180080ea1  movups  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x180080ea5  call    cs:__imp_UuidFromStringW
0x180080eab  test    eax, eax
0x180080ead  jz      short loc_180080ECA
0x180080eaf  mov     r9d, eax
0x180080eb2  lea     rdx, aNgcstatusstora; "NgcStatusStorage::Load"
0x180080eb9  mov     r8, r14
0x180080ebc  lea     rcx, aSTheRegistryKe_0; "%s: The registry key \"%s\" is not a va"...
0x180080ec3  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x180080ec8  jmp     short loc_180080EF8
0x180080eca  mov     r9, [rsi+8]
0x180080ece  lea     r8, [rbp+57h+var_60]; struct _GUID
0x180080ed2  movaps  xmm0, xmmword ptr [rbp+57h+Uuid.Data1]
0x180080ed6  mov     rdx, r14; unsigned __int16 *
0x180080ed9  mov     rcx, [rbp+57h+hKey]; HKEY
0x180080edd  shl     r9, 6
0x180080ee1  add     r9, [rsi]; struct STRUCT_NGC_REG_KEY *
0x180080ee4  movdqa  xmmword ptr [rbp+57h+var_60.Data1], xmm0
0x180080ee9  call    ?ReadKey@NgcStatusStorage@@CAKPEAUHKEY__@@PEBGU_GUID@@PEAUSTRUCT_NGC_REG_KEY@@@Z; NgcStatusStorage::ReadKey(HKEY__ *,ushort const *,_GUID,STRUCT_NGC_REG_KEY *)
0x180080eee  mov     ebx, eax
0x180080ef0  test    eax, eax
0x180080ef2  jnz     short loc_180080F0A
0x180080ef4  inc     qword ptr [rsi+8]
0x180080ef8  inc     r15d
0x180080efb  cmp     r15d, [rbp+57h+cSubKeys]
0x180080eff  jb      loc_180080E4F
0x180080f05  jmp     loc_180080F8E
0x180080f0a  mov     dword ptr [rsp+0E0h+lpcbMaxSubKeyLen], eax
0x180080f0e  lea     r8, aHkeyCurrentUse; "HKEY_CURRENT_USER"
0x180080f15  mov     r9, r13
0x180080f18  mov     [rsp+0E0h+phkResult], r14
0x180080f1d  lea     rdx, aNgcstatusstora; "NgcStatusStorage::Load"
0x180080f24  lea     rcx, aSFailedToReadR; "%s: Failed to read registry key \"%s\\%"...
0x180080f2b  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180080f30  jmp     short loc_180080F68
0x180080f32  lea     r9, aHkeyCurrentUse; "HKEY_CURRENT_USER"
0x180080f39  mov     ecx, ebx; unsigned int
0x180080f3b  lea     rdx, aRegenumkeyexw; "RegEnumKeyExW"
0x180080f42  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG000@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *,ushort const *,ushort const *)
0x180080f47  lea     rcx, aSCannotEnumera; "%s: Cannot enumerate keys under registr"...
0x180080f4e  mov     r9, r13
0x180080f51  mov     dword ptr [rsp+0E0h+phkResult], ebx
0x180080f55  lea     r8, aHkeyCurrentUse; "HKEY_CURRENT_USER"
0x180080f5c  lea     rdx, aNgcstatusstora; "NgcStatusStorage::Load"
0x180080f63  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180080f68  test    ebx, ebx
0x180080f6a  jg      short loc_180080F70
0x180080f6c  mov     edi, ebx
0x180080f6e  jmp     short loc_180080F8E
0x180080f70  movzx   edi, bx
0x180080f73  or      edi, 80070000h
0x180080f79  jmp     short loc_180080F8E
0x180080f7b  lea     rdx, aNgcstatusstora; "NgcStatusStorage::Load"
0x180080f82  lea     rcx, aSThereIsNoVali; "%s: There is no valid key registry."
0x180080f89  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180080f8e  mov     rcx, [rbp+57h+hKey]; hKey
0x180080f92  test    rcx, rcx
0x180080f95  jz      short loc_180080FA1
0x180080f97  call    cs:__imp_RegCloseKey
0x180080f9d  mov     [rbp+57h+hKey], r12
0x180080fa1  mov     rcx, r14; void *
0x180080fa4  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x180080fa9  xor     ecx, ecx; void *
0x180080fab  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x180080fb0  test    edi, edi
0x180080fb2  jns     short loc_180080FBC
0x180080fb4  mov     rcx, rsi; this
0x180080fb7  call    ?Cleanup@NgcStatusStorage@@QEAAXXZ; NgcStatusStorage::Cleanup(void)
0x180080fbc  mov     eax, edi
0x180080fbe  mov     rcx, [rbp+57h+var_40]
0x180080fc2  xor     rcx, rsp; StackCookie
0x180080fc5  call    __security_check_cookie
0x180080fca  mov     rbx, [rsp+0E0h+arg_10]
0x180080fd2  add     rsp, 0B0h
0x180080fd9  pop     r15
0x180080fdb  pop     r14
0x180080fdd  pop     r13
0x180080fdf  pop     r12
0x180080fe1  pop     rdi
0x180080fe2  pop     rsi
0x180080fe3  pop     rbp
0x180080fe4  retn
```
