# std::_Func_impl_no_alloc<std::_Fake_no_copy_callable_adapter<`winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase::CreateDialogAsync(bool)'::`2'::_lambda_1_>,void,>::_Do_call(void)

- ea: `0x180019220`
- end: `0x180019275`
- name: `?_Do_call@?$_Func_impl_no_alloc@V?$_Fake_no_copy_callable_adapter@V_lambda_1_@?1??CreateDialogAsync@FirewallDialogBase@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@QEAAX_N@Z@@std@@X$$V@std@@EEAAXXZ`
- size: `85`
- prototype: `void __fastcall(__int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800139a4`
- `0x1800148d0`
- `0x180019220`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180019230`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180019230`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180019259`

## string_xrefs

- `0x180019263`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall __Do_call____Func_impl_no_alloc_V___Fake_no_copy_callable_adapter_V_lambda_1___1__CreateDialogAsync_FirewallDialogBase_implementation_Firewall_NetworkUX_Internal_Windows_winrt__QEAAX_N_Z__std__X__V_std__EEAAXXZ(
        __int64 a1)
{
  HRESULT v2; // eax
  int v3; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = CoInitializeEx(0, 2u);
  if ( v2 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x14D3,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)(unsigned int)v2,
      v3);
  winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase::_CreateDialog(
    *(HWND **)(a1 + 8),
    **(_BYTE **)(a1 + 16));
  CoUninitialize();
}

```

## disassembly

```asm
0x180019220  push    rbx; int
0x180019222  sub     rsp, 20h
0x180019226  mov     rbx, rcx
0x180019229  mov     edx, 2; dwCoInit
0x18001922e  xor     ecx, ecx; pvReserved
0x180019230  call    cs:__imp_CoInitializeEx
0x180019236  mov     rcx, [rsp+28h]; this
0x18001923b  test    eax, eax
0x18001923d  js      short loc_180019260
0x18001923f  mov     [rsp+28h+arg_0], 1
0x180019244  mov     rdx, [rbx+10h]
0x180019248  mov     dl, [rdx]; bool
0x18001924a  mov     rcx, [rbx+8]; this
0x18001924e  call    ?_CreateDialog@FirewallDialogBase@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@AEAAX_N@Z; winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase::_CreateDialog(bool)
0x180019253  nop
0x180019254  add     rsp, 20h
0x180019258  pop     rbx
0x180019259  jmp     cs:__imp_CoUninitialize
0x180019260  mov     r9d, eax; char *
0x180019263  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001926a  mov     edx, 14D3h; void *
0x18001926f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
