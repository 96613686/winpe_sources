# StateRepository::Localization::CreateMrtUri(HSTRING__ *,Windows::Foundation::IUriRuntimeClass * *)

- ea: `0x180009f04`
- end: `0x180009f25`
- name: `?CreateMrtUri@Localization@StateRepository@@YAJPEAUHSTRING__@@PEAPEAUIUriRuntimeClass@Foundation@Windows@@@Z`
- size: `33`
- prototype: `int __fastcall(StateRepository::Localization *this, const unsigned __int16 *, struct Windows::Foundation::IUriRuntimeClass **)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180008420`
- `0x180008570`
- `0x1800086c0`
- `0x180008810`
- `0x180008960`
- `0x180008b10`
- `0x1800091f0`

## callees

- `0x180009f2c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180009f0f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180009f0f`

## pseudocode

```c
int __fastcall StateRepository::Localization::CreateMrtUri(
        StateRepository::Localization *this,
        const unsigned __int16 *a2,
        struct Windows::Foundation::IUriRuntimeClass **a3)
{
  StateRepository::Localization *StringRawBuffer; // rax
  struct Windows::Foundation::IUriRuntimeClass **v5; // r8

  StringRawBuffer = (StateRepository::Localization *)WindowsGetStringRawBuffer((HSTRING)this, 0);
  return StateRepository::Localization::CreateMrtUri(StringRawBuffer, a2, v5);
}

```

## disassembly

```asm
0x180009f04  push    rbx
0x180009f06  sub     rsp, 20h
0x180009f0a  mov     rbx, rdx
0x180009f0d  xor     edx, edx; length
0x180009f0f  call    cs:__imp_WindowsGetStringRawBuffer
0x180009f15  mov     rcx, rax; this
0x180009f18  mov     rdx, rbx; unsigned __int16 *
0x180009f1b  add     rsp, 20h
0x180009f1f  pop     rbx
0x180009f20  jmp     ?CreateMrtUri@Localization@StateRepository@@YAJPEBGPEAPEAUIUriRuntimeClass@Foundation@Windows@@@Z; StateRepository::Localization::CreateMrtUri(ushort const *,Windows::Foundation::IUriRuntimeClass * *)
```
