# CSyncStateManager::ValidateSyncFolder(ushort const *,unsigned __int64,bool,unsigned __int64 *)

- ea: `0x180027bf4`
- end: `0x180028268`
- name: `?ValidateSyncFolder@CSyncStateManager@@SAXPEBG_K_NPEA_K@Z`
- size: `1652`
- prototype: `void __fastcall(const unsigned __int16 *, _ULARGE_INTEGER, char, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x18001d3a0`
- `0x18003210c`

## callees

- `0x180002ab0`
- `0x1800035f8`
- `0x180003604`
- `0x180007b9c`
- `0x180007e10`
- `0x180008bdc`
- `0x180009384`
- `0x180010ee0`
- `0x180011314`
- `0x180015150`
- `0x1800244ec`
- `0x180027bf4`
- `0x180062ffc`
- `0x1800632c4`
- `0x1800640b4`
- `0x1800b8f94`
- `0x1800b95f8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180027eec`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180027f4c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180027eec`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180027f4c`
- `KERNEL32!GetDiskFreeSpaceExW` at `0x1800280f3`
- `KERNEL32!GetDiskFreeSpaceExW` at `0x1800280f3`
- `KERNEL32!GetVolumeInformationW` at `0x180027e97`
- `KERNEL32!GetVolumeInformationW` at `0x180027e97`
- `KERNEL32!GetDriveTypeW` at `0x180027dc0`
- `KERNEL32!GetDriveTypeW` at `0x180027dc0`
- `KERNEL32!GetVolumePathNameW` at `0x180027d7a`
- `KERNEL32!GetVolumePathNameW` at `0x180027d7a`
- `KERNEL32!GetFileAttributesW` at `0x180027cfa`
- `KERNEL32!GetFileAttributesW` at `0x180027cfa`
- `ntdll!RtlDetermineDosPathNameType_U` at `0x180027cac`
- `ntdll!RtlDetermineDosPathNameType_U` at `0x180027cac`

## pseudocode

```c
void __fastcall CSyncStateManager::ValidateSyncFolder(
        const unsigned __int16 *a1,
        _ULARGE_INTEGER a2,
        char a3,
        unsigned __int64 *a4)
{
  _BYTE *v8; // rax
  char v9; // cl
  DWORD FileAttributesW; // eax
  DWORD v11; // esi
  int v12; // edi
  const WCHAR *v13; // rax
  const WCHAR *v14; // rax
  __int64 v15; // rax
  __int64 v16; // rdx
  char v17; // r8
  int v18; // eax
  int v19; // eax
  int IsPathEncryptable; // eax
  const WCHAR *v21; // rax
  _ULARGE_INTEGER v22; // rsi
  _ULARGE_INTEGER v23; // rdi
  unsigned __int64 v24; // r14
  unsigned __int64 MinFreeSpaceBytes; // rax
  unsigned int v26; // edx
  unsigned int pExceptionObject; // [rsp+40h] [rbp-C0h] BYREF
  bool v28[4]; // [rsp+44h] [rbp-BCh] BYREF
  int LastFailureAsHRESULT; // [rsp+48h] [rbp-B8h] BYREF
  int v30; // [rsp+4Ch] [rbp-B4h]
  char v31; // [rsp+50h] [rbp-B0h]
  const char *v32; // [rsp+58h] [rbp-A8h]
  __int64 v33; // [rsp+60h] [rbp-A0h]
  _ULARGE_INTEGER FreeBytesAvailableToCaller; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v35[16]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v36; // [rsp+80h] [rbp-80h]
  _BYTE v37[32]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v38[32]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR szVolumePathName; // [rsp+D0h] [rbp-30h] BYREF
  char v40[526]; // [rsp+D2h] [rbp-2Eh] BYREF
  WCHAR FileSystemNameBuffer; // [rsp+2E0h] [rbp+1E0h] BYREF
  char v42[526]; // [rsp+2E2h] [rbp+1E2h] BYREF

  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 42, WPP_f5ae0f942fdc3eab058c35939ac72ca3_Traceguids);
    v8 = WPP_GLOBAL_Control;
  }
  if ( (v8[68] & 8) == 0 || (v9 = 1, v8[65] < 6u) )
    v9 = 0;
  LastFailureAsHRESULT = 0;
  v30 = 682;
  v31 = v9;
  v32 = "CSyncStateManager::ValidateSyncFolder";
  v33 = 0;
  if ( a4 )
    *a4 = 0;
  if ( ((RtlDetermineDosPathNameType_U(a1) - 2) & 0xFFFFFFFB) != 0 )
  {
    LastFailureAsHRESULT = -2134375641;
    HIWORD(v30) = 691;
    pExceptionObject = -2134375641;
    throw (long *)&pExceptionObject;
  }
  LastFailureAsHRESULT = 0;
  LOWORD(v30) = 691;
  FileAttributesW = GetFileAttributesW(a1);
  v11 = FileAttributesW;
  if ( FileAttributesW == -1 )
  {
    v12 = LastFailureAsHRESULT;
  }
  else
  {
    if ( (FileAttributesW & 0x400) != 0 )
    {
      LastFailureAsHRESULT = -2134375642;
      HIWORD(v30) = 697;
      pExceptionObject = -2134375642;
      throw (long *)&pExceptionObject;
    }
    v12 = 0;
    LastFailureAsHRESULT = 0;
    LOWORD(v30) = 697;
  }
  szVolumePathName = 0;
  memset_0(v40, 0, 0x206u);
  LastFailureAsHRESULT = v12;
  if ( !GetVolumePathNameW(a1, &szVolumePathName, 0x104u) )
  {
    LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
    HIWORD(v30) = 704;
    pExceptionObject = LastFailureAsHRESULT;
    throw (long *)&pExceptionObject;
  }
  LastFailureAsHRESULT = 0;
  LOWORD(v30) = 704;
  if ( GetDriveTypeW(&szVolumePathName) - 2 > 1 )
  {
    LastFailureAsHRESULT = -2134375641;
    HIWORD(v30) = 706;
    pExceptionObject = -2134375641;
    throw (long *)&pExceptionObject;
  }
  LastFailureAsHRESULT = 0;
  LOWORD(v30) = 706;
  std::wstring::wstring(v38, a1);
  std::wstring::wstring(v37);
  std::wstring::wstring(v35);
  v13 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v38);
  CEcsPath::GetVolumeNameForPathName(v13);
  FileSystemNameBuffer = 0;
  memset_0(v42, 0, 0x206u);
  v14 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v37);
  if ( !GetVolumeInformationW(v14, 0, 0, 0, 0, 0, &FileSystemNameBuffer, 0x104u) )
  {
    LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
    HIWORD(v30) = 719;
    pExceptionObject = LastFailureAsHRESULT;
    throw (long *)&pExceptionObject;
  }
  LOWORD(v30) = 719;
  LastFailureAsHRESULT = 0;
  if ( (unsigned int)_o__wcsicmp(&FileSystemNameBuffer) )
  {
    LastFailureAsHRESULT = -2134375640;
    HIWORD(v30) = 720;
    pExceptionObject = -2134375640;
    throw (long *)&pExceptionObject;
  }
  LOWORD(v30) = 720;
  LastFailureAsHRESULT = 0;
  if ( !v36
    || (v15 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v35), !(unsigned int)_o__wcsicmp(v15)) )
  {
    LastFailureAsHRESULT = -2134375639;
    HIWORD(v30) = 724;
    pExceptionObject = -2134375639;
    throw (long *)&pExceptionObject;
  }
  LOWORD(v30) = 724;
  LastFailureAsHRESULT = 0;
  if ( CEcsPath::IsPathOnMountPoint(a1) )
  {
    LastFailureAsHRESULT = -2134375642;
    HIWORD(v30) = 728;
    pExceptionObject = -2134375642;
    throw (long *)&pExceptionObject;
  }
  LastFailureAsHRESULT = 0;
  LOWORD(v30) = 728;
  CSyncStateManager::CheckNotAllowedSyncPaths(a1, v16, v17);
  if ( v11 == -1 )
  {
    v19 = LastFailureAsHRESULT;
  }
  else
  {
    v28[0] = 0;
    v18 = CSelectiveWipe::EnterpriseIdRevoked(a1, v28);
    LastFailureAsHRESULT = v18;
    if ( v18 < 0 )
    {
      HIWORD(v30) = 737;
      pExceptionObject = v18;
      throw (long *)&pExceptionObject;
    }
    LOWORD(v30) = 737;
    LastFailureAsHRESULT = v18;
    if ( v28[0] )
    {
      LastFailureAsHRESULT = -2134375638;
      HIWORD(v30) = 738;
      pExceptionObject = -2134375638;
      throw (long *)&pExceptionObject;
    }
    v19 = 0;
    LastFailureAsHRESULT = 0;
    LOWORD(v30) = 738;
    if ( a3 )
    {
      v28[0] = 0;
      IsPathEncryptable = CSelectiveWipe::IsPathEncryptable(a1, v28);
      LastFailureAsHRESULT = IsPathEncryptable;
      if ( IsPathEncryptable < 0 )
      {
        HIWORD(v30) = 744;
        pExceptionObject = IsPathEncryptable;
        throw (long *)&pExceptionObject;
      }
      LOWORD(v30) = 744;
      LastFailureAsHRESULT = IsPathEncryptable;
      if ( !v28[0] )
      {
        LastFailureAsHRESULT = -2134375621;
        HIWORD(v30) = 745;
        pExceptionObject = -2134375621;
        throw (long *)&pExceptionObject;
      }
      v19 = 0;
      LastFailureAsHRESULT = 0;
      LOWORD(v30) = 745;
    }
  }
  FreeBytesAvailableToCaller.QuadPart = 0;
  LastFailureAsHRESULT = v19;
  v21 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v37);
  if ( !GetDiskFreeSpaceExW(v21, &FreeBytesAvailableToCaller, 0, 0) )
  {
    LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
    HIWORD(v30) = 752;
    pExceptionObject = LastFailureAsHRESULT;
    throw (long *)&pExceptionObject;
  }
  LastFailureAsHRESULT = 0;
  LOWORD(v30) = 752;
  v22 = FreeBytesAvailableToCaller;
  v23.QuadPart = 0;
  v24 = -1;
  if ( a2.QuadPart != -1 )
    v23 = a2;
  MinFreeSpaceBytes = CEcsUtility::GetMinFreeSpaceBytes(a1);
  if ( a4 )
  {
    if ( MinFreeSpaceBytes + v23.QuadPart >= MinFreeSpaceBytes )
      v24 = MinFreeSpaceBytes + v23.QuadPart;
    v26 = MinFreeSpaceBytes + v23.QuadPart < MinFreeSpaceBytes ? 0x80070216 : 0;
    *a4 = v24;
    LastFailureAsHRESULT = v26;
    if ( MinFreeSpaceBytes + v23.QuadPart < MinFreeSpaceBytes )
    {
      HIWORD(v30) = 760;
      pExceptionObject = MinFreeSpaceBytes + v23.QuadPart < MinFreeSpaceBytes ? 0x80070216 : 0;
      throw (long *)&pExceptionObject;
    }
    LOWORD(v30) = 760;
  }
  else
  {
    v26 = LastFailureAsHRESULT;
  }
  LastFailureAsHRESULT = v26;
  if ( v22.QuadPart < v23.QuadPart || v22.QuadPart - v23.QuadPart < MinFreeSpaceBytes )
  {
    LastFailureAsHRESULT = -2134375654;
    HIWORD(v30) = 763;
    pExceptionObject = -2134375654;
    throw (long *)&pExceptionObject;
  }
  LastFailureAsHRESULT = 0;
  LOWORD(v30) = 763;
  std::wstring::~wstring(v35);
  std::wstring::~wstring(v37);
  std::wstring::~wstring(v38);
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&LastFailureAsHRESULT);
}

```

## disassembly

```asm
0x180027bf4  mov     [rsp-8+arg_8], rbx
0x180027bf9  push    rbp
0x180027bfa  push    rsi
0x180027bfb  push    rdi
0x180027bfc  push    r12
0x180027bfe  push    r13
0x180027c00  push    r14
0x180027c02  push    r15
0x180027c04  lea     rbp, [rsp-400h]
0x180027c0c  sub     rsp, 500h
0x180027c13  mov     rax, cs:__security_cookie
0x180027c1a  xor     rax, rsp
0x180027c1d  mov     [rbp+430h+var_40], rax
0x180027c24  mov     r15, r9
0x180027c27  mov     r14b, r8b
0x180027c2a  mov     r12, rdx
0x180027c2d  mov     rbx, rcx
0x180027c30  lea     rcx, WPP_GLOBAL_Control
0x180027c37  mov     rax, cs:WPP_GLOBAL_Control
0x180027c3e  cmp     rax, rcx
0x180027c41  jz      short loc_180027C6B
0x180027c43  test    byte ptr [rax+44h], 8
0x180027c47  jz      short loc_180027C6B
0x180027c49  cmp     byte ptr [rax+41h], 6
0x180027c4d  jb      short loc_180027C6B
0x180027c4f  mov     edx, 2Ah ; '*'
0x180027c54  lea     r8, WPP_f5ae0f942fdc3eab058c35939ac72ca3_Traceguids
0x180027c5b  mov     rcx, [rax+38h]
0x180027c5f  call    WPP_SF_
0x180027c64  mov     rax, cs:WPP_GLOBAL_Control
0x180027c6b  xor     r13d, r13d
0x180027c6e  test    byte ptr [rax+44h], 8
0x180027c72  jz      short loc_180027C7C
0x180027c74  cmp     byte ptr [rax+41h], 6
0x180027c78  mov     cl, 1
0x180027c7a  jnb     short loc_180027C7F
0x180027c7c  mov     cl, r13b
0x180027c7f  mov     [rsp+530h+var_4E8], r13d
0x180027c84  mov     [rsp+530h+var_4E4], 2AAh
0x180027c8c  mov     [rsp+530h+var_4E0], cl
0x180027c90  lea     rax, aCsyncstatemana_6; "CSyncStateManager::ValidateSyncFolder"
0x180027c97  mov     [rsp+530h+var_4D8], rax
0x180027c9c  mov     [rsp+530h+var_4D0], r13
0x180027ca1  test    r15, r15
0x180027ca4  jz      short loc_180027CA9
0x180027ca6  mov     [r15], r13
0x180027ca9  mov     rcx, rbx; Path
0x180027cac  call    cs:__imp_RtlDetermineDosPathNameType_U
0x180027cb2  mov     ecx, [rsp+530h+var_4E8]
0x180027cb6  mov     [rsp+530h+var_4E8], ecx
0x180027cba  add     eax, 0FFFFFFFEh
0x180027cbd  mov     ecx, 2B3h
0x180027cc2  test    eax, 0FFFFFFFBh
0x180027cc7  jz      short loc_180027CED
0x180027cc9  mov     eax, 80C80327h
0x180027cce  mov     [rsp+530h+var_4E8], eax
0x180027cd2  mov     word ptr [rsp+530h+var_4E4+2], cx
0x180027cd7  mov     [rsp+530h+pExceptionObject], eax
0x180027cdb  lea     rdx, _TI1J; pThrowInfo
0x180027ce2  lea     rcx, [rsp+530h+pExceptionObject]; pExceptionObject
0x180027ce7  call    _CxxThrowException_0
0x180027ced  mov     [rsp+530h+var_4E8], r13d
0x180027cf2  mov     word ptr [rsp+530h+var_4E4], cx
0x180027cf7  mov     rcx, rbx; lpFileName
0x180027cfa  call    cs:__imp_GetFileAttributesW
0x180027d00  mov     esi, eax
0x180027d02  cmp     eax, 0FFFFFFFFh
0x180027d05  jz      short loc_180027D4D
0x180027d07  mov     ecx, [rsp+530h+var_4E8]
0x180027d0b  mov     [rsp+530h+var_4E8], ecx
0x180027d0f  mov     ecx, 2B9h
0x180027d14  bt      eax, 0Ah
0x180027d18  jnb     short loc_180027D3E
0x180027d1a  mov     eax, 80C80326h
0x180027d1f  mov     [rsp+530h+var_4E8], eax
0x180027d23  mov     word ptr [rsp+530h+var_4E4+2], cx
0x180027d28  mov     [rsp+530h+pExceptionObject], eax
0x180027d2c  lea     rdx, _TI1J; pThrowInfo
0x180027d33  lea     rcx, [rsp+530h+pExceptionObject]; pExceptionObject
0x180027d38  call    _CxxThrowException_0
0x180027d3e  mov     edi, r13d
0x180027d41  mov     [rsp+530h+var_4E8], r13d
0x180027d46  mov     word ptr [rsp+530h+var_4E4], cx
0x180027d4b  jmp     short loc_180027D51
0x180027d4d  mov     edi, [rsp+530h+var_4E8]
0x180027d51  mov     [rbp+430h+szVolumePathName], r13w
0x180027d56  xor     edx, edx; Val
0x180027d58  mov     r8d, 206h; Size
0x180027d5e  lea     rcx, [rbp+430h+var_45E]; void *
0x180027d62  call    memset_0
0x180027d67  mov     [rsp+530h+var_4E8], edi
0x180027d6b  mov     edi, 104h
0x180027d70  mov     r8d, edi; cchBufferLength
0x180027d73  lea     rdx, [rbp+430h+szVolumePathName]; lpszVolumePathName
0x180027d77  mov     rcx, rbx; lpszFileName
0x180027d7a  call    cs:__imp_GetVolumePathNameW
0x180027d80  test    eax, eax
0x180027d82  jnz     short loc_180027DAD
0x180027d84  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x180027d89  mov     [rsp+530h+var_4E8], eax
0x180027d8d  mov     ecx, 2C0h
0x180027d92  mov     word ptr [rsp+530h+var_4E4+2], cx
0x180027d97  mov     [rsp+530h+pExceptionObject], eax
0x180027d9b  lea     rdx, _TI1J; pThrowInfo
0x180027da2  lea     rcx, [rsp+530h+pExceptionObject]; pExceptionObject
0x180027da7  call    _CxxThrowException_0
0x180027dad  mov     [rsp+530h+var_4E8], r13d
0x180027db2  mov     ecx, 2C0h
0x180027db7  mov     word ptr [rsp+530h+var_4E4], cx
0x180027dbc  lea     rcx, [rbp+430h+szVolumePathName]; lpRootPathName
0x180027dc0  call    cs:__imp_GetDriveTypeW
0x180027dc6  mov     ecx, [rsp+530h+var_4E8]
0x180027dca  mov     [rsp+530h+var_4E8], ecx
0x180027dce  add     eax, 0FFFFFFFEh
0x180027dd1  mov     ecx, 2C2h
0x180027dd6  cmp     eax, 1
0x180027dd9  jbe     short loc_180027DFF
0x180027ddb  mov     eax, 80C80327h
0x180027de0  mov     [rsp+530h+var_4E8], eax
0x180027de4  mov     word ptr [rsp+530h+var_4E4+2], cx
0x180027de9  mov     [rsp+530h+pExceptionObject], eax
0x180027ded  lea     rdx, _TI1J; pThrowInfo
0x180027df4  lea     rcx, [rsp+530h+pExceptionObject]; pExceptionObject
0x180027df9  call    _CxxThrowException_0
0x180027dff  mov     [rsp+530h+var_4E8], r13d
0x180027e04  mov     word ptr [rsp+530h+var_4E4], cx
0x180027e09  mov     rdx, rbx
0x180027e0c  lea     rcx, [rbp+430h+var_480]
0x180027e10  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180027e15  nop
0x180027e16  lea     rcx, [rbp+430h+var_4A0]
0x180027e1a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180027e1f  nop
0x180027e20  lea     rcx, [rsp+530h+var_4C0]
0x180027e25  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180027e2a  nop
0x180027e2b  lea     rcx, [rbp+430h+var_480]
0x180027e2f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180027e34  mov     rcx, rax; lpszFileName
0x180027e37  lea     r8, [rsp+530h+var_4C0]
0x180027e3c  lea     rdx, [rbp+430h+var_4A0]
0x180027e40  call    ?GetVolumeNameForPathName@CEcsPath@@SAXPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z; CEcsPath::GetVolumeNameForPathName(ushort const *,std::wstring &,std::wstring &)
0x180027e45  mov     [rbp+430h+FileSystemNameBuffer], r13w
0x180027e4d  xor     edx, edx; Val
0x180027e4f  mov     r8d, 206h; Size
0x180027e55  lea     rcx, [rbp+430h+var_24E]; void *
0x180027e5c  call    memset_0
0x180027e61  mov     eax, [rsp+530h+var_4E8]
0x180027e65  mov     [rsp+530h+var_4E8], eax
0x180027e69  lea     rcx, [rbp+430h+var_4A0]
0x180027e6d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180027e72  mov     rcx, rax; lpRootPathName
0x180027e75  mov     [rsp+530h+nFileSystemNameSize], edi; nFileSystemNameSize
0x180027e79  lea     rax, [rbp+430h+FileSystemNameBuffer]
0x180027e80  mov     [rsp+530h+lpFileSystemNameBuffer], rax; lpFileSystemNameBuffer
0x180027e85  mov     [rsp+530h+lpFileSystemFlags], r13; lpFileSystemFlags
0x180027e8a  mov     [rsp+530h+lpMaximumComponentLength], r13; lpMaximumComponentLength
0x180027e8f  xor     r9d, r9d; lpVolumeSerialNumber
0x180027e92  xor     r8d, r8d; nVolumeNameSize
0x180027e95  xor     edx, edx; lpVolumeNameBuffer
0x180027e97  call    cs:__imp_GetVolumeInformationW
0x180027e9d  test    eax, eax
0x180027e9f  jnz     short loc_180027ECA
0x180027ea1  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x180027ea6  mov     [rsp+530h+var_4E8], eax
0x180027eaa  mov     ecx, 2CFh
0x180027eaf  mov     word ptr [rsp+530h+var_4E4+2], cx
0x180027eb4  mov     [rsp+530h+pExceptionObject], eax
0x180027eb8  lea     rdx, _TI1J; pThrowInfo
0x180027ebf  lea     rcx, [rsp+530h+pExceptionObject]; pExceptionObject
0x180027ec4  call    _CxxThrowException_0
0x180027eca  mov     [rsp+530h+var_4E8], r13d
0x180027ecf  mov     ecx, 2CFh
0x180027ed4  mov     word ptr [rsp+530h+var_4E4], cx
0x180027ed9  mov     [rsp+530h+var_4E8], r13d
0x180027ede  lea     rdx, aNtfs; "NTFS"
0x180027ee5  lea     rcx, [rbp+430h+FileSystemNameBuffer]
0x180027eec  call    cs:__imp__o__wcsicmp
0x180027ef2  test    eax, eax
0x180027ef4  mov     eax, 2D0h
0x180027ef9  jz      short loc_180027F1F
0x180027efb  mov     ecx, 80C80328h
0x180027f00  mov     [rsp+530h+var_4E8], ecx
0x180027f04  mov     word ptr [rsp+530h+var_4E4+2], ax
0x180027f09  mov     [rsp+530h+pExceptionObject], ecx
0x180027f0d  lea     rdx, _TI1J; pThrowInfo
0x180027f14  lea     rcx, [rsp+530h+pExceptionObject]; pExceptionObject
0x180027f19  call    _CxxThrowException_0
0x180027f1f  mov     [rsp+530h+var_4E8], r13d
0x180027f24  mov     word ptr [rsp+530h+var_4E4], ax
0x180027f29  mov     [rsp+530h+var_4E8], r13d
0x180027f2e  cmp     [rbp+430h+var_4B0], r13
0x180027f32  jz      loc_18002823F
0x180027f38  lea     rcx, [rsp+530h+var_4C0]
0x180027f3d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180027f42  mov     rcx, rax
0x180027f45  lea     rdx, asc_18014CE40; "\\"
0x180027f4c  call    cs:__imp__o__wcsicmp
0x180027f52  test    eax, eax
0x180027f54  jz      loc_18002823F
0x180027f5a  mov     [rsp+530h+var_4E8], r13d
0x180027f5f  mov     eax, 2D4h
0x180027f64  mov     word ptr [rsp+530h+var_4E4], ax
0x180027f69  mov     [rsp+530h+var_4E8], r13d
0x180027f6e  mov     rcx, rbx; lpszFileName
0x180027f71  call    ?IsPathOnMountPoint@CEcsPath@@SA_NPEBG@Z; CEcsPath::IsPathOnMountPoint(ushort const *)
0x180027f76  mov     ecx, 2D8h
0x180027f7b  test    al, al
0x180027f7d  jz      short loc_180027FA3
0x180027f7f  mov     eax, 80C80326h
0x180027f84  mov     [rsp+530h+var_4E8], eax
0x180027f88  mov     word ptr [rsp+530h+var_4E4+2], cx
0x180027f8d  mov     [rsp+530h+pExceptionObject], eax
0x180027f91  lea     rdx, _TI1J; pThrowInfo
0x180027f98  lea     rcx, [rsp+530h+pExceptionObject]; pExceptionObject
0x180027f9d  call    _CxxThrowException_0
0x180027fa3  mov     [rsp+530h+var_4E8], r13d
0x180027fa8  mov     word ptr [rsp+530h+var_4E4], cx
0x180027fad  mov     rcx, rbx; unsigned __int16 *
0x180027fb0  call    ?CheckNotAllowedSyncPaths@CSyncStateManager@@CAXPEBG@Z; CSyncStateManager::CheckNotAllowedSyncPaths(ushort const *)
0x180027fb5  cmp     esi, 0FFFFFFFFh
0x180027fb8  jz      loc_1800280CF
0x180027fbe  mov     [rsp+530h+var_4EC], r13b
0x180027fc3  lea     rdx, [rsp+530h+var_4EC]; bool *
0x180027fc8  mov     rcx, rbx; unsigned __int16 *
0x180027fcb  call    ?EnterpriseIdRevoked@CSelectiveWipe@@SAJPEBGPEA_N@Z; CSelectiveWipe::EnterpriseIdRevoked(ushort const *,bool *)
0x180027fd0  mov     [rsp+530h+var_4E8], eax
0x180027fd4  mov     [rsp+530h+var_4E8], eax
0x180027fd8  mov     ecx, 2E1h
0x180027fdd  test    eax, eax
0x180027fdf  jns     short loc_180027FFC
0x180027fe1  mov     word ptr [rsp+530h+var_4E4+2], cx
0x180027fe6  mov     [rsp+530h+pExceptionObject], eax
0x180027fea  lea     rdx, _TI1J; pThrowInfo
0x180027ff1  lea     rcx, [rsp+530h+pExceptionObject]; pExceptionObject
0x180027ff6  call    _CxxThrowException_0
0x180027ffc  mov     word ptr [rsp+530h+var_4E4], cx
0x180028001  mov     [rsp+530h+var_4E8], eax
0x180028005  mov     ecx, 2E2h
0x18002800a  cmp     [rsp+530h+var_4EC], r13b
0x18002800f  jz      short loc_180028035
0x180028011  mov     eax, 80C8032Ah
0x180028016  mov     [rsp+530h+var_4E8], eax
0x18002801a  mov     word ptr [rsp+530h+var_4E4+2], cx
0x18002801f  mov     [rsp+530h+pExceptionObject], eax
0x180028023  lea     rdx, _TI1J; pThrowInfo
0x18002802a  lea     rcx, [rsp+530h+pExceptionObject]; pExceptionObject
0x18002802f  call    _CxxThrowException_0
0x180028035  mov     eax, r13d
0x180028038  mov     [rsp+530h+var_4E8], eax
0x18002803c  mov     word ptr [rsp+530h+var_4E4], cx
0x180028041  test    r14b, r14b
0x180028044  jz      loc_1800280D3
0x18002804a  mov     [rsp+530h+var_4EC], r13b
0x18002804f  lea     rdx, [rsp+530h+var_4EC]; bool *
0x180028054  mov     rcx, rbx; unsigned __int16 *
0x180028057  call    ?IsPathEncryptable@CSelectiveWipe@@SAJPEBGPEA_N@Z; CSelectiveWipe::IsPathEncryptable(ushort const *,bool *)
0x18002805c  mov     [rsp+530h+var_4E8], eax
0x180028060  mov     [rsp+530h+var_4E8], eax
0x180028064  mov     ecx, 2E8h
0x180028069  test    eax, eax
0x18002806b  jns     short loc_180028088
0x18002806d  mov     word ptr [rsp+530h+var_4E4+2], cx
0x180028072  mov     [rsp+530h+pExceptionObject], eax
0x180028076  lea     rdx, _TI1J; pThrowInfo
0x18002807d  lea     rcx, [rsp+530h+pExceptionObject]; pExceptionObject
0x180028082  call    _CxxThrowException_0
0x180028088  mov     word ptr [rsp+530h+var_4E4], cx
0x18002808d  mov     [rsp+530h+var_4E8], eax
0x180028091  mov     ecx, 2E9h
0x180028096  cmp     [rsp+530h+var_4EC], r13b
0x18002809b  jnz     short loc_1800280C1
0x18002809d  mov     eax, 80C8033Bh
0x1800280a2  mov     [rsp+530h+var_4E8], eax
0x1800280a6  mov     word ptr [rsp+530h+var_4E4+2], cx
0x1800280ab  mov     [rsp+530h+pExceptionObject], eax
0x1800280af  lea     rdx, _TI1J; pThrowInfo
0x1800280b6  lea     rcx, [rsp+530h+pExceptionObject]; pExceptionObject
0x1800280bb  call    _CxxThrowException_0
0x1800280c1  mov     eax, r13d
0x1800280c4  mov     [rsp+530h+var_4E8], eax
0x1800280c8  mov     word ptr [rsp+530h+var_4E4], cx
0x1800280cd  jmp     short loc_1800280D3
0x1800280cf  mov     eax, [rsp+530h+var_4E8]
0x1800280d3  mov     qword ptr [rsp+530h+FreeBytesAvailableToCaller], r13
0x1800280d8  mov     [rsp+530h+var_4E8], eax
0x1800280dc  lea     rcx, [rbp+430h+var_4A0]
0x1800280e0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800280e5  mov     rcx, rax; lpDirectoryName
0x1800280e8  xor     r9d, r9d; lpTotalNumberOfFreeBytes
0x1800280eb  xor     r8d, r8d; lpTotalNumberOfBytes
0x1800280ee  lea     rdx, [rsp+530h+FreeBytesAvailableToCaller]; lpFreeBytesAvailableToCaller
0x1800280f3  call    cs:__imp_GetDiskFreeSpaceExW
0x1800280f9  test    eax, eax
0x1800280fb  jnz     short loc_180028126
0x1800280fd  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x180028102  mov     [rsp+530h+var_4E8], eax
0x180028106  mov     ecx, 2F0h
0x18002810b  mov     word ptr [rsp+530h+var_4E4+2], cx
0x180028110  mov     [rsp+530h+pExceptionObject], eax
  ... truncated ...
```
