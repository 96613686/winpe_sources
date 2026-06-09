# Windows::Networking::UX::Internal::LaunchLegacyUX(_GUID const &)

- ea: `0x18006b2e8`
- end: `0x18006b446`
- name: `?LaunchLegacyUX@Internal@UX@Networking@Windows@@YAJAEBU_GUID@@@Z`
- size: `350`
- prototype: `__int64 __fastcall(IID *rclsid, const struct _GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18006b44c`

## callees

- `0x180003ed0`
- `0x180004a70`
- `0x180009d90`
- `0x18002f108`
- `0x18006b2e8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wgetenv` at `0x18006b34a`
- `api-ms-win-crt-private-l1-1-0!_o__wgetenv` at `0x18006b34a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b401`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b401`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18006b3a8`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18006b3a8`
- `ext-ms-win-shell-shell32-l1-2-0!ShellExecuteExW` at `0x18006b3f7`
- `ext-ms-win-shell-shell32-l1-2-0!ShellExecuteExW` at `0x18006b3f7`

## string_xrefs

- `0x18006b350`: `%s\system32`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::Internal::LaunchLegacyUX(IID *rclsid, const struct _GUID *a2)
{
  __int64 v3; // rax
  int v4; // ebx
  signed int LastError; // eax
  LPOLESTR lpsz[2]; // [rsp+30h] [rbp-D0h] BYREF
  SHELLEXECUTEINFOW pExecInfo; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v9[264]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v10[264]; // [rsp+2C0h] [rbp+1C0h] BYREF

  memset_0(v9, 0, 0x20Au);
  memset_0(v10, 0, 0x20Au);
  lpsz[0] = 0;
  v3 = _o__wgetenv(L"SystemRoot");
  v4 = StringCchPrintfW(v9, 0x104u, L"%s\\system32", v3);
  if ( v4 >= 0 )
  {
    v4 = StringCchPrintfW(v10, 0x104u, L"%s\\%s", v9, L"LegacyNetUXHost.exe");
    if ( v4 >= 0 )
    {
      v4 = StringFromCLSID(rclsid, lpsz);
      if ( v4 >= 0 )
      {
        memset_0(&pExecInfo.fMask, 0, 0x6Cu);
        pExecInfo.cbSize = 112;
        pExecInfo.lpFile = v10;
        pExecInfo.lpParameters = lpsz[0];
        pExecInfo.nShow = 1;
        pExecInfo.fMask = 33792;
        if ( !ShellExecuteExW(&pExecInfo) )
        {
          LastError = GetLastError();
          v4 = LastError;
          if ( LastError > 0 )
            v4 = (unsigned __int16)LastError | 0x80070000;
        }
      }
    }
  }
  CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(lpsz);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18006b2e8  mov     [rsp-8+arg_8], rbx
0x18006b2ed  mov     [rsp-8+arg_10], rdi
0x18006b2f2  push    rbp
0x18006b2f3  lea     rbp, [rsp-3E0h]
0x18006b2fb  sub     rsp, 4E0h
0x18006b302  mov     rax, cs:__security_cookie
0x18006b309  xor     rax, rsp
0x18006b30c  mov     [rbp+3E0h+var_10], rax
0x18006b313  mov     rdi, rcx
0x18006b316  mov     ebx, 20Ah
0x18006b31b  mov     r8d, ebx; Size
0x18006b31e  lea     rcx, [rbp+3E0h+var_430]; void *
0x18006b322  xor     edx, edx; Val
0x18006b324  call    memset_0
0x18006b329  mov     r8d, ebx; Size
0x18006b32c  lea     rcx, [rbp+3E0h+var_220]; void *
0x18006b333  xor     edx, edx; Val
0x18006b335  call    memset_0
0x18006b33a  lea     rcx, aSystemroot; "SystemRoot"
0x18006b341  mov     [rsp+4E0h+lpsz], 0
0x18006b34a  call    cs:__imp__o__wgetenv
0x18006b350  lea     r8, aSSystem32; "%s\\system32"
0x18006b357  mov     edx, 104h; unsigned __int64
0x18006b35c  mov     r9, rax
0x18006b35f  lea     rcx, [rbp+3E0h+var_430]; unsigned __int16 *
0x18006b363  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006b368  mov     ebx, eax
0x18006b36a  test    eax, eax
0x18006b36c  js      loc_18006B416
0x18006b372  lea     rax, aLegacynetuxhos; "LegacyNetUXHost.exe"
0x18006b379  mov     edx, 104h; unsigned __int64
0x18006b37e  lea     r9, [rbp+3E0h+var_430]
0x18006b382  mov     [rsp+4E0h+var_4C0], rax
0x18006b387  lea     r8, aSS; "%s\\%s"
0x18006b38e  lea     rcx, [rbp+3E0h+var_220]; unsigned __int16 *
0x18006b395  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006b39a  mov     ebx, eax
0x18006b39c  test    eax, eax
0x18006b39e  js      short loc_18006B416
0x18006b3a0  lea     rdx, [rsp+4E0h+lpsz]; lplpsz
0x18006b3a5  mov     rcx, rdi; rclsid
0x18006b3a8  call    cs:__imp_StringFromCLSID
0x18006b3ae  mov     ebx, eax
0x18006b3b0  test    eax, eax
0x18006b3b2  js      short loc_18006B416
0x18006b3b4  xor     edx, edx; Val
0x18006b3b6  lea     rcx, [rsp+4E0h+pExecInfo.fMask]; void *
0x18006b3bb  lea     r8d, [rdx+6Ch]; Size
0x18006b3bf  call    memset_0
0x18006b3c4  lea     rax, [rbp+3E0h+var_220]
0x18006b3cb  mov     [rsp+4E0h+pExecInfo.cbSize], 70h ; 'p'
0x18006b3d3  mov     [rsp+4E0h+pExecInfo.lpFile], rax
0x18006b3d8  lea     rcx, [rsp+4E0h+pExecInfo]; pExecInfo
0x18006b3dd  mov     rax, [rsp+4E0h+lpsz]
0x18006b3e2  mov     [rsp+4E0h+pExecInfo.lpParameters], rax
0x18006b3e7  mov     [rsp+4E0h+pExecInfo.nShow], 1
0x18006b3ef  mov     [rsp+4E0h+pExecInfo.fMask], 8400h
0x18006b3f7  call    cs:__imp_ShellExecuteExW
0x18006b3fd  test    eax, eax
0x18006b3ff  jnz     short loc_18006B416
0x18006b401  call    cs:__imp_GetLastError
0x18006b407  mov     ebx, eax
0x18006b409  test    eax, eax
0x18006b40b  jle     short loc_18006B416
0x18006b40d  movzx   ebx, ax
0x18006b410  or      ebx, 80070000h
0x18006b416  lea     rcx, [rsp+4E0h+lpsz]
0x18006b41b  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x18006b420  mov     eax, ebx
0x18006b422  mov     rcx, [rbp+3E0h+var_10]
0x18006b429  xor     rcx, rsp; StackCookie
0x18006b42c  call    __security_check_cookie
0x18006b431  lea     r11, [rsp+4E0h+var_s0]
0x18006b439  mov     rbx, [r11+18h]
0x18006b43d  mov     rdi, [r11+20h]
0x18006b441  mov     rsp, r11
0x18006b444  pop     rbp
0x18006b445  retn
```
