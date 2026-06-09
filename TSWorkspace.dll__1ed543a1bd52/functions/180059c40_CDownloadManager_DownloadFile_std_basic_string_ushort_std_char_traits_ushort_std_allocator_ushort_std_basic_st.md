# CDownloadManager::DownloadFile(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180059c40`
- end: `0x18005a27d`
- name: `?DownloadFile@CDownloadManager@@UEAAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `1597`
- prototype: `int __fastcall(HINTERNET *this, _BYTE *, _BYTE *)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800034b8`
- `0x18000b1d8`
- `0x18000d8d4`
- `0x18000ec94`
- `0x18000ece0`
- `0x180010ba4`
- `0x18001e5d8`
- `0x18001e974`
- `0x18003ce1c`
- `0x180058c2c`
- `0x18005913c`
- `0x180059c40`
- `0x18005d018`
- `0x18005e174`
- `0x180078020`
- `0x18009a520`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059edd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059ffe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a0e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059edd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059ffe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a0e7`
- `WINHTTP!WinHttpSetOption` at `0x180059ff4`
- `WINHTTP!WinHttpSetOption` at `0x18005a0dd`
- `WINHTTP!WinHttpSetOption` at `0x180059ff4`
- `WINHTTP!WinHttpSetOption` at `0x18005a0dd`
- `WINHTTP!WinHttpOpenRequest` at `0x180059ece`
- `WINHTTP!WinHttpOpenRequest` at `0x180059ece`

## string_xrefs

- `0x180059c91`: `application/xml`
- `0x180059cbd`: `application/x-msts-radc+xml;radc_schema_version=2.0`
- `0x180059cc8`: `application/x-msts-radc-discovery+xml`
- `0x180059db6`: `GetRelativeURLPath Failed`

## pseudocode

```c
int __fastcall CDownloadManager::DownloadFile(HINTERNET *this, _BYTE *a2, _BYTE *a3)
{
  _BYTE *v3; // rdi
  __int64 v6; // rdi
  __int64 v7; // rbx
  void *v8; // rax
  int RelativeURLPath; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  _DM_CONTEXT *v11; // rax
  HINTERNET *v12; // r15
  unsigned int v13; // eax
  _BYTE *v14; // rdx
  DWORD dwFlags; // ebx
  const WCHAR *v16; // rax
  HINTERNET v17; // rax
  signed int LastError; // edi
  unsigned int v19; // eax
  int result; // eax
  unsigned int v21; // eax
  unsigned int v22; // eax
  int v23; // ecx
  int v24; // eax
  unsigned int v25; // eax
  unsigned int v26; // eax
  __int64 v27; // rbx
  LPCWSTR *ppwszAcceptTypes; // [rsp+28h] [rbp-110h]
  LPCWSTR *ppwszAcceptTypesa; // [rsp+28h] [rbp-110h]
  _DM_CONTEXT *Buffer; // [rsp+50h] [rbp-E8h] BYREF
  int v32; // [rsp+58h] [rbp-E0h]
  _BYTE *v33; // [rsp+60h] [rbp-D8h]
  _BYTE *v34; // [rsp+68h] [rbp-D0h]
  CDownloadManager *v35; // [rsp+70h] [rbp-C8h]
  HINTERNET *v36; // [rsp+78h] [rbp-C0h]
  __int64 v37; // [rsp+80h] [rbp-B8h]
  _BYTE v38[32]; // [rsp+88h] [rbp-B0h] BYREF
  _BYTE v39[32]; // [rsp+A8h] [rbp-90h] BYREF
  LPCWSTR v40[8]; // [rsp+C8h] [rbp-70h] BYREF

  v37 = -2;
  v3 = a3;
  v35 = (CDownloadManager *)this;
  v33 = a2;
  v34 = a3;
  v40[0] = L"application/xml";
  v40[1] = L"Image/*";
  v40[2] = L"Application/*";
  v40[3] = L"text/*";
  v40[4] = L"application/x-msts-radc+xml;radc_schema_version=2.0";
  v40[5] = L"application/x-msts-radc-discovery+xml";
  v40[6] = 0;
  v36 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v6 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3);
    v7 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
    RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DSS(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, v6);
    v3 = a3;
  }
  if ( *((_DWORD *)this + 505) )
  {
    Buffer = (_DM_CONTEXT *)v38;
    v8 = (void *)std::wstring::wstring(v38, a2);
    RelativeURLPath = GetRelativeURLPath(v8);
    if ( RelativeURLPath < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      LODWORD(ppwszAcceptTypes) = RelativeURLPath;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        26,
        (unsigned int)&WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)"GetRelativeURLPath Failed",
        ppwszAcceptTypes);
    }
  }
  v11 = (_DM_CONTEXT *)operator new(0xE8u, (const struct std::nothrow_t *)&std::nothrow);
  Buffer = v11;
  if ( v11 )
    v12 = (HINTERNET *)_DM_CONTEXT::_DM_CONTEXT(v11);
  else
    v12 = 0;
  v36 = v12;
  if ( !v12 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        27,
        (unsigned int)&WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids,
        v13,
        (__int64)"DM_CONTEXT");
    }
    v14 = a3;
LABEL_73:
    v34 = v38;
    v27 = std::wstring::wstring(v38, v14);
    v33 = v39;
    std::wstring::wstring(v39, a2);
    return CDownloadManager::ReportDownloadStatus((CDownloadManager *)this, v27);
  }
  this[258] = v12;
  v32 = 256;
  dwFlags = 256;
  if ( *((_DWORD *)this + 59) == 2 )
    dwFlags = 8388864;
  v32 = dwFlags;
  v16 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
  v17 = WinHttpOpenRequest(this[49], 0, v16, 0, 0, v40, dwFlags);
  v12[5] = v17;
  if ( v17 )
  {
    std::wstring::operator=(v12 + 6, a2);
    std::wstring::operator=(v12 + 10, v3);
    LastError = CDownloadManager::SetAuthInfo((CDownloadManager *)this, (struct _DM_CONTEXT *)v12);
    if ( LastError >= 0 )
    {
      if ( WinHttpSetOption(v12[5], 0x26u, this + 50, 0x18u) )
      {
        if ( *((_DWORD *)this + 514) != -2147012721 )
          goto LABEL_66;
        LODWORD(Buffer) = 0;
        v23 = *((_DWORD *)this + 515);
        v24 = 0;
        if ( (v23 & 0x10) != 0 )
        {
          v24 = 4096;
          LODWORD(Buffer) = 4096;
        }
        if ( (v23 & 0x20) != 0 )
        {
          v24 |= 0x2000u;
          LODWORD(Buffer) = v24;
        }
        if ( (v23 & 8) != 0 )
        {
          v24 |= 0x100u;
          LODWORD(Buffer) = v24;
        }
        if ( v24 && !WinHttpSetOption(v12[5], 0x1Fu, &Buffer, 4u) )
        {
          LastError = GetLastError();
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v25 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              31,
              &WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids,
              v25,
              LastError);
          }
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          result = -2147467259;
          if ( LastError >= 0 )
            LastError = -2147467259;
          v14 = a3;
        }
        else
        {
LABEL_66:
          result = CDownloadManager::CallSendRequest((CDownloadManager *)this, (struct _DM_CONTEXT *)v12);
          LastError = result;
          if ( result >= 0 )
            return result;
          result = (int)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v26 = RdpWppGetCurrentThreadActivityIdPrefix();
            LODWORD(ppwszAcceptTypesa) = LastError;
            result = WPP_SF_DsD(
                       *((_QWORD *)WPP_GLOBAL_Control + 2),
                       32,
                       (unsigned int)&WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids,
                       v26,
                       (__int64)"CallSendRequest failed",
                       ppwszAcceptTypesa);
          }
          v14 = a3;
        }
      }
      else
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v22 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            30,
            &WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids,
            v22,
            LastError);
        }
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        result = -2147467259;
        if ( LastError >= 0 )
          LastError = -2147467259;
        v14 = a3;
      }
    }
    else
    {
      result = (int)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v21 = RdpWppGetCurrentThreadActivityIdPrefix();
        LODWORD(ppwszAcceptTypesa) = LastError;
        result = WPP_SF_DsD(
                   *((_QWORD *)WPP_GLOBAL_Control + 2),
                   29,
                   (unsigned int)&WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids,
                   v21,
                   (__int64)"SetAuthInfo failed",
                   ppwszAcceptTypesa);
      }
      v14 = a3;
    }
  }
  else
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v19 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        28,
        &WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids,
        v19,
        LastError);
    }
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    result = -2147467259;
    if ( LastError >= 0 )
      LastError = -2147467259;
    v14 = a3;
  }
  if ( LastError < 0 )
    goto LABEL_73;
  return result;
}

```

## disassembly

```asm
0x180059c40  mov     r11, rsp
0x180059c43  push    rdi
0x180059c44  push    r12
0x180059c46  push    r13
0x180059c48  push    r14
0x180059c4a  push    r15
0x180059c4c  sub     rsp, 110h
0x180059c53  mov     qword ptr [r11-0B8h], 0FFFFFFFFFFFFFFFEh
0x180059c5e  mov     [r11+20h], rbx
0x180059c62  mov     rax, cs:__security_cookie
0x180059c69  xor     rax, rsp
0x180059c6c  mov     [rsp+138h+var_30], rax
0x180059c74  mov     rdi, r8
0x180059c77  mov     [rsp+138h+var_F0], r8
0x180059c7c  mov     r12, rdx
0x180059c7f  mov     r13, rcx
0x180059c82  mov     [rsp+138h+var_C8], rcx
0x180059c87  mov     [rsp+138h+var_D8], rdx
0x180059c8c  mov     [rsp+138h+var_D0], r8
0x180059c91  lea     rax, aApplicationXml; "application/xml"
0x180059c98  mov     [r11-70h], rax
0x180059c9c  lea     rax, aImage; "Image/*"
0x180059ca3  mov     [r11-68h], rax
0x180059ca7  lea     rax, aApplication; "Application/*"
0x180059cae  mov     [r11-60h], rax
0x180059cb2  lea     rax, aText; "text/*"
0x180059cb9  mov     [r11-58h], rax
0x180059cbd  lea     rax, aApplicationXMs; "application/x-msts-radc+xml;radc_schema"...
0x180059cc4  mov     [r11-50h], rax
0x180059cc8  lea     rax, aApplicationXMs_0; "application/x-msts-radc-discovery+xml"
0x180059ccf  mov     [r11-48h], rax
0x180059cd3  mov     qword ptr [r11-40h], 0
0x180059cdb  mov     [rsp+138h+var_C0], 0
0x180059ce4  lea     r14, WPP_GLOBAL_Control
0x180059ceb  mov     rax, cs:WPP_GLOBAL_Control
0x180059cf2  cmp     rax, r14
0x180059cf5  jz      short loc_180059D4C
0x180059cf7  test    byte ptr [rax+1Ch], 1
0x180059cfb  jz      short loc_180059D4C
0x180059cfd  cmp     byte ptr [rax+19h], 4
0x180059d01  jb      short loc_180059D4C
0x180059d03  mov     rcx, r8
0x180059d06  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180059d0b  mov     rdi, rax
0x180059d0e  mov     rcx, r12
0x180059d11  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180059d16  mov     rbx, rax
0x180059d19  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180059d1e  mov     edx, 19h
0x180059d23  mov     [rsp+138h+ppwszAcceptTypes], rdi; __int64
0x180059d28  mov     [rsp+138h+pwszReferrer], rbx; __int64
0x180059d2d  mov     r9d, eax
0x180059d30  lea     r8, WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids
0x180059d37  mov     rcx, cs:WPP_GLOBAL_Control
0x180059d3e  mov     rcx, [rcx+10h]; LoggerHandle
0x180059d42  call    WPP_SF_DSS
0x180059d47  mov     rdi, [rsp+138h+var_F0]
0x180059d4c  cmp     dword ptr [r13+7E4h], 0
0x180059d54  jz      loc_180059DDE
0x180059d5a  lea     rax, [rsp+138h+var_B0]
0x180059d62  mov     [rsp+138h+Buffer], rax
0x180059d67  mov     rdx, r12
0x180059d6a  lea     rcx, [rsp+138h+var_B0]
0x180059d72  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180059d77  nop
0x180059d78  mov     rdx, r12
0x180059d7b  mov     rcx, rax
0x180059d7e  call    ?GetRelativeURLPath@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV12@@Z; GetRelativeURLPath(std::wstring,std::wstring &)
0x180059d83  mov     ebx, eax
0x180059d85  mov     [rsp+138h+var_F8], eax
0x180059d89  test    eax, eax
0x180059d8b  jns     short loc_180059DDE
0x180059d8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180059d94  cmp     rcx, r14
0x180059d97  jz      short loc_180059DDE
0x180059d99  mov     r14b, 8
0x180059d9c  test    [rcx+1Ch], r14b
0x180059da0  jz      short loc_180059DE1
0x180059da2  cmp     byte ptr [rcx+19h], 2
0x180059da6  jb      short loc_180059DE1
0x180059da8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180059dad  mov     edx, 1Ah
0x180059db2  mov     dword ptr [rsp+138h+ppwszAcceptTypes], ebx
0x180059db6  lea     rcx, aGetrelativeurl; "GetRelativeURLPath Failed"
0x180059dbd  mov     [rsp+138h+pwszReferrer], rcx
0x180059dc2  mov     r9d, eax
0x180059dc5  lea     r8, WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids
0x180059dcc  mov     rcx, cs:WPP_GLOBAL_Control
0x180059dd3  mov     rcx, [rcx+10h]
0x180059dd7  call    WPP_SF_DsD
0x180059ddc  jmp     short loc_180059DE1
0x180059dde  mov     r14b, 8
0x180059de1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180059de8  mov     ecx, 0E8h; unsigned __int64
0x180059ded  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180059df2  mov     [rsp+138h+Buffer], rax
0x180059df7  test    rax, rax
0x180059dfa  jz      short loc_180059E09
0x180059dfc  mov     rcx, rax; this
0x180059dff  call    ??0_DM_CONTEXT@@QEAA@XZ; _DM_CONTEXT::_DM_CONTEXT(void)
0x180059e04  mov     r15, rax
0x180059e07  jmp     short loc_180059E0C
0x180059e09  xor     r15d, r15d
0x180059e0c  mov     [rsp+138h+var_C0], r15
0x180059e11  test    r15, r15
0x180059e14  jnz     short loc_180059E77
0x180059e16  mov     rax, cs:WPP_GLOBAL_Control
0x180059e1d  lea     rcx, WPP_GLOBAL_Control
0x180059e24  cmp     rax, rcx
0x180059e27  jz      short loc_180059E64
0x180059e29  test    [rax+1Ch], r14b
0x180059e2d  jz      short loc_180059E64
0x180059e2f  cmp     byte ptr [rax+19h], 2
0x180059e33  jb      short loc_180059E64
0x180059e35  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180059e3a  lea     edx, [r15+1Bh]
0x180059e3e  lea     rcx, aDmContext; "DM_CONTEXT"
0x180059e45  mov     [rsp+138h+pwszReferrer], rcx
0x180059e4a  mov     r9d, eax
0x180059e4d  lea     r8, WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids
0x180059e54  mov     rcx, cs:WPP_GLOBAL_Control
0x180059e5b  mov     rcx, [rcx+10h]
0x180059e5f  call    WPP_SF_Ds
0x180059e64  mov     edi, 8007000Eh
0x180059e69  mov     [rsp+138h+var_F8], edi
0x180059e6d  mov     rdx, [rsp+138h+var_F0]
0x180059e72  jmp     loc_18005A202
0x180059e77  mov     [r13+810h], r15
0x180059e7e  mov     eax, 100h
0x180059e83  mov     [rsp+138h+var_E0], eax
0x180059e87  mov     ebx, eax
0x180059e89  mov     eax, 800100h
0x180059e8e  cmp     dword ptr [r13+0ECh], 2
0x180059e96  cmovz   ebx, eax
0x180059e99  mov     [rsp+138h+var_E0], ebx
0x180059e9d  mov     rcx, r12
0x180059ea0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180059ea5  mov     [rsp+138h+dwFlags], ebx; dwFlags
0x180059ea9  lea     rcx, [rsp+138h+var_70]
0x180059eb1  mov     [rsp+138h+ppwszAcceptTypes], rcx; ppwszAcceptTypes
0x180059eb6  mov     [rsp+138h+pwszReferrer], 0; pwszReferrer
0x180059ebf  xor     r9d, r9d; pwszVersion
0x180059ec2  mov     r8, rax; pwszObjectName
0x180059ec5  xor     edx, edx; pwszVerb
0x180059ec7  mov     rcx, [r13+188h]; hConnect
0x180059ece  call    cs:__imp_WinHttpOpenRequest
0x180059ed4  mov     [r15+28h], rax
0x180059ed8  test    rax, rax
0x180059edb  jnz     short loc_180059F55
0x180059edd  call    cs:__imp_GetLastError
0x180059ee3  mov     edi, eax
0x180059ee5  mov     rax, cs:WPP_GLOBAL_Control
0x180059eec  lea     rcx, WPP_GLOBAL_Control
0x180059ef3  cmp     rax, rcx
0x180059ef6  jz      short loc_180059F2C
0x180059ef8  test    [rax+1Ch], r14b
0x180059efc  jz      short loc_180059F2C
0x180059efe  cmp     byte ptr [rax+19h], 2
0x180059f02  jb      short loc_180059F2C
0x180059f04  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180059f09  mov     edx, 1Ch
0x180059f0e  mov     dword ptr [rsp+138h+pwszReferrer], edi
0x180059f12  mov     r9d, eax
0x180059f15  lea     r8, WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids
0x180059f1c  mov     rcx, cs:WPP_GLOBAL_Control
0x180059f23  mov     rcx, [rcx+10h]
0x180059f27  call    WPP_SF_Dd
0x180059f2c  test    edi, edi
0x180059f2e  jle     short loc_180059F39
0x180059f30  movzx   edi, di
0x180059f33  or      edi, 80070000h
0x180059f39  mov     [rsp+138h+var_F8], edi
0x180059f3d  mov     eax, 80004005h
0x180059f42  test    edi, edi
0x180059f44  cmovns  edi, eax
0x180059f47  mov     [rsp+138h+var_F8], edi
0x180059f4b  mov     rdx, [rsp+138h+var_F0]
0x180059f50  jmp     loc_18005A1FE
0x180059f55  lea     rcx, [r15+30h]
0x180059f59  mov     rdx, r12
0x180059f5c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180059f61  lea     rcx, [r15+50h]
0x180059f65  mov     rdx, rdi
0x180059f68  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180059f6d  mov     rdx, r15; struct _DM_CONTEXT *
0x180059f70  mov     rcx, r13; this
0x180059f73  call    ?SetAuthInfo@CDownloadManager@@IEAAJPEAU_DM_CONTEXT@@@Z; CDownloadManager::SetAuthInfo(_DM_CONTEXT *)
0x180059f78  mov     edi, eax
0x180059f7a  mov     [rsp+138h+var_F8], eax
0x180059f7e  test    eax, eax
0x180059f80  jns     short loc_180059FE0
0x180059f82  mov     rax, cs:WPP_GLOBAL_Control
0x180059f89  lea     rcx, WPP_GLOBAL_Control
0x180059f90  cmp     rax, rcx
0x180059f93  jz      short loc_180059FD6
0x180059f95  test    [rax+1Ch], r14b
0x180059f99  jz      short loc_180059FD6
0x180059f9b  cmp     byte ptr [rax+19h], 2
0x180059f9f  jb      short loc_180059FD6
0x180059fa1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180059fa6  mov     edx, 1Dh
0x180059fab  mov     dword ptr [rsp+138h+ppwszAcceptTypes], edi
0x180059faf  lea     rcx, aSetauthinfoFai; "SetAuthInfo failed"
0x180059fb6  mov     [rsp+138h+pwszReferrer], rcx
0x180059fbb  mov     r9d, eax
0x180059fbe  lea     r8, WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids
0x180059fc5  mov     rcx, cs:WPP_GLOBAL_Control
0x180059fcc  mov     rcx, [rcx+10h]
0x180059fd0  call    WPP_SF_DsD
0x180059fd5  nop
0x180059fd6  mov     rdx, [rsp+138h+var_F0]
0x180059fdb  jmp     loc_18005A1FE
0x180059fe0  lea     r8, [r13+190h]; lpBuffer
0x180059fe7  mov     edx, 26h ; '&'; dwOption
0x180059fec  lea     r9d, [rdx-0Eh]; dwBufferLength
0x180059ff0  mov     rcx, [r15+28h]; hInternet
0x180059ff4  call    cs:__imp_WinHttpSetOption
0x180059ffa  test    eax, eax
0x180059ffc  jnz     short loc_18005A076
0x180059ffe  call    cs:__imp_GetLastError
0x18005a004  mov     edi, eax
0x18005a006  mov     rax, cs:WPP_GLOBAL_Control
0x18005a00d  lea     rcx, WPP_GLOBAL_Control
0x18005a014  cmp     rax, rcx
0x18005a017  jz      short loc_18005A04D
0x18005a019  test    [rax+1Ch], r14b
0x18005a01d  jz      short loc_18005A04D
0x18005a01f  cmp     byte ptr [rax+19h], 2
0x18005a023  jb      short loc_18005A04D
0x18005a025  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005a02a  mov     edx, 1Eh
0x18005a02f  mov     dword ptr [rsp+138h+pwszReferrer], edi
0x18005a033  mov     r9d, eax
0x18005a036  lea     r8, WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids
0x18005a03d  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a044  mov     rcx, [rcx+10h]
0x18005a048  call    WPP_SF_Dd
0x18005a04d  test    edi, edi
0x18005a04f  jle     short loc_18005A05A
0x18005a051  movzx   edi, di
0x18005a054  or      edi, 80070000h
0x18005a05a  mov     [rsp+138h+var_F8], edi
0x18005a05e  mov     eax, 80004005h
0x18005a063  test    edi, edi
0x18005a065  cmovns  edi, eax
0x18005a068  mov     [rsp+138h+var_F8], edi
0x18005a06c  mov     rdx, [rsp+138h+var_F0]
0x18005a071  jmp     loc_18005A1FE
0x18005a076  cmp     dword ptr [r13+808h], 80072F8Fh
0x18005a081  jnz     loc_18005A15C
0x18005a087  mov     dword ptr [rsp+138h+Buffer], 0
0x18005a08f  mov     ecx, [r13+80Ch]
0x18005a096  xor     eax, eax
0x18005a098  test    cl, 10h
0x18005a09b  jz      short loc_18005A0A6
0x18005a09d  mov     eax, 1000h
0x18005a0a2  mov     dword ptr [rsp+138h+Buffer], eax
0x18005a0a6  test    cl, 20h
0x18005a0a9  jz      short loc_18005A0B3
0x18005a0ab  bts     eax, 0Dh
0x18005a0af  mov     dword ptr [rsp+138h+Buffer], eax
0x18005a0b3  test    r14b, cl
0x18005a0b6  jz      short loc_18005A0C0
0x18005a0b8  bts     eax, 8
0x18005a0bc  mov     dword ptr [rsp+138h+Buffer], eax
0x18005a0c0  test    eax, eax
0x18005a0c2  jz      loc_18005A15C
0x18005a0c8  mov     r9d, 4; dwBufferLength
0x18005a0ce  lea     r8, [rsp+138h+Buffer]; lpBuffer
0x18005a0d3  lea     ebx, [r9+1Bh]
0x18005a0d7  mov     edx, ebx; dwOption
0x18005a0d9  mov     rcx, [r15+28h]; hInternet
0x18005a0dd  call    cs:__imp_WinHttpSetOption
0x18005a0e3  test    eax, eax
0x18005a0e5  jnz     short loc_18005A15C
0x18005a0e7  call    cs:__imp_GetLastError
0x18005a0ed  mov     edi, eax
0x18005a0ef  mov     rax, cs:WPP_GLOBAL_Control
0x18005a0f6  lea     rcx, WPP_GLOBAL_Control
0x18005a0fd  cmp     rax, rcx
0x18005a100  jz      short loc_18005A133
0x18005a102  test    [rax+1Ch], r14b
0x18005a106  jz      short loc_18005A133
0x18005a108  cmp     byte ptr [rax+19h], 2
0x18005a10c  jb      short loc_18005A133
0x18005a10e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005a113  mov     edx, ebx
0x18005a115  mov     dword ptr [rsp+138h+pwszReferrer], edi
0x18005a119  mov     r9d, eax
0x18005a11c  lea     r8, WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids
0x18005a123  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a12a  mov     rcx, [rcx+10h]
0x18005a12e  call    WPP_SF_Dd
0x18005a133  test    edi, edi
0x18005a135  jle     short loc_18005A140
0x18005a137  movzx   edi, di
0x18005a13a  or      edi, 80070000h
0x18005a140  mov     [rsp+138h+var_F8], edi
0x18005a144  mov     eax, 80004005h
0x18005a149  test    edi, edi
  ... truncated ...
```
