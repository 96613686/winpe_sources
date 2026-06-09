# _anonymous_namespace_::MigratePluginXmlForUninstall

- ea: `0x180105ae0`
- end: `0x180105f4e`
- name: `_anonymous_namespace_::MigratePluginXmlForUninstall`
- size: `1134`
- prototype: `__int64 __fastcall(struct IRequestContext *, HKEY hkey, int)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180193110`
- `0x180193270`

## callees

- `0x180008920`
- `0x1800621e0`
- `0x180077490`
- `0x1800bac30`
- `0x180105ae0`
- `0x18010e030`
- `0x1801a65c0`
- `0x1801a6964`
- `0x1801a6a2c`
- `0x1801a6b98`
- `0x1801ba152`
- `0x1801ba1b0`
- `0x1801c2010`

## import_xrefs

- `msvcrt!fwprintf` at `0x180105b8c`
- `msvcrt!fwprintf` at `0x180105ca9`
- `msvcrt!fwprintf` at `0x180105ccf`
- `msvcrt!fwprintf` at `0x180105e1b`
- `msvcrt!fwprintf` at `0x180105e61`
- `msvcrt!fwprintf` at `0x180105e9f`
- `msvcrt!fwprintf` at `0x180105ecc`
- `msvcrt!fwprintf` at `0x180105efb`
- `msvcrt!fwprintf` at `0x180105b8c`
- `msvcrt!fwprintf` at `0x180105ca9`
- `msvcrt!fwprintf` at `0x180105ccf`
- `msvcrt!fwprintf` at `0x180105e1b`
- `msvcrt!fwprintf` at `0x180105e61`
- `msvcrt!fwprintf` at `0x180105e9f`
- `msvcrt!fwprintf` at `0x180105ecc`
- `msvcrt!fwprintf` at `0x180105efb`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180105b61`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180105b61`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180105d8c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180105d8c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180105dcf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180105dcf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180105be3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180105be3`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180105c12`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180105c12`

## string_xrefs

- `0x180105d1b`: `SOFTWARE\Microsoft\Windows\CurrentVersion\WSMAN\Plugin`
- `0x180105b85`: `Migrating plugin %ls\n`
- `0x180105bd2`: `ConfigXML`
- `0x180105dc3`: `ConfigXML`
- `0x180105ef4`: `Can not create buffer.\n`
- `0x180105ca2`: `Can not remove the credentials from CredStore. \n`
- `0x180105cc8`: `Plugin Migration ERROR: Failed to update SDKVersion.\n`
- `0x180105e41`: `Plugin Migration ERROR: Failed to remove Quota element\n`
- `0x180105e92`: `Plugin Migration ERROR: StringCchPrintf returned %x.\n`
- `0x180105e5a`: `Plugin Migration ERROR: RegSetValueEx returned %lu.\n`
- `0x180105ede`: `Plugin Migration ERROR: RegGetValue returned %lu.\n`
- `0x180105e14`: `Plugin Migration ERROR: RegEnumKeyEx returned %lu. on index = %d\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall anonymous_namespace_::MigratePluginXmlForUninstall(struct IRequestContext *a1, HKEY hkey, int a3)
{
  unsigned int v6; // edi
  DWORD v7; // r14d
  FILE *v8; // rax
  void *v9; // rbx
  unsigned int ValueW; // edi
  DWORD dwMajorVersion; // ecx
  DWORD dwMinorVersion; // edx
  unsigned int i; // edi
  const unsigned __int16 *v14; // rdx
  FILE *v15; // rax
  FILE *v16; // rax
  unsigned int j; // edi
  const unsigned __int16 *v18; // r8
  __int64 v19; // rax
  FILE *v20; // rax
  FILE *v21; // rax
  FILE *v22; // rax
  FILE *v23; // rax
  FILE *v24; // rax
  FILE *v25; // rax
  FILE *v26; // rax
  void *v28; // [rsp+50h] [rbp-B0h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  DWORD cchName; // [rsp+60h] [rbp-A0h] BYREF
  DWORD pcbData; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD dwDisposition; // [rsp+68h] [rbp-98h] BYREF
  struct _OSVERSIONINFOW VersionInformation; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Name[512]; // [rsp+190h] [rbp+90h] BYREF
  WCHAR SubKey[512]; // [rsp+590h] [rbp+490h] BYREF

  if ( hkey )
  {
    v6 = 0;
    v7 = 0;
    while ( 1 )
    {
      while ( 1 )
      {
        if ( v6 )
          return 1;
        cchName = 512;
        v6 = RegEnumKeyExW(hkey, v7++, Name, &cchName, 0, 0, 0, 0);
        if ( !v6 )
          break;
        if ( v6 != 259 )
        {
          v20 = _acrt_iob_func(2u);
          fwprintf(v20, L"Plugin Migration ERROR: RegEnumKeyEx returned %lu. on index = %d\n", v6, v7);
          (*(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a1 + 72LL))(a1, v6);
          return 0;
        }
      }
      v8 = _acrt_iob_func(0);
      fwprintf(v8, L"Migrating plugin %ls\n", Name);
      v9 = (void *)WSManMemory::Alloc(20480, 0, 0);
      v28 = v9;
      if ( !v9 )
        break;
      pcbData = 10240;
      ValueW = RegGetValueW(hkey, Name, L"ConfigXML", v6 + 2, 0, v9, &pcbData);
      if ( ValueW )
      {
        v25 = _acrt_iob_func(2u);
        fwprintf(v25, L"Plugin Migration ERROR: RegGetValue returned %lu.\n", ValueW);
LABEL_33:
        (*(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a1 + 72LL))(a1, ValueW);
        goto LABEL_38;
      }
      memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
      VersionInformation.dwOSVersionInfoSize = 284;
      if ( !GetVersionExW(&VersionInformation) )
      {
        v24 = _acrt_iob_func(2u);
        fwprintf(v24, L"Can not get the OS version information from this system. \n");
        goto LABEL_38;
      }
      dwMajorVersion = VersionInformation.dwMajorVersion;
      dwMinorVersion = VersionInformation.dwMinorVersion;
      if ( VersionInformation.dwMinorVersion + 10 * VersionInformation.dwMajorVersion <= 0x64 && a3 )
      {
        for ( i = 0; i < 2; ++i )
          RemoveAttribute((wchar_t *)v9, off_1801CD570[i]);
        dwMinorVersion = VersionInformation.dwMinorVersion;
        dwMajorVersion = VersionInformation.dwMajorVersion;
      }
      if ( dwMinorVersion + 10 * dwMajorVersion < 0x3E && !a3 )
      {
        if ( !RemoveRunAsUserIfPresent(a1, (const unsigned __int16 *)v9, Name) )
        {
          v15 = _acrt_iob_func(2u);
          fwprintf(v15, L"Can not remove the credentials from CredStore. \n");
        }
        if ( !DowngradeSDKVersion((wchar_t *)v9, v14) )
        {
          v16 = _acrt_iob_func(2u);
          fwprintf(v16, L"Plugin Migration ERROR: Failed to update SDKVersion.\n");
        }
        for ( j = 0; j < 6; ++j )
          RemoveAttribute((wchar_t *)v9, off_1801CD580[j]);
        if ( !RemoveNode(a1, (const unsigned __int16 *)v9, v18) )
        {
          v21 = _acrt_iob_func(2u);
          fwprintf(v21, L"Plugin Migration ERROR: Failed to remove Quota element\n");
          goto LABEL_38;
        }
      }
      ValueW = StringCchPrintfW(
                 SubKey,
                 0x200u,
                 L"%s\\%s",
                 L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WSMAN\\Plugin",
                 Name);
      if ( (ValueW & 0x80000000) != 0 )
      {
        v23 = _acrt_iob_func(2u);
        fwprintf(v23, L"Plugin Migration ERROR: StringCchPrintf returned %x.\n", ValueW);
        goto LABEL_33;
      }
      phkResult = 0;
      dwDisposition = 0;
      v6 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, (LPWSTR)&Class, 0, 0x6011Bu, 0, &phkResult, &dwDisposition);
      if ( v6 )
        goto LABEL_31;
      v19 = -1;
      do
        ++v19;
      while ( *((_WORD *)v9 + v19) );
      v6 = RegSetValueExW(phkResult, L"ConfigXML", 0, 1u, (const BYTE *)v9, 2 * v19 + 2);
      if ( v6 )
      {
LABEL_31:
        v22 = _acrt_iob_func(2u);
        fwprintf(v22, L"Plugin Migration ERROR: RegSetValueEx returned %lu.\n", v6);
        (*(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a1 + 72LL))(a1, v6);
        AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(&phkResult);
        goto LABEL_38;
      }
      AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(&phkResult);
      AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v28);
    }
    v26 = _acrt_iob_func(2u);
    fwprintf(v26, L"Can not create buffer.\n");
    (*(void (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a1 + 24LL))(a1);
LABEL_38:
    AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v28);
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180105ae0  mov     [rsp-8+arg_10], rbx
0x180105ae5  push    rbp
0x180105ae6  push    rsi
0x180105ae7  push    rdi
0x180105ae8  push    r12
0x180105aea  push    r13
0x180105aec  push    r14
0x180105aee  push    r15
0x180105af0  lea     rbp, [rsp-8A0h]
0x180105af8  sub     rsp, 9A0h
0x180105aff  mov     rax, cs:__security_cookie
0x180105b06  xor     rax, rsp
0x180105b09  mov     [rbp+8D0h+var_40], rax
0x180105b10  mov     r12d, r8d
0x180105b13  mov     r15, rdx
0x180105b16  mov     rsi, rcx
0x180105b19  xor     r13d, r13d
0x180105b1c  test    rdx, rdx
0x180105b1f  jz      loc_180105F1F
0x180105b25  mov     edi, r13d
0x180105b28  mov     r14d, r13d
0x180105b2b  test    edi, edi
0x180105b2d  jnz     loc_180105F1F
0x180105b33  mov     [rsp+9D0h+cchName], 200h
0x180105b3b  mov     [rsp+9D0h+lpftLastWriteTime], r13; lpftLastWriteTime
0x180105b40  mov     [rsp+9D0h+lpcchClass], r13; lpcchClass
0x180105b45  mov     [rsp+9D0h+lpClass], r13; lpClass
0x180105b4a  mov     [rsp+9D0h+lpReserved], r13; lpReserved
0x180105b4f  lea     r9, [rsp+9D0h+cchName]; lpcchName
0x180105b54  lea     r8, [rbp+8D0h+Name]; lpName
0x180105b5b  mov     edx, r14d; dwIndex
0x180105b5e  mov     rcx, r15; hKey
0x180105b61  call    cs:__imp_RegEnumKeyExW
0x180105b67  mov     edi, eax
0x180105b69  inc     r14d
0x180105b6c  test    eax, eax
0x180105b6e  jnz     loc_180105DF5
0x180105b74  xor     ecx, ecx; Ix
0x180105b76  call    __acrt_iob_func
0x180105b7b  mov     rcx, rax; Stream
0x180105b7e  lea     r8, [rbp+8D0h+Name]
0x180105b85  lea     rdx, aMigratingPlugi; "Migrating plugin %ls\n"
0x180105b8c  call    cs:__imp_fwprintf
0x180105b92  xor     r8d, r8d
0x180105b95  xor     edx, edx
0x180105b97  mov     ecx, 5000h
0x180105b9c  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x180105ba1  mov     rbx, rax
0x180105ba4  mov     [rsp+9D0h+var_980], rax
0x180105ba9  test    rax, rax
0x180105bac  jz      loc_180105EE7
0x180105bb2  mov     [rsp+9D0h+pcbData], 2800h
0x180105bba  lea     rax, [rsp+9D0h+pcbData]
0x180105bbf  mov     [rsp+9D0h+lpcchClass], rax; pcbData
0x180105bc4  mov     [rsp+9D0h+lpClass], rbx; pvData
0x180105bc9  mov     [rsp+9D0h+lpReserved], r13; pdwType
0x180105bce  lea     r9d, [rdi+2]; dwFlags
0x180105bd2  lea     r8, Value; "ConfigXML"
0x180105bd9  lea     rdx, [rbp+8D0h+Name]; lpSubKey
0x180105be0  mov     rcx, r15; hkey
0x180105be3  call    cs:__imp_RegGetValueW
0x180105be9  mov     edi, eax
0x180105beb  test    eax, eax
0x180105bed  jnz     loc_180105ED4
0x180105bf3  xor     edx, edx; Val
0x180105bf5  mov     r8d, 118h; Size
0x180105bfb  lea     rcx, [rsp+9D0h+VersionInformation.dwMajorVersion]; void *
0x180105c00  call    memset_0
0x180105c05  mov     [rsp+9D0h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x180105c0d  lea     rcx, [rsp+9D0h+VersionInformation]; lpVersionInformation
0x180105c12  call    cs:__imp_GetVersionExW
0x180105c18  test    eax, eax
0x180105c1a  jz      loc_180105EB8
0x180105c20  mov     ecx, [rsp+9D0h+VersionInformation.dwMajorVersion]
0x180105c24  lea     eax, [rcx+rcx*4]
0x180105c27  mov     edx, [rsp+9D0h+VersionInformation.dwMinorVersion]
0x180105c2b  lea     eax, [rdx+rax*2]
0x180105c2e  cmp     eax, 64h ; 'd'
0x180105c31  ja      short loc_180105C67
0x180105c33  test    r12d, r12d
0x180105c36  jz      short loc_180105C67
0x180105c38  mov     edi, r13d
0x180105c3b  lea     r13, __ImageBase
0x180105c42  movsxd  rdx, edi
0x180105c45  mov     rdx, ds:rva off_1801CD570[r13+rdx*8]; SubStr
0x180105c4d  mov     rcx, rbx; Str
0x180105c50  call    ?RemoveAttribute@@YAXPEAGPEBG@Z; RemoveAttribute(ushort *,ushort const *)
0x180105c55  inc     edi
0x180105c57  cmp     edi, 2
0x180105c5a  jb      short loc_180105C42
0x180105c5c  xor     r13d, r13d
0x180105c5f  mov     edx, [rsp+9D0h+VersionInformation.dwMinorVersion]
0x180105c63  mov     ecx, [rsp+9D0h+VersionInformation.dwMajorVersion]
0x180105c67  lea     eax, [rcx+rcx*4]
0x180105c6a  lea     ecx, [rdx+rax*2]
0x180105c6d  cmp     ecx, 3Eh ; '>'
0x180105c70  jnb     loc_180105D0F
0x180105c76  test    r12d, r12d
0x180105c79  jnz     loc_180105D0F
0x180105c7f  lea     r8, [rbp+8D0h+Name]; unsigned __int16 *
0x180105c86  mov     rdx, rbx; unsigned __int16 *
0x180105c89  mov     rcx, rsi; struct IRequestContext *
0x180105c8c  call    ?RemoveRunAsUserIfPresent@@YA_NPEAVIRequestContext@@PEBG1@Z; RemoveRunAsUserIfPresent(IRequestContext *,ushort const *,ushort const *)
0x180105c91  test    al, al
0x180105c93  jnz     short loc_180105CAF
0x180105c95  lea     ecx, [r12+2]; Ix
0x180105c9a  call    __acrt_iob_func
0x180105c9f  mov     rcx, rax; Stream
0x180105ca2  lea     rdx, aCanNotRemoveTh; "Can not remove the credentials from Cre"...
0x180105ca9  call    cs:__imp_fwprintf
0x180105caf  mov     rcx, rbx; Str
0x180105cb2  call    ?DowngradeSDKVersion@@YA_NPEBG0@Z; DowngradeSDKVersion(ushort const *,ushort const *)
0x180105cb7  test    al, al
0x180105cb9  jnz     short loc_180105CD5
0x180105cbb  mov     ecx, 2; Ix
0x180105cc0  call    __acrt_iob_func
0x180105cc5  mov     rcx, rax; Stream
0x180105cc8  lea     rdx, aPluginMigratio_11; "Plugin Migration ERROR: Failed to updat"...
0x180105ccf  call    cs:__imp_fwprintf
0x180105cd5  mov     edi, r13d
0x180105cd8  lea     r13, __ImageBase
0x180105cdf  movsxd  rdx, edi
0x180105ce2  mov     rdx, ds:rva off_1801CD580[r13+rdx*8]; SubStr
0x180105cea  mov     rcx, rbx; Str
0x180105ced  call    ?RemoveAttribute@@YAXPEAGPEBG@Z; RemoveAttribute(ushort *,ushort const *)
0x180105cf2  inc     edi
0x180105cf4  cmp     edi, 6
0x180105cf7  jb      short loc_180105CDF
0x180105cf9  xor     r13d, r13d
0x180105cfc  mov     rdx, rbx; unsigned __int16 *
0x180105cff  mov     rcx, rsi; struct IRequestContext *
0x180105d02  call    ?RemoveNode@@YA_NPEAVIRequestContext@@PEBG1@Z; RemoveNode(IRequestContext *,ushort const *,ushort const *)
0x180105d07  test    al, al
0x180105d09  jz      loc_180105E37
0x180105d0f  lea     rax, [rbp+8D0h+Name]
0x180105d16  mov     [rsp+9D0h+lpReserved], rax
0x180105d1b  lea     r9, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180105d22  lea     r8, aSS_0; "%s\\%s"
0x180105d29  mov     edx, 200h; unsigned __int64
0x180105d2e  lea     rcx, [rbp+8D0h+SubKey]; unsigned __int16 *
0x180105d35  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180105d3a  mov     edi, eax
0x180105d3c  test    eax, eax
0x180105d3e  js      loc_180105E88
0x180105d44  mov     [rsp+9D0h+phkResult], r13
0x180105d49  mov     [rsp+9D0h+dwDisposition], r13d
0x180105d4e  lea     rax, [rsp+9D0h+dwDisposition]
0x180105d53  mov     [rsp+9D0h+lpdwDisposition], rax; lpdwDisposition
0x180105d58  lea     rax, [rsp+9D0h+phkResult]
0x180105d5d  mov     [rsp+9D0h+lpftLastWriteTime], rax; phkResult
0x180105d62  mov     [rsp+9D0h+lpcchClass], r13; lpSecurityAttributes
0x180105d67  mov     dword ptr [rsp+9D0h+lpClass], 6011Bh; samDesired
0x180105d6f  mov     dword ptr [rsp+9D0h+lpReserved], r13d; dwOptions
0x180105d74  lea     r9, Class; lpClass
0x180105d7b  xor     r8d, r8d; Reserved
0x180105d7e  lea     rdx, [rbp+8D0h+SubKey]; lpSubKey
0x180105d85  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180105d8c  call    cs:__imp_RegCreateKeyExW
0x180105d92  mov     edi, eax
0x180105d94  test    eax, eax
0x180105d96  jnz     loc_180105E4A
0x180105d9c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180105da0  inc     rax
0x180105da3  cmp     [rbx+rax*2], r13w
0x180105da8  jnz     short loc_180105DA0
0x180105daa  lea     eax, ds:2[rax*2]
0x180105db1  mov     dword ptr [rsp+9D0h+lpClass], eax; cbData
0x180105db5  mov     [rsp+9D0h+lpReserved], rbx; lpData
0x180105dba  mov     r9d, 1; dwType
0x180105dc0  xor     r8d, r8d; Reserved
0x180105dc3  lea     rdx, Value; "ConfigXML"
0x180105dca  mov     rcx, [rsp+9D0h+phkResult]; hKey
0x180105dcf  call    cs:__imp_RegSetValueExW
0x180105dd5  mov     edi, eax
0x180105dd7  test    eax, eax
0x180105dd9  jnz     short loc_180105E4A
0x180105ddb  lea     rcx, [rsp+9D0h+phkResult]
0x180105de0  call    ??1?$AutoCleanup@VAutoRegKey@@PEAUHKEY__@@@@QEAA@XZ; AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(void)
0x180105de5  nop
0x180105de6  lea     rcx, [rsp+9D0h+var_980]
0x180105deb  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x180105df0  jmp     loc_180105B2B
0x180105df5  cmp     edi, 103h
0x180105dfb  jz      loc_180105B2B
0x180105e01  mov     ecx, 2; Ix
0x180105e06  call    __acrt_iob_func
0x180105e0b  mov     rcx, rax; Stream
0x180105e0e  mov     r9d, r14d
0x180105e11  mov     r8d, edi
0x180105e14  lea     rdx, aPluginMigratio_2; "Plugin Migration ERROR: RegEnumKeyEx re"...
0x180105e1b  call    cs:__imp_fwprintf
0x180105e21  mov     rax, [rsi]
0x180105e24  mov     edx, edi
0x180105e26  mov     rcx, rsi
0x180105e29  mov     rax, [rax+48h]
0x180105e2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180105e32  jmp     loc_180105F1B
0x180105e37  mov     ecx, 2; Ix
0x180105e3c  call    __acrt_iob_func
0x180105e41  lea     rdx, aPluginMigratio_1; "Plugin Migration ERROR: Failed to remov"...
0x180105e48  jmp     short loc_180105EC9
0x180105e4a  mov     ecx, 2; Ix
0x180105e4f  call    __acrt_iob_func
0x180105e54  mov     rcx, rax; Stream
0x180105e57  mov     r8d, edi
0x180105e5a  lea     rdx, aPluginMigratio_8; "Plugin Migration ERROR: RegSetValueEx r"...
0x180105e61  call    cs:__imp_fwprintf
0x180105e67  mov     rax, [rsi]
0x180105e6a  mov     edx, edi
0x180105e6c  mov     rcx, rsi
0x180105e6f  mov     rax, [rax+48h]
0x180105e73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180105e78  nop
0x180105e79  lea     rcx, [rsp+9D0h+phkResult]
0x180105e7e  call    ??1?$AutoCleanup@VAutoRegKey@@PEAUHKEY__@@@@QEAA@XZ; AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(void)
0x180105e83  jmp     loc_180105F11
0x180105e88  mov     ecx, 2; Ix
0x180105e8d  call    __acrt_iob_func
0x180105e92  lea     rdx, aPluginMigratio; "Plugin Migration ERROR: StringCchPrintf"...
0x180105e99  mov     r8d, edi
0x180105e9c  mov     rcx, rax; Stream
0x180105e9f  call    cs:__imp_fwprintf
0x180105ea5  mov     rax, [rsi]
0x180105ea8  mov     edx, edi
0x180105eaa  mov     rcx, rsi
0x180105ead  mov     rax, [rax+48h]
0x180105eb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180105eb6  jmp     short loc_180105F11
0x180105eb8  mov     ecx, 2; Ix
0x180105ebd  call    __acrt_iob_func
0x180105ec2  lea     rdx, aCanNotGetTheOs; "Can not get the OS version information "...
0x180105ec9  mov     rcx, rax; Stream
0x180105ecc  call    cs:__imp_fwprintf
0x180105ed2  jmp     short loc_180105F11
0x180105ed4  mov     ecx, 2; Ix
0x180105ed9  call    __acrt_iob_func
0x180105ede  lea     rdx, aPluginMigratio_6; "Plugin Migration ERROR: RegGetValue ret"...
0x180105ee5  jmp     short loc_180105E99
0x180105ee7  mov     ecx, 2; Ix
0x180105eec  call    __acrt_iob_func
0x180105ef1  mov     rcx, rax; Stream
0x180105ef4  lea     rdx, aCanNotCreateBu; "Can not create buffer.\n"
0x180105efb  call    cs:__imp_fwprintf
0x180105f01  mov     rax, [rsi]
0x180105f04  mov     rcx, rsi
0x180105f07  mov     rax, [rax+18h]
0x180105f0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180105f10  nop
0x180105f11  lea     rcx, [rsp+9D0h+var_980]
0x180105f16  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x180105f1b  xor     eax, eax
0x180105f1d  jmp     short loc_180105F24
0x180105f1f  mov     eax, 1
0x180105f24  mov     rcx, [rbp+8D0h+var_40]
0x180105f2b  xor     rcx, rsp; StackCookie
0x180105f2e  call    __security_check_cookie
0x180105f33  mov     rbx, [rsp+9D0h+arg_10]
0x180105f3b  add     rsp, 9A0h
0x180105f42  pop     r15
0x180105f44  pop     r14
0x180105f46  pop     r13
0x180105f48  pop     r12
0x180105f4a  pop     rdi
0x180105f4b  pop     rsi
0x180105f4c  pop     rbp
0x180105f4d  retn
```
