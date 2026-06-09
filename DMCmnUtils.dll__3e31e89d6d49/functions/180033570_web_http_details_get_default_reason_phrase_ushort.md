# web::http::details::get_default_reason_phrase(ushort)

- ea: `0x180033570`
- end: `0x180033d9b`
- name: `?get_default_reason_phrase@details@http@web@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@G@Z`
- size: `2091`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000e6b0`

## callees

- `0x180007620`
- `0x180033570`
- `0x180051ea0`
- `0x180051f08`
- `0x18005b348`
- `0x18005b73c`

## string_xrefs

- `0x180033669`: `Switching Protocols`
- `0x1800336a9`: `Created`
- `0x180033789`: `Already Reported`
- `0x1800337e9`: `Moved Permanently`
- `0x180033889`: `Temporary Redirect`
- `0x180033a89`: `Request Uri Too Large`
- `0x180033c89`: `Service Unavailable`

## pseudocode

```c
// Hidden C++ exception states: #wind=58
__int64 *__fastcall web::http::details::get_default_reason_phrase(__int64 *a1, __int16 a2)
{
  __int64 *v4; // rax
  __int64 *v6; // rdx

  if ( dword_18010DA50 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_18010DA50);
    if ( dword_18010DA50 == -1 )
    {
      std::wstring::wstring(qword_18010BE18, L"Continue");
      word_18010BE38 = 101;
      std::wstring::wstring(qword_18010BE40, L"Switching Protocols");
      word_18010BE60 = 200;
      std::wstring::wstring(qword_18010BE68, L"OK");
      word_18010BE88 = 201;
      std::wstring::wstring(qword_18010BE90, L"Created");
      word_18010BEB0 = 202;
      std::wstring::wstring(qword_18010BEB8, L"Accepted");
      word_18010BED8 = 203;
      std::wstring::wstring(qword_18010BEE0, L"Non-Authoritative Information");
      word_18010BF00 = 204;
      std::wstring::wstring(qword_18010BF08, L"No Content");
      word_18010BF28 = 205;
      std::wstring::wstring(qword_18010BF30, L"Reset Content");
      word_18010BF50 = 206;
      std::wstring::wstring(qword_18010BF58, L"Partial Content");
      word_18010BF78 = 207;
      std::wstring::wstring(qword_18010BF80, L"Multi-Status");
      word_18010BFA0 = 208;
      std::wstring::wstring(qword_18010BFA8, L"Already Reported");
      word_18010BFC8 = 226;
      std::wstring::wstring(qword_18010BFD0, L"IM Used");
      word_18010BFF0 = 300;
      std::wstring::wstring(qword_18010BFF8, L"Multiple Choices");
      word_18010C018 = 301;
      std::wstring::wstring(qword_18010C020, L"Moved Permanently");
      word_18010C040 = 302;
      std::wstring::wstring(qword_18010C048, L"Found");
      word_18010C068 = 303;
      std::wstring::wstring(qword_18010C070, L"See Other");
      word_18010C090 = 304;
      std::wstring::wstring(qword_18010C098, L"Not Modified");
      word_18010C0B8 = 305;
      std::wstring::wstring(qword_18010C0C0, L"Use Proxy");
      word_18010C0E0 = 307;
      std::wstring::wstring(qword_18010C0E8, L"Temporary Redirect");
      word_18010C108 = 308;
      std::wstring::wstring(qword_18010C110, L"Permanent Redirect");
      word_18010C130 = 400;
      std::wstring::wstring(qword_18010C138, L"Bad Request");
      word_18010C158 = 401;
      std::wstring::wstring(qword_18010C160, L"Unauthorized");
      word_18010C180 = 402;
      std::wstring::wstring(qword_18010C188, L"Payment Required");
      word_18010C1A8 = 403;
      std::wstring::wstring(qword_18010C1B0, L"Forbidden");
      word_18010C1D0 = 404;
      std::wstring::wstring(qword_18010C1D8, L"Not Found");
      word_18010C1F8 = 405;
      std::wstring::wstring(qword_18010C200, L"Method Not Allowed");
      word_18010C220 = 406;
      std::wstring::wstring(qword_18010C228, L"Not Acceptable");
      word_18010C248 = 407;
      std::wstring::wstring(qword_18010C250, L"Proxy Authentication Required");
      word_18010C270 = 408;
      std::wstring::wstring(qword_18010C278, L"Request Time-out");
      word_18010C298 = 409;
      std::wstring::wstring(qword_18010C2A0, L"Conflict");
      word_18010C2C0 = 410;
      std::wstring::wstring(qword_18010C2C8, L"Gone");
      word_18010C2E8 = 411;
      std::wstring::wstring(qword_18010C2F0, L"Length Required");
      word_18010C310 = 412;
      std::wstring::wstring(qword_18010C318, L"Precondition Failed");
      word_18010C338 = 413;
      std::wstring::wstring(qword_18010C340, L"Request Entity Too Large");
      word_18010C360 = 414;
      std::wstring::wstring(qword_18010C368, L"Request Uri Too Large");
      word_18010C388 = 415;
      std::wstring::wstring(qword_18010C390, L"Unsupported Media Type");
      word_18010C3B0 = 416;
      std::wstring::wstring(qword_18010C3B8, L"Requested range not satisfiable");
      word_18010C3D8 = 417;
      std::wstring::wstring(qword_18010C3E0, L"Expectation Failed");
      word_18010C400 = 421;
      std::wstring::wstring(qword_18010C408, L"Misdirected Request");
      word_18010C428 = 422;
      std::wstring::wstring(qword_18010C430, L"Unprocessable Entity");
      word_18010C450 = 423;
      std::wstring::wstring(qword_18010C458, L"Locked");
      word_18010C478 = 424;
      std::wstring::wstring(qword_18010C480, L"Failed Dependency");
      word_18010C4A0 = 426;
      std::wstring::wstring(qword_18010C4A8, L"Upgrade Required");
      word_18010C4C8 = 428;
      std::wstring::wstring(qword_18010C4D0, L"Precondition Required");
      word_18010C4F0 = 429;
      std::wstring::wstring(qword_18010C4F8, L"Too Many Requests");
      word_18010C518 = 431;
      std::wstring::wstring(qword_18010C520, L"Request Header Fields Too Large");
      word_18010C540 = 451;
      std::wstring::wstring(qword_18010C548, L"Unavailable For Legal Reasons");
      word_18010C568 = 500;
      std::wstring::wstring(qword_18010C570, L"Internal Error");
      word_18010C590 = 501;
      std::wstring::wstring(qword_18010C598, L"Not Implemented");
      word_18010C5B8 = 502;
      std::wstring::wstring(qword_18010C5C0, L"Bad Gateway");
      word_18010C5E0 = 503;
      std::wstring::wstring(qword_18010C5E8, L"Service Unavailable");
      word_18010C608 = 504;
      std::wstring::wstring(qword_18010C610, L"Gateway Time-out");
      word_18010C630 = 505;
      std::wstring::wstring(qword_18010C638, L"HTTP Version not supported");
      word_18010C658 = 506;
      std::wstring::wstring(qword_18010C660, L"Variant Also Negotiates");
      word_18010C680 = 507;
      std::wstring::wstring(qword_18010C688, L"Insufficient Storage");
      word_18010C6A8 = 508;
      std::wstring::wstring(qword_18010C6B0, L"Loop Detected");
      word_18010C6D0 = 510;
      std::wstring::wstring(qword_18010C6D8, L"Not Extended");
      word_18010C6F8 = 511;
      std::wstring::wstring(qword_18010C700, L"Network Authentication Required");
      atexit(web::http::details::get_default_reason_phrase_::_2_::_dynamic_atexit_destructor_for__idToPhraseMap__);
      Init_thread_footer(&dword_18010DA50);
    }
  }
  *(_OWORD *)a1 = 0;
  a1[2] = 0;
  a1[3] = 7;
  *(_WORD *)a1 = 0;
  v4 = &qword_18010BE10;
  while ( *(_WORD *)v4 != a2 )
  {
    v4 += 5;
    if ( v4 == _hexval )
      return a1;
  }
  if ( a1 != v4 + 1 )
  {
    if ( (unsigned __int64)v4[4] <= 7 )
      v6 = v4 + 1;
    else
      v6 = (__int64 *)v4[1];
    std::wstring::_Assign<unsigned short>(a1, v6, v4[3]);
  }
  return a1;
}

```

## disassembly

```asm
0x180033570  mov     [rsp+arg_8], rbx
0x180033575  mov     [rsp+arg_0], rcx
0x18003357a  push    rdi
0x18003357b  sub     rsp, 30h
0x18003357f  movzx   edi, dx
0x180033582  mov     rbx, rcx
0x180033585  mov     [rsp+38h+var_18], 0
0x18003358d  mov     r8d, cs:_tls_index
0x180033594  mov     rax, gs:58h
0x18003359d  mov     ecx, 4
0x1800335a2  mov     rax, [rax+r8*8]
0x1800335a6  mov     eax, [rcx+rax]
0x1800335a9  cmp     cs:dword_18010DA50, eax
0x1800335af  jg      short loc_180033630
0x1800335b1  xorps   xmm0, xmm0
0x1800335b4  movups  xmmword ptr [rbx], xmm0
0x1800335b7  mov     qword ptr [rbx+10h], 0
0x1800335bf  mov     qword ptr [rbx+18h], 7
0x1800335c7  xor     eax, eax
0x1800335c9  mov     [rbx], ax
0x1800335cc  mov     [rsp+38h+var_18], 1
0x1800335d4  lea     rax, qword_18010BE10
0x1800335db  lea     rcx, ?_hexval@@3V?$array@C$0IA@@std@@A; std::array<signed char,128> _hexval
0x1800335e2  cmp     [rax], di
0x1800335e5  jz      short loc_1800335FE
0x1800335e7  add     rax, 28h ; '('
0x1800335eb  cmp     rax, rcx
0x1800335ee  jnz     short loc_1800335E2
0x1800335f0  mov     rax, rbx
0x1800335f3  mov     rbx, [rsp+38h+arg_8]
0x1800335f8  add     rsp, 30h
0x1800335fc  pop     rdi
0x1800335fd  retn
0x1800335fe  lea     r8, [rax+8]
0x180033602  cmp     rbx, r8
0x180033605  jz      short loc_180033622
0x180033607  cmp     qword ptr [r8+18h], 7
0x18003360c  jbe     short loc_180033613
0x18003360e  mov     rdx, [r8]
0x180033611  jmp     short loc_180033616
0x180033613  mov     rdx, r8
0x180033616  mov     r8, [r8+10h]
0x18003361a  mov     rcx, rbx
0x18003361d  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180033622  mov     rax, rbx
0x180033625  mov     rbx, [rsp+38h+arg_8]
0x18003362a  add     rsp, 30h
0x18003362e  pop     rdi
0x18003362f  retn
0x180033630  lea     rcx, dword_18010DA50
0x180033637  call    _Init_thread_header
0x18003363c  cmp     cs:dword_18010DA50, 0FFFFFFFFh
0x180033643  jnz     loc_1800335B1
0x180033649  lea     rdx, aContinue; "Continue"
0x180033650  lea     rcx, qword_18010BE18
0x180033657  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003365c  nop
0x18003365d  mov     eax, 65h ; 'e'
0x180033662  mov     cs:word_18010BE38, ax
0x180033669  lea     rdx, aSwitchingProto; "Switching Protocols"
0x180033670  lea     rcx, qword_18010BE40
0x180033677  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003367c  nop
0x18003367d  mov     eax, 0C8h
0x180033682  mov     cs:word_18010BE60, ax
0x180033689  lea     rdx, aOk; "OK"
0x180033690  lea     rcx, qword_18010BE68
0x180033697  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003369c  nop
0x18003369d  mov     eax, 0C9h
0x1800336a2  mov     cs:word_18010BE88, ax
0x1800336a9  lea     rdx, aCreated; "Created"
0x1800336b0  lea     rcx, qword_18010BE90
0x1800336b7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800336bc  nop
0x1800336bd  mov     eax, 0CAh
0x1800336c2  mov     cs:word_18010BEB0, ax
0x1800336c9  lea     rdx, aAccepted; "Accepted"
0x1800336d0  lea     rcx, qword_18010BEB8
0x1800336d7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800336dc  nop
0x1800336dd  mov     eax, 0CBh
0x1800336e2  mov     cs:word_18010BED8, ax
0x1800336e9  lea     rdx, aNonAuthoritati; "Non-Authoritative Information"
0x1800336f0  lea     rcx, qword_18010BEE0
0x1800336f7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800336fc  nop
0x1800336fd  mov     eax, 0CCh
0x180033702  mov     cs:word_18010BF00, ax
0x180033709  lea     rdx, aNoContent; "No Content"
0x180033710  lea     rcx, qword_18010BF08
0x180033717  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003371c  nop
0x18003371d  mov     eax, 0CDh
0x180033722  mov     cs:word_18010BF28, ax
0x180033729  lea     rdx, aResetContent; "Reset Content"
0x180033730  lea     rcx, qword_18010BF30
0x180033737  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003373c  nop
0x18003373d  mov     eax, 0CEh
0x180033742  mov     cs:word_18010BF50, ax
0x180033749  lea     rdx, aPartialContent; "Partial Content"
0x180033750  lea     rcx, qword_18010BF58
0x180033757  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003375c  nop
0x18003375d  mov     eax, 0CFh
0x180033762  mov     cs:word_18010BF78, ax
0x180033769  lea     rdx, aMultiStatus; "Multi-Status"
0x180033770  lea     rcx, qword_18010BF80
0x180033777  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003377c  nop
0x18003377d  mov     eax, 0D0h
0x180033782  mov     cs:word_18010BFA0, ax
0x180033789  lea     rdx, aAlreadyReporte; "Already Reported"
0x180033790  lea     rcx, qword_18010BFA8
0x180033797  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003379c  nop
0x18003379d  mov     eax, 0E2h
0x1800337a2  mov     cs:word_18010BFC8, ax
0x1800337a9  lea     rdx, aImUsed; "IM Used"
0x1800337b0  lea     rcx, qword_18010BFD0
0x1800337b7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800337bc  nop
0x1800337bd  mov     eax, 12Ch
0x1800337c2  mov     cs:word_18010BFF0, ax
0x1800337c9  lea     rdx, aMultipleChoice; "Multiple Choices"
0x1800337d0  lea     rcx, qword_18010BFF8
0x1800337d7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800337dc  nop
0x1800337dd  mov     eax, 12Dh
0x1800337e2  mov     cs:word_18010C018, ax
0x1800337e9  lea     rdx, aMovedPermanent; "Moved Permanently"
0x1800337f0  lea     rcx, qword_18010C020
0x1800337f7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800337fc  nop
0x1800337fd  mov     eax, 12Eh
0x180033802  mov     cs:word_18010C040, ax
0x180033809  lea     rdx, aFound; "Found"
0x180033810  lea     rcx, qword_18010C048
0x180033817  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003381c  nop
0x18003381d  mov     eax, 12Fh
0x180033822  mov     cs:word_18010C068, ax
0x180033829  lea     rdx, aSeeOther; "See Other"
0x180033830  lea     rcx, qword_18010C070
0x180033837  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003383c  nop
0x18003383d  mov     eax, 130h
0x180033842  mov     cs:word_18010C090, ax
0x180033849  lea     rdx, aNotModified; "Not Modified"
0x180033850  lea     rcx, qword_18010C098
0x180033857  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003385c  nop
0x18003385d  mov     eax, 131h
0x180033862  mov     cs:word_18010C0B8, ax
0x180033869  lea     rdx, aUseProxy; "Use Proxy"
0x180033870  lea     rcx, qword_18010C0C0
0x180033877  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003387c  nop
0x18003387d  mov     eax, 133h
0x180033882  mov     cs:word_18010C0E0, ax
0x180033889  lea     rdx, aTemporaryRedir; "Temporary Redirect"
0x180033890  lea     rcx, qword_18010C0E8
0x180033897  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003389c  nop
0x18003389d  mov     eax, 134h
0x1800338a2  mov     cs:word_18010C108, ax
0x1800338a9  lea     rdx, aPermanentRedir; "Permanent Redirect"
0x1800338b0  lea     rcx, qword_18010C110
0x1800338b7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800338bc  nop
0x1800338bd  mov     eax, 190h
0x1800338c2  mov     cs:word_18010C130, ax
0x1800338c9  lea     rdx, aBadRequest; "Bad Request"
0x1800338d0  lea     rcx, qword_18010C138
0x1800338d7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800338dc  nop
0x1800338dd  mov     eax, 191h
0x1800338e2  mov     cs:word_18010C158, ax
0x1800338e9  lea     rdx, aUnauthorized; "Unauthorized"
0x1800338f0  lea     rcx, qword_18010C160
0x1800338f7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800338fc  nop
0x1800338fd  mov     eax, 192h
0x180033902  mov     cs:word_18010C180, ax
0x180033909  lea     rdx, aPaymentRequire; "Payment Required"
0x180033910  lea     rcx, qword_18010C188
0x180033917  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003391c  nop
0x18003391d  mov     eax, 193h
0x180033922  mov     cs:word_18010C1A8, ax
0x180033929  lea     rdx, aForbidden; "Forbidden"
0x180033930  lea     rcx, qword_18010C1B0
0x180033937  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003393c  nop
0x18003393d  mov     eax, 194h
0x180033942  mov     cs:word_18010C1D0, ax
0x180033949  lea     rdx, aNotFound; "Not Found"
0x180033950  lea     rcx, qword_18010C1D8
0x180033957  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003395c  nop
0x18003395d  mov     eax, 195h
0x180033962  mov     cs:word_18010C1F8, ax
0x180033969  lea     rdx, aMethodNotAllow; "Method Not Allowed"
0x180033970  lea     rcx, qword_18010C200
0x180033977  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003397c  nop
0x18003397d  mov     eax, 196h
0x180033982  mov     cs:word_18010C220, ax
0x180033989  lea     rdx, aNotAcceptable; "Not Acceptable"
0x180033990  lea     rcx, qword_18010C228
0x180033997  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003399c  nop
0x18003399d  mov     eax, 197h
0x1800339a2  mov     cs:word_18010C248, ax
0x1800339a9  lea     rdx, aProxyAuthentic; "Proxy Authentication Required"
0x1800339b0  lea     rcx, qword_18010C250
0x1800339b7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800339bc  nop
0x1800339bd  mov     eax, 198h
0x1800339c2  mov     cs:word_18010C270, ax
0x1800339c9  lea     rdx, aRequestTimeOut; "Request Time-out"
0x1800339d0  lea     rcx, qword_18010C278
0x1800339d7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800339dc  nop
0x1800339dd  mov     eax, 199h
0x1800339e2  mov     cs:word_18010C298, ax
0x1800339e9  lea     rdx, aConflict; "Conflict"
0x1800339f0  lea     rcx, qword_18010C2A0
0x1800339f7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800339fc  nop
0x1800339fd  mov     eax, 19Ah
0x180033a02  mov     cs:word_18010C2C0, ax
0x180033a09  lea     rdx, aGone; "Gone"
0x180033a10  lea     rcx, qword_18010C2C8
0x180033a17  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180033a1c  nop
0x180033a1d  mov     eax, 19Bh
0x180033a22  mov     cs:word_18010C2E8, ax
0x180033a29  lea     rdx, aLengthRequired; "Length Required"
0x180033a30  lea     rcx, qword_18010C2F0
0x180033a37  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180033a3c  nop
0x180033a3d  mov     eax, 19Ch
0x180033a42  mov     cs:word_18010C310, ax
0x180033a49  lea     rdx, aPreconditionFa; "Precondition Failed"
0x180033a50  lea     rcx, qword_18010C318
0x180033a57  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180033a5c  nop
0x180033a5d  mov     eax, 19Dh
0x180033a62  mov     cs:word_18010C338, ax
0x180033a69  lea     rdx, aRequestEntityT; "Request Entity Too Large"
0x180033a70  lea     rcx, qword_18010C340
0x180033a77  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180033a7c  nop
0x180033a7d  mov     eax, 19Eh
0x180033a82  mov     cs:word_18010C360, ax
0x180033a89  lea     rdx, aRequestUriTooL; "Request Uri Too Large"
0x180033a90  lea     rcx, qword_18010C368
0x180033a97  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180033a9c  nop
0x180033a9d  mov     eax, 19Fh
0x180033aa2  mov     cs:word_18010C388, ax
0x180033aa9  lea     rdx, aUnsupportedMed; "Unsupported Media Type"
0x180033ab0  lea     rcx, qword_18010C390
0x180033ab7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180033abc  nop
0x180033abd  mov     eax, 1A0h
0x180033ac2  mov     cs:word_18010C3B0, ax
0x180033ac9  lea     rdx, aRequestedRange; "Requested range not satisfiable"
0x180033ad0  lea     rcx, qword_18010C3B8
0x180033ad7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180033adc  nop
0x180033add  mov     eax, 1A1h
0x180033ae2  mov     cs:word_18010C3D8, ax
0x180033ae9  lea     rdx, aExpectationFai; "Expectation Failed"
0x180033af0  lea     rcx, qword_18010C3E0
0x180033af7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180033afc  nop
0x180033afd  mov     eax, 1A5h
0x180033b02  mov     cs:word_18010C400, ax
0x180033b09  lea     rdx, aMisdirectedReq; "Misdirected Request"
0x180033b10  lea     rcx, qword_18010C408
0x180033b17  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180033b1c  nop
0x180033b1d  mov     eax, 1A6h
0x180033b22  mov     cs:word_18010C428, ax
0x180033b29  lea     rdx, aUnprocessableE; "Unprocessable Entity"
0x180033b30  lea     rcx, qword_18010C430
0x180033b37  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180033b3c  nop
0x180033b3d  mov     eax, 1A7h
0x180033b42  mov     cs:word_18010C450, ax
0x180033b49  lea     rdx, aLocked; "Locked"
0x180033b50  lea     rcx, qword_18010C458
0x180033b57  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180033b5c  nop
0x180033b5d  mov     eax, 1A8h
0x180033b62  mov     cs:word_18010C478, ax
0x180033b69  lea     rdx, aFailedDependen; "Failed Dependency"
  ... truncated ...
```
