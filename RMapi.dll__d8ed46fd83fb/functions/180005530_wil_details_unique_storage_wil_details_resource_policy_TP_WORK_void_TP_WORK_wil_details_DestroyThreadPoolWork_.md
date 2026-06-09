# wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(_TP_WORK *)

- ea: `0x180005530`
- end: `0x180005596`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WORK@@@Z`
- size: `102`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000a534`
- `0x18000c31c`

## callees

- `0x180005530`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005573`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005573`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005552`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005552`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000556b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000556b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180005562`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180005562`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(
        struct _TP_WORK **a1,
        struct _TP_WORK *a2)
{
  struct _TP_WORK *v2; // rsi
  DWORD LastError; // edi

  v2 = *a1;
  if ( *a1 )
  {
    LastError = GetLastError();
    WaitForThreadpoolWorkCallbacks(v2, 1);
    CloseThreadpoolWork(v2);
    SetLastError(LastError);
    *a1 = a2;
  }
  else
  {
    *a1 = a2;
  }
}

```

## disassembly

```asm
0x180005530  mov     [rsp+arg_8], rbx
0x180005535  mov     [rsp+arg_10], rbp
0x18000553a  push    rsi
0x18000553b  sub     rsp, 20h
0x18000553f  mov     rsi, [rcx]
0x180005542  mov     rbp, rdx
0x180005545  mov     rbx, rcx
0x180005548  test    rsi, rsi
0x18000554b  jz      short loc_180005591
0x18000554d  mov     [rsp+28h+arg_0], rdi
0x180005552  call    cs:__imp_GetLastError
0x180005558  mov     edx, 1; fCancelPendingCallbacks
0x18000555d  mov     rcx, rsi; pwk
0x180005560  mov     edi, eax
0x180005562  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180005568  mov     rcx, rsi; pwk
0x18000556b  call    cs:__imp_CloseThreadpoolWork
0x180005571  mov     ecx, edi; dwErrCode
0x180005573  call    cs:__imp_SetLastError
0x180005579  mov     rdi, [rsp+28h+arg_0]
0x18000557e  mov     [rbx], rbp
0x180005581  mov     rbx, [rsp+28h+arg_8]
0x180005586  mov     rbp, [rsp+28h+arg_10]
0x18000558b  add     rsp, 20h
0x18000558f  pop     rsi
0x180005590  retn
0x180005591  mov     [rcx], rbp
0x180005594  jmp     short loc_180005581
```
