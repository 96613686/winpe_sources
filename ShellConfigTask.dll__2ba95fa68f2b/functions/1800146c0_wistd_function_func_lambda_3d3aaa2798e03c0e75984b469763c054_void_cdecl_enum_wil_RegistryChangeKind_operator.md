# wistd::__function::__func__lambda_3d3aaa2798e03c0e75984b469763c054__void___cdecl(enum_wil::RegistryChangeKind)_::operator()

- ea: `0x1800146c0`
- end: `0x180014752`
- name: `wistd::__function::__func__lambda_3d3aaa2798e03c0e75984b469763c054__void___cdecl(enum_wil::RegistryChangeKind)_::operator()`
- size: `146`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000c5d4`
- `0x180013d90`
- `0x1800146c0`
- `0x18001cea8`
- `0x1800222c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180014726`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180014726`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800146ff`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800146ff`

## string_xrefs

- `0x180014740`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
char __fastcall wistd::__function::__func__lambda_3d3aaa2798e03c0e75984b469763c054__void___cdecl_enum_wil::RegistryChangeKind__::operator()(
        __int64 a1,
        __int64 a2)
{
  int v3; // eax
  volatile signed __int32 *v4; // rbx
  const char *v5; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v8; // [rsp+38h] [rbp+10h] BYREF

  v8 = a2;
  LOBYTE(v3) = IsNDUPComplete();
  if ( (_BYTE)v3 )
  {
    v4 = *tip2::tip_test<tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>>::ensure_data(*(volatile signed __int32 ***)(a1 + 16));
    v8 = (__int64)v4;
    if ( v4 )
      _InterlockedIncrement(v4 + 70);
    EnterCriticalSection((LPCRITICAL_SECTION)v4 + 5);
    ++*((_DWORD *)v4 + 60);
    *((_DWORD *)v4 + 68) = 4;
    tip2::test_data_control<tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>>::~test_data_control<tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>>(&v8);
    v3 = SetEvent(**(HANDLE **)(a1 + 8));
    if ( !v3 )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA01,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
        v5);
  }
  return v3;
}

```

## disassembly

```asm
0x1800146c0  mov     [rsp+arg_0], rbx
0x1800146c5  mov     [rsp+arg_8], rdx
0x1800146ca  push    rdi
0x1800146cb  sub     rsp, 20h
0x1800146cf  mov     rdi, rcx
0x1800146d2  call    ?IsNDUPComplete@@YA_NXZ; IsNDUPComplete(void)
0x1800146d7  test    al, al
0x1800146d9  jz      short loc_180014730
0x1800146db  mov     rcx, [rdi+10h]
0x1800146df  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_WaitForOOBEOrNDUPTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_WaitForOOBEOrNDUPTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>>::ensure_data(void)
0x1800146e4  mov     rbx, [rax]
0x1800146e7  mov     [rsp+28h+arg_8], rbx
0x1800146ec  test    rbx, rbx
0x1800146ef  jz      short loc_1800146F8
0x1800146f1  lock inc dword ptr [rbx+118h]
0x1800146f8  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800146ff  call    cs:__imp_EnterCriticalSection
0x180014705  inc     dword ptr [rbx+0F0h]
0x18001470b  lea     rcx, [rsp+28h+arg_8]
0x180014710  mov     dword ptr [rbx+110h], 4
0x18001471a  call    ??1?$test_data_control@V?$merged_data@U_tip_WaitForOOBEOrNDUPTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>>::~test_data_control<tip2::details::merged_data<_tip_WaitForOOBEOrNDUPTipTest,_tip_WaitForOOBEOrNDUPTipTest>>(void)
0x18001471f  mov     rcx, [rdi+8]
0x180014723  mov     rcx, [rcx]; hEvent
0x180014726  call    cs:__imp_SetEvent
0x18001472c  test    eax, eax
0x18001472e  jz      short loc_18001473B
0x180014730  mov     rbx, [rsp+28h+arg_0]
0x180014735  add     rsp, 20h
0x180014739  pop     rdi
0x18001473a  retn
0x18001473b  mov     rcx, [rsp+28h]; this
0x180014740  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180014747  mov     edx, 0A01h; void *
0x18001474c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
