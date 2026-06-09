# Windows::Networking::UX::Internal::WlanClient::CreateProfile(_GUID const &,HSTRING__ *,HSTRING__ *,uchar,uchar,uchar,Windows::Networking::UX::WiFiSecurityType,HSTRING__ *)

- ea: `0x180013c98`
- end: `0x180013fca`
- name: `?CreateProfile@WlanClient@Internal@UX@Networking@Windows@@QEAAJAEBU_GUID@@PEAUHSTRING__@@1EEEW4WiFiSecurityType@345@1@Z`
- size: `818`
- prototype: `int __high(const struct _GUID *, HSTRING, HSTRING, unsigned __int8, unsigned __int8, unsigned __int8, enum Windows::Networking::UX::WiFiSecurityType, HSTRING)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002354c`

## callees

- `0x180003ed0`
- `0x18000de4c`
- `0x180013c98`
- `0x18001d4d4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180013e33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180013eac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180013ebf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180013e33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180013eac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180013ebf`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x180013da5`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x180013da5`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanSetProfile` at `0x180013f7e`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanSetProfile` at `0x180013f7e`
- `wlanapi!WlanGenerateProfileXmlBasicSettingsWithTransitionMode` at `0x180013efc`
- `wlanapi!WlanGenerateProfileXmlBasicSettingsWithTransitionMode` at `0x180013efc`
- `wlanapi!WlanStringToUtf8Ssid` at `0x180013e40`
- `wlanapi!WlanStringToUtf8Ssid` at `0x180013e40`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::Internal::WlanClient::CreateProfile(
        __int64 a1,
        GUID *a2,
        HSTRING a3,
        HSTRING a4,
        char a5,
        char a6,
        char a7,
        int a8,
        HSTRING string)
{
  PVOID *v10; // r9
  int v11; // r12d
  signed int v12; // ebx
  unsigned int v14; // esi
  int v15; // edi
  PCWSTR StringRawBuffer; // rax
  int v17; // eax
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  PCWSTR v20; // rbx
  PCWSTR v21; // rax
  int v22; // eax
  __int64 v23; // r9
  signed int v24; // eax
  DWORD pdwReasonCode; // [rsp+60h] [rbp-61h] BYREF
  PVOID pMemory; // [rsp+68h] [rbp-59h] BYREF
  HSTRING v27; // [rsp+70h] [rbp-51h]
  GUID *pInterfaceGuid; // [rsp+78h] [rbp-49h]
  __int64 v29; // [rsp+80h] [rbp-41h]
  _OWORD v30[2]; // [rsp+88h] [rbp-39h] BYREF
  int v31; // [rsp+A8h] [rbp-19h]

  v27 = a3;
  pInterfaceGuid = a2;
  v29 = a1;
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, &WPP_21979ef79db039135e573b3136931b8d_Traceguids);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  v11 = 0;
  pMemory = 0;
  v31 = 0;
  memset(v30, 0, sizeof(v30));
  pdwReasonCode = 65537;
  switch ( a8 )
  {
    case 1:
      v15 = 0;
      goto LABEL_26;
    case 4:
      v14 = 7;
LABEL_19:
      v15 = 4;
      goto LABEL_27;
    case 9:
      v15 = 257;
LABEL_26:
      v14 = 1;
      goto LABEL_27;
  }
  if ( a8 != 11 )
  {
    switch ( a8 )
    {
      case 12:
        v14 = 9;
        break;
      case 13:
        v14 = 10;
        break;
      case 14:
        v14 = 11;
        break;
      default:
        v12 = -2147024809;
        if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 2) != 0 )
          WPP_SF_(v10[2], 78, &WPP_21979ef79db039135e573b3136931b8d_Traceguids);
        goto LABEL_14;
    }
    goto LABEL_19;
  }
  v14 = 8;
  v15 = 9;
LABEL_27:
  StringRawBuffer = WindowsGetStringRawBuffer(a4, 0);
  v17 = WlanStringToUtf8Ssid(StringRawBuffer, v30);
  v12 = v17;
  if ( v17 > 0 )
    v12 = (unsigned __int16)v17 | 0x80070000;
  if ( v12 < 0 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_14;
    v19 = 79;
LABEL_42:
    v23 = (unsigned int)v12;
LABEL_43:
    WPP_SF_d(v18[2], v19, &WPP_21979ef79db039135e573b3136931b8d_Traceguids, v23);
    goto LABEL_14;
  }
  if ( string )
    v20 = WindowsGetStringRawBuffer(string, 0);
  else
    v20 = 0;
  v21 = WindowsGetStringRawBuffer(v27, 0);
  LOBYTE(v11) = a5 != 0;
  v22 = WlanGenerateProfileXmlBasicSettingsWithTransitionMode(
          v21,
          v30,
          1,
          v14,
          v15,
          0,
          v20,
          v11,
          a6 != 0,
          a7 != 0,
          &pMemory);
  v12 = v22;
  if ( v22 > 0 )
    v12 = (unsigned __int16)v22 | 0x80070000;
  if ( v12 < 0 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_14;
    v19 = 80;
    goto LABEL_42;
  }
  v24 = WlanSetProfile(*(HANDLE *)(v29 + 16), pInterfaceGuid, 0, (LPCWSTR)pMemory, 0, 0, 0, &pdwReasonCode);
  v12 = v24;
  if ( v24 > 0 )
    v12 = (unsigned __int16)v24 | 0x80070000;
  if ( v12 < 0 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v23 = pdwReasonCode;
      v19 = 81;
      goto LABEL_43;
    }
  }
LABEL_14:
  WlanFreeMemory(pMemory);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      82,
      &WPP_21979ef79db039135e573b3136931b8d_Traceguids,
      (unsigned int)v12);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180013c98  push    rbp
0x180013c9a  push    rbx
0x180013c9b  push    rsi
0x180013c9c  push    rdi
0x180013c9d  push    r12
0x180013c9f  push    r13
0x180013ca1  push    r14
0x180013ca3  push    r15
0x180013ca5  lea     rbp, [rsp-7]
0x180013caa  sub     rsp, 0C8h
0x180013cb1  mov     rax, cs:__security_cookie
0x180013cb8  xor     rax, rsp
0x180013cbb  mov     [rbp+3Fh+var_50], rax
0x180013cbf  mov     r13, [rbp+3Fh+string]
0x180013cc6  mov     rbx, r9
0x180013cc9  mov     [rbp+3Fh+var_90], r8
0x180013ccd  mov     [rbp+3Fh+pInterfaceGuid], rdx
0x180013cd1  mov     [rbp+3Fh+var_80], rcx
0x180013cd5  mov     r9, cs:WPP_GLOBAL_Control
0x180013cdc  lea     rdx, WPP_GLOBAL_Control
0x180013ce3  cmp     r9, rdx
0x180013ce6  jz      short loc_180013D12
0x180013ce8  test    byte ptr [r9+1Ch], 8
0x180013ced  jz      short loc_180013D12
0x180013cef  mov     rcx, [r9+10h]
0x180013cf3  lea     r8, WPP_21979ef79db039135e573b3136931b8d_Traceguids
0x180013cfa  mov     edx, 4Dh ; 'M'
0x180013cff  call    WPP_SF_
0x180013d04  mov     r9, cs:WPP_GLOBAL_Control
0x180013d0b  lea     rdx, WPP_GLOBAL_Control
0x180013d12  mov     ecx, [rbp+3Fh+arg_38]
0x180013d18  xor     r12d, r12d
0x180013d1b  xor     eax, eax
0x180013d1d  mov     [rbp+3Fh+pMemory], r12
0x180013d21  xorps   xmm0, xmm0
0x180013d24  mov     [rbp+3Fh+var_58], eax
0x180013d27  movups  [rbp+3Fh+var_78], xmm0
0x180013d2b  lea     eax, [r12+1]
0x180013d30  mov     [rbp+3Fh+var_A0], 10001h
0x180013d37  movups  [rbp+3Fh+var_68], xmm0
0x180013d3b  sub     ecx, eax
0x180013d3d  jz      loc_180013E29
0x180013d43  sub     ecx, 3
0x180013d46  jz      loc_180013E22
0x180013d4c  sub     ecx, 5
0x180013d4f  jz      loc_180013E1B
0x180013d55  sub     ecx, 2
0x180013d58  jz      loc_180013E11
0x180013d5e  sub     ecx, eax
0x180013d60  jz      loc_180013E0A
0x180013d66  sub     ecx, eax
0x180013d68  jz      loc_180013E03
0x180013d6e  cmp     ecx, eax
0x180013d70  jz      loc_180013DF7
0x180013d76  mov     ebx, 80070057h
0x180013d7b  cmp     r9, rdx
0x180013d7e  jz      short loc_180013D9A
0x180013d80  test    byte ptr [r9+1Ch], 2
0x180013d85  jz      short loc_180013D9A
0x180013d87  mov     rcx, [r9+10h]
0x180013d8b  lea     edx, [rax+4Dh]
0x180013d8e  lea     r8, WPP_21979ef79db039135e573b3136931b8d_Traceguids
0x180013d95  call    WPP_SF_
0x180013d9a  lea     rdi, WPP_GLOBAL_Control
0x180013da1  mov     rcx, [rbp+3Fh+pMemory]; pMemory
0x180013da5  call    cs:__imp_WlanFreeMemory
0x180013dab  mov     rcx, cs:WPP_GLOBAL_Control
0x180013db2  cmp     rcx, rdi
0x180013db5  jz      short loc_180013DD5
0x180013db7  test    byte ptr [rcx+1Ch], 8
0x180013dbb  jz      short loc_180013DD5
0x180013dbd  mov     rcx, [rcx+10h]
0x180013dc1  lea     r8, WPP_21979ef79db039135e573b3136931b8d_Traceguids
0x180013dc8  mov     edx, 52h ; 'R'
0x180013dcd  mov     r9d, ebx
0x180013dd0  call    WPP_SF_d
0x180013dd5  mov     eax, ebx
0x180013dd7  mov     rcx, [rbp+3Fh+var_50]
0x180013ddb  xor     rcx, rsp; StackCookie
0x180013dde  call    __security_check_cookie
0x180013de3  add     rsp, 0C8h
0x180013dea  pop     r15
0x180013dec  pop     r14
0x180013dee  pop     r13
0x180013df0  pop     r12
0x180013df2  pop     rdi
0x180013df3  pop     rsi
0x180013df4  pop     rbx
0x180013df5  pop     rbp
0x180013df6  retn
0x180013df7  mov     esi, 0Bh
0x180013dfc  mov     edi, 4
0x180013e01  jmp     short loc_180013E2E
0x180013e03  mov     esi, 0Ah
0x180013e08  jmp     short loc_180013DFC
0x180013e0a  mov     esi, 9
0x180013e0f  jmp     short loc_180013DFC
0x180013e11  mov     esi, 8
0x180013e16  lea     edi, [rsi+1]
0x180013e19  jmp     short loc_180013E2E
0x180013e1b  mov     edi, 101h
0x180013e20  jmp     short loc_180013E2C
0x180013e22  mov     esi, 7
0x180013e27  jmp     short loc_180013DFC
0x180013e29  mov     edi, r12d
0x180013e2c  mov     esi, eax
0x180013e2e  xor     edx, edx; length
0x180013e30  mov     rcx, rbx; string
0x180013e33  call    cs:__imp_WindowsGetStringRawBuffer
0x180013e39  mov     rcx, rax
0x180013e3c  lea     rdx, [rbp+3Fh+var_78]
0x180013e40  call    cs:__imp_WlanStringToUtf8Ssid
0x180013e46  mov     ebx, eax
0x180013e48  test    eax, eax
0x180013e4a  jle     short loc_180013E55
0x180013e4c  movzx   ebx, ax
0x180013e4f  or      ebx, 80070000h
0x180013e55  test    ebx, ebx
0x180013e57  jns     short loc_180013E84
0x180013e59  mov     rcx, cs:WPP_GLOBAL_Control
0x180013e60  lea     rdi, WPP_GLOBAL_Control
0x180013e67  cmp     rcx, rdi
0x180013e6a  jz      loc_180013DA1
0x180013e70  test    byte ptr [rcx+1Ch], 2
0x180013e74  jz      loc_180013DA1
0x180013e7a  mov     edx, 4Fh ; 'O'
0x180013e7f  jmp     loc_180013F3B
0x180013e84  cmp     [rbp+3Fh+arg_30], r12b
0x180013e88  mov     r14d, r12d
0x180013e8b  mov     r15d, r12d
0x180013e8e  setnz   r14b
0x180013e92  cmp     [rbp+3Fh+arg_28], r12b
0x180013e96  setnz   r15b
0x180013e9a  cmp     [rbp+3Fh+arg_20], r12b
0x180013e9e  setnz   r12b
0x180013ea2  test    r13, r13
0x180013ea5  jz      short loc_180013EB7
0x180013ea7  xor     edx, edx; length
0x180013ea9  mov     rcx, r13; string
0x180013eac  call    cs:__imp_WindowsGetStringRawBuffer
0x180013eb2  mov     rbx, rax
0x180013eb5  jmp     short loc_180013EB9
0x180013eb7  xor     ebx, ebx
0x180013eb9  mov     rcx, [rbp+3Fh+var_90]; string
0x180013ebd  xor     edx, edx; length
0x180013ebf  call    cs:__imp_WindowsGetStringRawBuffer
0x180013ec5  mov     r9d, esi
0x180013ec8  lea     rdx, [rbp+3Fh+var_78]
0x180013ecc  mov     rcx, rax
0x180013ecf  lea     rax, [rbp+3Fh+pMemory]
0x180013ed3  mov     [rsp+100h+var_B0], rax
0x180013ed8  mov     [rsp+100h+var_B8], r14d
0x180013edd  xor     r14d, r14d
0x180013ee0  mov     [rsp+100h+var_C0], r15d
0x180013ee5  mov     dword ptr [rsp+100h+pdwReasonCode], r12d
0x180013eea  mov     [rsp+100h+pReserved], rbx
0x180013eef  lea     r8d, [r14+1]
0x180013ef3  mov     [rsp+100h+bOverwrite], r14d
0x180013ef8  mov     dword ptr [rsp+100h+strAllUserProfileSecurity], edi
0x180013efc  call    cs:__imp_WlanGenerateProfileXmlBasicSettingsWithTransitionMode
0x180013f02  mov     ebx, eax
0x180013f04  test    eax, eax
0x180013f06  jle     short loc_180013F11
0x180013f08  movzx   ebx, ax
0x180013f0b  or      ebx, 80070000h
0x180013f11  test    ebx, ebx
0x180013f13  jns     short loc_180013F53
0x180013f15  mov     rcx, cs:WPP_GLOBAL_Control
0x180013f1c  lea     rdi, WPP_GLOBAL_Control
0x180013f23  cmp     rcx, rdi
0x180013f26  jz      loc_180013DA1
0x180013f2c  test    byte ptr [rcx+1Ch], 2
0x180013f30  jz      loc_180013DA1
0x180013f36  mov     edx, 50h ; 'P'
0x180013f3b  mov     r9d, ebx
0x180013f3e  mov     rcx, [rcx+10h]
0x180013f42  lea     r8, WPP_21979ef79db039135e573b3136931b8d_Traceguids
0x180013f49  call    WPP_SF_d
0x180013f4e  jmp     loc_180013DA1
0x180013f53  mov     rcx, [rbp+3Fh+var_80]
0x180013f57  lea     rax, [rbp+3Fh+var_A0]
0x180013f5b  mov     r9, [rbp+3Fh+pMemory]; strProfileXml
0x180013f5f  xor     r8d, r8d; dwFlags
0x180013f62  mov     rdx, [rbp+3Fh+pInterfaceGuid]; pInterfaceGuid
0x180013f66  mov     [rsp+100h+pdwReasonCode], rax; pdwReasonCode
0x180013f6b  mov     rcx, [rcx+10h]; hClientHandle
0x180013f6f  mov     [rsp+100h+pReserved], r14; pReserved
0x180013f74  mov     [rsp+100h+bOverwrite], r14d; bOverwrite
0x180013f79  mov     [rsp+100h+strAllUserProfileSecurity], r14; strAllUserProfileSecurity
0x180013f7e  call    cs:__imp_WlanSetProfile
0x180013f84  mov     ebx, eax
0x180013f86  test    eax, eax
0x180013f88  jle     short loc_180013F93
0x180013f8a  movzx   ebx, ax
0x180013f8d  or      ebx, 80070000h
0x180013f93  test    ebx, ebx
0x180013f95  jns     loc_180013D9A
0x180013f9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180013fa2  lea     rdi, WPP_GLOBAL_Control
0x180013fa9  cmp     rcx, rdi
0x180013fac  jz      loc_180013DA1
0x180013fb2  test    byte ptr [rcx+1Ch], 2
0x180013fb6  jz      loc_180013DA1
0x180013fbc  mov     r9d, [rbp+3Fh+var_A0]
0x180013fc0  mov     edx, 51h ; 'Q'
0x180013fc5  jmp     loc_180013F3E
```
