# web::json::details::JSON_Parser<wchar_t>::_ParseValue(web::json::details::JSON_Parser<wchar_t>::Token &)

- ea: `0x18002f6a4`
- end: `0x18002f954`
- name: `?_ParseValue@?$JSON_Parser@_W@details@json@web@@AEAA?AV?$unique_ptr@V_Value@details@json@web@@U?$default_delete@V_Value@details@json@web@@@std@@@std@@AEAUToken@1234@@Z`
- size: `688`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18002dbdc`
- `0x18002dd88`
- `0x180030358`
- `0x180030674`

## callees

- `0x180029a10`
- `0x180029a78`
- `0x18002e198`
- `0x18002f6a4`
- `0x180030358`
- `0x180030674`
- `0x180042bfc`
- `0x180047a30`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall web::json::details::JSON_Parser<wchar_t>::_ParseValue(__int64 a1, _QWORD *a2, __int64 a3)
{
  web::json::details *v6; // rcx
  _QWORD *v7; // rax
  _QWORD *v8; // rbx
  char v9; // cl
  _QWORD *v10; // rax
  _QWORD *v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  _QWORD *v15; // rax
  __int64 v16; // xmm0_8
  _QWORD *v17; // rax
  _QWORD *v19; // [rsp+20h] [rbp-20h] BYREF
  __int128 v20; // [rsp+30h] [rbp-10h]

  v19 = a2;
  switch ( *(_DWORD *)a3 )
  {
    case 1:
      web::json::details::JSON_Parser<wchar_t>::_ParseObject(a1);
      return a2;
    case 3:
      web::json::details::JSON_Parser<wchar_t>::_ParseArray(a1);
      return a2;
    case 7:
      v19 = 0;
      std::make_unique<web::json::details::_String,std::wstring,bool &,0>(&v19, a3 + 8, a3 + 56);
      web::json::details::JSON_Parser<wchar_t>::GetNextToken(a1, a3);
      if ( !*(_DWORD *)(a3 + 72) )
      {
        *a2 = v19;
        return a2;
      }
      v17 = operator new(8u);
      *(_QWORD *)&v20 = v17;
      *v17 = &web::json::details::_Null::`vftable';
      *a2 = v17;
      v11 = v19;
      if ( v19 )
      {
        v12 = *v19;
        goto LABEL_14;
      }
      break;
    case 8:
      v8 = operator new(0x18u);
      v19 = v8;
      v16 = *(_QWORD *)(a3 + 56);
      *v8 = &web::json::details::_Number::`vftable';
      v8[1] = v16;
      *((_DWORD *)v8 + 4) = 2;
      v19 = v8;
      web::json::details::JSON_Parser<wchar_t>::GetNextToken(a1, a3);
      if ( !*(_DWORD *)(a3 + 72) )
      {
        *a2 = v8;
        return a2;
      }
LABEL_12:
      v10 = operator new(8u);
      v19 = v10;
      *v10 = &web::json::details::_Null::`vftable';
      *a2 = v10;
LABEL_13:
      v11 = v8;
      v12 = *v8;
LABEL_14:
      (*(void (__fastcall **)(_QWORD *, __int64))(v12 + 192))(v11, 1);
      return a2;
    case 9:
      v19 = 0;
      if ( *(_BYTE *)(a3 + 64) )
      {
        v8 = operator new(0x18u);
        v19 = v8;
        v13 = *(_QWORD *)(a3 + 56);
        *v8 = &web::json::details::_Number::`vftable';
        v8[1] = v13;
        *((_DWORD *)v8 + 4) = v13 >= 0;
      }
      else
      {
        v8 = operator new(0x18u);
        v19 = v8;
        v14 = *(_QWORD *)(a3 + 56);
        *v8 = &web::json::details::_Number::`vftable';
        v8[1] = v14;
        *((_DWORD *)v8 + 4) = 1;
      }
      v19 = v8;
      web::json::details::JSON_Parser<wchar_t>::GetNextToken(a1, a3);
      if ( !*(_DWORD *)(a3 + 72) )
      {
        *a2 = v8;
        return a2;
      }
      v15 = operator new(8u);
      v19 = v15;
      *v15 = &web::json::details::_Null::`vftable';
      *a2 = v15;
      if ( v8 )
        goto LABEL_13;
      break;
    default:
      v6 = (web::json::details *)(unsigned int)(*(_DWORD *)a3 - 10);
      if ( *(_DWORD *)a3 != 10 )
      {
        if ( *(_DWORD *)a3 == 11 )
        {
          web::json::details::JSON_Parser<wchar_t>::GetNextToken(a1, a3);
        }
        else
        {
          LODWORD(v20) = 8;
          *((_QWORD *)&v20 + 1) = web::json::details::json_error_category(v6);
          *(_OWORD *)(a3 + 72) = v20;
        }
        v7 = operator new(8u);
        v19 = v7;
        *v7 = &web::json::details::_Null::`vftable';
        *a2 = v7;
        return a2;
      }
      v8 = operator new(0x10u);
      v19 = v8;
      v9 = *(_BYTE *)(a3 + 56);
      *v8 = &web::json::details::_Boolean::`vftable';
      *((_BYTE *)v8 + 8) = v9;
      v19 = v8;
      web::json::details::JSON_Parser<wchar_t>::GetNextToken(a1, a3);
      if ( !*(_DWORD *)(a3 + 72) )
      {
        *a2 = v8;
        return a2;
      }
      goto LABEL_12;
  }
  return a2;
}

```

## disassembly

```asm
0x18002f6a4  mov     [rsp-28h+arg_18], rbx
0x18002f6a9  push    rbp
0x18002f6aa  push    rsi
0x18002f6ab  push    rdi
0x18002f6ac  push    r14
0x18002f6ae  push    r15
0x18002f6b0  mov     rbp, rsp
0x18002f6b3  sub     rsp, 40h
0x18002f6b7  mov     rsi, r8
0x18002f6ba  mov     rdi, rdx
0x18002f6bd  mov     r14, rcx
0x18002f6c0  mov     [rbp+var_20], rdx
0x18002f6c4  mov     ecx, [r8]
0x18002f6c7  sub     ecx, 1
0x18002f6ca  jz      loc_18002F935
0x18002f6d0  sub     ecx, 2
0x18002f6d3  jz      loc_18002F92B
0x18002f6d9  sub     ecx, 4
0x18002f6dc  jz      loc_18002F8CB
0x18002f6e2  sub     ecx, 1
0x18002f6e5  jz      loc_18002F865
0x18002f6eb  sub     ecx, 1
0x18002f6ee  jz      loc_18002F7B9
0x18002f6f4  sub     ecx, 1; this
0x18002f6f7  jz      short loc_18002F744
0x18002f6f9  cmp     ecx, 1
0x18002f6fc  jz      short loc_18002F737
0x18002f6fe  call    ?json_error_category@details@json@web@@YAAEBVjson_error_category_impl@123@XZ; web::json::details::json_error_category(void)
0x18002f703  mov     dword ptr [rbp+var_10], 8
0x18002f70a  mov     qword ptr [rbp+var_10+8], rax
0x18002f70e  movups  xmm0, [rbp+var_10]
0x18002f712  movdqu  xmmword ptr [rsi+48h], xmm0
0x18002f717  mov     ecx, 8; Size
0x18002f71c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002f721  mov     [rbp+var_20], rax
0x18002f725  lea     rcx, ??_7_Null@details@json@web@@6B@; const web::json::details::_Null::`vftable'
0x18002f72c  mov     [rax], rcx
0x18002f72f  mov     [rdi], rax
0x18002f732  jmp     loc_18002F93D
0x18002f737  mov     rdx, rsi
0x18002f73a  mov     rcx, r14
0x18002f73d  call    ?GetNextToken@?$JSON_Parser@_W@details@json@web@@QEAAXAEAUToken@1234@@Z; web::json::details::JSON_Parser<wchar_t>::GetNextToken(web::json::details::JSON_Parser<wchar_t>::Token &)
0x18002f742  jmp     short loc_18002F717
0x18002f744  mov     ecx, 10h; Size
0x18002f749  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002f74e  mov     rbx, rax
0x18002f751  mov     [rbp+var_20], rax
0x18002f755  mov     cl, [rsi+38h]
0x18002f758  lea     rax, ??_7_Boolean@details@json@web@@6B@; const web::json::details::_Boolean::`vftable'
0x18002f75f  mov     [rbx], rax
0x18002f762  mov     [rbx+8], cl
0x18002f765  mov     [rbp+var_20], rbx
0x18002f769  mov     rdx, rsi
0x18002f76c  mov     rcx, r14
0x18002f76f  call    ?GetNextToken@?$JSON_Parser@_W@details@json@web@@QEAAXAEAUToken@1234@@Z; web::json::details::JSON_Parser<wchar_t>::GetNextToken(web::json::details::JSON_Parser<wchar_t>::Token &)
0x18002f774  cmp     dword ptr [rsi+48h], 0
0x18002f778  jz      short loc_18002F7B1
0x18002f77a  mov     ecx, 8; Size
0x18002f77f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002f784  mov     [rbp+var_20], rax
0x18002f788  lea     rcx, ??_7_Null@details@json@web@@6B@; const web::json::details::_Null::`vftable'
0x18002f78f  mov     [rax], rcx
0x18002f792  mov     [rdi], rax
0x18002f795  mov     rcx, rbx
0x18002f798  mov     rax, [rbx]
0x18002f79b  mov     edx, 1
0x18002f7a0  mov     rax, [rax+0C0h]
0x18002f7a7  call    _guard_dispatch_icall
0x18002f7ac  jmp     loc_18002F93D
0x18002f7b1  mov     [rdi], rbx
0x18002f7b4  jmp     loc_18002F93D
0x18002f7b9  mov     [rbp+var_20], 0
0x18002f7c1  mov     ecx, 18h; Size
0x18002f7c6  cmp     byte ptr [r8+40h], 0
0x18002f7cb  jz      short loc_18002F7F7
0x18002f7cd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002f7d2  mov     rbx, rax
0x18002f7d5  mov     [rbp+var_20], rax
0x18002f7d9  mov     rax, [rsi+38h]
0x18002f7dd  lea     rcx, ??_7_Number@details@json@web@@6B@; const web::json::details::_Number::`vftable'
0x18002f7e4  mov     [rbx], rcx
0x18002f7e7  mov     [rbx+8], rax
0x18002f7eb  shr     rax, 3Fh
0x18002f7ef  xor     eax, 1
0x18002f7f2  mov     [rbx+10h], eax
0x18002f7f5  jmp     short loc_18002F81C
0x18002f7f7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002f7fc  mov     rbx, rax
0x18002f7ff  mov     [rbp+var_20], rax
0x18002f803  mov     rax, [rsi+38h]
0x18002f807  lea     rcx, ??_7_Number@details@json@web@@6B@; const web::json::details::_Number::`vftable'
0x18002f80e  mov     [rbx], rcx
0x18002f811  mov     [rbx+8], rax
0x18002f815  mov     dword ptr [rbx+10h], 1
0x18002f81c  mov     r15, rbx
0x18002f81f  mov     [rbp+var_20], rbx
0x18002f823  mov     rdx, rsi
0x18002f826  mov     rcx, r14
0x18002f829  call    ?GetNextToken@?$JSON_Parser@_W@details@json@web@@QEAAXAEAUToken@1234@@Z; web::json::details::JSON_Parser<wchar_t>::GetNextToken(web::json::details::JSON_Parser<wchar_t>::Token &)
0x18002f82e  cmp     dword ptr [rsi+48h], 0
0x18002f832  jz      short loc_18002F85D
0x18002f834  mov     ecx, 8; Size
0x18002f839  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002f83e  mov     [rbp+var_20], rax
0x18002f842  lea     rcx, ??_7_Null@details@json@web@@6B@; const web::json::details::_Null::`vftable'
0x18002f849  mov     [rax], rcx
0x18002f84c  mov     [rdi], rax
0x18002f84f  test    rbx, rbx
0x18002f852  jz      loc_18002F93D
0x18002f858  jmp     loc_18002F795
0x18002f85d  mov     [rdi], rbx
0x18002f860  jmp     loc_18002F93D
0x18002f865  mov     ecx, 18h; Size
0x18002f86a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002f86f  mov     rbx, rax
0x18002f872  mov     [rbp+var_20], rax
0x18002f876  movsd   xmm0, qword ptr [rsi+38h]
0x18002f87b  lea     rcx, ??_7_Number@details@json@web@@6B@; const web::json::details::_Number::`vftable'
0x18002f882  mov     [rax], rcx
0x18002f885  movsd   qword ptr [rax+8], xmm0
0x18002f88a  mov     dword ptr [rax+10h], 2
0x18002f891  mov     [rbp+var_20], rax
0x18002f895  mov     rdx, rsi
0x18002f898  mov     rcx, r14
0x18002f89b  call    ?GetNextToken@?$JSON_Parser@_W@details@json@web@@QEAAXAEAUToken@1234@@Z; web::json::details::JSON_Parser<wchar_t>::GetNextToken(web::json::details::JSON_Parser<wchar_t>::Token &)
0x18002f8a0  cmp     dword ptr [rsi+48h], 0
0x18002f8a4  jz      short loc_18002F8C6
0x18002f8a6  mov     ecx, 8; Size
0x18002f8ab  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002f8b0  mov     [rbp+var_20], rax
0x18002f8b4  lea     rcx, ??_7_Null@details@json@web@@6B@; const web::json::details::_Null::`vftable'
0x18002f8bb  mov     [rax], rcx
0x18002f8be  mov     [rdi], rax
0x18002f8c1  jmp     loc_18002F795
0x18002f8c6  mov     [rdi], rbx
0x18002f8c9  jmp     short loc_18002F93D
0x18002f8cb  mov     [rbp+var_20], 0
0x18002f8d3  add     r8, 38h ; '8'
0x18002f8d7  lea     rdx, [rsi+8]
0x18002f8db  lea     rcx, [rbp+var_20]
0x18002f8df  call    ??$make_unique@V_String@details@json@web@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEA_N$0A@@std@@YA?AV?$unique_ptr@V_String@details@json@web@@U?$default_delete@V_String@details@json@web@@@std@@@0@$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@AEA_N@Z; std::make_unique<web::json::details::_String,std::wstring,bool &,0>(std::wstring &&,bool &)
0x18002f8e4  nop
0x18002f8e5  mov     rdx, rsi
0x18002f8e8  mov     rcx, r14
0x18002f8eb  call    ?GetNextToken@?$JSON_Parser@_W@details@json@web@@QEAAXAEAUToken@1234@@Z; web::json::details::JSON_Parser<wchar_t>::GetNextToken(web::json::details::JSON_Parser<wchar_t>::Token &)
0x18002f8f0  cmp     dword ptr [rsi+48h], 0
0x18002f8f4  jz      short loc_18002F922
0x18002f8f6  mov     ecx, 8; Size
0x18002f8fb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002f900  mov     qword ptr [rbp+var_10], rax
0x18002f904  lea     rcx, ??_7_Null@details@json@web@@6B@; const web::json::details::_Null::`vftable'
0x18002f90b  mov     [rax], rcx
0x18002f90e  mov     [rdi], rax
0x18002f911  mov     rcx, [rbp+var_20]
0x18002f915  test    rcx, rcx
0x18002f918  jz      short loc_18002F93D
0x18002f91a  mov     rax, [rcx]
0x18002f91d  jmp     loc_18002F79B
0x18002f922  mov     rax, [rbp+var_20]
0x18002f926  mov     [rdi], rax
0x18002f929  jmp     short loc_18002F93D
0x18002f92b  mov     rcx, r14
0x18002f92e  call    ?_ParseArray@?$JSON_Parser@_W@details@json@web@@AEAA?AV?$unique_ptr@V_Value@details@json@web@@U?$default_delete@V_Value@details@json@web@@@std@@@std@@AEAUToken@1234@@Z; web::json::details::JSON_Parser<wchar_t>::_ParseArray(web::json::details::JSON_Parser<wchar_t>::Token &)
0x18002f933  jmp     short loc_18002F93D
0x18002f935  mov     rcx, r14
0x18002f938  call    ?_ParseObject@?$JSON_Parser@_W@details@json@web@@AEAA?AV?$unique_ptr@V_Value@details@json@web@@U?$default_delete@V_Value@details@json@web@@@std@@@std@@AEAUToken@1234@@Z; web::json::details::JSON_Parser<wchar_t>::_ParseObject(web::json::details::JSON_Parser<wchar_t>::Token &)
0x18002f93d  mov     rax, rdi
0x18002f940  mov     rbx, [rsp+40h+arg_18]
0x18002f948  add     rsp, 40h
0x18002f94c  pop     r15
0x18002f94e  pop     r14
0x18002f950  pop     rdi
0x18002f951  pop     rsi
0x18002f952  pop     rbp
0x18002f953  retn
```
