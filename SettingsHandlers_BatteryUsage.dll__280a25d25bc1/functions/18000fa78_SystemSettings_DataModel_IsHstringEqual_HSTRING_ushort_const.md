# SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)

- ea: `0x18000fa78`
- end: `0x18000faaf`
- name: `?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z`
- size: `55`
- prototype: `bool(SystemSettings::DataModel *__hidden this, HSTRING, const unsigned __int16 *)`
- caller_count: `22`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ef50`
- `0x18000efc0`
- `0x18000f720`
- `0x180010830`
- `0x180018df0`
- `0x180019580`
- `0x18001d990`
- `0x18001da80`
- `0x1800207a0`
- `0x180020ab0`
- `0x180020cf0`
- `0x180026ac0`
- `0x18002cd90`
- `0x1800325c0`
- `0x180033fd0`
- `0x180034040`
- `0x180034250`
- `0x18004a9d0`
- `0x18004aab0`
- `0x18004bcb0`
- `0x18004ce90`
- `0x18004e2b0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000fa9d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000fa9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000fa83`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000fa83`

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
0x18000fa78  push    rbx
0x18000fa7a  sub     rsp, 30h
0x18000fa7e  mov     rbx, rdx
0x18000fa81  xor     edx, edx; length
0x18000fa83  call    cs:__imp_WindowsGetStringRawBuffer
0x18000fa89  or      edx, 0FFFFFFFFh; cchCount1
0x18000fa8c  mov     [rsp+38h+bIgnoreCase], 0; bIgnoreCase
0x18000fa94  mov     r9d, edx; cchCount2
0x18000fa97  mov     rcx, rax; lpString1
0x18000fa9a  mov     r8, rbx; lpString2
0x18000fa9d  call    cs:__imp_CompareStringOrdinal
0x18000faa3  cmp     eax, 2
0x18000faa6  setz    al
0x18000faa9  add     rsp, 30h
0x18000faad  pop     rbx
0x18000faae  retn
```
