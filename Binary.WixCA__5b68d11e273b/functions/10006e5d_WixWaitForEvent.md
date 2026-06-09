# WixWaitForEvent

- ea: `0x10006e5d`
- end: `0x10007086`
- name: `WixWaitForEvent`
- size: `553`
- prototype: `int __stdcall(MSIHANDLE hInstall)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x10006bb7`
- `0x10006e5d`
- `0x1000ad15`
- `0x1000c7b9`
- `0x1000d4ae`
- `0x1000d51f`
- `0x1000da66`
- `0x100106cb`

## import_xrefs

- `USER32!PostMessageW` at `0x1000706a`
- `USER32!PostMessageW` at `0x1000706a`
- `USER32!IsWindow` at `0x10007059`
- `USER32!IsWindow` at `0x10007059`
- `KERNEL32!CloseHandle` at `0x1000702d`
- `KERNEL32!CloseHandle` at `0x1000703c`
- `KERNEL32!CloseHandle` at `0x10007022`
- `KERNEL32!GetLastError` at `0x10006ee7`
- `KERNEL32!GetLastError` at `0x10006f46`
- `KERNEL32!GetLastError` at `0x10006f91`
- `KERNEL32!GetLastError` at `0x10006ee7`
- `KERNEL32!GetLastError` at `0x10006f46`
- `KERNEL32!GetLastError` at `0x10006f91`
- `KERNEL32!LocalFree` at `0x1000704b`
- `KERNEL32!LocalFree` at `0x1000704b`
- `KERNEL32!CreateEventW` at `0x10006f3d`
- `KERNEL32!CreateEventW` at `0x10006f88`
- `KERNEL32!CreateEventW` at `0x10006f2f`
- `KERNEL32!WaitForMultipleObjects` at `0x10006fd0`
- `KERNEL32!WaitForMultipleObjects` at `0x10006fd0`

## string_xrefs

- `0x10006eb0`: `Failed to create message window.`
- `0x10006f08`: `d:\a\_work\1\s\src\ext\ca\wixca\dll\test.cpp`
- `0x10006f67`: `d:\a\_work\1\s\src\ext\ca\wixca\dll\test.cpp`
- `0x10006fb2`: `d:\a\_work\1\s\src\ext\ca\wixca\dll\test.cpp`
- `0x10007001`: `d:\a\_work\1\s\src\ext\ca\wixca\dll\test.cpp`
- `0x10006f12`: `Failed to create the security descriptor for the events.`
- `0x10006f71`: `Failed to create the Global\WixWaitForEventFail event.`
- `0x10006fbc`: `Failed to create the Global\WixWaitForEventSucceed event.`

## pseudocode

```c
int __stdcall WixWaitForEvent(MSIHANDLE hInstall)
{
  int v1; // ebx
  signed int v2; // esi
  const WCHAR *v3; // eax
  signed int v4; // eax
  bool v5; // sf
  signed int v6; // eax
  bool v7; // sf
  signed int LastError; // eax
  bool v9; // sf
  signed int v10; // eax
  HWND v11; // edi
  _SECURITY_ATTRIBUTES EventAttributes; // [esp+Ch] [ebp-24h] BYREF
  HANDLE Handles; // [esp+18h] [ebp-18h] BYREF
  HANDLE hObject; // [esp+1Ch] [ebp-14h]
  int v16; // [esp+20h] [ebp-10h] BYREF
  HWND hWnd; // [esp+24h] [ebp-Ch] BYREF
  int v18; // [esp+28h] [ebp-8h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [esp+2Ch] [ebp-4h] BYREF

  v1 = 0;
  hWnd = 0;
  v18 = 0;
  v16 = 0;
  SecurityDescriptor = 0;
  memset(&EventAttributes, 0, sizeof(EventAttributes));
  v2 = sub_1000D51F(hInstall, (int)"WixWaitForEvent");
  if ( v2 >= 0 )
  {
    v2 = sub_10006BB7(&hWnd);
    if ( v2 >= 0 )
    {
      sub_1000C7B9(&v18, &v16);
      v3 = L"D:(A;;GA;;;WD)S:(ML;;NW;;;ME)";
      if ( v18 < 5 )
        v3 = L"D:(A;;GA;;;WD)";
      if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(v3, 1u, &SecurityDescriptor, 0) )
      {
        EventAttributes.lpSecurityDescriptor = SecurityDescriptor;
        EventAttributes.bInheritHandle = 0;
        EventAttributes.nLength = 12;
        Handles = CreateEventW(&EventAttributes, 0, 0, L"Global\\WixWaitForEventFail");
        if ( Handles )
        {
          hObject = CreateEventW(&EventAttributes, 0, 0, L"Global\\WixWaitForEventSucceed");
          if ( hObject )
          {
            v10 = WaitForMultipleObjects(2u, &Handles, 0, 0xFFFFFFFF);
            v1 = v10;
            if ( v10 )
            {
              if ( v10 == 1 )
              {
                v1 = 0;
              }
              else
              {
                if ( v10 > 0 )
                  v2 = (unsigned __int16)v10 | 0x80070000;
                else
                  v2 = v10;
                nullsub_1("d:\\a\\_work\\1\\s\\src\\ext\\ca\\wixca\\dll\\test.cpp", 121, v2);
                sub_1000DA66(v2, "Unexpected failure.");
              }
            }
            else
            {
              v1 = 1603;
            }
          }
          else
          {
            LastError = GetLastError();
            v2 = LastError;
            v9 = LastError < 0;
            if ( LastError > 0 )
            {
              v2 = (unsigned __int16)LastError | 0x80070000;
              v9 = 1;
            }
            if ( !v9 )
              v2 = -2147467259;
            nullsub_1("d:\\a\\_work\\1\\s\\src\\ext\\ca\\wixca\\dll\\test.cpp", 108, v2);
            sub_1000DA66(v2, "Failed to create the Global\\WixWaitForEventSucceed event.");
          }
        }
        else
        {
          v6 = GetLastError();
          v2 = v6;
          v7 = v6 < 0;
          if ( v6 > 0 )
          {
            v2 = (unsigned __int16)v6 | 0x80070000;
            v7 = 1;
          }
          if ( !v7 )
            v2 = -2147467259;
          nullsub_1("d:\\a\\_work\\1\\s\\src\\ext\\ca\\wixca\\dll\\test.cpp", 105, v2);
          sub_1000DA66(v2, "Failed to create the Global\\WixWaitForEventFail event.");
        }
      }
      else
      {
        v4 = GetLastError();
        v2 = v4;
        v5 = v4 < 0;
        if ( v4 > 0 )
        {
          v2 = (unsigned __int16)v4 | 0x80070000;
          v5 = 1;
        }
        if ( !v5 )
          v2 = -2147467259;
        nullsub_1("d:\\a\\_work\\1\\s\\src\\ext\\ca\\wixca\\dll\\test.cpp", 97, v2);
        sub_1000DA66(v2, "Failed to create the security descriptor for the events.");
      }
    }
    else
    {
      sub_1000DA66(v2, "Failed to create message window.");
    }
  }
  else
  {
    sub_1000DA66(v2, "Failed to initialize.");
  }
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  if ( Handles )
  {
    CloseHandle(Handles);
    Handles = 0;
  }
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  v11 = hWnd;
  if ( hWnd && IsWindow(hWnd) )
    PostMessageW(v11, 0x10u, 0, 0);
  if ( v2 < 0 )
    v1 = 1603;
  return sub_1000D4AE(v1);
}

```

## disassembly

```asm
0x10006e5d  push    ebp
0x10006e5e  mov     ebp, esp
0x10006e60  sub     esp, 24h
0x10006e63  push    ebx
0x10006e64  xor     eax, eax
0x10006e66  push    esi
0x10006e67  push    edi
0x10006e68  mov     ebx, eax
0x10006e6a  mov     [ebp+hWnd], eax
0x10006e6d  mov     [ebp+var_8], eax
0x10006e70  lea     edi, [ebp+EventAttributes]
0x10006e73  mov     [ebp+var_10], eax
0x10006e76  mov     [ebp+SecurityDescriptor], eax
0x10006e79  stosd
0x10006e7a  push    offset aWixwaitforeven_0; "WixWaitForEvent"
0x10006e7f  push    [ebp+hInstall]; hInstall
0x10006e82  stosd
0x10006e83  stosd
0x10006e84  call    sub_1000D51F
0x10006e89  mov     esi, eax
0x10006e8b  test    esi, esi
0x10006e8d  jns     short loc_10006EA1
0x10006e8f  push    offset aFailedToInitia_1; "Failed to initialize."
0x10006e94  push    esi
0x10006e95  call    sub_1000DA66
0x10006e9a  pop     ecx
0x10006e9b  pop     ecx
0x10006e9c  jmp     loc_1000701E
0x10006ea1  lea     eax, [ebp+hWnd]
0x10006ea4  push    eax
0x10006ea5  call    sub_10006BB7
0x10006eaa  mov     esi, eax
0x10006eac  test    esi, esi
0x10006eae  jns     short loc_10006EB7
0x10006eb0  push    offset aFailedToCreate_9; "Failed to create message window."
0x10006eb5  jmp     short loc_10006E94
0x10006eb7  lea     eax, [ebp+var_10]
0x10006eba  push    eax
0x10006ebb  lea     eax, [ebp+var_8]
0x10006ebe  push    eax
0x10006ebf  call    sub_1000C7B9
0x10006ec4  cmp     [ebp+var_8], 5
0x10006ec8  mov     eax, offset StringSecurityDescriptor; "D:(A;;GA;;;WD)S:(ML;;NW;;;ME)"
0x10006ecd  jge     short loc_10006ED4
0x10006ecf  mov     eax, offset aDAGaWd; "D:(A;;GA;;;WD)"
0x10006ed4  xor     edi, edi
0x10006ed6  lea     ecx, [ebp+SecurityDescriptor]
0x10006ed9  push    edi; SecurityDescriptorSize
0x10006eda  push    ecx; SecurityDescriptor
0x10006edb  push    1; StringSDRevision
0x10006edd  push    eax; StringSecurityDescriptor
0x10006ede  call    ConvertStringSecurityDescriptorToSecurityDescriptorW
0x10006ee3  test    eax, eax
0x10006ee5  jnz     short loc_10006F1C
0x10006ee7  call    ds:GetLastError
0x10006eed  mov     esi, eax
0x10006eef  test    esi, esi
0x10006ef1  jle     short loc_10006EFE
0x10006ef3  movzx   esi, si
0x10006ef6  or      esi, 80070000h
0x10006efc  test    esi, esi
0x10006efe  js      short loc_10006F05
0x10006f00  mov     esi, 80004005h
0x10006f05  push    esi
0x10006f06  push    61h ; 'a'
0x10006f08  push    offset aDAWork1SSrcExt_4; "d:\\a\\_work\\1\\s\\src\\ext\\ca\\wixca"...
0x10006f0d  call    nullsub_1
0x10006f12  push    offset aFailedToCreate_10; "Failed to create the security descripto"...
0x10006f17  jmp     loc_10006E94
0x10006f1c  mov     eax, [ebp+SecurityDescriptor]
0x10006f1f  push    offset aGlobalWixwaitf; "Global\\WixWaitForEventFail"
0x10006f24  push    edi; bInitialState
0x10006f25  mov     [ebp+EventAttributes.lpSecurityDescriptor], eax
0x10006f28  lea     eax, [ebp+EventAttributes]
0x10006f2b  push    edi; bManualReset
0x10006f2c  mov     [ebp+EventAttributes.bInheritHandle], edi
0x10006f2f  mov     edi, ds:CreateEventW
0x10006f35  push    eax; lpEventAttributes
0x10006f36  mov     [ebp+EventAttributes.nLength], 0Ch
0x10006f3d  call    edi ; CreateEventW
0x10006f3f  mov     [ebp+Handles], eax
0x10006f42  test    eax, eax
0x10006f44  jnz     short loc_10006F7B
0x10006f46  call    ds:GetLastError
0x10006f4c  mov     esi, eax
0x10006f4e  test    esi, esi
0x10006f50  jle     short loc_10006F5D
0x10006f52  movzx   esi, si
0x10006f55  or      esi, 80070000h
0x10006f5b  test    esi, esi
0x10006f5d  js      short loc_10006F64
0x10006f5f  mov     esi, 80004005h
0x10006f64  push    esi
0x10006f65  push    69h ; 'i'
0x10006f67  push    offset aDAWork1SSrcExt_4; "d:\\a\\_work\\1\\s\\src\\ext\\ca\\wixca"...
0x10006f6c  call    nullsub_1
0x10006f71  push    offset aFailedToCreate_11; "Failed to create the Global\\WixWaitFor"...
0x10006f76  jmp     loc_10006E94
0x10006f7b  push    offset aGlobalWixwaitf_0; "Global\\WixWaitForEventSucceed"
0x10006f80  push    0; bInitialState
0x10006f82  push    0; bManualReset
0x10006f84  lea     eax, [ebp+EventAttributes]
0x10006f87  push    eax; lpEventAttributes
0x10006f88  call    edi ; CreateEventW
0x10006f8a  mov     [ebp+hObject], eax
0x10006f8d  test    eax, eax
0x10006f8f  jnz     short loc_10006FC6
0x10006f91  call    ds:GetLastError
0x10006f97  mov     esi, eax
0x10006f99  test    esi, esi
0x10006f9b  jle     short loc_10006FA8
0x10006f9d  movzx   esi, si
0x10006fa0  or      esi, 80070000h
0x10006fa6  test    esi, esi
0x10006fa8  js      short loc_10006FAF
0x10006faa  mov     esi, 80004005h
0x10006faf  push    esi
0x10006fb0  push    6Ch ; 'l'
0x10006fb2  push    offset aDAWork1SSrcExt_4; "d:\\a\\_work\\1\\s\\src\\ext\\ca\\wixca"...
0x10006fb7  call    nullsub_1
0x10006fbc  push    offset aFailedToCreate_12; "Failed to create the Global\\WixWaitFor"...
0x10006fc1  jmp     loc_10006E94
0x10006fc6  push    0FFFFFFFFh; dwMilliseconds
0x10006fc8  push    0; bWaitAll
0x10006fca  lea     eax, [ebp+Handles]
0x10006fcd  push    eax; lpHandles
0x10006fce  push    2; nCount
0x10006fd0  call    ds:WaitForMultipleObjects
0x10006fd6  mov     ebx, eax
0x10006fd8  sub     eax, 0
0x10006fdb  jz      short loc_10007019
0x10006fdd  sub     eax, 1
0x10006fe0  jz      short loc_10007015
0x10006fe2  test    ebx, ebx
0x10006fe4  jz      short loc_1000701E
0x10006fe6  jg      short loc_10006FEC
0x10006fe8  mov     esi, ebx
0x10006fea  jmp     short loc_10006FF5
0x10006fec  movzx   esi, bx
0x10006fef  or      esi, 80070000h
0x10006ff5  test    esi, esi
0x10006ff7  js      short loc_10006FFE
0x10006ff9  mov     esi, 80004005h
0x10006ffe  push    esi
0x10006fff  push    79h ; 'y'
0x10007001  push    offset aDAWork1SSrcExt_4; "d:\\a\\_work\\1\\s\\src\\ext\\ca\\wixca"...
0x10007006  call    nullsub_1
0x1000700b  push    offset aUnexpectedFail; "Unexpected failure."
0x10007010  jmp     loc_10006E94
0x10007015  xor     ebx, ebx
0x10007017  jmp     short loc_1000701E
0x10007019  mov     ebx, 643h
0x1000701e  cmp     [ebp+hObject], 0
0x10007022  mov     edi, ds:CloseHandle
0x10007028  jz      short loc_10007033
0x1000702a  push    [ebp+hObject]; hObject
0x1000702d  call    edi ; CloseHandle
0x1000702f  and     [ebp+hObject], 0
0x10007033  cmp     [ebp+Handles], 0
0x10007037  jz      short loc_10007042
0x10007039  push    [ebp+Handles]; hObject
0x1000703c  call    edi ; CloseHandle
0x1000703e  and     [ebp+Handles], 0
0x10007042  cmp     [ebp+SecurityDescriptor], 0
0x10007046  jz      short loc_10007051
0x10007048  push    [ebp+SecurityDescriptor]; hMem
0x1000704b  call    ds:LocalFree
0x10007051  mov     edi, [ebp+hWnd]
0x10007054  test    edi, edi
0x10007056  jz      short loc_10007070
0x10007058  push    edi; hWnd
0x10007059  call    ds:IsWindow
0x1000705f  test    eax, eax
0x10007061  jz      short loc_10007070
0x10007063  push    0; lParam
0x10007065  push    0; wParam
0x10007067  push    10h; Msg
0x10007069  push    edi; hWnd
0x1000706a  call    ds:PostMessageW
0x10007070  test    esi, esi
0x10007072  jns     short loc_10007079
0x10007074  mov     ebx, 643h
0x10007079  push    ebx
0x1000707a  call    sub_1000D4AE
0x1000707f  pop     edi
0x10007080  pop     esi
0x10007081  pop     ebx
0x10007082  leave
0x10007083  retn    4
```
