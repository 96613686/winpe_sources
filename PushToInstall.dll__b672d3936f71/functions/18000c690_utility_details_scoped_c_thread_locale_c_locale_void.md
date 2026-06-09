# utility::details::scoped_c_thread_locale::c_locale(void)

- ea: `0x18000c690`
- end: `0x18000c783`
- name: `?c_locale@scoped_c_thread_locale@details@utility@@SAPEAU__crt_locale_pointers@@XZ`
- size: `243`
- prototype: `struct __crt_locale_pointers *(void)`
- caller_count: `4`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180008ce0`
- `0x180008e40`
- `0x18000a190`
- `0x18000bc30`

## callees

- `0x18000c610`
- `0x18000c690`
- `0x18000d748`
- `0x18000d75c`
- `0x18000dc43`
- `0x18004f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__create_locale` at `0x18000c6f7`
- `api-ms-win-crt-private-l1-1-0!_o__create_locale` at `0x18000c6f7`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000c73b`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000c73b`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000c6ae`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000c6ae`

## string_xrefs

- `0x18000c75a`: `Unable to create 'C' locale.`

## pseudocode

```c
struct __crt_locale_pointers *utility::details::scoped_c_thread_locale::c_locale(void)
{
  _locale_t *v0; // rbx
  _locale_t locale; // rax
  struct SERVICE_STATUS_HANDLE__ *v2; // rdx
  PushToInstallCallback *v3; // rcx
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
    v3 = (PushToInstallCallback *)qword_180065038;
    qword_180065038 = (__int64)v0;
    if ( v3 )
      utility::details::g_c_locale(v3, v2);
    utility::details::g_c_locale = (void (__fastcall *)(PushToInstallCallback *__hidden, struct SERVICE_STATUS_HANDLE__ *))_utility::details::scoped_c_thread_locale::c_locale_::_2_::_lambda_1_::operator()_::_2_::_lambda_1_::_lambda_invoker_cdecl_;
    if ( !InitOnceComplete(&utility::details::g_c_localeFlag, 0, 0) )
      _std_init_once_link_alternate_names_and_abort(v5, v4);
  }
  return *(struct __crt_locale_pointers **)qword_180065038;
}

```

## disassembly

```asm
0x18000c690  mov     [rsp+arg_8], rbx
0x18000c695  push    rdi
0x18000c696  sub     rsp, 50h
0x18000c69a  xor     r9d, r9d; lpContext
0x18000c69d  lea     r8, [rsp+58h+fPending]; fPending
0x18000c6a2  xor     edx, edx; dwFlags
0x18000c6a4  lea     rdi, ?g_c_localeFlag@details@utility@@3Uonce_flag@std@@A; std::once_flag utility::details::g_c_localeFlag
0x18000c6ab  mov     rcx, rdi; lpInitOnce
0x18000c6ae  call    cs:__imp___std_init_once_begin_initialize
0x18000c6b4  test    eax, eax
0x18000c6b6  jnz     short loc_18000C6BF
0x18000c6b8  mov     ecx, 5
0x18000c6bd  int     29h; Win8: RtlFailFast(ecx)
0x18000c6bf  cmp     [rsp+58h+fPending], 0
0x18000c6c4  jz      short loc_18000C745
0x18000c6c6  mov     [rsp+58h+var_38], rdi
0x18000c6cb  mov     [rsp+58h+var_30], 4
0x18000c6d3  mov     ecx, 8; Size
0x18000c6d8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c6dd  mov     rbx, rax
0x18000c6e0  test    rax, rax
0x18000c6e3  jz      short loc_18000C6EC
0x18000c6e5  xor     eax, eax
0x18000c6e7  mov     [rbx], rax
0x18000c6ea  jmp     short loc_18000C6EE
0x18000c6ec  xor     ebx, ebx
0x18000c6ee  lea     rdx, Locale; "C"
0x18000c6f5  xor     ecx, ecx; Category
0x18000c6f7  call    cs:__imp__create_locale
0x18000c6fd  mov     [rbx], rax
0x18000c700  test    rax, rax
0x18000c703  jz      short loc_18000C75A
0x18000c705  mov     rcx, cs:qword_180065038
0x18000c70c  mov     cs:qword_180065038, rbx
0x18000c713  test    rcx, rcx
0x18000c716  jz      short loc_18000C725
0x18000c718  mov     rax, cs:?g_c_locale@details@utility@@3V?$unique_ptr@PEAU__crt_locale_pointers@@P6AXPEAPEAU1@@Z@std@@A; std::unique_ptr<__crt_locale_pointers *,void (*)(__crt_locale_pointers * *)> utility::details::g_c_locale
0x18000c71f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c724  nop
0x18000c725  lea     rax, __utility__details__scoped_c_thread_locale__c_locale____2____lambda_1___operator______2____lambda_1____lambda_invoker_cdecl_
0x18000c72c  mov     cs:?g_c_locale@details@utility@@3V?$unique_ptr@PEAU__crt_locale_pointers@@P6AXPEAPEAU1@@Z@std@@A, rax; std::unique_ptr<__crt_locale_pointers *,void (*)(__crt_locale_pointers * *)> utility::details::g_c_locale
0x18000c733  xor     r8d, r8d; lpContext
0x18000c736  xor     edx, edx; dwFlags
0x18000c738  mov     rcx, rdi; lpInitOnce
0x18000c73b  call    cs:__imp_InitOnceComplete
0x18000c741  test    eax, eax
0x18000c743  jz      short loc_18000C77D
0x18000c745  mov     rax, cs:qword_180065038
0x18000c74c  mov     rax, [rax]
0x18000c74f  mov     rbx, [rsp+58h+arg_8]
0x18000c754  add     rsp, 50h
0x18000c758  pop     rdi
0x18000c759  retn
0x18000c75a  lea     rdx, aUnableToCreate; "Unable to create 'C' locale."
0x18000c761  lea     rcx, [rsp+58h+pExceptionObject]; this
0x18000c766  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x18000c76b  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18000c772  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18000c777  call    _CxxThrowException_0
0x18000c77d  call    __std_init_once_link_alternate_names_and_abort
```
