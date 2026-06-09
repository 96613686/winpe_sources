# utility::details::scoped_c_thread_locale::c_locale(void)

- ea: `0x1400fd024`
- end: `0x1400fd136`
- name: `?c_locale@scoped_c_thread_locale@details@utility@@SAPEAU__crt_locale_pointers@@XZ`
- size: `274`
- prototype: `struct __crt_locale_pointers *(void)`
- caller_count: `4`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1400fa554`
- `0x1400fb7ac`
- `0x1400fc8e0`
- `0x1400fc9a0`

## callees

- `0x14001dd90`
- `0x14003a0f4`
- `0x14003a5c0`
- `0x14003c78c`
- `0x14004f9a8`
- `0x14005eff4`
- `0x140087178`
- `0x1400fd024`
- `0x140166250`

## import_xrefs

- `KERNEL32!InitOnceComplete` at `0x1400fd0db`
- `KERNEL32!InitOnceComplete` at `0x1400fd0db`
- `KERNEL32!InitOnceBeginInitialize` at `0x1400fd059`
- `KERNEL32!InitOnceBeginInitialize` at `0x1400fd059`

## string_xrefs

- `0x1400fd107`: `Unable to create 'C' locale.`

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
  WINBOOL fPending; // [rsp+48h] [rbp-20h] BYREF

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
    v3 = qword_1401D9730;
    qword_1401D9730 = (__int64)v0;
    if ( v3 )
      ((void (__fastcall *)(__int64, __int64))utility::details::g_c_locale)(v3, v2);
    utility::details::g_c_locale = (__int64 (__fastcall *)())_utility::details::scoped_c_thread_locale::c_locale_::_2_::_lambda_1_::operator()_::_2_::_lambda_1_::_lambda_invoker_cdecl_;
    if ( !InitOnceComplete(&utility::details::g_c_localeFlag, 0, 0) )
      _std_init_once_link_alternate_names_and_abort(v5, v4);
  }
  return *(struct __crt_locale_pointers **)qword_1401D9730;
}

```

## disassembly

```asm
0x1400fd024  mov     [rsp+arg_0], rbx
0x1400fd029  push    rdi
0x1400fd02a  sub     rsp, 60h
0x1400fd02e  mov     rax, cs:__security_cookie
0x1400fd035  xor     rax, rsp
0x1400fd038  mov     [rsp+68h+var_18], rax
0x1400fd03d  mov     [rsp+68h+fPending], 0
0x1400fd045  xor     r9d, r9d; lpContext
0x1400fd048  lea     r8, [rsp+68h+fPending]; fPending
0x1400fd04d  xor     edx, edx; dwFlags
0x1400fd04f  lea     rdi, ?g_c_localeFlag@details@utility@@3Uonce_flag@std@@A; std::once_flag utility::details::g_c_localeFlag
0x1400fd056  mov     rcx, rdi; lpInitOnce
0x1400fd059  call    cs:__imp___std_init_once_begin_initialize
0x1400fd05f  test    eax, eax
0x1400fd061  jz      loc_1400FD12A
0x1400fd067  cmp     [rsp+68h+fPending], 0
0x1400fd06c  jz      short loc_1400FD0E5
0x1400fd06e  mov     [rsp+68h+var_48], rdi
0x1400fd073  mov     [rsp+68h+var_40], 4
0x1400fd07c  mov     ecx, 8; Size
0x1400fd081  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400fd086  mov     rbx, rax
0x1400fd089  xor     eax, eax
0x1400fd08b  mov     [rbx], rax
0x1400fd08e  lea     rdx, Locale; "C"
0x1400fd095  xor     ecx, ecx; Category
0x1400fd097  call    _create_locale
0x1400fd09c  mov     [rbx], rax
0x1400fd09f  test    rax, rax
0x1400fd0a2  jz      short loc_1400FD107
0x1400fd0a4  mov     rcx, cs:qword_1401D9730
0x1400fd0ab  mov     cs:qword_1401D9730, rbx
0x1400fd0b2  test    rcx, rcx
0x1400fd0b5  jz      short loc_1400FD0C5
0x1400fd0b7  mov     rax, cs:?g_c_locale@details@utility@@3V?$unique_ptr@PEAU__crt_locale_pointers@@P6AXPEAPEAU1@@Z@std@@A; std::unique_ptr<__crt_locale_pointers *,void (*)(__crt_locale_pointers * *)> utility::details::g_c_locale
0x1400fd0be  call    cs:__guard_dispatch_icall_fptr
0x1400fd0c4  nop
0x1400fd0c5  lea     rax, __utility__details__scoped_c_thread_locale__c_locale____2____lambda_1___operator______2____lambda_1____lambda_invoker_cdecl_
0x1400fd0cc  mov     cs:?g_c_locale@details@utility@@3V?$unique_ptr@PEAU__crt_locale_pointers@@P6AXPEAPEAU1@@Z@std@@A, rax; std::unique_ptr<__crt_locale_pointers *,void (*)(__crt_locale_pointers * *)> utility::details::g_c_locale
0x1400fd0d3  xor     r8d, r8d; lpContext
0x1400fd0d6  xor     edx, edx; dwFlags
0x1400fd0d8  mov     rcx, rdi; lpInitOnce
0x1400fd0db  call    cs:__imp_InitOnceComplete
0x1400fd0e1  test    eax, eax
0x1400fd0e3  jz      short loc_1400FD130
0x1400fd0e5  mov     rax, cs:qword_1401D9730
0x1400fd0ec  mov     rax, [rax]
0x1400fd0ef  mov     rcx, [rsp+68h+var_18]
0x1400fd0f4  xor     rcx, rsp; StackCookie
0x1400fd0f7  call    __security_check_cookie
0x1400fd0fc  mov     rbx, [rsp+68h+arg_0]
0x1400fd101  add     rsp, 60h
0x1400fd105  pop     rdi
0x1400fd106  retn
0x1400fd107  lea     rdx, aUnableToCreate; "Unable to create 'C' locale."
0x1400fd10e  lea     rcx, [rsp+68h+pExceptionObject]; this
0x1400fd113  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x1400fd118  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x1400fd11f  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x1400fd124  call    _CxxThrowException
0x1400fd12a  call    abort
0x1400fd130  call    __std_init_once_link_alternate_names_and_abort
```
