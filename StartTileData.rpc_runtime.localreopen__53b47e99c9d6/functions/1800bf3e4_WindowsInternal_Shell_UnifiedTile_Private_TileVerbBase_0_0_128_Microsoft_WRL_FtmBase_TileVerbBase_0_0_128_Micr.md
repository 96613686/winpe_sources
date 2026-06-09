# WindowsInternal::Shell::UnifiedTile::Private::TileVerbBase<0,0,128,Microsoft::WRL::FtmBase>::~TileVerbBase<0,0,128,Microsoft::WRL::FtmBase>(void)

- ea: `0x1800bf3e4`
- end: `0x1800bf493`
- name: `??1?$TileVerbBase@$0A@$0A@$0IA@VFtmBase@WRL@Microsoft@@@Private@UnifiedTile@Shell@WindowsInternal@@MEAA@XZ`
- size: `175`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800bf278`
- `0x180122c3c`
- `0x1801b8ed8`
- `0x18026db98`
- `0x18026dd10`
- `0x1802f6f40`
- `0x18031d100`
- `0x180392e63`
- `0x1803a5b00`

## callees

- `0x18000ce94`
- `0x180041bb4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf3fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf40c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf41e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf430`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf442`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf454`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf466`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf478`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf3fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf40c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf41e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf430`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf442`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf454`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf466`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf478`

## pseudocode

```c
__int64 __fastcall WindowsInternal::Shell::UnifiedTile::Private::TileVerbBase<0,0,128,Microsoft::WRL::FtmBase>::~TileVerbBase<0,0,128,Microsoft::WRL::FtmBase>(
        HSTRING *a1)
{
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(a1 + 16);
  WindowsDeleteString(a1[15]);
  a1[15] = 0;
  WindowsDeleteString(a1[14]);
  a1[14] = 0;
  WindowsDeleteString(a1[13]);
  a1[13] = 0;
  WindowsDeleteString(a1[12]);
  a1[12] = 0;
  WindowsDeleteString(a1[11]);
  a1[11] = 0;
  WindowsDeleteString(a1[10]);
  a1[10] = 0;
  WindowsDeleteString(a1[9]);
  a1[9] = 0;
  WindowsDeleteString(a1[8]);
  a1[8] = 0;
  return Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>,Microsoft::WRL::FtmBase>(a1);
}

```

## disassembly

```asm
0x1800bf3e4  push    rbx
0x1800bf3e6  sub     rsp, 20h
0x1800bf3ea  mov     rbx, rcx
0x1800bf3ed  sub     rcx, 0FFFFFFFFFFFFFF80h
0x1800bf3f1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800bf3f6  mov     rcx, [rbx+78h]; string
0x1800bf3fa  call    cs:__imp_WindowsDeleteString
0x1800bf400  mov     qword ptr [rbx+78h], 0
0x1800bf408  mov     rcx, [rbx+70h]; string
0x1800bf40c  call    cs:__imp_WindowsDeleteString
0x1800bf412  mov     qword ptr [rbx+70h], 0
0x1800bf41a  mov     rcx, [rbx+68h]; string
0x1800bf41e  call    cs:__imp_WindowsDeleteString
0x1800bf424  mov     qword ptr [rbx+68h], 0
0x1800bf42c  mov     rcx, [rbx+60h]; string
0x1800bf430  call    cs:__imp_WindowsDeleteString
0x1800bf436  mov     qword ptr [rbx+60h], 0
0x1800bf43e  mov     rcx, [rbx+58h]; string
0x1800bf442  call    cs:__imp_WindowsDeleteString
0x1800bf448  mov     qword ptr [rbx+58h], 0
0x1800bf450  mov     rcx, [rbx+50h]; string
0x1800bf454  call    cs:__imp_WindowsDeleteString
0x1800bf45a  mov     qword ptr [rbx+50h], 0
0x1800bf462  mov     rcx, [rbx+48h]; string
0x1800bf466  call    cs:__imp_WindowsDeleteString
0x1800bf46c  mov     qword ptr [rbx+48h], 0
0x1800bf474  mov     rcx, [rbx+40h]; string
0x1800bf478  call    cs:__imp_WindowsDeleteString
0x1800bf47e  mov     rcx, rbx
0x1800bf481  mov     qword ptr [rbx+40h], 0
0x1800bf489  add     rsp, 20h
0x1800bf48d  pop     rbx
0x1800bf48e  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IKeyValuePair@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *>,Microsoft::WRL::FtmBase>(void)
```
