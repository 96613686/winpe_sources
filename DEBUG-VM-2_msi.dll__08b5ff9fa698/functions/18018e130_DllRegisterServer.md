# DllRegisterServer

- ea: `0x18018e130`
- end: `0x18018e501`
- name: `DllRegisterServer`
- size: `977`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180022120`
- `0x18003c7e0`
- `0x180056144`
- `0x180184810`
- `0x18018483c`
- `0x18018e130`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18018e233`
- `ADVAPI32!RegCloseKey` at `0x18018e446`
- `ADVAPI32!RegCloseKey` at `0x18018e233`
- `ADVAPI32!RegCloseKey` at `0x18018e446`
- `ADVAPI32!RegSetValueExW` at `0x18018e200`
- `ADVAPI32!RegSetValueExW` at `0x18018e228`
- `ADVAPI32!RegSetValueExW` at `0x18018e3dd`
- `ADVAPI32!RegSetValueExW` at `0x18018e427`
- `ADVAPI32!RegSetValueExW` at `0x18018e200`
- `ADVAPI32!RegSetValueExW` at `0x18018e228`
- `ADVAPI32!RegSetValueExW` at `0x18018e3dd`
- `ADVAPI32!RegSetValueExW` at `0x18018e427`
- `KERNEL32!GetModuleFileNameW` at `0x18018e177`
- `KERNEL32!GetModuleFileNameW` at `0x18018e177`
- `KERNEL32!lstrlenW` at `0x18018e1d7`
- `KERNEL32!lstrlenW` at `0x18018e3b6`
- `KERNEL32!lstrlenW` at `0x18018e3fe`
- `KERNEL32!lstrlenW` at `0x18018e1d7`
- `KERNEL32!lstrlenW` at `0x18018e3b6`
- `KERNEL32!lstrlenW` at `0x18018e3fe`
- `RPCRT4!NdrDllRegisterProxy` at `0x18018e24e`
- `RPCRT4!NdrDllRegisterProxy` at `0x18018e24e`

## string_xrefs

- `0x18018e1c5`: `%SystemRoot%\system32\msimsg.dll`
- `0x18018e1a1`: `System\CurrentControlSet\Services\EventLog\Application\MsiInstaller`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  signed int ModuleFileNameW; // eax
  unsigned int v1; // r8d
  unsigned __int16 *v2; // r9
  int v3; // eax
  __int64 v4; // rbx
  wchar_t **v5; // rdi
  int v6; // eax
  HKEY v7; // rcx
  int v8; // eax
  LSTATUS v9; // eax
  int v11; // eax
  int v12; // ebx
  BYTE *lpData; // [rsp+20h] [rbp-E0h]
  __int64 cbData; // [rsp+28h] [rbp-D8h]
  struct _SECURITY_ATTRIBUTES *v15; // [rsp+30h] [rbp-D0h]
  BYTE Data[8]; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v18; // [rsp+60h] [rbp-A0h] BYREF
  int v19; // [rsp+68h] [rbp-98h] BYREF
  __int128 v20; // [rsp+6Ch] [rbp-94h]
  unsigned __int16 v21[80]; // [rsp+80h] [rbp-80h] BYREF

  word_180308206 = 0;
  v20 = 0;
  ModuleFileNameW = GetModuleFileNameW(g_hInstance, &Filename, 0x104u);
  if ( word_180308206 )
    return -2147467259;
  if ( ModuleFileNameW > 0 )
  {
    hKey = 0;
    if ( !MsiRegCreate64bitKey(
            HKEY_LOCAL_MACHINE,
            L"System\\CurrentControlSet\\Services\\EventLog\\Application\\MsiInstaller",
            v1,
            v2,
            (unsigned int)lpData,
            0x2001Fu,
            v15,
            &hKey,
            0) )
    {
      *(_DWORD *)Data = 7;
      v3 = lstrlenW(L"%SystemRoot%\\system32\\msimsg.dll");
      RegSetValueExW(hKey, L"EventMessageFile", 0, 2u, (const BYTE *)L"%SystemRoot%\\system32\\msimsg.dll", 2 * v3 + 2);
      RegSetValueExW(hKey, L"TypesSupported", 0, 4u, Data, 4u);
      RegCloseKey(hKey);
    }
  }
  v4 = NdrDllRegisterProxy(hProxyDll, (const ProxyFileInfo **)&aProxyFileList, &CLSID_PSFactoryBuffer) != 0;
  if ( (int)StringCchPrintfW(&qword_180307FB0, 0x28u, L"{%08lX-0000-0000-C000-000000000046}", 790672) < 0 )
    return -2147467259;
  if ( (int)StringCchPrintfW(&qword_180307F60, 0x28u, L"{%08lX-0000-0000-C000-000000000046}", 790557) < 0 )
    return -2147467259;
  v19 = 20;
  DllGetVersion(&v19);
  LODWORD(cbData) = DWORD2(v20);
  LODWORD(lpData) = DWORD1(v20);
  if ( (int)StringCchPrintfW(&qword_180307E40, 0x64u, L"%d.%d.%d", (unsigned int)v20, lpData, cbData) < 0
    || (int)StringCchPrintfW(&qword_180307DF0, 0x28u, L"{%08lX-0000-0000-C000-000000000046}", 790676) < 0
    || (int)StringCchPrintfW(&qword_180307F10, 0x28u, L"{%08lX-0000-0000-C000-000000000046}", 790674) < 0 )
  {
    return -2147467259;
  }
  v5 = &off_180269DF0;
  while ( *v5 )
  {
    if ( v5[1] && v5[2] )
    {
      if ( (int)StringCchPrintfW(v21, 0x50u, *v5) < 0 )
        return -2147467259;
      *(_QWORD *)Data = 0;
      if ( (unsigned int)((__int64 (__fastcall *)(unsigned __int64, unsigned __int16 *, _QWORD, _QWORD, _DWORD, int, _QWORD, BYTE *, _QWORD))RegCreateKeyAPI)(
                           0xFFFFFFFF80000000uLL,
                           v21,
                           0,
                           0,
                           0,
                           131103,
                           0,
                           Data,
                           0)
        || (v6 = lstrlenW(v5[2]), RegSetValueExW(*(HKEY *)Data, 0, 0, 1u, (const BYTE *)v5[2], 2 * v6 + 2)) )
      {
        LODWORD(v4) = v4 + 1;
      }
      v7 = *(HKEY *)Data;
      if ( *(_QWORD *)Data )
      {
        if ( v5[3] )
        {
          v8 = lstrlenW(v5[4]);
          v9 = RegSetValueExW(*(HKEY *)Data, v5[3], 0, 1u, (const BYTE *)v5[4], 2 * v8 + 2);
          v7 = *(HKEY *)Data;
          if ( v9 )
            LODWORD(v4) = v4 + 1;
        }
      }
      v5 += 5;
      if ( v7 )
        RegCloseKey(v7);
    }
  }
  if ( GetTestFlag(114) && (unsigned int)DllRegisterServerTest() )
    LODWORD(v4) = v4 + 1;
  if ( (_DWORD)v4 )
    return -2147220991;
  v18 = 0;
  v11 = ((__int64 (__fastcall *)(WCHAR *, __int64 *))OLEAUT32::LoadTypeLib)(&Filename, &v18);
  if ( v11 == -2147319784 )
    return 0;
  if ( v11 )
    return -2147220992;
  v12 = ((__int64 (__fastcall *)(__int64, WCHAR *, _QWORD))OLEAUT32::RegisterTypeLib)(v18, &Filename, 0);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  return v12 != 0 ? 0x80040200 : 0;
}

```

## disassembly

```asm
0x18018e130  push    rbp
0x18018e132  push    rbx
0x18018e133  push    rsi
0x18018e134  push    rdi
0x18018e135  push    r14
0x18018e137  lea     rbp, [rsp-30h]
0x18018e13c  sub     rsp, 130h
0x18018e143  mov     rax, cs:__security_cookie
0x18018e14a  xor     rax, rsp
0x18018e14d  mov     [rbp+50h+var_30], rax
0x18018e151  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hModule
0x18018e158  lea     rdx, Filename; lpFilename
0x18018e15f  xorps   xmm0, xmm0
0x18018e162  xor     esi, esi
0x18018e164  mov     r8d, 104h; nSize
0x18018e16a  mov     cs:word_180308206, si
0x18018e171  movdqu  [rsp+150h+var_E4], xmm0
0x18018e177  call    cs:__imp_GetModuleFileNameW
0x18018e17d  cmp     cs:word_180308206, si
0x18018e184  jnz     loc_18018E4E2
0x18018e18a  test    eax, eax
0x18018e18c  jle     loc_18018E239
0x18018e192  lea     rax, [rsp+150h+hKey]
0x18018e197  mov     [rsp+150h+var_110], rsi; unsigned int *
0x18018e19c  mov     [rsp+150h+var_118], rax; HKEY *
0x18018e1a1  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\Ev"...
0x18018e1a8  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x18018e1af  mov     dword ptr [rsp+150h+cbData], 2001Fh; unsigned int
0x18018e1b7  mov     [rsp+150h+hKey], rsi
0x18018e1bc  call    ?MsiRegCreate64bitKey@@YAKPEAUHKEY__@@PEBGKPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@Z; MsiRegCreate64bitKey(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x18018e1c1  test    eax, eax
0x18018e1c3  jnz     short loc_18018E239
0x18018e1c5  lea     rbx, Data; "%SystemRoot%\\system32\\msimsg.dll"
0x18018e1cc  mov     dword ptr [rsp+150h+Data], 7
0x18018e1d4  mov     rcx, rbx; lpString
0x18018e1d7  call    cs:__imp_lstrlenW
0x18018e1dd  mov     rcx, [rsp+150h+hKey]; hKey
0x18018e1e2  lea     r9d, [rsi+2]; dwType
0x18018e1e6  xor     r8d, r8d; Reserved
0x18018e1e9  lea     rdx, aEventmessagefi; "EventMessageFile"
0x18018e1f0  lea     eax, ds:2[rax*2]
0x18018e1f7  mov     dword ptr [rsp+150h+cbData], eax; cbData
0x18018e1fb  mov     [rsp+150h+lpData], rbx; lpData
0x18018e200  call    cs:__imp_RegSetValueExW
0x18018e206  mov     rcx, [rsp+150h+hKey]; hKey
0x18018e20b  lea     r9d, [rsi+4]; dwType
0x18018e20f  lea     rax, [rsp+150h+Data]
0x18018e214  mov     dword ptr [rsp+150h+cbData], r9d; cbData
0x18018e219  xor     r8d, r8d; Reserved
0x18018e21c  mov     [rsp+150h+lpData], rax; lpData
0x18018e221  lea     rdx, aTypessupported; "TypesSupported"
0x18018e228  call    cs:__imp_RegSetValueExW
0x18018e22e  mov     rcx, [rsp+150h+hKey]; hKey
0x18018e233  call    cs:__imp_RegCloseKey
0x18018e239  mov     rcx, cs:hProxyDll; hDll
0x18018e240  lea     r8, CLSID_PSFactoryBuffer; pclsid
0x18018e247  lea     rdx, aProxyFileList; pProxyFileList
0x18018e24e  call    cs:__imp_NdrDllRegisterProxy
0x18018e254  lea     rdi, a08lx00000000C0; "{%08lX-0000-0000-C000-000000000046}"
0x18018e25b  mov     r14d, 28h ; '('
0x18018e261  test    eax, eax
0x18018e263  lea     rcx, qword_180307FB0; unsigned __int16 *
0x18018e26a  mov     ebx, esi
0x18018e26c  mov     r9d, 0C1090h
0x18018e272  mov     r8, rdi; unsigned __int16 *
0x18018e275  mov     edx, r14d; unsigned __int64
0x18018e278  setnz   bl
0x18018e27b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18018e280  test    eax, eax
0x18018e282  js      loc_18018E4E2
0x18018e288  mov     r9d, 0C101Dh
0x18018e28e  lea     rcx, qword_180307F60; unsigned __int16 *
0x18018e295  mov     r8, rdi; unsigned __int16 *
0x18018e298  mov     edx, r14d; unsigned __int64
0x18018e29b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18018e2a0  test    eax, eax
0x18018e2a2  js      loc_18018E4E2
0x18018e2a8  lea     rcx, [rsp+150h+var_E8]
0x18018e2ad  mov     [rsp+150h+var_E8], 14h
0x18018e2b5  call    DllGetVersion
0x18018e2ba  mov     eax, dword ptr [rsp+150h+var_E4+8]
0x18018e2be  lea     r8, aDDD; "%d.%d.%d"
0x18018e2c5  mov     r9d, dword ptr [rsp+150h+var_E4]
0x18018e2ca  lea     edx, [r14+3Ch]; unsigned __int64
0x18018e2ce  mov     dword ptr [rsp+150h+cbData], eax
0x18018e2d2  lea     rcx, qword_180307E40; unsigned __int16 *
0x18018e2d9  mov     eax, dword ptr [rsp+150h+var_E4+4]
0x18018e2dd  mov     dword ptr [rsp+150h+lpData], eax
0x18018e2e1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18018e2e6  test    eax, eax
0x18018e2e8  js      loc_18018E4E2
0x18018e2ee  mov     r9d, 0C1094h
0x18018e2f4  lea     rcx, qword_180307DF0; unsigned __int16 *
0x18018e2fb  mov     r8, rdi; unsigned __int16 *
0x18018e2fe  mov     edx, r14d; unsigned __int64
0x18018e301  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18018e306  test    eax, eax
0x18018e308  js      loc_18018E4E2
0x18018e30e  mov     r9d, 0C1092h
0x18018e314  lea     rcx, qword_180307F10; unsigned __int16 *
0x18018e31b  mov     r8, rdi; unsigned __int16 *
0x18018e31e  mov     edx, r14d; unsigned __int64
0x18018e321  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18018e326  test    eax, eax
0x18018e328  js      loc_18018E4E2
0x18018e32e  lea     rdi, off_180269DF0; "CLSID\\%s\\InprocServer32"
0x18018e335  mov     r14d, 1
0x18018e33b  mov     r8, [rdi]; unsigned __int16 *
0x18018e33e  test    r8, r8
0x18018e341  jz      loc_18018E451
0x18018e347  mov     r9, [rdi+8]
0x18018e34b  test    r9, r9
0x18018e34e  jz      short loc_18018E33B
0x18018e350  cmp     [rdi+10h], rsi
0x18018e354  jz      short loc_18018E33B
0x18018e356  mov     edx, 50h ; 'P'; unsigned __int64
0x18018e35b  lea     rcx, [rbp+50h+var_D0]; unsigned __int16 *
0x18018e35f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18018e364  test    eax, eax
0x18018e366  js      loc_18018E4E2
0x18018e36c  mov     [rsp+150h+var_110], rsi
0x18018e371  lea     rax, [rsp+150h+Data]
0x18018e376  mov     [rsp+150h+var_118], rax
0x18018e37b  lea     rdx, [rbp+50h+var_D0]
0x18018e37f  mov     rax, cs:?RegCreateKeyAPI@@3P6AJPEAUHKEY__@@PEBGKPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@ZEA; long (*RegCreateKeyAPI)(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x18018e386  xor     r9d, r9d
0x18018e389  mov     [rsp+150h+var_120], rsi
0x18018e38e  xor     r8d, r8d
0x18018e391  mov     dword ptr [rsp+150h+cbData], 2001Fh
0x18018e399  mov     rcx, 0FFFFFFFF80000000h
0x18018e3a0  mov     dword ptr [rsp+150h+lpData], esi
0x18018e3a4  mov     qword ptr [rsp+150h+Data], rsi
0x18018e3a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018e3ae  test    eax, eax
0x18018e3b0  jnz     short loc_18018E3E7
0x18018e3b2  mov     rcx, [rdi+10h]; lpString
0x18018e3b6  call    cs:__imp_lstrlenW
0x18018e3bc  mov     rcx, qword ptr [rsp+150h+Data]; hKey
0x18018e3c1  mov     r9d, r14d; dwType
0x18018e3c4  xor     r8d, r8d; Reserved
0x18018e3c7  xor     edx, edx; lpValueName
0x18018e3c9  lea     eax, ds:2[rax*2]
0x18018e3d0  mov     dword ptr [rsp+150h+cbData], eax; cbData
0x18018e3d4  mov     rax, [rdi+10h]
0x18018e3d8  mov     [rsp+150h+lpData], rax; lpData
0x18018e3dd  call    cs:__imp_RegSetValueExW
0x18018e3e3  test    eax, eax
0x18018e3e5  jz      short loc_18018E3EA
0x18018e3e7  add     ebx, r14d
0x18018e3ea  mov     rcx, qword ptr [rsp+150h+Data]
0x18018e3ef  test    rcx, rcx
0x18018e3f2  jz      short loc_18018E439
0x18018e3f4  cmp     [rdi+18h], rsi
0x18018e3f8  jz      short loc_18018E439
0x18018e3fa  mov     rcx, [rdi+20h]; lpString
0x18018e3fe  call    cs:__imp_lstrlenW
0x18018e404  mov     rdx, [rdi+18h]; lpValueName
0x18018e408  mov     r9d, r14d; dwType
0x18018e40b  mov     rcx, qword ptr [rsp+150h+Data]; hKey
0x18018e410  xor     r8d, r8d; Reserved
0x18018e413  lea     eax, ds:2[rax*2]
0x18018e41a  mov     dword ptr [rsp+150h+cbData], eax; cbData
0x18018e41e  mov     rax, [rdi+20h]
0x18018e422  mov     [rsp+150h+lpData], rax; lpData
0x18018e427  call    cs:__imp_RegSetValueExW
0x18018e42d  mov     rcx, qword ptr [rsp+150h+Data]; hKey
0x18018e432  test    eax, eax
0x18018e434  jz      short loc_18018E439
0x18018e436  add     ebx, r14d
0x18018e439  add     rdi, 28h ; '('
0x18018e43d  test    rcx, rcx
0x18018e440  jz      loc_18018E33B
0x18018e446  call    cs:__imp_RegCloseKey
0x18018e44c  jmp     loc_18018E33B
0x18018e451  mov     ecx, 72h ; 'r'; int
0x18018e456  call    ?GetTestFlag@@YA_NH@Z; GetTestFlag(int)
0x18018e45b  test    al, al
0x18018e45d  jz      short loc_18018E46B
0x18018e45f  call    DllRegisterServerTest
0x18018e464  test    eax, eax
0x18018e466  jz      short loc_18018E46B
0x18018e468  add     ebx, r14d
0x18018e46b  test    ebx, ebx
0x18018e46d  jz      short loc_18018E476
0x18018e46f  mov     eax, 80040201h
0x18018e474  jmp     short loc_18018E4E7
0x18018e476  mov     rax, cs:?LoadTypeLib@OLEAUT32@@3P6AJPEBGPEAPEAUITypeLib@@@ZEA; long (*OLEAUT32::LoadTypeLib)(ushort const *,ITypeLib * *)
0x18018e47d  lea     rdx, [rsp+150h+var_F0]
0x18018e482  lea     rcx, Filename
0x18018e489  mov     [rsp+150h+var_F0], rsi
0x18018e48e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018e493  cmp     eax, 80028018h
0x18018e498  jnz     short loc_18018E49E
0x18018e49a  xor     eax, eax
0x18018e49c  jmp     short loc_18018E4E7
0x18018e49e  test    eax, eax
0x18018e4a0  jnz     short loc_18018E4DB
0x18018e4a2  mov     rcx, [rsp+150h+var_F0]
0x18018e4a7  lea     rdx, Filename
0x18018e4ae  mov     rax, cs:?RegisterTypeLib@OLEAUT32@@3P6AJPEAUITypeLib@@PEAG1@ZEA; long (*OLEAUT32::RegisterTypeLib)(ITypeLib *,ushort *,ushort *)
0x18018e4b5  xor     r8d, r8d
0x18018e4b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018e4bd  mov     rcx, [rsp+150h+var_F0]
0x18018e4c2  mov     ebx, eax
0x18018e4c4  mov     rdx, [rcx]
0x18018e4c7  mov     rax, [rdx+10h]
0x18018e4cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018e4d0  neg     ebx
0x18018e4d2  sbb     eax, eax
0x18018e4d4  and     eax, 80040200h
0x18018e4d9  jmp     short loc_18018E4E7
0x18018e4db  mov     eax, 80040200h
0x18018e4e0  jmp     short loc_18018E4E7
0x18018e4e2  mov     eax, 80004005h
0x18018e4e7  mov     rcx, [rbp+50h+var_30]
0x18018e4eb  xor     rcx, rsp; StackCookie
0x18018e4ee  call    __security_check_cookie
0x18018e4f3  add     rsp, 130h
0x18018e4fa  pop     r14
0x18018e4fc  pop     rdi
0x18018e4fd  pop     rsi
0x18018e4fe  pop     rbx
0x18018e4ff  pop     rbp
0x18018e500  retn
```
