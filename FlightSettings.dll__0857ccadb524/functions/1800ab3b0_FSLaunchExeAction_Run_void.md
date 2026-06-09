# FSLaunchExeAction::Run(void)

- ea: `0x1800ab3b0`
- end: `0x1800ab4f3`
- name: `?Run@FSLaunchExeAction@@UEAAJXZ`
- size: `323`
- prototype: `__int64 __fastcall(FSLaunchExeAction *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180005744`
- `0x18000cc6c`
- `0x18000cc8c`
- `0x18001c6f4`
- `0x18008907c`
- `0x1800ab3b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800ab4b7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800ab4b7`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800ab48b`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800ab48b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ab4c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ab4cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ab4c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ab4cb`

## string_xrefs

- `0x1800ab40c`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fslaunchexeaction.cpp`
- `0x1800ab499`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fslaunchexeaction.cpp`
- `0x1800ab3ee`: `%SystemRoot%\System32\DeviceCensus.exe`

## pseudocode

```c
__int64 __fastcall FSLaunchExeAction::Run(FSLaunchExeAction *this)
{
  unsigned __int16 *v1; // rbx
  int v3; // eax
  unsigned int LastError; // ebx
  const char *v5; // r9
  BOOL bInheritHandles; // [rsp+20h] [rbp-79h]
  unsigned __int16 *v8; // [rsp+50h] [rbp-49h] BYREF
  __int64 v9; // [rsp+58h] [rbp-41h]
  __int64 v10; // [rsp+60h] [rbp-39h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+68h] [rbp-31h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+80h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v1 = 0;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  if ( !*((_DWORD *)this + 14) )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v8);
    v9 = -1;
    v10 = -1;
    v3 = FlightSettingsAPICommon::ExpandEnvironmentPath(L"%SystemRoot%\\System32\\DeviceCensus.exe", &v8);
    LastError = v3;
    if ( v3 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x30,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fslaunchexeaction.cpp",
        (const char *)(unsigned int)v3,
        bInheritHandles);
      goto LABEL_8;
    }
    v1 = v8;
  }
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset_0(&StartupInfo.cb + 1, 0, 0x64u);
  StartupInfo.cb = 104;
  if ( CreateProcessW(0, v1, 0, 0, 0, 0, 0, 0, &StartupInfo, &ProcessInformation) )
  {
    WaitForSingleObject(ProcessInformation.hProcess, 1000 * *((_DWORD *)this + 15));
    CloseHandle(ProcessInformation.hThread);
    CloseHandle(ProcessInformation.hProcess);
    LastError = 0;
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x43,
                  (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fslaunchexeaction.cpp",
                  v5);
  }
LABEL_8:
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v8);
  return LastError;
}

```

## disassembly

```asm
0x1800ab3b0  mov     [rsp-8+arg_0], rbx
0x1800ab3b5  mov     [rsp-8+arg_8], rdi
0x1800ab3ba  push    rbp
0x1800ab3bb  lea     rbp, [rsp-57h]
0x1800ab3c0  sub     rsp, 0F0h
0x1800ab3c7  xor     ebx, ebx
0x1800ab3c9  mov     rdi, rcx
0x1800ab3cc  mov     [rbp+57h+var_A0], rbx
0x1800ab3d0  mov     [rbp+57h+var_98], rbx
0x1800ab3d4  mov     [rbp+57h+var_90], rbx
0x1800ab3d8  cmp     [rcx+38h], ebx
0x1800ab3db  jnz     short loc_1800AB429
0x1800ab3dd  lea     rcx, [rbp+57h+var_A0]
0x1800ab3e1  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800ab3e6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800ab3ea  lea     rdx, [rbp+57h+var_A0]; unsigned __int16 **
0x1800ab3ee  lea     rcx, Src; "%SystemRoot%\\System32\\DeviceCensus.ex"...
0x1800ab3f5  mov     [rbp+57h+var_98], rax
0x1800ab3f9  mov     [rbp+57h+var_90], rax
0x1800ab3fd  call    ?ExpandEnvironmentPath@FlightSettingsAPICommon@@SAJPEBGPEAPEAG@Z; FlightSettingsAPICommon::ExpandEnvironmentPath(ushort const *,ushort * *)
0x1800ab402  mov     ebx, eax
0x1800ab404  test    eax, eax
0x1800ab406  jns     short loc_1800AB425
0x1800ab408  mov     rcx, [rbp+5Fh]; this
0x1800ab40c  lea     r8, aOnecoreBaseFli_7; "onecore\\base\\flighting\\flightsetting"...
0x1800ab413  mov     r9d, eax; char *
0x1800ab416  mov     edx, 30h ; '0'; void *
0x1800ab41b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ab420  jmp     loc_1800AB4D3
0x1800ab425  mov     rbx, [rbp+57h+var_A0]
0x1800ab429  xor     eax, eax
0x1800ab42b  lea     rcx, [rbp+57h+StartupInfo+4]; void *
0x1800ab42f  xorps   xmm0, xmm0
0x1800ab432  mov     qword ptr [rbp+57h+ProcessInformation.dwProcessId], rax
0x1800ab436  xor     edx, edx; Val
0x1800ab438  movups  xmmword ptr [rbp+57h+ProcessInformation.hProcess], xmm0
0x1800ab43c  lea     r8d, [rax+64h]; Size
0x1800ab440  call    memset_0
0x1800ab445  lea     rax, [rbp+57h+ProcessInformation]
0x1800ab449  mov     [rbp+57h+StartupInfo.cb], 68h ; 'h'
0x1800ab450  mov     [rsp+0F0h+lpProcessInformation], rax; lpProcessInformation
0x1800ab455  xor     r9d, r9d; lpThreadAttributes
0x1800ab458  lea     rax, [rbp+57h+StartupInfo]
0x1800ab45c  xor     r8d, r8d; lpProcessAttributes
0x1800ab45f  mov     [rsp+0F0h+lpStartupInfo], rax; lpStartupInfo
0x1800ab464  mov     rdx, rbx; lpCommandLine
0x1800ab467  mov     [rsp+0F0h+lpCurrentDirectory], 0; lpCurrentDirectory
0x1800ab470  xor     ecx, ecx; lpApplicationName
0x1800ab472  mov     [rsp+0F0h+lpEnvironment], 0; lpEnvironment
0x1800ab47b  mov     [rsp+0F0h+dwCreationFlags], 0; dwCreationFlags
0x1800ab483  mov     [rsp+0F0h+bInheritHandles], 0; bInheritHandles
0x1800ab48b  call    cs:__imp_CreateProcessW
0x1800ab491  test    eax, eax
0x1800ab493  jnz     short loc_1800AB4AC
0x1800ab495  mov     rcx, [rbp+5Fh]; this
0x1800ab499  lea     r8, aOnecoreBaseFli_7; "onecore\\base\\flighting\\flightsetting"...
0x1800ab4a0  lea     edx, [rax+43h]; void *
0x1800ab4a3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800ab4a8  mov     ebx, eax
0x1800ab4aa  jmp     short loc_1800AB4D3
0x1800ab4ac  imul    edx, [rdi+3Ch], 3E8h; dwMilliseconds
0x1800ab4b3  mov     rcx, [rbp+57h+ProcessInformation.hProcess]; hHandle
0x1800ab4b7  call    cs:__imp_WaitForSingleObject
0x1800ab4bd  mov     rcx, [rbp+57h+ProcessInformation.hThread]; hObject
0x1800ab4c1  call    cs:__imp_CloseHandle
0x1800ab4c7  mov     rcx, [rbp+57h+ProcessInformation.hProcess]; hObject
0x1800ab4cb  call    cs:__imp_CloseHandle
0x1800ab4d1  xor     ebx, ebx
0x1800ab4d3  lea     rcx, [rbp+57h+var_A0]
0x1800ab4d7  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800ab4dc  lea     r11, [rsp+0F0h+var_s0]
0x1800ab4e4  mov     eax, ebx
0x1800ab4e6  mov     rbx, [r11+10h]
0x1800ab4ea  mov     rdi, [r11+18h]
0x1800ab4ee  mov     rsp, r11
0x1800ab4f1  pop     rbp
0x1800ab4f2  retn
```
