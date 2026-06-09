# CheckAttachDebugger(void)

- ea: `0x140018ab4`
- end: `0x140018ccd`
- name: `?CheckAttachDebugger@@YAXXZ`
- size: `537`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140019374`

## callees

- `0x140002470`
- `0x1400030a8`
- `0x140005468`
- `0x14000b540`
- `0x14001444c`
- `0x140014474`
- `0x140018ab4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140018b53`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140018b53`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140018caf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140018caf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140018b0d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140018b0d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140018b9b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140018b9b`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x140018c60`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x140018c60`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140018c70`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140018c70`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140018c80`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140018c90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140018c80`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140018c90`

## pseudocode

```c
void CheckAttachDebugger(void)
{
  HKEY *v0; // rax
  LSTATUS v1; // eax
  HKEY v2; // rcx
  unsigned int ValueW; // eax
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  HKEY hkey; // [rsp+50h] [rbp-B0h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp-A8h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+60h] [rbp-A0h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+80h] [rbp-80h] BYREF
  _BYTE pvData[528]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR CommandLine[264]; // [rsp+300h] [rbp+200h] BYREF

  pcbData = 0;
  hkey = 0;
  v0 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hkey);
  v1 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Hangs",
         0,
         0x20119u,
         v0);
  v2 = hkey;
  if ( !v1 )
  {
    pcbData = 520;
    ValueW = RegGetValueW(hkey, 0, L"Debugger", 2u, 0, pvData, &pcbData);
    if ( ValueW )
    {
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_35a6bf14758d33cd61dd1b0f627037ef_Traceguids, ValueW);
      }
    }
    else
    {
      LODWORD(phkResult) = GetCurrentProcessId();
      if ( (int)StringCchPrintfW(CommandLine, 0x104u, L"%s %u", pvData, phkResult) >= 0 )
      {
        if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_35a6bf14758d33cd61dd1b0f627037ef_Traceguids);
        }
        memset_0(&StartupInfo.cb + 1, 0, 0x64u);
        StartupInfo.cb = 104;
        memset(&ProcessInformation, 0, sizeof(ProcessInformation));
        if ( CreateProcessW(0, CommandLine, 0, 0, 0, 0, 0, 0, &StartupInfo, &ProcessInformation) )
          Sleep(0x1388u);
        if ( ProcessInformation.hProcess )
          CloseHandle(ProcessInformation.hProcess);
        if ( ProcessInformation.hThread )
          CloseHandle(ProcessInformation.hThread);
        memset(&ProcessInformation, 0, sizeof(ProcessInformation));
      }
    }
    v2 = hkey;
  }
  if ( v2 )
    RegCloseKey(v2);
}

```

## disassembly

```asm
0x140018ab4  push    rbp
0x140018ab6  lea     rbp, [rsp-420h]
0x140018abe  sub     rsp, 520h
0x140018ac5  mov     rax, cs:__security_cookie
0x140018acc  xor     rax, rsp
0x140018acf  mov     [rbp+420h+var_10], rax
0x140018ad6  lea     rcx, [rsp+520h+hkey]
0x140018adb  mov     [rsp+520h+var_4C8], 0
0x140018ae3  mov     [rsp+520h+hkey], 0
0x140018aec  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x140018af1  mov     r9d, 20119h; samDesired
0x140018af7  mov     [rsp+520h+phkResult], rax; phkResult
0x140018afc  xor     r8d, r8d; ulOptions
0x140018aff  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Windows\\Windows E"...
0x140018b06  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140018b0d  call    cs:__imp_RegOpenKeyExW
0x140018b13  mov     rcx, [rsp+520h+hkey]; hkey
0x140018b18  test    eax, eax
0x140018b1a  jnz     loc_140018CAA
0x140018b20  lea     rax, [rsp+520h+var_4C8]
0x140018b25  mov     [rsp+520h+var_4C8], 208h
0x140018b2d  mov     [rsp+520h+pcbData], rax; pcbData
0x140018b32  lea     r8, Value; "Debugger"
0x140018b39  lea     rax, [rbp+420h+var_430]
0x140018b3d  mov     r9d, 2; dwFlags
0x140018b43  mov     [rsp+520h+pvData], rax; pvData
0x140018b48  xor     edx, edx; lpSubKey
0x140018b4a  mov     [rsp+520h+phkResult], 0; pdwType
0x140018b53  call    cs:__imp_RegGetValueW
0x140018b59  test    eax, eax
0x140018b5b  jz      short loc_140018B9B
0x140018b5d  mov     rcx, cs:WPP_GLOBAL_Control
0x140018b64  lea     rdx, WPP_GLOBAL_Control
0x140018b6b  cmp     rcx, rdx
0x140018b6e  jz      loc_140018CA5
0x140018b74  test    byte ptr [rcx+1Ch], 1
0x140018b78  jz      loc_140018CA5
0x140018b7e  mov     rcx, [rcx+10h]
0x140018b82  lea     r8, WPP_35a6bf14758d33cd61dd1b0f627037ef_Traceguids
0x140018b89  mov     edx, 0Dh
0x140018b8e  mov     r9d, eax
0x140018b91  call    WPP_SF_d
0x140018b96  jmp     loc_140018CA5
0x140018b9b  call    cs:__imp_GetCurrentProcessId
0x140018ba1  lea     r9, [rbp+420h+var_430]
0x140018ba5  mov     edx, 104h; unsigned __int64
0x140018baa  lea     r8, aSU; "%s %u"
0x140018bb1  mov     dword ptr [rsp+520h+phkResult], eax
0x140018bb5  lea     rcx, [rbp+420h+CommandLine]; wchar_t *
0x140018bbc  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x140018bc1  test    eax, eax
0x140018bc3  js      loc_140018CA5
0x140018bc9  mov     rcx, cs:WPP_GLOBAL_Control
0x140018bd0  lea     rdx, WPP_GLOBAL_Control
0x140018bd7  cmp     rcx, rdx
0x140018bda  jz      short loc_140018BF7
0x140018bdc  test    byte ptr [rcx+1Ch], 4
0x140018be0  jz      short loc_140018BF7
0x140018be2  mov     rcx, [rcx+10h]
0x140018be6  lea     r8, WPP_35a6bf14758d33cd61dd1b0f627037ef_Traceguids
0x140018bed  mov     edx, 0Eh
0x140018bf2  call    WPP_SF_
0x140018bf7  xor     edx, edx; Val
0x140018bf9  lea     rcx, [rbp+420h+StartupInfo+4]; void *
0x140018bfd  lea     r8d, [rdx+64h]; Size
0x140018c01  call    memset_0
0x140018c06  xor     eax, eax
0x140018c08  mov     [rbp+420h+StartupInfo.cb], 68h ; 'h'
0x140018c0f  mov     qword ptr [rsp+520h+ProcessInformation.dwProcessId], rax
0x140018c14  lea     rdx, [rbp+420h+CommandLine]; lpCommandLine
0x140018c1b  lea     rax, [rsp+520h+ProcessInformation]
0x140018c20  xorps   xmm0, xmm0
0x140018c23  mov     [rsp+520h+lpProcessInformation], rax; lpProcessInformation
0x140018c28  xor     r9d, r9d; lpThreadAttributes
0x140018c2b  lea     rax, [rbp+420h+StartupInfo]
0x140018c2f  xor     r8d, r8d; lpProcessAttributes
0x140018c32  mov     [rsp+520h+lpStartupInfo], rax; lpStartupInfo
0x140018c37  xor     ecx, ecx; lpApplicationName
0x140018c39  mov     [rsp+520h+lpCurrentDirectory], 0; lpCurrentDirectory
0x140018c42  mov     [rsp+520h+pcbData], 0; lpEnvironment
0x140018c4b  mov     dword ptr [rsp+520h+pvData], 0; dwCreationFlags
0x140018c53  mov     dword ptr [rsp+520h+phkResult], 0; bInheritHandles
0x140018c5b  movups  xmmword ptr [rsp+520h+ProcessInformation.hProcess], xmm0
0x140018c60  call    cs:__imp_CreateProcessW
0x140018c66  cmp     eax, 1
0x140018c69  jnz     short loc_140018C76
0x140018c6b  mov     ecx, 1388h; dwMilliseconds
0x140018c70  call    cs:__imp_Sleep
0x140018c76  mov     rcx, [rsp+520h+ProcessInformation.hProcess]; hObject
0x140018c7b  test    rcx, rcx
0x140018c7e  jz      short loc_140018C86
0x140018c80  call    cs:__imp_CloseHandle
0x140018c86  mov     rcx, [rsp+520h+ProcessInformation.hThread]; hObject
0x140018c8b  test    rcx, rcx
0x140018c8e  jz      short loc_140018C96
0x140018c90  call    cs:__imp_CloseHandle
0x140018c96  xorps   xmm0, xmm0
0x140018c99  xor     eax, eax
0x140018c9b  movups  xmmword ptr [rsp+520h+ProcessInformation.hProcess], xmm0
0x140018ca0  mov     qword ptr [rsp+520h+ProcessInformation.dwProcessId], rax
0x140018ca5  mov     rcx, [rsp+520h+hkey]; hKey
0x140018caa  test    rcx, rcx
0x140018cad  jz      short loc_140018CB5
0x140018caf  call    cs:__imp_RegCloseKey
0x140018cb5  mov     rcx, [rbp+420h+var_10]
0x140018cbc  xor     rcx, rsp; StackCookie
0x140018cbf  call    __security_check_cookie
0x140018cc4  add     rsp, 520h
0x140018ccb  pop     rbp
0x140018ccc  retn
```
