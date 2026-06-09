# utility::details::scoped_c_thread_locale::c_locale(void)

- ea: `0x180031db0`
- end: `0x180031ea3`
- name: `?c_locale@scoped_c_thread_locale@details@utility@@SAPEAU__crt_locale_pointers@@XZ`
- size: `243`
- prototype: `struct __crt_locale_pointers *(void)`
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180030920`
- `0x180030a80`
- `0x180034970`
- `0x180036410`

## callees

- `0x180031db0`
- `0x180051d28`
- `0x180051d48`
- `0x1800522a2`
- `0x180083b48`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__create_locale` at `0x180031e17`
- `api-ms-win-crt-private-l1-1-0!_o__create_locale` at `0x180031e17`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180031e5b`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180031e5b`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180031dce`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180031dce`

## string_xrefs

- `0x180031e7a`: `Unable to create 'C' locale.`

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
  _BYTE pExceptionObject[40]; // [rsp+30h] [rbp-28h] BYREF
  WINBOOL fPending; // [rsp+60h] [rbp+8h] BYREF

  if ( !__std_init_once_begin_initialize(&utility::details::g_c_localeFlag, 0, &fPending, 0) )
    __fastfail(5u);
  if ( fPending )
  {
    v0 = (_locale_t *)operator new(8u);
    if ( v0 )
      *v0 = 0;
    else
      v0 = 0;
    locale = _create_locale(0, "C");
    *v0 = locale;
    if ( !locale )
    {
      std::runtime_error::runtime_error((std::runtime_error *)pExceptionObject, "Unable to create 'C' locale.");
      throw (std::runtime_error *)pExceptionObject;
    }
    v3 = qword_180102078;
    qword_180102078 = (__int64)v0;
    if ( v3 )
      ((void (__fastcall *)(__int64, __int64))utility::details::g_c_locale)(v3, v2);
    utility::details::g_c_locale = (__int64 (__fastcall *)())_utility::details::scoped_c_thread_locale::c_locale_::_2_::_lambda_1_::operator()_::_2_::_lambda_1_::_lambda_invoker_cdecl_;
    if ( !InitOnceComplete(&utility::details::g_c_localeFlag, 0, 0) )
      _std_init_once_link_alternate_names_and_abort(v5, v4);
  }
  return *(struct __crt_locale_pointers **)qword_180102078;
}

```

## disassembly

```asm
0x180031db0  mov     [rsp+arg_8], rbx
0x180031db5  push    rdi
0x180031db6  sub     rsp, 50h
0x180031dba  xor     r9d, r9d; lpContext
0x180031dbd  lea     r8, [rsp+58h+fPending]; fPending
0x180031dc2  xor     edx, edx; dwFlags
0x180031dc4  lea     rdi, ?g_c_localeFlag@details@utility@@3Uonce_flag@std@@A; std::once_flag utility::details::g_c_localeFlag
0x180031dcb  mov     rcx, rdi; lpInitOnce
0x180031dce  call    cs:__imp___std_init_once_begin_initialize
0x180031dd4  test    eax, eax
0x180031dd6  jnz     short loc_180031DDF
0x180031dd8  mov     ecx, 5
0x180031ddd  int     29h; Win8: RtlFailFast(ecx)
0x180031ddf  cmp     [rsp+58h+fPending], 0
0x180031de4  jz      short loc_180031E65
0x180031de6  mov     [rsp+58h+var_38], rdi
0x180031deb  mov     [rsp+58h+var_30], 4
0x180031df3  mov     ecx, 8; Size
0x180031df8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180031dfd  mov     rbx, rax
0x180031e00  test    rax, rax
0x180031e03  jz      short loc_180031E0C
0x180031e05  xor     eax, eax
0x180031e07  mov     [rbx], rax
0x180031e0a  jmp     short loc_180031E0E
0x180031e0c  xor     ebx, ebx
0x180031e0e  lea     rdx, Locale; "C"
0x180031e15  xor     ecx, ecx; Category
0x180031e17  call    cs:__imp__create_locale
0x180031e1d  mov     [rbx], rax
0x180031e20  test    rax, rax
0x180031e23  jz      short loc_180031E7A
0x180031e25  mov     rcx, cs:qword_180102078
0x180031e2c  mov     cs:qword_180102078, rbx
0x180031e33  test    rcx, rcx
0x180031e36  jz      short loc_180031E45
0x180031e38  mov     rax, cs:?g_c_locale@details@utility@@3V?$unique_ptr@PEAU__crt_locale_pointers@@P6AXPEAPEAU1@@Z@std@@A; std::unique_ptr<__crt_locale_pointers *,void (*)(__crt_locale_pointers * *)> utility::details::g_c_locale
0x180031e3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031e44  nop
0x180031e45  lea     rax, __utility__details__scoped_c_thread_locale__c_locale____2____lambda_1___operator______2____lambda_1____lambda_invoker_cdecl_
0x180031e4c  mov     cs:?g_c_locale@details@utility@@3V?$unique_ptr@PEAU__crt_locale_pointers@@P6AXPEAPEAU1@@Z@std@@A, rax; std::unique_ptr<__crt_locale_pointers *,void (*)(__crt_locale_pointers * *)> utility::details::g_c_locale
0x180031e53  xor     r8d, r8d; lpContext
0x180031e56  xor     edx, edx; dwFlags
0x180031e58  mov     rcx, rdi; lpInitOnce
0x180031e5b  call    cs:__imp_InitOnceComplete
0x180031e61  test    eax, eax
0x180031e63  jz      short loc_180031E9D
0x180031e65  mov     rax, cs:qword_180102078
0x180031e6c  mov     rax, [rax]
0x180031e6f  mov     rbx, [rsp+58h+arg_8]
0x180031e74  add     rsp, 50h
0x180031e78  pop     rdi
0x180031e79  retn
0x180031e7a  lea     rdx, aUnableToCreate; "Unable to create 'C' locale."
0x180031e81  lea     rcx, [rsp+58h+pExceptionObject]; this
0x180031e86  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x180031e8b  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180031e92  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180031e97  call    _CxxThrowException_0
0x180031e9d  call    __std_init_once_link_alternate_names_and_abort
```
