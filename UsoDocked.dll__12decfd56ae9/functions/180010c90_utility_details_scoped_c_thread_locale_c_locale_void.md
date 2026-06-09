# utility::details::scoped_c_thread_locale::c_locale(void)

- ea: `0x180010c90`
- end: `0x180010d83`
- name: `?c_locale@scoped_c_thread_locale@details@utility@@SAPEAU__crt_locale_pointers@@XZ`
- size: `243`
- prototype: `struct __crt_locale_pointers *(void)`
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000d8e0`
- `0x18000f310`
- `0x180010520`
- `0x180010680`

## callees

- `0x180007238`
- `0x180007dfc`
- `0x1800085a8`
- `0x180010c90`
- `0x18002af2c`
- `0x180071010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__create_locale` at `0x180010cf7`
- `api-ms-win-crt-private-l1-1-0!_o__create_locale` at `0x180010cf7`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180010cae`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180010cae`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180010d3b`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180010d3b`

## string_xrefs

- `0x180010d5a`: `Unable to create 'C' locale.`

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
    v3 = qword_180094018;
    qword_180094018 = (__int64)v0;
    if ( v3 )
      ((void (__fastcall *)(__int64, __int64))utility::details::g_c_locale)(v3, v2);
    utility::details::g_c_locale = (__int64 (__fastcall *)())_utility::details::scoped_c_thread_locale::c_locale_::_2_::_lambda_1_::operator()_::_2_::_lambda_1_::_lambda_invoker_cdecl_;
    if ( !InitOnceComplete(&utility::details::g_c_localeFlag, 0, 0) )
      _std_init_once_link_alternate_names_and_abort(v5, v4);
  }
  return *(struct __crt_locale_pointers **)qword_180094018;
}

```

## disassembly

```asm
0x180010c90  mov     [rsp+arg_8], rbx
0x180010c95  push    rdi
0x180010c96  sub     rsp, 50h
0x180010c9a  xor     r9d, r9d; lpContext
0x180010c9d  lea     r8, [rsp+58h+fPending]; fPending
0x180010ca2  xor     edx, edx; dwFlags
0x180010ca4  lea     rdi, ?g_c_localeFlag@details@utility@@3Uonce_flag@std@@A; std::once_flag utility::details::g_c_localeFlag
0x180010cab  mov     rcx, rdi; lpInitOnce
0x180010cae  call    cs:__imp___std_init_once_begin_initialize
0x180010cb4  test    eax, eax
0x180010cb6  jnz     short loc_180010CBF
0x180010cb8  mov     ecx, 5
0x180010cbd  int     29h; Win8: RtlFailFast(ecx)
0x180010cbf  cmp     [rsp+58h+fPending], 0
0x180010cc4  jz      short loc_180010D45
0x180010cc6  mov     [rsp+58h+var_38], rdi
0x180010ccb  mov     [rsp+58h+var_30], 4
0x180010cd3  mov     ecx, 8; Size
0x180010cd8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010cdd  mov     rbx, rax
0x180010ce0  test    rax, rax
0x180010ce3  jz      short loc_180010CEC
0x180010ce5  xor     eax, eax
0x180010ce7  mov     [rbx], rax
0x180010cea  jmp     short loc_180010CEE
0x180010cec  xor     ebx, ebx
0x180010cee  lea     rdx, Locale; "C"
0x180010cf5  xor     ecx, ecx; Category
0x180010cf7  call    cs:__imp__create_locale
0x180010cfd  mov     [rbx], rax
0x180010d00  test    rax, rax
0x180010d03  jz      short loc_180010D5A
0x180010d05  mov     rcx, cs:qword_180094018
0x180010d0c  mov     cs:qword_180094018, rbx
0x180010d13  test    rcx, rcx
0x180010d16  jz      short loc_180010D25
0x180010d18  mov     rax, cs:?g_c_locale@details@utility@@3V?$unique_ptr@PEAU__crt_locale_pointers@@P6AXPEAPEAU1@@Z@std@@A; std::unique_ptr<__crt_locale_pointers *,void (*)(__crt_locale_pointers * *)> utility::details::g_c_locale
0x180010d1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d24  nop
0x180010d25  lea     rax, __utility__details__scoped_c_thread_locale__c_locale____2____lambda_1___operator______2____lambda_1____lambda_invoker_cdecl_
0x180010d2c  mov     cs:?g_c_locale@details@utility@@3V?$unique_ptr@PEAU__crt_locale_pointers@@P6AXPEAPEAU1@@Z@std@@A, rax; std::unique_ptr<__crt_locale_pointers *,void (*)(__crt_locale_pointers * *)> utility::details::g_c_locale
0x180010d33  xor     r8d, r8d; lpContext
0x180010d36  xor     edx, edx; dwFlags
0x180010d38  mov     rcx, rdi; lpInitOnce
0x180010d3b  call    cs:__imp_InitOnceComplete
0x180010d41  test    eax, eax
0x180010d43  jz      short loc_180010D7D
0x180010d45  mov     rax, cs:qword_180094018
0x180010d4c  mov     rax, [rax]
0x180010d4f  mov     rbx, [rsp+58h+arg_8]
0x180010d54  add     rsp, 50h
0x180010d58  pop     rdi
0x180010d59  retn
0x180010d5a  lea     rdx, aUnableToCreate; "Unable to create 'C' locale."
0x180010d61  lea     rcx, [rsp+58h+pExceptionObject]; this
0x180010d66  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x180010d6b  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180010d72  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180010d77  call    _CxxThrowException_0
0x180010d7d  call    __std_init_once_link_alternate_names_and_abort
```
