# utility::details::scoped_c_thread_locale::c_locale(void)

- ea: `0x18001c8a0`
- end: `0x18001c993`
- name: `?c_locale@scoped_c_thread_locale@details@utility@@SAPEAU__crt_locale_pointers@@XZ`
- size: `243`
- prototype: `struct __crt_locale_pointers *(void)`
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180039db0`
- `0x180039f10`
- `0x180043ae0`
- `0x180045490`

## callees

- `0x18000bd0c`
- `0x18000c420`
- `0x18001c8a0`
- `0x180063694`
- `0x180083ca0`
- `0x1801fa010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__create_locale` at `0x18001c907`
- `api-ms-win-crt-private-l1-1-0!_o__create_locale` at `0x18001c907`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001c8be`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001c8be`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001c94b`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001c94b`

## string_xrefs

- `0x18001c96a`: `Unable to create 'C' locale.`

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
    v3 = qword_18029E070;
    qword_18029E070 = (__int64)v0;
    if ( v3 )
      ((void (__fastcall *)(__int64, __int64))utility::details::g_c_locale)(v3, v2);
    utility::details::g_c_locale = (__int64 (__fastcall *)())_utility::details::scoped_c_thread_locale::c_locale_::_2_::_lambda_1_::operator()_::_2_::_lambda_1_::_lambda_invoker_cdecl_;
    if ( !InitOnceComplete(&utility::details::g_c_localeFlag, 0, 0) )
      _std_init_once_link_alternate_names_and_abort(v5, v4);
  }
  return *(struct __crt_locale_pointers **)qword_18029E070;
}

```

## disassembly

```asm
0x18001c8a0  mov     [rsp+arg_8], rbx
0x18001c8a5  push    rdi
0x18001c8a6  sub     rsp, 50h
0x18001c8aa  xor     r9d, r9d; lpContext
0x18001c8ad  lea     r8, [rsp+58h+fPending]; fPending
0x18001c8b2  xor     edx, edx; dwFlags
0x18001c8b4  lea     rdi, ?g_c_localeFlag@details@utility@@3Uonce_flag@std@@A; std::once_flag utility::details::g_c_localeFlag
0x18001c8bb  mov     rcx, rdi; lpInitOnce
0x18001c8be  call    cs:__imp___std_init_once_begin_initialize
0x18001c8c4  test    eax, eax
0x18001c8c6  jnz     short loc_18001C8CF
0x18001c8c8  mov     ecx, 5
0x18001c8cd  int     29h; Win8: RtlFailFast(ecx)
0x18001c8cf  cmp     [rsp+58h+fPending], 0
0x18001c8d4  jz      short loc_18001C955
0x18001c8d6  mov     [rsp+58h+var_38], rdi
0x18001c8db  mov     [rsp+58h+var_30], 4
0x18001c8e3  mov     ecx, 8; Size
0x18001c8e8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c8ed  mov     rbx, rax
0x18001c8f0  test    rax, rax
0x18001c8f3  jz      short loc_18001C8FC
0x18001c8f5  xor     eax, eax
0x18001c8f7  mov     [rbx], rax
0x18001c8fa  jmp     short loc_18001C8FE
0x18001c8fc  xor     ebx, ebx
0x18001c8fe  lea     rdx, Locale; "C"
0x18001c905  xor     ecx, ecx; Category
0x18001c907  call    cs:__imp__create_locale
0x18001c90d  mov     [rbx], rax
0x18001c910  test    rax, rax
0x18001c913  jz      short loc_18001C96A
0x18001c915  mov     rcx, cs:qword_18029E070
0x18001c91c  mov     cs:qword_18029E070, rbx
0x18001c923  test    rcx, rcx
0x18001c926  jz      short loc_18001C935
0x18001c928  mov     rax, cs:?g_c_locale@details@utility@@3V?$unique_ptr@PEAU__crt_locale_pointers@@P6AXPEAPEAU1@@Z@std@@A; std::unique_ptr<__crt_locale_pointers *,void (*)(__crt_locale_pointers * *)> utility::details::g_c_locale
0x18001c92f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c934  nop
0x18001c935  lea     rax, __utility__details__scoped_c_thread_locale__c_locale____2____lambda_1___operator______2____lambda_1____lambda_invoker_cdecl_
0x18001c93c  mov     cs:?g_c_locale@details@utility@@3V?$unique_ptr@PEAU__crt_locale_pointers@@P6AXPEAPEAU1@@Z@std@@A, rax; std::unique_ptr<__crt_locale_pointers *,void (*)(__crt_locale_pointers * *)> utility::details::g_c_locale
0x18001c943  xor     r8d, r8d; lpContext
0x18001c946  xor     edx, edx; dwFlags
0x18001c948  mov     rcx, rdi; lpInitOnce
0x18001c94b  call    cs:__imp_InitOnceComplete
0x18001c951  test    eax, eax
0x18001c953  jz      short loc_18001C98D
0x18001c955  mov     rax, cs:qword_18029E070
0x18001c95c  mov     rax, [rax]
0x18001c95f  mov     rbx, [rsp+58h+arg_8]
0x18001c964  add     rsp, 50h
0x18001c968  pop     rdi
0x18001c969  retn
0x18001c96a  lea     rdx, aUnableToCreate_0; "Unable to create 'C' locale."
0x18001c971  lea     rcx, [rsp+58h+pExceptionObject]; this
0x18001c976  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x18001c97b  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18001c982  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18001c987  call    _CxxThrowException_0
0x18001c98d  call    __std_init_once_link_alternate_names_and_abort
```
