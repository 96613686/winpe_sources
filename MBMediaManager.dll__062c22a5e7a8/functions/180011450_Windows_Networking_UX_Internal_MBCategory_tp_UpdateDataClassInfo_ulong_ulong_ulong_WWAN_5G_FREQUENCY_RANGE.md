# Windows::Networking::UX::Internal::MBCategory::tp_UpdateDataClassInfo(ulong,ulong,ulong,_WWAN_5G_FREQUENCY_RANGE)

- ea: `0x180011450`
- end: `0x180011619`
- name: `?tp_UpdateDataClassInfo@MBCategory@Internal@UX@Networking@Windows@@AEAAXKKKW4_WWAN_5G_FREQUENCY_RANGE@@@Z`
- size: `457`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001dc70`
- `0x180044010`

## callees

- `0x180005fc0`
- `0x18000ad20`
- `0x18000c724`
- `0x180011450`
- `0x1800116e0`
- `0x18001bfa8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011558`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800115c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011558`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800115c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001158c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001158c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800115a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800115a3`

## string_xrefs

- `0x1800114bd`: `Windows::Networking::UX::Internal::MBCategory::tp_UpdateDataClassInfo`
- `0x1800114e0`: `Windows::Networking::UX::Internal::MBCategory::tp_UpdateDataClassInfo`
- `0x180011503`: `Windows::Networking::UX::Internal::MBCategory::tp_UpdateDataClassInfo`
- `0x180011602`: `Windows::Networking::UX::Internal::MBCategory::tp_UpdateDataClassInfo`
- `0x1800114b1`: `old _currentDataClass=%d, new _currentDataClass=%d`
- `0x1800115f6`: `old _availableDataClasses=%d, new _availableDataClasses=%d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Windows::Networking::UX::Internal::MBCategory::tp_UpdateDataClassInfo(
        HSTRING *a1,
        int a2,
        int a3,
        int a4,
        int a5)
{
  int v9; // r9d
  int v10; // edi
  int v11; // r9d
  unsigned __int64 v12; // rdi
  __int64 v13; // rdx
  LPVOID pv; // [rsp+30h] [rbp-48h] BYREF
  __int64 v15; // [rsp+38h] [rbp-40h]
  __int64 v16; // [rsp+40h] [rbp-38h]

  v9 = *((_DWORD *)a1 + 153);
  if ( v9 == a2 && *((_DWORD *)a1 + 155) == a4 )
  {
    v10 = a5;
    if ( *((_DWORD *)a1 + 156) == a5 )
      goto LABEL_4;
  }
  else
  {
    v10 = a5;
  }
  MBSettingUXLogging::Info(
    "Windows::Networking::UX::Internal::MBCategory::tp_UpdateDataClassInfo",
    0x1086u,
    "old _currentDataClass=%d, new _currentDataClass=%d",
    v9,
    a2);
  MBSettingUXLogging::Info(
    "Windows::Networking::UX::Internal::MBCategory::tp_UpdateDataClassInfo",
    0x1087u,
    "old _currentDataSubClass=%d, new _currentDataSubClass=%d",
    *((_DWORD *)a1 + 155),
    a4);
  MBSettingUXLogging::Info(
    "Windows::Networking::UX::Internal::MBCategory::tp_UpdateDataClassInfo",
    0x1088u,
    "old _frequencyRange5G=%d, new _frequencyRange5G=%d",
    *((_DWORD *)a1 + 156),
    v10);
  *((_DWORD *)a1 + 153) = a2;
  *((_DWORD *)a1 + 155) = a4;
  *((_DWORD *)a1 + 156) = v10;
  pv = 0;
  v15 = 0;
  v16 = 0;
  v12 = -1;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
    &pv,
    &sourceString,
    0xFFFFFFFFFFFFFFFFuLL);
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  v15 = -1;
  v16 = -1;
  if ( (int)Windows::Networking::UX::Internal::MBCategory::_CalculateCategoryName(
              (Windows::Networking::UX::Internal::MBCategory *)a1,
              v13,
              (unsigned __int16 **)&pv) >= 0 )
  {
    if ( pv )
    {
      do
        ++v12;
      while ( *((_WORD *)pv + v12) );
      if ( v12 <= 0xFFFFFFFF )
        Microsoft::WRL::Wrappers::HString::Set(
          (Microsoft::WRL::Wrappers::HString *)(a1 + 5),
          (const unsigned __int16 *)pv,
          v12);
    }
    else
    {
      WindowsDeleteString(a1[5]);
      a1[5] = 0;
      WindowsCreateString(&sourceString, 0, a1 + 5);
    }
    Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolInvoke(a1, 13);
  }
  if ( pv )
    CoTaskMemFree(pv);
LABEL_4:
  v11 = *((_DWORD *)a1 + 154);
  if ( v11 != a3 )
  {
    MBSettingUXLogging::Info(
      "Windows::Networking::UX::Internal::MBCategory::tp_UpdateDataClassInfo",
      0x109Cu,
      "old _availableDataClasses=%d, new _availableDataClasses=%d",
      v11,
      a3);
    *((_DWORD *)a1 + 154) = a3;
  }
}

```

## disassembly

```asm
0x180011450  push    rbx
0x180011452  push    rbp
0x180011453  push    rsi
0x180011454  push    rdi
0x180011455  push    r14
0x180011457  sub     rsp, 50h
0x18001145b  mov     ebp, r9d
0x18001145e  mov     esi, r8d
0x180011461  mov     r14d, edx
0x180011464  mov     rbx, rcx
0x180011467  mov     r9d, [rcx+264h]
0x18001146e  cmp     r9d, edx
0x180011471  jnz     short loc_1800114A5
0x180011473  cmp     [rcx+26Ch], ebp
0x180011479  jnz     short loc_1800114A5
0x18001147b  mov     edi, [rsp+78h+arg_20]
0x180011482  cmp     [rcx+270h], edi
0x180011488  jnz     short loc_1800114AC
0x18001148a  mov     r9d, [rbx+268h]
0x180011491  cmp     r9d, esi
0x180011494  jnz     loc_1800115F2
0x18001149a  add     rsp, 50h
0x18001149e  pop     r14
0x1800114a0  pop     rdi
0x1800114a1  pop     rsi
0x1800114a2  pop     rbp
0x1800114a3  pop     rbx
0x1800114a4  retn
0x1800114a5  mov     edi, [rsp+78h+arg_20]
0x1800114ac  mov     [rsp+78h+var_58], r14d
0x1800114b1  lea     r8, aOldCurrentdata_0; "old _currentDataClass=%d, new _currentD"...
0x1800114b8  mov     edx, 1086h; unsigned int
0x1800114bd  lea     rcx, aWindowsNetwork_132; "Windows::Networking::UX::Internal::MBCa"...
0x1800114c4  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x1800114c9  mov     [rsp+78h+var_58], ebp
0x1800114cd  mov     r9d, [rbx+26Ch]
0x1800114d4  lea     r8, aOldCurrentdata; "old _currentDataSubClass=%d, new _curre"...
0x1800114db  mov     edx, 1087h; unsigned int
0x1800114e0  lea     rcx, aWindowsNetwork_132; "Windows::Networking::UX::Internal::MBCa"...
0x1800114e7  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x1800114ec  mov     [rsp+78h+var_58], edi
0x1800114f0  mov     r9d, [rbx+270h]
0x1800114f7  lea     r8, aOldFrequencyra; "old _frequencyRange5G=%d, new _frequenc"...
0x1800114fe  mov     edx, 1088h; unsigned int
0x180011503  lea     rcx, aWindowsNetwork_132; "Windows::Networking::UX::Internal::MBCa"...
0x18001150a  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18001150f  mov     [rbx+264h], r14d
0x180011516  mov     [rbx+26Ch], ebp
0x18001151c  mov     [rbx+270h], edi
0x180011522  xor     ebp, ebp
0x180011524  mov     [rsp+78h+pv], rbp
0x180011529  mov     [rsp+78h+var_40], rbp
0x18001152e  mov     [rsp+78h+var_38], rbp
0x180011533  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18001153a  mov     r8, rdi
0x18001153d  lea     rdx, sourceString
0x180011544  lea     rcx, [rsp+78h+pv]
0x180011549  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18001154e  mov     rcx, [rsp+78h+pv]; pv
0x180011553  test    rcx, rcx
0x180011556  jz      short loc_180011563
0x180011558  call    cs:__imp_CoTaskMemFree
0x18001155e  mov     [rsp+78h+pv], rbp
0x180011563  mov     [rsp+78h+var_40], rdi
0x180011568  mov     [rsp+78h+var_38], rdi
0x18001156d  lea     r8, [rsp+78h+pv]; unsigned __int16 **
0x180011572  mov     rcx, rbx; this
0x180011575  call    ?_CalculateCategoryName@MBCategory@Internal@UX@Networking@Windows@@AEAAJ_NPEAPEAG@Z; Windows::Networking::UX::Internal::MBCategory::_CalculateCategoryName(bool,ushort * *)
0x18001157a  test    eax, eax
0x18001157c  js      short loc_1800115B7
0x18001157e  mov     rdx, [rsp+78h+pv]; unsigned __int16 *
0x180011583  test    rdx, rdx
0x180011586  jnz     short loc_1800115D0
0x180011588  mov     rcx, [rbx+28h]; string
0x18001158c  call    cs:__imp_WindowsDeleteString
0x180011592  mov     [rbx+28h], rbp
0x180011596  lea     r8, [rbx+28h]; string
0x18001159a  xor     edx, edx; length
0x18001159c  lea     rcx, sourceString; sourceString
0x1800115a3  call    cs:__imp_WindowsCreateString
0x1800115a9  mov     edx, 0Dh
0x1800115ae  mov     rcx, rbx
0x1800115b1  call    ?_SubmitThreadpoolInvoke@MBCategory@Internal@UX@Networking@Windows@@AEAAJW4MbInterfaceChangeProperty@345@@Z; Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolInvoke(Windows::Networking::UX::MbInterfaceChangeProperty)
0x1800115b6  nop
0x1800115b7  mov     rcx, [rsp+78h+pv]; pv
0x1800115bc  test    rcx, rcx
0x1800115bf  jz      loc_18001148A
0x1800115c5  call    cs:__imp_CoTaskMemFree
0x1800115cb  jmp     loc_18001148A
0x1800115d0  inc     rdi
0x1800115d3  cmp     word ptr [rdx+rdi*2], 0
0x1800115d8  jnz     short loc_1800115D0
0x1800115da  mov     eax, 0FFFFFFFFh
0x1800115df  cmp     rdi, rax
0x1800115e2  ja      short loc_1800115A9
0x1800115e4  mov     r8d, edi; unsigned int
0x1800115e7  lea     rcx, [rbx+28h]; this
0x1800115eb  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x1800115f0  jmp     short loc_1800115A9
0x1800115f2  mov     [rsp+78h+var_58], esi
0x1800115f6  lea     r8, aOldAvailableda; "old _availableDataClasses=%d, new _avai"...
0x1800115fd  mov     edx, 109Ch; unsigned int
0x180011602  lea     rcx, aWindowsNetwork_132; "Windows::Networking::UX::Internal::MBCa"...
0x180011609  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18001160e  mov     [rbx+268h], esi
0x180011614  jmp     loc_18001149A
```
