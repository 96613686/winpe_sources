# NgcUtils::Detail::CacheRemoveUser(ushort const * const)

- ea: `0x18005bd7c`
- end: `0x18005be84`
- name: `?CacheRemoveUser@Detail@NgcUtils@@YAJQEBG@Z`
- size: `264`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, const unsigned __int16 *const)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180027648`
- `0x18005bcac`

## callees

- `0x180018a9c`
- `0x1800199d8`
- `0x18001a77c`
- `0x180023278`
- `0x1800232a0`
- `0x1800264b8`
- `0x18002b0dc`
- `0x18005bd7c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18005be49`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18005be49`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005be0a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005be0a`

## string_xrefs

- `0x18005bdc4`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`
- `0x18005be24`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`

## pseudocode

```c
__int64 __fastcall NgcUtils::Detail::CacheRemoveUser(LPCWSTR lpSubKey, const unsigned __int16 *const a2)
{
  int NgcStateSeparatedRegistryLocation; // eax
  unsigned int v4; // ebx
  HKEY *v5; // rax
  unsigned int v6; // eax
  __int64 v7; // rdx
  unsigned __int16 **phkResult; // [rsp+20h] [rbp-18h]
  int phkResulta; // [rsp+20h] [rbp-18h]
  unsigned int phkResultb; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF
  LPCWSTR lpSubKeya; // [rsp+50h] [rbp+18h] BYREF

  lpSubKeya = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &lpSubKeya,
    0);
  NgcStateSeparatedRegistryLocation = NgcUtils::GetNgcStateSeparatedRegistryLocation(
                                        (NgcUtils *)L"NgcCredprov",
                                        L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Authentication\\Credential Provide"
                                         "rs\\{D6886603-9D2F-4EB2-B667-1971041FA96B}",
                                        0,
                                        (const unsigned __int16 *)&lpSubKeya,
                                        phkResult);
  v4 = NgcStateSeparatedRegistryLocation;
  if ( NgcStateSeparatedRegistryLocation >= 0 )
  {
    hKey = 0;
    v5 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
    v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKeya, 0, 0x2001Fu, v5);
    if ( v6 )
    {
      v7 = 1295;
    }
    else
    {
      v6 = RegDeleteTreeW(hKey, lpSubKey);
      if ( !v6 )
      {
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        v4 = 0;
        goto LABEL_9;
      }
      v7 = 1300;
    }
    v4 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v7,
           (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
           (const char *)v6,
           phkResultb);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x506,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
      (const char *)(unsigned int)NgcStateSeparatedRegistryLocation,
      phkResulta);
  }
LABEL_9:
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&lpSubKeya);
  return v4;
}

```

## disassembly

```asm
0x18005bd7c  mov     [rsp+arg_0], rbx
0x18005bd81  push    rdi
0x18005bd82  sub     rsp, 30h
0x18005bd86  mov     rdi, rcx
0x18005bd89  mov     [rsp+38h+lpSubKey], 0
0x18005bd92  lea     rcx, [rsp+38h+lpSubKey]
0x18005bd97  xor     edx, edx
0x18005bd99  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18005bd9e  lea     r9, [rsp+38h+lpSubKey]; unsigned __int16 *
0x18005bda3  xor     r8d, r8d; unsigned __int16 *
0x18005bda6  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18005bdad  lea     rcx, aNgccredprov; "NgcCredprov"
0x18005bdb4  call    ?GetNgcStateSeparatedRegistryLocation@NgcUtils@@YAJPEBG00PEAPEAG@Z; NgcUtils::GetNgcStateSeparatedRegistryLocation(ushort const *,ushort const *,ushort const *,ushort * *)
0x18005bdb9  mov     ebx, eax
0x18005bdbb  test    eax, eax
0x18005bdbd  jns     short loc_18005BDDD
0x18005bdbf  mov     rcx, [rsp+38h]; this
0x18005bdc4  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18005bdcb  mov     r9d, eax; char *
0x18005bdce  mov     edx, 506h; void *
0x18005bdd3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005bdd8  jmp     loc_18005BE6C
0x18005bddd  lea     rcx, [rsp+38h+hKey]
0x18005bde2  mov     [rsp+38h+hKey], 0
0x18005bdeb  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18005bdf0  mov     rdx, [rsp+38h+lpSubKey]; lpSubKey
0x18005bdf5  mov     r9d, 2001Fh; samDesired
0x18005bdfb  xor     r8d, r8d; ulOptions
0x18005bdfe  mov     [rsp+38h+phkResult], rax; unsigned int
0x18005be03  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005be0a  call    cs:__imp_RegOpenKeyExW
0x18005be11  nop     dword ptr [rax+rax+00h]
0x18005be16  test    eax, eax
0x18005be18  jz      short loc_18005BE41
0x18005be1a  mov     edx, 50Fh; void *
0x18005be1f  mov     rcx, [rsp+38h]; this
0x18005be24  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18005be2b  mov     r9d, eax; char *
0x18005be2e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18005be33  lea     rcx, [rsp+38h+hKey]
0x18005be38  mov     ebx, eax
0x18005be3a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005be3f  jmp     short loc_18005BE6C
0x18005be41  mov     rcx, [rsp+38h+hKey]; hKey
0x18005be46  mov     rdx, rdi; lpSubKey
0x18005be49  call    cs:__imp_RegDeleteTreeW
0x18005be50  nop     dword ptr [rax+rax+00h]
0x18005be55  test    eax, eax
0x18005be57  jz      short loc_18005BE60
0x18005be59  mov     edx, 514h
0x18005be5e  jmp     short loc_18005BE1F
0x18005be60  lea     rcx, [rsp+38h+hKey]
0x18005be65  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005be6a  xor     ebx, ebx
0x18005be6c  lea     rcx, [rsp+38h+lpSubKey]
0x18005be71  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18005be76  mov     eax, ebx
0x18005be78  mov     rbx, [rsp+38h+arg_0]
0x18005be7d  add     rsp, 30h
0x18005be81  pop     rdi
0x18005be82  retn
```
