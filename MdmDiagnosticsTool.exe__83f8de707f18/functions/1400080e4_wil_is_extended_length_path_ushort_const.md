# wil::is_extended_length_path(ushort const *)

- ea: `0x1400080e4`
- end: `0x140008105`
- name: `?is_extended_length_path@wil@@YA_NPEBG@Z`
- size: `33`
- prototype: `bool __fastcall(wil *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140005e44`

## callees

- `0x140009cd2`

## pseudocode

```c
bool __fastcall wil::is_extended_length_path(const wchar_t *this, const unsigned __int16 *a2)
{
  return wcsncmp_0(this, L"\\\\?\\", 4u) == 0;
}

```

## disassembly

```asm
0x1400080e4  sub     rsp, 28h
0x1400080e8  mov     r8d, 4; MaxCount
0x1400080ee  lea     rdx, String2; "\\\\?\\"
0x1400080f5  call    wcsncmp_0
0x1400080fa  test    eax, eax
0x1400080fc  setz    al
0x1400080ff  add     rsp, 28h
0x140008103  retn
```
