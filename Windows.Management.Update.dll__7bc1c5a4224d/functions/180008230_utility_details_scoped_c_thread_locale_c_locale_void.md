# utility::details::scoped_c_thread_locale::c_locale(void)

- ea: `0x180008230`
- end: `0x180008323`
- name: `?c_locale@scoped_c_thread_locale@details@utility@@SAPEAU__crt_locale_pointers@@XZ`
- size: `243`
- prototype: `struct __crt_locale_pointers *(void)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800079a0`
- `0x180007b00`

## callees

- `0x180002cfc`
- `0x18000340c`
- `0x1800081b0`
- `0x180008230`
- `0x180008698`
- `0x18002a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__create_locale` at `0x180008297`
- `api-ms-win-crt-private-l1-1-0!_o__create_locale` at `0x180008297`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000824e`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000824e`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800082db`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800082db`

## string_xrefs

- `0x1800082fa`: `Unable to create 'C' locale.`

## pseudocode

```c
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
    v3 = qword_18003A008;
    qword_18003A008 = (__int64)v0;
    if ( v3 )
      ((void (__fastcall *)(__int64, __int64))utility::details::g_c_locale)(v3, v2);
    utility::details::g_c_locale = (__int64 (__fastcall *)())_utility::details::scoped_c_thread_locale::c_locale_::_2_::_lambda_1_::operator()_::_2_::_lambda_1_::_lambda_invoker_cdecl_;
    if ( !InitOnceComplete(&utility::details::g_c_localeFlag, 0, 0) )
      _std_init_once_link_alternate_names_and_abort(v5, v4);
  }
  return *(struct __crt_locale_pointers **)qword_18003A008;
}

```

## disassembly

```asm
0x180008230  mov     [rsp+arg_8], rbx
0x180008235  push    rdi
0x180008236  sub     rsp, 50h
0x18000823a  xor     r9d, r9d; lpContext
0x18000823d  lea     r8, [rsp+58h+fPending]; fPending
0x180008242  xor     edx, edx; dwFlags
0x180008244  lea     rdi, ?g_c_localeFlag@details@utility@@3Uonce_flag@std@@A; std::once_flag utility::details::g_c_localeFlag
0x18000824b  mov     rcx, rdi; lpInitOnce
0x18000824e  call    cs:__imp___std_init_once_begin_initialize
0x180008254  test    eax, eax
0x180008256  jnz     short loc_18000825F
0x180008258  mov     ecx, 5
0x18000825d  int     29h; Win8: RtlFailFast(ecx)
0x18000825f  cmp     [rsp+58h+fPending], 0
0x180008264  jz      short loc_1800082E5
0x180008266  mov     [rsp+58h+var_38], rdi
0x18000826b  mov     [rsp+58h+var_30], 4
0x180008273  mov     ecx, 8; Size
0x180008278  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000827d  mov     rbx, rax
0x180008280  test    rax, rax
0x180008283  jz      short loc_18000828C
0x180008285  xor     eax, eax
0x180008287  mov     [rbx], rax
0x18000828a  jmp     short loc_18000828E
0x18000828c  xor     ebx, ebx
0x18000828e  lea     rdx, Locale; "C"
0x180008295  xor     ecx, ecx; Category
0x180008297  call    cs:__imp__create_locale
0x18000829d  mov     [rbx], rax
0x1800082a0  test    rax, rax
0x1800082a3  jz      short loc_1800082FA
0x1800082a5  mov     rcx, cs:qword_18003A008
0x1800082ac  mov     cs:qword_18003A008, rbx
0x1800082b3  test    rcx, rcx
0x1800082b6  jz      short loc_1800082C5
0x1800082b8  mov     rax, cs:?g_c_locale@details@utility@@3V?$unique_ptr@PEAU__crt_locale_pointers@@P6AXPEAPEAU1@@Z@std@@A; std::unique_ptr<__crt_locale_pointers *,void (*)(__crt_locale_pointers * *)> utility::details::g_c_locale
0x1800082bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082c4  nop
0x1800082c5  lea     rax, __utility__details__scoped_c_thread_locale__c_locale____2____lambda_1___operator______2____lambda_1____lambda_invoker_cdecl_
0x1800082cc  mov     cs:?g_c_locale@details@utility@@3V?$unique_ptr@PEAU__crt_locale_pointers@@P6AXPEAPEAU1@@Z@std@@A, rax; std::unique_ptr<__crt_locale_pointers *,void (*)(__crt_locale_pointers * *)> utility::details::g_c_locale
0x1800082d3  xor     r8d, r8d; lpContext
0x1800082d6  xor     edx, edx; dwFlags
0x1800082d8  mov     rcx, rdi; lpInitOnce
0x1800082db  call    cs:__imp_InitOnceComplete
0x1800082e1  test    eax, eax
0x1800082e3  jz      short loc_18000831D
0x1800082e5  mov     rax, cs:qword_18003A008
0x1800082ec  mov     rax, [rax]
0x1800082ef  mov     rbx, [rsp+58h+arg_8]
0x1800082f4  add     rsp, 50h
0x1800082f8  pop     rdi
0x1800082f9  retn
0x1800082fa  lea     rdx, aUnableToCreate; "Unable to create 'C' locale."
0x180008301  lea     rcx, [rsp+58h+pExceptionObject]; this
0x180008306  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x18000830b  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180008312  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180008317  call    _CxxThrowException_0
0x18000831d  call    __std_init_once_link_alternate_names_and_abort
```
