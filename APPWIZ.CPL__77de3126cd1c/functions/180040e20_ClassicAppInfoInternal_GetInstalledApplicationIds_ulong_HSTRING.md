# ClassicAppInfoInternal::GetInstalledApplicationIds(ulong *,HSTRING__ * * *)

- ea: `0x180040e20`
- end: `0x180041188`
- name: `?GetInstalledApplicationIds@ClassicAppInfoInternal@@UEAAJPEAKPEAPEAPEAUHSTRING__@@@Z`
- size: `872`
- prototype: `__int64 __fastcall(ClassicAppInfoInternal *__hidden this, unsigned int *, HSTRING **)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180007560`
- `0x1800405c4`
- `0x180040a3c`
- `0x180040e20`
- `0x180041d00`
- `0x1800582a2`
- `0x1800582e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180040e92`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180040f24`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180040e92`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180040f24`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180040edd`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180040f8d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180040edd`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180040f8d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180040f9f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180040f9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004102d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800410f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004102d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800410f4`
- `ADVAPI32!RegEnumKeyW` at `0x180041005`
- `ADVAPI32!RegEnumKeyW` at `0x1800410cc`
- `ADVAPI32!RegEnumKeyW` at `0x180041005`
- `ADVAPI32!RegEnumKeyW` at `0x1800410cc`

## string_xrefs

- `0x180040fb4`: `shell\cpls\appwzdui\installedclassicappinfo.cpp`
- `0x18004104f`: `shell\cpls\appwzdui\installedclassicappinfo.cpp`
- `0x180041091`: `shell\cpls\appwzdui\installedclassicappinfo.cpp`
- `0x180040e83`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Uninstall`
- `0x180040f1a`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Uninstall`

## pseudocode

```c
__int64 __fastcall ClassicAppInfoInternal::GetInstalledApplicationIds(
        ClassicAppInfoInternal *this,
        unsigned int *a2,
        HSTRING **a3)
{
  HRESULT String; // r14d
  unsigned int v6; // eax
  unsigned int v7; // r8d
  __int64 v8; // rdx
  int v9; // ebx
  unsigned int v10; // eax
  unsigned int v11; // r8d
  HSTRING *v12; // rsi
  unsigned int v13; // edi
  DWORD v14; // edx
  LSTATUS v15; // eax
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // rdx
  unsigned int v19; // r15d
  __int64 v20; // rdx
  bool v21; // sf
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  int phkResultb; // [rsp+20h] [rbp-E0h]
  HKEY v26; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cSubKeys; // [rsp+68h] [rbp-98h] BYREF
  DWORD v28; // [rsp+6Ch] [rbp-94h] BYREF
  HKEY hKey[2]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Name[256]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  String = 0;
  *a2 = 0;
  *a3 = 0;
  cSubKeys = 0;
  v28 = 0;
  hKey[0] = 0;
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall", 0, 0x20219u, hKey);
  if ( v6 )
  {
    v8 = 186;
LABEL_5:
    v9 = wil::details::in1diag3::Return_Win32(retaddr, (void *)v8, v7, (const char *)v6, phkResult);
    goto LABEL_43;
  }
  v6 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
  if ( v6 )
  {
    v8 = 187;
    goto LABEL_5;
  }
  v26 = 0;
  v10 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall", 0, 0x20119u, &v26);
  if ( v10 )
  {
    v9 = wil::details::in1diag3::Return_Win32(retaddr, (void *)0xC6, v11, (const char *)v10, phkResulta);
LABEL_8:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v26);
    goto LABEL_43;
  }
  RegQueryInfoKeyW(v26, 0, 0, 0, &v28, 0, 0, 0, 0, 0, 0, 0);
  v12 = (HSTRING *)CoTaskMemAlloc(8LL * (cSubKeys + v28));
  if ( !v12 )
  {
    v9 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCB,
      (unsigned int)"shell\\cpls\\appwzdui\\installedclassicappinfo.cpp",
      (const char *)0x8007000ELL,
      phkResultb);
    goto LABEL_8;
  }
  v13 = 0;
  memset_0(Name, 0, sizeof(Name));
  v14 = 0;
  v9 = 0;
  while ( 1 )
  {
    if ( v14 >= cSubKeys )
      goto LABEL_27;
    v15 = RegEnumKeyW(hKey[0], v14, Name, 0x100u);
    v9 = v15;
    if ( v15 )
    {
      if ( v15 != 259 )
      {
        if ( v15 > 0 )
          v9 = (unsigned __int16)v15 | 0x80070000;
        if ( v9 < 0 )
        {
          v18 = 222;
LABEL_25:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v18,
            (unsigned int)"shell\\cpls\\appwzdui\\installedclassicappinfo.cpp",
            (const char *)(unsigned int)v9,
            phkResultb);
        }
LABEL_26:
        DeleteStringArray(v13, v12);
        goto LABEL_8;
      }
LABEL_27:
      v19 = v13;
      while ( v13 - v19 < v28 )
      {
        v9 = RegEnumKeyW(v26, v13 - v19, Name, 0x100u);
        if ( v9 )
          goto LABEL_36;
        v20 = -1;
        do
          ++v20;
        while ( Name[v20] );
        String = WindowsCreateString(Name, v20, &v12[v13]);
        if ( String < 0 )
        {
          v17 = 231;
          goto LABEL_19;
        }
        ++v13;
        String = 0;
      }
      if ( v9 )
      {
LABEL_36:
        if ( v9 != 259 )
        {
          v21 = v9 < 0;
          if ( v9 > 0 )
          {
            v9 = (unsigned __int16)v9 | 0x80070000;
            v21 = v9 < 0;
          }
          if ( v21 )
          {
            v18 = 234;
            goto LABEL_25;
          }
          goto LABEL_26;
        }
      }
      *a3 = v12;
      *a2 = v13;
      goto LABEL_42;
    }
    v16 = -1;
    do
      ++v16;
    while ( Name[v16] );
    String = WindowsCreateString(Name, v16, &v12[v13]);
    if ( String < 0 )
      break;
    v14 = ++v13;
    String = 0;
  }
  v17 = 219;
LABEL_19:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v17,
    (unsigned int)"shell\\cpls\\appwzdui\\installedclassicappinfo.cpp",
    (const char *)(unsigned int)String,
    phkResultb);
  DeleteStringArray(v13, v12);
LABEL_42:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v26);
  v9 = String;
LABEL_43:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKey);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180040e20  mov     [rsp-8+arg_0], rbx
0x180040e25  push    rbp
0x180040e26  push    rsi
0x180040e27  push    rdi
0x180040e28  push    r12
0x180040e2a  push    r13
0x180040e2c  push    r14
0x180040e2e  push    r15
0x180040e30  lea     rbp, [rsp-190h]
0x180040e38  sub     rsp, 290h
0x180040e3f  mov     rax, cs:__security_cookie
0x180040e46  xor     rax, rsp
0x180040e49  mov     [rbp+1C0h+var_40], rax
0x180040e50  xor     r14d, r14d
0x180040e53  lea     rax, [rsp+2C0h+hKey]
0x180040e58  mov     [rdx], r14d
0x180040e5b  mov     r13, r8
0x180040e5e  mov     [r8], r14
0x180040e61  mov     r12, rdx
0x180040e64  mov     rbx, 0FFFFFFFF80000002h
0x180040e6b  mov     [rsp+2C0h+cSubKeys], r14d
0x180040e70  xor     r8d, r8d; ulOptions
0x180040e73  mov     [rsp+2C0h+var_254], r14d
0x180040e78  mov     r9d, 20219h; samDesired
0x180040e7e  mov     [rsp+2C0h+hKey], r14
0x180040e83  lea     rdx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180040e8a  mov     [rsp+2C0h+phkResult], rax; phkResult
0x180040e8f  mov     rcx, rbx; hKey
0x180040e92  call    cs:__imp_RegOpenKeyExW
0x180040e98  test    eax, eax
0x180040e9a  jz      short loc_180040EA3
0x180040e9c  mov     edx, 0BAh
0x180040ea1  jmp     short loc_180040EEC
0x180040ea3  mov     rcx, [rsp+2C0h+hKey]; hKey
0x180040ea8  lea     rax, [rsp+2C0h+cSubKeys]
0x180040ead  mov     [rsp+2C0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x180040eb2  xor     r9d, r9d; lpReserved
0x180040eb5  mov     [rsp+2C0h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x180040eba  xor     r8d, r8d; lpcchClass
0x180040ebd  mov     [rsp+2C0h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x180040ec2  xor     edx, edx; lpClass
0x180040ec4  mov     [rsp+2C0h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x180040ec9  mov     [rsp+2C0h+lpcValues], r14; lpcValues
0x180040ece  mov     [rsp+2C0h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x180040ed3  mov     [rsp+2C0h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x180040ed8  mov     [rsp+2C0h+phkResult], rax; unsigned int
0x180040edd  call    cs:__imp_RegQueryInfoKeyW
0x180040ee3  test    eax, eax
0x180040ee5  jz      short loc_180040F02
0x180040ee7  mov     edx, 0BBh; void *
0x180040eec  mov     rcx, [rbp+1C8h]; this
0x180040ef3  mov     r9d, eax; char *
0x180040ef6  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180040efb  mov     ebx, eax
0x180040efd  jmp     loc_180041152
0x180040f02  lea     rax, [rsp+2C0h+var_260]
0x180040f07  mov     [rsp+2C0h+var_260], r14
0x180040f0c  mov     r9d, 20119h; samDesired
0x180040f12  mov     [rsp+2C0h+phkResult], rax; unsigned int
0x180040f17  xor     r8d, r8d; ulOptions
0x180040f1a  lea     rdx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180040f21  mov     rcx, rbx; hKey
0x180040f24  call    cs:__imp_RegOpenKeyExW
0x180040f2a  test    eax, eax
0x180040f2c  jz      short loc_180040F53
0x180040f2e  mov     rcx, [rbp+1C8h]; this
0x180040f35  mov     r9d, eax; char *
0x180040f38  mov     edx, 0C6h; void *
0x180040f3d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180040f42  mov     ebx, eax
0x180040f44  lea     rcx, [rsp+2C0h+var_260]
0x180040f49  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180040f4e  jmp     loc_180041152
0x180040f53  mov     rcx, [rsp+2C0h+var_260]; hKey
0x180040f58  lea     rax, [rsp+2C0h+var_254]
0x180040f5d  mov     [rsp+2C0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x180040f62  xor     r9d, r9d; lpReserved
0x180040f65  mov     [rsp+2C0h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x180040f6a  xor     r8d, r8d; lpcchClass
0x180040f6d  mov     [rsp+2C0h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x180040f72  xor     edx, edx; lpClass
0x180040f74  mov     [rsp+2C0h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x180040f79  mov     [rsp+2C0h+lpcValues], r14; lpcValues
0x180040f7e  mov     [rsp+2C0h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x180040f83  mov     [rsp+2C0h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x180040f88  mov     [rsp+2C0h+phkResult], rax; int
0x180040f8d  call    cs:__imp_RegQueryInfoKeyW
0x180040f93  mov     ecx, [rsp+2C0h+var_254]
0x180040f97  add     ecx, [rsp+2C0h+cSubKeys]
0x180040f9b  shl     rcx, 3; cb
0x180040f9f  call    cs:__imp_CoTaskMemAlloc
0x180040fa5  mov     rsi, rax
0x180040fa8  test    rax, rax
0x180040fab  jnz     short loc_180040FD2
0x180040fad  mov     rcx, [rbp+1C8h]; this
0x180040fb4  lea     r8, aShellCplsAppwz; "shell\\cpls\\appwzdui\\installedclassic"...
0x180040fbb  mov     ebx, 8007000Eh
0x180040fc0  mov     edx, 0CBh; void *
0x180040fc5  mov     r9d, ebx; char *
0x180040fc8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040fcd  jmp     loc_180040F44
0x180040fd2  xor     edx, edx; Val
0x180040fd4  lea     rcx, [rbp+1C0h+Name]; void *
0x180040fd8  mov     r8d, 200h; Size
0x180040fde  mov     edi, r14d
0x180040fe1  call    memset_0
0x180040fe6  mov     edx, r14d; dwIndex
0x180040fe9  mov     ebx, r14d
0x180040fec  cmp     edx, [rsp+2C0h+cSubKeys]
0x180040ff0  jnb     loc_1800410AF
0x180040ff6  mov     rcx, [rsp+2C0h+hKey]; hKey
0x180040ffb  lea     r8, [rbp+1C0h+Name]; lpName
0x180040fff  mov     r9d, 100h; cchName
0x180041005  call    cs:__imp_RegEnumKeyW
0x18004100b  mov     ebx, eax
0x18004100d  test    eax, eax
0x18004100f  jnz     short loc_18004106D
0x180041011  lea     rax, [rbp+1C0h+Name]
0x180041015  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180041019  inc     rdx; length
0x18004101c  cmp     [rax+rdx*2], r14w
0x180041021  jnz     short loc_180041019
0x180041023  mov     eax, edi
0x180041025  lea     rcx, [rbp+1C0h+Name]; sourceString
0x180041029  lea     r8, [rsi+rax*8]; string
0x18004102d  call    cs:__imp_WindowsCreateString
0x180041033  mov     r14d, eax
0x180041036  test    eax, eax
0x180041038  js      short loc_180041043
0x18004103a  inc     edi
0x18004103c  mov     edx, edi
0x18004103e  xor     r14d, r14d
0x180041041  jmp     short loc_180040FEC
0x180041043  mov     edx, 0DBh; void *
0x180041048  mov     rcx, [rbp+1C8h]; this
0x18004104f  lea     r8, aShellCplsAppwz; "shell\\cpls\\appwzdui\\installedclassic"...
0x180041056  mov     r9d, r14d; char *
0x180041059  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004105e  mov     rdx, rsi; HSTRING *
0x180041061  mov     ecx, edi; unsigned int
0x180041063  call    ?DeleteStringArray@@YAXKPEAPEAUHSTRING__@@@Z; DeleteStringArray(ulong,HSTRING__ * *)
0x180041068  jmp     loc_180041145
0x18004106d  cmp     eax, 103h
0x180041072  jz      short loc_1800410AF
0x180041074  test    eax, eax
0x180041076  jle     short loc_180041081
0x180041078  movzx   ebx, ax
0x18004107b  or      ebx, 80070000h
0x180041081  test    ebx, ebx
0x180041083  jns     short loc_1800410A0
0x180041085  mov     edx, 0DEh; void *
0x18004108a  mov     rcx, [rbp+1C8h]; this
0x180041091  lea     r8, aShellCplsAppwz; "shell\\cpls\\appwzdui\\installedclassic"...
0x180041098  mov     r9d, ebx; char *
0x18004109b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800410a0  mov     rdx, rsi; HSTRING *
0x1800410a3  mov     ecx, edi; unsigned int
0x1800410a5  call    ?DeleteStringArray@@YAXKPEAPEAUHSTRING__@@@Z; DeleteStringArray(ulong,HSTRING__ * *)
0x1800410aa  jmp     loc_180040F44
0x1800410af  mov     r15d, edi
0x1800410b2  mov     edx, edi
0x1800410b4  sub     edx, r15d; dwIndex
0x1800410b7  cmp     edx, [rsp+2C0h+var_254]
0x1800410bb  jnb     short loc_180041112
0x1800410bd  mov     rcx, [rsp+2C0h+var_260]; hKey
0x1800410c2  lea     r8, [rbp+1C0h+Name]; lpName
0x1800410c6  mov     r9d, 100h; cchName
0x1800410cc  call    cs:__imp_RegEnumKeyW
0x1800410d2  mov     ebx, eax
0x1800410d4  test    eax, eax
0x1800410d6  jnz     short loc_180041116
0x1800410d8  lea     rax, [rbp+1C0h+Name]
0x1800410dc  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800410e0  inc     rdx; length
0x1800410e3  cmp     [rax+rdx*2], r14w
0x1800410e8  jnz     short loc_1800410E0
0x1800410ea  mov     eax, edi
0x1800410ec  lea     rcx, [rbp+1C0h+Name]; sourceString
0x1800410f0  lea     r8, [rsi+rax*8]; string
0x1800410f4  call    cs:__imp_WindowsCreateString
0x1800410fa  mov     r14d, eax
0x1800410fd  test    eax, eax
0x1800410ff  js      short loc_180041108
0x180041101  inc     edi
0x180041103  xor     r14d, r14d
0x180041106  jmp     short loc_1800410B2
0x180041108  mov     edx, 0E7h
0x18004110d  jmp     loc_180041048
0x180041112  test    ebx, ebx
0x180041114  jz      short loc_18004113D
0x180041116  cmp     ebx, 103h
0x18004111c  jz      short loc_18004113D
0x18004111e  test    ebx, ebx
0x180041120  jle     short loc_18004112D
0x180041122  movzx   ebx, bx
0x180041125  or      ebx, 80070000h
0x18004112b  test    ebx, ebx
0x18004112d  jns     loc_1800410A0
0x180041133  mov     edx, 0EAh
0x180041138  jmp     loc_18004108A
0x18004113d  mov     [r13+0], rsi
0x180041141  mov     [r12], edi
0x180041145  lea     rcx, [rsp+2C0h+var_260]
0x18004114a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18004114f  mov     ebx, r14d
0x180041152  lea     rcx, [rsp+2C0h+hKey]
0x180041157  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18004115c  mov     eax, ebx
0x18004115e  mov     rcx, [rbp+1C0h+var_40]
0x180041165  xor     rcx, rsp; StackCookie
0x180041168  call    __security_check_cookie
0x18004116d  mov     rbx, [rsp+2C0h+arg_0]
0x180041175  add     rsp, 290h
0x18004117c  pop     r15
0x18004117e  pop     r14
0x180041180  pop     r13
0x180041182  pop     r12
0x180041184  pop     rdi
0x180041185  pop     rsi
0x180041186  pop     rbp
0x180041187  retn
```
