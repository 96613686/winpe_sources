# OSIntegration::DEH::Internal::DefaultBackgroundTasksClassHelper::DeletePackageCapabilitiesInternal(OSIntegration::Package const *,OSIntegration::Tools::MoCOMHelper const *)

- ea: `0x180006454`
- end: `0x18000676a`
- name: `?DeletePackageCapabilitiesInternal@DefaultBackgroundTasksClassHelper@Internal@DEH@OSIntegration@@CAJPEBVPackage@4@PEBVMoCOMHelper@Tools@4@@Z`
- size: `790`
- prototype: `__int64 __fastcall(const struct OSIntegration::Package *, const struct OSIntegration::Tools::MoCOMHelper *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180006258`

## callees

- `0x180006454`
- `0x180012964`
- `0x18004f3c4`
- `0x180067050`
- `0x180087238`
- `0x180098bf4`
- `0x1800a021c`
- `0x1800a2854`
- `0x1800f0260`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000658c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000658c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800065cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800065cd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000653b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000653b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006511`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006511`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800065ab`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18000675f`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800065ab`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18000675f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800064b6`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800064b6`

## string_xrefs

- `0x180006624`: `onecore\admin\appmodel\osim\src\deh\uex\defaultbackgroundtasks\defaultbackgroundtasksclasshelper.cpp`
- `0x180006690`: `onecore\admin\appmodel\osim\src\deh\uex\defaultbackgroundtasks\defaultbackgroundtasksclasshelper.cpp`
- `0x1800066ad`: `onecore\admin\appmodel\osim\src\deh\uex\defaultbackgroundtasks\defaultbackgroundtasksclasshelper.cpp`
- `0x180006700`: `onecore\admin\appmodel\osim\src\deh\uex\defaultbackgroundtasks\defaultbackgroundtasksclasshelper.cpp`
- `0x18000671c`: `onecore\admin\appmodel\osim\src\deh\uex\defaultbackgroundtasks\defaultbackgroundtasksclasshelper.cpp`

## pseudocode

```c
__int64 __fastcall OSIntegration::DEH::Internal::DefaultBackgroundTasksClassHelper::DeletePackageCapabilitiesInternal(
        const struct OSIntegration::Package *a1,
        LPCWSTR *a2)
{
  void *v4; // rcx
  const char *v5; // r9
  int v6; // eax
  int LastError; // ebx
  __int64 v8; // rbx
  unsigned int v9; // eax
  DWORD v10; // eax
  int IsStateSeparationEnabled; // eax
  unsigned int v13; // edi
  __int64 v14; // rdx
  __int64 v15; // rdx
  int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  PHKEY phkResultb; // [rsp+20h] [rbp-E0h]
  bool v19; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cSubKeys; // [rsp+64h] [rbp-9Ch] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  LPWSTR StringSid[2]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR SubKey[520]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4B8h] [rbp+3B8h]

  if ( *((_BYTE *)a1 + 403) )
    return 0;
  if ( *((_BYTE *)a1 + 406) )
  {
    v19 = 0;
    IsStateSeparationEnabled = Common::StateSeparation::GetIsStateSeparationEnabled(&v19);
    v13 = IsStateSeparationEnabled;
    if ( IsStateSeparationEnabled < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xFE,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\defaultbackgroundtasks\\defaultbackgroundtasksclasshelper.cpp",
        (const char *)(unsigned int)IsStateSeparationEnabled,
        phkResult);
      return v13;
    }
    if ( v19 )
    {
      phkResultb = (PHKEY)L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\Notifications\\BackgroundCapability";
      LastError = StringCchPrintfW(SubKey, 0x208u, L"%s\\%s\\%s", L"OSDATA");
      if ( LastError < 0 )
      {
        v14 = 264;
LABEL_24:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v14,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\defaultbackgroundtasks\\defaultbackgroundtasksclasshelper.cpp",
          (const char *)(unsigned int)LastError,
          (int)phkResultb);
        return (unsigned int)LastError;
      }
    }
    else
    {
      LODWORD(phkResultb) = *((_QWORD *)a1 + 89);
      LastError = StringCchPrintfW(
                    SubKey,
                    0x208u,
                    L"%s\\%s",
                    L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\Notifications\\BackgroundCapability");
      if ( LastError < 0 )
      {
        v14 = 272;
        goto LABEL_24;
      }
    }
    v8 = -2147483646;
LABEL_7:
    cSubKeys = 0;
    hKey = 0;
    v9 = RegOpenKeyExW((HKEY)v8, SubKey, 0, 0x2001Fu, &hKey);
    if ( v9 == 2 )
    {
      LastError = 0;
    }
    else
    {
      if ( v9 )
      {
        v15 = 303;
      }
      else
      {
        v9 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        if ( v9 )
        {
          v15 = 316;
        }
        else
        {
          v10 = cSubKeys;
          if ( !cSubKeys )
          {
LABEL_13:
            if ( hKey )
            {
              RegCloseKey(hKey);
              v10 = cSubKeys;
            }
            if ( !v10 )
              RegDeleteKeyW((HKEY)v8, SubKey);
            return 0;
          }
          v9 = RegDeleteKeyW(hKey, a2[7]);
          if ( !v9 )
          {
            v10 = --cSubKeys;
            goto LABEL_13;
          }
          v15 = 319;
        }
      }
      LastError = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)v15,
                    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\defaultbackgroundtasks\\defaultbackgrou"
                                  "ndtasksclasshelper.cpp",
                    (const char *)v9,
                    phkResulta);
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return (unsigned int)LastError;
  }
  v4 = (void *)*((_QWORD *)a1 + 98);
  StringSid[0] = 0;
  if ( ConvertSidToStringSidW(v4, StringSid) )
  {
    v6 = StringCchPrintfW(SubKey, 0x208u, L"%s\\%s\\%s", StringSid[0]);
    LastError = v6;
    if ( v6 >= 0 )
    {
      v8 = -2147483645;
      if ( StringSid[0] )
        LocalFree(StringSid[0]);
      goto LABEL_7;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11E,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\defaultbackgroundtasks\\defaultbackgroundtasksclasshelper.cpp",
      (const char *)(unsigned int)v6,
      (int)L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\Notifications\\BackgroundCapability");
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x117,
                  (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\uex\\defaultbackgroundtasks\\defaultbackground"
                                "tasksclasshelper.cpp",
                  v5);
  }
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(StringSid);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180006454  mov     [rsp-8+arg_10], rbx
0x180006459  mov     [rsp-8+arg_18], rsi
0x18000645e  push    rbp
0x18000645f  push    rdi
0x180006460  push    r14
0x180006462  lea     rbp, [rsp-3A0h]
0x18000646a  sub     rsp, 4A0h
0x180006471  mov     rax, cs:__security_cookie
0x180006478  xor     rax, rsp
0x18000647b  mov     [rbp+3B0h+var_20], rax
0x180006482  xor     r14d, r14d
0x180006485  mov     rsi, rdx
0x180006488  mov     rbx, rcx
0x18000648b  cmp     [rcx+193h], r14b
0x180006492  jnz     loc_1800065DF
0x180006498  cmp     [rcx+196h], r14b
0x18000649f  jnz     loc_180006608
0x1800064a5  mov     rcx, [rcx+310h]; Sid
0x1800064ac  lea     rdx, [rsp+4B0h+StringSid]; StringSid
0x1800064b1  mov     [rsp+4B0h+StringSid], r14
0x1800064b6  call    cs:__imp_ConvertSidToStringSidW
0x1800064bc  test    eax, eax
0x1800064be  jz      loc_1800066F9
0x1800064c4  mov     rax, [rbx+2C8h]
0x1800064cb  lea     r8, aSSS; "%s\\%s\\%s"
0x1800064d2  mov     r9, [rsp+4B0h+StringSid]
0x1800064d7  lea     rcx, [rbp+3B0h+SubKey]; Buffer
0x1800064db  mov     [rsp+4B0h+lpcbMaxSubKeyLen], rax
0x1800064e0  mov     edx, 208h; unsigned __int64
0x1800064e5  lea     rax, aSoftwareMicros_25; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800064ec  mov     [rsp+4B0h+phkResult], rax; int
0x1800064f1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800064f6  mov     ebx, eax
0x1800064f8  test    eax, eax
0x1800064fa  js      loc_180006715
0x180006500  mov     rcx, [rsp+4B0h+StringSid]; hMem
0x180006505  mov     rbx, 0FFFFFFFF80000003h
0x18000650c  test    rcx, rcx
0x18000650f  jz      short loc_180006517
0x180006511  call    cs:__imp_LocalFree
0x180006517  lea     rax, [rsp+4B0h+hKey]
0x18000651c  mov     [rsp+4B0h+cSubKeys], r14d
0x180006521  mov     r9d, 2001Fh; samDesired
0x180006527  mov     [rsp+4B0h+phkResult], rax; phkResult
0x18000652c  xor     r8d, r8d; ulOptions
0x18000652f  mov     [rsp+4B0h+hKey], r14
0x180006534  lea     rdx, [rbp+3B0h+SubKey]; lpSubKey
0x180006538  mov     rcx, rbx; hKey
0x18000653b  call    cs:__imp_RegOpenKeyExW
0x180006541  cmp     eax, 2
0x180006544  jz      loc_18000673C
0x18000654a  test    eax, eax
0x18000654c  jnz     loc_180006744
0x180006552  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180006557  lea     rax, [rsp+4B0h+cSubKeys]
0x18000655c  mov     [rsp+4B0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x180006561  xor     r9d, r9d; lpReserved
0x180006564  mov     [rsp+4B0h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x180006569  xor     r8d, r8d; lpcchClass
0x18000656c  mov     [rsp+4B0h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x180006571  xor     edx, edx; lpClass
0x180006573  mov     [rsp+4B0h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x180006578  mov     [rsp+4B0h+lpcValues], r14; lpcValues
0x18000657d  mov     [rsp+4B0h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x180006582  mov     [rsp+4B0h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x180006587  mov     [rsp+4B0h+phkResult], rax; unsigned int
0x18000658c  call    cs:__imp_RegQueryInfoKeyW
0x180006592  test    eax, eax
0x180006594  jnz     loc_18000674E
0x18000659a  mov     eax, [rsp+4B0h+cSubKeys]
0x18000659e  test    eax, eax
0x1800065a0  jz      short loc_1800065C3
0x1800065a2  mov     rdx, [rsi+38h]; lpSubKey
0x1800065a6  mov     rcx, [rsp+4B0h+hKey]; hKey
0x1800065ab  call    cs:__imp_RegDeleteKeyW
0x1800065b1  test    eax, eax
0x1800065b3  jnz     loc_1800066A1
0x1800065b9  mov     eax, [rsp+4B0h+cSubKeys]
0x1800065bd  dec     eax
0x1800065bf  mov     [rsp+4B0h+cSubKeys], eax
0x1800065c3  mov     rcx, [rsp+4B0h+hKey]; hKey
0x1800065c8  test    rcx, rcx
0x1800065cb  jz      short loc_1800065D7
0x1800065cd  call    cs:__imp_RegCloseKey
0x1800065d3  mov     eax, [rsp+4B0h+cSubKeys]
0x1800065d7  test    eax, eax
0x1800065d9  jz      loc_180006758
0x1800065df  xor     eax, eax
0x1800065e1  mov     rcx, [rbp+3B0h+var_20]
0x1800065e8  xor     rcx, rsp; StackCookie
0x1800065eb  call    __security_check_cookie
0x1800065f0  lea     r11, [rsp+4B0h+var_10]
0x1800065f8  mov     rbx, [r11+30h]
0x1800065fc  mov     rsi, [r11+38h]
0x180006600  mov     rsp, r11
0x180006603  pop     r14
0x180006605  pop     rdi
0x180006606  pop     rbp
0x180006607  retn
0x180006608  lea     rcx, [rsp+4B0h+var_450]; bool *
0x18000660d  mov     [rsp+4B0h+var_450], r14b
0x180006612  call    ?GetIsStateSeparationEnabled@StateSeparation@Common@@SAJPEA_N@Z; Common::StateSeparation::GetIsStateSeparationEnabled(bool *)
0x180006617  mov     edi, eax
0x180006619  test    eax, eax
0x18000661b  jns     short loc_18000663C
0x18000661d  mov     rcx, [rbp+3B8h]; this
0x180006624  lea     r8, aOnecoreAdminAp_41; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18000662b  mov     r9d, eax; char *
0x18000662e  mov     edx, 0FEh; void *
0x180006633  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006638  mov     eax, edi
0x18000663a  jmp     short loc_1800065E1
0x18000663c  lea     rcx, [rbp+3B0h+SubKey]; Buffer
0x180006640  mov     rax, [rbx+2C8h]
0x180006647  mov     edx, 208h; unsigned __int64
0x18000664c  cmp     [rsp+4B0h+var_450], r14b
0x180006651  jz      short loc_1800066CF
0x180006653  mov     [rsp+4B0h+lpcbMaxSubKeyLen], rax
0x180006658  lea     r9, aOsdata; "OSDATA"
0x18000665f  lea     rax, aSoftwareMicros_25; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180006666  lea     r8, aSSS; "%s\\%s\\%s"
0x18000666d  mov     [rsp+4B0h+phkResult], rax
0x180006672  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006677  mov     ebx, eax
0x180006679  test    eax, eax
0x18000667b  jns     short loc_1800066ED
0x18000667d  mov     edx, 108h
0x180006682  jmp     short loc_180006689
0x180006684  mov     edx, 110h; void *
0x180006689  mov     rcx, [rbp+3B8h]; this
0x180006690  lea     r8, aOnecoreAdminAp_41; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180006697  mov     r9d, ebx; char *
0x18000669a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000669f  jmp     short loc_1800066C8
0x1800066a1  mov     edx, 13Fh; void *
0x1800066a6  mov     rcx, [rbp+3B8h]; this
0x1800066ad  lea     r8, aOnecoreAdminAp_41; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800066b4  mov     r9d, eax; char *
0x1800066b7  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800066bc  mov     ebx, eax
0x1800066be  lea     rcx, [rsp+4B0h+hKey]
0x1800066c3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800066c8  mov     eax, ebx
0x1800066ca  jmp     loc_1800065E1
0x1800066cf  lea     r9, aSoftwareMicros_25; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800066d6  mov     [rsp+4B0h+phkResult], rax; int
0x1800066db  lea     r8, aSS; "%s\\%s"
0x1800066e2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800066e7  mov     ebx, eax
0x1800066e9  test    eax, eax
0x1800066eb  js      short loc_180006684
0x1800066ed  mov     rbx, 0FFFFFFFF80000002h
0x1800066f4  jmp     loc_180006517
0x1800066f9  mov     rcx, [rbp+3B8h]; this
0x180006700  lea     r8, aOnecoreAdminAp_41; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180006707  mov     edx, 117h; void *
0x18000670c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006711  mov     ebx, eax
0x180006713  jmp     short loc_180006730
0x180006715  mov     rcx, [rbp+3B8h]; this
0x18000671c  lea     r8, aOnecoreAdminAp_41; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180006723  mov     r9d, eax; char *
0x180006726  mov     edx, 11Eh; void *
0x18000672b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006730  lea     rcx, [rsp+4B0h+StringSid]
0x180006735  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18000673a  jmp     short loc_1800066C8
0x18000673c  mov     ebx, r14d
0x18000673f  jmp     loc_1800066BE
0x180006744  mov     edx, 12Fh
0x180006749  jmp     loc_1800066A6
0x18000674e  mov     edx, 13Ch
0x180006753  jmp     loc_1800066A6
0x180006758  lea     rdx, [rbp+3B0h+SubKey]; lpSubKey
0x18000675c  mov     rcx, rbx; hKey
0x18000675f  call    cs:__imp_RegDeleteKeyW
0x180006765  jmp     loc_1800065DF
```
