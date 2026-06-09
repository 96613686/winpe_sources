# PTIUtils::SendRequest(HttpRequest &,TraceLoggingCorrelationVector *,web::json::value *)

- ea: `0x1800374d4`
- end: `0x180037b0c`
- name: `?SendRequest@PTIUtils@@YAXAEAVHttpRequest@@PEAVTraceLoggingCorrelationVector@@PEAVvalue@json@web@@@Z`
- size: `1592`
- prototype: `void(PTIUtils *__hidden this, struct HttpRequest *, struct TraceLoggingCorrelationVector *, struct web::json::value *)`
- caller_count: `2`
- callee_count: `26`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180032ac0`
- `0x1800354bc`

## callees

- `0x1800026b0`
- `0x18000316c`
- `0x1800061f0`
- `0x180007860`
- `0x18000c1f0`
- `0x18002008c`
- `0x18002c4b8`
- `0x18002d674`
- `0x18002f028`
- `0x18002fbb4`
- `0x180030a68`
- `0x180030aac`
- `0x18003159c`
- `0x180031ac0`
- `0x180034d14`
- `0x1800354a0`
- `0x1800367e4`
- `0x1800374d4`
- `0x180037ba8`
- `0x180037d04`
- `0x180046020`
- `0x180046eac`
- `0x1800471d8`
- `0x1800484d0`
- `0x180048cc0`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037af1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037af1`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180037951`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180037951`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800376ab`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180037725`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800376ab`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180037725`
- `WINHTTP!WinHttpReadData` at `0x1800377c3`
- `WINHTTP!WinHttpReadData` at `0x1800377c3`

## string_xrefs

- `0x1800379c8`: `onecoreuap\enduser\winstore\pushtoinstall\lib\ptiutils.cpp`
- `0x180037acd`: `onecoreuap\enduser\winstore\pushtoinstall\lib\ptiutils.cpp`
- `0x180037adf`: `onecoreuap\enduser\winstore\servicescommon\lib\httpforservices.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall PTIUtils::SendRequest(
        PTIUtils *this,
        struct HttpRequest *a2,
        struct TraceLoggingCorrelationVector *a3,
        struct web::json::value *a4)
{
  __int64 v7; // r8
  char **v8; // rbx
  char **v9; // rax
  char **v10; // rdi
  DWORD TickCount; // edi
  char *v12; // rbx
  char *v13; // rdx
  unsigned __int64 v14; // r8
  DWORD v15; // r14d
  int v16; // esi
  unsigned __int64 v17; // r8
  const char *v18; // r9
  __int64 v19; // r8
  char **v20; // rdi
  char **v21; // rdx
  const char *v22; // rdx
  const wchar_t *v23; // rax
  __int64 *v24; // rax
  signed int LastError; // eax
  int v26; // edx
  unsigned int v27; // r8d
  __int64 v28; // rax
  const char *v29; // rax
  unsigned __int8 v30; // [rsp+30h] [rbp-A58h]
  int v31; // [rsp+20h] [rbp-A68h]
  unsigned __int8 v32; // [rsp+30h] [rbp-A58h]
  __int64 v33; // [rsp+50h] [rbp-A38h] BYREF
  DWORD dwNumberOfBytesRead; // [rsp+58h] [rbp-A30h] BYREF
  int v35; // [rsp+5Ch] [rbp-A2Ch]
  PTIUtils *v36; // [rsp+60h] [rbp-A28h]
  __int128 Src; // [rsp+70h] [rbp-A18h] BYREF
  __m128i v38; // [rsp+80h] [rbp-A08h]
  __int128 v39; // [rsp+90h] [rbp-9F8h] BYREF
  __int64 v40[2]; // [rsp+A0h] [rbp-9E8h]
  CHAR MultiByteStr[16]; // [rsp+B0h] [rbp-9D8h] BYREF
  __int128 v42; // [rsp+C0h] [rbp-9C8h]
  char *v43[2]; // [rsp+D0h] [rbp-9B8h] BYREF
  unsigned __int64 v44; // [rsp+E0h] [rbp-9A8h]
  unsigned __int64 v45; // [rsp+E8h] [rbp-9A0h]
  void **v46; // [rsp+F8h] [rbp-990h] BYREF
  HINTERNET hRequest; // [rsp+100h] [rbp-988h]
  __int16 v48; // [rsp+120h] [rbp-968h] BYREF
  char v49; // [rsp+122h] [rbp-966h]
  __int64 v50; // [rsp+128h] [rbp-960h] BYREF
  __int128 v51; // [rsp+130h] [rbp-958h]
  __int128 v52; // [rsp+140h] [rbp-948h] BYREF
  __m128i si128; // [rsp+150h] [rbp-938h]
  _OWORD v54[2]; // [rsp+160h] [rbp-928h] BYREF
  char *v55[4]; // [rsp+180h] [rbp-908h] BYREF
  char Destination[144]; // [rsp+1A0h] [rbp-8E8h] BYREF
  _BYTE Buffer[2064]; // [rsp+230h] [rbp-858h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A88h] [rbp+0h]

  v36 = this;
  v48 = 0;
  v49 = 0;
  v50 = 0;
  v51 = 0;
  v52 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v52) = 0;
  v54[0] = 0;
  v54[1] = si128;
  LOWORD(v54[0]) = 0;
  ProxySettings::Capture((__int64)&v48, (__int64)this + 128);
  LODWORD(v33) = 0;
  TraceLoggingCorrelationVector::Increment(a2, Destination);
  v39 = 0;
  v40[0] = 0;
  v40[1] = 7;
  LOWORD(v39) = 0;
  v35 = 0;
  *(_OWORD *)MultiByteStr = 0;
  v42 = 0;
  v7 = -1;
  do
    ++v7;
  while ( Destination[v7] );
  try
  {
    std::string::_Construct<1,char const *>(MultiByteStr, Destination);
    v8 = (char **)ConvertToWide(v55, MultiByteStr, 0);
    Src = 0;
    v38 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&Src, L"MS-CV", 5u);
    v9 = (char **)std::map<std::wstring,std::wstring>::operator[]((char *)this + 248, &Src);
    v10 = v9;
    if ( v9 != v8 )
    {
      std::wstring::_Tidy_deallocate(v9);
      *(_OWORD *)v10 = *(_OWORD *)v8;
      *((_OWORD *)v10 + 1) = *((_OWORD *)v8 + 1);
      v8[2] = 0;
      v8[3] = (char *)7;
      *(_WORD *)v8 = 0;
    }
    std::wstring::_Tidy_deallocate((char **)&Src);
    std::wstring::_Tidy_deallocate(v55);
    std::string::_Tidy_deallocate(MultiByteStr);
    TickCount = GetTickCount();
    v12 = (char *)this + 32;
    if ( *((_QWORD *)this + 7) <= 7u )
      v13 = (char *)this + 32;
    else
      v13 = *(char **)v12;
    *(_OWORD *)MultiByteStr = 0;
    v42 = 0;
    v14 = -1;
    do
      ++v14;
    while ( *(_WORD *)&v13[2 * v14] );
    std::wstring::_Construct<1,unsigned short const *>(MultiByteStr, v13, v14);
    SendRequestAndWaitForResponse((__int64)v43, (__int64)MultiByteStr, (char *)&v48, (WCHAR *)this);
    std::wstring::_Tidy_deallocate((char **)MultiByteStr);
    v15 = GetTickCount() - TickCount;
    LODWORD(v33) = v15;
    v16 = HttpResponse::StatusCode((HttpResponse *)v43);
    v35 = v16;
    if ( (unsigned int)(v16 - 200) > 0x63 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x56,
        (int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\ptiutils.cpp",
        (const char *)(v16 | 0x80190000),
        v31);
    v17 = v44;
    if ( !v44 )
    {
      Src = 0;
      v38 = _mm_load_si128((const __m128i *)&_xmm);
      LOBYTE(Src) = 0;
      dwNumberOfBytesRead = 0;
      do
      {
        memset_0(Buffer, 0, 0x801u);
        if ( !WinHttpReadData(hRequest, Buffer, 0x800u, &dwNumberOfBytesRead) )
          wil::details::in1diag3::_Throw_GetLastError(
            retaddr,
            (void *)0x430,
            (int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\httpforservices.cpp",
            v18);
        v19 = -1;
        do
          ++v19;
        while ( Buffer[v19] );
        std::string::_Append<char>(&Src);
      }
      while ( dwNumberOfBytesRead );
      v20 = (char **)ConvertToWide(v55, (LPCCH)&Src, 0xFDE9u);
      if ( v43 != v20 )
      {
        std::wstring::_Tidy_deallocate(v43);
        v43[0] = *v20;
        v43[1] = v20[1];
        v44 = (unsigned __int64)v20[2];
        v45 = (unsigned __int64)v20[3];
        v20[2] = 0;
        v20[3] = (char *)7;
        *(_WORD *)v20 = 0;
      }
      std::wstring::_Tidy_deallocate(v55);
      std::string::_Tidy_deallocate(&Src);
      v17 = v44;
    }
    Src = 0;
    v38 = 0;
    v21 = v43;
    if ( v45 > 7 )
      v21 = (char **)v43[0];
    std::wstring::_Construct<2,unsigned short const *>((__int64)&Src, v21, v17);
    std::wstring::_Tidy_deallocate((char **)&v39);
    v39 = Src;
    *(__m128i *)v40 = v38;
    v38 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(Src) = 0;
    std::wstring::_Tidy_deallocate((char **)&Src);
    if ( *((_QWORD *)v12 + 3) <= 7u )
      v22 = v12;
    else
      v22 = *(const char **)v12;
    Windows::PushToInstall::TraceOutgoingServiceRequest(
      (Windows::PushToInstall *)Destination,
      v22,
      (const unsigned __int16 *)v15,
      v16,
      v40[0],
      1,
      v32);
    if ( IsDebuggerPresent() )
    {
      if ( v40[0] )
      {
        v23 = (const wchar_t *)&v39;
        if ( v40[1] > 7uLL )
          v23 = (const wchar_t *)v39;
      }
      else
      {
        v23 = L"<empty>";
      }
      if ( *((_QWORD *)v12 + 3) > 7u )
        v12 = *(char **)v12;
      LogMessage(
        4u,
        "onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\ptiutils.cpp",
        0x5Du,
        "PTIUtils::SendRequest",
        -1,
        L"[%hs] %s Response: %s",
        Destination,
        v12,
        v23);
    }
    v46 = &Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::`vftable';
    if ( hRequest )
    {
      if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::InternalClose(&v46) )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v26, v27);
        JUMPOUT(0x180037B0ALL);
      }
      hRequest = 0;
    }
    std::wstring::_Tidy_deallocate(v43);
  }
  catch ( ... )
  {
    v28 = HttpRequest::Uri(v36);
    v29 = (const char *)std::wstring::c_str(v28);
    Windows::PushToInstall::TraceOutgoingServiceRequest(
      (Windows::PushToInstall *)Destination,
      v29,
      (const unsigned __int16 *)(unsigned int)v33,
      v35,
      0,
      0,
      v30);
    throw;
  }
  if ( a3 )
  {
    if ( v40[0] )
      v24 = (__int64 *)web::json::value::parse(&v33, &v39);
    else
      v24 = (__int64 *)web::json::value::null(&v33);
    web::json::value::operator=((__int64 *)a3, v24);
    if ( v33 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v33 + 192LL))(v33, 1);
  }
  std::wstring::_Tidy_deallocate((char **)&v39);
  std::wstring::_Tidy_deallocate((char **)v54);
  std::wstring::_Tidy_deallocate((char **)&v52);
  std::vector<std::wstring>::_Tidy(&v50);
}

```

## disassembly

```asm
0x1800374d4  mov     r11, rsp
0x1800374d7  push    rbx
0x1800374d8  push    rsi
0x1800374d9  push    rdi
0x1800374da  push    r12
0x1800374dc  push    r13
0x1800374de  push    r14
0x1800374e0  push    r15
0x1800374e2  sub     rsp, 0A50h
0x1800374e9  mov     rax, cs:__security_cookie
0x1800374f0  xor     rax, rsp
0x1800374f3  mov     [rsp+0A88h+var_48], rax
0x1800374fb  mov     r15, r8
0x1800374fe  mov     rbx, rdx
0x180037501  mov     rsi, rcx
0x180037504  mov     [rsp+0A88h+var_A28], rcx
0x180037509  xor     r12d, r12d
0x18003750c  mov     [r11-968h], r12w
0x180037514  mov     [r11-966h], r12b
0x18003751b  mov     [r11-960h], r12
0x180037522  xorps   xmm0, xmm0
0x180037525  movdqa  [rsp+0A88h+var_958], xmm0
0x18003752e  xorps   xmm1, xmm1
0x180037531  movups  [rsp+0A88h+var_948], xmm1
0x180037539  movdqa  xmm2, cs:__xmm@00000000000000070000000000000000
0x180037541  movdqa  [rsp+0A88h+var_938], xmm2
0x18003754a  mov     [r11-948h], r12w
0x180037552  movups  [rsp+0A88h+var_928], xmm0
0x18003755a  movdqa  [rsp+0A88h+var_918], xmm2
0x180037563  mov     [r11-928h], r12w
0x18003756b  lea     rdx, [rcx+80h]
0x180037572  lea     rcx, [r11-968h]
0x180037579  call    ?Capture@ProxySettings@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ProxySettings::Capture(std::wstring const &)
0x18003757e  mov     dword ptr [rsp+0A88h+var_A38], r12d
0x180037583  lea     rdx, [rsp+0A88h+Destination]; Destination
0x18003758b  mov     rcx, rbx; this
0x18003758e  call    ?Increment@TraceLoggingCorrelationVector@@QEAA_NPEAD@Z; TraceLoggingCorrelationVector::Increment(char *)
0x180037593  xorps   xmm0, xmm0
0x180037596  movups  [rsp+0A88h+var_9F8], xmm0
0x18003759e  mov     [rsp+0A88h+var_9E8], r12
0x1800375a6  lea     r13d, [r12+7]
0x1800375ab  mov     [rsp+0A88h+var_9E8+8], r13
0x1800375b3  mov     word ptr [rsp+0A88h+var_9F8], r12w
0x1800375bc  mov     [rsp+0A88h+var_A2C], r12d
0x1800375c1  movups  xmmword ptr [rsp+0A88h+MultiByteStr], xmm0
0x1800375c9  xorps   xmm1, xmm1
0x1800375cc  movdqu  [rsp+0A88h+var_9C8], xmm1
0x1800375d5  lea     rax, [rsp+0A88h+Destination]
0x1800375dd  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800375e1  mov     r8, r14
0x1800375e4  inc     r8
0x1800375e7  cmp     [rax+r8], r12b
0x1800375eb  jnz     short loc_1800375E4
0x1800375ed  lea     rdx, [rsp+0A88h+Destination]
0x1800375f5  lea     rcx, [rsp+0A88h+MultiByteStr]
0x1800375fd  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180037602  nop
0x180037603  xor     r8d, r8d; CodePage
0x180037606  lea     rdx, [rsp+0A88h+MultiByteStr]; lpMultiByteStr
0x18003760e  lea     rcx, [rsp+0A88h+var_908]; Src
0x180037616  call    ?ConvertToWide@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@I@Z; ConvertToWide(std::string const &,uint)
0x18003761b  mov     rbx, rax
0x18003761e  xorps   xmm0, xmm0
0x180037621  movups  [rsp+0A88h+Src], xmm0
0x180037626  xorps   xmm1, xmm1
0x180037629  movdqu  [rsp+0A88h+var_A08], xmm1
0x180037632  mov     r8d, 5
0x180037638  lea     rdx, aMsCv; "MS-CV"
0x18003763f  lea     rcx, [rsp+0A88h+Src]
0x180037644  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180037649  nop
0x18003764a  lea     rcx, [rsi+0F8h]
0x180037651  lea     rdx, [rsp+0A88h+Src]
0x180037656  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x18003765b  mov     rdi, rax
0x18003765e  cmp     rax, rbx
0x180037661  jz      short loc_180037685
0x180037663  mov     rcx, rax
0x180037666  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003766b  movups  xmm0, xmmword ptr [rbx]
0x18003766e  movups  xmmword ptr [rdi], xmm0
0x180037671  movups  xmm1, xmmword ptr [rbx+10h]
0x180037675  movups  xmmword ptr [rdi+10h], xmm1
0x180037679  mov     [rbx+10h], r12
0x18003767d  mov     [rbx+18h], r13
0x180037681  mov     [rbx], r12w
0x180037685  lea     rcx, [rsp+0A88h+Src]
0x18003768a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003768f  nop
0x180037690  lea     rcx, [rsp+0A88h+var_908]
0x180037698  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003769d  nop
0x18003769e  lea     rcx, [rsp+0A88h+MultiByteStr]
0x1800376a6  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800376ab  call    cs:__imp_GetTickCount
0x1800376b1  mov     edi, eax
0x1800376b3  lea     rbx, [rsi+20h]
0x1800376b7  cmp     [rbx+18h], r13
0x1800376bb  jbe     short loc_1800376C2
0x1800376bd  mov     rdx, [rbx]
0x1800376c0  jmp     short loc_1800376C5
0x1800376c2  mov     rdx, rbx
0x1800376c5  xorps   xmm0, xmm0
0x1800376c8  movups  xmmword ptr [rsp+0A88h+MultiByteStr], xmm0
0x1800376d0  xorps   xmm1, xmm1
0x1800376d3  movdqu  [rsp+0A88h+var_9C8], xmm1
0x1800376dc  mov     r8, r14
0x1800376df  inc     r8
0x1800376e2  cmp     [rdx+r8*2], r12w
0x1800376e7  jnz     short loc_1800376DF
0x1800376e9  lea     rcx, [rsp+0A88h+MultiByteStr]
0x1800376f1  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800376f6  nop
0x1800376f7  mov     r9, rsi
0x1800376fa  lea     r8, [rsp+0A88h+var_968]
0x180037702  lea     rdx, [rsp+0A88h+MultiByteStr]
0x18003770a  lea     rcx, [rsp+0A88h+var_9B8]
0x180037712  call    ?SendRequestAndWaitForResponse@@YA?AVHttpResponse@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVProxySettings@@AEAVHttpRequest@@@Z; SendRequestAndWaitForResponse(std::wstring const &,ProxySettings const &,HttpRequest &)
0x180037717  nop
0x180037718  lea     rcx, [rsp+0A88h+MultiByteStr]
0x180037720  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180037725  call    cs:__imp_GetTickCount
0x18003772b  mov     r14d, eax
0x18003772e  sub     r14d, edi
0x180037731  mov     dword ptr [rsp+0A88h+var_A38], r14d
0x180037736  lea     rcx, [rsp+0A88h+var_9B8]; this
0x18003773e  call    ?StatusCode@HttpResponse@@QEBAKXZ; HttpResponse::StatusCode(void)
0x180037743  mov     esi, eax
0x180037745  mov     [rsp+0A88h+var_A2C], eax
0x180037749  mov     rcx, [rsp+0A88h]; this
0x180037751  add     eax, 0FFFFFF38h
0x180037756  cmp     eax, 63h ; 'c'
0x180037759  ja      loc_180037AC4
0x18003775f  mov     r8, [rsp+0A88h+var_9A8]
0x180037767  test    r8, r8
0x18003776a  jnz     loc_180037897
0x180037770  xorps   xmm0, xmm0
0x180037773  movups  [rsp+0A88h+Src], xmm0
0x180037778  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x180037780  movdqu  [rsp+0A88h+var_A08], xmm1
0x180037789  mov     byte ptr [rsp+0A88h+Src], r12b
0x18003778e  mov     [rsp+0A88h+dwNumberOfBytesRead], r12d
0x180037793  xor     edx, edx; Val
0x180037795  mov     r8d, 801h; Size
0x18003779b  lea     rcx, [rsp+0A88h+Buffer]; void *
0x1800377a3  call    memset_0
0x1800377a8  lea     r9, [rsp+0A88h+dwNumberOfBytesRead]; lpdwNumberOfBytesRead
0x1800377ad  mov     r8d, 800h; dwNumberOfBytesToRead
0x1800377b3  lea     rdx, [rsp+0A88h+Buffer]; lpBuffer
0x1800377bb  mov     rcx, [rsp+0A88h+hRequest]; hRequest
0x1800377c3  call    cs:__imp_WinHttpReadData
0x1800377c9  mov     rcx, [rsp+0A88h]; this
0x1800377d1  test    eax, eax
0x1800377d3  jz      loc_180037ADF
0x1800377d9  lea     rax, [rsp+0A88h+Buffer]
0x1800377e1  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800377e5  inc     r8
0x1800377e8  cmp     [rax+r8], r12b
0x1800377ec  jnz     short loc_1800377E5
0x1800377ee  lea     rdx, [rsp+0A88h+Buffer]
0x1800377f6  lea     rcx, [rsp+0A88h+Src]; Src
0x1800377fb  call    ??$_Append@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Append<char>(char const * const,unsigned __int64)
0x180037800  cmp     [rsp+0A88h+dwNumberOfBytesRead], r12d
0x180037805  ja      short loc_180037793
0x180037807  mov     r8d, 0FDE9h; CodePage
0x18003780d  lea     rdx, [rsp+0A88h+Src]; lpMultiByteStr
0x180037812  lea     rcx, [rsp+0A88h+var_908]; Src
0x18003781a  call    ?ConvertToWide@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@I@Z; ConvertToWide(std::string const &,uint)
0x18003781f  mov     rdi, rax
0x180037822  lea     rax, [rsp+0A88h+var_9B8]
0x18003782a  cmp     rax, rdi
0x18003782d  jz      short loc_180037877
0x18003782f  lea     rcx, [rsp+0A88h+var_9B8]
0x180037837  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003783c  mov     rcx, [rdi]
0x18003783f  mov     [rsp+0A88h+var_9B8], rcx
0x180037847  mov     rcx, [rdi+8]
0x18003784b  mov     [rsp+0A88h+var_9B0], rcx
0x180037853  mov     rcx, [rdi+10h]
0x180037857  mov     [rsp+0A88h+var_9A8], rcx
0x18003785f  mov     rax, [rdi+18h]
0x180037863  mov     [rsp+0A88h+var_9A0], rax
0x18003786b  mov     [rdi+10h], r12
0x18003786f  mov     [rdi+18h], r13
0x180037873  mov     [rdi], r12w
0x180037877  lea     rcx, [rsp+0A88h+var_908]
0x18003787f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180037884  nop
0x180037885  lea     rcx, [rsp+0A88h+Src]
0x18003788a  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18003788f  mov     r8, [rsp+0A88h+var_9A8]
0x180037897  xorps   xmm0, xmm0
0x18003789a  movups  [rsp+0A88h+Src], xmm0
0x18003789f  xorps   xmm1, xmm1
0x1800378a2  movdqu  [rsp+0A88h+var_A08], xmm1
0x1800378ab  lea     rdx, [rsp+0A88h+var_9B8]
0x1800378b3  cmp     [rsp+0A88h+var_9A0], r13
0x1800378bb  cmova   rdx, [rsp+0A88h+var_9B8]
0x1800378c4  lea     rcx, [rsp+0A88h+Src]
0x1800378c9  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x1800378ce  lea     rcx, [rsp+0A88h+var_9F8]
0x1800378d6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800378db  movups  xmm0, [rsp+0A88h+Src]
0x1800378e0  movups  [rsp+0A88h+var_9F8], xmm0
0x1800378e8  movups  xmm1, [rsp+0A88h+var_A08]
0x1800378f0  movups  xmmword ptr [rsp+0A88h+var_9E8], xmm1
0x1800378f8  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180037900  movdqu  [rsp+0A88h+var_A08], xmm0
0x180037909  mov     word ptr [rsp+0A88h+Src], r12w
0x18003790f  lea     rcx, [rsp+0A88h+Src]
0x180037914  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180037919  mov     rax, [rsp+0A88h+var_9E8]
0x180037921  cmp     [rbx+18h], r13
0x180037925  jbe     short loc_18003792C
0x180037927  mov     rdx, [rbx]
0x18003792a  jmp     short loc_18003792F
0x18003792c  mov     rdx, rbx; char *
0x18003792f  mov     edi, 1
0x180037934  mov     byte ptr [rsp+0A88h+var_A60], dil; char
0x180037939  mov     [rsp+0A88h+var_A68], rax; __int64
0x18003793e  mov     r9d, esi; int
0x180037941  mov     r8d, r14d; unsigned __int16 *
0x180037944  lea     rcx, [rsp+0A88h+Destination]; this
0x18003794c  call    ?TraceOutgoingServiceRequest@PushToInstall@Windows@@YAXPEBDPEBGHH_KE@Z; Windows::PushToInstall::TraceOutgoingServiceRequest(char const *,ushort const *,int,int,unsigned __int64,uchar)
0x180037951  call    cs:__imp_IsDebuggerPresent
0x180037957  test    eax, eax
0x180037959  jz      short loc_1800379D9
0x18003795b  cmp     [rsp+0A88h+var_9E8], r12
0x180037963  jnz     short loc_18003796E
0x180037965  lea     rax, aEmpty; "<empty>"
0x18003796c  jmp     short loc_180037987
0x18003796e  lea     rax, [rsp+0A88h+var_9F8]
0x180037976  cmp     [rsp+0A88h+var_9E8+8], r13
0x18003797e  cmova   rax, qword ptr [rsp+0A88h+var_9F8]
0x180037987  cmp     [rbx+18h], r13
0x18003798b  jbe     short loc_180037990
0x18003798d  mov     rbx, [rbx]
0x180037990  mov     [rsp+0A88h+var_A48], rax
0x180037995  mov     [rsp+0A88h+var_A50], rbx
0x18003799a  lea     rax, [rsp+0A88h+Destination]
0x1800379a2  mov     [rsp+0A88h+var_A58], rax
0x1800379a7  lea     rax, aHsSResponseS; "[%hs] %s Response: %s"
0x1800379ae  mov     [rsp+0A88h+var_A60], rax; unsigned __int16 *
0x1800379b3  mov     dword ptr [rsp+0A88h+var_A68], 0FFFFFFFFh; int
0x1800379bb  lea     r9, aPtiutilsSendre; "PTIUtils::SendRequest"
0x1800379c2  mov     r8d, 5Dh ; ']'; unsigned int
0x1800379c8  lea     rdx, aOnecoreuapEndu_10; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x1800379cf  lea     ecx, [r8-59h]; unsigned int
0x1800379d3  call    ?LogMessage@@YAXIPEBDI0JPEBGZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,...)
0x1800379d8  nop
0x1800379d9  lea     rax, ??_7?$HandleT@UHINTERNETTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::`vftable'
0x1800379e0  mov     [rsp+0A88h+var_990], rax
0x1800379e8  cmp     [rsp+0A88h+hRequest], r12
0x1800379f0  jz      short loc_180037A0F
0x1800379f2  lea     rcx, [rsp+0A88h+var_990]
0x1800379fa  call    ?InternalClose@?$HandleT@UHINTERNETTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::InternalClose(void)
0x1800379ff  test    al, al
0x180037a01  jz      loc_180037AF1
0x180037a07  mov     [rsp+0A88h+hRequest], r12
0x180037a0f  lea     rcx, [rsp+0A88h+var_9B8]
0x180037a17  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180037a1c  nop
0x180037a1d  test    r15, r15
0x180037a20  jz      short loc_180037A6C
0x180037a22  lea     rcx, [rsp+0A88h+var_A38]
0x180037a27  cmp     [rsp+0A88h+var_9E8], r12
0x180037a2f  jnz     short loc_180037A38
0x180037a31  call    ?null@value@json@web@@SA?AV123@XZ; web::json::value::null(void)
0x180037a36  jmp     short loc_180037A45
0x180037a38  lea     rdx, [rsp+0A88h+var_9F8]
0x180037a40  call    ?parse@value@json@web@@SA?AV123@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::parse(std::wstring const &)
0x180037a45  mov     rdx, rax
0x180037a48  mov     rcx, r15
0x180037a4b  call    ??4value@json@web@@QEAAAEAV012@$$QEAV012@@Z; web::json::value::operator=(web::json::value &&)
0x180037a50  mov     rcx, [rsp+0A88h+var_A38]
0x180037a55  test    rcx, rcx
0x180037a58  jz      short loc_180037A6C
0x180037a5a  mov     rax, [rcx]
0x180037a5d  mov     edx, edi
0x180037a5f  mov     rax, [rax+0C0h]
0x180037a66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037a6b  nop
0x180037a6c  lea     rcx, [rsp+0A88h+var_9F8]
0x180037a74  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180037a79  nop
0x180037a7a  lea     rcx, [rsp+0A88h+var_928]
0x180037a82  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180037a87  lea     rcx, [rsp+0A88h+var_948]
0x180037a8f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180037a94  lea     rcx, [rsp+0A88h+var_960]
0x180037a9c  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180037aa1  mov     rcx, [rsp+0A88h+var_48]
0x180037aa9  xor     rcx, rsp; StackCookie
0x180037aac  call    __security_check_cookie
0x180037ab1  add     rsp, 0A50h
0x180037ab8  pop     r15
0x180037aba  pop     r14
0x180037abc  pop     r13
0x180037abe  pop     r12
0x180037ac0  pop     rdi
  ... truncated ...
```
