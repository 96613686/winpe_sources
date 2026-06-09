# utility::details::scoped_c_thread_locale::c_locale(void)

- ea: `0x18001c8f0`
- end: `0x18001c9e3`
- name: `?c_locale@scoped_c_thread_locale@details@utility@@SAPEAU__crt_locale_pointers@@XZ`
- size: `243`
- prototype: `struct __crt_locale_pointers *(void)`
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180039f60`
- `0x18003a0c0`
- `0x180043c90`
- `0x180045640`

## callees

- `0x18000bddc`
- `0x18000c510`
- `0x18001c8f0`
- `0x180063874`
- `0x180084808`
- `0x180200010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__create_locale` at `0x18001c957`
- `api-ms-win-crt-private-l1-1-0!_o__create_locale` at `0x18001c957`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001c90e`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001c90e`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001c99b`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001c99b`

## string_xrefs

- `0x18001c9ba`: `Unable to create 'C' locale.`

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
    v3 = qword_1802A3070;
    qword_1802A3070 = (__int64)v0;
    if ( v3 )
      ((void (__fastcall *)(__int64, __int64))utility::details::g_c_locale)(v3, v2);
    utility::details::g_c_locale = (__int64 (__fastcall *)())_utility::details::scoped_c_thread_locale::c_locale_::_2_::_lambda_1_::operator()_::_2_::_lambda_1_::_lambda_invoker_cdecl_;
    if ( !InitOnceComplete(&utility::details::g_c_localeFlag, 0, 0) )
      _std_init_once_link_alternate_names_and_abort(v5, v4);
  }
  return *(struct __crt_locale_pointers **)qword_1802A3070;
}

```

## disassembly

```asm
0x18001c8f0  mov     [rsp+arg_8], rbx
0x18001c8f5  push    rdi
0x18001c8f6  sub     rsp, 50h
0x18001c8fa  xor     r9d, r9d; lpContext
0x18001c8fd  lea     r8, [rsp+58h+fPending]; fPending
0x18001c902  xor     edx, edx; dwFlags
0x18001c904  lea     rdi, ?g_c_localeFlag@details@utility@@3Uonce_flag@std@@A; std::once_flag utility::details::g_c_localeFlag
0x18001c90b  mov     rcx, rdi; lpInitOnce
0x18001c90e  call    cs:__imp___std_init_once_begin_initialize
0x18001c914  test    eax, eax
0x18001c916  jnz     short loc_18001C91F
0x18001c918  mov     ecx, 5
0x18001c91d  int     29h; Win8: RtlFailFast(ecx)
0x18001c91f  cmp     [rsp+58h+fPending], 0
0x18001c924  jz      short loc_18001C9A5
0x18001c926  mov     [rsp+58h+var_38], rdi
0x18001c92b  mov     [rsp+58h+var_30], 4
0x18001c933  mov     ecx, 8; Size
0x18001c938  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c93d  mov     rbx, rax
0x18001c940  test    rax, rax
0x18001c943  jz      short loc_18001C94C
0x18001c945  xor     eax, eax
0x18001c947  mov     [rbx], rax
0x18001c94a  jmp     short loc_18001C94E
0x18001c94c  xor     ebx, ebx
0x18001c94e  lea     rdx, Locale; "C"
0x18001c955  xor     ecx, ecx; Category
0x18001c957  call    cs:__imp__create_locale
0x18001c95d  mov     [rbx], rax
0x18001c960  test    rax, rax
0x18001c963  jz      short loc_18001C9BA
0x18001c965  mov     rcx, cs:qword_1802A3070
0x18001c96c  mov     cs:qword_1802A3070, rbx
0x18001c973  test    rcx, rcx
0x18001c976  jz      short loc_18001C985
0x18001c978  mov     rax, cs:?g_c_locale@details@utility@@3V?$unique_ptr@PEAU__crt_locale_pointers@@P6AXPEAPEAU1@@Z@std@@A; std::unique_ptr<__crt_locale_pointers *,void (*)(__crt_locale_pointers * *)> utility::details::g_c_locale
0x18001c97f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c984  nop
0x18001c985  lea     rax, __utility__details__scoped_c_thread_locale__c_locale____2____lambda_1___operator______2____lambda_1____lambda_invoker_cdecl_
0x18001c98c  mov     cs:?g_c_locale@details@utility@@3V?$unique_ptr@PEAU__crt_locale_pointers@@P6AXPEAPEAU1@@Z@std@@A, rax; std::unique_ptr<__crt_locale_pointers *,void (*)(__crt_locale_pointers * *)> utility::details::g_c_locale
0x18001c993  xor     r8d, r8d; lpContext
0x18001c996  xor     edx, edx; dwFlags
0x18001c998  mov     rcx, rdi; lpInitOnce
0x18001c99b  call    cs:__imp_InitOnceComplete
0x18001c9a1  test    eax, eax
0x18001c9a3  jz      short loc_18001C9DD
0x18001c9a5  mov     rax, cs:qword_1802A3070
0x18001c9ac  mov     rax, [rax]
0x18001c9af  mov     rbx, [rsp+58h+arg_8]
0x18001c9b4  add     rsp, 50h
0x18001c9b8  pop     rdi
0x18001c9b9  retn
0x18001c9ba  lea     rdx, aUnableToCreate_0; "Unable to create 'C' locale."
0x18001c9c1  lea     rcx, [rsp+58h+pExceptionObject]; this
0x18001c9c6  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x18001c9cb  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18001c9d2  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18001c9d7  call    _CxxThrowException_0
0x18001c9dd  call    __std_init_once_link_alternate_names_and_abort
```
