# wil::details::unique_storage<wil::details::resource_policy<_TP_POOL *,void (*)(_TP_POOL *),&CloseThreadpool(_TP_POOL *),wistd::integral_constant<unsigned __int64,0>,_TP_POOL *,_TP_POOL *,0,std::nullptr_t>>::reset(_TP_POOL *)

- ea: `0x180006950`
- end: `0x1800069a8`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_POOL@@P6AXPEAU1@@Z$1?CloseThreadpool@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_POOL@@@Z`
- size: `88`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180009f78`
- `0x1800196c0`

## callees

- `0x180006950`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006998`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006998`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006985`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006985`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180006990`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180006990`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<_TP_POOL *,void (*)(_TP_POOL *),&void CloseThreadpool(_TP_POOL *),wistd::integral_constant<unsigned __int64,0>,_TP_POOL *,_TP_POOL *,0,std::nullptr_t>>::reset(
        struct _TP_POOL **a1,
        struct _TP_POOL *a2)
{
  struct _TP_POOL *v2; // rbp
  DWORD LastError; // edi

  v2 = *a1;
  if ( *a1 )
  {
    LastError = GetLastError();
    CloseThreadpool(v2);
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
0x180006950  mov     [rsp+arg_8], rbx
0x180006955  mov     [rsp+arg_10], rbp
0x18000695a  push    rsi
0x18000695b  sub     rsp, 20h
0x18000695f  mov     rbp, [rcx]
0x180006962  mov     rsi, rdx
0x180006965  mov     rbx, rcx
0x180006968  test    rbp, rbp
0x18000696b  jnz     short loc_180006980
0x18000696d  mov     [rcx], rdx
0x180006970  mov     rbx, [rsp+28h+arg_8]
0x180006975  mov     rbp, [rsp+28h+arg_10]
0x18000697a  add     rsp, 20h
0x18000697e  pop     rsi
0x18000697f  retn
0x180006980  mov     [rsp+28h+arg_0], rdi
0x180006985  call    cs:__imp_GetLastError
0x18000698b  mov     rcx, rbp; ptpp
0x18000698e  mov     edi, eax
0x180006990  call    cs:__imp_CloseThreadpool
0x180006996  mov     ecx, edi; dwErrCode
0x180006998  call    cs:__imp_SetLastError
0x18000699e  mov     rdi, [rsp+28h+arg_0]
0x1800069a3  mov     [rbx], rsi
0x1800069a6  jmp     short loc_180006970
```
