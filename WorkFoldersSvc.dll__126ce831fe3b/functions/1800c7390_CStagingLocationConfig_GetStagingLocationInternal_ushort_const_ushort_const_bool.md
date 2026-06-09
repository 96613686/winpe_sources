# CStagingLocationConfig::GetStagingLocationInternal(ushort const *,ushort const *,bool)

- ea: `0x1800c7390`
- end: `0x1800c7913`
- name: `?GetStagingLocationInternal@CStagingLocationConfig@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0_N@Z`
- size: `1411`
- prototype: `__int64 __fastcall(__int64, __int64, const WCHAR *, char)`
- caller_count: `2`
- callee_count: `27`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800c71d8`
- `0x1800c72b4`

## callees

- `0x180002ab0`
- `0x1800035f8`
- `0x180003604`
- `0x180007b9c`
- `0x180007e10`
- `0x180009384`
- `0x180010ee0`
- `0x1800110fc`
- `0x180011314`
- `0x18001137c`
- `0x180015150`
- `0x1800155b8`
- `0x180023c90`
- `0x18002dad0`
- `0x180035564`
- `0x180060368`
- `0x180060850`
- `0x180060bc4`
- `0x180060fc8`
- `0x180061054`
- `0x180061b18`
- `0x180061cb0`
- `0x180062140`
- `0x18006269c`
- `0x180062ffc`
- `0x1800b2698`
- `0x1800c7390`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800c755d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800c755d`
- `KERNEL32!SetFileAttributesW` at `0x1800c776c`
- `KERNEL32!SetFileAttributesW` at `0x1800c776c`
- `KERNEL32!RemoveDirectoryW` at `0x1800c7824`
- `KERNEL32!RemoveDirectoryW` at `0x1800c7824`
- `KERNEL32!GetFileAttributesW` at `0x1800c766a`
- `KERNEL32!GetFileAttributesW` at `0x1800c769f`
- `KERNEL32!GetFileAttributesW` at `0x1800c766a`
- `KERNEL32!GetFileAttributesW` at `0x1800c769f`
- `KERNEL32!GetLastError` at `0x1800c77ce`
- `KERNEL32!GetLastError` at `0x1800c77ce`
- `ADVAPI32!SetFileSecurityW` at `0x1800c77c0`
- `ADVAPI32!SetFileSecurityW` at `0x1800c77c0`
- `USERENV!ExpandEnvironmentStringsForUserW` at `0x1800c74dc`
- `USERENV!ExpandEnvironmentStringsForUserW` at `0x1800c74dc`

## string_xrefs

- `0x1800c7434`: `CStagingLocationConfig::GetStagingLocationInternal`

## pseudocode

```c
// Hidden C++ exception states: #wind=34
__int64 __fastcall CStagingLocationConfig::GetStagingLocationInternal(__int64 a1, __int64 a2, const WCHAR *a3, char a4)
{
  _BYTE *v8; // rax
  char v9; // cl
  bool v10; // dl
  bool v11; // r8
  HANDLE v12; // rbx
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // r8
  __int64 v16; // rax
  char v17; // r14
  __int64 v18; // rdi
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  const WCHAR *v23; // rax
  const unsigned __int16 *v24; // rax
  const WCHAR *v25; // rax
  const WCHAR *v26; // rax
  struct _SECURITY_ATTRIBUTES *v27; // rdx
  const WCHAR *v28; // rax
  int v29; // edx
  int v30; // r8d
  int v31; // r9d
  __int64 SecurityDescriptor; // rax
  const WCHAR *v33; // rax
  signed int LastError; // ebx
  int v35; // eax
  __int64 v36; // r10
  const WCHAR *v37; // rax
  __int64 v38; // rax
  __int64 v39; // r10
  void *pExceptionObject; // [rsp+50h] [rbp-B0h] BYREF
  int v42; // [rsp+58h] [rbp-A8h]
  int LastFailureAsHRESULT; // [rsp+60h] [rbp-A0h] BYREF
  int v44; // [rsp+64h] [rbp-9Ch]
  char v45; // [rsp+68h] [rbp-98h]
  const char *v46; // [rsp+70h] [rbp-90h]
  __int64 v47; // [rsp+78h] [rbp-88h]
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+80h] [rbp-80h] BYREF
  HANDLE hToken; // [rsp+88h] [rbp-78h] BYREF
  int v50; // [rsp+90h] [rbp-70h] BYREF
  __int64 v51; // [rsp+98h] [rbp-68h]
  int v52; // [rsp+A0h] [rbp-60h]
  int v53; // [rsp+A4h] [rbp-5Ch]
  int v54; // [rsp+A8h] [rbp-58h]
  __int64 v55; // [rsp+B0h] [rbp-50h]
  int v56; // [rsp+B8h] [rbp-48h]
  __int64 v57; // [rsp+BCh] [rbp-44h]
  _BYTE *v58; // [rsp+C8h] [rbp-38h]
  int v59; // [rsp+D0h] [rbp-30h]
  int v60; // [rsp+D4h] [rbp-2Ch]
  __int64 v61; // [rsp+E0h] [rbp-20h]
  _BYTE v62[32]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v63[32]; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v64[32]; // [rsp+128h] [rbp+28h] BYREF
  _BYTE v65[32]; // [rsp+148h] [rbp+48h] BYREF
  _BYTE v66[32]; // [rsp+168h] [rbp+68h] BYREF
  _BYTE v67[40]; // [rsp+188h] [rbp+88h] BYREF
  _BYTE v68[80]; // [rsp+1B0h] [rbp+B0h] BYREF
  WCHAR Dest; // [rsp+200h] [rbp+100h] BYREF
  _BYTE v70[526]; // [rsp+202h] [rbp+102h] BYREF

  v61 = a1;
  v42 = 0;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) == 0 )
      goto LABEL_8;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 12, WPP_7c4ceb82cd073befcc4075c3bed8e1cf_Traceguids);
      v8 = WPP_GLOBAL_Control;
    }
  }
  if ( (v8[68] & 8) != 0 && v8[65] >= 6u )
  {
    v9 = 1;
    goto LABEL_9;
  }
LABEL_8:
  v9 = 0;
LABEL_9:
  LastFailureAsHRESULT = 0;
  v44 = 48;
  v45 = v9;
  v46 = "CStagingLocationConfig::GetStagingLocationInternal";
  v47 = 0;
  std::wstring::wstring(v63);
  std::wstring::wstring(v65);
  std::wstring::wstring(v64);
  std::wstring::wstring(a1);
  v42 = 1;
  hToken = 0;
  Dest = 0;
  memset_0(v70, 0, 0x206u);
  pExceptionObject = CTokenHelper::GetCurrentToken(0xEu, v10, v11);
  EcsUniqueHandle<void *,Win32HandleDeleter,0>::reset(&hToken, &pExceptionObject);
  v12 = hToken;
  if ( !ExpandEnvironmentStringsForUserW(hToken, L"%tmp%", &Dest, 0x104u) )
  {
    LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
    HIWORD(v44) = 67;
    LODWORD(pExceptionObject) = LastFailureAsHRESULT;
    throw (long *)&pExceptionObject;
  }
  LastFailureAsHRESULT = 0;
  LOWORD(v44) = 67;
  CEcsPath::GetVolumeNameForPathName(a3);
  CEcsPath::GetVolumeNameForPathName(&Dest);
  std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v65);
  v13 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v63);
  if ( (unsigned int)_o__wcsicmp(v13) )
  {
    v17 = 0;
    v18 = CTokenHelper::StringSidFromToken(v67, v12);
    v19 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v63);
    v20 = CEcsPath::ConcatenatePaths(v66, v19, a2, 0);
    v21 = std::operator+<unsigned short>(v62, v20, v18);
    std::wstring::operator=(a1, v21);
    std::wstring::~wstring(v62);
    std::wstring::~wstring(v66);
    std::wstring::~wstring(v67);
  }
  else
  {
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v64);
    v14 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v63);
    v16 = CEcsPath::ConcatenatePaths(v62, v14, v15, a2);
    std::wstring::operator=(a1, v16);
    std::wstring::~wstring(v62);
    v17 = 1;
  }
  v22 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
  CEcsPath::ConvertToLongPath(v62, v22, *(_QWORD *)(a1 + 16));
  v42 = 3;
  std::wstring::operator=(a1, v62);
  v42 = 1;
  std::wstring::~wstring(v62);
  if ( a4 )
  {
    v23 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
    if ( GetFileAttributesW(v23) != -1 )
    {
      v24 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
      CEcsPath::DeleteDirectoryRecursive(v24, 0, 1);
    }
    v25 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
    if ( GetFileAttributesW(v25) != -1 )
    {
      LastFailureAsHRESULT = -2134375673;
      HIWORD(v44) = 99;
      LODWORD(pExceptionObject) = -2134375673;
      throw (long *)&pExceptionObject;
    }
    LastFailureAsHRESULT = 0;
    LOWORD(v44) = 99;
  }
  v26 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
  if ( CEcsPath::CreateDirectoryW(v26, v27) && !v17 )
  {
    ATL::CComPtrBase<IFileInfoFromDisk>::CComPtrBase<IFileInfoFromDisk>(&pSecurityDescriptor);
    memset_0(v68, 0, 0x44u);
    v50 = 22;
    v51 = 0;
    v52 = 3;
    v53 = 2032127;
    v54 = 26;
    v55 = 0;
    v56 = 3;
    v57 = 2032127;
    v58 = v68;
    v59 = 3;
    v60 = 2032127;
    v28 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
    SetFileAttributesW(v28, 6u);
    CTokenHelper::UserSidFromToken(v12, 0x44u, v68);
    SecurityDescriptor = CSecurityHelper::CreateSecurityDescriptor(
                           (unsigned int)&pExceptionObject,
                           v29,
                           v30,
                           v31,
                           (__int64)&v50);
    std::unique_ptr<unsigned char [0]>::operator=<std::default_delete<unsigned char [0]>,0>(
      &pSecurityDescriptor,
      SecurityDescriptor);
    std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&pExceptionObject);
    v33 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
    if ( !SetFileSecurityW(v33, 4u, pSecurityDescriptor) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
      {
        v35 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
        WPP_SF_Sd(
          *(_QWORD *)(v36 + 56),
          13,
          (unsigned int)WPP_7c4ceb82cd073befcc4075c3bed8e1cf_Traceguids,
          v35,
          LastError);
      }
      v37 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
      RemoveDirectoryW(v37);
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      LastFailureAsHRESULT = LastError;
      HIWORD(v44) = 147;
      LODWORD(pExceptionObject) = LastError;
      throw (long *)&pExceptionObject;
    }
    std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&pSecurityDescriptor);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
  {
    v38 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
    WPP_SF_S(*(_QWORD *)(v39 + 56), 14, WPP_7c4ceb82cd073befcc4075c3bed8e1cf_Traceguids, v38);
  }
  pExceptionObject = 0;
  EcsUniqueHandle<void *,Win32HandleDeleter,0>::reset(&hToken, &pExceptionObject);
  std::wstring::~wstring(v64);
  std::wstring::~wstring(v65);
  std::wstring::~wstring(v63);
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&LastFailureAsHRESULT);
  return a1;
}

```

## disassembly

```asm
0x1800c7390  push    rbp
0x1800c7392  push    rbx
0x1800c7393  push    rsi
0x1800c7394  push    rdi
0x1800c7395  push    r12
0x1800c7397  push    r14
0x1800c7399  push    r15
0x1800c739b  lea     rbp, [rsp-320h]
0x1800c73a3  sub     rsp, 420h
0x1800c73aa  mov     rax, cs:__security_cookie
0x1800c73b1  xor     rax, rsp
0x1800c73b4  mov     [rbp+350h+var_40], rax
0x1800c73bb  mov     r12b, r9b
0x1800c73be  mov     rdi, r8
0x1800c73c1  mov     r15, rdx
0x1800c73c4  mov     rsi, rcx
0x1800c73c7  mov     [rbp+350h+var_370], rcx
0x1800c73cb  mov     [rsp+450h+var_3F8], 0
0x1800c73d3  lea     rcx, WPP_GLOBAL_Control
0x1800c73da  mov     rax, cs:WPP_GLOBAL_Control
0x1800c73e1  cmp     rax, rcx
0x1800c73e4  jz      short loc_1800C740E
0x1800c73e6  test    byte ptr [rax+44h], 8
0x1800c73ea  jz      short loc_1800C741E
0x1800c73ec  cmp     byte ptr [rax+41h], 6
0x1800c73f0  jb      short loc_1800C740E
0x1800c73f2  mov     edx, 0Ch
0x1800c73f7  lea     r8, WPP_7c4ceb82cd073befcc4075c3bed8e1cf_Traceguids
0x1800c73fe  mov     rcx, [rax+38h]
0x1800c7402  call    WPP_SF_
0x1800c7407  mov     rax, cs:WPP_GLOBAL_Control
0x1800c740e  test    byte ptr [rax+44h], 8
0x1800c7412  jz      short loc_1800C741E
0x1800c7414  cmp     byte ptr [rax+41h], 6
0x1800c7418  jb      short loc_1800C741E
0x1800c741a  mov     cl, 1
0x1800c741c  jmp     short loc_1800C7420
0x1800c741e  xor     cl, cl
0x1800c7420  mov     [rsp+450h+var_3F0], 0
0x1800c7428  mov     [rsp+450h+var_3EC], 30h ; '0'
0x1800c7430  mov     [rsp+450h+var_3E8], cl
0x1800c7434  lea     rax, aCstaginglocati_1; "CStagingLocationConfig::GetStagingLocat"...
0x1800c743b  mov     [rsp+450h+var_3E0], rax
0x1800c7440  mov     [rsp+450h+var_3D8], 0
0x1800c7449  lea     rcx, [rbp+350h+var_348]
0x1800c744d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800c7452  nop
0x1800c7453  lea     rcx, [rbp+350h+var_308]
0x1800c7457  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800c745c  nop
0x1800c745d  lea     rcx, [rbp+350h+var_328]
0x1800c7461  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800c7466  nop
0x1800c7467  mov     rcx, rsi
0x1800c746a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800c746f  mov     [rsp+450h+var_3F8], 1
0x1800c7477  mov     [rbp+350h+hToken], 0
0x1800c747f  xor     eax, eax
0x1800c7481  mov     [rbp+350h+Dest], ax
0x1800c7488  xor     edx, edx; Val
0x1800c748a  mov     r8d, 206h; Size
0x1800c7490  lea     rcx, [rbp+350h+var_24E]; void *
0x1800c7497  call    memset_0
0x1800c749c  mov     ecx, 0Eh; DesiredAccess
0x1800c74a1  call    ?GetCurrentToken@CTokenHelper@@SAPEAXK_N0@Z; CTokenHelper::GetCurrentToken(ulong,bool,bool)
0x1800c74a6  mov     [rsp+450h+pExceptionObject], rax
0x1800c74ab  lea     rdx, [rsp+450h+pExceptionObject]
0x1800c74b0  lea     rcx, [rbp+350h+hToken]
0x1800c74b4  call    ?reset@?$EcsUniqueHandle@PEAXUWin32HandleDeleter@@$0A@@@QEAAXAEBQEAX@Z; EcsUniqueHandle<void *,Win32HandleDeleter,0>::reset(void * const &)
0x1800c74b9  mov     eax, [rsp+450h+var_3F0]
0x1800c74bd  mov     [rsp+450h+var_3F0], eax
0x1800c74c1  mov     r9d, 104h; dwSize
0x1800c74c7  lea     r8, [rbp+350h+Dest]; lpDest
0x1800c74ce  lea     rdx, aTmp_1; "%tmp%"
0x1800c74d5  mov     rbx, [rbp+350h+hToken]
0x1800c74d9  mov     rcx, rbx; hToken
0x1800c74dc  call    cs:__imp_ExpandEnvironmentStringsForUserW
0x1800c74e2  test    eax, eax
0x1800c74e4  jnz     short loc_1800C750F
0x1800c74e6  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x1800c74eb  mov     [rsp+450h+var_3F0], eax
0x1800c74ef  mov     ecx, 43h ; 'C'
0x1800c74f4  mov     word ptr [rsp+450h+var_3EC+2], cx
0x1800c74f9  mov     dword ptr [rsp+450h+pExceptionObject], eax
0x1800c74fd  lea     rdx, _TI1J; pThrowInfo
0x1800c7504  lea     rcx, [rsp+450h+pExceptionObject]; pExceptionObject
0x1800c7509  call    _CxxThrowException_0
0x1800c750f  mov     [rsp+450h+var_3F0], 0
0x1800c7517  mov     ecx, 43h ; 'C'
0x1800c751c  mov     word ptr [rsp+450h+var_3EC], cx
0x1800c7521  lea     r8, [rbp+350h+var_328]
0x1800c7525  lea     rdx, [rbp+350h+var_348]
0x1800c7529  mov     rcx, rdi; lpszFileName
0x1800c752c  call    ?GetVolumeNameForPathName@CEcsPath@@SAXPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z; CEcsPath::GetVolumeNameForPathName(ushort const *,std::wstring &,std::wstring &)
0x1800c7531  lea     r8, [rbp+350h+var_328]
0x1800c7535  lea     rdx, [rbp+350h+var_308]
0x1800c7539  lea     rcx, [rbp+350h+Dest]; lpszFileName
0x1800c7540  call    ?GetVolumeNameForPathName@CEcsPath@@SAXPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z; CEcsPath::GetVolumeNameForPathName(ushort const *,std::wstring &,std::wstring &)
0x1800c7545  lea     rcx, [rbp+350h+var_308]
0x1800c7549  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800c754e  mov     rdx, rax
0x1800c7551  lea     rcx, [rbp+350h+var_348]
0x1800c7555  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800c755a  mov     rcx, rax
0x1800c755d  call    cs:__imp__o__wcsicmp
0x1800c7563  test    eax, eax
0x1800c7565  jnz     short loc_1800C75A6
0x1800c7567  lea     rcx, [rbp+350h+var_328]
0x1800c756b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800c7570  mov     r8, rax
0x1800c7573  lea     rcx, [rbp+350h+var_348]
0x1800c7577  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800c757c  mov     rdx, rax
0x1800c757f  mov     r9, r15
0x1800c7582  lea     rcx, [rbp+350h+var_368]
0x1800c7586  call    ?ConcatenatePaths@CEcsPath@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG00000000@Z; CEcsPath::ConcatenatePaths(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x1800c758b  nop
0x1800c758c  mov     rdx, rax
0x1800c758f  mov     rcx, rsi
0x1800c7592  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800c7597  nop
0x1800c7598  lea     rcx, [rbp+350h+var_368]
0x1800c759c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800c75a1  mov     r14b, 1
0x1800c75a4  jmp     short loc_1800C7614
0x1800c75a6  xor     r14b, r14b
0x1800c75a9  mov     rdx, rbx
0x1800c75ac  lea     rcx, [rbp+350h+var_2C8]
0x1800c75b3  call    ?StringSidFromToken@CTokenHelper@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; CTokenHelper::StringSidFromToken(void *)
0x1800c75b8  mov     rdi, rax
0x1800c75bb  lea     rcx, [rbp+350h+var_348]
0x1800c75bf  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800c75c4  mov     rdx, rax
0x1800c75c7  xor     r9d, r9d
0x1800c75ca  mov     r8, r15
0x1800c75cd  lea     rcx, [rbp+350h+var_2E8]
0x1800c75d1  call    ?ConcatenatePaths@CEcsPath@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG00000000@Z; CEcsPath::ConcatenatePaths(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x1800c75d6  nop
0x1800c75d7  mov     r8, rdi
0x1800c75da  mov     rdx, rax
0x1800c75dd  lea     rcx, [rbp+350h+var_368]
0x1800c75e1  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x1800c75e6  nop
0x1800c75e7  mov     rdx, rax
0x1800c75ea  mov     rcx, rsi
0x1800c75ed  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800c75f2  nop
0x1800c75f3  lea     rcx, [rbp+350h+var_368]
0x1800c75f7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800c75fc  nop
0x1800c75fd  lea     rcx, [rbp+350h+var_2E8]
0x1800c7601  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800c7606  nop
0x1800c7607  lea     rcx, [rbp+350h+var_2C8]
0x1800c760e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800c7613  nop
0x1800c7614  mov     rcx, rsi
0x1800c7617  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800c761c  mov     r8, [rsi+10h]
0x1800c7620  mov     rdx, rax
0x1800c7623  lea     rcx, [rbp+350h+var_368]
0x1800c7627  call    ?ConvertToLongPath@CEcsPath@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG_K@Z; CEcsPath::ConvertToLongPath(ushort const *,unsigned __int64)
0x1800c762c  mov     r15d, 3
0x1800c7632  mov     [rsp+450h+var_3F8], r15d
0x1800c7637  lea     rdx, [rbp+350h+var_368]
0x1800c763b  mov     rcx, rsi
0x1800c763e  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800c7643  mov     eax, r15d
0x1800c7646  and     eax, 0FFFFFFFDh
0x1800c7649  mov     [rsp+450h+var_3F8], eax
0x1800c764d  lea     rcx, [rbp+350h+var_368]
0x1800c7651  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800c7656  test    r12b, r12b
0x1800c7659  jz      loc_1800C76DF
0x1800c765f  mov     rcx, rsi
0x1800c7662  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800c7667  mov     rcx, rax; lpFileName
0x1800c766a  call    cs:__imp_GetFileAttributesW
0x1800c7670  or      edi, 0FFFFFFFFh
0x1800c7673  cmp     eax, edi
0x1800c7675  jz      short loc_1800C768C
0x1800c7677  mov     rcx, rsi
0x1800c767a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800c767f  mov     r8b, 1; bool
0x1800c7682  xor     edx, edx; unsigned __int16 *
0x1800c7684  mov     rcx, rax; unsigned __int16 *
0x1800c7687  call    ?DeleteDirectoryRecursive@CEcsPath@@SA_NPEBG0_N@Z; CEcsPath::DeleteDirectoryRecursive(ushort const *,ushort const *,bool)
0x1800c768c  mov     eax, [rsp+450h+var_3F0]
0x1800c7690  mov     [rsp+450h+var_3F0], eax
0x1800c7694  mov     rcx, rsi
0x1800c7697  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800c769c  mov     rcx, rax; lpFileName
0x1800c769f  call    cs:__imp_GetFileAttributesW
0x1800c76a5  cmp     eax, edi
0x1800c76a7  mov     eax, 63h ; 'c'
0x1800c76ac  jz      short loc_1800C76D2
0x1800c76ae  mov     ecx, 80C80307h
0x1800c76b3  mov     [rsp+450h+var_3F0], ecx
0x1800c76b7  mov     word ptr [rsp+450h+var_3EC+2], ax
0x1800c76bc  mov     dword ptr [rsp+450h+pExceptionObject], ecx
0x1800c76c0  lea     rdx, _TI1J; pThrowInfo
0x1800c76c7  lea     rcx, [rsp+450h+pExceptionObject]; pExceptionObject
0x1800c76cc  call    _CxxThrowException_0
0x1800c76d2  mov     [rsp+450h+var_3F0], 0
0x1800c76da  mov     word ptr [rsp+450h+var_3EC], ax
0x1800c76df  mov     rcx, rsi
0x1800c76e2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800c76e7  mov     rcx, rax; Name
0x1800c76ea  call    ?CreateDirectoryW@CEcsPath@@SA_NPEBGPEAU_SECURITY_ATTRIBUTES@@@Z; CEcsPath::CreateDirectoryW(ushort const *,_SECURITY_ATTRIBUTES *)
0x1800c76ef  test    al, al
0x1800c76f1  jz      loc_1800C786C
0x1800c76f7  test    r14b, r14b
0x1800c76fa  jnz     loc_1800C786C
0x1800c7700  lea     rcx, [rbp+350h+pSecurityDescriptor]
0x1800c7704  call    ??0?$CComPtrBase@UIFileInfoFromDisk@@@ATL@@IEAA@PEAUIFileInfoFromDisk@@@Z; ATL::CComPtrBase<IFileInfoFromDisk>::CComPtrBase<IFileInfoFromDisk>(IFileInfoFromDisk *)
0x1800c7709  nop
0x1800c770a  mov     edi, 44h ; 'D'
0x1800c770f  mov     r8d, edi; Size
0x1800c7712  xor     edx, edx; Val
0x1800c7714  lea     rcx, [rbp+350h+var_2A0]; void *
0x1800c771b  call    memset_0
0x1800c7720  mov     [rbp+350h+var_3C0], 16h
0x1800c7727  xor     eax, eax
0x1800c7729  mov     [rbp+350h+var_3B8], rax
0x1800c772d  mov     [rbp+350h+var_3B0], r15d
0x1800c7731  mov     ecx, 1F01FFh
0x1800c7736  mov     [rbp+350h+var_3AC], ecx
0x1800c7739  mov     [rbp+350h+var_3A8], 1Ah
0x1800c7740  mov     [rbp+350h+var_3A0], rax
0x1800c7744  mov     [rbp+350h+var_398], r15d
0x1800c7748  mov     [rbp+350h+var_394], rcx
0x1800c774c  lea     rax, [rbp+350h+var_2A0]
0x1800c7753  mov     [rbp+350h+var_388], rax
0x1800c7757  mov     [rbp+350h+var_380], r15d
0x1800c775b  mov     [rbp+350h+var_37C], ecx
0x1800c775e  mov     rcx, rsi
0x1800c7761  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800c7766  lea     edx, [rdi-3Eh]; dwFileAttributes
0x1800c7769  mov     rcx, rax; lpFileName
0x1800c776c  call    cs:__imp_SetFileAttributesW
0x1800c7772  lea     r8, [rbp+350h+var_2A0]; void *
0x1800c7779  mov     edx, edi; unsigned __int64
0x1800c777b  mov     rcx, rbx; TokenHandle
0x1800c777e  call    ?UserSidFromToken@CTokenHelper@@SAXPEAX_K0@Z; CTokenHelper::UserSidFromToken(void *,unsigned __int64,void *)
0x1800c7783  lea     rax, [rbp+350h+var_3C0]
0x1800c7787  mov     [rsp+450h+var_430], rax
0x1800c778c  lea     rcx, [rsp+450h+pExceptionObject]
0x1800c7791  call    ?CreateSecurityDescriptor@CSecurityHelper@@SA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@PEBUCSid@1@0KPEBUCSidAndAccess@1@_N2@Z; CSecurityHelper::CreateSecurityDescriptor(CSecurityHelper::CSid const *,CSecurityHelper::CSid const *,ulong,CSecurityHelper::CSidAndAccess const *,bool,bool)
0x1800c7796  nop
0x1800c7797  mov     rdx, rax
0x1800c779a  lea     rcx, [rbp+350h+pSecurityDescriptor]
0x1800c779e  call    ??$?4U?$default_delete@$$BY0A@E@std@@$0A@@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<uchar [0]>::operator=<std::default_delete<uchar [0]>,0>(std::unique_ptr<uchar [0]> &&)
0x1800c77a3  nop
0x1800c77a4  lea     rcx, [rsp+450h+pExceptionObject]
0x1800c77a9  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x1800c77ae  mov     rcx, rsi
0x1800c77b1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800c77b6  mov     r8, [rbp+350h+pSecurityDescriptor]; pSecurityDescriptor
0x1800c77ba  lea     edx, [rdi-40h]; SecurityInformation
0x1800c77bd  mov     rcx, rax; lpFileName
0x1800c77c0  call    cs:__imp_SetFileSecurityW
0x1800c77c6  test    eax, eax
0x1800c77c8  jnz     loc_1800C7863
0x1800c77ce  call    cs:__imp_GetLastError
0x1800c77d4  mov     ebx, eax
0x1800c77d6  mov     r10, cs:WPP_GLOBAL_Control
0x1800c77dd  lea     rax, WPP_GLOBAL_Control
0x1800c77e4  cmp     r10, rax
0x1800c77e7  jz      short loc_1800C7819
0x1800c77e9  test    byte ptr [r10+44h], 8
0x1800c77ee  jz      short loc_1800C7819
0x1800c77f0  cmp     byte ptr [r10+41h], 2
0x1800c77f5  jb      short loc_1800C7819
0x1800c77f7  mov     rcx, rsi
0x1800c77fa  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800c77ff  lea     edx, [rdi-37h]
0x1800c7802  mov     dword ptr [rsp+450h+var_430], ebx
0x1800c7806  mov     r9, rax
0x1800c7809  lea     r8, WPP_7c4ceb82cd073befcc4075c3bed8e1cf_Traceguids
0x1800c7810  mov     rcx, [r10+38h]
0x1800c7814  call    WPP_SF_Sd
0x1800c7819  mov     rcx, rsi
0x1800c781c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800c7821  mov     rcx, rax; lpPathName
0x1800c7824  call    cs:__imp_RemoveDirectoryW
0x1800c782a  mov     eax, [rsp+450h+var_3F0]
0x1800c782e  mov     [rsp+450h+var_3F0], eax
0x1800c7832  test    ebx, ebx
0x1800c7834  jle     short loc_1800C783F
0x1800c7836  movzx   ebx, bx
0x1800c7839  or      ebx, 80070000h
0x1800c783f  mov     [rsp+450h+var_3F0], ebx
0x1800c7843  mov     eax, 93h
0x1800c7848  mov     word ptr [rsp+450h+var_3EC+2], ax
0x1800c784d  mov     dword ptr [rsp+450h+pExceptionObject], ebx
0x1800c7851  lea     rdx, _TI1J; pThrowInfo
0x1800c7858  lea     rcx, [rsp+450h+pExceptionObject]; pExceptionObject
0x1800c785d  call    _CxxThrowException_0
0x1800c7863  lea     rcx, [rbp+350h+pSecurityDescriptor]
0x1800c7867  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
  ... truncated ...
```
