# Json::OurReader::parse(ushort const *,ushort const *,Json::Value &,bool)

- ea: `0x1800381b8`
- end: `0x180038377`
- name: `?parse@OurReader@Json@@QEAA_NPEBG0AEAVValue@2@_N@Z`
- size: `447`
- prototype: `bool __usercall@<al>(Json::OurReader *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, struct Json::Value *@<r9>, bool)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180038140`

## callees

- `0x1800094a0`
- `0x18000c354`
- `0x18000c3ac`
- `0x18000c850`
- `0x180035f40`
- `0x1800362f4`
- `0x180036e50`
- `0x180036ea0`
- `0x1800381b8`
- `0x18003840c`
- `0x180039080`
- `0x180039958`

## string_xrefs

- `0x180038321`: `A valid JSON document must be either an array or an object value.`
- `0x18003829f`: `Extra non-whitespace after JSON value.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall Json::OurReader::parse(
        Json::OurReader *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct Json::Value *a4,
        bool a5)
{
  bool Value; // si
  __int128 v11; // [rsp+30h] [rbp-50h] BYREF
  const unsigned __int16 *v12; // [rsp+40h] [rbp-40h]
  struct Json::Value *v13; // [rsp+48h] [rbp-38h] BYREF
  _BYTE v14[32]; // [rsp+50h] [rbp-30h] BYREF

  *((_QWORD *)this + 14) = a2;
  *((_QWORD *)this + 15) = a3;
  *((_BYTE *)this + 200) = *((_BYTE *)this + 188) != 0 && a5;
  *((_QWORD *)this + 16) = a2;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 18) = 0;
  std::wstring::assign((char *)this + 152, &qword_180048C70);
  std::deque<Json::OurReader::ErrorInfo>::_Tidy((char *)this + 40);
  while ( *((_QWORD *)this + 4) )
    std::deque<Json::Value *>::pop_back(this);
  v13 = a4;
  std::deque<Json::Value *>::_Emplace_back_internal<Json::Value *>((__int64)this, &v13);
  *((_DWORD *)this + 46) = 0;
  Value = Json::OurReader::readValue(this);
  v11 = 0;
  v12 = 0;
  Json::OurReader::skipCommentTokens(this, (struct Json::OurReader::Token *)&v11);
  if ( *((_BYTE *)this + 193) && (_DWORD)v11 != 16 && (_DWORD)v11 )
  {
    std::wstring::wstring((__int64)v14, (__int64)L"Extra non-whitespace after JSON value.");
    Json::OurReader::addError((_DWORD)this, 10, (unsigned int)v14, (unsigned int)&v11, 0);
LABEL_8:
    std::wstring::_Tidy_deallocate(v14);
    return 0;
  }
  if ( *((_BYTE *)this + 200) && *((_QWORD *)this + 21) )
    Json::Value::setComment(a4, (char *)this + 152, 2);
  if ( *((_BYTE *)this + 189) && (unsigned __int8)(*((_BYTE *)a4 + 8) - 6) > 1u )
  {
    LODWORD(v11) = 16;
    *((_QWORD *)&v11 + 1) = a2;
    v12 = a3;
    std::wstring::wstring((__int64)v14, (__int64)L"A valid JSON document must be either an array or an object value.");
    Json::OurReader::addError((_DWORD)this, 1, (unsigned int)v14, (unsigned int)&v11, 0);
    goto LABEL_8;
  }
  return Value;
}

```

## disassembly

```asm
0x1800381b8  push    rbp
0x1800381ba  push    rbx
0x1800381bb  push    rsi
0x1800381bc  push    rdi
0x1800381bd  push    r12
0x1800381bf  push    r14
0x1800381c1  push    r15
0x1800381c3  mov     rbp, rsp
0x1800381c6  sub     rsp, 80h
0x1800381cd  mov     rax, cs:__security_cookie
0x1800381d4  xor     rax, rsp
0x1800381d7  mov     [rbp+var_10], rax
0x1800381db  mov     rdi, r9
0x1800381de  mov     r12, r8
0x1800381e1  mov     r15, rdx
0x1800381e4  mov     rbx, rcx
0x1800381e7  mov     [rcx+70h], rdx
0x1800381eb  mov     [rcx+78h], r8
0x1800381ef  mov     al, [rcx+0BCh]
0x1800381f5  neg     al
0x1800381f7  sbb     cl, cl
0x1800381f9  and     cl, [rbp+arg_20]
0x1800381fc  mov     [rbx+0C8h], cl
0x180038202  mov     [rbx+80h], rdx
0x180038209  mov     qword ptr [rbx+88h], 0
0x180038214  mov     qword ptr [rbx+90h], 0
0x18003821f  lea     r14, [rbx+98h]
0x180038226  lea     rdx, qword_180048C70
0x18003822d  mov     rcx, r14
0x180038230  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180038235  lea     rcx, [rbx+28h]
0x180038239  call    ?_Tidy@?$deque@VErrorInfo@OurReader@Json@@V?$allocator@VErrorInfo@OurReader@Json@@@std@@@std@@AEAAXXZ; std::deque<Json::OurReader::ErrorInfo>::_Tidy(void)
0x18003823e  mov     rcx, rbx
0x180038241  cmp     qword ptr [rbx+20h], 0
0x180038246  jz      short loc_18003824F
0x180038248  call    ?pop_back@?$deque@PEAVValue@Json@@V?$allocator@PEAVValue@Json@@@std@@@std@@QEAAXXZ; std::deque<Json::Value *>::pop_back(void)
0x18003824d  jmp     short loc_18003823E
0x18003824f  mov     [rbp+var_38], rdi
0x180038253  lea     rdx, [rbp+var_38]
0x180038257  call    ??$_Emplace_back_internal@PEAVValue@Json@@@?$deque@PEAVValue@Json@@V?$allocator@PEAVValue@Json@@@std@@@std@@AEAAX$$QEAPEAVValue@Json@@@Z; std::deque<Json::Value *>::_Emplace_back_internal<Json::Value *>(Json::Value * &&)
0x18003825c  mov     dword ptr [rbx+0B8h], 0
0x180038266  mov     rcx, rbx; this
0x180038269  call    ?readValue@OurReader@Json@@AEAA_NXZ; Json::OurReader::readValue(void)
0x18003826e  mov     sil, al
0x180038271  xorps   xmm0, xmm0
0x180038274  xor     eax, eax
0x180038276  movups  [rbp+var_50], xmm0
0x18003827a  mov     [rbp+var_40], rax
0x18003827e  lea     rdx, [rbp+var_50]; struct Json::OurReader::Token *
0x180038282  mov     rcx, rbx; this
0x180038285  call    ?skipCommentTokens@OurReader@Json@@AEAAXAEAVToken@12@@Z; Json::OurReader::skipCommentTokens(Json::OurReader::Token &)
0x18003828a  cmp     byte ptr [rbx+0C1h], 0
0x180038291  jz      short loc_1800382DC
0x180038293  mov     ecx, dword ptr [rbp+var_50]
0x180038296  cmp     ecx, 10h
0x180038299  jz      short loc_1800382DC
0x18003829b  test    ecx, ecx
0x18003829d  jz      short loc_1800382DC
0x18003829f  lea     rdx, aExtraNonWhites; "Extra non-whitespace after JSON value."
0x1800382a6  lea     rcx, [rbp+var_30]
0x1800382aa  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800382af  nop
0x1800382b0  mov     [rsp+80h+var_60], 0
0x1800382b9  lea     r9, [rbp+var_50]
0x1800382bd  lea     r8, [rbp+var_30]
0x1800382c1  mov     edx, 0Ah
0x1800382c6  mov     rcx, rbx
0x1800382c9  call    ?addError@OurReader@Json@@AEAA_NW4JsonErrorType@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAVToken@12@PEBG@Z; Json::OurReader::addError(Json::JsonErrorType,std::wstring const &,Json::OurReader::Token &,ushort const *)
0x1800382ce  nop
0x1800382cf  lea     rcx, [rbp+var_30]
0x1800382d3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800382d8  xor     al, al
0x1800382da  jmp     short loc_180038359
0x1800382dc  cmp     byte ptr [rbx+0C8h], 0
0x1800382e3  jz      short loc_180038300
0x1800382e5  cmp     qword ptr [rbx+0A8h], 0
0x1800382ed  jz      short loc_180038300
0x1800382ef  mov     r8d, 2
0x1800382f5  mov     rdx, r14
0x1800382f8  mov     rcx, rdi
0x1800382fb  call    ?setComment@Value@Json@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4CommentPlacement@2@@Z; Json::Value::setComment(std::wstring const &,Json::CommentPlacement)
0x180038300  cmp     byte ptr [rbx+0BDh], 0
0x180038307  jz      short loc_180038356
0x180038309  mov     al, [rdi+8]
0x18003830c  sub     al, 6
0x18003830e  cmp     al, 1
0x180038310  jbe     short loc_180038356
0x180038312  mov     dword ptr [rbp+var_50], 10h
0x180038319  mov     qword ptr [rbp+var_50+8], r15
0x18003831d  mov     [rbp+var_40], r12
0x180038321  lea     rdx, aAValidJsonDocu; "A valid JSON document must be either an"...
0x180038328  lea     rcx, [rbp+var_30]
0x18003832c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180038331  nop
0x180038332  mov     [rsp+80h+var_60], 0
0x18003833b  lea     r9, [rbp+var_50]
0x18003833f  lea     r8, [rbp+var_30]
0x180038343  mov     edx, 1
0x180038348  mov     rcx, rbx
0x18003834b  call    ?addError@OurReader@Json@@AEAA_NW4JsonErrorType@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAVToken@12@PEBG@Z; Json::OurReader::addError(Json::JsonErrorType,std::wstring const &,Json::OurReader::Token &,ushort const *)
0x180038350  nop
0x180038351  jmp     loc_1800382CF
0x180038356  mov     al, sil
0x180038359  mov     rcx, [rbp+var_10]
0x18003835d  xor     rcx, rsp; StackCookie
0x180038360  call    __security_check_cookie
0x180038365  add     rsp, 80h
0x18003836c  pop     r15
0x18003836e  pop     r14
0x180038370  pop     r12
0x180038372  pop     rdi
0x180038373  pop     rsi
0x180038374  pop     rbx
0x180038375  pop     rbp
0x180038376  retn
```
