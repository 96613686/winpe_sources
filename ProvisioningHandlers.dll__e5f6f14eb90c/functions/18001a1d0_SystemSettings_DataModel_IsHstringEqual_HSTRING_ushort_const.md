# SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)

- ea: `0x18001a1d0`
- end: `0x18001a214`
- name: `?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z`
- size: `68`
- prototype: `bool(SystemSettings::DataModel *__hidden this, HSTRING, const unsigned __int16 *)`
- caller_count: `10`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016610`
- `0x1800168f0`
- `0x1800169d0`
- `0x180016a60`
- `0x180017a20`
- `0x180018410`
- `0x1800184d0`
- `0x180018620`
- `0x18001d170`
- `0x18001d350`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001a1fb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001a1fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001a1db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001a1db`

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
0x18001a1d0  push    rbx
0x18001a1d2  sub     rsp, 30h
0x18001a1d6  mov     rbx, rdx
0x18001a1d9  xor     edx, edx; length
0x18001a1db  call    cs:__imp_WindowsGetStringRawBuffer
0x18001a1e2  nop     dword ptr [rax+rax+00h]
0x18001a1e7  or      edx, 0FFFFFFFFh; cchCount1
0x18001a1ea  mov     [rsp+38h+bIgnoreCase], 0; bIgnoreCase
0x18001a1f2  mov     r9d, edx; cchCount2
0x18001a1f5  mov     rcx, rax; lpString1
0x18001a1f8  mov     r8, rbx; lpString2
0x18001a1fb  call    cs:__imp_CompareStringOrdinal
0x18001a202  nop     dword ptr [rax+rax+00h]
0x18001a207  cmp     eax, 2
0x18001a20a  setz    al
0x18001a20d  add     rsp, 30h
0x18001a211  pop     rbx
0x18001a212  retn
```
