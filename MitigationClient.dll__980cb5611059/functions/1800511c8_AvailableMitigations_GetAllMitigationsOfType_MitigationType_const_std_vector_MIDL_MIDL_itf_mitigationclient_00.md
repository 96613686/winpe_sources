# AvailableMitigations::GetAllMitigationsOfType(MitigationType const *,std::vector<__MIDL___MIDL_itf_mitigationclient_0000_0002_0002,std::allocator<__MIDL___MIDL_itf_mitigationclient_0000_0002_0002>> &)

- ea: `0x1800511c8`
- end: `0x1800513c9`
- name: `?GetAllMitigationsOfType@AvailableMitigations@@QEAAJPEBW4MitigationType@@AEAV?$vector@U__MIDL___MIDL_itf_mitigationclient_0000_0002_0002@@V?$allocator@U__MIDL___MIDL_itf_mitigationclient_0000_0002_0002@@@std@@@std@@@Z`
- size: `513`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003438c`

## callees

- `0x18000a6e0`
- `0x18000b2b4`
- `0x18000cecc`
- `0x18000ddb8`
- `0x18001208c`
- `0x180013a7c`
- `0x180018b54`
- `0x18001d5d8`
- `0x180050a7c`
- `0x1800511c8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800512a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800512ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800512f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800512a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800512ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800512f4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AvailableMitigations::GetAllMitigationsOfType(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rdx
  __int64 v5; // r9
  unsigned __int64 i; // rsi
  char *v7; // rbx
  __int64 v8; // rdi
  const WCHAR *v9; // rax
  HRESULT v10; // ebx
  const WCHAR *v11; // rax
  __int64 v12; // rdx
  const WCHAR *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rdx
  char *v17; // [rsp+20h] [rbp-49h] BYREF
  __int64 v18; // [rsp+28h] [rbp-41h]
  __int64 v19; // [rsp+30h] [rbp-39h]
  _BYTE v20[8]; // [rsp+38h] [rbp-31h] BYREF
  HSTRING string; // [rsp+40h] [rbp-29h] BYREF
  HSTRING v22; // [rsp+48h] [rbp-21h] BYREF
  __int128 v23; // [rsp+50h] [rbp-19h]
  HSTRING v24; // [rsp+60h] [rbp-9h] BYREF
  int v25; // [rsp+68h] [rbp-1h]
  __int16 v26; // [rsp+6Ch] [rbp+3h]
  int v27; // [rsp+70h] [rbp+7h]
  int v28; // [rsp+74h] [rbp+Bh]
  __int64 v29; // [rsp+78h] [rbp+Fh]
  int v30; // [rsp+80h] [rbp+17h]
  int v31; // [rsp+84h] [rbp+1Bh]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>>>>>>(&v17);
  MitigationLog<_AVAILABLE_MITIGATION_RECORD,MitigationResultInternal>::GetAllMitigationsOfTypeInternal(v5, v4, &v17);
  for ( i = 0; ; ++i )
  {
    v7 = v17;
    if ( i >= 0x86BCA1AF286BCA1BuLL * ((v18 - (__int64)v17) >> 3) )
      break;
    memset_0(&string, 0, 0x48u);
    v8 = 152 * i;
    v23 = *(_OWORD *)&v7[152 * i];
    v25 = *(_DWORD *)&v7[152 * i + 32];
    v26 = *(_WORD *)&v7[152 * i + 36];
    v27 = *(_DWORD *)&v7[152 * i + 16];
    v28 = *(_DWORD *)&v7[152 * i + 20];
    v29 = *(_QWORD *)&v7[152 * i + 24];
    v30 = *(_DWORD *)&v7[152 * i + 40];
    v31 = *(_DWORD *)&v7[152 * i + 144];
    v9 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v7[152 * i + 48]);
    v10 = WindowsCreateString(v9, *(_DWORD *)&v7[152 * i + 64], &string);
    if ( v10 < 0 )
    {
      v15 = 47;
      goto LABEL_10;
    }
    v11 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v17[v8 + 80]);
    v10 = WindowsCreateString(v11, *(_DWORD *)(v8 + v12 + 96), &v22);
    if ( v10 < 0 )
    {
      v15 = 48;
      goto LABEL_10;
    }
    v13 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v17[v8 + 112]);
    v10 = WindowsCreateString(v13, *(_DWORD *)(v8 + v14 + 128), &v24);
    if ( v10 < 0 )
    {
      v15 = 49;
LABEL_10:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\mitigationlog\\availablemitigations.cpp",
        (const char *)(unsigned int)v10,
        (int)v17);
      if ( v17 )
      {
        std::_Destroy_range<std::allocator<MitigationResultInternal>>(v17, v18);
        std::_Deallocate<16>(v17, 8 * ((v19 - (__int64)v17) >> 3));
      }
      return (unsigned int)v10;
    }
    std::vector<__MIDL___MIDL_itf_mitigationclient_0000_0002_0002>::emplace<__MIDL___MIDL_itf_mitigationclient_0000_0002_0002 const &>(
      a3,
      v20,
      *(_QWORD *)(a3 + 8),
      &string);
  }
  if ( v17 )
  {
    std::_Destroy_range<std::allocator<MitigationResultInternal>>(v17, v18);
    std::_Deallocate<16>(v17, 8 * ((v19 - (__int64)v17) >> 3));
  }
  return 0;
}

```

## disassembly

```asm
0x1800511c8  mov     [rsp-8+arg_8], rbx
0x1800511cd  push    rbp
0x1800511ce  push    rsi
0x1800511cf  push    rdi
0x1800511d0  push    r14
0x1800511d2  push    r15
0x1800511d4  lea     rbp, [rsp-37h]
0x1800511d9  sub     rsp, 0A0h
0x1800511e0  mov     rax, cs:__security_cookie
0x1800511e7  xor     rax, rsp
0x1800511ea  mov     [rbp+57h+var_30], rax
0x1800511ee  mov     r14, r8
0x1800511f1  mov     r9, rcx
0x1800511f4  lea     rcx, [rbp+57h+var_A0]
0x1800511f8  call    ??$?0AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>>>>>>(std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>> const &)
0x1800511fd  nop
0x1800511fe  lea     r8, [rbp+57h+var_A0]
0x180051202  mov     rcx, r9
0x180051205  call    ?GetAllMitigationsOfTypeInternal@?$MitigationLog@U_AVAILABLE_MITIGATION_RECORD@@UMitigationResultInternal@@@@QEAAJPEBW4MitigationType@@AEAV?$vector@UMitigationResultInternal@@V?$allocator@UMitigationResultInternal@@@std@@@std@@@Z; MitigationLog<_AVAILABLE_MITIGATION_RECORD,MitigationResultInternal>::GetAllMitigationsOfTypeInternal(MitigationType const *,std::vector<MitigationResultInternal> &)
0x18005120a  xor     esi, esi
0x18005120c  mov     r15, 86BCA1AF286BCA1Bh
0x180051216  mov     rbx, [rbp+57h+var_A0]
0x18005121a  mov     rdx, [rbp+57h+var_98]
0x18005121e  mov     rax, rdx
0x180051221  sub     rax, rbx
0x180051224  sar     rax, 3
0x180051228  imul    rax, r15
0x18005122c  cmp     rsi, rax
0x18005122f  jnb     loc_180051378
0x180051235  xor     edx, edx; Val
0x180051237  lea     r8d, [rdx+48h]; Size
0x18005123b  lea     rcx, [rbp+57h+string]; void *
0x18005123f  call    memset_0
0x180051244  imul    rdi, rsi, 98h
0x18005124b  movups  xmm0, xmmword ptr [rdi+rbx]
0x18005124f  movdqu  [rbp+57h+var_70], xmm0
0x180051254  mov     eax, [rdi+rbx+20h]
0x180051258  mov     [rbp+57h+var_58], eax
0x18005125b  movzx   eax, word ptr [rdi+rbx+24h]
0x180051260  mov     [rbp+57h+var_54], ax
0x180051264  mov     eax, [rdi+rbx+10h]
0x180051268  mov     [rbp+57h+var_50], eax
0x18005126b  mov     eax, [rdi+rbx+14h]
0x18005126f  mov     [rbp+57h+var_4C], eax
0x180051272  mov     rax, [rdi+rbx+18h]
0x180051277  mov     [rbp+57h+var_48], rax
0x18005127b  mov     eax, [rdi+rbx+28h]
0x18005127f  mov     [rbp+57h+var_40], eax
0x180051282  mov     eax, [rdi+rbx+90h]
0x180051289  mov     [rbp+57h+var_3C], eax
0x18005128c  lea     rcx, [rbx+30h]
0x180051290  add     rcx, rdi
0x180051293  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180051298  lea     r8, [rbp+57h+string]; string
0x18005129c  mov     edx, [rdi+rbx+40h]; length
0x1800512a0  mov     rcx, rax; sourceString
0x1800512a3  call    cs:__imp_WindowsCreateString
0x1800512a9  mov     ebx, eax
0x1800512ab  test    eax, eax
0x1800512ad  js      short loc_18005132A
0x1800512af  mov     rdx, [rbp+57h+var_A0]
0x1800512b3  lea     rcx, [rdx+50h]
0x1800512b7  add     rcx, rdi
0x1800512ba  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800512bf  lea     r8, [rbp+57h+var_78]; string
0x1800512c3  mov     edx, [rdi+rdx+60h]; length
0x1800512c7  mov     rcx, rax; sourceString
0x1800512ca  call    cs:__imp_WindowsCreateString
0x1800512d0  mov     ebx, eax
0x1800512d2  test    eax, eax
0x1800512d4  js      short loc_180051323
0x1800512d6  mov     rdx, [rbp+57h+var_A0]
0x1800512da  lea     rcx, [rdx+70h]
0x1800512de  add     rcx, rdi
0x1800512e1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800512e6  lea     r8, [rbp+57h+var_60]; string
0x1800512ea  mov     edx, [rdi+rdx+80h]; length
0x1800512f1  mov     rcx, rax; sourceString
0x1800512f4  call    cs:__imp_WindowsCreateString
0x1800512fa  mov     ebx, eax
0x1800512fc  test    eax, eax
0x1800512fe  js      short loc_18005131C
0x180051300  lea     r9, [rbp+57h+string]
0x180051304  mov     r8, [r14+8]
0x180051308  lea     rdx, [rbp+57h+var_88]
0x18005130c  mov     rcx, r14
0x18005130f  call    ??$emplace@AEBU__MIDL___MIDL_itf_mitigationclient_0000_0002_0002@@@?$vector@U__MIDL___MIDL_itf_mitigationclient_0000_0002_0002@@V?$allocator@U__MIDL___MIDL_itf_mitigationclient_0000_0002_0002@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@U__MIDL___MIDL_itf_mitigationclient_0000_0002_0002@@@std@@@std@@@1@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@U__MIDL___MIDL_itf_mitigationclient_0000_0002_0002@@@std@@@std@@@1@AEBU__MIDL___MIDL_itf_mitigationclient_0000_0002_0002@@@Z; std::vector<__MIDL___MIDL_itf_mitigationclient_0000_0002_0002>::emplace<__MIDL___MIDL_itf_mitigationclient_0000_0002_0002 const &>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<__MIDL___MIDL_itf_mitigationclient_0000_0002_0002>>>,__MIDL___MIDL_itf_mitigationclient_0000_0002_0002 const &)
0x180051314  inc     rsi
0x180051317  jmp     loc_180051216
0x18005131c  mov     edx, 31h ; '1'
0x180051321  jmp     short loc_18005132F
0x180051323  mov     edx, 30h ; '0'
0x180051328  jmp     short loc_18005132F
0x18005132a  mov     edx, 2Fh ; '/'; void *
0x18005132f  mov     rcx, [rbp+5Fh]; this
0x180051333  mov     r9d, ebx; char *
0x180051336  lea     r8, aOnecoreBaseDia_41; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18005133d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180051342  nop
0x180051343  mov     rcx, [rbp+57h+var_A0]
0x180051347  test    rcx, rcx
0x18005134a  jz      short loc_180051374
0x18005134c  mov     rdx, [rbp+57h+var_98]
0x180051350  call    ??$_Destroy_range@V?$allocator@UMitigationResultInternal@@@std@@@std@@YAXPEAUMitigationResultInternal@@QEAU1@AEAV?$allocator@UMitigationResultInternal@@@0@@Z; std::_Destroy_range<std::allocator<MitigationResultInternal>>(MitigationResultInternal *,MitigationResultInternal * const,std::allocator<MitigationResultInternal> &)
0x180051355  mov     rcx, [rbp+57h+var_A0]
0x180051359  mov     rax, [rbp+57h+var_90]
0x18005135d  sub     rax, rcx
0x180051360  sar     rax, 3
0x180051364  imul    rax, r15
0x180051368  imul    rdx, rax, 98h
0x18005136f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180051374  mov     eax, ebx
0x180051376  jmp     short loc_1800513A6
0x180051378  test    rbx, rbx
0x18005137b  jz      short loc_1800513A4
0x18005137d  mov     rcx, rbx
0x180051380  call    ??$_Destroy_range@V?$allocator@UMitigationResultInternal@@@std@@@std@@YAXPEAUMitigationResultInternal@@QEAU1@AEAV?$allocator@UMitigationResultInternal@@@0@@Z; std::_Destroy_range<std::allocator<MitigationResultInternal>>(MitigationResultInternal *,MitigationResultInternal * const,std::allocator<MitigationResultInternal> &)
0x180051385  mov     rcx, [rbp+57h+var_A0]
0x180051389  mov     rax, [rbp+57h+var_90]
0x18005138d  sub     rax, rcx
0x180051390  sar     rax, 3
0x180051394  imul    rax, r15
0x180051398  imul    rdx, rax, 98h
0x18005139f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800513a4  xor     eax, eax
0x1800513a6  mov     rcx, [rbp+57h+var_30]
0x1800513aa  xor     rcx, rsp; StackCookie
0x1800513ad  call    __security_check_cookie
0x1800513b2  mov     rbx, [rsp+0C0h+arg_8]
0x1800513ba  add     rsp, 0A0h
0x1800513c1  pop     r15
0x1800513c3  pop     r14
0x1800513c5  pop     rdi
0x1800513c6  pop     rsi
0x1800513c7  pop     rbp
0x1800513c8  retn
```
