# NgcUtils::Detail::CacheUpdateVersion(void)

- ea: `0x18008c740`
- end: `0x18008c8e8`
- name: `?CacheUpdateVersion@Detail@NgcUtils@@YAJXZ`
- size: `424`
- prototype: `__int64 __fastcall(NgcUtils::Detail *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18008b6d0`
- `0x18008d340`

## callees

- `0x180006b60`
- `0x18000782c`
- `0x1800281e0`
- `0x1800288a0`
- `0x180032b6c`
- `0x180032c20`
- `0x180048304`
- `0x180056438`
- `0x18008b900`
- `0x18008c740`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008c7ca`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008c7ca`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18008c838`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18008c838`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18008c8b7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18008c8b7`

## string_xrefs

- `0x18008c784`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`
- `0x18008c7d9`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`
- `0x18008c857`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`
- `0x18008c82b`: `CacheVersion`
- `0x18008c8ac`: `CacheVersion`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall NgcUtils::Detail::CacheUpdateVersion(NgcUtils::Detail *this)
{
  int NgcStateSeparatedRegistryLocation; // eax
  unsigned int v2; // ebx
  unsigned int v3; // eax
  __int64 v4; // rdx
  LSTATUS ValueW; // eax
  NgcUtils::Detail *v6; // rcx
  __int64 v7; // rdx
  NgcUtils::Detail *v8; // rcx
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
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hkey,
      0);
    v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x2001Fu, &hkey);
    if ( v3 )
    {
      v4 = 1678;
LABEL_5:
      v2 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v4,
             (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
             (const char *)v3,
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
      v7 = 1694;
LABEL_10:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v7,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
        (const char *)(unsigned int)ValueW,
        phkResultb);
      goto LABEL_6;
    }
    if ( pvData < 2 )
    {
      ValueW = NgcUtils::Detail::CacheCleanupMultipleSidsForUser(v6);
      v2 = ValueW;
      if ( ValueW < 0 )
      {
        v7 = 1703;
        goto LABEL_10;
      }
      ValueW = NgcUtils::Detail::CacheCleanupMultipleUsersForSid(v8);
      v2 = ValueW;
      if ( ValueW < 0 )
      {
        v7 = 1706;
        goto LABEL_10;
      }
      v3 = RegSetValueExW(hkey, L"CacheVersion", 0, 4u, &Data, 4u);
      if ( v3 )
      {
        v4 = 1716;
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
0x18008c740  push    rbp
0x18008c742  push    rbx
0x18008c743  mov     rbp, rsp
0x18008c746  sub     rsp, 48h
0x18008c74a  mov     [rbp+lpSubKey], 0
0x18008c752  xor     edx, edx
0x18008c754  lea     rcx, [rbp+lpSubKey]
0x18008c758  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18008c75d  lea     r9, [rbp+lpSubKey]; unsigned __int16 *
0x18008c761  xor     r8d, r8d; unsigned __int16 *
0x18008c764  lea     rdx, aSoftwareMicros_9; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18008c76b  lea     rcx, aNgccredprov; "NgcCredprov"
0x18008c772  call    ?GetNgcStateSeparatedRegistryLocation@NgcUtils@@YAJPEBG00PEAPEAG@Z; NgcUtils::GetNgcStateSeparatedRegistryLocation(ushort const *,ushort const *,ushort const *,ushort * *)
0x18008c777  mov     ebx, eax
0x18008c779  test    eax, eax
0x18008c77b  jns     short loc_18008C79A
0x18008c77d  mov     rcx, [rbp+10h]; this
0x18008c781  mov     r9d, eax; char *
0x18008c784  lea     r8, aOnecoreDsSecur_26; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18008c78b  mov     edx, 685h; void *
0x18008c790  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008c795  jmp     loc_18008C8D6
0x18008c79a  mov     [rbp+hkey], 0
0x18008c7a2  xor     edx, edx
0x18008c7a4  lea     rcx, [rbp+hkey]
0x18008c7a8  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18008c7ad  lea     rax, [rbp+hkey]
0x18008c7b1  mov     [rsp+48h+phkResult], rax; unsigned int
0x18008c7b6  mov     r9d, 2001Fh; samDesired
0x18008c7bc  xor     r8d, r8d; ulOptions
0x18008c7bf  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x18008c7c3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18008c7ca  call    cs:__imp_RegOpenKeyExW
0x18008c7d0  test    eax, eax
0x18008c7d2  jz      short loc_18008C7FC
0x18008c7d4  mov     edx, 68Eh; void *
0x18008c7d9  lea     r8, aOnecoreDsSecur_26; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18008c7e0  mov     r9d, eax; char *
0x18008c7e3  mov     rcx, [rbp+10h]; this
0x18008c7e7  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18008c7ec  mov     ebx, eax
0x18008c7ee  lea     rcx, [rbp+hkey]
0x18008c7f2  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18008c7f7  jmp     loc_18008C8D6
0x18008c7fc  mov     [rbp+arg_0], 0
0x18008c803  mov     [rbp+arg_8], 4
0x18008c80a  lea     rax, [rbp+arg_8]
0x18008c80e  mov     [rsp+48h+pcbData], rax; pcbData
0x18008c813  lea     rax, [rbp+arg_0]
0x18008c817  mov     [rsp+48h+pvData], rax; pvData
0x18008c81c  mov     [rsp+48h+phkResult], 0; int
0x18008c825  mov     r9d, 10h; dwFlags
0x18008c82b  lea     r8, aCacheversion; "CacheVersion"
0x18008c832  xor     edx, edx; lpSubKey
0x18008c834  mov     rcx, [rbp+hkey]; hkey
0x18008c838  call    cs:__imp_RegGetValueW
0x18008c83e  mov     ebx, eax
0x18008c840  test    eax, 0FFFFFFFDh
0x18008c845  jz      short loc_18008C865
0x18008c847  test    eax, eax
0x18008c849  jns     short loc_18008C7EE
0x18008c84b  mov     edx, 69Eh; void *
0x18008c850  mov     rcx, [rbp+10h]; this
0x18008c854  mov     r9d, eax; char *
0x18008c857  lea     r8, aOnecoreDsSecur_26; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18008c85e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008c863  jmp     short loc_18008C7EE
0x18008c865  cmp     [rbp+arg_0], 2
0x18008c869  jnb     short loc_18008C8CB
0x18008c86b  call    ?CacheCleanupMultipleSidsForUser@Detail@NgcUtils@@YAJXZ; NgcUtils::Detail::CacheCleanupMultipleSidsForUser(void)
0x18008c870  mov     ebx, eax
0x18008c872  test    eax, eax
0x18008c874  jns     short loc_18008C87D
0x18008c876  mov     edx, 6A7h
0x18008c87b  jmp     short loc_18008C850
0x18008c87d  call    ?CacheCleanupMultipleUsersForSid@Detail@NgcUtils@@YAJXZ; NgcUtils::Detail::CacheCleanupMultipleUsersForSid(void)
0x18008c882  mov     ebx, eax
0x18008c884  test    eax, eax
0x18008c886  jns     short loc_18008C88F
0x18008c888  mov     edx, 6AAh
0x18008c88d  jmp     short loc_18008C850
0x18008c88f  mov     dword ptr [rsp+48h+pvData], 4; cbData
0x18008c897  lea     rax, Data
0x18008c89e  mov     [rsp+48h+phkResult], rax; lpData
0x18008c8a3  mov     r9d, 4; dwType
0x18008c8a9  xor     r8d, r8d; Reserved
0x18008c8ac  lea     rdx, aCacheversion; "CacheVersion"
0x18008c8b3  mov     rcx, [rbp+hkey]; hKey
0x18008c8b7  call    cs:__imp_RegSetValueExW
0x18008c8bd  test    eax, eax
0x18008c8bf  jz      short loc_18008C8CB
0x18008c8c1  mov     edx, 6B4h
0x18008c8c6  jmp     loc_18008C7D9
0x18008c8cb  lea     rcx, [rbp+hkey]
0x18008c8cf  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18008c8d4  xor     ebx, ebx
0x18008c8d6  lea     rcx, [rbp+lpSubKey]; void *
0x18008c8da  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18008c8df  mov     eax, ebx
0x18008c8e1  add     rsp, 48h
0x18008c8e5  pop     rbx
0x18008c8e6  pop     rbp
0x18008c8e7  retn
```
