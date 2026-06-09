# WerRemoveExcludedApplication

- ea: `0x180060560`
- end: `0x1800606db`
- name: `WerRemoveExcludedApplication`
- size: `379`
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
- `0x180060560`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006060f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006064a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006060f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006064a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180060605`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180060605`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800605ee`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800605ee`

## pseudocode

```c
HRESULT __stdcall WerRemoveExcludedApplication(PCWSTR pwzExeName, BOOL bAllUsers)
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
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  hKey = 0;
  if ( !pwzExeName )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_22;
    v4 = 41;
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
    v4 = 42;
    goto LABEL_21;
  }
  phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  if ( RegOpenKeyExW(
         (HKEY)(bAllUsers - 0x7FFFFFFFLL),
         L"Software\\Microsoft\\Windows\\Windows Error Reporting\\ExcludedApplications",
         0,
         0x102u,
         phkResult)
    || !hKey )
  {
    LastError = GetLastError();
    v9 = ERROR_HR_FROM_WIN32(LastError);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v11 = 43;
      goto LABEL_17;
    }
  }
  else if ( RegDeleteValueW(hKey, v6) )
  {
    v8 = GetLastError();
    v9 = ERROR_HR_FROM_WIN32(v8);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v11 = 44;
LABEL_17:
      WPP_SF_d(*((_QWORD *)v10 + 2), v11, WPP_26d694b2c80e3437d7fa3faf31bb64a4_Traceguids, v9);
    }
  }
  else
  {
    v9 = 0;
  }
LABEL_23:
  tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  return v9;
}

```

## disassembly

```asm
0x180060560  mov     [rsp+arg_8], rbx
0x180060565  mov     [rsp+arg_10], rsi
0x18006056a  push    rdi
0x18006056b  sub     rsp, 30h
0x18006056f  xor     esi, esi
0x180060571  mov     edi, edx
0x180060573  mov     [rsp+38h+hKey], rsi
0x180060578  test    rcx, rcx
0x18006057b  jnz     short loc_1800605A6
0x18006057d  mov     rcx, cs:WPP_GLOBAL_Control; wchar_t *
0x180060584  lea     rax, WPP_GLOBAL_Control
0x18006058b  cmp     rcx, rax
0x18006058e  jz      loc_1800606BA
0x180060594  test    byte ptr [rcx+1Ch], 1
0x180060598  jz      loc_1800606BA
0x18006059e  lea     edx, [rsi+29h]
0x1800605a1  jmp     loc_1800606AA
0x1800605a6  call    ?UtilPathTail@@YAPEB_WPEB_W@Z; UtilPathTail(wchar_t const *)
0x1800605ab  mov     rbx, rax
0x1800605ae  test    rax, rax
0x1800605b1  jz      loc_18006068C
0x1800605b7  cmp     [rax], si
0x1800605ba  jz      loc_18006068C
0x1800605c0  lea     rcx, [rsp+38h+hKey]
0x1800605c5  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x1800605ca  neg     edi
0x1800605cc  mov     [rsp+38h+phkResult], rax; phkResult
0x1800605d1  mov     r9d, 102h; samDesired
0x1800605d7  lea     rdx, aSoftwareMicros_21; "Software\\Microsoft\\Windows\\Windows E"...
0x1800605de  sbb     rcx, rcx
0x1800605e1  xor     r8d, r8d; ulOptions
0x1800605e4  neg     rcx
0x1800605e7  add     rcx, 0FFFFFFFF80000001h; hKey
0x1800605ee  call    cs:__imp_RegOpenKeyExW
0x1800605f4  test    eax, eax
0x1800605f6  jnz     short loc_18006064A
0x1800605f8  mov     rcx, [rsp+38h+hKey]; hKey
0x1800605fd  test    rcx, rcx
0x180060600  jz      short loc_18006064A
0x180060602  mov     rdx, rbx; lpValueName
0x180060605  call    cs:__imp_RegDeleteValueW
0x18006060b  test    eax, eax
0x18006060d  jz      short loc_180060646
0x18006060f  call    cs:__imp_GetLastError
0x180060615  mov     ecx, eax; unsigned int
0x180060617  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18006061c  mov     ebx, eax
0x18006061e  mov     rcx, cs:WPP_GLOBAL_Control
0x180060625  lea     rax, WPP_GLOBAL_Control
0x18006062c  cmp     rcx, rax
0x18006062f  jz      loc_1800606BF
0x180060635  test    byte ptr [rcx+1Ch], 1
0x180060639  jz      loc_1800606BF
0x18006063f  mov     edx, 2Ch ; ','
0x180060644  jmp     short loc_180060677
0x180060646  mov     ebx, esi
0x180060648  jmp     short loc_1800606BF
0x18006064a  call    cs:__imp_GetLastError
0x180060650  mov     ecx, eax; unsigned int
0x180060652  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180060657  mov     ebx, eax
0x180060659  mov     rcx, cs:WPP_GLOBAL_Control
0x180060660  lea     rax, WPP_GLOBAL_Control
0x180060667  cmp     rcx, rax
0x18006066a  jz      short loc_1800606BF
0x18006066c  test    byte ptr [rcx+1Ch], 1
0x180060670  jz      short loc_1800606BF
0x180060672  mov     edx, 2Bh ; '+'
0x180060677  mov     rcx, [rcx+10h]
0x18006067b  lea     r8, WPP_26d694b2c80e3437d7fa3faf31bb64a4_Traceguids
0x180060682  mov     r9d, ebx
0x180060685  call    WPP_SF_d
0x18006068a  jmp     short loc_1800606BF
0x18006068c  mov     rcx, cs:WPP_GLOBAL_Control
0x180060693  lea     rax, WPP_GLOBAL_Control
0x18006069a  cmp     rcx, rax
0x18006069d  jz      short loc_1800606BA
0x18006069f  test    byte ptr [rcx+1Ch], 1
0x1800606a3  jz      short loc_1800606BA
0x1800606a5  mov     edx, 2Ah ; '*'
0x1800606aa  mov     rcx, [rcx+10h]
0x1800606ae  lea     r8, WPP_26d694b2c80e3437d7fa3faf31bb64a4_Traceguids
0x1800606b5  call    WPP_SF_
0x1800606ba  mov     ebx, 80070057h
0x1800606bf  lea     rcx, [rsp+38h+hKey]
0x1800606c4  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x1800606c9  mov     rsi, [rsp+38h+arg_10]
0x1800606ce  mov     eax, ebx
0x1800606d0  mov     rbx, [rsp+38h+arg_8]
0x1800606d5  add     rsp, 30h
0x1800606d9  pop     rdi
0x1800606da  retn
```
