# SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)

- ea: `0x1800168b4`
- end: `0x1800168eb`
- name: `?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z`
- size: `55`
- prototype: `bool(SystemSettings::DataModel *__hidden this, HSTRING, const unsigned __int16 *)`
- caller_count: `16`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d9a8`
- `0x180013f50`
- `0x180014490`
- `0x180014cf0`
- `0x180014db0`
- `0x180018de0`
- `0x18001b9c0`
- `0x18001ba80`
- `0x180027050`
- `0x180027f50`
- `0x1800281d0`
- `0x18002f740`
- `0x18002faf0`
- `0x1800326a4`
- `0x180037cc0`
- `0x180050050`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800168bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800168bf`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800168d9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800168d9`

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
0x1800168b4  push    rbx
0x1800168b6  sub     rsp, 30h
0x1800168ba  mov     rbx, rdx
0x1800168bd  xor     edx, edx; length
0x1800168bf  call    cs:__imp_WindowsGetStringRawBuffer
0x1800168c5  or      edx, 0FFFFFFFFh; cchCount1
0x1800168c8  mov     [rsp+38h+bIgnoreCase], 0; bIgnoreCase
0x1800168d0  mov     r9d, edx; cchCount2
0x1800168d3  mov     rcx, rax; lpString1
0x1800168d6  mov     r8, rbx; lpString2
0x1800168d9  call    cs:__imp_CompareStringOrdinal
0x1800168df  cmp     eax, 2
0x1800168e2  setz    al
0x1800168e5  add     rsp, 30h
0x1800168e9  pop     rbx
0x1800168ea  retn
```
