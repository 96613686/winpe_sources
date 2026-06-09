# CRASrv::GetSessionInfo(tagSAFEARRAY * *,int *)

- ea: `0x14000e0e0`
- end: `0x14000e5b4`
- name: `?GetSessionInfo@CRASrv@@UEAAJPEAPEAUtagSAFEARRAY@@PEAH@Z`
- size: `1236`
- prototype: `__int64 __fastcall(CRASrv *__hidden this, struct tagSAFEARRAY **, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000aafc`
- `0x14000e0e0`
- `0x140015240`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x14000e25a`
- `KERNEL32!HeapAlloc` at `0x14000e37a`
- `KERNEL32!HeapAlloc` at `0x14000e25a`
- `KERNEL32!HeapAlloc` at `0x14000e37a`
- `KERNEL32!GetProcAddress` at `0x14000e18f`
- `KERNEL32!GetProcAddress` at `0x14000e1a2`
- `KERNEL32!GetProcAddress` at `0x14000e18f`
- `KERNEL32!GetProcAddress` at `0x14000e1a2`
- `KERNEL32!GetProcessHeap` at `0x14000e249`
- `KERNEL32!GetProcessHeap` at `0x14000e369`
- `KERNEL32!GetProcessHeap` at `0x14000e4ee`
- `KERNEL32!GetProcessHeap` at `0x14000e516`
- `KERNEL32!GetProcessHeap` at `0x14000e249`
- `KERNEL32!GetProcessHeap` at `0x14000e369`
- `KERNEL32!GetProcessHeap` at `0x14000e4ee`
- `KERNEL32!GetProcessHeap` at `0x14000e516`
- `KERNEL32!LoadLibraryW` at `0x14000e173`
- `KERNEL32!LoadLibraryW` at `0x14000e173`
- `KERNEL32!HeapFree` at `0x14000e4fc`
- `KERNEL32!HeapFree` at `0x14000e524`
- `KERNEL32!HeapFree` at `0x14000e4fc`
- `KERNEL32!HeapFree` at `0x14000e524`
- `SHLWAPI!StrCmpIW` at `0x14000e34d`
- `SHLWAPI!StrCmpIW` at `0x14000e34d`
- `OLEAUT32!__imp_SysAllocString` at `0x14000e44a`
- `OLEAUT32!__imp_SysAllocString` at `0x14000e44a`
- `OLEAUT32!__imp_SysFreeString` at `0x14000e594`
- `OLEAUT32!__imp_SysFreeString` at `0x14000e594`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14000e57c`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14000e57c`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x14000e439`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x14000e439`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x14000e475`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x14000e475`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x14000e41c`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x14000e41c`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x14000e312`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x14000e338`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x14000e312`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x14000e338`
- `WTSAPI32!WTSFreeMemory` at `0x14000e2b6`
- `WTSAPI32!WTSFreeMemory` at `0x14000e2cd`
- `WTSAPI32!WTSFreeMemory` at `0x14000e533`
- `WTSAPI32!WTSFreeMemory` at `0x14000e54a`
- `WTSAPI32!WTSFreeMemory` at `0x14000e561`
- `WTSAPI32!WTSFreeMemory` at `0x14000e2b6`
- `WTSAPI32!WTSFreeMemory` at `0x14000e2cd`
- `WTSAPI32!WTSFreeMemory` at `0x14000e533`
- `WTSAPI32!WTSFreeMemory` at `0x14000e54a`
- `WTSAPI32!WTSFreeMemory` at `0x14000e561`
- `WTSAPI32!WTSEnumerateSessionsW` at `0x14000e1f7`
- `WTSAPI32!WTSEnumerateSessionsW` at `0x14000e1f7`

## string_xrefs

- `0x14000e213`: `base\diagnosis\ra\dcom\src\rasrv.cpp`
- `0x14000e3f0`: `base\diagnosis\ra\dcom\src\rasrv.cpp`
- `0x14000e4c8`: `base\diagnosis\ra\dcom\src\rasrv.cpp`
- `0x14000e169`: `wtsapi32.dll`

## pseudocode

```c
__int64 __fastcall CRASrv::GetSessionInfo(CRASrv *this, struct tagSAFEARRAY **a2, int *a3)
{
  _QWORD *v3; // r14
  int *v4; // r13
  SAFEARRAY **v5; // r12
  int v6; // edi
  HMODULE LibraryW; // rax
  const struct _EVENT_DESCRIPTOR *v8; // rdx
  CEventLogger *v9; // rcx
  HMODULE v10; // rbx
  FARPROC ProcAddress; // rdi
  const struct _EVENT_DESCRIPTOR *v12; // rdx
  CEventLogger *v13; // rcx
  const struct _EVENT_DESCRIPTOR *v14; // rdx
  CEventLogger *v15; // rcx
  unsigned int v16; // r9d
  SIZE_T v17; // rbx
  HANDLE ProcessHeap; // rax
  const struct _EVENT_DESCRIPTOR *v19; // rdx
  CEventLogger *v20; // rcx
  DWORD *p_SessionId; // rsi
  DWORD v22; // r13d
  __int64 v23; // r15
  DWORD v24; // r12d
  unsigned __int64 v25; // rdi
  HANDLE v26; // rax
  unsigned __int16 *v27; // rax
  signed int v28; // eax
  unsigned int v29; // r9d
  SAFEARRAY *Vector; // rax
  struct tagSAFEARRAY *v31; // r15
  __int64 i; // rsi
  BSTR v33; // rax
  DWORD v34; // eax
  __int64 j; // rbx
  void *v36; // r15
  HANDLE v37; // rax
  HANDLE v38; // rax
  __int64 v40; // [rsp+28h] [rbp-38h]
  DWORD pBytesReturned; // [rsp+30h] [rbp-30h] BYREF
  DWORD v42; // [rsp+34h] [rbp-2Ch] BYREF
  PVOID pMemory; // [rsp+38h] [rbp-28h] BYREF
  PVOID v44; // [rsp+40h] [rbp-20h] BYREF
  PWTS_SESSION_INFOW ppSessionInfo; // [rsp+48h] [rbp-18h] BYREF
  void *ppvData; // [rsp+50h] [rbp-10h] BYREF
  DWORD pCount; // [rsp+B8h] [rbp+58h] BYREF

  v3 = 0;
  ppSessionInfo = 0;
  pCount = 0;
  v4 = a3;
  pMemory = 0;
  v5 = a2;
  v44 = 0;
  ppvData = 0;
  if ( !a2 )
  {
    v6 = -2147467261;
    CEventLogger::LogError(
      this,
      0,
      L"base\\diagnosis\\ra\\dcom\\src\\rasrv.cpp",
      0xA9u,
      L"CRASrv::GetSessionInfo",
      0x80004003);
    goto LABEL_49;
  }
  if ( !a3 )
  {
    v6 = -2147467261;
    CEventLogger::LogError(
      this,
      (const struct _EVENT_DESCRIPTOR *)a2,
      L"base\\diagnosis\\ra\\dcom\\src\\rasrv.cpp",
      0xAAu,
      L"CRASrv::GetSessionInfo",
      0x80004003);
    goto LABEL_49;
  }
  *a2 = 0;
  *a3 = 0;
  LibraryW = LoadLibraryW(L"wtsapi32.dll");
  v10 = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, "WTSQuerySessionInformationW");
    if ( !GetProcAddress(v10, "WTSFreeMemory") )
    {
      v6 = -2147467261;
      CEventLogger::LogError(
        v13,
        v12,
        L"base\\diagnosis\\ra\\dcom\\src\\rasrv.cpp",
        0xCFu,
        L"CRASrv::GetSessionInfo",
        0x80004003);
      goto LABEL_49;
    }
    if ( !ProcAddress )
    {
      v6 = -2147467261;
      CEventLogger::LogError(
        v13,
        v12,
        L"base\\diagnosis\\ra\\dcom\\src\\rasrv.cpp",
        0xD0u,
        L"CRASrv::GetSessionInfo",
        0x80004003);
      goto LABEL_49;
    }
    if ( !WTSEnumerateSessionsW(0, 0, 1u, &ppSessionInfo, &pCount) )
    {
      v16 = 225;
LABEL_12:
      CEventLogger::LogError(v15, v14, L"base\\diagnosis\\ra\\dcom\\src\\rasrv.cpp", v16, L"CRASrv::GetSessionInfo", 0);
      v6 = -2147467259;
      goto LABEL_49;
    }
    if ( !pCount )
    {
      v16 = 227;
      goto LABEL_12;
    }
    if ( !ppSessionInfo )
    {
      v16 = 228;
      goto LABEL_12;
    }
    v17 = 8LL * pCount;
    ProcessHeap = GetProcessHeap();
    v3 = HeapAlloc(ProcessHeap, 8u, v17);
    if ( v3 )
    {
      p_SessionId = &ppSessionInfo->SessionId;
      v6 = 0;
      v22 = 0;
      v23 = 0;
      while ( v22 < pCount )
      {
        pBytesReturned = 0;
        v42 = 0;
        if ( !p_SessionId )
        {
          v29 = 243;
          goto LABEL_36;
        }
        if ( pMemory )
        {
          WTSFreeMemory(pMemory);
          pMemory = 0;
        }
        v20 = (CEventLogger *)v44;
        if ( v44 )
        {
          WTSFreeMemory(v44);
          v44 = 0;
        }
        v24 = *p_SessionId;
        if ( *p_SessionId != 0x10000
          && p_SessionId[4] - 4 > 1
          && WTSQuerySessionInformationW(0, v24, WTSUserName, (LPWSTR *)&pMemory, &pBytesReturned)
          && WTSQuerySessionInformationW(0, v24, WTSDomainName, (LPWSTR *)&v44, &v42)
          && StrCmpIW((PCWSTR)pMemory, &Class) )
        {
          v25 = (int)(v42 + 35 + pBytesReturned);
          v26 = GetProcessHeap();
          v27 = (unsigned __int16 *)HeapAlloc(v26, 8u, 2 * v25);
          v3[v23] = v27;
          if ( !v27 )
          {
            v29 = 317;
LABEL_36:
            v6 = -2147024882;
            CEventLogger::LogError(
              v20,
              v19,
              L"base\\diagnosis\\ra\\dcom\\src\\rasrv.cpp",
              v29,
              L"CRASrv::GetSessionInfo",
              0x8007000E);
            goto LABEL_37;
          }
          LODWORD(v40) = v24;
          v28 = StringCchPrintfW(v27, v25, L"%s\\%s:%d", v44, pMemory, v40);
          v6 = v28;
          if ( v28 < 0 )
          {
            CEventLogger::LogError(
              v20,
              v19,
              L"base\\diagnosis\\ra\\dcom\\src\\rasrv.cpp",
              0x145u,
              L"CRASrv::GetSessionInfo",
              v28);
LABEL_37:
            v5 = a2;
            v4 = a3;
            goto LABEL_49;
          }
          v23 = (unsigned int)(v23 + 1);
        }
        ++v22;
        p_SessionId += 6;
      }
      pCount = v23;
      Vector = SafeArrayCreateVector(8u, 0, v23);
      v31 = Vector;
      if ( !Vector )
      {
        v29 = 341;
        goto LABEL_36;
      }
      SafeArrayAccessData(Vector, &ppvData);
      for ( i = 0; (unsigned int)i < pCount; i = (unsigned int)(i + 1) )
      {
        v33 = SysAllocString((const OLECHAR *)v3[i]);
        v20 = (CEventLogger *)ppvData;
        *((_QWORD *)ppvData + i) = v33;
        if ( !*((_QWORD *)ppvData + i) )
        {
          v29 = 348;
          goto LABEL_36;
        }
      }
      SafeArrayUnaccessData(v31);
      v5 = a2;
      v4 = a3;
      v34 = pCount;
      ppvData = 0;
      *a2 = v31;
      *a3 = v34;
    }
    else
    {
      v6 = -2147024882;
      CEventLogger::LogError(
        v20,
        v19,
        L"base\\diagnosis\\ra\\dcom\\src\\rasrv.cpp",
        0xE6u,
        L"CRASrv::GetSessionInfo",
        0x8007000E);
    }
  }
  else
  {
    v6 = -2147467259;
    CEventLogger::LogError(
      v9,
      v8,
      L"base\\diagnosis\\ra\\dcom\\src\\rasrv.cpp",
      0xD4u,
      L"CRASrv::GetSessionInfo",
      0x80004005);
  }
LABEL_49:
  for ( j = 0; (unsigned int)j < pCount; j = (unsigned int)(j + 1) )
  {
    if ( v3 )
    {
      v36 = (void *)v3[j];
      if ( v36 )
      {
        v37 = GetProcessHeap();
        HeapFree(v37, 0, v36);
        v3[j] = 0;
      }
    }
  }
  if ( v3 )
  {
    v38 = GetProcessHeap();
    HeapFree(v38, 0, v3);
  }
  if ( pMemory )
  {
    WTSFreeMemory(pMemory);
    pMemory = 0;
  }
  if ( v44 )
  {
    WTSFreeMemory(v44);
    v44 = 0;
  }
  if ( ppSessionInfo )
  {
    WTSFreeMemory(ppSessionInfo);
    ppSessionInfo = 0;
  }
  if ( v6 < 0 )
  {
    if ( *v5 )
    {
      SafeArrayDestroy(*v5);
      *v5 = 0;
    }
    *v4 = 0;
  }
  SysFreeString(0);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14000e0e0  mov     rax, rsp
0x14000e0e3  mov     [rax+8], rbx
0x14000e0e7  mov     [rax+18h], r8
0x14000e0eb  mov     [rax+10h], rdx
0x14000e0ef  push    rbp
0x14000e0f0  push    rsi
0x14000e0f1  push    rdi
0x14000e0f2  push    r12
0x14000e0f4  push    r13
0x14000e0f6  push    r14
0x14000e0f8  push    r15
0x14000e0fa  mov     rbp, rsp
0x14000e0fd  sub     rsp, 60h
0x14000e101  xor     r14d, r14d
0x14000e104  mov     [rbp+ppSessionInfo], 0
0x14000e10c  mov     [rbp+arg_18], 0
0x14000e113  mov     r13, r8
0x14000e116  mov     [rbp+pMemory], 0
0x14000e11e  mov     r12, rdx
0x14000e121  mov     [rbp+var_20], 0
0x14000e129  mov     [rbp+ppvData], r14
0x14000e12d  test    rdx, rdx
0x14000e130  jnz     short loc_14000E149
0x14000e132  mov     edi, 80004003h
0x14000e137  mov     dword ptr [rax-70h], 80004003h
0x14000e13e  mov     r9d, 0A9h
0x14000e144  jmp     loc_14000E4C1
0x14000e149  test    r8, r8
0x14000e14c  jnz     short loc_14000E166
0x14000e14e  mov     edi, 80004003h
0x14000e153  mov     dword ptr [rsp+60h+var_38], 80004003h
0x14000e15b  mov     r9d, 0AAh
0x14000e161  jmp     loc_14000E4C1
0x14000e166  mov     [rdx], r14
0x14000e169  lea     rcx, aWtsapi32Dll_0; "wtsapi32.dll"
0x14000e170  mov     [r8], r14d
0x14000e173  call    cs:__imp_LoadLibraryW
0x14000e179  mov     rbx, rax
0x14000e17c  test    rax, rax
0x14000e17f  jz      loc_14000E4AE
0x14000e185  lea     rdx, aWtsquerysessio; "WTSQuerySessionInformationW"
0x14000e18c  mov     rcx, rax; hModule
0x14000e18f  call    cs:__imp_GetProcAddress
0x14000e195  lea     rdx, aWtsfreememory; "WTSFreeMemory"
0x14000e19c  mov     rcx, rbx; hModule
0x14000e19f  mov     rdi, rax
0x14000e1a2  call    cs:__imp_GetProcAddress
0x14000e1a8  test    rax, rax
0x14000e1ab  jnz     short loc_14000E1C5
0x14000e1ad  mov     edi, 80004003h
0x14000e1b2  mov     dword ptr [rsp+60h+var_38], 80004003h
0x14000e1ba  mov     r9d, 0CFh
0x14000e1c0  jmp     loc_14000E4C1
0x14000e1c5  test    rdi, rdi
0x14000e1c8  jnz     short loc_14000E1E2
0x14000e1ca  mov     edi, 80004003h
0x14000e1cf  mov     dword ptr [rsp+60h+var_38], 80004003h
0x14000e1d7  mov     r9d, 0D0h
0x14000e1dd  jmp     loc_14000E4C1
0x14000e1e2  xor     edx, edx; Reserved
0x14000e1e4  lea     rax, [rbp+arg_18]
0x14000e1e8  lea     r9, [rbp+ppSessionInfo]; ppSessionInfo
0x14000e1ec  mov     [rsp+60h+pCount], rax; pCount
0x14000e1f1  xor     ecx, ecx; hServer
0x14000e1f3  lea     r8d, [rdx+1]; Version
0x14000e1f7  call    cs:__imp_WTSEnumerateSessionsW
0x14000e1fd  test    eax, eax
0x14000e1ff  jnz     short loc_14000E22E
0x14000e201  mov     r9d, 0E1h; unsigned int
0x14000e207  lea     rax, aCrasrvGetsessi; "CRASrv::GetSessionInfo"
0x14000e20e  mov     dword ptr [rsp+60h+var_38], r14d; unsigned int
0x14000e213  lea     r8, aBaseDiagnosisR_2; "base\\diagnosis\\ra\\dcom\\src\\rasrv.c"...
0x14000e21a  mov     [rsp+60h+pCount], rax; unsigned __int16 *
0x14000e21f  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14000e224  mov     edi, 80004005h
0x14000e229  jmp     loc_14000E4D9
0x14000e22e  mov     eax, [rbp+arg_18]
0x14000e231  test    eax, eax
0x14000e233  jz      loc_14000E4A3
0x14000e239  cmp     [rbp+ppSessionInfo], r14
0x14000e23d  jz      loc_14000E498
0x14000e243  mov     ebx, eax
0x14000e245  shl     rbx, 3
0x14000e249  call    cs:__imp_GetProcessHeap
0x14000e24f  mov     r8, rbx; dwBytes
0x14000e252  mov     edx, 8; dwFlags
0x14000e257  mov     rcx, rax; hHeap
0x14000e25a  call    cs:__imp_HeapAlloc
0x14000e260  mov     r14, rax
0x14000e263  test    rax, rax
0x14000e266  jnz     short loc_14000E280
0x14000e268  mov     edi, 8007000Eh
0x14000e26d  mov     dword ptr [rsp+60h+var_38], 8007000Eh
0x14000e275  mov     r9d, 0E6h
0x14000e27b  jmp     loc_14000E4C1
0x14000e280  mov     rsi, [rbp+ppSessionInfo]
0x14000e284  xor     edi, edi
0x14000e286  xor     r13d, r13d
0x14000e289  xor     r15d, r15d
0x14000e28c  cmp     r13d, [rbp+arg_18]
0x14000e290  jnb     loc_14000E40E
0x14000e296  mov     [rbp+pBytesReturned], 0
0x14000e29d  mov     [rbp+var_2C], 0
0x14000e2a4  test    rsi, rsi
0x14000e2a7  jz      loc_14000E3D6
0x14000e2ad  mov     rcx, [rbp+pMemory]; pMemory
0x14000e2b1  test    rcx, rcx
0x14000e2b4  jz      short loc_14000E2C4
0x14000e2b6  call    cs:__imp_WTSFreeMemory
0x14000e2bc  mov     [rbp+pMemory], 0
0x14000e2c4  mov     rcx, [rbp+var_20]; pMemory
0x14000e2c8  test    rcx, rcx
0x14000e2cb  jz      short loc_14000E2DB
0x14000e2cd  call    cs:__imp_WTSFreeMemory
0x14000e2d3  mov     [rbp+var_20], 0
0x14000e2db  mov     r12d, [rsi]
0x14000e2de  cmp     r12d, 10000h
0x14000e2e5  jz      loc_14000E3B6
0x14000e2eb  mov     eax, [rsi+10h]
0x14000e2ee  sub     eax, 4
0x14000e2f1  cmp     eax, 1
0x14000e2f4  jbe     loc_14000E3B6
0x14000e2fa  lea     rax, [rbp+pBytesReturned]
0x14000e2fe  mov     r8d, 5; WTSInfoClass
0x14000e304  lea     r9, [rbp+pMemory]; ppBuffer
0x14000e308  mov     [rsp+60h+pCount], rax; pBytesReturned
0x14000e30d  mov     edx, r12d; SessionId
0x14000e310  xor     ecx, ecx; hServer
0x14000e312  call    cs:__imp_WTSQuerySessionInformationW
0x14000e318  test    eax, eax
0x14000e31a  jz      loc_14000E3B6
0x14000e320  lea     rax, [rbp+var_2C]
0x14000e324  mov     r8d, 7; WTSInfoClass
0x14000e32a  lea     r9, [rbp+var_20]; ppBuffer
0x14000e32e  mov     [rsp+60h+pCount], rax; pBytesReturned
0x14000e333  mov     edx, r12d; SessionId
0x14000e336  xor     ecx, ecx; hServer
0x14000e338  call    cs:__imp_WTSQuerySessionInformationW
0x14000e33e  test    eax, eax
0x14000e340  jz      short loc_14000E3B6
0x14000e342  mov     rcx, [rbp+pMemory]; psz1
0x14000e346  lea     rdx, Class; psz2
0x14000e34d  call    cs:__imp_StrCmpIW
0x14000e353  test    eax, eax
0x14000e355  jz      short loc_14000E3B6
0x14000e357  mov     eax, [rbp+var_2C]
0x14000e35a  mov     ecx, [rbp+pBytesReturned]
0x14000e35d  add     eax, 23h ; '#'
0x14000e360  add     ecx, eax
0x14000e362  movsxd  rdi, ecx
0x14000e365  lea     rbx, [rdi+rdi]
0x14000e369  call    cs:__imp_GetProcessHeap
0x14000e36f  mov     r8, rbx; dwBytes
0x14000e372  mov     edx, 8; dwFlags
0x14000e377  mov     rcx, rax; hHeap
0x14000e37a  call    cs:__imp_HeapAlloc
0x14000e380  mov     [r14+r15*8], rax
0x14000e384  test    rax, rax
0x14000e387  jz      short loc_14000E3CE
0x14000e389  mov     rcx, [rbp+pMemory]
0x14000e38d  lea     r8, aSSD; "%s\\%s:%d"
0x14000e394  mov     r9, [rbp+var_20]
0x14000e398  mov     rdx, rdi; unsigned __int64
0x14000e39b  mov     dword ptr [rsp+60h+var_38], r12d
0x14000e3a0  mov     [rsp+60h+pCount], rcx
0x14000e3a5  mov     rcx, rax; unsigned __int16 *
0x14000e3a8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000e3ad  mov     edi, eax
0x14000e3af  test    eax, eax
0x14000e3b1  js      short loc_14000E3C2
0x14000e3b3  inc     r15d
0x14000e3b6  inc     r13d
0x14000e3b9  add     rsi, 18h
0x14000e3bd  jmp     loc_14000E28C
0x14000e3c2  mov     dword ptr [rsp+60h+var_38], eax
0x14000e3c6  mov     r9d, 145h
0x14000e3cc  jmp     short loc_14000E3E9
0x14000e3ce  mov     r9d, 13Dh
0x14000e3d4  jmp     short loc_14000E3DC
0x14000e3d6  mov     r9d, 0F3h; unsigned int
0x14000e3dc  mov     dword ptr [rsp+60h+var_38], 8007000Eh; unsigned int
0x14000e3e4  mov     edi, 8007000Eh
0x14000e3e9  lea     rax, aCrasrvGetsessi; "CRASrv::GetSessionInfo"
0x14000e3f0  lea     r8, aBaseDiagnosisR_2; "base\\diagnosis\\ra\\dcom\\src\\rasrv.c"...
0x14000e3f7  mov     [rsp+60h+pCount], rax; unsigned __int16 *
0x14000e3fc  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14000e401  mov     r12, [rbp+arg_8]
0x14000e405  mov     r13, [rbp+arg_10]
0x14000e409  jmp     loc_14000E4D9
0x14000e40e  mov     ecx, 8; vt
0x14000e413  mov     [rbp+arg_18], r15d
0x14000e417  mov     r8d, r15d; cElements
0x14000e41a  xor     edx, edx; lLbound
0x14000e41c  call    cs:__imp_SafeArrayCreateVector
0x14000e422  mov     r15, rax
0x14000e425  test    rax, rax
0x14000e428  jnz     short loc_14000E432
0x14000e42a  mov     r9d, 155h
0x14000e430  jmp     short loc_14000E3DC
0x14000e432  lea     rdx, [rbp+ppvData]; ppvData
0x14000e436  mov     rcx, r15; psa
0x14000e439  call    cs:__imp_SafeArrayAccessData
0x14000e43f  xor     esi, esi
0x14000e441  cmp     esi, [rbp+arg_18]
0x14000e444  jnb     short loc_14000E472
0x14000e446  mov     rcx, [r14+rsi*8]; psz
0x14000e44a  call    cs:__imp_SysAllocString
0x14000e450  mov     rcx, [rbp+ppvData]
0x14000e454  mov     [rcx+rsi*8], rax
0x14000e458  mov     rax, [rbp+ppvData]
0x14000e45c  cmp     qword ptr [rax+rsi*8], 0
0x14000e461  jz      short loc_14000E467
0x14000e463  inc     esi
0x14000e465  jmp     short loc_14000E441
0x14000e467  mov     r9d, 15Ch
0x14000e46d  jmp     loc_14000E3DC
0x14000e472  mov     rcx, r15; psa
0x14000e475  call    cs:__imp_SafeArrayUnaccessData
0x14000e47b  mov     r12, [rbp+arg_8]
0x14000e47f  mov     r13, [rbp+arg_10]
0x14000e483  mov     eax, [rbp+arg_18]
0x14000e486  mov     [rbp+ppvData], 0
0x14000e48e  mov     [r12], r15
0x14000e492  mov     [r13+0], eax
0x14000e496  jmp     short loc_14000E4D9
0x14000e498  mov     r9d, 0E4h
0x14000e49e  jmp     loc_14000E207
0x14000e4a3  mov     r9d, 0E3h
0x14000e4a9  jmp     loc_14000E207
0x14000e4ae  mov     edi, 80004005h
0x14000e4b3  mov     dword ptr [rsp+60h+var_38], 80004005h; unsigned int
0x14000e4bb  mov     r9d, 0D4h; unsigned int
0x14000e4c1  lea     rax, aCrasrvGetsessi; "CRASrv::GetSessionInfo"
0x14000e4c8  lea     r8, aBaseDiagnosisR_2; "base\\diagnosis\\ra\\dcom\\src\\rasrv.c"...
0x14000e4cf  mov     [rsp+60h+pCount], rax; unsigned __int16 *
0x14000e4d4  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14000e4d9  xor     ebx, ebx
0x14000e4db  cmp     [rbp+arg_18], ebx
0x14000e4de  jbe     short loc_14000E511
0x14000e4e0  test    r14, r14
0x14000e4e3  jz      short loc_14000E50A
0x14000e4e5  mov     r15, [r14+rbx*8]
0x14000e4e9  test    r15, r15
0x14000e4ec  jz      short loc_14000E50A
0x14000e4ee  call    cs:__imp_GetProcessHeap
0x14000e4f4  mov     r8, r15; lpMem
0x14000e4f7  xor     edx, edx; dwFlags
0x14000e4f9  mov     rcx, rax; hHeap
0x14000e4fc  call    cs:__imp_HeapFree
0x14000e502  mov     qword ptr [r14+rbx*8], 0
0x14000e50a  inc     ebx
0x14000e50c  cmp     ebx, [rbp+arg_18]
0x14000e50f  jb      short loc_14000E4E0
0x14000e511  test    r14, r14
0x14000e514  jz      short loc_14000E52A
0x14000e516  call    cs:__imp_GetProcessHeap
0x14000e51c  mov     r8, r14; lpMem
0x14000e51f  xor     edx, edx; dwFlags
0x14000e521  mov     rcx, rax; hHeap
0x14000e524  call    cs:__imp_HeapFree
0x14000e52a  mov     rcx, [rbp+pMemory]; pMemory
0x14000e52e  test    rcx, rcx
0x14000e531  jz      short loc_14000E541
0x14000e533  call    cs:__imp_WTSFreeMemory
0x14000e539  mov     [rbp+pMemory], 0
0x14000e541  mov     rcx, [rbp+var_20]; pMemory
0x14000e545  test    rcx, rcx
0x14000e548  jz      short loc_14000E558
0x14000e54a  call    cs:__imp_WTSFreeMemory
0x14000e550  mov     [rbp+var_20], 0
0x14000e558  mov     rcx, [rbp+ppSessionInfo]; pMemory
0x14000e55c  test    rcx, rcx
0x14000e55f  jz      short loc_14000E56F
0x14000e561  call    cs:__imp_WTSFreeMemory
0x14000e567  mov     [rbp+ppSessionInfo], 0
0x14000e56f  test    edi, edi
0x14000e571  jns     short loc_14000E592
0x14000e573  mov     rcx, [r12]; psa
0x14000e577  test    rcx, rcx
0x14000e57a  jz      short loc_14000E58A
0x14000e57c  call    cs:__imp_SafeArrayDestroy
0x14000e582  mov     qword ptr [r12], 0
0x14000e58a  mov     dword ptr [r13+0], 0
0x14000e592  xor     ecx, ecx; bstrString
0x14000e594  call    cs:__imp_SysFreeString
0x14000e59a  mov     rbx, [rsp+60h+arg_0]
0x14000e5a2  mov     eax, edi
0x14000e5a4  add     rsp, 60h
0x14000e5a8  pop     r15
0x14000e5aa  pop     r14
0x14000e5ac  pop     r13
0x14000e5ae  pop     r12
0x14000e5b0  pop     rdi
0x14000e5b1  pop     rsi
0x14000e5b2  pop     rbp
0x14000e5b3  retn
```
