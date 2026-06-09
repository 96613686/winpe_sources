# utility::details::scoped_c_thread_locale::c_locale(void)

- ea: `0x1800521fc`
- end: `0x18005230d`
- name: `?c_locale@scoped_c_thread_locale@details@utility@@SAPEAU__crt_locale_pointers@@XZ`
- size: `273`
- prototype: `struct __crt_locale_pointers *(void)`
- caller_count: `4`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18004ef20`
- `0x18004f0b0`
- `0x1800506a4`
- `0x180050998`

## callees

- `0x1800345b0`
- `0x180037fa0`
- `0x1800521fc`
- `0x18005626a`
- `0x1800563c8`
- `0x180056500`
- `0x180056524`
- `0x180058abc`
- `0x18005c5e0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800522b2`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800522b2`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180052231`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180052231`

## string_xrefs

- `0x1800522ea`: `Unable to create 'C' locale.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct __crt_locale_pointers *utility::details::scoped_c_thread_locale::c_locale(void)
{
  _locale_t *v0; // rbx
  _locale_t locale; // rax
  __int64 v2; // rdx
  __int64 v3; // rcx
  __int64 v4; // rdx
  __int64 v5; // rcx
  _BYTE pExceptionObject[24]; // [rsp+30h] [rbp-38h] BYREF
  BOOL fPending; // [rsp+48h] [rbp-20h] BYREF

  fPending = 0;
  if ( !__std_init_once_begin_initialize(&utility::details::g_c_localeFlag, 0, &fPending, 0) )
    abort();
  if ( fPending )
  {
    v0 = (_locale_t *)operator new(8u);
    *v0 = 0;
    locale = create_locale(0, "C");
    *v0 = locale;
    if ( !locale )
    {
      std::runtime_error::runtime_error((std::runtime_error *)pExceptionObject, "Unable to create 'C' locale.");
      throw (std::runtime_error *)pExceptionObject;
    }
    v3 = qword_18009D4E8;
    qword_18009D4E8 = (__int64)v0;
    if ( v3 )
      ((void (__fastcall *)(__int64, __int64))utility::details::g_c_locale)(v3, v2);
    utility::details::g_c_locale = (__int64 (__fastcall *)())lambda_41ecd71de5d8b60bfbea6452d600c7b3_::_lambda_invoker_cdecl_;
    if ( !InitOnceComplete(&utility::details::g_c_localeFlag, 0, 0) )
      _std_init_once_link_alternate_names_and_abort(v5, v4);
  }
  return *(struct __crt_locale_pointers **)qword_18009D4E8;
}

```

## disassembly

```asm
0x1800521fc  mov     [rsp+arg_0], rbx
0x180052201  push    rdi
0x180052202  sub     rsp, 60h
0x180052206  mov     rax, cs:__security_cookie
0x18005220d  xor     rax, rsp
0x180052210  mov     [rsp+68h+var_18], rax
0x180052215  mov     [rsp+68h+fPending], 0
0x18005221d  xor     r9d, r9d; lpContext
0x180052220  lea     r8, [rsp+68h+fPending]; fPending
0x180052225  xor     edx, edx; dwFlags
0x180052227  lea     rdi, ?g_c_localeFlag@details@utility@@3Uonce_flag@std@@A; std::once_flag utility::details::g_c_localeFlag
0x18005222e  mov     rcx, rdi; lpInitOnce
0x180052231  call    cs:__imp___std_init_once_begin_initialize
0x180052237  test    eax, eax
0x180052239  jz      loc_1800522E4
0x18005223f  cmp     [rsp+68h+fPending], 0
0x180052244  jz      short loc_1800522BC
0x180052246  mov     [rsp+68h+var_48], rdi
0x18005224b  mov     [rsp+68h+var_40], 4
0x180052254  mov     ecx, 8; Size
0x180052259  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005225e  mov     rbx, rax
0x180052261  xor     eax, eax
0x180052263  mov     [rbx], rax
0x180052266  lea     rdx, Locale; "C"
0x18005226d  xor     ecx, ecx; Category
0x18005226f  call    _create_locale
0x180052274  mov     [rbx], rax
0x180052277  test    rax, rax
0x18005227a  jz      short loc_1800522EA
0x18005227c  mov     rcx, cs:qword_18009D4E8
0x180052283  mov     cs:qword_18009D4E8, rbx
0x18005228a  test    rcx, rcx
0x18005228d  jz      short loc_18005229C
0x18005228f  mov     rax, cs:?g_c_locale@details@utility@@3V?$unique_ptr@PEAU__crt_locale_pointers@@P6AXPEAPEAU1@@Z@std@@A; std::unique_ptr<__crt_locale_pointers *,void (*)(__crt_locale_pointers * *)> utility::details::g_c_locale
0x180052296  call    _guard_dispatch_icall
0x18005229b  nop
0x18005229c  lea     rax, _lambda_41ecd71de5d8b60bfbea6452d600c7b3____lambda_invoker_cdecl_
0x1800522a3  mov     cs:?g_c_locale@details@utility@@3V?$unique_ptr@PEAU__crt_locale_pointers@@P6AXPEAPEAU1@@Z@std@@A, rax; std::unique_ptr<__crt_locale_pointers *,void (*)(__crt_locale_pointers * *)> utility::details::g_c_locale
0x1800522aa  xor     r8d, r8d; lpContext
0x1800522ad  xor     edx, edx; dwFlags
0x1800522af  mov     rcx, rdi; lpInitOnce
0x1800522b2  call    cs:__imp_InitOnceComplete
0x1800522b8  test    eax, eax
0x1800522ba  jz      short loc_1800522DE
0x1800522bc  mov     rax, cs:qword_18009D4E8
0x1800522c3  mov     rax, [rax]
0x1800522c6  mov     rcx, [rsp+68h+var_18]
0x1800522cb  xor     rcx, rsp; StackCookie
0x1800522ce  call    __security_check_cookie
0x1800522d3  mov     rbx, [rsp+68h+arg_0]
0x1800522d8  add     rsp, 60h
0x1800522dc  pop     rdi
0x1800522dd  retn
0x1800522de  call    __std_init_once_link_alternate_names_and_abort
0x1800522e4  call    abort
0x1800522ea  lea     rdx, aUnableToCreate; "Unable to create 'C' locale."
0x1800522f1  lea     rcx, [rsp+68h+pExceptionObject]; this
0x1800522f6  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x1800522fb  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180052302  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180052307  call    _CxxThrowException
```
