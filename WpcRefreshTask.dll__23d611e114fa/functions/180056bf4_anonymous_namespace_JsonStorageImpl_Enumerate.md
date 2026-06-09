# _anonymous_namespace_::JsonStorageImpl::Enumerate

- ea: `0x180056bf4`
- end: `0x1800571bc`
- name: `_anonymous_namespace_::JsonStorageImpl::Enumerate`
- size: `1480`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config`

## callers

- `0x1800571e4`
- `0x180057224`

## callees

- `0x1800060a0`
- `0x180006108`
- `0x180006ee0`
- `0x180008d50`
- `0x180009a80`
- `0x180014698`
- `0x180015510`
- `0x180035e0c`
- `0x1800549b8`
- `0x180054b8c`
- `0x180056300`
- `0x180056314`
- `0x180056bf4`
- `0x180059150`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180056ff2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180056ff2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180056f6e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180056f6e`

## pseudocode

```c
// Hidden C++ exception states: #wind=31
__int64 __fastcall anonymous_namespace_::JsonStorageImpl::Enumerate(__int64 a1, __int64 a2, char a3)
{
  HSTRING v5; // r14
  __int64 (__fastcall ***v6)(_QWORD, GUID *, __int64 *); // r9
  __int64 v7; // rcx
  int v8; // eax
  HSTRING v9; // rdx
  int v10; // eax
  unsigned int v11; // esi
  char v12; // al
  __int64 v13; // rcx
  __int64 v14; // rbx
  __int64 (__fastcall *v15)(__int64, _QWORD **); // rdi
  _QWORD *v16; // rcx
  int v17; // eax
  _QWORD *v18; // rbx
  _QWORD *v19; // rdi
  int v20; // esi
  int v21; // r15d
  _QWORD *v22; // rcx
  int v23; // eax
  int v24; // esi
  int v25; // edi
  _QWORD *v26; // rcx
  PCWSTR StringRawBuffer; // rax
  __int64 v28; // r8
  _OWORD *v29; // rdx
  int v30; // eax
  __int64 v31; // rdx
  _QWORD *v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rcx
  char v36; // [rsp+20h] [rbp-89h] BYREF
  char v37; // [rsp+21h] [rbp-88h] BYREF
  char v38; // [rsp+22h] [rbp-87h]
  _QWORD *v39; // [rsp+28h] [rbp-81h] BYREF
  unsigned int v40; // [rsp+30h] [rbp-79h]
  HSTRING string; // [rsp+38h] [rbp-71h] BYREF
  __int64 v42; // [rsp+40h] [rbp-69h] BYREF
  _QWORD *v43; // [rsp+48h] [rbp-61h] BYREF
  __int64 v44; // [rsp+50h] [rbp-59h] BYREF
  __int64 v45; // [rsp+58h] [rbp-51h] BYREF
  __int64 v46; // [rsp+60h] [rbp-49h] BYREF
  __int64 v47; // [rsp+68h] [rbp-41h]
  _QWORD *v48; // [rsp+70h] [rbp-39h]
  _QWORD *v49; // [rsp+78h] [rbp-31h]
  _QWORD *v50; // [rsp+80h] [rbp-29h]
  _QWORD v51[3]; // [rsp+88h] [rbp-21h] BYREF
  __int128 pExceptionObject; // [rsp+A0h] [rbp-9h] BYREF
  __int128 v53; // [rsp+B0h] [rbp+7h]

  v38 = a3;
  v40 = 0;
  v5 = (HSTRING)operator new(0x28u);
  string = v5;
  *(_OWORD *)v5 = 0;
  *((_DWORD *)v5 + 2) = 1;
  *((_DWORD *)v5 + 3) = 1;
  *(_QWORD *)v5 = &std::_Ref_count_obj2<std::vector<std::wstring>>::`vftable';
  *((_QWORD *)v5 + 2) = 0;
  *((_QWORD *)v5 + 3) = 0;
  *((_QWORD *)v5 + 4) = 0;
  v51[0] = v5 + 4;
  v51[1] = v5;
  v6 = *(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))WinRT::As<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>,Windows::Data::Json::IJsonObject>(
                                                                &string,
                                                                a1 + 16);
  v7 = 0;
  v44 = 0;
  if ( v6 )
  {
    v8 = (**v6)(v6, &GUID_dfabb6e1_0411_5a8f_aa87_354e7110f099, &v44);
    if ( v8 < 0 )
    {
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)&pExceptionObject, v8);
      throw (ErrorCodeException *)&pExceptionObject;
    }
    v7 = v44;
  }
  v9 = string;
  if ( string )
  {
    string = 0;
    (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v9 + 16LL))(v9);
    v7 = v44;
  }
  v42 = 0;
  v43 = 0;
  if ( v7 )
  {
    v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v7 + 48LL))(v7, &v42);
    if ( v10 < 0 )
    {
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)&pExceptionObject, v10);
      throw (ErrorCodeException *)&pExceptionObject;
    }
  }
  v11 = 14;
  WinRT::iterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *>::end(
    v7,
    &v46);
  while ( 1 )
  {
    v36 = 0;
    if ( v42 )
      (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v42 + 56LL))(v42, &v36);
    v12 = 0;
    v37 = 0;
    v13 = v46;
    if ( v46 )
    {
      (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v46 + 56LL))(v46, &v37);
      v13 = v46;
      v12 = v37;
    }
    if ( v36 == v12 )
      break;
    v14 = v42;
    v15 = *(__int64 (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)v42 + 48LL);
    v16 = v43;
    if ( v43 )
    {
      v43 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v16 + 16LL))(v16);
    }
    v17 = v15(v14, &v43);
    if ( v17 < 0 )
    {
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)&pExceptionObject, v17);
      throw (ErrorCodeException *)&pExceptionObject;
    }
    v18 = v43;
    v51[2] = &v45;
    v19 = v43;
    v39 = v43;
    if ( v43 )
    {
      (*(void (__fastcall **)(_QWORD *))(*v43 + 8LL))(v43);
      v19 = v39;
    }
    v49 = &v39;
    v45 = 0;
    v20 = v11 | 0x80;
    v40 = v20;
    v50 = v19;
    if ( v19 )
      (*(void (__fastcall **)(_QWORD *))(*v19 + 8LL))(v19);
    v48 = v19;
    if ( v19 )
      (*(void (__fastcall **)(_QWORD *))(*v19 + 8LL))(v19);
    v21 =  Windows::Data::Json::IJsonValue::`vcall'{56,{flat}}(v19, &v45);
    if ( v19 )
    {
      (*(void (__fastcall **)(_QWORD *))(*v19 + 16LL))(v19);
      (*(void (__fastcall **)(_QWORD *))(*v19 + 16LL))(v19);
    }
    if ( v21 < 0 )
    {
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)&pExceptionObject, v21);
      throw (ErrorCodeException *)&pExceptionObject;
    }
    v22 = v39;
    if ( v39 )
    {
      v39 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v22 + 16LL))(v22);
    }
    v40 = v20 & 0xFFFFFF7F;
    v11 = v20 & 0xFFFFFF1F | 0x60;
    v23 = WinRT::Call<Windows::Data::Json::IJsonValue,long (Windows::Data::Json::IJsonValue::*)(enum Windows::Data::Json::JsonValueType *),>(&v45);
    if ( v38 == (v23 == 5) )
    {
      v39 = v18;
      if ( v18 )
      {
        (*(void (__fastcall **)(_QWORD *))(*v18 + 8LL))(v18);
        v18 = v39;
      }
      v48 = &v39;
      string = 0;
      v24 = v11 | 0x400;
      v40 = v24;
      v50 = v18;
      if ( v18 )
        (*(void (__fastcall **)(_QWORD *))(*v18 + 8LL))(v18);
      v49 = v18;
      if ( v18 )
        (*(void (__fastcall **)(_QWORD *))(*v18 + 8LL))(v18);
      v25 =  Windows::Foundation::Collections::IKeyValuePair_impl<HSTRING__ *,Windows::Data::Json::IJsonValue *>::`vcall'{48,{flat}}(
              v18,
              &string);
      if ( v18 )
      {
        (*(void (__fastcall **)(_QWORD *))(*v18 + 16LL))(v18);
        (*(void (__fastcall **)(_QWORD *))(*v18 + 16LL))(v18);
      }
      if ( v25 < 0 )
      {
        ErrorCodeException::ErrorCodeException((ErrorCodeException *)&pExceptionObject, v25);
        throw (ErrorCodeException *)&pExceptionObject;
      }
      v26 = v39;
      if ( v39 )
      {
        v39 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v26 + 16LL))(v26);
      }
      v40 = v24 & 0xFFFFFBFF;
      v11 = v24 & 0xFFFFF8FF | 0x300;
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      pExceptionObject = 0;
      v53 = 0u;
      v28 = -1;
      do
        ++v28;
      while ( StringRawBuffer[v28] );
      std::wstring::_Construct<1,unsigned short const *>(&pExceptionObject, StringRawBuffer, v28);
      v29 = (_OWORD *)*((_QWORD *)v5 + 3);
      if ( v29 == *((_OWORD **)v5 + 4) )
      {
        std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v5 + 4, v29, &pExceptionObject);
      }
      else
      {
        *v29 = pExceptionObject;
        v29[1] = v53;
        *(_QWORD *)&v53 = 0;
        *((_QWORD *)&v53 + 1) = 7;
        LOWORD(pExceptionObject) = 0;
        *((_QWORD *)v5 + 3) += 32LL;
      }
      std::wstring::~wstring(&pExceptionObject);
      if ( string )
        WindowsDeleteString(string);
    }
    v36 = 0;
    v30 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v42 + 64LL))(v42, &v36);
    if ( v30 < 0 )
    {
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)&pExceptionObject, v30);
      throw (ErrorCodeException *)&pExceptionObject;
    }
  }
  v31 = v47;
  if ( v47 )
  {
    v47 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    v13 = v46;
  }
  if ( v13 )
  {
    v46 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  v32 = v43;
  if ( v43 )
  {
    v43 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v32 + 16LL))(v32);
  }
  v33 = v42;
  if ( v42 )
  {
    v42 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  }
  v34 = v44;
  if ( v44 )
  {
    v44 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
  }
  Collections::Enumerable<std::wstring>::Enumerable<std::wstring>(a2, v51);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v5 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(HSTRING))v5)(v5);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v5 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v5 + 8LL))(v5);
  }
  return a2;
}

```

## disassembly

```asm
0x180056bf4  mov     [rsp-8+arg_10], rbx
0x180056bf9  push    rbp
0x180056bfa  push    rsi
0x180056bfb  push    rdi
0x180056bfc  push    r12
0x180056bfe  push    r13
0x180056c00  push    r14
0x180056c02  push    r15
0x180056c04  lea     rbp, [rsp-27h]
0x180056c09  sub     rsp, 0D0h
0x180056c10  mov     rax, cs:__security_cookie
0x180056c17  xor     rax, rsp
0x180056c1a  mov     [rbp+57h+var_38], rax
0x180056c1e  mov     [rsp+100h+var_DE], r8b
0x180056c23  mov     r13, rdx
0x180056c26  mov     rbx, rcx
0x180056c29  mov     [rbp+57h+string], rdx
0x180056c2d  xor     r15d, r15d
0x180056c30  mov     [rbp+57h+var_D0], r15d
0x180056c34  lea     ecx, [r15+28h]; Size
0x180056c38  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180056c3d  mov     r14, rax
0x180056c40  mov     [rbp+57h+string], rax
0x180056c44  xorps   xmm0, xmm0
0x180056c47  movups  xmmword ptr [rax], xmm0
0x180056c4a  lea     eax, [r15+1]
0x180056c4e  mov     [r14+8], eax
0x180056c52  mov     [r14+0Ch], eax
0x180056c56  lea     rax, ??_7?$_Ref_count_obj2@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@6B@; const std::_Ref_count_obj2<std::vector<std::wstring>>::`vftable'
0x180056c5d  mov     [r14], rax
0x180056c60  lea     r12, [r14+10h]
0x180056c64  mov     [r12], r15
0x180056c68  mov     [r12+8], r15
0x180056c6d  mov     [r12+10h], r15
0x180056c72  mov     [rbp+57h+var_78], r12
0x180056c76  mov     [rbp+57h+var_70], r14
0x180056c7a  lea     rdx, [rbx+10h]
0x180056c7e  lea     rcx, [rbp+57h+string]
0x180056c82  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@UIJsonObject@Json@Data@4@@WinRT@@YA?AV?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@AEBV?$ComPtr@UIJsonObject@Json@Data@Windows@@@23@PEAX@Z; WinRT::As<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>,Windows::Data::Json::IJsonObject>(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> const &,void *)
0x180056c87  nop
0x180056c88  mov     r9, [rax]
0x180056c8b  mov     ecx, r15d
0x180056c8e  mov     [rbp+57h+var_B0], rcx
0x180056c92  test    r9, r9
0x180056c95  jz      short loc_180056CBC
0x180056c97  mov     rax, [r9]
0x180056c9a  lea     r8, [rbp+57h+var_B0]
0x180056c9e  lea     rdx, _GUID_dfabb6e1_0411_5a8f_aa87_354e7110f099
0x180056ca5  mov     rcx, r9
0x180056ca8  mov     rax, [rax]
0x180056cab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056cb0  test    eax, eax
0x180056cb2  js      loc_18005714B
0x180056cb8  mov     rcx, [rbp+57h+var_B0]
0x180056cbc  mov     rdx, [rbp+57h+string]
0x180056cc0  test    rdx, rdx
0x180056cc3  jz      short loc_180056CDC
0x180056cc5  mov     [rbp+57h+string], r15
0x180056cc9  mov     rax, [rdx]
0x180056ccc  mov     rcx, rdx
0x180056ccf  mov     rax, [rax+10h]
0x180056cd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056cd8  mov     rcx, [rbp+57h+var_B0]
0x180056cdc  mov     [rbp+57h+var_C0], r15
0x180056ce0  mov     [rbp+57h+var_B8], r15
0x180056ce4  test    rcx, rcx
0x180056ce7  jz      short loc_180056D01
0x180056ce9  mov     rax, [rcx]
0x180056cec  lea     rdx, [rbp+57h+var_C0]
0x180056cf0  mov     rax, [rax+30h]
0x180056cf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056cf9  test    eax, eax
0x180056cfb  js      loc_180057167
0x180056d01  mov     esi, 0Eh
0x180056d06  lea     rdx, [rbp+57h+var_A0]
0x180056d0a  call    ?end@?$iterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WinRT@@QEBA?AViterator@12@XZ; WinRT::iterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *>::end(void)
0x180056d0f  nop
0x180056d10  mov     [rsp+100h+var_E0], r15b
0x180056d15  mov     rcx, [rbp+57h+var_C0]
0x180056d19  test    rcx, rcx
0x180056d1c  jz      short loc_180056D2F
0x180056d1e  mov     rax, [rcx]
0x180056d21  lea     rdx, [rsp+100h+var_E0]
0x180056d26  mov     rax, [rax+38h]
0x180056d2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056d2f  mov     al, r15b
0x180056d32  mov     [rsp+100h+var_DF], al
0x180056d36  mov     rcx, [rbp+57h+var_A0]
0x180056d3a  test    rcx, rcx
0x180056d3d  jz      short loc_180056D58
0x180056d3f  mov     rax, [rcx]
0x180056d42  lea     rdx, [rsp+100h+var_DF]
0x180056d47  mov     rax, [rax+38h]
0x180056d4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056d50  mov     rcx, [rbp+57h+var_A0]
0x180056d54  mov     al, [rsp+100h+var_DF]
0x180056d58  cmp     [rsp+100h+var_E0], al
0x180056d5c  jz      loc_18005701F
0x180056d62  mov     rbx, [rbp+57h+var_C0]
0x180056d66  mov     rax, [rbx]
0x180056d69  mov     rdi, [rax+30h]
0x180056d6d  mov     rcx, [rbp+57h+var_B8]
0x180056d71  test    rcx, rcx
0x180056d74  jz      short loc_180056D87
0x180056d76  mov     [rbp+57h+var_B8], r15
0x180056d7a  mov     rax, [rcx]
0x180056d7d  mov     rax, [rax+10h]
0x180056d81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056d86  nop
0x180056d87  lea     rdx, [rbp+57h+var_B8]
0x180056d8b  mov     rcx, rbx
0x180056d8e  mov     rax, rdi
0x180056d91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056d96  test    eax, eax
0x180056d98  js      loc_180057113
0x180056d9e  mov     rbx, [rbp+57h+var_B8]
0x180056da2  lea     rax, [rbp+57h+var_A8]
0x180056da6  mov     [rbp+57h+var_68], rax
0x180056daa  mov     rdi, rbx
0x180056dad  mov     [rsp+100h+var_D8], rbx
0x180056db2  test    rbx, rbx
0x180056db5  jz      short loc_180056DCB
0x180056db7  mov     rax, [rbx]
0x180056dba  mov     rcx, rbx
0x180056dbd  mov     rax, [rax+8]
0x180056dc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056dc6  mov     rdi, [rsp+100h+var_D8]
0x180056dcb  lea     rax, [rsp+100h+var_D8]
0x180056dd0  mov     [rbp+57h+var_88], rax
0x180056dd4  mov     [rbp+57h+var_A8], r15
0x180056dd8  bts     esi, 7
0x180056ddc  mov     [rbp+57h+var_D0], esi
0x180056ddf  mov     [rbp+57h+var_80], rdi
0x180056de3  test    rdi, rdi
0x180056de6  jz      short loc_180056DF8
0x180056de8  mov     rax, [rdi]
0x180056deb  mov     rcx, rdi
0x180056dee  mov     rax, [rax+8]
0x180056df2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056df7  nop
0x180056df8  mov     [rbp+57h+var_90], rdi
0x180056dfc  test    rdi, rdi
0x180056dff  jz      short loc_180056E11
0x180056e01  mov     rax, [rdi]
0x180056e04  mov     rcx, rdi
0x180056e07  mov     rax, [rax+8]
0x180056e0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056e10  nop
0x180056e11  lea     rdx, [rbp+57h+var_A8]
0x180056e15  mov     rcx, rdi
0x180056e18  call    ??_9IJsonValue@Json@Data@Windows@@$BDI@AA; [thunk]: Windows::Data::Json::IJsonValue::`vcall'{56,{flat}}
0x180056e1d  mov     r15d, eax
0x180056e20  test    rdi, rdi
0x180056e23  jz      short loc_180056E35
0x180056e25  mov     rax, [rdi]
0x180056e28  mov     rcx, rdi
0x180056e2b  mov     rax, [rax+10h]
0x180056e2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056e34  nop
0x180056e35  test    rdi, rdi
0x180056e38  jz      short loc_180056E4A
0x180056e3a  mov     rax, [rdi]
0x180056e3d  mov     rcx, rdi
0x180056e40  mov     rax, [rax+10h]
0x180056e44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056e49  nop
0x180056e4a  test    r15d, r15d
0x180056e4d  js      loc_18005719F
0x180056e53  mov     rcx, [rsp+100h+var_D8]
0x180056e58  xor     r15d, r15d
0x180056e5b  test    rcx, rcx
0x180056e5e  jz      short loc_180056E72
0x180056e60  mov     [rsp+100h+var_D8], r15
0x180056e65  mov     rax, [rcx]
0x180056e68  mov     rax, [rax+10h]
0x180056e6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056e71  nop
0x180056e72  btr     esi, 7
0x180056e76  mov     [rbp+57h+var_D0], esi
0x180056e79  or      esi, 60h
0x180056e7c  lea     rcx, [rbp+57h+var_A8]
0x180056e80  call    ??$Call@UIJsonValue@Json@Data@Windows@@P81234@EAAJPEAW4JsonValueType@234@@Z$$V@WinRT@@YA?AW4JsonValueType@Json@Data@Windows@@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@P8IJsonValue@234@EAAJPEAW41234@@Z@Z; WinRT::Call<Windows::Data::Json::IJsonValue,long (Windows::Data::Json::IJsonValue::*)(Windows::Data::Json::JsonValueType *),>(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>,long (Windows::Data::Json::IJsonValue::*)(Windows::Data::Json::JsonValueType *))
0x180056e85  mov     ecx, r15d
0x180056e88  cmp     eax, 5
0x180056e8b  setz    cl
0x180056e8e  movzx   eax, [rsp+100h+var_DE]
0x180056e93  cmp     eax, ecx
0x180056e95  jnz     loc_180056FF8
0x180056e9b  mov     [rsp+100h+var_D8], rbx
0x180056ea0  test    rbx, rbx
0x180056ea3  jz      short loc_180056EB9
0x180056ea5  mov     rax, [rbx]
0x180056ea8  mov     rcx, rbx
0x180056eab  mov     rax, [rax+8]
0x180056eaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056eb4  mov     rbx, [rsp+100h+var_D8]
0x180056eb9  lea     rax, [rsp+100h+var_D8]
0x180056ebe  mov     [rbp+57h+var_90], rax
0x180056ec2  mov     [rbp+57h+string], r15
0x180056ec6  bts     esi, 0Ah
0x180056eca  mov     [rbp+57h+var_D0], esi
0x180056ecd  mov     [rbp+57h+var_80], rbx
0x180056ed1  test    rbx, rbx
0x180056ed4  jz      short loc_180056EE6
0x180056ed6  mov     rax, [rbx]
0x180056ed9  mov     rcx, rbx
0x180056edc  mov     rax, [rax+8]
0x180056ee0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056ee5  nop
0x180056ee6  mov     [rbp+57h+var_88], rbx
0x180056eea  test    rbx, rbx
0x180056eed  jz      short loc_180056EFF
0x180056eef  mov     rax, [rbx]
0x180056ef2  mov     rcx, rbx
0x180056ef5  mov     rax, [rax+8]
0x180056ef9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056efe  nop
0x180056eff  lea     rdx, [rbp+57h+string]
0x180056f03  mov     rcx, rbx
0x180056f06  call    ??_9?$IKeyValuePair_impl@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@$BDA@AA; [thunk]: Windows::Foundation::Collections::IKeyValuePair_impl<HSTRING__ *,Windows::Data::Json::IJsonValue *>::`vcall'{48,{flat}}
0x180056f0b  mov     edi, eax
0x180056f0d  test    rbx, rbx
0x180056f10  jz      short loc_180056F22
0x180056f12  mov     rax, [rbx]
0x180056f15  mov     rcx, rbx
0x180056f18  mov     rax, [rax+10h]
0x180056f1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056f21  nop
0x180056f22  test    rbx, rbx
0x180056f25  jz      short loc_180056F37
0x180056f27  mov     rax, [rbx]
0x180056f2a  mov     rcx, rbx
0x180056f2d  mov     rax, [rax+10h]
0x180056f31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056f36  nop
0x180056f37  test    edi, edi
0x180056f39  js      loc_180057183
0x180056f3f  mov     rcx, [rsp+100h+var_D8]
0x180056f44  test    rcx, rcx
0x180056f47  jz      short loc_180056F5B
0x180056f49  mov     [rsp+100h+var_D8], r15
0x180056f4e  mov     rax, [rcx]
0x180056f51  mov     rax, [rax+10h]
0x180056f55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056f5a  nop
0x180056f5b  btr     esi, 0Ah
0x180056f5f  mov     [rbp+57h+var_D0], esi
0x180056f62  or      esi, 300h
0x180056f68  xor     edx, edx; length
0x180056f6a  mov     rcx, [rbp+57h+string]; string
0x180056f6e  call    cs:__imp_WindowsGetStringRawBuffer
0x180056f74  xorps   xmm0, xmm0
0x180056f77  movups  [rbp+57h+pExceptionObject], xmm0
0x180056f7b  mov     qword ptr [rbp+57h+var_50], r15
0x180056f7f  mov     qword ptr [rbp+57h+var_50+8], r15
0x180056f83  or      r8, 0FFFFFFFFFFFFFFFFh
0x180056f87  inc     r8
0x180056f8a  cmp     [rax+r8*2], r15w
0x180056f8f  jnz     short loc_180056F87
0x180056f91  mov     rdx, rax
0x180056f94  lea     rcx, [rbp+57h+pExceptionObject]
0x180056f98  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180056f9d  nop
0x180056f9e  mov     rdx, [r12+8]
0x180056fa3  cmp     rdx, [r12+10h]
0x180056fa8  jz      short loc_180056FD2
0x180056faa  movups  xmm0, [rbp+57h+pExceptionObject]
0x180056fae  movups  xmmword ptr [rdx], xmm0
0x180056fb1  movups  xmm1, [rbp+57h+var_50]
0x180056fb5  movups  xmmword ptr [rdx+10h], xmm1
0x180056fb9  mov     qword ptr [rbp+57h+var_50], r15
0x180056fbd  mov     qword ptr [rbp+57h+var_50+8], 7
0x180056fc5  mov     word ptr [rbp+57h+pExceptionObject], r15w
0x180056fca  add     qword ptr [r12+8], 20h ; ' '
0x180056fd0  jmp     short loc_180056FDF
0x180056fd2  lea     r8, [rbp+57h+pExceptionObject]
0x180056fd6  mov     rcx, r12
0x180056fd9  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x180056fde  nop
0x180056fdf  lea     rcx, [rbp+57h+pExceptionObject]
0x180056fe3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180056fe8  nop
0x180056fe9  mov     rcx, [rbp+57h+string]; string
0x180056fed  test    rcx, rcx
0x180056ff0  jz      short loc_180056FF8
0x180056ff2  call    cs:__imp_WindowsDeleteString
0x180056ff8  mov     [rsp+100h+var_E0], r15b
0x180056ffd  mov     rcx, [rbp+57h+var_C0]
0x180057001  mov     rax, [rcx]
0x180057004  lea     rdx, [rsp+100h+var_E0]
0x180057009  mov     rax, [rax+40h]
0x18005700d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057012  test    eax, eax
0x180057014  js      loc_18005712F
0x18005701a  jmp     loc_180056D10
0x18005701f  mov     rdx, [rbp+57h+var_98]
0x180057023  test    rdx, rdx
0x180057026  jz      short loc_18005703F
0x180057028  mov     [rbp+57h+var_98], r15
0x18005702c  mov     rax, [rdx]
  ... truncated ...
```
