# wil::is_extended_length_path(ushort const *)

- ea: `0x140007cb0`
- end: `0x140007cd0`
- name: `?is_extended_length_path@wil@@YA_NPEBG@Z`
- size: `32`
- prototype: `bool __fastcall(const wchar_t *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140005b1c`

## callees

- `0x1400096a2`

## pseudocode

```c
bool __fastcall wil::is_extended_length_path(const wchar_t *this, const unsigned __int16 *a2)
{
  return wcsncmp_0(this, L"\\\\?\\", 4u) == 0;
}

```

## disassembly

```asm
0x140007cb0  sub     rsp, 28h
0x140007cb4  mov     r8d, 4; MaxCount
0x140007cba  lea     rdx, String2; "\\\\?\\"
0x140007cc1  call    wcsncmp_0
0x140007cc6  test    eax, eax
0x140007cc8  setz    al
0x140007ccb  add     rsp, 28h
0x140007ccf  retn
```
