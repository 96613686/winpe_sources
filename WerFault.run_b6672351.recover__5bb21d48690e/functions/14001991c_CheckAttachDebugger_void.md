# CheckAttachDebugger(void)

- ea: `0x14001991c`
- end: `0x140019b66`
- name: `?CheckAttachDebugger@@YAXXZ`
- size: `586`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14001a274`

## callees

- `0x140002490`
- `0x1400030f8`
- `0x14000551c`
- `0x14000b580`
- `0x140014ee4`
- `0x140014f14`
- `0x14001991c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400199c1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400199c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140019b41`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140019b41`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140019975`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140019975`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140019a0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140019a0f`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x140019ada`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x140019ada`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140019af0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140019af0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140019b06`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140019b1c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140019b06`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140019b1c`

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
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_35a6bf14758d33cd61dd1b0f627037ef_Traceguids, ValueW);
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
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_35a6bf14758d33cd61dd1b0f627037ef_Traceguids);
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
0x14001991c  push    rbp
0x14001991e  lea     rbp, [rsp-420h]
0x140019926  sub     rsp, 520h
0x14001992d  mov     rax, cs:__security_cookie
0x140019934  xor     rax, rsp
0x140019937  mov     [rbp+420h+var_10], rax
0x14001993e  lea     rcx, [rsp+520h+hkey]
0x140019943  mov     [rsp+520h+var_4C8], 0
0x14001994b  mov     [rsp+520h+hkey], 0
0x140019954  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x140019959  mov     r9d, 20119h; samDesired
0x14001995f  mov     [rsp+520h+phkResult], rax; phkResult
0x140019964  xor     r8d, r8d; ulOptions
0x140019967  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Windows\\Windows E"...
0x14001996e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140019975  call    cs:__imp_RegOpenKeyExW
0x14001997c  nop     dword ptr [rax+rax+00h]
0x140019981  mov     rcx, [rsp+520h+hkey]; hkey
0x140019986  test    eax, eax
0x140019988  jnz     loc_140019B3C
0x14001998e  lea     rax, [rsp+520h+var_4C8]
0x140019993  mov     [rsp+520h+var_4C8], 208h
0x14001999b  mov     [rsp+520h+pcbData], rax; pcbData
0x1400199a0  lea     r8, Value; "Debugger"
0x1400199a7  lea     rax, [rbp+420h+var_430]
0x1400199ab  mov     r9d, 2; dwFlags
0x1400199b1  mov     [rsp+520h+pvData], rax; pvData
0x1400199b6  xor     edx, edx; lpSubKey
0x1400199b8  mov     [rsp+520h+phkResult], 0; pdwType
0x1400199c1  call    cs:__imp_RegGetValueW
0x1400199c8  nop     dword ptr [rax+rax+00h]
0x1400199cd  test    eax, eax
0x1400199cf  jz      short loc_140019A0F
0x1400199d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400199d8  lea     rdx, WPP_GLOBAL_Control
0x1400199df  cmp     rcx, rdx
0x1400199e2  jz      loc_140019B37
0x1400199e8  test    byte ptr [rcx+1Ch], 1
0x1400199ec  jz      loc_140019B37
0x1400199f2  mov     rcx, [rcx+10h]
0x1400199f6  lea     r8, WPP_35a6bf14758d33cd61dd1b0f627037ef_Traceguids
0x1400199fd  mov     edx, 0Dh
0x140019a02  mov     r9d, eax
0x140019a05  call    WPP_SF_d
0x140019a0a  jmp     loc_140019B37
0x140019a0f  call    cs:__imp_GetCurrentProcessId
0x140019a16  nop     dword ptr [rax+rax+00h]
0x140019a1b  lea     r9, [rbp+420h+var_430]
0x140019a1f  mov     edx, 104h; unsigned __int64
0x140019a24  lea     r8, aSU; "%s %u"
0x140019a2b  mov     dword ptr [rsp+520h+phkResult], eax
0x140019a2f  lea     rcx, [rbp+420h+CommandLine]; wchar_t *
0x140019a36  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x140019a3b  test    eax, eax
0x140019a3d  js      loc_140019B37
0x140019a43  mov     rcx, cs:WPP_GLOBAL_Control
0x140019a4a  lea     rdx, WPP_GLOBAL_Control
0x140019a51  cmp     rcx, rdx
0x140019a54  jz      short loc_140019A71
0x140019a56  test    byte ptr [rcx+1Ch], 4
0x140019a5a  jz      short loc_140019A71
0x140019a5c  mov     rcx, [rcx+10h]
0x140019a60  lea     r8, WPP_35a6bf14758d33cd61dd1b0f627037ef_Traceguids
0x140019a67  mov     edx, 0Eh
0x140019a6c  call    WPP_SF_
0x140019a71  xor     edx, edx; Val
0x140019a73  lea     rcx, [rbp+420h+StartupInfo+4]; void *
0x140019a77  lea     r8d, [rdx+64h]; Size
0x140019a7b  call    memset_0
0x140019a80  xor     eax, eax
0x140019a82  mov     [rbp+420h+StartupInfo.cb], 68h ; 'h'
0x140019a89  mov     qword ptr [rsp+520h+ProcessInformation.dwProcessId], rax
0x140019a8e  lea     rdx, [rbp+420h+CommandLine]; lpCommandLine
0x140019a95  lea     rax, [rsp+520h+ProcessInformation]
0x140019a9a  xorps   xmm0, xmm0
0x140019a9d  mov     [rsp+520h+lpProcessInformation], rax; lpProcessInformation
0x140019aa2  xor     r9d, r9d; lpThreadAttributes
0x140019aa5  lea     rax, [rbp+420h+StartupInfo]
0x140019aa9  xor     r8d, r8d; lpProcessAttributes
0x140019aac  mov     [rsp+520h+lpStartupInfo], rax; lpStartupInfo
0x140019ab1  xor     ecx, ecx; lpApplicationName
0x140019ab3  mov     [rsp+520h+lpCurrentDirectory], 0; lpCurrentDirectory
0x140019abc  mov     [rsp+520h+pcbData], 0; lpEnvironment
0x140019ac5  mov     dword ptr [rsp+520h+pvData], 0; dwCreationFlags
0x140019acd  mov     dword ptr [rsp+520h+phkResult], 0; bInheritHandles
0x140019ad5  movups  xmmword ptr [rsp+520h+ProcessInformation.hProcess], xmm0
0x140019ada  call    cs:__imp_CreateProcessW
0x140019ae1  nop     dword ptr [rax+rax+00h]
0x140019ae6  cmp     eax, 1
0x140019ae9  jnz     short loc_140019AFC
0x140019aeb  mov     ecx, 1388h; dwMilliseconds
0x140019af0  call    cs:__imp_Sleep
0x140019af7  nop     dword ptr [rax+rax+00h]
0x140019afc  mov     rcx, [rsp+520h+ProcessInformation.hProcess]; hObject
0x140019b01  test    rcx, rcx
0x140019b04  jz      short loc_140019B12
0x140019b06  call    cs:__imp_CloseHandle
0x140019b0d  nop     dword ptr [rax+rax+00h]
0x140019b12  mov     rcx, [rsp+520h+ProcessInformation.hThread]; hObject
0x140019b17  test    rcx, rcx
0x140019b1a  jz      short loc_140019B28
0x140019b1c  call    cs:__imp_CloseHandle
0x140019b23  nop     dword ptr [rax+rax+00h]
0x140019b28  xorps   xmm0, xmm0
0x140019b2b  xor     eax, eax
0x140019b2d  movups  xmmword ptr [rsp+520h+ProcessInformation.hProcess], xmm0
0x140019b32  mov     qword ptr [rsp+520h+ProcessInformation.dwProcessId], rax
0x140019b37  mov     rcx, [rsp+520h+hkey]; hKey
0x140019b3c  test    rcx, rcx
0x140019b3f  jz      short loc_140019B4D
0x140019b41  call    cs:__imp_RegCloseKey
0x140019b48  nop     dword ptr [rax+rax+00h]
0x140019b4d  mov     rcx, [rbp+420h+var_10]
0x140019b54  xor     rcx, rsp; StackCookie
0x140019b57  call    __security_check_cookie
0x140019b5c  add     rsp, 520h
0x140019b63  pop     rbp
0x140019b64  retn
```
