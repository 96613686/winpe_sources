# Microsoft::Windows::Autopilot::ScopedTsmLogger::LogTsmEventToRegistry(ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x18019f9f8`
- end: `0x18019fd78`
- name: `?LogTsmEventToRegistry@ScopedTsmLogger@Autopilot@Windows@Microsoft@@AEAAJPEBG000@Z`
- size: `896`
- prototype: `int(Microsoft::Windows::Autopilot::ScopedTsmLogger *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18019f59c`
- `0x18019f6b4`

## callees

- `0x18000b820`
- `0x18000c414`
- `0x180067a54`
- `0x180067ffc`
- `0x180084208`
- `0x1800873a4`
- `0x180089614`
- `0x180089ff4`
- `0x1800953b4`
- `0x1800a1fe4`
- `0x18019f9f8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18019fce1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18019fce1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18019fc8d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18019fc8d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18019fa7e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18019fa7e`
- `msvcp_win!_Mtx_unlock` at `0x18019fd46`
- `msvcp_win!_Mtx_unlock` at `0x18019fd46`

## string_xrefs

- `0x18019fa48`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\scopedtsmlogger.cpp`
- `0x18019fb3b`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\scopedtsmlogger.cpp`
- `0x18019fbd3`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\scopedtsmlogger.cpp`
- `0x18019fc22`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\scopedtsmlogger.cpp`
- `0x18019fca3`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\scopedtsmlogger.cpp`
- `0x18019fd12`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\scopedtsmlogger.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::ScopedTsmLogger::LogTsmEventToRegistry(
        Microsoft::Windows::Autopilot::ScopedTsmLogger *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5)
{
  const WCHAR *v5; // rsi
  unsigned int v9; // ebx
  int v10; // eax
  __int64 v11; // r9
  __int64 v12; // rdx
  __int64 v13; // rax
  unsigned __int64 v14; // rcx
  unsigned __int64 v15; // rdx
  __int64 v16; // rcx
  unsigned __int64 v17; // r8
  __int64 v18; // rcx
  unsigned __int64 v19; // rdx
  unsigned __int64 v20; // rcx
  unsigned __int64 v21; // rdi
  BYTE *v22; // rbx
  int v23; // eax
  unsigned int v24; // esi
  unsigned int v25; // eax
  __int64 v26; // rdx
  int dwOptions; // [rsp+20h] [rbp-E0h]
  int dwOptionsa; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  BYTE *lpData; // [rsp+58h] [rbp-A8h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR ValueName[264]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  v5 = a5;
  if ( *((_BYTE *)this + 72) )
  {
    std::_Mutex_base::lock((std::_Mutex_base *)qword_1802AFCC0);
    SystemTime = 0;
    GetSystemTime(&SystemTime);
    memset_0(ValueName, 0, 0x208u);
    dwOptionsa = SystemTime.wMonth;
    v10 = StringCchPrintfW(ValueName, 0x104u, L"%04d-%02d-%02dT%02d:%02d:%02d.%03dZ", SystemTime.wYear);
    v9 = v10;
    if ( v10 < 0 )
    {
      v11 = (unsigned int)v10;
      v12 = 129;
LABEL_12:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\scopedtsmlogger.cpp",
        (const char *)v11,
        dwOptionsa);
LABEL_40:
      _Mtx_unlock((_Mtx_t)qword_1802AFCC0);
      return v9;
    }
    if ( !a5 )
      v5 = &sourceString;
    v13 = -1;
    v14 = -1;
    do
      ++v14;
    while ( a2[v14] );
    v15 = v14 + 77;
    if ( v14 >= 0xFFFFFFFFFFFFFFB3uLL )
    {
      v12 = 135;
LABEL_11:
      v9 = -2147024362;
      v11 = 2147942934LL;
      goto LABEL_12;
    }
    v16 = -1;
    do
      ++v16;
    while ( a3[v16] );
    v17 = v15 + v16;
    if ( v15 + v16 < v15 )
    {
      v12 = 136;
      goto LABEL_11;
    }
    v18 = -1;
    do
      ++v18;
    while ( a4[v18] );
    v19 = v17 + v18;
    if ( v17 + v18 < v17 )
    {
      v12 = 137;
      goto LABEL_11;
    }
    do
      ++v13;
    while ( v5[v13] );
    v20 = v19 + v13;
    if ( v19 + v13 < v19 )
    {
      v12 = 138;
      goto LABEL_11;
    }
    v21 = v20 + 1;
    if ( v20 + 1 < v20 )
    {
      v12 = 139;
      goto LABEL_11;
    }
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &lpData,
      0,
      v20 + 1);
    v22 = lpData;
    if ( !lpData )
    {
      v9 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8E,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\scopedtsmlogger.cpp",
        (const char *)0x8007000ELL,
        dwOptionsa);
LABEL_39:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpData);
      goto LABEL_40;
    }
    v23 = StringCchPrintfW(
            (unsigned __int16 *)lpData,
            v21,
            L"{\"stateType\":\"%s\", \"processName\":\"%s\", \"stateName\":\"%s\", \"eventMessage\":\"%s\"}",
            a2);
    v24 = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x97,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\scopedtsmlogger.cpp",
        (const char *)(unsigned int)v23,
        (int)a3);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpData);
      v9 = v24;
      goto LABEL_40;
    }
    hKey = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v25 = RegCreateKeyExW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\Provisioning\\AutopilotSettings\\TSM",
            0,
            0,
            0,
            0x20006u,
            0,
            &hKey,
            0);
    if ( v25 )
    {
      v26 = 164;
    }
    else
    {
      if ( 2 * (unsigned __int64)(unsigned int)v21 > 0xFFFFFFFF )
      {
        v9 = -2147024362;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA8,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\scopedtsmlogger.cpp",
          (const char *)0x80070216LL,
          dwOptionsb);
        goto LABEL_38;
      }
      v25 = RegSetValueExW(hKey, ValueName, 0, 1u, v22, 2 * v21);
      if ( !v25 )
      {
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpData);
        v9 = 0;
        goto LABEL_40;
      }
      v26 = 176;
    }
    v9 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v26,
           (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\scopedtsmlogger.cpp",
           (const char *)v25,
           dwOptionsb);
LABEL_38:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    goto LABEL_39;
  }
  v9 = -2147467263;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x6C,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\scopedtsmlogger.cpp",
    (const char *)0x80004001LL,
    dwOptions);
  return v9;
}

```

## disassembly

```asm
0x18019f9f8  mov     [rsp-8+arg_0], rbx
0x18019f9fd  push    rbp
0x18019f9fe  push    rsi
0x18019f9ff  push    rdi
0x18019fa00  push    r12
0x18019fa02  push    r13
0x18019fa04  push    r14
0x18019fa06  push    r15
0x18019fa08  lea     rbp, [rsp-190h]
0x18019fa10  sub     rsp, 290h
0x18019fa17  mov     rax, cs:__security_cookie
0x18019fa1e  xor     rax, rsp
0x18019fa21  mov     [rbp+1C0h+var_40], rax
0x18019fa28  mov     rsi, [rbp+1C0h+arg_20]
0x18019fa2f  xor     r13d, r13d
0x18019fa32  mov     r12, r9
0x18019fa35  mov     r15, r8
0x18019fa38  mov     r14, rdx
0x18019fa3b  cmp     [rcx+48h], r13b
0x18019fa3f  jnz     short loc_18019FA65
0x18019fa41  mov     rcx, [rbp+1C8h]; this
0x18019fa48  lea     r8, aOnecoreuapAdmi_83; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019fa4f  mov     ebx, 80004001h
0x18019fa54  lea     edx, [r13+6Ch]; void *
0x18019fa58  mov     r9d, ebx; char *
0x18019fa5b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019fa60  jmp     loc_18019FD4C
0x18019fa65  lea     rcx, qword_1802AFCC0; this
0x18019fa6c  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18019fa71  xorps   xmm0, xmm0
0x18019fa74  lea     rcx, [rsp+2C0h+SystemTime]; lpSystemTime
0x18019fa79  movups  xmmword ptr [rsp+2C0h+SystemTime.wYear], xmm0
0x18019fa7e  call    cs:__imp_GetSystemTime
0x18019fa84  xor     edx, edx; Val
0x18019fa86  lea     rcx, [rsp+2C0h+ValueName]; void *
0x18019fa8b  mov     r8d, 208h; Size
0x18019fa91  call    memset_0
0x18019fa96  movzx   ecx, [rsp+2C0h+SystemTime.wSecond]
0x18019fa9b  movzx   edx, [rsp+2C0h+SystemTime.wMinute]
0x18019faa0  movzx   r8d, [rsp+2C0h+SystemTime.wHour]
0x18019faa6  movzx   eax, [rsp+2C0h+SystemTime.wMilliseconds]
0x18019faab  movzx   r10d, [rsp+2C0h+SystemTime.wDay]
0x18019fab1  movzx   r11d, [rsp+2C0h+SystemTime.wMonth]
0x18019fab7  movzx   r9d, [rsp+2C0h+SystemTime.wYear]
0x18019fabd  mov     [rsp+2C0h+var_278], eax
0x18019fac1  mov     dword ptr [rsp+2C0h+lpdwDisposition], ecx
0x18019fac5  lea     rcx, [rsp+2C0h+ValueName]; unsigned __int16 *
0x18019faca  mov     dword ptr [rsp+2C0h+phkResult], edx
0x18019face  mov     edx, 104h; unsigned __int64
0x18019fad3  mov     dword ptr [rsp+2C0h+lpSecurityAttributes], r8d
0x18019fad8  lea     r8, a04d02d02dt02d0; "%04d-%02d-%02dT%02d:%02d:%02d.%03dZ"
0x18019fadf  mov     [rsp+2C0h+samDesired], r10d
0x18019fae4  mov     [rsp+2C0h+dwOptions], r11d; int
0x18019fae9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18019faee  mov     ebx, eax
0x18019faf0  test    eax, eax
0x18019faf2  jns     short loc_18019FAFE
0x18019faf4  mov     r9d, eax
0x18019faf7  mov     edx, 81h
0x18019fafc  jmp     short loc_18019FB34
0x18019fafe  test    rsi, rsi
0x18019fb01  lea     rax, sourceString
0x18019fb08  cmovz   rsi, rax
0x18019fb0c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18019fb10  mov     rcx, rax
0x18019fb13  inc     rcx
0x18019fb16  cmp     [r14+rcx*2], r13w
0x18019fb1b  jnz     short loc_18019FB13
0x18019fb1d  lea     rdx, [rcx+4Dh]
0x18019fb21  cmp     rdx, 4Dh ; 'M'
0x18019fb25  jnb     short loc_18019FB4C
0x18019fb27  mov     edx, 87h; void *
0x18019fb2c  mov     ebx, 80070216h
0x18019fb31  mov     r9d, ebx; char *
0x18019fb34  mov     rcx, [rbp+1C8h]; this
0x18019fb3b  lea     r8, aOnecoreuapAdmi_83; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019fb42  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019fb47  jmp     loc_18019FD3F
0x18019fb4c  mov     rcx, rax
0x18019fb4f  inc     rcx
0x18019fb52  cmp     [r15+rcx*2], r13w
0x18019fb57  jnz     short loc_18019FB4F
0x18019fb59  lea     r8, [rdx+rcx]
0x18019fb5d  cmp     r8, rdx
0x18019fb60  jnb     short loc_18019FB69
0x18019fb62  mov     edx, 88h
0x18019fb67  jmp     short loc_18019FB2C
0x18019fb69  mov     rcx, rax
0x18019fb6c  inc     rcx
0x18019fb6f  cmp     [r12+rcx*2], r13w
0x18019fb74  jnz     short loc_18019FB6C
0x18019fb76  lea     rdx, [r8+rcx]
0x18019fb7a  cmp     rdx, r8
0x18019fb7d  jnb     short loc_18019FB86
0x18019fb7f  mov     edx, 89h
0x18019fb84  jmp     short loc_18019FB2C
0x18019fb86  inc     rax
0x18019fb89  cmp     [rsi+rax*2], r13w
0x18019fb8e  jnz     short loc_18019FB86
0x18019fb90  lea     rcx, [rdx+rax]
0x18019fb94  cmp     rcx, rdx
0x18019fb97  jnb     short loc_18019FBA0
0x18019fb99  mov     edx, 8Ah
0x18019fb9e  jmp     short loc_18019FB2C
0x18019fba0  lea     rdi, [rcx+1]
0x18019fba4  cmp     rdi, rcx
0x18019fba7  jnb     short loc_18019FBB3
0x18019fba9  mov     edx, 8Bh
0x18019fbae  jmp     loc_18019FB2C
0x18019fbb3  mov     r8, rdi
0x18019fbb6  lea     rcx, [rsp+2C0h+lpData]
0x18019fbbb  xor     edx, edx
0x18019fbbd  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18019fbc2  mov     rbx, [rsp+2C0h+lpData]
0x18019fbc7  test    rbx, rbx
0x18019fbca  jnz     short loc_18019FBF1
0x18019fbcc  mov     rcx, [rbp+1C8h]; this
0x18019fbd3  lea     r8, aOnecoreuapAdmi_83; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019fbda  mov     ebx, 8007000Eh
0x18019fbdf  mov     edx, 8Eh; void *
0x18019fbe4  mov     r9d, ebx; char *
0x18019fbe7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019fbec  jmp     loc_18019FD35
0x18019fbf1  mov     [rsp+2C0h+lpSecurityAttributes], rsi
0x18019fbf6  lea     r8, aStatetypeSProc; "{\"stateType\":\"%s\", \"processName\":"...
0x18019fbfd  mov     qword ptr [rsp+2C0h+samDesired], r12
0x18019fc02  mov     r9, r14
0x18019fc05  mov     rdx, rdi; unsigned __int64
0x18019fc08  mov     qword ptr [rsp+2C0h+dwOptions], r15; int
0x18019fc0d  mov     rcx, rbx; unsigned __int16 *
0x18019fc10  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18019fc15  mov     esi, eax
0x18019fc17  test    eax, eax
0x18019fc19  jns     short loc_18019FC47
0x18019fc1b  mov     rcx, [rbp+1C8h]; this
0x18019fc22  lea     r8, aOnecoreuapAdmi_83; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019fc29  mov     r9d, eax; char *
0x18019fc2c  mov     edx, 97h; void *
0x18019fc31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019fc36  lea     rcx, [rsp+2C0h+lpData]
0x18019fc3b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18019fc40  mov     ebx, esi
0x18019fc42  jmp     loc_18019FD3F
0x18019fc47  xor     edx, edx
0x18019fc49  mov     [rsp+2C0h+hKey], r13
0x18019fc4e  lea     rcx, [rsp+2C0h+hKey]
0x18019fc53  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18019fc58  mov     [rsp+2C0h+lpdwDisposition], r13; lpdwDisposition
0x18019fc5d  lea     rax, [rsp+2C0h+hKey]
0x18019fc62  mov     [rsp+2C0h+phkResult], rax; phkResult
0x18019fc67  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Provisioning\\Auto"...
0x18019fc6e  mov     [rsp+2C0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x18019fc73  xor     r9d, r9d; lpClass
0x18019fc76  mov     [rsp+2C0h+samDesired], 20006h; samDesired
0x18019fc7e  xor     r8d, r8d; Reserved
0x18019fc81  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18019fc88  mov     [rsp+2C0h+dwOptions], r13d; int
0x18019fc8d  call    cs:__imp_RegCreateKeyExW
0x18019fc93  test    eax, eax
0x18019fc95  jz      short loc_18019FCB6
0x18019fc97  mov     edx, 0A4h; void *
0x18019fc9c  mov     rcx, [rbp+1C8h]; this
0x18019fca3  lea     r8, aOnecoreuapAdmi_83; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019fcaa  mov     r9d, eax; char *
0x18019fcad  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18019fcb2  mov     ebx, eax
0x18019fcb4  jmp     short loc_18019FD2B
0x18019fcb6  mov     eax, edi
0x18019fcb8  mov     ecx, 0FFFFFFFFh
0x18019fcbd  add     rax, rax
0x18019fcc0  cmp     rax, rcx
0x18019fcc3  ja      short loc_18019FD0B
0x18019fcc5  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18019fcca  lea     rdx, [rsp+2C0h+ValueName]; lpValueName
0x18019fccf  mov     [rsp+2C0h+samDesired], eax; cbData
0x18019fcd3  mov     r9d, 1; dwType
0x18019fcd9  xor     r8d, r8d; Reserved
0x18019fcdc  mov     qword ptr [rsp+2C0h+dwOptions], rbx; lpData
0x18019fce1  call    cs:__imp_RegSetValueExW
0x18019fce7  test    eax, eax
0x18019fce9  jz      short loc_18019FCF2
0x18019fceb  mov     edx, 0B0h
0x18019fcf0  jmp     short loc_18019FC9C
0x18019fcf2  lea     rcx, [rsp+2C0h+hKey]
0x18019fcf7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18019fcfc  lea     rcx, [rsp+2C0h+lpData]
0x18019fd01  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18019fd06  mov     ebx, r13d
0x18019fd09  jmp     short loc_18019FD3F
0x18019fd0b  mov     rcx, [rbp+1C8h]; this
0x18019fd12  lea     r8, aOnecoreuapAdmi_83; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019fd19  mov     ebx, 80070216h
0x18019fd1e  mov     edx, 0A8h; void *
0x18019fd23  mov     r9d, ebx; char *
0x18019fd26  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019fd2b  lea     rcx, [rsp+2C0h+hKey]
0x18019fd30  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18019fd35  lea     rcx, [rsp+2C0h+lpData]
0x18019fd3a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18019fd3f  lea     rcx, qword_1802AFCC0; _Mtx_t
0x18019fd46  call    cs:__imp__Mtx_unlock
0x18019fd4c  mov     eax, ebx
0x18019fd4e  mov     rcx, [rbp+1C0h+var_40]
0x18019fd55  xor     rcx, rsp; StackCookie
0x18019fd58  call    __security_check_cookie
0x18019fd5d  mov     rbx, [rsp+2C0h+arg_0]
0x18019fd65  add     rsp, 290h
0x18019fd6c  pop     r15
0x18019fd6e  pop     r14
0x18019fd70  pop     r13
0x18019fd72  pop     r12
0x18019fd74  pop     rdi
0x18019fd75  pop     rsi
0x18019fd76  pop     rbp
0x18019fd77  retn
```
