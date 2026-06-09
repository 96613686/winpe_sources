# SingletonHelpers::SingletonHelper::SingletonHelper(wil::basic_zstring_view<wchar_t> const &,wil::basic_zstring_view<wchar_t> const &)

- ea: `0x1800218ec`
- end: `0x180021a1f`
- name: `??0SingletonHelper@SingletonHelpers@@QEAA@AEBV?$basic_zstring_view@_W@wil@@0@Z`
- size: `307`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x180023604`

## callees

- `0x180004f80`
- `0x180008968`
- `0x180016bac`
- `0x18001a878`
- `0x18001d838`
- `0x18001d8c8`
- `0x180021200`
- `0x180021310`
- `0x18002154c`
- `0x1800218ec`
- `0x180022078`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800219da`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800219da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800219e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800219e8`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall SingletonHelpers::SingletonHelper::SingletonHelper(__int64 a1)
{
  const WCHAR *v2; // rbx
  __int64 v3; // rdx
  __int64 v4; // r8
  void *v5; // rax
  __int64 v6; // rax
  void *v7; // rdx
  HANDLE Mutex; // rbx
  unsigned int v9; // r8d
  const char *v10; // r9
  _BYTE v12[32]; // [rsp+20h] [rbp-58h] BYREF
  _BYTE v13[32]; // [rsp+40h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  *(_QWORD *)a1 = &SingletonHelpers::SingletonHelper::`vftable';
  std::wstring::wstring(a1 + 8);
  std::wstring::wstring(a1 + 40);
  v2 = (const WCHAR *)(a1 + 72);
  std::wstring::wstring(a1 + 72, v3, v4);
  *(_QWORD *)(a1 + 104) = 0;
  *(_QWORD *)(a1 + 112) = 0;
  *(_DWORD *)(a1 + 120) = 0;
  ConnectionlessEndpoint::ConnectionlessEndpoint((ConnectionlessEndpoint *)(a1 + 128));
  *(_QWORD *)(a1 + 320) = 0;
  v5 = (void *)std::operator+<wchar_t>(v13, a1 + 8);
  v6 = std::wstring::_Append<wchar_t>(v5);
  std::wstring::wstring(v12, v6);
  std::wstring::operator=(a1 + 72, v12);
  std::wstring::_Tidy_deallocate(v12);
  std::wstring::_Tidy_deallocate(v13);
  if ( *(_QWORD *)(a1 + 96) > 7u )
    v2 = *(const WCHAR **)v2;
  Mutex = CreateMutexExW(0, v2, 0, 0x1F0001u);
  if ( !Mutex )
    wil::details::in1diag3::Throw_GetLastError(retaddr, v7, v9, v10);
  GetLastError();
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    a1 + 104,
    Mutex);
  return a1;
}

```

## disassembly

```asm
0x1800218ec  mov     [rsp+arg_8], rbx
0x1800218f1  mov     [rsp+arg_10], rsi
0x1800218f6  mov     [rsp+arg_0], rcx
0x1800218fb  push    rdi
0x1800218fc  push    r14
0x1800218fe  push    r15
0x180021900  sub     rsp, 60h
0x180021904  mov     rbx, r8
0x180021907  mov     r14, rcx
0x18002190a  lea     rax, ??_7SingletonHelper@SingletonHelpers@@6B@; const SingletonHelpers::SingletonHelper::`vftable'
0x180021911  mov     [rcx], rax
0x180021914  add     rcx, 8
0x180021918  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x18002191d  nop
0x18002191e  lea     rsi, [r14+28h]
0x180021922  mov     rdx, rbx
0x180021925  mov     rcx, rsi
0x180021928  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x18002192d  nop
0x18002192e  lea     rbx, [r14+48h]
0x180021932  mov     rcx, rbx
0x180021935  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002193a  nop
0x18002193b  mov     qword ptr [r14+68h], 0
0x180021943  mov     qword ptr [r14+70h], 0
0x18002194b  mov     dword ptr [r14+78h], 0
0x180021953  lea     rcx, [r14+80h]; this
0x18002195a  call    ??0ConnectionlessEndpoint@@QEAA@XZ; ConnectionlessEndpoint::ConnectionlessEndpoint(void)
0x18002195f  nop
0x180021960  mov     qword ptr [r14+140h], 0
0x18002196b  lea     rdx, [r14+8]
0x18002196f  lea     rcx, [rsp+78h+var_38]
0x180021974  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@AEBV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring const &,wchar_t const * const)
0x180021979  nop
0x18002197a  mov     r8, [rsi+10h]
0x18002197e  cmp     qword ptr [rsi+18h], 7
0x180021983  jbe     short loc_180021988
0x180021985  mov     rsi, [rsi]
0x180021988  mov     rdx, rsi
0x18002198b  mov     rcx, rax; Src
0x18002198e  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x180021993  mov     rdx, rax
0x180021996  lea     rcx, [rsp+78h+var_58]
0x18002199b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x1800219a0  lea     rdx, [rsp+78h+var_58]
0x1800219a5  mov     rcx, rbx
0x1800219a8  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800219ad  lea     rcx, [rsp+78h+var_58]
0x1800219b2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800219b7  nop
0x1800219b8  lea     rcx, [rsp+78h+var_38]
0x1800219bd  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800219c2  cmp     qword ptr [rbx+18h], 7
0x1800219c7  jbe     short loc_1800219CC
0x1800219c9  mov     rbx, [rbx]
0x1800219cc  mov     r9d, 1F0001h; dwDesiredAccess
0x1800219d2  xor     r8d, r8d; dwFlags
0x1800219d5  mov     rdx, rbx; lpName
0x1800219d8  xor     ecx, ecx; lpMutexAttributes
0x1800219da  call    cs:__imp_CreateMutexExW
0x1800219e0  mov     rbx, rax
0x1800219e3  test    rax, rax
0x1800219e6  jz      short loc_180021A14
0x1800219e8  call    cs:__imp_GetLastError
0x1800219ee  mov     rdx, rbx
0x1800219f1  lea     rcx, [r14+68h]
0x1800219f5  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800219fa  nop
0x1800219fb  mov     rax, r14
0x1800219fe  lea     r11, [rsp+78h+var_18]
0x180021a03  mov     rbx, [r11+28h]
0x180021a07  mov     rsi, [r11+30h]
0x180021a0b  mov     rsp, r11
0x180021a0e  pop     r15
0x180021a10  pop     r14
0x180021a12  pop     rdi
0x180021a13  retn
0x180021a14  mov     rcx, [rsp+78h]; this
0x180021a19  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
