# FilterDS::FilterSingleCandidate(IMtfSuggestionCandidate *,ushort *,int &,int &)

- ea: `0x180009890`
- end: `0x180009d24`
- name: `?FilterSingleCandidate@FilterDS@@IEAAXPEAUIMtfSuggestionCandidate@@PEAGAEAH2@Z`
- size: `1172`
- prototype: `void __fastcall(FilterDS *__hidden this, struct IMtfSuggestionCandidate *, unsigned __int16 *, int *, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000a000`

## callees

- `0x18000783c`
- `0x180008618`
- `0x180009890`
- `0x18000cc9c`
- `0x18000cd18`
- `0x18000dd08`
- `0x18000e21c`
- `0x180024010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180009bbc`
- `OLEAUT32!__imp_SysFreeString` at `0x180009bf4`
- `OLEAUT32!__imp_SysFreeString` at `0x180009c06`
- `OLEAUT32!__imp_SysFreeString` at `0x180009bbc`
- `OLEAUT32!__imp_SysFreeString` at `0x180009bf4`
- `OLEAUT32!__imp_SysFreeString` at `0x180009c06`
- `OLEAUT32!__imp_SysStringLen` at `0x1800099c8`
- `OLEAUT32!__imp_SysStringLen` at `0x1800099c8`

## string_xrefs

- `0x180009cbe`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
void __fastcall FilterDS::FilterSingleCandidate(
        FilterDS *this,
        struct IMtfSuggestionCandidate *a2,
        unsigned __int16 *a3,
        int *a4,
        int *a5)
{
  int *v5; // r15
  unsigned __int16 *v6; // rsi
  FilterDS *v8; // r12
  __int64 *v9; // r14
  int v10; // eax
  unsigned int v11; // ecx
  __int64 *v12; // rbx
  __int64 *v13; // rdi
  __int64 v14; // rax
  int v15; // eax
  int v16; // eax
  __int64 *v17; // rcx
  __int64 v18; // rax
  int v19; // eax
  __int64 (__fastcall ***v20)(_QWORD, GUID *, _QWORD *); // rsi
  int v21; // eax
  __int64 v22; // rax
  __int64 v23; // rsi
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rsi
  int v27; // r15d
  __int64 v28; // r12
  __int64 v29; // rcx
  bool v30; // zf
  int v31; // eax
  int v32; // eax
  int v33; // [rsp+28h] [rbp-A1h]
  char v34[8]; // [rsp+48h] [rbp-81h] BYREF
  __int64 v35; // [rsp+50h] [rbp-79h] BYREF
  unsigned int v36; // [rsp+58h] [rbp-71h] BYREF
  BSTR pbstr; // [rsp+60h] [rbp-69h] BYREF
  __int128 v38; // [rsp+68h] [rbp-61h] BYREF
  __int64 *v39; // [rsp+78h] [rbp-51h]
  unsigned int v40; // [rsp+80h] [rbp-49h]
  __int64 (__fastcall ***v41)(_QWORD, GUID *, __int64 *); // [rsp+88h] [rbp-41h] BYREF
  __int64 v42; // [rsp+90h] [rbp-39h] BYREF
  __int128 v43; // [rsp+98h] [rbp-31h] BYREF
  __int128 v44; // [rsp+A8h] [rbp-21h]
  __int128 v45; // [rsp+B8h] [rbp-11h]
  __int64 v46; // [rsp+C8h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+120h] [rbp+57h]
  __int64 v49; // [rsp+130h] [rbp+67h] BYREF
  unsigned __int16 *v50; // [rsp+138h] [rbp+6Fh]
  int *v51; // [rsp+140h] [rbp+77h]

  v51 = a4;
  v50 = a3;
  v5 = a4;
  v6 = a3;
  v8 = this;
  v38 = 0;
  v9 = 0;
  v39 = 0;
  v36 = 0;
  v10 = (*(__int64 (__fastcall **)(struct IMtfSuggestionCandidate *, unsigned int *))(*(_QWORD *)a2 + 56LL))(a2, &v36);
  if ( v10 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xCB,
      (int)"mincore\\textinput\\dev\\mtf\\datasources\\filterds\\lib\\filterds.cpp",
      (const char *)(unsigned int)v10,
      v33);
  LOBYTE(v49) = 0;
  v11 = 0;
  v40 = 0;
  if ( v36 )
  {
    v12 = (__int64 *)*((_QWORD *)&v38 + 1);
    v13 = (__int64 *)v38;
    while ( 1 )
    {
      v14 = *(_QWORD *)a2;
      v35 = 0;
      v15 = (*(__int64 (__fastcall **)(struct IMtfSuggestionCandidate *, _QWORD, __int64 *))(v14 + 64))(a2, v11, &v35);
      if ( v15 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0xD0,
          (int)"mincore\\textinput\\dev\\mtf\\datasources\\filterds\\lib\\filterds.cpp",
          (const char *)(unsigned int)v15,
          v33);
      v43 = 0;
      v44 = 0;
      v45 = 0;
      v46 = 0;
      LODWORD(v43) = 3;
      v16 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v35 + 40LL))(v35, &v43);
      if ( v16 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0xD4,
          (int)"mincore\\textinput\\dev\\mtf\\datasources\\filterds\\lib\\filterds.cpp",
          (const char *)(unsigned int)v16,
          v33);
      pbstr = 0;
      v17 = (__int64 *)*((_QWORD *)v8 + 5);
      v18 = *v17;
      pbstr = 0;
      v33 = 0;
      (*(void (__fastcall **)(__int64 *, unsigned __int16 *, _QWORD, _QWORD))(v18 + 8))(
        v17,
        v6,
        v44,
        *((_QWORD *)&v43 + 1));
      if ( !pbstr || *a5 )
      {
        if ( &v35 >= v12 || v13 > &v35 )
        {
          if ( v12 == v9 )
          {
            std::vector<wil::com_ptr_t<IMtfSuggestionCandidatePrimitive,wil::err_exception_policy>>::_Reserve(&v38);
            v9 = v39;
            v12 = (__int64 *)*((_QWORD *)&v38 + 1);
            v13 = (__int64 *)v38;
          }
          v25 = v35;
          *v12 = v35;
          if ( v25 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 8LL))(v25);
        }
        else
        {
          v23 = &v35 - v13;
          if ( v12 == v9 )
          {
            std::vector<wil::com_ptr_t<IMtfSuggestionCandidatePrimitive,wil::err_exception_policy>>::_Reserve(&v38);
            v9 = v39;
            v12 = (__int64 *)*((_QWORD *)&v38 + 1);
            v13 = (__int64 *)v38;
          }
          v24 = v13[v23];
          *v12 = v24;
          if ( v24 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 8LL))(v24);
        }
        *((_QWORD *)&v38 + 1) = ++v12;
      }
      else if ( SysStringLen(pbstr) )
      {
        v49 = v35;
        v41 = 0;
        v19 = Microsoft::WRL::Details::MakeAndInitialize<PrimitiveDisplayOverride,PrimitiveDisplayOverride,IMtfSuggestionCandidatePrimitive *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                &v41,
                &v49,
                &pbstr);
        if ( v19 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0xE4,
            (int)"mincore\\textinput\\dev\\mtf\\datasources\\filterds\\lib\\filterds.cpp",
            (const char *)(unsigned int)v19,
            0);
        v20 = v41;
        v49 = 0;
        v21 = (**v41)(v41, &GUID_92445657_1419_4aaa_a92f_486ab29470c0, &v49);
        if ( v21 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x1CBE,
            (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
            (const char *)(unsigned int)v21,
            0);
        if ( v12 == v9 )
        {
          std::vector<wil::com_ptr_t<IMtfSuggestionCandidatePrimitive,wil::err_exception_policy>>::_Reserve(&v38);
          v9 = v39;
          v12 = (__int64 *)*((_QWORD *)&v38 + 1);
          v13 = (__int64 *)v38;
        }
        v22 = v49;
        v49 = 0;
        *v12++ = v22;
        *((_QWORD *)&v38 + 1) = v12;
        if ( v49 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
        LOBYTE(v49) = 1;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v20)[2])(v20);
      }
      else
      {
        *v5 = 1;
      }
      if ( *v5 == 1 )
        break;
      v26 = *((_QWORD *)v8 + 5);
      v27 = DWORD2(v43);
      v28 = v44;
      *v51 = 0;
      v41 = 0;
      v34[0] = 2;
      std::_Hash<std::_Umap_traits<enum FilterType,std::unique_ptr<std::vector<std::unique_ptr<FilterAgent>>>,std::_Uhash_compare<enum FilterType,std::hash<enum FilterType>,std::equal_to<enum FilterType>>,std::allocator<std::pair<enum FilterType const,std::unique_ptr<std::vector<std::unique_ptr<FilterAgent>>>>>,0>>::find(
        v26 + 16,
        &v42,
        v34);
      v30 = v42 == *(_QWORD *)(v26 + 16);
      v6 = v50;
      if ( !v30 )
      {
        v33 = v27;
        FilterManager::GetReplaceByType(v29, v42 + 24, v50, v28);
      }
      v5 = v51;
      if ( *v51 == 1 )
      {
        if ( pbstr )
          SysFreeString(pbstr);
        goto LABEL_44;
      }
      if ( pbstr )
        SysFreeString(pbstr);
      if ( v35 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
      v11 = v40 + 1;
      v40 = v11;
      if ( v11 >= v36 )
        goto LABEL_46;
      v8 = this;
    }
    if ( pbstr )
      SysFreeString(pbstr);
LABEL_44:
    if ( v35 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
LABEL_46:
    if ( (_BYTE)v49 && v13 != v12 )
    {
      v31 = (*(__int64 (__fastcall **)(struct IMtfSuggestionCandidate *))(*(_QWORD *)a2 + 80LL))(a2);
      if ( v31 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x68,
          (int)"mincore\\textinput\\dev\\mtf\\datasources\\filterds\\lib\\filterds.cpp",
          (const char *)(unsigned int)v31,
          v33);
      while ( v13 != v12 )
      {
        v32 = (*(__int64 (__fastcall **)(struct IMtfSuggestionCandidate *, __int64))(*(_QWORD *)a2 + 72LL))(a2, *v13);
        if ( v32 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x6C,
            (int)"mincore\\textinput\\dev\\mtf\\datasources\\filterds\\lib\\filterds.cpp",
            (const char *)(unsigned int)v32,
            v33);
        ++v13;
      }
    }
  }
  std::vector<wil::com_ptr_t<IMtfSuggestionCandidatePrimitive,wil::err_exception_policy>>::~vector<wil::com_ptr_t<IMtfSuggestionCandidatePrimitive,wil::err_exception_policy>>((__int64)&v38);
}

```

## disassembly

```asm
0x180009890  mov     rax, rsp
0x180009893  mov     [rax+20h], r9
0x180009897  mov     [rax+18h], r8
0x18000989b  mov     [rax+8], rcx
0x18000989f  push    rbp
0x1800098a0  push    rbx
0x1800098a1  push    rsi
0x1800098a2  push    rdi
0x1800098a3  push    r12
0x1800098a5  push    r13
0x1800098a7  push    r14
0x1800098a9  push    r15
0x1800098ab  lea     rbp, [rax-57h]
0x1800098af  sub     rsp, 0D8h
0x1800098b6  mov     r15, r9
0x1800098b9  mov     rsi, r8
0x1800098bc  mov     r13, rdx
0x1800098bf  mov     r12, rcx
0x1800098c2  xor     ebx, ebx
0x1800098c4  xorps   xmm0, xmm0
0x1800098c7  movdqu  [rbp+4Fh+var_B0], xmm0
0x1800098cc  mov     r14d, ebx
0x1800098cf  mov     [rbp+4Fh+var_A0], rbx
0x1800098d3  mov     [rbp+4Fh+var_C0], ebx
0x1800098d6  mov     rax, [rdx]
0x1800098d9  lea     rdx, [rbp+4Fh+var_C0]
0x1800098dd  mov     rcx, r13
0x1800098e0  mov     rax, [rax+38h]
0x1800098e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098e9  mov     rcx, [rbp+57h]; this
0x1800098ed  test    eax, eax
0x1800098ef  js      loc_180009CA6
0x1800098f5  mov     byte ptr [rbp+4Fh+arg_8], bl
0x1800098f8  mov     ecx, ebx
0x1800098fa  mov     [rbp+4Fh+var_98], ebx
0x1800098fd  cmp     [rbp+4Fh+var_C0], ebx
0x180009900  jbe     loc_180009C74
0x180009906  mov     rbx, qword ptr [rbp+4Fh+var_B0+8]
0x18000990a  mov     rdi, qword ptr [rbp+4Fh+var_B0]
0x18000990e  mov     rax, [r13+0]
0x180009912  mov     [rbp+4Fh+var_C8], 0
0x18000991a  lea     r8, [rbp+4Fh+var_C8]
0x18000991e  mov     edx, ecx
0x180009920  mov     rcx, r13
0x180009923  mov     rax, [rax+40h]
0x180009927  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000992c  mov     rcx, [rbp+57h]; this
0x180009930  test    eax, eax
0x180009932  js      loc_180009C91
0x180009938  xorps   xmm0, xmm0
0x18000993b  xor     eax, eax
0x18000993d  movups  [rbp+4Fh+var_80], xmm0
0x180009941  movups  [rbp+4Fh+var_70], xmm0
0x180009945  movups  [rbp+4Fh+var_60], xmm0
0x180009949  mov     [rbp+4Fh+var_50], rax
0x18000994d  mov     dword ptr [rbp+4Fh+var_80], 3
0x180009954  mov     rcx, [rbp+4Fh+var_C8]
0x180009958  mov     rax, [rcx]
0x18000995b  lea     rdx, [rbp+4Fh+var_80]
0x18000995f  mov     rax, [rax+28h]
0x180009963  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009968  mov     rcx, [rbp+57h]; this
0x18000996c  xor     r8d, r8d
0x18000996f  test    eax, eax
0x180009971  js      loc_180009D0F
0x180009977  mov     [rbp+4Fh+pbstr], r8
0x18000997b  mov     rcx, [r12+28h]
0x180009980  mov     rax, [rcx]
0x180009983  mov     [rbp+4Fh+pbstr], r8
0x180009987  lea     rdx, [rbp+4Fh+pbstr]
0x18000998b  mov     [rsp+110h+var_E0], rdx
0x180009990  mov     [rsp+110h+var_E8], r15
0x180009995  mov     [rsp+110h+var_F0], r8d; int
0x18000999a  mov     r9, qword ptr [rbp+4Fh+var_80+8]
0x18000999e  mov     r8, qword ptr [rbp+4Fh+var_70]
0x1800099a2  mov     rdx, rsi
0x1800099a5  mov     rax, [rax+8]
0x1800099a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099ae  mov     rcx, [rbp+4Fh+pbstr]; pbstr
0x1800099b2  test    rcx, rcx
0x1800099b5  jz      loc_180009AA0
0x1800099bb  mov     rax, [rbp+4Fh+arg_20]
0x1800099bf  cmp     dword ptr [rax], 0
0x1800099c2  jnz     loc_180009AA0
0x1800099c8  call    cs:__imp_SysStringLen
0x1800099ce  test    eax, eax
0x1800099d0  jz      loc_180009A94
0x1800099d6  mov     rax, [rbp+4Fh+var_C8]
0x1800099da  mov     [rbp+4Fh+arg_8], rax
0x1800099de  mov     [rbp+4Fh+var_90], 0
0x1800099e6  lea     r8, [rbp+4Fh+pbstr]
0x1800099ea  lea     rdx, [rbp+4Fh+arg_8]
0x1800099ee  lea     rcx, [rbp+4Fh+var_90]
0x1800099f2  call    ??$MakeAndInitialize@VPrimitiveDisplayOverride@@V1@PEAUIMtfSuggestionCandidatePrimitive@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Details@WRL@Microsoft@@YAJPEAPEAVPrimitiveDisplayOverride@@$$QEAPEAUIMtfSuggestionCandidatePrimitive@@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Microsoft::WRL::Details::MakeAndInitialize<PrimitiveDisplayOverride,PrimitiveDisplayOverride,IMtfSuggestionCandidatePrimitive *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(PrimitiveDisplayOverride * *,IMtfSuggestionCandidatePrimitive * &&,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1800099f7  mov     rcx, [rbp+57h]; this
0x1800099fb  test    eax, eax
0x1800099fd  js      loc_180009CD0
0x180009a03  mov     rsi, [rbp+4Fh+var_90]
0x180009a07  mov     [rbp+4Fh+arg_8], 0
0x180009a0f  mov     rax, [rsi]
0x180009a12  lea     r8, [rbp+4Fh+arg_8]
0x180009a16  lea     rdx, _GUID_92445657_1419_4aaa_a92f_486ab29470c0
0x180009a1d  mov     rcx, rsi
0x180009a20  mov     rax, [rax]
0x180009a23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a28  mov     rcx, [rbp+57h]; this
0x180009a2c  test    eax, eax
0x180009a2e  js      loc_180009CBB
0x180009a34  cmp     rbx, r14
0x180009a37  jnz     short loc_180009A4E
0x180009a39  lea     rcx, [rbp+4Fh+var_B0]
0x180009a3d  call    ?_Reserve@?$vector@V?$com_ptr_t@UIMtfSuggestionCandidatePrimitive@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIMtfSuggestionCandidatePrimitive@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@IEAAX_K@Z; std::vector<wil::com_ptr_t<IMtfSuggestionCandidatePrimitive,wil::err_exception_policy>>::_Reserve(unsigned __int64)
0x180009a42  mov     r14, [rbp+4Fh+var_A0]
0x180009a46  mov     rbx, qword ptr [rbp+4Fh+var_B0+8]
0x180009a4a  mov     rdi, qword ptr [rbp+4Fh+var_B0]
0x180009a4e  mov     rax, [rbp+4Fh+arg_8]
0x180009a52  mov     [rbp+4Fh+arg_8], 0
0x180009a5a  mov     [rbx], rax
0x180009a5d  add     rbx, 8
0x180009a61  mov     qword ptr [rbp+4Fh+var_B0+8], rbx
0x180009a65  mov     rcx, [rbp+4Fh+arg_8]
0x180009a69  test    rcx, rcx
0x180009a6c  jz      short loc_180009A7B
0x180009a6e  mov     rax, [rcx]
0x180009a71  mov     rax, [rax+10h]
0x180009a75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a7a  nop
0x180009a7b  mov     byte ptr [rbp+4Fh+arg_8], 1
0x180009a7f  mov     rax, [rsi]
0x180009a82  mov     rcx, rsi
0x180009a85  mov     rax, [rax+10h]
0x180009a89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a8e  nop
0x180009a8f  jmp     loc_180009B2D
0x180009a94  mov     dword ptr [r15], 1
0x180009a9b  jmp     loc_180009B2D
0x180009aa0  lea     rax, [rbp+4Fh+var_C8]
0x180009aa4  cmp     rax, rbx
0x180009aa7  jnb     short loc_180009AF2
0x180009aa9  lea     rax, [rbp+4Fh+var_C8]
0x180009aad  cmp     rdi, rax
0x180009ab0  ja      short loc_180009AF2
0x180009ab2  lea     rsi, [rbp+4Fh+var_C8]
0x180009ab6  sub     rsi, rdi
0x180009ab9  sar     rsi, 3
0x180009abd  cmp     rbx, r14
0x180009ac0  jnz     short loc_180009AD7
0x180009ac2  lea     rcx, [rbp+4Fh+var_B0]
0x180009ac6  call    ?_Reserve@?$vector@V?$com_ptr_t@UIMtfSuggestionCandidatePrimitive@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIMtfSuggestionCandidatePrimitive@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@IEAAX_K@Z; std::vector<wil::com_ptr_t<IMtfSuggestionCandidatePrimitive,wil::err_exception_policy>>::_Reserve(unsigned __int64)
0x180009acb  mov     r14, [rbp+4Fh+var_A0]
0x180009acf  mov     rbx, qword ptr [rbp+4Fh+var_B0+8]
0x180009ad3  mov     rdi, qword ptr [rbp+4Fh+var_B0]
0x180009ad7  mov     rcx, [rdi+rsi*8]
0x180009adb  mov     [rbx], rcx
0x180009ade  test    rcx, rcx
0x180009ae1  jz      short loc_180009AF0
0x180009ae3  mov     rax, [rcx]
0x180009ae6  mov     rax, [rax+8]
0x180009aea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009aef  nop
0x180009af0  jmp     short loc_180009B25
0x180009af2  cmp     rbx, r14
0x180009af5  jnz     short loc_180009B0C
0x180009af7  lea     rcx, [rbp+4Fh+var_B0]
0x180009afb  call    ?_Reserve@?$vector@V?$com_ptr_t@UIMtfSuggestionCandidatePrimitive@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIMtfSuggestionCandidatePrimitive@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@IEAAX_K@Z; std::vector<wil::com_ptr_t<IMtfSuggestionCandidatePrimitive,wil::err_exception_policy>>::_Reserve(unsigned __int64)
0x180009b00  mov     r14, [rbp+4Fh+var_A0]
0x180009b04  mov     rbx, qword ptr [rbp+4Fh+var_B0+8]
0x180009b08  mov     rdi, qword ptr [rbp+4Fh+var_B0]
0x180009b0c  mov     rcx, [rbp+4Fh+var_C8]
0x180009b10  mov     [rbx], rcx
0x180009b13  test    rcx, rcx
0x180009b16  jz      short loc_180009B25
0x180009b18  mov     rax, [rcx]
0x180009b1b  mov     rax, [rax+8]
0x180009b1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b24  nop
0x180009b25  add     rbx, 8
0x180009b29  mov     qword ptr [rbp+4Fh+var_B0+8], rbx
0x180009b2d  cmp     dword ptr [r15], 1
0x180009b31  jz      loc_180009BFD
0x180009b37  mov     rsi, [r12+28h]
0x180009b3c  mov     r15, qword ptr [rbp+4Fh+var_80+8]
0x180009b40  mov     r12, qword ptr [rbp+4Fh+var_70]
0x180009b44  mov     rcx, [rbp+4Fh+arg_18]
0x180009b48  mov     dword ptr [rcx], 0
0x180009b4e  mov     [rbp+4Fh+var_90], 0
0x180009b56  mov     [rsp+110h+var_D0], 2
0x180009b5b  lea     r8, [rsp+110h+var_D0]
0x180009b60  lea     rdx, [rbp+4Fh+var_88]
0x180009b64  lea     rcx, [rsi+10h]
0x180009b68  call    ?find@?$_Hash@V?$_Umap_traits@W4FilterType@@V?$unique_ptr@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@U?$default_delete@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@@2@@std@@V?$_Uhash_compare@W4FilterType@@U?$hash@W4FilterType@@@std@@U?$equal_to@W4FilterType@@@3@@3@V?$allocator@U?$pair@$$CBW4FilterType@@V?$unique_ptr@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@U?$default_delete@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@@2@@std@@@std@@@3@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBW4FilterType@@V?$unique_ptr@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@U?$default_delete@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@@2@@std@@@std@@@std@@@std@@@2@AEBW4FilterType@@@Z; std::_Hash<std::_Umap_traits<FilterType,std::unique_ptr<std::vector<std::unique_ptr<FilterAgent>>>,std::_Uhash_compare<FilterType,std::hash<FilterType>,std::equal_to<FilterType>>,std::allocator<std::pair<FilterType const,std::unique_ptr<std::vector<std::unique_ptr<FilterAgent>>>>>,0>>::find(FilterType const &)
0x180009b6d  mov     rdx, [rbp+4Fh+var_88]
0x180009b71  cmp     rdx, [rsi+10h]
0x180009b75  mov     rsi, [rbp+4Fh+arg_10]
0x180009b79  jz      short loc_180009BA9
0x180009b7b  add     rdx, 18h
0x180009b7f  lea     rax, [rbp+4Fh+var_90]
0x180009b83  mov     qword ptr [rsp+110h+var_D8], rax
0x180009b88  mov     rax, [rbp+4Fh+arg_18]
0x180009b8c  mov     [rsp+110h+var_E0], rax
0x180009b91  mov     dword ptr [rsp+110h+var_E8], 0
0x180009b99  mov     qword ptr [rsp+110h+var_F0], r15
0x180009b9e  mov     r9, r12
0x180009ba1  mov     r8, rsi
0x180009ba4  call    ?GetReplaceByType@FilterManager@@IEAAXAEBV?$unique_ptr@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@U?$default_delete@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@@2@@std@@PEAGPEBG2KPEAHPEAPEAG@Z; FilterManager::GetReplaceByType(std::unique_ptr<std::vector<std::unique_ptr<FilterAgent>>> const &,ushort *,ushort const *,ushort const *,ulong,int *,ushort * *)
0x180009ba9  mov     r15, [rbp+4Fh+arg_18]
0x180009bad  mov     rcx, [rbp+4Fh+pbstr]; bstrString
0x180009bb1  cmp     dword ptr [r15], 1
0x180009bb5  jz      short loc_180009BEF
0x180009bb7  test    rcx, rcx
0x180009bba  jz      short loc_180009BC3
0x180009bbc  call    cs:__imp_SysFreeString
0x180009bc2  nop
0x180009bc3  mov     rcx, [rbp+4Fh+var_C8]
0x180009bc7  test    rcx, rcx
0x180009bca  jz      short loc_180009BD9
0x180009bcc  mov     rax, [rcx]
0x180009bcf  mov     rax, [rax+10h]
0x180009bd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bd8  nop
0x180009bd9  mov     ecx, [rbp+4Fh+var_98]
0x180009bdc  inc     ecx
0x180009bde  mov     [rbp+4Fh+var_98], ecx
0x180009be1  cmp     ecx, [rbp+4Fh+var_C0]
0x180009be4  jnb     short loc_180009C23
0x180009be6  mov     r12, [rbp+4Fh+arg_0]
0x180009bea  jmp     loc_18000990E
0x180009bef  test    rcx, rcx
0x180009bf2  jz      short loc_180009BFB
0x180009bf4  call    cs:__imp_SysFreeString
0x180009bfa  nop
0x180009bfb  jmp     short loc_180009C0D
0x180009bfd  mov     rcx, [rbp+4Fh+pbstr]; bstrString
0x180009c01  test    rcx, rcx
0x180009c04  jz      short loc_180009C0D
0x180009c06  call    cs:__imp_SysFreeString
0x180009c0c  nop
0x180009c0d  mov     rcx, [rbp+4Fh+var_C8]
0x180009c11  test    rcx, rcx
0x180009c14  jz      short loc_180009C23
0x180009c16  mov     rax, [rcx]
0x180009c19  mov     rax, [rax+10h]
0x180009c1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c22  nop
0x180009c23  cmp     byte ptr [rbp+4Fh+arg_8], 0
0x180009c27  jz      short loc_180009C74
0x180009c29  cmp     rdi, rbx
0x180009c2c  jz      short loc_180009C74
0x180009c2e  mov     rax, [r13+0]
0x180009c32  mov     rcx, r13
0x180009c35  mov     rax, [rax+50h]
0x180009c39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c3e  mov     rcx, [rbp+57h]; this
0x180009c42  test    eax, eax
0x180009c44  js      loc_180009CE5
0x180009c4a  cmp     rdi, rbx
0x180009c4d  jz      short loc_180009C74
0x180009c4f  mov     rax, [r13+0]
0x180009c53  mov     rdx, [rdi]
0x180009c56  mov     rcx, r13
0x180009c59  mov     rax, [rax+48h]
0x180009c5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c62  mov     rcx, [rbp+57h]; this
0x180009c66  test    eax, eax
0x180009c68  js      loc_180009CFA
0x180009c6e  add     rdi, 8
0x180009c72  jmp     short loc_180009C4A
0x180009c74  lea     rcx, [rbp+4Fh+var_B0]
0x180009c78  call    ??1?$vector@V?$com_ptr_t@UIMtfSuggestionCandidatePrimitive@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIMtfSuggestionCandidatePrimitive@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::com_ptr_t<IMtfSuggestionCandidatePrimitive,wil::err_exception_policy>>::~vector<wil::com_ptr_t<IMtfSuggestionCandidatePrimitive,wil::err_exception_policy>>(void)
0x180009c7d  add     rsp, 0D8h
0x180009c84  pop     r15
0x180009c86  pop     r14
0x180009c88  pop     r13
0x180009c8a  pop     r12
0x180009c8c  pop     rdi
0x180009c8d  pop     rsi
0x180009c8e  pop     rbx
0x180009c8f  pop     rbp
0x180009c90  retn
0x180009c91  mov     r9d, eax; char *
0x180009c94  lea     r8, aMincoreTextinp_18; "mincore\\textinput\\dev\\mtf\\datasourc"...
0x180009c9b  mov     edx, 0D0h; void *
0x180009ca0  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180009ca6  mov     r9d, eax; char *
0x180009ca9  lea     r8, aMincoreTextinp_18; "mincore\\textinput\\dev\\mtf\\datasourc"...
0x180009cb0  mov     edx, 0CBh; void *
0x180009cb5  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180009cbb  mov     r9d, eax; char *
0x180009cbe  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180009cc5  mov     edx, 1CBEh; void *
0x180009cca  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180009cd0  mov     r9d, eax; char *
0x180009cd3  lea     r8, aMincoreTextinp_18; "mincore\\textinput\\dev\\mtf\\datasourc"...
0x180009cda  mov     edx, 0E4h; void *
0x180009cdf  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180009ce5  mov     r9d, eax; char *
0x180009ce8  lea     r8, aMincoreTextinp_18; "mincore\\textinput\\dev\\mtf\\datasourc"...
0x180009cef  mov     edx, 68h ; 'h'; void *
0x180009cf4  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180009cfa  mov     r9d, eax; char *
  ... truncated ...
```
