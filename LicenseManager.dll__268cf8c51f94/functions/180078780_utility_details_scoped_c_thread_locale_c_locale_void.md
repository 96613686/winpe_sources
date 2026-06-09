# utility::details::scoped_c_thread_locale::c_locale(void)

- ea: `0x180078780`
- end: `0x180078873`
- name: `?c_locale@scoped_c_thread_locale@details@utility@@SAPEAU__crt_locale_pointers@@XZ`
- size: `243`
- prototype: `struct __crt_locale_pointers *(void)`
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18007e000`
- `0x18007e160`
- `0x18007f0c0`
- `0x180080af0`

## callees

- `0x1800767e0`
- `0x180076a00`
- `0x180078780`
- `0x180082098`
- `0x18008da1c`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__create_locale` at `0x1800787e7`
- `api-ms-win-crt-private-l1-1-0!_o__create_locale` at `0x1800787e7`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18007882b`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18007882b`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18007879e`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18007879e`

## string_xrefs

- `0x18007884a`: `Unable to create 'C' locale.`

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
    v3 = qword_1800F1038;
    qword_1800F1038 = (__int64)v0;
    if ( v3 )
      ((void (__fastcall *)(__int64, __int64))utility::details::g_c_locale)(v3, v2);
    utility::details::g_c_locale = (__int64 (__fastcall *)())_utility::details::scoped_c_thread_locale::c_locale_::_2_::_lambda_1_::operator()_::_2_::_lambda_1_::_lambda_invoker_cdecl_;
    if ( !InitOnceComplete(&utility::details::g_c_localeFlag, 0, 0) )
      _std_init_once_link_alternate_names_and_abort(v5, v4);
  }
  return *(struct __crt_locale_pointers **)qword_1800F1038;
}

```

## disassembly

```asm
0x180078780  mov     [rsp+arg_8], rbx
0x180078785  push    rdi
0x180078786  sub     rsp, 50h
0x18007878a  xor     r9d, r9d; lpContext
0x18007878d  lea     r8, [rsp+58h+fPending]; fPending
0x180078792  xor     edx, edx; dwFlags
0x180078794  lea     rdi, ?g_c_localeFlag@details@utility@@3Uonce_flag@std@@A; std::once_flag utility::details::g_c_localeFlag
0x18007879b  mov     rcx, rdi; lpInitOnce
0x18007879e  call    cs:__imp___std_init_once_begin_initialize
0x1800787a4  test    eax, eax
0x1800787a6  jnz     short loc_1800787AF
0x1800787a8  mov     ecx, 5
0x1800787ad  int     29h; Win8: RtlFailFast(ecx)
0x1800787af  cmp     [rsp+58h+fPending], 0
0x1800787b4  jz      short loc_180078835
0x1800787b6  mov     [rsp+58h+var_38], rdi
0x1800787bb  mov     [rsp+58h+var_30], 4
0x1800787c3  mov     ecx, 8; Size
0x1800787c8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800787cd  mov     rbx, rax
0x1800787d0  test    rax, rax
0x1800787d3  jz      short loc_1800787DC
0x1800787d5  xor     eax, eax
0x1800787d7  mov     [rbx], rax
0x1800787da  jmp     short loc_1800787DE
0x1800787dc  xor     ebx, ebx
0x1800787de  lea     rdx, Locale; "C"
0x1800787e5  xor     ecx, ecx; Category
0x1800787e7  call    cs:__imp__create_locale
0x1800787ed  mov     [rbx], rax
0x1800787f0  test    rax, rax
0x1800787f3  jz      short loc_18007884A
0x1800787f5  mov     rcx, cs:qword_1800F1038
0x1800787fc  mov     cs:qword_1800F1038, rbx
0x180078803  test    rcx, rcx
0x180078806  jz      short loc_180078815
0x180078808  mov     rax, cs:?g_c_locale@details@utility@@3V?$unique_ptr@PEAU__crt_locale_pointers@@P6AXPEAPEAU1@@Z@std@@A; std::unique_ptr<__crt_locale_pointers *,void (*)(__crt_locale_pointers * *)> utility::details::g_c_locale
0x18007880f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078814  nop
0x180078815  lea     rax, __utility__details__scoped_c_thread_locale__c_locale____2____lambda_1___operator______2____lambda_1____lambda_invoker_cdecl_
0x18007881c  mov     cs:?g_c_locale@details@utility@@3V?$unique_ptr@PEAU__crt_locale_pointers@@P6AXPEAPEAU1@@Z@std@@A, rax; std::unique_ptr<__crt_locale_pointers *,void (*)(__crt_locale_pointers * *)> utility::details::g_c_locale
0x180078823  xor     r8d, r8d; lpContext
0x180078826  xor     edx, edx; dwFlags
0x180078828  mov     rcx, rdi; lpInitOnce
0x18007882b  call    cs:__imp_InitOnceComplete
0x180078831  test    eax, eax
0x180078833  jz      short loc_18007886D
0x180078835  mov     rax, cs:qword_1800F1038
0x18007883c  mov     rax, [rax]
0x18007883f  mov     rbx, [rsp+58h+arg_8]
0x180078844  add     rsp, 50h
0x180078848  pop     rdi
0x180078849  retn
0x18007884a  lea     rdx, aUnableToCreate; "Unable to create 'C' locale."
0x180078851  lea     rcx, [rsp+58h+pExceptionObject]; this
0x180078856  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x18007885b  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180078862  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180078867  call    _CxxThrowException_0
0x18007886d  call    __std_init_once_link_alternate_names_and_abort
```
