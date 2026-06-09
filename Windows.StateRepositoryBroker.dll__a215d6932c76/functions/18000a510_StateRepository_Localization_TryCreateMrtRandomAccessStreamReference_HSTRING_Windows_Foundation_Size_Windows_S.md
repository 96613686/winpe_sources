# StateRepository::Localization::TryCreateMrtRandomAccessStreamReference(HSTRING__ *,Windows::Foundation::Size,Windows::Storage::Streams::IRandomAccessStreamReference * *)

- ea: `0x18000a510`
- end: `0x18000a545`
- name: `?TryCreateMrtRandomAccessStreamReference@Localization@StateRepository@@YAJPEAUHSTRING__@@USize@Foundation@Windows@@PEAPEAUIRandomAccessStreamReference@Streams@Storage@6@@Z`
- size: `53`
- prototype: `__int64 __fastcall(HSTRING, __int64, _QWORD *)`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x180008390`
- `0x1800084e0`
- `0x180008630`
- `0x180008780`
- `0x1800088d0`
- `0x180008a80`
- `0x180008e00`
- `0x180008e60`
- `0x180008ec0`
- `0x180008f20`
- `0x180008f80`
- `0x180008fe0`
- `0x180009160`

## callees

- `0x18000a54c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000a525`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000a525`

## pseudocode

```c
__int64 __fastcall StateRepository::Localization::TryCreateMrtRandomAccessStreamReference(
        HSTRING a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned __int16 *StringRawBuffer; // rax

  StringRawBuffer = (unsigned __int16 *)WindowsGetStringRawBuffer(a1, 0);
  return StateRepository::Localization::TryCreateMrtRandomAccessStreamReference(StringRawBuffer, a2, a3);
}

```

## disassembly

```asm
0x18000a510  push    rbx
0x18000a512  sub     rsp, 30h
0x18000a516  movaps  [rsp+38h+var_18], xmm6
0x18000a51b  mov     rbx, r8
0x18000a51e  movq    xmm6, rdx
0x18000a523  xor     edx, edx; length
0x18000a525  call    cs:__imp_WindowsGetStringRawBuffer
0x18000a52b  mov     r8, rbx
0x18000a52e  movq    rdx, xmm6
0x18000a533  mov     rcx, rax
0x18000a536  movaps  xmm6, [rsp+38h+var_18]
0x18000a53b  add     rsp, 30h
0x18000a53f  pop     rbx
0x18000a540  jmp     ?TryCreateMrtRandomAccessStreamReference@Localization@StateRepository@@YAJPEBGUSize@Foundation@Windows@@PEAPEAUIRandomAccessStreamReference@Streams@Storage@5@@Z; StateRepository::Localization::TryCreateMrtRandomAccessStreamReference(ushort const *,Windows::Foundation::Size,Windows::Storage::Streams::IRandomAccessStreamReference * *)
```
