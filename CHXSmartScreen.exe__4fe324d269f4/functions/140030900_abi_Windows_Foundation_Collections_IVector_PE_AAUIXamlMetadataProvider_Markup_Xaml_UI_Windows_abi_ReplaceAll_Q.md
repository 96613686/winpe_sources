# ?__abi_Windows_Foundation_Collections_?$IVector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@____abi_ReplaceAll@?Q?$IVector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@Collections@Foundation@Windows@@?$Vector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@U?$equal_to@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@std@@@2Platform@@UE$AAAJIPEAPE$AAUIXamlMetadataProvider@Markup@Xaml@UI@4@@Z

- ea: `0x140030900`
- end: `0x14003095c`
- name: `?__abi_Windows_Foundation_Collections_?$IVector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@____abi_ReplaceAll@?Q?$IVector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@Collections@Foundation@Windows@@?$Vector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@U?$equal_to@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@std@@@2Platform@@UE$AAAJIPEAPE$AAUIXamlMetadataProvider@Markup@Xaml@UI@4@@Z`
- size: `92`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140030970`

## callees

- `0x140028c5c`
- `0x14002c6a0`
- `0x140030900`

## import_xrefs

- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x14003091d`
- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x14003091d`

## pseudocode

```c
__int64 __fastcall ___abi_Windows_Foundation_Collections___IVector_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows______abi_ReplaceAll__Q__IVector_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows___Collections_Foundation_Windows____Vector_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows__U__equal_to_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows___std___2Platform__UE_AAAJIPEAPE_AAUIXamlMetadataProvider_Markup_Xaml_UI_4__Z(
        __int64 a1)
{
  __int64 v2; // rax

  if ( *(_BYTE *)(a1 + 168) )
    __abi_WinRTraiseObjectDisposedException();
  try
  {
    v2 = Platform::ArrayReference<Windows::UI::Xaml::Markup::IXamlMetadataProvider __gc *,1>::ArrayReference<Windows::UI::Xaml::Markup::IXamlMetadataProvider __gc *,1>();
    _ReplaceAll__Q__IVector_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows___Collections_Foundation_Windows____Vector_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows__U__equal_to_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows___std___2Platform__UE_AAAXP_01E_ABV__Array_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows___00_6__Z(
      a1,
      v2);
  }
  catch ( ... )
  {
    __abi_translateCurrentException(0);
  }
  return 0;
}

```

## disassembly

```asm
0x140030900  mov     [rsp+arg_18], rbx
0x140030905  push    rdi
0x140030906  sub     rsp, 0C0h
0x14003090d  mov     rax, r8
0x140030910  mov     rdi, rcx
0x140030913  xor     ebx, ebx
0x140030915  cmp     [rcx+0A8h], bl
0x14003091b  jz      short loc_140030924
0x14003091d  call    cs:__imp_?__abi_WinRTraiseObjectDisposedException@@YAXXZ; __abi_WinRTraiseObjectDisposedException(void)
0x140030923  nop
0x140030924  xor     r9d, r9d
0x140030927  mov     r8d, edx
0x14003092a  mov     rdx, rax
0x14003092d  lea     rcx, [rsp+0C8h+var_98]
0x140030932  call    ??0?$ArrayReference@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@$00@Platform@@QEAA@PEAPE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@I_N@Z; Platform::ArrayReference<Windows::UI::Xaml::Markup::IXamlMetadataProvider *,1>::ArrayReference<Windows::UI::Xaml::Markup::IXamlMetadataProvider *,1>(Windows::UI::Xaml::Markup::IXamlMetadataProvider * *,uint,bool)
0x140030937  mov     rdx, rax
0x14003093a  mov     rcx, rdi
0x14003093d  call    ?ReplaceAll@?Q?$IVector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@Collections@Foundation@Windows@@?$Vector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@U?$equal_to@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@std@@@2Platform@@UE$AAAXP$01E$ABV?$Array@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@$00@6@@Z
0x140030942  nop
0x140030943  jmp     short loc_140030949
0x140030945  mov     ebx, [rsp+0C8h+var_A8]
0x140030949  mov     eax, ebx
0x14003094b  mov     rbx, [rsp+0C8h+arg_18]
0x140030953  add     rsp, 0C0h
0x14003095a  pop     rdi
0x14003095b  retn
```
