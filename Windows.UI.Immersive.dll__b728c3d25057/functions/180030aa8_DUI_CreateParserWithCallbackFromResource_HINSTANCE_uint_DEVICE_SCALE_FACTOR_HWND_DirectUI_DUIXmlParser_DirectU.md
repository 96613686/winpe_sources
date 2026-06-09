# DUI_CreateParserWithCallbackFromResource(HINSTANCE__ *,uint,DEVICE_SCALE_FACTOR,HWND__ *,DirectUI::DUIXmlParser * *,DirectUI::Value * (*)(ushort const *,void *),void *)

- ea: `0x180030aa8`
- end: `0x180030b6e`
- name: `?DUI_CreateParserWithCallbackFromResource@@YAJPEAUHINSTANCE__@@IW4DEVICE_SCALE_FACTOR@@PEAUHWND__@@PEAPEAVDUIXmlParser@DirectUI@@P6APEAVValue@5@PEBGPEAX@Z5@Z`
- size: `198`
- prototype: `__int64 __fastcall(HINSTANCE, unsigned int, enum DEVICE_SCALE_FACTOR, HWND, struct DirectUI::DUIXmlParser **, struct DirectUI::Value *(*)(const unsigned __int16 *, void *), void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18003e8a8`

## callees

- `0x180030aa8`
- `0x1800448e8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180030b3e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180030b3e`
- `DUI70!?SetXMLFromResourceWithTheme@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@00@Z` at `0x180030b2e`
- `DUI70!?SetXMLFromResourceWithTheme@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@00@Z` at `0x180030b2e`
- `DUI70!?SetRootWindowForTheming@DUIXmlParser@DirectUI@@QEAAXPEAUHWND__@@@Z` at `0x180030b10`
- `DUI70!?SetRootWindowForTheming@DUIXmlParser@DirectUI@@QEAAXPEAUHWND__@@@Z` at `0x180030b10`
- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x180030afe`
- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x180030afe`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x180030b50`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x180030b50`

## pseudocode

```c
__int64 __fastcall DUI_CreateParserWithCallbackFromResource(
        unsigned __int16 **a1,
        unsigned int a2,
        enum DEVICE_SCALE_FACTOR a3,
        HWND a4,
        struct DirectUI::DUIXmlParser **a5)
{
  HINSTANCE ShellStyleHInstance; // rax
  HMODULE v9; // rsi
  HINSTANCE v10; // rbp
  int v11; // edi

  *a5 = 0;
  ShellStyleHInstance = GetShellStyleHInstance(a1);
  v9 = (HMODULE)a1;
  if ( ShellStyleHInstance )
    v9 = ShellStyleHInstance;
  v10 = ShellStyleHInstance;
  v11 = DirectUI::DUIXmlParser::Create(
          a5,
          (struct DirectUI::Value *(*)(const unsigned __int16 *, void *))DUI_ShellStyleSheet_GetSheetCB,
          0,
          (void (*)(const unsigned __int16 *, const unsigned __int16 *, int, void *))CSafeElementPtrBase<UIBridgeWindow>::OnListenedPropertyChanged,
          0);
  if ( v11 >= 0 )
  {
    DirectUI::DUIXmlParser::SetRootWindowForTheming(*a5, a4);
    v11 = DirectUI::DUIXmlParser::SetXMLFromResourceWithTheme(*a5, a2, (HINSTANCE)a1, v9, &_ImageBase);
  }
  if ( v10 )
    FreeLibrary(v9);
  if ( v11 < 0 && *a5 )
  {
    DirectUI::DUIXmlParser::Destroy(*a5);
    *a5 = 0;
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180030aa8  push    rbx
0x180030aaa  push    rbp
0x180030aab  push    rsi
0x180030aac  push    rdi
0x180030aad  push    r12
0x180030aaf  push    r14
0x180030ab1  push    r15
0x180030ab3  sub     rsp, 30h
0x180030ab7  mov     rbx, [rsp+68h+arg_20]
0x180030abf  mov     r15, r9
0x180030ac2  mov     r12d, edx
0x180030ac5  mov     r14, rcx
0x180030ac8  mov     qword ptr [rbx], 0
0x180030acf  call    ?GetShellStyleHInstance@@YAPEAUHINSTANCE__@@PEAPEAG@Z; GetShellStyleHInstance(ushort * *)
0x180030ad4  test    rax, rax
0x180030ad7  mov     [rsp+68h+var_48], 0
0x180030ae0  mov     rsi, r14
0x180030ae3  lea     r9, ?OnListenedPropertyChanged@?$CSafeElementPtrBase@VUIBridgeWindow@@@@MEAAXPEAVElement@DirectUI@@PEBUPropertyInfo@3@HPEAVValue@3@2@Z; CSafeElementPtrBase<UIBridgeWindow>::OnListenedPropertyChanged(DirectUI::Element *,DirectUI::PropertyInfo const *,int,DirectUI::Value *,DirectUI::Value *)
0x180030aea  cmovnz  rsi, rax
0x180030aee  lea     rdx, ?DUI_ShellStyleSheet_GetSheetCB@@YAPEAVValue@DirectUI@@PEBGPEAX@Z; DUI_ShellStyleSheet_GetSheetCB(ushort const *,void *)
0x180030af5  xor     r8d, r8d
0x180030af8  mov     rcx, rbx
0x180030afb  mov     rbp, rax
0x180030afe  call    cs:__imp_?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z; DirectUI::DUIXmlParser::Create(DirectUI::DUIXmlParser * *,DirectUI::Value * (*)(ushort const *,void *),void *,void (*)(ushort const *,ushort const *,int,void *),void *)
0x180030b04  mov     edi, eax
0x180030b06  test    eax, eax
0x180030b08  js      short loc_180030B36
0x180030b0a  mov     rcx, [rbx]
0x180030b0d  mov     rdx, r15
0x180030b10  call    cs:__imp_?SetRootWindowForTheming@DUIXmlParser@DirectUI@@QEAAXPEAUHWND__@@@Z; DirectUI::DUIXmlParser::SetRootWindowForTheming(HWND__ *)
0x180030b16  mov     rcx, [rbx]
0x180030b19  lea     rax, __ImageBase
0x180030b20  mov     r9, rsi
0x180030b23  mov     [rsp+68h+var_48], rax
0x180030b28  mov     r8, r14
0x180030b2b  mov     edx, r12d
0x180030b2e  call    cs:__imp_?SetXMLFromResourceWithTheme@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@00@Z; DirectUI::DUIXmlParser::SetXMLFromResourceWithTheme(uint,HINSTANCE__ *,HINSTANCE__ *,HINSTANCE__ *)
0x180030b34  mov     edi, eax
0x180030b36  test    rbp, rbp
0x180030b39  jz      short loc_180030B44
0x180030b3b  mov     rcx, rsi; hLibModule
0x180030b3e  call    cs:__imp_FreeLibrary
0x180030b44  test    edi, edi
0x180030b46  jns     short loc_180030B5D
0x180030b48  mov     rcx, [rbx]
0x180030b4b  test    rcx, rcx
0x180030b4e  jz      short loc_180030B5D
0x180030b50  call    cs:__imp_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ; DirectUI::DUIXmlParser::Destroy(void)
0x180030b56  mov     qword ptr [rbx], 0
0x180030b5d  mov     eax, edi
0x180030b5f  add     rsp, 30h
0x180030b63  pop     r15
0x180030b65  pop     r14
0x180030b67  pop     r12
0x180030b69  pop     rdi
0x180030b6a  pop     rsi
0x180030b6b  pop     rbp
0x180030b6c  pop     rbx
0x180030b6d  retn
```
