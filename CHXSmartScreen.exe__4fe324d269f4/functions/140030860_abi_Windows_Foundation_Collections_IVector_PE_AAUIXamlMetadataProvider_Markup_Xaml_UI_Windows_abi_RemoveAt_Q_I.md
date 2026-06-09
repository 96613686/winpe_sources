# ?__abi_Windows_Foundation_Collections_?$IVector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@____abi_RemoveAt@?Q?$IVector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@Collections@Foundation@Windows@@?$Vector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@U?$equal_to@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@std@@@2Platform@@UE$AAAJI@Z

- ea: `0x140030860`
- end: `0x14003088b`
- name: `?__abi_Windows_Foundation_Collections_?$IVector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@____abi_RemoveAt@?Q?$IVector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@Collections@Foundation@Windows@@?$Vector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@U?$equal_to@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@std@@@2Platform@@UE$AAAJI@Z`
- size: `43`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400308a0`
- `0x1400312f0`

## callees

- `0x14002c478`
- `0x140030860`

## import_xrefs

- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x140030870`
- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x140030870`

## pseudocode

```c
__int64 __fastcall ___abi_Windows_Foundation_Collections___IVector_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows______abi_RemoveAt__Q__IVector_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows___Collections_Foundation_Windows____Vector_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows__U__equal_to_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows___std___2Platform__UE_AAAJI_Z(
        __int64 a1,
        unsigned int a2)
{
  if ( *(_BYTE *)(a1 + 168) )
    __abi_WinRTraiseObjectDisposedException();
  _RemoveAt__Q__IVector_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows___Collections_Foundation_Windows____Vector_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows__U__equal_to_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows___std___2Platform__UE_AAAXI_Z(
    a1,
    a2);
  return 0;
}

```

## disassembly

```asm
0x140030860  push    rbx
0x140030862  sub     rsp, 20h
0x140030866  xor     ebx, ebx
0x140030868  cmp     [rcx+0A8h], bl
0x14003086e  jz      short loc_140030877
0x140030870  call    cs:__imp_?__abi_WinRTraiseObjectDisposedException@@YAXXZ; __abi_WinRTraiseObjectDisposedException(void)
0x140030876  nop
0x140030877  call    ?RemoveAt@?Q?$IVector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@Collections@Foundation@Windows@@?$Vector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@U?$equal_to@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@std@@@2Platform@@UE$AAAXI@Z
0x14003087c  nop
0x14003087d  jmp     short loc_140030883
0x14003087f  mov     ebx, [rsp+28h+arg_0]
0x140030883  mov     eax, ebx
0x140030885  add     rsp, 20h
0x140030889  pop     rbx
0x14003088a  retn
```
