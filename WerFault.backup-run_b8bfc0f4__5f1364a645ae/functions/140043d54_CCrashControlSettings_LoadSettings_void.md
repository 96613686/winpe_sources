# CCrashControlSettings::LoadSettings(void)

- ea: `0x140043d54`
- end: `0x140043f19`
- name: `?LoadSettings@CCrashControlSettings@@QEAAJXZ`
- size: `453`
- prototype: `__int64 __fastcall(CCrashControlSettings *__hidden this)`
- caller_count: `4`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x14003546c`
- `0x140035654`
- `0x14003a0c0`
- `0x14003d7d4`

## callees

- `0x140005468`
- `0x14000e47c`
- `0x14001211c`
- `0x140012210`
- `0x140034d9c`
- `0x140043d54`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140043f01`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140043f01`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x140043d89`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x140043d89`

## string_xrefs

- `0x140043dbc`: `Overwrite`
- `0x140043e7b`: `Failed to read settings for MiniDumpDir`
- `0x140043ee7`: `Failed to read settings for DumpFile`

## pseudocode

```c
__int64 __fastcall CCrashControlSettings::LoadSettings(CCrashControlSettings *this)
{
  HKEY *v2; // rax
  unsigned int DWORD; // eax
  HKEY v4; // rcx
  unsigned int v5; // eax
  HKEY v6; // rcx
  unsigned int v7; // eax
  HKEY v8; // rcx
  unsigned int v9; // eax
  HKEY v10; // rcx
  unsigned int v11; // eax
  int String; // ebx
  const char *v13; // rax
  __int64 v14; // rdx
  wil::details *v16; // [rsp+20h] [rbp-28h]
  bool v17; // [rsp+28h] [rbp-20h]
  bool v18; // [rsp+28h] [rbp-20h]
  bool v19; // [rsp+28h] [rbp-20h]
  bool v20; // [rsp+28h] [rbp-20h]
  bool v21; // [rsp+28h] [rbp-20h]
  DWORD v22; // [rsp+30h] [rbp-18h]
  const char *v23; // [rsp+30h] [rbp-18h]
  wil::details::in1diag4 *retaddr; // [rsp+48h] [rbp+0h]
  HKEY hKey; // [rsp+58h] [rbp+10h] BYREF

  hKey = 0;
  v2 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  if ( !RegOpenKeyW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\CrashControl", v2) )
  {
    DWORD = UtilRegGetDWORD(hKey, 0, L"LogEvent", 1u, 0, v17);
    v4 = hKey;
    *(_DWORD *)this = DWORD;
    v5 = UtilRegGetDWORD(v4, 0, L"Overwrite", 0, 0, v18);
    v6 = hKey;
    *((_DWORD *)this + 1) = v5;
    v7 = UtilRegGetDWORD(v6, 0, L"AlwaysKeepMemoryDump", 0, 0, v19);
    v8 = hKey;
    *((_DWORD *)this + 19) = v7;
    v9 = UtilRegGetDWORD(v8, 0, L"PersistDumpDiskSpaceLimit", 0, 0, v20);
    v10 = hKey;
    *((_DWORD *)this + 20) = v9;
    v11 = UtilRegGetDWORD(v10, 0, L"MinidumpsCount", 5u, 0, v21);
    *((_DWORD *)this + 18) = v11;
    if ( !v11 )
      *((_DWORD *)this + 18) = 5;
    String = UtilRegGetString(hKey, 0, L"MiniDumpDir", (__int64)this + 8, 1, v22);
    if ( String < 0 )
    {
      v13 = "Failed to read settings for MiniDumpDir";
      v14 = 184;
LABEL_6:
      LODWORD(v16) = String;
      wil::details::in1diag4::Log_HrMsg(
        retaddr,
        (void *)v14,
        (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\crashsettings.cpp",
        "CCrashControlSettings::LoadSettings",
        v16,
        (int)v13,
        v23);
      goto LABEL_10;
    }
    tlx::trim<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>((char *)this + 8, asc_14006B2A0);
    String = UtilRegGetString(hKey, 0, L"DumpFile", (__int64)this + 40, 1, (DWORD)v23);
    if ( String < 0 )
    {
      v13 = "Failed to read settings for DumpFile";
      v14 = 202;
      goto LABEL_6;
    }
  }
  String = 0;
LABEL_10:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x140043d54  mov     rax, rsp
0x140043d57  mov     [rax+8], rbx
0x140043d5b  mov     [rax+18h], rsi
0x140043d5f  push    rdi
0x140043d60  sub     rsp, 40h
0x140043d64  mov     rdi, rcx
0x140043d67  mov     qword ptr [rax+10h], 0
0x140043d6f  lea     rcx, [rax+10h]
0x140043d73  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x140043d78  mov     r8, rax; phkResult
0x140043d7b  lea     rdx, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Control\\Cra"...
0x140043d82  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140043d89  call    cs:__imp_RegOpenKeyW
0x140043d8f  test    eax, eax
0x140043d91  jnz     loc_140043EF5
0x140043d97  mov     rcx, [rsp+48h+hKey]; hKey
0x140043d9c  lea     r9d, [rax+1]; unsigned int
0x140043da0  lea     r8, aLogevent; "LogEvent"
0x140043da7  mov     [rsp+48h+var_28], 0; bool *
0x140043db0  xor     edx, edx; lpSubKey
0x140043db2  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x140043db7  mov     rcx, [rsp+48h+hKey]; hKey
0x140043dbc  lea     r8, aOverwrite; "Overwrite"
0x140043dc3  xor     r9d, r9d; unsigned int
0x140043dc6  mov     [rdi], eax
0x140043dc8  xor     edx, edx; lpSubKey
0x140043dca  mov     [rsp+48h+var_28], 0; bool *
0x140043dd3  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x140043dd8  mov     rcx, [rsp+48h+hKey]; hKey
0x140043ddd  lea     r8, aAlwayskeepmemo; "AlwaysKeepMemoryDump"
0x140043de4  xor     r9d, r9d; unsigned int
0x140043de7  mov     [rdi+4], eax
0x140043dea  xor     edx, edx; lpSubKey
0x140043dec  mov     [rsp+48h+var_28], 0; bool *
0x140043df5  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x140043dfa  mov     rcx, [rsp+48h+hKey]; hKey
0x140043dff  lea     r8, aPersistdumpdis; "PersistDumpDiskSpaceLimit"
0x140043e06  xor     r9d, r9d; unsigned int
0x140043e09  mov     [rdi+4Ch], eax
0x140043e0c  xor     edx, edx; lpSubKey
0x140043e0e  mov     [rsp+48h+var_28], 0; bool *
0x140043e17  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x140043e1c  mov     rcx, [rsp+48h+hKey]; hKey
0x140043e21  lea     r8, aMinidumpscount; "MinidumpsCount"
0x140043e28  mov     ebx, 5
0x140043e2d  mov     [rdi+50h], eax
0x140043e30  mov     r9d, ebx; unsigned int
0x140043e33  mov     [rsp+48h+var_28], 0; bool *
0x140043e3c  xor     edx, edx; lpSubKey
0x140043e3e  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x140043e43  mov     [rdi+48h], eax
0x140043e46  test    eax, eax
0x140043e48  jnz     short loc_140043E4D
0x140043e4a  mov     [rdi+48h], ebx
0x140043e4d  mov     rcx, [rsp+48h+hKey]; hKey
0x140043e52  lea     rsi, [rdi+8]
0x140043e56  mov     [rsp+48h+var_20], 1; char
0x140043e5b  lea     r9, aSystemrootMini; "%SystemRoot%\\Minidump"
0x140043e62  lea     r8, aMinidumpdir; "MiniDumpDir"
0x140043e69  mov     [rsp+48h+var_28], rsi; __int64
0x140043e6e  xor     edx, edx; lpSubKey
0x140043e70  call    ?UtilRegGetString@@YAJPEAUHKEY__@@PEB_W11PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N3@Z; UtilRegGetString(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,bool,bool)
0x140043e75  mov     ebx, eax
0x140043e77  test    eax, eax
0x140043e79  jns     short loc_140043EAA
0x140043e7b  lea     rax, aFailedToReadSe_0; "Failed to read settings for MiniDumpDir"
0x140043e82  mov     edx, 0B8h; void *
0x140043e87  mov     rcx, [rsp+48h]; this
0x140043e8c  lea     r8, aOnecoreWindows_11; "onecore\\windows\\feedback\\core\\werfa"...
0x140043e93  mov     qword ptr [rsp+48h+var_20], rax; int
0x140043e98  lea     r9, aCcrashcontrols; "CCrashControlSettings::LoadSettings"
0x140043e9f  mov     dword ptr [rsp+48h+var_28], ebx; wil::details *
0x140043ea3  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140043ea8  jmp     short loc_140043EF7
0x140043eaa  lea     rdx, asc_14006B2A0; "\\/ \r\n\t\v"
0x140043eb1  mov     rcx, rsi
0x140043eb4  call    ??$trim@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAXAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_W@Z; tlx::trim<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *)
0x140043eb9  mov     rcx, [rsp+48h+hKey]; hKey
0x140043ebe  lea     rax, [rdi+28h]
0x140043ec2  mov     [rsp+48h+var_20], 1; char
0x140043ec7  lea     r9, aSystemrootMemo; "%SystemRoot%\\MEMORY.DMP"
0x140043ece  lea     r8, aDumpfile; "DumpFile"
0x140043ed5  mov     [rsp+48h+var_28], rax; __int64
0x140043eda  xor     edx, edx; lpSubKey
0x140043edc  call    ?UtilRegGetString@@YAJPEAUHKEY__@@PEB_W11PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N3@Z; UtilRegGetString(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,bool,bool)
0x140043ee1  mov     ebx, eax
0x140043ee3  test    eax, eax
0x140043ee5  jns     short loc_140043EF5
0x140043ee7  lea     rax, aFailedToReadSe; "Failed to read settings for DumpFile"
0x140043eee  mov     edx, 0CAh
0x140043ef3  jmp     short loc_140043E87
0x140043ef5  xor     ebx, ebx
0x140043ef7  mov     rcx, [rsp+48h+hKey]; hKey
0x140043efc  test    rcx, rcx
0x140043eff  jz      short loc_140043F07
0x140043f01  call    cs:__imp_RegCloseKey
0x140043f07  mov     rsi, [rsp+48h+arg_10]
0x140043f0c  mov     eax, ebx
0x140043f0e  mov     rbx, [rsp+48h+arg_0]
0x140043f13  add     rsp, 40h
0x140043f17  pop     rdi
0x140043f18  retn
```
