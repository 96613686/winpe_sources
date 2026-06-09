# OneSettings::GetCloudSettings(void)

- ea: `0x1400168b4`
- end: `0x140016da3`
- name: `?GetCloudSettings@OneSettings@@AEAAJXZ`
- size: `1263`
- prototype: `__int64 __fastcall(HINTERNET *this, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140018a94`

## callees

- `0x140002600`
- `0x140002624`
- `0x1400030dc`
- `0x140007da8`
- `0x140007dc8`
- `0x140013a2c`
- `0x140013d3c`
- `0x1400141a4`
- `0x140014420`
- `0x1400153f4`
- `0x14001551c`
- `0x1400168b4`
- `0x140016dc0`
- `0x140017018`
- `0x140018680`
- `0x140018bf0`
- `0x14001a344`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1400169af`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1400169cc`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1400169af`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1400169cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001697d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001697d`
- `WINHTTP!WinHttpSendRequest` at `0x140016924`
- `WINHTTP!WinHttpSendRequest` at `0x140016924`
- `WINHTTP!WinHttpQueryHeaders` at `0x140016a19`
- `WINHTTP!WinHttpQueryHeaders` at `0x140016a19`
- `WINHTTP!WinHttpReadData` at `0x140016bbd`
- `WINHTTP!WinHttpReadData` at `0x140016bbd`
- `WINHTTP!WinHttpReceiveResponse` at `0x1400169e3`
- `WINHTTP!WinHttpReceiveResponse` at `0x1400169e3`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x140016b12`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x140016b12`
- `WINHTTP!WinHttpQueryOption` at `0x140016973`
- `WINHTTP!WinHttpQueryOption` at `0x140016973`

## pseudocode

```c
__int64 __fastcall OneSettings::GetCloudSettings(HINTERNET *this, __int64 a2, unsigned int a3)
{
  int EtagHeaderFromRegistry; // eax
  unsigned __int16 *v5; // rdx
  const char *v6; // r9
  __int64 v7; // rdx
  signed int LastError; // eax
  unsigned int v10; // ebx
  __int64 v11; // rdx
  int EtagFromRequest; // eax
  __int64 v13; // rdx
  const unsigned __int16 *v14; // rdx
  const char *v15; // r9
  size_t v16; // rdi
  void *v17; // rax
  void *v18; // rcx
  _QWORD *v19; // rax
  char *v20; // rbx
  const char *v21; // r9
  __int64 v22; // r9
  __int64 v23; // rdx
  int v24; // eax
  int dwOptionalLength; // [rsp+20h] [rbp-E0h]
  _BYTE v26[4]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD dwNumberOfBytesAvailable; // [rsp+44h] [rbp-BCh] BYREF
  int v28; // [rsp+48h] [rbp-B8h] BYREF
  char *v29[2]; // [rsp+50h] [rbp-B0h] BYREF
  char *v30; // [rsp+60h] [rbp-A0h]
  DWORD dwNumberOfBytesRead; // [rsp+68h] [rbp-98h] BYREF
  LPVOID lpBuffer[2]; // [rsp+70h] [rbp-90h] BYREF
  char *v33; // [rsp+80h] [rbp-80h]
  DWORD dwBufferLength[2]; // [rsp+88h] [rbp-78h] BYREF
  DWORD v35[4]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE Buffer[16]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v37; // [rsp+B0h] [rbp-50h]
  __int64 v38; // [rsp+B8h] [rbp-48h]
  unsigned __int16 *v39[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v40; // [rsp+F0h] [rbp-10h]
  unsigned __int64 v41; // [rsp+F8h] [rbp-8h]
  __int128 v42; // [rsp+100h] [rbp+0h] BYREF
  __int64 v43; // [rsp+110h] [rbp+10h]
  __int64 v44; // [rsp+118h] [rbp+18h]
  unsigned __int16 v45[264]; // [rsp+120h] [rbp+20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+358h] [rbp+258h]

  v28 = 0;
  v35[0] = 4;
  EtagHeaderFromRegistry = OneSettings::GetEtagHeaderFromRegistry((OneSettings *)this, v45, a3);
  v5 = v45;
  if ( EtagHeaderFromRegistry < 0 )
    v5 = 0;
  if ( !WinHttpSendRequest(this[23], v5, 0xFFFFFFFF, 0, 0, 0, 0) )
  {
    v7 = 744;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v7,
             (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\onesettings\\src\\onesettings.cpp",
             v6);
  }
  memset_0(Buffer, 0, 0x40u);
  dwBufferLength[0] = 64;
  if ( !WinHttpQueryOption(this[23], 0x20u, Buffer, dwBufferLength) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v10 = -2147467259;
    if ( LastError < 0 )
      v10 = LastError;
    goto LABEL_58;
  }
  if ( (unsigned int)_o__wcsnicmp(v38, L"US\r\nWashington\r\nRedmond\r\nMicrosoft Corporation")
    || (unsigned int)_o__wcsnicmp(v37, L"US\r\nWA\r\nRedmond\r\nMicrosoft\r\nWSE") )
  {
    v10 = -2089418751;
LABEL_58:
    v11 = 745;
    goto LABEL_59;
  }
  if ( !WinHttpReceiveResponse(this[23], 0) )
  {
    v7 = 746;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v7,
             (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\onesettings\\src\\onesettings.cpp",
             v6);
  }
  if ( !WinHttpQueryHeaders(this[23], 0x20000013u, 0, &v28, v35, 0) )
  {
    v7 = 747;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v7,
             (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\onesettings\\src\\onesettings.cpp",
             v6);
  }
  if ( v28 != 200 && v28 != 304 )
  {
    v10 = -2147467259;
    v11 = 749;
LABEL_59:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\onesettings\\src\\onesettings.cpp",
      (const char *)v10,
      dwOptionalLength);
    return v10;
  }
  *(_OWORD *)v39 = 0;
  v40 = 0;
  v41 = 7;
  LOWORD(v39[0]) = 0;
  v42 = 0;
  v43 = 0;
  v44 = 7;
  LOWORD(v42) = 0;
  EtagFromRequest = OneSettings::GetEtagFromRequest(this, v39, this + 24, &v42);
  v10 = EtagFromRequest;
  if ( EtagFromRequest >= 0 )
  {
    v14 = (const unsigned __int16 *)v39;
    if ( v41 > 7 )
      v14 = v39[0];
    EtagFromRequest = OneSettings::SaveEtagHeaderToRegistry((OneSettings *)this, v14);
    v10 = EtagFromRequest;
    if ( EtagFromRequest >= 0 )
    {
      if ( v28 == 304 )
      {
        v10 = 1;
      }
      else
      {
        dwNumberOfBytesAvailable = 0;
        dwNumberOfBytesRead = 0;
        *(_OWORD *)v29 = 0;
        v30 = 0;
        do
        {
          if ( !WinHttpQueryDataAvailable(this[23], &dwNumberOfBytesAvailable) )
          {
            v10 = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x300,
                    (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\onesettings\\src\\onesettings.cpp",
                    v15);
            goto LABEL_55;
          }
          if ( !dwNumberOfBytesAvailable )
            break;
          v16 = dwNumberOfBytesAvailable;
          *(_OWORD *)lpBuffer = 0;
          v33 = 0;
          if ( dwNumberOfBytesAvailable < 0x1000uLL )
          {
            v19 = operator new(dwNumberOfBytesAvailable);
          }
          else
          {
            if ( (unsigned __int64)dwNumberOfBytesAvailable + 39 < dwNumberOfBytesAvailable )
              __scrt_throw_std_bad_array_new_length();
            v17 = operator new(dwNumberOfBytesAvailable + 39LL);
            v18 = v17;
            if ( !v17 )
              __fastfail(5u);
            v19 = (_QWORD *)(((unsigned __int64)v17 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
            *(v19 - 1) = v18;
          }
          lpBuffer[0] = v19;
          v20 = (char *)v19 + v16;
          v33 = (char *)v19 + v16;
          memset_0(v19, 0, v16);
          lpBuffer[1] = v20;
          *(_QWORD *)dwBufferLength = 0;
          std::_Tidy_guard<std::vector<unsigned char>>::~_Tidy_guard<std::vector<unsigned char>>(dwBufferLength);
          if ( !WinHttpReadData(this[23], lpBuffer[0], dwNumberOfBytesAvailable, &dwNumberOfBytesRead) )
          {
            v10 = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x309,
                    (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\onesettings\\src\\onesettings.cpp",
                    v21);
            goto LABEL_46;
          }
          if ( dwNumberOfBytesRead != dwNumberOfBytesAvailable )
          {
            v10 = -2147418113;
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x30D,
              (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\onesettings\\src\\onesettings.cpp",
              (const char *)0x8000FFFFLL,
              dwOptionalLength);
LABEL_46:
            std::vector<unsigned char>::~vector<unsigned char>(lpBuffer);
            goto LABEL_55;
          }
          std::vector<unsigned char>::reserve(
            v29,
            (char *)lpBuffer[1] + v29[1] - v29[0] - (unsigned __int64)lpBuffer[0] + 1);
          std::vector<unsigned char>::_Insert_counted_range<unsigned char *>(
            v29,
            v29[1],
            lpBuffer[0],
            (char *)lpBuffer[1] - (char *)lpBuffer[0]);
          std::vector<unsigned char>::~vector<unsigned char>(lpBuffer);
        }
        while ( dwNumberOfBytesAvailable );
        if ( v29[1] == v29[0] )
        {
          v10 = -2147024664;
          v22 = 2147942632LL;
          v23 = 791;
        }
        else
        {
          v26[0] = 0;
          if ( v29[1] == v30 )
            std::vector<unsigned char>::_Emplace_reallocate<unsigned char>(v29, v29[1], v26);
          else
            *v29[1]++ = 0;
          v24 = OneSettings::ParseJsonBlob((OneSettings *)this, v29[0]);
          v10 = v24;
          if ( v24 >= 0 )
          {
            std::vector<unsigned char>::~vector<unsigned char>(v29);
            std::wstring::~wstring(&v42);
            std::wstring::~wstring(v39);
            return 0;
          }
          v22 = (unsigned int)v24;
          v23 = 796;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v23,
          (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\onesettings\\src\\onesettings.cpp",
          (const char *)v22,
          dwOptionalLength);
LABEL_55:
        std::vector<unsigned char>::~vector<unsigned char>(v29);
      }
      goto LABEL_56;
    }
    v13 = 754;
  }
  else
  {
    v13 = 753;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v13,
    (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\onesettings\\src\\onesettings.cpp",
    (const char *)(unsigned int)EtagFromRequest,
    dwOptionalLength);
LABEL_56:
  std::wstring::~wstring(&v42);
  std::wstring::~wstring(v39);
  return v10;
}

```

## disassembly

```asm
0x1400168b4  mov     [rsp-8+arg_8], rbx
0x1400168b9  mov     [rsp-8+arg_10], rsi
0x1400168be  push    rbp
0x1400168bf  push    rdi
0x1400168c0  push    r14
0x1400168c2  lea     rbp, [rsp-240h]
0x1400168ca  sub     rsp, 340h
0x1400168d1  mov     rax, cs:__security_cookie
0x1400168d8  xor     rax, rsp
0x1400168db  mov     [rbp+250h+var_20], rax
0x1400168e2  mov     rsi, rcx
0x1400168e5  xor     r14d, r14d
0x1400168e8  mov     [rsp+350h+var_308], r14d
0x1400168ed  mov     [rbp+250h+var_2C0], 4
0x1400168f4  lea     rdx, [rbp+250h+var_230]; unsigned __int16 *
0x1400168f8  call    ?GetEtagHeaderFromRegistry@OneSettings@@AEAAJPEAGK@Z; OneSettings::GetEtagHeaderFromRegistry(ushort *,ulong)
0x1400168fd  lea     rdx, [rbp+250h+var_230]
0x140016901  test    eax, eax
0x140016903  cmovs   rdx, r14; lpszHeaders
0x140016907  mov     [rsp+350h+dwContext], r14; dwContext
0x14001690c  mov     [rsp+350h+dwTotalLength], r14d; dwTotalLength
0x140016911  mov     [rsp+350h+dwOptionalLength], r14d; int
0x140016916  xor     r9d, r9d; lpOptional
0x140016919  or      r8d, 0FFFFFFFFh; dwHeadersLength
0x14001691d  mov     rcx, [rsi+0B8h]; hRequest
0x140016924  call    cs:__imp_WinHttpSendRequest
0x14001692a  test    eax, eax
0x14001692c  jnz     short loc_14001694B
0x14001692e  mov     edx, 2E8h; void *
0x140016933  mov     rcx, [rbp+258h]; this
0x14001693a  lea     r8, aOnecoreuapEndu_111; "onecoreuap\\enduser\\nui\\onecore\\ones"...
0x140016941  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140016946  jmp     loc_140016D76
0x14001694b  mov     ebx, 40h ; '@'
0x140016950  mov     r8d, ebx; Size
0x140016953  xor     edx, edx; Val
0x140016955  lea     rcx, [rbp+250h+Buffer]; void *
0x140016959  call    memset_0
0x14001695e  mov     [rbp+250h+dwBufferLength], ebx
0x140016961  lea     r9, [rbp+250h+dwBufferLength]; lpdwBufferLength
0x140016965  lea     r8, [rbp+250h+Buffer]; lpBuffer
0x140016969  lea     edx, [rbx-20h]; dwOption
0x14001696c  mov     rcx, [rsi+0B8h]; hInternet
0x140016973  call    cs:__imp_WinHttpQueryOption
0x140016979  test    eax, eax
0x14001697b  jnz     short loc_14001699E
0x14001697d  call    cs:__imp_GetLastError
0x140016983  test    eax, eax
0x140016985  jle     short loc_14001698F
0x140016987  movzx   eax, ax
0x14001698a  or      eax, 80070000h
0x14001698f  mov     ebx, 80004005h
0x140016994  test    eax, eax
0x140016996  cmovs   ebx, eax
0x140016999  jmp     loc_140016D59
0x14001699e  mov     r8d, 2Eh ; '.'
0x1400169a4  lea     rdx, aUsWashingtonRe; "US\r\nWashington\r\nRedmond\r\nMicrosof"...
0x1400169ab  mov     rcx, [rbp+250h+var_298]
0x1400169af  call    cs:__imp__o__wcsnicmp
0x1400169b5  test    eax, eax
0x1400169b7  jnz     loc_140016D54
0x1400169bd  lea     r8d, [rax+1Fh]
0x1400169c1  lea     rdx, aUsWaRedmondMic; "US\r\nWA\r\nRedmond\r\nMicrosoft\r\nWSE"
0x1400169c8  mov     rcx, [rbp+250h+var_2A0]
0x1400169cc  call    cs:__imp__o__wcsnicmp
0x1400169d2  test    eax, eax
0x1400169d4  jnz     loc_140016D54
0x1400169da  xor     edx, edx; lpReserved
0x1400169dc  mov     rcx, [rsi+0B8h]; hRequest
0x1400169e3  call    cs:__imp_WinHttpReceiveResponse
0x1400169e9  test    eax, eax
0x1400169eb  jnz     short loc_1400169F7
0x1400169ed  mov     edx, 2EAh
0x1400169f2  jmp     loc_140016933
0x1400169f7  mov     qword ptr [rsp+350h+dwTotalLength], r14; lpdwIndex
0x1400169fc  lea     rax, [rbp+250h+var_2C0]
0x140016a00  mov     qword ptr [rsp+350h+dwOptionalLength], rax; int
0x140016a05  lea     r9, [rsp+350h+var_308]; lpBuffer
0x140016a0a  xor     r8d, r8d; pwszName
0x140016a0d  mov     edx, 20000013h; dwInfoLevel
0x140016a12  mov     rcx, [rsi+0B8h]; hRequest
0x140016a19  call    cs:__imp_WinHttpQueryHeaders
0x140016a1f  test    eax, eax
0x140016a21  jnz     short loc_140016A2D
0x140016a23  mov     edx, 2EBh
0x140016a28  jmp     loc_140016933
0x140016a2d  mov     edi, 130h
0x140016a32  cmp     [rsp+350h+var_308], 0C8h
0x140016a3a  jz      short loc_140016A51
0x140016a3c  cmp     [rsp+350h+var_308], edi
0x140016a40  jz      short loc_140016A51
0x140016a42  mov     ebx, 80004005h
0x140016a47  mov     edx, 2EDh
0x140016a4c  jmp     loc_140016D5E
0x140016a51  xorps   xmm0, xmm0
0x140016a54  movups  xmmword ptr [rbp+250h+var_270], xmm0
0x140016a58  mov     [rbp+250h+var_260], r14
0x140016a5c  mov     [rbp+250h+var_258], 7
0x140016a64  mov     word ptr [rbp+250h+var_270], r14w
0x140016a69  movups  [rbp+250h+var_250], xmm0
0x140016a6d  mov     [rbp+250h+var_240], r14
0x140016a71  mov     [rbp+250h+var_238], 7
0x140016a79  mov     word ptr [rbp+250h+var_250], r14w
0x140016a7e  lea     r8, [rsi+0C0h]
0x140016a85  lea     r9, [rbp+250h+var_250]
0x140016a89  lea     rdx, [rbp+250h+var_270]
0x140016a8d  mov     rcx, rsi
0x140016a90  call    ?GetEtagFromRequest@OneSettings@@AEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAK0@Z; OneSettings::GetEtagFromRequest(std::wstring &,ulong &,std::wstring &)
0x140016a95  mov     ebx, eax
0x140016a97  test    eax, eax
0x140016a99  jns     short loc_140016AA2
0x140016a9b  mov     edx, 2F1h
0x140016aa0  jmp     short loc_140016AC3
0x140016aa2  lea     rdx, [rbp+250h+var_270]
0x140016aa6  cmp     [rbp+250h+var_258], 7
0x140016aab  cmova   rdx, [rbp+250h+var_270]; unsigned __int16 *
0x140016ab0  mov     rcx, rsi; this
0x140016ab3  call    ?SaveEtagHeaderToRegistry@OneSettings@@AEAAJPEBG@Z; OneSettings::SaveEtagHeaderToRegistry(ushort const *)
0x140016ab8  mov     ebx, eax
0x140016aba  test    eax, eax
0x140016abc  jns     short loc_140016ADE
0x140016abe  mov     edx, 2F2h; void *
0x140016ac3  lea     r8, aOnecoreuapEndu_111; "onecoreuap\\enduser\\nui\\onecore\\ones"...
0x140016aca  mov     r9d, eax; char *
0x140016acd  mov     rcx, [rbp+258h]; this
0x140016ad4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140016ad9  jmp     loc_140016D3F
0x140016ade  cmp     [rsp+350h+var_308], edi
0x140016ae2  jnz     short loc_140016AEE
0x140016ae4  mov     ebx, 1
0x140016ae9  jmp     loc_140016D3F
0x140016aee  mov     [rsp+350h+dwNumberOfBytesAvailable], r14d
0x140016af3  mov     [rsp+350h+dwNumberOfBytesRead], r14d
0x140016af8  xorps   xmm0, xmm0
0x140016afb  movdqu  xmmword ptr [rsp+350h+var_300], xmm0
0x140016b01  mov     [rsp+350h+var_2F0], r14
0x140016b06  lea     rdx, [rsp+350h+dwNumberOfBytesAvailable]; lpdwNumberOfBytesAvailable
0x140016b0b  mov     rcx, [rsi+0B8h]; hRequest
0x140016b12  call    cs:__imp_WinHttpQueryDataAvailable
0x140016b18  test    eax, eax
0x140016b1a  jz      loc_140016D1A
0x140016b20  mov     r8d, [rsp+350h+dwNumberOfBytesAvailable]
0x140016b25  test    r8d, r8d
0x140016b28  jz      loc_140016C2F
0x140016b2e  mov     edi, r8d
0x140016b31  xorps   xmm0, xmm0
0x140016b34  movdqu  xmmword ptr [rsp+350h+lpBuffer], xmm0
0x140016b3a  mov     [rbp+250h+var_2D0], r14
0x140016b3e  cmp     r8, 1000h
0x140016b45  jb      short loc_140016B73
0x140016b47  lea     rcx, [r8+27h]; Size
0x140016b4b  cmp     rcx, r8
0x140016b4e  jbe     loc_140016D9D
0x140016b54  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140016b59  mov     rcx, rax
0x140016b5c  test    rax, rax
0x140016b5f  jz      loc_140016C60
0x140016b65  add     rax, 27h ; '''
0x140016b69  and     rax, 0FFFFFFFFFFFFFFE0h
0x140016b6d  mov     [rax-8], rcx
0x140016b71  jmp     short loc_140016B7B
0x140016b73  mov     rcx, rdi; Size
0x140016b76  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140016b7b  mov     [rsp+350h+lpBuffer], rax
0x140016b80  lea     rbx, [rax+rdi]
0x140016b84  mov     [rbp+250h+var_2D0], rbx
0x140016b88  mov     r8, rdi; Size
0x140016b8b  xor     edx, edx; Val
0x140016b8d  mov     rcx, rax; void *
0x140016b90  call    memset_0
0x140016b95  mov     [rsp+350h+lpBuffer+8], rbx
0x140016b9a  mov     qword ptr [rbp+250h+dwBufferLength], r14
0x140016b9e  lea     rcx, [rbp+250h+dwBufferLength]
0x140016ba2  call    ??1?$_Tidy_guard@V?$vector@EV?$allocator@E@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<uchar>>::~_Tidy_guard<std::vector<uchar>>(void)
0x140016ba7  mov     r8d, [rsp+350h+dwNumberOfBytesAvailable]; dwNumberOfBytesToRead
0x140016bac  lea     r9, [rsp+350h+dwNumberOfBytesRead]; lpdwNumberOfBytesRead
0x140016bb1  mov     rdx, [rsp+350h+lpBuffer]; lpBuffer
0x140016bb6  mov     rcx, [rsi+0B8h]; hRequest
0x140016bbd  call    cs:__imp_WinHttpReadData
0x140016bc3  test    eax, eax
0x140016bc5  jz      loc_140016C97
0x140016bcb  mov     eax, [rsp+350h+dwNumberOfBytesAvailable]
0x140016bcf  cmp     [rsp+350h+dwNumberOfBytesRead], eax
0x140016bd3  jnz     loc_140016C67
0x140016bd9  mov     rcx, [rsp+350h+var_300+8]
0x140016bde  sub     rcx, [rsp+350h+var_300]
0x140016be3  sub     rcx, [rsp+350h+lpBuffer]
0x140016be8  mov     rdx, [rsp+350h+lpBuffer+8]
0x140016bed  inc     rdx
0x140016bf0  add     rdx, rcx
0x140016bf3  lea     rcx, [rsp+350h+var_300]
0x140016bf8  call    ?reserve@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::reserve(unsigned __int64)
0x140016bfd  mov     r9, [rsp+350h+lpBuffer+8]
0x140016c02  mov     r8, [rsp+350h+lpBuffer]
0x140016c07  sub     r9, r8
0x140016c0a  mov     rdx, [rsp+350h+var_300+8]
0x140016c0f  lea     rcx, [rsp+350h+var_300]
0x140016c14  call    ??$_Insert_counted_range@PEAE@?$vector@EV?$allocator@E@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@PEAE_K@Z; std::vector<uchar>::_Insert_counted_range<uchar *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,uchar *,unsigned __int64)
0x140016c19  nop
0x140016c1a  lea     rcx, [rsp+350h+lpBuffer]
0x140016c1f  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x140016c24  cmp     [rsp+350h+dwNumberOfBytesAvailable], r14d
0x140016c29  jnz     loc_140016B06
0x140016c2f  mov     rdx, [rsp+350h+var_300+8]
0x140016c34  cmp     rdx, [rsp+350h+var_300]
0x140016c39  jnz     short loc_140016CB3
0x140016c3b  mov     ebx, 800700E8h
0x140016c40  mov     r9d, ebx; char *
0x140016c43  mov     edx, 317h; void *
0x140016c48  lea     r8, aOnecoreuapEndu_111; "onecoreuap\\enduser\\nui\\onecore\\ones"...
0x140016c4f  mov     rcx, [rbp+258h]; this
0x140016c56  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140016c5b  jmp     loc_140016D34
0x140016c60  mov     ecx, 5
0x140016c65  int     29h; Win8: RtlFailFast(ecx)
0x140016c67  mov     rcx, [rbp+258h]; this
0x140016c6e  mov     ebx, 8000FFFFh
0x140016c73  mov     r9d, ebx; char *
0x140016c76  lea     r8, aOnecoreuapEndu_111; "onecoreuap\\enduser\\nui\\onecore\\ones"...
0x140016c7d  mov     edx, 30Dh; void *
0x140016c82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140016c87  nop
0x140016c88  lea     rcx, [rsp+350h+lpBuffer]
0x140016c8d  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x140016c92  jmp     loc_140016D34
0x140016c97  mov     rcx, [rbp+258h]; this
0x140016c9e  lea     r8, aOnecoreuapEndu_111; "onecoreuap\\enduser\\nui\\onecore\\ones"...
0x140016ca5  mov     edx, 309h; void *
0x140016caa  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140016caf  mov     ebx, eax
0x140016cb1  jmp     short loc_140016C88
0x140016cb3  mov     [rsp+350h+var_310], r14b
0x140016cb8  cmp     rdx, [rsp+350h+var_2F0]
0x140016cbd  jz      short loc_140016CC9
0x140016cbf  mov     [rdx], r14b
0x140016cc2  inc     [rsp+350h+var_300+8]
0x140016cc7  jmp     short loc_140016CD8
0x140016cc9  lea     r8, [rsp+350h+var_310]
0x140016cce  lea     rcx, [rsp+350h+var_300]
0x140016cd3  call    ??$_Emplace_reallocate@E@?$vector@EV?$allocator@E@std@@@std@@AEAAPEAEQEAE$$QEAE@Z; std::vector<uchar>::_Emplace_reallocate<uchar>(uchar * const,uchar &&)
0x140016cd8  mov     rdx, [rsp+350h+var_300]; char *
0x140016cdd  mov     rcx, rsi; this
0x140016ce0  call    ?ParseJsonBlob@OneSettings@@AEAAJPEBD@Z; OneSettings::ParseJsonBlob(char const *)
0x140016ce5  mov     ebx, eax
0x140016ce7  test    eax, eax
0x140016ce9  jns     short loc_140016CF8
0x140016ceb  mov     r9d, eax
0x140016cee  mov     edx, 31Ch
0x140016cf3  jmp     loc_140016C48
0x140016cf8  lea     rcx, [rsp+350h+var_300]
0x140016cfd  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x140016d02  nop
0x140016d03  lea     rcx, [rbp+250h+var_250]
0x140016d07  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140016d0c  nop
0x140016d0d  lea     rcx, [rbp+250h+var_270]
0x140016d11  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140016d16  xor     eax, eax
0x140016d18  jmp     short loc_140016D76
0x140016d1a  mov     rcx, [rbp+258h]; this
0x140016d21  lea     r8, aOnecoreuapEndu_111; "onecoreuap\\enduser\\nui\\onecore\\ones"...
0x140016d28  mov     edx, 300h; void *
0x140016d2d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140016d32  mov     ebx, eax
0x140016d34  lea     rcx, [rsp+350h+var_300]
0x140016d39  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x140016d3e  nop
0x140016d3f  lea     rcx, [rbp+250h+var_250]
0x140016d43  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140016d48  nop
0x140016d49  lea     rcx, [rbp+250h+var_270]
0x140016d4d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140016d52  jmp     short loc_140016D74
0x140016d54  mov     ebx, 83760001h
0x140016d59  mov     edx, 2E9h; void *
0x140016d5e  mov     r9d, ebx; char *
0x140016d61  lea     r8, aOnecoreuapEndu_111; "onecoreuap\\enduser\\nui\\onecore\\ones"...
0x140016d68  mov     rcx, [rbp+258h]; this
0x140016d6f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140016d74  mov     eax, ebx
0x140016d76  mov     rcx, [rbp+250h+var_20]
0x140016d7d  xor     rcx, rsp; StackCookie
0x140016d80  call    __security_check_cookie
0x140016d85  lea     r11, [rsp+350h+var_10]
0x140016d8d  mov     rbx, [r11+28h]
0x140016d91  mov     rsi, [r11+30h]
0x140016d95  mov     rsp, r11
0x140016d98  pop     r14
0x140016d9a  pop     rdi
0x140016d9b  pop     rbp
0x140016d9c  retn
0x140016d9d  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
