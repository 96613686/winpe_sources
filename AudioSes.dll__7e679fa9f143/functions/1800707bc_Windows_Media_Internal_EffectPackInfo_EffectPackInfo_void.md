# Windows::Media::Internal::EffectPackInfo::~EffectPackInfo(void)

- ea: `0x1800707bc`
- end: `0x18007081a`
- name: `??1EffectPackInfo@Internal@Media@Windows@@UEAA@XZ`
- size: `94`
- prototype: `void __fastcall(Windows::Media::Internal::EffectPackInfo *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18005d200`

## callees

- `0x18002c6ac`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800707c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800707db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800707ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800707ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800707c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800707db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800707ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800707ff`

## pseudocode

```c
void __fastcall Windows::Media::Internal::EffectPackInfo::~EffectPackInfo(HSTRING *this)
{
  WindowsDeleteString(this[15]);
  this[15] = 0;
  WindowsDeleteString(this[14]);
  this[14] = 0;
  WindowsDeleteString(this[13]);
  this[13] = 0;
  WindowsDeleteString(this[12]);
  this[12] = 0;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Microsoft::WRL::CloakedIid<Windows::Media::Internal::IMulticastSession>,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Microsoft::WRL::CloakedIid<Windows::Media::Internal::IMulticastSession>,Microsoft::WRL::FtmBase>(this);
}

```

## disassembly

```asm
0x1800707bc  push    rbx
0x1800707be  sub     rsp, 20h
0x1800707c2  mov     rbx, rcx
0x1800707c5  mov     rcx, [rcx+78h]; string
0x1800707c9  call    cs:__imp_WindowsDeleteString
0x1800707cf  mov     qword ptr [rbx+78h], 0
0x1800707d7  mov     rcx, [rbx+70h]; string
0x1800707db  call    cs:__imp_WindowsDeleteString
0x1800707e1  mov     qword ptr [rbx+70h], 0
0x1800707e9  mov     rcx, [rbx+68h]; string
0x1800707ed  call    cs:__imp_WindowsDeleteString
0x1800707f3  mov     qword ptr [rbx+68h], 0
0x1800707fb  mov     rcx, [rbx+60h]; string
0x1800707ff  call    cs:__imp_WindowsDeleteString
0x180070805  mov     rcx, rbx
0x180070808  mov     qword ptr [rbx+60h], 0
0x180070810  add     rsp, 20h
0x180070814  pop     rbx
0x180070815  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$CloakedIid@UIMulticastSession@Internal@Media@Windows@@@23@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Microsoft::WRL::CloakedIid<Windows::Media::Internal::IMulticastSession>,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Microsoft::WRL::CloakedIid<Windows::Media::Internal::IMulticastSession>,Microsoft::WRL::FtmBase>(void)
```
