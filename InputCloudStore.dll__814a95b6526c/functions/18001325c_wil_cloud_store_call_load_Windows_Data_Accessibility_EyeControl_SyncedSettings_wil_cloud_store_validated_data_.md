# wil::cloud_store::call_load<Windows::Data::Accessibility::EyeControl::SyncedSettings>(wil::cloud_store::validated_data_reference const &,wil::cloud_store_load_options,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x18001325c`
- end: `0x18001344e`
- name: `??$call_load@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@cloud_store@wil@@AEAA?AV?$cloud_store_data@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@1@AEBUvalidated_data_reference@01@W4cloud_store_load_options@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `498`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180021c50`

## callees

- `0x180003560`
- `0x180009388`
- `0x18001213c`
- `0x18001325c`
- `0x180018d24`
- `0x18001b128`
- `0x180022b44`
- `0x180022b80`
- `0x18002333c`
- `0x180024000`
- `0x180026170`
- `0x180031010`

## pseudocode

```c
__int64 __fastcall wil::cloud_store::call_load<Windows::Data::Accessibility::EyeControl::SyncedSettings>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5)
{
  __int64 cloud_store; // rax
  __int64 v10; // rsi
  __int64 (__fastcall *v11)(__int64, _QWORD, __int64, PVOID); // r15
  __int64 v12; // rax
  PVOID v13; // r9
  __int64 *v14; // r8
  __int64 v15; // r8
  int v16; // eax
  int v18; // [rsp+20h] [rbp-E0h]
  __int64 v19; // [rsp+50h] [rbp-B0h] BYREF
  const WCHAR *v20; // [rsp+58h] [rbp-A8h] BYREF
  const WCHAR *v21; // [rsp+60h] [rbp-A0h] BYREF
  int v22[4]; // [rsp+68h] [rbp-98h]
  PVOID Reserved1; // [rsp+78h] [rbp-88h]
  _QWORD *v24; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 v25; // [rsp+98h] [rbp-68h]
  HSTRING_HEADER v26; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v27; // [rsp+B8h] [rbp-48h]
  HSTRING_HEADER v28; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v29; // [rsp+D8h] [rbp-28h]
  HSTRING_HEADER v30; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v31; // [rsp+F8h] [rbp-8h]
  HSTRING_HEADER v32; // [rsp+100h] [rbp+0h] BYREF
  __int64 v33; // [rsp+118h] [rbp+18h]
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  *(_QWORD *)v22 = a2;
  v19 = 0;
  cloud_store = wil::details::shared_cloud_store_state::get_cloud_store(*(_QWORD *)a1);
  v10 = *(_QWORD *)cloud_store;
  v11 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, PVOID))(**(_QWORD **)cloud_store + 72LL);
  v19 = 0;
  v12 = wil::cloud_store::widen_string(&v24, a5);
  v21 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v12);
  Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v32, &v21);
  LODWORD(v21) = wil::cloud_store::convert_cloud_store_load_options(a4);
  v20 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a3 + 64);
  Reserved1 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v30, &v20)[1].Reserved.Reserved1;
  v20 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a3 + 32);
  *(_QWORD *)v22 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v28, &v20)[1].Reserved.Reserved1;
  v20 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a3);
  v13 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v26, &v20)[1].Reserved.Reserved1;
  v14 = *(__int64 **)(a1 + 24);
  if ( v14 )
    v15 = *v14;
  else
    v15 = 0;
  v18 = v22[0];
  v16 = v11(v10, *(unsigned int *)(a1 + 16), v15, v13);
  if ( v16 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x588,
      (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
      (const char *)(unsigned int)v16,
      v18);
  v27 = 0;
  v29 = 0;
  v31 = 0;
  v33 = 0;
  if ( v25 > 7 )
    std::_Deallocate<16>(v24, 2 * v25 + 2);
  wil::cloud_store::unmarshal<Windows::Data::Accessibility::EyeControl::SyncedSettings>(a2, v19, a4);
  wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(&v19);
  return a2;
}

```

## disassembly

```asm
0x18001325c  push    rbp
0x18001325e  push    rbx
0x18001325f  push    rsi
0x180013260  push    rdi
0x180013261  push    r12
0x180013263  push    r13
0x180013265  push    r14
0x180013267  push    r15
0x180013269  lea     rbp, [rsp-38h]
0x18001326e  sub     rsp, 138h
0x180013275  mov     rax, cs:__security_cookie
0x18001327c  xor     rax, rsp
0x18001327f  mov     [rbp+70h+var_50], rax
0x180013283  mov     r14d, r9d
0x180013286  mov     r13, r8
0x180013289  mov     rbx, rdx
0x18001328c  mov     rdi, rcx
0x18001328f  mov     qword ptr [rsp+170h+var_108], rdx
0x180013294  mov     r12, [rbp+70h+arg_20]
0x18001329b  mov     [rsp+170h+var_120], 0
0x1800132a4  mov     rcx, [rcx]
0x1800132a7  call    ?get_cloud_store@shared_cloud_store_state@details@wil@@QEAAAEBV?$com_ptr_t@UICloudStore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@3@XZ; wil::details::shared_cloud_store_state::get_cloud_store(void)
0x1800132ac  mov     rsi, [rax]
0x1800132af  mov     rax, [rsi]
0x1800132b2  mov     r15, [rax+48h]
0x1800132b6  mov     rcx, [rsp+170h+var_120]
0x1800132bb  mov     [rsp+170h+var_120], 0
0x1800132c4  test    rcx, rcx
0x1800132c7  jz      short loc_1800132D6
0x1800132c9  mov     rax, [rcx]
0x1800132cc  mov     rax, [rax+10h]
0x1800132d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800132d5  nop
0x1800132d6  mov     rdx, r12
0x1800132d9  lea     rcx, [rbp+70h+var_F0]
0x1800132dd  call    ?widen_string@cloud_store@wil@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; wil::cloud_store::widen_string(std::string const &)
0x1800132e2  nop
0x1800132e3  mov     rcx, rax
0x1800132e6  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800132eb  mov     [rsp+170h+var_110], rax
0x1800132f0  lea     rdx, [rsp+170h+var_110]
0x1800132f5  lea     rcx, [rbp+70h+var_70]
0x1800132f9  call    ??$?0PEB_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x1800132fe  nop
0x1800132ff  mov     r12, [rax+18h]
0x180013303  mov     ecx, r14d
0x180013306  call    ?convert_cloud_store_load_options@cloud_store@wil@@CA?AW4LoadOptions@Cloud@Storage@Internal@Windows@@W4cloud_store_load_options@2@@Z; wil::cloud_store::convert_cloud_store_load_options(wil::cloud_store_load_options)
0x18001330b  mov     dword ptr [rsp+170h+var_110], eax
0x18001330f  lea     rcx, [r13+40h]
0x180013313  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180013318  mov     [rsp+170h+var_118], rax
0x18001331d  lea     rdx, [rsp+170h+var_118]
0x180013322  lea     rcx, [rbp+70h+var_90]
0x180013326  call    ??$?0PEB_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x18001332b  nop
0x18001332c  mov     rax, [rax+18h]
0x180013330  mov     [rsp+170h+var_F8], rax
0x180013335  lea     rcx, [r13+20h]
0x180013339  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001333e  mov     [rsp+170h+var_118], rax
0x180013343  lea     rdx, [rsp+170h+var_118]
0x180013348  lea     rcx, [rbp+70h+var_B0]
0x18001334c  call    ??$?0PEB_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x180013351  nop
0x180013352  mov     rax, [rax+18h]
0x180013356  mov     qword ptr [rsp+170h+var_108], rax
0x18001335b  mov     rcx, r13
0x18001335e  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180013363  mov     [rsp+170h+var_118], rax
0x180013368  lea     rdx, [rsp+170h+var_118]
0x18001336d  lea     rcx, [rbp+70h+var_D0]
0x180013371  call    ??$?0PEB_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x180013376  nop
0x180013377  mov     r9, [rax+18h]
0x18001337b  mov     r8, [rdi+18h]
0x18001337f  xor     r13d, r13d
0x180013382  test    r8, r8
0x180013385  jz      short loc_18001338C
0x180013387  mov     r8, [r8]
0x18001338a  jmp     short loc_18001338F
0x18001338c  mov     r8, r13
0x18001338f  lea     rax, [rsp+170h+var_120]
0x180013394  mov     [rsp+170h+var_130], rax
0x180013399  mov     [rsp+170h+var_138], r12
0x18001339e  mov     eax, dword ptr [rsp+170h+var_110]
0x1800133a2  mov     [rsp+170h+var_140], eax
0x1800133a6  mov     rax, [rsp+170h+var_F8]
0x1800133ab  mov     [rsp+170h+var_148], rax
0x1800133b0  mov     rax, qword ptr [rsp+170h+var_108]
0x1800133b5  mov     qword ptr [rsp+170h+var_150], rax; int
0x1800133ba  mov     edx, [rdi+10h]
0x1800133bd  mov     rcx, rsi
0x1800133c0  mov     rax, r15
0x1800133c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800133c8  mov     rcx, [rbp+78h]; this
0x1800133cc  test    eax, eax
0x1800133ce  js      short loc_180013439
0x1800133d0  mov     [rbp+70h+var_B8], r13
0x1800133d4  mov     [rbp+70h+var_98], r13
0x1800133d8  mov     [rbp+70h+var_78], r13
0x1800133dc  mov     [rbp+70h+var_58], r13
0x1800133e0  mov     rdx, [rbp+70h+var_D8]
0x1800133e4  cmp     rdx, 7
0x1800133e8  jbe     short loc_1800133FB
0x1800133ea  lea     rdx, ds:2[rdx*2]
0x1800133f2  mov     rcx, [rbp+70h+var_F0]
0x1800133f6  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800133fb  mov     r8d, r14d
0x1800133fe  mov     rdx, [rsp+170h+var_120]
0x180013403  mov     rcx, rbx
0x180013406  call    ??$unmarshal@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@cloud_store@wil@@CA?AV?$cloud_store_data@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@1@PEAUICloudStoreData@Cloud@Storage@Internal@Windows@@W4cloud_store_load_options@1@@Z; wil::cloud_store::unmarshal<Windows::Data::Accessibility::EyeControl::SyncedSettings>(Windows::Internal::Storage::Cloud::ICloudStoreData *,wil::cloud_store_load_options)
0x18001340b  nop
0x18001340c  lea     rcx, [rsp+170h+var_120]
0x180013411  call    ??1?$com_ptr_t@UIWebAccount@Credentials@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Credentials::IWebAccount,wil::err_exception_policy>(void)
0x180013416  mov     rax, rbx
0x180013419  mov     rcx, [rbp+70h+var_50]
0x18001341d  xor     rcx, rsp; StackCookie
0x180013420  call    __security_check_cookie
0x180013425  add     rsp, 138h
0x18001342c  pop     r15
0x18001342e  pop     r14
0x180013430  pop     r13
0x180013432  pop     r12
0x180013434  pop     rdi
0x180013435  pop     rsi
0x180013436  pop     rbx
0x180013437  pop     rbp
0x180013438  retn
0x180013439  mov     r9d, eax; char *
0x18001343c  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x180013443  mov     edx, 588h; void *
0x180013448  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
