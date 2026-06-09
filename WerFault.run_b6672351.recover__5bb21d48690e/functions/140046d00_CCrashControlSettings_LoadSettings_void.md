# CCrashControlSettings::LoadSettings(void)

- ea: `0x140046d00`
- end: `0x140046ed2`
- name: `?LoadSettings@CCrashControlSettings@@QEAAJXZ`
- size: `466`
- prototype: `__int64 __fastcall(CCrashControlSettings *__hidden this)`
- caller_count: `4`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x140037978`
- `0x140037b60`
- `0x14003c780`
- `0x1400401fc`

## callees

- `0x14000551c`
- `0x14000e754`
- `0x140012994`
- `0x140012a9c`
- `0x1400372dc`
- `0x140046d00`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140046eb3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140046eb3`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x140046d35`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x140046d35`

## string_xrefs

- `0x140046d6e`: `Overwrite`
- `0x140046e2d`: `Failed to read settings for MiniDumpDir`
- `0x140046e99`: `Failed to read settings for DumpFile`

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
    tlx::trim<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>((char *)this + 8, asc_14006F200);
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
0x140046d00  mov     rax, rsp
0x140046d03  mov     [rax+8], rbx
0x140046d07  mov     [rax+18h], rsi
0x140046d0b  push    rdi
0x140046d0c  sub     rsp, 40h
0x140046d10  mov     rdi, rcx
0x140046d13  mov     qword ptr [rax+10h], 0
0x140046d1b  lea     rcx, [rax+10h]
0x140046d1f  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x140046d24  mov     r8, rax; phkResult
0x140046d27  lea     rdx, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Control\\Cra"...
0x140046d2e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140046d35  call    cs:__imp_RegOpenKeyW
0x140046d3c  nop     dword ptr [rax+rax+00h]
0x140046d41  test    eax, eax
0x140046d43  jnz     loc_140046EA7
0x140046d49  mov     rcx, [rsp+48h+hKey]; hKey
0x140046d4e  lea     r9d, [rax+1]; unsigned int
0x140046d52  lea     r8, aLogevent; "LogEvent"
0x140046d59  mov     [rsp+48h+var_28], 0; bool *
0x140046d62  xor     edx, edx; lpSubKey
0x140046d64  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x140046d69  mov     rcx, [rsp+48h+hKey]; hKey
0x140046d6e  lea     r8, aOverwrite; "Overwrite"
0x140046d75  xor     r9d, r9d; unsigned int
0x140046d78  mov     [rdi], eax
0x140046d7a  xor     edx, edx; lpSubKey
0x140046d7c  mov     [rsp+48h+var_28], 0; bool *
0x140046d85  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x140046d8a  mov     rcx, [rsp+48h+hKey]; hKey
0x140046d8f  lea     r8, aAlwayskeepmemo; "AlwaysKeepMemoryDump"
0x140046d96  xor     r9d, r9d; unsigned int
0x140046d99  mov     [rdi+4], eax
0x140046d9c  xor     edx, edx; lpSubKey
0x140046d9e  mov     [rsp+48h+var_28], 0; bool *
0x140046da7  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x140046dac  mov     rcx, [rsp+48h+hKey]; hKey
0x140046db1  lea     r8, aPersistdumpdis; "PersistDumpDiskSpaceLimit"
0x140046db8  xor     r9d, r9d; unsigned int
0x140046dbb  mov     [rdi+4Ch], eax
0x140046dbe  xor     edx, edx; lpSubKey
0x140046dc0  mov     [rsp+48h+var_28], 0; bool *
0x140046dc9  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x140046dce  mov     rcx, [rsp+48h+hKey]; hKey
0x140046dd3  lea     r8, aMinidumpscount; "MinidumpsCount"
0x140046dda  mov     ebx, 5
0x140046ddf  mov     [rdi+50h], eax
0x140046de2  mov     r9d, ebx; unsigned int
0x140046de5  mov     [rsp+48h+var_28], 0; bool *
0x140046dee  xor     edx, edx; lpSubKey
0x140046df0  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x140046df5  mov     [rdi+48h], eax
0x140046df8  test    eax, eax
0x140046dfa  jnz     short loc_140046DFF
0x140046dfc  mov     [rdi+48h], ebx
0x140046dff  mov     rcx, [rsp+48h+hKey]; hKey
0x140046e04  lea     rsi, [rdi+8]
0x140046e08  mov     [rsp+48h+var_20], 1; char
0x140046e0d  lea     r9, aSystemrootMini; "%SystemRoot%\\Minidump"
0x140046e14  lea     r8, aMinidumpdir; "MiniDumpDir"
0x140046e1b  mov     [rsp+48h+var_28], rsi; __int64
0x140046e20  xor     edx, edx; lpSubKey
0x140046e22  call    ?UtilRegGetString@@YAJPEAUHKEY__@@PEB_W11PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N3@Z; UtilRegGetString(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,bool,bool)
0x140046e27  mov     ebx, eax
0x140046e29  test    eax, eax
0x140046e2b  jns     short loc_140046E5C
0x140046e2d  lea     rax, aFailedToReadSe_0; "Failed to read settings for MiniDumpDir"
0x140046e34  mov     edx, 0B8h; void *
0x140046e39  mov     rcx, [rsp+48h]; this
0x140046e3e  lea     r8, aOnecoreWindows_11; "onecore\\windows\\feedback\\core\\werfa"...
0x140046e45  mov     qword ptr [rsp+48h+var_20], rax; int
0x140046e4a  lea     r9, aCcrashcontrols; "CCrashControlSettings::LoadSettings"
0x140046e51  mov     dword ptr [rsp+48h+var_28], ebx; wil::details *
0x140046e55  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140046e5a  jmp     short loc_140046EA9
0x140046e5c  lea     rdx, asc_14006F200; "\\/ \r\n\t\v"
0x140046e63  mov     rcx, rsi
0x140046e66  call    ??$trim@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAXAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_W@Z; tlx::trim<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *)
0x140046e6b  mov     rcx, [rsp+48h+hKey]; hKey
0x140046e70  lea     rax, [rdi+28h]
0x140046e74  mov     [rsp+48h+var_20], 1; char
0x140046e79  lea     r9, aSystemrootMemo; "%SystemRoot%\\MEMORY.DMP"
0x140046e80  lea     r8, aDumpfile; "DumpFile"
0x140046e87  mov     [rsp+48h+var_28], rax; __int64
0x140046e8c  xor     edx, edx; lpSubKey
0x140046e8e  call    ?UtilRegGetString@@YAJPEAUHKEY__@@PEB_W11PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N3@Z; UtilRegGetString(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,bool,bool)
0x140046e93  mov     ebx, eax
0x140046e95  test    eax, eax
0x140046e97  jns     short loc_140046EA7
0x140046e99  lea     rax, aFailedToReadSe; "Failed to read settings for DumpFile"
0x140046ea0  mov     edx, 0CAh
0x140046ea5  jmp     short loc_140046E39
0x140046ea7  xor     ebx, ebx
0x140046ea9  mov     rcx, [rsp+48h+hKey]; hKey
0x140046eae  test    rcx, rcx
0x140046eb1  jz      short loc_140046EBF
0x140046eb3  call    cs:__imp_RegCloseKey
0x140046eba  nop     dword ptr [rax+rax+00h]
0x140046ebf  mov     rsi, [rsp+48h+arg_10]
0x140046ec4  mov     eax, ebx
0x140046ec6  mov     rbx, [rsp+48h+arg_0]
0x140046ecb  add     rsp, 40h
0x140046ecf  pop     rdi
0x140046ed0  retn
```
