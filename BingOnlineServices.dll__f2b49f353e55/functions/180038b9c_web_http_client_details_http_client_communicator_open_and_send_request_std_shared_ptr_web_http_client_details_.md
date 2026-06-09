# web::http::client::details::_http_client_communicator::open_and_send_request(std::shared_ptr<web::http::client::details::request_context> const &)

- ea: `0x180038b9c`
- end: `0x180038c72`
- name: `?open_and_send_request@_http_client_communicator@details@client@http@web@@AEAAXAEBV?$shared_ptr@Vrequest_context@details@client@http@web@@@std@@@Z`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800358a0`

## callees

- `0x180002c2c`
- `0x180002ca8`
- `0x180004fa0`
- `0x180038b9c`
- `0x180039654`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038bd8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038bd8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180038c07`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180038c07`

## string_xrefs

- `0x180038c14`: `Open failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall web::http::client::details::_http_client_communicator::open_and_send_request(_BYTE *a1, __int64 *a2)
{
  unsigned int v4; // esi
  struct _RTL_CRITICAL_SECTION *v5; // rdi
  __int64 v6; // rbx
  _BYTE v8[32]; // [rsp+28h] [rbp-40h] BYREF

  if ( a1[744] )
    return (*(__int64 (__fastcall **)(_BYTE *, __int64 *))(*(_QWORD *)a1 + 16LL))(a1, a2);
  v4 = 0;
  v5 = (struct _RTL_CRITICAL_SECTION *)(a1 + 752);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 752));
  if ( !a1[744] )
  {
    v4 = (*(__int64 (__fastcall **)(_BYTE *))(*(_QWORD *)a1 + 8LL))(a1);
    if ( !v4 )
      a1[744] = 1;
  }
  LeaveCriticalSection(v5);
  if ( !v4 )
    return (*(__int64 (__fastcall **)(_BYTE *, __int64 *))(*(_QWORD *)a1 + 16LL))(a1, a2);
  v6 = *a2;
  std::wstring::wstring(v8, L"Open failed");
  web::http::client::details::request_context::report_error(v6, v4, v8);
  return std::wstring::_Tidy_deallocate(v8);
}

```

## disassembly

```asm
0x180038b9c  mov     [rsp+arg_10], rbx
0x180038ba1  push    rsi
0x180038ba2  push    rdi
0x180038ba3  push    r14
0x180038ba5  sub     rsp, 50h
0x180038ba9  mov     rax, cs:__security_cookie
0x180038bb0  xor     rax, rsp
0x180038bb3  mov     [rsp+68h+var_20], rax
0x180038bb8  mov     r14, rdx
0x180038bbb  mov     rbx, rcx
0x180038bbe  cmp     byte ptr [rcx+2E8h], 0
0x180038bc5  jnz     short loc_180038C42
0x180038bc7  xor     esi, esi
0x180038bc9  lea     rdi, [rcx+2F0h]
0x180038bd0  mov     [rsp+68h+var_48], rdi
0x180038bd5  mov     rcx, rdi; lpCriticalSection
0x180038bd8  call    cs:__imp_EnterCriticalSection
0x180038bde  nop
0x180038bdf  cmp     [rbx+2E8h], sil
0x180038be6  jnz     short loc_180038C04
0x180038be8  mov     rax, [rbx]
0x180038beb  mov     rcx, rbx
0x180038bee  mov     rax, [rax+8]
0x180038bf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038bf7  mov     esi, eax
0x180038bf9  test    eax, eax
0x180038bfb  jnz     short loc_180038C04
0x180038bfd  mov     byte ptr [rbx+2E8h], 1
0x180038c04  mov     rcx, rdi; lpCriticalSection
0x180038c07  call    cs:__imp_LeaveCriticalSection
0x180038c0d  test    esi, esi
0x180038c0f  jz      short loc_180038C42
0x180038c11  mov     rbx, [r14]
0x180038c14  lea     rdx, aOpenFailed; "Open failed"
0x180038c1b  lea     rcx, [rsp+68h+var_40]
0x180038c20  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180038c25  nop
0x180038c26  lea     r8, [rsp+68h+var_40]
0x180038c2b  mov     edx, esi
0x180038c2d  mov     rcx, rbx
0x180038c30  call    ?report_error@request_context@details@client@http@web@@QEAAXKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::http::client::details::request_context::report_error(ulong,std::wstring const &)
0x180038c35  nop
0x180038c36  lea     rcx, [rsp+68h+var_40]
0x180038c3b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180038c40  jmp     short loc_180038C54
0x180038c42  mov     rax, [rbx]
0x180038c45  mov     rdx, r14
0x180038c48  mov     rcx, rbx
0x180038c4b  mov     rax, [rax+10h]
0x180038c4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038c54  mov     rcx, [rsp+68h+var_20]
0x180038c59  xor     rcx, rsp; StackCookie
0x180038c5c  call    __security_check_cookie
0x180038c61  mov     rbx, [rsp+68h+arg_10]
0x180038c69  add     rsp, 50h
0x180038c6d  pop     r14
0x180038c6f  pop     rdi
0x180038c70  pop     rsi
0x180038c71  retn
```
