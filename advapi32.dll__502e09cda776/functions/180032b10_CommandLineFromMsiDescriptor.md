# CommandLineFromMsiDescriptor

- ea: `0x180032b10`
- end: `0x180032eb0`
- name: `CommandLineFromMsiDescriptor`
- size: `928`
- prototype: `DWORD __stdcall(LPWSTR Descriptor, LPWSTR CommandLine, DWORD *CommandLineLength)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x180032b10`
- `0x180032eb8`
- `0x180033064`
- `0x180048824`
- `0x180049e60`
- `0x1800720b0`
- `0x180074010`

## import_xrefs

- `KERNELBASE!LocalAlloc` at `0x180032d81`
- `KERNELBASE!LocalAlloc` at `0x180032e03`
- `KERNELBASE!LocalAlloc` at `0x180032d81`
- `KERNELBASE!LocalAlloc` at `0x180032e03`
- `KERNELBASE!lstrcmpW` at `0x180032b9b`
- `KERNELBASE!lstrcmpW` at `0x180032b9b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180032ca5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180032ca5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180032c6a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180032c6a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180032cb7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180032cb7`
- `KERNEL32!LocalFree` at `0x180032e30`
- `KERNEL32!LocalFree` at `0x180032e94`
- `KERNEL32!LocalFree` at `0x180032e30`
- `KERNEL32!LocalFree` at `0x180032e94`
- `KERNEL32!GetLastError` at `0x180032e7f`
- `KERNEL32!GetLastError` at `0x180032e7f`

## pseudocode

```c
DWORD __stdcall CommandLineFromMsiDescriptor(LPWSTR Descriptor, LPWSTR CommandLine, DWORD *CommandLineLength)
{
  DWORD LastError; // ebx
  const WCHAR *v7; // rdx
  unsigned int v8; // edi
  DWORD v9; // eax
  DWORD result; // eax
  LSTATUS v11; // ebx
  HWINSTA ProcessWindowStation; // rax
  HWINSTA v13; // rdi
  SIZE_T v14; // rax
  const WCHAR *v15; // rax
  CLoadMsi *v16; // rax
  CLoadMsi *v17; // rdi
  CLoadMsi *v18; // rax
  DWORD cbData; // [rsp+30h] [rbp-49h] BYREF
  unsigned int v20; // [rsp+34h] [rbp-45h] BYREF
  BYTE Data[4]; // [rsp+38h] [rbp-41h] BYREF
  int v22; // [rsp+3Ch] [rbp-3Dh] BYREF
  HKEY hKey; // [rsp+40h] [rbp-39h] BYREF
  WCHAR ValueName[40]; // [rsp+50h] [rbp-29h] BYREF

  LastError = 0;
  hKey = 0;
  cbData = 0;
  v22 = 0;
  v20 = 0;
  *(_DWORD *)Data = 0;
  if ( !qword_1800B1D58 )
  {
    v18 = (CLoadMsi *)LocalAlloc(0, 8u);
    if ( v18 )
    {
      v16 = CLoadMsi::CLoadMsi(v18, &v20);
      LastError = v20;
      v17 = v16;
    }
    else
    {
      v17 = 0;
    }
    qword_1800B1D58 = (__int64)v17;
    if ( v17 )
    {
      if ( !LastError )
        goto LABEL_2;
      CLoadMsi::~CLoadMsi(v17);
      LocalFree(v17);
      qword_1800B1D58 = 0;
    }
    if ( LastError )
      return LastError;
  }
LABEL_2:
  if ( !(unsigned int)LoadUser32Funcs() )
    return 14;
  v7 = hMem;
  if ( !hMem )
  {
    ProcessWindowStation = pfnGetProcessWindowStation();
    v13 = ProcessWindowStation;
    if ( ProcessWindowStation )
    {
      cbData = 0;
      ((void (__fastcall *)(HWINSTA, __int64, _QWORD))pfnGetUserObjectInformationW)(ProcessWindowStation, 2, 0);
      v14 = 0;
      if ( !is_mul_ok(0, 2u) )
        v14 = -1;
      v15 = (const WCHAR *)LocalAlloc(0, v14);
      hMem = v15;
      if ( v15 )
      {
        if ( !(unsigned int)((__int64 (__fastcall *)(HWINSTA, __int64, const WCHAR *, _QWORD, DWORD *))pfnGetUserObjectInformationW)(
                              v13,
                              2,
                              v15,
                              cbData,
                              &cbData) )
        {
          LastError = GetLastError();
          LocalFree((HLOCAL)hMem);
          hMem = 0;
        }
      }
      else
      {
        LastError = 14;
      }
      ((void (__fastcall *)(HWINSTA))pfnCloseWindowStation)(v13);
    }
    v7 = hMem;
  }
  if ( LastError )
    return LastError;
  if ( !v7 || lstrcmpW(L"WinSta0", v7) )
    ((void (__fastcall *)(__int64))gpfnMsiSetInternalUI)(2);
  v8 = ((__int64 (__fastcall *)(_QWORD, _QWORD))gpfnMsiSetInternalUI)(0, 0);
  if ( v8 == 2 )
    goto LABEL_8;
  result = ((__int64 (__fastcall *)(LPWSTR, WCHAR *, _QWORD, _QWORD, _QWORD))gpfnMsiDecomposeDescriptor)(
             Descriptor,
             ValueName,
             0,
             0,
             0);
  if ( !result )
  {
    if ( !RegOpenKeyExW(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Group Policy\\Appmgmt",
            0,
            0x20019u,
            &hKey) )
    {
      cbData = 4;
      v11 = RegQueryValueExW(hKey, ValueName, 0, 0, Data, &cbData);
      RegCloseKey(hKey);
      if ( !v11 )
        ((void (__fastcall *)(_QWORD, _QWORD))gpfnMsiSetInternalUI)(*(unsigned int *)Data, 0);
    }
LABEL_8:
    v9 = ((__int64 (__fastcall *)(LPWSTR, LPWSTR, DWORD *, int *))gpfnMsiProvideComponentFromDescriptor)(
           Descriptor,
           CommandLine,
           CommandLineLength,
           &v22);
    LastError = v9;
    if ( v9 == 1641 || v9 == 3010 || v9 == 1604 )
    {
      LastError = 0;
    }
    else if ( v9 )
    {
      if ( *(_DWORD *)&gDebugLevel )
        _DebugMsg(4u, 0x7D3u, Descriptor, v9);
    }
    ((void (__fastcall *)(_QWORD, _QWORD))gpfnMsiSetInternalUI)(v8, 0);
    return LastError;
  }
  return result;
}

```

## disassembly

```asm
0x180032b10  mov     [rsp-8+arg_18], rbx
0x180032b15  push    rbp
0x180032b16  push    rsi
0x180032b17  push    rdi
0x180032b18  push    r14
0x180032b1a  push    r15
0x180032b1c  lea     rbp, [rsp-37h]
0x180032b21  sub     rsp, 0B0h
0x180032b28  mov     rax, cs:__security_cookie
0x180032b2f  xor     rax, rsp
0x180032b32  mov     [rbp+57h+var_30], rax
0x180032b36  xor     ebx, ebx
0x180032b38  mov     [rbp+57h+hKey], 0
0x180032b40  cmp     cs:qword_1800B1D58, rbx
0x180032b47  mov     r15, r8
0x180032b4a  mov     r14, rdx
0x180032b4d  mov     [rbp+57h+cbData], 0
0x180032b54  mov     rsi, rcx
0x180032b57  mov     [rbp+57h+var_94], 0
0x180032b5e  mov     [rbp+57h+var_9C], ebx
0x180032b61  mov     dword ptr [rbp+57h+Data], ebx
0x180032b64  jz      loc_180032DFC
0x180032b6a  call    ?LoadUser32Funcs@@YAHXZ; LoadUser32Funcs(void)
0x180032b6f  test    eax, eax
0x180032b71  jz      loc_180032E49
0x180032b77  mov     rdx, cs:hMem; lpString2
0x180032b7e  test    rdx, rdx
0x180032b81  jz      loc_180032D26
0x180032b87  test    ebx, ebx
0x180032b89  jnz     short loc_180032BFE
0x180032b8b  test    rdx, rdx
0x180032b8e  jz      loc_180032DBB
0x180032b94  lea     rcx, aWinsta0; "WinSta0"
0x180032b9b  call    cs:__imp_lstrcmpW
0x180032ba2  nop     dword ptr [rax+rax+00h]
0x180032ba7  test    eax, eax
0x180032ba9  jnz     loc_180032DBB
0x180032baf  mov     rax, cs:?gpfnMsiSetInternalUI@@3P6A?AW4tagINSTALLUILEVEL@@W41@PEAPEAUHWND__@@@ZEA; tagINSTALLUILEVEL (*gpfnMsiSetInternalUI)(tagINSTALLUILEVEL,HWND__ * *)
0x180032bb6  xor     edx, edx
0x180032bb8  xor     ecx, ecx
0x180032bba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032bbf  mov     edi, eax
0x180032bc1  cmp     eax, 2
0x180032bc4  jnz     short loc_180032C24
0x180032bc6  mov     rax, cs:?gpfnMsiProvideComponentFromDescriptor@@3P6AIPEBGPEAGPEAK2@ZEA; uint (*gpfnMsiProvideComponentFromDescriptor)(ushort const *,ushort *,ulong *,ulong *)
0x180032bcd  lea     r9, [rbp+57h+var_94]
0x180032bd1  mov     r8, r15
0x180032bd4  mov     rdx, r14
0x180032bd7  mov     rcx, rsi
0x180032bda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032bdf  mov     ebx, eax
0x180032be1  cmp     eax, 669h
0x180032be6  jnz     loc_180032CE1
0x180032bec  xor     ebx, ebx
0x180032bee  mov     rax, cs:?gpfnMsiSetInternalUI@@3P6A?AW4tagINSTALLUILEVEL@@W41@PEAPEAUHWND__@@@ZEA; tagINSTALLUILEVEL (*gpfnMsiSetInternalUI)(tagINSTALLUILEVEL,HWND__ * *)
0x180032bf5  xor     edx, edx
0x180032bf7  mov     ecx, edi
0x180032bf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032bfe  mov     eax, ebx
0x180032c00  mov     rcx, [rbp+57h+var_30]
0x180032c04  xor     rcx, rsp; StackCookie
0x180032c07  call    __security_check_cookie
0x180032c0c  mov     rbx, [rsp+0D0h+arg_18]
0x180032c14  add     rsp, 0B0h
0x180032c1b  pop     r15
0x180032c1d  pop     r14
0x180032c1f  pop     rdi
0x180032c20  pop     rsi
0x180032c21  pop     rbp
0x180032c22  retn
0x180032c24  mov     rax, cs:?gpfnMsiDecomposeDescriptor@@3P6AIPEBGPEAG11PEAK@ZEA; uint (*gpfnMsiDecomposeDescriptor)(ushort const *,ushort *,ushort *,ushort *,ulong *)
0x180032c2b  lea     rdx, [rbp+57h+ValueName]
0x180032c2f  xor     r9d, r9d
0x180032c32  mov     [rsp+0D0h+phkResult], 0
0x180032c3b  xor     r8d, r8d
0x180032c3e  mov     rcx, rsi
0x180032c41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032c46  test    eax, eax
0x180032c48  jnz     short loc_180032C00
0x180032c4a  lea     rax, [rbp+57h+hKey]
0x180032c4e  mov     r9d, 20019h; samDesired
0x180032c54  xor     r8d, r8d; ulOptions
0x180032c57  mov     [rsp+0D0h+phkResult], rax; phkResult
0x180032c5c  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180032c63  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180032c6a  call    cs:__imp_RegOpenKeyExW
0x180032c71  nop     dword ptr [rax+rax+00h]
0x180032c76  test    eax, eax
0x180032c78  jnz     loc_180032BC6
0x180032c7e  mov     rcx, [rbp+57h+hKey]; hKey
0x180032c82  lea     rax, [rbp+57h+cbData]
0x180032c86  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x180032c8b  lea     rdx, [rbp+57h+ValueName]; lpValueName
0x180032c8f  lea     rax, [rbp+57h+Data]
0x180032c93  mov     [rbp+57h+cbData], 4
0x180032c9a  xor     r9d, r9d; lpType
0x180032c9d  mov     [rsp+0D0h+phkResult], rax; lpData
0x180032ca2  xor     r8d, r8d; lpReserved
0x180032ca5  call    cs:__imp_RegQueryValueExW
0x180032cac  nop     dword ptr [rax+rax+00h]
0x180032cb1  mov     rcx, [rbp+57h+hKey]; hKey
0x180032cb5  mov     ebx, eax
0x180032cb7  call    cs:__imp_RegCloseKey
0x180032cbe  nop     dword ptr [rax+rax+00h]
0x180032cc3  test    ebx, ebx
0x180032cc5  jnz     loc_180032BC6
0x180032ccb  mov     ecx, dword ptr [rbp+57h+Data]
0x180032cce  xor     edx, edx
0x180032cd0  mov     rax, cs:?gpfnMsiSetInternalUI@@3P6A?AW4tagINSTALLUILEVEL@@W41@PEAPEAUHWND__@@@ZEA; tagINSTALLUILEVEL (*gpfnMsiSetInternalUI)(tagINSTALLUILEVEL,HWND__ * *)
0x180032cd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032cdc  jmp     loc_180032BC6
0x180032ce1  cmp     eax, 0BC2h
0x180032ce6  jz      loc_180032BEC
0x180032cec  cmp     eax, 644h
0x180032cf1  jz      loc_180032BEC
0x180032cf7  test    eax, eax
0x180032cf9  jz      loc_180032BEE
0x180032cff  cmp     cs:?gDebugLevel@@3KA, 0; ulong gDebugLevel
0x180032d06  jz      loc_180032BEE
0x180032d0c  mov     r9d, eax
0x180032d0f  mov     r8, rsi
0x180032d12  mov     edx, 7D3h; unsigned int
0x180032d17  mov     ecx, 4; unsigned int
0x180032d1c  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x180032d21  jmp     loc_180032BEE
0x180032d26  mov     rax, cs:?pfnGetProcessWindowStation@@3P6APEAUHWINSTA__@@XZEA; HWINSTA__ * (*pfnGetProcessWindowStation)(void)
0x180032d2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032d32  mov     rdi, rax
0x180032d35  test    rax, rax
0x180032d38  jz      short loc_180032DAF
0x180032d3a  xor     r9d, r9d
0x180032d3d  mov     [rbp+57h+cbData], 0
0x180032d44  lea     rax, [rbp+57h+cbData]
0x180032d48  xor     r8d, r8d
0x180032d4b  mov     [rsp+0D0h+phkResult], rax
0x180032d50  mov     rcx, rdi
0x180032d53  mov     rax, cs:?pfnGetUserObjectInformationW@@3P6AHPEAXH0KPEAK@ZEA; int (*pfnGetUserObjectInformationW)(void *,int,void *,ulong,ulong *)
0x180032d5a  lea     edx, [r9+2]
0x180032d5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032d63  mov     ecx, [rbp+57h+cbData]
0x180032d66  mov     eax, 2
0x180032d6b  shr     rcx, 1
0x180032d6e  mul     rcx
0x180032d71  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180032d78  cmovb   rax, rcx
0x180032d7c  xor     ecx, ecx; uFlags
0x180032d7e  mov     rdx, rax; uBytes
0x180032d81  call    cs:__imp_LocalAlloc
0x180032d88  nop     dword ptr [rax+rax+00h]
0x180032d8d  mov     cs:hMem, rax
0x180032d94  test    rax, rax
0x180032d97  jnz     loc_180032E53
0x180032d9d  lea     ebx, [rax+0Eh]
0x180032da0  mov     rax, cs:?pfnCloseWindowStation@@3P6AHPEAUHWINSTA__@@@ZEA; int (*pfnCloseWindowStation)(HWINSTA__ *)
0x180032da7  mov     rcx, rdi
0x180032daa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032daf  mov     rdx, cs:hMem
0x180032db6  jmp     loc_180032B87
0x180032dbb  mov     rax, cs:?gpfnMsiSetInternalUI@@3P6A?AW4tagINSTALLUILEVEL@@W41@PEAPEAUHWND__@@@ZEA; tagINSTALLUILEVEL (*gpfnMsiSetInternalUI)(tagINSTALLUILEVEL,HWND__ * *)
0x180032dc2  xor     edx, edx
0x180032dc4  lea     ecx, [rdx+2]
0x180032dc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032dcc  jmp     loc_180032BAF
0x180032dd1  lea     rdx, [rbp+57h+var_9C]; unsigned int *
0x180032dd5  mov     rcx, rax; this
0x180032dd8  call    ??0CLoadMsi@@QEAA@AEAK@Z; CLoadMsi::CLoadMsi(ulong &)
0x180032ddd  mov     ebx, [rbp+57h+var_9C]
0x180032de0  mov     rdi, rax
0x180032de3  mov     cs:qword_1800B1D58, rdi
0x180032dea  test    rdi, rdi
0x180032ded  jnz     short loc_180032E18
0x180032def  test    ebx, ebx
0x180032df1  jz      loc_180032B6A
0x180032df7  jmp     loc_180032BFE
0x180032dfc  mov     edx, 8; uBytes
0x180032e01  xor     ecx, ecx; uFlags
0x180032e03  call    cs:__imp_LocalAlloc
0x180032e0a  nop     dword ptr [rax+rax+00h]
0x180032e0f  test    rax, rax
0x180032e12  jnz     short loc_180032DD1
0x180032e14  xor     edi, edi
0x180032e16  jmp     short loc_180032DE3
0x180032e18  test    ebx, ebx
0x180032e1a  jz      loc_180032B6A
0x180032e20  test    rdi, rdi
0x180032e23  jz      short loc_180032E3C
0x180032e25  mov     rcx, rdi; this
0x180032e28  call    ??1CLoadMsi@@QEAA@XZ; CLoadMsi::~CLoadMsi(void)
0x180032e2d  mov     rcx, rdi; hMem
0x180032e30  call    cs:__imp_LocalFree
0x180032e37  nop     dword ptr [rax+rax+00h]
0x180032e3c  mov     cs:qword_1800B1D58, 0
0x180032e47  jmp     short loc_180032DEF
0x180032e49  mov     eax, 0Eh
0x180032e4e  jmp     loc_180032C00
0x180032e53  mov     r9d, [rbp+57h+cbData]
0x180032e57  lea     rcx, [rbp+57h+cbData]
0x180032e5b  mov     [rsp+0D0h+phkResult], rcx
0x180032e60  mov     r8, rax
0x180032e63  mov     rax, cs:?pfnGetUserObjectInformationW@@3P6AHPEAXH0KPEAK@ZEA; int (*pfnGetUserObjectInformationW)(void *,int,void *,ulong,ulong *)
0x180032e6a  mov     rcx, rdi
0x180032e6d  mov     edx, 2
0x180032e72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032e77  test    eax, eax
0x180032e79  jnz     loc_180032DA0
0x180032e7f  call    cs:__imp_GetLastError
0x180032e86  nop     dword ptr [rax+rax+00h]
0x180032e8b  mov     rcx, cs:hMem; hMem
0x180032e92  mov     ebx, eax
0x180032e94  call    cs:__imp_LocalFree
0x180032e9b  nop     dword ptr [rax+rax+00h]
0x180032ea0  mov     cs:hMem, 0
0x180032eab  jmp     loc_180032DA0
```
