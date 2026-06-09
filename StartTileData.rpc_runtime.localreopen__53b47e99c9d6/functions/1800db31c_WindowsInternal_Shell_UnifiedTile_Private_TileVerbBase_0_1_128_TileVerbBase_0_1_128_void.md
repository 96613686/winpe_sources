# WindowsInternal::Shell::UnifiedTile::Private::TileVerbBase<0,1,128,>::~TileVerbBase<0,1,128,>(void)

- ea: `0x1800db31c`
- end: `0x1800db3cb`
- name: `??1?$TileVerbBase@$0A@$00$0IA@$$V@Private@UnifiedTile@Shell@WindowsInternal@@MEAA@XZ`
- size: `175`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800db24c`
- `0x1802db030`

## callees

- `0x18000ce94`
- `0x1800c3188`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db332`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db344`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db356`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db368`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db37a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db38c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db39e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db3b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db332`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db344`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db356`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db368`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db37a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db38c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db39e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800db3b0`

## pseudocode

```c
__int64 __fastcall WindowsInternal::Shell::UnifiedTile::Private::TileVerbBase<0,1,128,>::~TileVerbBase<0,1,128,>(
        HSTRING *a1)
{
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(a1 + 12);
  WindowsDeleteString(a1[11]);
  a1[11] = 0;
  WindowsDeleteString(a1[10]);
  a1[10] = 0;
  WindowsDeleteString(a1[9]);
  a1[9] = 0;
  WindowsDeleteString(a1[8]);
  a1[8] = 0;
  WindowsDeleteString(a1[7]);
  a1[7] = 0;
  WindowsDeleteString(a1[6]);
  a1[6] = 0;
  WindowsDeleteString(a1[5]);
  a1[5] = 0;
  WindowsDeleteString(a1[4]);
  a1[4] = 0;
  return Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,WindowsInternal::Shell::UnifiedTile::VisualCache::IStartVisualCacheWriterLock>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,WindowsInternal::Shell::UnifiedTile::VisualCache::IStartVisualCacheWriterLock>(a1);
}

```

## disassembly

```asm
0x1800db31c  push    rbx
0x1800db31e  sub     rsp, 20h
0x1800db322  mov     rbx, rcx
0x1800db325  add     rcx, 60h ; '`'
0x1800db329  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800db32e  mov     rcx, [rbx+58h]; string
0x1800db332  call    cs:__imp_WindowsDeleteString
0x1800db338  mov     qword ptr [rbx+58h], 0
0x1800db340  mov     rcx, [rbx+50h]; string
0x1800db344  call    cs:__imp_WindowsDeleteString
0x1800db34a  mov     qword ptr [rbx+50h], 0
0x1800db352  mov     rcx, [rbx+48h]; string
0x1800db356  call    cs:__imp_WindowsDeleteString
0x1800db35c  mov     qword ptr [rbx+48h], 0
0x1800db364  mov     rcx, [rbx+40h]; string
0x1800db368  call    cs:__imp_WindowsDeleteString
0x1800db36e  mov     qword ptr [rbx+40h], 0
0x1800db376  mov     rcx, [rbx+38h]; string
0x1800db37a  call    cs:__imp_WindowsDeleteString
0x1800db380  mov     qword ptr [rbx+38h], 0
0x1800db388  mov     rcx, [rbx+30h]; string
0x1800db38c  call    cs:__imp_WindowsDeleteString
0x1800db392  mov     qword ptr [rbx+30h], 0
0x1800db39a  mov     rcx, [rbx+28h]; string
0x1800db39e  call    cs:__imp_WindowsDeleteString
0x1800db3a4  mov     qword ptr [rbx+28h], 0
0x1800db3ac  mov     rcx, [rbx+20h]; string
0x1800db3b0  call    cs:__imp_WindowsDeleteString
0x1800db3b6  mov     rcx, rbx
0x1800db3b9  mov     qword ptr [rbx+20h], 0
0x1800db3c1  add     rsp, 20h
0x1800db3c5  pop     rbx
0x1800db3c6  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIStartVisualCacheWriterLock@VisualCache@UnifiedTile@Shell@WindowsInternal@@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,WindowsInternal::Shell::UnifiedTile::VisualCache::IStartVisualCacheWriterLock>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,WindowsInternal::Shell::UnifiedTile::VisualCache::IStartVisualCacheWriterLock>(void)
```
