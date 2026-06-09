# Uev::FileRoot::Parse<1>(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>)

- ea: `0x140048f30`
- end: `0x140049392`
- name: `??$Parse@$00@FileRoot@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z`
- size: `1122`
- prototype: `void __fastcall(__int64, BSTR **)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140049398`

## callees

- `0x140003e74`
- `0x14000423c`
- `0x140004ab4`
- `0x14000aa1c`
- `0x14000aa84`
- `0x14000ba60`
- `0x140011cf8`
- `0x1400260ec`
- `0x140048f30`
- `0x14005f408`
- `0x140060494`
- `0x14006059c`
- `0x140061c00`
- `0x1400663e4`
- `0x140087a7c`
- `0x14009b010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x140048fc1`
- `OLEAUT32!__imp_SysAllocString` at `0x14004906a`
- `OLEAUT32!__imp_SysAllocString` at `0x140049116`
- `OLEAUT32!__imp_SysAllocString` at `0x140048fc1`
- `OLEAUT32!__imp_SysAllocString` at `0x14004906a`
- `OLEAUT32!__imp_SysAllocString` at `0x140049116`

## string_xrefs

- `0x140049063`: `RegistryEntry`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Uev::FileRoot::Parse<1>(__int64 a1, BSTR **a2)
{
  _bstr_t *v4; // rsi
  BSTR *v5; // rbx
  BSTR v6; // rax
  __int64 v7; // rbx
  _bstr_t *v8; // rax
  _bstr_t *v9; // rsi
  _bstr_t *v10; // rsi
  BSTR *v11; // rbx
  BSTR v12; // rax
  __int64 v13; // rbx
  _bstr_t *v14; // rax
  _bstr_t *v15; // rsi
  _bstr_t *v16; // rsi
  BSTR *v17; // rbx
  BSTR v18; // rax
  __int64 v19; // rsi
  _bstr_t *v20; // rax
  _bstr_t *v21; // rbx
  __int64 *v22; // rbx
  int v23; // r12d
  volatile signed __int32 *v24; // rax
  __int64 v25; // rsi
  BSTR *v26; // rcx
  __int64 v27; // rsi
  __int64 **v28; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  _QWORD *v31; // rax
  BSTR *v32; // [rsp+20h] [rbp-69h] BYREF
  int v33; // [rsp+28h] [rbp-61h] BYREF
  char v34[8]; // [rsp+30h] [rbp-59h] BYREF
  int v35; // [rsp+38h] [rbp-51h] BYREF
  _QWORD v36[2]; // [rsp+40h] [rbp-49h] BYREF
  _BYTE v37[32]; // [rsp+50h] [rbp-39h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+70h] [rbp-19h] BYREF

  v36[1] = a2;
  if ( __TSS0__1____Parse__00_FileRoot_Uev__QEAAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B_____Z_4HA > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 4LL) )
  {
    Init_thread_header(&__TSS0__1____Parse__00_FileRoot_Uev__QEAAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B_____Z_4HA);
    if ( __TSS0__1____Parse__00_FileRoot_Uev__QEAAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B_____Z_4HA == -1 )
    {
      `Uev::FileRoot::Parse<1>'::`2'::rootStringTypes = 0;
      qword_1400D2298 = 0;
      v31 = operator new(0x30u);
      *v31 = v31;
      v31[1] = v31;
      v31[2] = v31;
      *((_WORD *)v31 + 12) = 257;
      `Uev::FileRoot::Parse<1>'::`2'::rootStringTypes = (__int64)v31;
      atexit(`Uev::FileRoot::Parse<1>'::`2'::`dynamic atexit destructor for 'rootStringTypes'');
      Init_thread_footer(&__TSS0__1____Parse__00_FileRoot_Uev__QEAAXV___com_ptr_t_V___com_IIID_UIXMLDOMNode___1__GUID_2933bf80_7b36_11d2_b20e_00c04f983e60__3U__s_GUID__B_____Z_4HA);
    }
  }
  if ( !qword_1400D2298 )
  {
    v4 = _bstr_t::_bstr_t((_bstr_t *)v34, off_1400CB2F8);
    v5 = (BSTR *)operator new(0x18u);
    v32 = v5;
    v5[1] = 0;
    *((_DWORD *)v5 + 4) = 1;
    v6 = SysAllocString(L"KnownFolder");
    *v5 = v6;
    if ( !v6 )
      _com_issue_error(-2147024882);
    v32 = v5;
    v7 = _bstr_t::operator+(v4, &v35, &v32);
    v33 = 1;
    v8 = (_bstr_t *)std::map<enum Uev::NormalizationRootType,_bstr_t>::operator[](
                      &`Uev::FileRoot::Parse<1>'::`2'::rootStringTypes,
                      &v33);
    v9 = v8;
    if ( *(_QWORD *)v7 )
      _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)v7 + 16LL), 1u);
    _bstr_t::_Free(v8);
    *(_QWORD *)v9 = *(_QWORD *)v7;
    _bstr_t::_Free((_bstr_t *)&v35);
    _bstr_t::_Free((_bstr_t *)&v32);
    _bstr_t::_Free((_bstr_t *)v34);
    v10 = _bstr_t::_bstr_t((_bstr_t *)&v35, off_1400CB2F8);
    v11 = (BSTR *)operator new(0x18u);
    v32 = v11;
    v11[1] = 0;
    *((_DWORD *)v11 + 4) = 1;
    v12 = SysAllocString(L"RegistryEntry");
    *v11 = v12;
    if ( !v12 )
      _com_issue_error(-2147024882);
    v32 = v11;
    v13 = _bstr_t::operator+(v10, v34, &v32);
    v33 = 2;
    v14 = (_bstr_t *)std::map<enum Uev::NormalizationRootType,_bstr_t>::operator[](
                       &`Uev::FileRoot::Parse<1>'::`2'::rootStringTypes,
                       &v33);
    v15 = v14;
    if ( *(_QWORD *)v13 )
      _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)v13 + 16LL), 1u);
    _bstr_t::_Free(v14);
    *(_QWORD *)v15 = *(_QWORD *)v13;
    _bstr_t::_Free((_bstr_t *)v34);
    _bstr_t::_Free((_bstr_t *)&v32);
    _bstr_t::_Free((_bstr_t *)&v35);
    v16 = _bstr_t::_bstr_t((_bstr_t *)&v35, off_1400CB2F8);
    v17 = (BSTR *)operator new(0x18u);
    v32 = v17;
    v17[1] = 0;
    *((_DWORD *)v17 + 4) = 1;
    v18 = SysAllocString(L"EnvironmentVariable");
    *v17 = v18;
    if ( !v18 )
      _com_issue_error(-2147024882);
    v32 = v17;
    v19 = _bstr_t::operator+(v16, v34, &v32);
    v33 = 0;
    v20 = (_bstr_t *)std::map<enum Uev::NormalizationRootType,_bstr_t>::operator[](
                       &`Uev::FileRoot::Parse<1>'::`2'::rootStringTypes,
                       &v33);
    v21 = v20;
    if ( *(_QWORD *)v19 )
      _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)v19 + 16LL), 1u);
    _bstr_t::_Free(v20);
    *(_QWORD *)v21 = *(_QWORD *)v19;
    _bstr_t::_Free((_bstr_t *)v34);
    _bstr_t::_Free((_bstr_t *)&v32);
    _bstr_t::_Free((_bstr_t *)&v35);
  }
  v22 = *(__int64 **)`Uev::FileRoot::Parse<1>'::`2'::rootStringTypes;
  while ( !*((_BYTE *)v22 + 25) )
  {
    v23 = *((_DWORD *)v22 + 8);
    v35 = v23;
    v24 = (volatile signed __int32 *)v22[5];
    v36[0] = v24;
    if ( v24 )
    {
      _InterlockedIncrement(v24 + 4);
      v25 = *(_QWORD *)v24;
    }
    else
    {
      v25 = 0;
    }
    v26 = *a2;
    v32 = v26;
    if ( v26 )
      (*((void (__fastcall **)(BSTR *))*v26 + 1))(v26);
    v27 = ((__int64 (__fastcall *)(_BYTE *, BSTR **, __int64, _QWORD))Uev::DomHelper::GetNodeText)(v37, &v32, v25, 0);
    if ( a1 + 8 != v27 )
    {
      std::wstring::_Tidy_deallocate(a1 + 8);
      *(_OWORD *)(a1 + 8) = *(_OWORD *)v27;
      *(_OWORD *)(a1 + 24) = *(_OWORD *)(v27 + 16);
      *(_QWORD *)(v27 + 16) = 0;
      *(_QWORD *)(v27 + 24) = 7;
      *(_WORD *)v27 = 0;
    }
    std::wstring::_Tidy_deallocate(v37);
    if ( *(_QWORD *)(a1 + 24) )
    {
      *(_DWORD *)a1 = v23;
      _bstr_t::_Free((_bstr_t *)v36);
      break;
    }
    _bstr_t::_Free((_bstr_t *)v36);
    v28 = (__int64 **)v22[2];
    if ( *((_BYTE *)v28 + 25) )
    {
      for ( i = (__int64 *)v22[1]; !*((_BYTE *)i + 25) && v22 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v22 = i;
      v22 = i;
    }
    else
    {
      v22 = (__int64 *)v22[2];
      for ( j = *v28; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v22 = j;
    }
  }
  if ( !*(_QWORD *)(a1 + 24) )
  {
    std::string::string(v37, "Unknown file root type.");
    Uev::UevException::UevException(pExceptionObject, v37);
    throw (Uev::UevException *)pExceptionObject;
  }
  if ( *a2 )
    (*((void (__fastcall **)(BSTR *))**a2 + 2))(*a2);
}

```

## disassembly

```asm
0x140048f30  mov     [rsp-8+arg_10], rbx
0x140048f35  push    rbp
0x140048f36  push    rsi
0x140048f37  push    rdi
0x140048f38  push    r12
0x140048f3a  push    r13
0x140048f3c  push    r14
0x140048f3e  push    r15
0x140048f40  lea     rbp, [rsp-27h]
0x140048f45  sub     rsp, 0B0h
0x140048f4c  mov     r13, rdx
0x140048f4f  mov     rdi, rcx
0x140048f52  mov     [rbp+57h+var_98], rdx
0x140048f56  mov     ecx, 4
0x140048f5b  mov     rax, gs:58h
0x140048f64  mov     rax, [rax]
0x140048f67  xor     r15d, r15d
0x140048f6a  lea     r12d, [r15+1]
0x140048f6e  mov     eax, [rcx+rax]
0x140048f71  cmp     cs:?$TSS0@?1???$Parse@$00@FileRoot@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z@4HA, eax
0x140048f77  jg      loc_14004930A
0x140048f7d  mov     r14d, 18h
0x140048f83  cmp     cs:qword_1400D2298, r15
0x140048f8a  jnz     loc_14004918E
0x140048f90  mov     rdx, cs:off_1400CB2F8; wchar_t *
0x140048f97  lea     rcx, [rbp+57h+var_B0]; this
0x140048f9b  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x140048fa0  mov     rsi, rax
0x140048fa3  mov     ecx, r14d; Size
0x140048fa6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140048fab  mov     rbx, rax
0x140048fae  mov     [rbp+57h+var_C0], rax
0x140048fb2  mov     [rax+8], r15
0x140048fb6  mov     [rax+10h], r12d
0x140048fba  lea     rcx, aKnownfolder; "KnownFolder"
0x140048fc1  call    cs:__imp_SysAllocString
0x140048fc7  mov     [rbx], rax
0x140048fca  test    rax, rax
0x140048fcd  jz      loc_140049371
0x140048fd3  mov     [rbp+57h+var_C0], rbx
0x140048fd7  lea     r8, [rbp+57h+var_C0]
0x140048fdb  lea     rdx, [rbp+57h+var_A8]
0x140048fdf  mov     rcx, rsi
0x140048fe2  call    ??H_bstr_t@@QEBA?AV0@AEBV0@@Z; _bstr_t::operator+(_bstr_t const &)
0x140048fe7  mov     rbx, rax
0x140048fea  mov     [rbp+57h+var_B8], r12d
0x140048fee  lea     rdx, [rbp+57h+var_B8]
0x140048ff2  lea     rcx, ?rootStringTypes@?1???$Parse@$00@FileRoot@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z@4V?$map@W4NormalizationRootType@Uev@@V_bstr_t@@U?$less@W4NormalizationRootType@Uev@@@std@@V?$allocator@U?$pair@$$CBW4NormalizationRootType@Uev@@V_bstr_t@@@std@@@5@@std@@A; std::map<Uev::NormalizationRootType,_bstr_t> `Uev::FileRoot::Parse<1>(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>)'::`2'::rootStringTypes
0x140048ff9  call    ??A?$map@W4NormalizationRootType@Uev@@V_bstr_t@@U?$less@W4NormalizationRootType@Uev@@@std@@V?$allocator@U?$pair@$$CBW4NormalizationRootType@Uev@@V_bstr_t@@@std@@@5@@std@@QEAAAEAV_bstr_t@@$$QEAW4NormalizationRootType@Uev@@@Z; std::map<Uev::NormalizationRootType,_bstr_t>::operator[](Uev::NormalizationRootType &&)
0x140048ffe  mov     rsi, rax
0x140049001  mov     rcx, [rbx]
0x140049004  test    rcx, rcx
0x140049007  jz      short loc_14004900E
0x140049009  lock add [rcx+10h], r12d
0x14004900e  mov     rcx, rsi; this
0x140049011  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x140049016  mov     rcx, [rbx]
0x140049019  mov     [rsi], rcx
0x14004901c  lea     rcx, [rbp+57h+var_A8]; this
0x140049020  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x140049025  nop
0x140049026  lea     rcx, [rbp+57h+var_C0]; this
0x14004902a  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x14004902f  nop
0x140049030  lea     rcx, [rbp+57h+var_B0]; this
0x140049034  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x140049039  mov     rdx, cs:off_1400CB2F8; wchar_t *
0x140049040  lea     rcx, [rbp+57h+var_A8]; this
0x140049044  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x140049049  mov     rsi, rax
0x14004904c  mov     rcx, r14; Size
0x14004904f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140049054  mov     rbx, rax
0x140049057  mov     [rbp+57h+var_C0], rax
0x14004905b  mov     [rax+8], r15
0x14004905f  mov     [rax+10h], r12d
0x140049063  lea     rcx, aRegistryentry; "RegistryEntry"
0x14004906a  call    cs:__imp_SysAllocString
0x140049070  mov     [rbx], rax
0x140049073  test    rax, rax
0x140049076  jz      loc_14004937C
0x14004907c  mov     [rbp+57h+var_C0], rbx
0x140049080  lea     r8, [rbp+57h+var_C0]
0x140049084  lea     rdx, [rbp+57h+var_B0]
0x140049088  mov     rcx, rsi
0x14004908b  call    ??H_bstr_t@@QEBA?AV0@AEBV0@@Z; _bstr_t::operator+(_bstr_t const &)
0x140049090  mov     rbx, rax
0x140049093  mov     [rbp+57h+var_B8], 2
0x14004909a  lea     rdx, [rbp+57h+var_B8]
0x14004909e  lea     rcx, ?rootStringTypes@?1???$Parse@$00@FileRoot@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z@4V?$map@W4NormalizationRootType@Uev@@V_bstr_t@@U?$less@W4NormalizationRootType@Uev@@@std@@V?$allocator@U?$pair@$$CBW4NormalizationRootType@Uev@@V_bstr_t@@@std@@@5@@std@@A; std::map<Uev::NormalizationRootType,_bstr_t> `Uev::FileRoot::Parse<1>(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>)'::`2'::rootStringTypes
0x1400490a5  call    ??A?$map@W4NormalizationRootType@Uev@@V_bstr_t@@U?$less@W4NormalizationRootType@Uev@@@std@@V?$allocator@U?$pair@$$CBW4NormalizationRootType@Uev@@V_bstr_t@@@std@@@5@@std@@QEAAAEAV_bstr_t@@$$QEAW4NormalizationRootType@Uev@@@Z; std::map<Uev::NormalizationRootType,_bstr_t>::operator[](Uev::NormalizationRootType &&)
0x1400490aa  mov     rsi, rax
0x1400490ad  mov     rcx, [rbx]
0x1400490b0  test    rcx, rcx
0x1400490b3  jz      short loc_1400490BA
0x1400490b5  lock add [rcx+10h], r12d
0x1400490ba  mov     rcx, rsi; this
0x1400490bd  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1400490c2  mov     rcx, [rbx]
0x1400490c5  mov     [rsi], rcx
0x1400490c8  lea     rcx, [rbp+57h+var_B0]; this
0x1400490cc  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1400490d1  nop
0x1400490d2  lea     rcx, [rbp+57h+var_C0]; this
0x1400490d6  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1400490db  nop
0x1400490dc  lea     rcx, [rbp+57h+var_A8]; this
0x1400490e0  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1400490e5  mov     rdx, cs:off_1400CB2F8; wchar_t *
0x1400490ec  lea     rcx, [rbp+57h+var_A8]; this
0x1400490f0  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x1400490f5  mov     rsi, rax
0x1400490f8  mov     rcx, r14; Size
0x1400490fb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140049100  mov     rbx, rax
0x140049103  mov     [rbp+57h+var_C0], rax
0x140049107  mov     [rax+8], r15
0x14004910b  mov     [rax+10h], r12d
0x14004910f  lea     rcx, aEnvironmentvar; "EnvironmentVariable"
0x140049116  call    cs:__imp_SysAllocString
0x14004911c  mov     [rbx], rax
0x14004911f  test    rax, rax
0x140049122  jz      loc_140049387
0x140049128  mov     [rbp+57h+var_C0], rbx
0x14004912c  lea     r8, [rbp+57h+var_C0]
0x140049130  lea     rdx, [rbp+57h+var_B0]
0x140049134  mov     rcx, rsi
0x140049137  call    ??H_bstr_t@@QEBA?AV0@AEBV0@@Z; _bstr_t::operator+(_bstr_t const &)
0x14004913c  mov     rsi, rax
0x14004913f  mov     [rbp+57h+var_B8], r15d
0x140049143  lea     rdx, [rbp+57h+var_B8]
0x140049147  lea     rcx, ?rootStringTypes@?1???$Parse@$00@FileRoot@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z@4V?$map@W4NormalizationRootType@Uev@@V_bstr_t@@U?$less@W4NormalizationRootType@Uev@@@std@@V?$allocator@U?$pair@$$CBW4NormalizationRootType@Uev@@V_bstr_t@@@std@@@5@@std@@A; std::map<Uev::NormalizationRootType,_bstr_t> `Uev::FileRoot::Parse<1>(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>)'::`2'::rootStringTypes
0x14004914e  call    ??A?$map@W4NormalizationRootType@Uev@@V_bstr_t@@U?$less@W4NormalizationRootType@Uev@@@std@@V?$allocator@U?$pair@$$CBW4NormalizationRootType@Uev@@V_bstr_t@@@std@@@5@@std@@QEAAAEAV_bstr_t@@$$QEAW4NormalizationRootType@Uev@@@Z; std::map<Uev::NormalizationRootType,_bstr_t>::operator[](Uev::NormalizationRootType &&)
0x140049153  mov     rbx, rax
0x140049156  mov     rcx, [rsi]
0x140049159  test    rcx, rcx
0x14004915c  jz      short loc_140049163
0x14004915e  lock add [rcx+10h], r12d
0x140049163  mov     rcx, rbx; this
0x140049166  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x14004916b  mov     rcx, [rsi]
0x14004916e  mov     [rbx], rcx
0x140049171  lea     rcx, [rbp+57h+var_B0]; this
0x140049175  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x14004917a  nop
0x14004917b  lea     rcx, [rbp+57h+var_C0]; this
0x14004917f  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x140049184  nop
0x140049185  lea     rcx, [rbp+57h+var_A8]; this
0x140049189  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x14004918e  mov     rbx, cs:?rootStringTypes@?1???$Parse@$00@FileRoot@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z@4V?$map@W4NormalizationRootType@Uev@@V_bstr_t@@U?$less@W4NormalizationRootType@Uev@@@std@@V?$allocator@U?$pair@$$CBW4NormalizationRootType@Uev@@V_bstr_t@@@std@@@5@@std@@A; std::map<Uev::NormalizationRootType,_bstr_t> `Uev::FileRoot::Parse<1>(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>)'::`2'::rootStringTypes
0x140049195  mov     rbx, [rbx]
0x140049198  cmp     [rbx+19h], r15b
0x14004919c  jnz     loc_1400492A4
0x1400491a2  mov     r12d, [rbx+20h]
0x1400491a6  mov     [rbp+57h+var_A8], r12d
0x1400491aa  mov     rax, [rbx+28h]
0x1400491ae  mov     [rbp+57h+var_A0], rax
0x1400491b2  test    rax, rax
0x1400491b5  jz      short loc_1400491BB
0x1400491b7  lock inc dword ptr [rax+10h]
0x1400491bb  test    rax, rax
0x1400491be  jz      short loc_1400491C5
0x1400491c0  mov     rsi, [rax]
0x1400491c3  jmp     short loc_1400491C8
0x1400491c5  mov     rsi, r15
0x1400491c8  mov     rcx, [r13+0]
0x1400491cc  mov     [rbp+57h+var_C0], rcx
0x1400491d0  test    rcx, rcx
0x1400491d3  jz      short loc_1400491E2
0x1400491d5  mov     rax, [rcx]
0x1400491d8  mov     rax, [rax+8]
0x1400491dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400491e1  nop
0x1400491e2  xor     r9d, r9d
0x1400491e5  mov     r8, rsi
0x1400491e8  lea     rdx, [rbp+57h+var_C0]
0x1400491ec  lea     rcx, [rbp+57h+var_90]
0x1400491f0  call    ?GetNodeText@DomHelper@Uev@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@PEA_W_N@Z; Uev::DomHelper::GetNodeText(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>,wchar_t *,bool)
0x1400491f5  mov     rsi, rax
0x1400491f8  lea     r15, [rdi+8]
0x1400491fc  cmp     r15, rax
0x1400491ff  jz      short loc_14004922E
0x140049201  mov     rcx, r15
0x140049204  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140049209  movups  xmm0, xmmword ptr [rsi]
0x14004920c  movups  xmmword ptr [r15], xmm0
0x140049210  movups  xmm1, xmmword ptr [rsi+10h]
0x140049214  movups  xmmword ptr [r15+10h], xmm1
0x140049219  xor     r15d, r15d
0x14004921c  mov     [rsi+10h], r15
0x140049220  mov     qword ptr [rsi+18h], 7
0x140049228  mov     [rsi], r15w
0x14004922c  jmp     short loc_140049231
0x14004922e  xor     r15d, r15d
0x140049231  lea     rcx, [rbp+57h+var_90]
0x140049235  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14004923a  cmp     [rdi+18h], r15
0x14004923e  jnz     short loc_140049298
0x140049240  lea     rcx, [rbp+57h+var_A0]; this
0x140049244  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x140049249  mov     rcx, [rbx+10h]
0x14004924d  cmp     [rcx+19h], r15b
0x140049251  jz      short loc_140049274
0x140049253  mov     rax, [rbx+8]
0x140049257  jmp     short loc_140049266
0x140049259  cmp     rbx, [rax+10h]
0x14004925d  jnz     short loc_14004926C
0x14004925f  mov     rbx, rax
0x140049262  mov     rax, [rax+8]
0x140049266  cmp     [rax+19h], r15b
0x14004926a  jz      short loc_140049259
0x14004926c  mov     rbx, rax
0x14004926f  jmp     loc_140049198
0x140049274  mov     rbx, rcx
0x140049277  mov     rcx, [rcx]
0x14004927a  cmp     [rcx+19h], r15b
0x14004927e  jnz     loc_140049198
0x140049284  mov     rbx, rcx
0x140049287  mov     rax, [rcx]
0x14004928a  mov     rcx, rax
0x14004928d  cmp     [rax+19h], r15b
0x140049291  jz      short loc_140049284
0x140049293  jmp     loc_140049198
0x140049298  mov     [rdi], r12d
0x14004929b  lea     rcx, [rbp+57h+var_A0]; this
0x14004929f  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1400492a4  cmp     [r14+rdi], r15
0x1400492a8  jz      short loc_1400492DB
0x1400492aa  mov     rcx, [r13+0]
0x1400492ae  test    rcx, rcx
0x1400492b1  jz      short loc_1400492C0
0x1400492b3  mov     rax, [rcx]
0x1400492b6  mov     rax, [rax+10h]
0x1400492ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400492bf  nop
0x1400492c0  mov     rbx, [rsp+0E0h+arg_10]
0x1400492c8  add     rsp, 0B0h
0x1400492cf  pop     r15
0x1400492d1  pop     r14
0x1400492d3  pop     r13
0x1400492d5  pop     r12
0x1400492d7  pop     rdi
0x1400492d8  pop     rsi
0x1400492d9  pop     rbp
0x1400492da  retn
0x1400492db  lea     rdx, aUnknownFileRoo; "Unknown file root type."
0x1400492e2  lea     rcx, [rbp+57h+var_90]
0x1400492e6  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400492eb  nop
0x1400492ec  lea     rdx, [rbp+57h+var_90]
0x1400492f0  lea     rcx, [rbp+57h+pExceptionObject]
0x1400492f4  call    ??0UevException@Uev@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Uev::UevException::UevException(std::string const &)
0x1400492f9  lea     rdx, _TI2?AVUevException@Uev@@; pThrowInfo
0x140049300  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140049304  call    _CxxThrowException_0
0x14004930a  lea     rcx, ?$TSS0@?1???$Parse@$00@FileRoot@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z@4HA
0x140049311  call    _Init_thread_header
0x140049316  cmp     cs:?$TSS0@?1???$Parse@$00@FileRoot@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z@4HA, 0FFFFFFFFh
0x14004931d  jnz     loc_140048F7D
0x140049323  mov     cs:?rootStringTypes@?1???$Parse@$00@FileRoot@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z@4V?$map@W4NormalizationRootType@Uev@@V_bstr_t@@U?$less@W4NormalizationRootType@Uev@@@std@@V?$allocator@U?$pair@$$CBW4NormalizationRootType@Uev@@V_bstr_t@@@std@@@5@@std@@A, r15; std::map<Uev::NormalizationRootType,_bstr_t> `Uev::FileRoot::Parse<1>(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>)'::`2'::rootStringTypes
0x14004932a  mov     cs:qword_1400D2298, r15
0x140049331  mov     ecx, 30h ; '0'; Size
0x140049336  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14004933b  mov     [rax], rax
0x14004933e  mov     [rax+8], rax
0x140049342  mov     [rax+10h], rax
0x140049346  mov     word ptr [rax+18h], 101h
0x14004934c  mov     cs:?rootStringTypes@?1???$Parse@$00@FileRoot@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z@4V?$map@W4NormalizationRootType@Uev@@V_bstr_t@@U?$less@W4NormalizationRootType@Uev@@@std@@V?$allocator@U?$pair@$$CBW4NormalizationRootType@Uev@@V_bstr_t@@@std@@@5@@std@@A, rax; std::map<Uev::NormalizationRootType,_bstr_t> `Uev::FileRoot::Parse<1>(_com_ptr_t<_com_IIID<IXMLDOMNode,&__s_GUID const _GUID_2933bf80_7b36_11d2_b20e_00c04f983e60>>)'::`2'::rootStringTypes
0x140049353  lea     rcx, ??__FrootStringTypes@?1???$Parse@$00@FileRoot@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z@YAXXZ; void (__cdecl *)()
0x14004935a  call    atexit
0x14004935f  nop
0x140049360  lea     rcx, ?$TSS0@?1???$Parse@$00@FileRoot@Uev@@QEAAXV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMNode@@$1?_GUID_2933bf80_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z@4HA
0x140049367  call    _Init_thread_footer
0x14004936c  jmp     loc_140048F7D
0x140049371  mov     ecx, 8007000Eh; int
0x140049376  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x14004937c  mov     ecx, 8007000Eh; int
0x140049381  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x140049387  mov     ecx, 8007000Eh; int
0x14004938c  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
