# SystemSettings::PenSettings::IsOemUriAlreadyDisplayed(ushort const *)

- ea: `0x1800543f4`
- end: `0x18005441e`
- name: `?IsOemUriAlreadyDisplayed@PenSettings@SystemSettings@@YA_NPEBG@Z`
- size: `42`
- prototype: `bool __fastcall(SystemSettings::PenSettings *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180027350`
- `0x180028910`
- `0x18002faf0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18005440d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18005440d`

## pseudocode

```c
bool __fastcall SystemSettings::PenSettings::IsOemUriAlreadyDisplayed(const WCHAR *this, const unsigned __int16 *a2)
{
  return CompareStringOrdinal(this, -1, L"ms-screenclip:?type=snipping", -1, 1) != 2;
}

```

## disassembly

```asm
0x1800543f4  sub     rsp, 38h
0x1800543f8  or      edx, 0FFFFFFFFh; cchCount1
0x1800543fb  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x180054403  mov     r9d, edx; cchCount2
0x180054406  lea     r8, aMsScreenclipTy; "ms-screenclip:?type=snipping"
0x18005440d  call    cs:__imp_CompareStringOrdinal
0x180054413  cmp     eax, 2
0x180054416  setnz   al
0x180054419  add     rsp, 38h
0x18005441d  retn
```
