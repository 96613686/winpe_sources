# Uev::TemplatePath::Parse(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>)

- ea: `0x1400655ac`
- end: `0x140065a7f`
- name: `?Parse@TemplatePath@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z`
- size: `1235`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `12`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14004830c`
- `0x140048718`
- `0x140048b24`
- `0x140049398`
- `0x140049b30`
- `0x14004ba24`
- `0x14004c1bc`
- `0x14004dc48`
- `0x14004e054`
- `0x14004e460`
- `0x14004ecd4`
- `0x14004f46c`

## callees

- `0x140003e50`
- `0x140003e74`
- `0x14000423c`
- `0x140004a6c`
- `0x14000aa1c`
- `0x14000aa84`
- `0x14000ba60`
- `0x14000c2b8`
- `0x14000c3a4`
- `0x14000e30c`
- `0x1400655ac`
- `0x140087a7c`
- `0x14009b010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1400659b0`
- `OLEAUT32!__imp_SysAllocString` at `0x140065a2b`
- `OLEAUT32!__imp_SysAllocString` at `0x1400659b0`
- `OLEAUT32!__imp_SysAllocString` at `0x140065a2b`
- `OLEAUT32!__imp_SysFreeString` at `0x1400657cd`
- `OLEAUT32!__imp_SysFreeString` at `0x1400658df`
- `OLEAUT32!__imp_SysFreeString` at `0x1400658f2`
- `OLEAUT32!__imp_SysFreeString` at `0x1400657cd`
- `OLEAUT32!__imp_SysFreeString` at `0x1400658df`
- `OLEAUT32!__imp_SysFreeString` at `0x1400658f2`

## string_xrefs

- `0x140065a24`: `DeleteIfNotFound`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall Uev::TemplatePath::Parse(__int64 a1, __int64 **a2)
{
  __int64 *ThreadLocalStoragePointer; // rax
  __int64 v5; // r14
  unsigned __int64 v6; // rdi
  char v7; // r15
  __int64 v8; // r8
  void *v9; // r9
  unsigned __int64 v10; // rdx
  char *v11; // r14
  __int64 v12; // rbx
  __int64 *v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rbx
  unsigned int (__fastcall *v16)(__int64, __int64, __int64 *); // r14
  __int64 v17; // rdx
  unsigned __int64 v18; // r8
  unsigned __int64 v19; // rbx
  const wchar_t *v20; // rcx
  size_t v21; // r8
  wchar_t **v22; // rax
  bool v23; // zf
  char v24; // al
  __int64 v25; // rbx
  unsigned int (__fastcall *v26)(__int64, __int64, __int64 *); // r14
  __int64 v27; // rdx
  unsigned __int64 v28; // rbx
  const wchar_t *v29; // rcx
  size_t v30; // r8
  wchar_t **v31; // rax
  OLECHAR *v32; // rbx
  BSTR v33; // rax
  OLECHAR *v34; // rbx
  BSTR v35; // rax
  BSTR bstrString; // [rsp+28h] [rbp-41h] BYREF
  void *Src; // [rsp+30h] [rbp-39h] BYREF
  __int64 v38; // [rsp+38h] [rbp-31h] BYREF
  __int64 v39; // [rsp+40h] [rbp-29h] BYREF
  wchar_t *S1[2]; // [rsp+48h] [rbp-21h] BYREF
  unsigned __int64 v41; // [rsp+58h] [rbp-11h]
  unsigned __int64 v42; // [rsp+60h] [rbp-9h]
  wchar_t *v43[2]; // [rsp+68h] [rbp-1h] BYREF
  unsigned __int64 v44; // [rsp+78h] [rbp+Fh]
  unsigned __int64 v45; // [rsp+80h] [rbp+17h]

  ThreadLocalStoragePointer = (__int64 *)NtCurrentTeb()->ThreadLocalStoragePointer;
  v5 = *ThreadLocalStoragePointer;
  v6 = -1;
  v7 = 1;
  if ( __TSS0__1__Parse_TemplatePath_Uev__QEAAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B_____Z_4HA > *(_DWORD *)(*ThreadLocalStoragePointer + 4) )
  {
    Init_thread_header(&__TSS0__1__Parse_TemplatePath_Uev__QEAAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B_____Z_4HA);
    if ( __TSS0__1__Parse_TemplatePath_Uev__QEAAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B_____Z_4HA == -1 )
    {
      v32 = (OLECHAR *)operator new(0x18u);
      bstrString = v32;
      *((_QWORD *)v32 + 1) = 0;
      *((_DWORD *)v32 + 4) = 1;
      v33 = SysAllocString(L"Recursive");
      *(_QWORD *)v32 = v33;
      if ( !v33 )
        _com_issue_error(-2147024882);
      `Uev::TemplatePath::Parse'::`2'::recursiveString = v32;
      atexit(`Uev::TemplatePath::Parse'::`2'::`dynamic atexit destructor for 'recursiveString'');
      Init_thread_footer(&__TSS0__1__Parse_TemplatePath_Uev__QEAAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B_____Z_4HA);
    }
  }
  if ( __TSS1__1__Parse_TemplatePath_Uev__QEAAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B_____Z_4HA > *(_DWORD *)(v5 + 4) )
  {
    Init_thread_header(&__TSS1__1__Parse_TemplatePath_Uev__QEAAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B_____Z_4HA);
    if ( __TSS1__1__Parse_TemplatePath_Uev__QEAAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B_____Z_4HA == -1 )
    {
      v34 = (OLECHAR *)operator new(0x18u);
      bstrString = v34;
      *((_QWORD *)v34 + 1) = 0;
      *((_DWORD *)v34 + 4) = 1;
      v35 = SysAllocString(L"DeleteIfNotFound");
      *(_QWORD *)v34 = v35;
      if ( !v35 )
        _com_issue_error(-2147024882);
      `Uev::TemplatePath::Parse'::`2'::deleteIfNotFoundString = v34;
      atexit(`Uev::TemplatePath::Parse'::`2'::`dynamic atexit destructor for 'deleteIfNotFoundString'');
      Init_thread_footer(&__TSS1__1__Parse_TemplatePath_Uev__QEAAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B_____Z_4HA);
    }
  }
  v38 = 0;
  Src = 0;
  if ( !*a2 )
    _com_issue_error(-2147467261);
  if ( !(*(unsigned int (__fastcall **)(__int64 *, void **))(**a2 + 208))(*a2, &Src) )
  {
    v9 = Src;
    v10 = -1;
    do
      ++v10;
    while ( *((_WORD *)Src + v10) );
    if ( v10 > *(_QWORD *)(a1 + 24) )
    {
      std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(
        (char **)a1,
        v10,
        v8,
        Src);
    }
    else
    {
      if ( *(_QWORD *)(a1 + 24) <= 7u )
        v11 = (char *)a1;
      else
        v11 = *(char **)a1;
      *(_QWORD *)(a1 + 16) = v10;
      v12 = 2 * v10;
      memmove_0(v11, v9, 2 * v10);
      *(_WORD *)&v11[v12] = 0;
    }
    v39 = 0;
    v13 = *a2;
    if ( *a2 )
    {
      v14 = *v13;
      v39 = 0;
      if ( (*(unsigned int (__fastcall **)(__int64 *, __int64 *))(v14 + 136))(v13, &v39) )
      {
LABEL_59:
        SysFreeString((BSTR)Src);
        if ( v39 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
        goto LABEL_61;
      }
      v15 = v39;
      if ( v39 )
      {
        v16 = *(unsigned int (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v39 + 56LL);
        if ( v38 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
        v38 = 0;
        if ( `Uev::TemplatePath::Parse'::`2'::recursiveString )
          v17 = *`Uev::TemplatePath::Parse'::`2'::recursiveString;
        else
          v17 = 0;
        if ( !v16(v15, v17, &v38) )
        {
          bstrString = 0;
          if ( !v38 )
            _com_issue_error(-2147467261);
          if ( !(*(unsigned int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v38 + 208LL))(v38, &bstrString) )
          {
            *(_OWORD *)S1 = 0;
            v41 = 0;
            v42 = 0;
            v18 = -1;
            do
              ++v18;
            while ( bstrString[v18] );
            std::wstring::_Construct<1,wchar_t *>(S1, bstrString, v18);
            v19 = v41;
            v20 = (const wchar_t *)S1;
            if ( v42 > 7 )
              v20 = S1[0];
            v21 = v41;
            if ( v41 > 4 )
              v21 = 4;
            if ( !wmemcmp(v20, L"true", v21) && v19 == 4 )
              goto LABEL_35;
            v22 = S1;
            if ( v42 > 7 )
              v22 = (wchar_t **)S1[0];
            v23 = *(_WORD *)v22 == 49;
            v24 = 0;
            if ( v23 )
LABEL_35:
              v24 = 1;
            *(_BYTE *)(a1 + 32) = v24;
            SysFreeString(bstrString);
            std::wstring::_Tidy_deallocate(S1);
          }
        }
        v25 = v39;
        if ( v39 )
        {
          v26 = *(unsigned int (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v39 + 56LL);
          if ( v38 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
          v38 = 0;
          if ( `Uev::TemplatePath::Parse'::`2'::deleteIfNotFoundString )
            v27 = *`Uev::TemplatePath::Parse'::`2'::deleteIfNotFoundString;
          else
            v27 = 0;
          if ( !v26(v25, v27, &v38) )
          {
            bstrString = 0;
            if ( !v38 )
              _com_issue_error(-2147467261);
            if ( !(*(unsigned int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v38 + 208LL))(v38, &bstrString) )
            {
              *(_OWORD *)v43 = 0;
              v44 = 0;
              v45 = 0;
              do
                ++v6;
              while ( bstrString[v6] );
              std::wstring::_Construct<1,wchar_t *>(v43, bstrString, v6);
              v28 = v44;
              v29 = (const wchar_t *)v43;
              if ( v45 > 7 )
                v29 = v43[0];
              v30 = v44;
              if ( v44 > 4 )
                v30 = 4;
              if ( wmemcmp(v29, L"true", v30) || v28 != 4 )
              {
                v31 = v43;
                if ( v45 > 7 )
                  v31 = (wchar_t **)v43[0];
                if ( *(_WORD *)v31 != 49 )
                  v7 = 0;
              }
              *(_BYTE *)(a1 + 33) = v7;
              SysFreeString(bstrString);
              std::wstring::_Tidy_deallocate(v43);
            }
          }
          goto LABEL_59;
        }
      }
    }
    _com_issue_error(-2147467261);
  }
LABEL_61:
  if ( v38 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
  if ( *a2 )
    (*(void (__fastcall **)(__int64 *))(**a2 + 16))(*a2);
}

```

## disassembly

```asm
0x1400655ac  mov     [rsp-8+arg_10], rbx
0x1400655b1  push    rbp
0x1400655b2  push    rsi
0x1400655b3  push    rdi
0x1400655b4  push    r12
0x1400655b6  push    r13
0x1400655b8  push    r14
0x1400655ba  push    r15
0x1400655bc  lea     rbp, [rsp-27h]
0x1400655c1  sub     rsp, 90h
0x1400655c8  mov     rax, cs:__security_cookie
0x1400655cf  xor     rax, rsp
0x1400655d2  mov     [rbp+57h+var_38], rax
0x1400655d6  mov     r12, rdx
0x1400655d9  mov     rsi, rcx
0x1400655dc  mov     [rbp+57h+var_A0], rdx
0x1400655e0  mov     ebx, 4
0x1400655e5  mov     rax, gs:58h
0x1400655ee  mov     r14, [rax]
0x1400655f1  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1400655f5  xor     r13d, r13d
0x1400655f8  lea     r15d, [rdi+2]
0x1400655fc  mov     eax, [rbx+r14]
0x140065600  cmp     cs:?$TSS0@?1??Parse@TemplatePath@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z@4HA, eax
0x140065606  jg      loc_140065978
0x14006560c  mov     eax, [rbx+r14]
0x140065610  cmp     cs:?$TSS1@?1??Parse@TemplatePath@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z@4HA, eax
0x140065616  jg      loc_1400659F3
0x14006561c  mov     [rbp+57h+var_88], r13
0x140065620  mov     [rbp+57h+Src], r13
0x140065624  mov     rcx, [r12]
0x140065628  test    rcx, rcx
0x14006562b  jz      loc_140065A69
0x140065631  mov     rax, [rcx]
0x140065634  lea     rdx, [rbp+57h+Src]
0x140065638  mov     rax, [rax+0D0h]
0x14006563f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140065644  test    eax, eax
0x140065646  jnz     loc_14006590F
0x14006564c  mov     r9, [rbp+57h+Src]
0x140065650  mov     rdx, rdi
0x140065653  inc     rdx
0x140065656  cmp     [r9+rdx*2], r13w
0x14006565b  jnz     short loc_140065653
0x14006565d  cmp     rdx, [rsi+18h]
0x140065661  ja      short loc_14006568F
0x140065663  cmp     qword ptr [rsi+18h], 7
0x140065668  jbe     short loc_14006566F
0x14006566a  mov     r14, [rsi]
0x14006566d  jmp     short loc_140065672
0x14006566f  mov     r14, rsi
0x140065672  mov     [rsi+10h], rdx
0x140065676  lea     rbx, [rdx+rdx]
0x14006567a  mov     r8, rbx; Size
0x14006567d  mov     rdx, r9; Src
0x140065680  mov     rcx, r14; void *
0x140065683  call    memmove_0
0x140065688  mov     [rbx+r14], r13w
0x14006568d  jmp     short loc_140065697
0x14006568f  mov     rcx, rsi
0x140065692  call    ??$_Reallocate_for@V_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@Z; std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(unsigned __int64,_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *)
0x140065697  mov     [rbp+57h+var_80], r13
0x14006569b  mov     rcx, [r12]
0x14006569f  test    rcx, rcx
0x1400656a2  jz      loc_14006596D
0x1400656a8  mov     rax, [rcx]
0x1400656ab  mov     [rbp+57h+var_80], r13
0x1400656af  lea     rdx, [rbp+57h+var_80]
0x1400656b3  mov     rax, [rax+88h]
0x1400656ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400656bf  test    eax, eax
0x1400656c1  jnz     loc_1400658EE
0x1400656c7  mov     rbx, [rbp+57h+var_80]
0x1400656cb  test    rbx, rbx
0x1400656ce  jz      loc_14006596D
0x1400656d4  mov     rax, [rbx]
0x1400656d7  mov     r14, [rax+38h]
0x1400656db  mov     rcx, [rbp+57h+var_88]
0x1400656df  test    rcx, rcx
0x1400656e2  jz      short loc_1400656F1
0x1400656e4  mov     rax, [rcx]
0x1400656e7  mov     rax, [rax+10h]
0x1400656eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400656f0  nop
0x1400656f1  mov     [rbp+57h+var_88], r13
0x1400656f5  mov     rax, cs:?recursiveString@?1??Parse@TemplatePath@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z@4V_bstr_t@@B; _bstr_t const `Uev::TemplatePath::Parse(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>)'::`2'::recursiveString
0x1400656fc  test    rax, rax
0x1400656ff  jz      short loc_140065706
0x140065701  mov     rdx, [rax]
0x140065704  jmp     short loc_140065709
0x140065706  mov     rdx, r13
0x140065709  lea     r8, [rbp+57h+var_88]
0x14006570d  mov     rcx, rbx
0x140065710  mov     rax, r14
0x140065713  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140065718  mov     r14d, 4
0x14006571e  test    eax, eax
0x140065720  jnz     loc_1400657DC
0x140065726  mov     [rbp+57h+bstrString], r13
0x14006572a  mov     rcx, [rbp+57h+var_88]
0x14006572e  test    rcx, rcx
0x140065731  jz      loc_140065A74
0x140065737  mov     rax, [rcx]
0x14006573a  lea     rdx, [rbp+57h+bstrString]
0x14006573e  mov     rax, [rax+0D0h]
0x140065745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006574a  test    eax, eax
0x14006574c  jnz     loc_1400657DC
0x140065752  mov     rdx, [rbp+57h+bstrString]
0x140065756  xorps   xmm0, xmm0
0x140065759  movups  xmmword ptr [rbp+57h+S1], xmm0
0x14006575d  mov     [rbp+57h+var_68], r13
0x140065761  mov     [rbp+57h+var_60], r13
0x140065765  mov     r8, rdi
0x140065768  inc     r8
0x14006576b  cmp     [rdx+r8*2], r13w
0x140065770  jnz     short loc_140065768
0x140065772  lea     rcx, [rbp+57h+S1]
0x140065776  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x14006577b  mov     rbx, [rbp+57h+var_68]
0x14006577f  lea     rcx, [rbp+57h+S1]
0x140065783  cmp     [rbp+57h+var_60], 7
0x140065788  cmova   rcx, [rbp+57h+S1]; S1
0x14006578d  mov     r8, rbx
0x140065790  cmp     rbx, r14
0x140065793  cmova   r8, r14; N
0x140065797  lea     rdx, aTrue; "true"
0x14006579e  call    wmemcmp
0x1400657a3  test    eax, eax
0x1400657a5  jnz     short loc_1400657AC
0x1400657a7  cmp     rbx, r14
0x1400657aa  jz      short loc_1400657C3
0x1400657ac  lea     rax, [rbp+57h+S1]
0x1400657b0  cmp     [rbp+57h+var_60], 7
0x1400657b5  cmova   rax, [rbp+57h+S1]
0x1400657ba  cmp     word ptr [rax], 31h ; '1'
0x1400657be  mov     al, r13b
0x1400657c1  jnz     short loc_1400657C6
0x1400657c3  mov     al, r15b
0x1400657c6  mov     [rsi+20h], al
0x1400657c9  mov     rcx, [rbp+57h+bstrString]; bstrString
0x1400657cd  call    cs:__imp_SysFreeString
0x1400657d3  lea     rcx, [rbp+57h+S1]
0x1400657d7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400657dc  mov     rbx, [rbp+57h+var_80]
0x1400657e0  test    rbx, rbx
0x1400657e3  jz      loc_14006596D
0x1400657e9  mov     rax, [rbx]
0x1400657ec  mov     r14, [rax+38h]
0x1400657f0  mov     rcx, [rbp+57h+var_88]
0x1400657f4  test    rcx, rcx
0x1400657f7  jz      short loc_140065806
0x1400657f9  mov     rax, [rcx]
0x1400657fc  mov     rax, [rax+10h]
0x140065800  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140065805  nop
0x140065806  mov     [rbp+57h+var_88], r13
0x14006580a  mov     rax, cs:?deleteIfNotFoundString@?1??Parse@TemplatePath@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z@4V_bstr_t@@B; _bstr_t const `Uev::TemplatePath::Parse(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>)'::`2'::deleteIfNotFoundString
0x140065811  test    rax, rax
0x140065814  jz      short loc_14006581B
0x140065816  mov     rdx, [rax]
0x140065819  jmp     short loc_14006581E
0x14006581b  mov     rdx, r13
0x14006581e  lea     r8, [rbp+57h+var_88]
0x140065822  mov     rcx, rbx
0x140065825  mov     rax, r14
0x140065828  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006582d  test    eax, eax
0x14006582f  jnz     loc_1400658EE
0x140065835  mov     [rbp+57h+bstrString], r13
0x140065839  mov     rcx, [rbp+57h+var_88]
0x14006583d  test    rcx, rcx
0x140065840  jz      loc_140065962
0x140065846  mov     rax, [rcx]
0x140065849  lea     rdx, [rbp+57h+bstrString]
0x14006584d  mov     rax, [rax+0D0h]
0x140065854  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140065859  test    eax, eax
0x14006585b  jnz     loc_1400658EE
0x140065861  mov     rdx, [rbp+57h+bstrString]
0x140065865  xorps   xmm0, xmm0
0x140065868  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x14006586c  mov     [rbp+57h+var_48], r13
0x140065870  mov     [rbp+57h+var_40], r13
0x140065874  inc     rdi
0x140065877  cmp     [rdx+rdi*2], r13w
0x14006587c  jnz     short loc_140065874
0x14006587e  mov     r8, rdi
0x140065881  lea     rcx, [rbp+57h+var_58]
0x140065885  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x14006588a  mov     rbx, [rbp+57h+var_48]
0x14006588e  lea     rcx, [rbp+57h+var_58]
0x140065892  cmp     [rbp+57h+var_40], 7
0x140065897  cmova   rcx, [rbp+57h+var_58]; S1
0x14006589c  mov     r8, rbx
0x14006589f  mov     edi, 4
0x1400658a4  cmp     rbx, rdi
0x1400658a7  cmova   r8, rdi; N
0x1400658ab  lea     rdx, aTrue; "true"
0x1400658b2  call    wmemcmp
0x1400658b7  test    eax, eax
0x1400658b9  jnz     short loc_1400658C0
0x1400658bb  cmp     rbx, rdi
0x1400658be  jz      short loc_1400658D7
0x1400658c0  lea     rax, [rbp+57h+var_58]
0x1400658c4  cmp     [rbp+57h+var_40], 7
0x1400658c9  cmova   rax, [rbp+57h+var_58]
0x1400658ce  cmp     word ptr [rax], 31h ; '1'
0x1400658d2  jz      short loc_1400658D7
0x1400658d4  mov     r15b, r13b
0x1400658d7  mov     [rsi+21h], r15b
0x1400658db  mov     rcx, [rbp+57h+bstrString]; bstrString
0x1400658df  call    cs:__imp_SysFreeString
0x1400658e5  lea     rcx, [rbp+57h+var_58]
0x1400658e9  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400658ee  mov     rcx, [rbp+57h+Src]; bstrString
0x1400658f2  call    cs:__imp_SysFreeString
0x1400658f8  nop
0x1400658f9  mov     rcx, [rbp+57h+var_80]
0x1400658fd  test    rcx, rcx
0x140065900  jz      short loc_14006590F
0x140065902  mov     rax, [rcx]
0x140065905  mov     rax, [rax+10h]
0x140065909  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006590e  nop
0x14006590f  mov     rcx, [rbp+57h+var_88]
0x140065913  test    rcx, rcx
0x140065916  jz      short loc_140065925
0x140065918  mov     rax, [rcx]
0x14006591b  mov     rax, [rax+10h]
0x14006591f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140065924  nop
0x140065925  mov     rcx, [r12]
0x140065929  test    rcx, rcx
0x14006592c  jz      short loc_14006593B
0x14006592e  mov     rax, [rcx]
0x140065931  mov     rax, [rax+10h]
0x140065935  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006593a  nop
0x14006593b  mov     rcx, [rbp+57h+var_38]
0x14006593f  xor     rcx, rsp; StackCookie
0x140065942  call    __security_check_cookie
0x140065947  mov     rbx, [rsp+0C0h+arg_10]
0x14006594f  add     rsp, 90h
0x140065956  pop     r15
0x140065958  pop     r14
0x14006595a  pop     r13
0x14006595c  pop     r12
0x14006595e  pop     rdi
0x14006595f  pop     rsi
0x140065960  pop     rbp
0x140065961  retn
0x140065962  mov     ecx, 80004003h; int
0x140065967  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x14006596d  mov     ecx, 80004003h; int
0x140065972  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x140065978  lea     rcx, ?$TSS0@?1??Parse@TemplatePath@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z@4HA
0x14006597f  call    _Init_thread_header
0x140065984  cmp     cs:?$TSS0@?1??Parse@TemplatePath@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z@4HA, edi
0x14006598a  jnz     loc_14006560C
0x140065990  mov     ecx, 18h; Size
0x140065995  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14006599a  mov     rbx, rax
0x14006599d  mov     [rbp+57h+bstrString], rax
0x1400659a1  mov     [rax+8], r13
0x1400659a5  mov     [rax+10h], r15d
0x1400659a9  lea     rcx, aRecursive; "Recursive"
0x1400659b0  call    cs:__imp_SysAllocString
0x1400659b6  mov     [rbx], rax
0x1400659b9  test    rax, rax
0x1400659bc  jnz     short loc_1400659C9
0x1400659be  mov     ecx, 8007000Eh; int
0x1400659c3  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1400659c9  mov     cs:?recursiveString@?1??Parse@TemplatePath@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z@4V_bstr_t@@B, rbx; _bstr_t const `Uev::TemplatePath::Parse(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>)'::`2'::recursiveString
0x1400659d0  lea     rcx, ??__FrecursiveString@?1??Parse@TemplatePath@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z@YAXXZ; void (__cdecl *)()
0x1400659d7  call    atexit
0x1400659dc  nop
0x1400659dd  lea     rcx, ?$TSS0@?1??Parse@TemplatePath@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z@4HA
0x1400659e4  call    _Init_thread_footer
0x1400659e9  mov     ebx, 4
0x1400659ee  jmp     loc_14006560C
0x1400659f3  lea     rcx, ?$TSS1@?1??Parse@TemplatePath@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z@4HA
0x1400659fa  call    _Init_thread_header
0x1400659ff  cmp     cs:?$TSS1@?1??Parse@TemplatePath@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z@4HA, edi
0x140065a05  jnz     loc_14006561C
0x140065a0b  mov     ecx, 18h; Size
0x140065a10  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140065a15  mov     rbx, rax
0x140065a18  mov     [rbp+57h+bstrString], rax
0x140065a1c  mov     [rax+8], r13
0x140065a20  mov     [rax+10h], r15d
0x140065a24  lea     rcx, aDeleteifnotfou; "DeleteIfNotFound"
0x140065a2b  call    cs:__imp_SysAllocString
0x140065a31  mov     [rbx], rax
0x140065a34  test    rax, rax
0x140065a37  jnz     short loc_140065A44
0x140065a39  mov     ecx, 8007000Eh; int
0x140065a3e  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x140065a44  mov     cs:?deleteIfNotFoundString@?1??Parse@TemplatePath@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z@4V_bstr_t@@B, rbx; _bstr_t const `Uev::TemplatePath::Parse(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>)'::`2'::deleteIfNotFoundString
0x140065a4b  lea     rcx, ??__FdeleteIfNotFoundString@?1??Parse@TemplatePath@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z@YAXXZ; void (__cdecl *)()
  ... truncated ...
```
