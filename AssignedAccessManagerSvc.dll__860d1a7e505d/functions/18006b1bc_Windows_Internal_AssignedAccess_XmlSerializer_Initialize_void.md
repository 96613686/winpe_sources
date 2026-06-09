# Windows::Internal::AssignedAccess::XmlSerializer::Initialize(void)

- ea: `0x18006b1bc`
- end: `0x18006b451`
- name: `?Initialize@XmlSerializer@AssignedAccess@Internal@Windows@@QEAAJXZ`
- size: `661`
- prototype: `__int64 __fastcall(Windows::Internal::AssignedAccess::XmlSerializer *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006817c`

## callees

- `0x180006640`
- `0x18000b6b4`
- `0x180010c98`
- `0x180014a5c`
- `0x18002001c`
- `0x180021514`
- `0x180051e2c`
- `0x18005391c`
- `0x18006aa3c`
- `0x18006b1bc`
- `0x18006b524`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006b228`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006b228`
- `OLEAUT32!__imp_VariantClear` at `0x18006b2c2`
- `OLEAUT32!__imp_VariantClear` at `0x18006b3d9`
- `OLEAUT32!__imp_VariantClear` at `0x18006b2c2`
- `OLEAUT32!__imp_VariantClear` at `0x18006b3d9`

## string_xrefs

- `0x18006b239`: `onecoreuap\base\embedded\sys\lockdown\mdmalert\lib\xmlserializer.cpp`
- `0x18006b403`: `onecoreuap\base\embedded\sys\lockdown\mdmalert\lib\xmlserializer.cpp`
- `0x18006b25e`: `XPath`
- `0x18006b2dd`: `xmlns:`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall Windows::Internal::AssignedAccess::XmlSerializer::Initialize(
        Windows::Internal::AssignedAccess::XmlSerializer *this)
{
  LPVOID *v2; // rdi
  __int64 v3; // rcx
  HRESULT Instance; // ebx
  __int64 v5; // rdx
  LPVOID v6; // rbx
  __int64 (__fastcall *v7)(LPVOID, _QWORD *, _QWORD *); // r14
  _variant_t *v8; // rax
  __int128 v9; // xmm6
  __int64 v10; // xmm7_8
  _QWORD *v11; // rdx
  __int64 v12; // rbx
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  LPVOID v17; // rbx
  __int64 (__fastcall *v18)(LPVOID, _QWORD *, _QWORD *); // rdi
  const unsigned __int16 *v19; // rax
  _variant_t *v20; // rax
  __int128 v21; // xmm6
  __int64 v22; // xmm7_8
  _QWORD *v23; // rdx
  unsigned __int64 v24; // r9
  __int64 v25; // rdx
  int v26; // eax
  int ppv; // [rsp+28h] [rbp-E0h]
  _BYTE v29[8]; // [rsp+38h] [rbp-D0h] BYREF
  _QWORD v30[3]; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v31; // [rsp+58h] [rbp-B0h]
  VARIANTARG pvarg; // [rsp+68h] [rbp-A0h] BYREF
  _BYTE v33[32]; // [rsp+80h] [rbp-88h] BYREF
  _BYTE v34[32]; // [rsp+A0h] [rbp-68h] BYREF
  _BYTE v35[32]; // [rsp+C0h] [rbp-48h] BYREF
  _BYTE v36[32]; // [rsp+E0h] [rbp-28h] BYREF
  _BYTE v37[32]; // [rsp+100h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+160h] [rbp+58h]

  v2 = (LPVOID *)((char *)this + 16);
  v3 = *((_QWORD *)this + 2);
  *v2 = 0;
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  Instance = CoCreateInstance(
               &GUID_88d96a05_f192_11d4_a65f_0040963251e5,
               0,
               1u,
               &GUID_2933bf96_7b36_11d2_b20e_00c04f983e60,
               v2);
  if ( Instance >= 0 )
  {
    v6 = *v2;
    v7 = *(__int64 (__fastcall **)(LPVOID, _QWORD *, _QWORD *))(*(_QWORD *)*v2 + 640LL);
    v8 = _variant_t::_variant_t((_variant_t *)&pvarg, L"XPath");
    v9 = *(_OWORD *)v8;
    v10 = *((_QWORD *)v8 + 2);
    v11 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)v29, L"SelectionLanguage");
    if ( v11 )
      v11 = (_QWORD *)*v11;
    *(_OWORD *)&v30[1] = v9;
    v31 = v10;
    Instance = v7(v6, v11, &v30[1]);
    _bstr_t::_Free((_bstr_t *)v29);
    VariantClear(&pvarg);
    if ( Instance < 0 )
    {
      v5 = 18;
      goto LABEL_5;
    }
    v12 = *((_QWORD *)this + 17);
    v13 = std::wstring::wstring(v37, L"xmlns:");
    v14 = std::operator+<unsigned short>(v36, v13, L"mal");
    v15 = std::operator+<unsigned short>(v35, v14, L"='");
    v16 = std::operator+<unsigned short>(v34, v15, v12);
    std::operator+<unsigned short>(v33, v16, L"'");
    std::wstring::_Tidy_deallocate(v34);
    std::wstring::_Tidy_deallocate(v35);
    std::wstring::_Tidy_deallocate(v36);
    std::wstring::_Tidy_deallocate(v37);
    v17 = *v2;
    v18 = *(__int64 (__fastcall **)(LPVOID, _QWORD *, _QWORD *))(*(_QWORD *)*v2 + 640LL);
    v19 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v33);
    v20 = _variant_t::_variant_t((_variant_t *)&pvarg, v19);
    v21 = *(_OWORD *)v20;
    v22 = *((_QWORD *)v20 + 2);
    v23 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)v29, L"SelectionNamespaces");
    if ( v23 )
      v23 = (_QWORD *)*v23;
    *(_OWORD *)&v30[1] = v21;
    v31 = v22;
    Instance = v18(v17, v23, &v30[1]);
    _bstr_t::_Free((_bstr_t *)v29);
    VariantClear(&pvarg);
    if ( Instance >= 0 )
    {
      v26 = Windows::Internal::AssignedAccess::XmlSerializer::InitializeEventsRootNode(this);
      Instance = v26;
      if ( v26 >= 0 )
      {
        Instance = 0;
        goto LABEL_18;
      }
      v24 = (unsigned int)v26;
      v25 = 21;
    }
    else
    {
      v24 = (unsigned int)Instance;
      v25 = 20;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v25,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\mdmalert\\lib\\xmlserializer.cpp",
      (const char *)v24,
      ppv);
LABEL_18:
    std::wstring::_Tidy_deallocate(v33);
    return (unsigned int)Instance;
  }
  v5 = 17;
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\mdmalert\\lib\\xmlserializer.cpp",
    (const char *)(unsigned int)Instance,
    ppv);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18006b1bc  mov     rax, rsp
0x18006b1bf  mov     [rax+10h], rbx
0x18006b1c3  mov     [rax+18h], rsi
0x18006b1c7  push    rbp
0x18006b1c8  push    rdi
0x18006b1c9  push    r14
0x18006b1cb  lea     rbp, [rax-58h]
0x18006b1cf  sub     rsp, 140h
0x18006b1d6  movaps  xmmword ptr [rax-28h], xmm6
0x18006b1da  movaps  xmmword ptr [rax-38h], xmm7
0x18006b1de  mov     rax, cs:__security_cookie
0x18006b1e5  xor     rax, rsp
0x18006b1e8  mov     [rbp+50h+var_38], rax
0x18006b1ec  mov     rsi, rcx
0x18006b1ef  lea     rdi, [rcx+10h]
0x18006b1f3  mov     rcx, [rdi]
0x18006b1f6  mov     qword ptr [rdi], 0
0x18006b1fd  test    rcx, rcx
0x18006b200  jz      short loc_18006B20F
0x18006b202  mov     rax, [rcx]
0x18006b205  mov     rax, [rax+10h]
0x18006b209  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b20e  nop
0x18006b20f  mov     qword ptr [rsp+150h+ppv], rdi; int
0x18006b214  lea     r9, _GUID_2933bf96_7b36_11d2_b20e_00c04f983e60; riid
0x18006b21b  xor     edx, edx; pUnkOuter
0x18006b21d  lea     r8d, [rdx+1]; dwClsContext
0x18006b221  lea     rcx, _GUID_88d96a05_f192_11d4_a65f_0040963251e5; rclsid
0x18006b228  call    cs:__imp_CoCreateInstance
0x18006b22e  mov     ebx, eax
0x18006b230  test    eax, eax
0x18006b232  jns     short loc_18006B251
0x18006b234  mov     edx, 11h; void *
0x18006b239  lea     r8, aOnecoreuapBase_61; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18006b240  mov     r9d, ebx; char *
0x18006b243  mov     rcx, [rbp+58h]; this
0x18006b247  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006b24c  jmp     loc_18006B421
0x18006b251  mov     rbx, [rdi]
0x18006b254  mov     rax, [rbx]
0x18006b257  mov     r14, [rax+280h]
0x18006b25e  lea     rdx, aXpath; "XPath"
0x18006b265  lea     rcx, [rsp+150h+pvarg]; this
0x18006b26a  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x18006b26f  nop
0x18006b270  movups  xmm6, xmmword ptr [rax]
0x18006b273  movsd   xmm7, qword ptr [rax+10h]
0x18006b278  lea     rdx, aSelectionlangu; "SelectionLanguage"
0x18006b27f  lea     rcx, [rsp+150h+var_120]; this
0x18006b284  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18006b289  nop
0x18006b28a  mov     rdx, [rax]
0x18006b28d  test    rdx, rdx
0x18006b290  jz      short loc_18006B295
0x18006b292  mov     rdx, [rdx]
0x18006b295  movaps  xmmword ptr [rsp+150h+var_118+8], xmm6
0x18006b29a  movsd   [rsp+150h+var_100], xmm7
0x18006b2a0  lea     r8, [rsp+150h+var_118+8]
0x18006b2a5  mov     rcx, rbx
0x18006b2a8  mov     rax, r14
0x18006b2ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b2b0  mov     ebx, eax
0x18006b2b2  lea     rcx, [rsp+150h+var_120]; this
0x18006b2b7  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18006b2bc  nop
0x18006b2bd  lea     rcx, [rsp+150h+pvarg]; pvarg
0x18006b2c2  call    cs:__imp_VariantClear
0x18006b2c8  test    ebx, ebx
0x18006b2ca  jns     short loc_18006B2D6
0x18006b2cc  mov     edx, 12h
0x18006b2d1  jmp     loc_18006B239
0x18006b2d6  mov     rbx, [rsi+88h]
0x18006b2dd  lea     rdx, aXmlns; "xmlns:"
0x18006b2e4  lea     rcx, [rbp+50h+var_58]
0x18006b2e8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006b2ed  nop
0x18006b2ee  lea     r8, aMal; "mal"
0x18006b2f5  mov     rdx, rax
0x18006b2f8  lea     rcx, [rbp+50h+var_78]
0x18006b2fc  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18006b301  nop
0x18006b302  lea     r8, asc_1800ACB2C; "='"
0x18006b309  mov     rdx, rax
0x18006b30c  lea     rcx, [rbp+50h+var_98]
0x18006b310  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18006b315  nop
0x18006b316  mov     r8, rbx
0x18006b319  mov     rdx, rax
0x18006b31c  lea     rcx, [rbp+50h+var_B8]
0x18006b320  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18006b325  nop
0x18006b326  lea     r8, asc_1800ACB34; "'"
0x18006b32d  mov     rdx, rax
0x18006b330  lea     rcx, [rsp+150h+var_D8]
0x18006b335  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18006b33a  nop
0x18006b33b  lea     rcx, [rbp+50h+var_B8]
0x18006b33f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006b344  nop
0x18006b345  lea     rcx, [rbp+50h+var_98]
0x18006b349  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006b34e  nop
0x18006b34f  lea     rcx, [rbp+50h+var_78]
0x18006b353  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006b358  nop
0x18006b359  lea     rcx, [rbp+50h+var_58]
0x18006b35d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006b362  mov     rbx, [rdi]
0x18006b365  mov     rax, [rbx]
0x18006b368  mov     rdi, [rax+280h]
0x18006b36f  lea     rcx, [rsp+150h+var_D8]
0x18006b374  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18006b379  mov     rdx, rax; unsigned __int16 *
0x18006b37c  lea     rcx, [rsp+150h+pvarg]; this
0x18006b381  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x18006b386  nop
0x18006b387  movups  xmm6, xmmword ptr [rax]
0x18006b38a  movsd   xmm7, qword ptr [rax+10h]
0x18006b38f  lea     rdx, aSelectionnames; "SelectionNamespaces"
0x18006b396  lea     rcx, [rsp+150h+var_120]; this
0x18006b39b  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18006b3a0  nop
0x18006b3a1  mov     rdx, [rax]
0x18006b3a4  test    rdx, rdx
0x18006b3a7  jz      short loc_18006B3AC
0x18006b3a9  mov     rdx, [rdx]
0x18006b3ac  movaps  xmmword ptr [rsp+150h+var_118+8], xmm6
0x18006b3b1  movsd   [rsp+150h+var_100], xmm7
0x18006b3b7  lea     r8, [rsp+150h+var_118+8]
0x18006b3bc  mov     rcx, rbx
0x18006b3bf  mov     rax, rdi
0x18006b3c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b3c7  mov     ebx, eax
0x18006b3c9  lea     rcx, [rsp+150h+var_120]; this
0x18006b3ce  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18006b3d3  nop
0x18006b3d4  lea     rcx, [rsp+150h+pvarg]; pvarg
0x18006b3d9  call    cs:__imp_VariantClear
0x18006b3df  test    ebx, ebx
0x18006b3e1  jns     short loc_18006B3ED
0x18006b3e3  mov     r9d, ebx
0x18006b3e6  mov     edx, 14h
0x18006b3eb  jmp     short loc_18006B403
0x18006b3ed  mov     rcx, rsi; this
0x18006b3f0  call    ?InitializeEventsRootNode@XmlSerializer@AssignedAccess@Internal@Windows@@AEAAJXZ; Windows::Internal::AssignedAccess::XmlSerializer::InitializeEventsRootNode(void)
0x18006b3f5  mov     ebx, eax
0x18006b3f7  test    eax, eax
0x18006b3f9  jns     short loc_18006B415
0x18006b3fb  mov     r9d, eax; char *
0x18006b3fe  mov     edx, 15h; void *
0x18006b403  lea     r8, aOnecoreuapBase_61; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18006b40a  mov     rcx, [rbp+58h]; this
0x18006b40e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006b413  jmp     short loc_18006B417
0x18006b415  xor     ebx, ebx
0x18006b417  lea     rcx, [rsp+150h+var_D8]
0x18006b41c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006b421  mov     eax, ebx
0x18006b423  mov     rcx, [rbp+50h+var_38]
0x18006b427  xor     rcx, rsp; StackCookie
0x18006b42a  call    __security_check_cookie
0x18006b42f  lea     r11, [rsp+150h+var_10]
0x18006b437  mov     rbx, [r11+28h]
0x18006b43b  mov     rsi, [r11+30h]
0x18006b43f  movaps  xmm6, xmmword ptr [r11-10h]
0x18006b444  movaps  xmm7, xmmword ptr [r11-20h]
0x18006b449  mov     rsp, r11
0x18006b44c  pop     r14
0x18006b44e  pop     rdi
0x18006b44f  pop     rbp
0x18006b450  retn
```
