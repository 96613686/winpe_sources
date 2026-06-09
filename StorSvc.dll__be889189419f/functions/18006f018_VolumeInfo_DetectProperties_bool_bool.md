# VolumeInfo::DetectProperties(bool,bool)

- ea: `0x18006f018`
- end: `0x18006f580`
- name: `?DetectProperties@VolumeInfo@@QEAA_N_N0@Z`
- size: `1384`
- prototype: `bool __fastcall(VolumeInfo *__hidden this, bool, bool)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x18006ccd0`

## callees

- `0x180001174`
- `0x180001248`
- `0x1800013c4`
- `0x180001c80`
- `0x180005824`
- `0x180005904`
- `0x18000d030`
- `0x18000d450`
- `0x180019d4c`
- `0x180019dd4`
- `0x18001c130`
- `0x18001c208`
- `0x18001dcf4`
- `0x18002ce80`
- `0x18002e740`
- `0x18003c1c0`
- `0x18006ef74`
- `0x18006ef94`
- `0x18006f018`
- `0x18007d490`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x18006f1b3`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x18006f1b3`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18006f213`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18006f2f9`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18006f213`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18006f2f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f3d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f3d1`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18006f366`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18006f366`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x18006f4db`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x18006f4db`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006f294`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006f294`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationByHandleW` at `0x18006f430`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationByHandleW` at `0x18006f430`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x18006f179`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x18006f179`

## string_xrefs

- `0x18006f441`: `onecore\drivers\storage\storsvc\diskmonitor\lib\dll\volumeinfo.cpp`
- `0x18006f4ee`: `onecore\drivers\storage\storsvc\diskmonitor\lib\dll\volumeinfo.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
char __fastcall VolumeInfo::DetectProperties(union _ULARGE_INTEGER *this)
{
  union _ULARGE_INTEGER *v2; // r14
  __int64 v3; // r8
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  const WCHAR *v7; // rax
  signed int DosDeviceW; // eax
  __int64 v9; // r15
  __int64 v10; // rax
  __int64 v11; // rsi
  const WCHAR *v12; // rax
  HANDLE FileW; // rax
  HANDLE v14; // rbx
  __int64 v16; // r9
  __int64 v17; // r9
  __int64 v18; // r8
  const char *v19; // r9
  __int64 v20; // rax
  const WCHAR *v21; // rax
  BOOL DiskFreeSpace; // ebx
  const char *v23; // r9
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 v26; // r9
  WCHAR *QuadPart; // [rsp+40h] [rbp-C0h] BYREF
  DWORD BytesReturned; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR *v29; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE hDevice; // [rsp+58h] [rbp-A8h] BYREF
  union _ULARGE_INTEGER TotalNumberOfBytes; // [rsp+60h] [rbp-A0h] BYREF
  union _ULARGE_INTEGER TotalNumberOfFreeBytes; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v33[16]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v34; // [rsp+80h] [rbp-80h]
  _BYTE v35[32]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR TargetPath[264]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR VolumeNameBuffer[264]; // [rsp+2C0h] [rbp+1C0h] BYREF
  WCHAR FileSystemNameBuffer[264]; // [rsp+4D0h] [rbp+3D0h] BYREF
  int OutBuffer; // [rsp+6E0h] [rbp+5E0h] BYREF
  DWORD v40; // [rsp+6E8h] [rbp+5E8h]
  wil::details::in1diag3 *retaddr; // [rsp+1728h] [rbp+1628h]

  v2 = this + 1;
  if ( (unsigned int)dword_1800BF170 > 5 )
  {
    QuadPart = (WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&this[1]);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)&dword_1800BF170,
      (__int64)byte_1800A9895,
      0,
      0,
      (const WCHAR **)&QuadPart);
  }
  this[5].LowPart = -1;
  std::wstring::wstring((__int64)v33, (__int64)v2);
  if ( v34 > 4 && *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v33) == 92 )
  {
    v4 = std::wstring::substr(v33, v35, v3);
    std::wstring::operator=(v33, v4);
    std::wstring::_Tidy_deallocate(v35);
    v5 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v33);
    if ( *(_WORD *)(v5 + 2 * v34 - 2) == 92 )
    {
      v6 = std::wstring::substr(v33, v35, 0);
      std::wstring::operator=(v33, v6);
      std::wstring::_Tidy_deallocate(v35);
    }
  }
  if ( (unsigned int)dword_1800BF170 > 5 )
  {
    QuadPart = (WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v33);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)&dword_1800BF170,
      (__int64)word_1800A985A,
      0,
      0,
      (const WCHAR **)&QuadPart);
  }
  v7 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v33);
  DosDeviceW = QueryDosDeviceW(v7, TargetPath, 0x105u);
  v9 = DosDeviceW;
  if ( DosDeviceW <= 0 )
    goto LABEL_21;
  if ( (unsigned __int64)DosDeviceW < 0x105 )
  {
    v10 = DosDeviceW;
    if ( (unsigned __int64)(2 * v9) >= 0x20A )
      _report_rangecheckfailure();
    TargetPath[v10] = 0;
    v11 = 0;
    do
    {
      TargetPath[v11] = _o_towlower(TargetPath[v11]);
      v11 = (unsigned int)(v11 + 1);
    }
    while ( (int)v11 < (int)v9 );
    if ( (unsigned int)dword_1800BF170 > 5 )
    {
      QuadPart = TargetPath;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)&dword_1800BF170,
        (__int64)byte_1800A97DB,
        0,
        0,
        (const WCHAR **)&QuadPart);
    }
    if ( wcsstr(TargetPath, L"floppy") )
    {
      if ( (unsigned int)dword_1800BF170 > 5 )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          (__int64)&dword_1800BF170,
          (__int64)&byte_1800A9797,
          0,
          0);
    }
    else if ( wcsstr(TargetPath, L"cdrom") && (unsigned int)dword_1800BF170 > 5 )
    {
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        (__int64)&dword_1800BF170,
        (__int64)&dword_1800A9754,
        0,
        0);
    }
  }
  hDevice = 0;
  BytesReturned = 0;
  TotalNumberOfFreeBytes.QuadPart = 0;
  TotalNumberOfBytes.QuadPart = 0;
  v12 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v2);
  FileW = CreateFileW(v12, 0x80000000, 3u, 0, 3u, 0x80u, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &hDevice,
    FileW);
  v14 = hDevice;
  if ( (((unsigned __int64)hDevice + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0
    || !DeviceIoControl(hDevice, 0x560000u, 0, 0, &OutBuffer, 0x1000u, &BytesReturned, 0) )
  {
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hDevice);
LABEL_21:
    std::wstring::_Tidy_deallocate(v33);
    return 0;
  }
  if ( BytesReturned < 0x20 )
  {
    if ( (unsigned int)dword_1800BF170 > 5 )
    {
      LODWORD(QuadPart) = GetLastError();
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_1800BF170,
        (__int64)byte_1800A9813,
        0,
        v17,
        (__int64)&QuadPart);
    }
  }
  else
  {
    if ( (unsigned int)dword_1800BF170 > 5 )
    {
      LODWORD(v29) = OutBuffer;
      LODWORD(QuadPart) = v40;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)&dword_1800BF170,
        (__int64)&dword_1800A96FC,
        0,
        v16,
        (__int64)&QuadPart,
        (__int64)&v29);
    }
    this[5].LowPart = v40;
  }
  if ( GetVolumeInformationByHandleW(v14, VolumeNameBuffer, 0x105u, 0, 0, 0, FileSystemNameBuffer, 0x105u) )
  {
    if ( (unsigned int)dword_1800BF170 > 5 )
    {
      QuadPart = FileSystemNameBuffer;
      v29 = VolumeNameBuffer;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (__int64)retaddr,
        (__int64)byte_1800A96A3,
        v18,
        (__int64)v19,
        (const WCHAR **)&v29,
        (const WCHAR **)&QuadPart);
    }
    std::wstring::assign(&this[6], VolumeNameBuffer);
    std::wstring::assign(&this[10], FileSystemNameBuffer);
  }
  else
  {
    wil::details::in1diag3::_Log_GetLastError(
      retaddr,
      (void *)0xF9,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\diskmonitor\\lib\\dll\\volumeinfo.cpp",
      v19);
  }
  v20 = std::operator+<unsigned short>(v35, v2);
  v21 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v20);
  DiskFreeSpace = GetDiskFreeSpaceExW(v21, 0, &TotalNumberOfBytes, &TotalNumberOfFreeBytes);
  if ( !DiskFreeSpace )
    wil::details::in1diag3::_Log_GetLastError(
      retaddr,
      (void *)0x112,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\diskmonitor\\lib\\dll\\volumeinfo.cpp",
      v23);
  std::wstring::_Tidy_deallocate(v35);
  if ( DiskFreeSpace )
  {
    if ( (unsigned int)dword_1800BF170 > 5 )
    {
      QuadPart = (WCHAR *)TotalNumberOfFreeBytes.QuadPart;
      v29 = (WCHAR *)TotalNumberOfBytes.QuadPart;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        v24,
        (__int64)byte_1800A963D,
        v25,
        v26,
        (__int64)&v29,
        (__int64)&QuadPart);
    }
    this[14] = TotalNumberOfBytes;
    this[15] = TotalNumberOfFreeBytes;
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hDevice);
  std::wstring::_Tidy_deallocate(v33);
  return 1;
}

```

## disassembly

```asm
0x18006f018  push    rbp
0x18006f01a  push    rbx
0x18006f01b  push    rsi
0x18006f01c  push    rdi
0x18006f01d  push    r14
0x18006f01f  push    r15
0x18006f021  lea     rbp, [rsp-15F8h]
0x18006f029  mov     eax, 16F8h
0x18006f02e  call    _alloca_probe
0x18006f033  sub     rsp, rax
0x18006f036  mov     rax, cs:__security_cookie
0x18006f03d  xor     rax, rsp
0x18006f040  mov     [rbp+1620h+var_40], rax
0x18006f047  mov     rdi, rcx
0x18006f04a  mov     eax, cs:dword_1800BF170
0x18006f050  lea     r14, [rcx+8]
0x18006f054  lea     rsi, dword_1800BF170
0x18006f05b  cmp     eax, 5
0x18006f05e  jbe     short loc_18006F08C
0x18006f060  mov     rcx, r14
0x18006f063  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18006f068  mov     [rsp+1720h+var_16E0], rax
0x18006f06d  lea     rax, [rsp+1720h+var_16E0]
0x18006f072  mov     qword ptr [rsp+1720h+dwCreationDisposition], rax
0x18006f077  xor     r9d, r9d
0x18006f07a  xor     r8d, r8d
0x18006f07d  lea     rdx, byte_1800A9895
0x18006f084  mov     rcx, rsi
0x18006f087  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18006f08c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18006f090  mov     [rdi+28h], ebx
0x18006f093  mov     rdx, r14
0x18006f096  lea     rcx, [rsp+1720h+var_16B0]
0x18006f09b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18006f0a0  nop
0x18006f0a1  lea     r8d, [rbx+5]
0x18006f0a5  cmp     [rbp+1620h+var_16A0], r8
0x18006f0a9  jbe     short loc_18006F127
0x18006f0ab  lea     rcx, [rsp+1720h+var_16B0]
0x18006f0b0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18006f0b5  cmp     word ptr [rax], 5Ch ; '\'
0x18006f0b9  jnz     short loc_18006F127
0x18006f0bb  mov     r9, rbx
0x18006f0be  lea     rdx, [rbp+1620h+var_1690]
0x18006f0c2  lea     rcx, [rsp+1720h+var_16B0]
0x18006f0c7  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x18006f0cc  nop
0x18006f0cd  mov     rdx, rax
0x18006f0d0  lea     rcx, [rsp+1720h+var_16B0]
0x18006f0d5  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18006f0da  nop
0x18006f0db  lea     rcx, [rbp+1620h+var_1690]
0x18006f0df  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006f0e4  lea     rcx, [rsp+1720h+var_16B0]
0x18006f0e9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18006f0ee  mov     r9, [rbp+1620h+var_16A0]
0x18006f0f2  cmp     word ptr [rax+r9*2-2], 5Ch ; '\'
0x18006f0f9  jnz     short loc_18006F127
0x18006f0fb  dec     r9
0x18006f0fe  xor     r8d, r8d
0x18006f101  lea     rdx, [rbp+1620h+var_1690]
0x18006f105  lea     rcx, [rsp+1720h+var_16B0]
0x18006f10a  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x18006f10f  nop
0x18006f110  mov     rdx, rax
0x18006f113  lea     rcx, [rsp+1720h+var_16B0]
0x18006f118  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18006f11d  nop
0x18006f11e  lea     rcx, [rbp+1620h+var_1690]
0x18006f122  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006f127  mov     eax, cs:dword_1800BF170
0x18006f12d  cmp     eax, 5
0x18006f130  jbe     short loc_18006F160
0x18006f132  lea     rcx, [rsp+1720h+var_16B0]
0x18006f137  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18006f13c  mov     [rsp+1720h+var_16E0], rax
0x18006f141  lea     rax, [rsp+1720h+var_16E0]
0x18006f146  mov     qword ptr [rsp+1720h+dwCreationDisposition], rax
0x18006f14b  xor     r9d, r9d
0x18006f14e  xor     r8d, r8d
0x18006f151  lea     rdx, word_1800A985A
0x18006f158  mov     rcx, rsi
0x18006f15b  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18006f160  lea     rcx, [rsp+1720h+var_16B0]
0x18006f165  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18006f16a  mov     rcx, rax; lpDeviceName
0x18006f16d  mov     ebx, 105h
0x18006f172  mov     r8d, ebx; ucchMax
0x18006f175  lea     rdx, [rbp+1620h+TargetPath]; lpTargetPath
0x18006f179  call    cs:__imp_QueryDosDeviceW
0x18006f17f  movsxd  r15, eax
0x18006f182  test    eax, eax
0x18006f184  jle     loc_18006F2C3
0x18006f18a  mov     rax, r15
0x18006f18d  cmp     r15, rbx
0x18006f190  jnb     loc_18006F242
0x18006f196  add     rax, rax
0x18006f199  cmp     rax, 20Ah
0x18006f19f  jnb     loc_18006F57A
0x18006f1a5  xor     ecx, ecx
0x18006f1a7  mov     [rbp+rax+1620h+TargetPath], cx
0x18006f1ac  xor     esi, esi
0x18006f1ae  movzx   ecx, [rbp+rsi*2+1620h+TargetPath]
0x18006f1b3  call    cs:__imp__o_towlower
0x18006f1b9  mov     [rbp+rsi*2+1620h+TargetPath], ax
0x18006f1be  inc     esi
0x18006f1c0  cmp     esi, r15d
0x18006f1c3  jl      short loc_18006F1AE
0x18006f1c5  mov     eax, cs:dword_1800BF170
0x18006f1cb  cmp     eax, 5
0x18006f1ce  jbe     short loc_18006F201
0x18006f1d0  lea     rax, [rbp+1620h+TargetPath]
0x18006f1d4  mov     [rsp+1720h+var_16E0], rax
0x18006f1d9  lea     rax, [rsp+1720h+var_16E0]
0x18006f1de  mov     qword ptr [rsp+1720h+dwCreationDisposition], rax
0x18006f1e3  xor     r9d, r9d
0x18006f1e6  xor     r8d, r8d
0x18006f1e9  lea     rdx, byte_1800A97DB
0x18006f1f0  lea     rsi, dword_1800BF170
0x18006f1f7  mov     rcx, rsi
0x18006f1fa  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18006f1ff  jmp     short loc_18006F208
0x18006f201  lea     rsi, dword_1800BF170
0x18006f208  lea     rdx, aFloppy; "floppy"
0x18006f20f  lea     rcx, [rbp+1620h+TargetPath]; Str
0x18006f213  call    cs:__imp_wcsstr
0x18006f219  test    rax, rax
0x18006f21c  jz      loc_18006F2EE
0x18006f222  mov     eax, cs:dword_1800BF170
0x18006f228  cmp     eax, 5
0x18006f22b  jbe     short loc_18006F242
0x18006f22d  xor     r9d, r9d
0x18006f230  xor     r8d, r8d
0x18006f233  lea     rdx, byte_1800A9797
0x18006f23a  mov     rcx, rsi
0x18006f23d  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18006f242  mov     [rsp+1720h+hDevice], 0
0x18006f24b  mov     [rsp+1720h+BytesReturned], 0
0x18006f253  mov     qword ptr [rsp+1720h+TotalNumberOfFreeBytes], 0
0x18006f25c  mov     qword ptr [rsp+1720h+TotalNumberOfBytes], 0
0x18006f265  mov     rcx, r14
0x18006f268  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18006f26d  mov     [rsp+1720h+hTemplateFile], 0; hTemplateFile
0x18006f276  mov     [rsp+1720h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18006f27e  mov     r8d, 3; dwShareMode
0x18006f284  mov     [rsp+1720h+dwCreationDisposition], r8d; dwCreationDisposition
0x18006f289  xor     r9d, r9d; lpSecurityAttributes
0x18006f28c  mov     edx, 80000000h; dwDesiredAccess
0x18006f291  mov     rcx, rax; lpFileName
0x18006f294  call    cs:__imp_CreateFileW
0x18006f29a  mov     rdx, rax
0x18006f29d  lea     rcx, [rsp+1720h+hDevice]
0x18006f2a2  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18006f2a7  mov     rbx, [rsp+1720h+hDevice]
0x18006f2ac  lea     rax, [rbx+1]
0x18006f2b0  test    rax, 0FFFFFFFFFFFFFFFEh
0x18006f2b6  jnz     short loc_18006F331
0x18006f2b8  lea     rcx, [rsp+1720h+hDevice]
0x18006f2bd  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18006f2c2  nop
0x18006f2c3  lea     rcx, [rsp+1720h+var_16B0]
0x18006f2c8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006f2cd  xor     al, al
0x18006f2cf  mov     rcx, [rbp+1620h+var_40]
0x18006f2d6  xor     rcx, rsp; StackCookie
0x18006f2d9  call    __security_check_cookie
0x18006f2de  add     rsp, 16F8h
0x18006f2e5  pop     r15
0x18006f2e7  pop     r14
0x18006f2e9  pop     rdi
0x18006f2ea  pop     rsi
0x18006f2eb  pop     rbx
0x18006f2ec  pop     rbp
0x18006f2ed  retn
0x18006f2ee  lea     rdx, aCdrom; "cdrom"
0x18006f2f5  lea     rcx, [rbp+1620h+TargetPath]; Str
0x18006f2f9  call    cs:__imp_wcsstr
0x18006f2ff  test    rax, rax
0x18006f302  jz      loc_18006F242
0x18006f308  mov     eax, cs:dword_1800BF170
0x18006f30e  cmp     eax, 5
0x18006f311  jbe     loc_18006F242
0x18006f317  xor     r9d, r9d
0x18006f31a  xor     r8d, r8d
0x18006f31d  lea     rdx, dword_1800A9754
0x18006f324  mov     rcx, rsi
0x18006f327  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18006f32c  jmp     loc_18006F242
0x18006f331  mov     [rsp+1720h+lpOverlapped], 0; lpOverlapped
0x18006f33a  lea     rax, [rsp+1720h+BytesReturned]
0x18006f33f  mov     [rsp+1720h+hTemplateFile], rax; lpBytesReturned
0x18006f344  mov     [rsp+1720h+dwFlagsAndAttributes], 1000h; nOutBufferSize
0x18006f34c  lea     rax, [rbp+1620h+OutBuffer]
0x18006f353  mov     qword ptr [rsp+1720h+dwCreationDisposition], rax; lpOutBuffer
0x18006f358  xor     r9d, r9d; nInBufferSize
0x18006f35b  xor     r8d, r8d; lpInBuffer
0x18006f35e  mov     edx, 560000h; dwIoControlCode
0x18006f363  mov     rcx, rbx; hDevice
0x18006f366  call    cs:__imp_DeviceIoControl
0x18006f36c  test    eax, eax
0x18006f36e  jnz     short loc_18006F375
0x18006f370  jmp     loc_18006F2B8
0x18006f375  cmp     [rsp+1720h+BytesReturned], 20h ; ' '
0x18006f37a  mov     eax, cs:dword_1800BF170
0x18006f380  jb      short loc_18006F3CC
0x18006f382  cmp     eax, 5
0x18006f385  jbe     short loc_18006F3C1
0x18006f387  mov     eax, [rbp+1620h+OutBuffer]
0x18006f38d  mov     dword ptr [rsp+1720h+var_16D0], eax
0x18006f391  mov     eax, [rbp+1620h+var_1038]
0x18006f397  mov     dword ptr [rsp+1720h+var_16E0], eax
0x18006f39b  lea     rax, [rsp+1720h+var_16D0]
0x18006f3a0  mov     qword ptr [rsp+1720h+dwFlagsAndAttributes], rax
0x18006f3a5  lea     rax, [rsp+1720h+var_16E0]
0x18006f3aa  mov     qword ptr [rsp+1720h+dwCreationDisposition], rax
0x18006f3af  xor     r8d, r8d
0x18006f3b2  lea     rdx, dword_1800A96FC
0x18006f3b9  mov     rcx, rsi
0x18006f3bc  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18006f3c1  mov     eax, [rbp+1620h+var_1038]
0x18006f3c7  mov     [rdi+28h], eax
0x18006f3ca  jmp     short loc_18006F3F7
0x18006f3cc  cmp     eax, 5
0x18006f3cf  jbe     short loc_18006F3F7
0x18006f3d1  call    cs:__imp_GetLastError
0x18006f3d7  mov     dword ptr [rsp+1720h+var_16E0], eax
0x18006f3db  lea     rax, [rsp+1720h+var_16E0]
0x18006f3e0  mov     qword ptr [rsp+1720h+dwCreationDisposition], rax
0x18006f3e5  xor     r8d, r8d
0x18006f3e8  lea     rdx, byte_1800A9813
0x18006f3ef  mov     rcx, rsi
0x18006f3f2  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18006f3f7  mov     dword ptr [rsp+1720h+lpOverlapped], 105h; nFileSystemNameSize
0x18006f3ff  lea     rax, [rbp+1620h+FileSystemNameBuffer]
0x18006f406  mov     [rsp+1720h+hTemplateFile], rax; lpFileSystemNameBuffer
0x18006f40b  mov     qword ptr [rsp+1720h+dwFlagsAndAttributes], 0; lpFileSystemFlags
0x18006f414  mov     qword ptr [rsp+1720h+dwCreationDisposition], 0; lpMaximumComponentLength
0x18006f41d  xor     r9d, r9d; lpVolumeSerialNumber
0x18006f420  mov     r8d, 105h; nVolumeNameSize
0x18006f426  lea     rdx, [rbp+1620h+VolumeNameBuffer]; lpVolumeNameBuffer
0x18006f42d  mov     rcx, rbx; hFile
0x18006f430  call    cs:__imp_GetVolumeInformationByHandleW
0x18006f436  mov     rcx, [rbp+1628h]; this
0x18006f43d  test    eax, eax
0x18006f43f  jnz     short loc_18006F454
0x18006f441  lea     r8, aOnecoreDrivers_23; "onecore\\drivers\\storage\\storsvc\\dis"...
0x18006f448  mov     edx, 0F9h; void *
0x18006f44d  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18006f452  jmp     short loc_18006F4B7
0x18006f454  mov     eax, cs:dword_1800BF170
0x18006f45a  cmp     eax, 5
0x18006f45d  jbe     short loc_18006F497
0x18006f45f  lea     rax, [rbp+1620h+FileSystemNameBuffer]
0x18006f466  mov     [rsp+1720h+var_16E0], rax
0x18006f46b  lea     rax, [rbp+1620h+VolumeNameBuffer]
0x18006f472  mov     [rsp+1720h+var_16D0], rax
0x18006f477  lea     rax, [rsp+1720h+var_16E0]
0x18006f47c  mov     qword ptr [rsp+1720h+dwFlagsAndAttributes], rax
0x18006f481  lea     rax, [rsp+1720h+var_16D0]
0x18006f486  mov     qword ptr [rsp+1720h+dwCreationDisposition], rax
0x18006f48b  lea     rdx, byte_1800A96A3
0x18006f492  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18006f497  lea     rcx, [rdi+30h]
0x18006f49b  lea     rdx, [rbp+1620h+VolumeNameBuffer]
0x18006f4a2  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18006f4a7  lea     rcx, [rdi+50h]
0x18006f4ab  lea     rdx, [rbp+1620h+FileSystemNameBuffer]
0x18006f4b2  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18006f4b7  mov     rdx, r14
0x18006f4ba  lea     rcx, [rbp+1620h+var_1690]
0x18006f4be  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@G@Z; std::operator+<ushort>(std::wstring const &,ushort)
0x18006f4c3  nop
0x18006f4c4  mov     rcx, rax
0x18006f4c7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18006f4cc  lea     r9, [rsp+1720h+TotalNumberOfFreeBytes]; lpTotalNumberOfFreeBytes
0x18006f4d1  lea     r8, [rsp+1720h+TotalNumberOfBytes]; lpTotalNumberOfBytes
0x18006f4d6  xor     edx, edx; lpFreeBytesAvailableToCaller
0x18006f4d8  mov     rcx, rax; lpDirectoryName
0x18006f4db  call    cs:__imp_GetDiskFreeSpaceExW
0x18006f4e1  mov     ebx, eax
0x18006f4e3  mov     rcx, [rbp+1628h]; this
0x18006f4ea  test    eax, eax
0x18006f4ec  jnz     short loc_18006F500
0x18006f4ee  lea     r8, aOnecoreDrivers_23; "onecore\\drivers\\storage\\storsvc\\dis"...
0x18006f4f5  mov     edx, 112h; void *
0x18006f4fa  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18006f4ff  nop
0x18006f500  lea     rcx, [rbp+1620h+var_1690]
0x18006f504  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006f509  test    ebx, ebx
0x18006f50b  jz      short loc_18006F55E
0x18006f50d  mov     eax, cs:dword_1800BF170
0x18006f513  cmp     eax, 5
0x18006f516  jbe     short loc_18006F54C
0x18006f518  mov     rax, qword ptr [rsp+1720h+TotalNumberOfFreeBytes]
0x18006f51d  mov     [rsp+1720h+var_16E0], rax
0x18006f522  mov     rax, qword ptr [rsp+1720h+TotalNumberOfBytes]
0x18006f527  mov     [rsp+1720h+var_16D0], rax
0x18006f52c  lea     rax, [rsp+1720h+var_16E0]
0x18006f531  mov     qword ptr [rsp+1720h+dwFlagsAndAttributes], rax
  ... truncated ...
```
