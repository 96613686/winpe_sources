# NgcIsoPregenPool::NgcIsoPregenPool(void)

- ea: `0x180047cfc`
- end: `0x180047e4d`
- name: `??0NgcIsoPregenPool@@AEAA@XZ`
- size: `337`
- prototype: `NgcIsoPregenPool *__fastcall(NgcIsoPregenPool *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180011108`

## callees

- `0x18000eeb8`
- `0x18000fa44`
- `0x180010360`
- `0x180011a60`
- `0x1800477fc`
- `0x180047cfc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180047d87`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180047d87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047d99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047d99`

## string_xrefs

- `0x180047e3b`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
NgcIsoPregenPool *__fastcall NgcIsoPregenPool::NgcIsoPregenPool(NgcIsoPregenPool *this)
{
  HANDLE Semaphore; // rbx
  const char *v2; // r9
  __int64 v3; // rdx
  __int64 v4; // rdx
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 *v7; // [rsp+40h] [rbp+8h] BYREF
  void *v8; // [rsp+48h] [rbp+10h]

  v7 = (__int64 *)this;
  v8 = &`NgcIsoPregenPool::Instance'::`2'::pregenPool;
  `NgcIsoPregenPool::Instance'::`2'::pregenPool = 0;
  std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(qword_1800C8E48);
  LODWORD(v7) = 0;
  ____0W4EventOptions_wil____V___unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA___QEAW4EventOptions_1__Z(
    &qword_1800C8E68,
    &v7);
  xmmword_1800C8E70 = 0;
  v7 = &qword_1800C8E80;
  qword_1800C8E80 = 0;
  Semaphore = CreateSemaphoreExW(0, 0, 0x7FFFFFFF, 0, 0, 0x1F0003u);
  if ( !Semaphore )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1CC8,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      v2);
  GetLastError();
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &qword_1800C8E80,
    Semaphore);
  qword_1800C8E88 = 0;
  xmmword_1800C8E90 = 0;
  qword_1800C8EA0 = 0;
  qword_1800C8EA8 = 0;
  qword_1800C8EB0 = 0;
  std::_Container_base12::_Alloc_proxy<std::allocator<std::_Container_proxy>>(&xmmword_1800C8E90, v3);
  qword_1800C8EB8 = 0;
  xmmword_1800C8EC0 = 0;
  qword_1800C8ED0 = 0;
  qword_1800C8ED8 = 0;
  qword_1800C8EE0 = 0;
  std::_Container_base12::_Alloc_proxy<std::allocator<std::_Container_proxy>>(&xmmword_1800C8EC0, v4);
  return (NgcIsoPregenPool *)&`NgcIsoPregenPool::Instance'::`2'::pregenPool;
}

```

## disassembly

```asm
0x180047cfc  mov     rax, rsp
0x180047cff  mov     [rax+18h], rbx
0x180047d03  mov     [rax+20h], rbp
0x180047d07  mov     [rax+8], rcx
0x180047d0b  push    rsi
0x180047d0c  sub     rsp, 30h
0x180047d10  lea     rbp, ?pregenPool@?1??Instance@NgcIsoPregenPool@@SAAEAV2@XZ@4V2@A; NgcIsoPregenPool `NgcIsoPregenPool::Instance(void)'::`2'::pregenPool
0x180047d17  mov     [rax+10h], rbp
0x180047d1b  mov     cs:?pregenPool@?1??Instance@NgcIsoPregenPool@@SAAEAV2@XZ@4V2@A, 0; NgcIsoPregenPool `NgcIsoPregenPool::Instance(void)'::`2'::pregenPool
0x180047d22  lea     rcx, qword_1800C8E48
0x180047d29  call    ??0?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x180047d2e  nop
0x180047d2f  mov     dword ptr [rsp+38h+arg_0], 0
0x180047d37  lea     rdx, [rsp+38h+arg_0]
0x180047d3c  lea     rcx, qword_1800C8E68
0x180047d43  call    ??$?0W4EventOptions@wil@@$$V@?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z
0x180047d48  nop
0x180047d49  xorps   xmm0, xmm0
0x180047d4c  movups  cs:xmmword_1800C8E70, xmm0
0x180047d53  lea     rsi, qword_1800C8E80
0x180047d5a  mov     [rsp+38h+arg_0], rsi
0x180047d5f  mov     cs:qword_1800C8E80, 0
0x180047d6a  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180047d72  mov     [rsp+38h+dwFlags], 0; dwFlags
0x180047d7a  xor     r9d, r9d; lpName
0x180047d7d  xor     edx, edx; lInitialCount
0x180047d7f  xor     ecx, ecx; lpSemaphoreAttributes
0x180047d81  mov     r8d, 7FFFFFFFh; lMaximumCount
0x180047d87  call    cs:__imp_CreateSemaphoreExW
0x180047d8d  mov     rbx, rax
0x180047d90  test    rax, rax
0x180047d93  jz      loc_180047E36
0x180047d99  call    cs:__imp_GetLastError
0x180047d9f  mov     rdx, rbx
0x180047da2  mov     rcx, rsi
0x180047da5  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180047daa  nop
0x180047dab  xor     eax, eax
0x180047dad  mov     cs:qword_1800C8E88, rax
0x180047db4  lea     rcx, xmmword_1800C8E90
0x180047dbb  xorps   xmm0, xmm0
0x180047dbe  movdqa  cs:xmmword_1800C8E90, xmm0
0x180047dc6  mov     cs:qword_1800C8EA0, rax
0x180047dcd  mov     cs:qword_1800C8EA8, rax
0x180047dd4  mov     cs:qword_1800C8EB0, rax
0x180047ddb  call    ??$_Alloc_proxy@V?$allocator@U_Container_proxy@std@@@std@@@_Container_base12@std@@QEAAX$$QEAV?$allocator@U_Container_proxy@std@@@1@@Z; std::_Container_base12::_Alloc_proxy<std::allocator<std::_Container_proxy>>(std::allocator<std::_Container_proxy> &&)
0x180047de0  nop
0x180047de1  xor     ecx, ecx
0x180047de3  mov     cs:qword_1800C8EB8, rcx
0x180047dea  lea     rcx, xmmword_1800C8EC0
0x180047df1  xorps   xmm0, xmm0
0x180047df4  movdqa  cs:xmmword_1800C8EC0, xmm0
0x180047dfc  mov     cs:qword_1800C8ED0, 0
0x180047e07  mov     cs:qword_1800C8ED8, 0
0x180047e12  mov     cs:qword_1800C8EE0, 0
0x180047e1d  call    ??$_Alloc_proxy@V?$allocator@U_Container_proxy@std@@@std@@@_Container_base12@std@@QEAAX$$QEAV?$allocator@U_Container_proxy@std@@@1@@Z; std::_Container_base12::_Alloc_proxy<std::allocator<std::_Container_proxy>>(std::allocator<std::_Container_proxy> &&)
0x180047e22  nop
0x180047e23  mov     rax, rbp
0x180047e26  mov     rbx, [rsp+38h+arg_10]
0x180047e2b  mov     rbp, [rsp+38h+arg_18]
0x180047e30  add     rsp, 30h
0x180047e34  pop     rsi
0x180047e35  retn
0x180047e36  mov     rcx, [rsp+38h]; this
0x180047e3b  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180047e42  mov     edx, 1CC8h; void *
0x180047e47  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
