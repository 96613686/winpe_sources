# FireHelpEntryDataPoint(ushort const *)

- ea: `0x18000659c`
- end: `0x1800065cf`
- name: `?FireHelpEntryDataPoint@@YAXPEBG@Z`
- size: `51`
- prototype: `void __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800134a0`
- `0x18001caf8`

## import_xrefs

- `ntdll!WinSqmAddToStream` at `0x1800065c4`
- `ntdll!WinSqmAddToStream` at `0x1800065c4`

## string_xrefs

- `0x1800065aa`: `HELP_ENTRY_ID_EASE_OF_ACCESS_HELP_MENU`

## pseudocode

```c
void __fastcall FireHelpEntryDataPoint(const unsigned __int16 *a1)
{
  int v1; // [rsp+20h] [rbp-18h] BYREF
  const wchar_t *v2; // [rsp+28h] [rbp-10h]

  v1 = 2;
  v2 = L"HELP_ENTRY_ID_EASE_OF_ACCESS_HELP_MENU";
  ((void (__fastcall *)(_QWORD, __int64, __int64, int *))WinSqmAddToStream)(0, 911, 1, &v1);
}

```

## disassembly

```asm
0x18000659c  sub     rsp, 38h
0x1800065a0  xor     ecx, ecx
0x1800065a2  mov     [rsp+38h+var_18], 2
0x1800065aa  lea     rax, aHelpEntryIdEas; "HELP_ENTRY_ID_EASE_OF_ACCESS_HELP_MENU"
0x1800065b1  mov     edx, 38Fh
0x1800065b6  lea     r9, [rsp+38h+var_18]
0x1800065bb  mov     [rsp+38h+var_10], rax
0x1800065c0  lea     r8d, [rcx+1]
0x1800065c4  call    cs:__imp_WinSqmAddToStream
0x1800065ca  add     rsp, 38h
0x1800065ce  retn
```
