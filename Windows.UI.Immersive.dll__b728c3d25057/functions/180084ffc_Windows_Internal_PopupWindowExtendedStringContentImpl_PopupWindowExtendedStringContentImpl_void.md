# Windows::Internal::PopupWindowExtendedStringContentImpl::~PopupWindowExtendedStringContentImpl(void)

- ea: `0x180084ffc`
- end: `0x180085044`
- name: `??1PopupWindowExtendedStringContentImpl@Internal@Windows@@UEAA@XZ`
- size: `72`
- prototype: `void __fastcall(Windows::Internal::PopupWindowExtendedStringContentImpl *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800855c0`

## callees

- `0x1800487d8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180085009`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180085013`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008501d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180085027`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180085031`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180085009`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180085013`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008501d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180085027`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180085031`

## pseudocode

```c
void __fastcall Windows::Internal::PopupWindowExtendedStringContentImpl::~PopupWindowExtendedStringContentImpl(
        LPVOID *this)
{
  CoTaskMemFree(this[9]);
  CoTaskMemFree(this[7]);
  CoTaskMemFree(this[6]);
  CoTaskMemFree(this[5]);
  CoTaskMemFree(this[4]);
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::UI::Core::ICoreWindowPopupShowingEventArgs>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::UI::Core::ICoreWindowPopupShowingEventArgs>(this);
}

```

## disassembly

```asm
0x180084ffc  push    rbx
0x180084ffe  sub     rsp, 20h
0x180085002  mov     rbx, rcx
0x180085005  mov     rcx, [rcx+48h]; pv
0x180085009  call    cs:__imp_CoTaskMemFree
0x18008500f  mov     rcx, [rbx+38h]; pv
0x180085013  call    cs:__imp_CoTaskMemFree
0x180085019  mov     rcx, [rbx+30h]; pv
0x18008501d  call    cs:__imp_CoTaskMemFree
0x180085023  mov     rcx, [rbx+28h]; pv
0x180085027  call    cs:__imp_CoTaskMemFree
0x18008502d  mov     rcx, [rbx+20h]; pv
0x180085031  call    cs:__imp_CoTaskMemFree
0x180085037  mov     rcx, rbx
0x18008503a  add     rsp, 20h
0x18008503e  pop     rbx
0x18008503f  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UICoreWindowPopupShowingEventArgs@Core@UI@Windows@@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::UI::Core::ICoreWindowPopupShowingEventArgs>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::UI::Core::ICoreWindowPopupShowingEventArgs>(void)
```
