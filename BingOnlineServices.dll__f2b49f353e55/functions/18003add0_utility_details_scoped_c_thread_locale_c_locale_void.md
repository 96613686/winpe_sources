# utility::details::scoped_c_thread_locale::c_locale(void)

- ea: `0x18003add0`
- end: `0x18003ae8c`
- name: `?c_locale@scoped_c_thread_locale@details@utility@@SAPEAU__crt_locale_pointers@@XZ`
- size: `188`
- prototype: `struct __crt_locale_pointers *(void)`
- caller_count: `8`
- callee_count: `6`
- tags: ``

## callers

- `0x180051100`
- `0x1800511c0`
- `0x180052988`
- `0x180052d0c`
- `0x180054bcc`
- `0x180054d50`
- `0x1800551b4`
- `0x180055208`

## callees

- `0x18000529c`
- `0x180005e9c`
- `0x180012144`
- `0x18003a4e8`
- `0x18003aa1c`
- `0x18003add0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__create_locale` at `0x18003ae15`
- `api-ms-win-crt-private-l1-1-0!_o__create_locale` at `0x18003ae15`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ade9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ade9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ae78`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ae78`

## string_xrefs

- `0x18003ae23`: `Unable to create 'C' locale.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct __crt_locale_pointers *utility::details::scoped_c_thread_locale::c_locale(void)
{
  __int64 *v0; // rbx
  _locale_t *v1; // rbx
  _locale_t locale; // rax
  __int64 v3; // rcx
  __int64 v4; // rbx
  _QWORD pExceptionObject[5]; // [rsp+20h] [rbp-28h] BYREF

  EnterCriticalSection(&utility::details::g_c_localeLock);
  v0 = (__int64 *)qword_18008E080;
  if ( !qword_18008E080 )
  {
    v1 = (_locale_t *)operator new(8u);
    *v1 = 0;
    locale = _create_locale(0, "C");
    *v1 = locale;
    if ( !locale )
    {
      std::runtime_error::runtime_error((std::runtime_error *)pExceptionObject, "Unable to create 'C' locale.");
      throw (std::runtime_error *)pExceptionObject;
    }
    pExceptionObject[0] = lambda_0e274f08bb789540ecdc3d483432214a_::_lambda_invoker_cdecl_;
    pExceptionObject[1] = v1;
    std::unique_ptr<__crt_locale_pointers *,void (*)(__crt_locale_pointers * *)>::operator=<void (*)(__crt_locale_pointers * *),0>(
      v3,
      pExceptionObject);
    std::unique_ptr<__crt_locale_pointers *,void (*)(__crt_locale_pointers * *)>::~unique_ptr<__crt_locale_pointers *,void (*)(__crt_locale_pointers * *)>(pExceptionObject);
    v0 = (__int64 *)qword_18008E080;
  }
  v4 = *v0;
  LeaveCriticalSection(&utility::details::g_c_localeLock);
  return (struct __crt_locale_pointers *)v4;
}

```

## disassembly

```asm
0x18003add0  mov     [rsp+arg_8], rbx
0x18003add5  push    rdi
0x18003add6  sub     rsp, 40h
0x18003adda  lea     rdi, ?g_c_localeLock@details@utility@@3Vcritical_section_impl@1pplx@@A; pplx::details::critical_section_impl utility::details::g_c_localeLock
0x18003ade1  mov     [rsp+48h+arg_0], rdi
0x18003ade6  mov     rcx, rdi; lpCriticalSection
0x18003ade9  call    cs:__imp_EnterCriticalSection
0x18003adef  nop
0x18003adf0  mov     rbx, cs:qword_18008E080
0x18003adf7  test    rbx, rbx
0x18003adfa  jnz     short loc_18003AE72
0x18003adfc  lea     ecx, [rbx+8]; Size
0x18003adff  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003ae04  mov     rbx, rax
0x18003ae07  xor     eax, eax
0x18003ae09  mov     [rbx], rax
0x18003ae0c  lea     rdx, Locale; "C"
0x18003ae13  xor     ecx, ecx; Category
0x18003ae15  call    cs:__imp__create_locale
0x18003ae1b  mov     [rbx], rax
0x18003ae1e  test    rax, rax
0x18003ae21  jnz     short loc_18003AE46
0x18003ae23  lea     rdx, aUnableToCreate; "Unable to create 'C' locale."
0x18003ae2a  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18003ae2f  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x18003ae34  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18003ae3b  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18003ae40  call    _CxxThrowException_0
0x18003ae46  lea     rax, _lambda_0e274f08bb789540ecdc3d483432214a____lambda_invoker_cdecl_
0x18003ae4d  mov     [rsp+48h+pExceptionObject], rax
0x18003ae52  mov     [rsp+48h+var_20], rbx
0x18003ae57  lea     rdx, [rsp+48h+pExceptionObject]
0x18003ae5c  call    ??$?4P6AXPEAPEAU__crt_locale_pointers@@@Z$0A@@?$unique_ptr@PEAU__crt_locale_pointers@@P6AXPEAPEAU1@@Z@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<__crt_locale_pointers *,void (*)(__crt_locale_pointers * *)>::operator=<void (*)(__crt_locale_pointers * *),0>(std::unique_ptr<__crt_locale_pointers *,void (*)(__crt_locale_pointers * *)> &&)
0x18003ae61  lea     rcx, [rsp+48h+pExceptionObject]
0x18003ae66  call    ??1?$unique_ptr@PEAU__crt_locale_pointers@@P6AXPEAPEAU1@@Z@std@@QEAA@XZ; std::unique_ptr<__crt_locale_pointers *,void (*)(__crt_locale_pointers * *)>::~unique_ptr<__crt_locale_pointers *,void (*)(__crt_locale_pointers * *)>(void)
0x18003ae6b  mov     rbx, cs:qword_18008E080
0x18003ae72  mov     rbx, [rbx]
0x18003ae75  mov     rcx, rdi; lpCriticalSection
0x18003ae78  call    cs:__imp_LeaveCriticalSection
0x18003ae7e  mov     rax, rbx
0x18003ae81  mov     rbx, [rsp+48h+arg_8]
0x18003ae86  add     rsp, 40h
0x18003ae8a  pop     rdi
0x18003ae8b  retn
```
