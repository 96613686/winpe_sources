# WixQueryOsInfo

- ea: `0x10002cd0`
- end: `0x10002f38`
- name: `WixQueryOsInfo`
- size: `616`
- prototype: `int __stdcall(MSIHANDLE hInstall)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x10002cd0`
- `0x1000d4ae`
- `0x1000d51f`
- `0x1000da66`
- `0x1000f00c`
- `0x10010720`
- `0x10011390`

## import_xrefs

- `USER32!GetSystemMetrics` at `0x10002eca`
- `USER32!GetSystemMetrics` at `0x10002ede`
- `USER32!GetSystemMetrics` at `0x10002ef2`
- `USER32!GetSystemMetrics` at `0x10002f06`
- `USER32!GetSystemMetrics` at `0x10002ec2`
- `KERNEL32!GetVersionExW` at `0x10002d30`
- `KERNEL32!GetVersionExW` at `0x10002d30`

## string_xrefs

- `0x10002d7b`: `WIX_SUITE_COMMUNICATIONS`
- `0x10002e52`: `WIX_SUITE_SECURITY_APPLIANCE`
- `0x10002e8a`: `WIX_SUITE_COMPUTE_SERVER`

## pseudocode

```c
int __stdcall WixQueryOsInfo(MSIHANDLE hInstall)
{
  int v1; // ebx
  int v2; // eax
  int v3; // edi
  __int16 v4; // cx
  _BYTE VersionInformation[284]; // [esp+Ch] [ebp-120h] BYREF

  v1 = 0;
  memset(VersionInformation, 0, sizeof(VersionInformation));
  v2 = sub_1000D51F(hInstall, (int)"WixQueryOsInfo");
  v3 = v2;
  if ( v2 >= 0 )
  {
    *(_DWORD *)VersionInformation = 284;
    GetVersionExW((LPOSVERSIONINFOW)VersionInformation);
    v4 = *(_WORD *)&VersionInformation[280];
    if ( (VersionInformation[280] & 1) != 0 )
    {
      sub_1000F00C(L"WIX_SUITE_SMALLBUSINESS", 1);
      v4 = *(_WORD *)&VersionInformation[280];
    }
    if ( (v4 & 2) != 0 )
    {
      sub_1000F00C(L"WIX_SUITE_ENTERPRISE", 1);
      v4 = *(_WORD *)&VersionInformation[280];
    }
    if ( (v4 & 4) != 0 )
    {
      sub_1000F00C(L"WIX_SUITE_BACKOFFICE", 1);
      v4 = *(_WORD *)&VersionInformation[280];
    }
    if ( (v4 & 8) != 0 )
    {
      sub_1000F00C(L"WIX_SUITE_COMMUNICATIONS", 1);
      v4 = *(_WORD *)&VersionInformation[280];
    }
    if ( (v4 & 0x10) != 0 )
    {
      sub_1000F00C(L"WIX_SUITE_TERMINAL", 1);
      v4 = *(_WORD *)&VersionInformation[280];
    }
    if ( (v4 & 0x20) != 0 )
    {
      sub_1000F00C(L"WIX_SUITE_SMALLBUSINESS_RESTRICTED", 1);
      v4 = *(_WORD *)&VersionInformation[280];
    }
    if ( (v4 & 0x40) != 0 )
    {
      sub_1000F00C(L"WIX_SUITE_EMBEDDEDNT", 1);
      v4 = *(_WORD *)&VersionInformation[280];
    }
    if ( (v4 & 0x80u) != 0 )
    {
      sub_1000F00C(L"WIX_SUITE_DATACENTER", 1);
      v4 = *(_WORD *)&VersionInformation[280];
    }
    if ( (v4 & 0x100) != 0 )
    {
      sub_1000F00C(L"WIX_SUITE_SINGLEUSERTS", 1);
      v4 = *(_WORD *)&VersionInformation[280];
    }
    if ( (v4 & 0x200) != 0 )
    {
      sub_1000F00C(L"WIX_SUITE_PERSONAL", 1);
      v4 = *(_WORD *)&VersionInformation[280];
    }
    if ( (v4 & 0x400) != 0 )
    {
      sub_1000F00C(L"WIX_SUITE_BLADE", 1);
      v4 = *(_WORD *)&VersionInformation[280];
    }
    if ( (v4 & 0x800) != 0 )
    {
      sub_1000F00C(L"WIX_SUITE_EMBEDDED_RESTRICTED", 1);
      v4 = *(_WORD *)&VersionInformation[280];
    }
    if ( (v4 & 0x1000) != 0 )
    {
      sub_1000F00C(L"WIX_SUITE_SECURITY_APPLIANCE", 1);
      v4 = *(_WORD *)&VersionInformation[280];
    }
    if ( (v4 & 0x2000) != 0 )
    {
      sub_1000F00C(L"WIX_SUITE_STORAGE_SERVER", 1);
      v4 = *(_WORD *)&VersionInformation[280];
    }
    if ( (v4 & 0x4000) != 0 )
    {
      sub_1000F00C(L"WIX_SUITE_COMPUTE_SERVER", 1);
      v4 = *(_WORD *)&VersionInformation[280];
    }
    if ( v4 < 0 )
      sub_1000F00C(L"WIX_SUITE_WH_SERVER", 1);
    if ( *(_DWORD *)&VersionInformation[4] > 5u
      || *(_DWORD *)&VersionInformation[4] == 5 && *(_DWORD *)&VersionInformation[8] )
    {
      if ( GetSystemMetrics(89) )
        sub_1000F00C(L"WIX_SUITE_SERVERR2", 1);
      if ( GetSystemMetrics(87) )
        sub_1000F00C(L"WIX_SUITE_MEDIACENTER", 1);
      if ( GetSystemMetrics(88) )
        sub_1000F00C(L"WIX_SUITE_STARTER", 1);
      if ( GetSystemMetrics(86) )
        sub_1000F00C(L"WIX_SUITE_TABLETPC", 1);
    }
  }
  else
  {
    sub_1000DA66(v2, "WixQueryOsInfo failed to initialize");
  }
  if ( v3 < 0 )
    v1 = 1603;
  return sub_1000D4AE(v1);
}

```

## disassembly

```asm
0x10002cd0  push    ebp
0x10002cd1  mov     ebp, esp
0x10002cd3  sub     esp, 120h
0x10002cd9  mov     eax, ___security_cookie
0x10002cde  xor     eax, ebp
0x10002ce0  mov     [ebp+var_4], eax
0x10002ce3  push    ebx
0x10002ce4  push    esi
0x10002ce5  push    edi
0x10002ce6  mov     esi, 11Ch
0x10002ceb  lea     eax, [ebp+VersionInformation]
0x10002cf1  push    esi; Size
0x10002cf2  xor     ebx, ebx
0x10002cf4  push    ebx; Val
0x10002cf5  push    eax; void *
0x10002cf6  call    _memset
0x10002cfb  add     esp, 0Ch
0x10002cfe  push    offset aWixqueryosinfo_0; "WixQueryOsInfo"
0x10002d03  push    [ebp+hInstall]; hInstall
0x10002d06  call    sub_1000D51F
0x10002d0b  mov     edi, eax
0x10002d0d  test    edi, edi
0x10002d0f  jns     short loc_10002D23
0x10002d11  push    offset aWixqueryosinfo_1; "WixQueryOsInfo failed to initialize"
0x10002d16  push    edi
0x10002d17  call    sub_1000DA66
0x10002d1c  pop     ecx
0x10002d1d  pop     ecx
0x10002d1e  jmp     loc_10002F18
0x10002d23  lea     eax, [ebp+VersionInformation]
0x10002d29  mov     [ebp+VersionInformation.dwOSVersionInfoSize], esi
0x10002d2f  push    eax; lpVersionInformation
0x10002d30  call    ds:GetVersionExW
0x10002d36  mov     ecx, [ebp+var_8]
0x10002d39  xor     esi, esi
0x10002d3b  inc     esi
0x10002d3c  test    cl, 1
0x10002d3f  jz      short loc_10002D4F
0x10002d41  push    esi; int
0x10002d42  push    offset aWixSuiteSmallb; "WIX_SUITE_SMALLBUSINESS"
0x10002d47  call    sub_1000F00C
0x10002d4c  mov     ecx, [ebp+var_8]
0x10002d4f  test    cl, 2
0x10002d52  jz      short loc_10002D62
0x10002d54  push    esi; int
0x10002d55  push    offset aWixSuiteEnterp; "WIX_SUITE_ENTERPRISE"
0x10002d5a  call    sub_1000F00C
0x10002d5f  mov     ecx, [ebp+var_8]
0x10002d62  test    cl, 4
0x10002d65  jz      short loc_10002D75
0x10002d67  push    esi; int
0x10002d68  push    offset aWixSuiteBackof; "WIX_SUITE_BACKOFFICE"
0x10002d6d  call    sub_1000F00C
0x10002d72  mov     ecx, [ebp+var_8]
0x10002d75  test    cl, 8
0x10002d78  jz      short loc_10002D88
0x10002d7a  push    esi; int
0x10002d7b  push    offset aWixSuiteCommun; "WIX_SUITE_COMMUNICATIONS"
0x10002d80  call    sub_1000F00C
0x10002d85  mov     ecx, [ebp+var_8]
0x10002d88  test    cl, 10h
0x10002d8b  jz      short loc_10002D9B
0x10002d8d  push    esi; int
0x10002d8e  push    offset aWixSuiteTermin; "WIX_SUITE_TERMINAL"
0x10002d93  call    sub_1000F00C
0x10002d98  mov     ecx, [ebp+var_8]
0x10002d9b  test    cl, 20h
0x10002d9e  jz      short loc_10002DAE
0x10002da0  push    esi; int
0x10002da1  push    offset aWixSuiteSmallb_0; "WIX_SUITE_SMALLBUSINESS_RESTRICTED"
0x10002da6  call    sub_1000F00C
0x10002dab  mov     ecx, [ebp+var_8]
0x10002dae  test    cl, 40h
0x10002db1  jz      short loc_10002DC1
0x10002db3  push    esi; int
0x10002db4  push    offset aWixSuiteEmbedd; "WIX_SUITE_EMBEDDEDNT"
0x10002db9  call    sub_1000F00C
0x10002dbe  mov     ecx, [ebp+var_8]
0x10002dc1  test    cl, cl
0x10002dc3  jns     short loc_10002DD3
0x10002dc5  push    esi; int
0x10002dc6  push    offset aWixSuiteDatace; "WIX_SUITE_DATACENTER"
0x10002dcb  call    sub_1000F00C
0x10002dd0  mov     ecx, [ebp+var_8]
0x10002dd3  mov     eax, ecx
0x10002dd5  xor     edx, edx
0x10002dd7  and     eax, 100h
0x10002ddc  cmp     dx, ax
0x10002ddf  jz      short loc_10002DEF
0x10002de1  push    esi; int
0x10002de2  push    offset aWixSuiteSingle; "WIX_SUITE_SINGLEUSERTS"
0x10002de7  call    sub_1000F00C
0x10002dec  mov     ecx, [ebp+var_8]
0x10002def  mov     eax, ecx
0x10002df1  xor     edx, edx
0x10002df3  and     eax, 200h
0x10002df8  cmp     dx, ax
0x10002dfb  jz      short loc_10002E0B
0x10002dfd  push    esi; int
0x10002dfe  push    offset aWixSuitePerson; "WIX_SUITE_PERSONAL"
0x10002e03  call    sub_1000F00C
0x10002e08  mov     ecx, [ebp+var_8]
0x10002e0b  mov     eax, ecx
0x10002e0d  xor     edx, edx
0x10002e0f  and     eax, 400h
0x10002e14  cmp     dx, ax
0x10002e17  jz      short loc_10002E27
0x10002e19  push    esi; int
0x10002e1a  push    offset aWixSuiteBlade; "WIX_SUITE_BLADE"
0x10002e1f  call    sub_1000F00C
0x10002e24  mov     ecx, [ebp+var_8]
0x10002e27  mov     eax, ecx
0x10002e29  xor     edx, edx
0x10002e2b  and     eax, 800h
0x10002e30  cmp     dx, ax
0x10002e33  jz      short loc_10002E43
0x10002e35  push    esi; int
0x10002e36  push    offset aWixSuiteEmbedd_0; "WIX_SUITE_EMBEDDED_RESTRICTED"
0x10002e3b  call    sub_1000F00C
0x10002e40  mov     ecx, [ebp+var_8]
0x10002e43  mov     eax, ecx
0x10002e45  xor     edx, edx
0x10002e47  and     eax, 1000h
0x10002e4c  cmp     dx, ax
0x10002e4f  jz      short loc_10002E5F
0x10002e51  push    esi; int
0x10002e52  push    offset aWixSuiteSecuri; "WIX_SUITE_SECURITY_APPLIANCE"
0x10002e57  call    sub_1000F00C
0x10002e5c  mov     ecx, [ebp+var_8]
0x10002e5f  mov     eax, ecx
0x10002e61  xor     edx, edx
0x10002e63  and     eax, 2000h
0x10002e68  cmp     dx, ax
0x10002e6b  jz      short loc_10002E7B
0x10002e6d  push    esi; int
0x10002e6e  push    offset aWixSuiteStorag; "WIX_SUITE_STORAGE_SERVER"
0x10002e73  call    sub_1000F00C
0x10002e78  mov     ecx, [ebp+var_8]
0x10002e7b  mov     eax, ecx
0x10002e7d  xor     edx, edx
0x10002e7f  and     eax, 4000h
0x10002e84  cmp     dx, ax
0x10002e87  jz      short loc_10002E97
0x10002e89  push    esi; int
0x10002e8a  push    offset aWixSuiteComput; "WIX_SUITE_COMPUTE_SERVER"
0x10002e8f  call    sub_1000F00C
0x10002e94  mov     ecx, [ebp+var_8]
0x10002e97  and     ecx, 8000h
0x10002e9d  xor     eax, eax
0x10002e9f  cmp     ax, cx
0x10002ea2  jz      short loc_10002EAF
0x10002ea4  push    esi; int
0x10002ea5  push    offset aWixSuiteWhServ; "WIX_SUITE_WH_SERVER"
0x10002eaa  call    sub_1000F00C
0x10002eaf  cmp     [ebp+VersionInformation.dwMajorVersion], 5
0x10002eb6  ja      short loc_10002EC2
0x10002eb8  jnz     short loc_10002F18
0x10002eba  cmp     [ebp+VersionInformation.dwMinorVersion], ebx
0x10002ec0  jbe     short loc_10002F18
0x10002ec2  mov     esi, ds:GetSystemMetrics
0x10002ec8  push    59h ; 'Y'; nIndex
0x10002eca  call    esi ; GetSystemMetrics
0x10002ecc  test    eax, eax
0x10002ece  jz      short loc_10002EDC
0x10002ed0  push    1; int
0x10002ed2  push    offset aWixSuiteServer; "WIX_SUITE_SERVERR2"
0x10002ed7  call    sub_1000F00C
0x10002edc  push    57h ; 'W'; nIndex
0x10002ede  call    esi ; GetSystemMetrics
0x10002ee0  test    eax, eax
0x10002ee2  jz      short loc_10002EF0
0x10002ee4  push    1; int
0x10002ee6  push    offset aWixSuiteMediac; "WIX_SUITE_MEDIACENTER"
0x10002eeb  call    sub_1000F00C
0x10002ef0  push    58h ; 'X'; nIndex
0x10002ef2  call    esi ; GetSystemMetrics
0x10002ef4  test    eax, eax
0x10002ef6  jz      short loc_10002F04
0x10002ef8  push    1; int
0x10002efa  push    offset aWixSuiteStarte; "WIX_SUITE_STARTER"
0x10002eff  call    sub_1000F00C
0x10002f04  push    56h ; 'V'; nIndex
0x10002f06  call    esi ; GetSystemMetrics
0x10002f08  test    eax, eax
0x10002f0a  jz      short loc_10002F18
0x10002f0c  push    1; int
0x10002f0e  push    offset aWixSuiteTablet; "WIX_SUITE_TABLETPC"
0x10002f13  call    sub_1000F00C
0x10002f18  test    edi, edi
0x10002f1a  jns     short loc_10002F21
0x10002f1c  mov     ebx, 643h
0x10002f21  push    ebx
0x10002f22  call    sub_1000D4AE
0x10002f27  mov     ecx, [ebp+var_4]
0x10002f2a  pop     edi
0x10002f2b  pop     esi
0x10002f2c  xor     ecx, ebp; StackCookie
0x10002f2e  pop     ebx
0x10002f2f  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10002f34  leave
0x10002f35  retn    4
```
