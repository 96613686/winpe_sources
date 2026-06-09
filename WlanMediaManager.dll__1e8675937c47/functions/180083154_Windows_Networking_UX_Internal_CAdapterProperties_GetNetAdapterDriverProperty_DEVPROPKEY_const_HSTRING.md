# Windows::Networking::UX::Internal::CAdapterProperties::GetNetAdapterDriverProperty(_DEVPROPKEY const &,HSTRING__ * *)

- ea: `0x180083154`
- end: `0x18008348e`
- name: `?GetNetAdapterDriverProperty@CAdapterProperties@Internal@UX@Networking@Windows@@AEAAJAEBU_DEVPROPKEY@@PEAPEAUHSTRING__@@@Z`
- size: `826`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::CAdapterProperties *__hidden this, const struct _DEVPROPKEY *, HSTRING *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180082280`

## callees

- `0x180003ed0`
- `0x180004a70`
- `0x18000de4c`
- `0x18001d4d4`
- `0x180083154`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800833a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800833c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180083406`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008341d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800833a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800833c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180083406`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008341d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800832cd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800832cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800833bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800833e1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800833bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800833e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180083399`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180083399`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800832f0`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800832f0`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x180083242`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x180083242`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x18008326f`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x18008326f`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1800831e8`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1800831e8`
- `DEVOBJ!DevObjGetClassDevs` at `0x18008321c`
- `DEVOBJ!DevObjGetClassDevs` at `0x18008321c`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x18008336e`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x18008336e`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1800833f4`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1800833f4`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::Internal::CAdapterProperties::GetNetAdapterDriverProperty(
        Windows::Networking::UX::Internal::CAdapterProperties *this,
        const struct _DEVPROPKEY *a2,
        HSTRING *a3)
{
  unsigned int v4; // r15d
  __int64 DeviceInfoList; // rax
  __int64 v6; // r14
  __int64 v7; // rsi
  char v8; // r13
  int v9; // ebx
  HKEY v10; // r12
  __int64 v11; // rax
  signed int v12; // eax
  signed int v13; // eax
  const char *v14; // r9
  signed int v15; // eax
  signed int LastError; // eax
  __int64 result; // rax
  Windows::Networking::UX::Internal::CAdapterProperties *v18; // [rsp+40h] [rbp-2E8h] BYREF
  DWORD cbData; // [rsp+48h] [rbp-2E0h] BYREF
  DWORD Type; // [rsp+4Ch] [rbp-2DCh] BYREF
  const struct _DEVPROPKEY *v21; // [rsp+50h] [rbp-2D8h]
  HSTRING *string; // [rsp+58h] [rbp-2D0h]
  GUID iid; // [rsp+60h] [rbp-2C8h] BYREF
  _OWORD v24[3]; // [rsp+70h] [rbp-2B8h] BYREF
  OLECHAR Data[40]; // [rsp+A0h] [rbp-288h] BYREF
  WCHAR sourceString[256]; // [rsp+F0h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+328h] [rbp+0h]

  string = a3;
  v21 = a2;
  v18 = this;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_07bd92578572370284dbe53730fdfa75_Traceguids);
  v4 = 0;
  *a3 = 0;
  memset(v24, 0, sizeof(v24));
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  v6 = DeviceInfoList;
  v7 = -1;
  if ( DeviceInfoList == -1 )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    v8 = 0;
    if ( (unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_DEVINTERFACE_NET, 0, 18, 0, 0) )
    {
      v9 = -2147024809;
      LODWORD(v24[0]) = 48;
      while ( (unsigned int)DevObjEnumDeviceInfo(v6, v4, v24) )
      {
        v10 = (HKEY)DevObjOpenDevRegKey(v6, v24, 1);
        if ( v10 != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
        {
          Type = 1;
          memset_0(Data, 0, 0x4Eu);
          cbData = 78;
          if ( RegQueryValueExW(v10, L"NetCfgInstanceId", 0, &Type, (LPBYTE)Data, &cbData) )
          {
            v12 = GetLastError();
            v9 = v12;
            if ( v12 > 0 )
              v9 = (unsigned __int16)v12 | 0x80070000;
          }
          else
          {
            iid = 0;
            v9 = IIDFromString(Data, &iid);
            if ( v9 >= 0 )
            {
              v11 = *(_QWORD *)&iid.Data1 - *((_QWORD *)v18 + 4);
              if ( *(_QWORD *)&iid.Data1 == *((_QWORD *)v18 + 4) )
                v11 = *(_QWORD *)iid.Data4 - *((_QWORD *)v18 + 5);
              if ( !v11 )
              {
                LODWORD(v18) = 0;
                memset_0(sourceString, 0, sizeof(sourceString));
                if ( (unsigned int)DevObjGetDeviceProperty(v6, v24, v21, &v18, sourceString, 512, 0, 0) )
                {
                  do
                    ++v7;
                  while ( sourceString[v7] );
                  v9 = WindowsCreateString(sourceString, v7, string);
                }
                else
                {
                  v13 = GetLastError();
                  v9 = v13;
                  if ( v13 > 0 )
                    v9 = (unsigned __int16)v13 | 0x80070000;
                }
                RegCloseKey(v10);
                v8 = 1;
                break;
              }
            }
          }
          RegCloseKey(v10);
        }
        ++v4;
      }
    }
    else
    {
      v15 = GetLastError();
      v9 = v15;
      if ( v15 > 0 )
        v9 = (unsigned __int16)v15 | 0x80070000;
    }
    DevObjDestroyDeviceInfoList(v6);
    if ( !v8 )
      v9 = -2147024894;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_07bd92578572370284dbe53730fdfa75_Traceguids, (unsigned int)v9);
  result = (unsigned int)v9;
  while ( 2 )
  {
    try
    {
    }
    catch ( ... )
    {
      LODWORD(v18) = wil::details::in1diag3::Return_CaughtException(
                       retaddr,
                       (void *)0x1A7,
                       (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\cadapterproperties.cpp",
                       v14);
      result = (unsigned int)v18;
      continue;
    }
    break;
  }
  return result;
}

```

## disassembly

```asm
0x180083154  mov     [rsp+arg_0], rbx
0x180083159  push    rsi
0x18008315a  push    r12
0x18008315c  push    r13
0x18008315e  push    r14
0x180083160  push    r15
0x180083162  sub     rsp, 300h
0x180083169  mov     rax, cs:__security_cookie
0x180083170  xor     rax, rsp
0x180083173  mov     [rsp+328h+var_38], rax
0x18008317b  mov     rbx, r8
0x18008317e  mov     [rsp+328h+string], rbx
0x180083183  mov     [rsp+328h+var_2D8], rdx
0x180083188  mov     [rsp+328h+var_2E8], rcx
0x18008318d  lea     r12, WPP_GLOBAL_Control
0x180083194  mov     rcx, cs:WPP_GLOBAL_Control
0x18008319b  cmp     rcx, r12
0x18008319e  jz      short loc_1800831BB
0x1800831a0  test    byte ptr [rcx+1Ch], 40h
0x1800831a4  jz      short loc_1800831BB
0x1800831a6  mov     edx, 10h
0x1800831ab  lea     r8, WPP_07bd92578572370284dbe53730fdfa75_Traceguids
0x1800831b2  mov     rcx, [rcx+10h]
0x1800831b6  call    WPP_SF_
0x1800831bb  xor     r15d, r15d
0x1800831be  mov     [rbx], r15
0x1800831c1  xorps   xmm0, xmm0
0x1800831c4  movups  [rsp+328h+var_2B8], xmm0
0x1800831c9  movups  [rsp+328h+var_2A8], xmm0
0x1800831d1  movups  [rsp+328h+var_298], xmm0
0x1800831d9  mov     [rsp+328h+lpData], r15
0x1800831de  xor     r9d, r9d
0x1800831e1  xor     r8d, r8d
0x1800831e4  xor     edx, edx
0x1800831e6  xor     ecx, ecx
0x1800831e8  call    cs:__imp_DevObjCreateDeviceInfoList
0x1800831ee  mov     r14, rax
0x1800831f1  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800831f5  cmp     rax, rsi
0x1800831f8  jz      loc_18008341D
0x1800831fe  mov     r13b, r15b
0x180083201  mov     [rsp+328h+lpcbData], r15
0x180083206  mov     [rsp+328h+lpData], r15
0x18008320b  lea     r9d, [r15+12h]
0x18008320f  xor     r8d, r8d
0x180083212  lea     rdx, GUID_DEVINTERFACE_NET
0x180083219  mov     rcx, rax
0x18008321c  call    cs:__imp_DevObjGetClassDevs
0x180083222  test    eax, eax
0x180083224  jz      loc_180083406
0x18008322a  mov     ebx, 80070057h
0x18008322f  mov     dword ptr [rsp+328h+var_2B8], 30h ; '0'
0x180083237  lea     r8, [rsp+328h+var_2B8]
0x18008323c  mov     edx, r15d
0x18008323f  mov     rcx, r14
0x180083242  call    cs:__imp_DevObjEnumDeviceInfo
0x180083248  test    eax, eax
0x18008324a  jz      loc_1800833EA
0x180083250  mov     dword ptr [rsp+328h+lpcbData], 20019h
0x180083258  mov     dword ptr [rsp+328h+lpData], 2
0x180083260  xor     r9d, r9d
0x180083263  lea     r8d, [r9+1]
0x180083267  lea     rdx, [rsp+328h+var_2B8]
0x18008326c  mov     rcx, r14
0x18008326f  call    cs:__imp_DevObjOpenDevRegKey
0x180083275  mov     r12, rax
0x180083278  cmp     rax, rsi
0x18008327b  jz      loc_1800833C1
0x180083281  mov     [rsp+328h+Type], 1
0x180083289  mov     ebx, 4Eh ; 'N'
0x18008328e  mov     r8d, ebx; Size
0x180083291  xor     edx, edx; Val
0x180083293  lea     rcx, [rsp+328h+Data]; void *
0x18008329b  call    memset_0
0x1800832a0  mov     [rsp+328h+cbData], ebx
0x1800832a4  lea     rax, [rsp+328h+cbData]
0x1800832a9  mov     [rsp+328h+lpcbData], rax; lpcbData
0x1800832ae  lea     rax, [rsp+328h+Data]
0x1800832b6  mov     [rsp+328h+lpData], rax; lpData
0x1800832bb  lea     r9, [rsp+328h+Type]; lpType
0x1800832c0  xor     r8d, r8d; lpReserved
0x1800832c3  lea     rdx, aNetcfginstance; "NetCfgInstanceId"
0x1800832ca  mov     rcx, r12; hKey
0x1800832cd  call    cs:__imp_RegQueryValueExW
0x1800832d3  test    eax, eax
0x1800832d5  jnz     loc_1800833A3
0x1800832db  xorps   xmm0, xmm0
0x1800832de  movups  xmmword ptr [rsp+328h+iid.Data1], xmm0
0x1800832e3  lea     rdx, [rsp+328h+iid]; lpiid
0x1800832e8  lea     rcx, [rsp+328h+Data]; lpsz
0x1800832f0  call    cs:__imp_IIDFromString
0x1800832f6  mov     ebx, eax
0x1800832f8  test    eax, eax
0x1800832fa  js      loc_1800833B8
0x180083300  mov     rax, qword ptr [rsp+328h+iid.Data1]
0x180083305  mov     rcx, [rsp+328h+var_2E8]
0x18008330a  sub     rax, [rcx+20h]
0x18008330e  jnz     short loc_180083319
0x180083310  mov     rax, qword ptr [rsp+328h+iid.Data4]
0x180083315  sub     rax, [rcx+28h]
0x180083319  test    rax, rax
0x18008331c  jnz     loc_1800833B8
0x180083322  xor     r15d, r15d
0x180083325  mov     dword ptr [rsp+328h+var_2E8], r15d
0x18008332a  mov     ebx, 200h
0x18008332f  mov     r8d, ebx; Size
0x180083332  xor     edx, edx; Val
0x180083334  lea     rcx, [rsp+328h+sourceString]; void *
0x18008333c  call    memset_0
0x180083341  mov     [rsp+328h+var_2F0], r15d
0x180083346  mov     [rsp+328h+var_2F8], r15
0x18008334b  mov     dword ptr [rsp+328h+lpcbData], ebx
0x18008334f  lea     rax, [rsp+328h+sourceString]
0x180083357  mov     [rsp+328h+lpData], rax
0x18008335c  lea     r9, [rsp+328h+var_2E8]
0x180083361  mov     r8, [rsp+328h+var_2D8]
0x180083366  lea     rdx, [rsp+328h+var_2B8]
0x18008336b  mov     rcx, r14
0x18008336e  call    cs:__imp_DevObjGetDeviceProperty
0x180083374  test    eax, eax
0x180083376  jz      short loc_1800833C9
0x180083378  lea     rax, [rsp+328h+sourceString]
0x180083380  inc     rsi
0x180083383  cmp     [rax+rsi*2], r15w
0x180083388  jnz     short loc_180083380
0x18008338a  mov     edx, esi; length
0x18008338c  mov     r8, [rsp+328h+string]; string
0x180083391  lea     rcx, [rsp+328h+sourceString]; sourceString
0x180083399  call    cs:__imp_WindowsCreateString
0x18008339f  mov     ebx, eax
0x1800833a1  jmp     short loc_1800833DE
0x1800833a3  call    cs:__imp_GetLastError
0x1800833a9  mov     ebx, eax
0x1800833ab  test    eax, eax
0x1800833ad  jle     short loc_1800833B8
0x1800833af  movzx   ebx, ax
0x1800833b2  or      ebx, 80070000h
0x1800833b8  mov     rcx, r12; hKey
0x1800833bb  call    cs:__imp_RegCloseKey
0x1800833c1  inc     r15d
0x1800833c4  jmp     loc_180083237
0x1800833c9  call    cs:__imp_GetLastError
0x1800833cf  mov     ebx, eax
0x1800833d1  test    eax, eax
0x1800833d3  jle     short loc_1800833DE
0x1800833d5  movzx   ebx, ax
0x1800833d8  or      ebx, 80070000h
0x1800833de  mov     rcx, r12; hKey
0x1800833e1  call    cs:__imp_RegCloseKey
0x1800833e7  mov     r13b, 1
0x1800833ea  lea     r12, WPP_GLOBAL_Control
0x1800833f1  mov     rcx, r14
0x1800833f4  call    cs:__imp_DevObjDestroyDeviceInfoList
0x1800833fa  test    r13b, r13b
0x1800833fd  jnz     short loc_180083432
0x1800833ff  mov     ebx, 80070002h
0x180083404  jmp     short loc_180083432
0x180083406  call    cs:__imp_GetLastError
0x18008340c  mov     ebx, eax
0x18008340e  test    eax, eax
0x180083410  jle     short loc_1800833F1
0x180083412  movzx   ebx, ax
0x180083415  or      ebx, 80070000h
0x18008341b  jmp     short loc_1800833F1
0x18008341d  call    cs:__imp_GetLastError
0x180083423  mov     ebx, eax
0x180083425  test    eax, eax
0x180083427  jle     short loc_180083432
0x180083429  movzx   ebx, ax
0x18008342c  or      ebx, 80070000h
0x180083432  mov     rcx, cs:WPP_GLOBAL_Control
0x180083439  cmp     rcx, r12
0x18008343c  jz      short loc_18008345C
0x18008343e  test    byte ptr [rcx+1Ch], 40h
0x180083442  jz      short loc_18008345C
0x180083444  mov     edx, 11h
0x180083449  mov     r9d, ebx
0x18008344c  lea     r8, WPP_07bd92578572370284dbe53730fdfa75_Traceguids
0x180083453  mov     rcx, [rcx+10h]
0x180083457  call    WPP_SF_d
0x18008345c  mov     eax, ebx
0x18008345e  jmp     short loc_180083464
0x180083460  mov     eax, dword ptr [rsp+328h+var_2E8]
0x180083464  mov     rcx, [rsp+328h+var_38]
0x18008346c  xor     rcx, rsp; StackCookie
0x18008346f  call    __security_check_cookie
0x180083474  mov     rbx, [rsp+328h+arg_0]
0x18008347c  add     rsp, 300h
0x180083483  pop     r15
0x180083485  pop     r14
0x180083487  pop     r13
0x180083489  pop     r12
0x18008348b  pop     rsi
0x18008348c  retn
```
