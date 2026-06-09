# ?__abi_Windows_UI_Xaml_Interop_IBindableVector____abi_RemoveAtEnd@?QIBindableVector@Interop@Xaml@UI@Windows@@?$Vector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@U?$equal_to@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@std@@@Collections@Platform@@UE$AAAJXZ

- ea: `0x1400308b0`
- end: `0x1400308db`
- name: `?__abi_Windows_UI_Xaml_Interop_IBindableVector____abi_RemoveAtEnd@?QIBindableVector@Interop@Xaml@UI@Windows@@?$Vector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@U?$equal_to@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@std@@@Collections@Platform@@UE$AAAJXZ`
- size: `43`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400308f0`
- `0x140031300`

## callees

- `0x14002c5d0`
- `0x1400308b0`

## import_xrefs

- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x1400308c0`
- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x1400308c0`

## pseudocode

```c
__int64 __fastcall ___abi_Windows_UI_Xaml_Interop_IBindableVector____abi_RemoveAtEnd__QIBindableVector_Interop_Xaml_UI_Windows____Vector_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows__U__equal_to_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows___std___Collections_Platform__UE_AAAJXZ(
        __int64 a1)
{
  if ( *(_BYTE *)(a1 + 168) )
    __abi_WinRTraiseObjectDisposedException();
  _RemoveAtEnd__Q__IVector_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows___Collections_Foundation_Windows____Vector_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows__U__equal_to_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows___std___2Platform__UE_AAAXXZ(a1);
  return 0;
}

```

## disassembly

```asm
0x1400308b0  push    rbx
0x1400308b2  sub     rsp, 20h
0x1400308b6  xor     ebx, ebx
0x1400308b8  cmp     [rcx+0A8h], bl
0x1400308be  jz      short loc_1400308C7
0x1400308c0  call    cs:__imp_?__abi_WinRTraiseObjectDisposedException@@YAXXZ; __abi_WinRTraiseObjectDisposedException(void)
0x1400308c6  nop
0x1400308c7  call    ?RemoveAtEnd@?Q?$IVector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@Collections@Foundation@Windows@@?$Vector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@U?$equal_to@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@std@@@2Platform@@UE$AAAXXZ
0x1400308cc  nop
0x1400308cd  jmp     short loc_1400308D3
0x1400308cf  mov     ebx, [rsp+28h+arg_0]
0x1400308d3  mov     eax, ebx
0x1400308d5  add     rsp, 20h
0x1400308d9  pop     rbx
0x1400308da  retn
```
