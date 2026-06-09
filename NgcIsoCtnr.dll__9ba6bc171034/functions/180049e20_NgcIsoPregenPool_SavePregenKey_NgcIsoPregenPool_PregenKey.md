# NgcIsoPregenPool::SavePregenKey(NgcIsoPregenPool::PregenKey &)

- ea: `0x180049e20`
- end: `0x18004a0d8`
- name: `?SavePregenKey@NgcIsoPregenPool@@AEAAJAEAUPregenKey@1@@Z`
- size: `696`
- prototype: `__int64 __fastcall(NgcIsoPregenPool *__hidden this, struct NgcIsoPregenPool::PregenKey *)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004c148`

## callees

- `0x180007670`
- `0x18000d62c`
- `0x180011c5c`
- `0x180011c9c`
- `0x180017f94`
- `0x18001cb98`
- `0x18001cbc8`
- `0x18001cbe8`
- `0x18001d624`
- `0x18002c63c`
- `0x18002e12c`
- `0x1800404a4`
- `0x1800406b4`
- `0x180047f30`
- `0x180048464`
- `0x180049e20`
- `0x18004a0e0`
- `0x180056fb4`
- `0x18006930c`
- `0x1800713cc`
- `0x180072dfc`
- `0x180073e68`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049f31`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004a0a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049f31`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004a0a5`

## string_xrefs

- `0x180049f94`: `.json`
- `0x180049e71`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\pregenpool.cpp`
- `0x180049e9a`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\pregenpool.cpp`
- `0x180049f08`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\pregenpool.cpp`
- `0x180049ffe`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\pregenpool.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall NgcIsoPregenPool::SavePregenKey(NgcIsoPregenPool *this, struct NgcIsoPregenPool::PregenKey *a2)
{
  int v4; // eax
  int v5; // ebx
  int v6; // eax
  unsigned int v7; // r8d
  HLOCAL v8; // rcx
  __int64 v9; // rdx
  int v10; // eax
  __int64 v11; // rdx
  const WCHAR *v12; // rax
  const unsigned __int16 *v13; // rdx
  const unsigned __int16 *v14; // r8
  HLOCAL v15; // rcx
  int v17; // [rsp+20h] [rbp-E0h]
  int v18; // [rsp+20h] [rbp-E0h]
  unsigned int *v19; // [rsp+28h] [rbp-D8h]
  HLOCAL hMem; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int8 *v21; // [rsp+38h] [rbp-C8h] BYREF
  HLOCAL *p_hMem; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v23[2]; // [rsp+48h] [rbp-B8h] BYREF
  char v24; // [rsp+50h] [rbp-B0h]
  _OWORD v25[2]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v26[16]; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int8 *v27; // [rsp+88h] [rbp-78h]
  _BYTE v28[40]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v29[16]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v30[32]; // [rsp+D0h] [rbp-30h] BYREF
  NgcUtils *v31; // [rsp+F0h] [rbp-10h] BYREF
  int v32; // [rsp+F8h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]

  Properties::SerializedPregenKey::SerializedPregenKey((Properties::SerializedPregenKey *)v29);
  v4 = NgcIsoTrustlet::SerializePregenKey((char *)a2 + 32, v29, &v31);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x21F,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\pregenpool.cpp",
      (const char *)(unsigned int)v4,
      v17);
    goto LABEL_17;
  }
  v6 = NgcIsoPregenPool::SaveTpmCounterStore(this);
  if ( v6 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x220,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\pregenpool.cpp",
      (const char *)(unsigned int)v6,
      v17);
  hMem = 0;
  LODWORD(v21) = 0;
  p_hMem = &hMem;
  *(_QWORD *)v23 = 0;
  v24 = 1;
  v5 = NgcUtils::ProtectData(
         v31,
         (const unsigned __int8 *)(unsigned int)(v32 - (_DWORD)v31),
         v7,
         (unsigned int)v23,
         &v21,
         v19);
  wil::details::out_param_t<wistd::unique_ptr<_CERT_PUBLIC_KEY_INFO,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CERT_PUBLIC_KEY_INFO,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22C,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\pregenpool.cpp",
      (const char *)(unsigned int)v5,
      v18);
    goto LABEL_7;
  }
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Assign_counted_range<unsigned char const *>(
    &v31,
    hMem,
    (unsigned int)v21);
  std::wstring::operator=(v30, a2);
  LOBYTE(p_hMem) = 0;
  *(_QWORD *)v23 = 0;
  Properties::to_json(&p_hMem, v29);
  nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::dump(
    &p_hMem,
    v26);
  LOBYTE(v9) = (_BYTE)p_hMem;
  nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
    v23,
    v9);
  std::operator+<unsigned short>(v28, a2, L".json");
  p_hMem = (HLOCAL *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 8);
  *(_QWORD *)v23 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v28);
  v25[0] = 0;
  v25[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v25[0]) = 0;
  v10 = NgcUtils::ComposePath(&p_hMem, 2, v25);
  v5 = v10;
  if ( v10 < 0 )
  {
    v11 = 580;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\pregenpool.cpp",
      (const char *)(unsigned int)v10,
      v18);
    std::wstring::_Tidy_deallocate(v25);
    std::wstring::_Tidy_deallocate(v28);
    std::string::_Tidy_deallocate(v26);
LABEL_7:
    v8 = hMem;
    hMem = 0;
    if ( v8 )
      LocalFree(v8);
    goto LABEL_17;
  }
  std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 8);
  std::_String_val<std::_Simple_types<char>>::_Myptr(v26);
  v12 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v25);
  v10 = NgcUtils::WriteFileSynchronously(v12, v13, v14, (const unsigned __int8 *)(unsigned int)v27);
  v5 = v10;
  if ( v10 < 0 )
  {
    v11 = 586;
    goto LABEL_11;
  }
  std::wstring::_Tidy_deallocate(v25);
  std::wstring::_Tidy_deallocate(v28);
  std::string::_Tidy_deallocate(v26);
  v15 = hMem;
  hMem = 0;
  if ( v15 )
    LocalFree(v15);
  v5 = 0;
LABEL_17:
  Properties::SerializedPregenKey::~SerializedPregenKey((Properties::SerializedPregenKey *)v29);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180049e20  mov     [rsp-8+arg_10], rbx
0x180049e25  push    rbp
0x180049e26  push    rsi
0x180049e27  push    r14
0x180049e29  lea     rbp, [rsp-20h]
0x180049e2e  sub     rsp, 120h
0x180049e35  mov     rax, cs:__security_cookie
0x180049e3c  xor     rax, rsp
0x180049e3f  mov     [rbp+30h+var_20], rax
0x180049e43  mov     r14, rdx
0x180049e46  mov     rsi, rcx
0x180049e49  lea     rcx, [rbp+30h+var_70]; this
0x180049e4d  call    ??0SerializedPregenKey@Properties@@QEAA@XZ; Properties::SerializedPregenKey::SerializedPregenKey(void)
0x180049e52  nop
0x180049e53  lea     rcx, [r14+20h]
0x180049e57  lea     r8, [rbp+30h+var_40]
0x180049e5b  lea     rdx, [rbp+30h+var_70]
0x180049e5f  call    ?SerializePregenKey@NgcIsoTrustlet@@YAJPEAPEAXPEAU_GUID@@PEAV?$vector@EU?$secure_allocator@E@wil@@@std@@@Z; NgcIsoTrustlet::SerializePregenKey(void * *,_GUID *,std::vector<uchar,wil::secure_allocator<uchar>> *)
0x180049e64  mov     ebx, eax
0x180049e66  test    eax, eax
0x180049e68  jns     short loc_180049E87
0x180049e6a  mov     rcx, [rbp+38h]; this
0x180049e6e  mov     r9d, eax; char *
0x180049e71  lea     r8, aOnecoreDsSecur_29; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x180049e78  mov     edx, 21Fh; void *
0x180049e7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049e82  jmp     loc_18004A0AD
0x180049e87  mov     rcx, rsi; this
0x180049e8a  call    ?SaveTpmCounterStore@NgcIsoPregenPool@@QEAAJXZ; NgcIsoPregenPool::SaveTpmCounterStore(void)
0x180049e8f  mov     rcx, [rbp+38h]; this
0x180049e93  test    eax, eax
0x180049e95  jns     short loc_180049EAB
0x180049e97  mov     r9d, eax; char *
0x180049e9a  lea     r8, aOnecoreDsSecur_29; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x180049ea1  mov     edx, 220h; void *
0x180049ea6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180049eab  mov     [rsp+130h+hMem], 0
0x180049eb4  mov     dword ptr [rsp+130h+var_F8], 0
0x180049ebc  lea     rax, [rsp+130h+hMem]
0x180049ec1  mov     [rsp+130h+var_F0], rax
0x180049ec6  mov     qword ptr [rsp+130h+var_E8], 0
0x180049ecf  mov     [rsp+130h+var_E0], 1
0x180049ed4  mov     rcx, [rbp+30h+var_40]; this
0x180049ed8  mov     edx, [rbp+30h+var_38]
0x180049edb  sub     edx, ecx; unsigned __int8 *
0x180049edd  lea     rax, [rsp+130h+var_F8]
0x180049ee2  mov     [rsp+130h+var_110], rax; unsigned int
0x180049ee7  lea     r9, [rsp+130h+var_E8]; unsigned int
0x180049eec  call    ?ProtectData@NgcUtils@@YAJPEBEKKPEAPEAEPEAK@Z; NgcUtils::ProtectData(uchar const *,ulong,ulong,uchar * *,ulong *)
0x180049ef1  mov     ebx, eax
0x180049ef3  lea     rcx, [rsp+130h+var_F0]
0x180049ef8  call    ??1?$out_param_t@V?$unique_ptr@U_CERT_PUBLIC_KEY_INFO@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_CERT_PUBLIC_KEY_INFO,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CERT_PUBLIC_KEY_INFO,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180049efd  test    ebx, ebx
0x180049eff  jns     short loc_180049F3C
0x180049f01  mov     rcx, [rbp+38h]; this
0x180049f05  mov     r9d, ebx; char *
0x180049f08  lea     r8, aOnecoreDsSecur_29; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x180049f0f  mov     edx, 22Ch; void *
0x180049f14  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049f19  nop
0x180049f1a  mov     rcx, [rsp+130h+hMem]; hMem
0x180049f1f  mov     [rsp+130h+hMem], 0
0x180049f28  test    rcx, rcx
0x180049f2b  jz      loc_18004A0AD
0x180049f31  call    cs:__imp_LocalFree
0x180049f37  jmp     loc_18004A0AD
0x180049f3c  mov     rdx, [rsp+130h+hMem]
0x180049f41  mov     r8d, dword ptr [rsp+130h+var_F8]
0x180049f46  lea     rcx, [rbp+30h+var_40]
0x180049f4a  call    ??$_Assign_counted_range@PEBE@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXPEBE_K@Z; std::vector<uchar,wil::secure_allocator<uchar>>::_Assign_counted_range<uchar const *>(uchar const *,unsigned __int64)
0x180049f4f  mov     rdx, r14
0x180049f52  lea     rcx, [rbp+30h+var_60]
0x180049f56  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180049f5b  mov     byte ptr [rsp+130h+var_F0], 0
0x180049f60  xor     eax, eax
0x180049f62  mov     qword ptr [rsp+130h+var_E8], rax
0x180049f67  lea     rdx, [rbp+30h+var_70]
0x180049f6b  lea     rcx, [rsp+130h+var_F0]
0x180049f70  call    ?to_json@Properties@@YAXAEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@AEBUSerializedPregenKey@1@@Z; Properties::to_json(nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>> &,Properties::SerializedPregenKey const &)
0x180049f75  nop
0x180049f76  lea     rdx, [rsp+130h+var_B8]
0x180049f7b  lea     rcx, [rsp+130h+var_F0]
0x180049f80  call    ?dump@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HD_NW4error_handler_t@detail@2@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::dump(int,char,bool,nlohmann::detail::error_handler_t)
0x180049f85  nop
0x180049f86  mov     dl, byte ptr [rsp+130h+var_F0]
0x180049f8a  lea     rcx, [rsp+130h+var_E8]
0x180049f8f  call    ?destroy@json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAXW4value_t@detail@3@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::destroy(nlohmann::detail::value_t)
0x180049f94  lea     r8, aJson_0; ".json"
0x180049f9b  mov     rdx, r14
0x180049f9e  lea     rcx, [rbp+30h+var_98]
0x180049fa2  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x180049fa7  nop
0x180049fa8  lea     rcx, [rsi+8]
0x180049fac  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180049fb1  mov     [rsp+130h+var_F0], rax
0x180049fb6  lea     rcx, [rbp+30h+var_98]
0x180049fba  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180049fbf  mov     qword ptr [rsp+130h+var_E8], rax
0x180049fc4  xorps   xmm0, xmm0
0x180049fc7  movups  [rsp+130h+var_D8], xmm0
0x180049fcc  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180049fd4  movdqu  [rsp+130h+var_C8], xmm1
0x180049fda  xor     eax, eax
0x180049fdc  mov     word ptr [rsp+130h+var_D8], ax
0x180049fe1  lea     r8, [rsp+130h+var_D8]
0x180049fe6  lea     edx, [rax+2]
0x180049fe9  lea     rcx, [rsp+130h+var_F0]
0x180049fee  call    ?ComposePath@NgcUtils@@YAJQEBQEBGKPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; NgcUtils::ComposePath(ushort const * const * const,ulong,std::wstring *)
0x180049ff3  mov     ebx, eax
0x180049ff5  test    eax, eax
0x180049ff7  jns     short loc_18004A036
0x180049ff9  mov     edx, 244h; void *
0x180049ffe  lea     r8, aOnecoreDsSecur_29; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x18004a005  mov     r9d, eax; char *
0x18004a008  mov     rcx, [rbp+38h]; this
0x18004a00c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004a011  nop
0x18004a012  lea     rcx, [rsp+130h+var_D8]
0x18004a017  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004a01c  nop
0x18004a01d  lea     rcx, [rbp+30h+var_98]
0x18004a021  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004a026  nop
0x18004a027  lea     rcx, [rsp+130h+var_B8]
0x18004a02c  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18004a031  jmp     loc_180049F1A
0x18004a036  lea     rcx, [rsi+8]
0x18004a03a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004a03f  mov     rdx, rax
0x18004a042  lea     rcx, [rsp+130h+var_B8]
0x18004a047  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18004a04c  mov     r8, rax
0x18004a04f  lea     rcx, [rsp+130h+var_D8]
0x18004a054  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004a059  mov     rcx, rax; lpNewFileName
0x18004a05c  mov     r9d, dword ptr [rbp+30h+var_A8]; unsigned __int8 *
0x18004a060  call    ?WriteFileSynchronously@NgcUtils@@YAJPEBG0PEBEK@Z; NgcUtils::WriteFileSynchronously(ushort const *,ushort const *,uchar const *,ulong)
0x18004a065  mov     ebx, eax
0x18004a067  test    eax, eax
0x18004a069  jns     short loc_18004A072
0x18004a06b  mov     edx, 24Ah
0x18004a070  jmp     short loc_180049FFE
0x18004a072  lea     rcx, [rsp+130h+var_D8]
0x18004a077  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004a07c  nop
0x18004a07d  lea     rcx, [rbp+30h+var_98]
0x18004a081  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004a086  nop
0x18004a087  lea     rcx, [rsp+130h+var_B8]
0x18004a08c  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18004a091  nop
0x18004a092  mov     rcx, [rsp+130h+hMem]; hMem
0x18004a097  mov     [rsp+130h+hMem], 0
0x18004a0a0  test    rcx, rcx
0x18004a0a3  jz      short loc_18004A0AB
0x18004a0a5  call    cs:__imp_LocalFree
0x18004a0ab  xor     ebx, ebx
0x18004a0ad  lea     rcx, [rbp+30h+var_70]; this
0x18004a0b1  call    ??1SerializedPregenKey@Properties@@QEAA@XZ; Properties::SerializedPregenKey::~SerializedPregenKey(void)
0x18004a0b6  mov     eax, ebx
0x18004a0b8  mov     rcx, [rbp+30h+var_20]
0x18004a0bc  xor     rcx, rsp; StackCookie
0x18004a0bf  call    __security_check_cookie
0x18004a0c4  mov     rbx, [rsp+130h+arg_10]
0x18004a0cc  add     rsp, 120h
0x18004a0d3  pop     r14
0x18004a0d5  pop     rsi
0x18004a0d6  pop     rbp
0x18004a0d7  retn
```
