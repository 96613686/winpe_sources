# DiskInfo::DetectProperties(bool,bool)

- ea: `0x18006e550`
- end: `0x18006ecde`
- name: `?DetectProperties@DiskInfo@@QEAA_N_N0@Z`
- size: `1934`
- prototype: `bool __fastcall(DiskInfo *__hidden this, bool, bool)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x18006c598`

## callees

- `0x180001174`
- `0x1800013c4`
- `0x180001c80`
- `0x1800055d4`
- `0x180005718`
- `0x1800057c4`
- `0x18000d030`
- `0x180019d4c`
- `0x18001c130`
- `0x18001dcf4`
- `0x18002ce80`
- `0x18005e8cc`
- `0x18006e550`
- `0x18006ece4`
- `0x18006ef74`
- `0x18007d490`

## import_xrefs

- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18006e6b0`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18006e728`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18006e80a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18006e895`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18006e938`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18006eafa`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18006ec83`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18006e6b0`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18006e728`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18006e80a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18006e895`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18006e938`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18006eafa`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18006ec83`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006e654`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006e654`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18006ebdb`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18006ebdb`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18006ec56`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18006ec56`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18006eb7c`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18006eb7c`
- `DEVOBJ!DevObjOpenDeviceInterface` at `0x18006ebab`
- `DEVOBJ!DevObjOpenDeviceInterface` at `0x18006ebab`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_IDW` at `0x18006ec07`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_IDW` at `0x18006ec07`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Parent` at `0x18006ebec`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Parent` at `0x18006ebec`

## string_xrefs

- `0x18006e739`: `onecore\drivers\storage\storsvc\diskmonitor\lib\dll\diskinfo.cpp`
- `0x18006e81b`: `onecore\drivers\storage\storsvc\diskmonitor\lib\dll\diskinfo.cpp`
- `0x18006e8a6`: `onecore\drivers\storage\storsvc\diskmonitor\lib\dll\diskinfo.cpp`
- `0x18006e949`: `onecore\drivers\storage\storsvc\diskmonitor\lib\dll\diskinfo.cpp`
- `0x18006eb0b`: `onecore\drivers\storage\storsvc\diskmonitor\lib\dll\diskinfo.cpp`
- `0x18006ec94`: `onecore\drivers\storage\storsvc\diskmonitor\lib\dll\diskinfo.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall DiskInfo::DetectProperties(DiskInfo *this)
{
  char *v2; // r14
  const WCHAR *v3; // rax
  char v4; // r15
  HANDLE FileW; // rax
  HANDLE v6; // rbx
  __int64 v8; // r9
  __int64 v9; // r8
  const char *v10; // r9
  unsigned int v11; // eax
  __int64 v12; // r8
  const char *v13; // r9
  const char *v14; // r9
  const char *v15; // r9
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 v22; // rax
  __int64 v23; // r8
  __int64 v24; // rax
  __int64 v25; // r8
  __int64 v26; // rax
  __int64 v27; // r8
  __int64 v28; // rax
  __int64 v29; // r8
  const char *v30; // r9
  __int64 DeviceInfoList; // rsi
  __int64 v32; // rax
  const char *v33; // r9
  DWORD BytesReturned; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v35; // [rsp+54h] [rbp-ACh] BYREF
  const WCHAR *v36; // [rsp+58h] [rbp-A8h] BYREF
  DEVNODE pdnDevInst; // [rsp+60h] [rbp-A0h] BYREF
  const unsigned __int16 *v38; // [rsp+68h] [rbp-98h] BYREF
  const unsigned __int16 *OffsetString; // [rsp+70h] [rbp-90h] BYREF
  HANDLE hDevice; // [rsp+78h] [rbp-88h] BYREF
  const unsigned __int16 *v41; // [rsp+80h] [rbp-80h] BYREF
  WCHAR *v42; // [rsp+88h] [rbp-78h] BYREF
  __int64 InBuffer; // [rsp+90h] [rbp-70h] BYREF
  int v44; // [rsp+98h] [rbp-68h]
  __int64 OutBuffer; // [rsp+A0h] [rbp-60h] BYREF
  int v46; // [rsp+A8h] [rbp-58h]
  __int128 v47; // [rsp+B0h] [rbp-50h] BYREF
  _OWORD v48[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v49; // [rsp+E0h] [rbp-20h] BYREF
  DEVINST dnDevInst[4]; // [rsp+F0h] [rbp-10h]
  __int128 v51; // [rsp+100h] [rbp+0h]
  WCHAR Buffer[2]; // [rsp+110h] [rbp+10h] BYREF
  int v53; // [rsp+114h] [rbp+14h]
  int v54; // [rsp+118h] [rbp+18h]
  unsigned int v55; // [rsp+11Ch] [rbp+1Ch]
  unsigned int v56; // [rsp+120h] [rbp+20h]
  unsigned int v57; // [rsp+124h] [rbp+24h]
  const unsigned __int16 *v58; // [rsp+128h] [rbp+28h]
  unsigned int v59; // [rsp+130h] [rbp+30h]
  _DWORD v60[1015]; // [rsp+134h] [rbp+34h]
  wil::details::in1diag3 *retaddr; // [rsp+1148h] [rbp+1048h]

  v2 = (char *)this + 8;
  if ( (unsigned int)dword_1800BF170 > 5 )
  {
    v36 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 8);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)&dword_1800BF170,
      (__int64)&unk_1800A9600,
      0,
      0,
      &v36);
  }
  *((_DWORD *)this + 18) = -1;
  *((_DWORD *)this + 20) = -1;
  *((_DWORD *)this + 21) = -1;
  *((_QWORD *)this + 14) = -1;
  *((_DWORD *)this + 22) = -1;
  *((_DWORD *)this + 24) = -1;
  *((_DWORD *)this + 25) = -1;
  *((_QWORD *)this + 13) = -1;
  hDevice = 0;
  OutBuffer = 0;
  v46 = 0;
  v47 = 0;
  InBuffer = 0;
  v44 = 0;
  v49 = 0;
  *(_OWORD *)dnDevInst = 0;
  v51 = 0;
  memset(v48, 0, sizeof(v48));
  pdnDevInst = 0;
  BytesReturned = 0;
  v3 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v2);
  v4 = 1;
  FileW = CreateFileW(v3, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &hDevice,
    FileW);
  v6 = hDevice;
  if ( hDevice == (HANDLE)-1LL )
  {
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hDevice);
    return 0;
  }
  else
  {
    if ( DeviceIoControl(hDevice, 0x2D1080u, 0, 0, &OutBuffer, 0xCu, &BytesReturned, 0) )
    {
      if ( (unsigned int)dword_1800BF170 > 5 )
      {
        LODWORD(v38) = HIDWORD(OutBuffer);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_1800BF170,
          (__int64)byte_1800A95BB,
          0,
          v8,
          (__int64)&v38);
      }
      *((_DWORD *)this + 18) = HIDWORD(OutBuffer);
      if ( DeviceIoControl(v6, 0x700A0u, 0, 0, Buffer, 0x1000u, &BytesReturned, 0) )
      {
        *((_DWORD *)this + 22) = v54;
        v11 = v57;
        *((_DWORD *)this + 24) = v57;
        *((_DWORD *)this + 25) = v11;
        *((_QWORD *)this + 14) = v58;
        if ( (unsigned int)dword_1800BF170 > 5 )
        {
          LODWORD(v38) = *(_DWORD *)((char *)v60 + v59);
          LODWORD(v41) = v60[0];
          OffsetString = v58;
          v35 = v57;
          LODWORD(v36) = v54;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v59,
            (__int64)&word_1800A953E,
            v9,
            (__int64)v10,
            (__int64)&v36,
            (__int64)&v35,
            (__int64)&OffsetString,
            (__int64)&v41,
            (__int64)&v38);
        }
        *((_DWORD *)this + 20) = v60[0];
      }
      else
      {
        wil::details::in1diag3::_Log_GetLastError(
          retaddr,
          (void *)0x118,
          (unsigned int)"onecore\\drivers\\storage\\storsvc\\diskmonitor\\lib\\dll\\diskinfo.cpp",
          v10);
      }
      if ( DeviceIoControl(v6, 0x700F0u, 0, 0, &v47, 0x10u, &BytesReturned, 0) )
      {
        if ( (unsigned int)dword_1800BF170 > 5 )
        {
          OffsetString = (const unsigned __int16 *)*((_QWORD *)&v47 + 1);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
            (__int64)&dword_1800BF170,
            (__int64)&byte_1800A94F7,
            v12,
            (__int64)v13,
            (__int64)&OffsetString);
        }
        *((_QWORD *)this + 13) = *((_QWORD *)&v47 + 1);
      }
      else
      {
        wil::details::in1diag3::_Log_GetLastError(
          retaddr,
          (void *)0x13D,
          (unsigned int)"onecore\\drivers\\storage\\storsvc\\diskmonitor\\lib\\dll\\diskinfo.cpp",
          v13);
      }
      if ( DeviceIoControl(v6, 0x70050u, 0, 0, Buffer, 0x1000u, &BytesReturned, 0) )
      {
        if ( (unsigned int)dword_1800BF170 > 5 )
        {
          LODWORD(v36) = v53;
          v35 = *(_DWORD *)Buffer;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (__int64)&dword_1800BF170,
            (__int64)&unk_1800A94A0,
            0,
            (__int64)v14,
            (__int64)&v35,
            (__int64)&v36);
        }
        *((_DWORD *)this + 21) = v53;
      }
      else
      {
        wil::details::in1diag3::_Log_GetLastError(
          retaddr,
          (void *)0x158,
          (unsigned int)"onecore\\drivers\\storage\\storsvc\\diskmonitor\\lib\\dll\\diskinfo.cpp",
          v14);
      }
      InBuffer = 0;
      if ( DeviceIoControl(v6, 0x2D1400u, &InBuffer, 0xCu, Buffer, 0x1000u, &BytesReturned, 0) )
      {
        if ( (unsigned int)dword_1800BF170 > 5 )
        {
          OffsetString = (const unsigned __int16 *)GetOffsetString(Buffer, BytesReturned, (unsigned int)v58);
          v41 = (const unsigned __int16 *)GetOffsetString(Buffer, v16, v57);
          v38 = (const unsigned __int16 *)GetOffsetString(Buffer, v17, v56);
          v42 = (WCHAR *)GetOffsetString(Buffer, v18, v55);
          LODWORD(v36) = HIDWORD(v58);
          v35 = BYTE2(v54);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v19,
            (__int64)&unk_1800A9418,
            v20,
            v21,
            (__int64)&v35,
            (__int64)&v36,
            (const unsigned __int16 **)&v42,
            &v38,
            &v41,
            &OffsetString);
        }
        v22 = GetOffsetString(Buffer, BytesReturned, v55);
        v23 = -1;
        do
          ++v23;
        while ( *(_BYTE *)(v22 + v23) );
        std::string::_Assign<char>((char *)this + 152, v22, v23);
        v24 = GetOffsetString(Buffer, BytesReturned, v56);
        v25 = -1;
        do
          ++v25;
        while ( *(_BYTE *)(v24 + v25) );
        std::string::_Assign<char>((char *)this + 120, v24, v25);
        v26 = GetOffsetString(Buffer, BytesReturned, v57);
        v27 = -1;
        do
          ++v27;
        while ( *(_BYTE *)(v26 + v27) );
        std::string::_Assign<char>((char *)this + 184, v26, v27);
        v28 = GetOffsetString(Buffer, BytesReturned, (unsigned int)v58);
        v29 = -1;
        do
          ++v29;
        while ( *(_BYTE *)(v28 + v29) );
        std::string::_Assign<char>((char *)this + 216, v28, v29);
        *((_DWORD *)this + 23) = HIDWORD(v58);
      }
      else
      {
        wil::details::in1diag3::_Log_GetLastError(
          retaddr,
          (void *)0x175,
          (unsigned int)"onecore\\drivers\\storage\\storsvc\\diskmonitor\\lib\\dll\\diskinfo.cpp",
          v15);
      }
      InBuffer = 6;
      if ( DeviceIoControl(v6, 0x2D1400u, &InBuffer, 0xCu, Buffer, 0x1000u, &BytesReturned, 0) )
      {
        if ( (unsigned int)dword_1800BF170 > 5 )
        {
          LODWORD(v36) = v57;
          v35 = v56;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (__int64)&dword_1800BF170,
            (__int64)&byte_1800A93AF,
            0,
            (__int64)v30,
            (__int64)&v35,
            (__int64)&v36);
        }
        *((_DWORD *)this + 24) = v57;
        *((_DWORD *)this + 25) = v56;
      }
      else
      {
        wil::details::in1diag3::_Log_GetLastError(
          retaddr,
          (void *)0x19B,
          (unsigned int)"onecore\\drivers\\storage\\storsvc\\diskmonitor\\lib\\dll\\diskinfo.cpp",
          v30);
      }
      DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
      if ( DeviceInfoList != -1 )
      {
        LODWORD(v48[0]) = 32;
        v32 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v2);
        if ( (unsigned int)DevObjOpenDeviceInterface(DeviceInfoList, v32, 0, v48) )
        {
          LODWORD(v49) = 48;
          DevObjGetDeviceInterfaceDetail(DeviceInfoList, v48, 0, 0, 0, &v49);
          if ( !CM_Get_Parent(&pdnDevInst, dnDevInst[1], 0) && !CM_Get_Device_IDW(pdnDevInst, Buffer, 0x800u, 0) )
          {
            if ( (unsigned int)dword_1800BF170 > 5 )
            {
              v42 = Buffer;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
                (__int64)&dword_1800BF170,
                (__int64)word_1800A9372,
                0,
                0,
                (const WCHAR **)&v42);
            }
            std::wstring::assign((char *)this + 40, Buffer);
          }
        }
        DevObjDestroyDeviceInfoList(DeviceInfoList);
      }
      if ( !DeviceIoControl(v6, 0x7421Cu, 0, 0, 0, 0, &BytesReturned, 0) )
        wil::details::in1diag3::_Log_GetLastError(
          retaddr,
          (void *)0x1ED,
          (unsigned int)"onecore\\drivers\\storage\\storsvc\\diskmonitor\\lib\\dll\\diskinfo.cpp",
          v33);
    }
    else
    {
      v4 = 0;
    }
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hDevice);
    return v4;
  }
}

```

## disassembly

```asm
0x18006e550  mov     [rsp-8+arg_8], rbx
0x18006e555  mov     [rsp-8+arg_10], rsi
0x18006e55a  push    rbp
0x18006e55b  push    rdi
0x18006e55c  push    r12
0x18006e55e  push    r14
0x18006e560  push    r15
0x18006e562  lea     rbp, [rsp-1020h]
0x18006e56a  mov     eax, 1120h
0x18006e56f  call    _alloca_probe
0x18006e574  sub     rsp, rax
0x18006e577  mov     rax, cs:__security_cookie
0x18006e57e  xor     rax, rsp
0x18006e581  mov     [rbp+1040h+var_30], rax
0x18006e588  mov     rdi, rcx
0x18006e58b  mov     eax, cs:dword_1800BF170
0x18006e591  lea     r14, [rcx+8]
0x18006e595  cmp     eax, 5
0x18006e598  jbe     short loc_18006E5CA
0x18006e59a  mov     rcx, r14
0x18006e59d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18006e5a2  mov     [rsp+1140h+var_10E8], rax
0x18006e5a7  lea     rax, [rsp+1140h+var_10E8]
0x18006e5ac  mov     qword ptr [rsp+1140h+dwCreationDisposition], rax
0x18006e5b1  xor     r9d, r9d
0x18006e5b4  xor     r8d, r8d
0x18006e5b7  lea     rdx, unk_1800A9600
0x18006e5be  lea     rcx, dword_1800BF170
0x18006e5c5  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18006e5ca  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18006e5ce  mov     [rdi+48h], esi
0x18006e5d1  mov     [rdi+50h], esi
0x18006e5d4  mov     [rdi+54h], esi
0x18006e5d7  mov     [rdi+70h], rsi
0x18006e5db  mov     [rdi+58h], esi
0x18006e5de  mov     [rdi+60h], esi
0x18006e5e1  mov     [rdi+64h], esi
0x18006e5e4  mov     [rdi+68h], rsi
0x18006e5e8  xor     r12d, r12d
0x18006e5eb  mov     [rsp+1140h+hDevice], r12
0x18006e5f0  xor     eax, eax
0x18006e5f2  mov     [rbp+1040h+OutBuffer], rax
0x18006e5f6  mov     [rbp+1040h+var_1098], eax
0x18006e5f9  xorps   xmm0, xmm0
0x18006e5fc  movups  [rbp+1040h+var_1090], xmm0
0x18006e600  mov     [rbp+1040h+InBuffer], rax
0x18006e604  mov     [rbp+1040h+var_10A8], eax
0x18006e607  movups  [rbp+1040h+var_1060], xmm0
0x18006e60b  movups  xmmword ptr [rbp+1040h+dnDevInst], xmm0
0x18006e60f  movups  [rbp+1040h+var_1040], xmm0
0x18006e613  movups  [rbp+1040h+var_1080], xmm0
0x18006e617  movups  [rbp+1040h+var_1070], xmm0
0x18006e61b  mov     [rsp+1140h+pdnDevInst], r12d
0x18006e620  mov     [rsp+1140h+BytesReturned], r12d
0x18006e625  mov     rcx, r14
0x18006e628  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18006e62d  mov     [rsp+1140h+hTemplateFile], r12; hTemplateFile
0x18006e632  mov     [rsp+1140h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18006e63a  mov     [rsp+1140h+dwCreationDisposition], 3; dwCreationDisposition
0x18006e642  xor     r9d, r9d; lpSecurityAttributes
0x18006e645  lea     r15d, [rsi+2]
0x18006e649  mov     r8d, r15d; dwShareMode
0x18006e64c  mov     edx, 80000000h; dwDesiredAccess
0x18006e651  mov     rcx, rax; lpFileName
0x18006e654  call    cs:__imp_CreateFileW
0x18006e65a  mov     rdx, rax
0x18006e65d  lea     rcx, [rsp+1140h+hDevice]
0x18006e662  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18006e667  mov     rbx, [rsp+1140h+hDevice]
0x18006e66c  cmp     rbx, rsi
0x18006e66f  jnz     short loc_18006E682
0x18006e671  lea     rcx, [rsp+1140h+hDevice]
0x18006e676  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18006e67b  xor     al, al
0x18006e67d  jmp     loc_18006ECB3
0x18006e682  mov     [rsp+1140h+lpOverlapped], r12; lpOverlapped
0x18006e687  lea     rax, [rsp+1140h+BytesReturned]
0x18006e68c  mov     [rsp+1140h+hTemplateFile], rax; lpBytesReturned
0x18006e691  mov     [rsp+1140h+dwFlagsAndAttributes], 0Ch; nOutBufferSize
0x18006e699  lea     rax, [rbp+1040h+OutBuffer]
0x18006e69d  mov     qword ptr [rsp+1140h+dwCreationDisposition], rax; lpOutBuffer
0x18006e6a2  xor     r9d, r9d; nInBufferSize
0x18006e6a5  xor     r8d, r8d; lpInBuffer
0x18006e6a8  mov     edx, 2D1080h; dwIoControlCode
0x18006e6ad  mov     rcx, rbx; hDevice
0x18006e6b0  call    cs:__imp_DeviceIoControl
0x18006e6b6  test    eax, eax
0x18006e6b8  jnz     short loc_18006E6C2
0x18006e6ba  mov     r15b, r12b
0x18006e6bd  jmp     loc_18006ECA6
0x18006e6c2  mov     eax, cs:dword_1800BF170
0x18006e6c8  cmp     eax, 5
0x18006e6cb  jbe     short loc_18006E6F4
0x18006e6cd  mov     eax, dword ptr [rbp+1040h+OutBuffer+4]
0x18006e6d0  mov     dword ptr [rsp+1140h+var_10D8], eax
0x18006e6d4  lea     rax, [rsp+1140h+var_10D8]
0x18006e6d9  mov     qword ptr [rsp+1140h+dwCreationDisposition], rax
0x18006e6de  xor     r8d, r8d
0x18006e6e1  lea     rdx, byte_1800A95BB
0x18006e6e8  lea     rcx, dword_1800BF170
0x18006e6ef  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18006e6f4  mov     eax, dword ptr [rbp+1040h+OutBuffer+4]
0x18006e6f7  mov     [rdi+48h], eax
0x18006e6fa  mov     [rsp+1140h+lpOverlapped], r12; lpOverlapped
0x18006e6ff  lea     rax, [rsp+1140h+BytesReturned]
0x18006e704  mov     [rsp+1140h+hTemplateFile], rax; lpBytesReturned
0x18006e709  mov     [rsp+1140h+dwFlagsAndAttributes], 1000h; nOutBufferSize
0x18006e711  lea     rax, [rbp+1040h+Buffer]
0x18006e715  mov     qword ptr [rsp+1140h+dwCreationDisposition], rax; lpOutBuffer
0x18006e71a  xor     r9d, r9d; nInBufferSize
0x18006e71d  xor     r8d, r8d; lpInBuffer
0x18006e720  mov     edx, 700A0h; dwIoControlCode
0x18006e725  mov     rcx, rbx; hDevice
0x18006e728  call    cs:__imp_DeviceIoControl
0x18006e72e  mov     rcx, [rbp+1048h]; this
0x18006e735  test    eax, eax
0x18006e737  jnz     short loc_18006E74F
0x18006e739  lea     r8, aOnecoreDrivers_14; "onecore\\drivers\\storage\\storsvc\\dis"...
0x18006e740  mov     edx, 118h; void *
0x18006e745  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18006e74a  jmp     loc_18006E7DC
0x18006e74f  mov     eax, [rbp+1040h+var_1028]
0x18006e752  mov     [rdi+58h], eax
0x18006e755  mov     eax, [rbp+1040h+var_101C]
0x18006e758  mov     [rdi+60h], eax
0x18006e75b  mov     [rdi+64h], eax
0x18006e75e  mov     rax, [rbp+1040h+var_1018]
0x18006e762  mov     [rdi+70h], rax
0x18006e766  mov     ecx, [rbp+1040h+var_1010]
0x18006e769  mov     eax, cs:dword_1800BF170
0x18006e76f  cmp     eax, 5
0x18006e772  jbe     short loc_18006E7D6
0x18006e774  mov     eax, [rbp+rcx+1040h+var_100C]
0x18006e778  mov     dword ptr [rsp+1140h+var_10D8], eax
0x18006e77c  mov     eax, [rbp+1040h+var_100C]
0x18006e77f  mov     dword ptr [rbp+1040h+var_10C0], eax
0x18006e782  mov     rax, [rbp+1040h+var_1018]
0x18006e786  mov     [rsp+1140h+var_10D0], rax
0x18006e78b  mov     eax, [rbp+1040h+var_101C]
0x18006e78e  mov     [rsp+1140h+var_10EC], eax
0x18006e792  mov     eax, [rbp+1040h+var_1028]
0x18006e795  mov     dword ptr [rsp+1140h+var_10E8], eax
0x18006e799  lea     rax, [rsp+1140h+var_10D8]
0x18006e79e  mov     [rsp+1140h+var_1100], rax
0x18006e7a3  lea     rax, [rbp+1040h+var_10C0]
0x18006e7a7  mov     [rsp+1140h+lpOverlapped], rax
0x18006e7ac  lea     rax, [rsp+1140h+var_10D0]
0x18006e7b1  mov     [rsp+1140h+hTemplateFile], rax
0x18006e7b6  lea     rax, [rsp+1140h+var_10EC]
0x18006e7bb  mov     qword ptr [rsp+1140h+dwFlagsAndAttributes], rax
0x18006e7c0  lea     rax, [rsp+1140h+var_10E8]
0x18006e7c5  mov     qword ptr [rsp+1140h+dwCreationDisposition], rax
0x18006e7ca  lea     rdx, word_1800A953E
0x18006e7d1  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18006e7d6  mov     eax, [rbp+1040h+var_100C]
0x18006e7d9  mov     [rdi+50h], eax
0x18006e7dc  mov     [rsp+1140h+lpOverlapped], r12; lpOverlapped
0x18006e7e1  lea     rax, [rsp+1140h+BytesReturned]
0x18006e7e6  mov     [rsp+1140h+hTemplateFile], rax; lpBytesReturned
0x18006e7eb  mov     [rsp+1140h+dwFlagsAndAttributes], 10h; nOutBufferSize
0x18006e7f3  lea     rax, [rbp+1040h+var_1090]
0x18006e7f7  mov     qword ptr [rsp+1140h+dwCreationDisposition], rax; lpOutBuffer
0x18006e7fc  xor     r9d, r9d; nInBufferSize
0x18006e7ff  xor     r8d, r8d; lpInBuffer
0x18006e802  mov     edx, 700F0h; dwIoControlCode
0x18006e807  mov     rcx, rbx; hDevice
0x18006e80a  call    cs:__imp_DeviceIoControl
0x18006e810  mov     rcx, [rbp+1048h]; this
0x18006e817  test    eax, eax
0x18006e819  jnz     short loc_18006E82E
0x18006e81b  lea     r8, aOnecoreDrivers_14; "onecore\\drivers\\storage\\storsvc\\dis"...
0x18006e822  mov     edx, 13Dh; void *
0x18006e827  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18006e82c  jmp     short loc_18006E867
0x18006e82e  mov     eax, cs:dword_1800BF170
0x18006e834  cmp     eax, 5
0x18006e837  jbe     short loc_18006E85F
0x18006e839  mov     rax, qword ptr [rbp+1040h+var_1090+8]
0x18006e83d  mov     [rsp+1140h+var_10D0], rax
0x18006e842  lea     rax, [rsp+1140h+var_10D0]
0x18006e847  mov     qword ptr [rsp+1140h+dwCreationDisposition], rax
0x18006e84c  lea     rdx, byte_1800A94F7
0x18006e853  lea     rcx, dword_1800BF170
0x18006e85a  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x18006e85f  mov     rax, qword ptr [rbp+1040h+var_1090+8]
0x18006e863  mov     [rdi+68h], rax
0x18006e867  mov     [rsp+1140h+lpOverlapped], r12; lpOverlapped
0x18006e86c  lea     rax, [rsp+1140h+BytesReturned]
0x18006e871  mov     [rsp+1140h+hTemplateFile], rax; lpBytesReturned
0x18006e876  mov     [rsp+1140h+dwFlagsAndAttributes], 1000h; nOutBufferSize
0x18006e87e  lea     rax, [rbp+1040h+Buffer]
0x18006e882  mov     qword ptr [rsp+1140h+dwCreationDisposition], rax; lpOutBuffer
0x18006e887  xor     r9d, r9d; nInBufferSize
0x18006e88a  xor     r8d, r8d; lpInBuffer
0x18006e88d  mov     edx, 70050h; dwIoControlCode
0x18006e892  mov     rcx, rbx; hDevice
0x18006e895  call    cs:__imp_DeviceIoControl
0x18006e89b  mov     rcx, [rbp+1048h]; this
0x18006e8a2  test    eax, eax
0x18006e8a4  jnz     short loc_18006E8B9
0x18006e8a6  lea     r8, aOnecoreDrivers_14; "onecore\\drivers\\storage\\storsvc\\dis"...
0x18006e8ad  mov     edx, 158h; void *
0x18006e8b2  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18006e8b7  jmp     short loc_18006E902
0x18006e8b9  mov     eax, cs:dword_1800BF170
0x18006e8bf  cmp     eax, 5
0x18006e8c2  jbe     short loc_18006E8FC
0x18006e8c4  mov     eax, [rbp+1040h+var_102C]
0x18006e8c7  mov     dword ptr [rsp+1140h+var_10E8], eax
0x18006e8cb  mov     eax, dword ptr [rbp+1040h+Buffer]
0x18006e8ce  mov     [rsp+1140h+var_10EC], eax
0x18006e8d2  lea     rax, [rsp+1140h+var_10E8]
0x18006e8d7  mov     qword ptr [rsp+1140h+dwFlagsAndAttributes], rax
0x18006e8dc  lea     rax, [rsp+1140h+var_10EC]
0x18006e8e1  mov     qword ptr [rsp+1140h+dwCreationDisposition], rax
0x18006e8e6  xor     r8d, r8d
0x18006e8e9  lea     rdx, unk_1800A94A0
0x18006e8f0  lea     rcx, dword_1800BF170
0x18006e8f7  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18006e8fc  mov     eax, [rbp+1040h+var_102C]
0x18006e8ff  mov     [rdi+54h], eax
0x18006e902  mov     [rbp+1040h+InBuffer], r12
0x18006e906  mov     [rsp+1140h+lpOverlapped], r12; lpOverlapped
0x18006e90b  lea     rax, [rsp+1140h+BytesReturned]
0x18006e910  mov     [rsp+1140h+hTemplateFile], rax; lpBytesReturned
0x18006e915  mov     [rsp+1140h+dwFlagsAndAttributes], 1000h; nOutBufferSize
0x18006e91d  lea     rax, [rbp+1040h+Buffer]
0x18006e921  mov     qword ptr [rsp+1140h+dwCreationDisposition], rax; lpOutBuffer
0x18006e926  mov     r9d, 0Ch; nInBufferSize
0x18006e92c  lea     r8, [rbp+1040h+InBuffer]; lpInBuffer
0x18006e930  mov     edx, 2D1400h; dwIoControlCode
0x18006e935  mov     rcx, rbx; hDevice
0x18006e938  call    cs:__imp_DeviceIoControl
0x18006e93e  mov     rcx, [rbp+1048h]; this
0x18006e945  test    eax, eax
0x18006e947  jnz     short loc_18006E95F
0x18006e949  lea     r8, aOnecoreDrivers_14; "onecore\\drivers\\storage\\storsvc\\dis"...
0x18006e950  mov     edx, 175h; void *
0x18006e955  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18006e95a  jmp     loc_18006EAC0
0x18006e95f  mov     eax, cs:dword_1800BF170
0x18006e965  cmp     eax, 5
0x18006e968  jbe     loc_18006EA0D
0x18006e96e  mov     r8d, dword ptr [rbp+1040h+var_1018]
0x18006e972  mov     edx, [rsp+1140h+BytesReturned]
0x18006e976  lea     rcx, [rbp+1040h+Buffer]
0x18006e97a  call    GetOffsetString
0x18006e97f  mov     [rsp+1140h+var_10D0], rax
0x18006e984  mov     r8d, [rbp+1040h+var_101C]
0x18006e988  lea     rcx, [rbp+1040h+Buffer]
0x18006e98c  call    GetOffsetString
0x18006e991  mov     [rbp+1040h+var_10C0], rax
0x18006e995  mov     r8d, [rbp+1040h+var_1020]
0x18006e999  lea     rcx, [rbp+1040h+Buffer]
0x18006e99d  call    GetOffsetString
0x18006e9a2  mov     [rsp+1140h+var_10D8], rax
0x18006e9a7  mov     r8d, [rbp+1040h+var_1024]
0x18006e9ab  lea     rcx, [rbp+1040h+Buffer]
0x18006e9af  call    GetOffsetString
0x18006e9b4  mov     [rbp+1040h+var_10B8], rax
0x18006e9b8  mov     eax, dword ptr [rbp+1040h+var_1018+4]
0x18006e9bb  mov     dword ptr [rsp+1140h+var_10E8], eax
0x18006e9bf  movzx   eax, byte ptr [rbp+1040h+var_1028+2]
0x18006e9c3  mov     [rsp+1140h+var_10EC], eax
0x18006e9c7  lea     rax, [rsp+1140h+var_10D0]
0x18006e9cc  mov     [rsp+1140h+var_10F8], rax
0x18006e9d1  lea     rax, [rbp+1040h+var_10C0]
0x18006e9d5  mov     [rsp+1140h+var_1100], rax
0x18006e9da  lea     rax, [rsp+1140h+var_10D8]
0x18006e9df  mov     [rsp+1140h+lpOverlapped], rax
0x18006e9e4  lea     rax, [rbp+1040h+var_10B8]
0x18006e9e8  mov     [rsp+1140h+hTemplateFile], rax
0x18006e9ed  lea     rax, [rsp+1140h+var_10E8]
0x18006e9f2  mov     qword ptr [rsp+1140h+dwFlagsAndAttributes], rax
0x18006e9f7  lea     rax, [rsp+1140h+var_10EC]
0x18006e9fc  mov     qword ptr [rsp+1140h+dwCreationDisposition], rax
0x18006ea01  lea     rdx, unk_1800A9418
0x18006ea08  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapSz@D@@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapSz@D@@444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18006ea0d  mov     r8d, [rbp+1040h+var_1024]
0x18006ea11  mov     edx, [rsp+1140h+BytesReturned]
0x18006ea15  lea     rcx, [rbp+1040h+Buffer]
0x18006ea19  call    GetOffsetString
0x18006ea1e  mov     r8, rsi
0x18006ea21  inc     r8
0x18006ea24  cmp     [rax+r8], r12b
0x18006ea28  jnz     short loc_18006EA21
0x18006ea2a  lea     rcx, [rdi+98h]
0x18006ea31  mov     rdx, rax
0x18006ea34  call    ??$_Assign@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Assign<char>(char const * const,unsigned __int64)
0x18006ea39  mov     r8d, [rbp+1040h+var_1020]
0x18006ea3d  mov     edx, [rsp+1140h+BytesReturned]
0x18006ea41  lea     rcx, [rbp+1040h+Buffer]
0x18006ea45  call    GetOffsetString
0x18006ea4a  mov     r8, rsi
0x18006ea4d  inc     r8
0x18006ea50  cmp     [rax+r8], r12b
0x18006ea54  jnz     short loc_18006EA4D
0x18006ea56  lea     rcx, [rdi+78h]
0x18006ea5a  mov     rdx, rax
0x18006ea5d  call    ??$_Assign@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Assign<char>(char const * const,unsigned __int64)
  ... truncated ...
```
