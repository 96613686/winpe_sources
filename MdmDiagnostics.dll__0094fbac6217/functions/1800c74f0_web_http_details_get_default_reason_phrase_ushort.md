# web::http::details::get_default_reason_phrase(ushort)

- ea: `0x1800c74f0`
- end: `0x1800c7d1b`
- name: `?get_default_reason_phrase@details@http@web@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@G@Z`
- size: `2091`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800b9b90`

## callees

- `0x1800194e8`
- `0x18001969c`
- `0x180019704`
- `0x1800c74f0`
- `0x1800e5248`
- `0x1800e66dc`

## string_xrefs

- `0x1800c75e9`: `Switching Protocols`
- `0x1800c7629`: `Created`
- `0x1800c7709`: `Already Reported`
- `0x1800c7769`: `Moved Permanently`
- `0x1800c7809`: `Temporary Redirect`
- `0x1800c7a09`: `Request Uri Too Large`
- `0x1800c7c09`: `Service Unavailable`

## pseudocode

```c
// Hidden C++ exception states: #wind=58
__int64 __fastcall web::http::details::get_default_reason_phrase(__int64 a1, __int16 a2)
{
  __int64 *v4; // rax
  const void *v6; // rdx

  if ( dword_1802631D0 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_1802631D0);
    if ( dword_1802631D0 == -1 )
    {
      std::wstring::wstring(qword_1802598F8, L"Continue");
      word_180259918 = 101;
      std::wstring::wstring(qword_180259920, L"Switching Protocols");
      word_180259940 = 200;
      std::wstring::wstring(qword_180259948, L"OK");
      word_180259968 = 201;
      std::wstring::wstring(qword_180259970, L"Created");
      word_180259990 = 202;
      std::wstring::wstring(qword_180259998, L"Accepted");
      word_1802599B8 = 203;
      std::wstring::wstring(qword_1802599C0, L"Non-Authoritative Information");
      word_1802599E0 = 204;
      std::wstring::wstring(qword_1802599E8, L"No Content");
      word_180259A08 = 205;
      std::wstring::wstring(qword_180259A10, L"Reset Content");
      word_180259A30 = 206;
      std::wstring::wstring(qword_180259A38, L"Partial Content");
      word_180259A58 = 207;
      std::wstring::wstring(qword_180259A60, L"Multi-Status");
      word_180259A80 = 208;
      std::wstring::wstring(qword_180259A88, L"Already Reported");
      word_180259AA8 = 226;
      std::wstring::wstring(qword_180259AB0, L"IM Used");
      word_180259AD0 = 300;
      std::wstring::wstring(qword_180259AD8, L"Multiple Choices");
      word_180259AF8 = 301;
      std::wstring::wstring(qword_180259B00, L"Moved Permanently");
      word_180259B20 = 302;
      std::wstring::wstring(qword_180259B28, L"Found");
      word_180259B48 = 303;
      std::wstring::wstring(qword_180259B50, L"See Other");
      word_180259B70 = 304;
      std::wstring::wstring(qword_180259B78, L"Not Modified");
      word_180259B98 = 305;
      std::wstring::wstring(qword_180259BA0, L"Use Proxy");
      word_180259BC0 = 307;
      std::wstring::wstring(qword_180259BC8, L"Temporary Redirect");
      word_180259BE8 = 308;
      std::wstring::wstring(qword_180259BF0, L"Permanent Redirect");
      word_180259C10 = 400;
      std::wstring::wstring(qword_180259C18, L"Bad Request");
      word_180259C38 = 401;
      std::wstring::wstring(qword_180259C40, L"Unauthorized");
      word_180259C60 = 402;
      std::wstring::wstring(qword_180259C68, L"Payment Required");
      word_180259C88 = 403;
      std::wstring::wstring(qword_180259C90, L"Forbidden");
      word_180259CB0 = 404;
      std::wstring::wstring(qword_180259CB8, L"Not Found");
      word_180259CD8 = 405;
      std::wstring::wstring(qword_180259CE0, L"Method Not Allowed");
      word_180259D00 = 406;
      std::wstring::wstring(qword_180259D08, L"Not Acceptable");
      word_180259D28 = 407;
      std::wstring::wstring(qword_180259D30, L"Proxy Authentication Required");
      word_180259D50 = 408;
      std::wstring::wstring(qword_180259D58, L"Request Time-out");
      word_180259D78 = 409;
      std::wstring::wstring(qword_180259D80, L"Conflict");
      word_180259DA0 = 410;
      std::wstring::wstring(qword_180259DA8, L"Gone");
      word_180259DC8 = 411;
      std::wstring::wstring(qword_180259DD0, L"Length Required");
      word_180259DF0 = 412;
      std::wstring::wstring(qword_180259DF8, L"Precondition Failed");
      word_180259E18 = 413;
      std::wstring::wstring(qword_180259E20, L"Request Entity Too Large");
      word_180259E40 = 414;
      std::wstring::wstring(qword_180259E48, L"Request Uri Too Large");
      word_180259E68 = 415;
      std::wstring::wstring(qword_180259E70, L"Unsupported Media Type");
      word_180259E90 = 416;
      std::wstring::wstring(qword_180259E98, L"Requested range not satisfiable");
      word_180259EB8 = 417;
      std::wstring::wstring(qword_180259EC0, L"Expectation Failed");
      word_180259EE0 = 421;
      std::wstring::wstring(qword_180259EE8, L"Misdirected Request");
      word_180259F08 = 422;
      std::wstring::wstring(qword_180259F10, L"Unprocessable Entity");
      word_180259F30 = 423;
      std::wstring::wstring(qword_180259F38, L"Locked");
      word_180259F58 = 424;
      std::wstring::wstring(qword_180259F60, L"Failed Dependency");
      word_180259F80 = 426;
      std::wstring::wstring(qword_180259F88, L"Upgrade Required");
      word_180259FA8 = 428;
      std::wstring::wstring(qword_180259FB0, L"Precondition Required");
      word_180259FD0 = 429;
      std::wstring::wstring(qword_180259FD8, L"Too Many Requests");
      word_180259FF8 = 431;
      std::wstring::wstring(qword_18025A000, L"Request Header Fields Too Large");
      word_18025A020 = 451;
      std::wstring::wstring(qword_18025A028, L"Unavailable For Legal Reasons");
      word_18025A048 = 500;
      std::wstring::wstring(qword_18025A050, L"Internal Error");
      word_18025A070 = 501;
      std::wstring::wstring(qword_18025A078, L"Not Implemented");
      word_18025A098 = 502;
      std::wstring::wstring(qword_18025A0A0, L"Bad Gateway");
      word_18025A0C0 = 503;
      std::wstring::wstring(qword_18025A0C8, L"Service Unavailable");
      word_18025A0E8 = 504;
      std::wstring::wstring(qword_18025A0F0, L"Gateway Time-out");
      word_18025A110 = 505;
      std::wstring::wstring(qword_18025A118, L"HTTP Version not supported");
      word_18025A138 = 506;
      std::wstring::wstring(qword_18025A140, L"Variant Also Negotiates");
      word_18025A160 = 507;
      std::wstring::wstring(qword_18025A168, L"Insufficient Storage");
      word_18025A188 = 508;
      std::wstring::wstring(qword_18025A190, L"Loop Detected");
      word_18025A1B0 = 510;
      std::wstring::wstring(qword_18025A1B8, L"Not Extended");
      word_18025A1D8 = 511;
      std::wstring::wstring(qword_18025A1E0, L"Network Authentication Required");
      atexit(web::http::details::get_default_reason_phrase_::_2_::_dynamic_atexit_destructor_for__idToPhraseMap__);
      Init_thread_footer(&dword_1802631D0);
    }
  }
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 7;
  *(_WORD *)a1 = 0;
  v4 = &qword_1802598F0;
  while ( *(_WORD *)v4 != a2 )
  {
    v4 += 5;
    if ( v4 == (__int64 *)&_scrt_ucrt_dll_is_in_use )
      return a1;
  }
  if ( (__int64 *)a1 != v4 + 1 )
  {
    if ( (unsigned __int64)v4[4] <= 7 )
      v6 = v4 + 1;
    else
      v6 = (const void *)v4[1];
    std::wstring::_Assign<unsigned short>(a1, v6, v4[3]);
  }
  return a1;
}

```

## disassembly

```asm
0x1800c74f0  mov     [rsp+arg_8], rbx
0x1800c74f5  mov     [rsp+arg_0], rcx
0x1800c74fa  push    rdi
0x1800c74fb  sub     rsp, 30h
0x1800c74ff  movzx   edi, dx
0x1800c7502  mov     rbx, rcx
0x1800c7505  mov     [rsp+38h+var_18], 0
0x1800c750d  mov     r8d, cs:_tls_index
0x1800c7514  mov     rax, gs:58h
0x1800c751d  mov     ecx, 4
0x1800c7522  mov     rax, [rax+r8*8]
0x1800c7526  mov     eax, [rcx+rax]
0x1800c7529  cmp     cs:dword_1802631D0, eax
0x1800c752f  jg      short loc_1800C75B0
0x1800c7531  xorps   xmm0, xmm0
0x1800c7534  movups  xmmword ptr [rbx], xmm0
0x1800c7537  mov     qword ptr [rbx+10h], 0
0x1800c753f  mov     qword ptr [rbx+18h], 7
0x1800c7547  xor     eax, eax
0x1800c7549  mov     [rbx], ax
0x1800c754c  mov     [rsp+38h+var_18], 1
0x1800c7554  lea     rax, qword_1802598F0
0x1800c755b  lea     rcx, __scrt_ucrt_dll_is_in_use
0x1800c7562  cmp     [rax], di
0x1800c7565  jz      short loc_1800C757E
0x1800c7567  add     rax, 28h ; '('
0x1800c756b  cmp     rax, rcx
0x1800c756e  jnz     short loc_1800C7562
0x1800c7570  mov     rax, rbx
0x1800c7573  mov     rbx, [rsp+38h+arg_8]
0x1800c7578  add     rsp, 30h
0x1800c757c  pop     rdi
0x1800c757d  retn
0x1800c757e  lea     r8, [rax+8]
0x1800c7582  cmp     rbx, r8
0x1800c7585  jz      short loc_1800C75A2
0x1800c7587  cmp     qword ptr [r8+18h], 7
0x1800c758c  jbe     short loc_1800C7593
0x1800c758e  mov     rdx, [r8]
0x1800c7591  jmp     short loc_1800C7596
0x1800c7593  mov     rdx, r8
0x1800c7596  mov     r8, [r8+10h]
0x1800c759a  mov     rcx, rbx
0x1800c759d  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800c75a2  mov     rax, rbx
0x1800c75a5  mov     rbx, [rsp+38h+arg_8]
0x1800c75aa  add     rsp, 30h
0x1800c75ae  pop     rdi
0x1800c75af  retn
0x1800c75b0  lea     rcx, dword_1802631D0
0x1800c75b7  call    _Init_thread_header
0x1800c75bc  cmp     cs:dword_1802631D0, 0FFFFFFFFh
0x1800c75c3  jnz     loc_1800C7531
0x1800c75c9  lea     rdx, aContinue; "Continue"
0x1800c75d0  lea     rcx, qword_1802598F8
0x1800c75d7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c75dc  nop
0x1800c75dd  mov     eax, 65h ; 'e'
0x1800c75e2  mov     cs:word_180259918, ax
0x1800c75e9  lea     rdx, aSwitchingProto; "Switching Protocols"
0x1800c75f0  lea     rcx, qword_180259920
0x1800c75f7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c75fc  nop
0x1800c75fd  mov     eax, 0C8h
0x1800c7602  mov     cs:word_180259940, ax
0x1800c7609  lea     rdx, aOk; "OK"
0x1800c7610  lea     rcx, qword_180259948
0x1800c7617  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c761c  nop
0x1800c761d  mov     eax, 0C9h
0x1800c7622  mov     cs:word_180259968, ax
0x1800c7629  lea     rdx, aCreated; "Created"
0x1800c7630  lea     rcx, qword_180259970
0x1800c7637  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c763c  nop
0x1800c763d  mov     eax, 0CAh
0x1800c7642  mov     cs:word_180259990, ax
0x1800c7649  lea     rdx, aAccepted; "Accepted"
0x1800c7650  lea     rcx, qword_180259998
0x1800c7657  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c765c  nop
0x1800c765d  mov     eax, 0CBh
0x1800c7662  mov     cs:word_1802599B8, ax
0x1800c7669  lea     rdx, aNonAuthoritati; "Non-Authoritative Information"
0x1800c7670  lea     rcx, qword_1802599C0
0x1800c7677  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c767c  nop
0x1800c767d  mov     eax, 0CCh
0x1800c7682  mov     cs:word_1802599E0, ax
0x1800c7689  lea     rdx, aNoContent; "No Content"
0x1800c7690  lea     rcx, qword_1802599E8
0x1800c7697  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c769c  nop
0x1800c769d  mov     eax, 0CDh
0x1800c76a2  mov     cs:word_180259A08, ax
0x1800c76a9  lea     rdx, aResetContent; "Reset Content"
0x1800c76b0  lea     rcx, qword_180259A10
0x1800c76b7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c76bc  nop
0x1800c76bd  mov     eax, 0CEh
0x1800c76c2  mov     cs:word_180259A30, ax
0x1800c76c9  lea     rdx, aPartialContent; "Partial Content"
0x1800c76d0  lea     rcx, qword_180259A38
0x1800c76d7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c76dc  nop
0x1800c76dd  mov     eax, 0CFh
0x1800c76e2  mov     cs:word_180259A58, ax
0x1800c76e9  lea     rdx, aMultiStatus; "Multi-Status"
0x1800c76f0  lea     rcx, qword_180259A60
0x1800c76f7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c76fc  nop
0x1800c76fd  mov     eax, 0D0h
0x1800c7702  mov     cs:word_180259A80, ax
0x1800c7709  lea     rdx, aAlreadyReporte; "Already Reported"
0x1800c7710  lea     rcx, qword_180259A88
0x1800c7717  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c771c  nop
0x1800c771d  mov     eax, 0E2h
0x1800c7722  mov     cs:word_180259AA8, ax
0x1800c7729  lea     rdx, aImUsed; "IM Used"
0x1800c7730  lea     rcx, qword_180259AB0
0x1800c7737  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c773c  nop
0x1800c773d  mov     eax, 12Ch
0x1800c7742  mov     cs:word_180259AD0, ax
0x1800c7749  lea     rdx, aMultipleChoice; "Multiple Choices"
0x1800c7750  lea     rcx, qword_180259AD8
0x1800c7757  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c775c  nop
0x1800c775d  mov     eax, 12Dh
0x1800c7762  mov     cs:word_180259AF8, ax
0x1800c7769  lea     rdx, aMovedPermanent; "Moved Permanently"
0x1800c7770  lea     rcx, qword_180259B00
0x1800c7777  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c777c  nop
0x1800c777d  mov     eax, 12Eh
0x1800c7782  mov     cs:word_180259B20, ax
0x1800c7789  lea     rdx, aFound; "Found"
0x1800c7790  lea     rcx, qword_180259B28
0x1800c7797  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c779c  nop
0x1800c779d  mov     eax, 12Fh
0x1800c77a2  mov     cs:word_180259B48, ax
0x1800c77a9  lea     rdx, aSeeOther; "See Other"
0x1800c77b0  lea     rcx, qword_180259B50
0x1800c77b7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c77bc  nop
0x1800c77bd  mov     eax, 130h
0x1800c77c2  mov     cs:word_180259B70, ax
0x1800c77c9  lea     rdx, aNotModified; "Not Modified"
0x1800c77d0  lea     rcx, qword_180259B78
0x1800c77d7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c77dc  nop
0x1800c77dd  mov     eax, 131h
0x1800c77e2  mov     cs:word_180259B98, ax
0x1800c77e9  lea     rdx, aUseProxy; "Use Proxy"
0x1800c77f0  lea     rcx, qword_180259BA0
0x1800c77f7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c77fc  nop
0x1800c77fd  mov     eax, 133h
0x1800c7802  mov     cs:word_180259BC0, ax
0x1800c7809  lea     rdx, aTemporaryRedir; "Temporary Redirect"
0x1800c7810  lea     rcx, qword_180259BC8
0x1800c7817  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c781c  nop
0x1800c781d  mov     eax, 134h
0x1800c7822  mov     cs:word_180259BE8, ax
0x1800c7829  lea     rdx, aPermanentRedir; "Permanent Redirect"
0x1800c7830  lea     rcx, qword_180259BF0
0x1800c7837  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c783c  nop
0x1800c783d  mov     eax, 190h
0x1800c7842  mov     cs:word_180259C10, ax
0x1800c7849  lea     rdx, aBadRequest; "Bad Request"
0x1800c7850  lea     rcx, qword_180259C18
0x1800c7857  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c785c  nop
0x1800c785d  mov     eax, 191h
0x1800c7862  mov     cs:word_180259C38, ax
0x1800c7869  lea     rdx, aUnauthorized; "Unauthorized"
0x1800c7870  lea     rcx, qword_180259C40
0x1800c7877  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c787c  nop
0x1800c787d  mov     eax, 192h
0x1800c7882  mov     cs:word_180259C60, ax
0x1800c7889  lea     rdx, aPaymentRequire; "Payment Required"
0x1800c7890  lea     rcx, qword_180259C68
0x1800c7897  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c789c  nop
0x1800c789d  mov     eax, 193h
0x1800c78a2  mov     cs:word_180259C88, ax
0x1800c78a9  lea     rdx, aForbidden; "Forbidden"
0x1800c78b0  lea     rcx, qword_180259C90
0x1800c78b7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c78bc  nop
0x1800c78bd  mov     eax, 194h
0x1800c78c2  mov     cs:word_180259CB0, ax
0x1800c78c9  lea     rdx, aNotFound; "Not Found"
0x1800c78d0  lea     rcx, qword_180259CB8
0x1800c78d7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c78dc  nop
0x1800c78dd  mov     eax, 195h
0x1800c78e2  mov     cs:word_180259CD8, ax
0x1800c78e9  lea     rdx, aMethodNotAllow; "Method Not Allowed"
0x1800c78f0  lea     rcx, qword_180259CE0
0x1800c78f7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c78fc  nop
0x1800c78fd  mov     eax, 196h
0x1800c7902  mov     cs:word_180259D00, ax
0x1800c7909  lea     rdx, aNotAcceptable; "Not Acceptable"
0x1800c7910  lea     rcx, qword_180259D08
0x1800c7917  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c791c  nop
0x1800c791d  mov     eax, 197h
0x1800c7922  mov     cs:word_180259D28, ax
0x1800c7929  lea     rdx, aProxyAuthentic; "Proxy Authentication Required"
0x1800c7930  lea     rcx, qword_180259D30
0x1800c7937  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c793c  nop
0x1800c793d  mov     eax, 198h
0x1800c7942  mov     cs:word_180259D50, ax
0x1800c7949  lea     rdx, aRequestTimeOut; "Request Time-out"
0x1800c7950  lea     rcx, qword_180259D58
0x1800c7957  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c795c  nop
0x1800c795d  mov     eax, 199h
0x1800c7962  mov     cs:word_180259D78, ax
0x1800c7969  lea     rdx, aConflict; "Conflict"
0x1800c7970  lea     rcx, qword_180259D80
0x1800c7977  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c797c  nop
0x1800c797d  mov     eax, 19Ah
0x1800c7982  mov     cs:word_180259DA0, ax
0x1800c7989  lea     rdx, aGone; "Gone"
0x1800c7990  lea     rcx, qword_180259DA8
0x1800c7997  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c799c  nop
0x1800c799d  mov     eax, 19Bh
0x1800c79a2  mov     cs:word_180259DC8, ax
0x1800c79a9  lea     rdx, aLengthRequired; "Length Required"
0x1800c79b0  lea     rcx, qword_180259DD0
0x1800c79b7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c79bc  nop
0x1800c79bd  mov     eax, 19Ch
0x1800c79c2  mov     cs:word_180259DF0, ax
0x1800c79c9  lea     rdx, aPreconditionFa; "Precondition Failed"
0x1800c79d0  lea     rcx, qword_180259DF8
0x1800c79d7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c79dc  nop
0x1800c79dd  mov     eax, 19Dh
0x1800c79e2  mov     cs:word_180259E18, ax
0x1800c79e9  lea     rdx, aRequestEntityT; "Request Entity Too Large"
0x1800c79f0  lea     rcx, qword_180259E20
0x1800c79f7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c79fc  nop
0x1800c79fd  mov     eax, 19Eh
0x1800c7a02  mov     cs:word_180259E40, ax
0x1800c7a09  lea     rdx, aRequestUriTooL; "Request Uri Too Large"
0x1800c7a10  lea     rcx, qword_180259E48
0x1800c7a17  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c7a1c  nop
0x1800c7a1d  mov     eax, 19Fh
0x1800c7a22  mov     cs:word_180259E68, ax
0x1800c7a29  lea     rdx, aUnsupportedMed; "Unsupported Media Type"
0x1800c7a30  lea     rcx, qword_180259E70
0x1800c7a37  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c7a3c  nop
0x1800c7a3d  mov     eax, 1A0h
0x1800c7a42  mov     cs:word_180259E90, ax
0x1800c7a49  lea     rdx, aRequestedRange; "Requested range not satisfiable"
0x1800c7a50  lea     rcx, qword_180259E98
0x1800c7a57  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c7a5c  nop
0x1800c7a5d  mov     eax, 1A1h
0x1800c7a62  mov     cs:word_180259EB8, ax
0x1800c7a69  lea     rdx, aExpectationFai; "Expectation Failed"
0x1800c7a70  lea     rcx, qword_180259EC0
0x1800c7a77  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c7a7c  nop
0x1800c7a7d  mov     eax, 1A5h
0x1800c7a82  mov     cs:word_180259EE0, ax
0x1800c7a89  lea     rdx, aMisdirectedReq; "Misdirected Request"
0x1800c7a90  lea     rcx, qword_180259EE8
0x1800c7a97  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c7a9c  nop
0x1800c7a9d  mov     eax, 1A6h
0x1800c7aa2  mov     cs:word_180259F08, ax
0x1800c7aa9  lea     rdx, aUnprocessableE; "Unprocessable Entity"
0x1800c7ab0  lea     rcx, qword_180259F10
0x1800c7ab7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c7abc  nop
0x1800c7abd  mov     eax, 1A7h
0x1800c7ac2  mov     cs:word_180259F30, ax
0x1800c7ac9  lea     rdx, aLocked; "Locked"
0x1800c7ad0  lea     rcx, qword_180259F38
0x1800c7ad7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c7adc  nop
0x1800c7add  mov     eax, 1A8h
0x1800c7ae2  mov     cs:word_180259F58, ax
0x1800c7ae9  lea     rdx, aFailedDependen; "Failed Dependency"
  ... truncated ...
```
