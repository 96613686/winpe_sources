# Windows::Networking::UX::Internal::CAdapterProperties::GetNetAdapterDriverProperty(_DEVPROPKEY const &,HSTRING__ * *)

- ea: `0x180002bd0`
- end: `0x180002f45`
- name: `?GetNetAdapterDriverProperty@CAdapterProperties@Internal@UX@Networking@Windows@@AEAAJAEBU_DEVPROPKEY@@PEAPEAUHSTRING__@@@Z`
- size: `885`
- prototype: `int(Windows::Networking::UX::Internal::CAdapterProperties *__hidden this, const struct _DEVPROPKEY *, HSTRING *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800028f8`

## callees

- `0x180002bd0`
- `0x180005be0`
- `0x180005c80`
- `0x18002cd20`
- `0x18002d8c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002e8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002ec3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002edc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002efa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002e8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002ec3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002edc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002efa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002d4a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002d4a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002d97`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002e2f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002d97`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002e2f`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180002d6d`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180002d6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180002e24`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180002e24`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x180002cd3`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x180002cd3`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180002c48`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180002c48`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x180002ca4`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x180002ca4`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180002e3b`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180002ecc`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180002e3b`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180002ecc`
- `DEVOBJ!DevObjGetClassDevs` at `0x180002c78`
- `DEVOBJ!DevObjGetClassDevs` at `0x180002c78`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x180002df0`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x180002df0`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::Internal::CAdapterProperties::GetNetAdapterDriverProperty(
        Windows::Networking::UX::Internal::CAdapterProperties *this,
        const struct _DEVPROPKEY *a2,
        HSTRING *a3)
{
  __int64 DeviceInfoList; // rax
  __int64 v6; // rdi
  char v7; // r15
  int String; // ebx
  unsigned int i; // r14d
  HKEY v10; // rsi
  __int64 v11; // rax
  __int64 v12; // rdx
  const char *v13; // r9
  __int64 result; // rax
  signed int LastError; // eax
  signed int v16; // eax
  signed int v17; // eax
  unsigned int v18; // [rsp+40h] [rbp-2E8h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-2E4h] BYREF
  DWORD Type; // [rsp+48h] [rbp-2E0h] BYREF
  const struct _DEVPROPKEY *v21; // [rsp+50h] [rbp-2D8h]
  GUID iid; // [rsp+58h] [rbp-2D0h] BYREF
  _OWORD v23[3]; // [rsp+68h] [rbp-2C0h] BYREF
  BYTE Data[16]; // [rsp+A0h] [rbp-288h] BYREF
  __int128 v25; // [rsp+B0h] [rbp-278h]
  __int128 v26; // [rsp+C0h] [rbp-268h]
  _BYTE v27[30]; // [rsp+D0h] [rbp-258h] BYREF
  WCHAR sourceString[256]; // [rsp+F0h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+328h] [rbp+0h]

  v21 = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_07bd92578572370284dbe53730fdfa75_Traceguids);
  *a3 = 0;
  memset(v23, 0, sizeof(v23));
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  v6 = DeviceInfoList;
  if ( DeviceInfoList == -1 )
  {
    LastError = GetLastError();
    String = LastError;
    if ( LastError > 0 )
      String = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_20;
  }
  if ( !(unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_DEVINTERFACE_NET, 0, 18, 0, 0) )
  {
    GetLastError();
    DevObjDestroyDeviceInfoList(v6);
LABEL_27:
    String = -2147024894;
    goto LABEL_20;
  }
  v7 = 0;
  String = -2147024809;
  LODWORD(v23[0]) = 48;
  for ( i = 0; (unsigned int)DevObjEnumDeviceInfo(v6, i, v23); ++i )
  {
    v10 = (HKEY)DevObjOpenDevRegKey(v6, v23, 1, 0, 2, 131097);
    if ( v10 != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    {
      Type = 1;
      *(_OWORD *)Data = 0;
      v25 = 0;
      v26 = 0;
      memset(v27, 0, sizeof(v27));
      cbData = 78;
      if ( RegQueryValueExW(v10, L"NetCfgInstanceId", 0, &Type, Data, &cbData) )
      {
        v17 = GetLastError();
        String = v17;
        if ( v17 > 0 )
          String = (unsigned __int16)v17 | 0x80070000;
      }
      else
      {
        iid = 0;
        String = IIDFromString((LPCOLESTR)Data, &iid);
        if ( String >= 0 )
        {
          v11 = *(_QWORD *)&iid.Data1 - *((_QWORD *)this + 4);
          if ( *(_QWORD *)&iid.Data1 == *((_QWORD *)this + 4) )
            v11 = *(_QWORD *)iid.Data4 - *((_QWORD *)this + 5);
          if ( !v11 )
          {
            v18 = 0;
            memset_0(sourceString, 0, sizeof(sourceString));
            if ( (unsigned int)DevObjGetDeviceProperty(v6, v23, v21, &v18, sourceString, 512, 0, 0) )
            {
              v12 = -1;
              do
                ++v12;
              while ( sourceString[v12] );
              String = WindowsCreateString(sourceString, v12, a3);
            }
            else
            {
              v16 = GetLastError();
              String = v16;
              if ( v16 > 0 )
                String = (unsigned __int16)v16 | 0x80070000;
            }
            RegCloseKey(v10);
            v7 = 1;
            break;
          }
        }
      }
      RegCloseKey(v10);
    }
  }
  DevObjDestroyDeviceInfoList(v6);
  if ( !v7 )
    goto LABEL_27;
LABEL_20:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      WPP_07bd92578572370284dbe53730fdfa75_Traceguids,
      (unsigned int)String);
  result = (unsigned int)String;
  while ( 2 )
  {
    try
    {
    }
    catch ( ... )
    {
      v18 = wil::details::in1diag3::Return_CaughtException(
              retaddr,
              (void *)0x1A7,
              (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\cadapterproperties.cpp",
              v13);
      result = v18;
      continue;
    }
    break;
  }
  return result;
}

```

## disassembly

```asm
0x180002bd0  mov     [rsp+arg_0], rbx
0x180002bd5  mov     [rsp+arg_18], rsi
0x180002bda  push    rdi
0x180002bdb  push    r12
0x180002bdd  push    r13
0x180002bdf  push    r14
0x180002be1  push    r15
0x180002be3  sub     rsp, 300h
0x180002bea  mov     rax, cs:__security_cookie
0x180002bf1  xor     rax, rsp
0x180002bf4  mov     [rsp+328h+var_38], rax
0x180002bfc  mov     r13, r8
0x180002bff  mov     [rsp+328h+var_2D8], rdx
0x180002c04  mov     r12, rcx
0x180002c07  lea     rax, WPP_GLOBAL_Control
0x180002c0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c15  cmp     rcx, rax
0x180002c18  jnz     loc_180002F18
0x180002c1e  xor     esi, esi
0x180002c20  mov     [r13+0], rsi
0x180002c24  xorps   xmm0, xmm0
0x180002c27  movups  [rsp+328h+var_2C0], xmm0
0x180002c2c  movups  [rsp+328h+var_2B0], xmm0
0x180002c31  movups  [rsp+328h+var_2A0], xmm0
0x180002c39  mov     [rsp+328h+lpData], rsi
0x180002c3e  xor     r9d, r9d
0x180002c41  xor     r8d, r8d
0x180002c44  xor     edx, edx
0x180002c46  xor     ecx, ecx
0x180002c48  call    cs:__imp_DevObjCreateDeviceInfoList
0x180002c4e  mov     rdi, rax
0x180002c51  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180002c55  jz      loc_180002E8C
0x180002c5b  mov     [rsp+328h+lpcbData], rsi
0x180002c60  mov     [rsp+328h+lpData], rsi
0x180002c65  mov     r9d, 12h
0x180002c6b  xor     r8d, r8d
0x180002c6e  lea     rdx, GUID_DEVINTERFACE_NET
0x180002c75  mov     rcx, rax
0x180002c78  call    cs:__imp_DevObjGetClassDevs
0x180002c7e  test    eax, eax
0x180002c80  jz      loc_180002EC3
0x180002c86  xor     r15b, r15b
0x180002c89  mov     ebx, 80070057h
0x180002c8e  mov     dword ptr [rsp+328h+var_2C0], 30h ; '0'
0x180002c96  mov     r14d, esi
0x180002c99  lea     r8, [rsp+328h+var_2C0]
0x180002c9e  mov     edx, r14d
0x180002ca1  mov     rcx, rdi
0x180002ca4  call    cs:__imp_DevObjEnumDeviceInfo
0x180002caa  test    eax, eax
0x180002cac  jz      loc_180002E38
0x180002cb2  mov     dword ptr [rsp+328h+lpcbData], 20019h
0x180002cba  mov     dword ptr [rsp+328h+lpData], 2
0x180002cc2  xor     r9d, r9d
0x180002cc5  mov     r8d, 1
0x180002ccb  lea     rdx, [rsp+328h+var_2C0]
0x180002cd0  mov     rcx, rdi
0x180002cd3  call    cs:__imp_DevObjOpenDevRegKey
0x180002cd9  mov     rsi, rax
0x180002cdc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180002ce0  jz      loc_180002D9D
0x180002ce6  mov     [rsp+328h+Type], 1
0x180002cee  xorps   xmm0, xmm0
0x180002cf1  movups  xmmword ptr [rsp+328h+Data], xmm0
0x180002cf9  movups  [rsp+328h+var_278], xmm0
0x180002d01  movups  [rsp+328h+var_268], xmm0
0x180002d09  movups  xmmword ptr [rsp+328h+var_258], xmm0
0x180002d11  movups  xmmword ptr [rsp+328h+var_258+0Eh], xmm0
0x180002d19  mov     [rsp+328h+cbData], 4Eh ; 'N'
0x180002d21  lea     rax, [rsp+328h+cbData]
0x180002d26  mov     [rsp+328h+lpcbData], rax; lpcbData
0x180002d2b  lea     rax, [rsp+328h+Data]
0x180002d33  mov     [rsp+328h+lpData], rax; lpData
0x180002d38  lea     r9, [rsp+328h+Type]; lpType
0x180002d3d  xor     r8d, r8d; lpReserved
0x180002d40  lea     rdx, ValueName; "NetCfgInstanceId"
0x180002d47  mov     rcx, rsi; hKey
0x180002d4a  call    cs:__imp_RegQueryValueExW
0x180002d50  test    eax, eax
0x180002d52  jnz     loc_180002EFA
0x180002d58  xorps   xmm0, xmm0
0x180002d5b  movups  xmmword ptr [rsp+328h+iid.Data1], xmm0
0x180002d60  lea     rdx, [rsp+328h+iid]; lpiid
0x180002d65  lea     rcx, [rsp+328h+Data]; lpsz
0x180002d6d  call    cs:__imp_IIDFromString
0x180002d73  mov     ebx, eax
0x180002d75  test    eax, eax
0x180002d77  js      short loc_180002D94
0x180002d79  mov     rax, qword ptr [rsp+328h+iid.Data1]
0x180002d7e  sub     rax, [r12+20h]
0x180002d83  jnz     short loc_180002D8F
0x180002d85  mov     rax, qword ptr [rsp+328h+iid.Data4]
0x180002d8a  sub     rax, [r12+28h]
0x180002d8f  test    rax, rax
0x180002d92  jz      short loc_180002DA5
0x180002d94  mov     rcx, rsi; hKey
0x180002d97  call    cs:__imp_RegCloseKey
0x180002d9d  inc     r14d
0x180002da0  jmp     loc_180002C99
0x180002da5  xor     ebx, ebx
0x180002da7  mov     [rsp+328h+var_2E8], ebx
0x180002dab  xor     edx, edx; Val
0x180002dad  mov     r8d, 200h; Size
0x180002db3  lea     rcx, [rsp+328h+sourceString]; void *
0x180002dbb  call    memset_0
0x180002dc0  mov     [rsp+328h+var_2F0], ebx
0x180002dc4  mov     [rsp+328h+var_2F8], rbx
0x180002dc9  mov     dword ptr [rsp+328h+lpcbData], 200h
0x180002dd1  lea     rax, [rsp+328h+sourceString]
0x180002dd9  mov     [rsp+328h+lpData], rax
0x180002dde  lea     r9, [rsp+328h+var_2E8]
0x180002de3  mov     r8, [rsp+328h+var_2D8]
0x180002de8  lea     rdx, [rsp+328h+var_2C0]
0x180002ded  mov     rcx, rdi
0x180002df0  call    cs:__imp_DevObjGetDeviceProperty
0x180002df6  test    eax, eax
0x180002df8  jz      loc_180002EDC
0x180002dfe  lea     rax, [rsp+328h+sourceString]
0x180002e06  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x180002e0d  nop     dword ptr [rax]
0x180002e10  inc     rdx; length
0x180002e13  cmp     [rax+rdx*2], bx
0x180002e17  jnz     short loc_180002E10
0x180002e19  mov     r8, r13; string
0x180002e1c  lea     rcx, [rsp+328h+sourceString]; sourceString
0x180002e24  call    cs:__imp_WindowsCreateString
0x180002e2a  mov     ebx, eax
0x180002e2c  mov     rcx, rsi; hKey
0x180002e2f  call    cs:__imp_RegCloseKey
0x180002e35  mov     r15b, 1
0x180002e38  mov     rcx, rdi
0x180002e3b  call    cs:__imp_DevObjDestroyDeviceInfoList
0x180002e41  test    r15b, r15b
0x180002e44  jz      loc_180002ED2
0x180002e4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180002e51  lea     rax, WPP_GLOBAL_Control
0x180002e58  cmp     rcx, rax
0x180002e5b  jnz     short loc_180002EA3
0x180002e5d  mov     eax, ebx
0x180002e5f  mov     rcx, [rsp+328h+var_38]
0x180002e67  xor     rcx, rsp; StackCookie
0x180002e6a  call    __security_check_cookie
0x180002e6f  lea     r11, [rsp+328h+var_28]
0x180002e77  mov     rbx, [r11+30h]
0x180002e7b  mov     rsi, [r11+48h]
0x180002e7f  mov     rsp, r11
0x180002e82  pop     r15
0x180002e84  pop     r14
0x180002e86  pop     r13
0x180002e88  pop     r12
0x180002e8a  pop     rdi
0x180002e8b  retn
0x180002e8c  call    cs:__imp_GetLastError
0x180002e92  mov     ebx, eax
0x180002e94  test    eax, eax
0x180002e96  jle     short loc_180002E4A
0x180002e98  movzx   ebx, ax
0x180002e9b  or      ebx, 80070000h
0x180002ea1  jmp     short loc_180002E4A
0x180002ea3  test    byte ptr [rcx+1Ch], 40h
0x180002ea7  jz      short loc_180002E5D
0x180002ea9  mov     edx, 11h
0x180002eae  mov     r9d, ebx
0x180002eb1  lea     r8, WPP_07bd92578572370284dbe53730fdfa75_Traceguids
0x180002eb8  mov     rcx, [rcx+10h]
0x180002ebc  call    WPP_SF_d
0x180002ec1  jmp     short loc_180002E5D
0x180002ec3  call    cs:__imp_GetLastError
0x180002ec9  mov     rcx, rdi
0x180002ecc  call    cs:__imp_DevObjDestroyDeviceInfoList
0x180002ed2  mov     ebx, 80070002h
0x180002ed7  jmp     loc_180002E4A
0x180002edc  call    cs:__imp_GetLastError
0x180002ee2  mov     ebx, eax
0x180002ee4  test    eax, eax
0x180002ee6  jle     loc_180002E2C
0x180002eec  movzx   ebx, ax
0x180002eef  or      ebx, 80070000h
0x180002ef5  jmp     loc_180002E2C
0x180002efa  call    cs:__imp_GetLastError
0x180002f00  mov     ebx, eax
0x180002f02  test    eax, eax
0x180002f04  jle     loc_180002D94
0x180002f0a  movzx   ebx, ax
0x180002f0d  or      ebx, 80070000h
0x180002f13  jmp     loc_180002D94
0x180002f18  test    byte ptr [rcx+1Ch], 40h
0x180002f1c  jz      loc_180002C1E
0x180002f22  mov     edx, 10h
0x180002f27  lea     r8, WPP_07bd92578572370284dbe53730fdfa75_Traceguids
0x180002f2e  mov     rcx, [rcx+10h]
0x180002f32  call    WPP_SF_
0x180002f37  jmp     loc_180002C1E
0x180002f3c  mov     eax, [rsp+328h+var_2E8]
0x180002f40  jmp     loc_180002E5F
```
