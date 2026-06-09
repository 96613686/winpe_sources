# web::http::details::get_default_reason_phrase(ushort)

- ea: `0x18004f9c0`
- end: `0x18004ff73`
- name: `?get_default_reason_phrase@details@http@web@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@G@Z`
- size: `1459`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004f270`

## callees

- `0x180002ca8`
- `0x18000511c`
- `0x180005184`
- `0x18000573c`
- `0x180009778`
- `0x18000a2f4`
- `0x18004f9c0`

## string_xrefs

- `0x18004fa3e`: `Switching Protocols`
- `0x18004fa7e`: `Created`
- `0x18004fb5e`: `Moved Permanently`
- `0x18004fbfe`: `Temporary Redirect`
- `0x18004fdde`: `Request Uri Too Large`
- `0x18004febe`: `Service Unavailable`

## pseudocode

```c
// Hidden C++ exception states: #wind=40
__int64 __fastcall web::http::details::get_default_reason_phrase(__int64 a1, __int16 a2)
{
  __int64 *i; // rdx

  if ( dword_18009C9E0 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_18009C9E0);
    if ( dword_18009C9E0 == -1 )
    {
      std::wstring::wstring(qword_18009B0B8, L"Continue");
      word_18009B0D8 = 101;
      std::wstring::wstring(qword_18009B0E0, L"Switching Protocols");
      word_18009B100 = 200;
      std::wstring::wstring(qword_18009B108, L"OK");
      word_18009B128 = 201;
      std::wstring::wstring(qword_18009B130, L"Created");
      word_18009B150 = 202;
      std::wstring::wstring(qword_18009B158, L"Accepted");
      word_18009B178 = 203;
      std::wstring::wstring(qword_18009B180, L"Non-Authoritative Information");
      word_18009B1A0 = 204;
      std::wstring::wstring(qword_18009B1A8, L"No Content");
      word_18009B1C8 = 205;
      std::wstring::wstring(qword_18009B1D0, L"Reset Content");
      word_18009B1F0 = 206;
      std::wstring::wstring(qword_18009B1F8, L"Partial Content");
      word_18009B218 = 300;
      std::wstring::wstring(qword_18009B220, L"Multiple Choices");
      word_18009B240 = 301;
      std::wstring::wstring(qword_18009B248, L"Moved Permanently");
      word_18009B268 = 302;
      std::wstring::wstring(qword_18009B270, L"Found");
      word_18009B290 = 303;
      std::wstring::wstring(qword_18009B298, L"See Other");
      word_18009B2B8 = 304;
      std::wstring::wstring(qword_18009B2C0, L"Not Modified");
      word_18009B2E0 = 305;
      std::wstring::wstring(qword_18009B2E8, L"Use Proxy");
      word_18009B308 = 307;
      std::wstring::wstring(qword_18009B310, L"Temporary Redirect");
      word_18009B330 = 400;
      std::wstring::wstring(qword_18009B338, L"Bad Request");
      word_18009B358 = 401;
      std::wstring::wstring(qword_18009B360, L"Unauthorized");
      word_18009B380 = 402;
      std::wstring::wstring(qword_18009B388, L"Payment Required");
      word_18009B3A8 = 403;
      std::wstring::wstring(qword_18009B3B0, L"Forbidden");
      word_18009B3D0 = 404;
      std::wstring::wstring(qword_18009B3D8, L"Not Found");
      word_18009B3F8 = 405;
      std::wstring::wstring(qword_18009B400, L"Method Not Allowed");
      word_18009B420 = 406;
      std::wstring::wstring(qword_18009B428, L"Not Acceptable");
      word_18009B448 = 407;
      std::wstring::wstring(qword_18009B450, L"Proxy Authentication Required");
      word_18009B470 = 408;
      std::wstring::wstring(qword_18009B478, L"Request Time-out");
      word_18009B498 = 409;
      std::wstring::wstring(qword_18009B4A0, L"Conflict");
      word_18009B4C0 = 410;
      std::wstring::wstring(qword_18009B4C8, L"Gone");
      word_18009B4E8 = 411;
      std::wstring::wstring(qword_18009B4F0, L"Length Required");
      word_18009B510 = 412;
      std::wstring::wstring(qword_18009B518, L"Precondition Failed");
      word_18009B538 = 413;
      std::wstring::wstring(qword_18009B540, L"Request Entity Too Large");
      word_18009B560 = 414;
      std::wstring::wstring(qword_18009B568, L"Request Uri Too Large");
      word_18009B588 = 415;
      std::wstring::wstring(qword_18009B590, L"Unsupported Media Type");
      word_18009B5B0 = 416;
      std::wstring::wstring(qword_18009B5B8, L"Requested range not satisfiable");
      word_18009B5D8 = 417;
      std::wstring::wstring(qword_18009B5E0, L"Expectation Failed");
      word_18009B600 = 500;
      std::wstring::wstring(qword_18009B608, L"Internal Error");
      word_18009B628 = 501;
      std::wstring::wstring(qword_18009B630, L"Not Implemented");
      word_18009B650 = 502;
      std::wstring::wstring(qword_18009B658, L"Bad Gateway");
      word_18009B678 = 503;
      std::wstring::wstring(qword_18009B680, L"Service Unavailable");
      word_18009B6A0 = 504;
      std::wstring::wstring(qword_18009B6A8, L"Gateway Time-out");
      word_18009B6C8 = 505;
      std::wstring::wstring(qword_18009B6D0, L"HTTP Version not supported");
      atexit(web::http::details::get_default_reason_phrase_::_2_::_dynamic_atexit_destructor_for__idToPhraseMap__);
      Init_thread_footer(&dword_18009C9E0);
    }
  }
  std::wstring::wstring(a1);
  for ( i = &qword_18009B0B0; i != g_header_init_InitializeResultHeader; i += 5 )
  {
    if ( *(_WORD *)i == a2 )
    {
      std::wstring::operator=(a1, i + 1);
      return a1;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18004f9c0  mov     [rsp+arg_8], rbx
0x18004f9c5  mov     [rsp+arg_0], rcx
0x18004f9ca  push    rdi
0x18004f9cb  sub     rsp, 30h
0x18004f9cf  movzx   edi, dx
0x18004f9d2  mov     rbx, rcx
0x18004f9d5  mov     [rsp+38h+var_18], 0
0x18004f9dd  mov     r8d, cs:_tls_index
0x18004f9e4  mov     rax, gs:58h
0x18004f9ed  mov     ecx, 4
0x18004f9f2  mov     rax, [rax+r8*8]
0x18004f9f6  mov     eax, [rcx+rax]
0x18004f9f9  cmp     cs:dword_18009C9E0, eax
0x18004f9ff  jle     loc_18004FF2A
0x18004fa05  lea     rcx, dword_18009C9E0
0x18004fa0c  call    _Init_thread_header
0x18004fa11  cmp     cs:dword_18009C9E0, 0FFFFFFFFh
0x18004fa18  jnz     loc_18004FF2A
0x18004fa1e  lea     rdx, aContinue; "Continue"
0x18004fa25  lea     rcx, qword_18009B0B8
0x18004fa2c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004fa31  nop
0x18004fa32  mov     eax, 65h ; 'e'
0x18004fa37  mov     cs:word_18009B0D8, ax
0x18004fa3e  lea     rdx, aSwitchingProto; "Switching Protocols"
0x18004fa45  lea     rcx, qword_18009B0E0
0x18004fa4c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004fa51  nop
0x18004fa52  mov     eax, 0C8h
0x18004fa57  mov     cs:word_18009B100, ax
0x18004fa5e  lea     rdx, aOk; "OK"
0x18004fa65  lea     rcx, qword_18009B108
0x18004fa6c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004fa71  nop
0x18004fa72  mov     eax, 0C9h
0x18004fa77  mov     cs:word_18009B128, ax
0x18004fa7e  lea     rdx, aCreated; "Created"
0x18004fa85  lea     rcx, qword_18009B130
0x18004fa8c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004fa91  nop
0x18004fa92  mov     eax, 0CAh
0x18004fa97  mov     cs:word_18009B150, ax
0x18004fa9e  lea     rdx, aAccepted; "Accepted"
0x18004faa5  lea     rcx, qword_18009B158
0x18004faac  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004fab1  nop
0x18004fab2  mov     eax, 0CBh
0x18004fab7  mov     cs:word_18009B178, ax
0x18004fabe  lea     rdx, aNonAuthoritati; "Non-Authoritative Information"
0x18004fac5  lea     rcx, qword_18009B180
0x18004facc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004fad1  nop
0x18004fad2  mov     eax, 0CCh
0x18004fad7  mov     cs:word_18009B1A0, ax
0x18004fade  lea     rdx, aNoContent; "No Content"
0x18004fae5  lea     rcx, qword_18009B1A8
0x18004faec  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004faf1  nop
0x18004faf2  mov     eax, 0CDh
0x18004faf7  mov     cs:word_18009B1C8, ax
0x18004fafe  lea     rdx, aResetContent; "Reset Content"
0x18004fb05  lea     rcx, qword_18009B1D0
0x18004fb0c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004fb11  nop
0x18004fb12  mov     eax, 0CEh
0x18004fb17  mov     cs:word_18009B1F0, ax
0x18004fb1e  lea     rdx, aPartialContent; "Partial Content"
0x18004fb25  lea     rcx, qword_18009B1F8
0x18004fb2c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004fb31  nop
0x18004fb32  mov     eax, 12Ch
0x18004fb37  mov     cs:word_18009B218, ax
0x18004fb3e  lea     rdx, aMultipleChoice; "Multiple Choices"
0x18004fb45  lea     rcx, qword_18009B220
0x18004fb4c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004fb51  nop
0x18004fb52  mov     eax, 12Dh
0x18004fb57  mov     cs:word_18009B240, ax
0x18004fb5e  lea     rdx, aMovedPermanent; "Moved Permanently"
0x18004fb65  lea     rcx, qword_18009B248
0x18004fb6c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004fb71  nop
0x18004fb72  mov     eax, 12Eh
0x18004fb77  mov     cs:word_18009B268, ax
0x18004fb7e  lea     rdx, aFound; "Found"
0x18004fb85  lea     rcx, qword_18009B270
0x18004fb8c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004fb91  nop
0x18004fb92  mov     eax, 12Fh
0x18004fb97  mov     cs:word_18009B290, ax
0x18004fb9e  lea     rdx, aSeeOther; "See Other"
0x18004fba5  lea     rcx, qword_18009B298
0x18004fbac  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004fbb1  nop
0x18004fbb2  mov     eax, 130h
0x18004fbb7  mov     cs:word_18009B2B8, ax
0x18004fbbe  lea     rdx, aNotModified; "Not Modified"
0x18004fbc5  lea     rcx, qword_18009B2C0
0x18004fbcc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004fbd1  nop
0x18004fbd2  mov     eax, 131h
0x18004fbd7  mov     cs:word_18009B2E0, ax
0x18004fbde  lea     rdx, aUseProxy; "Use Proxy"
0x18004fbe5  lea     rcx, qword_18009B2E8
0x18004fbec  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004fbf1  nop
0x18004fbf2  mov     eax, 133h
0x18004fbf7  mov     cs:word_18009B308, ax
0x18004fbfe  lea     rdx, aTemporaryRedir; "Temporary Redirect"
0x18004fc05  lea     rcx, qword_18009B310
0x18004fc0c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004fc11  nop
0x18004fc12  mov     eax, 190h
0x18004fc17  mov     cs:word_18009B330, ax
0x18004fc1e  lea     rdx, aBadRequest; "Bad Request"
0x18004fc25  lea     rcx, qword_18009B338
0x18004fc2c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004fc31  nop
0x18004fc32  mov     eax, 191h
0x18004fc37  mov     cs:word_18009B358, ax
0x18004fc3e  lea     rdx, aUnauthorized; "Unauthorized"
0x18004fc45  lea     rcx, qword_18009B360
0x18004fc4c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004fc51  nop
0x18004fc52  mov     eax, 192h
0x18004fc57  mov     cs:word_18009B380, ax
0x18004fc5e  lea     rdx, aPaymentRequire; "Payment Required"
0x18004fc65  lea     rcx, qword_18009B388
0x18004fc6c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004fc71  nop
0x18004fc72  mov     eax, 193h
0x18004fc77  mov     cs:word_18009B3A8, ax
0x18004fc7e  lea     rdx, aForbidden; "Forbidden"
0x18004fc85  lea     rcx, qword_18009B3B0
0x18004fc8c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004fc91  nop
0x18004fc92  mov     eax, 194h
0x18004fc97  mov     cs:word_18009B3D0, ax
0x18004fc9e  lea     rdx, aNotFound; "Not Found"
0x18004fca5  lea     rcx, qword_18009B3D8
0x18004fcac  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004fcb1  nop
0x18004fcb2  mov     eax, 195h
0x18004fcb7  mov     cs:word_18009B3F8, ax
0x18004fcbe  lea     rdx, aMethodNotAllow; "Method Not Allowed"
0x18004fcc5  lea     rcx, qword_18009B400
0x18004fccc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004fcd1  nop
0x18004fcd2  mov     eax, 196h
0x18004fcd7  mov     cs:word_18009B420, ax
0x18004fcde  lea     rdx, aNotAcceptable; "Not Acceptable"
0x18004fce5  lea     rcx, qword_18009B428
0x18004fcec  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004fcf1  nop
0x18004fcf2  mov     eax, 197h
0x18004fcf7  mov     cs:word_18009B448, ax
0x18004fcfe  lea     rdx, aProxyAuthentic_0; "Proxy Authentication Required"
0x18004fd05  lea     rcx, qword_18009B450
0x18004fd0c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004fd11  nop
0x18004fd12  mov     eax, 198h
0x18004fd17  mov     cs:word_18009B470, ax
0x18004fd1e  lea     rdx, aRequestTimeOut; "Request Time-out"
0x18004fd25  lea     rcx, qword_18009B478
0x18004fd2c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004fd31  nop
0x18004fd32  mov     eax, 199h
0x18004fd37  mov     cs:word_18009B498, ax
0x18004fd3e  lea     rdx, aConflict; "Conflict"
0x18004fd45  lea     rcx, qword_18009B4A0
0x18004fd4c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004fd51  nop
0x18004fd52  mov     eax, 19Ah
0x18004fd57  mov     cs:word_18009B4C0, ax
0x18004fd5e  lea     rdx, aGone; "Gone"
0x18004fd65  lea     rcx, qword_18009B4C8
0x18004fd6c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004fd71  nop
0x18004fd72  mov     eax, 19Bh
0x18004fd77  mov     cs:word_18009B4E8, ax
0x18004fd7e  lea     rdx, aLengthRequired; "Length Required"
0x18004fd85  lea     rcx, qword_18009B4F0
0x18004fd8c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004fd91  nop
0x18004fd92  mov     eax, 19Ch
0x18004fd97  mov     cs:word_18009B510, ax
0x18004fd9e  lea     rdx, aPreconditionFa; "Precondition Failed"
0x18004fda5  lea     rcx, qword_18009B518
0x18004fdac  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004fdb1  nop
0x18004fdb2  mov     eax, 19Dh
0x18004fdb7  mov     cs:word_18009B538, ax
0x18004fdbe  lea     rdx, aRequestEntityT; "Request Entity Too Large"
0x18004fdc5  lea     rcx, qword_18009B540
0x18004fdcc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004fdd1  nop
0x18004fdd2  mov     eax, 19Eh
0x18004fdd7  mov     cs:word_18009B560, ax
0x18004fdde  lea     rdx, aRequestUriTooL; "Request Uri Too Large"
0x18004fde5  lea     rcx, qword_18009B568
0x18004fdec  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004fdf1  nop
0x18004fdf2  mov     eax, 19Fh
0x18004fdf7  mov     cs:word_18009B588, ax
0x18004fdfe  lea     rdx, aUnsupportedMed; "Unsupported Media Type"
0x18004fe05  lea     rcx, qword_18009B590
0x18004fe0c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004fe11  nop
0x18004fe12  mov     eax, 1A0h
0x18004fe17  mov     cs:word_18009B5B0, ax
0x18004fe1e  lea     rdx, aRequestedRange; "Requested range not satisfiable"
0x18004fe25  lea     rcx, qword_18009B5B8
0x18004fe2c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004fe31  nop
0x18004fe32  mov     eax, 1A1h
0x18004fe37  mov     cs:word_18009B5D8, ax
0x18004fe3e  lea     rdx, aExpectationFai; "Expectation Failed"
0x18004fe45  lea     rcx, qword_18009B5E0
0x18004fe4c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004fe51  nop
0x18004fe52  mov     eax, 1F4h
0x18004fe57  mov     cs:word_18009B600, ax
0x18004fe5e  lea     rdx, aInternalError; "Internal Error"
0x18004fe65  lea     rcx, qword_18009B608
0x18004fe6c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004fe71  nop
0x18004fe72  mov     eax, 1F5h
0x18004fe77  mov     cs:word_18009B628, ax
0x18004fe7e  lea     rdx, aNotImplemented; "Not Implemented"
0x18004fe85  lea     rcx, qword_18009B630
0x18004fe8c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004fe91  nop
0x18004fe92  mov     eax, 1F6h
0x18004fe97  mov     cs:word_18009B650, ax
0x18004fe9e  lea     rdx, aBadGateway; "Bad Gateway"
0x18004fea5  lea     rcx, qword_18009B658
0x18004feac  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004feb1  nop
0x18004feb2  mov     eax, 1F7h
0x18004feb7  mov     cs:word_18009B678, ax
0x18004febe  lea     rdx, aServiceUnavail; "Service Unavailable"
0x18004fec5  lea     rcx, qword_18009B680
0x18004fecc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004fed1  nop
0x18004fed2  mov     eax, 1F8h
0x18004fed7  mov     cs:word_18009B6A0, ax
0x18004fede  lea     rdx, aGatewayTimeOut; "Gateway Time-out"
0x18004fee5  lea     rcx, qword_18009B6A8
0x18004feec  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004fef1  nop
0x18004fef2  mov     eax, 1F9h
0x18004fef7  mov     cs:word_18009B6C8, ax
0x18004fefe  lea     rdx, aHttpVersionNot; "HTTP Version not supported"
0x18004ff05  lea     rcx, qword_18009B6D0
0x18004ff0c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004ff11  nop
0x18004ff12  lea     rcx, _web__http__details__get_default_reason_phrase____2____dynamic_atexit_destructor_for__idToPhraseMap__; void (__cdecl *)()
0x18004ff19  call    atexit
0x18004ff1e  lea     rcx, dword_18009C9E0
0x18004ff25  call    _Init_thread_footer
0x18004ff2a  mov     rcx, rbx
0x18004ff2d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18004ff32  mov     [rsp+38h+var_18], 1
0x18004ff3a  lea     rdx, qword_18009B0B0
0x18004ff41  lea     rax, g_header_init_InitializeResultHeader
0x18004ff48  cmp     rdx, rax
0x18004ff4b  jz      short loc_18004FF64
0x18004ff4d  cmp     [rdx], di
0x18004ff50  jz      short loc_18004FF58
0x18004ff52  add     rdx, 28h ; '('
0x18004ff56  jmp     short loc_18004FF41
0x18004ff58  add     rdx, 8
0x18004ff5c  mov     rcx, rbx
0x18004ff5f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18004ff64  mov     rax, rbx
0x18004ff67  mov     rbx, [rsp+38h+arg_8]
0x18004ff6c  add     rsp, 30h
0x18004ff70  pop     rdi
0x18004ff71  retn
```
