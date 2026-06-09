# Common::String::CaseInsensitiveCompare(ushort const *,ulong,ushort const *,ulong)

- ea: `0x14000e1a4`
- end: `0x14000e1df`
- name: `?CaseInsensitiveCompare@String@Common@@SAHPEBGK0K@Z`
- size: `59`
- prototype: `__int64 __fastcall(LPCWCH lpString1, int, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000e1e8`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14000e1d1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14000e1d1`

## pseudocode

```c
__int64 __fastcall Common::String::CaseInsensitiveCompare(LPCWCH lpString1, int a2, const unsigned __int16 *a3, int a4)
{
  const WCHAR *v4; // rax
  const WCHAR *v5; // r8

  v4 = &qword_140010DA8;
  v5 = &qword_140010DA8;
  if ( a4 )
    v5 = L".MSI";
  if ( a2 )
    v4 = lpString1;
  return (unsigned int)(CompareStringOrdinal(v4, a2, v5, a4, 1) - 2);
}

```

## disassembly

```asm
0x14000e1a4  sub     rsp, 38h
0x14000e1a8  test    r9d, r9d
0x14000e1ab  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x14000e1b3  lea     rax, qword_140010DA8
0x14000e1ba  mov     r8, rax
0x14000e1bd  lea     r10, Buf2; ".MSI"
0x14000e1c4  cmovnz  r8, r10; lpString2
0x14000e1c8  test    edx, edx
0x14000e1ca  cmovnz  rax, rcx
0x14000e1ce  mov     rcx, rax; lpString1
0x14000e1d1  call    cs:__imp_CompareStringOrdinal
0x14000e1d7  sub     eax, 2
0x14000e1da  add     rsp, 38h
0x14000e1de  retn
```
