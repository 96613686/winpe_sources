# Sid::FromWellKnownSid(WELL_KNOWN_SID_TYPE)

- ea: `0x18002883c`
- end: `0x180028a9d`
- name: `?FromWellKnownSid@Sid@@SA?AV1@W4WELL_KNOWN_SID_TYPE@@@Z`
- size: `609`
- prototype: `void **__fastcall(void **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006960`

## callees

- `0x1800032a0`
- `0x180003d14`
- `0x180003d20`
- `0x18000b29c`
- `0x18000dd9c`
- `0x1800195c4`
- `0x18002310c`
- `0x1800284b8`
- `0x18002883c`
- `0x180028d60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002895f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800289c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028a2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002895f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800289c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028a2b`
- `ADVAPI32!LookupAccountNameW` at `0x1800288f1`
- `ADVAPI32!LookupAccountNameW` at `0x1800288f1`
- `ADVAPI32!CreateWellKnownSid` at `0x180028925`
- `ADVAPI32!CreateWellKnownSid` at `0x180028925`
- `KERNEL32!GetComputerNameW` at `0x180028898`
- `KERNEL32!GetComputerNameW` at `0x180028898`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void **__fastcall Sid::FromWellKnownSid(void **a1)
{
  signed int v3; // eax
  unsigned int v4; // ebx
  signed int LastError; // eax
  unsigned int v6; // ebx
  signed int v7; // eax
  unsigned int v8; // ebx
  int v9; // eax
  __int64 v10; // r10
  DWORD nSize; // [rsp+40h] [rbp-C0h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cchReferencedDomainName; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cbSid; // [rsp+4Ch] [rbp-B4h] BYREF
  DWORD v15[6]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Buffer[8]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v18; // [rsp+A0h] [rbp-60h]
  WCHAR ReferencedDomainName[8]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v20; // [rsp+C0h] [rbp-40h]
  _BYTE Sid[80]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE pSid[80]; // [rsp+120h] [rbp+20h] BYREF

  *(_QWORD *)v15 = a1;
  memset_0(Sid, 0, 0x44u);
  nSize = 16;
  *(_OWORD *)Buffer = 0;
  v18 = 0;
  if ( !GetComputerNameW(Buffer, &nSize) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 17, WPP_a33adb8c03dc3fcc91b55e28a073fb24_Traceguids, v6);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v6);
    throw (ErrorCodeException *)pExceptionObject;
  }
  cchReferencedDomainName = 16;
  cbSid = 68;
  peUse = 0;
  *(_OWORD *)ReferencedDomainName = 0;
  v20 = 0;
  if ( !LookupAccountNameW(0, Buffer, Sid, &cbSid, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
  {
    v7 = GetLastError();
    v8 = v7;
    if ( v7 > 0 )
      v8 = (unsigned __int16)v7 | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v9 = std::array<unsigned short,16>::data(Buffer);
      WPP_SF_Sd(*(_QWORD *)(v10 + 16), 18, (unsigned int)WPP_a33adb8c03dc3fcc91b55e28a073fb24_Traceguids, v9, v8);
    }
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v8);
    throw (ErrorCodeException *)pExceptionObject;
  }
  memset_0(pSid, 0, 0x44u);
  v15[0] = 68;
  if ( !CreateWellKnownSid(WinBuiltinAdministratorsSid, Sid, pSid, v15) )
  {
    v3 = GetLastError();
    v4 = v3;
    if ( v3 > 0 )
      v4 = (unsigned __int16)v3 | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_dd(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 19, WPP_a33adb8c03dc3fcc91b55e28a073fb24_Traceguids, 26, v4);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v4);
    throw (ErrorCodeException *)pExceptionObject;
  }
  Sid::FromPSID(a1, pSid);
  return a1;
}

```

## disassembly

```asm
0x18002883c  mov     [rsp-8+arg_8], rbx
0x180028841  mov     [rsp-8+arg_10], rdi
0x180028846  push    rbp
0x180028847  lea     rbp, [rsp-80h]
0x18002884c  sub     rsp, 180h
0x180028853  mov     rax, cs:__security_cookie
0x18002885a  xor     rax, rsp
0x18002885d  mov     [rbp+80h+var_10], rax
0x180028861  mov     rbx, rcx
0x180028864  mov     qword ptr [rsp+180h+var_130], rcx
0x180028869  mov     edi, 44h ; 'D'
0x18002886e  lea     rcx, [rbp+80h+Sid]; void *
0x180028872  mov     r8d, edi; Size
0x180028875  xor     edx, edx; Val
0x180028877  call    memset_0
0x18002887c  xorps   xmm0, xmm0
0x18002887f  mov     [rsp+180h+nSize], 10h
0x180028887  lea     rdx, [rsp+180h+nSize]; nSize
0x18002888c  lea     rcx, [rbp+80h+Buffer]; lpBuffer
0x180028890  movups  xmmword ptr [rbp+80h+Buffer], xmm0
0x180028894  movups  [rbp+80h+var_E0], xmm0
0x180028898  call    cs:__imp_GetComputerNameW
0x18002889e  test    eax, eax
0x1800288a0  jz      loc_1800289C7
0x1800288a6  xorps   xmm0, xmm0
0x1800288a9  mov     [rsp+180h+var_138], 10h
0x1800288b1  lea     rax, [rsp+180h+var_13C]
0x1800288b6  mov     [rsp+180h+cbSid], edi
0x1800288ba  mov     [rsp+180h+peUse], rax; peUse
0x1800288bf  lea     r9, [rsp+180h+cbSid]; cbSid
0x1800288c4  lea     rax, [rsp+180h+var_138]
0x1800288c9  mov     [rsp+180h+var_13C], 0
0x1800288d1  mov     [rsp+180h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800288d6  lea     r8, [rbp+80h+Sid]; Sid
0x1800288da  lea     rax, [rbp+80h+var_D0]
0x1800288de  xor     ecx, ecx; lpSystemName
0x1800288e0  lea     rdx, [rbp+80h+Buffer]; lpAccountName
0x1800288e4  mov     [rsp+180h+ReferencedDomainName], rax; ReferencedDomainName
0x1800288e9  movups  xmmword ptr [rbp+80h+var_D0], xmm0
0x1800288ed  movups  [rbp+80h+var_C0], xmm0
0x1800288f1  call    cs:__imp_LookupAccountNameW
0x1800288f7  test    eax, eax
0x1800288f9  jz      loc_180028A2B
0x1800288ff  mov     r8d, edi; Size
0x180028902  lea     rcx, [rbp+80h+pSid]; void *
0x180028906  xor     edx, edx; Val
0x180028908  call    memset_0
0x18002890d  mov     [rsp+180h+var_130], edi
0x180028911  lea     r9, [rsp+180h+var_130]; cbSid
0x180028916  mov     edi, 1Ah
0x18002891b  lea     r8, [rbp+80h+pSid]; pSid
0x18002891f  mov     ecx, edi; WellKnownSidType
0x180028921  lea     rdx, [rbp+80h+Sid]; DomainSid
0x180028925  call    cs:__imp_CreateWellKnownSid
0x18002892b  test    eax, eax
0x18002892d  jz      short loc_18002895F
0x18002892f  lea     rdx, [rbp+80h+pSid]
0x180028933  mov     rcx, rbx
0x180028936  call    ?FromPSID@Sid@@SA?AV1@PEAX@Z; Sid::FromPSID(void *)
0x18002893b  mov     rax, rbx
0x18002893e  mov     rcx, [rbp+80h+var_10]
0x180028942  xor     rcx, rsp; StackCookie
0x180028945  call    __security_check_cookie
0x18002894a  lea     r11, [rsp+180h+var_s0]
0x180028952  mov     rbx, [r11+18h]
0x180028956  mov     rdi, [r11+20h]
0x18002895a  mov     rsp, r11
0x18002895d  pop     rbp
0x18002895e  retn
0x18002895f  call    cs:__imp_GetLastError
0x180028965  mov     ebx, eax
0x180028967  test    eax, eax
0x180028969  jle     short loc_180028974
0x18002896b  movzx   ebx, ax
0x18002896e  or      ebx, 80070000h
0x180028974  mov     rcx, cs:WPP_GLOBAL_Control
0x18002897b  lea     rax, WPP_GLOBAL_Control
0x180028982  cmp     rcx, rax
0x180028985  jz      short loc_1800289A9
0x180028987  test    byte ptr [rcx+1Ch], 1
0x18002898b  jz      short loc_1800289A9
0x18002898d  mov     rcx, [rcx+10h]
0x180028991  lea     r8, WPP_a33adb8c03dc3fcc91b55e28a073fb24_Traceguids
0x180028998  mov     edx, 13h
0x18002899d  mov     dword ptr [rsp+180h+ReferencedDomainName], ebx
0x1800289a1  mov     r9d, edi
0x1800289a4  call    WPP_SF_dd
0x1800289a9  mov     edx, ebx; int
0x1800289ab  lea     rcx, [rsp+180h+pExceptionObject]; this
0x1800289b0  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x1800289b5  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x1800289bc  lea     rcx, [rsp+180h+pExceptionObject]; pExceptionObject
0x1800289c1  call    _CxxThrowException_0
0x1800289c7  call    cs:__imp_GetLastError
0x1800289cd  mov     ebx, eax
0x1800289cf  test    eax, eax
0x1800289d1  jle     short loc_1800289DC
0x1800289d3  movzx   ebx, ax
0x1800289d6  or      ebx, 80070000h
0x1800289dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800289e3  lea     rax, WPP_GLOBAL_Control
0x1800289ea  cmp     rcx, rax
0x1800289ed  jz      short loc_180028A0D
0x1800289ef  test    byte ptr [rcx+1Ch], 1
0x1800289f3  jz      short loc_180028A0D
0x1800289f5  mov     rcx, [rcx+10h]
0x1800289f9  lea     r8, WPP_a33adb8c03dc3fcc91b55e28a073fb24_Traceguids
0x180028a00  mov     edx, 11h
0x180028a05  mov     r9d, ebx
0x180028a08  call    WPP_SF_d
0x180028a0d  mov     edx, ebx; int
0x180028a0f  lea     rcx, [rsp+180h+pExceptionObject]; this
0x180028a14  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x180028a19  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x180028a20  lea     rcx, [rsp+180h+pExceptionObject]; pExceptionObject
0x180028a25  call    _CxxThrowException_0
0x180028a2b  call    cs:__imp_GetLastError
0x180028a31  mov     ebx, eax
0x180028a33  test    eax, eax
0x180028a35  jle     short loc_180028A40
0x180028a37  movzx   ebx, ax
0x180028a3a  or      ebx, 80070000h
0x180028a40  mov     r10, cs:WPP_GLOBAL_Control
0x180028a47  lea     rax, WPP_GLOBAL_Control
0x180028a4e  cmp     r10, rax
0x180028a51  jz      short loc_180028A7F
0x180028a53  test    byte ptr [r10+1Ch], 1
0x180028a58  jz      short loc_180028A7F
0x180028a5a  lea     rcx, [rbp+80h+Buffer]
0x180028a5e  call    ?data@?$array@G$0BA@@std@@QEAAPEAGXZ; std::array<ushort,16>::data(void)
0x180028a63  mov     rcx, [r10+10h]
0x180028a67  lea     r8, WPP_a33adb8c03dc3fcc91b55e28a073fb24_Traceguids
0x180028a6e  mov     r9, rax
0x180028a71  mov     dword ptr [rsp+180h+ReferencedDomainName], ebx
0x180028a75  mov     edx, 12h
0x180028a7a  call    WPP_SF_Sd
0x180028a7f  mov     edx, ebx; int
0x180028a81  lea     rcx, [rsp+180h+pExceptionObject]; this
0x180028a86  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x180028a8b  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x180028a92  lea     rcx, [rsp+180h+pExceptionObject]; pExceptionObject
0x180028a97  call    _CxxThrowException_0
```
