# MakePostRequest(TraceLoggingCorrelationVector *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,web::json::value const &)

- ea: `0x1800354bc`
- end: `0x180035713`
- name: `?MakePostRequest@@YA?AVvalue@json@web@@PEAVTraceLoggingCorrelationVector@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV123@@Z`
- size: `599`
- prototype: ``
- caller_count: `3`
- callee_count: `17`
- tags: `registry_config`

## callers

- `0x18002fd70`
- `0x180032cfc`
- `0x18003571c`

## callees

- `0x1800026b0`
- `0x180005fa0`
- `0x1800093f0`
- `0x18000d640`
- `0x18000dc5b`
- `0x18002d5f8`
- `0x18002d674`
- `0x180030aac`
- `0x180034948`
- `0x180034bd4`
- `0x180034d14`
- `0x1800354bc`
- `0x180036bfc`
- `0x1800374d4`
- `0x180037d04`
- `0x18004730c`
- `0x180048c0c`

## string_xrefs

- `0x1800356a4`: `application/json`
- `0x1800356bb`: `application/json`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
struct TraceLoggingCorrelationVector *__fastcall MakePostRequest(
        struct TraceLoggingCorrelationVector *a1,
        struct HttpRequest *a2,
        const unsigned __int16 *a3,
        __int64 a4)
{
  const unsigned __int16 *v8; // r9
  const WCHAR *v9; // rax
  const unsigned __int8 *v10; // rdx
  _QWORD *v11; // rsi
  unsigned __int64 v12; // rax
  char *v13; // rbx
  __int64 v14; // rax
  __int64 v15; // rdi
  _QWORD *v16; // rax
  __int64 v17; // rax
  _WORD *v18; // rbx
  struct web::json::value *v19; // r9
  __int128 v21; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v22; // [rsp+40h] [rbp-C0h]
  unsigned __int8 *Src[4]; // [rsp+50h] [rbp-B0h] BYREF
  char *v24[4]; // [rsp+70h] [rbp-90h] BYREF
  IMalloc v25[31]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v26[24]; // [rsp+188h] [rbp+88h] BYREF

  web::json::value::value(a1);
  PTIUtils::CreateHttpRequest((char *)v25, a3, L"POST", v8);
  v9 = (const WCHAR *)web::json::value::serialize(a4, v24);
  ConvertWideToUtf8(Src, v9);
  v10 = (const unsigned __int8 *)Src;
  if ( Src[3] > (unsigned __int8 *)0xF )
    v10 = Src[0];
  HttpRequest::SetBody(v25, v10, (unsigned __int64)Src[2]);
  v21 = 0;
  v22 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v21, L"Content-Type", 0xCu);
  v11 = (_QWORD *)std::map<std::wstring,std::wstring>::operator[](v26, &v21);
  v12 = v11[2];
  if ( v11[3] > 7u )
    v11 = (_QWORD *)*v11;
  if ( v12 < 7 || (v13 = (char *)v11 + 2 * v12, v14 = _std_search_2(v11, v13, L"charset"), (char *)v14 == v13) )
    v15 = -1;
  else
    v15 = (v14 - (__int64)v11) >> 1;
  std::wstring::_Tidy_deallocate((char **)&v21);
  if ( v15 == -1 )
  {
    v21 = 0;
    v22 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v21, L"Content-Type", 0xCu);
    v16 = (_QWORD *)std::map<std::wstring,std::wstring>::operator[](v26, &v21);
    std::wstring::_Append<unsigned short>(v16, L"; charset=utf-8", 0xFu);
    std::wstring::_Tidy_deallocate((char **)&v21);
  }
  std::string::_Tidy_deallocate(Src);
  std::wstring::_Tidy_deallocate(v24);
  v21 = 0;
  v22 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v21, L"Content-Type", 0xCu);
  v17 = std::map<std::wstring,std::wstring>::operator[](v26, &v21);
  if ( *(_QWORD *)(v17 + 24) < 0x10u )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v17);
  }
  else
  {
    v18 = *(_WORD **)v17;
    *(_QWORD *)(v17 + 16) = 16;
    memmove_0(v18, L"application/json", 0x20u);
    v18[16] = 0;
  }
  std::wstring::_Tidy_deallocate((char **)&v21);
  PTIUtils::SendRequest((PTIUtils *)v25, a2, a1, v19);
  HttpRequest::~HttpRequest((HttpRequest *)v25);
  return a1;
}

```

## disassembly

```asm
0x1800354bc  push    rbp
0x1800354be  push    rbx
0x1800354bf  push    rsi
0x1800354c0  push    rdi
0x1800354c1  push    r13
0x1800354c3  push    r14
0x1800354c5  push    r15
0x1800354c7  lea     rbp, [rsp-0B0h]
0x1800354cf  sub     rsp, 1B0h
0x1800354d6  mov     rax, cs:__security_cookie
0x1800354dd  xor     rax, rsp
0x1800354e0  mov     [rbp+0E0h+var_40], rax
0x1800354e7  mov     rdi, r9
0x1800354ea  mov     rbx, r8
0x1800354ed  mov     r15, rdx
0x1800354f0  mov     r14, rcx
0x1800354f3  mov     [rsp+1E0h+var_1B8], rcx
0x1800354f8  mov     [rsp+1E0h+var_1C0], 0
0x180035500  call    ??0value@json@web@@QEAA@XZ; web::json::value::value(void)
0x180035505  mov     [rsp+1E0h+var_1C0], 1
0x18003550d  lea     r8, aPost; "POST"
0x180035514  mov     rdx, rbx
0x180035517  lea     rcx, [rbp+0E0h+var_150]
0x18003551b  call    ?CreateHttpRequest@PTIUtils@@YA?AVHttpRequest@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; PTIUtils::CreateHttpRequest(std::wstring const &,ushort const *)
0x180035520  nop
0x180035521  lea     rdx, [rsp+1E0h+var_170]
0x180035526  mov     rcx, rdi
0x180035529  call    ?serialize@value@json@web@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; web::json::value::serialize(void)
0x18003552e  nop
0x18003552f  mov     rdx, rax; lpWideCharStr
0x180035532  lea     rcx, [rsp+1E0h+Src]; Src
0x180035537  call    ?ConvertWideToUtf8@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; ConvertWideToUtf8(std::wstring const &)
0x18003553c  nop
0x18003553d  lea     rdx, [rsp+1E0h+Src]
0x180035542  cmp     [rsp+1E0h+var_178], 0Fh
0x180035548  cmova   rdx, [rsp+1E0h+Src]; unsigned __int8 *
0x18003554e  mov     r8, [rsp+1E0h+var_180]; unsigned __int64
0x180035553  lea     rcx, [rbp+0E0h+var_150]; this
0x180035557  call    ?SetBody@HttpRequest@@QEAAXPEBE_K@Z; HttpRequest::SetBody(uchar const *,unsigned __int64)
0x18003555c  xorps   xmm0, xmm0
0x18003555f  movups  [rsp+1E0h+var_1B0], xmm0
0x180035564  xorps   xmm1, xmm1
0x180035567  movdqu  [rsp+1E0h+var_1A0], xmm1
0x18003556d  mov     r13d, 0Ch
0x180035573  mov     r8d, r13d
0x180035576  lea     rdx, aContentType; "Content-Type"
0x18003557d  lea     rcx, [rsp+1E0h+var_1B0]
0x180035582  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180035587  nop
0x180035588  lea     rdx, [rsp+1E0h+var_1B0]
0x18003558d  lea     rcx, [rbp+0E0h+var_58]
0x180035594  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x180035599  mov     rsi, rax
0x18003559c  mov     rax, [rax+10h]
0x1800355a0  lea     r9d, [r13-5]
0x1800355a4  cmp     [rsi+18h], r9
0x1800355a8  jbe     short loc_1800355AD
0x1800355aa  mov     rsi, [rsi]
0x1800355ad  cmp     rax, r9
0x1800355b0  jb      short loc_1800355D8
0x1800355b2  lea     rbx, [rsi+rax*2]
0x1800355b6  lea     r8, aCharset; "charset"
0x1800355bd  mov     rdx, rbx
0x1800355c0  mov     rcx, rsi
0x1800355c3  call    __std_search_2
0x1800355c8  mov     rdi, rax
0x1800355cb  cmp     rax, rbx
0x1800355ce  jz      short loc_1800355D8
0x1800355d0  sub     rdi, rsi
0x1800355d3  sar     rdi, 1
0x1800355d6  jmp     short loc_1800355DC
0x1800355d8  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800355dc  lea     rcx, [rsp+1E0h+var_1B0]
0x1800355e1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800355e6  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800355ea  jnz     short loc_180035642
0x1800355ec  xorps   xmm0, xmm0
0x1800355ef  movups  [rsp+1E0h+var_1B0], xmm0
0x1800355f4  xorps   xmm1, xmm1
0x1800355f7  movdqu  [rsp+1E0h+var_1A0], xmm1
0x1800355fd  mov     r8, r13
0x180035600  lea     rdx, aContentType; "Content-Type"
0x180035607  lea     rcx, [rsp+1E0h+var_1B0]
0x18003560c  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180035611  nop
0x180035612  lea     rdx, [rsp+1E0h+var_1B0]
0x180035617  lea     rcx, [rbp+0E0h+var_58]
0x18003561e  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x180035623  lea     r8d, [rdi+10h]
0x180035627  lea     rdx, aCharsetUtf8; "; charset=utf-8"
0x18003562e  mov     rcx, rax; Src
0x180035631  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180035636  nop
0x180035637  lea     rcx, [rsp+1E0h+var_1B0]
0x18003563c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180035641  nop
0x180035642  lea     rcx, [rsp+1E0h+Src]
0x180035647  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18003564c  nop
0x18003564d  lea     rcx, [rsp+1E0h+var_170]
0x180035652  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180035657  xorps   xmm0, xmm0
0x18003565a  movups  [rsp+1E0h+var_1B0], xmm0
0x18003565f  xorps   xmm1, xmm1
0x180035662  movdqu  [rsp+1E0h+var_1A0], xmm1
0x180035668  mov     r8, r13
0x18003566b  lea     rdx, aContentType; "Content-Type"
0x180035672  lea     rcx, [rsp+1E0h+var_1B0]
0x180035677  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18003567c  nop
0x18003567d  lea     rdx, [rsp+1E0h+var_1B0]
0x180035682  lea     rcx, [rbp+0E0h+var_58]
0x180035689  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x18003568e  mov     edx, 10h
0x180035693  cmp     [rax+18h], rdx
0x180035697  jb      short loc_1800356BB
0x180035699  mov     rbx, [rax]
0x18003569c  mov     [rax+10h], rdx
0x1800356a0  lea     r8d, [rdx+10h]; Size
0x1800356a4  lea     rdx, aApplicationJso; "application/json"
0x1800356ab  mov     rcx, rbx; void *
0x1800356ae  call    memmove_0
0x1800356b3  xor     eax, eax
0x1800356b5  mov     [rbx+20h], ax
0x1800356b9  jmp     short loc_1800356CB
0x1800356bb  lea     r9, aApplicationJso; "application/json"
0x1800356c2  mov     rcx, rax
0x1800356c5  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x1800356ca  nop
0x1800356cb  lea     rcx, [rsp+1E0h+var_1B0]
0x1800356d0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800356d5  mov     r8, r14; struct TraceLoggingCorrelationVector *
0x1800356d8  mov     rdx, r15; struct HttpRequest *
0x1800356db  lea     rcx, [rbp+0E0h+var_150]; this
0x1800356df  call    ?SendRequest@PTIUtils@@YAXAEAVHttpRequest@@PEAVTraceLoggingCorrelationVector@@PEAVvalue@json@web@@@Z; PTIUtils::SendRequest(HttpRequest &,TraceLoggingCorrelationVector *,web::json::value *)
0x1800356e4  nop
0x1800356e5  lea     rcx, [rbp+0E0h+var_150]; this
0x1800356e9  call    ??1HttpRequest@@QEAA@XZ; HttpRequest::~HttpRequest(void)
0x1800356ee  mov     rax, r14
0x1800356f1  mov     rcx, [rbp+0E0h+var_40]
0x1800356f8  xor     rcx, rsp; StackCookie
0x1800356fb  call    __security_check_cookie
0x180035700  add     rsp, 1B0h
0x180035707  pop     r15
0x180035709  pop     r14
0x18003570b  pop     r13
0x18003570d  pop     rdi
0x18003570e  pop     rsi
0x18003570f  pop     rbx
0x180035710  pop     rbp
0x180035711  retn
```
