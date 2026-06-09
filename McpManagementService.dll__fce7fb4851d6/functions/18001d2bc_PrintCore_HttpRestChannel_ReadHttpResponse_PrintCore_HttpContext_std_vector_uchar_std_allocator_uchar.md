# PrintCore::HttpRestChannel::_ReadHttpResponse(PrintCore::HttpContext,std::vector<uchar,std::allocator<uchar>> &)

- ea: `0x18001d2bc`
- end: `0x18001d60c`
- name: `?_ReadHttpResponse@HttpRestChannel@PrintCore@@AEAAJUHttpContext@2@AEAV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `848`
- prototype: `__int64 __fastcall(DWORD *, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `17`
- tags: ``

## callers

- `0x18001d7dc`

## callees

- `0x180003a60`
- `0x1800045d8`
- `0x180006b70`
- `0x18000e164`
- `0x18000e208`
- `0x18000f804`
- `0x1800114cc`
- `0x180011de0`
- `0x1800129c4`
- `0x180012bc0`
- `0x18001b060`
- `0x18001c0f4`
- `0x18001c2e4`
- `0x18001cca8`
- `0x18001d28c`
- `0x18001d2bc`
- `0x18001db44`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18001d43f`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18001d43f`
- `WINHTTP!WinHttpReceiveResponse` at `0x18001d2fe`
- `WINHTTP!WinHttpReceiveResponse` at `0x18001d2fe`
- `WINHTTP!WinHttpReadData` at `0x18001d386`
- `WINHTTP!WinHttpReadData` at `0x18001d386`

## string_xrefs

- `0x18001d49b`: `PrintCore::HttpRestChannel::_ReadHttpResponse`
- `0x18001d582`: `PrintCore::HttpRestChannel::_ReadHttpResponse`
- `0x18001d5cd`: `PrintCore::HttpRestChannel::_ReadHttpResponse`
- `0x18001d5bd`: `Error reading HTTP response body: 0x%x, HttpRequestId: %d`

## pseudocode

```c
__int64 __fastcall PrintCore::HttpRestChannel::_ReadHttpResponse(DWORD *a1, __int64 a2, __int64 *a3)
{
  __int64 v4; // rdi
  unsigned int Error; // eax
  const unsigned __int16 *v7; // rdx
  unsigned __int64 v8; // rsi
  __int64 v9; // rcx
  __int64 v10; // r14
  __int64 v11; // r15
  unsigned __int64 v12; // rdx
  unsigned __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rdx
  __int64 v16; // r14
  unsigned __int64 v17; // rcx
  __int64 v18; // rax
  size_t v19; // rsi
  __int64 v20; // rcx
  __int64 v21; // rax
  int v22; // eax
  unsigned int v23; // esi
  unsigned int v24; // r14d
  char v25; // al
  int v26; // edx
  _QWORD *v27; // r9
  __int64 v28; // rcx
  __int64 Header; // rax
  const char *v30; // r9
  unsigned int v32; // ebx
  __int64 v33; // [rsp+20h] [rbp-F8h]
  DWORD dwNumberOfBytesRead; // [rsp+40h] [rbp-D8h] BYREF
  unsigned int v35; // [rsp+44h] [rbp-D4h]
  int v36; // [rsp+48h] [rbp-D0h]
  DWORD *v37; // [rsp+50h] [rbp-C8h]
  __int64 v38; // [rsp+58h] [rbp-C0h]
  _QWORD v39[4]; // [rsp+60h] [rbp-B8h] BYREF
  _BYTE v40[32]; // [rsp+80h] [rbp-98h] BYREF
  _BYTE v41[32]; // [rsp+A0h] [rbp-78h] BYREF
  _BYTE v42[32]; // [rsp+C0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  v4 = a2;
  v37 = a1;
  v38 = a2;
  if ( !WinHttpReceiveResponse(**(HINTERNET **)(a2 + 32), 0) )
  {
    Error = ResultFromKnownLastError();
    v7 = L"Error receiving HTTP response: 0x%x, HttpRequestId: %d";
LABEL_28:
    v32 = Error;
    HttpRestTelemetry::WriteDbgTraceWarning(
      "PrintCore::HttpRestChannel::_ReadHttpResponse",
      v7,
      Error,
      *(unsigned int *)(v4 + 80));
    PrintCore::HttpContext::~HttpContext((PrintCore::HttpContext *)v4);
    return v32;
  }
  LODWORD(v8) = 0;
  dwNumberOfBytesRead = 0;
  do
  {
    v9 = *a3;
    v10 = a3[1];
    v11 = *a1;
    v12 = v10 + v11 - *a3;
    v13 = v10 - *a3;
    if ( v12 >= v13 )
    {
      if ( v12 <= v13 )
        goto LABEL_11;
      if ( v12 > a3[2] - v9 )
      {
        std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(a3);
        goto LABEL_11;
      }
      memset_0((void *)a3[1], 0, *a1);
      v14 = v11 + v10;
    }
    else
    {
      v14 = v12 + v9;
    }
    a3[1] = v14;
LABEL_11:
    if ( !WinHttpReadData(**(HINTERNET **)(v4 + 32), (LPVOID)(*a3 + (unsigned int)v8), *a1, &dwNumberOfBytesRead) )
    {
      Error = ResultFromKnownLastError();
      v7 = L"Error reading HTTP response body: 0x%x, HttpRequestId: %d";
      goto LABEL_28;
    }
    v8 = dwNumberOfBytesRead + (unsigned int)v8;
  }
  while ( dwNumberOfBytesRead );
  v15 = *a3;
  v16 = a3[1];
  v17 = v16 - *a3;
  if ( v8 < v17 )
  {
    v18 = v15 + v8;
    goto LABEL_19;
  }
  if ( v8 > v17 )
  {
    if ( v8 <= a3[2] - v15 )
    {
      v19 = v8 - v17;
      memset_0((void *)a3[1], 0, v19);
      v18 = v19 + v16;
LABEL_19:
      a3[1] = v18;
    }
    else
    {
      std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(a3);
    }
  }
  std::wstring::wstring((__int64)v40, (__int64)&dword_18002DF04);
  PrintCore::HttpRestChannel::_GetHeader(v20, v42, v4, 19, v40);
  std::wstring::_Tidy_deallocate(v40);
  v21 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  v22 = _o__wtoi(v21);
  v23 = v22;
  v36 = v22;
  if ( v22 < 200 || (v24 = 0, v35 = 0, v22 >= 300) )
  {
    std::string::string(v39, *a3, a3[1]);
    v25 = std::_String_val<std::_Simple_types<char>>::_Large_mode_engaged(v39, *(unsigned int *)(v4 + 80));
    v27 = v39;
    if ( v25 )
      v27 = (_QWORD *)v39[0];
    LODWORD(v33) = v26;
    HttpRestTelemetry::WriteDbgTraceWarning(
      "PrintCore::HttpRestChannel::_ReadHttpResponse",
      L"Error: server returned http status code %d and response: %S, HttpRequestId: %d",
      v23,
      v27,
      v33);
    v24 = v23 | 0x80190000;
    v35 = v23 | 0x80190000;
    std::string::_Tidy_deallocate(v39);
  }
  std::wstring::wstring((__int64)v41);
  try
  {
    std::wstring::wstring((__int64)v40, (__int64)L"X-MSEdge-Ref");
    Header = PrintCore::HttpRestChannel::_GetHeader(v28, v39, v4, 0xFFFF, v40);
    std::wstring::operator=(v41, Header);
    std::wstring::_Tidy_deallocate(v39);
    std::wstring::_Tidy_deallocate(v40);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x1BC,
      (unsigned int)"onecoreuap\\internal\\printscan\\inc\\HttpRestChannel.hxx",
      v30);
    v24 = v35;
    v23 = v36;
    v4 = v38;
  }
  std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  HttpRestTelemetry::WriteDbgTraceInfo(
    "PrintCore::HttpRestChannel::_ReadHttpResponse",
    L"HTTPStatusCode: %d, Request: %s %s, HttpRequestId: %d, Response TraceId: %s",
    v23);
  std::wstring::_Tidy_deallocate(v41);
  std::wstring::_Tidy_deallocate(v42);
  PrintCore::HttpContext::~HttpContext((PrintCore::HttpContext *)v4);
  return v24;
}

```

## disassembly

```asm
0x18001d2bc  mov     [rsp+arg_18], rbx
0x18001d2c1  push    rsi
0x18001d2c2  push    rdi
0x18001d2c3  push    r12
0x18001d2c5  push    r14
0x18001d2c7  push    r15
0x18001d2c9  sub     rsp, 0F0h
0x18001d2d0  mov     rax, cs:__security_cookie
0x18001d2d7  xor     rax, rsp
0x18001d2da  mov     [rsp+118h+var_38], rax
0x18001d2e2  mov     rbx, r8
0x18001d2e5  mov     rdi, rdx
0x18001d2e8  mov     r12, rcx
0x18001d2eb  mov     [rsp+118h+var_C8], rcx
0x18001d2f0  mov     [rsp+118h+var_C0], rdx
0x18001d2f5  mov     rcx, [rdx+20h]
0x18001d2f9  xor     edx, edx; lpReserved
0x18001d2fb  mov     rcx, [rcx]; hRequest
0x18001d2fe  call    cs:__imp_WinHttpReceiveResponse
0x18001d304  test    eax, eax
0x18001d306  jnz     short loc_18001D319
0x18001d308  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18001d30d  lea     rdx, aErrorReceiving; "Error receiving HTTP response: 0x%x, Ht"...
0x18001d314  jmp     loc_18001D5C4
0x18001d319  xor     esi, esi
0x18001d31b  mov     [rsp+118h+dwNumberOfBytesRead], esi
0x18001d31f  mov     rcx, [rbx]
0x18001d322  mov     r14, [rbx+8]
0x18001d326  mov     r15d, [r12]
0x18001d32a  mov     edx, r15d
0x18001d32d  sub     rdx, rcx
0x18001d330  add     rdx, r14
0x18001d333  mov     rax, r14
0x18001d336  sub     rax, rcx
0x18001d339  cmp     rdx, rax
0x18001d33c  jnb     short loc_18001D344
0x18001d33e  lea     rax, [rdx+rcx]
0x18001d342  jmp     short loc_18001D36D
0x18001d344  jbe     short loc_18001D371
0x18001d346  mov     rax, [rbx+10h]
0x18001d34a  sub     rax, rcx
0x18001d34d  cmp     rdx, rax
0x18001d350  jbe     short loc_18001D35C
0x18001d352  mov     rcx, rbx
0x18001d355  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18001d35a  jmp     short loc_18001D371
0x18001d35c  mov     r8, r15; Size
0x18001d35f  xor     edx, edx; Val
0x18001d361  mov     rcx, r14; void *
0x18001d364  call    memset_0
0x18001d369  lea     rax, [r15+r14]
0x18001d36d  mov     [rbx+8], rax
0x18001d371  mov     edx, esi
0x18001d373  add     rdx, [rbx]; lpBuffer
0x18001d376  mov     rcx, [rdi+20h]
0x18001d37a  lea     r9, [rsp+118h+dwNumberOfBytesRead]; lpdwNumberOfBytesRead
0x18001d37f  mov     r8d, [r12]; dwNumberOfBytesToRead
0x18001d383  mov     rcx, [rcx]; hRequest
0x18001d386  call    cs:__imp_WinHttpReadData
0x18001d38c  test    eax, eax
0x18001d38e  jz      loc_18001D5B8
0x18001d394  mov     eax, [rsp+118h+dwNumberOfBytesRead]
0x18001d398  add     esi, eax
0x18001d39a  test    eax, eax
0x18001d39c  jnz     short loc_18001D31F
0x18001d39e  mov     rdx, [rbx]
0x18001d3a1  mov     r14, [rbx+8]
0x18001d3a5  mov     rcx, r14
0x18001d3a8  sub     rcx, rdx
0x18001d3ab  cmp     rsi, rcx
0x18001d3ae  jnb     short loc_18001D3B6
0x18001d3b0  lea     rax, [rdx+rsi]
0x18001d3b4  jmp     short loc_18001D3E5
0x18001d3b6  jbe     short loc_18001D3E9
0x18001d3b8  mov     rax, [rbx+10h]
0x18001d3bc  sub     rax, rdx
0x18001d3bf  cmp     rsi, rax
0x18001d3c2  jbe     short loc_18001D3D1
0x18001d3c4  mov     rdx, rsi
0x18001d3c7  mov     rcx, rbx
0x18001d3ca  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18001d3cf  jmp     short loc_18001D3E9
0x18001d3d1  sub     rsi, rcx
0x18001d3d4  mov     r8, rsi; Size
0x18001d3d7  xor     edx, edx; Val
0x18001d3d9  mov     rcx, r14; void *
0x18001d3dc  call    memset_0
0x18001d3e1  lea     rax, [rsi+r14]
0x18001d3e5  mov     [rbx+8], rax
0x18001d3e9  lea     rdx, dword_18002DF04
0x18001d3f0  lea     rcx, [rsp+118h+var_98]
0x18001d3f8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001d3fd  nop
0x18001d3fe  lea     rax, [rsp+118h+var_98]
0x18001d406  mov     [rsp+118h+var_F8], rax
0x18001d40b  mov     r9d, 13h
0x18001d411  mov     r8, rdi
0x18001d414  lea     rdx, [rsp+118h+var_58]
0x18001d41c  call    ?_GetHeader@HttpRestChannel@PrintCore@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBUHttpContext@2@KAEBV34@@Z; PrintCore::HttpRestChannel::_GetHeader(PrintCore::HttpContext const &,ulong,std::wstring const &)
0x18001d421  nop
0x18001d422  lea     rcx, [rsp+118h+var_98]
0x18001d42a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d42f  lea     rcx, [rsp+118h+var_58]
0x18001d437  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001d43c  mov     rcx, rax
0x18001d43f  call    cs:__imp__o__wtoi
0x18001d445  mov     esi, eax
0x18001d447  mov     [rsp+118h+var_D0], eax
0x18001d44b  cmp     eax, 0C8h
0x18001d450  jl      short loc_18001D461
0x18001d452  xor     r14d, r14d
0x18001d455  mov     [rsp+118h+var_D4], r14d
0x18001d45a  cmp     eax, 12Ch
0x18001d45f  jl      short loc_18001D4C0
0x18001d461  mov     r8, [rbx+8]
0x18001d465  mov     rdx, [rbx]
0x18001d468  lea     rcx, [rsp+118h+var_B8]
0x18001d46d  call    ??$?0V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@std@@$0A@@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@0AEBV?$allocator@D@1@@Z; std::string::string(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,std::allocator<char> const &)
0x18001d472  nop
0x18001d473  mov     edx, [rdi+50h]
0x18001d476  lea     rcx, [rsp+118h+var_B8]
0x18001d47b  call    ?_Large_mode_engaged@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBA_NXZ; std::_String_val<std::_Simple_types<char>>::_Large_mode_engaged(void)
0x18001d480  lea     r9, [rsp+118h+var_B8]
0x18001d485  test    al, al
0x18001d487  cmovnz  r9, [rsp+118h+var_B8]
0x18001d48d  mov     dword ptr [rsp+118h+var_F8], edx
0x18001d491  mov     r8d, esi
0x18001d494  lea     rdx, aErrorServerRet; "Error: server returned http status code"...
0x18001d49b  lea     rcx, aPrintcoreHttpr_0; "PrintCore::HttpRestChannel::_ReadHttpRe"...
0x18001d4a2  call    ?WriteDbgTraceWarning@HttpRestTelemetry@@SAXPEBDPEBGZZ; HttpRestTelemetry::WriteDbgTraceWarning(char const *,ushort const *,...)
0x18001d4a7  mov     r14d, esi
0x18001d4aa  or      r14d, 80190000h
0x18001d4b1  mov     [rsp+118h+var_D4], r14d
0x18001d4b6  lea     rcx, [rsp+118h+var_B8]
0x18001d4bb  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18001d4c0  lea     rcx, [rsp+118h+var_78]
0x18001d4c8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001d4cd  nop
0x18001d4ce  lea     rdx, aXMsedgeRef; "X-MSEdge-Ref"
0x18001d4d5  lea     rcx, [rsp+118h+var_98]
0x18001d4dd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001d4e2  nop
0x18001d4e3  lea     rax, [rsp+118h+var_98]
0x18001d4eb  mov     [rsp+118h+var_F8], rax
0x18001d4f0  mov     r9d, 0FFFFh
0x18001d4f6  mov     r8, rdi
0x18001d4f9  lea     rdx, [rsp+118h+var_B8]
0x18001d4fe  call    ?_GetHeader@HttpRestChannel@PrintCore@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBUHttpContext@2@KAEBV34@@Z; PrintCore::HttpRestChannel::_GetHeader(PrintCore::HttpContext const &,ulong,std::wstring const &)
0x18001d503  mov     rdx, rax
0x18001d506  lea     rcx, [rsp+118h+var_78]
0x18001d50e  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001d513  lea     rcx, [rsp+118h+var_B8]
0x18001d518  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d51d  nop
0x18001d51e  lea     rcx, [rsp+118h+var_98]
0x18001d526  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d52b  nop
0x18001d52c  jmp     short loc_18001D541
0x18001d52e  mov     r14d, [rsp+118h+var_D4]
0x18001d533  mov     esi, [rsp+118h+var_D0]
0x18001d537  mov     rdi, [rsp+118h+var_C0]
0x18001d53c  mov     r12, [rsp+118h+var_C8]
0x18001d541  lea     rcx, [rdi+30h]
0x18001d545  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001d54a  mov     rdx, rax
0x18001d54d  lea     rcx, [r12+8]
0x18001d552  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001d557  mov     r9, rax
0x18001d55a  lea     rcx, [rsp+118h+var_78]
0x18001d562  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001d567  mov     [rsp+118h+var_E8], rax
0x18001d56c  mov     ecx, [rdi+50h]
0x18001d56f  mov     [rsp+118h+var_F0], ecx
0x18001d573  mov     [rsp+118h+var_F8], rdx
0x18001d578  mov     r8d, esi
0x18001d57b  lea     rdx, aHttpstatuscode; "HTTPStatusCode: %d, Request: %s %s, Htt"...
0x18001d582  lea     rcx, aPrintcoreHttpr_0; "PrintCore::HttpRestChannel::_ReadHttpRe"...
0x18001d589  call    ?WriteDbgTraceInfo@HttpRestTelemetry@@SAXPEBDPEBGZZ; HttpRestTelemetry::WriteDbgTraceInfo(char const *,ushort const *,...)
0x18001d58e  nop
0x18001d58f  lea     rcx, [rsp+118h+var_78]
0x18001d597  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d59c  nop
0x18001d59d  lea     rcx, [rsp+118h+var_58]
0x18001d5a5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d5aa  nop
0x18001d5ab  mov     rcx, rdi; this
0x18001d5ae  call    ??1HttpContext@PrintCore@@QEAA@XZ; PrintCore::HttpContext::~HttpContext(void)
0x18001d5b3  mov     eax, r14d
0x18001d5b6  jmp     short loc_18001D5E4
0x18001d5b8  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18001d5bd  lea     rdx, aErrorReadingHt; "Error reading HTTP response body: 0x%x,"...
0x18001d5c4  mov     ebx, eax
0x18001d5c6  mov     r9d, [rdi+50h]
0x18001d5ca  mov     r8d, eax
0x18001d5cd  lea     rcx, aPrintcoreHttpr_0; "PrintCore::HttpRestChannel::_ReadHttpRe"...
0x18001d5d4  call    ?WriteDbgTraceWarning@HttpRestTelemetry@@SAXPEBDPEBGZZ; HttpRestTelemetry::WriteDbgTraceWarning(char const *,ushort const *,...)
0x18001d5d9  nop
0x18001d5da  mov     rcx, rdi; this
0x18001d5dd  call    ??1HttpContext@PrintCore@@QEAA@XZ; PrintCore::HttpContext::~HttpContext(void)
0x18001d5e2  mov     eax, ebx
0x18001d5e4  mov     rcx, [rsp+118h+var_38]
0x18001d5ec  xor     rcx, rsp; StackCookie
0x18001d5ef  call    __security_check_cookie
0x18001d5f4  mov     rbx, [rsp+118h+arg_18]
0x18001d5fc  add     rsp, 0F0h
0x18001d603  pop     r15
0x18001d605  pop     r14
0x18001d607  pop     r12
0x18001d609  pop     rdi
0x18001d60a  pop     rsi
0x18001d60b  retn
```
