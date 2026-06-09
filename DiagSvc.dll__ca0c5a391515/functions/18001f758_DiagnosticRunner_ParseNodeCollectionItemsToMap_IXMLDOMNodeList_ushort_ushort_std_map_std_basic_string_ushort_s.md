# DiagnosticRunner::ParseNodeCollectionItemsToMap(IXMLDOMNodeList *,ushort *,ushort *,std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> *)

- ea: `0x18001f758`
- end: `0x18001fa3c`
- name: `?ParseNodeCollectionItemsToMap@DiagnosticRunner@@AEAAJPEAUIXMLDOMNodeList@@PEAG1PEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@Z`
- size: `740`
- prototype: `__int64 __fastcall(int, __int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18001f758`
- `0x18001fa50`

## callees

- `0x180003fc0`
- `0x180004b78`
- `0x18001cd68`
- `0x18001f758`
- `0x180027010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcslwr_s` at `0x18001f946`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr_s` at `0x18001f946`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18001f91c`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18001f91c`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18001f92d`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18001f92d`
- `OLEAUT32!__imp_SysFreeString` at `0x18001f9d8`
- `OLEAUT32!__imp_SysFreeString` at `0x18001f9e3`
- `OLEAUT32!__imp_SysFreeString` at `0x18001f9d8`
- `OLEAUT32!__imp_SysFreeString` at `0x18001f9e3`

## pseudocode

```c
__int64 __fastcall DiagnosticRunner::ParseNodeCollectionItemsToMap(
        int a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  int v7; // ebx
  unsigned int v8; // edi
  BSTR v9; // rbx
  wchar_t *v10; // rax
  BSTR v11; // rcx
  __int64 v13; // [rsp+30h] [rbp-D0h] BYREF
  int v14; // [rsp+38h] [rbp-C8h] BYREF
  __int64 i; // [rsp+40h] [rbp-C0h] BYREF
  BSTR bstrString; // [rsp+48h] [rbp-B8h] BYREF
  BSTR v17; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v18; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v19[2]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v20[16]; // [rsp+70h] [rbp-90h] BYREF
  wchar_t Str[256]; // [rsp+80h] [rbp-80h] BYREF

  v14 = 0;
  if ( a2 )
  {
    v7 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)a2 + 64LL))(a2, &v14);
    if ( v7 >= 0 )
    {
      v8 = 0;
      for ( i = 0; (int)v8 < v14; ++v8 )
      {
        v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)a2 + 56LL))(a2, v8, &i);
        if ( v7 >= 0 && i )
        {
          v13 = 0;
          bstrString = 0;
          v17 = 0;
          if ( (*(int (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)i + 296LL))(i, L"ID", &v13) >= 0 )
          {
            if ( v13 )
            {
              (*(void (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v13 + 208LL))(v13, &bstrString);
              if ( v13 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
                v13 = 0;
              }
            }
          }
          v7 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64 *))(*(_QWORD *)i + 296LL))(
                 i,
                 L"Status",
                 &v13);
          if ( v7 >= 0 )
          {
            if ( !v13 )
              goto LABEL_16;
            v7 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v13 + 208LL))(v13, &v17);
            if ( v13 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
              v13 = 0;
            }
            if ( v7 >= 0 )
            {
LABEL_16:
              v9 = bstrString;
              if ( bstrString )
              {
                memset_0(Str, 0, 0x1FEu);
                _o_wcscpy_s(Str, 255, v9);
                v10 = wcsstr(Str, L"/");
                if ( v10 )
                  *v10 = 0;
                _wcslwr_s(Str, 0xFFu);
                v11 = (BSTR)&qword_18002B598;
                if ( v17 )
                  v11 = v17;
                v19[1] = v11;
                v19[0] = Str;
                std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Emplace<std::pair<unsigned short *,unsigned short *>>(
                  a5,
                  v20,
                  v19);
              }
              v18 = 0;
              v7 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)i + 288LL))(
                     i,
                     L"/Resolutions/Resolution",
                     &v18);
              if ( v7 >= 0 && v18 )
                DiagnosticRunner::ParseNodeCollectionItemsToMap(
                  a1,
                  v18,
                  (unsigned int)L"ID",
                  (unsigned int)L"Status",
                  a5);
            }
          }
          SysFreeString(bstrString);
          SysFreeString(v17);
          if ( i )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)i + 16LL))(i);
            i = 0;
          }
        }
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001f758  mov     [rsp-8+arg_10], rbx
0x18001f75d  push    rbp
0x18001f75e  push    rsi
0x18001f75f  push    rdi
0x18001f760  push    r14
0x18001f762  push    r15
0x18001f764  lea     rbp, [rsp-190h]
0x18001f76c  sub     rsp, 290h
0x18001f773  mov     rax, cs:__security_cookie
0x18001f77a  xor     rax, rsp
0x18001f77d  mov     [rbp+1B0h+var_30], rax
0x18001f784  mov     r14, [rbp+1B0h+arg_20]
0x18001f78b  mov     rsi, rdx
0x18001f78e  mov     [rsp+2B0h+var_278], 0
0x18001f796  mov     r15, rcx
0x18001f799  test    rdx, rdx
0x18001f79c  jnz     short loc_18001F7A8
0x18001f79e  mov     ebx, 80070057h
0x18001f7a3  jmp     loc_18001FA14
0x18001f7a8  mov     rax, [rdx]
0x18001f7ab  mov     rcx, rsi
0x18001f7ae  lea     rdx, [rsp+2B0h+var_278]
0x18001f7b3  mov     rax, [rax+40h]
0x18001f7b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f7bc  mov     ebx, eax
0x18001f7be  test    eax, eax
0x18001f7c0  js      loc_18001FA14
0x18001f7c6  xor     edi, edi
0x18001f7c8  mov     [rsp+2B0h+var_270], 0
0x18001f7d1  cmp     [rsp+2B0h+var_278], edi
0x18001f7d5  jle     loc_18001FA14
0x18001f7db  mov     rax, [rsi]
0x18001f7de  lea     r8, [rsp+2B0h+var_270]
0x18001f7e3  mov     edx, edi
0x18001f7e5  mov     rcx, rsi
0x18001f7e8  mov     rax, [rax+38h]
0x18001f7ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f7f1  mov     ebx, eax
0x18001f7f3  test    eax, eax
0x18001f7f5  js      loc_18001FA08
0x18001f7fb  mov     rcx, [rsp+2B0h+var_270]
0x18001f800  test    rcx, rcx
0x18001f803  jz      loc_18001FA08
0x18001f809  mov     [rsp+2B0h+var_280], 0
0x18001f812  lea     r8, [rsp+2B0h+var_280]
0x18001f817  mov     [rsp+2B0h+bstrString], 0
0x18001f820  lea     rdx, aId; "ID"
0x18001f827  mov     [rsp+2B0h+var_260], 0
0x18001f830  mov     rax, [rcx]
0x18001f833  mov     rax, [rax+128h]
0x18001f83a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f83f  test    eax, eax
0x18001f841  js      short loc_18001F880
0x18001f843  mov     rcx, [rsp+2B0h+var_280]
0x18001f848  test    rcx, rcx
0x18001f84b  jz      short loc_18001F880
0x18001f84d  mov     rax, [rcx]
0x18001f850  lea     rdx, [rsp+2B0h+bstrString]
0x18001f855  mov     rax, [rax+0D0h]
0x18001f85c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f861  mov     rcx, [rsp+2B0h+var_280]
0x18001f866  test    rcx, rcx
0x18001f869  jz      short loc_18001F880
0x18001f86b  mov     rax, [rcx]
0x18001f86e  mov     rax, [rax+10h]
0x18001f872  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f877  mov     [rsp+2B0h+var_280], 0
0x18001f880  mov     rcx, [rsp+2B0h+var_270]
0x18001f885  lea     r8, [rsp+2B0h+var_280]
0x18001f88a  lea     rdx, aStatus; "Status"
0x18001f891  mov     rax, [rcx]
0x18001f894  mov     rax, [rax+128h]
0x18001f89b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f8a0  mov     ebx, eax
0x18001f8a2  test    eax, eax
0x18001f8a4  js      loc_18001F9D3
0x18001f8aa  mov     rcx, [rsp+2B0h+var_280]
0x18001f8af  test    rcx, rcx
0x18001f8b2  jz      short loc_18001F8F1
0x18001f8b4  mov     rax, [rcx]
0x18001f8b7  lea     rdx, [rsp+2B0h+var_260]
0x18001f8bc  mov     rax, [rax+0D0h]
0x18001f8c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f8c8  mov     rcx, [rsp+2B0h+var_280]
0x18001f8cd  mov     ebx, eax
0x18001f8cf  test    rcx, rcx
0x18001f8d2  jz      short loc_18001F8E9
0x18001f8d4  mov     rax, [rcx]
0x18001f8d7  mov     rax, [rax+10h]
0x18001f8db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f8e0  mov     [rsp+2B0h+var_280], 0
0x18001f8e9  test    ebx, ebx
0x18001f8eb  js      loc_18001F9D3
0x18001f8f1  mov     rbx, [rsp+2B0h+bstrString]
0x18001f8f6  test    rbx, rbx
0x18001f8f9  jz      loc_18001F97F
0x18001f8ff  xor     edx, edx; Val
0x18001f901  lea     rcx, [rbp+1B0h+Str]; void *
0x18001f905  mov     r8d, 1FEh; Size
0x18001f90b  call    memset_0
0x18001f910  mov     r8, rbx
0x18001f913  lea     rcx, [rbp+1B0h+Str]
0x18001f917  mov     edx, 0FFh
0x18001f91c  call    cs:__imp__o_wcscpy_s
0x18001f922  lea     rdx, SubStr; "/"
0x18001f929  lea     rcx, [rbp+1B0h+Str]; Str
0x18001f92d  call    cs:__imp_wcsstr
0x18001f933  test    rax, rax
0x18001f936  jz      short loc_18001F93D
0x18001f938  xor     ecx, ecx
0x18001f93a  mov     [rax], cx
0x18001f93d  mov     edx, 0FFh; SizeInWords
0x18001f942  lea     rcx, [rbp+1B0h+Str]; String
0x18001f946  call    cs:__imp__wcslwr_s
0x18001f94c  mov     rax, [rsp+2B0h+var_260]
0x18001f951  lea     rcx, qword_18002B598
0x18001f958  test    rax, rax
0x18001f95b  lea     r8, [rsp+2B0h+var_250]
0x18001f960  lea     rdx, [rsp+2B0h+var_240]
0x18001f965  cmovnz  rcx, rax
0x18001f969  lea     rax, [rbp+1B0h+Str]
0x18001f96d  mov     [rsp+2B0h+var_248], rcx
0x18001f972  mov     rcx, r14
0x18001f975  mov     [rsp+2B0h+var_250], rax
0x18001f97a  call    ??$_Emplace@U?$pair@PEAGPEAG@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@_N@1@$$QEAU?$pair@PEAGPEAG@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Emplace<std::pair<ushort *,ushort *>>(std::pair<ushort *,ushort *> &&)
0x18001f97f  mov     rcx, [rsp+2B0h+var_270]
0x18001f984  lea     r8, [rsp+2B0h+var_258]
0x18001f989  mov     [rsp+2B0h+var_258], 0
0x18001f992  lea     rdx, aResolutionsRes_0; "/Resolutions/Resolution"
0x18001f999  mov     rax, [rcx]
0x18001f99c  mov     rax, [rax+120h]
0x18001f9a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f9a8  mov     ebx, eax
0x18001f9aa  test    eax, eax
0x18001f9ac  js      short loc_18001F9D3
0x18001f9ae  mov     rdx, [rsp+2B0h+var_258]
0x18001f9b3  test    rdx, rdx
0x18001f9b6  jz      short loc_18001F9D3
0x18001f9b8  lea     r9, aStatus; "Status"
0x18001f9bf  mov     [rsp+2B0h+var_290], r14
0x18001f9c4  lea     r8, aId; "ID"
0x18001f9cb  mov     rcx, r15
0x18001f9ce  call    ?ParseNodeCollectionItemsToMap@DiagnosticRunner@@AEAAJPEAUIXMLDOMNodeList@@PEAG1PEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@Z; DiagnosticRunner::ParseNodeCollectionItemsToMap(IXMLDOMNodeList *,ushort *,ushort *,std::map<std::wstring,std::wstring> *)
0x18001f9d3  mov     rcx, [rsp+2B0h+bstrString]; bstrString
0x18001f9d8  call    cs:__imp_SysFreeString
0x18001f9de  mov     rcx, [rsp+2B0h+var_260]; bstrString
0x18001f9e3  call    cs:__imp_SysFreeString
0x18001f9e9  mov     rcx, [rsp+2B0h+var_270]
0x18001f9ee  test    rcx, rcx
0x18001f9f1  jz      short loc_18001FA08
0x18001f9f3  mov     rax, [rcx]
0x18001f9f6  mov     rax, [rax+10h]
0x18001f9fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f9ff  mov     [rsp+2B0h+var_270], 0
0x18001fa08  inc     edi
0x18001fa0a  cmp     edi, [rsp+2B0h+var_278]
0x18001fa0e  jl      loc_18001F7DB
0x18001fa14  mov     eax, ebx
0x18001fa16  mov     rcx, [rbp+1B0h+var_30]
0x18001fa1d  xor     rcx, rsp; StackCookie
0x18001fa20  call    __security_check_cookie
0x18001fa25  mov     rbx, [rsp+2B0h+arg_10]
0x18001fa2d  add     rsp, 290h
0x18001fa34  pop     r15
0x18001fa36  pop     r14
0x18001fa38  pop     rdi
0x18001fa39  pop     rsi
0x18001fa3a  pop     rbp
0x18001fa3b  retn
```
