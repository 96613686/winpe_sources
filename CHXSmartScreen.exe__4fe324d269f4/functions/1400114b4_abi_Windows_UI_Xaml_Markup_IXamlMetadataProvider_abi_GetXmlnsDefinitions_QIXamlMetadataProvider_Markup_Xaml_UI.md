# ?__abi_Windows_UI_Xaml_Markup_IXamlMetadataProvider____abi_GetXmlnsDefinitions@?QIXamlMetadataProvider@Markup@Xaml@UI@Windows@@App@CHXSmartScreen@@UE$AAAJPEAIPEAPEAVXmlnsDefinition@2345@@Z

- ea: `0x1400114b4`
- end: `0x14001150d`
- name: `?__abi_Windows_UI_Xaml_Markup_IXamlMetadataProvider____abi_GetXmlnsDefinitions@?QIXamlMetadataProvider@Markup@Xaml@UI@Windows@@App@CHXSmartScreen@@UE$AAAJPEAIPEAPEAVXmlnsDefinition@2345@@Z`
- size: `89`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140011520`

## callees

- `0x14000b168`
- `0x1400114b4`
- `0x14002b8d0`

## import_xrefs

- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x1400114d3`
- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x1400114d3`

## pseudocode

```c
__int64 __fastcall ___abi_Windows_UI_Xaml_Markup_IXamlMetadataProvider____abi_GetXmlnsDefinitions__QIXamlMetadataProvider_Markup_Xaml_UI_Windows__App_CHXSmartScreen__UE_AAAJPEAIPEAPEAVXmlnsDefinition_2345__Z(
        __int64 a1,
        _DWORD *a2,
        char **a3)
{
  __int64 XmlnsDefinitions__QIXamlMetadataProvider_Markup_Xaml_UI_Windows__App_CHXSmartScreen__UE_AAAP_01E_AAV__Array_VXmlnsDefinition_Markup_Xaml_UI_Windows___00_Platform__XZ; // rax

  if ( *(_BYTE *)(a1 + 184) )
  {
    __abi_WinRTraiseObjectDisposedException();
    __debugbreak();
  }
  *a2 = 0;
  *a3 = 0;
  try
  {
    XmlnsDefinitions__QIXamlMetadataProvider_Markup_Xaml_UI_Windows__App_CHXSmartScreen__UE_AAAP_01E_AAV__Array_VXmlnsDefinition_Markup_Xaml_UI_Windows___00_Platform__XZ = _GetXmlnsDefinitions__QIXamlMetadataProvider_Markup_Xaml_UI_Windows__App_CHXSmartScreen__UE_AAAP_01E_AAV__Array_VXmlnsDefinition_Markup_Xaml_UI_Windows___00_Platform__XZ();
    Platform::Details::__abi_array_copy_to_and_release<Windows::UI::Xaml::Markup::XmlnsDefinition,1>(
      XmlnsDefinitions__QIXamlMetadataProvider_Markup_Xaml_UI_Windows__App_CHXSmartScreen__UE_AAAP_01E_AAV__Array_VXmlnsDefinition_Markup_Xaml_UI_Windows___00_Platform__XZ,
      a3,
      a2);
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
0x1400114b4  mov     [rsp+arg_8], rbx
0x1400114b9  mov     [rsp+arg_10], rsi
0x1400114be  push    rdi
0x1400114bf  sub     rsp, 20h
0x1400114c3  mov     rdi, r8
0x1400114c6  mov     rsi, rdx
0x1400114c9  xor     eax, eax
0x1400114cb  cmp     [rcx+0B8h], al
0x1400114d1  jz      short loc_1400114DA
0x1400114d3  call    cs:__imp_?__abi_WinRTraiseObjectDisposedException@@YAXXZ; __abi_WinRTraiseObjectDisposedException(void)
0x1400114d9  int     3; Trap to Debugger
0x1400114da  mov     ebx, eax
0x1400114dc  mov     [rdx], eax
0x1400114de  mov     [r8], rax
0x1400114e1  call    ?GetXmlnsDefinitions@?QIXamlMetadataProvider@Markup@Xaml@UI@Windows@@App@CHXSmartScreen@@UE$AAAP$01E$AAV?$Array@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00@Platform@@XZ
0x1400114e6  mov     r8, rsi
0x1400114e9  mov     rdx, rdi
0x1400114ec  mov     rcx, rax
0x1400114ef  call    ??$__abi_array_copy_to_and_release@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00@Details@Platform@@YAXP$01E$AAV?$Array@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00@1@PEAPEAXPEAI@Z
0x1400114f4  nop
0x1400114f5  jmp     short loc_1400114FB
0x1400114f7  mov     ebx, [rsp+28h+arg_0]
0x1400114fb  mov     eax, ebx
0x1400114fd  mov     rbx, [rsp+28h+arg_8]
0x140011502  mov     rsi, [rsp+28h+arg_10]
0x140011507  add     rsp, 20h
0x14001150b  pop     rdi
0x14001150c  retn
```
