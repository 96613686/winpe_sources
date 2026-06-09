# CWinRTContentLinkInfo::~CWinRTContentLinkInfo(void)

- ea: `0x1801dfd08`
- end: `0x1801dfd69`
- name: `??1CWinRTContentLinkInfo@@UEAA@XZ`
- size: `97`
- prototype: `void __fastcall(CWinRTContentLinkInfo *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1801dfeb0`

## callees

- `0x180048d5c`
- `0x1801dfce8`
- `0x1801dfd08`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801dfd2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801dfd3e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801dfd4d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801dfd2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801dfd3e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801dfd4d`

## pseudocode

```c
void __fastcall CWinRTContentLinkInfo::~CWinRTContentLinkInfo(CWinRTContentLinkInfo *this)
{
  HSTRING v2; // rcx
  HSTRING v3; // rcx
  HSTRING v4; // rcx

  *(_QWORD *)this = &CWinRTContentLinkInfo::`vftable'{for `Windows::UI::Text::IContentLinkInfo'};
  *((_QWORD *)this + 1) = &CWinRTContentLinkInfo::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource>'};
  v2 = (HSTRING)*((_QWORD *)this + 5);
  if ( v2 )
    WindowsDeleteString(v2);
  v3 = (HSTRING)*((_QWORD *)this + 6);
  if ( v3 )
    WindowsDeleteString(v3);
  v4 = (HSTRING)*((_QWORD *)this + 8);
  if ( v4 )
    WindowsDeleteString(v4);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 56);
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Text::IContentLinkInfo>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Text::IContentLinkInfo>(this);
}

```

## disassembly

```asm
0x1801dfd08  push    rbx
0x1801dfd0a  sub     rsp, 20h
0x1801dfd0e  lea     rax, ??_7CWinRTContentLinkInfo@@6BIContentLinkInfo@Text@UI@Windows@@@; const CWinRTContentLinkInfo::`vftable'{for `Windows::UI::Text::IContentLinkInfo'}
0x1801dfd15  mov     rbx, rcx
0x1801dfd18  mov     [rcx], rax
0x1801dfd1b  lea     rax, ??_7CWinRTContentLinkInfo@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@@Details@WRL@Microsoft@@@; const CWinRTContentLinkInfo::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource>'}
0x1801dfd22  mov     [rcx+8], rax
0x1801dfd26  mov     rcx, [rcx+28h]; string
0x1801dfd2a  test    rcx, rcx
0x1801dfd2d  jz      short loc_1801DFD35
0x1801dfd2f  call    cs:__imp_WindowsDeleteString
0x1801dfd35  mov     rcx, [rbx+30h]; string
0x1801dfd39  test    rcx, rcx
0x1801dfd3c  jz      short loc_1801DFD44
0x1801dfd3e  call    cs:__imp_WindowsDeleteString
0x1801dfd44  mov     rcx, [rbx+40h]; string
0x1801dfd48  test    rcx, rcx
0x1801dfd4b  jz      short loc_1801DFD53
0x1801dfd4d  call    cs:__imp_WindowsDeleteString
0x1801dfd53  lea     rcx, [rbx+38h]
0x1801dfd57  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801dfd5c  mov     rcx, rbx
0x1801dfd5f  add     rsp, 20h
0x1801dfd63  pop     rbx
0x1801dfd64  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIContentLinkInfo@Text@UI@Windows@@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Text::IContentLinkInfo>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Text::IContentLinkInfo>(void)
```
