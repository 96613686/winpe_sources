# Microsoft::Win32::TaskSchedulerWrappers::TaskService::GetOrCreateFolder(ushort *,ushort *)

- ea: `0x14004f338`
- end: `0x14004f618`
- name: `?GetOrCreateFolder@TaskService@TaskSchedulerWrappers@Win32@Microsoft@@QEAA?AUTaskFolder@234@PEAG0@Z`
- size: `736`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14004f620`

## callees

- `0x140016334`
- `0x140016bf8`
- `0x140016e00`
- `0x1400171b4`
- `0x140018f7c`
- `0x140019130`
- `0x1400196d4`
- `0x140019d88`
- `0x140024354`
- `0x140024994`
- `0x14002c708`
- `0x14004c028`
- `0x14004f338`
- `0x1401b9010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x14004f48b`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x14004f48b`
- `OLEAUT32!__imp_SysStringLen` at `0x14004f421`
- `OLEAUT32!__imp_SysStringLen` at `0x14004f421`

## string_xrefs

- `0x14004f3a5`: `onecore\base\fs\refsdedupsvc\svclib\inc\TaskScheduler.h`
- `0x14004f3ff`: `onecore\base\fs\refsdedupsvc\svclib\inc\TaskScheduler.h`
- `0x14004f5b0`: `onecore\base\fs\refsdedupsvc\svclib\inc\TaskScheduler.h`
- `0x14004f5c2`: `onecore\base\fs\refsdedupsvc\svclib\inc\TaskScheduler.h`
- `0x14004f5d7`: `onecore\base\fs\refsdedupsvc\svclib\inc\TaskScheduler.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 *__fastcall Microsoft::Win32::TaskSchedulerWrappers::TaskService::GetOrCreateFolder(
        __int64 **a1,
        __int64 *a2,
        OLECHAR *a3,
        const unsigned __int16 *a4)
{
  __int64 *v8; // rcx
  __int64 v9; // rax
  int v10; // eax
  __int64 *v11; // rdi
  __int64 (__fastcall *v12)(__int64 *, _QWORD, __int64 *); // rbx
  _QWORD *bstr; // rax
  int v14; // eax
  __int64 v15; // r9
  int v16; // eax
  const OLECHAR **v17; // r9
  BSTR v18; // rbx
  const char *v19; // r9
  __int64 v20; // rdi
  unsigned int (__fastcall *v21)(__int64, BSTR, __int64 *); // r14
  __int64 v22; // rcx
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, BSTR, __int128 *, __int64 *); // r14
  __int64 v25; // rcx
  _variant_t *v26; // rax
  int v27; // eax
  __int64 v28; // rcx
  __int64 v29; // rcx
  int v31; // [rsp+20h] [rbp-49h]
  __int64 v32; // [rsp+30h] [rbp-39h] BYREF
  UINT ui[2]; // [rsp+38h] [rbp-31h] BYREF
  _QWORD v34[2]; // [rsp+40h] [rbp-29h] BYREF
  __int128 v35; // [rsp+50h] [rbp-19h] BYREF
  __int128 v36; // [rsp+60h] [rbp-9h] BYREF
  __int64 v37; // [rsp+70h] [rbp+7h]
  _BYTE v38[64]; // [rsp+80h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  *a2 = 0;
  v8 = *a1;
  v9 = *v8;
  *a2 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64 *, OLECHAR *, __int64 *))(v9 + 56))(v8, a3, a2);
  if ( v10 == -2147024894 )
  {
    v32 = 0;
    v11 = *a1;
    v12 = *(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(*v11 + 56);
    v32 = 0;
    bstr = (_QWORD *)wil::make_bstr(v34, L"\\");
    v14 = v12(v11, *bstr, &v32);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x315,
        (unsigned int)"onecore\\base\\fs\\refsdedupsvc\\svclib\\inc\\TaskScheduler.h",
        (const char *)(unsigned int)v14,
        v31);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v34);
    *(_QWORD *)&v35 = a3;
    *((_QWORD *)&v35 + 1) = SysStringLen(a3);
    ___split_string_GV_lambda_1___1__Tokenize___single_char_tokenizer_G_0FM__PathParsing_Microsoft__SA_AU__generator_V__basic_string_view_GU__char_traits_G_std___std__V__allocator_D_2__experimental_std__V__basic_string_view_GU__char_traits_G_std___8__Z__PathParsing_Microsoft__YA_AU__generator_V__basic_string_view_GU__char_traits_G_std___std__V__allocator_D_2__experimental_std__V__basic_string_view_GU__char_traits_G_std___4_V_lambda_1___1__Tokenize___single_char_tokenizer_G_0FM__01_SA_AU234_0_Z__N_Z(
      v34,
      &v35);
    std::experimental::generator<wil::basic_zstring_view<unsigned short>,std::allocator<char>>::begin(v34, &v35);
    while ( (_QWORD)v35 )
    {
      v15 = *(_QWORD *)(v35 - 32);
      ui[0] = 0;
      v16 = LongLongToULong(*(_QWORD *)(v15 + 8), ui);
      if ( v16 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x31A,
          (unsigned int)"onecore\\base\\fs\\refsdedupsvc\\svclib\\inc\\TaskScheduler.h",
          (const char *)(unsigned int)v16,
          v31);
      v18 = SysAllocStringLen(*v17, ui[0]);
      *(_QWORD *)ui = v18;
      if ( !v18 )
        wil::details::in1diag3::_Throw_NullAlloc(
          retaddr,
          (void *)0x31C,
          (unsigned int)"onecore\\base\\fs\\refsdedupsvc\\svclib\\inc\\TaskScheduler.h",
          v19);
      v20 = v32;
      v21 = *(unsigned int (__fastcall **)(__int64, BSTR, __int64 *))(*(_QWORD *)v32 + 72LL);
      v22 = *a2;
      *a2 = 0;
      if ( v22 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      if ( v21(v20, v18, a2) == -2147024894 )
      {
        v23 = v32;
        v24 = *(__int64 (__fastcall **)(__int64, BSTR, __int128 *, __int64 *))(*(_QWORD *)v32 + 88LL);
        v25 = *a2;
        *a2 = 0;
        if ( v25 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
        v26 = _variant_t::_variant_t((_variant_t *)v38, a4);
        v36 = *(_OWORD *)v26;
        v37 = *((_QWORD *)v26 + 2);
        v27 = v24(v23, v18, &v36, a2);
        if ( v27 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x321,
            (unsigned int)"onecore\\base\\fs\\refsdedupsvc\\svclib\\inc\\TaskScheduler.h",
            (const char *)(unsigned int)v27,
            v31);
        _variant_t::~_variant_t((_variant_t *)v38);
      }
      v28 = v32;
      v32 = 0;
      if ( v28 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      v29 = *a2;
      if ( *a2 )
      {
        v32 = *a2;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 8LL))(v29);
      }
      else
      {
        v32 = 0;
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(ui);
      std::experimental::generator<Microsoft::Win32::TaskSchedulerWrappers::RegisteredTask,std::allocator<char>>::iterator::operator++(&v35);
    }
    std::experimental::generator<std::basic_string_view<unsigned short>,std::allocator<char>>::~generator<std::basic_string_view<unsigned short>,std::allocator<char>>(v34);
    wil::com_ptr_t<IAction,wil::err_exception_policy>::~com_ptr_t<IAction,wil::err_exception_policy>(&v32);
  }
  else if ( v10 < 0 )
  {
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x310,
      (unsigned int)"onecore\\base\\fs\\refsdedupsvc\\svclib\\inc\\TaskScheduler.h",
      (const char *)(unsigned int)v10,
      v31);
  }
  return a2;
}

```

## disassembly

```asm
0x14004f338  mov     [rsp-8+arg_10], rbx
0x14004f33d  mov     [rsp-8+arg_8], rdx
0x14004f342  push    rbp
0x14004f343  push    rsi
0x14004f344  push    rdi
0x14004f345  push    r14
0x14004f347  push    r15
0x14004f349  lea     rbp, [rsp-37h]
0x14004f34e  sub     rsp, 0A0h
0x14004f355  mov     r15, r9
0x14004f358  mov     r14, r8
0x14004f35b  mov     rsi, rdx
0x14004f35e  mov     rdi, rcx
0x14004f361  mov     eax, 1
0x14004f366  mov     [rbp+57h+arg_0], eax
0x14004f369  mov     qword ptr [rdx], 0
0x14004f370  mov     [rbp+57h+arg_0], eax
0x14004f373  mov     rcx, [rcx]
0x14004f376  mov     rax, [rcx]
0x14004f379  mov     qword ptr [rdx], 0
0x14004f380  mov     r8, rdx
0x14004f383  mov     rdx, r14
0x14004f386  mov     rax, [rax+38h]
0x14004f38a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f38f  cmp     eax, 80070002h
0x14004f394  jz      short loc_14004F3B7
0x14004f396  mov     rcx, [rbp+5Fh]; this
0x14004f39a  test    eax, eax
0x14004f39c  jns     loc_14004F5FD
0x14004f3a2  mov     r9d, eax; char *
0x14004f3a5  lea     r8, aOnecoreBaseFsR_30; "onecore\\base\\fs\\refsdedupsvc\\svclib"...
0x14004f3ac  mov     edx, 310h; void *
0x14004f3b1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14004f3b7  mov     [rbp+57h+var_90], 0
0x14004f3bf  mov     rdi, [rdi]
0x14004f3c2  mov     rax, [rdi]
0x14004f3c5  mov     rbx, [rax+38h]
0x14004f3c9  mov     [rbp+57h+var_90], 0
0x14004f3d1  lea     rdx, StringValue; "\\"
0x14004f3d8  lea     rcx, [rbp+57h+var_80]
0x14004f3dc  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x14004f3e1  nop
0x14004f3e2  lea     r8, [rbp+57h+var_90]
0x14004f3e6  mov     rdx, [rax]
0x14004f3e9  mov     rcx, rdi
0x14004f3ec  mov     rax, rbx
0x14004f3ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f3f4  mov     rcx, [rbp+5Fh]; this
0x14004f3f8  test    eax, eax
0x14004f3fa  jns     short loc_14004F411
0x14004f3fc  mov     r9d, eax; char *
0x14004f3ff  lea     r8, aOnecoreBaseFsR_30; "onecore\\base\\fs\\refsdedupsvc\\svclib"...
0x14004f406  mov     edx, 315h; void *
0x14004f40b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14004f411  lea     rcx, [rbp+57h+var_80]
0x14004f415  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14004f41a  mov     [rbp+57h+var_70], r14
0x14004f41e  mov     rcx, r14; pbstr
0x14004f421  call    cs:__imp_SysStringLen
0x14004f428  nop     dword ptr [rax+rax+00h]
0x14004f42d  mov     eax, eax
0x14004f42f  mov     [rbp+57h+var_68], rax
0x14004f433  lea     rdx, [rbp+57h+var_70]
0x14004f437  lea     rcx, [rbp+57h+var_80]
0x14004f43b  call    ??$split_string@GV_lambda_1_@?1??Tokenize@?$single_char_tokenizer@G$0FM@@PathParsing@Microsoft@@SA?AU?$generator@V?$basic_string_view@GU?$char_traits@G@std@@@std@@V?$allocator@D@2@@experimental@std@@V?$basic_string_view@GU?$char_traits@G@std@@@8@@Z@@PathParsing@Microsoft@@YA?AU?$generator@V?$basic_string_view@GU?$char_traits@G@std@@@std@@V?$allocator@D@2@@experimental@std@@V?$basic_string_view@GU?$char_traits@G@std@@@4@V_lambda_1_@?1??Tokenize@?$single_char_tokenizer@G$0FM@@01@SA?AU234@0@Z@_N@Z; Microsoft::PathParsing::split_string<ushort,`Microsoft::PathParsing::single_char_tokenizer<ushort,92>::Tokenize(std::basic_string_view<ushort>)'::`2'::_lambda_1_>(std::basic_string_view<ushort>,`Microsoft::PathParsing::single_char_tokenizer<ushort,92>::Tokenize(std::basic_string_view<ushort>)'::`2'::_lambda_1_,bool)
0x14004f440  mov     [rbp+57h+arg_0], 3
0x14004f447  lea     rdx, [rbp+57h+var_70]
0x14004f44b  lea     rcx, [rbp+57h+var_80]
0x14004f44f  call    ?begin@?$generator@V?$basic_zstring_view@G@wil@@V?$allocator@D@std@@@experimental@std@@QEAA?AUiterator@123@XZ; std::experimental::generator<wil::basic_zstring_view<ushort>,std::allocator<char>>::begin(void)
0x14004f454  mov     rax, [rbp+57h+var_70]
0x14004f458  test    rax, rax
0x14004f45b  jz      loc_14004F5E9
0x14004f461  mov     r9, [rax-20h]
0x14004f465  mov     [rbp+57h+ui], 0
0x14004f46c  lea     rdx, [rbp+57h+ui]; unsigned int *
0x14004f470  mov     rcx, [r9+8]; __int64
0x14004f474  call    ?LongLongToULong@@YAJ_JPEAK@Z; LongLongToULong(__int64,ulong *)
0x14004f479  mov     rcx, [rbp+5Fh]; this
0x14004f47d  test    eax, eax
0x14004f47f  js      loc_14004F5D4
0x14004f485  mov     edx, [rbp+57h+ui]; ui
0x14004f488  mov     rcx, [r9]; strIn
0x14004f48b  call    cs:__imp_SysAllocStringLen
0x14004f492  nop     dword ptr [rax+rax+00h]
0x14004f497  mov     rbx, rax
0x14004f49a  mov     qword ptr [rbp+57h+ui], rax
0x14004f49e  mov     rcx, [rbp+5Fh]; this
0x14004f4a2  test    rax, rax
0x14004f4a5  jz      loc_14004F5C2
0x14004f4ab  mov     rdi, [rbp+57h+var_90]
0x14004f4af  mov     rax, [rdi]
0x14004f4b2  mov     r14, [rax+48h]
0x14004f4b6  mov     rcx, [rsi]
0x14004f4b9  mov     qword ptr [rsi], 0
0x14004f4c0  test    rcx, rcx
0x14004f4c3  jz      short loc_14004F4D2
0x14004f4c5  mov     rdx, [rcx]
0x14004f4c8  mov     rax, [rdx+10h]
0x14004f4cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f4d1  nop
0x14004f4d2  mov     r8, rsi
0x14004f4d5  mov     rdx, rbx
0x14004f4d8  mov     rcx, rdi
0x14004f4db  mov     rax, r14
0x14004f4de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f4e3  cmp     eax, 80070002h
0x14004f4e8  jnz     short loc_14004F556
0x14004f4ea  mov     rdi, [rbp+57h+var_90]
0x14004f4ee  mov     rax, [rdi]
0x14004f4f1  mov     r14, [rax+58h]
0x14004f4f5  mov     rcx, [rsi]
0x14004f4f8  mov     qword ptr [rsi], 0
0x14004f4ff  test    rcx, rcx
0x14004f502  jz      short loc_14004F511
0x14004f504  mov     rax, [rcx]
0x14004f507  mov     rax, [rax+10h]
0x14004f50b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f510  nop
0x14004f511  mov     rdx, r15; unsigned __int16 *
0x14004f514  lea     rcx, [rbp+57h+var_40]; this
0x14004f518  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x14004f51d  nop
0x14004f51e  movups  xmm0, xmmword ptr [rax]
0x14004f521  movaps  [rbp+57h+var_60], xmm0
0x14004f525  movsd   xmm1, qword ptr [rax+10h]
0x14004f52a  movsd   [rbp+57h+var_50], xmm1
0x14004f52f  mov     r9, rsi
0x14004f532  lea     r8, [rbp+57h+var_60]
0x14004f536  mov     rdx, rbx
0x14004f539  mov     rcx, rdi
0x14004f53c  mov     rax, r14
0x14004f53f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f544  mov     rcx, [rbp+5Fh]; this
0x14004f548  test    eax, eax
0x14004f54a  js      short loc_14004F5AD
0x14004f54c  lea     rcx, [rbp+57h+var_40]; this
0x14004f550  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x14004f555  nop
0x14004f556  mov     rcx, [rbp+57h+var_90]
0x14004f55a  mov     [rbp+57h+var_90], 0
0x14004f562  test    rcx, rcx
0x14004f565  jz      short loc_14004F574
0x14004f567  mov     rax, [rcx]
0x14004f56a  mov     rax, [rax+10h]
0x14004f56e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f573  nop
0x14004f574  mov     rcx, [rsi]
0x14004f577  test    rcx, rcx
0x14004f57a  jz      short loc_14004F58E
0x14004f57c  mov     [rbp+57h+var_90], rcx
0x14004f580  mov     rax, [rcx]
0x14004f583  mov     rax, [rax+8]
0x14004f587  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f58c  jmp     short loc_14004F596
0x14004f58e  mov     [rbp+57h+var_90], 0
0x14004f596  lea     rcx, [rbp+57h+ui]
0x14004f59a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14004f59f  lea     rcx, [rbp+57h+var_70]
0x14004f5a3  call    ??Eiterator@?$generator@URegisteredTask@TaskSchedulerWrappers@Win32@Microsoft@@V?$allocator@D@std@@@experimental@std@@QEAAAEAU0123@XZ; std::experimental::generator<Microsoft::Win32::TaskSchedulerWrappers::RegisteredTask,std::allocator<char>>::iterator::operator++(void)
0x14004f5a8  jmp     loc_14004F454
0x14004f5ad  mov     r9d, eax; char *
0x14004f5b0  lea     r8, aOnecoreBaseFsR_30; "onecore\\base\\fs\\refsdedupsvc\\svclib"...
0x14004f5b7  mov     edx, 321h; void *
0x14004f5bc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14004f5c2  lea     r8, aOnecoreBaseFsR_30; "onecore\\base\\fs\\refsdedupsvc\\svclib"...
0x14004f5c9  mov     edx, 31Ch; void *
0x14004f5ce  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x14004f5d4  mov     r9d, eax; char *
0x14004f5d7  lea     r8, aOnecoreBaseFsR_30; "onecore\\base\\fs\\refsdedupsvc\\svclib"...
0x14004f5de  mov     edx, 31Ah; void *
0x14004f5e3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14004f5e9  lea     rcx, [rbp+57h+var_80]
0x14004f5ed  call    ??1?$generator@V?$basic_string_view@GU?$char_traits@G@std@@@std@@V?$allocator@D@2@@experimental@std@@QEAA@XZ; std::experimental::generator<std::basic_string_view<ushort>,std::allocator<char>>::~generator<std::basic_string_view<ushort>,std::allocator<char>>(void)
0x14004f5f2  nop
0x14004f5f3  lea     rcx, [rbp+57h+var_90]
0x14004f5f7  call    ??1?$com_ptr_t@UIAction@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAction,wil::err_exception_policy>::~com_ptr_t<IAction,wil::err_exception_policy>(void)
0x14004f5fc  nop
0x14004f5fd  mov     rax, rsi
0x14004f600  mov     rbx, [rsp+0C0h+arg_10]
0x14004f608  add     rsp, 0A0h
0x14004f60f  pop     r15
0x14004f611  pop     r14
0x14004f613  pop     rdi
0x14004f614  pop     rsi
0x14004f615  pop     rbp
0x14004f616  retn
```
