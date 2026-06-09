# Sid::FromWellKnownSid(WELL_KNOWN_SID_TYPE)

- ea: `0x180062ac8`
- end: `0x180062d21`
- name: `?FromWellKnownSid@Sid@@SA?AV1@W4WELL_KNOWN_SID_TYPE@@@Z`
- size: `601`
- prototype: `static struct Sid __high(enum WELL_KNOWN_SID_TYPE)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002567c`
- `0x18002aae4`

## callees

- `0x1800060a0`
- `0x180006ed4`
- `0x180006ee0`
- `0x18000ecc0`
- `0x180035af4`
- `0x180035e0c`
- `0x180046660`
- `0x180059820`
- `0x1800625fc`
- `0x180062ac8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062be3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062c4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062caf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062be3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062c4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062caf`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180062bab`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180062bab`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180062b23`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180062b23`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180062b7c`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180062b7c`

## pseudocode

```c
void **__fastcall Sid::FromWellKnownSid(void **a1, WELL_KNOWN_SID_TYPE a2)
{
  signed int v5; // eax
  unsigned int v6; // ebx
  signed int LastError; // eax
  unsigned int v8; // ebx
  signed int v9; // eax
  unsigned int v10; // ebx
  int v11; // eax
  __int64 v12; // r10
  DWORD nSize; // [rsp+40h] [rbp-C0h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cchReferencedDomainName; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cbSid; // [rsp+4Ch] [rbp-B4h] BYREF
  DWORD v17[6]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Buffer[8]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v20; // [rsp+A0h] [rbp-60h]
  WCHAR ReferencedDomainName[8]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v22; // [rsp+C0h] [rbp-40h]
  _BYTE Sid[80]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE pSid[80]; // [rsp+120h] [rbp+20h] BYREF

  *(_QWORD *)v17 = a1;
  memset_0(Sid, 0, 0x44u);
  nSize = 16;
  *(_OWORD *)Buffer = 0;
  v20 = 0;
  if ( !GetComputerNameW(Buffer, &nSize) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_a33adb8c03dc3fcc91b55e28a073fb24_Traceguids, v8);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v8);
    throw (ErrorCodeException *)pExceptionObject;
  }
  cchReferencedDomainName = 16;
  cbSid = 68;
  peUse = 0;
  *(_OWORD *)ReferencedDomainName = 0;
  v22 = 0;
  if ( !LookupAccountNameW(0, Buffer, Sid, &cbSid, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
  {
    v9 = GetLastError();
    v10 = v9;
    if ( v9 > 0 )
      v10 = (unsigned __int16)v9 | 0x80070000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v11 = std::array<unsigned short,16>::data(Buffer);
      WPP_SF_Sd(*(_QWORD *)(v12 + 16), 18, (int)WPP_a33adb8c03dc3fcc91b55e28a073fb24_Traceguids, v11, v10);
    }
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v10);
    throw (ErrorCodeException *)pExceptionObject;
  }
  memset_0(pSid, 0, 0x44u);
  v17[0] = 68;
  if ( !CreateWellKnownSid(a2, Sid, pSid, v17) )
  {
    v5 = GetLastError();
    v6 = v5;
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        WPP_a33adb8c03dc3fcc91b55e28a073fb24_Traceguids,
        (unsigned int)a2,
        v6);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v6);
    throw (ErrorCodeException *)pExceptionObject;
  }
  Sid::FromPSID(a1, pSid);
  return a1;
}

```

## disassembly

```asm
0x180062ac8  mov     [rsp-8+arg_10], rbx
0x180062acd  push    rbp
0x180062ace  push    rsi
0x180062acf  push    rdi
0x180062ad0  lea     rbp, [rsp-80h]
0x180062ad5  sub     rsp, 180h
0x180062adc  mov     rax, cs:__security_cookie
0x180062ae3  xor     rax, rsp
0x180062ae6  mov     [rbp+90h+var_20], rax
0x180062aea  mov     edi, edx
0x180062aec  mov     qword ptr [rsp+190h+var_140], rcx
0x180062af1  mov     rbx, rcx
0x180062af4  mov     esi, 44h ; 'D'
0x180062af9  mov     r8d, esi; Size
0x180062afc  lea     rcx, [rbp+90h+Sid]; void *
0x180062b00  xor     edx, edx; Val
0x180062b02  call    memset_0
0x180062b07  xorps   xmm0, xmm0
0x180062b0a  mov     [rsp+190h+nSize], 10h
0x180062b12  lea     rdx, [rsp+190h+nSize]; nSize
0x180062b17  lea     rcx, [rbp+90h+Buffer]; lpBuffer
0x180062b1b  movups  xmmword ptr [rbp+90h+Buffer], xmm0
0x180062b1f  movups  [rbp+90h+var_F0], xmm0
0x180062b23  call    cs:__imp_GetComputerNameW
0x180062b29  test    eax, eax
0x180062b2b  jz      loc_180062C4B
0x180062b31  xorps   xmm0, xmm0
0x180062b34  mov     [rsp+190h+var_148], 10h
0x180062b3c  lea     rax, [rsp+190h+var_14C]
0x180062b41  mov     [rsp+190h+cbSid], esi
0x180062b45  mov     [rsp+190h+peUse], rax; peUse
0x180062b4a  lea     r9, [rsp+190h+cbSid]; cbSid
0x180062b4f  lea     rax, [rsp+190h+var_148]
0x180062b54  mov     [rsp+190h+var_14C], 0
0x180062b5c  mov     [rsp+190h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180062b61  lea     r8, [rbp+90h+Sid]; Sid
0x180062b65  lea     rax, [rbp+90h+var_E0]
0x180062b69  xor     ecx, ecx; lpSystemName
0x180062b6b  lea     rdx, [rbp+90h+Buffer]; lpAccountName
0x180062b6f  mov     [rsp+190h+ReferencedDomainName], rax; ReferencedDomainName
0x180062b74  movups  xmmword ptr [rbp+90h+var_E0], xmm0
0x180062b78  movups  [rbp+90h+var_D0], xmm0
0x180062b7c  call    cs:__imp_LookupAccountNameW
0x180062b82  test    eax, eax
0x180062b84  jz      loc_180062CAF
0x180062b8a  mov     r8d, esi; Size
0x180062b8d  lea     rcx, [rbp+90h+pSid]; void *
0x180062b91  xor     edx, edx; Val
0x180062b93  call    memset_0
0x180062b98  lea     r9, [rsp+190h+var_140]; cbSid
0x180062b9d  mov     [rsp+190h+var_140], esi
0x180062ba1  lea     r8, [rbp+90h+pSid]; pSid
0x180062ba5  mov     ecx, edi; WellKnownSidType
0x180062ba7  lea     rdx, [rbp+90h+Sid]; DomainSid
0x180062bab  call    cs:__imp_CreateWellKnownSid
0x180062bb1  test    eax, eax
0x180062bb3  jz      short loc_180062BE3
0x180062bb5  lea     rdx, [rbp+90h+pSid]
0x180062bb9  mov     rcx, rbx
0x180062bbc  call    ?FromPSID@Sid@@SA?AV1@PEAX@Z; Sid::FromPSID(void *)
0x180062bc1  mov     rax, rbx
0x180062bc4  mov     rcx, [rbp+90h+var_20]
0x180062bc8  xor     rcx, rsp; StackCookie
0x180062bcb  call    __security_check_cookie
0x180062bd0  mov     rbx, [rsp+190h+arg_10]
0x180062bd8  add     rsp, 180h
0x180062bdf  pop     rdi
0x180062be0  pop     rsi
0x180062be1  pop     rbp
0x180062be2  retn
0x180062be3  call    cs:__imp_GetLastError
0x180062be9  mov     ebx, eax
0x180062beb  test    eax, eax
0x180062bed  jle     short loc_180062BF8
0x180062bef  movzx   ebx, ax
0x180062bf2  or      ebx, 80070000h
0x180062bf8  mov     rcx, cs:WPP_GLOBAL_Control
0x180062bff  lea     rax, WPP_GLOBAL_Control
0x180062c06  cmp     rcx, rax
0x180062c09  jz      short loc_180062C2D
0x180062c0b  test    byte ptr [rcx+1Ch], 1
0x180062c0f  jz      short loc_180062C2D
0x180062c11  mov     rcx, [rcx+10h]
0x180062c15  lea     r8, WPP_a33adb8c03dc3fcc91b55e28a073fb24_Traceguids
0x180062c1c  mov     edx, 13h
0x180062c21  mov     dword ptr [rsp+190h+ReferencedDomainName], ebx
0x180062c25  mov     r9d, edi
0x180062c28  call    WPP_SF_dd
0x180062c2d  mov     edx, ebx; int
0x180062c2f  lea     rcx, [rsp+190h+pExceptionObject]; this
0x180062c34  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x180062c39  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x180062c40  lea     rcx, [rsp+190h+pExceptionObject]; pExceptionObject
0x180062c45  call    _CxxThrowException_0
0x180062c4b  call    cs:__imp_GetLastError
0x180062c51  mov     ebx, eax
0x180062c53  test    eax, eax
0x180062c55  jle     short loc_180062C60
0x180062c57  movzx   ebx, ax
0x180062c5a  or      ebx, 80070000h
0x180062c60  mov     rcx, cs:WPP_GLOBAL_Control
0x180062c67  lea     rax, WPP_GLOBAL_Control
0x180062c6e  cmp     rcx, rax
0x180062c71  jz      short loc_180062C91
0x180062c73  test    byte ptr [rcx+1Ch], 1
0x180062c77  jz      short loc_180062C91
0x180062c79  mov     rcx, [rcx+10h]
0x180062c7d  lea     r8, WPP_a33adb8c03dc3fcc91b55e28a073fb24_Traceguids
0x180062c84  mov     edx, 11h
0x180062c89  mov     r9d, ebx
0x180062c8c  call    WPP_SF_d
0x180062c91  mov     edx, ebx; int
0x180062c93  lea     rcx, [rsp+190h+pExceptionObject]; this
0x180062c98  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x180062c9d  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x180062ca4  lea     rcx, [rsp+190h+pExceptionObject]; pExceptionObject
0x180062ca9  call    _CxxThrowException_0
0x180062caf  call    cs:__imp_GetLastError
0x180062cb5  mov     ebx, eax
0x180062cb7  test    eax, eax
0x180062cb9  jle     short loc_180062CC4
0x180062cbb  movzx   ebx, ax
0x180062cbe  or      ebx, 80070000h
0x180062cc4  mov     r10, cs:WPP_GLOBAL_Control
0x180062ccb  lea     rax, WPP_GLOBAL_Control
0x180062cd2  cmp     r10, rax
0x180062cd5  jz      short loc_180062D03
0x180062cd7  test    byte ptr [r10+1Ch], 1
0x180062cdc  jz      short loc_180062D03
0x180062cde  lea     rcx, [rbp+90h+Buffer]
0x180062ce2  call    ?data@?$array@G$0BA@@std@@QEAAPEAGXZ; std::array<ushort,16>::data(void)
0x180062ce7  mov     rcx, [r10+10h]
0x180062ceb  lea     r8, WPP_a33adb8c03dc3fcc91b55e28a073fb24_Traceguids
0x180062cf2  mov     r9, rax
0x180062cf5  mov     dword ptr [rsp+190h+ReferencedDomainName], ebx
0x180062cf9  mov     edx, 12h
0x180062cfe  call    WPP_SF_Sd
0x180062d03  mov     edx, ebx; int
0x180062d05  lea     rcx, [rsp+190h+pExceptionObject]; this
0x180062d0a  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x180062d0f  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x180062d16  lea     rcx, [rsp+190h+pExceptionObject]; pExceptionObject
0x180062d1b  call    _CxxThrowException_0
```
