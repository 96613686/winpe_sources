# web::http::client::details::winhttp_client::open(void)

- ea: `0x1800388a0`
- end: `0x180038b96`
- name: `?open@winhttp_client@details@client@http@web@@MEAAKXZ`
- size: `758`
- prototype: `unsigned int __fastcall(web::http::client::details::winhttp_client *__hidden this)`
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002c2c`
- `0x180002c6c`
- `0x180002ca8`
- `0x180004fa0`
- `0x180009778`
- `0x18000a228`
- `0x18000a2f4`
- `0x18000e5a8`
- `0x1800167f8`
- `0x1800177f8`
- `0x18001a384`
- `0x18001adbc`
- `0x18001b200`
- `0x18001e604`
- `0x180024884`
- `0x180033174`
- `0x180034384`
- `0x180038864`
- `0x1800388a0`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z` at `0x1800389b2`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z` at `0x1800389b2`
- `msvcp_win!?classic@locale@std@@SAAEBV12@XZ` at `0x18003896a`
- `msvcp_win!?classic@locale@std@@SAAEBV12@XZ` at `0x18003896a`
- `msvcp_win!?imbue@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAA?AVlocale@2@AEBV32@@Z` at `0x18003897a`
- `msvcp_win!?imbue@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAA?AVlocale@2@AEBV32@@Z` at `0x18003897a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038a73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038ac5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038a73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038ac5`
- `WINHTTP!WinHttpSetTimeouts` at `0x180038a59`
- `WINHTTP!WinHttpSetTimeouts` at `0x180038a59`
- `WINHTTP!WinHttpOpen` at `0x180038a1a`
- `WINHTTP!WinHttpOpen` at `0x180038a1a`
- `WINHTTP!WinHttpSetStatusCallback` at `0x180038ae8`
- `WINHTTP!WinHttpSetStatusCallback` at `0x180038ae8`
- `WINHTTP!WinHttpSetOption` at `0x180038aab`
- `WINHTTP!WinHttpSetOption` at `0x180038aab`
- `WINHTTP!WinHttpConnect` at `0x180038b3f`
- `WINHTTP!WinHttpConnect` at `0x180038b3f`

## string_xrefs

- `0x180038a2c`: `Error opening session`
- `0x180038b51`: `Error opening connection`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall web::http::client::details::winhttp_client::open(web::http::client::details::winhttp_client *this)
{
  unsigned int v2; // eax
  DWORD v3; // r14d
  _BYTE *v4; // rcx
  const WCHAR *v5; // rax
  char *v6; // rbx
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  HINTERNET v10; // rax
  const wchar_t *v11; // rdx
  int v12; // edx
  DWORD LastError; // eax
  _BYTE *v14; // rcx
  DWORD v15; // ebx
  const wchar_t *v16; // rdx
  const WCHAR *v17; // rax
  INTERNET_PORT v18; // r8
  HINTERNET v19; // rax
  __int64 v21; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v22[232]; // [rsp+38h] [rbp-C8h] BYREF
  _DWORD Buffer[8]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v24[32]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v25[32]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v26[64]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v27[160]; // [rsp+1C0h] [rbp+C0h] BYREF
  int v28; // [rsp+260h] [rbp+160h]

  std::wstring::wstring(v25);
  web::uri::uri((web::uri *)v26);
  v2 = *((_DWORD *)this + 126);
  if ( v2 == 2 )
  {
    v3 = 1;
LABEL_12:
    v5 = 0;
    goto LABEL_13;
  }
  if ( v2 <= 1 )
  {
    v3 = 0;
    goto LABEL_12;
  }
  v3 = 3;
  web::uri::operator=(v26);
  if ( web::uri::is_port_default((web::uri *)v26) )
  {
    v4 = v27;
  }
  else
  {
    if ( v28 <= 0 )
    {
      std::wstring::operator=(v25, v27);
    }
    else
    {
      std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>(&v21);
      v6 = &v22[*(int *)(v21 + 4) - 8];
      v7 = std::locale::classic();
      std::basic_ios<unsigned short>::imbue(v6, Buffer, v7);
      std::locale::~locale((std::locale *)Buffer);
      v8 = std::operator<<<unsigned short>(&v21, v27);
      v9 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v8, L":");
      std::basic_ostream<unsigned short>::operator<<(v9, (unsigned int)v28);
      std::basic_stringbuf<unsigned short>::str(v22, Buffer);
      std::wstring::operator=(v25, Buffer);
      std::wstring::_Tidy_deallocate(Buffer);
      std::basic_ostringstream<unsigned short>::`vbase destructor'(&v21);
    }
    v4 = v25;
  }
  v5 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v4);
LABEL_13:
  v10 = WinHttpOpen(0, v3, v5, 0, 0x10000000u);
  *((_QWORD *)this + 108) = v10;
  if ( !v10 )
  {
    v11 = L"Error opening session";
LABEL_19:
    std::wstring::wstring(Buffer, v11);
    LastError = GetLastError();
    v14 = Buffer;
    goto LABEL_20;
  }
  v12 = *(_DWORD *)web::http::client::http_client_config::timeout<std::chrono::duration<__int64,std::ratio<1,1000>>>(
                     (char *)this + 240,
                     Buffer);
  if ( v12 < 1 )
    v12 = 1;
  if ( !WinHttpSetTimeouts(*((HINTERNET *)this + 108), v12, v12, v12, v12) )
  {
    v11 = L"Error setting timeouts";
    goto LABEL_19;
  }
  if ( !*((_BYTE *)this + 640) || (Buffer[0] = 1, WinHttpSetOption(*((HINTERNET *)this + 108), 0x49u, Buffer, 4u)) )
  {
    if ( WinHttpSetStatusCallback(
           *((HINTERNET *)this + 108),
           (WINHTTP_STATUS_CALLBACK)web::http::client::details::winhttp_client::completion_callback,
           0x97E0C00u,
           0) == (WINHTTP_STATUS_CALLBACK)-1LL )
    {
      v16 = L"Error registering callback";
    }
    else
    {
      web::uri::is_port_default((web::http::client::details::winhttp_client *)((char *)this + 8));
      v17 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 72);
      v19 = WinHttpConnect(*((HINTERNET *)this + 108), v17, v18, 0);
      *((_QWORD *)this + 109) = v19;
      if ( v19 )
      {
        v15 = 0;
        goto LABEL_30;
      }
      v16 = L"Error opening connection";
    }
  }
  else
  {
    v16 = L"Error setting options";
  }
  std::wstring::wstring(v24, v16);
  LastError = GetLastError();
  v14 = v24;
LABEL_20:
  v15 = LastError;
  std::wstring::_Tidy_deallocate(v14);
LABEL_30:
  web::uri::~uri((web::uri *)v26);
  std::wstring::_Tidy_deallocate(v25);
  return v15;
}

```

## disassembly

```asm
0x1800388a0  push    rbp
0x1800388a2  push    rbx
0x1800388a3  push    rsi
0x1800388a4  push    rdi
0x1800388a5  push    r14
0x1800388a7  push    r15
0x1800388a9  lea     rbp, [rsp-188h]
0x1800388b1  sub     rsp, 288h
0x1800388b8  mov     rax, cs:__security_cookie
0x1800388bf  xor     rax, rsp
0x1800388c2  mov     [rbp+1B0h+var_40], rax
0x1800388c9  mov     rdi, rcx
0x1800388cc  lea     rcx, [rbp+1B0h+var_150]
0x1800388d0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800388d5  nop
0x1800388d6  lea     rcx, [rbp+1B0h+var_130]; this
0x1800388dd  call    ??0uri@web@@QEAA@XZ; web::uri::uri(void)
0x1800388e2  nop
0x1800388e3  lea     r15, [rdi+0F0h]
0x1800388ea  lea     rdx, [r15+20h]
0x1800388ee  mov     eax, [rdx+0E8h]
0x1800388f4  mov     esi, 1
0x1800388f9  cmp     eax, 2
0x1800388fc  jnz     short loc_180038906
0x1800388fe  mov     r14d, esi
0x180038901  jmp     loc_180038A05
0x180038906  cmp     eax, esi
0x180038908  jbe     loc_180038A02
0x18003890e  mov     r14d, 3
0x180038914  lea     rcx, [rbp+1B0h+var_130]
0x18003891b  call    ??4uri@web@@QEAAAEAV01@AEBV01@@Z; web::uri::operator=(web::uri const &)
0x180038920  lea     rcx, [rbp+1B0h+var_130]; this
0x180038927  call    ?is_port_default@uri@web@@QEBA_NXZ; web::uri::is_port_default(void)
0x18003892c  test    al, al
0x18003892e  jz      short loc_180038941
0x180038930  lea     rcx, [rbp+1B0h+var_F0]
0x180038937  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003893c  jmp     loc_180038A07
0x180038941  cmp     [rbp+1B0h+var_50], 0
0x180038948  jle     loc_1800389E9
0x18003894e  lea     rcx, [rsp+2B0h+var_280]
0x180038953  call    ??0?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_ostringstream<ushort>::basic_ostringstream<ushort>(void)
0x180038958  nop
0x180038959  mov     rax, [rsp+2B0h+var_280]
0x18003895e  movsxd  rcx, dword ptr [rax+4]
0x180038962  lea     rbx, [rsp+2B0h+var_280]
0x180038967  add     rbx, rcx
0x18003896a  call    cs:__imp_?classic@locale@std@@SAAEBV12@XZ; std::locale::classic(void)
0x180038970  mov     r8, rax
0x180038973  lea     rdx, [rbp+1B0h+Buffer]
0x180038977  mov     rcx, rbx
0x18003897a  call    cs:__imp_?imbue@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAA?AVlocale@2@AEBV32@@Z; std::basic_ios<ushort>::imbue(std::locale const &)
0x180038980  lea     rcx, [rbp+1B0h+Buffer]; this
0x180038984  call    ??1locale@std@@QEAA@XZ; std::locale::~locale(void)
0x180038989  lea     rdx, [rbp+1B0h+var_F0]
0x180038990  lea     rcx, [rsp+2B0h+var_280]
0x180038995  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator<<<ushort>(std::basic_ostream<ushort> &,std::wstring const &)
0x18003899a  mov     rcx, rax
0x18003899d  lea     rdx, asc_180068AF0; ":"
0x1800389a4  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1800389a9  mov     edx, [rbp+1B0h+var_50]
0x1800389af  mov     rcx, rax
0x1800389b2  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z; std::basic_ostream<ushort>::operator<<(int)
0x1800389b8  lea     rdx, [rbp+1B0h+Buffer]
0x1800389bc  lea     rcx, [rsp+2B0h+var_278]
0x1800389c1  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x1800389c6  lea     rdx, [rbp+1B0h+Buffer]
0x1800389ca  lea     rcx, [rbp+1B0h+var_150]
0x1800389ce  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800389d3  lea     rcx, [rbp+1B0h+Buffer]
0x1800389d7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800389dc  nop
0x1800389dd  lea     rcx, [rsp+2B0h+var_280]
0x1800389e2  call    ??_D?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXXZ; std::basic_ostringstream<ushort>::`vbase destructor'(void)
0x1800389e7  jmp     short loc_1800389F9
0x1800389e9  lea     rdx, [rbp+1B0h+var_F0]
0x1800389f0  lea     rcx, [rbp+1B0h+var_150]
0x1800389f4  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800389f9  lea     rcx, [rbp+1B0h+var_150]
0x1800389fd  jmp     loc_180038937
0x180038a02  xor     r14d, r14d
0x180038a05  xor     eax, eax
0x180038a07  mov     [rsp+2B0h+dwFlags], 10000000h; dwFlags
0x180038a0f  xor     r9d, r9d; pszProxyBypassW
0x180038a12  mov     r8, rax; pszProxyW
0x180038a15  mov     edx, r14d; dwAccessType
0x180038a18  xor     ecx, ecx; pszAgentW
0x180038a1a  call    cs:__imp_WinHttpOpen
0x180038a20  mov     [rdi+360h], rax
0x180038a27  test    rax, rax
0x180038a2a  jnz     short loc_180038A35
0x180038a2c  lea     rdx, aErrorOpeningSe; "Error opening session"
0x180038a33  jmp     short loc_180038A6A
0x180038a35  lea     rdx, [rbp+1B0h+Buffer]
0x180038a39  mov     rcx, r15
0x180038a3c  call    ??$timeout@V?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@std@@@http_client_config@client@http@web@@QEBA?AV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@std@@XZ; web::http::client::http_client_config::timeout<std::chrono::duration<__int64,std::ratio<1,1000>>>(void)
0x180038a41  mov     edx, [rax]
0x180038a43  cmp     edx, esi
0x180038a45  cmovl   edx, esi; nResolveTimeout
0x180038a48  mov     [rsp+2B0h+dwFlags], edx; nReceiveTimeout
0x180038a4c  mov     r9d, edx; nSendTimeout
0x180038a4f  mov     r8d, edx; nConnectTimeout
0x180038a52  mov     rcx, [rdi+360h]; hInternet
0x180038a59  call    cs:__imp_WinHttpSetTimeouts
0x180038a5f  test    eax, eax
0x180038a61  jnz     short loc_180038A89
0x180038a63  lea     rdx, aErrorSettingTi; "Error setting timeouts"
0x180038a6a  lea     rcx, [rbp+1B0h+Buffer]
0x180038a6e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180038a73  call    cs:__imp_GetLastError
0x180038a79  lea     rcx, [rbp+1B0h+Buffer]
0x180038a7d  mov     ebx, eax
0x180038a7f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180038a84  jmp     loc_180038B5F
0x180038a89  cmp     byte ptr [r15+190h], 0
0x180038a91  jz      short loc_180038AD1
0x180038a93  mov     [rbp+1B0h+Buffer], esi
0x180038a96  mov     r9d, 4; dwBufferLength
0x180038a9c  lea     r8, [rbp+1B0h+Buffer]; lpBuffer
0x180038aa0  lea     edx, [r9+45h]; dwOption
0x180038aa4  mov     rcx, [rdi+360h]; hInternet
0x180038aab  call    cs:__imp_WinHttpSetOption
0x180038ab1  test    eax, eax
0x180038ab3  jnz     short loc_180038AD1
0x180038ab5  lea     rdx, aErrorSettingOp; "Error setting options"
0x180038abc  lea     rcx, [rbp+1B0h+var_170]
0x180038ac0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180038ac5  call    cs:__imp_GetLastError
0x180038acb  lea     rcx, [rbp+1B0h+var_170]
0x180038acf  jmp     short loc_180038A7D
0x180038ad1  xor     r9d, r9d; dwReserved
0x180038ad4  mov     r8d, 97E0C00h; dwNotificationFlags
0x180038ada  lea     rdx, ?completion_callback@winhttp_client@details@client@http@web@@CAXPEAX_KK0K@Z; lpfnInternetCallback
0x180038ae1  mov     rcx, [rdi+360h]; hInternet
0x180038ae8  call    cs:__imp_WinHttpSetStatusCallback
0x180038aee  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180038af2  jnz     short loc_180038AFD
0x180038af4  lea     rdx, aErrorRegisteri; "Error registering callback"
0x180038afb  jmp     short loc_180038ABC
0x180038afd  lea     rcx, [rdi+8]; this
0x180038b01  call    ?is_port_default@uri@web@@QEBA_NXZ; web::uri::is_port_default(void)
0x180038b06  test    al, al
0x180038b08  jz      short loc_180038B22
0x180038b0a  mov     al, [rdi+370h]
0x180038b10  neg     al
0x180038b12  sbb     r8d, r8d
0x180038b15  and     r8d, 16Bh
0x180038b1c  add     r8d, 50h ; 'P'
0x180038b20  jmp     short loc_180038B29
0x180038b22  mov     r8d, [rdi+0E8h]
0x180038b29  lea     rcx, [rdi+48h]
0x180038b2d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180038b32  xor     r9d, r9d; dwReserved
0x180038b35  mov     rdx, rax; pswzServerName
0x180038b38  mov     rcx, [rdi+360h]; hSession
0x180038b3f  call    cs:__imp_WinHttpConnect
0x180038b45  mov     [rdi+368h], rax
0x180038b4c  test    rax, rax
0x180038b4f  jnz     short loc_180038B5D
0x180038b51  lea     rdx, aErrorOpeningCo; "Error opening connection"
0x180038b58  jmp     loc_180038ABC
0x180038b5d  xor     ebx, ebx
0x180038b5f  lea     rcx, [rbp+1B0h+var_130]; this
0x180038b66  call    ??1uri@web@@QEAA@XZ; web::uri::~uri(void)
0x180038b6b  nop
0x180038b6c  lea     rcx, [rbp+1B0h+var_150]
0x180038b70  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180038b75  mov     eax, ebx
0x180038b77  mov     rcx, [rbp+1B0h+var_40]
0x180038b7e  xor     rcx, rsp; StackCookie
0x180038b81  call    __security_check_cookie
0x180038b86  add     rsp, 288h
0x180038b8d  pop     r15
0x180038b8f  pop     r14
0x180038b91  pop     rdi
0x180038b92  pop     rsi
0x180038b93  pop     rbx
0x180038b94  pop     rbp
0x180038b95  retn
```
