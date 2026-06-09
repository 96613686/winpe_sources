# StateRepository::Localization::CreateMrtString(HSTRING__ *,HSTRING__ * *)

- ea: `0x180009d58`
- end: `0x180009d79`
- name: `?CreateMrtString@Localization@StateRepository@@YAJPEAUHSTRING__@@PEAPEAU3@@Z`
- size: `33`
- prototype: `int(StateRepository::Localization *__hidden this, HSTRING, HSTRING *)`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x180008270`
- `0x1800082d0`
- `0x180008330`
- `0x180008480`
- `0x1800085d0`
- `0x180008720`
- `0x180008870`
- `0x1800089c0`
- `0x180008a20`
- `0x180009040`
- `0x1800090a0`
- `0x180009100`
- `0x180009250`

## callees

- `0x180009d80`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180009d63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180009d63`

## pseudocode

```c
__int64 __fastcall StateRepository::Localization::CreateMrtString(
        StateRepository::Localization *this,
        unsigned __int16 *a2,
        HSTRING *a3)
{
  StateRepository::Localization *StringRawBuffer; // rax
  HSTRING *v5; // r8

  StringRawBuffer = (StateRepository::Localization *)WindowsGetStringRawBuffer((HSTRING)this, 0);
  return StateRepository::Localization::CreateMrtString(StringRawBuffer, a2, v5);
}

```

## disassembly

```asm
0x180009d58  push    rbx
0x180009d5a  sub     rsp, 20h
0x180009d5e  mov     rbx, rdx
0x180009d61  xor     edx, edx; length
0x180009d63  call    cs:__imp_WindowsGetStringRawBuffer
0x180009d69  mov     rcx, rax; this
0x180009d6c  mov     rdx, rbx; unsigned __int16 *
0x180009d6f  add     rsp, 20h
0x180009d73  pop     rbx
0x180009d74  jmp     ?CreateMrtString@Localization@StateRepository@@YAJPEBGPEAPEAUHSTRING__@@@Z; StateRepository::Localization::CreateMrtString(ushort const *,HSTRING__ * *)
```
