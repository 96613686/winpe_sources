# BdeSvcSQMDiffuserVolume(ulong)

- ea: `0x18001dea0`
- end: `0x18001e254`
- name: `?BdeSvcSQMDiffuserVolume@@YAJK@Z`
- size: `948`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1800053a0`

## callees

- `0x180009f60`
- `0x18001dea0`
- `0x180034070`

## import_xrefs

- `ntdll!WinSqmAddToStreamEx` at `0x18001e183`
- `ntdll!WinSqmAddToStreamEx` at `0x18001e183`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001df93`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001df93`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001e018`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001e11e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001e018`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001e11e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001e0a9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001e1b4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001e0a9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001e1b4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e228`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e228`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18001df37`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18001df37`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18001df4b`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18001df4b`

## string_xrefs

- `0x18001df5b`: `SYSTEM\CurrentControlSet\Services\BdeSvc\SQMState`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall BdeSvcSQMDiffuserVolume(int a1)
{
  LSTATUS v2; // eax
  unsigned int v3; // edi
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  LSTATUS ValueW; // eax
  unsigned int i; // ebx
  int v8; // edi
  const WCHAR *v9; // rcx
  LSTATUS v10; // eax
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  LSTATUS v13; // eax
  _DWORD v15[4]; // [rsp+58h] [rbp-29h]
  LPCWSTR lpValueName[3]; // [rsp+68h] [rbp-19h]
  HKEY hkey; // [rsp+80h] [rbp-1h] BYREF
  DWORD pcbData; // [rsp+88h] [rbp+7h] BYREF
  BYTE Data[8]; // [rsp+90h] [rbp+Fh] BYREF
  unsigned __int64 pvData; // [rsp+98h] [rbp+17h] BYREF
  struct _FILETIME FileTime; // [rsp+A0h] [rbp+1Fh] BYREF
  unsigned __int64 v22; // [rsp+A8h] [rbp+27h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+B0h] [rbp+2Fh] BYREF
  int v24; // [rsp+C0h] [rbp+3Fh] BYREF
  __int64 v25; // [rsp+C4h] [rbp+43h]
  int v26; // [rsp+CCh] [rbp+4Bh]

  v25 = 0;
  v26 = 0;
  lpValueName[0] = L"LastOSDiffuserEnc";
  hkey = 0;
  lpValueName[1] = L"LastFDVDiffuserEnc";
  *(_QWORD *)Data = 0;
  lpValueName[2] = L"LastRDVDiffuserEnc";
  pvData = 0;
  v22 = 0;
  pcbData = 8;
  v24 = 0;
  v15[0] = 1;
  v15[1] = 2;
  v15[2] = 4;
  SystemTime = 0;
  FileTime = 0;
  GetSystemTime(&SystemTime);
  SystemTimeToFileTime(&SystemTime, &FileTime);
  *(struct _FILETIME *)Data = FileTime;
  v2 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\BdeSvc\\SQMState",
         0,
         0,
         0,
         3u,
         0,
         &hkey,
         0);
  v3 = v2;
  if ( v2 )
  {
    if ( v2 > 0 )
      v3 = (unsigned __int16)v2 | 0x80070000;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      v5 = 174;
LABEL_7:
      WPP_SF_d(v4[2], v5, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids, v3);
    }
  }
  else
  {
    ValueW = RegGetValueW(hkey, 0, L"LastDiffuserSQM", 0x40u, 0, &pvData, &pcbData);
    v3 = ValueW;
    if ( (ValueW & 0xFFFFFFFD) != 0 )
    {
      if ( ValueW > 0 )
        v3 = (unsigned __int16)ValueW | 0x80070000;
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        v5 = 175;
        goto LABEL_7;
      }
    }
    else
    {
      for ( i = 0; i < 3; ++i )
      {
        v8 = v15[i];
        v9 = lpValueName[i];
        if ( (v8 & a1) != 0 )
        {
          v10 = RegSetValueExW(hkey, v9, 0, 0xBu, Data, 8u);
          v3 = v10;
          if ( v10 )
          {
            if ( v10 > 0 )
              v3 = (unsigned __int16)v10 | 0x80070000;
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
            {
              v12 = 176;
LABEL_34:
              WPP_SF_d(v11[2], v12, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids, v3);
              goto LABEL_36;
            }
            goto LABEL_36;
          }
        }
        else
        {
          pcbData = 8;
          if ( !RegGetValueW(hkey, 0, v9, 0x40u, 0, &v22, &pcbData) && v22 > pvData )
            a1 |= v8;
        }
      }
      if ( *(_QWORD *)Data - pvData >= 0x46B8E92D8000LL
        && (v24 = 16,
            HIDWORD(v25) = a1,
            LODWORD(v25) = 1,
            WinSqmAddToStreamEx(0, 9209, 1, &v24, 0),
            v13 = RegSetValueExW(hkey, L"LastDiffuserSQM", 0, 0xBu, Data, 8u),
            (v3 = v13) != 0) )
      {
        if ( v13 > 0 )
          v3 = (unsigned __int16)v13 | 0x80070000;
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        {
          v12 = 177;
          goto LABEL_34;
        }
      }
      else
      {
        v3 = 0;
      }
    }
  }
LABEL_36:
  if ( hkey )
    RegCloseKey(hkey);
  return v3;
}

```

## disassembly

```asm
0x18001dea0  mov     r11, rsp
0x18001dea3  mov     [r11+20h], rdi
0x18001dea7  push    rbp
0x18001dea8  lea     rbp, [r11-5Fh]
0x18001deac  sub     rsp, 0D0h
0x18001deb3  mov     rax, cs:__security_cookie
0x18001deba  xor     rax, rsp
0x18001debd  mov     [rbp+57h+var_8], rax
0x18001dec1  xor     eax, eax
0x18001dec3  mov     [r11+10h], rsi
0x18001dec7  mov     [rbp+57h+var_14], rax
0x18001decb  mov     esi, ecx
0x18001decd  mov     [rbp+57h+var_C], eax
0x18001ded0  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x18001ded4  lea     rax, aLastosdiffuser; "LastOSDiffuserEnc"
0x18001dedb  mov     [r11+18h], r14
0x18001dedf  xor     r14d, r14d
0x18001dee2  mov     [rbp+57h+lpValueName], rax
0x18001dee6  lea     rax, aLastfdvdiffuse; "LastFDVDiffuserEnc"
0x18001deed  mov     [rbp+57h+hkey], r14
0x18001def1  mov     [rbp+57h+var_68], rax
0x18001def5  xorps   xmm0, xmm0
0x18001def8  lea     rax, aLastrdvdiffuse; "LastRDVDiffuserEnc"
0x18001deff  mov     qword ptr [rbp+57h+Data], r14
0x18001df03  mov     [rbp+57h+var_60], rax
0x18001df07  mov     [rbp+57h+pvData], r14
0x18001df0b  mov     [rbp+57h+var_30], r14
0x18001df0f  mov     [rbp+57h+pcbData], 8
0x18001df16  mov     [rbp+57h+var_18], r14d
0x18001df1a  mov     [rbp+57h+var_80], 1
0x18001df21  mov     [rbp+57h+var_7C], 2
0x18001df28  mov     [rbp+57h+var_78], 4
0x18001df2f  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x18001df33  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], r14
0x18001df37  call    cs:__imp_GetSystemTime
0x18001df3e  nop     dword ptr [rax+rax+00h]
0x18001df43  lea     rdx, [rbp+57h+FileTime]; lpFileTime
0x18001df47  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x18001df4b  call    cs:__imp_SystemTimeToFileTime
0x18001df52  nop     dword ptr [rax+rax+00h]
0x18001df57  mov     rax, qword ptr [rbp+57h+FileTime.dwLowDateTime]
0x18001df5b  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\Bd"...
0x18001df62  mov     [rsp+40h], r14; lpdwDisposition
0x18001df67  xor     r9d, r9d; lpClass
0x18001df6a  mov     qword ptr [rbp+57h+Data], rax
0x18001df6e  xor     r8d, r8d; Reserved
0x18001df71  lea     rax, [rbp+57h+hkey]
0x18001df75  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001df7c  mov     [rsp+0D0h+phkResult], rax; phkResult
0x18001df81  mov     [rsp+0D0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18001df86  mov     [rsp+0D0h+samDesired], 3; samDesired
0x18001df8e  mov     [rsp+0D0h+dwOptions], r14d; dwOptions
0x18001df93  call    cs:__imp_RegCreateKeyExW
0x18001df9a  nop     dword ptr [rax+rax+00h]
0x18001df9f  mov     edi, eax
0x18001dfa1  test    eax, eax
0x18001dfa3  jz      short loc_18001DFEE
0x18001dfa5  jle     short loc_18001DFB0
0x18001dfa7  movzx   edi, ax
0x18001dfaa  or      edi, 80070000h
0x18001dfb0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dfb7  lea     rax, WPP_GLOBAL_Control
0x18001dfbe  cmp     rcx, rax
0x18001dfc1  jz      loc_18001E20F
0x18001dfc7  test    byte ptr [rcx+1Ch], 40h
0x18001dfcb  jz      loc_18001E20F
0x18001dfd1  mov     edx, 0AEh
0x18001dfd6  mov     rcx, [rcx+10h]
0x18001dfda  lea     r8, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids
0x18001dfe1  mov     r9d, edi
0x18001dfe4  call    WPP_SF_d
0x18001dfe9  jmp     loc_18001E20F
0x18001dfee  mov     rcx, [rbp+57h+hkey]; hkey
0x18001dff2  lea     rax, [rbp+57h+pcbData]
0x18001dff6  mov     [rsp+0D0h+lpSecurityAttributes], rax; pcbData
0x18001dffb  lea     r8, aLastdiffusersq; "LastDiffuserSQM"
0x18001e002  lea     rax, [rbp+57h+pvData]
0x18001e006  mov     r9d, 40h ; '@'; dwFlags
0x18001e00c  mov     qword ptr [rsp+0D0h+samDesired], rax; pvData
0x18001e011  xor     edx, edx; lpSubKey
0x18001e013  mov     qword ptr [rsp+0D0h+dwOptions], r14; pdwType
0x18001e018  call    cs:__imp_RegGetValueW
0x18001e01f  nop     dword ptr [rax+rax+00h]
0x18001e024  mov     edi, eax
0x18001e026  test    eax, 0FFFFFFFDh
0x18001e02b  jz      short loc_18001E065
0x18001e02d  test    eax, eax
0x18001e02f  jle     short loc_18001E03A
0x18001e031  movzx   edi, ax
0x18001e034  or      edi, 80070000h
0x18001e03a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e041  lea     rax, WPP_GLOBAL_Control
0x18001e048  cmp     rcx, rax
0x18001e04b  jz      loc_18001E20F
0x18001e051  test    byte ptr [rcx+1Ch], 40h
0x18001e055  jz      loc_18001E20F
0x18001e05b  mov     edx, 0AFh
0x18001e060  jmp     loc_18001DFD6
0x18001e065  mov     [rsp+0D0h+arg_0], rbx
0x18001e06d  mov     ebx, r14d
0x18001e070  cmp     ebx, 3
0x18001e073  jnb     loc_18001E141
0x18001e079  mov     eax, ebx
0x18001e07b  mov     edi, [rbp+rax*4+57h+var_80]
0x18001e07f  mov     rcx, [rbp+rax*8+57h+lpValueName]
0x18001e084  test    esi, edi
0x18001e086  jz      short loc_18001E0F1
0x18001e088  lea     rax, [rbp+57h+Data]
0x18001e08c  mov     [rsp+0D0h+samDesired], 8; cbData
0x18001e094  mov     rdx, rcx; lpValueName
0x18001e097  mov     qword ptr [rsp+0D0h+dwOptions], rax; lpData
0x18001e09c  mov     rcx, [rbp+57h+hkey]; hKey
0x18001e0a0  mov     r9d, 0Bh; dwType
0x18001e0a6  xor     r8d, r8d; Reserved
0x18001e0a9  call    cs:__imp_RegSetValueExW
0x18001e0b0  nop     dword ptr [rax+rax+00h]
0x18001e0b5  mov     edi, eax
0x18001e0b7  test    eax, eax
0x18001e0b9  jz      short loc_18001E13A
0x18001e0bb  jle     short loc_18001E0C6
0x18001e0bd  movzx   edi, ax
0x18001e0c0  or      edi, 80070000h
0x18001e0c6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e0cd  lea     rax, WPP_GLOBAL_Control
0x18001e0d4  cmp     rcx, rax
0x18001e0d7  jz      loc_18001E207
0x18001e0dd  test    byte ptr [rcx+1Ch], 40h
0x18001e0e1  jz      loc_18001E207
0x18001e0e7  mov     edx, 0B0h
0x18001e0ec  jmp     loc_18001E1EF
0x18001e0f1  lea     rax, [rbp+57h+pcbData]
0x18001e0f5  mov     [rbp+57h+pcbData], 8
0x18001e0fc  mov     [rsp+0D0h+lpSecurityAttributes], rax; pcbData
0x18001e101  mov     r8, rcx; lpValue
0x18001e104  mov     rcx, [rbp+57h+hkey]; hkey
0x18001e108  lea     rax, [rbp+57h+var_30]
0x18001e10c  mov     qword ptr [rsp+0D0h+samDesired], rax; pvData
0x18001e111  mov     r9d, 40h ; '@'; dwFlags
0x18001e117  xor     edx, edx; lpSubKey
0x18001e119  mov     qword ptr [rsp+0D0h+dwOptions], r14; pdwType
0x18001e11e  call    cs:__imp_RegGetValueW
0x18001e125  nop     dword ptr [rax+rax+00h]
0x18001e12a  test    eax, eax
0x18001e12c  jnz     short loc_18001E13A
0x18001e12e  mov     rax, [rbp+57h+pvData]
0x18001e132  cmp     [rbp+57h+var_30], rax
0x18001e136  jbe     short loc_18001E13A
0x18001e138  or      esi, edi
0x18001e13a  inc     ebx
0x18001e13c  jmp     loc_18001E070
0x18001e141  mov     rax, qword ptr [rbp+57h+Data]
0x18001e145  mov     rcx, 46B8E92D8000h
0x18001e14f  sub     rax, [rbp+57h+pvData]
0x18001e153  cmp     rax, rcx
0x18001e156  jb      loc_18001E204
0x18001e15c  lea     r9, [rbp+57h+var_18]
0x18001e160  mov     [rbp+57h+var_18], 10h
0x18001e167  mov     edx, 23F9h
0x18001e16c  mov     dword ptr [rbp+57h+var_14+4], esi
0x18001e16f  xor     ecx, ecx
0x18001e171  mov     dword ptr [rbp+57h+var_14], 1
0x18001e178  mov     r8d, 1
0x18001e17e  mov     [rsp+0D0h+dwOptions], r14d
0x18001e183  call    cs:__imp_WinSqmAddToStreamEx
0x18001e18a  nop     dword ptr [rax+rax+00h]
0x18001e18f  mov     rcx, [rbp+57h+hkey]; hKey
0x18001e193  lea     rax, [rbp+57h+Data]
0x18001e197  mov     [rsp+0D0h+samDesired], 8; cbData
0x18001e19f  lea     rdx, aLastdiffusersq; "LastDiffuserSQM"
0x18001e1a6  mov     r9d, 0Bh; dwType
0x18001e1ac  mov     qword ptr [rsp+0D0h+dwOptions], rax; lpData
0x18001e1b1  xor     r8d, r8d; Reserved
0x18001e1b4  call    cs:__imp_RegSetValueExW
0x18001e1bb  nop     dword ptr [rax+rax+00h]
0x18001e1c0  mov     edi, eax
0x18001e1c2  test    eax, eax
0x18001e1c4  jz      short loc_18001E204
0x18001e1c6  jle     short loc_18001E1D1
0x18001e1c8  movzx   edi, ax
0x18001e1cb  or      edi, 80070000h
0x18001e1d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e1d8  lea     rax, WPP_GLOBAL_Control
0x18001e1df  cmp     rcx, rax
0x18001e1e2  jz      short loc_18001E207
0x18001e1e4  test    byte ptr [rcx+1Ch], 40h
0x18001e1e8  jz      short loc_18001E207
0x18001e1ea  mov     edx, 0B1h
0x18001e1ef  mov     rcx, [rcx+10h]
0x18001e1f3  lea     r8, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids
0x18001e1fa  mov     r9d, edi
0x18001e1fd  call    WPP_SF_d
0x18001e202  jmp     short loc_18001E207
0x18001e204  mov     edi, r14d
0x18001e207  mov     rbx, [rsp+0D0h+arg_0]
0x18001e20f  mov     rcx, [rbp+57h+hkey]; hKey
0x18001e213  mov     r14, [rsp+0D0h+arg_10]
0x18001e21b  mov     rsi, [rsp+0D0h+arg_8]
0x18001e223  test    rcx, rcx
0x18001e226  jz      short loc_18001E234
0x18001e228  call    cs:__imp_RegCloseKey
0x18001e22f  nop     dword ptr [rax+rax+00h]
0x18001e234  mov     eax, edi
0x18001e236  mov     rcx, [rbp+57h+var_8]
0x18001e23a  xor     rcx, rsp; StackCookie
0x18001e23d  call    __security_check_cookie
0x18001e242  mov     rdi, [rsp+0D0h+arg_18]
0x18001e24a  add     rsp, 0D0h
0x18001e251  pop     rbp
0x18001e252  retn
```
