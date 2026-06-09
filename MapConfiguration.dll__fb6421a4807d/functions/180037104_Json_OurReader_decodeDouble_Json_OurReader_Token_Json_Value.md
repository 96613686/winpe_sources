# Json::OurReader::decodeDouble(Json::OurReader::Token &,Json::Value &)

- ea: `0x180037104`
- end: `0x1800372c6`
- name: `?decodeDouble@OurReader@Json@@AEAA_NAEAVToken@12@AEAVValue@2@@Z`
- size: `450`
- prototype: `bool __fastcall(Json::OurReader *__hidden this, struct Json::OurReader::Token *, struct Json::Value *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x180037398`

## callees

- `0x1800094a0`
- `0x180009bc0`
- `0x18000b215`
- `0x18000c2f8`
- `0x18000c354`
- `0x18000c850`
- `0x18000cf90`
- `0x1800233c8`
- `0x180034630`
- `0x180036160`
- `0x180036ea0`
- `0x180037104`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstod` at `0x1800371b8`
- `api-ms-win-crt-private-l1-1-0!_o_wcstod` at `0x1800371e6`
- `api-ms-win-crt-private-l1-1-0!_o_wcstod` at `0x1800371b8`
- `api-ms-win-crt-private-l1-1-0!_o_wcstod` at `0x1800371e6`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180037184`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800371f9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180037184`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800371f9`

## string_xrefs

- `0x180037145`: `Unable to parse token length`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
char __fastcall Json::OurReader::decodeDouble(
        Json::OurReader *this,
        struct Json::OurReader::Token *a2,
        struct Json::Value *a3)
{
  int v5; // r15d
  __int64 v6; // rsi
  char v7; // bl
  double *v8; // rcx
  const void *v10; // rdx
  size_t v11; // rsi
  double v12; // xmm6_8
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  int v16; // eax
  _BYTE v17[32]; // [rsp+40h] [rbp-81h] BYREF
  _BYTE v18[40]; // [rsp+60h] [rbp-61h] BYREF
  double v19; // [rsp+88h] [rbp-39h] BYREF
  int v20; // [rsp+90h] [rbp-31h]
  __int128 v21; // [rsp+98h] [rbp-29h]
  __int64 v22; // [rsp+A8h] [rbp-19h]

  v5 = (int)this;
  v6 = (__int64)(*((_QWORD *)a2 + 2) - *((_QWORD *)a2 + 1)) >> 1;
  if ( v6 < 0 )
  {
    std::wstring::wstring((__int64)v17, (__int64)L"Unable to parse token length");
    v7 = Json::OurReader::addError(v5, 9, (unsigned int)v17, (_DWORD)a2, 0);
    v8 = (double *)v17;
LABEL_3:
    std::wstring::_Tidy_deallocate(v8);
    return v7;
  }
  *(_DWORD *)_o__errno() = 0;
  v10 = (const void *)*((_QWORD *)a2 + 1);
  if ( v6 > 32 )
  {
    std::wstring::wstring(v17, v10, *((_QWORD *)a2 + 2));
    v13 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v17);
    v12 = _o_wcstod(v13, 0);
    std::wstring::_Tidy_deallocate(v17);
  }
  else
  {
    v11 = 2 * v6;
    memcpy_0(&v19, v10, v11);
    if ( v11 >= 0x42 )
      _report_rangecheckfailure();
    *(_WORD *)((char *)&v19 + v11) = 0;
    v12 = _o_wcstod(&v19, 0);
  }
  if ( *(_DWORD *)_o__errno() )
  {
    v14 = std::wstring::wstring(&v19, *((_QWORD *)a2 + 1), *((_QWORD *)a2 + 2));
    v15 = std::operator+<unsigned short>(v18, L"'", v14);
    v16 = std::operator+<unsigned short>(v17, v15, L"' is not a number.");
    v7 = Json::OurReader::addError(v5, 9, v16, (_DWORD)a2, 0);
    std::wstring::_Tidy_deallocate(v17);
    std::wstring::_Tidy_deallocate(v18);
    v8 = &v19;
    goto LABEL_3;
  }
  LOBYTE(v20) = 3;
  v20 &= ~0x100u;
  v21 = 0;
  v22 = 0;
  v19 = v12;
  Json::Value::operator=(a3, &v19);
  return 1;
}

```

## disassembly

```asm
0x180037104  mov     rax, rsp
0x180037107  mov     [rax+20h], rbx
0x18003710b  push    rbp
0x18003710c  push    rsi
0x18003710d  push    rdi
0x18003710e  push    r14
0x180037110  push    r15
0x180037112  lea     rbp, [rax-5Fh]
0x180037116  sub     rsp, 0F0h
0x18003711d  movaps  xmmword ptr [rax-38h], xmm6
0x180037121  mov     rax, cs:__security_cookie
0x180037128  xor     rax, rsp
0x18003712b  mov     [rbp+57h+var_40], rax
0x18003712f  mov     r14, r8
0x180037132  mov     rdi, rdx
0x180037135  mov     r15, rcx
0x180037138  mov     rsi, [rdx+10h]
0x18003713c  sub     rsi, [rdx+8]
0x180037140  sar     rsi, 1
0x180037143  jns     short loc_180037184
0x180037145  lea     rdx, aUnableToParseT; "Unable to parse token length"
0x18003714c  lea     rcx, [rsp+110h+var_D8]
0x180037151  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180037156  nop
0x180037157  xor     ebx, ebx
0x180037159  mov     [rsp+110h+var_F0], rbx
0x18003715e  mov     r9, rdi
0x180037161  lea     r8, [rsp+110h+var_D8]
0x180037166  lea     edx, [rbx+9]
0x180037169  mov     rcx, r15
0x18003716c  call    ?addError@OurReader@Json@@AEAA_NW4JsonErrorType@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAVToken@12@PEBG@Z; Json::OurReader::addError(Json::JsonErrorType,std::wstring const &,Json::OurReader::Token &,ushort const *)
0x180037171  mov     bl, al
0x180037173  lea     rcx, [rsp+110h+var_D8]
0x180037178  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003717d  mov     al, bl
0x18003717f  jmp     loc_18003729E
0x180037184  call    cs:__imp__o__errno
0x18003718a  xor     ebx, ebx
0x18003718c  mov     [rax], ebx
0x18003718e  mov     rdx, [rdi+8]; Src
0x180037192  cmp     rsi, 20h ; ' '
0x180037196  jg      short loc_1800371C9
0x180037198  add     rsi, rsi
0x18003719b  mov     r8, rsi; Size
0x18003719e  lea     rcx, [rbp+57h+var_90]; void *
0x1800371a2  call    memcpy_0
0x1800371a7  cmp     rsi, 42h ; 'B'
0x1800371ab  jnb     short loc_1800371C3
0x1800371ad  mov     word ptr [rbp+rsi+57h+var_90], bx
0x1800371b2  xor     edx, edx
0x1800371b4  lea     rcx, [rbp+57h+var_90]
0x1800371b8  call    cs:__imp__o_wcstod
0x1800371be  movaps  xmm6, xmm0
0x1800371c1  jmp     short loc_1800371F9
0x1800371c3  call    __report_rangecheckfailure
0x1800371c9  mov     r8, [rdi+10h]
0x1800371cd  lea     rcx, [rsp+110h+var_D8]
0x1800371d2  call    ??$?0PEAG$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEAG0AEBV?$allocator@G@1@@Z; std::wstring::wstring(ushort *,ushort *,std::allocator<ushort> const &)
0x1800371d7  lea     rcx, [rsp+110h+var_D8]
0x1800371dc  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800371e1  mov     rcx, rax
0x1800371e4  xor     edx, edx
0x1800371e6  call    cs:__imp__o_wcstod
0x1800371ec  movaps  xmm6, xmm0
0x1800371ef  lea     rcx, [rsp+110h+var_D8]
0x1800371f4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800371f9  call    cs:__imp__o__errno
0x1800371ff  cmp     [rax], ebx
0x180037201  jz      short loc_180037276
0x180037203  mov     r8, [rdi+10h]
0x180037207  mov     rdx, [rdi+8]
0x18003720b  lea     rcx, [rbp+57h+var_90]
0x18003720f  call    ??$?0PEAG$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEAG0AEBV?$allocator@G@1@@Z; std::wstring::wstring(ushort *,ushort *,std::allocator<ushort> const &)
0x180037214  nop
0x180037215  mov     r8, rax
0x180037218  lea     rdx, asc_180069580; "'"
0x18003721f  lea     rcx, [rbp+57h+var_B8]
0x180037223  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG$$QEAV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring &&)
0x180037228  nop
0x180037229  lea     r8, aIsNotANumber; "' is not a number."
0x180037230  mov     rdx, rax
0x180037233  lea     rcx, [rsp+110h+var_D8]
0x180037238  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18003723d  nop
0x18003723e  mov     [rsp+110h+var_F0], rbx
0x180037243  mov     r9, rdi
0x180037246  mov     r8, rax
0x180037249  mov     edx, 9
0x18003724e  mov     rcx, r15
0x180037251  call    ?addError@OurReader@Json@@AEAA_NW4JsonErrorType@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAVToken@12@PEBG@Z; Json::OurReader::addError(Json::JsonErrorType,std::wstring const &,Json::OurReader::Token &,ushort const *)
0x180037256  mov     bl, al
0x180037258  lea     rcx, [rsp+110h+var_D8]
0x18003725d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180037262  nop
0x180037263  lea     rcx, [rbp+57h+var_B8]
0x180037267  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003726c  nop
0x18003726d  lea     rcx, [rbp+57h+var_90]
0x180037271  jmp     loc_180037178
0x180037276  mov     byte ptr [rbp+57h+var_88], 3
0x18003727a  btr     [rbp+57h+var_88], 8
0x18003727f  xorps   xmm0, xmm0
0x180037282  movdqu  [rbp+57h+var_80], xmm0
0x180037287  mov     [rbp+57h+var_70], rbx
0x18003728b  movsd   [rbp+57h+var_90], xmm6
0x180037290  lea     rdx, [rbp+57h+var_90]
0x180037294  mov     rcx, r14
0x180037297  call    ??4Value@Json@@QEAAAEAV01@V01@@Z; Json::Value::operator=(Json::Value)
0x18003729c  mov     al, 1
0x18003729e  mov     rcx, [rbp+57h+var_40]
0x1800372a2  xor     rcx, rsp; StackCookie
0x1800372a5  call    __security_check_cookie
0x1800372aa  lea     r11, [rsp+110h+var_20]
0x1800372b2  mov     rbx, [r11+48h]
0x1800372b6  movaps  xmm6, xmmword ptr [r11-10h]
0x1800372bb  mov     rsp, r11
0x1800372be  pop     r15
0x1800372c0  pop     r14
0x1800372c2  pop     rdi
0x1800372c3  pop     rsi
0x1800372c4  pop     rbp
0x1800372c5  retn
```
