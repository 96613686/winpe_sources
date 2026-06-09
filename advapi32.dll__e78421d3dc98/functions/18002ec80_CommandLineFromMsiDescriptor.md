# CommandLineFromMsiDescriptor

- ea: `0x18002ec80`
- end: `0x18002efe9`
- name: `CommandLineFromMsiDescriptor`
- size: `873`
- prototype: `DWORD __stdcall(LPWSTR Descriptor, LPWSTR CommandLine, DWORD *CommandLineLength)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x18002ec80`
- `0x18002eff0`
- `0x18002f164`
- `0x18004332c`
- `0x180044814`
- `0x180065090`
- `0x180066010`

## import_xrefs

- `KERNELBASE!LocalAlloc` at `0x18002eed8`
- `KERNELBASE!LocalAlloc` at `0x18002ef54`
- `KERNELBASE!LocalAlloc` at `0x18002eed8`
- `KERNELBASE!LocalAlloc` at `0x18002ef54`
- `KERNELBASE!lstrcmpW` at `0x18002ed0b`
- `KERNELBASE!lstrcmpW` at `0x18002ed0b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002ee08`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002ee08`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002edd3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002edd3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ee14`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ee14`
- `KERNEL32!LocalFree` at `0x18002ef7b`
- `KERNEL32!LocalFree` at `0x18002efd3`
- `KERNEL32!LocalFree` at `0x18002ef7b`
- `KERNEL32!LocalFree` at `0x18002efd3`
- `KERNEL32!GetLastError` at `0x18002efc4`
- `KERNEL32!GetLastError` at `0x18002efc4`

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
  if ( !qword_1800A2D58 )
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
    qword_1800A2D58 = (__int64)v17;
    if ( v17 )
    {
      if ( !LastError )
        goto LABEL_2;
      CLoadMsi::~CLoadMsi(v17);
      LocalFree(v17);
      qword_1800A2D58 = 0;
    }
    if ( LastError )
      return LastError;
  }
LABEL_2:
  if ( !(unsigned int)LoadUser32Funcs() )
    return 14;
  v7 = lpString2;
  if ( !lpString2 )
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
      lpString2 = v15;
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
          LocalFree((HLOCAL)lpString2);
          lpString2 = 0;
        }
      }
      else
      {
        LastError = 14;
      }
      ((void (__fastcall *)(HWINSTA))pfnCloseWindowStation)(v13);
    }
    v7 = lpString2;
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
0x18002ec80  mov     [rsp-8+arg_18], rbx
0x18002ec85  push    rbp
0x18002ec86  push    rsi
0x18002ec87  push    rdi
0x18002ec88  push    r14
0x18002ec8a  push    r15
0x18002ec8c  lea     rbp, [rsp-37h]
0x18002ec91  sub     rsp, 0B0h
0x18002ec98  mov     rax, cs:__security_cookie
0x18002ec9f  xor     rax, rsp
0x18002eca2  mov     [rbp+57h+var_30], rax
0x18002eca6  xor     ebx, ebx
0x18002eca8  mov     [rbp+57h+hKey], 0
0x18002ecb0  cmp     cs:qword_1800A2D58, rbx
0x18002ecb7  mov     r15, r8
0x18002ecba  mov     r14, rdx
0x18002ecbd  mov     [rbp+57h+cbData], 0
0x18002ecc4  mov     rsi, rcx
0x18002ecc7  mov     [rbp+57h+var_94], 0
0x18002ecce  mov     [rbp+57h+var_9C], ebx
0x18002ecd1  mov     dword ptr [rbp+57h+Data], ebx
0x18002ecd4  jz      loc_18002EF4D
0x18002ecda  call    ?LoadUser32Funcs@@YAHXZ; LoadUser32Funcs(void)
0x18002ecdf  test    eax, eax
0x18002ece1  jz      loc_18002EF8E
0x18002ece7  mov     rdx, cs:lpString2; lpString2
0x18002ecee  test    rdx, rdx
0x18002ecf1  jz      loc_18002EE7D
0x18002ecf7  test    ebx, ebx
0x18002ecf9  jnz     short loc_18002ED68
0x18002ecfb  test    rdx, rdx
0x18002ecfe  jz      loc_18002EF0C
0x18002ed04  lea     rcx, aWinsta0; "WinSta0"
0x18002ed0b  call    cs:__imp_lstrcmpW
0x18002ed11  test    eax, eax
0x18002ed13  jnz     loc_18002EF0C
0x18002ed19  mov     rax, cs:?gpfnMsiSetInternalUI@@3P6A?AW4tagINSTALLUILEVEL@@W41@PEAPEAUHWND__@@@ZEA; tagINSTALLUILEVEL (*gpfnMsiSetInternalUI)(tagINSTALLUILEVEL,HWND__ * *)
0x18002ed20  xor     edx, edx
0x18002ed22  xor     ecx, ecx
0x18002ed24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ed29  mov     edi, eax
0x18002ed2b  cmp     eax, 2
0x18002ed2e  jnz     short loc_18002ED8D
0x18002ed30  mov     rax, cs:?gpfnMsiProvideComponentFromDescriptor@@3P6AIPEBGPEAGPEAK2@ZEA; uint (*gpfnMsiProvideComponentFromDescriptor)(ushort const *,ushort *,ulong *,ulong *)
0x18002ed37  lea     r9, [rbp+57h+var_94]
0x18002ed3b  mov     r8, r15
0x18002ed3e  mov     rdx, r14
0x18002ed41  mov     rcx, rsi
0x18002ed44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ed49  mov     ebx, eax
0x18002ed4b  cmp     eax, 669h
0x18002ed50  jnz     loc_18002EE38
0x18002ed56  xor     ebx, ebx
0x18002ed58  mov     rax, cs:?gpfnMsiSetInternalUI@@3P6A?AW4tagINSTALLUILEVEL@@W41@PEAPEAUHWND__@@@ZEA; tagINSTALLUILEVEL (*gpfnMsiSetInternalUI)(tagINSTALLUILEVEL,HWND__ * *)
0x18002ed5f  xor     edx, edx
0x18002ed61  mov     ecx, edi
0x18002ed63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ed68  mov     eax, ebx
0x18002ed6a  mov     rcx, [rbp+57h+var_30]
0x18002ed6e  xor     rcx, rsp; StackCookie
0x18002ed71  call    __security_check_cookie
0x18002ed76  mov     rbx, [rsp+0D0h+arg_18]
0x18002ed7e  add     rsp, 0B0h
0x18002ed85  pop     r15
0x18002ed87  pop     r14
0x18002ed89  pop     rdi
0x18002ed8a  pop     rsi
0x18002ed8b  pop     rbp
0x18002ed8c  retn
0x18002ed8d  mov     rax, cs:?gpfnMsiDecomposeDescriptor@@3P6AIPEBGPEAG11PEAK@ZEA; uint (*gpfnMsiDecomposeDescriptor)(ushort const *,ushort *,ushort *,ushort *,ulong *)
0x18002ed94  lea     rdx, [rbp+57h+ValueName]
0x18002ed98  xor     r9d, r9d
0x18002ed9b  mov     [rsp+0D0h+phkResult], 0
0x18002eda4  xor     r8d, r8d
0x18002eda7  mov     rcx, rsi
0x18002edaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002edaf  test    eax, eax
0x18002edb1  jnz     short loc_18002ED6A
0x18002edb3  lea     rax, [rbp+57h+hKey]
0x18002edb7  mov     r9d, 20019h; samDesired
0x18002edbd  xor     r8d, r8d; ulOptions
0x18002edc0  mov     [rsp+0D0h+phkResult], rax; phkResult
0x18002edc5  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002edcc  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18002edd3  call    cs:__imp_RegOpenKeyExW
0x18002edd9  test    eax, eax
0x18002eddb  jnz     loc_18002ED30
0x18002ede1  mov     rcx, [rbp+57h+hKey]; hKey
0x18002ede5  lea     rax, [rbp+57h+cbData]
0x18002ede9  mov     [rsp+0D0h+lpcbData], rax; lpcbData
0x18002edee  lea     rdx, [rbp+57h+ValueName]; lpValueName
0x18002edf2  lea     rax, [rbp+57h+Data]
0x18002edf6  mov     [rbp+57h+cbData], 4
0x18002edfd  xor     r9d, r9d; lpType
0x18002ee00  mov     [rsp+0D0h+phkResult], rax; lpData
0x18002ee05  xor     r8d, r8d; lpReserved
0x18002ee08  call    cs:__imp_RegQueryValueExW
0x18002ee0e  mov     rcx, [rbp+57h+hKey]; hKey
0x18002ee12  mov     ebx, eax
0x18002ee14  call    cs:__imp_RegCloseKey
0x18002ee1a  test    ebx, ebx
0x18002ee1c  jnz     loc_18002ED30
0x18002ee22  mov     ecx, dword ptr [rbp+57h+Data]
0x18002ee25  xor     edx, edx
0x18002ee27  mov     rax, cs:?gpfnMsiSetInternalUI@@3P6A?AW4tagINSTALLUILEVEL@@W41@PEAPEAUHWND__@@@ZEA; tagINSTALLUILEVEL (*gpfnMsiSetInternalUI)(tagINSTALLUILEVEL,HWND__ * *)
0x18002ee2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ee33  jmp     loc_18002ED30
0x18002ee38  cmp     eax, 0BC2h
0x18002ee3d  jz      loc_18002ED56
0x18002ee43  cmp     eax, 644h
0x18002ee48  jz      loc_18002ED56
0x18002ee4e  test    eax, eax
0x18002ee50  jz      loc_18002ED58
0x18002ee56  cmp     cs:?gDebugLevel@@3KA, 0; ulong gDebugLevel
0x18002ee5d  jz      loc_18002ED58
0x18002ee63  mov     r9d, eax
0x18002ee66  mov     r8, rsi
0x18002ee69  mov     edx, 7D3h; unsigned int
0x18002ee6e  mov     ecx, 4; unsigned int
0x18002ee73  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18002ee78  jmp     loc_18002ED58
0x18002ee7d  mov     rax, cs:?pfnGetProcessWindowStation@@3P6APEAUHWINSTA__@@XZEA; HWINSTA__ * (*pfnGetProcessWindowStation)(void)
0x18002ee84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ee89  mov     rdi, rax
0x18002ee8c  test    rax, rax
0x18002ee8f  jz      short loc_18002EF00
0x18002ee91  xor     r9d, r9d
0x18002ee94  mov     [rbp+57h+cbData], 0
0x18002ee9b  lea     rax, [rbp+57h+cbData]
0x18002ee9f  xor     r8d, r8d
0x18002eea2  mov     [rsp+0D0h+phkResult], rax
0x18002eea7  mov     rcx, rdi
0x18002eeaa  mov     rax, cs:?pfnGetUserObjectInformationW@@3P6AHPEAXH0KPEAK@ZEA; int (*pfnGetUserObjectInformationW)(void *,int,void *,ulong,ulong *)
0x18002eeb1  lea     edx, [r9+2]
0x18002eeb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eeba  mov     ecx, [rbp+57h+cbData]
0x18002eebd  mov     eax, 2
0x18002eec2  shr     rcx, 1
0x18002eec5  mul     rcx
0x18002eec8  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002eecf  cmovb   rax, rcx
0x18002eed3  xor     ecx, ecx; uFlags
0x18002eed5  mov     rdx, rax; uBytes
0x18002eed8  call    cs:__imp_LocalAlloc
0x18002eede  mov     cs:lpString2, rax
0x18002eee5  test    rax, rax
0x18002eee8  jnz     loc_18002EF98
0x18002eeee  lea     ebx, [rax+0Eh]
0x18002eef1  mov     rax, cs:?pfnCloseWindowStation@@3P6AHPEAUHWINSTA__@@@ZEA; int (*pfnCloseWindowStation)(HWINSTA__ *)
0x18002eef8  mov     rcx, rdi
0x18002eefb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ef00  mov     rdx, cs:lpString2
0x18002ef07  jmp     loc_18002ECF7
0x18002ef0c  mov     rax, cs:?gpfnMsiSetInternalUI@@3P6A?AW4tagINSTALLUILEVEL@@W41@PEAPEAUHWND__@@@ZEA; tagINSTALLUILEVEL (*gpfnMsiSetInternalUI)(tagINSTALLUILEVEL,HWND__ * *)
0x18002ef13  xor     edx, edx
0x18002ef15  lea     ecx, [rdx+2]
0x18002ef18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ef1d  jmp     loc_18002ED19
0x18002ef22  lea     rdx, [rbp+57h+var_9C]; unsigned int *
0x18002ef26  mov     rcx, rax; this
0x18002ef29  call    ??0CLoadMsi@@QEAA@AEAK@Z; CLoadMsi::CLoadMsi(ulong &)
0x18002ef2e  mov     ebx, [rbp+57h+var_9C]
0x18002ef31  mov     rdi, rax
0x18002ef34  mov     cs:qword_1800A2D58, rdi
0x18002ef3b  test    rdi, rdi
0x18002ef3e  jnz     short loc_18002EF63
0x18002ef40  test    ebx, ebx
0x18002ef42  jz      loc_18002ECDA
0x18002ef48  jmp     loc_18002ED68
0x18002ef4d  mov     edx, 8; uBytes
0x18002ef52  xor     ecx, ecx; uFlags
0x18002ef54  call    cs:__imp_LocalAlloc
0x18002ef5a  test    rax, rax
0x18002ef5d  jnz     short loc_18002EF22
0x18002ef5f  xor     edi, edi
0x18002ef61  jmp     short loc_18002EF34
0x18002ef63  test    ebx, ebx
0x18002ef65  jz      loc_18002ECDA
0x18002ef6b  test    rdi, rdi
0x18002ef6e  jz      short loc_18002EF81
0x18002ef70  mov     rcx, rdi; this
0x18002ef73  call    ??1CLoadMsi@@QEAA@XZ; CLoadMsi::~CLoadMsi(void)
0x18002ef78  mov     rcx, rdi; hMem
0x18002ef7b  call    cs:__imp_LocalFree
0x18002ef81  mov     cs:qword_1800A2D58, 0
0x18002ef8c  jmp     short loc_18002EF40
0x18002ef8e  mov     eax, 0Eh
0x18002ef93  jmp     loc_18002ED6A
0x18002ef98  mov     r9d, [rbp+57h+cbData]
0x18002ef9c  lea     rcx, [rbp+57h+cbData]
0x18002efa0  mov     [rsp+0D0h+phkResult], rcx
0x18002efa5  mov     r8, rax
0x18002efa8  mov     rax, cs:?pfnGetUserObjectInformationW@@3P6AHPEAXH0KPEAK@ZEA; int (*pfnGetUserObjectInformationW)(void *,int,void *,ulong,ulong *)
0x18002efaf  mov     rcx, rdi
0x18002efb2  mov     edx, 2
0x18002efb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002efbc  test    eax, eax
0x18002efbe  jnz     loc_18002EEF1
0x18002efc4  call    cs:__imp_GetLastError
0x18002efca  mov     rcx, cs:lpString2; hMem
0x18002efd1  mov     ebx, eax
0x18002efd3  call    cs:__imp_LocalFree
0x18002efd9  mov     cs:lpString2, 0
0x18002efe4  jmp     loc_18002EEF1
```
