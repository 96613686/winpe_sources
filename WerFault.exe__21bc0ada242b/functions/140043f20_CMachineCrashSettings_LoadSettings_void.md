# CMachineCrashSettings::LoadSettings(void)

- ea: `0x140043f20`
- end: `0x140044011`
- name: `?LoadSettings@CMachineCrashSettings@@QEAAJXZ`
- size: `241`
- prototype: `__int64 __fastcall(CMachineCrashSettings *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14003d7d4`

## callees

- `0x140005468`
- `0x14001211c`
- `0x140012210`
- `0x140034d9c`
- `0x140043f20`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140044003`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140044003`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x140043f4d`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x140043f4d`

## string_xrefs

- `0x140043fcd`: `Failed to read the dumpfile setting for machine crash`
- `0x140043f7f`: `TempDestination`

## pseudocode

```c
__int64 __fastcall CMachineCrashSettings::LoadSettings(CMachineCrashSettings *this)
{
  HKEY *v2; // rax
  unsigned int DWORD; // eax
  HKEY v4; // rcx
  unsigned int v5; // eax
  HKEY v6; // rcx
  int String; // ebx
  wil::details *v9; // [rsp+20h] [rbp-28h]
  bool v10; // [rsp+28h] [rbp-20h]
  bool v11; // [rsp+28h] [rbp-20h]
  DWORD v12; // [rsp+30h] [rbp-18h]
  const char *v13; // [rsp+30h] [rbp-18h]
  wil::details::in1diag4 *retaddr; // [rsp+48h] [rbp+0h]
  HKEY hKey; // [rsp+58h] [rbp+10h] BYREF

  hKey = 0;
  v2 = tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  if ( RegOpenKeyW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\CrashControl\\MachineCrash", v2)
    || (DWORD = UtilRegGetDWORD(hKey, 0, L"BootStatus", 0, 0, v10),
        v4 = hKey,
        *(_DWORD *)this = DWORD,
        v5 = UtilRegGetDWORD(v4, 0, L"TempDestination", 0, 0, v11),
        v6 = hKey,
        *((_DWORD *)this + 1) = v5,
        String = UtilRegGetString(v6, 0, L"DumpFile", (__int64)this + 8, 1, v12),
        String >= 0) )
  {
    String = 0;
  }
  else
  {
    LODWORD(v9) = String;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)0x53,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\crashsettings.cpp",
      "CMachineCrashSettings::LoadSettings",
      v9,
      (int)"Failed to read the dumpfile setting for machine crash",
      v13);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x140043f20  push    rbx
0x140043f22  sub     rsp, 40h
0x140043f26  mov     rbx, rcx
0x140043f29  mov     [rsp+48h+hKey], 0
0x140043f32  lea     rcx, [rsp+48h+hKey]
0x140043f37  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x140043f3c  mov     r8, rax; phkResult
0x140043f3f  lea     rdx, aSystemCurrentc_7; "SYSTEM\\CurrentControlSet\\Control\\Cra"...
0x140043f46  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140043f4d  call    cs:__imp_RegOpenKeyW
0x140043f53  test    eax, eax
0x140043f55  jnz     loc_140043FF7
0x140043f5b  mov     rcx, [rsp+48h+hKey]; hKey
0x140043f60  lea     r8, aBootstatus; "BootStatus"
0x140043f67  xor     r9d, r9d; unsigned int
0x140043f6a  mov     [rsp+48h+var_28], 0; bool *
0x140043f73  xor     edx, edx; lpSubKey
0x140043f75  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x140043f7a  mov     rcx, [rsp+48h+hKey]; hKey
0x140043f7f  lea     r8, aTempdestinatio; "TempDestination"
0x140043f86  xor     r9d, r9d; unsigned int
0x140043f89  mov     [rbx], eax
0x140043f8b  xor     edx, edx; lpSubKey
0x140043f8d  mov     [rsp+48h+var_28], 0; bool *
0x140043f96  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x140043f9b  mov     rcx, [rsp+48h+hKey]; hKey
0x140043fa0  lea     r8, aDumpfile; "DumpFile"
0x140043fa7  mov     [rbx+4], eax
0x140043faa  xor     r9d, r9d
0x140043fad  lea     rax, [rbx+8]
0x140043fb1  mov     [rsp+48h+var_20], 1; char
0x140043fb6  xor     edx, edx; lpSubKey
0x140043fb8  mov     [rsp+48h+var_28], rax; __int64
0x140043fbd  call    ?UtilRegGetString@@YAJPEAUHKEY__@@PEB_W11PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N3@Z; UtilRegGetString(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,bool,bool)
0x140043fc2  mov     ebx, eax
0x140043fc4  test    eax, eax
0x140043fc6  jns     short loc_140043FF7
0x140043fc8  mov     rcx, [rsp+48h]; this
0x140043fcd  lea     rax, aFailedToReadTh; "Failed to read the dumpfile setting for"...
0x140043fd4  mov     qword ptr [rsp+48h+var_20], rax; int
0x140043fd9  lea     r9, aCmachinecrashs; "CMachineCrashSettings::LoadSettings"
0x140043fe0  lea     r8, aOnecoreWindows_11; "onecore\\windows\\feedback\\core\\werfa"...
0x140043fe7  mov     dword ptr [rsp+48h+var_28], ebx; wil::details *
0x140043feb  mov     edx, 53h ; 'S'; void *
0x140043ff0  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140043ff5  jmp     short loc_140043FF9
0x140043ff7  xor     ebx, ebx
0x140043ff9  mov     rcx, [rsp+48h+hKey]; hKey
0x140043ffe  test    rcx, rcx
0x140044001  jz      short loc_140044009
0x140044003  call    cs:__imp_RegCloseKey
0x140044009  mov     eax, ebx
0x14004400b  add     rsp, 40h
0x14004400f  pop     rbx
0x140044010  retn
```
