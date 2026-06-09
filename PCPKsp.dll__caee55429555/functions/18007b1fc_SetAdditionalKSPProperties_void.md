# SetAdditionalKSPProperties(void)

- ea: `0x18007b1fc`
- end: `0x18007b6fd`
- name: `?SetAdditionalKSPProperties@@YAJXZ`
- size: `1281`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18007aa10`

## callees

- `0x180014a60`
- `0x1800157c0`
- `0x180036ab4`
- `0x18005305c`
- `0x18005437c`
- `0x180061bac`
- `0x180068a8c`
- `0x1800764d0`
- `0x18007704c`
- `0x18007b1fc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007b473`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007b56f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007b66b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007b473`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007b56f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007b66b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007b35f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007b39c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007b4ae`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007b5aa`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007b6a6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007b35f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007b39c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007b4ae`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007b5aa`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007b6a6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007b2b8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007b43e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007b53a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007b636`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007b2b8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007b43e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007b53a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007b636`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18007b307`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18007b307`
- `ntdll!RtlGetPersistedStateLocation` at `0x18007b287`
- `ntdll!RtlGetPersistedStateLocation` at `0x18007b3f7`
- `ntdll!RtlGetPersistedStateLocation` at `0x18007b509`
- `ntdll!RtlGetPersistedStateLocation` at `0x18007b605`
- `ntdll!RtlGetPersistedStateLocation` at `0x18007b287`
- `ntdll!RtlGetPersistedStateLocation` at `0x18007b3f7`
- `ntdll!RtlGetPersistedStateLocation` at `0x18007b509`
- `ntdll!RtlGetPersistedStateLocation` at `0x18007b605`

## string_xrefs

- `0x18007b37b`: `PCPTPM12.dll`
- `0x18007b33e`: `credui.dll`

## pseudocode

```c
__int64 SetAdditionalKSPProperties(void)
{
  int PersistedStateLocation; // eax
  __int64 v1; // rdx
  unsigned int v2; // eax
  __int64 v3; // rdx
  int v4; // eax
  unsigned int v5; // ebx
  HKEY v6; // rbx
  HKEY v7; // rbx
  HKEY v8; // rbx
  unsigned int dwOptions; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  int v12; // [rsp+58h] [rbp-A8h]
  _BYTE v13[8]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v14[24]; // [rsp+68h] [rbp-98h] BYREF
  WCHAR SubKey[264]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v14, L"SetAdditionalKSPProperties", 1);
  hKey = 0;
  memset_0(SubKey, 0, 0x208u);
  v12 = 520;
  PersistedStateLocation = RtlGetPersistedStateLocation(
                             L"PCPKSPProperties",
                             0,
                             L"SYSTEM\\CurrentControlSet\\Control\\Cryptography\\Providers\\Microsoft Platform Crypto Prov"
                              "ider\\Properties",
                             0);
  if ( PersistedStateLocation < 0 )
  {
    v1 = 230;
LABEL_13:
    v4 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)v1,
           (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\registerkspprovider.cpp",
           (const char *)(unsigned int)PersistedStateLocation,
           (int)SubKey);
    goto LABEL_6;
  }
  hKey = 0;
  v2 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x20006u, 0, &hKey, 0);
  if ( v2 )
  {
    v3 = 240;
  }
  else
  {
    v2 = RegSetValueExW(hKey, L"UXImage", 0, 1u, L"credui.dll", 0x16u);
    if ( v2 )
    {
      v3 = 247;
    }
    else
    {
      v2 = RegSetValueExW(hKey, L"PlatformProvider", 0, 1u, L"PCPTPM12.dll", 0x1Au);
      if ( v2 )
      {
        v3 = 254;
      }
      else
      {
        hKey = 0;
        v12 = 520;
        memset_0(SubKey, 0, 0x208u);
        PersistedStateLocation = RtlGetPersistedStateLocation(
                                   L"PCPKSPUM3",
                                   0,
                                   L"SYSTEM\\CurrentControlSet\\Control\\Cryptography\\Providers\\Microsoft Platform Crypt"
                                    "o Provider\\UM\\00000003",
                                   0);
        if ( PersistedStateLocation < 0 )
        {
          v1 = 268;
          goto LABEL_13;
        }
        v6 = hKey;
        if ( hKey )
        {
          wil::last_error_context::last_error_context((wil::last_error_context *)v13);
          RegCloseKey(v6);
          wil::last_error_context::~last_error_context((wil::last_error_context *)v13);
        }
        hKey = 0;
        v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20006u, &hKey);
        if ( v2 )
        {
          v3 = 274;
        }
        else
        {
          v2 = RegSetValueExW(hKey, 0, 0, 1u, L"CRYPT_ASYMMETRIC_ENCRYPTION_INTERFACE", 0x4Cu);
          if ( v2 )
          {
            v3 = 281;
          }
          else
          {
            hKey = 0;
            v12 = 520;
            memset_0(SubKey, 0, 0x208u);
            PersistedStateLocation = RtlGetPersistedStateLocation(
                                       L"PCPKSPUM6",
                                       0,
                                       L"SYSTEM\\CurrentControlSet\\Control\\Cryptography\\Providers\\Microsoft Platform C"
                                        "rypto Provider\\UM\\00000006",
                                       0);
            if ( PersistedStateLocation < 0 )
            {
              v1 = 295;
              goto LABEL_13;
            }
            v7 = hKey;
            if ( hKey )
            {
              wil::last_error_context::last_error_context((wil::last_error_context *)v13);
              RegCloseKey(v7);
              wil::last_error_context::~last_error_context((wil::last_error_context *)v13);
            }
            hKey = 0;
            v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20006u, &hKey);
            if ( v2 )
            {
              v3 = 301;
            }
            else
            {
              v2 = RegSetValueExW(hKey, 0, 0, 1u, L"CRYPT_RNG_INTERFACE", 0x28u);
              if ( v2 )
              {
                v3 = 308;
              }
              else
              {
                hKey = 0;
                v12 = 520;
                memset_0(SubKey, 0, 0x208u);
                PersistedStateLocation = RtlGetPersistedStateLocation(
                                           L"PCPKSPUM1",
                                           0,
                                           L"SYSTEM\\CurrentControlSet\\Control\\Cryptography\\Providers\\Microsoft Platfo"
                                            "rm Crypto Provider\\UM\\00010001",
                                           0);
                if ( PersistedStateLocation < 0 )
                {
                  v1 = 322;
                  goto LABEL_13;
                }
                v8 = hKey;
                if ( hKey )
                {
                  wil::last_error_context::last_error_context((wil::last_error_context *)v13);
                  RegCloseKey(v8);
                  wil::last_error_context::~last_error_context((wil::last_error_context *)v13);
                }
                hKey = 0;
                v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20006u, &hKey);
                if ( v2 )
                {
                  v3 = 328;
                }
                else
                {
                  v2 = RegSetValueExW(hKey, 0, 0, 1u, L"CRYPT_KEY_STORAGE_INTERFACE", 0x38u);
                  if ( !v2 )
                  {
                    hKey = 0;
                    v5 = 0;
                    goto LABEL_37;
                  }
                  v3 = 335;
                }
              }
            }
          }
        }
      }
    }
  }
  v4 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)v3,
         (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\registerkspprovider.cpp",
         (const char *)v2,
         dwOptions);
LABEL_6:
  v5 = v4;
LABEL_37:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v14);
  return v5;
}

```

## disassembly

```asm
0x18007b1fc  push    rbp
0x18007b1fe  push    rbx
0x18007b1ff  push    rsi
0x18007b200  push    rdi
0x18007b201  push    r12
0x18007b203  push    r14
0x18007b205  lea     rbp, [rsp-1A8h]
0x18007b20d  sub     rsp, 2A8h
0x18007b214  mov     rax, cs:__security_cookie
0x18007b21b  xor     rax, rsp
0x18007b21e  mov     [rbp+1D0h+var_40], rax
0x18007b225  mov     r14d, 1
0x18007b22b  lea     rdx, aSetadditionalk; "SetAdditionalKSPProperties"
0x18007b232  mov     r8b, r14b; bool
0x18007b235  lea     rcx, [rsp+2D0h+var_268]; this
0x18007b23a  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x18007b23f  mov     esi, 208h
0x18007b244  lea     rcx, [rbp+1D0h+SubKey]; void *
0x18007b248  xor     edi, edi
0x18007b24a  mov     r8d, esi; Size
0x18007b24d  xor     edx, edx; Val
0x18007b24f  mov     [rsp+2D0h+hKey], rdi
0x18007b254  call    memset_0
0x18007b259  lea     rax, [rsp+2D0h+var_278]
0x18007b25e  mov     [rsp+2D0h+var_278], esi
0x18007b262  mov     [rsp+2D0h+lpSecurityAttributes], rax
0x18007b267  lea     r8, aSystemCurrentc_10; "SYSTEM\\CurrentControlSet\\Control\\Cry"...
0x18007b26e  lea     rax, [rbp+1D0h+SubKey]
0x18007b272  mov     [rsp+2D0h+samDesired], esi
0x18007b276  xor     r9d, r9d
0x18007b279  mov     qword ptr [rsp+2D0h+dwOptions], rax
0x18007b27e  xor     edx, edx
0x18007b280  lea     rcx, aPcpkspproperti; "PCPKSPProperties"
0x18007b287  call    cs:__imp_RtlGetPersistedStateLocation
0x18007b28e  nop     dword ptr [rax+rax+00h]
0x18007b293  test    eax, eax
0x18007b295  jns     short loc_18007B2A1
0x18007b297  mov     edx, 0E6h
0x18007b29c  jmp     loc_18007B40C
0x18007b2a1  mov     rbx, [rsp+2D0h+hKey]
0x18007b2a6  test    rbx, rbx
0x18007b2a9  jz      short loc_18007B2CE
0x18007b2ab  lea     rcx, [rsp+2D0h+var_270]; this
0x18007b2b0  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18007b2b5  mov     rcx, rbx; hKey
0x18007b2b8  call    cs:__imp_RegCloseKey
0x18007b2bf  nop     dword ptr [rax+rax+00h]
0x18007b2c4  lea     rcx, [rsp+2D0h+var_270]; this
0x18007b2c9  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18007b2ce  mov     [rsp+2D0h+lpdwDisposition], rdi; lpdwDisposition
0x18007b2d3  lea     rax, [rsp+2D0h+hKey]
0x18007b2d8  mov     [rsp+2D0h+phkResult], rax; phkResult
0x18007b2dd  lea     rdx, [rbp+1D0h+SubKey]; lpSubKey
0x18007b2e1  mov     [rsp+2D0h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18007b2e6  mov     r12, 0FFFFFFFF80000002h
0x18007b2ed  mov     [rsp+2D0h+samDesired], 20006h; samDesired
0x18007b2f5  xor     r9d, r9d; lpClass
0x18007b2f8  xor     r8d, r8d; Reserved
0x18007b2fb  mov     [rsp+2D0h+dwOptions], edi; unsigned int
0x18007b2ff  mov     rcx, r12; hKey
0x18007b302  mov     [rsp+2D0h+hKey], rdi
0x18007b307  call    cs:__imp_RegCreateKeyExW
0x18007b30e  nop     dword ptr [rax+rax+00h]
0x18007b313  test    eax, eax
0x18007b315  jz      short loc_18007B339
0x18007b317  mov     edx, 0F0h; void *
0x18007b31c  mov     rcx, [rbp+1D8h]; this
0x18007b323  lea     r8, aOnecoreBaseNgs_5; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18007b32a  mov     r9d, eax; char *
0x18007b32d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18007b332  mov     ebx, eax
0x18007b334  jmp     loc_18007B6C7
0x18007b339  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18007b33e  lea     rax, Data; "credui.dll"
0x18007b345  mov     [rsp+2D0h+samDesired], 16h; cbData
0x18007b34d  lea     rdx, aUximage; "UXImage"
0x18007b354  mov     r9d, r14d; dwType
0x18007b357  mov     qword ptr [rsp+2D0h+dwOptions], rax; lpData
0x18007b35c  xor     r8d, r8d; Reserved
0x18007b35f  call    cs:__imp_RegSetValueExW
0x18007b366  nop     dword ptr [rax+rax+00h]
0x18007b36b  test    eax, eax
0x18007b36d  jz      short loc_18007B376
0x18007b36f  mov     edx, 0F7h
0x18007b374  jmp     short loc_18007B31C
0x18007b376  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18007b37b  lea     rax, aPcptpm12Dll; "PCPTPM12.dll"
0x18007b382  mov     [rsp+2D0h+samDesired], 1Ah; cbData
0x18007b38a  lea     rdx, aPlatformprovid; "PlatformProvider"
0x18007b391  mov     r9d, r14d; dwType
0x18007b394  mov     qword ptr [rsp+2D0h+dwOptions], rax; lpData
0x18007b399  xor     r8d, r8d; Reserved
0x18007b39c  call    cs:__imp_RegSetValueExW
0x18007b3a3  nop     dword ptr [rax+rax+00h]
0x18007b3a8  test    eax, eax
0x18007b3aa  jz      short loc_18007B3B6
0x18007b3ac  mov     edx, 0FEh
0x18007b3b1  jmp     loc_18007B31C
0x18007b3b6  mov     r8, rsi; Size
0x18007b3b9  mov     [rsp+2D0h+hKey], rdi
0x18007b3be  xor     edx, edx; Val
0x18007b3c0  mov     [rsp+2D0h+var_278], esi
0x18007b3c4  lea     rcx, [rbp+1D0h+SubKey]; void *
0x18007b3c8  call    memset_0
0x18007b3cd  lea     rax, [rsp+2D0h+var_278]
0x18007b3d2  xor     r9d, r9d
0x18007b3d5  mov     [rsp+2D0h+lpSecurityAttributes], rax
0x18007b3da  lea     r8, aSystemCurrentc_11; "SYSTEM\\CurrentControlSet\\Control\\Cry"...
0x18007b3e1  lea     rax, [rbp+1D0h+SubKey]
0x18007b3e5  mov     [rsp+2D0h+samDesired], esi
0x18007b3e9  xor     edx, edx
0x18007b3eb  mov     qword ptr [rsp+2D0h+dwOptions], rax; int
0x18007b3f0  lea     rcx, aPcpkspum3; "PCPKSPUM3"
0x18007b3f7  call    cs:__imp_RtlGetPersistedStateLocation
0x18007b3fe  nop     dword ptr [rax+rax+00h]
0x18007b403  test    eax, eax
0x18007b405  jns     short loc_18007B427
0x18007b407  mov     edx, 10Ch; void *
0x18007b40c  mov     rcx, [rbp+1D8h]; this
0x18007b413  lea     r8, aOnecoreBaseNgs_5; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18007b41a  mov     r9d, eax; char *
0x18007b41d  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18007b422  jmp     loc_18007B332
0x18007b427  mov     rbx, [rsp+2D0h+hKey]
0x18007b42c  test    rbx, rbx
0x18007b42f  jz      short loc_18007B454
0x18007b431  lea     rcx, [rsp+2D0h+var_270]; this
0x18007b436  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18007b43b  mov     rcx, rbx; hKey
0x18007b43e  call    cs:__imp_RegCloseKey
0x18007b445  nop     dword ptr [rax+rax+00h]
0x18007b44a  lea     rcx, [rsp+2D0h+var_270]; this
0x18007b44f  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18007b454  lea     rax, [rsp+2D0h+hKey]
0x18007b459  mov     [rsp+2D0h+hKey], rdi
0x18007b45e  mov     r9d, 20006h; samDesired
0x18007b464  mov     qword ptr [rsp+2D0h+dwOptions], rax; phkResult
0x18007b469  xor     r8d, r8d; ulOptions
0x18007b46c  lea     rdx, [rbp+1D0h+SubKey]; lpSubKey
0x18007b470  mov     rcx, r12; hKey
0x18007b473  call    cs:__imp_RegOpenKeyExW
0x18007b47a  nop     dword ptr [rax+rax+00h]
0x18007b47f  test    eax, eax
0x18007b481  jz      short loc_18007B48D
0x18007b483  mov     edx, 112h
0x18007b488  jmp     loc_18007B31C
0x18007b48d  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18007b492  lea     rax, aCryptAsymmetri; "CRYPT_ASYMMETRIC_ENCRYPTION_INTERFACE"
0x18007b499  mov     [rsp+2D0h+samDesired], 4Ch ; 'L'; cbData
0x18007b4a1  mov     r9d, r14d; dwType
0x18007b4a4  xor     r8d, r8d; Reserved
0x18007b4a7  mov     qword ptr [rsp+2D0h+dwOptions], rax; lpData
0x18007b4ac  xor     edx, edx; lpValueName
0x18007b4ae  call    cs:__imp_RegSetValueExW
0x18007b4b5  nop     dword ptr [rax+rax+00h]
0x18007b4ba  test    eax, eax
0x18007b4bc  jz      short loc_18007B4C8
0x18007b4be  mov     edx, 119h
0x18007b4c3  jmp     loc_18007B31C
0x18007b4c8  mov     r8, rsi; Size
0x18007b4cb  mov     [rsp+2D0h+hKey], rdi
0x18007b4d0  xor     edx, edx; Val
0x18007b4d2  mov     [rsp+2D0h+var_278], esi
0x18007b4d6  lea     rcx, [rbp+1D0h+SubKey]; void *
0x18007b4da  call    memset_0
0x18007b4df  lea     rax, [rsp+2D0h+var_278]
0x18007b4e4  xor     r9d, r9d
0x18007b4e7  mov     [rsp+2D0h+lpSecurityAttributes], rax
0x18007b4ec  lea     r8, aSystemCurrentc_5; "SYSTEM\\CurrentControlSet\\Control\\Cry"...
0x18007b4f3  lea     rax, [rbp+1D0h+SubKey]
0x18007b4f7  mov     [rsp+2D0h+samDesired], esi
0x18007b4fb  xor     edx, edx
0x18007b4fd  mov     qword ptr [rsp+2D0h+dwOptions], rax
0x18007b502  lea     rcx, aPcpkspum6; "PCPKSPUM6"
0x18007b509  call    cs:__imp_RtlGetPersistedStateLocation
0x18007b510  nop     dword ptr [rax+rax+00h]
0x18007b515  test    eax, eax
0x18007b517  jns     short loc_18007B523
0x18007b519  mov     edx, 127h
0x18007b51e  jmp     loc_18007B40C
0x18007b523  mov     rbx, [rsp+2D0h+hKey]
0x18007b528  test    rbx, rbx
0x18007b52b  jz      short loc_18007B550
0x18007b52d  lea     rcx, [rsp+2D0h+var_270]; this
0x18007b532  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18007b537  mov     rcx, rbx; hKey
0x18007b53a  call    cs:__imp_RegCloseKey
0x18007b541  nop     dword ptr [rax+rax+00h]
0x18007b546  lea     rcx, [rsp+2D0h+var_270]; this
0x18007b54b  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18007b550  lea     rax, [rsp+2D0h+hKey]
0x18007b555  mov     [rsp+2D0h+hKey], rdi
0x18007b55a  mov     r9d, 20006h; samDesired
0x18007b560  mov     qword ptr [rsp+2D0h+dwOptions], rax; phkResult
0x18007b565  xor     r8d, r8d; ulOptions
0x18007b568  lea     rdx, [rbp+1D0h+SubKey]; lpSubKey
0x18007b56c  mov     rcx, r12; hKey
0x18007b56f  call    cs:__imp_RegOpenKeyExW
0x18007b576  nop     dword ptr [rax+rax+00h]
0x18007b57b  test    eax, eax
0x18007b57d  jz      short loc_18007B589
0x18007b57f  mov     edx, 12Dh
0x18007b584  jmp     loc_18007B31C
0x18007b589  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18007b58e  lea     rax, aCryptRngInterf; "CRYPT_RNG_INTERFACE"
0x18007b595  mov     [rsp+2D0h+samDesired], 28h ; '('; cbData
0x18007b59d  mov     r9d, r14d; dwType
0x18007b5a0  xor     r8d, r8d; Reserved
0x18007b5a3  mov     qword ptr [rsp+2D0h+dwOptions], rax; lpData
0x18007b5a8  xor     edx, edx; lpValueName
0x18007b5aa  call    cs:__imp_RegSetValueExW
0x18007b5b1  nop     dword ptr [rax+rax+00h]
0x18007b5b6  test    eax, eax
0x18007b5b8  jz      short loc_18007B5C4
0x18007b5ba  mov     edx, 134h
0x18007b5bf  jmp     loc_18007B31C
0x18007b5c4  mov     r8, rsi; Size
0x18007b5c7  mov     [rsp+2D0h+hKey], rdi
0x18007b5cc  xor     edx, edx; Val
0x18007b5ce  mov     [rsp+2D0h+var_278], esi
0x18007b5d2  lea     rcx, [rbp+1D0h+SubKey]; void *
0x18007b5d6  call    memset_0
0x18007b5db  lea     rax, [rsp+2D0h+var_278]
0x18007b5e0  xor     r9d, r9d
0x18007b5e3  mov     [rsp+2D0h+lpSecurityAttributes], rax
0x18007b5e8  lea     r8, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Cry"...
0x18007b5ef  lea     rax, [rbp+1D0h+SubKey]
0x18007b5f3  mov     [rsp+2D0h+samDesired], esi
0x18007b5f7  xor     edx, edx
0x18007b5f9  mov     qword ptr [rsp+2D0h+dwOptions], rax
0x18007b5fe  lea     rcx, aPcpkspum1; "PCPKSPUM1"
0x18007b605  call    cs:__imp_RtlGetPersistedStateLocation
0x18007b60c  nop     dword ptr [rax+rax+00h]
0x18007b611  test    eax, eax
0x18007b613  jns     short loc_18007B61F
0x18007b615  mov     edx, 142h
0x18007b61a  jmp     loc_18007B40C
0x18007b61f  mov     rbx, [rsp+2D0h+hKey]
0x18007b624  test    rbx, rbx
0x18007b627  jz      short loc_18007B64C
0x18007b629  lea     rcx, [rsp+2D0h+var_270]; this
0x18007b62e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18007b633  mov     rcx, rbx; hKey
0x18007b636  call    cs:__imp_RegCloseKey
0x18007b63d  nop     dword ptr [rax+rax+00h]
0x18007b642  lea     rcx, [rsp+2D0h+var_270]; this
0x18007b647  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18007b64c  lea     rax, [rsp+2D0h+hKey]
0x18007b651  mov     [rsp+2D0h+hKey], rdi
0x18007b656  mov     r9d, 20006h; samDesired
0x18007b65c  mov     qword ptr [rsp+2D0h+dwOptions], rax; phkResult
0x18007b661  xor     r8d, r8d; ulOptions
0x18007b664  lea     rdx, [rbp+1D0h+SubKey]; lpSubKey
0x18007b668  mov     rcx, r12; hKey
0x18007b66b  call    cs:__imp_RegOpenKeyExW
0x18007b672  nop     dword ptr [rax+rax+00h]
0x18007b677  test    eax, eax
0x18007b679  jz      short loc_18007B685
0x18007b67b  mov     edx, 148h
0x18007b680  jmp     loc_18007B31C
0x18007b685  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18007b68a  lea     rax, aCryptKeyStorag; "CRYPT_KEY_STORAGE_INTERFACE"
0x18007b691  mov     [rsp+2D0h+samDesired], 38h ; '8'; cbData
0x18007b699  mov     r9d, r14d; dwType
0x18007b69c  xor     r8d, r8d; Reserved
0x18007b69f  mov     qword ptr [rsp+2D0h+dwOptions], rax; lpData
0x18007b6a4  xor     edx, edx; lpValueName
0x18007b6a6  call    cs:__imp_RegSetValueExW
0x18007b6ad  nop     dword ptr [rax+rax+00h]
0x18007b6b2  test    eax, eax
0x18007b6b4  jz      short loc_18007B6C0
0x18007b6b6  mov     edx, 14Fh
0x18007b6bb  jmp     loc_18007B31C
0x18007b6c0  mov     [rsp+2D0h+hKey], rdi
0x18007b6c5  mov     ebx, edi
0x18007b6c7  lea     rcx, [rsp+2D0h+hKey]
0x18007b6cc  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18007b6d1  lea     rcx, [rsp+2D0h+var_268]; this
0x18007b6d6  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x18007b6db  mov     eax, ebx
0x18007b6dd  mov     rcx, [rbp+1D0h+var_40]
0x18007b6e4  xor     rcx, rsp; StackCookie
0x18007b6e7  call    __security_check_cookie
0x18007b6ec  add     rsp, 2A8h
0x18007b6f3  pop     r14
0x18007b6f5  pop     r12
0x18007b6f7  pop     rdi
0x18007b6f8  pop     rsi
0x18007b6f9  pop     rbx
0x18007b6fa  pop     rbp
0x18007b6fb  retn
```
