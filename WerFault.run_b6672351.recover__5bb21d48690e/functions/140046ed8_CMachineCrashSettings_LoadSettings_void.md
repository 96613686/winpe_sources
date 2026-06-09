# CMachineCrashSettings::LoadSettings(void)

- ea: `0x140046ed8`
- end: `0x140046fd6`
- name: `?LoadSettings@CMachineCrashSettings@@QEAAJXZ`
- size: `254`
- prototype: `__int64 __fastcall(CMachineCrashSettings *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1400401fc`

## callees

- `0x14000551c`
- `0x140012994`
- `0x140012a9c`
- `0x1400372dc`
- `0x140046ed8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140046fc1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140046fc1`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x140046f05`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x140046f05`

## string_xrefs

- `0x140046f8b`: `Failed to read the dumpfile setting for machine crash`
- `0x140046f3d`: `TempDestination`

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
  v2 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
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
0x140046ed8  push    rbx
0x140046eda  sub     rsp, 40h
0x140046ede  mov     rbx, rcx
0x140046ee1  mov     [rsp+48h+hKey], 0
0x140046eea  lea     rcx, [rsp+48h+hKey]
0x140046eef  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x140046ef4  mov     r8, rax; phkResult
0x140046ef7  lea     rdx, aSystemCurrentc_7; "SYSTEM\\CurrentControlSet\\Control\\Cra"...
0x140046efe  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140046f05  call    cs:__imp_RegOpenKeyW
0x140046f0c  nop     dword ptr [rax+rax+00h]
0x140046f11  test    eax, eax
0x140046f13  jnz     loc_140046FB5
0x140046f19  mov     rcx, [rsp+48h+hKey]; hKey
0x140046f1e  lea     r8, aBootstatus; "BootStatus"
0x140046f25  xor     r9d, r9d; unsigned int
0x140046f28  mov     [rsp+48h+var_28], 0; bool *
0x140046f31  xor     edx, edx; lpSubKey
0x140046f33  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x140046f38  mov     rcx, [rsp+48h+hKey]; hKey
0x140046f3d  lea     r8, aTempdestinatio; "TempDestination"
0x140046f44  xor     r9d, r9d; unsigned int
0x140046f47  mov     [rbx], eax
0x140046f49  xor     edx, edx; lpSubKey
0x140046f4b  mov     [rsp+48h+var_28], 0; bool *
0x140046f54  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x140046f59  mov     rcx, [rsp+48h+hKey]; hKey
0x140046f5e  lea     r8, aDumpfile; "DumpFile"
0x140046f65  mov     [rbx+4], eax
0x140046f68  xor     r9d, r9d
0x140046f6b  lea     rax, [rbx+8]
0x140046f6f  mov     [rsp+48h+var_20], 1; char
0x140046f74  xor     edx, edx; lpSubKey
0x140046f76  mov     [rsp+48h+var_28], rax; __int64
0x140046f7b  call    ?UtilRegGetString@@YAJPEAUHKEY__@@PEB_W11PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N3@Z; UtilRegGetString(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,bool,bool)
0x140046f80  mov     ebx, eax
0x140046f82  test    eax, eax
0x140046f84  jns     short loc_140046FB5
0x140046f86  mov     rcx, [rsp+48h]; this
0x140046f8b  lea     rax, aFailedToReadTh; "Failed to read the dumpfile setting for"...
0x140046f92  mov     qword ptr [rsp+48h+var_20], rax; int
0x140046f97  lea     r9, aCmachinecrashs; "CMachineCrashSettings::LoadSettings"
0x140046f9e  lea     r8, aOnecoreWindows_11; "onecore\\windows\\feedback\\core\\werfa"...
0x140046fa5  mov     dword ptr [rsp+48h+var_28], ebx; wil::details *
0x140046fa9  mov     edx, 53h ; 'S'; void *
0x140046fae  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140046fb3  jmp     short loc_140046FB7
0x140046fb5  xor     ebx, ebx
0x140046fb7  mov     rcx, [rsp+48h+hKey]; hKey
0x140046fbc  test    rcx, rcx
0x140046fbf  jz      short loc_140046FCD
0x140046fc1  call    cs:__imp_RegCloseKey
0x140046fc8  nop     dword ptr [rax+rax+00h]
0x140046fcd  mov     eax, ebx
0x140046fcf  add     rsp, 40h
0x140046fd3  pop     rbx
0x140046fd4  retn
```
