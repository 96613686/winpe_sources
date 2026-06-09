# XmlLoader::LoadSchemas(std::vector<std::pair<ushort const *,ushort const *>,std::allocator<std::pair<ushort const *,ushort const *>>> const &,std::function<long (ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)> const &,IXMLDOMSchemaCollection2 * *)

- ea: `0x180073a70`
- end: `0x180073c3c`
- name: `?LoadSchemas@XmlLoader@@AEAAJAEBV?$vector@U?$pair@PEBGPEBG@std@@V?$allocator@U?$pair@PEBGPEBG@std@@@2@@std@@AEBV?$function@$$A6AJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z@3@PEAPEAUIXMLDOMSchemaCollection2@@@Z`
- size: `460`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180073748`

## callees

- `0x18000b6b4`
- `0x18000cfe4`
- `0x180051e2c`
- `0x18005391c`
- `0x180073464`
- `0x180073a70`
- `0x180074260`
- `0x180074630`
- `0x180074640`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180073ae1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180073ae1`
- `OLEAUT32!__imp_VariantClear` at `0x180073ba6`
- `OLEAUT32!__imp_VariantClear` at `0x180073ba6`

## string_xrefs

- `0x180073af4`: `onecoreuap\base\embedded\sys\lockdown\utils\lib\xmlutils.cpp`
- `0x180073bce`: `onecoreuap\base\embedded\sys\lockdown\utils\lib\xmlutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall XmlLoader::LoadSchemas(void *a1, struct IDispatch *a2, __int64 a3, LPVOID *a4)
{
  HRESULT v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rbx
  __int64 v10; // rcx
  __int64 v11; // r14
  int v12; // edi
  bool v13; // r8
  LPVOID v14; // rdi
  __int64 (__fastcall *v15)(LPVOID, _QWORD *, __int128 *); // r12
  _variant_t *v16; // rax
  __int128 v17; // xmm6
  __int64 v18; // xmm7_8
  _QWORD *v19; // rdx
  __int64 v20; // rdx
  LPVOID v21; // rcx
  int v22; // [rsp+28h] [rbp-49h]
  __int128 v23; // [rsp+38h] [rbp-39h] BYREF
  __int64 v24; // [rsp+48h] [rbp-29h]
  VARIANTARG pvarg; // [rsp+58h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D0h] [rbp+5Fh]
  LPVOID ppv; // [rsp+D8h] [rbp+67h] BYREF
  struct IDispatch *v28; // [rsp+E0h] [rbp+6Fh] BYREF
  char v29; // [rsp+F0h] [rbp+7Fh] BYREF

  v28 = a2;
  ppv = a1;
  *a4 = 0;
  if ( qword_1800CFA30 == (void *)qword_1800CFA38 )
    return 0;
  ppv = 0;
  v7 = CoCreateInstance(
         &GUID_88d96a07_f192_11d4_a65f_0040963251e5,
         0,
         1u,
         &GUID_50ea08b0_dd1b_4664_9a50_c2f40f4bd79a,
         &ppv);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v9 = std::vector<std::pair<unsigned short const *,unsigned short const *>>::_Unchecked_begin();
    v11 = std::vector<std::pair<unsigned short const *,unsigned short const *>>::_Unchecked_end();
    while ( v9 != v11 )
    {
      v28 = 0;
      v12 = XmlLoader::ReadSchema(v10, *(_QWORD *)v9, a3, &v28);
      if ( v12 < 0 )
      {
        v20 = 82;
        goto LABEL_14;
      }
      v14 = ppv;
      v15 = *(__int64 (__fastcall **)(LPVOID, _QWORD *, __int128 *))(*(_QWORD *)ppv + 56LL);
      v16 = _variant_t::_variant_t((_variant_t *)&pvarg, v28, v13);
      v17 = *(_OWORD *)v16;
      v18 = *((_QWORD *)v16 + 2);
      v19 = *(_QWORD **)_bstr_t::_bstr_t((_bstr_t *)&v29, *(const unsigned __int16 **)(v9 + 8));
      if ( v19 )
        v19 = (_QWORD *)*v19;
      v23 = v17;
      v24 = v18;
      v12 = v15(v14, v19, &v23);
      _bstr_t::_Free((_bstr_t *)&v29);
      VariantClear(&pvarg);
      if ( v12 < 0 )
      {
        v20 = 83;
LABEL_14:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v20,
          (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\utils\\lib\\xmlutils.cpp",
          (const char *)(unsigned int)v12,
          v22);
        wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v28);
        v8 = v12;
        goto LABEL_19;
      }
      wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v28);
      v9 += 16;
    }
    v21 = ppv;
    if ( ppv )
    {
      *a4 = ppv;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v21 + 8LL))(v21);
    }
    else
    {
      *a4 = 0;
    }
    v8 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4E,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\utils\\lib\\xmlutils.cpp",
      (const char *)(unsigned int)v7,
      v22);
  }
LABEL_19:
  wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&ppv);
  return v8;
}

```

## disassembly

```asm
0x180073a70  mov     rax, rsp
0x180073a73  mov     [rax+10h], rdx
0x180073a77  mov     [rax+8], rcx
0x180073a7b  push    rbp
0x180073a7c  push    rbx
0x180073a7d  push    rsi
0x180073a7e  push    rdi
0x180073a7f  push    r12
0x180073a81  push    r14
0x180073a83  push    r15
0x180073a85  lea     rbp, [rax-5Fh]
0x180073a89  sub     rsp, 90h
0x180073a90  movaps  xmmword ptr [rax-48h], xmm6
0x180073a94  movaps  xmmword ptr [rax-58h], xmm7
0x180073a98  mov     rsi, r9
0x180073a9b  mov     r15, r8
0x180073a9e  mov     qword ptr [r9], 0
0x180073aa5  mov     rax, cs:qword_1800CFA38
0x180073aac  cmp     cs:qword_1800CFA30, rax
0x180073ab3  jnz     short loc_180073ABC
0x180073ab5  xor     eax, eax
0x180073ab7  jmp     loc_180073C1D
0x180073abc  mov     [rbp+57h+ppv], 0
0x180073ac4  lea     rax, [rbp+57h+ppv]
0x180073ac8  mov     [rsp+20h], rax; int
0x180073acd  lea     r9, _GUID_50ea08b0_dd1b_4664_9a50_c2f40f4bd79a; riid
0x180073ad4  xor     edx, edx; pUnkOuter
0x180073ad6  lea     r8d, [rdx+1]; dwClsContext
0x180073ada  lea     rcx, _GUID_88d96a07_f192_11d4_a65f_0040963251e5; rclsid
0x180073ae1  call    cs:__imp_CoCreateInstance
0x180073ae7  mov     ebx, eax
0x180073ae9  test    eax, eax
0x180073aeb  jns     short loc_180073B0A
0x180073aed  mov     rcx, [rbp+5Fh]; this
0x180073af1  mov     r9d, eax; char *
0x180073af4  lea     r8, aOnecoreuapBase_93; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180073afb  mov     edx, 4Eh ; 'N'; void *
0x180073b00  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180073b05  jmp     loc_180073C12
0x180073b0a  call    ?_Unchecked_begin@?$vector@U?$pair@PEBGPEBG@std@@V?$allocator@U?$pair@PEBGPEBG@std@@@2@@std@@QEBAPEBU?$pair@PEBGPEBG@2@XZ; std::vector<std::pair<ushort const *,ushort const *>>::_Unchecked_begin(void)
0x180073b0f  mov     rbx, rax
0x180073b12  call    ?_Unchecked_end@?$vector@U?$pair@PEBGPEBG@std@@V?$allocator@U?$pair@PEBGPEBG@std@@@2@@std@@QEBAPEBU?$pair@PEBGPEBG@2@XZ; std::vector<std::pair<ushort const *,ushort const *>>::_Unchecked_end(void)
0x180073b17  mov     r14, rax
0x180073b1a  cmp     rbx, r14
0x180073b1d  jz      loc_180073BEF
0x180073b23  mov     [rbp+57h+arg_8], 0
0x180073b2b  lea     r9, [rbp+57h+arg_8]
0x180073b2f  mov     r8, r15
0x180073b32  mov     rdx, [rbx]
0x180073b35  call    ?ReadSchema@XmlLoader@@AEAAJPEBGAEBV?$function@$$A6AJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z@std@@PEAPEAUIXMLDOMDocument3@@@Z; XmlLoader::ReadSchema(ushort const *,std::function<long (ushort const *,std::wstring &)> const &,IXMLDOMDocument3 * *)
0x180073b3a  mov     edi, eax
0x180073b3c  test    eax, eax
0x180073b3e  js      loc_180073BC9
0x180073b44  mov     rdi, [rbp+57h+ppv]
0x180073b48  mov     rax, [rdi]
0x180073b4b  mov     r12, [rax+38h]
0x180073b4f  mov     rdx, [rbp+57h+arg_8]; struct IDispatch *
0x180073b53  lea     rcx, [rbp+57h+pvarg]; this
0x180073b57  call    ??0_variant_t@@QEAA@PEAUIDispatch@@_N@Z; _variant_t::_variant_t(IDispatch *,bool)
0x180073b5c  nop
0x180073b5d  movups  xmm6, xmmword ptr [rax]
0x180073b60  movsd   xmm7, qword ptr [rax+10h]
0x180073b65  mov     rdx, [rbx+8]; unsigned __int16 *
0x180073b69  lea     rcx, [rbp+57h+arg_18]; this
0x180073b6d  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180073b72  nop
0x180073b73  mov     rdx, [rax]
0x180073b76  test    rdx, rdx
0x180073b79  jz      short loc_180073B7E
0x180073b7b  mov     rdx, [rdx]
0x180073b7e  movaps  [rbp+57h+var_90], xmm6
0x180073b82  movsd   [rbp+57h+var_80], xmm7
0x180073b87  lea     r8, [rbp+57h+var_90]
0x180073b8b  mov     rcx, rdi
0x180073b8e  mov     rax, r12
0x180073b91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073b96  mov     edi, eax
0x180073b98  lea     rcx, [rbp+57h+arg_18]; this
0x180073b9c  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180073ba1  nop
0x180073ba2  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180073ba6  call    cs:__imp_VariantClear
0x180073bac  test    edi, edi
0x180073bae  js      short loc_180073BC2
0x180073bb0  lea     rcx, [rbp+57h+arg_8]
0x180073bb4  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180073bb9  add     rbx, 10h
0x180073bbd  jmp     loc_180073B1A
0x180073bc2  mov     edx, 53h ; 'S'
0x180073bc7  jmp     short loc_180073BCE
0x180073bc9  mov     edx, 52h ; 'R'; void *
0x180073bce  lea     r8, aOnecoreuapBase_93; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180073bd5  mov     r9d, edi; char *
0x180073bd8  mov     rcx, [rbp+5Fh]; this
0x180073bdc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180073be1  nop
0x180073be2  lea     rcx, [rbp+57h+arg_8]
0x180073be6  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180073beb  mov     ebx, edi
0x180073bed  jmp     short loc_180073C12
0x180073bef  mov     rcx, [rbp+57h+ppv]
0x180073bf3  test    rcx, rcx
0x180073bf6  jz      short loc_180073C09
0x180073bf8  mov     [rsi], rcx
0x180073bfb  mov     rax, [rcx]
0x180073bfe  mov     rax, [rax+8]
0x180073c02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073c07  jmp     short loc_180073C10
0x180073c09  mov     qword ptr [rsi], 0
0x180073c10  xor     ebx, ebx
0x180073c12  lea     rcx, [rbp+57h+ppv]
0x180073c16  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180073c1b  mov     eax, ebx
0x180073c1d  movaps  xmm6, [rsp+0C0h+var_48+8]
0x180073c25  movaps  xmm7, [rsp+0C0h+var_58+8]
0x180073c2a  add     rsp, 90h
0x180073c31  pop     r15
0x180073c33  pop     r14
0x180073c35  pop     r12
0x180073c37  pop     rdi
0x180073c38  pop     rsi
0x180073c39  pop     rbx
0x180073c3a  pop     rbp
0x180073c3b  retn
```
