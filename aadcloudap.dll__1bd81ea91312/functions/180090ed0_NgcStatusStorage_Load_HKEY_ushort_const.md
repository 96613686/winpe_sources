# NgcStatusStorage::Load(HKEY__ *,ushort const *)

- ea: `0x180090ed0`
- end: `0x18009125d`
- name: `?Load@NgcStatusStorage@@QEAAJPEAUHKEY__@@PEBG@Z`
- size: `909`
- prototype: `__int64 __fastcall(NgcStatusStorage *__hidden this, HKEY hKey, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180091264`

## callees

- `0x180003c20`
- `0x180087188`
- `0x1800871b4`
- `0x18008a9ec`
- `0x18008aa28`
- `0x18008aa64`
- `0x18008aa9c`
- `0x18008aecc`
- `0x18008af38`
- `0x18008b014`
- `0x180090da8`
- `0x180090ed0`
- `0x1800912fc`

## import_xrefs

- `RPCRT4!UuidFromStringW` at `0x18009111d`
- `RPCRT4!UuidFromStringW` at `0x18009111d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180090f75`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180090f75`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009120f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009120f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180091011`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180091011`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800910ff`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800910ff`

## string_xrefs

- `0x180090fbd`: `RegOpenKeyExW`
- `0x180090f1c`: `hUserRegistry`
- `0x180090f3b`: `hUserRegistry`
- `0x180091032`: `%s: Cannot query values of registry key "%s\%s". Win32 error code: 0x%08x.`
- `0x180090f93`: `%s: The registry key "%s\%s" does not exist. Noting to read.`
- `0x180090fc9`: `%s: Cannot open registry key "%s\%s". Win32 error code: 0x%08x.`
- `0x1800911bf`: `%s: Cannot enumerate keys under registry key "%s\%s". Win32 error code: 0x%08x.`
- `0x180091134`: `%s: The registry key "%s" is not a valid NGC key ID. Error code: 0x%08x.`
- `0x1800911fa`: `%s: There is no valid key registry.`
- `0x18009119c`: `%s: Failed to read registry key "%s\%s\%s". Error code: 0x%08x.`

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
  unsigned __int64 v13; // rbx
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
    v14 = SafeAlloc(v13);
    *(_QWORD *)this = v14;
    if ( !v14 )
      goto LABEL_14;
    for ( ; v13; --v13 )
      *v14++ = 0;
    v15 = cbMaxSubKeyLen + 1;
    *((_QWORD *)this + 1) = 0;
    v4 = (WCHAR *)SafeAlloc(2 * v15);
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
0x180090ed0  mov     [rsp-8+arg_10], rbx
0x180090ed5  push    rbp
0x180090ed6  push    rsi
0x180090ed7  push    rdi
0x180090ed8  push    r12
0x180090eda  push    r13
0x180090edc  push    r14
0x180090ede  push    r15
0x180090ee0  lea     rbp, [rsp-27h]
0x180090ee5  sub     rsp, 0B0h
0x180090eec  mov     rax, cs:__security_cookie
0x180090ef3  xor     rax, rsp
0x180090ef6  mov     [rbp+57h+var_40], rax
0x180090efa  xor     r12d, r12d
0x180090efd  mov     rbx, rdx
0x180090f00  mov     [rbp+57h+hKey], r12
0x180090f04  mov     r14d, r12d
0x180090f07  mov     [rbp+57h+cSubKeys], r12d
0x180090f0b  mov     rsi, rcx
0x180090f0e  mov     [rbp+57h+cbMaxSubKeyLen], r12d
0x180090f12  call    ?Cleanup@NgcStatusStorage@@QEAAXXZ; NgcStatusStorage::Cleanup(void)
0x180090f17  test    rbx, rbx
0x180090f1a  jnz     short loc_180090F53
0x180090f1c  lea     r8, aHuserregistry; "hUserRegistry"
0x180090f23  mov     edi, 80070057h
0x180090f28  lea     rdx, aNgcstatusstora; "NgcStatusStorage::Load"
0x180090f2f  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180090f36  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180090f3b  lea     rdx, aHuserregistry; "hUserRegistry"
0x180090f42  lea     rcx, aNgcstatusstora; "NgcStatusStorage::Load"
0x180090f49  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x180090f4e  jmp     loc_180091206
0x180090f53  lea     rax, [rbp+57h+hKey]
0x180090f57  mov     r9d, 20019h; samDesired
0x180090f5d  lea     r13, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180090f64  mov     [rsp+0E0h+phkResult], rax; phkResult
0x180090f69  mov     rdx, r13; lpSubKey
0x180090f6c  xor     r8d, r8d; ulOptions
0x180090f6f  mov     rcx, rbx; hKey
0x180090f72  mov     edi, r12d
0x180090f75  call    cs:__imp_RegOpenKeyExW
0x180090f7b  mov     ebx, eax
0x180090f7d  cmp     eax, 2
0x180090f80  jnz     short loc_180090FA4
0x180090f82  mov     r9, r13
0x180090f85  lea     r8, aHkeyCurrentUse; "HKEY_CURRENT_USER"
0x180090f8c  lea     rdx, aNgcstatusstora; "NgcStatusStorage::Load"
0x180090f93  lea     rcx, aSTheRegistryKe_5; "%s: The registry key \"%s\\%s\" does no"...
0x180090f9a  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180090f9f  jmp     loc_180091206
0x180090fa4  test    ebx, ebx
0x180090fa6  jz      short loc_180090FD5
0x180090fa8  lea     r9, aHkeyCurrentUse; "HKEY_CURRENT_USER"
0x180090faf  mov     [rsp+0E0h+phkResult], r13
0x180090fb4  lea     r8, aSS_5; "%s\\%s"
0x180090fbb  mov     ecx, ebx; unsigned int
0x180090fbd  lea     rdx, aRegopenkeyexw; "RegOpenKeyExW"
0x180090fc4  call    ?WriteRegistryFailureEventEx@Logger@@SAJKPEBG0ZZ; Logger::WriteRegistryFailureEventEx(ulong,ushort const *,ushort const *,...)
0x180090fc9  lea     rcx, aSCannotOpenReg_1; "%s: Cannot open registry key \"%s\\%s\""...
0x180090fd0  jmp     loc_1800911C6
0x180090fd5  mov     rcx, [rbp+57h+hKey]; hKey
0x180090fd9  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x180090fdd  mov     [rsp+0E0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180090fe2  xor     r9d, r9d; lpReserved
0x180090fe5  mov     [rsp+0E0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x180090fea  xor     r8d, r8d; lpcchClass
0x180090fed  mov     [rsp+0E0h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x180090ff2  xor     edx, edx; lpClass
0x180090ff4  mov     [rsp+0E0h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x180090ff9  mov     [rsp+0E0h+lpcValues], r12; lpcValues
0x180090ffe  mov     [rsp+0E0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x180091003  mov     [rsp+0E0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180091008  lea     rax, [rbp+57h+cSubKeys]
0x18009100c  mov     [rsp+0E0h+phkResult], rax; unsigned __int16 *
0x180091011  call    cs:__imp_RegQueryInfoKeyW
0x180091017  mov     ebx, eax
0x180091019  test    eax, eax
0x18009101b  jz      short loc_18009103E
0x18009101d  lea     r9, aHkeyCurrentUse; "HKEY_CURRENT_USER"
0x180091024  mov     ecx, eax; unsigned int
0x180091026  lea     rdx, aRegqueryinfoke; "RegQueryInfoKeyW"
0x18009102d  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG000@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *,ushort const *,ushort const *)
0x180091032  lea     rcx, aSCannotQueryVa; "%s: Cannot query values of registry key"...
0x180091039  jmp     loc_1800911C6
0x18009103e  mov     eax, [rbp+57h+cSubKeys]
0x180091041  test    eax, eax
0x180091043  jz      loc_1800911F3
0x180091049  cmp     [rbp+57h+cbMaxSubKeyLen], r12d
0x18009104d  jz      loc_1800911F3
0x180091053  mov     ecx, 400h
0x180091058  cmp     eax, ecx
0x18009105a  cmova   eax, ecx
0x18009105d  mov     ebx, eax
0x18009105f  shl     rbx, 6
0x180091063  mov     rcx, rbx; unsigned __int64
0x180091066  call    ?SafeAlloc@@YAPEAX_K@Z; SafeAlloc(unsigned __int64)
0x18009106b  mov     [rsi], rax
0x18009106e  test    rax, rax
0x180091071  jnz     short loc_180091090
0x180091073  lea     rdx, aNgcstatusstora; "NgcStatusStorage::Load"
0x18009107a  mov     edi, 8007000Eh
0x18009107f  lea     rcx, aSOutOfMemoryAl_0; "%s: Out of memory. Allocation failed."
0x180091086  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x18009108b  jmp     loc_180091206
0x180091090  test    rbx, rbx
0x180091093  jz      short loc_1800910A1
0x180091095  mov     [rax], r12b
0x180091098  inc     rax
0x18009109b  sub     rbx, 1
0x18009109f  jnz     short loc_180091095
0x1800910a1  mov     ecx, [rbp+57h+cbMaxSubKeyLen]
0x1800910a4  inc     ecx
0x1800910a6  mov     [rsi+8], r12
0x1800910aa  add     rcx, rcx; unsigned __int64
0x1800910ad  call    ?SafeAlloc@@YAPEAX_K@Z; SafeAlloc(unsigned __int64)
0x1800910b2  mov     r14, rax
0x1800910b5  test    rax, rax
0x1800910b8  jz      short loc_180091073
0x1800910ba  mov     r15d, r12d
0x1800910bd  cmp     [rbp+57h+cSubKeys], r12d
0x1800910c1  jbe     loc_180091206
0x1800910c7  cmp     qword ptr [rsi+8], 400h
0x1800910cf  jnb     loc_180091206
0x1800910d5  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x1800910d8  lea     r9, [rbp+57h+cchName]; lpcchName
0x1800910dc  mov     rcx, [rbp+57h+hKey]; hKey
0x1800910e0  inc     eax
0x1800910e2  mov     [rsp+0E0h+lpcValues], r12; lpftLastWriteTime
0x1800910e7  mov     r8, r14; lpName
0x1800910ea  mov     [rsp+0E0h+lpcbMaxClassLen], r12; lpcchClass
0x1800910ef  mov     edx, r15d; dwIndex
0x1800910f2  mov     [rsp+0E0h+lpcbMaxSubKeyLen], r12; lpClass
0x1800910f7  mov     [rbp+57h+cchName], eax
0x1800910fa  mov     [rsp+0E0h+phkResult], r12; unsigned __int16 *
0x1800910ff  call    cs:__imp_RegEnumKeyExW
0x180091105  mov     ebx, eax
0x180091107  test    eax, eax
0x180091109  jnz     loc_1800911AA
0x18009110f  xorps   xmm0, xmm0
0x180091112  lea     rdx, [rbp+57h+Uuid]; Uuid
0x180091116  mov     rcx, r14; StringUuid
0x180091119  movups  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x18009111d  call    cs:__imp_UuidFromStringW
0x180091123  test    eax, eax
0x180091125  jz      short loc_180091142
0x180091127  mov     r9d, eax
0x18009112a  lea     rdx, aNgcstatusstora; "NgcStatusStorage::Load"
0x180091131  mov     r8, r14
0x180091134  lea     rcx, aSTheRegistryKe_0; "%s: The registry key \"%s\" is not a va"...
0x18009113b  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x180091140  jmp     short loc_180091170
0x180091142  mov     r9, [rsi+8]
0x180091146  lea     r8, [rbp+57h+var_60]; struct _GUID
0x18009114a  movaps  xmm0, xmmword ptr [rbp+57h+Uuid.Data1]
0x18009114e  mov     rdx, r14; unsigned __int16 *
0x180091151  mov     rcx, [rbp+57h+hKey]; HKEY
0x180091155  shl     r9, 6
0x180091159  add     r9, [rsi]; struct STRUCT_NGC_REG_KEY *
0x18009115c  movdqa  xmmword ptr [rbp+57h+var_60.Data1], xmm0
0x180091161  call    ?ReadKey@NgcStatusStorage@@CAKPEAUHKEY__@@PEBGU_GUID@@PEAUSTRUCT_NGC_REG_KEY@@@Z; NgcStatusStorage::ReadKey(HKEY__ *,ushort const *,_GUID,STRUCT_NGC_REG_KEY *)
0x180091166  mov     ebx, eax
0x180091168  test    eax, eax
0x18009116a  jnz     short loc_180091182
0x18009116c  inc     qword ptr [rsi+8]
0x180091170  inc     r15d
0x180091173  cmp     r15d, [rbp+57h+cSubKeys]
0x180091177  jb      loc_1800910C7
0x18009117d  jmp     loc_180091206
0x180091182  mov     dword ptr [rsp+0E0h+lpcbMaxSubKeyLen], eax
0x180091186  lea     r8, aHkeyCurrentUse; "HKEY_CURRENT_USER"
0x18009118d  mov     r9, r13
0x180091190  mov     [rsp+0E0h+phkResult], r14
0x180091195  lea     rdx, aNgcstatusstora; "NgcStatusStorage::Load"
0x18009119c  lea     rcx, aSFailedToReadR; "%s: Failed to read registry key \"%s\\%"...
0x1800911a3  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800911a8  jmp     short loc_1800911E0
0x1800911aa  lea     r9, aHkeyCurrentUse; "HKEY_CURRENT_USER"
0x1800911b1  mov     ecx, ebx; unsigned int
0x1800911b3  lea     rdx, aRegenumkeyexw; "RegEnumKeyExW"
0x1800911ba  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG000@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *,ushort const *,ushort const *)
0x1800911bf  lea     rcx, aSCannotEnumera; "%s: Cannot enumerate keys under registr"...
0x1800911c6  mov     r9, r13
0x1800911c9  mov     dword ptr [rsp+0E0h+phkResult], ebx
0x1800911cd  lea     r8, aHkeyCurrentUse; "HKEY_CURRENT_USER"
0x1800911d4  lea     rdx, aNgcstatusstora; "NgcStatusStorage::Load"
0x1800911db  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800911e0  test    ebx, ebx
0x1800911e2  jg      short loc_1800911E8
0x1800911e4  mov     edi, ebx
0x1800911e6  jmp     short loc_180091206
0x1800911e8  movzx   edi, bx
0x1800911eb  or      edi, 80070000h
0x1800911f1  jmp     short loc_180091206
0x1800911f3  lea     rdx, aNgcstatusstora; "NgcStatusStorage::Load"
0x1800911fa  lea     rcx, aSThereIsNoVali; "%s: There is no valid key registry."
0x180091201  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180091206  mov     rcx, [rbp+57h+hKey]; hKey
0x18009120a  test    rcx, rcx
0x18009120d  jz      short loc_180091219
0x18009120f  call    cs:__imp_RegCloseKey
0x180091215  mov     [rbp+57h+hKey], r12
0x180091219  mov     rcx, r14; void *
0x18009121c  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x180091221  xor     ecx, ecx; void *
0x180091223  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x180091228  test    edi, edi
0x18009122a  jns     short loc_180091234
0x18009122c  mov     rcx, rsi; this
0x18009122f  call    ?Cleanup@NgcStatusStorage@@QEAAXXZ; NgcStatusStorage::Cleanup(void)
0x180091234  mov     eax, edi
0x180091236  mov     rcx, [rbp+57h+var_40]
0x18009123a  xor     rcx, rsp; StackCookie
0x18009123d  call    __security_check_cookie
0x180091242  mov     rbx, [rsp+0E0h+arg_10]
0x18009124a  add     rsp, 0B0h
0x180091251  pop     r15
0x180091253  pop     r14
0x180091255  pop     r13
0x180091257  pop     r12
0x180091259  pop     rdi
0x18009125a  pop     rsi
0x18009125b  pop     rbp
0x18009125c  retn
```
