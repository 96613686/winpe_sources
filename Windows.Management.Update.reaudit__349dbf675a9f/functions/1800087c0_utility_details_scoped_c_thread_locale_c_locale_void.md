# utility::details::scoped_c_thread_locale::c_locale(void)

- ea: `0x1800087c0`
- end: `0x1800088b3`
- name: `?c_locale@scoped_c_thread_locale@details@utility@@SAPEAU__crt_locale_pointers@@XZ`
- size: `243`
- prototype: `struct __crt_locale_pointers *(void)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180007ec0`
- `0x180008010`

## callees

- `0x180002cac`
- `0x1800035f0`
- `0x1800086f0`
- `0x1800087c0`
- `0x180008c38`
- `0x18002c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__create_locale` at `0x180008827`
- `api-ms-win-crt-private-l1-1-0!_o__create_locale` at `0x180008827`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800087e8`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800087e8`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800087de`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800087de`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000886b`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000886b`

## string_xrefs

- `0x18000888a`: `Unable to create 'C' locale.`

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
  BOOL fPending; // [rsp+60h] [rbp+8h] BYREF

  if ( !__std_init_once_begin_initialize(&utility::details::g_c_localeFlag, 0, &fPending, 0) )
    abort();
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
    v3 = qword_18003C008;
    qword_18003C008 = (__int64)v0;
    if ( v3 )
      ((void (__fastcall *)(__int64, __int64))utility::details::g_c_locale)(v3, v2);
    utility::details::g_c_locale = (__int64 (__fastcall *)())_utility::details::scoped_c_thread_locale::c_locale_::_2_::_lambda_1_::operator()_::_2_::_lambda_1_::_lambda_invoker_cdecl_;
    if ( !InitOnceComplete(&utility::details::g_c_localeFlag, 0, 0) )
      _std_init_once_link_alternate_names_and_abort(v5, v4);
  }
  return *(struct __crt_locale_pointers **)qword_18003C008;
}

```

## disassembly

```asm
0x1800087c0  mov     [rsp+arg_8], rbx
0x1800087c5  push    rdi
0x1800087c6  sub     rsp, 50h
0x1800087ca  xor     r9d, r9d; lpContext
0x1800087cd  lea     r8, [rsp+58h+fPending]; fPending
0x1800087d2  xor     edx, edx; dwFlags
0x1800087d4  lea     rdi, ?g_c_localeFlag@details@utility@@3Uonce_flag@std@@A; std::once_flag utility::details::g_c_localeFlag
0x1800087db  mov     rcx, rdi; lpInitOnce
0x1800087de  call    cs:__imp___std_init_once_begin_initialize
0x1800087e4  test    eax, eax
0x1800087e6  jnz     short loc_1800087EF
0x1800087e8  call    cs:__imp_abort
0x1800087ef  cmp     [rsp+58h+fPending], 0
0x1800087f4  jz      short loc_180008875
0x1800087f6  mov     [rsp+58h+var_38], rdi
0x1800087fb  mov     [rsp+58h+var_30], 4
0x180008803  mov     ecx, 8; Size
0x180008808  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000880d  mov     rbx, rax
0x180008810  test    rax, rax
0x180008813  jz      short loc_18000881C
0x180008815  xor     eax, eax
0x180008817  mov     [rbx], rax
0x18000881a  jmp     short loc_18000881E
0x18000881c  xor     ebx, ebx
0x18000881e  lea     rdx, Locale; "C"
0x180008825  xor     ecx, ecx; Category
0x180008827  call    cs:__imp__create_locale
0x18000882d  mov     [rbx], rax
0x180008830  test    rax, rax
0x180008833  jz      short loc_18000888A
0x180008835  mov     rcx, cs:qword_18003C008
0x18000883c  mov     cs:qword_18003C008, rbx
0x180008843  test    rcx, rcx
0x180008846  jz      short loc_180008855
0x180008848  mov     rax, cs:?g_c_locale@details@utility@@3V?$unique_ptr@PEAU__crt_locale_pointers@@P6AXPEAPEAU1@@Z@std@@A; std::unique_ptr<__crt_locale_pointers *,void (*)(__crt_locale_pointers * *)> utility::details::g_c_locale
0x18000884f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008854  nop
0x180008855  lea     rax, __utility__details__scoped_c_thread_locale__c_locale____2____lambda_1___operator______2____lambda_1____lambda_invoker_cdecl_
0x18000885c  mov     cs:?g_c_locale@details@utility@@3V?$unique_ptr@PEAU__crt_locale_pointers@@P6AXPEAPEAU1@@Z@std@@A, rax; std::unique_ptr<__crt_locale_pointers *,void (*)(__crt_locale_pointers * *)> utility::details::g_c_locale
0x180008863  xor     r8d, r8d; lpContext
0x180008866  xor     edx, edx; dwFlags
0x180008868  mov     rcx, rdi; lpInitOnce
0x18000886b  call    cs:__imp_InitOnceComplete
0x180008871  test    eax, eax
0x180008873  jz      short loc_1800088AD
0x180008875  mov     rax, cs:qword_18003C008
0x18000887c  mov     rax, [rax]
0x18000887f  mov     rbx, [rsp+58h+arg_8]
0x180008884  add     rsp, 50h
0x180008888  pop     rdi
0x180008889  retn
0x18000888a  lea     rdx, aUnableToCreate; "Unable to create 'C' locale."
0x180008891  lea     rcx, [rsp+58h+pExceptionObject]; this
0x180008896  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x18000889b  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x1800088a2  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x1800088a7  call    _CxxThrowException_0
0x1800088ad  call    __std_init_once_link_alternate_names_and_abort
```
