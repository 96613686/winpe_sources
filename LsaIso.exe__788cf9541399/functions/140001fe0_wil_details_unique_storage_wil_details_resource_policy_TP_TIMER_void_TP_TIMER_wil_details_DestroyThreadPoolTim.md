# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x140001fe0`
- end: `0x140002037`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `87`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140002aa4`
- `0x140002b9c`

## callees

- `0x140001fe0`
- `0x140002a40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140002014`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140002014`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002002`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002002`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
        struct _TP_TIMER **a1,
        struct _TP_TIMER *a2)
{
  struct _TP_TIMER *v2; // rbp
  DWORD LastError; // edi

  v2 = *a1;
  if ( *a1 )
  {
    LastError = GetLastError();
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v2);
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
0x140001fe0  mov     [rsp+arg_8], rbx
0x140001fe5  mov     [rsp+arg_10], rbp
0x140001fea  push    rsi
0x140001feb  sub     rsp, 20h
0x140001fef  mov     rbp, [rcx]
0x140001ff2  mov     rsi, rdx
0x140001ff5  mov     rbx, rcx
0x140001ff8  test    rbp, rbp
0x140001ffb  jz      short loc_140002024
0x140001ffd  mov     [rsp+28h+arg_0], rdi
0x140002002  call    cs:__imp_GetLastError
0x140002008  mov     rcx, rbp; pti
0x14000200b  mov     edi, eax
0x14000200d  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x140002012  mov     ecx, edi; dwErrCode
0x140002014  call    cs:__imp_SetLastError
0x14000201a  mov     rdi, [rsp+28h+arg_0]
0x14000201f  mov     [rbx], rsi
0x140002022  jmp     short loc_140002027
0x140002024  mov     [rcx], rsi
0x140002027  mov     rbx, [rsp+28h+arg_8]
0x14000202c  mov     rbp, [rsp+28h+arg_10]
0x140002031  add     rsp, 20h
0x140002035  pop     rsi
0x140002036  retn
```
