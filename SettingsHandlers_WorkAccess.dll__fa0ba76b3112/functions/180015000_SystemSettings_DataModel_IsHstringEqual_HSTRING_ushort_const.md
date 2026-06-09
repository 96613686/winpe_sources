# SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)

- ea: `0x180015000`
- end: `0x180015044`
- name: `?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z`
- size: `68`
- prototype: `bool(SystemSettings::DataModel *__hidden this, HSTRING, const unsigned __int16 *)`
- caller_count: `24`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012b50`
- `0x180012bc0`
- `0x180012ce0`
- `0x180014080`
- `0x180017300`
- `0x18001b108`
- `0x180025cf0`
- `0x180025e30`
- `0x180026140`
- `0x180026480`
- `0x1800331b0`
- `0x1800333e0`
- `0x1800335a0`
- `0x180033850`
- `0x1800338c0`
- `0x180033920`
- `0x1800339a0`
- `0x180033c70`
- `0x180033d00`
- `0x18003e2f0`
- `0x18003e780`
- `0x180040ac0`
- `0x180042080`
- `0x180043740`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001502b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001502b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001500b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001500b`

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
0x180015000  push    rbx
0x180015002  sub     rsp, 30h
0x180015006  mov     rbx, rdx
0x180015009  xor     edx, edx; length
0x18001500b  call    cs:__imp_WindowsGetStringRawBuffer
0x180015012  nop     dword ptr [rax+rax+00h]
0x180015017  or      edx, 0FFFFFFFFh; cchCount1
0x18001501a  mov     [rsp+38h+bIgnoreCase], 0; bIgnoreCase
0x180015022  mov     r9d, edx; cchCount2
0x180015025  mov     rcx, rax; lpString1
0x180015028  mov     r8, rbx; lpString2
0x18001502b  call    cs:__imp_CompareStringOrdinal
0x180015032  nop     dword ptr [rax+rax+00h]
0x180015037  cmp     eax, 2
0x18001503a  setz    al
0x18001503d  add     rsp, 30h
0x180015041  pop     rbx
0x180015042  retn
```
