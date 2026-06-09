# PrintCore::RegHelpers::SetDwordValue(HKEY__ * const &,ushort const *,ushort const *,ulong)

- ea: `0x1800124ac`
- end: `0x1800124f1`
- name: `?SetDwordValue@RegHelpers@PrintCore@@SAJAEBQEAUHKEY__@@PEBG1K@Z`
- size: `69`
- prototype: `LSTATUS __fastcall(HKEY *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800121c0`
- `0x180012a50`
- `0x180012df8`

## callees

- `0x1800124ac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800124da`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800124da`

## pseudocode

```c
LSTATUS __fastcall PrintCore::RegHelpers::SetDwordValue(
        HKEY *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4)
{
  LSTATUS result; // eax
  int v5; // [rsp+58h] [rbp+20h] BYREF

  v5 = a4;
  result = RegSetKeyValueW(
             *a1,
             L"SYSTEM\\CurrentControlSet\\Control\\Print",
             L"WindowsProtectedPrintState",
             4u,
             &v5,
             4u);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800124ac  mov     r11, rsp
0x1800124af  mov     [r11+20h], r9d
0x1800124b3  sub     rsp, 38h
0x1800124b7  mov     rcx, [rcx]; hKey
0x1800124ba  lea     rax, [r11+20h]
0x1800124be  mov     r9d, 4; dwType
0x1800124c4  lea     r8, ValueName; "WindowsProtectedPrintState"
0x1800124cb  mov     [r11-10h], r9d
0x1800124cf  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Control\\Pri"...
0x1800124d6  mov     [r11-18h], rax
0x1800124da  call    cs:__imp_RegSetKeyValueW
0x1800124e0  test    eax, eax
0x1800124e2  jle     short loc_1800124EC
0x1800124e4  movzx   eax, ax
0x1800124e7  or      eax, 80070000h
0x1800124ec  add     rsp, 38h
0x1800124f0  retn
```
