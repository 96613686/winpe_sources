# RunCommands(ushort const *,ushort const *,ushort const *,ulong,int)

- ea: `0x180009c14`
- end: `0x18000a0b8`
- name: `?RunCommands@@YAJPEBG00KH@Z`
- size: `1188`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, LPCWSTR lpAppName, const unsigned __int16 *, char, int)`
- caller_count: `1`
- callee_count: `16`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x18000a0c0`

## callees

- `0x1800022bc`
- `0x1800035c8`
- `0x1800068ac`
- `0x180006928`
- `0x180006e54`
- `0x1800080c8`
- `0x1800082f0`
- `0x180008644`
- `0x180008a6c`
- `0x180009c14`
- `0x18000ae68`
- `0x18000c574`
- `0x1800198d0`
- `0x18001a688`
- `0x18001b294`
- `0x18001b980`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180009c86`
- `KERNEL32!GetLastError` at `0x180009ff7`
- `KERNEL32!GetLastError` at `0x18000a00e`
- `KERNEL32!GetLastError` at `0x180009c86`
- `KERNEL32!GetLastError` at `0x180009ff7`
- `KERNEL32!GetLastError` at `0x18000a00e`
- `KERNEL32!LocalFree` at `0x180009fd9`
- `KERNEL32!LocalFree` at `0x18000a066`
- `KERNEL32!LocalFree` at `0x18000a074`
- `KERNEL32!LocalFree` at `0x180009fd9`
- `KERNEL32!LocalFree` at `0x18000a066`
- `KERNEL32!LocalFree` at `0x18000a074`
- `KERNEL32!LocalAlloc` at `0x180009c78`
- `KERNEL32!LocalAlloc` at `0x180009c78`
- `KERNEL32!FormatMessageW` at `0x18000a038`
- `KERNEL32!FormatMessageW` at `0x18000a038`
- `ADVAPI32!RegCreateKeyExW` at `0x180009d7e`
- `ADVAPI32!RegCreateKeyExW` at `0x180009e0e`
- `ADVAPI32!RegCreateKeyExW` at `0x180009d7e`
- `ADVAPI32!RegCreateKeyExW` at `0x180009e0e`
- `ADVAPI32!RegCloseKey` at `0x180009e95`
- `ADVAPI32!RegCloseKey` at `0x180009f16`
- `ADVAPI32!RegCloseKey` at `0x180009e95`
- `ADVAPI32!RegCloseKey` at `0x180009f16`
- `ADVAPI32!RegSetValueExW` at `0x180009e7b`
- `ADVAPI32!RegSetValueExW` at `0x180009efc`
- `ADVAPI32!RegSetValueExW` at `0x180009e7b`
- `ADVAPI32!RegSetValueExW` at `0x180009efc`

## string_xrefs

- `0x180009c54`: `RunCommands: Sec=%1\n`
- `0x18000a07d`: `RunCommands: Sec=%1 End hr=0x%2!x!\n`

## pseudocode

```c
__int64 __fastcall RunCommands(LPCWSTR lpFileName, LPCWSTR lpAppName, const unsigned __int16 *a3, char a4, int a5)
{
  const WCHAR *v5; // rdi
  unsigned int v6; // r12d
  const unsigned __int16 *v8; // rsi
  unsigned __int16 *v10; // r14
  signed int v11; // eax
  unsigned int v12; // ebx
  int TranslatedLine; // eax
  BYTE *v14; // rdi
  int v15; // eax
  const WCHAR *v16; // rdx
  __int64 v17; // rax
  __int64 v18; // rax
  __int16 v19; // r11
  const WCHAR *v20; // rsi
  signed int LastError; // eax
  DWORD v22; // eax
  ULONG dwOptions; // [rsp+20h] [rbp-E0h]
  int dwOptionsa; // [rsp+20h] [rbp-E0h]
  int dwOptionsb; // [rsp+20h] [rbp-E0h]
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  const unsigned __int16 *v29; // [rsp+60h] [rbp-A0h]
  LPCWSTR v30; // [rsp+68h] [rbp-98h]
  WCHAR SubKey[512]; // [rsp+70h] [rbp-90h] BYREF

  v5 = lpFileName;
  v30 = lpFileName;
  v6 = 0;
  v29 = a3;
  phkResult = 0;
  v8 = a3;
  AdvWriteToLog(L"RunCommands: Sec=%1\r\n");
  v10 = (unsigned __int16 *)LocalAlloc(0x40u, 0x800u);
  if ( v10 )
  {
    v12 = 0;
    while ( 1 )
    {
      TranslatedLine = GetTranslatedLine(v5, lpAppName, v6, (unsigned __int16 **)&phkResult, 0);
      v14 = (BYTE *)phkResult;
      if ( TranslatedLine < 0 || !phkResult )
        break;
      if ( (a4 & 4) != 0 && (InternalNeedReboot(0, ctx) || a5) )
      {
        hKey = 0;
        phkResult = 0;
        if ( dword_180025198 == 989 && (unsigned int)UseRunOnceEx() )
        {
          v15 = 1;
          dword_180032300 = 1;
        }
        else
        {
          v15 = dword_180032300;
        }
        v16 = L"Software\\Microsoft\\Windows\\CurrentVersion\\RunOnce";
        if ( v15 )
          v16 = L"Software\\Microsoft\\Windows\\CurrentVersion\\RunOnceEx";
        if ( !RegCreateKeyExW(HKEY_LOCAL_MACHINE, v16, 0, 0, 0, 0x2001Fu, 0, &hKey, 0) )
        {
          if ( dword_180032300 )
          {
            if ( dword_180025198 == 989 )
              GetNextRunOnceExSubKey(hKey, SubKey, 0x200u, &dword_180025198);
            else
              StringCchPrintfW(SubKey, 0x200u, L"%d");
            if ( !RegCreateKeyExW(hKey, SubKey, 0, 0, 0, 0x2001Fu, 0, &phkResult, 0) )
            {
              dwOptionsa = dword_1800322FC++;
              GetNextRunOnceValName(phkResult, L"%03d", SubKey, 0x200u, dwOptionsa);
              v17 = -1;
              do
                ++v17;
              while ( *(_WORD *)&v14[2 * v17] );
              RegSetValueExW(phkResult, SubKey, 0, 1u, v14, 2 * v17 + 2);
              AdvWriteToLog(L"RunOnceEx Entry: %1\r\n", v14);
              RegCloseKey(phkResult);
            }
          }
          else
          {
            dwOptionsb = dword_1800322FC++;
            GetNextRunOnceValName(hKey, L"IExpressRegOCX%d", SubKey, 0x200u, dwOptionsb);
            v18 = -1;
            do
              ++v18;
            while ( *(_WORD *)&v14[2 * v18] );
            RegSetValueExW(hKey, SubKey, 0, 1u, v14, 2 * v18 + 2);
            AdvWriteToLog(L"RunOnce Entry: %1\r\n", v14);
          }
          RegCloseKey(hKey);
          v12 = 3010;
        }
      }
      else
      {
        if ( !IsFullPath((const unsigned __int16 *)v14) )
        {
          StringCchCopyW(v10, 0x400u, v8);
          v20 = (const WCHAR *)v14;
          if ( v14
            && !(unsigned int)PathIsUnc2((unsigned __int16 *)v14)
            && !IsExtendedLengthDosDevicePath((const unsigned __int16 *)v14)
            && *(_WORD *)v14 == 92 )
          {
            do
              ++v20;
            while ( *v20 == 92 );
          }
          PathCchCombineEx(v10, 0x400u, v10, v20, dwOptions);
          v8 = v29;
          v19 = 0;
        }
        if ( (*v10 == v19 || (unsigned int)LaunchAndWait(v10, 0, 0, 0xFFFFFFFF, a4) == -2147467259)
          && (unsigned int)LaunchAndWait((const unsigned __int16 *)v14, 0, 0, 0xFFFFFFFF, a4) == -2147467259 )
        {
          LastError = GetLastError();
          v12 = LastError;
          if ( LastError > 0 )
            v12 = (unsigned __int16)LastError | 0x80070000;
          v22 = GetLastError();
          FormatMessageW(0x1000u, 0, v22, 0, SubKey, 0x400u, 0);
          MsgBox2Param(hWnd, 0x476u, (const unsigned __int16 *)v14, SubKey, 0x10u, 0);
          break;
        }
      }
      LocalFree(v14);
      v5 = v30;
      phkResult = 0;
      ++v6;
      *v10 = 0;
    }
    LocalFree(v10);
    if ( v14 )
      LocalFree(v14);
  }
  else
  {
    v11 = GetLastError();
    v12 = v11;
    if ( v11 > 0 )
      v12 = (unsigned __int16)v11 | 0x80070000;
  }
  AdvWriteToLog(L"RunCommands: Sec=%1 End hr=0x%2!x!\r\n", lpAppName, v12);
  return v12;
}

```

## disassembly

```asm
0x180009c14  mov     [rsp-8+arg_18], rbx
0x180009c19  push    rbp
0x180009c1a  push    rsi
0x180009c1b  push    rdi
0x180009c1c  push    r12
0x180009c1e  push    r13
0x180009c20  push    r14
0x180009c22  push    r15
0x180009c24  lea     rbp, [rsp-380h]
0x180009c2c  sub     rsp, 480h
0x180009c33  mov     rax, cs:__security_cookie
0x180009c3a  xor     rax, rsp
0x180009c3d  mov     [rbp+3B0h+var_40], rax
0x180009c44  mov     rdi, rcx
0x180009c47  mov     [rsp+4B0h+var_448], rcx
0x180009c4c  xor     r12d, r12d
0x180009c4f  mov     [rsp+4B0h+var_450], r8
0x180009c54  lea     rcx, aRuncommandsSec; "RunCommands: Sec=%1\r\n"
0x180009c5b  mov     [rsp+4B0h+var_460], r12
0x180009c60  mov     r13d, r9d
0x180009c63  mov     rsi, r8
0x180009c66  mov     r15, rdx
0x180009c69  call    ?AdvWriteToLog@@YAXPEBGZZ; AdvWriteToLog(ushort const *,...)
0x180009c6e  mov     edx, 800h; uBytes
0x180009c73  lea     ecx, [r12+40h]; uFlags
0x180009c78  call    cs:__imp_LocalAlloc
0x180009c7e  mov     r14, rax
0x180009c81  test    rax, rax
0x180009c84  jnz     short loc_180009CA4
0x180009c86  call    cs:__imp_GetLastError
0x180009c8c  mov     ebx, eax
0x180009c8e  test    eax, eax
0x180009c90  jle     loc_18000A07A
0x180009c96  movzx   ebx, ax
0x180009c99  or      ebx, 80070000h
0x180009c9f  jmp     loc_18000A07A
0x180009ca4  mov     ebx, r12d
0x180009ca7  lea     r9, [rsp+4B0h+var_460]; unsigned __int16 **
0x180009cac  mov     qword ptr [rsp+4B0h+dwOptions], 0; unsigned int *
0x180009cb5  mov     r8d, r12d; unsigned int
0x180009cb8  mov     rdx, r15; lpAppName
0x180009cbb  mov     rcx, rdi; lpFileName
0x180009cbe  call    ?GetTranslatedLine@@YAJPEBG0KPEAPEAGPEAK@Z; GetTranslatedLine(ushort const *,ushort const *,ulong,ushort * *,ulong *)
0x180009cc3  mov     rdi, [rsp+4B0h+var_460]
0x180009cc8  xor     r11d, r11d
0x180009ccb  test    eax, eax
0x180009ccd  js      loc_18000A063
0x180009cd3  test    rdi, rdi
0x180009cd6  jz      loc_18000A063
0x180009cdc  test    r13b, 4
0x180009ce0  jz      loc_180009F26
0x180009ce6  movzx   edx, cs:?ctx@@3UADVCONTEXTW@@A; unsigned __int16
0x180009ced  xor     ecx, ecx; unsigned int
0x180009cef  call    ?InternalNeedReboot@@YAHKG@Z; InternalNeedReboot(ulong,ushort)
0x180009cf4  xor     r11d, r11d
0x180009cf7  test    eax, eax
0x180009cf9  jnz     short loc_180009D08
0x180009cfb  cmp     [rbp+3B0h+arg_20], r11d
0x180009d02  jz      loc_180009F26
0x180009d08  cmp     cs:dword_180025198, 3DDh
0x180009d12  mov     [rsp+4B0h+hKey], r11
0x180009d17  mov     [rsp+4B0h+var_460], r11
0x180009d1c  jnz     short loc_180009D36
0x180009d1e  call    ?UseRunOnceEx@@YAHXZ; UseRunOnceEx(void)
0x180009d23  xor     r11d, r11d
0x180009d26  test    eax, eax
0x180009d28  jz      short loc_180009D36
0x180009d2a  lea     eax, [r11+1]
0x180009d2e  mov     cs:dword_180032300, eax
0x180009d34  jmp     short loc_180009D3C
0x180009d36  mov     eax, cs:dword_180032300
0x180009d3c  mov     [rsp+4B0h+lpdwDisposition], r11; lpdwDisposition
0x180009d41  lea     rcx, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180009d48  test    eax, eax
0x180009d4a  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180009d51  lea     rax, [rsp+4B0h+hKey]
0x180009d56  mov     [rsp+4B0h+phkResult], rax; phkResult
0x180009d5b  cmovnz  rdx, rcx; lpSubKey
0x180009d5f  mov     [rsp+4B0h+lpSecurityAttributes], r11; lpSecurityAttributes
0x180009d64  xor     r9d, r9d; lpClass
0x180009d67  mov     [rsp+4B0h+samDesired], 2001Fh; samDesired
0x180009d6f  xor     r8d, r8d; Reserved
0x180009d72  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180009d79  mov     [rsp+4B0h+dwOptions], r11d; dwOptions
0x180009d7e  call    cs:__imp_RegCreateKeyExW
0x180009d84  test    eax, eax
0x180009d86  jnz     loc_180009FD6
0x180009d8c  xor     ebx, ebx
0x180009d8e  cmp     cs:dword_180032300, ebx
0x180009d94  jz      loc_180009E9D
0x180009d9a  mov     r9d, cs:dword_180025198
0x180009da1  cmp     r9d, 3DDh
0x180009da8  jnz     short loc_180009DC8
0x180009daa  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180009daf  lea     r9, dword_180025198; int *
0x180009db6  mov     r8d, 200h; unsigned int
0x180009dbc  lea     rdx, [rsp+4B0h+SubKey]; unsigned __int16 *
0x180009dc1  call    ?GetNextRunOnceExSubKey@@YAXPEAUHKEY__@@PEAGKPEAH@Z; GetNextRunOnceExSubKey(HKEY__ *,ushort *,ulong,int *)
0x180009dc6  jmp     short loc_180009DDE
0x180009dc8  lea     r8, aD; "%d"
0x180009dcf  mov     edx, 200h; unsigned __int64
0x180009dd4  lea     rcx, [rsp+4B0h+SubKey]; unsigned __int16 *
0x180009dd9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180009dde  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180009de3  lea     rax, [rsp+4B0h+var_460]
0x180009de8  mov     [rsp+4B0h+lpdwDisposition], rbx; lpdwDisposition
0x180009ded  lea     rdx, [rsp+4B0h+SubKey]; lpSubKey
0x180009df2  mov     [rsp+4B0h+phkResult], rax; phkResult
0x180009df7  xor     r9d, r9d; lpClass
0x180009dfa  mov     [rsp+4B0h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x180009dff  xor     r8d, r8d; Reserved
0x180009e02  mov     [rsp+4B0h+samDesired], 2001Fh; samDesired
0x180009e0a  mov     [rsp+4B0h+dwOptions], ebx; dwOptions
0x180009e0e  call    cs:__imp_RegCreateKeyExW
0x180009e14  test    eax, eax
0x180009e16  jnz     loc_180009F11
0x180009e1c  mov     ecx, cs:dword_1800322FC
0x180009e22  lea     r8, [rsp+4B0h+SubKey]; unsigned __int16 *
0x180009e27  mov     [rsp+4B0h+dwOptions], ecx; int
0x180009e2b  lea     rdx, a03d; "%03d"
0x180009e32  mov     r9d, 200h; unsigned int
0x180009e38  lea     eax, [rcx+1]
0x180009e3b  mov     rcx, [rsp+4B0h+var_460]; hKey
0x180009e40  mov     cs:dword_1800322FC, eax
0x180009e46  call    ?GetNextRunOnceValName@@YAXPEAUHKEY__@@PEBGPEAGKH@Z; GetNextRunOnceValName(HKEY__ *,ushort const *,ushort *,ulong,int)
0x180009e4b  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009e4f  inc     rax
0x180009e52  cmp     [rdi+rax*2], bx
0x180009e56  jnz     short loc_180009E4F
0x180009e58  mov     rcx, [rsp+4B0h+var_460]; hKey
0x180009e5d  lea     eax, ds:2[rax*2]
0x180009e64  mov     [rsp+4B0h+samDesired], eax; cbData
0x180009e68  lea     rdx, [rsp+4B0h+SubKey]; lpValueName
0x180009e6d  mov     r9d, 1; dwType
0x180009e73  mov     qword ptr [rsp+4B0h+dwOptions], rdi; lpData
0x180009e78  xor     r8d, r8d; Reserved
0x180009e7b  call    cs:__imp_RegSetValueExW
0x180009e81  mov     rdx, rdi
0x180009e84  lea     rcx, aRunonceexEntry; "RunOnceEx Entry: %1\r\n"
0x180009e8b  call    ?AdvWriteToLog@@YAXPEBGZZ; AdvWriteToLog(ushort const *,...)
0x180009e90  mov     rcx, [rsp+4B0h+var_460]; hKey
0x180009e95  call    cs:__imp_RegCloseKey
0x180009e9b  jmp     short loc_180009F11
0x180009e9d  mov     ecx, cs:dword_1800322FC
0x180009ea3  lea     r8, [rsp+4B0h+SubKey]; unsigned __int16 *
0x180009ea8  mov     [rsp+4B0h+dwOptions], ecx; int
0x180009eac  lea     rdx, aIexpressregocx; "IExpressRegOCX%d"
0x180009eb3  mov     r9d, 200h; unsigned int
0x180009eb9  lea     eax, [rcx+1]
0x180009ebc  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180009ec1  mov     cs:dword_1800322FC, eax
0x180009ec7  call    ?GetNextRunOnceValName@@YAXPEAUHKEY__@@PEBGPEAGKH@Z; GetNextRunOnceValName(HKEY__ *,ushort const *,ushort *,ulong,int)
0x180009ecc  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009ed0  inc     rax
0x180009ed3  cmp     [rdi+rax*2], bx
0x180009ed7  jnz     short loc_180009ED0
0x180009ed9  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180009ede  lea     eax, ds:2[rax*2]
0x180009ee5  mov     [rsp+4B0h+samDesired], eax; cbData
0x180009ee9  lea     rdx, [rsp+4B0h+SubKey]; lpValueName
0x180009eee  mov     r9d, 1; dwType
0x180009ef4  mov     qword ptr [rsp+4B0h+dwOptions], rdi; lpData
0x180009ef9  xor     r8d, r8d; Reserved
0x180009efc  call    cs:__imp_RegSetValueExW
0x180009f02  mov     rdx, rdi
0x180009f05  lea     rcx, aRunonceEntry1; "RunOnce Entry: %1\r\n"
0x180009f0c  call    ?AdvWriteToLog@@YAXPEBGZZ; AdvWriteToLog(ushort const *,...)
0x180009f11  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180009f16  call    cs:__imp_RegCloseKey
0x180009f1c  mov     ebx, 0BC2h
0x180009f21  jmp     loc_180009FD6
0x180009f26  mov     rcx, rdi; unsigned __int16 *
0x180009f29  call    ?IsFullPath@@YAHPEBG@Z; IsFullPath(ushort const *)
0x180009f2e  test    eax, eax
0x180009f30  jnz     short loc_180009F96
0x180009f32  mov     r8, rsi; unsigned __int16 *
0x180009f35  mov     edx, 400h; unsigned __int64
0x180009f3a  mov     rcx, r14; unsigned __int16 *
0x180009f3d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180009f42  mov     rsi, rdi
0x180009f45  test    rdi, rdi
0x180009f48  jz      short loc_180009F7B
0x180009f4a  lea     r8, IsBackslash
0x180009f51  xor     edx, edx
0x180009f53  mov     rcx, rdi; unsigned __int16 *
0x180009f56  call    PathIsUnc2
0x180009f5b  test    eax, eax
0x180009f5d  jnz     short loc_180009F7B
0x180009f5f  mov     rcx, rdi; unsigned __int16 *
0x180009f62  call    ?IsExtendedLengthDosDevicePath@@YA_NPEBG@Z; IsExtendedLengthDosDevicePath(ushort const *)
0x180009f67  test    al, al
0x180009f69  jnz     short loc_180009F7B
0x180009f6b  cmp     word ptr [rdi], 5Ch ; '\'
0x180009f6f  jnz     short loc_180009F7B
0x180009f71  add     rsi, 2
0x180009f75  cmp     word ptr [rsi], 5Ch ; '\'
0x180009f79  jz      short loc_180009F71
0x180009f7b  mov     r9, rsi; pszMore
0x180009f7e  mov     r8, r14; pszPathIn
0x180009f81  mov     edx, 400h; cchPathOut
0x180009f86  mov     rcx, r14; pszPathOut
0x180009f89  call    PathCchCombineEx
0x180009f8e  mov     rsi, [rsp+4B0h+var_450]
0x180009f93  xor     r11d, r11d
0x180009f96  cmp     [r14], r11w
0x180009f9a  jz      short loc_180009FB9
0x180009f9c  or      r9d, 0FFFFFFFFh; unsigned int
0x180009fa0  mov     [rsp+4B0h+dwOptions], r13d; unsigned int
0x180009fa5  xor     r8d, r8d; void **
0x180009fa8  xor     edx, edx; lpCurrentDirectory
0x180009faa  mov     rcx, r14; unsigned __int16 *
0x180009fad  call    ?LaunchAndWait@@YAJPEBG0PEAPEAXKK@Z; LaunchAndWait(ushort const *,ushort const *,void * *,ulong,ulong)
0x180009fb2  cmp     eax, 80004005h
0x180009fb7  jnz     short loc_180009FD6
0x180009fb9  or      r9d, 0FFFFFFFFh; unsigned int
0x180009fbd  mov     [rsp+4B0h+dwOptions], r13d; unsigned int
0x180009fc2  xor     r8d, r8d; void **
0x180009fc5  xor     edx, edx; lpCurrentDirectory
0x180009fc7  mov     rcx, rdi; unsigned __int16 *
0x180009fca  call    ?LaunchAndWait@@YAJPEBG0PEAPEAXKK@Z; LaunchAndWait(ushort const *,ushort const *,void * *,ulong,ulong)
0x180009fcf  cmp     eax, 80004005h
0x180009fd4  jz      short loc_180009FF7
0x180009fd6  mov     rcx, rdi; hMem
0x180009fd9  call    cs:__imp_LocalFree
0x180009fdf  mov     rdi, [rsp+4B0h+var_448]
0x180009fe4  xor     eax, eax
0x180009fe6  mov     [rsp+4B0h+var_460], rax
0x180009feb  inc     r12d
0x180009fee  mov     [r14], ax
0x180009ff2  jmp     loc_180009CA7
0x180009ff7  call    cs:__imp_GetLastError
0x180009ffd  xor     esi, esi
0x180009fff  mov     ebx, eax
0x18000a001  test    eax, eax
0x18000a003  jle     short loc_18000A00E
0x18000a005  movzx   ebx, ax
0x18000a008  or      ebx, 80070000h
0x18000a00e  call    cs:__imp_GetLastError
0x18000a014  mov     [rsp+4B0h+lpSecurityAttributes], rsi; Arguments
0x18000a019  xor     r9d, r9d; dwLanguageId
0x18000a01c  mov     r8d, eax; dwMessageId
0x18000a01f  mov     [rsp+4B0h+samDesired], 400h; nSize
0x18000a027  lea     rax, [rsp+4B0h+SubKey]
0x18000a02c  xor     edx, edx; lpSource
0x18000a02e  mov     ecx, 1000h; dwFlags
0x18000a033  mov     qword ptr [rsp+4B0h+dwOptions], rax; lpBuffer
0x18000a038  call    cs:__imp_FormatMessageW
0x18000a03e  mov     rcx, cs:hWnd; hWnd
0x18000a045  lea     r9, [rsp+4B0h+SubKey]; unsigned __int16 *
0x18000a04a  mov     r8, rdi; unsigned __int16 *
0x18000a04d  mov     [rsp+4B0h+samDesired], esi; unsigned int
0x18000a051  mov     edx, 476h; uID
0x18000a056  mov     [rsp+4B0h+dwOptions], 10h; unsigned int
0x18000a05e  call    ?MsgBox2Param@@YAHPEAUHWND__@@IPEBG1II@Z; MsgBox2Param(HWND__ *,uint,ushort const *,ushort const *,uint,uint)
0x18000a063  mov     rcx, r14; hMem
0x18000a066  call    cs:__imp_LocalFree
0x18000a06c  test    rdi, rdi
0x18000a06f  jz      short loc_18000A07A
0x18000a071  mov     rcx, rdi; hMem
0x18000a074  call    cs:__imp_LocalFree
0x18000a07a  mov     r8d, ebx
0x18000a07d  lea     rcx, aRuncommandsSec_0; "RunCommands: Sec=%1 End hr=0x%2!x!\r\n"
0x18000a084  mov     rdx, r15
0x18000a087  call    ?AdvWriteToLog@@YAXPEBGZZ; AdvWriteToLog(ushort const *,...)
0x18000a08c  mov     eax, ebx
0x18000a08e  mov     rcx, [rbp+3B0h+var_40]
0x18000a095  xor     rcx, rsp; StackCookie
0x18000a098  call    __security_check_cookie
0x18000a09d  mov     rbx, [rsp+4B0h+arg_18]
0x18000a0a5  add     rsp, 480h
0x18000a0ac  pop     r15
0x18000a0ae  pop     r14
0x18000a0b0  pop     r13
0x18000a0b2  pop     r12
0x18000a0b4  pop     rdi
0x18000a0b5  pop     rsi
0x18000a0b6  pop     rbp
0x18000a0b7  retn
```
