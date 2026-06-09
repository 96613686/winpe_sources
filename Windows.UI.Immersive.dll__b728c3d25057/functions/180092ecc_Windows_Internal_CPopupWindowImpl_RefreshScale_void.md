# Windows::Internal::CPopupWindowImpl::_RefreshScale(void)

- ea: `0x180092ecc`
- end: `0x180092f90`
- name: `?_RefreshScale@CPopupWindowImpl@Internal@Windows@@AEAAXXZ`
- size: `196`
- prototype: `void __fastcall(Windows::Internal::CPopupWindowImpl *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x1800207b0`
- `0x180024870`

## callees

- `0x18003e8a8`
- `0x18008b928`
- `0x180091658`
- `0x180092ecc`
- `0x1800e5010`

## import_xrefs

- `DUI70!?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ` at `0x180092eda`
- `DUI70!?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ` at `0x180092f31`
- `DUI70!?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ` at `0x180092f5d`
- `DUI70!?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ` at `0x180092eda`
- `DUI70!?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ` at `0x180092f31`
- `DUI70!?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ` at `0x180092f5d`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x180092f4a`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x180092f4a`
- `DUI70!?UpdateSheets@DUIXmlParser@DirectUI@@QEAAJPEAVElement@2@@Z` at `0x180092f3f`
- `DUI70!?UpdateSheets@DUIXmlParser@DirectUI@@QEAAJPEAVElement@2@@Z` at `0x180092f3f`
- `DUI70!?GetDisplayNode@Element@DirectUI@@QEAAPEAUHGADGET__@@XZ` at `0x180092f69`
- `DUI70!?GetDisplayNode@Element@DirectUI@@QEAAPEAUHGADGET__@@XZ` at `0x180092f7b`
- `DUI70!?GetDisplayNode@Element@DirectUI@@QEAAPEAUHGADGET__@@XZ` at `0x180092f69`
- `DUI70!?GetDisplayNode@Element@DirectUI@@QEAAPEAUHGADGET__@@XZ` at `0x180092f7b`
- `DUser!InvalidateGadget` at `0x180092f72`
- `DUser!InvalidateGadget` at `0x180092f72`
- `DUser!InvalidateLayeredDescendants` at `0x180092f84`
- `DUser!InvalidateLayeredDescendants` at `0x180092f84`

## pseudocode

```c
void __fastcall Windows::Internal::CPopupWindowImpl::_RefreshScale(Windows::Internal::CPopupWindowImpl *this)
{
  struct DirectUI::Element *Element; // rax
  __int64 v3; // rcx
  unsigned int v4; // eax
  struct DirectUI::Element *v5; // rax
  DirectUI::Element *v6; // rbx
  struct HGADGET__ *DisplayNode; // rax
  struct HGADGET__ *v8; // rax
  char v9; // [rsp+40h] [rbp+8h] BYREF
  DirectUI::DUIXmlParser *v10; // [rsp+48h] [rbp+10h]

  v9 = 0;
  Element = DirectUI::NativeHWNDHost::GetElement(this);
  ElementWalkAll__lambda_5887d6412ebffbf74f7db4f9848df3d6_(Element, &v9);
  v3 = *((_QWORD *)this + 12);
  v10 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 112LL))(v3);
  if ( (int)DUI_CreateParserFromResource(&_ImageBase, v4, 0) >= 0 )
  {
    v5 = DirectUI::NativeHWNDHost::GetElement(this);
    DirectUI::DUIXmlParser::UpdateSheets(v10, v5);
    DirectUI::DUIXmlParser::Destroy(v10);
  }
  Windows::Internal::CPopupWindowImpl::_FireResizeEvent(this, 0);
  v6 = DirectUI::NativeHWNDHost::GetElement(this);
  DisplayNode = DirectUI::Element::GetDisplayNode(v6);
  InvalidateGadget(DisplayNode);
  v8 = DirectUI::Element::GetDisplayNode(v6);
  InvalidateLayeredDescendants(v8);
}

```

## disassembly

```asm
0x180092ecc  push    rbx
0x180092ece  sub     rsp, 30h
0x180092ed2  mov     rbx, rcx
0x180092ed5  mov     [rsp+38h+arg_0], 0
0x180092eda  call    cs:__imp_?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ; DirectUI::NativeHWNDHost::GetElement(void)
0x180092ee0  mov     rcx, rax
0x180092ee3  lea     rdx, [rsp+38h+arg_0]
0x180092ee8  call    ElementWalkAll__lambda_5887d6412ebffbf74f7db4f9848df3d6___; ElementWalkAll__lambda_5887d6412ebffbf74f7db4f9848df3d6_
0x180092eed  mov     rcx, [rbx+60h]
0x180092ef1  mov     [rsp+38h+arg_8], 0
0x180092efa  mov     rax, [rcx]
0x180092efd  mov     rax, [rax+70h]
0x180092f01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092f06  lea     rcx, [rsp+38h+arg_8]
0x180092f0b  xor     r8d, r8d
0x180092f0e  mov     [rsp+38h+var_10], rcx
0x180092f13  mov     edx, eax
0x180092f15  lea     rcx, __ImageBase
0x180092f1c  mov     [rsp+38h+var_18], 0
0x180092f25  call    ?DUI_CreateParserFromResource@@YAJPEAUHINSTANCE__@@IW4DUI_PARSER_LOAD_FLAGS@@W4DEVICE_SCALE_FACTOR@@PEAUHWND__@@PEAPEAVDUIXmlParser@DirectUI@@@Z; DUI_CreateParserFromResource(HINSTANCE__ *,uint,DUI_PARSER_LOAD_FLAGS,DEVICE_SCALE_FACTOR,HWND__ *,DirectUI::DUIXmlParser * *)
0x180092f2a  test    eax, eax
0x180092f2c  js      short loc_180092F50
0x180092f2e  mov     rcx, rbx
0x180092f31  call    cs:__imp_?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ; DirectUI::NativeHWNDHost::GetElement(void)
0x180092f37  mov     rcx, [rsp+38h+arg_8]
0x180092f3c  mov     rdx, rax
0x180092f3f  call    cs:__imp_?UpdateSheets@DUIXmlParser@DirectUI@@QEAAJPEAVElement@2@@Z; DirectUI::DUIXmlParser::UpdateSheets(DirectUI::Element *)
0x180092f45  mov     rcx, [rsp+38h+arg_8]
0x180092f4a  call    cs:__imp_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ; DirectUI::DUIXmlParser::Destroy(void)
0x180092f50  xor     edx, edx; bool
0x180092f52  mov     rcx, rbx; this
0x180092f55  call    ?_FireResizeEvent@CPopupWindowImpl@Internal@Windows@@AEAAX_N@Z; Windows::Internal::CPopupWindowImpl::_FireResizeEvent(bool)
0x180092f5a  mov     rcx, rbx
0x180092f5d  call    cs:__imp_?GetElement@NativeHWNDHost@DirectUI@@QEAAPEAVElement@2@XZ; DirectUI::NativeHWNDHost::GetElement(void)
0x180092f63  mov     rcx, rax
0x180092f66  mov     rbx, rax
0x180092f69  call    cs:__imp_?GetDisplayNode@Element@DirectUI@@QEAAPEAUHGADGET__@@XZ; DirectUI::Element::GetDisplayNode(void)
0x180092f6f  mov     rcx, rax
0x180092f72  call    cs:__imp_InvalidateGadget
0x180092f78  mov     rcx, rbx
0x180092f7b  call    cs:__imp_?GetDisplayNode@Element@DirectUI@@QEAAPEAUHGADGET__@@XZ; DirectUI::Element::GetDisplayNode(void)
0x180092f81  mov     rcx, rax
0x180092f84  call    cs:__imp_InvalidateLayeredDescendants
0x180092f8a  add     rsp, 30h
0x180092f8e  pop     rbx
0x180092f8f  retn
```
