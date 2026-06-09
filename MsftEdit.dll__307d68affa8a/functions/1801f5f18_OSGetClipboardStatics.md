# OSGetClipboardStatics

- ea: `0x1801f5f18`
- end: `0x1801f5f85`
- name: `OSGetClipboardStatics`
- size: `109`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1801f5dac`

## callees

- `0x180048d5c`
- `0x1800e1264`
- `0x1801f5f18`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1801f5f65`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1801f5f65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f5f72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801f5f72`

## pseudocode

```c
__int64 __fastcall OSGetClipboardStatics(__int64 a1)
{
  unsigned int ActivationFactory; // ebx
  HSTRING v3; // rbx
  HSTRING string; // [rsp+38h] [rbp+10h] BYREF

  string = 0;
  ActivationFactory = Microsoft::WRL::Wrappers::HString::Set(
                        &string,
                        L"Windows.ApplicationModel.DataTransfer.Clipboard",
                        0x2Fu);
  if ( !ActivationFactory )
  {
    v3 = string;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1);
    ActivationFactory = RoGetActivationFactory(v3, &GUID_c627e291_34e2_4963_8eed_93cbb0ea3d70, a1);
  }
  WindowsDeleteString(string);
  return ActivationFactory;
}

```

## disassembly

```asm
0x1801f5f18  mov     [rsp+arg_0], rbx
0x1801f5f1d  push    rdi
0x1801f5f1e  sub     rsp, 20h
0x1801f5f22  mov     rdi, rcx
0x1801f5f25  mov     [rsp+28h+string], 0
0x1801f5f2e  lea     rcx, [rsp+28h+string]; this
0x1801f5f33  mov     r8d, 2Fh ; '/'; unsigned int
0x1801f5f39  lea     rdx, ?RuntimeClass_Windows_ApplicationModel_DataTransfer_Clipboard@@3QBGB; "Windows.ApplicationModel.DataTransfer.C"...
0x1801f5f40  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x1801f5f45  mov     ebx, eax
0x1801f5f47  test    eax, eax
0x1801f5f49  jnz     short loc_1801F5F6D
0x1801f5f4b  mov     rbx, [rsp+28h+string]
0x1801f5f50  mov     rcx, rdi
0x1801f5f53  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801f5f58  mov     r8, rdi
0x1801f5f5b  lea     rdx, _GUID_c627e291_34e2_4963_8eed_93cbb0ea3d70
0x1801f5f62  mov     rcx, rbx
0x1801f5f65  call    cs:__imp_RoGetActivationFactory
0x1801f5f6b  mov     ebx, eax
0x1801f5f6d  mov     rcx, [rsp+28h+string]; string
0x1801f5f72  call    cs:__imp_WindowsDeleteString
0x1801f5f78  mov     eax, ebx
0x1801f5f7a  mov     rbx, [rsp+28h+arg_0]
0x1801f5f7f  add     rsp, 20h
0x1801f5f83  pop     rdi
0x1801f5f84  retn
```
