# UtilRegSetCurrentTime(HKEY__ *,wchar_t const *,wchar_t const *)

- ea: `0x180098dec`
- end: `0x180098f48`
- name: `?UtilRegSetCurrentTime@@YAJPEAUHKEY__@@PEB_W1@Z`
- size: `348`
- prototype: `__int64 __fastcall(HKEY, const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004e430`

## callees

- `0x180004bb4`
- `0x18000716c`
- `0x18001c6d8`
- `0x1800492e0`
- `0x18004acdc`
- `0x180098dec`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180098ec1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180098ec1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180098e67`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180098e67`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180098ef7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180098ef7`

## pseudocode

```c
__int64 __fastcall UtilRegSetCurrentTime(HKEY a1, const wchar_t *a2, const wchar_t *a3)
{
  HKEY *phkResult; // rax
  LSTATUS Key; // ebx
  unsigned int v5; // ebx
  wchar_t *v6; // rcx
  __int64 v7; // rdx
  HKEY v8; // rbx
  LSTATUS v9; // eax
  _BYTE v11[32]; // [rsp+50h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+10h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+88h] [rbp+18h] BYREF
  struct _FILETIME Data; // [rsp+90h] [rbp+20h] BYREF

  hKey = 0;
  SystemTimeAsFileTime = 0;
  Data = 0;
  phkResult = (HKEY *)utl::out_ptr<void,tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>,>(
                        v11,
                        &hKey);
  Key = RegCreateKeyExW(
          HKEY_CURRENT_USER,
          L"Software\\Microsoft\\Windows\\Windows Error Reporting",
          0,
          0,
          0,
          0x20106u,
          0,
          phkResult,
          0);
  utl::out_ptr_t<tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>,HKEY__ *,>::~out_ptr_t<tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>,HKEY__ *,>(v11);
  if ( Key )
  {
    v5 = -2147467259;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v7 = 88;
LABEL_5:
      WPP_SF_(*((_QWORD *)v6 + 2), v7, WPP_988ce82756cb3ec502560a762615dae0_Traceguids);
    }
  }
  else
  {
    v8 = hKey;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    Data = SystemTimeAsFileTime;
    v9 = RegSetValueExW(v8, L"LastRateLimitedDumpGenerationTime", 0, 0xBu, (const BYTE *)&Data, 8u);
    if ( !v9 )
    {
      v5 = 0;
      goto LABEL_11;
    }
    v5 = ERROR_HR_FROM_WIN32(v9);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v7 = 89;
      goto LABEL_5;
    }
  }
LABEL_11:
  tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  return v5;
}

```

## disassembly

```asm
0x180098dec  mov     rax, rsp
0x180098def  mov     [rax+20h], rbx
0x180098df3  mov     [rax+18h], r8
0x180098df7  mov     [rax+10h], rdx
0x180098dfb  mov     [rax+8], rcx
0x180098dff  push    rbp
0x180098e00  mov     rbp, rsp
0x180098e03  sub     rsp, 70h
0x180098e07  lea     rdx, [rbp+hKey]
0x180098e0b  mov     [rbp+hKey], 0
0x180098e13  lea     rcx, [rbp+var_20]
0x180098e17  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x180098e1f  mov     [rbp+Data], 0
0x180098e27  call    ??$out_ptr@XV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@$$V@utl@@YA?A_PAEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@@Z
0x180098e2c  mov     [rsp+70h+lpdwDisposition], 0; lpdwDisposition
0x180098e35  lea     rdx, aSoftwareMicros_24; "Software\\Microsoft\\Windows\\Windows E"...
0x180098e3c  mov     [rsp+70h+phkResult], rax; phkResult
0x180098e41  xor     r9d, r9d; lpClass
0x180098e44  mov     [rsp+70h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180098e4d  xor     r8d, r8d; Reserved
0x180098e50  mov     [rsp+70h+samDesired], 20106h; samDesired
0x180098e58  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180098e5f  mov     [rsp+70h+dwOptions], 0; dwOptions
0x180098e67  call    cs:__imp_RegCreateKeyExW
0x180098e6d  lea     rcx, [rbp+var_20]
0x180098e71  mov     ebx, eax
0x180098e73  call    ??1?$out_ptr_t@V?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@PEAUHKEY__@@$$V@utl@@QEAA@XZ; utl::out_ptr_t<tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>,HKEY__ *,>::~out_ptr_t<tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>,HKEY__ *,>(void)
0x180098e78  test    ebx, ebx
0x180098e7a  jz      short loc_180098EB9
0x180098e7c  mov     ebx, 80004005h
0x180098e81  mov     rcx, cs:WPP_GLOBAL_Control
0x180098e88  lea     rax, WPP_GLOBAL_Control
0x180098e8f  cmp     rcx, rax
0x180098e92  jz      loc_180098F2F
0x180098e98  test    byte ptr [rcx+1Ch], 1
0x180098e9c  jz      loc_180098F2F
0x180098ea2  mov     edx, 58h ; 'X'
0x180098ea7  mov     rcx, [rcx+10h]
0x180098eab  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x180098eb2  call    WPP_SF_
0x180098eb7  jmp     short loc_180098F2F
0x180098eb9  mov     rbx, [rbp+hKey]
0x180098ebd  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180098ec1  call    cs:__imp_GetSystemTimeAsFileTime
0x180098ec7  mov     eax, [rbp+SystemTimeAsFileTime.dwHighDateTime]
0x180098eca  lea     rdx, aLastratelimite; "LastRateLimitedDumpGenerationTime"
0x180098ed1  mov     dword ptr [rbp+Data+4], eax
0x180098ed4  mov     r9d, 0Bh; dwType
0x180098eda  mov     eax, [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180098edd  xor     r8d, r8d; Reserved
0x180098ee0  mov     dword ptr [rbp+Data], eax
0x180098ee3  mov     rcx, rbx; hKey
0x180098ee6  lea     rax, [rbp+Data]
0x180098eea  mov     [rsp+70h+samDesired], 8; cbData
0x180098ef2  mov     qword ptr [rsp+70h+dwOptions], rax; lpData
0x180098ef7  call    cs:__imp_RegSetValueExW
0x180098efd  test    eax, eax
0x180098eff  jz      short loc_180098F2D
0x180098f01  mov     ecx, eax; unsigned int
0x180098f03  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180098f08  mov     ebx, eax
0x180098f0a  mov     rcx, cs:WPP_GLOBAL_Control
0x180098f11  lea     rax, WPP_GLOBAL_Control
0x180098f18  cmp     rcx, rax
0x180098f1b  jz      short loc_180098F2F
0x180098f1d  test    byte ptr [rcx+1Ch], 1
0x180098f21  jz      short loc_180098F2F
0x180098f23  mov     edx, 59h ; 'Y'
0x180098f28  jmp     loc_180098EA7
0x180098f2d  xor     ebx, ebx
0x180098f2f  lea     rcx, [rbp+hKey]
0x180098f33  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x180098f38  mov     eax, ebx
0x180098f3a  mov     rbx, [rsp+70h+arg_18]
0x180098f42  add     rsp, 70h
0x180098f46  pop     rbp
0x180098f47  retn
```
