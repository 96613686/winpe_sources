# Windows::Networking::UX::Internal::CAdapterProperties::GetNetAdapterDriverProperty(_DEVPROPKEY const &,HSTRING__ * *)

- ea: `0x1800421ec`
- end: `0x180042526`
- name: `?GetNetAdapterDriverProperty@CAdapterProperties@Internal@UX@Networking@Windows@@AEAAJAEBU_DEVPROPKEY@@PEAPEAUHSTRING__@@@Z`
- size: `826`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::CAdapterProperties *__hidden this, const struct _DEVPROPKEY *, HSTRING *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180041978`

## callees

- `0x180002520`
- `0x1800030a0`
- `0x18000a6e4`
- `0x180037c4c`
- `0x1800421ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004243b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042461`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004249e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800424b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004243b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042461`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004249e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800424b5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042453`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042479`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042453`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042479`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180042365`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180042365`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180042431`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180042431`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180042388`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180042388`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x1800422da`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x1800422da`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x180042406`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x180042406`
- `DEVOBJ!DevObjGetClassDevs` at `0x1800422b4`
- `DEVOBJ!DevObjGetClassDevs` at `0x1800422b4`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18004248c`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18004248c`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180042280`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180042280`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x180042307`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x180042307`

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
0x1800421ec  mov     [rsp+arg_0], rbx
0x1800421f1  push    rsi
0x1800421f2  push    r12
0x1800421f4  push    r13
0x1800421f6  push    r14
0x1800421f8  push    r15
0x1800421fa  sub     rsp, 300h
0x180042201  mov     rax, cs:__security_cookie
0x180042208  xor     rax, rsp
0x18004220b  mov     [rsp+328h+var_38], rax
0x180042213  mov     rbx, r8
0x180042216  mov     [rsp+328h+string], rbx
0x18004221b  mov     [rsp+328h+var_2D8], rdx
0x180042220  mov     [rsp+328h+var_2E8], rcx
0x180042225  lea     r12, WPP_GLOBAL_Control
0x18004222c  mov     rcx, cs:WPP_GLOBAL_Control
0x180042233  cmp     rcx, r12
0x180042236  jz      short loc_180042253
0x180042238  test    byte ptr [rcx+1Ch], 40h
0x18004223c  jz      short loc_180042253
0x18004223e  mov     edx, 10h
0x180042243  lea     r8, WPP_07bd92578572370284dbe53730fdfa75_Traceguids
0x18004224a  mov     rcx, [rcx+10h]
0x18004224e  call    WPP_SF_
0x180042253  xor     r15d, r15d
0x180042256  mov     [rbx], r15
0x180042259  xorps   xmm0, xmm0
0x18004225c  movups  [rsp+328h+var_2B8], xmm0
0x180042261  movups  [rsp+328h+var_2A8], xmm0
0x180042269  movups  [rsp+328h+var_298], xmm0
0x180042271  mov     [rsp+328h+lpData], r15
0x180042276  xor     r9d, r9d
0x180042279  xor     r8d, r8d
0x18004227c  xor     edx, edx
0x18004227e  xor     ecx, ecx
0x180042280  call    cs:__imp_DevObjCreateDeviceInfoList
0x180042286  mov     r14, rax
0x180042289  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18004228d  cmp     rax, rsi
0x180042290  jz      loc_1800424B5
0x180042296  mov     r13b, r15b
0x180042299  mov     [rsp+328h+lpcbData], r15
0x18004229e  mov     [rsp+328h+lpData], r15
0x1800422a3  lea     r9d, [r15+12h]
0x1800422a7  xor     r8d, r8d
0x1800422aa  lea     rdx, GUID_DEVINTERFACE_NET
0x1800422b1  mov     rcx, rax
0x1800422b4  call    cs:__imp_DevObjGetClassDevs
0x1800422ba  test    eax, eax
0x1800422bc  jz      loc_18004249E
0x1800422c2  mov     ebx, 80070057h
0x1800422c7  mov     dword ptr [rsp+328h+var_2B8], 30h ; '0'
0x1800422cf  lea     r8, [rsp+328h+var_2B8]
0x1800422d4  mov     edx, r15d
0x1800422d7  mov     rcx, r14
0x1800422da  call    cs:__imp_DevObjEnumDeviceInfo
0x1800422e0  test    eax, eax
0x1800422e2  jz      loc_180042482
0x1800422e8  mov     dword ptr [rsp+328h+lpcbData], 20019h
0x1800422f0  mov     dword ptr [rsp+328h+lpData], 2
0x1800422f8  xor     r9d, r9d
0x1800422fb  lea     r8d, [r9+1]
0x1800422ff  lea     rdx, [rsp+328h+var_2B8]
0x180042304  mov     rcx, r14
0x180042307  call    cs:__imp_DevObjOpenDevRegKey
0x18004230d  mov     r12, rax
0x180042310  cmp     rax, rsi
0x180042313  jz      loc_180042459
0x180042319  mov     [rsp+328h+Type], 1
0x180042321  mov     ebx, 4Eh ; 'N'
0x180042326  mov     r8d, ebx; Size
0x180042329  xor     edx, edx; Val
0x18004232b  lea     rcx, [rsp+328h+Data]; void *
0x180042333  call    memset_0
0x180042338  mov     [rsp+328h+cbData], ebx
0x18004233c  lea     rax, [rsp+328h+cbData]
0x180042341  mov     [rsp+328h+lpcbData], rax; lpcbData
0x180042346  lea     rax, [rsp+328h+Data]
0x18004234e  mov     [rsp+328h+lpData], rax; lpData
0x180042353  lea     r9, [rsp+328h+Type]; lpType
0x180042358  xor     r8d, r8d; lpReserved
0x18004235b  lea     rdx, aNetcfginstance; "NetCfgInstanceId"
0x180042362  mov     rcx, r12; hKey
0x180042365  call    cs:__imp_RegQueryValueExW
0x18004236b  test    eax, eax
0x18004236d  jnz     loc_18004243B
0x180042373  xorps   xmm0, xmm0
0x180042376  movups  xmmword ptr [rsp+328h+iid.Data1], xmm0
0x18004237b  lea     rdx, [rsp+328h+iid]; lpiid
0x180042380  lea     rcx, [rsp+328h+Data]; lpsz
0x180042388  call    cs:__imp_IIDFromString
0x18004238e  mov     ebx, eax
0x180042390  test    eax, eax
0x180042392  js      loc_180042450
0x180042398  mov     rax, qword ptr [rsp+328h+iid.Data1]
0x18004239d  mov     rcx, [rsp+328h+var_2E8]
0x1800423a2  sub     rax, [rcx+20h]
0x1800423a6  jnz     short loc_1800423B1
0x1800423a8  mov     rax, qword ptr [rsp+328h+iid.Data4]
0x1800423ad  sub     rax, [rcx+28h]
0x1800423b1  test    rax, rax
0x1800423b4  jnz     loc_180042450
0x1800423ba  xor     r15d, r15d
0x1800423bd  mov     dword ptr [rsp+328h+var_2E8], r15d
0x1800423c2  mov     ebx, 200h
0x1800423c7  mov     r8d, ebx; Size
0x1800423ca  xor     edx, edx; Val
0x1800423cc  lea     rcx, [rsp+328h+sourceString]; void *
0x1800423d4  call    memset_0
0x1800423d9  mov     [rsp+328h+var_2F0], r15d
0x1800423de  mov     [rsp+328h+var_2F8], r15
0x1800423e3  mov     dword ptr [rsp+328h+lpcbData], ebx
0x1800423e7  lea     rax, [rsp+328h+sourceString]
0x1800423ef  mov     [rsp+328h+lpData], rax
0x1800423f4  lea     r9, [rsp+328h+var_2E8]
0x1800423f9  mov     r8, [rsp+328h+var_2D8]
0x1800423fe  lea     rdx, [rsp+328h+var_2B8]
0x180042403  mov     rcx, r14
0x180042406  call    cs:__imp_DevObjGetDeviceProperty
0x18004240c  test    eax, eax
0x18004240e  jz      short loc_180042461
0x180042410  lea     rax, [rsp+328h+sourceString]
0x180042418  inc     rsi
0x18004241b  cmp     [rax+rsi*2], r15w
0x180042420  jnz     short loc_180042418
0x180042422  mov     edx, esi; length
0x180042424  mov     r8, [rsp+328h+string]; string
0x180042429  lea     rcx, [rsp+328h+sourceString]; sourceString
0x180042431  call    cs:__imp_WindowsCreateString
0x180042437  mov     ebx, eax
0x180042439  jmp     short loc_180042476
0x18004243b  call    cs:__imp_GetLastError
0x180042441  mov     ebx, eax
0x180042443  test    eax, eax
0x180042445  jle     short loc_180042450
0x180042447  movzx   ebx, ax
0x18004244a  or      ebx, 80070000h
0x180042450  mov     rcx, r12; hKey
0x180042453  call    cs:__imp_RegCloseKey
0x180042459  inc     r15d
0x18004245c  jmp     loc_1800422CF
0x180042461  call    cs:__imp_GetLastError
0x180042467  mov     ebx, eax
0x180042469  test    eax, eax
0x18004246b  jle     short loc_180042476
0x18004246d  movzx   ebx, ax
0x180042470  or      ebx, 80070000h
0x180042476  mov     rcx, r12; hKey
0x180042479  call    cs:__imp_RegCloseKey
0x18004247f  mov     r13b, 1
0x180042482  lea     r12, WPP_GLOBAL_Control
0x180042489  mov     rcx, r14
0x18004248c  call    cs:__imp_DevObjDestroyDeviceInfoList
0x180042492  test    r13b, r13b
0x180042495  jnz     short loc_1800424CA
0x180042497  mov     ebx, 80070002h
0x18004249c  jmp     short loc_1800424CA
0x18004249e  call    cs:__imp_GetLastError
0x1800424a4  mov     ebx, eax
0x1800424a6  test    eax, eax
0x1800424a8  jle     short loc_180042489
0x1800424aa  movzx   ebx, ax
0x1800424ad  or      ebx, 80070000h
0x1800424b3  jmp     short loc_180042489
0x1800424b5  call    cs:__imp_GetLastError
0x1800424bb  mov     ebx, eax
0x1800424bd  test    eax, eax
0x1800424bf  jle     short loc_1800424CA
0x1800424c1  movzx   ebx, ax
0x1800424c4  or      ebx, 80070000h
0x1800424ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800424d1  cmp     rcx, r12
0x1800424d4  jz      short loc_1800424F4
0x1800424d6  test    byte ptr [rcx+1Ch], 40h
0x1800424da  jz      short loc_1800424F4
0x1800424dc  mov     edx, 11h
0x1800424e1  mov     r9d, ebx
0x1800424e4  lea     r8, WPP_07bd92578572370284dbe53730fdfa75_Traceguids
0x1800424eb  mov     rcx, [rcx+10h]
0x1800424ef  call    WPP_SF_d
0x1800424f4  mov     eax, ebx
0x1800424f6  jmp     short loc_1800424FC
0x1800424f8  mov     eax, dword ptr [rsp+328h+var_2E8]
0x1800424fc  mov     rcx, [rsp+328h+var_38]
0x180042504  xor     rcx, rsp; StackCookie
0x180042507  call    __security_check_cookie
0x18004250c  mov     rbx, [rsp+328h+arg_0]
0x180042514  add     rsp, 300h
0x18004251b  pop     r15
0x18004251d  pop     r14
0x18004251f  pop     r13
0x180042521  pop     r12
0x180042523  pop     rsi
0x180042524  retn
```
