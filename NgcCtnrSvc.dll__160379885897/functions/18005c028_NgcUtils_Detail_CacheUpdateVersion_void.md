# NgcUtils::Detail::CacheUpdateVersion(void)

- ea: `0x18005c028`
- end: `0x18005c1dd`
- name: `?CacheUpdateVersion@Detail@NgcUtils@@YAJXZ`
- size: `437`
- prototype: `__int64 __fastcall(NgcUtils::Detail *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18005bcac`

## callees

- `0x180018a9c`
- `0x1800199d8`
- `0x18001a77c`
- `0x180023278`
- `0x1800232a0`
- `0x1800264b8`
- `0x180026e6c`
- `0x180027648`
- `0x18002b0dc`
- `0x18005c028`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005c120`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005c120`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005c1a5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005c1a5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005c0ac`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005c0ac`

## string_xrefs

- `0x18005c06c`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`
- `0x18005c0c1`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`
- `0x18005c145`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`
- `0x18005c113`: `CacheVersion`
- `0x18005c19a`: `CacheVersion`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall NgcUtils::Detail::CacheUpdateVersion(NgcUtils::Detail *this)
{
  int NgcStateSeparatedRegistryLocation; // eax
  unsigned int v2; // ebx
  HKEY *v3; // rax
  unsigned int v4; // eax
  __int64 v5; // rdx
  LSTATUS ValueW; // eax
  NgcUtils::Detail *v7; // rcx
  __int64 v8; // rdx
  NgcUtils::Detail *v9; // rcx
  int phkResult; // [rsp+20h] [rbp-28h]
  unsigned int phkResulta; // [rsp+20h] [rbp-28h]
  int phkResultb; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+10h]
  unsigned int pvData; // [rsp+60h] [rbp+18h] BYREF
  DWORD pcbData; // [rsp+68h] [rbp+20h] BYREF
  HKEY hkey; // [rsp+70h] [rbp+28h] BYREF
  LPCWSTR lpSubKey; // [rsp+78h] [rbp+30h] BYREF

  lpSubKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &lpSubKey,
    0);
  NgcStateSeparatedRegistryLocation = NgcUtils::GetNgcStateSeparatedRegistryLocation(
                                        (NgcUtils *)L"NgcCredprov",
                                        L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Authentication\\Credential Provide"
                                         "rs\\{D6886603-9D2F-4EB2-B667-1971041FA96B}",
                                        0,
                                        (unsigned __int16 *)&lpSubKey);
  v2 = NgcStateSeparatedRegistryLocation;
  if ( NgcStateSeparatedRegistryLocation >= 0 )
  {
    hkey = 0;
    v3 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hkey);
    v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x2001Fu, v3);
    if ( v4 )
    {
      v5 = 1678;
LABEL_5:
      v2 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v5,
             (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
             (const char *)v4,
             phkResulta);
LABEL_6:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
      goto LABEL_19;
    }
    pvData = 0;
    pcbData = 4;
    ValueW = RegGetValueW(hkey, 0, L"CacheVersion", 0x10u, 0, &pvData, &pcbData);
    v2 = ValueW;
    if ( (ValueW & 0xFFFFFFFD) != 0 )
    {
      if ( ValueW >= 0 )
        goto LABEL_6;
      v8 = 1694;
LABEL_10:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
        (const char *)(unsigned int)ValueW,
        phkResultb);
      goto LABEL_6;
    }
    if ( pvData < 2 )
    {
      ValueW = NgcUtils::Detail::CacheCleanupMultipleSidsForUser(v7);
      v2 = ValueW;
      if ( ValueW < 0 )
      {
        v8 = 1703;
        goto LABEL_10;
      }
      ValueW = NgcUtils::Detail::CacheCleanupMultipleUsersForSid(v9);
      v2 = ValueW;
      if ( ValueW < 0 )
      {
        v8 = 1706;
        goto LABEL_10;
      }
      v4 = RegSetValueExW(hkey, L"CacheVersion", 0, 4u, &Data, 4u);
      if ( v4 )
      {
        v5 = 1716;
        goto LABEL_5;
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
    v2 = 0;
    goto LABEL_19;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x685,
    (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
    (const char *)(unsigned int)NgcStateSeparatedRegistryLocation,
    phkResult);
LABEL_19:
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&lpSubKey);
  return v2;
}

```

## disassembly

```asm
0x18005c028  push    rbp
0x18005c02a  push    rbx
0x18005c02b  mov     rbp, rsp
0x18005c02e  sub     rsp, 48h
0x18005c032  mov     [rbp+lpSubKey], 0
0x18005c03a  xor     edx, edx
0x18005c03c  lea     rcx, [rbp+lpSubKey]
0x18005c040  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18005c045  lea     r9, [rbp+lpSubKey]; unsigned __int16 *
0x18005c049  xor     r8d, r8d; unsigned __int16 *
0x18005c04c  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18005c053  lea     rcx, aNgccredprov; "NgcCredprov"
0x18005c05a  call    ?GetNgcStateSeparatedRegistryLocation@NgcUtils@@YAJPEBG00PEAPEAG@Z; NgcUtils::GetNgcStateSeparatedRegistryLocation(ushort const *,ushort const *,ushort const *,ushort * *)
0x18005c05f  mov     ebx, eax
0x18005c061  test    eax, eax
0x18005c063  jns     short loc_18005C082
0x18005c065  mov     rcx, [rbp+10h]; this
0x18005c069  mov     r9d, eax; char *
0x18005c06c  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18005c073  mov     edx, 685h; void *
0x18005c078  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c07d  jmp     loc_18005C1CA
0x18005c082  mov     [rbp+hkey], 0
0x18005c08a  lea     rcx, [rbp+hkey]
0x18005c08e  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18005c093  mov     [rsp+48h+phkResult], rax; unsigned int
0x18005c098  mov     r9d, 2001Fh; samDesired
0x18005c09e  xor     r8d, r8d; ulOptions
0x18005c0a1  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x18005c0a5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005c0ac  call    cs:__imp_RegOpenKeyExW
0x18005c0b3  nop     dword ptr [rax+rax+00h]
0x18005c0b8  test    eax, eax
0x18005c0ba  jz      short loc_18005C0E4
0x18005c0bc  mov     edx, 68Eh; void *
0x18005c0c1  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18005c0c8  mov     r9d, eax; char *
0x18005c0cb  mov     rcx, [rbp+10h]; this
0x18005c0cf  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18005c0d4  mov     ebx, eax
0x18005c0d6  lea     rcx, [rbp+hkey]
0x18005c0da  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005c0df  jmp     loc_18005C1CA
0x18005c0e4  mov     [rbp+arg_0], 0
0x18005c0eb  mov     [rbp+arg_8], 4
0x18005c0f2  lea     rax, [rbp+arg_8]
0x18005c0f6  mov     [rsp+48h+pcbData], rax; pcbData
0x18005c0fb  lea     rax, [rbp+arg_0]
0x18005c0ff  mov     [rsp+48h+pvData], rax; pvData
0x18005c104  mov     [rsp+48h+phkResult], 0; int
0x18005c10d  mov     r9d, 10h; dwFlags
0x18005c113  lea     r8, aCacheversion; "CacheVersion"
0x18005c11a  xor     edx, edx; lpSubKey
0x18005c11c  mov     rcx, [rbp+hkey]; hkey
0x18005c120  call    cs:__imp_RegGetValueW
0x18005c127  nop     dword ptr [rax+rax+00h]
0x18005c12c  mov     ebx, eax
0x18005c12e  test    eax, 0FFFFFFFDh
0x18005c133  jz      short loc_18005C153
0x18005c135  test    eax, eax
0x18005c137  jns     short loc_18005C0D6
0x18005c139  mov     edx, 69Eh; void *
0x18005c13e  mov     rcx, [rbp+10h]; this
0x18005c142  mov     r9d, eax; char *
0x18005c145  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18005c14c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c151  jmp     short loc_18005C0D6
0x18005c153  cmp     [rbp+arg_0], 2
0x18005c157  jnb     short loc_18005C1BF
0x18005c159  call    ?CacheCleanupMultipleSidsForUser@Detail@NgcUtils@@YAJXZ; NgcUtils::Detail::CacheCleanupMultipleSidsForUser(void)
0x18005c15e  mov     ebx, eax
0x18005c160  test    eax, eax
0x18005c162  jns     short loc_18005C16B
0x18005c164  mov     edx, 6A7h
0x18005c169  jmp     short loc_18005C13E
0x18005c16b  call    ?CacheCleanupMultipleUsersForSid@Detail@NgcUtils@@YAJXZ; NgcUtils::Detail::CacheCleanupMultipleUsersForSid(void)
0x18005c170  mov     ebx, eax
0x18005c172  test    eax, eax
0x18005c174  jns     short loc_18005C17D
0x18005c176  mov     edx, 6AAh
0x18005c17b  jmp     short loc_18005C13E
0x18005c17d  mov     dword ptr [rsp+48h+pvData], 4; cbData
0x18005c185  lea     rax, Data
0x18005c18c  mov     [rsp+48h+phkResult], rax; lpData
0x18005c191  mov     r9d, 4; dwType
0x18005c197  xor     r8d, r8d; Reserved
0x18005c19a  lea     rdx, aCacheversion; "CacheVersion"
0x18005c1a1  mov     rcx, [rbp+hkey]; hKey
0x18005c1a5  call    cs:__imp_RegSetValueExW
0x18005c1ac  nop     dword ptr [rax+rax+00h]
0x18005c1b1  test    eax, eax
0x18005c1b3  jz      short loc_18005C1BF
0x18005c1b5  mov     edx, 6B4h
0x18005c1ba  jmp     loc_18005C0C1
0x18005c1bf  lea     rcx, [rbp+hkey]
0x18005c1c3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005c1c8  xor     ebx, ebx
0x18005c1ca  lea     rcx, [rbp+lpSubKey]
0x18005c1ce  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18005c1d3  mov     eax, ebx
0x18005c1d5  add     rsp, 48h
0x18005c1d9  pop     rbx
0x18005c1da  pop     rbp
0x18005c1db  retn
```
