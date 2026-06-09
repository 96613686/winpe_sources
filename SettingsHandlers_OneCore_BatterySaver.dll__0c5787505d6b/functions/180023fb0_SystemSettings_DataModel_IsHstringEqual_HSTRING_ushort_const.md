# SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)

- ea: `0x180023fb0`
- end: `0x180023fe7`
- name: `?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z`
- size: `55`
- prototype: `bool(SystemSettings::DataModel *__hidden this, HSTRING, const unsigned __int16 *)`
- caller_count: `22`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001f750`
- `0x18001f7c0`
- `0x18001f8a0`
- `0x18001fc10`
- `0x18001fcf0`
- `0x18001fd70`
- `0x18001fef0`
- `0x1800213b0`
- `0x180021470`
- `0x180021640`
- `0x180021770`
- `0x180021970`
- `0x180021da0`
- `0x180021fc0`
- `0x1800286d0`
- `0x180028b50`
- `0x18002d8a0`
- `0x18002fe90`
- `0x1800361f0`
- `0x18003ae30`
- `0x18003d880`
- `0x18003db80`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180023fd5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180023fd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180023fbb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180023fbb`

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
0x180023fb0  push    rbx
0x180023fb2  sub     rsp, 30h
0x180023fb6  mov     rbx, rdx
0x180023fb9  xor     edx, edx; length
0x180023fbb  call    cs:__imp_WindowsGetStringRawBuffer
0x180023fc1  or      edx, 0FFFFFFFFh; cchCount1
0x180023fc4  mov     [rsp+38h+bIgnoreCase], 0; bIgnoreCase
0x180023fcc  mov     r9d, edx; cchCount2
0x180023fcf  mov     rcx, rax; lpString1
0x180023fd2  mov     r8, rbx; lpString2
0x180023fd5  call    cs:__imp_CompareStringOrdinal
0x180023fdb  cmp     eax, 2
0x180023fde  setz    al
0x180023fe1  add     rsp, 30h
0x180023fe5  pop     rbx
0x180023fe6  retn
```
