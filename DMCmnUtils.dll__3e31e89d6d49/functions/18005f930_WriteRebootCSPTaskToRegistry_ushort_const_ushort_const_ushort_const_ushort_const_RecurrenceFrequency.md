# WriteRebootCSPTaskToRegistry(ushort const *,ushort const *,ushort const *,ushort const *,RecurrenceFrequency)

- ea: `0x18005f930`
- end: `0x18005fb41`
- name: `?WriteRebootCSPTaskToRegistry@@YAJPEBG000W4RecurrenceFrequency@@@Z`
- size: `529`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task`

## callees

- `0x180007270`
- `0x180057c6c`
- `0x180058420`
- `0x18005d010`
- `0x18005d508`
- `0x18005e730`
- `0x18005f930`
- `0x18005fb90`
- `0x1800617f0`
- `0x1800618d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005fa22`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005fa22`

## string_xrefs

- `0x18005fa63`: `taskfolderpath`
- `0x18005fa87`: `taskname`
- `0x18005faab`: `taskstartboundary`
- `0x18005fad3`: `taskrecurrencefrequency`

## pseudocode

```c
__int64 __fastcall WriteRebootCSPTaskToRegistry(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        unsigned int a5)
{
  const unsigned __int16 *v9; // r8
  int v10; // eax
  unsigned int v11; // ebx
  unsigned int v13; // ebx
  int v14; // eax
  __int64 v15; // rdx
  DWORD dwOptions; // [rsp+20h] [rbp-E0h]
  DWORD dwOptionsa; // [rsp+20h] [rbp-E0h]
  __int64 v18; // [rsp+50h] [rbp-B0h] BYREF
  __int64 *v19; // [rsp+58h] [rbp-A8h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  char v21; // [rsp+68h] [rbp-98h]
  WCHAR SubKey[128]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  if ( isSupportedSkuOnWCOS() )
  {
    v9 = qword_18010E290;
    if ( !a5 )
      v9 = qword_18010E298;
    v10 = StringCchPrintfW(SubKey, 0x80u, v9, a4);
    v11 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7E,
        (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\miscutils\\rebootcsputils.cpp",
        (const char *)(unsigned int)v10,
        dwOptions);
      return v11;
    }
    v19 = &v18;
    v18 = 0;
    phkResult = 0;
    v21 = 1;
    v13 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0xF003Fu, 0, &phkResult, 0);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v19);
    if ( v13 )
    {
      v11 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x81,
              (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\miscutils\\rebootcsputils.cpp",
              (const char *)v13,
              dwOptionsa);
LABEL_18:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v18);
      return v11;
    }
    v14 = OmaDmRegistrySetString(HKEY_LOCAL_MACHINE, SubKey, L"taskfolderpath", a1);
    v11 = v14;
    if ( v14 < 0 )
    {
      v15 = 131;
LABEL_17:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\miscutils\\rebootcsputils.cpp",
        (const char *)(unsigned int)v14,
        dwOptionsa);
      goto LABEL_18;
    }
    v14 = OmaDmRegistrySetString(HKEY_LOCAL_MACHINE, SubKey, L"taskname", a2);
    v11 = v14;
    if ( v14 < 0 )
    {
      v15 = 132;
      goto LABEL_17;
    }
    v14 = OmaDmRegistrySetString(HKEY_LOCAL_MACHINE, SubKey, L"taskstartboundary", a3);
    v11 = v14;
    if ( v14 < 0 )
    {
      v15 = 133;
      goto LABEL_17;
    }
    v14 = OmaDmRegistrySetDWORD(HKEY_LOCAL_MACHINE, SubKey, L"taskrecurrencefrequency", a5);
    v11 = v14;
    if ( v14 < 0 )
    {
      v15 = 134;
      goto LABEL_17;
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v18);
  }
  return 0;
}

```

## disassembly

```asm
0x18005f930  push    rbp
0x18005f932  push    rbx
0x18005f933  push    rsi
0x18005f934  push    r13
0x18005f936  push    r14
0x18005f938  push    r15
0x18005f93a  lea     rbp, [rsp-88h]
0x18005f942  sub     rsp, 188h
0x18005f949  mov     rax, cs:__security_cookie
0x18005f950  xor     rax, rsp
0x18005f953  mov     [rbp+0B0h+var_40], rax
0x18005f957  mov     rbx, r9
0x18005f95a  mov     r15, r8
0x18005f95d  mov     r14, rdx
0x18005f960  mov     rsi, rcx
0x18005f963  call    ?isSupportedSkuOnWCOS@@YA_NXZ; isSupportedSkuOnWCOS(void)
0x18005f968  test    al, al
0x18005f96a  jz      loc_18005FB21
0x18005f970  mov     r8, cs:qword_18010E290
0x18005f977  lea     rcx, [rsp+1B0h+SubKey]; unsigned __int16 *
0x18005f97c  cmp     [rbp+0B0h+arg_20], 0
0x18005f983  mov     r9, rbx
0x18005f986  mov     edx, 80h; unsigned __int64
0x18005f98b  cmovz   r8, cs:qword_18010E298; unsigned __int16 *
0x18005f993  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005f998  mov     ebx, eax
0x18005f99a  test    eax, eax
0x18005f99c  jns     short loc_18005F9C0
0x18005f99e  mov     rcx, [rbp+0B8h]; this
0x18005f9a5  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\dm\\dmcmnutils\\misc"...
0x18005f9ac  mov     r9d, eax; char *
0x18005f9af  mov     edx, 7Eh ; '~'; void *
0x18005f9b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005f9b9  mov     eax, ebx
0x18005f9bb  jmp     loc_18005FB23
0x18005f9c0  mov     [rsp+1B0h+lpdwDisposition], 0; lpdwDisposition
0x18005f9c9  lea     rax, [rsp+1B0h+var_160]
0x18005f9ce  mov     [rsp+1B0h+var_158], rax
0x18005f9d3  lea     rdx, [rsp+1B0h+SubKey]; lpSubKey
0x18005f9d8  lea     rax, [rsp+1B0h+var_150]
0x18005f9dd  mov     [rsp+1B0h+var_160], 0
0x18005f9e6  mov     [rsp+1B0h+phkResult], rax; phkResult
0x18005f9eb  mov     r13, 0FFFFFFFF80000002h
0x18005f9f2  mov     [rsp+1B0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18005f9fb  xor     r9d, r9d; lpClass
0x18005f9fe  mov     [rsp+1B0h+samDesired], 0F003Fh; samDesired
0x18005fa06  xor     r8d, r8d; Reserved
0x18005fa09  mov     rcx, r13; hKey
0x18005fa0c  mov     [rsp+1B0h+dwOptions], 0; int
0x18005fa14  mov     [rsp+1B0h+var_150], 0
0x18005fa1d  mov     [rsp+1B0h+var_148], 1
0x18005fa22  call    cs:__imp_RegCreateKeyExW
0x18005fa29  nop     dword ptr [rax+rax+00h]
0x18005fa2e  lea     rcx, [rsp+1B0h+var_158]
0x18005fa33  mov     ebx, eax
0x18005fa35  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18005fa3a  test    ebx, ebx
0x18005fa3c  jz      short loc_18005FA60
0x18005fa3e  mov     rcx, [rbp+0B8h]; this
0x18005fa45  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\dm\\dmcmnutils\\misc"...
0x18005fa4c  mov     r9d, ebx; char *
0x18005fa4f  mov     edx, 81h; void *
0x18005fa54  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18005fa59  mov     ebx, eax
0x18005fa5b  jmp     loc_18005FB08
0x18005fa60  mov     r9, rsi; unsigned __int16 *
0x18005fa63  lea     r8, aTaskfolderpath; "taskfolderpath"
0x18005fa6a  lea     rdx, [rsp+1B0h+SubKey]; unsigned __int16 *
0x18005fa6f  mov     rcx, r13; HKEY
0x18005fa72  call    ?OmaDmRegistrySetString@@YAJPEAUHKEY__@@PEBG11@Z; OmaDmRegistrySetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18005fa77  mov     ebx, eax
0x18005fa79  test    eax, eax
0x18005fa7b  jns     short loc_18005FA84
0x18005fa7d  mov     edx, 83h
0x18005fa82  jmp     short loc_18005FAF2
0x18005fa84  mov     r9, r14; unsigned __int16 *
0x18005fa87  lea     r8, aTaskname; "taskname"
0x18005fa8e  lea     rdx, [rsp+1B0h+SubKey]; unsigned __int16 *
0x18005fa93  mov     rcx, r13; HKEY
0x18005fa96  call    ?OmaDmRegistrySetString@@YAJPEAUHKEY__@@PEBG11@Z; OmaDmRegistrySetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18005fa9b  mov     ebx, eax
0x18005fa9d  test    eax, eax
0x18005fa9f  jns     short loc_18005FAA8
0x18005faa1  mov     edx, 84h
0x18005faa6  jmp     short loc_18005FAF2
0x18005faa8  mov     r9, r15; unsigned __int16 *
0x18005faab  lea     r8, aTaskstartbound; "taskstartboundary"
0x18005fab2  lea     rdx, [rsp+1B0h+SubKey]; unsigned __int16 *
0x18005fab7  mov     rcx, r13; HKEY
0x18005faba  call    ?OmaDmRegistrySetString@@YAJPEAUHKEY__@@PEBG11@Z; OmaDmRegistrySetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18005fabf  mov     ebx, eax
0x18005fac1  test    eax, eax
0x18005fac3  jns     short loc_18005FACC
0x18005fac5  mov     edx, 85h
0x18005faca  jmp     short loc_18005FAF2
0x18005facc  mov     r9d, [rbp+0B0h+arg_20]; unsigned int
0x18005fad3  lea     r8, aTaskrecurrence; "taskrecurrencefrequency"
0x18005fada  lea     rdx, [rsp+1B0h+SubKey]; unsigned __int16 *
0x18005fadf  mov     rcx, r13; HKEY
0x18005fae2  call    ?OmaDmRegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; OmaDmRegistrySetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18005fae7  mov     ebx, eax
0x18005fae9  test    eax, eax
0x18005faeb  jns     short loc_18005FB17
0x18005faed  mov     edx, 86h; void *
0x18005faf2  mov     rcx, [rbp+0B8h]; this
0x18005faf9  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\dm\\dmcmnutils\\misc"...
0x18005fb00  mov     r9d, eax; char *
0x18005fb03  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005fb08  lea     rcx, [rsp+1B0h+var_160]
0x18005fb0d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005fb12  jmp     loc_18005F9B9
0x18005fb17  lea     rcx, [rsp+1B0h+var_160]
0x18005fb1c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005fb21  xor     eax, eax
0x18005fb23  mov     rcx, [rbp+0B0h+var_40]
0x18005fb27  xor     rcx, rsp; StackCookie
0x18005fb2a  call    __security_check_cookie
0x18005fb2f  add     rsp, 188h
0x18005fb36  pop     r15
0x18005fb38  pop     r14
0x18005fb3a  pop     r13
0x18005fb3c  pop     rsi
0x18005fb3d  pop     rbx
0x18005fb3e  pop     rbp
0x18005fb3f  retn
```
