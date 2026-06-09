# PCPLoadUXFromRegistry(HINSTANCE__ * *)

- ea: `0x1800749b4`
- end: `0x180074cab`
- name: `?PCPLoadUXFromRegistry@@YAJPEAPEAUHINSTANCE__@@@Z`
- size: `759`
- prototype: `__int64 __fastcall(HINSTANCE *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18007db80`

## callees

- `0x18000f858`
- `0x1800133c4`
- `0x18001e100`
- `0x18001f2f0`
- `0x180020454`
- `0x180036ab4`
- `0x18004ddc8`
- `0x180061bac`
- `0x1800749b4`
- `0x180074cb4`
- `0x1800764d0`
- `0x1800768a0`
- `0x18007704c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180074bfe`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180074bfe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180074ac7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180074ac7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180074b33`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180074bb0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180074b33`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180074bb0`
- `ntdll!RtlGetPersistedStateLocation` at `0x180074a6b`
- `ntdll!RtlGetPersistedStateLocation` at `0x180074a6b`

## string_xrefs

- `0x1800749e2`: `PCPLoadUXFromRegistry`
- `0x180074c3a`: `PCPLoadUXFromRegistry`

## pseudocode

```c
__int64 __fastcall PCPLoadUXFromRegistry(HINSTANCE *a1)
{
  unsigned int LastError; // ebx
  int PersistedStateLocation; // eax
  __int64 v4; // rdx
  BYTE *v5; // rdi
  const struct std::nothrow_t *v6; // rdx
  HMODULE Library; // rax
  const char *v8; // r9
  const struct std::nothrow_t *v9; // rdx
  int phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  int phkResultb; // [rsp+20h] [rbp-E0h]
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  LPBYTE lpData; // [rsp+50h] [rbp-B0h] BYREF
  int v17; // [rsp+58h] [rbp-A8h]
  _BYTE v18[336]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR SubKey[264]; // [rsp+1B0h] [rbp+B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3D8h] [rbp+2D8h]

  KspDebugProvider::KspDebugActivity::Start<char const (&)[22]>(
    (KspDebugProvider::KspDebugActivity *)v18,
    "PCPLoadUXFromRegistry");
  if ( !a1 )
  {
    LastError = -2146893785;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12E,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
      (const char *)0x80090027LL,
      phkResult);
    goto LABEL_22;
  }
  *a1 = 0;
  memset_0(SubKey, 0, 0x208u);
  v17 = 520;
  PersistedStateLocation = RtlGetPersistedStateLocation(
                             L"PCPKSPProperties",
                             0,
                             L"System\\CurrentControlSet\\Control\\Cryptography\\Providers\\Microsoft Platform Crypto Prov"
                              "ider\\Properties",
                             0);
  if ( PersistedStateLocation < 0 )
  {
    LastError = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)0x13E,
                  (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
                  (const char *)(unsigned int)PersistedStateLocation,
                  (int)SubKey);
    goto LABEL_22;
  }
  hKey = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey) )
  {
    v4 = 328;
LABEL_7:
    LastError = -2146893794;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
      (const char *)0x8009001ELL,
      phkResulta);
LABEL_8:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    goto LABEL_22;
  }
  cbData = 0;
  if ( RegQueryValueExW(hKey, L"UXImage", 0, 0, 0, &cbData) )
  {
    v4 = 339;
    goto LABEL_7;
  }
  wil::make_unique_nothrow<unsigned short [0]>(&lpData, ((unsigned __int64)cbData >> 1) + 1);
  v5 = lpData;
  if ( !lpData )
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    LastError = -2147024888;
    goto LABEL_22;
  }
  memset_0(lpData, 0, cbData + 2LL);
  if ( RegQueryValueExW(hKey, L"UXImage", 0, 0, v5, &cbData) )
  {
    LastError = -2146893794;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x15E,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
      (const char *)0x8009001ELL,
      phkResultb);
    goto LABEL_15;
  }
  Library = LoadLibraryExW((LPCWSTR)v5, 0, 0);
  lpData = (LPBYTE)Library;
  if ( !Library )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x161,
                  (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\interface.cpp",
                  v8);
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&lpData);
LABEL_15:
    if ( v5 )
      operator delete(v5, v6);
    goto LABEL_8;
  }
  lpData = 0;
  *a1 = Library;
  KspDebugProvider::KspDebugActivity::Stop((KspDebugProvider::KspDebugActivity *)v18, "PCPLoadUXFromRegistry");
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&lpData);
  if ( v5 )
    operator delete(v5, v9);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  LastError = 0;
LABEL_22:
  KspDebugProvider::KspDebugActivity::~KspDebugActivity((KspDebugProvider::KspDebugActivity *)v18);
  return LastError;
}

```

## disassembly

```asm
0x1800749b4  mov     [rsp-8+arg_8], rbx
0x1800749b9  mov     [rsp-8+arg_10], rdi
0x1800749be  push    rbp
0x1800749bf  lea     rbp, [rsp-2D0h]
0x1800749c7  sub     rsp, 3D0h
0x1800749ce  mov     rax, cs:__security_cookie
0x1800749d5  xor     rax, rsp
0x1800749d8  mov     [rbp+2D0h+var_10], rax
0x1800749df  mov     rbx, rcx
0x1800749e2  lea     rdx, aPcploaduxfromr; "PCPLoadUXFromRegistry"
0x1800749e9  lea     rcx, [rsp+3D0h+var_370]; this
0x1800749ee  call    ??$Start@AEAY0BG@$$CBD@KspDebugActivity@KspDebugProvider@@SA?AV01@AEAY0BG@$$CBD@Z; KspDebugProvider::KspDebugActivity::Start<char const (&)[22]>(char const (&)[22])
0x1800749f3  test    rbx, rbx
0x1800749f6  jnz     short loc_180074A1D
0x1800749f8  mov     rcx, [rbp+2D8h]; this
0x1800749ff  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180074a06  mov     ebx, 80090027h
0x180074a0b  mov     edx, 12Eh; void *
0x180074a10  mov     r9d, ebx; char *
0x180074a13  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074a18  jmp     loc_180074C7A
0x180074a1d  mov     edi, 208h
0x180074a22  mov     qword ptr [rbx], 0
0x180074a29  mov     r8d, edi; Size
0x180074a2c  lea     rcx, [rbp+2D0h+SubKey]; void *
0x180074a33  xor     edx, edx; Val
0x180074a35  call    memset_0
0x180074a3a  lea     rax, [rsp+3D0h+var_378]
0x180074a3f  mov     [rsp+3D0h+var_378], edi
0x180074a43  mov     [rsp+3D0h+var_3A0], rax
0x180074a48  lea     r8, aSystemCurrentc_7; "System\\CurrentControlSet\\Control\\Cry"...
0x180074a4f  lea     rax, [rbp+2D0h+SubKey]
0x180074a56  mov     dword ptr [rsp+3D0h+lpcbData], edi
0x180074a5a  xor     r9d, r9d
0x180074a5d  mov     [rsp+3D0h+phkResult], rax; int
0x180074a62  xor     edx, edx
0x180074a64  lea     rcx, aPcpkspproperti; "PCPKSPProperties"
0x180074a6b  call    cs:__imp_RtlGetPersistedStateLocation
0x180074a72  nop     dword ptr [rax+rax+00h]
0x180074a77  test    eax, eax
0x180074a79  jns     short loc_180074A9D
0x180074a7b  mov     rcx, [rbp+2D8h]; this
0x180074a82  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180074a89  mov     r9d, eax; char *
0x180074a8c  mov     edx, 13Eh; void *
0x180074a91  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180074a96  mov     ebx, eax
0x180074a98  jmp     loc_180074C7A
0x180074a9d  lea     rax, [rsp+3D0h+hKey]
0x180074aa2  mov     [rsp+3D0h+hKey], 0
0x180074aab  mov     r9d, 20019h; samDesired
0x180074ab1  mov     [rsp+3D0h+phkResult], rax; int
0x180074ab6  xor     r8d, r8d; ulOptions
0x180074ab9  lea     rdx, [rbp+2D0h+SubKey]; lpSubKey
0x180074ac0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180074ac7  call    cs:__imp_RegOpenKeyExW
0x180074ace  nop     dword ptr [rax+rax+00h]
0x180074ad3  test    eax, eax
0x180074ad5  jz      short loc_180074B06
0x180074ad7  mov     edx, 148h; void *
0x180074adc  mov     rcx, [rbp+2D8h]; this
0x180074ae3  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180074aea  mov     ebx, 8009001Eh
0x180074aef  mov     r9d, ebx; char *
0x180074af2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074af7  lea     rcx, [rsp+3D0h+hKey]
0x180074afc  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180074b01  jmp     loc_180074C7A
0x180074b06  mov     rcx, [rsp+3D0h+hKey]; hKey
0x180074b0b  lea     rax, [rsp+3D0h+cbData]
0x180074b10  mov     [rsp+3D0h+lpcbData], rax; lpcbData
0x180074b15  lea     rdx, aUximage; "UXImage"
0x180074b1c  xor     r9d, r9d; lpType
0x180074b1f  mov     [rsp+3D0h+phkResult], 0; lpData
0x180074b28  xor     r8d, r8d; lpReserved
0x180074b2b  mov     [rsp+3D0h+cbData], 0
0x180074b33  call    cs:__imp_RegQueryValueExW
0x180074b3a  nop     dword ptr [rax+rax+00h]
0x180074b3f  test    eax, eax
0x180074b41  jz      short loc_180074B4A
0x180074b43  mov     edx, 153h
0x180074b48  jmp     short loc_180074ADC
0x180074b4a  mov     edx, [rsp+3D0h+cbData]
0x180074b4e  lea     rcx, [rsp+3D0h+lpData]
0x180074b53  shr     rdx, 1
0x180074b56  inc     rdx
0x180074b59  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x180074b5e  mov     rdi, [rsp+3D0h+lpData]
0x180074b63  test    rdi, rdi
0x180074b66  jnz     short loc_180074B7C
0x180074b68  lea     rcx, [rsp+3D0h+hKey]
0x180074b6d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180074b72  mov     ebx, 80070008h
0x180074b77  jmp     loc_180074C7A
0x180074b7c  mov     r8d, [rsp+3D0h+cbData]
0x180074b81  xor     edx, edx; Val
0x180074b83  add     r8, 2; Size
0x180074b87  mov     rcx, rdi; void *
0x180074b8a  call    memset_0
0x180074b8f  mov     rcx, [rsp+3D0h+hKey]; hKey
0x180074b94  lea     rax, [rsp+3D0h+cbData]
0x180074b99  mov     [rsp+3D0h+lpcbData], rax; lpcbData
0x180074b9e  lea     rdx, aUximage; "UXImage"
0x180074ba5  xor     r9d, r9d; lpType
0x180074ba8  mov     [rsp+3D0h+phkResult], rdi; int
0x180074bad  xor     r8d, r8d; lpReserved
0x180074bb0  call    cs:__imp_RegQueryValueExW
0x180074bb7  nop     dword ptr [rax+rax+00h]
0x180074bbc  test    eax, eax
0x180074bbe  jz      short loc_180074BF6
0x180074bc0  mov     rcx, [rbp+2D8h]; this
0x180074bc7  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180074bce  mov     ebx, 8009001Eh
0x180074bd3  mov     edx, 15Eh; void *
0x180074bd8  mov     r9d, ebx; char *
0x180074bdb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074be0  test    rdi, rdi
0x180074be3  jz      loc_180074AF7
0x180074be9  mov     rcx, rdi; void *
0x180074bec  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180074bf1  jmp     loc_180074AF7
0x180074bf6  xor     r8d, r8d; dwFlags
0x180074bf9  xor     edx, edx; hFile
0x180074bfb  mov     rcx, rdi; lpLibFileName
0x180074bfe  call    cs:__imp_LoadLibraryExW
0x180074c05  nop     dword ptr [rax+rax+00h]
0x180074c0a  mov     [rsp+3D0h+lpData], rax
0x180074c0f  test    rax, rax
0x180074c12  jnz     short loc_180074C3A
0x180074c14  mov     rcx, [rbp+2D8h]; this
0x180074c1b  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180074c22  mov     edx, 161h; void *
0x180074c27  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180074c2c  lea     rcx, [rsp+3D0h+lpData]
0x180074c31  mov     ebx, eax
0x180074c33  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180074c38  jmp     short loc_180074BE0
0x180074c3a  lea     rdx, aPcploaduxfromr; "PCPLoadUXFromRegistry"
0x180074c41  mov     [rsp+3D0h+lpData], 0
0x180074c4a  lea     rcx, [rsp+3D0h+var_370]; this
0x180074c4f  mov     [rbx], rax
0x180074c52  call    ?Stop@KspDebugActivity@KspDebugProvider@@QEAAXPEBD@Z; KspDebugProvider::KspDebugActivity::Stop(char const *)
0x180074c57  lea     rcx, [rsp+3D0h+lpData]
0x180074c5c  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180074c61  test    rdi, rdi
0x180074c64  jz      short loc_180074C6E
0x180074c66  mov     rcx, rdi; void *
0x180074c69  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180074c6e  lea     rcx, [rsp+3D0h+hKey]
0x180074c73  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180074c78  xor     ebx, ebx
0x180074c7a  lea     rcx, [rsp+3D0h+var_370]; this
0x180074c7f  call    ??1KspDebugActivity@KspDebugProvider@@QEAA@XZ; KspDebugProvider::KspDebugActivity::~KspDebugActivity(void)
0x180074c84  mov     eax, ebx
0x180074c86  mov     rcx, [rbp+2D0h+var_10]
0x180074c8d  xor     rcx, rsp; StackCookie
0x180074c90  call    __security_check_cookie
0x180074c95  lea     r11, [rsp+3D0h+var_s0]
0x180074c9d  mov     rbx, [r11+18h]
0x180074ca1  mov     rdi, [r11+20h]
0x180074ca5  mov     rsp, r11
0x180074ca8  pop     rbp
0x180074ca9  retn
```
