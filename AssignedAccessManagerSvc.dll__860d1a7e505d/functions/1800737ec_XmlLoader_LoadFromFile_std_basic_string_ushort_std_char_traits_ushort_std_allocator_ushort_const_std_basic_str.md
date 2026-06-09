# XmlLoader::LoadFromFile(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::function<void (std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,long,long,long)> const &,IXMLDOMDocument3 * *)

- ea: `0x1800737ec`
- end: `0x180073a68`
- name: `?LoadFromFile@XmlLoader@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEBV?$function@$$A6AXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@JJJ@Z@3@PEAPEAUIXMLDOMDocument3@@@Z`
- size: `636`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800521fc`

## callees

- `0x180006640`
- `0x18000b6b4`
- `0x18000cfe4`
- `0x180010c98`
- `0x18002001c`
- `0x18002249c`
- `0x1800271c4`
- `0x18006aa3c`
- `0x1800733a4`
- `0x1800737ec`
- `0x180073fcc`
- `0x1800743c0`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180073845`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180073845`
- `OLEAUT32!__imp_SysAllocString` at `0x18007390f`
- `OLEAUT32!__imp_SysAllocString` at `0x18007390f`
- `OLEAUT32!__imp_VariantClear` at `0x180073993`
- `OLEAUT32!__imp_VariantClear` at `0x180073993`

## string_xrefs

- `0x180073880`: `onecoreuap\base\embedded\sys\lockdown\utils\lib\xmlutils.cpp`
- `0x18007392a`: `onecoreuap\base\embedded\sys\lockdown\utils\lib\xmlutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall XmlLoader::LoadFromFile(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  HRESULT v8; // eax
  int v9; // ebx
  __int64 v10; // rdx
  const OLECHAR *v11; // rax
  const unsigned __int16 *v12; // rax
  __int64 v13; // rdx
  unsigned __int64 v14; // r9
  LPVOID v15; // rdi
  __int64 (__fastcall *v16)(LPVOID, __int128 *, __int16 *); // rbx
  _variant_t *v17; // rax
  int v18; // eax
  int ppv; // [rsp+20h] [rbp-B1h]
  __int16 v21; // [rsp+30h] [rbp-A1h] BYREF
  LPVOID v22; // [rsp+38h] [rbp-99h] BYREF
  _QWORD v23[2]; // [rsp+40h] [rbp-91h] BYREF
  __int128 v24; // [rsp+50h] [rbp-81h] BYREF
  __int64 v25; // [rsp+60h] [rbp-71h]
  _BYTE v26[64]; // [rsp+70h] [rbp-61h] BYREF
  _OWORD pvarg[3]; // [rsp+B0h] [rbp-21h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+57h]

  v22 = 0;
  v8 = CoCreateInstance(
         &GUID_88d96a05_f192_11d4_a65f_0040963251e5,
         0,
         1u,
         &GUID_2933bf96_7b36_11d2_b20e_00c04f983e60,
         &v22);
  v9 = v8;
  if ( v8 >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v22 + 504LL))(v22, 0);
    v9 = v8;
    if ( v8 < 0 )
    {
      v10 = 50;
      goto LABEL_5;
    }
    v8 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v22 + 544LL))(v22, 0);
    v9 = v8;
    if ( v8 < 0 )
    {
      v10 = 51;
      goto LABEL_5;
    }
    v8 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v22 + 560LL))(v22, 0);
    v9 = v8;
    if ( v8 < 0 )
    {
      v10 = 52;
      goto LABEL_5;
    }
    v8 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v22 + 576LL))(v22, 0xFFFFFFFFLL);
    v9 = v8;
    if ( v8 < 0 )
    {
      v10 = 54;
      goto LABEL_5;
    }
    v21 = 0;
    v11 = (const OLECHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
    v12 = SysAllocString(v11);
    v23[0] = v12;
    if ( v12 )
    {
      v15 = v22;
      v16 = *(__int64 (__fastcall **)(LPVOID, __int128 *, __int16 *))(*(_QWORD *)v22 + 464LL);
      v17 = _variant_t::_variant_t((_variant_t *)pvarg, v12);
      v24 = *(_OWORD *)v17;
      v25 = *((_QWORD *)v17 + 2);
      v9 = v16(v15, &v24, &v21);
      VariantClear((VARIANTARG *)pvarg);
      if ( v9 >= 0 )
      {
        if ( v21
          || (pvarg[2] = 0,
              pvarg[0] = 0,
              pvarg[1] = _mm_load_si128((const __m128i *)&_xmm),
              LOWORD(pvarg[0]) = 0,
              std::function<void (std::wstring,long,long,long)>::function<void (std::wstring,long,long,long)>(v26, a4),
              v9 = XmlParseErrorHelper::Log((XmlParseErrorHelper *)pvarg),
              std::wstring::_Tidy_deallocate(pvarg),
              v9 >= 0) )
        {
          v18 = SetXmlSelectionProperties(a3, v22);
          v9 = v18;
          if ( v18 >= 0 )
          {
            wil::com_ptr_t<Windows::Internal::AssignedAccess::IProfileOperation,wil::err_exception_policy>::copy_to<Windows::Internal::AssignedAccess::IProfileOperation>(
              &v22,
              a5);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v23);
            v9 = 0;
            goto LABEL_24;
          }
          v14 = (unsigned int)v18;
          v13 = 66;
          goto LABEL_15;
        }
        v13 = 63;
      }
      else
      {
        v13 = 60;
      }
    }
    else
    {
      v9 = -2147024882;
      v13 = 57;
    }
    v14 = (unsigned int)v9;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\utils\\lib\\xmlutils.cpp",
      (const char *)v14,
      ppv);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v23);
    goto LABEL_24;
  }
  v10 = 48;
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v10,
    (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\utils\\lib\\xmlutils.cpp",
    (const char *)(unsigned int)v8,
    ppv);
LABEL_24:
  wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v22);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800737ec  push    rbp
0x1800737ee  push    rbx
0x1800737ef  push    rsi
0x1800737f0  push    rdi
0x1800737f1  push    r12
0x1800737f3  push    r14
0x1800737f5  push    r15
0x1800737f7  lea     rbp, [rsp-1Fh]
0x1800737fc  sub     rsp, 0F0h
0x180073803  mov     rax, cs:__security_cookie
0x18007380a  xor     rax, rsp
0x18007380d  mov     [rbp+4Fh+var_40], rax
0x180073811  mov     r15, r9
0x180073814  mov     r14, r8
0x180073817  mov     rdi, rdx
0x18007381a  mov     rsi, [rbp+4Fh+arg_20]
0x18007381e  xor     r12d, r12d
0x180073821  mov     [rsp+120h+var_E8], r12
0x180073826  lea     rax, [rsp+120h+var_E8]
0x18007382b  mov     qword ptr [rsp+120h+ppv], rax; int
0x180073830  lea     r9, _GUID_2933bf96_7b36_11d2_b20e_00c04f983e60; riid
0x180073837  xor     edx, edx; pUnkOuter
0x180073839  lea     r8d, [r12+1]; dwClsContext
0x18007383e  lea     rcx, _GUID_88d96a05_f192_11d4_a65f_0040963251e5; rclsid
0x180073845  call    cs:__imp_CoCreateInstance
0x18007384b  mov     ebx, eax
0x18007384d  test    eax, eax
0x18007384f  jns     short loc_180073858
0x180073851  lea     edx, [r12+30h]
0x180073856  jmp     short loc_180073879
0x180073858  mov     rcx, [rsp+120h+var_E8]
0x18007385d  mov     rax, [rcx]
0x180073860  xor     edx, edx
0x180073862  mov     rax, [rax+1F8h]
0x180073869  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007386e  mov     ebx, eax
0x180073870  test    eax, eax
0x180073872  jns     short loc_180073891
0x180073874  mov     edx, 32h ; '2'; void *
0x180073879  mov     rcx, [rbp+57h]; this
0x18007387d  mov     r9d, eax; char *
0x180073880  lea     r8, aOnecoreuapBase_93; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180073887  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007388c  jmp     loc_180073A3E
0x180073891  mov     rcx, [rsp+120h+var_E8]
0x180073896  mov     rax, [rcx]
0x180073899  xor     edx, edx
0x18007389b  mov     rax, [rax+220h]
0x1800738a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800738a7  mov     ebx, eax
0x1800738a9  test    eax, eax
0x1800738ab  jns     short loc_1800738B4
0x1800738ad  mov     edx, 33h ; '3'
0x1800738b2  jmp     short loc_180073879
0x1800738b4  mov     rcx, [rsp+120h+var_E8]
0x1800738b9  mov     rax, [rcx]
0x1800738bc  xor     edx, edx
0x1800738be  mov     rax, [rax+230h]
0x1800738c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800738ca  mov     ebx, eax
0x1800738cc  test    eax, eax
0x1800738ce  jns     short loc_1800738D7
0x1800738d0  mov     edx, 34h ; '4'
0x1800738d5  jmp     short loc_180073879
0x1800738d7  mov     rcx, [rsp+120h+var_E8]
0x1800738dc  mov     rax, [rcx]
0x1800738df  or      edx, 0FFFFFFFFh
0x1800738e2  mov     rax, [rax+240h]
0x1800738e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800738ee  mov     ebx, eax
0x1800738f0  test    eax, eax
0x1800738f2  jns     short loc_1800738FE
0x1800738f4  mov     edx, 36h ; '6'
0x1800738f9  jmp     loc_180073879
0x1800738fe  mov     [rsp+120h+var_F0], r12w
0x180073904  mov     rcx, rdi
0x180073907  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007390c  mov     rcx, rax; psz
0x18007390f  call    cs:__imp_SysAllocString
0x180073915  mov     [rsp+120h+var_E0], rax
0x18007391a  test    rax, rax
0x18007391d  jnz     short loc_18007394A
0x18007391f  mov     ebx, 8007000Eh
0x180073924  lea     edx, [rax+39h]; void *
0x180073927  mov     r9d, ebx; char *
0x18007392a  lea     r8, aOnecoreuapBase_93; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180073931  mov     rcx, [rbp+57h]; this
0x180073935  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007393a  nop
0x18007393b  lea     rcx, [rsp+120h+var_E0]
0x180073940  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180073945  jmp     loc_180073A3E
0x18007394a  mov     rdi, [rsp+120h+var_E8]
0x18007394f  mov     rcx, [rdi]
0x180073952  mov     rbx, [rcx+1D0h]
0x180073959  mov     rdx, rax; unsigned __int16 *
0x18007395c  lea     rcx, [rbp+4Fh+pvarg]; this
0x180073960  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x180073965  nop
0x180073966  movups  xmm0, xmmword ptr [rax]
0x180073969  movaps  [rsp+120h+var_D0], xmm0
0x18007396e  movsd   xmm1, qword ptr [rax+10h]
0x180073973  movsd   [rbp+4Fh+var_C0], xmm1
0x180073978  lea     r8, [rsp+120h+var_F0]
0x18007397d  lea     rdx, [rsp+120h+var_D0]
0x180073982  mov     rcx, rdi
0x180073985  mov     rax, rbx
0x180073988  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007398d  mov     ebx, eax
0x18007398f  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x180073993  call    cs:__imp_VariantClear
0x180073999  test    ebx, ebx
0x18007399b  jns     short loc_1800739A4
0x18007399d  mov     edx, 3Ch ; '<'
0x1800739a2  jmp     short loc_180073927
0x1800739a4  cmp     [rsp+120h+var_F0], r12w
0x1800739aa  jnz     short loc_180073A03
0x1800739ac  xorps   xmm0, xmm0
0x1800739af  xorps   xmm1, xmm1
0x1800739b2  movdqu  [rbp+4Fh+var_50], xmm1
0x1800739b7  movups  xmmword ptr [rbp+4Fh+pvarg], xmm0
0x1800739bb  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800739c3  movdqu  xmmword ptr [rbp+4Fh+pvarg+10h], xmm1
0x1800739c8  mov     word ptr [rbp+4Fh+pvarg], r12w
0x1800739cd  mov     rdx, r15
0x1800739d0  lea     rcx, [rbp+4Fh+var_B0]
0x1800739d4  call    ??$?0AEBV?$function@$$A6AXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@JJJ@Z@std@@$0A@@?$function@$$A6AXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@JJJ@Z@std@@QEAA@AEBV?$function@$$A6AXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@JJJ@Z@1@@Z; std::function<void (std::wstring,long,long,long)>::function<void (std::wstring,long,long,long)>(std::function<void (std::wstring &,long,long,long)> const &)
0x1800739d9  mov     r8, rax
0x1800739dc  mov     rdx, [rsp+120h+var_E8]
0x1800739e1  lea     rcx, [rbp+4Fh+pvarg]; this
0x1800739e5  call    ?Log@XmlParseErrorHelper@@QEAAJPEAUIXMLDOMDocument3@@V?$function@$$A6AXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@JJJ@Z@std@@@Z; XmlParseErrorHelper::Log(IXMLDOMDocument3 *,std::function<void (std::wstring,long,long,long)>)
0x1800739ea  mov     ebx, eax
0x1800739ec  lea     rcx, [rbp+4Fh+pvarg]
0x1800739f0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800739f5  test    ebx, ebx
0x1800739f7  jns     short loc_180073A03
0x1800739f9  mov     edx, 3Fh ; '?'
0x1800739fe  jmp     loc_180073927
0x180073a03  mov     rdx, [rsp+120h+var_E8]
0x180073a08  mov     rcx, r14
0x180073a0b  call    ?SetXmlSelectionProperties@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUIXMLDOMDocument3@@@Z; SetXmlSelectionProperties(std::wstring const &,IXMLDOMDocument3 *)
0x180073a10  mov     ebx, eax
0x180073a12  test    eax, eax
0x180073a14  jns     short loc_180073A23
0x180073a16  mov     r9d, eax
0x180073a19  mov     edx, 42h ; 'B'
0x180073a1e  jmp     loc_18007392A
0x180073a23  mov     rdx, rsi
0x180073a26  lea     rcx, [rsp+120h+var_E8]
0x180073a2b  call    ??$copy_to@UIProfileOperation@AssignedAccess@Internal@Windows@@@?$com_ptr_t@UIProfileOperation@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEBAXPEAPEAUIProfileOperation@AssignedAccess@Internal@Windows@@@Z; wil::com_ptr_t<Windows::Internal::AssignedAccess::IProfileOperation,wil::err_exception_policy>::copy_to<Windows::Internal::AssignedAccess::IProfileOperation>(Windows::Internal::AssignedAccess::IProfileOperation * *)
0x180073a30  nop
0x180073a31  lea     rcx, [rsp+120h+var_E0]
0x180073a36  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180073a3b  mov     ebx, r12d
0x180073a3e  lea     rcx, [rsp+120h+var_E8]
0x180073a43  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x180073a48  mov     eax, ebx
0x180073a4a  mov     rcx, [rbp+4Fh+var_40]
0x180073a4e  xor     rcx, rsp; StackCookie
0x180073a51  call    __security_check_cookie
0x180073a56  add     rsp, 0F0h
0x180073a5d  pop     r15
0x180073a5f  pop     r14
0x180073a61  pop     r12
0x180073a63  pop     rdi
0x180073a64  pop     rsi
0x180073a65  pop     rbx
0x180073a66  pop     rbp
0x180073a67  retn
```
