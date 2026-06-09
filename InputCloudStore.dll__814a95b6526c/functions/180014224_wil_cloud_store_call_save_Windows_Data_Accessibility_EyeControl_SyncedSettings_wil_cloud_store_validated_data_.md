# wil::cloud_store::call_save<Windows::Data::Accessibility::EyeControl::SyncedSettings>(wil::cloud_store::validated_data_reference const &,wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings> const &,unsigned __int64,wil::cloud_store_save_options,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x180014224`
- end: `0x1800144b0`
- name: `??$call_save@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@cloud_store@wil@@AEAA?AVcloud_store_save_result@1@AEBUvalidated_data_reference@01@AEBV?$cloud_store_data@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@1@_KW4cloud_store_save_options@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `652`
- prototype: `wil::cloud_store_save_result *__fastcall(__int64, wil::cloud_store_save_result *, __int64, __int64, __int64, unsigned int, const WCHAR *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001cd78`

## callees

- `0x180003560`
- `0x180009388`
- `0x18001213c`
- `0x180014224`
- `0x180016410`
- `0x18001a5e8`
- `0x18001b128`
- `0x180022b44`
- `0x180022b80`
- `0x180023390`
- `0x180024000`
- `0x180026170`
- `0x180031010`

## pseudocode

```c
wil::cloud_store_save_result *__fastcall wil::cloud_store::call_save<Windows::Data::Accessibility::EyeControl::SyncedSettings>(
        __int64 a1,
        wil::cloud_store_save_result *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6,
        const WCHAR *a7)
{
  PVOID *v10; // rax
  char v11; // bl
  PVOID v12; // rsi
  __int64 cloud_store; // rax
  __int64 v14; // rbx
  __int64 (__fastcall *v15)(__int64, _QWORD, _QWORD *, PVOID); // r13
  struct Windows::Internal::Storage::Cloud::ICloudStoreSaveResult *v16; // rcx
  __int64 v17; // rax
  PVOID v18; // r9
  _QWORD *v19; // r8
  int v20; // eax
  int v22; // [rsp+20h] [rbp-E0h]
  const WCHAR *v23; // [rsp+70h] [rbp-90h] BYREF
  PVOID v24; // [rsp+78h] [rbp-88h] BYREF
  struct Windows::Internal::Storage::Cloud::ICloudStoreSaveResult *v25; // [rsp+80h] [rbp-80h] BYREF
  __int64 v26; // [rsp+88h] [rbp-78h]
  PVOID Reserved1; // [rsp+90h] [rbp-70h] BYREF
  int v28[2]; // [rsp+98h] [rbp-68h]
  PVOID v29; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD *v30; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 v31; // [rsp+C0h] [rbp-40h]
  HSTRING_HEADER v32; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v33; // [rsp+E0h] [rbp-20h]
  HSTRING_HEADER v34; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v35; // [rsp+100h] [rbp+0h]
  HSTRING_HEADER v36; // [rsp+108h] [rbp+8h] BYREF
  __int64 v37; // [rsp+120h] [rbp+20h]
  HSTRING_HEADER v38; // [rsp+128h] [rbp+28h] BYREF
  __int64 v39; // [rsp+140h] [rbp+40h]
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  v26 = a3;
  v23 = a7;
  LODWORD(v24) = 0;
  wil::cloud_store::convert_cloud_store_save_options(a6);
  if ( (a6 & 8) != 0 )
  {
    v24 = 0;
    v10 = &v24;
    v11 = 1;
    v12 = 0;
  }
  else
  {
    v10 = (PVOID *)wil::cloud_store::marshal<wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings>>(
                     &Reserved1,
                     a4);
    v11 = 2;
    v12 = *v10;
  }
  *v10 = 0;
  v29 = v12;
  if ( (v11 & 2) != 0 )
  {
    v11 &= ~2u;
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(&Reserved1);
  }
  if ( (v11 & 1) != 0 )
    wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(&v24);
  v25 = 0;
  cloud_store = wil::details::shared_cloud_store_state::get_cloud_store(*(_QWORD *)a1);
  v14 = *(_QWORD *)cloud_store;
  v15 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD *, PVOID))(**(_QWORD **)cloud_store + 88LL);
  v16 = v25;
  v25 = 0;
  if ( v16 )
    (*(void (__fastcall **)(struct Windows::Internal::Storage::Cloud::ICloudStoreSaveResult *))(*(_QWORD *)v16 + 16LL))(v16);
  v17 = wil::cloud_store::widen_string(&v30, v23);
  v23 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v17);
  Reserved1 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v38, &v23)[1].Reserved.Reserved1;
  v23 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v26 + 64);
  v24 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v36, &v23)[1].Reserved.Reserved1;
  v23 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v26 + 32);
  *(_QWORD *)v28 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v34, &v23)[1].Reserved.Reserved1;
  v23 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v26);
  v18 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v32, &v23)[1].Reserved.Reserved1;
  v19 = *(_QWORD **)(a1 + 24);
  if ( v19 )
    v19 = (_QWORD *)*v19;
  v22 = v28[0];
  v20 = v15(v14, *(unsigned int *)(a1 + 16), v19, v18);
  if ( v20 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x5E4,
      (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
      (const char *)(unsigned int)v20,
      v22);
  v33 = 0;
  v35 = 0;
  v37 = 0;
  v39 = 0;
  if ( v31 > 7 )
    std::_Deallocate<16>(v30, 2 * v31 + 2);
  wil::cloud_store_save_result::cloud_store_save_result(a2, v25);
  wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(&v25);
  wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(&v29);
  return a2;
}

```

## disassembly

```asm
0x180014224  push    rbp
0x180014226  push    rbx
0x180014227  push    rsi
0x180014228  push    rdi
0x180014229  push    r12
0x18001422b  push    r13
0x18001422d  push    r14
0x18001422f  push    r15
0x180014231  lea     rbp, [rsp-58h]
0x180014236  sub     rsp, 158h
0x18001423d  mov     rax, cs:__security_cookie
0x180014244  xor     rax, rsp
0x180014247  mov     [rbp+90h+var_48], rax
0x18001424b  mov     rdi, r9
0x18001424e  mov     [rbp+90h+var_108], r8
0x180014252  mov     r15, rdx
0x180014255  mov     r12, rcx
0x180014258  mov     rax, [rbp+90h+arg_30]
0x18001425f  mov     [rsp+190h+var_120], rax
0x180014264  xor     r13d, r13d
0x180014267  mov     dword ptr [rsp+190h+var_118], r13d
0x18001426c  mov     ecx, [rbp+90h+arg_28]
0x180014272  call    ?convert_cloud_store_save_options@cloud_store@wil@@CA?AW4SaveOptions@Cloud@Storage@Internal@Windows@@W4cloud_store_save_options@2@@Z; wil::cloud_store::convert_cloud_store_save_options(wil::cloud_store_save_options)
0x180014277  mov     r14d, eax
0x18001427a  cmp     [rdi+29h], r13b
0x18001427e  jnz     short loc_180014286
0x180014280  cmp     [rdi+20h], r13
0x180014284  jnz     short loc_18001428A
0x180014286  or      r14d, 8
0x18001428a  test    byte ptr [rbp+90h+arg_28], 8
0x180014291  jz      short loc_1800142A7
0x180014293  mov     [rsp+190h+var_118], r13
0x180014298  lea     rax, [rsp+190h+var_118]
0x18001429d  mov     ebx, 1
0x1800142a2  mov     rsi, r13
0x1800142a5  jmp     short loc_1800142BB
0x1800142a7  mov     rdx, rdi
0x1800142aa  lea     rcx, [rbp+90h+var_100]
0x1800142ae  call    ??$marshal@V?$cloud_store_data@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@wil@@@cloud_store@wil@@CA?AV?$com_ptr_t@UIBuffer@Streams@Storage@Windows@@Uerr_exception_policy@wil@@@1@AEBV?$cloud_store_data@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@1@@Z; wil::cloud_store::marshal<wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings>>(wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings> const &)
0x1800142b3  mov     ebx, 2
0x1800142b8  mov     rsi, [rax]
0x1800142bb  mov     [rax], r13
0x1800142be  mov     [rbp+90h+var_F0], rsi
0x1800142c2  test    bl, 2
0x1800142c5  jz      short loc_1800142D4
0x1800142c7  and     ebx, 0FFFFFFFDh
0x1800142ca  lea     rcx, [rbp+90h+var_100]
0x1800142ce  call    ??1?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(void)
0x1800142d3  nop
0x1800142d4  test    bl, 1
0x1800142d7  jz      short loc_1800142E3
0x1800142d9  lea     rcx, [rsp+190h+var_118]
0x1800142de  call    ??1?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(void)
0x1800142e3  mov     [rbp+90h+var_110], r13
0x1800142e7  mov     rcx, [r12]
0x1800142eb  call    ?get_cloud_store@shared_cloud_store_state@details@wil@@QEAAAEBV?$com_ptr_t@UICloudStore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@3@XZ; wil::details::shared_cloud_store_state::get_cloud_store(void)
0x1800142f0  mov     rbx, [rax]
0x1800142f3  mov     rax, [rbx]
0x1800142f6  mov     r13, [rax+58h]
0x1800142fa  mov     rcx, [rbp+90h+var_110]
0x1800142fe  mov     [rbp+90h+var_110], 0
0x180014306  test    rcx, rcx
0x180014309  jz      short loc_180014318
0x18001430b  mov     rax, [rcx]
0x18001430e  mov     rax, [rax+10h]
0x180014312  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014317  nop
0x180014318  mov     rdx, [rsp+190h+var_120]
0x18001431d  lea     rcx, [rbp+90h+var_E8]
0x180014321  call    ?widen_string@cloud_store@wil@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; wil::cloud_store::widen_string(std::string const &)
0x180014326  nop
0x180014327  mov     rcx, rax
0x18001432a  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001432f  mov     [rsp+190h+var_120], rax
0x180014334  lea     rdx, [rsp+190h+var_120]
0x180014339  lea     rcx, [rbp+90h+var_68]
0x18001433d  call    ??$?0PEB_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x180014342  nop
0x180014343  mov     rax, [rax+18h]
0x180014347  mov     [rbp+90h+var_100], rax
0x18001434b  mov     rdi, [rdi+20h]
0x18001434f  mov     rcx, [rbp+90h+var_108]
0x180014353  add     rcx, 40h ; '@'
0x180014357  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001435c  mov     [rsp+190h+var_120], rax
0x180014361  lea     rdx, [rsp+190h+var_120]
0x180014366  lea     rcx, [rbp+90h+var_88]
0x18001436a  call    ??$?0PEB_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x18001436f  nop
0x180014370  mov     rax, [rax+18h]
0x180014374  mov     [rsp+190h+var_118], rax
0x180014379  mov     rcx, [rbp+90h+var_108]
0x18001437d  add     rcx, 20h ; ' '
0x180014381  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180014386  mov     [rsp+190h+var_120], rax
0x18001438b  lea     rdx, [rsp+190h+var_120]
0x180014390  lea     rcx, [rbp+90h+var_A8]
0x180014394  call    ??$?0PEB_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x180014399  nop
0x18001439a  mov     rax, [rax+18h]
0x18001439e  mov     qword ptr [rbp+90h+var_F8], rax
0x1800143a2  mov     rcx, [rbp+90h+var_108]
0x1800143a6  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800143ab  mov     [rsp+190h+var_120], rax
0x1800143b0  lea     rdx, [rsp+190h+var_120]
0x1800143b5  lea     rcx, [rbp+90h+var_C8]
0x1800143b9  call    ??$?0PEB_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x1800143be  nop
0x1800143bf  mov     r9, [rax+18h]
0x1800143c3  mov     r8, [r12+18h]
0x1800143c8  test    r8, r8
0x1800143cb  jz      short loc_1800143D0
0x1800143cd  mov     r8, [r8]
0x1800143d0  lea     rax, [rbp+90h+var_110]
0x1800143d4  mov     [rsp+190h+var_138], rax
0x1800143d9  mov     rax, [rbp+90h+var_100]
0x1800143dd  mov     [rsp+190h+var_140], rax
0x1800143e2  mov     [rsp+190h+var_148], r14d
0x1800143e7  mov     [rsp+190h+var_150], rsi
0x1800143ec  mov     rax, [rbp+90h+arg_20]
0x1800143f3  mov     [rsp+190h+var_158], rax
0x1800143f8  mov     [rsp+190h+var_160], rdi
0x1800143fd  mov     rax, [rsp+190h+var_118]
0x180014402  mov     [rsp+190h+var_168], rax
0x180014407  mov     rax, qword ptr [rbp+90h+var_F8]
0x18001440b  mov     qword ptr [rsp+190h+var_170], rax; int
0x180014410  mov     edx, [r12+10h]
0x180014415  mov     rcx, rbx
0x180014418  mov     rax, r13
0x18001441b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014420  mov     rcx, [rbp+98h]; this
0x180014427  xor     edx, edx
0x180014429  test    eax, eax
0x18001442b  js      short loc_18001449B
0x18001442d  mov     [rbp+90h+var_B0], rdx
0x180014431  mov     [rbp+90h+var_90], rdx
0x180014435  mov     [rbp+90h+var_70], rdx
0x180014439  mov     [rbp+90h+var_50], rdx
0x18001443d  mov     rdx, [rbp+90h+var_D0]
0x180014441  cmp     rdx, 7
0x180014445  jbe     short loc_180014458
0x180014447  lea     rdx, ds:2[rdx*2]
0x18001444f  mov     rcx, [rbp+90h+var_E8]
0x180014453  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180014458  mov     rdx, [rbp+90h+var_110]; struct Windows::Internal::Storage::Cloud::ICloudStoreSaveResult *
0x18001445c  mov     rcx, r15; this
0x18001445f  call    ??0cloud_store_save_result@wil@@QEAA@PEAUICloudStoreSaveResult@Cloud@Storage@Internal@Windows@@@Z; wil::cloud_store_save_result::cloud_store_save_result(Windows::Internal::Storage::Cloud::ICloudStoreSaveResult *)
0x180014464  nop
0x180014465  lea     rcx, [rbp+90h+var_110]
0x180014469  call    ??1?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(void)
0x18001446e  nop
0x18001446f  lea     rcx, [rbp+90h+var_F0]
0x180014473  call    ??1?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(void)
0x180014478  mov     rax, r15
0x18001447b  mov     rcx, [rbp+90h+var_48]
0x18001447f  xor     rcx, rsp; StackCookie
0x180014482  call    __security_check_cookie
0x180014487  add     rsp, 158h
0x18001448e  pop     r15
0x180014490  pop     r14
0x180014492  pop     r13
0x180014494  pop     r12
0x180014496  pop     rdi
0x180014497  pop     rsi
0x180014498  pop     rbx
0x180014499  pop     rbp
0x18001449a  retn
0x18001449b  mov     r9d, eax; char *
0x18001449e  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x1800144a5  mov     edx, 5E4h; void *
0x1800144aa  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
