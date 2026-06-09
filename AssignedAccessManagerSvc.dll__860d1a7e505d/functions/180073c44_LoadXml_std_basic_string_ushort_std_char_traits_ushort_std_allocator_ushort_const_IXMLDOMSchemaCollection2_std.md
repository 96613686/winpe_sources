# LoadXml(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,IXMLDOMSchemaCollection2 *,std::function<void (std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,long,long,long)> const &,IXMLDOMDocument3 * *)

- ea: `0x180073c44`
- end: `0x180073fc6`
- name: `?LoadXml@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUIXMLDOMSchemaCollection2@@AEBV?$function@$$A6AXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@JJJ@Z@2@PEAPEAUIXMLDOMDocument3@@@Z`
- size: `898`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800736b0`

## callees

- `0x180006640`
- `0x18000b6b4`
- `0x18000cfe4`
- `0x18000f62c`
- `0x180010c98`
- `0x18002001c`
- `0x18002249c`
- `0x180022930`
- `0x180051e2c`
- `0x18005391c`
- `0x1800727e0`
- `0x1800733a4`
- `0x180073464`
- `0x180073c44`
- `0x180073fcc`
- `0x180074144`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180073c9d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180073c9d`
- `OLEAUT32!__imp_VariantClear` at `0x180073cfd`
- `OLEAUT32!__imp_VariantClear` at `0x180073cfd`

## string_xrefs

- `0x180073d0f`: `onecoreuap\base\embedded\sys\lockdown\utils\lib\xmlutils.cpp`
- `0x180073df1`: `onecoreuap\base\embedded\sys\lockdown\utils\lib\xmlutils.cpp`
- `0x180073f01`: `onecoreuap\base\embedded\sys\lockdown\utils\lib\xmlutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall LoadXml(__int64 a1, struct IDispatch *a2, __int64 a3, __int64 a4)
{
  HRESULT v8; // eax
  bool v9; // r8
  int v10; // ebx
  unsigned __int64 v11; // r9
  __int64 v12; // rdx
  LPVOID v13; // rdi
  __int64 (__fastcall *v14)(LPVOID, __int128 *); // rbx
  _variant_t *v15; // rax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  unsigned __int64 v21; // r9
  __int64 v22; // rdx
  LPVOID v23; // rbx
  __int64 (__fastcall *v24)(LPVOID, __int64, __int16 *); // rdi
  const unsigned __int16 *v25; // rax
  _bstr_t *v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // rax
  int v31; // eax
  __int64 v32; // rdx
  __int64 v33; // r8
  unsigned __int64 v34; // r9
  __int64 v35; // rdx
  __int64 v36; // rax
  int ppv; // [rsp+20h] [rbp-E0h]
  __int16 v39; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID v40; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v41[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v42; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v43; // [rsp+60h] [rbp-A0h]
  _BYTE v44[64]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE pvarg[32]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v46; // [rsp+D0h] [rbp-30h]
  _BYTE v47[32]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  v40 = 0;
  v8 = CoCreateInstance(
         &GUID_88d96a05_f192_11d4_a65f_0040963251e5,
         0,
         1u,
         &GUID_2933bf96_7b36_11d2_b20e_00c04f983e60,
         &v40);
  v10 = v8;
  if ( v8 >= 0 )
  {
    if ( a2 )
    {
      v13 = v40;
      v14 = *(__int64 (__fastcall **)(LPVOID, __int128 *))(*(_QWORD *)v40 + 624LL);
      v15 = _variant_t::_variant_t((_variant_t *)pvarg, a2, v9);
      v42 = *(_OWORD *)v15;
      v43 = *((_QWORD *)v15 + 2);
      v10 = v14(v13, &v42);
      VariantClear((VARIANTARG *)pvarg);
      if ( v10 < 0 )
      {
        v11 = (unsigned int)v10;
        v12 = 349;
        goto LABEL_6;
      }
    }
    v16 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v40 + 504LL))(v40, 0);
    v10 = v16;
    if ( v16 < 0 )
    {
      v11 = (unsigned int)v16;
      v12 = 352;
      goto LABEL_6;
    }
    v17 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v40 + 544LL))(v40, 0xFFFFFFFFLL);
    v10 = v17;
    if ( v17 < 0 )
    {
      v11 = (unsigned int)v17;
      v12 = 353;
      goto LABEL_6;
    }
    v18 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v40 + 560LL))(v40, 0);
    v10 = v18;
    if ( v18 < 0 )
    {
      v11 = (unsigned int)v18;
      v12 = 354;
      goto LABEL_6;
    }
    v19 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v40 + 576LL))(v40, 0);
    v10 = v19;
    if ( v19 < 0 )
    {
      v11 = (unsigned int)v19;
      v12 = 355;
      goto LABEL_6;
    }
    v39 = 0;
    std::wstring::wstring(v47, a1);
    v20 = TrimLeadingSpaces(v47);
    v10 = v20;
    if ( v20 < 0 )
    {
      v21 = (unsigned int)v20;
      v22 = 359;
LABEL_17:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v22,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\utils\\lib\\xmlutils.cpp",
        (const char *)v21,
        ppv);
LABEL_18:
      std::wstring::_Tidy_deallocate(v47);
      goto LABEL_36;
    }
    v23 = v40;
    v24 = *(__int64 (__fastcall **)(LPVOID, __int64, __int16 *))(*(_QWORD *)v40 + 520LL);
    v25 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v47);
    v26 = _bstr_t::_bstr_t((_bstr_t *)v41, v25);
    if ( *(_QWORD *)v26 )
      v27 = **(_QWORD **)v26;
    else
      v27 = 0;
    v10 = v24(v23, v27, &v39);
    _bstr_t::_Free((_bstr_t *)v41);
    if ( v10 < 0 )
    {
      v21 = (unsigned int)v10;
      v22 = 361;
      goto LABEL_17;
    }
    if ( !v39 )
    {
      memset(pvarg, 0, sizeof(pvarg));
      v46 = 0;
      std::wstring::wstring(pvarg, v28, v29);
      std::function<void (std::wstring,long,long,long)>::function<void (std::wstring,long,long,long)>(v44, a3);
      v10 = XmlParseErrorHelper::Log((XmlParseErrorHelper *)pvarg);
      std::wstring::_Tidy_deallocate(pvarg);
      if ( v10 < 0 )
      {
        v21 = (unsigned int)v10;
        v22 = 364;
        goto LABEL_17;
      }
    }
    if ( a2 )
    {
      v41[0] = 0;
      v30 = *(_QWORD *)v40;
      v41[0] = 0;
      v31 = (*(__int64 (__fastcall **)(LPVOID, _QWORD *))(v30 + 632))(v40, v41);
      v10 = v31;
      if ( v31 < 0 )
      {
        v34 = (unsigned int)v31;
        v35 = 371;
LABEL_30:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v35,
          (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\utils\\lib\\xmlutils.cpp",
          (const char *)v34,
          ppv);
        wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(v41);
        goto LABEL_18;
      }
      if ( v31 == 1 )
      {
        memset(pvarg, 0, sizeof(pvarg));
        v46 = 0;
        std::wstring::wstring(pvarg, v32, v33);
        v36 = std::function<void (std::wstring,long,long,long)>::function<void (std::wstring,long,long,long)>(v44, a3);
        v10 = XmlParseErrorHelper::Log(pvarg, v41[0], v36);
        std::wstring::_Tidy_deallocate(pvarg);
        if ( v10 < 0 )
        {
          v34 = (unsigned int)v10;
          v35 = 374;
          goto LABEL_30;
        }
      }
      wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(v41);
    }
    wil::com_ptr_t<Windows::Internal::AssignedAccess::IProfileOperation,wil::err_exception_policy>::copy_to<Windows::Internal::AssignedAccess::IProfileOperation>(
      &v40,
      a4);
    std::wstring::_Tidy_deallocate(v47);
    v10 = 0;
    goto LABEL_36;
  }
  v11 = (unsigned int)v8;
  v12 = 346;
LABEL_6:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v12,
    (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\utils\\lib\\xmlutils.cpp",
    (const char *)v11,
    ppv);
LABEL_36:
  wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v40);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180073c44  push    rbp
0x180073c46  push    rbx
0x180073c47  push    rsi
0x180073c48  push    rdi
0x180073c49  push    r12
0x180073c4b  push    r13
0x180073c4d  push    r14
0x180073c4f  push    r15
0x180073c51  lea     rbp, [rsp-18h]
0x180073c56  sub     rsp, 118h
0x180073c5d  mov     rax, cs:__security_cookie
0x180073c64  xor     rax, rsp
0x180073c67  mov     [rbp+50h+var_50], rax
0x180073c6b  mov     r12, r9
0x180073c6e  mov     r15, r8
0x180073c71  mov     rsi, rdx
0x180073c74  mov     r14, rcx
0x180073c77  xor     r13d, r13d
0x180073c7a  mov     [rsp+150h+var_118], r13
0x180073c7f  lea     rax, [rsp+150h+var_118]
0x180073c84  mov     qword ptr [rsp+150h+ppv], rax; int
0x180073c89  lea     r9, _GUID_2933bf96_7b36_11d2_b20e_00c04f983e60; riid
0x180073c90  xor     edx, edx; pUnkOuter
0x180073c92  lea     r8d, [r13+1]; dwClsContext
0x180073c96  lea     rcx, _GUID_88d96a05_f192_11d4_a65f_0040963251e5; rclsid
0x180073c9d  call    cs:__imp_CoCreateInstance
0x180073ca3  mov     ebx, eax
0x180073ca5  test    eax, eax
0x180073ca7  jns     short loc_180073CB3
0x180073ca9  mov     r9d, eax
0x180073cac  mov     edx, 15Ah
0x180073cb1  jmp     short loc_180073D0F
0x180073cb3  test    rsi, rsi
0x180073cb6  jz      short loc_180073D24
0x180073cb8  mov     rdi, [rsp+150h+var_118]
0x180073cbd  mov     rax, [rdi]
0x180073cc0  mov     rbx, [rax+270h]
0x180073cc7  mov     rdx, rsi; struct IDispatch *
0x180073cca  lea     rcx, [rbp+50h+pvarg]; this
0x180073cce  call    ??0_variant_t@@QEAA@PEAUIDispatch@@_N@Z; _variant_t::_variant_t(IDispatch *,bool)
0x180073cd3  nop
0x180073cd4  movups  xmm0, xmmword ptr [rax]
0x180073cd7  movaps  [rsp+150h+var_100], xmm0
0x180073cdc  movsd   xmm1, qword ptr [rax+10h]
0x180073ce1  movsd   [rsp+150h+var_F0], xmm1
0x180073ce7  lea     rdx, [rsp+150h+var_100]
0x180073cec  mov     rcx, rdi
0x180073cef  mov     rax, rbx
0x180073cf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073cf7  mov     ebx, eax
0x180073cf9  lea     rcx, [rbp+50h+pvarg]; pvarg
0x180073cfd  call    cs:__imp_VariantClear
0x180073d03  test    ebx, ebx
0x180073d05  jns     short loc_180073D24
0x180073d07  mov     r9d, ebx; char *
0x180073d0a  mov     edx, 15Dh; void *
0x180073d0f  lea     r8, aOnecoreuapBase_93; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180073d16  mov     rcx, [rbp+58h]; this
0x180073d1a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180073d1f  jmp     loc_180073F9A
0x180073d24  mov     rcx, [rsp+150h+var_118]
0x180073d29  mov     rax, [rcx]
0x180073d2c  xor     edx, edx
0x180073d2e  mov     rax, [rax+1F8h]
0x180073d35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073d3a  mov     ebx, eax
0x180073d3c  test    eax, eax
0x180073d3e  jns     short loc_180073D4A
0x180073d40  mov     r9d, eax
0x180073d43  mov     edx, 160h
0x180073d48  jmp     short loc_180073D0F
0x180073d4a  mov     rcx, [rsp+150h+var_118]
0x180073d4f  mov     rax, [rcx]
0x180073d52  or      edx, 0FFFFFFFFh
0x180073d55  mov     rax, [rax+220h]
0x180073d5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073d61  mov     ebx, eax
0x180073d63  test    eax, eax
0x180073d65  jns     short loc_180073D71
0x180073d67  mov     r9d, eax
0x180073d6a  mov     edx, 161h
0x180073d6f  jmp     short loc_180073D0F
0x180073d71  mov     rcx, [rsp+150h+var_118]
0x180073d76  mov     rax, [rcx]
0x180073d79  xor     edx, edx
0x180073d7b  mov     rax, [rax+230h]
0x180073d82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073d87  mov     ebx, eax
0x180073d89  test    eax, eax
0x180073d8b  jns     short loc_180073D9A
0x180073d8d  mov     r9d, eax
0x180073d90  mov     edx, 162h
0x180073d95  jmp     loc_180073D0F
0x180073d9a  mov     rcx, [rsp+150h+var_118]
0x180073d9f  mov     rax, [rcx]
0x180073da2  xor     edx, edx
0x180073da4  mov     rax, [rax+240h]
0x180073dab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073db0  mov     ebx, eax
0x180073db2  test    eax, eax
0x180073db4  jns     short loc_180073DC3
0x180073db6  mov     r9d, eax
0x180073db9  mov     edx, 163h
0x180073dbe  jmp     loc_180073D0F
0x180073dc3  mov     [rsp+150h+var_120], r13w
0x180073dc9  mov     rdx, r14
0x180073dcc  lea     rcx, [rbp+50h+var_70]
0x180073dd0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180073dd5  nop
0x180073dd6  lea     rcx, [rbp+50h+var_70]
0x180073dda  call    TrimLeadingSpaces
0x180073ddf  mov     ebx, eax
0x180073de1  test    eax, eax
0x180073de3  jns     short loc_180073E0C
0x180073de5  mov     r9d, eax; char *
0x180073de8  mov     edx, 167h; void *
0x180073ded  mov     rcx, [rbp+58h]; this
0x180073df1  lea     r8, aOnecoreuapBase_93; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180073df8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180073dfd  nop
0x180073dfe  lea     rcx, [rbp+50h+var_70]
0x180073e02  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180073e07  jmp     loc_180073F9A
0x180073e0c  mov     rbx, [rsp+150h+var_118]
0x180073e11  mov     rax, [rbx]
0x180073e14  mov     rdi, [rax+208h]
0x180073e1b  lea     rcx, [rbp+50h+var_70]
0x180073e1f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180073e24  mov     rdx, rax; unsigned __int16 *
0x180073e27  lea     rcx, [rsp+150h+var_110]; this
0x180073e2c  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180073e31  nop
0x180073e32  mov     rdx, [rax]
0x180073e35  test    rdx, rdx
0x180073e38  jz      short loc_180073E3F
0x180073e3a  mov     rdx, [rdx]
0x180073e3d  jmp     short loc_180073E42
0x180073e3f  mov     rdx, r13
0x180073e42  lea     r8, [rsp+150h+var_120]
0x180073e47  mov     rcx, rbx
0x180073e4a  mov     rax, rdi
0x180073e4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073e52  mov     ebx, eax
0x180073e54  lea     rcx, [rsp+150h+var_110]; this
0x180073e59  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180073e5e  test    ebx, ebx
0x180073e60  jns     short loc_180073E6C
0x180073e62  mov     r9d, ebx
0x180073e65  mov     edx, 169h
0x180073e6a  jmp     short loc_180073DED
0x180073e6c  cmp     [rsp+150h+var_120], r13w
0x180073e72  jnz     short loc_180073EC7
0x180073e74  xorps   xmm0, xmm0
0x180073e77  movups  xmmword ptr [rbp+50h+pvarg], xmm0
0x180073e7b  movups  xmmword ptr [rbp+50h+pvarg+10h], xmm0
0x180073e7f  movups  [rbp+50h+var_80], xmm0
0x180073e83  lea     rcx, [rbp+50h+pvarg]
0x180073e87  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180073e8c  nop
0x180073e8d  mov     rdx, r15
0x180073e90  lea     rcx, [rsp+150h+var_E0]
0x180073e95  call    ??$?0AEBV?$function@$$A6AXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@JJJ@Z@std@@$0A@@?$function@$$A6AXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@JJJ@Z@std@@QEAA@AEBV?$function@$$A6AXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@JJJ@Z@1@@Z; std::function<void (std::wstring,long,long,long)>::function<void (std::wstring,long,long,long)>(std::function<void (std::wstring &,long,long,long)> const &)
0x180073e9a  mov     r8, rax
0x180073e9d  mov     rdx, [rsp+150h+var_118]
0x180073ea2  lea     rcx, [rbp+50h+pvarg]; this
0x180073ea6  call    ?Log@XmlParseErrorHelper@@QEAAJPEAUIXMLDOMDocument3@@V?$function@$$A6AXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@JJJ@Z@std@@@Z; XmlParseErrorHelper::Log(IXMLDOMDocument3 *,std::function<void (std::wstring,long,long,long)>)
0x180073eab  mov     ebx, eax
0x180073ead  lea     rcx, [rbp+50h+pvarg]
0x180073eb1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180073eb6  test    ebx, ebx
0x180073eb8  jns     short loc_180073EC7
0x180073eba  mov     r9d, ebx
0x180073ebd  mov     edx, 16Ch
0x180073ec2  jmp     loc_180073DED
0x180073ec7  test    rsi, rsi
0x180073eca  jz      loc_180073F80
0x180073ed0  mov     [rsp+150h+var_110], r13
0x180073ed5  mov     rcx, [rsp+150h+var_118]
0x180073eda  mov     rax, [rcx]
0x180073edd  mov     [rsp+150h+var_110], r13
0x180073ee2  lea     rdx, [rsp+150h+var_110]
0x180073ee7  mov     rax, [rax+278h]
0x180073eee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073ef3  mov     ebx, eax
0x180073ef5  test    eax, eax
0x180073ef7  jns     short loc_180073F21
0x180073ef9  mov     r9d, eax; char *
0x180073efc  mov     edx, 173h; void *
0x180073f01  lea     r8, aOnecoreuapBase_93; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180073f08  mov     rcx, [rbp+58h]; this
0x180073f0c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180073f11  nop
0x180073f12  lea     rcx, [rsp+150h+var_110]
0x180073f17  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180073f1c  jmp     loc_180073DFE
0x180073f21  cmp     eax, 1
0x180073f24  jnz     short loc_180073F76
0x180073f26  xorps   xmm0, xmm0
0x180073f29  movups  xmmword ptr [rbp+50h+pvarg], xmm0
0x180073f2d  movups  xmmword ptr [rbp+50h+pvarg+10h], xmm0
0x180073f31  movups  [rbp+50h+var_80], xmm0
0x180073f35  lea     rcx, [rbp+50h+pvarg]
0x180073f39  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180073f3e  nop
0x180073f3f  mov     rdx, r15
0x180073f42  lea     rcx, [rsp+150h+var_E0]
0x180073f47  call    ??$?0AEBV?$function@$$A6AXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@JJJ@Z@std@@$0A@@?$function@$$A6AXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@JJJ@Z@std@@QEAA@AEBV?$function@$$A6AXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@JJJ@Z@1@@Z; std::function<void (std::wstring,long,long,long)>::function<void (std::wstring,long,long,long)>(std::function<void (std::wstring &,long,long,long)> const &)
0x180073f4c  mov     r8, rax
0x180073f4f  mov     rdx, [rsp+150h+var_110]
0x180073f54  lea     rcx, [rbp+50h+pvarg]
0x180073f58  call    ?Log@XmlParseErrorHelper@@QEAAJPEAUIXMLDOMParseError@@V?$function@$$A6AXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@JJJ@Z@std@@@Z; XmlParseErrorHelper::Log(IXMLDOMParseError *,std::function<void (std::wstring,long,long,long)>)
0x180073f5d  mov     ebx, eax
0x180073f5f  lea     rcx, [rbp+50h+pvarg]
0x180073f63  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180073f68  test    ebx, ebx
0x180073f6a  jns     short loc_180073F76
0x180073f6c  mov     r9d, ebx
0x180073f6f  mov     edx, 176h
0x180073f74  jmp     short loc_180073F01
0x180073f76  lea     rcx, [rsp+150h+var_110]
0x180073f7b  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180073f80  mov     rdx, r12
0x180073f83  lea     rcx, [rsp+150h+var_118]
0x180073f88  call    ??$copy_to@UIProfileOperation@AssignedAccess@Internal@Windows@@@?$com_ptr_t@UIProfileOperation@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEBAXPEAPEAUIProfileOperation@AssignedAccess@Internal@Windows@@@Z; wil::com_ptr_t<Windows::Internal::AssignedAccess::IProfileOperation,wil::err_exception_policy>::copy_to<Windows::Internal::AssignedAccess::IProfileOperation>(Windows::Internal::AssignedAccess::IProfileOperation * *)
0x180073f8d  nop
0x180073f8e  lea     rcx, [rbp+50h+var_70]
0x180073f92  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180073f97  mov     ebx, r13d
0x180073f9a  lea     rcx, [rsp+150h+var_118]
0x180073f9f  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180073fa4  mov     eax, ebx
0x180073fa6  mov     rcx, [rbp+50h+var_50]
0x180073faa  xor     rcx, rsp; StackCookie
0x180073fad  call    __security_check_cookie
0x180073fb2  add     rsp, 118h
0x180073fb9  pop     r15
0x180073fbb  pop     r14
0x180073fbd  pop     r13
0x180073fbf  pop     r12
0x180073fc1  pop     rdi
0x180073fc2  pop     rsi
0x180073fc3  pop     rbx
0x180073fc4  pop     rbp
0x180073fc5  retn
```
