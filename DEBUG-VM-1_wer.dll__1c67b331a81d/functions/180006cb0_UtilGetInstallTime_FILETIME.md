# UtilGetInstallTime(_FILETIME *)

- ea: `0x180006cb0`
- end: `0x180006e7e`
- name: `?UtilGetInstallTime@@YAJPEAU_FILETIME@@@Z`
- size: `462`
- prototype: `__int64 __fastcall(LPFILETIME lpFileTime)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180017a18`
- `0x1800914d8`

## callees

- `0x180006cb0`
- `0x18000716c`
- `0x18001fe24`
- `0x18003e994`
- `0x180045cac`
- `0x180050db0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006e2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006e2b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180006d53`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180006d53`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006d8c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006d8c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006d1b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006d1b`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180006e1d`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180006e1d`

## string_xrefs

- `0x180006d10`: `Software\Microsoft\WindowsUpdate\Orchestrator\Installation\Target`
- `0x180006d32`: `UpdateTimestamp`
- `0x180006dc7`: `OobeCompleteTime`

## pseudocode

```c
__int64 __fastcall UtilGetInstallTime(LPFILETIME lpFileTime)
{
  LSTATUS ValueW; // eax
  unsigned __int64 v3; // r9
  char v4; // si
  struct _FILETIME v5; // rbx
  unsigned int BINARY; // ebx
  struct _FILETIME QWORD; // rax
  HKEY v9; // rcx
  signed int LastError; // eax
  bool pvData; // [rsp+28h] [rbp-21h]
  bool pvDataa; // [rsp+28h] [rbp-21h]
  bool v13; // [rsp+40h] [rbp-9h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-5h] BYREF
  unsigned int v15; // [rsp+48h] [rbp-1h] BYREF
  bool v16[8]; // [rsp+50h] [rbp+7h] BYREF
  HKEY hkey; // [rsp+58h] [rbp+Fh] BYREF
  SYSTEMTIME SystemTime; // [rsp+60h] [rbp+17h] BYREF

  v15 = 16;
  *(_QWORD *)v16 = 0;
  pcbData = 8;
  v13 = 0;
  hkey = 0;
  SystemTime = 0;
  ValueW = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\WindowsUpdate\\Orchestrator\\Installation\\Target",
             0,
             0x101u,
             &hkey);
  if ( ValueW || (ValueW = RegGetValueW(hkey, 0, L"UpdateTimestamp", 0x40u, 0, v16, &pcbData)) != 0 )
  {
    v4 = 0;
    if ( (int)ERROR_HR_FROM_WIN32(ValueW) < 0 )
    {
      *(_QWORD *)v16 = 0;
      v4 = 1;
      v13 = 1;
    }
  }
  else
  {
    v4 = 0;
  }
  v5 = *(struct _FILETIME *)v16;
  if ( hkey )
    RegCloseKey(hkey);
  if ( !v4 )
  {
    *lpFileTime = v5;
    return 0;
  }
  QWORD = (struct _FILETIME)UtilRegGetQWORD(
                              HKEY_LOCAL_MACHINE,
                              L"Software\\Microsoft\\Shell\\OOBE",
                              L"OobeCompleteTime",
                              v3,
                              &v13,
                              pvData);
  if ( !v13 )
  {
    *lpFileTime = QWORD;
    return 0;
  }
  BINARY = UtilRegGetBINARY(
             v9,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\OOBE\\Stats",
             L"EndTimeStamp",
             (unsigned __int8 *)&SystemTime,
             &v15,
             pvDataa);
  if ( (BINARY & 0x80000000) != 0 )
    return BINARY;
  if ( SystemTimeToFileTime(&SystemTime, lpFileTime) )
    return 0;
  LastError = GetLastError();
  BINARY = LastError;
  if ( LastError > 0 )
    BINARY = (unsigned __int16)LastError | 0x80070000;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 165, WPP_988ce82756cb3ec502560a762615dae0_Traceguids, BINARY);
  return BINARY;
}

```

## disassembly

```asm
0x180006cb0  push    rbp
0x180006cb2  push    rbx
0x180006cb3  push    rsi
0x180006cb4  push    rdi
0x180006cb5  lea     rbp, [rsp-3Fh]
0x180006cba  sub     rsp, 88h
0x180006cc1  mov     rax, cs:__security_cookie
0x180006cc8  xor     rax, rsp
0x180006ccb  mov     [rbp+57h+var_30], rax
0x180006ccf  mov     rdi, rcx
0x180006cd2  mov     [rbp+57h+var_58], 10h
0x180006cd9  xorps   xmm0, xmm0
0x180006cdc  mov     qword ptr [rbp+57h+var_50], 0
0x180006ce4  lea     rax, [rbp+57h+hkey]
0x180006ce8  mov     [rbp+57h+var_5C], 8
0x180006cef  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180006cf6  mov     [rsp+0A0h+phkResult], rax; phkResult
0x180006cfb  mov     r9d, 101h; samDesired
0x180006d01  mov     [rbp+57h+var_60], 0
0x180006d05  xor     r8d, r8d; ulOptions
0x180006d08  mov     [rbp+57h+hkey], 0
0x180006d10  lea     rdx, SubKey; "Software\\Microsoft\\WindowsUpdate\\Orc"...
0x180006d17  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x180006d1b  call    cs:__imp_RegOpenKeyExW
0x180006d21  test    eax, eax
0x180006d23  jnz     short loc_180006D5D
0x180006d25  mov     rcx, [rbp+57h+hkey]; hkey
0x180006d29  lea     rax, [rbp+57h+var_5C]
0x180006d2d  mov     [rsp+0A0h+pcbData], rax; pcbData
0x180006d32  lea     r8, Value; "UpdateTimestamp"
0x180006d39  lea     rax, [rbp+57h+var_50]
0x180006d3d  mov     r9d, 40h ; '@'; dwFlags
0x180006d43  mov     [rsp+0A0h+pvData], rax; bool
0x180006d48  xor     edx, edx; lpSubKey
0x180006d4a  mov     [rsp+0A0h+phkResult], 0; pdwType
0x180006d53  call    cs:__imp_RegGetValueW
0x180006d59  test    eax, eax
0x180006d5b  jz      short loc_180006D7C
0x180006d5d  mov     ecx, eax; unsigned int
0x180006d5f  xor     sil, sil
0x180006d62  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180006d67  test    eax, eax
0x180006d69  jns     short loc_180006D7F
0x180006d6b  mov     qword ptr [rbp+57h+var_50], 0
0x180006d73  mov     sil, 1
0x180006d76  mov     [rbp+57h+var_60], 1
0x180006d7a  jmp     short loc_180006D7F
0x180006d7c  xor     sil, sil
0x180006d7f  mov     rcx, [rbp+57h+hkey]; hKey
0x180006d83  mov     rbx, qword ptr [rbp+57h+var_50]
0x180006d87  test    rcx, rcx
0x180006d8a  jz      short loc_180006D92
0x180006d8c  call    cs:__imp_RegCloseKey
0x180006d92  test    sil, sil
0x180006d95  jnz     short loc_180006DBC
0x180006d97  mov     [rdi], ebx
0x180006d99  shr     rbx, 20h
0x180006d9d  mov     [rdi+4], ebx
0x180006da0  xor     ebx, ebx
0x180006da2  mov     eax, ebx
0x180006da4  mov     rcx, [rbp+57h+var_30]
0x180006da8  xor     rcx, rsp; StackCookie
0x180006dab  call    __security_check_cookie
0x180006db0  add     rsp, 88h
0x180006db7  pop     rdi
0x180006db8  pop     rsi
0x180006db9  pop     rbx
0x180006dba  pop     rbp
0x180006dbb  retn
0x180006dbc  lea     rax, [rbp+57h+var_60]
0x180006dc0  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x180006dc7  lea     r8, aOobecompleteti; "OobeCompleteTime"
0x180006dce  mov     [rsp+0A0h+phkResult], rax; bool *
0x180006dd3  lea     rdx, aSoftwareMicros_22; "Software\\Microsoft\\Shell\\OOBE"
0x180006dda  call    ?UtilRegGetQWORD@@YA_KPEAUHKEY__@@PEB_W1_KPEA_N_N@Z; UtilRegGetQWORD(HKEY__ *,wchar_t const *,wchar_t const *,unsigned __int64,bool *,bool)
0x180006ddf  cmp     [rbp+57h+var_60], 0
0x180006de3  jnz     short loc_180006DF0
0x180006de5  mov     [rdi], eax
0x180006de7  shr     rax, 20h
0x180006deb  mov     [rdi+4], eax
0x180006dee  jmp     short loc_180006DA0
0x180006df0  lea     rax, [rbp+57h+var_58]
0x180006df4  lea     r9, [rbp+57h+SystemTime]; unsigned __int8 *
0x180006df8  mov     [rsp+0A0h+phkResult], rax; unsigned int *
0x180006dfd  lea     r8, aEndtimestamp; "EndTimeStamp"
0x180006e04  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180006e0b  call    ?UtilRegGetBINARY@@YAJPEAUHKEY__@@PEB_W1PEAEPEAK_N@Z; UtilRegGetBINARY(HKEY__ *,wchar_t const *,wchar_t const *,uchar *,ulong *,bool)
0x180006e10  mov     ebx, eax
0x180006e12  test    eax, eax
0x180006e14  js      short loc_180006DA2
0x180006e16  mov     rdx, rdi; lpFileTime
0x180006e19  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x180006e1d  call    cs:__imp_SystemTimeToFileTime
0x180006e23  test    eax, eax
0x180006e25  jnz     loc_180006DA0
0x180006e2b  call    cs:__imp_GetLastError
0x180006e31  mov     ebx, eax
0x180006e33  test    eax, eax
0x180006e35  jle     short loc_180006E40
0x180006e37  movzx   ebx, ax
0x180006e3a  or      ebx, 80070000h
0x180006e40  mov     rcx, cs:WPP_GLOBAL_Control
0x180006e47  lea     rax, WPP_GLOBAL_Control
0x180006e4e  cmp     rcx, rax
0x180006e51  jz      loc_180006DA2
0x180006e57  test    byte ptr [rcx+1Ch], 1
0x180006e5b  jz      loc_180006DA2
0x180006e61  mov     rcx, [rcx+10h]
0x180006e65  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x180006e6c  mov     edx, 0A5h
0x180006e71  mov     r9d, ebx
0x180006e74  call    WPP_SF_d
0x180006e79  jmp     loc_180006DA2
```
