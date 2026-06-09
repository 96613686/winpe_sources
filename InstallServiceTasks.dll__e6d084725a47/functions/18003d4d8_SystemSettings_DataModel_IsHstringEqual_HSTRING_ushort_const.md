# SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)

- ea: `0x18003d4d8`
- end: `0x18003d50f`
- name: `?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z`
- size: `55`
- prototype: `bool(SystemSettings::DataModel *__hidden this, HSTRING, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003cb00`
- `0x18003d110`
- `0x18003e0e0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003d4fd`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003d4fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003d4e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003d4e3`

## pseudocode

```c
bool __fastcall SystemSettings::DataModel::IsHstringEqual(
        SystemSettings::DataModel *this,
        const WCHAR *a2,
        const unsigned __int16 *a3)
{
  const WCHAR *StringRawBuffer; // rax

  StringRawBuffer = WindowsGetStringRawBuffer((HSTRING)this, 0);
  return CompareStringOrdinal(StringRawBuffer, -1, a2, -1, 0) == 2;
}

```

## disassembly

```asm
0x18003d4d8  push    rbx
0x18003d4da  sub     rsp, 30h
0x18003d4de  mov     rbx, rdx
0x18003d4e1  xor     edx, edx; length
0x18003d4e3  call    cs:__imp_WindowsGetStringRawBuffer
0x18003d4e9  or      edx, 0FFFFFFFFh; cchCount1
0x18003d4ec  mov     [rsp+38h+bIgnoreCase], 0; bIgnoreCase
0x18003d4f4  mov     r9d, edx; cchCount2
0x18003d4f7  mov     rcx, rax; lpString1
0x18003d4fa  mov     r8, rbx; lpString2
0x18003d4fd  call    cs:__imp_CompareStringOrdinal
0x18003d503  cmp     eax, 2
0x18003d506  setz    al
0x18003d509  add     rsp, 30h
0x18003d50d  pop     rbx
0x18003d50e  retn
```
