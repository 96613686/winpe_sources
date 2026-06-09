# CRDPENCNATHelper::Initialize(void)

- ea: `0x180107b44`
- end: `0x180107f74`
- name: `?Initialize@CRDPENCNATHelper@@QEAAJXZ`
- size: `1072`
- prototype: `__int64 __fastcall(CRDPENCNATHelper *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180100580`

## callees

- `0x1800018a4`
- `0x180004970`
- `0x180019a80`
- `0x180046a84`
- `0x18006e6a8`
- `0x1800711c8`
- `0x1800721d4`
- `0x1800787d4`
- `0x180078820`
- `0x180078c20`
- `0x180107b44`
- `0x180107f7c`
- `0x180162010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180107bfc`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180107bfc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180107b7c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180107b7c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180107c99`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180107c99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180107b89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180107b89`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180107de3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180107de3`
- `OLEAUT32!__imp_SysAllocString` at `0x180107d25`
- `OLEAUT32!__imp_SysAllocString` at `0x180107d90`
- `OLEAUT32!__imp_SysAllocString` at `0x180107d25`
- `OLEAUT32!__imp_SysAllocString` at `0x180107d90`

## string_xrefs

- `0x180107cee`: `Failed to create the map string`
- `0x180107e34`: `Failed to create the UPnPNAT object (0x%08x)`

## pseudocode

```c
__int64 __fastcall CRDPENCNATHelper::Initialize(CRDPENCNATHelper *this)
{
  signed int LastError; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  wchar_t *v4; // rax
  WCHAR *v5; // rbx
  __int64 v6; // rax
  unsigned __int64 v7; // rdi
  unsigned __int16 *v8; // r14
  unsigned int v9; // eax
  unsigned int v10; // eax
  BSTR v11; // rax
  unsigned int v12; // eax
  __int64 v13; // rdx
  BSTR v14; // rax
  HRESULT Instance; // eax
  int v16; // r8d
  int v17; // r9d
  _QWORD *v18; // rdi
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  DWORD ppv; // [rsp+20h] [rbp-E0h]
  int v24; // [rsp+50h] [rbp-B0h] BYREF
  int v25; // [rsp+54h] [rbp-ACh] BYREF
  HRESULT v26; // [rsp+58h] [rbp-A8h] BYREF
  const char *v27; // [rsp+60h] [rbp-A0h] BYREF
  const char *v28; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v29[2]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Filename[264]; // [rsp+80h] [rbp-80h] BYREF

  if ( !GetModuleFileNameW(0, Filename, 0x105u) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_b09187b3dd74372127f5ed128673031d_Traceguids,
        CurrentThreadActivityIdPrefix,
        LastError);
    }
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError >= 0 )
      LastError = -2147467259;
    goto LABEL_50;
  }
  v4 = wcsrchr(Filename, 0x5Cu);
  if ( v4 )
    v5 = v4 + 1;
  else
    v5 = Filename;
  v6 = -1;
  do
    ++v6;
  while ( v5[v6] );
  v7 = v6 + 47;
  v8 = (unsigned __int16 *)operator new(saturated_mul(v6 + 47, 2u));
  if ( !v8 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v9 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_b09187b3dd74372127f5ed128673031d_Traceguids,
        v9,
        -2147024882);
    }
    LastError = -2147024882;
    goto LABEL_50;
  }
  ppv = GetCurrentProcessId();
  LastError = StringCchPrintfW(v8, v7, L"%s(%d)#RDPENC", v5, ppv);
  if ( LastError < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        (unsigned int)WPP_b09187b3dd74372127f5ed128673031d_Traceguids,
        v10,
        (__int64)"Failed to create the map string",
        LastError);
    }
    goto LABEL_49;
  }
  v11 = SysAllocString(v8);
  *((_QWORD *)this + 6) = v11;
  if ( !v11 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_33;
    }
    v12 = RdpWppGetCurrentThreadActivityIdPrefix();
    v13 = 13;
LABEL_32:
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v13,
      WPP_b09187b3dd74372127f5ed128673031d_Traceguids,
      v12,
      -2147024882);
LABEL_33:
    LastError = -2147024882;
    goto LABEL_49;
  }
  v14 = SysAllocString(L"TCP");
  *((_QWORD *)this + 7) = v14;
  if ( !v14 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_33;
    }
    v12 = RdpWppGetCurrentThreadActivityIdPrefix();
    v13 = 14;
    goto LABEL_32;
  }
  Instance = CoCreateInstance(&CLSID_UPnPNAT, 0, 1u, &GUID_b171c812_cc76_485a_94d8_b6b3a2794e99, (LPVOID *)this);
  if ( Instance < 0 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      v26 = Instance;
      v24 = 79;
      v27 = "Initialize";
      v28 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencnatman.cpp";
      v25 = -2147467259;
      v29[0] = "Failed to create the UPnPNAT object (0x%08x)";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (_DWORD)CallbackContext,
        (unsigned int)&word_1801C7A9E,
        v16,
        v17,
        (__int64)v29,
        (__int64)&v25,
        (__int64)&v28,
        (__int64)&v24,
        (__int64)&v27,
        (__int64)&v26);
    }
    LastError = 1;
    goto LABEL_49;
  }
  v18 = (_QWORD *)((char *)this + 8);
  LastError = (*(__int64 (__fastcall **)(_QWORD, char *))(**(_QWORD **)this + 56LL))(*(_QWORD *)this, (char *)this + 8);
  if ( LastError >= 0 )
    goto LABEL_46;
  LastError = 1;
  if ( *v18 )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 8);
    *v18 = 0;
LABEL_46:
    if ( *v18 )
      goto LABEL_49;
  }
  if ( (unsigned int)CallbackContext > 2 )
  {
    v25 = 93;
    v29[0] = "Initialize";
    v28 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencnatman.cpp";
    v24 = -2147467259;
    v27 = "Null port map collection. NAT device unavailable";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v19,
      (unsigned int)&byte_1801C7AE7,
      v20,
      v21,
      (__int64)&v27,
      (__int64)&v24,
      (__int64)&v28,
      (__int64)&v25,
      (__int64)v29);
  }
LABEL_49:
  operator delete(v8);
  if ( LastError < 0 )
LABEL_50:
    CRDPENCNATHelper::Terminate(this);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180107b44  push    rbp
0x180107b46  push    rbx
0x180107b47  push    rsi
0x180107b48  push    rdi
0x180107b49  push    r14
0x180107b4b  push    r15
0x180107b4d  lea     rbp, [rsp-1A8h]
0x180107b55  sub     rsp, 2A8h
0x180107b5c  mov     rax, cs:__security_cookie
0x180107b63  xor     rax, rsp
0x180107b66  mov     [rbp+1D0h+var_40], rax
0x180107b6d  mov     rsi, rcx
0x180107b70  lea     rdx, [rbp+1D0h+Filename]; lpFilename
0x180107b74  xor     ecx, ecx; hModule
0x180107b76  mov     r8d, 105h; nSize
0x180107b7c  call    cs:__imp_GetModuleFileNameW
0x180107b82  xor     r15d, r15d
0x180107b85  test    eax, eax
0x180107b87  jnz     short loc_180107BF3
0x180107b89  call    cs:__imp_GetLastError
0x180107b8f  mov     ebx, eax
0x180107b91  mov     rcx, cs:WPP_GLOBAL_Control
0x180107b98  lea     rax, WPP_GLOBAL_Control
0x180107b9f  cmp     rcx, rax
0x180107ba2  jz      short loc_180107BD7
0x180107ba4  test    byte ptr [rcx+1Ch], 8
0x180107ba8  jz      short loc_180107BD7
0x180107baa  cmp     byte ptr [rcx+19h], 2
0x180107bae  jb      short loc_180107BD7
0x180107bb0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180107bb5  mov     rcx, cs:WPP_GLOBAL_Control
0x180107bbc  lea     edx, [r15+0Ah]
0x180107bc0  mov     r9d, eax
0x180107bc3  mov     dword ptr [rsp+2D0h+ppv], ebx
0x180107bc7  lea     r8, WPP_b09187b3dd74372127f5ed128673031d_Traceguids
0x180107bce  mov     rcx, [rcx+10h]
0x180107bd2  call    WPP_SF_Dd
0x180107bd7  test    ebx, ebx
0x180107bd9  jle     short loc_180107BE4
0x180107bdb  movzx   ebx, bx
0x180107bde  or      ebx, 80070000h
0x180107be4  test    ebx, ebx
0x180107be6  mov     eax, 80004005h
0x180107beb  cmovns  ebx, eax
0x180107bee  jmp     loc_180107F4B
0x180107bf3  mov     edx, 5Ch ; '\'; Ch
0x180107bf8  lea     rcx, [rbp+1D0h+Filename]; Str
0x180107bfc  call    cs:__imp_wcsrchr
0x180107c02  mov     rbx, rax
0x180107c05  test    rax, rax
0x180107c08  jnz     short loc_180107C10
0x180107c0a  lea     rbx, [rbp+1D0h+Filename]
0x180107c0e  jmp     short loc_180107C14
0x180107c10  add     rbx, 2
0x180107c14  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180107c18  mov     rax, rcx
0x180107c1b  inc     rax
0x180107c1e  cmp     [rbx+rax*2], r15w
0x180107c23  jnz     short loc_180107C1B
0x180107c25  lea     rdi, [rax+2Fh]
0x180107c29  mov     eax, 2
0x180107c2e  mul     rdi
0x180107c31  cmovb   rax, rcx
0x180107c35  mov     rcx, rax; Size
0x180107c38  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180107c3d  mov     r14, rax
0x180107c40  test    rax, rax
0x180107c43  jnz     short loc_180107C99
0x180107c45  mov     rcx, cs:WPP_GLOBAL_Control
0x180107c4c  lea     rax, WPP_GLOBAL_Control
0x180107c53  cmp     rcx, rax
0x180107c56  jz      short loc_180107C8F
0x180107c58  test    byte ptr [rcx+1Ch], 8
0x180107c5c  jz      short loc_180107C8F
0x180107c5e  cmp     byte ptr [rcx+19h], 2
0x180107c62  jb      short loc_180107C8F
0x180107c64  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180107c69  mov     rcx, cs:WPP_GLOBAL_Control
0x180107c70  lea     edx, [r14+0Bh]
0x180107c74  mov     r9d, eax
0x180107c77  mov     dword ptr [rsp+2D0h+ppv], 8007000Eh
0x180107c7f  lea     r8, WPP_b09187b3dd74372127f5ed128673031d_Traceguids
0x180107c86  mov     rcx, [rcx+10h]
0x180107c8a  call    WPP_SF_Dd
0x180107c8f  mov     ebx, 8007000Eh
0x180107c94  jmp     loc_180107F4B
0x180107c99  call    cs:__imp_GetCurrentProcessId
0x180107c9f  mov     r9, rbx
0x180107ca2  lea     r8, aSDRdpenc; "%s(%d)#RDPENC"
0x180107ca9  mov     rdx, rdi; unsigned __int64
0x180107cac  mov     dword ptr [rsp+2D0h+ppv], eax
0x180107cb0  mov     rcx, r14; unsigned __int16 *
0x180107cb3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180107cb8  mov     ebx, eax
0x180107cba  test    eax, eax
0x180107cbc  jns     short loc_180107D22
0x180107cbe  mov     rcx, cs:WPP_GLOBAL_Control
0x180107cc5  lea     rax, WPP_GLOBAL_Control
0x180107ccc  cmp     rcx, rax
0x180107ccf  jz      loc_180107F3F
0x180107cd5  test    byte ptr [rcx+1Ch], 8
0x180107cd9  jz      loc_180107F3F
0x180107cdf  cmp     byte ptr [rcx+19h], 2
0x180107ce3  jb      loc_180107F3F
0x180107ce9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180107cee  lea     rcx, aFailedToCreate_103; "Failed to create the map string"
0x180107cf5  mov     dword ptr [rsp+2D0h+var_2A8], ebx
0x180107cf9  mov     [rsp+2D0h+ppv], rcx
0x180107cfe  lea     r8, WPP_b09187b3dd74372127f5ed128673031d_Traceguids
0x180107d05  mov     rcx, cs:WPP_GLOBAL_Control
0x180107d0c  mov     edx, 0Ch
0x180107d11  mov     r9d, eax
0x180107d14  mov     rcx, [rcx+10h]
0x180107d18  call    WPP_SF_DsD
0x180107d1d  jmp     loc_180107F3F
0x180107d22  mov     rcx, r14; psz
0x180107d25  call    cs:__imp_SysAllocString
0x180107d2b  mov     [rsi+30h], rax
0x180107d2f  test    rax, rax
0x180107d32  jnz     short loc_180107D89
0x180107d34  mov     rcx, cs:WPP_GLOBAL_Control
0x180107d3b  lea     rax, WPP_GLOBAL_Control
0x180107d42  cmp     rcx, rax
0x180107d45  jz      short loc_180107D7F
0x180107d47  test    byte ptr [rcx+1Ch], 8
0x180107d4b  jz      short loc_180107D7F
0x180107d4d  cmp     byte ptr [rcx+19h], 2
0x180107d51  jb      short loc_180107D7F
0x180107d53  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180107d58  mov     edx, 0Dh
0x180107d5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180107d64  lea     r8, WPP_b09187b3dd74372127f5ed128673031d_Traceguids
0x180107d6b  mov     r9d, eax
0x180107d6e  mov     dword ptr [rsp+2D0h+ppv], 8007000Eh
0x180107d76  mov     rcx, [rcx+10h]
0x180107d7a  call    WPP_SF_Dd
0x180107d7f  mov     ebx, 8007000Eh
0x180107d84  jmp     loc_180107F3F
0x180107d89  lea     rcx, aTcp; "TCP"
0x180107d90  call    cs:__imp_SysAllocString
0x180107d96  mov     [rsi+38h], rax
0x180107d9a  test    rax, rax
0x180107d9d  jnz     short loc_180107DCA
0x180107d9f  mov     rcx, cs:WPP_GLOBAL_Control
0x180107da6  lea     rax, WPP_GLOBAL_Control
0x180107dad  cmp     rcx, rax
0x180107db0  jz      short loc_180107D7F
0x180107db2  test    byte ptr [rcx+1Ch], 8
0x180107db6  jz      short loc_180107D7F
0x180107db8  cmp     byte ptr [rcx+19h], 2
0x180107dbc  jb      short loc_180107D7F
0x180107dbe  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180107dc3  mov     edx, 0Eh
0x180107dc8  jmp     short loc_180107D5D
0x180107dca  xor     edx, edx; pUnkOuter
0x180107dcc  mov     [rsp+2D0h+ppv], rsi; ppv
0x180107dd1  lea     r9, _GUID_b171c812_cc76_485a_94d8_b6b3a2794e99; riid
0x180107dd8  lea     rcx, CLSID_UPnPNAT; rclsid
0x180107ddf  lea     r8d, [rdx+1]; dwClsContext
0x180107de3  call    cs:__imp_CoCreateInstance
0x180107de9  test    eax, eax
0x180107deb  jns     loc_180107E8B
0x180107df1  mov     ecx, cs:CallbackContext
0x180107df7  cmp     ecx, 2
0x180107dfa  jbe     loc_180107E81
0x180107e00  mov     [rsp+2D0h+var_278], eax
0x180107e04  lea     rdx, word_1801C7A9E
0x180107e0b  lea     rax, aInitialize; "Initialize"
0x180107e12  mov     [rsp+2D0h+var_280], 4Fh ; 'O'
0x180107e1a  mov     [rsp+2D0h+var_270], rax
0x180107e1f  lea     rax, aOnecoreTermsrv_34; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180107e26  mov     [rsp+2D0h+var_268], rax
0x180107e2b  mov     eax, 80004005h
0x180107e30  mov     [rsp+2D0h+var_27C], eax
0x180107e34  lea     rax, aFailedToCreate_63; "Failed to create the UPnPNAT object (0x"...
0x180107e3b  mov     [rsp+2D0h+var_260], rax
0x180107e40  lea     rax, [rsp+2D0h+var_278]
0x180107e45  mov     [rsp+2D0h+var_288], rax
0x180107e4a  lea     rax, [rsp+2D0h+var_270]
0x180107e4f  mov     [rsp+2D0h+var_290], rax
0x180107e54  lea     rax, [rsp+2D0h+var_280]
0x180107e59  mov     [rsp+2D0h+var_298], rax
0x180107e5e  lea     rax, [rsp+2D0h+var_268]
0x180107e63  mov     [rsp+2D0h+var_2A0], rax
0x180107e68  lea     rax, [rsp+2D0h+var_27C]
0x180107e6d  mov     [rsp+2D0h+var_2A8], rax
0x180107e72  lea     rax, [rsp+2D0h+var_260]
0x180107e77  mov     [rsp+2D0h+ppv], rax
0x180107e7c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180107e81  mov     ebx, 1
0x180107e86  jmp     loc_180107F3F
0x180107e8b  mov     rcx, [rsi]
0x180107e8e  lea     rdi, [rsi+8]
0x180107e92  mov     rdx, rdi
0x180107e95  mov     rax, [rcx]
0x180107e98  mov     rax, [rax+38h]
0x180107e9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180107ea1  mov     ebx, eax
0x180107ea3  test    eax, eax
0x180107ea5  jns     short loc_180107EBC
0x180107ea7  mov     ebx, 1
0x180107eac  cmp     [rdi], r15
0x180107eaf  jz      short loc_180107EC1
0x180107eb1  mov     rcx, rdi; void *
0x180107eb4  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x180107eb9  mov     [rdi], r15
0x180107ebc  cmp     [rdi], r15
0x180107ebf  jnz     short loc_180107F3F
0x180107ec1  mov     eax, cs:CallbackContext
0x180107ec7  cmp     eax, 2
0x180107eca  jbe     short loc_180107F3F
0x180107ecc  lea     rax, aInitialize; "Initialize"
0x180107ed3  mov     [rsp+2D0h+var_27C], 5Dh ; ']'
0x180107edb  mov     [rsp+2D0h+var_260], rax
0x180107ee0  lea     rdx, byte_1801C7AE7
0x180107ee7  lea     rax, aOnecoreTermsrv_34; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180107eee  mov     [rsp+2D0h+var_268], rax
0x180107ef3  mov     eax, 80004005h
0x180107ef8  mov     [rsp+2D0h+var_280], eax
0x180107efc  lea     rax, aNullPortMapCol; "Null port map collection. NAT device un"...
0x180107f03  mov     [rsp+2D0h+var_270], rax
0x180107f08  lea     rax, [rsp+2D0h+var_260]
0x180107f0d  mov     [rsp+2D0h+var_290], rax
0x180107f12  lea     rax, [rsp+2D0h+var_27C]
0x180107f17  mov     [rsp+2D0h+var_298], rax
0x180107f1c  lea     rax, [rsp+2D0h+var_268]
0x180107f21  mov     [rsp+2D0h+var_2A0], rax
0x180107f26  lea     rax, [rsp+2D0h+var_280]
0x180107f2b  mov     [rsp+2D0h+var_2A8], rax
0x180107f30  lea     rax, [rsp+2D0h+var_270]
0x180107f35  mov     [rsp+2D0h+ppv], rax
0x180107f3a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180107f3f  mov     rcx, r14; Block
0x180107f42  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180107f47  test    ebx, ebx
0x180107f49  jns     short loc_180107F53
0x180107f4b  mov     rcx, rsi; this
0x180107f4e  call    ?Terminate@CRDPENCNATHelper@@QEAAJXZ; CRDPENCNATHelper::Terminate(void)
0x180107f53  mov     eax, ebx
0x180107f55  mov     rcx, [rbp+1D0h+var_40]
0x180107f5c  xor     rcx, rsp; StackCookie
0x180107f5f  call    __security_check_cookie
0x180107f64  add     rsp, 2A8h
0x180107f6b  pop     r15
0x180107f6d  pop     r14
0x180107f6f  pop     rdi
0x180107f70  pop     rsi
0x180107f71  pop     rbx
0x180107f72  pop     rbp
0x180107f73  retn
```
