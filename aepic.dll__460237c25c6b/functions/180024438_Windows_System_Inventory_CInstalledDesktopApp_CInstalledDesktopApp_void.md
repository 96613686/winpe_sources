# Windows::System::Inventory::CInstalledDesktopApp::~CInstalledDesktopApp(void)

- ea: `0x180024438`
- end: `0x1800244ab`
- name: `??1CInstalledDesktopApp@Inventory@System@Windows@@UEAA@XZ`
- size: `115`
- prototype: `void __fastcall(Windows::System::Inventory::CInstalledDesktopApp *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180024870`

## callees

- `0x180024380`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002445a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002446c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002447e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024490`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002445a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002446c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002447e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024490`

## pseudocode

```c
void __fastcall Windows::System::Inventory::CInstalledDesktopApp::~CInstalledDesktopApp(
        Windows::System::Inventory::CInstalledDesktopApp *this)
{
  *(_QWORD *)this = &Windows::System::Inventory::CInstalledDesktopApp::`vftable'{for `Windows::System::Inventory::IInstalledDesktopApp'};
  *((_QWORD *)this + 1) = &Windows::System::Inventory::CInstalledDesktopApp::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource>'};
  WindowsDeleteString(*((HSTRING *)this + 7));
  *((_QWORD *)this + 7) = 0;
  WindowsDeleteString(*((HSTRING *)this + 6));
  *((_QWORD *)this + 6) = 0;
  WindowsDeleteString(*((HSTRING *)this + 5));
  *((_QWORD *)this + 5) = 0;
  WindowsDeleteString(*((HSTRING *)this + 4));
  *((_QWORD *)this + 4) = 0;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::System::Inventory::IInstalledDesktopApp>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::System::Inventory::IInstalledDesktopApp>(this);
}

```

## disassembly

```asm
0x180024438  push    rbx
0x18002443a  sub     rsp, 20h
0x18002443e  lea     rax, ??_7CInstalledDesktopApp@Inventory@System@Windows@@6BIInstalledDesktopApp@123@@; const Windows::System::Inventory::CInstalledDesktopApp::`vftable'{for `Windows::System::Inventory::IInstalledDesktopApp'}
0x180024445  mov     rbx, rcx
0x180024448  mov     [rcx], rax
0x18002444b  lea     rax, ??_7CInstalledDesktopApp@Inventory@System@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@@Details@WRL@Microsoft@@@; const Windows::System::Inventory::CInstalledDesktopApp::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource>'}
0x180024452  mov     [rcx+8], rax
0x180024456  mov     rcx, [rcx+38h]; string
0x18002445a  call    cs:__imp_WindowsDeleteString
0x180024460  mov     qword ptr [rbx+38h], 0
0x180024468  mov     rcx, [rbx+30h]; string
0x18002446c  call    cs:__imp_WindowsDeleteString
0x180024472  mov     qword ptr [rbx+30h], 0
0x18002447a  mov     rcx, [rbx+28h]; string
0x18002447e  call    cs:__imp_WindowsDeleteString
0x180024484  mov     qword ptr [rbx+28h], 0
0x18002448c  mov     rcx, [rbx+20h]; string
0x180024490  call    cs:__imp_WindowsDeleteString
0x180024496  mov     rcx, rbx
0x180024499  mov     qword ptr [rbx+20h], 0
0x1800244a1  add     rsp, 20h
0x1800244a5  pop     rbx
0x1800244a6  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIInstalledDesktopApp@Inventory@System@Windows@@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::System::Inventory::IInstalledDesktopApp>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::System::Inventory::IInstalledDesktopApp>(void)
```
