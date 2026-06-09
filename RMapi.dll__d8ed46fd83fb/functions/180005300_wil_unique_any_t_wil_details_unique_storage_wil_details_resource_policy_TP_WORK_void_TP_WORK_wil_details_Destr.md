# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>> &&)

- ea: `0x180005300`
- end: `0x18000537f`
- name: `??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z`
- size: `127`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000521c`
- `0x180009e14`

## callees

- `0x180005300`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000535e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000535e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000533d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000533d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180005356`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180005356`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18000534d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18000534d`

## pseudocode

```c
struct _TP_WORK **__fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>::operator=(
        struct _TP_WORK **a1,
        struct _TP_WORK **a2)
{
  struct _TP_WORK *v5; // rbp
  struct _TP_WORK *v6; // r14
  DWORD LastError; // edi

  if ( a1 != a2 )
  {
    v5 = *a1;
    v6 = *a2;
    if ( *a1 )
    {
      LastError = GetLastError();
      WaitForThreadpoolWorkCallbacks(v5, 1);
      CloseThreadpoolWork(v5);
      SetLastError(LastError);
    }
    *a1 = v6;
    *a2 = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x180005300  mov     [rsp+arg_18], rbx
0x180005305  push    rsi
0x180005306  sub     rsp, 20h
0x18000530a  mov     rsi, rdx
0x18000530d  mov     rbx, rcx
0x180005310  cmp     rcx, rdx
0x180005313  jnz     short loc_180005323
0x180005315  mov     rax, rbx
0x180005318  mov     rbx, [rsp+28h+arg_18]
0x18000531d  add     rsp, 20h
0x180005321  pop     rsi
0x180005322  retn
0x180005323  mov     [rsp+28h+arg_0], rbp
0x180005328  mov     rbp, [rcx]
0x18000532b  mov     [rsp+28h+arg_10], r14
0x180005330  mov     r14, [rdx]
0x180005333  test    rbp, rbp
0x180005336  jz      short loc_180005369
0x180005338  mov     [rsp+28h+arg_8], rdi
0x18000533d  call    cs:__imp_GetLastError
0x180005343  mov     edx, 1; fCancelPendingCallbacks
0x180005348  mov     rcx, rbp; pwk
0x18000534b  mov     edi, eax
0x18000534d  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180005353  mov     rcx, rbp; pwk
0x180005356  call    cs:__imp_CloseThreadpoolWork
0x18000535c  mov     ecx, edi; dwErrCode
0x18000535e  call    cs:__imp_SetLastError
0x180005364  mov     rdi, [rsp+28h+arg_8]
0x180005369  mov     rbp, [rsp+28h+arg_0]
0x18000536e  mov     [rbx], r14
0x180005371  mov     r14, [rsp+28h+arg_10]
0x180005376  mov     qword ptr [rsi], 0
0x18000537d  jmp     short loc_180005315
```
