# ApplicationSpecificEndpointInfo::GetAppKey(ulong,bool,HKEY__ * *)

- ea: `0x18000e37c`
- end: `0x18000e69c`
- name: `?GetAppKey@ApplicationSpecificEndpointInfo@@AEAAJK_NPEAPEAUHKEY__@@@Z`
- size: `800`
- prototype: `__int64 __fastcall(ApplicationSpecificEndpointInfo *this, REGSAM, char, HKEY *)`
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001a134`
- `0x1800463e8`
- `0x1800470a0`

## callees

- `0x18000a384`
- `0x18000e37c`
- `0x18000e6a4`
- `0x180012844`
- `0x1800146b0`
- `0x1800232a0`
- `0x180023e98`
- `0x180025db0`
- `0x1800272f8`
- `0x18002b724`
- `0x180031960`
- `0x1800478e4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000e504`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000e504`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e4c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e532`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e4c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e532`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e474`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e474`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000e617`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000e617`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e419`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e43d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e4d9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e58e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e5e4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e649`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e419`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e43d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e4d9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e58e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e5e4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e649`

## pseudocode

```c
__int64 __fastcall ApplicationSpecificEndpointInfo::GetAppKey(
        ApplicationSpecificEndpointInfo *this,
        REGSAM a2,
        char a3,
        HKEY *a4)
{
  int v7; // r13d
  int v8; // eax
  unsigned int v9; // ebx
  const char *v10; // r9
  __int64 result; // rax
  HKEY v12; // rbx
  LSTATUS Key; // eax
  unsigned int v14; // ebx
  void *v15; // rbx
  char v16; // di
  int v17; // r14d
  HKEY v18; // rcx
  unsigned int v19; // r8d
  int v20; // eax
  unsigned int v21; // ebx
  int v22; // eax
  unsigned int v23; // ebx
  unsigned int v24; // eax
  unsigned int v25; // ebx
  PHKEY phkResult; // [rsp+20h] [rbp-288h]
  int phkResulta; // [rsp+20h] [rbp-288h]
  unsigned int phkResultb; // [rsp+20h] [rbp-288h]
  __int64 cchCount2; // [rsp+28h] [rbp-280h]
  HKEY hKey; // [rsp+30h] [rbp-278h] BYREF
  REGSAM samDesired; // [rsp+38h] [rbp-270h]
  LPVOID pv; // [rsp+40h] [rbp-268h] BYREF
  _BYTE v33[8]; // [rsp+48h] [rbp-260h] BYREF
  WCHAR SubKey[264]; // [rsp+50h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+0h]

  try
  {
    samDesired = a2;
    v16 = 0;
    v17 = 0;
    hKey = 0;
    v7 = ATL::CStringElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::Hash(*((_QWORD *)this + 10));
    while ( 1 )
    {
      LODWORD(cchCount2) = v17;
      LODWORD(phkResult) = v7;
      v8 = StringCbPrintfW(
             SubKey,
             0x20Au,
             L"%s\\%x_%x",
             L"Software\\Microsoft\\Multimedia\\Audio\\DefaultEndpoint",
             phkResult,
             cchCount2);
      v9 = v8;
      if ( v8 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x22A,
          (unsigned int)"avcore\\audiocore\\server\\audiosrv\\applicationspecificendpointinfo\\applicationspecificendpointinfo.cpp",
          (const char *)(unsigned int)v8,
          phkResulta);
        if ( hKey )
          RegCloseKey(hKey);
        return v9;
      }
      v12 = hKey;
      if ( hKey )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)v33);
        RegCloseKey(v12);
        wil::last_error_context::~last_error_context((wil::last_error_context *)v33);
      }
      hKey = 0;
      if ( RegOpenKeyExW(HKEY_CURRENT_USER, SubKey, 0, samDesired, &hKey) )
        break;
      pv = 0;
      Key = ApplicationSpecificEndpointInfo::ReadKey(hKey, 0, (unsigned __int16 **)&pv);
      v14 = Key;
      if ( Key < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x232,
          (unsigned int)"avcore\\audiocore\\server\\audiosrv\\applicationspecificendpointinfo\\applicationspecificendpointinfo.cpp",
          (const char *)(unsigned int)Key,
          (int)phkResult);
        if ( pv )
          CoTaskMemFree(pv);
        if ( hKey )
          RegCloseKey(hKey);
        return v14;
      }
      v15 = pv;
      if ( CompareStringW(0x7Fu, 1u, *((PCNZWCH *)this + 10), -1, (PCNZWCH)pv, -1) == 2 )
      {
        v16 = 0;
      }
      else
      {
        ++v17;
        v16 = 1;
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
          &hKey,
          0);
      }
      if ( v15 )
        CoTaskMemFree(v15);
LABEL_33:
      if ( !v16 )
        goto LABEL_34;
    }
    if ( !a3 )
      goto LABEL_33;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v20 = CreateNewRegistryKey(v18, SubKey, v19, &hKey);
    v21 = v20;
    if ( v20 >= 0 )
    {
      pv = 0;
      v22 = StringCbLengthW(*((const unsigned __int16 **)this + 10), 0x20Au, (unsigned __int64 *)&pv);
      v23 = v22;
      if ( v22 >= 0 )
      {
        v24 = RegSetValueExW(hKey, 0, 0, 1u, *((const BYTE **)this + 10), (_DWORD)pv + 2);
        if ( !v24 )
        {
LABEL_34:
          if ( !hKey )
            return 2147943568LL;
          *a4 = hKey;
          return 0;
        }
        v25 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x256,
                (unsigned int)"avcore\\audiocore\\server\\audiosrv\\applicationspecificendpointinfo\\applicationspecificendpointinfo.cpp",
                (const char *)v24,
                phkResultb);
        if ( hKey )
          RegCloseKey(hKey);
        result = v25;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x248,
          (unsigned int)"avcore\\audiocore\\server\\audiosrv\\applicationspecificendpointinfo\\applicationspecificendpointinfo.cpp",
          (const char *)(unsigned int)v22,
          (int)phkResult);
        if ( hKey )
          RegCloseKey(hKey);
        result = v23;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x244,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\applicationspecificendpointinfo\\applicationspecificendpointinfo.cpp",
        (const char *)(unsigned int)v20,
        (int)phkResult);
      if ( hKey )
        RegCloseKey(hKey);
      result = v21;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x268,
                           (unsigned int)"avcore\\audiocore\\server\\audiosrv\\applicationspecificendpointinfo\\applicati"
                                         "onspecificendpointinfo.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x18000e37c  push    rbx
0x18000e37e  push    rsi
0x18000e37f  push    rdi
0x18000e380  push    r12
0x18000e382  push    r13
0x18000e384  push    r14
0x18000e386  push    r15
0x18000e388  sub     rsp, 270h
0x18000e38f  mov     rax, cs:__security_cookie
0x18000e396  xor     rax, rsp
0x18000e399  mov     [rsp+2A8h+var_48], rax
0x18000e3a1  mov     r15, r9
0x18000e3a4  mov     r12b, r8b
0x18000e3a7  mov     [rsp+2A8h+samDesired], edx
0x18000e3ab  mov     rsi, rcx
0x18000e3ae  xor     dil, dil
0x18000e3b1  xor     r14d, r14d
0x18000e3b4  mov     [rsp+2A8h+hKey], r14
0x18000e3b9  mov     rcx, [rcx+50h]
0x18000e3bd  call    ?Hash@?$CStringElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@SAKPEBG@Z; ATL::CStringElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::Hash(ushort const *)
0x18000e3c2  mov     r13d, eax
0x18000e3c5  mov     dword ptr [rsp+2A8h+cchCount2], r14d
0x18000e3ca  mov     dword ptr [rsp+2A8h+phkResult], r13d; int
0x18000e3cf  lea     r9, aSoftwareMicros; "Software\\Microsoft\\Multimedia\\Audio"...
0x18000e3d6  lea     r8, aSXX; "%s\\%x_%x"
0x18000e3dd  mov     edx, 20Ah; unsigned __int64
0x18000e3e2  lea     rcx, [rsp+2A8h+SubKey]; unsigned __int16 *
0x18000e3e7  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000e3ec  mov     ebx, eax
0x18000e3ee  test    eax, eax
0x18000e3f0  jns     short loc_18000E426
0x18000e3f2  mov     rcx, [rsp+2A8h]; this
0x18000e3fa  mov     r9d, eax; char *
0x18000e3fd  lea     r8, aAvcoreAudiocor_2; "avcore\\audiocore\\server\\audiosrv\\ap"...
0x18000e404  mov     edx, 22Ah; void *
0x18000e409  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e40e  nop
0x18000e40f  mov     rcx, [rsp+2A8h+hKey]; hKey
0x18000e414  test    rcx, rcx
0x18000e417  jz      short loc_18000E41F
0x18000e419  call    cs:__imp_RegCloseKey
0x18000e41f  mov     eax, ebx
0x18000e421  jmp     loc_18000E678
0x18000e426  mov     rbx, [rsp+2A8h+hKey]
0x18000e42b  test    rbx, rbx
0x18000e42e  jz      short loc_18000E44D
0x18000e430  lea     rcx, [rsp+2A8h+var_260]; this
0x18000e435  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000e43a  mov     rcx, rbx; hKey
0x18000e43d  call    cs:__imp_RegCloseKey
0x18000e443  lea     rcx, [rsp+2A8h+var_260]; this
0x18000e448  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000e44d  mov     [rsp+2A8h+hKey], 0
0x18000e456  lea     rax, [rsp+2A8h+hKey]
0x18000e45b  mov     [rsp+2A8h+phkResult], rax; int
0x18000e460  mov     r9d, [rsp+2A8h+samDesired]; samDesired
0x18000e465  xor     r8d, r8d; ulOptions
0x18000e468  lea     rdx, [rsp+2A8h+SubKey]; lpSubKey
0x18000e46d  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18000e474  call    cs:__imp_RegOpenKeyExW
0x18000e47a  test    eax, eax
0x18000e47c  jnz     loc_18000E53D
0x18000e482  mov     [rsp+2A8h+pv], 0
0x18000e48b  lea     r8, [rsp+2A8h+pv]; unsigned __int16 **
0x18000e490  xor     edx, edx; lpValue
0x18000e492  mov     rcx, [rsp+2A8h+hKey]; hkey
0x18000e497  call    ?ReadKey@ApplicationSpecificEndpointInfo@@CAJPEAUHKEY__@@PEBGPEAPEAG@Z; ApplicationSpecificEndpointInfo::ReadKey(HKEY__ *,ushort const *,ushort * *)
0x18000e49c  mov     ebx, eax
0x18000e49e  test    eax, eax
0x18000e4a0  jns     short loc_18000E4E6
0x18000e4a2  mov     rcx, [rsp+2A8h]; this
0x18000e4aa  mov     r9d, eax; char *
0x18000e4ad  lea     r8, aAvcoreAudiocor_2; "avcore\\audiocore\\server\\audiosrv\\ap"...
0x18000e4b4  mov     edx, 232h; void *
0x18000e4b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e4be  mov     rcx, [rsp+2A8h+pv]; pv
0x18000e4c3  test    rcx, rcx
0x18000e4c6  jz      short loc_18000E4CF
0x18000e4c8  call    cs:__imp_CoTaskMemFree
0x18000e4ce  nop
0x18000e4cf  mov     rcx, [rsp+2A8h+hKey]; hKey
0x18000e4d4  test    rcx, rcx
0x18000e4d7  jz      short loc_18000E4DF
0x18000e4d9  call    cs:__imp_RegCloseKey
0x18000e4df  mov     eax, ebx
0x18000e4e1  jmp     loc_18000E678
0x18000e4e6  or      eax, 0FFFFFFFFh
0x18000e4e9  mov     dword ptr [rsp+2A8h+cchCount2], eax; cchCount2
0x18000e4ed  mov     rbx, [rsp+2A8h+pv]
0x18000e4f2  mov     [rsp+2A8h+phkResult], rbx; lpString2
0x18000e4f7  mov     r9d, eax; cchCount1
0x18000e4fa  mov     r8, [rsi+50h]; lpString1
0x18000e4fe  lea     edx, [rax+2]; dwCmpFlags
0x18000e501  lea     ecx, [rdx+7Eh]; Locale
0x18000e504  call    cs:__imp_CompareStringW
0x18000e50a  cmp     eax, 2
0x18000e50d  jnz     short loc_18000E514
0x18000e50f  xor     dil, dil
0x18000e512  jmp     short loc_18000E526
0x18000e514  inc     r14d
0x18000e517  mov     dil, 1
0x18000e51a  xor     edx, edx
0x18000e51c  lea     rcx, [rsp+2A8h+hKey]
0x18000e521  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18000e526  test    rbx, rbx
0x18000e529  jz      loc_18000E653
0x18000e52f  mov     rcx, rbx; pv
0x18000e532  call    cs:__imp_CoTaskMemFree
0x18000e538  jmp     loc_18000E653
0x18000e53d  test    r12b, r12b
0x18000e540  jz      loc_18000E653
0x18000e546  xor     edx, edx
0x18000e548  lea     rcx, [rsp+2A8h+hKey]
0x18000e54d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18000e552  lea     r9, [rsp+2A8h+hKey]; HKEY *
0x18000e557  lea     rdx, [rsp+2A8h+SubKey]; unsigned __int16 *
0x18000e55c  call    ?CreateNewRegistryKey@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z; CreateNewRegistryKey(HKEY__ *,ushort const *,ulong,HKEY__ * *)
0x18000e561  mov     ebx, eax
0x18000e563  test    eax, eax
0x18000e565  jns     short loc_18000E59B
0x18000e567  mov     rcx, [rsp+2A8h]; this
0x18000e56f  mov     r9d, eax; char *
0x18000e572  lea     r8, aAvcoreAudiocor_2; "avcore\\audiocore\\server\\audiosrv\\ap"...
0x18000e579  mov     edx, 244h; void *
0x18000e57e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e583  nop
0x18000e584  mov     rcx, [rsp+2A8h+hKey]; hKey
0x18000e589  test    rcx, rcx
0x18000e58c  jz      short loc_18000E594
0x18000e58e  call    cs:__imp_RegCloseKey
0x18000e594  mov     eax, ebx
0x18000e596  jmp     loc_18000E678
0x18000e59b  mov     [rsp+2A8h+pv], 0
0x18000e5a4  lea     r8, [rsp+2A8h+pv]; unsigned __int64 *
0x18000e5a9  mov     edx, 20Ah; unsigned __int64
0x18000e5ae  mov     rcx, [rsi+50h]; unsigned __int16 *
0x18000e5b2  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000e5b7  mov     ebx, eax
0x18000e5b9  test    eax, eax
0x18000e5bb  jns     short loc_18000E5F1
0x18000e5bd  mov     rcx, [rsp+2A8h]; this
0x18000e5c5  mov     r9d, eax; char *
0x18000e5c8  lea     r8, aAvcoreAudiocor_2; "avcore\\audiocore\\server\\audiosrv\\ap"...
0x18000e5cf  mov     edx, 248h; void *
0x18000e5d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e5d9  nop
0x18000e5da  mov     rcx, [rsp+2A8h+hKey]; hKey
0x18000e5df  test    rcx, rcx
0x18000e5e2  jz      short loc_18000E5EA
0x18000e5e4  call    cs:__imp_RegCloseKey
0x18000e5ea  mov     eax, ebx
0x18000e5ec  jmp     loc_18000E678
0x18000e5f1  mov     rax, [rsp+2A8h+pv]
0x18000e5f6  add     rax, 2
0x18000e5fa  mov     dword ptr [rsp+2A8h+cchCount2], eax; cbData
0x18000e5fe  mov     rax, [rsi+50h]
0x18000e602  mov     [rsp+2A8h+phkResult], rax; unsigned int
0x18000e607  mov     r9d, 1; dwType
0x18000e60d  xor     r8d, r8d; Reserved
0x18000e610  xor     edx, edx; lpValueName
0x18000e612  mov     rcx, [rsp+2A8h+hKey]; hKey
0x18000e617  call    cs:__imp_RegSetValueExW
0x18000e61d  test    eax, eax
0x18000e61f  jz      short loc_18000E65C
0x18000e621  mov     rcx, [rsp+2A8h]; this
0x18000e629  mov     r9d, eax; char *
0x18000e62c  lea     r8, aAvcoreAudiocor_2; "avcore\\audiocore\\server\\audiosrv\\ap"...
0x18000e633  mov     edx, 256h; void *
0x18000e638  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000e63d  mov     ebx, eax
0x18000e63f  mov     rcx, [rsp+2A8h+hKey]; hKey
0x18000e644  test    rcx, rcx
0x18000e647  jz      short loc_18000E64F
0x18000e649  call    cs:__imp_RegCloseKey
0x18000e64f  mov     eax, ebx
0x18000e651  jmp     short loc_18000E678
0x18000e653  test    dil, dil
0x18000e656  jnz     loc_18000E3C5
0x18000e65c  mov     rax, [rsp+2A8h+hKey]
0x18000e661  test    rax, rax
0x18000e664  jz      short loc_18000E66D
0x18000e666  mov     [r15], rax
0x18000e669  xor     eax, eax
0x18000e66b  jmp     short loc_18000E678
0x18000e66d  mov     eax, 80070490h
0x18000e672  jmp     short loc_18000E678
0x18000e674  mov     eax, [rsp+2A8h+samDesired]
0x18000e678  mov     rcx, [rsp+2A8h+var_48]
0x18000e680  xor     rcx, rsp; StackCookie
0x18000e683  call    __security_check_cookie
0x18000e688  add     rsp, 270h
0x18000e68f  pop     r15
0x18000e691  pop     r14
0x18000e693  pop     r13
0x18000e695  pop     r12
0x18000e697  pop     rdi
0x18000e698  pop     rsi
0x18000e699  pop     rbx
0x18000e69a  retn
```
