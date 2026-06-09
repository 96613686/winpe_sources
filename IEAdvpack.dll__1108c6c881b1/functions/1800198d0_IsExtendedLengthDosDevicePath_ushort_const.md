# IsExtendedLengthDosDevicePath(ushort const *)

- ea: `0x1800198d0`
- end: `0x1800198f0`
- name: `?IsExtendedLengthDosDevicePath@@YA_NPEBG@Z`
- size: `32`
- prototype: `bool __fastcall(const unsigned __int16 *)`
- caller_count: `24`
- callee_count: `1`
- tags: ``

## callers

- `0x180001e40`
- `0x180002d50`
- `0x180004880`
- `0x180009c14`
- `0x18000a918`
- `0x18000b8f0`
- `0x18000c3b8`
- `0x18000c760`
- `0x18000c99c`
- `0x18000cc80`
- `0x18000ced8`
- `0x18000d184`
- `0x18000e060`
- `0x18000f7b0`
- `0x180010050`
- `0x1800115b0`
- `0x180011940`
- `0x180013c98`
- `0x180015ef8`
- `0x180017434`
- `0x180017bcc`
- `0x180019fb8`
- `0x18001b524`
- `0x18001b634`

## callees

- `0x18001b95a`

## pseudocode

```c
bool __fastcall IsExtendedLengthDosDevicePath(const unsigned __int16 *a1)
{
  return wcsncmp_0(a1, L"\\\\?\\", 4u) == 0;
}

```

## disassembly

```asm
0x1800198d0  sub     rsp, 28h
0x1800198d4  mov     r8d, 4; MaxCount
0x1800198da  lea     rdx, asc_180021228; "\\\\?\\"
0x1800198e1  call    wcsncmp_0
0x1800198e6  test    eax, eax
0x1800198e8  setz    al
0x1800198eb  add     rsp, 28h
0x1800198ef  retn
```
