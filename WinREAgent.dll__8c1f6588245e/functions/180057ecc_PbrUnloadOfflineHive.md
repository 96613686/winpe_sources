# PbrUnloadOfflineHive

- ea: `0x180057ecc`
- end: `0x180058700`
- name: `PbrUnloadOfflineHive`
- size: `2100`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x18005781c`

## callees

- `0x1800049a4`
- `0x180004af8`
- `0x1800050bc`
- `0x180005c70`
- `0x180005cc0`
- `0x1800074b8`
- `0x18000d5c0`
- `0x18000d92c`
- `0x180011ef4`
- `0x180012968`
- `0x18003717c`
- `0x180037344`
- `0x180038434`
- `0x18004a898`
- `0x18004d8d0`
- `0x18004e7f8`
- `0x180057ecc`
- `0x18006c652`
- `0x18006c690`
- `0x18006f010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18005848e`
- `msvcrt!_wcsnicmp` at `0x18005848e`
- `msvcrt!_wcsicmp` at `0x18005836f`
- `msvcrt!_wcsicmp` at `0x18005836f`
- `ADVAPI32!RegUnLoadKeyW` at `0x180058541`
- `ADVAPI32!RegUnLoadKeyW` at `0x180058541`
- `KERNEL32!GetLastError` at `0x180057fa9`
- `KERNEL32!GetLastError` at `0x180057ff4`
- `KERNEL32!GetLastError` at `0x180057fa9`
- `KERNEL32!GetLastError` at `0x180057ff4`
- `KERNEL32!QueryDosDeviceW` at `0x180057f9f`
- `KERNEL32!QueryDosDeviceW` at `0x180057f9f`

## string_xrefs

- `0x18005804d`: `Failed to get volume-relative path for [%s]`
- `0x180058133`: `Registry: Attempting to find and unload [%s]`
- `0x1800580e4`: `Failed to get NT object path for [%s] on volume [%s]`
- `0x18005816f`: `Failed to open host OS system hive`
- `0x1800582a7`: `Failed to enumerate mount points in registry hive list`
- `0x180058222`: `Failed to open host OS hive mount point list`
- `0x18005835a`: `Registry: Found mapping: [%s] -> [%s]`
- `0x1800583df`: `Failed to get file path for mount point [%s]`
- `0x1800584da`: `Unknown registry object path [%s]`
- `0x18005843e`: `Registry: [%s] is mounted at [%s]`
- `0x18005852c`: `Registry: Attempting to unload hive`
- `0x180058654`: `Registry: Did not find mount point for [%s]`
- `0x1800585fe`: `Registry: Successfully unloaded hive`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
signed int __fastcall PbrUnloadOfflineHive(__int64 a1)
{
  int Drive; // edi
  signed int result; // eax
  signed int LastError; // eax
  ATL::CStringData *v5; // rcx
  __int64 v6; // rbx
  wchar_t *v7; // rdi
  __int64 v8; // rax
  signed int v9; // ebx
  __int64 v10; // rsi
  __int64 (__fastcall *v11)(__int64, const wchar_t *, __int64); // rbx
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // r8
  unsigned __int64 v15; // r14
  wchar_t *v16; // rbx
  _QWORD *v17; // r15
  __int64 v18; // rax
  int v19; // esi
  wchar_t *v20; // rcx
  int *v21; // rsi
  __int64 v22; // rbx
  ATL::CStringData *v23; // r14
  char v24; // r13
  unsigned __int64 i; // rsi
  const wchar_t *v26; // rdx
  size_t v27; // r15
  HKEY v28; // r12
  unsigned int v29; // eax
  __int64 v30; // rcx
  LSTATUS KeyW; // eax
  WCHAR v32; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v33; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t *String2; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v35[2]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v36[2]; // [rsp+68h] [rbp-98h] BYREF
  wchar_t *v37; // [rsp+78h] [rbp-88h] BYREF
  LPCWSTR lpSubKey; // [rsp+80h] [rbp-80h] BYREF
  wchar_t *String1; // [rsp+88h] [rbp-78h] BYREF
  HKEY v40; // [rsp+90h] [rbp-70h]
  __int64 v41; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int64 v42; // [rsp+A0h] [rbp-60h]
  __int64 v43; // [rsp+A8h] [rbp-58h]
  int v44; // [rsp+B0h] [rbp-50h]
  WCHAR DeviceName; // [rsp+B8h] [rbp-48h] BYREF
  int v46; // [rsp+BAh] [rbp-46h]
  WCHAR TargetPath[264]; // [rsp+C0h] [rbp-40h] BYREF

  v32 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&String2,
    a1);
  Drive = PushButtonReset::Path::GetDrive(&String2, &v32);
  ATL::CStringData::Release((ATL::CStringData *)(String2 - 12));
  if ( Drive < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)Drive,
      "PbrUnloadOfflineHive",
      "base\\reset\\util\\src\\regoffline.cpp",
      104,
      L"Failed to get parent drive for [%s]",
      a1);
    return Drive;
  }
  v46 = 58;
  DeviceName = v32;
  memset_0(TargetPath, 0, 0x20Au);
  if ( QueryDosDeviceW(&DeviceName, TargetPath, 0x104u) )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v33);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&String2,
      a1);
    Drive = PushButtonReset::Path::GetVolumeRelPath(&String2, &v33);
    ATL::CStringData::Release((ATL::CStringData *)(String2 - 12));
    if ( Drive < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Drive,
        "PbrUnloadOfflineHive",
        "base\\reset\\util\\src\\regoffline.cpp",
        120,
        L"Failed to get volume-relative path for [%s]",
        a1);
      v5 = (ATL::CStringData *)(v33 - 24);
LABEL_11:
      ATL::CStringData::Release(v5);
      return Drive;
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&String2);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v37,
      (__int64)TargetPath);
    Drive = PushButtonReset::Path::Combine(&v37, &v33, &String2);
    ATL::CStringData::Release((ATL::CStringData *)(v37 - 12));
    if ( Drive < 0 )
    {
      v6 = v33;
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Drive,
        "PbrUnloadOfflineHive",
        "base\\reset\\util\\src\\regoffline.cpp",
        126,
        L"Failed to get NT object path for [%s] on volume [%s]",
        v33,
        TargetPath);
      ATL::CStringData::Release((ATL::CStringData *)(String2 - 12));
      v5 = (ATL::CStringData *)(v6 - 24);
      goto LABEL_11;
    }
    v7 = String2;
    PushButtonReset::Logging::Trace(0, L"Registry: Attempting to find and unload [%s]", String2);
    v36[1] = 0;
    v36[0] = &RAII::CAutoPbrDelete<PushButtonReset::RegKey *>::`vftable';
    v8 = RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)v36);
    v9 = PushButtonReset::RegHive::OpenSystemHive(2, v8);
    if ( v9 >= 0 )
    {
      v35[1] = 0;
      v35[0] = &RAII::CAutoPbrDelete<PushButtonReset::RegKey *>::`vftable';
      v10 = (*(__int64 (__fastcall **)(_QWORD *))(v36[0] + 24LL))(v36);
      v11 = *(__int64 (__fastcall **)(__int64, const wchar_t *, __int64))(*(_QWORD *)v10 + 24LL);
      v12 = (*(__int64 (__fastcall **)(_QWORD *))(v35[0] + 8LL))(v35);
      v9 = v11(v10, L"CurrentControlSet\\Control\\HiveList", v12);
      if ( v9 >= 0 )
      {
        v41 = 0;
        v42 = 0;
        v43 = 0;
        v44 = 0;
        v13 = (*(__int64 (__fastcall **)(_QWORD *))(v35[0] + 24LL))(v35);
        v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v13 + 152LL))(v13, &v41);
        if ( v9 >= 0 )
        {
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v37);
          v15 = 0;
          v16 = v37;
          while ( v15 < v42 )
          {
            v17 = (_QWORD *)ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(
                              &v41,
                              v15,
                              v14);
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&String1);
            v18 = (*(__int64 (__fastcall **)(_QWORD *))(v35[0] + 24LL))(v35);
            v19 = (*(__int64 (__fastcall **)(__int64, _QWORD, wchar_t **))(*(_QWORD *)v18 + 96LL))(v18, *v17, &String1);
            if ( v19 < 0 )
            {
              PushButtonReset::Logging::TraceErr(
                2,
                (unsigned int)v19,
                "PbrUnloadOfflineHive",
                "base\\reset\\util\\src\\regoffline.cpp",
                154,
                L"Failed to get file path for mount point [%s]",
                *v17);
              ATL::CStringData::Release((ATL::CStringData *)(String1 - 12));
              ATL::CStringData::Release((ATL::CStringData *)(v16 - 12));
LABEL_48:
              ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::~CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>((__int64)&v41);
              v35[0] = &RAII::CAutoPbrDelete<PushButtonReset::RegKey *>::`vftable';
              RAII::CAutoPbrDelete<WinREAgent::PrepareWinRE *>::Release(v35);
              v36[0] = &RAII::CAutoPbrDelete<PushButtonReset::RegKey *>::`vftable';
              RAII::CAutoPbrDelete<WinREAgent::PrepareWinRE *>::Release(v36);
              ATL::CStringData::Release((ATL::CStringData *)(v7 - 12));
              ATL::CStringData::Release((ATL::CStringData *)(v33 - 24));
              return v19;
            }
            PushButtonReset::Logging::Trace(0, L"Registry: Found mapping: [%s] -> [%s]", *v17, String1);
            if ( !_wcsicmp(String1, v7) )
            {
              v20 = (wchar_t *)(*v17 - 24LL);
              v21 = (int *)(v16 - 12);
              if ( v20 != v16 - 12 )
              {
                if ( v21[4] >= 0 && *(_QWORD *)v20 == *(_QWORD *)v21 )
                {
                  v22 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v20);
                  ATL::CStringData::Release((ATL::CStringData *)v21);
                  v16 = (wchar_t *)(v22 + 24);
                  v37 = v16;
                }
                else
                {
                  ATL::CSimpleStringT<unsigned short,0>::SetString(&v37, *v17, *(unsigned int *)(*v17 - 16LL));
                  v16 = v37;
                }
              }
            }
            ATL::CStringData::Release((ATL::CStringData *)(String1 - 12));
            ++v15;
          }
          v23 = (ATL::CStringData *)(v16 - 12);
          if ( *((int *)v16 - 4) <= 0 )
          {
            PushButtonReset::Logging::TraceErr(
              1,
              2147943568LL,
              "PbrUnloadOfflineHive",
              "base\\reset\\util\\src\\regoffline.cpp",
              218,
              L"Registry: Did not find mount point for [%s]",
              v7);
            ATL::CStringData::Release((ATL::CStringData *)(v16 - 12));
            ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::~CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>((__int64)&v41);
            v35[0] = &RAII::CAutoPbrDelete<PushButtonReset::RegKey *>::`vftable';
            RAII::CAutoPbrDelete<WinREAgent::PrepareWinRE *>::Release(v35);
            v36[0] = &RAII::CAutoPbrDelete<PushButtonReset::RegKey *>::`vftable';
            RAII::CAutoPbrDelete<WinREAgent::PrepareWinRE *>::Release(v36);
            ATL::CStringData::Release((ATL::CStringData *)(v7 - 12));
            ATL::CStringData::Release((ATL::CStringData *)(v33 - 24));
            return -2147023728;
          }
          PushButtonReset::Logging::Trace(0, L"Registry: [%s] is mounted at [%s]", v7, v16);
          v24 = 0;
          v40 = 0;
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            (__int64)&lpSubKey,
            (__int64)&pszFormat);
          for ( i = 0; i < 2; ++i )
          {
            v26 = (&off_1800AA100)[2 * i];
            v27 = -1;
            do
              ++v27;
            while ( v26[v27] );
            if ( _wcsnicmp(v16, v26, v27) )
            {
              v28 = v40;
            }
            else
            {
              v24 = 1;
              v28 = (HKEY)*(&off_1800AA100 + 2 * i + 1);
              v40 = v28;
              v29 = ATL::CSimpleStringT<unsigned short,0>::StringLength(&v16[v27]);
              ATL::CSimpleStringT<unsigned short,0>::SetString(&lpSubKey, v30, v29);
            }
          }
          v7 = String2;
          if ( !v24 )
          {
            PushButtonReset::Logging::TraceErr(
              2,
              2147942413LL,
              "PbrUnloadOfflineHive",
              "base\\reset\\util\\src\\regoffline.cpp",
              200,
              L"Unknown registry object path [%s]",
              v16);
            ATL::CStringData::Release((ATL::CStringData *)(lpSubKey - 12));
            ATL::CStringData::Release((ATL::CStringData *)(v16 - 12));
            v19 = -2147024883;
            goto LABEL_48;
          }
          PushButtonReset::Logging::Trace(0, L"Registry: Attempting to unload hive");
          KeyW = RegUnLoadKeyW(v28, lpSubKey);
          v9 = KeyW;
          if ( KeyW > 0 )
            v9 = (unsigned __int16)KeyW | 0x80070000;
          if ( v9 < 0 )
          {
            PushButtonReset::Logging::TraceErr(
              1,
              (unsigned int)v9,
              "PbrUnloadOfflineHive",
              "base\\reset\\util\\src\\regoffline.cpp",
              208,
              L"Failed to unload [%s]",
              lpSubKey);
            ATL::CStringData::Release((ATL::CStringData *)(lpSubKey - 12));
            ATL::CStringData::Release(v23);
            v19 = v9;
            goto LABEL_48;
          }
          PushButtonReset::Logging::Trace(0, L"Registry: Successfully unloaded hive");
          ATL::CStringData::Release((ATL::CStringData *)(lpSubKey - 12));
          ATL::CStringData::Release(v23);
          ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::~CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>((__int64)&v41);
          v35[0] = &RAII::CAutoPbrDelete<PushButtonReset::RegKey *>::`vftable';
          RAII::CAutoPbrDelete<WinREAgent::PrepareWinRE *>::Release(v35);
          v36[0] = &RAII::CAutoPbrDelete<PushButtonReset::RegKey *>::`vftable';
LABEL_17:
          RAII::CAutoPbrDelete<WinREAgent::PrepareWinRE *>::Release(v36);
          ATL::CStringData::Release((ATL::CStringData *)(v7 - 12));
          ATL::CStringData::Release((ATL::CStringData *)(v33 - 24));
          return v9;
        }
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)v9,
          "PbrUnloadOfflineHive",
          "base\\reset\\util\\src\\regoffline.cpp",
          144,
          L"Failed to enumerate mount points in registry hive list");
        ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::~CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>((__int64)&v41);
      }
      else
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)v9,
          "PbrUnloadOfflineHive",
          "base\\reset\\util\\src\\regoffline.cpp",
          140,
          L"Failed to open host OS hive mount point list");
      }
      v35[0] = &RAII::CAutoPbrDelete<PushButtonReset::RegKey *>::`vftable';
      RAII::CAutoPbrDelete<WinREAgent::PrepareWinRE *>::Release(v35);
    }
    else
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)v9,
        "PbrUnloadOfflineHive",
        "base\\reset\\util\\src\\regoffline.cpp",
        136,
        L"Failed to open host OS system hive");
    }
    v36[0] = &RAII::CAutoPbrDelete<PushButtonReset::RegKey *>::`vftable';
    goto LABEL_17;
  }
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  PushButtonReset::Logging::TraceErr(
    2,
    (unsigned int)LastError,
    "PbrUnloadOfflineHive",
    "base\\reset\\util\\src\\regoffline.cpp",
    115,
    L"Failed to get NT object name for [%s]",
    &DeviceName);
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180057ecc  push    rbp
0x180057ece  push    rbx
0x180057ecf  push    rsi
0x180057ed0  push    rdi
0x180057ed1  push    r12
0x180057ed3  push    r13
0x180057ed5  push    r14
0x180057ed7  push    r15
0x180057ed9  lea     rbp, [rsp-1E8h]
0x180057ee1  sub     rsp, 2E8h
0x180057ee8  mov     rax, cs:__security_cookie
0x180057eef  xor     rax, rsp
0x180057ef2  mov     [rbp+220h+var_50], rax
0x180057ef9  mov     rbx, rcx
0x180057efc  xor     r12d, r12d
0x180057eff  mov     [rsp+320h+var_2E0], r12w
0x180057f05  mov     rdx, rcx
0x180057f08  lea     rcx, [rsp+320h+String2]
0x180057f0d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180057f12  nop
0x180057f13  lea     rdx, [rsp+320h+var_2E0]
0x180057f18  lea     rcx, [rsp+320h+String2]
0x180057f1d  call    ?GetDrive@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAG@Z; PushButtonReset::Path::GetDrive(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort *)
0x180057f22  mov     edi, eax
0x180057f24  mov     rcx, [rsp+320h+String2]
0x180057f29  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180057f2d  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180057f32  test    edi, edi
0x180057f34  jns     short loc_180057F70
0x180057f36  mov     [rsp+320h+var_2F0], rbx
0x180057f3b  lea     rax, aFailedToGetPar_4; "Failed to get parent drive for [%s]"
0x180057f42  mov     [rsp+320h+var_2F8], rax
0x180057f47  mov     [rsp+320h+var_300], 68h ; 'h'
0x180057f4f  lea     r9, aBaseResetUtilS_3; "base\\reset\\util\\src\\regoffline.cpp"
0x180057f56  lea     r8, aPbrunloadoffli; "PbrUnloadOfflineHive"
0x180057f5d  mov     edx, edi
0x180057f5f  lea     ecx, [r12+2]
0x180057f64  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180057f69  mov     eax, edi
0x180057f6b  jmp     loc_1800586DD
0x180057f70  mov     [rbp+220h+var_266], 3Ah ; ':'
0x180057f77  movzx   eax, [rsp+320h+var_2E0]
0x180057f7c  mov     [rbp+220h+DeviceName], ax
0x180057f80  xor     edx, edx; Val
0x180057f82  mov     r8d, 20Ah; Size
0x180057f88  lea     rcx, [rbp+220h+TargetPath]; void *
0x180057f8c  call    memset_0
0x180057f91  mov     r8d, 104h; ucchMax
0x180057f97  lea     rdx, [rbp+220h+TargetPath]; lpTargetPath
0x180057f9b  lea     rcx, [rbp+220h+DeviceName]; lpDeviceName
0x180057f9f  call    cs:__imp_QueryDosDeviceW
0x180057fa5  test    eax, eax
0x180057fa7  jnz     short loc_18005800C
0x180057fa9  call    cs:__imp_GetLastError
0x180057faf  mov     esi, 80070000h
0x180057fb4  test    eax, eax
0x180057fb6  jle     short loc_180057FBD
0x180057fb8  movzx   eax, ax
0x180057fbb  or      eax, esi
0x180057fbd  lea     rcx, [rbp+220h+DeviceName]
0x180057fc1  mov     [rsp+320h+var_2F0], rcx
0x180057fc6  lea     rcx, aFailedToGetNtO; "Failed to get NT object name for [%s]"
0x180057fcd  mov     [rsp+320h+var_2F8], rcx
0x180057fd2  mov     [rsp+320h+var_300], 73h ; 's'
0x180057fda  lea     r9, aBaseResetUtilS_3; "base\\reset\\util\\src\\regoffline.cpp"
0x180057fe1  lea     r8, aPbrunloadoffli; "PbrUnloadOfflineHive"
0x180057fe8  mov     edx, eax
0x180057fea  mov     ecx, 2
0x180057fef  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180057ff4  call    cs:__imp_GetLastError
0x180057ffa  test    eax, eax
0x180057ffc  jle     loc_1800586DD
0x180058002  movzx   eax, ax
0x180058005  or      eax, esi
0x180058007  jmp     loc_1800586DD
0x18005800c  lea     rcx, [rsp+320h+var_2D8]
0x180058011  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180058016  nop
0x180058017  mov     rdx, rbx
0x18005801a  lea     rcx, [rsp+320h+String2]
0x18005801f  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180058024  nop
0x180058025  lea     rdx, [rsp+320h+var_2D8]
0x18005802a  lea     rcx, [rsp+320h+String2]
0x18005802f  call    ?GetVolumeRelPath@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAV34@@Z; PushButtonReset::Path::GetVolumeRelPath(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x180058034  mov     edi, eax
0x180058036  mov     rcx, [rsp+320h+String2]
0x18005803b  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18005803f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180058044  test    edi, edi
0x180058046  jns     short loc_18005808F
0x180058048  mov     [rsp+320h+var_2F0], rbx
0x18005804d  lea     rax, aFailedToGetVol_4; "Failed to get volume-relative path for "...
0x180058054  mov     [rsp+320h+var_2F8], rax
0x180058059  mov     [rsp+320h+var_300], 78h ; 'x'
0x180058061  lea     r9, aBaseResetUtilS_3; "base\\reset\\util\\src\\regoffline.cpp"
0x180058068  lea     r8, aPbrunloadoffli; "PbrUnloadOfflineHive"
0x18005806f  mov     edx, edi
0x180058071  mov     ecx, 2
0x180058076  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18005807b  nop
0x18005807c  mov     rcx, [rsp+320h+var_2D8]
0x180058081  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180058085  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18005808a  jmp     loc_180057F69
0x18005808f  lea     rcx, [rsp+320h+String2]
0x180058094  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180058099  nop
0x18005809a  lea     rdx, [rbp+220h+TargetPath]
0x18005809e  lea     rcx, [rsp+320h+var_2A8]
0x1800580a3  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800580a8  nop
0x1800580a9  lea     r8, [rsp+320h+String2]
0x1800580ae  lea     rdx, [rsp+320h+var_2D8]
0x1800580b3  lea     rcx, [rsp+320h+var_2A8]
0x1800580b8  call    ?Combine@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAV34@@Z; PushButtonReset::Path::Combine(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x1800580bd  mov     edi, eax
0x1800580bf  mov     rcx, [rsp+320h+var_2A8]
0x1800580c4  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800580c8  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800580cd  test    edi, edi
0x1800580cf  jns     short loc_18005812B
0x1800580d1  lea     rax, [rbp+220h+TargetPath]
0x1800580d5  mov     [rsp+320h+var_2E8], rax
0x1800580da  mov     rbx, [rsp+320h+var_2D8]
0x1800580df  mov     [rsp+320h+var_2F0], rbx
0x1800580e4  lea     rax, aFailedToGetNtO_0; "Failed to get NT object path for [%s] o"...
0x1800580eb  mov     [rsp+320h+var_2F8], rax
0x1800580f0  mov     [rsp+320h+var_300], 7Eh ; '~'
0x1800580f8  lea     r9, aBaseResetUtilS_3; "base\\reset\\util\\src\\regoffline.cpp"
0x1800580ff  lea     r8, aPbrunloadoffli; "PbrUnloadOfflineHive"
0x180058106  mov     edx, edi
0x180058108  mov     ecx, 2
0x18005810d  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180058112  nop
0x180058113  mov     rcx, [rsp+320h+String2]
0x180058118  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18005811c  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180058121  nop
0x180058122  lea     rcx, [rbx-18h]
0x180058126  jmp     loc_180058085
0x18005812b  mov     rdi, [rsp+320h+String2]
0x180058130  mov     r8, rdi
0x180058133  lea     rdx, aRegistryAttemp; "Registry: Attempting to find and unload"...
0x18005813a  xor     ecx, ecx
0x18005813c  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180058141  mov     [rsp+320h+var_2B0], r12
0x180058146  lea     r15, ??_7?$CAutoPbrDelete@PEAVRegKey@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::RegKey *>::`vftable'
0x18005814d  mov     [rsp+320h+var_2B8], r15
0x180058152  lea     rcx, [rsp+320h+var_2B8]
0x180058157  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x18005815c  mov     rdx, rax
0x18005815f  mov     ecx, 2
0x180058164  call    ?OpenSystemHive@RegHive@PushButtonReset@@SAJW4SystemHive@2@PEAPEAVRegKey@2@@Z; PushButtonReset::RegHive::OpenSystemHive(PushButtonReset::SystemHive,PushButtonReset::RegKey * *)
0x180058169  mov     ebx, eax
0x18005816b  test    eax, eax
0x18005816d  jns     short loc_1800581CD
0x18005816f  lea     rax, aFailedToOpenHo; "Failed to open host OS system hive"
0x180058176  mov     [rsp+320h+var_2F8], rax
0x18005817b  mov     [rsp+320h+var_300], 88h
0x180058183  lea     r9, aBaseResetUtilS_3; "base\\reset\\util\\src\\regoffline.cpp"
0x18005818a  lea     r8, aPbrunloadoffli; "PbrUnloadOfflineHive"
0x180058191  mov     edx, ebx
0x180058193  mov     ecx, 2
0x180058198  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18005819d  nop
0x18005819e  mov     [rsp+320h+var_2B8], r15
0x1800581a3  lea     rcx, [rsp+320h+var_2B8]
0x1800581a8  call    ?Release@?$CAutoPbrDelete@PEAVPrepareWinRE@WinREAgent@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<WinREAgent::PrepareWinRE *>::Release(void)
0x1800581ad  nop
0x1800581ae  lea     rcx, [rdi-18h]; this
0x1800581b2  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800581b7  nop
0x1800581b8  mov     rcx, [rsp+320h+var_2D8]
0x1800581bd  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800581c1  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800581c6  mov     eax, ebx
0x1800581c8  jmp     loc_1800586DD
0x1800581cd  mov     [rsp+320h+var_2C0], r12
0x1800581d2  mov     [rsp+320h+var_2C8], r15
0x1800581d7  mov     rax, [rsp+320h+var_2B8]
0x1800581dc  lea     rcx, [rsp+320h+var_2B8]
0x1800581e1  mov     rax, [rax+18h]
0x1800581e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800581ea  mov     rsi, rax
0x1800581ed  mov     rcx, [rax]
0x1800581f0  mov     rbx, [rcx+18h]
0x1800581f4  mov     rcx, [rsp+320h+var_2C8]
0x1800581f9  mov     rax, [rcx+8]
0x1800581fd  lea     rcx, [rsp+320h+var_2C8]
0x180058202  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058207  mov     r8, rax
0x18005820a  lea     rdx, aCurrentcontrol; "CurrentControlSet\\Control\\HiveList"
0x180058211  mov     rcx, rsi
0x180058214  mov     rax, rbx
0x180058217  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005821c  mov     ebx, eax
0x18005821e  test    eax, eax
0x180058220  jns     short loc_180058265
0x180058222  lea     rax, aFailedToOpenHo_0; "Failed to open host OS hive mount point"...
0x180058229  mov     [rsp+320h+var_2F8], rax
0x18005822e  mov     [rsp+320h+var_300], 8Ch
0x180058236  lea     r9, aBaseResetUtilS_3; "base\\reset\\util\\src\\regoffline.cpp"
0x18005823d  lea     r8, aPbrunloadoffli; "PbrUnloadOfflineHive"
0x180058244  mov     edx, ebx
0x180058246  mov     ecx, 2
0x18005824b  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180058250  nop
0x180058251  mov     [rsp+320h+var_2C8], r15
0x180058256  lea     rcx, [rsp+320h+var_2C8]
0x18005825b  call    ?Release@?$CAutoPbrDelete@PEAVPrepareWinRE@WinREAgent@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<WinREAgent::PrepareWinRE *>::Release(void)
0x180058260  jmp     loc_18005819E
0x180058265  mov     [rbp+220h+var_288], r12
0x180058269  mov     [rbp+220h+var_280], r12
0x18005826d  mov     [rbp+220h+var_278], r12
0x180058271  mov     [rbp+220h+var_270], r12d
0x180058275  mov     rax, [rsp+320h+var_2C8]
0x18005827a  lea     rcx, [rsp+320h+var_2C8]
0x18005827f  mov     rax, [rax+18h]
0x180058283  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058288  mov     r8, rax
0x18005828b  mov     rcx, [rax]
0x18005828e  mov     rax, [rcx+98h]
0x180058295  lea     rdx, [rbp+220h+var_288]
0x180058299  mov     rcx, r8
0x18005829c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800582a1  mov     ebx, eax
0x1800582a3  test    eax, eax
0x1800582a5  jns     short loc_1800582E4
0x1800582a7  lea     rax, aFailedToEnumer_1; "Failed to enumerate mount points in reg"...
0x1800582ae  mov     [rsp+320h+var_2F8], rax
0x1800582b3  mov     [rsp+320h+var_300], 90h
0x1800582bb  lea     r9, aBaseResetUtilS_3; "base\\reset\\util\\src\\regoffline.cpp"
0x1800582c2  lea     r8, aPbrunloadoffli; "PbrUnloadOfflineHive"
0x1800582c9  mov     edx, ebx
0x1800582cb  mov     ecx, 2
0x1800582d0  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800582d5  nop
0x1800582d6  lea     rcx, [rbp+220h+var_288]
0x1800582da  call    ??1?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAA@XZ; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::~CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>(void)
0x1800582df  jmp     loc_180058251
0x1800582e4  lea     rcx, [rsp+320h+var_2A8]
0x1800582e9  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800582ee  nop
0x1800582ef  mov     r14, r12
0x1800582f2  mov     rbx, [rsp+320h+var_2A8]
0x1800582f7  cmp     r14, [rbp+220h+var_280]
0x1800582fb  jnb     loc_18005842A
0x180058301  mov     rdx, r14
0x180058304  lea     rcx, [rbp+220h+var_288]
0x180058308  call    ?GetAt@?$CAtlArray@PEAVProperty@PushButtonReset@@V?$CElementTraits@PEAVProperty@PushButtonReset@@@ATL@@@ATL@@QEBAAEBQEAVProperty@PushButtonReset@@_K@Z; ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(unsigned __int64)
0x18005830d  mov     r15, rax
0x180058310  lea     rcx, [rbp+220h+String1]
0x180058314  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180058319  nop
0x18005831a  mov     rcx, [rsp+320h+var_2C8]
0x18005831f  mov     rax, [rcx+18h]
0x180058323  lea     rcx, [rsp+320h+var_2C8]
0x180058328  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005832d  mov     r9, rax
0x180058330  mov     rcx, [rax]
0x180058333  mov     rax, [rcx+60h]
0x180058337  lea     r8, [rbp+220h+String1]
0x18005833b  mov     rdx, [r15]
0x18005833e  mov     rcx, r9
0x180058341  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058346  mov     esi, eax
0x180058348  mov     rax, [r15]
0x18005834b  test    esi, esi
0x18005834d  js      loc_1800583DA
0x180058353  mov     r9, [rbp+220h+String1]
0x180058357  mov     r8, rax
0x18005835a  lea     rdx, aRegistryFoundM; "Registry: Found mapping: [%s] -> [%s]"
0x180058361  xor     ecx, ecx
0x180058363  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180058368  mov     rdx, rdi; String2
0x18005836b  mov     rcx, [rbp+220h+String1]; String1
0x18005836f  call    cs:__imp__wcsicmp
0x180058375  test    eax, eax
0x180058377  jnz     short loc_1800583C5
0x180058379  mov     rdx, [r15]
0x18005837c  lea     rcx, [rdx-18h]
0x180058380  lea     rsi, [rbx-18h]
0x180058384  cmp     rcx, rsi
0x180058387  jz      short loc_1800583C5
0x180058389  cmp     [rsi+10h], r12d
0x18005838d  jl      short loc_1800583B2
0x18005838f  mov     rax, [rsi]
0x180058392  cmp     [rcx], rax
0x180058395  jnz     short loc_1800583B2
0x180058397  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18005839c  mov     rbx, rax
0x18005839f  mov     rcx, rsi; this
0x1800583a2  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800583a7  add     rbx, 18h
0x1800583ab  mov     [rsp+320h+var_2A8], rbx
0x1800583b0  jmp     short loc_1800583C5
0x1800583b2  mov     r8d, [rdx-10h]
0x1800583b6  lea     rcx, [rsp+320h+var_2A8]
0x1800583bb  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
  ... truncated ...
```
