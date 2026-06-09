# RoutingRegistryHelper::WriteAppletIdGroupRegKeys(ushort const *,_AppletIdGroup const *,_AppletIdGroupAssetCollection const *,_GUID *)

- ea: `0x18003bc1c`
- end: `0x18003c0bd`
- name: `?WriteAppletIdGroupRegKeys@RoutingRegistryHelper@@SAJPEBGPEBU_AppletIdGroup@@PEBU_AppletIdGroupAssetCollection@@PEAU_GUID@@@Z`
- size: `1185`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const struct _AppletIdGroup *, const struct _AppletIdGroupAssetCollection *, struct _GUID *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003226c`

## callees

- `0x180003624`
- `0x1800049a0`
- `0x180005858`
- `0x180013274`
- `0x18003a878`
- `0x18003b6a0`
- `0x18003b9d4`
- `0x18003bc1c`
- `0x18003c0c4`
- `0x18007d3ec`
- `0x18007d504`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18003be6b`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18003be6b`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003be89`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003be89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bcb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bd85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bdad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bdd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bea7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bfb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bcb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bd85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bdad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bdd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bea7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bfb8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003bccc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003bd98`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003bdc0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003bde8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003beba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003bfcb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003bccc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003bd98`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003bdc0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003bde8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003beba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003bfcb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003bf32`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003bf32`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18003bd48`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18003bd48`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003bcc4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003bd90`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003bdb8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003bde0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003be1d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003be2e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003be3f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003beb2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003bfc3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003bcc4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003bd90`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003bdb8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003bde0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003be1d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003be2e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003be3f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003beb2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003bfc3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003beff`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003c009`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003beff`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003c009`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RoutingRegistryHelper::WriteAppletIdGroupRegKeys(
        const unsigned __int16 *a1,
        const struct _AppletIdGroup *a2,
        const struct _AppletIdGroupAssetCollection *a3,
        struct _GUID *a4)
{
  unsigned int v8; // edx
  struct _SECURITY_ATTRIBUTES *v9; // r9
  int v10; // eax
  int v11; // edi
  LSTATUS v12; // eax
  HKEY v13; // rsi
  HKEY v14; // r14
  DWORD LastError; // ebx
  DWORD v16; // ebx
  HKEY v17; // rsi
  DWORD v18; // ebx
  LSTATUS v20; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v22; // r9
  HKEY v23; // rdi
  DWORD v24; // ebx
  LSTATUS v25; // eax
  int v26; // r8d
  int v27; // r9d
  int lpcValues; // [rsp+38h] [rbp-C8h]
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  DWORD dwDisposition; // [rsp+70h] [rbp-90h] BYREF
  DWORD cSubKeys; // [rsp+74h] [rbp-8Ch] BYREF
  HKEY v33; // [rsp+78h] [rbp-88h] BYREF
  const unsigned __int16 *v34; // [rsp+80h] [rbp-80h] BYREF
  char v35; // [rsp+88h] [rbp-78h] BYREF
  GUID rguid; // [rsp+90h] [rbp-70h] BYREF
  GUID pguid; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v38[16]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v39[32]; // [rsp+C0h] [rbp-40h] BYREF
  OLECHAR sz[40]; // [rsp+E0h] [rbp-20h] BYREF

  phkResult = 0;
  v33 = 0;
  dwDisposition = 0;
  cSubKeys = 0;
  memset_0(sz, 0, 0x4Eu);
  pguid = GUID_NULL;
  v34 = a1;
  *(_QWORD *)&rguid.Data1 = &v34;
  *(_QWORD *)rguid.Data4 = &v35;
  NfcRegPath::NfcRegPath(v38, &qword_1800A1C18, &rguid);
  hKey = 0;
  v10 = NfcRegCreateKeyEx((const struct NfcRegistryLocation *)v38, v8, 0x2001Fu, v9, &hKey, &dwDisposition);
  v11 = v10;
  if ( v10 > 0 )
    v11 = (unsigned __int16)v10 | 0x80070000;
  if ( v11 < 0 )
    goto LABEL_9;
  v12 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
  v11 = v12;
  if ( v12 > 0 )
    v11 = (unsigned __int16)v12 | 0x80070000;
  if ( v11 < 0 )
    goto LABEL_9;
  if ( cSubKeys >= 0x64 )
  {
    v11 = -2134834669;
    goto LABEL_9;
  }
  v11 = CoCreateGuid(&pguid);
  if ( v11 < 0 )
  {
LABEL_9:
    v13 = hKey;
    if ( hKey )
    {
      v14 = v33;
      if ( v33 )
      {
        LastError = GetLastError();
        RegCloseKey(v14);
        SetLastError(LastError);
        v13 = hKey;
      }
      v33 = 0;
      if ( v13 )
      {
        v16 = GetLastError();
        RegCloseKey(v13);
        SetLastError(v16);
      }
      hKey = 0;
      v17 = phkResult;
      if ( phkResult )
      {
        v18 = GetLastError();
        RegCloseKey(v17);
        SetLastError(v18);
      }
      phkResult = 0;
      rguid = pguid;
      RoutingRegistryHelper::RemoveAppletIdGroupRegKeys(a1, &rguid);
    }
    goto LABEL_17;
  }
  if ( !StringFromGUID2(&pguid, sz, 39) )
  {
    v11 = -2147467259;
    goto LABEL_9;
  }
  phkResult = 0;
  v20 = RegCreateKeyExW(hKey, sz, 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition);
  v11 = v20;
  if ( v20 > 0 )
    v11 = (unsigned __int16)v20 | 0x80070000;
  if ( v11 < 0 )
    goto LABEL_9;
  if ( dwDisposition != 1 )
  {
    v11 = -2147418113;
    goto LABEL_9;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)a2 + 22), 0);
  LOBYTE(v22) = *((_BYTE *)a2 + 8) != 0;
  LOBYTE(lpcValues) = *((_BYTE *)a2 + 168) != 0;
  v11 = RoutingRegistryHelper::WriteAppletIdGroupFields(
          phkResult,
          *((unsigned int *)a2 + 1),
          *(unsigned int *)a2,
          v22,
          (char *)a2 + 10,
          *((_DWORD *)a2 + 38),
          *((_QWORD *)a2 + 20),
          lpcValues,
          StringRawBuffer);
  if ( v11 < 0 )
    goto LABEL_9;
  v11 = RoutingRegistryHelper::WriteAppletIdRegKeys(phkResult, *((struct _AppletId **)a2 + 18), *((_DWORD *)a2 + 35));
  if ( v11 < 0 )
    goto LABEL_9;
  v23 = v33;
  if ( v33 )
  {
    v24 = GetLastError();
    RegCloseKey(v23);
    SetLastError(v24);
  }
  v33 = 0;
  v25 = RegCreateKeyExW(phkResult, L"Assets", 0, 0, 0, 0x2001Fu, 0, &v33, 0);
  v11 = v25;
  if ( v25 > 0 )
    v11 = (unsigned __int16)v25 | 0x80070000;
  if ( v11 < 0 )
    goto LABEL_9;
  v11 = RoutingRegistryHelper::WriteAppletIdGroupAssetsRegKeys(v33, a1, &pguid, a3);
  if ( v11 < 0 )
    goto LABEL_9;
  *a4 = pguid;
  if ( (unsigned int)dword_18012F048 > 5
    && (qword_18012F058 & 0x400000000000LL) != 0
    && (qword_18012F060 & 0x400000000000LL) == qword_18012F060 )
  {
    LODWORD(v34) = cSubKeys + 1;
    *(_QWORD *)&rguid.Data1 = a1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      qword_18012F060,
      (unsigned int)&dword_18011CB5C,
      v26,
      v27,
      (__int64)&rguid,
      (__int64)&v34);
  }
LABEL_17:
  std::wstring::~wstring(v39);
  if ( v33 )
    RegCloseKey(v33);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18003bc1c  push    rbp
0x18003bc1e  push    rbx
0x18003bc1f  push    rsi
0x18003bc20  push    rdi
0x18003bc21  push    r12
0x18003bc23  push    r13
0x18003bc25  push    r14
0x18003bc27  push    r15
0x18003bc29  lea     rbp, [rsp-48h]
0x18003bc2e  sub     rsp, 148h
0x18003bc35  mov     rax, cs:__security_cookie
0x18003bc3c  xor     rax, rsp
0x18003bc3f  mov     [rbp+80h+var_50], rax
0x18003bc43  mov     r14, r9
0x18003bc46  mov     r12, r8
0x18003bc49  mov     rsi, rdx
0x18003bc4c  mov     r15, rcx
0x18003bc4f  xor     r13d, r13d
0x18003bc52  mov     [rsp+180h+hKey], r13
0x18003bc57  mov     [rsp+180h+phkResult], r13
0x18003bc5c  mov     [rsp+180h+var_108], r13
0x18003bc61  mov     [rsp+180h+dwDisposition], r13d
0x18003bc66  mov     [rsp+180h+cSubKeys], r13d
0x18003bc6b  xor     edx, edx; Val
0x18003bc6d  lea     r8d, [r13+4Eh]; Size
0x18003bc71  lea     rcx, [rbp+80h+sz]; void *
0x18003bc75  call    memset_0
0x18003bc7a  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18003bc81  movdqu  xmmword ptr [rbp+80h+pguid.Data1], xmm0
0x18003bc86  mov     [rbp+80h+var_100], r15
0x18003bc8a  lea     rax, [rbp+80h+var_100]
0x18003bc8e  mov     qword ptr [rbp+80h+rguid.Data1], rax
0x18003bc92  lea     rax, [rbp+80h+var_F8]
0x18003bc96  mov     qword ptr [rbp+80h+rguid.Data4], rax
0x18003bc9a  lea     r8, [rbp+80h+rguid]
0x18003bc9e  lea     rdx, qword_1800A1C18
0x18003bca5  lea     rcx, [rbp+80h+var_D0]
0x18003bca9  call    ??0NfcRegPath@@QEAA@AEBUNfcRegistryLocation@@V?$initializer_list@PEBG@std@@@Z; NfcRegPath::NfcRegPath(NfcRegistryLocation const &,std::initializer_list<ushort const *>)
0x18003bcae  nop
0x18003bcaf  mov     rdi, [rsp+180h+hKey]
0x18003bcb4  test    rdi, rdi
0x18003bcb7  jz      short loc_18003BCD2
0x18003bcb9  call    cs:__imp_GetLastError
0x18003bcbf  mov     ebx, eax
0x18003bcc1  mov     rcx, rdi; hKey
0x18003bcc4  call    cs:__imp_RegCloseKey
0x18003bcca  mov     ecx, ebx; dwErrCode
0x18003bccc  call    cs:__imp_SetLastError
0x18003bcd2  mov     [rsp+180h+hKey], r13
0x18003bcd7  lea     rax, [rsp+180h+dwDisposition]
0x18003bcdc  mov     [rsp+180h+lpcbMaxSubKeyLen], rax; unsigned int *
0x18003bce1  lea     rax, [rsp+180h+hKey]
0x18003bce6  mov     [rsp+180h+lpcSubKeys], rax; HKEY *
0x18003bceb  mov     r8d, 2001Fh; unsigned int
0x18003bcf1  lea     rcx, [rbp+80h+var_D0]; struct NfcRegistryLocation *
0x18003bcf5  call    ?NfcRegCreateKeyEx@@YAJAEBUNfcRegistryLocation@@KKPEAU_SECURITY_ATTRIBUTES@@PEAPEAUHKEY__@@PEAK@Z; NfcRegCreateKeyEx(NfcRegistryLocation const &,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x18003bcfa  mov     edi, eax
0x18003bcfc  mov     ebx, 80070000h
0x18003bd01  test    eax, eax
0x18003bd03  jle     short loc_18003BD0A
0x18003bd05  movzx   edi, ax
0x18003bd08  or      edi, ebx
0x18003bd0a  test    edi, edi
0x18003bd0c  js      short loc_18003BD6D
0x18003bd0e  mov     [rsp+180h+lpftLastWriteTime], r13; lpftLastWriteTime
0x18003bd13  mov     [rsp+180h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x18003bd18  mov     [rsp+180h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x18003bd1d  mov     [rsp+180h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x18003bd22  mov     [rsp+180h+lpcValues], r13; lpcValues
0x18003bd27  mov     [rsp+180h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x18003bd2c  mov     [rsp+180h+lpcbMaxSubKeyLen], r13; lpcbMaxSubKeyLen
0x18003bd31  lea     rax, [rsp+180h+cSubKeys]
0x18003bd36  mov     [rsp+180h+lpcSubKeys], rax; lpcSubKeys
0x18003bd3b  xor     r9d, r9d; lpReserved
0x18003bd3e  xor     r8d, r8d; lpcchClass
0x18003bd41  xor     edx, edx; lpClass
0x18003bd43  mov     rcx, [rsp+180h+hKey]; hKey
0x18003bd48  call    cs:__imp_RegQueryInfoKeyW
0x18003bd4e  mov     edi, eax
0x18003bd50  test    eax, eax
0x18003bd52  jle     short loc_18003BD59
0x18003bd54  movzx   edi, ax
0x18003bd57  or      edi, ebx
0x18003bd59  test    edi, edi
0x18003bd5b  js      short loc_18003BD6D
0x18003bd5d  cmp     [rsp+180h+cSubKeys], 64h ; 'd'
0x18003bd62  jb      loc_18003BE67
0x18003bd68  mov     edi, 80C10213h
0x18003bd6d  mov     rsi, [rsp+180h+hKey]
0x18003bd72  test    rsi, rsi
0x18003bd75  jz      loc_18003BE09
0x18003bd7b  mov     r14, [rsp+180h+var_108]
0x18003bd80  test    r14, r14
0x18003bd83  jz      short loc_18003BDA3
0x18003bd85  call    cs:__imp_GetLastError
0x18003bd8b  mov     ebx, eax
0x18003bd8d  mov     rcx, r14; hKey
0x18003bd90  call    cs:__imp_RegCloseKey
0x18003bd96  mov     ecx, ebx; dwErrCode
0x18003bd98  call    cs:__imp_SetLastError
0x18003bd9e  mov     rsi, [rsp+180h+hKey]
0x18003bda3  mov     [rsp+180h+var_108], r13
0x18003bda8  test    rsi, rsi
0x18003bdab  jz      short loc_18003BDC6
0x18003bdad  call    cs:__imp_GetLastError
0x18003bdb3  mov     ebx, eax
0x18003bdb5  mov     rcx, rsi; hKey
0x18003bdb8  call    cs:__imp_RegCloseKey
0x18003bdbe  mov     ecx, ebx; dwErrCode
0x18003bdc0  call    cs:__imp_SetLastError
0x18003bdc6  mov     [rsp+180h+hKey], r13
0x18003bdcb  mov     rsi, [rsp+180h+phkResult]
0x18003bdd0  test    rsi, rsi
0x18003bdd3  jz      short loc_18003BDEE
0x18003bdd5  call    cs:__imp_GetLastError
0x18003bddb  mov     ebx, eax
0x18003bddd  mov     rcx, rsi; hKey
0x18003bde0  call    cs:__imp_RegCloseKey
0x18003bde6  mov     ecx, ebx; dwErrCode
0x18003bde8  call    cs:__imp_SetLastError
0x18003bdee  mov     [rsp+180h+phkResult], r13
0x18003bdf3  movaps  xmm0, xmmword ptr [rbp+80h+pguid.Data1]
0x18003bdf7  movdqa  xmmword ptr [rbp+80h+rguid.Data1], xmm0
0x18003bdfc  lea     rdx, [rbp+80h+rguid]; rguid
0x18003be00  mov     rcx, r15; unsigned __int16 *
0x18003be03  call    ?RemoveAppletIdGroupRegKeys@RoutingRegistryHelper@@SAJPEBGU_GUID@@@Z; RoutingRegistryHelper::RemoveAppletIdGroupRegKeys(ushort const *,_GUID)
0x18003be08  nop
0x18003be09  lea     rcx, [rbp+80h+var_C0]
0x18003be0d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003be12  nop
0x18003be13  mov     rcx, [rsp+180h+var_108]; hKey
0x18003be18  test    rcx, rcx
0x18003be1b  jz      short loc_18003BE24
0x18003be1d  call    cs:__imp_RegCloseKey
0x18003be23  nop
0x18003be24  mov     rcx, [rsp+180h+phkResult]; hKey
0x18003be29  test    rcx, rcx
0x18003be2c  jz      short loc_18003BE35
0x18003be2e  call    cs:__imp_RegCloseKey
0x18003be34  nop
0x18003be35  mov     rcx, [rsp+180h+hKey]; hKey
0x18003be3a  test    rcx, rcx
0x18003be3d  jz      short loc_18003BE45
0x18003be3f  call    cs:__imp_RegCloseKey
0x18003be45  mov     eax, edi
0x18003be47  mov     rcx, [rbp+80h+var_50]
0x18003be4b  xor     rcx, rsp; StackCookie
0x18003be4e  call    __security_check_cookie
0x18003be53  add     rsp, 148h
0x18003be5a  pop     r15
0x18003be5c  pop     r14
0x18003be5e  pop     r13
0x18003be60  pop     r12
0x18003be62  pop     rdi
0x18003be63  pop     rsi
0x18003be64  pop     rbx
0x18003be65  pop     rbp
0x18003be66  retn
0x18003be67  lea     rcx, [rbp+80h+pguid]; pguid
0x18003be6b  call    cs:__imp_CoCreateGuid
0x18003be71  mov     edi, eax
0x18003be73  test    eax, eax
0x18003be75  js      loc_18003BD6D
0x18003be7b  mov     r8d, 27h ; '''; cchMax
0x18003be81  lea     rdx, [rbp+80h+sz]; lpsz
0x18003be85  lea     rcx, [rbp+80h+pguid]; rguid
0x18003be89  call    cs:__imp_StringFromGUID2
0x18003be8f  test    eax, eax
0x18003be91  jnz     short loc_18003BE9D
0x18003be93  mov     edi, 80004005h
0x18003be98  jmp     loc_18003BD6D
0x18003be9d  mov     rdi, [rsp+180h+phkResult]
0x18003bea2  test    rdi, rdi
0x18003bea5  jz      short loc_18003BEC5
0x18003bea7  call    cs:__imp_GetLastError
0x18003bead  mov     ebx, eax
0x18003beaf  mov     rcx, rdi; hKey
0x18003beb2  call    cs:__imp_RegCloseKey
0x18003beb8  mov     ecx, ebx; dwErrCode
0x18003beba  call    cs:__imp_SetLastError
0x18003bec0  mov     ebx, 80070000h
0x18003bec5  mov     [rsp+180h+phkResult], r13
0x18003beca  lea     rax, [rsp+180h+dwDisposition]
0x18003becf  mov     [rsp+180h+lpcbMaxValueNameLen], rax; lpdwDisposition
0x18003bed4  lea     rax, [rsp+180h+phkResult]
0x18003bed9  mov     [rsp+180h+lpcValues], rax; phkResult
0x18003bede  mov     [rsp+180h+lpcbMaxClassLen], r13; lpSecurityAttributes
0x18003bee3  mov     dword ptr [rsp+180h+lpcbMaxSubKeyLen], 2001Fh; samDesired
0x18003beeb  mov     dword ptr [rsp+180h+lpcSubKeys], r13d; dwOptions
0x18003bef0  xor     r9d, r9d; lpClass
0x18003bef3  xor     r8d, r8d; Reserved
0x18003bef6  lea     rdx, [rbp+80h+sz]; lpSubKey
0x18003befa  mov     rcx, [rsp+180h+hKey]; hKey
0x18003beff  call    cs:__imp_RegCreateKeyExW
0x18003bf05  mov     edi, eax
0x18003bf07  test    eax, eax
0x18003bf09  jle     short loc_18003BF10
0x18003bf0b  movzx   edi, ax
0x18003bf0e  or      edi, ebx
0x18003bf10  test    edi, edi
0x18003bf12  js      loc_18003BD6D
0x18003bf18  cmp     [rsp+180h+dwDisposition], 1
0x18003bf1d  jz      short loc_18003BF29
0x18003bf1f  mov     edi, 8000FFFFh
0x18003bf24  jmp     loc_18003BD6D
0x18003bf29  xor     edx, edx; length
0x18003bf2b  mov     rcx, [rsi+0B0h]; string
0x18003bf32  call    cs:__imp_WindowsGetStringRawBuffer
0x18003bf38  cmp     [rsi+0A8h], r13b
0x18003bf3f  setnz   cl
0x18003bf42  lea     r8, [rsi+0Ah]
0x18003bf46  cmp     [rsi+8], r13b
0x18003bf4a  setnz   r9b
0x18003bf4e  mov     [rsp+180h+lpcbMaxValueNameLen], rax
0x18003bf53  mov     byte ptr [rsp+180h+lpcValues], cl
0x18003bf57  mov     rax, [rsi+0A0h]
0x18003bf5e  mov     [rsp+180h+lpcbMaxClassLen], rax
0x18003bf63  mov     eax, [rsi+98h]
0x18003bf69  mov     dword ptr [rsp+180h+lpcbMaxSubKeyLen], eax
0x18003bf6d  mov     [rsp+180h+lpcSubKeys], r8
0x18003bf72  mov     r8d, [rsi]
0x18003bf75  mov     edx, [rsi+4]
0x18003bf78  mov     rcx, [rsp+180h+phkResult]
0x18003bf7d  call    ?WriteAppletIdGroupFields@RoutingRegistryHelper@@CAJPEAUHKEY__@@W4SecureElementType@@W4SmartCardEmulationCategory@@_NPEBGIPEBE34@Z; RoutingRegistryHelper::WriteAppletIdGroupFields(HKEY__ *,SecureElementType,SmartCardEmulationCategory,bool,ushort const *,uint,uchar const *,bool,ushort const *)
0x18003bf82  mov     edi, eax
0x18003bf84  test    eax, eax
0x18003bf86  js      loc_18003BD6D
0x18003bf8c  mov     r8d, [rsi+8Ch]; unsigned int
0x18003bf93  mov     rdx, [rsi+90h]; struct _AppletId *
0x18003bf9a  mov     rcx, [rsp+180h+phkResult]; HKEY
0x18003bf9f  call    ?WriteAppletIdRegKeys@RoutingRegistryHelper@@CAJPEAUHKEY__@@PEAU_AppletId@@K@Z; RoutingRegistryHelper::WriteAppletIdRegKeys(HKEY__ *,_AppletId *,ulong)
0x18003bfa4  mov     edi, eax
0x18003bfa6  test    eax, eax
0x18003bfa8  js      loc_18003BD6D
0x18003bfae  mov     rdi, [rsp+180h+var_108]
0x18003bfb3  test    rdi, rdi
0x18003bfb6  jz      short loc_18003BFD1
0x18003bfb8  call    cs:__imp_GetLastError
0x18003bfbe  mov     ebx, eax
0x18003bfc0  mov     rcx, rdi; hKey
0x18003bfc3  call    cs:__imp_RegCloseKey
0x18003bfc9  mov     ecx, ebx; dwErrCode
0x18003bfcb  call    cs:__imp_SetLastError
0x18003bfd1  mov     [rsp+180h+var_108], r13
0x18003bfd6  mov     [rsp+180h+lpcbMaxValueNameLen], r13; lpdwDisposition
0x18003bfdb  lea     rax, [rsp+180h+var_108]
0x18003bfe0  mov     [rsp+180h+lpcValues], rax; phkResult
0x18003bfe5  mov     [rsp+180h+lpcbMaxClassLen], r13; lpSecurityAttributes
0x18003bfea  mov     dword ptr [rsp+180h+lpcbMaxSubKeyLen], 2001Fh; samDesired
0x18003bff2  mov     dword ptr [rsp+180h+lpcSubKeys], r13d; dwOptions
0x18003bff7  xor     r9d, r9d; lpClass
0x18003bffa  xor     r8d, r8d; Reserved
0x18003bffd  lea     rdx, SubKey; "Assets"
0x18003c004  mov     rcx, [rsp+180h+phkResult]; hKey
0x18003c009  call    cs:__imp_RegCreateKeyExW
0x18003c00f  mov     edi, eax
0x18003c011  test    eax, eax
0x18003c013  jle     short loc_18003C01E
0x18003c015  movzx   edi, ax
0x18003c018  or      edi, 80070000h
0x18003c01e  test    edi, edi
0x18003c020  js      loc_18003BD6D
0x18003c026  mov     r9, r12; struct _AppletIdGroupAssetCollection *
0x18003c029  lea     r8, [rbp+80h+pguid]; struct _GUID *
0x18003c02d  mov     rdx, r15; unsigned __int16 *
0x18003c030  mov     rcx, [rsp+180h+var_108]; HKEY
0x18003c035  call    ?WriteAppletIdGroupAssetsRegKeys@RoutingRegistryHelper@@CAJPEAUHKEY__@@PEBGAEBU_GUID@@PEBU_AppletIdGroupAssetCollection@@@Z; RoutingRegistryHelper::WriteAppletIdGroupAssetsRegKeys(HKEY__ *,ushort const *,_GUID const &,_AppletIdGroupAssetCollection const *)
0x18003c03a  mov     edi, eax
0x18003c03c  test    eax, eax
0x18003c03e  js      loc_18003BD6D
0x18003c044  movaps  xmm0, xmmword ptr [rbp+80h+pguid.Data1]
0x18003c048  movdqu  xmmword ptr [r14], xmm0
0x18003c04d  mov     eax, cs:dword_18012F048
0x18003c053  cmp     eax, 5
0x18003c056  jbe     loc_18003BE09
0x18003c05c  mov     rcx, cs:qword_18012F060
0x18003c063  mov     rax, cs:qword_18012F058
0x18003c06a  mov     rdx, 400000000000h
0x18003c074  test    rdx, rax
0x18003c077  jz      loc_18003BE09
0x18003c07d  mov     rax, rcx
0x18003c080  and     rax, rdx
0x18003c083  cmp     rax, rcx
0x18003c086  jnz     loc_18003BE09
0x18003c08c  mov     eax, [rsp+180h+cSubKeys]
0x18003c090  inc     eax
0x18003c092  mov     dword ptr [rbp+80h+var_100], eax
0x18003c095  mov     qword ptr [rbp+80h+rguid.Data1], r15
0x18003c099  lea     rax, [rbp+80h+var_100]
0x18003c09d  mov     [rsp+180h+lpcbMaxSubKeyLen], rax
0x18003c0a2  lea     rax, [rbp+80h+rguid]
0x18003c0a6  mov     [rsp+180h+lpcSubKeys], rax
0x18003c0ab  lea     rdx, dword_18011CB5C
0x18003c0b2  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18003c0b7  jmp     loc_18003BE09
```
