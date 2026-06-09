# web::json::details::JSON_Parser<char>::_ParseObject(web::json::details::JSON_Parser<char>::Token &)

- ea: `0x180030844`
- end: `0x180030b1b`
- name: `?_ParseObject@?$JSON_Parser@D@details@json@web@@AEAA?AV?$unique_ptr@V_Value@details@json@web@@U?$default_delete@V_Value@details@json@web@@@std@@@std@@AEAUToken@1234@@Z`
- size: `727`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003008c`

## callees

- `0x18001ded4`
- `0x180028514`
- `0x180029644`
- `0x180029a10`
- `0x18002a57c`
- `0x18002e6b0`
- `0x18003008c`
- `0x180030844`
- `0x1800310f4`
- `0x180031c5c`
- `0x180042bfc`
- `0x180047a30`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall web::json::details::JSON_Parser<char>::_ParseObject(__int64 a1, _QWORD *a2, _DWORD *a3)
{
  __int64 v6; // rbx
  _OWORD *v7; // r14
  bool v8; // al
  _DWORD *v9; // rax
  __int64 *v10; // rax
  __int64 v11; // r13
  __int64 v12; // rdx
  web::json::details *v13; // rcx
  const struct web::json::details::json_error_category_impl *v14; // rax
  _QWORD *v15; // rax
  __int64 v17; // [rsp+20h] [rbp-49h] BYREF
  __int128 v18; // [rsp+28h] [rbp-41h] BYREF
  __int64 v19; // [rsp+38h] [rbp-31h]
  __int64 v20; // [rsp+40h] [rbp-29h]
  __int128 v21; // [rsp+48h] [rbp-21h] BYREF
  _OWORD *v22; // [rsp+58h] [rbp-11h]
  __int128 Src; // [rsp+68h] [rbp-1h] BYREF
  __int128 v24; // [rsp+78h] [rbp+Fh]

  v6 = 0;
  v7 = operator new(0x28u);
  *(_QWORD *)&v21 = v7;
  *v7 = 0;
  v7[1] = 0;
  *((_QWORD *)v7 + 4) = 0;
  v8 = web::json::details::g_keep_json_object_unsorted;
  *(_QWORD *)v7 = &web::json::details::_Object::`vftable';
  *((_QWORD *)v7 + 1) = 0;
  *((_QWORD *)v7 + 2) = 0;
  *((_QWORD *)v7 + 3) = 0;
  *((_BYTE *)v7 + 32) = v8;
  v22 = v7;
  web::json::details::JSON_Parser<char>::GetNextToken(a1, a3);
  if ( a3[18] )
    goto LABEL_20;
  if ( *a3 != 2 )
  {
    v18 = 0;
    v19 = 0;
    v20 = 15;
    LOBYTE(v18) = 0;
    if ( *a3 == 7 )
    {
      v9 = a3 + 2;
      while ( 1 )
      {
        std::string::operator=(&v18, v9);
        web::json::details::JSON_Parser<char>::GetNextToken(a1, a3);
        if ( a3[18] )
          break;
        if ( *a3 != 6 )
          goto LABEL_22;
        web::json::details::JSON_Parser<char>::GetNextToken(a1, a3);
        if ( a3[18] )
          break;
        v10 = (__int64 *)web::json::details::JSON_Parser<char>::_ParseValue(a1, &v21, a3);
        v11 = *v10;
        *v10 = 0;
        v17 = v11;
        utility::conversions::utf8_to_utf16(&Src);
        v12 = *((_QWORD *)v7 + 2);
        if ( v12 == *((_QWORD *)v7 + 3) )
        {
          std::vector<std::pair<std::wstring,web::json::value>>::_Emplace_reallocate<std::wstring,web::json::value>(
            (char *)v7 + 8,
            v12,
            &Src,
            &v17);
          v6 = v17;
        }
        else
        {
          *(_OWORD *)v12 = 0;
          *(_QWORD *)(v12 + 16) = 0;
          *(_QWORD *)(v12 + 24) = 0;
          *(_OWORD *)v12 = Src;
          *(_OWORD *)(v12 + 16) = v24;
          *(_QWORD *)&v24 = 0;
          *((_QWORD *)&v24 + 1) = 7;
          LOWORD(Src) = 0;
          *(_QWORD *)(v12 + 32) = v11;
          *((_QWORD *)v7 + 2) += 40LL;
        }
        std::wstring::_Tidy_deallocate(&Src);
        if ( v6 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v6 + 192LL))(v6, 1);
        v6 = 0;
        if ( a3[18] )
          break;
        if ( *a3 == 2 )
        {
LABEL_22:
          std::string::~string(&v18);
          goto LABEL_23;
        }
        if ( *a3 == 5 )
        {
          web::json::details::JSON_Parser<char>::GetNextToken(a1, a3);
          if ( !a3[18] )
          {
            std::string::~string(&v18);
            v18 = 0;
            v19 = 0;
            v20 = 15;
            LOBYTE(v18) = 0;
            v9 = a3 + 2;
            if ( *a3 == 7 )
              continue;
          }
        }
        break;
      }
    }
    std::string::~string(&v18);
    if ( !a3[18] )
    {
      v14 = web::json::details::json_error_category(v13);
      LODWORD(v21) = 5;
      *((_QWORD *)&v21 + 1) = v14;
      *(_OWORD *)(a3 + 18) = v21;
    }
    goto LABEL_20;
  }
LABEL_23:
  web::json::details::JSON_Parser<char>::GetNextToken(a1, a3);
  if ( a3[18] )
  {
LABEL_20:
    v15 = operator new(8u);
    v22 = v15;
    *v15 = &web::json::details::_Null::`vftable';
    *a2 = v15;
    (*(void (__fastcall **)(_OWORD *, __int64))(*(_QWORD *)v7 + 192LL))(v7, 1);
    return a2;
  }
  if ( !web::json::details::g_keep_json_object_unsorted )
    std::_Sort_unchecked<std::pair<std::wstring,web::json::value> *,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &)>(
      *((_QWORD *)v7 + 1),
      *((_QWORD *)v7 + 2),
      0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)v7 + 2) - *((_QWORD *)v7 + 1)) >> 3),
      web::json::object::compare_with_key);
  *a2 = v7;
  return a2;
}

```

## disassembly

```asm
0x180030844  mov     [rsp-8+arg_18], rbx
0x180030849  push    rbp
0x18003084a  push    rsi
0x18003084b  push    rdi
0x18003084c  push    r12
0x18003084e  push    r13
0x180030850  push    r14
0x180030852  push    r15
0x180030854  lea     rbp, [rsp-27h]
0x180030859  sub     rsp, 90h
0x180030860  mov     rdi, r8
0x180030863  mov     rsi, rdx
0x180030866  mov     r12, rcx
0x180030869  mov     qword ptr [rbp+57h+var_78], rdx
0x18003086d  xor     ebx, ebx
0x18003086f  lea     ecx, [rbx+28h]; Size
0x180030872  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180030877  mov     r14, rax
0x18003087a  mov     qword ptr [rbp+57h+var_78], rax
0x18003087e  xorps   xmm0, xmm0
0x180030881  xor     eax, eax
0x180030883  movups  xmmword ptr [r14], xmm0
0x180030887  movups  xmmword ptr [r14+10h], xmm0
0x18003088c  mov     [r14+20h], rax
0x180030890  mov     al, cs:?g_keep_json_object_unsorted@details@json@web@@3_NA; bool web::json::details::g_keep_json_object_unsorted
0x180030896  lea     rcx, ??_7_Object@details@json@web@@6B@; const web::json::details::_Object::`vftable'
0x18003089d  mov     [r14], rcx
0x1800308a0  lea     r15, [r14+8]
0x1800308a4  mov     [r15], rbx
0x1800308a7  mov     [r15+8], rbx
0x1800308ab  mov     [r15+10h], rbx
0x1800308af  mov     [r15+18h], al
0x1800308b3  mov     [rbp+57h+var_68], r14
0x1800308b7  mov     rdx, rdi
0x1800308ba  mov     rcx, r12
0x1800308bd  call    ?GetNextToken@?$JSON_Parser@D@details@json@web@@QEAAXAEAUToken@1234@@Z; web::json::details::JSON_Parser<char>::GetNextToken(web::json::details::JSON_Parser<char>::Token &)
0x1800308c2  cmp     [rdi+48h], ebx
0x1800308c5  jnz     loc_180030A50
0x1800308cb  cmp     dword ptr [rdi], 2
0x1800308ce  jz      loc_180030AA9
0x1800308d4  xorps   xmm0, xmm0
0x1800308d7  movups  [rbp+57h+var_98], xmm0
0x1800308db  mov     [rbp+57h+var_88], rbx
0x1800308df  mov     [rbp+57h+var_80], 0Fh
0x1800308e7  mov     byte ptr [rbp+57h+var_98], bl
0x1800308ea  cmp     dword ptr [rdi], 7
0x1800308ed  jnz     loc_180030A29
0x1800308f3  lea     rax, [rdi+8]
0x1800308f7  mov     rdx, rax
0x1800308fa  lea     rcx, [rbp+57h+var_98]
0x1800308fe  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x180030903  mov     rdx, rdi
0x180030906  mov     rcx, r12
0x180030909  call    ?GetNextToken@?$JSON_Parser@D@details@json@web@@QEAAXAEAUToken@1234@@Z; web::json::details::JSON_Parser<char>::GetNextToken(web::json::details::JSON_Parser<char>::Token &)
0x18003090e  cmp     [rdi+48h], ebx
0x180030911  jnz     loc_180030A29
0x180030917  cmp     dword ptr [rdi], 6
0x18003091a  jnz     loc_180030AA0
0x180030920  mov     rdx, rdi
0x180030923  mov     rcx, r12
0x180030926  call    ?GetNextToken@?$JSON_Parser@D@details@json@web@@QEAAXAEAUToken@1234@@Z; web::json::details::JSON_Parser<char>::GetNextToken(web::json::details::JSON_Parser<char>::Token &)
0x18003092b  cmp     [rdi+48h], ebx
0x18003092e  jnz     loc_180030A29
0x180030934  mov     r8, rdi
0x180030937  lea     rdx, [rbp+57h+var_78]
0x18003093b  mov     rcx, r12
0x18003093e  call    ?_ParseValue@?$JSON_Parser@D@details@json@web@@AEAA?AV?$unique_ptr@V_Value@details@json@web@@U?$default_delete@V_Value@details@json@web@@@std@@@std@@AEAUToken@1234@@Z; web::json::details::JSON_Parser<char>::_ParseValue(web::json::details::JSON_Parser<char>::Token &)
0x180030943  mov     r13, [rax]
0x180030946  mov     [rax], rbx
0x180030949  mov     [rbp+57h+var_A0], r13
0x18003094d  lea     rdx, [rbp+57h+var_98]
0x180030951  lea     rcx, [rbp+57h+Src]; Src
0x180030955  call    ?utf8_to_utf16@conversions@utility@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; utility::conversions::utf8_to_utf16(std::string const &)
0x18003095a  nop
0x18003095b  mov     rdx, [r15+8]
0x18003095f  cmp     rdx, [r15+10h]
0x180030963  jz      short loc_18003099D
0x180030965  xorps   xmm0, xmm0
0x180030968  movups  xmmword ptr [rdx], xmm0
0x18003096b  mov     [rdx+10h], rbx
0x18003096f  mov     [rdx+18h], rbx
0x180030973  movups  xmm0, [rbp+57h+Src]
0x180030977  movups  xmmword ptr [rdx], xmm0
0x18003097a  movups  xmm1, [rbp+57h+var_48]
0x18003097e  movups  xmmword ptr [rdx+10h], xmm1
0x180030982  mov     qword ptr [rbp+57h+var_48], rbx
0x180030986  mov     qword ptr [rbp+57h+var_48+8], 7
0x18003098e  mov     word ptr [rbp+57h+Src], bx
0x180030992  mov     [rdx+20h], r13
0x180030996  add     qword ptr [r15+8], 28h ; '('
0x18003099b  jmp     short loc_1800309B1
0x18003099d  lea     r9, [rbp+57h+var_A0]
0x1800309a1  lea     r8, [rbp+57h+Src]
0x1800309a5  mov     rcx, r15
0x1800309a8  call    ??$_Emplace_reallocate@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@Vvalue@json@web@@@?$vector@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@Vvalue@json@web@@@std@@V?$allocator@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@Vvalue@json@web@@@std@@@2@@std@@AEAAPEAU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@Vvalue@json@web@@@1@QEAU21@$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@$$QEAVvalue@json@web@@@Z; std::vector<std::pair<std::wstring,web::json::value>>::_Emplace_reallocate<std::wstring,web::json::value>(std::pair<std::wstring,web::json::value> * const,std::wstring &&,web::json::value &&)
0x1800309ad  mov     rbx, [rbp+57h+var_A0]
0x1800309b1  lea     rcx, [rbp+57h+Src]
0x1800309b5  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800309ba  nop
0x1800309bb  test    rbx, rbx
0x1800309be  jz      short loc_1800309D7
0x1800309c0  mov     rax, [rbx]
0x1800309c3  mov     edx, 1
0x1800309c8  mov     rcx, rbx
0x1800309cb  mov     rax, [rax+0C0h]
0x1800309d2  call    _guard_dispatch_icall
0x1800309d7  xor     ebx, ebx
0x1800309d9  cmp     [rdi+48h], ebx
0x1800309dc  jnz     short loc_180030A29
0x1800309de  cmp     dword ptr [rdi], 2
0x1800309e1  jz      loc_180030AA0
0x1800309e7  cmp     dword ptr [rdi], 5
0x1800309ea  jnz     short loc_180030A29
0x1800309ec  mov     rdx, rdi
0x1800309ef  mov     rcx, r12
0x1800309f2  call    ?GetNextToken@?$JSON_Parser@D@details@json@web@@QEAAXAEAUToken@1234@@Z; web::json::details::JSON_Parser<char>::GetNextToken(web::json::details::JSON_Parser<char>::Token &)
0x1800309f7  nop
0x1800309f8  lea     rcx, [rbp+57h+var_98]
0x1800309fc  cmp     [rdi+48h], ebx
0x1800309ff  jnz     short loc_180030A2D
0x180030a01  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180030a06  xorps   xmm0, xmm0
0x180030a09  movups  [rbp+57h+var_98], xmm0
0x180030a0d  mov     [rbp+57h+var_88], rbx
0x180030a11  mov     [rbp+57h+var_80], 0Fh
0x180030a19  mov     byte ptr [rbp+57h+var_98], bl
0x180030a1c  cmp     dword ptr [rdi], 7
0x180030a1f  lea     rax, [rdi+8]
0x180030a23  jz      loc_1800308F7
0x180030a29  lea     rcx, [rbp+57h+var_98]
0x180030a2d  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180030a32  cmp     [rdi+48h], ebx
0x180030a35  jnz     short loc_180030A50
0x180030a37  call    ?json_error_category@details@json@web@@YAAEBVjson_error_category_impl@123@XZ; web::json::details::json_error_category(void)
0x180030a3c  mov     dword ptr [rbp+57h+var_78], 5
0x180030a43  mov     qword ptr [rbp+57h+var_78+8], rax
0x180030a47  movups  xmm0, [rbp+57h+var_78]
0x180030a4b  movdqu  xmmword ptr [rdi+48h], xmm0
0x180030a50  mov     ecx, 8; Size
0x180030a55  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180030a5a  mov     [rbp+57h+var_68], rax
0x180030a5e  lea     rcx, ??_7_Null@details@json@web@@6B@; const web::json::details::_Null::`vftable'
0x180030a65  mov     [rax], rcx
0x180030a68  mov     [rsi], rax
0x180030a6b  mov     rax, [r14]
0x180030a6e  mov     rax, [rax+0C0h]
0x180030a75  mov     edx, 1
0x180030a7a  mov     rcx, r14
0x180030a7d  call    _guard_dispatch_icall
0x180030a82  mov     rax, rsi
0x180030a85  mov     rbx, [rsp+0C0h+arg_18]
0x180030a8d  add     rsp, 90h
0x180030a94  pop     r15
0x180030a96  pop     r14
0x180030a98  pop     r13
0x180030a9a  pop     r12
0x180030a9c  pop     rdi
0x180030a9d  pop     rsi
0x180030a9e  pop     rbp
0x180030a9f  retn
0x180030aa0  lea     rcx, [rbp+57h+var_98]
0x180030aa4  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180030aa9  mov     rdx, rdi
0x180030aac  mov     rcx, r12
0x180030aaf  call    ?GetNextToken@?$JSON_Parser@D@details@json@web@@QEAAXAEAUToken@1234@@Z; web::json::details::JSON_Parser<char>::GetNextToken(web::json::details::JSON_Parser<char>::Token &)
0x180030ab4  cmp     [rdi+48h], ebx
0x180030ab7  jz      short loc_180030AE0
0x180030ab9  mov     ecx, 8; Size
0x180030abe  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180030ac3  mov     [rbp+57h+var_68], rax
0x180030ac7  lea     rcx, ??_7_Null@details@json@web@@6B@; const web::json::details::_Null::`vftable'
0x180030ace  mov     [rax], rcx
0x180030ad1  mov     [rsi], rax
0x180030ad4  mov     rcx, [r14]
0x180030ad7  mov     rax, [rcx+0C0h]
0x180030ade  jmp     short loc_180030A75
0x180030ae0  cmp     cs:?g_keep_json_object_unsorted@details@json@web@@3_NA, bl; bool web::json::details::g_keep_json_object_unsorted
0x180030ae6  jnz     short loc_180030B13
0x180030ae8  mov     rdx, [r15+8]
0x180030aec  mov     r8, rdx
0x180030aef  sub     r8, [r15]
0x180030af2  sar     r8, 3
0x180030af6  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180030b00  imul    r8, rax
0x180030b04  lea     r9, ?compare_with_key@object@json@web@@CA_NAEBU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@Vvalue@json@web@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; web::json::object::compare_with_key(std::pair<std::wstring,web::json::value> const &,std::wstring const &)
0x180030b0b  mov     rcx, [r15]
0x180030b0e  call    ??$_Sort_unchecked@PEAU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@Vvalue@json@web@@@std@@P6A_NAEBU12@0@Z@std@@YAXPEAU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@Vvalue@json@web@@@0@0_JP6A_NAEBU10@2@Z@Z; std::_Sort_unchecked<std::pair<std::wstring,web::json::value> *,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &)>(std::pair<std::wstring,web::json::value> *,std::pair<std::wstring,web::json::value> *,__int64,bool (*)(std::pair<std::wstring,web::json::value> const &,std::pair<std::wstring,web::json::value> const &))
0x180030b13  mov     [rsi], r14
0x180030b16  jmp     loc_180030A82
```
