# Microsoft::Windows::Autopilot::ScopedTsmLogger::LogTsmEventToRegistry(ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x1801a4e64`
- end: `0x1801a51fd`
- name: `?LogTsmEventToRegistry@ScopedTsmLogger@Autopilot@Windows@Microsoft@@AEAAJPEBG000@Z`
- size: `921`
- prototype: `int(Microsoft::Windows::Autopilot::ScopedTsmLogger *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801a4a04`
- `0x1801a4b1c`

## callees

- `0x18000b8f0`
- `0x18000c504`
- `0x180067e54`
- `0x18006841c`
- `0x180084d80`
- `0x180088144`
- `0x18008a454`
- `0x18008aea8`
- `0x1800966b8`
- `0x1800a35f8`
- `0x1801a4e64`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1801a5159`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1801a5159`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801a50ff`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801a50ff`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1801a4eea`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1801a4eea`
- `msvcp_win!_Mtx_unlock` at `0x1801a51c4`
- `msvcp_win!_Mtx_unlock` at `0x1801a51c4`

## string_xrefs

- `0x1801a4eb4`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\scopedtsmlogger.cpp`
- `0x1801a4fad`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\scopedtsmlogger.cpp`
- `0x1801a5045`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\scopedtsmlogger.cpp`
- `0x1801a5094`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\scopedtsmlogger.cpp`
- `0x1801a511b`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\scopedtsmlogger.cpp`
- `0x1801a5190`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\scopedtsmlogger.cpp`

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
    std::_Mutex_base::lock((std::_Mutex_base *)qword_1802B4E00);
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
      _Mtx_unlock((_Mtx_t)qword_1802B4E00);
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
0x1801a4e64  mov     [rsp-8+arg_0], rbx
0x1801a4e69  push    rbp
0x1801a4e6a  push    rsi
0x1801a4e6b  push    rdi
0x1801a4e6c  push    r12
0x1801a4e6e  push    r13
0x1801a4e70  push    r14
0x1801a4e72  push    r15
0x1801a4e74  lea     rbp, [rsp-190h]
0x1801a4e7c  sub     rsp, 290h
0x1801a4e83  mov     rax, cs:__security_cookie
0x1801a4e8a  xor     rax, rsp
0x1801a4e8d  mov     [rbp+1C0h+var_40], rax
0x1801a4e94  mov     rsi, [rbp+1C0h+arg_20]
0x1801a4e9b  xor     r13d, r13d
0x1801a4e9e  mov     r12, r9
0x1801a4ea1  mov     r15, r8
0x1801a4ea4  mov     r14, rdx
0x1801a4ea7  cmp     [rcx+48h], r13b
0x1801a4eab  jnz     short loc_1801A4ED1
0x1801a4ead  mov     rcx, [rbp+1C8h]; this
0x1801a4eb4  lea     r8, aOnecoreuapAdmi_83; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801a4ebb  mov     ebx, 80004001h
0x1801a4ec0  lea     edx, [r13+6Ch]; void *
0x1801a4ec4  mov     r9d, ebx; char *
0x1801a4ec7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a4ecc  jmp     loc_1801A51D0
0x1801a4ed1  lea     rcx, qword_1802B4E00; this
0x1801a4ed8  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1801a4edd  xorps   xmm0, xmm0
0x1801a4ee0  lea     rcx, [rsp+2C0h+SystemTime]; lpSystemTime
0x1801a4ee5  movups  xmmword ptr [rsp+2C0h+SystemTime.wYear], xmm0
0x1801a4eea  call    cs:__imp_GetSystemTime
0x1801a4ef1  nop     dword ptr [rax+rax+00h]
0x1801a4ef6  xor     edx, edx; Val
0x1801a4ef8  lea     rcx, [rsp+2C0h+ValueName]; void *
0x1801a4efd  mov     r8d, 208h; Size
0x1801a4f03  call    memset_0
0x1801a4f08  movzx   ecx, [rsp+2C0h+SystemTime.wSecond]
0x1801a4f0d  movzx   edx, [rsp+2C0h+SystemTime.wMinute]
0x1801a4f12  movzx   r8d, [rsp+2C0h+SystemTime.wHour]
0x1801a4f18  movzx   eax, [rsp+2C0h+SystemTime.wMilliseconds]
0x1801a4f1d  movzx   r10d, [rsp+2C0h+SystemTime.wDay]
0x1801a4f23  movzx   r11d, [rsp+2C0h+SystemTime.wMonth]
0x1801a4f29  movzx   r9d, [rsp+2C0h+SystemTime.wYear]
0x1801a4f2f  mov     [rsp+2C0h+var_278], eax
0x1801a4f33  mov     dword ptr [rsp+2C0h+lpdwDisposition], ecx
0x1801a4f37  lea     rcx, [rsp+2C0h+ValueName]; unsigned __int16 *
0x1801a4f3c  mov     dword ptr [rsp+2C0h+phkResult], edx
0x1801a4f40  mov     edx, 104h; unsigned __int64
0x1801a4f45  mov     dword ptr [rsp+2C0h+lpSecurityAttributes], r8d
0x1801a4f4a  lea     r8, a04d02d02dt02d0; "%04d-%02d-%02dT%02d:%02d:%02d.%03dZ"
0x1801a4f51  mov     [rsp+2C0h+samDesired], r10d
0x1801a4f56  mov     [rsp+2C0h+dwOptions], r11d; int
0x1801a4f5b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801a4f60  mov     ebx, eax
0x1801a4f62  test    eax, eax
0x1801a4f64  jns     short loc_1801A4F70
0x1801a4f66  mov     r9d, eax
0x1801a4f69  mov     edx, 81h
0x1801a4f6e  jmp     short loc_1801A4FA6
0x1801a4f70  test    rsi, rsi
0x1801a4f73  lea     rax, sourceString
0x1801a4f7a  cmovz   rsi, rax
0x1801a4f7e  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801a4f82  mov     rcx, rax
0x1801a4f85  inc     rcx
0x1801a4f88  cmp     [r14+rcx*2], r13w
0x1801a4f8d  jnz     short loc_1801A4F85
0x1801a4f8f  lea     rdx, [rcx+4Dh]
0x1801a4f93  cmp     rdx, 4Dh ; 'M'
0x1801a4f97  jnb     short loc_1801A4FBE
0x1801a4f99  mov     edx, 87h; void *
0x1801a4f9e  mov     ebx, 80070216h
0x1801a4fa3  mov     r9d, ebx; char *
0x1801a4fa6  mov     rcx, [rbp+1C8h]; this
0x1801a4fad  lea     r8, aOnecoreuapAdmi_83; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801a4fb4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a4fb9  jmp     loc_1801A51BD
0x1801a4fbe  mov     rcx, rax
0x1801a4fc1  inc     rcx
0x1801a4fc4  cmp     [r15+rcx*2], r13w
0x1801a4fc9  jnz     short loc_1801A4FC1
0x1801a4fcb  lea     r8, [rdx+rcx]
0x1801a4fcf  cmp     r8, rdx
0x1801a4fd2  jnb     short loc_1801A4FDB
0x1801a4fd4  mov     edx, 88h
0x1801a4fd9  jmp     short loc_1801A4F9E
0x1801a4fdb  mov     rcx, rax
0x1801a4fde  inc     rcx
0x1801a4fe1  cmp     [r12+rcx*2], r13w
0x1801a4fe6  jnz     short loc_1801A4FDE
0x1801a4fe8  lea     rdx, [r8+rcx]
0x1801a4fec  cmp     rdx, r8
0x1801a4fef  jnb     short loc_1801A4FF8
0x1801a4ff1  mov     edx, 89h
0x1801a4ff6  jmp     short loc_1801A4F9E
0x1801a4ff8  inc     rax
0x1801a4ffb  cmp     [rsi+rax*2], r13w
0x1801a5000  jnz     short loc_1801A4FF8
0x1801a5002  lea     rcx, [rdx+rax]
0x1801a5006  cmp     rcx, rdx
0x1801a5009  jnb     short loc_1801A5012
0x1801a500b  mov     edx, 8Ah
0x1801a5010  jmp     short loc_1801A4F9E
0x1801a5012  lea     rdi, [rcx+1]
0x1801a5016  cmp     rdi, rcx
0x1801a5019  jnb     short loc_1801A5025
0x1801a501b  mov     edx, 8Bh
0x1801a5020  jmp     loc_1801A4F9E
0x1801a5025  mov     r8, rdi
0x1801a5028  lea     rcx, [rsp+2C0h+lpData]
0x1801a502d  xor     edx, edx
0x1801a502f  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1801a5034  mov     rbx, [rsp+2C0h+lpData]
0x1801a5039  test    rbx, rbx
0x1801a503c  jnz     short loc_1801A5063
0x1801a503e  mov     rcx, [rbp+1C8h]; this
0x1801a5045  lea     r8, aOnecoreuapAdmi_83; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801a504c  mov     ebx, 8007000Eh
0x1801a5051  mov     edx, 8Eh; void *
0x1801a5056  mov     r9d, ebx; char *
0x1801a5059  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a505e  jmp     loc_1801A51B3
0x1801a5063  mov     [rsp+2C0h+lpSecurityAttributes], rsi
0x1801a5068  lea     r8, aStatetypeSProc; "{\"stateType\":\"%s\", \"processName\":"...
0x1801a506f  mov     qword ptr [rsp+2C0h+samDesired], r12
0x1801a5074  mov     r9, r14
0x1801a5077  mov     rdx, rdi; unsigned __int64
0x1801a507a  mov     qword ptr [rsp+2C0h+dwOptions], r15; int
0x1801a507f  mov     rcx, rbx; unsigned __int16 *
0x1801a5082  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801a5087  mov     esi, eax
0x1801a5089  test    eax, eax
0x1801a508b  jns     short loc_1801A50B9
0x1801a508d  mov     rcx, [rbp+1C8h]; this
0x1801a5094  lea     r8, aOnecoreuapAdmi_83; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801a509b  mov     r9d, eax; char *
0x1801a509e  mov     edx, 97h; void *
0x1801a50a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a50a8  lea     rcx, [rsp+2C0h+lpData]
0x1801a50ad  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801a50b2  mov     ebx, esi
0x1801a50b4  jmp     loc_1801A51BD
0x1801a50b9  xor     edx, edx
0x1801a50bb  mov     [rsp+2C0h+hKey], r13
0x1801a50c0  lea     rcx, [rsp+2C0h+hKey]
0x1801a50c5  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1801a50ca  mov     [rsp+2C0h+lpdwDisposition], r13; lpdwDisposition
0x1801a50cf  lea     rax, [rsp+2C0h+hKey]
0x1801a50d4  mov     [rsp+2C0h+phkResult], rax; phkResult
0x1801a50d9  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Provisioning\\Auto"...
0x1801a50e0  mov     [rsp+2C0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x1801a50e5  xor     r9d, r9d; lpClass
0x1801a50e8  mov     [rsp+2C0h+samDesired], 20006h; samDesired
0x1801a50f0  xor     r8d, r8d; Reserved
0x1801a50f3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1801a50fa  mov     [rsp+2C0h+dwOptions], r13d; int
0x1801a50ff  call    cs:__imp_RegCreateKeyExW
0x1801a5106  nop     dword ptr [rax+rax+00h]
0x1801a510b  test    eax, eax
0x1801a510d  jz      short loc_1801A512E
0x1801a510f  mov     edx, 0A4h; void *
0x1801a5114  mov     rcx, [rbp+1C8h]; this
0x1801a511b  lea     r8, aOnecoreuapAdmi_83; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801a5122  mov     r9d, eax; char *
0x1801a5125  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801a512a  mov     ebx, eax
0x1801a512c  jmp     short loc_1801A51A9
0x1801a512e  mov     eax, edi
0x1801a5130  mov     ecx, 0FFFFFFFFh
0x1801a5135  add     rax, rax
0x1801a5138  cmp     rax, rcx
0x1801a513b  ja      short loc_1801A5189
0x1801a513d  mov     rcx, [rsp+2C0h+hKey]; hKey
0x1801a5142  lea     rdx, [rsp+2C0h+ValueName]; lpValueName
0x1801a5147  mov     [rsp+2C0h+samDesired], eax; cbData
0x1801a514b  mov     r9d, 1; dwType
0x1801a5151  xor     r8d, r8d; Reserved
0x1801a5154  mov     qword ptr [rsp+2C0h+dwOptions], rbx; lpData
0x1801a5159  call    cs:__imp_RegSetValueExW
0x1801a5160  nop     dword ptr [rax+rax+00h]
0x1801a5165  test    eax, eax
0x1801a5167  jz      short loc_1801A5170
0x1801a5169  mov     edx, 0B0h
0x1801a516e  jmp     short loc_1801A5114
0x1801a5170  lea     rcx, [rsp+2C0h+hKey]
0x1801a5175  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801a517a  lea     rcx, [rsp+2C0h+lpData]
0x1801a517f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801a5184  mov     ebx, r13d
0x1801a5187  jmp     short loc_1801A51BD
0x1801a5189  mov     rcx, [rbp+1C8h]; this
0x1801a5190  lea     r8, aOnecoreuapAdmi_83; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801a5197  mov     ebx, 80070216h
0x1801a519c  mov     edx, 0A8h; void *
0x1801a51a1  mov     r9d, ebx; char *
0x1801a51a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a51a9  lea     rcx, [rsp+2C0h+hKey]
0x1801a51ae  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801a51b3  lea     rcx, [rsp+2C0h+lpData]
0x1801a51b8  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801a51bd  lea     rcx, qword_1802B4E00; _Mtx_t
0x1801a51c4  call    cs:__imp__Mtx_unlock
0x1801a51cb  nop     dword ptr [rax+rax+00h]
0x1801a51d0  mov     eax, ebx
0x1801a51d2  mov     rcx, [rbp+1C0h+var_40]
0x1801a51d9  xor     rcx, rsp; StackCookie
0x1801a51dc  call    __security_check_cookie
0x1801a51e1  mov     rbx, [rsp+2C0h+arg_0]
0x1801a51e9  add     rsp, 290h
0x1801a51f0  pop     r15
0x1801a51f2  pop     r14
0x1801a51f4  pop     r13
0x1801a51f6  pop     r12
0x1801a51f8  pop     rdi
0x1801a51f9  pop     rsi
0x1801a51fa  pop     rbp
0x1801a51fb  retn
```
