# _FreeImage

- ea: `0x18001aa70`
- end: `0x18001aa94`
- name: `_FreeImage`
- size: `36`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1800050b0`
- `0x180006da0`
- `0x180007d60`
- `0x18000ccf0`
- `0x18001a61c`

## callees

- `0x18001aa70`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001aa82`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001aa82`

## pseudocode

```c
BOOL __fastcall FreeImage(HMODULE a1)
{
  BOOL result; // eax

  if ( a1 != (HMODULE)g_hInstance )
  {
    if ( a1 )
      return FreeLibrary(a1);
  }
  return result;
}

```

## disassembly

```asm
0x18001aa70  sub     rsp, 28h
0x18001aa74  cmp     rcx, cs:g_hInstance
0x18001aa7b  jz      short loc_18001AA8E
0x18001aa7d  test    rcx, rcx
0x18001aa80  jz      short loc_18001AA8E
0x18001aa82  call    cs:__imp_FreeLibrary
0x18001aa89  nop     dword ptr [rax+rax+00h]
0x18001aa8e  add     rsp, 28h
0x18001aa92  retn
```
