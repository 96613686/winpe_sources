# CDPComAppControlHandler::LaunchUri(unsigned __int64,uint,char const *,CDPComAppLocation,uchar const *,uint,unsigned __int64,char const *,char const *)

- ea: `0x1800268e0`
- end: `0x180026b4f`
- name: `?LaunchUri@CDPComAppControlHandler@@UEAAJ_KIPEBDW4CDPComAppLocation@@PEBEI011@Z`
- size: `623`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002a4c`
- `0x1800049f4`
- `0x180004a58`
- `0x18000ecb8`
- `0x180018e38`
- `0x180021398`
- `0x18002194c`
- `0x1800268e0`
- `0x180026bbc`
- `0x180027618`
- `0x180027634`
- `0x18002b614`
- `0x18002c570`
- `0x18004117c`
- `0x18004ab60`
- `0x18004b8f0`
- `0x18004bab4`
- `0x18004bb54`
- `0x180064010`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180026b15`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180026b15`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x180026a7f`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x180026a7f`

## pseudocode

```c
// Hidden C++ exception states: #wind=12 #try_helpers=1
__int64 __fastcall CDPComAppControlHandler::LaunchUri(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 a4,
        int a5,
        __int64 a6,
        unsigned int a7,
        __int64 a8,
        __int64 a9,
        __int64 a10)
{
  unsigned int v13; // edi
  unsigned __int64 v14; // rsi
  __int64 v16; // rax
  __int64 v17; // [rsp+30h] [rbp-168h] BYREF
  __int64 v18; // [rsp+38h] [rbp-160h] BYREF
  int v19; // [rsp+40h] [rbp-158h] BYREF
  __int64 v20; // [rsp+48h] [rbp-150h] BYREF
  _BYTE v21[24]; // [rsp+50h] [rbp-148h] BYREF
  _BYTE v22[16]; // [rsp+68h] [rbp-130h] BYREF
  unsigned __int64 v23; // [rsp+78h] [rbp-120h]
  _BYTE v24[32]; // [rsp+90h] [rbp-108h] BYREF
  _BYTE v25[32]; // [rsp+B0h] [rbp-E8h] BYREF
  _QWORD v26[2]; // [rsp+D0h] [rbp-C8h] BYREF
  int v27; // [rsp+E0h] [rbp-B8h]
  int v28; // [rsp+E4h] [rbp-B4h]
  _BYTE v29[24]; // [rsp+E8h] [rbp-B0h] BYREF
  __int64 v30; // [rsp+100h] [rbp-98h]
  __int64 v31; // [rsp+108h] [rbp-90h]
  __int64 v32; // [rsp+110h] [rbp-88h]
  _BYTE v33[32]; // [rsp+120h] [rbp-78h] BYREF
  _BYTE v34[32]; // [rsp+140h] [rbp-58h] BYREF

  v13 = 0;
  std::string::string((__int64)v22, a4);
  v14 = v23;
  if ( v23 >= 3 )
  {
    v16 = std::_String_val<std::_Simple_types<char>>::_Myptr(v22);
    std::wstring::wstring(v34, v16, v16 + v14);
    std::wstring::wstring(v33, L"ms-appsrv:");
    std::vector<unsigned char>::vector<unsigned char>(v21, a6, a6 + a7);
    v20 = a1;
    Microsoft::WRL::ComPtr<MobilityExperienceResourceHandler>::InternalAddRef(&v20);
    std::wstring::wstring(v24, v34);
    std::wstring::wstring(v25, v33);
    v26[0] = a1;
    Microsoft::WRL::ComPtr<MobilityExperienceResourceHandler>::InternalAddRef(v26);
    v26[1] = a2;
    v27 = a3;
    v28 = a5;
    std::vector<unsigned char>::vector<unsigned char>(v29, v21);
    v30 = a8;
    v31 = a9;
    v32 = a10;
    std::make_unique_std::tuple__lambda_df0a14eb6fce7e52dadd103c1b1a08a5_____lambda_df0a14eb6fce7e52dadd103c1b1a08a5__0_(
      &v17,
      v24);
    v18 = _o__beginthreadex(
            0,
            0,
            std::thread::_Invoke_std::tuple__lambda_df0a14eb6fce7e52dadd103c1b1a08a5____0_,
            v17,
            0,
            &v19);
    if ( v18 )
    {
      v17 = 0;
      std::unique_ptr_std::tuple__lambda_df0a14eb6fce7e52dadd103c1b1a08a5____std::default_delete_std::tuple__lambda_df0a14eb6fce7e52dadd103c1b1a08a5_______::_unique_ptr_std::tuple__lambda_df0a14eb6fce7e52dadd103c1b1a08a5____std::default_delete_std::tuple__lambda_df0a14eb6fce7e52dadd103c1b1a08a5_______(&v17);
      std::thread::detach((std::thread *)&v18);
      std::thread::~thread((std::thread *)&v18);
      lambda_df0a14eb6fce7e52dadd103c1b1a08a5_::__lambda_df0a14eb6fce7e52dadd103c1b1a08a5_(v24);
      if ( a1 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
      std::vector<enum CDPActivityStorePatchField>::_Tidy(v21);
      std::wstring::_Tidy_deallocate(v33);
      std::wstring::_Tidy_deallocate(v34);
      std::string::_Tidy_deallocate(v22);
    }
    else
    {
      v19 = 0;
      std::_Throw_Cpp_error(6);
      return (unsigned int)v17;
    }
    return v13;
  }
  else
  {
    std::string::_Tidy_deallocate(v22);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x1800268e0  mov     [rsp+arg_0], rbx
0x1800268e5  mov     [rsp+arg_8], rsi
0x1800268ea  push    rdi
0x1800268eb  push    r12
0x1800268ed  push    r13
0x1800268ef  push    r14
0x1800268f1  push    r15
0x1800268f3  sub     rsp, 170h
0x1800268fa  mov     rax, cs:__security_cookie
0x180026901  xor     rax, rsp
0x180026904  mov     [rsp+198h+var_38], rax
0x18002690c  mov     r12d, r8d
0x18002690f  mov     r13, rdx
0x180026912  mov     rbx, rcx
0x180026915  mov     r14, [rsp+198h+arg_28]
0x18002691d  mov     r15d, [rsp+198h+arg_30]
0x180026925  xor     edi, edi
0x180026927  mov     rdx, r9
0x18002692a  lea     rcx, [rsp+198h+var_130]
0x18002692f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180026934  nop
0x180026935  mov     rsi, [rsp+198h+var_120]
0x18002693a  cmp     rsi, 3
0x18002693e  jnb     short loc_180026954
0x180026940  lea     rcx, [rsp+198h+var_130]
0x180026945  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18002694a  mov     eax, 80070057h
0x18002694f  jmp     loc_180026B22
0x180026954  lea     rcx, [rsp+198h+var_130]
0x180026959  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18002695e  lea     r8, [rax+rsi]
0x180026962  mov     rdx, rax
0x180026965  lea     rcx, [rsp+198h+var_58]
0x18002696d  call    ??$?0V?$_String_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@std@@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@V?$_String_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@1@0AEBV?$allocator@G@1@@Z; std::wstring::wstring(std::_String_iterator<std::_String_val<std::_Simple_types<char>>>,std::_String_iterator<std::_String_val<std::_Simple_types<char>>>,std::allocator<ushort> const &)
0x180026972  nop
0x180026973  lea     rdx, ?RemoteAppContractLaunchScheme@@3QBGB; "ms-appsrv:"
0x18002697a  lea     rcx, [rsp+198h+var_78]
0x180026982  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180026987  nop
0x180026988  lea     r8, [r14+r15]
0x18002698c  mov     rdx, r14
0x18002698f  lea     rcx, [rsp+198h+var_148]
0x180026994  call    ??$?0PEBE$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@PEBE0AEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(uchar const *,uchar const *,std::allocator<uchar> const &)
0x180026999  nop
0x18002699a  mov     [rsp+198h+var_150], rbx
0x18002699f  lea     rcx, [rsp+198h+var_150]
0x1800269a4  call    ?InternalAddRef@?$ComPtr@VMobilityExperienceResourceHandler@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<MobilityExperienceResourceHandler>::InternalAddRef(void)
0x1800269a9  nop
0x1800269aa  lea     rdx, [rsp+198h+var_58]
0x1800269b2  lea     rcx, [rsp+198h+var_108]
0x1800269ba  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800269bf  nop
0x1800269c0  lea     rdx, [rsp+198h+var_78]
0x1800269c8  lea     rcx, [rsp+198h+var_E8]
0x1800269d0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800269d5  nop
0x1800269d6  mov     [rsp+198h+var_C8], rbx
0x1800269de  lea     rcx, [rsp+198h+var_C8]
0x1800269e6  call    ?InternalAddRef@?$ComPtr@VMobilityExperienceResourceHandler@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<MobilityExperienceResourceHandler>::InternalAddRef(void)
0x1800269eb  nop
0x1800269ec  mov     [rsp+198h+var_C0], r13
0x1800269f4  mov     [rsp+198h+var_B8], r12d
0x1800269fc  mov     eax, [rsp+198h+arg_20]
0x180026a03  mov     [rsp+198h+var_B4], eax
0x180026a0a  lea     rdx, [rsp+198h+var_148]
0x180026a0f  lea     rcx, [rsp+198h+var_B0]
0x180026a17  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@AEBV01@@Z; std::vector<uchar>::vector<uchar>(std::vector<uchar> const &)
0x180026a1c  mov     rax, [rsp+198h+arg_38]
0x180026a24  mov     [rsp+198h+var_98], rax
0x180026a2c  mov     rax, [rsp+198h+arg_40]
0x180026a34  mov     [rsp+198h+var_90], rax
0x180026a3c  mov     rax, [rsp+198h+arg_48]
0x180026a44  mov     [rsp+198h+var_88], rax
0x180026a4c  lea     rdx, [rsp+198h+var_108]
0x180026a54  lea     rcx, [rsp+198h+var_168]
0x180026a59  call    std__make_unique_std__tuple__lambda_df0a14eb6fce7e52dadd103c1b1a08a5_____lambda_df0a14eb6fce7e52dadd103c1b1a08a5__0_
0x180026a5e  nop
0x180026a5f  lea     rax, [rsp+198h+var_158]
0x180026a64  mov     [rsp+198h+var_170], rax
0x180026a69  xor     esi, esi
0x180026a6b  mov     [rsp+198h+var_178], esi
0x180026a6f  mov     r9, [rsp+198h+var_168]
0x180026a74  lea     r8, std__thread___Invoke_std__tuple__lambda_df0a14eb6fce7e52dadd103c1b1a08a5____0_
0x180026a7b  xor     edx, edx
0x180026a7d  xor     ecx, ecx
0x180026a7f  call    cs:__imp__o__beginthreadex
0x180026a85  mov     [rsp+198h+var_160], rax
0x180026a8a  test    rax, rax
0x180026a8d  jz      short loc_180026B0C
0x180026a8f  mov     [rsp+198h+var_168], rsi
0x180026a94  lea     rcx, [rsp+198h+var_168]
0x180026a99  call    std__unique_ptr_std__tuple__lambda_df0a14eb6fce7e52dadd103c1b1a08a5____std__default_delete_std__tuple__lambda_df0a14eb6fce7e52dadd103c1b1a08a5__________unique_ptr_std__tuple__lambda_df0a14eb6fce7e52dadd103c1b1a08a5____std__default_delete_std__tuple__lambda_df0a14eb6fce7e52dadd103c1b1a08a5_______
0x180026a9e  nop
0x180026a9f  lea     rcx, [rsp+198h+var_160]; this
0x180026aa4  call    ?detach@thread@std@@QEAAXXZ; std::thread::detach(void)
0x180026aa9  nop
0x180026aaa  lea     rcx, [rsp+198h+var_160]; this
0x180026aaf  call    ??1thread@std@@QEAA@XZ; std::thread::~thread(void)
0x180026ab4  nop
0x180026ab5  lea     rcx, [rsp+198h+var_108]
0x180026abd  call    _lambda_df0a14eb6fce7e52dadd103c1b1a08a5_____lambda_df0a14eb6fce7e52dadd103c1b1a08a5_
0x180026ac2  nop
0x180026ac3  test    rbx, rbx
0x180026ac6  jz      short loc_180026AD8
0x180026ac8  mov     rax, [rbx]
0x180026acb  mov     rcx, rbx
0x180026ace  mov     rax, [rax+10h]
0x180026ad2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026ad7  nop
0x180026ad8  lea     rcx, [rsp+198h+var_148]
0x180026add  call    ?_Tidy@?$vector@W4CDPActivityStorePatchField@@V?$allocator@W4CDPActivityStorePatchField@@@std@@@std@@AEAAXXZ; std::vector<CDPActivityStorePatchField>::_Tidy(void)
0x180026ae2  nop
0x180026ae3  lea     rcx, [rsp+198h+var_78]
0x180026aeb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180026af0  nop
0x180026af1  lea     rcx, [rsp+198h+var_58]
0x180026af9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180026afe  nop
0x180026aff  lea     rcx, [rsp+198h+var_130]
0x180026b04  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180026b09  nop
0x180026b0a  jmp     short loc_180026B20
0x180026b0c  mov     [rsp+198h+var_158], esi
0x180026b10  mov     ecx, 6
0x180026b15  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180026b1b  nop
0x180026b1c  mov     edi, dword ptr [rsp+198h+var_168]
0x180026b20  mov     eax, edi
0x180026b22  mov     rcx, [rsp+198h+var_38]
0x180026b2a  xor     rcx, rsp; StackCookie
0x180026b2d  call    __security_check_cookie
0x180026b32  lea     r11, [rsp+198h+var_28]
0x180026b3a  mov     rbx, [r11+30h]
0x180026b3e  mov     rsi, [r11+38h]
0x180026b42  mov     rsp, r11
0x180026b45  pop     r15
0x180026b47  pop     r14
0x180026b49  pop     r13
0x180026b4b  pop     r12
0x180026b4d  pop     rdi
0x180026b4e  retn
```
