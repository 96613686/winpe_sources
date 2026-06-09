# HidForceFeedbackSettings::LoadFromRegistry(HKEY__ *,ushort const *)

- ea: `0x180017088`
- end: `0x180017cc0`
- name: `?LoadFromRegistry@HidForceFeedbackSettings@@AEAAJPEAUHKEY__@@PEBG@Z`
- size: `3128`
- prototype: `__int64 __fastcall(HidForceFeedbackSettings *__hidden this, HKEY hKey, LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180017cc8`

## callees

- `0x180001304`
- `0x180002058`
- `0x180017088`
- `0x180017ec8`
- `0x18004c8a5`
- `0x18004c8e0`
- `0x18004d010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800176cb`
- `ntdll!RtlInitUnicodeString` at `0x1800176cb`
- `ntdll!RtlGUIDFromString` at `0x1800176e6`
- `ntdll!RtlGUIDFromString` at `0x1800176e6`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180017479`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180017479`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180017620`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180017620`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800170de`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800171ab`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017295`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017529`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001771c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800170de`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800171ab`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017295`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017529`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001771c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180017391`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180017772`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180017391`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180017772`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x1800176a6`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x1800176a6`

## string_xrefs

- `0x18001738a`: `CLSID`
- `0x180017816`: `HID force feedback registry info`

## pseudocode

```c
__int64 __fastcall HidForceFeedbackSettings::LoadFromRegistry(
        HidForceFeedbackSettings *this,
        HKEY hKey,
        LPCWSTR lpSubKey)
{
  signed int v5; // edi
  int v6; // r8d
  int v7; // r9d
  void (*v8)(void); // rax
  int v10; // r8d
  int v11; // r9d
  int v12; // r8d
  int v13; // r9d
  int v14; // ecx
  void *v15; // rdx
  void (*v16)(void); // rax
  int v17; // r8d
  int v18; // r9d
  int v19; // r8d
  int v20; // r9d
  int v21; // ecx
  __int16 *v22; // rdx
  DWORD v23; // ebx
  int v24; // r8d
  int v25; // r9d
  NTSTATUS v26; // edi
  int v27; // r8d
  int v28; // r9d
  int v29; // r8d
  int v30; // r9d
  void (*v31)(void); // rax
  int v32; // ecx
  __int16 *v33; // rdx
  void (*v34)(void); // rax
  DWORD v35; // [rsp+60h] [rbp-A0h] BYREF
  DWORD lpcbData; // [rsp+64h] [rbp-9Ch] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-98h] BYREF
  HKEY v38; // [rsp+70h] [rbp-90h] BYREF
  HKEY v39; // [rsp+78h] [rbp-88h] BYREF
  int v40; // [rsp+80h] [rbp-80h] BYREF
  int v41; // [rsp+84h] [rbp-7Ch] BYREF
  HKEY v42; // [rsp+88h] [rbp-78h] BYREF
  HKEY hKeya; // [rsp+90h] [rbp-70h] BYREF
  const char *v44; // [rsp+98h] [rbp-68h] BYREF
  DWORD cSubKeys; // [rsp+A0h] [rbp-60h] BYREF
  DWORD Type; // [rsp+A4h] [rbp-5Ch] BYREF
  DWORD cbData; // [rsp+A8h] [rbp-58h] BYREF
  int v48; // [rsp+ACh] [rbp-54h] BYREF
  const char *v49; // [rsp+B0h] [rbp-50h] BYREF
  const char *v50; // [rsp+B8h] [rbp-48h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+C0h] [rbp-40h] BYREF
  struct DIEFFECTATTRIBUTES v52; // [rsp+D0h] [rbp-30h] BYREF
  GUID Guid; // [rsp+E8h] [rbp-18h] BYREF
  WCHAR Name[40]; // [rsp+100h] [rbp+0h] BYREF
  OLECHAR Data[40]; // [rsp+150h] [rbp+50h] BYREF

  hKeya = 0;
  v5 = RegOpenKeyExW(
         hKey,
         L"System\\CurrentControlSet\\Control\\MediaProperties\\PrivateProperties\\Joystick\\OEM",
         0,
         1u,
         &hKeya);
  if ( v5 )
  {
    if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
    {
      v35 = v5;
      lpcbData = 76;
      v39 = (HKEY)"onecore\\xbox\\gameinput\\feedback\\hid\\HidForceFeedbackSettings.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_180069018,
        (unsigned int)byte_18005CE65,
        v6,
        v7,
        (__int64)&v39,
        (__int64)&lpcbData,
        (__int64)&v35);
    }
    if ( v5 > 0 )
      v5 = (unsigned __int16)v5 | 0x80070000;
    if ( !hKeya )
      return (unsigned int)v5;
    v8 = (void (*)(void))qword_1800697B0;
LABEL_10:
    if ( v8 )
      v8();
    return (unsigned int)v5;
  }
  phkResult = 0;
  v5 = RegOpenKeyExW(hKeya, lpSubKey, 0, 1u, &phkResult);
  if ( v5 )
  {
    if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
    {
      lpcbData = v5;
      v35 = 79;
      v39 = (HKEY)"onecore\\xbox\\gameinput\\feedback\\hid\\HidForceFeedbackSettings.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_180069018,
        (unsigned int)&unk_18005D2F0,
        v10,
        v11,
        (__int64)&v39,
        (__int64)&v35,
        (__int64)&lpcbData);
    }
    if ( v5 > 0 )
      v5 = (unsigned __int16)v5 | 0x80070000;
    v8 = (void (*)(void))qword_1800697B0;
    goto LABEL_21;
  }
  v38 = 0;
  v5 = RegOpenKeyExW(phkResult, L"OEMForceFeedback", 0, 1u, &v38);
  if ( v5 )
  {
    if ( (unsigned int)dword_180069000 > 2 )
    {
      v14 = qword_180069018;
      if ( (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
      {
        v35 = 82;
        v15 = &unk_18005C4F0;
LABEL_32:
        lpcbData = v5;
        v39 = (HKEY)"onecore\\xbox\\gameinput\\feedback\\hid\\HidForceFeedbackSettings.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v14,
          (_DWORD)v15,
          v12,
          v13,
          (__int64)&v39,
          (__int64)&v35,
          (__int64)&lpcbData);
        goto LABEL_33;
      }
    }
    goto LABEL_33;
  }
  Type = 0;
  memset_0(Data, 0, 0x4Eu);
  cbData = 78;
  v5 = RegQueryValueExW(v38, L"CLSID", 0, &Type, (LPBYTE)Data, &cbData);
  if ( v5 )
  {
    if ( (unsigned int)dword_180069000 > 2 )
    {
      v14 = qword_180069018;
      if ( (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
      {
        v35 = 93;
        v15 = &unk_18005B380;
        goto LABEL_32;
      }
    }
LABEL_33:
    if ( v5 > 0 )
      v5 = (unsigned __int16)v5 | 0x80070000;
LABEL_35:
    v8 = (void (*)(void))qword_1800697B0;
LABEL_36:
    if ( v38 )
    {
      if ( v8 )
      {
        v8();
        v8 = (void (*)(void))qword_1800697B0;
      }
      v38 = 0;
    }
LABEL_21:
    if ( phkResult )
    {
      if ( v8 )
      {
        v8();
        v8 = (void (*)(void))qword_1800697B0;
      }
      phkResult = 0;
    }
    if ( !hKeya )
      return (unsigned int)v5;
    goto LABEL_10;
  }
  if ( Type == 1 )
  {
    v5 = CLSIDFromString(Data, (LPCLSID)((char *)this + 236));
    if ( v5 < 0 )
    {
      if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
      {
        lpcbData = v5;
        v35 = 96;
        v39 = (HKEY)"onecore\\xbox\\gameinput\\feedback\\hid\\HidForceFeedbackSettings.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          qword_180069010,
          (unsigned int)byte_18005D47D,
          v17,
          v18,
          (__int64)&v39,
          (__int64)&v35,
          (__int64)&lpcbData);
      }
      goto LABEL_35;
    }
    v42 = 0;
    v5 = RegOpenKeyExW(v38, L"Effects", 0, 9u, &v42);
    if ( v5 )
    {
      if ( (unsigned int)dword_180069000 <= 2 )
        goto LABEL_62;
      v21 = qword_180069018;
      if ( (qword_180069010 & 8) == 0 || (qword_180069018 & 8) != qword_180069018 )
        goto LABEL_62;
      v35 = 99;
      v22 = (__int16 *)byte_18005DE4B;
    }
    else
    {
      cSubKeys = 0;
      v5 = RegQueryInfoKeyW(v42, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
      if ( !v5 )
      {
        v23 = 0;
        if ( !cSubKeys )
        {
LABEL_85:
          if ( (unsigned int)dword_180069000 > 4
            && (qword_180069010 & 8) != 0
            && (qword_180069018 & 8) == qword_180069018 )
          {
            v41 = *((_DWORD *)this + 58);
            v40 = *(_DWORD *)this;
            v49 = "HID force feedback registry info";
            v44 = (char *)this + 236;
            v48 = 150;
            v50 = "onecore\\xbox\\gameinput\\feedback\\hid\\HidForceFeedbackSettings.cpp";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
              qword_180069018,
              (unsigned int)qword_18005A798,
              v19,
              v20,
              (__int64)&v50,
              (__int64)&v48,
              (__int64)&v49,
              (__int64)&v40,
              (__int64)&v44,
              (__int64)&v41);
          }
          if ( *((_DWORD *)this + 58) )
          {
            v34 = (void (*)(void))qword_1800697B0;
            if ( v42 )
            {
              if ( qword_1800697B0 )
              {
                qword_1800697B0();
                v34 = (void (*)(void))qword_1800697B0;
              }
              v42 = 0;
            }
            if ( v38 )
            {
              if ( v34 )
              {
                v34();
                v34 = (void (*)(void))qword_1800697B0;
              }
              v38 = 0;
            }
            if ( phkResult )
            {
              if ( v34 )
              {
                v34();
                v34 = (void (*)(void))qword_1800697B0;
              }
              phkResult = 0;
            }
            if ( hKeya && v34 )
              v34();
            return 0;
          }
          else
          {
            if ( (unsigned int)dword_180069000 > 2
              && (qword_180069010 & 8) != 0
              && (qword_180069018 & 8) == qword_180069018 )
            {
              LODWORD(v49) = -2147023728;
              LODWORD(v44) = 152;
              v50 = "onecore\\xbox\\gameinput\\feedback\\hid\\HidForceFeedbackSettings.cpp";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                qword_180069018,
                (unsigned int)byte_18005B591,
                v19,
                v20,
                (__int64)&v50,
                (__int64)&v44,
                (__int64)&v49);
            }
            v31 = (void (*)(void))qword_1800697B0;
            if ( v42 )
            {
              if ( qword_1800697B0 )
              {
                qword_1800697B0();
                v31 = (void (*)(void))qword_1800697B0;
              }
              v42 = 0;
            }
            if ( v38 )
            {
              if ( v31 )
              {
                v31();
                v31 = (void (*)(void))qword_1800697B0;
              }
              v38 = 0;
            }
            if ( phkResult )
            {
              if ( v31 )
              {
                v31();
                v31 = (void (*)(void))qword_1800697B0;
              }
              phkResult = 0;
            }
            if ( hKeya && v31 )
              v31();
            return 2147943568LL;
          }
        }
        while ( 1 )
        {
          memset_0(Name, 0, 0x4Eu);
          v5 = RegEnumKeyW(v42, v23, Name, 0x27u);
          if ( v5 )
            break;
          DestinationString = 0;
          RtlInitUnicodeString(&DestinationString, Name);
          Guid = 0;
          v26 = RtlGUIDFromString(&DestinationString, &Guid);
          if ( v26 < 0 )
          {
            if ( (unsigned int)dword_180069000 > 2
              && (qword_180069010 & 8) != 0
              && (qword_180069018 & 8) == qword_180069018 )
            {
              v41 = v26;
              v40 = 125;
              v44 = "onecore\\xbox\\gameinput\\feedback\\hid\\HidForceFeedbackSettings.cpp";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                qword_180069018,
                (unsigned int)byte_18005A8FB,
                v27,
                v28,
                (__int64)&v44,
                (__int64)&v40,
                (__int64)&v41);
            }
            v5 = v26 | 0x10000000;
            goto LABEL_64;
          }
          v39 = 0;
          v5 = RegOpenKeyExW(v42, Name, 0, 1u, &v39);
          if ( v5 )
          {
            if ( (unsigned int)dword_180069000 > 2 )
            {
              v32 = qword_180069018;
              if ( (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
              {
                v40 = 128;
                v33 = word_18005D0B2;
LABEL_142:
                v41 = v5;
                v44 = "onecore\\xbox\\gameinput\\feedback\\hid\\HidForceFeedbackSettings.cpp";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                  v32,
                  (_DWORD)v33,
                  v29,
                  v30,
                  (__int64)&v44,
                  (__int64)&v40,
                  (__int64)&v41);
              }
            }
LABEL_143:
            if ( v5 > 0 )
              v5 = (unsigned __int16)v5 | 0x80070000;
            v8 = (void (*)(void))qword_1800697B0;
            if ( v39 )
            {
              if ( qword_1800697B0 )
              {
                qword_1800697B0();
                v8 = (void (*)(void))qword_1800697B0;
              }
              v39 = 0;
            }
            goto LABEL_65;
          }
          v35 = 0;
          lpcbData = 20;
          memset(&v52, 0, sizeof(v52));
          v5 = RegQueryValueExW(v39, L"Attributes", 0, &v35, (LPBYTE)&v52, &lpcbData);
          if ( v5 )
          {
            if ( (unsigned int)dword_180069000 > 2 )
            {
              v32 = qword_180069018;
              if ( (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
              {
                v40 = 139;
                v33 = (__int16 *)&dword_18005CA84;
                goto LABEL_142;
              }
            }
            goto LABEL_143;
          }
          if ( v35 != 3 )
          {
            if ( (unsigned int)dword_180069000 > 2
              && (qword_180069010 & 8) != 0
              && (qword_180069018 & 8) == qword_180069018 )
            {
              v40 = -2147024883;
              v41 = 141;
              v44 = "onecore\\xbox\\gameinput\\feedback\\hid\\HidForceFeedbackSettings.cpp";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                qword_180069018,
                (unsigned int)byte_18005A469,
                v29,
                v30,
                (__int64)&v44,
                (__int64)&v41,
                (__int64)&v40);
            }
            v16 = (void (*)(void))qword_1800697B0;
            if ( v39 )
            {
              if ( qword_1800697B0 )
              {
                qword_1800697B0();
                v16 = (void (*)(void))qword_1800697B0;
              }
              v39 = 0;
            }
            if ( v42 )
            {
              if ( v16 )
              {
                v16();
                v16 = (void (*)(void))qword_1800697B0;
              }
              v42 = 0;
            }
            goto LABEL_122;
          }
          HidForceFeedbackSettings::MapEffect(this, &Guid, &v52);
          if ( v39 )
          {
            if ( qword_1800697B0 )
              qword_1800697B0();
            v39 = 0;
          }
          if ( ++v23 >= cSubKeys )
            goto LABEL_85;
        }
        if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
        {
          v41 = v5;
          v40 = 119;
          v44 = "onecore\\xbox\\gameinput\\feedback\\hid\\HidForceFeedbackSettings.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            qword_180069018,
            (unsigned int)&byte_18005B20F,
            v24,
            v25,
            (__int64)&v44,
            (__int64)&v40,
            (__int64)&v41);
        }
LABEL_62:
        if ( v5 > 0 )
          v5 = (unsigned __int16)v5 | 0x80070000;
LABEL_64:
        v8 = (void (*)(void))qword_1800697B0;
LABEL_65:
        if ( v42 )
        {
          if ( v8 )
          {
            v8();
            v8 = (void (*)(void))qword_1800697B0;
          }
          v42 = 0;
        }
        goto LABEL_36;
      }
      if ( (unsigned int)dword_180069000 <= 2 )
        goto LABEL_62;
      v21 = qword_180069018;
      if ( (qword_180069010 & 8) == 0 || (qword_180069018 & 8) != qword_180069018 )
        goto LABEL_62;
      v35 = 114;
      v22 = word_18005DC5A;
    }
    lpcbData = v5;
    v39 = (HKEY)"onecore\\xbox\\gameinput\\feedback\\hid\\HidForceFeedbackSettings.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v21,
      (_DWORD)v22,
      v19,
      v20,
      (__int64)&v39,
      (__int64)&v35,
      (__int64)&lpcbData);
    goto LABEL_62;
  }
  if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
  {
    lpcbData = -2147024883;
    v35 = 95;
    v39 = (HKEY)"onecore\\xbox\\gameinput\\feedback\\hid\\HidForceFeedbackSettings.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      qword_180069018,
      (unsigned int)byte_18005C56D,
      v12,
      v13,
      (__int64)&v39,
      (__int64)&v35,
      (__int64)&lpcbData);
  }
  v16 = (void (*)(void))qword_1800697B0;
LABEL_122:
  if ( v38 )
  {
    if ( v16 )
    {
      v16();
      v16 = (void (*)(void))qword_1800697B0;
    }
    v38 = 0;
  }
  if ( phkResult )
  {
    if ( v16 )
    {
      v16();
      v16 = (void (*)(void))qword_1800697B0;
    }
    phkResult = 0;
  }
  if ( hKeya && v16 )
    v16();
  return 2147942413LL;
}

```

## disassembly

```asm
0x180017088  mov     [rsp-8+arg_18], rbx
0x18001708d  push    rbp
0x18001708e  push    rsi
0x18001708f  push    rdi
0x180017090  push    r14
0x180017092  push    r15
0x180017094  lea     rbp, [rsp-0B0h]
0x18001709c  sub     rsp, 1B0h
0x1800170a3  mov     rax, cs:__security_cookie
0x1800170aa  xor     rax, rsp
0x1800170ad  mov     [rbp+0D0h+var_30], rax
0x1800170b4  mov     rsi, rcx
0x1800170b7  mov     rax, rdx
0x1800170ba  xor     r15d, r15d
0x1800170bd  lea     rcx, [rbp+0D0h+hKey]
0x1800170c1  mov     rbx, r8
0x1800170c4  mov     [rsp+1D0h+phkResult], rcx; phkResult
0x1800170c9  xor     r8d, r8d; ulOptions
0x1800170cc  mov     [rbp+0D0h+hKey], r15
0x1800170d0  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Med"...
0x1800170d7  mov     rcx, rax; hKey
0x1800170da  lea     r9d, [r15+1]; samDesired
0x1800170de  call    cs:__imp_RegOpenKeyExW
0x1800170e5  nop     dword ptr [rax+rax+00h]
0x1800170ea  mov     edi, eax
0x1800170ec  test    eax, eax
0x1800170ee  jz      loc_18001718C
0x1800170f4  mov     eax, cs:dword_180069000
0x1800170fa  cmp     eax, 2
0x1800170fd  jbe     short loc_18001715E
0x1800170ff  mov     rcx, cs:qword_180069018
0x180017106  mov     rax, cs:qword_180069010
0x18001710d  test    al, 8
0x18001710f  jz      short loc_18001715E
0x180017111  mov     rax, rcx
0x180017114  and     eax, 8
0x180017117  cmp     rax, rcx
0x18001711a  jnz     short loc_18001715E
0x18001711c  lea     rax, [rsp+1D0h+var_170]
0x180017121  mov     [rsp+1D0h+var_170], edi
0x180017125  mov     [rsp+1D0h+lpcbMaxClassLen], rax
0x18001712a  lea     rbx, aOnecoreXboxGam_52; "onecore\\xbox\\gameinput\\feedback\\hid"...
0x180017131  lea     rax, [rsp+1D0h+var_16C]
0x180017136  mov     [rsp+1D0h+var_16C], 4Ch ; 'L'
0x18001713e  mov     [rsp+1D0h+lpcbData], rax
0x180017143  lea     rdx, byte_18005CE65
0x18001714a  lea     rax, [rsp+1D0h+var_158]
0x18001714f  mov     [rsp+1D0h+var_158], rbx
0x180017154  mov     [rsp+1D0h+phkResult], rax
0x180017159  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001715e  test    edi, edi
0x180017160  jle     short loc_18001716B
0x180017162  movzx   edi, di
0x180017165  or      edi, 80070000h
0x18001716b  mov     rcx, [rbp+0D0h+hKey]
0x18001716f  test    rcx, rcx
0x180017172  jz      short loc_180017185
0x180017174  mov     rax, cs:qword_1800697B0
0x18001717b  test    rax, rax
0x18001717e  jz      short loc_180017185
0x180017180  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017185  mov     eax, edi
0x180017187  jmp     loc_180017C99
0x18001718c  mov     rcx, [rbp+0D0h+hKey]; hKey
0x180017190  lea     rax, [rsp+1D0h+var_168]
0x180017195  mov     r9d, 1; samDesired
0x18001719b  mov     [rsp+1D0h+phkResult], rax; phkResult
0x1800171a0  xor     r8d, r8d; ulOptions
0x1800171a3  mov     [rsp+1D0h+var_168], r15
0x1800171a8  mov     rdx, rbx; lpSubKey
0x1800171ab  call    cs:__imp_RegOpenKeyExW
0x1800171b2  nop     dword ptr [rax+rax+00h]
0x1800171b7  mov     edi, eax
0x1800171b9  test    eax, eax
0x1800171bb  jz      loc_180017271
0x1800171c1  mov     eax, cs:dword_180069000
0x1800171c7  cmp     eax, 2
0x1800171ca  jbe     short loc_18001722B
0x1800171cc  mov     rcx, cs:qword_180069018
0x1800171d3  mov     rax, cs:qword_180069010
0x1800171da  test    al, 8
0x1800171dc  jz      short loc_18001722B
0x1800171de  mov     rax, rcx
0x1800171e1  and     eax, 8
0x1800171e4  cmp     rax, rcx
0x1800171e7  jnz     short loc_18001722B
0x1800171e9  lea     rax, [rsp+1D0h+var_16C]
0x1800171ee  mov     [rsp+1D0h+var_16C], edi
0x1800171f2  mov     [rsp+1D0h+lpcbMaxClassLen], rax
0x1800171f7  lea     rbx, aOnecoreXboxGam_52; "onecore\\xbox\\gameinput\\feedback\\hid"...
0x1800171fe  lea     rax, [rsp+1D0h+var_170]
0x180017203  mov     [rsp+1D0h+var_170], 4Fh ; 'O'
0x18001720b  mov     [rsp+1D0h+lpcbData], rax
0x180017210  lea     rdx, unk_18005D2F0
0x180017217  lea     rax, [rsp+1D0h+var_158]
0x18001721c  mov     [rsp+1D0h+var_158], rbx
0x180017221  mov     [rsp+1D0h+phkResult], rax
0x180017226  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001722b  test    edi, edi
0x18001722d  jle     short loc_180017238
0x18001722f  movzx   edi, di
0x180017232  or      edi, 80070000h
0x180017238  mov     rax, cs:qword_1800697B0
0x18001723f  mov     rcx, [rsp+1D0h+var_168]
0x180017244  test    rcx, rcx
0x180017247  jz      short loc_18001725F
0x180017249  test    rax, rax
0x18001724c  jz      short loc_18001725A
0x18001724e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017253  mov     rax, cs:qword_1800697B0
0x18001725a  mov     [rsp+1D0h+var_168], r15
0x18001725f  mov     rcx, [rbp+0D0h+hKey]
0x180017263  test    rcx, rcx
0x180017266  jz      loc_180017185
0x18001726c  jmp     loc_18001717B
0x180017271  mov     rcx, [rsp+1D0h+var_168]; hKey
0x180017276  lea     rax, [rsp+1D0h+var_160]
0x18001727b  mov     r9d, 1; samDesired
0x180017281  mov     [rsp+1D0h+phkResult], rax; phkResult
0x180017286  xor     r8d, r8d; ulOptions
0x180017289  mov     [rsp+1D0h+var_160], r15
0x18001728e  lea     rdx, aOemforcefeedba; "OEMForceFeedback"
0x180017295  call    cs:__imp_RegOpenKeyExW
0x18001729c  nop     dword ptr [rax+rax+00h]
0x1800172a1  mov     edi, eax
0x1800172a3  test    eax, eax
0x1800172a5  jz      loc_180017352
0x1800172ab  mov     eax, cs:dword_180069000
0x1800172b1  cmp     eax, 2
0x1800172b4  jbe     short loc_180017315
0x1800172b6  mov     rcx, cs:qword_180069018
0x1800172bd  mov     rax, cs:qword_180069010
0x1800172c4  test    al, 8
0x1800172c6  jz      short loc_180017315
0x1800172c8  mov     rax, rcx
0x1800172cb  and     eax, 8
0x1800172ce  cmp     rax, rcx
0x1800172d1  jnz     short loc_180017315
0x1800172d3  mov     [rsp+1D0h+var_170], 52h ; 'R'
0x1800172db  lea     rdx, unk_18005C4F0
0x1800172e2  lea     rax, [rsp+1D0h+var_16C]
0x1800172e7  mov     [rsp+1D0h+lpcbMaxClassLen], rax
0x1800172ec  lea     rbx, aOnecoreXboxGam_52; "onecore\\xbox\\gameinput\\feedback\\hid"...
0x1800172f3  lea     rax, [rsp+1D0h+var_170]
0x1800172f8  mov     [rsp+1D0h+lpcbData], rax
0x1800172fd  lea     rax, [rsp+1D0h+var_158]
0x180017302  mov     [rsp+1D0h+phkResult], rax
0x180017307  mov     [rsp+1D0h+var_16C], edi
0x18001730b  mov     [rsp+1D0h+var_158], rbx
0x180017310  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180017315  test    edi, edi
0x180017317  jle     short loc_180017322
0x180017319  movzx   edi, di
0x18001731c  or      edi, 80070000h
0x180017322  mov     rax, cs:qword_1800697B0
0x180017329  mov     rcx, [rsp+1D0h+var_160]
0x18001732e  test    rcx, rcx
0x180017331  jz      loc_18001723F
0x180017337  test    rax, rax
0x18001733a  jz      short loc_180017348
0x18001733c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017341  mov     rax, cs:qword_1800697B0
0x180017348  mov     [rsp+1D0h+var_160], r15
0x18001734d  jmp     loc_18001723F
0x180017352  xor     edx, edx; Val
0x180017354  mov     [rbp+0D0h+Type], r15d
0x180017358  lea     rcx, [rbp+0D0h+Data]; void *
0x18001735c  lea     r8d, [rdx+4Eh]; Size
0x180017360  call    memset_0
0x180017365  mov     rcx, [rsp+1D0h+var_160]; hKey
0x18001736a  lea     rax, [rbp+0D0h+cbData]
0x18001736e  mov     [rsp+1D0h+lpcbData], rax; lpcbData
0x180017373  lea     r9, [rbp+0D0h+Type]; lpType
0x180017377  lea     rax, [rbp+0D0h+Data]
0x18001737b  mov     [rbp+0D0h+cbData], 4Eh ; 'N'
0x180017382  xor     r8d, r8d; lpReserved
0x180017385  mov     [rsp+1D0h+phkResult], rax; lpData
0x18001738a  lea     rdx, ValueName; "CLSID"
0x180017391  call    cs:__imp_RegQueryValueExW
0x180017398  nop     dword ptr [rax+rax+00h]
0x18001739d  mov     edi, eax
0x18001739f  test    eax, eax
0x1800173a1  jz      short loc_1800173EB
0x1800173a3  mov     eax, cs:dword_180069000
0x1800173a9  cmp     eax, 2
0x1800173ac  jbe     loc_180017315
0x1800173b2  mov     rcx, cs:qword_180069018
0x1800173b9  mov     rax, cs:qword_180069010
0x1800173c0  test    al, 8
0x1800173c2  jz      loc_180017315
0x1800173c8  mov     rax, rcx
0x1800173cb  and     eax, 8
0x1800173ce  cmp     rax, rcx
0x1800173d1  jnz     loc_180017315
0x1800173d7  mov     [rsp+1D0h+var_170], 5Dh ; ']'
0x1800173df  lea     rdx, unk_18005B380
0x1800173e6  jmp     loc_1800172E2
0x1800173eb  cmp     [rbp+0D0h+Type], 1
0x1800173ef  jz      short loc_18001746B
0x1800173f1  mov     eax, cs:dword_180069000
0x1800173f7  cmp     eax, 2
0x1800173fa  jbe     short loc_18001745F
0x1800173fc  mov     rcx, cs:qword_180069018
0x180017403  mov     rax, cs:qword_180069010
0x18001740a  test    al, 8
0x18001740c  jz      short loc_18001745F
0x18001740e  mov     rax, rcx
0x180017411  and     eax, 8
0x180017414  cmp     rax, rcx
0x180017417  jnz     short loc_18001745F
0x180017419  lea     rax, [rsp+1D0h+var_16C]
0x18001741e  mov     [rsp+1D0h+var_16C], 8007000Dh
0x180017426  mov     [rsp+1D0h+lpcbMaxClassLen], rax
0x18001742b  lea     rbx, aOnecoreXboxGam_52; "onecore\\xbox\\gameinput\\feedback\\hid"...
0x180017432  lea     rax, [rsp+1D0h+var_170]
0x180017437  mov     [rsp+1D0h+var_170], 5Fh ; '_'
0x18001743f  mov     [rsp+1D0h+lpcbData], rax
0x180017444  lea     rdx, byte_18005C56D
0x18001744b  lea     rax, [rsp+1D0h+var_158]
0x180017450  mov     [rsp+1D0h+var_158], rbx
0x180017455  mov     [rsp+1D0h+phkResult], rax
0x18001745a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001745f  mov     rax, cs:qword_1800697B0
0x180017466  jmp     loc_180017A08
0x18001746b  lea     r14, [rsi+0ECh]
0x180017472  mov     rdx, r14; pclsid
0x180017475  lea     rcx, [rbp+0D0h+Data]; lpsz
0x180017479  call    cs:__imp_CLSIDFromString
0x180017480  nop     dword ptr [rax+rax+00h]
0x180017485  mov     edi, eax
0x180017487  test    eax, eax
0x180017489  jns     short loc_180017507
0x18001748b  mov     ecx, cs:dword_180069000
0x180017491  cmp     ecx, 2
0x180017494  jbe     loc_180017322
0x18001749a  mov     rdx, cs:qword_180069018
0x1800174a1  mov     rcx, cs:qword_180069010
0x1800174a8  test    cl, 8
0x1800174ab  jz      loc_180017322
0x1800174b1  mov     rax, rdx
0x1800174b4  and     eax, 8
0x1800174b7  cmp     rax, rdx
0x1800174ba  jnz     loc_180017322
0x1800174c0  lea     rax, [rsp+1D0h+var_16C]
0x1800174c5  mov     [rsp+1D0h+var_16C], edi
0x1800174c9  mov     [rsp+1D0h+lpcbMaxClassLen], rax
0x1800174ce  lea     rbx, aOnecoreXboxGam_52; "onecore\\xbox\\gameinput\\feedback\\hid"...
0x1800174d5  lea     rax, [rsp+1D0h+var_170]
0x1800174da  mov     [rsp+1D0h+var_170], 60h ; '`'
0x1800174e2  mov     [rsp+1D0h+lpcbData], rax
0x1800174e7  lea     rdx, byte_18005D47D
0x1800174ee  lea     rax, [rsp+1D0h+var_158]
0x1800174f3  mov     [rsp+1D0h+var_158], rbx
0x1800174f8  mov     [rsp+1D0h+phkResult], rax
0x1800174fd  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180017502  jmp     loc_180017322
0x180017507  mov     rcx, [rsp+1D0h+var_160]; hKey
0x18001750c  lea     rax, [rbp+0D0h+var_148]
0x180017510  mov     r9d, 9; samDesired
0x180017516  mov     [rsp+1D0h+phkResult], rax; phkResult
0x18001751b  xor     r8d, r8d; ulOptions
0x18001751e  mov     [rbp+0D0h+var_148], r15
0x180017522  lea     rdx, aEffects; "Effects"
0x180017529  call    cs:__imp_RegOpenKeyExW
0x180017530  nop     dword ptr [rax+rax+00h]
0x180017535  mov     edi, eax
0x180017537  test    eax, eax
0x180017539  jz      loc_1800175E4
0x18001753f  mov     eax, cs:dword_180069000
0x180017545  cmp     eax, 2
0x180017548  jbe     short loc_1800175A9
0x18001754a  mov     rcx, cs:qword_180069018
0x180017551  mov     rax, cs:qword_180069010
0x180017558  test    al, 8
0x18001755a  jz      short loc_1800175A9
0x18001755c  mov     rax, rcx
0x18001755f  and     eax, 8
0x180017562  cmp     rax, rcx
0x180017565  jnz     short loc_1800175A9
0x180017567  mov     [rsp+1D0h+var_170], 63h ; 'c'
0x18001756f  lea     rdx, byte_18005DE4B
0x180017576  lea     rax, [rsp+1D0h+var_16C]
0x18001757b  mov     [rsp+1D0h+lpcbMaxClassLen], rax
0x180017580  lea     rbx, aOnecoreXboxGam_52; "onecore\\xbox\\gameinput\\feedback\\hid"...
0x180017587  lea     rax, [rsp+1D0h+var_170]
0x18001758c  mov     [rsp+1D0h+lpcbData], rax
0x180017591  lea     rax, [rsp+1D0h+var_158]
0x180017596  mov     [rsp+1D0h+phkResult], rax
0x18001759b  mov     [rsp+1D0h+var_16C], edi
0x18001759f  mov     [rsp+1D0h+var_158], rbx
0x1800175a4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800175a9  test    edi, edi
0x1800175ab  jle     short loc_1800175B6
0x1800175ad  movzx   edi, di
0x1800175b0  or      edi, 80070000h
0x1800175b6  mov     rax, cs:qword_1800697B0
0x1800175bd  mov     rcx, [rbp+0D0h+var_148]
0x1800175c1  test    rcx, rcx
0x1800175c4  jz      loc_180017329
0x1800175ca  test    rax, rax
  ... truncated ...
```
