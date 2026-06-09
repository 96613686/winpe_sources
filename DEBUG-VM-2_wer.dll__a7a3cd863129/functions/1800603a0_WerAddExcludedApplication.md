# WerAddExcludedApplication

- ea: `0x1800603a0`
- end: `0x18006054f`
- name: `WerAddExcludedApplication`
- size: `431`
- prototype: `HRESULT __stdcall(PCWSTR pwzExeName, BOOL bAllUsers)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180004bb4`
- `0x18000716c`
- `0x18001c6d8`
- `0x18001f8c8`
- `0x18001fe24`
- `0x180021634`
- `0x1800603a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060483`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800604be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060483`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800604be`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180060444`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180060444`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180060479`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180060479`

## pseudocode

```c
HRESULT __stdcall WerAddExcludedApplication(PCWSTR pwzExeName, BOOL bAllUsers)
{
  wchar_t *v3; // rcx
  __int64 v4; // rdx
  const wchar_t *v5; // rax
  const WCHAR *v6; // rbx
  HKEY *phkResult; // rax
  DWORD v8; // eax
  unsigned int v9; // ebx
  wchar_t *v10; // rcx
  __int64 v11; // rdx
  DWORD LastError; // eax
  int Data; // [rsp+60h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  Data = 0;
  hKey = 0;
  if ( !pwzExeName )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_22;
    v4 = 37;
LABEL_21:
    WPP_SF_(*((_QWORD *)v3 + 2), v4, WPP_26d694b2c80e3437d7fa3faf31bb64a4_Traceguids);
LABEL_22:
    v9 = -2147024809;
    goto LABEL_23;
  }
  v5 = UtilPathTail(pwzExeName);
  v6 = v5;
  if ( !v5 || !*v5 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_22;
    v4 = 38;
    goto LABEL_21;
  }
  phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  if ( RegCreateKeyExW(
         (HKEY)(bAllUsers - 0x7FFFFFFFLL),
         L"Software\\Microsoft\\Windows\\Windows Error Reporting\\ExcludedApplications",
         0,
         0,
         0,
         0xF013Fu,
         0,
         phkResult,
         0)
    || !hKey )
  {
    LastError = GetLastError();
    v9 = ERROR_HR_FROM_WIN32(LastError);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v11 = 39;
      goto LABEL_17;
    }
  }
  else
  {
    Data = 1;
    if ( RegSetValueExW(hKey, v6, 0, 4u, (const BYTE *)&Data, 4u) )
    {
      v8 = GetLastError();
      v9 = ERROR_HR_FROM_WIN32(v8);
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v11 = 40;
LABEL_17:
        WPP_SF_d(*((_QWORD *)v10 + 2), v11, WPP_26d694b2c80e3437d7fa3faf31bb64a4_Traceguids, v9);
      }
    }
    else
    {
      v9 = 0;
    }
  }
LABEL_23:
  tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  return v9;
}

```

## disassembly

```asm
0x1800603a0  mov     rax, rsp
0x1800603a3  mov     [rax+10h], rbx
0x1800603a7  mov     [rax+20h], rsi
0x1800603ab  push    rdi
0x1800603ac  sub     rsp, 50h
0x1800603b0  xor     esi, esi
0x1800603b2  mov     edi, edx
0x1800603b4  mov     [rax+8], esi
0x1800603b7  mov     [rax+18h], rsi
0x1800603bb  test    rcx, rcx
0x1800603be  jnz     short loc_1800603E9
0x1800603c0  mov     rcx, cs:WPP_GLOBAL_Control; wchar_t *
0x1800603c7  lea     rax, WPP_GLOBAL_Control
0x1800603ce  cmp     rcx, rax
0x1800603d1  jz      loc_18006052E
0x1800603d7  test    byte ptr [rcx+1Ch], 1
0x1800603db  jz      loc_18006052E
0x1800603e1  lea     edx, [rsi+25h]
0x1800603e4  jmp     loc_18006051E
0x1800603e9  call    ?UtilPathTail@@YAPEB_WPEB_W@Z; UtilPathTail(wchar_t const *)
0x1800603ee  mov     rbx, rax
0x1800603f1  test    rax, rax
0x1800603f4  jz      loc_180060500
0x1800603fa  cmp     [rax], si
0x1800603fd  jz      loc_180060500
0x180060403  lea     rcx, [rsp+58h+hKey]
0x180060408  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18006040d  mov     [rsp+58h+lpdwDisposition], rsi; lpdwDisposition
0x180060412  lea     rdx, aSoftwareMicros_21; "Software\\Microsoft\\Windows\\Windows E"...
0x180060419  mov     [rsp+58h+phkResult], rax; phkResult
0x18006041e  neg     edi
0x180060420  mov     [rsp+58h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180060425  sbb     rcx, rcx
0x180060428  mov     [rsp+58h+samDesired], 0F013Fh; samDesired
0x180060430  neg     rcx
0x180060433  mov     [rsp+58h+dwOptions], esi; dwOptions
0x180060437  add     rcx, 0FFFFFFFF80000001h; hKey
0x18006043e  xor     r9d, r9d; lpClass
0x180060441  xor     r8d, r8d; Reserved
0x180060444  call    cs:__imp_RegCreateKeyExW
0x18006044a  test    eax, eax
0x18006044c  jnz     short loc_1800604BE
0x18006044e  mov     rcx, [rsp+58h+hKey]; hKey
0x180060453  test    rcx, rcx
0x180060456  jz      short loc_1800604BE
0x180060458  lea     r9d, [rax+4]; dwType
0x18006045c  mov     [rsp+58h+Data], 1
0x180060464  lea     rax, [rsp+58h+Data]
0x180060469  mov     [rsp+58h+samDesired], r9d; cbData
0x18006046e  xor     r8d, r8d; Reserved
0x180060471  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x180060476  mov     rdx, rbx; lpValueName
0x180060479  call    cs:__imp_RegSetValueExW
0x18006047f  test    eax, eax
0x180060481  jz      short loc_1800604BA
0x180060483  call    cs:__imp_GetLastError
0x180060489  mov     ecx, eax; unsigned int
0x18006048b  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180060490  mov     ebx, eax
0x180060492  mov     rcx, cs:WPP_GLOBAL_Control
0x180060499  lea     rax, WPP_GLOBAL_Control
0x1800604a0  cmp     rcx, rax
0x1800604a3  jz      loc_180060533
0x1800604a9  test    byte ptr [rcx+1Ch], 1
0x1800604ad  jz      loc_180060533
0x1800604b3  mov     edx, 28h ; '('
0x1800604b8  jmp     short loc_1800604EB
0x1800604ba  mov     ebx, esi
0x1800604bc  jmp     short loc_180060533
0x1800604be  call    cs:__imp_GetLastError
0x1800604c4  mov     ecx, eax; unsigned int
0x1800604c6  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800604cb  mov     ebx, eax
0x1800604cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800604d4  lea     rax, WPP_GLOBAL_Control
0x1800604db  cmp     rcx, rax
0x1800604de  jz      short loc_180060533
0x1800604e0  test    byte ptr [rcx+1Ch], 1
0x1800604e4  jz      short loc_180060533
0x1800604e6  mov     edx, 27h ; '''
0x1800604eb  mov     rcx, [rcx+10h]
0x1800604ef  lea     r8, WPP_26d694b2c80e3437d7fa3faf31bb64a4_Traceguids
0x1800604f6  mov     r9d, ebx
0x1800604f9  call    WPP_SF_d
0x1800604fe  jmp     short loc_180060533
0x180060500  mov     rcx, cs:WPP_GLOBAL_Control
0x180060507  lea     rax, WPP_GLOBAL_Control
0x18006050e  cmp     rcx, rax
0x180060511  jz      short loc_18006052E
0x180060513  test    byte ptr [rcx+1Ch], 1
0x180060517  jz      short loc_18006052E
0x180060519  mov     edx, 26h ; '&'
0x18006051e  mov     rcx, [rcx+10h]
0x180060522  lea     r8, WPP_26d694b2c80e3437d7fa3faf31bb64a4_Traceguids
0x180060529  call    WPP_SF_
0x18006052e  mov     ebx, 80070057h
0x180060533  lea     rcx, [rsp+58h+hKey]
0x180060538  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x18006053d  mov     rsi, [rsp+58h+arg_18]
0x180060542  mov     eax, ebx
0x180060544  mov     rbx, [rsp+58h+arg_8]
0x180060549  add     rsp, 50h
0x18006054d  pop     rdi
0x18006054e  retn
```
