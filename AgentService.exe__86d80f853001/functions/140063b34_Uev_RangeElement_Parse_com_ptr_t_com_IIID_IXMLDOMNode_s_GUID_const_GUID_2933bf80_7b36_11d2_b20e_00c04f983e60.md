# Uev::RangeElement::Parse(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>)

- ea: `0x140063b34`
- end: `0x140063f4e`
- name: `?Parse@RangeElement@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z`
- size: `1050`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14004af5c`
- `0x14004d5e8`
- `0x140050898`

## callees

- `0x140003e50`
- `0x140003e74`
- `0x14000423c`
- `0x140004ab4`
- `0x14000aa1c`
- `0x14000aa84`
- `0x140011cf8`
- `0x14005e368`
- `0x140063b34`
- `0x140087a7c`
- `0x14009b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x140063c3e`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x140063ced`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x140063c3e`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x140063ced`
- `OLEAUT32!__imp_SysAllocString` at `0x140063e46`
- `OLEAUT32!__imp_SysAllocString` at `0x140063ec0`
- `OLEAUT32!__imp_SysAllocString` at `0x140063e46`
- `OLEAUT32!__imp_SysAllocString` at `0x140063ec0`
- `OLEAUT32!__imp_SysFreeString` at `0x140063c4f`
- `OLEAUT32!__imp_SysFreeString` at `0x140063cff`
- `OLEAUT32!__imp_SysFreeString` at `0x140063c4f`
- `OLEAUT32!__imp_SysFreeString` at `0x140063cff`

## string_xrefs

- `0x140063ddb`: `Failure reading maximum attribute.`
- `0x140063dac`: `Failure reading minimum attribute.`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall Uev::RangeElement::Parse(__int64 a1, _QWORD *a2)
{
  __int64 *ThreadLocalStoragePointer; // rax
  __int64 v5; // r14
  __int64 *v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rcx
  __int64 (__fastcall *v9)(__int64, __int64, __int64 *); // r9
  __int64 v10; // rdx
  int v11; // eax
  int v12; // eax
  __int64 v13; // rbx
  __int64 (__fastcall *v14)(__int64, __int64, __int64 *); // r14
  __int64 v15; // rdx
  int v16; // eax
  int v17; // eax
  OLECHAR *v18; // rbx
  BSTR v19; // rax
  OLECHAR *v20; // rbx
  BSTR v21; // rax
  _BYTE v22[32]; // [rsp+20h] [rbp-59h] BYREF
  _QWORD *v23; // [rsp+40h] [rbp-39h]
  _QWORD pExceptionObject[8]; // [rsp+50h] [rbp-29h] BYREF
  BSTR bstrString; // [rsp+90h] [rbp+17h] BYREF
  __int64 v26; // [rsp+98h] [rbp+1Fh] BYREF
  __int64 v27; // [rsp+A0h] [rbp+27h] BYREF

  v23 = a2;
  ThreadLocalStoragePointer = (__int64 *)NtCurrentTeb()->ThreadLocalStoragePointer;
  v5 = *ThreadLocalStoragePointer;
  if ( __TSS0__1__Parse_RangeElement_Uev__QEAAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B_____Z_4HA > *(_DWORD *)(*ThreadLocalStoragePointer + 4) )
  {
    Init_thread_header(&__TSS0__1__Parse_RangeElement_Uev__QEAAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B_____Z_4HA);
    if ( __TSS0__1__Parse_RangeElement_Uev__QEAAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B_____Z_4HA == -1 )
    {
      v18 = (OLECHAR *)operator new(0x18u);
      bstrString = v18;
      *((_QWORD *)v18 + 1) = 0;
      *((_DWORD *)v18 + 4) = 1;
      v19 = SysAllocString(L"Minimum");
      *(_QWORD *)v18 = v19;
      if ( !v19 )
        _com_issue_error(-2147024882);
      `Uev::RangeElement::Parse'::`2'::minimumString = v18;
      atexit(`Uev::RangeElement::Parse'::`2'::`dynamic atexit destructor for 'minimumString'');
      Init_thread_footer(&__TSS0__1__Parse_RangeElement_Uev__QEAAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B_____Z_4HA);
    }
  }
  if ( __TSS1__1__Parse_RangeElement_Uev__QEAAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B_____Z_4HA > *(_DWORD *)(v5 + 4) )
  {
    Init_thread_header(&__TSS1__1__Parse_RangeElement_Uev__QEAAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B_____Z_4HA);
    if ( __TSS1__1__Parse_RangeElement_Uev__QEAAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B_____Z_4HA == -1 )
    {
      v20 = (OLECHAR *)operator new(0x18u);
      bstrString = v20;
      *((_QWORD *)v20 + 1) = 0;
      *((_DWORD *)v20 + 4) = 1;
      v21 = SysAllocString(L"Maximum");
      *(_QWORD *)v20 = v21;
      if ( !v21 )
        _com_issue_error(-2147024882);
      `Uev::RangeElement::Parse'::`2'::maximumString = v20;
      atexit(`Uev::RangeElement::Parse'::`2'::`dynamic atexit destructor for 'maximumString'');
      Init_thread_footer(&__TSS1__1__Parse_RangeElement_Uev__QEAAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B_____Z_4HA);
    }
  }
  *(_BYTE *)(a1 + 8) = 0;
  v6 = (__int64 *)*a2;
  if ( *a2 )
  {
    v27 = 0;
    v7 = *v6;
    v27 = 0;
    (*(void (__fastcall **)(__int64 *, __int64 *))(v7 + 136))(v6, &v27);
    v8 = v27;
    if ( v27 )
    {
      v26 = 0;
      v9 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v27 + 56LL);
      v26 = 0;
      if ( `Uev::RangeElement::Parse'::`2'::minimumString )
        v10 = *`Uev::RangeElement::Parse'::`2'::minimumString;
      else
        v10 = 0;
      v11 = v9(v27, v10, &v26);
      if ( v11 )
      {
        if ( v11 == 1 )
        {
          std::string::string(v22, "Missing minimum attribute.");
          Uev::InvalidXmlException::InvalidXmlException(pExceptionObject, (__int64)v22);
          throw (Uev::InvalidXmlException *)pExceptionObject;
        }
        if ( v11 < 0 )
        {
          std::string::string(v22, "Failure reading minimum attribute.");
          Uev::InvalidXmlException::InvalidXmlException(pExceptionObject, (__int64)v22);
          throw (Uev::InvalidXmlException *)pExceptionObject;
        }
      }
      else
      {
        bstrString = 0;
        if ( !v26 )
          _com_issue_error(-2147467261);
        if ( (*(int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v26 + 208LL))(v26, &bstrString) < 0 )
          v12 = 0;
        else
          v12 = _o__wtoi(bstrString);
        *(_DWORD *)a1 = v12;
        SysFreeString(bstrString);
      }
      v13 = v27;
      if ( !v27 )
        _com_issue_error(-2147467261);
      v14 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v27 + 56LL);
      if ( v26 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
      v26 = 0;
      if ( `Uev::RangeElement::Parse'::`2'::maximumString )
        v15 = *`Uev::RangeElement::Parse'::`2'::maximumString;
      else
        v15 = 0;
      v16 = v14(v13, v15, &v26);
      if ( v16 )
      {
        if ( v16 == 1 )
        {
          std::string::string(v22, "Missing maximum attribute.");
          Uev::InvalidXmlException::InvalidXmlException(pExceptionObject, (__int64)v22);
          throw (Uev::InvalidXmlException *)pExceptionObject;
        }
        if ( v16 < 0 )
        {
          std::string::string(v22, "Failure reading maximum attribute.");
          Uev::InvalidXmlException::InvalidXmlException(pExceptionObject, (__int64)v22);
          throw (Uev::InvalidXmlException *)pExceptionObject;
        }
      }
      else
      {
        bstrString = 0;
        if ( !v26 )
          _com_issue_error(-2147467261);
        if ( (*(int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v26 + 208LL))(v26, &bstrString) < 0 )
          v17 = 0;
        else
          v17 = _o__wtoi(bstrString);
        *(_DWORD *)(a1 + 4) = v17;
        SysFreeString(bstrString);
      }
      *(_BYTE *)(a1 + 8) = 1;
      if ( v26 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
      v8 = v27;
    }
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  else
  {
    *(_QWORD *)a1 = 0;
  }
  if ( *a2 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 16LL))(*a2);
}

```

## disassembly

```asm
0x140063b34  mov     [rsp-8+arg_10], rbx
0x140063b39  mov     [rsp-8+arg_18], rsi
0x140063b3e  push    rbp
0x140063b3f  push    rdi
0x140063b40  push    r13
0x140063b42  push    r14
0x140063b44  push    r15
0x140063b46  lea     rbp, [rsp-37h]
0x140063b4b  sub     rsp, 0B0h
0x140063b52  mov     rax, cs:__security_cookie
0x140063b59  xor     rax, rsp
0x140063b5c  mov     [rbp+57h+var_28], rax
0x140063b60  mov     rsi, rdx
0x140063b63  mov     rdi, rcx
0x140063b66  mov     [rbp+57h+var_90], rdx
0x140063b6a  mov     r13d, 4
0x140063b70  mov     rax, gs:58h
0x140063b79  mov     r14, [rax]
0x140063b7c  xor     r15d, r15d
0x140063b7f  mov     eax, [r14+r13]
0x140063b83  cmp     cs:?$TSS0@?1??Parse@RangeElement@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z@4HA, eax
0x140063b89  jg      loc_140063E0A
0x140063b8f  mov     eax, [r14+r13]
0x140063b93  cmp     cs:?$TSS1@?1??Parse@RangeElement@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z@4HA, eax
0x140063b99  jg      loc_140063E84
0x140063b9f  mov     [rdi+8], r15b
0x140063ba3  mov     rcx, [rsi]
0x140063ba6  test    rcx, rcx
0x140063ba9  jnz     short loc_140063BB3
0x140063bab  mov     [rdi], r15
0x140063bae  jmp     loc_140063D35
0x140063bb3  mov     [rbp+57h+var_30], r15
0x140063bb7  mov     rax, [rcx]
0x140063bba  mov     [rbp+57h+var_30], r15
0x140063bbe  lea     rdx, [rbp+57h+var_30]
0x140063bc2  mov     rax, [rax+88h]
0x140063bc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140063bce  mov     rcx, [rbp+57h+var_30]
0x140063bd2  test    rcx, rcx
0x140063bd5  jz      loc_140063D23
0x140063bdb  mov     [rbp+57h+var_38], r15
0x140063bdf  mov     rax, [rcx]
0x140063be2  mov     r9, [rax+38h]
0x140063be6  mov     [rbp+57h+var_38], r15
0x140063bea  mov     rax, cs:?minimumString@?1??Parse@RangeElement@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z@4V_bstr_t@@B; _bstr_t const `Uev::RangeElement::Parse(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>)'::`2'::minimumString
0x140063bf1  test    rax, rax
0x140063bf4  jz      short loc_140063BFB
0x140063bf6  mov     rdx, [rax]
0x140063bf9  jmp     short loc_140063BFE
0x140063bfb  mov     rdx, r15
0x140063bfe  lea     r8, [rbp+57h+var_38]
0x140063c02  mov     rax, r9
0x140063c05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140063c0a  test    eax, eax
0x140063c0c  jnz     loc_140063C94
0x140063c12  mov     [rbp+57h+bstrString], r15
0x140063c16  mov     rcx, [rbp+57h+var_38]
0x140063c1a  test    rcx, rcx
0x140063c1d  jz      loc_140063EFE
0x140063c23  mov     rax, [rcx]
0x140063c26  lea     rdx, [rbp+57h+bstrString]
0x140063c2a  mov     rax, [rax+0D0h]
0x140063c31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140063c36  test    eax, eax
0x140063c38  js      short loc_140063C46
0x140063c3a  mov     rcx, [rbp+57h+bstrString]
0x140063c3e  call    cs:__imp__o__wtoi
0x140063c44  jmp     short loc_140063C49
0x140063c46  mov     eax, r15d
0x140063c49  mov     [rdi], eax
0x140063c4b  mov     rcx, [rbp+57h+bstrString]; bstrString
0x140063c4f  call    cs:__imp_SysFreeString
0x140063c55  mov     rbx, [rbp+57h+var_30]
0x140063c59  test    rbx, rbx
0x140063c5c  jz      loc_140063F09
0x140063c62  mov     rax, [rbx]
0x140063c65  mov     r14, [rax+38h]
0x140063c69  mov     rcx, [rbp+57h+var_38]
0x140063c6d  test    rcx, rcx
0x140063c70  jz      short loc_140063C7F
0x140063c72  mov     rax, [rcx]
0x140063c75  mov     rax, [rax+10h]
0x140063c79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140063c7e  nop
0x140063c7f  mov     [rbp+57h+var_38], r15
0x140063c83  mov     rax, cs:?maximumString@?1??Parse@RangeElement@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z@4V_bstr_t@@B; _bstr_t const `Uev::RangeElement::Parse(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>)'::`2'::maximumString
0x140063c8a  test    rax, rax
0x140063c8d  jz      short loc_140063CA7
0x140063c8f  mov     rdx, [rax]
0x140063c92  jmp     short loc_140063CAA
0x140063c94  cmp     eax, 1
0x140063c97  jz      loc_140063F14
0x140063c9d  test    eax, eax
0x140063c9f  js      loc_140063DAC
0x140063ca5  jmp     short loc_140063C55
0x140063ca7  mov     rdx, r15
0x140063caa  lea     r8, [rbp+57h+var_38]
0x140063cae  mov     rcx, rbx
0x140063cb1  mov     rax, r14
0x140063cb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140063cb9  test    eax, eax
0x140063cbb  jnz     loc_140063D72
0x140063cc1  mov     [rbp+57h+bstrString], r15
0x140063cc5  mov     rcx, [rbp+57h+var_38]
0x140063cc9  test    rcx, rcx
0x140063ccc  jz      loc_140063F43
0x140063cd2  mov     rax, [rcx]
0x140063cd5  lea     rdx, [rbp+57h+bstrString]
0x140063cd9  mov     rax, [rax+0D0h]
0x140063ce0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140063ce5  test    eax, eax
0x140063ce7  js      short loc_140063CF5
0x140063ce9  mov     rcx, [rbp+57h+bstrString]
0x140063ced  call    cs:__imp__o__wtoi
0x140063cf3  jmp     short loc_140063CF8
0x140063cf5  mov     eax, r15d
0x140063cf8  mov     [rdi+4], eax
0x140063cfb  mov     rcx, [rbp+57h+bstrString]; bstrString
0x140063cff  call    cs:__imp_SysFreeString
0x140063d05  mov     byte ptr [rdi+8], 1
0x140063d09  mov     rcx, [rbp+57h+var_38]
0x140063d0d  test    rcx, rcx
0x140063d10  jz      short loc_140063D1F
0x140063d12  mov     rax, [rcx]
0x140063d15  mov     rax, [rax+10h]
0x140063d19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140063d1e  nop
0x140063d1f  mov     rcx, [rbp+57h+var_30]
0x140063d23  test    rcx, rcx
0x140063d26  jz      short loc_140063D35
0x140063d28  mov     rax, [rcx]
0x140063d2b  mov     rax, [rax+10h]
0x140063d2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140063d34  nop
0x140063d35  mov     rcx, [rsi]
0x140063d38  test    rcx, rcx
0x140063d3b  jz      short loc_140063D4A
0x140063d3d  mov     rax, [rcx]
0x140063d40  mov     rax, [rax+10h]
0x140063d44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140063d49  nop
0x140063d4a  mov     rcx, [rbp+57h+var_28]
0x140063d4e  xor     rcx, rsp; StackCookie
0x140063d51  call    __security_check_cookie
0x140063d56  lea     r11, [rsp+0D0h+var_20]
0x140063d5e  mov     rbx, [r11+40h]
0x140063d62  mov     rsi, [r11+48h]
0x140063d66  mov     rsp, r11
0x140063d69  pop     r15
0x140063d6b  pop     r14
0x140063d6d  pop     r13
0x140063d6f  pop     rdi
0x140063d70  pop     rbp
0x140063d71  retn
0x140063d72  cmp     eax, 1
0x140063d75  jz      short loc_140063D7D
0x140063d77  test    eax, eax
0x140063d79  js      short loc_140063DDB
0x140063d7b  jmp     short loc_140063D05
0x140063d7d  lea     rdx, aMissingMaximum; "Missing maximum attribute."
0x140063d84  lea     rcx, [rbp+57h+var_B0]
0x140063d88  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140063d8d  nop
0x140063d8e  lea     rdx, [rbp+57h+var_B0]
0x140063d92  lea     rcx, [rbp+57h+pExceptionObject]
0x140063d96  call    ??0InvalidXmlException@Uev@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Uev::InvalidXmlException::InvalidXmlException(std::string const &)
0x140063d9b  lea     rdx, _TI3?AVInvalidXmlException@Uev@@; pThrowInfo
0x140063da2  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140063da6  call    _CxxThrowException_0
0x140063dac  lea     rdx, aFailureReading_0; "Failure reading minimum attribute."
0x140063db3  lea     rcx, [rbp+57h+var_B0]
0x140063db7  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140063dbc  nop
0x140063dbd  lea     rdx, [rbp+57h+var_B0]
0x140063dc1  lea     rcx, [rbp+57h+pExceptionObject]
0x140063dc5  call    ??0InvalidXmlException@Uev@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Uev::InvalidXmlException::InvalidXmlException(std::string const &)
0x140063dca  lea     rdx, _TI3?AVInvalidXmlException@Uev@@; pThrowInfo
0x140063dd1  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140063dd5  call    _CxxThrowException_0
0x140063ddb  lea     rdx, aFailureReading; "Failure reading maximum attribute."
0x140063de2  lea     rcx, [rbp+57h+var_B0]
0x140063de6  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140063deb  nop
0x140063dec  lea     rdx, [rbp+57h+var_B0]
0x140063df0  lea     rcx, [rbp+57h+pExceptionObject]
0x140063df4  call    ??0InvalidXmlException@Uev@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Uev::InvalidXmlException::InvalidXmlException(std::string const &)
0x140063df9  lea     rdx, _TI3?AVInvalidXmlException@Uev@@; pThrowInfo
0x140063e00  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140063e04  call    _CxxThrowException_0
0x140063e0a  lea     rcx, ?$TSS0@?1??Parse@RangeElement@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z@4HA
0x140063e11  call    _Init_thread_header
0x140063e16  cmp     cs:?$TSS0@?1??Parse@RangeElement@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z@4HA, 0FFFFFFFFh
0x140063e1d  jnz     loc_140063B8F
0x140063e23  mov     ecx, 18h; Size
0x140063e28  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140063e2d  mov     rbx, rax
0x140063e30  mov     [rbp+57h+bstrString], rax
0x140063e34  mov     [rax+8], r15
0x140063e38  mov     dword ptr [rax+10h], 1
0x140063e3f  lea     rcx, aMinimum; "Minimum"
0x140063e46  call    cs:__imp_SysAllocString
0x140063e4c  mov     [rbx], rax
0x140063e4f  test    rax, rax
0x140063e52  jnz     short loc_140063E5F
0x140063e54  mov     ecx, 8007000Eh; int
0x140063e59  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x140063e5f  mov     cs:?minimumString@?1??Parse@RangeElement@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z@4V_bstr_t@@B, rbx; _bstr_t const `Uev::RangeElement::Parse(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>)'::`2'::minimumString
0x140063e66  lea     rcx, ??__FminimumString@?1??Parse@RangeElement@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z@YAXXZ; void (__cdecl *)()
0x140063e6d  call    atexit
0x140063e72  nop
0x140063e73  lea     rcx, ?$TSS0@?1??Parse@RangeElement@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z@4HA
0x140063e7a  call    _Init_thread_footer
0x140063e7f  jmp     loc_140063B8F
0x140063e84  lea     rcx, ?$TSS1@?1??Parse@RangeElement@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z@4HA
0x140063e8b  call    _Init_thread_header
0x140063e90  cmp     cs:?$TSS1@?1??Parse@RangeElement@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z@4HA, 0FFFFFFFFh
0x140063e97  jnz     loc_140063B9F
0x140063e9d  mov     ecx, 18h; Size
0x140063ea2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140063ea7  mov     rbx, rax
0x140063eaa  mov     [rbp+57h+bstrString], rax
0x140063eae  mov     [rax+8], r15
0x140063eb2  mov     dword ptr [rax+10h], 1
0x140063eb9  lea     rcx, aMaximum; "Maximum"
0x140063ec0  call    cs:__imp_SysAllocString
0x140063ec6  mov     [rbx], rax
0x140063ec9  test    rax, rax
0x140063ecc  jnz     short loc_140063ED9
0x140063ece  mov     ecx, 8007000Eh; int
0x140063ed3  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x140063ed9  mov     cs:?maximumString@?1??Parse@RangeElement@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z@4V_bstr_t@@B, rbx; _bstr_t const `Uev::RangeElement::Parse(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>)'::`2'::maximumString
0x140063ee0  lea     rcx, ??__FmaximumString@?1??Parse@RangeElement@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z@YAXXZ; void (__cdecl *)()
0x140063ee7  call    atexit
0x140063eec  nop
0x140063eed  lea     rcx, ?$TSS1@?1??Parse@RangeElement@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z@4HA
0x140063ef4  call    _Init_thread_footer
0x140063ef9  jmp     loc_140063B9F
0x140063efe  mov     ecx, 80004003h; int
0x140063f03  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x140063f09  mov     ecx, 80004003h; int
0x140063f0e  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x140063f14  lea     rdx, aMissingMinimum; "Missing minimum attribute."
0x140063f1b  lea     rcx, [rbp+57h+var_B0]
0x140063f1f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140063f24  nop
0x140063f25  lea     rdx, [rbp+57h+var_B0]
0x140063f29  lea     rcx, [rbp+57h+pExceptionObject]
0x140063f2d  call    ??0InvalidXmlException@Uev@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Uev::InvalidXmlException::InvalidXmlException(std::string const &)
0x140063f32  lea     rdx, _TI3?AVInvalidXmlException@Uev@@; pThrowInfo
0x140063f39  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140063f3d  call    _CxxThrowException_0
0x140063f43  mov     ecx, 80004003h; int
0x140063f48  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
